# CopyTxFilterOld

- ea: `0x18001d020`
- end: `0x18001d483`
- name: `CopyTxFilterOld`
- size: `1123`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int *)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18001da5c`
- `0x18001e3a4`

## callees

- `0x18000e510`
- `0x1800173d0`
- `0x1800175dc`
- `0x18001d020`
- `0x18001e514`
- `0x1800239f8`
- `0x180023ae0`
- `0x18004d05e`
- `0x18004d090`
- `0x18004d120`

## pseudocode

```c
__int64 __fastcall CopyTxFilterOld(__int64 a1, __int64 a2, unsigned int *a3)
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
  v5 = (__int32 *)(a1 + 84);
  *a3 = 0;
  v12 = *(_DWORD *)a1 == 1;
  v6 = (__int32 *)(a1 + 44);
  v7 = a1 + 44;
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
    GetV6AddressSubnets(a1 + 84, &v59, &v44);
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
    GetV4AddressSubnets(a1 + 84, &v59, &v44);
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
  GetPortRange(a1 + 132, &v45);
  GetPortRange(a1 + 140, &v46);
  v14 = *(_OWORD *)(a1 + 4);
  *(_QWORD *)&v52 = *(_QWORD *)(a1 + 124);
  v15 = *(_OWORD *)(a1 + 168);
  v48.m256i_i32[0] = *(_DWORD *)a1;
  *(_QWORD *)&v49 = *(_QWORD *)(a1 + 32);
  DWORD2(v49) = *(_DWORD *)(a1 + 40);
  *((_QWORD *)&v53 + 1) = *(_QWORD *)(a1 + 148);
  v16 = v42;
  *(_QWORD *)&v54[0] = 0;
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
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, WPP_d3e4a8f1960430b115941304a22a5749_Traceguids, v25);
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
0x18001d020  mov     [rsp-8+arg_18], rbx
0x18001d025  push    rbp
0x18001d026  push    rsi
0x18001d027  push    rdi
0x18001d028  push    r12
0x18001d02a  push    r13
0x18001d02c  push    r14
0x18001d02e  push    r15
0x18001d030  lea     rbp, [rsp-2210h]
0x18001d038  mov     eax, 2310h
0x18001d03d  call    _alloca_probe
0x18001d042  sub     rsp, rax
0x18001d045  mov     rax, cs:__security_cookie
0x18001d04c  xor     rax, rsp
0x18001d04f  mov     [rbp+2240h+var_40], rax
0x18001d056  mov     rbx, r8
0x18001d059  mov     [rsp+2340h+var_2308], rdx
0x18001d05e  mov     rdi, rcx
0x18001d061  mov     [rbp+2240h+var_2250], rbx
0x18001d065  xor     edx, edx; Val
0x18001d067  lea     rcx, [rsp+2340h+var_2300]; void *
0x18001d06c  mov     r8d, 0A8h; Size
0x18001d072  call    memset_0
0x18001d077  mov     esi, 1100h
0x18001d07c  lea     rcx, [rbp+2240h+var_2240]; void *
0x18001d080  mov     r8d, esi; Size
0x18001d083  xor     edx, edx; Val
0x18001d085  call    memset_0
0x18001d08a  mov     r8d, esi; Size
0x18001d08d  lea     rcx, [rbp+2240h+var_1140]; void *
0x18001d094  xor     edx, edx; Val
0x18001d096  call    memset_0
0x18001d09b  xor     eax, eax
0x18001d09d  lea     rsi, [rdi+54h]
0x18001d0a1  mov     [rbx], eax
0x18001d0a3  lea     r8, [rsp+2340h+var_2320]
0x18001d0a8  cmp     dword ptr [rdi], 1
0x18001d0ab  lea     rbx, [rdi+2Ch]
0x18001d0af  mov     rcx, rbx
0x18001d0b2  mov     [rsp+2340h+var_2314], eax
0x18001d0b6  mov     [rsp+2340h+var_2310], eax
0x18001d0ba  lea     rdx, [rbp+2240h+var_2240]
0x18001d0be  mov     [rsp+2340h+var_2320], eax
0x18001d0c2  mov     r13d, eax
0x18001d0c5  mov     [rsp+2340h+var_2318], eax
0x18001d0c9  mov     r15d, eax
0x18001d0cc  mov     [rsp+2340h+var_231C], eax
0x18001d0d0  mov     r14d, eax
0x18001d0d3  jnz     short loc_18001D135
0x18001d0d5  call    GetV6AddressSubnets
0x18001d0da  lea     r8, [rsp+2340h+var_2318]
0x18001d0df  mov     rcx, rsi
0x18001d0e2  lea     rdx, [rbp+2240h+var_1140]
0x18001d0e9  call    GetV6AddressSubnets
0x18001d0ee  mov     ecx, 2
0x18001d0f3  lea     r9d, [rcx-1]
0x18001d0f7  cmp     [rsp+2340h+var_2320], r9d
0x18001d0fc  jnz     short loc_18001D10B
0x18001d0fe  cmp     [rbp+2240h+var_2230], 80h
0x18001d102  jnz     short loc_18001D10B
0x18001d104  mov     dword ptr [rsp+2340h+var_22D0], r9d
0x18001d109  jmp     short loc_18001D122
0x18001d10b  mov     edx, [rbx]
0x18001d10d  lea     eax, [rdx-4]
0x18001d110  cmp     eax, 3
0x18001d113  jbe     short loc_18001D11B
0x18001d115  mov     dword ptr [rsp+2340h+var_22D0], ecx
0x18001d119  jmp     short loc_18001D122
0x18001d11b  mov     dword ptr [rsp+2340h+var_22D0], edx
0x18001d11f  mov     r15d, r9d
0x18001d122  mov     r12d, [rsp+2340h+var_2318]
0x18001d127  cmp     r12d, r9d
0x18001d12a  jnz     short loc_18001D19F
0x18001d12c  cmp     [rbp+2240h+var_1130], 80h
0x18001d133  jmp     short loc_18001D197
0x18001d135  call    GetV4AddressSubnets
0x18001d13a  lea     r8, [rsp+2340h+var_2318]
0x18001d13f  mov     rcx, rsi
0x18001d142  lea     rdx, [rbp+2240h+var_1140]
0x18001d149  call    GetV4AddressSubnets
0x18001d14e  mov     ecx, 2
0x18001d153  or      r8d, 0FFFFFFFFh
0x18001d157  lea     r9d, [rcx-1]
0x18001d15b  cmp     [rsp+2340h+var_2320], r9d
0x18001d160  jnz     short loc_18001D16F
0x18001d162  cmp     [rbp+2240h+var_223C], r8d
0x18001d166  jnz     short loc_18001D16F
0x18001d168  mov     dword ptr [rsp+2340h+var_22D0], r9d
0x18001d16d  jmp     short loc_18001D186
0x18001d16f  mov     edx, [rbx]
0x18001d171  lea     eax, [rdx-4]
0x18001d174  cmp     eax, 3
0x18001d177  jbe     short loc_18001D17F
0x18001d179  mov     dword ptr [rsp+2340h+var_22D0], ecx
0x18001d17d  jmp     short loc_18001D186
0x18001d17f  mov     dword ptr [rsp+2340h+var_22D0], edx
0x18001d183  mov     r15d, r9d
0x18001d186  mov     r12d, [rsp+2340h+var_2318]
0x18001d18b  cmp     r12d, r9d
0x18001d18e  jnz     short loc_18001D19F
0x18001d190  cmp     [rbp+2240h+var_113C], r8d
0x18001d197  jnz     short loc_18001D19F
0x18001d199  mov     dword ptr [rbp+2240h+var_22B0], r9d
0x18001d19d  jmp     short loc_18001D1B4
0x18001d19f  mov     edx, [rsi]
0x18001d1a1  lea     eax, [rdx-4]
0x18001d1a4  cmp     eax, 3
0x18001d1a7  jbe     short loc_18001D1AE
0x18001d1a9  mov     dword ptr [rbp+2240h+var_22B0], ecx
0x18001d1ac  jmp     short loc_18001D1B4
0x18001d1ae  mov     r14d, r9d
0x18001d1b1  mov     dword ptr [rbp+2240h+var_22B0], edx
0x18001d1b4  lea     rcx, [rdi+84h]
0x18001d1bb  lea     rdx, [rsp+2340h+var_2314]
0x18001d1c0  call    GetPortRange
0x18001d1c5  lea     rcx, [rdi+8Ch]
0x18001d1cc  lea     rdx, [rsp+2340h+var_2310]
0x18001d1d1  call    GetPortRange
0x18001d1d6  mov     rax, [rdi+7Ch]
0x18001d1da  movups  xmm0, xmmword ptr [rdi+4]
0x18001d1de  mov     qword ptr [rbp+2240h+var_2290], rax
0x18001d1e2  mov     eax, [rdi]
0x18001d1e4  movups  xmm1, xmmword ptr [rdi+0A8h]
0x18001d1eb  mov     dword ptr [rsp+2340h+var_2300], eax
0x18001d1ef  mov     eax, [rdi+20h]
0x18001d1f2  mov     dword ptr [rsp+2340h+var_22E0], eax
0x18001d1f6  mov     eax, [rdi+24h]
0x18001d1f9  mov     dword ptr [rsp+2340h+var_22E0+4], eax
0x18001d1fd  mov     eax, [rdi+28h]
0x18001d200  mov     dword ptr [rsp+2340h+var_22E0+8], eax
0x18001d204  mov     eax, [rdi+94h]
0x18001d20a  mov     dword ptr [rbp+2240h+var_2280+8], eax
0x18001d20d  mov     eax, [rdi+98h]
0x18001d213  mov     dword ptr [rbp+2240h+var_2280+0Ch], eax
0x18001d216  mov     eax, [rsp+2340h+var_2320]
0x18001d21a  mov     qword ptr [rbp+2240h+var_2270], r13
0x18001d21e  mov     dword ptr [rbp+2240h+var_2280], r9d
0x18001d222  mov     dword ptr [rbp+2240h+var_2290+8], r9d
0x18001d226  movdqu  [rsp+2340h+var_2300+4], xmm0
0x18001d22c  movdqu  xmmword ptr [rbp+2240h+var_2270+8], xmm1
0x18001d231  test    eax, eax
0x18001d233  jnz     short loc_18001D23A
0x18001d235  test    r15d, r15d
0x18001d238  jz      short loc_18001D255
0x18001d23a  test    r12d, r12d
0x18001d23d  jnz     short loc_18001D244
0x18001d23f  test    r14d, r14d
0x18001d242  jz      short loc_18001D255
0x18001d244  xor     esi, esi
0x18001d246  cmp     esi, eax
0x18001d248  ja      short loc_18001D250
0x18001d24a  jnz     short loc_18001D288
0x18001d24c  test    esi, esi
0x18001d24e  jz      short loc_18001D2C6
0x18001d250  mov     r13d, [rsp+2340h+var_231C]
0x18001d255  mov     rax, [rbp+2240h+var_2250]
0x18001d259  mov     [rax], r13d
0x18001d25c  xor     eax, eax
0x18001d25e  mov     rcx, [rbp+2240h+var_40]
0x18001d265  xor     rcx, rsp; StackCookie
0x18001d268  call    __security_check_cookie
0x18001d26d  mov     rbx, [rsp+2340h+arg_18]
0x18001d275  add     rsp, 2310h
0x18001d27c  pop     r15
0x18001d27e  pop     r14
0x18001d280  pop     r13
0x18001d282  pop     r12
0x18001d284  pop     rdi
0x18001d285  pop     rsi
0x18001d286  pop     rbp
0x18001d287  retn
0x18001d288  mov     ecx, esi
0x18001d28a  cmp     [rdi], r9d
0x18001d28d  jnz     short loc_18001D2B6
0x18001d28f  imul    rcx, 11h
0x18001d293  mov     eax, [rbp+rcx+2240h+var_2240]
0x18001d297  mov     dword ptr [rsp+2340h+var_22D0+4], eax
0x18001d29b  mov     eax, [rbp+rcx+2240h+var_223C]
0x18001d29f  mov     dword ptr [rsp+2340h+var_22D0+8], eax
0x18001d2a3  mov     rax, [rbp+rcx+2240h+var_2238]
0x18001d2a8  mov     qword ptr [rsp+2340h+var_22D0+0Ch], rax
0x18001d2ad  mov     al, [rbp+rcx+2240h+var_2230]
0x18001d2b1  mov     [rbp+2240h+var_22BC], al
0x18001d2b4  jmp     short loc_18001D2C6
0x18001d2b6  mov     eax, [rbp+rsi*8+2240h+var_2240]
0x18001d2ba  mov     dword ptr [rsp+2340h+var_22D0+4], eax
0x18001d2be  mov     eax, [rbp+rsi*8+2240h+var_223C]
0x18001d2c2  mov     dword ptr [rsp+2340h+var_22D0+8], eax
0x18001d2c6  xor     ebx, ebx
0x18001d2c8  cmp     ebx, r12d
0x18001d2cb  ja      short loc_18001D2D3
0x18001d2cd  jnz     short loc_18001D2DF
0x18001d2cf  test    ebx, ebx
0x18001d2d1  jz      short loc_18001D32A
0x18001d2d3  mov     eax, [rsp+2340h+var_2320]
0x18001d2d7  add     esi, r9d
0x18001d2da  jmp     loc_18001D246
0x18001d2df  mov     ecx, ebx
0x18001d2e1  cmp     [rdi], r9d
0x18001d2e4  jnz     short loc_18001D316
0x18001d2e6  imul    rcx, 11h
0x18001d2ea  mov     eax, [rbp+rcx+2240h+var_1140]
0x18001d2f1  mov     dword ptr [rbp+2240h+var_22B0+4], eax
0x18001d2f4  mov     eax, [rbp+rcx+2240h+var_113C]
0x18001d2fb  mov     dword ptr [rbp+2240h+var_22B0+8], eax
0x18001d2fe  mov     rax, [rbp+rcx+2240h+var_1138]
0x18001d306  mov     qword ptr [rbp+2240h+var_22B0+0Ch], rax
0x18001d30a  mov     al, [rbp+rcx+2240h+var_1130]
0x18001d311  mov     [rbp+2240h+var_229C], al
0x18001d314  jmp     short loc_18001D32A
0x18001d316  mov     eax, [rbp+rbx*8+2240h+var_1140]
0x18001d31d  mov     dword ptr [rbp+2240h+var_22B0+4], eax
0x18001d320  mov     eax, [rbp+rbx*8+2240h+var_113C]
0x18001d327  mov     dword ptr [rbp+2240h+var_22B0+8], eax
0x18001d32a  movzx   r14d, word ptr [rsp+2340h+var_2314]
0x18001d330  movzx   eax, word ptr [rsp+2340h+var_2314+2]
0x18001d335  cmp     r14d, eax
0x18001d338  ja      loc_18001D419
0x18001d33e  movzx   r13d, word ptr [rsp+2340h+var_2310]
0x18001d344  mov     word ptr [rbp+2240h+var_2290+0Ch], r14w
0x18001d349  movzx   eax, word ptr [rsp+2340h+var_2310+2]
0x18001d34e  cmp     r13d, eax
0x18001d351  ja      loc_18001D411
0x18001d357  mov     rcx, [rdi+18h]; pszSrc
0x18001d35b  lea     rdx, [rsp+2340h+var_22E8]
0x18001d360  mov     word ptr [rbp+2240h+var_2280+4], r13w
0x18001d365  call    CopyName
0x18001d36a  mov     r15d, eax
0x18001d36d  test    eax, eax
0x18001d36f  jnz     loc_18001D421
0x18001d375  mov     r8, [rsp+2340h+var_2308]
0x18001d37a  lea     r9d, [r15+1]
0x18001d37e  mov     edx, [rsp+2340h+var_231C]
0x18001d382  movaps  xmm0, [rsp+2340h+var_2300]
0x18001d387  movaps  xmm1, xmmword ptr [rsp+50h]
0x18001d38c  mov     rax, qword ptr [rbp+2240h+var_2270+10h]
0x18001d390  imul    rcx, rdx, 0A8h
0x18001d397  add     edx, r9d
0x18001d39a  mov     [rsp+2340h+var_231C], edx
0x18001d39e  add     r13d, r9d
0x18001d3a1  movups  xmmword ptr [rcx+r8], xmm0
0x18001d3a6  movaps  xmm0, [rsp+2340h+var_22E0]
0x18001d3ab  movups  xmmword ptr [rcx+r8+10h], xmm1
0x18001d3b1  movaps  xmm1, [rsp+2340h+var_22D0]
0x18001d3b6  movups  xmmword ptr [rcx+r8+20h], xmm0
0x18001d3bc  movaps  xmm0, xmmword ptr [rbp-80h]
0x18001d3c0  movups  xmmword ptr [rcx+r8+30h], xmm1
0x18001d3c6  movaps  xmm1, [rbp+2240h+var_22B0]
0x18001d3ca  movups  xmmword ptr [rcx+r8+40h], xmm0
0x18001d3d0  movaps  xmm0, xmmword ptr [rbp-60h]
0x18001d3d4  movups  xmmword ptr [rcx+r8+50h], xmm1
0x18001d3da  movaps  xmm1, [rbp+2240h+var_2290]
0x18001d3de  movups  xmmword ptr [rcx+r8+60h], xmm0
0x18001d3e4  movaps  xmm0, [rbp+2240h+var_2280]
0x18001d3e8  movups  xmmword ptr [rcx+r8+70h], xmm1
0x18001d3ee  movaps  xmm1, xmmword ptr [rbp+2240h+var_2270]
0x18001d3f2  movups  xmmword ptr [rcx+r8+80h], xmm0
0x18001d3fb  movups  xmmword ptr [rcx+r8+90h], xmm1
0x18001d404  mov     [rcx+r8+0A0h], rax
0x18001d40c  jmp     loc_18001D349
0x18001d411  add     r14d, r9d
0x18001d414  jmp     loc_18001D330
0x18001d419  add     ebx, r9d
0x18001d41c  jmp     loc_18001D2C8
0x18001d421  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d428  lea     rax, WPP_GLOBAL_Control
0x18001d42f  cmp     rcx, rax
0x18001d432  jz      short loc_18001D452
0x18001d434  test    byte ptr [rcx+1Ch], 10h
0x18001d438  jz      short loc_18001D452
0x18001d43a  mov     rcx, [rcx+10h]
0x18001d43e  lea     r8, WPP_d3e4a8f1960430b115941304a22a5749_Traceguids
0x18001d445  mov     edx, 48h ; 'H'
0x18001d44a  mov     r9d, r15d
0x18001d44d  call    WPP_SF_d
0x18001d452  mov     r13d, [rsp+2340h+var_231C]
0x18001d457  xor     ebx, ebx
0x18001d459  test    r13d, r13d
0x18001d45c  jz      short loc_18001D47B
0x18001d45e  mov     rsi, [rsp+2340h+var_2308]
0x18001d463  imul    rdi, r13, 0A8h
0x18001d46a  mov     rcx, [rdi+rsi+18h]
0x18001d46f  call    SPDApiBufferFree
0x18001d474  inc     ebx
0x18001d476  cmp     ebx, r13d
0x18001d479  jb      short loc_18001D46A
0x18001d47b  mov     eax, r15d
0x18001d47e  jmp     loc_18001D25E
```
