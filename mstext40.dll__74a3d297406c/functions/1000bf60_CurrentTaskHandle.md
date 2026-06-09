# CurrentTaskHandle()

- ea: `0x1000bf60`
- end: `0x1000bf66`
- name: `_CurrentTaskHandle@0`
- size: `6`
- prototype: `DWORD __stdcall()`
- caller_count: `18`
- callee_count: `0`
- tags: `authz_impersonation, service_task`

## callers

- `0x1000f0e0`
- `0x100108e0`
- `0x10011060`
- `0x10011310`
- `0x10011870`
- `0x10011d90`
- `0x10012e70`
- `0x10013b00`
- `0x100147d0`
- `0x100148d0`
- `0x10014ea0`
- `0x100170e0`
- `0x100178b0`
- `0x10017ea0`
- `0x10018160`
- `0x10018200`
- `0x1001ca20`
- `0x1001cb00`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x1000bf60`

## pseudocode

```c
// attributes: thunk
DWORD __stdcall CurrentTaskHandle()
{
  return GetCurrentProcessId();
}

```

## disassembly

```asm
0x1000bf60  jmp     ds:__imp__GetCurrentProcessId@0; GetCurrentProcessId()
```
