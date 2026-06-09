# CmRegUtilCreateUcKey

- ea: `0x14000e5ac`
- end: `0x14000e650`
- name: `CmRegUtilCreateUcKey`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14000e658`

## callees

- `0x14000e5ac`

## import_xrefs

- `ntoskrnl!ZwCreateKey` at `0x14000e614`
- `ntoskrnl!ZwCreateKey` at `0x14000e614`

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
0x14000e5ac  mov     [rsp-8+arg_18], r9d
0x14000e5b1  push    rbp
0x14000e5b2  mov     rbp, rsp
0x14000e5b5  sub     rsp, 70h
0x14000e5b9  xor     eax, eax
0x14000e5bb  mov     [rbp+ObjectAttributes.RootDirectory], rcx
0x14000e5bf  mov     [rbp+arg_18], eax
0x14000e5c2  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14000e5c6  mov     [rbp+KeyHandle], rax
0x14000e5ca  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x14000e5ce  mov     rax, [rbp+arg_20]
0x14000e5d2  xor     r9d, r9d; TitleIndex
0x14000e5d5  mov     [rbp+ObjectAttributes.SecurityDescriptor], rax
0x14000e5d9  lea     rax, [rbp+arg_18]
0x14000e5dd  mov     [rsp+70h+Disposition], rax; Disposition
0x14000e5e2  mov     [rbp+ObjectAttributes.ObjectName], rdx
0x14000e5e6  mov     edx, 0F003Fh; DesiredAccess
0x14000e5eb  mov     [rsp+70h+CreateOptions], 0; CreateOptions
0x14000e5f3  mov     [rsp+70h+Class], 0; Class
0x14000e5fc  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x14000e604  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x14000e60c  mov     [rbp+ObjectAttributes.SecurityQualityOfService], 0
0x14000e614  call    cs:__imp_ZwCreateKey
0x14000e61b  nop     dword ptr [rax+rax+00h]
0x14000e620  mov     r8d, eax
0x14000e623  test    eax, eax
0x14000e625  jns     short loc_14000E62D
0x14000e627  xor     edx, edx
0x14000e629  xor     ecx, ecx
0x14000e62b  jmp     short loc_14000E634
0x14000e62d  mov     ecx, [rbp+arg_18]
0x14000e630  mov     rdx, [rbp+KeyHandle]
0x14000e634  mov     rax, [rbp+arg_30]
0x14000e638  mov     [rax], rdx
0x14000e63b  mov     rax, [rbp+arg_28]
0x14000e63f  test    rax, rax
0x14000e642  jz      short loc_14000E646
0x14000e644  mov     [rax], ecx
0x14000e646  mov     eax, r8d
0x14000e649  add     rsp, 70h
0x14000e64d  pop     rbp
0x14000e64e  retn
```
