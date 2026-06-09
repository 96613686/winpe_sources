# CLdapStore::InternalCommit(ulong)

- ea: `0x18001d22c`
- end: `0x18001d459`
- name: `?InternalCommit@CLdapStore@@AEAAHK@Z`
- size: `557`
- prototype: `__int64 __fastcall(CLdapStore *this, char)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001d04c`
- `0x18001d5d0`
- `0x18001d698`

## callees

- `0x180005980`
- `0x18000a990`
- `0x180011060`
- `0x180012f9c`
- `0x180018954`
- `0x180018aa4`
- `0x18001d22c`
- `0x18002656a`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d270`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d328`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d39a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d416`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d270`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d328`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d39a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d416`
- `WLDAP32!__imp_ldap_modify_sW` at `0x18001d3fa`
- `WLDAP32!__imp_ldap_modify_sW` at `0x18001d3fa`

## pseudocode

```c
__int64 __fastcall CLdapStore::InternalCommit(CLdapStore *this, char a2)
{
  unsigned int v2; // r15d
  char *v4; // r14
  DWORD v5; // ecx
  unsigned int v7; // ebx
  _QWORD *v8; // rsi
  void *v9; // r13
  unsigned int v10; // r12d
  _DWORD *v11; // rax
  _DWORD *v12; // rdx
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 *v15; // rax
  __int64 v16; // rcx
  DWORD v17; // eax
  LDAPModW *mods[2]; // [rsp+20h] [rbp-30h] BYREF
  __int128 v19; // [rsp+30h] [rbp-20h] BYREF
  _QWORD *v20; // [rsp+40h] [rbp-10h]
  unsigned int v21; // [rsp+98h] [rbp+48h]
  char *v22; // [rsp+A8h] [rbp+58h] BYREF

  v2 = 1;
  v22 = (char *)1;
  v4 = (char *)1;
  if ( (a2 & 2) != 0 )
  {
    *((_DWORD *)this + 29) = 0;
    return v2;
  }
  if ( (*((_DWORD *)this + 28) & 0x8000) != 0 )
  {
    v5 = 5;
LABEL_5:
    SetLastError(v5);
    return 0;
  }
  v7 = 0;
  if ( !*((_DWORD *)this + 29) && (a2 & 1) == 0 )
    return v2;
  v8 = (_QWORD *)PkiZeroAlloc(0x50u);
  if ( !v8 )
  {
    v5 = -2147024882;
    goto LABEL_5;
  }
  v9 = 0;
  v21 = 10;
  v10 = 0;
  do
  {
    v9 = ObjectContextEnumObjectsInStore(*((HCERTSTORE *)this + 13), v4, v9, (const char **)&v22);
    if ( !v9 )
      break;
    v11 = (_DWORD *)PkiZeroAlloc(0x10u);
    v12 = v11;
    v8[v10] = v11;
    if ( v11 )
    {
      v4 = v22;
      if ( v22 == (char *)1 )
      {
        *v11 = *((_DWORD *)v9 + 4);
        goto LABEL_18;
      }
      if ( v22 == (char *)3 || v22 == (char *)2 )
      {
        *v11 = *((_DWORD *)v9 + 4);
LABEL_18:
        v13 = *((_QWORD *)v9 + 1);
      }
      else
      {
        *v11 = 0;
        v13 = 0;
      }
      *((_QWORD *)v12 + 1) = v13;
      ++v10;
      goto LABEL_22;
    }
    SetLastError(0x8007000E);
    v4 = v22;
    v2 = 0;
    ObjectContextFree(v22, v9);
LABEL_22:
    if ( v10 == v21 - 1 )
    {
      if ( v21 > 0xFFFFFF || (v14 = PkiRealloc(v8, 8LL * (v21 + 50))) == 0 )
      {
        SetLastError(0x8007000E);
        v2 = 0;
        break;
      }
      v8 = (_QWORD *)v14;
      memset_0((void *)(v14 + 8LL * v21), 0, 0x190u);
      v21 += 50;
    }
  }
  while ( v2 == 1 );
  if ( v2 == 1 )
  {
    v20 = 0;
    v15 = (__int64 *)*((_QWORD *)this + 9);
    *(_OWORD *)mods = 0;
    v19 = 0;
    v16 = *v15;
    mods[0] = (LDAPModW *)&v19;
    *((_QWORD *)&v19 + 1) = v16;
    mods[1] = 0;
    if ( v10 )
    {
      LODWORD(v19) = 130;
      v20 = v8;
    }
    else
    {
      LODWORD(v19) = 129;
      v20 = 0;
    }
    if ( ldap_modify_sW(*((LDAP **)this + 12), *((PWSTR *)this + 7), mods) )
    {
      v17 = I_CryptNetLdapMapErrorToWin32(*((LDAP **)this + 12));
      SetLastError(v17);
      v2 = 0;
    }
    else
    {
      *((_DWORD *)this + 29) = 0;
    }
  }
  if ( v10 )
  {
    do
      operator delete((HLOCAL)v8[v7++]);
    while ( v7 < v10 );
  }
  operator delete(v8);
  return v2;
}

```

## disassembly

```asm
0x18001d22c  mov     [rsp-38h+arg_0], rbx
0x18001d231  push    rbp
0x18001d232  push    rsi
0x18001d233  push    rdi
0x18001d234  push    r12
0x18001d236  push    r13
0x18001d238  push    r14
0x18001d23a  push    r15
0x18001d23c  mov     rbp, rsp
0x18001d23f  sub     rsp, 50h
0x18001d243  mov     r15d, 1
0x18001d249  mov     rdi, rcx
0x18001d24c  mov     [rbp+arg_18], r15
0x18001d250  mov     r14d, r15d
0x18001d253  test    dl, 2
0x18001d256  jz      short loc_18001D262
0x18001d258  xor     ebx, ebx
0x18001d25a  mov     [rcx+74h], ebx
0x18001d25d  jmp     loc_18001D43E
0x18001d262  test    dword ptr [rcx+70h], 8000h
0x18001d269  jz      short loc_18001D27D
0x18001d26b  mov     ecx, 5; dwErrCode
0x18001d270  call    cs:__imp_SetLastError
0x18001d276  xor     eax, eax
0x18001d278  jmp     loc_18001D441
0x18001d27d  xor     ebx, ebx
0x18001d27f  cmp     [rcx+74h], ebx
0x18001d282  jnz     short loc_18001D28D
0x18001d284  test    r15b, dl
0x18001d287  jz      loc_18001D43E
0x18001d28d  mov     ecx, 50h ; 'P'; uBytes
0x18001d292  call    PkiZeroAlloc
0x18001d297  mov     rsi, rax
0x18001d29a  test    rax, rax
0x18001d29d  jnz     short loc_18001D2A6
0x18001d29f  mov     ecx, 8007000Eh
0x18001d2a4  jmp     short loc_18001D270
0x18001d2a6  mov     r13, rbx
0x18001d2a9  mov     [rbp+arg_8], 0Ah
0x18001d2b0  mov     r12d, ebx
0x18001d2b3  mov     rcx, [rdi+68h]; hCertStore
0x18001d2b7  lea     r9, [rbp+arg_18]; char **
0x18001d2bb  mov     r8, r13; void *
0x18001d2be  mov     rdx, r14; char *
0x18001d2c1  call    ?ObjectContextEnumObjectsInStore@@YAPEAXPEAXPEBD0PEAPEBD@Z; ObjectContextEnumObjectsInStore(void *,char const *,void *,char const * *)
0x18001d2c6  mov     r13, rax
0x18001d2c9  test    rax, rax
0x18001d2cc  jz      loc_18001D3A3
0x18001d2d2  mov     ecx, 10h; uBytes
0x18001d2d7  call    PkiZeroAlloc
0x18001d2dc  mov     ecx, r12d
0x18001d2df  mov     rdx, rax
0x18001d2e2  mov     [rsi+rcx*8], rax
0x18001d2e6  test    rax, rax
0x18001d2e9  jz      short loc_18001D323
0x18001d2eb  mov     r14, [rbp+arg_18]
0x18001d2ef  cmp     r14, 1
0x18001d2f3  jnz     short loc_18001D2FD
0x18001d2f5  mov     ecx, [r13+10h]
0x18001d2f9  mov     [rax], ecx
0x18001d2fb  jmp     short loc_18001D30F
0x18001d2fd  cmp     r14, 3
0x18001d301  jz      short loc_18001D309
0x18001d303  cmp     r14, 2
0x18001d307  jnz     short loc_18001D315
0x18001d309  mov     eax, [r13+10h]
0x18001d30d  mov     [rdx], eax
0x18001d30f  mov     rax, [r13+8]
0x18001d313  jmp     short loc_18001D31A
0x18001d315  mov     [rax], ebx
0x18001d317  mov     rax, rbx
0x18001d31a  mov     [rdx+8], rax
0x18001d31e  inc     r12d
0x18001d321  jmp     short loc_18001D340
0x18001d323  mov     ecx, 8007000Eh; dwErrCode
0x18001d328  call    cs:__imp_SetLastError
0x18001d32e  mov     r14, [rbp+arg_18]
0x18001d332  mov     rdx, r13; void *
0x18001d335  mov     rcx, r14; char *
0x18001d338  mov     r15d, ebx
0x18001d33b  call    ?ObjectContextFree@@YAXPEBDPEAX@Z; ObjectContextFree(char const *,void *)
0x18001d340  mov     ecx, [rbp+arg_8]
0x18001d343  lea     eax, [rcx-1]
0x18001d346  cmp     r12d, eax
0x18001d349  jnz     short loc_18001D389
0x18001d34b  cmp     ecx, 0FFFFFFh
0x18001d351  ja      short loc_18001D395
0x18001d353  lea     eax, [rcx+32h]
0x18001d356  mov     rcx, rsi
0x18001d359  mov     edx, eax
0x18001d35b  shl     rdx, 3
0x18001d35f  mov     [rbp+arg_10], eax
0x18001d362  call    PkiRealloc
0x18001d367  test    rax, rax
0x18001d36a  jz      short loc_18001D395
0x18001d36c  mov     ecx, [rbp+arg_8]
0x18001d36f  xor     edx, edx; Val
0x18001d371  mov     r8d, 190h; Size
0x18001d377  mov     rsi, rax
0x18001d37a  lea     rcx, [rax+rcx*8]; void *
0x18001d37e  call    memset_0
0x18001d383  mov     ecx, [rbp+arg_10]
0x18001d386  mov     [rbp+arg_8], ecx
0x18001d389  cmp     r15d, 1
0x18001d38d  jz      loc_18001D2B3
0x18001d393  jmp     short loc_18001D3A3
0x18001d395  mov     ecx, 8007000Eh; dwErrCode
0x18001d39a  call    cs:__imp_SetLastError
0x18001d3a0  mov     r15d, ebx
0x18001d3a3  cmp     r15d, 1
0x18001d3a7  jnz     short loc_18001D41F
0x18001d3a9  xor     eax, eax
0x18001d3ab  xorps   xmm0, xmm0
0x18001d3ae  mov     [rbp+var_10], rax
0x18001d3b2  mov     rax, [rdi+48h]
0x18001d3b6  movups  xmmword ptr [rbp+mods], xmm0
0x18001d3ba  movups  [rbp+var_20], xmm0
0x18001d3be  mov     rcx, [rax]
0x18001d3c1  lea     rax, [rbp+var_20]
0x18001d3c5  mov     [rbp+mods], rax
0x18001d3c9  mov     qword ptr [rbp+var_20+8], rcx
0x18001d3cd  mov     [rbp+mods+8], rbx
0x18001d3d1  test    r12d, r12d
0x18001d3d4  jz      short loc_18001D3E3
0x18001d3d6  mov     dword ptr [rbp+var_20], 82h
0x18001d3dd  mov     [rbp+var_10], rsi
0x18001d3e1  jmp     short loc_18001D3EE
0x18001d3e3  mov     dword ptr [rbp+var_20], 81h
0x18001d3ea  mov     [rbp+var_10], rbx
0x18001d3ee  mov     rdx, [rdi+38h]; dn
0x18001d3f2  lea     r8, [rbp+mods]; mods
0x18001d3f6  mov     rcx, [rdi+60h]; ld
0x18001d3fa  call    cs:__imp_ldap_modify_sW
0x18001d400  test    eax, eax
0x18001d402  jnz     short loc_18001D409
0x18001d404  mov     [rdi+74h], ebx
0x18001d407  jmp     short loc_18001D41F
0x18001d409  mov     rcx, [rdi+60h]; ld
0x18001d40d  mov     edx, eax
0x18001d40f  call    I_CryptNetLdapMapErrorToWin32
0x18001d414  mov     ecx, eax; dwErrCode
0x18001d416  call    cs:__imp_SetLastError
0x18001d41c  mov     r15d, ebx
0x18001d41f  test    r12d, r12d
0x18001d422  jz      short loc_18001D436
0x18001d424  mov     ecx, ebx
0x18001d426  mov     rcx, [rsi+rcx*8]; hMem
0x18001d42a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001d42f  inc     ebx
0x18001d431  cmp     ebx, r12d
0x18001d434  jb      short loc_18001D424
0x18001d436  mov     rcx, rsi; hMem
0x18001d439  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001d43e  mov     eax, r15d
0x18001d441  mov     rbx, [rsp+50h+arg_0]
0x18001d449  add     rsp, 50h
0x18001d44d  pop     r15
0x18001d44f  pop     r14
0x18001d451  pop     r13
0x18001d453  pop     r12
0x18001d455  pop     rdi
0x18001d456  pop     rsi
0x18001d457  pop     rbp
0x18001d458  retn
```
