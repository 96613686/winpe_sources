# DecompressFrame8

- ea: `0x180005ad0`
- end: `0x180005c1d`
- name: `DecompressFrame8`
- size: `333`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180004b04`
- `0x180005ad0`
- `0x180005d98`

## pseudocode

```c
__int64 __fastcall DecompressFrame8(_DWORD *a1, unsigned __int8 *a2, int a3, int a4, int a5, int a6)
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
  int v19[4]; // [rsp+30h] [rbp-38h] BYREF
  int v20; // [rsp+70h] [rbp+8h] BYREF
  int v21; // [rsp+78h] [rbp+10h] BYREF

  v6 = a1[1];
  v7 = a1[2];
  v19[0] = a1[5];
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
        a2 = DecompressCBlockTo8(v13, a2, v19, v12, &v20);
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
0x180005ad0  mov     [rsp+arg_10], rbx
0x180005ad5  mov     [rsp+arg_18], rbp
0x180005ada  push    rsi
0x180005adb  push    rdi
0x180005adc  push    r12
0x180005ade  push    r14
0x180005ae0  push    r15
0x180005ae2  sub     rsp, 40h
0x180005ae6  mov     eax, [rcx+14h]
0x180005ae9  mov     r11, r8
0x180005aec  mov     r14d, [rcx+4]
0x180005af0  mov     r10, r9
0x180005af3  mov     esi, [rcx+8]
0x180005af6  mov     r12, rdx
0x180005af9  mov     r8d, [rsp+68h+arg_20]
0x180005b01  mov     rdx, r10
0x180005b04  mov     r9d, [rsp+68h+arg_28]
0x180005b0c  mov     rcx, r11
0x180005b0f  mov     [rsp+68h+var_38], eax
0x180005b13  lea     rax, [rsp+68h+arg_8]
0x180005b18  mov     [rsp+68h+var_48], rax
0x180005b1d  mov     [rsp+68h+arg_0], 0
0x180005b25  mov     [rsp+68h+arg_8], 0
0x180005b2d  shr     r14d, 2
0x180005b31  call    DibXY
0x180005b36  shr     esi, 2
0x180005b39  mov     rbp, rax
0x180005b3c  test    esi, esi
0x180005b3e  jz      loc_180005C02
0x180005b44  mov     r15d, [rsp+68h+arg_8]
0x180005b49  dec     esi
0x180005b4b  mov     rdi, rbp
0x180005b4e  mov     ebx, r14d
0x180005b51  test    r14d, r14d
0x180005b54  jz      loc_180005BEC
0x180005b5a  lea     rax, [rsp+68h+arg_0]
0x180005b5f  mov     r9d, r15d
0x180005b62  lea     r8, [rsp+68h+var_38]
0x180005b67  mov     [rsp+68h+var_48], rax
0x180005b6c  mov     rdx, r12
0x180005b6f  mov     rcx, rdi
0x180005b72  dec     ebx
0x180005b74  call    DecompressCBlockTo8
0x180005b79  mov     r12, rax
0x180005b7c  mov     eax, [rsp+68h+arg_0]
0x180005b80  test    eax, eax
0x180005b82  jz      short loc_180005BE0
0x180005b84  sub     ebx, eax
0x180005b86  jns     short loc_180005BCB
0x180005b88  neg     ebx
0x180005b8a  mov     ecx, esi
0x180005b8c  lea     eax, [rbx-1]
0x180005b8f  cdq
0x180005b90  idiv    r14d
0x180005b93  inc     eax
0x180005b95  cmp     esi, eax
0x180005b97  cmovge  ecx, eax
0x180005b9a  mov     eax, ebx
0x180005b9c  sub     esi, ecx
0x180005b9e  cdq
0x180005b9f  imul    ecx, r15d
0x180005ba3  idiv    r14d
0x180005ba6  shl     ecx, 2
0x180005ba9  movsxd  rcx, ecx
0x180005bac  add     rbp, rcx
0x180005baf  test    edx, edx
0x180005bb1  jz      short loc_180005BC7
0x180005bb3  lea     eax, ds:0FFFFFFFFFFFFFFFCh[rdx*4]
0x180005bba  mov     ebx, r14d
0x180005bbd  movsxd  rdi, eax
0x180005bc0  add     rdi, rbp
0x180005bc3  sub     ebx, edx
0x180005bc5  jmp     short loc_180005BD8
0x180005bc7  xor     ebx, ebx
0x180005bc9  jmp     short loc_180005BD8
0x180005bcb  test    ebx, ebx
0x180005bcd  jz      short loc_180005BD8
0x180005bcf  shl     eax, 2
0x180005bd2  movsxd  rcx, eax
0x180005bd5  add     rdi, rcx
0x180005bd8  mov     [rsp+68h+arg_0], 0
0x180005be0  add     rdi, 4
0x180005be4  test    ebx, ebx
0x180005be6  jnz     loc_180005B5A
0x180005bec  lea     eax, ds:0[r15*4]
0x180005bf4  movsxd  rcx, eax
0x180005bf7  add     rbp, rcx
0x180005bfa  test    esi, esi
0x180005bfc  jnz     loc_180005B49
0x180005c02  lea     r11, [rsp+68h+var_28]
0x180005c07  xor     eax, eax
0x180005c09  mov     rbx, [r11+40h]
0x180005c0d  mov     rbp, [r11+48h]
0x180005c11  mov     rsp, r11
0x180005c14  pop     r15
0x180005c16  pop     r14
0x180005c18  pop     r12
0x180005c1a  pop     rdi
0x180005c1b  pop     rsi
0x180005c1c  retn
```
