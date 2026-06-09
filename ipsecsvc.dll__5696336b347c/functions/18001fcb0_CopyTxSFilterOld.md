# CopyTxSFilterOld

- ea: `0x18001fcb0`
- end: `0x18002011f`
- name: `CopyTxSFilterOld`
- size: `1135`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int *)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x1800202cc`
- `0x18002059c`
- `0x1800209bc`

## callees

- `0x18000e510`
- `0x1800173d0`
- `0x1800175dc`
- `0x18001e514`
- `0x18001fcb0`
- `0x1800239f8`
- `0x180023ae0`
- `0x18004d05e`
- `0x18004d090`
- `0x18004d120`

## pseudocode

```c
__int64 __fastcall CopyTxSFilterOld(__int64 a1, __int64 a2, unsigned int *a3)
{
  __int32 *v5; // rsi
  __int32 *v6; // rbx
  __int64 v7; // rcx
  unsigned int v8; // r13d
  int v9; // r15d
  int v10; // r14d
  unsigned int v11; // r12d
  bool v12; // zf
  int v13; // r9d
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  unsigned int v16; // eax
  __int64 v17; // rsi
  __int64 v19; // rcx
  __int64 i; // rbx
  __int64 v21; // rcx
  unsigned int v22; // r14d
  unsigned int v23; // r13d
  const wchar_t *v24; // rcx
  unsigned int v25; // r15d
  __int64 v26; // r8
  __int128 v27; // xmm1
  __int64 v28; // rax
  __int64 v29; // rcx
  __int128 v30; // xmm0
  __int128 v31; // xmm1
  __int128 v32; // xmm0
  __int128 v33; // xmm1
  __int128 v34; // xmm0
  __int128 v35; // xmm1
  __int128 v36; // xmm0
  __int128 v37; // xmm1
  unsigned int v38; // r13d
  unsigned int v39; // ebx
  __int64 v40; // rsi
  __int64 v41; // rdi
  unsigned int v42; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int v43; // [rsp+24h] [rbp-DCh]
  unsigned int v44; // [rsp+28h] [rbp-D8h] BYREF
  int v45; // [rsp+2Ch] [rbp-D4h] BYREF
  int v46; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v47; // [rsp+38h] [rbp-C8h]
  __m256i v48; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v49; // [rsp+60h] [rbp-A0h]
  __m256i v50; // [rsp+70h] [rbp-90h]
  __m256i v51; // [rsp+90h] [rbp-70h]
  __int128 v52; // [rsp+B0h] [rbp-50h]
  __int128 v53; // [rsp+C0h] [rbp-40h]
  _OWORD v54[2]; // [rsp+D0h] [rbp-30h]
  unsigned int *v55; // [rsp+F0h] [rbp-10h]
  int v56; // [rsp+100h] [rbp+0h] BYREF
  _DWORD v57[3]; // [rsp+104h] [rbp+4h]
  _BYTE v58[4336]; // [rsp+110h] [rbp+10h]
  int v59; // [rsp+1200h] [rbp+1100h] BYREF
  _DWORD v60[3]; // [rsp+1204h] [rbp+1104h]
  _BYTE v61[4336]; // [rsp+1210h] [rbp+1110h]

  v47 = a2;
  v55 = a3;
  memset_0(&v48, 0, 0xA8u);
  memset_0(&v56, 0, 0x1100u);
  memset_0(&v59, 0, 0x1100u);
  v5 = (__int32 *)(a1 + 80);
  *a3 = 0;
  v12 = *(_DWORD *)a1 == 1;
  v6 = (__int32 *)(a1 + 40);
  v7 = a1 + 40;
  v45 = 0;
  v46 = 0;
  v42 = 0;
  v8 = 0;
  v44 = 0;
  v9 = 0;
  v43 = 0;
  v10 = 0;
  if ( v12 )
  {
    GetV6AddressSubnets(v7, &v56, &v42);
    GetV6AddressSubnets(a1 + 80, &v59, &v44);
    if ( v42 == 1 && v58[0] == 0x80 )
    {
      v50.m256i_i32[0] = 1;
    }
    else if ( (unsigned int)(*v6 - 4) <= 3 )
    {
      v50.m256i_i32[0] = *v6;
      v9 = 1;
    }
    else
    {
      v50.m256i_i32[0] = 2;
    }
    v11 = v44;
    if ( v44 != 1 )
      goto LABEL_20;
    v12 = v61[0] == 0x80;
  }
  else
  {
    GetV4AddressSubnets(v7, &v56, &v42);
    GetV4AddressSubnets(a1 + 80, &v59, &v44);
    if ( v42 == 1 && v57[0] == -1 )
    {
      v50.m256i_i32[0] = 1;
    }
    else if ( (unsigned int)(*v6 - 4) <= 3 )
    {
      v50.m256i_i32[0] = *v6;
      v9 = 1;
    }
    else
    {
      v50.m256i_i32[0] = 2;
    }
    v11 = v44;
    if ( v44 != 1 )
      goto LABEL_20;
    v12 = v60[0] == -1;
  }
  if ( !v12 )
  {
LABEL_20:
    if ( (unsigned int)(*v5 - 4) <= 3 )
    {
      v10 = 1;
      v51.m256i_i32[0] = *v5;
    }
    else
    {
      v51.m256i_i32[0] = 2;
    }
    goto LABEL_23;
  }
  v51.m256i_i32[0] = 1;
LABEL_23:
  GetPortRange(a1 + 128, &v45);
  GetPortRange(a1 + 136, &v46);
  v14 = *(_OWORD *)(a1 + 4);
  *(_QWORD *)&v52 = *(_QWORD *)(a1 + 120);
  v15 = *(_OWORD *)(a1 + 164);
  v48.m256i_i32[0] = *(_DWORD *)a1;
  *(_QWORD *)&v49 = *(unsigned int *)(a1 + 32);
  DWORD2(v49) = *(_DWORD *)(a1 + 36);
  *(_QWORD *)&v54[0] = *(_QWORD *)(a1 + 156);
  *((_QWORD *)&v53 + 1) = *(_QWORD *)(a1 + 144);
  v16 = v42;
  LODWORD(v53) = v13;
  DWORD2(v52) = v13;
  *(_OWORD *)((char *)v48.m256i_i64 + 4) = v14;
  *(_OWORD *)((char *)v54 + 8) = v15;
  if ( !v42 && !v9 || !v11 && !v10 )
    goto LABEL_32;
  v17 = 0;
LABEL_28:
  if ( (unsigned int)v17 > v16 )
  {
LABEL_31:
    v8 = v43;
LABEL_32:
    *v55 = v8;
    return 0;
  }
  if ( (_DWORD)v17 == v16 )
  {
    if ( (_DWORD)v17 )
      goto LABEL_31;
  }
  else if ( *(_DWORD *)a1 == v13 )
  {
    v19 = 17LL * (unsigned int)v17;
    *(__int64 *)((char *)v50.m256i_i64 + 4) = *(_QWORD *)((char *)&v57[-1] + v19);
    *(__int64 *)((char *)&v50.m256i_i64[1] + 4) = *(_QWORD *)((char *)&v57[1] + v19);
    v50.m256i_i8[20] = v58[v19];
  }
  else
  {
    v50.m256i_i32[1] = v57[2 * v17 - 1];
    v50.m256i_i32[2] = v57[2 * v17];
  }
  for ( i = 0; ; i = (unsigned int)(v13 + i) )
  {
    if ( (unsigned int)i > v11 )
    {
LABEL_40:
      v16 = v42;
      v17 = (unsigned int)(v13 + v17);
      goto LABEL_28;
    }
    if ( (_DWORD)i == v11 )
    {
      if ( (_DWORD)i )
        goto LABEL_40;
    }
    else if ( *(_DWORD *)a1 == v13 )
    {
      v21 = 17LL * (unsigned int)i;
      v51.m256i_i32[1] = *(_DWORD *)((char *)&v60[-1] + v21);
      v51.m256i_i32[2] = *(_DWORD *)((char *)v60 + v21);
      *(__int64 *)((char *)&v51.m256i_i64[1] + 4) = *(_QWORD *)((char *)&v60[1] + v21);
      v51.m256i_i8[20] = v61[v21];
    }
    else
    {
      v51.m256i_i32[1] = v60[2 * i - 1];
      v51.m256i_i32[2] = v60[2 * i];
    }
    v22 = (unsigned __int16)v45;
LABEL_45:
    if ( v22 <= HIWORD(v45) )
      break;
  }
  v23 = (unsigned __int16)v46;
  WORD6(v52) = v22;
  while ( 1 )
  {
    if ( v23 > HIWORD(v46) )
    {
      v22 += v13;
      goto LABEL_45;
    }
    v24 = *(const wchar_t **)(a1 + 24);
    WORD2(v53) = v23;
    v25 = CopyName(v24, &v48.m256i_i64[3]);
    if ( v25 )
      break;
    v26 = v47;
    v13 = 1;
    v27 = *(_OWORD *)&v48.m256i_u64[2];
    v28 = *(_QWORD *)&v54[1];
    v29 = 168LL * v43++;
    ++v23;
    *(_OWORD *)(v29 + v47) = *(_OWORD *)v48.m256i_i8;
    v30 = v49;
    *(_OWORD *)(v29 + v26 + 16) = v27;
    v31 = *(_OWORD *)v50.m256i_i8;
    *(_OWORD *)(v29 + v26 + 32) = v30;
    v32 = *(_OWORD *)&v50.m256i_u64[2];
    *(_OWORD *)(v29 + v26 + 48) = v31;
    v33 = *(_OWORD *)v51.m256i_i8;
    *(_OWORD *)(v29 + v26 + 64) = v32;
    v34 = *(_OWORD *)&v51.m256i_u64[2];
    *(_OWORD *)(v29 + v26 + 80) = v33;
    v35 = v52;
    *(_OWORD *)(v29 + v26 + 96) = v34;
    v36 = v53;
    *(_OWORD *)(v29 + v26 + 112) = v35;
    v37 = v54[0];
    *(_OWORD *)(v29 + v26 + 128) = v36;
    *(_OWORD *)(v29 + v26 + 144) = v37;
    *(_QWORD *)(v29 + v26 + 160) = v28;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_9e5bd0d0d2233fe69730d263c30676fb_Traceguids, v25);
  v38 = v43;
  v39 = 0;
  if ( v43 )
  {
    v40 = v47;
    v41 = 168LL * v43;
    do
    {
      SPDApiBufferFree(*(_QWORD *)(v41 + v40 + 24));
      ++v39;
    }
    while ( v39 < v38 );
  }
  return v25;
}

```

## disassembly

```asm
0x18001fcb0  mov     [rsp-8+arg_18], rbx
0x18001fcb5  push    rbp
0x18001fcb6  push    rsi
0x18001fcb7  push    rdi
0x18001fcb8  push    r12
0x18001fcba  push    r13
0x18001fcbc  push    r14
0x18001fcbe  push    r15
0x18001fcc0  lea     rbp, [rsp-2210h]
0x18001fcc8  mov     eax, 2310h
0x18001fccd  call    _alloca_probe
0x18001fcd2  sub     rsp, rax
0x18001fcd5  mov     rax, cs:__security_cookie
0x18001fcdc  xor     rax, rsp
0x18001fcdf  mov     [rbp+2240h+var_40], rax
0x18001fce6  mov     rbx, r8
0x18001fce9  mov     [rsp+2340h+var_2308], rdx
0x18001fcee  mov     rdi, rcx
0x18001fcf1  mov     [rbp+2240h+var_2250], rbx
0x18001fcf5  xor     edx, edx; Val
0x18001fcf7  lea     rcx, [rsp+2340h+var_2300]; void *
0x18001fcfc  mov     r8d, 0A8h; Size
0x18001fd02  call    memset_0
0x18001fd07  mov     esi, 1100h
0x18001fd0c  lea     rcx, [rbp+2240h+var_2240]; void *
0x18001fd10  mov     r8d, esi; Size
0x18001fd13  xor     edx, edx; Val
0x18001fd15  call    memset_0
0x18001fd1a  mov     r8d, esi; Size
0x18001fd1d  lea     rcx, [rbp+2240h+var_1140]; void *
0x18001fd24  xor     edx, edx; Val
0x18001fd26  call    memset_0
0x18001fd2b  xor     eax, eax
0x18001fd2d  lea     rsi, [rdi+50h]
0x18001fd31  mov     [rbx], eax
0x18001fd33  lea     r8, [rsp+2340h+var_2320]
0x18001fd38  cmp     dword ptr [rdi], 1
0x18001fd3b  lea     rbx, [rdi+28h]
0x18001fd3f  mov     rcx, rbx
0x18001fd42  mov     [rsp+2340h+var_2314], eax
0x18001fd46  mov     [rsp+2340h+var_2310], eax
0x18001fd4a  lea     rdx, [rbp+2240h+var_2240]
0x18001fd4e  mov     [rsp+2340h+var_2320], eax
0x18001fd52  mov     r13d, eax
0x18001fd55  mov     [rsp+2340h+var_2318], eax
0x18001fd59  mov     r15d, eax
0x18001fd5c  mov     [rsp+2340h+var_231C], eax
0x18001fd60  mov     r14d, eax
0x18001fd63  jnz     short loc_18001FDC5
0x18001fd65  call    GetV6AddressSubnets
0x18001fd6a  lea     r8, [rsp+2340h+var_2318]
0x18001fd6f  mov     rcx, rsi
0x18001fd72  lea     rdx, [rbp+2240h+var_1140]
0x18001fd79  call    GetV6AddressSubnets
0x18001fd7e  mov     ecx, 2
0x18001fd83  lea     r9d, [rcx-1]
0x18001fd87  cmp     [rsp+2340h+var_2320], r9d
0x18001fd8c  jnz     short loc_18001FD9B
0x18001fd8e  cmp     [rbp+2240h+var_2230], 80h
0x18001fd92  jnz     short loc_18001FD9B
0x18001fd94  mov     dword ptr [rsp+2340h+var_22D0], r9d
0x18001fd99  jmp     short loc_18001FDB2
0x18001fd9b  mov     edx, [rbx]
0x18001fd9d  lea     eax, [rdx-4]
0x18001fda0  cmp     eax, 3
0x18001fda3  jbe     short loc_18001FDAB
0x18001fda5  mov     dword ptr [rsp+2340h+var_22D0], ecx
0x18001fda9  jmp     short loc_18001FDB2
0x18001fdab  mov     dword ptr [rsp+2340h+var_22D0], edx
0x18001fdaf  mov     r15d, r9d
0x18001fdb2  mov     r12d, [rsp+2340h+var_2318]
0x18001fdb7  cmp     r12d, r9d
0x18001fdba  jnz     short loc_18001FE2F
0x18001fdbc  cmp     [rbp+2240h+var_1130], 80h
0x18001fdc3  jmp     short loc_18001FE27
0x18001fdc5  call    GetV4AddressSubnets
0x18001fdca  lea     r8, [rsp+2340h+var_2318]
0x18001fdcf  mov     rcx, rsi
0x18001fdd2  lea     rdx, [rbp+2240h+var_1140]
0x18001fdd9  call    GetV4AddressSubnets
0x18001fdde  mov     ecx, 2
0x18001fde3  or      r8d, 0FFFFFFFFh
0x18001fde7  lea     r9d, [rcx-1]
0x18001fdeb  cmp     [rsp+2340h+var_2320], r9d
0x18001fdf0  jnz     short loc_18001FDFF
0x18001fdf2  cmp     [rbp+2240h+var_223C], r8d
0x18001fdf6  jnz     short loc_18001FDFF
0x18001fdf8  mov     dword ptr [rsp+2340h+var_22D0], r9d
0x18001fdfd  jmp     short loc_18001FE16
0x18001fdff  mov     edx, [rbx]
0x18001fe01  lea     eax, [rdx-4]
0x18001fe04  cmp     eax, 3
0x18001fe07  jbe     short loc_18001FE0F
0x18001fe09  mov     dword ptr [rsp+2340h+var_22D0], ecx
0x18001fe0d  jmp     short loc_18001FE16
0x18001fe0f  mov     dword ptr [rsp+2340h+var_22D0], edx
0x18001fe13  mov     r15d, r9d
0x18001fe16  mov     r12d, [rsp+2340h+var_2318]
0x18001fe1b  cmp     r12d, r9d
0x18001fe1e  jnz     short loc_18001FE2F
0x18001fe20  cmp     [rbp+2240h+var_113C], r8d
0x18001fe27  jnz     short loc_18001FE2F
0x18001fe29  mov     dword ptr [rbp+2240h+var_22B0], r9d
0x18001fe2d  jmp     short loc_18001FE44
0x18001fe2f  mov     edx, [rsi]
0x18001fe31  lea     eax, [rdx-4]
0x18001fe34  cmp     eax, 3
0x18001fe37  jbe     short loc_18001FE3E
0x18001fe39  mov     dword ptr [rbp+2240h+var_22B0], ecx
0x18001fe3c  jmp     short loc_18001FE44
0x18001fe3e  mov     r14d, r9d
0x18001fe41  mov     dword ptr [rbp+2240h+var_22B0], edx
0x18001fe44  lea     rcx, [rdi+80h]
0x18001fe4b  lea     rdx, [rsp+2340h+var_2314]
0x18001fe50  call    GetPortRange
0x18001fe55  lea     rcx, [rdi+88h]
0x18001fe5c  lea     rdx, [rsp+2340h+var_2310]
0x18001fe61  call    GetPortRange
0x18001fe66  mov     rax, [rdi+78h]
0x18001fe6a  movups  xmm0, xmmword ptr [rdi+4]
0x18001fe6e  mov     qword ptr [rbp+2240h+var_2290], rax
0x18001fe72  mov     eax, [rdi]
0x18001fe74  movups  xmm1, xmmword ptr [rdi+0A4h]
0x18001fe7b  mov     dword ptr [rsp+2340h+var_2300], eax
0x18001fe7f  mov     eax, [rdi+20h]
0x18001fe82  mov     dword ptr [rsp+2340h+var_22E0], eax
0x18001fe86  mov     eax, [rdi+24h]
0x18001fe89  mov     dword ptr [rsp+2340h+var_22E0+8], eax
0x18001fe8d  mov     eax, [rdi+9Ch]
0x18001fe93  mov     dword ptr [rbp+2240h+var_2270], eax
0x18001fe96  mov     eax, [rdi+0A0h]
0x18001fe9c  mov     dword ptr [rbp+2240h+var_2270+4], eax
0x18001fe9f  mov     eax, [rdi+90h]
0x18001fea5  mov     dword ptr [rbp+2240h+var_2280+8], eax
0x18001fea8  mov     eax, [rdi+94h]
0x18001feae  mov     dword ptr [rbp+2240h+var_2280+0Ch], eax
0x18001feb1  mov     eax, [rsp+2340h+var_2320]
0x18001feb5  mov     dword ptr [rsp+2340h+var_22E0+4], r13d
0x18001feba  mov     dword ptr [rbp+2240h+var_2280], r9d
0x18001febe  mov     dword ptr [rbp+2240h+var_2290+8], r9d
0x18001fec2  movdqu  [rsp+2340h+var_2300+4], xmm0
0x18001fec8  movdqu  xmmword ptr [rbp+2240h+var_2270+8], xmm1
0x18001fecd  test    eax, eax
0x18001fecf  jnz     short loc_18001FED6
0x18001fed1  test    r15d, r15d
0x18001fed4  jz      short loc_18001FEF1
0x18001fed6  test    r12d, r12d
0x18001fed9  jnz     short loc_18001FEE0
0x18001fedb  test    r14d, r14d
0x18001fede  jz      short loc_18001FEF1
0x18001fee0  xor     esi, esi
0x18001fee2  cmp     esi, eax
0x18001fee4  ja      short loc_18001FEEC
0x18001fee6  jnz     short loc_18001FF24
0x18001fee8  test    esi, esi
0x18001feea  jz      short loc_18001FF62
0x18001feec  mov     r13d, [rsp+2340h+var_231C]
0x18001fef1  mov     rax, [rbp+2240h+var_2250]
0x18001fef5  mov     [rax], r13d
0x18001fef8  xor     eax, eax
0x18001fefa  mov     rcx, [rbp+2240h+var_40]
0x18001ff01  xor     rcx, rsp; StackCookie
0x18001ff04  call    __security_check_cookie
0x18001ff09  mov     rbx, [rsp+2340h+arg_18]
0x18001ff11  add     rsp, 2310h
0x18001ff18  pop     r15
0x18001ff1a  pop     r14
0x18001ff1c  pop     r13
0x18001ff1e  pop     r12
0x18001ff20  pop     rdi
0x18001ff21  pop     rsi
0x18001ff22  pop     rbp
0x18001ff23  retn
0x18001ff24  mov     ecx, esi
0x18001ff26  cmp     [rdi], r9d
0x18001ff29  jnz     short loc_18001FF52
0x18001ff2b  imul    rcx, 11h
0x18001ff2f  mov     eax, [rbp+rcx+2240h+var_2240]
0x18001ff33  mov     dword ptr [rsp+2340h+var_22D0+4], eax
0x18001ff37  mov     eax, [rbp+rcx+2240h+var_223C]
0x18001ff3b  mov     dword ptr [rsp+2340h+var_22D0+8], eax
0x18001ff3f  mov     rax, [rbp+rcx+2240h+var_2238]
0x18001ff44  mov     qword ptr [rsp+2340h+var_22D0+0Ch], rax
0x18001ff49  mov     al, [rbp+rcx+2240h+var_2230]
0x18001ff4d  mov     [rbp+2240h+var_22BC], al
0x18001ff50  jmp     short loc_18001FF62
0x18001ff52  mov     eax, [rbp+rsi*8+2240h+var_2240]
0x18001ff56  mov     dword ptr [rsp+2340h+var_22D0+4], eax
0x18001ff5a  mov     eax, [rbp+rsi*8+2240h+var_223C]
0x18001ff5e  mov     dword ptr [rsp+2340h+var_22D0+8], eax
0x18001ff62  xor     ebx, ebx
0x18001ff64  cmp     ebx, r12d
0x18001ff67  ja      short loc_18001FF6F
0x18001ff69  jnz     short loc_18001FF7B
0x18001ff6b  test    ebx, ebx
0x18001ff6d  jz      short loc_18001FFC6
0x18001ff6f  mov     eax, [rsp+2340h+var_2320]
0x18001ff73  add     esi, r9d
0x18001ff76  jmp     loc_18001FEE2
0x18001ff7b  mov     ecx, ebx
0x18001ff7d  cmp     [rdi], r9d
0x18001ff80  jnz     short loc_18001FFB2
0x18001ff82  imul    rcx, 11h
0x18001ff86  mov     eax, [rbp+rcx+2240h+var_1140]
0x18001ff8d  mov     dword ptr [rbp+2240h+var_22B0+4], eax
0x18001ff90  mov     eax, [rbp+rcx+2240h+var_113C]
0x18001ff97  mov     dword ptr [rbp+2240h+var_22B0+8], eax
0x18001ff9a  mov     rax, [rbp+rcx+2240h+var_1138]
0x18001ffa2  mov     qword ptr [rbp+2240h+var_22B0+0Ch], rax
0x18001ffa6  mov     al, [rbp+rcx+2240h+var_1130]
0x18001ffad  mov     [rbp+2240h+var_229C], al
0x18001ffb0  jmp     short loc_18001FFC6
0x18001ffb2  mov     eax, [rbp+rbx*8+2240h+var_1140]
0x18001ffb9  mov     dword ptr [rbp+2240h+var_22B0+4], eax
0x18001ffbc  mov     eax, [rbp+rbx*8+2240h+var_113C]
0x18001ffc3  mov     dword ptr [rbp+2240h+var_22B0+8], eax
0x18001ffc6  movzx   r14d, word ptr [rsp+2340h+var_2314]
0x18001ffcc  movzx   eax, word ptr [rsp+2340h+var_2314+2]
0x18001ffd1  cmp     r14d, eax
0x18001ffd4  ja      loc_1800200B5
0x18001ffda  movzx   r13d, word ptr [rsp+2340h+var_2310]
0x18001ffe0  mov     word ptr [rbp+2240h+var_2290+0Ch], r14w
0x18001ffe5  movzx   eax, word ptr [rsp+2340h+var_2310+2]
0x18001ffea  cmp     r13d, eax
0x18001ffed  ja      loc_1800200AD
0x18001fff3  mov     rcx, [rdi+18h]; pszSrc
0x18001fff7  lea     rdx, [rsp+2340h+var_22E8]
0x18001fffc  mov     word ptr [rbp+2240h+var_2280+4], r13w
0x180020001  call    CopyName
0x180020006  mov     r15d, eax
0x180020009  test    eax, eax
0x18002000b  jnz     loc_1800200BD
0x180020011  mov     r8, [rsp+2340h+var_2308]
0x180020016  lea     r9d, [r15+1]
0x18002001a  mov     edx, [rsp+2340h+var_231C]
0x18002001e  movaps  xmm0, [rsp+2340h+var_2300]
0x180020023  movaps  xmm1, xmmword ptr [rsp+50h]
0x180020028  mov     rax, qword ptr [rbp+2240h+var_2270+10h]
0x18002002c  imul    rcx, rdx, 0A8h
0x180020033  add     edx, r9d
0x180020036  mov     [rsp+2340h+var_231C], edx
0x18002003a  add     r13d, r9d
0x18002003d  movups  xmmword ptr [rcx+r8], xmm0
0x180020042  movaps  xmm0, [rsp+2340h+var_22E0]
0x180020047  movups  xmmword ptr [rcx+r8+10h], xmm1
0x18002004d  movaps  xmm1, [rsp+2340h+var_22D0]
0x180020052  movups  xmmword ptr [rcx+r8+20h], xmm0
0x180020058  movaps  xmm0, xmmword ptr [rbp-80h]
0x18002005c  movups  xmmword ptr [rcx+r8+30h], xmm1
0x180020062  movaps  xmm1, [rbp+2240h+var_22B0]
0x180020066  movups  xmmword ptr [rcx+r8+40h], xmm0
0x18002006c  movaps  xmm0, xmmword ptr [rbp-60h]
0x180020070  movups  xmmword ptr [rcx+r8+50h], xmm1
0x180020076  movaps  xmm1, [rbp+2240h+var_2290]
0x18002007a  movups  xmmword ptr [rcx+r8+60h], xmm0
0x180020080  movaps  xmm0, [rbp+2240h+var_2280]
0x180020084  movups  xmmword ptr [rcx+r8+70h], xmm1
0x18002008a  movaps  xmm1, xmmword ptr [rbp+2240h+var_2270]
0x18002008e  movups  xmmword ptr [rcx+r8+80h], xmm0
0x180020097  movups  xmmword ptr [rcx+r8+90h], xmm1
0x1800200a0  mov     [rcx+r8+0A0h], rax
0x1800200a8  jmp     loc_18001FFE5
0x1800200ad  add     r14d, r9d
0x1800200b0  jmp     loc_18001FFCC
0x1800200b5  add     ebx, r9d
0x1800200b8  jmp     loc_18001FF64
0x1800200bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800200c4  lea     rax, WPP_GLOBAL_Control
0x1800200cb  cmp     rcx, rax
0x1800200ce  jz      short loc_1800200EE
0x1800200d0  test    byte ptr [rcx+1Ch], 10h
0x1800200d4  jz      short loc_1800200EE
0x1800200d6  mov     rcx, [rcx+10h]
0x1800200da  lea     r8, WPP_9e5bd0d0d2233fe69730d263c30676fb_Traceguids
0x1800200e1  mov     edx, 2Ch ; ','
0x1800200e6  mov     r9d, r15d
0x1800200e9  call    WPP_SF_d
0x1800200ee  mov     r13d, [rsp+2340h+var_231C]
0x1800200f3  xor     ebx, ebx
0x1800200f5  test    r13d, r13d
0x1800200f8  jz      short loc_180020117
0x1800200fa  mov     rsi, [rsp+2340h+var_2308]
0x1800200ff  imul    rdi, r13, 0A8h
0x180020106  mov     rcx, [rdi+rsi+18h]
0x18002010b  call    SPDApiBufferFree
0x180020110  inc     ebx
0x180020112  cmp     ebx, r13d
0x180020115  jb      short loc_180020106
0x180020117  mov     eax, r15d
0x18002011a  jmp     loc_18001FEFA
```
