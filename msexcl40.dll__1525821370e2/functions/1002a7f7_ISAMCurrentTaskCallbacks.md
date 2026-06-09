# ISAMCurrentTaskCallbacks()

- ea: `0x1002a7f7`
- end: `0x1002a808`
- name: `_ISAMCurrentTaskCallbacks@0`
- size: `17`
- prototype: `_DWORD __stdcall()`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, service_task`

## callers

- `0x100246ef`
- `0x1002476e`

## callees

- `0x1002a7de`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1002a7f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1002a7f7`

## pseudocode

```c
int __stdcall ISAMCurrentTaskCallbacks()
{
  DWORD CurrentProcessId; // eax

  CurrentProcessId = GetCurrentProcessId();
  return *(_DWORD *)(ISAMDBFindTask(CurrentProcessId) + 28);
}

```

## disassembly

```asm
0x1002a7f7  call    ds:__imp__GetCurrentProcessId@0; GetCurrentProcessId()
0x1002a7fd  mov     ecx, eax
0x1002a7ff  call    _ISAMDBFindTask@4; ISAMDBFindTask(x)
0x1002a804  mov     eax, [eax+1Ch]
0x1002a807  retn
```
