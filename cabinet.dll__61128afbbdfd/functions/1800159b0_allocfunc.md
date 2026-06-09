# allocfunc

- ea: `0x1800159b0`
- end: `0x1800159b9`
- name: `allocfunc`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800159b2`

## pseudocode

```c
LPVOID __fastcall allocfunc(unsigned int a1)
{
  return CoTaskMemAlloc(a1);
}

```

## disassembly

```asm
0x1800159b0  mov     ecx, ecx
0x1800159b2  jmp     cs:__imp_CoTaskMemAlloc
```
