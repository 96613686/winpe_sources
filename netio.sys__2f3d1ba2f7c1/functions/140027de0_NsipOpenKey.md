# NsipOpenKey

- ea: `0x140027de0`
- end: `0x140027e69`
- name: `NsipOpenKey`
- size: `137`
- prototype: `__int64 __fastcall(PHANDLE KeyHandle)`
- caller_count: `2`
- callee_count: `0`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140023ff4`
- `0x140027b2c`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x140027e4c`
- `ntoskrnl!ZwOpenKey` at `0x140027e4c`
- `ntoskrnl!RtlInitUnicodeString` at `0x140027e11`
- `ntoskrnl!RtlInitUnicodeString` at `0x140027e11`

## pseudocode

```c
NTSTATUS __fastcall NsipOpenKey(PHANDLE KeyHandle, const WCHAR *a2, ACCESS_MASK a3)
{
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF

  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlInitUnicodeString(&DestinationString, a2);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 1728;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  return ZwOpenKey(KeyHandle, a3, &ObjectAttributes);
}

```

## disassembly

```asm
0x140027de0  mov     [rsp-8+arg_0], rbx
0x140027de5  mov     [rsp-8+arg_8], rdi
0x140027dea  push    rbp
0x140027deb  mov     rbp, rsp
0x140027dee  sub     rsp, 60h
0x140027df2  xorps   xmm0, xmm0
0x140027df5  mov     rbx, rcx
0x140027df8  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140027dfc  xor     eax, eax
0x140027dfe  lea     rcx, [rbp+DestinationString]; DestinationString
0x140027e02  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x140027e06  mov     edi, r8d
0x140027e09  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140027e0d  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140027e11  call    cs:__imp_RtlInitUnicodeString
0x140027e18  nop     dword ptr [rax+rax+00h]
0x140027e1d  lea     rax, [rbp+DestinationString]
0x140027e21  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140027e28  xorps   xmm0, xmm0
0x140027e2b  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140027e2f  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140027e33  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140027e3b  mov     edx, edi; DesiredAccess
0x140027e3d  mov     [rbp+ObjectAttributes.Attributes], 6C0h
0x140027e44  mov     rcx, rbx; KeyHandle
0x140027e47  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140027e4c  call    cs:__imp_ZwOpenKey
0x140027e53  nop     dword ptr [rax+rax+00h]
0x140027e58  mov     rbx, [rsp+60h+arg_0]
0x140027e5d  mov     rdi, [rsp+60h+arg_8]
0x140027e62  add     rsp, 60h
0x140027e66  pop     rbp
0x140027e67  retn
```
