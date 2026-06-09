# CopyMMSFilterOld

- ea: `0x1800259f0`
- end: `0x180025dc7`
- name: `CopyMMSFilterOld`
- size: `983`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int *)`
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0x180025f48`
- `0x180026218`
- `0x1800269a0`

## callees

- `0x18000e510`
- `0x1800173d0`
- `0x1800175dc`
- `0x1800239f8`
- `0x180023ae0`
- `0x1800259f0`
- `0x18004d05e`
- `0x18004d090`
- `0x18004d120`

## pseudocode

```c
__int64 __fastcall CopyMMSFilterOld(__int64 a1, __int64 a2, unsigned int *a3)
{
  __int32 *v5; // rdi
  __int32 *v6; // rbx
  __int64 v7; // rcx
  unsigned int v8; // r12d
  int v9; // r15d
  int v10; // esi
  unsigned int v11; // r13d
  __int32 v12; // edx
  unsigned int v13; // ebx
  bool v14; // zf
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int64 v17; // rdi
  __int64 v19; // rcx
  __int64 v20; // rsi
  __int64 v21; // rcx
  unsigned int v22; // r15d
  __int64 v23; // rdx
  __int128 v24; // xmm1
  __int64 v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rax
  __int128 v28; // xmm0
  __int128 v29; // xmm1
  __int128 v30; // xmm0
  __int128 v31; // xmm1
  __int128 v32; // xmm0
  __int128 v33; // xmm1
  __int128 v34; // xmm0
  unsigned int v35; // ebx
  __int64 v36; // rsi
  unsigned int v37; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int v38; // [rsp+24h] [rbp-DCh] BYREF
  __int64 v39; // [rsp+28h] [rbp-D8h]
  __m256i v40; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v41; // [rsp+50h] [rbp-B0h]
  __m256i v42; // [rsp+60h] [rbp-A0h]
  __m256i v43; // [rsp+80h] [rbp-80h]
  _BYTE v44[40]; // [rsp+A0h] [rbp-60h]
  unsigned int *v45; // [rsp+D0h] [rbp-30h]
  int v46; // [rsp+E0h] [rbp-20h] BYREF
  _DWORD v47[3]; // [rsp+E4h] [rbp-1Ch]
  _BYTE v48[4336]; // [rsp+F0h] [rbp-10h]
  int v49; // [rsp+11E0h] [rbp+10E0h] BYREF
  _DWORD v50[3]; // [rsp+11E4h] [rbp+10E4h]
  _BYTE v51[4336]; // [rsp+11F0h] [rbp+10F0h]

  v39 = a2;
  v45 = a3;
  memset_0(&v40, 0, 0x98u);
  memset_0(&v46, 0, 0x1100u);
  memset_0(&v49, 0, 0x1100u);
  v5 = (__int32 *)(a1 + 80);
  *a3 = 0;
  v14 = *(_DWORD *)a1 == 1;
  v6 = (__int32 *)(a1 + 40);
  v7 = a1 + 40;
  v38 = 0;
  v37 = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  if ( v14 )
  {
    GetV6AddressSubnets(v7, &v46, &v38);
    GetV6AddressSubnets(v5, &v49, &v37);
    v11 = v38;
    if ( (unsigned int)(*v6 - 4) <= 3 )
    {
      v42.m256i_i32[0] = *v6;
      v9 = 1;
    }
    else if ( v38 == 1 && v48[0] == 0x80 )
    {
      v42.m256i_i32[0] = 1;
    }
    else
    {
      v42.m256i_i32[0] = 2;
    }
    v12 = *v5;
    v13 = v37;
    if ( (unsigned int)(*v5 - 4) > 3 )
    {
      if ( v37 == 1 )
      {
        v14 = v51[0] == 0x80;
        goto LABEL_20;
      }
LABEL_22:
      v43.m256i_i32[0] = 2;
      goto LABEL_24;
    }
LABEL_23:
    v10 = 1;
    v43.m256i_i32[0] = v12;
    goto LABEL_24;
  }
  GetV4AddressSubnets(v7, &v46, &v38);
  GetV4AddressSubnets(v5, &v49, &v37);
  v11 = v38;
  if ( (unsigned int)(*v6 - 4) <= 3 )
  {
    v42.m256i_i32[0] = *v6;
    v9 = 1;
  }
  else if ( v38 == 1 && v47[0] == -1 )
  {
    v42.m256i_i32[0] = 1;
  }
  else
  {
    v42.m256i_i32[0] = 2;
  }
  v12 = *v5;
  v13 = v37;
  if ( (unsigned int)(*v5 - 4) <= 3 )
    goto LABEL_23;
  if ( v37 != 1 )
    goto LABEL_22;
  v14 = v50[0] == -1;
LABEL_20:
  if ( !v14 )
    goto LABEL_22;
  v43.m256i_i32[0] = 1;
LABEL_24:
  v40.m256i_i32[0] = *(_DWORD *)a1;
  *(_QWORD *)&v41 = *(unsigned int *)(a1 + 32);
  DWORD2(v41) = *(_DWORD *)(a1 + 36);
  *(_QWORD *)v44 = *(_QWORD *)(a1 + 124);
  v15 = *(_OWORD *)(a1 + 132);
  *(_OWORD *)((char *)v40.m256i_i64 + 4) = *(_OWORD *)(a1 + 4);
  v16 = *(_OWORD *)(a1 + 148);
  *(_OWORD *)&v44[8] = v15;
  *(_OWORD *)&v44[24] = v16;
  if ( !v11 && !v9 || !v13 && !v10 )
    goto LABEL_32;
  v17 = 0;
LABEL_29:
  if ( (unsigned int)v17 > v11 )
    goto LABEL_32;
  if ( (_DWORD)v17 == v11 )
  {
    if ( (_DWORD)v17 )
    {
LABEL_32:
      *v45 = v8;
      return 0;
    }
  }
  else if ( *(_DWORD *)a1 == 1 )
  {
    v19 = 17LL * (unsigned int)v17;
    v42.m256i_i32[1] = *(_DWORD *)((char *)&v47[-1] + v19);
    v42.m256i_i32[2] = *(_DWORD *)((char *)v47 + v19);
    *(__int64 *)((char *)&v42.m256i_i64[1] + 4) = *(_QWORD *)((char *)&v47[1] + v19);
    v42.m256i_i8[20] = v48[v19];
  }
  else
  {
    v42.m256i_i32[1] = v47[2 * v17 - 1];
    v42.m256i_i32[2] = v47[2 * v17];
  }
  v20 = 0;
  while ( 1 )
  {
    if ( (unsigned int)v20 > v13 )
    {
LABEL_40:
      v17 = (unsigned int)(v17 + 1);
      goto LABEL_29;
    }
    if ( (_DWORD)v20 == v13 )
    {
      if ( (_DWORD)v20 )
        goto LABEL_40;
    }
    else if ( *(_DWORD *)a1 == 1 )
    {
      v21 = 17LL * (unsigned int)v20;
      v43.m256i_i32[1] = *(_DWORD *)((char *)&v50[-1] + v21);
      v43.m256i_i32[2] = *(_DWORD *)((char *)v50 + v21);
      *(__int64 *)((char *)&v43.m256i_i64[1] + 4) = *(_QWORD *)((char *)&v50[1] + v21);
      v43.m256i_i8[20] = v51[v21];
    }
    else
    {
      v43.m256i_i32[1] = v50[2 * v20 - 1];
      v43.m256i_i32[2] = v50[2 * v20];
    }
    v22 = CopyName(*(STRSAFE_LPCWSTR *)(a1 + 24));
    if ( v22 )
      break;
    v23 = v39;
    v24 = *(_OWORD *)&v40.m256i_u64[2];
    v25 = v8++;
    v26 = 152 * v25;
    v27 = *(_QWORD *)&v44[32];
    v20 = (unsigned int)(v20 + 1);
    *(_OWORD *)(v26 + v39) = *(_OWORD *)v40.m256i_i8;
    v28 = v41;
    *(_OWORD *)(v26 + v23 + 16) = v24;
    v29 = *(_OWORD *)v42.m256i_i8;
    *(_OWORD *)(v26 + v23 + 32) = v28;
    v30 = *(_OWORD *)&v42.m256i_u64[2];
    *(_OWORD *)(v26 + v23 + 48) = v29;
    v31 = *(_OWORD *)v43.m256i_i8;
    *(_OWORD *)(v26 + v23 + 64) = v30;
    v32 = *(_OWORD *)&v43.m256i_u64[2];
    *(_OWORD *)(v26 + v23 + 80) = v31;
    v33 = *(_OWORD *)v44;
    *(_OWORD *)(v26 + v23 + 96) = v32;
    v34 = *(_OWORD *)&v44[16];
    *(_OWORD *)(v26 + v23 + 112) = v33;
    *(_OWORD *)(v26 + v23 + 128) = v34;
    *(_QWORD *)(v26 + v23 + 144) = v27;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_3e4f3b06ae6c3f7ee57f4df714640ff4_Traceguids, v22);
  v35 = 0;
  if ( v8 )
  {
    v36 = v39;
    do
    {
      SPDApiBufferFree(*(_QWORD *)(152LL * v8 + v36 + 24));
      ++v35;
    }
    while ( v35 < v8 );
  }
  return v22;
}

```

## disassembly

```asm
0x1800259f0  mov     [rsp-8+arg_18], rbx
0x1800259f5  push    rbp
0x1800259f6  push    rsi
0x1800259f7  push    rdi
0x1800259f8  push    r12
0x1800259fa  push    r13
0x1800259fc  push    r14
0x1800259fe  push    r15
0x180025a00  lea     rbp, [rsp-21F0h]
0x180025a08  mov     eax, 22F0h
0x180025a0d  call    _alloca_probe
0x180025a12  sub     rsp, rax
0x180025a15  mov     rax, cs:__security_cookie
0x180025a1c  xor     rax, rsp
0x180025a1f  mov     [rbp+2220h+var_40], rax
0x180025a26  mov     rbx, r8
0x180025a29  mov     [rsp+2320h+var_22F8], rdx
0x180025a2e  mov     r14, rcx
0x180025a31  mov     [rbp+2220h+var_2250], rbx
0x180025a35  xor     edx, edx; Val
0x180025a37  lea     rcx, [rsp+2320h+var_22F0]; void *
0x180025a3c  mov     r8d, 98h; Size
0x180025a42  call    memset_0
0x180025a47  mov     edi, 1100h
0x180025a4c  lea     rcx, [rbp+2220h+var_2240]; void *
0x180025a50  mov     r8d, edi; Size
0x180025a53  xor     edx, edx; Val
0x180025a55  call    memset_0
0x180025a5a  mov     r8d, edi; Size
0x180025a5d  lea     rcx, [rbp+2220h+var_1140]; void *
0x180025a64  xor     edx, edx; Val
0x180025a66  call    memset_0
0x180025a6b  xor     eax, eax
0x180025a6d  lea     rdi, [r14+50h]
0x180025a71  mov     [rbx], eax
0x180025a73  lea     r8, [rsp+2320h+var_22FC]
0x180025a78  cmp     dword ptr [r14], 1
0x180025a7c  lea     rbx, [r14+28h]
0x180025a80  mov     rcx, rbx
0x180025a83  mov     [rsp+2320h+var_22FC], eax
0x180025a87  mov     [rsp+2320h+var_2300], eax
0x180025a8b  lea     rdx, [rbp+2220h+var_2240]
0x180025a8f  mov     r12d, eax
0x180025a92  mov     r15d, eax
0x180025a95  mov     esi, eax
0x180025a97  jnz     short loc_180025B09
0x180025a99  call    GetV6AddressSubnets
0x180025a9e  lea     r8, [rsp+2320h+var_2300]
0x180025aa3  mov     rcx, rdi
0x180025aa6  lea     rdx, [rbp+2220h+var_1140]
0x180025aad  call    GetV6AddressSubnets
0x180025ab2  mov     edx, [rbx]
0x180025ab4  mov     ecx, 2
0x180025ab9  mov     r13d, [rsp+2320h+var_22FC]
0x180025abe  lea     eax, [rdx-4]
0x180025ac1  lea     r8d, [rcx-1]
0x180025ac5  cmp     eax, 3
0x180025ac8  jbe     short loc_180025AE2
0x180025aca  cmp     r13d, r8d
0x180025acd  jnz     short loc_180025ADC
0x180025acf  cmp     [rbp+2220h+var_2230], 80h
0x180025ad3  jnz     short loc_180025ADC
0x180025ad5  mov     dword ptr [rsp+2320h+var_22C0], r8d
0x180025ada  jmp     short loc_180025AE9
0x180025adc  mov     dword ptr [rsp+2320h+var_22C0], ecx
0x180025ae0  jmp     short loc_180025AE9
0x180025ae2  mov     dword ptr [rsp+2320h+var_22C0], edx
0x180025ae6  mov     r15d, r8d
0x180025ae9  mov     edx, [rdi]
0x180025aeb  mov     ebx, [rsp+2320h+var_2300]
0x180025aef  lea     eax, [rdx-4]
0x180025af2  cmp     eax, 3
0x180025af5  jbe     loc_180025B84
0x180025afb  cmp     ebx, r8d
0x180025afe  jnz     short loc_180025B7F
0x180025b00  cmp     [rbp+2220h+var_1130], 80h
0x180025b07  jmp     short loc_180025B77
0x180025b09  call    GetV4AddressSubnets
0x180025b0e  lea     r8, [rsp+2320h+var_2300]
0x180025b13  mov     rcx, rdi
0x180025b16  lea     rdx, [rbp+2220h+var_1140]
0x180025b1d  call    GetV4AddressSubnets
0x180025b22  mov     edx, [rbx]
0x180025b24  mov     ecx, 2
0x180025b29  mov     r13d, [rsp+2320h+var_22FC]
0x180025b2e  or      r9d, 0FFFFFFFFh
0x180025b32  lea     eax, [rdx-4]
0x180025b35  lea     r8d, [rcx-1]
0x180025b39  cmp     eax, 3
0x180025b3c  jbe     short loc_180025B56
0x180025b3e  cmp     r13d, r8d
0x180025b41  jnz     short loc_180025B50
0x180025b43  cmp     [rbp+2220h+var_223C], r9d
0x180025b47  jnz     short loc_180025B50
0x180025b49  mov     dword ptr [rsp+2320h+var_22C0], r8d
0x180025b4e  jmp     short loc_180025B5D
0x180025b50  mov     dword ptr [rsp+2320h+var_22C0], ecx
0x180025b54  jmp     short loc_180025B5D
0x180025b56  mov     dword ptr [rsp+2320h+var_22C0], edx
0x180025b5a  mov     r15d, r8d
0x180025b5d  mov     edx, [rdi]
0x180025b5f  mov     ebx, [rsp+2320h+var_2300]
0x180025b63  lea     eax, [rdx-4]
0x180025b66  cmp     eax, 3
0x180025b69  jbe     short loc_180025B84
0x180025b6b  cmp     ebx, r8d
0x180025b6e  jnz     short loc_180025B7F
0x180025b70  cmp     [rbp+2220h+var_113C], r9d
0x180025b77  jnz     short loc_180025B7F
0x180025b79  mov     dword ptr [rbp+2220h+var_22A0], r8d
0x180025b7d  jmp     short loc_180025B8A
0x180025b7f  mov     dword ptr [rbp+2220h+var_22A0], ecx
0x180025b82  jmp     short loc_180025B8A
0x180025b84  mov     esi, r8d
0x180025b87  mov     dword ptr [rbp+2220h+var_22A0], edx
0x180025b8a  mov     eax, [r14]
0x180025b8d  mov     dword ptr [rsp+2320h+var_22F0], eax
0x180025b91  mov     eax, [r14+20h]
0x180025b95  mov     dword ptr [rsp+2320h+var_22D0], eax
0x180025b99  mov     eax, [r14+24h]
0x180025b9d  mov     dword ptr [rsp+2320h+var_22D0+8], eax
0x180025ba1  mov     eax, [r14+7Ch]
0x180025ba5  mov     dword ptr [rbp+2220h+var_2280], eax
0x180025ba8  mov     eax, [r14+80h]
0x180025baf  mov     dword ptr [rbp+2220h+var_2280+4], eax
0x180025bb2  mov     dword ptr [rsp+2320h+var_22D0+4], r12d
0x180025bb7  movups  xmm0, xmmword ptr [r14+4]
0x180025bbc  movups  xmm1, xmmword ptr [r14+84h]
0x180025bc4  movdqu  [rsp+2320h+var_22F0+4], xmm0
0x180025bca  movups  xmm0, xmmword ptr [r14+94h]
0x180025bd2  movdqu  [rbp+2220h+var_2280+8], xmm1
0x180025bd7  movdqu  [rbp+2220h+var_2268], xmm0
0x180025bdc  test    r13d, r13d
0x180025bdf  jnz     short loc_180025BE6
0x180025be1  test    r15d, r15d
0x180025be4  jz      short loc_180025BFB
0x180025be6  test    ebx, ebx
0x180025be8  jnz     short loc_180025BEE
0x180025bea  test    esi, esi
0x180025bec  jz      short loc_180025BFB
0x180025bee  xor     edi, edi
0x180025bf0  cmp     edi, r13d
0x180025bf3  ja      short loc_180025BFB
0x180025bf5  jnz     short loc_180025C2E
0x180025bf7  test    edi, edi
0x180025bf9  jz      short loc_180025C6D
0x180025bfb  mov     rax, [rbp+2220h+var_2250]
0x180025bff  mov     [rax], r12d
0x180025c02  xor     eax, eax
0x180025c04  mov     rcx, [rbp+2220h+var_40]
0x180025c0b  xor     rcx, rsp; StackCookie
0x180025c0e  call    __security_check_cookie
0x180025c13  mov     rbx, [rsp+2320h+arg_18]
0x180025c1b  add     rsp, 22F0h
0x180025c22  pop     r15
0x180025c24  pop     r14
0x180025c26  pop     r13
0x180025c28  pop     r12
0x180025c2a  pop     rdi
0x180025c2b  pop     rsi
0x180025c2c  pop     rbp
0x180025c2d  retn
0x180025c2e  mov     ecx, edi
0x180025c30  cmp     [r14], r8d
0x180025c33  jnz     short loc_180025C5D
0x180025c35  imul    rcx, 11h
0x180025c39  mov     eax, [rbp+rcx+2220h+var_2240]
0x180025c3d  mov     dword ptr [rsp+2320h+var_22C0+4], eax
0x180025c41  mov     eax, [rbp+rcx+2220h+var_223C]
0x180025c45  mov     dword ptr [rsp+2320h+var_22C0+8], eax
0x180025c49  mov     rax, [rbp+rcx+2220h+var_2238]
0x180025c4e  mov     qword ptr [rsp+2320h+var_22C0+0Ch], rax
0x180025c53  mov     al, [rbp+rcx+2220h+var_2230]
0x180025c57  mov     [rsp+2320h+var_22AC], al
0x180025c5b  jmp     short loc_180025C6D
0x180025c5d  mov     eax, [rbp+rdi*8+2220h+var_2240]
0x180025c61  mov     dword ptr [rsp+2320h+var_22C0+4], eax
0x180025c65  mov     eax, [rbp+rdi*8+2220h+var_223C]
0x180025c69  mov     dword ptr [rsp+2320h+var_22C0+8], eax
0x180025c6d  xor     esi, esi
0x180025c6f  cmp     esi, ebx
0x180025c71  ja      short loc_180025C79
0x180025c73  jnz     short loc_180025C81
0x180025c75  test    esi, esi
0x180025c77  jz      short loc_180025CCC
0x180025c79  add     edi, r8d
0x180025c7c  jmp     loc_180025BF0
0x180025c81  mov     ecx, esi
0x180025c83  cmp     [r14], r8d
0x180025c86  jnz     short loc_180025CB8
0x180025c88  imul    rcx, 11h
0x180025c8c  mov     eax, [rbp+rcx+2220h+var_1140]
0x180025c93  mov     dword ptr [rbp+2220h+var_22A0+4], eax
0x180025c96  mov     eax, [rbp+rcx+2220h+var_113C]
0x180025c9d  mov     dword ptr [rbp+2220h+var_22A0+8], eax
0x180025ca0  mov     rax, [rbp+rcx+2220h+var_1138]
0x180025ca8  mov     qword ptr [rbp+2220h+var_22A0+0Ch], rax
0x180025cac  mov     al, [rbp+rcx+2220h+var_1130]
0x180025cb3  mov     [rbp+2220h+var_228C], al
0x180025cb6  jmp     short loc_180025CCC
0x180025cb8  mov     eax, [rbp+rsi*8+2220h+var_1140]
0x180025cbf  mov     dword ptr [rbp+2220h+var_22A0+4], eax
0x180025cc2  mov     eax, [rbp+rsi*8+2220h+var_113C]
0x180025cc9  mov     dword ptr [rbp+2220h+var_22A0+8], eax
0x180025ccc  mov     rcx, [r14+18h]; pszSrc
0x180025cd0  lea     rdx, [rsp+2320h+var_22D8]
0x180025cd5  call    CopyName
0x180025cda  mov     r15d, eax
0x180025cdd  test    eax, eax
0x180025cdf  jnz     loc_180025D67
0x180025ce5  mov     rdx, [rsp+2320h+var_22F8]
0x180025cea  lea     r8d, [r15+1]
0x180025cee  movaps  xmm0, [rsp+2320h+var_22F0]
0x180025cf3  movaps  xmm1, xmmword ptr [rsp+40h]
0x180025cf8  mov     eax, r12d
0x180025cfb  add     r12d, r8d
0x180025cfe  imul    rcx, rax, 98h
0x180025d05  mov     rax, qword ptr [rbp+2220h+var_2268+8]
0x180025d09  add     esi, r8d
0x180025d0c  movups  xmmword ptr [rcx+rdx], xmm0
0x180025d10  movaps  xmm0, [rsp+2320h+var_22D0]
0x180025d15  movups  xmmword ptr [rcx+rdx+10h], xmm1
0x180025d1a  movaps  xmm1, [rsp+2320h+var_22C0]
0x180025d1f  movups  xmmword ptr [rcx+rdx+20h], xmm0
0x180025d24  movaps  xmm0, xmmword ptr [rsp+70h]
0x180025d29  movups  xmmword ptr [rcx+rdx+30h], xmm1
0x180025d2e  movaps  xmm1, [rbp+2220h+var_22A0]
0x180025d32  movups  xmmword ptr [rcx+rdx+40h], xmm0
0x180025d37  movaps  xmm0, xmmword ptr [rbp-70h]
0x180025d3b  movups  xmmword ptr [rcx+rdx+50h], xmm1
0x180025d40  movaps  xmm1, [rbp+2220h+var_2280]
0x180025d44  movups  xmmword ptr [rcx+rdx+60h], xmm0
0x180025d49  movaps  xmm0, xmmword ptr [rbp-50h]
0x180025d4d  movups  xmmword ptr [rcx+rdx+70h], xmm1
0x180025d52  movups  xmmword ptr [rcx+rdx+80h], xmm0
0x180025d5a  mov     [rcx+rdx+90h], rax
0x180025d62  jmp     loc_180025C6F
0x180025d67  mov     rcx, cs:WPP_GLOBAL_Control
0x180025d6e  lea     rax, WPP_GLOBAL_Control
0x180025d75  cmp     rcx, rax
0x180025d78  jz      short loc_180025D98
0x180025d7a  test    byte ptr [rcx+1Ch], 10h
0x180025d7e  jz      short loc_180025D98
0x180025d80  mov     rcx, [rcx+10h]
0x180025d84  lea     r8, WPP_3e4f3b06ae6c3f7ee57f4df714640ff4_Traceguids
0x180025d8b  mov     edx, 1Bh
0x180025d90  mov     r9d, r15d
0x180025d93  call    WPP_SF_d
0x180025d98  xor     ebx, ebx
0x180025d9a  test    r12d, r12d
0x180025d9d  jz      short loc_180025DBF
0x180025d9f  mov     rsi, [rsp+2320h+var_22F8]
0x180025da4  mov     eax, r12d
0x180025da7  imul    rdi, rax, 98h
0x180025dae  mov     rcx, [rdi+rsi+18h]
0x180025db3  call    SPDApiBufferFree
0x180025db8  inc     ebx
0x180025dba  cmp     ebx, r12d
0x180025dbd  jb      short loc_180025DAE
0x180025dbf  mov     eax, r15d
0x180025dc2  jmp     loc_180025C04
```
