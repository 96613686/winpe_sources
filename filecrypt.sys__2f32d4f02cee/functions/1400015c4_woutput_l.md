# _woutput_l

- ea: `0x1400015c4`
- end: `0x140001ff8`
- name: `_woutput_l`
- size: `2612`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140001460`

## callees

- `0x1400015c4`
- `0x140002000`
- `0x140002058`
- `0x1400020c4`
- `0x140002280`
- `0x140003540`
- `0x140003640`

## pseudocode

```c
__int64 __fastcall woutput_l(__int64 a1, unsigned __int16 *a2, __int64 a3, int *a4)
{
  __int64 v4; // rsi
  __int64 v5; // r13
  wchar_t *v6; // rbx
  int *v7; // r15
  unsigned __int16 *v8; // r10
  int v9; // edi
  int v10; // r11d
  int v11; // r12d
  int v12; // r14d
  int *v13; // r8
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  unsigned __int64 v22; // r9
  __int64 v23; // rax
  char *v24; // rax
  unsigned int v25; // ecx
  int v26; // ecx
  const char *v27; // rax
  __int16 v28; // ax
  int v29; // eax
  int v30; // eax
  const wchar_t *v31; // rax
  const wchar_t *i; // r13
  unsigned __int64 v33; // r8
  char v34; // si
  char *v35; // rbx
  int v36; // ecx
  int v37; // edx
  unsigned int v38; // eax
  __int16 v39; // ax
  int v40; // ecx
  int v41; // r12d
  int v42; // r15d
  int v43; // esi
  __int64 v44; // r14
  unsigned __int16 *v45; // rsi
  int v46; // r14d
  __int64 v47; // rbx
  int v48; // esi
  __int64 v49; // rbx
  const char *v50; // r15
  int v51; // esi
  __int64 v52; // r14
  int v53; // r14d
  unsigned __int16 *v54; // rsi
  __int64 v55; // r12
  unsigned __int16 v56; // r9
  char *v58; // rsi
  unsigned __int64 v59; // rax
  __int64 v60; // rcx
  int v61; // eax
  int v62; // ecx
  int v63; // [rsp+30h] [rbp-D0h]
  int v64; // [rsp+34h] [rbp-CCh] BYREF
  int v65; // [rsp+38h] [rbp-C8h]
  int v66; // [rsp+3Ch] [rbp-C4h]
  wchar_t v67; // [rsp+40h] [rbp-C0h] BYREF
  int v68; // [rsp+44h] [rbp-BCh]
  __int64 v69; // [rsp+48h] [rbp-B8h]
  int *v70; // [rsp+50h] [rbp-B0h]
  const char *v71; // [rsp+58h] [rbp-A8h]
  char SrcCh[4]; // [rsp+60h] [rbp-A0h] BYREF
  _WORD v73[2]; // [rsp+64h] [rbp-9Ch] BYREF
  int v74; // [rsp+68h] [rbp-98h]
  __int64 v75; // [rsp+70h] [rbp-90h]
  unsigned __int16 *v76; // [rsp+78h] [rbp-88h]
  int v77; // [rsp+80h] [rbp-80h]
  int v78; // [rsp+84h] [rbp-7Ch]
  int v79; // [rsp+88h] [rbp-78h]
  int v80; // [rsp+8Ch] [rbp-74h]
  int v81; // [rsp+90h] [rbp-70h]
  wchar_t DstCh[512]; // [rsp+A0h] [rbp-60h] BYREF

  v76 = a2;
  v4 = a1;
  v69 = a1;
  LODWORD(v5) = 0;
  v6 = 0;
  v70 = a4;
  v71 = 0;
  v7 = a4;
  memset(DstCh, 0, sizeof(DstCh));
  v67 = 0;
  if ( v4 )
  {
    v8 = v76;
    if ( v76 )
    {
      v79 = 0;
      v9 = 0;
      v63 = 0;
      v10 = 0;
      v74 = 0;
      v11 = 0;
      v65 = 0;
      v12 = 0;
      v66 = 0;
      v78 = 0;
      v68 = 0;
      v64 = 0;
      v75 = 0;
      v80 = 0;
      while ( 1 )
      {
        while ( 1 )
        {
          while ( 1 )
          {
            while ( 1 )
            {
              v56 = *v8;
              if ( !*v8 || v12 < 0 )
                return (unsigned int)v12;
              v76 = ++v8;
              v13 = v7;
              if ( (unsigned __int16)(v56 - 32) > 0x5Au )
                v14 = 0;
              else
                v14 = _lookuptable[v56 - 32] & 0xF;
              v15 = _lookuptable[8 * v14 + v80] >> 4;
              v80 = v15;
              if ( !v15 )
                goto LABEL_192;
              v16 = v15 - 1;
              if ( v16 )
                break;
              v10 = -1;
              v78 = 0;
              v65 = -1;
              v11 = 0;
              v74 = 0;
              v9 = 0;
              v66 = 0;
              v63 = 0;
              v68 = 0;
            }
            v17 = v16 - 1;
            if ( v17 )
              break;
            switch ( v56 )
            {
              case ' ':
                v9 |= 2u;
                goto LABEL_218;
              case '#':
                v9 |= 0x80u;
                goto LABEL_218;
              case '+':
                v9 |= 1u;
                goto LABEL_218;
              case '-':
                v9 |= 4u;
                goto LABEL_218;
              case '0':
                v9 |= 8u;
                goto LABEL_218;
            }
          }
          v18 = v17 - 1;
          if ( v18 )
            break;
          if ( v56 == 42 )
          {
            v61 = *v7;
            v7 += 2;
            v70 = v7;
            if ( v61 < 0 )
            {
              v9 |= 4u;
              v63 = v9;
            }
            v62 = -v61;
            if ( v61 > 0 )
              v62 = v61;
          }
          else
          {
            v62 = v56 + 2 * (5 * v74 - 24);
          }
          v74 = v62;
        }
        v19 = v18 - 1;
        if ( !v19 )
          break;
        v20 = v19 - 1;
        if ( v20 )
        {
          v21 = v20 - 1;
          if ( v21 )
          {
            if ( v21 == 1 )
            {
              if ( v56 > 0x69u )
              {
                if ( v56 != 110 )
                {
                  switch ( v56 )
                  {
                    case 'o':
                      v22 = 8;
                      if ( (v9 & 0x80u) != 0 )
                      {
                        v9 |= 0x200u;
                        v63 = v9;
                      }
                      goto LABEL_26;
                    case 'p':
                      v9 |= 0x8000u;
                      v10 = 16;
                      v63 = v9;
LABEL_73:
                      v30 = 7;
LABEL_74:
                      v79 = v30;
                      if ( (v9 & 0x80u) != 0 )
                      {
                        v73[0] = 48;
                        v73[1] = v30 + 81;
                        v11 = 2;
                      }
                      v22 = 16;
LABEL_26:
                      v7 += 2;
                      v70 = v7;
                      if ( (v9 & 0x8000) != 0 || (v9 & 0x1000) != 0 )
                      {
                        v23 = *(_QWORD *)v13;
                        if ( (v9 & 0x40) != 0 )
                          goto LABEL_85;
LABEL_88:
                        v33 = (unsigned int)v23;
                        if ( (v9 & 0x9000) != 0 )
                          v33 = v23;
                        if ( v10 >= 0 )
                        {
                          v9 &= ~8u;
                          v63 = v9;
                          if ( v10 > 512 )
                            v10 = 512;
                        }
                        else
                        {
                          v10 = 1;
                        }
                        v34 = v79;
                        v35 = (char *)&DstCh[255] + 1;
                        v11 &= -(v33 != 0);
                        v66 = v11;
                        while ( 1 )
                        {
                          v36 = v10--;
                          if ( v36 <= 0 && !v33 )
                            break;
                          v37 = v33 % v22 + 48;
                          v33 /= v22;
                          if ( v37 > 57 )
                            LOBYTE(v37) = v34 + v37;
                          *v35-- = v37;
                        }
                        v4 = v69;
                        v38 = (unsigned int)&DstCh[48] + 415 - (_DWORD)v35;
                        v65 = v10;
                        v6 = (wchar_t *)(v35 + 1);
                        LODWORD(v5) = v38;
                        v75 = v38;
                        v71 = (const char *)v6;
                        if ( (v9 & 0x200) != 0 )
                        {
                          if ( !v38 || *(_BYTE *)v6 != 48 )
                          {
                            v6 = (wchar_t *)((char *)v6 - 1);
                            v70 = v7;
                            LODWORD(v5) = v38 + 1;
                            v71 = (const char *)v6;
                            v75 = v38 + 1;
                            *(_BYTE *)v6 = 48;
                          }
                        }
                        else
                        {
                          v70 = v7;
                        }
                        goto LABEL_105;
                      }
                      if ( (v9 & 0x20) != 0 )
                      {
                        if ( (v9 & 0x40) == 0 )
                        {
                          v23 = *(unsigned __int16 *)v13;
                          goto LABEL_88;
                        }
                        v23 = *(__int16 *)v13;
                      }
                      else
                      {
                        if ( (v9 & 0x40) == 0 )
                        {
                          v23 = (unsigned int)*v13;
                          goto LABEL_88;
                        }
                        v23 = *v13;
                      }
LABEL_85:
                      if ( v23 < 0 )
                      {
                        v23 = -v23;
                        v9 |= 0x100u;
                        v63 = v9;
                      }
                      goto LABEL_88;
                    case 's':
                      goto LABEL_42;
                    case 'u':
                      goto LABEL_25;
                    case 'x':
                      v30 = 39;
                      goto LABEL_74;
                  }
                  goto LABEL_105;
                }
                v58 = *(char **)v7;
                if ( !get_printf_count_output() )
                  return 0xFFFFFFFFLL;
                v7 += 2;
                v70 = v7;
                if ( (v9 & 0x20) != 0 )
                  *(_WORD *)v58 = v12;
                else
                  *(_DWORD *)v58 = v12;
                v4 = v69;
                v78 = 1;
LABEL_157:
                v8 = v76;
                v10 = v65;
              }
              else
              {
                switch ( v56 )
                {
                  case 'i':
                    goto LABEL_24;
                  case 'C':
                    if ( (v9 & 0x830) == 0 )
                    {
                      v9 |= 0x20u;
                      v63 = v9;
                    }
LABEL_49:
                    v28 = *(_WORD *)v7;
                    v7 += 2;
                    v70 = v7;
                    v67 = v28;
                    if ( (v9 & 0x20) != 0 )
                    {
                      SrcCh[0] = v28;
                      SrcCh[1] = 0;
                      v29 = mbtowc(DstCh, SrcCh, _mb_cur_max);
                      v8 = v76;
                      v10 = v65;
                      if ( v29 < 0 )
                        v78 = 1;
                    }
                    else
                    {
                      DstCh[0] = __PAIR16__(HIBYTE(v67), v28);
                    }
                    v68 = 1;
                    v6 = DstCh;
                    v5 = 1;
LABEL_38:
                    v71 = (const char *)v6;
                    v75 = v5;
                    break;
                  case 'S':
                    if ( (v9 & 0x830) == 0 )
                    {
                      v9 |= 0x20u;
                      v63 = v9;
                    }
LABEL_42:
                    v6 = *(wchar_t **)v7;
                    v26 = v10;
                    v71 = *(const char **)v7;
                    if ( v10 == -1 )
                      v26 = 0x7FFFFFFF;
                    v7 += 2;
                    v70 = v7;
                    if ( (v9 & 0x20) != 0 )
                    {
                      LODWORD(v5) = 0;
                      if ( v6 )
                      {
                        v27 = (const char *)v6;
                      }
                      else
                      {
                        v6 = (wchar_t *)"(null)";
                        v71 = "(null)";
                        v27 = "(null)";
                      }
                      v75 = 0;
                      if ( v26 > 0 )
                      {
                        do
                        {
                          if ( !*v27 )
                            break;
                          v5 = (unsigned int)(v5 + 1);
                          ++v27;
                          v75 = v5;
                        }
                        while ( (int)v5 < v26 );
                      }
                    }
                    else
                    {
                      v68 = 1;
                      v31 = L"(null)";
                      if ( v6 )
                        v31 = v6;
                      v71 = (const char *)v31;
                      v6 = (wchar_t *)v31;
                      for ( i = v31; v26; --v26 )
                      {
                        if ( !*i )
                          break;
                        ++i;
                      }
                      v5 = i - v31;
                      v75 = v5;
                    }
                    break;
                  case 'X':
                    goto LABEL_73;
                  case 'Z':
                    v24 = *(char **)v7;
                    v7 += 2;
                    v70 = v7;
                    if ( v24 && (v6 = (wchar_t *)*((_QWORD *)v24 + 1), (v71 = (const char *)v6) != 0) )
                    {
                      v25 = *(unsigned __int16 *)v24;
                      if ( *((_WORD *)v24 + 1) < (unsigned __int16)v25 )
                        return 0xFFFFFFFFLL;
                      if ( (v9 & 0x800) != 0 )
                      {
                        if ( (v25 & 1) != 0 || ((unsigned __int8)v6 & 1) != 0 )
                          return 0xFFFFFFFFLL;
                        v68 = 1;
                        LODWORD(v5) = v25 >> 1;
                        v75 = v25 >> 1;
                        break;
                      }
                      v68 = 0;
                      v5 = v25;
                    }
                    else
                    {
                      v6 = (wchar_t *)"(null)";
                      v5 = 6;
                    }
                    goto LABEL_38;
                  case 'c':
                    goto LABEL_49;
                  case 'd':
LABEL_24:
                    v9 |= 0x40u;
                    v63 = v9;
LABEL_25:
                    v22 = 10;
                    goto LABEL_26;
                }
LABEL_105:
                if ( !v78 )
                {
                  if ( (v9 & 0x40) != 0 )
                  {
                    if ( (v9 & 0x100) != 0 )
                    {
                      v39 = 45;
                      goto LABEL_111;
                    }
                    if ( (v9 & 1) != 0 )
                    {
                      v39 = 43;
LABEL_111:
                      v73[0] = v39;
LABEL_112:
                      v40 = 1;
                      v66 = 1;
LABEL_116:
                      v41 = v74 - v5 - v40;
                      v42 = v9 & 0xC;
                      v77 = v41;
                      v81 = v42;
                      if ( (v9 & 0xC) == 0 )
                      {
                        v43 = v74 - v5 - v40;
                        if ( v41 > 0 )
                        {
                          v44 = v69;
                          do
                          {
                            write_char(32, v44, &v64);
                            if ( v64 == -1 )
                              break;
                            --v43;
                          }
                          while ( v43 > 0 );
                          v6 = (wchar_t *)v71;
                          LODWORD(v5) = v75;
                          v12 = v64;
                          v40 = v66;
                        }
                        v4 = v69;
                      }
                      if ( (*(_DWORD *)(v4 + 24) & 0x40) == 0 || *(_QWORD *)(v4 + 16) )
                      {
                        v45 = v73;
                        v46 = v40;
                        if ( v40 > 0 )
                        {
                          v47 = v69;
                          do
                          {
                            write_char(*v45, v47, &v64);
                            if ( v64 == -1 )
                              break;
                            --v46;
                            ++v45;
                          }
                          while ( v46 > 0 );
                          v6 = (wchar_t *)v71;
                          v42 = v81;
                          v41 = v77;
                        }
                      }
                      else
                      {
                        v64 = v40 + v12;
                      }
                      if ( v42 == 8 )
                      {
                        v48 = v41;
                        if ( v41 > 0 )
                        {
                          v49 = v69;
                          do
                          {
                            write_char(48, v49, &v64);
                            if ( v64 == -1 )
                              break;
                            --v48;
                          }
                          while ( v48 > 0 );
                          v6 = (wchar_t *)v71;
                          v9 = v63;
                          v41 = v77;
                          LODWORD(v5) = v75;
                        }
                      }
                      if ( !v68 && (int)v5 > 0 )
                      {
                        v50 = (const char *)v6;
                        v51 = v5;
                        while ( 1 )
                        {
                          v52 = mbtowc(&v67, v50, _mb_cur_max);
                          if ( (int)v52 <= 0 )
                            break;
                          v51 -= ((_DWORD)v52 == 2) + 1;
                          write_char(v67, v69, &v64);
                          v50 += v52;
                          if ( v51 <= 0 )
                            goto LABEL_152;
                        }
                        v12 = -1;
                        v64 = -1;
                        goto LABEL_153;
                      }
                      v4 = v69;
                      if ( (*(_DWORD *)(v69 + 24) & 0x40) == 0 || *(_QWORD *)(v69 + 16) )
                      {
                        v53 = v5;
                        v54 = v6;
                        if ( (int)v5 > 0 )
                        {
                          v55 = v69;
                          do
                          {
                            write_char(*v54, v55, &v64);
                            if ( v64 == -1 )
                              break;
                            --v53;
                            ++v54;
                          }
                          while ( v53 > 0 );
                          v6 = (wchar_t *)v71;
                          v41 = v77;
                        }
LABEL_152:
                        v12 = v64;
LABEL_153:
                        v4 = v69;
                      }
                      else
                      {
                        v12 = v5 + v64;
                        v64 += v5;
                      }
                      if ( v12 >= 0 && (v9 & 4) != 0 )
                      {
                        while ( v41 > 0 )
                        {
                          write_char(32, v4, &v64);
                          v12 = v64;
                          if ( v64 == -1 )
                            break;
                          --v41;
                        }
                      }
                      v7 = v70;
                      v11 = v66;
                      goto LABEL_157;
                    }
                    if ( (v9 & 2) != 0 )
                    {
                      v73[0] = 32;
                      goto LABEL_112;
                    }
                  }
                  v40 = v66;
                  goto LABEL_116;
                }
              }
            }
          }
          else
          {
            switch ( v56 )
            {
              case 'I':
                goto LABEL_176;
              case 'h':
                v9 |= 0x20u;
                goto LABEL_218;
              case 'j':
                goto LABEL_176;
              case 'l':
                if ( *v8 == 108 )
                {
                  ++v8;
                  v9 |= 0x1000u;
                }
                else
                {
                  v9 |= 0x10u;
                }
                goto LABEL_218;
              case 't':
                goto LABEL_176;
              case 'w':
                v9 |= 0x800u;
                goto LABEL_218;
              case 'z':
LABEL_176:
                v9 |= 0x8000u;
                v63 = v9;
                if ( v56 == 73 )
                {
                  if ( *v8 == 54 )
                  {
                    if ( v8[1] != 52 )
                      goto LABEL_189;
                    v8 += 2;
                  }
                  else
                  {
                    if ( *v8 != 51 || v8[1] != 50 )
                      goto LABEL_189;
                    v8 += 2;
                    v9 &= ~0x8000u;
LABEL_218:
                    v63 = v9;
                  }
                }
                else if ( v56 != 106 )
                {
LABEL_189:
                  v59 = *v8;
                  LOWORD(v59) = v59 - 88;
                  if ( (unsigned __int16)v59 > 0x20u || (v60 = 0x120821001LL, !_bittest64(&v60, v59)) )
                  {
                    v80 = 0;
LABEL_192:
                    v68 = 1;
                    write_char(v56, v4, &v64);
                    v12 = v64;
                    goto LABEL_157;
                  }
                }
                break;
            }
          }
        }
        else
        {
          if ( v56 == 42 )
          {
            v10 = *v7;
            v7 += 2;
            v70 = v7;
            if ( v10 < 0 )
              v10 = -1;
          }
          else
          {
            v10 = v56 + 2 * (5 * v10 - 24);
          }
LABEL_199:
          v65 = v10;
        }
      }
      v10 = 0;
      goto LABEL_199;
    }
  }
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x1400015c4  mov     [rsp-8+arg_10], rbx
0x1400015c9  push    rbp
0x1400015ca  push    rsi
0x1400015cb  push    rdi
0x1400015cc  push    r12
0x1400015ce  push    r13
0x1400015d0  push    r14
0x1400015d2  push    r15
0x1400015d4  lea     rbp, [rsp-3B0h]
0x1400015dc  sub     rsp, 4B0h
0x1400015e3  mov     rax, cs:__security_cookie
0x1400015ea  xor     rax, rsp
0x1400015ed  mov     [rbp+3E0h+var_40], rax
0x1400015f4  mov     [rsp+4E0h+var_468], rdx
0x1400015f9  mov     rsi, rcx
0x1400015fc  mov     [rsp+4E0h+var_498], rcx
0x140001601  xor     r13d, r13d
0x140001604  mov     ebx, r13d
0x140001607  mov     [rsp+4E0h+var_490], r9
0x14000160c  xor     edx, edx; Val
0x14000160e  mov     [rsp+4E0h+var_488], rbx
0x140001613  mov     r8d, 400h; Size
0x140001619  lea     rcx, [rbp+3E0h+DstCh]; void *
0x14000161d  mov     r15, r9
0x140001620  call    memset
0x140001625  mov     [rsp+4E0h+var_4A0], r13w
0x14000162b  test    rsi, rsi
0x14000162e  jz      loc_140001FB6
0x140001634  mov     r10, [rsp+4E0h+var_468]
0x140001639  test    r10, r10
0x14000163c  jz      loc_140001FB6
0x140001642  mov     [rbp+3E0h+var_458], r13d
0x140001646  mov     edi, r13d
0x140001649  mov     [rsp+4E0h+var_4B0], r13d
0x14000164e  mov     r11d, r13d
0x140001651  mov     [rsp+4E0h+var_478], r13d
0x140001656  mov     r12d, r13d
0x140001659  mov     [rsp+4E0h+var_4A8], r13d
0x14000165e  mov     r14d, r13d
0x140001661  mov     [rsp+4E0h+var_4A4], r13d
0x140001666  mov     [rbp+3E0h+var_45C], r13d
0x14000166a  mov     [rsp+4E0h+var_49C], r13d
0x14000166f  mov     [rsp+4E0h+var_4AC], r13d
0x140001674  mov     [rsp+4E0h+var_470], r13
0x140001679  mov     [rbp+3E0h+var_454], ebx
0x14000167c  jmp     loc_140001D4B
0x140001681  test    r14d, r14d
0x140001684  js      loc_140001D59
0x14000168a  add     r10, 2
0x14000168e  movzx   edx, r9w
0x140001692  lea     eax, [r9-20h]
0x140001696  mov     [rsp+4E0h+var_468], r10
0x14000169b  mov     r8, r15
0x14000169e  cmp     ax, 5Ah ; 'Z'
0x1400016a2  ja      short loc_1400016B5
0x1400016a4  lea     rcx, __lookuptable
0x1400016ab  movsx   ecx, byte ptr [rdx+rcx-20h]
0x1400016b0  and     ecx, 0Fh
0x1400016b3  jmp     short loc_1400016B7
0x1400016b5  xor     ecx, ecx
0x1400016b7  mov     eax, [rbp+3E0h+var_454]
0x1400016ba  lea     eax, [rax+rcx*8]
0x1400016bd  movsxd  rcx, eax
0x1400016c0  lea     rax, __lookuptable
0x1400016c7  movsx   ecx, byte ptr [rcx+rax]
0x1400016cb  sar     ecx, 4
0x1400016ce  mov     [rbp+3E0h+var_454], ecx
0x1400016d1  test    ecx, ecx
0x1400016d3  jz      loc_140001E9E
0x1400016d9  sub     ecx, 1
0x1400016dc  jz      loc_140001F84
0x1400016e2  sub     ecx, 1
0x1400016e5  jz      loc_140001F3A
0x1400016eb  sub     ecx, 1
0x1400016ee  jz      loc_140001EFD
0x1400016f4  sub     ecx, 1
0x1400016f7  jz      loc_140001EF0
0x1400016fd  sub     ecx, 1
0x140001700  jz      loc_140001EC1
0x140001706  sub     ecx, 1
0x140001709  jz      loc_140001DBE
0x14000170f  cmp     ecx, 1
0x140001712  jnz     loc_140001D4B
0x140001718  cmp     r9w, 69h ; 'i'
0x14000171d  ja      loc_1400018F8
0x140001723  jz      short loc_140001756
0x140001725  sub     edx, 43h ; 'C'
0x140001728  jz      loc_14000187A
0x14000172e  sub     edx, 10h
0x140001731  jz      loc_140001818
0x140001737  sub     edx, 5
0x14000173a  jz      loc_1400019BD
0x140001740  sub     edx, 2
0x140001743  jz      short loc_140001793
0x140001745  sub     edx, 9
0x140001748  jz      loc_140001889
0x14000174e  cmp     edx, ecx
0x140001750  jnz     loc_140001B08
0x140001756  or      edi, 40h
0x140001759  mov     [rsp+4E0h+var_4B0], edi
0x14000175d  mov     r9d, 0Ah
0x140001763  mov     edx, 200h
0x140001768  add     r15, 8
0x14000176c  mov     [rsp+4E0h+var_490], r15
0x140001771  bt      edi, 0Fh
0x140001775  jb      short loc_140001781
0x140001777  bt      edi, 0Ch
0x14000177b  jnb     loc_140001A0D
0x140001781  mov     rax, [r8]
0x140001784  test    dil, 40h
0x140001788  jz      loc_140001A44
0x14000178e  jmp     loc_140001A2F
0x140001793  mov     rax, [r8]
0x140001796  add     r15, 8
0x14000179a  xor     r13d, r13d
0x14000179d  mov     [rsp+4E0h+var_490], r15
0x1400017a2  test    rax, rax
0x1400017a5  jz      short loc_140001809
0x1400017a7  mov     rbx, [rax+8]
0x1400017ab  mov     [rsp+4E0h+var_488], rbx
0x1400017b0  test    rbx, rbx
0x1400017b3  jz      short loc_140001809
0x1400017b5  movzx   ecx, word ptr [rax]
0x1400017b8  cmp     [rax+2], cx
0x1400017bc  jb      loc_140001FB6
0x1400017c2  bt      edi, 0Bh
0x1400017c6  jnb     short loc_1400017F2
0x1400017c8  test    cl, 1
0x1400017cb  jnz     loc_140001FB6
0x1400017d1  test    bl, 1
0x1400017d4  jnz     loc_140001FB6
0x1400017da  mov     r13d, ecx
0x1400017dd  mov     [rsp+4E0h+var_49C], 1
0x1400017e5  shr     r13d, 1
0x1400017e8  mov     [rsp+4E0h+var_470], r13
0x1400017ed  jmp     loc_140001B08
0x1400017f2  mov     [rsp+4E0h+var_49C], r13d
0x1400017f7  mov     r13d, ecx
0x1400017fa  mov     [rsp+4E0h+var_488], rbx
0x1400017ff  mov     [rsp+4E0h+var_470], r13
0x140001804  jmp     loc_140001B08
0x140001809  lea     rbx, SrcCh; "(null)"
0x140001810  mov     r13d, 6
0x140001816  jmp     short loc_1400017FA
0x140001818  test    edi, 830h
0x14000181e  jnz     short loc_140001827
0x140001820  or      edi, 20h
0x140001823  mov     [rsp+4E0h+var_4B0], edi
0x140001827  mov     rbx, [r8]
0x14000182a  cmp     r11d, 0FFFFFFFFh
0x14000182e  mov     ecx, r11d
0x140001831  mov     [rsp+4E0h+var_488], rbx
0x140001836  mov     eax, 7FFFFFFFh
0x14000183b  mov     r8d, 20h ; ' '
0x140001841  cmovz   ecx, eax
0x140001844  add     r15, 8
0x140001848  mov     [rsp+4E0h+var_490], r15
0x14000184d  test    r8b, dil
0x140001850  jz      loc_140001967
0x140001856  xor     r13d, r13d
0x140001859  test    rbx, rbx
0x14000185c  jnz     loc_140001936
0x140001862  lea     rbx, SrcCh; "(null)"
0x140001869  mov     [rsp+4E0h+var_488], rbx
0x14000186e  lea     rax, SrcCh; "(null)"
0x140001875  jmp     loc_140001939
0x14000187a  test    edi, 830h
0x140001880  jnz     short loc_140001889
0x140001882  or      edi, 20h
0x140001885  mov     [rsp+4E0h+var_4B0], edi
0x140001889  movzx   eax, word ptr [r8]
0x14000188d  add     r15, 8
0x140001891  mov     [rsp+4E0h+var_490], r15
0x140001896  mov     [rsp+4E0h+var_4A0], ax
0x14000189b  test    dil, 20h
0x14000189f  jz      short loc_1400018D7
0x1400018a1  movsxd  r8, cs:__mb_cur_max; SrcSizeInBytes
0x1400018a8  lea     rdx, [rsp+4E0h+SrcCh]; SrcCh
0x1400018ad  xor     ebx, ebx
0x1400018af  mov     [rsp+4E0h+SrcCh], al
0x1400018b3  lea     rcx, [rbp+3E0h+DstCh]; DstCh
0x1400018b7  mov     [rsp+4E0h+var_47F], bl
0x1400018bb  call    mbtowc
0x1400018c0  mov     r10, [rsp+4E0h+var_468]
0x1400018c5  mov     r11d, [rsp+4E0h+var_4A8]
0x1400018ca  test    eax, eax
0x1400018cc  jns     short loc_1400018E1
0x1400018ce  mov     [rbp+3E0h+var_45C], 1
0x1400018d5  jmp     short loc_1400018E1
0x1400018d7  mov     byte ptr [rbp+3E0h+DstCh], al
0x1400018da  mov     al, byte ptr [rsp+4E0h+var_4A0+1]
0x1400018de  mov     byte ptr [rbp+3E0h+DstCh+1], al
0x1400018e1  mov     [rsp+4E0h+var_49C], 1
0x1400018e9  lea     rbx, [rbp+3E0h+DstCh]
0x1400018ed  mov     r13d, 1
0x1400018f3  jmp     loc_1400017FA
0x1400018f8  sub     edx, 6Eh ; 'n'
0x1400018fb  jz      loc_140001D88
0x140001901  sub     edx, 1
0x140001904  jz      loc_1400019EC
0x14000190a  sub     edx, 1
0x14000190d  jz      loc_1400019AF
0x140001913  sub     edx, 3
0x140001916  jz      loc_140001827
0x14000191c  sub     edx, 2
0x14000191f  jz      loc_14000175D
0x140001925  cmp     edx, 3
0x140001928  jnz     loc_140001B08
0x14000192e  lea     eax, [rdx+24h]
0x140001931  jmp     loc_1400019C2
0x140001936  mov     rax, rbx
0x140001939  xor     r9d, r9d
0x14000193c  mov     [rsp+4E0h+var_470], r13
0x140001941  test    ecx, ecx
0x140001943  jle     loc_140001B11
0x140001949  cmp     [rax], r9b
0x14000194c  jz      loc_140001B11
0x140001952  inc     r13d
0x140001955  inc     rax
0x140001958  mov     [rsp+4E0h+var_470], r13
0x14000195d  cmp     r13d, ecx
0x140001960  jl      short loc_140001949
0x140001962  jmp     loc_140001B11
0x140001967  test    rbx, rbx
0x14000196a  mov     [rsp+4E0h+var_49C], 1
0x140001972  lea     rax, aNull_0; "(null)"
0x140001979  cmovnz  rax, rbx
0x14000197d  xor     r9d, r9d
0x140001980  mov     [rsp+4E0h+var_488], rax
0x140001985  mov     rbx, rax
0x140001988  mov     r13, rax
0x14000198b  test    ecx, ecx
0x14000198d  jz      short loc_14000199F
0x14000198f  cmp     [r13+0], r9w
0x140001994  jz      short loc_14000199F
0x140001996  add     r13, 2
0x14000199a  sub     ecx, 1
0x14000199d  jnz     short loc_14000198F
0x14000199f  sub     r13, rax
0x1400019a2  sar     r13, 1
0x1400019a5  mov     [rsp+4E0h+var_470], r13
0x1400019aa  jmp     loc_140001B11
0x1400019af  bts     edi, 0Fh
0x1400019b3  mov     r11d, 10h
0x1400019b9  mov     [rsp+4E0h+var_4B0], edi
0x1400019bd  mov     eax, 7
0x1400019c2  mov     [rbp+3E0h+var_458], eax
0x1400019c5  test    dil, dil
0x1400019c8  jns     short loc_1400019E1
0x1400019ca  mov     ecx, 30h ; '0'
0x1400019cf  add     ax, 51h ; 'Q'
0x1400019d3  mov     [rsp+4E0h+var_47C], cx
0x1400019d8  mov     [rsp+4E0h+var_47A], ax
0x1400019dd  lea     r12d, [rcx-2Eh]
0x1400019e1  mov     r9d, 10h
0x1400019e7  jmp     loc_140001763
0x1400019ec  mov     eax, 8
0x1400019f1  mov     r9d, eax
0x1400019f4  test    dil, dil
0x1400019f7  jns     loc_140001763
0x1400019fd  mov     edx, 200h
0x140001a02  or      edi, edx
0x140001a04  mov     [rsp+4E0h+var_4B0], edi
0x140001a08  jmp     loc_140001768
0x140001a0d  mov     eax, edi
0x140001a0f  and     eax, 40h
0x140001a12  test    dil, 20h
0x140001a16  jz      short loc_140001A28
0x140001a18  test    eax, eax
0x140001a1a  jz      short loc_140001A22
0x140001a1c  movsx   rax, word ptr [r8]
0x140001a20  jmp     short loc_140001A2F
0x140001a22  movzx   eax, word ptr [r8]
0x140001a26  jmp     short loc_140001A44
0x140001a28  test    eax, eax
0x140001a2a  jz      short loc_140001A41
0x140001a2c  movsxd  rax, dword ptr [r8]
0x140001a2f  test    rax, rax
0x140001a32  jns     short loc_140001A44
0x140001a34  neg     rax
0x140001a37  bts     edi, 8
0x140001a3b  mov     [rsp+4E0h+var_4B0], edi
0x140001a3f  jmp     short loc_140001A44
0x140001a41  mov     eax, [r8]
0x140001a44  test    edi, 9000h
0x140001a4a  mov     r8d, eax
0x140001a4d  cmovnz  r8, rax
0x140001a51  test    r11d, r11d
0x140001a54  jns     short loc_140001A5E
0x140001a56  mov     r11d, 1
0x140001a5c  jmp     short loc_140001A6C
0x140001a5e  and     edi, 0FFFFFFF7h
0x140001a61  cmp     r11d, edx
0x140001a64  mov     [rsp+4E0h+var_4B0], edi
0x140001a68  cmovg   r11d, edx
0x140001a6c  mov     esi, [rbp+3E0h+var_458]
0x140001a6f  lea     rbx, [rbp+3E0h+var_241]
0x140001a76  mov     rax, r8
0x140001a79  neg     rax
0x140001a7c  sbb     ecx, ecx
  ... truncated ...
```
