# DriverEntry

- ea: `0x14000b080`
- end: `0x14000b3c0`
- name: `DriverEntry`
- size: `832`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `13`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14000b010`

## callees

- `0x1400016c0`
- `0x1400018f0`
- `0x140001b40`
- `0x1400080e0`
- `0x140008230`
- `0x140008394`
- `0x1400085ac`
- `0x1400088cc`
- `0x140008920`
- `0x140009a50`
- `0x14000a320`
- `0x14000a5d0`
- `0x14000b080`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14000b248`
- `ntoskrnl!ZwClose` at `0x14000b25a`
- `ntoskrnl!ZwClose` at `0x14000b248`
- `ntoskrnl!ZwClose` at `0x14000b25a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b374`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b374`
- `ntoskrnl!ZwQueryValueKey` at `0x14000b222`
- `ntoskrnl!ZwQueryValueKey` at `0x14000b222`
- `ntoskrnl!ExAllocatePool2` at `0x14000b127`
- `ntoskrnl!ExAllocatePool2` at `0x14000b127`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000b19d`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000b1f3`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000b19d`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000b1f3`
- `ntoskrnl!ZwOpenKey` at `0x14000b1d8`
- `ntoskrnl!ZwOpenKey` at `0x14000b1d8`
- `FLTMGR!FltStartFiltering` at `0x14000b2f9`
- `FLTMGR!FltStartFiltering` at `0x14000b2f9`
- `FLTMGR!FltRegisterFilter` at `0x14000b2dc`
- `FLTMGR!FltRegisterFilter` at `0x14000b2dc`
- `FLTMGR!FltUnregisterFilter` at `0x14000b326`
- `FLTMGR!FltUnregisterFilter` at `0x14000b326`

## string_xrefs

- `0x14000b17c`: `\Registry\Machine\Software\Microsoft\Windows\CurrentVersion\NetworkServiceTriggers\Config\`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  int v3; // r14d
  int v4; // esi
  _OWORD *Pool2; // rax
  int v6; // edi
  int updated; // ebx
  _QWORD *DeviceExtension; // rcx
  _QWORD *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rdx
  NTSTATUS result; // eax
  struct _FLT_FILTER *v13; // rcx
  void *KeyHandle; // [rsp+30h] [rbp-59h] BYREF
  ULONG ResultLength; // [rsp+38h] [rbp-51h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-49h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-19h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+80h] [rbp-9h] BYREF
  _BYTE KeyValueInformation[12]; // [rsp+90h] [rbp+7h] BYREF
  __int64 v20; // [rsp+9Ch] [rbp+13h]

  ResultLength = 0;
  KeyHandle = 0;
  DriverObject->DriverUnload = (PDRIVER_UNLOAD)DriverUnload;
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_NptrigTracing;
  memset(&ObjectAttributes, 0, 44);
  v3 = 0;
  v4 = 0;
  WPP_MAIN_CB.NextDevice = 0;
  DestinationString = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  ValueName = 0;
  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  WppLoadTracingSupport(DriverObject, RegistryPath);
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm();
  Pool2 = (_OWORD *)ExAllocatePool2(64, 64, 1735684174);
  WPP_MAIN_CB.DeviceExtension = Pool2;
  if ( !Pool2 )
  {
    v6 = 0;
    updated = -1073741801;
    goto LABEL_13;
  }
  *Pool2 = 0;
  Pool2[1] = 0;
  Pool2[2] = 0;
  Pool2[3] = 0;
  NptrigInitializeLock(Pool2);
  NptrigInitializeLock((char *)WPP_MAIN_CB.DeviceExtension + 24);
  DeviceExtension = WPP_MAIN_CB.DeviceExtension;
  v9 = (char *)WPP_MAIN_CB.DeviceExtension + 8;
  *((_QWORD *)WPP_MAIN_CB.DeviceExtension + 2) = (char *)WPP_MAIN_CB.DeviceExtension + 8;
  *v9 = v9;
  DeviceExtension[5] = DeviceExtension + 4;
  DeviceExtension[4] = DeviceExtension + 4;
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\Software\\Microsoft\\Windows\\CurrentVersion\\NetworkServiceTriggers\\Config\\");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&KeyHandle, 0x80000000, &ObjectAttributes) < 0 )
    goto LABEL_7;
  RtlInitUnicodeString(&ValueName, L"NamedPipeTimeout");
  if ( ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, KeyValueInformation, 0x18u, &ResultLength) < 0 )
  {
    ZwClose(KeyHandle);
LABEL_7:
    *((_QWORD *)WPP_MAIN_CB.DeviceExtension + 6) = -300000000;
    goto LABEL_8;
  }
  *((_QWORD *)WPP_MAIN_CB.DeviceExtension + 6) = -v20;
  ZwClose(KeyHandle);
LABEL_8:
  McGenEventRegister_EtwRegister(
    NPTRIG_ETW_PROVIDER_GUID,
    v10,
    &NPTRIG_ETW_PROVIDER_GUID_Context,
    &NPTRIG_ETW_PROVIDER_GUID_Context);
  v6 = 1;
  McGenEventRegister_EtwRegister(
    SERVICE_TRIGGER_PERF_EVENT_GUID,
    v11,
    &SERVICE_TRIGGER_PERF_EVENT_GUID_Context,
    &SERVICE_TRIGGER_PERF_EVENT_GUID_Context);
  updated = RtdsReaderInitialize();
  if ( updated >= 0 )
  {
    v3 = 1;
    updated = RtdsRegisterUpdateCallback();
    if ( updated >= 0 )
    {
      updated = FltRegisterFilter(DriverObject, &NptrigRegistration, (PFLT_FILTER *)WPP_MAIN_CB.DeviceExtension + 7);
      if ( updated >= 0 )
      {
        result = FltStartFiltering(*((PFLT_FILTER *)WPP_MAIN_CB.DeviceExtension + 7));
        updated = result;
        if ( result >= 0 )
          return result;
      }
      v4 = 1;
    }
  }
LABEL_13:
  if ( WPP_MAIN_CB.DeviceExtension )
  {
    v13 = (struct _FLT_FILTER *)*((_QWORD *)WPP_MAIN_CB.DeviceExtension + 7);
    if ( v13 )
      FltUnregisterFilter(v13);
    if ( v4 )
      RtdsUnregisterUpdateCallback(&NAMED_PIPE_EVENT_GUID);
    if ( v3 )
      RtdsReaderShutdown();
    NptrigDeleteLock((char *)WPP_MAIN_CB.DeviceExtension + 24);
    NptrigDeleteLock(WPP_MAIN_CB.DeviceExtension);
    ExFreePoolWithTag(WPP_MAIN_CB.DeviceExtension, 0x6774704Eu);
    if ( v6 )
    {
      McGenEventUnregister_EtwUnregister(&NPTRIG_ETW_PROVIDER_GUID_Context);
      McGenEventUnregister_EtwUnregister(&SERVICE_TRIGGER_PERF_EVENT_GUID_Context);
    }
  }
  WppCleanupKm();
  return updated;
}

```

## disassembly

```asm
0x14000b080  push    rbp
0x14000b082  push    rbx
0x14000b083  push    rsi
0x14000b084  push    rdi
0x14000b085  push    r14
0x14000b087  push    r15
0x14000b089  lea     rbp, [rsp-2Fh]
0x14000b08e  sub     rsp, 0B8h
0x14000b095  mov     rax, cs:__security_cookie
0x14000b09c  xor     rax, rsp
0x14000b09f  mov     [rbp+57h+var_38], rax
0x14000b0a3  xor     ebx, ebx
0x14000b0a5  xorps   xmm0, xmm0
0x14000b0a8  xor     eax, eax
0x14000b0aa  mov     [rbp+57h+var_A8], ebx
0x14000b0ad  lea     rax, DriverUnload
0x14000b0b4  mov     [rbp+57h+KeyHandle], rbx
0x14000b0b8  mov     [rcx+68h], rax
0x14000b0bc  xorps   xmm1, xmm1
0x14000b0bf  lea     rax, WPP_ThisDir_CTLGUID_NptrigTracing
0x14000b0c6  mov     qword ptr cs:WPP_MAIN_CB.Type, rbx
0x14000b0cd  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14000b0d1  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x14000b0d8  mov     r15, rcx
0x14000b0db  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14000b0df  mov     r14d, ebx
0x14000b0e2  mov     esi, ebx
0x14000b0e4  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x14000b0e8  mov     cs:WPP_MAIN_CB.NextDevice, rbx
0x14000b0ef  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14000b0f3  mov     cs:WPP_MAIN_CB.CurrentIrp, rbx
0x14000b0fa  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm1
0x14000b0fe  mov     cs:WPP_MAIN_CB.Timer, 1
0x14000b109  call    WppLoadTracingSupport
0x14000b10e  mov     cs:WPP_MAIN_CB.CurrentIrp, rbx
0x14000b115  call    WppInitKm
0x14000b11a  mov     edx, 40h ; '@'
0x14000b11f  mov     r8d, 6774704Eh
0x14000b125  mov     ecx, edx
0x14000b127  call    cs:__imp_ExAllocatePool2
0x14000b12e  nop     dword ptr [rax+rax+00h]
0x14000b133  mov     cs:WPP_MAIN_CB.DeviceExtension, rax
0x14000b13a  test    rax, rax
0x14000b13d  jnz     short loc_14000B14B
0x14000b13f  mov     edi, ebx
0x14000b141  mov     ebx, 0C0000017h
0x14000b146  jmp     loc_14000B311
0x14000b14b  xorps   xmm0, xmm0
0x14000b14e  mov     rcx, rax
0x14000b151  movups  xmmword ptr [rax], xmm0
0x14000b154  movups  xmmword ptr [rax+10h], xmm0
0x14000b158  movups  xmmword ptr [rax+20h], xmm0
0x14000b15c  movups  xmmword ptr [rax+30h], xmm0
0x14000b160  call    NptrigInitializeLock
0x14000b165  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x14000b16c  add     rcx, 18h
0x14000b170  call    NptrigInitializeLock
0x14000b175  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x14000b17c  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\Software\\Microsof"...
0x14000b183  lea     rax, [rcx+8]
0x14000b187  mov     [rax+8], rax
0x14000b18b  mov     [rax], rax
0x14000b18e  lea     rax, [rcx+20h]
0x14000b192  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14000b196  mov     [rax+8], rax
0x14000b19a  mov     [rax], rax
0x14000b19d  call    cs:__imp_RtlInitUnicodeString
0x14000b1a4  nop     dword ptr [rax+rax+00h]
0x14000b1a9  lea     rax, [rbp+57h+DestinationString]
0x14000b1ad  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14000b1b4  xorps   xmm0, xmm0
0x14000b1b7  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14000b1bb  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14000b1bf  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x14000b1c3  mov     edx, 80000000h; DesiredAccess
0x14000b1c8  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14000b1cf  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14000b1d3  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000b1d8  call    cs:__imp_ZwOpenKey
0x14000b1df  nop     dword ptr [rax+rax+00h]
0x14000b1e4  test    eax, eax
0x14000b1e6  js      short loc_14000B266
0x14000b1e8  lea     rdx, aNamedpipetimeo; "NamedPipeTimeout"
0x14000b1ef  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x14000b1f3  call    cs:__imp_RtlInitUnicodeString
0x14000b1fa  nop     dword ptr [rax+rax+00h]
0x14000b1ff  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14000b203  lea     rax, [rbp+57h+var_A8]
0x14000b207  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x14000b20c  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x14000b210  mov     r8d, 2; KeyValueInformationClass
0x14000b216  mov     [rsp+0E0h+Length], 18h; Length
0x14000b21e  lea     rdx, [rbp+57h+ValueName]; ValueName
0x14000b222  call    cs:__imp_ZwQueryValueKey
0x14000b229  nop     dword ptr [rax+rax+00h]
0x14000b22e  test    eax, eax
0x14000b230  js      short loc_14000B256
0x14000b232  mov     rcx, [rbp+57h+var_44]
0x14000b236  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x14000b23d  neg     rcx
0x14000b240  mov     [rax+30h], rcx
0x14000b244  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x14000b248  call    cs:__imp_ZwClose
0x14000b24f  nop     dword ptr [rax+rax+00h]
0x14000b254  jmp     short loc_14000B275
0x14000b256  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x14000b25a  call    cs:__imp_ZwClose
0x14000b261  nop     dword ptr [rax+rax+00h]
0x14000b266  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x14000b26d  mov     qword ptr [rax+30h], 0FFFFFFFFEE1E5D00h
0x14000b275  lea     r9, NPTRIG_ETW_PROVIDER_GUID_Context
0x14000b27c  lea     r8, NPTRIG_ETW_PROVIDER_GUID_Context
0x14000b283  lea     rcx, NPTRIG_ETW_PROVIDER_GUID
0x14000b28a  call    McGenEventRegister_EtwRegister
0x14000b28f  lea     r9, SERVICE_TRIGGER_PERF_EVENT_GUID_Context
0x14000b296  mov     edi, 1
0x14000b29b  lea     r8, SERVICE_TRIGGER_PERF_EVENT_GUID_Context
0x14000b2a2  lea     rcx, SERVICE_TRIGGER_PERF_EVENT_GUID
0x14000b2a9  call    McGenEventRegister_EtwRegister
0x14000b2ae  call    RtdsReaderInitialize
0x14000b2b3  mov     ebx, eax
0x14000b2b5  test    eax, eax
0x14000b2b7  js      short loc_14000B311
0x14000b2b9  mov     r14d, edi
0x14000b2bc  call    RtdsRegisterUpdateCallback
0x14000b2c1  mov     ebx, eax
0x14000b2c3  test    eax, eax
0x14000b2c5  js      short loc_14000B311
0x14000b2c7  mov     r8, cs:WPP_MAIN_CB.DeviceExtension
0x14000b2ce  lea     rdx, NptrigRegistration; Registration
0x14000b2d5  add     r8, 38h ; '8'; RetFilter
0x14000b2d9  mov     rcx, r15; Driver
0x14000b2dc  call    cs:__imp_FltRegisterFilter
0x14000b2e3  nop     dword ptr [rax+rax+00h]
0x14000b2e8  mov     ebx, eax
0x14000b2ea  test    eax, eax
0x14000b2ec  js      short loc_14000B30F
0x14000b2ee  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x14000b2f5  mov     rcx, [rcx+38h]; Filter
0x14000b2f9  call    cs:__imp_FltStartFiltering
0x14000b300  nop     dword ptr [rax+rax+00h]
0x14000b305  mov     ebx, eax
0x14000b307  test    eax, eax
0x14000b309  jns     loc_14000B3A3
0x14000b30f  mov     esi, edi
0x14000b311  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x14000b318  test    rax, rax
0x14000b31b  jz      short loc_14000B39C
0x14000b31d  mov     rcx, [rax+38h]; Filter
0x14000b321  test    rcx, rcx
0x14000b324  jz      short loc_14000B332
0x14000b326  call    cs:__imp_FltUnregisterFilter
0x14000b32d  nop     dword ptr [rax+rax+00h]
0x14000b332  test    esi, esi
0x14000b334  jz      short loc_14000B342
0x14000b336  lea     rcx, NAMED_PIPE_EVENT_GUID
0x14000b33d  call    RtdsUnregisterUpdateCallback
0x14000b342  test    r14d, r14d
0x14000b345  jz      short loc_14000B34C
0x14000b347  call    RtdsReaderShutdown
0x14000b34c  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x14000b353  add     rcx, 18h
0x14000b357  call    NptrigDeleteLock
0x14000b35c  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x14000b363  call    NptrigDeleteLock
0x14000b368  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension; P
0x14000b36f  mov     edx, 6774704Eh; Tag
0x14000b374  call    cs:__imp_ExFreePoolWithTag
0x14000b37b  nop     dword ptr [rax+rax+00h]
0x14000b380  test    edi, edi
0x14000b382  jz      short loc_14000B39C
0x14000b384  lea     rcx, NPTRIG_ETW_PROVIDER_GUID_Context
0x14000b38b  call    McGenEventUnregister_EtwUnregister
0x14000b390  lea     rcx, SERVICE_TRIGGER_PERF_EVENT_GUID_Context
0x14000b397  call    McGenEventUnregister_EtwUnregister
0x14000b39c  call    WppCleanupKm
0x14000b3a1  mov     eax, ebx
0x14000b3a3  mov     rcx, [rbp+57h+var_38]
0x14000b3a7  xor     rcx, rsp; StackCookie
0x14000b3aa  call    __security_check_cookie
0x14000b3af  add     rsp, 0B8h
0x14000b3b6  pop     r15
0x14000b3b8  pop     r14
0x14000b3ba  pop     rdi
0x14000b3bb  pop     rsi
0x14000b3bc  pop     rbx
0x14000b3bd  pop     rbp
0x14000b3be  retn
```
