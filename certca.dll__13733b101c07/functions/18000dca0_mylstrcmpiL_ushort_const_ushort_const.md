# mylstrcmpiL(ushort const *,ushort const *)

- ea: `0x18000dca0`
- end: `0x18000dcd2`
- name: `?mylstrcmpiL@@YAHPEBG0@Z`
- size: `50`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, PCNZWCH lpString2)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000dcc4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000dcc4`

## pseudocode

```c
__int64 __fastcall mylstrcmpiL(PCNZWCH lpString1, PCNZWCH lpString2)
{
  return (unsigned int)(CompareStringW(0x7Fu, 1u, lpString1, -1, lpString2, -1) - 2);
}

```

## disassembly

```asm
0x18000dca0  sub     rsp, 38h
0x18000dca4  mov     r8, rcx; lpString1
0x18000dca7  mov     [rsp+38h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000dcaf  mov     [rsp+38h+lpString2], rdx; lpString2
0x18000dcb4  mov     r9d, 0FFFFFFFFh; cchCount1
0x18000dcba  mov     edx, 1; dwCmpFlags
0x18000dcbf  mov     ecx, 7Fh; Locale
0x18000dcc4  call    cs:__imp_CompareStringW
0x18000dcca  sub     eax, 2
0x18000dccd  add     rsp, 38h
0x18000dcd1  retn
```
