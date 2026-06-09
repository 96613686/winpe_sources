# CTempGlassTerminal::Connected(ITSSession *)

- ea: `0x18002dbf0`
- end: `0x18002dc83`
- name: `?Connected@CTempGlassTerminal@@UEAAJPEAUITSSession@@@Z`
- size: `147`
- prototype: `__int64 __fastcall(CTempGlassTerminal *__hidden this, struct ITSSession *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800074c0`
- `0x18002dbf0`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18002dc5d`
- `ntdll!RtlReleaseResource` at `0x18002dc5d`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002dc20`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002dc20`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002dc6b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002dc6b`

## string_xrefs

- `0x18002dc35`: `CTempGlassTerminal connect is call after terminal has start terminate`

## pseudocode

```c

```
