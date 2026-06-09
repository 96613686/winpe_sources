# CHttpIoRequestWinHttp::IoReadDataAsync(uchar *,uint)

- ea: `0x18009d8d0`
- end: `0x18009dda4`
- name: `?IoReadDataAsync@CHttpIoRequestWinHttp@@UEAAJPEAEI@Z`
- size: `1236`
- prototype: `int(CHttpIoRequestWinHttp *__hidden this, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800018a4`
- `0x180001aa0`
- `0x180004970`
- `0x18009a1b0`
- `0x18009d8d0`
- `0x18009e350`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009dc47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009dcf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009dc47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009dcf6`
- `WINHTTP!WinHttpWebSocketReceive` at `0x18009daea`
- `WINHTTP!WinHttpWebSocketReceive` at `0x18009daea`
- `WINHTTP!WinHttpReadData` at `0x18009dc39`
- `WINHTTP!WinHttpReadData` at `0x18009dc39`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x18009dce8`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x18009dce8`

## string_xrefs

- `0x18009d927`: `IoReadDataAsync`
- `0x18009d9b6`: `IoReadDataAsync`
- `0x18009da5e`: `IoReadDataAsync`
- `0x18009db1e`: `IoReadDataAsync`
- `0x18009dbc3`: `IoReadDataAsync`
- `0x18009dc67`: `IoReadDataAsync`
- `0x18009dd16`: `IoReadDataAsync`
- `0x18009d93d`: `WINHTTP IoReadDataAsync - wrong stream type`
- `0x18009d9de`: `WINHTTP IoReadDataAsync ERROR: read is already pending`
- `0x18009dbaa`: `WinHttpReadData not called because request handle is invalid`
- `0x18009dc8e`: `WinHttpReadData failed`

## pseudocode

```c
__int64 __fastcall CHttpIoRequestWinHttp::IoReadDataAsync(
        CHttpIoRequestWinHttp *this,
        unsigned __int8 *a2,
        DWORD a3,
        int a4)
{
  unsigned int v7; // ebx
  int v8; // r8d
  int v9; // r9d
  void *v10; // rcx
  int *v11; // rdx
  const char **v12; // rax
  signed int v13; // eax
  int v14; // r8d
  int v15; // r9d
  void *v16; // rcx
  DWORD v17; // r8d
  signed int LastError; // eax
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  signed int v22; // eax
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  const char **v27; // [rsp+30h] [rbp-50h]
  const char **v28; // [rsp+40h] [rbp-40h]
  const char **v29; // [rsp+48h] [rbp-38h]
  WINHTTP_WEB_SOCKET_BUFFER_TYPE peBufferType; // [rsp+50h] [rbp-30h] BYREF
  DWORD pdwBytesRead[2]; // [rsp+58h] [rbp-28h] BYREF
  const char *v32; // [rsp+60h] [rbp-20h] BYREF
  const char *v33; // [rsp+68h] [rbp-18h] BYREF
  const char *v34; // [rsp+70h] [rbp-10h] BYREF
  const char *v35; // [rsp+78h] [rbp-8h] BYREF
  int v36; // [rsp+B0h] [rbp+30h] BYREF
  int v37; // [rsp+C8h] [rbp+48h] BYREF

  v7 = -2147418113;
  if ( ((*((_DWORD *)this + 22) - 1) & 0xFFFFFFFD) != 0 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v36 = *((_DWORD *)this + 22);
      *(_QWORD *)pdwBytesRead = "IoReadDataAsync";
      v32 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
      v33 = "WINHTTP IoReadDataAsync - wrong stream type";
      v37 = 1607;
      peBufferType = -2147418113;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        1,
        (unsigned int)&dword_1801B1CC4,
        a3,
        a4,
        (__int64)&v33,
        (__int64)&peBufferType,
        (__int64)&v32,
        (__int64)&v37,
        (__int64)pdwBytesRead,
        (__int64)&v36);
    }
    return v7;
  }
  if ( !_InterlockedExchange((volatile __int32 *)this + 33, 1) )
  {
    CHttpIoRequestWinHttp::MarkIoOriginThread((CHttpIoRequestWinHttp *)((char *)this - 8));
    if ( *((_DWORD *)this + 22) == 3 )
    {
      v10 = (void *)*((_QWORD *)this + 3);
      if ( v10 )
      {
        peBufferType = WINHTTP_WEB_SOCKET_BINARY_MESSAGE_BUFFER_TYPE;
        pdwBytesRead[0] = 0;
        *((_QWORD *)this + 21) = a2;
        v13 = WinHttpWebSocketReceive(v10, a2, a3, pdwBytesRead, &peBufferType);
        v7 = v13;
        if ( v13 > 0 )
          v7 = (unsigned __int16)v13 | 0x80070000;
        if ( (v7 & 0x80000000) != 0 )
        {
          _InterlockedExchange((volatile __int32 *)this + 33, 0);
          if ( (unsigned int)CallbackContext > 2 )
          {
            v36 = 1641;
            v35 = "IoReadDataAsync";
            v37 = v7;
            v34 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
            v33 = "WinHttpWebSocketReceive failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              (_DWORD)CallbackContext,
              (unsigned int)qword_1801B1BF0,
              v14,
              v15,
              (__int64)&v33,
              (__int64)&v37,
              (__int64)&v34,
              (__int64)&v36,
              (__int64)&v35);
          }
        }
        goto LABEL_35;
      }
      v7 = -2147012877;
      if ( (unsigned int)CallbackContext > 2 )
      {
        v36 = 1625;
        v33 = "WinHttpWebSocketReceive not called because websocket handle is invalid";
        v11 = &dword_1801B1C34;
        v32 = "IoReadDataAsync";
        v34 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
        v35 = "Error condition failed";
        v29 = &v33;
        v28 = &v32;
        v27 = &v34;
        v12 = &v35;
LABEL_11:
        v37 = -2147012877;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          -2147012877,
          (_DWORD)v11,
          v8,
          v9,
          (__int64)v12,
          (__int64)&v37,
          (__int64)v27,
          (__int64)&v36,
          (__int64)v28,
          (__int64)v29);
      }
    }
    else
    {
      v16 = (void *)*((_QWORD *)this + 2);
      if ( v16 )
      {
        v17 = *((_DWORD *)this + 35);
        v7 = 0;
        if ( v17 )
        {
          if ( a3 < v17 )
            v17 = a3;
          if ( WinHttpReadData(v16, a2, v17, 0) )
            goto LABEL_35;
          LastError = GetLastError();
          v7 = LastError;
          if ( LastError > 0 )
            v7 = (unsigned __int16)LastError | 0x80070000;
          if ( (unsigned int)CallbackContext > 2 )
          {
            v36 = 1661;
            v35 = "IoReadDataAsync";
            v37 = v7;
            v34 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
            v33 = "WinHttpReadData failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v19,
              (unsigned int)qword_1801B1B60,
              v20,
              v21,
              (__int64)&v33,
              (__int64)&v37,
              (__int64)&v34,
              (__int64)&v36,
              (__int64)&v35);
          }
        }
        else
        {
          *((_QWORD *)this + 21) = a2;
          *((_DWORD *)this + 36) = a3;
          if ( WinHttpQueryDataAvailable(v16, 0) )
            goto LABEL_35;
          v22 = GetLastError();
          v7 = v22;
          if ( v22 > 0 )
            v7 = (unsigned __int16)v22 | 0x80070000;
          if ( (unsigned int)CallbackContext > 2 )
          {
            v36 = 1678;
            v35 = "IoReadDataAsync";
            v37 = v7;
            v34 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
            v33 = "WinHttpQueryDataAvailable failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v23,
              (unsigned int)&dword_1801B1B1C,
              v24,
              v25,
              (__int64)&v33,
              (__int64)&v37,
              (__int64)&v34,
              (__int64)&v36,
              (__int64)&v35);
          }
        }
        _InterlockedExchange((volatile __int32 *)this + 33, 0);
        goto LABEL_35;
      }
      v7 = -2147012877;
      if ( (unsigned int)CallbackContext > 2 )
      {
        v36 = 1648;
        v35 = "WinHttpReadData not called because request handle is invalid";
        v11 = &dword_1801B1BA4;
        v34 = "IoReadDataAsync";
        v33 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
        v32 = "Error condition failed";
        v29 = &v35;
        v28 = &v34;
        v27 = &v33;
        v12 = &v32;
        goto LABEL_11;
      }
    }
LABEL_35:
    CHttpIoRequestWinHttp::ClearIoOriginThreadMarking((CHttpIoRequestWinHttp *)((char *)this - 8));
    return v7;
  }
  if ( (unsigned int)CallbackContext > 2 )
  {
    v36 = 1614;
    v33 = "IoReadDataAsync";
    v32 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
    v37 = -2147418113;
    *(_QWORD *)pdwBytesRead = "WINHTTP IoReadDataAsync ERROR: read is already pending";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (unsigned int)pdwBytesRead,
      (unsigned int)qword_1801B1C80,
      a3,
      a4,
      (__int64)pdwBytesRead,
      (__int64)&v37,
      (__int64)&v32,
      (__int64)&v36,
      (__int64)&v33);
  }
  return v7;
}

```

## disassembly

```asm
0x18009d8d0  mov     r11, rsp
0x18009d8d3  mov     [r11+10h], rbx
0x18009d8d7  push    rbp
0x18009d8d8  push    rsi
0x18009d8d9  push    rdi
0x18009d8da  push    r14
0x18009d8dc  push    r15
0x18009d8de  mov     rbp, rsp
0x18009d8e1  sub     rsp, 80h
0x18009d8e8  mov     eax, [rcx+58h]
0x18009d8eb  mov     rdi, rcx
0x18009d8ee  mov     ecx, 1
0x18009d8f3  mov     r14d, r8d
0x18009d8f6  sub     eax, ecx
0x18009d8f8  mov     rsi, rdx
0x18009d8fb  mov     ebx, 8000FFFFh
0x18009d900  test    eax, 0FFFFFFFDh
0x18009d905  jz      loc_18009D98D
0x18009d90b  mov     eax, cs:CallbackContext
0x18009d911  cmp     eax, 2
0x18009d914  jbe     loc_18009DD8B
0x18009d91a  mov     eax, [rdi+58h]
0x18009d91d  lea     rdx, dword_1801B1CC4
0x18009d924  mov     [rbp+arg_0], eax
0x18009d927  lea     rax, aIoreaddataasyn; "IoReadDataAsync"
0x18009d92e  mov     qword ptr [rbp+pdwBytesRead], rax
0x18009d932  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdp\\win\\httpio\\win"...
0x18009d939  mov     [rbp+var_20], rax
0x18009d93d  lea     rax, aWinhttpIoreadd; "WINHTTP IoReadDataAsync - wrong stream "...
0x18009d944  mov     [rbp+var_18], rax
0x18009d948  lea     rax, [rbp+arg_0]
0x18009d94c  mov     [r11-60h], rax
0x18009d950  lea     rax, [rbp+pdwBytesRead]
0x18009d954  mov     [r11-68h], rax
0x18009d958  lea     rax, [rbp+arg_18]
0x18009d95c  mov     [r11-70h], rax
0x18009d960  lea     rax, [rbp+var_20]
0x18009d964  mov     [r11-78h], rax
0x18009d968  lea     rax, [rbp+var_30]
0x18009d96c  mov     [r11-80h], rax
0x18009d970  lea     rax, [rbp+var_18]
0x18009d974  mov     [rsp+80h+peBufferType], rax
0x18009d979  mov     [rbp+arg_18], 647h
0x18009d980  mov     [rbp+var_30], ebx
0x18009d983  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18009d988  jmp     loc_18009DD8B
0x18009d98d  xchg    ecx, [rdi+84h]
0x18009d993  test    ecx, ecx
0x18009d995  jz      short loc_18009DA0F
0x18009d997  mov     eax, cs:CallbackContext
0x18009d99d  cmp     eax, 2
0x18009d9a0  jbe     loc_18009DD8B
0x18009d9a6  lea     rcx, [rbp+var_18]
0x18009d9aa  mov     [rbp+arg_0], 64Eh
0x18009d9b1  mov     [rsp+80h+var_40], rcx
0x18009d9b6  lea     rax, aIoreaddataasyn; "IoReadDataAsync"
0x18009d9bd  mov     [rbp+var_18], rax
0x18009d9c1  lea     rcx, [rbp+arg_0]
0x18009d9c5  mov     [rsp+80h+var_48], rcx
0x18009d9ca  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdp\\win\\httpio\\win"...
0x18009d9d1  lea     rcx, [rbp+var_20]
0x18009d9d5  mov     [rbp+var_20], rax
0x18009d9d9  mov     [rsp+80h+var_50], rcx
0x18009d9de  lea     rax, aWinhttpIoreadd_0; "WINHTTP IoReadDataAsync ERROR: read is "...
0x18009d9e5  lea     rcx, [rbp+arg_18]
0x18009d9e9  mov     [rbp+arg_18], ebx
0x18009d9ec  mov     [rsp+80h+var_58], rcx
0x18009d9f1  lea     rdx, qword_1801B1C80
0x18009d9f8  lea     rcx, [rbp+pdwBytesRead]
0x18009d9fc  mov     qword ptr [rbp+pdwBytesRead], rax
0x18009da00  mov     [rsp+80h+peBufferType], rcx
0x18009da05  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18009da0a  jmp     loc_18009DD8B
0x18009da0f  lea     rcx, [rdi-8]; this
0x18009da13  call    ?MarkIoOriginThread@CHttpIoRequestWinHttp@@AEAAXXZ; CHttpIoRequestWinHttp::MarkIoOriginThread(void)
0x18009da18  cmp     dword ptr [rdi+58h], 3
0x18009da1c  jnz     loc_18009DB87
0x18009da22  mov     rcx, [rdi+18h]; hWebSocket
0x18009da26  test    rcx, rcx
0x18009da29  jnz     loc_18009DAC2
0x18009da2f  mov     eax, cs:CallbackContext
0x18009da35  mov     ecx, 80072EF3h
0x18009da3a  mov     ebx, ecx
0x18009da3c  cmp     eax, 2
0x18009da3f  jbe     loc_18009DD82
0x18009da45  lea     rax, aWinhttpwebsock_5; "WinHttpWebSocketReceive not called beca"...
0x18009da4c  mov     [rbp+arg_0], 659h
0x18009da53  mov     [rbp+var_18], rax
0x18009da57  lea     rdx, dword_1801B1C34
0x18009da5e  lea     rax, aIoreaddataasyn; "IoReadDataAsync"
0x18009da65  mov     [rbp+var_20], rax
0x18009da69  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdp\\win\\httpio\\win"...
0x18009da70  mov     [rbp+var_10], rax
0x18009da74  lea     rax, aErrorCondition; "Error condition failed"
0x18009da7b  mov     [rbp+var_8], rax
0x18009da7f  lea     rax, [rbp+var_18]
0x18009da83  mov     [rsp+80h+var_38], rax
0x18009da88  lea     rax, [rbp+var_20]
0x18009da8c  mov     [rsp+80h+var_40], rax
0x18009da91  lea     rax, [rbp+arg_0]
0x18009da95  mov     [rsp+80h+var_48], rax
0x18009da9a  lea     rax, [rbp+var_10]
0x18009da9e  mov     [rsp+80h+var_50], rax
0x18009daa3  lea     rax, [rbp+arg_18]
0x18009daa7  mov     [rsp+80h+var_58], rax
0x18009daac  lea     rax, [rbp+var_8]
0x18009dab0  mov     [rsp+80h+peBufferType], rax
0x18009dab5  mov     [rbp+arg_18], ecx
0x18009dab8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18009dabd  jmp     loc_18009DD82
0x18009dac2  lea     rax, [rbp+var_30]
0x18009dac6  mov     [rbp+var_30], 0
0x18009dacd  lea     r9, [rbp+pdwBytesRead]; pdwBytesRead
0x18009dad1  mov     [rsp+80h+peBufferType], rax; peBufferType
0x18009dad6  mov     r8d, r14d; dwBufferLength
0x18009dad9  mov     [rbp+pdwBytesRead], 0
0x18009dae0  mov     rdx, rsi; pvBuffer
0x18009dae3  mov     [rdi+0A8h], rsi
0x18009daea  call    cs:__imp_WinHttpWebSocketReceive
0x18009daf0  mov     ebx, eax
0x18009daf2  test    eax, eax
0x18009daf4  jle     short loc_18009DAFF
0x18009daf6  movzx   ebx, ax
0x18009daf9  or      ebx, 80070000h
0x18009daff  test    ebx, ebx
0x18009db01  jns     loc_18009DD82
0x18009db07  xor     eax, eax
0x18009db09  xchg    eax, [rdi+84h]
0x18009db0f  mov     ecx, cs:CallbackContext
0x18009db15  cmp     ecx, 2
0x18009db18  jbe     loc_18009DD82
0x18009db1e  lea     rax, aIoreaddataasyn; "IoReadDataAsync"
0x18009db25  mov     [rbp+arg_0], 669h
0x18009db2c  mov     [rbp+var_8], rax
0x18009db30  lea     rdx, qword_1801B1BF0
0x18009db37  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdp\\win\\httpio\\win"...
0x18009db3e  mov     [rbp+arg_18], ebx
0x18009db41  mov     [rbp+var_10], rax
0x18009db45  lea     rax, aWinhttpwebsock_8; "WinHttpWebSocketReceive failed"
0x18009db4c  mov     [rbp+var_18], rax
0x18009db50  lea     rax, [rbp+var_8]
0x18009db54  mov     [rsp+80h+var_40], rax
0x18009db59  lea     rax, [rbp+arg_0]
0x18009db5d  mov     [rsp+80h+var_48], rax
0x18009db62  lea     rax, [rbp+var_10]
0x18009db66  mov     [rsp+80h+var_50], rax
0x18009db6b  lea     rax, [rbp+arg_18]
0x18009db6f  mov     [rsp+80h+var_58], rax
0x18009db74  lea     rax, [rbp+var_18]
0x18009db78  mov     [rsp+80h+peBufferType], rax
0x18009db7d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18009db82  jmp     loc_18009DD82
0x18009db87  mov     rcx, [rdi+10h]; hRequest
0x18009db8b  test    rcx, rcx
0x18009db8e  jnz     loc_18009DC1A
0x18009db94  mov     eax, cs:CallbackContext
0x18009db9a  mov     ecx, 80072EF3h
0x18009db9f  mov     ebx, ecx
0x18009dba1  cmp     eax, 2
0x18009dba4  jbe     loc_18009DD82
0x18009dbaa  lea     rax, aWinhttpreaddat_0; "WinHttpReadData not called because requ"...
0x18009dbb1  mov     [rbp+arg_0], 670h
0x18009dbb8  mov     [rbp+var_8], rax
0x18009dbbc  lea     rdx, dword_1801B1BA4
0x18009dbc3  lea     rax, aIoreaddataasyn; "IoReadDataAsync"
0x18009dbca  mov     [rbp+var_10], rax
0x18009dbce  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdp\\win\\httpio\\win"...
0x18009dbd5  mov     [rbp+var_18], rax
0x18009dbd9  lea     rax, aErrorCondition; "Error condition failed"
0x18009dbe0  mov     [rbp+var_20], rax
0x18009dbe4  lea     rax, [rbp+var_8]
0x18009dbe8  mov     [rsp+80h+var_38], rax
0x18009dbed  lea     rax, [rbp+var_10]
0x18009dbf1  mov     [rsp+80h+var_40], rax
0x18009dbf6  lea     rax, [rbp+arg_0]
0x18009dbfa  mov     [rsp+80h+var_48], rax
0x18009dbff  lea     rax, [rbp+var_18]
0x18009dc03  mov     [rsp+80h+var_50], rax
0x18009dc08  lea     rax, [rbp+arg_18]
0x18009dc0c  mov     [rsp+80h+var_58], rax
0x18009dc11  lea     rax, [rbp+var_20]
0x18009dc15  jmp     loc_18009DAB0
0x18009dc1a  mov     r8d, [rdi+8Ch]
0x18009dc21  xor     ebx, ebx
0x18009dc23  test    r8d, r8d
0x18009dc26  jz      loc_18009DCD8
0x18009dc2c  cmp     r14d, r8d
0x18009dc2f  mov     rdx, rsi; lpBuffer
0x18009dc32  cmovb   r8d, r14d; dwNumberOfBytesToRead
0x18009dc36  xor     r9d, r9d; lpdwNumberOfBytesRead
0x18009dc39  call    cs:__imp_WinHttpReadData
0x18009dc3f  test    eax, eax
0x18009dc41  jnz     loc_18009DD82
0x18009dc47  call    cs:__imp_GetLastError
0x18009dc4d  mov     ebx, eax
0x18009dc4f  test    eax, eax
0x18009dc51  jle     short loc_18009DC5C
0x18009dc53  movzx   ebx, ax
0x18009dc56  or      ebx, 80070000h
0x18009dc5c  mov     eax, cs:CallbackContext
0x18009dc62  cmp     eax, 2
0x18009dc65  jbe     short loc_18009DCCB
0x18009dc67  lea     rax, aIoreaddataasyn; "IoReadDataAsync"
0x18009dc6e  mov     [rbp+arg_0], 67Dh
0x18009dc75  mov     [rbp+var_8], rax
0x18009dc79  lea     rdx, qword_1801B1B60
0x18009dc80  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdp\\win\\httpio\\win"...
0x18009dc87  mov     [rbp+arg_18], ebx
0x18009dc8a  mov     [rbp+var_10], rax
0x18009dc8e  lea     rax, aWinhttpreaddat_1; "WinHttpReadData failed"
0x18009dc95  mov     [rbp+var_18], rax
0x18009dc99  lea     rax, [rbp+var_8]
0x18009dc9d  mov     [rsp+80h+var_40], rax
0x18009dca2  lea     rax, [rbp+arg_0]
0x18009dca6  mov     [rsp+80h+var_48], rax
0x18009dcab  lea     rax, [rbp+var_10]
0x18009dcaf  mov     [rsp+80h+var_50], rax
0x18009dcb4  lea     rax, [rbp+arg_18]
0x18009dcb8  mov     [rsp+80h+var_58], rax
0x18009dcbd  lea     rax, [rbp+var_18]
0x18009dcc1  mov     [rsp+80h+peBufferType], rax
0x18009dcc6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18009dccb  xor     eax, eax
0x18009dccd  xchg    eax, [rdi+84h]
0x18009dcd3  jmp     loc_18009DD82
0x18009dcd8  xor     edx, edx; lpdwNumberOfBytesAvailable
0x18009dcda  mov     [rdi+0A8h], rsi
0x18009dce1  mov     [rdi+90h], r14d
0x18009dce8  call    cs:__imp_WinHttpQueryDataAvailable
0x18009dcee  test    eax, eax
0x18009dcf0  jnz     loc_18009DD82
0x18009dcf6  call    cs:__imp_GetLastError
0x18009dcfc  mov     ebx, eax
0x18009dcfe  test    eax, eax
0x18009dd00  jle     short loc_18009DD0B
0x18009dd02  movzx   ebx, ax
0x18009dd05  or      ebx, 80070000h
0x18009dd0b  mov     eax, cs:CallbackContext
0x18009dd11  cmp     eax, 2
0x18009dd14  jbe     short loc_18009DD7A
0x18009dd16  lea     rax, aIoreaddataasyn; "IoReadDataAsync"
0x18009dd1d  mov     [rbp+arg_0], 68Eh
0x18009dd24  mov     [rbp+var_8], rax
0x18009dd28  lea     rdx, dword_1801B1B1C
0x18009dd2f  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdp\\win\\httpio\\win"...
0x18009dd36  mov     [rbp+arg_18], ebx
0x18009dd39  mov     [rbp+var_10], rax
0x18009dd3d  lea     rax, aWinhttpqueryda_0; "WinHttpQueryDataAvailable failed"
0x18009dd44  mov     [rbp+var_18], rax
0x18009dd48  lea     rax, [rbp+var_8]
0x18009dd4c  mov     [rsp+80h+var_40], rax
0x18009dd51  lea     rax, [rbp+arg_0]
0x18009dd55  mov     [rsp+80h+var_48], rax
0x18009dd5a  lea     rax, [rbp+var_10]
0x18009dd5e  mov     [rsp+80h+var_50], rax
0x18009dd63  lea     rax, [rbp+arg_18]
0x18009dd67  mov     [rsp+80h+var_58], rax
0x18009dd6c  lea     rax, [rbp+var_18]
0x18009dd70  mov     [rsp+80h+peBufferType], rax
0x18009dd75  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18009dd7a  xor     edx, edx
0x18009dd7c  xchg    edx, [rdi+84h]
0x18009dd82  lea     rcx, [rdi-8]; this
0x18009dd86  call    ?ClearIoOriginThreadMarking@CHttpIoRequestWinHttp@@AEAAXXZ; CHttpIoRequestWinHttp::ClearIoOriginThreadMarking(void)
0x18009dd8b  mov     eax, ebx
0x18009dd8d  mov     rbx, [rsp+80h+arg_8]
0x18009dd95  add     rsp, 80h
0x18009dd9c  pop     r15
0x18009dd9e  pop     r14
0x18009dda0  pop     rdi
0x18009dda1  pop     rsi
0x18009dda2  pop     rbp
0x18009dda3  retn
```
