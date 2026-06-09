# DriverEntry

- ea: `0x180013078`
- end: `0x18001353f`
- name: `DriverEntry`
- size: `1223`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180013010`

## callees

- `0x180001430`
- `0x180001f70`
- `0x180002480`
- `0x18000a32c`
- `0x18000a3fc`
- `0x18000a490`
- `0x180013078`

## import_xrefs

- `ntoskrnl!FsRtlQueryMaximumVirtualDiskNestingLevel` at `0x1800131de`
- `ntoskrnl!FsRtlQueryMaximumVirtualDiskNestingLevel` at `0x1800131de`
- `ntoskrnl!ZwQueryValueKey` at `0x1800132ff`
- `ntoskrnl!ZwQueryValueKey` at `0x18001336e`
- `ntoskrnl!ZwQueryValueKey` at `0x1800133c0`
- `ntoskrnl!ZwQueryValueKey` at `0x18001348d`
- `ntoskrnl!ZwQueryValueKey` at `0x1800132ff`
- `ntoskrnl!ZwQueryValueKey` at `0x18001336e`
- `ntoskrnl!ZwQueryValueKey` at `0x1800133c0`
- `ntoskrnl!ZwQueryValueKey` at `0x18001348d`
- `ntoskrnl!ExInitializeResourceLite` at `0x1800130f0`
- `ntoskrnl!ExInitializeResourceLite` at `0x1800130f0`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800131d2`
- `ntoskrnl!RtlInitUnicodeString` at `0x18001325b`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800132d3`
- `ntoskrnl!RtlInitUnicodeString` at `0x180013342`
- `ntoskrnl!RtlInitUnicodeString` at `0x180013394`
- `ntoskrnl!RtlInitUnicodeString` at `0x180013407`
- `ntoskrnl!RtlInitUnicodeString` at `0x180013461`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800131d2`
- `ntoskrnl!RtlInitUnicodeString` at `0x18001325b`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800132d3`
- `ntoskrnl!RtlInitUnicodeString` at `0x180013342`
- `ntoskrnl!RtlInitUnicodeString` at `0x180013394`
- `ntoskrnl!RtlInitUnicodeString` at `0x180013407`
- `ntoskrnl!RtlInitUnicodeString` at `0x180013461`
- `ntoskrnl!KdDebuggerNotPresent` at `0x18001332b`
- `ntoskrnl!KdDebuggerEnabled` at `0x18001331f`
- `ntoskrnl!ZwClose` at `0x1800132ac`
- `ntoskrnl!ZwClose` at `0x1800134ac`
- `ntoskrnl!ZwClose` at `0x1800134bc`
- `ntoskrnl!ZwClose` at `0x1800132ac`
- `ntoskrnl!ZwClose` at `0x1800134ac`
- `ntoskrnl!ZwClose` at `0x1800134bc`
- `ntoskrnl!KeInitializeEvent` at `0x180013132`
- `ntoskrnl!KeInitializeEvent` at `0x180013132`
- `ntoskrnl!FsRtlAreVolumeStartupApplicationsComplete` at `0x1800134d1`
- `ntoskrnl!FsRtlAreVolumeStartupApplicationsComplete` at `0x1800134d1`
- `ntoskrnl!ZwOpenKey` at `0x180013228`
- `ntoskrnl!ZwOpenKey` at `0x18001329a`
- `ntoskrnl!ZwOpenKey` at `0x180013446`
- `ntoskrnl!ZwOpenKey` at `0x180013228`
- `ntoskrnl!ZwOpenKey` at `0x18001329a`
- `ntoskrnl!ZwOpenKey` at `0x180013446`

## string_xrefs

- `0x1800131c7`: `\Registry\Machine\System\CurrentControlSet\Control\FileSystem\GroupPolicyKeys`
- `0x1800132c8`: `VirtualDiskNoLocalMount`
- `0x180013389`: `VirtualDiskExpandOnMount`
- `0x1800133f8`: `AccessControl`
- `0x180013456`: `ISOMountAllowNormalUser`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  unsigned int v4; // edi
  struct _UNICODE_STRING *p_DestinationString; // rax
  NTSTATUS v6; // ebx
  __int64 v7; // rcx
  ULONG ResultLength; // [rsp+30h] [rbp-79h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-71h] BYREF
  HANDLE Handle; // [rsp+40h] [rbp-69h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+48h] [rbp-61h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-51h] BYREF
  struct _UNICODE_STRING v14; // [rsp+88h] [rbp-21h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-11h] BYREF
  _BYTE KeyValueInformation[12]; // [rsp+A8h] [rbp-1h] BYREF
  int v17; // [rsp+B4h] [rbp+Bh]

  KeyHandle = 0;
  ResultLength = 0;
  v4 = 0;
  memset(&ObjectAttributes, 0, 44);
  ValueName = 0;
  DestinationString = 0;
  memset(&dword_180005104, 0, 0x114u);
  Globals = 18362384;
  ExInitializeResourceLite(&Resource);
  qword_1800051A8 = (__int64)&qword_1800051A0;
  qword_1800051A0 = (__int64)&qword_1800051A0;
  qword_1800051B8 = (__int64)&qword_1800051B0;
  qword_1800051B0 = (__int64)&qword_1800051B0;
  KeInitializeEvent(&Event, NotificationEvent, 0);
  Driver = DriverObject;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_VdrvRootTraceGuid;
  dword_1800051C4 = 1;
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_6e0896578ce0378c051a248e53d8716f_Traceguids);
  }
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\FileSystem\\GroupPolicyKeys");
  dword_1800051C0 = FsRtlQueryMaximumVirtualDiskNestingLevel();
  do
  {
    while ( 1 )
    {
      ObjectAttributes.Length = 48;
      ++v4;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 576;
      p_DestinationString = &DestinationString;
      if ( v4 == 1 )
        p_DestinationString = RegistryPath;
      ObjectAttributes.ObjectName = p_DestinationString;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) < 0 )
        break;
      if ( v4 == 1 )
      {
        Handle = 0;
        v14 = 0;
        RtlInitUnicodeString(&v14, L"Parameters");
        ObjectAttributes.RootDirectory = KeyHandle;
        ObjectAttributes.Length = 48;
        ObjectAttributes.ObjectName = &v14;
        ObjectAttributes.Attributes = 576;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        v6 = ZwOpenKey(&Handle, 0x20019u, &ObjectAttributes);
        ZwClose(KeyHandle);
        KeyHandle = Handle;
        if ( v6 < 0 )
          continue;
      }
      RtlInitUnicodeString(&ValueName, L"VirtualDiskNoLocalMount");
      if ( ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, KeyValueInformation, 0x14u, &ResultLength) >= 0 )
        byte_18000519A = v17 != 0;
      if ( v4 == 1 )
      {
        if ( (_BYTE)KdDebuggerEnabled )
        {
          if ( !(_BYTE)KdDebuggerNotPresent )
          {
            RtlInitUnicodeString(&ValueName, L"RelaxedTestMode");
            if ( ZwQueryValueKey(
                   KeyHandle,
                   &ValueName,
                   KeyValuePartialInformation,
                   KeyValueInformation,
                   0x14u,
                   &ResultLength) >= 0 )
              byte_18000519C = v17 != 0;
          }
        }
      }
      RtlInitUnicodeString(&ValueName, L"VirtualDiskExpandOnMount");
      if ( ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, KeyValueInformation, 0x14u, &ResultLength) >= 0
        && ((v17 - 1) & 0xFFFFFFFC) == 0
        && v17 != 3 )
      {
        dword_1800051C4 = v17;
      }
      if ( v4 == 1 )
      {
        Handle = 0;
        v14 = 0;
        RtlInitUnicodeString(&v14, L"AccessControl");
        ObjectAttributes.RootDirectory = KeyHandle;
        ObjectAttributes.Length = 48;
        ObjectAttributes.ObjectName = &v14;
        ObjectAttributes.Attributes = 576;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        if ( ZwOpenKey(&Handle, 0x20019u, &ObjectAttributes) >= 0 )
        {
          RtlInitUnicodeString(&ValueName, L"ISOMountAllowNormalUser");
          if ( ZwQueryValueKey(
                 Handle,
                 &ValueName,
                 KeyValuePartialInformation,
                 KeyValueInformation,
                 0x14u,
                 &ResultLength) >= 0 )
            byte_18000519B = v17 != 0;
          ZwClose(Handle);
        }
      }
      ZwClose(KeyHandle);
      break;
    }
  }
  while ( v4 < 2 );
  if ( !FsRtlAreVolumeStartupApplicationsComplete() )
  {
    LOBYTE(v7) = 1;
    FsDepRegisterUnregisterForBugchecks(v7, 0);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_6e0896578ce0378c051a248e53d8716f_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x180013078  push    rbp
0x18001307a  push    rbx
0x18001307b  push    rsi
0x18001307c  push    rdi
0x18001307d  push    r14
0x18001307f  push    r15
0x180013081  lea     rbp, [rsp-2Fh]
0x180013086  sub     rsp, 0D8h
0x18001308d  mov     rax, cs:__security_cookie
0x180013094  xor     rax, rsp
0x180013097  mov     [rbp+57h+var_40], rax
0x18001309b  xorps   xmm0, xmm0
0x18001309e  xor     r14d, r14d
0x1800130a1  mov     rsi, rdx
0x1800130a4  mov     [rbp+57h+KeyHandle], r14
0x1800130a8  mov     rbx, rcx
0x1800130ab  mov     [rbp+57h+var_D0], r14d
0x1800130af  xorps   xmm1, xmm1
0x1800130b2  lea     rcx, dword_180005104; void *
0x1800130b9  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800130bd  xor     eax, eax
0x1800130bf  xor     edx, edx; Val
0x1800130c1  mov     r8d, 114h; Size
0x1800130c7  mov     edi, r14d
0x1800130ca  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800130ce  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800130d2  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm0
0x1800130d6  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x1800130da  call    memset
0x1800130df  lea     rcx, Resource; Resource
0x1800130e6  mov     cs:Globals, 1183010h
0x1800130f0  call    cs:__imp_ExInitializeResourceLite
0x1800130f7  nop     dword ptr [rax+rax+00h]
0x1800130fc  lea     rax, qword_1800051A0
0x180013103  xor     r8d, r8d; State
0x180013106  mov     cs:qword_1800051A8, rax
0x18001310d  lea     rcx, Event; Event
0x180013114  mov     cs:qword_1800051A0, rax
0x18001311b  xor     edx, edx; Type
0x18001311d  lea     rax, qword_1800051B0
0x180013124  mov     cs:qword_1800051B8, rax
0x18001312b  mov     cs:qword_1800051B0, rax
0x180013132  call    cs:__imp_KeInitializeEvent
0x180013139  nop     dword ptr [rax+rax+00h]
0x18001313e  lea     rax, WPP_ThisDir_CTLGUID_VdrvRootTraceGuid
0x180013145  mov     cs:Driver, rbx
0x18001314c  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x180013153  mov     cs:dword_1800051C4, 1
0x18001315d  mov     qword ptr cs:WPP_MAIN_CB.Type, r14
0x180013164  mov     cs:WPP_MAIN_CB.NextDevice, r14
0x18001316b  mov     cs:WPP_MAIN_CB.CurrentIrp, r14
0x180013172  mov     cs:WPP_MAIN_CB.Timer, 1
0x18001317d  call    WppLoadTracingSupport
0x180013182  mov     cs:WPP_MAIN_CB.CurrentIrp, r14
0x180013189  call    WppInitKm
0x18001318e  mov     rcx, cs:WPP_GLOBAL_Control
0x180013195  lea     rax, WPP_GLOBAL_Control
0x18001319c  lea     r15d, [r14+2]
0x1800131a0  cmp     rcx, rax
0x1800131a3  jz      short loc_1800131C7
0x1800131a5  mov     eax, [rcx+2Ch]
0x1800131a8  test    r15b, al
0x1800131ab  jz      short loc_1800131C7
0x1800131ad  cmp     byte ptr [rcx+29h], 4
0x1800131b1  jb      short loc_1800131C7
0x1800131b3  mov     rcx, [rcx+18h]
0x1800131b7  lea     edx, [r14+0Ah]
0x1800131bb  lea     r8, WPP_6e0896578ce0378c051a248e53d8716f_Traceguids
0x1800131c2  call    WPP_SF_
0x1800131c7  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x1800131ce  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800131d2  call    cs:__imp_RtlInitUnicodeString
0x1800131d9  nop     dword ptr [rax+rax+00h]
0x1800131de  call    cs:__imp_FsRtlQueryMaximumVirtualDiskNestingLevel
0x1800131e5  nop     dword ptr [rax+rax+00h]
0x1800131ea  mov     cs:dword_1800051C0, eax
0x1800131f0  xorps   xmm0, xmm0
0x1800131f3  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800131fa  inc     edi
0x1800131fc  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x180013200  cmp     edi, 1
0x180013203  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x18001320a  lea     rax, [rbp+57h+DestinationString]
0x18001320e  mov     edx, 20019h; DesiredAccess
0x180013213  cmovz   rax, rsi
0x180013217  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18001321b  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18001321f  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180013223  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180013228  call    cs:__imp_ZwOpenKey
0x18001322f  nop     dword ptr [rax+rax+00h]
0x180013234  test    eax, eax
0x180013236  js      loc_1800134C8
0x18001323c  cmp     edi, 1
0x18001323f  jnz     loc_1800132C8
0x180013245  xorps   xmm0, xmm0
0x180013248  mov     [rbp+57h+Handle], r14
0x18001324c  lea     rdx, aParameters; "Parameters"
0x180013253  lea     rcx, [rbp+57h+var_78]; DestinationString
0x180013257  movups  xmmword ptr [rbp+57h+var_78.Length], xmm0
0x18001325b  call    cs:__imp_RtlInitUnicodeString
0x180013262  nop     dword ptr [rax+rax+00h]
0x180013267  mov     rax, [rbp+57h+KeyHandle]
0x18001326b  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18001326f  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x180013273  lea     rcx, [rbp+57h+Handle]; KeyHandle
0x180013277  lea     rax, [rbp+57h+var_78]
0x18001327b  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180013282  xorps   xmm0, xmm0
0x180013285  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180013289  mov     edx, 20019h; DesiredAccess
0x18001328e  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x180013295  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001329a  call    cs:__imp_ZwOpenKey
0x1800132a1  nop     dword ptr [rax+rax+00h]
0x1800132a6  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1800132aa  mov     ebx, eax
0x1800132ac  call    cs:__imp_ZwClose
0x1800132b3  nop     dword ptr [rax+rax+00h]
0x1800132b8  mov     rcx, [rbp+57h+Handle]
0x1800132bc  mov     [rbp+57h+KeyHandle], rcx
0x1800132c0  test    ebx, ebx
0x1800132c2  js      loc_1800131F0
0x1800132c8  lea     rdx, aVirtualdisknol; "VirtualDiskNoLocalMount"
0x1800132cf  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x1800132d3  call    cs:__imp_RtlInitUnicodeString
0x1800132da  nop     dword ptr [rax+rax+00h]
0x1800132df  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800132e3  lea     rax, [rbp+57h+var_D0]
0x1800132e7  mov     [rsp+100h+ResultLength], rax; ResultLength
0x1800132ec  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x1800132f0  mov     r8d, r15d; KeyValueInformationClass
0x1800132f3  mov     [rsp+100h+Length], 14h; Length
0x1800132fb  lea     rdx, [rbp+57h+ValueName]; ValueName
0x1800132ff  call    cs:__imp_ZwQueryValueKey
0x180013306  nop     dword ptr [rax+rax+00h]
0x18001330b  test    eax, eax
0x18001330d  js      short loc_18001331A
0x18001330f  cmp     [rbp+57h+var_4C], r14d
0x180013313  setnz   cs:byte_18000519A
0x18001331a  cmp     edi, 1
0x18001331d  jnz     short loc_180013389
0x18001331f  mov     rax, cs:KdDebuggerEnabled
0x180013326  cmp     [rax], r14b
0x180013329  jz      short loc_180013389
0x18001332b  mov     rax, cs:KdDebuggerNotPresent
0x180013332  cmp     [rax], r14b
0x180013335  jnz     short loc_180013389
0x180013337  lea     rdx, aRelaxedtestmod; "RelaxedTestMode"
0x18001333e  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x180013342  call    cs:__imp_RtlInitUnicodeString
0x180013349  nop     dword ptr [rax+rax+00h]
0x18001334e  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180013352  lea     rax, [rbp+57h+var_D0]
0x180013356  mov     [rsp+100h+ResultLength], rax; ResultLength
0x18001335b  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x18001335f  mov     r8d, r15d; KeyValueInformationClass
0x180013362  mov     [rsp+100h+Length], 14h; Length
0x18001336a  lea     rdx, [rbp+57h+ValueName]; ValueName
0x18001336e  call    cs:__imp_ZwQueryValueKey
0x180013375  nop     dword ptr [rax+rax+00h]
0x18001337a  test    eax, eax
0x18001337c  js      short loc_180013389
0x18001337e  cmp     [rbp+57h+var_4C], r14d
0x180013382  setnz   cs:byte_18000519C
0x180013389  lea     rdx, aVirtualdiskexp; "VirtualDiskExpandOnMount"
0x180013390  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x180013394  call    cs:__imp_RtlInitUnicodeString
0x18001339b  nop     dword ptr [rax+rax+00h]
0x1800133a0  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800133a4  lea     rax, [rbp+57h+var_D0]
0x1800133a8  mov     [rsp+100h+ResultLength], rax; ResultLength
0x1800133ad  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x1800133b1  mov     r8d, r15d; KeyValueInformationClass
0x1800133b4  mov     [rsp+100h+Length], 14h; Length
0x1800133bc  lea     rdx, [rbp+57h+ValueName]; ValueName
0x1800133c0  call    cs:__imp_ZwQueryValueKey
0x1800133c7  nop     dword ptr [rax+rax+00h]
0x1800133cc  test    eax, eax
0x1800133ce  js      short loc_1800133E8
0x1800133d0  mov     ecx, [rbp+57h+var_4C]
0x1800133d3  lea     eax, [rcx-1]
0x1800133d6  test    eax, 0FFFFFFFCh
0x1800133db  jnz     short loc_1800133E8
0x1800133dd  cmp     ecx, 3
0x1800133e0  jz      short loc_1800133E8
0x1800133e2  mov     cs:dword_1800051C4, ecx
0x1800133e8  cmp     edi, 1
0x1800133eb  jnz     loc_1800134B8
0x1800133f1  xorps   xmm0, xmm0
0x1800133f4  mov     [rbp+57h+Handle], r14
0x1800133f8  lea     rdx, aAccesscontrol; "AccessControl"
0x1800133ff  lea     rcx, [rbp+57h+var_78]; DestinationString
0x180013403  movups  xmmword ptr [rbp+57h+var_78.Length], xmm0
0x180013407  call    cs:__imp_RtlInitUnicodeString
0x18001340e  nop     dword ptr [rax+rax+00h]
0x180013413  mov     rax, [rbp+57h+KeyHandle]
0x180013417  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18001341b  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x18001341f  lea     rcx, [rbp+57h+Handle]; KeyHandle
0x180013423  lea     rax, [rbp+57h+var_78]
0x180013427  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18001342e  xorps   xmm0, xmm0
0x180013431  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180013435  mov     edx, 20019h; DesiredAccess
0x18001343a  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x180013441  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180013446  call    cs:__imp_ZwOpenKey
0x18001344d  nop     dword ptr [rax+rax+00h]
0x180013452  test    eax, eax
0x180013454  js      short loc_1800134B8
0x180013456  lea     rdx, aIsomountallown; "ISOMountAllowNormalUser"
0x18001345d  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x180013461  call    cs:__imp_RtlInitUnicodeString
0x180013468  nop     dword ptr [rax+rax+00h]
0x18001346d  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x180013471  lea     rax, [rbp+57h+var_D0]
0x180013475  mov     [rsp+100h+ResultLength], rax; ResultLength
0x18001347a  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x18001347e  mov     r8d, r15d; KeyValueInformationClass
0x180013481  mov     [rsp+100h+Length], 14h; Length
0x180013489  lea     rdx, [rbp+57h+ValueName]; ValueName
0x18001348d  call    cs:__imp_ZwQueryValueKey
0x180013494  nop     dword ptr [rax+rax+00h]
0x180013499  test    eax, eax
0x18001349b  js      short loc_1800134A8
0x18001349d  cmp     [rbp+57h+var_4C], r14d
0x1800134a1  setnz   cs:byte_18000519B
0x1800134a8  mov     rcx, [rbp+57h+Handle]; Handle
0x1800134ac  call    cs:__imp_ZwClose
0x1800134b3  nop     dword ptr [rax+rax+00h]
0x1800134b8  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1800134bc  call    cs:__imp_ZwClose
0x1800134c3  nop     dword ptr [rax+rax+00h]
0x1800134c8  cmp     edi, r15d
0x1800134cb  jb      loc_1800131F0
0x1800134d1  call    cs:__imp_FsRtlAreVolumeStartupApplicationsComplete
0x1800134d8  nop     dword ptr [rax+rax+00h]
0x1800134dd  test    al, al
0x1800134df  jnz     short loc_1800134EA
0x1800134e1  xor     edx, edx
0x1800134e3  mov     cl, 1
0x1800134e5  call    FsDepRegisterUnregisterForBugchecks
0x1800134ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800134f1  lea     rax, WPP_GLOBAL_Control
0x1800134f8  cmp     rcx, rax
0x1800134fb  jz      short loc_180013520
0x1800134fd  mov     eax, [rcx+2Ch]
0x180013500  test    r15b, al
0x180013503  jz      short loc_180013520
0x180013505  cmp     byte ptr [rcx+29h], 4
0x180013509  jb      short loc_180013520
0x18001350b  mov     rcx, [rcx+18h]
0x18001350f  lea     r8, WPP_6e0896578ce0378c051a248e53d8716f_Traceguids
0x180013516  mov     edx, 0Bh
0x18001351b  call    WPP_SF_
0x180013520  xor     eax, eax
0x180013522  mov     rcx, [rbp+57h+var_40]
0x180013526  xor     rcx, rsp; StackCookie
0x180013529  call    __security_check_cookie
0x18001352e  add     rsp, 0D8h
0x180013535  pop     r15
0x180013537  pop     r14
0x180013539  pop     rdi
0x18001353a  pop     rsi
0x18001353b  pop     rbx
0x18001353c  pop     rbp
0x18001353d  retn
```
