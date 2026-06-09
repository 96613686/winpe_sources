# CMdct::Apply(int,MP3SI_GRCH const &,float (&)[2][32][18])

- ea: `0x180002790`
- end: `0x180002a88`
- name: `?Apply@CMdct@@QEAAXHAEBUMP3SI_GRCH@@AEAY21CA@BC@M@Z`
- size: `760`
- prototype: `void __fastcall(CMdct *__hidden this, int, const struct MP3SI_GRCH *, float (*)[2][32][18])`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180003b80`
- `0x18000d780`

## callees

- `0x180002790`
- `0x180002a90`
- `0x180003680`

## pseudocode

```c
void __fastcall CMdct::Apply(CMdct *this, int a2, const struct MP3SI_GRCH *a3, float (*a4)[2][32][18])
{
  __int64 v5; // r12
  int v8; // edx
  int v9; // r15d
  __int64 v10; // rax
  int v11; // r13d
  int v12; // ebx
  int v13; // edx
  __int64 v14; // rdi
  float *v15; // r10
  float *v16; // r8
  const float *v17; // r9
  bool v18; // zf
  float *v19; // rdx
  __int64 i; // rax

  v5 = a2;
  v8 = 32 >> *((_DWORD *)this + 1208);
  v9 = v8;
  if ( v8 >= *((_DWORD *)a3 + 26) + 1 )
    v9 = *((_DWORD *)a3 + 26) + 1;
  v10 = *((_QWORD *)this + 27);
  if ( *(_DWORD *)(v10 + 24) == 2 && *(_DWORD *)(v10 + 4) == 2 )
    v11 = 4;
  else
    v11 = 2;
  v12 = 0;
  if ( v8 > 0 )
  {
    do
    {
      if ( *((_DWORD *)a3 + 4) && *((_DWORD *)a3 + 6) && v12 < v11 )
        v13 = 0;
      else
        v13 = *((_DWORD *)a3 + 5);
      v14 = v12 + 32 * v5;
      v15 = (float *)((char *)this + 72 * v14);
      if ( v12 >= v9 )
      {
        (*a4)[0][v14][0] = v15[56];
        v15[56] = 0.0;
        (*a4)[0][v14][1] = *((float *)this + 18 * v14 + 57);
        *((_DWORD *)this + 18 * v14 + 57) = 0;
        (*a4)[0][v14][2] = *((float *)this + 18 * v14 + 58);
        *((_DWORD *)this + 18 * v14 + 58) = 0;
        (*a4)[0][v14][3] = *((float *)this + 18 * v14 + 59);
        *((_DWORD *)this + 18 * v14 + 59) = 0;
        (*a4)[0][v14][4] = *((float *)this + 18 * v14 + 60);
        *((_DWORD *)this + 18 * v14 + 60) = 0;
        (*a4)[0][v14][5] = *((float *)this + 18 * v14 + 61);
        *((_DWORD *)this + 18 * v14 + 61) = 0;
        (*a4)[0][v14][6] = *((float *)this + 18 * v14 + 62);
        *((_DWORD *)this + 18 * v14 + 62) = 0;
        (*a4)[0][v14][7] = *((float *)this + 18 * v14 + 63);
        *((_DWORD *)this + 18 * v14 + 63) = 0;
        (*a4)[0][v14][8] = *((float *)this + 18 * v14 + 64);
        *((_DWORD *)this + 18 * v14 + 64) = 0;
        (*a4)[0][v14][9] = *((float *)this + 18 * v14 + 65);
        *((_DWORD *)this + 18 * v14 + 65) = 0;
        (*a4)[0][v14][10] = *((float *)this + 18 * v14 + 66);
        *((_DWORD *)this + 18 * v14 + 66) = 0;
        (*a4)[0][v14][11] = *((float *)this + 18 * v14 + 67);
        *((_DWORD *)this + 18 * v14 + 67) = 0;
        (*a4)[0][v14][12] = *((float *)this + 18 * v14 + 68);
        *((_DWORD *)this + 18 * v14 + 68) = 0;
        (*a4)[0][v14][13] = *((float *)this + 18 * v14 + 69);
        *((_DWORD *)this + 18 * v14 + 69) = 0;
        (*a4)[0][v14][14] = *((float *)this + 18 * v14 + 70);
        *((_DWORD *)this + 18 * v14 + 70) = 0;
        (*a4)[0][v14][15] = *((float *)this + 18 * v14 + 71);
        *((_DWORD *)this + 18 * v14 + 71) = 0;
        (*a4)[0][v14][16] = *((float *)this + 18 * v14 + 72);
        *((_DWORD *)this + 18 * v14 + 72) = 0;
        (*a4)[0][v14][17] = *((float *)this + 18 * v14 + 73);
        *((_DWORD *)this + 18 * v14 + 73) = 0;
      }
      else
      {
        v16 = (*a4)[0][v14];
        v17 = (const float *)&qword_180014650[18 * v13];
        v18 = v13 == 2;
        v19 = v15 + 56;
        if ( v18 )
          CMdct::cos_t_h_short(this, v19, v16, v17);
        else
          CMdct::cos_t_h_long(this, v19, v16, v17);
      }
      if ( (v12 & 1) != 0 )
      {
        for ( i = 1; i != 19; i += 2 )
          LODWORD((*a4)[0][v14][i]) ^= _xmm;
      }
      ++v12;
    }
    while ( v12 < 32 >> *((_DWORD *)this + 1208) );
  }
}

```

## disassembly

```asm
0x180002790  mov     [rsp+arg_8], rbx
0x180002795  mov     [rsp+arg_10], rbp
0x18000279a  push    rsi
0x18000279b  push    r12
0x18000279d  push    r13
0x18000279f  push    r14
0x1800027a1  push    r15
0x1800027a3  sub     rsp, 30h
0x1800027a7  mov     eax, [r8+68h]
0x1800027ab  mov     rsi, rcx
0x1800027ae  mov     ecx, [rcx+12E0h]
0x1800027b4  inc     eax
0x1800027b6  movsxd  r12, edx
0x1800027b9  mov     r14, r9
0x1800027bc  mov     edx, 20h ; ' '
0x1800027c1  mov     rbp, r8
0x1800027c4  sar     edx, cl
0x1800027c6  cmp     edx, eax
0x1800027c8  mov     r15d, edx
0x1800027cb  cmovge  r15d, eax
0x1800027cf  mov     rax, [rsi+0D8h]
0x1800027d6  cmp     dword ptr [rax+18h], 2
0x1800027da  jz      loc_180002A73
0x1800027e0  mov     r13d, 2
0x1800027e6  xor     r8d, r8d
0x1800027e9  mov     ebx, r8d
0x1800027ec  test    edx, edx
0x1800027ee  jle     loc_180002891
0x1800027f4  mov     [rsp+58h+arg_0], rdi
0x1800027f9  lea     r9, qword_180014650
0x180002800  movaps  [rsp+58h+var_38], xmm6
0x180002805  movss   xmm6, cs:__xmm@80000000800000008000000080000000
0x18000280d  nop     dword ptr [rax]
0x180002810  cmp     dword ptr [rbp+10h], 0
0x180002814  jnz     loc_180002A44
0x18000281a  mov     edx, [rbp+14h]
0x18000281d  mov     rdi, r12
0x180002820  movsxd  rax, ebx
0x180002823  shl     rdi, 5
0x180002827  add     rdi, rax
0x18000282a  lea     rcx, [rdi+rdi*8]
0x18000282e  lea     r10, [rsi+rcx*8]
0x180002832  cmp     ebx, r15d
0x180002835  jge     loc_1800028D9
0x18000283b  lea     r8, [r14+rcx*8]; float *
0x18000283f  movsxd  rax, edx
0x180002842  lea     rcx, [rax+rax*8]
0x180002846  shl     rcx, 4
0x18000284a  add     r9, rcx; float *
0x18000284d  mov     rcx, rsi; this
0x180002850  cmp     edx, 2
0x180002853  lea     rdx, [r10+0E0h]; float *
0x18000285a  jz      loc_180002A5F
0x180002860  call    ?cos_t_h_long@CMdct@@IEAAXPEAM0PEBM@Z; CMdct::cos_t_h_long(float *,float *,float const *)
0x180002865  xor     r8d, r8d
0x180002868  lea     r9, qword_180014650
0x18000286f  test    bl, 1
0x180002872  jnz     short loc_1800028A9
0x180002874  mov     ecx, [rsi+12E0h]
0x18000287a  mov     eax, 20h ; ' '
0x18000287f  sar     eax, cl
0x180002881  inc     ebx
0x180002883  cmp     ebx, eax
0x180002885  jl      short loc_180002810
0x180002887  movaps  xmm6, [rsp+58h+var_38]
0x18000288c  mov     rdi, [rsp+58h+arg_0]
0x180002891  mov     rbx, [rsp+58h+arg_8]
0x180002896  mov     rbp, [rsp+58h+arg_10]
0x18000289b  add     rsp, 30h
0x18000289f  pop     r15
0x1800028a1  pop     r14
0x1800028a3  pop     r13
0x1800028a5  pop     r12
0x1800028a7  pop     rsi
0x1800028a8  retn
0x1800028a9  lea     rax, [rdi+rdi*8]
0x1800028ad  lea     rcx, [r14+rax*8]
0x1800028b1  mov     eax, 1
0x1800028b6  nop     word ptr [rax+rax+00000000h]
0x1800028c0  movss   xmm0, dword ptr [rcx+rax*4]
0x1800028c5  xorps   xmm0, xmm6
0x1800028c8  movss   dword ptr [rcx+rax*4], xmm0
0x1800028cd  add     rax, 2
0x1800028d1  cmp     rax, 13h
0x1800028d5  jnz     short loc_1800028C0
0x1800028d7  jmp     short loc_180002874
0x1800028d9  mov     eax, [r10+0E0h]
0x1800028e0  mov     [r14+rcx*8], eax
0x1800028e4  mov     [r10+0E0h], r8d
0x1800028eb  mov     eax, [rsi+rcx*8+0E4h]
0x1800028f2  mov     [r14+rcx*8+4], eax
0x1800028f7  mov     [rsi+rcx*8+0E4h], r8d
0x1800028ff  mov     eax, [rsi+rcx*8+0E8h]
0x180002906  mov     [r14+rcx*8+8], eax
0x18000290b  mov     [rsi+rcx*8+0E8h], r8d
0x180002913  mov     eax, [rsi+rcx*8+0ECh]
0x18000291a  mov     [r14+rcx*8+0Ch], eax
0x18000291f  mov     [rsi+rcx*8+0ECh], r8d
0x180002927  mov     eax, [rsi+rcx*8+0F0h]
0x18000292e  mov     [r14+rcx*8+10h], eax
0x180002933  mov     [rsi+rcx*8+0F0h], r8d
0x18000293b  mov     eax, [rsi+rcx*8+0F4h]
0x180002942  mov     [r14+rcx*8+14h], eax
0x180002947  mov     [rsi+rcx*8+0F4h], r8d
0x18000294f  mov     eax, [rsi+rcx*8+0F8h]
0x180002956  mov     [r14+rcx*8+18h], eax
0x18000295b  mov     [rsi+rcx*8+0F8h], r8d
0x180002963  mov     eax, [rsi+rcx*8+0FCh]
0x18000296a  mov     [r14+rcx*8+1Ch], eax
0x18000296f  mov     [rsi+rcx*8+0FCh], r8d
0x180002977  mov     eax, [rsi+rcx*8+100h]
0x18000297e  mov     [r14+rcx*8+20h], eax
0x180002983  mov     [rsi+rcx*8+100h], r8d
0x18000298b  mov     eax, [rsi+rcx*8+104h]
0x180002992  mov     [r14+rcx*8+24h], eax
0x180002997  mov     [rsi+rcx*8+104h], r8d
0x18000299f  mov     eax, [rsi+rcx*8+108h]
0x1800029a6  mov     [r14+rcx*8+28h], eax
0x1800029ab  mov     [rsi+rcx*8+108h], r8d
0x1800029b3  mov     eax, [rsi+rcx*8+10Ch]
0x1800029ba  mov     [r14+rcx*8+2Ch], eax
0x1800029bf  mov     [rsi+rcx*8+10Ch], r8d
0x1800029c7  mov     eax, [rsi+rcx*8+110h]
0x1800029ce  mov     [r14+rcx*8+30h], eax
0x1800029d3  mov     [rsi+rcx*8+110h], r8d
0x1800029db  mov     eax, [rsi+rcx*8+114h]
0x1800029e2  mov     [r14+rcx*8+34h], eax
0x1800029e7  mov     [rsi+rcx*8+114h], r8d
0x1800029ef  mov     eax, [rsi+rcx*8+118h]
0x1800029f6  mov     [r14+rcx*8+38h], eax
0x1800029fb  mov     [rsi+rcx*8+118h], r8d
0x180002a03  mov     eax, [rsi+rcx*8+11Ch]
0x180002a0a  mov     [r14+rcx*8+3Ch], eax
0x180002a0f  mov     [rsi+rcx*8+11Ch], r8d
0x180002a17  mov     eax, [rsi+rcx*8+120h]
0x180002a1e  mov     [r14+rcx*8+40h], eax
0x180002a23  mov     [rsi+rcx*8+120h], r8d
0x180002a2b  mov     eax, [rsi+rcx*8+124h]
0x180002a32  mov     [r14+rcx*8+44h], eax
0x180002a37  mov     [rsi+rcx*8+124h], r8d
0x180002a3f  jmp     loc_18000286F
0x180002a44  cmp     dword ptr [rbp+18h], 0
0x180002a48  jz      loc_18000281A
0x180002a4e  cmp     ebx, r13d
0x180002a51  jge     loc_18000281A
0x180002a57  mov     edx, r8d
0x180002a5a  jmp     loc_18000281D
0x180002a5f  call    ?cos_t_h_short@CMdct@@IEAAXPEAM0PEBM@Z; CMdct::cos_t_h_short(float *,float *,float const *)
0x180002a64  xor     r8d, r8d
0x180002a67  lea     r9, qword_180014650
0x180002a6e  jmp     loc_18000286F
0x180002a73  cmp     dword ptr [rax+4], 2
0x180002a77  jnz     loc_1800027E0
0x180002a7d  mov     r13d, 4
0x180002a83  jmp     loc_1800027E6
```
