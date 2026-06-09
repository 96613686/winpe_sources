# CSourceArticulation::Download(_DMUS_DOWNLOADINFO *,void * * const,ulong,ulong,int)

- ea: `0x180007fd0`
- end: `0x180008b28`
- name: `?Download@CSourceArticulation@@QEAAJPEAU_DMUS_DOWNLOADINFO@@QEAPEAXKKH@Z`
- size: `2904`
- prototype: `__int64 __fastcall(CSourceArticulation *this, struct _DMUS_DOWNLOADINFO *, void **const, int, int, int)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180008b30`
- `0x180008cb0`

## callees

- `0x180001d6a`
- `0x180007fd0`
- `0x180009ac0`
- `0x180009d80`

## pseudocode

```c
__int64 __fastcall CSourceArticulation::Download(
        CSourceArticulation *this,
        struct _DMUS_DOWNLOADINFO *a2,
        void **const a3,
        int a4,
        int a5,
        int a6)
{
  void **v6; // r13
  struct _DMUS_DOWNLOADINFO *v7; // r12
  unsigned int *v9; // r15
  __int64 v10; // rax
  _DWORD *v11; // rbx
  int v12; // ebp
  unsigned int v13; // r14d
  __int64 v14; // rdx
  unsigned int v15; // ecx
  unsigned int v16; // ecx
  unsigned int v17; // ecx
  unsigned int v18; // ecx
  unsigned int v19; // ecx
  int v20; // eax
  double v21; // xmm0_8
  __int64 v22; // rax
  double v23; // xmm0_8
  int v24; // eax
  double v25; // xmm0_8
  __int64 v26; // rax
  double v27; // xmm0_8
  int v28; // eax
  double v29; // xmm0_8
  __int64 v30; // rax
  double v31; // xmm0_8
  unsigned int v32; // ecx
  unsigned int v33; // ecx
  unsigned int v34; // ecx
  unsigned int v35; // ecx
  int v36; // eax
  double v37; // xmm0_8
  __int64 v38; // rax
  double v39; // xmm0_8
  int v40; // eax
  double v41; // xmm0_8
  __int64 v42; // rax
  double v43; // xmm0_8
  int v44; // eax
  double v45; // xmm0_8
  __int64 v46; // rax
  double v47; // xmm0_8
  int v48; // eax
  double v49; // xmm0_8
  __int64 v50; // rax
  double v51; // xmm0_8
  int v52; // eax
  double v53; // xmm0_8
  __int64 v54; // rax
  double v55; // xmm0_8
  unsigned int v56; // ecx
  unsigned int v57; // ecx
  int v58; // eax
  double v59; // xmm0_8
  __int64 v60; // rax
  double v61; // xmm0_8
  int v62; // eax
  double v63; // xmm0_8
  __int64 v64; // rax
  double v65; // xmm0_8
  int v66; // eax
  double v67; // xmm0_8
  __int64 v68; // rax
  double v69; // xmm0_8
  unsigned int v70; // ecx
  unsigned int v71; // ecx
  int v72; // eax
  __int16 v73; // ax
  int v74; // eax
  double v75; // xmm0_8
  __int64 v76; // rax
  double v77; // xmm0_8
  __int16 v78; // ax
  __int16 v79; // ax
  __int64 v80; // rax
  __int64 v81; // rax
  _DWORD *v83; // rdi
  unsigned int *v84; // [rsp+20h] [rbp-C8h]

  v6 = a3;
  v7 = a2;
  v9 = (unsigned int *)a3[a4];
  v84 = v9;
  if ( a6 )
  {
    if ( !v9 )
      goto LABEL_156;
    while ( 1 )
    {
      v10 = *v9;
      if ( !(_DWORD)v10 )
        goto LABEL_148;
      if ( (unsigned int)v10 >= v7->dwNumOffsetTableEntries )
        return 2289570086LL;
      v11 = v6[v10];
      v12 = 0;
      v13 = 8;
      if ( !v11[1] )
        goto LABEL_148;
      while ( 2 )
      {
        v14 = v13;
        v13 += 12;
        switch ( *(_WORD *)((char *)v11 + v14) )
        {
          case 0:
            v15 = *(unsigned __int16 *)((char *)v11 + v14 + 4);
            if ( v15 > 0x206 )
            {
              if ( v15 > 0x30A )
              {
                if ( v15 > 0x30F )
                {
                  v70 = v15 - 784;
                  if ( v70 )
                  {
                    v71 = v70 - 496;
                    if ( v71 )
                    {
                      if ( v71 == 1 )
                      {
                        v72 = *(__int16 *)((char *)v11 + v14 + 10);
                        *((_WORD *)this + 103) = v72;
                        *((_DWORD *)this + 52) = (int)(float)((float)((float)v72 / 15.0) + 0.5);
                      }
                    }
                    else
                    {
                      v73 = *(_WORD *)((char *)v11 + v14 + 10);
                      *((_WORD *)this + 101) = v73;
                      *((_WORD *)this + 102) = v73 - *((_WORD *)this + 100) + 10688;
                    }
                  }
                  else
                  {
                    v74 = *(_DWORD *)((char *)v11 + v14 + 8);
                    if ( v74 == 0x80000000 )
                    {
                      *((_QWORD *)this + 5) = 0;
                    }
                    else
                    {
                      v75 = pow(2.0, (double)v74 / 78643200.0);
                      v76 = (unsigned int)(40 * a5);
                      v77 = v75 * (double)a5;
                      if ( (unsigned int)(int)v77 <= v76 )
                        v76 = (unsigned int)(int)v77;
                      *((_QWORD *)this + 5) = v76;
                    }
                  }
                }
                else if ( v15 == 783 )
                {
                  v66 = *(_DWORD *)((char *)v11 + v14 + 8);
                  if ( v66 == 0x80000000 )
                  {
                    *((_QWORD *)this + 4) = 0;
                  }
                  else
                  {
                    v67 = pow(2.0, (double)v66 / 78643200.0);
                    v68 = (unsigned int)(40 * a5);
                    v69 = v67 * (double)a5;
                    if ( (unsigned int)(int)v69 <= v68 )
                      v68 = (unsigned int)(int)v69;
                    *((_QWORD *)this + 4) = v68;
                  }
                }
                else
                {
                  v56 = v15 - 779;
                  if ( v56 )
                  {
                    v57 = v56 - 2;
                    if ( v57 )
                    {
                      if ( v57 == 1 )
                        *((_WORD *)this + 14) = *(_WORD *)((char *)v11 + v14 + 10);
                    }
                    else
                    {
                      v58 = *(_DWORD *)((char *)v11 + v14 + 8);
                      if ( v58 == 0x80000000 )
                      {
                        *((_QWORD *)this + 2) = 0;
                      }
                      else
                      {
                        v59 = pow(2.0, (double)v58 / 78643200.0);
                        v60 = (unsigned int)(40 * a5);
                        v61 = v59 * (double)a5;
                        if ( (unsigned int)(int)v61 <= v60 )
                          v60 = (unsigned int)(int)v61;
                        *((_QWORD *)this + 2) = v60;
                      }
                    }
                  }
                  else
                  {
                    v62 = *(_DWORD *)((char *)v11 + v14 + 8);
                    if ( v62 == 0x80000000 )
                    {
                      *((_QWORD *)this + 1) = 0;
                    }
                    else
                    {
                      v63 = pow(2.0, (double)v62 / 78643200.0);
                      v64 = (unsigned int)(40 * a5);
                      v65 = v63 * (double)a5;
                      if ( (unsigned int)(int)v65 <= v64 )
                        v64 = (unsigned int)(int)v65;
                      *((_QWORD *)this + 1) = v64;
                    }
                  }
                }
              }
              else if ( v15 == 778 )
              {
                v52 = *(_DWORD *)((char *)v11 + v14 + 8);
                if ( v52 == 0x80000000 )
                {
                  *(_QWORD *)this = 0;
                }
                else
                {
                  v53 = pow(2.0, (double)v52 / 78643200.0);
                  v54 = (unsigned int)(40 * a5);
                  v55 = v53 * (double)a5;
                  if ( (unsigned int)(int)v55 <= v54 )
                    v54 = (unsigned int)(int)v55;
                  *(_QWORD *)this = v54;
                }
              }
              else
              {
                v32 = v15 - 519;
                if ( v32 )
                {
                  v33 = v32 - 2;
                  if ( v33 )
                  {
                    v34 = v33 - 1;
                    if ( v34 )
                    {
                      v35 = v34 - 1;
                      if ( v35 )
                      {
                        if ( v35 == 1 )
                        {
                          v36 = *(_DWORD *)((char *)v11 + v14 + 8);
                          if ( v36 == 0x80000000 )
                          {
                            *((_QWORD *)this + 12) = 0;
                          }
                          else
                          {
                            v37 = pow(2.0, (double)v36 / 78643200.0);
                            v38 = (unsigned int)(40 * a5);
                            v39 = v37 * (double)a5;
                            if ( (unsigned int)(int)v39 <= v38 )
                              v38 = (unsigned int)(int)v39;
                            *((_QWORD *)this + 12) = v38;
                          }
                        }
                      }
                      else
                      {
                        v40 = *(_DWORD *)((char *)v11 + v14 + 8);
                        if ( v40 == 0x80000000 )
                        {
                          *((_QWORD *)this + 11) = 0;
                        }
                        else
                        {
                          v41 = pow(2.0, (double)v40 / 78643200.0);
                          v42 = (unsigned int)(40 * a5);
                          v43 = v41 * (double)a5;
                          if ( (unsigned int)(int)v43 <= v42 )
                            v42 = (unsigned int)(int)v43;
                          *((_QWORD *)this + 11) = v42;
                        }
                      }
                    }
                    else
                    {
                      *((_WORD *)this + 42) = *(_WORD *)((char *)v11 + v14 + 10);
                    }
                  }
                  else
                  {
                    v44 = *(_DWORD *)((char *)v11 + v14 + 8);
                    if ( v44 == 0x80000000 )
                    {
                      *((_QWORD *)this + 9) = 0;
                    }
                    else
                    {
                      v45 = pow(2.0, (double)v44 / 78643200.0);
                      v46 = (unsigned int)(40 * a5);
                      v47 = v45 * (double)a5;
                      if ( (unsigned int)(int)v47 <= v46 )
                        v46 = (unsigned int)(int)v47;
                      *((_QWORD *)this + 9) = v46;
                    }
                  }
                }
                else
                {
                  v48 = *(_DWORD *)((char *)v11 + v14 + 8);
                  if ( v48 == 0x80000000 )
                  {
                    *((_QWORD *)this + 8) = 0;
                  }
                  else
                  {
                    v49 = pow(2.0, (double)v48 / 78643200.0);
                    v50 = (unsigned int)(40 * a5);
                    v51 = v49 * (double)a5;
                    if ( (unsigned int)(int)v51 <= v50 )
                      v50 = (unsigned int)(int)v51;
                    *((_QWORD *)this + 8) = v50;
                  }
                }
              }
            }
            else if ( v15 == 518 )
            {
              v28 = *(_DWORD *)((char *)v11 + v14 + 8);
              if ( v28 == 0x80000000 )
              {
                *((_QWORD *)this + 7) = 0;
              }
              else
              {
                v29 = pow(2.0, (double)v28 / 78643200.0);
                v30 = (unsigned int)(40 * a5);
                v31 = v29 * (double)a5;
                if ( (unsigned int)(int)v31 <= v30 )
                  v30 = (unsigned int)(int)v31;
                *((_QWORD *)this + 7) = v30;
              }
            }
            else
            {
              v16 = v15 - 4;
              if ( v16 )
              {
                v17 = v16 - 256;
                if ( v17 )
                {
                  v18 = v17 - 1;
                  if ( v18 )
                  {
                    v19 = v18 - 15;
                    if ( v19 )
                    {
                      if ( v19 == 1 )
                      {
                        v20 = *(_DWORD *)((char *)v11 + v14 + 8);
                        if ( v20 == 0x80000000 )
                        {
                          *((_QWORD *)this + 21) = 0;
                        }
                        else
                        {
                          v21 = pow(2.0, (double)v20 / 78643200.0);
                          v22 = (unsigned int)(10 * a5);
                          v23 = v21 * (double)a5;
                          if ( (unsigned int)(int)v23 <= v22 )
                            v22 = (unsigned int)(int)v23;
                          *((_QWORD *)this + 21) = v22;
                        }
                      }
                    }
                    else
                    {
                      *((_DWORD *)this + 40) = (int)(pow(
                                                       2.0,
                                                       ((double)*(int *)((char *)v11 + v14 + 8) * 0.0000152587890625
                                                      - 6900.0)
                                                     / 1200.0)
                                                   * 7381975040.0
                                                   / (double)a5);
                    }
                  }
                  else
                  {
                    v24 = *(_DWORD *)((char *)v11 + v14 + 8);
                    if ( v24 == 0x80000000 )
                    {
                      *((_QWORD *)this + 15) = 0;
                    }
                    else
                    {
                      v25 = pow(2.0, (double)v24 / 78643200.0);
                      v26 = (unsigned int)(10 * a5);
                      v27 = v25 * (double)a5;
                      if ( (unsigned int)(int)v27 <= v26 )
                        v26 = (unsigned int)(int)v27;
                      *((_QWORD *)this + 15) = v26;
                    }
                  }
                }
                else
                {
                  *((_DWORD *)this + 28) = (int)(pow(
                                                   2.0,
                                                   ((double)*(int *)((char *)v11 + v14 + 8) * 0.0000152587890625 - 6900.0)
                                                 / 1200.0)
                                               * 7381975040.0
                                               / (double)a5);
                }
              }
              else
              {
                *((_WORD *)this + 79) = (*(int *)((char *)v11 + v14 + 8) >> 12) / 125;
              }
            }
            goto LABEL_146;
          case 1:
            if ( *(_WORD *)((char *)v11 + v14 + 2) )
            {
              if ( *(_WORD *)((char *)v11 + v14 + 2) == 8 )
              {
                switch ( *(_WORD *)((char *)v11 + v14 + 4) )
                {
                  case 1:
                    *((_WORD *)this + 69) = *(_WORD *)((char *)v11 + v14 + 10);
                    break;
                  case 3:
                    *((_WORD *)this + 68) = *(_WORD *)((char *)v11 + v14 + 10);
                    break;
                  case 0x500:
                    *((_WORD *)this + 72) = *(_WORD *)((char *)v11 + v14 + 10);
                    break;
                }
              }
              else if ( *(_WORD *)((char *)v11 + v14 + 2) == 129 )
              {
                switch ( *(_WORD *)((char *)v11 + v14 + 4) )
                {
                  case 1:
                    *((_WORD *)this + 64) = (unsigned int)(10 * *(_DWORD *)((char *)v11 + v14 + 8)) >> 16;
                    break;
                  case 3:
                    *((_WORD *)this + 65) = *(_WORD *)((char *)v11 + v14 + 10);
                    break;
                  case 0x500:
                    *((_WORD *)this + 71) = *(_WORD *)((char *)v11 + v14 + 10);
                    break;
                }
              }
            }
            else
            {
              switch ( *(_WORD *)((char *)v11 + v14 + 4) )
              {
                case 1:
                  *((_WORD *)this + 66) = (unsigned int)(10 * *(_DWORD *)((char *)v11 + v14 + 8)) >> 16;
                  break;
                case 3:
                  *((_WORD *)this + 67) = *(_WORD *)((char *)v11 + v14 + 10);
                  break;
                case 0x500:
                  *((_WORD *)this + 70) = *(_WORD *)((char *)v11 + v14 + 10);
                  break;
              }
            }
            goto LABEL_146;
          case 2:
            v78 = *(_WORD *)((char *)v11 + v14 + 4);
            switch ( v78 )
            {
              case 518:
                *((_WORD *)this + 40) = *(_WORD *)((char *)v11 + v14 + 10);
                break;
              case 778:
                *((_WORD *)this + 12) = *(_WORD *)((char *)v11 + v14 + 10);
                break;
              case 1280:
                *((_WORD *)this + 106) = *(_WORD *)((char *)v11 + v14 + 10);
                break;
            }
            goto LABEL_146;
          case 3:
            switch ( *(_WORD *)((char *)v11 + v14 + 4) )
            {
              case 0x207:
                *((_WORD *)this + 41) = *(_WORD *)((char *)v11 + v14 + 10);
                break;
              case 0x20C:
              case 0x30B:
                *((_WORD *)this + 13) = *(_WORD *)((char *)v11 + v14 + 10);
                break;
              case 0x310:
                *((_WORD *)this + 13) = *(_WORD *)((char *)v11 + v14 + 10);
LABEL_130:
                *((_WORD *)this + 107) = *(_WORD *)((char *)v11 + v14 + 10);
                break;
              case 0x500:
                goto LABEL_130;
            }
LABEL_146:
            if ( (unsigned int)++v12 < v11[1] )
              continue;
            v9 = v84;
            v7 = a2;
            v6 = a3;
LABEL_148:
            v80 = v9[2];
            if ( !(_DWORD)v80 )
            {
LABEL_156:
              CSourceArticulation::Verify(this);
              return 0;
            }
            if ( (unsigned int)v80 >= v7->dwNumOffsetTableEntries )
              return 2289570086LL;
            v9 = (unsigned int *)v6[v80];
            v84 = v9;
            if ( !v9 )
              goto LABEL_156;
            break;
          case 5:
            v79 = *(_WORD *)((char *)v11 + v14 + 4);
            if ( v79 == 3 )
            {
              *((_WORD *)this + 15) = *(_WORD *)((char *)v11 + v14 + 10);
            }
            else if ( v79 == 1280 )
            {
              *((_WORD *)this + 25) = *(_WORD *)((char *)v11 + v14 + 10);
            }
            goto LABEL_146;
          case 9:
            if ( *(_WORD *)((char *)v11 + v14 + 2) )
            {
              if ( *(_WORD *)((char *)v11 + v14 + 2) == 8 )
              {
                if ( *(_WORD *)((char *)v11 + v14 + 4) == 3 )
                  *((_WORD *)this + 92) = *(_WORD *)((char *)v11 + v14 + 10);
              }
              else if ( *(_WORD *)((char *)v11 + v14 + 2) == 129 && *(_WORD *)((char *)v11 + v14 + 4) == 3 )
              {
                *((_WORD *)this + 89) = *(_WORD *)((char *)v11 + v14 + 10);
              }
            }
            else if ( *(_WORD *)((char *)v11 + v14 + 4) == 3 )
            {
              *((_WORD *)this + 91) = *(_WORD *)((char *)v11 + v14 + 10);
            }
            goto LABEL_146;
          default:
            goto LABEL_146;
        }
        break;
      }
    }
  }
  v81 = *v9;
  if ( !(_DWORD)v81 )
    goto LABEL_156;
  if ( (unsigned int)v81 < a2->dwNumOffsetTableEntries )
  {
    v83 = a3[v81];
    *((_DWORD *)this + 28) = (int)(pow(2.0, ((double)(int)*v83 * 0.0000152587890625 - 6900.0) / 1200.0)
                                 * 7381975040.0
                                 / (double)a5);
    *((_QWORD *)this + 15) = TimeCents2Samples(v83[1], a5, 10);
    *((_WORD *)this + 66) = (unsigned int)(10 * v83[2]) >> 16;
    *((_WORD *)this + 67) = *((_WORD *)v83 + 7);
    *((_WORD *)this + 64) = (unsigned int)(10 * v83[4]) >> 16;
    *((_WORD *)this + 65) = *((_WORD *)v83 + 11);
    *((_QWORD *)this + 7) = TimeCents2Samples(v83[6], a5, 40);
    *((_QWORD *)this + 8) = TimeCents2Samples(v83[7], a5, 40);
    *((_WORD *)this + 42) = *((_WORD *)v83 + 17);
    *((_QWORD *)this + 9) = TimeCents2Samples(v83[9], a5, 40);
    *((_WORD *)this + 40) = *((_WORD *)v83 + 21);
    *((_WORD *)this + 41) = *((_WORD *)v83 + 23);
    *((_WORD *)this + 13) = *((_WORD *)v83 + 35);
    *((_WORD *)this + 15) = *((_WORD *)v83 + 37);
    *((_WORD *)this + 12) = *((_WORD *)v83 + 33);
    *(_QWORD *)this = TimeCents2Samples(v83[12], a5, 40);
    *((_QWORD *)this + 1) = TimeCents2Samples(v83[13], a5, 40);
    *((_WORD *)this + 14) = *((_WORD *)v83 + 29);
    *((_QWORD *)this + 2) = TimeCents2Samples(v83[15], a5, 40);
    *((_WORD *)this + 79) = ((int)v83[19] >> 12) / 125;
    goto LABEL_156;
  }
  return 2289570086LL;
}

```

## disassembly

```asm
0x180007fd0  mov     rax, rsp
0x180007fd3  mov     [rax+8], rbx
0x180007fd7  mov     [rax+18h], r8
0x180007fdb  mov     [rax+10h], rdx
0x180007fdf  push    rbp
0x180007fe0  push    rsi
0x180007fe1  push    rdi
0x180007fe2  push    r12
0x180007fe4  push    r13
0x180007fe6  push    r14
0x180007fe8  push    r15
0x180007fea  sub     rsp, 0B0h
0x180007ff1  cmp     [rsp+0E8h+arg_28], 0
0x180007ff9  mov     r13, r8
0x180007ffc  movaps  xmmword ptr [rax-48h], xmm6
0x180008000  mov     r12, rdx
0x180008003  movaps  xmmword ptr [rax-58h], xmm7
0x180008007  mov     rsi, rcx
0x18000800a  movaps  xmmword ptr [rax-68h], xmm8
0x18000800f  movaps  xmmword ptr [rax-78h], xmm9
0x180008014  movaps  [rsp+0E8h+var_88], xmm10
0x18000801a  movaps  [rsp+0E8h+var_98], xmm11
0x180008020  mov     eax, r9d
0x180008023  movaps  [rsp+0E8h+var_A8], xmm12
0x180008029  movaps  [rsp+0E8h+var_B8], xmm13
0x18000802f  mov     r15, [r8+rax*8]
0x180008033  mov     [rsp+0E8h+var_C8], r15
0x180008038  jz      loc_180008927
0x18000803e  test    r15, r15
0x180008041  jz      loc_180008AB0
0x180008047  mov     edi, [rsp+0E8h+arg_20]
0x18000804e  mov     r9d, 29C0h
0x180008054  movsd   xmm7, cs:__real@4192c00000000000
0x18000805c  mov     r8d, 500h
0x180008062  movsd   xmm6, cs:__real@4000000000000000
0x18000806a  movsd   xmm8, cs:__real@3ef0000000000000
0x180008073  movsd   xmm9, cs:__real@40baf40000000000
0x18000807c  movsd   xmm10, cs:__real@4092c00000000000
0x180008085  movsd   xmm11, cs:__real@41fb800000000000
0x18000808e  movss   xmm12, cs:__real@41700000
0x180008097  movss   xmm13, cs:__real@3f000000
0x1800080a0  mov     eax, [r15]
0x1800080a3  test    eax, eax
0x1800080a5  jz      loc_1800088FC
0x1800080ab  cmp     eax, [r12+8]
0x1800080b0  jnb     loc_180008937
0x1800080b6  mov     rbx, [r13+rax*8+0]
0x1800080bb  xor     ebp, ebp
0x1800080bd  mov     r14d, 8
0x1800080c3  cmp     [rbx+4], ebp
0x1800080c6  jbe     loc_1800088FC
0x1800080cc  lea     r13, cs:180000000h
0x1800080d3  mov     r12d, 206h
0x1800080d9  mov     r15d, 30Ah
0x1800080df  nop
0x1800080e0  mov     edx, r14d
0x1800080e3  add     r14d, 0Ch
0x1800080e7  movzx   eax, word ptr [rdx+rbx]
0x1800080eb  cmp     eax, 9; switch 10 cases
0x1800080ee  ja      def_1800080FF; jumptable 00000001800080FF default case, cases 4,6-8
0x1800080f4  mov     eax, ds:(jpt_1800080FF - 180000000h)[r13+rax*4]
0x1800080fc  add     rax, r13
0x1800080ff  jmp     rax; switch jump
0x180008101  movzx   ecx, word ptr [rdx+rbx+4]; jumptable 00000001800080FF case 0
0x180008106  cmp     ecx, r12d
0x180008109  ja      loc_1800082DD
0x18000810f  jz      loc_18000828C
0x180008115  sub     ecx, 4
0x180008118  jz      loc_180008268
0x18000811e  sub     ecx, 100h
0x180008124  jz      loc_180008229
0x18000812a  sub     ecx, 1
0x18000812d  jz      loc_1800081D9
0x180008133  sub     ecx, 0Fh
0x180008136  jz      short loc_180008197
0x180008138  cmp     ecx, 1
0x18000813b  jnz     def_1800080FF; jumptable 00000001800080FF default case, cases 4,6-8
0x180008141  mov     eax, [rdx+rbx+8]
0x180008145  cmp     eax, 80000000h
0x18000814a  jnz     short loc_18000815A
0x18000814c  xor     eax, eax
0x18000814e  mov     [rsi+0A8h], rax
0x180008155  jmp     def_1800080FF; jumptable 00000001800080FF default case, cases 4,6-8
0x18000815a  movd    xmm1, eax
0x18000815e  movaps  xmm0, xmm6; X
0x180008161  cvtdq2pd xmm1, xmm1
0x180008165  divsd   xmm1, xmm7; Y
0x180008169  call    pow
0x18000816e  lea     eax, [rdi+rdi*4]
0x180008171  xorps   xmm1, xmm1
0x180008174  add     eax, eax
0x180008176  cvtsi2sd xmm1, rdi
0x18000817b  mulsd   xmm0, xmm1
0x18000817f  cvttsd2si rcx, xmm0
0x180008184  cmp     rcx, rax
0x180008187  cmovle  rax, rcx
0x18000818b  mov     [rsi+0A8h], rax
0x180008192  jmp     def_1800080FF; jumptable 00000001800080FF default case, cases 4,6-8
0x180008197  movd    xmm1, dword ptr [rdx+rbx+8]
0x18000819d  movaps  xmm0, xmm6; X
0x1800081a0  cvtdq2pd xmm1, xmm1
0x1800081a4  mulsd   xmm1, xmm8
0x1800081a9  subsd   xmm1, xmm9
0x1800081ae  divsd   xmm1, xmm10; Y
0x1800081b3  call    pow
0x1800081b8  xorps   xmm1, xmm1
0x1800081bb  mulsd   xmm0, xmm11
0x1800081c0  cvtsi2sd xmm1, rdi
0x1800081c5  divsd   xmm0, xmm1
0x1800081c9  cvttsd2si rax, xmm0
0x1800081ce  mov     [rsi+0A0h], eax
0x1800081d4  jmp     def_1800080FF; jumptable 00000001800080FF default case, cases 4,6-8
0x1800081d9  mov     eax, [rdx+rbx+8]
0x1800081dd  cmp     eax, 80000000h
0x1800081e2  jnz     short loc_1800081EF
0x1800081e4  xor     eax, eax
0x1800081e6  mov     [rsi+78h], rax
0x1800081ea  jmp     def_1800080FF; jumptable 00000001800080FF default case, cases 4,6-8
0x1800081ef  movd    xmm1, eax
0x1800081f3  movaps  xmm0, xmm6; X
0x1800081f6  cvtdq2pd xmm1, xmm1
0x1800081fa  divsd   xmm1, xmm7; Y
0x1800081fe  call    pow
0x180008203  lea     eax, [rdi+rdi*4]
0x180008206  xorps   xmm1, xmm1
0x180008209  add     eax, eax
0x18000820b  cvtsi2sd xmm1, rdi
0x180008210  mulsd   xmm0, xmm1
0x180008214  cvttsd2si rcx, xmm0
0x180008219  cmp     rcx, rax
0x18000821c  cmovle  rax, rcx
0x180008220  mov     [rsi+78h], rax
0x180008224  jmp     def_1800080FF; jumptable 00000001800080FF default case, cases 4,6-8
0x180008229  movd    xmm1, dword ptr [rdx+rbx+8]
0x18000822f  movaps  xmm0, xmm6; X
0x180008232  cvtdq2pd xmm1, xmm1
0x180008236  mulsd   xmm1, xmm8
0x18000823b  subsd   xmm1, xmm9
0x180008240  divsd   xmm1, xmm10; Y
0x180008245  call    pow
0x18000824a  xorps   xmm1, xmm1
0x18000824d  mulsd   xmm0, xmm11
0x180008252  cvtsi2sd xmm1, rdi
0x180008257  divsd   xmm0, xmm1
0x18000825b  cvttsd2si rax, xmm0
0x180008260  mov     [rsi+70h], eax
0x180008263  jmp     def_1800080FF; jumptable 00000001800080FF default case, cases 4,6-8
0x180008268  mov     ecx, [rdx+rbx+8]
0x18000826c  mov     eax, 10624DD3h
0x180008271  sar     ecx, 0Ch
0x180008274  imul    ecx
0x180008276  sar     edx, 3
0x180008279  mov     eax, edx
0x18000827b  shr     eax, 1Fh
0x18000827e  add     edx, eax
0x180008280  mov     [rsi+9Eh], dx
0x180008287  jmp     def_1800080FF; jumptable 00000001800080FF default case, cases 4,6-8
0x18000828c  mov     eax, [rdx+rbx+8]
0x180008290  cmp     eax, 80000000h
0x180008295  jnz     short loc_1800082A2
0x180008297  xor     eax, eax
0x180008299  mov     [rsi+38h], rax
0x18000829d  jmp     def_1800080FF; jumptable 00000001800080FF default case, cases 4,6-8
0x1800082a2  movd    xmm1, eax
0x1800082a6  movaps  xmm0, xmm6; X
0x1800082a9  cvtdq2pd xmm1, xmm1
0x1800082ad  divsd   xmm1, xmm7; Y
0x1800082b1  call    pow
0x1800082b6  lea     eax, [rdi+rdi*4]
0x1800082b9  xorps   xmm1, xmm1
0x1800082bc  shl     eax, 3
0x1800082bf  cvtsi2sd xmm1, rdi
0x1800082c4  mulsd   xmm0, xmm1
0x1800082c8  cvttsd2si rcx, xmm0
0x1800082cd  cmp     rcx, rax
0x1800082d0  cmovle  rax, rcx
0x1800082d4  mov     [rsi+38h], rax
0x1800082d8  jmp     def_1800080FF; jumptable 00000001800080FF default case, cases 4,6-8
0x1800082dd  cmp     ecx, r15d
0x1800082e0  ja      loc_1800084B9
0x1800082e6  jz      loc_18000846A
0x1800082ec  sub     ecx, 207h
0x1800082f2  jz      loc_180008419
0x1800082f8  sub     ecx, 2
0x1800082fb  jz      loc_1800083C8
0x180008301  sub     ecx, 1
0x180008304  jz      loc_1800083BA
0x18000830a  sub     ecx, 1
0x18000830d  jz      short loc_180008369
0x18000830f  cmp     ecx, 1
0x180008312  jnz     def_1800080FF; jumptable 00000001800080FF default case, cases 4,6-8
0x180008318  mov     eax, [rdx+rbx+8]
0x18000831c  cmp     eax, 80000000h
0x180008321  jnz     short loc_18000832E
0x180008323  xor     eax, eax
0x180008325  mov     [rsi+60h], rax
0x180008329  jmp     def_1800080FF; jumptable 00000001800080FF default case, cases 4,6-8
0x18000832e  movd    xmm1, eax
0x180008332  movaps  xmm0, xmm6; X
0x180008335  cvtdq2pd xmm1, xmm1
0x180008339  divsd   xmm1, xmm7; Y
0x18000833d  call    pow
0x180008342  lea     eax, [rdi+rdi*4]
0x180008345  xorps   xmm1, xmm1
0x180008348  shl     eax, 3
0x18000834b  cvtsi2sd xmm1, rdi
0x180008350  mulsd   xmm0, xmm1
0x180008354  cvttsd2si rcx, xmm0
0x180008359  cmp     rcx, rax
0x18000835c  cmovle  rax, rcx
0x180008360  mov     [rsi+60h], rax
0x180008364  jmp     def_1800080FF; jumptable 00000001800080FF default case, cases 4,6-8
0x180008369  mov     eax, [rdx+rbx+8]
0x18000836d  cmp     eax, 80000000h
0x180008372  jnz     short loc_18000837F
0x180008374  xor     eax, eax
0x180008376  mov     [rsi+58h], rax
0x18000837a  jmp     def_1800080FF; jumptable 00000001800080FF default case, cases 4,6-8
0x18000837f  movd    xmm1, eax
0x180008383  movaps  xmm0, xmm6; X
0x180008386  cvtdq2pd xmm1, xmm1
0x18000838a  divsd   xmm1, xmm7; Y
0x18000838e  call    pow
0x180008393  lea     eax, [rdi+rdi*4]
0x180008396  xorps   xmm1, xmm1
0x180008399  shl     eax, 3
0x18000839c  cvtsi2sd xmm1, rdi
0x1800083a1  mulsd   xmm0, xmm1
0x1800083a5  cvttsd2si rcx, xmm0
0x1800083aa  cmp     rcx, rax
0x1800083ad  cmovle  rax, rcx
0x1800083b1  mov     [rsi+58h], rax
0x1800083b5  jmp     def_1800080FF; jumptable 00000001800080FF default case, cases 4,6-8
0x1800083ba  movzx   eax, word ptr [rdx+rbx+0Ah]
0x1800083bf  mov     [rsi+54h], ax
0x1800083c3  jmp     def_1800080FF; jumptable 00000001800080FF default case, cases 4,6-8
0x1800083c8  mov     eax, [rdx+rbx+8]
0x1800083cc  cmp     eax, 80000000h
0x1800083d1  jnz     short loc_1800083DE
0x1800083d3  xor     eax, eax
0x1800083d5  mov     [rsi+48h], rax
0x1800083d9  jmp     def_1800080FF; jumptable 00000001800080FF default case, cases 4,6-8
0x1800083de  movd    xmm1, eax
0x1800083e2  movaps  xmm0, xmm6; X
0x1800083e5  cvtdq2pd xmm1, xmm1
0x1800083e9  divsd   xmm1, xmm7; Y
0x1800083ed  call    pow
0x1800083f2  lea     eax, [rdi+rdi*4]
0x1800083f5  xorps   xmm1, xmm1
0x1800083f8  shl     eax, 3
0x1800083fb  cvtsi2sd xmm1, rdi
0x180008400  mulsd   xmm0, xmm1
0x180008404  cvttsd2si rcx, xmm0
0x180008409  cmp     rcx, rax
0x18000840c  cmovle  rax, rcx
0x180008410  mov     [rsi+48h], rax
0x180008414  jmp     def_1800080FF; jumptable 00000001800080FF default case, cases 4,6-8
0x180008419  mov     eax, [rdx+rbx+8]
0x18000841d  cmp     eax, 80000000h
0x180008422  jnz     short loc_18000842F
0x180008424  xor     eax, eax
0x180008426  mov     [rsi+40h], rax
0x18000842a  jmp     def_1800080FF; jumptable 00000001800080FF default case, cases 4,6-8
0x18000842f  movd    xmm1, eax
0x180008433  movaps  xmm0, xmm6; X
0x180008436  cvtdq2pd xmm1, xmm1
0x18000843a  divsd   xmm1, xmm7; Y
0x18000843e  call    pow
0x180008443  lea     eax, [rdi+rdi*4]
0x180008446  xorps   xmm1, xmm1
0x180008449  shl     eax, 3
0x18000844c  cvtsi2sd xmm1, rdi
0x180008451  mulsd   xmm0, xmm1
0x180008455  cvttsd2si rcx, xmm0
0x18000845a  cmp     rcx, rax
0x18000845d  cmovle  rax, rcx
0x180008461  mov     [rsi+40h], rax
0x180008465  jmp     def_1800080FF; jumptable 00000001800080FF default case, cases 4,6-8
0x18000846a  mov     eax, [rdx+rbx+8]
0x18000846e  cmp     eax, 80000000h
0x180008473  jnz     short loc_18000847F
0x180008475  xor     eax, eax
0x180008477  mov     [rsi], rax
0x18000847a  jmp     def_1800080FF; jumptable 00000001800080FF default case, cases 4,6-8
0x18000847f  movd    xmm1, eax
0x180008483  movaps  xmm0, xmm6; X
0x180008486  cvtdq2pd xmm1, xmm1
0x18000848a  divsd   xmm1, xmm7; Y
0x18000848e  call    pow
0x180008493  lea     eax, [rdi+rdi*4]
0x180008496  xorps   xmm1, xmm1
0x180008499  shl     eax, 3
0x18000849c  cvtsi2sd xmm1, rdi
0x1800084a1  mulsd   xmm0, xmm1
0x1800084a5  cvttsd2si rcx, xmm0
0x1800084aa  cmp     rcx, rax
0x1800084ad  cmovle  rax, rcx
0x1800084b1  mov     [rsi], rax
0x1800084b4  jmp     def_1800080FF; jumptable 00000001800080FF default case, cases 4,6-8
0x1800084b9  cmp     ecx, 30Fh
  ... truncated ...
```
