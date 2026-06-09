# VerifyCredentials(_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *)

- ea: `0x1800a7290`
- end: `0x1800a757d`
- name: `?VerifyCredentials@@YAJPEAU_UNICODE_STRING@@00@Z`
- size: `749`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800a6dd0`

## callees

- `0x180070680`
- `0x18007108c`
- `0x1800a7290`

## import_xrefs

- `SAMSRV!SamIFree_SAMPR_USER_INFO_BUFFER` at `0x1800a74f2`
- `SAMSRV!SamIFree_SAMPR_USER_INFO_BUFFER` at `0x1800a74f2`
- `SAMSRV!SamIUpdateLogonStatistics` at `0x1800a7529`
- `SAMSRV!SamIUpdateLogonStatistics` at `0x1800a7529`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x1800a754d`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x1800a754d`
- `SAMSRV!SamrOpenDomain` at `0x1800a7370`
- `SAMSRV!SamrOpenDomain` at `0x1800a7370`
- `SAMSRV!SamrCloseHandle` at `0x1800a7339`
- `SAMSRV!SamrCloseHandle` at `0x1800a73a7`
- `SAMSRV!SamrCloseHandle` at `0x1800a753b`
- `SAMSRV!SamrCloseHandle` at `0x1800a7339`
- `SAMSRV!SamrCloseHandle` at `0x1800a73a7`
- `SAMSRV!SamrCloseHandle` at `0x1800a753b`
- `SAMSRV!SamIConnect` at `0x1800a7312`
- `SAMSRV!SamIConnect` at `0x1800a7312`
- `SAMSRV!SamIGetUserLogonInformationEx` at `0x1800a73e0`
- `SAMSRV!SamIGetUserLogonInformationEx` at `0x1800a7425`
- `SAMSRV!SamIGetUserLogonInformationEx` at `0x1800a73e0`
- `SAMSRV!SamIGetUserLogonInformationEx` at `0x1800a7425`
- `CRYPTSP!SystemFunction007` at `0x1800a7442`
- `CRYPTSP!SystemFunction007` at `0x1800a7442`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x1800a7382`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x1800a7382`
- `LSASRV!LsaIQueryInformationPolicyTrusted` at `0x1800a7349`
- `LSASRV!LsaIQueryInformationPolicyTrusted` at `0x1800a7349`

## pseudocode

```c
__int64 __fastcall VerifyCredentials(
        struct _UNICODE_STRING *a1,
        struct _UNICODE_STRING *a2,
        struct _UNICODE_STRING *a3,
        __int64 a4)
{
  bool v6; // si
  __int64 v7; // r14
  int v8; // ebx
  __int64 v9; // rdi
  char v10; // r8
  __int64 j; // rdx
  CHAR v12; // cl
  char v13; // al
  __int64 i; // rdx
  char v15; // cl
  char v16; // al
  __int128 *v17; // rax
  int v18; // eax
  __int64 v20; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v21; // [rsp+48h] [rbp-B8h] BYREF
  signed __int64 v22; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v23; // [rsp+58h] [rbp-A8h] BYREF
  signed __int64 v24; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v25; // [rsp+68h] [rbp-98h] BYREF
  __int64 v26; // [rsp+70h] [rbp-90h]
  __int128 v27; // [rsp+78h] [rbp-88h] BYREF
  int v28; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v29[188]; // [rsp+94h] [rbp-6Ch] BYREF

  v20 = 0;
  v21 = 0;
  v6 = 0;
  v7 = 16;
  v25 = 0;
  v27 = 0;
  v26 = 0;
  if ( !KerbGlobalDomainHandle )
  {
    LOBYTE(a4) = 1;
    v22 = 0;
    v24 = 0;
    v23 = 0;
    v8 = SamIConnect(0, &v22, 0, a4);
    if ( v8 < 0 )
      goto LABEL_24;
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&KerbGlobalSamHandle, v22, 0) )
      SamrCloseHandle(&v22);
    v8 = LsaIQueryInformationPolicyTrusted(5, &v23);
    if ( v8 < 0 )
      goto LABEL_24;
    v8 = SamrOpenDomain(KerbGlobalSamHandle, 0, *(_QWORD *)(v23 + 16), &v24);
    LsaIFree_LSAPR_POLICY_INFORMATION(5, v23);
    if ( v8 < 0 )
      goto LABEL_24;
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&KerbGlobalDomainHandle, v24, 0) )
      SamrCloseHandle(&v24);
  }
  v8 = SamIGetUserLogonInformationEx(KerbGlobalDomainHandle, 2056, a1, 554713088, &v21, &v25);
  if ( (unsigned int)(v8 + 1073741773) <= 1 )
    v8 = SamIGetUserLogonInformationEx(KerbGlobalDomainHandle, 520, a1, 554713088, &v21, &v25);
  if ( v8 >= 0 )
  {
    v9 = v21;
    v8 = SystemFunction007(a3, &v27);
    if ( v8 >= 0 )
    {
      v8 = -1073741715;
      if ( (*(_DWORD *)(v9 + 280) & 0x401) == 0 )
      {
        if ( *(_BYTE *)(v9 + 313) )
        {
          v10 = 0;
          for ( i = 0; i != 16; ++i )
          {
            v15 = *(_BYTE *)(i + *(_QWORD *)(v9 + 232));
            v16 = *((_BYTE *)&v27 + i);
            v10 |= v16 ^ v15;
          }
        }
        else
        {
          if ( *(_BYTE *)(v9 + 312) )
            goto LABEL_24;
          v10 = 0;
          for ( j = 0; j != 16; ++j )
          {
            v12 = KerbGlobalNullNtOwfPassword.data[0].data[j];
            v13 = *((_BYTE *)&v27 + j);
            v10 |= v13 ^ v12;
          }
        }
        if ( v10 )
        {
          v6 = 1;
        }
        else
        {
          v8 = 0;
          v6 = *(_WORD *)(v9 + 304) != 0;
        }
      }
    }
  }
LABEL_24:
  v17 = &v27;
  do
  {
    *(_BYTE *)v17 = 0;
    v17 = (__int128 *)((char *)v17 + 1);
    --v7;
  }
  while ( v7 );
  if ( v21 )
    SamIFree_SAMPR_USER_INFO_BUFFER(v21, 21);
  if ( v6 )
  {
    memset_0(v29, 0, sizeof(v29));
    v18 = 0x8000000;
    if ( v8 >= 0 )
      v18 = 0x1000000;
    v28 = v18;
    SamIUpdateLogonStatistics(v20, &v28);
  }
  if ( v20 )
    SamrCloseHandle(&v20);
  if ( v26 )
    SamIFreeSidAndAttributesList(&v25);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800a7290  mov     [rsp-8+arg_8], rbx
0x1800a7295  mov     [rsp-8+arg_18], rsi
0x1800a729a  push    rbp
0x1800a729b  push    rdi
0x1800a729c  push    r12
0x1800a729e  push    r14
0x1800a72a0  push    r15
0x1800a72a2  lea     rbp, [rsp-60h]
0x1800a72a7  sub     rsp, 160h
0x1800a72ae  mov     rax, cs:__security_cookie
0x1800a72b5  xor     rax, rsp
0x1800a72b8  mov     [rbp+80h+var_30], rax
0x1800a72bc  xor     r12d, r12d
0x1800a72bf  xorps   xmm0, xmm0
0x1800a72c2  cmp     cs:?KerbGlobalDomainHandle@@3PEAXEA, r12; void * KerbGlobalDomainHandle
0x1800a72c9  mov     r15, r8
0x1800a72cc  mov     rdi, rcx
0x1800a72cf  mov     [rsp+180h+var_140], r12
0x1800a72d4  mov     [rsp+180h+var_138], r12
0x1800a72d9  mov     sil, r12b
0x1800a72dc  lea     r14d, [r12+10h]
0x1800a72e1  mov     [rsp+180h+var_118], r12
0x1800a72e6  movups  [rsp+180h+var_108], xmm0
0x1800a72eb  mov     [rsp+180h+var_110], r12
0x1800a72f0  jnz     loc_1800A73AD
0x1800a72f6  mov     r9b, 1
0x1800a72f9  mov     [rsp+180h+var_130], r12
0x1800a72fe  xor     r8d, r8d
0x1800a7301  mov     [rsp+180h+var_120], r12
0x1800a7306  lea     rdx, [rsp+180h+var_130]
0x1800a730b  mov     [rsp+180h+var_128], r12
0x1800a7310  xor     ecx, ecx
0x1800a7312  call    cs:__imp_SamIConnect
0x1800a7318  mov     ebx, eax
0x1800a731a  test    eax, eax
0x1800a731c  js      loc_1800A74D3
0x1800a7322  mov     rcx, [rsp+180h+var_130]
0x1800a7327  xor     eax, eax
0x1800a7329  lock cmpxchg cs:?KerbGlobalSamHandle@@3PEAXEA, rcx; void * KerbGlobalSamHandle
0x1800a7332  jz      short loc_1800A733F
0x1800a7334  lea     rcx, [rsp+180h+var_130]
0x1800a7339  call    cs:__imp_SamrCloseHandle
0x1800a733f  lea     rdx, [rsp+180h+var_128]
0x1800a7344  mov     ecx, 5
0x1800a7349  call    cs:__imp_LsaIQueryInformationPolicyTrusted
0x1800a734f  mov     ebx, eax
0x1800a7351  test    eax, eax
0x1800a7353  js      loc_1800A74D3
0x1800a7359  mov     r8, [rsp+180h+var_128]
0x1800a735e  lea     r9, [rsp+180h+var_120]
0x1800a7363  mov     rcx, cs:?KerbGlobalSamHandle@@3PEAXEA; void * KerbGlobalSamHandle
0x1800a736a  xor     edx, edx
0x1800a736c  mov     r8, [r8+10h]
0x1800a7370  call    cs:__imp_SamrOpenDomain
0x1800a7376  mov     rdx, [rsp+180h+var_128]
0x1800a737b  mov     ecx, 5
0x1800a7380  mov     ebx, eax
0x1800a7382  call    cs:__imp_LsaIFree_LSAPR_POLICY_INFORMATION
0x1800a7388  test    ebx, ebx
0x1800a738a  js      loc_1800A74D3
0x1800a7390  mov     rcx, [rsp+180h+var_120]
0x1800a7395  xor     eax, eax
0x1800a7397  lock cmpxchg cs:?KerbGlobalDomainHandle@@3PEAXEA, rcx; void * KerbGlobalDomainHandle
0x1800a73a0  jz      short loc_1800A73AD
0x1800a73a2  lea     rcx, [rsp+180h+var_120]
0x1800a73a7  call    cs:__imp_SamrCloseHandle
0x1800a73ad  mov     rcx, cs:?KerbGlobalDomainHandle@@3PEAXEA; void * KerbGlobalDomainHandle
0x1800a73b4  lea     rax, [rsp+180h+var_140]
0x1800a73b9  mov     [rsp+180h+var_150], rax
0x1800a73be  mov     r9d, 21104000h
0x1800a73c4  lea     rax, [rsp+180h+var_118]
0x1800a73c9  mov     r8, rdi
0x1800a73cc  mov     [rsp+180h+var_158], rax
0x1800a73d1  mov     edx, 808h
0x1800a73d6  lea     rax, [rsp+180h+var_138]
0x1800a73db  mov     [rsp+180h+var_160], rax
0x1800a73e0  call    cs:__imp_SamIGetUserLogonInformationEx
0x1800a73e6  mov     ebx, eax
0x1800a73e8  add     eax, 3FFFFFCDh
0x1800a73ed  cmp     eax, 1
0x1800a73f0  ja      short loc_1800A742D
0x1800a73f2  mov     rcx, cs:?KerbGlobalDomainHandle@@3PEAXEA; void * KerbGlobalDomainHandle
0x1800a73f9  lea     rax, [rsp+180h+var_140]
0x1800a73fe  mov     [rsp+180h+var_150], rax
0x1800a7403  mov     r9d, 21104000h
0x1800a7409  lea     rax, [rsp+180h+var_118]
0x1800a740e  mov     r8, rdi
0x1800a7411  mov     [rsp+180h+var_158], rax
0x1800a7416  mov     edx, 208h
0x1800a741b  lea     rax, [rsp+180h+var_138]
0x1800a7420  mov     [rsp+180h+var_160], rax
0x1800a7425  call    cs:__imp_SamIGetUserLogonInformationEx
0x1800a742b  mov     ebx, eax
0x1800a742d  test    ebx, ebx
0x1800a742f  js      loc_1800A74D3
0x1800a7435  mov     rdi, [rsp+180h+var_138]
0x1800a743a  lea     rdx, [rsp+180h+var_108]
0x1800a743f  mov     rcx, r15
0x1800a7442  call    cs:__imp_SystemFunction007
0x1800a7448  mov     ebx, eax
0x1800a744a  test    eax, eax
0x1800a744c  js      loc_1800A74D3
0x1800a7452  test    dword ptr [rdi+118h], 401h
0x1800a745c  mov     ebx, 0C000006Dh
0x1800a7461  jnz     short loc_1800A74D3
0x1800a7463  cmp     [rdi+139h], r12b
0x1800a746a  jnz     short loc_1800A74A0
0x1800a746c  cmp     [rdi+138h], r12b
0x1800a7473  jnz     short loc_1800A74D3
0x1800a7475  mov     r8b, r12b
0x1800a7478  mov     rdx, r12
0x1800a747b  lea     rcx, ?KerbGlobalNullNtOwfPassword@@3U_LM_OWF_PASSWORD@@A; _LM_OWF_PASSWORD KerbGlobalNullNtOwfPassword
0x1800a7482  mov     cl, [rdx+rcx]
0x1800a7485  mov     al, byte ptr [rsp+rdx+180h+var_108]
0x1800a7489  inc     rdx
0x1800a748c  xor     cl, al
0x1800a748e  or      r8b, cl
0x1800a7491  cmp     rdx, r14
0x1800a7494  jnz     short loc_1800A747B
0x1800a7496  test    r8b, r8b
0x1800a7499  jz      short loc_1800A74C4
0x1800a749b  mov     sil, 1
0x1800a749e  jmp     short loc_1800A74D3
0x1800a74a0  mov     r9, [rdi+0E8h]
0x1800a74a7  mov     r8b, r12b
0x1800a74aa  mov     rdx, r12
0x1800a74ad  mov     cl, [rdx+r9]
0x1800a74b1  mov     al, byte ptr [rsp+rdx+180h+var_108]
0x1800a74b5  inc     rdx
0x1800a74b8  xor     cl, al
0x1800a74ba  or      r8b, cl
0x1800a74bd  cmp     rdx, r14
0x1800a74c0  jnz     short loc_1800A74AD
0x1800a74c2  jmp     short loc_1800A7496
0x1800a74c4  cmp     [rdi+130h], r12w
0x1800a74cc  mov     ebx, r12d
0x1800a74cf  setnz   sil
0x1800a74d3  lea     rax, [rsp+180h+var_108]
0x1800a74d8  mov     [rax], r12b
0x1800a74db  inc     rax
0x1800a74de  sub     r14, 1
0x1800a74e2  jnz     short loc_1800A74D8
0x1800a74e4  mov     rcx, [rsp+180h+var_138]
0x1800a74e9  test    rcx, rcx
0x1800a74ec  jz      short loc_1800A74F8
0x1800a74ee  lea     edx, [r14+15h]
0x1800a74f2  call    cs:__imp_SamIFree_SAMPR_USER_INFO_BUFFER
0x1800a74f8  test    sil, sil
0x1800a74fb  jz      short loc_1800A752F
0x1800a74fd  xor     edx, edx; Val
0x1800a74ff  lea     rcx, [rbp+80h+var_EC]; void *
0x1800a7503  mov     r8d, 0BCh; Size
0x1800a7509  call    memset_0
0x1800a750e  test    ebx, ebx
0x1800a7510  lea     rdx, [rbp+80h+var_F0]
0x1800a7514  mov     eax, 8000000h
0x1800a7519  mov     ecx, 1000000h
0x1800a751e  cmovns  eax, ecx
0x1800a7521  mov     rcx, [rsp+180h+var_140]
0x1800a7526  mov     [rbp+80h+var_F0], eax
0x1800a7529  call    cs:__imp_SamIUpdateLogonStatistics
0x1800a752f  cmp     [rsp+180h+var_140], r12
0x1800a7534  jz      short loc_1800A7541
0x1800a7536  lea     rcx, [rsp+180h+var_140]
0x1800a753b  call    cs:__imp_SamrCloseHandle
0x1800a7541  cmp     [rsp+180h+var_110], r12
0x1800a7546  jz      short loc_1800A7553
0x1800a7548  lea     rcx, [rsp+180h+var_118]
0x1800a754d  call    cs:__imp_SamIFreeSidAndAttributesList
0x1800a7553  mov     eax, ebx
0x1800a7555  mov     rcx, [rbp+80h+var_30]
0x1800a7559  xor     rcx, rsp; StackCookie
0x1800a755c  call    __security_check_cookie
0x1800a7561  lea     r11, [rsp+180h+var_20]
0x1800a7569  mov     rbx, [r11+38h]
0x1800a756d  mov     rsi, [r11+48h]
0x1800a7571  mov     rsp, r11
0x1800a7574  pop     r15
0x1800a7576  pop     r14
0x1800a7578  pop     r12
0x1800a757a  pop     rdi
0x1800a757b  pop     rbp
0x1800a757c  retn
```
