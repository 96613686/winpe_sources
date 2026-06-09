# DecompressFrame16To8X2C

- ea: `0x180005860`
- end: `0x1800059c8`
- name: `DecompressFrame16To8X2C`
- size: `360`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000450c`
- `0x180005860`
- `0x180005d98`

## pseudocode

```c
__int64 __fastcall DecompressFrame16To8X2C(_DWORD *a1, unsigned __int16 *a2, __int64 a3, __int64 a4, int a5, int a6)
{
  unsigned int v6; // r14d
  unsigned int v7; // esi
  int v9; // r14d
  int v10; // esi
  __int64 v11; // rbp
  int v12; // r15d
  int *v13; // rdi
  int i; // ebx
  int v15; // ebx
  int v16; // ecx
  int v17; // edx
  unsigned int v19[4]; // [rsp+30h] [rbp-38h] BYREF
  int v20; // [rsp+70h] [rbp+8h] BYREF
  int v21; // [rsp+78h] [rbp+10h] BYREF

  v6 = a1[1];
  v7 = a1[2];
  v19[0] = a1[5];
  lpScale = (__int64)lpDitherTable;
  lpLookup = (__int64)lpDitherTable + 0x10000;
  v20 = 0;
  v21 = 0;
  v9 = v6 >> 2;
  v10 = v7 >> 2;
  v11 = DibXY(a3, a4, a5, a6, (unsigned int *)&v21);
  if ( v10 )
  {
    v12 = v21;
    do
    {
      --v10;
      v13 = (int *)v11;
      for ( i = v9; i; v13 += 2 )
      {
        --i;
        a2 = DecompressCBlock16To8X2(v13, a2, v19, v12, &v20);
        if ( v20 )
        {
          i -= v20;
          if ( i >= 0 )
          {
            if ( i )
              v13 += 2 * v20;
          }
          else
          {
            v15 = -i;
            v16 = v10;
            if ( v10 >= (v15 - 1) / v9 + 1 )
              v16 = (v15 - 1) / v9 + 1;
            v10 -= v16;
            v17 = v15 % v9;
            v11 += 8 * v12 * v16;
            if ( v15 % v9 )
            {
              v13 = (int *)(v11 + 8 * v17 - 8);
              i = v9 - v17;
            }
            else
            {
              i = 0;
            }
          }
          v20 = 0;
        }
      }
      v11 += 8 * v12;
    }
    while ( v10 );
  }
  return 0;
}

```

## disassembly

```asm
0x180005860  mov     [rsp+arg_10], rbx
0x180005865  mov     [rsp+arg_18], rbp
0x18000586a  push    rsi
0x18000586b  push    rdi
0x18000586c  push    r12
0x18000586e  push    r14
0x180005870  push    r15
0x180005872  sub     rsp, 40h
0x180005876  mov     eax, [rcx+14h]
0x180005879  mov     r11, r8
0x18000587c  mov     r14d, [rcx+4]
0x180005880  mov     r10, r9
0x180005883  mov     esi, [rcx+8]
0x180005886  mov     r12, rdx
0x180005889  mov     r8d, [rsp+68h+arg_20]
0x180005891  mov     rdx, r10
0x180005894  mov     r9d, [rsp+68h+arg_28]
0x18000589c  mov     rcx, r11
0x18000589f  mov     [rsp+68h+var_38], eax
0x1800058a3  mov     rax, cs:lpDitherTable
0x1800058aa  mov     cs:lpScale, rax
0x1800058b1  add     rax, 10000h
0x1800058b7  mov     cs:lpLookup, rax
0x1800058be  lea     rax, [rsp+68h+arg_8]
0x1800058c3  mov     [rsp+68h+var_48], rax
0x1800058c8  mov     [rsp+68h+arg_0], 0
0x1800058d0  mov     [rsp+68h+arg_8], 0
0x1800058d8  shr     r14d, 2
0x1800058dc  call    DibXY
0x1800058e1  shr     esi, 2
0x1800058e4  mov     rbp, rax
0x1800058e7  test    esi, esi
0x1800058e9  jz      loc_1800059AD
0x1800058ef  mov     r15d, [rsp+68h+arg_8]
0x1800058f4  dec     esi
0x1800058f6  mov     rdi, rbp
0x1800058f9  mov     ebx, r14d
0x1800058fc  test    r14d, r14d
0x1800058ff  jz      loc_180005997
0x180005905  lea     rax, [rsp+68h+arg_0]
0x18000590a  mov     r9d, r15d
0x18000590d  lea     r8, [rsp+68h+var_38]
0x180005912  mov     [rsp+68h+var_48], rax
0x180005917  mov     rdx, r12
0x18000591a  mov     rcx, rdi
0x18000591d  dec     ebx
0x18000591f  call    DecompressCBlock16To8X2
0x180005924  mov     r12, rax
0x180005927  mov     eax, [rsp+68h+arg_0]
0x18000592b  test    eax, eax
0x18000592d  jz      short loc_18000598B
0x18000592f  sub     ebx, eax
0x180005931  jns     short loc_180005976
0x180005933  neg     ebx
0x180005935  mov     ecx, esi
0x180005937  lea     eax, [rbx-1]
0x18000593a  cdq
0x18000593b  idiv    r14d
0x18000593e  inc     eax
0x180005940  cmp     esi, eax
0x180005942  cmovge  ecx, eax
0x180005945  mov     eax, ebx
0x180005947  sub     esi, ecx
0x180005949  cdq
0x18000594a  imul    ecx, r15d
0x18000594e  idiv    r14d
0x180005951  shl     ecx, 3
0x180005954  movsxd  rcx, ecx
0x180005957  add     rbp, rcx
0x18000595a  test    edx, edx
0x18000595c  jz      short loc_180005972
0x18000595e  lea     eax, ds:0FFFFFFFFFFFFFFF8h[rdx*8]
0x180005965  mov     ebx, r14d
0x180005968  movsxd  rdi, eax
0x18000596b  add     rdi, rbp
0x18000596e  sub     ebx, edx
0x180005970  jmp     short loc_180005983
0x180005972  xor     ebx, ebx
0x180005974  jmp     short loc_180005983
0x180005976  test    ebx, ebx
0x180005978  jz      short loc_180005983
0x18000597a  shl     eax, 3
0x18000597d  movsxd  rcx, eax
0x180005980  add     rdi, rcx
0x180005983  mov     [rsp+68h+arg_0], 0
0x18000598b  add     rdi, 8
0x18000598f  test    ebx, ebx
0x180005991  jnz     loc_180005905
0x180005997  lea     eax, ds:0[r15*8]
0x18000599f  movsxd  rcx, eax
0x1800059a2  add     rbp, rcx
0x1800059a5  test    esi, esi
0x1800059a7  jnz     loc_1800058F4
0x1800059ad  lea     r11, [rsp+68h+var_28]
0x1800059b2  xor     eax, eax
0x1800059b4  mov     rbx, [r11+40h]
0x1800059b8  mov     rbp, [r11+48h]
0x1800059bc  mov     rsp, r11
0x1800059bf  pop     r15
0x1800059c1  pop     r14
0x1800059c3  pop     r12
0x1800059c5  pop     rdi
0x1800059c6  pop     rsi
0x1800059c7  retn
```
