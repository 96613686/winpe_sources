# GetScenariosList(std::set<_GUID_BUFFER,lessGuidBuffer,std::allocator<_GUID_BUFFER>> &)

- ea: `0x14000e924`
- end: `0x14000f653`
- name: `?GetScenariosList@@YAJAEAV?$set@U_GUID_BUFFER@@UlessGuidBuffer@@V?$allocator@U_GUID_BUFFER@@@std@@@std@@@Z`
- size: `3375`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x14000c47c`

## callees

- `0x140001414`
- `0x140001990`
- `0x14000b5c4`
- `0x14000bbc4`
- `0x14000d7cc`
- `0x14000dd30`
- `0x14000e750`
- `0x14000e924`
- `0x1400172c4`
- `0x1400187b2`
- `0x1400187e0`
- `0x140019010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14000e9c9`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000e9c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f5f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f5f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000f5fe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000f5fe`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x14000f2b4`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x14000f2d2`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x14000f2b4`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x14000f2d2`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x14000ebcf`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x14000ebcf`
- `XmlLite!CreateXmlReader` at `0x14000ed09`
- `XmlLite!CreateXmlReader` at `0x14000ed09`

## string_xrefs

- `0x14000ea74`: `GetDiagTrackStorePath failed.`
- `0x14000ead4`: `downloadedscenarios\windows.siuf.xml`
- `0x14000ebfa`: `Attempted to open manifest`
- `0x14000ecac`: `Failed to create a stream on the manifest.`
- `0x14000ed86`: `CreateXmlReader failed.`
- `0x14000ee63`: `reader->SetProperty failed.`
- `0x14000ef3d`: `reader->SetInput failed.`
- `0x14000f24c`: `GetQuestionIdFromSifActionNode failed`
- `0x14000f4eb`: `Unexpected result from IXmlReader->Read`

## pseudocode

```c
__int64 __fastcall GetScenariosList(_QWORD *a1)
{
  int v2; // r13d
  _QWORD *v3; // rdi
  _QWORD *i; // rbx
  __int64 v5; // rdx
  HRESULT DiagTrackStorePath; // edi
  int v7; // r8d
  int v8; // r9d
  int v9; // r8d
  int v10; // r9d
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  int v14; // r8d
  int v15; // r9d
  int v16; // r8d
  int v17; // r9d
  int v18; // r8d
  int v19; // r9d
  int v20; // r8d
  int v21; // r9d
  int v22; // r8d
  int v23; // r9d
  __int64 v24; // r8
  _WORD *v25; // rcx
  const wchar_t *v26; // rdx
  __int64 v27; // rax
  signed int ScenarioId; // r8d
  int v29; // r9d
  __int64 v30; // r8
  _WORD *v31; // rcx
  const wchar_t *v32; // rdx
  signed int QuestionDetails; // edi
  int v34; // r8d
  int v35; // r9d
  unsigned int v36; // eax
  __int64 v37; // r8
  WCHAR *v38; // r9
  char *v39; // rdx
  signed int v40; // r8d
  int v41; // r9d
  __int64 v42; // r8
  _WORD *v43; // rcx
  const wchar_t *v44; // rdx
  void *v45; // r12
  HANDLE ProcessHeap; // rax
  int v48; // [rsp+20h] [rbp-E0h]
  unsigned int v49; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v50; // [rsp+58h] [rbp-A8h] BYREF
  const char *v51; // [rsp+60h] [rbp-A0h] BYREF
  const char *v52; // [rsp+68h] [rbp-98h] BYREF
  int v53[2]; // [rsp+70h] [rbp-90h] BYREF
  const char *v54; // [rsp+78h] [rbp-88h] BYREF
  const char *v55; // [rsp+80h] [rbp-80h] BYREF
  const char *v56; // [rsp+88h] [rbp-78h] BYREF
  const char *v57; // [rsp+90h] [rbp-70h] BYREF
  __int64 v58; // [rsp+98h] [rbp-68h] BYREF
  void *ppvObject; // [rsp+A0h] [rbp-60h] BYREF
  int v60; // [rsp+A8h] [rbp-58h] BYREF
  _WORD *v61; // [rsp+B0h] [rbp-50h] BYREF
  IStream *ppstm; // [rsp+B8h] [rbp-48h] BYREF
  LPVOID lpMem; // [rsp+C0h] [rbp-40h] BYREF
  char v64; // [rsp+C8h] [rbp-38h] BYREF
  char v65; // [rsp+D8h] [rbp-28h] BYREF
  WCHAR sz[40]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR v67[40]; // [rsp+140h] [rbp+40h] BYREF
  WCHAR pszFile[264]; // [rsp+190h] [rbp+90h] BYREF

  ppvObject = 0;
  v60 = 0;
  ppstm = 0;
  v61 = 0;
  v2 = 0;
  v53[0] = 0;
  memset_0(v67, 0, 0x4Au);
  memset_0(sz, 0, 0x4Au);
  memset_0(pszFile, 0, 0x208u);
  lpMem = 0;
  v3 = *(_QWORD **)(*a1 + 8LL);
  for ( i = v3; !*((_BYTE *)i + 25); v3 = i )
  {
    std::_Tree<std::_Tset_traits<_GUID_BUFFER,lessGuidBuffer,std::allocator<_GUID_BUFFER>,0>>::_Erase(a1, i[2]);
    i = (_QWORD *)*i;
    operator delete(v3);
  }
  *(_QWORD *)(*a1 + 8LL) = *a1;
  *(_QWORD *)*a1 = *a1;
  *(_QWORD *)(*a1 + 16LL) = *a1;
  a1[1] = 0;
  DiagTrackStorePath = GetDiagTrackStorePath((unsigned __int16 **)&lpMem);
  if ( DiagTrackStorePath >= 0 )
  {
    memset_0(pszFile, 0, 0x208u);
    DiagTrackStorePath = StringCchPrintfW(pszFile, 0x104u, L"%s\\%s", lpMem, L"downloadedscenarios\\windows.siuf.xml");
    if ( DiagTrackStorePath >= 0 )
    {
      DiagTrackStorePath = SHCreateStreamOnFileW(pszFile, 0, &ppstm);
      if ( DiagTrackStorePath >= 0 )
      {
        if ( ppstm )
        {
          DiagTrackStorePath = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
          if ( DiagTrackStorePath >= 0 )
          {
            DiagTrackStorePath = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 40LL))(
                                   ppvObject,
                                   4);
            if ( DiagTrackStorePath >= 0 )
            {
              DiagTrackStorePath = (*(__int64 (__fastcall **)(void *, IStream *))(*(_QWORD *)ppvObject + 24LL))(
                                     ppvObject,
                                     ppstm);
              if ( DiagTrackStorePath >= 0 )
              {
                LODWORD(v54) = 0;
                LODWORD(v51) = 0;
                LODWORD(v52) = 0;
LABEL_37:
                while ( 1 )
                {
                  DiagTrackStorePath = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 48LL))(
                                         ppvObject,
                                         &v60);
                  if ( DiagTrackStorePath )
                    break;
                  if ( v60 == 1 )
                  {
                    v22 = (*(__int64 (__fastcall **)(void *, _WORD **, _QWORD))(*(_QWORD *)ppvObject + 112LL))(
                            ppvObject,
                            &v61,
                            0);
                    if ( v22 >= 0 )
                    {
                      if ( (_DWORD)v52 )
                      {
                        v30 = 7;
                        v31 = v61;
                        v32 = L"sifData";
                        do
                        {
                          if ( *v32 != *v31 )
                            goto LABEL_37;
                          ++v32;
                          ++v31;
                          --v30;
                        }
                        while ( v30 );
                        v49 = 1;
                        QuestionDetails = GetQuestionDetails((struct IXmlReader *)ppvObject, &v49, sz);
                        if ( QuestionDetails >= 0 )
                        {
                          v36 = v49;
                        }
                        else
                        {
                          if ( (unsigned int)dword_140027000 > 2
                            && (qword_140027010 & 0x400000000000LL) != 0
                            && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
                          {
                            v58 = 0x1000000;
                            LODWORD(v50) = 405;
                            v57 = "GetScenariosList";
                            v56 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\telman\\telman.cpp";
                            v49 = QuestionDetails;
                            v55 = "GetQuestionIdFromSifActionNode failed";
                            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                              qword_140027010,
                              (unsigned int)&unk_140021460,
                              v34,
                              v35,
                              (__int64)&v55,
                              (__int64)&v49,
                              (__int64)&v56,
                              (__int64)&v57,
                              (__int64)&v50,
                              (__int64)&v58);
                          }
                          v36 = 1;
                        }
                        if ( v36 >= 2 )
                        {
                          CharLowerBuffW(sz, 0x24u);
                          v38 = sz;
                          v39 = &v64;
LABEL_73:
                          LOBYTE(v48) = byte_140027C28;
                          std::_Tree<std::_Tset_traits<_GUID_BUFFER,lessGuidBuffer,std::allocator<_GUID_BUFFER>,0>>::_Insert_nohint<_GUID_BUFFER const &,std::_Nil>(
                            a1,
                            v39,
                            v37,
                            v38,
                            v48);
                          continue;
                        }
                        if ( v2 )
                        {
                          CharLowerBuffW(v67, 0x24u);
                          v38 = v67;
                          v39 = &v65;
                          goto LABEL_73;
                        }
                        if ( (unsigned int)dword_140027000 > 2
                          && (qword_140027010 & 0x400000000000LL) != 0
                          && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
                        {
                          v58 = 0x1000000;
                          LODWORD(v50) = 422;
                          v57 = "GetScenariosList";
                          v56 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\telman\\telman.cpp";
                          v49 = QuestionDetails;
                          v55 = "Failed to find scenario id and question version giuds";
                          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                            qword_140027018,
                            (unsigned int)byte_140021661,
                            v34,
                            v35,
                            (__int64)&v55,
                            (__int64)&v49,
                            (__int64)&v56,
                            (__int64)&v57,
                            (__int64)&v50,
                            (__int64)&v58);
                        }
                      }
                      else
                      {
                        v24 = 8;
                        v25 = v61;
                        v26 = L"scenario";
                        while ( *v26 == *v25 )
                        {
                          ++v26;
                          ++v25;
                          if ( !--v24 )
                          {
                            v27 = -1;
                            do
                              ++v27;
                            while ( v61[v27] );
                            if ( v27 == 8 )
                            {
                              LODWORD(v52) = 1;
                              LODWORD(v51) = (_DWORD)v51 + 1;
                              if ( !v2 )
                              {
                                ScenarioId = GetScenarioId((struct IXmlReader *)ppvObject, v53, v67);
                                if ( ScenarioId < 0
                                  && (unsigned int)dword_140027000 > 2
                                  && (qword_140027010 & 0x400000000000LL) != 0
                                  && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
                                {
                                  v58 = 0x1000000;
                                  LODWORD(v50) = 380;
                                  v57 = "GetScenariosList";
                                  v56 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\telman\\telman.cpp";
                                  v49 = ScenarioId;
                                  v55 = "GetScenarioId failed";
                                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                                    qword_140027010,
                                    (unsigned int)byte_1400217D9,
                                    ScenarioId,
                                    v29,
                                    (__int64)&v55,
                                    (__int64)&v49,
                                    (__int64)&v56,
                                    (__int64)&v57,
                                    (__int64)&v50,
                                    (__int64)&v58);
                                }
                                v2 = v53[0];
                              }
                            }
                            goto LABEL_37;
                          }
                        }
                      }
                    }
                    else if ( (unsigned int)dword_140027000 > 2
                           && (qword_140027010 & 0x400000000000LL) != 0
                           && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
                    {
                      v55 = (const char *)0x1000000;
                      v49 = 350;
                      v56 = "GetScenariosList";
                      v57 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\telman\\telman.cpp";
                      LODWORD(v50) = v22;
                      v58 = (__int64)"GetLocalName failed";
                      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                        qword_140027010,
                        (unsigned int)&unk_1400212E8,
                        v22,
                        v23,
                        (__int64)&v58,
                        (__int64)&v50,
                        (__int64)&v57,
                        (__int64)&v56,
                        (__int64)&v49,
                        (__int64)&v55);
                    }
                  }
                  else if ( v60 == 15 && (_DWORD)v52 )
                  {
                    v40 = (*(__int64 (__fastcall **)(void *, _WORD **, _QWORD))(*(_QWORD *)ppvObject + 112LL))(
                            ppvObject,
                            &v61,
                            0);
                    if ( v40 >= 0 )
                    {
                      v42 = 8;
                      v43 = v61;
                      v44 = L"scenario";
                      while ( *v44 == *v43 )
                      {
                        ++v44;
                        ++v43;
                        if ( !--v42 )
                        {
                          LODWORD(v52) = 0;
                          v2 = 0;
                          v53[0] = 0;
                          LODWORD(v54) = (_DWORD)v54 + 1;
                          goto LABEL_37;
                        }
                      }
                    }
                    else if ( (unsigned int)dword_140027000 > 2
                           && (qword_140027010 & 0x400000000000LL) != 0
                           && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
                    {
                      v58 = 0x1000000;
                      LODWORD(v50) = 434;
                      v57 = "GetScenariosList";
                      v56 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\telman\\telman.cpp";
                      v49 = v40;
                      v55 = "GetLocalName failed";
                      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                        qword_140027010,
                        (unsigned int)&byte_140021C37,
                        v40,
                        v41,
                        (__int64)&v55,
                        (__int64)&v49,
                        (__int64)&v56,
                        (__int64)&v57,
                        (__int64)&v50,
                        (__int64)&v58);
                    }
                  }
                }
                if ( DiagTrackStorePath != 1 )
                {
                  if ( (unsigned int)dword_140027000 > 2
                    && (qword_140027010 & 0x400000000000LL) != 0
                    && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
                  {
                    v58 = 0x1000000;
                    LODWORD(v50) = 453;
                    v57 = "GetScenariosList";
                    v56 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\telman\\telman.cpp";
                    v49 = DiagTrackStorePath;
                    v55 = "Unexpected result from IXmlReader->Read";
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                      qword_140027018,
                      (unsigned int)&word_140021346,
                      v20,
                      v21,
                      (__int64)&v55,
                      (__int64)&v49,
                      (__int64)&v56,
                      (__int64)&v57,
                      (__int64)&v50,
                      (__int64)&v58);
                  }
                  DiagTrackStorePath = 0;
                }
                if ( (_DWORD)v51 != (_DWORD)v54 )
                {
                  DiagTrackStorePath = -2147467259;
                  if ( (unsigned int)dword_140027000 > 2
                    && (qword_140027010 & 0x400000000000LL) != 0
                    && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
                  {
                    v58 = 0x1000000;
                    LODWORD(v50) = 464;
                    v57 = "GetScenariosList";
                    v56 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\telman\\telman.cpp";
                    v49 = -2147467259;
                    v55 = "Scenario start count does not match end count.";
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                      qword_140027018,
                      (unsigned int)byte_140021A0D,
                      v20,
                      v21,
                      (__int64)&v55,
                      (__int64)&v49,
                      (__int64)&v56,
                      (__int64)&v57,
                      (__int64)&v50,
                      (__int64)&v58);
                  }
                }
              }
              else if ( (unsigned int)dword_140027000 > 2
                     && (qword_140027010 & 0x400000000000LL) != 0
                     && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
              {
                v50 = 0x1000000;
                v49 = 338;
                v54 = "GetScenariosList";
                *(_QWORD *)v53 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\telman\\telman.cpp";
                LODWORD(v51) = DiagTrackStorePath;
                v52 = "reader->SetInput failed.";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                  qword_140027018,
                  (unsigned int)byte_140021BD9,
                  v18,
                  v19,
                  (__int64)&v52,
                  (__int64)&v51,
                  (__int64)v53,
                  (__int64)&v54,
                  (__int64)&v49,
                  (__int64)&v50);
              }
            }
            else if ( (unsigned int)dword_140027000 > 2
                   && (qword_140027010 & 0x400000000000LL) != 0
                   && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
            {
              v50 = 0x1000000;
              v49 = 330;
              v54 = "GetScenariosList";
              *(_QWORD *)v53 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\telman\\telman.cpp";
              LODWORD(v51) = DiagTrackStorePath;
              v52 = "reader->SetProperty failed.";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                qword_140027018,
                (unsigned int)byte_140021895,
                v16,
                v17,
                (__int64)&v52,
                (__int64)&v51,
                (__int64)v53,
                (__int64)&v54,
                (__int64)&v49,
                (__int64)&v50);
            }
          }
          else if ( (unsigned int)dword_140027000 > 2
                 && (qword_140027010 & 0x400000000000LL) != 0
                 && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
          {
            v50 = 0x1000000;
            v49 = 321;
            v54 = "GetScenariosList";
            *(_QWORD *)v53 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\telman\\telman.cpp";
            LODWORD(v51) = DiagTrackStorePath;
            v52 = "CreateXmlReader failed.";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
              qword_140027018,
              (unsigned int)byte_140021A6B,
              v14,
              v15,
              (__int64)&v52,
              (__int64)&v51,
              (__int64)v53,
              (__int64)&v54,
              (__int64)&v49,
              (__int64)&v50);
          }
        }
        else if ( (unsigned int)dword_140027000 > 2
               && (qword_140027010 & 0x400000000000LL) != 0
               && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
        {
          v50 = 0x1000000;
          v49 = 311;
          v54 = "GetScenariosList";
          *(_QWORD *)v53 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\telman\\telman.cpp";
          LODWORD(v51) = DiagTrackStorePath;
          v52 = "Failed to create a stream on the manifest.";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
            qword_140027018,
            (unsigned int)byte_1400218F3,
            v12,
            v13,
            (__int64)&v52,
            (__int64)&v51,
            (__int64)v53,
            (__int64)&v54,
            (__int64)&v49,
            (__int64)&v50);
        }
      }
      else if ( (unsigned int)dword_140027000 > 5 )
      {
        v50 = (__int64)pszFile;
        v49 = DiagTrackStorePath;
        v51 = "Attempted to open manifest";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
          v11,
          (unsigned int)qword_1400215D8,
          v12,
          v13,
          (__int64)&v51,
          (__int64)&v49,
          (__int64)&v50);
      }
    }
    else if ( (unsigned int)dword_140027000 > 2
           && (qword_140027010 & 0x400000000000LL) != 0
           && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
    {
      v50 = 0x1000000;
      v49 = 287;
      v54 = "GetScenariosList";
      *(_QWORD *)v53 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\telman\\telman.cpp";
      LODWORD(v51) = DiagTrackStorePath;
      v52 = "StringCchPrintfW failed to build loc folder string.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        qword_140027018,
        (unsigned int)byte_140021603,
        v9,
        v10,
        (__int64)&v52,
        (__int64)&v51,
        (__int64)v53,
        (__int64)&v54,
        (__int64)&v49,
        (__int64)&v50);
    }
  }
  else if ( (unsigned int)dword_140027000 > 2 )
  {
    v5 = qword_140027018;
    if ( (qword_140027010 & 0x400000000000LL) != 0 && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
    {
      v50 = 0x1000000;
      v49 = 271;
      v54 = "GetScenariosList";
      *(_QWORD *)v53 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\telman\\telman.cpp";
      LODWORD(v51) = DiagTrackStorePath;
      v52 = "GetDiagTrackStorePath failed.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        qword_140027010,
        (unsigned int)word_14002157A,
        v7,
        v8,
        (__int64)&v52,
        (__int64)&v51,
        (__int64)v53,
        (__int64)&v54,
        (__int64)&v49,
        (__int64)&v50);
    }
  }
  v45 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v45);
  }
  if ( ppvObject )
    (*(void (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 16LL))(ppvObject, v5);
  if ( ppstm )
    (*(void (__fastcall **)(IStream *, __int64))(*(_QWORD *)ppstm + 16LL))(ppstm, v5);
  return (unsigned int)DiagTrackStorePath;
}

```

## disassembly

```asm
0x14000e924  push    rbp
0x14000e926  push    rbx
0x14000e927  push    rsi
0x14000e928  push    rdi
0x14000e929  push    r12
0x14000e92b  push    r13
0x14000e92d  push    r14
0x14000e92f  push    r15
0x14000e931  lea     rbp, [rsp-2B8h]
0x14000e939  sub     rsp, 3B8h
0x14000e940  mov     rax, cs:__security_cookie
0x14000e947  xor     rax, rsp
0x14000e94a  mov     [rbp+2F0h+var_50], rax
0x14000e951  mov     r12, rcx
0x14000e954  xor     esi, esi
0x14000e956  mov     [rbp+2F0h+ppvObject], rsi
0x14000e95a  mov     [rbp+2F0h+var_348], esi
0x14000e95d  mov     [rbp+2F0h+ppstm], rsi
0x14000e961  mov     [rbp+2F0h+var_340], rsi
0x14000e965  mov     r13d, esi
0x14000e968  mov     [rsp+3F0h+var_380], esi
0x14000e96c  lea     ebx, [rsi+4Ah]
0x14000e96f  mov     r8d, ebx; Size
0x14000e972  xor     edx, edx; Val
0x14000e974  lea     rcx, [rbp+2F0h+var_2B0]; void *
0x14000e978  call    memset_0
0x14000e97d  mov     r8d, ebx; Size
0x14000e980  xor     edx, edx; Val
0x14000e982  lea     rcx, [rbp+2F0h+sz]; void *
0x14000e986  call    memset_0
0x14000e98b  mov     r14d, 208h
0x14000e991  mov     r8d, r14d; Size
0x14000e994  xor     edx, edx; Val
0x14000e996  lea     rcx, [rbp+2F0h+pszFile]; void *
0x14000e99d  call    memset_0
0x14000e9a2  mov     [rbp+2F0h+lpMem], rsi
0x14000e9a6  mov     rax, [r12]
0x14000e9aa  mov     rdi, [rax+8]
0x14000e9ae  mov     rbx, rdi
0x14000e9b1  cmp     [rdi+19h], sil
0x14000e9b5  jnz     short loc_14000E9D8
0x14000e9b7  mov     rdx, [rbx+10h]
0x14000e9bb  mov     rcx, r12
0x14000e9be  call    ?_Erase@?$_Tree@V?$_Tset_traits@U_GUID_BUFFER@@UlessGuidBuffer@@V?$allocator@U_GUID_BUFFER@@@std@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U_GUID_BUFFER@@PEAX@2@@Z; std::_Tree<std::_Tset_traits<_GUID_BUFFER,lessGuidBuffer,std::allocator<_GUID_BUFFER>,0>>::_Erase(std::_Tree_node<_GUID_BUFFER,void *> *)
0x14000e9c3  mov     rbx, [rbx]
0x14000e9c6  mov     rcx, rdi
0x14000e9c9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000e9cf  mov     rdi, rbx
0x14000e9d2  cmp     [rbx+19h], sil
0x14000e9d6  jz      short loc_14000E9B7
0x14000e9d8  mov     rax, [r12]
0x14000e9dc  mov     [rax+8], rax
0x14000e9e0  mov     rax, [r12]
0x14000e9e4  mov     [rax], rax
0x14000e9e7  mov     rax, [r12]
0x14000e9eb  mov     [rax+10h], rax
0x14000e9ef  mov     [r12+8], rsi
0x14000e9f4  lea     rcx, [rbp+2F0h+lpMem]; unsigned __int16 **
0x14000e9f8  call    ?GetDiagTrackStorePath@@YAJPEAPEAG@Z; GetDiagTrackStorePath(ushort * *)
0x14000e9fd  mov     edi, eax
0x14000e9ff  test    eax, eax
0x14000ea01  jns     loc_14000EAC3
0x14000ea07  mov     ecx, cs:dword_140027000
0x14000ea0d  cmp     ecx, 2
0x14000ea10  jbe     loc_14000F5E7
0x14000ea16  mov     rdx, cs:qword_140027018
0x14000ea1d  mov     rcx, cs:qword_140027010
0x14000ea24  mov     rbx, 400000000000h
0x14000ea2e  test    rbx, rcx
0x14000ea31  jz      loc_14000F5E7
0x14000ea37  mov     rax, rdx
0x14000ea3a  and     rax, rbx
0x14000ea3d  cmp     rax, rdx
0x14000ea40  jnz     loc_14000F5E7
0x14000ea46  mov     esi, 1000000h
0x14000ea4b  mov     [rsp+3F0h+var_398], rsi
0x14000ea50  mov     [rsp+3F0h+var_3A0], 10Fh
0x14000ea58  lea     r14, aGetscenariosli; "GetScenariosList"
0x14000ea5f  mov     [rsp+3F0h+var_378], r14
0x14000ea64  lea     r15, aOnecoreBaseDia_5; "onecore\\base\\diagnosis\\feedback\\siu"...
0x14000ea6b  mov     qword ptr [rsp+3F0h+var_380], r15
0x14000ea70  mov     dword ptr [rsp+3F0h+var_390], edi
0x14000ea74  lea     rax, aGetdiagtrackst; "GetDiagTrackStorePath failed."
0x14000ea7b  mov     [rsp+3F0h+var_388], rax
0x14000ea80  lea     rax, [rsp+3F0h+var_398]
0x14000ea85  mov     [rsp+3F0h+var_3A8], rax
0x14000ea8a  lea     rax, [rsp+3F0h+var_3A0]
0x14000ea8f  mov     [rsp+3F0h+var_3B0], rax
0x14000ea94  lea     rax, [rsp+3F0h+var_378]
0x14000ea99  mov     [rsp+3F0h+var_3B8], rax
0x14000ea9e  lea     rax, [rsp+3F0h+var_380]
0x14000eaa3  mov     [rsp+3F0h+var_3C0], rax
0x14000eaa8  lea     rax, [rsp+3F0h+var_390]
0x14000eaad  mov     [rsp+3F0h+var_3C8], rax
0x14000eab2  lea     rax, [rsp+3F0h+var_388]
0x14000eab7  lea     rdx, word_14002157A
0x14000eabe  jmp     loc_14000F5DD
0x14000eac3  mov     r8, r14; Size
0x14000eac6  xor     edx, edx; Val
0x14000eac8  lea     rcx, [rbp+2F0h+pszFile]; void *
0x14000eacf  call    memset_0
0x14000ead4  lea     rax, aDownloadedscen; "downloadedscenarios\\windows.siuf.xml"
0x14000eadb  mov     [rsp+3F0h+var_3D0], rax
0x14000eae0  mov     r9, [rbp+2F0h+lpMem]
0x14000eae4  lea     r8, aSS_0; "%s\\%s"
0x14000eaeb  mov     edx, 104h; unsigned __int64
0x14000eaf0  lea     rcx, [rbp+2F0h+pszFile]; unsigned __int16 *
0x14000eaf7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000eafc  mov     edi, eax
0x14000eafe  test    eax, eax
0x14000eb00  jns     loc_14000EBC2
0x14000eb06  mov     eax, cs:dword_140027000
0x14000eb0c  cmp     eax, 2
0x14000eb0f  jbe     loc_14000F5E7
0x14000eb15  mov     rcx, cs:qword_140027018
0x14000eb1c  mov     rax, cs:qword_140027010
0x14000eb23  mov     rbx, 400000000000h
0x14000eb2d  test    rbx, rax
0x14000eb30  jz      loc_14000F5E7
0x14000eb36  mov     rax, rcx
0x14000eb39  and     rax, rbx
0x14000eb3c  cmp     rax, rcx
0x14000eb3f  jnz     loc_14000F5E7
0x14000eb45  mov     esi, 1000000h
0x14000eb4a  mov     [rsp+3F0h+var_398], rsi
0x14000eb4f  mov     [rsp+3F0h+var_3A0], 11Fh
0x14000eb57  lea     r14, aGetscenariosli; "GetScenariosList"
0x14000eb5e  mov     [rsp+3F0h+var_378], r14
0x14000eb63  lea     r15, aOnecoreBaseDia_5; "onecore\\base\\diagnosis\\feedback\\siu"...
0x14000eb6a  mov     qword ptr [rsp+3F0h+var_380], r15
0x14000eb6f  mov     dword ptr [rsp+3F0h+var_390], edi
0x14000eb73  lea     rax, aStringcchprint_1; "StringCchPrintfW failed to build loc fo"...
0x14000eb7a  mov     [rsp+3F0h+var_388], rax
0x14000eb7f  lea     rax, [rsp+3F0h+var_398]
0x14000eb84  mov     [rsp+3F0h+var_3A8], rax
0x14000eb89  lea     rax, [rsp+3F0h+var_3A0]
0x14000eb8e  mov     [rsp+3F0h+var_3B0], rax
0x14000eb93  lea     rax, [rsp+3F0h+var_378]
0x14000eb98  mov     [rsp+3F0h+var_3B8], rax
0x14000eb9d  lea     rax, [rsp+3F0h+var_380]
0x14000eba2  mov     [rsp+3F0h+var_3C0], rax
0x14000eba7  lea     rax, [rsp+3F0h+var_390]
0x14000ebac  mov     [rsp+3F0h+var_3C8], rax
0x14000ebb1  lea     rax, [rsp+3F0h+var_388]
0x14000ebb6  lea     rdx, byte_140021603
0x14000ebbd  jmp     loc_14000F5DD
0x14000ebc2  lea     r8, [rbp+2F0h+ppstm]; ppstm
0x14000ebc6  xor     edx, edx; grfMode
0x14000ebc8  lea     rcx, [rbp+2F0h+pszFile]; pszFile
0x14000ebcf  call    cs:__imp_SHCreateStreamOnFileW
0x14000ebd5  mov     edi, eax
0x14000ebd7  test    eax, eax
0x14000ebd9  jns     short loc_14000EC35
0x14000ebdb  mov     eax, cs:dword_140027000
0x14000ebe1  cmp     eax, 5
0x14000ebe4  jbe     loc_14000F5E7
0x14000ebea  lea     rax, [rbp+2F0h+pszFile]
0x14000ebf1  mov     [rsp+3F0h+var_398], rax
0x14000ebf6  mov     [rsp+3F0h+var_3A0], edi
0x14000ebfa  lea     rax, aAttemptedToOpe; "Attempted to open manifest"
0x14000ec01  mov     [rsp+3F0h+var_390], rax
0x14000ec06  lea     rax, [rsp+3F0h+var_398]
0x14000ec0b  mov     [rsp+3F0h+var_3C0], rax
0x14000ec10  lea     rax, [rsp+3F0h+var_3A0]
0x14000ec15  mov     [rsp+3F0h+var_3C8], rax
0x14000ec1a  lea     rax, [rsp+3F0h+var_390]
0x14000ec1f  mov     [rsp+3F0h+var_3D0], rax
0x14000ec24  lea     rdx, qword_1400215D8
0x14000ec2b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x14000ec30  jmp     loc_14000F5E7
0x14000ec35  cmp     [rbp+2F0h+ppstm], rsi
0x14000ec39  jnz     loc_14000ECFB
0x14000ec3f  mov     eax, cs:dword_140027000
0x14000ec45  cmp     eax, 2
0x14000ec48  jbe     loc_14000F5E7
0x14000ec4e  mov     rcx, cs:qword_140027018
0x14000ec55  mov     rax, cs:qword_140027010
0x14000ec5c  mov     rbx, 400000000000h
0x14000ec66  test    rbx, rax
0x14000ec69  jz      loc_14000F5E7
0x14000ec6f  mov     rax, rcx
0x14000ec72  and     rax, rbx
0x14000ec75  cmp     rax, rcx
0x14000ec78  jnz     loc_14000F5E7
0x14000ec7e  mov     esi, 1000000h
0x14000ec83  mov     [rsp+3F0h+var_398], rsi
0x14000ec88  mov     [rsp+3F0h+var_3A0], 137h
0x14000ec90  lea     r14, aGetscenariosli; "GetScenariosList"
0x14000ec97  mov     [rsp+3F0h+var_378], r14
0x14000ec9c  lea     r15, aOnecoreBaseDia_5; "onecore\\base\\diagnosis\\feedback\\siu"...
0x14000eca3  mov     qword ptr [rsp+3F0h+var_380], r15
0x14000eca8  mov     dword ptr [rsp+3F0h+var_390], edi
0x14000ecac  lea     rax, aFailedToCreate_0; "Failed to create a stream on the manife"...
0x14000ecb3  mov     [rsp+3F0h+var_388], rax
0x14000ecb8  lea     rax, [rsp+3F0h+var_398]
0x14000ecbd  mov     [rsp+3F0h+var_3A8], rax
0x14000ecc2  lea     rax, [rsp+3F0h+var_3A0]
0x14000ecc7  mov     [rsp+3F0h+var_3B0], rax
0x14000eccc  lea     rax, [rsp+3F0h+var_378]
0x14000ecd1  mov     [rsp+3F0h+var_3B8], rax
0x14000ecd6  lea     rax, [rsp+3F0h+var_380]
0x14000ecdb  mov     [rsp+3F0h+var_3C0], rax
0x14000ece0  lea     rax, [rsp+3F0h+var_390]
0x14000ece5  mov     [rsp+3F0h+var_3C8], rax
0x14000ecea  lea     rax, [rsp+3F0h+var_388]
0x14000ecef  lea     rdx, byte_1400218F3
0x14000ecf6  jmp     loc_14000F5DD
0x14000ecfb  xor     r8d, r8d; pMalloc
0x14000ecfe  lea     rdx, [rbp+2F0h+ppvObject]; ppvObject
0x14000ed02  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x14000ed09  call    cs:__imp_CreateXmlReader
0x14000ed0f  mov     edi, eax
0x14000ed11  test    eax, eax
0x14000ed13  jns     loc_14000EDD5
0x14000ed19  mov     eax, cs:dword_140027000
0x14000ed1f  cmp     eax, 2
0x14000ed22  jbe     loc_14000F5E7
0x14000ed28  mov     rcx, cs:qword_140027018
0x14000ed2f  mov     rax, cs:qword_140027010
0x14000ed36  mov     rbx, 400000000000h
0x14000ed40  test    rbx, rax
0x14000ed43  jz      loc_14000F5E7
0x14000ed49  mov     rax, rcx
0x14000ed4c  and     rax, rbx
0x14000ed4f  cmp     rax, rcx
0x14000ed52  jnz     loc_14000F5E7
0x14000ed58  mov     esi, 1000000h
0x14000ed5d  mov     [rsp+3F0h+var_398], rsi
0x14000ed62  mov     [rsp+3F0h+var_3A0], 141h
0x14000ed6a  lea     r14, aGetscenariosli; "GetScenariosList"
0x14000ed71  mov     [rsp+3F0h+var_378], r14
0x14000ed76  lea     r15, aOnecoreBaseDia_5; "onecore\\base\\diagnosis\\feedback\\siu"...
0x14000ed7d  mov     qword ptr [rsp+3F0h+var_380], r15
0x14000ed82  mov     dword ptr [rsp+3F0h+var_390], edi
0x14000ed86  lea     rax, aCreatexmlreade; "CreateXmlReader failed."
0x14000ed8d  mov     [rsp+3F0h+var_388], rax
0x14000ed92  lea     rax, [rsp+3F0h+var_398]
0x14000ed97  mov     [rsp+3F0h+var_3A8], rax
0x14000ed9c  lea     rax, [rsp+3F0h+var_3A0]
0x14000eda1  mov     [rsp+3F0h+var_3B0], rax
0x14000eda6  lea     rax, [rsp+3F0h+var_378]
0x14000edab  mov     [rsp+3F0h+var_3B8], rax
0x14000edb0  lea     rax, [rsp+3F0h+var_380]
0x14000edb5  mov     [rsp+3F0h+var_3C0], rax
0x14000edba  lea     rax, [rsp+3F0h+var_390]
0x14000edbf  mov     [rsp+3F0h+var_3C8], rax
0x14000edc4  lea     rax, [rsp+3F0h+var_388]
0x14000edc9  lea     rdx, byte_140021A6B
0x14000edd0  jmp     loc_14000F5DD
0x14000edd5  mov     rcx, [rbp+2F0h+ppvObject]
0x14000edd9  mov     rax, [rcx]
0x14000eddc  xor     r8d, r8d
0x14000eddf  lea     edx, [r8+4]
0x14000ede3  mov     rax, [rax+28h]
0x14000ede7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000edec  mov     edi, eax
0x14000edee  test    eax, eax
0x14000edf0  jns     loc_14000EEB2
0x14000edf6  mov     eax, cs:dword_140027000
0x14000edfc  cmp     eax, 2
0x14000edff  jbe     loc_14000F5E7
0x14000ee05  mov     rcx, cs:qword_140027018
0x14000ee0c  mov     rax, cs:qword_140027010
0x14000ee13  mov     rbx, 400000000000h
0x14000ee1d  test    rbx, rax
0x14000ee20  jz      loc_14000F5E7
0x14000ee26  mov     rax, rcx
0x14000ee29  and     rax, rbx
0x14000ee2c  cmp     rax, rcx
0x14000ee2f  jnz     loc_14000F5E7
0x14000ee35  mov     esi, 1000000h
0x14000ee3a  mov     [rsp+3F0h+var_398], rsi
0x14000ee3f  mov     [rsp+3F0h+var_3A0], 14Ah
0x14000ee47  lea     r14, aGetscenariosli; "GetScenariosList"
0x14000ee4e  mov     [rsp+3F0h+var_378], r14
0x14000ee53  lea     r15, aOnecoreBaseDia_5; "onecore\\base\\diagnosis\\feedback\\siu"...
0x14000ee5a  mov     qword ptr [rsp+3F0h+var_380], r15
0x14000ee5f  mov     dword ptr [rsp+3F0h+var_390], edi
0x14000ee63  lea     rax, aReaderSetprope; "reader->SetProperty failed."
0x14000ee6a  mov     [rsp+3F0h+var_388], rax
0x14000ee6f  lea     rax, [rsp+3F0h+var_398]
0x14000ee74  mov     [rsp+3F0h+var_3A8], rax
0x14000ee79  lea     rax, [rsp+3F0h+var_3A0]
0x14000ee7e  mov     [rsp+3F0h+var_3B0], rax
0x14000ee83  lea     rax, [rsp+3F0h+var_378]
0x14000ee88  mov     [rsp+3F0h+var_3B8], rax
0x14000ee8d  lea     rax, [rsp+3F0h+var_380]
0x14000ee92  mov     [rsp+3F0h+var_3C0], rax
0x14000ee97  lea     rax, [rsp+3F0h+var_390]
0x14000ee9c  mov     [rsp+3F0h+var_3C8], rax
0x14000eea1  lea     rax, [rsp+3F0h+var_388]
0x14000eea6  lea     rdx, byte_140021895
0x14000eead  jmp     loc_14000F5DD
0x14000eeb2  mov     rcx, [rbp+2F0h+ppvObject]
0x14000eeb6  mov     rax, [rcx]
0x14000eeb9  mov     rdx, [rbp+2F0h+ppstm]
0x14000eebd  mov     rax, [rax+18h]
0x14000eec1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000eec6  mov     edi, eax
0x14000eec8  test    eax, eax
  ... truncated ...
```
