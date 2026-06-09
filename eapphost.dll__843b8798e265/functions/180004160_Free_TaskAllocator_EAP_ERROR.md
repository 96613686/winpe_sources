# Free<TaskAllocator>(_EAP_ERROR &)

- ea: `0x180004160`
- end: `0x18000419c`
- name: `??$Free@VTaskAllocator@@@@YAXAEAU_EAP_ERROR@@@Z`
- size: `60`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004204`
- `0x180017ffc`
- `0x180018498`
- `0x180018e80`

## callees

- `0x1800034cc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000416d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000417d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000416d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000417d`

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
0x180004160  push    rbx
0x180004162  sub     rsp, 20h
0x180004166  mov     rbx, rcx
0x180004169  mov     rcx, [rcx+48h]; pv
0x18000416d  call    cs:__imp_CoTaskMemFree
0x180004174  nop     dword ptr [rax+rax+00h]
0x180004179  mov     rcx, [rbx+50h]; pv
0x18000417d  call    cs:__imp_CoTaskMemFree
0x180004184  nop     dword ptr [rax+rax+00h]
0x180004189  xor     edx, edx; Val
0x18000418b  mov     rcx, rbx; void *
0x18000418e  lea     r8d, [rdx+58h]; Size
0x180004192  add     rsp, 20h
0x180004196  pop     rbx
0x180004197  jmp     memset_0
```
