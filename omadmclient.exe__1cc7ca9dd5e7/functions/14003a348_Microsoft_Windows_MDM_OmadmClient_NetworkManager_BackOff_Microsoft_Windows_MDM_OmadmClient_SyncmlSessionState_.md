# Microsoft::Windows::MDM::OmadmClient::NetworkManager::BackOff(Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState &,ulong,ulong,PushRouterSubmitOrigin)

- ea: `0x14003a348`
- end: `0x14003a733`
- name: `?BackOff@NetworkManager@OmadmClient@MDM@Windows@Microsoft@@IEAAJAEAVSyncmlSessionState@2345@KKW4PushRouterSubmitOrigin@@@Z`
- size: `1003`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14003b9f0`

## callees

- `0x14000e610`
- `0x14000fe6c`
- `0x140010f18`
- `0x140013404`
- `0x140013bc8`
- `0x1400152d4`
- `0x14003a348`
- `0x14003a73c`
- `0x14003ac50`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003a4c5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003a4c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003a511`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003a511`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x14003a4ff`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x14003a4ff`
- `DMCmnUtils!IsWvdFeatureAllowed` at `0x14003a482`
- `DMCmnUtils!IsWvdFeatureAllowed` at `0x14003a482`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::NetworkManager::BackOff(
        Microsoft::Windows::MDM::OmadmClient::NetworkManager *a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        int a5)
{
  __int64 v5; // r15
  unsigned __int64 v9; // rax
  int v10; // ecx
  __int64 v11; // rcx
  unsigned int v12; // edi
  unsigned int v13; // r8d
  LSTATUS v14; // eax
  unsigned int v15; // ebx
  const unsigned __int16 *v16; // rbx
  __int64 v17; // rax
  COmaDmLogger *Logger; // rax
  const unsigned __int16 *v19; // r8
  unsigned int v20; // ebx
  int v21; // eax
  __int64 v22; // rcx
  unsigned int v23; // r8d
  unsigned int v24; // r9d
  struct COmaDmLogger *v25; // rax
  HKEY *phkResult; // [rsp+20h] [rbp-60h]
  HKEY *phkResulta; // [rsp+20h] [rbp-60h]
  int v29; // [rsp+40h] [rbp-40h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-38h] BYREF
  __int64 v31; // [rsp+50h] [rbp-30h] BYREF
  _QWORD v32[3]; // [rsp+58h] [rbp-28h] BYREF
  int v33; // [rsp+70h] [rbp-10h]
  int *v34; // [rsp+78h] [rbp-8h]

  v5 = a4;
  v29 = 0;
  v32[0] = 0;
  v32[1] = "BackOff";
  v32[2] = COmaDmLogger::GetLogger();
  v33 = 2;
  v34 = &v29;
  LODWORD(v9) = *(_DWORD *)(a2 + 792);
  v10 = 1;
  if ( a3 > 1 )
  {
    while ( 1 )
    {
      v9 = 2LL * (unsigned int)v9;
      if ( v9 > 0xFFFFFFFF )
        break;
      if ( ++v10 >= a3 )
        goto LABEL_6;
    }
    LODWORD(v9) = 86400000;
  }
LABEL_6:
  v11 = *(unsigned int *)(a2 + 788);
  if ( (unsigned int)v9 <= (unsigned int)v11 )
    v11 = (unsigned int)v9;
  if ( (_DWORD)v5 )
  {
    v12 = 1000 * v5;
    if ( (unsigned __int64)(1000 * v5) > 0xFFFFFFFF )
      v12 = 86400000;
    if ( a3 > 1 && (unsigned int)v11 >= v12 )
      v12 = v11;
  }
  else
  {
    v12 = v11;
  }
  v13 = *(_DWORD *)Feature_OmaDmClient_BackOff_Retry_ScheduledTask__descriptor;
  if ( (*(_DWORD *)Feature_OmaDmClient_BackOff_Retry_ScheduledTask__descriptor & 4) == 0 )
  {
    v31 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OmaDmClient_BackOff_Retry_ScheduledTask>::GetCachedFeatureEnabledState(
                       v11,
                       &v31);
    v13 = v31;
  }
  LODWORD(hKey) = 0;
  WORD2(hKey) = 3;
  phkResult = &hKey;
  wil::details::ReportUsageToService(&qword_1400850A0, 57312060, (v13 >> 10) & 1, (v13 >> 11) & 1);
  if ( a5 == 20
    || (unsigned int)(a5 - 36) < 2
    || IsWvdFeatureAllowed(*(const unsigned __int16 **)(a2 + 560))
    || v12 <= 0xFA00 )
  {
    v20 = v29;
  }
  else
  {
    hKey = 0;
    v14 = RegOpenKeyExW(*(HKEY *)(a2 + 936), 0, 0, 0x2001Fu, &hKey);
    v15 = v14;
    if ( v14 )
    {
      if ( v14 > 0 )
        v15 = (unsigned __int16)v14 | 0x80070000;
    }
    else
    {
      v15 = OmaDmRegistrySetDWORD(hKey, 0, L"RetryDelay", v12 / 0xEA60 + 1);
      RegCloseKey(hKey);
    }
    v29 = v15;
    v16 = 0;
    v17 = *(_QWORD *)(a2 + 40);
    if ( *(_QWORD *)(v17 + 32) )
      v16 = *(const unsigned __int16 **)(v17 + 32);
    Logger = COmaDmLogger::GetLogger();
    v19 = &word_14006E728;
    if ( v16 )
      v19 = v16;
    COmaDmLogger::LogOmaDmSessionStoreBackOffRetryInfo(Logger, *(const unsigned __int16 **)(a2 + 560), v19, v12, v29);
    v20 = v29;
    if ( v29 >= 0 )
    {
      v20 = -2102657013;
      v29 = -2102657013;
    }
  }
  if ( v20 != -2102657013 )
  {
    v21 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD))(**((_QWORD **)a1 + 8) + 16LL))(*((_QWORD **)a1 + 8), 0);
    v20 = v21;
    v29 = v21;
    if ( v21 < 0 )
    {
      LODWORD(v32[0]) = 18021;
LABEL_49:
      HIDWORD(v32[0]) = v21;
      goto LABEL_50;
    }
    LODWORD(phkResult) = a5;
    v21 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD, __int64, HKEY *, int))(**((_QWORD **)a1 + 8) + 8LL))(
            *((_QWORD **)a1 + 8),
            2,
            v12 / 0x3E8 + 5,
            2,
            phkResult,
            1);
    v20 = v21;
    v29 = v21;
    if ( v21 < 0 )
    {
      LODWORD(v32[0]) = 18020;
      goto LABEL_49;
    }
    v23 = *(_DWORD *)Feature_OmaDmClient_CheckForDisconnectedNetworkDuringBackOff__descriptor;
    if ( (*(_DWORD *)Feature_OmaDmClient_CheckForDisconnectedNetworkDuringBackOff__descriptor & 4) == 0 )
    {
      v31 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OmaDmClient_CheckForDisconnectedNetworkDuringBackOff>::GetCachedFeatureEnabledState(
                         v22,
                         &v31);
      v23 = v31;
    }
    LODWORD(hKey) = 0;
    WORD2(hKey) = 3;
    phkResulta = &hKey;
    wil::details::ReportUsageToService(&qword_140085258, 46731456, (v23 >> 10) & 1, (v23 >> 11) & 1);
    v29 = Microsoft::Windows::MDM::OmadmClient::NetworkManager::BackOffWhileNetworkConnected(
            a1,
            (struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *)a2,
            v12,
            v24);
    if ( v29 >= 0 )
    {
      if ( (_DWORD)v5 )
      {
        v25 = COmaDmLogger::GetLogger();
        Microsoft::Windows::TelemetryLogger::LogMeasureWithPrivacyTag(
          v25,
          1,
          0x2000000,
          30041,
          L"429 timeout finished",
          1);
      }
      v21 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(**((_QWORD **)a1 + 8) + 16LL))(*((_QWORD **)a1 + 8), 2);
      v20 = v21;
      v29 = v21;
      if ( v21 < 0 )
        goto LABEL_42;
      LODWORD(phkResulta) = a5;
      v21 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, _QWORD, _QWORD, HKEY *))(**((_QWORD **)a1 + 8) + 8LL))(
              *((_QWORD **)a1 + 8),
              0,
              3 * *(_DWORD *)(a2 + 772) / 0x7D0u,
              0,
              phkResulta);
      v20 = v21;
      v29 = v21;
      if ( v21 < 0 )
      {
        LODWORD(v32[0]) = 18019;
        goto LABEL_49;
      }
    }
    else
    {
      v21 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(**((_QWORD **)a1 + 8) + 16LL))(*((_QWORD **)a1 + 8), 2);
      v20 = v21;
      if ( v21 < 0 )
      {
LABEL_42:
        LODWORD(v32[0]) = 18022;
        goto LABEL_49;
      }
      v20 = v29;
    }
  }
LABEL_50:
  Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v32);
  return v20;
}

```

## disassembly

```asm
0x14003a348  push    rbp
0x14003a34a  push    rbx
0x14003a34b  push    rsi
0x14003a34c  push    rdi
0x14003a34d  push    r12
0x14003a34f  push    r14
0x14003a351  push    r15
0x14003a353  mov     rbp, rsp
0x14003a356  sub     rsp, 80h
0x14003a35d  mov     r15d, r9d
0x14003a360  mov     ebx, r8d
0x14003a363  mov     rsi, rdx
0x14003a366  mov     r14, rcx
0x14003a369  mov     [rbp+var_40], 0
0x14003a370  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x14003a375  mov     [rbp+var_28], 0
0x14003a37d  lea     rcx, aBackoff; "BackOff"
0x14003a384  mov     [rbp+var_20], rcx
0x14003a388  mov     [rbp+var_18], rax
0x14003a38c  mov     [rbp+var_10], 2
0x14003a393  lea     rax, [rbp+var_40]
0x14003a397  mov     [rbp+var_8], rax
0x14003a39b  mov     eax, [rsi+318h]
0x14003a3a1  mov     r12d, 1
0x14003a3a7  mov     ecx, r12d
0x14003a3aa  mov     edx, 5265C00h
0x14003a3af  mov     r8d, 0FFFFFFFFh
0x14003a3b5  cmp     ebx, r12d
0x14003a3b8  jbe     short loc_14003A3CF
0x14003a3ba  mov     eax, eax
0x14003a3bc  add     rax, rax
0x14003a3bf  cmp     rax, r8
0x14003a3c2  ja      short loc_14003A3CD
0x14003a3c4  add     ecx, r12d
0x14003a3c7  cmp     ecx, ebx
0x14003a3c9  jb      short loc_14003A3BA
0x14003a3cb  jmp     short loc_14003A3CF
0x14003a3cd  mov     eax, edx
0x14003a3cf  mov     ecx, [rsi+314h]
0x14003a3d5  cmp     eax, ecx
0x14003a3d7  cmovbe  ecx, eax
0x14003a3da  test    r15d, r15d
0x14003a3dd  jz      short loc_14003A3F9
0x14003a3df  imul    rdi, r15, 3E8h
0x14003a3e6  cmp     rdi, r8
0x14003a3e9  jbe     short loc_14003A3ED
0x14003a3eb  mov     edi, edx
0x14003a3ed  cmp     ebx, r12d
0x14003a3f0  jbe     short loc_14003A3FB
0x14003a3f2  cmp     ecx, edi
0x14003a3f4  cmovnb  edi, ecx
0x14003a3f7  jmp     short loc_14003A3FB
0x14003a3f9  mov     edi, ecx
0x14003a3fb  mov     rax, cs:Feature_OmaDmClient_BackOff_Retry_ScheduledTask__descriptor
0x14003a402  mov     r8d, [rax]
0x14003a405  test    r8b, 4
0x14003a409  jnz     short loc_14003A41E
0x14003a40b  lea     rdx, [rbp+var_30]
0x14003a40f  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_OmaDmClient_BackOff_Retry_ScheduledTask@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OmaDmClient_BackOff_Retry_ScheduledTask>::GetCachedFeatureEnabledState(void)
0x14003a414  mov     rcx, [rax]
0x14003a417  mov     [rbp+var_30], rcx
0x14003a41b  mov     r8d, ecx
0x14003a41e  xor     eax, eax
0x14003a420  mov     dword ptr [rbp+hKey], eax
0x14003a423  mov     word ptr [rbp+hKey+4], 3
0x14003a429  mov     r9d, r8d
0x14003a42c  shr     r9d, 0Bh
0x14003a430  and     r9d, r12d
0x14003a433  shr     r8d, 0Ah
0x14003a437  and     r8d, r12d
0x14003a43a  mov     [rsp+80h+var_58], r12d
0x14003a43f  lea     rax, [rbp+hKey]
0x14003a443  mov     [rsp+80h+phkResult], rax
0x14003a448  mov     edx, 36A833Ch
0x14003a44d  lea     rcx, qword_1400850A0
0x14003a454  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x14003a459  mov     r12d, [rbp+arg_20]
0x14003a45d  mov     ecx, r12d
0x14003a460  sub     ecx, 14h
0x14003a463  jz      loc_14003A56C
0x14003a469  sub     ecx, 10h
0x14003a46c  jz      loc_14003A56C
0x14003a472  cmp     ecx, 1
0x14003a475  jz      loc_14003A56C
0x14003a47b  mov     rcx, [rsi+230h]
0x14003a482  call    cs:__imp_?IsWvdFeatureAllowed@@YAHPEBG@Z; IsWvdFeatureAllowed(ushort const *)
0x14003a489  nop     dword ptr [rax+rax+00h]
0x14003a48e  test    eax, eax
0x14003a490  jnz     loc_14003A56C
0x14003a496  cmp     edi, 0FA00h
0x14003a49c  jbe     loc_14003A56C
0x14003a4a2  mov     [rbp+hKey], 0
0x14003a4aa  lea     rax, [rbp+hKey]
0x14003a4ae  mov     [rsp+80h+phkResult], rax; phkResult
0x14003a4b3  mov     r9d, 2001Fh; samDesired
0x14003a4b9  xor     r8d, r8d; ulOptions
0x14003a4bc  xor     edx, edx; lpSubKey
0x14003a4be  mov     rcx, [rsi+3A8h]; hKey
0x14003a4c5  call    cs:__imp_RegOpenKeyExW
0x14003a4cc  nop     dword ptr [rax+rax+00h]
0x14003a4d1  mov     ebx, eax
0x14003a4d3  test    eax, eax
0x14003a4d5  jz      short loc_14003A4E4
0x14003a4d7  jle     short loc_14003A51D
0x14003a4d9  movzx   ebx, ax
0x14003a4dc  or      ebx, 80070000h
0x14003a4e2  jmp     short loc_14003A51D
0x14003a4e4  mov     eax, 45E7B273h
0x14003a4e9  mul     edi
0x14003a4eb  shr     edx, 0Eh
0x14003a4ee  lea     r9d, [rdx+1]
0x14003a4f2  lea     r8, aRetrydelay; "RetryDelay"
0x14003a4f9  xor     edx, edx
0x14003a4fb  mov     rcx, [rbp+hKey]
0x14003a4ff  call    cs:__imp_?OmaDmRegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; OmaDmRegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x14003a506  nop     dword ptr [rax+rax+00h]
0x14003a50b  mov     ebx, eax
0x14003a50d  mov     rcx, [rbp+hKey]; hKey
0x14003a511  call    cs:__imp_RegCloseKey
0x14003a518  nop     dword ptr [rax+rax+00h]
0x14003a51d  mov     [rbp+var_40], ebx
0x14003a520  xor     ebx, ebx
0x14003a522  mov     rax, [rsi+28h]
0x14003a526  cmp     [rax+20h], rbx
0x14003a52a  cmovnz  rbx, [rax+20h]
0x14003a52f  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x14003a534  mov     ecx, [rbp+var_40]
0x14003a537  lea     r8, word_14006E728
0x14003a53e  test    rbx, rbx
0x14003a541  cmovnz  r8, rbx; unsigned __int16 *
0x14003a545  mov     dword ptr [rsp+80h+phkResult], ecx; int
0x14003a549  mov     r9d, edi; unsigned int
0x14003a54c  mov     rdx, [rsi+230h]; unsigned __int16 *
0x14003a553  mov     rcx, rax; this
0x14003a556  call    ?LogOmaDmSessionStoreBackOffRetryInfo@COmaDmLogger@@QEAAXPEBG0KJ@Z; COmaDmLogger::LogOmaDmSessionStoreBackOffRetryInfo(ushort const *,ushort const *,ulong,long)
0x14003a55b  mov     ebx, [rbp+var_40]
0x14003a55e  test    ebx, ebx
0x14003a560  js      short loc_14003A56F
0x14003a562  mov     ebx, 82AC000Bh
0x14003a567  mov     [rbp+var_40], ebx
0x14003a56a  jmp     short loc_14003A56F
0x14003a56c  mov     ebx, [rbp+var_40]
0x14003a56f  cmp     ebx, 82AC000Bh
0x14003a575  jz      loc_14003A715
0x14003a57b  mov     rcx, [r14+40h]
0x14003a57f  mov     rax, [rcx]
0x14003a582  xor     edx, edx
0x14003a584  mov     rax, [rax+10h]
0x14003a588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003a58d  mov     ebx, eax
0x14003a58f  mov     [rbp+var_40], eax
0x14003a592  test    eax, eax
0x14003a594  jns     short loc_14003A5A2
0x14003a596  mov     dword ptr [rbp+var_28], 4665h
0x14003a59d  jmp     loc_14003A712
0x14003a5a2  mov     rcx, [r14+40h]
0x14003a5a6  mov     r10, [rcx]
0x14003a5a9  mov     eax, 10624DD3h
0x14003a5ae  mul     edi
0x14003a5b0  shr     edx, 6
0x14003a5b3  lea     r8d, [rdx+5]
0x14003a5b7  mov     dword ptr [rsp+80h+phkResult], r12d
0x14003a5bc  mov     eax, 2
0x14003a5c1  mov     r9d, eax
0x14003a5c4  mov     edx, eax
0x14003a5c6  mov     rax, [r10+8]
0x14003a5ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003a5cf  mov     ebx, eax
0x14003a5d1  mov     [rbp+var_40], eax
0x14003a5d4  test    eax, eax
0x14003a5d6  jns     short loc_14003A5E4
0x14003a5d8  mov     dword ptr [rbp+var_28], 4664h
0x14003a5df  jmp     loc_14003A712
0x14003a5e4  mov     rax, cs:Feature_OmaDmClient_CheckForDisconnectedNetworkDuringBackOff__descriptor
0x14003a5eb  mov     r8d, [rax]
0x14003a5ee  test    r8b, 4
0x14003a5f2  jnz     short loc_14003A607
0x14003a5f4  lea     rdx, [rbp+var_30]
0x14003a5f8  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_OmaDmClient_CheckForDisconnectedNetworkDuringBackOff@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OmaDmClient_CheckForDisconnectedNetworkDuringBackOff>::GetCachedFeatureEnabledState(void)
0x14003a5fd  mov     rcx, [rax]
0x14003a600  mov     [rbp+var_30], rcx
0x14003a604  mov     r8d, ecx
0x14003a607  xor     eax, eax
0x14003a609  mov     dword ptr [rbp+hKey], eax
0x14003a60c  mov     word ptr [rbp+hKey+4], 3
0x14003a612  mov     r9d, r8d
0x14003a615  shr     r9d, 0Bh
0x14003a619  lea     ebx, [rax+1]
0x14003a61c  and     r9d, ebx
0x14003a61f  shr     r8d, 0Ah
0x14003a623  and     r8d, ebx
0x14003a626  mov     [rsp+80h+var_58], ebx
0x14003a62a  lea     rax, [rbp+hKey]
0x14003a62e  mov     [rsp+80h+phkResult], rax
0x14003a633  mov     edx, 2C910C0h
0x14003a638  lea     rcx, qword_140085258
0x14003a63f  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x14003a644  mov     r8d, edi; unsigned int
0x14003a647  mov     rdx, rsi; struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *
0x14003a64a  mov     rcx, r14; this
0x14003a64d  call    ?BackOffWhileNetworkConnected@NetworkManager@OmadmClient@MDM@Windows@Microsoft@@IEAAJAEAVSyncmlSessionState@2345@KK@Z; Microsoft::Windows::MDM::OmadmClient::NetworkManager::BackOffWhileNetworkConnected(Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState &,ulong,ulong)
0x14003a652  mov     [rbp+var_40], eax
0x14003a655  test    eax, eax
0x14003a657  jns     short loc_14003A686
0x14003a659  mov     rcx, [r14+40h]
0x14003a65d  mov     rax, [rcx]
0x14003a660  lea     edx, [rbx+1]
0x14003a663  mov     rax, [rax+10h]
0x14003a667  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003a66c  mov     ebx, eax
0x14003a66e  test    eax, eax
0x14003a670  jns     short loc_14003A67E
0x14003a672  mov     dword ptr [rbp+var_28], 4666h
0x14003a679  jmp     loc_14003A712
0x14003a67e  mov     ebx, [rbp+var_40]
0x14003a681  jmp     loc_14003A715
0x14003a686  test    r15d, r15d
0x14003a689  jz      short loc_14003A6B2
0x14003a68b  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x14003a690  lea     rcx, a429TimeoutFini; "429 timeout finished"
0x14003a697  mov     [rsp+80h+phkResult], rcx
0x14003a69c  mov     r9d, 7559h
0x14003a6a2  mov     r8d, 2000000h
0x14003a6a8  mov     edx, ebx
0x14003a6aa  mov     rcx, rax
0x14003a6ad  call    ?LogMeasureWithPrivacyTag@TelemetryLogger@Windows@Microsoft@@QEAAXW4TracingLevel@23@IKPEBGZZ; Microsoft::Windows::TelemetryLogger::LogMeasureWithPrivacyTag(Microsoft::Windows::TracingLevel,uint,ulong,ushort const *,...)
0x14003a6b2  mov     rcx, [r14+40h]
0x14003a6b6  mov     rax, [rcx]
0x14003a6b9  mov     edx, 2
0x14003a6be  mov     rax, [rax+10h]
0x14003a6c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003a6c7  mov     ebx, eax
0x14003a6c9  mov     [rbp+var_40], eax
0x14003a6cc  test    eax, eax
0x14003a6ce  js      short loc_14003A672
0x14003a6d0  mov     rcx, [r14+40h]
0x14003a6d4  mov     r9, [rcx]
0x14003a6d7  mov     edx, [rsi+304h]
0x14003a6dd  lea     r8d, [rdx+rdx*2]
0x14003a6e1  mov     eax, 10624DD3h
0x14003a6e6  mul     r8d
0x14003a6e9  shr     edx, 7
0x14003a6ec  mov     rax, [r9+8]
0x14003a6f0  mov     dword ptr [rsp+80h+phkResult], r12d
0x14003a6f5  xor     r9d, r9d
0x14003a6f8  mov     r8d, edx
0x14003a6fb  xor     edx, edx
0x14003a6fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003a702  mov     ebx, eax
0x14003a704  mov     [rbp+var_40], eax
0x14003a707  test    eax, eax
0x14003a709  jns     short loc_14003A715
0x14003a70b  mov     dword ptr [rbp+var_28], 4663h
0x14003a712  mov     dword ptr [rbp+var_28+4], eax
0x14003a715  lea     rcx, [rbp+var_28]; this
0x14003a719  call    ??1TelemetryInfo@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::TelemetryInfo::~TelemetryInfo(void)
0x14003a71e  mov     eax, ebx
0x14003a720  add     rsp, 80h
0x14003a727  pop     r15
0x14003a729  pop     r14
0x14003a72b  pop     r12
0x14003a72d  pop     rdi
0x14003a72e  pop     rsi
0x14003a72f  pop     rbx
0x14003a730  pop     rbp
0x14003a731  retn
```
