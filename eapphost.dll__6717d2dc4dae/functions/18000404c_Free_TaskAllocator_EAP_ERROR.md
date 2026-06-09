# Free<TaskAllocator>(_EAP_ERROR &)

- ea: `0x18000404c`
- end: `0x18000407c`
- name: `??$Free@VTaskAllocator@@@@YAXAEAU_EAP_ERROR@@@Z`
- size: `48`
- prototype: `void *__fastcall(LPVOID *)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800040d0`
- `0x180017704`
- `0x180017b78`
- `0x180018500`

## callees

- `0x18000343c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004059`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004063`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004059`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004063`

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
0x18000404c  push    rbx
0x18000404e  sub     rsp, 20h
0x180004052  mov     rbx, rcx
0x180004055  mov     rcx, [rcx+48h]; pv
0x180004059  call    cs:__imp_CoTaskMemFree
0x18000405f  mov     rcx, [rbx+50h]; pv
0x180004063  call    cs:__imp_CoTaskMemFree
0x180004069  xor     edx, edx; Val
0x18000406b  mov     rcx, rbx; void *
0x18000406e  lea     r8d, [rdx+58h]; Size
0x180004072  add     rsp, 20h
0x180004076  pop     rbx
0x180004077  jmp     memset_0
```
