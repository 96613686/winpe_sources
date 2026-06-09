# UxStartEnvironmentModule

- ea: `0x1400dfc40`
- end: `0x1400e03f8`
- name: `UxStartEnvironmentModule`
- size: `1976`
- prototype: ``
- caller_count: `0`
- callee_count: `26`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x14008fe1c`
- `0x1400a2f60`
- `0x1400d6e54`
- `0x1400de4d4`
- `0x1400de52c`
- `0x1400de584`
- `0x1400de5dc`
- `0x1400de634`
- `0x1400de68c`
- `0x1400de6e4`
- `0x1400de73c`
- `0x1400de794`
- `0x1400de7ec`
- `0x1400de844`
- `0x1400de89c`
- `0x1400deb7c`
- `0x1400debd8`
- `0x1400dfc40`
- `0x1400e0450`
- `0x140103ee0`
- `0x14010476c`
- `0x140167700`
- `0x140167b40`
- `0x1401c3f58`
- `0x1401da5a4`
- `0x1401df078`

## import_xrefs

- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x1400dffe1`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x1400dffe1`
- `ntoskrnl!RtlGetVersion` at `0x1400e0082`
- `ntoskrnl!RtlGetVersion` at `0x1400e0082`
- `ntoskrnl!ZwOpenKey` at `0x1400e00f7`
- `ntoskrnl!ZwOpenKey` at `0x1400e00f7`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x1400dfff3`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x1400dfff3`
- `ntoskrnl!ZwClose` at `0x1400e03a4`
- `ntoskrnl!ZwClose` at `0x1400e03a4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e03bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e03bf`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400e00ab`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400e00ab`
- `HAL!KeQueryPerformanceCounter` at `0x1400e035a`
- `HAL!KeQueryPerformanceCounter` at `0x1400e035a`

## string_xrefs

- `0x1400dfc8f`: `\Registry\Machine\System\CurrentControlSet\Services\Http\Parameters`
- `0x1400e0124`: `CompactMode`
- `0x1400e031a`: `AllowNonprivilegedCaptureCred`

## pseudocode

```c
__int64 UxStartEnvironmentModule()
{
  void *QuadPart; // rdi
  int PhysicalMemorySize; // ebx
  void *v2; // rcx
  __int64 v3; // r8
  char LongLongParameter; // al
  _BYTE v6[8]; // [rsp+40h] [rbp-C0h] BYREF
  void *KeyHandle; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v8; // [rsp+50h] [rbp-B0h] BYREF
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v10[2]; // [rsp+60h] [rbp-A0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-90h] BYREF
  _BYTE VersionInformation[284]; // [rsp+A0h] [rbp-60h] BYREF

  memset(VersionInformation, 0, sizeof(VersionInformation));
  v10[0] = 8913030;
  KeyHandle = 0;
  v8 = 0;
  v10[1] = L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\Http\\Parameters";
  QuadPart = 0;
  PerformanceFrequency.QuadPart = 0;
  memset(&ObjectAttributes, 0, 44);
  v6[0] = 0;
  PhysicalMemorySize = wil_InitializeFeatureStaging();
  if ( PhysicalMemorySize >= 0 )
  {
    UxFeatureStagingInitialized = 1;
    UxKirDtHttpFastForwardHttp11Client = (unsigned int)Feature_DtHttpFastForwardHttp11Client__private_IsEnabledDeviceUsageNoInline() != 0;
    UxKirBrHttpQuerySocketTtl = (unsigned int)Feature_HttpQueryTcpTtlRedux__private_IsEnabledDeviceUsageNoInline() != 0;
    UxKirDtHttp2IsbLimit = (unsigned int)Feature_DtHttpIsbLimitHttp2__private_IsEnabledDeviceUsageNoInline() != 0;
    UxKirHttpBugFix25Q1 = (unsigned int)Feature_HttpBugFix25Q1__private_IsEnabledDeviceUsageNoInline() != 0;
    UxKirAddDisableAiaFlag = (unsigned int)Feature_Servicing_AddDisableAiaFlag__private_IsEnabledDeviceUsageNoInline() != 0;
    UxKirRefactorIoctls = (unsigned int)Feature_RefactorIoctls__private_IsEnabledDeviceUsageNoInline() != 0;
    UxKirMsQuic_2_5 = (unsigned int)Feature_MsQuic_2_5__private_IsEnabledDeviceUsageNoInline() != 0;
    UxKirHttpBugFix26Q1 = (unsigned int)Feature_HttpBugFix26Q1__private_IsEnabledDeviceUsageNoInline() != 0;
    UxKirHttpReadingTrailersFromUm = 1;
    UxKirWritingAndReadingUm = 1;
    UxKirWritingAndReadingUmCertList = 1;
    UxKirHKERangeRequestH2StatusCode = (unsigned int)Feature_HttpsysHKERangeRequestH2StatusCode__private_IsEnabledDeviceUsageNoInline() != 0;
    UxKirHttpTlsHandshakePerfCounter = (unsigned int)Feature_HttpTlsHandshakePerfCounter__private_IsEnabledDeviceUsageNoInline() != 0;
    UxKirNewUma = (unsigned int)Feature_NewUMAHttpSys__private_IsEnabledDeviceUsageNoInline() != 0;
    UxKirHttpBugFix26Q2 = (unsigned int)Feature_HttpBugFix26Q2__private_IsEnabledDeviceUsageNoInline() != 0;
    UxKirQuicParseLengthCheck = 1;
    if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_d(1049, 10, WPP_0d31acbfce0c3b7e2240b0d09fd2f2d4_Traceguids, (unsigned __int8)UxKirHttpBugFix25Q1);
    if ( UxKirDtHttp2IsbLimit && (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_(1049, 11, WPP_0d31acbfce0c3b7e2240b0d09fd2f2d4_Traceguids);
    if ( UxKirDtHttpFastForwardHttp11Client && (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_(1049, 12, WPP_0d31acbfce0c3b7e2240b0d09fd2f2d4_Traceguids);
    if ( UxKirHttpBugFix25Q1 && (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_(1049, 13, WPP_0d31acbfce0c3b7e2240b0d09fd2f2d4_Traceguids);
    if ( UxKirBrHttpQuerySocketTtl && (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_(1049, 14, WPP_0d31acbfce0c3b7e2240b0d09fd2f2d4_Traceguids);
    if ( UxKirAddDisableAiaFlag && (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_(1049, 15, WPP_0d31acbfce0c3b7e2240b0d09fd2f2d4_Traceguids);
    if ( UxKirMsQuic_2_5 && (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_(1049, 16, WPP_0d31acbfce0c3b7e2240b0d09fd2f2d4_Traceguids);
    if ( UxKirHKERangeRequestH2StatusCode && (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_(1049, 17, WPP_0d31acbfce0c3b7e2240b0d09fd2f2d4_Traceguids);
    if ( UxKirRefactorIoctls && (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_(1049, 18, WPP_0d31acbfce0c3b7e2240b0d09fd2f2d4_Traceguids);
    if ( UxKirHttpBugFix26Q1 && (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_(1049, 19, WPP_0d31acbfce0c3b7e2240b0d09fd2f2d4_Traceguids);
    if ( UxKirHttpReadingTrailersFromUm && (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_(1049, 20, WPP_0d31acbfce0c3b7e2240b0d09fd2f2d4_Traceguids);
    if ( UxKirWritingAndReadingUm && (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_(1049, 21, WPP_0d31acbfce0c3b7e2240b0d09fd2f2d4_Traceguids);
    if ( UxKirWritingAndReadingUmCertList && (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_(1049, 22, WPP_0d31acbfce0c3b7e2240b0d09fd2f2d4_Traceguids);
    if ( UxKirHttpTlsHandshakePerfCounter && (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_(1049, 23, WPP_0d31acbfce0c3b7e2240b0d09fd2f2d4_Traceguids);
    if ( UxKirNewUma && (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_(1049, 24, WPP_0d31acbfce0c3b7e2240b0d09fd2f2d4_Traceguids);
    if ( UxKirHttpBugFix26Q2 && (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_(1049, 25, WPP_0d31acbfce0c3b7e2240b0d09fd2f2d4_Traceguids);
    if ( UxKirQuicParseLengthCheck && (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_(1049, 26, WPP_0d31acbfce0c3b7e2240b0d09fd2f2d4_Traceguids);
    UxNumberOfProcessors = 0;
    UxMaximumNumberOfProcessors = KeQueryMaximumProcessorCountEx(0xFFFFu);
    UxNumberOfNodes = KeQueryHighestNodeNumber() + 1;
    PhysicalMemorySize = UxGetPhysicalMemorySize(&UxTotalPhysicalMemMB);
    if ( PhysicalMemorySize >= 0 )
    {
      PhysicalMemorySize = UxOpenNamedEvent(L"\\KernelObjects\\LowNonPagedPoolCondition");
      if ( PhysicalMemorySize >= 0 )
      {
        PhysicalMemorySize = UxOpenNamedEvent(L"\\KernelObjects\\HighNonPagedPoolCondition");
        if ( PhysicalMemorySize >= 0 )
        {
          PhysicalMemorySize = UxOpenNamedEvent(L"\\KernelObjects\\LowMemoryCondition");
          if ( PhysicalMemorySize >= 0 )
          {
            *(_DWORD *)VersionInformation = 284;
            PhysicalMemorySize = RtlGetVersion((PRTL_OSVERSIONINFOW)VersionInformation);
            if ( PhysicalMemorySize >= 0 )
            {
              UxServerSystem = (unsigned __int8)(VersionInformation[282] - 2) <= 1u;
              UxSystemProcess = IoGetCurrentProcess();
              HttpCmnInitializeStaticHttpCharsTable();
              ObjectAttributes.Length = 48;
              ObjectAttributes.ObjectName = (PUNICODE_STRING)v10;
              ObjectAttributes.RootDirectory = 0;
              ObjectAttributes.Attributes = 576;
              *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
              PhysicalMemorySize = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
              if ( PhysicalMemorySize >= 0 )
              {
                v2 = KeyHandle;
              }
              else
              {
                v2 = 0;
                PhysicalMemorySize = 0;
                KeyHandle = 0;
              }
              UxReadBooleanSetting(v2, L"CompactMode", 0, &UxCompactMode);
              if ( UxKirHttpBugFix25Q1 )
                UxReadBooleanSetting(KeyHandle, L"EnableIrqlEnforcement", 0, &UxEnableIrqlEnforcement);
              UxReadBooleanSetting(KeyHandle, L"SendEndpointInfoToAsc", 0, &UxSendEndpointInfoToASC);
              UxReadBooleanSetting(KeyHandle, L"TlsUseStaticServerHello", 0, &UxTlsUseStaticServerHello);
              UxReadBoundedULongSetting(
                (_DWORD)KeyHandle,
                (unsigned int)L"AscThrottleLimit",
                0,
                0,
                0x7FFFFFFF,
                0,
                (__int64)&UxAscThrottleLimit);
              LOBYTE(v3) = 1;
              UxReadBooleanSetting(KeyHandle, L"EnableSslLargeBuffer", v3, &UxSslLargeBufferEnabled);
              UxReadBoundedULongSetting(
                (_DWORD)KeyHandle,
                (unsigned int)L"RssStatusCheckControl",
                1,
                0,
                2,
                0,
                (__int64)&UxRssEnabledCheckControl);
              UxReadBooleanSetting(KeyHandle, L"EnableHttp3", 0, &UxHttp3ServerEnabled);
              UxReadBooleanSetting(KeyHandle, L"EnableHttp3Push", 0, &UxHttp3PushEnabled);
              UxReadBooleanSetting(KeyHandle, L"EnableExtendedEvents", 0, &UxExtendedEventsEnabled);
              UxReadBoundedULongSetting(
                (_DWORD)KeyHandle,
                (unsigned int)L"ExtendedEventsFrequency",
                3600,
                15,
                0x7FFFFFFF,
                0,
                (__int64)&v8);
              UxExtendedEventsFrequency = 10000000LL * v8;
              UxReadBooleanSetting(KeyHandle, L"EnableAltSvc", 0, &UxAltSvcEnabled);
              if ( UxTelAssertInitialized )
                UxReadBooleanSetting(KeyHandle, L"EnableTelAsserts", 0, &UxTelAssertsEnabled);
              else
                UxTelAssertsEnabled = 0;
              UlReadGenericParameter(KeyHandle);
              QuadPart = (void *)PerformanceFrequency.QuadPart;
              if ( PerformanceFrequency.QuadPart && *(_DWORD *)(PerformanceFrequency.QuadPart + 4) == 7 )
              {
                UxHttp3AlpnRegValue = (PVOID)PerformanceFrequency.QuadPart;
                QuadPart = 0;
              }
              UxReadBooleanSetting(KeyHandle, L"AllowNonprivilegedCaptureCred", 0, &UxAllowNonprivilegedCaptureCred);
              LongLongParameter = UlReadLongLongParameter(KeyHandle, L"DebugFlags", 0);
              PerformanceFrequency.QuadPart = 0;
              UxDebugCheckRefcount = LongLongParameter & 1;
              UxDebugDisableLookaside = (LongLongParameter & 2) != 0;
              KeQueryPerformanceCounter(&PerformanceFrequency);
              UxPerformanceCounterPeriod = PerformanceFrequency.QuadPart;
              UxReadBooleanSetting(KeyHandle, L"DisableMultipleLanes", 0, v6);
              if ( v6[0] )
                UxNumberOfNodes = 1;
            }
          }
        }
      }
    }
  }
  if ( KeyHandle )
  {
    ZwClose(KeyHandle);
    KeyHandle = 0;
  }
  if ( QuadPart )
    ExFreePoolWithTag(QuadPart, 0);
  if ( PhysicalMemorySize < 0 )
    UxStopEnvironmentModule();
  return (unsigned int)PhysicalMemorySize;
}

```

## disassembly

```asm
0x1400dfc40  push    rbp
0x1400dfc42  push    rbx
0x1400dfc43  push    rsi
0x1400dfc44  push    rdi
0x1400dfc45  push    r12
0x1400dfc47  push    r14
0x1400dfc49  push    r15
0x1400dfc4b  lea     rbp, [rsp-0D0h]
0x1400dfc53  sub     rsp, 1D0h
0x1400dfc5a  mov     rax, cs:__security_cookie
0x1400dfc61  xor     rax, rsp
0x1400dfc64  mov     [rbp+100h+var_40], rax
0x1400dfc6b  xor     edx, edx; Val
0x1400dfc6d  lea     rcx, [rbp+100h+VersionInformation]; void *
0x1400dfc71  mov     r8d, 11Ch; Size
0x1400dfc77  call    memset
0x1400dfc7c  xor     esi, esi
0x1400dfc7e  mov     [rsp+200h+var_1A0], 880086h
0x1400dfc87  xorps   xmm0, xmm0
0x1400dfc8a  mov     [rsp+200h+KeyHandle], rsi
0x1400dfc8f  lea     rax, aRegistryMachin_7; "\\Registry\\Machine\\System\\CurrentCon"...
0x1400dfc96  mov     [rsp+200h+var_1B0], esi
0x1400dfc9a  mov     [rsp+200h+var_198], rax
0x1400dfc9f  mov     edi, esi
0x1400dfca1  movups  xmmword ptr [rbp+100h+ObjectAttributes.ObjectName], xmm0
0x1400dfca5  xor     eax, eax
0x1400dfca7  mov     qword ptr [rsp+200h+PerformanceFrequency], rsi
0x1400dfcac  movups  xmmword ptr [rsp+200h+ObjectAttributes.Length], xmm0
0x1400dfcb1  mov     [rsp+200h+var_1C0], sil
0x1400dfcb6  movups  xmmword ptr [rbp+100h+ObjectAttributes+1Ch], xmm0
0x1400dfcba  call    wil_InitializeFeatureStaging
0x1400dfcbf  mov     ebx, eax
0x1400dfcc1  test    eax, eax
0x1400dfcc3  js      loc_1400E039A
0x1400dfcc9  lea     r12d, [rsi+1]
0x1400dfccd  mov     cs:UxFeatureStagingInitialized, r12b
0x1400dfcd4  call    Feature_DtHttpFastForwardHttp11Client__private_IsEnabledDeviceUsageNoInline
0x1400dfcd9  test    eax, eax
0x1400dfcdb  setnz   cs:UxKirDtHttpFastForwardHttp11Client
0x1400dfce2  call    Feature_HttpQueryTcpTtlRedux__private_IsEnabledDeviceUsageNoInline
0x1400dfce7  test    eax, eax
0x1400dfce9  setnz   cs:UxKirBrHttpQuerySocketTtl
0x1400dfcf0  call    Feature_DtHttpIsbLimitHttp2__private_IsEnabledDeviceUsageNoInline
0x1400dfcf5  test    eax, eax
0x1400dfcf7  setnz   cs:UxKirDtHttp2IsbLimit
0x1400dfcfe  call    Feature_HttpBugFix25Q1__private_IsEnabledDeviceUsageNoInline
0x1400dfd03  test    eax, eax
0x1400dfd05  setnz   cs:UxKirHttpBugFix25Q1
0x1400dfd0c  call    Feature_Servicing_AddDisableAiaFlag__private_IsEnabledDeviceUsageNoInline
0x1400dfd11  test    eax, eax
0x1400dfd13  setnz   cs:UxKirAddDisableAiaFlag
0x1400dfd1a  call    Feature_RefactorIoctls__private_IsEnabledDeviceUsageNoInline
0x1400dfd1f  test    eax, eax
0x1400dfd21  setnz   cs:UxKirRefactorIoctls
0x1400dfd28  call    Feature_MsQuic_2_5__private_IsEnabledDeviceUsageNoInline
0x1400dfd2d  test    eax, eax
0x1400dfd2f  setnz   cs:UxKirMsQuic_2_5
0x1400dfd36  call    Feature_HttpBugFix26Q1__private_IsEnabledDeviceUsageNoInline
0x1400dfd3b  test    eax, eax
0x1400dfd3d  setnz   cs:UxKirHttpBugFix26Q1
0x1400dfd44  mov     cs:UxKirHttpReadingTrailersFromUm, r12b
0x1400dfd4b  mov     cs:UxKirWritingAndReadingUm, r12b
0x1400dfd52  mov     cs:UxKirWritingAndReadingUmCertList, r12b
0x1400dfd59  call    Feature_HttpsysHKERangeRequestH2StatusCode__private_IsEnabledDeviceUsageNoInline
0x1400dfd5e  test    eax, eax
0x1400dfd60  setnz   cs:UxKirHKERangeRequestH2StatusCode
0x1400dfd67  call    Feature_HttpTlsHandshakePerfCounter__private_IsEnabledDeviceUsageNoInline
0x1400dfd6c  test    eax, eax
0x1400dfd6e  setnz   cs:UxKirHttpTlsHandshakePerfCounter
0x1400dfd75  call    Feature_NewUMAHttpSys__private_IsEnabledDeviceUsageNoInline
0x1400dfd7a  test    eax, eax
0x1400dfd7c  setnz   cs:UxKirNewUma
0x1400dfd83  call    Feature_HttpBugFix26Q2__private_IsEnabledDeviceUsageNoInline
0x1400dfd88  test    eax, eax
0x1400dfd8a  setnz   cs:UxKirHttpBugFix26Q2
0x1400dfd91  mov     cs:UxKirQuicParseLengthCheck, r12b
0x1400dfd98  lea     r14d, [rsi+2]
0x1400dfd9c  mov     ebx, 419h
0x1400dfda1  test    byte ptr cs:xmmword_1401A2CA0+3, r14b
0x1400dfda8  lea     r15, WPP_0d31acbfce0c3b7e2240b0d09fd2f2d4_Traceguids
0x1400dfdaf  jz      short loc_1400DFDC6
0x1400dfdb1  movzx   r9d, cs:UxKirHttpBugFix25Q1
0x1400dfdb9  lea     edx, [rsi+0Ah]
0x1400dfdbc  mov     ecx, ebx
0x1400dfdbe  mov     r8, r15
0x1400dfdc1  call    WPP_SF_d
0x1400dfdc6  cmp     cs:UxKirDtHttp2IsbLimit, sil
0x1400dfdcd  jz      short loc_1400DFDE7
0x1400dfdcf  test    byte ptr cs:xmmword_1401A2CA0+3, r14b
0x1400dfdd6  jz      short loc_1400DFDE7
0x1400dfdd8  mov     edx, 0Bh
0x1400dfddd  mov     ecx, ebx
0x1400dfddf  mov     r8, r15
0x1400dfde2  call    WPP_SF_
0x1400dfde7  cmp     cs:UxKirDtHttpFastForwardHttp11Client, sil
0x1400dfdee  jz      short loc_1400DFE08
0x1400dfdf0  test    byte ptr cs:xmmword_1401A2CA0+3, r14b
0x1400dfdf7  jz      short loc_1400DFE08
0x1400dfdf9  mov     edx, 0Ch
0x1400dfdfe  mov     ecx, ebx
0x1400dfe00  mov     r8, r15
0x1400dfe03  call    WPP_SF_
0x1400dfe08  cmp     cs:UxKirHttpBugFix25Q1, sil
0x1400dfe0f  jz      short loc_1400DFE29
0x1400dfe11  test    byte ptr cs:xmmword_1401A2CA0+3, r14b
0x1400dfe18  jz      short loc_1400DFE29
0x1400dfe1a  mov     edx, 0Dh
0x1400dfe1f  mov     ecx, ebx
0x1400dfe21  mov     r8, r15
0x1400dfe24  call    WPP_SF_
0x1400dfe29  cmp     cs:UxKirBrHttpQuerySocketTtl, sil
0x1400dfe30  jz      short loc_1400DFE4A
0x1400dfe32  test    byte ptr cs:xmmword_1401A2CA0+3, r14b
0x1400dfe39  jz      short loc_1400DFE4A
0x1400dfe3b  mov     edx, 0Eh
0x1400dfe40  mov     ecx, ebx
0x1400dfe42  mov     r8, r15
0x1400dfe45  call    WPP_SF_
0x1400dfe4a  cmp     cs:UxKirAddDisableAiaFlag, sil
0x1400dfe51  jz      short loc_1400DFE6B
0x1400dfe53  test    byte ptr cs:xmmword_1401A2CA0+3, r14b
0x1400dfe5a  jz      short loc_1400DFE6B
0x1400dfe5c  mov     edx, 0Fh
0x1400dfe61  mov     ecx, ebx
0x1400dfe63  mov     r8, r15
0x1400dfe66  call    WPP_SF_
0x1400dfe6b  cmp     cs:UxKirMsQuic_2_5, sil
0x1400dfe72  jz      short loc_1400DFE8C
0x1400dfe74  test    byte ptr cs:xmmword_1401A2CA0+3, r14b
0x1400dfe7b  jz      short loc_1400DFE8C
0x1400dfe7d  mov     edx, 10h
0x1400dfe82  mov     ecx, ebx
0x1400dfe84  mov     r8, r15
0x1400dfe87  call    WPP_SF_
0x1400dfe8c  cmp     cs:UxKirHKERangeRequestH2StatusCode, sil
0x1400dfe93  jz      short loc_1400DFEAD
0x1400dfe95  test    byte ptr cs:xmmword_1401A2CA0+3, r14b
0x1400dfe9c  jz      short loc_1400DFEAD
0x1400dfe9e  mov     edx, 11h
0x1400dfea3  mov     ecx, ebx
0x1400dfea5  mov     r8, r15
0x1400dfea8  call    WPP_SF_
0x1400dfead  cmp     cs:UxKirRefactorIoctls, sil
0x1400dfeb4  jz      short loc_1400DFECE
0x1400dfeb6  test    byte ptr cs:xmmword_1401A2CA0+3, r14b
0x1400dfebd  jz      short loc_1400DFECE
0x1400dfebf  mov     edx, 12h
0x1400dfec4  mov     ecx, ebx
0x1400dfec6  mov     r8, r15
0x1400dfec9  call    WPP_SF_
0x1400dfece  cmp     cs:UxKirHttpBugFix26Q1, sil
0x1400dfed5  jz      short loc_1400DFEEF
0x1400dfed7  test    byte ptr cs:xmmword_1401A2CA0+3, r14b
0x1400dfede  jz      short loc_1400DFEEF
0x1400dfee0  mov     edx, 13h
0x1400dfee5  mov     ecx, ebx
0x1400dfee7  mov     r8, r15
0x1400dfeea  call    WPP_SF_
0x1400dfeef  cmp     cs:UxKirHttpReadingTrailersFromUm, sil
0x1400dfef6  jz      short loc_1400DFF10
0x1400dfef8  test    byte ptr cs:xmmword_1401A2CA0+3, r14b
0x1400dfeff  jz      short loc_1400DFF10
0x1400dff01  mov     edx, 14h
0x1400dff06  mov     ecx, ebx
0x1400dff08  mov     r8, r15
0x1400dff0b  call    WPP_SF_
0x1400dff10  cmp     cs:UxKirWritingAndReadingUm, sil
0x1400dff17  jz      short loc_1400DFF31
0x1400dff19  test    byte ptr cs:xmmword_1401A2CA0+3, r14b
0x1400dff20  jz      short loc_1400DFF31
0x1400dff22  mov     edx, 15h
0x1400dff27  mov     ecx, ebx
0x1400dff29  mov     r8, r15
0x1400dff2c  call    WPP_SF_
0x1400dff31  cmp     cs:UxKirWritingAndReadingUmCertList, sil
0x1400dff38  jz      short loc_1400DFF52
0x1400dff3a  test    byte ptr cs:xmmword_1401A2CA0+3, r14b
0x1400dff41  jz      short loc_1400DFF52
0x1400dff43  mov     edx, 16h
0x1400dff48  mov     ecx, ebx
0x1400dff4a  mov     r8, r15
0x1400dff4d  call    WPP_SF_
0x1400dff52  cmp     cs:UxKirHttpTlsHandshakePerfCounter, sil
0x1400dff59  jz      short loc_1400DFF73
0x1400dff5b  test    byte ptr cs:xmmword_1401A2CA0+3, r14b
0x1400dff62  jz      short loc_1400DFF73
0x1400dff64  mov     edx, 17h
0x1400dff69  mov     ecx, ebx
0x1400dff6b  mov     r8, r15
0x1400dff6e  call    WPP_SF_
0x1400dff73  cmp     cs:UxKirNewUma, sil
0x1400dff7a  jz      short loc_1400DFF94
0x1400dff7c  test    byte ptr cs:xmmword_1401A2CA0+3, r14b
0x1400dff83  jz      short loc_1400DFF94
0x1400dff85  mov     edx, 18h
0x1400dff8a  mov     ecx, ebx
0x1400dff8c  mov     r8, r15
0x1400dff8f  call    WPP_SF_
0x1400dff94  cmp     cs:UxKirHttpBugFix26Q2, sil
0x1400dff9b  jz      short loc_1400DFFB5
0x1400dff9d  test    byte ptr cs:xmmword_1401A2CA0+3, r14b
0x1400dffa4  jz      short loc_1400DFFB5
0x1400dffa6  mov     edx, 19h
0x1400dffab  mov     ecx, ebx
0x1400dffad  mov     r8, r15
0x1400dffb0  call    WPP_SF_
0x1400dffb5  cmp     cs:UxKirQuicParseLengthCheck, sil
0x1400dffbc  jz      short loc_1400DFFD6
0x1400dffbe  test    byte ptr cs:xmmword_1401A2CA0+3, r14b
0x1400dffc5  jz      short loc_1400DFFD6
0x1400dffc7  mov     edx, 1Ah
0x1400dffcc  mov     ecx, ebx
0x1400dffce  mov     r8, r15
0x1400dffd1  call    WPP_SF_
0x1400dffd6  mov     ecx, 0FFFFh; GroupNumber
0x1400dffdb  mov     cs:UxNumberOfProcessors, esi
0x1400dffe1  call    cs:__imp_KeQueryMaximumProcessorCountEx
0x1400dffe8  nop     dword ptr [rax+rax+00h]
0x1400dffed  mov     cs:UxMaximumNumberOfProcessors, eax
0x1400dfff3  call    cs:__imp_KeQueryHighestNodeNumber
0x1400dfffa  nop     dword ptr [rax+rax+00h]
0x1400dffff  add     ax, r12w
0x1400e0003  lea     rcx, UxTotalPhysicalMemMB
0x1400e000a  mov     cs:UxNumberOfNodes, ax
0x1400e0011  call    UxGetPhysicalMemorySize
0x1400e0016  mov     ebx, eax
0x1400e0018  test    eax, eax
0x1400e001a  js      loc_1400E039A
0x1400e0020  lea     rdx, UxLowNonPagedPoolEvent
0x1400e0027  lea     rcx, aKernelobjectsL_0; "\\KernelObjects\\LowNonPagedPoolConditi"...
0x1400e002e  call    UxOpenNamedEvent
0x1400e0033  mov     ebx, eax
0x1400e0035  test    eax, eax
0x1400e0037  js      loc_1400E039A
0x1400e003d  lea     rdx, UxHighNonPagedPoolEvent
0x1400e0044  lea     rcx, aKernelobjectsH; "\\KernelObjects\\HighNonPagedPoolCondit"...
0x1400e004b  call    UxOpenNamedEvent
0x1400e0050  mov     ebx, eax
0x1400e0052  test    eax, eax
0x1400e0054  js      loc_1400E039A
0x1400e005a  lea     rdx, UxLowMemoryEvent
0x1400e0061  lea     rcx, aKernelobjectsL; "\\KernelObjects\\LowMemoryCondition"
0x1400e0068  call    UxOpenNamedEvent
0x1400e006d  mov     ebx, eax
0x1400e006f  test    eax, eax
0x1400e0071  js      loc_1400E039A
0x1400e0077  lea     rcx, [rbp+100h+VersionInformation]; lpVersionInformation
0x1400e007b  mov     [rbp+100h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x1400e0082  call    cs:__imp_RtlGetVersion
0x1400e0089  nop     dword ptr [rax+rax+00h]
0x1400e008e  mov     ebx, eax
0x1400e0090  test    eax, eax
0x1400e0092  js      loc_1400E039A
0x1400e0098  mov     al, [rbp+100h+var_46]
0x1400e009e  sub     al, r14b
0x1400e00a1  cmp     al, r12b
0x1400e00a4  setbe   cs:UxServerSystem
0x1400e00ab  call    cs:__imp_IoGetCurrentProcess
0x1400e00b2  nop     dword ptr [rax+rax+00h]
0x1400e00b7  mov     cs:UxSystemProcess, rax
0x1400e00be  call    HttpCmnInitializeStaticHttpCharsTable
0x1400e00c3  lea     rax, [rsp+200h+var_1A0]
0x1400e00c8  mov     [rsp+200h+ObjectAttributes.Length], 30h ; '0'
0x1400e00d0  xorps   xmm0, xmm0
0x1400e00d3  mov     [rbp+100h+ObjectAttributes.ObjectName], rax
0x1400e00d7  lea     r8, [rsp+200h+ObjectAttributes]; ObjectAttributes
0x1400e00dc  mov     [rsp+200h+ObjectAttributes.RootDirectory], rsi
0x1400e00e1  mov     edx, 20019h; DesiredAccess
0x1400e00e6  mov     [rbp+100h+ObjectAttributes.Attributes], 240h
0x1400e00ed  lea     rcx, [rsp+200h+KeyHandle]; KeyHandle
0x1400e00f2  movdqu  xmmword ptr [rbp+100h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400e00f7  call    cs:__imp_ZwOpenKey
0x1400e00fe  nop     dword ptr [rax+rax+00h]
0x1400e0103  mov     ebx, eax
0x1400e0105  test    eax, eax
0x1400e0107  jns     short loc_1400E0115
0x1400e0109  mov     rcx, rsi
0x1400e010c  mov     ebx, esi
0x1400e010e  mov     [rsp+200h+KeyHandle], rcx
0x1400e0113  jmp     short loc_1400E011A
0x1400e0115  mov     rcx, [rsp+200h+KeyHandle]
0x1400e011a  lea     r9, UxCompactMode
0x1400e0121  xor     r8d, r8d
0x1400e0124  lea     rdx, aCompactmode; "CompactMode"
0x1400e012b  call    UxReadBooleanSetting
0x1400e0130  cmp     cs:UxKirHttpBugFix25Q1, sil
0x1400e0137  jz      short loc_1400E0154
0x1400e0139  mov     rcx, [rsp+200h+KeyHandle]
0x1400e013e  lea     r9, UxEnableIrqlEnforcement
0x1400e0145  xor     r8d, r8d
0x1400e0148  lea     rdx, aEnableirqlenfo; "EnableIrqlEnforcement"
0x1400e014f  call    UxReadBooleanSetting
0x1400e0154  mov     rcx, [rsp+200h+KeyHandle]
0x1400e0159  lea     r9, UxSendEndpointInfoToASC
0x1400e0160  xor     r8d, r8d
0x1400e0163  lea     rdx, aSendendpointin; "SendEndpointInfoToAsc"
0x1400e016a  call    UxReadBooleanSetting
0x1400e016f  mov     rcx, [rsp+200h+KeyHandle]
0x1400e0174  lea     r9, UxTlsUseStaticServerHello
0x1400e017b  xor     r8d, r8d
  ... truncated ...
```
