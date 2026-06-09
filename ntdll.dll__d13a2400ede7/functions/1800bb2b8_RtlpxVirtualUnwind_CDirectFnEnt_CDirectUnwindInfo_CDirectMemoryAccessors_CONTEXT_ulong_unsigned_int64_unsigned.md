# RtlpxVirtualUnwind<CDirectFnEnt,CDirectUnwindInfo,CDirectMemoryAccessors,_CONTEXT *>(ulong,unsigned __int64,unsigned __int64,CDirectFnEnt,_CONTEXT *,uchar *,void * *,unsigned __int64 *,_EXCEPTION_DISPOSITION (**)(_EXCEPTION_RECORD *,void *,_CONTEXT *,void *),_AMD64_UNWIND_PARAMS *,ulong,ulong *)

- ea: `0x1800bb2b8`
- end: `0x1800bbcf6`
- name: `??$RtlpxVirtualUnwind@VCDirectFnEnt@@VCDirectUnwindInfo@@VCDirectMemoryAccessors@@PEAU_CONTEXT@@@@YAJK_K0VCDirectFnEnt@@PEAU_CONTEXT@@PEAEPEAPEAXPEA_KPEAP6A?AW4_EXCEPTION_DISPOSITION@@PEAU_EXCEPTION_RECORD@@PEAX27@ZPEAU_AMD64_UNWIND_PARAMS@@KPEAK@Z`
- size: `2622`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x1800ba744`
- `0x1800ba840`
- `0x180115ac0`
- `0x180116430`

## callees

- `0x1800bb2b8`
- `0x1800c3b64`
- `0x1800e25d8`
- `0x1800fca1c`
- `0x180103e58`
- `0x180117914`
- `0x18014a124`
- `0x18014a194`
- `0x18014a2d4`
- `0x18014c428`

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
0x1800bb2b8  mov     rax, rsp
0x1800bb2bb  mov     [rax+20h], r9
0x1800bb2bf  mov     [rax+18h], r8
0x1800bb2c3  mov     [rax+10h], rdx
0x1800bb2c7  mov     [rax+8], ecx
0x1800bb2ca  push    rbx
0x1800bb2cb  push    rdi
0x1800bb2cc  push    r12
0x1800bb2ce  push    r13
0x1800bb2d0  push    r14
0x1800bb2d2  push    r15
0x1800bb2d4  sub     rsp, 0B8h
0x1800bb2db  mov     rax, r9
0x1800bb2de  mov     r14, r8
0x1800bb2e1  mov     r10, rdx
0x1800bb2e4  mov     r11d, ecx
0x1800bb2e7  test    r9, r9
0x1800bb2ea  jnz     loc_1800BB3D9
0x1800bb2f0  mov     r8, [rsp+0E8h+arg_20]
0x1800bb2f8  lea     rdx, [r8+98h]
0x1800bb2ff  mov     [rsp+0E8h+var_68], rdx
0x1800bb307  mov     rbx, [rdx]
0x1800bb30a  mov     [rsp+0E8h+var_60], rbx
0x1800bb312  mov     rcx, [rsp+0E8h+arg_48]
0x1800bb31a  mov     rax, [rcx]
0x1800bb31d  test    rax, rax
0x1800bb320  jz      short loc_1800BB341
0x1800bb322  cmp     rbx, [rax]
0x1800bb325  jb      short loc_1800BB337
0x1800bb327  mov     rax, [rcx+8]
0x1800bb32b  mov     rcx, [rax]
0x1800bb32e  sub     rcx, 8
0x1800bb332  cmp     rbx, rcx
0x1800bb335  jbe     short loc_1800BB341
0x1800bb337  mov     eax, 0C0000028h
0x1800bb33c  jmp     loc_1800BBCE3
0x1800bb341  xor     eax, eax
0x1800bb343  jmp     short loc_1800BB365
0x1800bb345  mov     r8, [rsp+0E8h+arg_20]
0x1800bb34d  mov     r14, [rsp+0E8h+arg_10]
0x1800bb355  mov     rdx, [rsp+0E8h+var_68]
0x1800bb35d  mov     rbx, [rsp+0E8h+var_60]
0x1800bb365  test    eax, eax
0x1800bb367  js      loc_1800BBCE3
0x1800bb36d  mov     rax, [rbx]
0x1800bb370  cmp     r14, rax
0x1800bb373  jnz     short loc_1800BB37F
0x1800bb375  mov     eax, 0C00000FFh
0x1800bb37a  jmp     loc_1800BBCE3
0x1800bb37f  mov     [r8+0F8h], rax
0x1800bb386  add     qword ptr [rdx], 8
0x1800bb38a  mov     rcx, r8
0x1800bb38d  call    ??$RtlpVirtualPopShadowStack@PEAU_CONTEXT@@@@YAXPEAU_CONTEXT@@KK@Z; RtlpVirtualPopShadowStack<_CONTEXT *>(_CONTEXT *,ulong,ulong)
0x1800bb392  mov     rax, [rsp+0E8h+arg_38]
0x1800bb39a  mov     [rax], rbx
0x1800bb39d  mov     rax, [rsp+0E8h+arg_28]
0x1800bb3a5  test    rax, rax
0x1800bb3a8  jz      short loc_1800BB3AD
0x1800bb3aa  mov     byte ptr [rax], 0
0x1800bb3ad  mov     rax, [rsp+0E8h+arg_30]
0x1800bb3b5  mov     qword ptr [rax], 0
0x1800bb3bc  mov     rax, [rsp+0E8h+arg_40]
0x1800bb3c4  test    rax, rax
0x1800bb3c7  jz      loc_1800BBCE1
0x1800bb3cd  mov     qword ptr [rax], 0
0x1800bb3d4  jmp     loc_1800BBCE1
0x1800bb3d9  mov     ebx, [r9+8]
0x1800bb3dd  add     rbx, rdx
0x1800bb3e0  movzx   r15d, byte ptr [rbx]
0x1800bb3e4  and     r15d, 7
0x1800bb3e8  cmp     r15d, 3
0x1800bb3ec  jb      short loc_1800BB44E
0x1800bb3ee  mov     rcx, [rsp+0E8h+arg_48]
0x1800bb3f6  mov     [rsp+0E8h+var_98], rcx
0x1800bb3fb  mov     rcx, [rsp+0E8h+arg_40]
0x1800bb403  mov     [rsp+0E8h+var_A0], rcx
0x1800bb408  mov     rcx, [rsp+0E8h+arg_38]
0x1800bb410  mov     [rsp+0E8h+var_A8], rcx
0x1800bb415  mov     rcx, [rsp+0E8h+arg_30]
0x1800bb41d  mov     [rsp+0E8h+var_B0], rcx
0x1800bb422  mov     rcx, [rsp+0E8h+arg_28]
0x1800bb42a  mov     [rsp+0E8h+var_B8], rcx
0x1800bb42f  mov     rcx, [rsp+0E8h+arg_20]
0x1800bb437  mov     [rsp+0E8h+var_C0], rcx
0x1800bb43c  mov     [rsp+0E8h+var_C8], rbx
0x1800bb441  mov     ecx, r11d
0x1800bb444  call    ??$RtlpxVirtualUnwindV3@VCDirectFnEnt@@VCDirectUnwindInfo@@VCDirectMemoryAccessors@@PEAU_CONTEXT@@@@YAJK_K0VCDirectFnEnt@@VCDirectUnwindInfo@@PEAU_CONTEXT@@PEAEPEAPEAXPEA_KPEAP6A?AW4_EXCEPTION_DISPOSITION@@PEAU_EXCEPTION_RECORD@@PEAX38@ZPEAU_AMD64_UNWIND_PARAMS@@KPEAK@Z; RtlpxVirtualUnwindV3<CDirectFnEnt,CDirectUnwindInfo,CDirectMemoryAccessors,_CONTEXT *>(ulong,unsigned __int64,unsigned __int64,CDirectFnEnt,CDirectUnwindInfo,_CONTEXT *,uchar *,void * *,unsigned __int64 *,_EXCEPTION_DISPOSITION (**)(_EXCEPTION_RECORD *,void *,_CONTEXT *,void *),_AMD64_UNWIND_PARAMS *,ulong,ulong *)
0x1800bb449  jmp     loc_1800BBCE3
0x1800bb44e  mov     [rsp+0E8h+var_48], 0
0x1800bb45a  xor     ecx, ecx
0x1800bb45c  mov     [rsp+0E8h+arg_58], ecx
0x1800bb463  mov     [rsp+0E8h+var_78], ecx
0x1800bb467  mov     rcx, [rsp+0E8h+arg_28]
0x1800bb46f  test    rcx, rcx
0x1800bb472  jz      short loc_1800BB483
0x1800bb474  cmp     byte ptr [rcx], 0
0x1800bb477  jnz     short loc_1800BB483
0x1800bb479  mov     edx, 1
0x1800bb47e  mov     r13d, edx
0x1800bb481  jmp     short loc_1800BB4B8
0x1800bb483  xor     r13d, r13d
0x1800bb486  cmp     r15d, 2
0x1800bb48a  jnb     short loc_1800BB4B3
0x1800bb48c  mov     r8, rbx
0x1800bb48f  mov     rcx, rax
0x1800bb492  call    ??$RtlpxTrivialFunction@VCDirectFnEnt@@VCDirectUnwindInfo@@@@YAKVCDirectFnEnt@@_KVCDirectUnwindInfo@@PEBU_AMD64_UNWIND_PARAMS@@@Z; RtlpxTrivialFunction<CDirectFnEnt,CDirectUnwindInfo>(CDirectFnEnt,unsigned __int64,CDirectUnwindInfo,_AMD64_UNWIND_PARAMS const *)
0x1800bb497  lea     edx, [r13+1]
0x1800bb49b  test    eax, eax
0x1800bb49d  cmovnz  r13d, edx
0x1800bb4a1  mov     rax, [rsp+0E8h+arg_18]
0x1800bb4a9  mov     r10, [rsp+0E8h+arg_8]
0x1800bb4b1  jmp     short loc_1800BB4B8
0x1800bb4b3  mov     edx, 1
0x1800bb4b8  mov     [rsp+0E8h+var_74], 0
0x1800bb4c0  test    byte ptr [rbx+3], 0Fh
0x1800bb4c4  jz      short loc_1800BB528
0x1800bb4c6  mov     edi, r14d
0x1800bb4c9  sub     edi, r10d
0x1800bb4cc  sub     edi, [rax]
0x1800bb4ce  movzx   ecx, byte ptr [rbx+1]
0x1800bb4d2  cmp     edi, ecx
0x1800bb4d4  jnb     short loc_1800BB524
0x1800bb4d6  test    byte ptr [rbx], 20h
0x1800bb4d9  jnz     short loc_1800BB524
0x1800bb4db  xor     r12d, r12d
0x1800bb4de  cmp     [rbx+2], r12b
0x1800bb4e2  jbe     short loc_1800BB510
0x1800bb4e4  movzx   ecx, word ptr [rbx+r12*2+4]
0x1800bb4ea  movzx   eax, cx
0x1800bb4ed  shr     ax, 8
0x1800bb4f1  and     al, 0Fh
0x1800bb4f3  cmp     al, 3
0x1800bb4f5  jz      short loc_1800BB508
0x1800bb4f7  call    RtlpUnwindOpSlots
0x1800bb4fc  add     r12d, eax
0x1800bb4ff  movzx   eax, byte ptr [rbx+2]
0x1800bb503  cmp     r12d, eax
0x1800bb506  jb      short loc_1800BB4E4
0x1800bb508  mov     rax, [rsp+0E8h+arg_18]
0x1800bb510  movzx   edx, byte ptr [rbx+r12*2+4]
0x1800bb516  cmp     edi, edx
0x1800bb518  jb      short loc_1800BB528
0x1800bb51a  mov     [rsp+0E8h+var_74], 1
0x1800bb522  jmp     short loc_1800BB528
0x1800bb524  mov     [rsp+0E8h+var_74], edx
0x1800bb528  mov     r12, [rsp+0E8h+arg_20]
0x1800bb530  cmp     [rsp+0E8h+var_74], 0
0x1800bb535  jnz     short loc_1800BB541
0x1800bb537  mov     rdx, [r12+98h]
0x1800bb53f  jmp     short loc_1800BB568
0x1800bb541  movzx   edi, byte ptr [rbx+3]
0x1800bb545  mov     edx, edi
0x1800bb547  and     edx, 0Fh
0x1800bb54a  mov     rcx, r12
0x1800bb54d  call    ??$RtlpAmd64GetContextGp@PEAU_CONTEXT@@@@YA_KPEAU_CONTEXT@@KPEBU_AMD64_UNWIND_PARAMS@@@Z; RtlpAmd64GetContextGp<_CONTEXT *>(_CONTEXT *,ulong,_AMD64_UNWIND_PARAMS const *)
0x1800bb552  mov     rdx, rax
0x1800bb555  mov     eax, 0FFFFFFF0h
0x1800bb55a  and     rdi, rax
0x1800bb55d  sub     rdx, rdi
0x1800bb560  mov     rax, [rsp+0E8h+arg_18]
0x1800bb568  mov     rcx, [rsp+0E8h+arg_38]
0x1800bb570  mov     [rcx], rdx
0x1800bb573  test    r13d, r13d
0x1800bb576  jnz     loc_1800BBBDB
0x1800bb57c  cmp     r15d, 2
0x1800bb580  jnb     loc_1800BBACC
0x1800bb586  mov     rdx, r14
0x1800bb589  movzx   r8d, byte ptr [r14]
0x1800bb58d  xor     r15d, r15d
0x1800bb590  cmp     r8b, 48h ; 'H'
0x1800bb594  jnz     short loc_1800BB5E2
0x1800bb596  cmp     byte ptr [r14+1], 83h
0x1800bb59b  jnz     short loc_1800BB5C8
0x1800bb59d  cmp     byte ptr [r14+2], 0C4h
0x1800bb5a2  jnz     short loc_1800BB5C8
0x1800bb5a4  lea     rdx, [r14+4]
0x1800bb5a8  mov     r8b, [rdx]
0x1800bb5ab  mov     r13d, 1
0x1800bb5b1  mov     cl, r8b
0x1800bb5b4  and     cl, 0F8h
0x1800bb5b7  cmp     cl, 58h ; 'X'
0x1800bb5ba  jnz     loc_1800BB640
0x1800bb5c0  add     rdx, r13
0x1800bb5c3  jmp     loc_1800BB65A
0x1800bb5c8  cmp     r8b, 48h ; 'H'
0x1800bb5cc  jnz     short loc_1800BB5E2
0x1800bb5ce  cmp     byte ptr [r14+1], 81h
0x1800bb5d3  jnz     short loc_1800BB5E2
0x1800bb5d5  cmp     byte ptr [r14+2], 0C4h
0x1800bb5da  jnz     short loc_1800BB5E2
0x1800bb5dc  lea     rdx, [r14+7]
0x1800bb5e0  jmp     short loc_1800BB5A8
0x1800bb5e2  mov     cl, r8b
0x1800bb5e5  and     cl, 0FEh
0x1800bb5e8  cmp     cl, 48h ; 'H'
0x1800bb5eb  jnz     short loc_1800BB5AB
0x1800bb5ed  mov     r13d, 1
0x1800bb5f3  cmp     byte ptr [r14+1], 8Dh
0x1800bb5f8  jnz     short loc_1800BB5B1
0x1800bb5fa  movzx   r9d, byte ptr [r14+2]
0x1800bb5ff  mov     r15d, r8d
0x1800bb602  and     r15d, r13d
0x1800bb605  shl     r15d, 3
0x1800bb609  mov     ecx, r9d
0x1800bb60c  and     ecx, 7
0x1800bb60f  or      r15d, ecx
0x1800bb612  jz      short loc_1800BB5B1
0x1800bb614  movzx   ecx, byte ptr [rbx+3]
0x1800bb618  and     ecx, 0Fh
0x1800bb61b  cmp     r15d, ecx
0x1800bb61e  jnz     short loc_1800BB5B1
0x1800bb620  and     r9b, 0F8h
0x1800bb624  cmp     r9b, 60h ; '`'
0x1800bb628  jnz     short loc_1800BB630
0x1800bb62a  lea     rdx, [r14+4]
0x1800bb62e  jmp     short loc_1800BB65A
0x1800bb630  cmp     r9b, 0A0h
0x1800bb634  jnz     loc_1800BB5B1
0x1800bb63a  lea     rdx, [r14+7]
0x1800bb63e  jmp     short loc_1800BB65A
0x1800bb640  mov     cl, r8b
0x1800bb643  and     cl, 0F0h
0x1800bb646  cmp     cl, 40h ; '@'
0x1800bb649  jnz     short loc_1800BB662
0x1800bb64b  mov     cl, [rdx+1]
0x1800bb64e  and     cl, 0F8h
0x1800bb651  cmp     cl, 58h ; 'X'
0x1800bb654  jnz     short loc_1800BB662
0x1800bb656  add     rdx, 2
0x1800bb65a  mov     r8b, [rdx]
0x1800bb65d  jmp     loc_1800BB5B1
0x1800bb662  cmp     r8b, 0F2h
0x1800bb666  jnz     short loc_1800BB66E
0x1800bb668  add     rdx, r13
0x1800bb66b  mov     r8b, [rdx]
0x1800bb66e  lea     ecx, [r8+3Eh]
0x1800bb672  cmp     cl, r13b
0x1800bb675  jbe     short loc_1800BB6D1
0x1800bb677  cmp     r8b, 0F3h
0x1800bb67b  jnz     short loc_1800BB683
0x1800bb67d  cmp     byte ptr [rdx+1], 0C3h
0x1800bb681  jz      short loc_1800BB6D1
0x1800bb683  lea     ecx, [r8+17h]
0x1800bb687  test    cl, 0FDh
0x1800bb68a  jz      short loc_1800BB6E3
0x1800bb68c  cmp     r8b, 0FFh
0x1800bb690  jnz     short loc_1800BB6AA
0x1800bb692  cmp     byte ptr [rdx+1], 25h ; '%'
0x1800bb696  jnz     short loc_1800BB6AA
0x1800bb698  mov     [rsp+0E8h+arg_58], r13d
0x1800bb6a0  mov     [rsp+0E8h+var_78], r13d
0x1800bb6a5  jmp     loc_1800BB762
0x1800bb6aa  and     r8b, 0F8h
0x1800bb6ae  cmp     r8b, 48h ; 'H'
0x1800bb6b2  jnz     loc_1800BB753
0x1800bb6b8  cmp     byte ptr [rdx+1], 0FFh
0x1800bb6bc  jnz     loc_1800BB753
0x1800bb6c2  mov     cl, [rdx+2]
0x1800bb6c5  and     cl, 38h
0x1800bb6c8  cmp     cl, 20h ; ' '
0x1800bb6cb  jnz     loc_1800BB753
0x1800bb6d1  mov     edi, r13d
0x1800bb6d4  mov     [rsp+0E8h+arg_58], r13d
0x1800bb6dc  mov     [rsp+0E8h+var_78], r13d
0x1800bb6e1  jmp     short loc_1800BB75A
0x1800bb6e3  mov     r9, rdx
0x1800bb6e6  mov     r10, [rsp+0E8h+arg_8]
0x1800bb6ee  sub     r9, r10
0x1800bb6f1  cmp     r8b, 0EBh
0x1800bb6f5  jnz     short loc_1800BB700
0x1800bb6f7  movsx   ecx, byte ptr [rdx+1]
0x1800bb6fb  add     ecx, 2
0x1800bb6fe  jmp     short loc_1800BB706
0x1800bb700  mov     ecx, [rdx+1]
0x1800bb703  add     ecx, 5
0x1800bb706  movsxd  rdi, ecx
0x1800bb709  add     rdi, r9
0x1800bb70c  mov     edx, [rax]
0x1800bb70e  cmp     rdi, rdx
0x1800bb711  jb      short loc_1800BB725
0x1800bb713  mov     ecx, [rax+4]
0x1800bb716  cmp     rdi, rcx
0x1800bb719  jnb     short loc_1800BB725
0x1800bb71b  cmp     rdi, rdx
0x1800bb71e  jnz     short loc_1800BB753
0x1800bb720  test    byte ptr [rbx], 20h
0x1800bb723  jmp     short loc_1800BB6CB
0x1800bb725  lea     r9, [rdi+r10]
0x1800bb729  mov     r8, r10
0x1800bb72c  mov     rdx, rax
0x1800bb72f  lea     rcx, [rsp+0E8h+var_40]
0x1800bb737  call    ??$RtlpxSameFunction@VCDirectFnEnt@@VCDirectUnwindInfo@@@@YA?AVCDirectFnEnt@@V0@_K1PEBU_AMD64_UNWIND_PARAMS@@@Z; RtlpxSameFunction<CDirectFnEnt,CDirectUnwindInfo>(CDirectFnEnt,unsigned __int64,unsigned __int64,_AMD64_UNWIND_PARAMS const *)
0x1800bb73c  mov     rcx, [rax]
0x1800bb73f  test    rcx, rcx
0x1800bb742  jz      short loc_1800BB7AD
0x1800bb744  mov     eax, [rcx]
0x1800bb746  cmp     rdi, rax
0x1800bb749  jz      short loc_1800BB7AD
0x1800bb74b  mov     rax, [rsp+0E8h+arg_18]
0x1800bb753  mov     edi, [rsp+0E8h+arg_58]
  ... truncated ...
```
