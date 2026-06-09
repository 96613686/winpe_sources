# Free<TaskAllocator>(_EAP_ERROR &)

- ea: `0x1800022a8`
- end: `0x1800022e4`
- name: `??$Free@VTaskAllocator@@@@YAXAEAU_EAP_ERROR@@@Z`
- size: `60`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007090`
- `0x18000cae8`
- `0x18000cf94`

## callees

- `0x180002106`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800022b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800022c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800022b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800022c5`

## pseudocode

```c
void *__fastcall Free<TaskAllocator>(LPVOID *a1)
{
  CoTaskMemFree(a1[9]);
  CoTaskMemFree(a1[10]);
  return memset_0(a1, 0, 0x58u);
}

```

## disassembly

```asm
0x1800022a8  push    rbx
0x1800022aa  sub     rsp, 20h
0x1800022ae  mov     rbx, rcx
0x1800022b1  mov     rcx, [rcx+48h]; pv
0x1800022b5  call    cs:__imp_CoTaskMemFree
0x1800022bc  nop     dword ptr [rax+rax+00h]
0x1800022c1  mov     rcx, [rbx+50h]; pv
0x1800022c5  call    cs:__imp_CoTaskMemFree
0x1800022cc  nop     dword ptr [rax+rax+00h]
0x1800022d1  xor     edx, edx; Val
0x1800022d3  mov     rcx, rbx; void *
0x1800022d6  lea     r8d, [rdx+58h]; Size
0x1800022da  add     rsp, 20h
0x1800022de  pop     rbx
0x1800022df  jmp     memset_0
```
