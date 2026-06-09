# CKsNotification::GetLEDInfo(void)

- ea: `0x180051cc0`
- end: `0x180051ebe`
- name: `?GetLEDInfo@CKsNotification@@IEAAEXZ`
- size: `510`
- prototype: `unsigned __int8 __fastcall(CKsNotification *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180065958`

## callees

- `0x18000b7bc`
- `0x180019fc0`
- `0x180051cc0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180051d1e`
- `ntoskrnl!RtlInitUnicodeString` at `0x180051d35`
- `ntoskrnl!RtlInitUnicodeString` at `0x180051d1e`
- `ntoskrnl!RtlInitUnicodeString` at `0x180051d35`
- `ntoskrnl!ZwQueryValueKey` at `0x180051da2`
- `ntoskrnl!ZwQueryValueKey` at `0x180051e0a`
- `ntoskrnl!ZwQueryValueKey` at `0x180051da2`
- `ntoskrnl!ZwQueryValueKey` at `0x180051e0a`
- `ntoskrnl!ZwClose` at `0x180051e36`
- `ntoskrnl!ZwClose` at `0x180051e36`
- `ntoskrnl!ZwOpenKey` at `0x180051d70`
- `ntoskrnl!ZwOpenKey` at `0x180051d70`
- `ntoskrnl!ExFreePoolWithTag` at `0x180051e50`
- `ntoskrnl!ExFreePoolWithTag` at `0x180051e50`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180051dc7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180051dc7`

## string_xrefs

- `0x180051cee`: `\Registry\Machine\SOFTWARE\Microsoft\OEM\Device\Capture`

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
0x180051cc0  mov     [rsp-18h+arg_10], rbx
0x180051cc5  mov     [rsp-18h+arg_0], rcx
0x180051cca  push    rbp
0x180051ccb  push    rsi
0x180051ccc  push    rdi
0x180051ccd  mov     rbp, rsp
0x180051cd0  sub     rsp, 80h
0x180051cd7  lea     rax, WPP_RECORDER_INITIALIZED
0x180051cde  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180051ce5  jnz     loc_180051E74
0x180051ceb  xorps   xmm0, xmm0
0x180051cee  lea     rdx, aRegistryMachin_5; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x180051cf5  xor     esi, esi
0x180051cf7  lea     rcx, [rbp+DestinationString]; DestinationString
0x180051cfb  xorps   xmm1, xmm1
0x180051cfe  mov     [rbp+KeyHandle], rsi
0x180051d02  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180051d06  mov     ebx, esi
0x180051d08  mov     dword ptr [rbp+arg_0], esi
0x180051d0b  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180051d0f  xor     dil, dil
0x180051d12  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180051d16  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180051d1a  movups  xmmword ptr [rbp+ValueName.Length], xmm1
0x180051d1e  call    cs:__imp_RtlInitUnicodeString
0x180051d25  nop     dword ptr [rax+rax+00h]
0x180051d2a  lea     rdx, aNophysicalcame; "NoPhysicalCameraLED"
0x180051d31  lea     rcx, [rbp+ValueName]; DestinationString
0x180051d35  call    cs:__imp_RtlInitUnicodeString
0x180051d3c  nop     dword ptr [rax+rax+00h]
0x180051d41  lea     rax, [rbp+DestinationString]
0x180051d45  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180051d4c  xorps   xmm0, xmm0
0x180051d4f  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180051d53  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180051d57  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x180051d5b  mov     edx, 20019h; DesiredAccess
0x180051d60  mov     [rbp+ObjectAttributes.Attributes], 240h
0x180051d67  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x180051d6b  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180051d70  call    cs:__imp_ZwOpenKey
0x180051d77  nop     dword ptr [rax+rax+00h]
0x180051d7c  test    eax, eax
0x180051d7e  js      loc_180051E2D
0x180051d84  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180051d88  lea     rax, [rbp+arg_0]
0x180051d8c  mov     [rsp+80h+ResultLength], rax; ResultLength
0x180051d91  lea     rdx, [rbp+ValueName]; ValueName
0x180051d95  xor     r9d, r9d; KeyValueInformation
0x180051d98  mov     [rsp+80h+Length], esi; Length
0x180051d9c  mov     r8d, 2; KeyValueInformationClass
0x180051da2  call    cs:__imp_ZwQueryValueKey
0x180051da9  nop     dword ptr [rax+rax+00h]
0x180051dae  cmp     eax, 0C0000023h
0x180051db3  jnz     loc_180051EAE
0x180051db9  mov     edx, dword ptr [rbp+arg_0]; NumberOfBytes
0x180051dbc  mov     ecx, 1; PoolType
0x180051dc1  mov     r8d, 6B70534Bh; Tag
0x180051dc7  call    cs:__imp_ExAllocatePoolWithTag
0x180051dce  nop     dword ptr [rax+rax+00h]
0x180051dd3  mov     rbx, rax
0x180051dd6  test    rax, rax
0x180051dd9  jz      short loc_180051E2D
0x180051ddb  mov     r8d, dword ptr [rbp+arg_0]; Size
0x180051ddf  xor     edx, edx; Val
0x180051de1  mov     rcx, rax; void *
0x180051de4  call    memset
0x180051de9  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180051ded  lea     rax, [rbp+arg_0]
0x180051df1  mov     [rsp+80h+ResultLength], rax; ResultLength
0x180051df6  lea     rdx, [rbp+ValueName]; ValueName
0x180051dfa  mov     eax, dword ptr [rbp+arg_0]
0x180051dfd  mov     r9, rbx; KeyValueInformation
0x180051e00  mov     r8d, 2; KeyValueInformationClass
0x180051e06  mov     [rsp+80h+Length], eax; Length
0x180051e0a  call    cs:__imp_ZwQueryValueKey
0x180051e11  nop     dword ptr [rax+rax+00h]
0x180051e16  test    eax, eax
0x180051e18  js      short loc_180051E2D
0x180051e1a  cmp     dword ptr [rbx+4], 4
0x180051e1e  jnz     short loc_180051E2D
0x180051e20  cmp     dword ptr [rbx+8], 4
0x180051e24  jnz     short loc_180051E2D
0x180051e26  cmp     [rbx+0Ch], esi
0x180051e29  setnz   dil
0x180051e2d  mov     rcx, [rbp+KeyHandle]; Handle
0x180051e31  test    rcx, rcx
0x180051e34  jz      short loc_180051E46
0x180051e36  call    cs:__imp_ZwClose
0x180051e3d  nop     dword ptr [rax+rax+00h]
0x180051e42  mov     [rbp+KeyHandle], rsi
0x180051e46  test    rbx, rbx
0x180051e49  jz      short loc_180051E5C
0x180051e4b  xor     edx, edx; Tag
0x180051e4d  mov     rcx, rbx; P
0x180051e50  call    cs:__imp_ExFreePoolWithTag
0x180051e57  nop     dword ptr [rax+rax+00h]
0x180051e5c  mov     rbx, [rsp+80h+arg_10]
0x180051e64  movzx   eax, dil
0x180051e68  add     rsp, 80h
0x180051e6f  pop     rdi
0x180051e70  pop     rsi
0x180051e71  pop     rbp
0x180051e72  retn
0x180051e74  mov     rcx, cs:WPP_GLOBAL_Control
0x180051e7b  cmp     word ptr [rcx+48h], 0
0x180051e80  jz      loc_180051CEB
0x180051e86  mov     rcx, [rcx+40h]
0x180051e8a  lea     rax, WPP_0f409e30936e3eb7e2fb5867878996e2_Traceguids
0x180051e91  mov     r9d, 22h ; '"'
0x180051e97  mov     qword ptr [rsp+80h+Length], rax
0x180051e9c  mov     r8d, 1
0x180051ea2  mov     dl, 5
0x180051ea4  call    WPP_RECORDER_SF_
0x180051ea9  jmp     loc_180051CEB
0x180051eae  cmp     eax, 80000005h
0x180051eb3  jnz     loc_180051E2D
0x180051eb9  jmp     loc_180051DB9
```
