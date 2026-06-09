# CImpIIndexDefinition::CreateIndex(tagDBID *,tagDBID *,unsigned __int64,tagDBINDEXCOLUMNDESC const * const,ulong,tagDBPROPSET * const,tagDBID * *)

- ea: `0x18011c390`
- end: `0x18011d23a`
- name: `?CreateIndex@CImpIIndexDefinition@@UEAAJPEAUtagDBID@@0_KQEBUtagDBINDEXCOLUMNDESC@@KQEAUtagDBPROPSET@@PEAPEAU2@@Z`
- size: `3754`
- prototype: `__int64 __fastcall(CImpIIndexDefinition *__hidden this, struct tagDBID *, struct tagDBID *, unsigned __int64, const struct tagDBINDEXCOLUMNDESC *const, unsigned int, struct tagDBPROPSET *const, struct tagDBID **)`
- caller_count: `0`
- callee_count: `25`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180001f70`
- `0x180002ef0`
- `0x180003030`
- `0x1800030c0`
- `0x180003824`
- `0x180003d80`
- `0x180008c80`
- `0x180009340`
- `0x18002f310`
- `0x1800833f0`
- `0x180084ec0`
- `0x180084ef0`
- `0x180086810`
- `0x1800af320`
- `0x1800fd490`
- `0x18011c390`
- `0x1801336f4`
- `0x180133bcc`
- `0x180134658`
- `0x180134738`
- `0x18013b6c8`
- `0x18013e0fc`
- `0x18013f6e0`
- `0x18013f7d0`
- `0x1801ad6a0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18011cf9a`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18011cf9a`
- `api-ms-win-crt-convert-l1-1-0!_ltow_s` at `0x18011cd3c`
- `api-ms-win-crt-convert-l1-1-0!_ltow_s` at `0x18011cd3c`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18011c4a2`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18011c4a2`

## string_xrefs

- `0x18011c95a`: `create`
- `0x18011c9ad`: ` primary xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CImpIIndexDefinition::CreateIndex(
        CImpIIndexDefinition *this,
        struct tagDBID *a2,
        struct tagDBID *a3,
        unsigned __int64 a4,
        const struct tagDBINDEXCOLUMNDESC *const a5,
        unsigned int a6,
        struct tagDBPROPSET *const a7,
        struct tagDBID **a8)
{
  const struct tagDBINDEXCOLUMNDESC *v12; // r15
  __int64 v13; // rax
  CDataSource *v14; // rsi
  __int64 *v15; // rbx
  int v16; // eax
  int v17; // ebx
  LPOLESTR pwszName; // rcx
  unsigned __int64 v19; // rdx
  const wchar_t *v20; // rcx
  unsigned __int64 v21; // rdx
  LPOLESTR v22; // r12
  CUtlProps2 *v23; // rax
  CUtlProps2 *v24; // rsi
  unsigned __int64 v25; // rdi
  int v26; // eax
  int v27; // eax
  char v28; // al
  int v29; // eax
  CExtBaseBuffer *v30; // rax
  LPOLESTR v31; // rdx
  __int64 v32; // r8
  __int64 v33; // r8
  int v34; // eax
  int v35; // eax
  int v36; // eax
  int v37; // eax
  int v38; // eax
  int v39; // eax
  __int64 v40; // r8
  LPOLESTR v41; // rdx
  __int64 v42; // r8
  int v43; // eax
  DBID *pColumnID; // rcx
  const wchar_t *v45; // rcx
  unsigned __int64 v46; // rdx
  LPOLESTR v47; // rdx
  __int64 v48; // r8
  int v49; // eax
  int v50; // eax
  int v51; // ecx
  __int64 v52; // r8
  CCommand *v53; // rax
  CCommand *v54; // rdi
  int v55; // eax
  int v56; // eax
  int v57; // eax
  struct tagDBID *v58; // rax
  unsigned __int64 v59; // rdi
  size_t v60; // rax
  OLECHAR *v61; // rcx
  LPOLESTR v62; // rcx
  unsigned __int64 v63; // rdx
  signed __int64 v64; // r12
  OLECHAR v65; // ax
  LPOLESTR v66; // rax
  int v67; // eax
  CExtBaseBuffer *v68; // rdi
  int v70; // [rsp+68h] [rbp-98h]
  CCommand *v71; // [rsp+70h] [rbp-90h]
  __int64 v72; // [rsp+88h] [rbp-78h]
  CExtBaseBuffer *v73; // [rsp+90h] [rbp-70h] BYREF
  CImpIIndexDefinition *v74; // [rsp+98h] [rbp-68h]
  __int64 v75; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t Buffer[8]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v77; // [rsp+B8h] [rbp-48h]
  wchar_t v78[136]; // [rsp+C0h] [rbp-40h] BYREF

  v74 = this;
  v12 = a5;
  v75 = -1;
  if ( (bidGblFlags & 4) != 0 && off_180266630[0] )
    bidScopeEnterW(&v75, off_180266630[0], *(unsigned int *)(*((_QWORD *)this + 1) + 52LL), a2);
  v70 = 0;
  v13 = *((_QWORD *)this + 1);
  v14 = *(CDataSource **)(v13 + 832);
  v71 = 0;
  v73 = 0;
  v15 = (__int64 *)(v13 + 24);
  if ( v13 == -24 )
  {
    v72 = 0;
  }
  else
  {
    if ( *v15 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)(*v15 + 32) + 8LL))(*v15 + 32);
    v72 = *v15;
  }
  SetErrorInfo(0, 0);
  if ( a8 )
    *a8 = 0;
  if ( !a2 || !a3 && !a8 || !a4 || !a5 )
  {
    if ( (bidGblFlags & 2) != 0 )
      v17 = bidTraceHR(off_1802605D0[0], 146441, 2147942487LL);
    else
      v17 = -2147024809;
    goto LABEL_184;
  }
  v16 = CUtlProps2::SetPropertiesArgChk(a6, a7);
  v17 = v16;
  if ( v16 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      _mm_lfence();
      bidTraceHR(off_1802605D0[0], 151561, (unsigned int)v16);
    }
    goto LABEL_184;
  }
  if ( a2->eKind != 2 )
    goto LABEL_178;
  pwszName = a2->uName.pwszName;
  if ( !pwszName )
    goto LABEL_178;
  if ( !*pwszName )
    goto LABEL_178;
  v19 = -1;
  do
    ++v19;
  while ( pwszName[v19] );
  if ( !(unsigned int)FIsValidQualifiedName(pwszName, v19, 3u, 0) )
  {
LABEL_178:
    if ( (bidGblFlags & 2) != 0 )
      v17 = bidTraceHR(off_1802605D0[0], 162825, 2147749431LL);
    else
      v17 = -2147217865;
    goto LABEL_184;
  }
  if ( a3 )
  {
    if ( a3->eKind == 2 )
    {
      v20 = a3->uName.pwszName;
      if ( v20 )
      {
        if ( *v20 )
        {
          v21 = -1;
          do
            ++v21;
          while ( v20[v21] );
          if ( FIsValidIdentifier(v20, v21) )
          {
            v22 = a3->uName.pwszName;
            goto LABEL_37;
          }
        }
      }
    }
    if ( (bidGblFlags & 2) != 0 )
      v17 = bidTraceHR(off_1802605D0[0], 177161, 2147749490LL);
    else
      v17 = -2147217806;
LABEL_184:
    v24 = 0;
    goto LABEL_185;
  }
  v22 = v78;
  CDataSource::CreateUniqueIdentifier(v14, v78, 0x81u, 0);
LABEL_37:
  v23 = (CUtlProps2 *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)g_pMO + 88LL))(
                        g_pMO,
                        576);
  v24 = v23;
  if ( v23 )
  {
    CUtlProps2::CUtlProps2(v23, 0);
    *(_QWORD *)v24 = &CIndexProps::`vftable';
    v25 = 0;
  }
  else
  {
    v25 = 0;
    v24 = 0;
  }
  if ( !v24 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      v17 = bidTraceHR(off_1802605D0[0], 193545, 2147942414LL);
      goto LABEL_185;
    }
    goto LABEL_43;
  }
  v26 = (*(__int64 (__fastcall **)(CUtlProps2 *, _QWORD))(*(_QWORD *)v24 + 16LL))(v24, 0);
  v17 = v26;
  if ( v26 < 0 )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_187;
    _mm_lfence();
    bidTraceHR(off_1802605D0[0], 199689, (unsigned int)v26);
    goto LABEL_185;
  }
  _mm_lfence();
  v27 = CIndexProps::SetProperties(v24, a6, a7);
  v17 = v27;
  if ( v27 < 0 )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_187;
    _mm_lfence();
    bidTraceHR(off_1802605D0[0], 203785, (unsigned int)v27);
    goto LABEL_185;
  }
  _mm_lfence();
  v70 = v27;
  if ( *(_WORD *)(*(_QWORD *)(*((_QWORD *)v24 + 6) + 40LL) + 40LL) != 0xFFFF || a4 == 1 )
  {
    v30 = (CExtBaseBuffer *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)g_pMO + 88LL))(
                              g_pMO,
                              48);
    if ( !v30
      || (*(_QWORD *)v30 = 0,
          *((_QWORD *)v30 + 1) = 0,
          *((_QWORD *)v30 + 2) = 0,
          *((_QWORD *)v30 + 3) = 0,
          *((_QWORD *)v30 + 4) = 0,
          *((_QWORD *)v30 + 5) = 0,
          v73 = v30,
          !(unsigned int)CExtByteBuffer::FInit(v30, 0x400u, 0x400u)) )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        v17 = bidTraceHR(off_1802605D0[0], 228361, 2147942414LL);
        goto LABEL_185;
      }
LABEL_43:
      v17 = -2147024882;
      goto LABEL_185;
    }
    _mm_lfence();
    if ( *(_WORD *)(*(_QWORD *)(*((_QWORD *)v24 + 6) + 16LL) + 152LL) == 0xFFFF )
    {
      v17 = CExtByteBuffer::WriteIntoExtBuffer(v73, L"alter table ", 0x18u);
      if ( v17 < 0 )
        goto LABEL_185;
      v31 = a2->uName.pwszName;
      v32 = -1;
      do
        ++v32;
      while ( v31[v32] );
      v17 = CExtByteBuffer::WriteIntoExtBuffer(v73, v31, 2 * v32);
      if ( v17 < 0 )
        goto LABEL_185;
      v17 = CExtByteBuffer::WriteIntoExtBuffer(v73, L" add constraint ", 0x20u);
      if ( v17 < 0 )
        goto LABEL_185;
      v33 = -1;
      do
        ++v33;
      while ( v22[v33] );
      v17 = CExtByteBuffer::WriteIntoExtBuffer(v73, v22, 2 * v33);
      if ( v17 < 0 )
        goto LABEL_185;
      v17 = CExtByteBuffer::WriteIntoExtBuffer(v73, L" primary key ", 0x1Au);
      if ( v17 < 0 )
        goto LABEL_185;
      _mm_lfence();
      if ( *(_WORD *)(*(_QWORD *)(*((_QWORD *)v24 + 6) + 16LL) + 40LL) == 0xFFFF )
      {
        v34 = CExtByteBuffer::WriteIntoExtBuffer(v73, L" clustered", 0x14u);
        v17 = v34;
        if ( v34 < 0 )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_187;
          _mm_lfence();
          bidTraceHR(off_1802605D0[0], 252937, (unsigned int)v34);
          goto LABEL_185;
        }
      }
      else
      {
        v35 = CExtByteBuffer::WriteIntoExtBuffer(v73, L" nonclustered", 0x1Au);
        v17 = v35;
        if ( v35 < 0 )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_187;
          _mm_lfence();
          bidTraceHR(off_1802605D0[0], 259081, (unsigned int)v35);
          goto LABEL_185;
        }
      }
    }
    else
    {
      v36 = CExtByteBuffer::WriteIntoExtBuffer(v73, L"create", 0xCu);
      v17 = v36;
      if ( v36 < 0 )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_187;
        _mm_lfence();
        bidTraceHR(off_1802605D0[0], 266249, (unsigned int)v36);
        goto LABEL_185;
      }
      _mm_lfence();
      if ( *(_WORD *)(*(_QWORD *)(*((_QWORD *)v24 + 6) + 40LL) + 40LL) == 0xFFFF )
      {
        v37 = CExtByteBuffer::WriteIntoExtBuffer(v73, L" primary xml", 0x18u);
        v17 = v37;
        if ( v37 < 0 )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_187;
          _mm_lfence();
          bidTraceHR(off_1802605D0[0], 274441, (unsigned int)v37);
          goto LABEL_185;
        }
      }
      else
      {
        _mm_lfence();
        if ( *(_WORD *)(*(_QWORD *)(*((_QWORD *)v24 + 6) + 16LL) + 208LL) == 0xFFFF )
        {
          v38 = CExtByteBuffer::WriteIntoExtBuffer(v73, L" unique", 0xEu);
          v17 = v38;
          if ( v38 < 0 )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_187;
            _mm_lfence();
            bidTraceHR(off_1802605D0[0], 283657, (unsigned int)v38);
            goto LABEL_185;
          }
        }
        _mm_lfence();
        if ( *(_WORD *)(*(_QWORD *)(*((_QWORD *)v24 + 6) + 16LL) + 40LL) == 0xFFFF )
        {
          v39 = CExtByteBuffer::WriteIntoExtBuffer(v73, L" clustered", 0x14u);
          v17 = v39;
          if ( v39 < 0 )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_187;
            _mm_lfence();
            bidTraceHR(off_1802605D0[0], 291849, (unsigned int)v39);
            goto LABEL_185;
          }
        }
      }
      v17 = CExtByteBuffer::WriteIntoExtBuffer(v73, L" index ", 0xEu);
      if ( v17 < 0 )
        goto LABEL_185;
      v40 = -1;
      do
        ++v40;
      while ( v22[v40] );
      v17 = CExtByteBuffer::WriteIntoExtBuffer(v73, v22, 2 * v40);
      if ( v17 < 0 )
        goto LABEL_185;
      v17 = CExtByteBuffer::WriteIntoExtBuffer(v73, L" on ", 8u);
      if ( v17 < 0 )
        goto LABEL_185;
      v41 = a2->uName.pwszName;
      v42 = -1;
      do
        ++v42;
      while ( v41[v42] );
      v17 = CExtByteBuffer::WriteIntoExtBuffer(v73, v41, 2 * v42);
      if ( v17 < 0 )
        goto LABEL_185;
    }
    v43 = CExtByteBuffer::WriteWCharToExtBuffer(v73, 0x28u);
    v17 = v43;
    if ( v43 < 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_187;
      _mm_lfence();
      bidTraceHR(off_1802605D0[0], 309257, (unsigned int)v43);
      goto LABEL_185;
    }
    do
    {
      if ( v25 )
      {
        v17 = CExtByteBuffer::WriteWCharToExtBuffer(v73, 0x2Cu);
        if ( v17 < 0 )
          goto LABEL_185;
      }
      if ( v12->eIndexColOrder )
      {
        if ( (bidGblFlags & 2) != 0 )
          v17 = bidTraceHR(off_1802605D0[0], 320521, 2147942487LL);
        else
          v17 = -2147024809;
        goto LABEL_185;
      }
      pColumnID = v12->pColumnID;
      if ( !v12->pColumnID )
        goto LABEL_123;
      if ( pColumnID->eKind != 2 )
        goto LABEL_123;
      v45 = pColumnID->uName.pwszName;
      if ( !v45 )
        goto LABEL_123;
      if ( !*v45 )
        goto LABEL_123;
      v46 = -1;
      do
        ++v46;
      while ( v45[v46] );
      if ( !FIsValidIdentifier(v45, v46) )
      {
LABEL_123:
        if ( (bidGblFlags & 2) != 0 )
          v17 = bidTraceHR(off_1802605D0[0], 332809, 2147749477LL);
        else
          v17 = -2147217819;
        goto LABEL_185;
      }
      v47 = v12->pColumnID->uName.pwszName;
      v48 = -1;
      do
        ++v48;
      while ( v47[v48] );
      v49 = CExtByteBuffer::WriteIntoExtBuffer(v73, v47, 2 * v48);
      v17 = v49;
      if ( v49 < 0 )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_187;
        _mm_lfence();
        bidTraceHR(off_1802605D0[0], 339977, (unsigned int)v49);
        goto LABEL_185;
      }
      ++v25;
      ++v12;
    }
    while ( v25 < a4 );
    v50 = CExtByteBuffer::WriteWCharToExtBuffer(v73, 0x29u);
    v17 = v50;
    if ( v50 < 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_187;
      _mm_lfence();
      bidTraceHR(off_1802605D0[0], 344073, (unsigned int)v50);
      goto LABEL_185;
    }
    _mm_lfence();
    v51 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v24 + 6) + 16LL) + 96LL);
    if ( !v51 )
      goto LABEL_138;
    *(_OWORD *)Buffer = 0;
    v77 = 0;
    if ( _ltow_s(v51, Buffer, 0xCu, 10) )
    {
      if ( (bidGblFlags & 2) != 0 )
        v17 = bidTraceHR(off_1802605D0[0], 353289, 2147500037LL);
      else
        v17 = -2147467259;
      goto LABEL_185;
    }
    v17 = CExtByteBuffer::WriteIntoExtBuffer(v73, L" with fillfactor=", 0x22u);
    if ( v17 >= 0 )
    {
      v52 = -1;
      do
        ++v52;
      while ( Buffer[v52] );
      v17 = CExtByteBuffer::WriteIntoExtBuffer(v73, Buffer, 2 * v52);
      if ( v17 >= 0 )
      {
LABEL_138:
        v53 = (CCommand *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)g_pMO + 88LL))(
                            g_pMO,
                            1544);
        if ( v53 )
        {
          v54 = CCommand::CCommand(v53, *((struct CDBSession **)v74 + 1), 0);
          v71 = v54;
        }
        else
        {
          v54 = 0;
          v71 = 0;
        }
        if ( !v54 )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_43;
          v17 = bidTraceHR(off_1802605D0[0], 374793, 2147942414LL);
          goto LABEL_185;
        }
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)v74 + 1) + 40LL) + 8LL))(*(_QWORD *)(*((_QWORD *)v74 + 1) + 40LL));
        (*(void (__fastcall **)(CCommand *))(*(_QWORD *)v54 + 8LL))(v54);
        v55 = CCommand::FInit(v54, 0, 0);
        v17 = v55;
        if ( v55 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            _mm_lfence();
            bidTraceHR(off_1802605D0[0], 384009, (unsigned int)v55);
          }
          goto LABEL_189;
        }
        _mm_lfence();
        *(GUID *)((char *)v54 + 1256) = IID_IIndexDefinition;
        *((_DWORD *)v54 + 372) = 5;
        CCommand::ApplyGeneralTimeout(v54);
        v56 = CCommand::Prepare(v54, 0x40u, &IID_IIndexDefinition, &v73);
        v17 = v56;
        if ( v56 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            _mm_lfence();
            bidTraceHR(off_1802605D0[0], 395273, (unsigned int)v56);
          }
          goto LABEL_189;
        }
        _mm_lfence();
        v57 = CCommand::Execute(v54);
        v17 = v57;
        if ( v57 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            _mm_lfence();
            bidTraceHR(off_1802605D0[0], 399369, (unsigned int)v57);
          }
          goto LABEL_189;
        }
        if ( !a8 )
          goto LABEL_189;
        v58 = (struct tagDBID *)((__int64 (__fastcall *)(LPMALLOC, __int64))g_pIMalloc->lpVtbl->Alloc)(g_pIMalloc, 32);
        *a8 = v58;
        if ( !v58 )
          goto LABEL_165;
        v58->eKind = 2;
        if ( v22 )
        {
          v60 = wcsnlen(v22, 0xFFFFFFFFFFFFFFFFuLL);
          v59 = v60 + 1;
          if ( v60 == -1 )
            goto LABEL_160;
        }
        else
        {
          v59 = 1;
        }
        if ( is_mul_ok(v59, 2u) )
        {
          v61 = (OLECHAR *)((__int64 (__fastcall *)(LPMALLOC, unsigned __int64))g_pIMalloc->lpVtbl->Alloc)(
                             g_pIMalloc,
                             2 * v59);
LABEL_161:
          (*a8)->uName.pwszName = v61;
          v62 = (*a8)->uName.pwszName;
          if ( !v62 )
          {
            ((void (__fastcall *)(LPMALLOC))g_pIMalloc->lpVtbl->Free)(g_pIMalloc);
            *a8 = 0;
LABEL_166:
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_43;
            v17 = bidTraceHR(off_1802605D0[0], 429065, 2147942414LL);
            goto LABEL_185;
          }
          if ( v59 )
          {
            if ( v59 <= 0x7FFFFFFF )
            {
              v63 = 2147483646 - v59;
              v64 = (char *)v22 - (char *)v62;
              do
              {
                if ( !(v63 + v59) )
                  break;
                v65 = *(LPOLESTR)((char *)v62 + v64);
                if ( !v65 )
                  break;
                *v62++ = v65;
                --v59;
              }
              while ( v59 );
              v66 = v62 - 1;
              if ( v59 )
                v66 = v62;
              *v66 = 0;
            }
            else
            {
              *v62 = 0;
            }
          }
LABEL_165:
          if ( *a8 )
            goto LABEL_189;
          goto LABEL_166;
        }
LABEL_160:
        v61 = 0;
        goto LABEL_161;
      }
    }
LABEL_185:
    if ( (bidGblFlags & 2) != 0 )
    {
      v67 = bidTraceHR(off_1802605D0[0], 444425, (unsigned int)v17);
LABEL_188:
      CError::PostHResult(g_pCError, v67, &IID_IIndexDefinition);
      goto LABEL_189;
    }
LABEL_187:
    v67 = v17;
    goto LABEL_188;
  }
  v28 = bidGblFlags;
  if ( (bidGblFlags & 2) != 0 )
  {
    v17 = bidTraceHR(off_1802605D0[0], 215049, 2147500037LL);
    v28 = bidGblFlags;
  }
  else
  {
    v17 = -2147467259;
  }
  if ( (v28 & 2) != 0 )
    v29 = bidTraceHR(off_1802605D0[0], 216073, (unsigned int)v17);
  else
    v29 = v17;
  CError::PostError(g_pCError, v29, &IID_IIndexDefinition, 0x9F19u, 0);
LABEL_189:
  v68 = v73;
  if ( v73 )
  {
    CExtBaseBuffer::~CExtBaseBuffer(v73);
    operator delete(v68, 0x30u);
    v73 = 0;
  }
  if ( v71 )
    (*(void (__fastcall **)(CCommand *))(*(_QWORD *)v71 + 16LL))(v71);
  if ( v24 )
    (*(void (__fastcall **)(CUtlProps2 *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 1);
  if ( !v17 )
    v17 = v70;
  if ( (bidGblFlags & 2) != 0 && off_180263890[0] )
    bidTraceW(off_1802605D0[0], 440320, off_180263890[0], (unsigned int)v17);
  if ( v72 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v72 + 32) + 24LL))(v72 + 32);
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v75);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x18011c390  push    rbp
0x18011c392  push    rbx
0x18011c393  push    rsi
0x18011c394  push    rdi
0x18011c395  push    r12
0x18011c397  push    r13
0x18011c399  push    r14
0x18011c39b  push    r15
0x18011c39d  lea     rbp, [rsp-0E8h]
0x18011c3a5  sub     rsp, 1E8h
0x18011c3ac  mov     rax, cs:__security_cookie
0x18011c3b3  xor     rax, rsp
0x18011c3b6  mov     [rbp+120h+var_50], rax
0x18011c3bd  mov     r13, r9
0x18011c3c0  mov     rdi, r8
0x18011c3c3  mov     r14, rdx
0x18011c3c6  mov     rbx, rcx
0x18011c3c9  mov     [rbp+120h+var_188], rcx
0x18011c3cd  mov     r15, [rbp+120h+arg_20]
0x18011c3d4  mov     rcx, [rbp+120h+arg_30]
0x18011c3db  mov     [rsp+220h+var_1A8], rcx
0x18011c3e0  mov     r12, [rbp+120h+arg_38]
0x18011c3e7  mov     [rbp+120h+var_1A0], r12
0x18011c3eb  mov     [rbp+120h+var_180], 0FFFFFFFFFFFFFFFFh
0x18011c3f3  test    byte ptr cs:_bidGblFlags, 4
0x18011c3fa  jz      short loc_18011C450
0x18011c3fc  mov     rax, cs:off_180266630; "<IIndexDefinition::CreateIndex|OLEDB|AP"...
0x18011c403  test    rax, rax
0x18011c406  jz      short loc_18011C450
0x18011c408  mov     r8, [rbx+8]
0x18011c40c  mov     [rsp+220h+var_1C8], r12
0x18011c411  mov     [rsp+220h+var_1D0], rcx
0x18011c416  mov     [rsp+220h+var_1D8], r9
0x18011c41b  mov     eax, [rbp+120h+arg_28]
0x18011c421  mov     [rsp+220h+var_1E0], eax
0x18011c425  mov     [rsp+220h+var_1E8], r15
0x18011c42a  mov     [rsp+220h+var_1F0], r9
0x18011c42f  mov     [rsp+220h+var_1F8], r9
0x18011c434  mov     [rsp+220h+var_200], rdi
0x18011c439  mov     r9, rdx
0x18011c43c  mov     r8d, [r8+34h]
0x18011c440  mov     rdx, cs:off_180266630; "<IIndexDefinition::CreateIndex|OLEDB|AP"...
0x18011c447  lea     rcx, [rbp+120h+var_180]
0x18011c44b  call    _bidScopeEnterW
0x18011c450  xor     ecx, ecx
0x18011c452  mov     [rsp+220h+var_1B8], ecx
0x18011c456  mov     rax, [rbx+8]
0x18011c45a  mov     rsi, [rax+340h]
0x18011c461  mov     [rsp+220h+var_1B0], rcx
0x18011c466  mov     [rbp+120h+var_190], rcx
0x18011c46a  mov     [rsp+220h+var_1C0], rcx
0x18011c46f  lea     rbx, [rax+18h]
0x18011c473  test    rbx, rbx
0x18011c476  jz      short loc_18011C49A
0x18011c478  mov     rcx, [rbx]
0x18011c47b  test    rcx, rcx
0x18011c47e  jz      short loc_18011C491
0x18011c480  add     rcx, 20h ; ' '
0x18011c484  mov     rax, [rcx]
0x18011c487  mov     rax, [rax+8]
0x18011c48b  call    cs:__guard_dispatch_icall_fptr
0x18011c491  mov     rax, [rbx]
0x18011c494  mov     [rbp+120h+var_198], rax
0x18011c498  jmp     short loc_18011C49E
0x18011c49a  mov     [rbp+120h+var_198], rcx
0x18011c49e  xor     edx, edx; perrinfo
0x18011c4a0  xor     ecx, ecx; dwReserved
0x18011c4a2  call    cs:__imp_SetErrorInfo
0x18011c4a8  test    r12, r12
0x18011c4ab  jz      short loc_18011C4B5
0x18011c4ad  mov     qword ptr [r12], 0
0x18011c4b5  test    r14, r14
0x18011c4b8  jz      loc_18011D0E2
0x18011c4be  test    rdi, rdi
0x18011c4c1  jnz     short loc_18011C4CC
0x18011c4c3  test    r12, r12
0x18011c4c6  jz      loc_18011D0E2
0x18011c4cc  test    r13, r13
0x18011c4cf  jz      loc_18011D0E2
0x18011c4d5  test    r15, r15
0x18011c4d8  jz      loc_18011D0E2
0x18011c4de  mov     rdx, [rsp+220h+var_1A8]; struct tagDBPROPSET *
0x18011c4e3  mov     ecx, [rbp+120h+arg_28]; unsigned int
0x18011c4e9  call    ?SetPropertiesArgChk@CUtlProps2@@SAJKQEBUtagDBPROPSET@@@Z; CUtlProps2::SetPropertiesArgChk(ulong,tagDBPROPSET const * const)
0x18011c4ee  mov     ebx, eax
0x18011c4f0  test    eax, eax
0x18011c4f2  jns     short loc_18011C51D
0x18011c4f4  test    byte ptr cs:_bidGblFlags, 2
0x18011c4fb  jz      loc_18011D10B
0x18011c501  lfence
0x18011c504  mov     r8d, eax
0x18011c507  mov     edx, 25009h
0x18011c50c  mov     rcx, cs:off_1802605D0; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18011c513  call    _bidTraceHR
0x18011c518  jmp     loc_18011D10B
0x18011c51d  cmp     dword ptr [r14+10h], 2
0x18011c522  jnz     loc_18011D0B7
0x18011c528  mov     rcx, [r14+18h]; wchar_t *
0x18011c52c  test    rcx, rcx
0x18011c52f  jz      loc_18011D0B7
0x18011c535  cmp     word ptr [rcx], 0
0x18011c539  jz      loc_18011D0B7
0x18011c53f  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x18011c546  inc     rdx; unsigned __int64
0x18011c549  cmp     word ptr [rcx+rdx*2], 0
0x18011c54e  jnz     short loc_18011C546
0x18011c550  xor     r9d, r9d; unsigned __int64 *
0x18011c553  mov     r8d, 3; unsigned __int64
0x18011c559  call    ?FIsValidQualifiedName@@YAHPEB_W_K1PEA_K@Z; FIsValidQualifiedName(wchar_t const *,unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18011c55e  test    eax, eax
0x18011c560  jz      loc_18011D0B7
0x18011c566  test    rdi, rdi
0x18011c569  jz      short loc_18011C5DA
0x18011c56b  cmp     dword ptr [rdi+10h], 2
0x18011c56f  jnz     short loc_18011C5A9
0x18011c571  mov     rcx, [rdi+18h]; wchar_t *
0x18011c575  test    rcx, rcx
0x18011c578  jz      short loc_18011C5A9
0x18011c57a  cmp     word ptr [rcx], 0
0x18011c57e  jz      short loc_18011C5A9
0x18011c580  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x18011c587  nop     word ptr [rax+rax+00000000h]
0x18011c590  inc     rdx; unsigned __int64
0x18011c593  cmp     word ptr [rcx+rdx*2], 0
0x18011c598  jnz     short loc_18011C590
0x18011c59a  call    ?FIsValidIdentifier@@YAHPEB_W_K@Z; FIsValidIdentifier(wchar_t const *,unsigned __int64)
0x18011c59f  test    eax, eax
0x18011c5a1  jz      short loc_18011C5A9
0x18011c5a3  mov     r12, [rdi+18h]
0x18011c5a7  jmp     short loc_18011C5F4
0x18011c5a9  test    byte ptr cs:_bidGblFlags, 2
0x18011c5b0  jz      short loc_18011C5D0
0x18011c5b2  mov     edx, 2B409h
0x18011c5b7  mov     r8d, 80040E72h
0x18011c5bd  mov     rcx, cs:off_1802605D0; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18011c5c4  call    _bidTraceHR
0x18011c5c9  mov     ebx, eax
0x18011c5cb  jmp     loc_18011D10B
0x18011c5d0  mov     ebx, 80040E72h
0x18011c5d5  jmp     loc_18011D10B
0x18011c5da  lea     r12, [rbp+120h+var_160]
0x18011c5de  xor     r9d, r9d; int
0x18011c5e1  mov     r8d, 81h; unsigned __int64
0x18011c5e7  lea     rdx, [rbp+120h+var_160]; wchar_t *
0x18011c5eb  mov     rcx, rsi; this
0x18011c5ee  call    ?CreateUniqueIdentifier@CDataSource@@QEAAXPEA_W_KH@Z; CDataSource::CreateUniqueIdentifier(wchar_t *,unsigned __int64,int)
0x18011c5f3  nop
0x18011c5f4  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x18011c5fb  mov     rax, [rcx]
0x18011c5fe  mov     edx, 240h
0x18011c603  mov     rax, [rax+58h]
0x18011c607  call    cs:__guard_dispatch_icall_fptr
0x18011c60d  mov     rsi, rax
0x18011c610  mov     [rsp+220h+var_1C0], rax
0x18011c615  test    rax, rax
0x18011c618  jz      short loc_18011C632
0x18011c61a  xor     edx, edx; unsigned int
0x18011c61c  mov     rcx, rax; this
0x18011c61f  call    ??0CUtlProps2@@QEAA@K@Z; CUtlProps2::CUtlProps2(ulong)
0x18011c624  lea     rax, ??_7CIndexProps@@6B@; const CIndexProps::`vftable'
0x18011c62b  mov     [rsi], rax
0x18011c62e  xor     edi, edi
0x18011c630  jmp     short loc_18011C636
0x18011c632  xor     edi, edi
0x18011c634  mov     esi, edi
0x18011c636  test    rsi, rsi
0x18011c639  jnz     short loc_18011C66C
0x18011c63b  test    byte ptr cs:_bidGblFlags, 2
0x18011c642  jz      short loc_18011C662
0x18011c644  mov     edx, 2F409h
0x18011c649  mov     r8d, 8007000Eh
0x18011c64f  mov     rcx, cs:off_1802605D0; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18011c656  call    _bidTraceHR
0x18011c65b  mov     ebx, eax
0x18011c65d  jmp     loc_18011D110
0x18011c662  mov     ebx, 8007000Eh
0x18011c667  jmp     loc_18011D110
0x18011c66c  mov     rax, [rsi]
0x18011c66f  xor     edx, edx
0x18011c671  mov     rcx, rsi
0x18011c674  mov     rax, [rax+10h]
0x18011c678  call    cs:__guard_dispatch_icall_fptr
0x18011c67e  mov     ebx, eax
0x18011c680  test    eax, eax
0x18011c682  jns     short loc_18011C6AD
0x18011c684  test    byte ptr cs:_bidGblFlags, 2
0x18011c68b  jz      loc_18011D12F
0x18011c691  lfence
0x18011c694  mov     r8d, eax
0x18011c697  mov     edx, 30C09h
0x18011c69c  mov     rcx, cs:off_1802605D0; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18011c6a3  call    _bidTraceHR
0x18011c6a8  jmp     loc_18011D110
0x18011c6ad  lfence
0x18011c6b0  mov     r8, [rsp+220h+var_1A8]; struct tagDBPROPSET *
0x18011c6b5  mov     edx, [rbp+120h+arg_28]; unsigned int
0x18011c6bb  mov     rcx, rsi; this
0x18011c6be  call    ?SetProperties@CIndexProps@@QEAAJKQEBUtagDBPROPSET@@@Z; CIndexProps::SetProperties(ulong,tagDBPROPSET const * const)
0x18011c6c3  mov     ebx, eax
0x18011c6c5  test    eax, eax
0x18011c6c7  jns     short loc_18011C6F2
0x18011c6c9  test    byte ptr cs:_bidGblFlags, 2
0x18011c6d0  jz      loc_18011D12F
0x18011c6d6  lfence
0x18011c6d9  mov     r8d, eax
0x18011c6dc  mov     edx, 31C09h
0x18011c6e1  mov     rcx, cs:off_1802605D0; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18011c6e8  call    _bidTraceHR
0x18011c6ed  jmp     loc_18011D110
0x18011c6f2  lfence
0x18011c6f5  mov     [rsp+220h+var_1B8], eax
0x18011c6f9  mov     rax, [rsi+30h]
0x18011c6fd  mov     rcx, [rax+28h]
0x18011c701  cmp     word ptr [rcx+28h], 0FFFFh
0x18011c706  jnz     short loc_18011C77F
0x18011c708  cmp     r13, 1
0x18011c70c  jz      short loc_18011C77F
0x18011c70e  mov     eax, cs:_bidGblFlags
0x18011c714  test    al, 2
0x18011c716  jz      short loc_18011C739
0x18011c718  mov     edx, 34809h
0x18011c71d  mov     r8d, 80004005h
0x18011c723  mov     rcx, cs:off_1802605D0; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18011c72a  call    _bidTraceHR
0x18011c72f  mov     ebx, eax
0x18011c731  mov     eax, cs:_bidGblFlags
0x18011c737  jmp     short loc_18011C73E
0x18011c739  mov     ebx, 80004005h
0x18011c73e  test    al, 2
0x18011c740  jz      short loc_18011C758
0x18011c742  mov     r8d, ebx
0x18011c745  mov     edx, 34C09h
0x18011c74a  mov     rcx, cs:off_1802605D0; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18011c751  call    _bidTraceHR
0x18011c756  jmp     short loc_18011C75A
0x18011c758  mov     eax, ebx
0x18011c75a  mov     [rsp+220h+var_200], rdi; struct tagDISPPARAMS *
0x18011c75f  mov     r9d, 9F19h; unsigned int
0x18011c765  lea     r8, IID_IIndexDefinition; struct _GUID *
0x18011c76c  mov     edx, eax; int
0x18011c76e  mov     rcx, cs:?g_pCError@@3PEAVCError@@EA; this
0x18011c775  call    ?PostError@CError@@QEAAJJPEBU_GUID@@KPEAUtagDISPPARAMS@@@Z; CError::PostError(long,_GUID const *,ulong,tagDISPPARAMS *)
0x18011c77a  jmp     loc_18011D146
0x18011c77f  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x18011c786  mov     rax, [rcx]
0x18011c789  mov     edx, 30h ; '0'
0x18011c78e  mov     rax, [rax+58h]
0x18011c792  call    cs:__guard_dispatch_icall_fptr
0x18011c798  nop
0x18011c799  test    rax, rax
0x18011c79c  jz      loc_18011D08F
0x18011c7a2  mov     [rax], rdi
0x18011c7a5  mov     [rax+8], rdi
0x18011c7a9  mov     [rax+10h], rdi
0x18011c7ad  mov     [rax+18h], rdi
0x18011c7b1  mov     [rax+20h], rdi
0x18011c7b5  mov     [rax+28h], rdi
0x18011c7b9  mov     [rbp+120h+var_190], rax
0x18011c7bd  mov     edx, 400h; unsigned __int64
0x18011c7c2  mov     r8d, edx; unsigned __int64
0x18011c7c5  mov     rcx, rax; this
0x18011c7c8  call    ?FInit@CExtByteBuffer@@QEAAH_K0@Z; CExtByteBuffer::FInit(unsigned __int64,unsigned __int64)
0x18011c7cd  test    eax, eax
0x18011c7cf  jz      loc_18011D08F
0x18011c7d5  lfence
0x18011c7d8  mov     rax, [rsi+30h]
0x18011c7dc  mov     rcx, [rax+10h]
0x18011c7e0  cmp     word ptr [rcx+98h], 0FFFFh
0x18011c7e8  mov     rcx, [rbp+120h+var_190]; this
0x18011c7ec  jnz     loc_18011C954
0x18011c7f2  mov     r8d, 18h; Size
0x18011c7f8  lea     rdx, aAlterTable_0; "alter table "
0x18011c7ff  call    ?WriteIntoExtBuffer@CExtByteBuffer@@QEAAJPEBX_K@Z; CExtByteBuffer::WriteIntoExtBuffer(void const *,unsigned __int64)
0x18011c804  mov     ebx, eax
0x18011c806  test    eax, eax
0x18011c808  js      loc_18011D110
0x18011c80e  mov     rdx, [r14+18h]; Src
0x18011c812  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18011c819  nop     dword ptr [rax+00000000h]
0x18011c820  inc     r8
0x18011c823  cmp     word ptr [rdx+r8*2], 0
0x18011c829  jnz     short loc_18011C820
0x18011c82b  add     r8, r8; Size
0x18011c82e  mov     rcx, [rbp+120h+var_190]; this
0x18011c832  call    ?WriteIntoExtBuffer@CExtByteBuffer@@QEAAJPEBX_K@Z; CExtByteBuffer::WriteIntoExtBuffer(void const *,unsigned __int64)
0x18011c837  mov     ebx, eax
0x18011c839  test    eax, eax
0x18011c83b  js      loc_18011D110
0x18011c841  mov     r8d, 20h ; ' '; Size
0x18011c847  lea     rdx, aAddConstraint; " add constraint "
0x18011c84e  mov     rcx, [rbp+120h+var_190]; this
0x18011c852  call    ?WriteIntoExtBuffer@CExtByteBuffer@@QEAAJPEBX_K@Z; CExtByteBuffer::WriteIntoExtBuffer(void const *,unsigned __int64)
0x18011c857  mov     ebx, eax
0x18011c859  test    eax, eax
0x18011c85b  js      loc_18011D110
0x18011c861  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18011c868  nop     dword ptr [rax+rax+00000000h]
0x18011c870  inc     r8
0x18011c873  cmp     word ptr [r12+r8*2], 0
0x18011c879  jnz     short loc_18011C870
  ... truncated ...
```
