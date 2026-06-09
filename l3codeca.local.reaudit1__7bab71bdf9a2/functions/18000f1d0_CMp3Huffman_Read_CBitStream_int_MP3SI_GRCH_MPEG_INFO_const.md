# CMp3Huffman::Read(CBitStream &,int *,MP3SI_GRCH &,MPEG_INFO const &)

- ea: `0x18000f1d0`
- end: `0x18000f5b6`
- name: `?Read@CMp3Huffman@@QEAAXAEAVCBitStream@@PEAHAEAUMP3SI_GRCH@@AEBUMPEG_INFO@@@Z`
- size: `998`
- prototype: `void __usercall(CMp3Huffman *__hidden this@<rcx>, struct CBitStream *@<rdx>, int *@<r8>, struct MP3SI_GRCH *@<r9>, const struct MPEG_INFO *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180004910`

## callees

- `0x18000b870`
- `0x18000bad0`
- `0x18000f1d0`

## pseudocode

```c
void __fastcall CMp3Huffman::Read(
        CMp3Huffman *this,
        struct CBitStream *a2,
        int *a3,
        struct MP3SI_GRCH *a4,
        const struct MPEG_INFO *a5)
{
  const struct MPEG_INFO *v9; // rbp
  __int64 v10; // rax
  int v11; // edx
  int v12; // r8d
  __int64 v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rcx
  int v18; // ebx
  int v19; // edi
  int v20; // eax
  int v21; // eax
  int BigValues; // eax
  int Count1Area; // eax
  bool v24; // zf
  int v25; // r8d
  __int64 v26; // rax
  BOOL v27; // eax
  __int64 v28; // rdx
  int v29; // r10d
  int v30; // r9d
  int v31; // ecx
  int v32; // edx
  int v33; // r8d
  int v34; // r9d
  __int64 v35; // rcx
  char *v36; // r11
  __int64 v37; // rbx
  int v38; // r8d
  int v39; // ecx
  int v40; // r8d
  __int64 v41; // rcx
  int v42; // r8d
  int v43; // edx
  int v44; // eax
  int v45; // r8d
  __int64 v46; // rdx
  int v47[2]; // [rsp+30h] [rbp-38h] BYREF
  int v48; // [rsp+38h] [rbp-30h]

  if ( *((_DWORD *)a4 + 4) && *((_DWORD *)a4 + 5) == 2 )
  {
    v9 = a5;
    v10 = *((int *)a5 + 6);
    if ( *((_DWORD *)a4 + 6) )
    {
      v13 = *((int *)a5 + 1) + 3 * v10;
      if ( *((_BYTE *)a5 + 32) )
      {
        v14 = 37 * v13;
        v11 = 576;
        v12 = *((_DWORD *)&sfBandIndex + v14 + *((int *)a4 + 13) + 1);
      }
      else
      {
        v15 = 148 * v13;
        v11 = 576;
        v12 = *(_DWORD *)((char *)&sfBandIndex + v15 + 24)
            + 2 * (*(_DWORD *)((char *)&sfBandIndex + v15 + 108) - *(_DWORD *)((char *)&sfBandIndex + v15 + 104));
      }
    }
    else
    {
      v11 = 576;
      v12 = 3 * *((_DWORD *)&sfBandIndex + 111 * v10 + 37 * *((int *)a5 + 1) + (*((_DWORD *)a4 + 13) + 1) / 3 + 23);
    }
  }
  else
  {
    v9 = a5;
    v16 = 37 * (*((int *)a5 + 1) + 3LL * *((int *)a5 + 6));
    v17 = *((int *)a4 + 13);
    v12 = *((_DWORD *)&sfBandIndex + v16 + v17 + 1);
    v11 = *((_DWORD *)&sfBandIndex + v16 + (int)v17 + *((_DWORD *)a4 + 14) + 2);
  }
  v18 = *(_DWORD *)a4;
  v19 = *((_DWORD *)a4 + 17);
  v20 = 2 * *((_DWORD *)a4 + 1);
  v48 = v20;
  if ( v20 >= v12 )
    v20 = v12;
  v47[0] = v20;
  v21 = v48;
  if ( v48 >= v11 )
    v21 = v11;
  v47[1] = v21;
  BigValues = CHuffmanDecoder::ReadBigValues(this, a2, a3, (const int *)a4 + 7, v47);
  Count1Area = CHuffmanDecoder::ReadCount1Area(this, a2, a3, v19 + 32, BigValues, v18);
  v24 = *((_DWORD *)a4 + 4) == 0;
  v25 = Count1Area;
  *((_DWORD *)a4 + 19) = Count1Area;
  if ( v24 || *((_DWORD *)a4 + 5) != 2 )
  {
    *((_DWORD *)a4 + 20) = 1;
LABEL_47:
    v46 = 0;
    do
    {
      if ( v25 <= *((_DWORD *)&sfBandIndex + 111 * *((int *)v9 + 6) + 37 * *((int *)v9 + 1) + v46) )
        break;
      v46 = (unsigned int)(v46 + 1);
    }
    while ( (int)v46 < 22 );
    *((_DWORD *)a4 + 21) = v46;
    return;
  }
  if ( *((_DWORD *)a4 + 6) )
  {
    v26 = 28;
    if ( !*((_BYTE *)v9 + 32) )
      v26 = 20;
    v27 = v25 <= *(_DWORD *)((char *)&sfBandIndex + 444 * *((int *)v9 + 6) + 148 * *((int *)v9 + 1) + v26);
  }
  else
  {
    v27 = 0;
  }
  *((_DWORD *)a4 + 20) = v27;
  if ( v27 )
    goto LABEL_47;
  v28 = 0;
  do
  {
    if ( v25 <= 3 * dword_180017C2C[111 * *((int *)v9 + 6) + 37 * *((int *)v9 + 1) + v28] )
      break;
    v28 = (unsigned int)(v28 + 1);
  }
  while ( (int)v28 < 13 );
  *((_DWORD *)a4 + 22) = v28;
  v29 = v28 - 1;
  *((_DWORD *)a4 + 23) = v28;
  v30 = v28 - 1;
  *((_DWORD *)a4 + 24) = v28;
  *((_DWORD *)a4 + 25) = v28;
  if ( (int)v28 - 1 >= 0 )
  {
    while ( 1 )
    {
      v31 = *((_DWORD *)&sfBandIndex + 111 * *((int *)v9 + 6) + 37 * *((int *)v9 + 1) + v30 + 23);
      v32 = 3 * v31;
      v33 = 3 * v31 + *((_DWORD *)&sfBandIndex + 111 * *((int *)v9 + 6) + 37 * *((int *)v9 + 1) + v30 + 24) - v31;
      if ( 3 * v31 < v33 )
        break;
LABEL_28:
      if ( --v30 < 0 )
        goto LABEL_31;
    }
    while ( !a3[v32] )
    {
      if ( ++v32 >= v33 )
        goto LABEL_28;
    }
    *((_DWORD *)a4 + 23) = v30 + 1;
  }
LABEL_31:
  v34 = v29;
  if ( v29 >= 0 )
  {
    v35 = *((int *)v9 + 1) + 3LL * *((int *)v9 + 6);
    v36 = (char *)&sfBandIndex + 148 * v35;
    v37 = 37 * v35 + 1;
    while ( 1 )
    {
      v38 = *(_DWORD *)&v36[4 * v34 + 92];
      v39 = *((_DWORD *)&sfBandIndex + v37 + v34 + 23) + 2 * v38;
      v40 = v39 + *((_DWORD *)&sfBandIndex + v37 + v34 + 23) - v38;
      if ( v39 < v40 )
        break;
LABEL_36:
      if ( --v34 < 0 )
        goto LABEL_39;
    }
    while ( !a3[v39] )
    {
      if ( ++v39 >= v40 )
        goto LABEL_36;
    }
    *((_DWORD *)a4 + 24) = v34 + 1;
LABEL_39:
    v41 = *((int *)v9 + 1) + 3LL * *((int *)v9 + 6);
    while ( 1 )
    {
      v42 = *((_DWORD *)&sfBandIndex + 37 * v41 + v29 + 23);
      v43 = *((_DWORD *)&sfBandIndex + 37 * v41 + v29 + 24) - v42;
      v44 = 3 * v42 + 2 * v43;
      v45 = v43 + v44;
      if ( v44 < v43 + v44 )
        break;
LABEL_43:
      if ( --v29 < 0 )
        return;
    }
    while ( !a3[v44] )
    {
      if ( ++v44 >= v45 )
        goto LABEL_43;
    }
    *((_DWORD *)a4 + 25) = v29 + 1;
  }
}

```

## disassembly

```asm
0x18000f1d0  mov     rax, rsp
0x18000f1d3  mov     [rax+20h], rbx
0x18000f1d7  mov     [rax+8], rcx
0x18000f1db  push    rbp
0x18000f1dc  push    rsi
0x18000f1dd  push    r12
0x18000f1df  push    r14
0x18000f1e1  push    r15
0x18000f1e3  sub     rsp, 40h
0x18000f1e7  cmp     dword ptr [r9+10h], 0
0x18000f1ec  mov     r14, r9
0x18000f1ef  mov     [rax+10h], rdi
0x18000f1f3  mov     rsi, r8
0x18000f1f6  mov     [rax+18h], r13
0x18000f1fa  mov     r10, rcx
0x18000f1fd  mov     r13, rdx
0x18000f200  jz      loc_18000F2AF
0x18000f206  cmp     dword ptr [r9+14h], 2
0x18000f20b  jnz     loc_18000F2AF
0x18000f211  cmp     dword ptr [r9+18h], 0
0x18000f216  lea     r15, ?sfBandIndex@@3QAY02$$CBU_unnamed_type_SF_BAND_INDEX_@@A; _unnamed_type_SF_BAND_INDEX_ const (near * sfBandIndex)[3]
0x18000f21d  mov     rbp, [rsp+68h+arg_20]
0x18000f225  movsxd  rax, dword ptr [rbp+18h]
0x18000f229  jnz     short loc_18000F266
0x18000f22b  lea     rcx, [rax+rax*2]
0x18000f22f  movsxd  rax, dword ptr [rbp+4]
0x18000f233  add     rcx, rax
0x18000f236  mov     eax, 55555556h
0x18000f23b  imul    r8, rcx, 25h ; '%'
0x18000f23f  mov     ecx, [r9+34h]
0x18000f243  inc     ecx
0x18000f245  imul    ecx
0x18000f247  mov     eax, edx
0x18000f249  shr     eax, 1Fh
0x18000f24c  add     eax, edx
0x18000f24e  mov     edx, 240h
0x18000f253  cdqe
0x18000f255  add     r8, rax
0x18000f258  mov     eax, [r15+r8*4+5Ch]
0x18000f25d  lea     r8d, [rax+rax*2]
0x18000f261  jmp     loc_18000F2EF
0x18000f266  lea     rdx, [rax+rax*2]
0x18000f26a  movsxd  rax, dword ptr [rbp+4]
0x18000f26e  add     rdx, rax
0x18000f271  cmp     byte ptr [rbp+20h], 0
0x18000f275  jz      short loc_18000F28E
0x18000f277  movsxd  rcx, dword ptr [r9+34h]
0x18000f27b  imul    rax, rdx, 25h ; '%'
0x18000f27f  mov     edx, 240h
0x18000f284  add     rcx, rax
0x18000f287  mov     r8d, [r15+rcx*4+4]
0x18000f28c  jmp     short loc_18000F2EF
0x18000f28e  imul    rax, rdx, 94h
0x18000f295  mov     edx, 240h
0x18000f29a  mov     ecx, [rax+r15+6Ch]
0x18000f29f  sub     ecx, [rax+r15+68h]
0x18000f2a4  mov     eax, [rax+r15+18h]
0x18000f2a9  lea     r8d, [rax+rcx*2]
0x18000f2ad  jmp     short loc_18000F2EF
0x18000f2af  mov     rbp, [rsp+68h+arg_20]
0x18000f2b7  lea     r15, ?sfBandIndex@@3QAY02$$CBU_unnamed_type_SF_BAND_INDEX_@@A; _unnamed_type_SF_BAND_INDEX_ const (near * sfBandIndex)[3]
0x18000f2be  movsxd  rax, dword ptr [rbp+18h]
0x18000f2c2  lea     rcx, [rax+rax*2]
0x18000f2c6  movsxd  rax, dword ptr [rbp+4]
0x18000f2ca  add     rcx, rax
0x18000f2cd  imul    rdx, rcx, 25h ; '%'
0x18000f2d1  movsxd  rcx, dword ptr [r9+34h]
0x18000f2d5  lea     rax, [rdx+rcx]
0x18000f2d9  mov     r8d, [r15+rax*4+4]
0x18000f2de  mov     eax, [r9+38h]
0x18000f2e2  add     eax, ecx
0x18000f2e4  movsxd  rcx, eax
0x18000f2e7  add     rcx, rdx
0x18000f2ea  mov     edx, [r15+rcx*4+8]
0x18000f2ef  mov     ecx, [r9+4]
0x18000f2f3  mov     ebx, [r9]
0x18000f2f6  add     ecx, ecx
0x18000f2f8  mov     edi, [r9+44h]
0x18000f2fc  cmp     ecx, r8d
0x18000f2ff  mov     eax, ecx
0x18000f301  mov     [rsp+68h+var_30], ecx
0x18000f305  cmovge  eax, r8d
0x18000f309  cmp     ecx, edx
0x18000f30b  mov     [rsp+68h+var_38], eax
0x18000f30f  mov     r8, rsi; int *
0x18000f312  mov     eax, ecx
0x18000f314  mov     rcx, r10; this
0x18000f317  cmovge  eax, edx
0x18000f31a  add     r9, 1Ch; int *
0x18000f31e  mov     [rsp+68h+var_34], eax
0x18000f322  mov     rdx, r13; struct CBitStream *
0x18000f325  lea     rax, [rsp+68h+var_38]
0x18000f32a  mov     [rsp+68h+var_48], rax; int *
0x18000f32f  call    ?ReadBigValues@CHuffmanDecoder@@AEAAHAEAVCBitStream@@PEAHPEBH2@Z; CHuffmanDecoder::ReadBigValues(CBitStream &,int *,int const *,int const *)
0x18000f334  mov     rcx, [rsp+68h+arg_0]; this
0x18000f339  lea     r9d, [rdi+20h]; int
0x18000f33d  mov     r8, rsi; int *
0x18000f340  mov     [rsp+68h+var_40], ebx; int
0x18000f344  mov     rdx, r13; struct CBitStream *
0x18000f347  mov     dword ptr [rsp+68h+var_48], eax; int
0x18000f34b  call    ?ReadCount1Area@CHuffmanDecoder@@AEAAHAEAVCBitStream@@PEAHHHH@Z; CHuffmanDecoder::ReadCount1Area(CBitStream &,int *,int,int,int)
0x18000f350  cmp     dword ptr [r14+10h], 0
0x18000f355  mov     r8d, eax
0x18000f358  mov     r13, [rsp+68h+arg_10]
0x18000f360  mov     rdi, [rsp+68h+arg_8]
0x18000f365  mov     [r14+4Ch], eax
0x18000f369  jz      loc_18000F566
0x18000f36f  cmp     dword ptr [r14+14h], 2
0x18000f374  jnz     loc_18000F566
0x18000f37a  cmp     dword ptr [r14+18h], 0
0x18000f37f  jz      short loc_18000F3B6
0x18000f381  movsxd  rcx, dword ptr [rbp+18h]
0x18000f385  movsxd  rax, dword ptr [rbp+4]
0x18000f389  lea     rdx, [rcx+rcx*2]
0x18000f38d  add     rdx, rax
0x18000f390  mov     eax, 1Ch
0x18000f395  imul    rcx, rdx, 94h
0x18000f39c  cmp     byte ptr [rbp+20h], 0
0x18000f3a0  mov     edx, 14h
0x18000f3a5  cmovz   eax, edx
0x18000f3a8  add     rcx, rax
0x18000f3ab  xor     eax, eax
0x18000f3ad  cmp     r8d, [rcx+r15]
0x18000f3b1  setle   al
0x18000f3b4  jmp     short loc_18000F3B8
0x18000f3b6  xor     eax, eax
0x18000f3b8  mov     [r14+50h], eax
0x18000f3bc  test    eax, eax
0x18000f3be  jnz     loc_18000F56E
0x18000f3c4  movsxd  rax, dword ptr [rbp+18h]
0x18000f3c8  xor     edx, edx
0x18000f3ca  lea     rcx, [rax+rax*2]
0x18000f3ce  movsxd  rax, dword ptr [rbp+4]
0x18000f3d2  add     rcx, rax
0x18000f3d5  lea     rax, dword_180017C2C
0x18000f3dc  imul    r9, rcx, 94h
0x18000f3e3  add     r9, rax
0x18000f3e6  nop     word ptr [rax+rax+00000000h]
0x18000f3f0  mov     ecx, [r9+rdx*4]
0x18000f3f4  lea     eax, [rcx+rcx*2]
0x18000f3f7  cmp     r8d, eax
0x18000f3fa  jle     short loc_18000F403
0x18000f3fc  inc     edx
0x18000f3fe  cmp     edx, 0Dh
0x18000f401  jl      short loc_18000F3F0
0x18000f403  mov     [r14+58h], edx
0x18000f407  lea     r10d, [rdx-1]
0x18000f40b  mov     [r14+5Ch], edx
0x18000f40f  mov     r9d, r10d
0x18000f412  mov     [r14+60h], edx
0x18000f416  mov     [r14+64h], edx
0x18000f41a  test    r10d, r10d
0x18000f41d  js      short loc_18000F480
0x18000f41f  movsxd  rax, dword ptr [rbp+18h]
0x18000f423  lea     rcx, [rax+rax*2]
0x18000f427  movsxd  rax, dword ptr [rbp+4]
0x18000f42b  add     rcx, rax
0x18000f42e  imul    rax, rcx, 94h
0x18000f435  lea     r11, [rax+r15]
0x18000f439  lea     rbx, [rax+r15]
0x18000f43d  nop     dword ptr [rax]
0x18000f440  movsxd  rax, r9d
0x18000f443  mov     ecx, [r11+rax*4+5Ch]
0x18000f448  mov     r8d, [rbx+rax*4+60h]
0x18000f44d  sub     r8d, ecx
0x18000f450  lea     edx, [rcx+rcx*2]
0x18000f453  add     r8d, edx
0x18000f456  cmp     edx, r8d
0x18000f459  jge     short loc_18000F470
0x18000f45b  nop     dword ptr [rax+rax+00h]
0x18000f460  movsxd  rax, edx
0x18000f463  cmp     dword ptr [rsi+rax*4], 0
0x18000f467  jnz     short loc_18000F478
0x18000f469  inc     edx
0x18000f46b  cmp     edx, r8d
0x18000f46e  jl      short loc_18000F460
0x18000f470  sub     r9d, 1
0x18000f474  jns     short loc_18000F440
0x18000f476  jmp     short loc_18000F480
0x18000f478  lea     eax, [r9+1]
0x18000f47c  mov     [r14+5Ch], eax
0x18000f480  mov     r9d, r10d
0x18000f483  test    r10d, r10d
0x18000f486  js      loc_18000F5A1
0x18000f48c  movsxd  rax, dword ptr [rbp+18h]
0x18000f490  lea     rcx, [rax+rax*2]
0x18000f494  movsxd  rax, dword ptr [rbp+4]
0x18000f498  add     rcx, rax
0x18000f49b  imul    rax, rcx, 25h ; '%'
0x18000f49f  lea     r11, [r15+rax*4]
0x18000f4a3  lea     rbx, [rax+1]
0x18000f4a7  nop     word ptr [rax+rax+00000000h]
0x18000f4b0  movsxd  rax, r9d
0x18000f4b3  mov     r8d, [r11+rax*4+5Ch]
0x18000f4b8  lea     rcx, [rbx+rax]
0x18000f4bc  mov     edx, [r15+rcx*4+5Ch]
0x18000f4c1  sub     edx, r8d
0x18000f4c4  lea     ecx, [rdx+r8*2]
0x18000f4c8  add     ecx, r8d
0x18000f4cb  lea     r8d, [rcx+rdx]
0x18000f4cf  cmp     ecx, r8d
0x18000f4d2  jge     short loc_18000F4E4
0x18000f4d4  movsxd  rax, ecx
0x18000f4d7  cmp     dword ptr [rsi+rax*4], 0
0x18000f4db  jnz     short loc_18000F4EC
0x18000f4dd  inc     ecx
0x18000f4df  cmp     ecx, r8d
0x18000f4e2  jl      short loc_18000F4D4
0x18000f4e4  sub     r9d, 1
0x18000f4e8  jns     short loc_18000F4B0
0x18000f4ea  jmp     short loc_18000F4F4
0x18000f4ec  lea     eax, [r9+1]
0x18000f4f0  mov     [r14+60h], eax
0x18000f4f4  test    r10d, r10d
0x18000f4f7  js      loc_18000F5A1
0x18000f4fd  movsxd  rax, dword ptr [rbp+18h]
0x18000f501  lea     rcx, [rax+rax*2]
0x18000f505  movsxd  rax, dword ptr [rbp+4]
0x18000f509  add     rcx, rax
0x18000f50c  imul    rax, rcx, 25h ; '%'
0x18000f510  lea     r9, [r15+rax*4]
0x18000f514  lea     r11, [rax+1]
0x18000f518  nop     dword ptr [rax+rax+00000000h]
0x18000f520  movsxd  rax, r10d
0x18000f523  mov     r8d, [r9+rax*4+5Ch]
0x18000f528  lea     rcx, [r11+rax]
0x18000f52c  mov     edx, [r15+rcx*4+5Ch]
0x18000f531  sub     edx, r8d
0x18000f534  lea     eax, [r8+r8*2]
0x18000f538  lea     eax, [rax+rdx*2]
0x18000f53b  lea     r8d, [rdx+rax]
0x18000f53f  cmp     eax, r8d
0x18000f542  jge     short loc_18000F554
0x18000f544  movsxd  rcx, eax
0x18000f547  cmp     dword ptr [rsi+rcx*4], 0
0x18000f54b  jnz     short loc_18000F55C
0x18000f54d  inc     eax
0x18000f54f  cmp     eax, r8d
0x18000f552  jl      short loc_18000F544
0x18000f554  sub     r10d, 1
0x18000f558  jns     short loc_18000F520
0x18000f55a  jmp     short loc_18000F5A1
0x18000f55c  lea     eax, [r10+1]
0x18000f560  mov     [r14+64h], eax
0x18000f564  jmp     short loc_18000F5A1
0x18000f566  mov     dword ptr [r14+50h], 1
0x18000f56e  movsxd  rax, dword ptr [rbp+18h]
0x18000f572  xor     edx, edx
0x18000f574  lea     rcx, [rax+rax*2]
0x18000f578  movsxd  rax, dword ptr [rbp+4]
0x18000f57c  add     rcx, rax
0x18000f57f  imul    r9, rcx, 94h
0x18000f586  add     r9, r15
0x18000f589  nop     dword ptr [rax+00000000h]
0x18000f590  cmp     r8d, [r9+rdx*4]
0x18000f594  jle     short loc_18000F59D
0x18000f596  inc     edx
0x18000f598  cmp     edx, 16h
0x18000f59b  jl      short loc_18000F590
0x18000f59d  mov     [r14+54h], edx
0x18000f5a1  mov     rbx, [rsp+68h+arg_18]
0x18000f5a9  add     rsp, 40h
0x18000f5ad  pop     r15
0x18000f5af  pop     r14
0x18000f5b1  pop     r12
0x18000f5b3  pop     rsi
0x18000f5b4  pop     rbp
0x18000f5b5  retn
```
