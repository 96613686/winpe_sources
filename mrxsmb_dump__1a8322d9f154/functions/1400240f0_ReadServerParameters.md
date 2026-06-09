# ReadServerParameters

- ea: `0x1400240f0`
- end: `0x14002421a`
- name: `ReadServerParameters`
- size: `298`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14008fb70`
- `0x1400926ac`

## callees

- `0x1400240f0`
- `0x140059dc0`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x1400241d0`
- `ntoskrnl!ZwQueryValueKey` at `0x1400241d0`
- `ntoskrnl!ZwOpenKey` at `0x14002417a`
- `ntoskrnl!ZwOpenKey` at `0x14002417a`
- `ntoskrnl!RtlInitUnicodeString` at `0x140024137`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002419a`
- `ntoskrnl!RtlInitUnicodeString` at `0x140024137`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002419a`
- `ntoskrnl!ZwClose` at `0x1400241f4`
- `ntoskrnl!ZwClose` at `0x1400241f4`

## string_xrefs

- `0x14002410e`: `\Registry\Machine\System\CurrentControlSet\Services\LanmanServer\Parameters`

## pseudocode

```c
int ReadServerParameters()
{
  int result; // eax
  ULONG ResultLength; // [rsp+30h] [rbp-E8h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-E0h] BYREF
  UNICODE_STRING DestinationString; // [rsp+40h] [rbp-D8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-C8h] BYREF
  _BYTE KeyValueInformation[12]; // [rsp+80h] [rbp-98h] BYREF
  __int128 v6; // [rsp+8Ch] [rbp-8Ch]

  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( result >= 0 )
  {
    ResultLength = 0;
    RtlInitUnicodeString(&DestinationString, L"Guid");
    if ( ZwQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x80u,
           &ResultLength) >= 0 )
      xmmword_14007D0C4 = v6;
    return ZwClose(KeyHandle);
  }
  return result;
}

```

## disassembly

```asm
0x1400240f0  push    rbx
0x1400240f2  sub     rsp, 110h
0x1400240f9  mov     rax, cs:__security_cookie
0x140024100  xor     rax, rsp
0x140024103  mov     [rsp+118h+var_18], rax
0x14002410b  xorps   xmm0, xmm0
0x14002410e  lea     rdx, SourceString; "\\Registry\\Machine\\System\\CurrentCon"...
0x140024115  movups  xmmword ptr [rsp+118h+ObjectAttributes.ObjectName], xmm0
0x14002411a  xor     ebx, ebx
0x14002411c  lea     rcx, [rsp+118h+DestinationString]; DestinationString
0x140024121  xor     eax, eax
0x140024123  mov     [rsp+118h+KeyHandle], rbx
0x140024128  movups  xmmword ptr [rsp+118h+ObjectAttributes+1Ch], xmm0
0x14002412d  movups  xmmword ptr [rsp+118h+ObjectAttributes.Length], xmm0
0x140024132  movups  xmmword ptr [rsp+118h+DestinationString.Length], xmm0
0x140024137  call    cs:__imp_RtlInitUnicodeString
0x14002413e  nop     dword ptr [rax+rax+00h]
0x140024143  lea     rax, [rsp+118h+DestinationString]
0x140024148  mov     [rsp+118h+ObjectAttributes.Length], 30h ; '0'
0x140024150  xorps   xmm0, xmm0
0x140024153  mov     [rsp+118h+ObjectAttributes.ObjectName], rax
0x140024158  lea     r8, [rsp+118h+ObjectAttributes]; ObjectAttributes
0x14002415d  mov     [rsp+118h+ObjectAttributes.RootDirectory], rbx
0x140024162  mov     edx, 20019h; DesiredAccess
0x140024167  mov     [rsp+118h+ObjectAttributes.Attributes], 240h
0x14002416f  lea     rcx, [rsp+118h+KeyHandle]; KeyHandle
0x140024174  movdqu  xmmword ptr [rsp+118h+ObjectAttributes.SecurityDescriptor], xmm0
0x14002417a  call    cs:__imp_ZwOpenKey
0x140024181  nop     dword ptr [rax+rax+00h]
0x140024186  test    eax, eax
0x140024188  js      short loc_140024200
0x14002418a  lea     rdx, aGuid; "Guid"
0x140024191  mov     [rsp+118h+var_E8], ebx
0x140024195  lea     rcx, [rsp+118h+DestinationString]; DestinationString
0x14002419a  call    cs:__imp_RtlInitUnicodeString
0x1400241a1  nop     dword ptr [rax+rax+00h]
0x1400241a6  mov     rcx, [rsp+118h+KeyHandle]; KeyHandle
0x1400241ab  lea     rax, [rsp+118h+var_E8]
0x1400241b0  mov     [rsp+118h+ResultLength], rax; ResultLength
0x1400241b5  lea     r9, [rsp+118h+KeyValueInformation]; KeyValueInformation
0x1400241bd  mov     r8d, 2; KeyValueInformationClass
0x1400241c3  mov     [rsp+118h+Length], 80h; Length
0x1400241cb  lea     rdx, [rsp+118h+DestinationString]; ValueName
0x1400241d0  call    cs:__imp_ZwQueryValueKey
0x1400241d7  nop     dword ptr [rax+rax+00h]
0x1400241dc  test    eax, eax
0x1400241de  js      short loc_1400241EF
0x1400241e0  movups  xmm0, [rsp+118h+var_8C]
0x1400241e8  movups  cs:xmmword_14007D0C4, xmm0
0x1400241ef  mov     rcx, [rsp+118h+KeyHandle]; Handle
0x1400241f4  call    cs:__imp_ZwClose
0x1400241fb  nop     dword ptr [rax+rax+00h]
0x140024200  mov     rcx, [rsp+118h+var_18]
0x140024208  xor     rcx, rsp; StackCookie
0x14002420b  call    __security_check_cookie
0x140024210  add     rsp, 110h
0x140024217  pop     rbx
0x140024218  retn
```
