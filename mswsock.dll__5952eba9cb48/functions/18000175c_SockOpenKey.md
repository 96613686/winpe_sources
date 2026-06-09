# SockOpenKey

- ea: `0x18000175c`
- end: `0x18000180d`
- name: `SockOpenKey`
- size: `177`
- prototype: `__int64 __fastcall(PHANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `0`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000170c`

## import_xrefs

- `ntdll!RtlAnsiStringToUnicodeString` at `0x1800017a0`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x1800017a0`
- `ntdll!RtlFreeUnicodeString` at `0x1800017f0`
- `ntdll!RtlFreeUnicodeString` at `0x1800017f0`
- `ntdll!NtOpenKey` at `0x1800017de`
- `ntdll!NtOpenKey` at `0x1800017de`
- `ntdll!RtlInitString` at `0x180001789`
- `ntdll!RtlInitString` at `0x180001789`

## pseudocode

```c
__int64 __fastcall SockOpenKey(PHANDLE KeyHandle, const char *a2)
{
  struct _UNICODE_STRING UnicodeString; // [rsp+20h] [rbp-50h] BYREF
  struct _STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
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
0x18000175c  mov     [rsp-8+arg_0], rbx
0x180001761  push    rbp
0x180001762  mov     rbp, rsp
0x180001765  sub     rsp, 70h
0x180001769  xorps   xmm0, xmm0
0x18000176c  mov     rbx, rcx
0x18000176f  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180001773  xor     eax, eax
0x180001775  lea     rcx, [rbp+DestinationString]; DestinationString
0x180001779  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x18000177d  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180001781  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180001785  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x180001789  call    cs:__imp_RtlInitString
0x180001790  nop     dword ptr [rax+rax+00h]
0x180001795  mov     r8b, 1; AllocateDestinationString
0x180001798  lea     rdx, [rbp+DestinationString]; SourceString
0x18000179c  lea     rcx, [rbp+UnicodeString]; DestinationString
0x1800017a0  call    cs:__imp_RtlAnsiStringToUnicodeString
0x1800017a7  nop     dword ptr [rax+rax+00h]
0x1800017ac  xor     eax, eax
0x1800017ae  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800017b6  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x1800017ba  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800017be  lea     rax, [rbp+UnicodeString]
0x1800017c2  mov     qword ptr [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x1800017ca  xorps   xmm0, xmm0
0x1800017cd  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1800017d1  mov     edx, 20019h; DesiredAccess
0x1800017d6  mov     rcx, rbx; KeyHandle
0x1800017d9  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800017de  call    cs:__imp_NtOpenKey
0x1800017e5  nop     dword ptr [rax+rax+00h]
0x1800017ea  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x1800017ee  mov     ebx, eax
0x1800017f0  call    cs:__imp_RtlFreeUnicodeString
0x1800017f7  nop     dword ptr [rax+rax+00h]
0x1800017fc  mov     eax, ebx
0x1800017fe  mov     rbx, [rsp+70h+arg_0]
0x180001806  add     rsp, 70h
0x18000180a  pop     rbp
0x18000180b  retn
```
