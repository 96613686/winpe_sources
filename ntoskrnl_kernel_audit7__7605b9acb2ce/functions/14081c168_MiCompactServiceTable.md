# MiCompactServiceTable

- ea: `0x14081c168`
- end: `0x14081c728`
- name: `MiCompactServiceTable`
- size: `1472`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x14081c730`
- `0x1408bc714`

## callees

- `0x140346450`
- `0x140346480`
- `0x14041fe50`
- `0x1405eddb8`
- `0x1406f7740`
- `0x14081c168`
- `0x140a6ba88`

## string_xrefs

- `0x14081c439`: `W32pServiceTableFilter`
- `0x14081c501`: `W32pServiceLimitFilter`
- `0x14081c2a9`: `W32pServiceLimit`
- `0x14081c1e1`: `W32pServiceTable`

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
  unsigned int v73; // edi
  __int64 v74; // r14
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
0x14081c168  push    rbp
0x14081c16a  push    rbx
0x14081c16b  push    rsi
0x14081c16c  push    rdi
0x14081c16d  push    r12
0x14081c16f  push    r13
0x14081c171  push    r14
0x14081c173  push    r15
0x14081c175  mov     rbp, rsp
0x14081c178  sub     rsp, 68h
0x14081c17c  mov     rsi, [rcx+30h]
0x14081c180  lea     r9, [rbp+arg_0]
0x14081c184  xor     r14d, r14d
0x14081c187  mov     r13, rcx
0x14081c18a  xor     r8d, r8d
0x14081c18d  mov     [rbp+arg_10], r14
0x14081c191  mov     rcx, rsi
0x14081c194  mov     [rbp+arg_18], r14
0x14081c198  mov     [rbp+arg_0], r14d
0x14081c19c  lea     ebx, [r14+1]
0x14081c1a0  mov     dl, bl
0x14081c1a2  call    RtlImageDirectoryEntryToData
0x14081c1a7  mov     rdi, rax
0x14081c1aa  test    rax, rax
0x14081c1ad  jz      loc_14081C711
0x14081c1b3  mov     eax, [rax+20h]
0x14081c1b6  mov     r12d, r14d
0x14081c1b9  mov     r15d, [rdi+18h]
0x14081c1bd  add     rax, rsi
0x14081c1c0  mov     [rbp+arg_8], rax
0x14081c1c4  sub     r15d, ebx
0x14081c1c7  cmp     r15d, r12d
0x14081c1ca  jl      loc_14081C711
0x14081c1d0  lea     r14d, [r12+r15]
0x14081c1d4  sar     r14d, 1
0x14081c1d7  movsxd  rcx, r14d
0x14081c1da  mov     [rbp+var_38], rcx
0x14081c1de  mov     edx, [rax+rcx*4]
0x14081c1e1  lea     rcx, aW32pservicetab; "W32pServiceTable"
0x14081c1e8  add     rdx, rsi; Str2
0x14081c1eb  call    strcmp
0x14081c1f0  test    eax, eax
0x14081c1f2  jns     short loc_14081C203
0x14081c1f4  test    r14d, r14d
0x14081c1f7  jz      loc_14081C711
0x14081c1fd  lea     r15d, [r14-1]
0x14081c201  jmp     short loc_14081C209
0x14081c203  jle     short loc_14081C20F
0x14081c205  lea     r12d, [r14+1]
0x14081c209  mov     rax, [rbp+arg_8]
0x14081c20d  jmp     short loc_14081C1C7
0x14081c20f  mov     ecx, [rdi+24h]
0x14081c212  mov     rax, [rbp+var_38]
0x14081c216  add     rcx, rsi
0x14081c219  movzx   eax, word ptr [rcx+rax*2]
0x14081c21d  cmp     eax, [rdi+14h]
0x14081c220  jnb     loc_14081C711
0x14081c226  mov     ecx, [rdi+1Ch]
0x14081c229  add     rcx, rsi
0x14081c22c  mov     ecx, [rcx+rax*4]
0x14081c22f  add     rcx, rsi
0x14081c232  mov     [rbp+var_30], rcx
0x14081c236  cmp     rcx, rdi
0x14081c239  jbe     short loc_14081C24A
0x14081c23b  mov     eax, [rbp+arg_0]
0x14081c23e  add     rax, rdi
0x14081c241  cmp     rcx, rax
0x14081c244  jb      loc_14081C711
0x14081c24a  test    rcx, rcx
0x14081c24d  jz      loc_14081C711
0x14081c253  mov     rsi, [r13+30h]
0x14081c257  lea     r9, [rbp+arg_0]
0x14081c25b  mov     rcx, rsi
0x14081c25e  mov     [rbp+arg_0], 0
0x14081c265  xor     r8d, r8d
0x14081c268  mov     dl, bl
0x14081c26a  call    RtlImageDirectoryEntryToData
0x14081c26f  mov     rdi, rax
0x14081c272  test    rax, rax
0x14081c275  jz      loc_14081C711
0x14081c27b  mov     eax, [rax+20h]
0x14081c27e  xor     r12d, r12d
0x14081c281  mov     r15d, [rdi+18h]
0x14081c285  add     rax, rsi
0x14081c288  mov     [rbp+arg_8], rax
0x14081c28c  sub     r15d, ebx
0x14081c28f  cmp     r15d, r12d
0x14081c292  jl      loc_14081C711
0x14081c298  lea     r14d, [r12+r15]
0x14081c29c  sar     r14d, 1
0x14081c29f  movsxd  rcx, r14d
0x14081c2a2  mov     [rbp+var_38], rcx
0x14081c2a6  mov     edx, [rax+rcx*4]
0x14081c2a9  lea     rcx, aW32pservicelim; "W32pServiceLimit"
0x14081c2b0  add     rdx, rsi; Str2
0x14081c2b3  call    strcmp
0x14081c2b8  test    eax, eax
0x14081c2ba  jns     short loc_14081C2CB
0x14081c2bc  test    r14d, r14d
0x14081c2bf  jz      loc_14081C711
0x14081c2c5  lea     r15d, [r14-1]
0x14081c2c9  jmp     short loc_14081C2D1
0x14081c2cb  jle     short loc_14081C2D7
0x14081c2cd  lea     r12d, [r14+1]
0x14081c2d1  mov     rax, [rbp+arg_8]
0x14081c2d5  jmp     short loc_14081C28F
0x14081c2d7  mov     ecx, [rdi+24h]
0x14081c2da  mov     rax, [rbp+var_38]
0x14081c2de  add     rcx, rsi
0x14081c2e1  movzx   eax, word ptr [rcx+rax*2]
0x14081c2e5  cmp     eax, [rdi+14h]
0x14081c2e8  jnb     loc_14081C711
0x14081c2ee  mov     ecx, [rdi+1Ch]
0x14081c2f1  add     rcx, rsi
0x14081c2f4  mov     ecx, [rcx+rax*4]
0x14081c2f7  add     rcx, rsi
0x14081c2fa  mov     [rbp+var_18], rcx
0x14081c2fe  cmp     rcx, rdi
0x14081c301  jbe     short loc_14081C312
0x14081c303  mov     eax, [rbp+arg_0]
0x14081c306  add     rax, rdi
0x14081c309  cmp     rcx, rax
0x14081c30c  jb      loc_14081C711
0x14081c312  test    rcx, rcx
0x14081c315  jz      loc_14081C711
0x14081c31b  mov     rsi, [r13+30h]
0x14081c31f  lea     r9, [rbp+arg_0]
0x14081c323  mov     rcx, rsi
0x14081c326  mov     [rbp+arg_0], 0
0x14081c32d  xor     r8d, r8d
0x14081c330  mov     dl, bl
0x14081c332  call    RtlImageDirectoryEntryToData
0x14081c337  mov     rdi, rax
0x14081c33a  test    rax, rax
0x14081c33d  jz      loc_14081C711
0x14081c343  mov     eax, [rax+20h]
0x14081c346  xor     r12d, r12d
0x14081c349  mov     r15d, [rdi+18h]
0x14081c34d  add     rax, rsi
0x14081c350  mov     [rbp+arg_8], rax
0x14081c354  sub     r15d, ebx
0x14081c357  cmp     r15d, r12d
0x14081c35a  jl      loc_14081C711
0x14081c360  lea     r14d, [r12+r15]
0x14081c364  sar     r14d, 1
0x14081c367  movsxd  rcx, r14d
0x14081c36a  mov     [rbp+var_38], rcx
0x14081c36e  mov     edx, [rax+rcx*4]
0x14081c371  lea     rcx, aW32pargumentta; "W32pArgumentTable"
0x14081c378  add     rdx, rsi; Str2
0x14081c37b  call    strcmp
0x14081c380  test    eax, eax
0x14081c382  jns     short loc_14081C393
0x14081c384  test    r14d, r14d
0x14081c387  jz      loc_14081C711
0x14081c38d  lea     r15d, [r14-1]
0x14081c391  jmp     short loc_14081C399
0x14081c393  jle     short loc_14081C39F
0x14081c395  lea     r12d, [r14+1]
0x14081c399  mov     rax, [rbp+arg_8]
0x14081c39d  jmp     short loc_14081C357
0x14081c39f  mov     ecx, [rdi+24h]
0x14081c3a2  mov     rax, [rbp+var_38]
0x14081c3a6  add     rcx, rsi
0x14081c3a9  movzx   eax, word ptr [rcx+rax*2]
0x14081c3ad  cmp     eax, [rdi+14h]
0x14081c3b0  jnb     loc_14081C711
0x14081c3b6  mov     ecx, [rdi+1Ch]
0x14081c3b9  add     rcx, rsi
0x14081c3bc  mov     ecx, [rcx+rax*4]
0x14081c3bf  add     rcx, rsi
0x14081c3c2  mov     qword ptr [rbp+var_10], rcx
0x14081c3c6  cmp     rcx, rdi
0x14081c3c9  jbe     short loc_14081C3DA
0x14081c3cb  mov     eax, [rbp+arg_0]
0x14081c3ce  add     rax, rdi
0x14081c3d1  cmp     rcx, rax
0x14081c3d4  jb      loc_14081C711
0x14081c3da  test    rcx, rcx
0x14081c3dd  jz      loc_14081C711
0x14081c3e3  mov     rsi, [r13+30h]
0x14081c3e7  lea     r9, [rbp+arg_0]
0x14081c3eb  mov     rcx, rsi
0x14081c3ee  mov     [rbp+arg_0], 0
0x14081c3f5  xor     r8d, r8d
0x14081c3f8  mov     dl, bl
0x14081c3fa  call    RtlImageDirectoryEntryToData
0x14081c3ff  mov     rdi, rax
0x14081c402  test    rax, rax
0x14081c405  jz      loc_14081C711
0x14081c40b  mov     eax, [rax+20h]
0x14081c40e  xor     r12d, r12d
0x14081c411  mov     r15d, [rdi+18h]
0x14081c415  add     rax, rsi
0x14081c418  mov     [rbp+arg_8], rax
0x14081c41c  sub     r15d, ebx
0x14081c41f  cmp     r15d, r12d
0x14081c422  jl      loc_14081C711
0x14081c428  lea     r14d, [r12+r15]
0x14081c42c  sar     r14d, 1
0x14081c42f  movsxd  rcx, r14d
0x14081c432  mov     [rbp+var_38], rcx
0x14081c436  mov     edx, [rax+rcx*4]
0x14081c439  lea     rcx, aW32pservicetab_0; "W32pServiceTableFilter"
0x14081c440  add     rdx, rsi; Str2
0x14081c443  call    strcmp
0x14081c448  test    eax, eax
0x14081c44a  jns     short loc_14081C45B
0x14081c44c  test    r14d, r14d
0x14081c44f  jz      loc_14081C711
0x14081c455  lea     r15d, [r14-1]
0x14081c459  jmp     short loc_14081C461
0x14081c45b  jle     short loc_14081C467
0x14081c45d  lea     r12d, [r14+1]
0x14081c461  mov     rax, [rbp+arg_8]
0x14081c465  jmp     short loc_14081C41F
0x14081c467  mov     ecx, [rdi+24h]
0x14081c46a  mov     rax, [rbp+var_38]
0x14081c46e  add     rcx, rsi
0x14081c471  movzx   edx, word ptr [rcx+rax*2]
0x14081c475  cmp     edx, [rdi+14h]
0x14081c478  jnb     loc_14081C711
0x14081c47e  mov     eax, [rdi+1Ch]
0x14081c481  add     rax, rsi
0x14081c484  mov     ecx, [rax+rdx*4]
0x14081c487  add     rcx, rsi
0x14081c48a  mov     [rbp+var_20], rcx
0x14081c48e  cmp     rcx, rdi
0x14081c491  jbe     short loc_14081C4A2
0x14081c493  mov     eax, [rbp+arg_0]
0x14081c496  add     rax, rdi
0x14081c499  cmp     rcx, rax
0x14081c49c  jb      loc_14081C711
0x14081c4a2  test    rcx, rcx
0x14081c4a5  jz      loc_14081C711
0x14081c4ab  mov     rsi, [r13+30h]
0x14081c4af  lea     r9, [rbp+arg_0]
0x14081c4b3  mov     rcx, rsi
0x14081c4b6  mov     [rbp+arg_0], 0
0x14081c4bd  xor     r8d, r8d
0x14081c4c0  mov     dl, bl
0x14081c4c2  call    RtlImageDirectoryEntryToData
0x14081c4c7  mov     rdi, rax
0x14081c4ca  test    rax, rax
0x14081c4cd  jz      loc_14081C711
0x14081c4d3  mov     eax, [rax+20h]
0x14081c4d6  xor     r12d, r12d
0x14081c4d9  mov     r15d, [rdi+18h]
0x14081c4dd  add     rax, rsi
0x14081c4e0  mov     [rbp+arg_8], rax
0x14081c4e4  sub     r15d, ebx
0x14081c4e7  cmp     r15d, r12d
0x14081c4ea  jl      loc_14081C711
0x14081c4f0  lea     r14d, [r12+r15]
0x14081c4f4  sar     r14d, 1
0x14081c4f7  movsxd  rcx, r14d
0x14081c4fa  mov     [rbp+var_38], rcx
0x14081c4fe  mov     edx, [rax+rcx*4]
0x14081c501  lea     rcx, aW32pservicelim_0; "W32pServiceLimitFilter"
0x14081c508  add     rdx, rsi; Str2
0x14081c50b  call    strcmp
0x14081c510  test    eax, eax
0x14081c512  jns     short loc_14081C523
0x14081c514  test    r14d, r14d
0x14081c517  jz      loc_14081C711
0x14081c51d  lea     r15d, [r14-1]
0x14081c521  jmp     short loc_14081C529
0x14081c523  jle     short loc_14081C52F
0x14081c525  lea     r12d, [r14+1]
0x14081c529  mov     rax, [rbp+arg_8]
0x14081c52d  jmp     short loc_14081C4E7
0x14081c52f  mov     ecx, [rdi+24h]
0x14081c532  mov     rax, [rbp+var_38]
0x14081c536  add     rcx, rsi
0x14081c539  movzx   edx, word ptr [rcx+rax*2]
0x14081c53d  cmp     edx, [rdi+14h]
0x14081c540  jnb     loc_14081C711
0x14081c546  mov     eax, [rdi+1Ch]
0x14081c549  add     rax, rsi
0x14081c54c  mov     ecx, [rax+rdx*4]
0x14081c54f  add     rcx, rsi
0x14081c552  mov     [rbp+var_28], rcx
0x14081c556  cmp     rcx, rdi
0x14081c559  jbe     short loc_14081C56A
0x14081c55b  mov     eax, [rbp+arg_0]
0x14081c55e  add     rax, rdi
0x14081c561  cmp     rcx, rax
0x14081c564  jb      loc_14081C711
0x14081c56a  test    rcx, rcx
0x14081c56d  jz      loc_14081C711
0x14081c573  mov     rsi, [r13+30h]
0x14081c577  lea     r9, [rbp+arg_0]
0x14081c57b  mov     rcx, rsi
0x14081c57e  mov     [rbp+arg_0], 0
0x14081c585  xor     r8d, r8d
0x14081c588  mov     dl, bl
0x14081c58a  call    RtlImageDirectoryEntryToData
0x14081c58f  mov     rdi, rax
0x14081c592  test    rax, rax
0x14081c595  jz      loc_14081C711
  ... truncated ...
```
