# Free<TaskAllocator>(wchar_t *)

- ea: `0x1800042a0`
- end: `0x1800042a7`
- name: `??$Free@VTaskAllocator@@@@YAXPEA_W@Z`
- size: `7`
- prototype: `void __stdcall(LPVOID pv)`
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180018990`
- `0x180036b0c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800042a0`

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
0x1800042a0  jmp     cs:__imp_CoTaskMemFree
```
