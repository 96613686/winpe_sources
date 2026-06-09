# OpenAppServiceConnection(AppServiceType,Windows::ApplicationModel::AppService::IAppServiceConnection * *,Windows::ApplicationModel::AppService::AppServiceConnectionStatus *)

- ea: `0x14000a3c4`
- end: `0x14000a986`
- name: `?OpenAppServiceConnection@@YAJW4AppServiceType@@PEAPEAUIAppServiceConnection@AppService@ApplicationModel@Windows@@PEAW4AppServiceConnectionStatus@345@@Z`
- size: `1474`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x140005bd4`
- `0x1400081c4`

## callees

- `0x140001604`
- `0x140004198`
- `0x14000a3c4`
- `0x14000ac50`
- `0x14000bff0`
- `0x140019610`
- `0x14001a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000a431`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000a57c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000a69b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000a431`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000a57c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000a69b`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x14000a44d`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x14000a44d`

## string_xrefs

- `0x14000a4a9`: `OpenAppServiceConnection`
- `0x14000a5f0`: `OpenAppServiceConnection`
- `0x14000a70f`: `OpenAppServiceConnection`
- `0x14000a81f`: `OpenAppServiceConnection`
- `0x14000a42a`: `Windows.ApplicationModel.AppService.AppServiceConnection`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall OpenAppServiceConnection(int a1, _QWORD *a2, int *a3)
{
  __int64 v5; // rdi
  HRESULT v6; // eax
  int v7; // edx
  unsigned int v8; // r8d
  __int64 v9; // rdx
  int v10; // ebx
  __int64 v11; // r8
  int v12; // r9d
  __int64 v13; // rcx
  __int64 *v14; // rcx
  __int64 *v16; // rbx
  __int64 v17; // r15
  const WCHAR *v18; // rcx
  unsigned __int64 v19; // rdx
  HRESULT v20; // eax
  int v21; // edx
  unsigned int v22; // r8d
  __int64 v23; // rdx
  __int64 v24; // r8
  int v25; // r9d
  __int64 v26; // rcx
  __int64 *v27; // rcx
  __int64 *v28; // rbx
  __int64 v29; // rdi
  HRESULT v30; // eax
  int v31; // edx
  unsigned int v32; // r8d
  __int64 v33; // rdx
  __int64 v34; // r8
  int v35; // r9d
  __int64 v36; // rcx
  __int64 *v37; // rcx
  __int64 *v38; // rbx
  __int64 (__fastcall *v39)(__int64 *, __int64 *); // rdi
  __int64 v40; // rcx
  __int64 v41; // rdx
  __int64 v42; // r8
  int v43; // r9d
  __int64 v44; // rcx
  __int64 *v45; // rcx
  __int64 v46; // rbx
  int v47; // eax
  void *v48; // rdx
  unsigned int v49; // r8d
  int v50; // eax
  __int64 *v51; // rax
  __int64 v52; // rcx
  __int64 *v53; // rcx
  int v54; // [rsp+20h] [rbp-69h]
  int v55; // [rsp+50h] [rbp-39h] BYREF
  __int64 *v56; // [rsp+58h] [rbp-31h] BYREF
  int v57; // [rsp+60h] [rbp-29h] BYREF
  __int64 v58; // [rsp+68h] [rbp-21h] BYREF
  __int64 v59; // [rsp+70h] [rbp-19h] BYREF
  const char *v60; // [rsp+78h] [rbp-11h] BYREF
  __int64 v61; // [rsp+80h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+88h] [rbp-1h] BYREF
  HSTRING string; // [rsp+A0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v56 = 0;
  v58 = 0;
  if ( !a2 )
    return 2147942487LL;
  if ( !a3 )
    return 2147942487LL;
  v5 = a1;
  if ( (unsigned __int64)a1 > 2 )
    return 2147942487LL;
  string = 0;
  v6 = WindowsCreateStringReference(
         L"Windows.ApplicationModel.AppService.AppServiceConnection",
         0x38u,
         &hstringHeader,
         &string);
  if ( v6 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v6, v7, v8);
    __debugbreak();
  }
  v10 = RoActivateInstance(string, &v56);
  if ( v10 < 0 )
  {
    if ( (unsigned int)dword_140028000 > 2 )
    {
      v11 = qword_140028018;
      v9 = 0x400000000000LL;
      if ( (qword_140028010 & 0x400000000000LL) != 0 && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
      {
        v59 = 0x1000000;
        v55 = 426;
        v60 = "OpenAppServiceConnection";
        v61 = (__int64)"onecore\\base\\diagnosis\\feedback\\siuf\\deploymentmgr\\client\\exe\\main.cpp";
        v57 = v10;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          qword_140028010,
          (unsigned int)&byte_14002105F,
          qword_140028018,
          v12,
          (__int64)&v57,
          (__int64)&v61,
          (__int64)&v60,
          (__int64)&v55,
          (__int64)&v59);
      }
    }
    v13 = v58;
    if ( v58 )
    {
      v58 = 0;
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v13 + 16LL))(v13, v9, v11);
    }
    v14 = v56;
    if ( v56 )
    {
      v56 = 0;
      (*(void (__fastcall **)(__int64 *, __int64, __int64))(*v14 + 16))(v14, v9, v11);
    }
    return (unsigned int)v10;
  }
  v16 = v56;
  v17 = *v56;
  string = 0;
  v18 = off_14001BD10[v5];
  v19 = -1;
  do
    ++v19;
  while ( v18[v19] );
  if ( v19 > 0xFFFFFFFF )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v19, v11);
    __debugbreak();
  }
  if ( (int)v19 + 1 < (unsigned int)v19 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v19, v11);
    __debugbreak();
  }
  v20 = WindowsCreateStringReference(v18, v19, &hstringHeader, &string);
  if ( v20 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v20, v21, v22);
    __debugbreak();
  }
  v10 = (*(__int64 (__fastcall **)(__int64 *, HSTRING))(v17 + 56))(v16, string);
  if ( v10 < 0 )
  {
    if ( (unsigned int)dword_140028000 > 2 )
    {
      v24 = qword_140028018;
      v23 = 0x400000000000LL;
      if ( (qword_140028010 & 0x400000000000LL) != 0 && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
      {
        v61 = 0x1000000;
        v57 = 430;
        v60 = "OpenAppServiceConnection";
        v59 = (__int64)"onecore\\base\\diagnosis\\feedback\\siuf\\deploymentmgr\\client\\exe\\main.cpp";
        v55 = v10;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          qword_140028010,
          (unsigned int)&word_140021A06,
          qword_140028018,
          v25,
          (__int64)&v55,
          (__int64)&v59,
          (__int64)&v60,
          (__int64)&v57,
          (__int64)&v61);
      }
    }
    v26 = v58;
    if ( v58 )
    {
      v58 = 0;
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v26 + 16LL))(v26, v23, v24);
    }
    v27 = v56;
    if ( v56 )
    {
      v56 = 0;
      (*(void (__fastcall **)(__int64 *, __int64, __int64))(*v27 + 16))(v27, v23, v24);
    }
    return (unsigned int)v10;
  }
  v28 = v56;
  v29 = *v56;
  string = 0;
  v30 = WindowsCreateStringReference(L"Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe", 0x2Au, &hstringHeader, &string);
  if ( v30 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v30, v31, v32);
    __debugbreak();
  }
  v10 = (*(__int64 (__fastcall **)(__int64 *, HSTRING))(v29 + 72))(v28, string);
  if ( v10 < 0 )
  {
    if ( (unsigned int)dword_140028000 > 2 )
    {
      v34 = qword_140028018;
      v33 = 0x400000000000LL;
      if ( (qword_140028010 & 0x400000000000LL) != 0 && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
      {
        v61 = 0x1000000;
        v57 = 432;
        v60 = "OpenAppServiceConnection";
        v59 = (__int64)"onecore\\base\\diagnosis\\feedback\\siuf\\deploymentmgr\\client\\exe\\main.cpp";
        v55 = v10;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          qword_140028010,
          (unsigned int)byte_140021B1B,
          qword_140028018,
          v35,
          (__int64)&v55,
          (__int64)&v59,
          (__int64)&v60,
          (__int64)&v57,
          (__int64)&v61);
      }
    }
    v36 = v58;
    if ( v58 )
    {
      v58 = 0;
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v36 + 16LL))(v36, v33, v34);
    }
    v37 = v56;
    if ( v56 )
    {
      v56 = 0;
      (*(void (__fastcall **)(__int64 *, __int64, __int64))(*v37 + 16))(v37, v33, v34);
    }
    return (unsigned int)v10;
  }
  v38 = v56;
  v39 = *(__int64 (__fastcall **)(__int64 *, __int64 *))(*v56 + 80);
  v40 = v58;
  if ( v58 )
  {
    v58 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
  }
  v10 = v39(v38, &v58);
  if ( v10 < 0 )
  {
    if ( (unsigned int)dword_140028000 > 2 )
    {
      v42 = qword_140028018;
      v41 = 0x400000000000LL;
      if ( (qword_140028010 & 0x400000000000LL) != 0 && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
      {
        v61 = 0x1000000;
        v57 = 433;
        v60 = "OpenAppServiceConnection";
        v59 = (__int64)"onecore\\base\\diagnosis\\feedback\\siuf\\deploymentmgr\\client\\exe\\main.cpp";
        v55 = v10;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          qword_140028010,
          (unsigned int)&byte_140021AC7,
          qword_140028018,
          v43,
          (__int64)&v55,
          (__int64)&v59,
          (__int64)&v60,
          (__int64)&v57,
          (__int64)&v61);
      }
    }
    v44 = v58;
    if ( v58 )
    {
      v58 = 0;
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v44 + 16LL))(v44, v41, v42);
    }
    v45 = v56;
    if ( v56 )
    {
      v56 = 0;
      (*(void (__fastcall **)(__int64 *, __int64, __int64))(*v45 + 16))(v45, v41, v42);
    }
    return (unsigned int)v10;
  }
  v46 = v58;
  v55 = 0;
  v47 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<enum Windows::ApplicationModel::AppService::AppServiceConnectionStatus> *>(v58);
  if ( v47 >= 0 )
    v47 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v46 + 64LL))(v46, &v55);
  if ( v47 < 0 )
    wil::details::in1diag3::_Throw_Hr(retaddr, v48, v49, (const char *)(unsigned int)v47, v54);
  v50 = v55;
  *a3 = v55;
  if ( !v50 )
  {
    v51 = v56;
    v56 = 0;
    *a2 = v51;
  }
  v52 = v58;
  if ( v58 )
  {
    v58 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
  }
  v53 = v56;
  if ( v56 )
  {
    v56 = 0;
    (*(void (__fastcall **)(__int64 *))(*v53 + 16))(v53);
  }
  return 0;
}

```

## disassembly

```asm
0x14000a3c4  push    rbp
0x14000a3c6  push    rbx
0x14000a3c7  push    rsi
0x14000a3c8  push    rdi
0x14000a3c9  push    r12
0x14000a3cb  push    r14
0x14000a3cd  push    r15
0x14000a3cf  lea     rbp, [rsp-27h]
0x14000a3d4  sub     rsp, 0B0h
0x14000a3db  mov     rax, cs:__security_cookie
0x14000a3e2  xor     rax, rsp
0x14000a3e5  mov     [rbp+57h+var_38], rax
0x14000a3e9  mov     rsi, r8
0x14000a3ec  mov     r14, rdx
0x14000a3ef  xor     r12d, r12d
0x14000a3f2  mov     [rbp+57h+var_88], r12
0x14000a3f6  mov     [rbp+57h+var_78], r12
0x14000a3fa  test    rdx, rdx
0x14000a3fd  jz      loc_14000A92B
0x14000a403  test    r8, r8
0x14000a406  jz      loc_14000A92B
0x14000a40c  movsxd  rdi, ecx
0x14000a40f  cmp     rdi, 2
0x14000a413  ja      loc_14000A92B
0x14000a419  mov     [rbp+57h+string], r12
0x14000a41d  lea     r9, [rbp+57h+string]; string
0x14000a421  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x14000a425  lea     edx, [r12+38h]; length
0x14000a42a  lea     rcx, ?RuntimeClass_Windows_ApplicationModel_AppService_AppServiceConnection@@3QBGB; "Windows.ApplicationModel.AppService.App"...
0x14000a431  call    cs:__imp_WindowsCreateStringReference
0x14000a438  nop     dword ptr [rax+rax+00h]
0x14000a43d  test    eax, eax
0x14000a43f  js      loc_14000A95A
0x14000a445  lea     rdx, [rbp+57h+var_88]
0x14000a449  mov     rcx, [rbp+57h+string]
0x14000a44d  call    cs:__imp_RoActivateInstance
0x14000a454  nop     dword ptr [rax+rax+00h]
0x14000a459  mov     ebx, eax
0x14000a45b  test    eax, eax
0x14000a45d  jns     loc_14000A537
0x14000a463  mov     ecx, cs:dword_140028000
0x14000a469  cmp     ecx, 2
0x14000a46c  jbe     loc_14000A4FC
0x14000a472  mov     r8, cs:qword_140028018
0x14000a479  mov     rcx, cs:qword_140028010
0x14000a480  mov     rdx, 400000000000h
0x14000a48a  test    rdx, rcx
0x14000a48d  jz      short loc_14000A4FC
0x14000a48f  mov     rax, r8
0x14000a492  and     rax, rdx
0x14000a495  cmp     rax, r8
0x14000a498  jnz     short loc_14000A4FC
0x14000a49a  mov     [rbp+57h+var_70], 1000000h
0x14000a4a2  mov     [rbp+57h+var_90], 1AAh
0x14000a4a9  lea     rax, aOpenappservice; "OpenAppServiceConnection"
0x14000a4b0  mov     [rbp+57h+var_68], rax
0x14000a4b4  lea     rax, aOnecoreBaseDia; "onecore\\base\\diagnosis\\feedback\\siu"...
0x14000a4bb  mov     [rbp+57h+var_60], rax
0x14000a4bf  mov     [rbp+57h+var_80], ebx
0x14000a4c2  lea     rax, [rbp+57h+var_70]
0x14000a4c6  mov     [rsp+0E0h+var_A0], rax
0x14000a4cb  lea     rax, [rbp+57h+var_90]
0x14000a4cf  mov     [rsp+0E0h+var_A8], rax
0x14000a4d4  lea     rax, [rbp+57h+var_68]
0x14000a4d8  mov     [rsp+0E0h+var_B0], rax
0x14000a4dd  lea     rax, [rbp+57h+var_60]
0x14000a4e1  mov     [rsp+0E0h+var_B8], rax
0x14000a4e6  lea     rax, [rbp+57h+var_80]
0x14000a4ea  mov     [rsp+0E0h+var_C0], rax
0x14000a4ef  lea     rdx, byte_14002105F
0x14000a4f6  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@43AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x14000a4fb  nop
0x14000a4fc  mov     rcx, [rbp+57h+var_78]
0x14000a500  test    rcx, rcx
0x14000a503  jz      short loc_14000A516
0x14000a505  mov     [rbp+57h+var_78], r12
0x14000a509  mov     rax, [rcx]
0x14000a50c  mov     rax, [rax+10h]
0x14000a510  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a515  nop
0x14000a516  mov     rcx, [rbp+57h+var_88]
0x14000a51a  test    rcx, rcx
0x14000a51d  jz      short loc_14000A530
0x14000a51f  mov     [rbp+57h+var_88], r12
0x14000a523  mov     rax, [rcx]
0x14000a526  mov     rax, [rax+10h]
0x14000a52a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a52f  nop
0x14000a530  mov     eax, ebx
0x14000a532  jmp     loc_14000A930
0x14000a537  mov     rbx, [rbp+57h+var_88]
0x14000a53b  mov     r15, [rbx]
0x14000a53e  mov     [rbp+57h+string], r12
0x14000a542  lea     rcx, off_14001BD10; "com.microsoft.feedbackhub.siufservice"
0x14000a549  mov     rcx, [rcx+rdi*8]; sourceString
0x14000a54d  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14000a551  inc     rdx; int
0x14000a554  cmp     [rcx+rdx*2], r12w
0x14000a559  jnz     short loc_14000A551
0x14000a55b  mov     eax, 0FFFFFFFFh
0x14000a560  cmp     rdx, rax
0x14000a563  ja      loc_14000A94F
0x14000a569  lea     eax, [rdx+1]
0x14000a56c  cmp     eax, edx
0x14000a56e  jb      loc_14000A962
0x14000a574  lea     r9, [rbp+57h+string]; string
0x14000a578  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x14000a57c  call    cs:__imp_WindowsCreateStringReference
0x14000a583  nop     dword ptr [rax+rax+00h]
0x14000a588  test    eax, eax
0x14000a58a  js      loc_14000A96D
0x14000a590  mov     rdx, [rbp+57h+string]
0x14000a594  mov     rcx, rbx
0x14000a597  mov     rax, [r15+38h]
0x14000a59b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a5a0  mov     ebx, eax
0x14000a5a2  test    eax, eax
0x14000a5a4  jns     loc_14000A67C
0x14000a5aa  mov     ecx, cs:dword_140028000
0x14000a5b0  cmp     ecx, 2
0x14000a5b3  jbe     loc_14000A643
0x14000a5b9  mov     r8, cs:qword_140028018
0x14000a5c0  mov     rcx, cs:qword_140028010
0x14000a5c7  mov     rdx, 400000000000h
0x14000a5d1  test    rdx, rcx
0x14000a5d4  jz      short loc_14000A643
0x14000a5d6  mov     rax, r8
0x14000a5d9  and     rax, rdx
0x14000a5dc  cmp     rax, r8
0x14000a5df  jnz     short loc_14000A643
0x14000a5e1  mov     [rbp+57h+var_60], 1000000h
0x14000a5e9  mov     [rbp+57h+var_80], 1AEh
0x14000a5f0  lea     rax, aOpenappservice; "OpenAppServiceConnection"
0x14000a5f7  mov     [rbp+57h+var_68], rax
0x14000a5fb  lea     rax, aOnecoreBaseDia; "onecore\\base\\diagnosis\\feedback\\siu"...
0x14000a602  mov     [rbp+57h+var_70], rax
0x14000a606  mov     [rbp+57h+var_90], ebx
0x14000a609  lea     rax, [rbp+57h+var_60]
0x14000a60d  mov     [rsp+0E0h+var_A0], rax
0x14000a612  lea     rax, [rbp+57h+var_80]
0x14000a616  mov     [rsp+0E0h+var_A8], rax
0x14000a61b  lea     rax, [rbp+57h+var_68]
0x14000a61f  mov     [rsp+0E0h+var_B0], rax
0x14000a624  lea     rax, [rbp+57h+var_70]
0x14000a628  mov     [rsp+0E0h+var_B8], rax
0x14000a62d  lea     rax, [rbp+57h+var_90]
0x14000a631  mov     [rsp+0E0h+var_C0], rax
0x14000a636  lea     rdx, word_140021A06
0x14000a63d  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@43AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x14000a642  nop
0x14000a643  mov     rcx, [rbp+57h+var_78]
0x14000a647  test    rcx, rcx
0x14000a64a  jz      short loc_14000A65D
0x14000a64c  mov     [rbp+57h+var_78], r12
0x14000a650  mov     rax, [rcx]
0x14000a653  mov     rax, [rax+10h]
0x14000a657  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a65c  nop
0x14000a65d  mov     rcx, [rbp+57h+var_88]
0x14000a661  test    rcx, rcx
0x14000a664  jz      short loc_14000A677
0x14000a666  mov     [rbp+57h+var_88], r12
0x14000a66a  mov     rax, [rcx]
0x14000a66d  mov     rax, [rax+10h]
0x14000a671  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a676  nop
0x14000a677  jmp     loc_14000A530
0x14000a67c  mov     rbx, [rbp+57h+var_88]
0x14000a680  mov     rdi, [rbx]
0x14000a683  mov     [rbp+57h+string], r12
0x14000a687  lea     r9, [rbp+57h+string]; string
0x14000a68b  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x14000a68f  mov     edx, 2Ah ; '*'; length
0x14000a694  lea     rcx, aMicrosoftWindo; "Microsoft.WindowsFeedbackHub_8wekyb3d8b"...
0x14000a69b  call    cs:__imp_WindowsCreateStringReference
0x14000a6a2  nop     dword ptr [rax+rax+00h]
0x14000a6a7  test    eax, eax
0x14000a6a9  js      loc_14000A975
0x14000a6af  mov     rdx, [rbp+57h+string]
0x14000a6b3  mov     rcx, rbx
0x14000a6b6  mov     rax, [rdi+48h]
0x14000a6ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a6bf  mov     ebx, eax
0x14000a6c1  test    eax, eax
0x14000a6c3  jns     loc_14000A79B
0x14000a6c9  mov     ecx, cs:dword_140028000
0x14000a6cf  cmp     ecx, 2
0x14000a6d2  jbe     loc_14000A762
0x14000a6d8  mov     r8, cs:qword_140028018
0x14000a6df  mov     rcx, cs:qword_140028010
0x14000a6e6  mov     rdx, 400000000000h
0x14000a6f0  test    rdx, rcx
0x14000a6f3  jz      short loc_14000A762
0x14000a6f5  mov     rax, r8
0x14000a6f8  and     rax, rdx
0x14000a6fb  cmp     rax, r8
0x14000a6fe  jnz     short loc_14000A762
0x14000a700  mov     [rbp+57h+var_60], 1000000h
0x14000a708  mov     [rbp+57h+var_80], 1B0h
0x14000a70f  lea     rax, aOpenappservice; "OpenAppServiceConnection"
0x14000a716  mov     [rbp+57h+var_68], rax
0x14000a71a  lea     rax, aOnecoreBaseDia; "onecore\\base\\diagnosis\\feedback\\siu"...
0x14000a721  mov     [rbp+57h+var_70], rax
0x14000a725  mov     [rbp+57h+var_90], ebx
0x14000a728  lea     rax, [rbp+57h+var_60]
0x14000a72c  mov     [rsp+0E0h+var_A0], rax
0x14000a731  lea     rax, [rbp+57h+var_80]
0x14000a735  mov     [rsp+0E0h+var_A8], rax
0x14000a73a  lea     rax, [rbp+57h+var_68]
0x14000a73e  mov     [rsp+0E0h+var_B0], rax
0x14000a743  lea     rax, [rbp+57h+var_70]
0x14000a747  mov     [rsp+0E0h+var_B8], rax
0x14000a74c  lea     rax, [rbp+57h+var_90]
0x14000a750  mov     [rsp+0E0h+var_C0], rax
0x14000a755  lea     rdx, byte_140021B1B
0x14000a75c  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@43AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x14000a761  nop
0x14000a762  mov     rcx, [rbp+57h+var_78]
0x14000a766  test    rcx, rcx
0x14000a769  jz      short loc_14000A77C
0x14000a76b  mov     [rbp+57h+var_78], r12
0x14000a76f  mov     rax, [rcx]
0x14000a772  mov     rax, [rax+10h]
0x14000a776  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a77b  nop
0x14000a77c  mov     rcx, [rbp+57h+var_88]
0x14000a780  test    rcx, rcx
0x14000a783  jz      short loc_14000A796
0x14000a785  mov     [rbp+57h+var_88], r12
0x14000a789  mov     rax, [rcx]
0x14000a78c  mov     rax, [rax+10h]
0x14000a790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a795  nop
0x14000a796  jmp     loc_14000A530
0x14000a79b  mov     rbx, [rbp+57h+var_88]
0x14000a79f  mov     rax, [rbx]
0x14000a7a2  mov     rdi, [rax+50h]
0x14000a7a6  mov     rcx, [rbp+57h+var_78]
0x14000a7aa  test    rcx, rcx
0x14000a7ad  jz      short loc_14000A7C0
0x14000a7af  mov     [rbp+57h+var_78], r12
0x14000a7b3  mov     rdx, [rcx]
0x14000a7b6  mov     rax, [rdx+10h]
0x14000a7ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a7bf  nop
0x14000a7c0  lea     rdx, [rbp+57h+var_78]
0x14000a7c4  mov     rcx, rbx
0x14000a7c7  mov     rax, rdi
0x14000a7ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a7cf  mov     ebx, eax
0x14000a7d1  test    eax, eax
0x14000a7d3  jns     loc_14000A8AB
0x14000a7d9  mov     ecx, cs:dword_140028000
0x14000a7df  cmp     ecx, 2
0x14000a7e2  jbe     loc_14000A872
0x14000a7e8  mov     r8, cs:qword_140028018
0x14000a7ef  mov     rcx, cs:qword_140028010
0x14000a7f6  mov     rdx, 400000000000h
0x14000a800  test    rdx, rcx
0x14000a803  jz      short loc_14000A872
0x14000a805  mov     rax, r8
0x14000a808  and     rax, rdx
0x14000a80b  cmp     rax, r8
0x14000a80e  jnz     short loc_14000A872
0x14000a810  mov     [rbp+57h+var_60], 1000000h
0x14000a818  mov     [rbp+57h+var_80], 1B1h
0x14000a81f  lea     rax, aOpenappservice; "OpenAppServiceConnection"
0x14000a826  mov     [rbp+57h+var_68], rax
0x14000a82a  lea     rax, aOnecoreBaseDia; "onecore\\base\\diagnosis\\feedback\\siu"...
0x14000a831  mov     [rbp+57h+var_70], rax
0x14000a835  mov     [rbp+57h+var_90], ebx
0x14000a838  lea     rax, [rbp+57h+var_60]
0x14000a83c  mov     [rsp+0E0h+var_A0], rax
0x14000a841  lea     rax, [rbp+57h+var_80]
0x14000a845  mov     [rsp+0E0h+var_A8], rax
0x14000a84a  lea     rax, [rbp+57h+var_68]
0x14000a84e  mov     [rsp+0E0h+var_B0], rax
0x14000a853  lea     rax, [rbp+57h+var_70]
0x14000a857  mov     [rsp+0E0h+var_B8], rax
0x14000a85c  lea     rax, [rbp+57h+var_90]
0x14000a860  mov     [rsp+0E0h+var_C0], rax
0x14000a865  lea     rdx, byte_140021AC7
0x14000a86c  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@43AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x14000a871  nop
0x14000a872  mov     rcx, [rbp+57h+var_78]
0x14000a876  test    rcx, rcx
0x14000a879  jz      short loc_14000A88C
0x14000a87b  mov     [rbp+57h+var_78], r12
0x14000a87f  mov     rax, [rcx]
0x14000a882  mov     rax, [rax+10h]
0x14000a886  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a88b  nop
0x14000a88c  mov     rcx, [rbp+57h+var_88]
0x14000a890  test    rcx, rcx
0x14000a893  jz      short loc_14000A8A6
0x14000a895  mov     [rbp+57h+var_88], r12
0x14000a899  mov     rax, [rcx]
0x14000a89c  mov     rax, [rax+10h]
0x14000a8a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a8a5  nop
  ... truncated ...
```
