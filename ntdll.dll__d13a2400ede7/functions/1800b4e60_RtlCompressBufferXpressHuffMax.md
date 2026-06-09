# RtlCompressBufferXpressHuffMax

- ea: `0x1800b4e60`
- end: `0x1800b5628`
- name: `RtlCompressBufferXpressHuffMax`
- size: `1992`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, void *, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800b4da0`

## callees

- `0x1800b4e60`
- `0x1800b66c0`
- `0x1800b6710`
- `0x1800b6c50`
- `0x18016f030`

## pseudocode

```c
__int64 __fastcall RtlCompressBufferXpressHuffMax(
        unsigned __int64 a1,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        _DWORD *a5,
        char *a6)
{
  unsigned __int8 *v8; // rbp
  unsigned __int64 v10; // r15
  unsigned __int8 *v11; // rbx
  __int64 v12; // r12
  int *v13; // rcx
  unsigned __int8 *v14; // rdx
  int *v15; // r11
  unsigned __int8 *v16; // rsi
  unsigned __int64 v17; // r13
  int v18; // edi
  char v19; // al
  char v20; // al
  int v21; // edi
  __int64 v22; // rax
  unsigned __int8 *v24; // r10
  __int64 v25; // r9
  unsigned __int64 v26; // rdx
  __int64 v27; // rax
  unsigned __int64 v28; // r8
  int v29; // ebp
  int v30; // r12d
  unsigned __int8 *v31; // rax
  int v32; // ecx
  unsigned __int8 *v33; // rdi
  unsigned __int8 *v34; // r15
  unsigned __int64 v35; // r11
  unsigned __int64 v36; // rsi
  unsigned __int8 *v37; // rbx
  _DWORD *i; // rax
  unsigned __int64 v39; // rbx
  unsigned __int8 *v40; // rcx
  unsigned __int8 *v41; // r9
  unsigned __int8 *v42; // r10
  int v43; // edx
  int v44; // ecx
  unsigned __int64 v45; // rdx
  __int64 v46; // rcx
  unsigned __int64 v47; // r8
  unsigned __int64 v48; // rdx
  char v49; // cl
  _WORD *v50; // r9
  unsigned __int8 v51; // cl
  int *v52; // rax
  __int64 v53; // rax
  int v54; // ecx
  int v55; // ecx
  __int64 XpressCallback; // rax
  unsigned __int8 *v57; // [rsp+30h] [rbp-98h]
  __int64 v58; // [rsp+38h] [rbp-90h]
  __int64 v59; // [rsp+40h] [rbp-88h]
  unsigned __int64 v60; // [rsp+48h] [rbp-80h]
  __int64 v61; // [rsp+50h] [rbp-78h]
  __int64 v62; // [rsp+58h] [rbp-70h]
  unsigned __int8 *v63; // [rsp+60h] [rbp-68h]
  unsigned __int64 v64; // [rsp+68h] [rbp-60h]
  _QWORD v65[2]; // [rsp+70h] [rbp-58h] BYREF
  unsigned int v66; // [rsp+80h] [rbp-48h]
  int v67; // [rsp+84h] [rbp-44h]
  int v69; // [rsp+D8h] [rbp+10h]
  int v70; // [rsp+E0h] [rbp+18h]
  char *v71; // [rsp+F8h] [rbp+30h]
  __int64 v73; // [rsp+100h] [rbp+38h]
  char *v75; // [rsp+108h] [rbp+40h]

  v70 = a3;
  v67 = 0;
  v8 = (unsigned __int8 *)a1;
  if ( a4 < 0x12C )
    return 3221225507LL;
  if ( a1 > 0x10001 )
  {
    v10 = a2 + a1;
    v62 = a2;
    v64 = a3 + a4;
    v60 = v10;
    memset_thunk_772440563353939046(a6, 0, 0x40000u);
    v11 = v8;
    v61 = a3;
    *((_QWORD *)a6 + 0x8000) = 0;
    v65[0] = 0;
    v65[1] = 0;
    v66 = a2;
    v57 = 0;
    while ( 1 )
    {
      v58 = 0;
      v59 = 0;
      v12 = 0;
      memset_thunk_772440563353939046(a6 + 1339936, 0, 0x800u);
      v13 = (int *)(a6 + 1342240);
      v14 = (unsigned __int8 *)v10;
      v75 = a6 + 1342240;
      if ( (unsigned __int64)(v11 + 0x10000) <= v10 )
        v14 = v11 + 0x10000;
      v15 = (int *)(a6 + 1342244);
      v16 = &v11[v62];
      v63 = v14;
      v71 = a6 + 1342244;
      v17 = (unsigned __int64)(v14 - 5);
      if ( v14 - 5 < &v11[v62] )
        v16 = v14 - 5;
      v73 = (__int64)v16;
      if ( v11 == v8 )
      {
        v18 = 2;
        ++*(_DWORD *)&a6[4 * *v11 + 1339936];
        v19 = *v11++;
        *(_BYTE *)v15 = v19;
        v15 = (int *)(a6 + 1342245);
        v71 = a6 + 1342245;
      }
      else
      {
        v18 = 1;
      }
      v69 = v18;
      if ( (unsigned __int64)v11 < v17 )
        break;
LABEL_11:
      if ( v11 < v14 )
      {
        do
        {
          ++*(_DWORD *)&a6[4 * *v11 + 1339936];
          v20 = *v11++;
          *(_BYTE *)v15 = v20;
          v15 = (int *)((char *)v15 + 1);
          if ( v18 < 0 )
          {
            *v13 = 2 * v18;
            v18 = 1;
            v13 = v15++;
          }
          else
          {
            v18 *= 2;
          }
        }
        while ( v11 < v14 );
        LODWORD(v71) = (_DWORD)v15;
      }
      for ( ; v18 >= 0; v18 = (2 * v18) | 1 )
        ;
      *v13 = (2 * v18) | 1;
      if ( (unsigned __int64)v11 < v10 )
      {
        v21 = 0;
      }
      else
      {
        ++*((_DWORD *)a6 + 335240);
        v21 = 1;
      }
      if ( v59 + 4 * ((unsigned __int64)(v12 + XpressBuildHuffmanEncodings(a6 + 1310720) + 31) >> 5) + v61 + 258 >= v64 )
        return 3221225507LL;
      v22 = XpressDoHuffmanPass((int)a6 + 1310720, (int)a6 + 1342240, (_DWORD)v71, v61, v21);
      v61 = v22;
      if ( v21 )
      {
        *a5 = v22 - v70;
        return 0;
      }
    }
    v24 = v11;
    v25 = (v11 - v8) % 0x20000;
    do
    {
      v26 = (unsigned __int16)word_18018F740[v24[1]]
          ^ (unsigned __int16)XpressHashFunction[*v24]
          ^ (unsigned __int64)(unsigned __int16)word_18018F940[v24[2]];
      v27 = *(_QWORD *)&a6[8 * v26];
      *(_QWORD *)&a6[8 * v26] = v24++;
      *(_QWORD *)&a6[8 * v25 + 0x40000] = v27;
      v25 = ((_DWORD)v25 + 1) & 0x1FFFF;
    }
    while ( (unsigned __int64)v24 < v17 );
    while ( 1 )
    {
      if ( v11 >= v16 )
      {
        if ( (unsigned __int64)v11 >= v17 )
        {
          v8 = (unsigned __int8 *)a1;
          v10 = v60;
          v12 = v58;
          v13 = (int *)v75;
          v14 = v63;
          goto LABEL_11;
        }
        XpressCallback = RtlpMakeXpressCallback(v65, v17, v11);
        v15 = (int *)v71;
        v73 = XpressCallback;
      }
      v28 = a1;
      v29 = *(_DWORD *)v11;
      v30 = v18;
      v31 = *(unsigned __int8 **)&a6[8 * ((__int64)&v11[-a1] % 0x20000) + 0x40000];
      if ( v31 + 0x10000 <= v11 )
        goto LABEL_67;
      v32 = *(_DWORD *)v31 ^ v29;
      if ( v32 )
      {
        if ( (v32 & 0xFFFFFF) == 0 )
          goto LABEL_70;
        v31 = *(unsigned __int8 **)&a6[8 * ((__int64)&v31[-a1] % 0x20000) + 0x40000];
        if ( v31 + 0x10000 <= v11 )
          goto LABEL_67;
        v54 = *(_DWORD *)v31 ^ v29;
        if ( v54 )
        {
          if ( (v54 & 0xFFFFFF) == 0 )
            goto LABEL_70;
          v31 = *(unsigned __int8 **)&a6[8 * ((__int64)&v31[-a1] % 0x20000) + 0x40000];
          if ( v31 + 0x10000 <= v11 )
            goto LABEL_67;
          v55 = *(_DWORD *)v31 ^ v29;
          if ( v55 )
            break;
        }
      }
      v33 = v11;
      v34 = v11 - 0x10000;
      v35 = 0;
      v36 = 3;
LABEL_43:
      v37 = v11 + 4;
      for ( i = v31 + 4; ; i += 8 )
      {
        v42 = v37 + 32;
        if ( (unsigned __int64)(v37 + 32) >= v60 )
          break;
        v43 = *i;
        v44 = *(_DWORD *)v37;
        if ( *(_DWORD *)v37 != *i )
          goto LABEL_35;
        v43 = i[1];
        v44 = *((_DWORD *)v37 + 1);
        if ( v44 != v43 )
        {
          v37 += 4;
          ++i;
          goto LABEL_35;
        }
        v43 = i[2];
        v44 = *((_DWORD *)v37 + 2);
        if ( v44 != v43 )
        {
          v37 += 8;
          i += 2;
          goto LABEL_35;
        }
        v43 = i[3];
        v44 = *((_DWORD *)v37 + 3);
        if ( v44 != v43 )
        {
          v37 += 12;
          i += 3;
          goto LABEL_35;
        }
        v43 = i[4];
        v44 = *((_DWORD *)v37 + 4);
        if ( v44 != v43 )
        {
          v37 += 16;
          i += 4;
          goto LABEL_35;
        }
        v43 = i[5];
        v44 = *((_DWORD *)v37 + 5);
        if ( v44 != v43 )
        {
          v37 += 20;
          i += 5;
          goto LABEL_35;
        }
        v43 = i[6];
        v44 = *((_DWORD *)v37 + 6);
        if ( v44 != v43 )
        {
          v37 += 24;
          i += 6;
LABEL_35:
          if ( (_BYTE)v44 == (_BYTE)v43 )
          {
            if ( v37[1] == *((_BYTE *)i + 1) )
            {
              if ( v37[2] == *((_BYTE *)i + 2) )
              {
                v37 += 3;
                i = (_DWORD *)((char *)i + 3);
              }
              else
              {
                v37 += 2;
                i = (_DWORD *)((char *)i + 2);
              }
            }
            else
            {
              ++v37;
              i = (_DWORD *)((char *)i + 1);
            }
          }
          goto LABEL_36;
        }
        v44 = *((_DWORD *)v37 + 7);
        v37 += 28;
        v43 = i[7];
        if ( v44 != v43 )
        {
          i += 7;
          goto LABEL_35;
        }
        v37 = v42;
      }
      for ( ; (unsigned __int64)v37 < v60; i = (_DWORD *)((char *)i + 1) )
      {
        if ( *v37 != *(_BYTE *)i )
          break;
        ++v37;
      }
LABEL_36:
      v39 = v37 - v33;
      v40 = (unsigned __int8 *)i;
      v31 = (unsigned __int8 *)i - v39;
      if ( v39 <= v36 )
      {
        v35 += v39;
LABEL_38:
        v28 = a1;
        goto LABEL_39;
      }
      v57 = v31;
      v36 = v39;
      v41 = v31;
      if ( v40 <= v33 )
        goto LABEL_38;
LABEL_56:
      v11 = &v33[v36];
      v45 = v33 - v41;
      if ( v36 == 3 && v45 > 0x1000 )
      {
        v15 = (int *)v71;
        v11 = v33;
LABEL_67:
        v18 = 2 * v30;
        ++*(_DWORD *)&a6[4 * (unsigned __int8)v29 + 1339936];
        *(_BYTE *)v15 = v29;
        v15 = (int *)((char *)v15 + 1);
        ++v11;
        goto LABEL_62;
      }
      if ( v45 >= 0x100 )
        v46 = *((unsigned __int8 *)XpressHighBitIndexTable + (v45 >> 8)) + 8LL;
      else
        v46 = *((unsigned __int8 *)XpressHighBitIndexTable + v45);
      v58 += v46;
      v47 = v36 - 3;
      v48 = v45 - (1LL << v46);
      v49 = 16 * v46;
      if ( v36 - 3 >= 0xF )
      {
        v51 = v49 + 15;
        *v71 = v51;
        v50 = v71 + 2;
        if ( v36 - 18 >= 0xFF )
        {
          v71[1] = -1;
          if ( v47 < 0x10000 )
          {
            *v50 = v47;
            v59 += 3;
            v50 = v71 + 4;
            goto LABEL_61;
          }
          *((_DWORD *)v71 + 1) = v47;
          *v50 = 0;
          v50 = v71 + 8;
          v53 = 7;
        }
        else
        {
          v71[1] = v36 - 18;
          v53 = 1;
        }
        v59 += v53;
      }
      else
      {
        v50 = v71 + 1;
        v51 = v49 + v47;
        *v71 = v51;
      }
LABEL_61:
      v15 = (int *)(v50 + 1);
      ++*(_DWORD *)&a6[4 * v51 + 1340960];
      v18 = (2 * v69) | 1;
      *v50 = v48;
LABEL_62:
      v16 = (unsigned __int8 *)v73;
      v71 = (char *)v15;
      v69 = v18;
      if ( v30 < 0 )
      {
        v52 = (int *)v75;
        v75 = (char *)v15++;
        v71 = (char *)v15;
        *v52 = v18;
        v18 = 1;
        v69 = 1;
      }
    }
    if ( (v55 & 0xFFFFFF) != 0 )
      goto LABEL_67;
LABEL_70:
    v33 = v11;
    v57 = v31;
    v34 = v11 - 0x10000;
    v35 = 0;
    v36 = 3;
    do
    {
      v31 = *(unsigned __int8 **)&a6[8 * ((__int64)&v31[-v28] % 0x20000) + 0x40000];
      if ( v31 <= v34 )
        break;
      if ( v29 == *(_DWORD *)v31 )
      {
        v11 = v33;
        goto LABEL_43;
      }
LABEL_39:
      ++v35;
    }
    while ( v35 < 0xC );
    v41 = v57;
    goto LABEL_56;
  }
  return 3221225659LL;
}

```

## disassembly

```asm
0x1800b4e60  mov     rax, rsp
0x1800b4e63  mov     [rax+20h], rbx
0x1800b4e67  mov     [rax+18h], r8
0x1800b4e6b  mov     [rax+8], rcx
0x1800b4e6f  push    rbp
0x1800b4e70  push    rsi
0x1800b4e71  push    rdi
0x1800b4e72  push    r12
0x1800b4e74  push    r13
0x1800b4e76  push    r14
0x1800b4e78  push    r15
0x1800b4e7a  sub     rsp, 90h
0x1800b4e81  xor     r13d, r13d
0x1800b4e84  mov     edi, edx
0x1800b4e86  mov     [rax-44h], r13d
0x1800b4e8a  mov     rsi, r8
0x1800b4e8d  mov     rbp, rcx
0x1800b4e90  cmp     r9d, 12Ch
0x1800b4e97  jb      loc_1800B5085
0x1800b4e9d  cmp     rcx, 10001h
0x1800b4ea4  jbe     loc_1800B50A6
0x1800b4eaa  mov     r14, [rsp+0C8h+arg_28]
0x1800b4eb2  lea     r15, [rdi+rcx]
0x1800b4eb6  mov     eax, r9d
0x1800b4eb9  xor     edx, edx; Val
0x1800b4ebb  add     rax, r8
0x1800b4ebe  mov     [rsp+0C8h+var_70], rdi
0x1800b4ec3  mov     r8d, 40000h; Size
0x1800b4ec9  mov     [rsp+0C8h+var_60], rax
0x1800b4ece  mov     rcx, r14; void *
0x1800b4ed1  mov     [rsp+0C8h+var_80], r15
0x1800b4ed6  call    memset$thunk$772440563353939046
0x1800b4edb  mov     rbx, rbp
0x1800b4ede  mov     [rsp+0C8h+var_78], rsi
0x1800b4ee3  mov     [r14+40000h], r13
0x1800b4eea  mov     [rsp+0C8h+var_58], r13
0x1800b4eef  mov     [rsp+0C8h+var_50], r13
0x1800b4ef4  mov     [rsp+0C8h+var_48], edi
0x1800b4efb  mov     [rsp+0C8h+var_98], r13
0x1800b4f00  lea     rcx, [r14+147220h]; void *
0x1800b4f07  mov     [rsp+0C8h+var_90], r13
0x1800b4f0c  xor     edx, edx; Val
0x1800b4f0e  mov     [rsp+0C8h+var_88], r13
0x1800b4f13  mov     r8d, 800h; Size
0x1800b4f19  mov     r12, r13
0x1800b4f1c  call    memset$thunk$772440563353939046
0x1800b4f21  mov     rsi, [rsp+0C8h+var_70]
0x1800b4f26  lea     rax, [rbx+10000h]
0x1800b4f2d  cmp     rax, r15
0x1800b4f30  lea     rcx, [r14+147B20h]
0x1800b4f37  mov     rdx, r15
0x1800b4f3a  mov     [rsp+0C8h+arg_38], rcx
0x1800b4f42  cmovbe  rdx, rax
0x1800b4f46  lea     r11, [r14+147B24h]
0x1800b4f4d  add     rsi, rbx
0x1800b4f50  mov     [rsp+0C8h+var_68], rdx
0x1800b4f55  mov     [rsp+0C8h+arg_28], r11
0x1800b4f5d  lea     r13, [rdx-5]
0x1800b4f61  cmp     r13, rsi
0x1800b4f64  cmovb   rsi, r13
0x1800b4f68  mov     [rsp+0C8h+arg_30], rsi
0x1800b4f70  cmp     rbx, rbp
0x1800b4f73  jnz     loc_1800B561E
0x1800b4f79  movzx   eax, byte ptr [rbx]
0x1800b4f7c  mov     edi, 2
0x1800b4f81  inc     dword ptr [r14+rax*4+147220h]
0x1800b4f89  movzx   eax, byte ptr [rbx]
0x1800b4f8c  inc     rbx
0x1800b4f8f  mov     [r11], al
0x1800b4f92  inc     r11
0x1800b4f95  mov     [rsp+0C8h+arg_28], r11
0x1800b4f9d  mov     [rsp+0C8h+arg_8], edi
0x1800b4fa4  cmp     rbx, r13
0x1800b4fa7  jb      loc_1800B50D8
0x1800b4fad  cmp     rbx, rdx
0x1800b4fb0  jnb     short loc_1800B4FE3
0x1800b4fb2  movzx   eax, byte ptr [rbx]
0x1800b4fb5  inc     dword ptr [r14+rax*4+147220h]
0x1800b4fbd  movzx   eax, byte ptr [rbx]
0x1800b4fc0  inc     rbx
0x1800b4fc3  mov     [r11], al
0x1800b4fc6  inc     r11
0x1800b4fc9  lea     eax, [rdi+rdi]
0x1800b4fcc  test    edi, edi
0x1800b4fce  js      loc_1800B50AD
0x1800b4fd4  mov     edi, eax
0x1800b4fd6  cmp     rbx, rdx
0x1800b4fd9  jb      short loc_1800B4FB2
0x1800b4fdb  mov     [rsp+0C8h+arg_28], r11
0x1800b4fe3  test    edi, edi
0x1800b4fe5  jns     loc_1800B50C0
0x1800b4feb  lea     eax, [rdi+rdi]
0x1800b4fee  or      eax, 1
0x1800b4ff1  mov     [rcx], eax
0x1800b4ff3  cmp     rbx, r15
0x1800b4ff6  jb      loc_1800B50CD
0x1800b4ffc  inc     dword ptr [r14+147620h]
0x1800b5003  mov     edi, 1
0x1800b5008  xor     r13d, r13d
0x1800b500b  lea     rcx, [r14+140000h]
0x1800b5012  call    XpressBuildHuffmanEncodings
0x1800b5017  mov     r9, [rsp+0C8h+var_78]
0x1800b501c  lea     r10, [rax+1Fh]
0x1800b5020  mov     rax, [rsp+0C8h+var_88]
0x1800b5025  add     r10, r12
0x1800b5028  shr     r10, 5
0x1800b502c  lea     rax, [rax+r10*4]
0x1800b5030  lea     r10, [r9+102h]
0x1800b5037  add     r10, rax
0x1800b503a  cmp     r10, [rsp+0C8h+var_60]
0x1800b503f  jnb     short loc_1800B5085
0x1800b5041  mov     r8, [rsp+0C8h+arg_28]
0x1800b5049  lea     rdx, [r14+147B20h]
0x1800b5050  lea     rcx, [r14+140000h]
0x1800b5057  mov     [rsp+0C8h+var_A8], edi
0x1800b505b  call    XpressDoHuffmanPass
0x1800b5060  mov     [rsp+0C8h+var_78], rax
0x1800b5065  mov     rcx, rax
0x1800b5068  test    edi, edi
0x1800b506a  jz      loc_1800B4F00
0x1800b5070  mov     rax, [rsp+0C8h+arg_20]
0x1800b5078  sub     ecx, [rsp+0C8h+arg_10]
0x1800b507f  mov     [rax], ecx
0x1800b5081  xor     eax, eax
0x1800b5083  jmp     short loc_1800B508A
0x1800b5085  mov     eax, 0C0000023h
0x1800b508a  mov     rbx, [rsp+0C8h+arg_18]
0x1800b5092  add     rsp, 90h
0x1800b5099  pop     r15
0x1800b509b  pop     r14
0x1800b509d  pop     r13
0x1800b509f  pop     r12
0x1800b50a1  pop     rdi
0x1800b50a2  pop     rsi
0x1800b50a3  pop     rbp
0x1800b50a4  retn
0x1800b50a6  mov     eax, 0C00000BBh
0x1800b50ab  jmp     short loc_1800B508A
0x1800b50ad  mov     [rcx], eax
0x1800b50af  mov     edi, 1
0x1800b50b4  mov     rcx, r11
0x1800b50b7  add     r11, 4
0x1800b50bb  jmp     loc_1800B4FD6
0x1800b50c0  add     edi, edi
0x1800b50c2  or      edi, 1
0x1800b50c5  jl      loc_1800B4FEB
0x1800b50cb  jmp     short loc_1800B50C0
0x1800b50cd  xor     r13d, r13d
0x1800b50d0  mov     edi, r13d
0x1800b50d3  jmp     loc_1800B500B
0x1800b50d8  mov     rax, rbx
0x1800b50db  mov     r10, rbx
0x1800b50de  sub     rax, rbp
0x1800b50e1  lea     rbp, cs:180000000h
0x1800b50e8  cqo
0x1800b50ea  and     edx, 1FFFFh
0x1800b50f0  lea     r9, [rdx+rax]
0x1800b50f4  and     r9d, 1FFFFh
0x1800b50fb  sub     r9, rdx
0x1800b50fe  xchg    ax, ax
0x1800b5100  movzx   ecx, byte ptr [r10+2]
0x1800b5105  lea     r8, [r10+1]
0x1800b5109  movzx   edx, ss:rva word_18018F940[rbp+rcx*2]
0x1800b5111  movzx   ecx, byte ptr [r10]
0x1800b5115  movzx   eax, ss:rva XpressHashFunction[rbp+rcx*2]
0x1800b511d  xor     rdx, rax
0x1800b5120  movzx   eax, byte ptr [r8]
0x1800b5124  movzx   eax, ss:rva word_18018F740[rbp+rax*2]
0x1800b512c  xor     rdx, rax
0x1800b512f  mov     rax, [r14+rdx*8]
0x1800b5133  mov     [r14+rdx*8], r10
0x1800b5137  mov     r10, r8
0x1800b513a  mov     [r14+r9*8+40000h], rax
0x1800b5142  inc     r9
0x1800b5145  and     r9d, 1FFFFh
0x1800b514c  cmp     r8, r13
0x1800b514f  jb      short loc_1800B5100
0x1800b5151  cmp     rbx, rsi
0x1800b5154  jnb     loc_1800B55B8
0x1800b515a  mov     r8, [rsp+0C8h+arg_0]
0x1800b5162  mov     rax, rbx
0x1800b5165  mov     ebp, [rbx]
0x1800b5167  sub     rax, r8
0x1800b516a  cqo
0x1800b516c  mov     r12d, edi
0x1800b516f  and     edx, 1FFFFh
0x1800b5175  add     rax, rdx
0x1800b5178  and     eax, 1FFFFh
0x1800b517d  sub     rax, rdx
0x1800b5180  mov     rax, [r14+rax*8+40000h]
0x1800b5188  lea     rcx, [rax+10000h]
0x1800b518f  cmp     rcx, rbx
0x1800b5192  jbe     loc_1800B53DB
0x1800b5198  mov     ecx, ebp
0x1800b519a  xor     ecx, [rax]
0x1800b519c  jnz     loc_1800B5418
0x1800b51a2  mov     rdi, rbx
0x1800b51a5  lea     r15, [rbx-10000h]
0x1800b51ac  xor     r11d, r11d
0x1800b51af  mov     esi, 3
0x1800b51b4  jmp     short loc_1800B522F
0x1800b51b6  add     rbx, 4
0x1800b51ba  add     rax, 4
0x1800b51be  cmp     cl, dl
0x1800b51c0  jz      loc_1800B53A9
0x1800b51c6  sub     rbx, rdi
0x1800b51c9  mov     rcx, rax
0x1800b51cc  sub     rax, rbx
0x1800b51cf  cmp     rbx, rsi
0x1800b51d2  jbe     loc_1800B52C7
0x1800b51d8  mov     [rsp+0C8h+var_98], rax
0x1800b51dd  mov     rsi, rbx
0x1800b51e0  mov     r9, rax
0x1800b51e3  cmp     rcx, rdi
0x1800b51e6  ja      loc_1800B52D4
0x1800b51ec  mov     r8, [rsp+0C8h+arg_0]
0x1800b51f4  inc     r11
0x1800b51f7  cmp     r11, 0Ch
0x1800b51fb  jnb     loc_1800B52CF
0x1800b5201  sub     rax, r8
0x1800b5204  cqo
0x1800b5206  and     edx, 1FFFFh
0x1800b520c  add     rax, rdx
0x1800b520f  and     eax, 1FFFFh
0x1800b5214  sub     rax, rdx
0x1800b5217  mov     rax, [r14+rax*8+40000h]
0x1800b521f  cmp     rax, r15
0x1800b5222  jbe     loc_1800B52CF
0x1800b5228  cmp     ebp, [rax]
0x1800b522a  jnz     short loc_1800B51F4
0x1800b522c  mov     rbx, rdi
0x1800b522f  add     rbx, 4
0x1800b5233  add     rax, 4
0x1800b5237  mov     rdx, [rsp+0C8h+var_80]
0x1800b523c  lea     r10, [rbx+20h]
0x1800b5240  cmp     r10, rdx
0x1800b5243  jnb     loc_1800B54D4
0x1800b5249  mov     edx, [rax]
0x1800b524b  mov     ecx, [rbx]
0x1800b524d  cmp     ecx, edx
0x1800b524f  jnz     loc_1800B51BE
0x1800b5255  mov     edx, [rax+4]
0x1800b5258  mov     ecx, [rbx+4]
0x1800b525b  cmp     ecx, edx
0x1800b525d  jnz     loc_1800B51B6
0x1800b5263  mov     edx, [rax+8]
0x1800b5266  mov     ecx, [rbx+8]
0x1800b5269  cmp     ecx, edx
0x1800b526b  jnz     loc_1800B546D
0x1800b5271  mov     edx, [rax+0Ch]
0x1800b5274  mov     ecx, [rbx+0Ch]
0x1800b5277  cmp     ecx, edx
0x1800b5279  jnz     loc_1800B5492
0x1800b527f  mov     edx, [rax+10h]
0x1800b5282  mov     ecx, [rbx+10h]
0x1800b5285  cmp     ecx, edx
0x1800b5287  jnz     loc_1800B54B1
0x1800b528d  mov     edx, [rax+14h]
0x1800b5290  mov     ecx, [rbx+14h]
0x1800b5293  cmp     ecx, edx
0x1800b5295  jnz     loc_1800B54BE
0x1800b529b  mov     edx, [rax+18h]
0x1800b529e  mov     ecx, [rbx+18h]
0x1800b52a1  cmp     ecx, edx
0x1800b52a3  jnz     loc_1800B54F9
0x1800b52a9  mov     ecx, [rbx+1Ch]
0x1800b52ac  add     rbx, 1Ch
0x1800b52b0  mov     edx, [rax+1Ch]
0x1800b52b3  cmp     ecx, edx
0x1800b52b5  jnz     loc_1800B54CB
0x1800b52bb  mov     rbx, r10
0x1800b52be  add     rax, 20h ; ' '
0x1800b52c2  jmp     loc_1800B5237
0x1800b52c7  add     r11, rbx
0x1800b52ca  jmp     loc_1800B51EC
0x1800b52cf  mov     r9, [rsp+0C8h+var_98]
0x1800b52d4  mov     rdx, rdi
0x1800b52d7  lea     rbx, [rsi+rdi]
0x1800b52db  sub     rdx, r9
0x1800b52de  cmp     rsi, 3
0x1800b52e2  jz      loc_1800B549F
0x1800b52e8  cmp     rdx, 100h
0x1800b52ef  jnb     loc_1800B53F9
0x1800b52f5  lea     rax, cs:180000000h
0x1800b52fc  movzx   ecx, byte ptr [rdx+rax+17B1A0h]
0x1800b5304  add     [rsp+0C8h+var_90], rcx
0x1800b5309  lea     r8, [rsi-3]
0x1800b530d  mov     r11, [rsp+0C8h+arg_28]
0x1800b5315  mov     eax, 1
0x1800b531a  shl     rax, cl
0x1800b531d  sub     rdx, rax
0x1800b5320  shl     cl, 4
0x1800b5323  cmp     r8, 0Fh
0x1800b5327  jnb     loc_1800B5440
0x1800b532d  add     r8b, cl
0x1800b5330  lea     r9, [r11+1]
0x1800b5334  movzx   ecx, r8b
0x1800b5338  mov     [r11], r8b
0x1800b533b  mov     edi, [rsp+0C8h+arg_8]
0x1800b5342  lea     r11, [r9+2]
  ... truncated ...
```
