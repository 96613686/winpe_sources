# CHttpIoRequestWinHttp::StatusCallback(ulong,void *,ulong)

- ea: `0x18009f024`
- end: `0x1800a027b`
- name: `?StatusCallback@CHttpIoRequestWinHttp@@AEAAXKPEAXK@Z`
- size: `4695`
- prototype: `void __fastcall(CHttpIoRequestWinHttp *__hidden this, unsigned int, union CHttpIoRequestWinHttp::STATUS_INFORMATION_BUFFER *, unsigned int)`
- caller_count: `1`
- callee_count: `24`
- tags: `broker_com_uri`

## callers

- `0x1800a0290`

## callees

- `0x1800018a4`
- `0x180001e7c`
- `0x1800022f4`
- `0x180002550`
- `0x1800025dc`
- `0x180002c8c`
- `0x180004120`
- `0x180004970`
- `0x180004a94`
- `0x180038984`
- `0x18004a888`
- `0x1800787d4`
- `0x180078c20`
- `0x18007969c`
- `0x180099cf8`
- `0x180099ec4`
- `0x18009a33c`
- `0x18009c6d4`
- `0x18009f024`
- `0x1800a0370`
- `0x1800a09c4`
- `0x1800a0ba8`
- `0x1800a0c0c`
- `0x180162010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18009f07b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800a0251`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18009f07b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800a0251`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18009f098`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18009f098`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f795`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f92e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009fb4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009fe28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f795`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f92e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009fb4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009fe28`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18009f2a2`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18009f2a2`
- `WINHTTP!WinHttpCloseHandle` at `0x18009f61e`
- `WINHTTP!WinHttpCloseHandle` at `0x18009fdc0`
- `WINHTTP!WinHttpCloseHandle` at `0x18009f61e`
- `WINHTTP!WinHttpCloseHandle` at `0x18009fdc0`
- `WINHTTP!WinHttpWriteData` at `0x18009fb31`
- `WINHTTP!WinHttpWriteData` at `0x18009fb31`
- `WINHTTP!WinHttpReadData` at `0x18009f77f`
- `WINHTTP!WinHttpReadData` at `0x18009f77f`
- `WINHTTP!WinHttpReceiveResponse` at `0x18009fe12`
- `WINHTTP!WinHttpReceiveResponse` at `0x18009fe12`
- `WINHTTP!WinHttpWebSocketQueryCloseStatus` at `0x18009f52d`
- `WINHTTP!WinHttpWebSocketQueryCloseStatus` at `0x18009f52d`
- `WINHTTP!WinHttpWebSocketClose` at `0x18009f67d`
- `WINHTTP!WinHttpWebSocketClose` at `0x18009f67d`

## string_xrefs

- `0x18009fba2`: `WinHttpWriteData failed`
- `0x18009f7e5`: `WinHttpReadData failed`
- `0x18009fdd6`: `WINHTTP_CALLBACK_STATUS_SENDREQUEST_COMPLETE called`
- `0x18009fad4`: `Partial write`
- `0x18009fc13`: `Unexpected callback in WINHTTP_CALLBACK_STATUS_WRITE_COMPLETE for out channel`
- `0x18009f85e`: `Unexpected callback in WINHTTP_CALLBACK_STATUS_DATA_AVAILABLE for write stream`
- `0x18009f6e9`: `Unexpected callback in WINHTTP_CALLBACK_STATUS_READ_COMPLETE for write stream`
- `0x1800a014c`: `Unexpected stream type in API_WRITE_DATA`
- `0x1800a01b0`: `Unexpected stream type in API_READ_DATA`
- `0x18009f2c1`: `WINHTTP_CALLBACK_STATUS_HANDLE_CREATED called`
- `0x18009fd46`: `WINHTTP_CALLBACK_STATUS_CLOSE_COMPLETE called`
- `0x18009fcba`: `WINHTTP_CALLBACK_STATUS_SHUTDOWN_COMPLETE called`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CHttpIoRequestWinHttp::StatusCallback(
        CHttpIoRequestWinHttp *this,
        unsigned int a2,
        OLECHAR *a3,
        unsigned int a4)
{
  signed int LastError; // r14d
  unsigned __int8 *v9; // r13
  int v10; // ecx
  int v11; // r9d
  int v12; // r8d
  const char *v13; // rax
  int *v14; // rdx
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  int v18; // r8d
  int v19; // r9d
  unsigned __int64 v20; // r11
  unsigned __int64 v21; // r15
  unsigned __int16 *v22; // rax
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  unsigned int v26; // ecx
  int v27; // r15d
  const char *v28; // rcx
  void *v29; // r15
  int v30; // r8d
  int v31; // r9d
  int v32; // ecx
  int v33; // ecx
  volatile __int32 *v34; // rax
  DWORD v35; // eax
  DWORD v36; // r8d
  signed int v37; // eax
  int v38; // r8d
  int v39; // r9d
  const char *v40; // rax
  __int64 *v41; // rdx
  const char *v42; // rax
  __int16 *v43; // rdx
  int v44; // r8d
  int v45; // r9d
  unsigned int v46; // eax
  unsigned int v47; // ebx
  unsigned int v48; // eax
  unsigned int v49; // ecx
  int v50; // r8d
  int v51; // r9d
  unsigned int v52; // eax
  int v53; // ecx
  int v54; // r8d
  int v55; // r9d
  char *v56; // rbx
  __int16 *v57; // rdx
  unsigned int v58; // eax
  unsigned int v59; // r8d
  unsigned int v60; // eax
  int v61; // ecx
  int v62; // ecx
  unsigned int v63; // r8d
  unsigned int v64; // eax
  unsigned __int64 v65; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pdwReasonLengthConsumed[2]; // [rsp+58h] [rbp-A8h] BYREF
  const char *v67; // [rsp+60h] [rbp-A0h] BYREF
  const char *v68; // [rsp+68h] [rbp-98h] BYREF
  const char *v69; // [rsp+70h] [rbp-90h] BYREF
  bool v70; // [rsp+78h] [rbp-88h]
  unsigned int v71; // [rsp+7Ch] [rbp-84h] BYREF
  USHORT pusStatus[4]; // [rsp+80h] [rbp-80h] BYREF
  GUID ActivityId; // [rsp+88h] [rbp-78h] BYREF
  _BYTE pvReason[128]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v75[264]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v76[264]; // [rsp+330h] [rbp+230h] BYREF

  LastError = 0;
  v71 = 0;
  v9 = 0;
  ActivityId = *(GUID *)((char *)this + 120);
  EventActivityIdControl(4u, &ActivityId);
  if ( *((_BYTE *)this + 136) )
    v70 = 0;
  else
    v70 = TlsGetValue(*((_DWORD *)this + 148)) == (LPVOID)4660;
  v12 = -2147467259;
  if ( a2 > 0x4000 )
  {
    v26 = 0x100000;
    if ( a2 <= 0x100000 )
    {
      v27 = 0;
      if ( a2 != 0x100000 )
      {
        switch ( a2 )
        {
          case 0x8000u:
            if ( (unsigned int)CallbackContext > 4 )
            {
              LODWORD(v65) = a3 != 0 ? (unsigned int)a3 : 0;
              v67 = "WINHTTP_CALLBACK_STATUS_INTERMEDIATE_RESPONSE";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                v65,
                (unsigned int)&dword_1801B127C,
                -2147467259,
                v11,
                (__int64)&v67,
                (__int64)&v65);
            }
            goto LABEL_199;
          case 0x10000u:
            v47 = *(_DWORD *)a3;
            v48 = CHttpIoRequestWinHttp::CertErrorToHResult((CHttpIoRequestWinHttp *)0x100000, v47);
            *((_DWORD *)this + 25) = v47;
            if ( (unsigned int)CallbackContext <= 2 )
              goto LABEL_199;
            LODWORD(v65) = *((_DWORD *)this + 25);
            v67 = "StatusCallback";
            pdwReasonLengthConsumed[0] = 2239;
            v28 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
            v68 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
            v71 = v48;
            v42 = "WINHTTP_CALLBACK_STATUS_SECURE_FAILURE called";
            v43 = (__int16 *)byte_1801B142B;
            break;
          case 0x20000u:
            if ( (unsigned int)CallbackContext > 4 )
            {
              v67 = "WINHTTP_CALLBACK_STATUS_HEADERS_AVAILABLE called";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
                (unsigned int)&CallbackContext,
                (unsigned int)qword_1801B18C8,
                0,
                v11,
                (__int64)&v67);
            }
            pdwReasonLengthConsumed[0] = 0;
            if ( CHttpIoRequestWinHttp::GetResponseStatusCode(this, pdwReasonLengthConsumed)
              && pdwReasonLengthConsumed[0] == 101 )
            {
              if ( CHttpIoRequestWinHttp::WebSocketCompleteUpgrade(this) )
              {
                *((_DWORD *)this + 24) = 3;
              }
              else
              {
                LastError = GetLastError();
                if ( (unsigned int)CallbackContext > 2 )
                {
                  v67 = "StatusCallback";
                  LODWORD(v65) = 1907;
                  v68 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
                  if ( LastError > 0 )
                    v46 = (unsigned __int16)LastError | 0x80070000;
                  else
                    v46 = LastError;
                  *(_DWORD *)pusStatus = v46;
                  v69 = "WINHTTP_CALLBACK_STATUS_HEADERS_AVAILABLE called";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                    (unsigned int)"onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp",
                    (unsigned int)&dword_1801B1884,
                    v44,
                    v45,
                    (__int64)&v69,
                    (__int64)pusStatus,
                    (__int64)&v68,
                    (__int64)&v65,
                    (__int64)&v67);
                }
              }
            }
            goto LABEL_37;
          default:
            LODWORD(v28) = 0x40000;
            if ( a2 != 0x40000 )
            {
              if ( a2 != 0x80000 )
                goto LABEL_142;
              if ( *((_DWORD *)this + 24) == 3 )
              {
                if ( a3 && a4 >= 8 && *((_DWORD *)a3 + 1) == 4 )
                {
                  v29 = (void *)_InterlockedCompareExchange64((volatile signed __int64 *)this + 4, 0, 0);
                  pusStatus[0] = 1000;
                  pdwReasonLengthConsumed[0] = 0;
                  memset_0(pvReason, 0, 0x7Cu);
                  if ( v29 )
                  {
                    if ( !WinHttpWebSocketQueryCloseStatus(v29, pusStatus, pvReason, 0x7Bu, pdwReasonLengthConsumed)
                      && pdwReasonLengthConsumed[0] - 1 <= 0x7A )
                    {
                      pvReason[123] = 0;
                      if ( (unsigned int)CallbackContext > 4 )
                      {
                        v68 = pvReason;
                        v69 = "Received websocket close frame reason";
                        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
                          v32,
                          (unsigned int)word_1801B16D2,
                          v30,
                          v31,
                          (__int64)&v69,
                          (__int64)&v68);
                      }
                    }
                  }
                  v33 = 0;
                  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 19, 0, 0) )
                  {
                    _InterlockedExchange64((volatile __int64 *)this + 4, 0);
                    if ( (unsigned int)CallbackContext > 4 )
                    {
                      LODWORD(v65) = pusStatus[0];
                      v68 = "Received Websocket close frame reply.";
                      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                        0,
                        (unsigned int)byte_1801B16A5,
                        v30,
                        v31,
                        (__int64)&v68,
                        (__int64)&v65);
                    }
                    if ( (unsigned int)CallbackContext > 4 )
                    {
                      v68 = (const char *)v29;
                      v69 = "Closing Websocket Handle";
                      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
                        v33,
                        (unsigned int)byte_1801B167D,
                        v30,
                        v31,
                        (__int64)&v69,
                        (__int64)&v68);
                    }
                    if ( v29 )
                      WinHttpCloseHandle(v29);
                    v27 = 0;
                  }
                  else
                  {
                    if ( (unsigned int)CallbackContext > 4 )
                    {
                      LODWORD(v65) = pusStatus[0];
                      v68 = "Received Websocket close frame. Sending reply.";
                      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                        0,
                        (unsigned int)qword_1801B1650,
                        v30,
                        v31,
                        (__int64)&v68,
                        (__int64)&v65);
                    }
                    if ( v29 )
                      WinHttpWebSocketClose(v29, pusStatus[0], 0, 0);
                    a2 = 0x2000000;
                    v27 = 1;
                    a4 = 0;
                  }
                  goto LABEL_87;
                }
                v9 = (unsigned __int8 *)*((_QWORD *)this + 22);
              }
              else
              {
                if ( *((_DWORD *)this + 24) != 1 )
                {
                  if ( (unsigned int)CallbackContext > 2 )
                  {
                    LODWORD(v65) = 0x80000;
                    v68 = "StatusCallback";
                    pdwReasonLengthConsumed[0] = 2111;
                    v69 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
                    *(_DWORD *)pusStatus = -2147467259;
                    v67 = "Unexpected callback in WINHTTP_CALLBACK_STATUS_READ_COMPLETE for write stream";
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                      0x40000,
                      (unsigned int)word_1801B1602,
                      -2147467259,
                      v11,
                      (__int64)&v67,
                      (__int64)pusStatus,
                      (__int64)&v69,
                      (__int64)pdwReasonLengthConsumed,
                      (__int64)&v68,
                      (__int64)&v65);
                  }
                  goto LABEL_87;
                }
                v71 = a4;
                a4 = 0;
                *((_DWORD *)this + 37) -= v71;
                v9 = (unsigned __int8 *)a3;
              }
              v27 = 1;
LABEL_87:
              v34 = (volatile __int32 *)((char *)this + 140);
              goto LABEL_134;
            }
            if ( *((_DWORD *)this + 24) == 1 )
            {
              if ( !a3 )
                goto LABEL_199;
              v35 = *(_DWORD *)a3;
              *((_DWORD *)this + 37) = *(_DWORD *)a3;
              v36 = *((_DWORD *)this + 38);
              if ( v36 >= v35 )
                v36 = v35;
              if ( WinHttpReadData(*((HINTERNET *)this + 3), *((LPVOID *)this + 22), v36, 0) )
                goto LABEL_199;
              a2 = 0x80000;
              a4 = 0;
              v37 = GetLastError();
              LastError = v37;
              _InterlockedExchange((volatile __int32 *)this + 35, 0);
              if ( (unsigned int)CallbackContext > 2 )
              {
                v67 = "StatusCallback";
                LODWORD(v65) = 2006;
                v68 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
                if ( v37 > 0 )
                  v37 = (unsigned __int16)v37 | 0x80070000;
                pdwReasonLengthConsumed[0] = v37;
                v40 = "WinHttpReadData failed";
                v41 = qword_1801B1748;
LABEL_97:
                v69 = v40;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                  (unsigned int)"onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp",
                  (_DWORD)v41,
                  v38,
                  v39,
                  (__int64)&v69,
                  (__int64)pdwReasonLengthConsumed,
                  (__int64)&v68,
                  (__int64)&v65,
                  (__int64)&v67);
              }
LABEL_38:
              if ( v70 )
              {
                if ( CHttpIoRequestWinHttp::StoreStatusInfoForProcessing(this, a2, a3, a4, LastError, v71, v9) )
                {
                  (**(void (__fastcall ***)(CHttpIoRequestWinHttp *))this)(this);
                  SubmitThreadpoolWork(*((PTP_WORK *)this + 14));
                }
                else if ( (unsigned int)CallbackContext > 2 )
                {
                  v67 = "StatusCallback";
                  LODWORD(v65) = 2356;
                  v68 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
                  pdwReasonLengthConsumed[0] = -2147467259;
                  v69 = "StoreStatusInfoForProcessing error";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                    v15,
                    (unsigned int)qword_1801B11E8,
                    v16,
                    v17,
                    (__int64)&v69,
                    (__int64)pdwReasonLengthConsumed,
                    (__int64)&v68,
                    (__int64)&v65,
                    (__int64)&v67);
                }
              }
              else
              {
                CHttpIoRequestWinHttp::ContinueProcessingCallback(
                  this,
                  a2,
                  (union CHttpIoRequestWinHttp::STATUS_INFORMATION_BUFFER *)a3,
                  a4,
                  LastError,
                  v71,
                  v9);
              }
              goto LABEL_199;
            }
            if ( (unsigned int)CallbackContext <= 2 )
              goto LABEL_199;
            LODWORD(v65) = 0x40000;
            v67 = "StatusCallback";
            pdwReasonLengthConsumed[0] = 2013;
            v68 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
            v71 = -2147467259;
            v42 = "Unexpected callback in WINHTTP_CALLBACK_STATUS_DATA_AVAILABLE for write stream";
            v43 = word_1801B16FA;
            break;
        }
LABEL_100:
        v69 = v42;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (_DWORD)v28,
          (_DWORD)v43,
          v12,
          v11,
          (__int64)&v69,
          (__int64)&v71,
          (__int64)&v68,
          (__int64)pdwReasonLengthConsumed,
          (__int64)&v67,
          (__int64)&v65);
        goto LABEL_199;
      }
      if ( *((_DWORD *)this + 24) == 3 )
      {
        v9 = (unsigned __int8 *)*((_QWORD *)this + 23);
      }
      else
      {
        if ( *((_DWORD *)this + 24) != 2 )
        {
          if ( (unsigned int)CallbackContext > 2 )
          {
            LODWORD(v65) = 0x100000;
            v67 = "StatusCallback";
            pdwReasonLengthConsumed[0] = 1976;
            v68 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
            *(_DWORD *)pusStatus = -2147467259;
            v69 = "Unexpected callback in WINHTTP_CALLBACK_STATUS_WRITE_COMPLETE for out channel";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              0x100000,
              (unsigned int)&dword_1801B178C,
              -2147467259,
              v11,
              (__int64)&v69,
              (__int64)pusStatus,
              (__int64)&v68,
              (__int64)pdwReasonLengthConsumed,
              (__int64)&v67,
              (__int64)&v65);
          }
          goto LABEL_133;
        }
        v9 = (unsigned __int8 *)*((_QWORD *)this + 23);
        if ( !a3 || a4 < 4 )
        {
LABEL_133:
          v34 = (volatile __int32 *)((char *)this + 144);
LABEL_134:
          _InterlockedExchange(v34, 0);
          if ( !v27 )
            goto LABEL_199;
          goto LABEL_38;
        }
        v49 = *(_DWORD *)a3;
        *((_DWORD *)this + 51) += *(_DWORD *)a3;
        if ( *((_DWORD *)this + 51) < *((_DWORD *)this + 52) )
        {
          if ( (unsigned int)CallbackContext > 5 )
          {
            LODWORD(v65) = *((_DWORD *)this + 52);
            pdwReasonLengthConsumed[0] = *((_DWORD *)this + 51);
            *(_DWORD *)pusStatus = v49;
            v67 = "Partial write";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v49,
              (unsigned int)&word_1801B181E,
              -2147467259,
              v11,
              (__int64)&v67,
              (__int64)pusStatus,
              (__int64)pdwReasonLengthConsumed,
              (__int64)&v65);
          }
          if ( !WinHttpWriteData(
                  *((HINTERNET *)this + 3),
                  (LPCVOID)(*((_QWORD *)this + 24) + *((unsigned int *)this + 51)),
                  *((_DWORD *)this + 52) - *((_DWORD *)this + 51),
                  0) )
          {
            a2 = 0x100000;
            v27 = 1;
            a4 = 0;
            LastError = GetLastError();
            _InterlockedExchange((volatile __int32 *)this + 36, 0);
            if ( (unsigned int)CallbackContext > 2 )
            {
              v67 = "StatusCallback";
              LODWORD(v65) = 1963;
              v68 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
              if ( LastError > 0 )
                v52 = (unsigned __int16)LastError | 0x80070000;
              else
                v52 = LastError;
              pdwReasonLengthConsumed[0] = v52;
              v69 = "WinHttpWriteData failed";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                (unsigned int)"onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp",
                (unsigned int)word_1801B17DA,
                v50,
                v51,
                (__int64)&v69,
                (__int64)pdwReasonLengthConsumed,
                (__int64)&v68,
                (__int64)&v65,
                (__int64)&v67);
            }
          }
          goto LABEL_133;
        }
      }
      v27 = 1;
      goto LABEL_133;
    }
    if ( a2 != 0x200000 )
    {
      if ( a2 == 0x400000 )
      {
        if ( (unsigned int)CallbackContext > 4 )
        {
          v67 = "WINHTTP_CALLBACK_STATUS_SENDREQUEST_COMPLETE called";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            (unsigned int)&CallbackContext,
            (unsigned int)&dword_1801B192C,
            0,
            v11,
            (__int64)&v67);
        }
        if ( *((_DWORD *)this + 24) == 2 )
          goto LABEL_37;
        if ( WinHttpReceiveResponse(*((HINTERNET *)this + 3), 0) )
          goto LABEL_199;
        a2 = 0x20000;
        a4 = 0;
        LastError = GetLastError();
        if ( (unsigned int)CallbackContext <= 2 )
          goto LABEL_38;
        v67 = "StatusCallback";
        LODWORD(v65) = 1884;
        v68 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
        if ( LastError > 0 )
          v58 = (unsigned __int16)LastError | 0x80070000;
        else
          v58 = LastError;
        pdwReasonLengthConsumed[0] = v58;
        v40 = "WinHttpReceiveResponse failed";
        v41 = qword_1801B18E8;
        goto LABEL_97;
      }
      if ( a2 != 0x2000000 )
      {
        if ( a2 != 0x4000000 )
          goto LABEL_142;
        if ( (unsigned int)CallbackContext > 4 )
        {
          v67 = "WINHTTP_CALLBACK_STATUS_SHUTDOWN_COMPLETE called";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            (unsigned int)&CallbackContext,
            (unsigned int)word_1801B1312,
            0,
            v11,
            (__int64)&v67);
        }
        goto LABEL_199;
      }
      if ( (unsigned int)CallbackContext > 4 )
      {
        v67 = "WINHTTP_CALLBACK_STATUS_CLOSE_COMPLETE called";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (unsigned int)&CallbackContext,
          (unsigned int)word_1801B135A,
          0,
          v11,
          (__int64)&v67);
      }
      v56 = (char *)_InterlockedExchange64((volatile __int64 *)this + 4, 0);
      if ( !v56 )
        goto LABEL_199;
      if ( (unsigned int)CallbackContext > 4 )
      {
        v57 = word_1801B1332;
LABEL_149:
        v68 = "Closing Websocket Handle";
        v67 = v56;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
          v26,
          (_DWORD)v57,
          v12,
          v11,
          (__int64)&v68,
          (__int64)&v67);
        goto LABEL_150;
      }
      goto LABEL_150;
    }
    if ( (unsigned int)CallbackContext > 4 )
    {
      v67 = "WINHTTP_CALLBACK_STATUS_REQUEST_ERROR called";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&CallbackContext,
        (unsigned int)word_1801B15E2,
        0,
        v11,
        (__int64)&v67);
    }
    if ( *((_BYTE *)this + 72) )
    {
      memset_0(v76, 0, 0x208u);
      CHttpIoRequestWinHttp::WinHTTPOperationToString(*((_DWORD *)a3 + 4), v76, v59);
      LastError = *((_DWORD *)a3 + 2);
      if ( (unsigned int)CallbackContext > 2 )
      {
        v67 = (const char *)v76;
        v68 = "StatusCallback";
        LODWORD(v65) = 2132;
        v69 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
        if ( LastError > 0 )
          v60 = (unsigned __int16)LastError | 0x80070000;
        else
          v60 = LastError;
        pdwReasonLengthConsumed[0] = v60;
        *(_QWORD *)pusStatus = "WINHTTP_CALLBACK_STATUS_REQUEST_ERROR WebSocket operation";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          (unsigned int)"onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp",
          (unsigned int)&byte_1801B158F,
          v12,
          v11,
          (__int64)pusStatus,
          (__int64)pdwReasonLengthConsumed,
          (__int64)&v69,
          (__int64)&v65,
          (__int64)&v68,
          (__int64)&v67);
      }
      v61 = *((_DWORD *)a3 + 4);
      if ( v61 )
      {
        v62 = v61 - 1;
        if ( v62 )
        {
          v26 = v62 - 1;
          if ( v26 > 1 )
            goto LABEL_199;
          v56 = (char *)_InterlockedExchange64((volatile __int64 *)this + 4, 0);
          if ( !v56 )
            goto LABEL_199;
          if ( (unsigned int)CallbackContext > 4 )
          {
            v57 = (__int16 *)&byte_1801B1567;
            goto LABEL_149;
          }
LABEL_150:
          WinHttpCloseHandle(v56);
          goto LABEL_199;
        }
LABEL_192:
        v9 = (unsigned __int8 *)*((_QWORD *)this + 22);
        _InterlockedExchange((volatile __int32 *)this + 35, 0);
        goto LABEL_38;
      }
    }
    else
    {
      memset_0(v75, 0, 0x208u);
      CHttpIoRequestWinHttp::WinHTTPStatusAPIToString(*(_QWORD *)a3, v75, v63);
      LastError = *((_DWORD *)a3 + 2);
      if ( (unsigned int)CallbackContext > 2 )
      {
        v67 = (const char *)v75;
        v68 = "StatusCallback";
        LODWORD(v65) = 2176;
        v69 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
        if ( LastError > 0 )
          v64 = (unsigned __int16)LastError | 0x80070000;
        else
          v64 = LastError;
        pdwReasonLengthConsumed[0] = v64;
        *(_QWORD *)pusStatus = "WINHTTP_CALLBACK_STATUS_REQUEST_ERROR HTTP API";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          (unsigned int)"onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp",
          (unsigned int)&word_1801B151E,
          v12,
          v11,
          (__int64)pusStatus,
          (__int64)pdwReasonLengthConsumed,
          (__int64)&v69,
          (__int64)&v65,
          (__int64)&v68,
          (__int64)&v67);
      }
      switch ( *(_QWORD *)a3 )
      {
        case 1LL:
          goto LABEL_38;
        case 2LL:
          a2 = 0x80000;
          goto LABEL_192;
        case 3LL:
          if ( *((_DWORD *)this + 24) != 1 )
          {
            if ( (unsigned int)CallbackContext <= 2 )
              goto LABEL_199;
            LODWORD(v65) = *((_DWORD *)this + 24);
            v67 = "StatusCallback";
            pdwReasonLengthConsumed[0] = 2221;
            v68 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
            v71 = -2147418113;
            v42 = "Unexpected stream type in API_READ_DATA";
            v43 = &word_1801B147E;
            goto LABEL_100;
          }
          goto LABEL_192;
      }
      if ( *(_QWORD *)a3 != 4 )
      {
        if ( *(_QWORD *)a3 != 5 )
          goto LABEL_199;
        a2 = 0x20000;
        goto LABEL_38;
      }
      if ( *((_DWORD *)this + 24) != 2 )
      {
        if ( (unsigned int)CallbackContext <= 2 )
          goto LABEL_199;
        LODWORD(v65) = *((_DWORD *)this + 24);
        v67 = "StatusCallback";
        pdwReasonLengthConsumed[0] = 2199;
        v68 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
        v71 = -2147418113;
        v42 = "Unexpected stream type in API_WRITE_DATA";
        v43 = &word_1801B14CE;
        goto LABEL_100;
      }
    }
    v9 = (unsigned __int8 *)*((_QWORD *)this + 23);
    _InterlockedExchange((volatile __int32 *)this + 36, 0);
    goto LABEL_38;
  }
  if ( a2 == 0x4000 )
  {
    if ( (unsigned int)CallbackContext > 4 )
    {
      v65 = (unsigned __int64)"WINHTTP_CALLBACK_STATUS_REDIRECT called";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&CallbackContext,
        (unsigned int)byte_1801B13E3,
        0,
        v11,
        (__int64)&v65);
    }
    if ( a3 )
    {
      v65 = 0;
      v18 = StringCchLengthW(a3, 0x7FFFFFFFu, &v65);
      if ( v18 < 0 )
      {
        if ( (unsigned int)CallbackContext > 2 )
        {
          v65 = v20;
          pdwReasonLengthConsumed[0] = 2268;
          v69 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
          *(_DWORD *)pusStatus = v18;
          v68 = "WINHTTP_CALLBACK_STATUS_REDIRECT URL length is incorrect";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            (unsigned int)"onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp",
            (unsigned int)word_1801B137A,
            v18,
            v19,
            (__int64)&v68,
            (__int64)pusStatus,
            (__int64)&v69,
            (__int64)pdwReasonLengthConsumed,
            (__int64)&v65);
        }
      }
      else
      {
        v21 = v65 + 1;
        v22 = (unsigned __int16 *)operator new(saturated_mul(v65 + 1, 2u));
        *((_QWORD *)this + 73) = v22;
        if ( v22 )
        {
          StringCchCopyW(v22, v21, a3);
          if ( (unsigned int)CallbackContext > 4 )
          {
            v65 = *((_QWORD *)this + 73);
            *(_QWORD *)pdwReasonLengthConsumed = "WINHTTP_CALLBACK_STATUS_REDIRECT";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
              v23,
              (unsigned int)&word_1801B13BE,
              v24,
              v25,
              (__int64)pdwReasonLengthConsumed,
              (__int64)&v65);
          }
        }
      }
    }
    goto LABEL_37;
  }
  if ( a2 <= 0x20 )
  {
    switch ( a2 )
    {
      case 0x20u:
        goto LABEL_199;
      case 1u:
        if ( (unsigned int)CallbackContext <= 4 )
          goto LABEL_199;
        if ( !a3 )
          a3 = (OLECHAR *)&word_18016FF08;
        v13 = "WINHTTP_CALLBACK_STATUS_RESOLVING_NAME";
        v14 = (int *)&word_1801B1256;
        break;
      case 2u:
        if ( (unsigned int)CallbackContext <= 4 )
          goto LABEL_199;
        if ( !a3 )
          a3 = (OLECHAR *)&word_18016FF08;
        v13 = "WINHTTP_CALLBACK_STATUS_NAME_RESOLVED";
        v14 = &dword_1801B12EC;
        break;
      case 4u:
        if ( (unsigned int)CallbackContext <= 4 )
          goto LABEL_199;
        if ( !a3 )
          a3 = (OLECHAR *)&word_18016FF08;
        v13 = "WINHTTP_CALLBACK_STATUS_CONNECTING_TO_SERVER";
        v14 = &dword_1801B12A4;
        break;
      case 8u:
        if ( (unsigned int)CallbackContext <= 4 )
          goto LABEL_199;
        if ( !a3 )
          a3 = (OLECHAR *)&word_18016FF08;
        v13 = "WINHTTP_CALLBACK_STATUS_CONNECTED_TO_SERVER";
        v14 = (int *)qword_1801B12C8;
        break;
      case 0x10u:
        goto LABEL_199;
      default:
        goto LABEL_142;
    }
    *(_QWORD *)pdwReasonLengthConsumed = v13;
    v65 = (unsigned __int64)a3;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
      v10,
      (_DWORD)v14,
      -2147467259,
      v11,
      (__int64)pdwReasonLengthConsumed,
      (__int64)&v65);
    goto LABEL_199;
  }
  if ( a2 == 64 || a2 == 128 )
    goto LABEL_199;
  if ( a2 != 1024 )
  {
    if ( a2 == 2048 )
    {
      if ( (unsigned int)CallbackContext > 4 )
      {
        v65 = (unsigned __int64)a3;
        *(_QWORD *)pdwReasonLengthConsumed = "WINHTTP_CALLBACK_STATUS_HANDLE_CLOSING called";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
          v10,
          (unsigned int)&dword_1801B185C,
          -2147467259,
          v11,
          (__int64)pdwReasonLengthConsumed,
          (__int64)&v65);
      }
LABEL_37:
      a4 = 0;
      goto LABEL_38;
    }
LABEL_142:
    CHttpIoRequestWinHttp::CallbackStatusToString(a2, v75, 0x80004005);
    if ( (unsigned int)CallbackContext > 4 )
    {
      v67 = (const char *)v75;
      v68 = "Winhttp callback called";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v53,
        (unsigned int)&dword_1801B122C,
        v54,
        v55,
        (__int64)&v68,
        (__int64)&v67);
    }
    goto LABEL_199;
  }
  if ( (unsigned int)CallbackContext > 4 )
  {
    v65 = (unsigned __int64)a3;
    *(_QWORD *)pdwReasonLengthConsumed = "WINHTTP_CALLBACK_STATUS_HANDLE_CREATED called";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      v10,
      (unsigned int)byte_1801B1403,
      -2147467259,
      v11,
      (__int64)pdwReasonLengthConsumed,
      (__int64)&v65);
  }
LABEL_199:
  EventActivityIdControl(2u, &ActivityId);
}

```

## disassembly

```asm
0x18009f024  push    rbp
0x18009f026  push    rbx
0x18009f027  push    rsi
0x18009f028  push    rdi
0x18009f029  push    r12
0x18009f02b  push    r13
0x18009f02d  push    r14
0x18009f02f  push    r15
0x18009f031  lea     rbp, [rsp-458h]
0x18009f039  sub     rsp, 558h
0x18009f040  mov     rax, cs:__security_cookie
0x18009f047  xor     rax, rsp
0x18009f04a  mov     [rbp+490h+var_50], rax
0x18009f051  mov     r12d, r9d
0x18009f054  mov     rbx, r8
0x18009f057  mov     esi, edx
0x18009f059  mov     rdi, rcx
0x18009f05c  xor     r14d, r14d
0x18009f05f  mov     [rsp+590h+var_514], r14d
0x18009f064  xor     r13d, r13d
0x18009f067  movups  xmm0, xmmword ptr [rcx+78h]
0x18009f06b  movdqu  xmmword ptr [rbp+490h+ActivityId.Data1], xmm0
0x18009f070  lea     rdx, [rbp+490h+ActivityId]; ActivityId
0x18009f074  lea     r15d, [r14+4]
0x18009f078  mov     ecx, r15d; ControlCode
0x18009f07b  call    cs:__imp_EventActivityIdControl
0x18009f081  nop
0x18009f082  cmp     [rdi+88h], r13b
0x18009f089  jz      short loc_18009F092
0x18009f08b  mov     [rsp+590h+var_518], r13b
0x18009f090  jmp     short loc_18009F0A9
0x18009f092  mov     ecx, [rdi+250h]; dwTlsIndex
0x18009f098  call    cs:__imp_TlsGetValue
0x18009f09e  cmp     rax, 1234h
0x18009f0a4  setz    [rsp+590h+var_518]
0x18009f0a9  lea     r11, aStatuscallback; "StatusCallback"
0x18009f0b0  lea     rdx, aOnecoreTermsrv_8; "onecore\\termsrv\\rdp\\win\\httpio\\win"...
0x18009f0b7  mov     eax, 4000h
0x18009f0bc  mov     r8d, 80004005h; unsigned int
0x18009f0c2  cmp     esi, eax
0x18009f0c4  ja      loc_18009F468
0x18009f0ca  jz      loc_18009F2F2
0x18009f0d0  cmp     esi, 20h ; ' '
0x18009f0d3  ja      loc_18009F1EB
0x18009f0d9  jz      loc_1800A0248
0x18009f0df  mov     eax, esi
0x18009f0e1  sub     eax, 1
0x18009f0e4  jz      loc_18009F1BB
0x18009f0ea  sub     eax, 1
0x18009f0ed  jz      loc_18009F18B
0x18009f0f3  sub     eax, 2
0x18009f0f6  jz      short loc_18009F15E
0x18009f0f8  sub     eax, r15d
0x18009f0fb  jz      short loc_18009F10B
0x18009f0fd  cmp     eax, 8
0x18009f100  jz      loc_1800A0248
0x18009f106  jmp     loc_18009FCF1
0x18009f10b  mov     eax, cs:CallbackContext
0x18009f111  cmp     eax, r15d
0x18009f114  jbe     loc_1800A0248
0x18009f11a  lea     rax, word_18016FF08
0x18009f121  test    rbx, rbx
0x18009f124  cmovz   rbx, rax
0x18009f128  lea     rax, aWinhttpCallbac_8; "WINHTTP_CALLBACK_STATUS_CONNECTED_TO_SE"...
0x18009f12f  lea     rdx, qword_1801B12C8
0x18009f136  mov     qword ptr [rsp+590h+var_538], rax
0x18009f13b  lea     rax, [rsp+590h+var_540]
0x18009f140  mov     qword ptr [rsp+590h+var_568], rax
0x18009f145  lea     rax, [rsp+590h+var_538]
0x18009f14a  mov     [rsp+590h+var_540], rbx
0x18009f14f  mov     [rsp+590h+pdwReasonLengthConsumed], rax
0x18009f154  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18009f159  jmp     loc_1800A0248
0x18009f15e  mov     eax, cs:CallbackContext
0x18009f164  cmp     eax, r15d
0x18009f167  jbe     loc_1800A0248
0x18009f16d  lea     rax, word_18016FF08
0x18009f174  test    rbx, rbx
0x18009f177  cmovz   rbx, rax
0x18009f17b  lea     rax, aWinhttpCallbac_24; "WINHTTP_CALLBACK_STATUS_CONNECTING_TO_S"...
0x18009f182  lea     rdx, dword_1801B12A4
0x18009f189  jmp     short loc_18009F136
0x18009f18b  mov     eax, cs:CallbackContext
0x18009f191  cmp     eax, r15d
0x18009f194  jbe     loc_1800A0248
0x18009f19a  lea     rax, word_18016FF08
0x18009f1a1  test    rbx, rbx
0x18009f1a4  cmovz   rbx, rax
0x18009f1a8  lea     rax, aWinhttpCallbac_37; "WINHTTP_CALLBACK_STATUS_NAME_RESOLVED"
0x18009f1af  lea     rdx, dword_1801B12EC
0x18009f1b6  jmp     loc_18009F136
0x18009f1bb  mov     eax, cs:CallbackContext
0x18009f1c1  cmp     eax, r15d
0x18009f1c4  jbe     loc_1800A0248
0x18009f1ca  lea     rax, word_18016FF08
0x18009f1d1  test    rbx, rbx
0x18009f1d4  cmovz   rbx, rax
0x18009f1d8  lea     rax, aWinhttpCallbac_13; "WINHTTP_CALLBACK_STATUS_RESOLVING_NAME"
0x18009f1df  lea     rdx, word_1801B1256
0x18009f1e6  jmp     loc_18009F136
0x18009f1eb  mov     eax, esi
0x18009f1ed  sub     eax, 40h ; '@'
0x18009f1f0  jz      loc_1800A0248
0x18009f1f6  sub     eax, 40h ; '@'
0x18009f1f9  jz      loc_1800A0248
0x18009f1ff  sub     eax, 380h
0x18009f204  jz      loc_18009F2AD
0x18009f20a  cmp     eax, 400h
0x18009f20f  jnz     loc_18009FCF1
0x18009f215  mov     eax, cs:CallbackContext
0x18009f21b  cmp     eax, r15d
0x18009f21e  jbe     short loc_18009F251
0x18009f220  mov     [rsp+590h+var_540], rbx
0x18009f225  lea     rax, aWinhttpCallbac_28; "WINHTTP_CALLBACK_STATUS_HANDLE_CLOSING "...
0x18009f22c  mov     qword ptr [rsp+590h+var_538], rax
0x18009f231  lea     rax, [rsp+590h+var_540]
0x18009f236  mov     qword ptr [rsp+590h+var_568], rax
0x18009f23b  lea     rax, [rsp+590h+var_538]
0x18009f240  mov     [rsp+590h+pdwReasonLengthConsumed], rax
0x18009f245  lea     rdx, dword_1801B185C
0x18009f24c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18009f251  xor     r12d, r12d
0x18009f254  lea     r15, aStatuscallback; "StatusCallback"
0x18009f25b  mov     [rsp+590h+var_560], r13; unsigned __int8 *
0x18009f260  mov     eax, [rsp+590h+var_514]
0x18009f264  mov     r9d, r12d; unsigned int
0x18009f267  mov     r8, rbx; union CHttpIoRequestWinHttp::STATUS_INFORMATION_BUFFER *
0x18009f26a  mov     edx, esi; unsigned int
0x18009f26c  mov     rcx, rdi; this
0x18009f26f  mov     [rsp+590h+var_568], eax; unsigned int
0x18009f273  mov     dword ptr [rsp+590h+pdwReasonLengthConsumed], r14d; unsigned int
0x18009f278  cmp     [rsp+590h+var_518], 0
0x18009f27d  jz      loc_1800A0242
0x18009f283  call    ?StoreStatusInfoForProcessing@CHttpIoRequestWinHttp@@AEAA_NKPEAXKKKPEAE@Z; CHttpIoRequestWinHttp::StoreStatusInfoForProcessing(ulong,void *,ulong,ulong,ulong,uchar *)
0x18009f288  test    al, al
0x18009f28a  jz      loc_1800A01CA
0x18009f290  mov     rax, [rdi]
0x18009f293  mov     rcx, rdi
0x18009f296  mov     rax, [rax]
0x18009f299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f29e  mov     rcx, [rdi+70h]; pwk
0x18009f2a2  call    cs:__imp_SubmitThreadpoolWork
0x18009f2a8  jmp     loc_1800A0248
0x18009f2ad  mov     eax, cs:CallbackContext
0x18009f2b3  cmp     eax, r15d
0x18009f2b6  jbe     loc_1800A0248
0x18009f2bc  mov     [rsp+590h+var_540], rbx
0x18009f2c1  lea     rax, aWinhttpCallbac_32; "WINHTTP_CALLBACK_STATUS_HANDLE_CREATED "...
0x18009f2c8  mov     qword ptr [rsp+590h+var_538], rax
0x18009f2cd  lea     rax, [rsp+590h+var_540]
0x18009f2d2  mov     qword ptr [rsp+590h+var_568], rax
0x18009f2d7  lea     rax, [rsp+590h+var_538]
0x18009f2dc  mov     [rsp+590h+pdwReasonLengthConsumed], rax
0x18009f2e1  lea     rdx, byte_1801B1403
0x18009f2e8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18009f2ed  jmp     loc_1800A0248
0x18009f2f2  mov     eax, cs:CallbackContext
0x18009f2f8  cmp     eax, r15d
0x18009f2fb  jbe     short loc_18009F330
0x18009f2fd  lea     rax, aWinhttpCallbac_39; "WINHTTP_CALLBACK_STATUS_REDIRECT called"
0x18009f304  mov     [rsp+590h+var_540], rax
0x18009f309  lea     rax, [rsp+590h+var_540]
0x18009f30e  mov     [rsp+590h+pdwReasonLengthConsumed], rax
0x18009f313  xor     r8d, r8d
0x18009f316  lea     rdx, byte_1801B13E3
0x18009f31d  lea     rcx, CallbackContext
0x18009f324  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18009f329  lea     r11, aStatuscallback; "StatusCallback"
0x18009f330  test    rbx, rbx
0x18009f333  jz      loc_18009F251
0x18009f339  mov     [rsp+590h+var_540], 0
0x18009f342  lea     r8, [rsp+590h+var_540]; unsigned __int64 *
0x18009f347  mov     edx, 7FFFFFFFh; unsigned __int64
0x18009f34c  mov     rcx, rbx; unsigned __int16 *
0x18009f34f  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18009f354  mov     r8d, eax
0x18009f357  test    eax, eax
0x18009f359  js      loc_18009F3EE
0x18009f35f  mov     r15, [rsp+590h+var_540]
0x18009f364  inc     r15
0x18009f367  mov     eax, 2
0x18009f36c  mul     r15
0x18009f36f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18009f376  cmovb   rax, rcx
0x18009f37a  mov     rcx, rax; Size
0x18009f37d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18009f382  mov     [rdi+248h], rax
0x18009f389  test    rax, rax
0x18009f38c  jz      loc_18009F251
0x18009f392  mov     r8, rbx; unsigned __int16 *
0x18009f395  mov     rdx, r15; unsigned __int64
0x18009f398  mov     rcx, rax; unsigned __int16 *
0x18009f39b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18009f3a0  mov     r11d, cs:CallbackContext
0x18009f3a7  cmp     r11d, 4
0x18009f3ab  jbe     loc_18009F251
0x18009f3b1  mov     rax, [rdi+248h]
0x18009f3b8  mov     [rsp+590h+var_540], rax
0x18009f3bd  lea     rax, aWinhttpCallbac_0; "WINHTTP_CALLBACK_STATUS_REDIRECT"
0x18009f3c4  mov     qword ptr [rsp+590h+var_538], rax
0x18009f3c9  lea     rax, [rsp+590h+var_540]
0x18009f3ce  mov     qword ptr [rsp+590h+var_568], rax
0x18009f3d3  lea     rax, [rsp+590h+var_538]
0x18009f3d8  mov     [rsp+590h+pdwReasonLengthConsumed], rax
0x18009f3dd  lea     rdx, word_1801B13BE
0x18009f3e4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18009f3e9  jmp     loc_18009F251
0x18009f3ee  mov     eax, cs:CallbackContext
0x18009f3f4  cmp     eax, 2
0x18009f3f7  jbe     loc_18009F251
0x18009f3fd  mov     [rsp+590h+var_540], r11
0x18009f402  mov     [rsp+590h+var_538], 8DCh
0x18009f40a  lea     rcx, aOnecoreTermsrv_8; "onecore\\termsrv\\rdp\\win\\httpio\\win"...
0x18009f411  mov     [rsp+590h+var_520], rcx
0x18009f416  mov     dword ptr [rbp+490h+pusStatus], r8d
0x18009f41a  lea     rax, aWinhttpCallbac_10; "WINHTTP_CALLBACK_STATUS_REDIRECT URL le"...
0x18009f421  mov     [rsp+590h+var_528], rax
0x18009f426  lea     rax, [rsp+590h+var_540]
0x18009f42b  mov     [rsp+590h+var_550], rax
0x18009f430  lea     rax, [rsp+590h+var_538]
0x18009f435  mov     [rsp+590h+var_558], rax
0x18009f43a  lea     rax, [rsp+590h+var_520]
0x18009f43f  mov     [rsp+590h+var_560], rax
0x18009f444  lea     rax, [rbp+490h+pusStatus]
0x18009f448  mov     qword ptr [rsp+590h+var_568], rax
0x18009f44d  lea     rax, [rsp+590h+var_528]
0x18009f452  lea     rdx, word_1801B137A
0x18009f459  mov     [rsp+590h+pdwReasonLengthConsumed], rax
0x18009f45e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18009f463  jmp     loc_18009F251
0x18009f468  mov     ecx, 100000h; this
0x18009f46d  cmp     esi, ecx
0x18009f46f  ja      loc_18009FC7F
0x18009f475  xor     r15d, r15d
0x18009f478  cmp     esi, ecx
0x18009f47a  jz      loc_18009FA60
0x18009f480  cmp     esi, 8000h
0x18009f486  jz      loc_18009FA12
0x18009f48c  cmp     esi, 10000h
0x18009f492  jz      loc_18009F9B9
0x18009f498  cmp     esi, 20000h
0x18009f49e  jz      loc_18009F8B7
0x18009f4a4  mov     ecx, 40000h
0x18009f4a9  cmp     esi, ecx
0x18009f4ab  jz      loc_18009F748
0x18009f4b1  cmp     esi, 80000h
0x18009f4b7  jnz     loc_18009FCEB
0x18009f4bd  cmp     dword ptr [rdi+60h], 3
0x18009f4c1  jnz     loc_18009F69F
0x18009f4c7  test    rbx, rbx
0x18009f4ca  jz      loc_18009F696
0x18009f4d0  cmp     r12d, 8
0x18009f4d4  jb      loc_18009F696
0x18009f4da  cmp     dword ptr [rbx+4], 4
0x18009f4de  jnz     loc_18009F696
0x18009f4e4  xor     ecx, ecx
0x18009f4e6  xor     eax, eax
0x18009f4e8  lock cmpxchg [rdi+20h], rcx
0x18009f4ee  mov     r15, rax
0x18009f4f1  mov     eax, 3E8h
0x18009f4f6  mov     [rbp+490h+pusStatus], ax
0x18009f4fa  mov     [rsp+590h+var_538], ecx
0x18009f4fe  xor     edx, edx; Val
0x18009f500  lea     r8d, [rcx+7Ch]; Size
0x18009f504  lea     rcx, [rbp+490h+pvReason]; void *
0x18009f508  call    memset_0
0x18009f50d  test    r15, r15
0x18009f510  jz      short loc_18009F586
0x18009f512  lea     rax, [rsp+590h+var_538]
0x18009f517  mov     [rsp+590h+pdwReasonLengthConsumed], rax; pdwReasonLengthConsumed
0x18009f51c  mov     r9d, 7Bh ; '{'; dwReasonLength
0x18009f522  lea     r8, [rbp+490h+pvReason]; pvReason
0x18009f526  lea     rdx, [rbp+490h+pusStatus]; pusStatus
0x18009f52a  mov     rcx, r15; hWebSocket
0x18009f52d  call    cs:__imp_WinHttpWebSocketQueryCloseStatus
0x18009f533  test    eax, eax
0x18009f535  jnz     short loc_18009F586
0x18009f537  mov     eax, [rsp+590h+var_538]
0x18009f53b  dec     eax
0x18009f53d  cmp     eax, 7Ah ; 'z'
0x18009f540  ja      short loc_18009F586
0x18009f542  mov     [rbp+490h+var_475], 0
0x18009f546  mov     eax, cs:CallbackContext
0x18009f54c  cmp     eax, 4
0x18009f54f  jbe     short loc_18009F586
0x18009f551  lea     rax, [rbp+490h+pvReason]
0x18009f555  mov     [rsp+590h+var_528], rax
0x18009f55a  lea     rax, aReceivedWebsoc; "Received websocket close frame reason"
0x18009f561  mov     [rsp+590h+var_520], rax
0x18009f566  lea     rax, [rsp+590h+var_528]
0x18009f56b  mov     qword ptr [rsp+590h+var_568], rax
0x18009f570  lea     rax, [rsp+590h+var_520]
0x18009f575  mov     [rsp+590h+pdwReasonLengthConsumed], rax
0x18009f57a  lea     rdx, word_1801B16D2
0x18009f581  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18009f586  xor     ecx, ecx
0x18009f588  xor     eax, eax
0x18009f58a  lock cmpxchg [rdi+4Ch], ecx
0x18009f58f  jz      loc_18009F62C
0x18009f595  xor     eax, eax
  ... truncated ...
```
