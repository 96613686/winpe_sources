# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180008cf8`
- end: `0x180008d35`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `61`
- prototype: `__int64 __fastcall(unsigned __int16 *, size_t, size_t *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180007074`
- `0x180008ea8`
- `0x18000c99c`
- `0x1800130a4`

## callees

- `0x180008cf8`
- `0x180008da0`

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
0x180008cf8  sub     rsp, 38h
0x180008cfc  mov     rax, rdx
0x180008cff  test    rdx, rdx
0x180008d02  jz      short loc_180008D1F
0x180008d04  cmp     rax, 7FFFFFFFh
0x180008d0a  jbe     short loc_180008D13
0x180008d0c  mov     edx, 80070057h; cchDest
0x180008d11  jmp     short loc_180008D29
0x180008d13  mov     r9, r8; pszSrc
0x180008d16  call    StringCopyWorkerW
0x180008d1b  mov     edx, eax
0x180008d1d  jmp     short loc_180008D2E
0x180008d1f  mov     edx, 80070057h
0x180008d24  test    rax, rax
0x180008d27  jz      short loc_180008D2E
0x180008d29  xor     eax, eax
0x180008d2b  mov     [rcx], ax
0x180008d2e  mov     eax, edx
0x180008d30  add     rsp, 38h
0x180008d34  retn
```
