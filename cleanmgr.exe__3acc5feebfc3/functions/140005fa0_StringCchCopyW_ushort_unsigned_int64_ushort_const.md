# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x140005fa0`
- end: `0x140005fdd`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `61`
- prototype: `__int64 __fastcall(unsigned __int16 *, size_t, size_t *)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x1400043e4`
- `0x1400061a0`
- `0x1400083c8`
- `0x14000b5bc`
- `0x14000bd24`
- `0x14000fa20`
- `0x140012064`
- `0x1400124b8`
- `0x140013530`
- `0x140014fe0`

## callees

- `0x140005fa0`
- `0x140006048`

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
0x140005fa0  sub     rsp, 38h
0x140005fa4  mov     rax, rdx
0x140005fa7  test    rdx, rdx
0x140005faa  jz      short loc_140005FC7
0x140005fac  cmp     rax, 7FFFFFFFh
0x140005fb2  jbe     short loc_140005FBB
0x140005fb4  mov     edx, 80070057h; cchDest
0x140005fb9  jmp     short loc_140005FD1
0x140005fbb  mov     r9, r8; pszSrc
0x140005fbe  call    StringCopyWorkerW
0x140005fc3  mov     edx, eax
0x140005fc5  jmp     short loc_140005FD6
0x140005fc7  mov     edx, 80070057h
0x140005fcc  test    rax, rax
0x140005fcf  jz      short loc_140005FD6
0x140005fd1  xor     eax, eax
0x140005fd3  mov     [rcx], ax
0x140005fd6  mov     eax, edx
0x140005fd8  add     rsp, 38h
0x140005fdc  retn
```
