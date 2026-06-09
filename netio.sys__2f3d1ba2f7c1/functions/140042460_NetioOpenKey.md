# NetioOpenKey

- ea: `0x140042460`
- end: `0x1400424eb`
- name: `NetioOpenKey`
- size: `139`
- prototype: `__int64 __fastcall(PCWSTR SourceString, ACCESS_MASK DesiredAccess, PHANDLE KeyHandle)`
- caller_count: `6`
- callee_count: `0`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14005c36c`
- `0x14005c45c`
- `0x14005c9a0`
- `0x14005ce70`
- `0x14005d654`
- `0x140076400`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x1400424ce`
- `ntoskrnl!ZwOpenKey` at `0x1400424ce`
- `ntoskrnl!RtlInitUnicodeString` at `0x140042493`
- `ntoskrnl!RtlInitUnicodeString` at `0x140042493`

## pseudocode

```c
NTSTATUS __fastcall NetioOpenKey(PCWSTR SourceString, ACCESS_MASK DesiredAccess, PHANDLE KeyHandle)
{
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF

  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  return ZwOpenKey(KeyHandle, DesiredAccess, &ObjectAttributes);
}

```

## disassembly

```asm
0x140042460  mov     [rsp-8+arg_0], rbx
0x140042465  mov     [rsp-8+arg_8], rdi
0x14004246a  push    rbp
0x14004246b  mov     rbp, rsp
0x14004246e  sub     rsp, 60h
0x140042472  xorps   xmm0, xmm0
0x140042475  mov     ebx, edx
0x140042477  mov     rdx, rcx; SourceString
0x14004247a  xor     eax, eax
0x14004247c  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140042480  lea     rcx, [rbp+DestinationString]; DestinationString
0x140042484  mov     rdi, r8
0x140042487  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x14004248b  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14004248f  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140042493  call    cs:__imp_RtlInitUnicodeString
0x14004249a  nop     dword ptr [rax+rax+00h]
0x14004249f  lea     rax, [rbp+DestinationString]
0x1400424a3  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400424aa  xorps   xmm0, xmm0
0x1400424ad  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1400424b1  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400424b5  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1400424bd  mov     edx, ebx; DesiredAccess
0x1400424bf  mov     [rbp+ObjectAttributes.Attributes], 240h
0x1400424c6  mov     rcx, rdi; KeyHandle
0x1400424c9  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400424ce  call    cs:__imp_ZwOpenKey
0x1400424d5  nop     dword ptr [rax+rax+00h]
0x1400424da  mov     rbx, [rsp+60h+arg_0]
0x1400424df  mov     rdi, [rsp+60h+arg_8]
0x1400424e4  add     rsp, 60h
0x1400424e8  pop     rbp
0x1400424e9  retn
```
