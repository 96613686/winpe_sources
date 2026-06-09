# Free<TaskAllocator>(_EAP_ATTRIBUTES &)

- ea: `0x1800040f4`
- end: `0x180004158`
- name: `??$Free@VTaskAllocator@@@@YAXAEAU_EAP_ATTRIBUTES@@@Z`
- size: `100`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004204`
- `0x180004f30`
- `0x180006a80`
- `0x180017ffc`
- `0x180018c40`
- `0x180018e80`

## callees

- `0x1800040f4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000411b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004135`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000411b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004135`

## pseudocode

```c
void __fastcall Free<TaskAllocator>(unsigned int *a1)
{
  unsigned __int64 i; // rsi

  for ( i = 0; i < *a1; CoTaskMemFree(*(LPVOID *)(*((_QWORD *)a1 + 1) + 16 * i++ + 8)) )
    ;
  CoTaskMemFree(*((LPVOID *)a1 + 1));
  *(_OWORD *)a1 = 0;
}

```

## disassembly

```asm
0x1800040f4  mov     [rsp+arg_0], rbx
0x1800040f9  mov     [rsp+arg_8], rsi
0x1800040fe  push    rdi
0x1800040ff  sub     rsp, 20h
0x180004103  xor     esi, esi
0x180004105  mov     rdi, rcx
0x180004108  cmp     [rcx], esi
0x18000410a  jbe     short loc_180004131
0x18000410c  mov     rcx, [rdi+8]
0x180004110  mov     rax, rsi
0x180004113  add     rax, rax
0x180004116  mov     rcx, [rcx+rax*8+8]; pv
0x18000411b  call    cs:__imp_CoTaskMemFree
0x180004122  nop     dword ptr [rax+rax+00h]
0x180004127  mov     eax, [rdi]
0x180004129  inc     rsi
0x18000412c  cmp     rsi, rax
0x18000412f  jb      short loc_18000410C
0x180004131  mov     rcx, [rdi+8]; pv
0x180004135  call    cs:__imp_CoTaskMemFree
0x18000413c  nop     dword ptr [rax+rax+00h]
0x180004141  mov     rbx, [rsp+28h+arg_0]
0x180004146  xorps   xmm0, xmm0
0x180004149  mov     rsi, [rsp+28h+arg_8]
0x18000414e  movups  xmmword ptr [rdi], xmm0
0x180004151  add     rsp, 20h
0x180004155  pop     rdi
0x180004156  retn
```
