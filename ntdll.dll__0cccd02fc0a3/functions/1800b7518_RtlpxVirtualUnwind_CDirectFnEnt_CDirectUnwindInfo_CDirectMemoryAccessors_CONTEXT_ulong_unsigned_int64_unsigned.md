# RtlpxVirtualUnwind<CDirectFnEnt,CDirectUnwindInfo,CDirectMemoryAccessors,_CONTEXT *>(ulong,unsigned __int64,unsigned __int64,CDirectFnEnt,_CONTEXT *,uchar *,void * *,unsigned __int64 *,_EXCEPTION_DISPOSITION (**)(_EXCEPTION_RECORD *,void *,_CONTEXT *,void *),_AMD64_UNWIND_PARAMS *,ulong,ulong *)

- ea: `0x1800b7518`
- end: `0x1800b7f56`
- name: `??$RtlpxVirtualUnwind@VCDirectFnEnt@@VCDirectUnwindInfo@@VCDirectMemoryAccessors@@PEAU_CONTEXT@@@@YAJK_K0VCDirectFnEnt@@PEAU_CONTEXT@@PEAEPEAPEAXPEA_KPEAP6A?AW4_EXCEPTION_DISPOSITION@@PEAU_EXCEPTION_RECORD@@PEAX27@ZPEAU_AMD64_UNWIND_PARAMS@@KPEAK@Z`
- size: `2622`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x1800b6964`
- `0x1800b6a60`
- `0x1801146d0`
- `0x180115040`

## callees

- `0x1800b7518`
- `0x1800bf884`
- `0x1800e1fc8`
- `0x1800fbd3c`
- `0x180103208`
- `0x180116514`
- `0x1801497c4`
- `0x180149834`
- `0x180149974`
- `0x18014bac8`

## pseudocode

```c
__int64 __fastcall RtlpxVirtualUnwind<CDirectFnEnt,CDirectUnwindInfo,CDirectMemoryAccessors,_CONTEXT *>(
        int a1,
        __int64 a2,
        _BYTE *a3,
        unsigned int *a4,
        __int64 a5,
        _BYTE *a6,
        _QWORD *a7,
        __int64 *a8,
        _QWORD *a9,
        __int64 a10,
        unsigned int a11,
        int a12)
{
  unsigned int *v12; // rax
  _BYTE *v13; // r14
  int v14; // r10d
  __int64 v15; // r8
  _QWORD *v16; // rdx
  _QWORD *v17; // rbx
  __int64 result; // rax
  __int64 v19; // rbx
  unsigned int v20; // r15d
  BOOL v21; // r13d
  unsigned int v22; // edi
  __int64 v23; // r12
  __int64 v24; // r12
  __int64 v25; // rdx
  int v26; // edi
  _BYTE *v27; // rdx
  char v28; // r8
  unsigned int v29; // r15d
  char v30; // r9
  bool v31; // zf
  BOOL v32; // edi
  int v33; // ecx
  unsigned __int64 v34; // rdi
  unsigned __int64 v35; // rdx
  _QWORD *v36; // rax
  __int64 v37; // rcx
  _QWORD *v38; // r9
  char v39; // dl
  char v40; // al
  __int64 Context; // rax
  __int64 v42; // rbx
  _QWORD **v43; // rbx
  unsigned int v44; // edi
  _QWORD *v45; // rbx
  __int64 v46; // rcx
  _QWORD *v47; // r15
  __int64 v48; // rdi
  __int64 v49; // rcx
  _QWORD *v50; // rcx
  int v51; // edx
  unsigned int v52; // r15d
  int v53; // r11d
  int v54; // r10d
  unsigned int v55; // r8d
  unsigned int v56; // edi
  unsigned int v57; // r9d
  __int16 v58; // r11
  _BYTE *v59; // rcx
  __int64 v60; // r9
  int v61; // [rsp+74h] [rbp-74h]
  __int64 v62; // [rsp+A0h] [rbp-48h]
  __int64 v63[8]; // [rsp+A8h] [rbp-40h] BYREF
  unsigned int *v66; // [rsp+108h] [rbp+20h] BYREF

  v66 = a4;
  v12 = a4;
  v13 = a3;
  v14 = a2;
  if ( a4 )
  {
    v19 = a2 + a4[2];
    v20 = *(_BYTE *)v19 & 7;
    if ( v20 >= 3 )
      return RtlpxVirtualUnwindV3<CDirectFnEnt,CDirectUnwindInfo,CDirectMemoryAccessors,_CONTEXT *>(
               a1,
               a2,
               (_DWORD)a3,
               (_DWORD)a4,
               v19,
               a5,
               (__int64)a6,
               (__int64)a7,
               (__int64)a8,
               (__int64)a9,
               a10);
    v62 = 0;
    a12 = 0;
    if ( !a6 || *a6 )
    {
      v21 = 0;
      if ( v20 < 2 )
      {
        v21 = RtlpxTrivialFunction<CDirectFnEnt,CDirectUnwindInfo>(a4, a2, v19) != 0;
        v12 = v66;
        v14 = a2;
      }
    }
    else
    {
      v21 = 1;
    }
    v61 = 0;
    if ( (*(_BYTE *)(v19 + 3) & 0xF) != 0 )
    {
      v22 = (_DWORD)v13 - v14 - *v12;
      if ( v22 >= *(unsigned __int8 *)(v19 + 1) || (*(_BYTE *)v19 & 0x20) != 0 )
      {
        v61 = 1;
      }
      else
      {
        v23 = 0;
        if ( *(_BYTE *)(v19 + 2) )
        {
          do
          {
            if ( (HIBYTE(*(_WORD *)(v19 + 2 * v23 + 4)) & 0xF) == 3 )
              break;
            v23 = (unsigned int)RtlpUnwindOpSlots() + (unsigned int)v23;
          }
          while ( (unsigned int)v23 < *(unsigned __int8 *)(v19 + 2) );
          v12 = v66;
        }
        if ( v22 >= *(unsigned __int8 *)(v19 + 2 * v23 + 4) )
          v61 = 1;
      }
    }
    v24 = a5;
    if ( v61 )
    {
      v26 = *(unsigned __int8 *)(v19 + 3);
      v25 = RtlpAmd64GetContextGp<_CONTEXT *>(a5, *(_BYTE *)(v19 + 3) & 0xF) - (v26 & 0xFFFFFFF0);
      v12 = v66;
    }
    else
    {
      v25 = *(_QWORD *)(a5 + 152);
    }
    *a8 = v25;
    if ( !v21 )
    {
      if ( v20 < 2 )
      {
        v27 = v13;
        v28 = *v13;
        v29 = 0;
        if ( *v13 == 72 )
        {
          if ( v13[1] == 0x83 && v13[2] == 0xC4 )
          {
            v27 = v13 + 4;
LABEL_38:
            v28 = *v27;
            goto LABEL_39;
          }
          if ( v13[1] == 0x81 && v13[2] == 0xC4 )
          {
            v27 = v13 + 7;
            goto LABEL_38;
          }
        }
        if ( (v28 & 0xFE) == 0x48 && v13[1] == 0x8D )
        {
          v29 = v13[2] & 7 | (8 * (v28 & 1));
          if ( v29 )
          {
            if ( v29 == (*(_BYTE *)(v19 + 3) & 0xF) )
            {
              v30 = v13[2] & 0xF8;
              if ( v30 == 96 )
              {
                v27 = v13 + 4;
                goto LABEL_55;
              }
              if ( v30 == -96 )
              {
                v27 = v13 + 7;
                goto LABEL_55;
              }
            }
          }
        }
        while ( 1 )
        {
LABEL_39:
          if ( (v28 & 0xF8) == 0x58 )
          {
            ++v27;
          }
          else
          {
            if ( (v28 & 0xF0) != 0x40 || (v27[1] & 0xF8) != 0x58 )
            {
              if ( v28 == -14 )
                v28 = *++v27;
              if ( (unsigned __int8)(v28 + 62) <= 1u || v28 == -13 && v27[1] == 0xC3 )
                goto LABEL_69;
              if ( ((v28 + 23) & 0xFD) != 0 )
              {
                if ( v28 == -1 && v27[1] == 37 )
                {
                  a12 = 1;
                  goto LABEL_82;
                }
                if ( (v28 & 0xF8) == 0x48 && v27[1] == 0xFF )
                {
                  v31 = (v27[2] & 0x38) == 32;
                  goto LABEL_68;
                }
                goto LABEL_80;
              }
              if ( v28 == -21 )
                v33 = (char)v27[1] + 2;
              else
                v33 = *(_DWORD *)(v27 + 1) + 5;
              v34 = (unsigned __int64)&v27[v33 - a2];
              v35 = *v12;
              if ( v34 < v35 || v34 >= v12[1] )
              {
                v36 = (_QWORD *)RtlpxSameFunction<CDirectFnEnt,CDirectUnwindInfo>(v63, v12, a2, v34 + a2);
                if ( *v36 && v34 != *(_DWORD *)*v36 )
                {
                  LODWORD(v12) = (_DWORD)v66;
                  goto LABEL_80;
                }
                v32 = 1;
                a12 = 1;
                LODWORD(v12) = (_DWORD)v66;
              }
              else
              {
                if ( v34 != v35 )
                  goto LABEL_80;
                v31 = (*(_BYTE *)v19 & 0x20) == 0;
LABEL_68:
                if ( v31 )
                {
LABEL_69:
                  v32 = 1;
                  a12 = 1;
                }
                else
                {
LABEL_80:
                  v32 = a12;
                }
              }
              if ( v32 )
              {
LABEL_82:
                v63[0] = v24;
                v37 = a10;
                v38 = (_QWORD *)a10;
                v39 = *v13;
                LOBYTE(a11) = v39;
                if ( (v39 & 0xF8) == 0x48 )
                {
                  switch ( v13[1] )
                  {
                    case 0x83:
                      *(_QWORD *)(v24 + 152) += (char)v13[3];
                      v13 += 4;
                      goto LABEL_94;
                    case 0x81:
                      *(_QWORD *)(v24 + 152) += *(int *)(v13 + 3);
                      goto LABEL_93;
                    case 0x8D:
                      v40 = v13[2] & 0xF8;
                      if ( v40 == 96 )
                      {
                        Context = RtlpAmd64GetContextGp<_CONTEXT *>(v24, v29);
                        *(_QWORD *)(v24 + 152) = Context;
                        *(_QWORD *)(v24 + 152) = Context + (char)v13[3];
                        v13 += 4;
                        v37 = a10;
                        v38 = (_QWORD *)a10;
                        goto LABEL_94;
                      }
                      if ( v40 == -96 )
                      {
                        v42 = *(int *)(v13 + 3);
                        *(_QWORD *)(v24 + 152) = RtlpAmd64GetContextGp<_CONTEXT *>(v24, v29) + v42;
                        v37 = a10;
                        v38 = (_QWORD *)a10;
LABEL_93:
                        v13 += 7;
LABEL_94:
                        v39 = *v13;
                        LOBYTE(a11) = *v13;
                      }
                      break;
                  }
                }
                v43 = (_QWORD **)(v24 + 152);
                while ( 1 )
                {
                  if ( (v39 & 0xF8) == 0x58 )
                  {
                    v44 = v39 & 7;
                    a11 = v44;
                    v45 = *(_QWORD **)(v24 + 152);
                    if ( *v38
                      && ((unsigned __int64)v45 < *(_QWORD *)*v38 || (unsigned __int64)v45 > **(_QWORD **)(v37 + 8)
                                                                                           - 8LL) )
                    {
                      return 3221225512LL;
                    }
                    RtlpAmd64SetContextGp<_CONTEXT *>(v24, v39 & 7, *v45);
                    v46 = *(_QWORD *)(a10 + 16);
                    if ( v46 )
                      *(_QWORD *)(v46 + 8LL * v44 + 128) = v45;
                    *(_QWORD *)(v24 + 152) += 8LL;
                    ++v13;
                    v43 = (_QWORD **)(v63[0] + 152);
                  }
                  else
                  {
                    if ( (v39 & 0xF0) != 0x40 || (v13[1] & 0xF8) != 0x58 )
                    {
                      if ( !*v38
                        || (unsigned __int64)*v43 >= *(_QWORD *)*v38
                        && (unsigned __int64)*v43 <= **(_QWORD **)(v37 + 8) - 8LL )
                      {
                        v32 = a12;
                        v50 = *v43;
                        *(_QWORD *)(v24 + 248) = **v43;
                        *v43 = v50 + 1;
                        RtlpVirtualPopShadowStack<_CONTEXT *>(v24);
LABEL_116:
                        if ( a6 )
                          *a6 = 0;
LABEL_142:
                        if ( a9 )
                          *a9 = v62;
                        if ( v32 && v61 )
                          *a8 = *(_QWORD *)(v24 + 152) - 8LL;
                        return 0;
                      }
                      return 3221225512LL;
                    }
                    v47 = *v43;
                    if ( *v38
                      && ((unsigned __int64)v47 < *(_QWORD *)*v38 || (unsigned __int64)v47 > **(_QWORD **)(v37 + 8)
                                                                                           - 8LL) )
                    {
                      return 3221225512LL;
                    }
                    v48 = v13[1] & 7 | (8 * (v39 & 1u));
                    RtlpAmd64SetContextGp<_CONTEXT *>(v24, (unsigned int)v48, *v47);
                    v49 = *(_QWORD *)(a10 + 16);
                    if ( v49 )
                      *(_QWORD *)(v49 + 8 * v48 + 128) = v47;
                    ++*v43;
                    v13 += 2;
                  }
                  v39 = *v13;
                  LOBYTE(a11) = *v13;
                  v37 = a10;
                  v38 = (_QWORD *)a10;
                }
              }
LABEL_137:
              result = RtlpUnwindPrologue<CDirectFnEnt,CDirectUnwindInfo,CDirectMemoryAccessors,_CONTEXT *>(
                         a2,
                         (_DWORD)v13,
                         *a8,
                         (_DWORD)v12,
                         v24,
                         (__int64)a6,
                         (__int64)&v66,
                         a10);
              if ( (int)result >= 0 )
              {
                if ( (a1 & 0x7FFFFFFF) != 0 )
                {
                  v59 = (_BYTE *)(a2 + v66[2]);
                  if ( (_DWORD)v13 - (_DWORD)a2 - *v66 >= (unsigned __int8)v59[1]
                    && ((*v59 >> 3) & (unsigned __int8)a1) != 0 )
                  {
                    v60 = (unsigned __int8)v59[2] + (v59[2] & 1u);
                    *a7 = &v59[2 * (unsigned int)(v60 + 2) + 4];
                    v62 = a2 + *(unsigned int *)&v59[2 * v60 + 4];
                  }
                }
                goto LABEL_142;
              }
              return result;
            }
            v27 += 2;
          }
LABEL_55:
          v28 = *v27;
        }
      }
      if ( *(_BYTE *)(v19 + 2) )
      {
        v51 = *(unsigned __int16 *)(v19 + 4);
        LOWORD(v51) = BYTE1(v51);
        if ( (v51 & 0xF) == 6 )
        {
          v52 = *(unsigned __int8 *)(v19 + 4);
          v53 = a2;
          v54 = (_DWORD)v13 - a2;
          if ( (v51 & 0x10) != 0 )
          {
            v55 = v12[1] - v52;
            v32 = v54 - v55 < v52;
            a12 = v32;
          }
          else
          {
            v55 = 0;
            v32 = a12;
          }
          if ( !v32 )
          {
            v56 = *(unsigned __int8 *)(v19 + 2);
            if ( v56 <= 1 )
            {
              v32 = a12;
            }
            else
            {
              v57 = 1;
              while ( 1 )
              {
                v58 = HIBYTE(*(_WORD *)(v19 + 2LL * v57 + 4));
                LOBYTE(v51) = v58 & 0xF;
                if ( (v58 & 0xF) != 6
                  || (v51 = *(unsigned __int8 *)(v19 + 2LL * v57 + 4),
                      (v55 = v51 + ((unsigned __int8)v58 >> 4 << 8)) == 0) )
                {
LABEL_130:
                  v32 = a12;
                  goto LABEL_131;
                }
                v55 = v12[1] - v55;
                if ( v54 - v55 < v52 )
                  break;
                if ( ++v57 >= v56 )
                  goto LABEL_130;
              }
              v32 = 1;
LABEL_131:
              v53 = a2;
            }
            if ( !v32 )
              goto LABEL_137;
          }
          RtlpUnwindEpilogue<CDirectFnEnt,CDirectUnwindInfo,CDirectMemoryAccessors,_CONTEXT *>(
            v53,
            v51,
            v54 - v55,
            (_DWORD)v12,
            v24,
            a10);
          goto LABEL_116;
        }
      }
    }
    v32 = a12;
    goto LABEL_137;
  }
  v15 = a5;
  v16 = (_QWORD *)(a5 + 152);
  v17 = *(_QWORD **)(a5 + 152);
  if ( *(_QWORD *)a10
    && ((unsigned __int64)v17 < **(_QWORD **)a10 || (unsigned __int64)v17 > **(_QWORD **)(a10 + 8) - 8LL) )
  {
    return 3221225512LL;
  }
  if ( v13 != (_BYTE *)*v17 )
  {
    *(_QWORD *)(a5 + 248) = *v17;
    *v16 += 8LL;
    RtlpVirtualPopShadowStack<_CONTEXT *>(v15);
    *a8 = (__int64)v17;
    if ( a6 )
      *a6 = 0;
    *a7 = 0;
    if ( a9 )
      *a9 = 0;
    return 0;
  }
  return 3221225727LL;
}

```

## disassembly

```asm
0x1800b7518  mov     rax, rsp
0x1800b751b  mov     [rax+20h], r9
0x1800b751f  mov     [rax+18h], r8
0x1800b7523  mov     [rax+10h], rdx
0x1800b7527  mov     [rax+8], ecx
0x1800b752a  push    rbx
0x1800b752b  push    rdi
0x1800b752c  push    r12
0x1800b752e  push    r13
0x1800b7530  push    r14
0x1800b7532  push    r15
0x1800b7534  sub     rsp, 0B8h
0x1800b753b  mov     rax, r9
0x1800b753e  mov     r14, r8
0x1800b7541  mov     r10, rdx
0x1800b7544  mov     r11d, ecx
0x1800b7547  test    r9, r9
0x1800b754a  jnz     loc_1800B7639
0x1800b7550  mov     r8, [rsp+0E8h+arg_20]
0x1800b7558  lea     rdx, [r8+98h]
0x1800b755f  mov     [rsp+0E8h+var_68], rdx
0x1800b7567  mov     rbx, [rdx]
0x1800b756a  mov     [rsp+0E8h+var_60], rbx
0x1800b7572  mov     rcx, [rsp+0E8h+arg_48]
0x1800b757a  mov     rax, [rcx]
0x1800b757d  test    rax, rax
0x1800b7580  jz      short loc_1800B75A1
0x1800b7582  cmp     rbx, [rax]
0x1800b7585  jb      short loc_1800B7597
0x1800b7587  mov     rax, [rcx+8]
0x1800b758b  mov     rcx, [rax]
0x1800b758e  sub     rcx, 8
0x1800b7592  cmp     rbx, rcx
0x1800b7595  jbe     short loc_1800B75A1
0x1800b7597  mov     eax, 0C0000028h
0x1800b759c  jmp     loc_1800B7F43
0x1800b75a1  xor     eax, eax
0x1800b75a3  jmp     short loc_1800B75C5
0x1800b75a5  mov     r8, [rsp+0E8h+arg_20]
0x1800b75ad  mov     r14, [rsp+0E8h+arg_10]
0x1800b75b5  mov     rdx, [rsp+0E8h+var_68]
0x1800b75bd  mov     rbx, [rsp+0E8h+var_60]
0x1800b75c5  test    eax, eax
0x1800b75c7  js      loc_1800B7F43
0x1800b75cd  mov     rax, [rbx]
0x1800b75d0  cmp     r14, rax
0x1800b75d3  jnz     short loc_1800B75DF
0x1800b75d5  mov     eax, 0C00000FFh
0x1800b75da  jmp     loc_1800B7F43
0x1800b75df  mov     [r8+0F8h], rax
0x1800b75e6  add     qword ptr [rdx], 8
0x1800b75ea  mov     rcx, r8
0x1800b75ed  call    ??$RtlpVirtualPopShadowStack@PEAU_CONTEXT@@@@YAXPEAU_CONTEXT@@KK@Z; RtlpVirtualPopShadowStack<_CONTEXT *>(_CONTEXT *,ulong,ulong)
0x1800b75f2  mov     rax, [rsp+0E8h+arg_38]
0x1800b75fa  mov     [rax], rbx
0x1800b75fd  mov     rax, [rsp+0E8h+arg_28]
0x1800b7605  test    rax, rax
0x1800b7608  jz      short loc_1800B760D
0x1800b760a  mov     byte ptr [rax], 0
0x1800b760d  mov     rax, [rsp+0E8h+arg_30]
0x1800b7615  mov     qword ptr [rax], 0
0x1800b761c  mov     rax, [rsp+0E8h+arg_40]
0x1800b7624  test    rax, rax
0x1800b7627  jz      loc_1800B7F41
0x1800b762d  mov     qword ptr [rax], 0
0x1800b7634  jmp     loc_1800B7F41
0x1800b7639  mov     ebx, [r9+8]
0x1800b763d  add     rbx, rdx
0x1800b7640  movzx   r15d, byte ptr [rbx]
0x1800b7644  and     r15d, 7
0x1800b7648  cmp     r15d, 3
0x1800b764c  jb      short loc_1800B76AE
0x1800b764e  mov     rcx, [rsp+0E8h+arg_48]
0x1800b7656  mov     [rsp+0E8h+var_98], rcx
0x1800b765b  mov     rcx, [rsp+0E8h+arg_40]
0x1800b7663  mov     [rsp+0E8h+var_A0], rcx
0x1800b7668  mov     rcx, [rsp+0E8h+arg_38]
0x1800b7670  mov     [rsp+0E8h+var_A8], rcx
0x1800b7675  mov     rcx, [rsp+0E8h+arg_30]
0x1800b767d  mov     [rsp+0E8h+var_B0], rcx
0x1800b7682  mov     rcx, [rsp+0E8h+arg_28]
0x1800b768a  mov     [rsp+0E8h+var_B8], rcx
0x1800b768f  mov     rcx, [rsp+0E8h+arg_20]
0x1800b7697  mov     [rsp+0E8h+var_C0], rcx
0x1800b769c  mov     [rsp+0E8h+var_C8], rbx
0x1800b76a1  mov     ecx, r11d
0x1800b76a4  call    ??$RtlpxVirtualUnwindV3@VCDirectFnEnt@@VCDirectUnwindInfo@@VCDirectMemoryAccessors@@PEAU_CONTEXT@@@@YAJK_K0VCDirectFnEnt@@VCDirectUnwindInfo@@PEAU_CONTEXT@@PEAEPEAPEAXPEA_KPEAP6A?AW4_EXCEPTION_DISPOSITION@@PEAU_EXCEPTION_RECORD@@PEAX38@ZPEAU_AMD64_UNWIND_PARAMS@@KPEAK@Z; RtlpxVirtualUnwindV3<CDirectFnEnt,CDirectUnwindInfo,CDirectMemoryAccessors,_CONTEXT *>(ulong,unsigned __int64,unsigned __int64,CDirectFnEnt,CDirectUnwindInfo,_CONTEXT *,uchar *,void * *,unsigned __int64 *,_EXCEPTION_DISPOSITION (**)(_EXCEPTION_RECORD *,void *,_CONTEXT *,void *),_AMD64_UNWIND_PARAMS *,ulong,ulong *)
0x1800b76a9  jmp     loc_1800B7F43
0x1800b76ae  mov     [rsp+0E8h+var_48], 0
0x1800b76ba  xor     ecx, ecx
0x1800b76bc  mov     [rsp+0E8h+arg_58], ecx
0x1800b76c3  mov     [rsp+0E8h+var_78], ecx
0x1800b76c7  mov     rcx, [rsp+0E8h+arg_28]
0x1800b76cf  test    rcx, rcx
0x1800b76d2  jz      short loc_1800B76E3
0x1800b76d4  cmp     byte ptr [rcx], 0
0x1800b76d7  jnz     short loc_1800B76E3
0x1800b76d9  mov     edx, 1
0x1800b76de  mov     r13d, edx
0x1800b76e1  jmp     short loc_1800B7718
0x1800b76e3  xor     r13d, r13d
0x1800b76e6  cmp     r15d, 2
0x1800b76ea  jnb     short loc_1800B7713
0x1800b76ec  mov     r8, rbx
0x1800b76ef  mov     rcx, rax
0x1800b76f2  call    ??$RtlpxTrivialFunction@VCDirectFnEnt@@VCDirectUnwindInfo@@@@YAKVCDirectFnEnt@@_KVCDirectUnwindInfo@@PEBU_AMD64_UNWIND_PARAMS@@@Z; RtlpxTrivialFunction<CDirectFnEnt,CDirectUnwindInfo>(CDirectFnEnt,unsigned __int64,CDirectUnwindInfo,_AMD64_UNWIND_PARAMS const *)
0x1800b76f7  lea     edx, [r13+1]
0x1800b76fb  test    eax, eax
0x1800b76fd  cmovnz  r13d, edx
0x1800b7701  mov     rax, [rsp+0E8h+arg_18]
0x1800b7709  mov     r10, [rsp+0E8h+arg_8]
0x1800b7711  jmp     short loc_1800B7718
0x1800b7713  mov     edx, 1
0x1800b7718  mov     [rsp+0E8h+var_74], 0
0x1800b7720  test    byte ptr [rbx+3], 0Fh
0x1800b7724  jz      short loc_1800B7788
0x1800b7726  mov     edi, r14d
0x1800b7729  sub     edi, r10d
0x1800b772c  sub     edi, [rax]
0x1800b772e  movzx   ecx, byte ptr [rbx+1]
0x1800b7732  cmp     edi, ecx
0x1800b7734  jnb     short loc_1800B7784
0x1800b7736  test    byte ptr [rbx], 20h
0x1800b7739  jnz     short loc_1800B7784
0x1800b773b  xor     r12d, r12d
0x1800b773e  cmp     [rbx+2], r12b
0x1800b7742  jbe     short loc_1800B7770
0x1800b7744  movzx   ecx, word ptr [rbx+r12*2+4]
0x1800b774a  movzx   eax, cx
0x1800b774d  shr     ax, 8
0x1800b7751  and     al, 0Fh
0x1800b7753  cmp     al, 3
0x1800b7755  jz      short loc_1800B7768
0x1800b7757  call    RtlpUnwindOpSlots
0x1800b775c  add     r12d, eax
0x1800b775f  movzx   eax, byte ptr [rbx+2]
0x1800b7763  cmp     r12d, eax
0x1800b7766  jb      short loc_1800B7744
0x1800b7768  mov     rax, [rsp+0E8h+arg_18]
0x1800b7770  movzx   edx, byte ptr [rbx+r12*2+4]
0x1800b7776  cmp     edi, edx
0x1800b7778  jb      short loc_1800B7788
0x1800b777a  mov     [rsp+0E8h+var_74], 1
0x1800b7782  jmp     short loc_1800B7788
0x1800b7784  mov     [rsp+0E8h+var_74], edx
0x1800b7788  mov     r12, [rsp+0E8h+arg_20]
0x1800b7790  cmp     [rsp+0E8h+var_74], 0
0x1800b7795  jnz     short loc_1800B77A1
0x1800b7797  mov     rdx, [r12+98h]
0x1800b779f  jmp     short loc_1800B77C8
0x1800b77a1  movzx   edi, byte ptr [rbx+3]
0x1800b77a5  mov     edx, edi
0x1800b77a7  and     edx, 0Fh
0x1800b77aa  mov     rcx, r12
0x1800b77ad  call    ??$RtlpAmd64GetContextGp@PEAU_CONTEXT@@@@YA_KPEAU_CONTEXT@@KPEBU_AMD64_UNWIND_PARAMS@@@Z; RtlpAmd64GetContextGp<_CONTEXT *>(_CONTEXT *,ulong,_AMD64_UNWIND_PARAMS const *)
0x1800b77b2  mov     rdx, rax
0x1800b77b5  mov     eax, 0FFFFFFF0h
0x1800b77ba  and     rdi, rax
0x1800b77bd  sub     rdx, rdi
0x1800b77c0  mov     rax, [rsp+0E8h+arg_18]
0x1800b77c8  mov     rcx, [rsp+0E8h+arg_38]
0x1800b77d0  mov     [rcx], rdx
0x1800b77d3  test    r13d, r13d
0x1800b77d6  jnz     loc_1800B7E3B
0x1800b77dc  cmp     r15d, 2
0x1800b77e0  jnb     loc_1800B7D2C
0x1800b77e6  mov     rdx, r14
0x1800b77e9  movzx   r8d, byte ptr [r14]
0x1800b77ed  xor     r15d, r15d
0x1800b77f0  cmp     r8b, 48h ; 'H'
0x1800b77f4  jnz     short loc_1800B7842
0x1800b77f6  cmp     byte ptr [r14+1], 83h
0x1800b77fb  jnz     short loc_1800B7828
0x1800b77fd  cmp     byte ptr [r14+2], 0C4h
0x1800b7802  jnz     short loc_1800B7828
0x1800b7804  lea     rdx, [r14+4]
0x1800b7808  mov     r8b, [rdx]
0x1800b780b  mov     r13d, 1
0x1800b7811  mov     cl, r8b
0x1800b7814  and     cl, 0F8h
0x1800b7817  cmp     cl, 58h ; 'X'
0x1800b781a  jnz     loc_1800B78A0
0x1800b7820  add     rdx, r13
0x1800b7823  jmp     loc_1800B78BA
0x1800b7828  cmp     r8b, 48h ; 'H'
0x1800b782c  jnz     short loc_1800B7842
0x1800b782e  cmp     byte ptr [r14+1], 81h
0x1800b7833  jnz     short loc_1800B7842
0x1800b7835  cmp     byte ptr [r14+2], 0C4h
0x1800b783a  jnz     short loc_1800B7842
0x1800b783c  lea     rdx, [r14+7]
0x1800b7840  jmp     short loc_1800B7808
0x1800b7842  mov     cl, r8b
0x1800b7845  and     cl, 0FEh
0x1800b7848  cmp     cl, 48h ; 'H'
0x1800b784b  jnz     short loc_1800B780B
0x1800b784d  mov     r13d, 1
0x1800b7853  cmp     byte ptr [r14+1], 8Dh
0x1800b7858  jnz     short loc_1800B7811
0x1800b785a  movzx   r9d, byte ptr [r14+2]
0x1800b785f  mov     r15d, r8d
0x1800b7862  and     r15d, r13d
0x1800b7865  shl     r15d, 3
0x1800b7869  mov     ecx, r9d
0x1800b786c  and     ecx, 7
0x1800b786f  or      r15d, ecx
0x1800b7872  jz      short loc_1800B7811
0x1800b7874  movzx   ecx, byte ptr [rbx+3]
0x1800b7878  and     ecx, 0Fh
0x1800b787b  cmp     r15d, ecx
0x1800b787e  jnz     short loc_1800B7811
0x1800b7880  and     r9b, 0F8h
0x1800b7884  cmp     r9b, 60h ; '`'
0x1800b7888  jnz     short loc_1800B7890
0x1800b788a  lea     rdx, [r14+4]
0x1800b788e  jmp     short loc_1800B78BA
0x1800b7890  cmp     r9b, 0A0h
0x1800b7894  jnz     loc_1800B7811
0x1800b789a  lea     rdx, [r14+7]
0x1800b789e  jmp     short loc_1800B78BA
0x1800b78a0  mov     cl, r8b
0x1800b78a3  and     cl, 0F0h
0x1800b78a6  cmp     cl, 40h ; '@'
0x1800b78a9  jnz     short loc_1800B78C2
0x1800b78ab  mov     cl, [rdx+1]
0x1800b78ae  and     cl, 0F8h
0x1800b78b1  cmp     cl, 58h ; 'X'
0x1800b78b4  jnz     short loc_1800B78C2
0x1800b78b6  add     rdx, 2
0x1800b78ba  mov     r8b, [rdx]
0x1800b78bd  jmp     loc_1800B7811
0x1800b78c2  cmp     r8b, 0F2h
0x1800b78c6  jnz     short loc_1800B78CE
0x1800b78c8  add     rdx, r13
0x1800b78cb  mov     r8b, [rdx]
0x1800b78ce  lea     ecx, [r8+3Eh]
0x1800b78d2  cmp     cl, r13b
0x1800b78d5  jbe     short loc_1800B7931
0x1800b78d7  cmp     r8b, 0F3h
0x1800b78db  jnz     short loc_1800B78E3
0x1800b78dd  cmp     byte ptr [rdx+1], 0C3h
0x1800b78e1  jz      short loc_1800B7931
0x1800b78e3  lea     ecx, [r8+17h]
0x1800b78e7  test    cl, 0FDh
0x1800b78ea  jz      short loc_1800B7943
0x1800b78ec  cmp     r8b, 0FFh
0x1800b78f0  jnz     short loc_1800B790A
0x1800b78f2  cmp     byte ptr [rdx+1], 25h ; '%'
0x1800b78f6  jnz     short loc_1800B790A
0x1800b78f8  mov     [rsp+0E8h+arg_58], r13d
0x1800b7900  mov     [rsp+0E8h+var_78], r13d
0x1800b7905  jmp     loc_1800B79C2
0x1800b790a  and     r8b, 0F8h
0x1800b790e  cmp     r8b, 48h ; 'H'
0x1800b7912  jnz     loc_1800B79B3
0x1800b7918  cmp     byte ptr [rdx+1], 0FFh
0x1800b791c  jnz     loc_1800B79B3
0x1800b7922  mov     cl, [rdx+2]
0x1800b7925  and     cl, 38h
0x1800b7928  cmp     cl, 20h ; ' '
0x1800b792b  jnz     loc_1800B79B3
0x1800b7931  mov     edi, r13d
0x1800b7934  mov     [rsp+0E8h+arg_58], r13d
0x1800b793c  mov     [rsp+0E8h+var_78], r13d
0x1800b7941  jmp     short loc_1800B79BA
0x1800b7943  mov     r9, rdx
0x1800b7946  mov     r10, [rsp+0E8h+arg_8]
0x1800b794e  sub     r9, r10
0x1800b7951  cmp     r8b, 0EBh
0x1800b7955  jnz     short loc_1800B7960
0x1800b7957  movsx   ecx, byte ptr [rdx+1]
0x1800b795b  add     ecx, 2
0x1800b795e  jmp     short loc_1800B7966
0x1800b7960  mov     ecx, [rdx+1]
0x1800b7963  add     ecx, 5
0x1800b7966  movsxd  rdi, ecx
0x1800b7969  add     rdi, r9
0x1800b796c  mov     edx, [rax]
0x1800b796e  cmp     rdi, rdx
0x1800b7971  jb      short loc_1800B7985
0x1800b7973  mov     ecx, [rax+4]
0x1800b7976  cmp     rdi, rcx
0x1800b7979  jnb     short loc_1800B7985
0x1800b797b  cmp     rdi, rdx
0x1800b797e  jnz     short loc_1800B79B3
0x1800b7980  test    byte ptr [rbx], 20h
0x1800b7983  jmp     short loc_1800B792B
0x1800b7985  lea     r9, [rdi+r10]
0x1800b7989  mov     r8, r10
0x1800b798c  mov     rdx, rax
0x1800b798f  lea     rcx, [rsp+0E8h+var_40]
0x1800b7997  call    ??$RtlpxSameFunction@VCDirectFnEnt@@VCDirectUnwindInfo@@@@YA?AVCDirectFnEnt@@V0@_K1PEBU_AMD64_UNWIND_PARAMS@@@Z; RtlpxSameFunction<CDirectFnEnt,CDirectUnwindInfo>(CDirectFnEnt,unsigned __int64,unsigned __int64,_AMD64_UNWIND_PARAMS const *)
0x1800b799c  mov     rcx, [rax]
0x1800b799f  test    rcx, rcx
0x1800b79a2  jz      short loc_1800B7A0D
0x1800b79a4  mov     eax, [rcx]
0x1800b79a6  cmp     rdi, rax
0x1800b79a9  jz      short loc_1800B7A0D
0x1800b79ab  mov     rax, [rsp+0E8h+arg_18]
0x1800b79b3  mov     edi, [rsp+0E8h+arg_58]
  ... truncated ...
```
