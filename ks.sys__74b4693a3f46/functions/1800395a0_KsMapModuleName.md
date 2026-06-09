# KsMapModuleName

- ea: `0x1800395a0`
- end: `0x180039744`
- name: `KsMapModuleName`
- size: `420`
- prototype: `NTSTATUS __stdcall(PDEVICE_OBJECT PhysicalDeviceObject, PUNICODE_STRING ModuleName, PUNICODE_STRING ImageName, PULONG_PTR ResourceId, PULONG ValueType)`
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800129e0`
- `0x180019fc0`
- `0x1800395a0`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x1800396cb`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1800396cb`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x1800395eb`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x1800395eb`
- `ntoskrnl!ZwClose` at `0x1800396db`
- `ntoskrnl!ZwClose` at `0x180039704`
- `ntoskrnl!ZwClose` at `0x180039731`
- `ntoskrnl!ZwClose` at `0x1800396db`
- `ntoskrnl!ZwClose` at `0x180039704`
- `ntoskrnl!ZwClose` at `0x180039731`
- `ntoskrnl!ZwOpenKey` at `0x1800396b9`
- `ntoskrnl!ZwOpenKey` at `0x1800396b9`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18003965b`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18003965b`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x180039674`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x180039674`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180039613`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180039613`

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
0x1800395a0  push    rbp
0x1800395a2  push    rbx
0x1800395a3  push    rsi
0x1800395a4  push    rdi
0x1800395a5  push    r12
0x1800395a7  push    r14
0x1800395a9  mov     rbp, rsp
0x1800395ac  sub     rsp, 78h
0x1800395b0  xorps   xmm0, xmm0
0x1800395b3  mov     [rbp+DeviceRegKey], 0
0x1800395bb  xor     eax, eax
0x1800395bd  mov     [rbp+KeyHandle], 0
0x1800395c5  mov     rsi, r9
0x1800395c8  mov     r14, r8
0x1800395cb  mov     rdi, rdx
0x1800395ce  lea     r9, [rbp+DeviceRegKey]; DeviceRegKey
0x1800395d2  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800395d6  lea     edx, [rax+1]; DevInstKeyType
0x1800395d9  mov     r8d, 20019h; DesiredAccess
0x1800395df  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800395e3  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x1800395e7  movups  xmmword ptr [rbp+Destination.Length], xmm0
0x1800395eb  call    cs:__imp_IoOpenDeviceRegistryKey
0x1800395f2  nop     dword ptr [rax+rax+00h]
0x1800395f7  test    eax, eax
0x1800395f9  js      loc_180039712
0x1800395ff  mov     r12d, 104h
0x180039605  mov     r8d, 7072534Bh; Tag
0x18003960b  mov     edx, r12d; NumberOfBytes
0x18003960e  mov     ecx, 401h; PoolType
0x180039613  call    cs:__imp_ExAllocatePoolWithTag
0x18003961a  nop     dword ptr [rax+rax+00h]
0x18003961f  cmp     cs:ExPoolZeroingNativelySupported, 0
0x180039626  mov     rbx, rax
0x180039629  jnz     loc_180039720
0x18003962f  test    rax, rax
0x180039632  jz      loc_180039720
0x180039638  mov     r8d, r12d; Size
0x18003963b  xor     edx, edx; Val
0x18003963d  mov     rcx, rax; void *
0x180039640  call    memset
0x180039645  mov     [rbp+Destination.Buffer], rbx
0x180039649  lea     rdx, aModules; "Modules\\"
0x180039650  mov     dword ptr [rbp+Destination.Length], 1040000h
0x180039657  lea     rcx, [rbp+Destination]; Destination
0x18003965b  call    cs:__imp_RtlAppendUnicodeToString
0x180039662  nop     dword ptr [rax+rax+00h]
0x180039667  mov     ebx, eax
0x180039669  test    eax, eax
0x18003966b  js      short loc_1800396C7
0x18003966d  mov     rdx, rdi; Source
0x180039670  lea     rcx, [rbp+Destination]; Destination
0x180039674  call    cs:__imp_RtlAppendUnicodeStringToString
0x18003967b  nop     dword ptr [rax+rax+00h]
0x180039680  mov     ebx, eax
0x180039682  test    eax, eax
0x180039684  js      short loc_1800396C7
0x180039686  mov     rax, [rbp+DeviceRegKey]
0x18003968a  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18003968e  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x180039692  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x180039696  lea     rax, [rbp+Destination]
0x18003969a  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800396a1  xorps   xmm0, xmm0
0x1800396a4  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1800396a8  mov     edx, 20019h; DesiredAccess
0x1800396ad  mov     [rbp+ObjectAttributes.Attributes], 240h
0x1800396b4  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800396b9  call    cs:__imp_ZwOpenKey
0x1800396c0  nop     dword ptr [rax+rax+00h]
0x1800396c5  mov     ebx, eax
0x1800396c7  lea     rcx, [rbp+Destination]; UnicodeString
0x1800396cb  call    cs:__imp_RtlFreeUnicodeString
0x1800396d2  nop     dword ptr [rax+rax+00h]
0x1800396d7  mov     rcx, [rbp+DeviceRegKey]; Handle
0x1800396db  call    cs:__imp_ZwClose
0x1800396e2  nop     dword ptr [rax+rax+00h]
0x1800396e7  test    ebx, ebx
0x1800396e9  js      short loc_180039710
0x1800396eb  mov     r9, [rbp+ValueType]; ValueType
0x1800396ef  mov     r8, rsi; ResourceId
0x1800396f2  mov     rcx, [rbp+KeyHandle]; RegKey
0x1800396f6  mov     rdx, r14; ImageName
0x1800396f9  call    KsGetImageNameAndResourceId
0x1800396fe  mov     rcx, [rbp+KeyHandle]; Handle
0x180039702  mov     ebx, eax
0x180039704  call    cs:__imp_ZwClose
0x18003970b  nop     dword ptr [rax+rax+00h]
0x180039710  mov     eax, ebx
0x180039712  add     rsp, 78h
0x180039716  pop     r14
0x180039718  pop     r12
0x18003971a  pop     rdi
0x18003971b  pop     rsi
0x18003971c  pop     rbx
0x18003971d  pop     rbp
0x18003971e  retn
0x180039720  mov     [rbp+Destination.Buffer], rbx
0x180039724  test    rbx, rbx
0x180039727  jnz     loc_180039649
0x18003972d  mov     rcx, [rbp+DeviceRegKey]; Handle
0x180039731  call    cs:__imp_ZwClose
0x180039738  nop     dword ptr [rax+rax+00h]
0x18003973d  mov     eax, 0C000009Ah
0x180039742  jmp     short loc_180039712
```
