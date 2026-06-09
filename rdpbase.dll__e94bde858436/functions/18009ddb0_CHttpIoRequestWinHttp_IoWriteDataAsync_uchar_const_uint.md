# CHttpIoRequestWinHttp::IoWriteDataAsync(uchar const *,uint)

- ea: `0x18009ddb0`
- end: `0x18009e32d`
- name: `?IoWriteDataAsync@CHttpIoRequestWinHttp@@UEAAJPEBEI@Z`
- size: `1405`
- prototype: `int(CHttpIoRequestWinHttp *__hidden this, const unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x1800018a4`
- `0x180001aa0`
- `0x180003e7c`
- `0x180004970`
- `0x180078c20`
- `0x180079572`
- `0x180079624`
- `0x18009a1b0`
- `0x18009ddb0`
- `0x18009e350`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e1ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e1ca`
- `WINHTTP!WinHttpWebSocketSend` at `0x18009dfe8`
- `WINHTTP!WinHttpWebSocketSend` at `0x18009dfe8`
- `WINHTTP!WinHttpWriteData` at `0x18009e1bc`
- `WINHTTP!WinHttpWriteData` at `0x18009e1bc`

## string_xrefs

- `0x18009de18`: `IoWriteDataAsync`
- `0x18009dead`: `IoWriteDataAsync`
- `0x18009df7c`: `IoWriteDataAsync`
- `0x18009e01b`: `IoWriteDataAsync`
- `0x18009e0f8`: `IoWriteDataAsync`
- `0x18009e1ea`: `IoWriteDataAsync`
- `0x18009e27a`: `IoWriteDataAsync`
- `0x18009de2e`: `WINHTTP IoWriteDataAsync - wrong stream type`
- `0x18009ded5`: `WINHTTP IoWriteDataAsync - write is already pending`
- `0x18009e2a2`: `Invalid size of the write buffer`
- `0x18009e0a6`: `WinHttpWriteData not called because request handle is invalid`
- `0x18009e211`: `WinHttpWriteData failed`

## pseudocode

```c
__int64 __fastcall CHttpIoRequestWinHttp::IoWriteDataAsync(
        CHttpIoRequestWinHttp *this,
        unsigned __int8 *a2,
        unsigned int a3,
        int a4)
{
  rsize_t v5; // r14
  unsigned int v7; // edi
  int v8; // r8d
  int v9; // r9d
  bool v10; // zf
  void *v11; // rcx
  char *v12; // rax
  int *v13; // rdx
  signed int v14; // eax
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  __int64 *v18; // rdx
  const char *v19; // rax
  __int64 i; // rbx
  __int64 v21; // rbx
  void *v22; // rcx
  __int64 v23; // r8
  void *v24; // rcx
  __int64 v25; // r8
  const void *v26; // rdx
  signed int LastError; // eax
  int v28; // ecx
  int v29; // r8d
  int v30; // r9d
  int v32; // [rsp+60h] [rbp-29h] BYREF
  int v33; // [rsp+64h] [rbp-25h] BYREF
  HINTERNET hRequest; // [rsp+68h] [rbp-21h] BYREF
  const char *v35; // [rsp+70h] [rbp-19h] BYREF
  const char *v36; // [rsp+78h] [rbp-11h] BYREF
  const char *v37; // [rsp+80h] [rbp-9h] BYREF
  const char *v38; // [rsp+88h] [rbp-1h] BYREF
  char Buffer[16]; // [rsp+90h] [rbp+7h] BYREF

  v5 = a3;
  v7 = -2147418113;
  if ( (unsigned int)(*((_DWORD *)this + 22) - 2) > 1 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v37) = *((_DWORD *)this + 22);
      v36 = "IoWriteDataAsync";
      v35 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
      hRequest = "WINHTTP IoWriteDataAsync - wrong stream type";
      v32 = 1478;
      v33 = -2147418113;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        1,
        (unsigned int)byte_1801B1F15,
        a3,
        a4,
        (__int64)&hRequest,
        (__int64)&v33,
        (__int64)&v35,
        (__int64)&v32,
        (__int64)&v36,
        (__int64)&v37);
    }
    return v7;
  }
  if ( _InterlockedExchange((volatile __int32 *)this + 34, 1) )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v33 = 1485;
      hRequest = "IoWriteDataAsync";
      v36 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
      v32 = -2147418113;
      v35 = "WINHTTP IoWriteDataAsync - write is already pending";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (unsigned int)&v35,
        (unsigned int)byte_1801B1ED1,
        a3,
        a4,
        (__int64)&v35,
        (__int64)&v32,
        (__int64)&v36,
        (__int64)&v33,
        (__int64)&hRequest);
    }
    return v7;
  }
  if ( a3 && (*((_DWORD *)this + 22) != 2 || a3 + 10 <= 0x10000) )
  {
    CHttpIoRequestWinHttp::MarkIoOriginThread((CHttpIoRequestWinHttp *)((char *)this - 8));
    v10 = *((_DWORD *)this + 22) == 3;
    *((_QWORD *)this + 22) = a2;
    if ( v10 )
    {
      v11 = (void *)*((_QWORD *)this + 3);
      if ( !v11 )
      {
        v7 = -2147012877;
        if ( (unsigned int)CallbackContext > 2 )
        {
          v12 = "WinHttpWebSocketSend not called because websocket handle is invalid";
          v33 = 1508;
          v13 = &dword_1801B1E2C;
LABEL_14:
          hRequest = v12;
          v36 = "IoWriteDataAsync";
          v35 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
          v37 = "Error condition failed";
          v32 = -2147012877;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            -2147012877,
            (_DWORD)v13,
            v8,
            v9,
            (__int64)&v37,
            (__int64)&v32,
            (__int64)&v35,
            (__int64)&v33,
            (__int64)&v36,
            (__int64)&hRequest);
          goto LABEL_35;
        }
        goto LABEL_35;
      }
      v14 = WinHttpWebSocketSend(v11, WINHTTP_WEB_SOCKET_BINARY_MESSAGE_BUFFER_TYPE, a2, v5);
      v7 = v14;
      if ( v14 > 0 )
        v7 = (unsigned __int16)v14 | 0x80070000;
      if ( (v7 & 0x80000000) == 0 )
        goto LABEL_35;
      _InterlockedExchange((volatile __int32 *)this + 34, 0);
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_35;
      v33 = 1519;
      hRequest = "IoWriteDataAsync";
      v18 = qword_1801B1DE8;
      v36 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
      v19 = "WinHttpWebSocketSend failed";
    }
    else
    {
      hRequest = (HINTERNET)*((_QWORD *)this + 2);
      if ( !hRequest )
      {
        v7 = -2147012877;
        if ( (unsigned int)CallbackContext <= 2 )
          goto LABEL_35;
        v12 = "WinHttpWriteData not called because request handle is invalid";
        v33 = 1534;
        v13 = &dword_1801B1D9C;
        goto LABEL_14;
      }
      *((_QWORD *)this + 24) = 0;
      if ( !itoa_s(v5, Buffer, 0xAu, 16) )
      {
        v7 = 0;
        for ( i = 0; Buffer[i]; i = (unsigned int)(i + 1) )
          *(_BYTE *)(i + *((_QWORD *)this + 23)) = Buffer[i];
        *(_BYTE *)(i + *((_QWORD *)this + 23)) = 13;
        v21 = (unsigned int)(i + 1);
        *(_BYTE *)(v21 + *((_QWORD *)this + 23)) = 10;
        LODWORD(v21) = v21 + 1;
        v22 = (void *)(*((_QWORD *)this + 23) + (unsigned int)v21);
        *((_DWORD *)this + 48) = v21 + 2;
        memcpy_s(v22, (unsigned int)(0x10000 - v21), a2, v5);
        v23 = (unsigned int)(v21 + v5);
        v24 = hRequest;
        *(_BYTE *)(v23 + *((_QWORD *)this + 23)) = 13;
        v25 = (unsigned int)(v23 + 1);
        *(_BYTE *)(v25 + *((_QWORD *)this + 23)) = 10;
        LODWORD(v25) = v25 + 1;
        v26 = (const void *)*((_QWORD *)this + 23);
        *((_DWORD *)this + 50) = v25;
        if ( !WinHttpWriteData(v24, v26, v25, 0) )
        {
          LastError = GetLastError();
          v7 = LastError;
          if ( LastError > 0 )
            v7 = (unsigned __int16)LastError | 0x80070000;
          if ( (unsigned int)CallbackContext > 2 )
          {
            v33 = 1576;
            hRequest = "IoWriteDataAsync";
            v32 = v7;
            v36 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
            v35 = "WinHttpWriteData failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v28,
              (unsigned int)&dword_1801B1D14,
              v29,
              v30,
              (__int64)&v35,
              (__int64)&v32,
              (__int64)&v36,
              (__int64)&v33,
              (__int64)&hRequest);
          }
          _InterlockedExchange((volatile __int32 *)this + 34, 0);
        }
        goto LABEL_35;
      }
      v7 = -2147467259;
      if ( (unsigned int)CallbackContext <= 2 )
      {
LABEL_35:
        CHttpIoRequestWinHttp::ClearIoOriginThreadMarking((CHttpIoRequestWinHttp *)((char *)this - 8));
        return v7;
      }
      v33 = 1543;
      hRequest = "IoWriteDataAsync";
      v18 = qword_1801B1D58;
      v36 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
      v19 = "_itoa_s failed";
    }
    v35 = v19;
    v32 = v7;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v15,
      (_DWORD)v18,
      v16,
      v17,
      (__int64)&v35,
      (__int64)&v32,
      (__int64)&v36,
      (__int64)&v33,
      (__int64)&hRequest);
    goto LABEL_35;
  }
  v7 = -2147024809;
  if ( (unsigned int)CallbackContext > 2 )
  {
    v32 = 1;
    hRequest = "IoWriteDataAsync";
    v33 = 65526;
    v38 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
    LODWORD(v37) = a3;
    *(_QWORD *)Buffer = "Invalid size of the write buffer";
    LODWORD(v35) = 1495;
    LODWORD(v36) = -2147024809;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (unsigned int)Buffer,
      (unsigned int)qword_1801B1E78,
      a3,
      a4,
      (__int64)Buffer,
      (__int64)&v36,
      (__int64)&v38,
      (__int64)&v35,
      (__int64)&hRequest,
      (__int64)&v37,
      (__int64)&v32,
      (__int64)&v33);
  }
  return v7;
}

```

## disassembly

```asm
0x18009ddb0  mov     [rsp-8+arg_18], rbx
0x18009ddb5  push    rbp
0x18009ddb6  push    rsi
0x18009ddb7  push    rdi
0x18009ddb8  push    r12
0x18009ddba  push    r13
0x18009ddbc  push    r14
0x18009ddbe  push    r15
0x18009ddc0  lea     rbp, [rsp-27h]
0x18009ddc5  sub     rsp, 0B0h
0x18009ddcc  mov     rax, cs:__security_cookie
0x18009ddd3  xor     rax, rsp
0x18009ddd6  mov     [rbp+57h+var_40], rax
0x18009ddda  mov     eax, [rcx+58h]
0x18009dddd  mov     ebx, 2
0x18009dde2  mov     rsi, rcx
0x18009dde5  mov     r14d, r8d
0x18009dde8  sub     eax, ebx
0x18009ddea  mov     r12, rdx
0x18009dded  mov     edi, 8000FFFFh
0x18009ddf2  lea     ecx, [rbx-1]
0x18009ddf5  cmp     eax, ecx
0x18009ddf7  jbe     loc_18009DE83
0x18009ddfd  mov     eax, cs:CallbackContext
0x18009de03  cmp     eax, ebx
0x18009de05  jbe     loc_18009E304
0x18009de0b  mov     eax, [rsi+58h]
0x18009de0e  lea     rdx, byte_1801B1F15
0x18009de15  mov     dword ptr [rbp+57h+var_60], eax
0x18009de18  lea     rax, aIowritedataasy; "IoWriteDataAsync"
0x18009de1f  mov     [rbp+57h+var_68], rax
0x18009de23  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdp\\win\\httpio\\win"...
0x18009de2a  mov     [rbp+57h+var_70], rax
0x18009de2e  lea     rax, aWinhttpIowrite_0; "WINHTTP IoWriteDataAsync - wrong stream"...
0x18009de35  mov     [rbp+57h+hRequest], rax
0x18009de39  lea     rax, [rbp+57h+var_60]
0x18009de3d  mov     [rsp+0E0h+var_98], rax
0x18009de42  lea     rax, [rbp+57h+var_68]
0x18009de46  mov     [rsp+0E0h+var_A0], rax
0x18009de4b  lea     rax, [rbp+57h+var_80]
0x18009de4f  mov     [rsp+0E0h+var_A8], rax
0x18009de54  lea     rax, [rbp+57h+var_70]
0x18009de58  mov     [rsp+0E0h+var_B0], rax
0x18009de5d  lea     rax, [rbp+57h+var_7C]
0x18009de61  mov     [rsp+0E0h+var_B8], rax
0x18009de66  lea     rax, [rbp+57h+hRequest]
0x18009de6a  mov     [rsp+0E0h+var_C0], rax
0x18009de6f  mov     [rbp+57h+var_80], 5C6h
0x18009de76  mov     [rbp+57h+var_7C], edi
0x18009de79  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18009de7e  jmp     loc_18009E304
0x18009de83  mov     eax, ecx
0x18009de85  xchg    eax, [rsi+88h]
0x18009de8b  test    eax, eax
0x18009de8d  jz      short loc_18009DF06
0x18009de8f  mov     eax, cs:CallbackContext
0x18009de95  cmp     eax, ebx
0x18009de97  jbe     loc_18009E304
0x18009de9d  lea     rcx, [rbp+57h+hRequest]
0x18009dea1  mov     [rbp+57h+var_7C], 5CDh
0x18009dea8  mov     [rsp+0E0h+var_A0], rcx
0x18009dead  lea     rax, aIowritedataasy; "IoWriteDataAsync"
0x18009deb4  mov     [rbp+57h+hRequest], rax
0x18009deb8  lea     rcx, [rbp+57h+var_7C]
0x18009debc  mov     [rsp+0E0h+var_A8], rcx
0x18009dec1  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdp\\win\\httpio\\win"...
0x18009dec8  lea     rcx, [rbp+57h+var_68]
0x18009decc  mov     [rbp+57h+var_68], rax
0x18009ded0  mov     [rsp+0E0h+var_B0], rcx
0x18009ded5  lea     rax, aWinhttpIowrite; "WINHTTP IoWriteDataAsync - write is alr"...
0x18009dedc  lea     rcx, [rbp+57h+var_80]
0x18009dee0  mov     [rbp+57h+var_80], edi
0x18009dee3  mov     [rsp+0E0h+var_B8], rcx
0x18009dee8  lea     rdx, byte_1801B1ED1
0x18009deef  lea     rcx, [rbp+57h+var_70]
0x18009def3  mov     [rbp+57h+var_70], rax
0x18009def7  mov     [rsp+0E0h+var_C0], rcx
0x18009defc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18009df01  jmp     loc_18009E304
0x18009df06  test    r8d, r8d
0x18009df09  jz      loc_18009E264
0x18009df0f  mov     r13d, 10000h
0x18009df15  cmp     [rsi+58h], ebx
0x18009df18  jnz     short loc_18009DF27
0x18009df1a  lea     eax, [r14+0Ah]
0x18009df1e  cmp     eax, r13d
0x18009df21  ja      loc_18009E264
0x18009df27  lea     rcx, [rsi-8]; this
0x18009df2b  call    ?MarkIoOriginThread@CHttpIoRequestWinHttp@@AEAAXXZ; CHttpIoRequestWinHttp::MarkIoOriginThread(void)
0x18009df30  cmp     dword ptr [rsi+58h], 3
0x18009df34  mov     [rsi+0B0h], r12
0x18009df3b  jnz     loc_18009E084
0x18009df41  mov     rcx, [rsi+18h]; hWebSocket
0x18009df45  test    rcx, rcx
0x18009df48  jnz     loc_18009DFE0
0x18009df4e  mov     eax, cs:CallbackContext
0x18009df54  mov     ecx, 80072EF3h
0x18009df59  mov     edi, ecx
0x18009df5b  cmp     eax, ebx
0x18009df5d  jbe     loc_18009E256
0x18009df63  lea     rax, aWinhttpwebsock_7; "WinHttpWebSocketSend not called because"...
0x18009df6a  mov     [rbp+57h+var_7C], 5E4h
0x18009df71  lea     rdx, dword_1801B1E2C
0x18009df78  mov     [rbp+57h+hRequest], rax
0x18009df7c  lea     rax, aIowritedataasy; "IoWriteDataAsync"
0x18009df83  mov     [rbp+57h+var_68], rax
0x18009df87  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdp\\win\\httpio\\win"...
0x18009df8e  mov     [rbp+57h+var_70], rax
0x18009df92  lea     rax, aErrorCondition; "Error condition failed"
0x18009df99  mov     [rbp+57h+var_60], rax
0x18009df9d  lea     rax, [rbp+57h+hRequest]
0x18009dfa1  mov     [rsp+0E0h+var_98], rax
0x18009dfa6  lea     rax, [rbp+57h+var_68]
0x18009dfaa  mov     [rsp+0E0h+var_A0], rax
0x18009dfaf  lea     rax, [rbp+57h+var_7C]
0x18009dfb3  mov     [rsp+0E0h+var_A8], rax
0x18009dfb8  lea     rax, [rbp+57h+var_70]
0x18009dfbc  mov     [rsp+0E0h+var_B0], rax
0x18009dfc1  lea     rax, [rbp+57h+var_80]
0x18009dfc5  mov     [rsp+0E0h+var_B8], rax
0x18009dfca  lea     rax, [rbp+57h+var_60]
0x18009dfce  mov     [rsp+0E0h+var_C0], rax
0x18009dfd3  mov     [rbp+57h+var_80], ecx
0x18009dfd6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18009dfdb  jmp     loc_18009E256
0x18009dfe0  mov     r9d, r14d; dwBufferLength
0x18009dfe3  mov     r8, r12; pvBuffer
0x18009dfe6  xor     edx, edx; eBufferType
0x18009dfe8  call    cs:__imp_WinHttpWebSocketSend
0x18009dfee  mov     edi, eax
0x18009dff0  test    eax, eax
0x18009dff2  jle     short loc_18009DFFD
0x18009dff4  movzx   edi, ax
0x18009dff7  or      edi, 80070000h
0x18009dffd  test    edi, edi
0x18009dfff  jns     loc_18009E256
0x18009e005  xor     eax, eax
0x18009e007  xchg    eax, [rsi+88h]
0x18009e00d  mov     eax, cs:CallbackContext
0x18009e013  cmp     eax, ebx
0x18009e015  jbe     loc_18009E256
0x18009e01b  lea     rax, aIowritedataasy; "IoWriteDataAsync"
0x18009e022  mov     [rbp+57h+var_7C], 5EFh
0x18009e029  mov     [rbp+57h+hRequest], rax
0x18009e02d  lea     rdx, qword_1801B1DE8
0x18009e034  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdp\\win\\httpio\\win"...
0x18009e03b  mov     [rbp+57h+var_68], rax
0x18009e03f  lea     rax, aWinhttpwebsock_4; "WinHttpWebSocketSend failed"
0x18009e046  mov     [rbp+57h+var_70], rax
0x18009e04a  lea     rax, [rbp+57h+hRequest]
0x18009e04e  mov     [rsp+0E0h+var_A0], rax
0x18009e053  lea     rax, [rbp+57h+var_7C]
0x18009e057  mov     [rsp+0E0h+var_A8], rax
0x18009e05c  lea     rax, [rbp+57h+var_68]
0x18009e060  mov     [rsp+0E0h+var_B0], rax
0x18009e065  lea     rax, [rbp+57h+var_80]
0x18009e069  mov     [rsp+0E0h+var_B8], rax
0x18009e06e  lea     rax, [rbp+57h+var_70]
0x18009e072  mov     [rsp+0E0h+var_C0], rax
0x18009e077  mov     [rbp+57h+var_80], edi
0x18009e07a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18009e07f  jmp     loc_18009E256
0x18009e084  mov     rax, [rsi+10h]
0x18009e088  mov     [rbp+57h+hRequest], rax
0x18009e08c  test    rax, rax
0x18009e08f  jnz     short loc_18009E0C0
0x18009e091  mov     eax, cs:CallbackContext
0x18009e097  mov     ecx, 80072EF3h
0x18009e09c  mov     edi, ecx
0x18009e09e  cmp     eax, ebx
0x18009e0a0  jbe     loc_18009E256
0x18009e0a6  lea     rax, aWinhttpwriteda_0; "WinHttpWriteData not called because req"...
0x18009e0ad  mov     [rbp+57h+var_7C], 5FEh
0x18009e0b4  lea     rdx, dword_1801B1D9C
0x18009e0bb  jmp     loc_18009DF78
0x18009e0c0  mov     r9d, 10h; Radix
0x18009e0c6  mov     qword ptr [rsi+0C0h], 0
0x18009e0d1  lea     rdx, [rbp+57h+Buffer]; Buffer
0x18009e0d5  mov     ecx, r14d; Value
0x18009e0d8  lea     r8d, [r9-6]; BufferCount
0x18009e0dc  call    _itoa_s
0x18009e0e1  test    eax, eax
0x18009e0e3  jz      short loc_18009E128
0x18009e0e5  mov     eax, cs:CallbackContext
0x18009e0eb  mov     edi, 80004005h
0x18009e0f0  cmp     eax, ebx
0x18009e0f2  jbe     loc_18009E256
0x18009e0f8  lea     rax, aIowritedataasy; "IoWriteDataAsync"
0x18009e0ff  mov     [rbp+57h+var_7C], 607h
0x18009e106  mov     [rbp+57h+hRequest], rax
0x18009e10a  lea     rdx, qword_1801B1D58
0x18009e111  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdp\\win\\httpio\\win"...
0x18009e118  mov     [rbp+57h+var_68], rax
0x18009e11c  lea     rax, aItoaSFailed; "_itoa_s failed"
0x18009e123  jmp     loc_18009E046
0x18009e128  xor     edi, edi
0x18009e12a  xor     ebx, ebx
0x18009e12c  cmp     [rbp+57h+Buffer], bl
0x18009e12f  jz      short loc_18009E148
0x18009e131  mov     al, [rbp+rbx+57h+Buffer]
0x18009e135  mov     rcx, [rsi+0B8h]
0x18009e13c  mov     [rbx+rcx], al
0x18009e13f  inc     ebx
0x18009e141  cmp     [rbp+rbx+57h+Buffer], dil
0x18009e146  jnz     short loc_18009E131
0x18009e148  mov     rax, [rsi+0B8h]
0x18009e14f  mov     r9, r14; SourceSize
0x18009e152  mov     r8, r12; Source
0x18009e155  mov     byte ptr [rbx+rax], 0Dh
0x18009e159  inc     ebx
0x18009e15b  mov     rax, [rsi+0B8h]
0x18009e162  mov     byte ptr [rbx+rax], 0Ah
0x18009e166  inc     ebx
0x18009e168  sub     r13d, ebx
0x18009e16b  mov     ecx, ebx
0x18009e16d  add     rcx, [rsi+0B8h]; Destination
0x18009e174  mov     edx, r13d; DestinationSize
0x18009e177  lea     eax, [rbx+2]
0x18009e17a  mov     [rsi+0C0h], eax
0x18009e180  call    memcpy_s
0x18009e185  mov     rax, [rsi+0B8h]
0x18009e18c  lea     r8d, [rbx+r14]
0x18009e190  mov     rcx, [rbp+57h+hRequest]; hRequest
0x18009e194  xor     r9d, r9d; lpdwNumberOfBytesWritten
0x18009e197  mov     byte ptr [r8+rax], 0Dh
0x18009e19c  inc     r8d
0x18009e19f  mov     rax, [rsi+0B8h]
0x18009e1a6  mov     byte ptr [r8+rax], 0Ah
0x18009e1ab  inc     r8d; dwNumberOfBytesToWrite
0x18009e1ae  mov     rdx, [rsi+0B8h]; lpBuffer
0x18009e1b5  mov     [rsi+0C8h], r8d
0x18009e1bc  call    cs:__imp_WinHttpWriteData
0x18009e1c2  test    eax, eax
0x18009e1c4  jnz     loc_18009E256
0x18009e1ca  call    cs:__imp_GetLastError
0x18009e1d0  mov     edi, eax
0x18009e1d2  test    eax, eax
0x18009e1d4  jle     short loc_18009E1DF
0x18009e1d6  movzx   edi, ax
0x18009e1d9  or      edi, 80070000h
0x18009e1df  mov     eax, cs:CallbackContext
0x18009e1e5  cmp     eax, 2
0x18009e1e8  jbe     short loc_18009E24E
0x18009e1ea  lea     rax, aIowritedataasy; "IoWriteDataAsync"
0x18009e1f1  mov     [rbp+57h+var_7C], 628h
0x18009e1f8  mov     [rbp+57h+hRequest], rax
0x18009e1fc  lea     rdx, dword_1801B1D14
0x18009e203  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdp\\win\\httpio\\win"...
0x18009e20a  mov     [rbp+57h+var_80], edi
0x18009e20d  mov     [rbp+57h+var_68], rax
0x18009e211  lea     rax, aWinhttpwriteda_1; "WinHttpWriteData failed"
0x18009e218  mov     [rbp+57h+var_70], rax
0x18009e21c  lea     rax, [rbp+57h+hRequest]
0x18009e220  mov     [rsp+0E0h+var_A0], rax
0x18009e225  lea     rax, [rbp+57h+var_7C]
0x18009e229  mov     [rsp+0E0h+var_A8], rax
0x18009e22e  lea     rax, [rbp+57h+var_68]
0x18009e232  mov     [rsp+0E0h+var_B0], rax
0x18009e237  lea     rax, [rbp+57h+var_80]
0x18009e23b  mov     [rsp+0E0h+var_B8], rax
0x18009e240  lea     rax, [rbp+57h+var_70]
0x18009e244  mov     [rsp+0E0h+var_C0], rax
0x18009e249  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18009e24e  xor     edx, edx
0x18009e250  xchg    edx, [rsi+88h]
0x18009e256  lea     rcx, [rsi-8]; this
0x18009e25a  call    ?ClearIoOriginThreadMarking@CHttpIoRequestWinHttp@@AEAAXXZ; CHttpIoRequestWinHttp::ClearIoOriginThreadMarking(void)
0x18009e25f  jmp     loc_18009E304
0x18009e264  mov     eax, cs:CallbackContext
0x18009e26a  mov     edi, 80070057h
0x18009e26f  cmp     eax, ebx
0x18009e271  jbe     loc_18009E304
0x18009e277  mov     [rbp+57h+var_80], ecx
0x18009e27a  lea     rax, aIowritedataasy; "IoWriteDataAsync"
0x18009e281  mov     [rbp+57h+hRequest], rax
0x18009e285  lea     rcx, [rbp+57h+hRequest]
0x18009e289  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdp\\win\\httpio\\win"...
0x18009e290  mov     [rbp+57h+var_7C], 0FFF6h
0x18009e297  mov     [rbp+57h+var_58], rax
0x18009e29b  lea     rdx, qword_1801B1E78
0x18009e2a2  lea     rax, aInvalidSizeOfT; "Invalid size of the write buffer"
0x18009e2a9  mov     dword ptr [rbp+57h+var_60], r14d
0x18009e2ad  mov     qword ptr [rbp+57h+Buffer], rax
0x18009e2b1  lea     rax, [rbp+57h+var_7C]
0x18009e2b5  mov     [rsp+0E0h+var_88], rax
0x18009e2ba  lea     rax, [rbp+57h+var_80]
0x18009e2be  mov     [rsp+0E0h+var_90], rax
0x18009e2c3  lea     rax, [rbp+57h+var_60]
0x18009e2c7  mov     [rsp+0E0h+var_98], rax
0x18009e2cc  mov     [rsp+0E0h+var_A0], rcx
0x18009e2d1  lea     rcx, [rbp+57h+var_70]
0x18009e2d5  mov     [rsp+0E0h+var_A8], rcx
0x18009e2da  lea     rcx, [rbp+57h+var_58]
0x18009e2de  mov     [rsp+0E0h+var_B0], rcx
0x18009e2e3  lea     rcx, [rbp+57h+var_68]
0x18009e2e7  mov     [rsp+0E0h+var_B8], rcx
0x18009e2ec  lea     rcx, [rbp+57h+Buffer]
0x18009e2f0  mov     [rsp+0E0h+var_C0], rcx
0x18009e2f5  mov     dword ptr [rbp+57h+var_70], 5D7h
0x18009e2fc  mov     dword ptr [rbp+57h+var_68], edi
  ... truncated ...
```
