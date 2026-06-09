# HsmOsGetPolicyDWord

- ea: `0x140012e7c`
- end: `0x140013095`
- name: `HsmOsGetPolicyDWord`
- size: `537`
- prototype: `__int64 __fastcall(PUNICODE_STRING ValueName)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140009364`
- `0x14007a0d4`

## callees

- `0x140012e7c`
- `0x14001e140`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x14001300b`
- `ntoskrnl!ZwQueryValueKey` at `0x14001300b`
- `ntoskrnl!ZwOpenKey` at `0x140012f3a`
- `ntoskrnl!ZwOpenKey` at `0x140012f83`
- `ntoskrnl!ZwOpenKey` at `0x140012fcc`
- `ntoskrnl!ZwOpenKey` at `0x140012f3a`
- `ntoskrnl!ZwOpenKey` at `0x140012f83`
- `ntoskrnl!ZwOpenKey` at `0x140012fcc`
- `ntoskrnl!ZwClose` at `0x140013042`
- `ntoskrnl!ZwClose` at `0x140013057`
- `ntoskrnl!ZwClose` at `0x14001306c`
- `ntoskrnl!ZwClose` at `0x140013042`
- `ntoskrnl!ZwClose` at `0x140013057`
- `ntoskrnl!ZwClose` at `0x14001306c`

## string_xrefs

- `0x140012ea3`: `\Registry\Machine`

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
0x140012e7c  push    rbp
0x140012e7e  push    rbx
0x140012e7f  push    rsi
0x140012e80  push    rdi
0x140012e81  push    r14
0x140012e83  lea     rbp, [rsp-37h]
0x140012e88  sub     rsp, 0D0h
0x140012e8f  mov     rax, cs:__security_cookie
0x140012e96  xor     rax, rsp
0x140012e99  mov     [rbp+57h+var_30], rax
0x140012e9d  xorps   xmm0, xmm0
0x140012ea0  mov     byte ptr [rdx], 0
0x140012ea3  lea     rax, aRegistryMachin_1; "\\Registry\\Machine"
0x140012eaa  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140012eb2  mov     [rbp+57h+var_68], rax
0x140012eb6  mov     rsi, r8
0x140012eb9  lea     rax, aSoftware; "SOFTWARE"
0x140012ec0  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x140012ec8  mov     [rbp+57h+var_58], rax
0x140012ecc  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140012ed0  lea     rax, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\CloudFil"...
0x140012ed7  mov     [rbp+57h+var_70], 240022h
0x140012edf  mov     [rbp+57h+var_48], rax
0x140012ee3  mov     rdi, rdx
0x140012ee6  lea     rax, [rbp+57h+var_70]
0x140012eea  mov     [rbp+57h+var_60], 120010h
0x140012ef2  mov     r14, rcx
0x140012ef5  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140012ef9  mov     edx, 20019h; DesiredAccess
0x140012efe  mov     [rbp+57h+var_50], 4E004Ch
0x140012f06  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140012f0a  mov     [rbp+57h+KeyHandle], 0
0x140012f12  mov     [rbp+57h+Handle], 0
0x140012f1a  mov     [rbp+57h+var_B0], 0
0x140012f22  movups  [rbp+57h+KeyValueInformation], xmm0
0x140012f26  mov     [rbp+57h+var_B8], 0
0x140012f2d  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140012f35  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140012f3a  call    cs:__imp_ZwOpenKey
0x140012f41  nop     dword ptr [rax+rax+00h]
0x140012f46  mov     ebx, eax
0x140012f48  test    eax, eax
0x140012f4a  js      loc_140013039
0x140012f50  mov     rax, [rbp+57h+KeyHandle]
0x140012f54  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140012f58  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x140012f5c  lea     rcx, [rbp+57h+Handle]; KeyHandle
0x140012f60  lea     rax, [rbp+57h+var_60]
0x140012f64  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140012f6b  xorps   xmm0, xmm0
0x140012f6e  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140012f72  mov     edx, 20019h; DesiredAccess
0x140012f77  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140012f7e  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140012f83  call    cs:__imp_ZwOpenKey
0x140012f8a  nop     dword ptr [rax+rax+00h]
0x140012f8f  mov     ebx, eax
0x140012f91  test    eax, eax
0x140012f93  js      loc_140013039
0x140012f99  mov     rax, [rbp+57h+KeyHandle]
0x140012f9d  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140012fa1  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x140012fa5  lea     rcx, [rbp+57h+var_B0]; KeyHandle
0x140012fa9  lea     rax, [rbp+57h+var_50]
0x140012fad  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140012fb4  xorps   xmm0, xmm0
0x140012fb7  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140012fbb  mov     edx, 20019h; DesiredAccess
0x140012fc0  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140012fc7  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140012fcc  call    cs:__imp_ZwOpenKey
0x140012fd3  nop     dword ptr [rax+rax+00h]
0x140012fd8  mov     ebx, eax
0x140012fda  cmp     eax, 0C0000034h
0x140012fdf  jnz     short loc_140012FE5
0x140012fe1  xor     ebx, ebx
0x140012fe3  jmp     short loc_140013039
0x140012fe5  test    eax, eax
0x140012fe7  js      short loc_140013039
0x140012fe9  mov     rcx, [rbp+57h+var_B0]; KeyHandle
0x140012fed  lea     rax, [rbp+57h+var_B8]
0x140012ff1  mov     [rsp+0F0h+ResultLength], rax; ResultLength
0x140012ff6  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x140012ffa  mov     r8d, 2; KeyValueInformationClass
0x140013000  mov     [rsp+0F0h+Length], 10h; Length
0x140013008  mov     rdx, r14; ValueName
0x14001300b  call    cs:__imp_ZwQueryValueKey
0x140013012  nop     dword ptr [rax+rax+00h]
0x140013017  mov     ebx, eax
0x140013019  cmp     eax, 0C0000034h
0x14001301e  jz      short loc_140012FE1
0x140013020  test    eax, eax
0x140013022  js      short loc_140013039
0x140013024  cmp     dword ptr [rbp+57h+KeyValueInformation+4], 4
0x140013028  jz      short loc_140013031
0x14001302a  mov     ebx, 0C0000024h
0x14001302f  jmp     short loc_140013039
0x140013031  mov     eax, dword ptr [rbp+57h+KeyValueInformation+0Ch]
0x140013034  mov     byte ptr [rdi], 1
0x140013037  mov     [rsi], eax
0x140013039  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x14001303d  test    rcx, rcx
0x140013040  jz      short loc_14001304E
0x140013042  call    cs:__imp_ZwClose
0x140013049  nop     dword ptr [rax+rax+00h]
0x14001304e  mov     rcx, [rbp+57h+Handle]; Handle
0x140013052  test    rcx, rcx
0x140013055  jz      short loc_140013063
0x140013057  call    cs:__imp_ZwClose
0x14001305e  nop     dword ptr [rax+rax+00h]
0x140013063  mov     rcx, [rbp+57h+var_B0]; Handle
0x140013067  test    rcx, rcx
0x14001306a  jz      short loc_140013078
0x14001306c  call    cs:__imp_ZwClose
0x140013073  nop     dword ptr [rax+rax+00h]
0x140013078  mov     eax, ebx
0x14001307a  mov     rcx, [rbp+57h+var_30]
0x14001307e  xor     rcx, rsp; StackCookie
0x140013081  call    __security_check_cookie
0x140013086  add     rsp, 0D0h
0x14001308d  pop     r14
0x14001308f  pop     rdi
0x140013090  pop     rsi
0x140013091  pop     rbx
0x140013092  pop     rbp
0x140013093  retn
```
