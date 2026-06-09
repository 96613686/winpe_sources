# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x18000b978`
- end: `0x18000b9b5`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `61`
- prototype: `int(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `15`
- callee_count: `2`
- tags: ``

## callers

- `0x1800050d0`
- `0x180006250`
- `0x18000bffc`
- `0x18000d248`
- `0x18000f830`
- `0x180010414`
- `0x180013660`
- `0x180017420`
- `0x180018a58`
- `0x180029ea8`
- `0x18002a8a8`
- `0x18002aa30`
- `0x18002ab90`
- `0x18002b0b0`
- `0x18002bc10`

## callees

- `0x18000b978`
- `0x18000baa4`

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
0x18000b978  sub     rsp, 38h
0x18000b97c  mov     rax, rdx
0x18000b97f  test    rdx, rdx
0x18000b982  jz      short loc_18000B99F
0x18000b984  cmp     rax, 7FFFFFFFh
0x18000b98a  jbe     short loc_18000B993
0x18000b98c  mov     edx, 80070057h; cchDest
0x18000b991  jmp     short loc_18000B9A9
0x18000b993  mov     r9, r8; pszSrc
0x18000b996  call    StringCopyWorkerW
0x18000b99b  mov     edx, eax
0x18000b99d  jmp     short loc_18000B9AE
0x18000b99f  mov     edx, 80070057h
0x18000b9a4  test    rax, rax
0x18000b9a7  jz      short loc_18000B9AE
0x18000b9a9  xor     eax, eax
0x18000b9ab  mov     [rcx], ax
0x18000b9ae  mov     eax, edx
0x18000b9b0  add     rsp, 38h
0x18000b9b4  retn
```
