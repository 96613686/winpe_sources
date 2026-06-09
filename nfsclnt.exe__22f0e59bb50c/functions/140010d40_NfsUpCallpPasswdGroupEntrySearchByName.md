# NfsUpCallpPasswdGroupEntrySearchByName

- ea: `0x140010d40`
- end: `0x140010d4d`
- name: `NfsUpCallpPasswdGroupEntrySearchByName`
- size: `13`
- prototype: `LONG __fastcall(const UNICODE_STRING *, PCUNICODE_STRING *)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x140010d46`

## pseudocode

```c
LONG __fastcall NfsUpCallpPasswdGroupEntrySearchByName(const UNICODE_STRING *a1, PCUNICODE_STRING *a2)
{
  return RtlCompareUnicodeString(a1, *a2, 1u);
}

```

## disassembly

```asm
0x140010d40  mov     rdx, [rdx]
0x140010d43  mov     r8b, 1
0x140010d46  jmp     cs:__imp_RtlCompareUnicodeString
```
