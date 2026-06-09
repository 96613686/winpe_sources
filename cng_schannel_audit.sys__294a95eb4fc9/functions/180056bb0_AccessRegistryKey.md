# AccessRegistryKey

- ea: `0x180056bb0`
- end: `0x180056c69`
- name: `AccessRegistryKey`
- size: `185`
- prototype: `__int64 __fastcall(PCWSTR SourceString, ACCESS_MASK DesiredAccess, PHANDLE KeyHandle)`
- caller_count: `3`
- callee_count: `0`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180056c70`
- `0x180057498`
- `0x18005d750`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180056be6`
- `ntoskrnl!RtlInitUnicodeString` at `0x180056be6`
- `ntoskrnl!ZwCreateKey` at `0x180056c3e`
- `ntoskrnl!ZwCreateKey` at `0x180056c3e`

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
0x180056bb0  mov     [rsp-8+arg_0], rbx
0x180056bb5  mov     [rsp-8+arg_8], rdi
0x180056bba  push    rbp
0x180056bbb  mov     rbp, rsp
0x180056bbe  sub     rsp, 80h
0x180056bc5  xorps   xmm0, xmm0
0x180056bc8  mov     ebx, edx
0x180056bca  mov     rdx, rcx; SourceString
0x180056bcd  xor     eax, eax
0x180056bcf  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180056bd3  lea     rcx, [rbp+DestinationString]; DestinationString
0x180056bd7  mov     rdi, r8
0x180056bda  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180056bde  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180056be2  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180056be6  call    cs:__imp_RtlInitUnicodeString
0x180056bed  nop     dword ptr [rax+rax+00h]
0x180056bf2  lea     rax, [rbp+DestinationString]
0x180056bf6  mov     [rsp+80h+Disposition], 0; Disposition
0x180056bff  xorps   xmm0, xmm0
0x180056c02  mov     [rsp+80h+CreateOptions], 0; CreateOptions
0x180056c0a  xor     r9d, r9d; TitleIndex
0x180056c0d  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180056c11  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180056c15  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180056c1c  mov     edx, ebx; DesiredAccess
0x180056c1e  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180056c26  mov     rcx, rdi; KeyHandle
0x180056c29  mov     [rbp+ObjectAttributes.Attributes], 240h
0x180056c30  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180056c35  mov     [rsp+80h+Class], 0; Class
0x180056c3e  call    cs:__imp_ZwCreateKey
0x180056c45  nop     dword ptr [rax+rax+00h]
0x180056c4a  xor     ecx, ecx
0x180056c4c  lea     r11, [rsp+80h+var_s0]
0x180056c54  mov     rbx, [r11+10h]
0x180056c58  test    eax, eax
0x180056c5a  mov     rdi, [r11+18h]
0x180056c5e  setns   cl
0x180056c61  mov     eax, ecx
0x180056c63  mov     rsp, r11
0x180056c66  pop     rbp
0x180056c67  retn
```
