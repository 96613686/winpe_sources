# StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)

- ea: `0x140008768`
- end: `0x1400087b3`
- name: `?StringCchCopyNW@@YAJPEAG_KPEBG1@Z`
- size: `75`
- prototype: `__int64 __fastcall(unsigned __int16 *, size_t, size_t *, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400040d4`
- `0x1400066d8`

## callees

- `0x140008768`
- `0x14000894c`

## pseudocode

```c
__int64 __fastcall StringCchCopyNW(unsigned __int16 *a1, size_t a2, size_t *a3, size_t cchToCopy)
{
  unsigned int v4; // edx

  if ( a2 )
  {
    if ( a2 > 0x7FFFFFFF || cchToCopy > 0x7FFFFFFE )
    {
      v4 = -2147024809;
      *a1 = 0;
    }
    else
    {
      return (unsigned int)StringCopyWorkerW(a1, a2, a3, (STRSAFE_PCNZWCH)a3, cchToCopy);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v4;
}

```

## disassembly

```asm
0x140008768  sub     rsp, 38h
0x14000876c  mov     rax, rdx
0x14000876f  test    rdx, rdx
0x140008772  jz      short loc_14000879D
0x140008774  cmp     rax, 7FFFFFFFh
0x14000877a  jbe     short loc_140008783
0x14000877c  mov     edx, 80070057h; cchDest
0x140008781  jmp     short loc_1400087A7
0x140008783  cmp     r9, 7FFFFFFEh
0x14000878a  ja      short loc_14000877C
0x14000878c  mov     [rsp+38h+cchToCopy], r9; cchToCopy
0x140008791  mov     r9, r8; pszSrc
0x140008794  call    StringCopyWorkerW
0x140008799  mov     edx, eax
0x14000879b  jmp     short loc_1400087AC
0x14000879d  mov     edx, 80070057h
0x1400087a2  test    rax, rax
0x1400087a5  jz      short loc_1400087AC
0x1400087a7  xor     eax, eax
0x1400087a9  mov     [rcx], ax
0x1400087ac  mov     eax, edx
0x1400087ae  add     rsp, 38h
0x1400087b2  retn
```
