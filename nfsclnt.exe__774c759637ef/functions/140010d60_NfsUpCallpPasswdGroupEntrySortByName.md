# NfsUpCallpPasswdGroupEntrySortByName

- ea: `0x140010d60`
- end: `0x140010d70`
- name: `NfsUpCallpPasswdGroupEntrySortByName`
- size: `16`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x140010d69`

## pseudocode

```c
LONG __fastcall NfsUpCallpPasswdGroupEntrySortByName(PCUNICODE_STRING *a1, PCUNICODE_STRING *a2)
{
  return RtlCompareUnicodeString(*a1, *a2, 1u);
}

```

## disassembly

```asm
0x140010d60  mov     rdx, [rdx]
0x140010d63  mov     r8b, 1
0x140010d66  mov     rcx, [rcx]
0x140010d69  jmp     cs:__imp_RtlCompareUnicodeString
```
