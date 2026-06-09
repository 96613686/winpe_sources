# StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)

- ea: `0x180008bf4`
- end: `0x180008c3f`
- name: `?StringCchCopyNW@@YAJPEAG_KPEBG1@Z`
- size: `75`
- prototype: `int(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800066dc`

## callees

- `0x180008bf4`
- `0x180008d0c`

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
0x180008bf4  sub     rsp, 38h
0x180008bf8  mov     rax, rdx
0x180008bfb  test    rdx, rdx
0x180008bfe  jz      short loc_180008C29
0x180008c00  cmp     rax, 7FFFFFFFh
0x180008c06  jbe     short loc_180008C0F
0x180008c08  mov     edx, 80070057h; cchDest
0x180008c0d  jmp     short loc_180008C33
0x180008c0f  cmp     r9, 7FFFFFFEh
0x180008c16  ja      short loc_180008C08
0x180008c18  mov     [rsp+38h+cchToCopy], r9; cchToCopy
0x180008c1d  mov     r9, r8; pszSrc
0x180008c20  call    StringCopyWorkerW
0x180008c25  mov     edx, eax
0x180008c27  jmp     short loc_180008C38
0x180008c29  mov     edx, 80070057h
0x180008c2e  test    rax, rax
0x180008c31  jz      short loc_180008C38
0x180008c33  xor     eax, eax
0x180008c35  mov     [rcx], ax
0x180008c38  mov     eax, edx
0x180008c3a  add     rsp, 38h
0x180008c3e  retn
```
