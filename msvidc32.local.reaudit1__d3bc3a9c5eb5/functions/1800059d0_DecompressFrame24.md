# DecompressFrame24

- ea: `0x1800059d0`
- end: `0x180005ac2`
- name: `DecompressFrame24`
- size: `242`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180005184`
- `0x1800059d0`
- `0x180005d98`

## pseudocode

```c
__int64 __fastcall DecompressFrame24(_DWORD *a1, __int16 *a2, int a3, int a4, int a5, int a6)
{
  unsigned int v6; // r12d
  unsigned int v7; // r15d
  signed int v9; // r12d
  signed int v10; // r15d
  __int64 v11; // rax
  int v12; // ebx
  int v13; // r14d
  __int64 v14; // rbp
  int v15; // esi
  __int64 v16; // rdi
  __int16 *v17; // rax
  unsigned int v19[18]; // [rsp+30h] [rbp-48h] BYREF
  int v20; // [rsp+80h] [rbp+8h] BYREF
  int v21; // [rsp+88h] [rbp+10h] BYREF

  v6 = a1[1];
  v7 = a1[2];
  v19[0] = a1[5];
  v20 = 0;
  v21 = 0;
  v9 = v6 >> 2;
  v10 = v7 >> 2;
  v11 = DibXY(a3, a4, a5, a6, (__int64)&v20);
  v12 = v20;
  v13 = 0;
  v14 = v11;
  if ( v10 )
  {
    do
    {
      v15 = 0;
      v16 = v14;
      if ( v9 )
      {
        do
        {
          v17 = DecompressCBlockToRGBTRIPLE(v16, a2, v19, v12, &v21);
          ++v15;
          v16 += 12;
          a2 = v17;
        }
        while ( v15 < v9 );
      }
      ++v13;
      v14 += 4 * v12;
    }
    while ( v13 < v10 );
  }
  return (unsigned int)(4 * v10 * v12);
}

```

## disassembly

```asm
0x1800059d0  mov     [rsp+arg_10], rbx
0x1800059d5  push    rbp
0x1800059d6  push    rsi
0x1800059d7  push    rdi
0x1800059d8  push    r12
0x1800059da  push    r13
0x1800059dc  push    r14
0x1800059de  push    r15
0x1800059e0  sub     rsp, 40h
0x1800059e4  mov     eax, [rcx+14h]
0x1800059e7  mov     r11, r8
0x1800059ea  mov     r12d, [rcx+4]
0x1800059ee  mov     r10, r9
0x1800059f1  mov     r15d, [rcx+8]
0x1800059f5  mov     r13, rdx
0x1800059f8  mov     r8d, [rsp+78h+arg_20]
0x180005a00  mov     rdx, r10
0x180005a03  mov     r9d, [rsp+78h+arg_28]
0x180005a0b  mov     rcx, r11
0x180005a0e  mov     [rsp+78h+var_48], eax
0x180005a12  lea     rax, [rsp+78h+arg_0]
0x180005a1a  mov     [rsp+78h+var_58], rax
0x180005a1f  mov     [rsp+78h+arg_0], 0
0x180005a2a  mov     [rsp+78h+arg_8], 0
0x180005a35  shr     r12d, 2
0x180005a39  shr     r15d, 2
0x180005a3d  call    DibXY
0x180005a42  mov     ebx, [rsp+78h+arg_0]
0x180005a49  xor     r14d, r14d
0x180005a4c  mov     rbp, rax
0x180005a4f  test    r15d, r15d
0x180005a52  jz      short loc_180005AA1
0x180005a54  xor     esi, esi
0x180005a56  mov     rdi, rbp
0x180005a59  test    r12d, r12d
0x180005a5c  jz      short loc_180005A8C
0x180005a5e  lea     rax, [rsp+78h+arg_8]
0x180005a66  mov     r9d, ebx
0x180005a69  lea     r8, [rsp+78h+var_48]
0x180005a6e  mov     [rsp+78h+var_58], rax
0x180005a73  mov     rdx, r13
0x180005a76  mov     rcx, rdi
0x180005a79  call    DecompressCBlockToRGBTRIPLE
0x180005a7e  inc     esi
0x180005a80  add     rdi, 0Ch
0x180005a84  mov     r13, rax
0x180005a87  cmp     esi, r12d
0x180005a8a  jl      short loc_180005A5E
0x180005a8c  lea     ecx, ds:0[rbx*4]
0x180005a93  inc     r14d
0x180005a96  movsxd  rdx, ecx
0x180005a99  add     rbp, rdx
0x180005a9c  cmp     r14d, r15d
0x180005a9f  jl      short loc_180005A54
0x180005aa1  imul    ebx, r15d
0x180005aa5  shl     ebx, 2
0x180005aa8  mov     eax, ebx
0x180005aaa  mov     rbx, [rsp+78h+arg_10]
0x180005ab2  add     rsp, 40h
0x180005ab6  pop     r15
0x180005ab8  pop     r14
0x180005aba  pop     r13
0x180005abc  pop     r12
0x180005abe  pop     rdi
0x180005abf  pop     rsi
0x180005ac0  pop     rbp
0x180005ac1  retn
```
