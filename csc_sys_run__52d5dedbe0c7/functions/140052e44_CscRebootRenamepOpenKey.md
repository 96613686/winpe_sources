# CscRebootRenamepOpenKey

- ea: `0x140052e44`
- end: `0x140052f6e`
- name: `CscRebootRenamepOpenKey`
- size: `298`
- prototype: `__int64 __fastcall(PHANDLE KeyHandle, struct _UNICODE_STRING *, char, _BYTE *)`
- caller_count: `3`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1400522a4`
- `0x1400526cc`
- `0x1400529f8`

## callees

- `0x140052908`
- `0x140052e44`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140052f4a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052f4a`
- `ntoskrnl!ZwOpenKey` at `0x140052f2f`
- `ntoskrnl!ZwOpenKey` at `0x140052f2f`
- `ntoskrnl!ZwCreateKey` at `0x140052eed`
- `ntoskrnl!ZwCreateKey` at `0x140052eed`

## pseudocode

```c
__int64 __fastcall CscRebootRenamepOpenKey(PHANDLE KeyHandle, struct _UNICODE_STRING *a2, char a3, _BYTE *a4)
{
  PVOID v4; // rdi
  __int64 result; // rax
  unsigned int v9; // esi
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  PVOID P; // [rsp+90h] [rbp+20h] BYREF
  ULONG Disposition; // [rsp+A0h] [rbp+30h] BYREF

  v4 = 0;
  Disposition = 0;
  P = 0;
  *KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( a4 )
    *a4 = 1;
  if ( a3 )
  {
    result = CscRebootRenamepCreateSecurityDescriptor(&P);
    if ( (int)result < 0 )
      return result;
    ObjectAttributes.RootDirectory = 0;
    v4 = P;
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = a2;
    ObjectAttributes.SecurityDescriptor = P;
    ObjectAttributes.SecurityQualityOfService = 0;
    v9 = ZwCreateKey(KeyHandle, 0xF003Fu, &ObjectAttributes, 0, 0, 0, &Disposition);
    if ( Disposition == 1 && a4 )
      *a4 = 0;
  }
  else
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = a2;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v9 = ZwOpenKey(KeyHandle, 0xF003Fu, &ObjectAttributes);
  }
  if ( v4 )
    ExFreePoolWithTag(v4, 0x52727343u);
  return v9;
}

```

## disassembly

```asm
0x140052e44  mov     [rsp-18h+arg_8], rbx
0x140052e49  mov     [rsp-18h+arg_18], rsi
0x140052e4e  push    rbp
0x140052e4f  push    rdi
0x140052e50  push    r14
0x140052e52  mov     rbp, rsp
0x140052e55  sub     rsp, 70h
0x140052e59  xor     eax, eax
0x140052e5b  xorps   xmm0, xmm0
0x140052e5e  xor     edi, edi
0x140052e60  mov     [rbp+arg_10], eax
0x140052e63  mov     [rbp+P], rdi
0x140052e67  mov     rbx, r9
0x140052e6a  mov     [rcx], rax
0x140052e6d  mov     r14, rdx
0x140052e70  mov     rsi, rcx
0x140052e73  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140052e77  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x140052e7b  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140052e7f  test    r9, r9
0x140052e82  jz      short loc_140052E88
0x140052e84  mov     byte ptr [r9], 1
0x140052e88  test    r8b, r8b
0x140052e8b  jz      short loc_140052F0B
0x140052e8d  lea     rcx, [rbp+P]
0x140052e91  call    CscRebootRenamepCreateSecurityDescriptor
0x140052e96  test    eax, eax
0x140052e98  js      loc_140052F58
0x140052e9e  lea     rax, [rbp+arg_10]
0x140052ea2  mov     [rbp+ObjectAttributes.RootDirectory], rdi
0x140052ea6  mov     rdi, [rbp+P]
0x140052eaa  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140052eae  mov     [rsp+70h+Disposition], rax; Disposition
0x140052eb3  xor     r9d, r9d; TitleIndex
0x140052eb6  mov     [rsp+70h+CreateOptions], 0; CreateOptions
0x140052ebe  mov     edx, 0F003Fh; DesiredAccess
0x140052ec3  mov     rcx, rsi; KeyHandle
0x140052ec6  mov     [rsp+70h+Class], 0; Class
0x140052ecf  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140052ed6  mov     [rbp+ObjectAttributes.Attributes], 240h
0x140052edd  mov     [rbp+ObjectAttributes.ObjectName], r14
0x140052ee1  mov     [rbp+ObjectAttributes.SecurityDescriptor], rdi
0x140052ee5  mov     [rbp+ObjectAttributes.SecurityQualityOfService], 0
0x140052eed  call    cs:__imp_ZwCreateKey
0x140052ef4  nop     dword ptr [rax+rax+00h]
0x140052ef9  cmp     [rbp+arg_10], 1
0x140052efd  mov     esi, eax
0x140052eff  jnz     short loc_140052F3D
0x140052f01  test    rbx, rbx
0x140052f04  jz      short loc_140052F3D
0x140052f06  mov     byte ptr [rbx], 0
0x140052f09  jmp     short loc_140052F3D
0x140052f0b  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140052f0f  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140052f16  mov     edx, 0F003Fh; DesiredAccess
0x140052f1b  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x140052f1f  mov     [rbp+ObjectAttributes.Attributes], 240h
0x140052f26  mov     [rbp+ObjectAttributes.ObjectName], r14
0x140052f2a  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140052f2f  call    cs:__imp_ZwOpenKey
0x140052f36  nop     dword ptr [rax+rax+00h]
0x140052f3b  mov     esi, eax
0x140052f3d  test    rdi, rdi
0x140052f40  jz      short loc_140052F56
0x140052f42  mov     edx, 52727343h; Tag
0x140052f47  mov     rcx, rdi; P
0x140052f4a  call    cs:__imp_ExFreePoolWithTag
0x140052f51  nop     dword ptr [rax+rax+00h]
0x140052f56  mov     eax, esi
0x140052f58  lea     r11, [rsp+70h+var_s0]
0x140052f5d  mov     rbx, [r11+28h]
0x140052f61  mov     rsi, [r11+38h]
0x140052f65  mov     rsp, r11
0x140052f68  pop     r14
0x140052f6a  pop     rdi
0x140052f6b  pop     rbp
0x140052f6c  retn
```
