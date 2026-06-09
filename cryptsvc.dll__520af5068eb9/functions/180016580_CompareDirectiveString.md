# _CompareDirectiveString

- ea: `0x180016580`
- end: `0x1800165bc`
- name: `_CompareDirectiveString`
- size: `60`
- prototype: `_BOOL8 __fastcall(PCNZCH lpString1, int cchCount1, PCNZCH lpString2, int cchCount2)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180016b30`

## callees

- `0x180016580`

## import_xrefs

- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800165a3`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800165a3`

## pseudocode

```c
_BOOL8 __fastcall CompareDirectiveString(PCNZCH lpString1, int cchCount1, PCNZCH lpString2, int cchCount2)
{
  return cchCount1 == cchCount2 && CompareStringA(0x409u, 1u, lpString1, cchCount1, lpString2, cchCount2) == 2;
}

```

## disassembly

```asm
0x180016580  sub     rsp, 38h
0x180016584  cmp     edx, r9d
0x180016587  jnz     short loc_1800165B5
0x180016589  mov     [rsp+38h+cchCount2], r9d; cchCount2
0x18001658e  mov     r9d, edx; cchCount1
0x180016591  mov     [rsp+38h+lpString2], r8; lpString2
0x180016596  mov     edx, 1; dwCmpFlags
0x18001659b  mov     r8, rcx; lpString1
0x18001659e  mov     ecx, 409h; Locale
0x1800165a3  call    cs:__imp_CompareStringA
0x1800165a9  xor     ecx, ecx
0x1800165ab  cmp     eax, 2
0x1800165ae  setz    cl
0x1800165b1  mov     eax, ecx
0x1800165b3  jmp     short loc_1800165B7
0x1800165b5  xor     eax, eax
0x1800165b7  add     rsp, 38h
0x1800165bb  retn
```
