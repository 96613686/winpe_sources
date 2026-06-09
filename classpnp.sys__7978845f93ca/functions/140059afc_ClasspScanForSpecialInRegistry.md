# ClasspScanForSpecialInRegistry

- ea: `0x140059afc`
- end: `0x140059cad`
- name: `ClasspScanForSpecialInRegistry`
- size: `433`
- prototype: `int __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400579b4`

## callees

- `0x14003e470`
- `0x14003e940`
- `0x140059afc`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140059b7d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140059c16`
- `ntoskrnl!RtlInitUnicodeString` at `0x140059b7d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140059c16`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x140059b5e`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x140059b5e`
- `ntoskrnl!RtlQueryRegistryValues` at `0x140059c4a`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140059c26`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140059c26`
- `ntoskrnl!ZwClose` at `0x140059c80`
- `ntoskrnl!ZwClose` at `0x140059c95`
- `ntoskrnl!ZwClose` at `0x140059c80`
- `ntoskrnl!ZwClose` at `0x140059c95`
- `ntoskrnl!ZwOpenKey` at `0x140059bbc`
- `ntoskrnl!ZwOpenKey` at `0x140059bbc`

## string_xrefs

- `0x140059bdf`: `RtlQueryRegistryValuesEx`

## pseudocode

```c
int __fastcall ClasspScanForSpecialInRegistry(__int64 a1)
{
  struct _DEVICE_OBJECT *v2; // rcx
  __int64 v3; // rax
  void *v4; // rbx
  PVOID SystemRoutineAddress; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-79h] BYREF
  struct _UNICODE_STRING SystemRoutineName; // [rsp+40h] [rbp-69h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-59h] BYREF
  _QWORD v10[16]; // [rsp+80h] [rbp-29h] BYREF
  unsigned int v11; // [rsp+110h] [rbp+67h] BYREF
  void *DeviceRegKey; // [rsp+118h] [rbp+6Fh] BYREF
  void *KeyHandle; // [rsp+120h] [rbp+77h] BYREF

  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  memset(v10, 0, 0x70u);
  v2 = *(struct _DEVICE_OBJECT **)(a1 + 512);
  DeviceRegKey = 0;
  KeyHandle = 0;
  v11 = 0;
  LODWORD(v3) = IoOpenDeviceRegistryKey(v2, 1u, 0x20006u, &DeviceRegKey);
  if ( (int)v3 >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"Classpnp");
    ObjectAttributes.RootDirectory = DeviceRegKey;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    LODWORD(v3) = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
    if ( (int)v3 >= 0 )
    {
      v4 = KeyHandle;
      v10[2] = L"HackMask";
      LODWORD(v10[1]) = 288;
      v10[3] = &v11;
      LODWORD(v10[4]) = 67108868;
      v10[5] = &v11;
      LODWORD(v10[6]) = 0;
      SystemRoutineName = 0;
      RtlInitUnicodeString(&SystemRoutineName, L"RtlQueryRegistryValuesEx");
      SystemRoutineAddress = MmGetSystemRoutineAddress(&SystemRoutineName);
      if ( !SystemRoutineAddress )
        SystemRoutineAddress = RtlQueryRegistryValues;
      LODWORD(v3) = ((__int64 (__fastcall *)(__int64, void *, _QWORD *, _QWORD, _QWORD))SystemRoutineAddress)(
                      0x40000000,
                      v4,
                      v10,
                      0,
                      0);
      if ( (int)v3 >= 0 )
      {
        v11 &= 0x3Fu;
        v3 = *(_QWORD *)(a1 + 1144);
        *(_QWORD *)(v3 + 1320) |= v11;
      }
    }
  }
  if ( DeviceRegKey )
    LODWORD(v3) = ZwClose(DeviceRegKey);
  if ( KeyHandle )
    LODWORD(v3) = ZwClose(KeyHandle);
  return v3;
}

```

## disassembly

```asm
0x140059afc  push    rbp
0x140059afe  push    rbx
0x140059aff  push    rdi
0x140059b00  lea     rbp, [rsp-47h]
0x140059b05  sub     rsp, 0F0h
0x140059b0c  xorps   xmm0, xmm0
0x140059b0f  xor     edx, edx; Val
0x140059b11  mov     rdi, rcx
0x140059b14  lea     rcx, [rbp+57h+var_80]; void *
0x140059b18  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140059b1c  lea     r8d, [rdx+70h]; Size
0x140059b20  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140059b24  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140059b28  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140059b2c  call    memset
0x140059b31  mov     rcx, [rdi+200h]; DeviceObject
0x140059b38  lea     r9, [rbp+57h+DeviceRegKey]; DeviceRegKey
0x140059b3c  mov     edx, 1; DevInstKeyType
0x140059b41  mov     [rbp+57h+DeviceRegKey], 0
0x140059b49  mov     r8d, 20006h; DesiredAccess
0x140059b4f  mov     [rbp+57h+KeyHandle], 0
0x140059b57  mov     [rbp+57h+arg_0], 0
0x140059b5e  call    cs:__imp_IoOpenDeviceRegistryKey
0x140059b65  nop     dword ptr [rax+rax+00h]
0x140059b6a  test    eax, eax
0x140059b6c  js      loc_140059C77
0x140059b72  lea     rdx, SubkeyName; "Classpnp"
0x140059b79  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140059b7d  call    cs:__imp_RtlInitUnicodeString
0x140059b84  nop     dword ptr [rax+rax+00h]
0x140059b89  mov     rax, [rbp+57h+DeviceRegKey]
0x140059b8d  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140059b91  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x140059b95  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140059b99  lea     rax, [rbp+57h+DestinationString]
0x140059b9d  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140059ba4  xorps   xmm0, xmm0
0x140059ba7  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140059bab  mov     edx, 20019h; DesiredAccess
0x140059bb0  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140059bb7  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140059bbc  call    cs:__imp_ZwOpenKey
0x140059bc3  nop     dword ptr [rax+rax+00h]
0x140059bc8  test    eax, eax
0x140059bca  js      loc_140059C77
0x140059bd0  mov     rbx, [rbp+57h+KeyHandle]
0x140059bd4  lea     rax, aHackmask; "HackMask"
0x140059bdb  mov     [rbp+57h+var_70], rax
0x140059bdf  lea     rdx, SourceString; "RtlQueryRegistryValuesEx"
0x140059be6  lea     rax, [rbp+57h+arg_0]
0x140059bea  mov     [rbp+57h+var_78], 120h
0x140059bf1  mov     [rbp+57h+var_68], rax
0x140059bf5  lea     rcx, [rbp+57h+SystemRoutineName]; DestinationString
0x140059bf9  lea     rax, [rbp+57h+arg_0]
0x140059bfd  mov     [rbp+57h+var_60], 4000004h
0x140059c04  xorps   xmm0, xmm0
0x140059c07  mov     [rbp+57h+var_58], rax
0x140059c0b  mov     [rbp+57h+var_50], 0
0x140059c12  movups  xmmword ptr [rbp+57h+SystemRoutineName.Length], xmm0
0x140059c16  call    cs:__imp_RtlInitUnicodeString
0x140059c1d  nop     dword ptr [rax+rax+00h]
0x140059c22  lea     rcx, [rbp+57h+SystemRoutineName]; SystemRoutineName
0x140059c26  call    cs:__imp_MmGetSystemRoutineAddress
0x140059c2d  nop     dword ptr [rax+rax+00h]
0x140059c32  lea     r8, [rbp+57h+var_80]
0x140059c36  mov     [rsp+100h+var_E0], 0
0x140059c3f  test    rax, rax
0x140059c42  mov     rdx, rbx
0x140059c45  mov     ecx, 40000000h
0x140059c4a  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x140059c52  xor     r9d, r9d
0x140059c55  call    _guard_dispatch_icall
0x140059c5a  test    eax, eax
0x140059c5c  js      short loc_140059C77
0x140059c5e  mov     eax, [rbp+57h+arg_0]
0x140059c61  and     eax, 3Fh
0x140059c64  mov     [rbp+57h+arg_0], eax
0x140059c67  mov     ecx, eax
0x140059c69  mov     rax, [rdi+478h]
0x140059c70  or      [rax+528h], rcx
0x140059c77  mov     rcx, [rbp+57h+DeviceRegKey]; Handle
0x140059c7b  test    rcx, rcx
0x140059c7e  jz      short loc_140059C8C
0x140059c80  call    cs:__imp_ZwClose
0x140059c87  nop     dword ptr [rax+rax+00h]
0x140059c8c  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x140059c90  test    rcx, rcx
0x140059c93  jz      short loc_140059CA1
0x140059c95  call    cs:__imp_ZwClose
0x140059c9c  nop     dword ptr [rax+rax+00h]
0x140059ca1  add     rsp, 0F0h
0x140059ca8  pop     rdi
0x140059ca9  pop     rbx
0x140059caa  pop     rbp
0x140059cab  retn
```
