# GetScenariosList(std::set<_GUID_BUFFER,lessGuidBuffer,std::allocator<_GUID_BUFFER>> &)

- ea: `0x14000ee98`
- end: `0x14000fbf2`
- name: `?GetScenariosList@@YAJAEAV?$set@U_GUID_BUFFER@@UlessGuidBuffer@@V?$allocator@U_GUID_BUFFER@@@std@@@std@@@Z`
- size: `3418`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x14000c928`

## callees

- `0x140001418`
- `0x1400019a8`
- `0x14000b904`
- `0x14000bf68`
- `0x14000dd04`
- `0x14000e290`
- `0x14000ecc0`
- `0x14000ee98`
- `0x14001505c`
- `0x1400195e2`
- `0x140019610`
- `0x14001a010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14000ef3d`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000ef3d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000fb82`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000fb82`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000fb96`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000fb96`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x14000f83a`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x14000f85e`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x14000f83a`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x14000f85e`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x14000f149`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x14000f149`
- `XmlLite!CreateXmlReader` at `0x14000f289`
- `XmlLite!CreateXmlReader` at `0x14000f289`

## string_xrefs

- `0x14000efee`: `GetDiagTrackStorePath failed.`
- `0x14000f04e`: `downloadedscenarios\windows.siuf.xml`
- `0x14000f17a`: `Attempted to open manifest`
- `0x14000f22c`: `Failed to create a stream on the manifest.`
- `0x14000f30c`: `CreateXmlReader failed.`
- `0x14000f3e9`: `reader->SetProperty failed.`
- `0x14000f4c3`: `reader->SetInput failed.`
- `0x14000f7d2`: `GetQuestionIdFromSifActionNode failed`
- `0x14000fa7d`: `Unexpected result from IXmlReader->Read`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
                          if ( (unsigned int)dword_140028000 > 2
                            && (qword_140028010 & 0x400000000000LL) != 0
                            && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
                          {
                            v58 = 0x1000000;
                            LODWORD(v50) = 405;
                            v57 = "GetScenariosList";
                            v56 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\telman\\telman.cpp";
                            v49 = QuestionDetails;
                            v55 = "GetQuestionIdFromSifActionNode failed";
                            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                              qword_140028010,
                              (unsigned int)&unk_140022468,
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
                          LOBYTE(v48) = byte_140028C20;
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
                        if ( (unsigned int)dword_140028000 > 2
                          && (qword_140028010 & 0x400000000000LL) != 0
                          && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
                        {
                          v58 = 0x1000000;
                          LODWORD(v50) = 422;
                          v57 = "GetScenariosList";
                          v56 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\telman\\telman.cpp";
                          v49 = QuestionDetails;
                          v55 = "Failed to find scenario id and question version giuds";
                          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                            qword_140028018,
                            (unsigned int)byte_140022669,
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
                                  && (unsigned int)dword_140028000 > 2
                                  && (qword_140028010 & 0x400000000000LL) != 0
                                  && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
                                {
                                  v58 = 0x1000000;
                                  LODWORD(v50) = 380;
                                  v57 = "GetScenariosList";
                                  v56 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\telman\\telman.cpp";
                                  v49 = ScenarioId;
                                  v55 = "GetScenarioId failed";
                                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                                    qword_140028010,
                                    (unsigned int)byte_1400227E1,
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
                    else if ( (unsigned int)dword_140028000 > 2
                           && (qword_140028010 & 0x400000000000LL) != 0
                           && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
                    {
                      v55 = (const char *)0x1000000;
                      v49 = 350;
                      v56 = "GetScenariosList";
                      v57 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\telman\\telman.cpp";
                      LODWORD(v50) = v22;
                      v58 = (__int64)"GetLocalName failed";
                      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                        qword_140028010,
                        (unsigned int)&unk_1400222F0,
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
                    else if ( (unsigned int)dword_140028000 > 2
                           && (qword_140028010 & 0x400000000000LL) != 0
                           && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
                    {
                      v58 = 0x1000000;
                      LODWORD(v50) = 434;
                      v57 = "GetScenariosList";
                      v56 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\telman\\telman.cpp";
                      v49 = v40;
                      v55 = "GetLocalName failed";
                      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                        qword_140028010,
                        (unsigned int)&byte_140022C3F,
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
                  if ( (unsigned int)dword_140028000 > 2
                    && (qword_140028010 & 0x400000000000LL) != 0
                    && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
                  {
                    v58 = 0x1000000;
                    LODWORD(v50) = 453;
                    v57 = "GetScenariosList";
                    v56 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\telman\\telman.cpp";
                    v49 = DiagTrackStorePath;
                    v55 = "Unexpected result from IXmlReader->Read";
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                      qword_140028018,
                      (unsigned int)&word_14002234E,
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
                  if ( (unsigned int)dword_140028000 > 2
                    && (qword_140028010 & 0x400000000000LL) != 0
                    && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
                  {
                    v58 = 0x1000000;
                    LODWORD(v50) = 464;
                    v57 = "GetScenariosList";
                    v56 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\telman\\telman.cpp";
                    v49 = -2147467259;
                    v55 = "Scenario start count does not match end count.";
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                      qword_140028018,
                      (unsigned int)byte_140022A15,
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
              else if ( (unsigned int)dword_140028000 > 2
                     && (qword_140028010 & 0x400000000000LL) != 0
                     && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
              {
                v50 = 0x1000000;
                v49 = 338;
                v54 = "GetScenariosList";
                *(_QWORD *)v53 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\telman\\telman.cpp";
                LODWORD(v51) = DiagTrackStorePath;
                v52 = "reader->SetInput failed.";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                  qword_140028018,
                  (unsigned int)byte_140022BE1,
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
            else if ( (unsigned int)dword_140028000 > 2
                   && (qword_140028010 & 0x400000000000LL) != 0
                   && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
            {
              v50 = 0x1000000;
              v49 = 330;
              v54 = "GetScenariosList";
              *(_QWORD *)v53 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\telman\\telman.cpp";
              LODWORD(v51) = DiagTrackStorePath;
              v52 = "reader->SetProperty failed.";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                qword_140028018,
                (unsigned int)byte_14002289D,
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
          else if ( (unsigned int)dword_140028000 > 2
                 && (qword_140028010 & 0x400000000000LL) != 0
                 && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
          {
            v50 = 0x1000000;
            v49 = 321;
            v54 = "GetScenariosList";
            *(_QWORD *)v53 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\telman\\telman.cpp";
            LODWORD(v51) = DiagTrackStorePath;
            v52 = "CreateXmlReader failed.";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
              qword_140028018,
              (unsigned int)byte_140022A73,
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
        else if ( (unsigned int)dword_140028000 > 2
               && (qword_140028010 & 0x400000000000LL) != 0
               && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
        {
          v50 = 0x1000000;
          v49 = 311;
          v54 = "GetScenariosList";
          *(_QWORD *)v53 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\telman\\telman.cpp";
          LODWORD(v51) = DiagTrackStorePath;
          v52 = "Failed to create a stream on the manifest.";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
            qword_140028018,
            (unsigned int)byte_1400228FB,
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
      else if ( (unsigned int)dword_140028000 > 5 )
      {
        v50 = (__int64)pszFile;
        v49 = DiagTrackStorePath;
        v51 = "Attempted to open manifest";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
          v11,
          (unsigned int)qword_1400225E0,
          v12,
          v13,
          (__int64)&v51,
          (__int64)&v49,
          (__int64)&v50);
      }
    }
    else if ( (unsigned int)dword_140028000 > 2
           && (qword_140028010 & 0x400000000000LL) != 0
           && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
    {
      v50 = 0x1000000;
      v49 = 287;
      v54 = "GetScenariosList";
      *(_QWORD *)v53 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\telman\\telman.cpp";
      LODWORD(v51) = DiagTrackStorePath;
      v52 = "StringCchPrintfW failed to build loc folder string.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        qword_140028018,
        (unsigned int)byte_14002260B,
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
  else if ( (unsigned int)dword_140028000 > 2 )
  {
    v5 = qword_140028018;
    if ( (qword_140028010 & 0x400000000000LL) != 0 && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
    {
      v50 = 0x1000000;
      v49 = 271;
      v54 = "GetScenariosList";
      *(_QWORD *)v53 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\telman\\telman.cpp";
      LODWORD(v51) = DiagTrackStorePath;
      v52 = "GetDiagTrackStorePath failed.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        qword_140028010,
        (unsigned int)word_140022582,
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
0x14000ee98  push    rbp
0x14000ee9a  push    rbx
0x14000ee9b  push    rsi
0x14000ee9c  push    rdi
0x14000ee9d  push    r12
0x14000ee9f  push    r13
0x14000eea1  push    r14
0x14000eea3  push    r15
0x14000eea5  lea     rbp, [rsp-2B8h]
0x14000eead  sub     rsp, 3B8h
0x14000eeb4  mov     rax, cs:__security_cookie
0x14000eebb  xor     rax, rsp
0x14000eebe  mov     [rbp+2F0h+var_50], rax
0x14000eec5  mov     r12, rcx
0x14000eec8  xor     esi, esi
0x14000eeca  mov     [rbp+2F0h+ppvObject], rsi
0x14000eece  mov     [rbp+2F0h+var_348], esi
0x14000eed1  mov     [rbp+2F0h+ppstm], rsi
0x14000eed5  mov     [rbp+2F0h+var_340], rsi
0x14000eed9  mov     r13d, esi
0x14000eedc  mov     [rsp+3F0h+var_380], esi
0x14000eee0  lea     ebx, [rsi+4Ah]
0x14000eee3  mov     r8d, ebx; Size
0x14000eee6  xor     edx, edx; Val
0x14000eee8  lea     rcx, [rbp+2F0h+var_2B0]; void *
0x14000eeec  call    memset_0
0x14000eef1  mov     r8d, ebx; Size
0x14000eef4  xor     edx, edx; Val
0x14000eef6  lea     rcx, [rbp+2F0h+sz]; void *
0x14000eefa  call    memset_0
0x14000eeff  mov     r14d, 208h
0x14000ef05  mov     r8d, r14d; Size
0x14000ef08  xor     edx, edx; Val
0x14000ef0a  lea     rcx, [rbp+2F0h+pszFile]; void *
0x14000ef11  call    memset_0
0x14000ef16  mov     [rbp+2F0h+lpMem], rsi
0x14000ef1a  mov     rax, [r12]
0x14000ef1e  mov     rdi, [rax+8]
0x14000ef22  mov     rbx, rdi
0x14000ef25  cmp     [rdi+19h], sil
0x14000ef29  jnz     short loc_14000EF52
0x14000ef2b  mov     rdx, [rbx+10h]
0x14000ef2f  mov     rcx, r12
0x14000ef32  call    ?_Erase@?$_Tree@V?$_Tset_traits@U_GUID_BUFFER@@UlessGuidBuffer@@V?$allocator@U_GUID_BUFFER@@@std@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U_GUID_BUFFER@@PEAX@2@@Z; std::_Tree<std::_Tset_traits<_GUID_BUFFER,lessGuidBuffer,std::allocator<_GUID_BUFFER>,0>>::_Erase(std::_Tree_node<_GUID_BUFFER,void *> *)
0x14000ef37  mov     rbx, [rbx]
0x14000ef3a  mov     rcx, rdi
0x14000ef3d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000ef44  nop     dword ptr [rax+rax+00h]
0x14000ef49  mov     rdi, rbx
0x14000ef4c  cmp     [rbx+19h], sil
0x14000ef50  jz      short loc_14000EF2B
0x14000ef52  mov     rax, [r12]
0x14000ef56  mov     [rax+8], rax
0x14000ef5a  mov     rax, [r12]
0x14000ef5e  mov     [rax], rax
0x14000ef61  mov     rax, [r12]
0x14000ef65  mov     [rax+10h], rax
0x14000ef69  mov     [r12+8], rsi
0x14000ef6e  lea     rcx, [rbp+2F0h+lpMem]; unsigned __int16 **
0x14000ef72  call    ?GetDiagTrackStorePath@@YAJPEAPEAG@Z; GetDiagTrackStorePath(ushort * *)
0x14000ef77  mov     edi, eax
0x14000ef79  test    eax, eax
0x14000ef7b  jns     loc_14000F03D
0x14000ef81  mov     ecx, cs:dword_140028000
0x14000ef87  cmp     ecx, 2
0x14000ef8a  jbe     loc_14000FB79
0x14000ef90  mov     rdx, cs:qword_140028018
0x14000ef97  mov     rcx, cs:qword_140028010
0x14000ef9e  mov     rbx, 400000000000h
0x14000efa8  test    rbx, rcx
0x14000efab  jz      loc_14000FB79
0x14000efb1  mov     rax, rdx
0x14000efb4  and     rax, rbx
0x14000efb7  cmp     rax, rdx
0x14000efba  jnz     loc_14000FB79
0x14000efc0  mov     esi, 1000000h
0x14000efc5  mov     [rsp+3F0h+var_398], rsi
0x14000efca  mov     [rsp+3F0h+var_3A0], 10Fh
0x14000efd2  lea     r14, aGetscenariosli; "GetScenariosList"
0x14000efd9  mov     [rsp+3F0h+var_378], r14
0x14000efde  lea     r15, aOnecoreBaseDia_5; "onecore\\base\\diagnosis\\feedback\\siu"...
0x14000efe5  mov     qword ptr [rsp+3F0h+var_380], r15
0x14000efea  mov     dword ptr [rsp+3F0h+var_390], edi
0x14000efee  lea     rax, aGetdiagtrackst; "GetDiagTrackStorePath failed."
0x14000eff5  mov     [rsp+3F0h+var_388], rax
0x14000effa  lea     rax, [rsp+3F0h+var_398]
0x14000efff  mov     [rsp+3F0h+var_3A8], rax
0x14000f004  lea     rax, [rsp+3F0h+var_3A0]
0x14000f009  mov     [rsp+3F0h+var_3B0], rax
0x14000f00e  lea     rax, [rsp+3F0h+var_378]
0x14000f013  mov     [rsp+3F0h+var_3B8], rax
0x14000f018  lea     rax, [rsp+3F0h+var_380]
0x14000f01d  mov     [rsp+3F0h+var_3C0], rax
0x14000f022  lea     rax, [rsp+3F0h+var_390]
0x14000f027  mov     [rsp+3F0h+var_3C8], rax
0x14000f02c  lea     rax, [rsp+3F0h+var_388]
0x14000f031  lea     rdx, word_140022582
0x14000f038  jmp     loc_14000FB6F
0x14000f03d  mov     r8, r14; Size
0x14000f040  xor     edx, edx; Val
0x14000f042  lea     rcx, [rbp+2F0h+pszFile]; void *
0x14000f049  call    memset_0
0x14000f04e  lea     rax, aDownloadedscen; "downloadedscenarios\\windows.siuf.xml"
0x14000f055  mov     [rsp+3F0h+var_3D0], rax
0x14000f05a  mov     r9, [rbp+2F0h+lpMem]
0x14000f05e  lea     r8, aSS_0; "%s\\%s"
0x14000f065  mov     edx, 104h; unsigned __int64
0x14000f06a  lea     rcx, [rbp+2F0h+pszFile]; unsigned __int16 *
0x14000f071  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000f076  mov     edi, eax
0x14000f078  test    eax, eax
0x14000f07a  jns     loc_14000F13C
0x14000f080  mov     eax, cs:dword_140028000
0x14000f086  cmp     eax, 2
0x14000f089  jbe     loc_14000FB79
0x14000f08f  mov     rcx, cs:qword_140028018
0x14000f096  mov     rax, cs:qword_140028010
0x14000f09d  mov     rbx, 400000000000h
0x14000f0a7  test    rbx, rax
0x14000f0aa  jz      loc_14000FB79
0x14000f0b0  mov     rax, rcx
0x14000f0b3  and     rax, rbx
0x14000f0b6  cmp     rax, rcx
0x14000f0b9  jnz     loc_14000FB79
0x14000f0bf  mov     esi, 1000000h
0x14000f0c4  mov     [rsp+3F0h+var_398], rsi
0x14000f0c9  mov     [rsp+3F0h+var_3A0], 11Fh
0x14000f0d1  lea     r14, aGetscenariosli; "GetScenariosList"
0x14000f0d8  mov     [rsp+3F0h+var_378], r14
0x14000f0dd  lea     r15, aOnecoreBaseDia_5; "onecore\\base\\diagnosis\\feedback\\siu"...
0x14000f0e4  mov     qword ptr [rsp+3F0h+var_380], r15
0x14000f0e9  mov     dword ptr [rsp+3F0h+var_390], edi
0x14000f0ed  lea     rax, aStringcchprint_1; "StringCchPrintfW failed to build loc fo"...
0x14000f0f4  mov     [rsp+3F0h+var_388], rax
0x14000f0f9  lea     rax, [rsp+3F0h+var_398]
0x14000f0fe  mov     [rsp+3F0h+var_3A8], rax
0x14000f103  lea     rax, [rsp+3F0h+var_3A0]
0x14000f108  mov     [rsp+3F0h+var_3B0], rax
0x14000f10d  lea     rax, [rsp+3F0h+var_378]
0x14000f112  mov     [rsp+3F0h+var_3B8], rax
0x14000f117  lea     rax, [rsp+3F0h+var_380]
0x14000f11c  mov     [rsp+3F0h+var_3C0], rax
0x14000f121  lea     rax, [rsp+3F0h+var_390]
0x14000f126  mov     [rsp+3F0h+var_3C8], rax
0x14000f12b  lea     rax, [rsp+3F0h+var_388]
0x14000f130  lea     rdx, byte_14002260B
0x14000f137  jmp     loc_14000FB6F
0x14000f13c  lea     r8, [rbp+2F0h+ppstm]; ppstm
0x14000f140  xor     edx, edx; grfMode
0x14000f142  lea     rcx, [rbp+2F0h+pszFile]; pszFile
0x14000f149  call    cs:__imp_SHCreateStreamOnFileW
0x14000f150  nop     dword ptr [rax+rax+00h]
0x14000f155  mov     edi, eax
0x14000f157  test    eax, eax
0x14000f159  jns     short loc_14000F1B5
0x14000f15b  mov     eax, cs:dword_140028000
0x14000f161  cmp     eax, 5
0x14000f164  jbe     loc_14000FB79
0x14000f16a  lea     rax, [rbp+2F0h+pszFile]
0x14000f171  mov     [rsp+3F0h+var_398], rax
0x14000f176  mov     [rsp+3F0h+var_3A0], edi
0x14000f17a  lea     rax, aAttemptedToOpe; "Attempted to open manifest"
0x14000f181  mov     [rsp+3F0h+var_390], rax
0x14000f186  lea     rax, [rsp+3F0h+var_398]
0x14000f18b  mov     [rsp+3F0h+var_3C0], rax
0x14000f190  lea     rax, [rsp+3F0h+var_3A0]
0x14000f195  mov     [rsp+3F0h+var_3C8], rax
0x14000f19a  lea     rax, [rsp+3F0h+var_390]
0x14000f19f  mov     [rsp+3F0h+var_3D0], rax
0x14000f1a4  lea     rdx, qword_1400225E0
0x14000f1ab  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x14000f1b0  jmp     loc_14000FB79
0x14000f1b5  cmp     [rbp+2F0h+ppstm], rsi
0x14000f1b9  jnz     loc_14000F27B
0x14000f1bf  mov     eax, cs:dword_140028000
0x14000f1c5  cmp     eax, 2
0x14000f1c8  jbe     loc_14000FB79
0x14000f1ce  mov     rcx, cs:qword_140028018
0x14000f1d5  mov     rax, cs:qword_140028010
0x14000f1dc  mov     rbx, 400000000000h
0x14000f1e6  test    rbx, rax
0x14000f1e9  jz      loc_14000FB79
0x14000f1ef  mov     rax, rcx
0x14000f1f2  and     rax, rbx
0x14000f1f5  cmp     rax, rcx
0x14000f1f8  jnz     loc_14000FB79
0x14000f1fe  mov     esi, 1000000h
0x14000f203  mov     [rsp+3F0h+var_398], rsi
0x14000f208  mov     [rsp+3F0h+var_3A0], 137h
0x14000f210  lea     r14, aGetscenariosli; "GetScenariosList"
0x14000f217  mov     [rsp+3F0h+var_378], r14
0x14000f21c  lea     r15, aOnecoreBaseDia_5; "onecore\\base\\diagnosis\\feedback\\siu"...
0x14000f223  mov     qword ptr [rsp+3F0h+var_380], r15
0x14000f228  mov     dword ptr [rsp+3F0h+var_390], edi
0x14000f22c  lea     rax, aFailedToCreate_0; "Failed to create a stream on the manife"...
0x14000f233  mov     [rsp+3F0h+var_388], rax
0x14000f238  lea     rax, [rsp+3F0h+var_398]
0x14000f23d  mov     [rsp+3F0h+var_3A8], rax
0x14000f242  lea     rax, [rsp+3F0h+var_3A0]
0x14000f247  mov     [rsp+3F0h+var_3B0], rax
0x14000f24c  lea     rax, [rsp+3F0h+var_378]
0x14000f251  mov     [rsp+3F0h+var_3B8], rax
0x14000f256  lea     rax, [rsp+3F0h+var_380]
0x14000f25b  mov     [rsp+3F0h+var_3C0], rax
0x14000f260  lea     rax, [rsp+3F0h+var_390]
0x14000f265  mov     [rsp+3F0h+var_3C8], rax
0x14000f26a  lea     rax, [rsp+3F0h+var_388]
0x14000f26f  lea     rdx, byte_1400228FB
0x14000f276  jmp     loc_14000FB6F
0x14000f27b  xor     r8d, r8d; pMalloc
0x14000f27e  lea     rdx, [rbp+2F0h+ppvObject]; ppvObject
0x14000f282  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x14000f289  call    cs:__imp_CreateXmlReader
0x14000f290  nop     dword ptr [rax+rax+00h]
0x14000f295  mov     edi, eax
0x14000f297  test    eax, eax
0x14000f299  jns     loc_14000F35B
0x14000f29f  mov     eax, cs:dword_140028000
0x14000f2a5  cmp     eax, 2
0x14000f2a8  jbe     loc_14000FB79
0x14000f2ae  mov     rcx, cs:qword_140028018
0x14000f2b5  mov     rax, cs:qword_140028010
0x14000f2bc  mov     rbx, 400000000000h
0x14000f2c6  test    rbx, rax
0x14000f2c9  jz      loc_14000FB79
0x14000f2cf  mov     rax, rcx
0x14000f2d2  and     rax, rbx
0x14000f2d5  cmp     rax, rcx
0x14000f2d8  jnz     loc_14000FB79
0x14000f2de  mov     esi, 1000000h
0x14000f2e3  mov     [rsp+3F0h+var_398], rsi
0x14000f2e8  mov     [rsp+3F0h+var_3A0], 141h
0x14000f2f0  lea     r14, aGetscenariosli; "GetScenariosList"
0x14000f2f7  mov     [rsp+3F0h+var_378], r14
0x14000f2fc  lea     r15, aOnecoreBaseDia_5; "onecore\\base\\diagnosis\\feedback\\siu"...
0x14000f303  mov     qword ptr [rsp+3F0h+var_380], r15
0x14000f308  mov     dword ptr [rsp+3F0h+var_390], edi
0x14000f30c  lea     rax, aCreatexmlreade; "CreateXmlReader failed."
0x14000f313  mov     [rsp+3F0h+var_388], rax
0x14000f318  lea     rax, [rsp+3F0h+var_398]
0x14000f31d  mov     [rsp+3F0h+var_3A8], rax
0x14000f322  lea     rax, [rsp+3F0h+var_3A0]
0x14000f327  mov     [rsp+3F0h+var_3B0], rax
0x14000f32c  lea     rax, [rsp+3F0h+var_378]
0x14000f331  mov     [rsp+3F0h+var_3B8], rax
0x14000f336  lea     rax, [rsp+3F0h+var_380]
0x14000f33b  mov     [rsp+3F0h+var_3C0], rax
0x14000f340  lea     rax, [rsp+3F0h+var_390]
0x14000f345  mov     [rsp+3F0h+var_3C8], rax
0x14000f34a  lea     rax, [rsp+3F0h+var_388]
0x14000f34f  lea     rdx, byte_140022A73
0x14000f356  jmp     loc_14000FB6F
0x14000f35b  mov     rcx, [rbp+2F0h+ppvObject]
0x14000f35f  mov     rax, [rcx]
0x14000f362  xor     r8d, r8d
0x14000f365  lea     edx, [r8+4]
0x14000f369  mov     rax, [rax+28h]
0x14000f36d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f372  mov     edi, eax
0x14000f374  test    eax, eax
0x14000f376  jns     loc_14000F438
0x14000f37c  mov     eax, cs:dword_140028000
0x14000f382  cmp     eax, 2
0x14000f385  jbe     loc_14000FB79
0x14000f38b  mov     rcx, cs:qword_140028018
0x14000f392  mov     rax, cs:qword_140028010
0x14000f399  mov     rbx, 400000000000h
0x14000f3a3  test    rbx, rax
0x14000f3a6  jz      loc_14000FB79
0x14000f3ac  mov     rax, rcx
0x14000f3af  and     rax, rbx
0x14000f3b2  cmp     rax, rcx
0x14000f3b5  jnz     loc_14000FB79
0x14000f3bb  mov     esi, 1000000h
0x14000f3c0  mov     [rsp+3F0h+var_398], rsi
0x14000f3c5  mov     [rsp+3F0h+var_3A0], 14Ah
0x14000f3cd  lea     r14, aGetscenariosli; "GetScenariosList"
0x14000f3d4  mov     [rsp+3F0h+var_378], r14
0x14000f3d9  lea     r15, aOnecoreBaseDia_5; "onecore\\base\\diagnosis\\feedback\\siu"...
0x14000f3e0  mov     qword ptr [rsp+3F0h+var_380], r15
0x14000f3e5  mov     dword ptr [rsp+3F0h+var_390], edi
0x14000f3e9  lea     rax, aReaderSetprope; "reader->SetProperty failed."
0x14000f3f0  mov     [rsp+3F0h+var_388], rax
0x14000f3f5  lea     rax, [rsp+3F0h+var_398]
0x14000f3fa  mov     [rsp+3F0h+var_3A8], rax
0x14000f3ff  lea     rax, [rsp+3F0h+var_3A0]
0x14000f404  mov     [rsp+3F0h+var_3B0], rax
0x14000f409  lea     rax, [rsp+3F0h+var_378]
0x14000f40e  mov     [rsp+3F0h+var_3B8], rax
0x14000f413  lea     rax, [rsp+3F0h+var_380]
0x14000f418  mov     [rsp+3F0h+var_3C0], rax
0x14000f41d  lea     rax, [rsp+3F0h+var_390]
0x14000f422  mov     [rsp+3F0h+var_3C8], rax
0x14000f427  lea     rax, [rsp+3F0h+var_388]
0x14000f42c  lea     rdx, byte_14002289D
0x14000f433  jmp     loc_14000FB6F
0x14000f438  mov     rcx, [rbp+2F0h+ppvObject]
0x14000f43c  mov     rax, [rcx]
0x14000f43f  mov     rdx, [rbp+2F0h+ppstm]
0x14000f443  mov     rax, [rax+18h]
  ... truncated ...
```
