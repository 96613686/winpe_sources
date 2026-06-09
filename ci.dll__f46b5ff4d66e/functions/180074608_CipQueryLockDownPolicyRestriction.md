# CipQueryLockDownPolicyRestriction

- ea: `0x180074608`
- end: `0x180074728`
- name: `CipQueryLockDownPolicyRestriction`
- size: `288`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18005e420`

## callees

- `0x18002bef0`
- `0x180074608`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x1800746bb`
- `ntoskrnl!ZwQueryValueKey` at `0x1800746bb`
- `ntoskrnl!ZwClose` at `0x1800746ef`
- `ntoskrnl!ZwClose` at `0x1800746ef`
- `ntoskrnl!ZwOpenKey` at `0x180074686`
- `ntoskrnl!ZwOpenKey` at `0x180074686`

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
0x180074608  mov     [rsp-8+arg_8], rbx
0x18007460d  mov     [rsp-8+arg_10], rdi
0x180074612  push    rbp
0x180074613  lea     rbp, [rsp-57h]
0x180074618  sub     rsp, 0A0h
0x18007461f  mov     rax, cs:__security_cookie
0x180074626  xor     rax, rsp
0x180074629  mov     [rbp+57h+var_8], rax
0x18007462d  lea     rax, aLockdownrestri; "LockDownRestriction"
0x180074634  mov     [rbp+57h+KeyHandle], 0
0x18007463c  mov     [rbp+57h+ValueName.Buffer], rax
0x180074640  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180074644  xor     eax, eax
0x180074646  mov     qword ptr [rbp+57h+ValueName.Length], 280026h
0x18007464e  mov     [rcx], al
0x180074650  mov     rdi, rcx
0x180074653  mov     [rbp+57h+var_70], eax
0x180074656  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18007465a  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x18007465e  xorps   xmm0, xmm0
0x180074661  lea     rax, aXz; "xz"
0x180074668  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180074670  mov     edx, 20019h; DesiredAccess
0x180074675  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180074679  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x180074681  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180074686  call    cs:__imp_ZwOpenKey
0x18007468d  nop     dword ptr [rax+rax+00h]
0x180074692  mov     ebx, eax
0x180074694  test    eax, eax
0x180074696  js      short loc_1800746FB
0x180074698  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18007469c  lea     rax, [rbp+57h+var_70]
0x1800746a0  mov     [rsp+0A0h+ResultLength], rax; ResultLength
0x1800746a5  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x1800746a9  mov     r8d, 2; KeyValueInformationClass
0x1800746af  mov     [rsp+0A0h+Length], 14h; Length
0x1800746b7  lea     rdx, [rbp+57h+ValueName]; ValueName
0x1800746bb  call    cs:__imp_ZwQueryValueKey
0x1800746c2  nop     dword ptr [rax+rax+00h]
0x1800746c7  mov     ebx, eax
0x1800746c9  test    eax, eax
0x1800746cb  js      short loc_1800746E7
0x1800746cd  cmp     [rbp+57h+var_1C], 4
0x1800746d1  jnz     short loc_1800746E7
0x1800746d3  cmp     [rbp+57h+var_18], 4
0x1800746d7  jb      short loc_1800746E7
0x1800746d9  mov     eax, [rbp+57h+var_14]
0x1800746dc  mov     ecx, 1
0x1800746e1  dec     eax
0x1800746e3  cmp     eax, ecx
0x1800746e5  jbe     short loc_1800746E9
0x1800746e7  xor     cl, cl
0x1800746e9  mov     [rdi], cl
0x1800746eb  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1800746ef  call    cs:__imp_ZwClose
0x1800746f6  nop     dword ptr [rax+rax+00h]
0x1800746fb  xor     eax, eax
0x1800746fd  cmp     ebx, 0C0000034h
0x180074703  cmovnz  eax, ebx
0x180074706  mov     rcx, [rbp+57h+var_8]
0x18007470a  xor     rcx, rsp; StackCookie
0x18007470d  call    __security_check_cookie
0x180074712  lea     r11, [rsp+0A0h+var_s0]
0x18007471a  mov     rbx, [r11+18h]
0x18007471e  mov     rdi, [r11+20h]
0x180074722  mov     rsp, r11
0x180074725  pop     rbp
0x180074726  retn
```
