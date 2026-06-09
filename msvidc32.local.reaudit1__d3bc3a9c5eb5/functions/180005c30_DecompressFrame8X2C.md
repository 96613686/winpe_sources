# DecompressFrame8X2C

- ea: `0x180005c30`
- end: `0x180005d8f`
- name: `DecompressFrame8X2C`
- size: `351`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180004dbc`
- `0x180005c30`
- `0x180005d98`

## pseudocode

```c
__int64 __fastcall DecompressFrame8X2C(int *a1, unsigned __int8 *a2, int a3, int a4, int a5, int a6)
{
  __int64 v7; // kr00_8
  int v9; // r14d
  __int64 v10; // rsi
  int v11; // ebp
  int v12; // r15d
  int *v13; // rdi
  int v14; // ebx
  int v15; // ebx
  int v16; // ecx
  int v17; // edx
  int v19[4]; // [rsp+30h] [rbp-38h] BYREF
  int v20; // [rsp+70h] [rbp+8h] BYREF
  int v21; // [rsp+78h] [rbp+10h] BYREF

  v19[0] = a1[5];
  v7 = a1[1];
  v20 = 0;
  v21 = 0;
  v9 = ((BYTE4(v7) & 3) + (int)v7) >> 2;
  v10 = DibXY(a3, a4, a5, a6, (__int64)&v21);
  v11 = a1[2] / 4;
  if ( v11 )
  {
    v12 = v21;
    do
    {
      --v11;
      v13 = (int *)v10;
      v14 = ((BYTE4(v7) & 3) + (int)v7) >> 2;
      if ( v9 )
      {
        do
        {
          --v14;
          a2 = DecompressCBlockTo8X2(v13, a2, v19, v12, &v20);
          if ( v20 )
          {
            v14 -= v20;
            if ( v14 >= 0 )
            {
              if ( v14 )
                v13 += 2 * v20;
            }
            else
            {
              v15 = -v14;
              v16 = v11;
              if ( v11 >= (v15 - 1) / v9 + 1 )
                v16 = (v15 - 1) / v9 + 1;
              v11 -= v16;
              v17 = v15 % v9;
              v10 += 8 * v12 * v16;
              if ( v15 % v9 )
              {
                v13 = (int *)(v10 + 8 * v17 - 8);
                v14 = v9 - v17;
              }
              else
              {
                v14 = 0;
              }
            }
            v20 = 0;
          }
          v13 += 2;
        }
        while ( v14 );
      }
      v10 += 8 * v12;
    }
    while ( v11 );
  }
  return 0;
}

```

## disassembly

```asm
0x180005c30  mov     [rsp+arg_10], rbx
0x180005c35  mov     [rsp+arg_18], rbp
0x180005c3a  push    rsi
0x180005c3b  push    rdi
0x180005c3c  push    r12
0x180005c3e  push    r14
0x180005c40  push    r15
0x180005c42  sub     rsp, 40h
0x180005c46  mov     eax, [rcx+14h]
0x180005c49  mov     r12, rdx
0x180005c4c  mov     [rsp+68h+var_38], eax
0x180005c50  mov     r11, r8
0x180005c53  mov     eax, [rcx+4]
0x180005c56  mov     r10, r9
0x180005c59  mov     r8d, [rsp+68h+arg_20]
0x180005c61  cdq
0x180005c62  mov     r9d, [rsp+68h+arg_28]
0x180005c6a  and     edx, 3
0x180005c6d  mov     rbx, rcx
0x180005c70  mov     [rsp+68h+arg_0], 0
0x180005c78  mov     rcx, r11
0x180005c7b  mov     [rsp+68h+arg_8], 0
0x180005c83  lea     r14d, [rdx+rax]
0x180005c87  mov     rdx, r10
0x180005c8a  lea     rax, [rsp+68h+arg_8]
0x180005c8f  sar     r14d, 2
0x180005c93  mov     [rsp+68h+var_48], rax
0x180005c98  call    DibXY
0x180005c9d  mov     rsi, rax
0x180005ca0  mov     eax, [rbx+8]
0x180005ca3  cdq
0x180005ca4  and     edx, 3
0x180005ca7  add     eax, edx
0x180005ca9  sar     eax, 2
0x180005cac  mov     ebp, eax
0x180005cae  test    eax, eax
0x180005cb0  jz      loc_180005D74
0x180005cb6  mov     r15d, [rsp+68h+arg_8]
0x180005cbb  dec     ebp
0x180005cbd  mov     rdi, rsi
0x180005cc0  mov     ebx, r14d
0x180005cc3  test    r14d, r14d
0x180005cc6  jz      loc_180005D5E
0x180005ccc  lea     rax, [rsp+68h+arg_0]
0x180005cd1  mov     r9d, r15d
0x180005cd4  lea     r8, [rsp+68h+var_38]
0x180005cd9  mov     [rsp+68h+var_48], rax
0x180005cde  mov     rdx, r12
0x180005ce1  mov     rcx, rdi
0x180005ce4  dec     ebx
0x180005ce6  call    DecompressCBlockTo8X2
0x180005ceb  mov     r12, rax
0x180005cee  mov     eax, [rsp+68h+arg_0]
0x180005cf2  test    eax, eax
0x180005cf4  jz      short loc_180005D52
0x180005cf6  sub     ebx, eax
0x180005cf8  jns     short loc_180005D3D
0x180005cfa  neg     ebx
0x180005cfc  mov     ecx, ebp
0x180005cfe  lea     eax, [rbx-1]
0x180005d01  cdq
0x180005d02  idiv    r14d
0x180005d05  inc     eax
0x180005d07  cmp     ebp, eax
0x180005d09  cmovge  ecx, eax
0x180005d0c  mov     eax, ebx
0x180005d0e  sub     ebp, ecx
0x180005d10  cdq
0x180005d11  imul    ecx, r15d
0x180005d15  idiv    r14d
0x180005d18  shl     ecx, 3
0x180005d1b  movsxd  rcx, ecx
0x180005d1e  add     rsi, rcx
0x180005d21  test    edx, edx
0x180005d23  jz      short loc_180005D39
0x180005d25  lea     eax, ds:0FFFFFFFFFFFFFFF8h[rdx*8]
0x180005d2c  mov     ebx, r14d
0x180005d2f  movsxd  rdi, eax
0x180005d32  add     rdi, rsi
0x180005d35  sub     ebx, edx
0x180005d37  jmp     short loc_180005D4A
0x180005d39  xor     ebx, ebx
0x180005d3b  jmp     short loc_180005D4A
0x180005d3d  test    ebx, ebx
0x180005d3f  jz      short loc_180005D4A
0x180005d41  shl     eax, 3
0x180005d44  movsxd  rcx, eax
0x180005d47  add     rdi, rcx
0x180005d4a  mov     [rsp+68h+arg_0], 0
0x180005d52  add     rdi, 8
0x180005d56  test    ebx, ebx
0x180005d58  jnz     loc_180005CCC
0x180005d5e  lea     eax, ds:0[r15*8]
0x180005d66  movsxd  rcx, eax
0x180005d69  add     rsi, rcx
0x180005d6c  test    ebp, ebp
0x180005d6e  jnz     loc_180005CBB
0x180005d74  lea     r11, [rsp+68h+var_28]
0x180005d79  xor     eax, eax
0x180005d7b  mov     rbx, [r11+40h]
0x180005d7f  mov     rbp, [r11+48h]
0x180005d83  mov     rsp, r11
0x180005d86  pop     r15
0x180005d88  pop     r14
0x180005d8a  pop     r12
0x180005d8c  pop     rdi
0x180005d8d  pop     rsi
0x180005d8e  retn
```
