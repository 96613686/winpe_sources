# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180006c6c`
- end: `0x180006caa`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `62`
- prototype: `int(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x1800042b4`
- `0x180007118`
- `0x180008064`
- `0x1800083a0`
- `0x180014bb0`
- `0x18001bd94`
- `0x180020508`
- `0x1800239a8`
- `0x1800247f4`

## callees

- `0x180006c6c`
- `0x180006d14`

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
0x180006c6c  sub     rsp, 38h
0x180006c70  mov     rax, rdx
0x180006c73  test    rdx, rdx
0x180006c76  jz      short loc_180006C93
0x180006c78  cmp     rax, 7FFFFFFFh
0x180006c7e  jbe     short loc_180006C87
0x180006c80  mov     edx, 80070057h; cchDest
0x180006c85  jmp     short loc_180006C9D
0x180006c87  mov     r9, r8; pszSrc
0x180006c8a  call    StringCopyWorkerW
0x180006c8f  mov     edx, eax
0x180006c91  jmp     short loc_180006CA2
0x180006c93  mov     edx, 80070057h
0x180006c98  test    rax, rax
0x180006c9b  jz      short loc_180006CA2
0x180006c9d  xor     eax, eax
0x180006c9f  mov     [rcx], ax
0x180006ca2  mov     eax, edx
0x180006ca4  add     rsp, 38h
0x180006ca8  retn
```
