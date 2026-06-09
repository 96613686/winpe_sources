# CompareNetNames(ushort const *,ushort const *)

- ea: `0x1800044cc`
- end: `0x1800044e7`
- name: `?CompareNetNames@@YA?AW4_comparisonresult@@PEBG0@Z`
- size: `27`
- prototype: `__int64 __fastcall(const WCHAR *, const WCHAR *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800043e4`
- `0x1800044f0`
- `0x1800049dc`

## callees

- `0x180004e98`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800044d0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800044d0`

## pseudocode

```c
__int64 __fastcall CompareNetNames(const WCHAR *a1, const WCHAR *a2)
{
  unsigned int v2; // eax

  v2 = lstrcmpW(a1, a2);
  return MapIntToComparisonResult(v2);
}

```

## disassembly

```asm
0x1800044cc  sub     rsp, 28h
0x1800044d0  call    cs:__imp_lstrcmpW
0x1800044d7  nop     dword ptr [rax+rax+00h]
0x1800044dc  mov     ecx, eax
0x1800044de  add     rsp, 28h
0x1800044e2  jmp     ?MapIntToComparisonResult@@YA?AW4_comparisonresult@@H@Z; MapIntToComparisonResult(int)
```
