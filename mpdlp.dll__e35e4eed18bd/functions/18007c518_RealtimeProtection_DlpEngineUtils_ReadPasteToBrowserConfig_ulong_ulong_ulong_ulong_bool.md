# RealtimeProtection::DlpEngineUtils::ReadPasteToBrowserConfig(ulong &,ulong &,ulong &,ulong &,bool &)

- ea: `0x18007c518`
- end: `0x18007c86b`
- name: `?ReadPasteToBrowserConfig@DlpEngineUtils@RealtimeProtection@@YAJAEAK000AEA_N@Z`
- size: `851`
- prototype: `__int64 __fastcall(RealtimeProtection::DlpEngineUtils *__hidden this, unsigned int *, unsigned int *, unsigned int *, unsigned int *, bool *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18007a790`
- `0x18019d7f8`

## callees

- `0x180046d10`
- `0x180079dc0`
- `0x18007c518`
- `0x18007d9b8`
- `0x1800809d0`
- `0x180089510`
- `0x180097960`
- `0x1800a7df0`
- `0x1800bc308`
- `0x18010cb40`
- `0x1801ab6a4`

## import_xrefs

- `MpClient!MpConfigSetValue` at `0x18007c7f2`
- `MpClient!MpConfigSetValue` at `0x18007c7f2`
- `MpClient!MpConfigClose` at `0x18007c795`
- `MpClient!MpConfigClose` at `0x18007c7bf`
- `MpClient!MpConfigClose` at `0x18007c7ce`
- `MpClient!MpConfigClose` at `0x18007c837`
- `MpClient!MpConfigClose` at `0x18007c846`
- `MpClient!MpConfigClose` at `0x18007c795`
- `MpClient!MpConfigClose` at `0x18007c7bf`
- `MpClient!MpConfigClose` at `0x18007c7ce`
- `MpClient!MpConfigClose` at `0x18007c837`
- `MpClient!MpConfigClose` at `0x18007c846`
- `MpClient!MpConfigOpen` at `0x18007c5c5`
- `MpClient!MpConfigOpen` at `0x18007c6ed`
- `MpClient!MpConfigOpen` at `0x18007c7aa`
- `MpClient!MpConfigOpen` at `0x18007c5c5`
- `MpClient!MpConfigOpen` at `0x18007c6ed`
- `MpClient!MpConfigOpen` at `0x18007c7aa`

## string_xrefs

- `0x18007c5be`: `Miscellaneous Configuration`
- `0x18007c6e6`: `Miscellaneous Configuration`
- `0x18007c68f`: `DlpEngineutils::ReadPasteToBrowserConfig:Call to GetPasteToBrowserConfigurationFromEngine() failed. HRESULT 0x%x`
- `0x18007c6b3`: `DlpEngineutils::ReadPasteToBrowserConfig(%d): PTB config fetch done. MinBufSize %d, WaitTime %d, FallbackMode %d, BlockModeTimeOut %d`
- `0x18007c663`: `DlpEngineutils::ReadPasteToBrowserConfig(%d):PasteToBrowserSigMisc %d, SyncClassificationCap %d, FeatureEnabled %d`

## pseudocode

```c
__int64 __fastcall RealtimeProtection::DlpEngineUtils::ReadPasteToBrowserConfig(
        RealtimeProtection::DlpEngineUtils *this,
        unsigned int *a2,
        unsigned int *a3,
        unsigned int *a4,
        unsigned int *a5)
{
  int PasteToBrowserSettingsFromEngine; // eax
  unsigned int *v10; // rdx
  const wchar_t *v11; // r9
  unsigned int ConfigDwordValue; // eax
  __int64 v13; // r8
  int PasteToBrowserConfigurationFromEngine; // eax
  int v15; // ebx
  __int64 v16; // rcx
  int v18; // eax
  enum tagMP_CONFIG_ORIGIN *v19; // [rsp+20h] [rbp-48h]
  __int64 v20; // [rsp+20h] [rbp-48h]
  __int64 v21; // [rsp+20h] [rbp-48h]
  unsigned int v22; // [rsp+30h] [rbp-38h] BYREF
  unsigned int v23; // [rsp+34h] [rbp-34h] BYREF
  __int64 v24; // [rsp+38h] [rbp-30h] BYREF
  int v25; // [rsp+40h] [rbp-28h] BYREF
  __int64 v26; // [rsp+48h] [rbp-20h] BYREF
  __int64 v27; // [rsp+50h] [rbp-18h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 140, &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids);
  v23 = 0;
  PasteToBrowserSettingsFromEngine = anonymous_namespace_::GetPasteToBrowserSettingsFromEngine(&v23);
  if ( PasteToBrowserSettingsFromEngine < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      141,
      &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
      (unsigned int)PasteToBrowserSettingsFromEngine);
  }
  v27 = 0;
  if ( (int)MpConfigOpen(L"Miscellaneous Configuration", &v27) >= 0 )
  {
    v22 = 0;
    if ( (int)MpConfigGetValueDword(v27, L"EnableBrowserPasteEnforcement", &v22, 0) >= 0 )
      v23 = v22;
  }
  v22 = 0;
  ConfigDwordValue = MpConfigUtils::GetConfigDwordValue((MpConfigUtils *)&v22, v10, L"SenseDlpJitEnabled", v11, v19);
  if ( ConfigDwordValue )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        142,
        &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
        ConfigDwordValue,
        v23);
    v13 = 0;
    v23 = 0;
  }
  else
  {
    v13 = v23;
  }
  *(_BYTE *)a5 = (_DWORD)v13 != 0;
  LODWORD(v20) = v13 != 0;
  RealtimeProtection::MpLogMessageImpl(
    (RealtimeProtection *)L"DlpEngineutils::ReadPasteToBrowserConfig(%d):PasteToBrowserSigMisc %d, SyncClassificationCap %"
                           "d, FeatureEnabled %d",
    (const wchar_t *)0x870,
    v13,
    v22,
    v20);
  if ( *(_BYTE *)a5 )
  {
    PasteToBrowserConfigurationFromEngine = anonymous_namespace_::GetPasteToBrowserConfigurationFromEngine(
                                              (unsigned int *)this,
                                              a2,
                                              a3,
                                              a4);
    if ( PasteToBrowserConfigurationFromEngine < 0 )
      RealtimeProtection::MpLogMessageImpl(
        (RealtimeProtection *)L"DlpEngineutils::ReadPasteToBrowserConfig:Call to GetPasteToBrowserConfigurationFromEngine("
                               ") failed. HRESULT 0x%x",
        (const wchar_t *)(unsigned int)PasteToBrowserConfigurationFromEngine);
    LODWORD(v21) = *a3;
    RealtimeProtection::MpLogMessageImpl(
      (RealtimeProtection *)L"DlpEngineutils::ReadPasteToBrowserConfig(%d): PTB config fetch done. MinBufSize %d, WaitTime"
                             " %d, FallbackMode %d, BlockModeTimeOut %d",
      (const wchar_t *)0x88F,
      *(unsigned int *)this,
      *a2,
      v21,
      *a4);
    v25 = 0;
    if ( (int)MpIsDevMode(&v25) >= 0 && v25 )
    {
      v24 = 0;
      if ( (int)MpConfigOpen(L"Miscellaneous Configuration", &v24) >= 0 )
      {
        v22 = 0;
        if ( (int)MpConfigGetValueDword(v24, L"MpDlp_PTBMinimumBufferSize", &v22, 0) >= 0 )
          *(_DWORD *)this = v22;
        v22 = 0;
        if ( (int)MpConfigGetValueDword(v24, L"MpDlp_PTBWaitTimeInSeconds", &v22, 0) >= 0 )
          *a2 = v22;
        v22 = 0;
        if ( (int)MpConfigGetValueDword(v24, L"MpDlp_PTBFallbackMode", &v22, 0) >= 0 )
          *a3 = v22;
        v22 = 0;
        if ( (int)MpConfigGetValueDword(v24, L"MpDlp_PTBBlockModeTimeoutInSeconds", &v22, 0) >= 0 )
          *a4 = v22;
      }
      if ( v24 )
        MpConfigClose();
    }
  }
  v26 = 0;
  v15 = MpConfigOpen(L"Features", &v26);
  v16 = v26;
  if ( v15 < 0 )
    goto LABEL_34;
  v18 = MpConfigSetValue(v26, L"DlpEnableBrowserPasteEnforcement", 1, 4, &v23);
  v15 = v18;
  if ( v18 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        143,
        &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
        (unsigned int)v18);
    v16 = v26;
LABEL_34:
    if ( v16 )
      MpConfigClose();
    if ( v27 )
      MpConfigClose();
    return (unsigned int)v15;
  }
  if ( v26 )
    MpConfigClose();
  if ( v27 )
    MpConfigClose();
  return 0;
}

```

## disassembly

```asm
0x18007c518  push    rbp
0x18007c51a  push    rbx
0x18007c51b  push    rsi
0x18007c51c  push    rdi
0x18007c51d  push    r12
0x18007c51f  push    r13
0x18007c521  push    r14
0x18007c523  push    r15
0x18007c525  mov     rbp, rsp
0x18007c528  sub     rsp, 68h
0x18007c52c  mov     rax, cs:__security_cookie
0x18007c533  xor     rax, rsp
0x18007c536  mov     [rbp+var_10], rax
0x18007c53a  mov     r14, r9
0x18007c53d  mov     rsi, r8
0x18007c540  mov     rdi, rdx
0x18007c543  mov     rbx, rcx
0x18007c546  mov     r15, [rbp+arg_20]
0x18007c54a  lea     r13, WPP_GLOBAL_Control
0x18007c551  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c558  cmp     rcx, r13
0x18007c55b  jz      short loc_18007C578
0x18007c55d  test    byte ptr [rcx+1Ch], 4
0x18007c561  jz      short loc_18007C578
0x18007c563  mov     edx, 8Ch
0x18007c568  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x18007c56f  mov     rcx, [rcx+10h]
0x18007c573  call    WPP_SF_
0x18007c578  xor     r12d, r12d
0x18007c57b  mov     [rbp+var_34], r12d
0x18007c57f  lea     rcx, [rbp+var_34]
0x18007c583  call    _anonymous_namespace___GetPasteToBrowserSettingsFromEngine
0x18007c588  test    eax, eax
0x18007c58a  jns     short loc_18007C5B6
0x18007c58c  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c593  cmp     rcx, r13
0x18007c596  jz      short loc_18007C5B6
0x18007c598  test    byte ptr [rcx+1Ch], 4
0x18007c59c  jz      short loc_18007C5B6
0x18007c59e  mov     edx, 8Dh
0x18007c5a3  mov     r9d, eax
0x18007c5a6  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x18007c5ad  mov     rcx, [rcx+10h]
0x18007c5b1  call    WPP_SF_d
0x18007c5b6  mov     [rbp+var_18], r12
0x18007c5ba  lea     rdx, [rbp+var_18]
0x18007c5be  lea     rcx, aMiscellaneousC_0; "Miscellaneous Configuration"
0x18007c5c5  call    cs:__imp_MpConfigOpen
0x18007c5cb  test    eax, eax
0x18007c5cd  js      short loc_18007C5F4
0x18007c5cf  mov     [rbp+var_38], r12d
0x18007c5d3  xor     r9d, r9d
0x18007c5d6  lea     r8, [rbp+var_38]
0x18007c5da  lea     rdx, aEnablebrowserp; "EnableBrowserPasteEnforcement"
0x18007c5e1  mov     rcx, [rbp+var_18]
0x18007c5e5  call    MpConfigGetValueDword
0x18007c5ea  test    eax, eax
0x18007c5ec  js      short loc_18007C5F4
0x18007c5ee  mov     eax, [rbp+var_38]
0x18007c5f1  mov     [rbp+var_34], eax
0x18007c5f4  mov     [rbp+var_38], r12d
0x18007c5f8  lea     r8, aSensedlpjitena; "SenseDlpJitEnabled"
0x18007c5ff  lea     rcx, [rbp+var_38]; this
0x18007c603  call    ?GetConfigDwordValue@MpConfigUtils@@YAJPEAKPEB_W1PEAW4tagMP_CONFIG_ORIGIN@@@Z; MpConfigUtils::GetConfigDwordValue(ulong *,wchar_t const *,wchar_t const *,tagMP_CONFIG_ORIGIN *)
0x18007c608  mov     r9d, eax
0x18007c60b  test    eax, eax
0x18007c60d  jz      short loc_18007C646
0x18007c60f  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c616  cmp     rcx, r13
0x18007c619  jz      short loc_18007C63D
0x18007c61b  test    byte ptr [rcx+1Ch], 2
0x18007c61f  jz      short loc_18007C63D
0x18007c621  mov     edx, 8Eh
0x18007c626  mov     eax, [rbp+var_34]
0x18007c629  mov     dword ptr [rsp+68h+var_48], eax
0x18007c62d  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x18007c634  mov     rcx, [rcx+10h]
0x18007c638  call    WPP_SF_Dd
0x18007c63d  mov     r8d, r12d
0x18007c640  mov     [rbp+var_34], r12d
0x18007c644  jmp     short loc_18007C64A
0x18007c646  mov     r8d, [rbp+var_34]
0x18007c64a  test    r8d, r8d
0x18007c64d  setnz   al
0x18007c650  mov     [r15], al
0x18007c653  movzx   eax, al
0x18007c656  mov     dword ptr [rsp+68h+var_48], eax
0x18007c65a  mov     r9d, [rbp+var_38]
0x18007c65e  mov     edx, 870h; wchar_t *
0x18007c663  lea     rcx, aDlpengineutils; "DlpEngineutils::ReadPasteToBrowserConfi"...
0x18007c66a  call    ?MpLogMessageImpl@RealtimeProtection@@YAJPEB_WZZ; RealtimeProtection::MpLogMessageImpl(wchar_t const *,...)
0x18007c66f  cmp     [r15], r12b
0x18007c672  jz      loc_18007C79B
0x18007c678  mov     r9, r14; unsigned int *
0x18007c67b  mov     r8, rsi; unsigned int *
0x18007c67e  mov     rdx, rdi; unsigned int *
0x18007c681  mov     rcx, rbx; unsigned int *
0x18007c684  call    _anonymous_namespace___GetPasteToBrowserConfigurationFromEngine
0x18007c689  test    eax, eax
0x18007c68b  jns     short loc_18007C69B
0x18007c68d  mov     edx, eax; wchar_t *
0x18007c68f  lea     rcx, aDlpengineutils_1; "DlpEngineutils::ReadPasteToBrowserConfi"...
0x18007c696  call    ?MpLogMessageImpl@RealtimeProtection@@YAJPEB_WZZ; RealtimeProtection::MpLogMessageImpl(wchar_t const *,...)
0x18007c69b  mov     eax, [r14]
0x18007c69e  mov     [rsp+68h+var_40], eax
0x18007c6a2  mov     eax, [rsi]
0x18007c6a4  mov     dword ptr [rsp+68h+var_48], eax
0x18007c6a8  mov     r9d, [rdi]
0x18007c6ab  mov     r8d, [rbx]
0x18007c6ae  mov     edx, 88Fh; wchar_t *
0x18007c6b3  lea     rcx, aDlpengineutils_0; "DlpEngineutils::ReadPasteToBrowserConfi"...
0x18007c6ba  call    ?MpLogMessageImpl@RealtimeProtection@@YAJPEB_WZZ; RealtimeProtection::MpLogMessageImpl(wchar_t const *,...)
0x18007c6bf  mov     [rbp+var_28], r12d
0x18007c6c3  lea     rcx, [rbp+var_28]
0x18007c6c7  call    MpIsDevMode
0x18007c6cc  test    eax, eax
0x18007c6ce  js      loc_18007C79B
0x18007c6d4  cmp     [rbp+var_28], r12d
0x18007c6d8  jz      loc_18007C79B
0x18007c6de  mov     [rbp+var_30], r12
0x18007c6e2  lea     rdx, [rbp+var_30]
0x18007c6e6  lea     rcx, aMiscellaneousC_0; "Miscellaneous Configuration"
0x18007c6ed  call    cs:__imp_MpConfigOpen
0x18007c6f3  test    eax, eax
0x18007c6f5  js      loc_18007C78C
0x18007c6fb  mov     [rbp+var_38], r12d
0x18007c6ff  xor     r9d, r9d
0x18007c702  lea     r8, [rbp+var_38]
0x18007c706  lea     rdx, aMpdlpPtbminimu; "MpDlp_PTBMinimumBufferSize"
0x18007c70d  mov     rcx, [rbp+var_30]
0x18007c711  call    MpConfigGetValueDword
0x18007c716  test    eax, eax
0x18007c718  js      short loc_18007C71F
0x18007c71a  mov     eax, [rbp+var_38]
0x18007c71d  mov     [rbx], eax
0x18007c71f  mov     [rbp+var_38], r12d
0x18007c723  xor     r9d, r9d
0x18007c726  lea     r8, [rbp+var_38]
0x18007c72a  lea     rdx, aMpdlpPtbwaitti; "MpDlp_PTBWaitTimeInSeconds"
0x18007c731  mov     rcx, [rbp+var_30]
0x18007c735  call    MpConfigGetValueDword
0x18007c73a  test    eax, eax
0x18007c73c  js      short loc_18007C743
0x18007c73e  mov     eax, [rbp+var_38]
0x18007c741  mov     [rdi], eax
0x18007c743  mov     [rbp+var_38], r12d
0x18007c747  xor     r9d, r9d
0x18007c74a  lea     r8, [rbp+var_38]
0x18007c74e  lea     rdx, aMpdlpPtbfallba; "MpDlp_PTBFallbackMode"
0x18007c755  mov     rcx, [rbp+var_30]
0x18007c759  call    MpConfigGetValueDword
0x18007c75e  test    eax, eax
0x18007c760  js      short loc_18007C767
0x18007c762  mov     eax, [rbp+var_38]
0x18007c765  mov     [rsi], eax
0x18007c767  mov     [rbp+var_38], r12d
0x18007c76b  xor     r9d, r9d
0x18007c76e  lea     r8, [rbp+var_38]
0x18007c772  lea     rdx, aMpdlpPtbblockm; "MpDlp_PTBBlockModeTimeoutInSeconds"
0x18007c779  mov     rcx, [rbp+var_30]
0x18007c77d  call    MpConfigGetValueDword
0x18007c782  test    eax, eax
0x18007c784  js      short loc_18007C78C
0x18007c786  mov     eax, [rbp+var_38]
0x18007c789  mov     [r14], eax
0x18007c78c  mov     rcx, [rbp+var_30]
0x18007c790  test    rcx, rcx
0x18007c793  jz      short loc_18007C79B
0x18007c795  call    cs:__imp_MpConfigClose
0x18007c79b  mov     [rbp+var_20], r12
0x18007c79f  lea     rdx, [rbp+var_20]
0x18007c7a3  lea     rcx, aFeatures_0; "Features"
0x18007c7aa  call    cs:__imp_MpConfigOpen
0x18007c7b0  mov     ebx, eax
0x18007c7b2  mov     rcx, [rbp+var_20]
0x18007c7b6  test    eax, eax
0x18007c7b8  jns     short loc_18007C7D8
0x18007c7ba  test    rcx, rcx
0x18007c7bd  jz      short loc_18007C7C5
0x18007c7bf  call    cs:__imp_MpConfigClose
0x18007c7c5  mov     rcx, [rbp+var_18]
0x18007c7c9  test    rcx, rcx
0x18007c7cc  jz      short loc_18007C7D4
0x18007c7ce  call    cs:__imp_MpConfigClose
0x18007c7d4  mov     eax, ebx
0x18007c7d6  jmp     short loc_18007C84E
0x18007c7d8  lea     rax, [rbp+var_34]
0x18007c7dc  mov     [rsp+68h+var_48], rax
0x18007c7e1  mov     r9d, 4
0x18007c7e7  lea     r8d, [r9-3]
0x18007c7eb  lea     rdx, aDlpenablebrows; "DlpEnableBrowserPasteEnforcement"
0x18007c7f2  call    cs:__imp_MpConfigSetValue
0x18007c7f8  mov     ebx, eax
0x18007c7fa  test    eax, eax
0x18007c7fc  jns     short loc_18007C82E
0x18007c7fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c805  cmp     rcx, r13
0x18007c808  jz      short loc_18007C828
0x18007c80a  test    byte ptr [rcx+1Ch], 1
0x18007c80e  jz      short loc_18007C828
0x18007c810  mov     edx, 8Fh
0x18007c815  mov     r9d, eax
0x18007c818  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x18007c81f  mov     rcx, [rcx+10h]
0x18007c823  call    WPP_SF_d
0x18007c828  mov     rcx, [rbp+var_20]
0x18007c82c  jmp     short loc_18007C7BA
0x18007c82e  mov     rcx, [rbp+var_20]
0x18007c832  test    rcx, rcx
0x18007c835  jz      short loc_18007C83D
0x18007c837  call    cs:__imp_MpConfigClose
0x18007c83d  mov     rcx, [rbp+var_18]
0x18007c841  test    rcx, rcx
0x18007c844  jz      short loc_18007C84C
0x18007c846  call    cs:__imp_MpConfigClose
0x18007c84c  xor     eax, eax
0x18007c84e  mov     rcx, [rbp+var_10]
0x18007c852  xor     rcx, rsp; StackCookie
0x18007c855  call    __security_check_cookie
0x18007c85a  add     rsp, 68h
0x18007c85e  pop     r15
0x18007c860  pop     r14
0x18007c862  pop     r13
0x18007c864  pop     r12
0x18007c866  pop     rdi
0x18007c867  pop     rsi
0x18007c868  pop     rbx
0x18007c869  pop     rbp
0x18007c86a  retn
```
