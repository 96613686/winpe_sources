# BinaryLogReader_Operation_OnDestroy

- ea: `0x1800298c0`
- end: `0x180029982`
- name: `BinaryLogReader_Operation_OnDestroy`
- size: `194`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000ab88`
- `0x1800263f4`
- `0x180029720`
- `0x1800298c0`
- `0x180044880`
- `0x180045010`

## import_xrefs

- `msvcrt!free` at `0x1800298f0`
- `msvcrt!free` at `0x1800298ff`
- `msvcrt!free` at `0x180029921`
- `msvcrt!free` at `0x18002992e`
- `msvcrt!free` at `0x1800298f0`
- `msvcrt!free` at `0x1800298ff`
- `msvcrt!free` at `0x180029921`
- `msvcrt!free` at `0x18002992e`

## pseudocode

```c
ULONG __fastcall BinaryLogReader_Operation_OnDestroy(__int64 a1)
{
  __int64 v1; // rbx
  __int64 v2; // rdx
  __int64 v3; // r8
  void *v4; // rcx
  void *v5; // rcx
  __int64 v6; // rax
  EVENT_DESCRIPTOR v8; // [rsp+20h] [rbp-28h] BYREF

  v1 = a1 + 152;
  BinaryLogReader_Core_Cleanup(a1 + 152);
  v4 = *(void **)(v1 + 128);
  if ( v4 )
    free(v4);
  v5 = *(void **)(v1 + 120);
  if ( v5 )
    free(v5);
  if ( *(_QWORD *)(v1 + 152) )
  {
    DeleteListBuckets();
    free(*(void **)(*(_QWORD *)(v1 + 152) + 8LL));
    free(*(void **)(v1 + 152));
  }
  v6 = *(_QWORD *)(v1 + 144);
  if ( v6 )
    (*(void (__fastcall **)(_QWORD))(v6 + 24))(*(_QWORD *)v6);
  *(_DWORD *)&v8.Id = 10204;
  *(_DWORD *)&v8.Level = 4;
  v8.Keyword = 1;
  return Etw_Trace0(&v8, v2, v3);
}

```

## disassembly

```asm
0x1800298c0  push    rbx
0x1800298c2  sub     rsp, 40h
0x1800298c6  mov     rax, cs:__security_cookie
0x1800298cd  xor     rax, rsp
0x1800298d0  mov     [rsp+48h+var_18], rax
0x1800298d5  lea     rbx, [rcx+98h]
0x1800298dc  mov     rcx, rbx
0x1800298df  call    BinaryLogReader_Core_Cleanup
0x1800298e4  mov     rcx, [rbx+80h]; Block
0x1800298eb  test    rcx, rcx
0x1800298ee  jz      short loc_1800298F6
0x1800298f0  call    cs:__imp_free
0x1800298f6  mov     rcx, [rbx+78h]; Block
0x1800298fa  test    rcx, rcx
0x1800298fd  jz      short loc_180029905
0x1800298ff  call    cs:__imp_free
0x180029905  mov     rcx, [rbx+98h]
0x18002990c  test    rcx, rcx
0x18002990f  jz      short loc_180029934
0x180029911  call    DeleteListBuckets
0x180029916  mov     rcx, [rbx+98h]
0x18002991d  mov     rcx, [rcx+8]; Block
0x180029921  call    cs:__imp_free
0x180029927  mov     rcx, [rbx+98h]; Block
0x18002992e  call    cs:__imp_free
0x180029934  mov     rax, [rbx+90h]
0x18002993b  test    rax, rax
0x18002993e  jz      short loc_18002994C
0x180029940  mov     rcx, [rax]
0x180029943  mov     rax, [rax+18h]
0x180029947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002994c  lea     rcx, [rsp+48h+var_28]
0x180029951  mov     [rsp+48h+var_28], 27DCh
0x180029959  mov     [rsp+48h+var_24], 4
0x180029961  mov     [rsp+48h+var_20], 1
0x18002996a  call    Etw_Trace0
0x18002996f  mov     rcx, [rsp+48h+var_18]
0x180029974  xor     rcx, rsp; StackCookie
0x180029977  call    __security_check_cookie
0x18002997c  add     rsp, 40h
0x180029980  pop     rbx
0x180029981  retn
```
