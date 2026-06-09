# CRPCSQLSender::SendCommand(bool)

- ea: `0x1004cb4e0`
- end: `0x1004cbff1`
- name: `?SendCommand@CRPCSQLSender@@UEAAJ_N@Z`
- size: `2833`
- prototype: `__int64 __fastcall(CRPCSQLSender *__hidden this, bool)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x10045b624`
- `0x10045be64`
- `0x100463e78`
- `0x100480138`
- `0x1004be91c`
- `0x1004cb4e0`
- `0x1004cbff8`
- `0x100546a24`
- `0x100548210`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x1004cb6ec`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x1004cb91a`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x1004cbb57`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x1004cbd22`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x1004cbeaa`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x1004cb6ec`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x1004cb91a`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x1004cbb57`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x1004cbd22`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x1004cbeaa`

## pseudocode

```c
__int64 __fastcall CRPCSQLSender::SendCommand(CRPCSQLSender *this, char a2)
{
  char *v2; // rbx
  char v3; // r14
  CRPCSQLSender *v4; // r12
  int v5; // eax
  __int64 v6; // r9
  __int64 v7; // r11
  int v8; // edi
  __int64 v9; // rdx
  __int64 v10; // r8
  unsigned __int16 v11; // r9
  unsigned __int8 *v12; // r10
  unsigned int v13; // esi
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  bool v17; // zf
  __int64 v18; // r8
  __int64 v19; // rdx
  __int64 v20; // rcx
  unsigned int *v21; // rsi
  __int64 v22; // rcx
  unsigned __int64 v23; // r14
  _QWORD *v24; // r8
  __int64 v25; // r9
  __int64 v26; // rcx
  char v27; // dl
  int v28; // ecx
  __int64 v29; // rdx
  int v30; // eax
  unsigned __int64 v31; // rax
  sqlencrypt::SHA256 *v32; // rcx
  __int64 v33; // rcx
  unsigned __int8 *v34; // rax
  __int16 v35; // cx
  _WORD *v36; // rax
  __int16 v37; // cx
  unsigned int v38; // eax
  sqlencrypt::SHA256 *v39; // rcx
  __int64 v40; // rax
  unsigned __int64 v41; // r14
  __int64 v42; // r8
  char *v43; // r14
  rsize_t v44; // r10
  unsigned __int64 v45; // rdx
  int v46; // eax
  char v47; // cl
  unsigned __int64 v48; // rcx
  rsize_t v49; // rax
  __int64 v50; // rax
  __int64 v51; // rdx
  unsigned __int8 *v52; // rcx
  __int16 v53; // ax
  __int64 v54; // rdx
  unsigned __int64 v55; // rdx
  int v56; // eax
  char v57; // cl
  unsigned __int64 v58; // rcx
  int v59; // eax
  bool v60; // cc
  __int64 v61; // r14
  int v62; // eax
  __int64 v63; // rax
  int v64; // eax
  unsigned __int64 v65; // r14
  int *v66; // rsi
  _QWORD *v67; // r8
  __int64 v68; // rdx
  __int64 v69; // rcx
  char v70; // r9
  int v71; // ecx
  __int64 v72; // r9
  sqlencrypt::SHA256 *v73; // rcx
  const unsigned __int8 *v74; // rdx
  int v75; // eax
  sqlencrypt::SHA256 *v76; // rcx
  __int64 v77; // r15
  __int64 v78; // rax
  unsigned __int64 v79; // r14
  char *v80; // r15
  _QWORD *v81; // r8
  __int64 v82; // rdx
  __int64 v83; // rcx
  char v84; // r9
  int v85; // ecx
  __int64 v86; // r9
  sqlencrypt::SHA256 *v87; // rcx
  __int64 v88; // r12
  __int64 v89; // rax
  unsigned __int64 v90; // r14
  _QWORD *v91; // rdx
  CRPCRequest *v92; // rcx
  int v94; // [rsp+48h] [rbp-49h]
  unsigned __int8 *v96; // [rsp+50h] [rbp-41h]
  unsigned int v97; // [rsp+58h] [rbp-39h]
  unsigned int v98; // [rsp+5Ch] [rbp-35h]
  const unsigned __int8 *Source; // [rsp+60h] [rbp-31h]
  unsigned __int64 v101; // [rsp+70h] [rbp-21h]
  rsize_t v102; // [rsp+70h] [rbp-21h]
  __int64 v103; // [rsp+78h] [rbp-19h]
  int *v104; // [rsp+80h] [rbp-11h]
  unsigned int v105; // [rsp+88h] [rbp-9h]
  int v106[2]; // [rsp+90h] [rbp-1h]
  __int64 v107; // [rsp+98h] [rbp+7h]
  __int64 v108; // [rsp+A0h] [rbp+Fh]
  int v109; // [rsp+B8h] [rbp+27h] BYREF
  int v110; // [rsp+BCh] [rbp+2Bh] BYREF

  v2 = (char *)this + 96;
  v3 = a2;
  v4 = this;
  v5 = CRPCSQLStream::OnBeginSendCommand(
         (CRPCSQLSender *)((char *)this + 96),
         (CRPCSQLSender *)((char *)this + 40),
         *(_DWORD *)(*((_QWORD *)this + 1) + 796LL),
         *((_QWORD *)this + 4));
  v7 = 0;
  v8 = v5;
  if ( v5 < 0 )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_147;
    v9 = 8026121;
    goto LABEL_145;
  }
  _mm_lfence();
  if ( !*(_DWORD *)(*((_QWORD *)v4 + 1) + 796LL) )
  {
    if ( !*((_QWORD *)v4 + 4) )
      goto LABEL_142;
    _mm_lfence();
    v66 = (int *)(v2 + 40);
    v80 = (char *)*((_QWORD *)v4 + 3);
    v65 = 2LL * *((_QWORD *)v4 + 4);
    if ( !v2[32] )
    {
      v81 = (_QWORD *)*((_QWORD *)v2 + 1);
      v82 = *((unsigned int *)v2 + 4);
      v83 = v81[1];
      if ( (unsigned __int64)(v82 - v83) <= 4 )
      {
        v84 = 1;
        v85 = 1;
      }
      else
      {
        *((_QWORD *)v2 + 6) = v83;
        v84 = 0;
        v85 = v82 - v83 - 4;
      }
      *((_DWORD *)v2 + 9) = v85;
      *v66 = v85;
      v2[33] = v84;
      v86 = v81[1];
      if ( (unsigned __int64)(v82 - v86) <= 4 )
      {
        if ( (int)BATCHCTX::QueuePacket(
                    *(BATCHCTX **)v2,
                    *(void **)(*(_QWORD *)v2 + 112LL),
                    4u,
                    (const unsigned __int8 *)v2 + 40,
                    3,
                    *((_DWORD *)v2 + 5),
                    0) < 0 )
        {
          v8 = -2147467259;
          goto LABEL_139;
        }
      }
      else
      {
        *(_DWORD *)(v86 + *v81) = v85;
        *(_QWORD *)(*((_QWORD *)v2 + 1) + 8LL) += 4LL;
      }
      v2[32] = 1;
    }
    if ( v65 < (unsigned int)*v66 )
    {
      memcpy_s((void *const)(**((_QWORD **)v2 + 1) + *(_QWORD *)(*((_QWORD *)v2 + 1) + 8LL)), v65, v80, v65);
      v73 = (sqlencrypt::SHA256 *)*((_QWORD *)v2 + 8);
      if ( !v73 )
        goto LABEL_110;
      v74 = (const unsigned __int8 *)v80;
      goto LABEL_109;
    }
    _mm_lfence();
    v87 = (sqlencrypt::SHA256 *)*((_QWORD *)v2 + 8);
    v88 = (unsigned int)*v66;
    if ( v87 )
      sqlencrypt::SHA256::hash(v87, (const unsigned __int8 *)v80, v88);
    v8 = BATCHCTX::QueuePacket(
           *(BATCHCTX **)v2,
           *(void **)(*(_QWORD *)v2 + 112LL),
           (unsigned int)*v66,
           (const unsigned __int8 *)v80,
           3,
           *((_DWORD *)v2 + 5),
           0);
    if ( v8 >= 0 )
    {
      v89 = (unsigned int)*v66;
      *v66 = 0;
      v2[32] = 0;
      v90 = v65 - v89;
      if ( !v90
        || (_mm_lfence(),
            v8 = CRPCSQLStream::SendCommandPart((CRPCSQLStream *)v2, (const unsigned __int16 *)&v80[v88], v90),
            v8 >= 0) )
      {
        v4 = this;
        goto LABEL_142;
      }
    }
    v4 = this;
LABEL_139:
    if ( (bidGblFlags & 2) != 0 )
    {
      v42 = (unsigned int)v8;
      v9 = 8160265;
      goto LABEL_146;
    }
    goto LABEL_147;
  }
  _mm_lfence();
  v10 = *((_QWORD *)v4 + 1);
  v11 = 0;
  v12 = (unsigned __int8 *)*((_QWORD *)v4 + 3);
  v13 = 1;
  *(_QWORD *)v106 = *((_QWORD *)v4 + 4);
  v14 = *(_QWORD *)(v10 + 464) + 8LL;
  v109 = 0x400000;
  v110 = 3145808;
  v108 = v10;
  v96 = v12;
  Source = (const unsigned __int8 *)&v109 + 2;
  v97 = 6;
  v98 = 1;
  v107 = v14;
  if ( !*(_DWORD *)(v10 + 796) )
  {
LABEL_98:
    v65 = 2LL
        * ((unsigned int)v11 + *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v14 + 24LL) * (v13 - 1) + *(_QWORD *)v14 + 32LL));
    if ( !v65 )
    {
LABEL_142:
      v5 = CRPCSQLStream::OnEndSendCommand((CRPCSQLStream *)v2);
      v8 = v5;
      if ( v5 >= 0 )
        return (unsigned int)v8;
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_147;
      v9 = 8165385;
LABEL_145:
      v42 = (unsigned int)v5;
      goto LABEL_146;
    }
    v66 = (int *)(v2 + 40);
    if ( v2[32] == (_BYTE)v7 )
    {
      v67 = (_QWORD *)*((_QWORD *)v2 + 1);
      v68 = *((unsigned int *)v2 + 4);
      v69 = v67[1];
      if ( (unsigned __int64)(v68 - v69) <= 4 )
      {
        v70 = 1;
        v71 = 1;
      }
      else
      {
        *((_QWORD *)v2 + 6) = v69;
        v70 = v7;
        v71 = v68 - v69 - 4;
      }
      *((_DWORD *)v2 + 9) = v71;
      *v66 = v71;
      v2[33] = v70;
      v72 = v67[1];
      if ( (unsigned __int64)(v68 - v72) <= 4 )
      {
        v75 = BATCHCTX::QueuePacket(
                *(BATCHCTX **)v2,
                *(void **)(*(_QWORD *)v2 + 112LL),
                4u,
                (const unsigned __int8 *)v2 + 40,
                3,
                *((_DWORD *)v2 + 5),
                v7);
        LODWORD(v7) = 0;
        if ( v75 < 0 )
        {
          v8 = -2147467259;
          goto LABEL_118;
        }
      }
      else
      {
        *(_DWORD *)(v72 + *v67) = v71;
        *(_QWORD *)(*((_QWORD *)v2 + 1) + 8LL) += 4LL;
      }
      v2[32] = 1;
    }
    if ( v65 < (unsigned int)*v66 )
    {
      memcpy_s((void *const)(**((_QWORD **)v2 + 1) + *(_QWORD *)(*((_QWORD *)v2 + 1) + 8LL)), v65, v96, v65);
      v73 = (sqlencrypt::SHA256 *)*((_QWORD *)v2 + 8);
      if ( !v73 )
      {
LABEL_110:
        *(_QWORD *)(*((_QWORD *)v2 + 1) + 8LL) += v65;
        *v66 -= v65;
        goto LABEL_142;
      }
      v74 = v96;
LABEL_109:
      sqlencrypt::SHA256::hash(v73, v74, v65);
      goto LABEL_110;
    }
    _mm_lfence();
    v76 = (sqlencrypt::SHA256 *)*((_QWORD *)v2 + 8);
    v77 = (unsigned int)*v66;
    if ( v76 )
    {
      sqlencrypt::SHA256::hash(v76, v96, v77);
      LODWORD(v7) = 0;
    }
    v8 = BATCHCTX::QueuePacket(
           *(BATCHCTX **)v2,
           *(void **)(*(_QWORD *)v2 + 112LL),
           (unsigned int)*v66,
           v96,
           3,
           *((_DWORD *)v2 + 5),
           v7);
    if ( v8 >= 0 )
    {
      v78 = (unsigned int)*v66;
      *v66 = 0;
      v2[32] = 0;
      v79 = v65 - v78;
      if ( !v79 )
        goto LABEL_142;
      _mm_lfence();
      v8 = CRPCSQLStream::SendCommandPart((CRPCSQLStream *)v2, (const unsigned __int16 *)&v96[v77], v79);
      if ( v8 >= 0 )
        goto LABEL_142;
    }
LABEL_118:
    if ( (bidGblFlags & 2) != 0 )
    {
      v42 = (unsigned int)v8;
      v9 = 8153097;
      goto LABEL_146;
    }
    goto LABEL_147;
  }
  while ( 1 )
  {
    if ( v3
      || (v15 = *(_QWORD *)(v10 + 456), (unsigned __int64)v13 > *(_QWORD *)(v15 + 8))
      || (v16 = *(_QWORD *)(v15 + 24) * (v13 - 1LL) + 32, v17 = v15 + v16 == 0, v18 = v15 + v16, v103 = v18, !v17)
      && (_WORD)v7 == *(_WORD *)(v18 + 16) )
    {
      v103 = v7;
    }
    v19 = *(_QWORD *)v14;
    v20 = v13 - 1;
    v21 = (unsigned int *)(v2 + 40);
    v22 = *(_QWORD *)(v19 + 24) * v20;
    v23 = 2LL * (*(_DWORD *)(v22 + v19 + 32) + (unsigned int)v11);
    v94 = *(_DWORD *)(v22 + v19 + 32) + v11;
    if ( v2[32] == (_BYTE)v7 )
    {
      v24 = (_QWORD *)*((_QWORD *)v2 + 1);
      v25 = *((unsigned int *)v2 + 4);
      v26 = v24[1];
      if ( (unsigned __int64)(v25 - v26) <= 4 )
      {
        v27 = 1;
        v28 = 1;
      }
      else
      {
        *((_QWORD *)v2 + 6) = v26;
        v27 = v7;
        v28 = v25 - v26 - 4;
      }
      *((_DWORD *)v2 + 9) = v28;
      *v21 = v28;
      v2[33] = v27;
      v29 = v24[1];
      if ( (unsigned __int64)(v25 - v29) <= 4 )
      {
        v30 = BATCHCTX::QueuePacket(
                *(BATCHCTX **)v2,
                *(void **)(*(_QWORD *)v2 + 112LL),
                4u,
                (const unsigned __int8 *)v2 + 40,
                3,
                *((_DWORD *)v2 + 5),
                v7);
        LODWORD(v7) = 0;
        if ( v30 < 0 )
        {
          v8 = -2147467259;
LABEL_35:
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_147;
          v42 = (unsigned int)v8;
          v9 = 8079369;
          goto LABEL_146;
        }
        v12 = v96;
      }
      else
      {
        *(_DWORD *)(v29 + *v24) = v28;
        *(_QWORD *)(*((_QWORD *)v2 + 1) + 8LL) += 4LL;
      }
      v2[32] = 1;
    }
    v31 = *v21;
    v101 = v31;
    if ( v23 < v31 )
    {
      memcpy_s((void *const)(**((_QWORD **)v4 + 13) + *(_QWORD *)(*((_QWORD *)v4 + 13) + 8LL)), v23, v12, v23);
      v32 = (sqlencrypt::SHA256 *)*((_QWORD *)v4 + 20);
      if ( v32 )
        sqlencrypt::SHA256::hash(v32, v96, v23);
      *(_QWORD *)(*((_QWORD *)v4 + 13) + 8LL) += v23;
      *((_DWORD *)v4 + 34) -= v23;
LABEL_24:
      v104 = (int *)(v2 + 40);
      goto LABEL_25;
    }
    v39 = (sqlencrypt::SHA256 *)*((_QWORD *)v4 + 20);
    if ( v39 )
    {
      sqlencrypt::SHA256::hash(v39, v12, v31);
      LODWORD(v7) = 0;
    }
    v8 = BATCHCTX::QueuePacket(
           *(BATCHCTX **)v2,
           *(void **)(*(_QWORD *)v2 + 112LL),
           *((unsigned int *)v4 + 34),
           v96,
           3,
           *((_DWORD *)v4 + 29),
           v7);
    if ( v8 < 0 )
      goto LABEL_35;
    v40 = *((unsigned int *)v4 + 34);
    *((_DWORD *)v4 + 34) = 0;
    *((_BYTE *)v4 + 128) = 0;
    v41 = v23 - v40;
    if ( !v41 )
      goto LABEL_24;
    _mm_lfence();
    v104 = (int *)(v2 + 40);
    v8 = CRPCSQLStream::SendCommandPart((CRPCSQLStream *)v2, (const unsigned __int16 *)&v96[v101], v41);
    if ( v8 < 0 )
      goto LABEL_35;
LABEL_25:
    v33 = (unsigned int)(v94 + 1);
    *(_QWORD *)v106 -= v33;
    v34 = &v96[2 * v33];
    v35 = HIWORD(v110);
    v96 = v34;
    v36 = (_WORD *)&v110 + 1;
    if ( HIWORD(v110) == 57 )
    {
      do
      {
        *v36-- = 48;
        v35 = *v36;
      }
      while ( *v36 == 57 );
      v4 = this;
    }
    v37 = v35 + 1;
    *v36 = v37;
    if ( v37 == 81 )
    {
      Source -= 2;
      *v36 = 49;
      *((_DWORD *)v36 - 1) = 5242944;
      v38 = v97 + 2;
      v97 += 2;
    }
    else
    {
      v38 = v97;
    }
    v43 = v2 + 8;
    v44 = v38;
    v102 = v38;
    if ( !v2[32] )
      break;
LABEL_47:
    v49 = *v21;
    _mm_lfence();
    if ( v44 >= v49 )
    {
      v105 = *v21;
      if ( *((_QWORD *)v2 + 8) )
      {
        _mm_lfence();
        sqlencrypt::SHA256::hash(*((sqlencrypt::SHA256 **)v2 + 8), Source, *v21);
      }
      v8 = BATCHCTX::QueuePacket(
             *(BATCHCTX **)v2,
             *(void **)(*(_QWORD *)v2 + 112LL),
             *v21,
             Source,
             3,
             *((_DWORD *)v2 + 5),
             0);
      if ( v8 < 0 )
        goto LABEL_93;
      v50 = *v21;
      *v21 = 0;
      v2[32] = 0;
      if ( v102 != v50 )
      {
        _mm_lfence();
        v8 = CRPCSQLStream::SendCommandPart((CRPCSQLStream *)v2, (const unsigned __int16 *)&Source[v105], v102 - v50);
        if ( v8 < 0 )
          goto LABEL_93;
      }
    }
    else
    {
      memcpy_s((void *const)(**(_QWORD **)v43 + *(_QWORD *)(*(_QWORD *)v43 + 8LL)), v44, Source, v44);
      if ( *((_QWORD *)v2 + 8) )
      {
        _mm_lfence();
        sqlencrypt::SHA256::hash(*((sqlencrypt::SHA256 **)v2 + 8), Source, v97);
      }
      *(_QWORD *)(*(_QWORD *)v43 + 8LL) += v102;
      *v21 -= v97;
    }
    v7 = *(_QWORD *)v106;
    v12 = v96;
    v51 = *(_QWORD *)v106;
    v52 = v96;
    if ( !*(_QWORD *)v106 )
      goto LABEL_152;
    v7 = 0;
    do
    {
      if ( *(_WORD *)v52 != 32 && (unsigned __int16)(*(_WORD *)v52 - 9) > 4u )
        break;
      v52 += 2;
      --v51;
    }
    while ( v51 );
    v4 = this;
    if ( v51 && *(_WORD *)v52 == 61 )
    {
      if ( v103 )
      {
        v53 = *(_WORD *)(v103 + 22);
        if ( (v53 & 4) != 0 )
          *(_WORD *)(v103 + 22) = v53 & 0xFFF9 | 2;
      }
      v11 = *(_WORD *)v96 == 61;
    }
    else
    {
LABEL_152:
      if ( v103 )
      {
        if ( (*(_BYTE *)(v103 + 22) & 6) != 0 )
        {
          _mm_lfence();
          v54 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v4 + 1) + 1424LL) + 272LL);
          if ( (*(_BYTE *)(*(_QWORD *)(v54 + 24) * (v98 - 1LL) + v54 + 54) & 4) == 0 )
          {
            if ( v2[32] == (_BYTE)v7 )
            {
              _mm_lfence();
              v55 = *((unsigned int *)v2 + 4) - *(_QWORD *)(*(_QWORD *)v43 + 8LL);
              if ( v55 <= 4 )
              {
                v57 = 1;
                v56 = 1;
              }
              else
              {
                _mm_lfence();
                v56 = v55 - 4;
                *((_QWORD *)v2 + 6) = *(_QWORD *)(*(_QWORD *)v43 + 8LL);
                v57 = v7;
              }
              *((_DWORD *)v2 + 9) = v56;
              *v104 = v56;
              v2[33] = v57;
              v58 = *((unsigned int *)v2 + 4) - *(_QWORD *)(*(_QWORD *)v43 + 8LL);
              _mm_lfence();
              if ( v58 <= 4 )
              {
                v59 = BATCHCTX::QueuePacket(
                        *(BATCHCTX **)v2,
                        *(void **)(*(_QWORD *)v2 + 112LL),
                        4u,
                        (const unsigned __int8 *)v2 + 40,
                        3,
                        *((_DWORD *)v2 + 5),
                        v7);
                v7 = 0;
                if ( v59 < 0 )
                {
                  v8 = -2147467259;
LABEL_96:
                  if ( (bidGblFlags & 2) == 0 )
                    goto LABEL_147;
                  v42 = (unsigned int)v8;
                  v9 = 8138761;
                  goto LABEL_146;
                }
              }
              else
              {
                *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v43 + 8LL) + **(_QWORD **)v43) = *v21;
                *(_QWORD *)(*(_QWORD *)v43 + 8LL) += 4LL;
              }
              v2[32] = 1;
            }
            v60 = *v21 <= 0xE;
            _mm_lfence();
            if ( v60 )
            {
              v61 = *v21;
              if ( *((_QWORD *)v2 + 8) != v7 )
              {
                _mm_lfence();
                sqlencrypt::SHA256::hash(*((sqlencrypt::SHA256 **)v2 + 8), L" OUTPUT", v61);
                LODWORD(v7) = 0;
              }
              v62 = BATCHCTX::QueuePacket(
                      *(BATCHCTX **)v2,
                      *(void **)(*(_QWORD *)v2 + 112LL),
                      *v21,
                      L" OUTPUT",
                      3,
                      *((_DWORD *)v2 + 5),
                      v7);
              v7 = 0;
              v8 = v62;
              if ( v62 < 0 )
                goto LABEL_96;
              v63 = *v21;
              *v21 = 0;
              v2[32] = 0;
              if ( 14 != v63 )
              {
                _mm_lfence();
                v64 = CRPCSQLStream::SendCommandPart(
                        (CRPCSQLStream *)v2,
                        (const unsigned __int16 *)&aOutput[v61],
                        14 - v63);
                v7 = 0;
                v8 = v64;
                if ( v64 < 0 )
                  goto LABEL_96;
              }
            }
            else
            {
              memcpy_s((void *const)(**(_QWORD **)v43 + *(_QWORD *)(*(_QWORD *)v43 + 8LL)), 0xEu, L" OUTPUT", 0xEu);
              v7 = 0;
              if ( *((_QWORD *)v2 + 8) )
              {
                _mm_lfence();
                sqlencrypt::SHA256::hash(*((sqlencrypt::SHA256 **)v2 + 8), L" OUTPUT", 0xEu);
                v7 = 0;
              }
              *(_QWORD *)(*(_QWORD *)v43 + 8LL) += 14LL;
              *v21 -= 14;
            }
            v12 = v96;
          }
        }
      }
      v11 = 0;
    }
    v10 = v108;
    v13 = v98 + 1;
    v14 = v107;
    v98 = v13;
    if ( v13 > *(_DWORD *)(v108 + 796) )
      goto LABEL_98;
    v3 = a2;
  }
  _mm_lfence();
  v45 = *((unsigned int *)v2 + 4) - *(_QWORD *)(*(_QWORD *)v43 + 8LL);
  if ( v45 <= 4 )
  {
    v47 = 1;
    v46 = 1;
  }
  else
  {
    _mm_lfence();
    v46 = v45 - 4;
    *((_QWORD *)v2 + 6) = *(_QWORD *)(*(_QWORD *)v43 + 8LL);
    v47 = 0;
  }
  *((_DWORD *)v2 + 9) = v46;
  *v21 = v46;
  v2[33] = v47;
  v48 = *((unsigned int *)v2 + 4) - *(_QWORD *)(*(_QWORD *)v43 + 8LL);
  _mm_lfence();
  if ( v48 > 4 )
  {
    *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v43 + 8LL) + **(_QWORD **)v43) = *v21;
    *(_QWORD *)(*(_QWORD *)v43 + 8LL) += 4LL;
LABEL_46:
    v2[32] = 1;
    goto LABEL_47;
  }
  if ( (int)BATCHCTX::QueuePacket(
              *(BATCHCTX **)v2,
              *(void **)(*(_QWORD *)v2 + 112LL),
              4u,
              (const unsigned __int8 *)v2 + 40,
              3,
              *((_DWORD *)v2 + 5),
              0) >= 0 )
  {
    v44 = v102;
    goto LABEL_46;
  }
  v8 = -2147467259;
LABEL_93:
  if ( (bidGblFlags & 2) == 0 )
    goto LABEL_147;
  v42 = (unsigned int)v8;
  v9 = 8105993;
LABEL_146:
  _mm_lfence();
  bidTraceHR(0, v9, v42, v6);
LABEL_147:
  _mm_lfence();
  v91 = (_QWORD *)*((_QWORD *)v4 + 1);
  v92 = (CRPCRequest *)v91[140];
  if ( v92 )
    CRPCRequest::RemoveAllCommands(v92, v91);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1004cb4e0  mov     rax, rsp
0x1004cb4e3  mov     [rax+10h], rbx
0x1004cb4e7  mov     [rax+18h], rsi
0x1004cb4eb  mov     [rax+20h], rdi
0x1004cb4ef  push    rbp
0x1004cb4f0  push    r12
0x1004cb4f2  push    r13
0x1004cb4f4  push    r14
0x1004cb4f6  push    r15
0x1004cb4f8  lea     rbp, [rax-5Fh]
0x1004cb4fc  sub     rsp, 0C0h
0x1004cb503  mov     rax, cs:__security_cookie
0x1004cb50a  xor     rax, rsp
0x1004cb50d  mov     [rbp+57h+var_28], rax
0x1004cb511  mov     rax, [rcx+8]
0x1004cb515  lea     rbx, [rcx+60h]
0x1004cb519  mov     r9, [rcx+20h]; unsigned __int64
0x1004cb51d  mov     r14b, dl
0x1004cb520  mov     [rbp+57h+var_9C], dl
0x1004cb523  mov     r12, rcx
0x1004cb526  mov     [rbp+57h+var_80], rcx
0x1004cb52a  lea     rdx, [rcx+28h]; struct RPCPARAMEXINFO *
0x1004cb52e  mov     r8d, [rax+31Ch]; unsigned int
0x1004cb535  mov     rcx, rbx; this
0x1004cb538  call    ?OnBeginSendCommand@CRPCSQLStream@@QEAAJPEAVRPCPARAMEXINFO@@K_K@Z; CRPCSQLStream::OnBeginSendCommand(RPCPARAMEXINFO *,ulong,unsigned __int64)
0x1004cb53d  xor     r11d, r11d
0x1004cb540  mov     edi, eax
0x1004cb542  lea     r13d, [r11+2]
0x1004cb546  test    eax, eax
0x1004cb548  jns     short loc_1004CB561
0x1004cb54a  test    byte ptr cs:_bidGblFlags, r13b
0x1004cb551  jz      loc_1004CBFA9
0x1004cb557  mov     edx, 7A7809h
0x1004cb55c  jmp     loc_1004CBF9C
0x1004cb561  lfence
0x1004cb564  mov     rax, [r12+8]
0x1004cb569  cmp     [rax+31Ch], r11d
0x1004cb570  jz      loc_1004CBE13
0x1004cb576  lfence
0x1004cb579  mov     r8, [r12+8]
0x1004cb57e  mov     edi, 1
0x1004cb583  mov     rcx, [r12+20h]
0x1004cb588  movzx   r9d, r11w
0x1004cb58c  mov     r10, [r12+18h]
0x1004cb591  mov     esi, edi
0x1004cb593  mov     qword ptr [rbp+57h+var_58], rcx
0x1004cb597  lea     rcx, [rbp+57h+var_2E]
0x1004cb59b  mov     rdx, [r8+1D0h]
0x1004cb5a2  lea     r15d, [rdi+3]
0x1004cb5a6  add     rdx, 8
0x1004cb5aa  mov     [rbp+57h+var_40], r11
0x1004cb5ae  mov     [rbp+57h+var_38], r11
0x1004cb5b2  mov     dword ptr [rbp+27h], 400000h
0x1004cb5b9  mov     [rbp+57h+var_2C], 300050h
0x1004cb5c0  mov     [rbp+57h+var_48], r8
0x1004cb5c4  mov     [rbp+57h+var_98], r10
0x1004cb5c8  mov     [rbp+57h+Source], rcx
0x1004cb5cc  mov     [rbp+57h+var_90], 6
0x1004cb5d3  mov     [rbp+57h+var_8C], edi
0x1004cb5d6  mov     [rbp+57h+var_50], rdx
0x1004cb5da  cmp     [r8+31Ch], edi
0x1004cb5e1  jb      loc_1004CBC8B
0x1004cb5e7  test    r14b, r14b
0x1004cb5ea  jnz     short loc_1004CB618
0x1004cb5ec  mov     rcx, [r8+1C8h]
0x1004cb5f3  mov     eax, esi
0x1004cb5f5  cmp     rax, [rcx+8]
0x1004cb5f9  ja      short loc_1004CB618
0x1004cb5fb  lea     r8, [rax-1]
0x1004cb5ff  imul    r8, [rcx+18h]
0x1004cb604  add     r8, 20h ; ' '
0x1004cb608  add     r8, rcx
0x1004cb60b  mov     [rbp+57h+var_70], r8
0x1004cb60f  jz      short loc_1004CB61C
0x1004cb611  cmp     r11w, [r8+10h]
0x1004cb616  jnz     short loc_1004CB61C
0x1004cb618  mov     [rbp+57h+var_70], r11
0x1004cb61c  mov     rdx, [rdx]
0x1004cb61f  lea     ecx, [rsi-1]
0x1004cb622  movzx   eax, r9w
0x1004cb626  lea     rsi, [rbx+28h]
0x1004cb62a  imul    rcx, [rdx+18h]
0x1004cb62f  add     eax, [rcx+rdx+20h]
0x1004cb633  mov     r14d, eax
0x1004cb636  add     r14, r14
0x1004cb639  mov     [rbp+57h+var_A0], eax
0x1004cb63c  cmp     [rbx+20h], r11b
0x1004cb640  jnz     loc_1004CB6C8
0x1004cb646  mov     r8, [rbx+8]
0x1004cb64a  mov     r9d, [rbx+10h]
0x1004cb64e  mov     eax, r9d
0x1004cb651  mov     rcx, [r8+8]
0x1004cb655  sub     rax, rcx
0x1004cb658  cmp     rax, r15
0x1004cb65b  jbe     short loc_1004CB669
0x1004cb65d  mov     [rbx+30h], rcx
0x1004cb661  mov     dl, r11b
0x1004cb664  lea     ecx, [rax-4]
0x1004cb667  jmp     short loc_1004CB66E
0x1004cb669  mov     dl, dil
0x1004cb66c  mov     ecx, edi
0x1004cb66e  mov     [rbx+24h], ecx
0x1004cb671  mov     [rsi], ecx
0x1004cb673  mov     [rbx+21h], dl
0x1004cb676  mov     rdx, [r8+8]
0x1004cb67a  sub     r9, rdx
0x1004cb67d  cmp     r9, r15
0x1004cb680  jbe     short loc_1004CB692
0x1004cb682  mov     rax, [r8]
0x1004cb685  mov     [rdx+rax], ecx
0x1004cb688  mov     rax, [rbx+8]
0x1004cb68c  add     [rax+8], r15
0x1004cb690  jmp     short loc_1004CB6C4
0x1004cb692  mov     rcx, [rbx]; this
0x1004cb695  mov     r9, rsi; unsigned __int8 *
0x1004cb698  mov     eax, [rbx+14h]
0x1004cb69b  mov     r8, r15; unsigned __int64
0x1004cb69e  mov     [rsp+0E0h+var_B0], r11d; int
0x1004cb6a3  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x1004cb6a7  mov     rdx, [rcx+70h]; void *
0x1004cb6ab  mov     [rsp+0E0h+var_C0], 3; char
0x1004cb6b0  call    ?QueuePacket@BATCHCTX@@AEAAJPEAX_KPEBEEKH@Z; BATCHCTX::QueuePacket(void *,unsigned __int64,uchar const *,uchar,ulong,int)
0x1004cb6b5  xor     r11d, r11d
0x1004cb6b8  test    eax, eax
0x1004cb6ba  js      loc_1004CBC43
0x1004cb6c0  mov     r10, [rbp+57h+var_98]
0x1004cb6c4  mov     [rbx+20h], dil
0x1004cb6c8  mov     eax, [rsi]
0x1004cb6ca  mov     [rbp+57h+var_78], rax
0x1004cb6ce  cmp     r14, rax
0x1004cb6d1  jnb     loc_1004CB79E
0x1004cb6d7  mov     rax, [r12+68h]
0x1004cb6dc  mov     r9, r14; SourceSize
0x1004cb6df  mov     r8, r10; Source
0x1004cb6e2  mov     rdx, r14; DestinationSize
0x1004cb6e5  mov     rcx, [rax+8]
0x1004cb6e9  add     rcx, [rax]; Destination
0x1004cb6ec  call    cs:__imp_memcpy_s
0x1004cb6f2  mov     rcx, [r12+0A0h]; this
0x1004cb6fa  xor     r11d, r11d
0x1004cb6fd  test    rcx, rcx
0x1004cb700  jz      short loc_1004CB711
0x1004cb702  mov     rdx, [rbp+57h+var_98]; unsigned __int8 *
0x1004cb706  mov     r8d, r14d; unsigned int
0x1004cb709  call    ?hash@SHA256@sqlencrypt@@QEAAXPEBEK@Z; sqlencrypt::SHA256::hash(uchar const *,ulong)
0x1004cb70e  xor     r11d, r11d
0x1004cb711  mov     rax, [r12+68h]
0x1004cb716  add     [rax+8], r14
0x1004cb71a  sub     [r12+88h], r14d
0x1004cb722  mov     [rbp+57h+var_68], rsi
0x1004cb726  mov     ecx, [rbp+57h+var_A0]
0x1004cb729  mov     rax, [rbp+57h+var_98]
0x1004cb72d  inc     ecx
0x1004cb72f  sub     qword ptr [rbp+57h+var_58], rcx
0x1004cb733  mov     [rbp+57h+var_A0], r11d
0x1004cb737  lea     rax, [rax+rcx*2]
0x1004cb73b  movzx   ecx, word ptr [rbp+57h+var_2C+2]
0x1004cb73f  mov     [rbp+57h+var_98], rax
0x1004cb743  lea     rax, [rbp+57h+var_2C+2]
0x1004cb747  cmp     cx, 39h ; '9'
0x1004cb74b  jnz     short loc_1004CB767
0x1004cb74d  mov     r12d, 30h ; '0'
0x1004cb753  mov     [rax], r12w
0x1004cb757  sub     rax, r13
0x1004cb75a  movzx   ecx, word ptr [rax]
0x1004cb75d  cmp     cx, 39h ; '9'
0x1004cb761  jz      short loc_1004CB753
0x1004cb763  mov     r12, [rbp+57h+var_80]
0x1004cb767  mov     edi, 1
0x1004cb76c  add     cx, di
0x1004cb76f  mov     [rax], cx
0x1004cb772  cmp     cx, 51h ; 'Q'
0x1004cb776  jnz     loc_1004CB84F
0x1004cb77c  sub     [rbp+57h+Source], r13
0x1004cb780  lea     ecx, [rdi+30h]
0x1004cb783  mov     [rax], cx
0x1004cb786  sub     rax, r13
0x1004cb789  mov     dword ptr [rax-2], 500040h
0x1004cb790  mov     eax, [rbp+57h+var_90]
0x1004cb793  add     eax, r13d
0x1004cb796  mov     [rbp+57h+var_90], eax
0x1004cb799  jmp     loc_1004CB852
0x1004cb79e  mov     rcx, [r12+0A0h]; this
0x1004cb7a6  test    rcx, rcx
0x1004cb7a9  jz      short loc_1004CB7B9
0x1004cb7ab  mov     r8d, eax; unsigned int
0x1004cb7ae  mov     rdx, r10; unsigned __int8 *
0x1004cb7b1  call    ?hash@SHA256@sqlencrypt@@QEAAXPEBEK@Z; sqlencrypt::SHA256::hash(uchar const *,ulong)
0x1004cb7b6  xor     r11d, r11d
0x1004cb7b9  mov     rcx, [rbx]; this
0x1004cb7bc  mov     eax, [r12+74h]
0x1004cb7c1  mov     r8d, [r12+88h]; unsigned __int64
0x1004cb7c9  mov     r9, [rbp+57h+var_98]; unsigned __int8 *
0x1004cb7cd  mov     rdx, [rcx+70h]; void *
0x1004cb7d1  mov     [rsp+0E0h+var_B0], r11d; int
0x1004cb7d6  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x1004cb7da  mov     [rsp+0E0h+var_C0], 3; char
0x1004cb7df  call    ?QueuePacket@BATCHCTX@@AEAAJPEAX_KPEBEEKH@Z; BATCHCTX::QueuePacket(void *,unsigned __int64,uchar const *,uchar,ulong,int)
0x1004cb7e4  xor     r11d, r11d
0x1004cb7e7  mov     edi, eax
0x1004cb7e9  test    eax, eax
0x1004cb7eb  js      short loc_1004CB835
0x1004cb7ed  mov     eax, [r12+88h]
0x1004cb7f5  mov     [r12+88h], r11d
0x1004cb7fd  mov     [r12+80h], r11b
0x1004cb805  sub     r14, rax
0x1004cb808  jz      loc_1004CB722
0x1004cb80e  lfence
0x1004cb811  mov     rdx, [rbp+57h+var_98]
0x1004cb815  mov     r8, r14; unsigned __int64
0x1004cb818  add     rdx, [rbp+57h+var_78]; unsigned __int16 *
0x1004cb81c  mov     rcx, rbx; this
0x1004cb81f  call    ?SendCommandPart@CRPCSQLStream@@QEAAJPEBG_K@Z; CRPCSQLStream::SendCommandPart(ushort const *,unsigned __int64)
0x1004cb824  xor     r11d, r11d
0x1004cb827  mov     [rbp+57h+var_68], rsi
0x1004cb82b  mov     edi, eax
0x1004cb82d  test    eax, eax
0x1004cb82f  jns     loc_1004CB726
0x1004cb835  test    byte ptr cs:_bidGblFlags, r13b
0x1004cb83c  jz      loc_1004CBFA9
0x1004cb842  mov     r8d, edi
0x1004cb845  mov     edx, 7B4809h
0x1004cb84a  jmp     loc_1004CBF9F
0x1004cb84f  mov     eax, [rbp+57h+var_90]
0x1004cb852  lea     r14, [rbx+8]
0x1004cb856  mov     r10d, eax
0x1004cb859  mov     [rbp+57h+var_78], r10
0x1004cb85d  cmp     [rbx+20h], r11b
0x1004cb861  jnz     loc_1004CB8FC
0x1004cb867  lfence
0x1004cb86a  mov     rax, [r14]
0x1004cb86d  mov     edx, [rbx+10h]
0x1004cb870  sub     rdx, [rax+8]
0x1004cb874  cmp     rdx, r15
0x1004cb877  jbe     short loc_1004CB88F
0x1004cb879  lfence
0x1004cb87c  mov     rax, [r14]
0x1004cb87f  mov     rcx, [rax+8]
0x1004cb883  lea     eax, [rdx-4]
0x1004cb886  mov     [rbx+30h], rcx
0x1004cb88a  mov     cl, r11b
0x1004cb88d  jmp     short loc_1004CB894
0x1004cb88f  mov     cl, dil
0x1004cb892  mov     eax, edi
0x1004cb894  mov     [rbx+24h], eax
0x1004cb897  mov     [rsi], eax
0x1004cb899  mov     [rbx+21h], cl
0x1004cb89c  mov     rax, [r14]
0x1004cb89f  mov     ecx, [rbx+10h]
0x1004cb8a2  sub     rcx, [rax+8]
0x1004cb8a6  lfence
0x1004cb8a9  cmp     rcx, r15
0x1004cb8ac  jbe     short loc_1004CB8C6
0x1004cb8ae  mov     rax, [r14]
0x1004cb8b1  mov     rdx, [rax+8]
0x1004cb8b5  mov     rcx, [rax]
0x1004cb8b8  mov     eax, [rsi]
0x1004cb8ba  mov     [rdx+rcx], eax
0x1004cb8bd  mov     rax, [r14]
0x1004cb8c0  add     [rax+8], r15
0x1004cb8c4  jmp     short loc_1004CB8F8
0x1004cb8c6  mov     rcx, [rbx]; this
0x1004cb8c9  mov     r9, rsi; unsigned __int8 *
0x1004cb8cc  mov     eax, [rbx+14h]
0x1004cb8cf  mov     r8, r15; unsigned __int64
0x1004cb8d2  mov     [rsp+0E0h+var_B0], r11d; int
0x1004cb8d7  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x1004cb8db  mov     rdx, [rcx+70h]; void *
0x1004cb8df  mov     [rsp+0E0h+var_C0], 3; char
0x1004cb8e4  call    ?QueuePacket@BATCHCTX@@AEAAJPEAX_KPEBEEKH@Z; BATCHCTX::QueuePacket(void *,unsigned __int64,uchar const *,uchar,ulong,int)
0x1004cb8e9  xor     r11d, r11d
0x1004cb8ec  test    eax, eax
0x1004cb8ee  js      loc_1004CBC4D
0x1004cb8f4  mov     r10, [rbp+57h+var_78]
0x1004cb8f8  mov     [rbx+20h], dil
0x1004cb8fc  mov     eax, [rsi]
0x1004cb8fe  lfence
0x1004cb901  cmp     r10, rax
0x1004cb904  jnb     short loc_1004CB950
0x1004cb906  mov     rax, [r14]
0x1004cb909  mov     r9, r10; SourceSize
0x1004cb90c  mov     r8, [rbp+57h+Source]; Source
0x1004cb910  mov     rdx, r10; DestinationSize
0x1004cb913  mov     rcx, [rax+8]
0x1004cb917  add     rcx, [rax]; Destination
0x1004cb91a  call    cs:__imp_memcpy_s
0x1004cb920  cmp     qword ptr [rbx+40h], 0
0x1004cb925  jz      short loc_1004CB93B
0x1004cb927  lfence
0x1004cb92a  mov     r8d, [rbp+57h+var_90]; unsigned int
0x1004cb92e  mov     rdx, [rbp+57h+Source]; unsigned __int8 *
0x1004cb932  mov     rcx, [rbx+40h]; this
0x1004cb936  call    ?hash@SHA256@sqlencrypt@@QEAAXPEBEK@Z; sqlencrypt::SHA256::hash(uchar const *,ulong)
0x1004cb93b  mov     rax, [r14]
0x1004cb93e  mov     r8, [rbp+57h+var_78]
0x1004cb942  add     [rax+8], r8
0x1004cb946  mov     eax, [rbp+57h+var_90]
0x1004cb949  sub     [rsi], eax
0x1004cb94b  jmp     loc_1004CB9D5
0x1004cb950  mov     eax, [rsi]
  ... truncated ...
```
