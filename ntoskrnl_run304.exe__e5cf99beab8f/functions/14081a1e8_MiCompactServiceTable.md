# MiCompactServiceTable

- ea: `0x14081a1e8`
- end: `0x14081a7aa`
- name: `MiCompactServiceTable`
- size: `1474`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x14081a7b0`
- `0x1409772b4`

## callees

- `0x14027c240`
- `0x14027d17c`
- `0x140408610`
- `0x1405e71d8`
- `0x1406f4c40`
- `0x14081a1e8`
- `0x140a63578`

## string_xrefs

- `0x14081a581`: `W32pServiceLimitFilter`
- `0x14081a4b9`: `W32pServiceTableFilter`
- `0x14081a329`: `W32pServiceLimit`
- `0x14081a261`: `W32pServiceTable`

## pseudocode

```c
__int64 __fastcall MiCompactServiceTable(__int64 a1, __int64 a2)
{
  __int64 v2; // rsi
  unsigned int v4; // ebx
  __int64 v5; // rax
  _DWORD *v6; // rdi
  int v7; // r12d
  int v8; // r15d
  __int64 v9; // rax
  int v10; // r15d
  int v11; // r14d
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rax
  unsigned __int64 v15; // rcx
  __int64 v16; // rsi
  __int64 v17; // rax
  _DWORD *v18; // rdi
  int v19; // r12d
  int v20; // r15d
  __int64 v21; // rax
  int v22; // r15d
  int v23; // r14d
  int v24; // eax
  __int64 v25; // rdx
  __int64 v26; // rax
  _DWORD *v27; // rcx
  __int64 v28; // rsi
  __int64 v29; // rax
  _DWORD *v30; // rdi
  int v31; // r12d
  int v32; // r15d
  __int64 v33; // rax
  int v34; // r15d
  int v35; // r14d
  int v36; // eax
  __int64 v37; // rdx
  __int64 v38; // rax
  unsigned __int64 v39; // rcx
  __int64 v40; // rsi
  __int64 v41; // rax
  _DWORD *v42; // rdi
  int v43; // r12d
  int v44; // r15d
  __int64 v45; // rax
  int v46; // r15d
  int v47; // r14d
  int v48; // eax
  __int64 v49; // rdx
  unsigned __int64 v50; // rcx
  __int64 v51; // rsi
  __int64 v52; // rax
  _DWORD *v53; // rdi
  int v54; // r12d
  int v55; // r15d
  __int64 v56; // rax
  int v57; // r15d
  int v58; // r14d
  int v59; // eax
  __int64 v60; // rdx
  _DWORD *v61; // rcx
  __int64 v62; // rsi
  __int64 v63; // rax
  _DWORD *v64; // rdi
  int v65; // r12d
  int v66; // r15d
  __int64 v67; // rax
  int v68; // r15d
  int v69; // r14d
  int v70; // eax
  __int64 v71; // rdx
  unsigned __int64 v72; // rsi
  __int64 v73; // r15
  __int64 v74; // rdi
  int v76; // [rsp+38h] [rbp-30h]
  _DWORD *v77; // [rsp+40h] [rbp-28h]
  int v78; // [rsp+48h] [rbp-20h]
  _DWORD *v79; // [rsp+50h] [rbp-18h]
  int v80; // [rsp+58h] [rbp-10h]
  unsigned int v81; // [rsp+B0h] [rbp+48h] BYREF
  __int64 v82; // [rsp+B8h] [rbp+50h]
  __int64 v83; // [rsp+C0h] [rbp+58h] BYREF
  __int64 v84; // [rsp+C8h] [rbp+60h] BYREF

  v2 = *(_QWORD *)(a1 + 48);
  v83 = 0;
  v84 = 0;
  v81 = 0;
  v4 = 1;
  LOBYTE(a2) = 1;
  v5 = RtlImageDirectoryEntryToData(v2, a2, 0, &v81);
  v6 = (_DWORD *)v5;
  if ( v5 )
  {
    v7 = 0;
    v8 = *(_DWORD *)(v5 + 24);
    v9 = v2 + *(unsigned int *)(v5 + 32);
    v82 = v9;
    v10 = v8 - 1;
    while ( v10 >= v7 )
    {
      v11 = (v7 + v10) >> 1;
      v12 = strcmp("W32pServiceTable", (const char *)(v2 + *(unsigned int *)(v9 + 4LL * v11)));
      if ( v12 >= 0 )
      {
        if ( v12 <= 0 )
        {
          v14 = *(unsigned __int16 *)(v2 + (unsigned int)v6[9] + 2LL * v11);
          if ( (unsigned int)v14 < v6[5] )
          {
            v15 = v2 + *(unsigned int *)(v2 + (unsigned int)v6[7] + 4 * v14);
            v76 = v2 + *(_DWORD *)(v2 + (unsigned int)v6[7] + 4 * v14);
            if ( v15 <= (unsigned __int64)v6 || v15 >= (unsigned __int64)v6 + v81 )
            {
              if ( v15 )
              {
                v16 = *(_QWORD *)(a1 + 48);
                v81 = 0;
                LOBYTE(v13) = 1;
                v17 = RtlImageDirectoryEntryToData(v16, v13, 0, &v81);
                v18 = (_DWORD *)v17;
                if ( v17 )
                {
                  v19 = 0;
                  v20 = *(_DWORD *)(v17 + 24);
                  v21 = v16 + *(unsigned int *)(v17 + 32);
                  v82 = v21;
                  v22 = v20 - 1;
                  while ( v22 >= v19 )
                  {
                    v23 = (v19 + v22) >> 1;
                    v24 = strcmp("W32pServiceLimit", (const char *)(v16 + *(unsigned int *)(v21 + 4LL * v23)));
                    if ( v24 >= 0 )
                    {
                      if ( v24 <= 0 )
                      {
                        v26 = *(unsigned __int16 *)(v16 + (unsigned int)v18[9] + 2LL * v23);
                        if ( (unsigned int)v26 < v18[5] )
                        {
                          v27 = (_DWORD *)(v16 + *(unsigned int *)(v16 + (unsigned int)v18[7] + 4 * v26));
                          v79 = v27;
                          if ( v27 <= v18 || v27 >= (_DWORD *)((char *)v18 + v81) )
                          {
                            if ( v27 )
                            {
                              v28 = *(_QWORD *)(a1 + 48);
                              v81 = 0;
                              LOBYTE(v25) = 1;
                              v29 = RtlImageDirectoryEntryToData(v28, v25, 0, &v81);
                              v30 = (_DWORD *)v29;
                              if ( v29 )
                              {
                                v31 = 0;
                                v32 = *(_DWORD *)(v29 + 24);
                                v33 = v28 + *(unsigned int *)(v29 + 32);
                                v82 = v33;
                                v34 = v32 - 1;
                                while ( v34 >= v31 )
                                {
                                  v35 = (v31 + v34) >> 1;
                                  v36 = strcmp(
                                          "W32pArgumentTable",
                                          (const char *)(v28 + *(unsigned int *)(v33 + 4LL * v35)));
                                  if ( v36 >= 0 )
                                  {
                                    if ( v36 <= 0 )
                                    {
                                      v38 = *(unsigned __int16 *)(v28 + (unsigned int)v30[9] + 2LL * v35);
                                      if ( (unsigned int)v38 < v30[5] )
                                      {
                                        v39 = v28 + *(unsigned int *)(v28 + (unsigned int)v30[7] + 4 * v38);
                                        v80 = v28 + *(_DWORD *)(v28 + (unsigned int)v30[7] + 4 * v38);
                                        if ( v39 <= (unsigned __int64)v30 || v39 >= (unsigned __int64)v30 + v81 )
                                        {
                                          if ( v39 )
                                          {
                                            v40 = *(_QWORD *)(a1 + 48);
                                            v81 = 0;
                                            LOBYTE(v37) = 1;
                                            v41 = RtlImageDirectoryEntryToData(v40, v37, 0, &v81);
                                            v42 = (_DWORD *)v41;
                                            if ( v41 )
                                            {
                                              v43 = 0;
                                              v44 = *(_DWORD *)(v41 + 24);
                                              v45 = v40 + *(unsigned int *)(v41 + 32);
                                              v82 = v45;
                                              v46 = v44 - 1;
                                              while ( v46 >= v43 )
                                              {
                                                v47 = (v43 + v46) >> 1;
                                                v48 = strcmp(
                                                        "W32pServiceTableFilter",
                                                        (const char *)(v40 + *(unsigned int *)(v45 + 4LL * v47)));
                                                if ( v48 >= 0 )
                                                {
                                                  if ( v48 <= 0 )
                                                  {
                                                    v49 = *(unsigned __int16 *)(v40 + (unsigned int)v42[9] + 2LL * v47);
                                                    if ( (unsigned int)v49 < v42[5] )
                                                    {
                                                      v50 = v40
                                                          + *(unsigned int *)(v40 + (unsigned int)v42[7] + 4 * v49);
                                                      v78 = v40 + *(_DWORD *)(v40 + (unsigned int)v42[7] + 4 * v49);
                                                      if ( v50 <= (unsigned __int64)v42
                                                        || v50 >= (unsigned __int64)v42 + v81 )
                                                      {
                                                        if ( v50 )
                                                        {
                                                          v51 = *(_QWORD *)(a1 + 48);
                                                          v81 = 0;
                                                          LOBYTE(v49) = 1;
                                                          v52 = RtlImageDirectoryEntryToData(v51, v49, 0, &v81);
                                                          v53 = (_DWORD *)v52;
                                                          if ( v52 )
                                                          {
                                                            v54 = 0;
                                                            v55 = *(_DWORD *)(v52 + 24);
                                                            v56 = v51 + *(unsigned int *)(v52 + 32);
                                                            v82 = v56;
                                                            v57 = v55 - 1;
                                                            while ( v57 >= v54 )
                                                            {
                                                              v58 = (v54 + v57) >> 1;
                                                              v59 = strcmp(
                                                                      "W32pServiceLimitFilter",
                                                                      (const char *)(v51
                                                                                   + *(unsigned int *)(v56 + 4LL * v58)));
                                                              if ( v59 >= 0 )
                                                              {
                                                                if ( v59 <= 0 )
                                                                {
                                                                  v60 = *(unsigned __int16 *)(v51
                                                                                            + (unsigned int)v53[9]
                                                                                            + 2LL * v58);
                                                                  if ( (unsigned int)v60 < v53[5] )
                                                                  {
                                                                    v61 = (_DWORD *)(v51
                                                                                   + *(unsigned int *)(v51 + (unsigned int)v53[7] + 4 * v60));
                                                                    v77 = v61;
                                                                    if ( v61 <= v53
                                                                      || v61 >= (_DWORD *)((char *)v53 + v81) )
                                                                    {
                                                                      if ( v61 )
                                                                      {
                                                                        v62 = *(_QWORD *)(a1 + 48);
                                                                        v81 = 0;
                                                                        LOBYTE(v60) = 1;
                                                                        v63 = RtlImageDirectoryEntryToData(
                                                                                v62,
                                                                                v60,
                                                                                0,
                                                                                &v81);
                                                                        v64 = (_DWORD *)v63;
                                                                        if ( v63 )
                                                                        {
                                                                          v65 = 0;
                                                                          v66 = *(_DWORD *)(v63 + 24);
                                                                          v67 = v62 + *(unsigned int *)(v63 + 32);
                                                                          v82 = v67;
                                                                          v68 = v66 - 1;
                                                                          while ( v68 >= v65 )
                                                                          {
                                                                            v69 = (v65 + v68) >> 1;
                                                                            v70 = strcmp(
                                                                                    "W32pArgumentTableFilter",
                                                                                    (const char *)(v62
                                                                                                 + *(unsigned int *)(v67 + 4LL * v69)));
                                                                            if ( v70 >= 0 )
                                                                            {
                                                                              if ( v70 <= 0 )
                                                                              {
                                                                                v71 = *(unsigned __int16 *)(v62 + (unsigned int)v64[9] + 2LL * v69);
                                                                                if ( (unsigned int)v71 >= v64[5] )
                                                                                  return 3221225594LL;
                                                                                v72 = *(unsigned int *)(v62 + (unsigned int)v64[7] + 4 * v71)
                                                                                    + v62;
                                                                                if ( v72 > (unsigned __int64)v64
                                                                                  && v72 < (unsigned __int64)v64 + v81 )
                                                                                {
                                                                                  return 3221225594LL;
                                                                                }
                                                                                if ( !v72 )
                                                                                  return 3221225594LL;
                                                                                MiSnapDriverRange(
                                                                                  a1,
                                                                                  0,
                                                                                  64,
                                                                                  v76,
                                                                                  (__int64)&v84,
                                                                                  (__int64)&v83);
                                                                                v73 = ((unsigned int)((v83 - v84) >> 3)
                                                                                     + 1) << 12;
                                                                                v74 = v84 << 25 >> 16;
                                                                                MiSetImageProtection(a1, v74, v73, 4);
                                                                                KeCompactServiceTable(
                                                                                  v78,
                                                                                  v72,
                                                                                  *v77,
                                                                                  3,
                                                                                  *(_QWORD *)(a1 + 48));
                                                                                KeCompactServiceTable(
                                                                                  v76,
                                                                                  v80,
                                                                                  *v79,
                                                                                  1,
                                                                                  *(_QWORD *)(a1 + 48));
                                                                                if ( *(_QWORD *)(a1 + 112) )
                                                                                {
                                                                                  if ( *(_QWORD *)(MiSectionControlArea()
                                                                                                 + 144) )
                                                                                    v4 = 256;
                                                                                }
                                                                                MiSetImageProtection(a1, v74, v73, v4);
                                                                                return 0;
                                                                              }
                                                                              v65 = v69 + 1;
                                                                            }
                                                                            else
                                                                            {
                                                                              if ( !v69 )
                                                                                return 3221225594LL;
                                                                              v68 = v69 - 1;
                                                                            }
                                                                            v67 = v82;
                                                                          }
                                                                        }
                                                                      }
                                                                    }
                                                                  }
                                                                  return 3221225594LL;
                                                                }
                                                                v54 = v58 + 1;
                                                              }
                                                              else
                                                              {
                                                                if ( !v58 )
                                                                  return 3221225594LL;
                                                                v57 = v58 - 1;
                                                              }
                                                              v56 = v82;
                                                            }
                                                          }
                                                        }
                                                      }
                                                    }
                                                    return 3221225594LL;
                                                  }
                                                  v43 = v47 + 1;
                                                }
                                                else
                                                {
                                                  if ( !v47 )
                                                    return 3221225594LL;
                                                  v46 = v47 - 1;
                                                }
                                                v45 = v82;
                                              }
                                            }
                                          }
                                        }
                                      }
                                      return 3221225594LL;
                                    }
                                    v31 = v35 + 1;
                                  }
                                  else
                                  {
                                    if ( !v35 )
                                      return 3221225594LL;
                                    v34 = v35 - 1;
                                  }
                                  v33 = v82;
                                }
                              }
                            }
                          }
                        }
                        return 3221225594LL;
                      }
                      v19 = v23 + 1;
                    }
                    else
                    {
                      if ( !v23 )
                        return 3221225594LL;
                      v22 = v23 - 1;
                    }
                    v21 = v82;
                  }
                }
              }
            }
          }
          return 3221225594LL;
        }
        v7 = v11 + 1;
      }
      else
      {
        if ( !v11 )
          return 3221225594LL;
        v10 = v11 - 1;
      }
      v9 = v82;
    }
  }
  return 3221225594LL;
}

```

## disassembly

```asm
0x14081a1e8  push    rbp
0x14081a1ea  push    rbx
0x14081a1eb  push    rsi
0x14081a1ec  push    rdi
0x14081a1ed  push    r12
0x14081a1ef  push    r13
0x14081a1f1  push    r14
0x14081a1f3  push    r15
0x14081a1f5  mov     rbp, rsp
0x14081a1f8  sub     rsp, 68h
0x14081a1fc  mov     rsi, [rcx+30h]
0x14081a200  lea     r9, [rbp+arg_0]
0x14081a204  xor     r14d, r14d
0x14081a207  mov     r13, rcx
0x14081a20a  xor     r8d, r8d
0x14081a20d  mov     [rbp+arg_10], r14
0x14081a211  mov     rcx, rsi
0x14081a214  mov     [rbp+arg_18], r14
0x14081a218  mov     [rbp+arg_0], r14d
0x14081a21c  lea     ebx, [r14+1]
0x14081a220  mov     dl, bl
0x14081a222  call    RtlImageDirectoryEntryToData
0x14081a227  mov     rdi, rax
0x14081a22a  test    rax, rax
0x14081a22d  jz      loc_14081A793
0x14081a233  mov     eax, [rax+20h]
0x14081a236  mov     r12d, r14d
0x14081a239  mov     r15d, [rdi+18h]
0x14081a23d  add     rax, rsi
0x14081a240  mov     [rbp+arg_8], rax
0x14081a244  sub     r15d, ebx
0x14081a247  cmp     r15d, r12d
0x14081a24a  jl      loc_14081A793
0x14081a250  lea     r14d, [r12+r15]
0x14081a254  sar     r14d, 1
0x14081a257  movsxd  rcx, r14d
0x14081a25a  mov     [rbp+var_38], rcx
0x14081a25e  mov     edx, [rax+rcx*4]
0x14081a261  lea     rcx, aW32pservicetab; "W32pServiceTable"
0x14081a268  add     rdx, rsi; Str2
0x14081a26b  call    strcmp
0x14081a270  test    eax, eax
0x14081a272  jns     short loc_14081A283
0x14081a274  test    r14d, r14d
0x14081a277  jz      loc_14081A793
0x14081a27d  lea     r15d, [r14-1]
0x14081a281  jmp     short loc_14081A289
0x14081a283  jle     short loc_14081A28F
0x14081a285  lea     r12d, [r14+1]
0x14081a289  mov     rax, [rbp+arg_8]
0x14081a28d  jmp     short loc_14081A247
0x14081a28f  mov     ecx, [rdi+24h]
0x14081a292  mov     rax, [rbp+var_38]
0x14081a296  add     rcx, rsi
0x14081a299  movzx   eax, word ptr [rcx+rax*2]
0x14081a29d  cmp     eax, [rdi+14h]
0x14081a2a0  jnb     loc_14081A793
0x14081a2a6  mov     ecx, [rdi+1Ch]
0x14081a2a9  add     rcx, rsi
0x14081a2ac  mov     ecx, [rcx+rax*4]
0x14081a2af  add     rcx, rsi
0x14081a2b2  mov     [rbp+var_30], rcx
0x14081a2b6  cmp     rcx, rdi
0x14081a2b9  jbe     short loc_14081A2CA
0x14081a2bb  mov     eax, [rbp+arg_0]
0x14081a2be  add     rax, rdi
0x14081a2c1  cmp     rcx, rax
0x14081a2c4  jb      loc_14081A793
0x14081a2ca  test    rcx, rcx
0x14081a2cd  jz      loc_14081A793
0x14081a2d3  mov     rsi, [r13+30h]
0x14081a2d7  lea     r9, [rbp+arg_0]
0x14081a2db  mov     rcx, rsi
0x14081a2de  mov     [rbp+arg_0], 0
0x14081a2e5  xor     r8d, r8d
0x14081a2e8  mov     dl, bl
0x14081a2ea  call    RtlImageDirectoryEntryToData
0x14081a2ef  mov     rdi, rax
0x14081a2f2  test    rax, rax
0x14081a2f5  jz      loc_14081A793
0x14081a2fb  mov     eax, [rax+20h]
0x14081a2fe  xor     r12d, r12d
0x14081a301  mov     r15d, [rdi+18h]
0x14081a305  add     rax, rsi
0x14081a308  mov     [rbp+arg_8], rax
0x14081a30c  sub     r15d, ebx
0x14081a30f  cmp     r15d, r12d
0x14081a312  jl      loc_14081A793
0x14081a318  lea     r14d, [r12+r15]
0x14081a31c  sar     r14d, 1
0x14081a31f  movsxd  rcx, r14d
0x14081a322  mov     [rbp+var_38], rcx
0x14081a326  mov     edx, [rax+rcx*4]
0x14081a329  lea     rcx, aW32pservicelim; "W32pServiceLimit"
0x14081a330  add     rdx, rsi; Str2
0x14081a333  call    strcmp
0x14081a338  test    eax, eax
0x14081a33a  jns     short loc_14081A34B
0x14081a33c  test    r14d, r14d
0x14081a33f  jz      loc_14081A793
0x14081a345  lea     r15d, [r14-1]
0x14081a349  jmp     short loc_14081A351
0x14081a34b  jle     short loc_14081A357
0x14081a34d  lea     r12d, [r14+1]
0x14081a351  mov     rax, [rbp+arg_8]
0x14081a355  jmp     short loc_14081A30F
0x14081a357  mov     ecx, [rdi+24h]
0x14081a35a  mov     rax, [rbp+var_38]
0x14081a35e  add     rcx, rsi
0x14081a361  movzx   eax, word ptr [rcx+rax*2]
0x14081a365  cmp     eax, [rdi+14h]
0x14081a368  jnb     loc_14081A793
0x14081a36e  mov     ecx, [rdi+1Ch]
0x14081a371  add     rcx, rsi
0x14081a374  mov     ecx, [rcx+rax*4]
0x14081a377  add     rcx, rsi
0x14081a37a  mov     [rbp+var_18], rcx
0x14081a37e  cmp     rcx, rdi
0x14081a381  jbe     short loc_14081A392
0x14081a383  mov     eax, [rbp+arg_0]
0x14081a386  add     rax, rdi
0x14081a389  cmp     rcx, rax
0x14081a38c  jb      loc_14081A793
0x14081a392  test    rcx, rcx
0x14081a395  jz      loc_14081A793
0x14081a39b  mov     rsi, [r13+30h]
0x14081a39f  lea     r9, [rbp+arg_0]
0x14081a3a3  mov     rcx, rsi
0x14081a3a6  mov     [rbp+arg_0], 0
0x14081a3ad  xor     r8d, r8d
0x14081a3b0  mov     dl, bl
0x14081a3b2  call    RtlImageDirectoryEntryToData
0x14081a3b7  mov     rdi, rax
0x14081a3ba  test    rax, rax
0x14081a3bd  jz      loc_14081A793
0x14081a3c3  mov     eax, [rax+20h]
0x14081a3c6  xor     r12d, r12d
0x14081a3c9  mov     r15d, [rdi+18h]
0x14081a3cd  add     rax, rsi
0x14081a3d0  mov     [rbp+arg_8], rax
0x14081a3d4  sub     r15d, ebx
0x14081a3d7  cmp     r15d, r12d
0x14081a3da  jl      loc_14081A793
0x14081a3e0  lea     r14d, [r12+r15]
0x14081a3e4  sar     r14d, 1
0x14081a3e7  movsxd  rcx, r14d
0x14081a3ea  mov     [rbp+var_38], rcx
0x14081a3ee  mov     edx, [rax+rcx*4]
0x14081a3f1  lea     rcx, aW32pargumentta; "W32pArgumentTable"
0x14081a3f8  add     rdx, rsi; Str2
0x14081a3fb  call    strcmp
0x14081a400  test    eax, eax
0x14081a402  jns     short loc_14081A413
0x14081a404  test    r14d, r14d
0x14081a407  jz      loc_14081A793
0x14081a40d  lea     r15d, [r14-1]
0x14081a411  jmp     short loc_14081A419
0x14081a413  jle     short loc_14081A41F
0x14081a415  lea     r12d, [r14+1]
0x14081a419  mov     rax, [rbp+arg_8]
0x14081a41d  jmp     short loc_14081A3D7
0x14081a41f  mov     ecx, [rdi+24h]
0x14081a422  mov     rax, [rbp+var_38]
0x14081a426  add     rcx, rsi
0x14081a429  movzx   eax, word ptr [rcx+rax*2]
0x14081a42d  cmp     eax, [rdi+14h]
0x14081a430  jnb     loc_14081A793
0x14081a436  mov     ecx, [rdi+1Ch]
0x14081a439  add     rcx, rsi
0x14081a43c  mov     ecx, [rcx+rax*4]
0x14081a43f  add     rcx, rsi
0x14081a442  mov     qword ptr [rbp+var_10], rcx
0x14081a446  cmp     rcx, rdi
0x14081a449  jbe     short loc_14081A45A
0x14081a44b  mov     eax, [rbp+arg_0]
0x14081a44e  add     rax, rdi
0x14081a451  cmp     rcx, rax
0x14081a454  jb      loc_14081A793
0x14081a45a  test    rcx, rcx
0x14081a45d  jz      loc_14081A793
0x14081a463  mov     rsi, [r13+30h]
0x14081a467  lea     r9, [rbp+arg_0]
0x14081a46b  mov     rcx, rsi
0x14081a46e  mov     [rbp+arg_0], 0
0x14081a475  xor     r8d, r8d
0x14081a478  mov     dl, bl
0x14081a47a  call    RtlImageDirectoryEntryToData
0x14081a47f  mov     rdi, rax
0x14081a482  test    rax, rax
0x14081a485  jz      loc_14081A793
0x14081a48b  mov     eax, [rax+20h]
0x14081a48e  xor     r12d, r12d
0x14081a491  mov     r15d, [rdi+18h]
0x14081a495  add     rax, rsi
0x14081a498  mov     [rbp+arg_8], rax
0x14081a49c  sub     r15d, ebx
0x14081a49f  cmp     r15d, r12d
0x14081a4a2  jl      loc_14081A793
0x14081a4a8  lea     r14d, [r12+r15]
0x14081a4ac  sar     r14d, 1
0x14081a4af  movsxd  rcx, r14d
0x14081a4b2  mov     [rbp+var_38], rcx
0x14081a4b6  mov     edx, [rax+rcx*4]
0x14081a4b9  lea     rcx, aW32pservicetab_0; "W32pServiceTableFilter"
0x14081a4c0  add     rdx, rsi; Str2
0x14081a4c3  call    strcmp
0x14081a4c8  test    eax, eax
0x14081a4ca  jns     short loc_14081A4DB
0x14081a4cc  test    r14d, r14d
0x14081a4cf  jz      loc_14081A793
0x14081a4d5  lea     r15d, [r14-1]
0x14081a4d9  jmp     short loc_14081A4E1
0x14081a4db  jle     short loc_14081A4E7
0x14081a4dd  lea     r12d, [r14+1]
0x14081a4e1  mov     rax, [rbp+arg_8]
0x14081a4e5  jmp     short loc_14081A49F
0x14081a4e7  mov     ecx, [rdi+24h]
0x14081a4ea  mov     rax, [rbp+var_38]
0x14081a4ee  add     rcx, rsi
0x14081a4f1  movzx   edx, word ptr [rcx+rax*2]
0x14081a4f5  cmp     edx, [rdi+14h]
0x14081a4f8  jnb     loc_14081A793
0x14081a4fe  mov     eax, [rdi+1Ch]
0x14081a501  add     rax, rsi
0x14081a504  mov     ecx, [rax+rdx*4]
0x14081a507  add     rcx, rsi
0x14081a50a  mov     [rbp+var_20], rcx
0x14081a50e  cmp     rcx, rdi
0x14081a511  jbe     short loc_14081A522
0x14081a513  mov     eax, [rbp+arg_0]
0x14081a516  add     rax, rdi
0x14081a519  cmp     rcx, rax
0x14081a51c  jb      loc_14081A793
0x14081a522  test    rcx, rcx
0x14081a525  jz      loc_14081A793
0x14081a52b  mov     rsi, [r13+30h]
0x14081a52f  lea     r9, [rbp+arg_0]
0x14081a533  mov     rcx, rsi
0x14081a536  mov     [rbp+arg_0], 0
0x14081a53d  xor     r8d, r8d
0x14081a540  mov     dl, bl
0x14081a542  call    RtlImageDirectoryEntryToData
0x14081a547  mov     rdi, rax
0x14081a54a  test    rax, rax
0x14081a54d  jz      loc_14081A793
0x14081a553  mov     eax, [rax+20h]
0x14081a556  xor     r12d, r12d
0x14081a559  mov     r15d, [rdi+18h]
0x14081a55d  add     rax, rsi
0x14081a560  mov     [rbp+arg_8], rax
0x14081a564  sub     r15d, ebx
0x14081a567  cmp     r15d, r12d
0x14081a56a  jl      loc_14081A793
0x14081a570  lea     r14d, [r12+r15]
0x14081a574  sar     r14d, 1
0x14081a577  movsxd  rcx, r14d
0x14081a57a  mov     [rbp+var_38], rcx
0x14081a57e  mov     edx, [rax+rcx*4]
0x14081a581  lea     rcx, aW32pservicelim_0; "W32pServiceLimitFilter"
0x14081a588  add     rdx, rsi; Str2
0x14081a58b  call    strcmp
0x14081a590  test    eax, eax
0x14081a592  jns     short loc_14081A5A3
0x14081a594  test    r14d, r14d
0x14081a597  jz      loc_14081A793
0x14081a59d  lea     r15d, [r14-1]
0x14081a5a1  jmp     short loc_14081A5A9
0x14081a5a3  jle     short loc_14081A5AF
0x14081a5a5  lea     r12d, [r14+1]
0x14081a5a9  mov     rax, [rbp+arg_8]
0x14081a5ad  jmp     short loc_14081A567
0x14081a5af  mov     ecx, [rdi+24h]
0x14081a5b2  mov     rax, [rbp+var_38]
0x14081a5b6  add     rcx, rsi
0x14081a5b9  movzx   edx, word ptr [rcx+rax*2]
0x14081a5bd  cmp     edx, [rdi+14h]
0x14081a5c0  jnb     loc_14081A793
0x14081a5c6  mov     eax, [rdi+1Ch]
0x14081a5c9  add     rax, rsi
0x14081a5cc  mov     ecx, [rax+rdx*4]
0x14081a5cf  add     rcx, rsi
0x14081a5d2  mov     [rbp+var_28], rcx
0x14081a5d6  cmp     rcx, rdi
0x14081a5d9  jbe     short loc_14081A5EA
0x14081a5db  mov     eax, [rbp+arg_0]
0x14081a5de  add     rax, rdi
0x14081a5e1  cmp     rcx, rax
0x14081a5e4  jb      loc_14081A793
0x14081a5ea  test    rcx, rcx
0x14081a5ed  jz      loc_14081A793
0x14081a5f3  mov     rsi, [r13+30h]
0x14081a5f7  lea     r9, [rbp+arg_0]
0x14081a5fb  mov     rcx, rsi
0x14081a5fe  mov     [rbp+arg_0], 0
0x14081a605  xor     r8d, r8d
0x14081a608  mov     dl, bl
0x14081a60a  call    RtlImageDirectoryEntryToData
0x14081a60f  mov     rdi, rax
0x14081a612  test    rax, rax
0x14081a615  jz      loc_14081A793
  ... truncated ...
```
