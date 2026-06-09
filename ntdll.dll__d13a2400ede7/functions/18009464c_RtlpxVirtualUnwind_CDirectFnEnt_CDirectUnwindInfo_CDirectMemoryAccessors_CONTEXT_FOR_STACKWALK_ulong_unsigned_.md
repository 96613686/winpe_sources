# RtlpxVirtualUnwind<CDirectFnEnt,CDirectUnwindInfo,CDirectMemoryAccessors,_CONTEXT_FOR_STACKWALK *>(ulong,unsigned __int64,unsigned __int64,CDirectFnEnt,_CONTEXT_FOR_STACKWALK *,uchar *,void * *,unsigned __int64 *,_EXCEPTION_DISPOSITION (**)(_EXCEPTION_RECORD *,void *,_CONTEXT *,void *),_AMD64_UNWIND_PARAMS *,ulong,ulong *)

- ea: `0x18009464c`
- end: `0x180094ef9`
- name: `??$RtlpxVirtualUnwind@VCDirectFnEnt@@VCDirectUnwindInfo@@VCDirectMemoryAccessors@@PEAU_CONTEXT_FOR_STACKWALK@@@@YAJK_K0VCDirectFnEnt@@PEAU_CONTEXT_FOR_STACKWALK@@PEAEPEAPEAXPEA_KPEAP6A?AW4_EXCEPTION_DISPOSITION@@PEAU_EXCEPTION_RECORD@@PEAXPEAU_CONTEXT@@7@ZPEAU_AMD64_UNWIND_PARAMS@@KPEAK@Z`
- size: `2221`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180093684`

## callees

- `0x18009464c`
- `0x1800e25d8`
- `0x1800f8ba4`
- `0x1800fca1c`
- `0x180103e58`
- `0x180117f94`
- `0x18014a15c`
- `0x18014a1d4`
- `0x18014a6ac`
- `0x18014c6b4`

## pseudocode

```c
__int64 __fastcall RtlpxVirtualUnwind<CDirectFnEnt,CDirectUnwindInfo,CDirectMemoryAccessors,_CONTEXT_FOR_STACKWALK *>(
        int a1,
        __int64 a2,
        _BYTE *a3,
        unsigned int *a4,
        _QWORD *a5,
        _BYTE *a6,
        _QWORD *a7,
        __int64 *a8,
        int a9,
        __int64 a10,
        int a11,
        int a12)
{
  unsigned int *v12; // r10
  _BYTE *v13; // rdi
  __int64 v14; // r11
  _QWORD *v15; // r9
  _QWORD *v16; // r8
  _QWORD *v17; // rdx
  __int64 result; // rax
  __int64 v19; // rdx
  __int64 v20; // rbx
  unsigned int v21; // esi
  BOOL v22; // r12d
  unsigned int v23; // r14d
  __int64 v24; // r15
  _QWORD *v25; // r15
  __int64 v26; // rax
  __int64 Context; // rax
  int v28; // r8d
  _BYTE *i; // rcx
  char v30; // dl
  int v31; // r9d
  char v32; // r8
  bool v33; // zf
  BOOL v34; // r12d
  int v35; // eax
  unsigned __int64 v36; // rsi
  unsigned __int64 v37; // rcx
  _QWORD *v38; // rax
  __int64 v39; // rbx
  _QWORD *v40; // rsi
  char v41; // dl
  char v42; // al
  __int64 v43; // rax
  _QWORD **v44; // r9
  _QWORD *v45; // r9
  __int64 v46; // r9
  unsigned int v47; // r10d
  _QWORD *v48; // r11
  __int64 v49; // rcx
  _QWORD *v50; // r10
  __int64 v51; // rax
  __int64 v52; // r10
  __int64 v53; // rcx
  _QWORD *v54; // rcx
  __int16 v55; // cx
  unsigned int v56; // r14d
  int v57; // r8d
  int v58; // edx
  unsigned int v59; // esi
  unsigned int v60; // r9d
  __int16 v61; // r11
  unsigned int v62; // [rsp+70h] [rbp-68h]
  _QWORD *v63; // [rsp+98h] [rbp-40h] BYREF
  unsigned int *v65; // [rsp+F8h] [rbp+20h] BYREF

  v65 = a4;
  v12 = a4;
  v13 = a3;
  v14 = a2;
  if ( a4 )
  {
    v20 = a2 + a4[2];
    v21 = *(_BYTE *)v20 & 7;
    if ( v21 >= 3 )
      return RtlpxVirtualUnwindV3<CDirectFnEnt,CDirectUnwindInfo,CDirectMemoryAccessors,_CONTEXT_FOR_STACKWALK *>(
               a1,
               a2,
               (_DWORD)a3,
               (_DWORD)a4,
               v20,
               (__int64)a5,
               (__int64)a6,
               (__int64)a7,
               (__int64)a8);
    a11 = 0;
    a9 = 0;
    if ( !a6 || *a6 )
    {
      v22 = 0;
      if ( v21 < 2 )
      {
        v22 = RtlpxTrivialFunction<CDirectFnEnt,CDirectUnwindInfo>(a4, a2, v20) != 0;
        v12 = v65;
        v14 = a2;
      }
    }
    else
    {
      v22 = 1;
    }
    a12 = 0;
    if ( (*(_BYTE *)(v20 + 3) & 0xF) != 0 )
    {
      v23 = (_DWORD)v13 - v14 - *v12;
      if ( v23 >= *(unsigned __int8 *)(v20 + 1) || (*(_BYTE *)v20 & 0x20) != 0 )
        goto LABEL_26;
      v24 = 0;
      if ( *(_BYTE *)(v20 + 2) )
      {
        do
        {
          if ( (HIBYTE(*(_WORD *)(v20 + 2 * v24 + 4)) & 0xF) == 3 )
            break;
          v24 = (unsigned int)RtlpUnwindOpSlots() + (unsigned int)v24;
        }
        while ( (unsigned int)v24 < *(unsigned __int8 *)(v20 + 2) );
        v12 = v65;
        v14 = a2;
      }
      if ( v23 >= *(unsigned __int8 *)(v20 + 2 * v24 + 4) )
LABEL_26:
        a12 = 1;
    }
    v25 = a5;
    if ( a12 )
    {
      Context = RtlpAmd64GetContextGp<_CONTEXT_FOR_STACKWALK *>(a5, *(_BYTE *)(v20 + 3) & 0xF);
      v26 = Context - (v28 & 0xFFFFFFF0);
    }
    else
    {
      v26 = a5[1];
    }
    *a8 = v26;
    if ( !v22 )
    {
      if ( v21 < 2 )
      {
        i = v13;
        v30 = *v13;
        v62 = 0;
        if ( *v13 != 72 )
          goto LABEL_41;
        if ( v13[1] == 0x83 && v13[2] == 0xC4 )
        {
LABEL_35:
          for ( i = v13 + 4; ; i += 2 )
          {
LABEL_45:
            while ( 1 )
            {
              v30 = *i;
LABEL_46:
              if ( (v30 & 0xF8) != 0x58 )
                break;
              ++i;
            }
            if ( (v30 & 0xF0) != 0x40 || (i[1] & 0xF8) != 0x58 )
              break;
          }
          if ( v30 == -14 )
            v30 = *++i;
          if ( (unsigned __int8)(v30 + 62) <= 1u || v30 == -13 && i[1] == 0xC3 )
            goto LABEL_64;
          if ( ((v30 + 23) & 0xFD) != 0 )
          {
            if ( v30 == -1 && i[1] == 37 )
            {
              a11 = 1;
              a9 = 1;
              goto LABEL_77;
            }
            if ( (v30 & 0xF8) == 0x48 && i[1] == 0xFF )
            {
              v33 = (i[2] & 0x38) == 32;
              goto LABEL_63;
            }
          }
          else
          {
            if ( v30 == -21 )
              v35 = (char)i[1] + 2;
            else
              v35 = *(_DWORD *)(i + 1) + 5;
            v36 = (unsigned __int64)&i[v35 - v14];
            v37 = *v12;
            if ( v36 < v37 || v36 >= v12[1] )
            {
              v38 = (_QWORD *)RtlpxSameFunction<CDirectFnEnt,CDirectUnwindInfo>(&v63, v12, v14, v36 + v14);
              if ( !*v38 || v36 == *(_DWORD *)*v38 )
              {
                v34 = 1;
                a11 = 1;
                a9 = 1;
                LODWORD(v12) = (_DWORD)v65;
LABEL_76:
                if ( v34 )
                {
LABEL_77:
                  v63 = v25;
                  v39 = a10;
                  v40 = (_QWORD *)a10;
                  v41 = *v13;
                  if ( (*v13 & 0xF8) == 0x48 )
                  {
                    switch ( v13[1] )
                    {
                      case 0x83:
                        v25[1] += (char)v13[3];
LABEL_80:
                        v13 += 4;
LABEL_90:
                        v41 = *v13;
                        break;
                      case 0x81:
                        v25[1] += *(int *)(v13 + 3);
LABEL_89:
                        v13 += 7;
                        goto LABEL_90;
                      case 0x8D:
                        v42 = v13[2] & 0xF8;
                        if ( v42 == 96 )
                        {
                          v43 = RtlpAmd64GetContextGp<_CONTEXT_FOR_STACKWALK *>(v25, v62);
                          v25[1] = v43;
                          v25[1] = v43 + (char)v13[3];
                          goto LABEL_80;
                        }
                        if ( v42 == -96 )
                        {
                          v25[1] = *(int *)(v13 + 3) + RtlpAmd64GetContextGp<_CONTEXT_FOR_STACKWALK *>(v25, v62);
                          goto LABEL_89;
                        }
                        break;
                    }
                  }
                  v44 = (_QWORD **)(v25 + 1);
                  while ( 1 )
                  {
                    if ( (v41 & 0xF8) == 0x58 )
                    {
                      v45 = (_QWORD *)v25[1];
                      if ( *v40
                        && ((unsigned __int64)v45 < *(_QWORD *)*v40
                         || (unsigned __int64)v45 > **(_QWORD **)(v39 + 8) - 8LL) )
                      {
                        return 3221225512LL;
                      }
                      RtlpAmd64SetContextGp<_CONTEXT_FOR_STACKWALK *>(v25, v41 & 7, *v45);
                      v49 = *(_QWORD *)(v39 + 16);
                      if ( v49 )
                        *(_QWORD *)(v49 + 8LL * v47 + 128) = v46;
                      *v48 += 8LL;
                      ++v13;
                      v44 = (_QWORD **)(v25 + 1);
                    }
                    else
                    {
                      if ( (v41 & 0xF0) != 0x40 || (v13[1] & 0xF8) != 0x58 )
                      {
                        if ( !*v40
                          || (unsigned __int64)*v44 >= *(_QWORD *)*v40
                          && (unsigned __int64)*v44 <= **(_QWORD **)(v39 + 8) - 8LL )
                        {
                          v34 = a11;
                          v54 = *v44;
                          *v25 = **v44;
                          *v44 = v54 + 1;
                          RtlpVirtualPopShadowStack<_CONTEXT_FOR_STACKWALK *>(v25);
LABEL_112:
                          if ( a6 )
                            *a6 = 0;
LABEL_133:
                          if ( v34 && a12 )
                            *a8 = v25[1] - 8LL;
                          return 0;
                        }
                        return 3221225512LL;
                      }
                      v50 = *v44;
                      if ( *v40
                        && ((unsigned __int64)v50 < *(_QWORD *)*v40
                         || (unsigned __int64)v50 > **(_QWORD **)(v39 + 8) - 8LL) )
                      {
                        return 3221225512LL;
                      }
                      v51 = RtlpAmd64SetContextGp<_CONTEXT_FOR_STACKWALK *>(v25, v13[1] & 7 | (8 * (v41 & 1u)), *v50);
                      v53 = *(_QWORD *)(v39 + 16);
                      if ( v53 )
                        *(_QWORD *)(v53 + 8 * v51 + 128) = v52;
                      ++*v44;
                      v13 += 2;
                    }
                    v41 = *v13;
                  }
                }
LABEL_132:
                result = RtlpUnwindPrologue<CDirectFnEnt,CDirectUnwindInfo,CDirectMemoryAccessors,_CONTEXT_FOR_STACKWALK *>(
                           a2,
                           (_DWORD)v13,
                           *a8,
                           (_DWORD)v12,
                           (__int64)v25,
                           (__int64)a6,
                           (__int64)&v65,
                           a10);
                if ( (int)result >= 0 )
                  goto LABEL_133;
                return result;
              }
              LODWORD(v12) = (_DWORD)v65;
            }
            else if ( v36 == v37 )
            {
              v33 = (*(_BYTE *)v20 & 0x20) == 0;
LABEL_63:
              if ( v33 )
              {
LABEL_64:
                v34 = 1;
                a11 = 1;
                a9 = 1;
                goto LABEL_76;
              }
            }
          }
          v34 = 0;
          goto LABEL_76;
        }
        if ( v13[1] != 0x81 || v13[2] != 0xC4 )
        {
LABEL_41:
          if ( (v30 & 0xFE) != 0x48 )
            goto LABEL_46;
          if ( v13[1] != 0x8D )
            goto LABEL_46;
          v31 = v13[2] & 7 | (8 * (v30 & 1));
          v62 = v31;
          if ( !v31 || v31 != (*(_BYTE *)(v20 + 3) & 0xF) )
            goto LABEL_46;
          v32 = v13[2] & 0xF8;
          if ( v32 == 96 )
            goto LABEL_35;
          if ( v32 != -96 )
            goto LABEL_46;
        }
        i = v13 + 7;
        goto LABEL_45;
      }
      if ( *(_BYTE *)(v20 + 2) )
      {
        v55 = HIBYTE(*(_WORD *)(v20 + 4));
        if ( (v55 & 0xF) == 6 )
        {
          v56 = *(unsigned __int8 *)(v20 + 4);
          v57 = (_DWORD)v13 - v14;
          if ( (v55 & 0x10) != 0 )
          {
            v58 = v12[1] - v56;
            v34 = v57 - v58 < v56;
          }
          else
          {
            v58 = 0;
            v34 = 0;
          }
          if ( v34 )
            goto LABEL_130;
          v59 = *(unsigned __int8 *)(v20 + 2);
          if ( v59 > 1 )
          {
            v60 = 1;
            while ( 1 )
            {
              v61 = HIBYTE(*(_WORD *)(v20 + 2LL * v60 + 4));
              if ( (v61 & 0xF) != 6 )
                goto LABEL_128;
              v58 = *(unsigned __int8 *)(v20 + 2LL * v60 + 4) + ((unsigned __int8)v61 >> 4 << 8);
              if ( !v58 )
                goto LABEL_128;
              v58 = v12[1] - v58;
              if ( v57 - v58 < v56 )
                break;
              if ( ++v60 >= v59 )
                goto LABEL_128;
            }
            v34 = 1;
LABEL_128:
            LODWORD(v14) = a2;
          }
          if ( v34 )
          {
LABEL_130:
            RtlpUnwindEpilogue<CDirectFnEnt,CDirectUnwindInfo,CDirectMemoryAccessors,_CONTEXT_FOR_STACKWALK *>(
              v14,
              v58,
              v57 - v58,
              (_DWORD)v12,
              (__int64)v25,
              a10);
            goto LABEL_112;
          }
          goto LABEL_132;
        }
      }
    }
    v34 = 0;
    goto LABEL_132;
  }
  v15 = a5;
  v16 = a5 + 1;
  v17 = (_QWORD *)a5[1];
  if ( *(_QWORD *)a10
    && ((unsigned __int64)v17 < **(_QWORD **)a10 || (unsigned __int64)v17 > **(_QWORD **)(a10 + 8) - 8LL) )
  {
    return 3221225512LL;
  }
  if ( v13 != (_BYTE *)*v17 )
  {
    *a5 = *v17;
    *v16 += 8LL;
    RtlpVirtualPopShadowStack<_CONTEXT_FOR_STACKWALK *>(v15);
    *a8 = v19;
    if ( a6 )
      *a6 = 0;
    *a7 = 0;
    return 0;
  }
  return 3221225727LL;
}

```

## disassembly

```asm
0x18009464c  mov     rax, rsp
0x18009464f  mov     [rax+20h], r9
0x180094653  mov     [rax+18h], r8
0x180094657  mov     [rax+10h], rdx
0x18009465b  mov     [rax+8], ecx
0x18009465e  push    rbx
0x18009465f  push    rsi
0x180094660  push    rdi
0x180094661  push    r12
0x180094663  push    r13
0x180094665  push    r14
0x180094667  push    r15
0x180094669  sub     rsp, 0A0h
0x180094670  mov     r10, r9
0x180094673  mov     rdi, r8
0x180094676  mov     r11, rdx
0x180094679  test    r9, r9
0x18009467c  jnz     loc_180094746
0x180094682  mov     r9, [rsp+0D8h+arg_20]
0x18009468a  lea     r8, [r9+8]
0x18009468e  mov     [rsp+0D8h+var_68], r8
0x180094693  mov     rdx, [r8]
0x180094696  mov     [rsp+0D8h+var_58], rdx
0x18009469e  mov     rcx, [rsp+0D8h+arg_48]
0x1800946a6  mov     rax, [rcx]
0x1800946a9  test    rax, rax
0x1800946ac  jz      short loc_1800946CD
0x1800946ae  cmp     rdx, [rax]
0x1800946b1  jb      short loc_1800946C3
0x1800946b3  mov     rax, [rcx+8]
0x1800946b7  mov     rcx, [rax]
0x1800946ba  sub     rcx, 8
0x1800946be  cmp     rdx, rcx
0x1800946c1  jbe     short loc_1800946CD
0x1800946c3  mov     eax, 0C0000028h
0x1800946c8  jmp     loc_180094EE5
0x1800946cd  xor     eax, eax
0x1800946cf  jmp     short loc_1800946EE
0x1800946d1  mov     r9, [rsp+0D8h+arg_20]
0x1800946d9  mov     rdi, [rsp+0D8h+arg_10]
0x1800946e1  mov     r8, [rsp+0D8h+var_68]
0x1800946e6  mov     rdx, [rsp+0D8h+var_58]
0x1800946ee  test    eax, eax
0x1800946f0  js      loc_180094EE5
0x1800946f6  mov     rax, [rdx]
0x1800946f9  cmp     rdi, rax
0x1800946fc  jnz     short loc_180094708
0x1800946fe  mov     eax, 0C00000FFh
0x180094703  jmp     loc_180094EE5
0x180094708  mov     [r9], rax
0x18009470b  add     qword ptr [r8], 8
0x18009470f  mov     rcx, r9
0x180094712  call    ??$RtlpVirtualPopShadowStack@PEAU_CONTEXT_FOR_STACKWALK@@@@YAXPEAU_CONTEXT_FOR_STACKWALK@@KK@Z; RtlpVirtualPopShadowStack<_CONTEXT_FOR_STACKWALK *>(_CONTEXT_FOR_STACKWALK *,ulong,ulong)
0x180094717  mov     rax, [rsp+0D8h+arg_38]
0x18009471f  mov     [rax], rdx
0x180094722  mov     rax, [rsp+0D8h+arg_28]
0x18009472a  test    rax, rax
0x18009472d  jz      short loc_180094732
0x18009472f  mov     byte ptr [rax], 0
0x180094732  mov     rax, [rsp+0D8h+arg_30]
0x18009473a  mov     qword ptr [rax], 0
0x180094741  jmp     loc_180094EE3
0x180094746  mov     ebx, [r9+8]
0x18009474a  add     rbx, rdx
0x18009474d  movzx   esi, byte ptr [rbx]
0x180094750  and     esi, 7
0x180094753  cmp     esi, 3
0x180094756  jb      short loc_1800947A8
0x180094758  mov     rax, [rsp+0D8h+arg_48]
0x180094760  mov     [rsp+0D8h+var_88], rax
0x180094765  mov     rax, [rsp+0D8h+arg_38]
0x18009476d  mov     [rsp+0D8h+var_98], rax
0x180094772  mov     rax, [rsp+0D8h+arg_30]
0x18009477a  mov     [rsp+0D8h+var_A0], rax
0x18009477f  mov     rax, [rsp+0D8h+arg_28]
0x180094787  mov     [rsp+0D8h+var_A8], rax
0x18009478c  mov     rax, [rsp+0D8h+arg_20]
0x180094794  mov     [rsp+0D8h+var_B0], rax
0x180094799  mov     [rsp+0D8h+var_B8], rbx
0x18009479e  call    ??$RtlpxVirtualUnwindV3@VCDirectFnEnt@@VCDirectUnwindInfo@@VCDirectMemoryAccessors@@PEAU_CONTEXT_FOR_STACKWALK@@@@YAJK_K0VCDirectFnEnt@@VCDirectUnwindInfo@@PEAU_CONTEXT_FOR_STACKWALK@@PEAEPEAPEAXPEA_KPEAP6A?AW4_EXCEPTION_DISPOSITION@@PEAU_EXCEPTION_RECORD@@PEAXPEAU_CONTEXT@@8@ZPEAU_AMD64_UNWIND_PARAMS@@KPEAK@Z; RtlpxVirtualUnwindV3<CDirectFnEnt,CDirectUnwindInfo,CDirectMemoryAccessors,_CONTEXT_FOR_STACKWALK *>(ulong,unsigned __int64,unsigned __int64,CDirectFnEnt,CDirectUnwindInfo,_CONTEXT_FOR_STACKWALK *,uchar *,void * *,unsigned __int64 *,_EXCEPTION_DISPOSITION (**)(_EXCEPTION_RECORD *,void *,_CONTEXT *,void *),_AMD64_UNWIND_PARAMS *,ulong,ulong *)
0x1800947a3  jmp     loc_180094EE5
0x1800947a8  xor     ecx, ecx
0x1800947aa  mov     [rsp+0D8h+arg_50], ecx
0x1800947b1  mov     [rsp+0D8h+arg_40], ecx
0x1800947b8  mov     rax, [rsp+0D8h+arg_28]
0x1800947c0  test    rax, rax
0x1800947c3  jz      short loc_1800947D2
0x1800947c5  cmp     [rax], cl
0x1800947c7  jnz     short loc_1800947D2
0x1800947c9  lea     r13d, [rcx+1]
0x1800947cd  mov     r12d, r13d
0x1800947d0  jmp     short loc_180094808
0x1800947d2  xor     r12d, r12d
0x1800947d5  cmp     esi, 2
0x1800947d8  jnb     short loc_180094802
0x1800947da  mov     r8, rbx
0x1800947dd  mov     rcx, r9
0x1800947e0  call    ??$RtlpxTrivialFunction@VCDirectFnEnt@@VCDirectUnwindInfo@@@@YAKVCDirectFnEnt@@_KVCDirectUnwindInfo@@PEBU_AMD64_UNWIND_PARAMS@@@Z; RtlpxTrivialFunction<CDirectFnEnt,CDirectUnwindInfo>(CDirectFnEnt,unsigned __int64,CDirectUnwindInfo,_AMD64_UNWIND_PARAMS const *)
0x1800947e5  lea     r13d, [r12+1]
0x1800947ea  test    eax, eax
0x1800947ec  cmovnz  r12d, r13d
0x1800947f0  mov     r10, [rsp+0D8h+arg_18]
0x1800947f8  mov     r11, [rsp+0D8h+arg_8]
0x180094800  jmp     short loc_180094808
0x180094802  mov     r13d, 1
0x180094808  mov     [rsp+0D8h+arg_58], 0
0x180094813  test    byte ptr [rbx+3], 0Fh
0x180094817  jz      short loc_180094880
0x180094819  mov     r14d, edi
0x18009481c  sub     r14d, r11d
0x18009481f  sub     r14d, [r10]
0x180094822  movzx   eax, byte ptr [rbx+1]
0x180094826  cmp     r14d, eax
0x180094829  jnb     short loc_180094878
0x18009482b  test    byte ptr [rbx], 20h
0x18009482e  jnz     short loc_180094878
0x180094830  xor     r15d, r15d
0x180094833  cmp     [rbx+2], r15b
0x180094837  jbe     short loc_18009486D
0x180094839  movzx   ecx, word ptr [rbx+r15*2+4]
0x18009483f  movzx   eax, cx
0x180094842  shr     ax, 8
0x180094846  and     al, 0Fh
0x180094848  cmp     al, 3
0x18009484a  jz      short loc_18009485D
0x18009484c  call    RtlpUnwindOpSlots
0x180094851  add     r15d, eax
0x180094854  movzx   eax, byte ptr [rbx+2]
0x180094858  cmp     r15d, eax
0x18009485b  jb      short loc_180094839
0x18009485d  mov     r10, [rsp+0D8h+arg_18]
0x180094865  mov     r11, [rsp+0D8h+arg_8]
0x18009486d  movzx   ecx, byte ptr [rbx+r15*2+4]
0x180094873  cmp     r14d, ecx
0x180094876  jb      short loc_180094880
0x180094878  mov     [rsp+0D8h+arg_58], r13d
0x180094880  mov     r15, [rsp+0D8h+arg_20]
0x180094888  cmp     [rsp+0D8h+arg_58], 0
0x180094890  jnz     short loc_180094898
0x180094892  mov     rax, [r15+8]
0x180094896  jmp     short loc_1800948B6
0x180094898  movzx   r8d, byte ptr [rbx+3]
0x18009489d  mov     edx, r8d
0x1800948a0  and     edx, 0Fh
0x1800948a3  mov     rcx, r15
0x1800948a6  call    ??$RtlpAmd64GetContextGp@PEAU_CONTEXT_FOR_STACKWALK@@@@YA_KPEAU_CONTEXT_FOR_STACKWALK@@KPEBU_AMD64_UNWIND_PARAMS@@@Z; RtlpAmd64GetContextGp<_CONTEXT_FOR_STACKWALK *>(_CONTEXT_FOR_STACKWALK *,ulong,_AMD64_UNWIND_PARAMS const *)
0x1800948ab  mov     ecx, 0FFFFFFF0h
0x1800948b0  and     r8, rcx
0x1800948b3  sub     rax, r8
0x1800948b6  mov     rcx, [rsp+0D8h+arg_38]
0x1800948be  mov     [rcx], rax
0x1800948c1  test    r12d, r12d
0x1800948c4  jnz     loc_180094E70
0x1800948ca  cmp     esi, 2
0x1800948cd  jnb     loc_180094D97
0x1800948d3  mov     rcx, rdi
0x1800948d6  movzx   edx, byte ptr [rdi]
0x1800948d9  mov     dword ptr [rsp+0D8h+var_68], r12d
0x1800948de  cmp     dl, 48h ; 'H'
0x1800948e1  jnz     short loc_180094906
0x1800948e3  cmp     byte ptr [rdi+1], 83h
0x1800948e7  jnz     short loc_1800948F5
0x1800948e9  cmp     byte ptr [rdi+2], 0C4h
0x1800948ed  jnz     short loc_1800948F5
0x1800948ef  lea     rcx, [rdi+4]
0x1800948f3  jmp     short loc_180094953
0x1800948f5  cmp     dl, 48h ; 'H'
0x1800948f8  jnz     short loc_180094906
0x1800948fa  cmp     byte ptr [rdi+1], 81h
0x1800948fe  jnz     short loc_180094906
0x180094900  cmp     byte ptr [rdi+2], 0C4h
0x180094904  jz      short loc_18009494F
0x180094906  mov     al, dl
0x180094908  and     al, 0FEh
0x18009490a  cmp     al, 48h ; 'H'
0x18009490c  jnz     short loc_180094955
0x18009490e  cmp     byte ptr [rdi+1], 8Dh
0x180094912  jnz     short loc_180094955
0x180094914  movzx   r8d, byte ptr [rdi+2]
0x180094919  mov     r9d, edx
0x18009491c  and     r9d, r13d
0x18009491f  shl     r9d, 3
0x180094923  mov     eax, r8d
0x180094926  and     eax, 7
0x180094929  or      r9d, eax
0x18009492c  mov     dword ptr [rsp+0D8h+var_68], r9d
0x180094931  jz      short loc_180094955
0x180094933  movzx   eax, byte ptr [rbx+3]
0x180094937  and     eax, 0Fh
0x18009493a  cmp     r9d, eax
0x18009493d  jnz     short loc_180094955
0x18009493f  and     r8b, 0F8h
0x180094943  cmp     r8b, 60h ; '`'
0x180094947  jz      short loc_1800948EF
0x180094949  cmp     r8b, 0A0h
0x18009494d  jnz     short loc_180094955
0x18009494f  lea     rcx, [rdi+7]
0x180094953  mov     dl, [rcx]
0x180094955  mov     al, dl
0x180094957  and     al, 0F8h
0x180094959  cmp     al, 58h ; 'X'
0x18009495b  jnz     short loc_180094962
0x18009495d  add     rcx, r13
0x180094960  jmp     short loc_180094953
0x180094962  mov     al, dl
0x180094964  and     al, 0F0h
0x180094966  cmp     al, 40h ; '@'
0x180094968  jnz     short loc_180094979
0x18009496a  mov     al, [rcx+1]
0x18009496d  and     al, 0F8h
0x18009496f  cmp     al, 58h ; 'X'
0x180094971  jnz     short loc_180094979
0x180094973  add     rcx, 2
0x180094977  jmp     short loc_180094953
0x180094979  cmp     dl, 0F2h
0x18009497c  jnz     short loc_180094983
0x18009497e  add     rcx, r13
0x180094981  mov     dl, [rcx]
0x180094983  lea     eax, [rdx+3Eh]
0x180094986  cmp     al, r13b
0x180094989  jbe     short loc_1800949DC
0x18009498b  cmp     dl, 0F3h
0x18009498e  jnz     short loc_180094996
0x180094990  cmp     byte ptr [rcx+1], 0C3h
0x180094994  jz      short loc_1800949DC
0x180094996  lea     eax, [rdx+17h]
0x180094999  test    al, 0FDh
0x18009499b  jz      short loc_1800949F1
0x18009499d  cmp     dl, 0FFh
0x1800949a0  jnz     short loc_1800949BD
0x1800949a2  cmp     byte ptr [rcx+1], 25h ; '%'
0x1800949a6  jnz     short loc_1800949BD
0x1800949a8  mov     [rsp+0D8h+arg_50], r13d
0x1800949b0  mov     [rsp+0D8h+arg_40], r13d
0x1800949b8  jmp     loc_180094A66
0x1800949bd  and     dl, 0F8h
0x1800949c0  cmp     dl, 48h ; 'H'
0x1800949c3  jnz     loc_180094A5A
0x1800949c9  cmp     byte ptr [rcx+1], 0FFh
0x1800949cd  jnz     loc_180094A5A
0x1800949d3  mov     al, [rcx+2]
0x1800949d6  and     al, 38h
0x1800949d8  cmp     al, 20h ; ' '
0x1800949da  jnz     short loc_180094A5A
0x1800949dc  mov     r12d, r13d
0x1800949df  mov     [rsp+0D8h+arg_50], r13d
0x1800949e7  mov     [rsp+0D8h+arg_40], r13d
0x1800949ef  jmp     short loc_180094A5D
0x1800949f1  mov     r8, rcx
0x1800949f4  sub     r8, r11
0x1800949f7  cmp     dl, 0EBh
0x1800949fa  jnz     short loc_180094A05
0x1800949fc  movsx   eax, byte ptr [rcx+1]
0x180094a00  add     eax, 2
0x180094a03  jmp     short loc_180094A0B
0x180094a05  mov     eax, [rcx+1]
0x180094a08  add     eax, 5
0x180094a0b  movsxd  rsi, eax
0x180094a0e  add     rsi, r8
0x180094a11  mov     ecx, [r10]
0x180094a14  cmp     rsi, rcx
0x180094a17  jb      short loc_180094A2C
0x180094a19  mov     eax, [r10+4]
0x180094a1d  cmp     rsi, rax
0x180094a20  jnb     short loc_180094A2C
0x180094a22  cmp     rsi, rcx
0x180094a25  jnz     short loc_180094A5A
0x180094a27  test    byte ptr [rbx], 20h
0x180094a2a  jmp     short loc_1800949DA
0x180094a2c  lea     r9, [rsi+r11]
0x180094a30  mov     r8, r11
0x180094a33  mov     rdx, r10
0x180094a36  lea     rcx, [rsp+0D8h+var_40]
0x180094a3e  call    ??$RtlpxSameFunction@VCDirectFnEnt@@VCDirectUnwindInfo@@@@YA?AVCDirectFnEnt@@V0@_K1PEBU_AMD64_UNWIND_PARAMS@@@Z; RtlpxSameFunction<CDirectFnEnt,CDirectUnwindInfo>(CDirectFnEnt,unsigned __int64,unsigned __int64,_AMD64_UNWIND_PARAMS const *)
0x180094a43  mov     rcx, [rax]
0x180094a46  test    rcx, rcx
0x180094a49  jz      short loc_180094AAB
0x180094a4b  mov     eax, [rcx]
0x180094a4d  cmp     rsi, rax
0x180094a50  jz      short loc_180094AAB
0x180094a52  mov     r10, [rsp+0D8h+arg_18]
0x180094a5a  xor     r12d, r12d
0x180094a5d  test    r12d, r12d
0x180094a60  jz      loc_180094E73
0x180094a66  mov     r14, r15
0x180094a69  mov     [rsp+0D8h+var_40], r15
0x180094a71  mov     rbx, [rsp+0D8h+arg_48]
0x180094a79  mov     rsi, rbx
0x180094a7c  mov     [rsp+0D8h+var_60], rdi
0x180094a81  mov     dl, [rdi]
0x180094a83  mov     byte ptr [rsp+0D8h+arg_0], dl
0x180094a8a  mov     al, dl
0x180094a8c  and     al, 0F8h
0x180094a8e  cmp     al, 48h ; 'H'
0x180094a90  jnz     loc_180094B32
0x180094a96  cmp     byte ptr [rdi+1], 83h
0x180094a9a  jnz     short loc_180094AC8
0x180094a9c  movsx   rax, byte ptr [rdi+3]
0x180094aa1  add     [r15+8], rax
0x180094aa5  add     rdi, 4
  ... truncated ...
```
