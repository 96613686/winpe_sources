# CipQueryLockDownPolicyRestriction

- ea: `0x180075ea4`
- end: `0x180075fc4`
- name: `CipQueryLockDownPolicyRestriction`
- size: `288`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18005eac0`

## callees

- `0x18002c0d0`
- `0x180075ea4`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x180075f57`
- `ntoskrnl!ZwQueryValueKey` at `0x180075f57`
- `ntoskrnl!ZwClose` at `0x180075f8b`
- `ntoskrnl!ZwClose` at `0x180075f8b`
- `ntoskrnl!ZwOpenKey` at `0x180075f22`
- `ntoskrnl!ZwOpenKey` at `0x180075f22`

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
0x180075ea4  mov     [rsp-8+arg_8], rbx
0x180075ea9  mov     [rsp-8+arg_10], rdi
0x180075eae  push    rbp
0x180075eaf  lea     rbp, [rsp-57h]
0x180075eb4  sub     rsp, 0A0h
0x180075ebb  mov     rax, cs:__security_cookie
0x180075ec2  xor     rax, rsp
0x180075ec5  mov     [rbp+57h+var_8], rax
0x180075ec9  lea     rax, aLockdownrestri; "LockDownRestriction"
0x180075ed0  mov     [rbp+57h+KeyHandle], 0
0x180075ed8  mov     [rbp+57h+ValueName.Buffer], rax
0x180075edc  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180075ee0  xor     eax, eax
0x180075ee2  mov     qword ptr [rbp+57h+ValueName.Length], 280026h
0x180075eea  mov     [rcx], al
0x180075eec  mov     rdi, rcx
0x180075eef  mov     [rbp+57h+var_70], eax
0x180075ef2  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180075ef6  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x180075efa  xorps   xmm0, xmm0
0x180075efd  lea     rax, aXz; "xz"
0x180075f04  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180075f0c  mov     edx, 20019h; DesiredAccess
0x180075f11  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180075f15  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x180075f1d  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180075f22  call    cs:__imp_ZwOpenKey
0x180075f29  nop     dword ptr [rax+rax+00h]
0x180075f2e  mov     ebx, eax
0x180075f30  test    eax, eax
0x180075f32  js      short loc_180075F97
0x180075f34  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180075f38  lea     rax, [rbp+57h+var_70]
0x180075f3c  mov     [rsp+0A0h+ResultLength], rax; ResultLength
0x180075f41  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x180075f45  mov     r8d, 2; KeyValueInformationClass
0x180075f4b  mov     [rsp+0A0h+Length], 14h; Length
0x180075f53  lea     rdx, [rbp+57h+ValueName]; ValueName
0x180075f57  call    cs:__imp_ZwQueryValueKey
0x180075f5e  nop     dword ptr [rax+rax+00h]
0x180075f63  mov     ebx, eax
0x180075f65  test    eax, eax
0x180075f67  js      short loc_180075F83
0x180075f69  cmp     [rbp+57h+var_1C], 4
0x180075f6d  jnz     short loc_180075F83
0x180075f6f  cmp     [rbp+57h+var_18], 4
0x180075f73  jb      short loc_180075F83
0x180075f75  mov     eax, [rbp+57h+var_14]
0x180075f78  mov     ecx, 1
0x180075f7d  dec     eax
0x180075f7f  cmp     eax, ecx
0x180075f81  jbe     short loc_180075F85
0x180075f83  xor     cl, cl
0x180075f85  mov     [rdi], cl
0x180075f87  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x180075f8b  call    cs:__imp_ZwClose
0x180075f92  nop     dword ptr [rax+rax+00h]
0x180075f97  xor     eax, eax
0x180075f99  cmp     ebx, 0C0000034h
0x180075f9f  cmovnz  eax, ebx
0x180075fa2  mov     rcx, [rbp+57h+var_8]
0x180075fa6  xor     rcx, rsp; StackCookie
0x180075fa9  call    __security_check_cookie
0x180075fae  lea     r11, [rsp+0A0h+var_s0]
0x180075fb6  mov     rbx, [r11+18h]
0x180075fba  mov     rdi, [r11+20h]
0x180075fbe  mov     rsp, r11
0x180075fc1  pop     rbp
0x180075fc2  retn
```
