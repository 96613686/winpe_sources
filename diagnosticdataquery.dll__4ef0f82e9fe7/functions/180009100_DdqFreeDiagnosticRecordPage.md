# DdqFreeDiagnosticRecordPage

- ea: `0x180009100`
- end: `0x180009197`
- name: `DdqFreeDiagnosticRecordPage`
- size: `151`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800018d0`
- `0x180009100`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000912c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009137`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009142`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000914d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009158`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009163`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009175`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000912c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009137`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009142`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000914d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009158`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009163`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009175`

## pseudocode

```c
__int64 __fastcall DdqFreeDiagnosticRecordPage(void *a1)
{
  unsigned int v1; // r14d
  unsigned int i; // r15d
  __int64 v4; // rbx
  __int64 v5; // rdi

  v1 = *((_DWORD *)a1 + 4);
  for ( i = 0; i < v1; ++i )
  {
    v4 = *((_QWORD *)a1 + 1);
    v5 = 104LL * i;
    CoTaskMemFree(*(LPVOID *)(v5 + v4 + 24));
    CoTaskMemFree(*(LPVOID *)(v5 + v4 + 32));
    CoTaskMemFree(*(LPVOID *)(v5 + v4 + 40));
    CoTaskMemFree(*(LPVOID *)(v5 + v4 + 80));
    CoTaskMemFree(*(LPVOID *)(v5 + v4 + 88));
    CoTaskMemFree(*(LPVOID *)(v5 + v4 + 96));
  }
  CoTaskMemFree(*((LPVOID *)a1 + 1));
  operator delete(a1);
  return 0;
}

```

## disassembly

```asm
0x180009100  push    rbx
0x180009102  push    rbp
0x180009103  push    rsi
0x180009104  push    rdi
0x180009105  push    r14
0x180009107  push    r15
0x180009109  sub     rsp, 28h
0x18000910d  mov     r14d, [rcx+10h]
0x180009111  xor     r15d, r15d
0x180009114  mov     rbp, rcx
0x180009117  test    r14d, r14d
0x18000911a  jz      short loc_180009171
0x18000911c  mov     rbx, [rbp+8]
0x180009120  mov     eax, r15d
0x180009123  imul    rdi, rax, 68h ; 'h'
0x180009127  mov     rcx, [rdi+rbx+18h]; pv
0x18000912c  call    cs:__imp_CoTaskMemFree
0x180009132  mov     rcx, [rdi+rbx+20h]; pv
0x180009137  call    cs:__imp_CoTaskMemFree
0x18000913d  mov     rcx, [rdi+rbx+28h]; pv
0x180009142  call    cs:__imp_CoTaskMemFree
0x180009148  mov     rcx, [rdi+rbx+50h]; pv
0x18000914d  call    cs:__imp_CoTaskMemFree
0x180009153  mov     rcx, [rdi+rbx+58h]; pv
0x180009158  call    cs:__imp_CoTaskMemFree
0x18000915e  mov     rcx, [rdi+rbx+60h]; pv
0x180009163  call    cs:__imp_CoTaskMemFree
0x180009169  inc     r15d
0x18000916c  cmp     r15d, r14d
0x18000916f  jb      short loc_18000911C
0x180009171  mov     rcx, [rbp+8]; pv
0x180009175  call    cs:__imp_CoTaskMemFree
0x18000917b  mov     edx, 4; unsigned __int64
0x180009180  mov     rcx, rbp; void *
0x180009183  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009188  xor     eax, eax
0x18000918a  add     rsp, 28h
0x18000918e  pop     r15
0x180009190  pop     r14
0x180009192  pop     rdi
0x180009193  pop     rsi
0x180009194  pop     rbp
0x180009195  pop     rbx
0x180009196  retn
```
