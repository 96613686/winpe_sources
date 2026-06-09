# RtlCompressBufferXpressHuffMax

- ea: `0x18007fd90`
- end: `0x180080558`
- name: `RtlCompressBufferXpressHuffMax`
- size: `1992`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, void *, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18007fcd0`

## callees

- `0x18007fd90`
- `0x1800815f0`
- `0x180081640`
- `0x180081b80`
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
      v26 = (unsigned __int16)word_18018F360[v24[1]]
          ^ (unsigned __int16)XpressHashFunction[*v24]
          ^ (unsigned __int64)(unsigned __int16)word_18018F560[v24[2]];
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
0x18007fd90  mov     rax, rsp
0x18007fd93  mov     [rax+20h], rbx
0x18007fd97  mov     [rax+18h], r8
0x18007fd9b  mov     [rax+8], rcx
0x18007fd9f  push    rbp
0x18007fda0  push    rsi
0x18007fda1  push    rdi
0x18007fda2  push    r12
0x18007fda4  push    r13
0x18007fda6  push    r14
0x18007fda8  push    r15
0x18007fdaa  sub     rsp, 90h
0x18007fdb1  xor     r13d, r13d
0x18007fdb4  mov     edi, edx
0x18007fdb6  mov     [rax-44h], r13d
0x18007fdba  mov     rsi, r8
0x18007fdbd  mov     rbp, rcx
0x18007fdc0  cmp     r9d, 12Ch
0x18007fdc7  jb      loc_18007FFB5
0x18007fdcd  cmp     rcx, 10001h
0x18007fdd4  jbe     loc_18007FFD6
0x18007fdda  mov     r14, [rsp+0C8h+arg_28]
0x18007fde2  lea     r15, [rdi+rcx]
0x18007fde6  mov     eax, r9d
0x18007fde9  xor     edx, edx; Val
0x18007fdeb  add     rax, r8
0x18007fdee  mov     [rsp+0C8h+var_70], rdi
0x18007fdf3  mov     r8d, 40000h; Size
0x18007fdf9  mov     [rsp+0C8h+var_60], rax
0x18007fdfe  mov     rcx, r14; void *
0x18007fe01  mov     [rsp+0C8h+var_80], r15
0x18007fe06  call    memset$thunk$772440563353939046
0x18007fe0b  mov     rbx, rbp
0x18007fe0e  mov     [rsp+0C8h+var_78], rsi
0x18007fe13  mov     [r14+40000h], r13
0x18007fe1a  mov     [rsp+0C8h+var_58], r13
0x18007fe1f  mov     [rsp+0C8h+var_50], r13
0x18007fe24  mov     [rsp+0C8h+var_48], edi
0x18007fe2b  mov     [rsp+0C8h+var_98], r13
0x18007fe30  lea     rcx, [r14+147220h]; void *
0x18007fe37  mov     [rsp+0C8h+var_90], r13
0x18007fe3c  xor     edx, edx; Val
0x18007fe3e  mov     [rsp+0C8h+var_88], r13
0x18007fe43  mov     r8d, 800h; Size
0x18007fe49  mov     r12, r13
0x18007fe4c  call    memset$thunk$772440563353939046
0x18007fe51  mov     rsi, [rsp+0C8h+var_70]
0x18007fe56  lea     rax, [rbx+10000h]
0x18007fe5d  cmp     rax, r15
0x18007fe60  lea     rcx, [r14+147B20h]
0x18007fe67  mov     rdx, r15
0x18007fe6a  mov     [rsp+0C8h+arg_38], rcx
0x18007fe72  cmovbe  rdx, rax
0x18007fe76  lea     r11, [r14+147B24h]
0x18007fe7d  add     rsi, rbx
0x18007fe80  mov     [rsp+0C8h+var_68], rdx
0x18007fe85  mov     [rsp+0C8h+arg_28], r11
0x18007fe8d  lea     r13, [rdx-5]
0x18007fe91  cmp     r13, rsi
0x18007fe94  cmovb   rsi, r13
0x18007fe98  mov     [rsp+0C8h+arg_30], rsi
0x18007fea0  cmp     rbx, rbp
0x18007fea3  jnz     loc_18008054E
0x18007fea9  movzx   eax, byte ptr [rbx]
0x18007feac  mov     edi, 2
0x18007feb1  inc     dword ptr [r14+rax*4+147220h]
0x18007feb9  movzx   eax, byte ptr [rbx]
0x18007febc  inc     rbx
0x18007febf  mov     [r11], al
0x18007fec2  inc     r11
0x18007fec5  mov     [rsp+0C8h+arg_28], r11
0x18007fecd  mov     [rsp+0C8h+arg_8], edi
0x18007fed4  cmp     rbx, r13
0x18007fed7  jb      loc_180080008
0x18007fedd  cmp     rbx, rdx
0x18007fee0  jnb     short loc_18007FF13
0x18007fee2  movzx   eax, byte ptr [rbx]
0x18007fee5  inc     dword ptr [r14+rax*4+147220h]
0x18007feed  movzx   eax, byte ptr [rbx]
0x18007fef0  inc     rbx
0x18007fef3  mov     [r11], al
0x18007fef6  inc     r11
0x18007fef9  lea     eax, [rdi+rdi]
0x18007fefc  test    edi, edi
0x18007fefe  js      loc_18007FFDD
0x18007ff04  mov     edi, eax
0x18007ff06  cmp     rbx, rdx
0x18007ff09  jb      short loc_18007FEE2
0x18007ff0b  mov     [rsp+0C8h+arg_28], r11
0x18007ff13  test    edi, edi
0x18007ff15  jns     loc_18007FFF0
0x18007ff1b  lea     eax, [rdi+rdi]
0x18007ff1e  or      eax, 1
0x18007ff21  mov     [rcx], eax
0x18007ff23  cmp     rbx, r15
0x18007ff26  jb      loc_18007FFFD
0x18007ff2c  inc     dword ptr [r14+147620h]
0x18007ff33  mov     edi, 1
0x18007ff38  xor     r13d, r13d
0x18007ff3b  lea     rcx, [r14+140000h]
0x18007ff42  call    XpressBuildHuffmanEncodings
0x18007ff47  mov     r9, [rsp+0C8h+var_78]
0x18007ff4c  lea     r10, [rax+1Fh]
0x18007ff50  mov     rax, [rsp+0C8h+var_88]
0x18007ff55  add     r10, r12
0x18007ff58  shr     r10, 5
0x18007ff5c  lea     rax, [rax+r10*4]
0x18007ff60  lea     r10, [r9+102h]
0x18007ff67  add     r10, rax
0x18007ff6a  cmp     r10, [rsp+0C8h+var_60]
0x18007ff6f  jnb     short loc_18007FFB5
0x18007ff71  mov     r8, [rsp+0C8h+arg_28]
0x18007ff79  lea     rdx, [r14+147B20h]
0x18007ff80  lea     rcx, [r14+140000h]
0x18007ff87  mov     [rsp+0C8h+var_A8], edi
0x18007ff8b  call    XpressDoHuffmanPass
0x18007ff90  mov     [rsp+0C8h+var_78], rax
0x18007ff95  mov     rcx, rax
0x18007ff98  test    edi, edi
0x18007ff9a  jz      loc_18007FE30
0x18007ffa0  mov     rax, [rsp+0C8h+arg_20]
0x18007ffa8  sub     ecx, [rsp+0C8h+arg_10]
0x18007ffaf  mov     [rax], ecx
0x18007ffb1  xor     eax, eax
0x18007ffb3  jmp     short loc_18007FFBA
0x18007ffb5  mov     eax, 0C0000023h
0x18007ffba  mov     rbx, [rsp+0C8h+arg_18]
0x18007ffc2  add     rsp, 90h
0x18007ffc9  pop     r15
0x18007ffcb  pop     r14
0x18007ffcd  pop     r13
0x18007ffcf  pop     r12
0x18007ffd1  pop     rdi
0x18007ffd2  pop     rsi
0x18007ffd3  pop     rbp
0x18007ffd4  retn
0x18007ffd6  mov     eax, 0C00000BBh
0x18007ffdb  jmp     short loc_18007FFBA
0x18007ffdd  mov     [rcx], eax
0x18007ffdf  mov     edi, 1
0x18007ffe4  mov     rcx, r11
0x18007ffe7  add     r11, 4
0x18007ffeb  jmp     loc_18007FF06
0x18007fff0  add     edi, edi
0x18007fff2  or      edi, 1
0x18007fff5  jl      loc_18007FF1B
0x18007fffb  jmp     short loc_18007FFF0
0x18007fffd  xor     r13d, r13d
0x180080000  mov     edi, r13d
0x180080003  jmp     loc_18007FF3B
0x180080008  mov     rax, rbx
0x18008000b  mov     r10, rbx
0x18008000e  sub     rax, rbp
0x180080011  lea     rbp, cs:180000000h
0x180080018  cqo
0x18008001a  and     edx, 1FFFFh
0x180080020  lea     r9, [rdx+rax]
0x180080024  and     r9d, 1FFFFh
0x18008002b  sub     r9, rdx
0x18008002e  xchg    ax, ax
0x180080030  movzx   ecx, byte ptr [r10+2]
0x180080035  lea     r8, [r10+1]
0x180080039  movzx   edx, ss:rva word_18018F560[rbp+rcx*2]
0x180080041  movzx   ecx, byte ptr [r10]
0x180080045  movzx   eax, ss:rva XpressHashFunction[rbp+rcx*2]
0x18008004d  xor     rdx, rax
0x180080050  movzx   eax, byte ptr [r8]
0x180080054  movzx   eax, ss:rva word_18018F360[rbp+rax*2]
0x18008005c  xor     rdx, rax
0x18008005f  mov     rax, [r14+rdx*8]
0x180080063  mov     [r14+rdx*8], r10
0x180080067  mov     r10, r8
0x18008006a  mov     [r14+r9*8+40000h], rax
0x180080072  inc     r9
0x180080075  and     r9d, 1FFFFh
0x18008007c  cmp     r8, r13
0x18008007f  jb      short loc_180080030
0x180080081  cmp     rbx, rsi
0x180080084  jnb     loc_1800804E8
0x18008008a  mov     r8, [rsp+0C8h+arg_0]
0x180080092  mov     rax, rbx
0x180080095  mov     ebp, [rbx]
0x180080097  sub     rax, r8
0x18008009a  cqo
0x18008009c  mov     r12d, edi
0x18008009f  and     edx, 1FFFFh
0x1800800a5  add     rax, rdx
0x1800800a8  and     eax, 1FFFFh
0x1800800ad  sub     rax, rdx
0x1800800b0  mov     rax, [r14+rax*8+40000h]
0x1800800b8  lea     rcx, [rax+10000h]
0x1800800bf  cmp     rcx, rbx
0x1800800c2  jbe     loc_18008030B
0x1800800c8  mov     ecx, ebp
0x1800800ca  xor     ecx, [rax]
0x1800800cc  jnz     loc_180080348
0x1800800d2  mov     rdi, rbx
0x1800800d5  lea     r15, [rbx-10000h]
0x1800800dc  xor     r11d, r11d
0x1800800df  mov     esi, 3
0x1800800e4  jmp     short loc_18008015F
0x1800800e6  add     rbx, 4
0x1800800ea  add     rax, 4
0x1800800ee  cmp     cl, dl
0x1800800f0  jz      loc_1800802D9
0x1800800f6  sub     rbx, rdi
0x1800800f9  mov     rcx, rax
0x1800800fc  sub     rax, rbx
0x1800800ff  cmp     rbx, rsi
0x180080102  jbe     loc_1800801F7
0x180080108  mov     [rsp+0C8h+var_98], rax
0x18008010d  mov     rsi, rbx
0x180080110  mov     r9, rax
0x180080113  cmp     rcx, rdi
0x180080116  ja      loc_180080204
0x18008011c  mov     r8, [rsp+0C8h+arg_0]
0x180080124  inc     r11
0x180080127  cmp     r11, 0Ch
0x18008012b  jnb     loc_1800801FF
0x180080131  sub     rax, r8
0x180080134  cqo
0x180080136  and     edx, 1FFFFh
0x18008013c  add     rax, rdx
0x18008013f  and     eax, 1FFFFh
0x180080144  sub     rax, rdx
0x180080147  mov     rax, [r14+rax*8+40000h]
0x18008014f  cmp     rax, r15
0x180080152  jbe     loc_1800801FF
0x180080158  cmp     ebp, [rax]
0x18008015a  jnz     short loc_180080124
0x18008015c  mov     rbx, rdi
0x18008015f  add     rbx, 4
0x180080163  add     rax, 4
0x180080167  mov     rdx, [rsp+0C8h+var_80]
0x18008016c  lea     r10, [rbx+20h]
0x180080170  cmp     r10, rdx
0x180080173  jnb     loc_180080404
0x180080179  mov     edx, [rax]
0x18008017b  mov     ecx, [rbx]
0x18008017d  cmp     ecx, edx
0x18008017f  jnz     loc_1800800EE
0x180080185  mov     edx, [rax+4]
0x180080188  mov     ecx, [rbx+4]
0x18008018b  cmp     ecx, edx
0x18008018d  jnz     loc_1800800E6
0x180080193  mov     edx, [rax+8]
0x180080196  mov     ecx, [rbx+8]
0x180080199  cmp     ecx, edx
0x18008019b  jnz     loc_18008039D
0x1800801a1  mov     edx, [rax+0Ch]
0x1800801a4  mov     ecx, [rbx+0Ch]
0x1800801a7  cmp     ecx, edx
0x1800801a9  jnz     loc_1800803C2
0x1800801af  mov     edx, [rax+10h]
0x1800801b2  mov     ecx, [rbx+10h]
0x1800801b5  cmp     ecx, edx
0x1800801b7  jnz     loc_1800803E1
0x1800801bd  mov     edx, [rax+14h]
0x1800801c0  mov     ecx, [rbx+14h]
0x1800801c3  cmp     ecx, edx
0x1800801c5  jnz     loc_1800803EE
0x1800801cb  mov     edx, [rax+18h]
0x1800801ce  mov     ecx, [rbx+18h]
0x1800801d1  cmp     ecx, edx
0x1800801d3  jnz     loc_180080429
0x1800801d9  mov     ecx, [rbx+1Ch]
0x1800801dc  add     rbx, 1Ch
0x1800801e0  mov     edx, [rax+1Ch]
0x1800801e3  cmp     ecx, edx
0x1800801e5  jnz     loc_1800803FB
0x1800801eb  mov     rbx, r10
0x1800801ee  add     rax, 20h ; ' '
0x1800801f2  jmp     loc_180080167
0x1800801f7  add     r11, rbx
0x1800801fa  jmp     loc_18008011C
0x1800801ff  mov     r9, [rsp+0C8h+var_98]
0x180080204  mov     rdx, rdi
0x180080207  lea     rbx, [rsi+rdi]
0x18008020b  sub     rdx, r9
0x18008020e  cmp     rsi, 3
0x180080212  jz      loc_1800803CF
0x180080218  cmp     rdx, 100h
0x18008021f  jnb     loc_180080329
0x180080225  lea     rax, cs:180000000h
0x18008022c  movzx   ecx, byte ptr [rdx+rax+178BB0h]
0x180080234  add     [rsp+0C8h+var_90], rcx
0x180080239  lea     r8, [rsi-3]
0x18008023d  mov     r11, [rsp+0C8h+arg_28]
0x180080245  mov     eax, 1
0x18008024a  shl     rax, cl
0x18008024d  sub     rdx, rax
0x180080250  shl     cl, 4
0x180080253  cmp     r8, 0Fh
0x180080257  jnb     loc_180080370
0x18008025d  add     r8b, cl
0x180080260  lea     r9, [r11+1]
0x180080264  movzx   ecx, r8b
0x180080268  mov     [r11], r8b
0x18008026b  mov     edi, [rsp+0C8h+arg_8]
0x180080272  lea     r11, [r9+2]
  ... truncated ...
```
