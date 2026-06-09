# CmRegUtilCreateUcKey

- ea: `0x140022254`
- end: `0x1400222f8`
- name: `CmRegUtilCreateUcKey`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140022300`

## callees

- `0x140022254`

## import_xrefs

- `ntoskrnl!ZwCreateKey` at `0x1400222bc`
- `ntoskrnl!ZwCreateKey` at `0x1400222bc`

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
0x140022254  mov     [rsp-8+arg_18], r9d
0x140022259  push    rbp
0x14002225a  mov     rbp, rsp
0x14002225d  sub     rsp, 70h
0x140022261  xor     eax, eax
0x140022263  mov     [rbp+ObjectAttributes.RootDirectory], rcx
0x140022267  mov     [rbp+arg_18], eax
0x14002226a  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14002226e  mov     [rbp+KeyHandle], rax
0x140022272  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x140022276  mov     rax, [rbp+arg_20]
0x14002227a  xor     r9d, r9d; TitleIndex
0x14002227d  mov     [rbp+ObjectAttributes.SecurityDescriptor], rax
0x140022281  lea     rax, [rbp+arg_18]
0x140022285  mov     [rsp+70h+Disposition], rax; Disposition
0x14002228a  mov     [rbp+ObjectAttributes.ObjectName], rdx
0x14002228e  mov     edx, 0F003Fh; DesiredAccess
0x140022293  mov     [rsp+70h+CreateOptions], 0; CreateOptions
0x14002229b  mov     [rsp+70h+Class], 0; Class
0x1400222a4  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400222ac  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x1400222b4  mov     [rbp+ObjectAttributes.SecurityQualityOfService], 0
0x1400222bc  call    cs:__imp_ZwCreateKey
0x1400222c3  nop     dword ptr [rax+rax+00h]
0x1400222c8  mov     r8d, eax
0x1400222cb  test    eax, eax
0x1400222cd  jns     short loc_1400222D5
0x1400222cf  xor     edx, edx
0x1400222d1  xor     ecx, ecx
0x1400222d3  jmp     short loc_1400222DC
0x1400222d5  mov     ecx, [rbp+arg_18]
0x1400222d8  mov     rdx, [rbp+KeyHandle]
0x1400222dc  mov     rax, [rbp+arg_30]
0x1400222e0  mov     [rax], rdx
0x1400222e3  mov     rax, [rbp+arg_28]
0x1400222e7  test    rax, rax
0x1400222ea  jz      short loc_1400222EE
0x1400222ec  mov     [rax], ecx
0x1400222ee  mov     eax, r8d
0x1400222f1  add     rsp, 70h
0x1400222f5  pop     rbp
0x1400222f6  retn
```
