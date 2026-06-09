# Mso::MemoryState::AppMemoryState::GetCommitMemoryStats(Mso::MemoryState::Commit_Stats *)

- ea: `0x18012ab50`
- end: `0x18012ac1d`
- name: `?GetCommitMemoryStats@AppMemoryState@MemoryState@Mso@@UEBA_NPEAUCommit_Stats@23@@Z`
- size: `205`
- prototype: `bool __fastcall(Mso::MemoryState::AppMemoryState *__hidden this, struct Mso::MemoryState::Commit_Stats *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18003e690`
- `0x18012ab50`
- `0x18012c0c8`
- `0x1801460c0`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x18012abaf`
- `KERNEL32!GetCurrentProcess` at `0x18012abaf`
- `KERNEL32!K32GetProcessMemoryInfo` at `0x18012abc3`
- `KERNEL32!K32GetProcessMemoryInfo` at `0x18012abc3`

## string_xrefs

- `0x18012abcd`: `GetProcessMemoryInfo failed for GetCommitMemoryStats`

## pseudocode

```c

```
