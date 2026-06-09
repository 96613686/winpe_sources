# CKsNotification::GetLEDInfo(void)

- ea: `0x180051e60`
- end: `0x18005205e`
- name: `?GetLEDInfo@CKsNotification@@IEAAEXZ`
- size: `510`
- prototype: `_BOOL8 __fastcall(CKsNotification *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180065af8`

## callees

- `0x18000b7bc`
- `0x18001a000`
- `0x180051e60`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180051ebe`
- `ntoskrnl!RtlInitUnicodeString` at `0x180051ed5`
- `ntoskrnl!RtlInitUnicodeString` at `0x180051ebe`
- `ntoskrnl!RtlInitUnicodeString` at `0x180051ed5`
- `ntoskrnl!ZwQueryValueKey` at `0x180051f42`
- `ntoskrnl!ZwQueryValueKey` at `0x180051faa`
- `ntoskrnl!ZwQueryValueKey` at `0x180051f42`
- `ntoskrnl!ZwQueryValueKey` at `0x180051faa`
- `ntoskrnl!ZwClose` at `0x180051fd6`
- `ntoskrnl!ZwClose` at `0x180051fd6`
- `ntoskrnl!ZwOpenKey` at `0x180051f10`
- `ntoskrnl!ZwOpenKey` at `0x180051f10`
- `ntoskrnl!ExFreePoolWithTag` at `0x180051ff0`
- `ntoskrnl!ExFreePoolWithTag` at `0x180051ff0`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180051f67`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180051f67`

## string_xrefs

- `0x180051e8e`: `\Registry\Machine\SOFTWARE\Microsoft\OEM\Device\Capture`

## pseudocode

```c
_BOOL8 __fastcall CKsNotification::GetLEDInfo(CKsNotification *this)
{
  _DWORD *v1; // rbx
  bool v2; // di
  NTSTATUS v3; // eax
  _DWORD *PoolWithTag; // rax
  UNICODE_STRING ValueName; // [rsp+30h] [rbp-50h] BYREF
  UNICODE_STRING DestinationString; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  CKsNotification *ResultLength; // [rsp+A0h] [rbp+20h] BYREF
  void *KeyHandle; // [rsp+A8h] [rbp+28h] BYREF

  ResultLength = this;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      34,
      (__int64)WPP_0f409e30936e3eb7e2fb5867878996e2_Traceguids);
  KeyHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v1 = 0;
  LODWORD(ResultLength) = 0;
  v2 = 0;
  DestinationString = 0;
  ValueName = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\SOFTWARE\\Microsoft\\OEM\\Device\\Capture");
  RtlInitUnicodeString(&ValueName, L"NoPhysicalCameraLED");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
  {
    v3 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, 0, 0, (PULONG)&ResultLength);
    if ( v3 == -1073741789 || v3 == -2147483643 )
    {
      PoolWithTag = ExAllocatePoolWithTag(PagedPool, (unsigned int)ResultLength, 0x6B70534Bu);
      v1 = PoolWithTag;
      if ( PoolWithTag )
      {
        memset(PoolWithTag, 0, (unsigned int)ResultLength);
        if ( ZwQueryValueKey(
               KeyHandle,
               &ValueName,
               KeyValuePartialInformation,
               v1,
               (ULONG)ResultLength,
               (PULONG)&ResultLength) >= 0
          && v1[1] == 4
          && v1[2] == 4 )
        {
          v2 = v1[3] != 0;
        }
      }
    }
  }
  if ( KeyHandle )
  {
    ZwClose(KeyHandle);
    KeyHandle = 0;
  }
  if ( v1 )
    ExFreePoolWithTag(v1, 0);
  return v2;
}

```

## disassembly

```asm
0x180051e60  mov     [rsp-18h+arg_10], rbx
0x180051e65  mov     [rsp-18h+arg_0], rcx
0x180051e6a  push    rbp
0x180051e6b  push    rsi
0x180051e6c  push    rdi
0x180051e6d  mov     rbp, rsp
0x180051e70  sub     rsp, 80h
0x180051e77  lea     rax, WPP_RECORDER_INITIALIZED
0x180051e7e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180051e85  jnz     loc_180052014
0x180051e8b  xorps   xmm0, xmm0
0x180051e8e  lea     rdx, aRegistryMachin_5; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x180051e95  xor     esi, esi
0x180051e97  lea     rcx, [rbp+DestinationString]; DestinationString
0x180051e9b  xorps   xmm1, xmm1
0x180051e9e  mov     [rbp+KeyHandle], rsi
0x180051ea2  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180051ea6  mov     ebx, esi
0x180051ea8  mov     dword ptr [rbp+arg_0], esi
0x180051eab  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180051eaf  xor     dil, dil
0x180051eb2  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180051eb6  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180051eba  movups  xmmword ptr [rbp+ValueName.Length], xmm1
0x180051ebe  call    cs:__imp_RtlInitUnicodeString
0x180051ec5  nop     dword ptr [rax+rax+00h]
0x180051eca  lea     rdx, aNophysicalcame; "NoPhysicalCameraLED"
0x180051ed1  lea     rcx, [rbp+ValueName]; DestinationString
0x180051ed5  call    cs:__imp_RtlInitUnicodeString
0x180051edc  nop     dword ptr [rax+rax+00h]
0x180051ee1  lea     rax, [rbp+DestinationString]
0x180051ee5  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180051eec  xorps   xmm0, xmm0
0x180051eef  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180051ef3  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180051ef7  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x180051efb  mov     edx, 20019h; DesiredAccess
0x180051f00  mov     [rbp+ObjectAttributes.Attributes], 240h
0x180051f07  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x180051f0b  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180051f10  call    cs:__imp_ZwOpenKey
0x180051f17  nop     dword ptr [rax+rax+00h]
0x180051f1c  test    eax, eax
0x180051f1e  js      loc_180051FCD
0x180051f24  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180051f28  lea     rax, [rbp+arg_0]
0x180051f2c  mov     [rsp+80h+ResultLength], rax; ResultLength
0x180051f31  lea     rdx, [rbp+ValueName]; ValueName
0x180051f35  xor     r9d, r9d; KeyValueInformation
0x180051f38  mov     [rsp+80h+Length], esi; Length
0x180051f3c  mov     r8d, 2; KeyValueInformationClass
0x180051f42  call    cs:__imp_ZwQueryValueKey
0x180051f49  nop     dword ptr [rax+rax+00h]
0x180051f4e  cmp     eax, 0C0000023h
0x180051f53  jnz     loc_18005204E
0x180051f59  mov     edx, dword ptr [rbp+arg_0]; NumberOfBytes
0x180051f5c  mov     ecx, 1; PoolType
0x180051f61  mov     r8d, 6B70534Bh; Tag
0x180051f67  call    cs:__imp_ExAllocatePoolWithTag
0x180051f6e  nop     dword ptr [rax+rax+00h]
0x180051f73  mov     rbx, rax
0x180051f76  test    rax, rax
0x180051f79  jz      short loc_180051FCD
0x180051f7b  mov     r8d, dword ptr [rbp+arg_0]; Size
0x180051f7f  xor     edx, edx; Val
0x180051f81  mov     rcx, rax; void *
0x180051f84  call    memset
0x180051f89  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180051f8d  lea     rax, [rbp+arg_0]
0x180051f91  mov     [rsp+80h+ResultLength], rax; ResultLength
0x180051f96  lea     rdx, [rbp+ValueName]; ValueName
0x180051f9a  mov     eax, dword ptr [rbp+arg_0]
0x180051f9d  mov     r9, rbx; KeyValueInformation
0x180051fa0  mov     r8d, 2; KeyValueInformationClass
0x180051fa6  mov     [rsp+80h+Length], eax; Length
0x180051faa  call    cs:__imp_ZwQueryValueKey
0x180051fb1  nop     dword ptr [rax+rax+00h]
0x180051fb6  test    eax, eax
0x180051fb8  js      short loc_180051FCD
0x180051fba  cmp     dword ptr [rbx+4], 4
0x180051fbe  jnz     short loc_180051FCD
0x180051fc0  cmp     dword ptr [rbx+8], 4
0x180051fc4  jnz     short loc_180051FCD
0x180051fc6  cmp     [rbx+0Ch], esi
0x180051fc9  setnz   dil
0x180051fcd  mov     rcx, [rbp+KeyHandle]; Handle
0x180051fd1  test    rcx, rcx
0x180051fd4  jz      short loc_180051FE6
0x180051fd6  call    cs:__imp_ZwClose
0x180051fdd  nop     dword ptr [rax+rax+00h]
0x180051fe2  mov     [rbp+KeyHandle], rsi
0x180051fe6  test    rbx, rbx
0x180051fe9  jz      short loc_180051FFC
0x180051feb  xor     edx, edx; Tag
0x180051fed  mov     rcx, rbx; P
0x180051ff0  call    cs:__imp_ExFreePoolWithTag
0x180051ff7  nop     dword ptr [rax+rax+00h]
0x180051ffc  mov     rbx, [rsp+80h+arg_10]
0x180052004  movzx   eax, dil
0x180052008  add     rsp, 80h
0x18005200f  pop     rdi
0x180052010  pop     rsi
0x180052011  pop     rbp
0x180052012  retn
0x180052014  mov     rcx, cs:WPP_GLOBAL_Control
0x18005201b  cmp     word ptr [rcx+48h], 0
0x180052020  jz      loc_180051E8B
0x180052026  mov     rcx, [rcx+40h]
0x18005202a  lea     rax, WPP_0f409e30936e3eb7e2fb5867878996e2_Traceguids
0x180052031  mov     r9d, 22h ; '"'
0x180052037  mov     qword ptr [rsp+80h+Length], rax
0x18005203c  mov     r8d, 1
0x180052042  mov     dl, 5
0x180052044  call    WPP_RECORDER_SF_
0x180052049  jmp     loc_180051E8B
0x18005204e  cmp     eax, 80000005h
0x180052053  jnz     loc_180051FCD
0x180052059  jmp     loc_180051F59
```
