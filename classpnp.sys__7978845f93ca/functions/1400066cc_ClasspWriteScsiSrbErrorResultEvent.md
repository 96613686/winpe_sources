# ClasspWriteScsiSrbErrorResultEvent

- ea: `0x1400066cc`
- end: `0x140006f4d`
- name: `ClasspWriteScsiSrbErrorResultEvent`
- size: `2177`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140005560`
- `0x1400073d4`

## callees

- `0x1400066cc`
- `0x140007000`
- `0x14003e430`

## pseudocode

```c
void __fastcall ClasspWriteScsiSrbErrorResultEvent(int a1, __int64 a2, int a3, __int64 a4, char a5)
{
  __int64 v5; // r13
  int v6; // edi
  _DWORD *v7; // rsi
  char v8; // al
  char v9; // r14
  char *v10; // rcx
  char v11; // al
  char v12; // dl
  unsigned int v13; // r11d
  __int64 v14; // r10
  char v15; // bl
  __int64 v16; // rcx
  unsigned __int64 v17; // r8
  __int64 v18; // rdx
  int v19; // ecx
  unsigned int v20; // r11d
  __int64 v21; // r10
  char v22; // bl
  __int64 v23; // rcx
  unsigned __int64 v24; // r8
  __int64 v25; // rdx
  int v26; // ecx
  int v27; // ecx
  __int64 v28; // rcx
  unsigned __int8 v29; // r8
  int v30; // ecx
  unsigned int v31; // ebx
  __int64 v32; // r11
  char v33; // di
  __int64 v34; // rcx
  unsigned __int64 v35; // r10
  __int64 v36; // rdx
  int v37; // ecx
  int v38; // ecx
  __int64 v39; // r11
  _DWORD *v40; // rax
  __int64 v41; // rbx
  __int64 v42; // rdi
  char v43; // bp
  char *v44; // rcx
  char v45; // r12
  char v46; // r15
  __int64 v47; // r13
  __int64 v48; // r8
  unsigned int v49; // ecx
  int v50; // edx
  __int64 v51; // r8
  int v52; // edx
  __int64 v53; // r8
  int v54; // edx
  __int64 v55; // rdx
  char *v56; // r8
  bool v57; // zf
  _BYTE *v58; // rdx
  unsigned int v59; // edi
  __int64 v60; // r11
  char v61; // bl
  unsigned __int64 v62; // r10
  __int64 v63; // r8
  int v64; // ecx
  unsigned __int8 v65; // r8
  unsigned int v66; // edi
  __int64 v67; // rbx
  char v68; // si
  unsigned __int64 v69; // r11
  __int64 v70; // r10
  int v71; // ecx
  char *v72; // rax
  unsigned int v73; // eax
  unsigned __int64 v74; // r8
  char v75; // [rsp+91h] [rbp-97h]
  char v76; // [rsp+92h] [rbp-96h]
  __int64 v78; // [rsp+98h] [rbp-90h]
  int v79; // [rsp+A0h] [rbp-88h]
  __int64 v80; // [rsp+A8h] [rbp-80h]
  __int64 v81; // [rsp+B0h] [rbp-78h]
  __int64 v82; // [rsp+B8h] [rbp-70h]
  __int64 v83; // [rsp+C0h] [rbp-68h]
  int v84; // [rsp+C8h] [rbp-60h]
  __int128 v86; // [rsp+D8h] [rbp-50h] BYREF

  v5 = *(_QWORD *)(a2 + 64);
  v6 = a3;
  v83 = v5;
  v86 = 0;
  if ( !v5 )
    return;
  v7 = (_DWORD *)(a4 + 20);
  v8 = *(_BYTE *)(a4 + 2);
  v79 = 0;
  v76 = 0;
  v75 = v8;
  if ( v8 != 40 )
  {
    v9 = *(_BYTE *)(a4 + 4);
    v10 = (char *)(a4 + 72);
    v78 = a4 + 72;
    goto LABEL_4;
  }
  v9 = 0;
  if ( !*v7 )
  {
    v13 = *(_DWORD *)(a4 + 56);
    if ( v13 )
    {
      v14 = 0;
      v15 = 0;
      while ( 1 )
      {
        v16 = *(unsigned int *)(a4 + 4 * v14 + 120);
        if ( (unsigned int)v16 >= 0x80 )
        {
          v17 = *(unsigned int *)(a4 + 16);
          if ( (unsigned int)v16 < (unsigned int)v17 )
            break;
        }
LABEL_50:
        v14 = (unsigned int)(v14 + 1);
        if ( (unsigned int)v14 >= v13 )
          goto LABEL_23;
      }
      v18 = (unsigned int)v16;
      v19 = *(_DWORD *)(v16 + a4) - 64;
      if ( !v19 )
        goto LABEL_21;
      v30 = v19 - 1;
      if ( v30 )
      {
        if ( v30 == 1 )
        {
LABEL_21:
          if ( v18 + 40 <= v17 )
          {
            v9 = *(_BYTE *)(v18 + a4 + 8);
            goto LABEL_23;
          }
        }
      }
      else if ( v18 + 56 <= v17 )
      {
        v9 = *(_BYTE *)(v18 + a4 + 8);
        v15 = 1;
      }
      if ( v15 )
        goto LABEL_23;
      goto LABEL_50;
    }
  }
LABEL_23:
  v10 = 0;
  v78 = 0;
  if ( *v7 )
    goto LABEL_4;
  v20 = *(_DWORD *)(a4 + 56);
  if ( !v20 )
    goto LABEL_4;
  v21 = 0;
  v22 = 0;
  while ( 1 )
  {
    v23 = *(unsigned int *)(a4 + 4 * v21 + 120);
    if ( (unsigned int)v23 >= 0x80 )
    {
      v24 = *(unsigned int *)(a4 + 16);
      if ( (unsigned int)v23 < (unsigned int)v24 )
        break;
    }
LABEL_45:
    v21 = (unsigned int)(v21 + 1);
    if ( (unsigned int)v21 >= v20 )
      goto LABEL_46;
  }
  v25 = (unsigned int)v23;
  v26 = *(_DWORD *)(v23 + a4) - 64;
  if ( v26 )
  {
    v27 = v26 - 1;
    if ( v27 )
    {
      if ( v27 == 1 && v25 + 40 <= v24 )
      {
        if ( *(_DWORD *)(v25 + a4 + 12) )
        {
          v28 = a4 + 32;
          goto LABEL_49;
        }
LABEL_46:
        v10 = (char *)v78;
        goto LABEL_4;
      }
    }
    else if ( v25 + 56 <= v24 )
    {
      if ( !*(_BYTE *)(v25 + a4 + 10) )
        goto LABEL_46;
      v22 = 1;
      v10 = (char *)(v25 + a4 + 24);
      v78 = (__int64)v10;
      goto LABEL_31;
    }
LABEL_30:
    v10 = (char *)v78;
LABEL_31:
    if ( v22 )
      goto LABEL_4;
    goto LABEL_45;
  }
  if ( v25 + 40 > v24 )
    goto LABEL_30;
  if ( !*(_BYTE *)(v25 + a4 + 10) )
    goto LABEL_46;
  v28 = a4 + 24;
LABEL_49:
  v10 = (char *)(v25 + v28);
  v78 = (__int64)v10;
LABEL_4:
  if ( v10 )
  {
    v76 = *v10;
    if ( v8 != 40 )
    {
      v29 = *(_BYTE *)(a4 + 10);
      goto LABEL_41;
    }
    v29 = 0;
    if ( !*v7 )
    {
      v31 = *(_DWORD *)(a4 + 56);
      if ( v31 )
      {
        v32 = 0;
        v33 = 0;
        while ( 1 )
        {
          v34 = *(unsigned int *)(a4 + 4 * v32 + 120);
          if ( (unsigned int)v34 >= 0x80 )
          {
            v35 = *(unsigned int *)(a4 + 16);
            if ( (unsigned int)v34 < (unsigned int)v35 )
            {
              v36 = (unsigned int)v34;
              v37 = *(_DWORD *)(v34 + a4) - 64;
              if ( v37 )
              {
                v38 = v37 - 1;
                if ( v38 )
                {
                  if ( v38 == 1 && v36 + 40 <= v35 )
                    goto LABEL_60;
                }
                else if ( v36 + 56 <= v35 )
                {
                  v29 = *(_BYTE *)(v36 + a4 + 10);
                  v33 = 1;
                }
              }
              else if ( v36 + 40 <= v35 )
              {
                v29 = *(_BYTE *)(v36 + a4 + 10);
LABEL_60:
                v6 = a3;
                break;
              }
              if ( v33 )
                goto LABEL_60;
            }
          }
          v32 = (unsigned int)(v32 + 1);
          if ( (unsigned int)v32 >= v31 )
            goto LABEL_60;
        }
      }
    }
LABEL_41:
    v79 = v29;
  }
  if ( v6 == -1073741306
    || v6 == -2147483643
    || v6 == -1073741822
    || v6 == -1073741820
    || v6 == -1073741808
    || v6 == -1073741789
    || v6 == -1073741637
    || (v11 = 0, v6 == -1073740701) )
  {
    v11 = 1;
  }
  v12 = *(_BYTE *)(a4 + 3);
  if ( v12 != 18 && !v11 )
  {
    v39 = 0;
    v40 = *(_DWORD **)(v5 + 520);
    v41 = 0;
    v42 = 0;
    v80 = 0;
    v43 = 0;
    v81 = 0;
    v44 = *(char **)(v5 + 1168);
    v45 = 0;
    v46 = 0;
    v82 = 0;
    v47 = 0;
    if ( v44 )
      LODWORD(v44) = (_DWORD)v44 + 4;
    else
      v44 = (char *)&v86;
    v84 = (int)v44;
    if ( v40 )
    {
      v48 = (unsigned int)v40[3];
      v49 = v40[1];
      if ( (_DWORD *)((char *)v40 + v48) < v40 || (unsigned int)v48 > v49 )
        v50 = 0;
      else
        v50 = v49 - v48;
      if ( (_DWORD)v48 )
      {
        if ( v50 )
          v39 = (__int64)v40 + v48;
        v80 = v39;
      }
      v51 = (unsigned int)v40[4];
      if ( (_DWORD *)((char *)v40 + v51) < v40 || (unsigned int)v51 > v49 )
        v52 = 0;
      else
        v52 = v49 - v51;
      if ( (_DWORD)v51 )
      {
        if ( v52 )
          v41 = (__int64)v40 + v51;
        v81 = v41;
      }
      v53 = (unsigned int)v40[5];
      if ( (_DWORD *)((char *)v40 + v53) < v40 || (unsigned int)v53 > v49 )
        v54 = 0;
      else
        v54 = v49 - v53;
      if ( (_DWORD)v53 )
      {
        if ( v54 )
          v42 = (__int64)v40 + v53;
        v82 = v42;
      }
      v55 = (unsigned int)v40[6];
      v56 = (char *)v40 + v55;
      if ( (_DWORD *)((char *)v40 + v55) < v40 || (unsigned int)v55 > v49 )
        LODWORD(v44) = 0;
      else
        LODWORD(v44) = v49 - v55;
      v57 = (_DWORD)v55 == 0;
      v12 = *(_BYTE *)(a4 + 3);
      if ( !v57 && (_DWORD)v44 )
        v47 = (__int64)v56;
    }
    if ( v12 >= 0 )
    {
LABEL_105:
      LOBYTE(v44) = v76;
      if ( ((v76 - 8) & 0x5F) != 0 )
      {
        LOBYTE(v44) = v76 - 10;
        if ( ((v76 - 10) & 0x5F) != 0 )
        {
          if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 4) != 0 )
            McTemplateK0jqssssduuuuuqbr12u_EtwWriteTransfer(
              (_DWORD)v44,
              (unsigned int)EventSrbScsiNonReadWriteFailure,
              a1,
              v84,
              *(_DWORD *)(v83 + 588),
              v39,
              v41,
              v42,
              v47,
              a3,
              v12,
              v9,
              v43,
              v45,
              v46,
              v79,
              v78,
              a5);
        }
        else if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 2) != 0 )
        {
          McTemplateK0jqssssduuuuuqbr12u_EtwWriteTransfer(
            (_DWORD)v44,
            (unsigned int)EventSrbScsiWriteFailure,
            a1,
            v84,
            *(_DWORD *)(v83 + 588),
            v39,
            v41,
            v42,
            v47,
            a3,
            v12,
            v9,
            v43,
            v45,
            v46,
            v79,
            v78,
            a5);
        }
      }
      else if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 1) != 0 )
      {
        McTemplateK0jqssssduuuuuqbr12u_EtwWriteTransfer(
          (_DWORD)v44,
          (unsigned int)EventSrbScsiReadFailure,
          a1,
          v84,
          *(_DWORD *)(v83 + 588),
          v39,
          v41,
          v42,
          v47,
          a3,
          v12,
          v9,
          v43,
          v45,
          v46,
          v79,
          v78,
          a5);
      }
      return;
    }
    if ( v75 == 40 )
    {
      v58 = 0;
      if ( !*v7 )
      {
        v59 = *(_DWORD *)(a4 + 56);
        if ( v59 )
        {
          v60 = 0;
          v61 = 0;
          do
          {
            v44 = (char *)*(unsigned int *)(a4 + 4 * v60 + 120);
            if ( (unsigned int)v44 >= 0x80 )
            {
              v62 = *(unsigned int *)(a4 + 16);
              if ( (unsigned int)v44 < (unsigned int)v62 )
              {
                v63 = (unsigned int)v44;
                v64 = *(_DWORD *)&v44[a4] - 64;
                if ( v64 )
                {
                  LODWORD(v44) = v64 - 1;
                  if ( (_DWORD)v44 )
                  {
                    if ( (_DWORD)v44 == 1 )
                    {
                      LODWORD(v44) = v63 + 40;
                      if ( v63 + 40 <= v62 )
                      {
                        v58 = *(_BYTE **)(v63 + a4 + 24);
                        break;
                      }
                    }
                  }
                  else
                  {
                    LODWORD(v44) = v63 + 56;
                    if ( v63 + 56 <= v62 )
                    {
                      v58 = *(_BYTE **)(v63 + a4 + 16);
                      v61 = 1;
                    }
                  }
                }
                else
                {
                  LODWORD(v44) = v63 + 40;
                  if ( v63 + 40 <= v62 )
                  {
                    v58 = *(_BYTE **)(v63 + a4 + 16);
                    break;
                  }
                }
                if ( v61 )
                  break;
              }
            }
            v60 = (unsigned int)(v60 + 1);
          }
          while ( (unsigned int)v60 < v59 );
        }
      }
      v65 = 0;
      if ( !*v7 )
      {
        v66 = *(_DWORD *)(a4 + 56);
        if ( v66 )
        {
          v67 = 0;
          v68 = 0;
          while ( 1 )
          {
            v44 = (char *)*(unsigned int *)(a4 + 4 * v67 + 120);
            if ( (unsigned int)v44 >= 0x80 )
            {
              v69 = *(unsigned int *)(a4 + 16);
              if ( (unsigned int)v44 < (unsigned int)v69 )
                break;
            }
LABEL_150:
            v67 = (unsigned int)(v67 + 1);
            if ( (unsigned int)v67 >= v66 )
              goto LABEL_126;
          }
          v70 = (unsigned int)v44;
          v71 = *(_DWORD *)&v44[a4] - 64;
          if ( !v71 )
            goto LABEL_124;
          LODWORD(v44) = v71 - 1;
          if ( (_DWORD)v44 )
          {
            if ( (_DWORD)v44 == 1 )
            {
LABEL_124:
              LODWORD(v44) = v70 + 40;
              if ( v70 + 40 <= v69 )
              {
                v65 = *(_BYTE *)(a4 + v70 + 9);
                goto LABEL_126;
              }
            }
          }
          else
          {
            LODWORD(v44) = v70 + 56;
            if ( v70 + 56 <= v69 )
            {
              v65 = *(_BYTE *)(a4 + v70 + 9);
              v68 = 1;
            }
          }
          if ( v68 )
            goto LABEL_126;
          goto LABEL_150;
        }
      }
    }
    else
    {
      v65 = *(_BYTE *)(a4 + 11);
      v58 = *(_BYTE **)(a4 + 32);
    }
LABEL_126:
    if ( v58 && v65 )
    {
      v44 = &v58[v65];
      v72 = v58 + 8;
      if ( (unsigned __int8)((*v58 & 0x7F) - 114) <= 1u )
      {
        if ( v72 <= v44 )
        {
          v45 = v58[2];
          v43 = v58[1] & 0xF;
          v46 = v58[3];
        }
      }
      else if ( v72 <= v44 )
      {
        v73 = v65;
        v43 = v58[2] & 0xF;
        if ( (unsigned int)(unsigned __int8)v58[7] + 8 <= v65 )
          v73 = (unsigned __int8)v58[7] + 8;
        v44 = v58 + 13;
        v74 = (unsigned __int64)&v58[v73];
        if ( (unsigned __int64)(v58 + 13) <= v74 )
          v45 = v58[12];
        if ( (unsigned __int64)(v58 + 14) <= v74 )
          v46 = *v44;
      }
    }
    v12 = *(_BYTE *)(a4 + 3);
    v42 = v82;
    v41 = v81;
    v39 = v80;
    goto LABEL_105;
  }
}

```

## disassembly

```asm
0x1400066cc  mov     r11, rsp
0x1400066cf  mov     [r11+18h], rbx
0x1400066d3  push    rbp
0x1400066d4  push    rsi
0x1400066d5  push    rdi
0x1400066d6  push    r12
0x1400066d8  push    r13
0x1400066da  push    r14
0x1400066dc  push    r15
0x1400066de  sub     rsp, 0F0h
0x1400066e5  mov     rax, cs:__security_cookie
0x1400066ec  xor     rax, rsp
0x1400066ef  mov     [rsp+128h+var_40], rax
0x1400066f7  mov     r13, [rdx+40h]
0x1400066fb  xorps   xmm0, xmm0
0x1400066fe  mov     [rsp+128h+var_94], r8d
0x140006706  mov     edi, r8d
0x140006709  mov     [rsp+128h+var_58], rcx
0x140006711  mov     [rsp+128h+var_68], r13
0x140006719  movups  xmmword ptr [r11-50h], xmm0
0x14000671e  test    r13, r13
0x140006721  jz      loc_1400067ED
0x140006727  mov     al, [r9+3]
0x14000672b  lea     rsi, [r9+14h]
0x14000672f  xor     cl, cl
0x140006731  mov     [rsp+128h+var_98], al
0x140006738  mov     al, [r9+2]
0x14000673c  mov     ebp, 80h
0x140006741  mov     [rsp+128h+var_88], 0
0x14000674c  mov     [rsp+128h+var_96], cl
0x140006753  mov     [rsp+128h+var_97], al
0x14000675a  cmp     al, 28h ; '('
0x14000675c  jz      loc_140006819
0x140006762  mov     r14b, [r9+4]
0x140006766  lea     rcx, [r9+48h]
0x14000676a  mov     [rsp+128h+var_90], rcx
0x140006772  test    rcx, rcx
0x140006775  jnz     loc_1400068F8
0x14000677b  cmp     edi, 0C0000206h
0x140006781  jz      loc_1400068CC
0x140006787  cmp     edi, 80000005h
0x14000678d  jz      loc_1400068CC
0x140006793  cmp     edi, 0C0000002h
0x140006799  jz      loc_1400068CC
0x14000679f  cmp     edi, 0C0000004h
0x1400067a5  jz      loc_1400068CC
0x1400067ab  cmp     edi, 0C0000010h
0x1400067b1  jz      loc_1400068CC
0x1400067b7  cmp     edi, 0C0000023h
0x1400067bd  jz      loc_1400068CC
0x1400067c3  cmp     edi, 0C00000BBh
0x1400067c9  jz      loc_1400068CC
0x1400067cf  xor     al, al
0x1400067d1  cmp     edi, 0C0000463h
0x1400067d7  jz      loc_1400068CC
0x1400067dd  mov     dl, [rsp+128h+var_98]
0x1400067e4  cmp     dl, 12h
0x1400067e7  jnz     loc_140006A52
0x1400067ed  mov     rcx, [rsp+128h+var_40]
0x1400067f5  xor     rcx, rsp; StackCookie
0x1400067f8  call    __security_check_cookie
0x1400067fd  mov     rbx, [rsp+128h+arg_10]
0x140006805  add     rsp, 0F0h
0x14000680c  pop     r15
0x14000680e  pop     r14
0x140006810  pop     r13
0x140006812  pop     r12
0x140006814  pop     rdi
0x140006815  pop     rsi
0x140006816  pop     rbp
0x140006817  retn
0x140006819  xor     r14b, r14b
0x14000681c  cmp     dword ptr [rsi], 0
0x14000681f  jnz     short loc_14000686D
0x140006821  mov     r11d, [r9+38h]
0x140006825  test    r11d, r11d
0x140006828  jz      short loc_14000686D
0x14000682a  xor     r10d, r10d
0x14000682d  xor     bl, bl
0x14000682f  mov     ecx, [r9+r10*4+78h]
0x140006834  cmp     ecx, ebp
0x140006836  jb      loc_140006962
0x14000683c  mov     r8d, [r9+10h]
0x140006840  cmp     ecx, r8d
0x140006843  jnb     loc_140006962
0x140006849  mov     edx, ecx
0x14000684b  mov     ecx, [rcx+r9]
0x14000684f  sub     ecx, 40h ; '@'
0x140006852  jnz     loc_140006919
0x140006858  lea     rcx, [rdx+28h]
0x14000685c  cmp     rcx, r8
0x14000685f  jbe     loc_1400069C0
0x140006865  test    bl, bl
0x140006867  jz      loc_140006962
0x14000686d  xor     ecx, ecx
0x14000686f  mov     [rsp+128h+var_90], rcx
0x140006877  cmp     [rsi], ecx
0x140006879  jnz     short loc_1400068C7
0x14000687b  mov     r11d, [r9+38h]
0x14000687f  test    r11d, r11d
0x140006882  jz      short loc_1400068C7
0x140006884  xor     r10d, r10d
0x140006887  xor     bl, bl
0x140006889  mov     ecx, [r9+r10*4+78h]
0x14000688e  cmp     ecx, ebp
0x140006890  jb      loc_140006930
0x140006896  mov     r8d, [r9+10h]
0x14000689a  cmp     ecx, r8d
0x14000689d  jnb     loc_140006930
0x1400068a3  mov     edx, ecx
0x1400068a5  mov     ecx, [rcx+r9]
0x1400068a9  sub     ecx, 40h ; '@'
0x1400068ac  jnz     short loc_1400068D3
0x1400068ae  lea     rcx, [rdx+28h]
0x1400068b2  cmp     rcx, r8
0x1400068b5  jbe     loc_140006946
0x1400068bb  mov     rcx, [rsp+128h+var_90]
0x1400068c3  test    bl, bl
0x1400068c5  jz      short loc_140006930
0x1400068c7  jmp     loc_140006772
0x1400068cc  mov     al, 1
0x1400068ce  jmp     loc_1400067DD
0x1400068d3  sub     ecx, 1
0x1400068d6  jz      loc_1400069F0
0x1400068dc  cmp     ecx, 1
0x1400068df  jnz     short loc_1400068BB
0x1400068e1  lea     rcx, [rdx+28h]
0x1400068e5  cmp     rcx, r8
0x1400068e8  ja      short loc_1400068BB
0x1400068ea  cmp     dword ptr [rdx+r9+0Ch], 0
0x1400068f0  jbe     short loc_14000693C
0x1400068f2  lea     rcx, [r9+20h]
0x1400068f6  jmp     short loc_140006952
0x1400068f8  mov     cl, [rcx]
0x1400068fa  mov     [rsp+128h+var_96], cl
0x140006901  cmp     al, 28h ; '('
0x140006903  jz      short loc_140006973
0x140006905  mov     r8b, [r9+0Ah]
0x140006909  movzx   eax, r8b
0x14000690d  mov     [rsp+128h+var_88], eax
0x140006914  jmp     loc_14000677B
0x140006919  sub     ecx, 1
0x14000691c  jz      loc_140006A1F
0x140006922  cmp     ecx, 1
0x140006925  jnz     loc_140006865
0x14000692b  jmp     loc_140006858
0x140006930  inc     r10d
0x140006933  cmp     r10d, r11d
0x140006936  jb      loc_140006889
0x14000693c  mov     rcx, [rsp+128h+var_90]
0x140006944  jmp     short loc_1400068C7
0x140006946  cmp     byte ptr [rdx+r9+0Ah], 0
0x14000694c  jbe     short loc_14000693C
0x14000694e  lea     rcx, [r9+18h]
0x140006952  add     rcx, rdx
0x140006955  mov     [rsp+128h+var_90], rcx
0x14000695d  jmp     loc_1400068C7
0x140006962  inc     r10d
0x140006965  cmp     r10d, r11d
0x140006968  jnb     loc_14000686D
0x14000696e  jmp     loc_14000682F
0x140006973  xor     r8b, r8b
0x140006976  cmp     dword ptr [rsi], 0
0x140006979  jnz     short loc_140006909
0x14000697b  mov     ebx, [r9+38h]
0x14000697f  test    ebx, ebx
0x140006981  jz      short loc_140006909
0x140006983  xor     r11d, r11d
0x140006986  xor     dil, dil
0x140006989  mov     ecx, [r9+r11*4+78h]
0x14000698e  cmp     ecx, ebp
0x140006990  jb      short loc_1400069DF
0x140006992  mov     r10d, [r9+10h]
0x140006996  cmp     ecx, r10d
0x140006999  jnb     short loc_1400069DF
0x14000699b  mov     edx, ecx
0x14000699d  mov     ecx, [rcx+r9]
0x1400069a1  sub     ecx, 40h ; '@'
0x1400069a4  jnz     short loc_1400069CA
0x1400069a6  lea     rcx, [rdx+28h]
0x1400069aa  cmp     rcx, r10
0x1400069ad  jbe     short loc_1400069E9
0x1400069af  test    dil, dil
0x1400069b2  jz      short loc_1400069DF
0x1400069b4  mov     edi, [rsp+128h+var_94]
0x1400069bb  jmp     loc_140006909
0x1400069c0  mov     r14b, [rdx+r9+8]
0x1400069c5  jmp     loc_14000686D
0x1400069ca  sub     ecx, 1
0x1400069cd  jz      short loc_140006A38
0x1400069cf  cmp     ecx, 1
0x1400069d2  jnz     short loc_1400069AF
0x1400069d4  lea     rcx, [rdx+28h]
0x1400069d8  cmp     rcx, r10
0x1400069db  jbe     short loc_1400069B4
0x1400069dd  jmp     short loc_1400069AF
0x1400069df  inc     r11d
0x1400069e2  cmp     r11d, ebx
0x1400069e5  jnb     short loc_1400069B4
0x1400069e7  jmp     short loc_140006989
0x1400069e9  mov     r8b, [rdx+r9+0Ah]
0x1400069ee  jmp     short loc_1400069B4
0x1400069f0  lea     rcx, [rdx+38h]
0x1400069f4  cmp     rcx, r8
0x1400069f7  ja      loc_1400068BB
0x1400069fd  cmp     byte ptr [rdx+r9+0Ah], 0
0x140006a03  jbe     loc_14000693C
0x140006a09  lea     rcx, [r9+18h]
0x140006a0d  mov     bl, 1
0x140006a0f  add     rcx, rdx
0x140006a12  mov     [rsp+128h+var_90], rcx
0x140006a1a  jmp     loc_1400068C3
0x140006a1f  lea     rcx, [rdx+38h]
0x140006a23  cmp     rcx, r8
0x140006a26  ja      loc_140006865
0x140006a2c  mov     r14b, [rdx+r9+8]
0x140006a31  mov     bl, 1
0x140006a33  jmp     loc_140006865
0x140006a38  lea     rcx, [rdx+38h]
0x140006a3c  cmp     rcx, r10
0x140006a3f  ja      loc_1400069AF
0x140006a45  mov     r8b, [rdx+r9+0Ah]
0x140006a4a  mov     dil, 1
0x140006a4d  jmp     loc_1400069AF
0x140006a52  test    al, al
0x140006a54  jnz     loc_1400067ED
0x140006a5a  mov     rcx, [rsp+128h+var_68]
0x140006a62  xor     r11d, r11d
0x140006a65  mov     rax, [r13+208h]
0x140006a6c  xor     ebx, ebx
0x140006a6e  xor     edi, edi
0x140006a70  mov     [rsp+128h+var_80], r11
0x140006a78  xor     bpl, bpl
0x140006a7b  mov     [rsp+128h+var_78], rbx
0x140006a83  mov     rcx, [rcx+490h]
0x140006a8a  xor     r12b, r12b
0x140006a8d  xor     r15b, r15b
0x140006a90  mov     [rsp+128h+var_70], rdi
0x140006a98  xor     r13d, r13d
0x140006a9b  test    rcx, rcx
0x140006a9e  jz      loc_140006E97
0x140006aa4  add     rcx, 4
0x140006aa8  mov     [rsp+128h+var_60], rcx
0x140006ab0  test    rax, rax
0x140006ab3  jz      loc_140006B73
0x140006ab9  mov     r8d, [rax+0Ch]
0x140006abd  mov     ecx, [rax+4]
0x140006ac0  lea     r10, [r8+rax]
0x140006ac4  cmp     r10, rax
0x140006ac7  jb      loc_140006ED7
0x140006acd  cmp     r8d, ecx
0x140006ad0  ja      loc_140006ED7
0x140006ad6  mov     edx, ecx
0x140006ad8  sub     edx, r8d
0x140006adb  test    r8d, r8d
0x140006ade  jnz     loc_140006D7A
0x140006ae4  mov     r8d, [rax+10h]
0x140006ae8  lea     r10, [r8+rax]
0x140006aec  cmp     r10, rax
0x140006aef  jb      loc_140006EDE
0x140006af5  cmp     r8d, ecx
0x140006af8  ja      loc_140006EDE
0x140006afe  mov     edx, ecx
0x140006b00  sub     edx, r8d
0x140006b03  test    r8d, r8d
0x140006b06  jz      short loc_140006B16
0x140006b08  test    edx, edx
0x140006b0a  cmovnz  rbx, r10
0x140006b0e  mov     [rsp+128h+var_78], rbx
0x140006b16  mov     r8d, [rax+14h]
0x140006b1a  lea     r10, [r8+rax]
0x140006b1e  cmp     r10, rax
0x140006b21  jb      loc_140006EE5
0x140006b27  cmp     r8d, ecx
0x140006b2a  ja      loc_140006EE5
0x140006b30  mov     edx, ecx
0x140006b32  sub     edx, r8d
0x140006b35  test    r8d, r8d
0x140006b38  jz      short loc_140006B48
0x140006b3a  test    edx, edx
0x140006b3c  cmovnz  rdi, r10
0x140006b40  mov     [rsp+128h+var_70], rdi
0x140006b48  mov     edx, [rax+18h]
0x140006b4b  lea     r8, [rdx+rax]
0x140006b4f  cmp     r8, rax
0x140006b52  jb      loc_140006EEC
0x140006b58  cmp     edx, ecx
0x140006b5a  ja      loc_140006EEC
0x140006b60  sub     ecx, edx
0x140006b62  test    edx, edx
0x140006b64  mov     dl, [rsp+128h+var_98]
0x140006b6b  jz      short loc_140006B73
0x140006b6d  test    ecx, ecx
0x140006b6f  cmovnz  r13, r8
0x140006b73  test    dl, dl
0x140006b75  js      loc_140006C39
0x140006b7b  mov     cl, [rsp+128h+var_96]
0x140006b82  lea     eax, [rcx-8]
0x140006b85  test    al, 5Fh
0x140006b87  jz      loc_140006DDA
  ... truncated ...
```
