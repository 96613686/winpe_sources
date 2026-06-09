# HsmOsGetPolicyDWord

- ea: `0x140012efc`
- end: `0x140013115`
- name: `HsmOsGetPolicyDWord`
- size: `537`
- prototype: `__int64 __fastcall(PUNICODE_STRING ValueName, _BYTE *, _DWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140009364`
- `0x14007a214`

## callees

- `0x140012efc`
- `0x14001e1c0`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x14001308b`
- `ntoskrnl!ZwQueryValueKey` at `0x14001308b`
- `ntoskrnl!ZwOpenKey` at `0x140012fba`
- `ntoskrnl!ZwOpenKey` at `0x140013003`
- `ntoskrnl!ZwOpenKey` at `0x14001304c`
- `ntoskrnl!ZwOpenKey` at `0x140012fba`
- `ntoskrnl!ZwOpenKey` at `0x140013003`
- `ntoskrnl!ZwOpenKey` at `0x14001304c`
- `ntoskrnl!ZwClose` at `0x1400130c2`
- `ntoskrnl!ZwClose` at `0x1400130d7`
- `ntoskrnl!ZwClose` at `0x1400130ec`
- `ntoskrnl!ZwClose` at `0x1400130c2`
- `ntoskrnl!ZwClose` at `0x1400130d7`
- `ntoskrnl!ZwClose` at `0x1400130ec`

## string_xrefs

- `0x140012f23`: `\Registry\Machine`

## pseudocode

```c
__int64 __fastcall HsmOsGetPolicyDWord(PUNICODE_STRING ValueName, _BYTE *a2, _DWORD *a3)
{
  NTSTATUS v6; // ebx
  NTSTATUS v7; // eax
  NTSTATUS v8; // eax
  int v9; // eax
  void *KeyHandle; // [rsp+30h] [rbp-69h] BYREF
  ULONG ResultLength; // [rsp+38h] [rbp-61h] BYREF
  HANDLE v13; // [rsp+40h] [rbp-59h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-51h] BYREF
  HANDLE Handle; // [rsp+78h] [rbp-21h] BYREF
  _QWORD v16[2]; // [rsp+80h] [rbp-19h] BYREF
  _QWORD v17[2]; // [rsp+90h] [rbp-9h] BYREF
  _QWORD v18[2]; // [rsp+A0h] [rbp+7h] BYREF
  __int128 KeyValueInformation; // [rsp+B0h] [rbp+17h] BYREF

  *a2 = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  v16[1] = L"\\Registry\\Machine";
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  v17[1] = L"SOFTWARE";
  v16[0] = 2359330;
  v18[1] = L"SOFTWARE\\Policies\\Microsoft\\CloudFiles";
  v17[0] = 1179664;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v16;
  v18[0] = 5111884;
  KeyHandle = 0;
  Handle = 0;
  v13 = 0;
  KeyValueInformation = 0;
  ResultLength = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v6 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v6 >= 0 )
  {
    ObjectAttributes.RootDirectory = KeyHandle;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)v17;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v6 = ZwOpenKey(&Handle, 0x20019u, &ObjectAttributes);
    if ( v6 >= 0 )
    {
      ObjectAttributes.RootDirectory = KeyHandle;
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)v18;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v7 = ZwOpenKey(&v13, 0x20019u, &ObjectAttributes);
      v6 = v7;
      if ( v7 == -1073741772 )
      {
LABEL_4:
        v6 = 0;
        goto LABEL_11;
      }
      if ( v7 >= 0 )
      {
        v8 = ZwQueryValueKey(v13, ValueName, KeyValuePartialInformation, &KeyValueInformation, 0x10u, &ResultLength);
        v6 = v8;
        if ( v8 == -1073741772 )
          goto LABEL_4;
        if ( v8 >= 0 )
        {
          if ( DWORD1(KeyValueInformation) == 4 )
          {
            v9 = HIDWORD(KeyValueInformation);
            *a2 = 1;
            *a3 = v9;
          }
          else
          {
            v6 = -1073741788;
          }
        }
      }
    }
  }
LABEL_11:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( Handle )
    ZwClose(Handle);
  if ( v13 )
    ZwClose(v13);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140012efc  push    rbp
0x140012efe  push    rbx
0x140012eff  push    rsi
0x140012f00  push    rdi
0x140012f01  push    r14
0x140012f03  lea     rbp, [rsp-37h]
0x140012f08  sub     rsp, 0D0h
0x140012f0f  mov     rax, cs:__security_cookie
0x140012f16  xor     rax, rsp
0x140012f19  mov     [rbp+57h+var_30], rax
0x140012f1d  xorps   xmm0, xmm0
0x140012f20  mov     byte ptr [rdx], 0
0x140012f23  lea     rax, aRegistryMachin_1; "\\Registry\\Machine"
0x140012f2a  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140012f32  mov     [rbp+57h+var_68], rax
0x140012f36  mov     rsi, r8
0x140012f39  lea     rax, aSoftware; "SOFTWARE"
0x140012f40  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x140012f48  mov     [rbp+57h+var_58], rax
0x140012f4c  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140012f50  lea     rax, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\CloudFil"...
0x140012f57  mov     [rbp+57h+var_70], 240022h
0x140012f5f  mov     [rbp+57h+var_48], rax
0x140012f63  mov     rdi, rdx
0x140012f66  lea     rax, [rbp+57h+var_70]
0x140012f6a  mov     [rbp+57h+var_60], 120010h
0x140012f72  mov     r14, rcx
0x140012f75  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140012f79  mov     edx, 20019h; DesiredAccess
0x140012f7e  mov     [rbp+57h+var_50], 4E004Ch
0x140012f86  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140012f8a  mov     [rbp+57h+KeyHandle], 0
0x140012f92  mov     [rbp+57h+Handle], 0
0x140012f9a  mov     [rbp+57h+var_B0], 0
0x140012fa2  movups  [rbp+57h+KeyValueInformation], xmm0
0x140012fa6  mov     [rbp+57h+var_B8], 0
0x140012fad  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140012fb5  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140012fba  call    cs:__imp_ZwOpenKey
0x140012fc1  nop     dword ptr [rax+rax+00h]
0x140012fc6  mov     ebx, eax
0x140012fc8  test    eax, eax
0x140012fca  js      loc_1400130B9
0x140012fd0  mov     rax, [rbp+57h+KeyHandle]
0x140012fd4  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140012fd8  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x140012fdc  lea     rcx, [rbp+57h+Handle]; KeyHandle
0x140012fe0  lea     rax, [rbp+57h+var_60]
0x140012fe4  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140012feb  xorps   xmm0, xmm0
0x140012fee  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140012ff2  mov     edx, 20019h; DesiredAccess
0x140012ff7  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140012ffe  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140013003  call    cs:__imp_ZwOpenKey
0x14001300a  nop     dword ptr [rax+rax+00h]
0x14001300f  mov     ebx, eax
0x140013011  test    eax, eax
0x140013013  js      loc_1400130B9
0x140013019  mov     rax, [rbp+57h+KeyHandle]
0x14001301d  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140013021  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x140013025  lea     rcx, [rbp+57h+var_B0]; KeyHandle
0x140013029  lea     rax, [rbp+57h+var_50]
0x14001302d  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140013034  xorps   xmm0, xmm0
0x140013037  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14001303b  mov     edx, 20019h; DesiredAccess
0x140013040  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140013047  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14001304c  call    cs:__imp_ZwOpenKey
0x140013053  nop     dword ptr [rax+rax+00h]
0x140013058  mov     ebx, eax
0x14001305a  cmp     eax, 0C0000034h
0x14001305f  jnz     short loc_140013065
0x140013061  xor     ebx, ebx
0x140013063  jmp     short loc_1400130B9
0x140013065  test    eax, eax
0x140013067  js      short loc_1400130B9
0x140013069  mov     rcx, [rbp+57h+var_B0]; KeyHandle
0x14001306d  lea     rax, [rbp+57h+var_B8]
0x140013071  mov     [rsp+0F0h+ResultLength], rax; ResultLength
0x140013076  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x14001307a  mov     r8d, 2; KeyValueInformationClass
0x140013080  mov     [rsp+0F0h+Length], 10h; Length
0x140013088  mov     rdx, r14; ValueName
0x14001308b  call    cs:__imp_ZwQueryValueKey
0x140013092  nop     dword ptr [rax+rax+00h]
0x140013097  mov     ebx, eax
0x140013099  cmp     eax, 0C0000034h
0x14001309e  jz      short loc_140013061
0x1400130a0  test    eax, eax
0x1400130a2  js      short loc_1400130B9
0x1400130a4  cmp     dword ptr [rbp+57h+KeyValueInformation+4], 4
0x1400130a8  jz      short loc_1400130B1
0x1400130aa  mov     ebx, 0C0000024h
0x1400130af  jmp     short loc_1400130B9
0x1400130b1  mov     eax, dword ptr [rbp+57h+KeyValueInformation+0Ch]
0x1400130b4  mov     byte ptr [rdi], 1
0x1400130b7  mov     [rsi], eax
0x1400130b9  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1400130bd  test    rcx, rcx
0x1400130c0  jz      short loc_1400130CE
0x1400130c2  call    cs:__imp_ZwClose
0x1400130c9  nop     dword ptr [rax+rax+00h]
0x1400130ce  mov     rcx, [rbp+57h+Handle]; Handle
0x1400130d2  test    rcx, rcx
0x1400130d5  jz      short loc_1400130E3
0x1400130d7  call    cs:__imp_ZwClose
0x1400130de  nop     dword ptr [rax+rax+00h]
0x1400130e3  mov     rcx, [rbp+57h+var_B0]; Handle
0x1400130e7  test    rcx, rcx
0x1400130ea  jz      short loc_1400130F8
0x1400130ec  call    cs:__imp_ZwClose
0x1400130f3  nop     dword ptr [rax+rax+00h]
0x1400130f8  mov     eax, ebx
0x1400130fa  mov     rcx, [rbp+57h+var_30]
0x1400130fe  xor     rcx, rsp; StackCookie
0x140013101  call    __security_check_cookie
0x140013106  add     rsp, 0D0h
0x14001310d  pop     r14
0x14001310f  pop     rdi
0x140013110  pop     rsi
0x140013111  pop     rbx
0x140013112  pop     rbp
0x140013113  retn
```
