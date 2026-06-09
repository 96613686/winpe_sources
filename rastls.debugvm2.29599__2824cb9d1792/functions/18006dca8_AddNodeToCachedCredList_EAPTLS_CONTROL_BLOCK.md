# AddNodeToCachedCredList(_EAPTLS_CONTROL_BLOCK *)

- ea: `0x18006dca8`
- end: `0x18006e0f2`
- name: `?AddNodeToCachedCredList@@YAKPEAU_EAPTLS_CONTROL_BLOCK@@@Z`
- size: `1098`
- prototype: `unsigned int __fastcall(struct _EAPTLS_CONTROL_BLOCK *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006e508`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x18002550c`
- `0x180032acc`
- `0x180035680`
- `0x18006dca8`
- `0x18006e0f8`
- `0x18006e47c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18006e04a`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18006e04a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ddce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006de3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ddce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006de3a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006ddc4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006ddc4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006ddaf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006ddaf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006e0c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006e0c1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006de30`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006de30`
- `rtutils!TraceDumpExA` at `0x18006e08c`
- `rtutils!TraceDumpExA` at `0x18006e08c`

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
  DWORD ReturnLength; // [rsp+40h] [rbp-29h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-21h] BYREF
  struct _EAPTLS_CACHED_CREDS *NodeInCachedCredList; // [rsp+50h] [rbp-19h] BYREF
  _BYTE TokenInformation[56]; // [rsp+58h] [rbp-11h] BYREF

  NewCachedCredListNode = 0;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  ReturnLength = 0;
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
    if ( !GetTokenInformation(TokenHandle, TokenStatistics, TokenInformation, 0x38u, &ReturnLength) )
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
  _o_wcsncpy_s((char *)v11 + 92, 257, (char *)a1 + 16, 256);
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
0x18006dca8  mov     [rsp-8+arg_8], rbx
0x18006dcad  mov     [rsp-8+arg_10], rsi
0x18006dcb2  push    rbp
0x18006dcb3  push    rdi
0x18006dcb4  push    r12
0x18006dcb6  push    r13
0x18006dcb8  push    r14
0x18006dcba  lea     rbp, [rsp-37h]
0x18006dcbf  sub     rsp, 0A0h
0x18006dcc6  mov     rax, cs:__security_cookie
0x18006dccd  xor     rax, rsp
0x18006dcd0  mov     [rbp+57h+var_30], rax
0x18006dcd4  xorps   xmm0, xmm0
0x18006dcd7  xor     r14d, r14d
0x18006dcda  xor     eax, eax
0x18006dcdc  mov     dword ptr [rbp+57h+TokenInformation], r14d
0x18006dce0  mov     [rbp+57h+var_34], eax
0x18006dce3  mov     rdi, rcx
0x18006dce6  mov     [rbp+57h+var_80], eax
0x18006dce9  mov     [rbp+57h+TokenHandle], rax
0x18006dced  movups  [rbp+57h+TokenInformation+4], xmm0
0x18006dcf1  movups  [rbp+57h+var_54], xmm0
0x18006dcf5  movups  [rbp+57h+var_44], xmm0
0x18006dcf9  lea     rsi, [rcx+4]
0x18006dcfd  mov     rcx, cs:WPP_GLOBAL_Control
0x18006dd04  lea     r13, WPP_GLOBAL_Control
0x18006dd0b  lea     rbx, WPP_9b7471db29383f688da4f00fe4f52bf0_Traceguids
0x18006dd12  cmp     rcx, r13
0x18006dd15  jz      short loc_18006DD30
0x18006dd17  mov     r9d, [rsi]
0x18006dd1a  lea     edx, [rax+15h]
0x18006dd1d  mov     rcx, [rcx+10h]
0x18006dd21  mov     r8, rbx
0x18006dd24  call    WPP_SF_d
0x18006dd29  mov     rcx, cs:WPP_GLOBAL_Control
0x18006dd30  mov     r8d, [rsi]
0x18006dd33  test    r8b, 4
0x18006dd37  jz      short loc_18006DD4C
0x18006dd39  cmp     rcx, r13
0x18006dd3c  jz      loc_18006E0B8
0x18006dd42  mov     edx, 16h
0x18006dd47  jmp     loc_18006E0AC
0x18006dd4c  bt      r8d, 16h
0x18006dd51  jnb     short loc_18006DD66
0x18006dd53  cmp     rcx, r13
0x18006dd56  jz      loc_18006E0B8
0x18006dd5c  mov     edx, 17h
0x18006dd61  jmp     loc_18006E0AC
0x18006dd66  shr     r8d, 0Ah
0x18006dd6a  mov     r12d, 1
0x18006dd70  not     r8d
0x18006dd73  xor     edx, edx; int
0x18006dd75  and     r8d, r12d; int
0x18006dd78  mov     rcx, rdi; struct _EAPTLS_CONTROL_BLOCK *
0x18006dd7b  call    ?FindNodeInCachedCredList@@YAPEAU_EAPTLS_CACHED_CREDS@@PEAU_EAPTLS_CONTROL_BLOCK@@HH@Z; FindNodeInCachedCredList(_EAPTLS_CONTROL_BLOCK *,int,int)
0x18006dd80  mov     [rbp+57h+var_70], rax
0x18006dd84  test    rax, rax
0x18006dd87  jz      short loc_18006DDA3
0x18006dd89  mov     rcx, cs:WPP_GLOBAL_Control
0x18006dd90  cmp     rcx, r13
0x18006dd93  jz      loc_18006E0B8
0x18006dd99  lea     edx, [r12+17h]
0x18006dd9e  jmp     loc_18006E0AC
0x18006dda3  test    dword ptr [rsi], 401h
0x18006dda9  jnz     loc_18006DE5A
0x18006ddaf  call    cs:__imp_GetCurrentThread
0x18006ddb5  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18006ddb9  mov     r8d, r12d; OpenAsSelf
0x18006ddbc  mov     rcx, rax; ThreadHandle
0x18006ddbf  mov     edx, 8; DesiredAccess
0x18006ddc4  call    cs:__imp_OpenThreadToken
0x18006ddca  test    eax, eax
0x18006ddcc  jnz     short loc_18006DE00
0x18006ddce  call    cs:__imp_GetLastError
0x18006ddd4  mov     r14d, eax
0x18006ddd7  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ddde  cmp     rcx, r13
0x18006dde1  jz      loc_18006E0B8
0x18006dde7  mov     edx, 19h
0x18006ddec  mov     rcx, [rcx+10h]
0x18006ddf0  mov     r9d, eax
0x18006ddf3  mov     r8, rbx
0x18006ddf6  call    WPP_SF_d
0x18006ddfb  jmp     loc_18006E0B8
0x18006de00  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18006de04  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18006de08  xorps   xmm0, xmm0
0x18006de0b  xor     eax, eax
0x18006de0d  mov     r9d, 38h ; '8'; TokenInformationLength
0x18006de13  mov     qword ptr [rbp+57h+var_44+0Ch], rax
0x18006de17  lea     rax, [rbp+57h+var_80]
0x18006de1b  movups  [rbp+57h+TokenInformation], xmm0
0x18006de1f  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x18006de24  lea     edx, [r9-2Eh]; TokenInformationClass
0x18006de28  movups  xmmword ptr [rbp-1], xmm0
0x18006de2c  movups  [rbp+57h+var_54+0Ch], xmm0
0x18006de30  call    cs:__imp_GetTokenInformation
0x18006de36  test    eax, eax
0x18006de38  jnz     short loc_18006DE5A
0x18006de3a  call    cs:__imp_GetLastError
0x18006de40  mov     r14d, eax
0x18006de43  mov     rcx, cs:WPP_GLOBAL_Control
0x18006de4a  cmp     rcx, r13
0x18006de4d  jz      loc_18006E0B8
0x18006de53  mov     edx, 1Ah
0x18006de58  jmp     short loc_18006DDEC
0x18006de5a  lea     rcx, [rbp+57h+var_70]; struct _EAPTLS_CACHED_CREDS **
0x18006de5e  call    ?GetNewCachedCredListNode@@YAKPEAPEAU_EAPTLS_CACHED_CREDS@@@Z; GetNewCachedCredListNode(_EAPTLS_CACHED_CREDS * *)
0x18006de63  mov     r14d, eax
0x18006de66  test    eax, eax
0x18006de68  jnz     loc_18006E09B
0x18006de6e  mov     rbx, [rbp+57h+var_70]
0x18006de72  test    rbx, rbx
0x18006de75  jz      loc_18006E094
0x18006de7b  mov     eax, [rdi+4]
0x18006de7e  and     eax, r12d
0x18006de81  shl     eax, 4
0x18006de84  or      [rbx+20h], eax
0x18006de87  mov     eax, [rsi]
0x18006de89  shr     eax, 9
0x18006de8c  and     eax, 8
0x18006de8f  or      eax, [rbx+20h]
0x18006de92  mov     [rbx+20h], eax
0x18006de95  mov     ecx, [rsi]
0x18006de97  shr     ecx, 0Ah
0x18006de9a  and     ecx, 20h
0x18006de9d  or      ecx, eax
0x18006de9f  mov     [rbx+20h], ecx
0x18006dea2  test    dword ptr [rsi], 400h
0x18006dea8  jz      short loc_18006DEB0
0x18006deaa  or      ecx, 40h
0x18006dead  mov     [rbx+20h], ecx
0x18006deb0  test    dword ptr [rsi], 4000h
0x18006deb6  jz      short loc_18006DEEC
0x18006deb8  or      ecx, 2
0x18006debb  mov     [rbx+20h], ecx
0x18006debe  test    dword ptr [rsi], 401h
0x18006dec4  jnz     short loc_18006DEFF
0x18006dec6  mov     rax, [rdi+220h]
0x18006decd  test    rax, rax
0x18006ded0  jz      short loc_18006DEFF
0x18006ded2  test    byte ptr [rax+8], 20h
0x18006ded6  jz      short loc_18006DEDE
0x18006ded8  bts     ecx, 8
0x18006dedc  jmp     short loc_18006DEFC
0x18006dede  mov     edx, 200h
0x18006dee3  test    [rax+8], edx
0x18006dee6  jz      short loc_18006DEFF
0x18006dee8  or      ecx, edx
0x18006deea  jmp     short loc_18006DEFC
0x18006deec  test    dword ptr [rsi], 10000h
0x18006def2  jz      short loc_18006DEF9
0x18006def4  or      ecx, 4
0x18006def7  jmp     short loc_18006DEFC
0x18006def9  or      ecx, r12d
0x18006defc  mov     [rbx+20h], ecx
0x18006deff  test    [rsi], r12b
0x18006df02  jnz     short loc_18006DF1D
0x18006df04  mov     rax, [rdi+220h]
0x18006df0b  test    rax, rax
0x18006df0e  jz      short loc_18006DF1D
0x18006df10  test    [rax+8], r12b
0x18006df14  jnz     short loc_18006DF1D
0x18006df16  bts     ecx, 7
0x18006df1a  mov     [rbx+20h], ecx
0x18006df1d  test    dword ptr [rsi], 800000h
0x18006df23  jz      short loc_18006DF48
0x18006df25  mov     [rbx+260h], r12d
0x18006df2c  mov     eax, [rdi+338h]
0x18006df32  mov     [rbx+264h], eax
0x18006df38  mov     rax, [rdi+340h]
0x18006df3f  mov     [rbx+268h], rax
0x18006df46  jmp     short loc_18006DF52
0x18006df48  mov     dword ptr [rbx+260h], 0
0x18006df52  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EapServerTls13@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EapServerTls13@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EapServerTls13> `wil::Feature<__WilFeatureTraits_Feature_EapServerTls13>::GetImpl(void)'::`2'::impl
0x18006df59  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EapServerTls13@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EapServerTls13>::__private_IsEnabled(void)
0x18006df5e  test    al, al
0x18006df60  jz      short loc_18006DF74
0x18006df62  xor     eax, eax
0x18006df64  cmp     eax, [rdi+278h]
0x18006df6a  sbb     eax, eax
0x18006df6c  and     eax, 400h
0x18006df71  or      [rbx+20h], eax
0x18006df74  mov     rcx, cs:WPP_GLOBAL_Control
0x18006df7b  cmp     rcx, r13
0x18006df7e  jz      short loc_18006DF99
0x18006df80  mov     r9d, [rbx+20h]
0x18006df84  lea     r8, WPP_9b7471db29383f688da4f00fe4f52bf0_Traceguids
0x18006df8b  mov     rcx, [rcx+10h]
0x18006df8f  mov     edx, 1Ch
0x18006df94  call    WPP_SF_d
0x18006df99  mov     rax, [rdi+238h]
0x18006dfa0  movups  xmm0, xmmword ptr [rax+10h]
0x18006dfa4  movups  xmmword ptr [rbx+8], xmm0
0x18006dfa8  movsd   xmm1, qword ptr [rax+20h]
0x18006dfad  movsd   qword ptr [rbx+18h], xmm1
0x18006dfb2  movups  xmm0, xmmword ptr [rdi+268h]
0x18006dfb9  movdqu  xmmword ptr [rbx+28h], xmm0
0x18006dfbe  mov     rax, [rdi+250h]
0x18006dfc5  mov     [rbx+38h], rax
0x18006dfc9  mov     rax, [rdi+258h]
0x18006dfd0  mov     [rbx+40h], rax
0x18006dfd4  mov     eax, [rdi+260h]
0x18006dfda  mov     [rbx+48h], eax
0x18006dfdd  mov     eax, [rdi+264h]
0x18006dfe3  mov     [rbx+4Ch], eax
0x18006dfe6  mov     eax, [rdi+304h]
0x18006dfec  mov     [rbx+58h], eax
0x18006dfef  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EapServerTls13@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EapServerTls13@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EapServerTls13> `wil::Feature<__WilFeatureTraits_Feature_EapServerTls13>::GetImpl(void)'::`2'::impl
0x18006dff6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EapServerTls13@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EapServerTls13>::__private_IsEnabled(void)
0x18006dffb  test    al, al
0x18006dffd  jz      short loc_18006E02C
0x18006dfff  test    [rsi], r12b
0x18006e002  jz      short loc_18006E019
0x18006e004  lea     rdx, [rdi+360h]
0x18006e00b  lea     rcx, [rbx+278h]; this
0x18006e012  call    ??4EapServerSchannelUtil@Utility@Eap@Internal@Windows@winrt@@QEAAAEAU012345@AEBU012345@@Z; winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil::operator=(winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil const &)
0x18006e017  jmp     short loc_18006E02C
0x18006e019  lea     rdx, [rdi+358h]
0x18006e020  lea     rcx, [rbx+270h]; this
0x18006e027  call    ??4EapServerSchannelUtil@Utility@Eap@Internal@Windows@winrt@@QEAAAEAU012345@AEBU012345@@Z; winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil::operator=(winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil const &)
0x18006e02c  test    [rsi], r12b
0x18006e02f  jnz     short loc_18006E039
0x18006e031  mov     rax, qword ptr [rbp+57h+TokenInformation+8]
0x18006e035  mov     [rbx+50h], rax
0x18006e039  mov     edx, 101h
0x18006e03e  lea     r8, [rdi+10h]
0x18006e042  lea     rcx, [rbx+5Ch]
0x18006e046  lea     r9d, [rdx-1]
0x18006e04a  call    cs:__imp__o_wcsncpy_s
0x18006e050  mov     rax, cs:?g_pCachedCreds@@3PEAU_EAPTLS_CACHED_CREDS@@EA; _EAPTLS_CACHED_CREDS * g_pCachedCreds
0x18006e057  mov     cs:?g_pCachedCreds@@3PEAU_EAPTLS_CACHED_CREDS@@EA, rbx; _EAPTLS_CACHED_CREDS * g_pCachedCreds
0x18006e05e  test    rax, rax
0x18006e061  jz      short loc_18006E066
0x18006e063  mov     [rbx], rax
0x18006e066  mov     r9d, [rbx+8]; dwByteCount
0x18006e06a  lea     r8, [rbx+0Ch]; lpbBytes
0x18006e06e  mov     ecx, cs:?g_dwEapTlsTraceId@@3KA; dwTraceID
0x18006e074  mov     edx, 10006h; dwFlags
0x18006e079  mov     [rsp+0C0h+lpszPrefix], 0; lpszPrefix
0x18006e082  mov     [rsp+0C0h+bAddressPrefix], r12d; bAddressPrefix
0x18006e087  mov     dword ptr [rsp+0C0h+ReturnLength], r12d; dwGroupSize
0x18006e08c  call    cs:__imp_TraceDumpExA
0x18006e092  jmp     short loc_18006E0B8
0x18006e094  lea     rbx, WPP_9b7471db29383f688da4f00fe4f52bf0_Traceguids
0x18006e09b  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e0a2  cmp     rcx, r13
0x18006e0a5  jz      short loc_18006E0B8
0x18006e0a7  mov     edx, 1Bh
0x18006e0ac  mov     rcx, [rcx+10h]
0x18006e0b0  mov     r8, rbx
0x18006e0b3  call    WPP_SF_
0x18006e0b8  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18006e0bc  test    rcx, rcx
0x18006e0bf  jz      short loc_18006E0C7
0x18006e0c1  call    cs:__imp_CloseHandle
0x18006e0c7  mov     eax, r14d
0x18006e0ca  mov     rcx, [rbp+57h+var_30]
0x18006e0ce  xor     rcx, rsp; StackCookie
0x18006e0d1  call    __security_check_cookie
0x18006e0d6  lea     r11, [rsp+0C0h+var_20]
0x18006e0de  mov     rbx, [r11+38h]
0x18006e0e2  mov     rsi, [r11+40h]
0x18006e0e6  mov     rsp, r11
0x18006e0e9  pop     r14
0x18006e0eb  pop     r13
0x18006e0ed  pop     r12
0x18006e0ef  pop     rdi
0x18006e0f0  pop     rbp
0x18006e0f1  retn
```
