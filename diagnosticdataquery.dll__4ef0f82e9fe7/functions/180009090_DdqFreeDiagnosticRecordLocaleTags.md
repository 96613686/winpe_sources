# DdqFreeDiagnosticRecordLocaleTags

- ea: `0x180009090`
- end: `0x1800090f8`
- name: `DdqFreeDiagnosticRecordLocaleTags`
- size: `104`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800018d0`
- `0x180009090`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800090b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800090c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800090d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800090b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800090c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800090d6`

## pseudocode

```c
__int64 __fastcall DdqFreeDiagnosticRecordLocaleTags(void *a1)
{
  unsigned int v1; // r15d
  __int64 i; // r14
  __int64 v4; // rbx

  v1 = *((_DWORD *)a1 + 4);
  for ( i = 0; (unsigned int)i < v1; i = (unsigned int)(i + 1) )
  {
    v4 = *((_QWORD *)a1 + 1);
    CoTaskMemFree(*(LPVOID *)(v4 + 24 * i + 8));
    CoTaskMemFree(*(LPVOID *)(v4 + 24 * i + 16));
  }
  CoTaskMemFree(*((LPVOID *)a1 + 1));
  operator delete(a1);
  return 0;
}

```

## disassembly

```asm
0x180009090  push    rbx
0x180009092  push    rbp
0x180009093  push    rsi
0x180009094  push    rdi
0x180009095  push    r14
0x180009097  push    r15
0x180009099  sub     rsp, 28h
0x18000909d  mov     r15d, [rcx+10h]
0x1800090a1  xor     r14d, r14d
0x1800090a4  mov     rbp, rcx
0x1800090a7  test    r15d, r15d
0x1800090aa  jz      short loc_1800090D2
0x1800090ac  mov     rbx, [rbp+8]
0x1800090b0  lea     rdi, [r14+r14*2]
0x1800090b4  mov     rcx, [rbx+rdi*8+8]; pv
0x1800090b9  call    cs:__imp_CoTaskMemFree
0x1800090bf  mov     rcx, [rbx+rdi*8+10h]; pv
0x1800090c4  call    cs:__imp_CoTaskMemFree
0x1800090ca  inc     r14d
0x1800090cd  cmp     r14d, r15d
0x1800090d0  jb      short loc_1800090AC
0x1800090d2  mov     rcx, [rbp+8]; pv
0x1800090d6  call    cs:__imp_CoTaskMemFree
0x1800090dc  mov     edx, 4; unsigned __int64
0x1800090e1  mov     rcx, rbp; void *
0x1800090e4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800090e9  xor     eax, eax
0x1800090eb  add     rsp, 28h
0x1800090ef  pop     r15
0x1800090f1  pop     r14
0x1800090f3  pop     rdi
0x1800090f4  pop     rsi
0x1800090f5  pop     rbp
0x1800090f6  pop     rbx
0x1800090f7  retn
```
