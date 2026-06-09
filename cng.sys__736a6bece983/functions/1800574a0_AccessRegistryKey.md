# AccessRegistryKey

- ea: `0x1800574a0`
- end: `0x180057559`
- name: `AccessRegistryKey`
- size: `185`
- prototype: `_BOOL8 __fastcall(PCWSTR SourceString, ACCESS_MASK DesiredAccess, PHANDLE KeyHandle)`
- caller_count: `3`
- callee_count: `0`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180057560`
- `0x180057d88`
- `0x18005e040`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1800574d6`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800574d6`
- `ntoskrnl!ZwCreateKey` at `0x18005752e`
- `ntoskrnl!ZwCreateKey` at `0x18005752e`

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
0x1800574a0  mov     [rsp-8+arg_0], rbx
0x1800574a5  mov     [rsp-8+arg_8], rdi
0x1800574aa  push    rbp
0x1800574ab  mov     rbp, rsp
0x1800574ae  sub     rsp, 80h
0x1800574b5  xorps   xmm0, xmm0
0x1800574b8  mov     ebx, edx
0x1800574ba  mov     rdx, rcx; SourceString
0x1800574bd  xor     eax, eax
0x1800574bf  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800574c3  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800574c7  mov     rdi, r8
0x1800574ca  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x1800574ce  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800574d2  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800574d6  call    cs:__imp_RtlInitUnicodeString
0x1800574dd  nop     dword ptr [rax+rax+00h]
0x1800574e2  lea     rax, [rbp+DestinationString]
0x1800574e6  mov     [rsp+80h+Disposition], 0; Disposition
0x1800574ef  xorps   xmm0, xmm0
0x1800574f2  mov     [rsp+80h+CreateOptions], 0; CreateOptions
0x1800574fa  xor     r9d, r9d; TitleIndex
0x1800574fd  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180057501  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180057505  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18005750c  mov     edx, ebx; DesiredAccess
0x18005750e  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180057516  mov     rcx, rdi; KeyHandle
0x180057519  mov     [rbp+ObjectAttributes.Attributes], 240h
0x180057520  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180057525  mov     [rsp+80h+Class], 0; Class
0x18005752e  call    cs:__imp_ZwCreateKey
0x180057535  nop     dword ptr [rax+rax+00h]
0x18005753a  xor     ecx, ecx
0x18005753c  lea     r11, [rsp+80h+var_s0]
0x180057544  mov     rbx, [r11+10h]
0x180057548  test    eax, eax
0x18005754a  mov     rdi, [r11+18h]
0x18005754e  setns   cl
0x180057551  mov     eax, ecx
0x180057553  mov     rsp, r11
0x180057556  pop     rbp
0x180057557  retn
```
