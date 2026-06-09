# Csl::StringEqualIgnoreCase(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &,utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)

- ea: `0x14000d7e4`
- end: `0x14000d815`
- name: `?StringEqualIgnoreCase@Csl@@YA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@0@Z`
- size: `49`
- prototype: `bool __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x14001bb2c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14000d7fd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14000d7fd`

## pseudocode

```c
bool __fastcall Csl::StringEqualIgnoreCase(__int64 a1, __int64 a2)
{
  return CompareStringOrdinal(*(LPCWCH *)a1, *(_DWORD *)(a1 + 8), *(LPCWCH *)a2, *(_DWORD *)(a2 + 8), 1) == 2;
}

```

## disassembly

```asm
0x14000d7e4  sub     rsp, 38h
0x14000d7e8  mov     r9d, [rdx+8]; cchCount2
0x14000d7ec  mov     r8, [rdx]; lpString2
0x14000d7ef  mov     edx, [rcx+8]; cchCount1
0x14000d7f2  mov     rcx, [rcx]; lpString1
0x14000d7f5  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x14000d7fd  call    cs:__imp_CompareStringOrdinal
0x14000d804  nop     dword ptr [rax+rax+00h]
0x14000d809  cmp     eax, 2
0x14000d80c  setz    al
0x14000d80f  add     rsp, 38h
0x14000d813  retn
```
