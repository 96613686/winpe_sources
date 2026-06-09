# CPolyphase::window_band_s(int,short *,int)

- ea: `0x180007290`
- end: `0x1800078c5`
- name: `?window_band_s@CPolyphase@@IEAAXHPEAFH@Z`
- size: `1589`
- prototype: `void __fastcall(CPolyphase *__hidden this, int, __int16 *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005be0`

## callees

- `0x180007290`

## pseudocode

```c
void __fastcall CPolyphase::window_band_s(CPolyphase *this, int a2, __int16 *a3)
{
  __int64 v3; // r11
  float *v4; // r9
  __int64 v5; // rbx
  int v6; // esi
  double v8; // xmm6_8
  double v9; // xmm7_8
  double v10; // xmm8_8
  double v11; // xmm5_8
  int v12; // edi
  __int64 v13; // rax
  __int64 v14; // rcx
  float v15; // xmm4_4
  float v16; // xmm3_4
  double v17; // xmm2_8
  double v18; // xmm0_8
  float v19; // xmm1_4
  double v20; // xmm5_8
  double v21; // xmm7_8
  double v22; // xmm6_8
  double v23; // xmm8_8
  double v24; // xmm5_8
  double v25; // xmm7_8
  double v26; // xmm6_8
  double v27; // xmm8_8
  int v28; // ecx
  int v29; // eax
  int v30; // r11d
  __int64 v31; // rdx
  __int64 v32; // rbx
  double v33; // xmm14_8
  double v34; // xmm13_8
  double v35; // xmm12_8
  double v36; // xmm11_8
  int v37; // eax
  int v38; // edi
  int v39; // ecx
  float v40; // xmm8_4
  float v41; // xmm0_4
  __int64 v42; // rax
  float v43; // xmm7_4
  double v44; // xmm11_8
  float v45; // xmm1_4
  float v46; // xmm6_4
  double v47; // xmm0_8
  float v48; // xmm1_4
  float v49; // xmm5_4
  float v50; // xmm1_4
  float v51; // xmm8_4
  double v52; // xmm11_8
  __int64 v53; // rbx
  double v54; // xmm12_8
  double v55; // xmm13_8
  double v56; // xmm14_8
  int v57; // eax
  int v58; // r11d
  __int64 v59; // rdx
  __int64 v60; // rbx
  double v61; // xmm14_8
  double v62; // xmm13_8
  double v63; // xmm12_8
  double v64; // xmm11_8
  int v65; // eax
  int v66; // edi
  int v67; // ecx
  float v68; // xmm4_4
  float v69; // xmm3_4
  float v70; // xmm8_4
  float v71; // xmm0_4
  __int64 v72; // rax
  float v73; // xmm7_4
  float v74; // xmm0_4
  float v75; // xmm8_4
  float v76; // xmm0_4
  double v77; // xmm11_8
  __int64 v78; // rbx
  double v79; // xmm12_8
  double v80; // xmm13_8
  double v81; // xmm14_8
  int v82; // eax

  v3 = *((_QWORD *)this + 1);
  v4 = (float *)qword_180013910;
  v5 = *((_QWORD *)this + 2);
  v6 = a2;
  v8 = 0.0;
  v9 = 0.0;
  v10 = 0.0;
  v11 = 0.0;
  v12 = 8;
  do
  {
    v13 = ((_WORD)a2 + 32) & 0x1FF;
    v14 = a2;
    a2 = ((((_WORD)a2 + 32) & 0x1FF) + 32) & 0x1FF;
    v15 = *v4 * *(float *)(v5 + 4 * v14 + 64);
    v16 = v4[2] * *(float *)(v5 + 4 * v13 + 64);
    v17 = (float)(*v4 * *(float *)(v3 + 4 * v14 + 64));
    v18 = (float)(v4[2] * *(float *)(v3 + 4 * v13 + 64));
    v19 = v4[3];
    v4 += 4;
    v11 = v11 + v17 + v18;
    v8 = v8 + v15 + v16;
    v9 = v9 + (float)(v19 * *(float *)(v3 + 4 * v13));
    v10 = v10 + (float)(v19 * *(float *)(v5 + 4 * v13));
    --v12;
  }
  while ( v12 );
  if ( *((_DWORD *)this + 11) )
  {
    if ( v11 >= 32767.0 )
      v24 = DOUBLE_32767_0;
    else
      v24 = fmax(v11, -32767.0);
    *(_BYTE *)a3 = ((unsigned __int16)(int)v24 >> 8) + 0x80;
    if ( v9 >= 32767.0 )
      v25 = DOUBLE_32767_0;
    else
      v25 = fmax(v9, -32767.0);
    *((_BYTE *)a3 + (32LL >> *((_DWORD *)this + 10))) = ((unsigned __int16)(int)v25 >> 8) + 0x80;
    if ( v8 >= 32767.0 )
      v26 = DOUBLE_32767_0;
    else
      v26 = fmax(v8, -32767.0);
    *((_BYTE *)a3 + 1) = ((unsigned __int16)(int)v26 >> 8) + 0x80;
    if ( v10 >= 32767.0 )
      v27 = DOUBLE_32767_0;
    else
      v27 = fmax(v10, -32767.0);
    *((_BYTE *)a3 + (32LL >> *((_DWORD *)this + 10)) + 1) = ((unsigned __int16)(int)v27 >> 8) + 0x80;
  }
  else
  {
    if ( v11 >= 32767.0 )
      v20 = DOUBLE_32767_0;
    else
      v20 = fmax(v11, -32767.0);
    *a3 = (int)v20;
    if ( v9 >= 32767.0 )
      v21 = DOUBLE_32767_0;
    else
      v21 = fmax(v9, -32767.0);
    a3[32LL >> *((_DWORD *)this + 10)] = (int)v21;
    if ( v8 >= 32767.0 )
      v22 = DOUBLE_32767_0;
    else
      v22 = fmax(v8, -32767.0);
    a3[1] = (int)v22;
    if ( v10 >= 32767.0 )
      v23 = DOUBLE_32767_0;
    else
      v23 = fmax(v10, -32767.0);
    a3[(32LL >> *((_DWORD *)this + 10)) + 1] = (int)v23;
  }
  v28 = *((_DWORD *)this + 10);
  v29 = 16 >> v28;
  if ( *((_DWORD *)this + 11) )
  {
    if ( v29 > 1 )
    {
      v58 = 1;
      do
      {
        v59 = *((_QWORD *)this + 1);
        v60 = *((_QWORD *)this + 2);
        v61 = 0.0;
        v62 = 0.0;
        v63 = 0.0;
        v64 = 0.0;
        v65 = 32 * (1 << v28);
        v66 = 8;
        v67 = v6 + v58 * (1 << v28);
        v4 += v65 - 32;
        do
        {
          v68 = v4[2];
          v69 = v4[3];
          v70 = *(float *)(v60 + 4LL * v67 + 64);
          v71 = *(float *)(v59 + 4LL * v67 + 64);
          v72 = ((_WORD)v67 + 32) & 0x1FF;
          v73 = v71 * v4[1];
          v67 = ((((_WORD)v67 + 32) & 0x1FF) + 32) & 0x1FF;
          v64 = v64 + (float)(v71 * *v4) + (float)(*(float *)(v59 + 4 * v72) * v68);
          v74 = v70;
          v75 = v70 * v4[1];
          v76 = v74 * *v4;
          v4 += 4;
          v62 = v62 + v76 + (float)(v68 * *(float *)(v60 + 4 * v72));
          v63 = v63 + v73 + (float)(*(float *)(v59 + 4 * v72) * v69);
          v61 = v61 + v75 + (float)(v69 * *(float *)(v60 + 4 * v72));
          --v66;
        }
        while ( v66 );
        if ( v64 >= 32767.0 )
          v77 = DOUBLE_32767_0;
        else
          v77 = fmax(v64, -32767.0);
        v78 = v58;
        LOBYTE(a3[v78]) = ((unsigned __int16)(int)v77 >> 8) + 0x80;
        if ( v63 >= 32767.0 )
          v79 = DOUBLE_32767_0;
        else
          v79 = fmax(v63, -32767.0);
        LOBYTE(a3[(32 >> *((_DWORD *)this + 10)) - v58]) = ((unsigned __int16)(int)v79 >> 8) + 0x80;
        if ( v62 >= 32767.0 )
          v80 = DOUBLE_32767_0;
        else
          v80 = fmax(v62, -32767.0);
        HIBYTE(a3[v78]) = ((unsigned __int16)(int)v80 >> 8) + 0x80;
        if ( v61 >= 32767.0 )
          v81 = DOUBLE_32767_0;
        else
          v81 = fmax(v61, -32767.0);
        v82 = (32 >> *((_DWORD *)this + 10)) - v58++;
        HIBYTE(a3[v82]) = ((unsigned __int16)(int)v81 >> 8) + 0x80;
        v28 = *((_DWORD *)this + 10);
      }
      while ( v58 < 16 >> v28 );
    }
  }
  else if ( v29 > 1 )
  {
    v30 = 1;
    do
    {
      v31 = *((_QWORD *)this + 1);
      v32 = *((_QWORD *)this + 2);
      v33 = 0.0;
      v34 = 0.0;
      v35 = 0.0;
      v36 = 0.0;
      v37 = 32 * (1 << v28);
      v38 = 8;
      v39 = v6 + v30 * (1 << v28);
      v4 += v37 - 32;
      do
      {
        v40 = *(float *)(v32 + 4LL * v39 + 64);
        v41 = *(float *)(v31 + 4LL * v39 + 64) * *v4;
        v42 = ((_WORD)v39 + 32) & 0x1FF;
        v43 = *(float *)(v31 + 4LL * v39 + 64) * v4[1];
        v39 = ((((_WORD)v39 + 32) & 0x1FF) + 32) & 0x1FF;
        v44 = v36 + v41;
        v45 = *(float *)(v31 + 4 * v42);
        v46 = v45 * v4[3];
        v47 = (float)(v45 * v4[2]);
        v48 = *(float *)(v32 + 4 * v42);
        v49 = v48 * v4[3];
        v50 = v48 * v4[2];
        v36 = v44 + v47;
        *(float *)&v47 = v40;
        v51 = v40 * v4[1];
        *(float *)&v47 = *(float *)&v47 * *v4;
        v4 += 4;
        v34 = v34 + *(float *)&v47 + v50;
        v35 = v35 + v43 + v46;
        v33 = v33 + v51 + v49;
        --v38;
      }
      while ( v38 );
      if ( v36 >= 32767.0 )
        v52 = DOUBLE_32767_0;
      else
        v52 = fmax(v36, -32767.0);
      v53 = 2 * v30;
      a3[v53] = (int)v52;
      if ( v35 >= 32767.0 )
        v54 = DOUBLE_32767_0;
      else
        v54 = fmax(v35, -32767.0);
      a3[2 * ((32 >> *((_DWORD *)this + 10)) - v30)] = (int)v54;
      if ( v34 >= 32767.0 )
        v55 = DOUBLE_32767_0;
      else
        v55 = fmax(v34, -32767.0);
      a3[v53 + 1] = (int)v55;
      if ( v33 >= 32767.0 )
        v56 = DOUBLE_32767_0;
      else
        v56 = fmax(v33, -32767.0);
      v57 = (32 >> *((_DWORD *)this + 10)) - v30++;
      a3[2 * v57 + 1] = (int)v56;
      v28 = *((_DWORD *)this + 10);
    }
    while ( v30 < 16 >> v28 );
  }
}

```

## disassembly

```asm
0x180007290  mov     rax, rsp
0x180007293  mov     [rax+8], rbx
0x180007297  mov     [rax+10h], rsi
0x18000729b  push    rdi
0x18000729c  sub     rsp, 90h
0x1800072a3  mov     r11, [rcx+8]
0x1800072a7  lea     r9, qword_180013910
0x1800072ae  mov     rbx, [rcx+10h]
0x1800072b2  mov     esi, edx
0x1800072b4  movaps  xmmword ptr [rax-18h], xmm6
0x1800072b8  mov     r10, rcx
0x1800072bb  movaps  xmmword ptr [rax-28h], xmm7
0x1800072bf  xorps   xmm6, xmm6
0x1800072c2  movaps  xmmword ptr [rax-38h], xmm8
0x1800072c7  xorps   xmm7, xmm7
0x1800072ca  xorps   xmm8, xmm8
0x1800072ce  xorps   xmm5, xmm5
0x1800072d1  mov     edi, 8
0x1800072d6  nop     word ptr [rax+rax+00000000h]
0x1800072e0  movss   xmm4, dword ptr [r9]
0x1800072e5  lea     eax, [rdx+20h]
0x1800072e8  movss   xmm3, dword ptr [r9+8]
0x1800072ee  and     eax, 1FFh
0x1800072f3  movsxd  rcx, edx
0x1800072f6  movaps  xmm0, xmm4
0x1800072f9  movaps  xmm1, xmm3
0x1800072fc  mov     edx, eax
0x1800072fe  add     edx, 20h ; ' '
0x180007301  mulss   xmm1, dword ptr [r11+rax*4+40h]
0x180007308  and     edx, 1FFh
0x18000730e  mulss   xmm0, dword ptr [r11+rcx*4+40h]
0x180007315  mulss   xmm4, dword ptr [rbx+rcx*4+40h]
0x18000731b  mulss   xmm3, dword ptr [rbx+rax*4+40h]
0x180007321  cvtps2pd xmm2, xmm0
0x180007324  cvtps2pd xmm0, xmm1
0x180007327  cvtps2pd xmm1, xmm4
0x18000732a  addsd   xmm5, xmm2
0x18000732e  addsd   xmm6, xmm1
0x180007332  movss   xmm1, dword ptr [r9+0Ch]
0x180007338  add     r9, 10h
0x18000733c  addsd   xmm5, xmm0
0x180007340  cvtps2pd xmm0, xmm3
0x180007343  addsd   xmm6, xmm0
0x180007347  movaps  xmm0, xmm1
0x18000734a  mulss   xmm0, dword ptr [r11+rax*4]
0x180007350  mulss   xmm1, dword ptr [rbx+rax*4]
0x180007355  cvtps2pd xmm0, xmm0
0x180007358  addsd   xmm7, xmm0
0x18000735c  cvtps2pd xmm0, xmm1
0x18000735f  addsd   xmm8, xmm0
0x180007364  sub     edi, 1
0x180007367  jnz     loc_1800072E0
0x18000736d  movaps  [rsp+98h+var_48], xmm9
0x180007373  movsd   xmm9, cs:__real@40dfffc000000000
0x18000737c  movaps  [rsp+98h+var_58], xmm10
0x180007382  movsd   xmm10, cs:__real@c0dfffc000000000
0x18000738b  cmp     [r10+2Ch], edi
0x18000738f  jnz     loc_18000741F
0x180007395  comisd  xmm9, xmm5
0x18000739a  jbe     short loc_1800073A3
0x18000739c  maxsd   xmm5, xmm10
0x1800073a1  jmp     short loc_1800073A7
0x1800073a3  movaps  xmm5, xmm9
0x1800073a7  comisd  xmm9, xmm7
0x1800073ac  cvttsd2si eax, xmm5
0x1800073b0  mov     [r8], ax
0x1800073b4  jbe     short loc_1800073BD
0x1800073b6  maxsd   xmm7, xmm10
0x1800073bb  jmp     short loc_1800073C1
0x1800073bd  movaps  xmm7, xmm9
0x1800073c1  mov     ecx, [r10+28h]
0x1800073c5  mov     eax, 20h ; ' '
0x1800073ca  sar     rax, cl
0x1800073cd  comisd  xmm9, xmm6
0x1800073d2  cvttsd2si edx, xmm7
0x1800073d6  mov     [r8+rax*2], dx
0x1800073db  jbe     short loc_1800073E4
0x1800073dd  maxsd   xmm6, xmm10
0x1800073e2  jmp     short loc_1800073E8
0x1800073e4  movaps  xmm6, xmm9
0x1800073e8  comisd  xmm9, xmm8
0x1800073ed  cvttsd2si eax, xmm6
0x1800073f1  mov     [r8+2], ax
0x1800073f6  jbe     short loc_1800073FF
0x1800073f8  maxsd   xmm8, xmm10
0x1800073fd  jmp     short loc_180007403
0x1800073ff  movaps  xmm8, xmm9
0x180007403  mov     ecx, [r10+28h]
0x180007407  mov     eax, 20h ; ' '
0x18000740c  cvttsd2si edx, xmm8
0x180007411  sar     rax, cl
0x180007414  mov     [r8+rax*2+2], dx
0x18000741a  jmp     loc_1800074BA
0x18000741f  comisd  xmm9, xmm5
0x180007424  jbe     short loc_18000742D
0x180007426  maxsd   xmm5, xmm10
0x18000742b  jmp     short loc_180007431
0x18000742d  movaps  xmm5, xmm9
0x180007431  cvttsd2si eax, xmm5
0x180007435  sar     ax, 8
0x180007439  add     al, 80h
0x18000743b  comisd  xmm9, xmm7
0x180007440  mov     [r8], al
0x180007443  jbe     short loc_18000744C
0x180007445  maxsd   xmm7, xmm10
0x18000744a  jmp     short loc_180007450
0x18000744c  movaps  xmm7, xmm9
0x180007450  mov     ecx, [r10+28h]
0x180007454  mov     eax, 20h ; ' '
0x180007459  sar     rax, cl
0x18000745c  cvttsd2si edx, xmm7
0x180007460  sar     dx, 8
0x180007464  add     dl, 80h
0x180007467  comisd  xmm9, xmm6
0x18000746c  mov     [rax+r8], dl
0x180007470  jbe     short loc_180007479
0x180007472  maxsd   xmm6, xmm10
0x180007477  jmp     short loc_18000747D
0x180007479  movaps  xmm6, xmm9
0x18000747d  cvttsd2si eax, xmm6
0x180007481  sar     ax, 8
0x180007485  add     al, 80h
0x180007487  comisd  xmm9, xmm8
0x18000748c  mov     [r8+1], al
0x180007490  jbe     short loc_180007499
0x180007492  maxsd   xmm8, xmm10
0x180007497  jmp     short loc_18000749D
0x180007499  movaps  xmm8, xmm9
0x18000749d  mov     ecx, [r10+28h]
0x1800074a1  mov     eax, 20h ; ' '
0x1800074a6  cvttsd2si edx, xmm8
0x1800074ab  sar     dx, 8
0x1800074af  add     dl, 80h
0x1800074b2  sar     rax, cl
0x1800074b5  mov     [rax+r8+1], dl
0x1800074ba  mov     ecx, [r10+28h]
0x1800074be  mov     eax, 10h
0x1800074c3  movaps  [rsp+98h+var_68], xmm11
0x1800074c9  movaps  [rsp+98h+var_78], xmm12
0x1800074cf  sar     eax, cl
0x1800074d1  cmp     dword ptr [r10+2Ch], 0
0x1800074d6  movaps  [rsp+98h+var_88], xmm13
0x1800074dc  movaps  [rsp+98h+var_98], xmm14
0x1800074e1  jnz     loc_1800076AF
0x1800074e7  cmp     eax, 1
0x1800074ea  jle     loc_18000787E
0x1800074f0  mov     r11d, 1
0x1800074f6  nop     word ptr [rax+rax+00000000h]
0x180007500  mov     rdx, [r10+8]
0x180007504  mov     eax, 1
0x180007509  mov     rbx, [r10+10h]
0x18000750d  xorps   xmm14, xmm14
0x180007511  shl     eax, cl
0x180007513  xorps   xmm13, xmm13
0x180007517  mov     ecx, eax
0x180007519  xorps   xmm12, xmm12
0x18000751d  imul    ecx, r11d
0x180007521  xorps   xmm11, xmm11
0x180007525  shl     eax, 5
0x180007528  mov     edi, 8
0x18000752d  add     ecx, esi
0x18000752f  sub     eax, 20h ; ' '
0x180007532  cdqe
0x180007534  lea     r9, [r9+rax*4]
0x180007538  nop     dword ptr [rax+rax+00000000h]
0x180007540  movsxd  rax, ecx
0x180007543  movss   xmm7, dword ptr [rdx+rax*4+40h]
0x180007549  movss   xmm8, dword ptr [rbx+rax*4+40h]
0x180007550  movaps  xmm0, xmm7
0x180007553  mulss   xmm0, dword ptr [r9]
0x180007558  lea     eax, [rcx+20h]
0x18000755b  and     eax, 1FFh
0x180007560  mulss   xmm7, dword ptr [r9+4]
0x180007566  mov     ecx, eax
0x180007568  cvtps2pd xmm2, xmm0
0x18000756b  add     ecx, 20h ; ' '
0x18000756e  and     ecx, 1FFh
0x180007574  movss   xmm6, dword ptr [rdx+rax*4]
0x180007579  movss   xmm5, dword ptr [rbx+rax*4]
0x18000757e  addsd   xmm11, xmm2
0x180007583  movaps  xmm1, xmm6
0x180007586  mulss   xmm6, dword ptr [r9+0Ch]
0x18000758c  mulss   xmm1, dword ptr [r9+8]
0x180007592  cvtps2pd xmm0, xmm1
0x180007595  movaps  xmm1, xmm5
0x180007598  mulss   xmm5, dword ptr [r9+0Ch]
0x18000759e  mulss   xmm1, dword ptr [r9+8]
0x1800075a4  addsd   xmm11, xmm0
0x1800075a9  movaps  xmm0, xmm8
0x1800075ad  mulss   xmm8, dword ptr [r9+4]
0x1800075b3  mulss   xmm0, dword ptr [r9]
0x1800075b8  add     r9, 10h
0x1800075bc  cvtps2pd xmm2, xmm0
0x1800075bf  cvtps2pd xmm0, xmm1
0x1800075c2  addsd   xmm13, xmm2
0x1800075c7  cvtps2pd xmm1, xmm7
0x1800075ca  addsd   xmm13, xmm0
0x1800075cf  addsd   xmm12, xmm1
0x1800075d4  cvtps2pd xmm0, xmm6
0x1800075d7  cvtps2pd xmm1, xmm8
0x1800075db  addsd   xmm12, xmm0
0x1800075e0  addsd   xmm14, xmm1
0x1800075e5  cvtps2pd xmm0, xmm5
0x1800075e8  addsd   xmm14, xmm0
0x1800075ed  sub     edi, 1
0x1800075f0  jnz     loc_180007540
0x1800075f6  comisd  xmm9, xmm11
0x1800075fb  jbe     short loc_180007604
0x1800075fd  maxsd   xmm11, xmm10
0x180007602  jmp     short loc_180007608
0x180007604  movaps  xmm11, xmm9
0x180007608  comisd  xmm9, xmm12
0x18000760d  lea     eax, [r11+r11]
0x180007611  movsxd  rbx, eax
0x180007614  cvttsd2si eax, xmm11
0x180007619  mov     [r8+rbx*2], ax
0x18000761e  jbe     short loc_180007627
0x180007620  maxsd   xmm12, xmm10
0x180007625  jmp     short loc_18000762B
0x180007627  movaps  xmm12, xmm9
0x18000762b  mov     ecx, [r10+28h]
0x18000762f  mov     eax, 20h ; ' '
0x180007634  sar     eax, cl
0x180007636  sub     eax, r11d
0x180007639  add     eax, eax
0x18000763b  comisd  xmm9, xmm13
0x180007640  cdqe
0x180007642  cvttsd2si edx, xmm12
0x180007647  mov     [r8+rax*2], dx
0x18000764c  jbe     short loc_180007655
0x18000764e  maxsd   xmm13, xmm10
0x180007653  jmp     short loc_180007659
0x180007655  movaps  xmm13, xmm9
0x180007659  comisd  xmm9, xmm14
0x18000765e  cvttsd2si eax, xmm13
0x180007663  mov     [r8+rbx*2+2], ax
0x180007669  jbe     short loc_180007672
0x18000766b  maxsd   xmm14, xmm10
0x180007670  jmp     short loc_180007676
0x180007672  movaps  xmm14, xmm9
0x180007676  mov     ecx, [r10+28h]
0x18000767a  mov     eax, 20h ; ' '
0x18000767f  sar     eax, cl
0x180007681  sub     eax, r11d
0x180007684  inc     r11d
0x180007687  add     eax, eax
0x180007689  cdqe
0x18000768b  cvttsd2si edx, xmm14
0x180007690  mov     [r8+rax*2+2], dx
0x180007696  mov     eax, 10h
0x18000769b  mov     ecx, [r10+28h]
0x18000769f  sar     eax, cl
0x1800076a1  cmp     r11d, eax
0x1800076a4  jl      loc_180007500
0x1800076aa  jmp     loc_18000787E
0x1800076af  cmp     eax, 1
0x1800076b2  jle     loc_18000787E
0x1800076b8  mov     r11d, 1
0x1800076be  xchg    ax, ax
0x1800076c0  mov     rdx, [r10+8]
0x1800076c4  mov     eax, 1
0x1800076c9  mov     rbx, [r10+10h]
0x1800076cd  xorps   xmm14, xmm14
0x1800076d1  shl     eax, cl
0x1800076d3  xorps   xmm13, xmm13
0x1800076d7  mov     ecx, eax
0x1800076d9  xorps   xmm12, xmm12
0x1800076dd  imul    ecx, r11d
0x1800076e1  xorps   xmm11, xmm11
0x1800076e5  shl     eax, 5
0x1800076e8  mov     edi, 8
0x1800076ed  add     ecx, esi
0x1800076ef  sub     eax, 20h ; ' '
0x1800076f2  cdqe
0x1800076f4  lea     r9, [r9+rax*4]
0x1800076f8  nop     dword ptr [rax+rax+00000000h]
0x180007700  movss   xmm4, dword ptr [r9+8]
0x180007706  movss   xmm3, dword ptr [r9+0Ch]
0x18000770c  movsxd  rax, ecx
0x18000770f  movss   xmm7, dword ptr [rdx+rax*4+40h]
0x180007715  movss   xmm8, dword ptr [rbx+rax*4+40h]
0x18000771c  movaps  xmm0, xmm7
0x18000771f  mulss   xmm0, dword ptr [r9]
0x180007724  lea     eax, [rcx+20h]
0x180007727  and     eax, 1FFh
0x18000772c  mulss   xmm7, dword ptr [r9+4]
0x180007732  mov     ecx, eax
0x180007734  cvtps2pd xmm2, xmm0
0x180007737  add     ecx, 20h ; ' '
0x18000773a  and     ecx, 1FFh
0x180007740  movss   xmm6, dword ptr [rdx+rax*4]
0x180007745  movaps  xmm1, xmm6
0x180007748  addsd   xmm11, xmm2
0x18000774d  mulss   xmm1, xmm4
0x180007751  mulss   xmm4, dword ptr [rbx+rax*4]
0x180007756  cvtps2pd xmm0, xmm1
0x180007759  mulss   xmm6, xmm3
0x18000775d  mulss   xmm3, dword ptr [rbx+rax*4]
0x180007762  addsd   xmm11, xmm0
0x180007767  movaps  xmm0, xmm8
  ... truncated ...
```
