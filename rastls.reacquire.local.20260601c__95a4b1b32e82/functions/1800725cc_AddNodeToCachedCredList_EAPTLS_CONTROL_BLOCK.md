# AddNodeToCachedCredList(_EAPTLS_CONTROL_BLOCK *)

- ea: `0x1800725cc`
- end: `0x180072a47`
- name: `?AddNodeToCachedCredList@@YAKPEAU_EAPTLS_CONTROL_BLOCK@@@Z`
- size: `1147`
- prototype: `unsigned int __fastcall(struct _EAPTLS_CONTROL_BLOCK *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180072e98`

## callees

- `0x180005010`
- `0x180007d00`
- `0x18002706c`
- `0x1800356f4`
- `0x180038270`
- `0x1800725cc`
- `0x180072a50`
- `0x180072e04`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18007298c`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18007298c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800726fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072776`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800726fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072776`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800726ee`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800726ee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800726d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800726d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180072a0f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180072a0f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180072766`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180072766`
- `rtutils!TraceDumpExA` at `0x1800729d4`
- `rtutils!TraceDumpExA` at `0x1800729d4`

## pseudocode

```c
__int64 __fastcall AddNodeToCachedCredList(struct _EAPTLS_CONTROL_BLOCK *a1)
{
  unsigned int NewCachedCredListNode; // r14d
  unsigned int *v3; // rsi
  struct _EAPTLS_CONTROL_BLOCK *v4; // rcx
  unsigned int v5; // r8d
  __int64 v6; // rdx
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  struct _EAPTLS_CONTROL_BLOCK *v9; // rcx
  __int64 v10; // rdx
  struct _EAPTLS_CACHED_CREDS *v11; // rbx
  int v12; // eax
  int v13; // ecx
  int v14; // ecx
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  HLOCAL v18; // rax
  PDWORD ReturnLength; // [rsp+20h] [rbp-49h]
  DWORD v21; // [rsp+40h] [rbp-29h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-21h] BYREF
  struct _EAPTLS_CACHED_CREDS *NodeInCachedCredList; // [rsp+50h] [rbp-19h] BYREF
  _BYTE TokenInformation[56]; // [rsp+58h] [rbp-11h] BYREF

  NewCachedCredListNode = 0;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  v21 = 0;
  TokenHandle = 0;
  v3 = (unsigned int *)((char *)a1 + 4);
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_9b7471db29383f688da4f00fe4f52bf0_Traceguids, *v3);
    v4 = WPP_GLOBAL_Control;
  }
  v5 = *v3;
  if ( (*v3 & 4) != 0 )
  {
    if ( v4 == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_58;
    v6 = 22;
LABEL_57:
    WPP_SF_(*((_QWORD *)v4 + 2), v6, &WPP_9b7471db29383f688da4f00fe4f52bf0_Traceguids);
    goto LABEL_58;
  }
  if ( (v5 & 0x400000) != 0 )
  {
    if ( v4 == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_58;
    v6 = 23;
    goto LABEL_57;
  }
  NodeInCachedCredList = FindNodeInCachedCredList(a1, 0, ((v5 >> 10) & 1) == 0);
  if ( NodeInCachedCredList )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_58;
    v6 = 24;
    goto LABEL_57;
  }
  if ( (*v3 & 0x401) == 0 )
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    {
      LastError = GetLastError();
      NewCachedCredListNode = LastError;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        goto LABEL_58;
      v10 = 25;
      goto LABEL_16;
    }
    memset(TokenInformation, 0, sizeof(TokenInformation));
    if ( !GetTokenInformation(TokenHandle, TokenStatistics, TokenInformation, 0x38u, &v21) )
    {
      LastError = GetLastError();
      NewCachedCredListNode = LastError;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        goto LABEL_58;
      v10 = 26;
LABEL_16:
      WPP_SF_d(*((_QWORD *)v9 + 2), v10, &WPP_9b7471db29383f688da4f00fe4f52bf0_Traceguids, LastError);
      goto LABEL_58;
    }
  }
  NewCachedCredListNode = GetNewCachedCredListNode(&NodeInCachedCredList);
  if ( NewCachedCredListNode || (v11 = NodeInCachedCredList) == 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_58;
    v6 = 27;
    goto LABEL_57;
  }
  *((_DWORD *)NodeInCachedCredList + 8) |= 16 * (*((_DWORD *)a1 + 1) & 1);
  v12 = *((_DWORD *)v11 + 8) | (*v3 >> 9) & 8;
  *((_DWORD *)v11 + 8) = v12;
  v13 = v12 | (*v3 >> 10) & 0x20;
  *((_DWORD *)v11 + 8) = v13;
  if ( (*v3 & 0x400) != 0 )
  {
    v13 |= 0x40u;
    *((_DWORD *)v11 + 8) = v13;
  }
  if ( (*v3 & 0x4000) != 0 )
  {
    v14 = v13 | 2;
    *((_DWORD *)v11 + 8) = v14;
    if ( (*v3 & 0x401) != 0 )
      goto LABEL_35;
    v15 = *((_QWORD *)a1 + 68);
    if ( !v15 )
      goto LABEL_35;
    if ( (*(_BYTE *)(v15 + 8) & 0x20) != 0 )
    {
      v14 |= 0x100u;
    }
    else
    {
      if ( (*(_DWORD *)(v15 + 8) & 0x200) == 0 )
        goto LABEL_35;
      v14 |= 0x200u;
    }
  }
  else if ( (*v3 & 0x10000) != 0 )
  {
    v14 = v13 | 4;
  }
  else
  {
    v14 = v13 | 1;
  }
  *((_DWORD *)v11 + 8) = v14;
LABEL_35:
  if ( (*(_BYTE *)v3 & 1) == 0 )
  {
    v16 = *((_QWORD *)a1 + 68);
    if ( v16 )
    {
      if ( (*(_BYTE *)(v16 + 8) & 1) == 0 )
        *((_DWORD *)v11 + 8) = v14 | 0x80;
    }
  }
  if ( (*v3 & 0x800000) != 0 )
  {
    *((_DWORD *)v11 + 152) = 1;
    *((_DWORD *)v11 + 153) = *((_DWORD *)a1 + 206);
    *((_QWORD *)v11 + 77) = *((_QWORD *)a1 + 104);
  }
  else
  {
    *((_DWORD *)v11 + 152) = 0;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EapServerTls13>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EapServerTls13>::GetImpl'::`2'::impl) )
    *((_DWORD *)v11 + 8) |= *((_DWORD *)a1 + 158) != 0 ? 0x400 : 0;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      28,
      &WPP_9b7471db29383f688da4f00fe4f52bf0_Traceguids,
      *((unsigned int *)v11 + 8));
  v17 = *((_QWORD *)a1 + 71);
  *(_OWORD *)((char *)v11 + 8) = *(_OWORD *)(v17 + 16);
  *((_QWORD *)v11 + 3) = *(_QWORD *)(v17 + 32);
  *(_OWORD *)((char *)v11 + 40) = *(_OWORD *)((char *)a1 + 616);
  *((_QWORD *)v11 + 7) = *((_QWORD *)a1 + 74);
  *((_QWORD *)v11 + 8) = *((_QWORD *)a1 + 75);
  *((_DWORD *)v11 + 18) = *((_DWORD *)a1 + 152);
  *((_DWORD *)v11 + 19) = *((_DWORD *)a1 + 153);
  *((_DWORD *)v11 + 22) = *((_DWORD *)a1 + 193);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EapServerTls13>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EapServerTls13>::GetImpl'::`2'::impl) )
  {
    if ( (*(_BYTE *)v3 & 1) != 0 )
      winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil::operator=((struct _EAPTLS_CACHED_CREDS *)((char *)v11 + 632));
    else
      winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil::operator=((struct _EAPTLS_CACHED_CREDS *)((char *)v11 + 624));
  }
  if ( (*(_BYTE *)v3 & 1) == 0 )
    *((_QWORD *)v11 + 10) = *(_QWORD *)&TokenInformation[8];
  _o_wcsncpy_s((char *)v11 + 92, 257, (char *)a1 + 16, 256, ReturnLength);
  v18 = g_pCachedCreds;
  g_pCachedCreds = v11;
  if ( v18 )
    *(_QWORD *)v11 = v18;
  TraceDumpExA(g_dwEapTlsTraceId, 0x10006u, (LPBYTE)v11 + 12, *((_DWORD *)v11 + 2), 1u, 1, 0);
LABEL_58:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return NewCachedCredListNode;
}

```

## disassembly

```asm
0x1800725cc  mov     [rsp-8+arg_8], rbx
0x1800725d1  mov     [rsp-8+arg_10], rsi
0x1800725d6  push    rbp
0x1800725d7  push    rdi
0x1800725d8  push    r12
0x1800725da  push    r13
0x1800725dc  push    r14
0x1800725de  lea     rbp, [rsp-37h]
0x1800725e3  sub     rsp, 0A0h
0x1800725ea  mov     rax, cs:__security_cookie
0x1800725f1  xor     rax, rsp
0x1800725f4  mov     [rbp+57h+var_30], rax
0x1800725f8  xorps   xmm0, xmm0
0x1800725fb  xor     r14d, r14d
0x1800725fe  xor     eax, eax
0x180072600  mov     dword ptr [rbp+57h+TokenInformation], r14d
0x180072604  mov     [rbp+57h+var_34], eax
0x180072607  mov     rdi, rcx
0x18007260a  mov     [rbp+57h+var_80], eax
0x18007260d  mov     [rbp+57h+TokenHandle], rax
0x180072611  movups  [rbp+57h+TokenInformation+4], xmm0
0x180072615  movups  [rbp+57h+var_54], xmm0
0x180072619  movups  [rbp+57h+var_44], xmm0
0x18007261d  lea     rsi, [rcx+4]
0x180072621  mov     rcx, cs:WPP_GLOBAL_Control
0x180072628  lea     r13, WPP_GLOBAL_Control
0x18007262f  lea     rbx, WPP_9b7471db29383f688da4f00fe4f52bf0_Traceguids
0x180072636  cmp     rcx, r13
0x180072639  jz      short loc_180072654
0x18007263b  mov     r9d, [rsi]
0x18007263e  lea     edx, [rax+15h]
0x180072641  mov     rcx, [rcx+10h]
0x180072645  mov     r8, rbx
0x180072648  call    WPP_SF_d
0x18007264d  mov     rcx, cs:WPP_GLOBAL_Control
0x180072654  mov     r8d, [rsi]
0x180072657  test    r8b, 4
0x18007265b  jz      short loc_180072670
0x18007265d  cmp     rcx, r13
0x180072660  jz      loc_180072A06
0x180072666  mov     edx, 16h
0x18007266b  jmp     loc_1800729FA
0x180072670  bt      r8d, 16h
0x180072675  jnb     short loc_18007268A
0x180072677  cmp     rcx, r13
0x18007267a  jz      loc_180072A06
0x180072680  mov     edx, 17h
0x180072685  jmp     loc_1800729FA
0x18007268a  shr     r8d, 0Ah
0x18007268e  mov     r12d, 1
0x180072694  not     r8d
0x180072697  xor     edx, edx; int
0x180072699  and     r8d, r12d; int
0x18007269c  mov     rcx, rdi; struct _EAPTLS_CONTROL_BLOCK *
0x18007269f  call    ?FindNodeInCachedCredList@@YAPEAU_EAPTLS_CACHED_CREDS@@PEAU_EAPTLS_CONTROL_BLOCK@@HH@Z; FindNodeInCachedCredList(_EAPTLS_CONTROL_BLOCK *,int,int)
0x1800726a4  mov     [rbp+57h+var_70], rax
0x1800726a8  test    rax, rax
0x1800726ab  jz      short loc_1800726C7
0x1800726ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800726b4  cmp     rcx, r13
0x1800726b7  jz      loc_180072A06
0x1800726bd  lea     edx, [r12+17h]
0x1800726c2  jmp     loc_1800729FA
0x1800726c7  test    dword ptr [rsi], 401h
0x1800726cd  jnz     loc_18007279C
0x1800726d3  call    cs:__imp_GetCurrentThread
0x1800726da  nop     dword ptr [rax+rax+00h]
0x1800726df  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1800726e3  mov     r8d, r12d; OpenAsSelf
0x1800726e6  mov     rcx, rax; ThreadHandle
0x1800726e9  mov     edx, 8; DesiredAccess
0x1800726ee  call    cs:__imp_OpenThreadToken
0x1800726f5  nop     dword ptr [rax+rax+00h]
0x1800726fa  test    eax, eax
0x1800726fc  jnz     short loc_180072736
0x1800726fe  call    cs:__imp_GetLastError
0x180072705  nop     dword ptr [rax+rax+00h]
0x18007270a  mov     r14d, eax
0x18007270d  mov     rcx, cs:WPP_GLOBAL_Control
0x180072714  cmp     rcx, r13
0x180072717  jz      loc_180072A06
0x18007271d  mov     edx, 19h
0x180072722  mov     rcx, [rcx+10h]
0x180072726  mov     r9d, eax
0x180072729  mov     r8, rbx
0x18007272c  call    WPP_SF_d
0x180072731  jmp     loc_180072A06
0x180072736  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18007273a  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18007273e  xorps   xmm0, xmm0
0x180072741  xor     eax, eax
0x180072743  mov     r9d, 38h ; '8'; TokenInformationLength
0x180072749  mov     qword ptr [rbp+57h+var_44+0Ch], rax
0x18007274d  lea     rax, [rbp+57h+var_80]
0x180072751  movups  [rbp+57h+TokenInformation], xmm0
0x180072755  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x18007275a  lea     edx, [r9-2Eh]; TokenInformationClass
0x18007275e  movups  xmmword ptr [rbp-1], xmm0
0x180072762  movups  [rbp+57h+var_54+0Ch], xmm0
0x180072766  call    cs:__imp_GetTokenInformation
0x18007276d  nop     dword ptr [rax+rax+00h]
0x180072772  test    eax, eax
0x180072774  jnz     short loc_18007279C
0x180072776  call    cs:__imp_GetLastError
0x18007277d  nop     dword ptr [rax+rax+00h]
0x180072782  mov     r14d, eax
0x180072785  mov     rcx, cs:WPP_GLOBAL_Control
0x18007278c  cmp     rcx, r13
0x18007278f  jz      loc_180072A06
0x180072795  mov     edx, 1Ah
0x18007279a  jmp     short loc_180072722
0x18007279c  lea     rcx, [rbp+57h+var_70]; struct _EAPTLS_CACHED_CREDS **
0x1800727a0  call    ?GetNewCachedCredListNode@@YAKPEAPEAU_EAPTLS_CACHED_CREDS@@@Z; GetNewCachedCredListNode(_EAPTLS_CACHED_CREDS * *)
0x1800727a5  mov     r14d, eax
0x1800727a8  test    eax, eax
0x1800727aa  jnz     loc_1800729E9
0x1800727b0  mov     rbx, [rbp+57h+var_70]
0x1800727b4  test    rbx, rbx
0x1800727b7  jz      loc_1800729E2
0x1800727bd  mov     eax, [rdi+4]
0x1800727c0  and     eax, r12d
0x1800727c3  shl     eax, 4
0x1800727c6  or      [rbx+20h], eax
0x1800727c9  mov     eax, [rsi]
0x1800727cb  shr     eax, 9
0x1800727ce  and     eax, 8
0x1800727d1  or      eax, [rbx+20h]
0x1800727d4  mov     [rbx+20h], eax
0x1800727d7  mov     ecx, [rsi]
0x1800727d9  shr     ecx, 0Ah
0x1800727dc  and     ecx, 20h
0x1800727df  or      ecx, eax
0x1800727e1  mov     [rbx+20h], ecx
0x1800727e4  test    dword ptr [rsi], 400h
0x1800727ea  jz      short loc_1800727F2
0x1800727ec  or      ecx, 40h
0x1800727ef  mov     [rbx+20h], ecx
0x1800727f2  test    dword ptr [rsi], 4000h
0x1800727f8  jz      short loc_18007282E
0x1800727fa  or      ecx, 2
0x1800727fd  mov     [rbx+20h], ecx
0x180072800  test    dword ptr [rsi], 401h
0x180072806  jnz     short loc_180072841
0x180072808  mov     rax, [rdi+220h]
0x18007280f  test    rax, rax
0x180072812  jz      short loc_180072841
0x180072814  test    byte ptr [rax+8], 20h
0x180072818  jz      short loc_180072820
0x18007281a  bts     ecx, 8
0x18007281e  jmp     short loc_18007283E
0x180072820  mov     edx, 200h
0x180072825  test    [rax+8], edx
0x180072828  jz      short loc_180072841
0x18007282a  or      ecx, edx
0x18007282c  jmp     short loc_18007283E
0x18007282e  test    dword ptr [rsi], 10000h
0x180072834  jz      short loc_18007283B
0x180072836  or      ecx, 4
0x180072839  jmp     short loc_18007283E
0x18007283b  or      ecx, r12d
0x18007283e  mov     [rbx+20h], ecx
0x180072841  test    [rsi], r12b
0x180072844  jnz     short loc_18007285F
0x180072846  mov     rax, [rdi+220h]
0x18007284d  test    rax, rax
0x180072850  jz      short loc_18007285F
0x180072852  test    [rax+8], r12b
0x180072856  jnz     short loc_18007285F
0x180072858  bts     ecx, 7
0x18007285c  mov     [rbx+20h], ecx
0x18007285f  test    dword ptr [rsi], 800000h
0x180072865  jz      short loc_18007288A
0x180072867  mov     [rbx+260h], r12d
0x18007286e  mov     eax, [rdi+338h]
0x180072874  mov     [rbx+264h], eax
0x18007287a  mov     rax, [rdi+340h]
0x180072881  mov     [rbx+268h], rax
0x180072888  jmp     short loc_180072894
0x18007288a  mov     dword ptr [rbx+260h], 0
0x180072894  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EapServerTls13@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EapServerTls13@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EapServerTls13> `wil::Feature<__WilFeatureTraits_Feature_EapServerTls13>::GetImpl(void)'::`2'::impl
0x18007289b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EapServerTls13@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EapServerTls13>::__private_IsEnabled(void)
0x1800728a0  test    al, al
0x1800728a2  jz      short loc_1800728B6
0x1800728a4  xor     eax, eax
0x1800728a6  cmp     eax, [rdi+278h]
0x1800728ac  sbb     eax, eax
0x1800728ae  and     eax, 400h
0x1800728b3  or      [rbx+20h], eax
0x1800728b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800728bd  cmp     rcx, r13
0x1800728c0  jz      short loc_1800728DB
0x1800728c2  mov     r9d, [rbx+20h]
0x1800728c6  lea     r8, WPP_9b7471db29383f688da4f00fe4f52bf0_Traceguids
0x1800728cd  mov     rcx, [rcx+10h]
0x1800728d1  mov     edx, 1Ch
0x1800728d6  call    WPP_SF_d
0x1800728db  mov     rax, [rdi+238h]
0x1800728e2  movups  xmm0, xmmword ptr [rax+10h]
0x1800728e6  movups  xmmword ptr [rbx+8], xmm0
0x1800728ea  movsd   xmm1, qword ptr [rax+20h]
0x1800728ef  movsd   qword ptr [rbx+18h], xmm1
0x1800728f4  movups  xmm0, xmmword ptr [rdi+268h]
0x1800728fb  movdqu  xmmword ptr [rbx+28h], xmm0
0x180072900  mov     rax, [rdi+250h]
0x180072907  mov     [rbx+38h], rax
0x18007290b  mov     rax, [rdi+258h]
0x180072912  mov     [rbx+40h], rax
0x180072916  mov     eax, [rdi+260h]
0x18007291c  mov     [rbx+48h], eax
0x18007291f  mov     eax, [rdi+264h]
0x180072925  mov     [rbx+4Ch], eax
0x180072928  mov     eax, [rdi+304h]
0x18007292e  mov     [rbx+58h], eax
0x180072931  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EapServerTls13@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EapServerTls13@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EapServerTls13> `wil::Feature<__WilFeatureTraits_Feature_EapServerTls13>::GetImpl(void)'::`2'::impl
0x180072938  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EapServerTls13@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EapServerTls13>::__private_IsEnabled(void)
0x18007293d  test    al, al
0x18007293f  jz      short loc_18007296E
0x180072941  test    [rsi], r12b
0x180072944  jz      short loc_18007295B
0x180072946  lea     rdx, [rdi+360h]
0x18007294d  lea     rcx, [rbx+278h]; this
0x180072954  call    ??4EapServerSchannelUtil@Utility@Eap@Internal@Windows@winrt@@QEAAAEAU012345@AEBU012345@@Z; winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil::operator=(winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil const &)
0x180072959  jmp     short loc_18007296E
0x18007295b  lea     rdx, [rdi+358h]
0x180072962  lea     rcx, [rbx+270h]; this
0x180072969  call    ??4EapServerSchannelUtil@Utility@Eap@Internal@Windows@winrt@@QEAAAEAU012345@AEBU012345@@Z; winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil::operator=(winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil const &)
0x18007296e  test    [rsi], r12b
0x180072971  jnz     short loc_18007297B
0x180072973  mov     rax, qword ptr [rbp+57h+TokenInformation+8]
0x180072977  mov     [rbx+50h], rax
0x18007297b  mov     edx, 101h
0x180072980  lea     r8, [rdi+10h]
0x180072984  lea     rcx, [rbx+5Ch]
0x180072988  lea     r9d, [rdx-1]
0x18007298c  call    cs:__imp__o_wcsncpy_s
0x180072993  nop     dword ptr [rax+rax+00h]
0x180072998  mov     rax, cs:?g_pCachedCreds@@3PEAU_EAPTLS_CACHED_CREDS@@EA; _EAPTLS_CACHED_CREDS * g_pCachedCreds
0x18007299f  mov     cs:?g_pCachedCreds@@3PEAU_EAPTLS_CACHED_CREDS@@EA, rbx; _EAPTLS_CACHED_CREDS * g_pCachedCreds
0x1800729a6  test    rax, rax
0x1800729a9  jz      short loc_1800729AE
0x1800729ab  mov     [rbx], rax
0x1800729ae  mov     r9d, [rbx+8]; dwByteCount
0x1800729b2  lea     r8, [rbx+0Ch]; lpbBytes
0x1800729b6  mov     ecx, cs:?g_dwEapTlsTraceId@@3KA; dwTraceID
0x1800729bc  mov     edx, 10006h; dwFlags
0x1800729c1  mov     [rsp+0C0h+lpszPrefix], 0; lpszPrefix
0x1800729ca  mov     [rsp+0C0h+bAddressPrefix], r12d; bAddressPrefix
0x1800729cf  mov     dword ptr [rsp+0C0h+ReturnLength], r12d; dwGroupSize
0x1800729d4  call    cs:__imp_TraceDumpExA
0x1800729db  nop     dword ptr [rax+rax+00h]
0x1800729e0  jmp     short loc_180072A06
0x1800729e2  lea     rbx, WPP_9b7471db29383f688da4f00fe4f52bf0_Traceguids
0x1800729e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800729f0  cmp     rcx, r13
0x1800729f3  jz      short loc_180072A06
0x1800729f5  mov     edx, 1Bh
0x1800729fa  mov     rcx, [rcx+10h]
0x1800729fe  mov     r8, rbx
0x180072a01  call    WPP_SF_
0x180072a06  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180072a0a  test    rcx, rcx
0x180072a0d  jz      short loc_180072A1B
0x180072a0f  call    cs:__imp_CloseHandle
0x180072a16  nop     dword ptr [rax+rax+00h]
0x180072a1b  mov     eax, r14d
0x180072a1e  mov     rcx, [rbp+57h+var_30]
0x180072a22  xor     rcx, rsp; StackCookie
0x180072a25  call    __security_check_cookie
0x180072a2a  lea     r11, [rsp+0C0h+var_20]
0x180072a32  mov     rbx, [r11+38h]
0x180072a36  mov     rsi, [r11+40h]
0x180072a3a  mov     rsp, r11
0x180072a3d  pop     r14
0x180072a3f  pop     r13
0x180072a41  pop     r12
0x180072a43  pop     rdi
0x180072a44  pop     rbp
0x180072a45  retn
```
