# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x14000c2a8`
- end: `0x14000c2e5`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `61`
- prototype: `int(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14000b1fc`
- `0x14000c5f8`
- `0x14000f7d8`

## callees

- `0x14000c2a8`
- `0x14000c374`

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
0x14000c2a8  sub     rsp, 38h
0x14000c2ac  mov     rax, rdx
0x14000c2af  test    rdx, rdx
0x14000c2b2  jz      short loc_14000C2CF
0x14000c2b4  cmp     rax, 7FFFFFFFh
0x14000c2ba  jbe     short loc_14000C2C3
0x14000c2bc  mov     edx, 80070057h; cchDest
0x14000c2c1  jmp     short loc_14000C2D9
0x14000c2c3  mov     r9, r8; pszSrc
0x14000c2c6  call    StringCopyWorkerW
0x14000c2cb  mov     edx, eax
0x14000c2cd  jmp     short loc_14000C2DE
0x14000c2cf  mov     edx, 80070057h
0x14000c2d4  test    rax, rax
0x14000c2d7  jz      short loc_14000C2DE
0x14000c2d9  xor     eax, eax
0x14000c2db  mov     [rcx], ax
0x14000c2de  mov     eax, edx
0x14000c2e0  add     rsp, 38h
0x14000c2e4  retn
```
