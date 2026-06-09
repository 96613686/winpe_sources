# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180008c48`
- end: `0x180008c8e`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `70`
- prototype: `int(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x18000527c`
- `0x180009100`
- `0x18000ba40`
- `0x18000bfa4`
- `0x18000dc64`
- `0x18000eb9c`
- `0x18000ef20`
- `0x180010440`
- `0x18001226c`

## callees

- `0x180008c48`
- `0x180008d0c`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, size_t a2, size_t *a3)
{
  unsigned int v3; // edx

  if ( a2 )
  {
    if ( a2 <= 0x7FFFFFFF )
    {
      return (unsigned int)StringCopyWorkerW(a1, a2, a3, (STRSAFE_PCNZWCH)a3, 0x7FFFFFFEu);
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
0x180008c48  sub     rsp, 38h
0x180008c4c  mov     rax, rdx
0x180008c4f  test    rdx, rdx
0x180008c52  jz      short loc_180008C78
0x180008c54  cmp     rax, 7FFFFFFFh
0x180008c5a  jbe     short loc_180008C63
0x180008c5c  mov     edx, 80070057h; cchDest
0x180008c61  jmp     short loc_180008C82
0x180008c63  mov     r9, r8; pszSrc
0x180008c66  mov     [rsp+38h+cchToCopy], 7FFFFFFEh; cchToCopy
0x180008c6f  call    StringCopyWorkerW
0x180008c74  mov     edx, eax
0x180008c76  jmp     short loc_180008C87
0x180008c78  mov     edx, 80070057h
0x180008c7d  test    rax, rax
0x180008c80  jz      short loc_180008C87
0x180008c82  xor     eax, eax
0x180008c84  mov     [rcx], ax
0x180008c87  mov     eax, edx
0x180008c89  add     rsp, 38h
0x180008c8d  retn
```
