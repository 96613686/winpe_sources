# CErrorConcealment::ran3(long *)

- ea: `0x180010440`
- end: `0x180010bb5`
- name: `?ran3@CErrorConcealment@@IEAAMPEAJ@Z`
- size: `1909`
- prototype: `float __fastcall(CErrorConcealment *__hidden this, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000fbe0`

## callees

- `0x180010440`

## pseudocode

```c
float __fastcall CErrorConcealment::ran3(CErrorConcealment *this, int *a2)
{
  int v3; // ebx
  int v4; // r10d
  int v5; // ecx
  int v6; // esi
  int v7; // edi
  int v8; // edi
  int v9; // r9d
  int v10; // r10d
  int v11; // r8d
  int v12; // r9d
  int v13; // r10d
  int v14; // r8d
  int v15; // r9d
  int v16; // r10d
  int v17; // r8d
  int v18; // r9d
  int v19; // r10d
  int v20; // r8d
  int v21; // r9d
  int v22; // r10d
  int v23; // r8d
  int v24; // r9d
  int v25; // r10d
  int v26; // r8d
  int v27; // r9d
  int v28; // r10d
  int v29; // r8d
  int v30; // r9d
  int v31; // r10d
  int v32; // r8d
  int v33; // r9d
  int v34; // r10d
  int v35; // r8d
  int v36; // r9d
  int v37; // r10d
  int v38; // r8d
  int v39; // r9d
  int v40; // r10d
  int v41; // ecx
  int v42; // r9d
  int v43; // ecx
  int v44; // r10d
  int v45; // r9d
  __int64 v46; // r8
  int v47; // ecx
  bool v48; // sf
  int v49; // ecx
  int v50; // ecx
  int v51; // ecx
  int v52; // ecx
  int v53; // ecx
  int v54; // ecx
  int v55; // ecx
  int v56; // ecx
  int v57; // ecx
  int v58; // ecx
  int v59; // eax
  __int64 v60; // rdx
  int v61; // ecx
  int v62; // eax

  v3 = 1;
  if ( *a2 < 0 || !*((_DWORD *)this + 6330) )
  {
    *((_DWORD *)this + 6330) = 1;
    v4 = 1;
    v5 = -*a2;
    v6 = 1;
    if ( *a2 > 0 )
      v5 = *a2;
    v7 = (161803398 - v5) % 1000000000;
    *((_DWORD *)this + 6329) = v7;
    do
    {
      v8 = v7 - v4;
      *((_DWORD *)this + 21 * v6 % 55 + 6274) = v4;
      v9 = v8 + 1000000000;
      if ( v8 >= 0 )
        v9 = v8;
      v10 = v4 - v9;
      *((_DWORD *)this + (21 * v6 + 21) % 55 + 6274) = v9;
      v11 = v10 + 1000000000;
      if ( v10 >= 0 )
        v11 = v10;
      v12 = v9 - v11;
      *((_DWORD *)this + 21 * (v6 + 2) % 55 + 6274) = v11;
      v13 = v12 + 1000000000;
      if ( v12 >= 0 )
        v13 = v12;
      v14 = v11 - v13;
      *((_DWORD *)this + 21 * (v6 + 3) % 55 + 6274) = v13;
      v15 = v14 + 1000000000;
      if ( v14 >= 0 )
        v15 = v14;
      v16 = v13 - v15;
      *((_DWORD *)this + 21 * (v6 + 4) % 55 + 6274) = v15;
      v17 = v16 + 1000000000;
      if ( v16 >= 0 )
        v17 = v16;
      v18 = v15 - v17;
      *((_DWORD *)this + 21 * (v6 + 5) % 55 + 6274) = v17;
      v19 = v18 + 1000000000;
      if ( v18 >= 0 )
        v19 = v18;
      v20 = v17 - v19;
      *((_DWORD *)this + 21 * (v6 + 6) % 55 + 6274) = v19;
      v21 = v20 + 1000000000;
      if ( v20 >= 0 )
        v21 = v20;
      v22 = v19 - v21;
      *((_DWORD *)this + 21 * (v6 + 7) % 55 + 6274) = v21;
      v23 = v22 + 1000000000;
      if ( v22 >= 0 )
        v23 = v22;
      v24 = v21 - v23;
      *((_DWORD *)this + 21 * (v6 + 8) % 55 + 6274) = v23;
      v25 = v24 + 1000000000;
      if ( v24 >= 0 )
        v25 = v24;
      v26 = v23 - v25;
      *((_DWORD *)this + 21 * (v6 + 9) % 55 + 6274) = v25;
      v27 = v26 + 1000000000;
      if ( v26 >= 0 )
        v27 = v26;
      v28 = v25 - v27;
      *((_DWORD *)this + 21 * (v6 + 10) % 55 + 6274) = v27;
      v29 = v28 + 1000000000;
      if ( v28 >= 0 )
        v29 = v28;
      v30 = v27 - v29;
      *((_DWORD *)this + 21 * (v6 + 11) % 55 + 6274) = v29;
      v31 = v30 + 1000000000;
      if ( v30 >= 0 )
        v31 = v30;
      v32 = v29 - v31;
      *((_DWORD *)this + 21 * (v6 + 12) % 55 + 6274) = v31;
      v33 = v32 + 1000000000;
      if ( v32 >= 0 )
        v33 = v32;
      v34 = v31 - v33;
      *((_DWORD *)this + 21 * (v6 + 13) % 55 + 6274) = v33;
      v35 = v34 + 1000000000;
      if ( v34 >= 0 )
        v35 = v34;
      v36 = v33 - v35;
      *((_DWORD *)this + 21 * (v6 + 14) % 55 + 6274) = v35;
      v37 = v36 + 1000000000;
      if ( v36 >= 0 )
        v37 = v36;
      v38 = v35 - v37;
      *((_DWORD *)this + 21 * (v6 + 15) % 55 + 6274) = v37;
      v39 = v38 + 1000000000;
      if ( v38 >= 0 )
        v39 = v38;
      v40 = v37 - v39;
      *((_DWORD *)this + 21 * (v6 + 16) % 55 + 6274) = v39;
      v7 = v40 + 1000000000;
      if ( v40 >= 0 )
        v7 = v40;
      v41 = 21 * (v6 + 17);
      v42 = v39 - v7;
      v6 += 18;
      v4 = v42 + 1000000000;
      v43 = v41 % 55;
      if ( v42 >= 0 )
        v4 = v42;
      *((_DWORD *)this + v43 + 6274) = v7;
    }
    while ( v6 <= 54 );
    v44 = 4;
    do
    {
      v45 = 1;
      v46 = 1;
      do
      {
        v47 = *((_DWORD *)this + (v45 + 30) % 55 + 6275);
        v48 = *((_DWORD *)this + v46 + 6274) - v47 < 0;
        *((_DWORD *)this + v46 + 6274) -= v47;
        if ( v48 )
          *((_DWORD *)this + v46 + 6274) += 1000000000;
        v49 = *((_DWORD *)this + (v45 + 31) % 55 + 6275);
        v48 = *((_DWORD *)this + v46 + 6275) - v49 < 0;
        *((_DWORD *)this + v46 + 6275) -= v49;
        if ( v48 )
          *((_DWORD *)this + v46 + 6275) += 1000000000;
        v50 = *((_DWORD *)this + (v45 + 32) % 55 + 6275);
        v48 = *((_DWORD *)this + v46 + 6276) - v50 < 0;
        *((_DWORD *)this + v46 + 6276) -= v50;
        if ( v48 )
          *((_DWORD *)this + v46 + 6276) += 1000000000;
        v51 = *((_DWORD *)this + (v45 + 33) % 55 + 6275);
        v48 = *((_DWORD *)this + v46 + 6277) - v51 < 0;
        *((_DWORD *)this + v46 + 6277) -= v51;
        if ( v48 )
          *((_DWORD *)this + v46 + 6277) += 1000000000;
        v52 = *((_DWORD *)this + (v45 + 34) % 55 + 6275);
        v48 = *((_DWORD *)this + v46 + 6278) - v52 < 0;
        *((_DWORD *)this + v46 + 6278) -= v52;
        if ( v48 )
          *((_DWORD *)this + v46 + 6278) += 1000000000;
        v53 = *((_DWORD *)this + (v45 + 35) % 55 + 6275);
        v48 = *((_DWORD *)this + v46 + 6279) - v53 < 0;
        *((_DWORD *)this + v46 + 6279) -= v53;
        if ( v48 )
          *((_DWORD *)this + v46 + 6279) += 1000000000;
        v54 = *((_DWORD *)this + (v45 + 36) % 55 + 6275);
        v48 = *((_DWORD *)this + v46 + 6280) - v54 < 0;
        *((_DWORD *)this + v46 + 6280) -= v54;
        if ( v48 )
          *((_DWORD *)this + v46 + 6280) += 1000000000;
        v55 = *((_DWORD *)this + (v45 + 37) % 55 + 6275);
        v48 = *((_DWORD *)this + v46 + 6281) - v55 < 0;
        *((_DWORD *)this + v46 + 6281) -= v55;
        if ( v48 )
          *((_DWORD *)this + v46 + 6281) += 1000000000;
        v56 = *((_DWORD *)this + (v45 + 38) % 55 + 6275);
        v48 = *((_DWORD *)this + v46 + 6282) - v56 < 0;
        *((_DWORD *)this + v46 + 6282) -= v56;
        if ( v48 )
          *((_DWORD *)this + v46 + 6282) += 1000000000;
        v57 = *((_DWORD *)this + (v45 + 39) % 55 + 6275);
        v48 = *((_DWORD *)this + v46 + 6283) - v57 < 0;
        *((_DWORD *)this + v46 + 6283) -= v57;
        if ( v48 )
          *((_DWORD *)this + v46 + 6283) += 1000000000;
        v58 = *((_DWORD *)this + (v45 + 40) % 55 + 6275);
        v48 = *((_DWORD *)this + v46 + 6284) - v58 < 0;
        *((_DWORD *)this + v46 + 6284) -= v58;
        if ( v48 )
          *((_DWORD *)this + v46 + 6284) += 1000000000;
        v45 += 11;
        v46 += 11;
      }
      while ( v45 <= 55 );
      --v44;
    }
    while ( v44 );
    *((_DWORD *)this + 6272) = 0;
    *((_DWORD *)this + 6273) = 31;
    *a2 = 1;
  }
  v59 = ++*((_DWORD *)this + 6272);
  if ( v59 >= 56 )
  {
    *((_DWORD *)this + 6272) = 1;
    v59 = 1;
  }
  if ( (int)++*((_DWORD *)this + 6273) < 56 )
    v3 = *((_DWORD *)this + 6273);
  else
    *((_DWORD *)this + 6273) = 1;
  v60 = v59;
  v61 = *((_DWORD *)this + v59 + 6274) - *((_DWORD *)this + v3 + 6274);
  v62 = v61 + 1000000000;
  if ( v61 >= 0 )
    v62 = v61;
  *((_DWORD *)this + v60 + 6274) = v62;
  return (float)v62 * 9.9999997e-10;
}

```

## disassembly

```asm
0x180010440  push    rbx
0x180010442  cmp     dword ptr [rdx], 0
0x180010445  mov     r11, rcx
0x180010448  mov     [rsp+8+arg_10], r14
0x18001044d  mov     ebx, 1
0x180010452  mov     r14, rdx
0x180010455  jl      short loc_180010464
0x180010457  cmp     dword ptr [rcx+62E8h], 0
0x18001045e  jnz     loc_180010B3E
0x180010464  mov     [rcx+62E8h], ebx
0x18001046a  mov     eax, 44B82FA1h
0x18001046f  mov     ecx, [rdx]
0x180010471  mov     r10d, ebx
0x180010474  neg     ecx
0x180010476  mov     [rsp+8+arg_0], rsi
0x18001047b  mov     [rsp+8+arg_8], rdi
0x180010480  mov     esi, ebx
0x180010482  cmovs   ecx, [rdx]
0x180010485  mov     edi, 9A4EC86h
0x18001048a  sub     edi, ecx
0x18001048c  imul    edi
0x18001048e  sar     edx, 1Ch
0x180010491  mov     eax, edx
0x180010493  shr     eax, 1Fh
0x180010496  add     edx, eax
0x180010498  imul    eax, edx, 3B9ACA00h
0x18001049e  sub     edi, eax
0x1800104a0  mov     [r11+62E4h], edi
0x1800104a7  nop     word ptr [rax+rax+00000000h]
0x1800104b0  imul    r8d, esi, 15h
0x1800104b4  mov     eax, 94F2095h
0x1800104b9  imul    r8d
0x1800104bc  mov     ecx, r8d
0x1800104bf  sar     edx, 1
0x1800104c1  mov     eax, edx
0x1800104c3  shr     eax, 1Fh
0x1800104c6  add     edx, eax
0x1800104c8  imul    eax, edx, 37h ; '7'
0x1800104cb  sub     ecx, eax
0x1800104cd  movsxd  rax, ecx
0x1800104d0  sub     edi, r10d
0x1800104d3  lea     ecx, [r8+15h]
0x1800104d7  mov     [r11+rax*4+6208h], r10d
0x1800104df  lea     r9d, [rdi+3B9ACA00h]
0x1800104e6  cmovns  r9d, edi
0x1800104ea  mov     eax, 94F2095h
0x1800104ef  imul    ecx
0x1800104f1  sar     edx, 1
0x1800104f3  mov     eax, edx
0x1800104f5  shr     eax, 1Fh
0x1800104f8  add     edx, eax
0x1800104fa  imul    eax, edx, 37h ; '7'
0x1800104fd  sub     ecx, eax
0x1800104ff  movsxd  rax, ecx
0x180010502  sub     r10d, r9d
0x180010505  mov     [r11+rax*4+6208h], r9d
0x18001050d  lea     r8d, [r10+3B9ACA00h]
0x180010514  cmovns  r8d, r10d
0x180010518  lea     eax, [rsi+2]
0x18001051b  imul    ecx, eax, 15h
0x18001051e  mov     eax, 94F2095h
0x180010523  imul    ecx
0x180010525  sar     edx, 1
0x180010527  mov     eax, edx
0x180010529  shr     eax, 1Fh
0x18001052c  add     edx, eax
0x18001052e  imul    eax, edx, 37h ; '7'
0x180010531  sub     ecx, eax
0x180010533  sub     r9d, r8d
0x180010536  movsxd  rax, ecx
0x180010539  mov     [r11+rax*4+6208h], r8d
0x180010541  lea     r10d, [r9+3B9ACA00h]
0x180010548  cmovns  r10d, r9d
0x18001054c  lea     eax, [rsi+3]
0x18001054f  imul    ecx, eax, 15h
0x180010552  mov     eax, 94F2095h
0x180010557  imul    ecx
0x180010559  sar     edx, 1
0x18001055b  mov     eax, edx
0x18001055d  shr     eax, 1Fh
0x180010560  add     edx, eax
0x180010562  imul    eax, edx, 37h ; '7'
0x180010565  sub     ecx, eax
0x180010567  movsxd  rax, ecx
0x18001056a  sub     r8d, r10d
0x18001056d  mov     [r11+rax*4+6208h], r10d
0x180010575  lea     r9d, [r8+3B9ACA00h]
0x18001057c  cmovns  r9d, r8d
0x180010580  lea     eax, [rsi+4]
0x180010583  imul    ecx, eax, 15h
0x180010586  mov     eax, 94F2095h
0x18001058b  imul    ecx
0x18001058d  sar     edx, 1
0x18001058f  mov     eax, edx
0x180010591  shr     eax, 1Fh
0x180010594  add     edx, eax
0x180010596  imul    eax, edx, 37h ; '7'
0x180010599  sub     ecx, eax
0x18001059b  movsxd  rax, ecx
0x18001059e  sub     r10d, r9d
0x1800105a1  mov     [r11+rax*4+6208h], r9d
0x1800105a9  lea     r8d, [r10+3B9ACA00h]
0x1800105b0  cmovns  r8d, r10d
0x1800105b4  lea     eax, [rsi+5]
0x1800105b7  imul    ecx, eax, 15h
0x1800105ba  mov     eax, 94F2095h
0x1800105bf  imul    ecx
0x1800105c1  sar     edx, 1
0x1800105c3  mov     eax, edx
0x1800105c5  shr     eax, 1Fh
0x1800105c8  add     edx, eax
0x1800105ca  imul    eax, edx, 37h ; '7'
0x1800105cd  sub     ecx, eax
0x1800105cf  movsxd  rax, ecx
0x1800105d2  sub     r9d, r8d
0x1800105d5  mov     [r11+rax*4+6208h], r8d
0x1800105dd  lea     r10d, [r9+3B9ACA00h]
0x1800105e4  cmovns  r10d, r9d
0x1800105e8  lea     eax, [rsi+6]
0x1800105eb  imul    ecx, eax, 15h
0x1800105ee  mov     eax, 94F2095h
0x1800105f3  imul    ecx
0x1800105f5  sar     edx, 1
0x1800105f7  mov     eax, edx
0x1800105f9  shr     eax, 1Fh
0x1800105fc  add     edx, eax
0x1800105fe  imul    eax, edx, 37h ; '7'
0x180010601  sub     ecx, eax
0x180010603  movsxd  rax, ecx
0x180010606  sub     r8d, r10d
0x180010609  mov     [r11+rax*4+6208h], r10d
0x180010611  lea     r9d, [r8+3B9ACA00h]
0x180010618  cmovns  r9d, r8d
0x18001061c  lea     eax, [rsi+7]
0x18001061f  imul    ecx, eax, 15h
0x180010622  mov     eax, 94F2095h
0x180010627  imul    ecx
0x180010629  sar     edx, 1
0x18001062b  mov     eax, edx
0x18001062d  shr     eax, 1Fh
0x180010630  add     edx, eax
0x180010632  imul    eax, edx, 37h ; '7'
0x180010635  sub     ecx, eax
0x180010637  movsxd  rax, ecx
0x18001063a  sub     r10d, r9d
0x18001063d  mov     [r11+rax*4+6208h], r9d
0x180010645  lea     r8d, [r10+3B9ACA00h]
0x18001064c  cmovns  r8d, r10d
0x180010650  lea     eax, [rsi+8]
0x180010653  imul    ecx, eax, 15h
0x180010656  mov     eax, 94F2095h
0x18001065b  imul    ecx
0x18001065d  sar     edx, 1
0x18001065f  mov     eax, edx
0x180010661  shr     eax, 1Fh
0x180010664  add     edx, eax
0x180010666  imul    eax, edx, 37h ; '7'
0x180010669  sub     ecx, eax
0x18001066b  movsxd  rax, ecx
0x18001066e  sub     r9d, r8d
0x180010671  mov     [r11+rax*4+6208h], r8d
0x180010679  lea     r10d, [r9+3B9ACA00h]
0x180010680  cmovns  r10d, r9d
0x180010684  lea     eax, [rsi+9]
0x180010687  imul    ecx, eax, 15h
0x18001068a  mov     eax, 94F2095h
0x18001068f  imul    ecx
0x180010691  sar     edx, 1
0x180010693  mov     eax, edx
0x180010695  shr     eax, 1Fh
0x180010698  add     edx, eax
0x18001069a  imul    eax, edx, 37h ; '7'
0x18001069d  sub     ecx, eax
0x18001069f  movsxd  rax, ecx
0x1800106a2  sub     r8d, r10d
0x1800106a5  mov     [r11+rax*4+6208h], r10d
0x1800106ad  lea     r9d, [r8+3B9ACA00h]
0x1800106b4  cmovns  r9d, r8d
0x1800106b8  lea     eax, [rsi+0Ah]
0x1800106bb  imul    ecx, eax, 15h
0x1800106be  mov     eax, 94F2095h
0x1800106c3  imul    ecx
0x1800106c5  sar     edx, 1
0x1800106c7  mov     eax, edx
0x1800106c9  shr     eax, 1Fh
0x1800106cc  add     edx, eax
0x1800106ce  imul    eax, edx, 37h ; '7'
0x1800106d1  sub     ecx, eax
0x1800106d3  movsxd  rax, ecx
0x1800106d6  sub     r10d, r9d
0x1800106d9  mov     [r11+rax*4+6208h], r9d
0x1800106e1  lea     r8d, [r10+3B9ACA00h]
0x1800106e8  cmovns  r8d, r10d
0x1800106ec  lea     eax, [rsi+0Bh]
0x1800106ef  imul    ecx, eax, 15h
0x1800106f2  mov     eax, 94F2095h
0x1800106f7  imul    ecx
0x1800106f9  sar     edx, 1
0x1800106fb  mov     eax, edx
0x1800106fd  shr     eax, 1Fh
0x180010700  add     edx, eax
0x180010702  imul    eax, edx, 37h ; '7'
0x180010705  sub     ecx, eax
0x180010707  sub     r9d, r8d
0x18001070a  movsxd  rax, ecx
0x18001070d  mov     [r11+rax*4+6208h], r8d
0x180010715  lea     r10d, [r9+3B9ACA00h]
0x18001071c  cmovns  r10d, r9d
0x180010720  lea     eax, [rsi+0Ch]
0x180010723  imul    ecx, eax, 15h
0x180010726  mov     eax, 94F2095h
0x18001072b  imul    ecx
0x18001072d  sar     edx, 1
0x18001072f  mov     eax, edx
0x180010731  shr     eax, 1Fh
0x180010734  add     edx, eax
0x180010736  imul    eax, edx, 37h ; '7'
0x180010739  sub     ecx, eax
0x18001073b  movsxd  rax, ecx
0x18001073e  sub     r8d, r10d
0x180010741  mov     [r11+rax*4+6208h], r10d
0x180010749  lea     r9d, [r8+3B9ACA00h]
0x180010750  cmovns  r9d, r8d
0x180010754  lea     eax, [rsi+0Dh]
0x180010757  imul    ecx, eax, 15h
0x18001075a  mov     eax, 94F2095h
0x18001075f  imul    ecx
0x180010761  sar     edx, 1
0x180010763  mov     eax, edx
0x180010765  shr     eax, 1Fh
0x180010768  add     edx, eax
0x18001076a  imul    eax, edx, 37h ; '7'
0x18001076d  sub     ecx, eax
0x18001076f  sub     r10d, r9d
0x180010772  movsxd  rax, ecx
0x180010775  mov     [r11+rax*4+6208h], r9d
0x18001077d  lea     r8d, [r10+3B9ACA00h]
0x180010784  cmovns  r8d, r10d
0x180010788  lea     eax, [rsi+0Eh]
0x18001078b  imul    ecx, eax, 15h
0x18001078e  mov     eax, 94F2095h
0x180010793  imul    ecx
0x180010795  sar     edx, 1
0x180010797  mov     eax, edx
0x180010799  shr     eax, 1Fh
0x18001079c  add     edx, eax
0x18001079e  imul    eax, edx, 37h ; '7'
0x1800107a1  sub     ecx, eax
0x1800107a3  movsxd  rax, ecx
0x1800107a6  sub     r9d, r8d
0x1800107a9  mov     [r11+rax*4+6208h], r8d
0x1800107b1  lea     r10d, [r9+3B9ACA00h]
0x1800107b8  cmovns  r10d, r9d
0x1800107bc  lea     eax, [rsi+0Fh]
0x1800107bf  imul    ecx, eax, 15h
0x1800107c2  mov     eax, 94F2095h
0x1800107c7  imul    ecx
0x1800107c9  sar     edx, 1
0x1800107cb  mov     eax, edx
0x1800107cd  shr     eax, 1Fh
0x1800107d0  add     edx, eax
0x1800107d2  imul    eax, edx, 37h ; '7'
0x1800107d5  sub     ecx, eax
0x1800107d7  movsxd  rax, ecx
0x1800107da  sub     r8d, r10d
0x1800107dd  mov     [r11+rax*4+6208h], r10d
0x1800107e5  lea     r9d, [r8+3B9ACA00h]
0x1800107ec  lea     eax, [rsi+10h]
0x1800107ef  cmovns  r9d, r8d
0x1800107f3  imul    ecx, eax, 15h
0x1800107f6  mov     eax, 94F2095h
0x1800107fb  imul    ecx
0x1800107fd  sar     edx, 1
0x1800107ff  mov     eax, edx
0x180010801  shr     eax, 1Fh
0x180010804  add     edx, eax
0x180010806  imul    eax, edx, 37h ; '7'
0x180010809  sub     ecx, eax
0x18001080b  sub     r10d, r9d
0x18001080e  movsxd  rax, ecx
0x180010811  mov     [r11+rax*4+6208h], r9d
0x180010819  lea     edi, [r10+3B9ACA00h]
0x180010820  cmovns  edi, r10d
0x180010824  lea     eax, [rsi+11h]
0x180010827  imul    ecx, eax, 15h
0x18001082a  sub     r9d, edi
0x18001082d  mov     eax, 94F2095h
0x180010832  add     esi, 12h
0x180010835  lea     r10d, [r9+3B9ACA00h]
0x18001083c  imul    ecx
0x18001083e  sar     edx, 1
0x180010840  mov     eax, edx
0x180010842  shr     eax, 1Fh
0x180010845  add     edx, eax
0x180010847  imul    eax, edx, 37h ; '7'
0x18001084a  sub     ecx, eax
0x18001084c  test    r9d, r9d
0x18001084f  movsxd  rax, ecx
0x180010852  cmovns  r10d, r9d
0x180010856  mov     [r11+rax*4+6208h], edi
  ... truncated ...
```
