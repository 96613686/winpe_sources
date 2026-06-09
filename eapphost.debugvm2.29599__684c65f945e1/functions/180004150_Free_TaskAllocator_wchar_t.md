# Free<TaskAllocator>(wchar_t *)

- ea: `0x180004150`
- end: `0x180004157`
- name: `??$Free@VTaskAllocator@@@@YAXPEA_W@Z`
- size: `7`
- prototype: `void __stdcall(LPVOID pv)`
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180018020`
- `0x180035751`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004150`

## pseudocode

```c
// attributes: thunk
void __stdcall Free<TaskAllocator>(LPVOID pv)
{
  CoTaskMemFree(pv);
}

```

## disassembly

```asm
0x180004150  jmp     cs:__imp_CoTaskMemFree
```
