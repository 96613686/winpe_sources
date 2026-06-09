# CTempGlassTerminal::Connected(ITSSession *)

- ea: `0x18002fc20`
- end: `0x18002fcc6`
- name: `?Connected@CTempGlassTerminal@@UEAAJPEAUITSSession@@@Z`
- size: `166`
- prototype: `__int64 __fastcall(CTempGlassTerminal *__hidden this, struct ITSSession *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800077a0`
- `0x18002fc20`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18002fc93`
- `ntdll!RtlReleaseResource` at `0x18002fc93`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002fc50`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002fc50`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002fca7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002fca7`

## string_xrefs

- `0x18002fc6b`: `CTempGlassTerminal connect is call after terminal has start terminate`

## pseudocode

```c

```
