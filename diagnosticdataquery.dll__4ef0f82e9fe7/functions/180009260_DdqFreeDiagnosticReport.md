# DdqFreeDiagnosticReport

- ea: `0x180009260`
- end: `0x18000935f`
- name: `DdqFreeDiagnosticReport`
- size: `255`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800018d0`
- `0x180009260`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009296`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800092a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800092b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800092c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800092ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800092dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800092ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000930c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009326`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000933b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009296`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800092a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800092b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800092c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800092ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800092dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800092ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000930c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009326`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000933b`

## pseudocode

```c
__int64 __fastcall DdqFreeDiagnosticReport(void *a1)
{
  unsigned int v1; // r12d
  unsigned int i; // edi
  __int64 v4; // r14
  __int64 v5; // rbp
  __int64 v6; // r15
  __int64 j; // rsi

  v1 = *((_DWORD *)a1 + 4);
  for ( i = 0; i < v1; ++i )
  {
    v4 = *((_QWORD *)a1 + 1);
    v5 = 8064LL * i;
    CoTaskMemFree(*(LPVOID *)(v4 + v5 + 7960));
    CoTaskMemFree(*(LPVOID *)(v4 + v5 + 8008));
    CoTaskMemFree(*(LPVOID *)(v4 + v5 + 8016));
    CoTaskMemFree(*(LPVOID *)(v4 + v5 + 8024));
    CoTaskMemFree(*(LPVOID *)(v4 + v5 + 8032));
    CoTaskMemFree(*(LPVOID *)(v4 + v5 + 8040));
    CoTaskMemFree(*(LPVOID *)(v4 + v5 + 8056));
    v6 = 0;
    for ( j = v4 + v5; (unsigned int)v6 < *(_DWORD *)(v4 + v5 + 8000); v6 = (unsigned int)(v6 + 1) )
      CoTaskMemFree(*(LPVOID *)(*(_QWORD *)(j + 7992) + 8 * v6));
    CoTaskMemFree(*(LPVOID *)(j + 7992));
  }
  CoTaskMemFree(*((LPVOID *)a1 + 1));
  operator delete(a1);
  return 0;
}

```

## disassembly

```asm
0x180009260  push    rbx
0x180009262  push    rbp
0x180009263  push    rsi
0x180009264  push    rdi
0x180009265  push    r12
0x180009267  push    r14
0x180009269  push    r15
0x18000926b  sub     rsp, 20h
0x18000926f  mov     r12d, [rcx+10h]
0x180009273  xor     edi, edi
0x180009275  mov     rbx, rcx
0x180009278  test    r12d, r12d
0x18000927b  jz      loc_180009337
0x180009281  mov     r14, [rbx+8]
0x180009285  mov     eax, edi
0x180009287  imul    rbp, rax, 1F80h
0x18000928e  mov     rcx, [r14+rbp+1F18h]; pv
0x180009296  call    cs:__imp_CoTaskMemFree
0x18000929c  mov     rcx, [r14+rbp+1F48h]; pv
0x1800092a4  call    cs:__imp_CoTaskMemFree
0x1800092aa  mov     rcx, [r14+rbp+1F50h]; pv
0x1800092b2  call    cs:__imp_CoTaskMemFree
0x1800092b8  mov     rcx, [r14+rbp+1F58h]; pv
0x1800092c0  call    cs:__imp_CoTaskMemFree
0x1800092c6  mov     rcx, [r14+rbp+1F60h]; pv
0x1800092ce  call    cs:__imp_CoTaskMemFree
0x1800092d4  mov     rcx, [r14+rbp+1F68h]; pv
0x1800092dc  call    cs:__imp_CoTaskMemFree
0x1800092e2  mov     rcx, [r14+rbp+1F78h]; pv
0x1800092ea  call    cs:__imp_CoTaskMemFree
0x1800092f0  xor     r15d, r15d
0x1800092f3  lea     rsi, [r14+rbp]
0x1800092f7  cmp     [r14+rbp+1F40h], r15d
0x1800092ff  jbe     short loc_18000931F
0x180009301  mov     rcx, [rsi+1F38h]
0x180009308  mov     rcx, [rcx+r15*8]; pv
0x18000930c  call    cs:__imp_CoTaskMemFree
0x180009312  inc     r15d
0x180009315  cmp     r15d, [r14+rbp+1F40h]
0x18000931d  jb      short loc_180009301
0x18000931f  mov     rcx, [rsi+1F38h]; pv
0x180009326  call    cs:__imp_CoTaskMemFree
0x18000932c  inc     edi
0x18000932e  cmp     edi, r12d
0x180009331  jb      loc_180009281
0x180009337  mov     rcx, [rbx+8]; pv
0x18000933b  call    cs:__imp_CoTaskMemFree
0x180009341  mov     edx, 4; unsigned __int64
0x180009346  mov     rcx, rbx; void *
0x180009349  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000934e  xor     eax, eax
0x180009350  add     rsp, 20h
0x180009354  pop     r15
0x180009356  pop     r14
0x180009358  pop     r12
0x18000935a  pop     rdi
0x18000935b  pop     rsi
0x18000935c  pop     rbp
0x18000935d  pop     rbx
0x18000935e  retn
```
