# BuildUYVYToRGB32

- ea: `0x180002764`
- end: `0x18000285e`
- name: `BuildUYVYToRGB32`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800021c8`

## callees

- `0x180002764`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180002786`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180002786`

## pseudocode

```c
_WORD *__fastcall BuildUYVYToRGB32(__int64 a1)
{
  _WORD *result; // rax
  __int64 v2; // r8
  __int64 v3; // r8
  double v4; // xmm0_8
  __int64 v5; // r8
  double v6; // xmm0_8

  result = *(_WORD **)(a1 + 8);
  if ( !result )
  {
    result = VirtualAlloc(0, 0xA00u, 0x3000u, 4u);
    if ( result )
    {
      v2 = 0;
      do
      {
        result[v2] = (int)((double)((int)v2 - 16) * 1.164 + 0.0);
        v2 = (unsigned int)(v2 + 1);
      }
      while ( (int)v2 < 256 );
      v3 = 0;
      do
      {
        v4 = (double)((int)v3 - 128);
        result[v3 + 256] = (int)(v4 * 1.596);
        result[v3 + 512] = (int)(v4 * -0.8129999999999999);
        v3 = (unsigned int)(v3 + 1);
      }
      while ( (int)v3 < 256 );
      v5 = 0;
      do
      {
        v6 = (double)((int)v5 - 128);
        result[v5 + 768] = (int)(v6 * -0.391);
        result[v5 + 1024] = (int)(v6 * 2.018);
        v5 = (unsigned int)(v5 + 1);
      }
      while ( (int)v5 < 256 );
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002764  sub     rsp, 28h
0x180002768  mov     rax, [rcx+8]
0x18000276c  test    rax, rax
0x18000276f  jnz     loc_180002859
0x180002775  mov     edx, 0A00h; dwSize
0x18000277a  lea     r9d, [rax+4]; flProtect
0x18000277e  xor     ecx, ecx; lpAddress
0x180002780  mov     r8d, 3000h; flAllocationType
0x180002786  call    cs:__imp_VirtualAlloc
0x18000278c  mov     rdx, rax
0x18000278f  test    rax, rax
0x180002792  jz      loc_180002859
0x180002798  xor     r8d, r8d
0x18000279b  mov     r9d, 100h
0x1800027a1  lea     eax, [r8-10h]
0x1800027a5  movd    xmm0, eax
0x1800027a9  cvtdq2pd xmm0, xmm0
0x1800027ad  mulsd   xmm0, cs:__real@3ff29fbe76c8b439
0x1800027b5  addsd   xmm0, cs:__real@0000000000000000
0x1800027bd  cvttsd2si ecx, xmm0
0x1800027c1  mov     [rdx+r8*2], cx
0x1800027c6  inc     r8d
0x1800027c9  cmp     r8d, r9d
0x1800027cc  jl      short loc_1800027A1
0x1800027ce  xor     r8d, r8d
0x1800027d1  lea     eax, [r8-80h]
0x1800027d5  movd    xmm1, eax
0x1800027d9  cvtdq2pd xmm1, xmm1
0x1800027dd  movaps  xmm0, xmm1
0x1800027e0  mulsd   xmm1, cs:__real@bfea04189374bc6a
0x1800027e8  mulsd   xmm0, cs:__real@3ff989374bc6a7f0
0x1800027f0  cvttsd2si eax, xmm0
0x1800027f4  mov     [rdx+r8*2+200h], ax
0x1800027fd  cvttsd2si eax, xmm1
0x180002801  mov     [rdx+r8*2+400h], ax
0x18000280a  inc     r8d
0x18000280d  cmp     r8d, r9d
0x180002810  jl      short loc_1800027D1
0x180002812  xor     r8d, r8d
0x180002815  lea     eax, [r8-80h]
0x180002819  movd    xmm1, eax
0x18000281d  cvtdq2pd xmm1, xmm1
0x180002821  movaps  xmm0, xmm1
0x180002824  mulsd   xmm1, cs:__real@400024dd2f1a9fbe
0x18000282c  mulsd   xmm0, cs:__real@bfd90624dd2f1aa0
0x180002834  cvttsd2si eax, xmm0
0x180002838  mov     [rdx+r8*2+600h], ax
0x180002841  cvttsd2si eax, xmm1
0x180002845  mov     [rdx+r8*2+800h], ax
0x18000284e  inc     r8d
0x180002851  cmp     r8d, r9d
0x180002854  jl      short loc_180002815
0x180002856  mov     rax, rdx
0x180002859  add     rsp, 28h
0x18000285d  retn
```
