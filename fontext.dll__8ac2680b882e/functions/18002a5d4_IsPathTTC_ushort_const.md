# IsPathTTC(ushort const *)

- ea: `0x18002a5d4`
- end: `0x18002a60b`
- name: `?IsPathTTC@@YAHPEBG@Z`
- size: `55`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ec84`
- `0x18000f6b8`

## import_xrefs

- `SHLWAPI!PathFindExtensionW` at `0x18002a5d8`
- `SHLWAPI!PathFindExtensionW` at `0x18002a5d8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002a5f6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002a5f6`

## pseudocode

```c
_BOOL8 __fastcall IsPathTTC(const unsigned __int16 *a1)
{
  const WCHAR *ExtensionW; // rax

  ExtensionW = PathFindExtensionW(a1);
  return CompareStringOrdinal(L".ttc", -1, ExtensionW, -1, 1) == 2;
}

```

## disassembly

```asm
0x18002a5d4  sub     rsp, 38h
0x18002a5d8  call    cs:__imp_PathFindExtensionW
0x18002a5de  or      edx, 0FFFFFFFFh; cchCount1
0x18002a5e1  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18002a5e9  mov     r9d, edx; cchCount2
0x18002a5ec  lea     rcx, aTtc; ".ttc"
0x18002a5f3  mov     r8, rax; lpString2
0x18002a5f6  call    cs:__imp_CompareStringOrdinal
0x18002a5fc  xor     ecx, ecx
0x18002a5fe  cmp     eax, 2
0x18002a601  setz    cl
0x18002a604  mov     eax, ecx
0x18002a606  add     rsp, 38h
0x18002a60a  retn
```
