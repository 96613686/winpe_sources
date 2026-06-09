# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180007f38`
- end: `0x180007f75`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `61`
- prototype: `__int64 __fastcall(unsigned __int16 *, size_t, size_t *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180001790`
- `0x180001de0`
- `0x180006a34`
- `0x180008138`

## callees

- `0x180007f38`
- `0x180008028`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, size_t a2, size_t *a3)
{
  unsigned int v3; // edx
  size_t v5; // [rsp+20h] [rbp-18h]

  if ( a2 )
  {
    if ( a2 <= 0x7FFFFFFF )
    {
      return (unsigned int)StringCopyWorkerW(a1, a2, a3, (STRSAFE_PCNZWCH)a3, v5);
    }
    else
    {
      v3 = -2147024809;
      *a1 = 0;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v3;
}

```

## disassembly

```asm
0x180007f38  sub     rsp, 38h
0x180007f3c  mov     rax, rdx
0x180007f3f  test    rdx, rdx
0x180007f42  jz      short loc_180007F5F
0x180007f44  cmp     rax, 7FFFFFFFh
0x180007f4a  jbe     short loc_180007F53
0x180007f4c  mov     edx, 80070057h; cchDest
0x180007f51  jmp     short loc_180007F69
0x180007f53  mov     r9, r8; pszSrc
0x180007f56  call    StringCopyWorkerW
0x180007f5b  mov     edx, eax
0x180007f5d  jmp     short loc_180007F6E
0x180007f5f  mov     edx, 80070057h
0x180007f64  test    rax, rax
0x180007f67  jz      short loc_180007F6E
0x180007f69  xor     eax, eax
0x180007f6b  mov     [rcx], ax
0x180007f6e  mov     eax, edx
0x180007f70  add     rsp, 38h
0x180007f74  retn
```
