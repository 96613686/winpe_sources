# CCscWorkOfflineTaskDialog::~CCscWorkOfflineTaskDialog(void)

- ea: `0x180043c24`
- end: `0x180043ca5`
- name: `??1CCscWorkOfflineTaskDialog@@QEAA@XZ`
- size: `129`
- prototype: `void __fastcall(CCscWorkOfflineTaskDialog *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180043d3c`

## callees

- `0x180043c24`
- `0x180044588`
- `0x1800446ec`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180043c4b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180043c4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043c58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043c6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043c58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043c6b`

## pseudocode

```c
void __fastcall CCscWorkOfflineTaskDialog::~CCscWorkOfflineTaskDialog(CCscWorkOfflineTaskDialog *this)
{
  __int64 v1; // rbp
  LPVOID *i; // rsi
  __int64 v4; // rcx

  v1 = 0;
  for ( i = (LPVOID *)((char *)this + 432); (unsigned int)v1 < *((_DWORD *)this + 110); v1 = (unsigned int)(v1 + 1) )
  {
    LocalFree(**((HLOCAL **)*i + v1));
    CoTaskMemFree(*((LPVOID *)*i + v1));
  }
  CoTaskMemFree(*i);
  v4 = *((_QWORD *)this + 53);
  if ( v4 )
  {
    CComTaskThread<CCscUiComTaskContext>::TerminateThread(v4);
    CComTaskThread<CCscUiComTaskContext>::Release(*((void **)this + 53));
  }
  *((_QWORD *)this + 49) = &CComTaskContext::`vftable';
}

```

## disassembly

```asm
0x180043c24  push    rbx
0x180043c26  push    rbp
0x180043c27  push    rsi
0x180043c28  push    rdi
0x180043c29  sub     rsp, 28h
0x180043c2d  xor     ebp, ebp
0x180043c2f  lea     rsi, [rcx+1B0h]
0x180043c36  mov     rdi, rcx
0x180043c39  cmp     [rcx+1B8h], ebp
0x180043c3f  jbe     short loc_180043C68
0x180043c41  mov     rax, [rsi]
0x180043c44  mov     rcx, [rax+rbp*8]
0x180043c48  mov     rcx, [rcx]; hMem
0x180043c4b  call    cs:__imp_LocalFree
0x180043c51  mov     rcx, [rsi]
0x180043c54  mov     rcx, [rcx+rbp*8]; pv
0x180043c58  call    cs:__imp_CoTaskMemFree
0x180043c5e  inc     ebp
0x180043c60  cmp     ebp, [rdi+1B8h]
0x180043c66  jb      short loc_180043C41
0x180043c68  mov     rcx, [rsi]; pv
0x180043c6b  call    cs:__imp_CoTaskMemFree
0x180043c71  mov     rcx, [rdi+1A8h]
0x180043c78  test    rcx, rcx
0x180043c7b  jz      short loc_180043C8E
0x180043c7d  call    ?TerminateThread@?$CComTaskThread@VCCscUiComTaskContext@@@@QEAAJXZ; CComTaskThread<CCscUiComTaskContext>::TerminateThread(void)
0x180043c82  mov     rcx, [rdi+1A8h]; Block
0x180043c89  call    ?Release@?$CComTaskThread@VCCscUiComTaskContext@@@@QEAAKXZ; CComTaskThread<CCscUiComTaskContext>::Release(void)
0x180043c8e  lea     rax, ??_7CComTaskContext@@6B@; const CComTaskContext::`vftable'
0x180043c95  mov     [rdi+188h], rax
0x180043c9c  add     rsp, 28h
0x180043ca0  pop     rdi
0x180043ca1  pop     rsi
0x180043ca2  pop     rbp
0x180043ca3  pop     rbx
0x180043ca4  retn
```
