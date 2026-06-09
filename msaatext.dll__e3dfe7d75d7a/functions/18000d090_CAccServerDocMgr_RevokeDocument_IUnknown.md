# CAccServerDocMgr::RevokeDocument(IUnknown *)

- ea: `0x18000d090`
- end: `0x18000d2d6`
- name: `?RevokeDocument@CAccServerDocMgr@@UEAAJPEAUIUnknown@@@Z`
- size: `582`
- prototype: `__int64 __fastcall(CAccServerDocMgr *__hidden this, struct IUnknown *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x1800026d0`
- `0x18000d090`
- `0x180014010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000d2b0`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000d2b0`

## string_xrefs

- `0x18000d1e9`: `dl-remove(), pEl is not on the list`
- `0x18000d281`: `~Link_dl(), link still on a list?`

## pseudocode

```c
__int64 __fastcall CAccServerDocMgr::RevokeDocument(CAccServerDocMgr *this, struct IUnknown *a2)
{
  _QWORD *v3; // rbx
  _QWORD *i; // rax
  int v5; // eax
  unsigned int v6; // esi
  __int64 v7; // rax
  _QWORD *v8; // rcx
  int v10; // [rsp+20h] [rbp-28h]
  __int64 v11; // [rsp+58h] [rbp+10h] BYREF
  __int64 v12; // [rsp+60h] [rbp+18h] BYREF

  if ( !a2 )
    return 2147942487LL;
  v12 = 0;
  if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
         a2,
         &IID_IUnknown,
         &v12)
    || !v12 )
  {
    return 2147500037LL;
  }
  v3 = 0;
  for ( i = (_QWORD *)*((_QWORD *)this + 2); i; i = (_QWORD *)i[1] )
  {
    if ( i[2] == v12 )
    {
      v3 = i;
      break;
    }
  }
  (*(void (**)(void))(*(_QWORD *)v12 + 16LL))();
  if ( !v3 )
    return 2147942487LL;
  v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 4) + 32LL))(*((_QWORD *)this + 4), v3[3]);
  if ( v5 )
    InternalTrace(L"windows\\oleacc\\msaatext\\msaaadapter.cpp", 0xDCu, v10, v5, (__int64)L"m_pAccStore->Unregister()");
  v11 = 0;
  v6 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))v3[3])(v3[3], &IID_IInternalDocWrap, &v11);
  if ( v6 || !v11 )
  {
    InternalTrace(
      L"windows\\oleacc\\msaatext\\msaaadapter.cpp",
      0xECu,
      v10,
      v6,
      (__int64)L"pdocAnchor didn't support IInternalDocWrap - was it wrapped properly?");
  }
  else
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 24LL))(v11);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  if ( !v3[1] && !*v3 && *((_QWORD **)this + 2) != v3 )
    InternalTrace(L"windows\\oleacc\\inc\\list_dl.h", 0x91u, v10, 0, (__int64)L"dl-remove(), pEl is not on the list");
  v7 = v3[1];
  if ( *v3 )
    *(_QWORD *)(*v3 + 8LL) = v7;
  else
    *((_QWORD *)this + 2) = v7;
  v8 = (_QWORD *)v3[1];
  if ( v8 )
    *v8 = *v3;
  else
    *((_QWORD *)this + 3) = 0;
  *v3 = 0;
  v3[1] = 0;
  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v3[2] + 16LL))(v3[2]);
  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v3[3] + 16LL))(v3[3]);
  if ( v3[1] || *v3 )
    InternalTrace(L"windows\\oleacc\\inc\\list_dl.h", 0x1Fu, v10, 0, (__int64)L"~Link_dl(), link still on a list?");
  operator delete(v3);
  return v6;
}

```

## disassembly

```asm
0x18000d090  mov     r11, rsp
0x18000d093  mov     [r11+8], rbx
0x18000d097  mov     [r11+20h], rsi
0x18000d09b  push    rdi
0x18000d09c  sub     rsp, 40h
0x18000d0a0  mov     r9, rdx
0x18000d0a3  mov     rdi, rcx
0x18000d0a6  test    rdx, rdx
0x18000d0a9  jz      loc_18000D2C1
0x18000d0af  mov     qword ptr [r11+18h], 0
0x18000d0b7  mov     rax, [rdx]
0x18000d0ba  lea     r8, [r11+18h]
0x18000d0be  lea     rdx, IID_IUnknown
0x18000d0c5  mov     rcx, r9
0x18000d0c8  mov     rax, [rax]
0x18000d0cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0d0  test    eax, eax
0x18000d0d2  jnz     loc_18000D2BA
0x18000d0d8  mov     rcx, [rsp+48h+arg_10]
0x18000d0dd  test    rcx, rcx
0x18000d0e0  jz      loc_18000D2BA
0x18000d0e6  xor     ebx, ebx
0x18000d0e8  mov     rax, [rdi+10h]
0x18000d0ec  test    rax, rax
0x18000d0ef  jz      short loc_18000D100
0x18000d0f1  cmp     [rax+10h], rcx
0x18000d0f5  jz      short loc_18000D0FD
0x18000d0f7  mov     rax, [rax+8]
0x18000d0fb  jmp     short loc_18000D0EC
0x18000d0fd  mov     rbx, rax
0x18000d100  mov     rax, [rcx]
0x18000d103  mov     rax, [rax+10h]
0x18000d107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d10c  test    rbx, rbx
0x18000d10f  jz      loc_18000D2C1
0x18000d115  mov     rcx, [rdi+20h]
0x18000d119  mov     rax, [rcx]
0x18000d11c  mov     rdx, [rbx+18h]
0x18000d120  mov     rax, [rax+20h]
0x18000d124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d129  test    eax, eax
0x18000d12b  jz      short loc_18000D158
0x18000d12d  lea     rcx, aMPaccstoreUnre; "m_pAccStore->Unregister()"
0x18000d134  mov     [rsp+48h+var_18], rcx; __int64
0x18000d139  mov     [rsp+48h+var_20], eax; int
0x18000d13d  mov     edx, 0DCh; Value
0x18000d142  mov     r9d, 1
0x18000d148  lea     r8d, [r9+2]
0x18000d14c  lea     rcx, aWindowsOleaccM_2; "windows\\oleacc\\msaatext\\msaaadapter."...
0x18000d153  call    InternalTrace
0x18000d158  mov     [rsp+48h+arg_8], 0
0x18000d161  mov     rcx, [rbx+18h]
0x18000d165  mov     rax, [rcx]
0x18000d168  lea     r8, [rsp+48h+arg_8]
0x18000d16d  lea     rdx, IID_IInternalDocWrap
0x18000d174  mov     rax, [rax]
0x18000d177  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d17c  mov     esi, eax
0x18000d17e  test    eax, eax
0x18000d180  jnz     short loc_18000D1AB
0x18000d182  mov     rcx, [rsp+48h+arg_8]
0x18000d187  test    rcx, rcx
0x18000d18a  jz      short loc_18000D1AB
0x18000d18c  mov     rdx, [rcx]
0x18000d18f  mov     rax, [rdx+18h]
0x18000d193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d198  mov     rcx, [rsp+48h+arg_8]
0x18000d19d  mov     rax, [rcx]
0x18000d1a0  mov     rax, [rax+10h]
0x18000d1a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1a9  jmp     short loc_18000D1D6
0x18000d1ab  lea     rax, aPdocanchorDidn; "pdocAnchor didn't support IInternalDocW"...
0x18000d1b2  mov     [rsp+48h+var_18], rax; __int64
0x18000d1b7  mov     [rsp+48h+var_20], esi; int
0x18000d1bb  mov     edx, 0ECh; Value
0x18000d1c0  mov     r9d, 1
0x18000d1c6  lea     r8d, [r9+2]
0x18000d1ca  lea     rcx, aWindowsOleaccM_2; "windows\\oleacc\\msaatext\\msaaadapter."...
0x18000d1d1  call    InternalTrace
0x18000d1d6  cmp     qword ptr [rbx+8], 0
0x18000d1db  jnz     short loc_18000D215
0x18000d1dd  cmp     qword ptr [rbx], 0
0x18000d1e1  jnz     short loc_18000D215
0x18000d1e3  cmp     [rdi+10h], rbx
0x18000d1e7  jz      short loc_18000D215
0x18000d1e9  lea     rax, aDlRemovePelIsN; "dl-remove(), pEl is not on the list"
0x18000d1f0  mov     [rsp+48h+var_18], rax; __int64
0x18000d1f5  mov     [rsp+48h+var_20], 0; int
0x18000d1fd  xor     r9d, r9d
0x18000d200  mov     edx, 91h; Value
0x18000d205  lea     r8d, [r9+8]
0x18000d209  lea     rcx, aWindowsOleaccI; "windows\\oleacc\\inc\\list_dl.h"
0x18000d210  call    InternalTrace
0x18000d215  mov     rcx, [rbx]
0x18000d218  mov     rax, [rbx+8]
0x18000d21c  test    rcx, rcx
0x18000d21f  jz      short loc_18000D227
0x18000d221  mov     [rcx+8], rax
0x18000d225  jmp     short loc_18000D22B
0x18000d227  mov     [rdi+10h], rax
0x18000d22b  mov     rcx, [rbx+8]
0x18000d22f  test    rcx, rcx
0x18000d232  jz      short loc_18000D23C
0x18000d234  mov     rax, [rbx]
0x18000d237  mov     [rcx], rax
0x18000d23a  jmp     short loc_18000D244
0x18000d23c  mov     qword ptr [rdi+18h], 0
0x18000d244  mov     qword ptr [rbx], 0
0x18000d24b  mov     qword ptr [rbx+8], 0
0x18000d253  mov     rcx, [rbx+10h]
0x18000d257  mov     rax, [rcx]
0x18000d25a  mov     rax, [rax+10h]
0x18000d25e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d263  mov     rcx, [rbx+18h]
0x18000d267  mov     rax, [rcx]
0x18000d26a  mov     rax, [rax+10h]
0x18000d26e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d273  nop
0x18000d274  cmp     qword ptr [rbx+8], 0
0x18000d279  jnz     short loc_18000D281
0x18000d27b  cmp     qword ptr [rbx], 0
0x18000d27f  jz      short loc_18000D2AD
0x18000d281  lea     rax, aLinkDlLinkStil; "~Link_dl(), link still on a list?"
0x18000d288  mov     [rsp+48h+var_18], rax; __int64
0x18000d28d  mov     [rsp+48h+var_20], 0; int
0x18000d295  xor     r9d, r9d
0x18000d298  lea     edx, [r9+1Fh]; Value
0x18000d29c  lea     r8d, [r9+8]
0x18000d2a0  lea     rcx, aWindowsOleaccI; "windows\\oleacc\\inc\\list_dl.h"
0x18000d2a7  call    InternalTrace
0x18000d2ac  nop
0x18000d2ad  mov     rcx, rbx
0x18000d2b0  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000d2b6  mov     eax, esi
0x18000d2b8  jmp     short loc_18000D2C6
0x18000d2ba  mov     eax, 80004005h
0x18000d2bf  jmp     short loc_18000D2C6
0x18000d2c1  mov     eax, 80070057h
0x18000d2c6  mov     rbx, [rsp+48h+arg_0]
0x18000d2cb  mov     rsi, [rsp+48h+arg_18]
0x18000d2d0  add     rsp, 40h
0x18000d2d4  pop     rdi
0x18000d2d5  retn
```
