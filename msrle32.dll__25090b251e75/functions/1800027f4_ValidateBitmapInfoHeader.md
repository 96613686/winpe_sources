# ValidateBitmapInfoHeader

- ea: `0x1800027f4`
- end: `0x18000294b`
- name: `ValidateBitmapInfoHeader`
- size: `343`
- prototype: `_BOOL8 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002780`

## callees

- `0x1800027f4`

## pseudocode

```c
_BOOL8 __fastcall ValidateBitmapInfoHeader(unsigned int *a1)
{
  __int64 v1; // rsi
  int v3; // eax
  unsigned __int16 v4; // r9
  unsigned int v5; // r10d
  unsigned int v6; // ecx
  int v7; // r11d
  unsigned int v8; // ecx
  unsigned int v9; // ecx
  unsigned int v10; // r10d
  unsigned int v11; // edx
  unsigned int v12; // r10d
  __int64 v13; // rcx

  v1 = *a1;
  if ( (unsigned int)(v1 - 40) > 0xFD8 )
    return 0;
  if ( !a1[1] )
    return 0;
  v3 = a1[2];
  if ( !v3 )
    return 0;
  v4 = *((_WORD *)a1 + 7);
  v5 = 32;
  if ( v4 )
    v5 = v4;
  if ( v4 > 0xC8u )
    return 0;
  v6 = a1[1];
  v7 = -v3;
  if ( v3 > 0 )
    v7 = v3;
  v8 = v5 * v6;
  if ( v8 / v5 != a1[1] )
    return 0;
  v9 = ((v8 >> 3) + 3) & 0xFFFFFFFC;
  v10 = v7 * v9;
  if ( v9 )
  {
    if ( v10 / v9 != v7 )
      return 0;
  }
  if ( v10 > 0x40000000 )
    return 0;
  if ( a1[5] > 0x40000000 )
    return 0;
  v11 = a1[8];
  if ( v11 > 0x100 )
    return 0;
  if ( !v11 && (unsigned __int16)(v4 - 1) <= 7u )
    v11 = 1 << v4;
  v12 = a1[4];
  if ( v12 == 3 && ((v4 - 16) & 0xFFEF) != 0 )
    return 0;
  v13 = 12;
  if ( v12 != 3 )
    v13 = 0;
  return v1 + v13 + 4 * (unsigned __int64)v11 <= 0x90C
      && (v12 && v12 != 3 || !a1[5] || v7 * (((a1[1] * v4 + 31) >> 3) & 0x1FFFFFFC) <= a1[5]);
}

```

## disassembly

```asm
0x1800027f4  push    rbp
0x1800027f6  push    rsi
0x1800027f7  push    r14
0x1800027f9  mov     esi, [rcx]
0x1800027fb  mov     r8, rcx
0x1800027fe  lea     eax, [rsi-28h]
0x180002801  cmp     eax, 0FD8h
0x180002806  ja      loc_180002944
0x18000280c  xor     ebp, ebp
0x18000280e  cmp     [rcx+4], ebp
0x180002811  jz      loc_180002944
0x180002817  mov     eax, [rcx+8]
0x18000281a  test    eax, eax
0x18000281c  jz      loc_180002944
0x180002822  movzx   r9d, word ptr [rcx+0Eh]
0x180002827  lea     r10d, [rbp+20h]
0x18000282b  test    r9w, r9w
0x18000282f  jz      short loc_180002835
0x180002831  movzx   r10d, r9w
0x180002835  mov     ecx, 0C8h
0x18000283a  cmp     r9w, cx
0x18000283e  ja      loc_180002944
0x180002844  mov     ecx, [r8+4]
0x180002848  mov     r11d, eax
0x18000284b  neg     r11d
0x18000284e  cmovs   r11d, eax
0x180002852  imul    ecx, r10d
0x180002856  test    r10d, r10d
0x180002859  jz      short loc_18000286C
0x18000285b  xor     edx, edx
0x18000285d  mov     eax, ecx
0x18000285f  div     r10d
0x180002862  cmp     eax, [r8+4]
0x180002866  jnz     loc_180002944
0x18000286c  shr     ecx, 3
0x18000286f  add     ecx, 3
0x180002872  and     ecx, 0FFFFFFFCh
0x180002875  mov     r10d, ecx
0x180002878  imul    r10d, r11d
0x18000287c  test    ecx, ecx
0x18000287e  jz      short loc_180002890
0x180002880  xor     edx, edx
0x180002882  mov     eax, r10d
0x180002885  div     ecx
0x180002887  cmp     eax, r11d
0x18000288a  jnz     loc_180002944
0x180002890  mov     eax, 40000000h
0x180002895  cmp     r10d, eax
0x180002898  ja      loc_180002944
0x18000289e  cmp     [r8+14h], eax
0x1800028a2  ja      loc_180002944
0x1800028a8  mov     edx, [r8+20h]
0x1800028ac  cmp     edx, 100h
0x1800028b2  ja      loc_180002944
0x1800028b8  mov     r14d, 1
0x1800028be  test    edx, edx
0x1800028c0  jnz     short loc_1800028D8
0x1800028c2  movzx   eax, r9w
0x1800028c6  sub     ax, r14w
0x1800028ca  cmp     ax, 7
0x1800028ce  ja      short loc_1800028D8
0x1800028d0  mov     ecx, r9d
0x1800028d3  mov     edx, r14d
0x1800028d6  shl     edx, cl
0x1800028d8  mov     r10d, [r8+10h]
0x1800028dc  cmp     r10d, 3
0x1800028e0  jnz     short loc_1800028F0
0x1800028e2  lea     eax, [r9-10h]
0x1800028e6  mov     ecx, 0FFEFh
0x1800028eb  test    cx, ax
0x1800028ee  jnz     short loc_180002944
0x1800028f0  cmp     r10d, 3
0x1800028f4  mov     eax, edx
0x1800028f6  mov     ecx, 0Ch
0x1800028fb  cmovnz  rcx, rbp
0x1800028ff  lea     rcx, [rcx+rax*4]
0x180002903  add     rcx, rsi
0x180002906  cmp     rcx, 90Ch
0x18000290d  ja      short loc_180002944
0x18000290f  test    r10d, r10d
0x180002912  jz      short loc_18000291A
0x180002914  cmp     r10d, 3
0x180002918  jnz     short loc_18000293F
0x18000291a  cmp     [r8+14h], ebp
0x18000291e  jz      short loc_18000293F
0x180002920  movzx   ecx, r9w
0x180002924  imul    ecx, [r8+4]
0x180002929  add     ecx, 1Fh
0x18000292c  shr     ecx, 3
0x18000292f  and     ecx, 1FFFFFFCh
0x180002935  imul    ecx, r11d
0x180002939  cmp     ecx, [r8+14h]
0x18000293d  ja      short loc_180002944
0x18000293f  mov     eax, r14d
0x180002942  jmp     short loc_180002946
0x180002944  xor     eax, eax
0x180002946  pop     r14
0x180002948  pop     rsi
0x180002949  pop     rbp
0x18000294a  retn
```
