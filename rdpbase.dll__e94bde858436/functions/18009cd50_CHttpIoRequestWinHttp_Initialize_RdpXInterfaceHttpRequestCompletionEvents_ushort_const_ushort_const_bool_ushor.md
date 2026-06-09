# CHttpIoRequestWinHttp::Initialize(RdpXInterfaceHttpRequestCompletionEvents *,ushort const *,ushort const *,bool,ushort const *,bool)

- ea: `0x18009cd50`
- end: `0x18009d306`
- name: `?Initialize@CHttpIoRequestWinHttp@@QEAAJPEAURdpXInterfaceHttpRequestCompletionEvents@@PEBG1_N12@Z`
- size: `1462`
- prototype: `__int64 __usercall@<rax>(CHttpIoRequestWinHttp *__hidden this@<rcx>, struct RdpXInterfaceHttpRequestCompletionEvents *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, bool, const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18009b2a0`

## callees

- `0x1800018a4`
- `0x180001aa0`
- `0x180002550`
- `0x180038984`
- `0x18004a888`
- `0x1800787d4`
- `0x180078820`
- `0x180079678`
- `0x18007969c`
- `0x18009cd50`
- `0x18009ea50`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x18009cdc2`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x18009cdc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d162`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d21f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d278`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d162`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d21f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d278`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18009d210`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18009d210`
- `WINHTTP!WinHttpOpenRequest` at `0x18009d14f`
- `WINHTTP!WinHttpOpenRequest` at `0x18009d14f`

## string_xrefs

- `0x18009ce10`: `Failed to allocated thread local storage`
- `0x18009cf6f`: `XChar16_Array_acceptMediaTypesCopy allocation failed`
- `0x18009d186`: `WinHttpOpenRequest failed`
- `0x18009d243`: `CreateThreadpoolWork failed`

## pseudocode

```c
__int64 __fastcall CHttpIoRequestWinHttp::Initialize(
        CHttpIoRequestWinHttp *this,
        struct RdpXInterfaceHttpRequestCompletionEvents *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        bool a5,
        unsigned __int16 *a6,
        int a7)
{
  DWORD v10; // eax
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  unsigned int v14; // ebx
  const unsigned __int16 *v15; // rsi
  unsigned __int16 *v16; // r15
  void *v17; // r14
  LPCWSTR *ppwszAcceptTypes; // rdx
  int v19; // r8d
  int v20; // r9d
  unsigned __int64 v21; // r14
  unsigned __int16 *v22; // rax
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  unsigned __int16 v26; // r11
  BOOL v27; // ecx
  unsigned __int16 *v28; // rdx
  bool v29; // zf
  int v30; // eax
  unsigned __int64 v31; // rsi
  void *v32; // rax
  int v33; // r8d
  int v34; // r9d
  __int64 v35; // rsi
  wchar_t *i; // rcx
  wchar_t *v37; // rax
  HINTERNET v38; // rax
  signed int v39; // eax
  int v40; // ecx
  int v41; // r8d
  int v42; // r9d
  const char *v43; // rax
  char *v44; // rdx
  PTP_WORK ThreadpoolWork; // rax
  signed int v46; // eax
  signed int LastError; // eax
  wchar_t *Context; // [rsp+50h] [rbp-31h] BYREF
  const char *v50; // [rsp+58h] [rbp-29h] BYREF
  const char *v51; // [rsp+60h] [rbp-21h] BYREF
  const char *v52; // [rsp+68h] [rbp-19h] BYREF
  const char *v53; // [rsp+70h] [rbp-11h] BYREF
  LPCWSTR v54[9]; // [rsp+78h] [rbp-9h] BYREF
  unsigned __int64 v55; // [rsp+D0h] [rbp+4Fh] BYREF
  LPCWSTR pwszVerb; // [rsp+E0h] [rbp+5Fh]

  pwszVerb = a3;
  v54[1] = 0;
  v54[0] = L"*/*";
  if ( (unsigned int)CallbackContext > 4 )
  {
    v55 = (unsigned __int64)"Initializing request instance";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (unsigned int)&CallbackContext,
      (unsigned int)&byte_1801B27AF,
      0,
      (_DWORD)a4,
      (__int64)&v55);
  }
  v10 = TlsAlloc();
  *((_DWORD *)this + 148) = v10;
  if ( v10 == -1 )
  {
    v14 = -2147024882;
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v55) = -2147024882;
      Context = (wchar_t *)"Initialize";
      a7 = 769;
      v50 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
      v51 = "Failed to allocated thread local storage";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v11,
        (unsigned int)byte_1801B276B,
        v12,
        v13,
        (__int64)&v51,
        (__int64)&v55,
        (__int64)&v50,
        (__int64)&a7,
        (__int64)&Context);
    }
    return v14;
  }
  v15 = a6;
  v16 = 0;
  v17 = 0;
  v14 = 0;
  if ( a6 == (unsigned __int16 *)-1LL )
  {
    ppwszAcceptTypes = v54;
    goto LABEL_28;
  }
  if ( !a6 )
  {
    ppwszAcceptTypes = 0;
    goto LABEL_28;
  }
  v55 = 0;
  Context = 0;
  v14 = StringCchLengthW(a6, 0x7FFFFFFFu, &v55);
  if ( (v14 & 0x80000000) != 0 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      a7 = 788;
      v51 = "StringCchLength failed";
      LODWORD(v55) = v14;
      v50 = "Initialize";
      v52 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
      v53 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (_DWORD)CallbackContext,
        (unsigned int)&byte_1801B271F,
        v19,
        v20,
        (__int64)&v53,
        (__int64)&v55,
        (__int64)&v52,
        (__int64)&a7,
        (__int64)&v50,
        (__int64)&v51);
    }
    return v14;
  }
  v21 = v55 + 1;
  v22 = (unsigned __int16 *)operator new(saturated_mul(v55 + 1, 2u));
  v16 = v22;
  if ( v22 )
  {
    StringCchCopyW(v22, v21, v15);
    v26 = *v16;
    v27 = *v16 != 0;
    if ( *v16 )
    {
      v28 = v16;
      do
      {
        v29 = v26 == 44;
        v30 = v27 + 1;
        v26 = *++v28;
        if ( !v29 )
          v30 = v27;
        v27 = v30;
      }
      while ( v26 );
    }
    v31 = (unsigned int)(v27 + 1);
    v32 = operator new(saturated_mul(v31, 8u));
    v17 = v32;
    if ( !v32 )
    {
      v14 = -2147024882;
      if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(v55) = -2147024882;
        v53 = "LPCWSTR_Array_pCustomAcceptTypes allocation failed";
        a7 = 812;
        v52 = "Initialize";
        v51 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
        v50 = "Error condition failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (_DWORD)CallbackContext,
          (unsigned int)&byte_1801B2687,
          v33,
          v34,
          (__int64)&v50,
          (__int64)&v55,
          (__int64)&v51,
          (__int64)&a7,
          (__int64)&v52,
          (__int64)&v53);
      }
LABEL_46:
      operator delete(v16);
LABEL_47:
      if ( v17 )
        operator delete(v17);
      return v14;
    }
    memset_0(v32, 0, 8 * v31);
    v35 = 0;
    for ( i = v16; ; i = 0 )
    {
      v37 = o_wcstok_s_0(i, L",", &Context);
      if ( !v37 )
        break;
      *((_QWORD *)v17 + v35) = v37;
      v35 = (unsigned int)(v35 + 1);
    }
    ppwszAcceptTypes = (LPCWSTR *)v17;
LABEL_28:
    v38 = WinHttpOpenRequest(
            *(HINTERNET *)(*((_QWORD *)this + 5) + 16LL),
            pwszVerb,
            a4,
            0,
            0,
            ppwszAcceptTypes,
            ((unsigned __int8)a5 << 23) + 256);
    *((_QWORD *)this + 3) = v38;
    if ( v38 )
    {
      ThreadpoolWork = CreateThreadpoolWork(CHttpIoRequestWinHttp::TpCallback, this, 0);
      *((_QWORD *)this + 14) = ThreadpoolWork;
      if ( ThreadpoolWork )
      {
        *((_QWORD *)this + 7) = a2;
        *((_BYTE *)this + 136) = 0;
        if ( CHttpIoRequestWinHttp::SetHttpCallback(this) )
        {
          (***((void (__fastcall ****)(_QWORD))this + 7))(*((_QWORD *)this + 7));
          (**(void (__fastcall ***)(CHttpIoRequestWinHttp *))this)(this);
        }
        else
        {
          *((_QWORD *)this + 7) = 0;
          LastError = GetLastError();
          v14 = LastError;
          if ( LastError > 0 )
            v14 = (unsigned __int16)LastError | 0x80070000;
          if ( (unsigned int)CallbackContext > 2 )
          {
            v43 = "WinHttpSetStatusCallback failed";
            a7 = 854;
            v44 = byte_1801B25A3;
            goto LABEL_33;
          }
        }
      }
      else
      {
        v46 = GetLastError();
        v14 = v46;
        if ( v46 > 0 )
          v14 = (unsigned __int16)v46 | 0x80070000;
        if ( (unsigned int)CallbackContext > 2 )
        {
          v43 = "CreateThreadpoolWork failed";
          a7 = 846;
          v44 = &byte_1801B25EF;
          goto LABEL_33;
        }
      }
    }
    else
    {
      v39 = GetLastError();
      v14 = v39;
      if ( v39 > 0 )
        v14 = (unsigned __int16)v39 | 0x80070000;
      if ( (unsigned int)CallbackContext > 2 )
      {
        v43 = "WinHttpOpenRequest failed";
        a7 = 839;
        v44 = byte_1801B263B;
LABEL_33:
        v53 = v43;
        v52 = "Initialize";
        v51 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
        v50 = "Error condition failed";
        LODWORD(v55) = v14;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v40,
          (_DWORD)v44,
          v41,
          v42,
          (__int64)&v50,
          (__int64)&v55,
          (__int64)&v51,
          (__int64)&a7,
          (__int64)&v52,
          (__int64)&v53);
      }
    }
    if ( !v16 )
      goto LABEL_47;
    goto LABEL_46;
  }
  v14 = -2147024882;
  if ( (unsigned int)CallbackContext > 2 )
  {
    LODWORD(v55) = -2147024882;
    v53 = "XChar16_Array_acceptMediaTypesCopy allocation failed";
    a7 = 791;
    v52 = "Initialize";
    v51 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
    v50 = "Error condition failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v23,
      (unsigned int)byte_1801B26D3,
      v24,
      v25,
      (__int64)&v50,
      (__int64)&v55,
      (__int64)&v51,
      (__int64)&a7,
      (__int64)&v52,
      (__int64)&v53);
  }
  return v14;
}

```

## disassembly

```asm
0x18009cd50  mov     [rsp-8+arg_8], rbx
0x18009cd55  mov     [rsp-8+pwszVerb], r8
0x18009cd5a  push    rbp
0x18009cd5b  push    rsi
0x18009cd5c  push    rdi
0x18009cd5d  push    r12
0x18009cd5f  push    r13
0x18009cd61  push    r14
0x18009cd63  push    r15
0x18009cd65  lea     rbp, [rsp-0Fh]
0x18009cd6a  sub     rsp, 90h
0x18009cd71  lea     rax, asc_1801771E8; "*/*"
0x18009cd78  mov     [rbp+3Fh+var_40], 0
0x18009cd80  mov     [rbp+3Fh+var_48], rax
0x18009cd84  mov     r13, r9
0x18009cd87  mov     eax, cs:CallbackContext
0x18009cd8d  mov     r12, rdx
0x18009cd90  mov     rdi, rcx
0x18009cd93  cmp     eax, 4
0x18009cd96  jbe     short loc_18009CDC2
0x18009cd98  lea     rax, aInitializingRe; "Initializing request instance"
0x18009cd9f  xor     r8d, r8d
0x18009cda2  mov     [rbp+3Fh+arg_0], rax
0x18009cda6  lea     rdx, byte_1801B27AF
0x18009cdad  lea     rax, [rbp+3Fh+arg_0]
0x18009cdb1  lea     rcx, CallbackContext
0x18009cdb8  mov     [rsp+0C0h+pwszReferrer], rax
0x18009cdbd  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18009cdc2  call    cs:__imp_TlsAlloc
0x18009cdc8  mov     [rdi+250h], eax
0x18009cdce  cmp     eax, 0FFFFFFFFh
0x18009cdd1  jnz     short loc_18009CE52
0x18009cdd3  mov     eax, cs:CallbackContext
0x18009cdd9  mov     edx, 8007000Eh
0x18009cdde  mov     ebx, edx
0x18009cde0  cmp     eax, 2
0x18009cde3  jbe     loc_18009D2E9
0x18009cde9  lea     rax, aInitialize; "Initialize"
0x18009cdf0  mov     dword ptr [rbp+3Fh+arg_0], edx
0x18009cdf3  mov     [rbp+3Fh+Context], rax
0x18009cdf7  lea     rdx, byte_1801B276B
0x18009cdfe  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdp\\win\\httpio\\win"...
0x18009ce05  mov     [rbp+3Fh+arg_30], 301h
0x18009ce0c  mov     [rbp+3Fh+var_68], rax
0x18009ce10  lea     rax, aFailedToAlloca_25; "Failed to allocated thread local storag"...
0x18009ce17  mov     [rbp+3Fh+var_60], rax
0x18009ce1b  lea     rax, [rbp+3Fh+Context]
0x18009ce1f  mov     [rsp+0C0h+var_80], rax
0x18009ce24  lea     rax, [rbp+3Fh+arg_30]
0x18009ce28  mov     [rsp+0C0h+var_88], rax
0x18009ce2d  lea     rax, [rbp+3Fh+var_68]
0x18009ce31  mov     qword ptr [rsp+0C0h+dwFlags], rax
0x18009ce36  lea     rax, [rbp+3Fh+arg_0]
0x18009ce3a  mov     [rsp+0C0h+ppwszAcceptTypes], rax
0x18009ce3f  lea     rax, [rbp+3Fh+var_60]
0x18009ce43  mov     [rsp+0C0h+pwszReferrer], rax
0x18009ce48  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18009ce4d  jmp     loc_18009D2E9
0x18009ce52  mov     rsi, [rbp+3Fh+arg_28]
0x18009ce56  xor     r11d, r11d
0x18009ce59  mov     r15d, r11d
0x18009ce5c  mov     r14d, r11d
0x18009ce5f  mov     ebx, r11d
0x18009ce62  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18009ce66  jnz     short loc_18009CE73
0x18009ce68  lea     rdx, [rbp+3Fh+var_48]
0x18009ce6c  xor     esi, esi
0x18009ce6e  jmp     loc_18009D123
0x18009ce73  test    rsi, rsi
0x18009ce76  jz      loc_18009D120
0x18009ce7c  lea     r8, [rbp+3Fh+arg_0]; unsigned __int64 *
0x18009ce80  mov     [rbp+3Fh+arg_0], r11
0x18009ce84  mov     edx, 7FFFFFFFh; unsigned __int64
0x18009ce89  mov     [rbp+3Fh+Context], r11
0x18009ce8d  mov     rcx, rsi; unsigned __int16 *
0x18009ce90  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18009ce95  mov     ebx, eax
0x18009ce97  test    eax, eax
0x18009ce99  jns     loc_18009CF2B
0x18009ce9f  mov     ecx, cs:CallbackContext
0x18009cea5  cmp     ecx, 2
0x18009cea8  jbe     loc_18009D2E9
0x18009ceae  lea     rax, aStringcchlengt_3; "StringCchLength failed"
0x18009ceb5  mov     [rbp+3Fh+arg_30], 314h
0x18009cebc  mov     [rbp+3Fh+var_60], rax
0x18009cec0  lea     rdx, byte_1801B271F
0x18009cec7  lea     rax, aInitialize; "Initialize"
0x18009cece  mov     dword ptr [rbp+3Fh+arg_0], ebx
0x18009ced1  mov     [rbp+3Fh+var_68], rax
0x18009ced5  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdp\\win\\httpio\\win"...
0x18009cedc  mov     [rbp+3Fh+var_58], rax
0x18009cee0  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18009cee7  mov     [rbp+3Fh+var_50], rax
0x18009ceeb  lea     rax, [rbp+3Fh+var_60]
0x18009ceef  mov     [rsp+0C0h+var_78], rax
0x18009cef4  lea     rax, [rbp+3Fh+var_68]
0x18009cef8  mov     [rsp+0C0h+var_80], rax
0x18009cefd  lea     rax, [rbp+3Fh+arg_30]
0x18009cf01  mov     [rsp+0C0h+var_88], rax
0x18009cf06  lea     rax, [rbp+3Fh+var_58]
0x18009cf0a  mov     qword ptr [rsp+0C0h+dwFlags], rax
0x18009cf0f  lea     rax, [rbp+3Fh+arg_0]
0x18009cf13  mov     [rsp+0C0h+ppwszAcceptTypes], rax
0x18009cf18  lea     rax, [rbp+3Fh+var_50]
0x18009cf1c  mov     [rsp+0C0h+pwszReferrer], rax
0x18009cf21  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18009cf26  jmp     loc_18009D2E9
0x18009cf2b  mov     r14, [rbp+3Fh+arg_0]
0x18009cf2f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18009cf36  inc     r14
0x18009cf39  mov     eax, 2
0x18009cf3e  mul     r14
0x18009cf41  cmovb   rax, rcx
0x18009cf45  mov     rcx, rax; Size
0x18009cf48  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18009cf4d  mov     r15, rax
0x18009cf50  test    rax, rax
0x18009cf53  jnz     loc_18009CFE2
0x18009cf59  mov     eax, cs:CallbackContext
0x18009cf5f  mov     edx, 8007000Eh
0x18009cf64  mov     ebx, edx
0x18009cf66  cmp     eax, 2
0x18009cf69  jbe     loc_18009D2E9
0x18009cf6f  lea     rax, aXchar16ArrayAc; "XChar16_Array_acceptMediaTypesCopy allo"...
0x18009cf76  mov     dword ptr [rbp+3Fh+arg_0], edx
0x18009cf79  mov     [rbp+3Fh+var_50], rax
0x18009cf7d  lea     rdx, byte_1801B26D3
0x18009cf84  lea     rax, aInitialize; "Initialize"
0x18009cf8b  mov     [rbp+3Fh+arg_30], 317h
0x18009cf92  mov     [rbp+3Fh+var_58], rax
0x18009cf96  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdp\\win\\httpio\\win"...
0x18009cf9d  mov     [rbp+3Fh+var_60], rax
0x18009cfa1  lea     rax, aErrorCondition; "Error condition failed"
0x18009cfa8  mov     [rbp+3Fh+var_68], rax
0x18009cfac  lea     rax, [rbp+3Fh+var_50]
0x18009cfb0  mov     [rsp+0C0h+var_78], rax
0x18009cfb5  lea     rax, [rbp+3Fh+var_58]
0x18009cfb9  mov     [rsp+0C0h+var_80], rax
0x18009cfbe  lea     rax, [rbp+3Fh+arg_30]
0x18009cfc2  mov     [rsp+0C0h+var_88], rax
0x18009cfc7  lea     rax, [rbp+3Fh+var_60]
0x18009cfcb  mov     qword ptr [rsp+0C0h+dwFlags], rax
0x18009cfd0  lea     rax, [rbp+3Fh+arg_0]
0x18009cfd4  mov     [rsp+0C0h+ppwszAcceptTypes], rax
0x18009cfd9  lea     rax, [rbp+3Fh+var_68]
0x18009cfdd  jmp     loc_18009CF1C
0x18009cfe2  mov     r8, rsi; unsigned __int16 *
0x18009cfe5  mov     rdx, r14; unsigned __int64
0x18009cfe8  mov     rcx, r15; unsigned __int16 *
0x18009cfeb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18009cff0  movzx   r11d, word ptr [r15]
0x18009cff4  xor     r8d, r8d
0x18009cff7  test    r11w, r11w
0x18009cffb  mov     ecx, r8d
0x18009cffe  setnz   cl
0x18009d001  test    r11w, r11w
0x18009d005  jz      short loc_18009D025
0x18009d007  mov     rdx, r15
0x18009d00a  cmp     r11w, 2Ch ; ','
0x18009d00f  lea     eax, [rcx+1]
0x18009d012  lea     rdx, [rdx+2]
0x18009d016  movzx   r11d, word ptr [rdx]
0x18009d01a  cmovnz  eax, ecx
0x18009d01d  mov     ecx, eax
0x18009d01f  test    r11w, r11w
0x18009d023  jnz     short loc_18009D00A
0x18009d025  lea     esi, [rcx+1]
0x18009d028  mov     eax, 8
0x18009d02d  mul     rsi
0x18009d030  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18009d037  cmovb   rax, rcx
0x18009d03b  mov     rcx, rax; Size
0x18009d03e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18009d043  mov     r14, rax
0x18009d046  test    rax, rax
0x18009d049  jnz     loc_18009D0E2
0x18009d04f  mov     ecx, cs:CallbackContext
0x18009d055  mov     edx, 8007000Eh
0x18009d05a  mov     ebx, edx
0x18009d05c  cmp     ecx, 2
0x18009d05f  jbe     loc_18009D2D4
0x18009d065  lea     rax, aLpcwstrArrayPc; "LPCWSTR_Array_pCustomAcceptTypes alloca"...
0x18009d06c  mov     dword ptr [rbp+3Fh+arg_0], edx
0x18009d06f  mov     [rbp+3Fh+var_50], rax
0x18009d073  lea     rdx, byte_1801B2687
0x18009d07a  lea     rax, aInitialize; "Initialize"
0x18009d081  mov     [rbp+3Fh+arg_30], 32Ch
0x18009d088  mov     [rbp+3Fh+var_58], rax
0x18009d08c  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdp\\win\\httpio\\win"...
0x18009d093  mov     [rbp+3Fh+var_60], rax
0x18009d097  lea     rax, aErrorCondition; "Error condition failed"
0x18009d09e  mov     [rbp+3Fh+var_68], rax
0x18009d0a2  lea     rax, [rbp+3Fh+var_50]
0x18009d0a6  mov     [rsp+0C0h+var_78], rax
0x18009d0ab  lea     rax, [rbp+3Fh+var_58]
0x18009d0af  mov     [rsp+0C0h+var_80], rax
0x18009d0b4  lea     rax, [rbp+3Fh+arg_30]
0x18009d0b8  mov     [rsp+0C0h+var_88], rax
0x18009d0bd  lea     rax, [rbp+3Fh+var_60]
0x18009d0c1  mov     qword ptr [rsp+0C0h+dwFlags], rax
0x18009d0c6  lea     rax, [rbp+3Fh+arg_0]
0x18009d0ca  mov     [rsp+0C0h+ppwszAcceptTypes], rax
0x18009d0cf  lea     rax, [rbp+3Fh+var_68]
0x18009d0d3  mov     [rsp+0C0h+pwszReferrer], rax
0x18009d0d8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18009d0dd  jmp     loc_18009D2D4
0x18009d0e2  lea     r8, ds:0[rsi*8]; Size
0x18009d0ea  xor     edx, edx; Val
0x18009d0ec  mov     rcx, r14; void *
0x18009d0ef  call    memset_0
0x18009d0f4  xor     esi, esi
0x18009d0f6  mov     rcx, r15
0x18009d0f9  jmp     short loc_18009D103
0x18009d0fb  mov     [r14+rsi*8], rax
0x18009d0ff  inc     esi
0x18009d101  xor     ecx, ecx; String
0x18009d103  lea     r8, [rbp+3Fh+Context]; Context
0x18009d107  lea     rdx, asc_1801772AC; ","
0x18009d10e  call    _o_wcstok_s_0
0x18009d113  test    rax, rax
0x18009d116  jnz     short loc_18009D0FB
0x18009d118  mov     rdx, r14
0x18009d11b  jmp     loc_18009CE6C
0x18009d120  mov     rdx, rsi
0x18009d123  movzx   eax, [rbp+3Fh+arg_20]
0x18009d127  xor     r9d, r9d; pwszVersion
0x18009d12a  mov     rcx, [rdi+28h]
0x18009d12e  mov     r8, r13; pwszObjectName
0x18009d131  shl     eax, 17h
0x18009d134  add     eax, 100h
0x18009d139  mov     [rsp+0C0h+dwFlags], eax; dwFlags
0x18009d13d  mov     rcx, [rcx+10h]; hConnect
0x18009d141  mov     [rsp+0C0h+ppwszAcceptTypes], rdx; ppwszAcceptTypes
0x18009d146  mov     rdx, [rbp+3Fh+pwszVerb]; pwszVerb
0x18009d14a  mov     [rsp+0C0h+pwszReferrer], rsi; pwszReferrer
0x18009d14f  call    cs:__imp_WinHttpOpenRequest
0x18009d155  mov     [rdi+18h], rax
0x18009d159  test    rax, rax
0x18009d15c  jnz     loc_18009D203
0x18009d162  call    cs:__imp_GetLastError
0x18009d168  mov     ebx, eax
0x18009d16a  test    eax, eax
0x18009d16c  jle     short loc_18009D177
0x18009d16e  movzx   ebx, ax
0x18009d171  or      ebx, 80070000h
0x18009d177  mov     eax, cs:CallbackContext
0x18009d17d  cmp     eax, 2
0x18009d180  jbe     loc_18009D2CF
0x18009d186  lea     rax, aWinhttpopenreq_0; "WinHttpOpenRequest failed"
0x18009d18d  mov     [rbp+3Fh+arg_30], 347h
0x18009d194  lea     rdx, byte_1801B263B
0x18009d19b  mov     [rbp+3Fh+var_50], rax
0x18009d19f  lea     rax, aInitialize; "Initialize"
0x18009d1a6  mov     [rbp+3Fh+var_58], rax
0x18009d1aa  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdp\\win\\httpio\\win"...
0x18009d1b1  mov     [rbp+3Fh+var_60], rax
0x18009d1b5  lea     rax, aErrorCondition; "Error condition failed"
0x18009d1bc  mov     [rbp+3Fh+var_68], rax
0x18009d1c0  lea     rax, [rbp+3Fh+var_50]
0x18009d1c4  mov     [rsp+0C0h+var_78], rax
0x18009d1c9  lea     rax, [rbp+3Fh+var_58]
0x18009d1cd  mov     [rsp+0C0h+var_80], rax
0x18009d1d2  lea     rax, [rbp+3Fh+arg_30]
0x18009d1d6  mov     [rsp+0C0h+var_88], rax
0x18009d1db  lea     rax, [rbp+3Fh+var_60]
0x18009d1df  mov     qword ptr [rsp+0C0h+dwFlags], rax
0x18009d1e4  lea     rax, [rbp+3Fh+arg_0]
0x18009d1e8  mov     [rsp+0C0h+ppwszAcceptTypes], rax
0x18009d1ed  lea     rax, [rbp+3Fh+var_68]
0x18009d1f1  mov     [rsp+0C0h+pwszReferrer], rax
0x18009d1f6  mov     dword ptr [rbp+3Fh+arg_0], ebx
0x18009d1f9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18009d1fe  jmp     loc_18009D2CF
0x18009d203  xor     r8d, r8d; pcbe
0x18009d206  lea     rcx, ?TpCallback@CHttpIoRequestWinHttp@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18009d20d  mov     rdx, rdi; pv
0x18009d210  call    cs:__imp_CreateThreadpoolWork
0x18009d216  mov     [rdi+70h], rax
0x18009d21a  test    rax, rax
0x18009d21d  jnz     short loc_18009D25D
0x18009d21f  call    cs:__imp_GetLastError
0x18009d225  mov     ebx, eax
0x18009d227  test    eax, eax
0x18009d229  jle     short loc_18009D234
0x18009d22b  movzx   ebx, ax
0x18009d22e  or      ebx, 80070000h
0x18009d234  mov     eax, cs:CallbackContext
0x18009d23a  cmp     eax, 2
0x18009d23d  jbe     loc_18009D2CF
0x18009d243  lea     rax, aCreatethreadpo; "CreateThreadpoolWork failed"
0x18009d24a  mov     [rbp+3Fh+arg_30], 34Eh
0x18009d251  lea     rdx, byte_1801B25EF
0x18009d258  jmp     loc_18009D19B
0x18009d25d  mov     rcx, rdi; this
0x18009d260  mov     [rdi+38h], r12
0x18009d264  mov     [rdi+88h], sil
0x18009d26b  call    ?SetHttpCallback@CHttpIoRequestWinHttp@@AEAA_NXZ; CHttpIoRequestWinHttp::SetHttpCallback(void)
0x18009d270  test    al, al
0x18009d272  jnz     short loc_18009D2B2
0x18009d274  mov     [rdi+38h], rsi
  ... truncated ...
```
