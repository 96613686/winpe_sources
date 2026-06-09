# RealtimeProtection::DlpEngineUtils::DlpSetNumberOfThreadsForKernelMessageUnSafe(void)

- ea: `0x18007ac50`
- end: `0x18007aeba`
- name: `?DlpSetNumberOfThreadsForKernelMessageUnSafe@DlpEngineUtils@RealtimeProtection@@YAJXZ`
- size: `618`
- prototype: `__int64 __fastcall(RealtimeProtection::DlpEngineUtils *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x18007c380`

## callees

- `0x180046d10`
- `0x18007ac50`
- `0x18007aebc`
- `0x18007af18`
- `0x1800809d0`
- `0x1800bb4ec`
- `0x18010cb40`

## import_xrefs

- `MpClient!MpConfigSetValue` at `0x18007acd4`
- `MpClient!MpConfigSetValue` at `0x18007ad65`
- `MpClient!MpConfigSetValue` at `0x18007ade1`
- `MpClient!MpConfigSetValue` at `0x18007acd4`
- `MpClient!MpConfigSetValue` at `0x18007ad65`
- `MpClient!MpConfigSetValue` at `0x18007ade1`
- `MpClient!MpConfigClose` at `0x18007ae96`
- `MpClient!MpConfigClose` at `0x18007ae96`
- `MpClient!MpConfigOpen` at `0x18007aca8`
- `MpClient!MpConfigOpen` at `0x18007aca8`

## string_xrefs

- `0x18007ad5a`: `DlpAsyncThreadNumberFactorInPercent`
- `0x18007add6`: `DlpSyncThreadNumberFactorInPercent`

## pseudocode

```c
__int64 __fastcall RealtimeProtection::DlpEngineUtils::DlpSetNumberOfThreadsForKernelMessageUnSafe(
        RealtimeProtection::DlpEngineUtils *this,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  int v11; // eax
  int v12; // eax
  int v13; // eax
  unsigned int IsDlpKernelPortFeatureDisabled; // [rsp+40h] [rbp-20h] BYREF
  unsigned int v16; // [rsp+44h] [rbp-1Ch] BYREF
  unsigned int FcValue; // [rsp+48h] [rbp-18h] BYREF
  __int64 v18; // [rsp+50h] [rbp-10h] BYREF

  FcValue = RealtimeProtection::DlpPlugin::GetFcValue(55, a2, a3, a4);
  v16 = RealtimeProtection::DlpPlugin::GetFcValue(56, v4, v5, v6);
  IsDlpKernelPortFeatureDisabled = (unsigned __int8)anonymous_namespace_::IsDlpKernelPortFeatureDisabled();
  v18 = 0;
  v7 = MpConfigOpen(L"Features", &v18);
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_LLLd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        178,
        &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
        FcValue,
        v16,
        IsDlpKernelPortFeatureDisabled,
        v7);
  }
  else
  {
    v11 = MpConfigSetValue(v18, L"DlpDisableKernelPort", 1, 4, &IsDlpKernelPortFeatureDisabled);
    if ( v11 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          173,
          &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
          IsDlpKernelPortFeatureDisabled,
          v11);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        172,
        &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
        IsDlpKernelPortFeatureDisabled);
    }
    v12 = MpConfigSetValue(v18, L"DlpAsyncThreadNumberFactorInPercent", 1, 4, &FcValue);
    if ( v12 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          175,
          &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
          FcValue,
          v12);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 174, &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids, FcValue);
    }
    v13 = MpConfigSetValue(v18, L"DlpSyncThreadNumberFactorInPercent", 1, 4, &v16);
    if ( v13 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 177, &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids, v16, v13);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 176, &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids, v16);
    }
  }
  if ( v18 )
    MpConfigClose(v18, v8, v9, v10);
  return 0;
}

```

## disassembly

```asm
0x18007ac50  mov     [rsp-8+arg_0], rbx
0x18007ac55  mov     [rsp-8+arg_8], rsi
0x18007ac5a  push    rbp
0x18007ac5b  mov     rbp, rsp
0x18007ac5e  sub     rsp, 60h
0x18007ac62  mov     rax, cs:__security_cookie
0x18007ac69  xor     rax, rsp
0x18007ac6c  mov     [rbp+var_8], rax
0x18007ac70  mov     ecx, 37h ; '7'
0x18007ac75  call    ?GetFcValue@DlpPlugin@RealtimeProtection@@YAKW4FeatureControlEnum@@@Z; RealtimeProtection::DlpPlugin::GetFcValue(FeatureControlEnum)
0x18007ac7a  mov     ecx, 38h ; '8'
0x18007ac7f  mov     [rbp+var_18], eax
0x18007ac82  call    ?GetFcValue@DlpPlugin@RealtimeProtection@@YAKW4FeatureControlEnum@@@Z; RealtimeProtection::DlpPlugin::GetFcValue(FeatureControlEnum)
0x18007ac87  mov     [rbp+var_1C], eax
0x18007ac8a  call    _anonymous_namespace___IsDlpKernelPortFeatureDisabled
0x18007ac8f  movzx   eax, al
0x18007ac92  lea     rdx, [rbp+var_10]
0x18007ac96  lea     rcx, aFeatures_0; "Features"
0x18007ac9d  mov     [rbp+var_20], eax
0x18007aca0  mov     [rbp+var_10], 0
0x18007aca8  call    cs:__imp_MpConfigOpen
0x18007acae  test    eax, eax
0x18007acb0  js      loc_18007AE49
0x18007acb6  mov     rcx, [rbp+var_10]
0x18007acba  lea     rax, [rbp+var_20]
0x18007acbe  mov     r9d, 4
0x18007acc4  mov     [rsp+60h+var_40], rax
0x18007acc9  lea     rdx, aDlpdisablekern; "DlpDisableKernelPort"
0x18007acd0  lea     r8d, [r9-3]
0x18007acd4  call    cs:__imp_MpConfigSetValue
0x18007acda  lea     rsi, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x18007ace1  test    eax, eax
0x18007ace3  js      short loc_18007AD15
0x18007ace5  mov     rcx, cs:WPP_GLOBAL_Control
0x18007acec  lea     rbx, WPP_GLOBAL_Control
0x18007acf3  cmp     rcx, rbx
0x18007acf6  jz      short loc_18007AD47
0x18007acf8  test    byte ptr [rcx+1Ch], 4
0x18007acfc  jz      short loc_18007AD47
0x18007acfe  mov     r9d, [rbp+var_20]
0x18007ad02  mov     edx, 0ACh
0x18007ad07  mov     rcx, [rcx+10h]
0x18007ad0b  mov     r8, rsi
0x18007ad0e  call    WPP_SF_d
0x18007ad13  jmp     short loc_18007AD47
0x18007ad15  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ad1c  lea     rbx, WPP_GLOBAL_Control
0x18007ad23  cmp     rcx, rbx
0x18007ad26  jz      short loc_18007AD47
0x18007ad28  test    byte ptr [rcx+1Ch], 1
0x18007ad2c  jz      short loc_18007AD47
0x18007ad2e  mov     r9d, [rbp+var_20]
0x18007ad32  mov     edx, 0ADh
0x18007ad37  mov     rcx, [rcx+10h]
0x18007ad3b  mov     r8, rsi
0x18007ad3e  mov     dword ptr [rsp+60h+var_40], eax
0x18007ad42  call    WPP_SF_Dd
0x18007ad47  mov     rcx, [rbp+var_10]
0x18007ad4b  lea     rax, [rbp+var_18]
0x18007ad4f  mov     r9d, 4
0x18007ad55  mov     [rsp+60h+var_40], rax
0x18007ad5a  lea     rdx, aDlpasyncthread; "DlpAsyncThreadNumberFactorInPercent"
0x18007ad61  lea     r8d, [r9-3]
0x18007ad65  call    cs:__imp_MpConfigSetValue
0x18007ad6b  test    eax, eax
0x18007ad6d  js      short loc_18007AD98
0x18007ad6f  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ad76  cmp     rcx, rbx
0x18007ad79  jz      short loc_18007ADC3
0x18007ad7b  test    byte ptr [rcx+1Ch], 4
0x18007ad7f  jz      short loc_18007ADC3
0x18007ad81  mov     r9d, [rbp+var_18]
0x18007ad85  mov     edx, 0AEh
0x18007ad8a  mov     rcx, [rcx+10h]
0x18007ad8e  mov     r8, rsi
0x18007ad91  call    WPP_SF_d
0x18007ad96  jmp     short loc_18007ADC3
0x18007ad98  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ad9f  cmp     rcx, rbx
0x18007ada2  jz      short loc_18007ADC3
0x18007ada4  test    byte ptr [rcx+1Ch], 1
0x18007ada8  jz      short loc_18007ADC3
0x18007adaa  mov     r9d, [rbp+var_18]
0x18007adae  mov     edx, 0AFh
0x18007adb3  mov     rcx, [rcx+10h]
0x18007adb7  mov     r8, rsi
0x18007adba  mov     dword ptr [rsp+60h+var_40], eax
0x18007adbe  call    WPP_SF_Dd
0x18007adc3  mov     rcx, [rbp+var_10]
0x18007adc7  lea     rax, [rbp+var_1C]
0x18007adcb  mov     r9d, 4
0x18007add1  mov     [rsp+60h+var_40], rax
0x18007add6  lea     rdx, aDlpsyncthreadn; "DlpSyncThreadNumberFactorInPercent"
0x18007addd  lea     r8d, [r9-3]
0x18007ade1  call    cs:__imp_MpConfigSetValue
0x18007ade7  test    eax, eax
0x18007ade9  js      short loc_18007AE1C
0x18007adeb  mov     rcx, cs:WPP_GLOBAL_Control
0x18007adf2  cmp     rcx, rbx
0x18007adf5  jz      loc_18007AE8D
0x18007adfb  test    byte ptr [rcx+1Ch], 4
0x18007adff  jz      loc_18007AE8D
0x18007ae05  mov     r9d, [rbp+var_1C]
0x18007ae09  mov     edx, 0B0h
0x18007ae0e  mov     rcx, [rcx+10h]
0x18007ae12  mov     r8, rsi
0x18007ae15  call    WPP_SF_d
0x18007ae1a  jmp     short loc_18007AE8D
0x18007ae1c  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ae23  cmp     rcx, rbx
0x18007ae26  jz      short loc_18007AE8D
0x18007ae28  test    byte ptr [rcx+1Ch], 1
0x18007ae2c  jz      short loc_18007AE8D
0x18007ae2e  mov     r9d, [rbp+var_1C]
0x18007ae32  mov     edx, 0B1h
0x18007ae37  mov     rcx, [rcx+10h]
0x18007ae3b  mov     r8, rsi
0x18007ae3e  mov     dword ptr [rsp+60h+var_40], eax
0x18007ae42  call    WPP_SF_Dd
0x18007ae47  jmp     short loc_18007AE8D
0x18007ae49  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ae50  lea     rbx, WPP_GLOBAL_Control
0x18007ae57  cmp     rcx, rbx
0x18007ae5a  jz      short loc_18007AE8D
0x18007ae5c  test    byte ptr [rcx+1Ch], 1
0x18007ae60  jz      short loc_18007AE8D
0x18007ae62  mov     r9d, [rbp+var_18]
0x18007ae66  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x18007ae6d  mov     rcx, [rcx+10h]
0x18007ae71  mov     edx, 0B2h
0x18007ae76  mov     [rsp+60h+var_30], eax
0x18007ae7a  mov     eax, [rbp+var_20]
0x18007ae7d  mov     [rsp+60h+var_38], eax
0x18007ae81  mov     eax, [rbp+var_1C]
0x18007ae84  mov     dword ptr [rsp+60h+var_40], eax
0x18007ae88  call    WPP_SF_LLLd
0x18007ae8d  mov     rcx, [rbp+var_10]
0x18007ae91  test    rcx, rcx
0x18007ae94  jz      short loc_18007AE9C
0x18007ae96  call    cs:__imp_MpConfigClose
0x18007ae9c  xor     eax, eax
0x18007ae9e  mov     rcx, [rbp+var_8]
0x18007aea2  xor     rcx, rsp; StackCookie
0x18007aea5  call    __security_check_cookie
0x18007aeaa  mov     rbx, [rsp+60h+arg_0]
0x18007aeaf  mov     rsi, [rsp+60h+arg_8]
0x18007aeb4  add     rsp, 60h
0x18007aeb8  pop     rbp
0x18007aeb9  retn
```
