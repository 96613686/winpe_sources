# CHttpIoRequestWinHttp::WebSocketCompleteUpgrade(void)

- ea: `0x1800a09c4`
- end: `0x1800a0ba2`
- name: `?WebSocketCompleteUpgrade@CHttpIoRequestWinHttp@@AEAA_NXZ`
- size: `478`
- prototype: `bool __fastcall(CHttpIoRequestWinHttp *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18009f024`

## callees

- `0x180001aa0`
- `0x1800022f4`
- `0x18009ea50`
- `0x1800a09c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0a01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0b04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0a01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0b04`
- `WINHTTP!WinHttpCloseHandle` at `0x1800a0ae6`
- `WINHTTP!WinHttpCloseHandle` at `0x1800a0ae6`
- `WINHTTP!WinHttpWebSocketCompleteUpgrade` at `0x1800a09ee`
- `WINHTTP!WinHttpWebSocketCompleteUpgrade` at `0x1800a09ee`
- `WINHTTP!WinHttpSetStatusCallback` at `0x1800a09e2`
- `WINHTTP!WinHttpSetStatusCallback` at `0x1800a09e2`

## string_xrefs

- `0x1800a0a25`: `WinHttpWebSocketCompleteUpgrade failed`
- `0x1800a0a3e`: `WebSocketCompleteUpgrade`
- `0x1800a0b3d`: `WebSocketCompleteUpgrade`

## pseudocode

```c
char __fastcall CHttpIoRequestWinHttp::WebSocketCompleteUpgrade(HINTERNET *this)
{
  char v2; // di
  HINTERNET v3; // rax
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d
  signed int v7; // eax
  int v8; // r8d
  int v9; // r9d
  unsigned int v10; // ecx
  __int64 *v11; // rdx
  const char **v12; // rax
  signed int LastError; // eax
  const char **v15; // [rsp+30h] [rbp-30h]
  const char *v16; // [rsp+50h] [rbp-10h] BYREF
  const char *v17; // [rsp+58h] [rbp-8h] BYREF
  HINTERNET v18; // [rsp+80h] [rbp+20h] BYREF
  const char *v19; // [rsp+88h] [rbp+28h] BYREF
  const char *v20; // [rsp+90h] [rbp+30h] BYREF
  const char *v21; // [rsp+98h] [rbp+38h] BYREF

  v2 = 0;
  WinHttpSetStatusCallback(this[3], 0, 0xFFFFFFFF, 0);
  v3 = WinHttpWebSocketCompleteUpgrade(this[3], 0);
  this[4] = v3;
  if ( v3 )
  {
    *((_BYTE *)this + 72) = 1;
    if ( (unsigned int)CallbackContext > 4 )
    {
      v18 = this[3];
      v19 = "Closing Request Handle";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        v4,
        (unsigned int)&dword_1801B1A64,
        v5,
        v6,
        (__int64)&v19,
        (__int64)&v18);
    }
    WinHttpCloseHandle(this[3]);
    this[3] = 0;
    if ( CHttpIoRequestWinHttp::SetHttpCallback((CHttpIoRequestWinHttp *)this) )
      return 1;
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v18) = 1745;
      v20 = "SetHttpCallback failed";
      v11 = qword_1801B1A18;
      v21 = "WebSocketCompleteUpgrade";
      v17 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
      v16 = "Error condition failed";
      v15 = &v17;
      v12 = &v16;
      goto LABEL_6;
    }
  }
  else
  {
    v7 = GetLastError();
    v10 = v7;
    if ( v7 > 0 )
      v10 = (unsigned __int16)v7 | 0x80070000;
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v18) = 1735;
      v20 = "WinHttpWebSocketCompleteUpgrade failed";
      v11 = (__int64 *)&dword_1801B1A8C;
      v21 = "WebSocketCompleteUpgrade";
      v16 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
      v17 = "Error condition failed";
      v15 = &v16;
      v12 = &v17;
LABEL_6:
      LODWORD(v19) = v10;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v10,
        (_DWORD)v11,
        v8,
        v9,
        (__int64)v12,
        (__int64)&v19,
        (__int64)v15,
        (__int64)&v18,
        (__int64)&v21,
        (__int64)&v20);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1800a09c4  push    rbp
0x1800a09c6  push    rbx
0x1800a09c7  push    rdi
0x1800a09c8  mov     rbp, rsp
0x1800a09cb  sub     rsp, 60h
0x1800a09cf  mov     rbx, rcx
0x1800a09d2  xor     r9d, r9d; dwReserved
0x1800a09d5  mov     rcx, [rcx+18h]; hInternet
0x1800a09d9  or      r8d, 0FFFFFFFFh; dwNotificationFlags
0x1800a09dd  xor     edx, edx; lpfnInternetCallback
0x1800a09df  xor     dil, dil
0x1800a09e2  call    cs:__imp_WinHttpSetStatusCallback
0x1800a09e8  mov     rcx, [rbx+18h]; hRequest
0x1800a09ec  xor     edx, edx; pContext
0x1800a09ee  call    cs:__imp_WinHttpWebSocketCompleteUpgrade
0x1800a09f4  mov     [rbx+20h], rax
0x1800a09f8  test    rax, rax
0x1800a09fb  jnz     loc_1800A0AA2
0x1800a0a01  call    cs:__imp_GetLastError
0x1800a0a07  mov     ecx, eax
0x1800a0a09  test    eax, eax
0x1800a0a0b  jle     short loc_1800A0A16
0x1800a0a0d  movzx   ecx, ax
0x1800a0a10  or      ecx, 80070000h
0x1800a0a16  mov     eax, cs:CallbackContext
0x1800a0a1c  cmp     eax, 2
0x1800a0a1f  jbe     loc_1800A0B97
0x1800a0a25  lea     rax, aWinhttpwebsock_9; "WinHttpWebSocketCompleteUpgrade failed"
0x1800a0a2c  mov     dword ptr [rbp+arg_0], 6C7h
0x1800a0a33  mov     [rbp+arg_10], rax
0x1800a0a37  lea     rdx, dword_1801B1A8C
0x1800a0a3e  lea     rax, aWebsocketcompl; "WebSocketCompleteUpgrade"
0x1800a0a45  mov     [rbp+arg_18], rax
0x1800a0a49  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdp\\win\\httpio\\win"...
0x1800a0a50  mov     [rbp+var_10], rax
0x1800a0a54  lea     rax, aErrorCondition; "Error condition failed"
0x1800a0a5b  mov     [rbp+var_8], rax
0x1800a0a5f  lea     rax, [rbp+arg_10]
0x1800a0a63  mov     [rsp+60h+var_18], rax
0x1800a0a68  lea     rax, [rbp+arg_18]
0x1800a0a6c  mov     [rsp+60h+var_20], rax
0x1800a0a71  lea     rax, [rbp+arg_0]
0x1800a0a75  mov     [rsp+60h+var_28], rax
0x1800a0a7a  lea     rax, [rbp+var_10]
0x1800a0a7e  mov     [rsp+60h+var_30], rax
0x1800a0a83  lea     rax, [rbp+arg_8]
0x1800a0a87  mov     [rsp+60h+var_38], rax
0x1800a0a8c  lea     rax, [rbp+var_8]
0x1800a0a90  mov     [rsp+60h+var_40], rax
0x1800a0a95  mov     dword ptr [rbp+arg_8], ecx
0x1800a0a98  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800a0a9d  jmp     loc_1800A0B97
0x1800a0aa2  mov     byte ptr [rbx+48h], 1
0x1800a0aa6  mov     eax, cs:CallbackContext
0x1800a0aac  cmp     eax, 4
0x1800a0aaf  jbe     short loc_1800A0AE2
0x1800a0ab1  mov     rax, [rbx+18h]
0x1800a0ab5  lea     rdx, dword_1801B1A64
0x1800a0abc  mov     [rbp+arg_0], rax
0x1800a0ac0  lea     rax, aClosingRequest; "Closing Request Handle"
0x1800a0ac7  mov     [rbp+arg_8], rax
0x1800a0acb  lea     rax, [rbp+arg_0]
0x1800a0acf  mov     [rsp+60h+var_38], rax
0x1800a0ad4  lea     rax, [rbp+arg_8]
0x1800a0ad8  mov     [rsp+60h+var_40], rax
0x1800a0add  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x1800a0ae2  mov     rcx, [rbx+18h]; hInternet
0x1800a0ae6  call    cs:__imp_WinHttpCloseHandle
0x1800a0aec  mov     rcx, rbx; this
0x1800a0aef  mov     qword ptr [rbx+18h], 0
0x1800a0af7  call    ?SetHttpCallback@CHttpIoRequestWinHttp@@AEAA_NXZ; CHttpIoRequestWinHttp::SetHttpCallback(void)
0x1800a0afc  test    al, al
0x1800a0afe  jnz     loc_1800A0B94
0x1800a0b04  call    cs:__imp_GetLastError
0x1800a0b0a  mov     ecx, eax
0x1800a0b0c  test    eax, eax
0x1800a0b0e  jle     short loc_1800A0B19
0x1800a0b10  movzx   ecx, ax
0x1800a0b13  or      ecx, 80070000h
0x1800a0b19  mov     eax, cs:CallbackContext
0x1800a0b1f  cmp     eax, 2
0x1800a0b22  jbe     short loc_1800A0B97
0x1800a0b24  lea     rax, aSethttpcallbac; "SetHttpCallback failed"
0x1800a0b2b  mov     dword ptr [rbp+arg_0], 6D1h
0x1800a0b32  mov     [rbp+arg_10], rax
0x1800a0b36  lea     rdx, qword_1801B1A18
0x1800a0b3d  lea     rax, aWebsocketcompl; "WebSocketCompleteUpgrade"
0x1800a0b44  mov     [rbp+arg_18], rax
0x1800a0b48  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdp\\win\\httpio\\win"...
0x1800a0b4f  mov     [rbp+var_8], rax
0x1800a0b53  lea     rax, aErrorCondition; "Error condition failed"
0x1800a0b5a  mov     [rbp+var_10], rax
0x1800a0b5e  lea     rax, [rbp+arg_10]
0x1800a0b62  mov     [rsp+60h+var_18], rax
0x1800a0b67  lea     rax, [rbp+arg_18]
0x1800a0b6b  mov     [rsp+60h+var_20], rax
0x1800a0b70  lea     rax, [rbp+arg_0]
0x1800a0b74  mov     [rsp+60h+var_28], rax
0x1800a0b79  lea     rax, [rbp+var_8]
0x1800a0b7d  mov     [rsp+60h+var_30], rax
0x1800a0b82  lea     rax, [rbp+arg_8]
0x1800a0b86  mov     [rsp+60h+var_38], rax
0x1800a0b8b  lea     rax, [rbp+var_10]
0x1800a0b8f  jmp     loc_1800A0A90
0x1800a0b94  mov     dil, 1
0x1800a0b97  mov     al, dil
0x1800a0b9a  add     rsp, 60h
0x1800a0b9e  pop     rdi
0x1800a0b9f  pop     rbx
0x1800a0ba0  pop     rbp
0x1800a0ba1  retn
```
