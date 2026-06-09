# GetMSIPresults

- ea: `0x180005f7c`
- end: `0x1800064dc`
- name: `GetMSIPresults`
- size: `1376`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180005020`

## callees

- `0x180005690`
- `0x180005730`
- `0x1800058b8`
- `0x180005984`
- `0x180005af0`
- `0x180005db0`
- `0x180005f7c`
- `0x1800064e4`
- `0x180006558`

## pseudocode

```c
__int64 __fastcall GetMSIPresults(__int64 a1, __int64 a2, int a3)
{
  _QWORD *v3; // rax
  _OWORD *v4; // r13
  __int64 v5; // r14
  __int64 v7; // rax
  __int64 v8; // xmm1_8
  _OWORD *v9; // rax
  __int64 v10; // rdx
  __int128 v11; // xmm1
  _OWORD *v12; // rax
  _OWORD *v13; // rcx
  __int128 v14; // xmm1
  __int64 v15; // rcx
  unsigned int v16; // esi
  __int64 i; // rcx
  int v18; // ebx
  int v19; // edi
  int v20; // r8d
  __int64 v21; // rdx
  int v22; // r9d
  int v23; // ecx
  int v24; // r11d
  _DWORD *v25; // r10
  unsigned int v26; // edx
  unsigned int v27; // r8d
  __int64 v28; // rdx
  int *v29; // r12
  unsigned int v30; // eax
  int v31; // ebx
  int v32; // edi
  _BYTE *v33; // r13
  int v34; // r9d
  __int64 j; // rcx
  __int64 v36; // rdx
  __int64 v37; // rcx
  int k; // r9d
  __int64 v39; // r8
  int v40; // r14d
  int v41; // esi
  int v42; // edi
  int v43; // ebx
  int v44; // eax
  int v45; // r9d
  int v46; // r14d
  int v47; // ecx
  __int64 m; // rcx
  _OWORD *v49; // rax
  __int64 v50; // rcx
  __int64 result; // rax
  int v52; // [rsp+30h] [rbp-38h] BYREF
  int v53; // [rsp+34h] [rbp-34h]
  int v54; // [rsp+38h] [rbp-30h] BYREF
  int v55; // [rsp+3Ch] [rbp-2Ch]
  _DWORD v56[4]; // [rsp+40h] [rbp-28h] BYREF
  __int64 v57; // [rsp+50h] [rbp-18h]
  int v58; // [rsp+58h] [rbp-10h]
  int v59; // [rsp+5Ch] [rbp-Ch]
  int v61; // [rsp+B8h] [rbp+50h] BYREF
  int v62; // [rsp+BCh] [rbp+54h]
  int v63; // [rsp+C0h] [rbp+58h]
  int v64; // [rsp+C8h] [rbp+60h]

  v3 = *(_QWORD **)a1;
  v4 = (_OWORD *)(a2 + 16);
  v5 = a2 + 99;
  *(_QWORD *)(a2 + 64) = **(_QWORD **)a1;
  *(_DWORD *)(a2 + 72) = *((_DWORD *)v3 + 2);
  v7 = *(_QWORD *)(a1 + 16);
  *(_OWORD *)(a2 + 76) = *(_OWORD *)v7;
  v8 = *(_QWORD *)(v7 + 15);
  v9 = *(_OWORD **)(a1 + 8);
  *(_QWORD *)(a2 + 91) = v8;
  v10 = 2;
  *v4 = *v9;
  v11 = v9[1];
  v12 = *(_OWORD **)(a1 + 24);
  v13 = (_OWORD *)v5;
  v4[1] = v11;
  do
  {
    *v13 = *v12;
    v13[1] = v12[1];
    v13[2] = v12[2];
    v13[3] = v12[3];
    v13[4] = v12[4];
    v13[5] = v12[5];
    v13[6] = v12[6];
    v14 = v12[7];
    v12 += 8;
    v13[7] = v14;
    v13 += 8;
    --v10;
  }
  while ( v10 );
  v15 = 0;
  v16 = 8;
  do
  {
    *(_BYTE *)(a2 + v15) = *(_BYTE *)(a2 + v15 + 64);
    ++v15;
  }
  while ( v15 != 8 );
  for ( i = 0; i != 4; ++i )
    *(_BYTE *)(i + a2 + 8) = *(_BYTE *)(a2 + i + 72);
  *(_BYTE *)(a2 + 12) = *(_BYTE *)(a2 + 64) ^ *(_BYTE *)(a2 + 84);
  *(_BYTE *)(a2 + 13) = *(_BYTE *)(a2 + 85) ^ *(_BYTE *)(a2 + 65);
  *(_BYTE *)(a2 + 14) = *(_BYTE *)(a2 + 86) ^ *(_BYTE *)(a2 + 66);
  *(_BYTE *)(a2 + 15) = *(_BYTE *)(a2 + 87) ^ *(_BYTE *)(a2 + 67);
  dword_18000C83C = -2;
  qword_18000C834 = 0xFFFFFFFEFFFFFFFEuLL;
  dword_18000C830 = 1;
  dword_18000C82C = 1;
  dword_18000C828 = 1;
  dword_18000C824 = 1;
  sCSKey = 1;
  v58 = 0;
  v59 = 0;
  ParveCBCMAC(a2 + 8, (_DWORD)v4, a3, (unsigned int)&v61, v5);
  v18 = v61;
  v19 = v62;
  v56[0] = v61 | 1;
  v56[1] = v62 | 1;
  v56[2] = v61 ^ 0x11A58E30 | 1;
  v56[3] = v62 ^ 0xF10A4EA | 1;
  v57 = v61 ^ 0xE79A9CE | 1u;
  CS64ComputeMAC(v4, 8, v56, &v61);
  v63 = v18 ^ v61;
  v64 = v19 ^ v62;
  ParveCBCMAC(a2 + 8, (_DWORD)v4, v20, (unsigned int)&v54, v5);
  CS64_Modular(v4, v21, &v54, &v52);
  v22 = 0;
  v23 = 0;
  v24 = (v52 ^ v54 | 1) + 10551296;
  v25 = v4;
  v61 = (v53 ^ v55 | 1) - 286326784;
  do
  {
    v16 -= 2;
    v26 = v23 + *v25;
    v25 += 2;
    v27 = -517991971 * (153223329 * HIWORD(v26) + v24 * v26)
        - 1814993220 * ((153223329 * HIWORD(v26) + v24 * v26) >> 16);
    v28 = v61 * (v27 + *(v25 - 1)) - 1412567313 * ((v27 + *(v25 - 1)) >> 16);
    v23 = 1546139565 * v28 + 1684656550 * ((v61 * (v27 + *(v25 - 1)) - 1412567313 * ((v27 + *(v25 - 1)) >> 16)) >> 16);
    v22 += v23 + v27;
  }
  while ( v16 > 1 );
  v29 = (int *)(a2 + 48);
  if ( v16 == 1 )
  {
    v30 = -517991971 * (153223329 * ((unsigned int)(v23 + *v25) >> 16) + v24 * (v23 + *v25))
        - 1814993220 * ((153223329 * ((unsigned int)(v23 + *v25) >> 16) + v24 * (v23 + *v25)) >> 16);
    v28 = v61 * v30 - 1412567313 * HIWORD(v30);
    v23 = 1546139565 * v28 + 1684656550 * ((v61 * v30 - 1412567313 * HIWORD(v30)) >> 16);
    v22 += v23 + v30;
  }
  v31 = v23 ^ v52 ^ v54;
  v52 = v23;
  v32 = v22 ^ v53 ^ v55;
  v53 = v22;
  v54 = v31;
  v55 = v32;
  CS64_Reversible(v4, v28, &v54, &v52);
  v33 = (_BYTE *)(a2 + 56);
  dword_18000C65C = v32 ^ v53;
  dword_18000C654 = v64;
  sCombHash = v63;
  dword_18000C658 = v52 ^ v31;
  *v29 = v63;
  *(_DWORD *)(a2 + 52) = dword_18000C654;
  *(_DWORD *)(a2 + 56) = dword_18000C658;
  *(_DWORD *)(a2 + 60) = dword_18000C65C;
  CS64Encrypt(a2, (unsigned int)&sCSKey, a2 + 48, v34, v5);
  for ( j = 0; j != 16; ++j )
    *((_BYTE *)&sCombRslt + j) = *(_BYTE *)(a2 + j + 48);
  *v29 = sCombHash;
  *(_DWORD *)(a2 + 52) = dword_18000C654;
  *(_DWORD *)v33 = dword_18000C658;
  *(_DWORD *)(a2 + 60) = dword_18000C65C;
  BV4GenerateKey(16, &sCombRslt, a2 + 56);
  BV4Crypt(v37, v36, a2 + 48);
  for ( k = 1; k != 9; ++k )
  {
    v39 = 6;
    *v33 = __ROR1__(*v33, 1) - *(_BYTE *)((unsigned __int8)(k + *(_BYTE *)(a2 + 7) + *(_BYTE *)(a2 + 63)) + v5);
    do
    {
      v33[v39 + 1] = __ROR1__(v33[v39 + 1], 1) - *(_BYTE *)((unsigned __int8)(k + *(_BYTE *)(a2 + v39) + v33[v39]) + v5);
      --v39;
    }
    while ( v39 != -1 );
  }
  v40 = *(_DWORD *)v33;
  v41 = *(_DWORD *)(a2 + 60);
  CS64ComputeMAC(a2 + 48, 2, &sCSKey, &v61);
  v42 = ModInvert32_32((unsigned int)sCSKey);
  LODWORD(qword_18000C834) = v42;
  v43 = ModInvert32_32((unsigned int)dword_18000C828);
  HIDWORD(qword_18000C834) = v43;
  v44 = ModInvert32_32((unsigned int)dword_18000C830);
  dword_18000C83C = v44;
  v46 = v40 - v41 - v61;
  v47 = v42 * (v46 - dword_18000C824);
  *(_DWORD *)(a2 + 60) = v43 * (v41 - dword_18000C82C) - v46;
  *(_DWORD *)v33 = v44 * (v47 - v62);
  for ( m = 0; m != 16; ++m )
    *((_BYTE *)&sCombRslt + m + 16) = *(_BYTE *)(a2 + m + 48);
  v49 = *(_OWORD **)(a1 + 40);
  *v49 = sCombRslt;
  v49[1] = xmmword_18000C810;
  *(_QWORD *)v29 = *(_QWORD *)(a2 + 64);
  *(_DWORD *)(a2 + 56) = *(_DWORD *)(a2 + 72);
  *(_BYTE *)(a2 + 60) = *(_BYTE *)(a2 + 84);
  *(_BYTE *)(a2 + 61) = *(_BYTE *)(a2 + 85);
  *(_BYTE *)(a2 + 62) = *(_BYTE *)(a2 + 86);
  *(_BYTE *)(a2 + 63) = *(_BYTE *)(a2 + 87);
  CS64Encrypt(a2 + 8, (unsigned int)&sCSKey, a2 + 48, v45, a2 + 99);
  v50 = *(_QWORD *)(a1 + 32);
  *(_QWORD *)v50 = *(_QWORD *)v29;
  result = *(unsigned int *)(a2 + 56);
  *(_DWORD *)(v50 + 8) = result;
  return result;
}

```

## disassembly

```asm
0x180005f7c  mov     [rsp-40h+arg_0], rcx
0x180005f81  push    rbp
0x180005f82  push    rbx
0x180005f83  push    rsi
0x180005f84  push    rdi
0x180005f85  push    r12
0x180005f87  push    r13
0x180005f89  push    r14
0x180005f8b  push    r15
0x180005f8d  mov     rbp, rsp
0x180005f90  sub     rsp, 68h
0x180005f94  mov     rax, [rcx]
0x180005f97  lea     r13, [rdx+10h]
0x180005f9b  lea     r14, [rdx+63h]
0x180005f9f  mov     r15, rdx
0x180005fa2  movsd   xmm0, qword ptr [rax]
0x180005fa6  movsd   qword ptr [rdx+40h], xmm0
0x180005fab  mov     eax, [rax+8]
0x180005fae  mov     [rdx+48h], eax
0x180005fb1  mov     rax, [rcx+10h]
0x180005fb5  movups  xmm0, xmmword ptr [rax]
0x180005fb8  movups  xmmword ptr [rdx+4Ch], xmm0
0x180005fbc  movsd   xmm1, qword ptr [rax+0Fh]
0x180005fc1  mov     rax, [rcx+8]
0x180005fc5  movsd   qword ptr [rdx+5Bh], xmm1
0x180005fca  mov     edx, 2
0x180005fcf  movups  xmm0, xmmword ptr [rax]
0x180005fd2  lea     r9d, [rdx+7Eh]
0x180005fd6  movaps  xmmword ptr [r13+0], xmm0
0x180005fdb  movups  xmm1, xmmword ptr [rax+10h]
0x180005fdf  mov     rax, [rcx+18h]
0x180005fe3  mov     rcx, r14
0x180005fe6  movaps  xmmword ptr [r13+10h], xmm1
0x180005feb  movups  xmm0, xmmword ptr [rax]
0x180005fee  movups  xmmword ptr [rcx], xmm0
0x180005ff1  movups  xmm1, xmmword ptr [rax+10h]
0x180005ff5  movups  xmmword ptr [rcx+10h], xmm1
0x180005ff9  movups  xmm0, xmmword ptr [rax+20h]
0x180005ffd  movups  xmmword ptr [rcx+20h], xmm0
0x180006001  movups  xmm1, xmmword ptr [rax+30h]
0x180006005  movups  xmmword ptr [rcx+30h], xmm1
0x180006009  movups  xmm0, xmmword ptr [rax+40h]
0x18000600d  movups  xmmword ptr [rcx+40h], xmm0
0x180006011  movups  xmm1, xmmword ptr [rax+50h]
0x180006015  movups  xmmword ptr [rcx+50h], xmm1
0x180006019  movups  xmm0, xmmword ptr [rax+60h]
0x18000601d  movups  xmmword ptr [rcx+60h], xmm0
0x180006021  movups  xmm1, xmmword ptr [rax+70h]
0x180006025  add     rax, r9
0x180006028  movups  xmmword ptr [rcx+70h], xmm1
0x18000602c  add     rcx, r9
0x18000602f  sub     rdx, 1
0x180006033  jnz     short loc_180005FEB
0x180006035  xor     ecx, ecx
0x180006037  lea     esi, [rdx+8]
0x18000603a  mov     al, [r15+rcx+40h]
0x18000603f  mov     [r15+rcx], al
0x180006043  inc     rcx
0x180006046  cmp     rcx, rsi
0x180006049  jnz     short loc_18000603A
0x18000604b  xor     ecx, ecx
0x18000604d  mov     al, [r15+rcx+48h]
0x180006052  mov     [rcx+r15+8], al
0x180006057  inc     rcx
0x18000605a  cmp     rcx, 4
0x18000605e  jnz     short loc_18000604D
0x180006060  mov     cl, [r15+54h]
0x180006064  lea     r9, [rbp+arg_8]
0x180006068  xor     cl, [r15+40h]
0x18000606c  mov     r12d, 1
0x180006072  mov     [r15+0Ch], cl
0x180006076  mov     eax, 0FFFFFFFEh
0x18000607b  mov     cl, [r15+41h]
0x18000607f  mov     rdx, r13
0x180006082  xor     cl, [r15+55h]
0x180006086  mov     [r15+0Dh], cl
0x18000608a  mov     cl, [r15+42h]
0x18000608e  xor     cl, [r15+56h]
0x180006092  mov     [r15+0Eh], cl
0x180006096  mov     cl, [r15+43h]
0x18000609a  xor     cl, [r15+57h]
0x18000609e  mov     [r15+0Fh], cl
0x1800060a2  lea     rcx, [r15+8]
0x1800060a6  mov     cs:dword_18000C83C, eax
0x1800060ac  mov     dword ptr cs:qword_18000C834+4, eax
0x1800060b2  mov     dword ptr cs:qword_18000C834, eax
0x1800060b8  mov     cs:dword_18000C830, r12d
0x1800060bf  mov     cs:dword_18000C82C, r12d
0x1800060c6  mov     cs:dword_18000C828, r12d
0x1800060cd  mov     cs:dword_18000C824, r12d
0x1800060d4  mov     cs:sCSKey, r12d
0x1800060db  mov     [rbp+var_14], 0
0x1800060e3  mov     [rbp+var_C], 0
0x1800060ea  mov     [rsp+68h+var_48], r14
0x1800060ef  call    ParveCBCMAC
0x1800060f4  mov     rbx, [rbp+arg_8]
0x1800060f8  lea     r9, [rbp+arg_8]
0x1800060fc  mov     edi, dword ptr [rbp+arg_8+4]
0x1800060ff  lea     r8, [rbp+var_28]
0x180006103  mov     eax, ebx
0x180006105  mov     edx, esi
0x180006107  or      eax, r12d
0x18000610a  mov     rcx, r13
0x18000610d  mov     [rbp+var_28], eax
0x180006110  mov     eax, edi
0x180006112  or      eax, r12d
0x180006115  mov     [rbp+var_24], eax
0x180006118  mov     eax, ebx
0x18000611a  xor     eax, 11A58E30h
0x18000611f  or      eax, r12d
0x180006122  mov     [rbp+var_20], eax
0x180006125  mov     eax, edi
0x180006127  xor     eax, 0F10A4EAh
0x18000612c  or      eax, r12d
0x18000612f  mov     [rbp+var_1C], eax
0x180006132  mov     eax, ebx
0x180006134  xor     eax, 0E79A9CEh
0x180006139  or      eax, r12d
0x18000613c  mov     [rbp+var_18], eax
0x18000613f  call    CS64ComputeMAC
0x180006144  mov     eax, dword ptr [rbp+arg_8]
0x180006147  lea     r9, [rbp+var_30]
0x18000614b  xor     eax, ebx
0x18000614d  mov     [rsp+68h+var_48], r14
0x180006152  mov     [rbp+arg_10], eax
0x180006155  lea     rcx, [r15+8]
0x180006159  mov     eax, dword ptr [rbp+arg_8+4]
0x18000615c  mov     rdx, r13
0x18000615f  xor     eax, edi
0x180006161  mov     [rbp+arg_18], eax
0x180006164  call    ParveCBCMAC
0x180006169  lea     r9, [rbp+var_38]
0x18000616d  mov     rcx, r13
0x180006170  lea     r8, [rbp+var_30]
0x180006174  call    CS64_Modular
0x180006179  mov     ebx, [rbp+var_30]
0x18000617c  xor     r9d, r9d
0x18000617f  xor     ebx, [rbp+var_38]
0x180006182  xor     ecx, ecx
0x180006184  mov     edi, [rbp+var_2C]
0x180006187  mov     r11d, ebx
0x18000618a  xor     edi, [rbp+var_34]
0x18000618d  or      r11d, r12d
0x180006190  add     r11d, 0A10000h
0x180006197  mov     eax, edi
0x180006199  or      eax, r12d
0x18000619c  mov     r10, r13
0x18000619f  sub     eax, 11110000h
0x1800061a4  mov     dword ptr [rbp+arg_8], eax
0x1800061a7  mov     r12d, eax
0x1800061aa  mov     edx, [r10]
0x1800061ad  add     esi, 0FFFFFFFEh
0x1800061b0  add     edx, ecx
0x1800061b2  lea     r10, [r10+8]
0x1800061b6  mov     eax, edx
0x1800061b8  imul    edx, r11d
0x1800061bc  shr     eax, 10h
0x1800061bf  imul    ecx, eax, 92200A1h
0x1800061c5  add     edx, ecx
0x1800061c7  imul    r8d, edx, 0E12011DDh
0x1800061ce  mov     eax, edx
0x1800061d0  shr     eax, 10h
0x1800061d3  imul    ecx, eax, 6C2E9944h
0x1800061d9  sub     r8d, ecx
0x1800061dc  mov     ecx, [r10-4]
0x1800061e0  add     ecx, r8d
0x1800061e3  add     r9d, r8d
0x1800061e6  mov     edx, ecx
0x1800061e8  shr     ecx, 10h
0x1800061eb  imul    eax, ecx, 54321111h
0x1800061f1  imul    edx, r12d
0x1800061f5  sub     edx, eax
0x1800061f7  mov     eax, edx
0x1800061f9  shr     eax, 10h
0x1800061fc  imul    ecx, eax, 6469D1A6h
0x180006202  imul    eax, edx, 5C2837ADh
0x180006208  add     ecx, eax
0x18000620a  add     r9d, ecx
0x18000620d  cmp     esi, 1
0x180006210  ja      short loc_1800061AA
0x180006212  lea     r12, [r15+30h]
0x180006216  jnz     short loc_18000626B
0x180006218  mov     edx, [r10]
0x18000621b  add     edx, ecx
0x18000621d  mov     eax, edx
0x18000621f  imul    edx, r11d
0x180006223  shr     eax, 10h
0x180006226  imul    ecx, eax, 92200A1h
0x18000622c  add     edx, ecx
0x18000622e  mov     eax, edx
0x180006230  shr     eax, 10h
0x180006233  imul    ecx, eax, 6C2E9944h
0x180006239  imul    eax, edx, 0E12011DDh
0x18000623f  sub     eax, ecx
0x180006241  add     r9d, eax
0x180006244  mov     edx, eax
0x180006246  imul    edx, dword ptr [rbp+arg_8]
0x18000624a  shr     eax, 10h
0x18000624d  imul    eax, 54321111h
0x180006253  sub     edx, eax
0x180006255  mov     eax, edx
0x180006257  shr     eax, 10h
0x18000625a  imul    ecx, eax, 6469D1A6h
0x180006260  imul    eax, edx, 5C2837ADh
0x180006266  add     ecx, eax
0x180006268  add     r9d, ecx
0x18000626b  xor     ebx, ecx
0x18000626d  mov     [rbp+var_38], ecx
0x180006270  xor     edi, r9d
0x180006273  mov     [rbp+var_34], r9d
0x180006277  lea     r9, [rbp+var_38]
0x18000627b  mov     [rbp+var_30], ebx
0x18000627e  mov     rcx, r13
0x180006281  mov     [rbp+var_2C], edi
0x180006284  lea     r8, [rbp+var_30]
0x180006288  call    CS64_Reversible
0x18000628d  mov     ecx, [rbp+arg_10]
0x180006290  lea     r13, [r12+8]
0x180006295  mov     eax, [rbp+var_34]
0x180006298  mov     r8, r12
0x18000629b  mov     edx, [rbp+arg_18]
0x18000629e  xor     eax, edi
0x1800062a0  xor     ebx, [rbp+var_38]
0x1800062a3  mov     cs:dword_18000C65C, eax
0x1800062a9  mov     cs:dword_18000C654, edx
0x1800062af  lea     rdx, sCSKey
0x1800062b6  mov     cs:sCombHash, ecx
0x1800062bc  mov     cs:dword_18000C658, ebx
0x1800062c2  mov     [r12], ecx
0x1800062c6  mov     rcx, r15
0x1800062c9  mov     eax, cs:dword_18000C654
0x1800062cf  mov     [r12+4], eax
0x1800062d4  mov     eax, cs:dword_18000C658
0x1800062da  mov     [r13+0], eax
0x1800062de  mov     eax, cs:dword_18000C65C
0x1800062e4  mov     [r12+0Ch], eax
0x1800062e9  mov     [rsp+68h+var_48], r14
0x1800062ee  call    CS64Encrypt
0x1800062f3  xor     ecx, ecx
0x1800062f5  lea     rdx, sCombRslt
0x1800062fc  mov     al, [r15+rcx+30h]
0x180006301  mov     [rcx+rdx], al
0x180006304  inc     rcx
0x180006307  cmp     rcx, 10h
0x18000630b  jnz     short loc_1800062FC
0x18000630d  mov     eax, cs:sCombHash
0x180006313  mov     r8, r13
0x180006316  mov     [r12], eax
0x18000631a  mov     eax, cs:dword_18000C654
0x180006320  mov     [r12+4], eax
0x180006325  mov     eax, cs:dword_18000C658
0x18000632b  mov     [r13+0], eax
0x18000632f  mov     eax, cs:dword_18000C65C
0x180006335  mov     [r12+0Ch], eax
0x18000633a  call    BV4GenerateKey
0x18000633f  mov     r8, r12
0x180006342  call    BV4Crypt
0x180006347  mov     r9d, 1
0x18000634d  movzx   eax, byte ptr [r15+7]
0x180006352  mov     r8d, 6
0x180006358  movzx   ecx, byte ptr [r13+7]
0x18000635d  add     eax, r9d
0x180006360  mov     dl, [r13+0]
0x180006364  add     ecx, eax
0x180006366  movzx   eax, cl
0x180006369  ror     dl, 1
0x18000636b  sub     dl, [rax+r14]
0x18000636f  mov     [r13+0], dl
0x180006373  movzx   eax, byte ptr [r15+r8]
0x180006378  mov     dl, [r8+r13+1]
0x18000637d  add     eax, r9d
0x180006380  movzx   ecx, byte ptr [r8+r13]
0x180006385  add     ecx, eax
0x180006387  ror     dl, 1
0x180006389  movzx   eax, cl
0x18000638c  sub     dl, [rax+r14]
0x180006390  mov     [r8+r13+1], dl
0x180006395  dec     r8
0x180006398  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000639c  jnz     short loc_180006373
0x18000639e  inc     r9d
0x1800063a1  cmp     r9d, 9
0x1800063a5  jnz     short loc_18000634D
0x1800063a7  mov     r14d, [r13+0]
0x1800063ab  lea     r9, [rbp+arg_8]
0x1800063af  mov     esi, [r13+4]
0x1800063b3  lea     r8, sCSKey
0x1800063ba  mov     edx, 2
0x1800063bf  mov     rcx, r12
0x1800063c2  call    CS64ComputeMAC
0x1800063c7  mov     ecx, cs:sCSKey
0x1800063cd  call    ModInvert32_32
0x1800063d2  mov     ecx, cs:dword_18000C828
0x1800063d8  mov     edi, eax
0x1800063da  mov     dword ptr cs:qword_18000C834, eax
0x1800063e0  call    ModInvert32_32
0x1800063e5  mov     ecx, cs:dword_18000C830
0x1800063eb  mov     ebx, eax
0x1800063ed  mov     dword ptr cs:qword_18000C834+4, eax
0x1800063f3  call    ModInvert32_32
  ... truncated ...
```
