# OptimalEncoderDeflate

- ea: `0x180002da0`
- end: `0x18000370a`
- name: `OptimalEncoderDeflate`
- size: `2410`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x1800028e0`

## callees

- `0x180002da0`
- `0x180003760`
- `0x180005b08`
- `0x180005cf8`
- `0x180005d84`
- `0x180005df0`
- `0x180005e58`
- `0x180006384`
- `0x180006514`

## pseudocode

```c
__int64 __fastcall OptimalEncoderDeflate(__int64 a1)
{
  __int64 v1; // rbp
  _DWORD *v2; // rsi
  int i; // ebx
  __int64 v4; // rdx
  unsigned int v5; // ebx
  __int64 v6; // r15
  int v7; // r13d
  unsigned int v8; // r12d
  _WORD *v9; // r14
  unsigned __int64 v10; // rcx
  unsigned int v11; // eax
  int match; // eax
  unsigned int v13; // edi
  __int64 v14; // rdx
  __int64 v15; // rdx
  unsigned int v16; // r9d
  int v17; // r10d
  int v18; // r8d
  int v19; // eax
  unsigned int v20; // r13d
  __int64 v21; // rdi
  __int64 v22; // rbx
  int matched; // eax
  __int64 v24; // r11
  int v25; // edi
  int v26; // edx
  int k; // r9d
  __int64 v28; // rax
  unsigned int v29; // edx
  unsigned int m; // ebx
  unsigned int v31; // edx
  _DWORD *v32; // rcx
  int v33; // edx
  __int64 v34; // rcx
  unsigned int j; // ebx
  int v36; // edi
  __int64 v37; // rax
  int v38; // edx
  __int64 v39; // rcx
  __int64 v40; // r9
  __int64 v41; // r10
  unsigned int v42; // edx
  __int64 v43; // rax
  __int64 v44; // r8
  __int64 v45; // rcx
  int v46; // edx
  int v47; // edi
  int v48; // r9d
  unsigned int v49; // r8d
  char v50; // cl
  char v51; // cl
  __int64 v52; // rdx
  unsigned int v53; // r10d
  unsigned int n; // ebx
  __int64 v55; // rax
  __int64 v56; // rdx
  __int64 v57; // rcx
  int v58; // r11d
  int v59; // r9d
  unsigned int v60; // r8d
  char v61; // cl
  char v62; // cl
  int v63; // eax
  __int64 result; // rax
  unsigned int v65; // [rsp+20h] [rbp-68h]
  unsigned int v66; // [rsp+24h] [rbp-64h]
  int v67; // [rsp+24h] [rbp-64h]
  _DWORD *v68; // [rsp+28h] [rbp-60h]
  unsigned int v69; // [rsp+30h] [rbp-58h]
  __int64 v70; // [rsp+38h] [rbp-50h]
  int v72; // [rsp+98h] [rbp+10h]
  unsigned int v73; // [rsp+98h] [rbp+10h]
  int v74; // [rsp+A0h] [rbp+18h]
  int v75; // [rsp+A0h] [rbp+18h]
  int v76; // [rsp+A0h] [rbp+18h]
  unsigned int v77; // [rsp+A8h] [rbp+20h]
  __int64 v78; // [rsp+A8h] [rbp+20h]

  v1 = *(_QWORD *)(a1 + 88);
  v2 = (_DWORD *)a1;
  for ( i = 50; i > 0; --i )
  {
    v4 = (unsigned int)(v2[8] - i);
    if ( (int)v4 > 0x8000 )
      optimal_insert(v2, v4, (unsigned int)(v4 - 32764));
  }
  v5 = v2[9];
  LODWORD(v6) = v2[8];
  v65 = v5;
  while ( 2 )
  {
    v7 = *(_DWORD *)(v1 + 541168);
    v8 = *(_DWORD *)(v1 + 541164);
    v9 = *(_WORD **)(v1 + 541176);
LABEL_7:
    v72 = v7;
LABEL_8:
    v10 = v1 + 541156;
    while ( (unsigned int)v6 < v5 )
    {
      v11 = *(_DWORD *)(v1 + 541184);
      if ( v2[7] >= v11 )
      {
        *(_DWORD *)(v1 + 541184) = v11 + 1024;
        calculateUpdatedEstimates(v2);
        fixOptimalEstimates(v2);
        v10 = v1 + 541156;
      }
      if ( v2[7] >= 0xFAF8u )
        goto LABEL_96;
      if ( (unsigned __int64)(v9 + 1923) >= v10 )
        break;
      match = optimal_find_match(v2, (unsigned int)v6);
      v66 = match;
      v13 = match;
      if ( match < 3 || (int)v6 + match > v5 && (v13 = v5 - v6, v66 = v5 - v6, (int)(v5 - v6) < 3) )
      {
        ++v2[7];
        ++*(_WORD *)(v1 + 2LL * *(unsigned __int8 *)((unsigned int)v6 + v1) + 553412);
        v14 = *(unsigned __int8 *)((unsigned int)v6 + v1);
        v8 |= *(unsigned __int16 *)(v1 + 2 * v14 + 552836) << v7;
        v7 += *(unsigned __int8 *)(v14 + v1 + 552548);
        v72 = v7;
        if ( v7 >= 16 )
        {
          *v9++ = v8;
          v8 >>= 16;
          v7 -= 16;
          v72 = v7;
        }
        LODWORD(v6) = v6 + 1;
        goto LABEL_8;
      }
      if ( v13 < 0x32 )
      {
        v74 = v6;
        v69 = v6 + 1024;
        v15 = (unsigned int)(v6 + 1);
        v16 = v6 + v13;
        v77 = v6 + v13;
        v17 = v6;
        v18 = *(unsigned __int8 *)(*(unsigned __int8 *)((unsigned int)v6 + v1) + v1 + 555140);
        *(_DWORD *)(v1 + 65820) = v18;
        *(_DWORD *)(v1 + 65816) = v6;
        v19 = v18 + *(unsigned __int8 *)(*(unsigned __int8 *)(v15 + v1) + v1 + 555140);
        *(_DWORD *)(v1 + 65828) = v15;
        *(_DWORD *)(v1 + 65832) = v19;
        if ( v13 >= 3 )
        {
          v20 = 3;
          do
          {
            v21 = 4LL * v20;
            v22 = 12LL * v20;
            matched = match_est(v1, v20++, *(unsigned int *)(v21 + v1 + 81376));
            *(_DWORD *)(v22 + v1 + 65808) = matched;
            *(_DWORD *)(v22 + v1 + 65804) = v6;
            *(_DWORD *)(v22 + v1 + 65800) = *(_DWORD *)(v21 + v1 + 81376);
          }
          while ( v20 <= v66 );
          v2 = (_DWORD *)a1;
          v17 = v6;
          v7 = v72;
          v5 = v65;
          v16 = v77;
        }
        *(_DWORD *)(v1 + 65808) = 0;
        v24 = v1 + 65800 + 12LL * -(int)v6;
        v70 = v24;
        while ( 1 )
        {
          v6 = (unsigned int)(v6 + 1);
          if ( v16 == (_DWORD)v6 )
            break;
          v25 = optimal_find_match(v2, (unsigned int)v6);
          if ( (int)v6 + v25 <= v5 || (v25 = v5 - v6, (int)(v5 - v6) >= 3) )
          {
            if ( v25 > 50 )
              goto LABEL_47;
          }
          else
          {
            v25 = 0;
          }
          if ( (int)v6 + v25 >= v69 )
          {
LABEL_47:
            v24 = v70;
            v33 = *(_DWORD *)(v1 + 4LL * v25 + 81376);
            v34 = 3LL * (unsigned int)(v6 + v25);
            *(_DWORD *)(v70 + 4 * v34) = v33;
            *(_DWORD *)(v70 + 4 * v34 + 4) = v6;
            if ( v33 == 3 && v25 > 16 )
            {
              optimal_insert(v2, (unsigned int)(v6 + 1), (unsigned int)(v6 - 32766));
              goto LABEL_53;
            }
            if ( (unsigned int)v25 > 1 )
            {
              for ( j = 1; j < v25; ++j )
                optimal_insert(v2, (unsigned int)v6 + j, (unsigned int)v6 + j - 32764);
LABEL_53:
              v24 = v70;
            }
            LODWORD(v6) = v6 + v25;
            v17 = v74;
            break;
          }
          v16 = v77;
          v17 = v74;
          if ( v25 >= 3 && v77 < (int)v6 + v25 )
          {
            v26 = 1023;
            if ( (unsigned int)(v25 + v6 - v74) < 0x3FF )
              v26 = v25 + v6 - v74;
            for ( k = v77 - v74 + 1; k <= v26; *(_DWORD *)(v1 + 12 * v28 + 65808) = -1 )
              v28 = k++;
            v16 = v6 + v25;
            v77 = v6 + v25;
          }
          v24 = v70;
          v67 = *(_DWORD *)(v70 + 12 * v6 + 8);
          v29 = *(unsigned __int8 *)(*(unsigned __int8 *)(v6 + v1) + v1 + 555140) + v67;
          if ( v29 < *(_DWORD *)(v70 + 12LL * (unsigned int)(v6 + 1) + 8) )
          {
            *(_DWORD *)(v70 + 12LL * (unsigned int)(v6 + 1) + 8) = v29;
            *(_DWORD *)(v70 + 12LL * (unsigned int)(v6 + 1) + 4) = v6;
          }
          if ( (unsigned int)v25 >= 3 )
          {
            for ( m = 3; m <= v25; ++m )
            {
              v68 = (_DWORD *)(v1 + 4LL * m + 81376);
              v31 = match_est(v1, m, (unsigned int)*v68) + v67;
              v32 = (_DWORD *)(v70 + 12LL * ((unsigned int)v6 + m));
              if ( v31 < v32[2] )
              {
                v32[2] = v31;
                v32[1] = v6;
                *v32 = *v68;
              }
            }
            v2 = (_DWORD *)a1;
            v7 = v72;
            v5 = v65;
            v16 = v77;
            v24 = v70;
            v17 = v74;
          }
        }
        v36 = 0;
        v37 = *(unsigned int *)(v24 + 12LL * (unsigned int)v6 + 4);
        do
        {
          v38 = v37;
          v39 = 3 * v37;
          v37 = *(unsigned int *)(v24 + 12 * v37 + 4);
          ++v36;
          *(_DWORD *)(v24 + 4 * v39 + 4) = v6;
          LODWORD(v6) = v38;
        }
        while ( v38 != v17 );
        v75 = v36;
        do
        {
          v40 = *(unsigned int *)(v24 + 12LL * (unsigned int)v6 + 4);
          v41 = 12LL * (unsigned int)v6;
          if ( (unsigned int)v40 <= (int)v6 + 1 )
          {
            ++v2[7];
            ++*(_WORD *)(v1 + 2LL * *(unsigned __int8 *)((unsigned int)v6 + v1) + 553412);
            v52 = *(unsigned __int8 *)((unsigned int)v6 + v1);
            v8 |= *(unsigned __int16 *)(v1 + 2 * v52 + 552836) << v7;
            v7 += *(unsigned __int8 *)(v52 + v1 + 552548);
            if ( v7 >= 16 )
            {
              *v9++ = v8;
              v8 >>= 16;
              v7 -= 16;
            }
            LODWORD(v6) = v6 + 1;
          }
          else
          {
            v42 = *(_DWORD *)(v24 + 12 * v40);
            v43 = (v42 >> 7) + 256;
            if ( v42 < 0x100 )
              v43 = v42;
            ++v2[7];
            v44 = *((unsigned __int8 *)g_DistLookup + v43);
            v78 = v44;
            v45 = *((unsigned __int8 *)g_LengthLookup + (unsigned int)(v40 - v6 - 3));
            ++*(_WORD *)(v1 + 2 * v45 + 553926);
            ++*(_WORD *)(v1 + 2 * v44 + 555428);
            v46 = (unsigned __int8)g_ExtraDistanceBits[v44];
            v47 = *((unsigned __int8 *)&g_ExtraLengthBits + v45);
            v48 = v7 + *(unsigned __int8 *)(v45 + 257 + v1 + 552548);
            v49 = v8 | (*(unsigned __int16 *)(v1 + 2 * (v45 + 257) + 552836) << v7);
            if ( v48 >= 16 )
            {
              *v9++ = v49;
              v49 >>= 16;
              v48 -= 16;
            }
            if ( v47 )
            {
              v50 = v48;
              v48 += v47;
              v49 |= (((1 << v47) - 1) & (*(_DWORD *)(v41 + v24 + 4) - (_DWORD)v6 - 3)) << v50;
              if ( v48 >= 16 )
              {
                *v9++ = v49;
                v49 >>= 16;
                v48 -= 16;
              }
            }
            v7 = v48 + *(unsigned __int8 *)(v78 + v1 + 541956);
            v8 = v49 | (*(unsigned __int16 *)(v1 + 2 * v78 + 541988) << v48);
            if ( v7 >= 16 )
            {
              *v9++ = v8;
              v8 >>= 16;
              v7 -= 16;
            }
            if ( v46 )
            {
              v51 = v7;
              v7 += v46;
              v8 |= (((1 << v46) - 1) & *(_DWORD *)(v24 + 12LL * *(unsigned int *)(v41 + v24 + 4))) << v51;
              if ( v7 >= 16 )
              {
                *v9++ = v8;
                v8 >>= 16;
                v7 -= 16;
              }
            }
            LODWORD(v6) = *(_DWORD *)(v41 + v24 + 4);
            v36 = v75;
          }
          v75 = --v36;
        }
        while ( v36 );
        v5 = v65;
        goto LABEL_7;
      }
      _mm_lfence();
      v73 = *(_DWORD *)(v1 + 4LL * v13 + 81376);
      if ( v73 == 3 )
      {
        optimal_insert(v2, (unsigned int)(v6 + 1), (unsigned int)(v6 - 32766));
        v53 = 3;
        LODWORD(v6) = v13 + v6;
      }
      else
      {
        for ( n = 1; n < v13; ++n )
          optimal_insert(v2, (unsigned int)v6 + n, (unsigned int)v6 + n - 0x7FFF);
        v53 = v73;
        LODWORD(v6) = v13 + v6;
        v5 = v65;
        if ( v73 >= 0x100 )
        {
          v55 = (v73 >> 7) + 256;
          goto LABEL_84;
        }
      }
      v55 = v53;
LABEL_84:
      ++v2[7];
      v56 = *((unsigned __int8 *)g_DistLookup + v55);
      v76 = (unsigned __int8)g_ExtraDistanceBits[v56];
      v57 = *((unsigned __int8 *)&qword_18000AC20[31] + v13 + 5);
      ++*(_WORD *)(v1 + 2 * v57 + 553926);
      ++*(_WORD *)(v1 + 2 * v56 + 555428);
      v58 = *((unsigned __int8 *)&g_ExtraLengthBits + v57);
      v59 = v7 + *(unsigned __int8 *)(v57 + 257 + v1 + 552548);
      v60 = v8 | (*(unsigned __int16 *)(v1 + 2 * (v57 + 257) + 552836) << v7);
      if ( v59 >= 16 )
      {
        *v9++ = v60;
        v60 >>= 16;
        v59 -= 16;
      }
      if ( v58 )
      {
        v61 = v59;
        v59 += v58;
        v60 |= ((v13 - 3) & ((1 << v58) - 1)) << v61;
        if ( v59 >= 16 )
        {
          *v9++ = v60;
          v60 >>= 16;
          v59 -= 16;
        }
      }
      v7 = v59 + *(unsigned __int8 *)(v56 + v1 + 541956);
      v8 = v60 | (*(unsigned __int16 *)(v1 + 2 * v56 + 541988) << v59);
      v72 = v7;
      if ( v7 >= 16 )
      {
        *v9++ = v8;
        v8 >>= 16;
        v7 -= 16;
        v72 = v7;
      }
      v10 = v1 + 541156;
      if ( v76 )
      {
        v62 = v7;
        v7 += v76;
        v72 = v7;
        v63 = (v53 & ((1 << v76) - 1)) << v62;
        v10 = v1 + 541156;
        v8 |= v63;
        if ( v7 >= 16 )
        {
          *v9++ = v8;
          v8 >>= 16;
          v7 -= 16;
          goto LABEL_7;
        }
      }
    }
    if ( v2[7] < 0xFAF8u && (unsigned __int64)(v9 + 1923) < v10 )
      break;
LABEL_96:
    *v9++ = v8;
    OptimalEncoderOutputBlock(v2);
    fixOptimalEstimates(v2);
    *(_DWORD *)(v1 + 541184) = 1024;
    if ( !*v2 )
      continue;
    break;
  }
  *(_QWORD *)(v1 + 541176) = v9;
  *(_DWORD *)(v1 + 541164) = v8;
  *(_DWORD *)(v1 + 541168) = v7;
  v2[8] = v6;
  result = removeNodes(v2);
  if ( v2[8] == 0x10000 )
    return OptimalEncoderMoveWindows(v2);
  return result;
}

```

## disassembly

```asm
0x180002da0  mov     [rsp+arg_0], rcx
0x180002da5  push    rbx
0x180002da6  push    rbp
0x180002da7  push    rsi
0x180002da8  push    rdi
0x180002da9  push    r12
0x180002dab  push    r13
0x180002dad  push    r14
0x180002daf  push    r15
0x180002db1  sub     rsp, 48h
0x180002db5  mov     rbp, [rcx+58h]
0x180002db9  mov     rsi, rcx
0x180002dbc  mov     ebx, 32h ; '2'
0x180002dc1  mov     edx, [rsi+20h]
0x180002dc4  sub     edx, ebx
0x180002dc6  cmp     edx, 8000h
0x180002dcc  jle     short loc_180002DDD
0x180002dce  lea     r8d, [rdx-7FFCh]
0x180002dd5  mov     rcx, rsi
0x180002dd8  call    optimal_insert
0x180002ddd  dec     ebx
0x180002ddf  test    ebx, ebx
0x180002de1  jg      short loc_180002DC1
0x180002de3  mov     ebx, [rsi+24h]
0x180002de6  mov     r15d, [rsi+20h]
0x180002dea  mov     [rsp+88h+var_68], ebx
0x180002dee  mov     r13d, [rbp+841F0h]
0x180002df5  mov     r12d, [rbp+841ECh]
0x180002dfc  mov     r14, [rbp+841F8h]
0x180002e03  mov     dword ptr [rsp+88h+arg_8], r13d
0x180002e0b  lea     rcx, [rbp+841E4h]
0x180002e12  cmp     r15d, ebx
0x180002e15  jnb     loc_18000367E
0x180002e1b  mov     eax, [rbp+84200h]
0x180002e21  cmp     [rsi+1Ch], eax
0x180002e24  jb      short loc_180002E48
0x180002e26  add     eax, 400h
0x180002e2b  mov     rcx, rsi
0x180002e2e  mov     [rbp+84200h], eax
0x180002e34  call    calculateUpdatedEstimates
0x180002e39  mov     rcx, rsi
0x180002e3c  call    fixOptimalEstimates
0x180002e41  lea     rcx, [rbp+841E4h]
0x180002e48  cmp     dword ptr [rsi+1Ch], 0FAF8h
0x180002e4f  jnb     loc_180003693
0x180002e55  lea     rax, [r14+0F06h]
0x180002e5c  cmp     rax, rcx
0x180002e5f  jnb     loc_18000367E
0x180002e65  mov     edx, r15d
0x180002e68  mov     rcx, rsi
0x180002e6b  call    optimal_find_match
0x180002e70  mov     [rsp+88h+var_64], eax
0x180002e74  mov     edi, eax
0x180002e76  cmp     eax, 3
0x180002e79  jl      short loc_180002E91
0x180002e7b  lea     ecx, [r15+rax]
0x180002e7f  cmp     ecx, ebx
0x180002e81  jbe     short loc_180002EF9
0x180002e83  mov     edi, ebx
0x180002e85  sub     edi, r15d
0x180002e88  mov     [rsp+88h+var_64], edi
0x180002e8c  cmp     edi, 3
0x180002e8f  jge     short loc_180002EF9
0x180002e91  inc     dword ptr [rsi+1Ch]
0x180002e94  mov     ecx, r15d
0x180002e97  movzx   eax, byte ptr [rcx+rbp]
0x180002e9b  inc     word ptr [rbp+rax*2+871C4h]
0x180002ea3  movzx   edx, byte ptr [rcx+rbp]
0x180002ea7  mov     ecx, r13d
0x180002eaa  movzx   eax, word ptr [rbp+rdx*2+86F84h]
0x180002eb2  shl     eax, cl
0x180002eb4  or      r12d, eax
0x180002eb7  movzx   eax, byte ptr [rdx+rbp+86E64h]
0x180002ebf  add     r13d, eax
0x180002ec2  mov     dword ptr [rsp+88h+arg_8], r13d
0x180002eca  cmp     r13d, 10h
0x180002ece  jl      short loc_180002EF1
0x180002ed0  mov     [r14], r12b
0x180002ed3  mov     eax, r12d
0x180002ed6  shr     eax, 8
0x180002ed9  mov     [r14+1], al
0x180002edd  add     r14, 2
0x180002ee1  shr     r12d, 10h
0x180002ee5  add     r13d, 0FFFFFFF0h
0x180002ee9  mov     dword ptr [rsp+88h+arg_8], r13d
0x180002ef1  inc     r15d
0x180002ef4  jmp     loc_180002E0B
0x180002ef9  cmp     edi, 32h ; '2'
0x180002efc  jnb     loc_18000346F
0x180002f02  lea     eax, [r15+400h]
0x180002f09  mov     [rsp+88h+arg_10], r15d
0x180002f11  mov     [rsp+88h+var_58], eax
0x180002f15  lea     edx, [r15+1]
0x180002f19  mov     eax, r15d
0x180002f1c  lea     r9d, [r15+rdi]
0x180002f20  mov     dword ptr [rsp+88h+arg_18], r9d
0x180002f28  mov     r10d, r15d
0x180002f2b  mov     dword ptr [rsp+88h+var_60], 3
0x180002f33  movzx   ecx, byte ptr [rax+rbp]
0x180002f37  movzx   r8d, byte ptr [rcx+rbp+87884h]
0x180002f40  mov     [rbp+1011Ch], r8d
0x180002f47  mov     [rbp+10118h], r15d
0x180002f4e  movzx   ecx, byte ptr [rdx+rbp]
0x180002f52  movzx   eax, byte ptr [rcx+rbp+87884h]
0x180002f5a  add     eax, r8d
0x180002f5d  mov     [rbp+10124h], edx
0x180002f63  mov     [rbp+10128h], eax
0x180002f69  cmp     edi, 3
0x180002f6c  jb      short loc_180002FE5
0x180002f6e  mov     esi, [rsp+88h+var_64]
0x180002f72  mov     r13d, dword ptr [rsp+88h+var_60]
0x180002f77  mov     eax, r13d
0x180002f7a  mov     edx, r13d
0x180002f7d  mov     rcx, rbp
0x180002f80  lea     rdi, ds:0[rax*4]
0x180002f88  mov     r8d, [rdi+rbp+13DE0h]
0x180002f90  lea     rax, [rax+rax*2]
0x180002f94  lea     rbx, ds:0[rax*4]
0x180002f9c  call    match_est
0x180002fa1  inc     r13d
0x180002fa4  mov     [rbx+rbp+10110h], eax
0x180002fab  mov     [rbx+rbp+1010Ch], r15d
0x180002fb3  mov     eax, [rdi+rbp+13DE0h]
0x180002fba  mov     [rbx+rbp+10108h], eax
0x180002fc1  cmp     r13d, esi
0x180002fc4  jbe     short loc_180002F77
0x180002fc6  mov     rsi, [rsp+88h+arg_0]
0x180002fce  mov     r10d, r15d
0x180002fd1  mov     r13d, dword ptr [rsp+88h+arg_8]
0x180002fd9  mov     ebx, [rsp+88h+var_68]
0x180002fdd  mov     r9d, dword ptr [rsp+88h+arg_18]
0x180002fe5  mov     eax, r15d
0x180002fe8  mov     dword ptr [rbp+10110h], 0
0x180002ff2  neg     eax
0x180002ff4  lea     r11, [rbp+10108h]
0x180002ffb  cdqe
0x180002ffd  lea     rcx, [rax+rax*2]
0x180003001  lea     r11, [r11+rcx*4]
0x180003005  mov     [rsp+88h+var_50], r11
0x18000300a  inc     r15d
0x18000300d  cmp     r9d, r15d
0x180003010  jz      loc_18000320F
0x180003016  mov     edx, r15d
0x180003019  mov     rcx, rsi
0x18000301c  call    optimal_find_match
0x180003021  mov     edi, eax
0x180003023  lea     ecx, [r15+rax]
0x180003027  cmp     ecx, ebx
0x180003029  jbe     short loc_180003039
0x18000302b  mov     edi, ebx
0x18000302d  sub     edi, r15d
0x180003030  cmp     edi, 3
0x180003033  jge     short loc_180003039
0x180003035  xor     edi, edi
0x180003037  jmp     short loc_180003042
0x180003039  cmp     edi, 32h ; '2'
0x18000303c  jg      loc_180003181
0x180003042  lea     r8d, [r15+rdi]
0x180003046  cmp     r8d, [rsp+88h+var_58]
0x18000304b  jnb     loc_180003181
0x180003051  mov     r9d, dword ptr [rsp+88h+arg_18]
0x180003059  mov     r10d, [rsp+88h+arg_10]
0x180003061  cmp     edi, 3
0x180003064  jl      short loc_1800030AD
0x180003066  cmp     r9d, r8d
0x180003069  jnb     short loc_1800030AD
0x18000306b  mov     edx, 3FFh
0x180003070  mov     ecx, r15d
0x180003073  sub     ecx, r10d
0x180003076  add     ecx, edi
0x180003078  cmp     ecx, edx
0x18000307a  cmovb   edx, ecx
0x18000307d  sub     r9d, r10d
0x180003080  inc     r9d
0x180003083  cmp     r9d, edx
0x180003086  jg      short loc_1800030A2
0x180003088  movsxd  rax, r9d
0x18000308b  inc     r9d
0x18000308e  lea     rcx, [rax+rax*2]
0x180003092  mov     dword ptr [rbp+rcx*4+10110h], 0FFFFFFFFh
0x18000309d  cmp     r9d, edx
0x1800030a0  jle     short loc_180003088
0x1800030a2  mov     r9d, r8d
0x1800030a5  mov     dword ptr [rsp+88h+arg_18], r8d
0x1800030ad  mov     r11, [rsp+88h+var_50]
0x1800030b2  lea     rax, [r15+r15*2]
0x1800030b6  mov     edx, [r11+rax*4+8]
0x1800030bb  movzx   eax, byte ptr [r15+rbp]
0x1800030c0  mov     [rsp+88h+var_64], edx
0x1800030c4  movzx   ecx, byte ptr [rax+rbp+87884h]
0x1800030cc  lea     eax, [r15+1]
0x1800030d0  lea     rax, [rax+rax*2]
0x1800030d4  add     edx, ecx
0x1800030d6  cmp     edx, [r11+rax*4+8]
0x1800030db  jnb     short loc_1800030E7
0x1800030dd  mov     [r11+rax*4+8], edx
0x1800030e2  mov     [r11+rax*4+4], r15d
0x1800030e7  mov     dword ptr [rsp+88h+var_60], 3
0x1800030ef  cmp     edi, 3
0x1800030f2  jb      loc_18000300A
0x1800030f8  mov     ebx, dword ptr [rsp+88h+var_60]
0x1800030fc  mov     r13, r11
0x1800030ff  mov     esi, [rsp+88h+var_64]
0x180003103  mov     eax, ebx
0x180003105  mov     edx, ebx
0x180003107  mov     rcx, rbp
0x18000310a  lea     rax, ds:13DE0h[rax*4]
0x180003112  add     rax, rbp
0x180003115  mov     [rsp+88h+var_60], rax
0x18000311a  mov     r8d, [rax]
0x18000311d  call    match_est
0x180003122  lea     edx, [rax+rsi]
0x180003125  lea     eax, [r15+rbx]
0x180003129  lea     rax, [rax+rax*2]
0x18000312d  lea     rcx, ds:0[rax*4]
0x180003135  add     rcx, r13
0x180003138  cmp     edx, [rcx+8]
0x18000313b  jnb     short loc_18000314D
0x18000313d  mov     rax, [rsp+88h+var_60]
0x180003142  mov     [rcx+8], edx
0x180003145  mov     [rcx+4], r15d
0x180003149  mov     eax, [rax]
0x18000314b  mov     [rcx], eax
0x18000314d  inc     ebx
0x18000314f  cmp     ebx, edi
0x180003151  jbe     short loc_180003103
0x180003153  mov     rsi, [rsp+88h+arg_0]
0x18000315b  mov     r13d, dword ptr [rsp+88h+arg_8]
0x180003163  mov     ebx, [rsp+88h+var_68]
0x180003167  mov     r9d, dword ptr [rsp+88h+arg_18]
0x18000316f  mov     r11, [rsp+88h+var_50]
0x180003174  mov     r10d, [rsp+88h+arg_10]
0x18000317c  jmp     loc_18000300A
0x180003181  mov     r11, [rsp+88h+var_50]
0x180003186  movsxd  rax, edi
0x180003189  mov     edx, [rbp+rax*4+13DE0h]
0x180003190  lea     eax, [r15+rdi]
0x180003194  mov     dword ptr [rsp+88h+arg_18], eax
0x18000319b  lea     rcx, [rax+rax*2]
0x18000319f  mov     [r11+rcx*4], edx
0x1800031a3  mov     [r11+rcx*4+4], r15d
0x1800031a8  cmp     edx, 3
0x1800031ab  jnz     short loc_1800031C7
0x1800031ad  cmp     edi, 10h
0x1800031b0  jle     short loc_1800031C7
0x1800031b2  lea     r8d, [r15-7FFEh]
0x1800031b9  mov     rcx, rsi
0x1800031bc  lea     edx, [r15+1]
0x1800031c0  call    optimal_insert
0x1800031c5  jmp     short loc_1800031FA
0x1800031c7  mov     dword ptr [rsp+88h+arg_8], 1
0x1800031d2  cmp     edi, 1
0x1800031d5  jbe     short loc_1800031FF
0x1800031d7  mov     ebx, dword ptr [rsp+88h+arg_8]
0x1800031de  lea     r8d, [rbx-7FFCh]
0x1800031e5  mov     rcx, rsi
0x1800031e8  add     r8d, r15d
0x1800031eb  lea     edx, [r15+rbx]
0x1800031ef  call    optimal_insert
0x1800031f4  inc     ebx
0x1800031f6  cmp     ebx, edi
0x1800031f8  jb      short loc_1800031DE
0x1800031fa  mov     r11, [rsp+88h+var_50]
0x1800031ff  mov     r15d, dword ptr [rsp+88h+arg_18]
0x180003207  mov     r10d, [rsp+88h+arg_10]
0x18000320f  mov     eax, r15d
0x180003212  xor     edi, edi
0x180003214  lea     rcx, [rax+rax*2]
0x180003218  mov     eax, [r11+rcx*4+4]
0x18000321d  mov     edx, eax
0x18000321f  lea     rcx, [rax+rax*2]
0x180003223  mov     eax, [r11+rcx*4+4]
0x180003228  inc     edi
0x18000322a  mov     [r11+rcx*4+4], r15d
0x18000322f  mov     r15d, edx
0x180003232  cmp     edx, r10d
0x180003235  jnz     short loc_18000321D
0x180003237  mov     [rsp+88h+arg_10], edi
0x18000323e  lea     rbx, cs:180000000h
0x180003245  mov     ecx, r15d
0x180003248  lea     r8d, [r15+1]
0x18000324c  lea     rax, [rcx+rcx*2]
0x180003250  mov     r9d, [r11+rax*4+4]
0x180003255  lea     r10, ds:0[rax*4]
0x18000325d  cmp     r9d, r8d
0x180003260  jbe     loc_180003406
0x180003266  lea     rcx, [r9+r9*2]
0x18000326a  mov     edx, [r11+rcx*4]
0x18000326e  mov     eax, edx
0x180003270  shr     eax, 7
0x180003273  add     eax, 100h
0x180003278  cmp     edx, 100h
0x18000327e  cmovb   eax, edx
0x180003281  inc     dword ptr [rsi+1Ch]
0x180003284  sub     r9d, r15d
0x180003287  sub     r9d, 3
0x18000328b  movzx   r8d, byte ptr [rax+rbx+0AB20h]
0x180003294  mov     [rsp+88h+arg_18], r8
0x18000329c  movzx   ecx, byte ptr [r9+rbx+0AD20h]
0x1800032a5  inc     word ptr [rbp+rcx*2+873C6h]
  ... truncated ...
```
