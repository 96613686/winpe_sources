# OpenSyncEvent

- ea: `0x18000c548`
- end: `0x18000c5cc`
- name: `OpenSyncEvent`
- size: `132`
- prototype: `__int64 __fastcall(PHANDLE EventHandle)`
- caller_count: `1`
- callee_count: `0`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180006bf4`

## import_xrefs

- `ntoskrnl!ZwOpenEvent` at `0x18000c5b4`
- `ntoskrnl!ZwOpenEvent` at `0x18000c5b4`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000c576`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000c576`

## string_xrefs

- `0x18000c558`: `\SECURITY\LSA_AUTHENTICATION_INITIALIZED`

## pseudocode

```c
NTSTATUS __fastcall OpenSyncEvent(PHANDLE EventHandle)
{
  UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF

  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\SECURITY\\LSA_AUTHENTICATION_INITIALIZED");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  return ZwOpenEvent(EventHandle, 0x1F0003u, &ObjectAttributes);
}

```

## disassembly

```asm
0x18000c548  mov     [rsp-8+arg_0], rbx
0x18000c54d  push    rbp
0x18000c54e  mov     rbp, rsp
0x18000c551  sub     rsp, 60h
0x18000c555  xorps   xmm0, xmm0
0x18000c558  lea     rdx, aSecurityLsaAut; "\\SECURITY\\LSA_AUTHENTICATION_INITIALI"...
0x18000c55f  mov     rbx, rcx
0x18000c562  lea     rcx, [rbp+DestinationString]; DestinationString
0x18000c566  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18000c56a  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18000c56e  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18000c572  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18000c576  call    cs:__imp_RtlInitUnicodeString
0x18000c57d  nop     dword ptr [rax+rax+00h]
0x18000c582  lea     rax, [rbp+DestinationString]
0x18000c586  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18000c58d  xorps   xmm0, xmm0
0x18000c590  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18000c594  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18000c598  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18000c5a0  mov     edx, 1F0003h; DesiredAccess
0x18000c5a5  mov     [rbp+ObjectAttributes.Attributes], 240h
0x18000c5ac  mov     rcx, rbx; EventHandle
0x18000c5af  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18000c5b4  call    cs:__imp_ZwOpenEvent
0x18000c5bb  nop     dword ptr [rax+rax+00h]
0x18000c5c0  mov     rbx, [rsp+60h+arg_0]
0x18000c5c5  add     rsp, 60h
0x18000c5c9  pop     rbp
0x18000c5ca  retn
```
