# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x1800069ec`
- end: `0x180006a29`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `61`
- prototype: `int(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x1800041bc`
- `0x180006e88`
- `0x180007ce4`
- `0x180008000`
- `0x180014340`
- `0x18001b2d4`
- `0x18001f888`
- `0x180022c08`
- `0x1800239f4`

## callees

- `0x1800069ec`
- `0x180006a94`

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
0x1800069ec  sub     rsp, 38h
0x1800069f0  mov     rax, rdx
0x1800069f3  test    rdx, rdx
0x1800069f6  jz      short loc_180006A13
0x1800069f8  cmp     rax, 7FFFFFFFh
0x1800069fe  jbe     short loc_180006A07
0x180006a00  mov     edx, 80070057h; cchDest
0x180006a05  jmp     short loc_180006A1D
0x180006a07  mov     r9, r8; pszSrc
0x180006a0a  call    StringCopyWorkerW
0x180006a0f  mov     edx, eax
0x180006a11  jmp     short loc_180006A22
0x180006a13  mov     edx, 80070057h
0x180006a18  test    rax, rax
0x180006a1b  jz      short loc_180006A22
0x180006a1d  xor     eax, eax
0x180006a1f  mov     [rcx], ax
0x180006a22  mov     eax, edx
0x180006a24  add     rsp, 38h
0x180006a28  retn
```
