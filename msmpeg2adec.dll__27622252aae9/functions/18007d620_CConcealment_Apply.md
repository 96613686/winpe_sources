# CConcealment_Apply

- ea: `0x18007d620`
- end: `0x18007de9b`
- name: `CConcealment_Apply`
- size: `2171`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180034030`
- `0x180074560`

## callees

- `0x1800017b0`
- `0x180002184`
- `0x1800021a8`
- `0x18007d620`
- `0x18007deb0`
- `0x18007e4f0`
- `0x18007e5d0`

## import_xrefs

- `mfperfhelper!__imp_ippsZero_8u` at `0x18007dd64`
- `mfperfhelper!__imp_ippsZero_8u` at `0x18007dd64`
- `mfperfhelper!__imp_ippsCopy_8u` at `0x18007d6ec`
- `mfperfhelper!__imp_ippsCopy_8u` at `0x18007d9ed`
- `mfperfhelper!__imp_ippsCopy_8u` at `0x18007d6ec`
- `mfperfhelper!__imp_ippsCopy_8u` at `0x18007d9ed`

## pseudocode

```c
__int64 __fastcall CConcealment_Apply(__int64 a1, __int64 a2, char a3)
{
  __int64 v3; // r14
  char v4; // di
  __int64 v5; // r12
  __int64 v6; // r15
  char v7; // al
  char v8; // cl
  char v9; // al
  char v10; // cl
  int v11; // r9d
  _DWORD *v12; // rdx
  BOOL v13; // r8d
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  __int64 v17; // rdi
  int v18; // eax
  __int64 *v19; // rbp
  int v20; // r13d
  int v21; // edi
  int v22; // ebx
  __int64 v23; // rsi
  int v24; // ebx
  __int64 v25; // r12
  float v26; // xmm1_4
  __int64 v27; // rax
  int v28; // esi
  __int64 v29; // rdi
  int v30; // ebx
  __int64 v31; // rcx
  __int64 v32; // rcx
  int v33; // ebx
  char v34; // cl
  int v35; // edx
  __int64 i; // rdx
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  int v40; // ecx
  __int64 result; // rax
  int v42; // ecx
  int v43; // ecx
  __int64 j; // rdx
  __int64 k; // rcx
  int v47; // [rsp+34h] [rbp-214h]
  int v49; // [rsp+40h] [rbp-208h] BYREF
  _BYTE v50[204]; // [rsp+44h] [rbp-204h] BYREF
  float v51[52]; // [rsp+110h] [rbp-138h] BYREF

  v3 = *(_QWORD *)(a1 + 48);
  v4 = a3;
  v5 = a2;
  v49 = 0;
  memset_0(v50, 0, 0xC8u);
  v6 = *(_QWORD *)(v5 + 16);
  v7 = *(_BYTE *)(v3 + 4096);
  if ( v4 )
  {
    v8 = *(_BYTE *)(v5 + 26);
    *(_BYTE *)(v5 + 26) = v7;
    v9 = *(_BYTE *)(v3 + 4097);
    *(_BYTE *)(v3 + 4096) = v8;
    v10 = *(_BYTE *)(v5 + 27);
    *(_BYTE *)(v5 + 27) = v9;
    *(_BYTE *)(v3 + 4097) = v10;
    VectorSwap_SSE(v6, v3);
  }
  else
  {
    *(_BYTE *)(v5 + 26) = v7;
    *(_BYTE *)(v5 + 27) = *(_BYTE *)(v3 + 4097);
    ippsCopy_8u(v3, v6, 4096);
  }
  v11 = *(_DWORD *)(v3 + 4108);
  v12 = (_DWORD *)(v3 + 4104);
  v13 = v11 || *v12 && v4;
  v14 = *(_DWORD *)(v3 + 4116);
  if ( !v14 )
  {
    if ( v13 )
      goto LABEL_26;
    goto LABEL_25;
  }
  v15 = v14 - 1;
  if ( v15 )
  {
    v16 = v15 - 1;
    if ( v16 )
    {
      if ( v16 != 1 )
        goto LABEL_26;
      if ( v13 )
      {
        if ( ++*(_DWORD *)(v3 + 4112) == *(_DWORD *)(v3 + 4120) )
          *(_QWORD *)(v3 + 4112) = 0;
        goto LABEL_26;
      }
      *(_DWORD *)(v3 + 4112) = 0;
LABEL_25:
      *(_DWORD *)(v3 + 4116) = 1;
      goto LABEL_26;
    }
    if ( v13 )
    {
      if ( ++*(_DWORD *)(v3 + 4112) >= *(_DWORD *)(v3 + 4124) )
      {
        *(_DWORD *)(v3 + 4112) = 0;
        *(_DWORD *)(v3 + 4116) = 3;
      }
    }
  }
  else if ( v13 )
  {
    *(_QWORD *)(v3 + 4112) = 0;
  }
  else if ( ++*(_DWORD *)(v3 + 4112) == *(_DWORD *)(v3 + 4128) )
  {
    *(_DWORD *)(v3 + 4112) = 0;
    *(_DWORD *)(v3 + 4116) = 2;
  }
LABEL_26:
  if ( v11 )
    goto LABEL_56;
  if ( v4 && *(_DWORD *)(v3 + 4104) )
  {
    if ( *(_BYTE *)(v5 + 27) == 2 )
    {
      v17 = 4LL * *(char *)(v5 + 31);
      if ( *(_BYTE *)(v3 + 4097) == 2 )
      {
        v18 = 0;
        v19 = (__int64 *)(&off_18008B4A8)[v17];
        v20 = SLOBYTE(qword_18008B4A0[v17]);
        *(_WORD *)(v5 + 26) = 513;
        v47 = 0;
        do
        {
          v21 = *(char *)(v5 + 31);
          v22 = v18;
          v23 = v6 + 4LL * v18;
          CConcealment_CalcBandEnergy(v6 + 4 * v18, 2, v21, 0, (__int64)&v49);
          CConcealment_CalcBandEnergy(v3 + 4 * v22, 2, v21, 0, (__int64)v51);
          v24 = 0;
          v25 = 0;
          if ( v20 > 0 )
          {
            while ( 1 )
            {
              v26 = pow((float)(v51[v25] / *(float *)&v50[4 * v25 - 4]), 0.25);
              if ( v24 < *((__int16 *)v19 + v25 + 1) )
                break;
LABEL_36:
              v25 = (unsigned int)(v25 + 1);
              if ( (int)v25 >= v20 )
                goto LABEL_37;
            }
            while ( v24 < 1024 )
            {
              v27 = v24++;
              *(float *)(v23 + 4 * v27) = v26 * *(float *)(v23 + 4 * v27);
              if ( v24 >= *((__int16 *)v19 + v25 + 1) )
                goto LABEL_36;
            }
          }
LABEL_37:
          v5 = a2;
          v18 = v47 + 128;
          v47 = v18;
        }
        while ( v18 != 1024 );
        goto LABEL_44;
      }
      v28 = SBYTE4(SamplingRateInfoTable[v17]);
      v29 = *(__int64 *)((char *)&off_18008B498 + v17 * 8);
      v30 = *(char *)(v5 + 31);
      CConcealment_CalcBandEnergy(v6 + 3584, 2, v30, 1, (__int64)v51);
      CConcealment_CalcBandEnergy(v3, 0, v30, 0, (__int64)&v49);
      *(_WORD *)(v5 + 26) = 768;
      ippsCopy_8u(v31, v6, 4096);
    }
    else
    {
      v32 = *(char *)(v5 + 31);
      v33 = *(char *)(v5 + 31);
      v28 = SBYTE4(SamplingRateInfoTable[4 * v32]);
      v29 = (__int64)*(&off_18008B498 + 4 * v32);
      CConcealment_CalcBandEnergy(v6, 0, v33, 0, (__int64)&v49);
      v34 = *(_BYTE *)(v3 + 4097);
      v35 = 2;
      *(_BYTE *)(v5 + 26) = v34 == 2;
      *(_BYTE *)(v5 + 27) = v34 == 2;
      if ( v34 != 2 )
        v35 = 0;
      CConcealment_CalcBandEnergy(v3, v35, v33, v34 == 2, (__int64)v51);
    }
    CConcealment_InterpolateBuffer(v6, (unsigned int)&v49, (unsigned int)v51, v28, v29);
LABEL_44:
    v4 = a3;
  }
  for ( i = 0; i != 1024; i += 4 )
  {
    if ( *(float *)&sbr_randomPhase[2 * *(int *)(v3 + 4100)] < 0.0 )
      *(_DWORD *)(v6 + 4 * i) ^= _xmm;
    v37 = ((unsigned __int16)*(_DWORD *)(v3 + 4100) + 1) & 0x1FF;
    *(_DWORD *)(v3 + 4100) = ((unsigned __int16)*(_DWORD *)(v3 + 4100) + 1) & 0x1FF;
    if ( *(float *)&sbr_randomPhase[2 * v37] < 0.0 )
      *(_DWORD *)(v6 + 4 * i + 4) ^= _xmm;
    v38 = ((unsigned __int16)*(_DWORD *)(v3 + 4100) + 1) & 0x1FF;
    *(_DWORD *)(v3 + 4100) = ((unsigned __int16)*(_DWORD *)(v3 + 4100) + 1) & 0x1FF;
    if ( *(float *)&sbr_randomPhase[2 * v38] < 0.0 )
      *(_DWORD *)(v6 + 4 * i + 8) ^= _xmm;
    v39 = ((unsigned __int16)*(_DWORD *)(v3 + 4100) + 1) & 0x1FF;
    *(_DWORD *)(v3 + 4100) = ((unsigned __int16)*(_DWORD *)(v3 + 4100) + 1) & 0x1FF;
    if ( *(float *)&sbr_randomPhase[2 * v39] < 0.0 )
      *(_DWORD *)(v6 + 4 * i + 12) ^= _xmm;
    *(_DWORD *)(v3 + 4100) = ((unsigned __int16)*(_DWORD *)(v3 + 4100) + 1) & 0x1FF;
  }
  v12 = (_DWORD *)(v3 + 4104);
LABEL_56:
  v40 = *(_DWORD *)(v3 + 4116);
  *v12 = *(_DWORD *)(v3 + 4108);
  result = (unsigned int)v4;
  *(_DWORD *)(v3 + 4108) = result;
  v42 = v40 - 1;
  if ( v42 )
  {
    v43 = v42 - 1;
    if ( v43 )
    {
      if ( v43 == 1 )
      {
        for ( j = 0; j != 1024; j += 8 )
        {
          *(float *)(v6 + 4 * j) = *(float *)&dword_1800A312C[*(_DWORD *)(v3 + 4120) - *(_DWORD *)(v3 + 4112)]
                                 * *(float *)(v6 + 4 * j);
          *(float *)(v6 + 4 * j + 4) = *(float *)&dword_1800A312C[*(_DWORD *)(v3 + 4120) - *(_DWORD *)(v3 + 4112)]
                                     * *(float *)(v6 + 4 * j + 4);
          *(float *)(v6 + 4 * j + 8) = *(float *)&dword_1800A312C[*(_DWORD *)(v3 + 4120) - *(_DWORD *)(v3 + 4112)]
                                     * *(float *)(v6 + 4 * j + 8);
          *(float *)(v6 + 4 * j + 12) = *(float *)&dword_1800A312C[*(_DWORD *)(v3 + 4120) - *(_DWORD *)(v3 + 4112)]
                                      * *(float *)(v6 + 4 * j + 12);
          *(float *)(v6 + 4 * j + 16) = *(float *)&dword_1800A312C[*(_DWORD *)(v3 + 4120) - *(_DWORD *)(v3 + 4112)]
                                      * *(float *)(v6 + 4 * j + 16);
          *(float *)(v6 + 4 * j + 20) = *(float *)&dword_1800A312C[*(_DWORD *)(v3 + 4120) - *(_DWORD *)(v3 + 4112)]
                                      * *(float *)(v6 + 4 * j + 20);
          *(float *)(v6 + 4 * j + 24) = *(float *)&dword_1800A312C[*(_DWORD *)(v3 + 4120) - *(_DWORD *)(v3 + 4112)]
                                      * *(float *)(v6 + 4 * j + 24);
          result = (unsigned int)(*(_DWORD *)(v3 + 4120) - *(_DWORD *)(v3 + 4112));
          *(float *)(v6 + 4 * j + 28) = *(float *)&dword_1800A312C[(int)result] * *(float *)(v6 + 4 * j + 28);
        }
      }
    }
    else
    {
      return ippsZero_8u(v3, 4096);
    }
  }
  else
  {
    for ( k = 0; k != 1024; k += 8 )
    {
      *(float *)(v6 + 4 * k) = *(float *)&dword_1800A3130[*(int *)(v3 + 4112)] * *(float *)(v6 + 4 * k);
      *(float *)(v6 + 4 * k + 4) = *(float *)&dword_1800A3130[*(int *)(v3 + 4112)] * *(float *)(v6 + 4 * k + 4);
      *(float *)(v6 + 4 * k + 8) = *(float *)&dword_1800A3130[*(int *)(v3 + 4112)] * *(float *)(v6 + 4 * k + 8);
      *(float *)(v6 + 4 * k + 12) = *(float *)&dword_1800A3130[*(int *)(v3 + 4112)] * *(float *)(v6 + 4 * k + 12);
      *(float *)(v6 + 4 * k + 16) = *(float *)&dword_1800A3130[*(int *)(v3 + 4112)] * *(float *)(v6 + 4 * k + 16);
      *(float *)(v6 + 4 * k + 20) = *(float *)&dword_1800A3130[*(int *)(v3 + 4112)] * *(float *)(v6 + 4 * k + 20);
      *(float *)(v6 + 4 * k + 24) = *(float *)&dword_1800A3130[*(int *)(v3 + 4112)] * *(float *)(v6 + 4 * k + 24);
      result = *(int *)(v3 + 4112);
      *(float *)(v6 + 4 * k + 28) = *(float *)&dword_1800A3130[result] * *(float *)(v6 + 4 * k + 28);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18007d620  mov     r11, rsp
0x18007d623  push    r14
0x18007d625  push    r15
0x18007d627  sub     rsp, 238h
0x18007d62e  mov     rax, cs:__security_cookie
0x18007d635  xor     rax, rsp
0x18007d638  mov     [rsp+248h+var_68], rax
0x18007d640  mov     r14, [rcx+30h]
0x18007d644  lea     rcx, [rsp+248h+var_204]; void *
0x18007d649  mov     [r11+18h], rbx
0x18007d64d  mov     [r11-28h], rdi
0x18007d651  movzx   edi, r8b
0x18007d655  mov     [r11-30h], r12
0x18007d659  mov     r12, rdx
0x18007d65c  mov     [rsp+248h+var_218], r8b
0x18007d661  mov     r8d, 0C8h; Size
0x18007d667  mov     [rsp+248h+var_210], rdx
0x18007d66c  xor     edx, edx; Val
0x18007d66e  movaps  xmmword ptr [r11-58h], xmm7
0x18007d673  xorps   xmm7, xmm7
0x18007d676  mov     [rsp+248h+var_208], 0
0x18007d67e  call    memset_0
0x18007d683  mov     r15, [r12+10h]
0x18007d688  movzx   eax, byte ptr [r14+1000h]
0x18007d690  test    dil, dil
0x18007d693  jz      short loc_18007D6CE
0x18007d695  movzx   ecx, byte ptr [r12+1Ah]
0x18007d69b  mov     rdx, r14
0x18007d69e  mov     [r12+1Ah], al
0x18007d6a3  movzx   eax, byte ptr [r14+1001h]
0x18007d6ab  mov     [r14+1000h], cl
0x18007d6b2  movzx   ecx, byte ptr [r12+1Bh]
0x18007d6b8  mov     [r12+1Bh], al
0x18007d6bd  mov     [r14+1001h], cl
0x18007d6c4  mov     rcx, r15
0x18007d6c7  call    VectorSwap_SSE
0x18007d6cc  jmp     short loc_18007D6F8
0x18007d6ce  mov     [r12+1Ah], al
0x18007d6d3  mov     r8d, 1000h
0x18007d6d9  movzx   eax, byte ptr [r14+1001h]
0x18007d6e1  mov     rdx, r15
0x18007d6e4  mov     rcx, r14
0x18007d6e7  mov     [r12+1Bh], al
0x18007d6ec  call    cs:__imp_ippsCopy_8u
0x18007d6f3  nop     dword ptr [rax+rax+00h]
0x18007d6f8  mov     r9d, [r14+100Ch]
0x18007d6ff  lea     rdx, [r14+1008h]
0x18007d706  test    r9d, r9d
0x18007d709  jnz     short loc_18007D71A
0x18007d70b  cmp     [rdx], r9d
0x18007d70e  jz      short loc_18007D715
0x18007d710  test    dil, dil
0x18007d713  jnz     short loc_18007D71A
0x18007d715  xor     r8d, r8d
0x18007d718  jmp     short loc_18007D720
0x18007d71a  mov     r8d, 1
0x18007d720  mov     ecx, [r14+1014h]
0x18007d727  mov     r10d, 2
0x18007d72d  test    ecx, ecx
0x18007d72f  jz      loc_18007D7F6
0x18007d735  sub     ecx, 1
0x18007d738  jz      short loc_18007D7B9
0x18007d73a  sub     ecx, 1
0x18007d73d  jz      short loc_18007D785
0x18007d73f  cmp     ecx, 1
0x18007d742  jnz     loc_18007D806
0x18007d748  test    r8d, r8d
0x18007d74b  jz      short loc_18007D778
0x18007d74d  inc     dword ptr [r14+1010h]
0x18007d754  mov     eax, [r14+1010h]
0x18007d75b  cmp     eax, [r14+1018h]
0x18007d762  jnz     loc_18007D806
0x18007d768  mov     qword ptr [r14+1010h], 0
0x18007d773  jmp     loc_18007D806
0x18007d778  mov     dword ptr [r14+1010h], 0
0x18007d783  jmp     short loc_18007D7FB
0x18007d785  test    r8d, r8d
0x18007d788  jz      short loc_18007D806
0x18007d78a  inc     dword ptr [r14+1010h]
0x18007d791  mov     eax, [r14+1010h]
0x18007d798  cmp     eax, [r14+101Ch]
0x18007d79f  jl      short loc_18007D806
0x18007d7a1  mov     dword ptr [r14+1010h], 0
0x18007d7ac  mov     dword ptr [r14+1014h], 3
0x18007d7b7  jmp     short loc_18007D806
0x18007d7b9  test    r8d, r8d
0x18007d7bc  jz      short loc_18007D7CB
0x18007d7be  mov     qword ptr [r14+1010h], 0
0x18007d7c9  jmp     short loc_18007D806
0x18007d7cb  inc     dword ptr [r14+1010h]
0x18007d7d2  mov     eax, [r14+1010h]
0x18007d7d9  cmp     eax, [r14+1020h]
0x18007d7e0  jnz     short loc_18007D806
0x18007d7e2  mov     dword ptr [r14+1010h], 0
0x18007d7ed  mov     [r14+1014h], r10d
0x18007d7f4  jmp     short loc_18007D806
0x18007d7f6  test    r8d, r8d
0x18007d7f9  jnz     short loc_18007D806
0x18007d7fb  mov     dword ptr [r14+1014h], 1
0x18007d806  lea     r8, __ImageBase
0x18007d80d  test    r9d, r9d
0x18007d810  jnz     loc_18007DBA7
0x18007d816  test    dil, dil
0x18007d819  jz      loc_18007DAB0
0x18007d81f  cmp     [r14+1008h], r9d
0x18007d826  jz      loc_18007DAB0
0x18007d82c  mov     [rsp+248h+var_20], rsi
0x18007d834  cmp     [r12+1Bh], r10b
0x18007d839  jnz     loc_18007D9FE
0x18007d83f  movsx   rax, byte ptr [r12+1Fh]
0x18007d845  mov     rdi, rax
0x18007d848  shl     rdi, 5
0x18007d84c  cmp     [r14+1001h], r10b
0x18007d853  jnz     loc_18007D98A
0x18007d859  mov     [rsp+248h+var_18], rbp
0x18007d861  xor     eax, eax
0x18007d863  mov     rbp, [rdi+r8+8B4A8h]
0x18007d86b  mov     [rsp+248h+var_38], r13
0x18007d873  movsx   r13d, byte ptr [rdi+r8+8B4A0h]
0x18007d87c  movaps  [rsp+248h+var_48], xmm6
0x18007d884  movsd   xmm6, cs:__real@3fd0000000000000
0x18007d88c  mov     word ptr [r12+1Ah], 201h
0x18007d894  mov     [rsp+248h+var_214], eax
0x18007d898  nop     dword ptr [rax+rax+00000000h]
0x18007d8a0  movsx   edi, byte ptr [r12+1Fh]
0x18007d8a6  xor     r9d, r9d
0x18007d8a9  movsxd  rbx, eax
0x18007d8ac  mov     r8d, edi
0x18007d8af  lea     rax, [rsp+248h+var_208]
0x18007d8b4  mov     edx, r10d
0x18007d8b7  mov     [rsp+248h+var_228], rax
0x18007d8bc  lea     rsi, [r15+rbx*4]
0x18007d8c0  mov     rcx, rsi
0x18007d8c3  call    CConcealment_CalcBandEnergy
0x18007d8c8  lea     rax, [rsp+248h+var_138]
0x18007d8d0  xor     r9d, r9d
0x18007d8d3  lea     rcx, [r14+rbx*4]
0x18007d8d7  mov     [rsp+248h+var_228], rax
0x18007d8dc  mov     r8d, edi
0x18007d8df  mov     edx, 2
0x18007d8e4  call    CConcealment_CalcBandEnergy
0x18007d8e9  xor     ebx, ebx
0x18007d8eb  xor     r12d, r12d
0x18007d8ee  test    r13d, r13d
0x18007d8f1  jle     short loc_18007D94C
0x18007d8f3  movss   xmm0, [rsp+r12*4+248h+var_138]
0x18007d8fd  movaps  xmm1, xmm6; Y
0x18007d900  divss   xmm0, [rsp+r12*4+248h+var_208]
0x18007d907  cvtps2pd xmm0, xmm0; X
0x18007d90a  call    pow
0x18007d90f  movsx   eax, word ptr [rbp+r12*2+2]
0x18007d915  xorps   xmm1, xmm1
0x18007d918  cvtsd2ss xmm1, xmm0
0x18007d91c  cmp     ebx, eax
0x18007d91e  jge     short loc_18007D944
0x18007d920  cmp     ebx, 400h
0x18007d926  jge     short loc_18007D94C
0x18007d928  movsxd  rax, ebx
0x18007d92b  movaps  xmm0, xmm1
0x18007d92e  inc     ebx
0x18007d930  mulss   xmm0, dword ptr [rsi+rax*4]
0x18007d935  movss   dword ptr [rsi+rax*4], xmm0
0x18007d93a  movsx   eax, word ptr [rbp+r12*2+2]
0x18007d940  cmp     ebx, eax
0x18007d942  jl      short loc_18007D920
0x18007d944  inc     r12d
0x18007d947  cmp     r12d, r13d
0x18007d94a  jl      short loc_18007D8F3
0x18007d94c  mov     eax, [rsp+248h+var_214]
0x18007d950  mov     r10d, 2
0x18007d956  mov     r12, [rsp+248h+var_210]
0x18007d95b  sub     eax, 0FFFFFF80h
0x18007d95e  mov     [rsp+248h+var_214], eax
0x18007d962  cmp     eax, 400h
0x18007d967  jnz     loc_18007D8A0
0x18007d96d  movaps  xmm6, [rsp+248h+var_48]
0x18007d975  mov     r13, [rsp+248h+var_38]
0x18007d97d  mov     rbp, [rsp+248h+var_18]
0x18007d985  jmp     loc_18007DA9C
0x18007d98a  movsx   esi, byte ptr [rdi+r8+8B494h]
0x18007d993  lea     rcx, [r15+0E00h]
0x18007d99a  mov     rdi, [rdi+r8+8B498h]
0x18007d9a2  mov     ebx, eax
0x18007d9a4  lea     rax, [rsp+248h+var_138]
0x18007d9ac  mov     r8d, ebx
0x18007d9af  mov     r9d, 1
0x18007d9b5  mov     [rsp+248h+var_228], rax
0x18007d9ba  mov     edx, r10d
0x18007d9bd  call    CConcealment_CalcBandEnergy
0x18007d9c2  lea     rcx, [rsp+248h+var_208]
0x18007d9c7  xor     r9d, r9d
0x18007d9ca  mov     [rsp+248h+var_228], rcx
0x18007d9cf  mov     r8d, ebx
0x18007d9d2  mov     rcx, r14
0x18007d9d5  xor     edx, edx
0x18007d9d7  call    CConcealment_CalcBandEnergy
0x18007d9dc  mov     r8d, 1000h
0x18007d9e2  mov     word ptr [r12+1Ah], 300h
0x18007d9ea  mov     rdx, r15
0x18007d9ed  call    cs:__imp_ippsCopy_8u
0x18007d9f4  nop     dword ptr [rax+rax+00h]
0x18007d9f9  jmp     loc_18007DA7F
0x18007d9fe  movsx   rcx, byte ptr [r12+1Fh]
0x18007da04  xor     r9d, r9d
0x18007da07  mov     rax, rcx
0x18007da0a  mov     ebx, ecx
0x18007da0c  shl     rax, 5
0x18007da10  xor     edx, edx
0x18007da12  movsx   esi, byte ptr [rax+r8+8B494h]
0x18007da1b  mov     rdi, [rax+r8+8B498h]
0x18007da23  lea     rax, [rsp+248h+var_208]
0x18007da28  mov     r8d, ecx
0x18007da2b  mov     [rsp+248h+var_228], rax
0x18007da30  mov     rcx, r15
0x18007da33  call    CConcealment_CalcBandEnergy
0x18007da38  movzx   ecx, byte ptr [r14+1001h]
0x18007da40  mov     edx, 2
0x18007da45  cmp     cl, 2
0x18007da48  mov     r8d, ebx
0x18007da4b  setz    al
0x18007da4e  xor     r9d, r9d
0x18007da51  cmp     cl, 2
0x18007da54  mov     [r12+1Ah], al
0x18007da59  mov     [r12+1Bh], al
0x18007da5e  setz    r9b
0x18007da62  xor     eax, eax
0x18007da64  cmp     cl, 2
0x18007da67  mov     rcx, r14
0x18007da6a  cmovnz  edx, eax
0x18007da6d  lea     rax, [rsp+248h+var_138]
0x18007da75  mov     [rsp+248h+var_228], rax
0x18007da7a  call    CConcealment_CalcBandEnergy
0x18007da7f  mov     r9d, esi
0x18007da82  mov     [rsp+248h+var_228], rdi
0x18007da87  lea     r8, [rsp+248h+var_138]
0x18007da8f  mov     rcx, r15
0x18007da92  lea     rdx, [rsp+248h+var_208]
0x18007da97  call    CConcealment_InterpolateBuffer
0x18007da9c  movzx   edi, [rsp+248h+var_218]
0x18007daa1  lea     r8, __ImageBase
0x18007daa8  mov     rsi, [rsp+248h+var_20]
0x18007dab0  movss   xmm1, dword ptr cs:__xmm@80000000800000008000000080000000
0x18007dab8  xor     edx, edx
0x18007daba  nop     word ptr [rax+rax+00h]
0x18007dac0  movsxd  rax, dword ptr [r14+1004h]
0x18007dac7  comiss  xmm7, ds:rva sbr_randomPhase[r8+rax*8]
0x18007dad0  jbe     short loc_18007DAE1
0x18007dad2  movss   xmm0, dword ptr [r15+rdx*4]
0x18007dad8  xorps   xmm0, xmm1
0x18007dadb  movss   dword ptr [r15+rdx*4], xmm0
0x18007dae1  mov     eax, [r14+1004h]
0x18007dae8  inc     eax
0x18007daea  and     eax, 1FFh
0x18007daef  mov     ecx, eax
0x18007daf1  mov     [r14+1004h], ecx
0x18007daf8  comiss  xmm7, ds:rva sbr_randomPhase[r8+rax*8]
0x18007db01  jbe     short loc_18007DB14
0x18007db03  movss   xmm0, dword ptr [r15+rdx*4+4]
0x18007db0a  xorps   xmm0, xmm1
0x18007db0d  movss   dword ptr [r15+rdx*4+4], xmm0
0x18007db14  mov     eax, [r14+1004h]
0x18007db1b  inc     eax
0x18007db1d  and     eax, 1FFh
0x18007db22  mov     ecx, eax
0x18007db24  mov     [r14+1004h], ecx
0x18007db2b  comiss  xmm7, ds:rva sbr_randomPhase[r8+rax*8]
0x18007db34  jbe     short loc_18007DB47
0x18007db36  movss   xmm0, dword ptr [r15+rdx*4+8]
0x18007db3d  xorps   xmm0, xmm1
0x18007db40  movss   dword ptr [r15+rdx*4+8], xmm0
0x18007db47  mov     eax, [r14+1004h]
0x18007db4e  inc     eax
0x18007db50  and     eax, 1FFh
0x18007db55  mov     ecx, eax
0x18007db57  mov     [r14+1004h], ecx
0x18007db5e  comiss  xmm7, ds:rva sbr_randomPhase[r8+rax*8]
0x18007db67  jbe     short loc_18007DB7A
0x18007db69  movss   xmm0, dword ptr [r15+rdx*4+0Ch]
0x18007db70  xorps   xmm0, xmm1
0x18007db73  movss   dword ptr [r15+rdx*4+0Ch], xmm0
0x18007db7a  mov     eax, [r14+1004h]
0x18007db81  add     rdx, 4
0x18007db85  inc     eax
0x18007db87  and     eax, 1FFh
0x18007db8c  mov     [r14+1004h], eax
0x18007db93  cmp     rdx, 400h
0x18007db9a  jnz     loc_18007DAC0
0x18007dba0  lea     rdx, [r14+1008h]
0x18007dba7  mov     eax, [r14+100Ch]
0x18007dbae  mov     ecx, [r14+1014h]
0x18007dbb5  movaps  xmm7, [rsp+248h+var_58]
0x18007dbbd  mov     r12, [rsp+248h+var_30]
0x18007dbc5  mov     rbx, [rsp+248h+arg_10]
0x18007dbcd  mov     [rdx], eax
0x18007dbcf  movsx   eax, dil
0x18007dbd3  mov     rdi, [rsp+248h+var_28]
0x18007dbdb  mov     [r14+100Ch], eax
0x18007dbe2  sub     ecx, 1
0x18007dbe5  jz      loc_18007DD75
0x18007dbeb  sub     ecx, 1
  ... truncated ...
```
