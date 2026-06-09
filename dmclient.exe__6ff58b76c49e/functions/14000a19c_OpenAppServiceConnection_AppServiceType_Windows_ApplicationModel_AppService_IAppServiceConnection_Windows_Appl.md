# OpenAppServiceConnection(AppServiceType,Windows::ApplicationModel::AppService::IAppServiceConnection * *,Windows::ApplicationModel::AppService::AppServiceConnectionStatus *)

- ea: `0x14000a19c`
- end: `0x14000a745`
- name: `?OpenAppServiceConnection@@YAJW4AppServiceType@@PEAPEAUIAppServiceConnection@AppService@ApplicationModel@Windows@@PEAW4AppServiceConnectionStatus@345@@Z`
- size: `1449`
- prototype: `__int64 __fastcall(int, _QWORD *, int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x140005b34`
- `0x140007ff8`

## callees

- `0x1400015fc`
- `0x140004110`
- `0x14000a19c`
- `0x14000a9f0`
- `0x14000bc48`
- `0x1400187e0`
- `0x140019010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000a209`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000a348`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000a461`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000a209`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000a348`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000a461`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x14000a21f`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x14000a21f`

## string_xrefs

- `0x14000a275`: `OpenAppServiceConnection`
- `0x14000a3b6`: `OpenAppServiceConnection`
- `0x14000a4cf`: `OpenAppServiceConnection`
- `0x14000a5df`: `OpenAppServiceConnection`
- `0x14000a202`: `Windows.ApplicationModel.AppService.AppServiceConnection`

## pseudocode

```c
__int64 __fastcall OpenAppServiceConnection(int a1, _QWORD *a2, int *a3)
{
  __int64 v5; // rdi
  HRESULT v6; // eax
  int v7; // edx
  unsigned int v8; // r8d
  __int64 v9; // rdx
  int v10; // ebx
  __int64 v11; // r8
  __int64 v12; // r9
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
  __int64 v25; // r9
  __int64 v26; // rcx
  __int64 *v27; // rcx
  __int64 *v28; // rbx
  __int64 v29; // rdi
  HRESULT v30; // eax
  int v31; // edx
  unsigned int v32; // r8d
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // r9
  __int64 v36; // rcx
  __int64 *v37; // rcx
  __int64 *v38; // rbx
  __int64 (__fastcall *v39)(__int64 *, __int64 *); // rdi
  __int64 v40; // rcx
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 v43; // r9
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
    if ( (unsigned int)dword_140027000 > 2 )
    {
      v11 = qword_140027018;
      v9 = 0x400000000000LL;
      if ( (qword_140027010 & 0x400000000000LL) != 0 && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
      {
        v59 = 0x1000000;
        v55 = 426;
        v60 = "OpenAppServiceConnection";
        v61 = (__int64)"onecore\\base\\diagnosis\\feedback\\siuf\\deploymentmgr\\client\\exe\\main.cpp";
        v57 = v10;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          qword_140027010,
          (__int64)&byte_140020057,
          qword_140027018,
          v12,
          (__int64)&v57,
          (const unsigned __int16 **)&v61,
          (const unsigned __int16 **)&v60,
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
  v18 = off_14001AD10[v5];
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
    if ( (unsigned int)dword_140027000 > 2 )
    {
      v24 = qword_140027018;
      v23 = 0x400000000000LL;
      if ( (qword_140027010 & 0x400000000000LL) != 0 && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
      {
        v61 = 0x1000000;
        v57 = 430;
        v60 = "OpenAppServiceConnection";
        v59 = (__int64)"onecore\\base\\diagnosis\\feedback\\siuf\\deploymentmgr\\client\\exe\\main.cpp";
        v55 = v10;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          qword_140027010,
          (__int64)&word_1400209FE,
          qword_140027018,
          v25,
          (__int64)&v55,
          (const unsigned __int16 **)&v59,
          (const unsigned __int16 **)&v60,
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
    if ( (unsigned int)dword_140027000 > 2 )
    {
      v34 = qword_140027018;
      v33 = 0x400000000000LL;
      if ( (qword_140027010 & 0x400000000000LL) != 0 && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
      {
        v61 = 0x1000000;
        v57 = 432;
        v60 = "OpenAppServiceConnection";
        v59 = (__int64)"onecore\\base\\diagnosis\\feedback\\siuf\\deploymentmgr\\client\\exe\\main.cpp";
        v55 = v10;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          qword_140027010,
          (__int64)byte_140020B13,
          qword_140027018,
          v35,
          (__int64)&v55,
          (const unsigned __int16 **)&v59,
          (const unsigned __int16 **)&v60,
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
    if ( (unsigned int)dword_140027000 > 2 )
    {
      v42 = qword_140027018;
      v41 = 0x400000000000LL;
      if ( (qword_140027010 & 0x400000000000LL) != 0 && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
      {
        v61 = 0x1000000;
        v57 = 433;
        v60 = "OpenAppServiceConnection";
        v59 = (__int64)"onecore\\base\\diagnosis\\feedback\\siuf\\deploymentmgr\\client\\exe\\main.cpp";
        v55 = v10;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          qword_140027010,
          (__int64)&byte_140020ABF,
          qword_140027018,
          v43,
          (__int64)&v55,
          (const unsigned __int16 **)&v59,
          (const unsigned __int16 **)&v60,
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
  v47 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<enum Windows::ApplicationModel::AppService::AppServiceConnectionStatus> *>(
          v58,
          v41,
          v42);
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
0x14000a19c  push    rbp
0x14000a19e  push    rbx
0x14000a19f  push    rsi
0x14000a1a0  push    rdi
0x14000a1a1  push    r12
0x14000a1a3  push    r14
0x14000a1a5  push    r15
0x14000a1a7  lea     rbp, [rsp-27h]
0x14000a1ac  sub     rsp, 0B0h
0x14000a1b3  mov     rax, cs:__security_cookie
0x14000a1ba  xor     rax, rsp
0x14000a1bd  mov     [rbp+57h+var_38], rax
0x14000a1c1  mov     rsi, r8
0x14000a1c4  mov     r14, rdx
0x14000a1c7  xor     r12d, r12d
0x14000a1ca  mov     [rbp+57h+var_88], r12
0x14000a1ce  mov     [rbp+57h+var_78], r12
0x14000a1d2  test    rdx, rdx
0x14000a1d5  jz      loc_14000A6EB
0x14000a1db  test    r8, r8
0x14000a1de  jz      loc_14000A6EB
0x14000a1e4  movsxd  rdi, ecx
0x14000a1e7  cmp     rdi, 2
0x14000a1eb  ja      loc_14000A6EB
0x14000a1f1  mov     [rbp+57h+string], r12
0x14000a1f5  lea     r9, [rbp+57h+string]; string
0x14000a1f9  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x14000a1fd  lea     edx, [r12+38h]; length
0x14000a202  lea     rcx, ?RuntimeClass_Windows_ApplicationModel_AppService_AppServiceConnection@@3QBGB; "Windows.ApplicationModel.AppService.App"...
0x14000a209  call    cs:__imp_WindowsCreateStringReference
0x14000a20f  test    eax, eax
0x14000a211  js      loc_14000A719
0x14000a217  lea     rdx, [rbp+57h+var_88]
0x14000a21b  mov     rcx, [rbp+57h+string]
0x14000a21f  call    cs:__imp_RoActivateInstance
0x14000a225  mov     ebx, eax
0x14000a227  test    eax, eax
0x14000a229  jns     loc_14000A303
0x14000a22f  mov     ecx, cs:dword_140027000
0x14000a235  cmp     ecx, 2
0x14000a238  jbe     loc_14000A2C8
0x14000a23e  mov     r8, cs:qword_140027018
0x14000a245  mov     rcx, cs:qword_140027010
0x14000a24c  mov     rdx, 400000000000h
0x14000a256  test    rdx, rcx
0x14000a259  jz      short loc_14000A2C8
0x14000a25b  mov     rax, r8
0x14000a25e  and     rax, rdx
0x14000a261  cmp     rax, r8
0x14000a264  jnz     short loc_14000A2C8
0x14000a266  mov     [rbp+57h+var_70], 1000000h
0x14000a26e  mov     [rbp+57h+var_90], 1AAh
0x14000a275  lea     rax, aOpenappservice; "OpenAppServiceConnection"
0x14000a27c  mov     [rbp+57h+var_68], rax
0x14000a280  lea     rax, aOnecoreBaseDia; "onecore\\base\\diagnosis\\feedback\\siu"...
0x14000a287  mov     [rbp+57h+var_60], rax
0x14000a28b  mov     [rbp+57h+var_80], ebx
0x14000a28e  lea     rax, [rbp+57h+var_70]
0x14000a292  mov     [rsp+0E0h+var_A0], rax
0x14000a297  lea     rax, [rbp+57h+var_90]
0x14000a29b  mov     [rsp+0E0h+var_A8], rax
0x14000a2a0  lea     rax, [rbp+57h+var_68]
0x14000a2a4  mov     [rsp+0E0h+var_B0], rax
0x14000a2a9  lea     rax, [rbp+57h+var_60]
0x14000a2ad  mov     [rsp+0E0h+var_B8], rax
0x14000a2b2  lea     rax, [rbp+57h+var_80]
0x14000a2b6  mov     [rsp+0E0h+var_C0], rax
0x14000a2bb  lea     rdx, byte_140020057
0x14000a2c2  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@43AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x14000a2c7  nop
0x14000a2c8  mov     rcx, [rbp+57h+var_78]
0x14000a2cc  test    rcx, rcx
0x14000a2cf  jz      short loc_14000A2E2
0x14000a2d1  mov     [rbp+57h+var_78], r12
0x14000a2d5  mov     rax, [rcx]
0x14000a2d8  mov     rax, [rax+10h]
0x14000a2dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a2e1  nop
0x14000a2e2  mov     rcx, [rbp+57h+var_88]
0x14000a2e6  test    rcx, rcx
0x14000a2e9  jz      short loc_14000A2FC
0x14000a2eb  mov     [rbp+57h+var_88], r12
0x14000a2ef  mov     rax, [rcx]
0x14000a2f2  mov     rax, [rax+10h]
0x14000a2f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a2fb  nop
0x14000a2fc  mov     eax, ebx
0x14000a2fe  jmp     loc_14000A6F0
0x14000a303  mov     rbx, [rbp+57h+var_88]
0x14000a307  mov     r15, [rbx]
0x14000a30a  mov     [rbp+57h+string], r12
0x14000a30e  lea     rcx, off_14001AD10; "com.microsoft.feedbackhub.siufservice"
0x14000a315  mov     rcx, [rcx+rdi*8]; sourceString
0x14000a319  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14000a31d  inc     rdx; int
0x14000a320  cmp     [rcx+rdx*2], r12w
0x14000a325  jnz     short loc_14000A31D
0x14000a327  mov     eax, 0FFFFFFFFh
0x14000a32c  cmp     rdx, rax
0x14000a32f  ja      loc_14000A70E
0x14000a335  lea     eax, [rdx+1]
0x14000a338  cmp     eax, edx
0x14000a33a  jb      loc_14000A721
0x14000a340  lea     r9, [rbp+57h+string]; string
0x14000a344  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x14000a348  call    cs:__imp_WindowsCreateStringReference
0x14000a34e  test    eax, eax
0x14000a350  js      loc_14000A72C
0x14000a356  mov     rdx, [rbp+57h+string]
0x14000a35a  mov     rcx, rbx
0x14000a35d  mov     rax, [r15+38h]
0x14000a361  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a366  mov     ebx, eax
0x14000a368  test    eax, eax
0x14000a36a  jns     loc_14000A442
0x14000a370  mov     ecx, cs:dword_140027000
0x14000a376  cmp     ecx, 2
0x14000a379  jbe     loc_14000A409
0x14000a37f  mov     r8, cs:qword_140027018
0x14000a386  mov     rcx, cs:qword_140027010
0x14000a38d  mov     rdx, 400000000000h
0x14000a397  test    rdx, rcx
0x14000a39a  jz      short loc_14000A409
0x14000a39c  mov     rax, r8
0x14000a39f  and     rax, rdx
0x14000a3a2  cmp     rax, r8
0x14000a3a5  jnz     short loc_14000A409
0x14000a3a7  mov     [rbp+57h+var_60], 1000000h
0x14000a3af  mov     [rbp+57h+var_80], 1AEh
0x14000a3b6  lea     rax, aOpenappservice; "OpenAppServiceConnection"
0x14000a3bd  mov     [rbp+57h+var_68], rax
0x14000a3c1  lea     rax, aOnecoreBaseDia; "onecore\\base\\diagnosis\\feedback\\siu"...
0x14000a3c8  mov     [rbp+57h+var_70], rax
0x14000a3cc  mov     [rbp+57h+var_90], ebx
0x14000a3cf  lea     rax, [rbp+57h+var_60]
0x14000a3d3  mov     [rsp+0E0h+var_A0], rax
0x14000a3d8  lea     rax, [rbp+57h+var_80]
0x14000a3dc  mov     [rsp+0E0h+var_A8], rax
0x14000a3e1  lea     rax, [rbp+57h+var_68]
0x14000a3e5  mov     [rsp+0E0h+var_B0], rax
0x14000a3ea  lea     rax, [rbp+57h+var_70]
0x14000a3ee  mov     [rsp+0E0h+var_B8], rax
0x14000a3f3  lea     rax, [rbp+57h+var_90]
0x14000a3f7  mov     [rsp+0E0h+var_C0], rax
0x14000a3fc  lea     rdx, word_1400209FE
0x14000a403  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@43AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x14000a408  nop
0x14000a409  mov     rcx, [rbp+57h+var_78]
0x14000a40d  test    rcx, rcx
0x14000a410  jz      short loc_14000A423
0x14000a412  mov     [rbp+57h+var_78], r12
0x14000a416  mov     rax, [rcx]
0x14000a419  mov     rax, [rax+10h]
0x14000a41d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a422  nop
0x14000a423  mov     rcx, [rbp+57h+var_88]
0x14000a427  test    rcx, rcx
0x14000a42a  jz      short loc_14000A43D
0x14000a42c  mov     [rbp+57h+var_88], r12
0x14000a430  mov     rax, [rcx]
0x14000a433  mov     rax, [rax+10h]
0x14000a437  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a43c  nop
0x14000a43d  jmp     loc_14000A2FC
0x14000a442  mov     rbx, [rbp+57h+var_88]
0x14000a446  mov     rdi, [rbx]
0x14000a449  mov     [rbp+57h+string], r12
0x14000a44d  lea     r9, [rbp+57h+string]; string
0x14000a451  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x14000a455  mov     edx, 2Ah ; '*'; length
0x14000a45a  lea     rcx, aMicrosoftWindo; "Microsoft.WindowsFeedbackHub_8wekyb3d8b"...
0x14000a461  call    cs:__imp_WindowsCreateStringReference
0x14000a467  test    eax, eax
0x14000a469  js      loc_14000A734
0x14000a46f  mov     rdx, [rbp+57h+string]
0x14000a473  mov     rcx, rbx
0x14000a476  mov     rax, [rdi+48h]
0x14000a47a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a47f  mov     ebx, eax
0x14000a481  test    eax, eax
0x14000a483  jns     loc_14000A55B
0x14000a489  mov     ecx, cs:dword_140027000
0x14000a48f  cmp     ecx, 2
0x14000a492  jbe     loc_14000A522
0x14000a498  mov     r8, cs:qword_140027018
0x14000a49f  mov     rcx, cs:qword_140027010
0x14000a4a6  mov     rdx, 400000000000h
0x14000a4b0  test    rdx, rcx
0x14000a4b3  jz      short loc_14000A522
0x14000a4b5  mov     rax, r8
0x14000a4b8  and     rax, rdx
0x14000a4bb  cmp     rax, r8
0x14000a4be  jnz     short loc_14000A522
0x14000a4c0  mov     [rbp+57h+var_60], 1000000h
0x14000a4c8  mov     [rbp+57h+var_80], 1B0h
0x14000a4cf  lea     rax, aOpenappservice; "OpenAppServiceConnection"
0x14000a4d6  mov     [rbp+57h+var_68], rax
0x14000a4da  lea     rax, aOnecoreBaseDia; "onecore\\base\\diagnosis\\feedback\\siu"...
0x14000a4e1  mov     [rbp+57h+var_70], rax
0x14000a4e5  mov     [rbp+57h+var_90], ebx
0x14000a4e8  lea     rax, [rbp+57h+var_60]
0x14000a4ec  mov     [rsp+0E0h+var_A0], rax
0x14000a4f1  lea     rax, [rbp+57h+var_80]
0x14000a4f5  mov     [rsp+0E0h+var_A8], rax
0x14000a4fa  lea     rax, [rbp+57h+var_68]
0x14000a4fe  mov     [rsp+0E0h+var_B0], rax
0x14000a503  lea     rax, [rbp+57h+var_70]
0x14000a507  mov     [rsp+0E0h+var_B8], rax
0x14000a50c  lea     rax, [rbp+57h+var_90]
0x14000a510  mov     [rsp+0E0h+var_C0], rax
0x14000a515  lea     rdx, byte_140020B13
0x14000a51c  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@43AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x14000a521  nop
0x14000a522  mov     rcx, [rbp+57h+var_78]
0x14000a526  test    rcx, rcx
0x14000a529  jz      short loc_14000A53C
0x14000a52b  mov     [rbp+57h+var_78], r12
0x14000a52f  mov     rax, [rcx]
0x14000a532  mov     rax, [rax+10h]
0x14000a536  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a53b  nop
0x14000a53c  mov     rcx, [rbp+57h+var_88]
0x14000a540  test    rcx, rcx
0x14000a543  jz      short loc_14000A556
0x14000a545  mov     [rbp+57h+var_88], r12
0x14000a549  mov     rax, [rcx]
0x14000a54c  mov     rax, [rax+10h]
0x14000a550  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a555  nop
0x14000a556  jmp     loc_14000A2FC
0x14000a55b  mov     rbx, [rbp+57h+var_88]
0x14000a55f  mov     rax, [rbx]
0x14000a562  mov     rdi, [rax+50h]
0x14000a566  mov     rcx, [rbp+57h+var_78]
0x14000a56a  test    rcx, rcx
0x14000a56d  jz      short loc_14000A580
0x14000a56f  mov     [rbp+57h+var_78], r12
0x14000a573  mov     rdx, [rcx]
0x14000a576  mov     rax, [rdx+10h]
0x14000a57a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a57f  nop
0x14000a580  lea     rdx, [rbp+57h+var_78]
0x14000a584  mov     rcx, rbx
0x14000a587  mov     rax, rdi
0x14000a58a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a58f  mov     ebx, eax
0x14000a591  test    eax, eax
0x14000a593  jns     loc_14000A66B
0x14000a599  mov     ecx, cs:dword_140027000
0x14000a59f  cmp     ecx, 2
0x14000a5a2  jbe     loc_14000A632
0x14000a5a8  mov     r8, cs:qword_140027018
0x14000a5af  mov     rcx, cs:qword_140027010
0x14000a5b6  mov     rdx, 400000000000h
0x14000a5c0  test    rdx, rcx
0x14000a5c3  jz      short loc_14000A632
0x14000a5c5  mov     rax, r8
0x14000a5c8  and     rax, rdx
0x14000a5cb  cmp     rax, r8
0x14000a5ce  jnz     short loc_14000A632
0x14000a5d0  mov     [rbp+57h+var_60], 1000000h
0x14000a5d8  mov     [rbp+57h+var_80], 1B1h
0x14000a5df  lea     rax, aOpenappservice; "OpenAppServiceConnection"
0x14000a5e6  mov     [rbp+57h+var_68], rax
0x14000a5ea  lea     rax, aOnecoreBaseDia; "onecore\\base\\diagnosis\\feedback\\siu"...
0x14000a5f1  mov     [rbp+57h+var_70], rax
0x14000a5f5  mov     [rbp+57h+var_90], ebx
0x14000a5f8  lea     rax, [rbp+57h+var_60]
0x14000a5fc  mov     [rsp+0E0h+var_A0], rax
0x14000a601  lea     rax, [rbp+57h+var_80]
0x14000a605  mov     [rsp+0E0h+var_A8], rax
0x14000a60a  lea     rax, [rbp+57h+var_68]
0x14000a60e  mov     [rsp+0E0h+var_B0], rax
0x14000a613  lea     rax, [rbp+57h+var_70]
0x14000a617  mov     [rsp+0E0h+var_B8], rax
0x14000a61c  lea     rax, [rbp+57h+var_90]
0x14000a620  mov     [rsp+0E0h+var_C0], rax
0x14000a625  lea     rdx, byte_140020ABF
0x14000a62c  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@43AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x14000a631  nop
0x14000a632  mov     rcx, [rbp+57h+var_78]
0x14000a636  test    rcx, rcx
0x14000a639  jz      short loc_14000A64C
0x14000a63b  mov     [rbp+57h+var_78], r12
0x14000a63f  mov     rax, [rcx]
0x14000a642  mov     rax, [rax+10h]
0x14000a646  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a64b  nop
0x14000a64c  mov     rcx, [rbp+57h+var_88]
0x14000a650  test    rcx, rcx
0x14000a653  jz      short loc_14000A666
0x14000a655  mov     [rbp+57h+var_88], r12
0x14000a659  mov     rax, [rcx]
0x14000a65c  mov     rax, [rax+10h]
0x14000a660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a665  nop
0x14000a666  jmp     loc_14000A2FC
0x14000a66b  mov     rbx, [rbp+57h+var_78]
0x14000a66f  mov     [rbp+57h+var_90], r12d
0x14000a673  mov     rcx, rbx
  ... truncated ...
```
