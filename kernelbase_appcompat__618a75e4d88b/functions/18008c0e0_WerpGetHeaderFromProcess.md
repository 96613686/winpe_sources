# WerpGetHeaderFromProcess

- ea: `0x18008c0e0`
- end: `0x18008c3af`
- name: `WerpGetHeaderFromProcess`
- size: `719`
- prototype: `__int64 __fastcall(HANDLE hProcess, PVOID Buffer)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18008bf7c`
- `0x18008c5cc`
- `0x1801300d0`

## callees

- `0x18004b9d0`
- `0x18008a810`
- `0x18008c0e0`
- `0x18008c3c0`
- `0x18008c418`
- `0x18012e570`

## import_xrefs

- `ntdll!DbgPrintEx` at `0x18008c234`
- `ntdll!DbgPrintEx` at `0x18008c28b`
- `ntdll!DbgPrintEx` at `0x18008c2cb`
- `ntdll!DbgPrintEx` at `0x18008c317`
- `ntdll!DbgPrintEx` at `0x18008c399`
- `ntdll!DbgPrintEx` at `0x18008c234`
- `ntdll!DbgPrintEx` at `0x18008c28b`
- `ntdll!DbgPrintEx` at `0x18008c2cb`
- `ntdll!DbgPrintEx` at `0x18008c317`
- `ntdll!DbgPrintEx` at `0x18008c399`
- `ntdll!NtReadVirtualMemory` at `0x18008c1c0`
- `ntdll!NtReadVirtualMemory` at `0x18008c1c0`
- `ntdll!RtlWow64GetProcessMachines` at `0x18008c148`
- `ntdll!RtlWow64GetProcessMachines` at `0x18008c148`

## string_xrefs

- `0x18008c2b1`: `WER/CrashAPI/%u:%u: ERROR ReadProcessMemory failed while trying to read WerRegistrationData\n`
- `0x18008c222`: `WER/CrashAPI/%u:%u: ERROR Failed to read the peb from the process\n`
- `0x18008c255`: `WER/CrashAPI/%u:%u: ERROR Failed to read the peb from the process\n`
- `0x18008c37f`: `WER/CrashAPI/%u:%u: ERROR WerpNtWow64ReadVirtualMemory64 failed while trying to read PebBaseAddress\n`

## pseudocode

```c

```
