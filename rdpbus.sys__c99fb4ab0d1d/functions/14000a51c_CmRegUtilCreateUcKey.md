# CmRegUtilCreateUcKey

- ea: `0x14000a51c`
- end: `0x14000a5c0`
- name: `CmRegUtilCreateUcKey`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14000a5c8`

## callees

- `0x14000a51c`

## import_xrefs

- `ntoskrnl!ZwCreateKey` at `0x14000a584`
- `ntoskrnl!ZwCreateKey` at `0x14000a584`

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
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
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
0x14000a51c  mov     [rsp-8+arg_18], r9d
0x14000a521  push    rbp
0x14000a522  mov     rbp, rsp
0x14000a525  sub     rsp, 70h
0x14000a529  xor     eax, eax
0x14000a52b  mov     [rbp+ObjectAttributes.RootDirectory], rcx
0x14000a52f  mov     [rbp+arg_18], eax
0x14000a532  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14000a536  mov     [rbp+KeyHandle], rax
0x14000a53a  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x14000a53e  mov     rax, [rbp+arg_20]
0x14000a542  xor     r9d, r9d; TitleIndex
0x14000a545  mov     [rbp+ObjectAttributes.SecurityDescriptor], rax
0x14000a549  lea     rax, [rbp+arg_18]
0x14000a54d  mov     [rsp+70h+Disposition], rax; Disposition
0x14000a552  mov     [rbp+ObjectAttributes.ObjectName], rdx
0x14000a556  mov     edx, 0F003Fh; DesiredAccess
0x14000a55b  mov     [rsp+70h+CreateOptions], 0; CreateOptions
0x14000a563  mov     [rsp+70h+Class], 0; Class
0x14000a56c  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x14000a574  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x14000a57c  mov     [rbp+ObjectAttributes.SecurityQualityOfService], 0
0x14000a584  call    cs:__imp_ZwCreateKey
0x14000a58b  nop     dword ptr [rax+rax+00h]
0x14000a590  mov     r8d, eax
0x14000a593  test    eax, eax
0x14000a595  jns     short loc_14000A59D
0x14000a597  xor     edx, edx
0x14000a599  xor     ecx, ecx
0x14000a59b  jmp     short loc_14000A5A4
0x14000a59d  mov     ecx, [rbp+arg_18]
0x14000a5a0  mov     rdx, [rbp+KeyHandle]
0x14000a5a4  mov     rax, [rbp+arg_30]
0x14000a5a8  mov     [rax], rdx
0x14000a5ab  mov     rax, [rbp+arg_28]
0x14000a5af  test    rax, rax
0x14000a5b2  jz      short loc_14000A5B6
0x14000a5b4  mov     [rax], ecx
0x14000a5b6  mov     eax, r8d
0x14000a5b9  add     rsp, 70h
0x14000a5bd  pop     rbp
0x14000a5be  retn
```
