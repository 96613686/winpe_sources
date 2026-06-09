# RouterGetKeyDataBlob

- ea: `0x18005c528`
- end: `0x18005c6c0`
- name: `RouterGetKeyDataBlob`
- size: `408`
- prototype: `__int64 __fastcall(__int64, void *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18005c15c`

## callees

- `0x18000743c`
- `0x18001bd90`
- `0x18001be80`
- `0x18005c528`
- `0x18009d820`
- `0x18009d860`
- `0x18009da40`

## string_xrefs

- `0x18005c5b4`: `onecore\ds\security\cryptoapi\ncrypt\crypt\routeraeskeywrap.c`
- `0x18005c640`: `onecore\ds\security\cryptoapi\ncrypt\crypt\routeraeskeywrap.c`

## pseudocode

```c
__int64 __fastcall RouterGetKeyDataBlob(__int64 a1, void *a2, unsigned int a3)
{
  __int64 v3; // rax
  __int64 v5; // r15
  __int64 (__fastcall *v6)(__int64, _QWORD, const WCHAR *, char *, unsigned int, unsigned int *, _DWORD); // r12
  size_t v7; // rbp
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // r9
  __int64 v11; // rcx
  unsigned int v12; // eax
  _BYTE *v13; // rdi
  char *v14; // rsi
  __int64 v15; // rax
  int v16; // eax
  __int64 v17; // r9
  __int64 v18; // rcx
  __int64 v19; // rax
  _BYTE *v20; // rcx
  unsigned int v22; // [rsp+40h] [rbp-A8h] BYREF
  _DWORD v23[3]; // [rsp+44h] [rbp-A4h] BYREF
  char v24; // [rsp+50h] [rbp-98h] BYREF

  v3 = *(_QWORD *)(a1 + 8);
  v5 = *(_QWORD *)(a1 + 16);
  v22 = 0;
  v23[0] = 0;
  v6 = *(__int64 (__fastcall **)(__int64, _QWORD, const WCHAR *, char *, unsigned int, unsigned int *, _DWORD))(v3 + 120);
  v7 = a3;
  v8 = v6(v5, 0, L"KeyDataBlob", 0, 0, &v22, 0);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 70;
    v11 = (unsigned int)v8;
LABEL_3:
    DebugTraceError(v11, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\routeraeskeywrap.c", v10);
    return v9;
  }
  v12 = v22;
  if ( v22 > 0x4C )
  {
    v15 = BCryptAlloc(v22);
    v13 = (_BYTE *)v15;
    if ( !v15 )
    {
      v9 = -1073741801;
      v10 = 87;
      v11 = 3221225495LL;
      goto LABEL_3;
    }
    v14 = (char *)v15;
    v12 = v22;
  }
  else
  {
    v13 = 0;
    v14 = &v24;
  }
  v16 = v6(v5, 0, L"KeyDataBlob", v14, v12, v23, 0);
  v9 = v16;
  if ( v16 < 0 )
  {
    v17 = 107;
    v18 = (unsigned int)v16;
LABEL_11:
    DebugTraceError(v18, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\routeraeskeywrap.c", v17);
    goto LABEL_15;
  }
  if ( (_DWORD)v7 != *((_DWORD *)v14 + 2) )
  {
    v9 = -1073741811;
    v17 = 116;
    v18 = 3221225485LL;
    goto LABEL_11;
  }
  memmove(a2, v14 + 12, v7);
  v9 = 0;
LABEL_15:
  if ( v13 )
  {
    v19 = v22;
    v20 = v13;
    if ( v22 )
    {
      do
      {
        *v20++ = 0;
        --v19;
      }
      while ( v19 );
    }
    BCryptFree(v13);
  }
  return v9;
}

```

## disassembly

```asm
0x18005c528  push    rbx
0x18005c52a  push    rbp
0x18005c52b  push    rsi
0x18005c52c  push    rdi
0x18005c52d  push    r12
0x18005c52f  push    r14
0x18005c531  push    r15
0x18005c533  sub     rsp, 0B0h
0x18005c53a  mov     rax, cs:__security_cookie
0x18005c541  xor     rax, rsp
0x18005c544  mov     [rsp+0E8h+var_48], rax
0x18005c54c  mov     rax, [rcx+8]
0x18005c550  mov     r14, rdx
0x18005c553  mov     r15, [rcx+10h]
0x18005c557  xor     r9d, r9d
0x18005c55a  mov     [rsp+0E8h+var_A8], 0
0x18005c562  xor     edx, edx
0x18005c564  mov     [rsp+0E8h+var_A4], 0
0x18005c56c  mov     rcx, r15
0x18005c56f  mov     r12, [rax+78h]
0x18005c573  lea     rax, [rsp+0E8h+var_A8]
0x18005c578  mov     [rsp+0E8h+var_B8], 0
0x18005c580  mov     [rsp+0E8h+var_C0], rax
0x18005c585  mov     rax, r12
0x18005c588  mov     ebp, r8d
0x18005c58b  lea     r8, aKeydatablob; "KeyDataBlob"
0x18005c592  mov     [rsp+0E8h+var_C8], 0
0x18005c59a  call    _guard_dispatch_icall
0x18005c59f  mov     ebx, eax
0x18005c5a1  test    eax, eax
0x18005c5a3  jns     short loc_18005C5C5
0x18005c5a5  mov     r9d, 46h ; 'F'
0x18005c5ab  mov     ecx, eax
0x18005c5ad  lea     rdx, aStatus; "Status"
0x18005c5b4  lea     r8, aOnecoreDsSecur_22; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005c5bb  call    DebugTraceError
0x18005c5c0  jmp     loc_18005C69B
0x18005c5c5  mov     eax, [rsp+0E8h+var_A8]
0x18005c5c9  cmp     eax, 4Ch ; 'L'
0x18005c5cc  ja      short loc_18005C5D7
0x18005c5ce  xor     edi, edi
0x18005c5d0  lea     rsi, [rsp+0E8h+var_98]
0x18005c5d5  jmp     short loc_18005C5FE
0x18005c5d7  mov     rcx, rax
0x18005c5da  call    BCryptAlloc
0x18005c5df  mov     rdi, rax
0x18005c5e2  test    rax, rax
0x18005c5e5  jnz     short loc_18005C5F7
0x18005c5e7  mov     ebx, 0C0000017h
0x18005c5ec  lea     r9d, [rax+57h]
0x18005c5f0  mov     ecx, 0C0000017h
0x18005c5f5  jmp     short loc_18005C5AD
0x18005c5f7  mov     rsi, rax
0x18005c5fa  mov     eax, [rsp+0E8h+var_A8]
0x18005c5fe  lea     rcx, [rsp+0E8h+var_A4]
0x18005c603  mov     [rsp+0E8h+var_B8], 0
0x18005c60b  mov     [rsp+0E8h+var_C0], rcx
0x18005c610  lea     r8, aKeydatablob; "KeyDataBlob"
0x18005c617  mov     [rsp+0E8h+var_C8], eax
0x18005c61b  mov     r9, rsi
0x18005c61e  mov     rax, r12
0x18005c621  xor     edx, edx
0x18005c623  mov     rcx, r15
0x18005c626  call    _guard_dispatch_icall
0x18005c62b  mov     ebx, eax
0x18005c62d  test    eax, eax
0x18005c62f  jns     short loc_18005C64E
0x18005c631  mov     r9d, 6Bh ; 'k'
0x18005c637  mov     ecx, eax
0x18005c639  lea     rdx, aStatus; "Status"
0x18005c640  lea     r8, aOnecoreDsSecur_22; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005c647  call    DebugTraceError
0x18005c64c  jmp     short loc_18005C676
0x18005c64e  cmp     ebp, [rsi+8]
0x18005c651  jz      short loc_18005C665
0x18005c653  mov     ebx, 0C000000Dh
0x18005c658  mov     r9d, 74h ; 't'
0x18005c65e  mov     ecx, 0C000000Dh
0x18005c663  jmp     short loc_18005C639
0x18005c665  mov     r8, rbp; Size
0x18005c668  lea     rdx, [rsi+0Ch]; Src
0x18005c66c  mov     rcx, r14; void *
0x18005c66f  call    memmove
0x18005c674  xor     ebx, ebx
0x18005c676  test    rdi, rdi
0x18005c679  jz      short loc_18005C69B
0x18005c67b  mov     eax, [rsp+0E8h+var_A8]
0x18005c67f  mov     rcx, rdi
0x18005c682  test    rax, rax
0x18005c685  jz      short loc_18005C693
0x18005c687  mov     byte ptr [rcx], 0
0x18005c68a  inc     rcx
0x18005c68d  sub     rax, 1
0x18005c691  jnz     short loc_18005C687
0x18005c693  mov     rcx, rdi; P
0x18005c696  call    BCryptFree
0x18005c69b  mov     eax, ebx
0x18005c69d  mov     rcx, [rsp+0E8h+var_48]
0x18005c6a5  xor     rcx, rsp; StackCookie
0x18005c6a8  call    __security_check_cookie
0x18005c6ad  add     rsp, 0B0h
0x18005c6b4  pop     r15
0x18005c6b6  pop     r14
0x18005c6b8  pop     r12
0x18005c6ba  pop     rdi
0x18005c6bb  pop     rsi
0x18005c6bc  pop     rbp
0x18005c6bd  pop     rbx
0x18005c6be  retn
```
