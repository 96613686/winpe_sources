# DpiGdoCreateGdiObjects

- ea: `0x1402c6878`
- end: `0x1402c6c7c`
- name: `DpiGdoCreateGdiObjects`
- size: `1028`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, loader_planting, installer_update`

## callers

- `0x1402a9720`

## callees

- `0x1402b7740`
- `0x1402c6878`
- `0x1402c7158`
- `0x140401d58`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c6bb4`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c6c1c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c6c2c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c6bb4`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c6c1c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c6c2c`
- `ntoskrnl!IoDeleteDevice` at `0x1402c6c04`
- `ntoskrnl!IoDeleteDevice` at `0x1402c6c04`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402c68c4`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402c68c4`
- `ntoskrnl!KeReleaseMutex` at `0x1402c6c59`
- `ntoskrnl!KeReleaseMutex` at `0x1402c6c59`
- `ntoskrnl!IoRegisterDeviceInterface` at `0x1402c6acf`
- `ntoskrnl!IoRegisterDeviceInterface` at `0x1402c6acf`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1402c6b75`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1402c6b75`
- `ntoskrnl!IoInitializeRemoveLockEx` at `0x1402c6a4e`
- `ntoskrnl!IoInitializeRemoveLockEx` at `0x1402c6a4e`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1402c69c8`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1402c69c8`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x1402c6bca`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x1402c6bca`
- `watchdog!WdLogSingleEntry1` at `0x1402c6979`
- `watchdog!WdLogSingleEntry1` at `0x1402c69e3`
- `watchdog!WdLogSingleEntry1` at `0x1402c6a9e`
- `watchdog!WdLogSingleEntry1` at `0x1402c6aea`
- `watchdog!WdLogSingleEntry1` at `0x1402c6b97`
- `watchdog!WdLogSingleEntry1` at `0x1402c6979`
- `watchdog!WdLogSingleEntry1` at `0x1402c69e3`
- `watchdog!WdLogSingleEntry1` at `0x1402c6a9e`
- `watchdog!WdLogSingleEntry1` at `0x1402c6aea`
- `watchdog!WdLogSingleEntry1` at `0x1402c6b97`

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
  NTSTATUS v11; // eax
  char v12; // r12
  NTSTATUS v13; // eax
  char v14; // r13
  PVOID DeviceExtension; // rdi
  NTSTATUS v16; // eax
  _QWORD *v17; // rdx
  PDEVICE_OBJECT v18; // rax
  NTSTATUS v19; // eax
  _QWORD *v20; // rax
  PVOID *v21; // rcx
  BOOLEAN v23; // [rsp+30h] [rbp-41h]
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
    v11 = WdmlibIoCreateDeviceSecure(
            *(PDRIVER_OBJECT *)(*(_QWORD *)(v3 + 40) + 32LL),
            0xC8u,
            &DeviceName,
            0x23u,
            0x100u,
            v23,
            &SDDL_DEVOBJ_KERNEL_ONLY,
            &GUID_SD_GDO,
            &DeviceObject);
    appended = v11;
    if ( v11 < 0 )
    {
      WdLogSingleEntry1(2, v11);
      WdLogGlobalForLineNumber = 168;
      goto LABEL_28;
    }
    v12 = 0;
    if ( !*(_BYTE *)(v3 + 2847) )
    {
      appended = DpiAppendNumberToString(L"\\DosDevices\\DISPLAY", *(_DWORD *)(v4 + 4 * v7) + 1, &SymbolicLinkName);
      if ( appended < 0 )
        goto LABEL_28;
      v13 = IoCreateSymbolicLink(&SymbolicLinkName, &DeviceName);
      appended = v13;
      if ( v13 < 0 )
      {
        WdLogSingleEntry1(2, v13);
        WdLogGlobalForLineNumber = 201;
LABEL_28:
        if ( DeviceObject )
        {
          IoDeleteDevice(DeviceObject);
          DeviceObject = 0;
        }
        goto LABEL_30;
      }
      v12 = 1;
    }
    v14 = 0;
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
      WdLogSingleEntry1(2, (unsigned int)v7);
      WdLogGlobalForLineNumber = 259;
    }
    v16 = IoRegisterDeviceInterface(
            *(PDEVICE_OBJECT *)(v3 + 152),
            &GUID_DEVINTERFACE_DISPLAY_ADAPTER,
            0,
            (PUNICODE_STRING)DeviceExtension + 10);
    appended = v16;
    if ( v16 < 0 )
    {
      WdLogSingleEntry1(2, v16);
      WdLogGlobalForLineNumber = 273;
LABEL_22:
      if ( v12 == 1 )
        IoDeleteSymbolicLink(&SymbolicLinkName);
      if ( v14 == 1 )
      {
        v20 = *(_QWORD **)DeviceExtension;
        if ( *(PVOID *)(*(_QWORD *)DeviceExtension + 8LL) != DeviceExtension
          || (v21 = (PVOID *)*((_QWORD *)DeviceExtension + 1), *v21 != DeviceExtension) )
        {
LABEL_32:
          __fastfail(3u);
        }
        *v21 = v20;
        v20[1] = v21;
        --*(_DWORD *)(v3 + 3776);
      }
      goto LABEL_28;
    }
    appended = DpiGdoSetupGdiParameters((__int64)DeviceObject, (__int64)&DeviceName, v7);
    if ( appended < 0 )
      goto LABEL_21;
    *((_QWORD *)DeviceExtension + 22) = *(_QWORD *)(v3 + 4032);
    *((_DWORD *)DeviceExtension + 48) = -1;
    v17 = *(_QWORD **)(v3 + 3712);
    if ( *v17 != v3 + 3704 )
      goto LABEL_32;
    *((_QWORD *)DeviceExtension + 1) = v17;
    *(_QWORD *)DeviceExtension = v3 + 3704;
    *v17 = DeviceExtension;
    *(_QWORD *)(v3 + 3712) = DeviceExtension;
    v18 = DeviceObject;
    ++*(_DWORD *)(v3 + 3776);
    v18->Flags |= 4u;
    DeviceObject->Flags &= ~0x80u;
    v19 = IoSetDeviceInterfaceState((PUNICODE_STRING)DeviceExtension + 10, 1u);
    appended = v19;
    if ( v19 < 0 )
    {
      v14 = 1;
      WdLogSingleEntry1(2, v19);
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
0x1402c6878  mov     rax, rsp
0x1402c687b  mov     [rax+18h], r8
0x1402c687f  mov     [rax+10h], edx
0x1402c6882  mov     [rax+8], rcx
0x1402c6886  push    rbp
0x1402c6887  push    rbx
0x1402c6888  push    rsi
0x1402c6889  push    rdi
0x1402c688a  push    r12
0x1402c688c  push    r13
0x1402c688e  push    r14
0x1402c6890  push    r15
0x1402c6892  lea     rbp, [rax-5Fh]
0x1402c6896  sub     rsp, 88h
0x1402c689d  mov     rsi, [rcx+40h]
0x1402c68a1  mov     rdi, r8
0x1402c68a4  mov     r15d, edx
0x1402c68a7  xor     ebx, ebx
0x1402c68a9  xor     r9d, r9d; Alertable
0x1402c68ac  mov     [rsp+20h], rbx; Timeout
0x1402c68b1  xor     r8d, r8d; WaitMode
0x1402c68b4  xor     edx, edx; WaitReason
0x1402c68b6  lea     rax, [rsi+0E88h]
0x1402c68bd  mov     rcx, rax; Object
0x1402c68c0  mov     [rbp+57h+Mutex], rax
0x1402c68c4  call    cs:__imp_KeWaitForSingleObject
0x1402c68cb  nop     dword ptr [rax+rax+00h]
0x1402c68d0  xor     r14d, r14d
0x1402c68d3  cmp     r14d, r15d
0x1402c68d6  jnb     loc_1402C6C53
0x1402c68dc  cmp     byte ptr [rsi+0B1Fh], 0
0x1402c68e3  lea     rdx, aDeviceVideo; "\\Device\\Video"
0x1402c68ea  xorps   xmm0, xmm0
0x1402c68ed  mov     [rbp+57h+DeviceObject], 0
0x1402c68f5  xorps   xmm1, xmm1
0x1402c68f8  mov     r15d, r14d
0x1402c68fb  lea     rcx, aDeviceRemotevi; "\\Device\\RemoteVideo"
0x1402c6902  cmovz   rcx, rdx; SourceString
0x1402c6906  lea     r8, [rbp+57h+DeviceName]; Destination
0x1402c690a  mov     edx, [rdi+r14*4]; Value
0x1402c690e  movups  xmmword ptr [rbp+57h+DeviceName.Length], xmm0
0x1402c6912  movups  xmmword ptr [rbp+57h+SymbolicLinkName.Length], xmm1
0x1402c6916  call    DpiAppendNumberToString
0x1402c691b  mov     ebx, eax
0x1402c691d  test    eax, eax
0x1402c691f  js      loc_1402C6BFB
0x1402c6925  mov     rcx, [rsi+28h]
0x1402c6929  lea     rax, [rbp+57h+DeviceObject]
0x1402c692d  mov     [rsp+40h], rax; DeviceObject
0x1402c6932  lea     r8, [rbp+57h+DeviceName]; DeviceName
0x1402c6936  lea     rax, GUID_SD_GDO
0x1402c693d  mov     r9d, 23h ; '#'; DeviceType
0x1402c6943  mov     [rsp+0C0h+DeviceClassGuid], rax; DeviceClassGuid
0x1402c6948  mov     edx, 0C8h; DeviceExtensionSize
0x1402c694d  mov     rcx, [rcx+20h]; DriverObject
0x1402c6951  lea     rax, SDDL_DEVOBJ_KERNEL_ONLY
0x1402c6958  mov     [rsp+0C0h+DefaultSDDLString], rax; DefaultSDDLString
0x1402c695d  mov     dword ptr [rsp+20h], 100h; DeviceCharacteristics
0x1402c6965  call    WdmlibIoCreateDeviceSecure
0x1402c696a  movsxd  rbx, eax
0x1402c696d  test    eax, eax
0x1402c696f  jns     short loc_1402C6994
0x1402c6971  mov     rdx, rbx
0x1402c6974  mov     ecx, 2
0x1402c6979  call    cs:__imp_WdLogSingleEntry1
0x1402c6980  nop     dword ptr [rax+rax+00h]
0x1402c6985  mov     cs:WdLogGlobalForLineNumber, 0A8h
0x1402c698f  jmp     loc_1402C6BFB
0x1402c6994  xor     r12b, r12b
0x1402c6997  cmp     [rsi+0B1Fh], r12b
0x1402c699e  jnz     short loc_1402C6A01
0x1402c69a0  mov     edx, [rdi+r14*4]
0x1402c69a4  lea     r8, [rbp+57h+SymbolicLinkName]; Destination
0x1402c69a8  inc     edx; Value
0x1402c69aa  lea     rcx, aDosdevicesDisp; "\\DosDevices\\DISPLAY"
0x1402c69b1  call    DpiAppendNumberToString
0x1402c69b6  mov     ebx, eax
0x1402c69b8  test    eax, eax
0x1402c69ba  js      loc_1402C6BFB
0x1402c69c0  lea     rdx, [rbp+57h+DeviceName]; DeviceName
0x1402c69c4  lea     rcx, [rbp+57h+SymbolicLinkName]; SymbolicLinkName
0x1402c69c8  call    cs:__imp_IoCreateSymbolicLink
0x1402c69cf  nop     dword ptr [rax+rax+00h]
0x1402c69d4  movsxd  rbx, eax
0x1402c69d7  test    eax, eax
0x1402c69d9  jns     short loc_1402C69FE
0x1402c69db  mov     rdx, rbx
0x1402c69de  mov     ecx, 2
0x1402c69e3  call    cs:__imp_WdLogSingleEntry1
0x1402c69ea  nop     dword ptr [rax+rax+00h]
0x1402c69ef  mov     cs:WdLogGlobalForLineNumber, 0C9h
0x1402c69f9  jmp     loc_1402C6BFB
0x1402c69fe  mov     r12b, 1
0x1402c6a01  mov     rax, [rbp+57h+DeviceObject]
0x1402c6a05  mov     edx, 74727044h; AllocateTag
0x1402c6a0a  xor     r9d, r9d; HighWatermark
0x1402c6a0d  mov     dword ptr [rsp+20h], 20h ; ' '; RemlockSize
0x1402c6a15  xor     r13b, r13b
0x1402c6a18  mov     rdi, [rax+40h]
0x1402c6a1c  lea     r8d, [r9+1]; MaxLockedMinutes
0x1402c6a20  mov     [rdi+10h], edx
0x1402c6a23  lea     rcx, [rdi+40h]; Lock
0x1402c6a27  mov     dword ptr [rdi+14h], 6
0x1402c6a2e  mov     rax, [rbp+57h+DeviceObject]
0x1402c6a32  mov     [rdi+18h], rax
0x1402c6a36  mov     rax, [rbp+57h+arg_0]
0x1402c6a3a  mov     [rdi+20h], rax
0x1402c6a3e  mov     rax, [rsi+28h]
0x1402c6a42  mov     [rdi+28h], rax
0x1402c6a46  mov     rax, [rsi+30h]
0x1402c6a4a  mov     [rdi+30h], rax
0x1402c6a4e  call    cs:__imp_IoInitializeRemoveLockEx
0x1402c6a55  nop     dword ptr [rax+rax+00h]
0x1402c6a5a  lea     rax, DpiGdoDispatchCreate
0x1402c6a61  mov     [rdi+68h], rax
0x1402c6a65  lea     rax, DpiGdoDispatchInternalIoctl
0x1402c6a6c  mov     [rdi+70h], rax
0x1402c6a70  lea     rax, DpiGdoDispatchIoctl
0x1402c6a77  mov     [rdi+78h], rax
0x1402c6a7b  mov     rax, [rbp+57h+arg_10]
0x1402c6a7f  mov     eax, [rax+r14*4]
0x1402c6a83  mov     [rdi+98h], eax
0x1402c6a89  mov     [rdi+9Ch], r14d
0x1402c6a90  cmp     r14d, 10h
0x1402c6a94  jb      short loc_1402C6AB4
0x1402c6a96  mov     rdx, r15
0x1402c6a99  mov     ecx, 2
0x1402c6a9e  call    cs:__imp_WdLogSingleEntry1
0x1402c6aa5  nop     dword ptr [rax+rax+00h]
0x1402c6aaa  mov     cs:WdLogGlobalForLineNumber, 103h
0x1402c6ab4  mov     rcx, [rsi+98h]; PhysicalDeviceObject
0x1402c6abb  lea     r15, [rdi+0A0h]
0x1402c6ac2  mov     r9, r15; SymbolicLinkName
0x1402c6ac5  lea     rdx, GUID_DEVINTERFACE_DISPLAY_ADAPTER; InterfaceClassGuid
0x1402c6acc  xor     r8d, r8d; ReferenceString
0x1402c6acf  call    cs:__imp_IoRegisterDeviceInterface
0x1402c6ad6  nop     dword ptr [rax+rax+00h]
0x1402c6adb  movsxd  rbx, eax
0x1402c6ade  test    eax, eax
0x1402c6ae0  jns     short loc_1402C6B05
0x1402c6ae2  mov     rdx, rbx
0x1402c6ae5  mov     ecx, 2
0x1402c6aea  call    cs:__imp_WdLogSingleEntry1
0x1402c6af1  nop     dword ptr [rax+rax+00h]
0x1402c6af6  mov     cs:WdLogGlobalForLineNumber, 111h
0x1402c6b00  jmp     loc_1402C6BC0
0x1402c6b05  mov     rcx, [rbp+57h+DeviceObject]
0x1402c6b09  lea     rdx, [rbp+57h+DeviceName]
0x1402c6b0d  mov     r8d, r14d
0x1402c6b10  call    DpiGdoSetupGdiParameters
0x1402c6b15  mov     ebx, eax
0x1402c6b17  test    eax, eax
0x1402c6b19  js      loc_1402C6BAD
0x1402c6b1f  mov     rax, [rsi+0FC0h]
0x1402c6b26  mov     [rdi+0B0h], rax
0x1402c6b2d  lea     rax, [rsi+0E78h]
0x1402c6b34  mov     dword ptr [rdi+0C0h], 0FFFFFFFFh
0x1402c6b3e  mov     rdx, [rax+8]
0x1402c6b42  cmp     [rdx], rax
0x1402c6b45  jnz     loc_1402C6C4C
0x1402c6b4b  mov     [rdi+8], rdx
0x1402c6b4f  mov     rcx, r15; SymbolicLinkName
0x1402c6b52  mov     [rdi], rax
0x1402c6b55  mov     [rdx], rdi
0x1402c6b58  mov     dl, 1; Enable
0x1402c6b5a  mov     [rax+8], rdi
0x1402c6b5e  mov     rax, [rbp+57h+DeviceObject]
0x1402c6b62  inc     dword ptr [rsi+0EC0h]
0x1402c6b68  or      dword ptr [rax+30h], 4
0x1402c6b6c  mov     rax, [rbp+57h+DeviceObject]
0x1402c6b70  btr     dword ptr [rax+30h], 7
0x1402c6b75  call    cs:__imp_IoSetDeviceInterfaceState
0x1402c6b7c  nop     dword ptr [rax+rax+00h]
0x1402c6b81  movsxd  rbx, eax
0x1402c6b84  test    eax, eax
0x1402c6b86  jns     loc_1402C6C18
0x1402c6b8c  mov     r13b, 1
0x1402c6b8f  mov     rdx, rbx
0x1402c6b92  mov     ecx, 2
0x1402c6b97  call    cs:__imp_WdLogSingleEntry1
0x1402c6b9e  nop     dword ptr [rax+rax+00h]
0x1402c6ba3  mov     cs:WdLogGlobalForLineNumber, 14Dh
0x1402c6bad  lea     rcx, [rdi+0A0h]; UnicodeString
0x1402c6bb4  call    cs:__imp_RtlFreeUnicodeString
0x1402c6bbb  nop     dword ptr [rax+rax+00h]
0x1402c6bc0  cmp     r12b, 1
0x1402c6bc4  jnz     short loc_1402C6BD6
0x1402c6bc6  lea     rcx, [rbp+57h+SymbolicLinkName]; SymbolicLinkName
0x1402c6bca  call    cs:__imp_IoDeleteSymbolicLink
0x1402c6bd1  nop     dword ptr [rax+rax+00h]
0x1402c6bd6  cmp     r13b, 1
0x1402c6bda  jnz     short loc_1402C6BFB
0x1402c6bdc  mov     rax, [rdi]
0x1402c6bdf  cmp     [rax+8], rdi
0x1402c6be3  jnz     short loc_1402C6C4C
0x1402c6be5  mov     rcx, [rdi+8]
0x1402c6be9  cmp     [rcx], rdi
0x1402c6bec  jnz     short loc_1402C6C4C
0x1402c6bee  mov     [rcx], rax
0x1402c6bf1  mov     [rax+8], rcx
0x1402c6bf5  dec     dword ptr [rsi+0EC0h]
0x1402c6bfb  mov     rcx, [rbp+57h+DeviceObject]; DeviceObject
0x1402c6bff  test    rcx, rcx
0x1402c6c02  jz      short loc_1402C6C18
0x1402c6c04  call    cs:__imp_IoDeleteDevice
0x1402c6c0b  nop     dword ptr [rax+rax+00h]
0x1402c6c10  mov     [rbp+57h+DeviceObject], 0
0x1402c6c18  lea     rcx, [rbp+57h+DeviceName]; UnicodeString
0x1402c6c1c  call    cs:__imp_RtlFreeUnicodeString
0x1402c6c23  nop     dword ptr [rax+rax+00h]
0x1402c6c28  lea     rcx, [rbp+57h+SymbolicLinkName]; UnicodeString
0x1402c6c2c  call    cs:__imp_RtlFreeUnicodeString
0x1402c6c33  nop     dword ptr [rax+rax+00h]
0x1402c6c38  test    ebx, ebx
0x1402c6c3a  js      short loc_1402C6C53
0x1402c6c3c  mov     rdi, [rbp+57h+arg_10]
0x1402c6c40  inc     r14d
0x1402c6c43  mov     r15d, [rbp+57h+arg_8]
0x1402c6c47  jmp     loc_1402C68D3
0x1402c6c4c  mov     ecx, 3
0x1402c6c51  int     29h; Win8: RtlFailFast(ecx)
0x1402c6c53  mov     rcx, [rbp+57h+Mutex]; Mutex
0x1402c6c57  xor     edx, edx; Wait
0x1402c6c59  call    cs:__imp_KeReleaseMutex
0x1402c6c60  nop     dword ptr [rax+rax+00h]
0x1402c6c65  mov     eax, ebx
0x1402c6c67  add     rsp, 88h
0x1402c6c6e  pop     r15
0x1402c6c70  pop     r14
0x1402c6c72  pop     r13
0x1402c6c74  pop     r12
0x1402c6c76  pop     rdi
0x1402c6c77  pop     rsi
0x1402c6c78  pop     rbx
0x1402c6c79  pop     rbp
0x1402c6c7a  retn
```
