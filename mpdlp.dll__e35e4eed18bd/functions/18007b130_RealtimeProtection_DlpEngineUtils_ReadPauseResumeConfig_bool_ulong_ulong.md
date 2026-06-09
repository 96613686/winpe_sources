# RealtimeProtection::DlpEngineUtils::ReadPauseResumeConfig(bool &,ulong &,ulong &)

- ea: `0x18007b130`
- end: `0x18007b333`
- name: `?ReadPauseResumeConfig@DlpEngineUtils@RealtimeProtection@@YAJAEA_NAEAK1@Z`
- size: `515`
- prototype: `__int64 __fastcall(RealtimeProtection::DlpEngineUtils *__hidden this, bool *, unsigned int *, unsigned int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18007a790`
- `0x18019d7f8`

## callees

- `0x180079dc0`
- `0x18007aebc`
- `0x18007b130`
- `0x1800809d0`
- `0x180089510`
- `0x18010cb40`

## import_xrefs

- `MpClient!MpConfigSetValue` at `0x18007b214`
- `MpClient!MpConfigSetValue` at `0x18007b26e`
- `MpClient!MpConfigSetValue` at `0x18007b2b1`
- `MpClient!MpConfigSetValue` at `0x18007b214`
- `MpClient!MpConfigSetValue` at `0x18007b26e`
- `MpClient!MpConfigSetValue` at `0x18007b2b1`
- `MpClient!MpConfigClose` at `0x18007b1ed`
- `MpClient!MpConfigClose` at `0x18007b30b`
- `MpClient!MpConfigClose` at `0x18007b1ed`
- `MpClient!MpConfigClose` at `0x18007b30b`
- `MpClient!MpConfigOpen` at `0x18007b1d8`
- `MpClient!MpConfigOpen` at `0x18007b1d8`

## string_xrefs

- `0x18007b1b9`: `DLP::ReadPauseResumeConfig:  GetFcValues done. PauseResumeSetting %lx, PauseResumeWaitTime %lx, PauseResumeActionType %lx`
- `0x18007b2f6`: `DLP::ReadPauseResumeConfig: Exiting... Features reg key set for PauseResumeSetting %d, PauseResumeWaitTime %d`

## pseudocode

```c
__int64 __fastcall RealtimeProtection::DlpEngineUtils::ReadPauseResumeConfig(
        RealtimeProtection::DlpEngineUtils *this,
        bool *a2,
        unsigned int *a3,
        unsigned int *a4)
{
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rdx
  int v14; // ebx
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // rcx
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 v24; // [rsp+30h] [rbp-20h] BYREF
  unsigned int FcValue; // [rsp+38h] [rbp-18h] BYREF
  unsigned int v26; // [rsp+3Ch] [rbp-14h] BYREF
  unsigned int v27; // [rsp+40h] [rbp-10h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 155, &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids);
  FcValue = RealtimeProtection::DlpPlugin::GetFcValue(81, a2, a3, a4);
  v26 = RealtimeProtection::DlpPlugin::GetFcValue(82, v7, v8, v9);
  v27 = RealtimeProtection::DlpPlugin::GetFcValue(129, v10, v11, v12);
  RealtimeProtection::MpLogMessageImpl(
    (RealtimeProtection *)L"DLP::ReadPauseResumeConfig:  GetFcValues done. PauseResumeSetting %lx, PauseResumeWaitTime %lx"
                           ", PauseResumeActionType %lx",
    (const wchar_t *)FcValue,
    v26,
    v27);
  v24 = 0;
  v14 = MpConfigOpen(L"Features", &v24);
  v17 = v24;
  if ( v14 < 0 )
    goto LABEL_5;
  v14 = MpConfigSetValue(v24, L"MpFC_Dlp_PauseResume_Enable", 1, 4, &FcValue);
  if ( v14 < 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_13;
    v20 = 156;
LABEL_12:
    WPP_SF_d(v19[2], v20, &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids, (unsigned int)v14);
LABEL_13:
    v17 = v24;
LABEL_5:
    if ( v17 )
      MpConfigClose(v17, v13, v15, v16);
    return (unsigned int)v14;
  }
  v14 = MpConfigSetValue(v24, L"MpFC_Dlp_PauseResume_WaitTime", 1, 4, &v26);
  if ( v14 < 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_13;
    v20 = 157;
    goto LABEL_12;
  }
  v14 = MpConfigSetValue(v24, L"MpFC_Dlp_PauseResume_ActionType", 1, 4, &v27);
  if ( v14 < 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_13;
    v20 = 158;
    goto LABEL_12;
  }
  *(_BYTE *)this = FcValue != 0;
  *a3 = v27;
  *(_DWORD *)a2 = v26;
  RealtimeProtection::MpLogMessageImpl(
    (RealtimeProtection *)L"DLP::ReadPauseResumeConfig: Exiting... Features reg key set for PauseResumeSetting %d, PauseResumeWaitTime %d",
    (const wchar_t *)*(unsigned __int8 *)this);
  if ( v24 )
    MpConfigClose(v24, v21, v22, v23);
  return 0;
}

```

## disassembly

```asm
0x18007b130  mov     [rsp-28h+arg_18], rbx
0x18007b135  push    rbp
0x18007b136  push    rsi
0x18007b137  push    rdi
0x18007b138  push    r12
0x18007b13a  push    r14
0x18007b13c  mov     rbp, rsp
0x18007b13f  sub     rsp, 50h
0x18007b143  mov     rax, cs:__security_cookie
0x18007b14a  xor     rax, rsp
0x18007b14d  mov     [rbp+var_8], rax
0x18007b151  mov     r14, r8
0x18007b154  mov     rsi, rdx
0x18007b157  mov     rdi, rcx
0x18007b15a  lea     r12, WPP_GLOBAL_Control
0x18007b161  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b168  cmp     rcx, r12
0x18007b16b  jz      short loc_18007B188
0x18007b16d  test    byte ptr [rcx+1Ch], 4
0x18007b171  jz      short loc_18007B188
0x18007b173  mov     edx, 9Bh
0x18007b178  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x18007b17f  mov     rcx, [rcx+10h]
0x18007b183  call    WPP_SF_
0x18007b188  mov     ecx, 51h ; 'Q'
0x18007b18d  call    ?GetFcValue@DlpPlugin@RealtimeProtection@@YAKW4FeatureControlEnum@@@Z; RealtimeProtection::DlpPlugin::GetFcValue(FeatureControlEnum)
0x18007b192  mov     dword ptr [rbp+var_18], eax
0x18007b195  mov     ecx, 52h ; 'R'
0x18007b19a  call    ?GetFcValue@DlpPlugin@RealtimeProtection@@YAKW4FeatureControlEnum@@@Z; RealtimeProtection::DlpPlugin::GetFcValue(FeatureControlEnum)
0x18007b19f  mov     dword ptr [rbp+var_18+4], eax
0x18007b1a2  mov     ecx, 81h
0x18007b1a7  call    ?GetFcValue@DlpPlugin@RealtimeProtection@@YAKW4FeatureControlEnum@@@Z; RealtimeProtection::DlpPlugin::GetFcValue(FeatureControlEnum)
0x18007b1ac  mov     [rbp+var_10], eax
0x18007b1af  mov     r9d, eax
0x18007b1b2  mov     r8d, dword ptr [rbp+var_18+4]
0x18007b1b6  mov     edx, dword ptr [rbp+var_18]; wchar_t *
0x18007b1b9  lea     rcx, aDlpReadpausere_0; "DLP::ReadPauseResumeConfig:  GetFcValue"...
0x18007b1c0  call    ?MpLogMessageImpl@RealtimeProtection@@YAJPEB_WZZ; RealtimeProtection::MpLogMessageImpl(wchar_t const *,...)
0x18007b1c5  mov     [rbp+var_20], 0
0x18007b1cd  lea     rdx, [rbp+var_20]
0x18007b1d1  lea     rcx, aFeatures_0; "Features"
0x18007b1d8  call    cs:__imp_MpConfigOpen
0x18007b1de  mov     ebx, eax
0x18007b1e0  mov     rcx, [rbp+var_20]
0x18007b1e4  test    eax, eax
0x18007b1e6  jns     short loc_18007B1FA
0x18007b1e8  test    rcx, rcx
0x18007b1eb  jz      short loc_18007B1F3
0x18007b1ed  call    cs:__imp_MpConfigClose
0x18007b1f3  mov     eax, ebx
0x18007b1f5  jmp     loc_18007B313
0x18007b1fa  lea     rax, [rbp+var_18]
0x18007b1fe  mov     [rsp+50h+var_30], rax
0x18007b203  mov     r9d, 4
0x18007b209  lea     r8d, [r9-3]
0x18007b20d  lea     rdx, aMpfcDlpPausere_0; "MpFC_Dlp_PauseResume_Enable"
0x18007b214  call    cs:__imp_MpConfigSetValue
0x18007b21a  mov     ebx, eax
0x18007b21c  test    eax, eax
0x18007b21e  jns     short loc_18007B250
0x18007b220  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b227  cmp     rcx, r12
0x18007b22a  jz      short loc_18007B24A
0x18007b22c  test    byte ptr [rcx+1Ch], 1
0x18007b230  jz      short loc_18007B24A
0x18007b232  mov     edx, 9Ch
0x18007b237  mov     r9d, ebx
0x18007b23a  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x18007b241  mov     rcx, [rcx+10h]
0x18007b245  call    WPP_SF_d
0x18007b24a  mov     rcx, [rbp+var_20]
0x18007b24e  jmp     short loc_18007B1E8
0x18007b250  lea     rax, [rbp+var_18+4]
0x18007b254  mov     [rsp+50h+var_30], rax
0x18007b259  mov     r9d, 4
0x18007b25f  lea     r8d, [r9-3]
0x18007b263  lea     rdx, aMpfcDlpPausere_1; "MpFC_Dlp_PauseResume_WaitTime"
0x18007b26a  mov     rcx, [rbp+var_20]
0x18007b26e  call    cs:__imp_MpConfigSetValue
0x18007b274  mov     ebx, eax
0x18007b276  test    eax, eax
0x18007b278  jns     short loc_18007B293
0x18007b27a  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b281  cmp     rcx, r12
0x18007b284  jz      short loc_18007B24A
0x18007b286  test    byte ptr [rcx+1Ch], 1
0x18007b28a  jz      short loc_18007B24A
0x18007b28c  mov     edx, 9Dh
0x18007b291  jmp     short loc_18007B237
0x18007b293  lea     rax, [rbp+var_10]
0x18007b297  mov     [rsp+50h+var_30], rax
0x18007b29c  mov     r9d, 4
0x18007b2a2  lea     r8d, [r9-3]
0x18007b2a6  lea     rdx, aMpfcDlpPausere; "MpFC_Dlp_PauseResume_ActionType"
0x18007b2ad  mov     rcx, [rbp+var_20]
0x18007b2b1  call    cs:__imp_MpConfigSetValue
0x18007b2b7  mov     ebx, eax
0x18007b2b9  test    eax, eax
0x18007b2bb  jns     short loc_18007B2DD
0x18007b2bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b2c4  cmp     rcx, r12
0x18007b2c7  jz      short loc_18007B24A
0x18007b2c9  test    byte ptr [rcx+1Ch], 1
0x18007b2cd  jz      loc_18007B24A
0x18007b2d3  mov     edx, 9Eh
0x18007b2d8  jmp     loc_18007B237
0x18007b2dd  cmp     dword ptr [rbp+var_18], 0
0x18007b2e1  setnz   al
0x18007b2e4  mov     [rdi], al
0x18007b2e6  mov     eax, [rbp+var_10]
0x18007b2e9  mov     [r14], eax
0x18007b2ec  mov     r8d, dword ptr [rbp+var_18+4]
0x18007b2f0  mov     [rsi], r8d
0x18007b2f3  movzx   edx, byte ptr [rdi]; wchar_t *
0x18007b2f6  lea     rcx, aDlpReadpausere; "DLP::ReadPauseResumeConfig: Exiting... "...
0x18007b2fd  call    ?MpLogMessageImpl@RealtimeProtection@@YAJPEB_WZZ; RealtimeProtection::MpLogMessageImpl(wchar_t const *,...)
0x18007b302  mov     rcx, [rbp+var_20]
0x18007b306  test    rcx, rcx
0x18007b309  jz      short loc_18007B311
0x18007b30b  call    cs:__imp_MpConfigClose
0x18007b311  xor     eax, eax
0x18007b313  mov     rcx, [rbp+var_8]
0x18007b317  xor     rcx, rsp; StackCookie
0x18007b31a  call    __security_check_cookie
0x18007b31f  mov     rbx, [rsp+50h+arg_18]
0x18007b327  add     rsp, 50h
0x18007b32b  pop     r14
0x18007b32d  pop     r12
0x18007b32f  pop     rdi
0x18007b330  pop     rsi
0x18007b331  pop     rbp
0x18007b332  retn
```
