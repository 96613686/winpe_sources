# CopyMMFilterOld

- ea: `0x180021f80`
- end: `0x180022342`
- name: `CopyMMFilterOld`
- size: `962`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int *)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x180022ed0`
- `0x1800237a4`

## callees

- `0x18000e510`
- `0x1800173d0`
- `0x1800175dc`
- `0x180021f80`
- `0x1800239f8`
- `0x180023ae0`
- `0x18004d05e`
- `0x18004d090`
- `0x18004d120`

## pseudocode

```c
__int64 __fastcall CopyMMFilterOld(__int64 a1, __int64 a2, unsigned int *a3)
{
  __int32 *v5; // rdi
  __int32 *v6; // rbx
  __int64 v7; // rcx
  unsigned int v8; // r12d
  int v9; // r14d
  unsigned int v10; // r13d
  unsigned int v11; // r15d
  bool v12; // zf
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int64 v15; // rbx
  __int64 v17; // rcx
  __int64 v18; // rdi
  __int64 v19; // rcx
  unsigned int v20; // r14d
  __int64 v21; // rdx
  __int128 v22; // xmm1
  __int64 v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rax
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  __int128 v28; // xmm0
  __int128 v29; // xmm1
  __int128 v30; // xmm0
  __int128 v31; // xmm1
  __int128 v32; // xmm0
  unsigned int v33; // ebx
  __int64 v34; // rsi
  unsigned int v35; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int v36; // [rsp+24h] [rbp-DCh] BYREF
  int v37; // [rsp+28h] [rbp-D8h]
  __int64 v38; // [rsp+30h] [rbp-D0h]
  __m256i v39; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v40; // [rsp+60h] [rbp-A0h]
  __m256i v41; // [rsp+70h] [rbp-90h]
  __m256i v42; // [rsp+90h] [rbp-70h]
  _BYTE v43[40]; // [rsp+B0h] [rbp-50h]
  unsigned int *v44; // [rsp+E0h] [rbp-20h]
  int v45; // [rsp+F0h] [rbp-10h] BYREF
  _DWORD v46[3]; // [rsp+F4h] [rbp-Ch]
  _BYTE v47[4336]; // [rsp+100h] [rbp+0h]
  int v48; // [rsp+11F0h] [rbp+10F0h] BYREF
  _DWORD v49[3]; // [rsp+11F4h] [rbp+10F4h]
  _BYTE v50[4336]; // [rsp+1200h] [rbp+1100h]

  v38 = a2;
  v44 = a3;
  memset_0(&v39, 0, 0x98u);
  memset_0(&v45, 0, 0x1100u);
  memset_0(&v48, 0, 0x1100u);
  v5 = (__int32 *)(a1 + 84);
  *a3 = 0;
  v12 = *(_DWORD *)a1 == 1;
  v6 = (__int32 *)(a1 + 44);
  v7 = a1 + 44;
  v35 = 0;
  v36 = 0;
  v8 = 0;
  v37 = 0;
  v9 = 0;
  if ( v12 )
  {
    GetV6AddressSubnets(v7, &v45, &v35);
    GetV6AddressSubnets(a1 + 84, &v48, &v36);
    v10 = v35;
    if ( v35 == 1 && v47[0] == 0x80 )
    {
      v41.m256i_i32[0] = 1;
    }
    else if ( (unsigned int)(*v6 - 4) <= 3 )
    {
      v41.m256i_i32[0] = *v6;
      v37 = 1;
    }
    else
    {
      v41.m256i_i32[0] = 2;
    }
    v11 = v36;
    if ( v36 != 1 )
      goto LABEL_20;
    v12 = v50[0] == 0x80;
  }
  else
  {
    GetV4AddressSubnets(v7, &v45, &v35);
    GetV4AddressSubnets(a1 + 84, &v48, &v36);
    v10 = v35;
    if ( v35 == 1 && v46[0] == -1 )
    {
      v41.m256i_i32[0] = 1;
    }
    else if ( (unsigned int)(*v6 - 4) <= 3 )
    {
      v41.m256i_i32[0] = *v6;
      v37 = 1;
    }
    else
    {
      v41.m256i_i32[0] = 2;
    }
    v11 = v36;
    if ( v36 != 1 )
      goto LABEL_20;
    v12 = v49[0] == -1;
  }
  if ( v12 )
  {
    v42.m256i_i32[0] = 1;
    goto LABEL_23;
  }
LABEL_20:
  if ( (unsigned int)(*v5 - 4) <= 3 )
  {
    v9 = 1;
    v42.m256i_i32[0] = *v5;
  }
  else
  {
    v42.m256i_i32[0] = 2;
  }
LABEL_23:
  v39.m256i_i32[0] = *(_DWORD *)a1;
  *(_QWORD *)&v40 = *(_QWORD *)(a1 + 32);
  DWORD2(v40) = *(_DWORD *)(a1 + 40);
  *(_QWORD *)v43 = 0;
  v13 = *(_OWORD *)(a1 + 136);
  *(_OWORD *)((char *)v39.m256i_i64 + 4) = *(_OWORD *)(a1 + 4);
  v14 = *(_OWORD *)(a1 + 152);
  *(_OWORD *)&v43[8] = v13;
  *(_OWORD *)&v43[24] = v14;
  if ( !v10 && !v37 || !v11 && !v9 )
    goto LABEL_31;
  v15 = 0;
LABEL_28:
  if ( (unsigned int)v15 > v10 )
    goto LABEL_31;
  if ( (_DWORD)v15 == v10 )
  {
    if ( (_DWORD)v15 )
    {
LABEL_31:
      *v44 = v8;
      return 0;
    }
  }
  else if ( *(_DWORD *)a1 == 1 )
  {
    v17 = 17LL * (unsigned int)v15;
    v41.m256i_i32[1] = *(_DWORD *)((char *)&v46[-1] + v17);
    v41.m256i_i32[2] = *(_DWORD *)((char *)v46 + v17);
    *(__int64 *)((char *)&v41.m256i_i64[1] + 4) = *(_QWORD *)((char *)&v46[1] + v17);
    v41.m256i_i8[20] = v47[v17];
  }
  else
  {
    v41.m256i_i32[1] = v46[2 * v15 - 1];
    v41.m256i_i32[2] = v46[2 * v15];
  }
  v18 = 0;
  while ( 1 )
  {
    if ( (unsigned int)v18 > v11 )
    {
LABEL_39:
      v15 = (unsigned int)(v15 + 1);
      goto LABEL_28;
    }
    if ( (_DWORD)v18 == v11 )
    {
      if ( (_DWORD)v18 )
        goto LABEL_39;
    }
    else if ( *(_DWORD *)a1 == 1 )
    {
      v19 = 17LL * (unsigned int)v18;
      v42.m256i_i32[1] = *(_DWORD *)((char *)&v49[-1] + v19);
      v42.m256i_i32[2] = *(_DWORD *)((char *)v49 + v19);
      *(__int64 *)((char *)&v42.m256i_i64[1] + 4) = *(_QWORD *)((char *)&v49[1] + v19);
      v42.m256i_i8[20] = v50[v19];
    }
    else
    {
      v42.m256i_i32[1] = v49[2 * v18 - 1];
      v42.m256i_i32[2] = v49[2 * v18];
    }
    v20 = CopyName(*(STRSAFE_LPCWSTR *)(a1 + 24));
    if ( v20 )
      break;
    v21 = v38;
    v22 = *(_OWORD *)&v39.m256i_u64[2];
    v23 = v8++;
    v24 = 152 * v23;
    v25 = *(_QWORD *)&v43[32];
    v18 = (unsigned int)(v18 + 1);
    *(_OWORD *)(v24 + v38) = *(_OWORD *)v39.m256i_i8;
    v26 = v40;
    *(_OWORD *)(v24 + v21 + 16) = v22;
    v27 = *(_OWORD *)v41.m256i_i8;
    *(_OWORD *)(v24 + v21 + 32) = v26;
    v28 = *(_OWORD *)&v41.m256i_u64[2];
    *(_OWORD *)(v24 + v21 + 48) = v27;
    v29 = *(_OWORD *)v42.m256i_i8;
    *(_OWORD *)(v24 + v21 + 64) = v28;
    v30 = *(_OWORD *)&v42.m256i_u64[2];
    *(_OWORD *)(v24 + v21 + 80) = v29;
    v31 = *(_OWORD *)v43;
    *(_OWORD *)(v24 + v21 + 96) = v30;
    v32 = *(_OWORD *)&v43[16];
    *(_OWORD *)(v24 + v21 + 112) = v31;
    *(_OWORD *)(v24 + v21 + 128) = v32;
    *(_QWORD *)(v24 + v21 + 144) = v25;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, WPP_7c0a21c92210358d3ee1e33826382c7b_Traceguids, v20);
  v33 = 0;
  if ( v8 )
  {
    v34 = v38;
    do
    {
      SPDApiBufferFree(*(_QWORD *)(152LL * v8 + v34 + 24));
      ++v33;
    }
    while ( v33 < v8 );
  }
  return v20;
}

```

## disassembly

```asm
0x180021f80  mov     [rsp-8+arg_18], rbx
0x180021f85  push    rbp
0x180021f86  push    rsi
0x180021f87  push    rdi
0x180021f88  push    r12
0x180021f8a  push    r13
0x180021f8c  push    r14
0x180021f8e  push    r15
0x180021f90  lea     rbp, [rsp-2200h]
0x180021f98  mov     eax, 2300h
0x180021f9d  call    _alloca_probe
0x180021fa2  sub     rsp, rax
0x180021fa5  mov     rax, cs:__security_cookie
0x180021fac  xor     rax, rsp
0x180021faf  mov     [rbp+2230h+var_40], rax
0x180021fb6  mov     rbx, r8
0x180021fb9  mov     [rsp+2330h+var_2300], rdx
0x180021fbe  mov     rsi, rcx
0x180021fc1  mov     [rbp+2230h+var_2250], rbx
0x180021fc5  xor     edx, edx; Val
0x180021fc7  lea     rcx, [rsp+2330h+var_22F0]; void *
0x180021fcc  mov     r8d, 98h; Size
0x180021fd2  call    memset_0
0x180021fd7  mov     edi, 1100h
0x180021fdc  lea     rcx, [rbp+2230h+var_2240]; void *
0x180021fe0  mov     r8d, edi; Size
0x180021fe3  xor     edx, edx; Val
0x180021fe5  call    memset_0
0x180021fea  mov     r8d, edi; Size
0x180021fed  lea     rcx, [rbp+2230h+var_1140]; void *
0x180021ff4  xor     edx, edx; Val
0x180021ff6  call    memset_0
0x180021ffb  xor     eax, eax
0x180021ffd  lea     rdi, [rsi+54h]
0x180022001  mov     [rbx], eax
0x180022003  lea     r8, [rsp+2330h+var_2310]
0x180022008  cmp     dword ptr [rsi], 1
0x18002200b  lea     rbx, [rsi+2Ch]
0x18002200f  mov     rcx, rbx
0x180022012  mov     [rsp+2330h+var_2310], eax
0x180022016  mov     [rsp+2330h+var_230C], eax
0x18002201a  lea     rdx, [rbp+2230h+var_2240]
0x18002201e  mov     r12d, eax
0x180022021  mov     [rsp+2330h+var_2308], eax
0x180022025  mov     r14d, eax
0x180022028  jnz     short loc_18002208F
0x18002202a  call    GetV6AddressSubnets
0x18002202f  lea     r8, [rsp+2330h+var_230C]
0x180022034  mov     rcx, rdi
0x180022037  lea     rdx, [rbp+2230h+var_1140]
0x18002203e  call    GetV6AddressSubnets
0x180022043  mov     r13d, [rsp+2330h+var_2310]
0x180022048  mov     ecx, 2
0x18002204d  lea     r8d, [rcx-1]
0x180022051  cmp     r13d, r8d
0x180022054  jnz     short loc_180022063
0x180022056  cmp     [rbp+2230h+var_2230], 80h
0x18002205a  jnz     short loc_180022063
0x18002205c  mov     dword ptr [rsp+2330h+var_22C0], r8d
0x180022061  jmp     short loc_18002207C
0x180022063  mov     edx, [rbx]
0x180022065  lea     eax, [rdx-4]
0x180022068  cmp     eax, 3
0x18002206b  jbe     short loc_180022073
0x18002206d  mov     dword ptr [rsp+2330h+var_22C0], ecx
0x180022071  jmp     short loc_18002207C
0x180022073  mov     dword ptr [rsp+2330h+var_22C0], edx
0x180022077  mov     [rsp+2330h+var_2308], r8d
0x18002207c  mov     r15d, [rsp+2330h+var_230C]
0x180022081  cmp     r15d, r8d
0x180022084  jnz     short loc_1800220FE
0x180022086  cmp     [rbp+2230h+var_1130], 80h
0x18002208d  jmp     short loc_1800220F6
0x18002208f  call    GetV4AddressSubnets
0x180022094  lea     r8, [rsp+2330h+var_230C]
0x180022099  mov     rcx, rdi
0x18002209c  lea     rdx, [rbp+2230h+var_1140]
0x1800220a3  call    GetV4AddressSubnets
0x1800220a8  mov     r13d, [rsp+2330h+var_2310]
0x1800220ad  mov     ecx, 2
0x1800220b2  or      r9d, 0FFFFFFFFh
0x1800220b6  lea     r8d, [rcx-1]
0x1800220ba  cmp     r13d, r8d
0x1800220bd  jnz     short loc_1800220CC
0x1800220bf  cmp     [rbp+2230h+var_223C], r9d
0x1800220c3  jnz     short loc_1800220CC
0x1800220c5  mov     dword ptr [rsp+2330h+var_22C0], r8d
0x1800220ca  jmp     short loc_1800220E5
0x1800220cc  mov     edx, [rbx]
0x1800220ce  lea     eax, [rdx-4]
0x1800220d1  cmp     eax, 3
0x1800220d4  jbe     short loc_1800220DC
0x1800220d6  mov     dword ptr [rsp+2330h+var_22C0], ecx
0x1800220da  jmp     short loc_1800220E5
0x1800220dc  mov     dword ptr [rsp+2330h+var_22C0], edx
0x1800220e0  mov     [rsp+2330h+var_2308], r8d
0x1800220e5  mov     r15d, [rsp+2330h+var_230C]
0x1800220ea  cmp     r15d, r8d
0x1800220ed  jnz     short loc_1800220FE
0x1800220ef  cmp     [rbp+2230h+var_113C], r9d
0x1800220f6  jnz     short loc_1800220FE
0x1800220f8  mov     dword ptr [rbp+2230h+var_22A0], r8d
0x1800220fc  jmp     short loc_180022113
0x1800220fe  mov     edx, [rdi]
0x180022100  lea     eax, [rdx-4]
0x180022103  cmp     eax, 3
0x180022106  jbe     short loc_18002210D
0x180022108  mov     dword ptr [rbp+2230h+var_22A0], ecx
0x18002210b  jmp     short loc_180022113
0x18002210d  mov     r14d, r8d
0x180022110  mov     dword ptr [rbp+2230h+var_22A0], edx
0x180022113  mov     eax, [rsi]
0x180022115  mov     dword ptr [rsp+2330h+var_22F0], eax
0x180022119  mov     eax, [rsi+20h]
0x18002211c  mov     dword ptr [rsp+2330h+var_22D0], eax
0x180022120  mov     eax, [rsi+24h]
0x180022123  mov     dword ptr [rsp+2330h+var_22D0+4], eax
0x180022127  mov     eax, [rsi+28h]
0x18002212a  mov     dword ptr [rsp+2330h+var_22D0+8], eax
0x18002212e  mov     qword ptr [rbp+2230h+var_2280], r12
0x180022132  movups  xmm0, xmmword ptr [rsi+4]
0x180022136  movups  xmm1, xmmword ptr [rsi+88h]
0x18002213d  movdqu  [rsp+2330h+var_22F0+4], xmm0
0x180022143  movups  xmm0, xmmword ptr [rsi+98h]
0x18002214a  movdqu  [rbp+2230h+var_2280+8], xmm1
0x18002214f  movdqu  [rbp+2230h+var_2268], xmm0
0x180022154  test    r13d, r13d
0x180022157  jnz     short loc_180022160
0x180022159  cmp     [rsp+2330h+var_2308], r12d
0x18002215e  jz      short loc_180022177
0x180022160  test    r15d, r15d
0x180022163  jnz     short loc_18002216A
0x180022165  test    r14d, r14d
0x180022168  jz      short loc_180022177
0x18002216a  xor     ebx, ebx
0x18002216c  cmp     ebx, r13d
0x18002216f  ja      short loc_180022177
0x180022171  jnz     short loc_1800221AA
0x180022173  test    ebx, ebx
0x180022175  jz      short loc_1800221E8
0x180022177  mov     rax, [rbp+2230h+var_2250]
0x18002217b  mov     [rax], r12d
0x18002217e  xor     eax, eax
0x180022180  mov     rcx, [rbp+2230h+var_40]
0x180022187  xor     rcx, rsp; StackCookie
0x18002218a  call    __security_check_cookie
0x18002218f  mov     rbx, [rsp+2330h+arg_18]
0x180022197  add     rsp, 2300h
0x18002219e  pop     r15
0x1800221a0  pop     r14
0x1800221a2  pop     r13
0x1800221a4  pop     r12
0x1800221a6  pop     rdi
0x1800221a7  pop     rsi
0x1800221a8  pop     rbp
0x1800221a9  retn
0x1800221aa  mov     ecx, ebx
0x1800221ac  cmp     [rsi], r8d
0x1800221af  jnz     short loc_1800221D8
0x1800221b1  imul    rcx, 11h
0x1800221b5  mov     eax, [rbp+rcx+2230h+var_2240]
0x1800221b9  mov     dword ptr [rsp+2330h+var_22C0+4], eax
0x1800221bd  mov     eax, [rbp+rcx+2230h+var_223C]
0x1800221c1  mov     dword ptr [rsp+2330h+var_22C0+8], eax
0x1800221c5  mov     rax, [rbp+rcx+2230h+var_2238]
0x1800221ca  mov     qword ptr [rsp+2330h+var_22C0+0Ch], rax
0x1800221cf  mov     al, [rbp+rcx+2230h+var_2230]
0x1800221d3  mov     [rbp+2230h+var_22AC], al
0x1800221d6  jmp     short loc_1800221E8
0x1800221d8  mov     eax, [rbp+rbx*8+2230h+var_2240]
0x1800221dc  mov     dword ptr [rsp+2330h+var_22C0+4], eax
0x1800221e0  mov     eax, [rbp+rbx*8+2230h+var_223C]
0x1800221e4  mov     dword ptr [rsp+2330h+var_22C0+8], eax
0x1800221e8  xor     edi, edi
0x1800221ea  cmp     edi, r15d
0x1800221ed  ja      short loc_1800221F5
0x1800221ef  jnz     short loc_1800221FD
0x1800221f1  test    edi, edi
0x1800221f3  jz      short loc_180022248
0x1800221f5  add     ebx, r8d
0x1800221f8  jmp     loc_18002216C
0x1800221fd  mov     ecx, edi
0x1800221ff  cmp     [rsi], r8d
0x180022202  jnz     short loc_180022234
0x180022204  imul    rcx, 11h
0x180022208  mov     eax, [rbp+rcx+2230h+var_1140]
0x18002220f  mov     dword ptr [rbp+2230h+var_22A0+4], eax
0x180022212  mov     eax, [rbp+rcx+2230h+var_113C]
0x180022219  mov     dword ptr [rbp+2230h+var_22A0+8], eax
0x18002221c  mov     rax, [rbp+rcx+2230h+var_1138]
0x180022224  mov     qword ptr [rbp+2230h+var_22A0+0Ch], rax
0x180022228  mov     al, [rbp+rcx+2230h+var_1130]
0x18002222f  mov     [rbp+2230h+var_228C], al
0x180022232  jmp     short loc_180022248
0x180022234  mov     eax, [rbp+rdi*8+2230h+var_1140]
0x18002223b  mov     dword ptr [rbp+2230h+var_22A0+4], eax
0x18002223e  mov     eax, [rbp+rdi*8+2230h+var_113C]
0x180022245  mov     dword ptr [rbp+2230h+var_22A0+8], eax
0x180022248  mov     rcx, [rsi+18h]; pszSrc
0x18002224c  lea     rdx, [rsp+2330h+var_22D8]
0x180022251  call    CopyName
0x180022256  mov     r14d, eax
0x180022259  test    eax, eax
0x18002225b  jnz     loc_1800222E2
0x180022261  mov     rdx, [rsp+2330h+var_2300]
0x180022266  lea     r8d, [r14+1]
0x18002226a  movaps  xmm0, [rsp+2330h+var_22F0]
0x18002226f  movaps  xmm1, xmmword ptr [rsp+50h]
0x180022274  mov     eax, r12d
0x180022277  add     r12d, r8d
0x18002227a  imul    rcx, rax, 98h
0x180022281  mov     rax, qword ptr [rbp+2230h+var_2268+8]
0x180022285  add     edi, r8d
0x180022288  movups  xmmword ptr [rcx+rdx], xmm0
0x18002228c  movaps  xmm0, [rsp+2330h+var_22D0]
0x180022291  movups  xmmword ptr [rcx+rdx+10h], xmm1
0x180022296  movaps  xmm1, [rsp+2330h+var_22C0]
0x18002229b  movups  xmmword ptr [rcx+rdx+20h], xmm0
0x1800222a0  movaps  xmm0, xmmword ptr [rbp-80h]
0x1800222a4  movups  xmmword ptr [rcx+rdx+30h], xmm1
0x1800222a9  movaps  xmm1, [rbp+2230h+var_22A0]
0x1800222ad  movups  xmmword ptr [rcx+rdx+40h], xmm0
0x1800222b2  movaps  xmm0, xmmword ptr [rbp-60h]
0x1800222b6  movups  xmmword ptr [rcx+rdx+50h], xmm1
0x1800222bb  movaps  xmm1, [rbp+2230h+var_2280]
0x1800222bf  movups  xmmword ptr [rcx+rdx+60h], xmm0
0x1800222c4  movaps  xmm0, xmmword ptr [rbp-40h]
0x1800222c8  movups  xmmword ptr [rcx+rdx+70h], xmm1
0x1800222cd  movups  xmmword ptr [rcx+rdx+80h], xmm0
0x1800222d5  mov     [rcx+rdx+90h], rax
0x1800222dd  jmp     loc_1800221EA
0x1800222e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800222e9  lea     rax, WPP_GLOBAL_Control
0x1800222f0  cmp     rcx, rax
0x1800222f3  jz      short loc_180022313
0x1800222f5  test    byte ptr [rcx+1Ch], 10h
0x1800222f9  jz      short loc_180022313
0x1800222fb  mov     rcx, [rcx+10h]
0x1800222ff  lea     r8, WPP_7c0a21c92210358d3ee1e33826382c7b_Traceguids
0x180022306  mov     edx, 46h ; 'F'
0x18002230b  mov     r9d, r14d
0x18002230e  call    WPP_SF_d
0x180022313  xor     ebx, ebx
0x180022315  test    r12d, r12d
0x180022318  jz      short loc_18002233A
0x18002231a  mov     rsi, [rsp+2330h+var_2300]
0x18002231f  mov     eax, r12d
0x180022322  imul    rdi, rax, 98h
0x180022329  mov     rcx, [rdi+rsi+18h]
0x18002232e  call    SPDApiBufferFree
0x180022333  inc     ebx
0x180022335  cmp     ebx, r12d
0x180022338  jb      short loc_180022329
0x18002233a  mov     eax, r14d
0x18002233d  jmp     loc_180022180
```
