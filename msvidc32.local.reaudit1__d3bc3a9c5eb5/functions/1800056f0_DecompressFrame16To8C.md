# DecompressFrame16To8C

- ea: `0x1800056f0`
- end: `0x180005858`
- name: `DecompressFrame16To8C`
- size: `360`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180003f30`
- `0x1800056f0`
- `0x180005d98`

## pseudocode

```c
__int64 __fastcall DecompressFrame16To8C(_DWORD *a1, __int16 *a2, int a3, int a4, int a5, int a6)
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
  v11 = DibXY(a3, a4, a5, a6, (__int64)&v21);
  if ( v10 )
  {
    v12 = v21;
    do
    {
      --v10;
      v13 = (int *)v11;
      for ( i = v9; i; ++v13 )
      {
        --i;
        a2 = DecompressCBlock16To8(v13, a2, v19, v12, &v20);
        if ( v20 )
        {
          i -= v20;
          if ( i >= 0 )
          {
            if ( i )
              v13 += v20;
          }
          else
          {
            v15 = -i;
            v16 = v10;
            if ( v10 >= (v15 - 1) / v9 + 1 )
              v16 = (v15 - 1) / v9 + 1;
            v10 -= v16;
            v17 = v15 % v9;
            v11 += 4 * v12 * v16;
            if ( v15 % v9 )
            {
              v13 = (int *)(v11 + 4 * v17 - 4);
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
      v11 += 4 * v12;
    }
    while ( v10 );
  }
  return 0;
}

```

## disassembly

```asm
0x1800056f0  mov     [rsp+arg_10], rbx
0x1800056f5  mov     [rsp+arg_18], rbp
0x1800056fa  push    rsi
0x1800056fb  push    rdi
0x1800056fc  push    r12
0x1800056fe  push    r14
0x180005700  push    r15
0x180005702  sub     rsp, 40h
0x180005706  mov     eax, [rcx+14h]
0x180005709  mov     r11, r8
0x18000570c  mov     r14d, [rcx+4]
0x180005710  mov     r10, r9
0x180005713  mov     esi, [rcx+8]
0x180005716  mov     r12, rdx
0x180005719  mov     r8d, [rsp+68h+arg_20]
0x180005721  mov     rdx, r10
0x180005724  mov     r9d, [rsp+68h+arg_28]
0x18000572c  mov     rcx, r11
0x18000572f  mov     [rsp+68h+var_38], eax
0x180005733  mov     rax, cs:lpDitherTable
0x18000573a  mov     cs:lpScale, rax
0x180005741  add     rax, 10000h
0x180005747  mov     cs:lpLookup, rax
0x18000574e  lea     rax, [rsp+68h+arg_8]
0x180005753  mov     [rsp+68h+var_48], rax
0x180005758  mov     [rsp+68h+arg_0], 0
0x180005760  mov     [rsp+68h+arg_8], 0
0x180005768  shr     r14d, 2
0x18000576c  call    DibXY
0x180005771  shr     esi, 2
0x180005774  mov     rbp, rax
0x180005777  test    esi, esi
0x180005779  jz      loc_18000583D
0x18000577f  mov     r15d, [rsp+68h+arg_8]
0x180005784  dec     esi
0x180005786  mov     rdi, rbp
0x180005789  mov     ebx, r14d
0x18000578c  test    r14d, r14d
0x18000578f  jz      loc_180005827
0x180005795  lea     rax, [rsp+68h+arg_0]
0x18000579a  mov     r9d, r15d
0x18000579d  lea     r8, [rsp+68h+var_38]
0x1800057a2  mov     [rsp+68h+var_48], rax
0x1800057a7  mov     rdx, r12
0x1800057aa  mov     rcx, rdi
0x1800057ad  dec     ebx
0x1800057af  call    DecompressCBlock16To8
0x1800057b4  mov     r12, rax
0x1800057b7  mov     eax, [rsp+68h+arg_0]
0x1800057bb  test    eax, eax
0x1800057bd  jz      short loc_18000581B
0x1800057bf  sub     ebx, eax
0x1800057c1  jns     short loc_180005806
0x1800057c3  neg     ebx
0x1800057c5  mov     ecx, esi
0x1800057c7  lea     eax, [rbx-1]
0x1800057ca  cdq
0x1800057cb  idiv    r14d
0x1800057ce  inc     eax
0x1800057d0  cmp     esi, eax
0x1800057d2  cmovge  ecx, eax
0x1800057d5  mov     eax, ebx
0x1800057d7  sub     esi, ecx
0x1800057d9  cdq
0x1800057da  imul    ecx, r15d
0x1800057de  idiv    r14d
0x1800057e1  shl     ecx, 2
0x1800057e4  movsxd  rcx, ecx
0x1800057e7  add     rbp, rcx
0x1800057ea  test    edx, edx
0x1800057ec  jz      short loc_180005802
0x1800057ee  lea     eax, ds:0FFFFFFFFFFFFFFFCh[rdx*4]
0x1800057f5  mov     ebx, r14d
0x1800057f8  movsxd  rdi, eax
0x1800057fb  add     rdi, rbp
0x1800057fe  sub     ebx, edx
0x180005800  jmp     short loc_180005813
0x180005802  xor     ebx, ebx
0x180005804  jmp     short loc_180005813
0x180005806  test    ebx, ebx
0x180005808  jz      short loc_180005813
0x18000580a  shl     eax, 2
0x18000580d  movsxd  rcx, eax
0x180005810  add     rdi, rcx
0x180005813  mov     [rsp+68h+arg_0], 0
0x18000581b  add     rdi, 4
0x18000581f  test    ebx, ebx
0x180005821  jnz     loc_180005795
0x180005827  lea     eax, ds:0[r15*4]
0x18000582f  movsxd  rcx, eax
0x180005832  add     rbp, rcx
0x180005835  test    esi, esi
0x180005837  jnz     loc_180005784
0x18000583d  lea     r11, [rsp+68h+var_28]
0x180005842  xor     eax, eax
0x180005844  mov     rbx, [r11+40h]
0x180005848  mov     rbp, [r11+48h]
0x18000584c  mov     rsp, r11
0x18000584f  pop     r15
0x180005851  pop     r14
0x180005853  pop     r12
0x180005855  pop     rdi
0x180005856  pop     rsi
0x180005857  retn
```
