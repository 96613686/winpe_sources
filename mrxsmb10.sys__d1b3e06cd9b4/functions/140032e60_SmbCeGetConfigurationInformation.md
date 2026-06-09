# SmbCeGetConfigurationInformation

- ea: `0x140032e60`
- end: `0x1400330ad`
- name: `SmbCeGetConfigurationInformation`
- size: `589`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14003108c`

## callees

- `0x14000dfa8`
- `0x14000f760`
- `0x140016560`
- `0x140032114`
- `0x1400327a4`
- `0x140032e60`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x140032f06`
- `ntoskrnl!ZwOpenKey` at `0x140032f06`
- `ntoskrnl!ZwClose` at `0x14003307d`
- `ntoskrnl!ZwClose` at `0x14003307d`
- `ntoskrnl!ZwQueryValueKey` at `0x140032f54`
- `ntoskrnl!ZwQueryValueKey` at `0x140032ffa`
- `ntoskrnl!ZwQueryValueKey` at `0x140032f54`
- `ntoskrnl!ZwQueryValueKey` at `0x140032ffa`
- `ntoskrnl!RtlInitUnicodeString` at `0x140032ec7`
- `ntoskrnl!RtlInitUnicodeString` at `0x140032f25`
- `ntoskrnl!RtlInitUnicodeString` at `0x140032ec7`
- `ntoskrnl!RtlInitUnicodeString` at `0x140032f25`
- `ntoskrnl!ExAllocatePool2` at `0x140032fc8`
- `ntoskrnl!ExAllocatePool2` at `0x140032fc8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032f9c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003306d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032f9c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003306d`

## string_xrefs

- `0x140032ebc`: `\Registry\Machine\System\CurrentControlSet\Services\LanmanWorkStation\Linkage`

## pseudocode

```c
NTSTATUS SmbCeGetConfigurationInformation()
{
  NTSTATUS result; // eax
  NTSTATUS v1; // eax
  NTSTATUS v2; // ebx
  ULONG Length; // ebx
  __int64 Pool2; // rdi
  ULONG ResultLength; // [rsp+30h] [rbp-19h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-11h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp+7h] BYREF
  __int128 KeyValueInformation; // [rsp+80h] [rbp+37h] BYREF

  KeyHandle = 0;
  ResultLength = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  KeyValueInformation = 0;
  MRxSmbGetPolicyInformation();
  MRxSmbReadMiscellaneousRegistryParameters();
  MRxSmbReadSmb1UninstallRegistryParameters();
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanWorkStation\\Linkage");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( result >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"Bind");
    v1 = ZwQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           &KeyValueInformation,
           0x10u,
           &ResultLength);
    v2 = 0;
    if ( v1 != -2147483643 )
      v2 = v1;
    if ( v2 >= 0 )
    {
      Length = DWORD2(KeyValueInformation) + 16;
      if ( (unsigned int)(DWORD2(KeyValueInformation) + 16) > 0xFFFF )
        goto LABEL_6;
      if ( stru_140020300.Buffer )
      {
        ExFreePoolWithTag(stru_140020300.Buffer - 6, 0);
        stru_140020300.Buffer = 0;
        *(_DWORD *)&stru_140020300.Length = 0;
      }
      Pool2 = ExAllocatePool2(258, Length, 1934454099);
      if ( Pool2 )
      {
        v2 = ZwQueryValueKey(
               KeyHandle,
               &DestinationString,
               KeyValuePartialInformation,
               (PVOID)Pool2,
               Length,
               &ResultLength);
        if ( v2 >= 0 && *(_DWORD *)(Pool2 + 8) && *(_DWORD *)(Pool2 + 4) == 7 )
        {
          stru_140020300.Length = *(_WORD *)(Pool2 + 8);
          stru_140020300.MaximumLength = stru_140020300.Length;
          stru_140020300.Buffer = (PWSTR)(Pool2 + 12);
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_3ef6dccc05f63d6d417ef27503099bef_Traceguids);
          }
          ExFreePoolWithTag((PVOID)Pool2, 0);
        }
      }
      else
      {
LABEL_6:
        v2 = -1073741670;
      }
    }
    ZwClose(KeyHandle);
    return v2;
  }
  return result;
}

```

## disassembly

```asm
0x140032e60  mov     [rsp-8+arg_0], rbx
0x140032e65  mov     [rsp-8+arg_8], rdi
0x140032e6a  push    rbp
0x140032e6b  lea     rbp, [rsp-57h]
0x140032e70  sub     rsp, 0A0h
0x140032e77  mov     rax, cs:__security_cookie
0x140032e7e  xor     rax, rsp
0x140032e81  mov     [rbp+57h+var_10], rax
0x140032e85  xorps   xmm0, xmm0
0x140032e88  mov     [rbp+57h+KeyHandle], 0
0x140032e90  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140032e94  xor     eax, eax
0x140032e96  mov     [rbp+57h+var_70], 0
0x140032e9d  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x140032ea1  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140032ea5  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140032ea9  movups  [rbp+57h+KeyValueInformation], xmm0
0x140032ead  call    MRxSmbGetPolicyInformation
0x140032eb2  call    MRxSmbReadMiscellaneousRegistryParameters
0x140032eb7  call    MRxSmbReadSmb1UninstallRegistryParameters
0x140032ebc  lea     rdx, aRegistryMachin_1; "\\Registry\\Machine\\System\\CurrentCon"...
0x140032ec3  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140032ec7  call    cs:__imp_RtlInitUnicodeString
0x140032ece  nop     dword ptr [rax+rax+00h]
0x140032ed3  lea     rax, [rbp+57h+DestinationString]
0x140032ed7  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140032ede  xorps   xmm0, xmm0
0x140032ee1  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140032ee5  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140032ee9  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140032ef1  mov     edx, 20019h; DesiredAccess
0x140032ef6  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140032efd  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140032f01  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140032f06  call    cs:__imp_ZwOpenKey
0x140032f0d  nop     dword ptr [rax+rax+00h]
0x140032f12  test    eax, eax
0x140032f14  js      loc_14003308B
0x140032f1a  lea     rdx, aBind; "Bind"
0x140032f21  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140032f25  call    cs:__imp_RtlInitUnicodeString
0x140032f2c  nop     dword ptr [rax+rax+00h]
0x140032f31  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140032f35  lea     rax, [rbp+57h+var_70]
0x140032f39  mov     [rsp+0A0h+ResultLength], rax; ResultLength
0x140032f3e  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x140032f42  mov     r8d, 2; KeyValueInformationClass
0x140032f48  mov     [rsp+0A0h+Length], 10h; Length
0x140032f50  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x140032f54  call    cs:__imp_ZwQueryValueKey
0x140032f5b  nop     dword ptr [rax+rax+00h]
0x140032f60  xor     ebx, ebx
0x140032f62  cmp     eax, 80000005h
0x140032f67  cmovnz  ebx, eax
0x140032f6a  test    ebx, ebx
0x140032f6c  js      loc_140033079
0x140032f72  mov     ebx, dword ptr [rbp+57h+KeyValueInformation+8]
0x140032f75  add     ebx, 10h
0x140032f78  cmp     ebx, 0FFFFh
0x140032f7e  jbe     short loc_140032F8A
0x140032f80  mov     ebx, 0C000009Ah
0x140032f85  jmp     loc_140033079
0x140032f8a  mov     rcx, cs:stru_140020300.Buffer
0x140032f91  test    rcx, rcx
0x140032f94  jz      short loc_140032FBB
0x140032f96  add     rcx, 0FFFFFFFFFFFFFFF4h; P
0x140032f9a  xor     edx, edx; Tag
0x140032f9c  call    cs:__imp_ExFreePoolWithTag
0x140032fa3  nop     dword ptr [rax+rax+00h]
0x140032fa8  xor     eax, eax
0x140032faa  mov     cs:stru_140020300.Buffer, 0
0x140032fb5  mov     dword ptr cs:stru_140020300.Length, eax
0x140032fbb  mov     edx, ebx
0x140032fbd  mov     ecx, 102h
0x140032fc2  mov     r8d, 734D6D53h
0x140032fc8  call    cs:__imp_ExAllocatePool2
0x140032fcf  nop     dword ptr [rax+rax+00h]
0x140032fd4  mov     rdi, rax
0x140032fd7  test    rax, rax
0x140032fda  jz      short loc_140032F80
0x140032fdc  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140032fe0  lea     rax, [rbp+57h+var_70]
0x140032fe4  mov     [rsp+0A0h+ResultLength], rax; ResultLength
0x140032fe9  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x140032fed  mov     r9, rdi; KeyValueInformation
0x140032ff0  mov     [rsp+0A0h+Length], ebx; Length
0x140032ff4  mov     r8d, 2; KeyValueInformationClass
0x140032ffa  call    cs:__imp_ZwQueryValueKey
0x140033001  nop     dword ptr [rax+rax+00h]
0x140033006  mov     ebx, eax
0x140033008  test    eax, eax
0x14003300a  js      short loc_140033037
0x14003300c  cmp     dword ptr [rdi+8], 0
0x140033010  jbe     short loc_140033037
0x140033012  cmp     dword ptr [rdi+4], 7
0x140033016  jnz     short loc_140033037
0x140033018  movzx   ecx, word ptr [rdi+8]
0x14003301c  mov     cs:stru_140020300.Length, cx
0x140033023  mov     cs:stru_140020300.MaximumLength, cx
0x14003302a  lea     rcx, [rdi+0Ch]
0x14003302e  mov     cs:stru_140020300.Buffer, rcx
0x140033035  jmp     short loc_140033079
0x140033037  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003303e  lea     rax, WPP_GLOBAL_Control
0x140033045  cmp     rcx, rax
0x140033048  jz      short loc_140033068
0x14003304a  test    dword ptr [rcx+2Ch], 200h
0x140033051  jz      short loc_140033068
0x140033053  mov     rcx, [rcx+18h]
0x140033057  lea     r8, WPP_3ef6dccc05f63d6d417ef27503099bef_Traceguids
0x14003305e  mov     edx, 13h
0x140033063  call    WPP_SF_
0x140033068  xor     edx, edx; Tag
0x14003306a  mov     rcx, rdi; P
0x14003306d  call    cs:__imp_ExFreePoolWithTag
0x140033074  nop     dword ptr [rax+rax+00h]
0x140033079  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x14003307d  call    cs:__imp_ZwClose
0x140033084  nop     dword ptr [rax+rax+00h]
0x140033089  mov     eax, ebx
0x14003308b  mov     rcx, [rbp+57h+var_10]
0x14003308f  xor     rcx, rsp; StackCookie
0x140033092  call    __security_check_cookie
0x140033097  lea     r11, [rsp+0A0h+var_s0]
0x14003309f  mov     rbx, [r11+10h]
0x1400330a3  mov     rdi, [r11+18h]
0x1400330a7  mov     rsp, r11
0x1400330aa  pop     rbp
0x1400330ab  retn
```
