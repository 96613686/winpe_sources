# UYVYToRGB8

- ea: `0x180003e88`
- end: `0x1800046f4`
- name: `UYVYToRGB8`
- size: `2156`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000208c`

## callees

- `0x180003e88`

## pseudocode

```c
__int64 __fastcall UYVYToRGB8(__int64 a1, int *a2, char *a3, __int64 a4, _WORD *a5)
{
  unsigned __int64 v5; // r13
  char *v6; // r14
  int *v7; // r11
  unsigned __int64 v8; // rbp
  int v9; // esi
  unsigned __int64 v11; // r8
  char *v12; // r15
  unsigned __int64 v13; // rdx
  __int64 result; // rax
  __int64 v15; // rcx
  char *v16; // r12
  _WORD *v17; // rbx
  _WORD *v18; // rdi
  unsigned int v19; // r8d
  unsigned int v20; // r10d
  unsigned int v21; // r11d
  int v22; // r14d
  int v23; // r8d
  unsigned int v24; // r9d
  unsigned __int64 v25; // rax
  unsigned int v26; // r9d
  unsigned int v27; // r11d
  __int64 v28; // rdx
  unsigned int v29; // r8d
  unsigned int v30; // r10d
  unsigned int v31; // r11d
  int v32; // r14d
  int v33; // edx
  unsigned int v34; // r11d
  __int64 v35; // r9
  unsigned int v36; // eax
  unsigned int v37; // r11d
  __int64 v38; // rdx
  unsigned int v39; // r8d
  unsigned int v40; // r10d
  unsigned int v41; // r11d
  int v42; // r14d
  unsigned int v43; // r10d
  unsigned int v44; // r8d
  unsigned int v45; // r9d
  unsigned int v46; // r11d
  __int64 v47; // rdx
  unsigned __int64 v48; // [rsp+0h] [rbp-78h]
  unsigned __int64 v49; // [rsp+8h] [rbp-70h]
  unsigned __int64 v50; // [rsp+8h] [rbp-70h]
  __int64 v51; // [rsp+10h] [rbp-68h]
  unsigned __int64 v52; // [rsp+20h] [rbp-58h]
  unsigned __int64 v53; // [rsp+20h] [rbp-58h]
  unsigned __int64 v54; // [rsp+20h] [rbp-58h]
  int v55; // [rsp+80h] [rbp+8h]
  __int64 v58; // [rsp+98h] [rbp+20h]

  v58 = a4;
  v5 = a2[1];
  v6 = a3;
  v7 = a2;
  v8 = (unsigned __int64)a5;
  v9 = -a2[2];
  v11 = v5;
  if ( a2[2] > 0 )
    v9 = a2[2];
  v12 = v6;
  v13 = v5 >> 1;
  v55 = 3 * (v5 >> 1);
  result = (int)((unsigned __int64)(2 * (int)v5) >> 2);
  v15 = 4 * result;
  v51 = 4 * result;
  v16 = &v6[4 * result];
  if ( *(int *)(a4 + 8) < 0 )
  {
    v17 = a5;
  }
  else
  {
    v17 = (_WORD *)((char *)a5 + (int)v5 * (v9 - 1));
    result = (unsigned int)(v5 * (v9 - 2));
    v11 = (int)result;
  }
  v18 = (_WORD *)((char *)a5 + v11);
  if ( *(_DWORD *)(a1 + 4) == 1498831189 )
  {
    if ( v9 > 1 )
    {
      v19 = (unsigned int)v5 >> 2;
      while ( 1 )
      {
        v20 = 8 * v19;
        if ( v6 > v12 )
          break;
        if ( v7[5] < v20 )
          break;
        result = v12 - v6;
        v52 = v7[5] - v20;
        if ( v12 - v6 > v52 )
          break;
        v21 = 4 * v19;
        if ( v8 > (unsigned __int64)v17 )
          break;
        if ( *(_DWORD *)(a4 + 20) < v21 )
          break;
        v48 = *(_DWORD *)(a4 + 20) - v21;
        result = (__int64)v17 - v8;
        if ( (unsigned __int64)v17 - v8 > v48 )
          break;
        if ( v6 > v16 )
          break;
        result = (__int64)a2;
        if ( a2[5] < v20 )
          break;
        result = v16 - v6;
        if ( v16 - v6 > v52 )
          break;
        if ( v8 > (unsigned __int64)v18 )
          break;
        if ( *(_DWORD *)(a4 + 20) < v21 )
          break;
        result = (__int64)v18 - v8;
        if ( (unsigned __int64)v18 - v8 > v48 )
          break;
        if ( (int)v5 > 3 )
        {
          v22 = v5;
          do
          {
            v23 = *(_DWORD *)v12;
            v22 -= 4;
            v24 = *((_DWORD *)v12 + 1);
            v25 = (unsigned __int64)*(unsigned int *)v12 >> 24;
            v12 += 8;
            *v17 = cLUT_B0[2 * (unsigned __int8)v23]
                 | word_180006388[2 * BYTE1(v23)]
                 | cLUT_R0[2 * BYTE2(v23)]
                 | word_180006FC8[2 * v25];
            v17[1] = word_1800067B0[2 * (unsigned __int8)v24]
                   | word_180006380[2 * BYTE1(v24)]
                   | yLUT_1[2 * ((unsigned __int64)v24 >> 24)]
                   | word_180006BC0[2 * BYTE2(v24)];
            v17 += 2;
            v26 = *(_DWORD *)v16;
            v27 = *((_DWORD *)v16 + 1);
            v28 = (unsigned __int8)BYTE1(*(_DWORD *)v16);
            v16 += 8;
            *v18 = yLUT_1[2 * HIBYTE(v26)]
                 | word_1800067B0[2 * (unsigned __int8)v26]
                 | word_180006BC0[2 * BYTE2(v26)]
                 | word_180006380[2 * v28];
            v18[1] = cLUT_B0[2 * (unsigned __int8)v27]
                   | word_180006388[2 * BYTE1(v27)]
                   | cLUT_R0[2 * BYTE2(v27)]
                   | word_180006FC8[2 * ((unsigned __int64)v27 >> 24)];
            v18 += 2;
          }
          while ( v22 > 3 );
          v8 = (unsigned __int64)a5;
          v6 = a3;
          v15 = v51;
          a4 = v58;
          v13 = v5 >> 1;
          v19 = (unsigned int)v5 >> 2;
        }
        if ( *(int *)(a4 + 8) < 0 )
        {
          result = 2LL * (int)v13;
          v17 = (_WORD *)((char *)v17 + result);
          v18 = (_WORD *)((char *)v18 + result);
        }
        else
        {
          result = 2LL * v55;
          v17 = (_WORD *)((char *)v17 - result);
          v18 = (_WORD *)((char *)v18 - result);
        }
        v9 -= 2;
        if ( v9 <= 1 )
          break;
        v7 = a2;
        v12 += v15;
        v16 += v15;
      }
    }
  }
  else if ( *(_DWORD *)(a1 + 4) == 844715353 )
  {
    if ( v9 > 1 )
    {
      v29 = (unsigned int)v5 >> 2;
      while ( 1 )
      {
        v30 = 8 * v29;
        if ( v6 > v12 )
          break;
        if ( v7[5] < v30 )
          break;
        result = v12 - v6;
        v53 = v7[5] - v30;
        if ( v12 - v6 > v53 )
          break;
        v31 = 4 * v29;
        if ( v8 > (unsigned __int64)v17 )
          break;
        if ( *(_DWORD *)(a4 + 20) < v31 )
          break;
        v49 = *(_DWORD *)(a4 + 20) - v31;
        result = (__int64)v17 - v8;
        if ( (unsigned __int64)v17 - v8 > v49 )
          break;
        if ( v6 > v16 )
          break;
        result = (__int64)a2;
        if ( a2[5] < v30 )
          break;
        result = v16 - v6;
        if ( v16 - v6 > v53 )
          break;
        if ( v8 > (unsigned __int64)v18 )
          break;
        if ( *(_DWORD *)(a4 + 20) < v31 )
          break;
        result = (__int64)v18 - v8;
        if ( (unsigned __int64)v18 - v8 > v49 )
          break;
        if ( (int)v5 > 3 )
        {
          v32 = v5;
          do
          {
            v33 = *(_DWORD *)v12;
            v32 -= 4;
            v34 = *((_DWORD *)v12 + 1);
            v35 = HIBYTE(*(_DWORD *)v12);
            v36 = HIWORD(*(_DWORD *)v12);
            v12 += 8;
            *v17 = word_180006FC8[2 * (unsigned __int8)v36]
                 | cLUT_R0[2 * v35]
                 | word_180006388[2 * (unsigned __int8)v33]
                 | cLUT_B0[2 * BYTE1(v33)];
            v17[1] = word_180006380[2 * (unsigned __int8)v34]
                   | yLUT_1[2 * BYTE2(v34)]
                   | word_1800067B0[2 * BYTE1(v34)]
                   | word_180006BC0[2 * ((unsigned __int64)v34 >> 24)];
            v17 += 2;
            LODWORD(v35) = *(_DWORD *)v16;
            v37 = *((_DWORD *)v16 + 1);
            v38 = (unsigned __int8)BYTE1(*(_DWORD *)v16);
            v16 += 8;
            *v18 = word_180006BC0[2 * BYTE3(v35)]
                 | word_180006380[2 * (unsigned __int8)v35]
                 | word_1800067B0[2 * v38]
                 | yLUT_1[2 * BYTE2(v35)];
            v18[1] = word_180006388[2 * (unsigned __int8)v37]
                   | cLUT_B0[2 * BYTE1(v37)]
                   | word_180006FC8[2 * BYTE2(v37)]
                   | cLUT_R0[2 * ((unsigned __int64)v37 >> 24)];
            v18 += 2;
          }
          while ( v32 > 3 );
          v8 = (unsigned __int64)a5;
          v6 = a3;
          v15 = v51;
          a4 = v58;
          v13 = v5 >> 1;
          v29 = (unsigned int)v5 >> 2;
        }
        if ( *(int *)(a4 + 8) < 0 )
        {
          result = 2LL * (int)v13;
          v17 = (_WORD *)((char *)v17 + result);
          v18 = (_WORD *)((char *)v18 + result);
        }
        else
        {
          result = 2LL * v55;
          v17 = (_WORD *)((char *)v17 - result);
          v18 = (_WORD *)((char *)v18 - result);
        }
        v9 -= 2;
        if ( v9 <= 1 )
          break;
        v7 = a2;
        v12 += v15;
        v16 += v15;
      }
    }
  }
  else if ( *(_DWORD *)(a1 + 4) == 1431918169 && v9 > 1 )
  {
    v39 = (unsigned int)v5 >> 2;
    while ( 1 )
    {
      v40 = 8 * v39;
      if ( v6 > v12 )
        break;
      if ( v7[5] < v40 )
        break;
      result = v12 - v6;
      v54 = v7[5] - v40;
      if ( v12 - v6 > v54 )
        break;
      v41 = 4 * v39;
      if ( v8 > (unsigned __int64)v17 )
        break;
      if ( *(_DWORD *)(a4 + 20) < v41 )
        break;
      v50 = *(_DWORD *)(a4 + 20) - v41;
      result = (__int64)v17 - v8;
      if ( (unsigned __int64)v17 - v8 > v50 )
        break;
      if ( v6 > v16 )
        break;
      result = (__int64)a2;
      if ( a2[5] < v40 )
        break;
      result = v16 - v6;
      if ( v16 - v6 > v54 )
        break;
      if ( v8 > (unsigned __int64)v18 )
        break;
      if ( *(_DWORD *)(a4 + 20) < v41 )
        break;
      result = (__int64)v18 - v8;
      if ( (unsigned __int64)v18 - v8 > v50 )
        break;
      if ( (int)v5 > 3 )
      {
        v42 = v5;
        do
        {
          v43 = *((_DWORD *)v12 + 1);
          v42 -= 4;
          v44 = *(_DWORD *)v12;
          v12 += 8;
          *v17 = cLUT_B0[2 * HIBYTE(v44)]
               | word_180006388[2 * (unsigned __int8)v44]
               | cLUT_R0[2 * BYTE1(v44)]
               | word_180006FC8[2 * BYTE2(v44)];
          v17[1] = word_180006380[2 * (unsigned __int8)v43]
                 | yLUT_1[2 * BYTE2(v43)]
                 | word_180006BC0[2 * BYTE1(v43)]
                 | word_1800067B0[2 * ((unsigned __int64)v43 >> 24)];
          v17 += 2;
          v45 = *(_DWORD *)v16;
          v46 = *((_DWORD *)v16 + 1);
          v47 = (unsigned __int8)BYTE1(*(_DWORD *)v16);
          v16 += 8;
          *v18 = word_1800067B0[2 * HIBYTE(v45)]
               | word_180006380[2 * (unsigned __int8)v45]
               | word_180006BC0[2 * v47]
               | yLUT_1[2 * BYTE2(v45)];
          v18[1] = word_180006388[2 * (unsigned __int8)v46]
                 | cLUT_R0[2 * BYTE1(v46)]
                 | word_180006FC8[2 * BYTE2(v46)]
                 | cLUT_B0[2 * ((unsigned __int64)v46 >> 24)];
          v18 += 2;
        }
        while ( v42 > 3 );
        v8 = (unsigned __int64)a5;
        v6 = a3;
        v15 = v51;
        a4 = v58;
        v13 = v5 >> 1;
        v39 = (unsigned int)v5 >> 2;
      }
      if ( *(int *)(a4 + 8) < 0 )
      {
        result = 2LL * (int)v13;
        v17 = (_WORD *)((char *)v17 + result);
        v18 = (_WORD *)((char *)v18 + result);
      }
      else
      {
        result = 2LL * v55;
        v17 = (_WORD *)((char *)v17 - result);
        v18 = (_WORD *)((char *)v18 - result);
      }
      v9 -= 2;
      if ( v9 <= 1 )
        break;
      v7 = a2;
      v12 += v15;
      v16 += v15;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180003e88  mov     [rsp+arg_18], r9
0x180003e8d  mov     [rsp+arg_10], r8
0x180003e92  mov     [rsp+arg_8], rdx
0x180003e97  push    rbx
0x180003e98  push    rbp
0x180003e99  push    rsi
0x180003e9a  push    rdi
0x180003e9b  push    r12
0x180003e9d  push    r13
0x180003e9f  push    r14
0x180003ea1  push    r15
0x180003ea3  sub     rsp, 38h
0x180003ea7  movsxd  r13, dword ptr [rdx+4]
0x180003eab  mov     r14, r8
0x180003eae  mov     esi, [rdx+8]
0x180003eb1  mov     r11, rdx
0x180003eb4  mov     rbp, [rsp+78h+arg_20]
0x180003ebc  neg     esi
0x180003ebe  mov     r10, rcx
0x180003ec1  mov     r8, r13
0x180003ec4  cmovs   esi, [rdx+8]
0x180003ec8  mov     r15, r14
0x180003ecb  mov     rdx, r13
0x180003ece  shr     rdx, 1
0x180003ed1  mov     [rsp+78h+var_60], rdx
0x180003ed6  lea     eax, [rdx+rdx*2]
0x180003ed9  mov     [rsp+78h+arg_0], eax
0x180003ee0  lea     eax, ds:0[r13*2]
0x180003ee8  cdqe
0x180003eea  shr     rax, 2
0x180003eee  cmp     dword ptr [r9+8], 0
0x180003ef3  cdqe
0x180003ef5  lea     rcx, ds:0[rax*4]
0x180003efd  mov     [rsp+78h+var_68], rcx
0x180003f02  lea     r12, [rcx+r14]
0x180003f06  jl      short loc_180003F21
0x180003f08  lea     eax, [rsi-1]
0x180003f0b  imul    eax, r13d
0x180003f0f  movsxd  rbx, eax
0x180003f12  lea     eax, [rsi-2]
0x180003f15  add     rbx, rbp
0x180003f18  imul    eax, r13d
0x180003f1c  movsxd  r8, eax
0x180003f1f  jmp     short loc_180003F24
0x180003f21  mov     rbx, rbp
0x180003f24  cmp     dword ptr [r10+4], 59565955h
0x180003f2c  lea     rdi, [r8+rbp]
0x180003f30  jnz     loc_1800041BB
0x180003f36  cmp     esi, 1
0x180003f39  jle     loc_1800046E3
0x180003f3f  mov     r8d, r13d
0x180003f42  shr     r8d, 2
0x180003f46  mov     dword ptr [rsp+78h+var_70], r8d
0x180003f4b  lea     r10d, ds:0[r8*8]
0x180003f53  cmp     r14, r15
0x180003f56  ja      loc_1800046E3
0x180003f5c  cmp     [r11+14h], r10d
0x180003f60  jb      loc_1800046E3
0x180003f66  mov     r11d, [r11+14h]
0x180003f6a  mov     rax, r15
0x180003f6d  sub     r11d, r10d
0x180003f70  sub     rax, r14
0x180003f73  mov     [rsp+78h+var_58], r11
0x180003f78  cmp     rax, r11
0x180003f7b  ja      loc_1800046E3
0x180003f81  lea     r11d, ds:0[r8*4]
0x180003f89  cmp     rbp, rbx
0x180003f8c  ja      loc_1800046E3
0x180003f92  cmp     [r9+14h], r11d
0x180003f96  jb      loc_1800046E3
0x180003f9c  mov     eax, [r9+14h]
0x180003fa0  sub     eax, r11d
0x180003fa3  mov     [rsp+78h+var_78], rax
0x180003fa7  mov     rax, rbx
0x180003faa  sub     rax, rbp
0x180003fad  cmp     rax, [rsp+78h+var_78]
0x180003fb1  ja      loc_1800046E3
0x180003fb7  cmp     r14, r12
0x180003fba  ja      loc_1800046E3
0x180003fc0  mov     rax, [rsp+78h+arg_8]
0x180003fc8  cmp     [rax+14h], r10d
0x180003fcc  jb      loc_1800046E3
0x180003fd2  mov     rax, r12
0x180003fd5  sub     rax, r14
0x180003fd8  cmp     rax, [rsp+78h+var_58]
0x180003fdd  ja      loc_1800046E3
0x180003fe3  cmp     rbp, rdi
0x180003fe6  ja      loc_1800046E3
0x180003fec  cmp     [r9+14h], r11d
0x180003ff0  jb      loc_1800046E3
0x180003ff6  mov     rax, rdi
0x180003ff9  sub     rax, rbp
0x180003ffc  cmp     rax, [rsp+78h+var_78]
0x180004000  ja      loc_1800046E3
0x180004006  cmp     r13d, 3
0x18000400a  jle     loc_180004176
0x180004010  lea     rbp, cs:180000000h
0x180004017  mov     r14d, r13d
0x18000401a  mov     r8d, [r15]
0x18000401d  sub     r14d, 4
0x180004021  mov     r9d, [r15+4]
0x180004025  mov     eax, r8d
0x180004028  shr     rax, 18h
0x18000402c  add     r15, 8
0x180004030  movzx   edx, ss:rva word_180006FC8[rbp+rax*4]
0x180004038  mov     eax, r8d
0x18000403b  shr     eax, 10h
0x18000403e  movzx   ecx, al
0x180004041  mov     eax, r8d
0x180004044  shr     eax, 8
0x180004047  or      dx, ss:rva cLUT_R0[rbp+rcx*4]
0x18000404f  movzx   ecx, al
0x180004052  movzx   eax, r8b
0x180004056  or      dx, ss:rva word_180006388[rbp+rcx*4]
0x18000405e  or      dx, ss:rva cLUT_B0[rbp+rax*4]
0x180004066  mov     eax, r9d
0x180004069  shr     eax, 10h
0x18000406c  movzx   ecx, al
0x18000406f  mov     eax, r9d
0x180004072  shr     rax, 18h
0x180004076  mov     [rbx], dx
0x180004079  movzx   edx, ss:rva word_180006BC0[rbp+rcx*4]
0x180004081  or      dx, ss:rva yLUT_1[rbp+rax*4]
0x180004089  mov     eax, r9d
0x18000408c  shr     eax, 8
0x18000408f  movzx   ecx, al
0x180004092  movzx   eax, r9b
0x180004096  or      dx, ss:rva word_180006380[rbp+rcx*4]
0x18000409e  or      dx, ss:rva word_1800067B0[rbp+rax*4]
0x1800040a6  mov     [rbx+2], dx
0x1800040aa  add     rbx, 4
0x1800040ae  mov     r9d, [r12]
0x1800040b2  mov     r11d, [r12+4]
0x1800040b7  mov     eax, r9d
0x1800040ba  shr     eax, 8
0x1800040bd  mov     r10d, r9d
0x1800040c0  movzx   edx, al
0x1800040c3  add     r12, 8
0x1800040c7  mov     eax, r9d
0x1800040ca  shr     r10d, 18h
0x1800040ce  shr     eax, 10h
0x1800040d1  movzx   ecx, al
0x1800040d4  movzx   r8d, ss:rva word_180006380[rbp+rdx*4]
0x1800040dd  movzx   eax, r9b
0x1800040e1  or      r8w, ss:rva word_180006BC0[rbp+rcx*4]
0x1800040ea  or      r8w, ss:rva word_1800067B0[rbp+rax*4]
0x1800040f3  mov     eax, r11d
0x1800040f6  or      r8w, ss:rva yLUT_1[rbp+r10*4]
0x1800040ff  shr     rax, 18h
0x180004103  mov     [rdi], r8w
0x180004107  movzx   edx, ss:rva word_180006FC8[rbp+rax*4]
0x18000410f  mov     eax, r11d
0x180004112  shr     eax, 10h
0x180004115  movzx   ecx, al
0x180004118  mov     eax, r11d
0x18000411b  shr     eax, 8
0x18000411e  or      dx, ss:rva cLUT_R0[rbp+rcx*4]
0x180004126  movzx   ecx, al
0x180004129  movzx   eax, r11b
0x18000412d  or      dx, ss:rva word_180006388[rbp+rcx*4]
0x180004135  or      dx, ss:rva cLUT_B0[rbp+rax*4]
0x18000413d  mov     [rdi+2], dx
0x180004141  add     rdi, 4
0x180004145  cmp     r14d, 3
0x180004149  jg      loc_18000401A
0x18000414f  mov     rbp, [rsp+78h+arg_20]
0x180004157  mov     r14, [rsp+78h+arg_10]
0x18000415f  mov     rcx, [rsp+78h+var_68]
0x180004164  mov     r9, [rsp+78h+arg_18]
0x18000416c  mov     rdx, [rsp+78h+var_60]
0x180004171  mov     r8d, dword ptr [rsp+78h+var_70]
0x180004176  cmp     dword ptr [r9+8], 0
0x18000417b  jl      short loc_180004190
0x18000417d  movsxd  rax, [rsp+78h+arg_0]
0x180004185  add     rax, rax
0x180004188  sub     rbx, rax
0x18000418b  sub     rdi, rax
0x18000418e  jmp     short loc_18000419C
0x180004190  movsxd  rax, edx
0x180004193  add     rax, rax
0x180004196  add     rbx, rax
0x180004199  add     rdi, rax
0x18000419c  sub     esi, 2
0x18000419f  cmp     esi, 1
0x1800041a2  jle     loc_1800046E3
0x1800041a8  mov     r11, [rsp+78h+arg_8]
0x1800041b0  add     r15, rcx
0x1800041b3  add     r12, rcx
0x1800041b6  jmp     loc_180003F4B
0x1800041bb  cmp     dword ptr [r10+4], 32595559h
0x1800041c3  jnz     loc_180004452
0x1800041c9  cmp     esi, 1
0x1800041cc  jle     loc_1800046E3
0x1800041d2  mov     r8d, r13d
0x1800041d5  shr     r8d, 2
0x1800041d9  mov     dword ptr [rsp+78h+var_78], r8d
0x1800041dd  lea     r10d, ds:0[r8*8]
0x1800041e5  cmp     r14, r15
0x1800041e8  ja      loc_1800046E3
0x1800041ee  cmp     [r11+14h], r10d
0x1800041f2  jb      loc_1800046E3
0x1800041f8  mov     r11d, [r11+14h]
0x1800041fc  mov     rax, r15
0x1800041ff  sub     r11d, r10d
0x180004202  sub     rax, r14
0x180004205  mov     [rsp+78h+var_58], r11
0x18000420a  cmp     rax, r11
0x18000420d  ja      loc_1800046E3
0x180004213  lea     r11d, ds:0[r8*4]
0x18000421b  cmp     rbp, rbx
0x18000421e  ja      loc_1800046E3
0x180004224  cmp     [r9+14h], r11d
0x180004228  jb      loc_1800046E3
0x18000422e  mov     eax, [r9+14h]
0x180004232  sub     eax, r11d
0x180004235  mov     [rsp+78h+var_70], rax
0x18000423a  mov     rax, rbx
0x18000423d  sub     rax, rbp
0x180004240  cmp     rax, [rsp+78h+var_70]
0x180004245  ja      loc_1800046E3
0x18000424b  cmp     r14, r12
0x18000424e  ja      loc_1800046E3
0x180004254  mov     rax, [rsp+78h+arg_8]
0x18000425c  cmp     [rax+14h], r10d
0x180004260  jb      loc_1800046E3
0x180004266  mov     rax, r12
0x180004269  sub     rax, r14
0x18000426c  cmp     rax, [rsp+78h+var_58]
0x180004271  ja      loc_1800046E3
0x180004277  cmp     rbp, rdi
0x18000427a  ja      loc_1800046E3
0x180004280  cmp     [r9+14h], r11d
0x180004284  jb      loc_1800046E3
0x18000428a  mov     rax, rdi
0x18000428d  sub     rax, rbp
0x180004290  cmp     rax, [rsp+78h+var_70]
0x180004295  ja      loc_1800046E3
0x18000429b  cmp     r13d, 3
0x18000429f  jle     loc_18000440D
0x1800042a5  lea     rbp, cs:180000000h
0x1800042ac  mov     r14d, r13d
0x1800042af  mov     edx, [r15]
0x1800042b2  sub     r14d, 4
0x1800042b6  mov     r11d, [r15+4]
0x1800042ba  mov     r9d, edx
0x1800042bd  mov     eax, edx
0x1800042bf  shr     r9d, 18h
0x1800042c3  shr     eax, 10h
0x1800042c6  add     r15, 8
0x1800042ca  movzx   r10d, al
0x1800042ce  mov     eax, edx
0x1800042d0  shr     eax, 8
0x1800042d3  movzx   ecx, al
0x1800042d6  movzx   eax, dl
0x1800042d9  movzx   r8d, ss:rva cLUT_B0[rbp+rcx*4]
0x1800042e2  or      r8w, ss:rva word_180006388[rbp+rax*4]
0x1800042eb  mov     eax, r11d
0x1800042ee  or      r8w, ss:rva cLUT_R0[rbp+r9*4]
0x1800042f7  or      r8w, ss:rva word_180006FC8[rbp+r10*4]
0x180004300  shr     rax, 18h
0x180004304  mov     [rbx], r8w
0x180004308  movzx   edx, ss:rva word_180006BC0[rbp+rax*4]
0x180004310  mov     eax, r11d
0x180004313  shr     eax, 8
0x180004316  movzx   ecx, al
0x180004319  mov     eax, r11d
0x18000431c  shr     eax, 10h
0x18000431f  or      dx, ss:rva word_1800067B0[rbp+rcx*4]
0x180004327  movzx   ecx, al
0x18000432a  movzx   eax, r11b
0x18000432e  or      dx, ss:rva yLUT_1[rbp+rcx*4]
0x180004336  or      dx, ss:rva word_180006380[rbp+rax*4]
0x18000433e  mov     [rbx+2], dx
0x180004342  add     rbx, 4
0x180004346  mov     r9d, [r12]
0x18000434a  mov     r11d, [r12+4]
0x18000434f  mov     eax, r9d
0x180004352  shr     eax, 8
0x180004355  mov     r10d, r9d
0x180004358  movzx   edx, al
0x18000435b  add     r12, 8
0x18000435f  mov     eax, r9d
0x180004362  shr     r10d, 18h
0x180004366  shr     eax, 10h
0x180004369  movzx   ecx, al
0x18000436c  movzx   eax, r9b
0x180004370  movzx   r8d, ss:rva yLUT_1[rbp+rcx*4]
0x180004379  or      r8w, ss:rva word_1800067B0[rbp+rdx*4]
0x180004382  or      r8w, ss:rva word_180006380[rbp+rax*4]
0x18000438b  mov     eax, r11d
0x18000438e  or      r8w, ss:rva word_180006BC0[rbp+r10*4]
0x180004397  shr     rax, 18h
0x18000439b  mov     [rdi], r8w
0x18000439f  movzx   edx, ss:rva cLUT_R0[rbp+rax*4]
0x1800043a7  mov     eax, r11d
0x1800043aa  shr     eax, 10h
0x1800043ad  movzx   ecx, al
0x1800043b0  mov     eax, r11d
0x1800043b3  shr     eax, 8
0x1800043b6  or      dx, ss:rva word_180006FC8[rbp+rcx*4]
  ... truncated ...
```
