<h1 align="center">sevenv1 - About ME!</h1>

```python
from __future__ import annotations
from typing import Dict, List, Any
from functools import cached_property, lru_cache
from dataclasses import dataclass, field
from datetime import datetime
import json

@dataclass
class Project:
    name: str
    url: str
    technologies: List[str] = field(default_factory=list)
    
    def to_dict(self) -> Dict[str, Any]:
        return {
            "name": self.name,
            "url": self.url,
            "technologies": self.technologies
        }

class sevenv1:
    @cached_property
    def age(self) -> int:
        return datetime.now().year - 2008
        
    @property
    def identity(self) -> Dict[str, Any]:
        return {"real_name": "Lebron James", "age": self.age}
    
    @lru_cache(maxsize=8)
    def code(self) -> Dict[str, Any]:
        return {
            "languages": {
                "expert": ["python"],
                "proficient": ["html", "css", "javascript", "typescript"],
                "beginner": ["lua", "php", "golang"]
            },
            "specialties": ["web/app reverse engineering", "discord bots & tools", "web development"]
        }
        
    def projects(self) -> List[Project]:
        return [
            Project(
                name="idk i jump around on discord stuff alot",
                url="https://discord.com/",
                technologies=["Python", "GO", "Javascript"]
            ),
            Project(
                name="Tigron AutoAdvertiser (Im Not The Founder)",
                url="https://tigron.tools/",
                technologies=["Python", "GO", "Javascript"]
            ),
            Project(
                name="Custom Discord Bots made by me!",
                url="https://discord.gg/custombots",
                technologies=["Python", "Javascript"]
            )
        ]
    
    @property
    def socials(self) -> Dict[str, str]:
        return {
            "GitHub": "https://github.com/sevenv1",
            "YouTube": "https://www.youtube.com/@sevenv1",
            "Discord": "https://discord.com/users/832746701525745724" + " (got termed might change this alot)"
        }

if __name__ == "__main__":
    dev = sevenv1()
    output = {
        "identity": dev.identity,
        "code": dev.code(),
        "projects": [p.to_dict() for p in dev.projects()],
        "socials": dev.socials
    }
    print(json.dumps(output, indent=4))
```
[![SKILLS/LANGUAGES](https://skillicons.dev/icons?i=js,html,css,ts,py,go,php,css,lua)](https://skillicons.dev)

![PROFILE VIEWS](https://komarev.com/ghpvc/?username=sevenv1&color=FF0000&style=for-the-badge)
