# NlpOpenCache(void)

- ea: `0x180042c48`
- end: `0x180042cc5`
- name: `?NlpOpenCache@@YAJXZ`
- size: `125`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `0`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800425d0`

## import_xrefs

- `ntdll!NtCreateKey` at `0x180042cb6`
- `ntdll!NtCreateKey` at `0x180042cb6`

## string_xrefs

- `0x180042c5e`: `\Registry\Machine\Security\Cache`

## pseudocode

```c
NTSTATUS NlpOpenCache(void)
{
  _QWORD v1[2]; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  ULONG Disposition; // [rsp+90h] [rbp+10h] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  Disposition = 0;
  v1[1] = L"\\Registry\\Machine\\Security\\Cache";
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v1;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  v1[0] = 4194368;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  return NtCreateKey(&NlpCacheHandle, 0x2001Fu, &ObjectAttributes, 0x64u, 0, 0, &Disposition);
}

```

## disassembly

```asm
0x180042c48  push    rbp
0x180042c4a  mov     rbp, rsp
0x180042c4d  sub     rsp, 80h
0x180042c54  xor     edx, edx
0x180042c56  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x180042c5e  lea     rax, aRegistryMachin; "\\Registry\\Machine\\Security\\Cache"
0x180042c65  mov     [rbp+arg_0], edx
0x180042c68  mov     [rbp+var_38], rax
0x180042c6c  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180042c70  lea     rax, [rbp+var_40]
0x180042c74  mov     [rbp+ObjectAttributes.RootDirectory], rdx
0x180042c78  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180042c7c  lea     r9d, [rdx+64h]; TitleIndex
0x180042c80  lea     rax, [rbp+arg_0]
0x180042c84  mov     qword ptr [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180042c8c  mov     [rsp+80h+Disposition], rax; Disposition
0x180042c91  lea     rcx, ?NlpCacheHandle@@3PEAXEA; KeyHandle
0x180042c98  mov     [rsp+80h+CreateOptions], edx; CreateOptions
0x180042c9c  xorps   xmm0, xmm0
0x180042c9f  mov     [rsp+80h+Class], rdx; Class
0x180042ca4  mov     edx, 2001Fh; DesiredAccess
0x180042ca9  mov     [rbp+var_40], 400040h
0x180042cb1  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180042cb6  call    cs:__imp_NtCreateKey
0x180042cbc  add     rsp, 80h
0x180042cc3  pop     rbp
0x180042cc4  retn
```
