# scanfrac

- ea: `0x180008b44`
- end: `0x180008b8a`
- name: `scanfrac`
- size: `70`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800057a0`
- `0x180005ae0`

## callees

- `0x180008b44`

## pseudocode

```c
char __fastcall scanfrac(_BYTE *a1, int a2, _QWORD *a3, _DWORD *a4)
{
  double v4; // xmm2_8
  double i; // xmm0_8
  int v6; // eax
  int v7; // eax

  v4 = DOUBLE_1_0;
  for ( i = 0.0; a2; --a2 )
  {
    LOBYTE(v6) = *a1 - 48;
    if ( (unsigned __int8)v6 > 9u )
      break;
    v4 = v4 / 10.0;
    v7 = (char)*a1++;
    v6 = v7 - 48;
    i = i + (double)v6 * v4;
  }
  *a3 = a1;
  *a4 = a2;
  return v6;
}

```

## disassembly

```asm
0x180008b44  movsd   xmm2, cs:__real@3ff0000000000000
0x180008b4c  xorps   xmm0, xmm0
0x180008b4f  test    edx, edx
0x180008b51  jz      short loc_180008B5B
0x180008b53  mov     al, [rcx]
0x180008b55  sub     al, 30h ; '0'
0x180008b57  cmp     al, 9
0x180008b59  jbe     short loc_180008B62
0x180008b5b  mov     [r8], rcx
0x180008b5e  mov     [r9], edx
0x180008b61  retn
0x180008b62  divsd   xmm2, cs:__real@4024000000000000
0x180008b6a  movsx   eax, byte ptr [rcx]
0x180008b6d  inc     rcx
0x180008b70  sub     eax, 30h ; '0'
0x180008b73  movd    xmm1, eax
0x180008b77  cvtdq2pd xmm1, xmm1
0x180008b7b  mulsd   xmm1, xmm2
0x180008b7f  addsd   xmm0, xmm1
0x180008b83  add     edx, 0FFFFFFFFh
0x180008b86  jnz     short loc_180008B53
0x180008b88  jmp     short loc_180008B5B
```
