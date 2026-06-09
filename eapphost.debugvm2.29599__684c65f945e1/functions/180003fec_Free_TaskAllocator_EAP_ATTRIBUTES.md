# Free<TaskAllocator>(_EAP_ATTRIBUTES &)

- ea: `0x180003fec`
- end: `0x180004043`
- name: `??$Free@VTaskAllocator@@@@YAXAEAU_EAP_ATTRIBUTES@@@Z`
- size: `87`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800040d0`
- `0x180004df4`
- `0x1800067f0`
- `0x180017704`
- `0x1800182d0`
- `0x180018500`

## callees

- `0x180003fec`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004013`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004027`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004013`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004027`

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
0x180003fec  mov     [rsp+arg_0], rbx
0x180003ff1  mov     [rsp+arg_8], rsi
0x180003ff6  push    rdi
0x180003ff7  sub     rsp, 20h
0x180003ffb  xor     esi, esi
0x180003ffd  mov     rdi, rcx
0x180004000  cmp     [rcx], esi
0x180004002  jbe     short loc_180004023
0x180004004  mov     rcx, [rdi+8]
0x180004008  mov     rax, rsi
0x18000400b  add     rax, rax
0x18000400e  mov     rcx, [rcx+rax*8+8]; pv
0x180004013  call    cs:__imp_CoTaskMemFree
0x180004019  mov     eax, [rdi]
0x18000401b  inc     rsi
0x18000401e  cmp     rsi, rax
0x180004021  jb      short loc_180004004
0x180004023  mov     rcx, [rdi+8]; pv
0x180004027  call    cs:__imp_CoTaskMemFree
0x18000402d  mov     rbx, [rsp+28h+arg_0]
0x180004032  xorps   xmm0, xmm0
0x180004035  mov     rsi, [rsp+28h+arg_8]
0x18000403a  movups  xmmword ptr [rdi], xmm0
0x18000403d  add     rsp, 20h
0x180004041  pop     rdi
0x180004042  retn
```
