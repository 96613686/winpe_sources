# MupiGetIrpStackSize

- ea: `0x1400118fc`
- end: `0x140011a0f`
- name: `MupiGetIrpStackSize`
- size: `275`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140010f18`

## callees

- `0x1400054a0`
- `0x1400118fc`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140011981`
- `ntoskrnl!RtlInitUnicodeString` at `0x140011981`
- `ntoskrnl!ZwQueryValueKey` at `0x1400119b0`
- `ntoskrnl!ZwQueryValueKey` at `0x1400119b0`
- `ntoskrnl!ZwClose` at `0x1400119e3`
- `ntoskrnl!ZwClose` at `0x1400119e3`
- `ntoskrnl!ZwOpenKey` at `0x140011966`
- `ntoskrnl!ZwOpenKey` at `0x140011966`

## pseudocode

```c
char MupiGetIrpStackSize()
{
  char v0; // bl
  ULONG ResultLength; // [rsp+30h] [rbp-19h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-11h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp+7h] BYREF
  __int128 KeyValueInformation; // [rsp+80h] [rbp+37h] BYREF
  int v7; // [rsp+90h] [rbp+47h]

  *(_QWORD *)&ObjectAttributes.Length = 48;
  v7 = 0;
  ResultLength = 0;
  KeyHandle = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&WPP_MAIN_CB.Queue.Wcb.DeviceObject;
  v0 = 3;
  KeyValueInformation = 0;
  DestinationString = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"IrpStackSize");
    if ( ZwQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           &KeyValueInformation,
           0x14u,
           &ResultLength) >= 0
      && DWORD1(KeyValueInformation) == 4 )
    {
      v0 = 3;
      if ( (unsigned int)(HIDWORD(KeyValueInformation) - 4) <= 6 )
        v0 = BYTE12(KeyValueInformation);
    }
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return v0;
}

```

## disassembly

```asm
0x1400118fc  mov     [rsp-8+arg_0], rbx
0x140011901  push    rbp
0x140011902  lea     rbp, [rsp-57h]
0x140011907  sub     rsp, 0A0h
0x14001190e  mov     rax, cs:__security_cookie
0x140011915  xor     rax, rsp
0x140011918  mov     [rbp+57h+var_8], rax
0x14001191c  xor     eax, eax
0x14001191e  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140011926  xorps   xmm0, xmm0
0x140011929  mov     [rbp+57h+var_10], eax
0x14001192c  mov     [rbp+57h+var_70], eax
0x14001192f  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140011933  mov     [rbp+57h+KeyHandle], rax
0x140011937  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14001193b  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x14001193f  mov     edx, 20019h; DesiredAccess
0x140011944  lea     rax, WPP_MAIN_CB.Queue+30h
0x14001194b  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x140011953  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140011957  mov     bl, 3
0x140011959  movups  [rbp+57h+KeyValueInformation], xmm0
0x14001195d  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140011961  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140011966  call    cs:__imp_ZwOpenKey
0x14001196d  nop     dword ptr [rax+rax+00h]
0x140011972  test    eax, eax
0x140011974  js      short loc_1400119DA
0x140011976  lea     rdx, aIrpstacksize; "IrpStackSize"
0x14001197d  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140011981  call    cs:__imp_RtlInitUnicodeString
0x140011988  nop     dword ptr [rax+rax+00h]
0x14001198d  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140011991  lea     rax, [rbp+57h+var_70]
0x140011995  mov     [rsp+0A0h+ResultLength], rax; ResultLength
0x14001199a  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x14001199e  mov     r8d, 2; KeyValueInformationClass
0x1400119a4  mov     [rsp+0A0h+Length], 14h; Length
0x1400119ac  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x1400119b0  call    cs:__imp_ZwQueryValueKey
0x1400119b7  nop     dword ptr [rax+rax+00h]
0x1400119bc  test    eax, eax
0x1400119be  js      short loc_1400119DA
0x1400119c0  cmp     dword ptr [rbp+57h+KeyValueInformation+4], 4
0x1400119c4  jnz     short loc_1400119DA
0x1400119c6  mov     eax, dword ptr [rbp+57h+KeyValueInformation+0Ch]
0x1400119c9  movzx   ebx, bl
0x1400119cc  movzx   ecx, al
0x1400119cf  lea     r8d, [rax-4]
0x1400119d3  cmp     r8d, 6
0x1400119d7  cmovbe  ebx, ecx
0x1400119da  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1400119de  test    rcx, rcx
0x1400119e1  jz      short loc_1400119EF
0x1400119e3  call    cs:__imp_ZwClose
0x1400119ea  nop     dword ptr [rax+rax+00h]
0x1400119ef  mov     al, bl
0x1400119f1  mov     rcx, [rbp+57h+var_8]
0x1400119f5  xor     rcx, rsp; StackCookie
0x1400119f8  call    __security_check_cookie
0x1400119fd  mov     rbx, [rsp+0A0h+arg_0]
0x140011a05  add     rsp, 0A0h
0x140011a0c  pop     rbp
0x140011a0d  retn
```
