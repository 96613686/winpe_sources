# ACpDeleteFile

- ea: `0x14000f2b4`
- end: `0x14000f317`
- name: `ACpDeleteFile`
- size: `99`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `2`
- callee_count: `0`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14000ef78`
- `0x14000fcb8`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14000f2c8`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000f2c8`
- `ntoskrnl!ZwDeleteFile` at `0x14000f305`
- `ntoskrnl!ZwDeleteFile` at `0x14000f305`

## pseudocode

```c
NTSTATUS __fastcall ACpDeleteFile(PCWSTR SourceString)
{
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-38h] BYREF

  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  return ZwDeleteFile(&ObjectAttributes);
}

```

## disassembly

```asm
0x14000f2b4  sub     rsp, 68h
0x14000f2b8  xorps   xmm0, xmm0
0x14000f2bb  mov     rdx, rcx; SourceString
0x14000f2be  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x14000f2c3  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x14000f2c8  call    cs:__imp_RtlInitUnicodeString
0x14000f2cf  nop     dword ptr [rax+rax+00h]
0x14000f2d4  xor     eax, eax
0x14000f2d6  mov     qword ptr [rsp+68h+ObjectAttributes.Length], 30h ; '0'
0x14000f2df  mov     [rsp+68h+ObjectAttributes.RootDirectory], rax
0x14000f2e4  lea     rcx, [rsp+68h+ObjectAttributes]; ObjectAttributes
0x14000f2e9  lea     rax, [rsp+68h+DestinationString]
0x14000f2ee  mov     qword ptr [rsp+68h+ObjectAttributes.Attributes], 40h ; '@'
0x14000f2f7  xorps   xmm0, xmm0
0x14000f2fa  mov     [rsp+68h+ObjectAttributes.ObjectName], rax
0x14000f2ff  movdqu  xmmword ptr [rsp+68h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000f305  call    cs:__imp_ZwDeleteFile
0x14000f30c  nop     dword ptr [rax+rax+00h]
0x14000f311  add     rsp, 68h
0x14000f315  retn
```
