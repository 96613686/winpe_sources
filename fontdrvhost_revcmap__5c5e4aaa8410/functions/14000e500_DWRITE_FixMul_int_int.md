# DWRITE_FixMul(int,int)

- ea: `0x14000e500`
- end: `0x14000e53a`
- name: `?DWRITE_FixMul@@YAHHH@Z`
- size: `58`
- prototype: `__int64 __fastcall(int, int)`
- caller_count: `21`
- callee_count: `1`
- tags: ``

## callers

- `0x140001554`
- `0x14000c29c`
- `0x14000cf80`
- `0x14000d128`
- `0x14000d918`
- `0x14000e258`
- `0x14000e348`
- `0x14000e3e4`
- `0x140014364`
- `0x14001d214`
- `0x140029e04`
- `0x14002a840`
- `0x1400324b0`
- `0x140049848`
- `0x140049f44`
- `0x14005d7b0`
- `0x14005d950`
- `0x14005e75c`
- `0x140064c60`
- `0x1400916bc`
- `0x140092488`

## callees

- `0x14000e500`

## pseudocode

```c
__int64 __fastcall DWRITE_FixMul(int a1, int a2)
{
  __int64 result; // rax

  result = (a2 * (__int64)a1 + ((a2 * (__int64)a1) >> 63) + 0x8000) >> 16;
  if ( result > 0x7FFFFFFF )
    return 0x7FFFFFFF;
  if ( result < (__int64)0xFFFFFFFF80000000uLL )
    return 0x80000000LL;
  return result;
}

```

## disassembly

```asm
0x14000e500  movsxd  rax, edx
0x14000e503  movsxd  r8, ecx
0x14000e506  imul    r8, rax
0x14000e50a  mov     rax, r8
0x14000e50d  sar     rax, 3Fh
0x14000e511  add     rax, 8000h
0x14000e517  add     rax, r8
0x14000e51a  sar     rax, 10h
0x14000e51e  cmp     rax, 7FFFFFFFh
0x14000e524  jg      short loc_14000E534
0x14000e526  mov     rcx, 0FFFFFFFF80000000h
0x14000e52d  cmp     rax, rcx
0x14000e530  cmovl   eax, ecx
0x14000e533  retn
0x14000e534  mov     eax, 7FFFFFFFh
0x14000e539  retn
```
