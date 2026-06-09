# CPolyphase::window_band_m(int,short *,int)

- ea: `0x180006ed0`
- end: `0x180007282`
- name: `?window_band_m@CPolyphase@@IEAAXHPEAFH@Z`
- size: `946`
- prototype: `void __fastcall(CPolyphase *__hidden this, int, __int16 *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005be0`

## callees

- `0x180006ed0`

## pseudocode

```c
void __fastcall CPolyphase::window_band_m(CPolyphase *this, int a2, __int16 *a3)
{
  __int64 v3; // r10
  float *v4; // r9
  int v6; // ebx
  double v9; // xmm4_8
  double v10; // xmm3_8
  int v11; // r11d
  __int16 v12; // cx
  double v13; // xmm2_8
  float v14; // xmm0_4
  double v15; // xmm2_8
  double v16; // xmm3_8
  double v17; // xmm4_8
  double v18; // xmm3_8
  double v19; // xmm4_8
  int v20; // ecx
  int v21; // eax
  int v22; // r10d
  __int64 v23; // r11
  int v24; // r8d
  double v25; // xmm7_8
  double v26; // xmm6_8
  int v27; // edx
  __int16 v28; // ax
  float v29; // xmm4_4
  float v30; // xmm1_4
  float v31; // xmm4_4
  float v32; // xmm0_4
  float v33; // xmm3_4
  float v34; // xmm0_4
  double v35; // xmm6_8
  double v36; // xmm7_8
  int v37; // eax
  int v38; // r10d
  __int64 v39; // r11
  int v40; // r8d
  double v41; // xmm7_8
  double v42; // xmm6_8
  int v43; // edx
  __int16 v44; // ax
  float v45; // xmm4_4
  float v46; // xmm1_4
  float v47; // xmm4_4
  float v48; // xmm0_4
  float v49; // xmm3_4
  float v50; // xmm0_4
  double v51; // xmm6_8
  double v52; // xmm7_8
  int v53; // eax

  v3 = *((_QWORD *)this + 1);
  v4 = (float *)qword_180013910;
  v6 = 8;
  v9 = 0.0;
  v10 = 0.0;
  v11 = a2;
  do
  {
    v12 = v11;
    v11 += 64;
    v9 = v9 + (float)(*(float *)(v3 + 4LL * ((v12 + 32) & 0x1FF)) * v4[3]);
    v13 = (float)(*(float *)(v3 + 4LL * ((v12 + 48) & 0x1FF)) * v4[2]);
    v14 = *(float *)(v3 + 4LL * ((v12 + 16) & 0x1FF)) * *v4;
    v4 += 4;
    v15 = v13 + v14 + v10;
    v10 = v15;
    --v6;
  }
  while ( v6 );
  if ( *((_DWORD *)this + 11) )
  {
    if ( v15 >= 32767.0 )
      v18 = DOUBLE_32767_0;
    else
      v18 = fmax(v15, -32767.0);
    *(_BYTE *)a3 = ((unsigned __int16)(int)v18 >> 8) + 0x80;
    if ( v9 >= 32767.0 )
      v19 = DOUBLE_32767_0;
    else
      v19 = fmax(v9, -32767.0);
    *((_BYTE *)a3 + (16LL >> *((_DWORD *)this + 10))) = ((unsigned __int16)(int)v19 >> 8) + 0x80;
  }
  else
  {
    if ( v15 >= 32767.0 )
      v16 = DOUBLE_32767_0;
    else
      v16 = fmax(v15, -32767.0);
    *a3 = (int)v16;
    if ( v9 >= 32767.0 )
      v17 = DOUBLE_32767_0;
    else
      v17 = fmax(v9, -32767.0);
    a3[16LL >> *((_DWORD *)this + 10)] = (int)v17;
  }
  v20 = *((_DWORD *)this + 10);
  v21 = 16 >> v20;
  if ( *((_DWORD *)this + 11) )
  {
    if ( v21 > 1 )
    {
      v38 = 1;
      do
      {
        v39 = *((_QWORD *)this + 1);
        v40 = 0;
        v41 = 0.0;
        v42 = 0.0;
        v4 += (32 << v20) - 32;
        v43 = a2 + v38 * __ROL4__(1, v20);
        do
        {
          v44 = v43 + v40;
          v40 += 64;
          v45 = *(float *)(v39 + 4LL * ((v44 + 32) & 0x1FF));
          v46 = v45 * v4[2];
          v47 = v45 * v4[3];
          v48 = *(float *)(v39 + 4LL * ((v44 + 16) & 0x1FF));
          v49 = v48 * v4[1];
          v50 = v48 * *v4;
          v4 += 4;
          v42 = v42 + v50 + v46;
          v41 = v41 + v49 + v47;
        }
        while ( v40 < 512 );
        if ( v42 >= 32767.0 )
          v51 = DOUBLE_32767_0;
        else
          v51 = fmax(v42, -32767.0);
        *((_BYTE *)a3 + v38) = ((unsigned __int16)(int)v51 >> 8) + 0x80;
        if ( v41 >= 32767.0 )
          v52 = DOUBLE_32767_0;
        else
          v52 = fmax(v41, -32767.0);
        v53 = (32 >> *((_DWORD *)this + 10)) - v38++;
        *((_BYTE *)a3 + v53) = ((unsigned __int16)(int)v52 >> 8) + 0x80;
        v20 = *((_DWORD *)this + 10);
      }
      while ( v38 < 16 >> v20 );
    }
  }
  else if ( v21 > 1 )
  {
    v22 = 1;
    do
    {
      v23 = *((_QWORD *)this + 1);
      v24 = 0;
      v25 = 0.0;
      v26 = 0.0;
      v4 += (32 << v20) - 32;
      v27 = a2 + v22 * __ROL4__(1, v20);
      do
      {
        v28 = v27 + v24;
        v24 += 64;
        v29 = *(float *)(v23 + 4LL * ((v28 + 32) & 0x1FF));
        v30 = v29 * v4[2];
        v31 = v29 * v4[3];
        v32 = *(float *)(v23 + 4LL * ((v28 + 16) & 0x1FF));
        v33 = v32 * v4[1];
        v34 = v32 * *v4;
        v4 += 4;
        v26 = v26 + v34 + v30;
        v25 = v25 + v33 + v31;
      }
      while ( v24 < 512 );
      if ( v26 >= 32767.0 )
        v35 = DOUBLE_32767_0;
      else
        v35 = fmax(v26, -32767.0);
      a3[v22] = (int)v35;
      if ( v25 >= 32767.0 )
        v36 = DOUBLE_32767_0;
      else
        v36 = fmax(v25, -32767.0);
      v37 = (32 >> *((_DWORD *)this + 10)) - v22++;
      a3[v37] = (int)v36;
      v20 = *((_DWORD *)this + 10);
    }
    while ( v22 < 16 >> v20 );
  }
}

```

## disassembly

```asm
0x180006ed0  mov     [rsp+arg_8], rbp
0x180006ed5  mov     [rsp+arg_10], rsi
0x180006eda  push    rdi
0x180006edb  sub     rsp, 30h
0x180006edf  mov     r10, [rcx+8]
0x180006ee3  lea     r9, qword_180013910
0x180006eea  mov     [rsp+38h+arg_0], rbx
0x180006eef  mov     rsi, r8
0x180006ef2  mov     ebx, 8
0x180006ef7  mov     ebp, edx
0x180006ef9  mov     rdi, rcx
0x180006efc  xorps   xmm4, xmm4
0x180006eff  xorps   xmm3, xmm3
0x180006f02  mov     r11d, edx
0x180006f05  nop     word ptr [rax+rax+00000000h]
0x180006f10  movsxd  rcx, r11d
0x180006f13  add     r11d, 40h ; '@'
0x180006f17  lea     rax, [rcx+20h]
0x180006f1b  and     eax, 1FFh
0x180006f20  movss   xmm0, dword ptr [r10+rax*4]
0x180006f26  lea     rax, [rcx+30h]
0x180006f2a  mulss   xmm0, dword ptr [r9+0Ch]
0x180006f30  and     eax, 1FFh
0x180006f35  cvtps2pd xmm0, xmm0
0x180006f38  addsd   xmm4, xmm0
0x180006f3c  movss   xmm0, dword ptr [r10+rax*4]
0x180006f42  mulss   xmm0, dword ptr [r9+8]
0x180006f48  lea     rax, [rcx+10h]
0x180006f4c  and     eax, 1FFh
0x180006f51  cvtps2pd xmm2, xmm0
0x180006f54  movss   xmm0, dword ptr [r10+rax*4]
0x180006f5a  mulss   xmm0, dword ptr [r9]
0x180006f5f  add     r9, 10h
0x180006f63  cvtps2pd xmm1, xmm0
0x180006f66  addsd   xmm1, xmm3
0x180006f6a  addsd   xmm2, xmm1
0x180006f6e  movaps  xmm3, xmm2
0x180006f71  sub     ebx, 1
0x180006f74  jnz     short loc_180006F10
0x180006f76  cmp     dword ptr [rdi+2Ch], 0
0x180006f7a  mov     rbx, [rsp+38h+arg_0]
0x180006f7f  movsd   xmm5, cs:__real@40dfffc000000000
0x180006f87  movaps  [rsp+38h+var_38], xmm8
0x180006f8c  movsd   xmm8, cs:__real@c0dfffc000000000
0x180006f95  jnz     short loc_180006FD5
0x180006f97  comisd  xmm5, xmm2
0x180006f9b  jbe     short loc_180006FA4
0x180006f9d  maxsd   xmm3, xmm8
0x180006fa2  jmp     short loc_180006FA7
0x180006fa4  movaps  xmm3, xmm5
0x180006fa7  comisd  xmm5, xmm4
0x180006fab  cvttsd2si eax, xmm3
0x180006faf  mov     [r8], ax
0x180006fb3  jbe     short loc_180006FBC
0x180006fb5  maxsd   xmm4, xmm8
0x180006fba  jmp     short loc_180006FBF
0x180006fbc  movaps  xmm4, xmm5
0x180006fbf  mov     ecx, [rdi+28h]
0x180006fc2  mov     eax, 10h
0x180006fc7  cvttsd2si edx, xmm4
0x180006fcb  sar     rax, cl
0x180006fce  mov     [r8+rax*2], dx
0x180006fd3  jmp     short loc_18000701C
0x180006fd5  comisd  xmm5, xmm3
0x180006fd9  jbe     short loc_180006FE2
0x180006fdb  maxsd   xmm3, xmm8
0x180006fe0  jmp     short loc_180006FE5
0x180006fe2  movaps  xmm3, xmm5
0x180006fe5  cvttsd2si eax, xmm3
0x180006fe9  sar     ax, 8
0x180006fed  add     al, 80h
0x180006fef  comisd  xmm5, xmm4
0x180006ff3  mov     [r8], al
0x180006ff6  jbe     short loc_180006FFF
0x180006ff8  maxsd   xmm4, xmm8
0x180006ffd  jmp     short loc_180007002
0x180006fff  movaps  xmm4, xmm5
0x180007002  mov     ecx, [rdi+28h]
0x180007005  mov     eax, 10h
0x18000700a  cvttsd2si edx, xmm4
0x18000700e  sar     dx, 8
0x180007012  add     dl, 80h
0x180007015  sar     rax, cl
0x180007018  mov     [rax+r8], dl
0x18000701c  mov     ecx, [rdi+28h]
0x18000701f  mov     eax, 10h
0x180007024  sar     eax, cl
0x180007026  cmp     dword ptr [rdi+2Ch], 0
0x18000702a  movaps  [rsp+38h+var_18], xmm6
0x18000702f  movaps  [rsp+38h+var_28], xmm7
0x180007034  jnz     loc_18000714C
0x18000703a  cmp     eax, 1
0x18000703d  jle     loc_180007263
0x180007043  mov     r10d, 1
0x180007049  nop     dword ptr [rax+00000000h]
0x180007050  mov     r11, [rdi+8]
0x180007054  mov     eax, 20h ; ' '
0x180007059  shl     eax, cl
0x18000705b  mov     edx, 1
0x180007060  rol     edx, cl
0x180007062  sub     eax, 20h ; ' '
0x180007065  imul    edx, r10d
0x180007069  xor     r8d, r8d
0x18000706c  cdqe
0x18000706e  xorps   xmm7, xmm7
0x180007071  xorps   xmm6, xmm6
0x180007074  lea     r9, [r9+rax*4]
0x180007078  add     edx, ebp
0x18000707a  nop     word ptr [rax+rax+00h]
0x180007080  lea     eax, [rdx+r8]
0x180007084  add     r8d, 40h ; '@'
0x180007088  movsxd  rcx, eax
0x18000708b  lea     rax, [rcx+20h]
0x18000708f  and     eax, 1FFh
0x180007094  movss   xmm4, dword ptr [r11+rax*4]
0x18000709a  lea     rax, [rcx+10h]
0x18000709e  movaps  xmm1, xmm4
0x1800070a1  and     eax, 1FFh
0x1800070a6  mulss   xmm1, dword ptr [r9+8]
0x1800070ac  mulss   xmm4, dword ptr [r9+0Ch]
0x1800070b2  movss   xmm3, dword ptr [r11+rax*4]
0x1800070b8  movaps  xmm0, xmm3
0x1800070bb  mulss   xmm3, dword ptr [r9+4]
0x1800070c1  mulss   xmm0, dword ptr [r9]
0x1800070c6  add     r9, 10h
0x1800070ca  cvtps2pd xmm2, xmm0
0x1800070cd  cvtps2pd xmm0, xmm1
0x1800070d0  addsd   xmm6, xmm2
0x1800070d4  cvtps2pd xmm1, xmm3
0x1800070d7  addsd   xmm6, xmm0
0x1800070db  addsd   xmm7, xmm1
0x1800070df  cvtps2pd xmm0, xmm4
0x1800070e2  addsd   xmm7, xmm0
0x1800070e6  cmp     r8d, 200h
0x1800070ed  jl      short loc_180007080
0x1800070ef  comisd  xmm5, xmm6
0x1800070f3  jbe     short loc_1800070FC
0x1800070f5  maxsd   xmm6, xmm8
0x1800070fa  jmp     short loc_1800070FF
0x1800070fc  movaps  xmm6, xmm5
0x1800070ff  comisd  xmm5, xmm7
0x180007103  movsxd  rax, r10d
0x180007106  cvttsd2si ecx, xmm6
0x18000710a  mov     [rsi+rax*2], cx
0x18000710e  jbe     short loc_180007117
0x180007110  maxsd   xmm7, xmm8
0x180007115  jmp     short loc_18000711A
0x180007117  movaps  xmm7, xmm5
0x18000711a  mov     ecx, [rdi+28h]
0x18000711d  mov     eax, 20h ; ' '
0x180007122  sar     eax, cl
0x180007124  sub     eax, r10d
0x180007127  inc     r10d
0x18000712a  cdqe
0x18000712c  cvttsd2si edx, xmm7
0x180007130  mov     [rsi+rax*2], dx
0x180007134  mov     eax, 10h
0x180007139  mov     ecx, [rdi+28h]
0x18000713c  sar     eax, cl
0x18000713e  cmp     r10d, eax
0x180007141  jl      loc_180007050
0x180007147  jmp     loc_180007263
0x18000714c  cmp     eax, 1
0x18000714f  jle     loc_180007263
0x180007155  mov     r10d, 1
0x18000715b  nop     dword ptr [rax+rax+00h]
0x180007160  mov     r11, [rdi+8]
0x180007164  mov     eax, 20h ; ' '
0x180007169  shl     eax, cl
0x18000716b  mov     edx, 1
0x180007170  rol     edx, cl
0x180007172  sub     eax, 20h ; ' '
0x180007175  imul    edx, r10d
0x180007179  xor     r8d, r8d
0x18000717c  cdqe
0x18000717e  xorps   xmm7, xmm7
0x180007181  xorps   xmm6, xmm6
0x180007184  lea     r9, [r9+rax*4]
0x180007188  add     edx, ebp
0x18000718a  nop     word ptr [rax+rax+00h]
0x180007190  lea     eax, [rdx+r8]
0x180007194  add     r8d, 40h ; '@'
0x180007198  movsxd  rcx, eax
0x18000719b  lea     rax, [rcx+20h]
0x18000719f  and     eax, 1FFh
0x1800071a4  movss   xmm4, dword ptr [r11+rax*4]
0x1800071aa  lea     rax, [rcx+10h]
0x1800071ae  movaps  xmm1, xmm4
0x1800071b1  and     eax, 1FFh
0x1800071b6  mulss   xmm1, dword ptr [r9+8]
0x1800071bc  mulss   xmm4, dword ptr [r9+0Ch]
0x1800071c2  movss   xmm3, dword ptr [r11+rax*4]
0x1800071c8  movaps  xmm0, xmm3
0x1800071cb  mulss   xmm3, dword ptr [r9+4]
0x1800071d1  mulss   xmm0, dword ptr [r9]
0x1800071d6  add     r9, 10h
0x1800071da  cvtps2pd xmm2, xmm0
0x1800071dd  cvtps2pd xmm0, xmm1
0x1800071e0  addsd   xmm6, xmm2
0x1800071e4  cvtps2pd xmm1, xmm3
0x1800071e7  addsd   xmm6, xmm0
0x1800071eb  addsd   xmm7, xmm1
0x1800071ef  cvtps2pd xmm0, xmm4
0x1800071f2  addsd   xmm7, xmm0
0x1800071f6  cmp     r8d, 200h
0x1800071fd  jl      short loc_180007190
0x1800071ff  comisd  xmm5, xmm6
0x180007203  jbe     short loc_18000720C
0x180007205  maxsd   xmm6, xmm8
0x18000720a  jmp     short loc_18000720F
0x18000720c  movaps  xmm6, xmm5
0x18000720f  cvttsd2si ecx, xmm6
0x180007213  movsxd  rax, r10d
0x180007216  sar     cx, 8
0x18000721a  add     cl, 80h
0x18000721d  comisd  xmm5, xmm7
0x180007221  mov     [rax+rsi], cl
0x180007224  jbe     short loc_18000722D
0x180007226  maxsd   xmm7, xmm8
0x18000722b  jmp     short loc_180007230
0x18000722d  movaps  xmm7, xmm5
0x180007230  mov     ecx, [rdi+28h]
0x180007233  mov     eax, 20h ; ' '
0x180007238  sar     eax, cl
0x18000723a  sub     eax, r10d
0x18000723d  inc     r10d
0x180007240  cdqe
0x180007242  cvttsd2si edx, xmm7
0x180007246  sar     dx, 8
0x18000724a  add     dl, 80h
0x18000724d  mov     [rax+rsi], dl
0x180007250  mov     eax, 10h
0x180007255  mov     ecx, [rdi+28h]
0x180007258  sar     eax, cl
0x18000725a  cmp     r10d, eax
0x18000725d  jl      loc_180007160
0x180007263  movaps  xmm8, [rsp+38h+var_38]
0x180007268  movaps  xmm7, [rsp+38h+var_28]
0x18000726d  movaps  xmm6, [rsp+38h+var_18]
0x180007272  mov     rbp, [rsp+38h+arg_8]
0x180007277  mov     rsi, [rsp+38h+arg_10]
0x18000727c  add     rsp, 30h
0x180007280  pop     rdi
0x180007281  retn
```
