# UxStartEnvironmentModule

- ea: `0x1c015e310`
- end: `0x1c015e610`
- name: `UxStartEnvironmentModule`
- size: `768`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x1c001a4b0`
- `0x1c001b900`
- `0x1c00d6f1c`
- `0x1c00d75bc`
- `0x1c00d7ec8`
- `0x1c00d7fe4`
- `0x1c0115030`
- `0x1c015e310`
- `0x1c015e618`

## import_xrefs

- `ntoskrnl!KeQueryHighestNodeNumber` at `0x1c015e396`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x1c015e396`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x1c015e384`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x1c015e384`
- `ntoskrnl!RtlGetVersion` at `0x1c015e42b`
- `ntoskrnl!RtlGetVersion` at `0x1c015e42b`
- `ntoskrnl!ZwOpenKey` at `0x1c015e4a2`
- `ntoskrnl!ZwOpenKey` at `0x1c015e4a2`
- `ntoskrnl!ZwClose` at `0x1c015e5cc`
- `ntoskrnl!ZwClose` at `0x1c015e5cc`
- `ntoskrnl!IoGetCurrentProcess` at `0x1c015e453`
- `ntoskrnl!IoGetCurrentProcess` at `0x1c015e453`
- `HAL!KeQueryPerformanceCounter` at `0x1c015e5aa`
- `HAL!KeQueryPerformanceCounter` at `0x1c015e5aa`

## string_xrefs

- `0x1c015e352`: `\Registry\Machine\System\CurrentControlSet\Services\Http\Parameters`
- `0x1c015e4c7`: `CompactMode`

## pseudocode

```c
__int64 UxStartEnvironmentModule()
{
  NTSTATUS PhysicalMemorySize; // ebx
  void *v1; // rcx
  void *KeyHandle; // [rsp+40h] [rbp-C0h] BYREF
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v5[2]; // [rsp+50h] [rbp-B0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE VersionInformation[284]; // [rsp+90h] [rbp-70h] BYREF

  memset(VersionInformation, 0, sizeof(VersionInformation));
  KeyHandle = 0;
  UxNumberOfProcessors = 0;
  v5[1] = L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\Http\\Parameters";
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v5[0] = 8913030;
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
            ObjectAttributes.RootDirectory = 0;
            ObjectAttributes.ObjectName = (PUNICODE_STRING)v5;
            ObjectAttributes.Length = 48;
            ObjectAttributes.Attributes = 576;
            *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
            PhysicalMemorySize = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
            if ( PhysicalMemorySize < 0 )
            {
              v1 = 0;
              KeyHandle = 0;
              PhysicalMemorySize = 0;
            }
            else
            {
              v1 = KeyHandle;
            }
            UxReadBooleanSetting(v1, L"CompactMode", 0, &UxCompactMode);
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
            UxReadBoundedULongSetting(
              (_DWORD)KeyHandle,
              (unsigned int)L"RssStatusCheckControl",
              1,
              0,
              2,
              0,
              (__int64)&UxRssEnabledCheckControl);
            UxReadBooleanSetting(KeyHandle, L"EnableHttp3", 0, &UxHttp3Enabled);
            UxReadBooleanSetting(KeyHandle, L"EnableAltSvc", 0, &UxAltSvcEnabled);
            PerformanceFrequency.QuadPart = 0;
            KeQueryPerformanceCounter(&PerformanceFrequency);
            UxPerformanceCounterPeriod = PerformanceFrequency.QuadPart;
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
  if ( PhysicalMemorySize < 0 )
    UxStopEnvironmentModule();
  return (unsigned int)PhysicalMemorySize;
}

```

## disassembly

```asm
0x1c015e310  mov     [rsp-8+arg_0], rbx
0x1c015e315  mov     [rsp-8+arg_8], r14
0x1c015e31a  push    rbp
0x1c015e31b  lea     rbp, [rsp-0C0h]
0x1c015e323  sub     rsp, 1C0h
0x1c015e32a  mov     rax, cs:__security_cookie
0x1c015e331  xor     rax, rsp
0x1c015e334  mov     [rbp+0C0h+var_10], rax
0x1c015e33b  xor     edx, edx; Val
0x1c015e33d  lea     rcx, [rbp+0C0h+VersionInformation]; void *
0x1c015e341  mov     r8d, 11Ch; Size
0x1c015e347  call    memset
0x1c015e34c  and     [rsp+1C0h+KeyHandle], 0
0x1c015e352  lea     rax, aRegistryMachin_7; "\\Registry\\Machine\\System\\CurrentCon"...
0x1c015e359  and     cs:UxNumberOfProcessors, 0
0x1c015e360  xorps   xmm0, xmm0
0x1c015e363  mov     ecx, 0FFFFh; GroupNumber
0x1c015e368  mov     [rsp+1C0h+var_168], rax
0x1c015e36d  movups  xmmword ptr [rsp+1C0h+ObjectAttributes.Length], xmm0
0x1c015e372  mov     [rsp+1C0h+var_170], 880086h
0x1c015e37b  movups  xmmword ptr [rsp+1C0h+ObjectAttributes.ObjectName], xmm0
0x1c015e380  movups  xmmword ptr [rbp+0C0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1c015e384  call    cs:__imp_KeQueryMaximumProcessorCountEx
0x1c015e38b  nop     dword ptr [rax+rax+00h]
0x1c015e390  mov     cs:UxMaximumNumberOfProcessors, eax
0x1c015e396  call    cs:__imp_KeQueryHighestNodeNumber
0x1c015e39d  nop     dword ptr [rax+rax+00h]
0x1c015e3a2  mov     r14d, 1
0x1c015e3a8  lea     rcx, UxTotalPhysicalMemMB
0x1c015e3af  add     ax, r14w
0x1c015e3b3  mov     cs:UxNumberOfNodes, ax
0x1c015e3ba  call    UxGetPhysicalMemorySize
0x1c015e3bf  mov     ebx, eax
0x1c015e3c1  test    eax, eax
0x1c015e3c3  js      loc_1C015E5C2
0x1c015e3c9  lea     rdx, UxLowNonPagedPoolEvent
0x1c015e3d0  lea     rcx, aKernelobjectsL_0; "\\KernelObjects\\LowNonPagedPoolConditi"...
0x1c015e3d7  call    UxOpenNamedEvent
0x1c015e3dc  mov     ebx, eax
0x1c015e3de  test    eax, eax
0x1c015e3e0  js      loc_1C015E5C2
0x1c015e3e6  lea     rdx, UxHighNonPagedPoolEvent
0x1c015e3ed  lea     rcx, aKernelobjectsH; "\\KernelObjects\\HighNonPagedPoolCondit"...
0x1c015e3f4  call    UxOpenNamedEvent
0x1c015e3f9  mov     ebx, eax
0x1c015e3fb  test    eax, eax
0x1c015e3fd  js      loc_1C015E5C2
0x1c015e403  lea     rdx, UxLowMemoryEvent
0x1c015e40a  lea     rcx, aKernelobjectsL; "\\KernelObjects\\LowMemoryCondition"
0x1c015e411  call    UxOpenNamedEvent
0x1c015e416  mov     ebx, eax
0x1c015e418  test    eax, eax
0x1c015e41a  js      loc_1C015E5C2
0x1c015e420  lea     rcx, [rbp+0C0h+VersionInformation]; lpVersionInformation
0x1c015e424  mov     [rbp+0C0h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x1c015e42b  call    cs:__imp_RtlGetVersion
0x1c015e432  nop     dword ptr [rax+rax+00h]
0x1c015e437  mov     ebx, eax
0x1c015e439  test    eax, eax
0x1c015e43b  js      loc_1C015E5C2
0x1c015e441  mov     al, [rbp+0C0h+var_16]
0x1c015e447  sub     al, 2
0x1c015e449  cmp     al, r14b
0x1c015e44c  setbe   cs:UxServerSystem
0x1c015e453  call    cs:__imp_IoGetCurrentProcess
0x1c015e45a  nop     dword ptr [rax+rax+00h]
0x1c015e45f  mov     cs:UxSystemProcess, rax
0x1c015e466  call    HttpCmnInitializeStaticHttpCharsTable
0x1c015e46b  and     [rsp+1C0h+ObjectAttributes.RootDirectory], 0
0x1c015e471  lea     rax, [rsp+1C0h+var_170]
0x1c015e476  xorps   xmm0, xmm0
0x1c015e479  mov     [rsp+1C0h+ObjectAttributes.ObjectName], rax
0x1c015e47e  lea     r8, [rsp+1C0h+ObjectAttributes]; ObjectAttributes
0x1c015e483  mov     [rsp+1C0h+ObjectAttributes.Length], 30h ; '0'
0x1c015e48b  mov     edx, 20019h; DesiredAccess
0x1c015e490  mov     [rsp+1C0h+ObjectAttributes.Attributes], 240h
0x1c015e498  lea     rcx, [rsp+1C0h+KeyHandle]; KeyHandle
0x1c015e49d  movdqu  xmmword ptr [rbp+0C0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1c015e4a2  call    cs:__imp_ZwOpenKey
0x1c015e4a9  nop     dword ptr [rax+rax+00h]
0x1c015e4ae  mov     ebx, eax
0x1c015e4b0  test    eax, eax
0x1c015e4b2  js      loc_1C015FB6E
0x1c015e4b8  mov     rcx, [rsp+1C0h+KeyHandle]
0x1c015e4bd  lea     r9, UxCompactMode
0x1c015e4c4  xor     r8d, r8d
0x1c015e4c7  lea     rdx, aCompactmode; "CompactMode"
0x1c015e4ce  call    UxReadBooleanSetting
0x1c015e4d3  mov     rcx, [rsp+1C0h+KeyHandle]
0x1c015e4d8  lea     r9, UxSendEndpointInfoToASC
0x1c015e4df  xor     r8d, r8d
0x1c015e4e2  lea     rdx, aSendendpointin; "SendEndpointInfoToAsc"
0x1c015e4e9  call    UxReadBooleanSetting
0x1c015e4ee  mov     rcx, [rsp+1C0h+KeyHandle]
0x1c015e4f3  lea     r9, UxTlsUseStaticServerHello
0x1c015e4fa  xor     r8d, r8d
0x1c015e4fd  lea     rdx, aTlsusestaticse; "TlsUseStaticServerHello"
0x1c015e504  call    UxReadBooleanSetting
0x1c015e509  mov     rcx, [rsp+1C0h+KeyHandle]
0x1c015e50e  lea     rax, UxAscThrottleLimit
0x1c015e515  mov     [rsp+1C0h+var_190], rax
0x1c015e51a  lea     rdx, aAscthrottlelim; "AscThrottleLimit"
0x1c015e521  and     [rsp+1C0h+var_198], 0
0x1c015e526  xor     r9d, r9d
0x1c015e529  xor     r8d, r8d
0x1c015e52c  mov     [rsp+1C0h+var_1A0], 7FFFFFFFh
0x1c015e534  call    UxReadBoundedULongSetting
0x1c015e539  mov     rcx, [rsp+1C0h+KeyHandle]
0x1c015e53e  lea     rax, UxRssEnabledCheckControl
0x1c015e545  mov     [rsp+1C0h+var_190], rax
0x1c015e54a  lea     rdx, aRssstatuscheck; "RssStatusCheckControl"
0x1c015e551  and     [rsp+1C0h+var_198], 0
0x1c015e556  xor     r9d, r9d
0x1c015e559  mov     r8d, r14d
0x1c015e55c  mov     [rsp+1C0h+var_1A0], 2
0x1c015e564  call    UxReadBoundedULongSetting
0x1c015e569  mov     rcx, [rsp+1C0h+KeyHandle]
0x1c015e56e  lea     r9, UxHttp3Enabled
0x1c015e575  xor     r8d, r8d
0x1c015e578  lea     rdx, aEnablehttp3; "EnableHttp3"
0x1c015e57f  call    UxReadBooleanSetting
0x1c015e584  mov     rcx, [rsp+1C0h+KeyHandle]
0x1c015e589  lea     r9, UxAltSvcEnabled
0x1c015e590  xor     r8d, r8d
0x1c015e593  lea     rdx, aEnablealtsvc; "EnableAltSvc"
0x1c015e59a  call    UxReadBooleanSetting
0x1c015e59f  and     qword ptr [rsp+1C0h+PerformanceFrequency], 0
0x1c015e5a5  lea     rcx, [rsp+1C0h+PerformanceFrequency]; PerformanceFrequency
0x1c015e5aa  call    cs:__imp_KeQueryPerformanceCounter
0x1c015e5b1  nop     dword ptr [rax+rax+00h]
0x1c015e5b6  mov     rax, qword ptr [rsp+1C0h+PerformanceFrequency]
0x1c015e5bb  mov     cs:UxPerformanceCounterPeriod, rax
0x1c015e5c2  mov     rcx, [rsp+1C0h+KeyHandle]; Handle
0x1c015e5c7  test    rcx, rcx
0x1c015e5ca  jz      short loc_1C015E5DE
0x1c015e5cc  call    cs:__imp_ZwClose
0x1c015e5d3  nop     dword ptr [rax+rax+00h]
0x1c015e5d8  and     [rsp+1C0h+KeyHandle], 0
0x1c015e5de  test    ebx, ebx
0x1c015e5e0  js      short loc_1C015E609
0x1c015e5e2  mov     eax, ebx
0x1c015e5e4  mov     rcx, [rbp+0C0h+var_10]
0x1c015e5eb  xor     rcx, rsp; StackCookie
0x1c015e5ee  call    __security_check_cookie
0x1c015e5f3  lea     r11, [rsp+1C0h+var_s0]
0x1c015e5fb  mov     rbx, [r11+10h]
0x1c015e5ff  mov     r14, [r11+18h]
0x1c015e603  mov     rsp, r11
0x1c015e606  pop     rbp
0x1c015e607  retn
0x1c015e609  call    UxStopEnvironmentModule
0x1c015e60e  jmp     short loc_1C015E5E2
0x1c015fb6e  xor     ecx, ecx
0x1c015fb70  mov     [rsp+1C0h+KeyHandle], rcx
0x1c015fb75  xor     ebx, ebx
0x1c015fb77  jmp     loc_1C015E4BD
```
