# CS64_Modular

- ea: `0x180005af0`
- end: `0x180005da9`
- name: `CS64_Modular`
- size: `697`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005f7c`

## callees

- `0x18000583c`
- `0x1800059e8`
- `0x180005a54`
- `0x180005af0`

## pseudocode

```c
__int64 __fastcall CS64_Modular(int *a1, __int64 a2, int *a3, int *a4)
{
  int v5; // ecx
  __int16 v7; // r11
  __int16 v8; // r11d^2
  int v9; // ecx
  __int64 v10; // rax
  __int64 v11; // rbx
  _DWORD *v12; // r15
  __int64 v13; // rax
  __int64 v14; // rdi
  __int64 v15; // rbx
  int v16; // r13d
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rbx
  __int64 v20; // rax
  __int64 result; // rax
  int v22; // ecx
  __int64 v23; // [rsp+28h] [rbp-28h]
  __int64 v24; // [rsp+28h] [rbp-28h]
  __int64 v25; // [rsp+30h] [rbp-20h]
  __int64 v26; // [rsp+38h] [rbp-18h] BYREF
  __int64 v27; // [rsp+40h] [rbp-10h] BYREF
  __int64 v28; // [rsp+80h] [rbp+30h] BYREF
  __int64 v29; // [rsp+90h] [rbp+40h] BYREF
  unsigned __int64 v30; // [rsp+98h] [rbp+48h]

  LODWORD(v23) = 0;
  v5 = *a3;
  v30 = 0xA9C10E7900000000uLL;
  LODWORD(v28) = 0;
  WORD2(v28) = HIWORD(v5);
  HIWORD(v28) = v5;
  v27 = v28;
  CS64Mod(&v27);
  HIWORD(v28) = v7;
  LODWORD(v28) = 0;
  WORD2(v28) = v8;
  v26 = v28;
  CS64Mod(&v26);
  v9 = *a1;
  LODWORD(v28) = 0;
  v29 = 0xA4EB0F1000000000uLL;
  WORD2(v28) = HIWORD(v9);
  HIWORD(v28) = v9;
  v28 = CS64Mult(v30, v28);
  CS64Mod(&v28);
  v10 = CS64Mult(v27, v28);
  v28 = CS64Add(v10, v26);
  CS64Mod(&v28);
  v11 = CS64Add(0, v28);
  HIWORD(v23) = a1[1];
  WORD2(v23) = HIWORD(a1[1]);
  v28 = CS64Add(v28, v23);
  v12 = a1 + 2;
  CS64Mod(&v28);
  v13 = CS64Mult(0x8E3101A500000000uLL, v28);
  v28 = CS64Add(v13, v29);
  CS64Mod(&v28);
  v14 = v28;
  v15 = CS64Add(v11, v28);
  v16 = 3;
  do
  {
    LODWORD(v24) = 0;
    HIWORD(v24) = *v12;
    WORD2(v24) = HIWORD(*v12);
    v17 = CS64Mult(v30, v24);
    v28 = CS64Add(v17, v14);
    CS64Mod(&v28);
    v18 = CS64Mult(v27, v28);
    v28 = CS64Add(v18, v26);
    CS64Mod(&v28);
    v19 = CS64Add(v15, v28);
    HIWORD(v25) = v12[1];
    LODWORD(v25) = 0;
    WORD2(v25) = HIWORD(v12[1]);
    v28 = CS64Add(v28, v25);
    v12 += 2;
    CS64Mod(&v28);
    v20 = CS64Mult(0x8E3101A500000000uLL, v28);
    v28 = CS64Add(v20, v29);
    CS64Mod(&v28);
    v14 = v28;
    v15 = CS64Add(v19, v28);
    --v16;
  }
  while ( v16 );
  v28 = CS64Add(v14, v26);
  CS64Mod(&v28);
  v29 = CS64Add(v15, v29);
  CS64Mod(&v29);
  result = HIWORD(v29);
  v22 = HIWORD(v29) | (WORD2(v29) << 16);
  *a4 = HIWORD(v28) | (WORD2(v28) << 16);
  a4[1] = v22;
  return result;
}

```

## disassembly

```asm
0x180005af0  mov     [rsp-28h+arg_8], rbx
0x180005af5  push    rbp
0x180005af6  push    rdi
0x180005af7  push    r12
0x180005af9  push    r13
0x180005afb  push    r15
0x180005afd  mov     rbp, rsp
0x180005b00  sub     rsp, 50h
0x180005b04  mov     r11d, [r8+4]
0x180005b08  xor     eax, eax
0x180005b0a  mov     [rbp+var_28], rax
0x180005b0e  mov     r15, rcx
0x180005b11  mov     ecx, [r8]
0x180005b14  mov     r12, r9
0x180005b17  mov     dword ptr [rbp+arg_18], eax
0x180005b1a  mov     dword ptr [rbp+arg_0], eax
0x180005b1d  mov     eax, ecx
0x180005b1f  shr     eax, 10h
0x180005b22  mov     word ptr [rbp+arg_0+6], cx
0x180005b26  lea     rcx, [rbp+var_10]
0x180005b2a  mov     word ptr [rbp+arg_0+4], ax
0x180005b2e  mov     rax, [rbp+arg_0]
0x180005b32  mov     [rbp+var_10], rax
0x180005b36  mov     dword ptr [rbp+arg_18+4], 0A9C10E79h
0x180005b3d  call    CS64Mod
0x180005b42  xor     eax, eax
0x180005b44  mov     word ptr [rbp+arg_0+6], r11w
0x180005b49  mov     dword ptr [rbp+arg_0], eax
0x180005b4c  lea     rcx, [rbp+var_18]
0x180005b50  mov     eax, r11d
0x180005b53  shr     eax, 10h
0x180005b56  mov     word ptr [rbp+arg_0+4], ax
0x180005b5a  mov     rax, [rbp+arg_0]
0x180005b5e  mov     [rbp+var_18], rax
0x180005b62  call    CS64Mod
0x180005b67  mov     ecx, [r15]
0x180005b6a  xor     eax, eax
0x180005b6c  mov     dword ptr [rbp+arg_0], eax
0x180005b6f  xor     r11d, r11d
0x180005b72  mov     dword ptr [rbp+arg_10], eax
0x180005b75  mov     eax, ecx
0x180005b77  mov     word ptr [rbp+arg_0+6], cx
0x180005b7b  mov     rcx, [rbp+arg_18]
0x180005b7f  shr     eax, 10h
0x180005b82  mov     word ptr [rbp+arg_0+4], ax
0x180005b86  mov     rdx, [rbp+arg_0]
0x180005b8a  mov     dword ptr [rbp+var_30], r11d
0x180005b8e  mov     dword ptr [rbp+var_30+4], 8E3101A5h
0x180005b95  mov     dword ptr [rbp+arg_10+4], 0A4EB0F10h
0x180005b9c  call    CS64Mult
0x180005ba1  lea     rcx, [rbp+arg_0]
0x180005ba5  mov     [rbp+arg_0], rax
0x180005ba9  call    CS64Mod
0x180005bae  mov     rdx, [rbp+arg_0]
0x180005bb2  mov     rcx, [rbp+var_10]
0x180005bb6  call    CS64Mult
0x180005bbb  mov     rdx, [rbp+var_18]
0x180005bbf  mov     rcx, rax
0x180005bc2  call    CS64Add
0x180005bc7  lea     rcx, [rbp+arg_0]
0x180005bcb  mov     [rbp+arg_0], rax
0x180005bcf  call    CS64Mod
0x180005bd4  mov     rdx, [rbp+arg_0]
0x180005bd8  mov     rcx, [rbp+var_28]
0x180005bdc  call    CS64Add
0x180005be1  mov     ecx, [r15+4]
0x180005be5  mov     rbx, rax
0x180005be8  xor     eax, eax
0x180005bea  mov     word ptr [rbp+var_28+6], cx
0x180005bee  mov     dword ptr [rbp+var_28], eax
0x180005bf1  mov     eax, ecx
0x180005bf3  mov     rcx, [rbp+arg_0]
0x180005bf7  shr     eax, 10h
0x180005bfa  mov     word ptr [rbp+var_28+4], ax
0x180005bfe  mov     rdx, [rbp+var_28]
0x180005c02  call    CS64Add
0x180005c07  lea     rcx, [rbp+arg_0]
0x180005c0b  mov     [rbp+arg_0], rax
0x180005c0f  add     r15, 8
0x180005c13  call    CS64Mod
0x180005c18  mov     rdx, [rbp+arg_0]
0x180005c1c  mov     rcx, [rbp+var_30]
0x180005c20  call    CS64Mult
0x180005c25  mov     rdx, [rbp+arg_10]
0x180005c29  mov     rcx, rax
0x180005c2c  call    CS64Add
0x180005c31  lea     rcx, [rbp+arg_0]
0x180005c35  mov     [rbp+arg_0], rax
0x180005c39  call    CS64Mod
0x180005c3e  mov     rdi, [rbp+arg_0]
0x180005c42  mov     rcx, rbx
0x180005c45  mov     rdx, rdi
0x180005c48  call    CS64Add
0x180005c4d  mov     rbx, rax
0x180005c50  mov     r13d, 3
0x180005c56  mov     ecx, [r15]
0x180005c59  xor     eax, eax
0x180005c5b  mov     dword ptr [rbp+var_28], eax
0x180005c5e  mov     eax, ecx
0x180005c60  mov     word ptr [rbp+var_28+6], cx
0x180005c64  mov     rcx, [rbp+arg_18]
0x180005c68  shr     eax, 10h
0x180005c6b  mov     word ptr [rbp+var_28+4], ax
0x180005c6f  mov     rdx, [rbp+var_28]
0x180005c73  call    CS64Mult
0x180005c78  mov     rdx, rdi
0x180005c7b  mov     rcx, rax
0x180005c7e  call    CS64Add
0x180005c83  lea     rcx, [rbp+arg_0]
0x180005c87  mov     [rbp+arg_0], rax
0x180005c8b  call    CS64Mod
0x180005c90  mov     rdx, [rbp+arg_0]
0x180005c94  mov     rcx, [rbp+var_10]
0x180005c98  call    CS64Mult
0x180005c9d  mov     rdx, [rbp+var_18]
0x180005ca1  mov     rcx, rax
0x180005ca4  call    CS64Add
0x180005ca9  lea     rcx, [rbp+arg_0]
0x180005cad  mov     [rbp+arg_0], rax
0x180005cb1  call    CS64Mod
0x180005cb6  mov     rdx, [rbp+arg_0]
0x180005cba  mov     rcx, rbx
0x180005cbd  call    CS64Add
0x180005cc2  mov     ecx, [r15+4]
0x180005cc6  mov     rbx, rax
0x180005cc9  xor     eax, eax
0x180005ccb  mov     word ptr [rbp+var_20+6], cx
0x180005ccf  mov     dword ptr [rbp+var_20], eax
0x180005cd2  mov     eax, ecx
0x180005cd4  mov     rcx, [rbp+arg_0]
0x180005cd8  shr     eax, 10h
0x180005cdb  mov     word ptr [rbp+var_20+4], ax
0x180005cdf  mov     rdx, [rbp+var_20]
0x180005ce3  call    CS64Add
0x180005ce8  lea     rcx, [rbp+arg_0]
0x180005cec  mov     [rbp+arg_0], rax
0x180005cf0  lea     r15, [r15+8]
0x180005cf4  call    CS64Mod
0x180005cf9  mov     rdx, [rbp+arg_0]
0x180005cfd  mov     rcx, [rbp+var_30]
0x180005d01  call    CS64Mult
0x180005d06  mov     rdx, [rbp+arg_10]
0x180005d0a  mov     rcx, rax
0x180005d0d  call    CS64Add
0x180005d12  lea     rcx, [rbp+arg_0]
0x180005d16  mov     [rbp+arg_0], rax
0x180005d1a  call    CS64Mod
0x180005d1f  mov     rdi, [rbp+arg_0]
0x180005d23  mov     rcx, rbx
0x180005d26  mov     rdx, rdi
0x180005d29  call    CS64Add
0x180005d2e  mov     rbx, rax
0x180005d31  add     r13d, 0FFFFFFFFh
0x180005d35  jnz     loc_180005C56
0x180005d3b  mov     rdx, [rbp+var_18]
0x180005d3f  mov     rcx, rdi
0x180005d42  call    CS64Add
0x180005d47  lea     rcx, [rbp+arg_0]
0x180005d4b  mov     [rbp+arg_0], rax
0x180005d4f  call    CS64Mod
0x180005d54  mov     rdx, [rbp+arg_10]
0x180005d58  mov     rcx, rbx
0x180005d5b  call    CS64Add
0x180005d60  lea     rcx, [rbp+arg_10]
0x180005d64  mov     [rbp+arg_10], rax
0x180005d68  call    CS64Mod
0x180005d6d  movzx   eax, word ptr [rbp+arg_0+6]
0x180005d71  movzx   r11d, word ptr [rbp+arg_0+4]
0x180005d76  movzx   ecx, word ptr [rbp+arg_10+4]
0x180005d7a  mov     rbx, [rsp+50h+arg_8]
0x180005d82  shl     r11d, 10h
0x180005d86  or      r11d, eax
0x180005d89  shl     ecx, 10h
0x180005d8c  movzx   eax, word ptr [rbp+arg_10+6]
0x180005d90  or      ecx, eax
0x180005d92  mov     [r12], r11d
0x180005d96  mov     [r12+4], ecx
0x180005d9b  add     rsp, 50h
0x180005d9f  pop     r15
0x180005da1  pop     r13
0x180005da3  pop     r12
0x180005da5  pop     rdi
0x180005da6  pop     rbp
0x180005da7  retn
```
