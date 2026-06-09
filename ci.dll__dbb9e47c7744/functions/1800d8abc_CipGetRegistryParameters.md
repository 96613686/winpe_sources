# CipGetRegistryParameters

- ea: `0x1800d8abc`
- end: `0x1800d8d0c`
- name: `CipGetRegistryParameters`
- size: `592`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18005ed68`
- `0x18005fa58`
- `0x1800d8a30`

## callees

- `0x18002bf20`
- `0x18005f8cc`
- `0x1800d8abc`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1800d8bf0`
- `ntoskrnl!ExAllocatePool2` at `0x1800d8bf0`
- `ntoskrnl!ZwQueryValueKey` at `0x1800d8b95`
- `ntoskrnl!ZwQueryValueKey` at `0x1800d8c2a`
- `ntoskrnl!ZwQueryValueKey` at `0x1800d8b95`
- `ntoskrnl!ZwQueryValueKey` at `0x1800d8c2a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800d8bd4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800d8cc1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800d8bd4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800d8cc1`
- `ntoskrnl!ZwClose` at `0x1800d8cd6`
- `ntoskrnl!ZwClose` at `0x1800d8cd6`
- `ntoskrnl!ZwOpenKey` at `0x1800d8b2a`
- `ntoskrnl!ZwOpenKey` at `0x1800d8b2a`

## pseudocode

```c
__int64 __fastcall CipGetRegistryParameters(
        struct _UNICODE_STRING *a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        int a5)
{
  __int64 v5; // rsi
  NTSTATUS v7; // eax
  NTSTATUS v8; // ebx
  _DWORD *Pool2; // rdi
  ULONG Length; // r15d
  __int64 i; // r14
  __int64 v12; // rsi
  NTSTATUS v13; // eax
  ULONG v14; // eax
  int v15; // eax
  ULONG ResultLength; // [rsp+30h] [rbp-51h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-49h] BYREF
  __int64 v19; // [rsp+40h] [rbp-41h]
  __int64 v20; // [rsp+48h] [rbp-39h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-31h] BYREF
  _BYTE KeyValueInformation[24]; // [rsp+80h] [rbp-1h] BYREF

  v5 = a2;
  v20 = a2;
  ObjectAttributes.ObjectName = a1;
  KeyHandle = 0;
  ResultLength = 0;
  ObjectAttributes.RootDirectory = 0;
  v19 = a4;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v7 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  v8 = v7;
  if ( v7 < 0 )
  {
    if ( v7 == -1073741772 || v7 == -1073741766 )
      v8 = 0;
    goto LABEL_29;
  }
  Pool2 = KeyValueInformation;
  Length = 20;
  for ( i = 0; (unsigned int)i < a3; i = (unsigned int)(i + 1) )
  {
    v12 = v5 + 40 * i;
    v13 = ZwQueryValueKey(KeyHandle, (PUNICODE_STRING)v12, KeyValuePartialInformation, Pool2, Length, &ResultLength);
    v8 = v13;
    if ( v13 == -1073741789 || v13 == -2147483643 )
    {
      v14 = ResultLength;
      if ( ResultLength > 0x40000 )
        goto LABEL_23;
      if ( Pool2 != (_DWORD *)KeyValueInformation )
      {
        ExFreePoolWithTag(Pool2, 0x63734943u);
        v14 = ResultLength;
      }
      Pool2 = (_DWORD *)ExAllocatePool2(258, v14, 1668499779);
      if ( !Pool2 )
      {
        v8 = -1073741801;
        goto LABEL_29;
      }
      Length = ResultLength;
      v8 = ZwQueryValueKey(
             KeyHandle,
             (PUNICODE_STRING)v12,
             KeyValuePartialInformation,
             Pool2,
             ResultLength,
             &ResultLength);
    }
    if ( v8 >= 0 )
    {
      v15 = Pool2[1];
      if ( v15 == *(_DWORD *)(v12 + 16) )
      {
        if ( v15 == 4 )
        {
          if ( Pool2[2] == 4 )
          {
            *(_DWORD *)(v12 + 24) = Pool2[3];
            *(_DWORD *)(v12 + 20) = 1;
          }
        }
        else if ( v15 == 7 )
        {
          *(_DWORD *)(v12 + 20) = (int)CipRegMultiSzToUnicodeStrings(
                                         (int)Pool2 + 12,
                                         Pool2[2],
                                         (int)v12 + 24,
                                         (int)v12 + 32,
                                         v19,
                                         a5) >= 0;
        }
      }
    }
    else if ( v8 != -1073741772 )
    {
      goto LABEL_26;
    }
LABEL_23:
    v5 = v20;
  }
  v8 = 0;
LABEL_26:
  if ( Pool2 && Pool2 != (_DWORD *)KeyValueInformation )
    ExFreePoolWithTag(Pool2, 0x63734943u);
LABEL_29:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800d8abc  mov     [rsp-8+arg_10], rbx
0x1800d8ac1  push    rbp
0x1800d8ac2  push    rsi
0x1800d8ac3  push    rdi
0x1800d8ac4  push    r12
0x1800d8ac6  push    r13
0x1800d8ac8  push    r14
0x1800d8aca  push    r15
0x1800d8acc  lea     rbp, [rsp-1Fh]
0x1800d8ad1  sub     rsp, 0A0h
0x1800d8ad8  mov     rax, cs:__security_cookie
0x1800d8adf  xor     rax, rsp
0x1800d8ae2  mov     [rbp+4Fh+var_38], rax
0x1800d8ae6  mov     rsi, rdx
0x1800d8ae9  mov     [rbp+4Fh+var_88], rdx
0x1800d8aed  xor     edx, edx
0x1800d8aef  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rcx
0x1800d8af3  mov     [rbp+4Fh+KeyHandle], rdx
0x1800d8af7  lea     rcx, [rbp+4Fh+KeyHandle]; KeyHandle
0x1800d8afb  mov     [rbp+4Fh+var_A0], edx
0x1800d8afe  mov     r13d, r8d
0x1800d8b01  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], rdx
0x1800d8b05  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x1800d8b09  xorps   xmm0, xmm0
0x1800d8b0c  mov     [rbp+4Fh+var_90], r9
0x1800d8b10  mov     edx, 20019h; DesiredAccess
0x1800d8b15  mov     qword ptr [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x1800d8b1d  mov     qword ptr [rbp+4Fh+ObjectAttributes.Attributes], 240h
0x1800d8b25  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x1800d8b2a  call    cs:__imp_ZwOpenKey
0x1800d8b31  nop     dword ptr [rax+rax+00h]
0x1800d8b36  mov     ebx, eax
0x1800d8b38  test    eax, eax
0x1800d8b3a  jns     short loc_1800D8B55
0x1800d8b3c  cmp     eax, 0C0000034h
0x1800d8b41  jz      short loc_1800D8B4E
0x1800d8b43  cmp     eax, 0C000003Ah
0x1800d8b48  jnz     loc_1800D8CCD
0x1800d8b4e  xor     ebx, ebx
0x1800d8b50  jmp     loc_1800D8CCD
0x1800d8b55  mov     r12d, [rbp+4Fh+arg_20]
0x1800d8b59  lea     rdi, [rbp+4Fh+KeyValueInformation]
0x1800d8b5d  mov     r15d, 14h
0x1800d8b63  xor     r14d, r14d
0x1800d8b66  cmp     r14d, r13d
0x1800d8b69  jnb     loc_1800D8CA9
0x1800d8b6f  lea     rcx, [r14+r14*4]
0x1800d8b73  mov     r9, rdi; KeyValueInformation
0x1800d8b76  lea     rsi, [rsi+rcx*8]
0x1800d8b7a  mov     r8d, 2; KeyValueInformationClass
0x1800d8b80  mov     rcx, [rbp+4Fh+KeyHandle]; KeyHandle
0x1800d8b84  lea     rax, [rbp+4Fh+var_A0]
0x1800d8b88  mov     [rsp+0D0h+ResultLength], rax; ResultLength
0x1800d8b8d  mov     rdx, rsi; ValueName
0x1800d8b90  mov     [rsp+0D0h+Length], r15d; Length
0x1800d8b95  call    cs:__imp_ZwQueryValueKey
0x1800d8b9c  nop     dword ptr [rax+rax+00h]
0x1800d8ba1  mov     ebx, eax
0x1800d8ba3  cmp     eax, 0C0000023h
0x1800d8ba8  jz      short loc_1800D8BB5
0x1800d8baa  cmp     eax, 80000005h
0x1800d8baf  jnz     loc_1800D8C38
0x1800d8bb5  mov     eax, [rbp+4Fh+var_A0]
0x1800d8bb8  cmp     eax, 40000h
0x1800d8bbd  ja      loc_1800D8C96
0x1800d8bc3  lea     rcx, [rbp+4Fh+KeyValueInformation]
0x1800d8bc7  cmp     rdi, rcx
0x1800d8bca  jz      short loc_1800D8BE3
0x1800d8bcc  mov     edx, 63734943h; Tag
0x1800d8bd1  mov     rcx, rdi; P
0x1800d8bd4  call    cs:__imp_ExFreePoolWithTag
0x1800d8bdb  nop     dword ptr [rax+rax+00h]
0x1800d8be0  mov     eax, [rbp+4Fh+var_A0]
0x1800d8be3  mov     edx, eax
0x1800d8be5  mov     ecx, 102h
0x1800d8bea  mov     r8d, 63734943h
0x1800d8bf0  call    cs:__imp_ExAllocatePool2
0x1800d8bf7  nop     dword ptr [rax+rax+00h]
0x1800d8bfc  mov     rdi, rax
0x1800d8bff  test    rax, rax
0x1800d8c02  jz      loc_1800D8CA2
0x1800d8c08  mov     r15d, [rbp+4Fh+var_A0]
0x1800d8c0c  lea     rax, [rbp+4Fh+var_A0]
0x1800d8c10  mov     rcx, [rbp+4Fh+KeyHandle]; KeyHandle
0x1800d8c14  mov     r9, rdi; KeyValueInformation
0x1800d8c17  mov     [rsp+0D0h+ResultLength], rax; ResultLength
0x1800d8c1c  mov     r8d, 2; KeyValueInformationClass
0x1800d8c22  mov     rdx, rsi; ValueName
0x1800d8c25  mov     [rsp+0D0h+Length], r15d; Length
0x1800d8c2a  call    cs:__imp_ZwQueryValueKey
0x1800d8c31  nop     dword ptr [rax+rax+00h]
0x1800d8c36  mov     ebx, eax
0x1800d8c38  test    ebx, ebx
0x1800d8c3a  jns     short loc_1800D8C46
0x1800d8c3c  cmp     ebx, 0C0000034h
0x1800d8c42  jz      short loc_1800D8C96
0x1800d8c44  jmp     short loc_1800D8CAB
0x1800d8c46  mov     eax, [rdi+4]
0x1800d8c49  cmp     eax, [rsi+10h]
0x1800d8c4c  jnz     short loc_1800D8C96
0x1800d8c4e  cmp     eax, 4
0x1800d8c51  jnz     short loc_1800D8C67
0x1800d8c53  cmp     [rdi+8], eax
0x1800d8c56  jnz     short loc_1800D8C96
0x1800d8c58  mov     eax, [rdi+0Ch]
0x1800d8c5b  mov     [rsi+18h], eax
0x1800d8c5e  mov     dword ptr [rsi+14h], 1
0x1800d8c65  jmp     short loc_1800D8C96
0x1800d8c67  cmp     eax, 7
0x1800d8c6a  jnz     short loc_1800D8C96
0x1800d8c6c  mov     rax, [rbp+4Fh+var_90]
0x1800d8c70  lea     r9, [rsi+20h]
0x1800d8c74  mov     edx, [rdi+8]
0x1800d8c77  lea     r8, [rsi+18h]
0x1800d8c7b  lea     rcx, [rdi+0Ch]
0x1800d8c7f  mov     dword ptr [rsp+0D0h+ResultLength], r12d
0x1800d8c84  mov     qword ptr [rsp+0D0h+Length], rax
0x1800d8c89  call    CipRegMultiSzToUnicodeStrings
0x1800d8c8e  not     eax
0x1800d8c90  shr     eax, 1Fh
0x1800d8c93  mov     [rsi+14h], eax
0x1800d8c96  mov     rsi, [rbp+4Fh+var_88]
0x1800d8c9a  inc     r14d
0x1800d8c9d  jmp     loc_1800D8B66
0x1800d8ca2  mov     ebx, 0C0000017h
0x1800d8ca7  jmp     short loc_1800D8CCD
0x1800d8ca9  xor     ebx, ebx
0x1800d8cab  test    rdi, rdi
0x1800d8cae  jz      short loc_1800D8CCD
0x1800d8cb0  lea     rax, [rbp+4Fh+KeyValueInformation]
0x1800d8cb4  cmp     rdi, rax
0x1800d8cb7  jz      short loc_1800D8CCD
0x1800d8cb9  mov     edx, 63734943h; Tag
0x1800d8cbe  mov     rcx, rdi; P
0x1800d8cc1  call    cs:__imp_ExFreePoolWithTag
0x1800d8cc8  nop     dword ptr [rax+rax+00h]
0x1800d8ccd  mov     rcx, [rbp+4Fh+KeyHandle]; Handle
0x1800d8cd1  test    rcx, rcx
0x1800d8cd4  jz      short loc_1800D8CE2
0x1800d8cd6  call    cs:__imp_ZwClose
0x1800d8cdd  nop     dword ptr [rax+rax+00h]
0x1800d8ce2  mov     eax, ebx
0x1800d8ce4  mov     rcx, [rbp+4Fh+var_38]
0x1800d8ce8  xor     rcx, rsp; StackCookie
0x1800d8ceb  call    __security_check_cookie
0x1800d8cf0  mov     rbx, [rsp+0D0h+arg_10]
0x1800d8cf8  add     rsp, 0A0h
0x1800d8cff  pop     r15
0x1800d8d01  pop     r14
0x1800d8d03  pop     r13
0x1800d8d05  pop     r12
0x1800d8d07  pop     rdi
0x1800d8d08  pop     rsi
0x1800d8d09  pop     rbp
0x1800d8d0a  retn
```
