# SockOpenKey

- ea: `0x180008ac0`
- end: `0x180008b71`
- name: `SockOpenKey`
- size: `177`
- prototype: `__int64 __fastcall(PHANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `0`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180009e48`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x180008b54`
- `ntdll!RtlFreeUnicodeString` at `0x180008b54`
- `ntdll!NtOpenKey` at `0x180008b42`
- `ntdll!NtOpenKey` at `0x180008b42`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180008b04`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180008b04`
- `ntdll!RtlInitString` at `0x180008aed`
- `ntdll!RtlInitString` at `0x180008aed`

## pseudocode

```c
__int64 __fastcall SockOpenKey(PHANDLE KeyHandle, const char *a2)
{
  _UNICODE_STRING UnicodeString; // [rsp+20h] [rbp-50h] BYREF
  _STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF

  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  UnicodeString = 0;
  RtlInitString(&DestinationString, a2);
  RtlAnsiStringToUnicodeString(&UnicodeString, &DestinationString, 1u);
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &UnicodeString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  LODWORD(KeyHandle) = NtOpenKey(KeyHandle, 0x20019u, &ObjectAttributes);
  RtlFreeUnicodeString(&UnicodeString);
  return (unsigned int)KeyHandle;
}

```

## disassembly

```asm
0x180008ac0  mov     [rsp-8+arg_0], rbx
0x180008ac5  push    rbp
0x180008ac6  mov     rbp, rsp
0x180008ac9  sub     rsp, 70h
0x180008acd  xorps   xmm0, xmm0
0x180008ad0  mov     rbx, rcx
0x180008ad3  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180008ad7  xor     eax, eax
0x180008ad9  lea     rcx, [rbp+DestinationString]; DestinationString
0x180008add  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180008ae1  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180008ae5  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180008ae9  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x180008aed  call    cs:__imp_RtlInitString
0x180008af4  nop     dword ptr [rax+rax+00h]
0x180008af9  mov     r8b, 1; AllocateDestinationString
0x180008afc  lea     rdx, [rbp+DestinationString]; SourceString
0x180008b00  lea     rcx, [rbp+UnicodeString]; DestinationString
0x180008b04  call    cs:__imp_RtlAnsiStringToUnicodeString
0x180008b0b  nop     dword ptr [rax+rax+00h]
0x180008b10  xor     eax, eax
0x180008b12  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x180008b1a  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x180008b1e  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180008b22  lea     rax, [rbp+UnicodeString]
0x180008b26  mov     qword ptr [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180008b2e  xorps   xmm0, xmm0
0x180008b31  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180008b35  mov     edx, 20019h; DesiredAccess
0x180008b3a  mov     rcx, rbx; KeyHandle
0x180008b3d  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180008b42  call    cs:__imp_NtOpenKey
0x180008b49  nop     dword ptr [rax+rax+00h]
0x180008b4e  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x180008b52  mov     ebx, eax
0x180008b54  call    cs:__imp_RtlFreeUnicodeString
0x180008b5b  nop     dword ptr [rax+rax+00h]
0x180008b60  mov     eax, ebx
0x180008b62  mov     rbx, [rsp+70h+arg_0]
0x180008b6a  add     rsp, 70h
0x180008b6e  pop     rbp
0x180008b6f  retn
```
