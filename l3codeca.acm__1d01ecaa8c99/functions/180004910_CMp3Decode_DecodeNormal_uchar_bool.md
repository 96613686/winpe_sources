# CMp3Decode::DecodeNormal(uchar *,bool)

- ea: `0x180004910`
- end: `0x180004d8f`
- name: `?DecodeNormal@CMp3Decode@@IEAA?AW4SSC@@PEAE_N@Z`
- size: `1151`
- prototype: `__int64 __fastcall(__int64, __int16 *, char)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x1800045d0`

## callees

- `0x180001cd4`
- `0x180004910`
- `0x180005110`
- `0x180005be0`
- `0x1800078d0`
- `0x18000ce70`
- `0x18000d090`
- `0x18000d370`
- `0x18000d660`
- `0x18000d850`
- `0x18000da70`
- `0x18000de50`
- `0x18000f1d0`
- `0x18000f870`

## pseudocode

```c
__int64 __fastcall CMp3Decode::DecodeNormal(__int64 a1, __int16 *a2, char a3)
{
  char v3; // di
  int v5; // edx
  int v6; // r14d
  struct MP3SI_GRCH *v7; // rax
  struct CBitStream *v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rdi
  __int64 v11; // rbp
  int v12; // r15d
  __int64 v13; // rbx
  int v14; // r12d
  __int64 v15; // rdi
  __int64 v16; // rbx
  __int64 v17; // rcx
  __int64 v18; // rbp
  __int64 v19; // rbx
  __int64 v20; // r14
  int v21; // r15d
  __int64 v22; // r12
  __int64 v23; // rdi
  float *v24; // rbx
  __int64 v25; // r9
  int v26; // r11d
  _DWORD *v27; // rbp
  int v28; // r8d
  int v29; // r10d
  int v30; // r9d
  int v31; // r9d
  int v32; // r10d
  __int16 *v33; // rax
  struct MP3SCF *v35; // [rsp+20h] [rbp-88h]
  int v36; // [rsp+40h] [rbp-68h]
  int v37; // [rsp+48h] [rbp-60h]
  struct MP3SI_GRCH *v38; // [rsp+50h] [rbp-58h]
  struct MP3SI_GRCH *v39; // [rsp+50h] [rbp-58h]
  __int64 v40; // [rsp+58h] [rbp-50h]
  __int64 v41; // [rsp+B0h] [rbp+8h]
  char v42; // [rsp+B0h] [rbp+8h]
  int v45; // [rsp+C8h] [rbp+20h]

  v3 = a3;
  if ( *(_DWORD *)(a1 + 41200) )
    v36 = 1;
  else
    v36 = *(_DWORD *)(*(_QWORD *)(a1 + 30352) + 136LL);
  v5 = 0;
  while ( 1 )
  {
    v45 = v5;
    if ( v5 >= (*(_BYTE *)(a1 + 30344) != 0) + 1 )
      return 0;
    v6 = 0;
    v7 = (struct MP3SI_GRCH *)v5;
    v38 = (struct MP3SI_GRCH *)v5;
    if ( *(int *)(a1 + 30312) > 0 )
    {
      v8 = (struct CBitStream *)(a1 + 30360);
      v41 = 108LL * v5;
      v9 = a1 + v41 + 30448;
      do
      {
        v10 = 232LL * v6;
        v11 = v9 + v10;
        v12 = a1 + 392 * v6 + 30896;
        mp3ScaleFactorRead(
          v8,
          (struct MP3SI_GRCH *)(v9 + v10),
          (struct MP3SCF *)(a1 + 392LL * v6 + 30896),
          (const struct MPEG_INFO *)(a1 + 30312),
          (const int *)(v10 + a1 + 30432),
          v5,
          v6);
        v13 = 2304LL * v6;
        v14 = v13 + a1 + 31680;
        CMp3Huffman::Read(
          (CMp3Huffman *)a1,
          (struct CBitStream *)(a1 + 30360),
          (int *)(v13 + a1 + 31680),
          (struct MP3SI_GRCH *)v11,
          (const struct MPEG_INFO *)(a1 + 30312));
        v15 = v41 + v10;
        v16 = a1 + v13 + 36288;
        if ( *(_DWORD *)(v11 + 16) && *(_DWORD *)(v11 + 20) == 2 )
        {
          v35 = (struct MP3SCF *)(a1 + 30312);
          if ( *(_DWORD *)(v11 + 24) )
            III_deq_mixed(v14, v16, v11, v12, (__int64)v35);
          else
            III_deq_short(v14, v16, v11, v12, (__int64)v35);
        }
        else
        {
          III_deq_long(v14, v16, v11, v12, a1 + 30312);
        }
        v17 = *(int *)(a1 + v15 + 30524);
        if ( (int)v17 < 576 )
          memset_0((void *)(v16 + 4 * v17), 0, 4LL * (576 - (int)v17));
        v9 = a1 + v41 + 30448;
        v8 = (struct CBitStream *)(a1 + 30360);
        v5 = v45;
        ++v6;
      }
      while ( v6 < *(_DWORD *)(a1 + 30312) );
      v7 = v38;
      v3 = a3;
    }
    v18 = 108LL * (_QWORD)v7;
    v19 = a1 + 36288;
    v20 = a1 + 108LL * (_QWORD)v7;
    v40 = 108LL * (_QWORD)v7;
    mp3StereoProcessing(
      (float *)(a1 + 36288),
      (float *)(a1 + 38592),
      (struct MP3SI_GRCH *)(v20 + 30448),
      (struct MP3SI_GRCH *)(v20 + 30680),
      (const struct MP3SCF *)(a1 + 31288),
      (const struct MPEG_INFO *)(a1 + 30312),
      *(_DWORD *)(a1 + 41200));
    v21 = 0;
    if ( v36 > 0 )
    {
      v42 = v3 ^ 1;
      v22 = 0;
      do
      {
        v23 = 232 * v22;
        v24 = (float *)(2304 * v22 + v19);
        v39 = (struct MP3SI_GRCH *)(232 * v22 + v18 + a1 + 30448);
        mp3Reorder(v24, v39, (const struct MPEG_INFO *)(a1 + 30312));
        v25 = v20 + 232 * v22;
        v37 = *(_DWORD *)(a1 + 41192);
        v26 = *(_DWORD *)(a1 + v18 + 232 * v22 + 30464);
        if ( v26 && *(_DWORD *)(v25 + 30468) == 2 )
        {
          v27 = (_DWORD *)(a1 + 30336);
          v28 = 3
              * dword_180017C2C[111 * *(int *)(a1 + 30336) + 37 * *(int *)(a1 + 30316) + *(int *)(v20 + v23 + 30536)];
          v29 = (v28 != 18 * (v28 / 18)) + v28 / 18;
          *(_DWORD *)(v20 + v23 + 30552) = v29;
        }
        else
        {
          v27 = (_DWORD *)(a1 + 30336);
          v29 = (*(_DWORD *)(v20 + v23 + 30524) != 18 * (*(_DWORD *)(v20 + v23 + 30524) / 18))
              + *(_DWORD *)(v20 + v23 + 30524) / 18;
          *(_DWORD *)(v20 + v23 + 30552) = v29;
          if ( !v26 )
            goto LABEL_32;
        }
        if ( *(_DWORD *)(v25 + 30468) == 2 && !*(_DWORD *)(v20 + v23 + 30472) )
          goto LABEL_36;
        if ( !*(_DWORD *)(v20 + v23 + 30472) || *(_DWORD *)(v25 + 30468) != 2 )
        {
LABEL_32:
          if ( (32 >> v37) - 1 < v29 )
            v29 = (32 >> v37) - 1;
          goto LABEL_34;
        }
        if ( *v27 == 2 && *(_DWORD *)(a1 + 30316) == 2 )
        {
          v30 = 0;
          do
          {
LABEL_35:
            antialias_sb(&v24[18 * v30], &v24[18 * v30 + 18]);
            v30 = v31 + 1;
          }
          while ( v30 < v32 );
          goto LABEL_36;
        }
        v29 = 1;
LABEL_34:
        v30 = 0;
        if ( v29 > 0 )
          goto LABEL_35;
LABEL_36:
        CErrorConcealment::Apply(
          (CErrorConcealment *)(a1 + 4976),
          v42,
          (const struct MPEG_INFO *)(a1 + 30312),
          (struct MP3SI *)(a1 + 30424),
          v24,
          v45,
          v21);
        v19 = a1 + 36288;
        CMdct::Apply((CMdct *)(a1 + 80), v21, v39, (float (*)[2][32][18])(a1 + 36288));
        v18 = v40;
        ++v21;
        ++v22;
      }
      while ( v21 < v36 );
    }
    CMp3Decode::PolyphaseReorder((CMp3Decode *)a1);
    v33 = CPolyphase::Apply((CPolyphase *)(a1 + 4920), (float *(*)[2][18])(a1 + 40896), a2);
    v3 = a3;
    v5 = v45 + 1;
    a2 = v33;
  }
}

```

## disassembly

```asm
0x180004910  mov     [rsp+arg_10], r8b
0x180004915  mov     [rsp+arg_8], rdx
0x18000491a  push    rbx
0x18000491b  push    rbp
0x18000491c  push    rsi
0x18000491d  push    rdi
0x18000491e  push    r12
0x180004920  push    r13
0x180004922  push    r14
0x180004924  push    r15
0x180004926  sub     rsp, 68h
0x18000492a  cmp     dword ptr [rcx+0A0F0h], 0
0x180004931  movzx   edi, r8b
0x180004935  mov     rsi, rcx
0x180004938  jz      short loc_180004944
0x18000493a  mov     [rsp+0A8h+var_68], 1
0x180004942  jmp     short loc_180004955
0x180004944  mov     rax, [rcx+7690h]
0x18000494b  mov     eax, [rax+88h]
0x180004951  mov     [rsp+0A8h+var_68], eax
0x180004955  xor     edx, edx
0x180004957  xor     eax, eax
0x180004959  mov     [rsp+0A8h+arg_18], edx
0x180004960  cmp     [rsi+7688h], al
0x180004966  setnz   al
0x180004969  inc     eax
0x18000496b  cmp     edx, eax
0x18000496d  jge     loc_180004D7C
0x180004973  xor     r14d, r14d
0x180004976  movsxd  rax, edx
0x180004979  lea     r13, [rsi+7668h]
0x180004980  mov     [rsp+0A8h+var_58], rax
0x180004985  cmp     [r13+0], r14d
0x180004989  jle     loc_180004AD0
0x18000498f  imul    rax, 6Ch ; 'l'
0x180004993  lea     rcx, [rsi+7698h]; this
0x18000499a  mov     [rsp+0A8h+arg_0], rax
0x1800049a2  add     rax, 76F0h
0x1800049a8  add     rax, rsi
0x1800049ab  mov     [rsp+0A8h+var_60], rax
0x1800049b0  movsxd  rbx, r14d
0x1800049b3  mov     r9, r13; struct MPEG_INFO *
0x1800049b6  imul    rdi, rbx, 0E8h
0x1800049bd  imul    r15, rbx, 188h
0x1800049c4  lea     rbp, [rax+rdi]
0x1800049c8  mov     [rsp+0A8h+var_78], r14d; int
0x1800049cd  mov     dword ptr [rsp+0A8h+var_80], edx; int
0x1800049d1  lea     rax, [rsi+76E0h]
0x1800049d8  add     rax, rdi
0x1800049db  mov     rdx, rbp; struct MP3SI_GRCH *
0x1800049de  mov     [rsp+0A8h+var_88], rax; int *
0x1800049e3  add     r15, 78B0h
0x1800049ea  add     r15, rsi
0x1800049ed  mov     r8, r15; struct MP3SCF *
0x1800049f0  call    ?mp3ScaleFactorRead@@YAXAEAVCBitStream@@AEAUMP3SI_GRCH@@AEAUMP3SCF@@AEBUMPEG_INFO@@PEBHHH@Z; mp3ScaleFactorRead(CBitStream &,MP3SI_GRCH &,MP3SCF &,MPEG_INFO const &,int const *,int,int)
0x1800049f5  lea     rbx, [rbx+rbx*8]
0x1800049f9  mov     [rsp+0A8h+var_88], r13; struct MPEG_INFO *
0x1800049fe  shl     rbx, 8
0x180004a02  lea     r12, [rsi+7BC0h]
0x180004a09  add     r12, rbx
0x180004a0c  lea     rdx, [rsi+7698h]; struct CBitStream *
0x180004a13  mov     r8, r12; int *
0x180004a16  mov     r9, rbp; struct MP3SI_GRCH *
0x180004a19  mov     rcx, rsi; this
0x180004a1c  call    ?Read@CMp3Huffman@@QEAAXAEAVCBitStream@@PEAHAEAUMP3SI_GRCH@@AEBUMPEG_INFO@@@Z; CMp3Huffman::Read(CBitStream &,int *,MP3SI_GRCH &,MPEG_INFO const &)
0x180004a21  add     rdi, [rsp+0A8h+arg_0]
0x180004a29  add     rbx, 8DC0h
0x180004a30  add     rbx, rsi
0x180004a33  cmp     dword ptr [rbp+10h], 0
0x180004a37  jz      short loc_180004A64
0x180004a39  cmp     dword ptr [rbp+14h], 2
0x180004a3d  jnz     short loc_180004A64
0x180004a3f  cmp     dword ptr [rbp+18h], 0
0x180004a43  mov     r9, r15
0x180004a46  mov     [rsp+0A8h+var_88], r13
0x180004a4b  mov     r8, rbp
0x180004a4e  mov     rdx, rbx
0x180004a51  mov     rcx, r12
0x180004a54  jz      short loc_180004A5D
0x180004a56  call    III_deq_mixed
0x180004a5b  jmp     short loc_180004A7A
0x180004a5d  call    III_deq_short
0x180004a62  jmp     short loc_180004A7A
0x180004a64  mov     r9, r15
0x180004a67  mov     [rsp+0A8h+var_88], r13
0x180004a6c  mov     r8, rbp
0x180004a6f  mov     rdx, rbx
0x180004a72  mov     rcx, r12
0x180004a75  call    III_deq_long
0x180004a7a  movsxd  rcx, dword ptr [rsi+rdi+773Ch]
0x180004a82  cmp     ecx, 240h
0x180004a88  jge     short loc_180004AA3
0x180004a8a  mov     eax, 240h
0x180004a8f  xor     edx, edx; Val
0x180004a91  sub     eax, ecx
0x180004a93  lea     rcx, [rbx+rcx*4]; void *
0x180004a97  movsxd  r8, eax
0x180004a9a  shl     r8, 2; Size
0x180004a9e  call    memset_0
0x180004aa3  mov     rax, [rsp+0A8h+var_60]
0x180004aa8  lea     rcx, [rsi+7698h]
0x180004aaf  mov     edx, [rsp+0A8h+arg_18]
0x180004ab6  inc     r14d
0x180004ab9  cmp     r14d, [r13+0]
0x180004abd  jl      loc_1800049B0
0x180004ac3  mov     rax, [rsp+0A8h+var_58]
0x180004ac8  movzx   edi, [rsp+0A8h+arg_10]
0x180004ad0  imul    rbp, rax, 6Ch ; 'l'
0x180004ad4  mov     eax, [rsi+0A0F0h]
0x180004ada  lea     rcx, [rsi+7A38h]
0x180004ae1  mov     [rsp+0A8h+var_78], eax; int
0x180004ae5  lea     rbx, [rsi+8DC0h]
0x180004aec  mov     [rsp+0A8h+var_80], r13; struct MPEG_INFO *
0x180004af1  lea     rdx, [rsi+96C0h]; float *
0x180004af8  mov     [rsp+0A8h+var_88], rcx; struct MP3SCF *
0x180004afd  mov     rcx, rbx; float *
0x180004b00  lea     r14, [rsi+rbp]
0x180004b04  mov     [rsp+0A8h+var_50], rbp
0x180004b09  lea     r9, [r14+77D8h]; struct MP3SI_GRCH *
0x180004b10  lea     r8, [r14+76F0h]; struct MP3SI_GRCH *
0x180004b17  call    ?mp3StereoProcessing@@YAXPEAM0AEAUMP3SI_GRCH@@1AEBUMP3SCF@@AEBUMPEG_INFO@@H@Z; mp3StereoProcessing(float *,float *,MP3SI_GRCH &,MP3SI_GRCH &,MP3SCF const &,MPEG_INFO const &,int)
0x180004b1c  xor     r15d, r15d
0x180004b1f  cmp     [rsp+0A8h+var_68], r15d
0x180004b24  jle     loc_180004D3B
0x180004b2a  movzx   eax, dil
0x180004b2e  xor     al, 1
0x180004b30  mov     byte ptr [rsp+0A8h+arg_0], al
0x180004b37  xor     r12d, r12d
0x180004b3a  nop     word ptr [rax+rax+00h]
0x180004b40  imul    rdi, r12, 0E8h
0x180004b47  lea     rcx, [rsi+76F0h]
0x180004b4e  mov     r8, r13; struct MPEG_INFO *
0x180004b51  add     rcx, rbp
0x180004b54  lea     rax, [r12+r12*8]
0x180004b58  add     rcx, rdi
0x180004b5b  shl     rax, 8
0x180004b5f  add     rbx, rax
0x180004b62  mov     [rsp+0A8h+var_58], rcx
0x180004b67  mov     rdx, rcx; struct MP3SI_GRCH *
0x180004b6a  mov     rcx, rbx; float *
0x180004b6d  call    ?mp3Reorder@@YAXPEAMAEBUMP3SI_GRCH@@AEBUMPEG_INFO@@@Z; mp3Reorder(float *,MP3SI_GRCH const &,MPEG_INFO const &)
0x180004b72  mov     eax, [rsi+0A0E8h]
0x180004b78  lea     r9, [r14+rdi]
0x180004b7c  mov     dword ptr [rsp+0A8h+var_60], eax
0x180004b80  lea     rax, [rsi+rbp]
0x180004b84  mov     r11d, [rax+rdi+7700h]
0x180004b8c  test    r11d, r11d
0x180004b8f  jz      short loc_180004BFE
0x180004b91  cmp     dword ptr [r9+7704h], 2
0x180004b99  jnz     short loc_180004BFE
0x180004b9b  movsxd  rdx, dword ptr [rsi+766Ch]
0x180004ba2  lea     rbp, [rsi+7680h]
0x180004ba9  movsxd  rax, dword ptr [rbp+0]
0x180004bad  lea     rcx, [rax+rax*2]
0x180004bb1  movsxd  rax, dword ptr [r14+rdi+7748h]
0x180004bb9  add     rdx, rcx
0x180004bbc  imul    rcx, rdx, 25h ; '%'
0x180004bc0  add     rcx, rax
0x180004bc3  lea     rax, dword_180017C2C
0x180004bca  mov     eax, [rax+rcx*4]
0x180004bcd  xor     ecx, ecx
0x180004bcf  lea     r8d, [rax+rax*2]
0x180004bd3  mov     eax, 38E38E39h
0x180004bd8  imul    r8d
0x180004bdb  sar     edx, 2
0x180004bde  mov     eax, edx
0x180004be0  shr     eax, 1Fh
0x180004be3  add     edx, eax
0x180004be5  lea     eax, [rdx+rdx*8]
0x180004be8  add     eax, eax
0x180004bea  cmp     r8d, eax
0x180004bed  setnz   cl
0x180004bf0  lea     r10d, [rcx+rdx]
0x180004bf4  mov     [r14+rdi+7758h], r10d
0x180004bfc  jmp     short loc_180004C3D
0x180004bfe  mov     r8d, [r14+rdi+773Ch]
0x180004c06  lea     rbp, [rsi+7680h]
0x180004c0d  xor     ecx, ecx
0x180004c0f  mov     eax, 38E38E39h
0x180004c14  imul    r8d
0x180004c17  sar     edx, 2
0x180004c1a  mov     eax, edx
0x180004c1c  shr     eax, 1Fh
0x180004c1f  add     edx, eax
0x180004c21  lea     eax, [rdx+rdx*8]
0x180004c24  add     eax, eax
0x180004c26  cmp     r8d, eax
0x180004c29  setnz   cl
0x180004c2c  lea     r10d, [rcx+rdx]
0x180004c30  mov     [r14+rdi+7758h], r10d
0x180004c38  test    r11d, r11d
0x180004c3b  jz      short loc_180004C92
0x180004c3d  cmp     dword ptr [r9+7704h], 2
0x180004c45  jnz     short loc_180004C56
0x180004c47  cmp     dword ptr [r14+rdi+7708h], 0
0x180004c50  jz      loc_180004CD7
0x180004c56  test    r11d, r11d
0x180004c59  jz      short loc_180004C92
0x180004c5b  cmp     dword ptr [r14+rdi+7708h], 0
0x180004c64  jz      short loc_180004C92
0x180004c66  cmp     dword ptr [r9+7704h], 2
0x180004c6e  jnz     short loc_180004C92
0x180004c70  cmp     dword ptr [rbp+0], 2
0x180004c74  jnz     short loc_180004C8A
0x180004c76  cmp     dword ptr [rsi+766Ch], 2
0x180004c7d  jnz     short loc_180004C8A
0x180004c7f  mov     r10d, 3
0x180004c85  xor     r9d, r9d
0x180004c88  jmp     short loc_180004CB0
0x180004c8a  mov     r10d, 1
0x180004c90  jmp     short loc_180004CA6
0x180004c92  mov     ecx, dword ptr [rsp+0A8h+var_60]
0x180004c96  mov     eax, 20h ; ' '
0x180004c9b  sar     eax, cl
0x180004c9d  dec     eax
0x180004c9f  cmp     eax, r10d
0x180004ca2  cmovl   r10d, eax
0x180004ca6  xor     r9d, r9d
0x180004ca9  test    r10d, r10d
0x180004cac  jle     short loc_180004CD7
0x180004cae  xchg    ax, ax
0x180004cb0  lea     eax, [r9+r9*8]
0x180004cb4  lea     r8d, [rax+rax]
0x180004cb8  lea     eax, [r8+12h]
0x180004cbc  movsxd  rcx, eax
0x180004cbf  movsxd  rax, r8d
0x180004cc2  lea     rdx, [rbx+rcx*4]
0x180004cc6  lea     rcx, [rbx+rax*4]
0x180004cca  call    antialias_sb
0x180004ccf  inc     r9d
0x180004cd2  cmp     r9d, r10d
0x180004cd5  jl      short loc_180004CB0
0x180004cd7  mov     eax, [rsp+0A8h+arg_18]
0x180004cde  lea     r9, [rsi+76D8h]; struct MP3SI *
0x180004ce5  movzx   edx, byte ptr [rsp+0A8h+arg_0]; bool
0x180004ced  lea     rcx, [rsi+1370h]; this
0x180004cf4  mov     [rsp+0A8h+var_78], r15d; int
0x180004cf9  mov     r8, r13; struct MPEG_INFO *
0x180004cfc  mov     dword ptr [rsp+0A8h+var_80], eax; int
0x180004d00  mov     [rsp+0A8h+var_88], rbx; float *
0x180004d05  call    ?Apply@CErrorConcealment@@QEAAX_NAEBUMPEG_INFO@@AEAUMP3SI@@PEAMHH@Z; CErrorConcealment::Apply(bool,MPEG_INFO const &,MP3SI &,float *,int,int)
0x180004d0a  mov     r8, [rsp+0A8h+var_58]; struct MP3SI_GRCH *
0x180004d0f  lea     rbx, [rsi+8DC0h]
0x180004d16  mov     r9, rbx; float (*)[2][32][18]
0x180004d19  lea     rcx, [rsi+50h]; this
0x180004d1d  mov     edx, r15d; int
0x180004d20  call    ?Apply@CMdct@@QEAAXHAEBUMP3SI_GRCH@@AEAY21CA@BC@M@Z; CMdct::Apply(int,MP3SI_GRCH const &,float (&)[2][32][18])
0x180004d25  mov     rbp, [rsp+0A8h+var_50]
0x180004d2a  inc     r15d
0x180004d2d  inc     r12
0x180004d30  cmp     r15d, [rsp+0A8h+var_68]
0x180004d35  jl      loc_180004B40
0x180004d3b  mov     rcx, rsi; this
0x180004d3e  call    ?PolyphaseReorder@CMp3Decode@@IEAAXXZ; CMp3Decode::PolyphaseReorder(void)
0x180004d43  mov     r8, [rsp+0A8h+arg_8]; __int16 *
0x180004d4b  lea     rdx, [rsi+9FC0h]; float *(*)[2][18]
0x180004d52  lea     rcx, [rsi+1338h]; this
0x180004d59  call    ?Apply@CPolyphase@@QEAAPEAFAEAY11BC@PEAMPEAF@Z; CPolyphase::Apply(float * (&)[2][18],short *)
0x180004d5e  mov     edx, [rsp+0A8h+arg_18]
0x180004d65  movzx   edi, [rsp+0A8h+arg_10]
0x180004d6d  inc     edx
0x180004d6f  mov     [rsp+0A8h+arg_8], rax
0x180004d77  jmp     loc_180004957
0x180004d7c  xor     eax, eax
0x180004d7e  add     rsp, 68h
0x180004d82  pop     r15
0x180004d84  pop     r14
0x180004d86  pop     r13
0x180004d88  pop     r12
0x180004d8a  pop     rdi
0x180004d8b  pop     rsi
0x180004d8c  pop     rbp
0x180004d8d  pop     rbx
0x180004d8e  retn
```
