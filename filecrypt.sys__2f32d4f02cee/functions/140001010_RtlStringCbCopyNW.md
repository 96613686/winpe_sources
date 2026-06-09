# RtlStringCbCopyNW

- ea: `0x140001010`
- end: `0x14000104e`
- name: `RtlStringCbCopyNW`
- size: `62`
- prototype: `NTSTATUS __stdcall(NTSTRSAFE_PWSTR pszDest, size_t cbDest, STRSAFE_PCNZWCH pszSrc, size_t cbToCopy)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140010500`
- `0x1400113e0`
- `0x140012a40`

## callees

- `0x140001010`
- `0x140001060`

## pseudocode

```c
NTSTATUS __stdcall RtlStringCbCopyNW(NTSTRSAFE_PWSTR pszDest, size_t cbDest, STRSAFE_PCNZWCH pszSrc, size_t cbToCopy)
{
  size_t v4; // rdx
  size_t cchToCopy; // r9

  v4 = cbDest >> 1;
  if ( v4 - 1 <= 0x7FFFFFFE )
  {
    cchToCopy = cbToCopy >> 1;
    if ( cchToCopy <= 0x7FFFFFFE )
      return RtlStringCopyWorkerW(pszDest, v4, (size_t *)pszSrc, pszSrc, cchToCopy);
    *pszDest = 0;
  }
  return -1073741811;
}

```

## disassembly

```asm
0x140001010  sub     rsp, 38h
0x140001014  shr     rdx, 1; cchDest
0x140001017  lea     rax, [rdx-1]
0x14000101b  cmp     rax, 7FFFFFFEh
0x140001021  ja      short loc_140001047
0x140001023  shr     r9, 1
0x140001026  cmp     r9, 7FFFFFFEh
0x14000102d  ja      short loc_140001042
0x14000102f  mov     [rsp+38h+cchToCopy], r9; cchToCopy
0x140001034  mov     r9, r8; pszSrc
0x140001037  call    RtlStringCopyWorkerW
0x14000103c  add     rsp, 38h
0x140001040  retn
0x140001042  xor     eax, eax
0x140001044  mov     [rcx], ax
0x140001047  mov     eax, 0C000000Dh
0x14000104c  jmp     short loc_14000103C
```
