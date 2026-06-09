# CMdct::Apply(int,MP3SI_GRCH const &,float (&)[2][32][18])

- ea: `0x18000de50`
- end: `0x18000e123`
- name: `?Apply@CMdct@@QEAAXHAEBUMP3SI_GRCH@@AEAY21CA@BC@M@Z`
- size: `723`
- prototype: `void __fastcall(CMdct *__hidden this, int, const struct MP3SI_GRCH *, float (*)[2][32][18])`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180004910`
- `0x180004da0`

## callees

- `0x18000de50`
- `0x18000e200`
- `0x18000e3e0`

## pseudocode

```c
void __fastcall CMdct::Apply(CMdct *this, int a2, const struct MP3SI_GRCH *a3, float (*a4)[2][32][18])
{
  int v5; // eax
  __int64 v6; // r13
  int v9; // r8d
  int v10; // r12d
  __int64 v11; // rax
  int v12; // r15d
  int v13; // edi
  int v14; // edx
  __int64 v15; // rsi
  float *v16; // r10
  float *v17; // r8
  const float *v18; // r9
  bool v19; // zf
  float *v20; // rdx
  __int64 i; // rax

  v5 = *((_DWORD *)a3 + 26) + 1;
  v6 = a2;
  v9 = 32 >> *((_DWORD *)this + 1208);
  v10 = v9;
  if ( v9 >= v5 )
    v10 = v5;
  v11 = *((_QWORD *)this + 27);
  if ( *(_DWORD *)(v11 + 24) != 2 || (v12 = 4, *(_DWORD *)(v11 + 4) != 2) )
    v12 = 2;
  v13 = 0;
  if ( v9 > 0 )
  {
    do
    {
      if ( !*((_DWORD *)a3 + 4) || !*((_DWORD *)a3 + 6) || (v14 = 0, v13 >= v12) )
        v14 = *((_DWORD *)a3 + 5);
      v15 = v13 + 32 * v6;
      v16 = (float *)((char *)this + 72 * v15);
      if ( v13 >= v10 )
      {
        (*a4)[0][v15][0] = v16[56];
        v16[56] = 0.0;
        (*a4)[0][v15][1] = *((float *)this + 18 * v15 + 57);
        *((_DWORD *)this + 18 * v15 + 57) = 0;
        (*a4)[0][v15][2] = *((float *)this + 18 * v15 + 58);
        *((_DWORD *)this + 18 * v15 + 58) = 0;
        (*a4)[0][v15][3] = *((float *)this + 18 * v15 + 59);
        *((_DWORD *)this + 18 * v15 + 59) = 0;
        (*a4)[0][v15][4] = *((float *)this + 18 * v15 + 60);
        *((_DWORD *)this + 18 * v15 + 60) = 0;
        (*a4)[0][v15][5] = *((float *)this + 18 * v15 + 61);
        *((_DWORD *)this + 18 * v15 + 61) = 0;
        (*a4)[0][v15][6] = *((float *)this + 18 * v15 + 62);
        *((_DWORD *)this + 18 * v15 + 62) = 0;
        (*a4)[0][v15][7] = *((float *)this + 18 * v15 + 63);
        *((_DWORD *)this + 18 * v15 + 63) = 0;
        (*a4)[0][v15][8] = *((float *)this + 18 * v15 + 64);
        *((_DWORD *)this + 18 * v15 + 64) = 0;
        (*a4)[0][v15][9] = *((float *)this + 18 * v15 + 65);
        *((_DWORD *)this + 18 * v15 + 65) = 0;
        (*a4)[0][v15][10] = *((float *)this + 18 * v15 + 66);
        *((_DWORD *)this + 18 * v15 + 66) = 0;
        (*a4)[0][v15][11] = *((float *)this + 18 * v15 + 67);
        *((_DWORD *)this + 18 * v15 + 67) = 0;
        (*a4)[0][v15][12] = *((float *)this + 18 * v15 + 68);
        *((_DWORD *)this + 18 * v15 + 68) = 0;
        (*a4)[0][v15][13] = *((float *)this + 18 * v15 + 69);
        *((_DWORD *)this + 18 * v15 + 69) = 0;
        (*a4)[0][v15][14] = *((float *)this + 18 * v15 + 70);
        *((_DWORD *)this + 18 * v15 + 70) = 0;
        (*a4)[0][v15][15] = *((float *)this + 18 * v15 + 71);
        *((_DWORD *)this + 18 * v15 + 71) = 0;
        (*a4)[0][v15][16] = *((float *)this + 18 * v15 + 72);
        *((_DWORD *)this + 18 * v15 + 72) = 0;
        (*a4)[0][v15][17] = *((float *)this + 18 * v15 + 73);
        *((_DWORD *)this + 18 * v15 + 73) = 0;
      }
      else
      {
        v17 = (*a4)[0][v15];
        v18 = (const float *)&qword_180014810[18 * v14];
        v19 = v14 == 2;
        v20 = v16 + 56;
        if ( v19 )
          CMdct::cos_t_h_short(this, v20, v17, v18);
        else
          CMdct::cos_t_h_long(this, v20, v17, v18);
      }
      if ( (v13 & 1) != 0 )
      {
        for ( i = 1; i != 19; i += 2 )
          LODWORD((*a4)[0][v15][i]) ^= _xmm;
      }
      ++v13;
    }
    while ( v13 < 32 >> *((_DWORD *)this + 1208) );
  }
}

```

## disassembly

```asm
0x18000de50  mov     [rsp+arg_8], rbx
0x18000de55  mov     [rsp+arg_10], rbp
0x18000de5a  push    rdi
0x18000de5b  push    r12
0x18000de5d  push    r13
0x18000de5f  push    r14
0x18000de61  push    r15
0x18000de63  sub     rsp, 30h
0x18000de67  mov     eax, [r8+68h]
0x18000de6b  mov     rbp, r8
0x18000de6e  inc     eax
0x18000de70  movsxd  r13, edx
0x18000de73  mov     rbx, rcx
0x18000de76  mov     r8d, 20h ; ' '
0x18000de7c  mov     ecx, [rcx+12E0h]
0x18000de82  mov     r14, r9
0x18000de85  sar     r8d, cl
0x18000de88  cmp     r8d, eax
0x18000de8b  mov     r12d, r8d
0x18000de8e  cmovge  r12d, eax
0x18000de92  mov     rax, [rbx+0D8h]
0x18000de99  cmp     dword ptr [rax+18h], 2
0x18000de9d  jnz     short loc_18000DEAB
0x18000de9f  cmp     dword ptr [rax+4], 2
0x18000dea3  mov     r15d, 4
0x18000dea9  jz      short loc_18000DEB1
0x18000deab  mov     r15d, 2
0x18000deb1  xor     r9d, r9d
0x18000deb4  mov     edi, r9d
0x18000deb7  test    r8d, r8d
0x18000deba  jle     loc_18000E10B
0x18000dec0  mov     [rsp+58h+arg_0], rsi
0x18000dec5  lea     r11, qword_180014810
0x18000decc  movaps  [rsp+58h+var_38], xmm6
0x18000ded1  movss   xmm6, cs:__xmm@80000000800000008000000080000000
0x18000ded9  nop     dword ptr [rax+00000000h]
0x18000dee0  cmp     dword ptr [rbp+10h], 0
0x18000dee4  jz      short loc_18000DEF4
0x18000dee6  cmp     dword ptr [rbp+18h], 0
0x18000deea  jz      short loc_18000DEF4
0x18000deec  mov     edx, r9d
0x18000deef  cmp     edi, r15d
0x18000def2  jl      short loc_18000DEF7
0x18000def4  mov     edx, [rbp+14h]
0x18000def7  mov     rsi, r13
0x18000defa  movsxd  rax, edi
0x18000defd  shl     rsi, 5
0x18000df01  add     rsi, rax
0x18000df04  lea     rcx, [rsi+rsi*8]
0x18000df08  lea     r10, [rbx+rcx*8]
0x18000df0c  cmp     edi, r12d
0x18000df0f  jge     short loc_18000DF5A
0x18000df11  movsxd  rax, edx
0x18000df14  lea     r8, [r14+rcx*8]; float *
0x18000df18  mov     rcx, rbx; this
0x18000df1b  lea     r9, [rax+rax*8]
0x18000df1f  shl     r9, 4
0x18000df23  add     r9, r11; float *
0x18000df26  cmp     edx, 2
0x18000df29  lea     rdx, [r10+0E0h]; float *
0x18000df30  jnz     short loc_18000DF46
0x18000df32  call    ?cos_t_h_short@CMdct@@IEAAXPEAM0PEBM@Z; CMdct::cos_t_h_short(float *,float *,float const *)
0x18000df37  xor     r9d, r9d
0x18000df3a  lea     r11, qword_180014810
0x18000df41  jmp     loc_18000E0C0
0x18000df46  call    ?cos_t_h_long@CMdct@@IEAAXPEAM0PEBM@Z; CMdct::cos_t_h_long(float *,float *,float const *)
0x18000df4b  xor     r9d, r9d
0x18000df4e  lea     r11, qword_180014810
0x18000df55  jmp     loc_18000E0C0
0x18000df5a  mov     eax, [r10+0E0h]
0x18000df61  mov     [r14+rcx*8], eax
0x18000df65  mov     [r10+0E0h], r9d
0x18000df6c  mov     eax, [rbx+rcx*8+0E4h]
0x18000df73  mov     [r14+rcx*8+4], eax
0x18000df78  mov     [rbx+rcx*8+0E4h], r9d
0x18000df80  mov     eax, [rbx+rcx*8+0E8h]
0x18000df87  mov     [r14+rcx*8+8], eax
0x18000df8c  mov     [rbx+rcx*8+0E8h], r9d
0x18000df94  mov     eax, [rbx+rcx*8+0ECh]
0x18000df9b  mov     [r14+rcx*8+0Ch], eax
0x18000dfa0  mov     [rbx+rcx*8+0ECh], r9d
0x18000dfa8  mov     eax, [rbx+rcx*8+0F0h]
0x18000dfaf  mov     [r14+rcx*8+10h], eax
0x18000dfb4  mov     [rbx+rcx*8+0F0h], r9d
0x18000dfbc  mov     eax, [rbx+rcx*8+0F4h]
0x18000dfc3  mov     [r14+rcx*8+14h], eax
0x18000dfc8  mov     [rbx+rcx*8+0F4h], r9d
0x18000dfd0  mov     eax, [rbx+rcx*8+0F8h]
0x18000dfd7  mov     [r14+rcx*8+18h], eax
0x18000dfdc  mov     [rbx+rcx*8+0F8h], r9d
0x18000dfe4  mov     eax, [rbx+rcx*8+0FCh]
0x18000dfeb  mov     [r14+rcx*8+1Ch], eax
0x18000dff0  mov     [rbx+rcx*8+0FCh], r9d
0x18000dff8  mov     eax, [rbx+rcx*8+100h]
0x18000dfff  mov     [r14+rcx*8+20h], eax
0x18000e004  mov     [rbx+rcx*8+100h], r9d
0x18000e00c  mov     eax, [rbx+rcx*8+104h]
0x18000e013  mov     [r14+rcx*8+24h], eax
0x18000e018  mov     [rbx+rcx*8+104h], r9d
0x18000e020  mov     eax, [rbx+rcx*8+108h]
0x18000e027  mov     [r14+rcx*8+28h], eax
0x18000e02c  mov     [rbx+rcx*8+108h], r9d
0x18000e034  mov     eax, [rbx+rcx*8+10Ch]
0x18000e03b  mov     [r14+rcx*8+2Ch], eax
0x18000e040  mov     [rbx+rcx*8+10Ch], r9d
0x18000e048  mov     eax, [rbx+rcx*8+110h]
0x18000e04f  mov     [r14+rcx*8+30h], eax
0x18000e054  mov     [rbx+rcx*8+110h], r9d
0x18000e05c  mov     eax, [rbx+rcx*8+114h]
0x18000e063  mov     [r14+rcx*8+34h], eax
0x18000e068  mov     [rbx+rcx*8+114h], r9d
0x18000e070  mov     eax, [rbx+rcx*8+118h]
0x18000e077  mov     [r14+rcx*8+38h], eax
0x18000e07c  mov     [rbx+rcx*8+118h], r9d
0x18000e084  mov     eax, [rbx+rcx*8+11Ch]
0x18000e08b  mov     [r14+rcx*8+3Ch], eax
0x18000e090  mov     [rbx+rcx*8+11Ch], r9d
0x18000e098  mov     eax, [rbx+rcx*8+120h]
0x18000e09f  mov     [r14+rcx*8+40h], eax
0x18000e0a4  mov     [rbx+rcx*8+120h], r9d
0x18000e0ac  mov     eax, [rbx+rcx*8+124h]
0x18000e0b3  mov     [r14+rcx*8+44h], eax
0x18000e0b8  mov     [rbx+rcx*8+124h], r9d
0x18000e0c0  test    dil, 1
0x18000e0c4  jz      short loc_18000E0EA
0x18000e0c6  lea     rax, [rsi+rsi*8]
0x18000e0ca  lea     rcx, [r14+rax*8]
0x18000e0ce  mov     eax, 1
0x18000e0d3  movss   xmm0, dword ptr [rcx+rax*4]
0x18000e0d8  xorps   xmm0, xmm6
0x18000e0db  movss   dword ptr [rcx+rax*4], xmm0
0x18000e0e0  add     rax, 2
0x18000e0e4  cmp     rax, 13h
0x18000e0e8  jnz     short loc_18000E0D3
0x18000e0ea  mov     ecx, [rbx+12E0h]
0x18000e0f0  mov     eax, 20h ; ' '
0x18000e0f5  sar     eax, cl
0x18000e0f7  inc     edi
0x18000e0f9  cmp     edi, eax
0x18000e0fb  jl      loc_18000DEE0
0x18000e101  movaps  xmm6, [rsp+58h+var_38]
0x18000e106  mov     rsi, [rsp+58h+arg_0]
0x18000e10b  mov     rbx, [rsp+58h+arg_8]
0x18000e110  mov     rbp, [rsp+58h+arg_10]
0x18000e115  add     rsp, 30h
0x18000e119  pop     r15
0x18000e11b  pop     r14
0x18000e11d  pop     r13
0x18000e11f  pop     r12
0x18000e121  pop     rdi
0x18000e122  retn
```
