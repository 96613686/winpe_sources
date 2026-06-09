# FindNodeInCachedCredList(_EAPTLS_CONTROL_BLOCK *,int,int)

- ea: `0x18006e0f8`
- end: `0x18006e474`
- name: `?FindNodeInCachedCredList@@YAPEAU_EAPTLS_CACHED_CREDS@@PEAU_EAPTLS_CONTROL_BLOCK@@HH@Z`
- size: `892`
- prototype: `struct _EAPTLS_CACHED_CREDS *__fastcall(struct _EAPTLS_CONTROL_BLOCK *, int, int)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180022a48`
- `0x180051510`
- `0x18006dca8`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x18001e8f0`
- `0x18002ce48`
- `0x180032acc`
- `0x180035680`
- `0x180036230`
- `0x18006e0f8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006e2c1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006e2c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e356`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e418`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e356`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e418`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006e334`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006e334`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006e31e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006e31e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006e44b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006e44b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006e3fe`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006e3fe`

## pseudocode

```c
struct _EAPTLS_CACHED_CREDS *__fastcall FindNodeInCachedCredList(
        struct _EAPTLS_CONTROL_BLOCK *a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD *v3; // rbx
  int v5; // r13d
  struct _EAPTLS_CONTROL_BLOCK *v6; // rcx
  unsigned int *v7; // r12
  int v8; // edx
  __int64 v9; // rdx
  int v10; // eax
  unsigned int v11; // edi
  __int64 v12; // rax
  _DWORD *v13; // rsi
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  __int64 v16; // rdx
  __int64 v17; // rdx
  int v19; // [rsp+30h] [rbp-39h]
  DWORD ReturnLength; // [rsp+34h] [rbp-35h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-31h] BYREF
  __int128 TokenInformation; // [rsp+40h] [rbp-29h] BYREF
  __int128 v23; // [rsp+50h] [rbp-19h]
  __int128 v24; // [rsp+60h] [rbp-9h]
  __int64 v25; // [rsp+70h] [rbp+7h]

  v3 = g_pCachedCreds;
  v19 = a2;
  v5 = a3;
  v25 = 0;
  ReturnLength = 0;
  TokenHandle = 0;
  TokenInformation = 0;
  v23 = 0;
  v24 = 0;
  v6 = WPP_GLOBAL_Control;
  v7 = (unsigned int *)((char *)a1 + 4);
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    WPP_SF_Ddd(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, *v7, a2, a3);
    v6 = WPP_GLOBAL_Control;
  }
  v8 = *v7;
  if ( (*v7 & 4) != 0 )
  {
    if ( v6 == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_56;
    v9 = 16;
    goto LABEL_6;
  }
  if ( (v8 & 0x400000) != 0 )
  {
    if ( v6 == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_56;
    v9 = 17;
LABEL_6:
    WPP_SF_(*((_QWORD *)v6 + 2), v9, &WPP_9b7471db29383f688da4f00fe4f52bf0_Traceguids);
    goto LABEL_56;
  }
  if ( (v8 & 0x4000) != 0 )
    v10 = 2;
  else
    v10 = (v8 & 0x10000) != 0 ? 4 : 1;
  v11 = v10 | (16 * (*v7 & 1)) | ((*v7 & 0x400) != 0 ? 0x40 : 0) | ((*v7 & 0x1000 | (*v7 >> 1) & 0x4000) >> 9);
  if ( (v8 & 1) == 0 )
  {
    v12 = *((_QWORD *)a1 + 68);
    if ( v12 && (*(_BYTE *)(v12 + 8) & 1) == 0 )
      v11 |= 0x80u;
    if ( (v8 & 0x4000) != 0 && (v8 & 0x400) == 0 && v12 )
    {
      if ( (*(_BYTE *)(v12 + 8) & 0x20) != 0 )
      {
        v11 |= 0x100u;
      }
      else if ( (*(_DWORD *)(v12 + 8) & 0x200) != 0 )
      {
        v11 |= 0x200u;
      }
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EapServerTls13>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EapServerTls13>::GetImpl'::`2'::impl) )
    v11 |= *((_DWORD *)a1 + 158) != 0 ? 0x400 : 0;
  if ( !v3 )
    goto LABEL_57;
  while ( 1 )
  {
    v13 = v3 + 4;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        &WPP_9b7471db29383f688da4f00fe4f52bf0_Traceguids,
        (unsigned int)*v13);
    if ( (v11 & 0x10) == 0 && (unsigned int)_o__wcsicmp((char *)v3 + 92, (char *)a1 + 16) )
      goto LABEL_49;
    if ( v19 )
      break;
    if ( (v11 & 2) == 0 || (v11 & 0x10) != 0 )
    {
      if ( *v13 != v11 )
        goto LABEL_49;
      if ( !*((_DWORD *)v3 + 2) )
        goto LABEL_49;
      v17 = *((_QWORD *)a1 + 71);
      if ( !v17 || memcmp_0((char *)v3 + 12, (const void *)(v17 + 20), *((unsigned int *)v3 + 2)) )
        goto LABEL_49;
      goto LABEL_48;
    }
    if ( *v13 == v11 )
      goto LABEL_38;
LABEL_49:
    v3 = (_QWORD *)*v3;
    if ( !v3 )
      goto LABEL_57;
  }
  v11 |= 0x20u;
  if ( *v13 != v11 || !*((_QWORD *)a1 + 71) )
    goto LABEL_49;
LABEL_48:
  if ( !v3[7] )
    goto LABEL_49;
LABEL_38:
  if ( (*(_BYTE *)v7 & 1) == 0 && v5 )
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    {
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        LastError = GetLastError();
        v16 = 19;
        goto LABEL_43;
      }
      goto LABEL_56;
    }
    v25 = 0;
    TokenInformation = 0;
    v23 = 0;
    v24 = 0;
    if ( GetTokenInformation(TokenHandle, TokenStatistics, &TokenInformation, 0x38u, &ReturnLength) )
    {
      if ( *((_QWORD *)&TokenInformation + 1) != v3[10] )
      {
        RemoveNodeFromCachedCredList(v3);
        goto LABEL_56;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        LastError = GetLastError();
        v16 = 20;
LABEL_43:
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, &WPP_9b7471db29383f688da4f00fe4f52bf0_Traceguids, LastError);
      }
LABEL_56:
      v3 = 0;
    }
  }
LABEL_57:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (struct _EAPTLS_CACHED_CREDS *)v3;
}

```

## disassembly

```asm
0x18006e0f8  push    rbp
0x18006e0fa  push    rbx
0x18006e0fb  push    rsi
0x18006e0fc  push    rdi
0x18006e0fd  push    r12
0x18006e0ff  push    r13
0x18006e101  push    r14
0x18006e103  push    r15
0x18006e105  lea     rbp, [rsp-1Fh]
0x18006e10a  sub     rsp, 88h
0x18006e111  mov     rax, cs:__security_cookie
0x18006e118  xor     rax, rsp
0x18006e11b  mov     [rbp+57h+var_48], rax
0x18006e11f  mov     rbx, cs:?g_pCachedCreds@@3PEAU_EAPTLS_CACHED_CREDS@@EA; _EAPTLS_CACHED_CREDS * g_pCachedCreds
0x18006e126  xorps   xmm0, xmm0
0x18006e129  mov     r15, rcx
0x18006e12c  mov     [rbp+57h+var_90], edx
0x18006e12f  xor     ecx, ecx
0x18006e131  mov     r13d, r8d
0x18006e134  mov     [rbp+57h+var_50], rcx
0x18006e138  mov     [rbp+57h+var_8C], ecx
0x18006e13b  mov     [rbp+57h+TokenHandle], rcx
0x18006e13f  movups  [rbp+57h+TokenInformation], xmm0
0x18006e143  movups  [rbp+57h+var_70], xmm0
0x18006e147  movups  [rbp+57h+var_60], xmm0
0x18006e14b  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e152  lea     r14, WPP_GLOBAL_Control
0x18006e159  lea     r12, [r15+4]
0x18006e15d  cmp     rcx, r14
0x18006e160  jz      short loc_18006E17F
0x18006e162  mov     r9d, [r12]
0x18006e166  mov     rcx, [rcx+10h]
0x18006e16a  mov     [rsp+0C0h+var_98], r8d
0x18006e16f  mov     dword ptr [rsp+0C0h+ReturnLength], edx
0x18006e173  call    WPP_SF_Ddd
0x18006e178  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e17f  mov     edx, [r12]
0x18006e183  test    dl, 4
0x18006e186  jz      short loc_18006E1AB
0x18006e188  cmp     rcx, r14
0x18006e18b  jz      loc_18006E440
0x18006e191  mov     edx, 10h
0x18006e196  mov     rcx, [rcx+10h]
0x18006e19a  lea     r8, WPP_9b7471db29383f688da4f00fe4f52bf0_Traceguids
0x18006e1a1  call    WPP_SF_
0x18006e1a6  jmp     loc_18006E440
0x18006e1ab  bt      edx, 16h
0x18006e1af  jnb     short loc_18006E1C1
0x18006e1b1  cmp     rcx, r14
0x18006e1b4  jz      loc_18006E440
0x18006e1ba  mov     edx, 11h
0x18006e1bf  jmp     short loc_18006E196
0x18006e1c1  mov     r10d, 4000h
0x18006e1c7  mov     edi, edx
0x18006e1c9  shr     edi, 1
0x18006e1cb  mov     eax, edx
0x18006e1cd  and     edi, r10d
0x18006e1d0  and     eax, 1000h
0x18006e1d5  or      edi, eax
0x18006e1d7  mov     r9d, edx
0x18006e1da  shr     edi, 9
0x18006e1dd  mov     esi, 400h
0x18006e1e2  and     r9d, esi
0x18006e1e5  mov     r8d, edx
0x18006e1e8  and     r8d, 1
0x18006e1ec  mov     eax, r9d
0x18006e1ef  neg     eax
0x18006e1f1  mov     eax, r8d
0x18006e1f4  sbb     ecx, ecx
0x18006e1f6  shl     eax, 4
0x18006e1f9  and     ecx, 40h
0x18006e1fc  or      edi, ecx
0x18006e1fe  mov     ecx, edx
0x18006e200  or      edi, eax
0x18006e202  and     ecx, r10d
0x18006e205  jz      short loc_18006E20E
0x18006e207  mov     eax, 2
0x18006e20c  jmp     short loc_18006E21D
0x18006e20e  and     edx, 10000h
0x18006e214  neg     edx
0x18006e216  sbb     eax, eax
0x18006e218  and     eax, 3
0x18006e21b  inc     eax
0x18006e21d  or      edi, eax
0x18006e21f  test    r8d, r8d
0x18006e222  jnz     short loc_18006E260
0x18006e224  mov     rax, [r15+220h]
0x18006e22b  test    rax, rax
0x18006e22e  jz      short loc_18006E23A
0x18006e230  test    byte ptr [rax+8], 1
0x18006e234  jnz     short loc_18006E23A
0x18006e236  bts     edi, 7
0x18006e23a  test    ecx, ecx
0x18006e23c  jz      short loc_18006E260
0x18006e23e  test    r9d, r9d
0x18006e241  jnz     short loc_18006E260
0x18006e243  test    rax, rax
0x18006e246  jz      short loc_18006E260
0x18006e248  test    byte ptr [rax+8], 20h
0x18006e24c  jz      short loc_18006E254
0x18006e24e  bts     edi, 8
0x18006e252  jmp     short loc_18006E260
0x18006e254  mov     ecx, 200h
0x18006e259  test    [rax+8], ecx
0x18006e25c  jz      short loc_18006E260
0x18006e25e  or      edi, ecx
0x18006e260  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EapServerTls13@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EapServerTls13@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EapServerTls13> `wil::Feature<__WilFeatureTraits_Feature_EapServerTls13>::GetImpl(void)'::`2'::impl
0x18006e267  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EapServerTls13@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EapServerTls13>::__private_IsEnabled(void)
0x18006e26c  test    al, al
0x18006e26e  jz      short loc_18006E27F
0x18006e270  xor     eax, eax
0x18006e272  cmp     eax, [r15+278h]
0x18006e279  sbb     eax, eax
0x18006e27b  and     eax, esi
0x18006e27d  or      edi, eax
0x18006e27f  test    rbx, rbx
0x18006e282  jz      loc_18006E442
0x18006e288  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e28f  lea     rsi, [rbx+20h]
0x18006e293  cmp     rcx, r14
0x18006e296  jz      short loc_18006E2B0
0x18006e298  mov     r9d, [rsi]
0x18006e29b  lea     r8, WPP_9b7471db29383f688da4f00fe4f52bf0_Traceguids
0x18006e2a2  mov     rcx, [rcx+10h]
0x18006e2a6  mov     edx, 12h
0x18006e2ab  call    WPP_SF_d
0x18006e2b0  mov     r14d, edi
0x18006e2b3  and     r14d, 10h
0x18006e2b7  jnz     short loc_18006E2CF
0x18006e2b9  lea     rdx, [r15+10h]
0x18006e2bd  lea     rcx, [rbx+5Ch]
0x18006e2c1  call    cs:__imp__o__wcsicmp
0x18006e2c7  test    eax, eax
0x18006e2c9  jnz     loc_18006E3B6
0x18006e2cf  cmp     [rbp+57h+var_90], 0
0x18006e2d3  jz      short loc_18006E2F3
0x18006e2d5  or      edi, 20h
0x18006e2d8  cmp     [rsi], edi
0x18006e2da  jnz     loc_18006E3B6
0x18006e2e0  cmp     qword ptr [r15+238h], 0
0x18006e2e8  jz      loc_18006E3B6
0x18006e2ee  jmp     loc_18006E3AB
0x18006e2f3  test    dil, 2
0x18006e2f7  jz      loc_18006E380
0x18006e2fd  test    r14d, r14d
0x18006e300  jnz     short loc_18006E380
0x18006e302  cmp     [rsi], edi
0x18006e304  jnz     loc_18006E3B6
0x18006e30a  test    byte ptr [r12], 1
0x18006e30f  jnz     loc_18006E442
0x18006e315  test    r13d, r13d
0x18006e318  jz      loc_18006E442
0x18006e31e  call    cs:__imp_GetCurrentThread
0x18006e324  mov     edx, 8; DesiredAccess
0x18006e329  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18006e32d  mov     rcx, rax; ThreadHandle
0x18006e330  lea     r8d, [rdx-7]; OpenAsSelf
0x18006e334  call    cs:__imp_OpenThreadToken
0x18006e33a  test    eax, eax
0x18006e33c  jnz     loc_18006E3CE
0x18006e342  lea     rax, WPP_GLOBAL_Control
0x18006e349  cmp     cs:WPP_GLOBAL_Control, rax
0x18006e350  jz      loc_18006E440
0x18006e356  call    cs:__imp_GetLastError
0x18006e35c  mov     edx, 13h
0x18006e361  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e368  lea     r8, WPP_9b7471db29383f688da4f00fe4f52bf0_Traceguids
0x18006e36f  mov     r9d, eax
0x18006e372  mov     rcx, [rcx+10h]
0x18006e376  call    WPP_SF_d
0x18006e37b  jmp     loc_18006E440
0x18006e380  cmp     [rsi], edi
0x18006e382  jnz     short loc_18006E3B6
0x18006e384  cmp     dword ptr [rbx+8], 0
0x18006e388  jz      short loc_18006E3B6
0x18006e38a  mov     rdx, [r15+238h]
0x18006e391  test    rdx, rdx
0x18006e394  jz      short loc_18006E3B6
0x18006e396  mov     r8d, [rbx+8]; Size
0x18006e39a  lea     rcx, [rbx+0Ch]; Buf1
0x18006e39e  add     rdx, 14h; Buf2
0x18006e3a2  call    memcmp_0
0x18006e3a7  test    eax, eax
0x18006e3a9  jnz     short loc_18006E3B6
0x18006e3ab  cmp     qword ptr [rbx+38h], 0
0x18006e3b0  jnz     loc_18006E30A
0x18006e3b6  mov     rbx, [rbx]
0x18006e3b9  test    rbx, rbx
0x18006e3bc  jz      loc_18006E442
0x18006e3c2  lea     r14, WPP_GLOBAL_Control
0x18006e3c9  jmp     loc_18006E288
0x18006e3ce  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18006e3d2  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18006e3d6  xorps   xmm0, xmm0
0x18006e3d9  xor     eax, eax
0x18006e3db  mov     r9d, 38h ; '8'; TokenInformationLength
0x18006e3e1  mov     [rbp+57h+var_50], rax
0x18006e3e5  lea     rax, [rbp+57h+var_8C]
0x18006e3e9  movups  [rbp+57h+TokenInformation], xmm0
0x18006e3ed  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x18006e3f2  lea     edx, [r9-2Eh]; TokenInformationClass
0x18006e3f6  movups  [rbp+57h+var_70], xmm0
0x18006e3fa  movups  [rbp+57h+var_60], xmm0
0x18006e3fe  call    cs:__imp_GetTokenInformation
0x18006e404  test    eax, eax
0x18006e406  jnz     short loc_18006E428
0x18006e408  lea     rax, WPP_GLOBAL_Control
0x18006e40f  cmp     cs:WPP_GLOBAL_Control, rax
0x18006e416  jz      short loc_18006E440
0x18006e418  call    cs:__imp_GetLastError
0x18006e41e  mov     edx, 14h
0x18006e423  jmp     loc_18006E361
0x18006e428  mov     eax, [rbx+50h]
0x18006e42b  cmp     dword ptr [rbp+57h+TokenInformation+8], eax
0x18006e42e  jnz     short loc_18006E438
0x18006e430  mov     eax, [rbx+54h]
0x18006e433  cmp     dword ptr [rbp+57h+TokenInformation+0Ch], eax
0x18006e436  jz      short loc_18006E442
0x18006e438  mov     rcx, rbx; hMem
0x18006e43b  call    ?RemoveNodeFromCachedCredList@@YAKPEAU_EAPTLS_CACHED_CREDS@@@Z; RemoveNodeFromCachedCredList(_EAPTLS_CACHED_CREDS *)
0x18006e440  xor     ebx, ebx
0x18006e442  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18006e446  test    rcx, rcx
0x18006e449  jz      short loc_18006E451
0x18006e44b  call    cs:__imp_CloseHandle
0x18006e451  mov     rax, rbx
0x18006e454  mov     rcx, [rbp+57h+var_48]
0x18006e458  xor     rcx, rsp; StackCookie
0x18006e45b  call    __security_check_cookie
0x18006e460  add     rsp, 88h
0x18006e467  pop     r15
0x18006e469  pop     r14
0x18006e46b  pop     r13
0x18006e46d  pop     r12
0x18006e46f  pop     rdi
0x18006e470  pop     rsi
0x18006e471  pop     rbx
0x18006e472  pop     rbp
0x18006e473  retn
```
