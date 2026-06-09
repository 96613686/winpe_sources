# CmRegUtilCreateUcKey

- ea: `0x1400122fc`
- end: `0x1400123a0`
- name: `CmRegUtilCreateUcKey`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1400123a8`

## callees

- `0x1400122fc`

## import_xrefs

- `ntoskrnl!ZwCreateKey` at `0x140012364`
- `ntoskrnl!ZwCreateKey` at `0x140012364`

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
0x1400122fc  mov     [rsp-8+arg_18], r9d
0x140012301  push    rbp
0x140012302  mov     rbp, rsp
0x140012305  sub     rsp, 70h
0x140012309  xor     eax, eax
0x14001230b  mov     [rbp+ObjectAttributes.RootDirectory], rcx
0x14001230f  mov     [rbp+arg_18], eax
0x140012312  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140012316  mov     [rbp+KeyHandle], rax
0x14001231a  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x14001231e  mov     rax, [rbp+arg_20]
0x140012322  xor     r9d, r9d; TitleIndex
0x140012325  mov     [rbp+ObjectAttributes.SecurityDescriptor], rax
0x140012329  lea     rax, [rbp+arg_18]
0x14001232d  mov     [rsp+70h+Disposition], rax; Disposition
0x140012332  mov     [rbp+ObjectAttributes.ObjectName], rdx
0x140012336  mov     edx, 0F003Fh; DesiredAccess
0x14001233b  mov     [rsp+70h+CreateOptions], 0; CreateOptions
0x140012343  mov     [rsp+70h+Class], 0; Class
0x14001234c  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x140012354  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x14001235c  mov     [rbp+ObjectAttributes.SecurityQualityOfService], 0
0x140012364  call    cs:__imp_ZwCreateKey
0x14001236b  nop     dword ptr [rax+rax+00h]
0x140012370  mov     r8d, eax
0x140012373  test    eax, eax
0x140012375  jns     short loc_14001237D
0x140012377  xor     edx, edx
0x140012379  xor     ecx, ecx
0x14001237b  jmp     short loc_140012384
0x14001237d  mov     ecx, [rbp+arg_18]
0x140012380  mov     rdx, [rbp+KeyHandle]
0x140012384  mov     rax, [rbp+arg_30]
0x140012388  mov     [rax], rdx
0x14001238b  mov     rax, [rbp+arg_28]
0x14001238f  test    rax, rax
0x140012392  jz      short loc_140012396
0x140012394  mov     [rax], ecx
0x140012396  mov     eax, r8d
0x140012399  add     rsp, 70h
0x14001239d  pop     rbp
0x14001239e  retn
```
