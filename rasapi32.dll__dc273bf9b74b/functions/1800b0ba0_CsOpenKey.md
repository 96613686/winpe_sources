# CsOpenKey

- ea: `0x1800b0ba0`
- end: `0x1800b0c22`
- name: `CsOpenKey`
- size: `130`
- prototype: `NTSTATUS __fastcall(PHANDLE KeyHandle, ACCESS_MASK DesiredAccess)`
- caller_count: `2`
- callee_count: `0`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800b06e0`
- `0x1800b0800`

## import_xrefs

- `ntdll!NtOpenKey` at `0x1800b0c0c`
- `ntdll!NtOpenKey` at `0x1800b0c0c`
- `ntdll!RtlInitUnicodeString` at `0x1800b0bd7`
- `ntdll!RtlInitUnicodeString` at `0x1800b0bd7`

## string_xrefs

- `0x1800b0bba`: `\Registry\Machine\System\CurrentControlSet\Services\SharedAccess\Parameters`

## pseudocode

```c
NTSTATUS __fastcall CsOpenKey(PHANDLE KeyHandle, ACCESS_MASK DesiredAccess)
{
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF

  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\SharedAccess\\Parameters");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  return NtOpenKey(KeyHandle, DesiredAccess, &ObjectAttributes);
}

```

## disassembly

```asm
0x1800b0ba0  mov     [rsp-8+arg_0], rbx
0x1800b0ba5  mov     [rsp-8+arg_8], rdi
0x1800b0baa  push    rbp
0x1800b0bab  mov     rbp, rsp
0x1800b0bae  sub     rsp, 60h
0x1800b0bb2  xorps   xmm0, xmm0
0x1800b0bb5  mov     ebx, edx
0x1800b0bb7  mov     rdi, rcx
0x1800b0bba  lea     rdx, c_szSharedAccessParametersKey; "\\Registry\\Machine\\System\\CurrentCon"...
0x1800b0bc1  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800b0bc5  xor     eax, eax
0x1800b0bc7  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800b0bcb  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x1800b0bcf  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800b0bd3  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800b0bd7  call    cs:__imp_RtlInitUnicodeString
0x1800b0bdd  lea     rax, [rbp+DestinationString]
0x1800b0be1  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800b0be8  xorps   xmm0, xmm0
0x1800b0beb  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1800b0bef  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800b0bf3  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1800b0bfb  mov     edx, ebx; DesiredAccess
0x1800b0bfd  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x1800b0c04  mov     rcx, rdi; KeyHandle
0x1800b0c07  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800b0c0c  call    cs:__imp_NtOpenKey
0x1800b0c12  mov     rbx, [rsp+60h+arg_0]
0x1800b0c17  mov     rdi, [rsp+60h+arg_8]
0x1800b0c1c  add     rsp, 60h
0x1800b0c20  pop     rbp
0x1800b0c21  retn
```
