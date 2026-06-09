# SockOpenKey

- ea: `0x1800085d0`
- end: `0x180008668`
- name: `SockOpenKey`
- size: `152`
- prototype: `__int64 __fastcall(PHANDLE KeyHandle, const char *)`
- caller_count: `1`
- callee_count: `0`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000980c`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x180008652`
- `ntdll!RtlFreeUnicodeString` at `0x180008652`
- `ntdll!NtOpenKey` at `0x180008646`
- `ntdll!NtOpenKey` at `0x180008646`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18000860e`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18000860e`
- `ntdll!RtlInitString` at `0x1800085fd`
- `ntdll!RtlInitString` at `0x1800085fd`

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
0x1800085d0  mov     [rsp-8+arg_0], rbx
0x1800085d5  push    rbp
0x1800085d6  mov     rbp, rsp
0x1800085d9  sub     rsp, 70h
0x1800085dd  xorps   xmm0, xmm0
0x1800085e0  mov     rbx, rcx
0x1800085e3  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800085e7  xor     eax, eax
0x1800085e9  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800085ed  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x1800085f1  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800085f5  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800085f9  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x1800085fd  call    cs:__imp_RtlInitString
0x180008603  mov     r8b, 1; AllocateDestinationString
0x180008606  lea     rdx, [rbp+DestinationString]; SourceString
0x18000860a  lea     rcx, [rbp+UnicodeString]; DestinationString
0x18000860e  call    cs:__imp_RtlAnsiStringToUnicodeString
0x180008614  xor     eax, eax
0x180008616  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x18000861e  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x180008622  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180008626  lea     rax, [rbp+UnicodeString]
0x18000862a  mov     qword ptr [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180008632  xorps   xmm0, xmm0
0x180008635  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180008639  mov     edx, 20019h; DesiredAccess
0x18000863e  mov     rcx, rbx; KeyHandle
0x180008641  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180008646  call    cs:__imp_NtOpenKey
0x18000864c  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x180008650  mov     ebx, eax
0x180008652  call    cs:__imp_RtlFreeUnicodeString
0x180008658  mov     eax, ebx
0x18000865a  mov     rbx, [rsp+70h+arg_0]
0x180008662  add     rsp, 70h
0x180008666  pop     rbp
0x180008667  retn
```
