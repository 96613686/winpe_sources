# CmRegUtilCreateUcKey

- ea: `0x1400449ac`
- end: `0x140044a50`
- name: `CmRegUtilCreateUcKey`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140044a58`

## callees

- `0x1400449ac`

## import_xrefs

- `ntoskrnl!ZwCreateKey` at `0x140044a14`
- `ntoskrnl!ZwCreateKey` at `0x140044a14`

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
0x1400449ac  mov     [rsp-8+arg_18], r9d
0x1400449b1  push    rbp
0x1400449b2  mov     rbp, rsp
0x1400449b5  sub     rsp, 70h
0x1400449b9  xor     eax, eax
0x1400449bb  mov     [rbp+ObjectAttributes.RootDirectory], rcx
0x1400449bf  mov     [rbp+arg_18], eax
0x1400449c2  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400449c6  mov     [rbp+KeyHandle], rax
0x1400449ca  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x1400449ce  mov     rax, [rbp+arg_20]
0x1400449d2  xor     r9d, r9d; TitleIndex
0x1400449d5  mov     [rbp+ObjectAttributes.SecurityDescriptor], rax
0x1400449d9  lea     rax, [rbp+arg_18]
0x1400449dd  mov     [rsp+70h+Disposition], rax; Disposition
0x1400449e2  mov     [rbp+ObjectAttributes.ObjectName], rdx
0x1400449e6  mov     edx, 0F003Fh; DesiredAccess
0x1400449eb  mov     [rsp+70h+CreateOptions], 0; CreateOptions
0x1400449f3  mov     [rsp+70h+Class], 0; Class
0x1400449fc  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x140044a04  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x140044a0c  mov     [rbp+ObjectAttributes.SecurityQualityOfService], 0
0x140044a14  call    cs:__imp_ZwCreateKey
0x140044a1b  nop     dword ptr [rax+rax+00h]
0x140044a20  mov     r8d, eax
0x140044a23  test    eax, eax
0x140044a25  jns     short loc_140044A2D
0x140044a27  xor     edx, edx
0x140044a29  xor     ecx, ecx
0x140044a2b  jmp     short loc_140044A34
0x140044a2d  mov     ecx, [rbp+arg_18]
0x140044a30  mov     rdx, [rbp+KeyHandle]
0x140044a34  mov     rax, [rbp+arg_30]
0x140044a38  mov     [rax], rdx
0x140044a3b  mov     rax, [rbp+arg_28]
0x140044a3f  test    rax, rax
0x140044a42  jz      short loc_140044A46
0x140044a44  mov     [rax], ecx
0x140044a46  mov     eax, r8d
0x140044a49  add     rsp, 70h
0x140044a4d  pop     rbp
0x140044a4e  retn
```
