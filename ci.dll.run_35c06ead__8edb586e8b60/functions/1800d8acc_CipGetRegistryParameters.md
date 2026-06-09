# CipGetRegistryParameters

- ea: `0x1800d8acc`
- end: `0x1800d8d1c`
- name: `CipGetRegistryParameters`
- size: `592`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18005ed08`
- `0x18005f9f8`
- `0x1800d8a40`

## callees

- `0x18002c0d0`
- `0x18005f86c`
- `0x1800d8acc`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1800d8c00`
- `ntoskrnl!ExAllocatePool2` at `0x1800d8c00`
- `ntoskrnl!ZwQueryValueKey` at `0x1800d8ba5`
- `ntoskrnl!ZwQueryValueKey` at `0x1800d8c3a`
- `ntoskrnl!ZwQueryValueKey` at `0x1800d8ba5`
- `ntoskrnl!ZwQueryValueKey` at `0x1800d8c3a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800d8be4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800d8cd1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800d8be4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800d8cd1`
- `ntoskrnl!ZwClose` at `0x1800d8ce6`
- `ntoskrnl!ZwClose` at `0x1800d8ce6`
- `ntoskrnl!ZwOpenKey` at `0x1800d8b3a`
- `ntoskrnl!ZwOpenKey` at `0x1800d8b3a`

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
0x1800d8acc  mov     [rsp-8+arg_10], rbx
0x1800d8ad1  push    rbp
0x1800d8ad2  push    rsi
0x1800d8ad3  push    rdi
0x1800d8ad4  push    r12
0x1800d8ad6  push    r13
0x1800d8ad8  push    r14
0x1800d8ada  push    r15
0x1800d8adc  lea     rbp, [rsp-1Fh]
0x1800d8ae1  sub     rsp, 0A0h
0x1800d8ae8  mov     rax, cs:__security_cookie
0x1800d8aef  xor     rax, rsp
0x1800d8af2  mov     [rbp+4Fh+var_38], rax
0x1800d8af6  mov     rsi, rdx
0x1800d8af9  mov     [rbp+4Fh+var_88], rdx
0x1800d8afd  xor     edx, edx
0x1800d8aff  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rcx
0x1800d8b03  mov     [rbp+4Fh+KeyHandle], rdx
0x1800d8b07  lea     rcx, [rbp+4Fh+KeyHandle]; KeyHandle
0x1800d8b0b  mov     [rbp+4Fh+var_A0], edx
0x1800d8b0e  mov     r13d, r8d
0x1800d8b11  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], rdx
0x1800d8b15  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x1800d8b19  xorps   xmm0, xmm0
0x1800d8b1c  mov     [rbp+4Fh+var_90], r9
0x1800d8b20  mov     edx, 20019h; DesiredAccess
0x1800d8b25  mov     qword ptr [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x1800d8b2d  mov     qword ptr [rbp+4Fh+ObjectAttributes.Attributes], 240h
0x1800d8b35  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x1800d8b3a  call    cs:__imp_ZwOpenKey
0x1800d8b41  nop     dword ptr [rax+rax+00h]
0x1800d8b46  mov     ebx, eax
0x1800d8b48  test    eax, eax
0x1800d8b4a  jns     short loc_1800D8B65
0x1800d8b4c  cmp     eax, 0C0000034h
0x1800d8b51  jz      short loc_1800D8B5E
0x1800d8b53  cmp     eax, 0C000003Ah
0x1800d8b58  jnz     loc_1800D8CDD
0x1800d8b5e  xor     ebx, ebx
0x1800d8b60  jmp     loc_1800D8CDD
0x1800d8b65  mov     r12d, [rbp+4Fh+arg_20]
0x1800d8b69  lea     rdi, [rbp+4Fh+KeyValueInformation]
0x1800d8b6d  mov     r15d, 14h
0x1800d8b73  xor     r14d, r14d
0x1800d8b76  cmp     r14d, r13d
0x1800d8b79  jnb     loc_1800D8CB9
0x1800d8b7f  lea     rcx, [r14+r14*4]
0x1800d8b83  mov     r9, rdi; KeyValueInformation
0x1800d8b86  lea     rsi, [rsi+rcx*8]
0x1800d8b8a  mov     r8d, 2; KeyValueInformationClass
0x1800d8b90  mov     rcx, [rbp+4Fh+KeyHandle]; KeyHandle
0x1800d8b94  lea     rax, [rbp+4Fh+var_A0]
0x1800d8b98  mov     [rsp+0D0h+ResultLength], rax; ResultLength
0x1800d8b9d  mov     rdx, rsi; ValueName
0x1800d8ba0  mov     [rsp+0D0h+Length], r15d; Length
0x1800d8ba5  call    cs:__imp_ZwQueryValueKey
0x1800d8bac  nop     dword ptr [rax+rax+00h]
0x1800d8bb1  mov     ebx, eax
0x1800d8bb3  cmp     eax, 0C0000023h
0x1800d8bb8  jz      short loc_1800D8BC5
0x1800d8bba  cmp     eax, 80000005h
0x1800d8bbf  jnz     loc_1800D8C48
0x1800d8bc5  mov     eax, [rbp+4Fh+var_A0]
0x1800d8bc8  cmp     eax, 40000h
0x1800d8bcd  ja      loc_1800D8CA6
0x1800d8bd3  lea     rcx, [rbp+4Fh+KeyValueInformation]
0x1800d8bd7  cmp     rdi, rcx
0x1800d8bda  jz      short loc_1800D8BF3
0x1800d8bdc  mov     edx, 63734943h; Tag
0x1800d8be1  mov     rcx, rdi; P
0x1800d8be4  call    cs:__imp_ExFreePoolWithTag
0x1800d8beb  nop     dword ptr [rax+rax+00h]
0x1800d8bf0  mov     eax, [rbp+4Fh+var_A0]
0x1800d8bf3  mov     edx, eax
0x1800d8bf5  mov     ecx, 102h
0x1800d8bfa  mov     r8d, 63734943h
0x1800d8c00  call    cs:__imp_ExAllocatePool2
0x1800d8c07  nop     dword ptr [rax+rax+00h]
0x1800d8c0c  mov     rdi, rax
0x1800d8c0f  test    rax, rax
0x1800d8c12  jz      loc_1800D8CB2
0x1800d8c18  mov     r15d, [rbp+4Fh+var_A0]
0x1800d8c1c  lea     rax, [rbp+4Fh+var_A0]
0x1800d8c20  mov     rcx, [rbp+4Fh+KeyHandle]; KeyHandle
0x1800d8c24  mov     r9, rdi; KeyValueInformation
0x1800d8c27  mov     [rsp+0D0h+ResultLength], rax; ResultLength
0x1800d8c2c  mov     r8d, 2; KeyValueInformationClass
0x1800d8c32  mov     rdx, rsi; ValueName
0x1800d8c35  mov     [rsp+0D0h+Length], r15d; Length
0x1800d8c3a  call    cs:__imp_ZwQueryValueKey
0x1800d8c41  nop     dword ptr [rax+rax+00h]
0x1800d8c46  mov     ebx, eax
0x1800d8c48  test    ebx, ebx
0x1800d8c4a  jns     short loc_1800D8C56
0x1800d8c4c  cmp     ebx, 0C0000034h
0x1800d8c52  jz      short loc_1800D8CA6
0x1800d8c54  jmp     short loc_1800D8CBB
0x1800d8c56  mov     eax, [rdi+4]
0x1800d8c59  cmp     eax, [rsi+10h]
0x1800d8c5c  jnz     short loc_1800D8CA6
0x1800d8c5e  cmp     eax, 4
0x1800d8c61  jnz     short loc_1800D8C77
0x1800d8c63  cmp     [rdi+8], eax
0x1800d8c66  jnz     short loc_1800D8CA6
0x1800d8c68  mov     eax, [rdi+0Ch]
0x1800d8c6b  mov     [rsi+18h], eax
0x1800d8c6e  mov     dword ptr [rsi+14h], 1
0x1800d8c75  jmp     short loc_1800D8CA6
0x1800d8c77  cmp     eax, 7
0x1800d8c7a  jnz     short loc_1800D8CA6
0x1800d8c7c  mov     rax, [rbp+4Fh+var_90]
0x1800d8c80  lea     r9, [rsi+20h]
0x1800d8c84  mov     edx, [rdi+8]
0x1800d8c87  lea     r8, [rsi+18h]
0x1800d8c8b  lea     rcx, [rdi+0Ch]
0x1800d8c8f  mov     dword ptr [rsp+0D0h+ResultLength], r12d
0x1800d8c94  mov     qword ptr [rsp+0D0h+Length], rax
0x1800d8c99  call    CipRegMultiSzToUnicodeStrings
0x1800d8c9e  not     eax
0x1800d8ca0  shr     eax, 1Fh
0x1800d8ca3  mov     [rsi+14h], eax
0x1800d8ca6  mov     rsi, [rbp+4Fh+var_88]
0x1800d8caa  inc     r14d
0x1800d8cad  jmp     loc_1800D8B76
0x1800d8cb2  mov     ebx, 0C0000017h
0x1800d8cb7  jmp     short loc_1800D8CDD
0x1800d8cb9  xor     ebx, ebx
0x1800d8cbb  test    rdi, rdi
0x1800d8cbe  jz      short loc_1800D8CDD
0x1800d8cc0  lea     rax, [rbp+4Fh+KeyValueInformation]
0x1800d8cc4  cmp     rdi, rax
0x1800d8cc7  jz      short loc_1800D8CDD
0x1800d8cc9  mov     edx, 63734943h; Tag
0x1800d8cce  mov     rcx, rdi; P
0x1800d8cd1  call    cs:__imp_ExFreePoolWithTag
0x1800d8cd8  nop     dword ptr [rax+rax+00h]
0x1800d8cdd  mov     rcx, [rbp+4Fh+KeyHandle]; Handle
0x1800d8ce1  test    rcx, rcx
0x1800d8ce4  jz      short loc_1800D8CF2
0x1800d8ce6  call    cs:__imp_ZwClose
0x1800d8ced  nop     dword ptr [rax+rax+00h]
0x1800d8cf2  mov     eax, ebx
0x1800d8cf4  mov     rcx, [rbp+4Fh+var_38]
0x1800d8cf8  xor     rcx, rsp; StackCookie
0x1800d8cfb  call    __security_check_cookie
0x1800d8d00  mov     rbx, [rsp+0D0h+arg_10]
0x1800d8d08  add     rsp, 0A0h
0x1800d8d0f  pop     r15
0x1800d8d11  pop     r14
0x1800d8d13  pop     r13
0x1800d8d15  pop     r12
0x1800d8d17  pop     rdi
0x1800d8d18  pop     rsi
0x1800d8d19  pop     rbp
0x1800d8d1a  retn
```
