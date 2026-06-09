# CipQueryLockDownPolicyRestriction

- ea: `0x180075bc4`
- end: `0x180075ce4`
- name: `CipQueryLockDownPolicyRestriction`
- size: `288`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18005eb20`

## callees

- `0x18002bf20`
- `0x180075bc4`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x180075c77`
- `ntoskrnl!ZwQueryValueKey` at `0x180075c77`
- `ntoskrnl!ZwClose` at `0x180075cab`
- `ntoskrnl!ZwClose` at `0x180075cab`
- `ntoskrnl!ZwOpenKey` at `0x180075c42`
- `ntoskrnl!ZwOpenKey` at `0x180075c42`

## pseudocode

```c
__int64 __fastcall CipQueryLockDownPolicyRestriction(char *a1)
{
  NTSTATUS v2; // ebx
  char v3; // cl
  __int64 result; // rax
  ULONG ResultLength; // [rsp+30h] [rbp-19h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-11h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+40h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp+7h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+80h] [rbp+37h] BYREF
  int v10; // [rsp+84h] [rbp+3Bh]
  unsigned int v11; // [rsp+88h] [rbp+3Fh]
  int v12; // [rsp+8Ch] [rbp+43h]

  KeyHandle = 0;
  ValueName.Buffer = L"LockDownRestriction";
  *(_QWORD *)&ValueName.Length = 2621478;
  *a1 = 0;
  ResultLength = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)L"xz";
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v2 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v2 >= 0 )
  {
    v2 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, KeyValueInformation, 0x14u, &ResultLength);
    if ( v2 < 0 || v10 != 4 || v11 < 4 || (v3 = 1, (unsigned int)(v12 - 1) > 1) )
      v3 = 0;
    *a1 = v3;
    ZwClose(KeyHandle);
  }
  result = 0;
  if ( v2 != -1073741772 )
    return (unsigned int)v2;
  return result;
}

```

## disassembly

```asm
0x180075bc4  mov     [rsp-8+arg_8], rbx
0x180075bc9  mov     [rsp-8+arg_10], rdi
0x180075bce  push    rbp
0x180075bcf  lea     rbp, [rsp-57h]
0x180075bd4  sub     rsp, 0A0h
0x180075bdb  mov     rax, cs:__security_cookie
0x180075be2  xor     rax, rsp
0x180075be5  mov     [rbp+57h+var_8], rax
0x180075be9  lea     rax, aLockdownrestri; "LockDownRestriction"
0x180075bf0  mov     [rbp+57h+KeyHandle], 0
0x180075bf8  mov     [rbp+57h+ValueName.Buffer], rax
0x180075bfc  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180075c00  xor     eax, eax
0x180075c02  mov     qword ptr [rbp+57h+ValueName.Length], 280026h
0x180075c0a  mov     [rcx], al
0x180075c0c  mov     rdi, rcx
0x180075c0f  mov     [rbp+57h+var_70], eax
0x180075c12  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180075c16  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x180075c1a  xorps   xmm0, xmm0
0x180075c1d  lea     rax, aXz; "xz"
0x180075c24  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180075c2c  mov     edx, 20019h; DesiredAccess
0x180075c31  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180075c35  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x180075c3d  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180075c42  call    cs:__imp_ZwOpenKey
0x180075c49  nop     dword ptr [rax+rax+00h]
0x180075c4e  mov     ebx, eax
0x180075c50  test    eax, eax
0x180075c52  js      short loc_180075CB7
0x180075c54  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180075c58  lea     rax, [rbp+57h+var_70]
0x180075c5c  mov     [rsp+0A0h+ResultLength], rax; ResultLength
0x180075c61  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x180075c65  mov     r8d, 2; KeyValueInformationClass
0x180075c6b  mov     [rsp+0A0h+Length], 14h; Length
0x180075c73  lea     rdx, [rbp+57h+ValueName]; ValueName
0x180075c77  call    cs:__imp_ZwQueryValueKey
0x180075c7e  nop     dword ptr [rax+rax+00h]
0x180075c83  mov     ebx, eax
0x180075c85  test    eax, eax
0x180075c87  js      short loc_180075CA3
0x180075c89  cmp     [rbp+57h+var_1C], 4
0x180075c8d  jnz     short loc_180075CA3
0x180075c8f  cmp     [rbp+57h+var_18], 4
0x180075c93  jb      short loc_180075CA3
0x180075c95  mov     eax, [rbp+57h+var_14]
0x180075c98  mov     ecx, 1
0x180075c9d  dec     eax
0x180075c9f  cmp     eax, ecx
0x180075ca1  jbe     short loc_180075CA5
0x180075ca3  xor     cl, cl
0x180075ca5  mov     [rdi], cl
0x180075ca7  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x180075cab  call    cs:__imp_ZwClose
0x180075cb2  nop     dword ptr [rax+rax+00h]
0x180075cb7  xor     eax, eax
0x180075cb9  cmp     ebx, 0C0000034h
0x180075cbf  cmovnz  eax, ebx
0x180075cc2  mov     rcx, [rbp+57h+var_8]
0x180075cc6  xor     rcx, rsp; StackCookie
0x180075cc9  call    __security_check_cookie
0x180075cce  lea     r11, [rsp+0A0h+var_s0]
0x180075cd6  mov     rbx, [r11+18h]
0x180075cda  mov     rdi, [r11+20h]
0x180075cde  mov     rsp, r11
0x180075ce1  pop     rbp
0x180075ce2  retn
```
