# Free<TaskAllocator>(_EAP_ERROR &)

- ea: `0x18001330c`
- end: `0x18001333c`
- name: `??$Free@VTaskAllocator@@@@YAXAEAU_EAP_ERROR@@@Z`
- size: `48`
- prototype: `void *__fastcall(LPVOID *)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180013dbc`
- `0x180027ec0`
- `0x180028c90`

## callees

- `0x18000213c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013319`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013323`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013319`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013323`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void *__fastcall Free<TaskAllocator>(LPVOID *a1)
{
  CoTaskMemFree(a1[9]);
  CoTaskMemFree(a1[10]);
  return memset_0(a1, 0, 0x58u);
}

```

## disassembly

```asm
0x18001330c  push    rbx
0x18001330e  sub     rsp, 20h
0x180013312  mov     rbx, rcx
0x180013315  mov     rcx, [rcx+48h]; pv
0x180013319  call    cs:__imp_CoTaskMemFree
0x18001331f  mov     rcx, [rbx+50h]; pv
0x180013323  call    cs:__imp_CoTaskMemFree
0x180013329  xor     edx, edx; Val
0x18001332b  mov     rcx, rbx; void *
0x18001332e  lea     r8d, [rdx+58h]; Size
0x180013332  add     rsp, 20h
0x180013336  pop     rbx
0x180013337  jmp     memset_0
```
