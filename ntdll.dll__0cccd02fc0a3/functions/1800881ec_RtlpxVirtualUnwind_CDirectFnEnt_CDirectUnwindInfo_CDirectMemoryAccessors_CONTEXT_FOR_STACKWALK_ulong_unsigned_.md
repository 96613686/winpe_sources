# RtlpxVirtualUnwind<CDirectFnEnt,CDirectUnwindInfo,CDirectMemoryAccessors,_CONTEXT_FOR_STACKWALK *>(ulong,unsigned __int64,unsigned __int64,CDirectFnEnt,_CONTEXT_FOR_STACKWALK *,uchar *,void * *,unsigned __int64 *,_EXCEPTION_DISPOSITION (**)(_EXCEPTION_RECORD *,void *,_CONTEXT *,void *),_AMD64_UNWIND_PARAMS *,ulong,ulong *)

- ea: `0x1800881ec`
- end: `0x180088a99`
- name: `??$RtlpxVirtualUnwind@VCDirectFnEnt@@VCDirectUnwindInfo@@VCDirectMemoryAccessors@@PEAU_CONTEXT_FOR_STACKWALK@@@@YAJK_K0VCDirectFnEnt@@PEAU_CONTEXT_FOR_STACKWALK@@PEAEPEAPEAXPEA_KPEAP6A?AW4_EXCEPTION_DISPOSITION@@PEAU_EXCEPTION_RECORD@@PEAXPEAU_CONTEXT@@7@ZPEAU_AMD64_UNWIND_PARAMS@@KPEAK@Z`
- size: `2221`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180087224`

## callees

- `0x1800881ec`
- `0x1800e1fc8`
- `0x1800f80c4`
- `0x1800fbd3c`
- `0x180103208`
- `0x180116b94`
- `0x1801497fc`
- `0x180149874`
- `0x180149d4c`
- `0x18014bd54`

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
0x1800881ec  mov     rax, rsp
0x1800881ef  mov     [rax+20h], r9
0x1800881f3  mov     [rax+18h], r8
0x1800881f7  mov     [rax+10h], rdx
0x1800881fb  mov     [rax+8], ecx
0x1800881fe  push    rbx
0x1800881ff  push    rsi
0x180088200  push    rdi
0x180088201  push    r12
0x180088203  push    r13
0x180088205  push    r14
0x180088207  push    r15
0x180088209  sub     rsp, 0A0h
0x180088210  mov     r10, r9
0x180088213  mov     rdi, r8
0x180088216  mov     r11, rdx
0x180088219  test    r9, r9
0x18008821c  jnz     loc_1800882E6
0x180088222  mov     r9, [rsp+0D8h+arg_20]
0x18008822a  lea     r8, [r9+8]
0x18008822e  mov     [rsp+0D8h+var_68], r8
0x180088233  mov     rdx, [r8]
0x180088236  mov     [rsp+0D8h+var_58], rdx
0x18008823e  mov     rcx, [rsp+0D8h+arg_48]
0x180088246  mov     rax, [rcx]
0x180088249  test    rax, rax
0x18008824c  jz      short loc_18008826D
0x18008824e  cmp     rdx, [rax]
0x180088251  jb      short loc_180088263
0x180088253  mov     rax, [rcx+8]
0x180088257  mov     rcx, [rax]
0x18008825a  sub     rcx, 8
0x18008825e  cmp     rdx, rcx
0x180088261  jbe     short loc_18008826D
0x180088263  mov     eax, 0C0000028h
0x180088268  jmp     loc_180088A85
0x18008826d  xor     eax, eax
0x18008826f  jmp     short loc_18008828E
0x180088271  mov     r9, [rsp+0D8h+arg_20]
0x180088279  mov     rdi, [rsp+0D8h+arg_10]
0x180088281  mov     r8, [rsp+0D8h+var_68]
0x180088286  mov     rdx, [rsp+0D8h+var_58]
0x18008828e  test    eax, eax
0x180088290  js      loc_180088A85
0x180088296  mov     rax, [rdx]
0x180088299  cmp     rdi, rax
0x18008829c  jnz     short loc_1800882A8
0x18008829e  mov     eax, 0C00000FFh
0x1800882a3  jmp     loc_180088A85
0x1800882a8  mov     [r9], rax
0x1800882ab  add     qword ptr [r8], 8
0x1800882af  mov     rcx, r9
0x1800882b2  call    ??$RtlpVirtualPopShadowStack@PEAU_CONTEXT_FOR_STACKWALK@@@@YAXPEAU_CONTEXT_FOR_STACKWALK@@KK@Z; RtlpVirtualPopShadowStack<_CONTEXT_FOR_STACKWALK *>(_CONTEXT_FOR_STACKWALK *,ulong,ulong)
0x1800882b7  mov     rax, [rsp+0D8h+arg_38]
0x1800882bf  mov     [rax], rdx
0x1800882c2  mov     rax, [rsp+0D8h+arg_28]
0x1800882ca  test    rax, rax
0x1800882cd  jz      short loc_1800882D2
0x1800882cf  mov     byte ptr [rax], 0
0x1800882d2  mov     rax, [rsp+0D8h+arg_30]
0x1800882da  mov     qword ptr [rax], 0
0x1800882e1  jmp     loc_180088A83
0x1800882e6  mov     ebx, [r9+8]
0x1800882ea  add     rbx, rdx
0x1800882ed  movzx   esi, byte ptr [rbx]
0x1800882f0  and     esi, 7
0x1800882f3  cmp     esi, 3
0x1800882f6  jb      short loc_180088348
0x1800882f8  mov     rax, [rsp+0D8h+arg_48]
0x180088300  mov     [rsp+0D8h+var_88], rax
0x180088305  mov     rax, [rsp+0D8h+arg_38]
0x18008830d  mov     [rsp+0D8h+var_98], rax
0x180088312  mov     rax, [rsp+0D8h+arg_30]
0x18008831a  mov     [rsp+0D8h+var_A0], rax
0x18008831f  mov     rax, [rsp+0D8h+arg_28]
0x180088327  mov     [rsp+0D8h+var_A8], rax
0x18008832c  mov     rax, [rsp+0D8h+arg_20]
0x180088334  mov     [rsp+0D8h+var_B0], rax
0x180088339  mov     [rsp+0D8h+var_B8], rbx
0x18008833e  call    ??$RtlpxVirtualUnwindV3@VCDirectFnEnt@@VCDirectUnwindInfo@@VCDirectMemoryAccessors@@PEAU_CONTEXT_FOR_STACKWALK@@@@YAJK_K0VCDirectFnEnt@@VCDirectUnwindInfo@@PEAU_CONTEXT_FOR_STACKWALK@@PEAEPEAPEAXPEA_KPEAP6A?AW4_EXCEPTION_DISPOSITION@@PEAU_EXCEPTION_RECORD@@PEAXPEAU_CONTEXT@@8@ZPEAU_AMD64_UNWIND_PARAMS@@KPEAK@Z; RtlpxVirtualUnwindV3<CDirectFnEnt,CDirectUnwindInfo,CDirectMemoryAccessors,_CONTEXT_FOR_STACKWALK *>(ulong,unsigned __int64,unsigned __int64,CDirectFnEnt,CDirectUnwindInfo,_CONTEXT_FOR_STACKWALK *,uchar *,void * *,unsigned __int64 *,_EXCEPTION_DISPOSITION (**)(_EXCEPTION_RECORD *,void *,_CONTEXT *,void *),_AMD64_UNWIND_PARAMS *,ulong,ulong *)
0x180088343  jmp     loc_180088A85
0x180088348  xor     ecx, ecx
0x18008834a  mov     [rsp+0D8h+arg_50], ecx
0x180088351  mov     [rsp+0D8h+arg_40], ecx
0x180088358  mov     rax, [rsp+0D8h+arg_28]
0x180088360  test    rax, rax
0x180088363  jz      short loc_180088372
0x180088365  cmp     [rax], cl
0x180088367  jnz     short loc_180088372
0x180088369  lea     r13d, [rcx+1]
0x18008836d  mov     r12d, r13d
0x180088370  jmp     short loc_1800883A8
0x180088372  xor     r12d, r12d
0x180088375  cmp     esi, 2
0x180088378  jnb     short loc_1800883A2
0x18008837a  mov     r8, rbx
0x18008837d  mov     rcx, r9
0x180088380  call    ??$RtlpxTrivialFunction@VCDirectFnEnt@@VCDirectUnwindInfo@@@@YAKVCDirectFnEnt@@_KVCDirectUnwindInfo@@PEBU_AMD64_UNWIND_PARAMS@@@Z; RtlpxTrivialFunction<CDirectFnEnt,CDirectUnwindInfo>(CDirectFnEnt,unsigned __int64,CDirectUnwindInfo,_AMD64_UNWIND_PARAMS const *)
0x180088385  lea     r13d, [r12+1]
0x18008838a  test    eax, eax
0x18008838c  cmovnz  r12d, r13d
0x180088390  mov     r10, [rsp+0D8h+arg_18]
0x180088398  mov     r11, [rsp+0D8h+arg_8]
0x1800883a0  jmp     short loc_1800883A8
0x1800883a2  mov     r13d, 1
0x1800883a8  mov     [rsp+0D8h+arg_58], 0
0x1800883b3  test    byte ptr [rbx+3], 0Fh
0x1800883b7  jz      short loc_180088420
0x1800883b9  mov     r14d, edi
0x1800883bc  sub     r14d, r11d
0x1800883bf  sub     r14d, [r10]
0x1800883c2  movzx   eax, byte ptr [rbx+1]
0x1800883c6  cmp     r14d, eax
0x1800883c9  jnb     short loc_180088418
0x1800883cb  test    byte ptr [rbx], 20h
0x1800883ce  jnz     short loc_180088418
0x1800883d0  xor     r15d, r15d
0x1800883d3  cmp     [rbx+2], r15b
0x1800883d7  jbe     short loc_18008840D
0x1800883d9  movzx   ecx, word ptr [rbx+r15*2+4]
0x1800883df  movzx   eax, cx
0x1800883e2  shr     ax, 8
0x1800883e6  and     al, 0Fh
0x1800883e8  cmp     al, 3
0x1800883ea  jz      short loc_1800883FD
0x1800883ec  call    RtlpUnwindOpSlots
0x1800883f1  add     r15d, eax
0x1800883f4  movzx   eax, byte ptr [rbx+2]
0x1800883f8  cmp     r15d, eax
0x1800883fb  jb      short loc_1800883D9
0x1800883fd  mov     r10, [rsp+0D8h+arg_18]
0x180088405  mov     r11, [rsp+0D8h+arg_8]
0x18008840d  movzx   ecx, byte ptr [rbx+r15*2+4]
0x180088413  cmp     r14d, ecx
0x180088416  jb      short loc_180088420
0x180088418  mov     [rsp+0D8h+arg_58], r13d
0x180088420  mov     r15, [rsp+0D8h+arg_20]
0x180088428  cmp     [rsp+0D8h+arg_58], 0
0x180088430  jnz     short loc_180088438
0x180088432  mov     rax, [r15+8]
0x180088436  jmp     short loc_180088456
0x180088438  movzx   r8d, byte ptr [rbx+3]
0x18008843d  mov     edx, r8d
0x180088440  and     edx, 0Fh
0x180088443  mov     rcx, r15
0x180088446  call    ??$RtlpAmd64GetContextGp@PEAU_CONTEXT_FOR_STACKWALK@@@@YA_KPEAU_CONTEXT_FOR_STACKWALK@@KPEBU_AMD64_UNWIND_PARAMS@@@Z; RtlpAmd64GetContextGp<_CONTEXT_FOR_STACKWALK *>(_CONTEXT_FOR_STACKWALK *,ulong,_AMD64_UNWIND_PARAMS const *)
0x18008844b  mov     ecx, 0FFFFFFF0h
0x180088450  and     r8, rcx
0x180088453  sub     rax, r8
0x180088456  mov     rcx, [rsp+0D8h+arg_38]
0x18008845e  mov     [rcx], rax
0x180088461  test    r12d, r12d
0x180088464  jnz     loc_180088A10
0x18008846a  cmp     esi, 2
0x18008846d  jnb     loc_180088937
0x180088473  mov     rcx, rdi
0x180088476  movzx   edx, byte ptr [rdi]
0x180088479  mov     dword ptr [rsp+0D8h+var_68], r12d
0x18008847e  cmp     dl, 48h ; 'H'
0x180088481  jnz     short loc_1800884A6
0x180088483  cmp     byte ptr [rdi+1], 83h
0x180088487  jnz     short loc_180088495
0x180088489  cmp     byte ptr [rdi+2], 0C4h
0x18008848d  jnz     short loc_180088495
0x18008848f  lea     rcx, [rdi+4]
0x180088493  jmp     short loc_1800884F3
0x180088495  cmp     dl, 48h ; 'H'
0x180088498  jnz     short loc_1800884A6
0x18008849a  cmp     byte ptr [rdi+1], 81h
0x18008849e  jnz     short loc_1800884A6
0x1800884a0  cmp     byte ptr [rdi+2], 0C4h
0x1800884a4  jz      short loc_1800884EF
0x1800884a6  mov     al, dl
0x1800884a8  and     al, 0FEh
0x1800884aa  cmp     al, 48h ; 'H'
0x1800884ac  jnz     short loc_1800884F5
0x1800884ae  cmp     byte ptr [rdi+1], 8Dh
0x1800884b2  jnz     short loc_1800884F5
0x1800884b4  movzx   r8d, byte ptr [rdi+2]
0x1800884b9  mov     r9d, edx
0x1800884bc  and     r9d, r13d
0x1800884bf  shl     r9d, 3
0x1800884c3  mov     eax, r8d
0x1800884c6  and     eax, 7
0x1800884c9  or      r9d, eax
0x1800884cc  mov     dword ptr [rsp+0D8h+var_68], r9d
0x1800884d1  jz      short loc_1800884F5
0x1800884d3  movzx   eax, byte ptr [rbx+3]
0x1800884d7  and     eax, 0Fh
0x1800884da  cmp     r9d, eax
0x1800884dd  jnz     short loc_1800884F5
0x1800884df  and     r8b, 0F8h
0x1800884e3  cmp     r8b, 60h ; '`'
0x1800884e7  jz      short loc_18008848F
0x1800884e9  cmp     r8b, 0A0h
0x1800884ed  jnz     short loc_1800884F5
0x1800884ef  lea     rcx, [rdi+7]
0x1800884f3  mov     dl, [rcx]
0x1800884f5  mov     al, dl
0x1800884f7  and     al, 0F8h
0x1800884f9  cmp     al, 58h ; 'X'
0x1800884fb  jnz     short loc_180088502
0x1800884fd  add     rcx, r13
0x180088500  jmp     short loc_1800884F3
0x180088502  mov     al, dl
0x180088504  and     al, 0F0h
0x180088506  cmp     al, 40h ; '@'
0x180088508  jnz     short loc_180088519
0x18008850a  mov     al, [rcx+1]
0x18008850d  and     al, 0F8h
0x18008850f  cmp     al, 58h ; 'X'
0x180088511  jnz     short loc_180088519
0x180088513  add     rcx, 2
0x180088517  jmp     short loc_1800884F3
0x180088519  cmp     dl, 0F2h
0x18008851c  jnz     short loc_180088523
0x18008851e  add     rcx, r13
0x180088521  mov     dl, [rcx]
0x180088523  lea     eax, [rdx+3Eh]
0x180088526  cmp     al, r13b
0x180088529  jbe     short loc_18008857C
0x18008852b  cmp     dl, 0F3h
0x18008852e  jnz     short loc_180088536
0x180088530  cmp     byte ptr [rcx+1], 0C3h
0x180088534  jz      short loc_18008857C
0x180088536  lea     eax, [rdx+17h]
0x180088539  test    al, 0FDh
0x18008853b  jz      short loc_180088591
0x18008853d  cmp     dl, 0FFh
0x180088540  jnz     short loc_18008855D
0x180088542  cmp     byte ptr [rcx+1], 25h ; '%'
0x180088546  jnz     short loc_18008855D
0x180088548  mov     [rsp+0D8h+arg_50], r13d
0x180088550  mov     [rsp+0D8h+arg_40], r13d
0x180088558  jmp     loc_180088606
0x18008855d  and     dl, 0F8h
0x180088560  cmp     dl, 48h ; 'H'
0x180088563  jnz     loc_1800885FA
0x180088569  cmp     byte ptr [rcx+1], 0FFh
0x18008856d  jnz     loc_1800885FA
0x180088573  mov     al, [rcx+2]
0x180088576  and     al, 38h
0x180088578  cmp     al, 20h ; ' '
0x18008857a  jnz     short loc_1800885FA
0x18008857c  mov     r12d, r13d
0x18008857f  mov     [rsp+0D8h+arg_50], r13d
0x180088587  mov     [rsp+0D8h+arg_40], r13d
0x18008858f  jmp     short loc_1800885FD
0x180088591  mov     r8, rcx
0x180088594  sub     r8, r11
0x180088597  cmp     dl, 0EBh
0x18008859a  jnz     short loc_1800885A5
0x18008859c  movsx   eax, byte ptr [rcx+1]
0x1800885a0  add     eax, 2
0x1800885a3  jmp     short loc_1800885AB
0x1800885a5  mov     eax, [rcx+1]
0x1800885a8  add     eax, 5
0x1800885ab  movsxd  rsi, eax
0x1800885ae  add     rsi, r8
0x1800885b1  mov     ecx, [r10]
0x1800885b4  cmp     rsi, rcx
0x1800885b7  jb      short loc_1800885CC
0x1800885b9  mov     eax, [r10+4]
0x1800885bd  cmp     rsi, rax
0x1800885c0  jnb     short loc_1800885CC
0x1800885c2  cmp     rsi, rcx
0x1800885c5  jnz     short loc_1800885FA
0x1800885c7  test    byte ptr [rbx], 20h
0x1800885ca  jmp     short loc_18008857A
0x1800885cc  lea     r9, [rsi+r11]
0x1800885d0  mov     r8, r11
0x1800885d3  mov     rdx, r10
0x1800885d6  lea     rcx, [rsp+0D8h+var_40]
0x1800885de  call    ??$RtlpxSameFunction@VCDirectFnEnt@@VCDirectUnwindInfo@@@@YA?AVCDirectFnEnt@@V0@_K1PEBU_AMD64_UNWIND_PARAMS@@@Z; RtlpxSameFunction<CDirectFnEnt,CDirectUnwindInfo>(CDirectFnEnt,unsigned __int64,unsigned __int64,_AMD64_UNWIND_PARAMS const *)
0x1800885e3  mov     rcx, [rax]
0x1800885e6  test    rcx, rcx
0x1800885e9  jz      short loc_18008864B
0x1800885eb  mov     eax, [rcx]
0x1800885ed  cmp     rsi, rax
0x1800885f0  jz      short loc_18008864B
0x1800885f2  mov     r10, [rsp+0D8h+arg_18]
0x1800885fa  xor     r12d, r12d
0x1800885fd  test    r12d, r12d
0x180088600  jz      loc_180088A13
0x180088606  mov     r14, r15
0x180088609  mov     [rsp+0D8h+var_40], r15
0x180088611  mov     rbx, [rsp+0D8h+arg_48]
0x180088619  mov     rsi, rbx
0x18008861c  mov     [rsp+0D8h+var_60], rdi
0x180088621  mov     dl, [rdi]
0x180088623  mov     byte ptr [rsp+0D8h+arg_0], dl
0x18008862a  mov     al, dl
0x18008862c  and     al, 0F8h
0x18008862e  cmp     al, 48h ; 'H'
0x180088630  jnz     loc_1800886D2
0x180088636  cmp     byte ptr [rdi+1], 83h
0x18008863a  jnz     short loc_180088668
0x18008863c  movsx   rax, byte ptr [rdi+3]
0x180088641  add     [r15+8], rax
0x180088645  add     rdi, 4
  ... truncated ...
```
