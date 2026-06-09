# CHttpIoRequestWinHttp::SendStreamModeRequestAsync(bool,bool)

- ea: `0x18009e690`
- end: `0x18009ea49`
- name: `?SendStreamModeRequestAsync@CHttpIoRequestWinHttp@@UEAAJ_N0@Z`
- size: `953`
- prototype: `__int64 __fastcall(CHttpIoRequestWinHttp *__hidden this, bool, bool)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting`

## callees

- `0x1800018a4`
- `0x180001aa0`
- `0x180002550`
- `0x18004c01c`
- `0x1800787d4`
- `0x180088810`
- `0x18009a1b0`
- `0x18009e350`
- `0x18009e690`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009e705`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009e705`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18009e74b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18009e74b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e77d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e78e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e839`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e9a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e77d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e78e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e839`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e9a2`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18009e6e9`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18009e6e9`
- `WINHTTP!WinHttpSetOption` at `0x18009e76f`
- `WINHTTP!WinHttpSetOption` at `0x18009e76f`
- `WINHTTP!WinHttpSendRequest` at `0x18009e98a`
- `WINHTTP!WinHttpSendRequest` at `0x18009e98a`

## string_xrefs

- `0x18009e6e2`: `WinHttp.dll`
- `0x18009e855`: `LoadLibrary for WinHttp.dll failed`

## pseudocode

```c
__int64 __fastcall CHttpIoRequestWinHttp::SendStreamModeRequestAsync(CHttpIoRequestWinHttp *this, char a2, char a3)
{
  unsigned __int16 v6; // cx
  unsigned __int16 v7; // r8
  HMODULE LibraryW; // rax
  HMODULE v9; // rbx
  int v10; // r9d
  signed int v11; // eax
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  unsigned int v15; // edi
  char *v16; // rdx
  GUID *v17; // rax
  signed int v18; // eax
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  const char *v22; // rax
  void *v23; // rax
  const char *v24; // rax
  BOOL v25; // ebx
  signed int LastError; // eax
  const char **dwContext; // [rsp+30h] [rbp-40h]
  GUID *p_ActivityId; // [rsp+40h] [rbp-30h]
  const char *v30; // [rsp+50h] [rbp-20h] BYREF
  const char *v31; // [rsp+58h] [rbp-18h] BYREF
  GUID ActivityId; // [rsp+60h] [rbp-10h] BYREF
  const char *v33; // [rsp+A0h] [rbp+30h] BYREF
  int v34; // [rsp+A8h] [rbp+38h] BYREF
  const char *v35; // [rsp+B8h] [rbp+48h] BYREF

  *(struct _GUID *)((char *)this + 120) = *RdpActivityId::GetCurrentActivityId(&ActivityId);
  if ( !a2 )
    goto LABEL_19;
  if ( IsWindowsVersionOrGreater(v6, 2u, v7) )
    goto LABEL_9;
  LibraryW = LoadLibraryW(L"WinHttp.dll");
  v9 = LibraryW;
  if ( LibraryW )
  {
    if ( !GetProcAddress(LibraryW, "WinHttpWebSocketSend") )
    {
      if ( (unsigned int)CallbackContext > 4 )
      {
        v33 = "SendStreamModeRequestAsync - WebSockets not supported on this platform";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (unsigned int)&CallbackContext,
          (unsigned int)byte_1801B2125,
          0,
          v10,
          (__int64)&v33);
      }
      a2 = 0;
    }
    FreeLibrary(v9);
    if ( a2 )
      goto LABEL_9;
LABEL_19:
    v15 = 0;
    if ( a3 )
    {
      v15 = (*(__int64 (__fastcall **)(CHttpIoRequestWinHttp *, const wchar_t *, const wchar_t *, __int64))(*(_QWORD *)this + 24LL))(
              this,
              L"transfer-encoding",
              L"chunked",
              1);
      if ( (v15 & 0x80000000) != 0 )
      {
        v12 = (int)CallbackContext;
        if ( (unsigned int)CallbackContext <= 2 )
          return v15;
        v34 = 1347;
        v35 = "AddRequestHeaders transfer-encoding: chunked failed";
        v16 = byte_1801B2049;
        v31 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
        v22 = "Error HResult failed";
LABEL_34:
        v30 = v22;
        p_ActivityId = &ActivityId;
        dwContext = &v31;
        v17 = (GUID *)&v30;
        *(_QWORD *)&ActivityId.Data1 = "SendStreamModeRequestAsync";
        goto LABEL_35;
      }
      if ( !*((_QWORD *)this + 24) )
      {
        v23 = operator new(0x10000u);
        *((_QWORD *)this + 24) = v23;
        if ( !v23 )
        {
          v15 = -2147024882;
          if ( (unsigned int)CallbackContext <= 2 )
            return v15;
          v24 = "Allocating buffer for chunk transfer encoding failed";
          v34 = 1353;
          v16 = byte_1801B1FFD;
LABEL_33:
          v35 = v24;
          v31 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
          v22 = "Error condition failed";
          goto LABEL_34;
        }
      }
      *((_DWORD *)this + 24) = 2;
    }
    CHttpIoRequestWinHttp::MarkIoOriginThread(this);
    v25 = WinHttpSendRequest(*((HINTERNET *)this + 3), 0, 0, 0, 0, 0, 0);
    CHttpIoRequestWinHttp::ClearIoOriginThreadMarking(this);
    if ( v25 )
      return v15;
    LastError = GetLastError();
    v15 = LastError;
    if ( LastError > 0 )
      v15 = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)CallbackContext <= 2 )
      return v15;
    v24 = "WINHTTP WinHttpSendRequest failed";
    v34 = 1375;
    v16 = byte_1801B1FB1;
    goto LABEL_33;
  }
  if ( (unsigned int)CallbackContext > 2 )
  {
    v35 = "SendStreamModeRequestAsync";
    v30 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
    v34 = 1316;
    v18 = GetLastError();
    if ( v18 > 0 )
      v18 = (unsigned __int16)v18 | 0x80070000;
    LODWORD(v33) = v18;
    v31 = "LoadLibrary for WinHttp.dll failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v19,
      (unsigned int)byte_1801B20E1,
      v20,
      v21,
      (__int64)&v31,
      (__int64)&v33,
      (__int64)&v30,
      (__int64)&v34,
      (__int64)&v35);
  }
LABEL_9:
  if ( WinHttpSetOption(*((HINTERNET *)this + 3), 0x72u, 0, 0) || GetLastError() == 12155 )
    goto LABEL_19;
  v11 = GetLastError();
  v15 = v11;
  if ( v11 > 0 )
    v15 = (unsigned __int16)v11 | 0x80070000;
  if ( (unsigned int)CallbackContext > 2 )
  {
    v31 = "SendStreamModeRequestAsync";
    v35 = "SendStreamModeRequestAsync (Upgrade to Web Socket) failed";
    v16 = byte_1801B2095;
    v34 = 1333;
    *(_QWORD *)&ActivityId.Data1 = "Error condition failed";
    p_ActivityId = (GUID *)&v31;
    dwContext = &v30;
    v17 = &ActivityId;
    v30 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
LABEL_35:
    LODWORD(v33) = v15;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v12,
      (_DWORD)v16,
      v13,
      v14,
      (__int64)v17,
      (__int64)&v33,
      (__int64)dwContext,
      (__int64)&v34,
      (__int64)p_ActivityId,
      (__int64)&v35);
  }
  return v15;
}

```

## disassembly

```asm
0x18009e690  mov     [rsp-28h+arg_10], rbx
0x18009e695  push    rbp
0x18009e696  push    rsi
0x18009e697  push    rdi
0x18009e698  push    r13
0x18009e69a  push    r14
0x18009e69c  mov     rbp, rsp
0x18009e69f  sub     rsp, 70h
0x18009e6a3  mov     rsi, rcx
0x18009e6a6  mov     r14b, r8b
0x18009e6a9  lea     rcx, [rbp+ActivityId]; ActivityId
0x18009e6ad  mov     dil, dl
0x18009e6b0  call    ?GetCurrentActivityId@RdpActivityId@@SA?AU_GUID@@XZ; RdpActivityId::GetCurrentActivityId(void)
0x18009e6b5  lea     r13, aSendstreammode_1; "SendStreamModeRequestAsync"
0x18009e6bc  lea     rbx, aOnecoreTermsrv_8; "onecore\\termsrv\\rdp\\win\\httpio\\win"...
0x18009e6c3  movups  xmm0, xmmword ptr [rax]
0x18009e6c6  movdqu  xmmword ptr [rsi+78h], xmm0
0x18009e6cb  test    dil, dil
0x18009e6ce  jz      loc_18009E897
0x18009e6d4  mov     edx, 2; unsigned __int16
0x18009e6d9  call    ?IsWindowsVersionOrGreater@@YA_NGGG@Z; IsWindowsVersionOrGreater(ushort,ushort,ushort)
0x18009e6de  test    al, al
0x18009e6e0  jnz     short loc_18009E761
0x18009e6e2  lea     rcx, aWinhttpDll_0; "WinHttp.dll"
0x18009e6e9  call    cs:__imp_LoadLibraryW
0x18009e6ef  mov     rbx, rax
0x18009e6f2  test    rax, rax
0x18009e6f5  jz      loc_18009E814
0x18009e6fb  lea     rdx, aWinhttpwebsock_6; "WinHttpWebSocketSend"
0x18009e702  mov     rcx, rax; hModule
0x18009e705  call    cs:__imp_GetProcAddress
0x18009e70b  test    rax, rax
0x18009e70e  jnz     short loc_18009E748
0x18009e710  mov     ecx, cs:CallbackContext
0x18009e716  cmp     ecx, 4
0x18009e719  jbe     short loc_18009E745
0x18009e71b  lea     rax, aSendstreammode; "SendStreamModeRequestAsync - WebSockets"...
0x18009e722  xor     r8d, r8d
0x18009e725  mov     [rbp+arg_0], rax
0x18009e729  lea     rdx, byte_1801B2125
0x18009e730  lea     rax, [rbp+arg_0]
0x18009e734  lea     rcx, CallbackContext
0x18009e73b  mov     qword ptr [rsp+70h+dwOptionalLength], rax
0x18009e740  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18009e745  xor     dil, dil
0x18009e748  mov     rcx, rbx; hLibModule
0x18009e74b  call    cs:__imp_FreeLibrary
0x18009e751  test    dil, dil
0x18009e754  jz      loc_18009E897
0x18009e75a  lea     rbx, aOnecoreTermsrv_8; "onecore\\termsrv\\rdp\\win\\httpio\\win"...
0x18009e761  mov     rcx, [rsi+18h]; hInternet
0x18009e765  xor     r9d, r9d; dwBufferLength
0x18009e768  xor     r8d, r8d; lpBuffer
0x18009e76b  lea     edx, [r9+72h]; dwOption
0x18009e76f  call    cs:__imp_WinHttpSetOption
0x18009e775  test    eax, eax
0x18009e777  jnz     loc_18009E897
0x18009e77d  call    cs:__imp_GetLastError
0x18009e783  cmp     eax, 2F7Bh
0x18009e788  jz      loc_18009E897
0x18009e78e  call    cs:__imp_GetLastError
0x18009e794  mov     edi, eax
0x18009e796  test    eax, eax
0x18009e798  jle     short loc_18009E7A3
0x18009e79a  movzx   edi, ax
0x18009e79d  or      edi, 80070000h
0x18009e7a3  mov     eax, cs:CallbackContext
0x18009e7a9  cmp     eax, 2
0x18009e7ac  jbe     loc_18009EA33
0x18009e7b2  lea     rax, aSendstreammode_0; "SendStreamModeRequestAsync (Upgrade to "...
0x18009e7b9  mov     [rbp+var_18], r13
0x18009e7bd  mov     [rbp+arg_18], rax
0x18009e7c1  lea     rdx, byte_1801B2095
0x18009e7c8  lea     rax, aErrorCondition; "Error condition failed"
0x18009e7cf  mov     [rbp+arg_8], 535h
0x18009e7d6  mov     qword ptr [rbp+ActivityId.Data1], rax
0x18009e7da  lea     rax, [rbp+arg_18]
0x18009e7de  mov     [rsp+70h+var_28], rax
0x18009e7e3  lea     rax, [rbp+var_18]
0x18009e7e7  mov     [rsp+70h+var_30], rax
0x18009e7ec  lea     rax, [rbp+arg_8]
0x18009e7f0  mov     [rsp+70h+var_38], rax
0x18009e7f5  lea     rax, [rbp+var_20]
0x18009e7f9  mov     [rsp+70h+dwContext], rax
0x18009e7fe  lea     rax, [rbp+arg_0]
0x18009e802  mov     qword ptr [rsp+70h+dwTotalLength], rax
0x18009e807  lea     rax, [rbp+ActivityId]
0x18009e80b  mov     [rbp+var_20], rbx
0x18009e80f  jmp     loc_18009EA26
0x18009e814  mov     eax, cs:CallbackContext
0x18009e81a  cmp     eax, 2
0x18009e81d  jbe     loc_18009E75A
0x18009e823  lea     rbx, aOnecoreTermsrv_8; "onecore\\termsrv\\rdp\\win\\httpio\\win"...
0x18009e82a  mov     [rbp+arg_18], r13
0x18009e82e  mov     [rbp+var_20], rbx
0x18009e832  mov     [rbp+arg_8], 524h
0x18009e839  call    cs:__imp_GetLastError
0x18009e83f  test    eax, eax
0x18009e841  jle     short loc_18009E84B
0x18009e843  movzx   eax, ax
0x18009e846  or      eax, 80070000h
0x18009e84b  mov     dword ptr [rbp+arg_0], eax
0x18009e84e  lea     rdx, byte_1801B20E1
0x18009e855  lea     rax, aLoadlibraryFor; "LoadLibrary for WinHttp.dll failed"
0x18009e85c  mov     [rbp+var_18], rax
0x18009e860  lea     rax, [rbp+arg_18]
0x18009e864  mov     [rsp+70h+var_30], rax
0x18009e869  lea     rax, [rbp+arg_8]
0x18009e86d  mov     [rsp+70h+var_38], rax
0x18009e872  lea     rax, [rbp+var_20]
0x18009e876  mov     [rsp+70h+dwContext], rax
0x18009e87b  lea     rax, [rbp+arg_0]
0x18009e87f  mov     qword ptr [rsp+70h+dwTotalLength], rax
0x18009e884  lea     rax, [rbp+var_18]
0x18009e888  mov     qword ptr [rsp+70h+dwOptionalLength], rax
0x18009e88d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18009e892  jmp     loc_18009E761
0x18009e897  xor     edi, edi
0x18009e899  test    r14b, r14b
0x18009e89c  jz      loc_18009E95D
0x18009e8a2  mov     rax, [rsi]
0x18009e8a5  lea     r9d, [rdi+1]
0x18009e8a9  lea     r8, aChunked; "chunked"
0x18009e8b0  mov     rcx, rsi
0x18009e8b3  lea     rdx, aTransferEncodi; "transfer-encoding"
0x18009e8ba  mov     rax, [rax+18h]
0x18009e8be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e8c3  mov     edi, eax
0x18009e8c5  test    eax, eax
0x18009e8c7  jns     short loc_18009E908
0x18009e8c9  mov     ecx, cs:CallbackContext
0x18009e8cf  cmp     ecx, 2
0x18009e8d2  jbe     loc_18009EA33
0x18009e8d8  lea     rax, aAddrequesthead; "AddRequestHeaders transfer-encoding: ch"...
0x18009e8df  mov     [rbp+arg_8], 543h
0x18009e8e6  mov     [rbp+arg_18], rax
0x18009e8ea  lea     rdx, byte_1801B2049
0x18009e8f1  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdp\\win\\httpio\\win"...
0x18009e8f8  mov     [rbp+var_18], rax
0x18009e8fc  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18009e903  jmp     loc_18009E9ED
0x18009e908  cmp     qword ptr [rsi+0C0h], 0
0x18009e910  jnz     short loc_18009E956
0x18009e912  mov     ecx, 10000h; Size
0x18009e917  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18009e91c  mov     [rsi+0C0h], rax
0x18009e923  test    rax, rax
0x18009e926  jnz     short loc_18009E956
0x18009e928  mov     eax, cs:CallbackContext
0x18009e92e  mov     edi, 8007000Eh
0x18009e933  cmp     eax, 2
0x18009e936  jbe     loc_18009EA33
0x18009e93c  lea     rax, aAllocatingBuff_0; "Allocating buffer for chunk transfer en"...
0x18009e943  mov     [rbp+arg_8], 549h
0x18009e94a  lea     rdx, byte_1801B1FFD
0x18009e951  jmp     loc_18009E9D7
0x18009e956  mov     dword ptr [rsi+60h], 2
0x18009e95d  mov     rcx, rsi; this
0x18009e960  call    ?MarkIoOriginThread@CHttpIoRequestWinHttp@@AEAAXXZ; CHttpIoRequestWinHttp::MarkIoOriginThread(void)
0x18009e965  mov     rcx, [rsi+18h]; hRequest
0x18009e969  xor     r9d, r9d; lpOptional
0x18009e96c  mov     [rsp+70h+dwContext], 0; dwContext
0x18009e975  xor     r8d, r8d; dwHeadersLength
0x18009e978  mov     [rsp+70h+dwTotalLength], 0; dwTotalLength
0x18009e980  xor     edx, edx; lpszHeaders
0x18009e982  mov     [rsp+70h+dwOptionalLength], 0; dwOptionalLength
0x18009e98a  call    cs:__imp_WinHttpSendRequest
0x18009e990  mov     rcx, rsi; this
0x18009e993  mov     ebx, eax
0x18009e995  call    ?ClearIoOriginThreadMarking@CHttpIoRequestWinHttp@@AEAAXXZ; CHttpIoRequestWinHttp::ClearIoOriginThreadMarking(void)
0x18009e99a  test    ebx, ebx
0x18009e99c  jnz     loc_18009EA33
0x18009e9a2  call    cs:__imp_GetLastError
0x18009e9a8  mov     edi, eax
0x18009e9aa  test    eax, eax
0x18009e9ac  jle     short loc_18009E9B7
0x18009e9ae  movzx   edi, ax
0x18009e9b1  or      edi, 80070000h
0x18009e9b7  mov     eax, cs:CallbackContext
0x18009e9bd  cmp     eax, 2
0x18009e9c0  jbe     short loc_18009EA33
0x18009e9c2  lea     rax, aWinhttpWinhttp; "WINHTTP WinHttpSendRequest failed"
0x18009e9c9  mov     [rbp+arg_8], 55Fh
0x18009e9d0  lea     rdx, byte_1801B1FB1
0x18009e9d7  mov     [rbp+arg_18], rax
0x18009e9db  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdp\\win\\httpio\\win"...
0x18009e9e2  mov     [rbp+var_18], rax
0x18009e9e6  lea     rax, aErrorCondition; "Error condition failed"
0x18009e9ed  mov     [rbp+var_20], rax
0x18009e9f1  lea     rax, [rbp+arg_18]
0x18009e9f5  mov     [rsp+70h+var_28], rax
0x18009e9fa  lea     rax, [rbp+ActivityId]
0x18009e9fe  mov     [rsp+70h+var_30], rax
0x18009ea03  lea     rax, [rbp+arg_8]
0x18009ea07  mov     [rsp+70h+var_38], rax
0x18009ea0c  lea     rax, [rbp+var_18]
0x18009ea10  mov     [rsp+70h+dwContext], rax
0x18009ea15  lea     rax, [rbp+arg_0]
0x18009ea19  mov     qword ptr [rsp+70h+dwTotalLength], rax
0x18009ea1e  lea     rax, [rbp+var_20]
0x18009ea22  mov     qword ptr [rbp+ActivityId.Data1], r13
0x18009ea26  mov     qword ptr [rsp+70h+dwOptionalLength], rax
0x18009ea2b  mov     dword ptr [rbp+arg_0], edi
0x18009ea2e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18009ea33  mov     rbx, [rsp+70h+arg_10]
0x18009ea3b  mov     eax, edi
0x18009ea3d  add     rsp, 70h
0x18009ea41  pop     r14
0x18009ea43  pop     r13
0x18009ea45  pop     rdi
0x18009ea46  pop     rsi
0x18009ea47  pop     rbp
0x18009ea48  retn
```
