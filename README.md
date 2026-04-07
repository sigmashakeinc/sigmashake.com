# sigmashake.com

Demo [asciicast v2](https://docs.asciinema.org/manual/asciicast/v2/) terminal recordings for [sigmashake.com](https://sigmashake.com).

These `.cast` files are served via `raw.githubusercontent.com` and rendered by [asciinema-player](https://github.com/asciinema/asciinema-player) on the SigmaShake landing page.

## Cast Files

| File | Rule | What It Blocks |
|------|------|----------------|
| `no-rm-rf.cast` | Block Recursive Delete | `rm -rf` commands |
| `no-chmod-777.cast` | Block World-Writable Permissions | `chmod 777` |
| `no-curl-pipe-shell.cast` | Block Curl-Pipe-Shell | `curl ... \| bash` |
| `no-git-add-all.cast` | Block git add -A | Mass file staging |
| `no-stderr-redirect.cast` | Block stderr redirect | `2>&1` suppression |
| `no-sourcemap-in-tsconfig.cast` | Block Source Maps | Production sourcemaps |
| `no-secrets-in-code.cast` | Block Hardcoded Secrets | API keys in source |
| `no-npm-install-global.cast` | Block Global npm Install | `npm install -g` |
| `ask-sudo.cast` | Require Approval for sudo | Privilege escalation |
| `no-docker-privileged.cast` | Block Docker --privileged | Container escape risk |

## Usage

Each cast simulates a Claude Code session where SigmaShake's `ssg hook eval` hook blocks a dangerous action in real-time.

```html
<script src="https://cdn.jsdelivr.net/npm/asciinema-player@3/dist/bundle/asciinema-player.min.js"></script>
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/asciinema-player@3/dist/bundle/asciinema-player.css">

<div id="demo"></div>
<script>
  AsciinemaPlayer.create(
    'https://raw.githubusercontent.com/sigmashakeinc/sigmashake.com/main/casts/no-rm-rf.cast',
    document.getElementById('demo'),
    { autoPlay: true, theme: 'monokai', fit: 'width' }
  );
</script>
```

## License

MIT — [SigmaShake Inc.](https://sigmashake.com)
