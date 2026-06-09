# CRPCPolicy::WriteTVPColMetadata(tagTVPCOLMETADATA *)

- ea: `0x10045c5a4`
- end: `0x10045d603`
- name: `?WriteTVPColMetadata@CRPCPolicy@@QEAAJPEAUtagTVPCOLMETADATA@@@Z`
- size: `4191`
- prototype: `int(CRPCPolicy *__hidden this, struct tagTVPCOLMETADATA *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x10045aae0`

## callees

- `0x10045c5a4`
- `0x100463e78`
- `0x100546a24`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045c5f6`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045c634`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045c677`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045c6ff`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045c737`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045c8dd`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045c917`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045c971`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045cc07`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045cd3d`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045ce1b`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045ce61`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045cead`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045ceea`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045cf36`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045cf73`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045d1c3`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045d20f`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045d24c`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045d298`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045d2d5`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045d4d1`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045d50c`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045c5f6`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045c634`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045c677`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045c6ff`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045c737`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045c8dd`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045c917`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045c971`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045cc07`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045cd3d`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045ce1b`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045ce61`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045cead`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045ceea`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045cf36`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045cf73`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045d1c3`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045d20f`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045d24c`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045d298`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045d2d5`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045d4d1`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10045d50c`

## pseudocode

```c
__int64 __fastcall CRPCPolicy::WriteTVPColMetadata(CRPCPolicy *this, struct tagTVPCOLMETADATA *a2)
{
  _QWORD *v3; // rcx
  __int64 v5; // rdx
  unsigned int *v6; // r15
  unsigned __int64 v7; // rcx
  unsigned __int64 v8; // rcx
  __int64 v9; // r9
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  unsigned __int64 v16; // rcx
  char *v17; // r8
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  unsigned int v20; // edi
  int v21; // eax
  __int64 v22; // rdx
  rsize_t v23; // rdi
  unsigned __int64 v24; // rcx
  char *v25; // r8
  unsigned int v26; // ecx
  unsigned int v27; // ecx
  unsigned int v28; // ecx
  unsigned int v29; // ecx
  unsigned __int64 v30; // rcx
  unsigned __int64 v31; // rcx
  unsigned __int64 v32; // rcx
  unsigned __int64 v33; // rcx
  unsigned __int64 v34; // rcx
  unsigned __int64 v35; // rcx
  unsigned int v36; // ecx
  unsigned int v37; // ecx
  unsigned int v38; // ecx
  unsigned int v39; // ecx
  unsigned int v40; // ecx
  unsigned __int64 v41; // rcx
  unsigned __int64 v42; // rcx
  unsigned int v43; // ecx
  unsigned int v44; // ecx
  unsigned int v45; // ecx
  unsigned int v46; // ecx
  unsigned __int64 v48; // rcx
  unsigned __int64 v49; // rcx
  unsigned __int64 v50; // rcx
  _BYTE *v51; // r14
  unsigned __int64 v52; // rcx
  unsigned __int64 v53; // rdi
  unsigned __int64 v54; // rcx
  _BYTE *v55; // r14
  unsigned __int64 v56; // rcx
  unsigned __int64 v57; // rdi
  unsigned __int64 v58; // rcx
  _WORD *v59; // r14
  unsigned __int64 v60; // rcx
  char *v61; // rdx
  rsize_t v62; // rcx
  _BYTE *v63; // r14
  unsigned __int64 v64; // rcx
  unsigned __int64 v65; // rdi
  unsigned __int64 v66; // rcx
  _BYTE *v67; // r14
  unsigned __int64 v68; // rcx
  unsigned __int64 v69; // rdi
  unsigned __int64 v70; // rcx
  _BYTE *v71; // r14
  unsigned __int64 v72; // rcx
  rsize_t v73; // rcx
  unsigned __int64 v74; // rcx
  unsigned __int64 v75; // rcx

  v3 = (_QWORD *)*((_QWORD *)this + 1);
  v5 = v3[1];
  v6 = (unsigned int *)((char *)this + 20);
  if ( (unsigned __int64)*((unsigned int *)this + 4) - v5 <= 4 )
  {
    v21 = BATCHCTX::QueuePacket(
            *(BATCHCTX **)this,
            *(void **)(*(_QWORD *)this + 112LL),
            4u,
            (const unsigned __int8 *)a2,
            3,
            *v6,
            0);
    v20 = v21;
    if ( v21 < 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
        return v20;
      v22 = 566281;
      goto LABEL_192;
    }
  }
  else
  {
    memcpy_s((void *const)(v5 + *v3), 4u, a2, 4u);
    *(_QWORD *)(*((_QWORD *)this + 1) + 8LL) += 4LL;
  }
  v7 = *((unsigned int *)this + 4) - *(_QWORD *)(*((_QWORD *)this + 1) + 8LL);
  _mm_lfence();
  if ( v7 <= 2 )
  {
    v21 = BATCHCTX::QueuePacket(
            *(BATCHCTX **)this,
            *(void **)(*(_QWORD *)this + 112LL),
            2u,
            (const unsigned __int8 *)a2 + 4,
            3,
            *v6,
            0);
    v20 = v21;
    if ( v21 < 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
        return v20;
      v22 = 570377;
      goto LABEL_192;
    }
  }
  else
  {
    memcpy_s((void *const)(**((_QWORD **)this + 1) + *(_QWORD *)(*((_QWORD *)this + 1) + 8LL)), 2u, (char *)a2 + 4, 2u);
    *(_QWORD *)(*((_QWORD *)this + 1) + 8LL) += 2LL;
  }
  v8 = *((unsigned int *)this + 4) - *(_QWORD *)(*((_QWORD *)this + 1) + 8LL);
  _mm_lfence();
  if ( v8 <= 1 )
  {
    v21 = BATCHCTX::QueuePacket(
            *(BATCHCTX **)this,
            *(void **)(*(_QWORD *)this + 112LL),
            1u,
            (const unsigned __int8 *)a2 + 6,
            3,
            *v6,
            0);
    v20 = v21;
    if ( v21 < 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
        return v20;
      v22 = 574473;
      goto LABEL_192;
    }
  }
  else
  {
    memcpy_s((void *const)(**((_QWORD **)this + 1) + *(_QWORD *)(*((_QWORD *)this + 1) + 8LL)), 1u, (char *)a2 + 6, 1u);
    ++*(_QWORD *)(*((_QWORD *)this + 1) + 8LL);
  }
  v10 = *((unsigned __int8 *)a2 + 6);
  if ( v10 > 0x6C )
  {
    if ( v10 > 0xAF )
    {
      v43 = v10 - 231;
      if ( v43 )
      {
        v44 = v43 - 8;
        if ( v44 )
        {
          v45 = v44 - 1;
          if ( v45 )
          {
            v46 = v45 - 1;
            if ( v46 )
            {
              if ( v46 != 4 )
                goto LABEL_95;
              v48 = *((unsigned int *)this + 4) - *(_QWORD *)(*((_QWORD *)this + 1) + 8LL);
              _mm_lfence();
              if ( v48 <= 2 )
              {
                v21 = BATCHCTX::QueuePacket(
                        *(BATCHCTX **)this,
                        *(void **)(*(_QWORD *)this + 112LL),
                        2u,
                        (const unsigned __int8 *)a2 + 8,
                        3,
                        *v6,
                        0);
                v20 = v21;
                if ( v21 < 0 )
                {
                  if ( (bidGblFlags & 2) == 0 )
                    return v20;
                  v22 = 770057;
                  goto LABEL_192;
                }
              }
              else
              {
                memcpy_s(
                  (void *const)(**((_QWORD **)this + 1) + *(_QWORD *)(*((_QWORD *)this + 1) + 8LL)),
                  2u,
                  (char *)a2 + 8,
                  2u);
                *(_QWORD *)(*((_QWORD *)this + 1) + 8LL) += 2LL;
              }
              v49 = *((unsigned int *)this + 4) - *(_QWORD *)(*((_QWORD *)this + 1) + 8LL);
              _mm_lfence();
              if ( v49 <= 1 )
              {
                v21 = BATCHCTX::QueuePacket(
                        *(BATCHCTX **)this,
                        *(void **)(*(_QWORD *)this + 112LL),
                        1u,
                        (const unsigned __int8 *)a2 + 10,
                        3,
                        *v6,
                        0);
                v20 = v21;
                if ( v21 < 0 )
                {
                  if ( (bidGblFlags & 2) == 0 )
                    return v20;
                  v22 = 775177;
                  goto LABEL_192;
                }
                goto LABEL_20;
              }
LABEL_46:
              v17 = (char *)a2 + 10;
              goto LABEL_19;
            }
            v50 = *((unsigned int *)this + 4) - *(_QWORD *)(*((_QWORD *)this + 1) + 8LL);
            _mm_lfence();
            if ( v50 <= 1 )
            {
              v21 = BATCHCTX::QueuePacket(
                      *(BATCHCTX **)this,
                      *(void **)(*(_QWORD *)this + 112LL),
                      1u,
                      (const unsigned __int8 *)a2 + 8,
                      3,
                      *v6,
                      0);
              v20 = v21;
              if ( v21 < 0 )
              {
                if ( (bidGblFlags & 2) == 0 )
                  return v20;
                v22 = 719881;
                goto LABEL_192;
              }
            }
            else
            {
              memcpy_s(
                (void *const)(**((_QWORD **)this + 1) + *(_QWORD *)(*((_QWORD *)this + 1) + 8LL)),
                1u,
                (char *)a2 + 8,
                1u);
              ++*(_QWORD *)(*((_QWORD *)this + 1) + 8LL);
            }
            if ( *((_BYTE *)a2 + 8) != 1 )
              goto LABEL_20;
            v51 = (char *)a2 + 9;
            v52 = *((unsigned int *)this + 4) - *(_QWORD *)(*((_QWORD *)this + 1) + 8LL);
            _mm_lfence();
            if ( v52 <= 1 )
            {
              v21 = BATCHCTX::QueuePacket(
                      *(BATCHCTX **)this,
                      *(void **)(*(_QWORD *)this + 112LL),
                      1u,
                      (const unsigned __int8 *)a2 + 9,
                      3,
                      *v6,
                      0);
              v20 = v21;
              if ( v21 < 0 )
              {
                if ( (bidGblFlags & 2) == 0 )
                  return v20;
                v22 = 727049;
                goto LABEL_192;
              }
            }
            else
            {
              memcpy_s(
                (void *const)(**((_QWORD **)this + 1) + *(_QWORD *)(*((_QWORD *)this + 1) + 8LL)),
                1u,
                (char *)a2 + 9,
                1u);
              ++*(_QWORD *)(*((_QWORD *)this + 1) + 8LL);
            }
            if ( *v51 )
            {
              _mm_lfence();
              v53 = 2LL * (unsigned __int8)*v51;
              v54 = *((unsigned int *)this + 4) - *(_QWORD *)(*((_QWORD *)this + 1) + 8LL);
              _mm_lfence();
              if ( v53 >= v54 )
              {
                v21 = BATCHCTX::QueuePacket(
                        *(BATCHCTX **)this,
                        *(void **)(*(_QWORD *)this + 112LL),
                        2LL * (unsigned __int8)*v51,
                        *((const unsigned __int8 **)a2 + 2),
                        3,
                        *v6,
                        0);
                v20 = v21;
                if ( v21 < 0 )
                {
                  if ( (bidGblFlags & 2) == 0 )
                    return v20;
                  v22 = 734217;
                  goto LABEL_192;
                }
              }
              else
              {
                memcpy_s(
                  (void *const)(**((_QWORD **)this + 1) + *(_QWORD *)(*((_QWORD *)this + 1) + 8LL)),
                  2LL * (unsigned __int8)*v51,
                  *((const void *const *)a2 + 2),
                  2LL * (unsigned __int8)*v51);
                *(_QWORD *)(*((_QWORD *)this + 1) + 8LL) += v53;
              }
            }
            v55 = (char *)a2 + 24;
            v56 = *((unsigned int *)this + 4) - *(_QWORD *)(*((_QWORD *)this + 1) + 8LL);
            _mm_lfence();
            if ( v56 <= 1 )
            {
              v21 = BATCHCTX::QueuePacket(
                      *(BATCHCTX **)this,
                      *(void **)(*(_QWORD *)this + 112LL),
                      1u,
                      (const unsigned __int8 *)a2 + 24,
                      3,
                      *v6,
                      0);
              v20 = v21;
              if ( v21 < 0 )
              {
                if ( (bidGblFlags & 2) == 0 )
                  return v20;
                v22 = 740361;
                goto LABEL_192;
              }
            }
            else
            {
              memcpy_s(
                (void *const)(**((_QWORD **)this + 1) + *(_QWORD *)(*((_QWORD *)this + 1) + 8LL)),
                1u,
                (char *)a2 + 24,
                1u);
              ++*(_QWORD *)(*((_QWORD *)this + 1) + 8LL);
            }
            if ( *v55 )
            {
              _mm_lfence();
              v57 = 2LL * (unsigned __int8)*v55;
              v58 = *((unsigned int *)this + 4) - *(_QWORD *)(*((_QWORD *)this + 1) + 8LL);
              _mm_lfence();
              if ( v57 >= v58 )
              {
                v21 = BATCHCTX::QueuePacket(
                        *(BATCHCTX **)this,
                        *(void **)(*(_QWORD *)this + 112LL),
                        2LL * (unsigned __int8)*v55,
                        *((const unsigned __int8 **)a2 + 4),
                        3,
                        *v6,
                        0);
                v20 = v21;
                if ( v21 < 0 )
                {
                  if ( (bidGblFlags & 2) == 0 )
                    return v20;
                  v22 = 747529;
                  goto LABEL_192;
                }
              }
              else
              {
                memcpy_s(
                  (void *const)(**((_QWORD **)this + 1) + *(_QWORD *)(*((_QWORD *)this + 1) + 8LL)),
                  2LL * (unsigned __int8)*v55,
                  *((const void *const *)a2 + 4),
                  2LL * (unsigned __int8)*v55);
                *(_QWORD *)(*((_QWORD *)this + 1) + 8LL) += v57;
              }
            }
            v59 = (_WORD *)((char *)a2 + 40);
            v60 = *((unsigned int *)this + 4) - *(_QWORD *)(*((_QWORD *)this + 1) + 8LL);
            _mm_lfence();
            if ( v60 <= 2 )
            {
              v21 = BATCHCTX::QueuePacket(
                      *(BATCHCTX **)this,
                      *(void **)(*(_QWORD *)this + 112LL),
                      2u,
                      (const unsigned __int8 *)a2 + 40,
                      3,
                      *v6,
                      0);
              v20 = v21;
              if ( v21 < 0 )
              {
                if ( (bidGblFlags & 2) == 0 )
                  return v20;
                v22 = 753673;
                goto LABEL_192;
              }
            }
            else
            {
              memcpy_s(
                (void *const)(**((_QWORD **)this + 1) + *(_QWORD *)(*((_QWORD *)this + 1) + 8LL)),
                2u,
                (char *)a2 + 40,
                2u);
              *(_QWORD *)(*((_QWORD *)this + 1) + 8LL) += 2LL;
            }
            if ( !*v59 )
              goto LABEL_20;
            _mm_lfence();
            v23 = 2LL * (unsigned __int16)*v59;
            v61 = (char *)*((_QWORD *)a2 + 6);
            v62 = *((unsigned int *)this + 4) - *(_QWORD *)(*((_QWORD *)this + 1) + 8LL);
            _mm_lfence();
            if ( v23 >= v62 )
            {
              v21 = BATCHCTX::QueuePacket(
                      *(BATCHCTX **)this,
                      *(void **)(*(_QWORD *)this + 112LL),
                      2LL * (unsigned __int16)*v59,
                      *((const unsigned __int8 **)a2 + 6),
                      3,
                      *v6,
                      0);
              v20 = v21;
              if ( v21 < 0 )
              {
                if ( (bidGblFlags & 2) == 0 )
                  return v20;
                v22 = 760841;
                goto LABEL_192;
              }
              goto LABEL_20;
            }
          }
          else
          {
            v63 = (char *)a2 + 8;
            v64 = *((unsigned int *)this + 4) - *(_QWORD *)(*((_QWORD *)this + 1) + 8LL);
            _mm_lfence();
            if ( v64 <= 1 )
            {
              v21 = BATCHCTX::QueuePacket(
                      *(BATCHCTX **)this,
                      *(void **)(*(_QWORD *)this + 112LL),
                      1u,
                      (const unsigned __int8 *)a2 + 8,
                      3,
                      *v6,
                      0);
              v20 = v21;
              if ( v21 < 0 )
              {
                if ( (bidGblFlags & 2) == 0 )
                  return v20;
                v22 = 677897;
                goto LABEL_192;
              }
            }
            else
            {
              memcpy_s(
                (void *const)(**((_QWORD **)this + 1) + *(_QWORD *)(*((_QWORD *)this + 1) + 8LL)),
                1u,
                (char *)a2 + 8,
                1u);
              ++*(_QWORD *)(*((_QWORD *)this + 1) + 8LL);
            }
            if ( *v63 )
            {
              _mm_lfence();
              v65 = 2LL * (unsigned __int8)*v63;
              v66 = *((unsigned int *)this + 4) - *(_QWORD *)(*((_QWORD *)this + 1) + 8LL);
              _mm_lfence();
              if ( v65 >= v66 )
              {
                v21 = BATCHCTX::QueuePacket(
                        *(BATCHCTX **)this,
                        *(void **)(*(_QWORD *)this + 112LL),
                        2LL * (unsigned __int8)*v63,
                        *((const unsigned __int8 **)a2 + 2),
                        3,
                        *v6,
                        0);
                v20 = v21;
                if ( v21 < 0 )
                {
                  if ( (bidGblFlags & 2) == 0 )
                    return v20;
                  v22 = 685065;
                  goto LABEL_192;
                }
              }
              else
              {
                memcpy_s(
                  (void *const)(**((_QWORD **)this + 1) + *(_QWORD *)(*((_QWORD *)this + 1) + 8LL)),
                  2LL * (unsigned __int8)*v63,
                  *((const void *const *)a2 + 2),
                  2LL * (unsigned __int8)*v63);
                *(_QWORD *)(*((_QWORD *)this + 1) + 8LL) += v65;
              }
            }
            v67 = (char *)a2 + 24;
            v68 = *((unsigned int *)this + 4) - *(_QWORD *)(*((_QWORD *)this + 1) + 8LL);
            _mm_lfence();
            if ( v68 <= 1 )
            {
              v21 = BATCHCTX::QueuePacket(
                      *(BATCHCTX **)this,
                      *(void **)(*(_QWORD *)this + 112LL),
                      1u,
                      (const unsigned __int8 *)a2 + 24,
                      3,
                      *v6,
                      0);
              v20 = v21;
              if ( v21 < 0 )
              {
                if ( (bidGblFlags & 2) == 0 )
                  return v20;
                v22 = 691209;
                goto LABEL_192;
              }
            }
            else
            {
              memcpy_s(
                (void *const)(**((_QWORD **)this + 1) + *(_QWORD *)(*((_QWORD *)this + 1) + 8LL)),
                1u,
                (char *)a2 + 24,
                1u);
              ++*(_QWORD *)(*((_QWORD *)this + 1) + 8LL);
            }
            if ( *v67 )
            {
              _mm_lfence();
              v69 = 2LL * (unsigned __int8)*v67;
              v70 = *((unsigned int *)this + 4) - *(_QWORD *)(*((_QWORD *)this + 1) + 8LL);
              _mm_lfence();
              if ( v69 >= v70 )
              {
                v21 = BATCHCTX::QueuePacket(
                        *(BATCHCTX **)this,
                        *(void **)(*(_QWORD *)this + 112LL),
                        2LL * (unsigned __int8)*v67,
                        *((const unsigned __int8 **)a2 + 4),
                        3,
                        *v6,
                        0);
                v20 = v21;
                if ( v21 < 0 )
                {
                  if ( (bidGblFlags & 2) == 0 )
                    return v20;
                  v22 = 698377;
                  goto LABEL_192;
                }
              }
              else
              {
                memcpy_s(
                  (void *const)(**((_QWORD **)this + 1) + *(_QWORD *)(*((_QWORD *)this + 1) + 8LL)),
                  2LL * (unsigned __int8)*v67,
                  *((const void *const *)a2 + 4),
                  2LL * (unsigned __int8)*v67);
                *(_QWORD *)(*((_QWORD *)this + 1) + 8LL) += v69;
              }
            }
            v71 = (char *)a2 + 40;
            v72 = *((unsigned int *)this + 4) - *(_QWORD *)(*((_QWORD *)this + 1) + 8LL);
            _mm_lfence();
            if ( v72 <= 1 )
            {
              v21 = BATCHCTX::QueuePacket(
                      *(BATCHCTX **)this,
                      *(void **)(*(_QWORD *)this + 112LL),
                      1u,
                      (const unsigned __int8 *)a2 + 40,
                      3,
                      *v6,
                      0);
              v20 = v21;
              if ( v21 < 0 )
              {
                if ( (bidGblFlags & 2) == 0 )
                  return v20;
                v22 = 704521;
                goto LABEL_192;
              }
            }
            else
            {
              memcpy_s(
                (void *const)(**((_QWORD **)this + 1) + *(_QWORD *)(*((_QWORD *)this + 1) + 8LL)),
                1u,
                (char *)a2 + 40,
                1u);
              ++*(_QWORD *)(*((_QWORD *)this + 1) + 8LL);
            }
            if ( !*v71 )
              goto LABEL_20;
            _mm_lfence();
            v23 = 2LL * (unsigned __int8)*v71;
            v61 = (char *)*((_QWORD *)a2 + 6);
            v73 = *((unsigned int *)this + 4) - *(_QWORD *)(*((_QWORD *)this + 1) + 8LL);
            _mm_lfence();
            if ( v23 >= v73 )
            {
              v21 = BATCHCTX::QueuePacket(
                      *(BATCHCTX **)this,
                      *(void **)(*(_QWORD *)this + 112LL),
                      2LL * (unsigned __int8)*v71,
                      *((const unsigned __int8 **)a2 + 6),
                      3,
                      *v6,
                      0);
              v20 = v21;
              if ( v21 < 0 )
              {
                if ( (bidGblFlags & 2) == 0 )
                  return v20;
                v22 = 711689;
                goto LABEL_192;
              }
              goto LABEL_20;
            }
          }
          v25 = v61;
          goto LABEL_182;
        }
      }
    }
    else if ( v10 != 175 )
    {
      v36 = v10 - 109;
      if ( !v36 || (v37 = v36 - 1) == 0 || (v38 = v37 - 1) == 0 )
      {
LABEL_86:
        v42 = *((unsigned int *)this + 4) - *(_QWORD *)(*((_QWORD *)this + 1) + 8LL);
        _mm_lfence();
        if ( v42 <= 1 )
        {
          v21 = BATCHCTX::QueuePacket(
                  *(BATCHCTX **)this,
                  *(void **)(*(_QWORD *)this + 112LL),
                  1u,
                  (const unsigned __int8 *)a2 + 8,
                  3,
                  *v6,
                  0);
          v20 = v21;
          if ( v21 < 0 )
          {
            if ( (bidGblFlags & 2) == 0 )
              return v20;
            v22 = 588809;
            goto LABEL_192;
          }
          goto LABEL_20;
        }
        goto LABEL_18;
      }
      v39 = v38 - 54;
      if ( !v39 )
      {
LABEL_81:
        v41 = *((unsigned int *)this + 4) - *(_QWORD *)(*((_QWORD *)this + 1) + 8LL);
        _mm_lfence();
        if ( v41 <= 2 )
        {
          v21 = BATCHCTX::QueuePacket(
                  *(BATCHCTX **)this,
                  *(void **)(*(_QWORD *)this + 112LL),
                  2u,
                  (const unsigned __int8 *)a2 + 8,
                  3,
                  *v6,
                  0);
          v20 = v21;
          if ( v21 < 0 )
          {
            if ( (bidGblFlags & 2) == 0 )
              return v20;
            v22 = 627721;
            goto LABEL_192;
          }
        }
        else
        {
          memcpy_s(
            (void *const)(**((_QWORD **)this + 1) + *(_QWORD *)(*((_QWORD *)this + 1) + 8LL)),
            2u,
            (char *)a2 + 8,
            2u);
          *(_QWORD *)(*((_QWORD *)this + 1) + 8LL) += 2LL;
        }
        goto LABEL_20;
      }
      v40 = v39 - 2;
      if ( v40 )
      {
        if ( v40 != 6 )
          goto LABEL_95;
        goto LABEL_81;
      }
    }
    v74 = *((unsigned int *)this + 4) - *(_QWORD *)(*((_QWORD *)this + 1) + 8LL);
    _mm_lfence();
    if ( v74 <= 2 )
    {
      v21 = BATCHCTX::QueuePacket(
              *(BATCHCTX **)this,
              *(void **)(*(_QWORD *)this + 112LL),
              2u,
              (const unsigned __int8 *)a2 + 8,
              3,
              *v6,
              0);
      v20 = v21;
      if ( v21 < 0 )
      {
        if ( (bidGblFlags & 2) == 0 )
          return v20;
        v22 = 637961;
        goto LABEL_192;
      }
    }
    else
    {
      memcpy_s(
        (void *const)(**((_QWORD **)this + 1) + *(_QWORD *)(*((_QWORD *)this + 1) + 8LL)),
        2u,
        (char *)a2 + 8,
        2u);
      *(_QWORD *)(*((_QWORD *)this + 1) + 8LL) += 2LL;
    }
    v23 = 5;
    v75 = *((unsigned int *)this + 4) - *(_QWORD *)(*((_QWORD *)this + 1) + 8LL);
    _mm_lfence();
    if ( v75 <= 5 )
    {
      v21 = BATCHCTX::QueuePacket(
              *(BATCHCTX **)this,
              *(void **)(*(_QWORD *)this + 112LL),
              5u,
              (const unsigned __int8 *)a2 + 10,
              3,
              *v6,
              0);
      v20 = v21;
      if ( v21 < 0 )
      {
        if ( (bidGblFlags & 2) == 0 )
          return v20;
        v22 = 643081;
        goto LABEL_192;
      }
      goto LABEL_20;
    }
    v25 = (char *)a2 + 10;
    goto LABEL_182;
  }
  if ( v10 == 108 )
  {
LABEL_41:
    v30 = *((unsigned int *)this + 4) - *(_QWORD *)(*((_QWORD *)this + 1) + 8LL);
    _mm_lfence();
    if ( v30 <= 1 )
    {
      v21 = BATCHCTX::QueuePacket(
              *(BATCHCTX **)this,
              *(void **)(*(_QWORD *)this + 112LL),
              1u,
              (const unsigned __int8 *)a2 + 8,
              3,
              *v6,
              0);
      v20 = v21;
      if ( v21 < 0 )
      {
        if ( (bidGblFlags & 2) == 0 )
          return v20;
        v22 = 609289;
        goto LABEL_192;
      }
    }
    else
    {
      memcpy_s(
        (void *const)(**((_QWORD **)this + 1) + *(_QWORD *)(*((_QWORD *)this + 1) + 8LL)),
        1u,
        (char *)a2 + 8,
        1u);
      ++*(_QWORD *)(*((_QWORD *)this + 1) + 8LL);
    }
    v31 = *((unsigned int *)this + 4) - *(_QWORD *)(*((_QWORD *)this + 1) + 8LL);
    _mm_lfence();
    if ( v31 <= 1 )
    {
      v21 = BATCHCTX::QueuePacket(
              *(BATCHCTX **)this,
              *(void **)(*(_QWORD *)this + 112LL),
              1u,
              (const unsigned __int8 *)a2 + 9,
              3,
              *v6,
              0);
      v20 = v21;
      if ( v21 < 0 )
      {
        if ( (bidGblFlags & 2) == 0 )
          return v20;
        v22 = 614409;
        goto LABEL_192;
      }
    }
    else
    {
      memcpy_s(
        (void *const)(**((_QWORD **)this + 1) + *(_QWORD *)(*((_QWORD *)this + 1) + 8LL)),
        1u,
        (char *)a2 + 9,
        1u);
      ++*(_QWORD *)(*((_QWORD *)this + 1) + 8LL);
    }
    v32 = *((unsigned int *)this + 4) - *(_QWORD *)(*((_QWORD *)this + 1) + 8LL);
    _mm_lfence();
    if ( v32 <= 1 )
    {
      v21 = BATCHCTX::QueuePacket(
              *(BATCHCTX **)this,
              *(void **)(*(_QWORD *)this + 112LL),
              1u,
              (const unsigned __int8 *)a2 + 10,
              3,
              *v6,
              0);
      v20 = v21;
      if ( v21 < 0 )
      {
        if ( (bidGblFlags & 2) == 0 )
          return v20;
        v22 = 619529;
        goto LABEL_192;
      }
      goto LABEL_20;
    }
    goto LABEL_46;
  }
  if ( v10 > 0x2A )
  {
    v26 = v10 - 43;
    if ( !v26 )
    {
LABEL_17:
      v16 = *((unsigned int *)this + 4) - *(_QWORD *)(*((_QWORD *)this + 1) + 8LL);
      _mm_lfence();
      if ( v16 <= 1 )
      {
        v21 = BATCHCTX::QueuePacket(
                *(BATCHCTX **)this,
                *(void **)(*(_QWORD *)this + 112LL),
                1u,
                (const unsigned __int8 *)a2 + 8,
                3,
                *v6,
                0);
        v20 = v21;
        if ( v21 < 0 )
        {
          if ( (bidGblFlags & 2) == 0 )
            return v20;
          v22 = 601097;
          goto LABEL_192;
        }
        goto LABEL_20;
      }
LABEL_18:
      v17 = (char *)a2 + 8;
LABEL_19:
      memcpy_s((void *const)(**((_QWORD **)this + 1) + *(_QWORD *)(*((_QWORD *)this + 1) + 8LL)), 1u, v17, 1u);
      ++*(_QWORD *)(*((_QWORD *)this + 1) + 8LL);
      goto LABEL_20;
    }
    v27 = v26 - 55;
    if ( !v27 )
    {
      v23 = 4;
      v35 = *((unsigned int *)this + 4) - *(_QWORD *)(*((_QWORD *)this + 1) + 8LL);
      _mm_lfence();
      if ( v35 <= 4 )
      {
        v21 = BATCHCTX::QueuePacket(
                *(BATCHCTX **)this,
                *(void **)(*(_QWORD *)this + 112LL),
                4u,
                (const unsigned __int8 *)a2 + 8,
                3,
                *v6,
                0);
        v20 = v21;
        if ( v21 < 0 )
        {
          if ( (bidGblFlags & 2) == 0 )
            return v20;
          v22 = 670729;
          goto LABEL_192;
        }
        goto LABEL_20;
      }
      goto LABEL_32;
    }
    v28 = v27 - 1;
    if ( !v28 )
      goto LABEL_47;
    v29 = v28 - 5;
    if ( !v29 )
      goto LABEL_86;
    if ( v29 != 2 )
      goto LABEL_95;
    goto LABEL_41;
  }
  if ( v10 == 42 )
    goto LABEL_17;
  v11 = v10 - 34;
  if ( !v11 )
  {
    v23 = 4;
    v24 = *((unsigned int *)this + 4) - *(_QWORD *)(*((_QWORD *)this + 1) + 8LL);
    _mm_lfence();
    if ( v24 <= 4 )
    {
      v21 = BATCHCTX::QueuePacket(
              *(BATCHCTX **)this,
              *(void **)(*(_QWORD *)this + 112LL),
              4u,
              (const unsigned __int8 *)a2 + 8,
              3,
              *v6,
              0);
      v20 = v21;
      if ( v21 < 0 )
      {
        if ( (bidGblFlags & 2) == 0 )
          return v20;
        v22 = 650249;
        goto LABEL_192;
      }
      goto LABEL_20;
    }
LABEL_32:
    v25 = (char *)a2 + 8;
LABEL_182:
    memcpy_s((void *const)(**((_QWORD **)this + 1) + *(_QWORD *)(*((_QWORD *)this + 1) + 8LL)), v23, v25, v23);
    *(_QWORD *)(*((_QWORD *)this + 1) + 8LL) += v23;
    goto LABEL_20;
  }
  v12 = v11 - 1;
  if ( !v12 )
  {
LABEL_47:
    v33 = *((unsigned int *)this + 4) - *(_QWORD *)(*((_QWORD *)this + 1) + 8LL);
    _mm_lfence();
    if ( v33 <= 4 )
    {
      v21 = BATCHCTX::QueuePacket(
              *(BATCHCTX **)this,
              *(void **)(*(_QWORD *)this + 112LL),
              4u,
              (const unsigned __int8 *)a2 + 8,
              3,
              *v6,
              0);
      v20 = v21;
      if ( v21 < 0 )
      {
        if ( (bidGblFlags & 2) == 0 )
          return v20;
        v22 = 658441;
        goto LABEL_192;
      }
    }
    else
    {
      memcpy_s(
        (void *const)(**((_QWORD **)this + 1) + *(_QWORD *)(*((_QWORD *)this + 1) + 8LL)),
        4u,
        (char *)a2 + 8,
        4u);
      *(_QWORD *)(*((_QWORD *)this + 1) + 8LL) += 4LL;
    }
    v23 = 5;
    v34 = *((unsigned int *)this + 4) - *(_QWORD *)(*((_QWORD *)this + 1) + 8LL);
    _mm_lfence();
    if ( v34 <= 5 )
    {
      v21 = BATCHCTX::QueuePacket(
              *(BATCHCTX **)this,
              *(void **)(*(_QWORD *)this + 112LL),
              5u,
              (const unsigned __int8 *)a2 + 12,
              3,
              *v6,
              0);
      v20 = v21;
      if ( v21 < 0 )
      {
        if ( (bidGblFlags & 2) == 0 )
          return v20;
        v22 = 663561;
        goto LABEL_192;
      }
      goto LABEL_20;
    }
    v25 = (char *)a2 + 12;
    goto LABEL_182;
  }
  v13 = v12 - 1;
  if ( !v13 )
    goto LABEL_86;
  v14 = v13 - 2;
  if ( !v14 )
    goto LABEL_86;
  v15 = v14 - 2;
  if ( !v15 )
  {
LABEL_20:
    v18 = (_QWORD *)*((_QWORD *)this + 1);
    v19 = v18[1];
    if ( (unsigned __int64)*((unsigned int *)this + 4) - v19 > 1 )
    {
      memcpy_s((void *const)(v19 + *v18), 1u, &dword_10058E8F4, 1u);
      v20 = 0;
      ++*(_QWORD *)(*((_QWORD *)this + 1) + 8LL);
      return v20;
    }
    v21 = BATCHCTX::QueuePacket(
            *(BATCHCTX **)this,
            *(void **)(*(_QWORD *)this + 112LL),
            1u,
            &dword_10058E8F4,
            3,
            *v6,
            0);
    v20 = v21;
    if ( v21 >= 0 || (bidGblFlags & 2) == 0 )
      return v20;
    v22 = 787465;
LABEL_192:
    _mm_lfence();
    bidTraceHR(0, v22, (unsigned int)v21, v9);
    return v20;
  }
  if ( v15 == 1 )
    goto LABEL_17;
LABEL_95:
  if ( (bidGblFlags & 2) != 0 )
    return bidTraceHR(0, 782345, 2147500037LL, v9);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x10045c5a4  mov     [rsp+arg_0], rbx
0x10045c5a9  mov     [rsp+arg_8], rbp
0x10045c5ae  mov     [rsp+arg_10], rsi
0x10045c5b3  push    rdi
0x10045c5b4  push    r12
0x10045c5b6  push    r13
0x10045c5b8  push    r14
0x10045c5ba  push    r15
0x10045c5bc  sub     rsp, 40h
0x10045c5c0  mov     rbx, rcx
0x10045c5c3  xor     r13d, r13d
0x10045c5c6  mov     rcx, [rcx+8]
0x10045c5ca  mov     rbp, rdx
0x10045c5cd  mov     eax, [rbx+10h]
0x10045c5d0  lea     edi, [r13+4]
0x10045c5d4  mov     rdx, [rcx+8]
0x10045c5d8  lea     r15, [rbx+14h]
0x10045c5dc  sub     rax, rdx
0x10045c5df  cmp     rax, rdi
0x10045c5e2  jbe     loc_10045C74D
0x10045c5e8  mov     rcx, [rcx]
0x10045c5eb  mov     r9d, edi; SourceSize
0x10045c5ee  add     rcx, rdx; Destination
0x10045c5f1  mov     r8, rbp; Source
0x10045c5f4  mov     edx, edi; DestinationSize
0x10045c5f6  call    cs:__imp_memcpy_s
0x10045c5fc  mov     rax, [rbx+8]
0x10045c600  add     [rax+8], rdi
0x10045c604  mov     rax, [rbx+8]
0x10045c608  mov     esi, 2
0x10045c60d  mov     ecx, [rbx+10h]
0x10045c610  sub     rcx, [rax+8]
0x10045c614  lfence
0x10045c617  cmp     rcx, rsi
0x10045c61a  jbe     loc_10045C796
0x10045c620  mov     rax, [rbx+8]
0x10045c624  lea     r8, [rbp+4]; Source
0x10045c628  mov     r9d, esi; SourceSize
0x10045c62b  mov     edx, esi; DestinationSize
0x10045c62d  mov     rcx, [rax+8]
0x10045c631  add     rcx, [rax]; Destination
0x10045c634  call    cs:__imp_memcpy_s
0x10045c63a  mov     rax, [rbx+8]
0x10045c63e  add     [rax+8], rsi
0x10045c642  mov     rax, [rbx+8]
0x10045c646  lea     r14, [rbp+6]
0x10045c64a  mov     ecx, [rbx+10h]
0x10045c64d  mov     r12d, 1
0x10045c653  sub     rcx, [rax+8]
0x10045c657  lfence
0x10045c65a  cmp     rcx, r12
0x10045c65d  jbe     loc_10045C7DB
0x10045c663  mov     rax, [rbx+8]
0x10045c667  mov     r9d, r12d; SourceSize
0x10045c66a  mov     r8, r14; Source
0x10045c66d  mov     edx, r12d; DestinationSize
0x10045c670  mov     rcx, [rax+8]
0x10045c674  add     rcx, [rax]; Destination
0x10045c677  call    cs:__imp_memcpy_s
0x10045c67d  mov     rax, [rbx+8]
0x10045c681  add     [rax+8], r12
0x10045c685  movzx   ecx, byte ptr [r14]
0x10045c689  cmp     ecx, 6Ch ; 'l'
0x10045c68c  ja      loc_10045CB9B
0x10045c692  jz      loc_10045C8B1
0x10045c698  cmp     ecx, 2Ah ; '*'
0x10045c69b  ja      loc_10045C885
0x10045c6a1  jz      short loc_10045C6D3
0x10045c6a3  sub     ecx, 22h ; '"'
0x10045c6a6  jz      loc_10045C81F
0x10045c6ac  sub     ecx, r12d
0x10045c6af  jz      loc_10045C945
0x10045c6b5  sub     ecx, r12d
0x10045c6b8  jz      loc_10045CC5F
0x10045c6be  sub     ecx, esi
0x10045c6c0  jz      loc_10045CC5F
0x10045c6c6  sub     ecx, esi
0x10045c6c8  jz      short loc_10045C70D
0x10045c6ca  cmp     ecx, r12d
0x10045c6cd  jnz     loc_10045CCEB
0x10045c6d3  mov     rax, [rbx+8]
0x10045c6d7  mov     ecx, [rbx+10h]
0x10045c6da  sub     rcx, [rax+8]
0x10045c6de  lfence
0x10045c6e1  cmp     rcx, r12
0x10045c6e4  jbe     loc_10045CA87
0x10045c6ea  lea     r8, [rbp+8]; Source
0x10045c6ee  mov     rax, [rbx+8]
0x10045c6f2  mov     r9, r12; SourceSize
0x10045c6f5  mov     rdx, r12; DestinationSize
0x10045c6f8  mov     rcx, [rax+8]
0x10045c6fc  add     rcx, [rax]; Destination
0x10045c6ff  call    cs:__imp_memcpy_s
0x10045c705  mov     rax, [rbx+8]
0x10045c709  add     [rax+8], r12
0x10045c70d  mov     rcx, [rbx+8]
0x10045c711  mov     eax, [rbx+10h]
0x10045c714  mov     rdx, [rcx+8]
0x10045c718  sub     rax, rdx
0x10045c71b  cmp     rax, r12
0x10045c71e  jbe     loc_10045D59B
0x10045c724  mov     rcx, [rcx]
0x10045c727  lea     r8, dword_10058E8F4; Source
0x10045c72e  add     rcx, rdx; Destination
0x10045c731  mov     r9, r12; SourceSize
0x10045c734  mov     rdx, r12; DestinationSize
0x10045c737  call    cs:__imp_memcpy_s
0x10045c73d  mov     rax, [rbx+8]
0x10045c741  mov     edi, r13d
0x10045c744  add     [rax+8], r12
0x10045c748  jmp     loc_10045D5E3
0x10045c74d  mov     rcx, [rbx]; this
0x10045c750  mov     r9, rbp; unsigned __int8 *
0x10045c753  mov     eax, [r15]
0x10045c756  mov     r8, rdi; unsigned __int64
0x10045c759  mov     [rsp+68h+var_38], r13d; int
0x10045c75e  mov     [rsp+68h+var_40], eax; unsigned int
0x10045c762  mov     rdx, [rcx+70h]; void *
0x10045c766  mov     [rsp+68h+var_48], 3; char
0x10045c76b  call    ?QueuePacket@BATCHCTX@@AEAAJPEAX_KPEBEEKH@Z; BATCHCTX::QueuePacket(void *,unsigned __int64,uchar const *,uchar,ulong,int)
0x10045c770  mov     edi, eax
0x10045c772  test    eax, eax
0x10045c774  jns     loc_10045C604
0x10045c77a  mov     esi, 2
0x10045c77f  test    byte ptr cs:_bidGblFlags, sil
0x10045c786  jz      loc_10045D5E3
0x10045c78c  mov     edx, 8A409h
0x10045c791  jmp     loc_10045D5D6
0x10045c796  mov     rcx, [rbx]; this
0x10045c799  lea     r9, [rbp+4]; unsigned __int8 *
0x10045c79d  mov     eax, [r15]
0x10045c7a0  mov     r8, rsi; unsigned __int64
0x10045c7a3  mov     [rsp+68h+var_38], r13d; int
0x10045c7a8  mov     [rsp+68h+var_40], eax; unsigned int
0x10045c7ac  mov     rdx, [rcx+70h]; void *
0x10045c7b0  mov     [rsp+68h+var_48], 3; char
0x10045c7b5  call    ?QueuePacket@BATCHCTX@@AEAAJPEAX_KPEBEEKH@Z; BATCHCTX::QueuePacket(void *,unsigned __int64,uchar const *,uchar,ulong,int)
0x10045c7ba  mov     edi, eax
0x10045c7bc  test    eax, eax
0x10045c7be  jns     loc_10045C642
0x10045c7c4  test    byte ptr cs:_bidGblFlags, sil
0x10045c7cb  jz      loc_10045D5E3
0x10045c7d1  mov     edx, 8B409h
0x10045c7d6  jmp     loc_10045D5D6
0x10045c7db  mov     rcx, [rbx]; this
0x10045c7de  mov     r9, r14; unsigned __int8 *
0x10045c7e1  mov     eax, [r15]
0x10045c7e4  mov     r8, r12; unsigned __int64
0x10045c7e7  mov     [rsp+68h+var_38], r13d; int
0x10045c7ec  mov     [rsp+68h+var_40], eax; unsigned int
0x10045c7f0  mov     rdx, [rcx+70h]; void *
0x10045c7f4  mov     [rsp+68h+var_48], 3; char
0x10045c7f9  call    ?QueuePacket@BATCHCTX@@AEAAJPEAX_KPEBEEKH@Z; BATCHCTX::QueuePacket(void *,unsigned __int64,uchar const *,uchar,ulong,int)
0x10045c7fe  mov     edi, eax
0x10045c800  test    eax, eax
0x10045c802  jns     loc_10045C685
0x10045c808  test    byte ptr cs:_bidGblFlags, sil
0x10045c80f  jz      loc_10045D5E3
0x10045c815  mov     edx, 8C409h
0x10045c81a  jmp     loc_10045D5D6
0x10045c81f  mov     rax, [rbx+8]
0x10045c823  mov     edi, 4
0x10045c828  mov     ecx, [rbx+10h]
0x10045c82b  sub     rcx, [rax+8]
0x10045c82f  lfence
0x10045c832  cmp     rcx, rdi
0x10045c835  jbe     short loc_10045C840
0x10045c837  lea     r8, [rbp+8]
0x10045c83b  jmp     loc_10045D4FB
0x10045c840  mov     rcx, [rbx]; this
0x10045c843  lea     r9, [rbp+8]; unsigned __int8 *
0x10045c847  mov     eax, [r15]
0x10045c84a  mov     r8, rdi; unsigned __int64
0x10045c84d  mov     [rsp+68h+var_38], r13d; int
0x10045c852  mov     [rsp+68h+var_40], eax; unsigned int
0x10045c856  mov     rdx, [rcx+70h]; void *
0x10045c85a  mov     [rsp+68h+var_48], 3; char
0x10045c85f  call    ?QueuePacket@BATCHCTX@@AEAAJPEAX_KPEBEEKH@Z; BATCHCTX::QueuePacket(void *,unsigned __int64,uchar const *,uchar,ulong,int)
0x10045c864  mov     edi, eax
0x10045c866  test    eax, eax
0x10045c868  jns     loc_10045C70D
0x10045c86e  test    byte ptr cs:_bidGblFlags, sil
0x10045c875  jz      loc_10045D5E3
0x10045c87b  mov     edx, 9EC09h
0x10045c880  jmp     loc_10045D5D6
0x10045c885  sub     ecx, 2Bh ; '+'
0x10045c888  jz      loc_10045C6D3
0x10045c88e  sub     ecx, 37h ; '7'
0x10045c891  jz      loc_10045CA26
0x10045c897  sub     ecx, r12d
0x10045c89a  jz      loc_10045C945
0x10045c8a0  sub     ecx, 5
0x10045c8a3  jz      loc_10045CC5F
0x10045c8a9  cmp     ecx, esi
0x10045c8ab  jnz     loc_10045CCEB
0x10045c8b1  mov     rax, [rbx+8]
0x10045c8b5  mov     ecx, [rbx+10h]
0x10045c8b8  sub     rcx, [rax+8]
0x10045c8bc  lfence
0x10045c8bf  cmp     rcx, r12
0x10045c8c2  jbe     loc_10045CACC
0x10045c8c8  mov     rax, [rbx+8]
0x10045c8cc  lea     r8, [rbp+8]; Source
0x10045c8d0  mov     r9, r12; SourceSize
0x10045c8d3  mov     rdx, r12; DestinationSize
0x10045c8d6  mov     rcx, [rax+8]
0x10045c8da  add     rcx, [rax]; Destination
0x10045c8dd  call    cs:__imp_memcpy_s
0x10045c8e3  mov     rax, [rbx+8]
0x10045c8e7  add     [rax+8], r12
0x10045c8eb  mov     rax, [rbx+8]
0x10045c8ef  mov     ecx, [rbx+10h]
0x10045c8f2  sub     rcx, [rax+8]
0x10045c8f6  lfence
0x10045c8f9  cmp     rcx, r12
0x10045c8fc  jbe     loc_10045CB11
0x10045c902  mov     rax, [rbx+8]
0x10045c906  lea     r8, [rbp+9]; Source
0x10045c90a  mov     r9, r12; SourceSize
0x10045c90d  mov     rdx, r12; DestinationSize
0x10045c910  mov     rcx, [rax+8]
0x10045c914  add     rcx, [rax]; Destination
0x10045c917  call    cs:__imp_memcpy_s
0x10045c91d  mov     rax, [rbx+8]
0x10045c921  add     [rax+8], r12
0x10045c925  mov     rax, [rbx+8]
0x10045c929  mov     ecx, [rbx+10h]
0x10045c92c  sub     rcx, [rax+8]
0x10045c930  lfence
0x10045c933  cmp     rcx, r12
0x10045c936  jbe     loc_10045CB56
0x10045c93c  lea     r8, [rbp+0Ah]
0x10045c940  jmp     loc_10045C6EE
0x10045c945  mov     rax, [rbx+8]
0x10045c949  mov     edi, 4
0x10045c94e  mov     ecx, [rbx+10h]
0x10045c951  sub     rcx, [rax+8]
0x10045c955  lfence
0x10045c958  cmp     rcx, rdi
0x10045c95b  jbe     short loc_10045C9A0
0x10045c95d  mov     rax, [rbx+8]
0x10045c961  lea     r8, [rbp+8]; Source
0x10045c965  mov     r9d, edi; SourceSize
0x10045c968  mov     edx, edi; DestinationSize
0x10045c96a  mov     rcx, [rax+8]
0x10045c96e  add     rcx, [rax]; Destination
0x10045c971  call    cs:__imp_memcpy_s
0x10045c977  mov     rax, [rbx+8]
0x10045c97b  add     [rax+8], rdi
0x10045c97f  mov     rax, [rbx+8]
0x10045c983  mov     edi, 5
0x10045c988  mov     ecx, [rbx+10h]
0x10045c98b  sub     rcx, [rax+8]
0x10045c98f  lfence
0x10045c992  cmp     rcx, rdi
0x10045c995  jbe     short loc_10045C9E1
0x10045c997  lea     r8, [rbp+0Ch]
0x10045c99b  jmp     loc_10045D4FB
0x10045c9a0  mov     rcx, [rbx]; this
0x10045c9a3  lea     r9, [rbp+8]; unsigned __int8 *
0x10045c9a7  mov     eax, [r15]
0x10045c9aa  mov     r8, rdi; unsigned __int64
0x10045c9ad  mov     [rsp+68h+var_38], r13d; int
0x10045c9b2  mov     [rsp+68h+var_40], eax; unsigned int
0x10045c9b6  mov     rdx, [rcx+70h]; void *
0x10045c9ba  mov     [rsp+68h+var_48], 3; char
0x10045c9bf  call    ?QueuePacket@BATCHCTX@@AEAAJPEAX_KPEBEEKH@Z; BATCHCTX::QueuePacket(void *,unsigned __int64,uchar const *,uchar,ulong,int)
0x10045c9c4  mov     edi, eax
0x10045c9c6  test    eax, eax
0x10045c9c8  jns     short loc_10045C97F
0x10045c9ca  test    byte ptr cs:_bidGblFlags, sil
0x10045c9d1  jz      loc_10045D5E3
0x10045c9d7  mov     edx, 0A0C09h
0x10045c9dc  jmp     loc_10045D5D6
0x10045c9e1  mov     rcx, [rbx]; this
0x10045c9e4  lea     r9, [rbp+0Ch]; unsigned __int8 *
0x10045c9e8  mov     eax, [r15]
0x10045c9eb  mov     r8, rdi; unsigned __int64
0x10045c9ee  mov     [rsp+68h+var_38], r13d; int
0x10045c9f3  mov     [rsp+68h+var_40], eax; unsigned int
0x10045c9f7  mov     rdx, [rcx+70h]; void *
0x10045c9fb  mov     [rsp+68h+var_48], 3; char
0x10045ca00  call    ?QueuePacket@BATCHCTX@@AEAAJPEAX_KPEBEEKH@Z; BATCHCTX::QueuePacket(void *,unsigned __int64,uchar const *,uchar,ulong,int)
0x10045ca05  mov     edi, eax
0x10045ca07  test    eax, eax
0x10045ca09  jns     loc_10045C70D
0x10045ca0f  test    byte ptr cs:_bidGblFlags, sil
0x10045ca16  jz      loc_10045D5E3
0x10045ca1c  mov     edx, 0A2009h
0x10045ca21  jmp     loc_10045D5D6
0x10045ca26  mov     rax, [rbx+8]
0x10045ca2a  mov     edi, 4
0x10045ca2f  mov     ecx, [rbx+10h]
0x10045ca32  sub     rcx, [rax+8]
0x10045ca36  lfence
0x10045ca39  cmp     rcx, rdi
0x10045ca3c  ja      loc_10045C837
0x10045ca42  mov     rcx, [rbx]; this
0x10045ca45  lea     r9, [rbp+8]; unsigned __int8 *
0x10045ca49  mov     eax, [r15]
  ... truncated ...
```
