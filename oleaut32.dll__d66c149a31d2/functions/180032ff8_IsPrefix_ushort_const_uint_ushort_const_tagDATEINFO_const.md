# IsPrefix(ushort const *,uint,ushort const *,tagDATEINFO const *)

- ea: `0x180032ff8`
- end: `0x180033048`
- name: `?IsPrefix@@YAIPEBGI0PEBUtagDATEINFO@@@Z`
- size: `80`
- prototype: `unsigned int __fastcall(PCNZWCH lpString1, unsigned int, const unsigned __int16 *, const struct tagDATEINFO *)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180027ef0`
- `0x180032ed8`
- `0x180046128`
- `0x180046494`
- `0x180046df4`
- `0x18007712c`

## callees

- `0x180032ff8`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180033031`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180033031`

## pseudocode

```c
__int64 __fastcall IsPrefix(
        PCNZWCH lpString1,
        unsigned int a2,
        const unsigned __int16 *lpString2,
        const struct tagDATEINFO *a4)
{
  __int64 cchCount2; // rbx

  cchCount2 = -1;
  do
    ++cchCount2;
  while ( lpString2[cchCount2] );
  if ( (_DWORD)cchCount2
    && a2 >= (unsigned int)cchCount2
    && CompareStringW(*((_DWORD *)a4 + 4), 1u, lpString1, cchCount2, lpString2, cchCount2) == 2 )
  {
    return (unsigned int)cchCount2;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x180032ff8  push    rbx
0x180032ffa  sub     rsp, 30h
0x180032ffe  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180033002  mov     rax, r9
0x180033005  xor     r9d, r9d
0x180033008  inc     rbx
0x18003300b  cmp     [r8+rbx*2], r9w
0x180033010  jnz     short loc_180033008
0x180033012  test    ebx, ebx
0x180033014  jz      short loc_18003303C
0x180033016  cmp     edx, ebx
0x180033018  jb      short loc_18003303C
0x18003301a  mov     [rsp+38h+cchCount2], ebx; cchCount2
0x18003301e  mov     r9d, ebx; cchCount1
0x180033021  mov     [rsp+38h+lpString2], r8; lpString2
0x180033026  mov     edx, 1; dwCmpFlags
0x18003302b  mov     r8, rcx; lpString1
0x18003302e  mov     ecx, [rax+10h]; Locale
0x180033031  call    cs:__imp_CompareStringW
0x180033037  cmp     eax, 2
0x18003303a  jz      short loc_180033044
0x18003303c  xor     eax, eax
0x18003303e  add     rsp, 30h
0x180033042  pop     rbx
0x180033043  retn
0x180033044  mov     eax, ebx
0x180033046  jmp     short loc_18003303E
```
