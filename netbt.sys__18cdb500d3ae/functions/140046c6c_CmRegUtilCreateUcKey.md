# CmRegUtilCreateUcKey

- ea: `0x140046c6c`
- end: `0x140046d10`
- name: `CmRegUtilCreateUcKey`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140046d18`

## callees

- `0x140046c6c`

## import_xrefs

- `ntoskrnl!ZwCreateKey` at `0x140046cd4`
- `ntoskrnl!ZwCreateKey` at `0x140046cd4`

## pseudocode

```c
__int64 __fastcall CmRegUtilCreateUcKey(
        void *a1,
        struct _UNICODE_STRING *a2,
        __int64 a3,
        __int64 a4,
        void *a5,
        ULONG *a6,
        _QWORD *a7)
{
  NTSTATUS v7; // r8d
  void *v8; // rdx
  ULONG v9; // ecx
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+80h] [rbp+10h] BYREF
  ULONG Disposition; // [rsp+98h] [rbp+28h] BYREF

  ObjectAttributes.RootDirectory = a1;
  Disposition = 0;
  KeyHandle = 0;
  ObjectAttributes.SecurityDescriptor = a5;
  ObjectAttributes.ObjectName = a2;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  ObjectAttributes.SecurityQualityOfService = 0;
  v7 = ZwCreateKey(&KeyHandle, 0xF003Fu, &ObjectAttributes, 0, 0, 0, &Disposition);
  if ( v7 >= 0 )
  {
    v9 = Disposition;
    v8 = KeyHandle;
  }
  else
  {
    v8 = 0;
    v9 = 0;
  }
  *a7 = v8;
  if ( a6 )
    *a6 = v9;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140046c6c  mov     [rsp-8+arg_18], r9d
0x140046c71  push    rbp
0x140046c72  mov     rbp, rsp
0x140046c75  sub     rsp, 70h
0x140046c79  xor     eax, eax
0x140046c7b  mov     [rbp+ObjectAttributes.RootDirectory], rcx
0x140046c7f  mov     [rbp+arg_18], eax
0x140046c82  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140046c86  mov     [rbp+KeyHandle], rax
0x140046c8a  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x140046c8e  mov     rax, [rbp+arg_20]
0x140046c92  xor     r9d, r9d; TitleIndex
0x140046c95  mov     [rbp+ObjectAttributes.SecurityDescriptor], rax
0x140046c99  lea     rax, [rbp+arg_18]
0x140046c9d  mov     [rsp+70h+Disposition], rax; Disposition
0x140046ca2  mov     [rbp+ObjectAttributes.ObjectName], rdx
0x140046ca6  mov     edx, 0F003Fh; DesiredAccess
0x140046cab  mov     [rsp+70h+CreateOptions], 0; CreateOptions
0x140046cb3  mov     [rsp+70h+Class], 0; Class
0x140046cbc  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x140046cc4  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x140046ccc  mov     [rbp+ObjectAttributes.SecurityQualityOfService], 0
0x140046cd4  call    cs:__imp_ZwCreateKey
0x140046cdb  nop     dword ptr [rax+rax+00h]
0x140046ce0  mov     r8d, eax
0x140046ce3  test    eax, eax
0x140046ce5  jns     short loc_140046CED
0x140046ce7  xor     edx, edx
0x140046ce9  xor     ecx, ecx
0x140046ceb  jmp     short loc_140046CF4
0x140046ced  mov     ecx, [rbp+arg_18]
0x140046cf0  mov     rdx, [rbp+KeyHandle]
0x140046cf4  mov     rax, [rbp+arg_30]
0x140046cf8  mov     [rax], rdx
0x140046cfb  mov     rax, [rbp+arg_28]
0x140046cff  test    rax, rax
0x140046d02  jz      short loc_140046D06
0x140046d04  mov     [rax], ecx
0x140046d06  mov     eax, r8d
0x140046d09  add     rsp, 70h
0x140046d0d  pop     rbp
0x140046d0e  retn
```
