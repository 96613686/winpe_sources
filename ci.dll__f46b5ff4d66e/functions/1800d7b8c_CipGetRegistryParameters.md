# CipGetRegistryParameters

- ea: `0x1800d7b8c`
- end: `0x1800d7ddc`
- name: `CipGetRegistryParameters`
- size: `592`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18005e61c`
- `0x18005f308`
- `0x1800d7b00`

## callees

- `0x18002bef0`
- `0x18005f17c`
- `0x1800d7b8c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1800d7cc0`
- `ntoskrnl!ExAllocatePool2` at `0x1800d7cc0`
- `ntoskrnl!ZwQueryValueKey` at `0x1800d7c65`
- `ntoskrnl!ZwQueryValueKey` at `0x1800d7cfa`
- `ntoskrnl!ZwQueryValueKey` at `0x1800d7c65`
- `ntoskrnl!ZwQueryValueKey` at `0x1800d7cfa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800d7ca4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800d7d91`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800d7ca4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800d7d91`
- `ntoskrnl!ZwClose` at `0x1800d7da6`
- `ntoskrnl!ZwClose` at `0x1800d7da6`
- `ntoskrnl!ZwOpenKey` at `0x1800d7bfa`
- `ntoskrnl!ZwOpenKey` at `0x1800d7bfa`

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
0x1800d7b8c  mov     [rsp-8+arg_10], rbx
0x1800d7b91  push    rbp
0x1800d7b92  push    rsi
0x1800d7b93  push    rdi
0x1800d7b94  push    r12
0x1800d7b96  push    r13
0x1800d7b98  push    r14
0x1800d7b9a  push    r15
0x1800d7b9c  lea     rbp, [rsp-1Fh]
0x1800d7ba1  sub     rsp, 0A0h
0x1800d7ba8  mov     rax, cs:__security_cookie
0x1800d7baf  xor     rax, rsp
0x1800d7bb2  mov     [rbp+4Fh+var_38], rax
0x1800d7bb6  mov     rsi, rdx
0x1800d7bb9  mov     [rbp+4Fh+var_88], rdx
0x1800d7bbd  xor     edx, edx
0x1800d7bbf  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rcx
0x1800d7bc3  mov     [rbp+4Fh+KeyHandle], rdx
0x1800d7bc7  lea     rcx, [rbp+4Fh+KeyHandle]; KeyHandle
0x1800d7bcb  mov     [rbp+4Fh+var_A0], edx
0x1800d7bce  mov     r13d, r8d
0x1800d7bd1  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], rdx
0x1800d7bd5  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x1800d7bd9  xorps   xmm0, xmm0
0x1800d7bdc  mov     [rbp+4Fh+var_90], r9
0x1800d7be0  mov     edx, 20019h; DesiredAccess
0x1800d7be5  mov     qword ptr [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x1800d7bed  mov     qword ptr [rbp+4Fh+ObjectAttributes.Attributes], 240h
0x1800d7bf5  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x1800d7bfa  call    cs:__imp_ZwOpenKey
0x1800d7c01  nop     dword ptr [rax+rax+00h]
0x1800d7c06  mov     ebx, eax
0x1800d7c08  test    eax, eax
0x1800d7c0a  jns     short loc_1800D7C25
0x1800d7c0c  cmp     eax, 0C0000034h
0x1800d7c11  jz      short loc_1800D7C1E
0x1800d7c13  cmp     eax, 0C000003Ah
0x1800d7c18  jnz     loc_1800D7D9D
0x1800d7c1e  xor     ebx, ebx
0x1800d7c20  jmp     loc_1800D7D9D
0x1800d7c25  mov     r12d, [rbp+4Fh+arg_20]
0x1800d7c29  lea     rdi, [rbp+4Fh+KeyValueInformation]
0x1800d7c2d  mov     r15d, 14h
0x1800d7c33  xor     r14d, r14d
0x1800d7c36  cmp     r14d, r13d
0x1800d7c39  jnb     loc_1800D7D79
0x1800d7c3f  lea     rcx, [r14+r14*4]
0x1800d7c43  mov     r9, rdi; KeyValueInformation
0x1800d7c46  lea     rsi, [rsi+rcx*8]
0x1800d7c4a  mov     r8d, 2; KeyValueInformationClass
0x1800d7c50  mov     rcx, [rbp+4Fh+KeyHandle]; KeyHandle
0x1800d7c54  lea     rax, [rbp+4Fh+var_A0]
0x1800d7c58  mov     [rsp+0D0h+ResultLength], rax; ResultLength
0x1800d7c5d  mov     rdx, rsi; ValueName
0x1800d7c60  mov     [rsp+0D0h+Length], r15d; Length
0x1800d7c65  call    cs:__imp_ZwQueryValueKey
0x1800d7c6c  nop     dword ptr [rax+rax+00h]
0x1800d7c71  mov     ebx, eax
0x1800d7c73  cmp     eax, 0C0000023h
0x1800d7c78  jz      short loc_1800D7C85
0x1800d7c7a  cmp     eax, 80000005h
0x1800d7c7f  jnz     loc_1800D7D08
0x1800d7c85  mov     eax, [rbp+4Fh+var_A0]
0x1800d7c88  cmp     eax, 40000h
0x1800d7c8d  ja      loc_1800D7D66
0x1800d7c93  lea     rcx, [rbp+4Fh+KeyValueInformation]
0x1800d7c97  cmp     rdi, rcx
0x1800d7c9a  jz      short loc_1800D7CB3
0x1800d7c9c  mov     edx, 63734943h; Tag
0x1800d7ca1  mov     rcx, rdi; P
0x1800d7ca4  call    cs:__imp_ExFreePoolWithTag
0x1800d7cab  nop     dword ptr [rax+rax+00h]
0x1800d7cb0  mov     eax, [rbp+4Fh+var_A0]
0x1800d7cb3  mov     edx, eax
0x1800d7cb5  mov     ecx, 102h
0x1800d7cba  mov     r8d, 63734943h
0x1800d7cc0  call    cs:__imp_ExAllocatePool2
0x1800d7cc7  nop     dword ptr [rax+rax+00h]
0x1800d7ccc  mov     rdi, rax
0x1800d7ccf  test    rax, rax
0x1800d7cd2  jz      loc_1800D7D72
0x1800d7cd8  mov     r15d, [rbp+4Fh+var_A0]
0x1800d7cdc  lea     rax, [rbp+4Fh+var_A0]
0x1800d7ce0  mov     rcx, [rbp+4Fh+KeyHandle]; KeyHandle
0x1800d7ce4  mov     r9, rdi; KeyValueInformation
0x1800d7ce7  mov     [rsp+0D0h+ResultLength], rax; ResultLength
0x1800d7cec  mov     r8d, 2; KeyValueInformationClass
0x1800d7cf2  mov     rdx, rsi; ValueName
0x1800d7cf5  mov     [rsp+0D0h+Length], r15d; Length
0x1800d7cfa  call    cs:__imp_ZwQueryValueKey
0x1800d7d01  nop     dword ptr [rax+rax+00h]
0x1800d7d06  mov     ebx, eax
0x1800d7d08  test    ebx, ebx
0x1800d7d0a  jns     short loc_1800D7D16
0x1800d7d0c  cmp     ebx, 0C0000034h
0x1800d7d12  jz      short loc_1800D7D66
0x1800d7d14  jmp     short loc_1800D7D7B
0x1800d7d16  mov     eax, [rdi+4]
0x1800d7d19  cmp     eax, [rsi+10h]
0x1800d7d1c  jnz     short loc_1800D7D66
0x1800d7d1e  cmp     eax, 4
0x1800d7d21  jnz     short loc_1800D7D37
0x1800d7d23  cmp     [rdi+8], eax
0x1800d7d26  jnz     short loc_1800D7D66
0x1800d7d28  mov     eax, [rdi+0Ch]
0x1800d7d2b  mov     [rsi+18h], eax
0x1800d7d2e  mov     dword ptr [rsi+14h], 1
0x1800d7d35  jmp     short loc_1800D7D66
0x1800d7d37  cmp     eax, 7
0x1800d7d3a  jnz     short loc_1800D7D66
0x1800d7d3c  mov     rax, [rbp+4Fh+var_90]
0x1800d7d40  lea     r9, [rsi+20h]
0x1800d7d44  mov     edx, [rdi+8]
0x1800d7d47  lea     r8, [rsi+18h]
0x1800d7d4b  lea     rcx, [rdi+0Ch]
0x1800d7d4f  mov     dword ptr [rsp+0D0h+ResultLength], r12d
0x1800d7d54  mov     qword ptr [rsp+0D0h+Length], rax
0x1800d7d59  call    CipRegMultiSzToUnicodeStrings
0x1800d7d5e  not     eax
0x1800d7d60  shr     eax, 1Fh
0x1800d7d63  mov     [rsi+14h], eax
0x1800d7d66  mov     rsi, [rbp+4Fh+var_88]
0x1800d7d6a  inc     r14d
0x1800d7d6d  jmp     loc_1800D7C36
0x1800d7d72  mov     ebx, 0C0000017h
0x1800d7d77  jmp     short loc_1800D7D9D
0x1800d7d79  xor     ebx, ebx
0x1800d7d7b  test    rdi, rdi
0x1800d7d7e  jz      short loc_1800D7D9D
0x1800d7d80  lea     rax, [rbp+4Fh+KeyValueInformation]
0x1800d7d84  cmp     rdi, rax
0x1800d7d87  jz      short loc_1800D7D9D
0x1800d7d89  mov     edx, 63734943h; Tag
0x1800d7d8e  mov     rcx, rdi; P
0x1800d7d91  call    cs:__imp_ExFreePoolWithTag
0x1800d7d98  nop     dword ptr [rax+rax+00h]
0x1800d7d9d  mov     rcx, [rbp+4Fh+KeyHandle]; Handle
0x1800d7da1  test    rcx, rcx
0x1800d7da4  jz      short loc_1800D7DB2
0x1800d7da6  call    cs:__imp_ZwClose
0x1800d7dad  nop     dword ptr [rax+rax+00h]
0x1800d7db2  mov     eax, ebx
0x1800d7db4  mov     rcx, [rbp+4Fh+var_38]
0x1800d7db8  xor     rcx, rsp; StackCookie
0x1800d7dbb  call    __security_check_cookie
0x1800d7dc0  mov     rbx, [rsp+0D0h+arg_10]
0x1800d7dc8  add     rsp, 0A0h
0x1800d7dcf  pop     r15
0x1800d7dd1  pop     r14
0x1800d7dd3  pop     r13
0x1800d7dd5  pop     r12
0x1800d7dd7  pop     rdi
0x1800d7dd8  pop     rsi
0x1800d7dd9  pop     rbp
0x1800d7dda  retn
```
