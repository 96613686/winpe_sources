# CuiGetTokenForApp(HINSTANCE__ *,_CONSENTUI_PARAM_HEADER *,_CREDUI_CONTEXT *,ulong,_AUTO_APPROVE_TYPE,ulong,_AM_SCAN_RESULT,char const *,void * *,void * *)

- ea: `0x14000cfdc`
- end: `0x14000d68a`
- name: `?CuiGetTokenForApp@@YAKPEAUHINSTANCE__@@PEAU_CONSENTUI_PARAM_HEADER@@PEAU_CREDUI_CONTEXT@@KW4_AUTO_APPROVE_TYPE@@KW4_AM_SCAN_RESULT@@PEBDPEAPEAX6@Z`
- size: `1710`
- prototype: `__int64 __fastcall(__int64, __int64, const struct _CREDUI_CONTEXT *, unsigned int, int, int, int, __int64, PHANDLE TargetHandle, void **)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14001a080`

## callees

- `0x140007ce0`
- `0x14000a280`
- `0x14000ab5c`
- `0x14000cfdc`
- `0x14000d690`
- `0x14000fbec`
- `0x14000fc2c`
- `0x140010080`
- `0x140013928`
- `0x140013cec`
- `0x140013ee0`
- `0x1400148f8`
- `0x140014a18`
- `0x140015c28`
- `0x140015d68`
- `0x14001700c`
- `0x140019b34`
- `0x14001cf8c`
- `0x14001e050`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x14000d18c`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x14000d18c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14000d19b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14000d19b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000d03d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000d27e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000d2c3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000d2e2`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000d32f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000d4f9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000d536`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000d619`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000d03d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000d27e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000d2c3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000d2e2`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000d32f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000d4f9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000d536`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000d619`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x14000d047`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x14000d047`
- `ntdll!RtlNtStatusToDosError` at `0x14000d39a`
- `ntdll!RtlNtStatusToDosError` at `0x14000d39a`
- `ntdll!RtlEqualSid` at `0x14000d42c`
- `ntdll!RtlEqualSid` at `0x14000d42c`

## pseudocode

```c
__int64 __fastcall CuiGetTokenForApp(
        __int64 a1,
        __int64 a2,
        const struct _CREDUI_CONTEXT *a3,
        unsigned int a4,
        int a5,
        int a6,
        int a7,
        __int64 a8,
        PHANDLE TargetHandle,
        void **a10)
{
  __int64 v13; // r14
  ULONG AutomaticAdminAccount; // ebx
  void **v15; // r14
  __int64 v16; // rcx
  __int64 v17; // rdx
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  HINSTANCE v25; // rcx
  const struct _CREDUI_CONTEXT *v26; // r8
  unsigned int v27; // r9d
  HINSTANCE v28; // rcx
  NTSTATUS v29; // eax
  unsigned __int16 token_information; // ax
  char v31; // r12
  unsigned int v32; // r15d
  _QWORD *v33; // r14
  __int64 v34; // rax
  __int64 v35; // rcx
  __int64 v36; // rdx
  void *v37; // rcx
  unsigned int v38; // eax
  __int64 v39; // r9
  void *Block; // [rsp+58h] [rbp-41h] BYREF
  LARGE_INTEGER v42; // [rsp+60h] [rbp-39h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+68h] [rbp-31h] BYREF
  void *v44; // [rsp+70h] [rbp-29h] BYREF
  LARGE_INTEGER Frequency; // [rsp+78h] [rbp-21h] BYREF
  _DWORD Sid2[4]; // [rsp+80h] [rbp-19h] BYREF

  v13 = a8;
  AutomaticAdminAccount = 0;
  Block = 0;
  Frequency.QuadPart = 0;
  PerformanceCount.QuadPart = 0;
  v42.QuadPart = 0;
  QueryPerformanceCounter(&PerformanceCount);
  QueryPerformanceFrequency(&Frequency);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl) )
    v42 = PerformanceCount;
  *TargetHandle = 0;
  *a10 = 0;
  if ( (*(_DWORD *)(a2 + 48) & 0x2000) == 0 )
    goto LABEL_6;
  if ( *(_DWORD *)(a2 + 8) != 1 )
  {
    *(_DWORD *)(a2 + 8) = 0;
    goto LABEL_6;
  }
  AutomaticAdminAccount = CuipCreateAutomaticAdminAccount(*(HANDLE *)(a2 + 24), TargetHandle);
  if ( !AutomaticAdminAccount )
  {
LABEL_6:
    if ( (*(_DWORD *)(a2 + 48) & 0x8000) != 0 )
    {
      if ( *(_DWORD *)(a2 + 8) != 1 )
      {
        AutomaticAdminAccount = 87;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
          WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 11, WPP_dfa7687bdc833f88b236fff3fe8ed34e_Traceguids);
        goto LABEL_103;
      }
      v15 = (void **)(a2 + 24);
      AutomaticAdminAccount = CuipCreateAutomaticAdminAccount(*(HANDLE *)(a2 + 24), TargetHandle);
      if ( AutomaticAdminAccount )
      {
        v16 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
          goto LABEL_102;
        v17 = 12;
        goto LABEL_19;
      }
    }
    else
    {
      v15 = (void **)(a2 + 24);
    }
    if ( *(_DWORD *)(a2 + 8) >= 2u )
    {
      v15 = (void **)(a2 + 24);
      if ( ImpersonateLoggedOnUser(*(HANDLE *)(a2 + 24)) )
      {
        CuiPlayConsentLaunchedSound();
        RevertToSelf();
      }
    }
    v18 = *(_DWORD *)(a2 + 8);
    if ( !v18 )
    {
      *TargetHandle = 0;
      goto LABEL_102;
    }
    v19 = v18 - 1;
    if ( v19 )
    {
      if ( v19 == 2 )
      {
        v20 = *(_DWORD *)(a2 + 4);
        if ( !v20 )
          goto LABEL_33;
        v21 = v20 - 1;
        if ( !v21 )
          goto LABEL_33;
        v22 = v21 - 1;
        if ( !v22 )
          goto LABEL_33;
        v23 = v22 - 1;
        if ( !v23 )
          goto LABEL_33;
        v24 = v23 - 1;
        if ( v24 )
        {
          if ( v24 != 1 )
            goto LABEL_102;
LABEL_33:
          AutomaticAdminAccount = CuipGetClientLUID(*(HANDLE *)(a2 + 24), (struct _LUID *)&Block);
          if ( AutomaticAdminAccount )
          {
            v16 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
            {
              goto LABEL_102;
            }
            v17 = 14;
            goto LABEL_19;
          }
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl) )
            QueryPerformanceCounter(&PerformanceCount);
          AutomaticAdminAccount = GetCredentials(
                                    v28,
                                    *(HWND *)(a2 + 16),
                                    *(_DWORD *)(a2 + 48),
                                    a4,
                                    a3,
                                    HIDWORD(Block),
                                    (unsigned int)Block,
                                    *(void **)(a2 + 24),
                                    TargetHandle);
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl) )
            QueryPerformanceCounter(&v42);
          if ( AutomaticAdminAccount )
          {
            v16 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
            {
              goto LABEL_102;
            }
            v17 = 15;
            goto LABEL_19;
          }
          if ( (*(_DWORD *)(a2 + 48) & 0x4000) == 0 )
            goto LABEL_102;
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl) )
          {
            LODWORD(Block) = 0;
            v29 = LUAIsUserUACAdminEx(*TargetHandle);
            if ( v29 < 0 )
            {
              AutomaticAdminAccount = RtlNtStatusToDosError(v29);
              goto LABEL_102;
            }
            if ( (_DWORD)Block != 1 )
              goto LABEL_102;
          }
          else
          {
            Sid2[0] = 513;
            Sid2[1] = 83886080;
            Sid2[2] = 32;
            Sid2[3] = 544;
            Block = 0;
            token_information = wil::get_token_information_nothrow<_TOKEN_GROUPS_AND_PRIVILEGES,0>(
                                  &Block,
                                  *TargetHandle);
            AutomaticAdminAccount = token_information;
            if ( token_information )
            {
              if ( Block )
                operator delete(Block);
              goto LABEL_102;
            }
            v31 = 0;
            v32 = 0;
            v33 = Block;
            if ( *(_DWORD *)Block )
            {
              while ( 1 )
              {
                v34 = v33[1];
                if ( (*(_BYTE *)(v34 + 16LL * v32 + 8) & 0x10) != 0 )
                {
                  if ( RtlEqualSid(*(PSID *)(v34 + 16LL * v32), Sid2) )
                    break;
                }
                if ( ++v32 >= *(_DWORD *)v33 )
                  goto LABEL_68;
              }
              v31 = 1;
            }
LABEL_68:
            if ( v33 )
              operator delete(v33);
            if ( !v31 )
              goto LABEL_102;
          }
          v44 = 0;
          AutomaticAdminAccount = CuipCreateAutomaticAdminAccount(*TargetHandle, &v44);
          if ( AutomaticAdminAccount )
          {
            v35 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
            {
              goto LABEL_76;
            }
            v36 = 16;
          }
          else
          {
            AutomaticAdminAccount = CuipDuplicateToken(v44, TargetHandle);
            if ( !AutomaticAdminAccount )
              goto LABEL_76;
            v35 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
            {
              goto LABEL_76;
            }
            v36 = 17;
          }
          WPP_SF_D(*(_QWORD *)(v35 + 16), v36, WPP_dfa7687bdc833f88b236fff3fe8ed34e_Traceguids, AutomaticAdminAccount);
LABEL_76:
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v44);
          goto LABEL_102;
        }
        AutomaticAdminAccount = CuipGetClientLogonSessionLUID(
                                  (struct _CONSENTUI_PARAM_HEADER *)a2,
                                  (struct _LUID *)&Block);
        if ( !AutomaticAdminAccount )
        {
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl) )
            QueryPerformanceCounter(&PerformanceCount);
          AutomaticAdminAccount = RefreshSmartCardCredentials(
                                    v25,
                                    *(HWND *)(a2 + 16),
                                    v26,
                                    v27,
                                    HIDWORD(Block),
                                    (unsigned int)Block,
                                    *(void **)(a2 + 24),
                                    a10);
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl) )
            QueryPerformanceCounter(&v42);
          goto LABEL_102;
        }
        v16 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
        {
LABEL_102:
          v13 = a8;
          goto LABEL_103;
        }
        v17 = 18;
      }
      else
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl) )
          QueryPerformanceCounter(&PerformanceCount);
        AutomaticAdminAccount = GetConsent(*(HWND *)(a2 + 16), *(_DWORD *)(a2 + 48), a3);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl) )
        {
          EtwEventWrite_CredUI_Elevation(a3, *(void **)(a2 + 24), *TargetHandle, AutomaticAdminAccount);
          QueryPerformanceCounter(&v42);
        }
        if ( AutomaticAdminAccount )
        {
          v16 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
            goto LABEL_102;
          v17 = 19;
        }
        else
        {
          v37 = *(void **)(a2 + 24);
          if ( (*(_DWORD *)(a2 + 48) & 0x4000) != 0 )
            v38 = CuipCreateAutomaticAdminAccount(v37, TargetHandle);
          else
            v38 = CuipDuplicateToken(v37, TargetHandle);
          AutomaticAdminAccount = v38;
          if ( !v38 )
            goto LABEL_102;
          v16 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
            goto LABEL_102;
          v17 = 20;
        }
      }
    }
    else
    {
      if ( (*(_DWORD *)(a2 + 48) & 0xA000) != 0 )
        goto LABEL_102;
      AutomaticAdminAccount = CuipDuplicateToken(*v15, TargetHandle);
      if ( !AutomaticAdminAccount )
        goto LABEL_102;
      v16 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
        goto LABEL_102;
      v17 = 13;
    }
LABEL_19:
    WPP_SF_D(*(_QWORD *)(v16 + 16), v17, WPP_dfa7687bdc833f88b236fff3fe8ed34e_Traceguids, AutomaticAdminAccount);
    goto LABEL_102;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
    WPP_SF_D(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      10,
      WPP_dfa7687bdc833f88b236fff3fe8ed34e_Traceguids,
      AutomaticAdminAccount);
LABEL_103:
  if ( ((*(_DWORD *)(a2 + 4) - 4) & 0xFFFFFFFD) != 0 )
  {
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl) )
      QueryPerformanceCounter(&v42);
    LOBYTE(v39) = a5 != 0;
    CuiGenerateTelemetryEvent(
      AutomaticAdminAccount,
      a2,
      a3,
      v39,
      a6,
      a7,
      v13,
      1000 * (v42.QuadPart - PerformanceCount.QuadPart) / Frequency.QuadPart);
  }
  return AutomaticAdminAccount;
}

```

## disassembly

```asm
0x14000cfdc  mov     [rsp-8+arg_0], rbx
0x14000cfe1  push    rbp
0x14000cfe2  push    rsi
0x14000cfe3  push    rdi
0x14000cfe4  push    r12
0x14000cfe6  push    r13
0x14000cfe8  push    r14
0x14000cfea  push    r15
0x14000cfec  lea     rbp, [rsp-7]
0x14000cff1  sub     rsp, 0A0h
0x14000cff8  mov     rax, cs:__security_cookie
0x14000cfff  xor     rax, rsp
0x14000d002  mov     [rbp+37h+var_40], rax
0x14000d006  mov     r12d, r9d
0x14000d009  mov     r13, r8
0x14000d00c  mov     rdi, rdx
0x14000d00f  mov     r14, [rbp+37h+arg_38]
0x14000d013  mov     [rbp+37h+var_80], r14
0x14000d017  mov     rsi, [rbp+37h+TargetHandle]
0x14000d01e  mov     r15, [rbp+37h+arg_48]
0x14000d025  xor     ecx, ecx
0x14000d027  mov     ebx, ecx
0x14000d029  mov     [rbp+37h+Block], rcx
0x14000d02d  mov     qword ptr [rbp+37h+Frequency], rcx
0x14000d031  mov     qword ptr [rbp+37h+PerformanceCount], rcx
0x14000d035  mov     qword ptr [rbp+37h+var_70], rcx
0x14000d039  lea     rcx, [rbp+37h+PerformanceCount]; lpPerformanceCount
0x14000d03d  call    cs:__imp_QueryPerformanceCounter
0x14000d043  lea     rcx, [rbp+37h+Frequency]; lpFrequency
0x14000d047  call    cs:__imp_QueryPerformanceFrequency
0x14000d04d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x14000d054  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x14000d059  test    al, al
0x14000d05b  jz      short loc_14000D065
0x14000d05d  mov     rax, qword ptr [rbp+37h+PerformanceCount]
0x14000d061  mov     qword ptr [rbp+37h+var_70], rax
0x14000d065  mov     [rsi], rbx
0x14000d068  mov     [r15], rbx
0x14000d06b  test    dword ptr [rdi+30h], 2000h
0x14000d072  jz      short loc_14000D07D
0x14000d074  cmp     dword ptr [rdi+8], 1
0x14000d078  jz      short loc_14000D0D2
0x14000d07a  mov     [rdi+8], ebx
0x14000d07d  test    dword ptr [rdi+30h], 8000h
0x14000d084  jz      loc_14000D175
0x14000d08a  cmp     dword ptr [rdi+8], 1
0x14000d08e  jz      loc_14000D122
0x14000d094  mov     ebx, 57h ; 'W'
0x14000d099  lea     rax, WPP_GLOBAL_Control
0x14000d0a0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d0a7  cmp     rcx, rax
0x14000d0aa  jz      loc_14000D5F8
0x14000d0b0  test    byte ptr [rcx+1Ch], 2
0x14000d0b4  jz      loc_14000D5F8
0x14000d0ba  lea     edx, [rbx-4Ch]
0x14000d0bd  lea     r8, WPP_dfa7687bdc833f88b236fff3fe8ed34e_Traceguids
0x14000d0c4  mov     rcx, [rcx+10h]
0x14000d0c8  call    WPP_SF_
0x14000d0cd  jmp     loc_14000D5F8
0x14000d0d2  mov     rdx, rsi; TargetHandle
0x14000d0d5  mov     rcx, [rdi+18h]; SourceHandle
0x14000d0d9  call    ?CuipCreateAutomaticAdminAccount@@YAKPEAXPEAPEAX@Z; CuipCreateAutomaticAdminAccount(void *,void * *)
0x14000d0de  mov     ebx, eax
0x14000d0e0  test    eax, eax
0x14000d0e2  jz      short loc_14000D07D
0x14000d0e4  lea     rax, WPP_GLOBAL_Control
0x14000d0eb  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d0f2  cmp     rcx, rax
0x14000d0f5  jz      loc_14000D5F8
0x14000d0fb  test    byte ptr [rcx+1Ch], 2
0x14000d0ff  jz      loc_14000D5F8
0x14000d105  mov     edx, 0Ah
0x14000d10a  mov     r9d, ebx
0x14000d10d  lea     r8, WPP_dfa7687bdc833f88b236fff3fe8ed34e_Traceguids
0x14000d114  mov     rcx, [rcx+10h]
0x14000d118  call    WPP_SF_D
0x14000d11d  jmp     loc_14000D5F8
0x14000d122  lea     r14, [rdi+18h]
0x14000d126  mov     rdx, rsi; TargetHandle
0x14000d129  mov     rcx, [r14]; SourceHandle
0x14000d12c  call    ?CuipCreateAutomaticAdminAccount@@YAKPEAXPEAPEAX@Z; CuipCreateAutomaticAdminAccount(void *,void * *)
0x14000d131  mov     ebx, eax
0x14000d133  test    eax, eax
0x14000d135  jz      short loc_14000D179
0x14000d137  lea     rax, WPP_GLOBAL_Control
0x14000d13e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d145  cmp     rcx, rax
0x14000d148  jz      loc_14000D5F4
0x14000d14e  test    byte ptr [rcx+1Ch], 2
0x14000d152  jz      loc_14000D5F4
0x14000d158  mov     edx, 0Ch
0x14000d15d  mov     r9d, ebx
0x14000d160  lea     r8, WPP_dfa7687bdc833f88b236fff3fe8ed34e_Traceguids
0x14000d167  mov     rcx, [rcx+10h]
0x14000d16b  call    WPP_SF_D
0x14000d170  jmp     loc_14000D5F4
0x14000d175  lea     r14, [rdi+18h]
0x14000d179  cmp     dword ptr [rdi+8], 0
0x14000d17d  jz      short loc_14000D1A1
0x14000d17f  cmp     dword ptr [rdi+8], 1
0x14000d183  jz      short loc_14000D1A1
0x14000d185  lea     r14, [rdi+18h]
0x14000d189  mov     rcx, [r14]; hToken
0x14000d18c  call    cs:__imp_ImpersonateLoggedOnUser
0x14000d192  test    eax, eax
0x14000d194  jz      short loc_14000D1A1
0x14000d196  call    ?CuiPlayConsentLaunchedSound@@YAXXZ; CuiPlayConsentLaunchedSound(void)
0x14000d19b  call    cs:__imp_RevertToSelf
0x14000d1a1  mov     ecx, [rdi+8]
0x14000d1a4  test    ecx, ecx
0x14000d1a6  jz      loc_14000D5ED
0x14000d1ac  sub     ecx, 1
0x14000d1af  jz      loc_14000D5B0
0x14000d1b5  sub     ecx, 1
0x14000d1b8  jz      loc_14000D4E5
0x14000d1be  cmp     ecx, 1
0x14000d1c1  jnz     loc_14000D4E5
0x14000d1c7  mov     ecx, [rdi+4]
0x14000d1ca  test    ecx, ecx
0x14000d1cc  jz      short loc_14000D1EB
0x14000d1ce  sub     ecx, 1
0x14000d1d1  jz      short loc_14000D1EB
0x14000d1d3  sub     ecx, 1
0x14000d1d6  jz      short loc_14000D1EB
0x14000d1d8  sub     ecx, 1
0x14000d1db  jz      short loc_14000D1EB
0x14000d1dd  sub     ecx, 1
0x14000d1e0  jz      short loc_14000D22D
0x14000d1e2  cmp     ecx, 1
0x14000d1e5  jnz     loc_14000D5F4
0x14000d1eb  lea     rdx, [rbp+37h+Block]; struct _LUID *
0x14000d1ef  mov     rcx, [rdi+18h]; TokenHandle
0x14000d1f3  call    ?CuipGetClientLUID@@YAKPEAXPEAU_LUID@@@Z; CuipGetClientLUID(void *,_LUID *)
0x14000d1f8  mov     ebx, eax
0x14000d1fa  test    eax, eax
0x14000d1fc  jz      loc_14000D2CE
0x14000d202  lea     rax, WPP_GLOBAL_Control
0x14000d209  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d210  cmp     rcx, rax
0x14000d213  jz      loc_14000D5F4
0x14000d219  test    byte ptr [rcx+1Ch], 2
0x14000d21d  jz      loc_14000D5F4
0x14000d223  mov     edx, 0Eh
0x14000d228  jmp     loc_14000D15D
0x14000d22d  lea     rdx, [rbp+37h+Block]; struct _LUID *
0x14000d231  mov     rcx, rdi; struct _CONSENTUI_PARAM_HEADER *
0x14000d234  call    ?CuipGetClientLogonSessionLUID@@YAKPEAU_CONSENTUI_PARAM_HEADER@@PEAU_LUID@@@Z; CuipGetClientLogonSessionLUID(_CONSENTUI_PARAM_HEADER *,_LUID *)
0x14000d239  mov     ebx, eax
0x14000d23b  test    eax, eax
0x14000d23d  jz      short loc_14000D26A
0x14000d23f  lea     rax, WPP_GLOBAL_Control
0x14000d246  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d24d  cmp     rcx, rax
0x14000d250  jz      loc_14000D5F4
0x14000d256  test    byte ptr [rcx+1Ch], 2
0x14000d25a  jz      loc_14000D5F4
0x14000d260  mov     edx, 12h
0x14000d265  jmp     loc_14000D15D
0x14000d26a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x14000d271  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x14000d276  test    al, al
0x14000d278  jz      short loc_14000D284
0x14000d27a  lea     rcx, [rbp+37h+PerformanceCount]; lpPerformanceCount
0x14000d27e  call    cs:__imp_QueryPerformanceCounter
0x14000d284  mov     [rsp+0D0h+var_98], r15; void **
0x14000d289  mov     rax, [rdi+18h]
0x14000d28d  mov     [rsp+0D0h+var_A0], rax; void *
0x14000d292  mov     eax, dword ptr [rbp+37h+Block]
0x14000d295  mov     [rsp+0D0h+var_A8], eax; unsigned int
0x14000d299  mov     eax, dword ptr [rbp+37h+Block+4]
0x14000d29c  mov     dword ptr [rsp+0D0h+var_B0], eax; unsigned int
0x14000d2a0  mov     rdx, [rdi+10h]; HWND
0x14000d2a4  call    ?RefreshSmartCardCredentials@@YAKPEAUHINSTANCE__@@PEAUHWND__@@PEBU_CREDUI_CONTEXT@@KKKPEAXPEAPEAX@Z; RefreshSmartCardCredentials(HINSTANCE__ *,HWND__ *,_CREDUI_CONTEXT const *,ulong,ulong,ulong,void *,void * *)
0x14000d2a9  mov     ebx, eax
0x14000d2ab  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x14000d2b2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x14000d2b7  test    al, al
0x14000d2b9  jz      loc_14000D5F4
0x14000d2bf  lea     rcx, [rbp+37h+var_70]; lpPerformanceCount
0x14000d2c3  call    cs:__imp_QueryPerformanceCounter
0x14000d2c9  jmp     loc_14000D5F4
0x14000d2ce  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x14000d2d5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x14000d2da  test    al, al
0x14000d2dc  jz      short loc_14000D2E8
0x14000d2de  lea     rcx, [rbp+37h+PerformanceCount]; lpPerformanceCount
0x14000d2e2  call    cs:__imp_QueryPerformanceCounter
0x14000d2e8  mov     [rsp+0D0h+var_90], rsi; void **
0x14000d2ed  mov     rax, [rdi+18h]
0x14000d2f1  mov     [rsp+0D0h+var_98], rax; void *
0x14000d2f6  mov     eax, dword ptr [rbp+37h+Block]
0x14000d2f9  mov     dword ptr [rsp+0D0h+var_A0], eax; unsigned int
0x14000d2fd  mov     eax, dword ptr [rbp+37h+Block+4]
0x14000d300  mov     [rsp+0D0h+var_A8], eax; unsigned int
0x14000d304  mov     [rsp+0D0h+var_B0], r13; struct _CREDUI_CONTEXT *
0x14000d309  mov     r9d, r12d; unsigned int
0x14000d30c  mov     r8d, [rdi+30h]; unsigned int
0x14000d310  mov     rdx, [rdi+10h]; HWND
0x14000d314  call    ?GetCredentials@@YAKPEAUHINSTANCE__@@PEAUHWND__@@KKPEBU_CREDUI_CONTEXT@@KKPEAXPEAPEAX@Z; GetCredentials(HINSTANCE__ *,HWND__ *,ulong,ulong,_CREDUI_CONTEXT const *,ulong,ulong,void *,void * *)
0x14000d319  mov     ebx, eax
0x14000d31b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x14000d322  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x14000d327  test    al, al
0x14000d329  jz      short loc_14000D335
0x14000d32b  lea     rcx, [rbp+37h+var_70]; lpPerformanceCount
0x14000d32f  call    cs:__imp_QueryPerformanceCounter
0x14000d335  test    ebx, ebx
0x14000d337  jz      short loc_14000D364
0x14000d339  lea     rax, WPP_GLOBAL_Control
0x14000d340  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d347  cmp     rcx, rax
0x14000d34a  jz      loc_14000D5F4
0x14000d350  test    byte ptr [rcx+1Ch], 2
0x14000d354  jz      loc_14000D5F4
0x14000d35a  mov     edx, 0Fh
0x14000d35f  jmp     loc_14000D15D
0x14000d364  test    dword ptr [rdi+30h], 4000h
0x14000d36b  jz      loc_14000D5F4
0x14000d371  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x14000d378  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x14000d37d  test    al, al
0x14000d37f  jz      short loc_14000D3B6
0x14000d381  mov     dword ptr [rbp+37h+Block], 0
0x14000d388  lea     rdx, [rbp+37h+Block]
0x14000d38c  mov     rcx, [rsi]; TokenHandle
0x14000d38f  call    LUAIsUserUACAdminEx
0x14000d394  test    eax, eax
0x14000d396  jns     short loc_14000D3A7
0x14000d398  mov     ecx, eax; Status
0x14000d39a  call    cs:__imp_RtlNtStatusToDosError
0x14000d3a0  mov     ebx, eax
0x14000d3a2  jmp     loc_14000D5F4
0x14000d3a7  cmp     dword ptr [rbp+37h+Block], 1
0x14000d3ab  jnz     loc_14000D5F4
0x14000d3b1  jmp     loc_14000D459
0x14000d3b6  mov     [rbp+37h+Sid2], 201h
0x14000d3bd  mov     [rbp+37h+var_4C], 5000000h
0x14000d3c4  mov     [rbp+37h+var_48], 20h ; ' '
0x14000d3cb  mov     [rbp+37h+var_44], 220h
0x14000d3d2  mov     [rbp+37h+Block], 0
0x14000d3da  mov     rdx, [rsi]
0x14000d3dd  lea     rcx, [rbp+37h+Block]
0x14000d3e1  call    ??$get_token_information_nothrow@U_TOKEN_GROUPS_AND_PRIVILEGES@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_GROUPS_AND_PRIVILEGES@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_GROUPS_AND_PRIVILEGES,0>(wistd::unique_ptr<_TOKEN_GROUPS_AND_PRIVILEGES,wil::details::token_info_deleter> &,void *)
0x14000d3e6  movzx   ebx, ax
0x14000d3e9  test    ebx, ebx
0x14000d3eb  jz      short loc_14000D404
0x14000d3ed  mov     rcx, [rbp+37h+Block]; Block
0x14000d3f1  test    rcx, rcx
0x14000d3f4  jz      loc_14000D5F4
0x14000d3fa  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000d3ff  jmp     loc_14000D5F4
0x14000d404  xor     r12b, r12b
0x14000d407  xor     r15d, r15d
0x14000d40a  mov     r14, [rbp+37h+Block]
0x14000d40e  cmp     [r14], r15d
0x14000d411  jbe     short loc_14000D443
0x14000d413  mov     ecx, r15d
0x14000d416  add     rcx, rcx
0x14000d419  mov     rax, [r14+8]
0x14000d41d  test    byte ptr [rax+rcx*8+8], 10h
0x14000d422  jz      short loc_14000D436
0x14000d424  lea     rdx, [rbp+37h+Sid2]; Sid2
0x14000d428  mov     rcx, [rax+rcx*8]; Sid1
0x14000d42c  call    cs:__imp_RtlEqualSid
0x14000d432  test    al, al
0x14000d434  jnz     short loc_14000D440
0x14000d436  inc     r15d
0x14000d439  cmp     r15d, [r14]
0x14000d43c  jb      short loc_14000D413
0x14000d43e  jmp     short loc_14000D443
0x14000d440  mov     r12b, 1
0x14000d443  test    r14, r14
0x14000d446  jz      short loc_14000D450
0x14000d448  mov     rcx, r14; Block
0x14000d44b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000d450  test    r12b, r12b
0x14000d453  jz      loc_14000D5F4
0x14000d459  mov     [rbp+37h+var_60], 0
0x14000d461  lea     rdx, [rbp+37h+var_60]; TargetHandle
0x14000d465  mov     rcx, [rsi]; SourceHandle
0x14000d468  call    ?CuipCreateAutomaticAdminAccount@@YAKPEAXPEAPEAX@Z; CuipCreateAutomaticAdminAccount(void *,void * *)
0x14000d46d  mov     ebx, eax
0x14000d46f  test    eax, eax
0x14000d471  jz      short loc_14000D4B3
0x14000d473  lea     rax, WPP_GLOBAL_Control
0x14000d47a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d481  cmp     rcx, rax
0x14000d484  jz      short loc_14000D4A5
0x14000d486  test    byte ptr [rcx+1Ch], 2
0x14000d48a  jz      short loc_14000D4A5
0x14000d48c  mov     edx, 10h
0x14000d491  mov     r9d, ebx
0x14000d494  lea     r8, WPP_dfa7687bdc833f88b236fff3fe8ed34e_Traceguids
0x14000d49b  mov     rcx, [rcx+10h]
0x14000d49f  call    WPP_SF_D
0x14000d4a4  nop
0x14000d4a5  lea     rcx, [rbp+37h+var_60]
0x14000d4a9  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14000d4ae  jmp     loc_14000D5F4
0x14000d4b3  mov     rdx, rsi; void **
  ... truncated ...
```
