# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180006b04`
- end: `0x180006b41`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `61`
- prototype: `__int64 __fastcall(unsigned __int16 *, size_t, size_t *)`
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x180003c08`
- `0x180006fb4`
- `0x18000f248`
- `0x18000f5bc`
- `0x18000f7c8`
- `0x18000fc14`
- `0x180010184`
- `0x1800104f0`
- `0x180013730`
- `0x18001795c`
- `0x18001919c`

## callees

- `0x180006b04`
- `0x180006bac`

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
0x180006b04  sub     rsp, 38h
0x180006b08  mov     rax, rdx
0x180006b0b  test    rdx, rdx
0x180006b0e  jz      short loc_180006B2B
0x180006b10  cmp     rax, 7FFFFFFFh
0x180006b16  jbe     short loc_180006B1F
0x180006b18  mov     edx, 80070057h; cchDest
0x180006b1d  jmp     short loc_180006B35
0x180006b1f  mov     r9, r8; pszSrc
0x180006b22  call    StringCopyWorkerW
0x180006b27  mov     edx, eax
0x180006b29  jmp     short loc_180006B3A
0x180006b2b  mov     edx, 80070057h
0x180006b30  test    rax, rax
0x180006b33  jz      short loc_180006B3A
0x180006b35  xor     eax, eax
0x180006b37  mov     [rcx], ax
0x180006b3a  mov     eax, edx
0x180006b3c  add     rsp, 38h
0x180006b40  retn
```
