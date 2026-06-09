# CILogRead::_DumpRestartPage(char *,ulong,ulong,_RESTARTPAGE *,_DUMP_TYPE,ulong *,ulong)

- ea: `0x180003a5c`
- end: `0x180004283`
- name: `?_DumpRestartPage@CILogRead@@AEAAJPEADKKPEAU_RESTARTPAGE@@W4_DUMP_TYPE@@PEAKK@Z`
- size: `2087`
- prototype: `__int64 __fastcall(__int64, char *, unsigned int, int, int *, int, _DWORD *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180002900`

## callees

- `0x1800032d8`
- `0x180003358`
- `0x180003a5c`
- `0x1800127f2`
- `0x180012830`

## import_xrefs

- `msvcrt!isprint` at `0x180003c13`
- `msvcrt!isprint` at `0x180003c13`

## pseudocode

```c
__int64 __fastcall CILogRead::_DumpRestartPage(
        __int64 a1,
        char *a2,
        unsigned int a3,
        int a4,
        int *a5,
        int a6,
        _DWORD *a7,
        int a8)
{
  char *v8; // r15
  _DWORD *v9; // r13
  unsigned int v11; // ebx
  char *v12; // r14
  char *v13; // rsi
  unsigned int v14; // ebx
  char *v15; // r14
  char *v16; // r14
  unsigned int v17; // esi
  unsigned int v18; // esi
  char *v19; // rbx
  int *v20; // r13
  int v21; // r12d
  unsigned int v22; // r14d
  unsigned int v23; // esi
  char *v24; // rbx
  int v25; // edi
  int v26; // ecx
  char v27; // al
  unsigned int v28; // ecx
  unsigned int v29; // esi
  char *v30; // r14
  unsigned int v31; // ebx
  char *v32; // rsi
  unsigned int v33; // ebx
  char *v34; // rsi
  unsigned int v35; // ebx
  char *v36; // rsi
  unsigned int v37; // ebx
  char *v38; // rsi
  unsigned int v39; // ebx
  char *v40; // rsi
  unsigned int v41; // ebx
  char *v42; // rsi
  unsigned int v43; // ebx
  char *v44; // rsi
  unsigned int v45; // ebx
  char *v46; // rsi
  unsigned int v47; // ebx
  char *v48; // rsi
  unsigned int v49; // ebx
  char *v50; // rsi
  unsigned int v51; // ebx
  char *v52; // rsi
  unsigned int v53; // ebx
  char *v54; // rsi
  unsigned int v55; // ebx
  char *v56; // rsi
  unsigned int v57; // ebx
  char *v58; // rsi
  unsigned int v59; // ebx
  char *v60; // rsi
  unsigned int v61; // ebx
  char *v62; // rsi
  unsigned int v63; // ebx
  char *v64; // rsi
  unsigned int v65; // ebx
  char *v66; // rsi
  unsigned int v67; // ebx
  char *v68; // rsi
  unsigned int v69; // ebx
  char *v70; // rsi
  unsigned int v71; // ebx
  char *v72; // r14
  char *v73; // r14
  unsigned int v74; // esi
  unsigned int v75; // esi
  unsigned int v76; // r14d
  int *v77; // r12
  unsigned int v78; // esi
  char *v79; // r15
  char *v80; // r15
  unsigned int v81; // ebx
  char *v82; // r15
  unsigned int v83; // esi
  unsigned int v84; // r15d
  __int64 v85; // rcx
  int v87; // [rsp+28h] [rbp-58h]
  int v88; // [rsp+30h] [rbp-50h]
  unsigned int v89; // [rsp+40h] [rbp-40h] BYREF
  char *v90; // [rsp+48h] [rbp-38h]
  char *v91; // [rsp+50h] [rbp-30h]
  _DWORD *v92; // [rsp+58h] [rbp-28h]
  char v93[24]; // [rsp+60h] [rbp-20h] BYREF

  v8 = a2;
  v9 = a7;
  v91 = a2;
  v88 = a5[1];
  v87 = *a5;
  v92 = a7;
  v89 = 0;
  TracedSafeStrPrintfA(a2, a3, &v89, "Restart Page %d \n\tSignature  :  %.8X \tChecksum   :  %.8X\n", a4, v87, v88);
  if ( a3 < v89 )
    return 2147942934LL;
  v11 = a3 - v89;
  v12 = &v8[v89];
  if ( a8 == a5[1] )
  {
    v13 = &v8[v89];
  }
  else
  {
    TracedSafeStrPrintfA(v12, v11, &v89, "!!! BAD CHECKSUM !!!\n\tChecksum   :  %.8X\n", a8);
    if ( v11 < v89 )
      return 2147942934LL;
    v13 = &v12[v89];
    v11 -= v89;
  }
  TracedSafeStrPrintfA(v13, v11, &v89, "\tGeneration :  %.8X \tPageOffset :  %.8X\n", a5[2], a5[3]);
  if ( v11 < v89 )
    return 2147942934LL;
  v14 = v11 - v89;
  v15 = &v13[v89];
  TracedSafeStrPrintfA(v15, v14, &v89, "\tVersion    :  %.8X \n", a5[4]);
  if ( v14 < v89 )
    return 2147942934LL;
  v16 = &v15[v89];
  v17 = v14 - v89;
  TracedSafeStrPrintfA(v16, v14 - v89, &v89, "======================================================\n\n");
  if ( v17 < v89 )
    return 2147942934LL;
  v18 = v17 - v89;
  v19 = &v16[v89];
  if ( !a6 )
  {
    v20 = a5 + 8;
    v21 = a5[3] + 32;
    v22 = 2040;
LABEL_11:
    if ( v22 < 4 )
      memcpy_0(&v20[v22], "0000000000000000", 16LL - v22 * 4);
    StringCchPrintfA(v19, v18, "%.6X  ", v21);
    if ( v18 >= 8 )
    {
      v23 = v18 - 8;
      v93[16] = 0;
      v24 = v19 + 8;
      v25 = 0;
      while ( 1 )
      {
        while ( 1 )
        {
          v26 = *((unsigned __int8 *)v20 + v25);
          LODWORD(v90) = v26;
          v27 = isprint(v26) ? *((_BYTE *)v20 + v25) : 46;
          v93[v25] = v27;
          if ( v25 != 7 )
            break;
          TracedSafeStrPrintfA(v24, v23, &v89, "%.2hX  ", (_DWORD)v90);
          if ( v23 < v89 )
            return 2147942934LL;
          v23 -= v89;
          v24 += v89;
          v25 = 8;
        }
        TracedSafeStrPrintfA(v24, v23, &v89, "%.2hX ", (_DWORD)v90);
        if ( v23 < v89 )
          break;
        v24 += v89;
        v23 -= v89;
        ++v25;
        v90 = v24;
        if ( v25 >= 16 )
        {
          TracedSafeStrPrintfA(v24, v23, &v89, " %s\n", v93);
          if ( v23 < v89 )
            return 2147942934LL;
          v28 = v22 * 4;
          v22 -= 4;
          v19 = &v90[v89];
          if ( v28 <= 0x10 )
            v22 = 0;
          if ( (int)v22 > 0 )
          {
            v21 += 16;
            v18 = v23 - v89;
            v20 += 4;
            goto LABEL_11;
          }
          v9 = v92;
          goto LABEL_64;
        }
      }
    }
    return 2147942934LL;
  }
  if ( a6 == 1 )
  {
    TracedSafeStrPrintfA(v19, v18, &v89, "Restart information\n");
    if ( v18 >= v89 )
    {
      v29 = v18 - v89;
      v30 = &v19[v89];
      TracedSafeStrPrintfA(v30, v29, &v89, "\tLeadOffset \t: %.8X\n", a5[6]);
      if ( v29 >= v89 )
      {
        v31 = v29 - v89;
        v32 = &v30[v89];
        TracedSafeStrPrintfA(v32, v31, &v89, "\tLeadGenNum \t: %.8X\n\n", a5[7]);
        if ( v31 >= v89 )
        {
          v33 = v31 - v89;
          v34 = &v32[v89];
          TracedSafeStrPrintfA(v34, v33, &v89, "\tTrailOffset \t: %.8X\n", a5[8]);
          if ( v33 >= v89 )
          {
            v35 = v33 - v89;
            v36 = &v34[v89];
            TracedSafeStrPrintfA(v36, v35, &v89, "\tTrailGenNum \t: %.8X\n\n", a5[9]);
            if ( v35 >= v89 )
            {
              v37 = v35 - v89;
              v38 = &v36[v89];
              TracedSafeStrPrintfA(v38, v37, &v89, "\tRecoveryOffset \t: %.8X\n", a5[10]);
              if ( v37 >= v89 )
              {
                v39 = v37 - v89;
                v40 = &v38[v89];
                TracedSafeStrPrintfA(v40, v39, &v89, "\tRecoveryGenNum \t: %.8X\n\n", a5[11]);
                if ( v39 >= v89 )
                {
                  v41 = v39 - v89;
                  v42 = &v40[v89];
                  TracedSafeStrPrintfA(v42, v41, &v89, "\tDirtyOffset \t: %.8X\n", a5[12]);
                  if ( v41 >= v89 )
                  {
                    v43 = v41 - v89;
                    v44 = &v42[v89];
                    TracedSafeStrPrintfA(v44, v43, &v89, "\tDirtyGenNum \t: %.8X\n\n", a5[13]);
                    if ( v43 >= v89 )
                    {
                      v45 = v43 - v89;
                      v46 = &v44[v89];
                      TracedSafeStrPrintfA(v46, v45, &v89, "\tLogSize \t: %.8X\n", a5[14]);
                      if ( v45 >= v89 )
                      {
                        v47 = v45 - v89;
                        v48 = &v46[v89];
                        TracedSafeStrPrintfA(v48, v47, &v89, "\tBeginChkptOffset: %.8X\n", a5[15]);
                        if ( v47 >= v89 )
                        {
                          v49 = v47 - v89;
                          v50 = &v48[v89];
                          TracedSafeStrPrintfA(v50, v49, &v89, "\tBeginChkptGenNum: %.8X\n\n", a5[16]);
                          if ( v49 >= v89 )
                          {
                            v51 = v49 - v89;
                            v52 = &v50[v89];
                            TracedSafeStrPrintfA(v52, v51, &v89, "\tEndChkptOffset \t: %.8X\n", a5[17]);
                            if ( v51 >= v89 )
                            {
                              v53 = v51 - v89;
                              v54 = &v52[v89];
                              TracedSafeStrPrintfA(v54, v53, &v89, "\tEndChkptGenNum \t: %.8X\n\n", a5[18]);
                              if ( v53 >= v89 )
                              {
                                v55 = v53 - v89;
                                v56 = &v54[v89];
                                TracedSafeStrPrintfA(v56, v55, &v89, "\tTotalSize \t: %.8X\n", a5[19]);
                                if ( v55 >= v89 )
                                {
                                  v57 = v55 - v89;
                                  v58 = &v56[v89];
                                  TracedSafeStrPrintfA(v58, v57, &v89, "\tPageSize \t: %.8X\n\n", a5[20]);
                                  if ( v57 >= v89 )
                                  {
                                    v59 = v57 - v89;
                                    v60 = &v58[v89];
                                    TracedSafeStrPrintfA(
                                      v60,
                                      v59,
                                      &v89,
                                      "\tVersion \t: %.4X %.4X\n",
                                      *((unsigned __int16 *)a5 + 42),
                                      *((unsigned __int16 *)a5 + 43));
                                    if ( v59 >= v89 )
                                    {
                                      v61 = v59 - v89;
                                      v62 = &v60[v89];
                                      TracedSafeStrPrintfA(
                                        v62,
                                        v61,
                                        &v89,
                                        "\tStrmTblEntries \t: %.4X\n",
                                        *((unsigned __int16 *)a5 + 44));
                                      if ( v61 >= v89 )
                                      {
                                        v63 = v61 - v89;
                                        v64 = &v62[v89];
                                        TracedSafeStrPrintfA(
                                          v64,
                                          v63,
                                          &v89,
                                          "\tStrmTblSize \t: %.4X\n\n",
                                          *((unsigned __int16 *)a5 + 45));
                                        if ( v63 >= v89 )
                                        {
                                          v65 = v63 - v89;
                                          v66 = &v64[v89];
                                          TracedSafeStrPrintfA(v66, v65, &v89, "\tTimerInterval \t: %.8X\n", a5[23]);
                                          if ( v65 >= v89 )
                                          {
                                            v67 = v65 - v89;
                                            v68 = &v66[v89];
                                            TracedSafeStrPrintfA(v68, v67, &v89, "\tFlushInterval \t: %.8X\n", a5[24]);
                                            if ( v67 >= v89 )
                                            {
                                              v69 = v67 - v89;
                                              v70 = &v68[v89];
                                              TracedSafeStrPrintfA(
                                                v70,
                                                v69,
                                                &v89,
                                                "\tChkPtInterval \t: %.8X\n\n",
                                                a5[25]);
                                              if ( v69 >= v89 )
                                              {
                                                v71 = v69 - v89;
                                                v72 = &v70[v89];
                                                TracedSafeStrPrintfA(
                                                  v72,
                                                  v71,
                                                  &v89,
                                                  "\tfIsCircular \t: %.8X\n\n",
                                                  a5[26]);
                                                if ( v71 >= v89 )
                                                {
                                                  v73 = &v72[v89];
                                                  v74 = v71 - v89;
                                                  TracedSafeStrPrintfA(v73, v71 - v89, &v89, "\n\tStream Table\n");
                                                  if ( v74 >= v89 )
                                                  {
                                                    v75 = v74 - v89;
                                                    v19 = &v73[v89];
                                                    v76 = 0;
                                                    if ( *((_WORD *)a5 + 44) )
                                                    {
LABEL_54:
                                                      v77 = &a5[11 * v76 + 27];
                                                      TracedSafeStrPrintfA(
                                                        v19,
                                                        v75,
                                                        &v89,
                                                        "\tStream Name: %s\n",
                                                        (const char *)v77);
                                                      if ( v75 >= v89 )
                                                      {
                                                        v78 = v75 - v89;
                                                        v79 = &v19[v89];
                                                        TracedSafeStrPrintfA(
                                                          v79,
                                                          v78,
                                                          &v89,
                                                          "\t\tChkpoints \t:%.4X\n",
                                                          *((unsigned __int16 *)v77 + 8));
                                                        if ( v78 >= v89 )
                                                        {
                                                          v80 = &v79[v89];
                                                          v81 = v78 - v89;
                                                          TracedSafeStrPrintfA(
                                                            v80,
                                                            v78 - v89,
                                                            &v89,
                                                            "\t\tNext Chkpt \t:%.4X\n",
                                                            *((unsigned __int16 *)v77 + 9));
                                                          if ( v81 >= v89 )
                                                          {
                                                            v82 = &v80[v89];
                                                            v83 = v81 - v89;
                                                            TracedSafeStrPrintfA(
                                                              v82,
                                                              v81 - v89,
                                                              &v89,
                                                              "\t\tCheckpoints\n");
                                                            if ( v83 >= v89 )
                                                            {
                                                              v75 = v83 - v89;
                                                              v19 = &v82[v89];
                                                              v84 = 0;
                                                              while ( 1 )
                                                              {
                                                                v85 = v84++;
                                                                TracedSafeStrPrintfA(
                                                                  v19,
                                                                  v75,
                                                                  &v89,
                                                                  "\t\t\tChkpt %d: %.8X %.8X\n",
                                                                  v84,
                                                                  v77[2 * v85 + 8],
                                                                  v77[2 * v85 + 7]);
                                                                if ( v75 < v89 )
                                                                  break;
                                                                v75 -= v89;
                                                                v19 += v89;
                                                                if ( v84 >= 2 )
                                                                {
                                                                  if ( ++v76 < *((unsigned __int16 *)a5 + 44) )
                                                                    goto LABEL_54;
LABEL_64:
                                                                  LODWORD(v8) = (_DWORD)v91;
                                                                  goto LABEL_65;
                                                                }
                                                              }
                                                            }
                                                          }
                                                        }
                                                      }
                                                      return 2147942934LL;
                                                    }
                                                    goto LABEL_65;
                                                  }
                                                }
                                              }
                                            }
                                          }
                                        }
                                      }
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    return 2147942934LL;
  }
LABEL_65:
  if ( v9 )
    *v9 = (_DWORD)v19 - (_DWORD)v8 + 1;
  return 0;
}

```

## disassembly

```asm
0x180003a5c  mov     [rsp-38h+arg_0], rbx
0x180003a61  push    rbp
0x180003a62  push    rsi
0x180003a63  push    rdi
0x180003a64  push    r12
0x180003a66  push    r13
0x180003a68  push    r14
0x180003a6a  push    r15
0x180003a6c  mov     rbp, rsp
0x180003a6f  sub     rsp, 80h
0x180003a76  mov     rax, cs:__security_cookie
0x180003a7d  xor     rax, rsp
0x180003a80  mov     [rbp+var_8], rax
0x180003a84  mov     rdi, [rbp+arg_20]
0x180003a88  mov     r15, rdx
0x180003a8b  mov     r13, [rbp+arg_30]
0x180003a8f  mov     rcx, r15; char *
0x180003a92  mov     [rbp+var_30], rdx
0x180003a96  mov     ebx, r8d
0x180003a99  mov     eax, [rdi+4]
0x180003a9c  mov     [rsp+80h+var_50], eax
0x180003aa0  mov     eax, [rdi]
0x180003aa2  mov     [rsp+80h+var_58], eax
0x180003aa6  mov     dword ptr [rsp+80h+var_60], r9d
0x180003aab  lea     r9, aRestartPageDSi; "Restart Page %d \n\tSignature  :  %.8X "...
0x180003ab2  mov     edx, r8d; unsigned __int64
0x180003ab5  lea     r8, [rbp+var_40]; unsigned int *
0x180003ab9  mov     [rbp+var_28], r13
0x180003abd  mov     [rbp+var_40], 0
0x180003ac4  call    ?TracedSafeStrPrintfA@@YAXPEAD_KPEAKPEBDZZ; TracedSafeStrPrintfA(char *,unsigned __int64,ulong *,char const *,...)
0x180003ac9  mov     eax, [rbp+var_40]
0x180003acc  cmp     ebx, eax
0x180003ace  jb      loc_180004257
0x180003ad4  sub     ebx, eax
0x180003ad6  lea     r14, [r15+rax]
0x180003ada  mov     eax, [rbp+arg_38]
0x180003add  mov     esi, ebx
0x180003adf  cmp     eax, [rdi+4]
0x180003ae2  jz      short loc_180003B10
0x180003ae4  mov     edx, esi; unsigned __int64
0x180003ae6  mov     dword ptr [rsp+80h+var_60], eax
0x180003aea  lea     r9, aBadChecksumChe; "!!! BAD CHECKSUM !!!\n\tChecksum   :  %"...
0x180003af1  mov     rcx, r14; char *
0x180003af4  lea     r8, [rbp+var_40]; unsigned int *
0x180003af8  call    ?TracedSafeStrPrintfA@@YAXPEAD_KPEAKPEBDZZ; TracedSafeStrPrintfA(char *,unsigned __int64,ulong *,char const *,...)
0x180003afd  mov     eax, [rbp+var_40]
0x180003b00  cmp     esi, eax
0x180003b02  jb      loc_180004257
0x180003b08  lea     rsi, [r14+rax]
0x180003b0c  sub     ebx, eax
0x180003b0e  jmp     short loc_180003B13
0x180003b10  mov     rsi, r14
0x180003b13  mov     eax, [rdi+0Ch]
0x180003b16  lea     r9, aGeneration8xPa; "\tGeneration :  %.8X \tPageOffset :  %."...
0x180003b1d  mov     [rsp+80h+var_58], eax
0x180003b21  lea     r8, [rbp+var_40]; unsigned int *
0x180003b25  mov     eax, [rdi+8]
0x180003b28  mov     rcx, rsi; char *
0x180003b2b  mov     edx, ebx; unsigned __int64
0x180003b2d  mov     dword ptr [rsp+80h+var_60], eax
0x180003b31  call    ?TracedSafeStrPrintfA@@YAXPEAD_KPEAKPEBDZZ; TracedSafeStrPrintfA(char *,unsigned __int64,ulong *,char const *,...)
0x180003b36  mov     eax, [rbp+var_40]
0x180003b39  cmp     ebx, eax
0x180003b3b  jb      loc_180004257
0x180003b41  sub     ebx, eax
0x180003b43  lea     r14, [rsi+rax]
0x180003b47  mov     eax, [rdi+10h]
0x180003b4a  lea     r9, aVersion8x; "\tVersion    :  %.8X \n"
0x180003b51  mov     edx, ebx; unsigned __int64
0x180003b53  mov     dword ptr [rsp+80h+var_60], eax
0x180003b57  mov     rcx, r14; char *
0x180003b5a  lea     r8, [rbp+var_40]; unsigned int *
0x180003b5e  call    ?TracedSafeStrPrintfA@@YAXPEAD_KPEAKPEBDZZ; TracedSafeStrPrintfA(char *,unsigned __int64,ulong *,char const *,...)
0x180003b63  mov     eax, [rbp+var_40]
0x180003b66  cmp     ebx, eax
0x180003b68  jb      loc_180004257
0x180003b6e  sub     ebx, eax
0x180003b70  lea     r9, asc_180017348; "======================================="...
0x180003b77  add     r14, rax
0x180003b7a  mov     edx, ebx; unsigned __int64
0x180003b7c  mov     rcx, r14; char *
0x180003b7f  mov     esi, ebx
0x180003b81  lea     r8, [rbp+var_40]; unsigned int *
0x180003b85  call    ?TracedSafeStrPrintfA@@YAXPEAD_KPEAKPEBDZZ; TracedSafeStrPrintfA(char *,unsigned __int64,ulong *,char const *,...)
0x180003b8a  mov     eax, [rbp+var_40]
0x180003b8d  cmp     ebx, eax
0x180003b8f  jb      loc_180004257
0x180003b95  sub     esi, eax
0x180003b97  lea     rbx, [r14+rax]
0x180003b9b  mov     eax, [rbp+arg_28]
0x180003b9e  test    eax, eax
0x180003ba0  jnz     loc_180003CEA
0x180003ba6  mov     r12d, [rdi+0Ch]
0x180003baa  lea     r13, [rdi+20h]
0x180003bae  add     r12d, 20h ; ' '
0x180003bb2  mov     r14d, 1FE0h
0x180003bb8  cmp     r14d, 10h
0x180003bbc  jnb     short loc_180003BDC
0x180003bbe  mov     eax, r14d
0x180003bc1  lea     rdx, a00000000000000; "0000000000000000"
0x180003bc8  mov     r8d, 10h
0x180003bce  mov     ecx, r14d
0x180003bd1  sub     r8, rax; Size
0x180003bd4  add     rcx, r13; void *
0x180003bd7  call    memcpy_0
0x180003bdc  mov     edx, esi; unsigned __int64
0x180003bde  lea     r8, a6x; "%.6X  "
0x180003be5  mov     r9d, r12d
0x180003be8  mov     rcx, rbx; char *
0x180003beb  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180003bf0  cmp     esi, 8
0x180003bf3  jb      loc_180004257
0x180003bf9  add     esi, 0FFFFFFF8h
0x180003bfc  mov     [rbp+var_10], 0
0x180003c00  add     rbx, 8
0x180003c04  xor     edi, edi
0x180003c06  movsxd  r15, edi
0x180003c09  movzx   eax, byte ptr [r15+r13]
0x180003c0e  mov     ecx, eax; C
0x180003c10  mov     dword ptr [rbp+var_38], eax
0x180003c13  call    cs:__imp_isprint
0x180003c19  test    eax, eax
0x180003c1b  jz      short loc_180003C23
0x180003c1d  mov     al, [r15+r13]
0x180003c21  jmp     short loc_180003C25
0x180003c23  mov     al, 2Eh ; '.'
0x180003c25  mov     [rbp+r15+var_20], al
0x180003c2a  lea     r8, [rbp+var_40]; unsigned int *
0x180003c2e  mov     eax, dword ptr [rbp+var_38]
0x180003c31  mov     rcx, rbx; char *
0x180003c34  mov     dword ptr [rsp+80h+var_60], eax
0x180003c38  mov     edx, esi; unsigned __int64
0x180003c3a  cmp     edi, 7
0x180003c3d  jnz     short loc_180003C5F
0x180003c3f  lea     r9, a2hx; "%.2hX  "
0x180003c46  call    ?TracedSafeStrPrintfA@@YAXPEAD_KPEAKPEBDZZ; TracedSafeStrPrintfA(char *,unsigned __int64,ulong *,char const *,...)
0x180003c4b  mov     eax, [rbp+var_40]
0x180003c4e  cmp     esi, eax
0x180003c50  jb      loc_180004257
0x180003c56  sub     esi, eax
0x180003c58  add     rbx, rax
0x180003c5b  inc     edi
0x180003c5d  jmp     short loc_180003C06
0x180003c5f  lea     r9, a2hx_0; "%.2hX "
0x180003c66  call    ?TracedSafeStrPrintfA@@YAXPEAD_KPEAKPEBDZZ; TracedSafeStrPrintfA(char *,unsigned __int64,ulong *,char const *,...)
0x180003c6b  mov     ecx, [rbp+var_40]
0x180003c6e  cmp     esi, ecx
0x180003c70  jb      loc_180004257
0x180003c76  add     rbx, rcx
0x180003c79  sub     esi, ecx
0x180003c7b  inc     edi
0x180003c7d  mov     [rbp+var_38], rbx
0x180003c81  mov     r15d, esi
0x180003c84  cmp     edi, 10h
0x180003c87  jl      loc_180003C06
0x180003c8d  lea     rax, [rbp+var_20]
0x180003c91  mov     edx, r15d; unsigned __int64
0x180003c94  lea     r9, aS; " %s\n"
0x180003c9b  mov     [rsp+80h+var_60], rax
0x180003ca0  lea     r8, [rbp+var_40]; unsigned int *
0x180003ca4  mov     rcx, rbx; char *
0x180003ca7  call    ?TracedSafeStrPrintfA@@YAXPEAD_KPEAKPEBDZZ; TracedSafeStrPrintfA(char *,unsigned __int64,ulong *,char const *,...)
0x180003cac  mov     edx, [rbp+var_40]
0x180003caf  cmp     r15d, edx
0x180003cb2  jb      loc_180004257
0x180003cb8  mov     ecx, r14d
0x180003cbb  xor     eax, eax
0x180003cbd  add     r14d, 0FFFFFFF0h
0x180003cc1  mov     ebx, edx
0x180003cc3  add     rbx, [rbp+var_38]
0x180003cc7  cmp     ecx, 10h
0x180003cca  cmovbe  r14d, eax
0x180003cce  test    r14d, r14d
0x180003cd1  jle     loc_18000423D
0x180003cd7  sub     r15d, edx
0x180003cda  add     r12d, 10h
0x180003cde  mov     esi, r15d
0x180003ce1  add     r13, 10h
0x180003ce5  jmp     loc_180003BB8
0x180003cea  cmp     eax, 1
0x180003ced  jnz     loc_180004245
0x180003cf3  mov     edx, esi; unsigned __int64
0x180003cf5  lea     r9, aRestartInforma; "Restart information\n"
0x180003cfc  lea     r8, [rbp+var_40]; unsigned int *
0x180003d00  mov     rcx, rbx; char *
0x180003d03  call    ?TracedSafeStrPrintfA@@YAXPEAD_KPEAKPEBDZZ; TracedSafeStrPrintfA(char *,unsigned __int64,ulong *,char const *,...)
0x180003d08  mov     eax, [rbp+var_40]
0x180003d0b  cmp     esi, eax
0x180003d0d  jb      loc_180004257
0x180003d13  sub     esi, eax
0x180003d15  lea     r14, [rbx+rax]
0x180003d19  mov     eax, [rdi+18h]
0x180003d1c  lea     r9, aLeadoffset8x; "\tLeadOffset \t: %.8X\n"
0x180003d23  mov     edx, esi; unsigned __int64
0x180003d25  mov     dword ptr [rsp+80h+var_60], eax
0x180003d29  mov     rcx, r14; char *
0x180003d2c  lea     r8, [rbp+var_40]; unsigned int *
0x180003d30  call    ?TracedSafeStrPrintfA@@YAXPEAD_KPEAKPEBDZZ; TracedSafeStrPrintfA(char *,unsigned __int64,ulong *,char const *,...)
0x180003d35  mov     eax, [rbp+var_40]
0x180003d38  cmp     esi, eax
0x180003d3a  jb      loc_180004257
0x180003d40  sub     esi, eax
0x180003d42  lea     r9, aLeadgennum8x; "\tLeadGenNum \t: %.8X\n\n"
0x180003d49  mov     ebx, esi
0x180003d4b  lea     r8, [rbp+var_40]; unsigned int *
0x180003d4f  lea     rsi, [r14+rax]
0x180003d53  mov     edx, ebx; unsigned __int64
0x180003d55  mov     eax, [rdi+1Ch]
0x180003d58  mov     rcx, rsi; char *
0x180003d5b  mov     dword ptr [rsp+80h+var_60], eax
0x180003d5f  call    ?TracedSafeStrPrintfA@@YAXPEAD_KPEAKPEBDZZ; TracedSafeStrPrintfA(char *,unsigned __int64,ulong *,char const *,...)
0x180003d64  mov     eax, [rbp+var_40]
0x180003d67  cmp     ebx, eax
0x180003d69  jb      loc_180004257
0x180003d6f  sub     ebx, eax
0x180003d71  lea     r9, aTrailoffset8x; "\tTrailOffset \t: %.8X\n"
0x180003d78  add     rsi, rax
0x180003d7b  lea     r8, [rbp+var_40]; unsigned int *
0x180003d7f  mov     eax, [rdi+20h]
0x180003d82  mov     edx, ebx; unsigned __int64
0x180003d84  mov     rcx, rsi; char *
0x180003d87  mov     dword ptr [rsp+80h+var_60], eax
0x180003d8b  call    ?TracedSafeStrPrintfA@@YAXPEAD_KPEAKPEBDZZ; TracedSafeStrPrintfA(char *,unsigned __int64,ulong *,char const *,...)
0x180003d90  mov     eax, [rbp+var_40]
0x180003d93  cmp     ebx, eax
0x180003d95  jb      loc_180004257
0x180003d9b  sub     ebx, eax
0x180003d9d  lea     r9, aTrailgennum8x; "\tTrailGenNum \t: %.8X\n\n"
0x180003da4  add     rsi, rax
0x180003da7  lea     r8, [rbp+var_40]; unsigned int *
0x180003dab  mov     eax, [rdi+24h]
0x180003dae  mov     edx, ebx; unsigned __int64
0x180003db0  mov     rcx, rsi; char *
0x180003db3  mov     dword ptr [rsp+80h+var_60], eax
0x180003db7  call    ?TracedSafeStrPrintfA@@YAXPEAD_KPEAKPEBDZZ; TracedSafeStrPrintfA(char *,unsigned __int64,ulong *,char const *,...)
0x180003dbc  mov     eax, [rbp+var_40]
0x180003dbf  cmp     ebx, eax
0x180003dc1  jb      loc_180004257
0x180003dc7  sub     ebx, eax
0x180003dc9  lea     r9, aRecoveryoffset; "\tRecoveryOffset \t: %.8X\n"
0x180003dd0  add     rsi, rax
0x180003dd3  lea     r8, [rbp+var_40]; unsigned int *
0x180003dd7  mov     eax, [rdi+28h]
0x180003dda  mov     edx, ebx; unsigned __int64
0x180003ddc  mov     rcx, rsi; char *
0x180003ddf  mov     dword ptr [rsp+80h+var_60], eax
0x180003de3  call    ?TracedSafeStrPrintfA@@YAXPEAD_KPEAKPEBDZZ; TracedSafeStrPrintfA(char *,unsigned __int64,ulong *,char const *,...)
0x180003de8  mov     eax, [rbp+var_40]
0x180003deb  cmp     ebx, eax
0x180003ded  jb      loc_180004257
0x180003df3  sub     ebx, eax
0x180003df5  lea     r9, aRecoverygennum; "\tRecoveryGenNum \t: %.8X\n\n"
0x180003dfc  add     rsi, rax
0x180003dff  lea     r8, [rbp+var_40]; unsigned int *
0x180003e03  mov     eax, [rdi+2Ch]
0x180003e06  mov     edx, ebx; unsigned __int64
0x180003e08  mov     rcx, rsi; char *
0x180003e0b  mov     dword ptr [rsp+80h+var_60], eax
0x180003e0f  call    ?TracedSafeStrPrintfA@@YAXPEAD_KPEAKPEBDZZ; TracedSafeStrPrintfA(char *,unsigned __int64,ulong *,char const *,...)
0x180003e14  mov     eax, [rbp+var_40]
0x180003e17  cmp     ebx, eax
0x180003e19  jb      loc_180004257
0x180003e1f  sub     ebx, eax
0x180003e21  lea     r9, aDirtyoffset8x; "\tDirtyOffset \t: %.8X\n"
0x180003e28  add     rsi, rax
0x180003e2b  lea     r8, [rbp+var_40]; unsigned int *
0x180003e2f  mov     eax, [rdi+30h]
0x180003e32  mov     edx, ebx; unsigned __int64
0x180003e34  mov     rcx, rsi; char *
0x180003e37  mov     dword ptr [rsp+80h+var_60], eax
0x180003e3b  call    ?TracedSafeStrPrintfA@@YAXPEAD_KPEAKPEBDZZ; TracedSafeStrPrintfA(char *,unsigned __int64,ulong *,char const *,...)
0x180003e40  mov     eax, [rbp+var_40]
0x180003e43  cmp     ebx, eax
0x180003e45  jb      loc_180004257
0x180003e4b  sub     ebx, eax
0x180003e4d  lea     r9, aDirtygennum8x; "\tDirtyGenNum \t: %.8X\n\n"
0x180003e54  add     rsi, rax
0x180003e57  lea     r8, [rbp+var_40]; unsigned int *
0x180003e5b  mov     eax, [rdi+34h]
0x180003e5e  mov     edx, ebx; unsigned __int64
0x180003e60  mov     rcx, rsi; char *
0x180003e63  mov     dword ptr [rsp+80h+var_60], eax
0x180003e67  call    ?TracedSafeStrPrintfA@@YAXPEAD_KPEAKPEBDZZ; TracedSafeStrPrintfA(char *,unsigned __int64,ulong *,char const *,...)
0x180003e6c  mov     eax, [rbp+var_40]
0x180003e6f  cmp     ebx, eax
0x180003e71  jb      loc_180004257
0x180003e77  sub     ebx, eax
0x180003e79  lea     r9, aLogsize8x; "\tLogSize \t: %.8X\n"
0x180003e80  add     rsi, rax
0x180003e83  lea     r8, [rbp+var_40]; unsigned int *
0x180003e87  mov     eax, [rdi+38h]
0x180003e8a  mov     edx, ebx; unsigned __int64
0x180003e8c  mov     rcx, rsi; char *
0x180003e8f  mov     dword ptr [rsp+80h+var_60], eax
0x180003e93  call    ?TracedSafeStrPrintfA@@YAXPEAD_KPEAKPEBDZZ; TracedSafeStrPrintfA(char *,unsigned __int64,ulong *,char const *,...)
0x180003e98  mov     eax, [rbp+var_40]
0x180003e9b  cmp     ebx, eax
0x180003e9d  jb      loc_180004257
0x180003ea3  sub     ebx, eax
0x180003ea5  lea     r9, aBeginchkptoffs; "\tBeginChkptOffset: %.8X\n"
  ... truncated ...
```
