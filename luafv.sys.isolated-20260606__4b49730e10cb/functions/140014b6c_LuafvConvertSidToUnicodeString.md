# LuafvConvertSidToUnicodeString

- ea: `0x140014b6c`
- end: `0x140014b85`
- name: `LuafvConvertSidToUnicodeString`
- size: `25`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x1400051a8`
- `0x1400058cc`

## import_xrefs

- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x140014b73`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x140014b73`

## pseudocode

```c
NTSTATUS __fastcall LuafvConvertSidToUnicodeString(struct _UNICODE_STRING *a1, void *a2)
{
  return RtlConvertSidToUnicodeString(a1, a2, 1u);
}

```

## disassembly

```asm
0x140014b6c  sub     rsp, 28h
0x140014b70  mov     r8b, 1; AllocateDestinationString
0x140014b73  call    cs:__imp_RtlConvertSidToUnicodeString
0x140014b7a  nop     dword ptr [rax+rax+00h]
0x140014b7f  add     rsp, 28h
0x140014b83  retn
```
