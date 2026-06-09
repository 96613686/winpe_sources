# CIStreamMultipleResults::Read(void *,ulong,ulong *)

- ea: `0x180125150`
- end: `0x180126084`
- name: `?Read@CIStreamMultipleResults@@UEAAJPEAXKPEAK@Z`
- size: `3892`
- prototype: `int(CIStreamMultipleResults *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180003030`
- `0x180003824`
- `0x180003d80`
- `0x18000bc00`
- `0x180013360`
- `0x180056690`
- `0x180123bb0`
- `0x180124880`
- `0x180125150`
- `0x18012e4e0`
- `0x18012e590`
- `0x18012e5e0`
- `0x18012e810`
- `0x1801a65e1`
- `0x1801a65f0`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180125cf8`
- `KERNEL32!GetLastError` at `0x180125cf8`
- `KERNEL32!MultiByteToWideChar` at `0x180125c8e`
- `KERNEL32!MultiByteToWideChar` at `0x180125cee`
- `KERNEL32!MultiByteToWideChar` at `0x180125c8e`
- `KERNEL32!MultiByteToWideChar` at `0x180125cee`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180125750`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1801257f8`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18012594a`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18012597e`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180125991`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180125750`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1801257f8`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18012594a`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18012597e`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180125991`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18012575c`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180125804`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18012599d`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18012575c`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180125804`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18012599d`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180125aa2`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180125aa2`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1801251a2`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180125ad3`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1801251a2`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180125ad3`

## string_xrefs

- `0x180125621`: `<?xml version="1.0" encoding="%s" ?>`
- `0x1801255d6`: `<?xml version="1.0" encoding="%S" ?>`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CIStreamMultipleResults::Read(
        CIStreamMultipleResults *this,
        char *a2,
        unsigned int a3,
        unsigned int *a4)
{
  char *v5; // rsi
  unsigned int StreamOverRowset; // ebx
  unsigned int v8; // r13d
  int v9; // eax
  const wchar_t *v10; // rax
  const wchar_t *v11; // rbx
  const wchar_t *v12; // rdx
  unsigned __int64 v13; // rax
  _WORD *v14; // rcx
  __int64 v15; // rdx
  __int16 v16; // ax
  _WORD *v17; // rax
  _DWORD *v18; // r15
  int WideCharToMultiByteInfo; // eax
  __int64 v20; // rax
  int v21; // eax
  int v22; // eax
  unsigned int v23; // eax
  int v24; // eax
  __int64 v25; // rcx
  int v26; // eax
  char *v27; // rsi
  __int64 v28; // rax
  char *v29; // rsi
  __int64 v30; // rax
  int v31; // eax
  unsigned __int64 v32; // rcx
  unsigned __int64 v33; // rcx
  __int64 v34; // rdx
  _WORD *v35; // rsi
  char *v36; // rsi
  size_t v37; // r8
  const void *v38; // rdx
  __int64 v39; // rcx
  _DWORD *v40; // rsi
  void *v41; // rsi
  __int64 v42; // r8
  bool v43; // zf
  size_t v44; // r8
  const void *v45; // rdx
  __int64 (__fastcall *v46)(char *, __int64, _QWORD, int *, char *, IErrorInfo **); // rax
  __int64 v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // rdx
  unsigned int v50; // ecx
  size_t v51; // rsi
  __int64 v52; // r15
  char *v53; // rcx
  __int64 v54; // rdx
  int v55; // eax
  unsigned int v56; // r14d
  IErrorInfo *v57; // rdx
  __int64 v58; // rcx
  void *v59; // rsi
  int v60; // eax
  CBinXMLConvert *v61; // rax
  IErrorInfo *v62; // rax
  unsigned int v63; // eax
  int v64; // eax
  __int64 v65; // rcx
  __int64 (__fastcall *v66)(__int64, CHAR *, __int64, int *); // rax
  int v67; // eax
  signed int LastError; // eax
  unsigned int v69; // ecx
  int v70; // eax
  __int64 v71; // rax
  __int64 v72; // rsi
  __int64 v73; // r14
  __int64 v74; // rax
  struct IRowset *v78; // [rsp+50h] [rbp-B0h] BYREF
  int cbMultiByte[2]; // [rsp+58h] [rbp-A8h] BYREF
  IErrorInfo *pperrinfo; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v81; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v82; // [rsp+6Ch] [rbp-94h] BYREF
  CHAR MultiByteStr[1040]; // [rsp+70h] [rbp-90h] BYREF

  v5 = a2;
  StreamOverRowset = 0;
  v78 = 0;
  v8 = 0;
  SetErrorInfo(0, 0);
  if ( v5 )
  {
    if ( !a3 )
      goto LABEL_218;
    while ( 1 )
    {
      if ( StreamOverRowset == 1 )
        goto LABEL_218;
      v81 = 0;
      switch ( *((_DWORD *)this + 16) )
      {
        case 0:
          v10 = (const wchar_t *)(*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64))(**((_QWORD **)this + 5)
                                                                                              + 96LL))(
                                   *((_QWORD *)this + 5),
                                   12,
                                   -1,
                                   9);
          v11 = v10;
          *((_QWORD *)this + 972) = v10;
          v82 = 0;
          if ( !v10 )
            goto LABEL_227;
          v12 = v10;
          v13 = *v10;
          if ( (_WORD)v13 && (*((_BYTE *)(&g_apCharTables)[v13 >> 8] + (unsigned __int8)v13) & 4) != 0 )
            v12 = ParseNameToken(v11, &v82);
          if ( *v12 || v12 == v11 )
          {
            if ( (bidGblFlags & 2) != 0 )
              StreamOverRowset = bidTraceHR(off_180260608[0], 961545, 2147500037LL);
            else
              StreamOverRowset = -2147467259;
            InternalPostSQLXMLError(StreamOverRowset, &IID_ICommand, 0x234u);
          }
          else
          {
LABEL_227:
            if ( (*(unsigned int (__fastcall **)(CIStreamMultipleResults *, __int64))(*(_QWORD *)this + 56LL))(this, 16) )
            {
              v14 = (_WORD *)((char *)this + 96);
              v15 = 255;
              do
              {
                if ( v15 == -2147483391 )
                  break;
                v16 = *(_WORD *)((char *)v14 + (char *)L"UCS-2" - ((char *)this + 96));
                if ( !v16 )
                  break;
                *v14++ = v16;
                --v15;
              }
              while ( v15 );
              v17 = v14 - 1;
              if ( v15 )
                v17 = v14;
              *v17 = 0;
            }
            v18 = (_DWORD *)((char *)this + 7804);
            WideCharToMultiByteInfo = CharEncoder::getWideCharToMultiByteInfo(
                                        (const wchar_t *)this + 48,
                                        (unsigned int *)this + 1951,
                                        (int (**)(unsigned int *, unsigned int, wchar_t *, unsigned int *, unsigned __int8 *, unsigned int *))this
                                      + 977,
                                        (unsigned int *)this + 1953);
            StreamOverRowset = WideCharToMultiByteInfo;
            _mm_lfence();
            if ( WideCharToMultiByteInfo >= 0 )
            {
              if ( (*(unsigned int (__fastcall **)(CIStreamMultipleResults *, __int64))(*(_QWORD *)this + 56LL))(
                     this,
                     1)
                && *((_QWORD *)this + 972)
                && (_mm_lfence(), **((_WORD **)this + 972)) )
              {
                _mm_lfence();
                v20 = -1;
                do
                  ++v20;
                while ( *(_WORD *)(*((_QWORD *)this + 972) + 2 * v20) );
                *((_QWORD *)this + 974) = v20;
                if ( *v18 == 1200 || (v21 = 3, *v18 == 12000) )
                  v21 = 2;
                *((_DWORD *)this + 16) = v21;
              }
              else
              {
                *((_DWORD *)this + 16) = 6;
              }
              goto LABEL_34;
            }
            InternalPostSQLXMLError(WideCharToMultiByteInfo, &IID_ICommand, 0x22Eu);
            *((_QWORD *)this + 977) = 0;
            *v18 = -1;
            *((_DWORD *)this + 1953) = 3;
            if ( (bidGblFlags & 2) != 0 )
            {
              _mm_lfence();
              bidTraceHR(off_180260608[0], 982025, StreamOverRowset);
            }
          }
          goto LABEL_218;
        case 2:
          if ( *((_QWORD *)this + 974) )
          {
            v24 = 3;
          }
          else if ( StreamOverRowset )
          {
            v24 = 10;
            if ( StreamOverRowset == 265929 )
              v24 = 12;
          }
          else
          {
            v24 = 6;
            if ( *((_QWORD *)this + 7) )
              v24 = 9;
          }
          *((_DWORD *)this + 17) = v24;
          v25 = *((_QWORD *)this + 7);
          if ( v25
            && (*(unsigned int (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v25 + 56LL))(
                 v25,
                 2,
                 -1,
                 9)
            && !(*(unsigned int (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 7) + 56LL))(
                  *((_QWORD *)this + 7),
                  32) )
          {
            *((_DWORD *)this + 16) = *((_DWORD *)this + 17);
          }
          else
          {
            *((_DWORD *)this + 16) = 8;
            if ( *((_DWORD *)this + 1951) == 12000 )
            {
              *((_QWORD *)this + 11) = byte_1801E3A30;
              *((_QWORD *)this + 10) = 4;
            }
            else
            {
              *((_QWORD *)this + 11) = &dword_1801E3A2C;
              *((_QWORD *)this + 10) = 2;
            }
          }
          goto LABEL_111;
        case 3:
          *((_DWORD *)this + 16) = 8;
          *((_DWORD *)this + 17) = 4;
          v26 = *((_DWORD *)this + 1951);
          if ( v26 == 1200 || v26 == 12000 )
          {
            v29 = (char *)this + 606;
            if ( (int)StringCchPrintfW(
                        (wchar_t *)this + 303,
                        1025,
                        L"<?xml version=\"1.0\" encoding=\"%s\" ?>",
                        (char *)this + 96) < 0 )
            {
              if ( (bidGblFlags & 2) != 0 )
              {
                StreamOverRowset = bidTraceHR(off_180260608[0], 1139721, 2147549183LL);
                goto LABEL_218;
              }
LABEL_209:
              StreamOverRowset = -2147418113;
              goto LABEL_218;
            }
            _mm_lfence();
            v30 = -1;
            do
              ++v30;
            while ( *(_WORD *)&v29[2 * v30] );
            *((_QWORD *)this + 10) = 2 * v30;
            if ( *((_DWORD *)this + 1951) == 12000 )
              *((_DWORD *)this + 16) = 7;
            *((_QWORD *)this + 11) = v29;
          }
          else
          {
            v27 = (char *)this + 606;
            if ( (int)StringCchPrintfA(
                        (char *)this + 606,
                        1025,
                        "<?xml version=\"1.0\" encoding=\"%S\" ?>",
                        (const wchar_t *)this + 48) < 0 )
            {
              if ( (bidGblFlags & 2) != 0 )
              {
                StreamOverRowset = bidTraceHR(off_180260608[0], 1155081, 2147549183LL);
                goto LABEL_218;
              }
              goto LABEL_209;
            }
            _mm_lfence();
            v28 = -1;
            do
              ++v28;
            while ( v27[v28] );
            *((_QWORD *)this + 10) = v28;
            *((_QWORD *)this + 11) = v27;
          }
          goto LABEL_111;
        case 4:
          *((_DWORD *)this + 16) = 7;
          if ( StreamOverRowset )
          {
            v31 = 10;
            if ( StreamOverRowset == 265929 )
              v31 = 5;
          }
          else if ( *((_QWORD *)this + 7) )
          {
            v31 = 9;
          }
          else
          {
            v31 = (*((_QWORD *)this + 6) != 0) + 5;
          }
          *((_DWORD *)this + 17) = v31;
          v32 = *((_QWORD *)this + 974);
          if ( v32 <= 0x3FD )
          {
            v35 = (_WORD *)((char *)this + 606);
          }
          else
          {
            if ( v32 > 0xFFFFFFFFFFFFFFFCuLL )
            {
              *((_QWORD *)this + 973) = 0;
LABEL_213:
              if ( (bidGblFlags & 2) != 0 )
              {
                StreamOverRowset = bidTraceHR(off_180260608[0], 1186825, 2147942414LL);
                goto LABEL_218;
              }
              goto LABEL_215;
            }
            v33 = v32 + 3;
            v34 = 2 * v33;
            if ( !is_mul_ok(v33, 2u) )
              v34 = -1;
            v35 = (_WORD *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64, __int64, __int64))(*(_QWORD *)g_pMO + 112LL))(
                             g_pMO,
                             v34,
                             -1,
                             9);
            *((_QWORD *)this + 973) = v35;
            if ( !v35 )
              goto LABEL_213;
          }
          *((_QWORD *)this + 11) = v35;
          *v35 = 60;
          v36 = (char *)(v35 + 1);
          v37 = 2LL * *((_QWORD *)this + 974);
          v38 = (const void *)*((_QWORD *)this + 972);
          if ( !v37 )
            goto LABEL_96;
          if ( !v36 )
            goto LABEL_95;
          if ( v38 )
          {
            memcpy_0(v36, v38, v37);
          }
          else
          {
            memset_0(v36, 0, v37);
LABEL_95:
            *_errno() = 22;
            _invalid_parameter_noinfo();
          }
LABEL_96:
          v39 = 2LL * *((_QWORD *)this + 974);
          *((_QWORD *)this + 10) = v39 + 4;
          *(_WORD *)&v36[v39] = 62;
          goto LABEL_111;
        case 5:
          *((_DWORD *)this + 16) = 7;
          *((_DWORD *)this + 17) = 12;
          if ( (unsigned __int64)(*((_QWORD *)this + 974) + 3LL) <= 0x400 )
            v40 = (_DWORD *)((char *)this + 606);
          else
            v40 = (_DWORD *)*((_QWORD *)this + 973);
          *((_QWORD *)this + 11) = v40;
          *v40 = 3080252;
          v41 = v40 + 1;
          v42 = *((_QWORD *)this + 974);
          v43 = 2 * v42 == 0;
          v44 = 2 * v42;
          v45 = (const void *)*((_QWORD *)this + 972);
          if ( v43 )
            goto LABEL_106;
          if ( !v41 )
            goto LABEL_105;
          if ( v45 )
          {
            memcpy_0(v41, v45, v44);
          }
          else
          {
            memset_0(v41, 0, v44);
LABEL_105:
            *_errno() = 22;
            _invalid_parameter_noinfo();
          }
LABEL_106:
          *((_WORD *)v41 + *((_QWORD *)this + 974)) = 62;
          *((_QWORD *)this + 10) = 2LL * *((_QWORD *)this + 974) + 6;
          goto LABEL_111;
        case 6:
LABEL_34:
          if ( !*((_QWORD *)this + 6) )
          {
            v22 = 12;
            if ( *((_QWORD *)this + 974) )
              v22 = 4;
            *((_DWORD *)this + 16) = v22;
            goto LABEL_111;
          }
          while ( 1 )
          {
            v23 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, GUID *, _QWORD, struct IRowset **))(**((_QWORD **)this + 6) + 24LL))(
                    *((_QWORD *)this + 6),
                    0,
                    0,
                    &IID_IRowset,
                    0,
                    &v78);
            StreamOverRowset = v23;
            if ( v23 )
              break;
            if ( v78 )
            {
              StreamOverRowset = CreateStreamOverRowset(v78, (struct ISequentialStream **)this + 7);
              if ( v78 )
              {
                ((void (__fastcall *)(struct IRowset *))v78->lpVtbl->Release)(v78);
                v78 = 0;
              }
LABEL_47:
              if ( *((_DWORD *)this + 16) == 6 )
                *((_DWORD *)this + 16) = (StreamOverRowset != 0) + 9;
              goto LABEL_111;
            }
          }
          if ( v23 != 265929 )
          {
            if ( v23 == -2147217915 )
              *((_BYTE *)this + 7801) = 1;
            goto LABEL_47;
          }
          if ( *((_DWORD *)this + 16) == 6 )
          {
            StreamOverRowset = 0;
LABEL_134:
            v55 = 12;
            if ( *((_QWORD *)this + 974) )
              v55 = 5;
            *((_DWORD *)this + 16) = v55;
          }
          goto LABEL_111;
        case 7:
          v46 = (__int64 (__fastcall *)(char *, __int64, _QWORD, int *, char *, IErrorInfo **))*((_QWORD *)this + 977);
          if ( !v46 )
            goto LABEL_117;
          v47 = *((unsigned int *)this + 1951);
          if ( (_DWORD)v47 == 1200 )
            goto LABEL_117;
          *(_QWORD *)cbMultiByte = *((_QWORD *)this + 10) >> 1;
          pperrinfo = (IErrorInfo *)5120;
          v9 = v46((char *)this + 7808, v47, *((_QWORD *)this + 11), cbMultiByte, (char *)this + 2656, &pperrinfo);
          if ( v9 < 0 )
            goto LABEL_4;
          *((_QWORD *)this + 10) = pperrinfo;
          *((_QWORD *)this + 11) = (char *)this + 2656;
LABEL_117:
          *((_DWORD *)this + 16) = 8;
LABEL_118:
          v48 = *((_QWORD *)this + 10);
          v49 = *((_QWORD *)this + 9);
          if ( a3 >= (unsigned __int64)(v48 - v49) )
            v50 = v48 - v49;
          else
            v50 = a3;
          v81 = v50;
          v51 = v50;
          v52 = v49 + *((_QWORD *)this + 11);
          v53 = &a2[v8];
          if ( !v51 )
            goto LABEL_131;
          if ( !v53 )
            goto LABEL_123;
          if ( v52 && a3 >= v51 )
          {
            memcpy_0(v53, (const void *)(v49 + *((_QWORD *)this + 11)), v51);
            goto LABEL_131;
          }
          memset_0(v53, 0, a3);
          if ( v52 )
          {
            if ( a3 >= v51 )
              goto LABEL_131;
            *_errno() = 34;
          }
          else
          {
LABEL_123:
            *_errno() = 22;
          }
          _invalid_parameter_noinfo();
LABEL_131:
          v54 = v81 + *((_QWORD *)this + 9);
          *((_QWORD *)this + 9) = v54;
          if ( v54 == *((_QWORD *)this + 10) )
          {
            *((_DWORD *)this + 16) = *((_DWORD *)this + 17);
            *((_QWORD *)this + 10) = 0;
            *((_QWORD *)this + 9) = 0;
          }
          goto LABEL_110;
        case 8:
          goto LABEL_118;
        case 9:
          if ( !*((_QWORD *)this + 6) )
            goto LABEL_134;
          if ( (*(unsigned int (__fastcall **)(_QWORD, __int64, __int64, __int64))(**((_QWORD **)this + 7) + 56LL))(
                 *((_QWORD *)this + 7),
                 4,
                 -1,
                 9)
            && *((_DWORD *)this + 1951) == 1200
            || (*(unsigned int (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 7) + 56LL))(
                 *((_QWORD *)this + 7),
                 2)
            && !(*(unsigned int (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 7) + 56LL))(
                  *((_QWORD *)this + 7),
                  32) )
          {
            StreamOverRowset = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD, unsigned int *))(**((_QWORD **)this + 7)
                                                                                                 + 24LL))(
                                 *((_QWORD *)this + 7),
                                 &v5[v8],
                                 a3,
                                 &v81);
            goto LABEL_142;
          }
          cbMultiByte[0] = 0;
          if ( (*(unsigned int (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 7) + 56LL))(
                 *((_QWORD *)this + 7),
                 2) )
          {
            v61 = (CBinXMLConvert *)*((_QWORD *)this + 982);
            if ( v61
              || ((v62 = (IErrorInfo *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)g_pMO + 88LL))(
                                         g_pMO,
                                         1024),
                   (pperrinfo = v62) == 0)
                ? (v61 = 0)
                : (v61 = CBinXMLConvert::CBinXMLConvert((CBinXMLConvert *)v62)),
                  (*((_QWORD *)this + 982) = v61) != 0) )
            {
              v63 = CBinXMLConvert::ConvertBinaryXML(
                      v61,
                      *((struct ISequentialStream **)this + 7),
                      *((struct ISQLXMLHelper **)this + 5),
                      (wchar_t *)this + 303,
                      (unsigned int *)cbMultiByte);
            }
            else
            {
              if ( (bidGblFlags & 2) == 0 )
              {
                StreamOverRowset = -2147024882;
                goto LABEL_180;
              }
              v63 = bidTraceHR(off_180260608[0], 1490953, 2147942414LL);
            }
          }
          else
          {
            v64 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 7) + 56LL))(
                    *((_QWORD *)this + 7),
                    8);
            v65 = *((_QWORD *)this + 7);
            v43 = v64 == 0;
            v66 = *(__int64 (__fastcall **)(__int64, CHAR *, __int64, int *))(*(_QWORD *)v65 + 24LL);
            if ( !v43 )
            {
              StreamOverRowset = v66(v65, MultiByteStr, 1024, cbMultiByte);
              if ( StreamOverRowset )
                goto LABEL_176;
              v67 = cbMultiByte[0];
              if ( cbMultiByte[0] )
              {
                LODWORD(pperrinfo) = 0;
                if ( !MultiByteToWideChar(0, 0, MultiByteStr, cbMultiByte[0], (LPWSTR)this + 303, 1025) )
                {
                  StreamOverRowset = (*(__int64 (__fastcall **)(_QWORD, CHAR *, __int64, IErrorInfo **))(**((_QWORD **)this + 7) + 24LL))(
                                       *((_QWORD *)this + 7),
                                       &MultiByteStr[cbMultiByte[0] - 1],
                                       1,
                                       &pperrinfo);
                  if ( !StreamOverRowset
                    && (!(_DWORD)pperrinfo
                     || !MultiByteToWideChar(
                           0,
                           0,
                           MultiByteStr,
                           (_DWORD)pperrinfo + cbMultiByte[0],
                           (LPWSTR)this + 303,
                           1025)) )
                  {
                    LastError = GetLastError();
                    StreamOverRowset = LastError;
                    if ( LastError > 0 )
                      StreamOverRowset = (unsigned __int16)LastError | 0x80070000;
                  }
                }
LABEL_176:
                v67 = cbMultiByte[0];
              }
              v69 = 2 * v67;
              goto LABEL_181;
            }
            v63 = v66(v65, (CHAR *)this + 606, 2050, cbMultiByte);
          }
          StreamOverRowset = v63;
LABEL_180:
          v69 = cbMultiByte[0];
LABEL_181:
          if ( !StreamOverRowset && v69 )
          {
            *((_DWORD *)this + 16) = 7;
            *((_QWORD *)this + 11) = (char *)this + 606;
            *((_QWORD *)this + 10) = v69;
            *((_DWORD *)this + 17) = 9;
            goto LABEL_111;
          }
LABEL_142:
          v56 = StreamOverRowset;
          if ( StreamOverRowset == -2147483638 || !StreamOverRowset )
          {
            StreamOverRowset = 0;
          }
          else
          {
            v57 = 0;
            pperrinfo = 0;
            if ( StreamOverRowset != 1 )
            {
              GetErrorInfo(0, &pperrinfo);
              v57 = pperrinfo;
            }
            v58 = *((_QWORD *)this + 7);
            if ( v58 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
              *((_QWORD *)this + 7) = 0;
              v57 = pperrinfo;
            }
            if ( v57 )
            {
              SetErrorInfo(0, v57);
              if ( pperrinfo )
                ((void (__fastcall *)(IErrorInfo *))pperrinfo->lpVtbl->Release)(pperrinfo);
            }
            v59 = (void *)*((_QWORD *)this + 982);
            if ( v59 )
            {
              CBinXMLConvert::~CBinXMLConvert(*((CBinXMLConvert **)this + 982));
              operator delete(v59, 0x400u);
              *((_QWORD *)this + 982) = 0;
            }
            if ( *((_BYTE *)this + 7801) )
            {
              v60 = 12;
              if ( *((_QWORD *)this + 974) )
                v60 = 5;
              *((_DWORD *)this + 16) = v60;
            }
            else
            {
              if ( StreamOverRowset == 1 )
                StreamOverRowset = 0;
              v70 = 6;
              if ( v56 != 1 )
                v70 = 10;
              *((_DWORD *)this + 16) = v70;
            }
          }
LABEL_110:
          v8 += v81;
          a3 -= v81;
LABEL_111:
          if ( !a3 )
            goto LABEL_218;
          v5 = a2;
          break;
        case 0xA:
          v71 = (*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64, __int64, __int64))(*(_QWORD *)g_pMO + 88LL))(
                  g_pMO,
                  632,
                  -1,
                  9);
          v72 = v71;
          pperrinfo = (IErrorInfo *)v71;
          if ( v71 )
          {
            v73 = *((_QWORD *)this + 5);
            *(_QWORD *)(v71 + 24) = &CImpISeqStream::`vftable';
            *(_QWORD *)(v71 + 32) = v71;
            *(_QWORD *)(v71 + 8) = 1;
            *(_QWORD *)(v71 + 16) = v71;
            *(_QWORD *)v71 = &CIStreamError::`vftable';
            *(_DWORD *)(v71 + 40) = StreamOverRowset;
            *(_DWORD *)(v71 + 44) = 0;
            *(_BYTE *)(v71 + 48) = 0;
            *(_QWORD *)(v71 + 52) = 0;
            *(_QWORD *)(v71 + 72) = 0;
            *(_QWORD *)(v71 + 80) = 0;
            *(_DWORD *)(v71 + 88) = 0;
            *(_QWORD *)(v71 + 96) = 0;
            *(_QWORD *)(v71 + 104) = 0;
            memset_0((void *)(v71 + 112), 0, 0x200u);
            *(_QWORD *)(v72 + 624) = 0;
            *(_DWORD *)(v72 + 12) |= 4u;
            *(_QWORD *)(v72 + 64) = v73;
            if ( v73 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 8LL))(v73);
            if ( StreamOverRowset == -2147024882 )
            {
              *(_DWORD *)(v72 + 44) = 7;
              v74 = -1;
              do
                ++v74;
              while ( CIStreamError::m_outofmemory[v74] );
              *(_DWORD *)(v72 + 628) = 2 * v74;
              *(_DWORD *)(v72 + 624) = 0;
            }
          }
          else
          {
            v72 = 0;
          }
          *((_QWORD *)this + 7) = v72;
          if ( !v72 )
          {
            if ( (bidGblFlags & 2) != 0 )
            {
              StreamOverRowset = bidTraceHR(off_180260608[0], 1437705, 2147942414LL);
              goto LABEL_218;
            }
LABEL_215:
            StreamOverRowset = -2147024882;
            goto LABEL_218;
          }
          *((_DWORD *)this + 16) = 9;
          StreamOverRowset = 0;
          goto LABEL_111;
        case 0xB:
          goto LABEL_217;
        case 0xC:
          StreamOverRowset = 1;
          if ( v8
            || !*((_BYTE *)this + 7800)
            || !(*(unsigned int (__fastcall **)(_QWORD, __int64, __int64, __int64))(**((_QWORD **)this + 5) + 40LL))(
                  *((_QWORD *)this + 5),
                  12,
                  -1,
                  9) )
          {
            goto LABEL_110;
          }
          *((_DWORD *)this + 16) = 11;
LABEL_217:
          StreamOverRowset = 265946;
          goto LABEL_218;
        default:
          goto LABEL_110;
      }
    }
  }
  if ( (bidGblFlags & 2) != 0 )
  {
    v9 = bidTraceHR(off_180260608[0], 941065, 2147680265LL);
LABEL_4:
    StreamOverRowset = v9;
  }
  else
  {
    StreamOverRowset = -2147287031;
  }
LABEL_218:
  if ( a4 )
    *a4 = v8;
  if ( StreamOverRowset == 1 )
    return v8 == 0;
  return StreamOverRowset;
}

```

## disassembly

```asm
0x180125150  push    rbp
0x180125152  push    rbx
0x180125153  push    rsi
0x180125154  push    rdi
0x180125155  push    r12
0x180125157  push    r13
0x180125159  push    r14
0x18012515b  push    r15
0x18012515d  lea     rbp, [rsp-398h]
0x180125165  sub     rsp, 498h
0x18012516c  mov     rax, cs:__security_cookie
0x180125173  xor     rax, rsp
0x180125176  mov     [rbp+3D0h+var_50], rax
0x18012517d  mov     [rsp+4D0h+var_488], r9
0x180125182  mov     r12d, r8d
0x180125185  mov     rsi, rdx
0x180125188  mov     [rsp+4D0h+var_490], rdx
0x18012518d  mov     rdi, rcx
0x180125190  xor     r15d, r15d
0x180125193  mov     ebx, r15d
0x180125196  mov     [rsp+4D0h+var_480], r15
0x18012519b  mov     r13d, r15d
0x18012519e  xor     edx, edx; perrinfo
0x1801251a0  xor     ecx, ecx; dwReserved
0x1801251a2  call    cs:__imp_SetErrorInfo
0x1801251a8  test    rsi, rsi
0x1801251ab  jnz     short loc_1801251DE
0x1801251ad  test    byte ptr cs:_bidGblFlags, 2
0x1801251b4  jz      short loc_1801251D4
0x1801251b6  mov     edx, 0E5C09h
0x1801251bb  mov     r8d, 80030009h
0x1801251c1  mov     rcx, cs:off_180260608; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x1801251c8  call    _bidTraceHR
0x1801251cd  mov     ebx, eax
0x1801251cf  jmp     loc_180125FED
0x1801251d4  mov     ebx, 80030009h
0x1801251d9  jmp     loc_180125FED
0x1801251de  test    r12d, r12d
0x1801251e1  jz      loc_180125FED
0x1801251e7  lea     r14, cs:180000000h
0x1801251ee  mov     edx, 0Ch
0x1801251f3  mov     r10d, 5
0x1801251f9  mov     r9d, 9
0x1801251ff  mov     r11d, 4
0x180125205  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18012520c  cmp     ebx, 1
0x18012520f  jz      loc_180125FED
0x180125215  mov     [rsp+4D0h+var_468], r15d
0x18012521a  movsxd  rax, dword ptr [rdi+40h]
0x18012521e  cmp     eax, 0Ch; switch 13 cases
0x180125221  ja      def_180125232; jumptable 0000000180125232 default case, case 1
0x180125227  mov     ecx, ds:(jpt_180125232 - 180000000h)[r14+rax*4]
0x18012522f  add     rcx, r14
0x180125232  jmp     rcx; switch jump
0x180125234  mov     rcx, [rdi+28h]; jumptable 0000000180125232 case 0
0x180125238  mov     rax, [rcx]
0x18012523b  mov     rax, [rax+60h]
0x18012523f  call    cs:__guard_dispatch_icall_fptr
0x180125245  mov     rbx, rax
0x180125248  mov     [rdi+1E60h], rax
0x18012524f  mov     [rsp+4D0h+var_464], r15d
0x180125254  test    rax, rax
0x180125257  jz      short loc_18012529C
0x180125259  mov     rdx, rax
0x18012525c  movzx   eax, word ptr [rax]
0x18012525f  test    ax, ax
0x180125262  jz      short loc_180125289
0x180125264  movzx   ecx, al
0x180125267  shr     rax, 8
0x18012526b  mov     rax, rva ?g_apCharTables@@3PAPEAEA[r14+rax*8]; uchar * near * g_apCharTables ...
0x180125273  test    byte ptr [rcx+rax], 4
0x180125277  jz      short loc_180125289
0x180125279  lea     rdx, [rsp+4D0h+var_464]; unsigned int *
0x18012527e  mov     rcx, rbx; wchar_t *
0x180125281  call    ?ParseNameToken@@YAPEB_WPEB_WPEAK@Z; ParseNameToken(wchar_t const *,ulong *)
0x180125286  mov     rdx, rax
0x180125289  cmp     word ptr [rdx], 0
0x18012528d  jnz     loc_180125ECF
0x180125293  cmp     rdx, rbx
0x180125296  jz      loc_180125ECF
0x18012529c  mov     rax, [rdi]
0x18012529f  mov     edx, 10h
0x1801252a4  mov     rcx, rdi
0x1801252a7  mov     rax, [rax+38h]
0x1801252ab  call    cs:__guard_dispatch_icall_fptr
0x1801252b1  test    eax, eax
0x1801252b3  jz      short loc_180125302
0x1801252b5  lea     rcx, [rdi+60h]
0x1801252b9  mov     edx, 0FFh
0x1801252be  lea     r8, aUcs2; "UCS-2"
0x1801252c5  sub     r8, rcx
0x1801252c8  nop     dword ptr [rax+rax+00000000h]
0x1801252d0  lea     rax, [rdx+7FFFFEFFh]
0x1801252d7  test    rax, rax
0x1801252da  jz      short loc_1801252F3
0x1801252dc  movzx   eax, word ptr [r8+rcx]
0x1801252e1  test    ax, ax
0x1801252e4  jz      short loc_1801252F3
0x1801252e6  mov     [rcx], ax
0x1801252e9  add     rcx, 2
0x1801252ed  sub     rdx, 1
0x1801252f1  jnz     short loc_1801252D0
0x1801252f3  lea     rax, [rcx-2]
0x1801252f7  test    rdx, rdx
0x1801252fa  cmovnz  rax, rcx
0x1801252fe  mov     [rax], r15w
0x180125302  lea     rsi, [rdi+1E84h]
0x180125309  lea     r14, [rdi+1E88h]
0x180125310  lea     r15, [rdi+1E7Ch]
0x180125317  lea     rcx, [rdi+60h]; String1
0x18012531b  mov     r9, rsi; unsigned int *
0x18012531e  mov     r8, r14; int (**)(unsigned int *, unsigned int, wchar_t *, unsigned int *, unsigned __int8 *, unsigned int *)
0x180125321  mov     rdx, r15; unsigned int *
0x180125324  call    ?getWideCharToMultiByteInfo@CharEncoder@@SAJPEB_WPEAIPEAP6AJPEAKIPEA_W1PEAE1@Z1@Z; CharEncoder::getWideCharToMultiByteInfo(wchar_t const *,uint *,long (**)(ulong *,uint,wchar_t *,uint *,uchar *,uint *),uint *)
0x180125329  mov     ebx, eax
0x18012532b  lfence
0x18012532e  test    eax, eax
0x180125330  js      loc_180125F11
0x180125336  mov     rax, [rdi]
0x180125339  mov     edx, 1
0x18012533e  mov     rcx, rdi
0x180125341  mov     rax, [rax+38h]
0x180125345  call    cs:__guard_dispatch_icall_fptr
0x18012534b  test    eax, eax
0x18012534d  jz      short loc_1801253B1
0x18012534f  cmp     qword ptr [rdi+1E60h], 0
0x180125357  jz      short loc_1801253B1
0x180125359  lfence
0x18012535c  mov     rax, [rdi+1E60h]
0x180125363  cmp     word ptr [rax], 0
0x180125367  jz      short loc_1801253B1
0x180125369  lfence
0x18012536c  mov     rcx, [rdi+1E60h]
0x180125373  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18012537a  nop     word ptr [rax+rax+00h]
0x180125380  inc     rax
0x180125383  cmp     word ptr [rcx+rax*2], 0
0x180125388  jnz     short loc_180125380
0x18012538a  mov     [rdi+1E70h], rax
0x180125391  mov     eax, [r15]
0x180125394  cmp     eax, 4B0h
0x180125399  jz      short loc_1801253A7
0x18012539b  cmp     eax, 2EE0h
0x1801253a0  mov     eax, 3
0x1801253a5  jnz     short loc_1801253AC
0x1801253a7  mov     eax, 2
0x1801253ac  mov     [rdi+40h], eax
0x1801253af  jmp     short loc_1801253B8
0x1801253b1  mov     dword ptr [rdi+40h], 6
0x1801253b8  mov     r11d, 4
0x1801253be  mov     r10d, 5
0x1801253c4  mov     r9d, 9
0x1801253ca  mov     edx, 0Ch
0x1801253cf  lea     r14, cs:180000000h
0x1801253d6  xor     r15d, r15d
0x1801253d9  cmp     qword ptr [rdi+30h], 0; jumptable 0000000180125232 case 6
0x1801253de  jnz     short loc_180125400
0x1801253e0  mov     eax, edx
0x1801253e2  cmp     qword ptr [rdi+1E70h], 0
0x1801253ea  cmovnz  eax, r11d
0x1801253ee  mov     [rdi+40h], eax
0x1801253f1  jmp     loc_180125884
0x180125400  mov     rcx, [rdi+30h]
0x180125404  mov     rax, [rcx]
0x180125407  lea     rdx, [rsp+4D0h+var_480]
0x18012540c  mov     qword ptr [rsp+4D0h+cchWideChar], rdx
0x180125411  mov     [rsp+4D0h+lpWideCharStr], r15
0x180125416  lea     r9, IID_IRowset
0x18012541d  xor     r8d, r8d
0x180125420  xor     edx, edx
0x180125422  mov     rax, [rax+18h]
0x180125426  call    cs:__guard_dispatch_icall_fptr
0x18012542c  mov     ebx, eax
0x18012542e  test    eax, eax
0x180125430  jnz     short loc_180125465
0x180125432  mov     rcx, [rsp+4D0h+var_480]; struct IRowset *
0x180125437  test    rcx, rcx
0x18012543a  jz      short loc_180125400
0x18012543c  lea     rdx, [rdi+38h]; struct ISequentialStream **
0x180125440  call    ?CreateStreamOverRowset@@YAJPEAUIRowset@@PEAPEAUISequentialStream@@@Z; CreateStreamOverRowset(IRowset *,ISequentialStream * *)
0x180125445  mov     ebx, eax
0x180125447  mov     rcx, [rsp+4D0h+var_480]
0x18012544c  test    rcx, rcx
0x18012544f  jz      short loc_18012549D
0x180125451  mov     rax, [rcx]
0x180125454  mov     rax, [rax+10h]
0x180125458  call    cs:__guard_dispatch_icall_fptr
0x18012545e  mov     [rsp+4D0h+var_480], r15
0x180125463  jmp     short loc_18012549D
0x180125465  cmp     eax, 40EC9h
0x18012546a  jnz     short loc_18012548F
0x18012546c  mov     edx, 0Ch
0x180125471  mov     r10d, 5
0x180125477  mov     r9d, 9
0x18012547d  cmp     dword ptr [rdi+40h], 6
0x180125481  jnz     loc_180125884
0x180125487  mov     ebx, r15d
0x18012548a  jmp     loc_1801259E0
0x18012548f  cmp     eax, 80040E05h
0x180125494  jnz     short loc_18012549D
0x180125496  mov     byte ptr [rdi+1E79h], 1
0x18012549d  mov     edx, 0Ch
0x1801254a2  mov     r9d, 9
0x1801254a8  mov     r10d, 5
0x1801254ae  cmp     dword ptr [rdi+40h], 6
0x1801254b2  jnz     loc_180125884
0x1801254b8  mov     eax, r15d
0x1801254bb  test    ebx, ebx
0x1801254bd  setnz   al
0x1801254c0  add     eax, r9d
0x1801254c3  mov     [rdi+40h], eax
0x1801254c6  jmp     loc_180125884
0x1801254cb  cmp     qword ptr [rdi+1E70h], 0; jumptable 0000000180125232 case 2
0x1801254d3  jz      short loc_1801254DC
0x1801254d5  mov     eax, 3
0x1801254da  jmp     short loc_1801254FE
0x1801254dc  test    ebx, ebx
0x1801254de  jz      short loc_1801254F0
0x1801254e0  mov     eax, 0Ah
0x1801254e5  cmp     ebx, 40EC9h
0x1801254eb  cmovz   eax, edx
0x1801254ee  jmp     short loc_1801254FE
0x1801254f0  mov     eax, 6
0x1801254f5  cmp     qword ptr [rdi+38h], 0
0x1801254fa  cmovnz  eax, r9d
0x1801254fe  mov     [rdi+44h], eax
0x180125501  mov     rcx, [rdi+38h]
0x180125505  test    rcx, rcx
0x180125508  jz      short loc_18012556D
0x18012550a  mov     rax, [rcx]
0x18012550d  mov     edx, 2
0x180125512  mov     rax, [rax+38h]
0x180125516  call    cs:__guard_dispatch_icall_fptr
0x18012551c  test    eax, eax
0x18012551e  jz      short loc_180125556
0x180125520  mov     rcx, [rdi+38h]
0x180125524  mov     rax, [rcx]
0x180125527  mov     edx, 20h ; ' '
0x18012552c  mov     rax, [rax+38h]
0x180125530  call    cs:__guard_dispatch_icall_fptr
0x180125536  mov     edx, 0Ch
0x18012553b  mov     r9d, 9
0x180125541  mov     r10d, 5
0x180125547  test    eax, eax
0x180125549  jnz     short loc_180125567
0x18012554b  mov     eax, [rdi+44h]
0x18012554e  mov     [rdi+40h], eax
0x180125551  jmp     loc_180125884
0x180125556  mov     edx, 0Ch
0x18012555b  mov     r9d, 9
0x180125561  mov     r10d, 5
0x180125567  mov     r11d, 4
0x18012556d  mov     dword ptr [rdi+40h], 8
0x180125574  cmp     dword ptr [rdi+1E7Ch], 2EE0h
0x18012557e  jnz     short loc_180125594
0x180125580  lea     rax, byte_1801E3A30
0x180125587  mov     [rdi+58h], rax
0x18012558b  mov     [rdi+50h], r11
0x18012558f  jmp     loc_180125884
0x180125594  lea     rax, dword_1801E3A2C
0x18012559b  mov     [rdi+58h], rax
0x18012559f  mov     qword ptr [rdi+50h], 2
0x1801255a7  jmp     loc_180125884
0x1801255ac  mov     dword ptr [rdi+40h], 8; jumptable 0000000180125232 case 3
0x1801255b3  mov     [rdi+44h], r11d
0x1801255b7  mov     eax, [rdi+1E7Ch]
0x1801255bd  cmp     eax, 4B0h
0x1801255c2  jz      short loc_180125616
0x1801255c4  cmp     eax, 2EE0h
0x1801255c9  jz      short loc_180125616
0x1801255cb  lea     rsi, [rdi+25Eh]
0x1801255d2  lea     r9, [rdi+60h]
0x1801255d6  lea     r8, aXmlVersion10En; "<?xml version=\"1.0\" encoding=\"%S\" ?"...
0x1801255dd  mov     edx, 401h; unsigned __int64
0x1801255e2  mov     rcx, rsi; Buffer
0x1801255e5  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1801255ea  test    eax, eax
0x1801255ec  js      loc_180125F60
0x1801255f2  lfence
0x1801255f5  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1801255fc  nop     dword ptr [rax+00h]
0x180125600  inc     rax
0x180125603  cmp     byte ptr [rsi+rax], 0
0x180125607  jnz     short loc_180125600
0x180125609  mov     [rdi+50h], rax
0x18012560d  mov     [rdi+58h], rsi
0x180125611  jmp     loc_18012577B
0x180125616  lea     rsi, [rdi+25Eh]
0x18012561d  lea     r9, [rdi+60h]
0x180125621  lea     r8, aXmlVersion10En_0; "<?xml version=\"1.0\" encoding=\"%s\" ?"...
0x180125628  mov     edx, 401h; unsigned __int64
0x18012562d  mov     rcx, rsi; Buffer
0x180125630  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180125635  test    eax, eax
0x180125637  js      loc_180125F8B
0x18012563d  lfence
0x180125640  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180125647  nop     word ptr [rax+rax+00000000h]
0x180125650  inc     rax
0x180125653  cmp     word ptr [rsi+rax*2], 0
  ... truncated ...
```
