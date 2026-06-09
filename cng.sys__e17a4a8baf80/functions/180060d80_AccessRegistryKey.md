# AccessRegistryKey

- ea: `0x180060d80`
- end: `0x180060e39`
- name: `AccessRegistryKey`
- size: `185`
- prototype: `__int64 __fastcall(PCWSTR SourceString, ACCESS_MASK DesiredAccess, PHANDLE KeyHandle)`
- caller_count: `3`
- callee_count: `0`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180060e40`
- `0x180061668`
- `0x180067920`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180060db6`
- `ntoskrnl!RtlInitUnicodeString` at `0x180060db6`
- `ntoskrnl!ZwCreateKey` at `0x180060e0e`
- `ntoskrnl!ZwCreateKey` at `0x180060e0e`

## pseudocode

```c
_BOOL8 __fastcall AccessRegistryKey(PCWSTR SourceString, ACCESS_MASK DesiredAccess, PHANDLE KeyHandle)
{
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF

  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  return ZwCreateKey(KeyHandle, DesiredAccess, &ObjectAttributes, 0, 0, 0, 0) >= 0;
}

```

## disassembly

```asm
0x180060d80  mov     [rsp-8+arg_0], rbx
0x180060d85  mov     [rsp-8+arg_8], rdi
0x180060d8a  push    rbp
0x180060d8b  mov     rbp, rsp
0x180060d8e  sub     rsp, 80h
0x180060d95  xorps   xmm0, xmm0
0x180060d98  mov     ebx, edx
0x180060d9a  mov     rdx, rcx; SourceString
0x180060d9d  xor     eax, eax
0x180060d9f  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180060da3  lea     rcx, [rbp+DestinationString]; DestinationString
0x180060da7  mov     rdi, r8
0x180060daa  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180060dae  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180060db2  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180060db6  call    cs:__imp_RtlInitUnicodeString
0x180060dbd  nop     dword ptr [rax+rax+00h]
0x180060dc2  lea     rax, [rbp+DestinationString]
0x180060dc6  mov     [rsp+80h+Disposition], 0; Disposition
0x180060dcf  xorps   xmm0, xmm0
0x180060dd2  mov     [rsp+80h+CreateOptions], 0; CreateOptions
0x180060dda  xor     r9d, r9d; TitleIndex
0x180060ddd  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180060de1  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180060de5  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180060dec  mov     edx, ebx; DesiredAccess
0x180060dee  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180060df6  mov     rcx, rdi; KeyHandle
0x180060df9  mov     [rbp+ObjectAttributes.Attributes], 240h
0x180060e00  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180060e05  mov     [rsp+80h+Class], 0; Class
0x180060e0e  call    cs:__imp_ZwCreateKey
0x180060e15  nop     dword ptr [rax+rax+00h]
0x180060e1a  xor     ecx, ecx
0x180060e1c  lea     r11, [rsp+80h+var_s0]
0x180060e24  mov     rbx, [r11+10h]
0x180060e28  test    eax, eax
0x180060e2a  mov     rdi, [r11+18h]
0x180060e2e  setns   cl
0x180060e31  mov     eax, ecx
0x180060e33  mov     rsp, r11
0x180060e36  pop     rbp
0x180060e37  retn
```
