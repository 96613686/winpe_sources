# KsMapModuleName

- ea: `0x1800395f0`
- end: `0x180039794`
- name: `KsMapModuleName`
- size: `420`
- prototype: `NTSTATUS __stdcall(PDEVICE_OBJECT PhysicalDeviceObject, PUNICODE_STRING ModuleName, PUNICODE_STRING ImageName, PULONG_PTR ResourceId, PULONG ValueType)`
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800129e0`
- `0x18001a000`
- `0x1800395f0`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x18003971b`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18003971b`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x18003963b`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x18003963b`
- `ntoskrnl!ZwClose` at `0x18003972b`
- `ntoskrnl!ZwClose` at `0x180039754`
- `ntoskrnl!ZwClose` at `0x180039781`
- `ntoskrnl!ZwClose` at `0x18003972b`
- `ntoskrnl!ZwClose` at `0x180039754`
- `ntoskrnl!ZwClose` at `0x180039781`
- `ntoskrnl!ZwOpenKey` at `0x180039709`
- `ntoskrnl!ZwOpenKey` at `0x180039709`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1800396ab`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1800396ab`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1800396c4`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1800396c4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180039663`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180039663`

## pseudocode

```c
NTSTATUS __stdcall KsMapModuleName(
        PDEVICE_OBJECT PhysicalDeviceObject,
        PUNICODE_STRING ModuleName,
        PUNICODE_STRING ImageName,
        PULONG_PTR ResourceId,
        PULONG ValueType)
{
  NTSTATUS result; // eax
  wchar_t *PoolWithTag; // rax
  wchar_t *v10; // rbx
  int appended; // ebx
  void *DeviceRegKey; // [rsp+20h] [rbp-58h] BYREF
  void *KeyHandle; // [rsp+28h] [rbp-50h] BYREF
  UNICODE_STRING Destination; // [rsp+30h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-38h] BYREF

  DeviceRegKey = 0;
  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  Destination = 0;
  result = IoOpenDeviceRegistryKey(PhysicalDeviceObject, 1u, 0x20019u, &DeviceRegKey);
  if ( result >= 0 )
  {
    PoolWithTag = (wchar_t *)ExAllocatePoolWithTag((POOL_TYPE)1025, 0x104u, 0x7072534Bu);
    v10 = PoolWithTag;
    if ( ExPoolZeroingNativelySupported || !PoolWithTag )
    {
      Destination.Buffer = PoolWithTag;
      if ( !PoolWithTag )
      {
        ZwClose(DeviceRegKey);
        return -1073741670;
      }
    }
    else
    {
      memset(PoolWithTag, 0, 0x104u);
      Destination.Buffer = v10;
    }
    *(_DWORD *)&Destination.Length = 17039360;
    appended = RtlAppendUnicodeToString(&Destination, L"Modules\\");
    if ( appended >= 0 )
    {
      appended = RtlAppendUnicodeStringToString(&Destination, ModuleName);
      if ( appended >= 0 )
      {
        ObjectAttributes.RootDirectory = DeviceRegKey;
        ObjectAttributes.Length = 48;
        ObjectAttributes.ObjectName = &Destination;
        ObjectAttributes.Attributes = 576;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        appended = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
      }
    }
    RtlFreeUnicodeString(&Destination);
    ZwClose(DeviceRegKey);
    if ( appended >= 0 )
    {
      appended = KsGetImageNameAndResourceId(KeyHandle, ImageName, ResourceId, ValueType);
      ZwClose(KeyHandle);
    }
    return appended;
  }
  return result;
}

```

## disassembly

```asm
0x1800395f0  push    rbp
0x1800395f2  push    rbx
0x1800395f3  push    rsi
0x1800395f4  push    rdi
0x1800395f5  push    r12
0x1800395f7  push    r14
0x1800395f9  mov     rbp, rsp
0x1800395fc  sub     rsp, 78h
0x180039600  xorps   xmm0, xmm0
0x180039603  mov     [rbp+DeviceRegKey], 0
0x18003960b  xor     eax, eax
0x18003960d  mov     [rbp+KeyHandle], 0
0x180039615  mov     rsi, r9
0x180039618  mov     r14, r8
0x18003961b  mov     rdi, rdx
0x18003961e  lea     r9, [rbp+DeviceRegKey]; DeviceRegKey
0x180039622  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180039626  lea     edx, [rax+1]; DevInstKeyType
0x180039629  mov     r8d, 20019h; DesiredAccess
0x18003962f  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180039633  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180039637  movups  xmmword ptr [rbp+Destination.Length], xmm0
0x18003963b  call    cs:__imp_IoOpenDeviceRegistryKey
0x180039642  nop     dword ptr [rax+rax+00h]
0x180039647  test    eax, eax
0x180039649  js      loc_180039762
0x18003964f  mov     r12d, 104h
0x180039655  mov     r8d, 7072534Bh; Tag
0x18003965b  mov     edx, r12d; NumberOfBytes
0x18003965e  mov     ecx, 401h; PoolType
0x180039663  call    cs:__imp_ExAllocatePoolWithTag
0x18003966a  nop     dword ptr [rax+rax+00h]
0x18003966f  cmp     cs:ExPoolZeroingNativelySupported, 0
0x180039676  mov     rbx, rax
0x180039679  jnz     loc_180039770
0x18003967f  test    rax, rax
0x180039682  jz      loc_180039770
0x180039688  mov     r8d, r12d; Size
0x18003968b  xor     edx, edx; Val
0x18003968d  mov     rcx, rax; void *
0x180039690  call    memset
0x180039695  mov     [rbp+Destination.Buffer], rbx
0x180039699  lea     rdx, aModules; "Modules\\"
0x1800396a0  mov     dword ptr [rbp+Destination.Length], 1040000h
0x1800396a7  lea     rcx, [rbp+Destination]; Destination
0x1800396ab  call    cs:__imp_RtlAppendUnicodeToString
0x1800396b2  nop     dword ptr [rax+rax+00h]
0x1800396b7  mov     ebx, eax
0x1800396b9  test    eax, eax
0x1800396bb  js      short loc_180039717
0x1800396bd  mov     rdx, rdi; Source
0x1800396c0  lea     rcx, [rbp+Destination]; Destination
0x1800396c4  call    cs:__imp_RtlAppendUnicodeStringToString
0x1800396cb  nop     dword ptr [rax+rax+00h]
0x1800396d0  mov     ebx, eax
0x1800396d2  test    eax, eax
0x1800396d4  js      short loc_180039717
0x1800396d6  mov     rax, [rbp+DeviceRegKey]
0x1800396da  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800396de  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x1800396e2  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x1800396e6  lea     rax, [rbp+Destination]
0x1800396ea  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800396f1  xorps   xmm0, xmm0
0x1800396f4  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1800396f8  mov     edx, 20019h; DesiredAccess
0x1800396fd  mov     [rbp+ObjectAttributes.Attributes], 240h
0x180039704  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180039709  call    cs:__imp_ZwOpenKey
0x180039710  nop     dword ptr [rax+rax+00h]
0x180039715  mov     ebx, eax
0x180039717  lea     rcx, [rbp+Destination]; UnicodeString
0x18003971b  call    cs:__imp_RtlFreeUnicodeString
0x180039722  nop     dword ptr [rax+rax+00h]
0x180039727  mov     rcx, [rbp+DeviceRegKey]; Handle
0x18003972b  call    cs:__imp_ZwClose
0x180039732  nop     dword ptr [rax+rax+00h]
0x180039737  test    ebx, ebx
0x180039739  js      short loc_180039760
0x18003973b  mov     r9, [rbp+ValueType]; ValueType
0x18003973f  mov     r8, rsi; ResourceId
0x180039742  mov     rcx, [rbp+KeyHandle]; RegKey
0x180039746  mov     rdx, r14; ImageName
0x180039749  call    KsGetImageNameAndResourceId
0x18003974e  mov     rcx, [rbp+KeyHandle]; Handle
0x180039752  mov     ebx, eax
0x180039754  call    cs:__imp_ZwClose
0x18003975b  nop     dword ptr [rax+rax+00h]
0x180039760  mov     eax, ebx
0x180039762  add     rsp, 78h
0x180039766  pop     r14
0x180039768  pop     r12
0x18003976a  pop     rdi
0x18003976b  pop     rsi
0x18003976c  pop     rbx
0x18003976d  pop     rbp
0x18003976e  retn
0x180039770  mov     [rbp+Destination.Buffer], rbx
0x180039774  test    rbx, rbx
0x180039777  jnz     loc_180039699
0x18003977d  mov     rcx, [rbp+DeviceRegKey]; Handle
0x180039781  call    cs:__imp_ZwClose
0x180039788  nop     dword ptr [rax+rax+00h]
0x18003978d  mov     eax, 0C000009Ah
0x180039792  jmp     short loc_180039762
```
