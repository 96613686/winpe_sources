# I_BCryptIsoLaunchKeyGuard

- ea: `0x18002831c`
- end: `0x1800289d3`
- name: `I_BCryptIsoLaunchKeyGuard`
- size: `1719`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `20`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800167fc`
- `0x18003ac40`

## callees

- `0x18000af80`
- `0x18001a1c0`
- `0x18001b4a0`
- `0x18001b634`
- `0x18001eb88`
- `0x1800248ac`
- `0x18002490c`
- `0x180024cd4`
- `0x18002831c`
- `0x180028a70`
- `0x1800358ec`
- `0x180035a04`
- `0x180036150`
- `0x180038970`
- `0x180039b04`
- `0x18003c1e0`
- `0x18003c304`
- `0x18003ed94`
- `0x18003f57c`
- `0x180062310`

## import_xrefs

- `ntdll!NtWaitForSingleObject` at `0x180028713`
- `ntdll!NtWaitForSingleObject` at `0x180028713`
- `ntdll!NtCreateEvent` at `0x180028547`
- `ntdll!NtCreateEvent` at `0x180028547`
- `ntdll!NtClose` at `0x180028982`
- `ntdll!NtClose` at `0x180028982`
- `ntdll!RtlInitUnicodeString` at `0x180028503`
- `ntdll!RtlInitUnicodeString` at `0x180028503`
- `ntdll!RtlDllShutdownInProgress` at `0x180028850`
- `ntdll!RtlDllShutdownInProgress` at `0x180028850`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028589`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028915`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028951`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028589`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028915`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028951`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180028905`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180028905`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028941`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028941`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800283af`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180028835`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800283af`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180028835`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180028579`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180028579`

## string_xrefs

- `0x18002846b`: `onecore\ds\security\cryptoapi\ncrypt\ium\lib\bcryptisotrustlet.cpp`
- `0x18002859b`: `onecore\ds\security\cryptoapi\ncrypt\ium\lib\bcryptisotrustlet.cpp`
- `0x180028927`: `onecore\ds\security\cryptoapi\ncrypt\ium\lib\bcryptisotrustlet.cpp`
- `0x180028963`: `onecore\ds\security\cryptoapi\ncrypt\ium\lib\bcryptisotrustlet.cpp`
- `0x180028998`: `onecore\ds\security\cryptoapi\ncrypt\ium\lib\bcryptisotrustlet.cpp`
- `0x180028572`: `%SystemRoot%\system32\lsaiso.exe`
- `0x1800284f8`: `\LSA_ISO_READY_LAUNCHED_AFTER_BOOT`

## pseudocode

```c
__int64 I_BCryptIsoLaunchKeyGuard()
{
  int v0; // r14d
  int v1; // r12d
  int CanLaunchSecureProcess; // esi
  int v3; // r13d
  ULONGLONG TickCount64; // rax
  ULONGLONG v5; // rbx
  unsigned int DwordFromRegistry; // ecx
  int v7; // eax
  __int64 v8; // r9
  DWORD LastError; // ebx
  __int64 v10; // rcx
  unsigned int v11; // edi
  __int64 v12; // r8
  NTSTATUS v13; // eax
  bool v14; // zf
  __int64 v15; // r8
  __int64 v16; // rax
  int v17; // eax
  int v18; // eax
  __int64 v19; // r8
  __int64 v20; // r9
  int v21; // ecx
  int v22; // r8d
  DWORD v23; // eax
  DWORD v24; // eax
  NTSTATUS v25; // eax
  int KGRunningInProdMode; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hProcess; // [rsp+48h] [rbp-B8h] BYREF
  int v29[2]; // [rsp+50h] [rbp-B0h] BYREF
  union _LARGE_INTEGER Timeout; // [rsp+58h] [rbp-A8h] BYREF
  void *EventHandle; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v32; // [rsp+68h] [rbp-98h] BYREF
  __int64 v33; // [rsp+70h] [rbp-90h] BYREF
  __int64 v34; // [rsp+78h] [rbp-88h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-80h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-70h] BYREF
  WCHAR Dst[264]; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t Buffer[264]; // [rsp+2D0h] [rbp+1D0h] BYREF

  hProcess = 0;
  EventHandle = 0;
  Timeout.QuadPart = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  memset_0(Dst, 0, 0x208u);
  memset_0(Buffer, 0, 0x208u);
  v0 = 0;
  v29[0] = 0;
  KGRunningInProdMode = 0;
  v1 = 0;
  CanLaunchSecureProcess = I_BCryptIsoCanLaunchSecureProcess();
  v3 = 0;
  TickCount64 = GetTickCount64();
  if ( dword_18007A110 )
  {
    v5 = TickCount64 - qword_18007A108;
    DwordFromRegistry = I_BCryptIsoReadDwordFromRegistry(
                          L"SYSTEM\\CurrentControlSet\\Control\\DeviceGuard\\Scenarios\\KeyGuard",
                          L"NoLaunchTimeoutSeconds");
    if ( !DwordFromRegistry )
      DwordFromRegistry = 5;
    if ( v5 / 0x3E8 < DwordFromRegistry )
    {
      v7 = dword_18007A110;
    }
    else
    {
      v7 = 0;
      dword_18007A110 = 0;
    }
    if ( v7 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_a6b47fe3e7aa3dc67b817b99b29667f9_Traceguids);
      v8 = 532;
      goto LABEL_12;
    }
  }
  BCryptIsoReadProcessModeFromRegistry(v29, &KGRunningInProdMode);
  v0 = v29[0];
  v11 = KGRunningInProdMode;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_KG_Skip_Launch_Without_VBS>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_KG_Skip_Launch_Without_VBS>::GetImpl'::`2'::impl)
    && v11
    && !CanLaunchSecureProcess )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, v12, v11, 0);
    v3 = 1;
LABEL_59:
    LastError = -1073741823;
    goto LABEL_60;
  }
  RtlInitUnicodeString(&DestinationString, L"\\LSA_ISO_READY_LAUNCHED_AFTER_BOOT");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 0;
  I_BCryptIsoStopProcess();
  v13 = NtCreateEvent(&EventHandle, 0x1F0003u, &ObjectAttributes, NotificationEvent, 0);
  LastError = v13;
  if ( v13 < 0 )
  {
    v8 = 575;
LABEL_23:
    v10 = (unsigned int)v13;
    goto LABEL_13;
  }
  if ( ExpandEnvironmentStringsW(L"%SystemRoot%\\system32\\lsaiso.exe", Dst, 0x104u) )
  {
    v13 = RtlStringCchPrintfW(Buffer, 0x104u, L"%s %s %s", Dst, L"-KeyGuard", L"-LaunchedAfterBoot");
    LastError = v13;
    if ( v13 < 0 )
    {
      v8 = 600;
      goto LABEL_23;
    }
    if ( v0 )
    {
      v1 = 1;
      v13 = I_BCryptIsoLaunchRegularProcess(Dst, Buffer);
      LastError = v13;
      if ( v13 < 0 )
      {
        v8 = 613;
        goto LABEL_23;
      }
    }
    else
    {
      if ( !v11 || !CanLaunchSecureProcess )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_ddd(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, v15, 0, v11, CanLaunchSecureProcess);
        goto LABEL_59;
      }
      KGRunningInProdMode = 0;
      v13 = CheckWhetherSecureKernelIsRunning(&KGRunningInProdMode);
      LastError = v13;
      if ( v13 < 0 )
      {
        v8 = 624;
        goto LABEL_23;
      }
      if ( KGRunningInProdMode )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_a6b47fe3e7aa3dc67b817b99b29667f9_Traceguids);
        goto LABEL_52;
      }
      v1 = 1;
      v13 = I_BCryptIsoLaunchSecureProcess(Dst, Buffer, &hProcess);
      LastError = v13;
      if ( v13 < 0 )
      {
        v8 = 638;
        goto LABEL_23;
      }
    }
    v16 = I_BCryptIsoReadDwordFromRegistry(
            L"SYSTEM\\CurrentControlSet\\Control\\DeviceGuard\\Scenarios\\KeyGuard",
            L"LaunchWaitTimeoutSeconds");
    if ( !(_DWORD)v16 )
      v16 = 5;
    Timeout.QuadPart = -10000000 * v16;
    v13 = NtWaitForSingleObject(EventHandle, 0, &Timeout);
    LastError = v13;
    if ( v13 < 0 )
    {
      v8 = 661;
      goto LABEL_23;
    }
    if ( v11 )
    {
      KGRunningInProdMode = 0;
      v13 = CheckWhetherSecureKernelIsRunning(&KGRunningInProdMode);
      LastError = v13;
      if ( v13 < 0 )
      {
        v8 = 675;
        goto LABEL_23;
      }
      if ( !KGRunningInProdMode )
      {
        v8 = 682;
LABEL_12:
        LastError = -1073741823;
        v10 = 3221225473LL;
LABEL_13:
        DebugTraceError(v10, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\lib\\bcryptisotrustlet.cpp", v8);
LABEL_60:
        v17 = 0;
        goto LABEL_61;
      }
    }
    ::hProcess = hProcess;
    hProcess = 0;
    goto LABEL_52;
  }
  LastError = GetLastError();
  DebugTraceError(LastError, "error", "onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\lib\\bcryptisotrustlet.cpp", 586);
  v14 = LastError == 0;
  if ( (int)LastError > 0 )
  {
    LastError = (unsigned __int16)LastError | 0xC0070000;
LABEL_52:
    v14 = LastError == 0;
  }
  if ( !v14 || v1 )
    goto LABEL_60;
  v17 = 1;
LABEL_61:
  if ( !dword_18007A110 && !v17 && !v3 )
  {
    if ( LastError )
      ++dword_18007A114;
    I_BCryptIsoUpdateAndLogRestartData(LastError, v0);
    if ( !LastError )
      goto LABEL_70;
    v18 = I_BCryptIsoReadDwordFromRegistry(
            L"SYSTEM\\CurrentControlSet\\Control\\DeviceGuard\\Scenarios\\KeyGuard",
            L"FailedLaunchesThreshold");
    if ( !v18 )
      v18 = 2;
    if ( dword_18007A114 == v18 )
    {
LABEL_70:
      dword_18007A110 = 1;
      dword_18007A114 = 0;
      qword_18007A108 = GetTickCount64();
    }
    if ( CanLaunchSecureProcess
      && !RtlDllShutdownInProgress()
      && dword_180079128
      && (unsigned __int8)tlgKeywordOn(&dword_180079128, 0x800000000000LL, v19, v20) )
    {
      *(_QWORD *)v29 = 2048;
      KGRunningInProdMode = BCryptIsoGetKGRunningInProdMode(&g_keyguardRegistryData);
      v32 = 0;
      v33 = 0;
      v34 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        v21,
        (unsigned int)&word_18006FB76,
        v22,
        (unsigned int)&v34,
        (__int64)&v33,
        (__int64)&v32,
        (__int64)&KGRunningInProdMode,
        (__int64)v29);
    }
  }
  if ( hProcess )
  {
    if ( !TerminateProcess(hProcess, 0) )
    {
      v23 = GetLastError();
      DebugTraceError(
        v23,
        "GetLastError()",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\lib\\bcryptisotrustlet.cpp",
        739);
    }
    if ( !CloseHandle(hProcess) )
    {
      v24 = GetLastError();
      DebugTraceError(
        v24,
        "GetLastError()",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\lib\\bcryptisotrustlet.cpp",
        744);
    }
  }
  if ( EventHandle )
  {
    v25 = NtClose(EventHandle);
    if ( v25 < 0 )
      DebugTraceError(
        (unsigned int)v25,
        "status2",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\lib\\bcryptisotrustlet.cpp",
        753);
  }
  return LastError;
}

```

## disassembly

```asm
0x18002831c  push    rbp
0x18002831e  push    rbx
0x18002831f  push    rsi
0x180028320  push    rdi
0x180028321  push    r12
0x180028323  push    r13
0x180028325  push    r14
0x180028327  push    r15
0x180028329  lea     rbp, [rsp-3F8h]
0x180028331  sub     rsp, 4F8h
0x180028338  mov     rax, cs:__security_cookie
0x18002833f  xor     rax, rsp
0x180028342  mov     [rbp+430h+var_50], rax
0x180028349  xorps   xmm1, xmm1
0x18002834c  lea     rcx, [rbp+430h+Dst]; void *
0x180028350  xor     r15d, r15d
0x180028353  xorps   xmm0, xmm0
0x180028356  mov     ebx, 208h
0x18002835b  mov     [rsp+530h+hProcess], r15
0x180028360  mov     r8d, ebx; Size
0x180028363  mov     [rsp+530h+EventHandle], r15
0x180028368  xor     edx, edx; Val
0x18002836a  mov     qword ptr [rsp+530h+Timeout], r15
0x18002836f  movups  xmmword ptr [rbp+430h+DestinationString.Length], xmm0
0x180028373  movups  xmmword ptr [rbp+430h+ObjectAttributes.Length], xmm1
0x180028377  movups  xmmword ptr [rbp+430h+ObjectAttributes.ObjectName], xmm1
0x18002837b  movups  xmmword ptr [rbp+430h+ObjectAttributes.SecurityDescriptor], xmm1
0x18002837f  call    memset_0
0x180028384  mov     r8d, ebx; Size
0x180028387  lea     rcx, [rbp+430h+Buffer]; void *
0x18002838e  xor     edx, edx; Val
0x180028390  call    memset_0
0x180028395  mov     r14d, r15d
0x180028398  mov     [rsp+530h+var_4E0], r15d
0x18002839d  mov     [rsp+530h+var_4F0], r15d
0x1800283a2  mov     r12d, r15d
0x1800283a5  call    I_BCryptIsoCanLaunchSecureProcess
0x1800283aa  mov     esi, eax
0x1800283ac  mov     r13d, r15d
0x1800283af  call    cs:__imp_GetTickCount64
0x1800283b6  nop     dword ptr [rax+rax+00h]
0x1800283bb  cmp     cs:dword_18007A110, r15d
0x1800283c2  lea     edi, [r15+5]
0x1800283c6  mov     rbx, rax
0x1800283c9  jz      loc_18002847C
0x1800283cf  sub     rbx, cs:qword_18007A108
0x1800283d6  lea     rdx, aNolaunchtimeou; "NoLaunchTimeoutSeconds"
0x1800283dd  lea     rcx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Control\\Dev"...
0x1800283e4  call    I_BCryptIsoReadDwordFromRegistry
0x1800283e9  test    eax, eax
0x1800283eb  mov     ecx, eax
0x1800283ed  mov     rax, 624DD2F1A9FBE77h
0x1800283f7  cmovz   ecx, edi
0x1800283fa  mul     rbx
0x1800283fd  mov     eax, ecx
0x1800283ff  sub     rbx, rdx
0x180028402  shr     rbx, 1
0x180028405  add     rbx, rdx
0x180028408  shr     rbx, 9
0x18002840c  cmp     rbx, rax
0x18002840f  jb      short loc_18002841C
0x180028411  mov     eax, r15d
0x180028414  mov     cs:dword_18007A110, eax
0x18002841a  jmp     short loc_180028422
0x18002841c  mov     eax, cs:dword_18007A110
0x180028422  test    eax, eax
0x180028424  jz      short loc_18002847C
0x180028426  mov     rcx, cs:WPP_GLOBAL_Control
0x18002842d  lea     rax, WPP_GLOBAL_Control
0x180028434  cmp     rcx, rax
0x180028437  jz      short loc_180028454
0x180028439  test    byte ptr [rcx+1Ch], 8
0x18002843d  jz      short loc_180028454
0x18002843f  mov     rcx, [rcx+10h]
0x180028443  lea     r8, WPP_a6b47fe3e7aa3dc67b817b99b29667f9_Traceguids
0x18002844a  mov     edx, 0Ch
0x18002844f  call    WPP_SF_
0x180028454  mov     r9d, 214h
0x18002845a  mov     ebx, 0C0000001h
0x18002845f  mov     ecx, 0C0000001h
0x180028464  lea     rdx, aStatus_0; "status"
0x18002846b  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180028472  call    DebugTraceError
0x180028477  jmp     loc_1800287BE
0x18002847c  lea     rdx, [rsp+530h+var_4F0]; int *
0x180028481  lea     rcx, [rsp+530h+var_4E0]; int *
0x180028486  call    ?BCryptIsoReadProcessModeFromRegistry@@YAXPEAH0@Z; BCryptIsoReadProcessModeFromRegistry(int *,int *)
0x18002848b  mov     r14d, [rsp+530h+var_4E0]
0x180028490  mov     edi, [rsp+530h+var_4F0]
0x180028494  test    esi, esi
0x180028496  jz      short loc_18002849C
0x180028498  test    edi, edi
0x18002849a  jnz     short loc_1800284A1
0x18002849c  test    r14d, r14d
0x18002849f  jz      short loc_1800284A7
0x1800284a1  mov     r15d, 1
0x1800284a7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_KG_Skip_Launch_Without_VBS@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_KG_Skip_Launch_Without_VBS@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_KG_Skip_Launch_Without_VBS> `wil::Feature<__WilFeatureTraits_Feature_KG_Skip_Launch_Without_VBS>::GetImpl(void)'::`2'::impl
0x1800284ae  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_KG_Skip_Launch_Without_VBS@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_KG_Skip_Launch_Without_VBS>::__private_IsEnabled(void)
0x1800284b3  xor     ebx, ebx
0x1800284b5  test    al, al
0x1800284b7  jz      short loc_1800284F8
0x1800284b9  test    edi, edi
0x1800284bb  jz      short loc_1800284F8
0x1800284bd  test    esi, esi
0x1800284bf  jnz     short loc_1800284F8
0x1800284c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800284c8  lea     rax, WPP_GLOBAL_Control
0x1800284cf  cmp     rcx, rax
0x1800284d2  jz      short loc_1800284ED
0x1800284d4  test    byte ptr [rcx+1Ch], 8
0x1800284d8  jz      short loc_1800284ED
0x1800284da  mov     rcx, [rcx+10h]
0x1800284de  lea     edx, [rbx+0Dh]
0x1800284e1  mov     r9d, edi
0x1800284e4  mov     dword ptr [rsp+530h+InitialState], ebx
0x1800284e8  call    WPP_SF_dd
0x1800284ed  mov     r13d, 1
0x1800284f3  jmp     loc_1800287B9
0x1800284f8  lea     rdx, aLsaIsoReadyLau; "\\LSA_ISO_READY_LAUNCHED_AFTER_BOOT"
0x1800284ff  lea     rcx, [rbp+430h+DestinationString]; DestinationString
0x180028503  call    cs:__imp_RtlInitUnicodeString
0x18002850a  nop     dword ptr [rax+rax+00h]
0x18002850f  lea     rax, [rbp+430h+DestinationString]
0x180028513  mov     [rbp+430h+ObjectAttributes.Length], 30h ; '0'
0x18002851a  xorps   xmm0, xmm0
0x18002851d  mov     [rbp+430h+ObjectAttributes.ObjectName], rax
0x180028521  movdqu  xmmword ptr [rbp+430h+ObjectAttributes.SecurityDescriptor], xmm0
0x180028526  mov     [rbp+430h+ObjectAttributes.RootDirectory], rbx
0x18002852a  mov     [rbp+430h+ObjectAttributes.Attributes], ebx
0x18002852d  call    I_BCryptIsoStopProcess
0x180028532  xor     r9d, r9d; EventType
0x180028535  mov     [rsp+530h+InitialState], bl; InitialState
0x180028539  lea     r8, [rbp+430h+ObjectAttributes]; ObjectAttributes
0x18002853d  mov     edx, 1F0003h; DesiredAccess
0x180028542  lea     rcx, [rsp+530h+EventHandle]; EventHandle
0x180028547  call    cs:__imp_NtCreateEvent
0x18002854e  nop     dword ptr [rax+rax+00h]
0x180028553  mov     ebx, eax
0x180028555  test    eax, eax
0x180028557  jns     short loc_180028566
0x180028559  mov     r9d, 23Fh
0x18002855f  mov     ecx, eax
0x180028561  jmp     loc_180028464
0x180028566  mov     ebx, 104h
0x18002856b  lea     rdx, [rbp+430h+Dst]; lpDst
0x18002856f  mov     r8d, ebx; nSize
0x180028572  lea     rcx, Src; "%SystemRoot%\\system32\\lsaiso.exe"
0x180028579  call    cs:__imp_ExpandEnvironmentStringsW
0x180028580  nop     dword ptr [rax+rax+00h]
0x180028585  test    eax, eax
0x180028587  jnz     short loc_1800285C8
0x180028589  call    cs:__imp_GetLastError
0x180028590  nop     dword ptr [rax+rax+00h]
0x180028595  mov     r9d, 24Ah
0x18002859b  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800285a2  mov     ecx, eax
0x1800285a4  lea     rdx, aError; "error"
0x1800285ab  mov     ebx, eax
0x1800285ad  call    DebugTraceError
0x1800285b2  test    ebx, ebx
0x1800285b4  jle     loc_180028779
0x1800285ba  movzx   ebx, bx
0x1800285bd  or      ebx, 0C0070000h
0x1800285c3  jmp     loc_180028777
0x1800285c8  lea     rax, aLaunchedafterb; "-LaunchedAfterBoot"
0x1800285cf  mov     rdx, rbx; unsigned __int64
0x1800285d2  mov     [rsp+530h+var_508], rax
0x1800285d7  lea     r9, [rbp+430h+Dst]
0x1800285db  lea     rax, aKeyguard; "-KeyGuard"
0x1800285e2  lea     r8, aSSS_0; "%s %s %s"
0x1800285e9  mov     qword ptr [rsp+530h+InitialState], rax
0x1800285ee  lea     rcx, [rbp+430h+Buffer]; Buffer
0x1800285f5  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800285fa  mov     ebx, eax
0x1800285fc  test    eax, eax
0x1800285fe  jns     short loc_18002860B
0x180028600  mov     r9d, 258h
0x180028606  jmp     loc_18002855F
0x18002860b  test    r14d, r14d
0x18002860e  jz      short loc_180028640
0x180028610  lea     r8, [rsp+530h+hProcess]
0x180028615  mov     r12d, 1
0x18002861b  lea     rdx, [rbp+430h+Buffer]; lpCommandLine
0x180028622  lea     rcx, [rbp+430h+Dst]; lpApplicationName
0x180028626  call    I_BCryptIsoLaunchRegularProcess
0x18002862b  mov     ebx, eax
0x18002862d  test    eax, eax
0x18002862f  jns     loc_1800286DE
0x180028635  mov     r9d, 265h
0x18002863b  jmp     loc_18002855F
0x180028640  test    edi, edi
0x180028642  jz      loc_180028787
0x180028648  test    esi, esi
0x18002864a  jz      loc_180028787
0x180028650  lea     rcx, [rsp+530h+var_4F0]
0x180028655  mov     [rsp+530h+var_4F0], r12d
0x18002865a  call    CheckWhetherSecureKernelIsRunning
0x18002865f  mov     ebx, eax
0x180028661  test    eax, eax
0x180028663  jns     short loc_180028670
0x180028665  mov     r9d, 270h
0x18002866b  jmp     loc_18002855F
0x180028670  cmp     [rsp+530h+var_4F0], r12d
0x180028675  jz      short loc_1800286B2
0x180028677  mov     rcx, cs:WPP_GLOBAL_Control
0x18002867e  lea     rax, WPP_GLOBAL_Control
0x180028685  cmp     rcx, rax
0x180028688  jz      loc_180028777
0x18002868e  test    byte ptr [rcx+1Ch], 8
0x180028692  jz      loc_180028777
0x180028698  mov     rcx, [rcx+10h]
0x18002869c  lea     r8, WPP_a6b47fe3e7aa3dc67b817b99b29667f9_Traceguids
0x1800286a3  mov     edx, 0Eh
0x1800286a8  call    WPP_SF_
0x1800286ad  jmp     loc_180028777
0x1800286b2  lea     r8, [rsp+530h+hProcess]
0x1800286b7  mov     r12d, 1
0x1800286bd  lea     rdx, [rbp+430h+Buffer]
0x1800286c4  lea     rcx, [rbp+430h+Dst]
0x1800286c8  call    I_BCryptIsoLaunchSecureProcess
0x1800286cd  mov     ebx, eax
0x1800286cf  test    eax, eax
0x1800286d1  jns     short loc_1800286DE
0x1800286d3  mov     r9d, 27Eh
0x1800286d9  jmp     loc_18002855F
0x1800286de  lea     rdx, aLaunchwaittime; "LaunchWaitTimeoutSeconds"
0x1800286e5  lea     rcx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Control\\Dev"...
0x1800286ec  call    I_BCryptIsoReadDwordFromRegistry
0x1800286f1  test    eax, eax
0x1800286f3  lea     r8, [rsp+530h+Timeout]; Timeout
0x1800286f8  mov     ecx, 5
0x1800286fd  cmovz   eax, ecx
0x180028700  xor     edx, edx; Alertable
0x180028702  imul    rcx, rax, 0FFFFFFFFFF676980h
0x180028709  mov     qword ptr [rsp+530h+Timeout], rcx
0x18002870e  mov     rcx, [rsp+530h+EventHandle]; Handle
0x180028713  call    cs:__imp_NtWaitForSingleObject
0x18002871a  nop     dword ptr [rax+rax+00h]
0x18002871f  mov     ebx, eax
0x180028721  test    eax, eax
0x180028723  jns     short loc_180028730
0x180028725  mov     r9d, 295h
0x18002872b  jmp     loc_18002855F
0x180028730  test    edi, edi
0x180028732  jz      short loc_180028766
0x180028734  lea     rcx, [rsp+530h+var_4F0]
0x180028739  mov     [rsp+530h+var_4F0], r13d
0x18002873e  call    CheckWhetherSecureKernelIsRunning
0x180028743  mov     ebx, eax
0x180028745  test    eax, eax
0x180028747  jns     short loc_180028754
0x180028749  mov     r9d, 2A3h
0x18002874f  jmp     loc_18002855F
0x180028754  cmp     [rsp+530h+var_4F0], r13d
0x180028759  jnz     short loc_180028766
0x18002875b  mov     r9d, 2AAh
0x180028761  jmp     loc_18002845A
0x180028766  mov     rax, [rsp+530h+hProcess]
0x18002876b  mov     cs:hProcess, rax
0x180028772  mov     [rsp+530h+hProcess], r13
0x180028777  test    ebx, ebx
0x180028779  jnz     short loc_1800287BE
0x18002877b  test    r12d, r12d
0x18002877e  jnz     short loc_1800287BE
0x180028780  lea     eax, [r12+1]
0x180028785  jmp     short loc_1800287C0
0x180028787  mov     rcx, cs:WPP_GLOBAL_Control
0x18002878e  lea     rax, WPP_GLOBAL_Control
0x180028795  cmp     rcx, rax
0x180028798  jz      short loc_1800287B9
0x18002879a  test    byte ptr [rcx+1Ch], 1
0x18002879e  jz      short loc_1800287B9
0x1800287a0  mov     rcx, [rcx+10h]
0x1800287a4  mov     edx, 0Fh
0x1800287a9  mov     dword ptr [rsp+530h+var_508], esi
0x1800287ad  xor     r9d, r9d
0x1800287b0  mov     dword ptr [rsp+530h+InitialState], edi
0x1800287b4  call    WPP_SF_ddd
0x1800287b9  mov     ebx, 0C0000001h
0x1800287be  xor     eax, eax
0x1800287c0  cmp     cs:dword_18007A110, 0
0x1800287c7  jnz     loc_1800288F9
0x1800287cd  test    eax, eax
0x1800287cf  jnz     loc_1800288F9
0x1800287d5  test    r13d, r13d
0x1800287d8  jnz     loc_1800288F9
0x1800287de  test    ebx, ebx
0x1800287e0  jz      short loc_1800287E8
0x1800287e2  inc     cs:dword_18007A114
0x1800287e8  mov     r9d, r15d
0x1800287eb  mov     r8d, r12d
0x1800287ee  mov     edx, r14d; int
0x1800287f1  mov     ecx, ebx; int
0x1800287f3  call    I_BCryptIsoUpdateAndLogRestartData
0x1800287f8  test    ebx, ebx
0x1800287fa  jz      short loc_180028821
0x1800287fc  lea     rdx, aFailedlaunches; "FailedLaunchesThreshold"
0x180028803  lea     rcx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Control\\Dev"...
0x18002880a  call    I_BCryptIsoReadDwordFromRegistry
0x18002880f  test    eax, eax
  ... truncated ...
```
