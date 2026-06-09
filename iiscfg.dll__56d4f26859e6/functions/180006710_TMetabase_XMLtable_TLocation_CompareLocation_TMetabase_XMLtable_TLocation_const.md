# TMetabase_XMLtable::TLocation::CompareLocation(TMetabase_XMLtable::TLocation const &)

- ea: `0x180006710`
- end: `0x18000673f`
- name: `?CompareLocation@TLocation@TMetabase_XMLtable@@AEBAHAEBV12@@Z`
- size: `47`
- prototype: `__int64 __fastcall(TMetabase_XMLtable::TLocation *__hidden this, const struct TMetabase_XMLtable::TLocation *)`
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006310`
- `0x18000d110`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x180006734`
- `KERNEL32!CompareStringW` at `0x180006734`

## pseudocode

```c
int __fastcall TMetabase_XMLtable::TLocation::CompareLocation(
        TMetabase_XMLtable::TLocation *this,
        const struct TMetabase_XMLtable::TLocation *a2)
{
  return CompareStringW(0x800u, 0x1001u, *(PCNZWCH *)this, *((_DWORD *)this + 4), *(PCNZWCH *)a2, *((_DWORD *)a2 + 4));
}

```

## disassembly

```asm
0x180006710  sub     rsp, 38h
0x180006714  mov     eax, [rdx+10h]
0x180006717  mov     r9d, [rcx+10h]; cchCount1
0x18000671b  mov     r8, [rcx]; lpString1
0x18000671e  mov     ecx, 800h; Locale
0x180006723  mov     [rsp+38h+cchCount2], eax; cchCount2
0x180006727  mov     rax, [rdx]
0x18000672a  mov     edx, 1001h; dwCmpFlags
0x18000672f  mov     [rsp+38h+lpString2], rax; lpString2
0x180006734  call    cs:__imp_CompareStringW
0x18000673a  add     rsp, 38h
0x18000673e  retn
```
