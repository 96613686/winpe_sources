# PcwpRbNameCompareNoCase

- ea: `0x14000f134`
- end: `0x14000f151`
- name: `PcwpRbNameCompareNoCase`
- size: `29`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x14000ed0c`
- `0x14000f094`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x14000f13f`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000f13f`

## pseudocode

```c
LONG __fastcall PcwpRbNameCompareNoCase(const UNICODE_STRING *a1, __int64 a2)
{
  return RtlCompareUnicodeString(a1, (PCUNICODE_STRING)(a2 + 24), 1u);
}

```

## disassembly

```asm
0x14000f134  sub     rsp, 28h
0x14000f138  add     rdx, 18h; String2
0x14000f13c  mov     r8b, 1; CaseInSensitive
0x14000f13f  call    cs:__imp_RtlCompareUnicodeString
0x14000f146  nop     dword ptr [rax+rax+00h]
0x14000f14b  add     rsp, 28h
0x14000f14f  retn
```
