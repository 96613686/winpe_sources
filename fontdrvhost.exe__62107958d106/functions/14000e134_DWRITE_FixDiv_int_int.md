# DWRITE_FixDiv(int,int)

- ea: `0x14000e134`
- end: `0x14000e195`
- name: `?DWRITE_FixDiv@@YAHHH@Z`
- size: `97`
- prototype: `__int64 __fastcall(int, int)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x14000cf80`
- `0x14000d754`
- `0x14000d918`
- `0x14000e074`
- `0x14000e258`
- `0x14001f5b0`
- `0x140029e04`
- `0x14002a840`
- `0x140049848`
- `0x14005d900`
- `0x14005daa8`

## callees

- `0x14000e134`

## pseudocode

```c
__int64 __fastcall DWRITE_FixDiv(int a1, int a2)
{
  unsigned __int64 v2; // r10
  unsigned __int64 v3; // r9
  unsigned __int64 v4; // rax
  signed __int64 v5; // r10
  signed __int64 v6; // r8

  v2 = (__int64)a1 << 16;
  v3 = v2 >> 63;
  v6 = a2 / 2;
  v4 = v6 + v2;
  v5 = v2 - v6;
  LODWORD(v6) = 0x7FFFFFFF;
  if ( a2 < 0 == (_BYTE)v3 )
    v5 = v4;
  if ( a2 )
  {
    if ( v5 / a2 <= 0x7FFFFFFF )
    {
      v6 = v5 / a2;
      if ( v6 < (__int64)0xFFFFFFFF80000000uLL )
        LODWORD(v6) = 0x80000000;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14000e134  movsxd  r11, edx
0x14000e137  movsxd  r10, ecx
0x14000e13a  mov     eax, r11d
0x14000e13d  shl     r10, 10h
0x14000e141  cdq
0x14000e142  mov     ecx, 2
0x14000e147  mov     r9, r10
0x14000e14a  idiv    ecx
0x14000e14c  shr     r9, 3Fh
0x14000e150  mov     ecx, r11d
0x14000e153  movsxd  r8, eax
0x14000e156  shr     ecx, 1Fh
0x14000e159  lea     rax, [r8+r10]
0x14000e15d  sub     r10, r8
0x14000e160  cmp     cl, r9b
0x14000e163  mov     r8d, 7FFFFFFFh
0x14000e169  cmovz   r10, rax
0x14000e16d  test    r11d, r11d
0x14000e170  jz      short loc_14000E191
0x14000e172  mov     rax, r10
0x14000e175  cqo
0x14000e177  idiv    r11
0x14000e17a  cmp     rax, r8
0x14000e17d  jg      short loc_14000E191
0x14000e17f  mov     rcx, 0FFFFFFFF80000000h
0x14000e186  mov     r8, rax
0x14000e189  cmp     rax, rcx
0x14000e18c  jge     short loc_14000E191
0x14000e18e  mov     r8d, ecx
0x14000e191  mov     eax, r8d
0x14000e194  retn
```
