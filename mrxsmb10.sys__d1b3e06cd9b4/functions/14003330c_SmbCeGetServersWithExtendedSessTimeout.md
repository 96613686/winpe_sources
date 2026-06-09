# SmbCeGetServersWithExtendedSessTimeout

- ea: `0x14003330c`
- end: `0x140033519`
- name: `SmbCeGetServersWithExtendedSessTimeout`
- size: `525`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14003108c`

## callees

- `0x14000dfa8`
- `0x140016560`
- `0x14003330c`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x1400333a3`
- `ntoskrnl!ZwOpenKey` at `0x1400333a3`
- `ntoskrnl!ZwClose` at `0x1400334e9`
- `ntoskrnl!ZwClose` at `0x1400334e9`
- `ntoskrnl!ZwQueryValueKey` at `0x1400333f1`
- `ntoskrnl!ZwQueryValueKey` at `0x140033466`
- `ntoskrnl!ZwQueryValueKey` at `0x1400333f1`
- `ntoskrnl!ZwQueryValueKey` at `0x140033466`
- `ntoskrnl!RtlInitUnicodeString` at `0x140033364`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400333c2`
- `ntoskrnl!RtlInitUnicodeString` at `0x140033364`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400333c2`
- `ntoskrnl!ExAllocatePool2` at `0x140033434`
- `ntoskrnl!ExAllocatePool2` at `0x140033434`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400334d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400334d9`

## string_xrefs

- `0x140033349`: `\Registry\Machine\System\CurrentControlSet\Services\LanmanWorkStation\Parameters`

## pseudocode

```c
NTSTATUS SmbCeGetServersWithExtendedSessTimeout()
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
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanWorkStation\\Parameters");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( result >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"ServersWithExtendedSessTimeout");
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
      if ( (unsigned int)(DWORD2(KeyValueInformation) + 16) <= 0xFFFF
        && (Pool2 = ExAllocatePool2(258, Length, 1934454099)) != 0 )
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
          stru_140020310.Length = *(_WORD *)(Pool2 + 8);
          stru_140020310.MaximumLength = stru_140020310.Length;
          stru_140020310.Buffer = (PWSTR)(Pool2 + 12);
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_3ef6dccc05f63d6d417ef27503099bef_Traceguids);
          }
          ExFreePoolWithTag((PVOID)Pool2, 0);
        }
      }
      else
      {
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
0x14003330c  mov     [rsp-8+arg_0], rbx
0x140033311  mov     [rsp-8+arg_8], rdi
0x140033316  push    rbp
0x140033317  lea     rbp, [rsp-57h]
0x14003331c  sub     rsp, 0A0h
0x140033323  mov     rax, cs:__security_cookie
0x14003332a  xor     rax, rsp
0x14003332d  mov     [rbp+57h+var_10], rax
0x140033331  xorps   xmm0, xmm0
0x140033334  mov     [rbp+57h+KeyHandle], 0
0x14003333c  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140033340  xor     eax, eax
0x140033342  mov     [rbp+57h+var_70], 0
0x140033349  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x140033350  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140033354  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x140033358  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14003335c  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140033360  movups  [rbp+57h+KeyValueInformation], xmm0
0x140033364  call    cs:__imp_RtlInitUnicodeString
0x14003336b  nop     dword ptr [rax+rax+00h]
0x140033370  lea     rax, [rbp+57h+DestinationString]
0x140033374  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14003337b  xorps   xmm0, xmm0
0x14003337e  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140033382  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140033386  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14003338e  mov     edx, 20019h; DesiredAccess
0x140033393  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14003339a  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14003339e  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400333a3  call    cs:__imp_ZwOpenKey
0x1400333aa  nop     dword ptr [rax+rax+00h]
0x1400333af  test    eax, eax
0x1400333b1  js      loc_1400334F7
0x1400333b7  lea     rdx, aServerswithext; "ServersWithExtendedSessTimeout"
0x1400333be  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400333c2  call    cs:__imp_RtlInitUnicodeString
0x1400333c9  nop     dword ptr [rax+rax+00h]
0x1400333ce  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400333d2  lea     rax, [rbp+57h+var_70]
0x1400333d6  mov     [rsp+0A0h+ResultLength], rax; ResultLength
0x1400333db  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x1400333df  mov     r8d, 2; KeyValueInformationClass
0x1400333e5  mov     [rsp+0A0h+Length], 10h; Length
0x1400333ed  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x1400333f1  call    cs:__imp_ZwQueryValueKey
0x1400333f8  nop     dword ptr [rax+rax+00h]
0x1400333fd  xor     ebx, ebx
0x1400333ff  cmp     eax, 80000005h
0x140033404  cmovnz  ebx, eax
0x140033407  test    ebx, ebx
0x140033409  js      loc_1400334E5
0x14003340f  mov     ebx, dword ptr [rbp+57h+KeyValueInformation+8]
0x140033412  add     ebx, 10h
0x140033415  cmp     ebx, 0FFFFh
0x14003341b  jbe     short loc_140033427
0x14003341d  mov     ebx, 0C000009Ah
0x140033422  jmp     loc_1400334E5
0x140033427  mov     edx, ebx
0x140033429  mov     ecx, 102h
0x14003342e  mov     r8d, 734D6D53h
0x140033434  call    cs:__imp_ExAllocatePool2
0x14003343b  nop     dword ptr [rax+rax+00h]
0x140033440  mov     rdi, rax
0x140033443  test    rax, rax
0x140033446  jz      short loc_14003341D
0x140033448  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14003344c  lea     rax, [rbp+57h+var_70]
0x140033450  mov     [rsp+0A0h+ResultLength], rax; ResultLength
0x140033455  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x140033459  mov     r9, rdi; KeyValueInformation
0x14003345c  mov     [rsp+0A0h+Length], ebx; Length
0x140033460  mov     r8d, 2; KeyValueInformationClass
0x140033466  call    cs:__imp_ZwQueryValueKey
0x14003346d  nop     dword ptr [rax+rax+00h]
0x140033472  mov     ebx, eax
0x140033474  test    eax, eax
0x140033476  js      short loc_1400334A3
0x140033478  cmp     dword ptr [rdi+8], 0
0x14003347c  jbe     short loc_1400334A3
0x14003347e  cmp     dword ptr [rdi+4], 7
0x140033482  jnz     short loc_1400334A3
0x140033484  movzx   ecx, word ptr [rdi+8]
0x140033488  mov     cs:stru_140020310.Length, cx
0x14003348f  mov     cs:stru_140020310.MaximumLength, cx
0x140033496  lea     rcx, [rdi+0Ch]
0x14003349a  mov     cs:stru_140020310.Buffer, rcx
0x1400334a1  jmp     short loc_1400334E5
0x1400334a3  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400334aa  lea     rax, WPP_GLOBAL_Control
0x1400334b1  cmp     rcx, rax
0x1400334b4  jz      short loc_1400334D4
0x1400334b6  test    dword ptr [rcx+2Ch], 200h
0x1400334bd  jz      short loc_1400334D4
0x1400334bf  mov     rcx, [rcx+18h]
0x1400334c3  lea     r8, WPP_3ef6dccc05f63d6d417ef27503099bef_Traceguids
0x1400334ca  mov     edx, 14h
0x1400334cf  call    WPP_SF_
0x1400334d4  xor     edx, edx; Tag
0x1400334d6  mov     rcx, rdi; P
0x1400334d9  call    cs:__imp_ExFreePoolWithTag
0x1400334e0  nop     dword ptr [rax+rax+00h]
0x1400334e5  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1400334e9  call    cs:__imp_ZwClose
0x1400334f0  nop     dword ptr [rax+rax+00h]
0x1400334f5  mov     eax, ebx
0x1400334f7  mov     rcx, [rbp+57h+var_10]
0x1400334fb  xor     rcx, rsp; StackCookie
0x1400334fe  call    __security_check_cookie
0x140033503  lea     r11, [rsp+0A0h+var_s0]
0x14003350b  mov     rbx, [r11+10h]
0x14003350f  mov     rdi, [r11+18h]
0x140033513  mov     rsp, r11
0x140033516  pop     rbp
0x140033517  retn
```
