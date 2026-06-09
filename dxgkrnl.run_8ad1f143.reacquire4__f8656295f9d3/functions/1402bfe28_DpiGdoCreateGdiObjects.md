# DpiGdoCreateGdiObjects

- ea: `0x1402bfe28`
- end: `0x1402c022c`
- name: `DpiGdoCreateGdiObjects`
- size: `1028`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, loader_planting, installer_update`

## callers

- `0x1402a2d70`

## callees

- `0x1402b0d90`
- `0x1402bfe28`
- `0x1402c0708`
- `0x140404050`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c0164`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c01cc`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c01dc`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c0164`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c01cc`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c01dc`
- `ntoskrnl!IoDeleteDevice` at `0x1402c01b4`
- `ntoskrnl!IoDeleteDevice` at `0x1402c01b4`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402bfe74`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402bfe74`
- `ntoskrnl!KeReleaseMutex` at `0x1402c0209`
- `ntoskrnl!KeReleaseMutex` at `0x1402c0209`
- `ntoskrnl!IoRegisterDeviceInterface` at `0x1402c007f`
- `ntoskrnl!IoRegisterDeviceInterface` at `0x1402c007f`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1402c0125`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1402c0125`
- `ntoskrnl!IoInitializeRemoveLockEx` at `0x1402bfffe`
- `ntoskrnl!IoInitializeRemoveLockEx` at `0x1402bfffe`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1402bff78`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1402bff78`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x1402c017a`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x1402c017a`
- `watchdog!WdLogSingleEntry1` at `0x1402bff29`
- `watchdog!WdLogSingleEntry1` at `0x1402bff93`
- `watchdog!WdLogSingleEntry1` at `0x1402c004e`
- `watchdog!WdLogSingleEntry1` at `0x1402c009a`
- `watchdog!WdLogSingleEntry1` at `0x1402c0147`
- `watchdog!WdLogSingleEntry1` at `0x1402bff29`
- `watchdog!WdLogSingleEntry1` at `0x1402bff93`
- `watchdog!WdLogSingleEntry1` at `0x1402c004e`
- `watchdog!WdLogSingleEntry1` at `0x1402c009a`
- `watchdog!WdLogSingleEntry1` at `0x1402c0147`

## pseudocode

```c
__int64 __fastcall DpiGdoCreateGdiObjects(__int64 a1, unsigned int a2, __int64 a3)
{
  __int64 v3; // rsi
  __int64 v4; // rdi
  unsigned int v5; // r15d
  int appended; // ebx
  __int64 v7; // r14
  bool v8; // zf
  const WCHAR *v9; // rcx
  ULONG v10; // edx
  char v11; // r12
  char v12; // r13
  PVOID DeviceExtension; // rdi
  _QWORD *v14; // rdx
  PDEVICE_OBJECT v15; // rax
  _QWORD *v16; // rax
  PVOID *v17; // rcx
  BOOLEAN v19; // [rsp+30h] [rbp-41h]
  struct _UNICODE_STRING DeviceName; // [rsp+60h] [rbp-11h] BYREF
  struct _UNICODE_STRING SymbolicLinkName; // [rsp+70h] [rbp-1h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+F0h] [rbp+7Fh] BYREF

  v3 = *(_QWORD *)(a1 + 64);
  v4 = a3;
  v5 = a2;
  appended = 0;
  KeWaitForSingleObject((PVOID)(v3 + 3720), Executive, 0, 0, 0);
  v7 = 0;
  while ( (unsigned int)v7 < v5 )
  {
    v8 = *(_BYTE *)(v3 + 2847) == 0;
    DeviceObject = 0;
    v9 = L"\\Device\\RemoteVideo";
    if ( v8 )
      v9 = L"\\Device\\Video";
    v10 = *(_DWORD *)(v4 + 4 * v7);
    DeviceName = 0;
    SymbolicLinkName = 0;
    appended = DpiAppendNumberToString(v9, v10, &DeviceName);
    if ( appended < 0 )
      goto LABEL_28;
    appended = WdmlibIoCreateDeviceSecure(
                 *(PDRIVER_OBJECT *)(*(_QWORD *)(v3 + 40) + 32LL),
                 0xC8u,
                 &DeviceName,
                 0x23u,
                 0x100u,
                 v19,
                 &SDDL_DEVOBJ_KERNEL_ONLY,
                 &GUID_SD_GDO,
                 &DeviceObject);
    if ( appended < 0 )
    {
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 168;
      goto LABEL_28;
    }
    v11 = 0;
    if ( !*(_BYTE *)(v3 + 2847) )
    {
      appended = DpiAppendNumberToString(L"\\DosDevices\\DISPLAY", *(_DWORD *)(v4 + 4 * v7) + 1, &SymbolicLinkName);
      if ( appended < 0 )
        goto LABEL_28;
      appended = IoCreateSymbolicLink(&SymbolicLinkName, &DeviceName);
      if ( appended < 0 )
      {
        WdLogSingleEntry1(2);
        WdLogGlobalForLineNumber = 201;
LABEL_28:
        if ( DeviceObject )
        {
          IoDeleteDevice(DeviceObject);
          DeviceObject = 0;
        }
        goto LABEL_30;
      }
      v11 = 1;
    }
    v12 = 0;
    DeviceExtension = DeviceObject->DeviceExtension;
    *((_DWORD *)DeviceExtension + 4) = 1953656900;
    *((_DWORD *)DeviceExtension + 5) = 6;
    *((_QWORD *)DeviceExtension + 3) = DeviceObject;
    *((_QWORD *)DeviceExtension + 4) = a1;
    *((_QWORD *)DeviceExtension + 5) = *(_QWORD *)(v3 + 40);
    *((_QWORD *)DeviceExtension + 6) = *(_QWORD *)(v3 + 48);
    IoInitializeRemoveLockEx((PIO_REMOVE_LOCK)DeviceExtension + 2, 0x74727044u, 1u, 0, 0x20u);
    *((_QWORD *)DeviceExtension + 13) = &DpiGdoDispatchCreate;
    *((_QWORD *)DeviceExtension + 14) = DpiGdoDispatchInternalIoctl;
    *((_QWORD *)DeviceExtension + 15) = &DpiGdoDispatchIoctl;
    *((_DWORD *)DeviceExtension + 38) = *(_DWORD *)(a3 + 4 * v7);
    *((_DWORD *)DeviceExtension + 39) = v7;
    if ( (unsigned int)v7 >= 0x10 )
    {
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 259;
    }
    appended = IoRegisterDeviceInterface(
                 *(PDEVICE_OBJECT *)(v3 + 152),
                 &GUID_DEVINTERFACE_DISPLAY_ADAPTER,
                 0,
                 (PUNICODE_STRING)DeviceExtension + 10);
    if ( appended < 0 )
    {
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 273;
LABEL_22:
      if ( v11 == 1 )
        IoDeleteSymbolicLink(&SymbolicLinkName);
      if ( v12 == 1 )
      {
        v16 = *(_QWORD **)DeviceExtension;
        if ( *(PVOID *)(*(_QWORD *)DeviceExtension + 8LL) != DeviceExtension
          || (v17 = (PVOID *)*((_QWORD *)DeviceExtension + 1), *v17 != DeviceExtension) )
        {
LABEL_32:
          __fastfail(3u);
        }
        *v17 = v16;
        v16[1] = v17;
        --*(_DWORD *)(v3 + 3776);
      }
      goto LABEL_28;
    }
    appended = DpiGdoSetupGdiParameters((__int64)DeviceObject, (__int64)&DeviceName, v7);
    if ( appended < 0 )
      goto LABEL_21;
    *((_QWORD *)DeviceExtension + 22) = *(_QWORD *)(v3 + 4032);
    *((_DWORD *)DeviceExtension + 48) = -1;
    v14 = *(_QWORD **)(v3 + 3712);
    if ( *v14 != v3 + 3704 )
      goto LABEL_32;
    *((_QWORD *)DeviceExtension + 1) = v14;
    *(_QWORD *)DeviceExtension = v3 + 3704;
    *v14 = DeviceExtension;
    *(_QWORD *)(v3 + 3712) = DeviceExtension;
    v15 = DeviceObject;
    ++*(_DWORD *)(v3 + 3776);
    v15->Flags |= 4u;
    DeviceObject->Flags &= ~0x80u;
    appended = IoSetDeviceInterfaceState((PUNICODE_STRING)DeviceExtension + 10, 1u);
    if ( appended < 0 )
    {
      v12 = 1;
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 333;
LABEL_21:
      RtlFreeUnicodeString((PUNICODE_STRING)DeviceExtension + 10);
      goto LABEL_22;
    }
LABEL_30:
    RtlFreeUnicodeString(&DeviceName);
    RtlFreeUnicodeString(&SymbolicLinkName);
    if ( appended < 0 )
      break;
    v4 = a3;
    v7 = (unsigned int)(v7 + 1);
    v5 = a2;
  }
  KeReleaseMutex((PRKMUTEX)(v3 + 3720), 0);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x1402bfe28  mov     rax, rsp
0x1402bfe2b  mov     [rax+18h], r8
0x1402bfe2f  mov     [rax+10h], edx
0x1402bfe32  mov     [rax+8], rcx
0x1402bfe36  push    rbp
0x1402bfe37  push    rbx
0x1402bfe38  push    rsi
0x1402bfe39  push    rdi
0x1402bfe3a  push    r12
0x1402bfe3c  push    r13
0x1402bfe3e  push    r14
0x1402bfe40  push    r15
0x1402bfe42  lea     rbp, [rax-5Fh]
0x1402bfe46  sub     rsp, 88h
0x1402bfe4d  mov     rsi, [rcx+40h]
0x1402bfe51  mov     rdi, r8
0x1402bfe54  mov     r15d, edx
0x1402bfe57  xor     ebx, ebx
0x1402bfe59  xor     r9d, r9d; Alertable
0x1402bfe5c  mov     [rsp+20h], rbx; Timeout
0x1402bfe61  xor     r8d, r8d; WaitMode
0x1402bfe64  xor     edx, edx; WaitReason
0x1402bfe66  lea     rax, [rsi+0E88h]
0x1402bfe6d  mov     rcx, rax; Object
0x1402bfe70  mov     [rbp+57h+Mutex], rax
0x1402bfe74  call    cs:__imp_KeWaitForSingleObject
0x1402bfe7b  nop     dword ptr [rax+rax+00h]
0x1402bfe80  xor     r14d, r14d
0x1402bfe83  cmp     r14d, r15d
0x1402bfe86  jnb     loc_1402C0203
0x1402bfe8c  cmp     byte ptr [rsi+0B1Fh], 0
0x1402bfe93  lea     rdx, aDeviceVideo; "\\Device\\Video"
0x1402bfe9a  xorps   xmm0, xmm0
0x1402bfe9d  mov     [rbp+57h+DeviceObject], 0
0x1402bfea5  xorps   xmm1, xmm1
0x1402bfea8  mov     r15d, r14d
0x1402bfeab  lea     rcx, aDeviceRemotevi; "\\Device\\RemoteVideo"
0x1402bfeb2  cmovz   rcx, rdx; SourceString
0x1402bfeb6  lea     r8, [rbp+57h+DeviceName]; Destination
0x1402bfeba  mov     edx, [rdi+r14*4]; Value
0x1402bfebe  movups  xmmword ptr [rbp+57h+DeviceName.Length], xmm0
0x1402bfec2  movups  xmmword ptr [rbp+57h+SymbolicLinkName.Length], xmm1
0x1402bfec6  call    DpiAppendNumberToString
0x1402bfecb  mov     ebx, eax
0x1402bfecd  test    eax, eax
0x1402bfecf  js      loc_1402C01AB
0x1402bfed5  mov     rcx, [rsi+28h]
0x1402bfed9  lea     rax, [rbp+57h+DeviceObject]
0x1402bfedd  mov     [rsp+40h], rax; DeviceObject
0x1402bfee2  lea     r8, [rbp+57h+DeviceName]; DeviceName
0x1402bfee6  lea     rax, GUID_SD_GDO
0x1402bfeed  mov     r9d, 23h ; '#'; DeviceType
0x1402bfef3  mov     [rsp+0C0h+DeviceClassGuid], rax; DeviceClassGuid
0x1402bfef8  mov     edx, 0C8h; DeviceExtensionSize
0x1402bfefd  mov     rcx, [rcx+20h]; DriverObject
0x1402bff01  lea     rax, SDDL_DEVOBJ_KERNEL_ONLY
0x1402bff08  mov     [rsp+0C0h+DefaultSDDLString], rax; DefaultSDDLString
0x1402bff0d  mov     dword ptr [rsp+20h], 100h; DeviceCharacteristics
0x1402bff15  call    WdmlibIoCreateDeviceSecure
0x1402bff1a  movsxd  rbx, eax
0x1402bff1d  test    eax, eax
0x1402bff1f  jns     short loc_1402BFF44
0x1402bff21  mov     rdx, rbx
0x1402bff24  mov     ecx, 2
0x1402bff29  call    cs:__imp_WdLogSingleEntry1
0x1402bff30  nop     dword ptr [rax+rax+00h]
0x1402bff35  mov     cs:WdLogGlobalForLineNumber, 0A8h
0x1402bff3f  jmp     loc_1402C01AB
0x1402bff44  xor     r12b, r12b
0x1402bff47  cmp     [rsi+0B1Fh], r12b
0x1402bff4e  jnz     short loc_1402BFFB1
0x1402bff50  mov     edx, [rdi+r14*4]
0x1402bff54  lea     r8, [rbp+57h+SymbolicLinkName]; Destination
0x1402bff58  inc     edx; Value
0x1402bff5a  lea     rcx, aDosdevicesDisp; "\\DosDevices\\DISPLAY"
0x1402bff61  call    DpiAppendNumberToString
0x1402bff66  mov     ebx, eax
0x1402bff68  test    eax, eax
0x1402bff6a  js      loc_1402C01AB
0x1402bff70  lea     rdx, [rbp+57h+DeviceName]; DeviceName
0x1402bff74  lea     rcx, [rbp+57h+SymbolicLinkName]; SymbolicLinkName
0x1402bff78  call    cs:__imp_IoCreateSymbolicLink
0x1402bff7f  nop     dword ptr [rax+rax+00h]
0x1402bff84  movsxd  rbx, eax
0x1402bff87  test    eax, eax
0x1402bff89  jns     short loc_1402BFFAE
0x1402bff8b  mov     rdx, rbx
0x1402bff8e  mov     ecx, 2
0x1402bff93  call    cs:__imp_WdLogSingleEntry1
0x1402bff9a  nop     dword ptr [rax+rax+00h]
0x1402bff9f  mov     cs:WdLogGlobalForLineNumber, 0C9h
0x1402bffa9  jmp     loc_1402C01AB
0x1402bffae  mov     r12b, 1
0x1402bffb1  mov     rax, [rbp+57h+DeviceObject]
0x1402bffb5  mov     edx, 74727044h; AllocateTag
0x1402bffba  xor     r9d, r9d; HighWatermark
0x1402bffbd  mov     dword ptr [rsp+20h], 20h ; ' '; RemlockSize
0x1402bffc5  xor     r13b, r13b
0x1402bffc8  mov     rdi, [rax+40h]
0x1402bffcc  lea     r8d, [r9+1]; MaxLockedMinutes
0x1402bffd0  mov     [rdi+10h], edx
0x1402bffd3  lea     rcx, [rdi+40h]; Lock
0x1402bffd7  mov     dword ptr [rdi+14h], 6
0x1402bffde  mov     rax, [rbp+57h+DeviceObject]
0x1402bffe2  mov     [rdi+18h], rax
0x1402bffe6  mov     rax, [rbp+57h+arg_0]
0x1402bffea  mov     [rdi+20h], rax
0x1402bffee  mov     rax, [rsi+28h]
0x1402bfff2  mov     [rdi+28h], rax
0x1402bfff6  mov     rax, [rsi+30h]
0x1402bfffa  mov     [rdi+30h], rax
0x1402bfffe  call    cs:__imp_IoInitializeRemoveLockEx
0x1402c0005  nop     dword ptr [rax+rax+00h]
0x1402c000a  lea     rax, DpiGdoDispatchCreate
0x1402c0011  mov     [rdi+68h], rax
0x1402c0015  lea     rax, DpiGdoDispatchInternalIoctl
0x1402c001c  mov     [rdi+70h], rax
0x1402c0020  lea     rax, DpiGdoDispatchIoctl
0x1402c0027  mov     [rdi+78h], rax
0x1402c002b  mov     rax, [rbp+57h+arg_10]
0x1402c002f  mov     eax, [rax+r14*4]
0x1402c0033  mov     [rdi+98h], eax
0x1402c0039  mov     [rdi+9Ch], r14d
0x1402c0040  cmp     r14d, 10h
0x1402c0044  jb      short loc_1402C0064
0x1402c0046  mov     rdx, r15
0x1402c0049  mov     ecx, 2
0x1402c004e  call    cs:__imp_WdLogSingleEntry1
0x1402c0055  nop     dword ptr [rax+rax+00h]
0x1402c005a  mov     cs:WdLogGlobalForLineNumber, 103h
0x1402c0064  mov     rcx, [rsi+98h]; PhysicalDeviceObject
0x1402c006b  lea     r15, [rdi+0A0h]
0x1402c0072  mov     r9, r15; SymbolicLinkName
0x1402c0075  lea     rdx, GUID_DEVINTERFACE_DISPLAY_ADAPTER; InterfaceClassGuid
0x1402c007c  xor     r8d, r8d; ReferenceString
0x1402c007f  call    cs:__imp_IoRegisterDeviceInterface
0x1402c0086  nop     dword ptr [rax+rax+00h]
0x1402c008b  movsxd  rbx, eax
0x1402c008e  test    eax, eax
0x1402c0090  jns     short loc_1402C00B5
0x1402c0092  mov     rdx, rbx
0x1402c0095  mov     ecx, 2
0x1402c009a  call    cs:__imp_WdLogSingleEntry1
0x1402c00a1  nop     dword ptr [rax+rax+00h]
0x1402c00a6  mov     cs:WdLogGlobalForLineNumber, 111h
0x1402c00b0  jmp     loc_1402C0170
0x1402c00b5  mov     rcx, [rbp+57h+DeviceObject]
0x1402c00b9  lea     rdx, [rbp+57h+DeviceName]
0x1402c00bd  mov     r8d, r14d
0x1402c00c0  call    DpiGdoSetupGdiParameters
0x1402c00c5  mov     ebx, eax
0x1402c00c7  test    eax, eax
0x1402c00c9  js      loc_1402C015D
0x1402c00cf  mov     rax, [rsi+0FC0h]
0x1402c00d6  mov     [rdi+0B0h], rax
0x1402c00dd  lea     rax, [rsi+0E78h]
0x1402c00e4  mov     dword ptr [rdi+0C0h], 0FFFFFFFFh
0x1402c00ee  mov     rdx, [rax+8]
0x1402c00f2  cmp     [rdx], rax
0x1402c00f5  jnz     loc_1402C01FC
0x1402c00fb  mov     [rdi+8], rdx
0x1402c00ff  mov     rcx, r15; SymbolicLinkName
0x1402c0102  mov     [rdi], rax
0x1402c0105  mov     [rdx], rdi
0x1402c0108  mov     dl, 1; Enable
0x1402c010a  mov     [rax+8], rdi
0x1402c010e  mov     rax, [rbp+57h+DeviceObject]
0x1402c0112  inc     dword ptr [rsi+0EC0h]
0x1402c0118  or      dword ptr [rax+30h], 4
0x1402c011c  mov     rax, [rbp+57h+DeviceObject]
0x1402c0120  btr     dword ptr [rax+30h], 7
0x1402c0125  call    cs:__imp_IoSetDeviceInterfaceState
0x1402c012c  nop     dword ptr [rax+rax+00h]
0x1402c0131  movsxd  rbx, eax
0x1402c0134  test    eax, eax
0x1402c0136  jns     loc_1402C01C8
0x1402c013c  mov     r13b, 1
0x1402c013f  mov     rdx, rbx
0x1402c0142  mov     ecx, 2
0x1402c0147  call    cs:__imp_WdLogSingleEntry1
0x1402c014e  nop     dword ptr [rax+rax+00h]
0x1402c0153  mov     cs:WdLogGlobalForLineNumber, 14Dh
0x1402c015d  lea     rcx, [rdi+0A0h]; UnicodeString
0x1402c0164  call    cs:__imp_RtlFreeUnicodeString
0x1402c016b  nop     dword ptr [rax+rax+00h]
0x1402c0170  cmp     r12b, 1
0x1402c0174  jnz     short loc_1402C0186
0x1402c0176  lea     rcx, [rbp+57h+SymbolicLinkName]; SymbolicLinkName
0x1402c017a  call    cs:__imp_IoDeleteSymbolicLink
0x1402c0181  nop     dword ptr [rax+rax+00h]
0x1402c0186  cmp     r13b, 1
0x1402c018a  jnz     short loc_1402C01AB
0x1402c018c  mov     rax, [rdi]
0x1402c018f  cmp     [rax+8], rdi
0x1402c0193  jnz     short loc_1402C01FC
0x1402c0195  mov     rcx, [rdi+8]
0x1402c0199  cmp     [rcx], rdi
0x1402c019c  jnz     short loc_1402C01FC
0x1402c019e  mov     [rcx], rax
0x1402c01a1  mov     [rax+8], rcx
0x1402c01a5  dec     dword ptr [rsi+0EC0h]
0x1402c01ab  mov     rcx, [rbp+57h+DeviceObject]; DeviceObject
0x1402c01af  test    rcx, rcx
0x1402c01b2  jz      short loc_1402C01C8
0x1402c01b4  call    cs:__imp_IoDeleteDevice
0x1402c01bb  nop     dword ptr [rax+rax+00h]
0x1402c01c0  mov     [rbp+57h+DeviceObject], 0
0x1402c01c8  lea     rcx, [rbp+57h+DeviceName]; UnicodeString
0x1402c01cc  call    cs:__imp_RtlFreeUnicodeString
0x1402c01d3  nop     dword ptr [rax+rax+00h]
0x1402c01d8  lea     rcx, [rbp+57h+SymbolicLinkName]; UnicodeString
0x1402c01dc  call    cs:__imp_RtlFreeUnicodeString
0x1402c01e3  nop     dword ptr [rax+rax+00h]
0x1402c01e8  test    ebx, ebx
0x1402c01ea  js      short loc_1402C0203
0x1402c01ec  mov     rdi, [rbp+57h+arg_10]
0x1402c01f0  inc     r14d
0x1402c01f3  mov     r15d, [rbp+57h+arg_8]
0x1402c01f7  jmp     loc_1402BFE83
0x1402c01fc  mov     ecx, 3
0x1402c0201  int     29h; Win8: RtlFailFast(ecx)
0x1402c0203  mov     rcx, [rbp+57h+Mutex]; Mutex
0x1402c0207  xor     edx, edx; Wait
0x1402c0209  call    cs:__imp_KeReleaseMutex
0x1402c0210  nop     dword ptr [rax+rax+00h]
0x1402c0215  mov     eax, ebx
0x1402c0217  add     rsp, 88h
0x1402c021e  pop     r15
0x1402c0220  pop     r14
0x1402c0222  pop     r13
0x1402c0224  pop     r12
0x1402c0226  pop     rdi
0x1402c0227  pop     rsi
0x1402c0228  pop     rbx
0x1402c0229  pop     rbp
0x1402c022a  retn
```
