# CDataFileWriter::WriteRecord(CStmt *)

- ea: `0x18011b110`
- end: `0x18011bf9d`
- name: `?WriteRecord@CDataFileWriter@@QEAAJPEAVCStmt@@@Z`
- size: `3725`
- prototype: `__int64 __fastcall(CDataFileWriter *__hidden this, struct CStmt *)`
- caller_count: `1`
- callee_count: `28`
- tags: `loader_planting`

## callers

- `0x180114740`

## callees

- `0x180003030`
- `0x180003d80`
- `0x1800138c0`
- `0x180019d20`
- `0x180027810`
- `0x180052d40`
- `0x18006ac30`
- `0x18006fe70`
- `0x180072070`
- `0x180106be0`
- `0x180106c90`
- `0x180106d40`
- `0x180106df0`
- `0x1801072f0`
- `0x18010ba20`
- `0x18010bbe0`
- `0x1801102b0`
- `0x180119970`
- `0x18011a920`
- `0x18011aa90`
- `0x18011afb0`
- `0x18011b110`
- `0x180129020`
- `0x1801336f4`
- `0x180133bcc`
- `0x1801a65e1`
- `0x1801a65f0`
- `0x1801ad6a0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18011b451`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18011b4f0`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18011b451`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18011b4f0`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18011b45d`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18011b45d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDataFileWriter::WriteRecord(CDataFileWriter *this, struct CStmt *a2)
{
  unsigned int *v3; // r15
  __int64 v4; // rbx
  int v5; // eax
  int ConversionSize; // edi
  __int64 v7; // rdx
  __int64 v8; // r8
  int v9; // eax
  unsigned __int16 v10; // ax
  __int64 v11; // rcx
  __int64 v12; // r12
  unsigned __int16 v13; // si
  unsigned __int16 v14; // r15
  __int64 v15; // r13
  int ColumnData; // eax
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  size_t v20; // rsi
  int v21; // eax
  __int64 v22; // r12
  size_t v23; // r15
  void *v24; // rcx
  int v25; // eax
  unsigned __int64 v26; // r15
  unsigned int v27; // edx
  int v28; // eax
  int v29; // esi
  __int64 v30; // r8
  __int64 v31; // r9
  struct SSVARIANT *v32; // rdi
  unsigned int v33; // edx
  int v34; // eax
  __int64 v35; // rdx
  unsigned __int64 v36; // rdx
  int v37; // eax
  int v38; // eax
  int v39; // eax
  unsigned int v40; // edx
  int v41; // eax
  __int64 v42; // rdx
  int v43; // eax
  __int64 v44; // r8
  __int64 v45; // r9
  int v46; // eax
  __int64 v47; // rdx
  void *v48; // r8
  int v49; // eax
  __int64 v50; // rdx
  int v51; // eax
  int BLOBLength; // eax
  size_t v53; // rcx
  __int64 v54; // rax
  int v55; // eax
  __int64 v56; // rdx
  void *v57; // r8
  int v58; // eax
  __int64 v59; // rdx
  int v60; // eax
  __int64 v61; // rdx
  __int64 v62; // rdx
  int v63; // ecx
  _QWORD *v64; // rbx
  int v66; // [rsp+20h] [rbp-E0h]
  int v67; // [rsp+38h] [rbp-C8h]
  int v68; // [rsp+48h] [rbp-B8h]
  int v69; // [rsp+50h] [rbp-B0h]
  unsigned int *v70; // [rsp+80h] [rbp-80h]
  unsigned __int16 v72; // [rsp+90h] [rbp-70h]
  unsigned int v73; // [rsp+94h] [rbp-6Ch]
  unsigned __int64 v74; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v75; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v76[2]; // [rsp+A8h] [rbp-58h] BYREF
  bool v77[8]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v78; // [rsp+B8h] [rbp-48h] BYREF
  size_t Size; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v80; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int64 v81[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v82; // [rsp+E0h] [rbp-20h]
  __int128 v83; // [rsp+F0h] [rbp-10h]

  v3 = *(unsigned int **)(*((_QWORD *)this + 10) + 832LL);
  v70 = v3;
  v4 = 0;
  Size = 0;
  v74 = 0;
  v75 = 0;
  v80 = 0;
  v73 = v3[287];
  v5 = (*(__int64 (__fastcall **)(CDataFileWriter *, __int64 *))(*(_QWORD *)this + 32LL))(this, &v80);
  ConversionSize = v5;
  if ( v5 < 0 )
  {
    if ( (bidGblFlags & 2) == 0 )
    {
LABEL_6:
      a2 = 0;
      goto LABEL_194;
    }
    v7 = 7076873;
    goto LABEL_4;
  }
  _mm_lfence();
  v9 = CRecordFetcher::Lock(*((CRecordFetcher **)this + 11));
  if ( v9 )
  {
    ConversionSize = -2147221263;
    if ( v9 == 4 )
      ConversionSize = -2147221212;
    goto LABEL_194;
  }
  v10 = 0;
  v72 = 0;
  v11 = *((_QWORD *)this + 10);
  if ( !*(_WORD *)(v11 + 2716) )
    goto LABEL_193;
  while ( 1 )
  {
    v4 = *(_QWORD *)(v11 + 2720) + 408LL * v10;
    v12 = *(_QWORD *)(v4 + 296);
    *(_QWORD *)v76 = v12;
    if ( v12 )
      break;
LABEL_157:
    v10 = v72 + 1;
    v72 = v10;
    v11 = *((_QWORD *)this + 10);
    if ( v10 >= *(_WORD *)(v11 + 2716) )
      goto LABEL_193;
  }
  v13 = v72 + 1;
  v14 = *(_WORD *)(v12 + 2);
  v15 = *(unsigned __int16 *)(v4 + 24);
  if ( !*(_DWORD *)(v12 + 572) && !*(_DWORD *)(v12 + 576) )
  {
    if ( *(_DWORD *)(v4 + 20) )
    {
      ColumnData = CRecordFetcher::GetColumnData(
                     *((CRecordFetcher **)this + 11),
                     v13,
                     *((unsigned __int8 **)this + 12),
                     0x1F49u,
                     &Size,
                     &v75);
      switch ( ColumnData )
      {
        case -1:
        case 2:
          goto LABEL_179;
        case 4:
          ConversionSize = -2147221212;
          v3 = v70;
          goto LABEL_194;
        case 100:
          goto LABEL_179;
      }
      if ( v75 != 3 )
      {
        v3 = v70;
        if ( *(_DWORD *)(v4 + 360) )
          CDataSource::SetClientCP((CDataSource *)v70, *(_DWORD *)(v4 + 292));
        v17 = *(_DWORD *)(v4 + 364);
        if ( v17 )
        {
          v18 = v17 - 1;
          if ( v18 )
          {
            v19 = v18 - 1;
            if ( !v19 || v19 == 2 )
            {
              LOBYTE(v69) = *(_BYTE *)(v12 + 291);
              LOBYTE(v68) = *(_BYTE *)(v12 + 290);
              LOWORD(v67) = v15;
              LOBYTE(v66) = *(_BYTE *)(v12 + 288);
              ConversionSize = CDataSource::OLEDBdataFromSQLdata(
                                 *(_QWORD *)(*((_QWORD *)this + 10) + 832LL),
                                 *(unsigned int *)(v12 + 564),
                                 Size,
                                 *(unsigned __int8 *)(v12 + 289),
                                 v66,
                                 *((_QWORD *)this + 12),
                                 0,
                                 v67,
                                 *(_QWORD *)(v4 + 320),
                                 v68,
                                 v69,
                                 *(_QWORD *)(v4 + 312),
                                 &v74,
                                 &v75,
                                 *(_DWORD *)(v12 + 556),
                                 448);
              if ( ConversionSize < 0 )
                goto LABEL_159;
              v20 = v74;
            }
            else
            {
              v20 = v74;
            }
          }
          else
          {
            v21 = CDBConnection::XlateCharFromServer(
                    *(CDBConnection **)(*((_QWORD *)this + 11) + 8LL),
                    *((const char **)this + 12),
                    Size,
                    *(char **)(v4 + 312),
                    *(_QWORD *)(v4 + 320),
                    (__int64 *)&v74,
                    0,
                    (struct CErrorData *)(**((_QWORD **)this + 11) + 136LL),
                    *(_DWORD *)(v12 + 556));
            if ( v21 == 1 )
            {
              ConversionSize = 265937;
              v20 = v74;
            }
            else
            {
              if ( v21 == -1 )
              {
LABEL_159:
                ConversionSize = -2147221260;
                goto LABEL_194;
              }
              v20 = v74;
            }
          }
LABEL_41:
          v3 = v70;
          if ( *(_DWORD *)(v4 + 360) )
          {
            CDataSource::SetClientCP((CDataSource *)v70, v73);
            v20 = v74;
          }
          if ( v75 != 3 )
          {
            switch ( (int)v15 )
            {
              case 6:
                v25 = CDataFileWriter::WriteCurrency(this, (struct CBCPField *)v4, v20);
                ConversionSize = v25;
                if ( v25 >= 0 )
                  goto LABEL_155;
                if ( (bidGblFlags & 2) != 0 )
                {
                  _mm_lfence();
                  bidTraceHR(off_1802605B8[0], 7374857, (unsigned int)v25);
                }
                goto LABEL_54;
              case 11:
                v26 = 1;
                *(_QWORD *)v76 = 1;
                v77[0] = **(_WORD **)(v4 + 312) == 0xFFFF;
                v27 = *(_DWORD *)(v4 + 16);
                if ( !v27 )
                  goto LABEL_58;
                v28 = CDataFileWriter::WriteNonNullPrefix(this, v27, 1u, *(_DWORD *)(v4 + 20), (unsigned __int64 *)v76);
                v29 = v28;
                ConversionSize = v28;
                if ( v28 < 0 )
                {
                  if ( (bidGblFlags & 2) != 0 )
                  {
                    v62 = 8297481;
LABEL_165:
                    _mm_lfence();
                    bidTraceHR(off_1802605B8[0], v62, (unsigned int)v28);
LABEL_166:
                    if ( (bidGblFlags & 2) != 0 )
                    {
                      _mm_lfence();
                      bidTraceHR(off_1802605B8[0], 7378953, (unsigned int)v29);
                      a2 = 0;
                      v3 = v70;
                      goto LABEL_194;
                    }
                    goto LABEL_190;
                  }
                }
                else
                {
                  v26 = *(_QWORD *)v76;
LABEL_58:
                  v28 = (*(__int64 (__fastcall **)(CDataFileWriter *, _QWORD, bool *))(*(_QWORD *)this + 16LL))(
                          this,
                          (unsigned int)v26,
                          v77);
                  v29 = v28;
                  ConversionSize = v28;
                  if ( v28 >= 0 )
                  {
                    if ( *(_DWORD *)(v4 + 16)
                      || *(_DWORD *)(v4 + 4)
                      || *(int *)(v4 + 20) <= v26
                      || (_mm_lfence(),
                          v28 = CDataFileWriter::WritePadding<unsigned char,0>(
                                  this,
                                  *(int *)(v4 + 20) - *(_QWORD *)v76,
                                  v30,
                                  v31),
                          v29 = v28,
                          ConversionSize = v28,
                          v28 >= 0)
                      || (bidGblFlags & 2) == 0 )
                    {
                      ConversionSize = v29;
                      if ( v29 < 0 )
                        goto LABEL_166;
LABEL_154:
                      v3 = v70;
LABEL_155:
                      v61 = *(unsigned int *)(v4 + 4);
                      if ( !(_DWORD)v61 )
                        goto LABEL_157;
                      v5 = (*(__int64 (__fastcall **)(CDataFileWriter *, __int64, _QWORD))(*(_QWORD *)this + 16LL))(
                             this,
                             v61,
                             *(_QWORD *)(v4 + 8));
                      ConversionSize = v5;
                      if ( v5 >= 0 )
                        goto LABEL_157;
                      if ( (bidGblFlags & 2) != 0 )
                      {
                        v7 = 7442441;
LABEL_4:
                        v8 = (unsigned int)v5;
LABEL_5:
                        _mm_lfence();
                        bidTraceHR(off_1802605B8[0], v7, v8);
                        goto LABEL_6;
                      }
                      break;
                    }
                    v62 = 8306697;
                    goto LABEL_165;
                  }
                  if ( (bidGblFlags & 2) != 0 )
                  {
                    v62 = 8301577;
                    goto LABEL_165;
                  }
                }
                goto LABEL_190;
              case 129:
                v37 = CDataFileWriter::WriteString<char>(this);
                ConversionSize = v37;
                if ( v37 >= 0 )
                  goto LABEL_155;
                if ( (bidGblFlags & 2) == 0 )
                  goto LABEL_54;
                _mm_lfence();
                bidTraceHR(off_1802605B8[0], 7390217, (unsigned int)v37);
                a2 = 0;
                goto LABEL_194;
              case 130:
                v38 = CDataFileWriter::WriteString<wchar_t>(this);
                ConversionSize = v38;
                if ( v38 >= 0 )
                  goto LABEL_155;
                if ( (bidGblFlags & 2) == 0 )
                  goto LABEL_54;
                _mm_lfence();
                bidTraceHR(off_1802605B8[0], 7394313, (unsigned int)v38);
                a2 = 0;
                goto LABEL_194;
              case 133:
              case 135:
              case 145:
              case 146:
                v39 = CDataFileWriter::WriteDateTime(this, (struct CBCPField *)v4, v20);
                ConversionSize = v39;
                if ( v39 >= 0 )
                  goto LABEL_155;
                if ( (bidGblFlags & 2) == 0 )
                  goto LABEL_54;
                _mm_lfence();
                bidTraceHR(off_1802605B8[0], 7401481, (unsigned int)v39);
                a2 = 0;
                goto LABEL_194;
              case 144:
                v76[0] = 0;
                v81[0] = 0;
                v81[1] = 0;
                v82 = 0u;
                v83 = 0;
                v78 = *(int *)(v4 + 20);
                v32 = *(struct SSVARIANT **)(v4 + 312);
                if ( !(unsigned int)CExtByteBuffer::FInit((CExtByteBuffer *)v81, 0x40u, 0x40u) )
                {
                  ConversionSize = -2147221260;
                  goto LABEL_80;
                }
                if ( (int)CDataSource::DBTYPE_SQLVARIANTToSQL_VARIANT(
                            (CDataSource *)v70,
                            v32,
                            v76,
                            0,
                            (struct CExtByteBuffer *)v81,
                            *(_BYTE *)(*((_QWORD *)this + 10) + 2648LL) < 0x64u,
                            0x40u) < 0 )
                {
                  ConversionSize = -2147221260;
                  goto LABEL_80;
                }
                v33 = *(_DWORD *)(v4 + 16);
                if ( v33 )
                {
                  v34 = CDataFileWriter::WriteNonNullPrefix(this, v33, v81[1], *(_DWORD *)(v4 + 20), &v78);
                  ConversionSize = v34;
                  if ( v34 < 0 )
                  {
                    if ( (bidGblFlags & 2) == 0 )
                      goto LABEL_80;
                    v35 = 8353801;
                    goto LABEL_79;
                  }
                  v36 = v78;
                }
                else
                {
                  v36 = v81[1];
                }
                v34 = (*(__int64 (__fastcall **)(CDataFileWriter *, unsigned __int64, _QWORD))(*(_QWORD *)this + 16LL))(
                        this,
                        v36,
                        v83);
                ConversionSize = v34;
                if ( v34 >= 0 || (bidGblFlags & 2) == 0 )
                {
LABEL_80:
                  CExtBaseBuffer::~CExtBaseBuffer((CExtBaseBuffer *)v81);
                  if ( ConversionSize < 0 )
                  {
                    if ( (bidGblFlags & 2) == 0 )
                      goto LABEL_6;
                    v8 = (unsigned int)ConversionSize;
                    v7 = 7383049;
                    goto LABEL_5;
                  }
                  SSVariantClear(*(struct SSVARIANT **)(v4 + 312));
                  goto LABEL_155;
                }
                v35 = 8364041;
LABEL_79:
                _mm_lfence();
                bidTraceHR(off_1802605B8[0], v35, (unsigned int)v34);
                goto LABEL_80;
              default:
                v40 = *(_DWORD *)(v4 + 16);
                if ( v40 )
                {
                  v78 = 0;
                  v41 = CDataFileWriter::WriteNonNullPrefix(this, v40, v20, *(_DWORD *)(v4 + 20), &v78);
                  ConversionSize = v41;
                  if ( v41 < 0 )
                  {
                    if ( (bidGblFlags & 2) != 0 )
                    {
                      v42 = 7414793;
                      goto LABEL_172;
                    }
                  }
                  else
                  {
                    _mm_lfence();
                    v41 = (*(__int64 (__fastcall **)(CDataFileWriter *, _QWORD, _QWORD))(*(_QWORD *)this + 16LL))(
                            this,
                            (unsigned int)v78,
                            *(_QWORD *)(v4 + 312));
                    ConversionSize = v41;
                    if ( v41 >= 0 )
                      goto LABEL_155;
                    if ( (bidGblFlags & 2) != 0 )
                    {
                      v42 = 7418889;
LABEL_172:
                      _mm_lfence();
                      bidTraceHR(off_1802605B8[0], v42, (unsigned int)v41);
                    }
                  }
                  a2 = 0;
                  goto LABEL_194;
                }
                v43 = (*(__int64 (__fastcall **)(CDataFileWriter *, _QWORD, _QWORD))(*(_QWORD *)this + 16LL))(
                        this,
                        (unsigned int)v20,
                        *(_QWORD *)(v4 + 312));
                ConversionSize = v43;
                if ( v43 >= 0 )
                {
                  if ( !*(_DWORD *)(v4 + 4) && *(int *)(v4 + 20) > v74 )
                  {
                    _mm_lfence();
                    v46 = CDataFileWriter::WritePadding<unsigned char,0>(this, *(int *)(v4 + 20) - v74, v44, v45);
                    ConversionSize = v46;
                    if ( v46 < 0 )
                    {
                      if ( (bidGblFlags & 2) != 0 )
                      {
                        _mm_lfence();
                        bidTraceHR(off_1802605B8[0], 7430153, (unsigned int)v46);
                        a2 = 0;
                      }
                      else
                      {
LABEL_54:
                        a2 = 0;
                      }
                      goto LABEL_194;
                    }
                  }
                  goto LABEL_155;
                }
                if ( (bidGblFlags & 2) != 0 )
                {
                  _mm_lfence();
                  bidTraceHR(off_1802605B8[0], 7425033, (unsigned int)v43);
                  a2 = 0;
                  goto LABEL_194;
                }
                break;
            }
LABEL_193:
            a2 = 0;
            if ( ConversionSize >= 0 )
              goto LABEL_195;
LABEL_194:
            _mm_lfence();
            (*(void (__fastcall **)(CDataFileWriter *, __int64, _QWORD))(*(_QWORD *)this + 24LL))(this, v80, 0);
            ConversionSize = CBCPErrorHandler::PostBCPErrors(a2, ConversionSize);
            goto LABEL_195;
          }
          goto LABEL_103;
        }
        v20 = *(_QWORD *)(v4 + 320);
        if ( Size < v20 )
          v20 = Size;
        v74 = v20;
        v22 = *((_QWORD *)this + 12);
        v23 = *(_QWORD *)(v4 + 320);
        v24 = *(void **)(v4 + 312);
        if ( !v20 )
          goto LABEL_41;
        if ( !v24 )
          goto LABEL_38;
        if ( v22 && v23 >= v20 )
        {
          memcpy_0(v24, *((const void **)this + 12), v20);
          goto LABEL_40;
        }
        memset_0(v24, 0, *(_QWORD *)(v4 + 320));
        if ( v22 )
        {
          if ( v23 >= v20 )
            goto LABEL_40;
          *_errno() = 34;
        }
        else
        {
LABEL_38:
          *_errno() = 22;
        }
        _invalid_parameter_noinfo();
LABEL_40:
        v20 = v74;
        goto LABEL_41;
      }
    }
    else
    {
      v75 = 3;
    }
LABEL_103:
    v47 = *(unsigned int *)(v4 + 16);
    if ( (_DWORD)v47 )
    {
      v78 = -1;
      v76[0] = 0;
      v48 = v76;
      if ( (_WORD)v15 != 144 )
        v48 = &v78;
      v49 = (*(__int64 (__fastcall **)(CDataFileWriter *, __int64, void *, __int64))(*(_QWORD *)this + 16LL))(
              this,
              v47,
              v48,
              130);
      ConversionSize = v49;
      if ( v49 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          _mm_lfence();
          bidTraceHR(off_1802605B8[0], 7347209, (unsigned int)v49);
          a2 = 0;
          v3 = v70;
          goto LABEL_194;
        }
LABEL_187:
        a2 = 0;
        v3 = v70;
        goto LABEL_194;
      }
      v3 = v70;
      goto LABEL_155;
    }
    if ( *(_DWORD *)(v4 + 4) || !*(_DWORD *)(v4 + 20) )
      goto LABEL_154;
    v50 = *(int *)(v4 + 20);
    if ( (_WORD)v15 == 129 )
      v51 = CDataFileWriter::WritePadding<char,32>(this, v50, 129, 130);
    else
      v51 = (_WORD)v15 == 130
          ? CDataFileWriter::WritePadding<wchar_t,32>(this, v50, 129, 130)
          : CDataFileWriter::WritePadding<unsigned char,0>(this, v50, 129, 130);
    ConversionSize = v51;
    if ( v51 >= 0 )
      goto LABEL_154;
    if ( (bidGblFlags & 2) != 0 )
    {
      _mm_lfence();
      bidTraceHR(off_1802605B8[0], 7365641, (unsigned int)v51);
      a2 = 0;
      v3 = v70;
      goto LABEL_194;
    }
LABEL_190:
    a2 = 0;
    v3 = v70;
    goto LABEL_194;
  }
  if ( !*(_DWORD *)(v4 + 20) )
  {
    v75 = 3;
LABEL_141:
    v56 = *(unsigned int *)(v4 + 16);
    if ( (_DWORD)v56 )
    {
      v78 = -1;
      v76[0] = 0;
      v57 = v76;
      if ( (_WORD)v15 != 144 )
        v57 = &v78;
      v58 = (*(__int64 (__fastcall **)(CDataFileWriter *, __int64, void *, __int64))(*(_QWORD *)this + 16LL))(
              this,
              v56,
              v57,
              130);
      ConversionSize = v58;
      if ( v58 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          _mm_lfence();
          bidTraceHR(off_1802605B8[0], 7189513, (unsigned int)v58);
        }
        goto LABEL_187;
      }
      v3 = v70;
      goto LABEL_155;
    }
    if ( *(_DWORD *)(v4 + 4) || !*(_DWORD *)(v4 + 20) )
      goto LABEL_154;
    v59 = *(int *)(v4 + 20);
    if ( (_WORD)v15 == 129 )
      v60 = CDataFileWriter::WritePadding<char,32>(this, v59, 129, 130);
    else
      v60 = (_WORD)v15 == 130
          ? CDataFileWriter::WritePadding<wchar_t,32>(this, v59, 129, 130)
          : CDataFileWriter::WritePadding<unsigned char,0>(this, v59, 129, 130);
    ConversionSize = v60;
    if ( v60 >= 0 )
      goto LABEL_154;
    if ( (bidGblFlags & 2) != 0 )
    {
      _mm_lfence();
      bidTraceHR(off_1802605B8[0], 7206921, (unsigned int)v60);
    }
    goto LABEL_190;
  }
  BLOBLength = CRecordFetcher::GetBLOBLength(*((CRecordFetcher **)this + 11), v13, &Size, &v75);
  if ( BLOBLength )
  {
    v63 = -2147221212;
    if ( BLOBLength != 4 )
      v63 = -2147221263;
    ConversionSize = v63;
    v3 = v70;
    goto LABEL_194;
  }
  if ( v75 == 3 )
    goto LABEL_141;
  v53 = Size;
  if ( !*(_DWORD *)(v4 + 364) || Size == -1 )
  {
    v74 = Size;
    v3 = v70;
  }
  else
  {
    if ( *(_DWORD *)(v4 + 360) )
    {
      CDataSource::SetClientCP((CDataSource *)v70, *(_DWORD *)(v4 + 292));
      v53 = Size;
    }
    if ( (*(_BYTE *)(v4 + 364) & 1) != 0 )
    {
      v54 = 2;
      if ( *(_DWORD *)(v4 + 292) == 54936 )
        v54 = 4;
      v74 = v53 * v54 + 1;
    }
    else
    {
      ConversionSize = CDataConvert::GetConversionSize(
                         v14,
                         v15,
                         &Size,
                         &v74,
                         0,
                         0,
                         0xC0u,
                         *(_DWORD *)(v12 + 556),
                         v70[287]);
    }
    if ( ConversionSize < 0 )
    {
LABEL_179:
      ConversionSize = -2147221262;
      v3 = v70;
      goto LABEL_194;
    }
    v74 -= `GetAdjustmentFactor'::`2'::cbAdjustment[v15];
    v3 = v70;
    if ( *(_DWORD *)(v4 + 360) )
      CDataSource::SetClientCP((CDataSource *)v70, v73);
  }
  if ( v75 == 3 )
    goto LABEL_141;
  if ( *(_DWORD *)(v4 + 360) )
    CDataSource::SetClientCP((CDataSource *)v3, *(_DWORD *)(v4 + 292));
  v55 = CDataFileWriter::WriteBLOBColumn(
          this,
          (struct CBCPField *)v4,
          (struct CBCPColumn *)v12,
          v13,
          *(struct COLINFO **)(v4 + 352),
          *((struct CRecordFetcher **)this + 11),
          (struct CDataSource *)v3,
          v74);
  ConversionSize = v55;
  if ( v55 >= 0 )
  {
    if ( *(_DWORD *)(v4 + 360) )
    {
      _mm_lfence();
      CDataSource::SetClientCP((CDataSource *)v3, v73);
    }
    goto LABEL_155;
  }
  if ( (bidGblFlags & 2) != 0 )
  {
    _mm_lfence();
    bidTraceHR(off_1802605B8[0], 7223305, (unsigned int)v55);
  }
LABEL_195:
  if ( v4 && *(_DWORD *)(v4 + 360) )
    CDataSource::SetClientCP((CDataSource *)v3, v73);
  v64 = (_QWORD *)*((_QWORD *)this + 11);
  CAutoBatchCtx::Release((CAutoBatchCtx *)(v64 + 7));
  v64[6] = 0;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(*v64 + 88LL) + 32LL) + 24LL))(*(_QWORD *)(*v64 + 88LL) + 32LL);
  return (unsigned int)ConversionSize;
}

```

## disassembly

```asm
0x18011b110  mov     [rsp-8+arg_10], rbx
0x18011b115  push    rbp
0x18011b116  push    rsi
0x18011b117  push    rdi
0x18011b118  push    r12
0x18011b11a  push    r13
0x18011b11c  push    r14
0x18011b11e  push    r15
0x18011b120  lea     rbp, [rsp-10h]
0x18011b125  sub     rsp, 110h
0x18011b12c  mov     rax, cs:__security_cookie
0x18011b133  xor     rax, rsp
0x18011b136  mov     [rbp+40h+var_40], rax
0x18011b13a  mov     [rbp+40h+var_B8], rdx
0x18011b13e  mov     r14, rcx
0x18011b141  mov     rax, [rcx+50h]
0x18011b145  mov     r15, [rax+340h]
0x18011b14c  mov     [rbp+40h+var_C0], r15
0x18011b150  xor     esi, esi
0x18011b152  mov     ebx, esi
0x18011b154  mov     [rbp+40h+Size], rsi
0x18011b158  mov     [rbp+40h+var_A8], rsi
0x18011b15c  mov     [rbp+40h+var_A0], esi
0x18011b15f  mov     [rbp+40h+var_78], rsi
0x18011b163  mov     eax, [r15+47Ch]
0x18011b16a  mov     [rbp+40h+var_AC], eax
0x18011b16d  mov     rax, [rcx]
0x18011b170  lea     rdx, [rbp+40h+var_78]
0x18011b174  mov     rax, [rax+20h]
0x18011b178  call    cs:__guard_dispatch_icall_fptr
0x18011b17e  mov     edi, eax
0x18011b180  test    eax, eax
0x18011b182  jns     short loc_18011B1AD
0x18011b184  test    byte ptr cs:_bidGblFlags, 2
0x18011b18b  jz      short loc_18011B1A4
0x18011b18d  mov     edx, 6BFC09h
0x18011b192  mov     r8d, eax
0x18011b195  lfence
0x18011b198  mov     rcx, cs:off_1802605B8; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18011b19f  call    _bidTraceHR
0x18011b1a4  mov     [rbp+40h+var_B8], rsi
0x18011b1a8  jmp     loc_18011BE5B
0x18011b1ad  lfence
0x18011b1b0  mov     rcx, [r14+58h]; this
0x18011b1b4  call    ?Lock@CRecordFetcher@@QEAAHXZ; CRecordFetcher::Lock(void)
0x18011b1b9  test    eax, eax
0x18011b1bb  jz      short loc_18011B1D2
0x18011b1bd  mov     edi, 800400F1h
0x18011b1c2  mov     ecx, 80040124h
0x18011b1c7  cmp     eax, 4
0x18011b1ca  cmovz   edi, ecx
0x18011b1cd  jmp     loc_18011BE5B
0x18011b1d2  movzx   eax, si
0x18011b1d5  mov     [rbp+40h+var_B0], ax
0x18011b1d9  mov     rcx, [r14+50h]
0x18011b1dd  cmp     si, [rcx+0A9Ch]
0x18011b1e4  jnb     loc_18011BE53
0x18011b1ea  mov     r10d, 90h
0x18011b1f0  mov     r8d, 81h
0x18011b1f6  mov     r9d, 82h
0x18011b1fc  nop     dword ptr [rax+00h]
0x18011b200  movzx   eax, ax
0x18011b203  imul    rbx, rax, 198h
0x18011b20a  add     rbx, [rcx+0AA0h]
0x18011b211  mov     r12, [rbx+128h]
0x18011b218  mov     qword ptr [rbp+40h+var_98], r12
0x18011b21c  test    r12, r12
0x18011b21f  jz      loc_18011BC45
0x18011b225  movzx   esi, [rbp+40h+var_B0]
0x18011b229  inc     si
0x18011b22c  movzx   r15d, word ptr [r12+2]
0x18011b232  movzx   r13d, word ptr [rbx+18h]
0x18011b237  cmp     dword ptr [r12+23Ch], 0
0x18011b240  jnz     loc_18011B9DE
0x18011b246  cmp     dword ptr [r12+240h], 0
0x18011b24f  jnz     loc_18011B9DE
0x18011b255  cmp     dword ptr [rbx+14h], 0
0x18011b259  jz      loc_18011B904
0x18011b25f  lea     rax, [rbp+40h+var_A0]
0x18011b263  mov     [rsp+140h+var_118], rax; unsigned int *
0x18011b268  lea     rax, [rbp+40h+Size]
0x18011b26c  mov     [rsp+140h+var_120], rax; unsigned __int64 *
0x18011b271  mov     r9d, 1F49h; unsigned int
0x18011b277  mov     r8, [r14+60h]; unsigned __int8 *
0x18011b27b  movzx   edx, si; unsigned __int16
0x18011b27e  mov     rcx, [r14+58h]; this
0x18011b282  call    ?GetColumnData@CRecordFetcher@@QEAAHGPEAEKPEA_KPEAK@Z; CRecordFetcher::GetColumnData(ushort,uchar *,ulong,unsigned __int64 *,ulong *)
0x18011b287  cmp     eax, 0FFFFFFFFh
0x18011b28a  jz      loc_18011BD97
0x18011b290  cmp     eax, 2
0x18011b293  jz      loc_18011BD97
0x18011b299  cmp     eax, 4
0x18011b29c  jz      loc_18011BD58
0x18011b2a2  cmp     eax, 64h ; 'd'
0x18011b2a5  jz      loc_18011BD97
0x18011b2ab  cmp     [rbp+40h+var_A0], 3
0x18011b2af  jz      loc_18011B90D
0x18011b2b5  mov     r15, [rbp+40h+var_C0]
0x18011b2b9  cmp     dword ptr [rbx+168h], 0
0x18011b2c0  jz      short loc_18011B2D0
0x18011b2c2  mov     edx, [rbx+124h]; unsigned int
0x18011b2c8  mov     rcx, r15; this
0x18011b2cb  call    ?SetClientCP@CDataSource@@QEAAXI@Z; CDataSource::SetClientCP(uint)
0x18011b2d0  mov     ecx, [rbx+16Ch]
0x18011b2d6  test    ecx, ecx
0x18011b2d8  jz      loc_18011B421
0x18011b2de  sub     ecx, 1
0x18011b2e1  jz      loc_18011B3AE
0x18011b2e7  sub     ecx, 1
0x18011b2ea  jz      short loc_18011B2FA
0x18011b2ec  cmp     ecx, 2
0x18011b2ef  jz      short loc_18011B2FA
0x18011b2f1  mov     rsi, [rbp+40h+var_A8]
0x18011b2f5  jmp     loc_18011B46B
0x18011b2fa  mov     rax, [r14+50h]
0x18011b2fe  mov     rcx, [rax+340h]
0x18011b305  mov     [rsp+140h+var_C8], 1C0h
0x18011b30d  mov     eax, [r12+22Ch]
0x18011b315  mov     [rsp+140h+var_D0], eax
0x18011b319  lea     rax, [rbp+40h+var_A0]
0x18011b31d  mov     [rsp+140h+var_D8], rax
0x18011b322  lea     rax, [rbp+40h+var_A8]
0x18011b326  mov     [rsp+140h+var_E0], rax
0x18011b32b  mov     rax, [rbx+138h]
0x18011b332  mov     [rsp+140h+var_E8], rax
0x18011b337  movzx   eax, byte ptr [r12+123h]
0x18011b340  mov     [rsp+140h+var_F0], al
0x18011b344  movzx   eax, byte ptr [r12+122h]
0x18011b34d  mov     [rsp+140h+var_F8], al
0x18011b351  mov     rax, [rbx+140h]
0x18011b358  mov     qword ptr [rsp+140h+CodePage], rax
0x18011b35d  mov     word ptr [rsp+140h+var_108], r13w
0x18011b363  mov     dword ptr [rsp+140h+var_110], 0
0x18011b36b  mov     rax, [r14+60h]
0x18011b36f  mov     [rsp+140h+var_118], rax
0x18011b374  movzx   eax, byte ptr [r12+120h]
0x18011b37d  mov     byte ptr [rsp+140h+var_120], al
0x18011b381  movzx   r9d, byte ptr [r12+121h]
0x18011b38a  mov     r8, [rbp+40h+Size]
0x18011b38e  mov     edx, [r12+234h]
0x18011b396  call    ?OLEDBdataFromSQLdata@CDataSource@@QEAAJW4EnumSQLDataTypes@@_KEEPEAXKG1EE2PEA_KPEAKIK@Z; CDataSource::OLEDBdataFromSQLdata(EnumSQLDataTypes,unsigned __int64,uchar,uchar,void *,ulong,ushort,unsigned __int64,uchar,uchar,void *,unsigned __int64 *,ulong *,uint,ulong)
0x18011b39b  mov     edi, eax
0x18011b39d  test    eax, eax
0x18011b39f  js      loc_18011BC66
0x18011b3a5  mov     rsi, [rbp+40h+var_A8]
0x18011b3a9  jmp     loc_18011B46B
0x18011b3ae  mov     r8, [rbx+140h]
0x18011b3b5  mov     rax, [r14+58h]
0x18011b3b9  mov     rcx, [rax+8]; this
0x18011b3bd  mov     rdx, [rax]
0x18011b3c0  add     rdx, 88h
0x18011b3c7  mov     eax, [r12+22Ch]
0x18011b3cf  mov     [rsp+140h+CodePage], eax; CodePage
0x18011b3d3  mov     [rsp+140h+var_108], rdx; struct CErrorData *
0x18011b3d8  mov     dword ptr [rsp+140h+var_110], 0; int
0x18011b3e0  lea     rax, [rbp+40h+var_A8]
0x18011b3e4  mov     [rsp+140h+var_118], rax; __int64 *
0x18011b3e9  mov     [rsp+140h+var_120], r8; Size
0x18011b3ee  mov     r9, [rbx+138h]; char *
0x18011b3f5  mov     r8, [rbp+40h+Size]; __int64
0x18011b3f9  mov     rdx, [r14+60h]; char *
0x18011b3fd  call    ?XlateCharFromServer@CDBConnection@@QEAAHPEBD_JPEAD1PEA_JHPEAVCErrorData@@I@Z; CDBConnection::XlateCharFromServer(char const *,__int64,char *,__int64,__int64 *,int,CErrorData *,uint)
0x18011b402  cmp     eax, 1
0x18011b405  jnz     short loc_18011B412
0x18011b407  mov     edi, 40ED1h
0x18011b40c  mov     rsi, [rbp+40h+var_A8]
0x18011b410  jmp     short loc_18011B46B
0x18011b412  cmp     eax, 0FFFFFFFFh
0x18011b415  jz      loc_18011BC66
0x18011b41b  mov     rsi, [rbp+40h+var_A8]
0x18011b41f  jmp     short loc_18011B46B
0x18011b421  mov     rsi, [rbx+140h]
0x18011b428  cmp     [rbp+40h+Size], rsi
0x18011b42c  cmovb   rsi, [rbp+40h+Size]
0x18011b431  mov     [rbp+40h+var_A8], rsi
0x18011b435  mov     r12, [r14+60h]
0x18011b439  mov     r15, [rbx+140h]
0x18011b440  mov     rcx, [rbx+138h]; void *
0x18011b447  test    rsi, rsi
0x18011b44a  jz      short loc_18011B467
0x18011b44c  test    rcx, rcx
0x18011b44f  jnz     short loc_18011B4BD
0x18011b451  call    cs:__imp__errno
0x18011b457  mov     dword ptr [rax], 16h
0x18011b45d  call    cs:__imp__invalid_parameter_noinfo
0x18011b463  mov     rsi, [rbp+40h+var_A8]
0x18011b467  mov     r12, qword ptr [rbp+40h+var_98]
0x18011b46b  mov     r15, [rbp+40h+var_C0]
0x18011b46f  cmp     dword ptr [rbx+168h], 0
0x18011b476  jz      short loc_18011B487
0x18011b478  mov     edx, [rbp+40h+var_AC]; unsigned int
0x18011b47b  mov     rcx, r15; this
0x18011b47e  call    ?SetClientCP@CDataSource@@QEAAXI@Z; CDataSource::SetClientCP(uint)
0x18011b483  mov     rsi, [rbp+40h+var_A8]
0x18011b487  cmp     [rbp+40h+var_A0], 3
0x18011b48b  jz      loc_18011B90D
0x18011b491  lea     eax, [r13-6]; switch 141 cases
0x18011b495  cmp     eax, 8Ch
0x18011b49a  ja      def_18011B4BB; jumptable 000000018011B4BB default case, cases 7-10,12-128,131,132,134,136-143
0x18011b4a0  cdqe
0x18011b4a2  lea     rdx, cs:180000000h
0x18011b4a9  movzx   eax, ds:(byte_18011BF10 - 180000000h)[rdx+rax]
0x18011b4b1  mov     ecx, ds:(jpt_18011B4BB - 180000000h)[rdx+rax*4]
0x18011b4b8  add     rcx, rdx
0x18011b4bb  jmp     rcx; switch jump
0x18011b4bd  test    r12, r12
0x18011b4c0  jz      short loc_18011B4D4
0x18011b4c2  cmp     r15, rsi
0x18011b4c5  jb      short loc_18011B4D4
0x18011b4c7  mov     r8, rsi; Size
0x18011b4ca  mov     rdx, r12; Src
0x18011b4cd  call    memcpy_0
0x18011b4d2  jmp     short loc_18011B463
0x18011b4d4  mov     r8, r15; Size
0x18011b4d7  xor     edx, edx; Val
0x18011b4d9  call    memset_0
0x18011b4de  test    r12, r12
0x18011b4e1  jz      loc_18011B451
0x18011b4e7  cmp     r15, rsi
0x18011b4ea  jnb     loc_18011B463
0x18011b4f0  call    cs:__imp__errno
0x18011b4f6  mov     dword ptr [rax], 22h ; '"'
0x18011b4fc  jmp     loc_18011B45D
0x18011b501  mov     r8, rsi; jumptable 000000018011B4BB case 6
0x18011b504  mov     rdx, rbx; struct CBCPField *
0x18011b507  mov     rcx, r14; this
0x18011b50a  call    ?WriteCurrency@CDataFileWriter@@QEAAJPEAVCBCPField@@_K@Z; CDataFileWriter::WriteCurrency(CBCPField *,unsigned __int64)
0x18011b50f  mov     edi, eax
0x18011b511  test    eax, eax
0x18011b513  jns     loc_18011BC0C
0x18011b519  test    byte ptr cs:_bidGblFlags, 2
0x18011b520  jz      short loc_18011B539
0x18011b522  lfence
0x18011b525  mov     r8d, eax
0x18011b528  mov     edx, 708809h
0x18011b52d  mov     rcx, cs:off_1802605B8; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18011b534  call    _bidTraceHR
0x18011b539  mov     [rbp+40h+var_B8], 0
0x18011b541  jmp     loc_18011BE5B
0x18011b546  mov     r15d, 1; jumptable 000000018011B4BB case 11
0x18011b54c  mov     qword ptr [rbp+40h+var_98], r15
0x18011b550  mov     rax, [rbx+138h]
0x18011b557  cmp     word ptr [rax], 0FFFFh
0x18011b55b  setz    [rbp+40h+var_90]
0x18011b55f  mov     edx, [rbx+10h]; unsigned int
0x18011b562  test    edx, edx
0x18011b564  jz      short loc_18011B58E
0x18011b566  lea     rax, [rbp+40h+var_98]
0x18011b56a  mov     [rsp+140h+var_120], rax; unsigned __int64 *
0x18011b56f  mov     r9d, [rbx+14h]; int
0x18011b573  mov     r8d, r15d; unsigned __int64
0x18011b576  mov     rcx, r14; this
0x18011b579  call    ?WriteNonNullPrefix@CDataFileWriter@@QEAAJK_KHPEA_K@Z; CDataFileWriter::WriteNonNullPrefix(ulong,unsigned __int64,int,unsigned __int64 *)
0x18011b57e  mov     esi, eax
0x18011b580  mov     edi, eax
0x18011b582  test    eax, eax
0x18011b584  js      loc_18011BC70
0x18011b58a  mov     r15, qword ptr [rbp+40h+var_98]
0x18011b58e  mov     rax, [r14]
0x18011b591  lea     r8, [rbp+40h+var_90]
0x18011b595  mov     edx, r15d
0x18011b598  mov     rcx, r14
0x18011b59b  mov     rax, [rax+10h]
0x18011b59f  call    cs:__guard_dispatch_icall_fptr
0x18011b5a5  mov     esi, eax
0x18011b5a7  mov     edi, eax
0x18011b5a9  test    eax, eax
0x18011b5ab  js      loc_18011BC8B
0x18011b5b1  cmp     dword ptr [rbx+10h], 0
0x18011b5b5  jnz     short loc_18011B5EE
0x18011b5b7  cmp     dword ptr [rbx+4], 0
0x18011b5bb  jnz     short loc_18011B5EE
0x18011b5bd  movsxd  rax, dword ptr [rbx+14h]
0x18011b5c1  cmp     rax, r15
0x18011b5c4  jbe     short loc_18011B5EE
0x18011b5c6  lfence
0x18011b5c9  movsxd  rdx, dword ptr [rbx+14h]
0x18011b5cd  sub     rdx, qword ptr [rbp+40h+var_98]
0x18011b5d1  mov     rcx, r14
0x18011b5d4  call    ??$WritePadding@E$0A@@CDataFileWriter@@QEAAJ_K@Z; CDataFileWriter::WritePadding<uchar,0>(unsigned __int64)
0x18011b5d9  mov     esi, eax
0x18011b5db  mov     edi, eax
0x18011b5dd  test    eax, eax
0x18011b5df  jns     short loc_18011B5EE
0x18011b5e1  test    byte ptr cs:_bidGblFlags, 2
0x18011b5e8  jnz     loc_18011BC84
0x18011b5ee  mov     edi, esi
0x18011b5f0  test    esi, esi
0x18011b5f2  js      loc_18011BCAF
0x18011b5f8  jmp     loc_18011BC08
0x18011b5fd  xor     esi, esi; jumptable 000000018011B4BB case 144
0x18011b5ff  mov     [rbp+40h+var_98], esi
0x18011b602  xorps   xmm0, xmm0
0x18011b605  movups  xmmword ptr [rbp+40h+var_70], xmm0
0x18011b609  movups  [rbp+40h+var_60], xmm0
0x18011b60d  mov     [rbp+40h+var_70], rsi
0x18011b611  mov     [rbp+40h+var_70+8], rsi
0x18011b615  mov     qword ptr [rbp+40h+var_60], rsi
0x18011b619  mov     qword ptr [rbp+40h+var_60+8], rsi
0x18011b61d  movdqu  [rbp+40h+var_50], xmm0
  ... truncated ...
```
