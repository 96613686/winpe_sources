# ProcessAccount

- ea: `0x1800acd98`
- end: `0x1800ad31d`
- name: `ProcessAccount`
- size: `1413`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800ad324`

## callees

- `0x1800084f4`
- `0x180012c7c`
- `0x1800318e8`
- `0x180031a20`
- `0x180044300`
- `0x180046ae8`
- `0x180046b3c`
- `0x1800abc0c`
- `0x1800ac3d0`
- `0x1800acd98`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ace23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ace62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800acf38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad2a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad2b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad2c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ace23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ace62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800acf38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad2a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad2b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad2c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ad047`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ad056`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ad065`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ad09c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ad0ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ad0ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ad214`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ad223`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ad232`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ad269`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ad278`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ad287`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ad047`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ad056`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ad065`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ad09c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ad0ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ad0ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ad214`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ad223`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ad232`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ad269`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ad278`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ad287`

## string_xrefs

- `0x1800ace08`: `ComPtr<IWebAccount>::As`
- `0x1800ad104`: `ITokenBrokerInternalStatics::DeleteAccountAsync`
- `0x1800ad126`: `WaitForCompletion`
- `0x1800ad1d0`: `Remove account result: 0x%08x.\n`
- `0x1800ad1e6`: `Remove account result: 0x%08x.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall ProcessAccount(__int64 a1, __int64 (__fastcall ****a2)(_QWORD, GUID *, __int64), char a3)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  int v8; // r14d
  _BYTE **CurrentRef; // rax
  const wchar_t *v10; // rsi
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, HSTRING *); // rbx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 (__fastcall ***v15)(_QWORD, GUID *, __int64); // rdi
  __int64 (__fastcall *v16)(_QWORD, GUID *, __int64); // rbx
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, __int64 *); // rbx
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rdi
  int (__fastcall *v24)(__int64, __int64, _BYTE *); // rbx
  char v25; // si
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // rdi
  __int64 (__fastcall *v29)(__int64, __int64, HSTRING *); // rbx
  __int64 v30; // rdx
  __int64 v31; // rcx
  _QWORD *v32; // rax
  __int64 v33; // rdx
  _QWORD *v34; // rax
  __int64 v35; // rdx
  __int64 v36; // rax
  __int64 v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // rdx
  __int64 v40; // rcx
  PCWSTR StringRawBuffer; // rsi
  PCWSTR v42; // rdi
  PCWSTR v43; // rbx
  __int64 v44; // rdx
  __int64 v45; // rcx
  __int64 v46; // rax
  PCWSTR v47; // rdi
  PCWSTR v48; // rbx
  PCWSTR v49; // rax
  __int64 (__fastcall *v50)(__int64, _QWORD, _QWORD); // rbx
  __int64 v51; // rdx
  __int64 v52; // rcx
  __int64 v53; // r8
  _BYTE **v54; // rax
  const wchar_t *v55; // r12
  __int64 v56; // rdx
  __int64 v57; // rcx
  _QWORD *v58; // rax
  __int64 v59; // rdx
  _QWORD *v60; // rax
  __int64 v61; // rdx
  __int64 v62; // rax
  _QWORD *v63; // rax
  __int64 v64; // rdx
  _QWORD *v65; // rax
  __int64 v66; // rcx
  __int64 v67; // rax
  PCWSTR v68; // rsi
  PCWSTR v69; // rdi
  PCWSTR v70; // rbx
  __int64 v71; // rdx
  __int64 v72; // rcx
  __int64 v73; // rax
  PCWSTR v74; // rdi
  PCWSTR v75; // rbx
  PCWSTR v76; // rax
  __int64 v78; // [rsp+20h] [rbp-59h]
  _BYTE v79[8]; // [rsp+30h] [rbp-49h] BYREF
  HSTRING v80; // [rsp+38h] [rbp-41h] BYREF
  HSTRING v81; // [rsp+40h] [rbp-39h] BYREF
  HSTRING string; // [rsp+48h] [rbp-31h] BYREF
  __int64 v83; // [rsp+50h] [rbp-29h] BYREF
  int (__fastcall ***v84)(_QWORD, GUID *, __int64 *); // [rsp+58h] [rbp-21h] BYREF
  __int64 v85; // [rsp+60h] [rbp-19h] BYREF
  int v86; // [rsp+68h] [rbp-11h]
  __int64 (__fastcall ****v87)(_QWORD, GUID *, __int64); // [rsp+70h] [rbp-9h]
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp-1h] BYREF
  __int64 v89; // [rsp+90h] [rbp+17h]

  v87 = a2;
  v86 = 0;
  v85 = 0;
  v84 = 0;
  v83 = 0;
  string = 0;
  v81 = 0;
  v80 = 0;
  v79[0] = 0;
  v8 = Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::As<Windows::Security::Credentials::IWebAccount2>(
         a2,
         (__int64)&v85);
  if ( v8 < 0 )
  {
    CurrentRef = (_BYTE **)CmdOptions::GetCurrentRef(v7, v6);
    v10 = L"ComPtr<IWebAccount>::As";
LABEL_15:
    if ( **CurrentRef )
    {
      wprintf(L"%s: %s failed with error code: 0x%08x.\n", L"ProcessAccount", v10, (unsigned int)v8);
      v32 = (_QWORD *)CmdOptions::GetCurrentRef(v31, v30);
      if ( *(_BYTE *)(*v32 + 12LL) )
      {
        v34 = (_QWORD *)CmdOptions::GetCurrentRef(*v32, v33);
        if ( *(_QWORD *)(*v34 + 184LL) )
        {
          v36 = CmdOptions::GetCurrentRef(*v34, v35);
          fwprintf_s(
            *(FILE *const *)(*(_QWORD *)v36 + 184LL),
            L"%s: %s failed with error code: 0x%08x.\n",
            L"ProcessAccount",
            v10,
            v8);
        }
      }
    }
    Logger::TraceError(L"%s: %s failed with error code: 0x%08x.\n", L"ProcessAccount", v10, (unsigned int)v8);
    if ( a3 )
      goto LABEL_34;
    goto LABEL_42;
  }
  v11 = v85;
  v12 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v85 + 48LL);
  WindowsDeleteString(string);
  string = 0;
  v8 = v12(v11, &string);
  if ( v8 < 0 )
  {
    CurrentRef = (_BYTE **)CmdOptions::GetCurrentRef(v14, v13);
    v10 = L"IWebAccount2::get_Id";
    goto LABEL_15;
  }
  v15 = *a2;
  v16 = (**a2)[7];
  WindowsDeleteString(v81);
  v81 = 0;
  v8 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), HSTRING *))v16)(v15, &v81);
  if ( v8 < 0 )
  {
    CurrentRef = (_BYTE **)CmdOptions::GetCurrentRef(v18, v17);
    v10 = L"IWebAccount::get_UserName";
    goto LABEL_15;
  }
  v19 = v85;
  v20 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v85 + 56LL);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v83);
  v8 = v20(v19, &v83);
  if ( v8 < 0 )
  {
    CurrentRef = (_BYTE **)CmdOptions::GetCurrentRef(v22, v21);
    v10 = L"IWebAccount2::get_Properties";
    goto LABEL_15;
  }
  v23 = v83;
  v24 = *(int (__fastcall **)(__int64, __int64, _BYTE *))(*(_QWORD *)v83 + 64LL);
  v89 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Authority", 0xAu, 9u);
  v25 = 1;
  v86 = 1;
  if ( v24(v23, v89, v79) < 0 || !v79[0] )
    v25 = 0;
  if ( v25 )
  {
    v28 = v83;
    v29 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)v83 + 48LL);
    WindowsDeleteString(v80);
    v80 = 0;
    v89 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Authority", 0xAu, 9u);
    v8 = v29(v28, v89, &v80);
    if ( v8 < 0 )
    {
      CurrentRef = (_BYTE **)CmdOptions::GetCurrentRef(v27, v26);
      v10 = L"IMapView::Lookup";
      goto LABEL_15;
    }
  }
  v40 = *(_QWORD *)CmdOptions::GetCurrentRef(v27, v26);
  if ( a3 )
  {
    if ( *(_BYTE *)(v40 + 12) && *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef(v40, v39) + 184LL) )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(v80, 0);
      v42 = WindowsGetStringRawBuffer(v81, 0);
      v43 = WindowsGetStringRawBuffer(string, 0);
      v46 = CmdOptions::GetCurrentRef(v45, v44);
      fwprintf_s(
        *(FILE *const *)(*(_QWORD *)v46 + 184LL),
        L"Removing account: %s, user: %s, authority: %s.\n",
        v43,
        v42,
        StringRawBuffer);
    }
    v47 = WindowsGetStringRawBuffer(v80, 0);
    v48 = WindowsGetStringRawBuffer(v81, 0);
    v49 = WindowsGetStringRawBuffer(string, 0);
    wprintf(L"Removing account: %s, user: %s, authority: %s.\n", v49, v48, v47);
    v50 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)a1 + 120LL);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v84);
    v8 = v50(a1, *a2, &v84);
    if ( v8 >= 0 )
    {
      v8 = WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(
             v84,
             v51,
             v53);
      if ( v8 >= 0 )
      {
LABEL_34:
        v63 = (_QWORD *)CmdOptions::GetCurrentRef(v38, v37);
        if ( *(_BYTE *)(*v63 + 12LL) )
        {
          v65 = (_QWORD *)CmdOptions::GetCurrentRef(*v63, v64);
          if ( *(_QWORD *)(*v65 + 184LL) )
          {
            v67 = CmdOptions::GetCurrentRef(v66, *v65);
            fwprintf_s(*(FILE *const *)(*(_QWORD *)v67 + 184LL), L"Remove account result: 0x%08x.\n", (unsigned int)v8);
          }
        }
        wprintf(L"Remove account result: 0x%08x.\n", (unsigned int)v8);
        goto LABEL_42;
      }
      v54 = (_BYTE **)CmdOptions::GetCurrentRef(v38, v37);
      v55 = L"WaitForCompletion";
    }
    else
    {
      v54 = (_BYTE **)CmdOptions::GetCurrentRef(v52, v51);
      v55 = L"ITokenBrokerInternalStatics::DeleteAccountAsync";
    }
    if ( **v54 )
    {
      wprintf(L"%s: %s failed with error code: 0x%08x.\n", L"ProcessAccount", v55, (unsigned int)v8);
      v58 = (_QWORD *)CmdOptions::GetCurrentRef(v57, v56);
      if ( *(_BYTE *)(*v58 + 12LL) )
      {
        v60 = (_QWORD *)CmdOptions::GetCurrentRef(*v58, v59);
        if ( *(_QWORD *)(*v60 + 184LL) )
        {
          v62 = CmdOptions::GetCurrentRef(*v60, v61);
          LODWORD(v78) = v8;
          fwprintf_s(
            *(FILE *const *)(*(_QWORD *)v62 + 184LL),
            L"%s: %s failed with error code: 0x%08x.\n",
            L"ProcessAccount",
            v55,
            v78);
        }
      }
    }
    Logger::TraceError(L"%s: %s failed with error code: 0x%08x.\n", L"ProcessAccount", v55, (unsigned int)v8);
    goto LABEL_34;
  }
  if ( *(_BYTE *)(v40 + 12) && *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef(v40, v39) + 184LL) )
  {
    v68 = WindowsGetStringRawBuffer(v80, 0);
    v69 = WindowsGetStringRawBuffer(v81, 0);
    v70 = WindowsGetStringRawBuffer(string, 0);
    v73 = CmdOptions::GetCurrentRef(v72, v71);
    fwprintf_s(*(FILE *const *)(*(_QWORD *)v73 + 184LL), L"Account: %s, user: %s, authority: %s.\n", v70, v69, v68);
  }
  v74 = WindowsGetStringRawBuffer(v80, 0);
  v75 = WindowsGetStringRawBuffer(v81, 0);
  v76 = WindowsGetStringRawBuffer(string, 0);
  wprintf(L"Account: %s, user: %s, authority: %s.\n", v76, v75, v74);
LABEL_42:
  WindowsDeleteString(v80);
  v80 = 0;
  WindowsDeleteString(v81);
  v81 = 0;
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v83);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v84);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v85);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(a2);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800acd98  mov     [rsp-8+arg_10], rbx
0x1800acd9d  push    rbp
0x1800acd9e  push    rsi
0x1800acd9f  push    rdi
0x1800acda0  push    r12
0x1800acda2  push    r13
0x1800acda4  push    r14
0x1800acda6  push    r15
0x1800acda8  lea     rbp, [rsp-27h]
0x1800acdad  sub     rsp, 0A0h
0x1800acdb4  mov     rax, cs:__security_cookie
0x1800acdbb  xor     rax, rsp
0x1800acdbe  mov     [rbp+57h+var_38], rax
0x1800acdc2  mov     r12b, r8b
0x1800acdc5  mov     r15, rdx
0x1800acdc8  mov     r13, rcx
0x1800acdcb  mov     [rbp+57h+var_60], rdx
0x1800acdcf  xor     esi, esi
0x1800acdd1  mov     [rbp+57h+var_68], esi
0x1800acdd4  mov     [rbp+57h+var_70], rsi
0x1800acdd8  mov     [rbp+57h+var_78], rsi
0x1800acddc  mov     [rbp+57h+var_80], rsi
0x1800acde0  mov     [rbp+57h+string], rsi
0x1800acde4  mov     [rbp+57h+var_90], rsi
0x1800acde8  mov     [rbp+57h+var_98], rsi
0x1800acdec  mov     [rbp+57h+var_A0], sil
0x1800acdf0  lea     rdx, [rbp+57h+var_70]
0x1800acdf4  mov     rcx, r15
0x1800acdf7  call    ??$As@UIWebAccount2@Credentials@Security@Windows@@@?$ComPtr@UIWebAccount@Credentials@Security@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWebAccount2@Credentials@Security@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::As<Windows::Security::Credentials::IWebAccount2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount2>>)
0x1800acdfc  mov     r14d, eax
0x1800acdff  test    eax, eax
0x1800ace01  jns     short loc_1800ACE14
0x1800ace03  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800ace08  lea     rsi, aComptrIwebacco_0; "ComPtr<IWebAccount>::As"
0x1800ace0f  jmp     loc_1800ACF8B
0x1800ace14  mov     rdi, [rbp+57h+var_70]
0x1800ace18  mov     rax, [rdi]
0x1800ace1b  mov     rbx, [rax+30h]
0x1800ace1f  mov     rcx, [rbp+57h+string]; string
0x1800ace23  call    cs:__imp_WindowsDeleteString
0x1800ace29  mov     [rbp+57h+string], rsi
0x1800ace2d  lea     rdx, [rbp+57h+string]
0x1800ace31  mov     rcx, rdi
0x1800ace34  mov     rax, rbx
0x1800ace37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ace3c  mov     r14d, eax
0x1800ace3f  test    eax, eax
0x1800ace41  jns     short loc_1800ACE54
0x1800ace43  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800ace48  lea     rsi, aIwebaccount2Ge; "IWebAccount2::get_Id"
0x1800ace4f  jmp     loc_1800ACF8B
0x1800ace54  mov     rdi, [r15]
0x1800ace57  mov     rax, [rdi]
0x1800ace5a  mov     rbx, [rax+38h]
0x1800ace5e  mov     rcx, [rbp+57h+var_90]; string
0x1800ace62  call    cs:__imp_WindowsDeleteString
0x1800ace68  mov     [rbp+57h+var_90], rsi
0x1800ace6c  lea     rdx, [rbp+57h+var_90]
0x1800ace70  mov     rcx, rdi
0x1800ace73  mov     rax, rbx
0x1800ace76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ace7b  mov     r14d, eax
0x1800ace7e  test    eax, eax
0x1800ace80  jns     short loc_1800ACE93
0x1800ace82  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800ace87  lea     rsi, aIwebaccountGet; "IWebAccount::get_UserName"
0x1800ace8e  jmp     loc_1800ACF8B
0x1800ace93  mov     rdi, [rbp+57h+var_70]
0x1800ace97  mov     rax, [rdi]
0x1800ace9a  mov     rbx, [rax+38h]
0x1800ace9e  lea     rcx, [rbp+57h+var_80]
0x1800acea2  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800acea7  lea     rdx, [rbp+57h+var_80]
0x1800aceab  mov     rcx, rdi
0x1800aceae  mov     rax, rbx
0x1800aceb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aceb6  mov     r14d, eax
0x1800aceb9  test    eax, eax
0x1800acebb  jns     short loc_1800ACECE
0x1800acebd  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800acec2  lea     rsi, aIwebaccount2Ge_0; "IWebAccount2::get_Properties"
0x1800acec9  jmp     loc_1800ACF8B
0x1800acece  mov     rdi, [rbp+57h+var_80]
0x1800aced2  mov     rax, [rdi]
0x1800aced5  mov     rbx, [rax+40h]
0x1800aced9  mov     [rbp+57h+var_40], rsi
0x1800acedd  mov     r9d, 9; unsigned int
0x1800acee3  lea     r8d, [r9+1]; unsigned int
0x1800acee7  lea     rdx, aAuthority; "Authority"
0x1800aceee  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800acef2  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800acef7  nop
0x1800acef8  mov     esi, 1
0x1800acefd  mov     [rbp+57h+var_68], esi
0x1800acf00  lea     r8, [rbp+57h+var_A0]
0x1800acf04  mov     rdx, [rbp+57h+var_40]
0x1800acf08  mov     rcx, rdi
0x1800acf0b  mov     rax, rbx
0x1800acf0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acf13  test    eax, eax
0x1800acf15  js      short loc_1800ACF1D
0x1800acf17  cmp     [rbp+57h+var_A0], 0
0x1800acf1b  jnz     short loc_1800ACF20
0x1800acf1d  xor     sil, sil
0x1800acf20  test    sil, sil
0x1800acf23  jz      loc_1800AD017
0x1800acf29  mov     rdi, [rbp+57h+var_80]
0x1800acf2d  mov     rax, [rdi]
0x1800acf30  mov     rbx, [rax+30h]
0x1800acf34  mov     rcx, [rbp+57h+var_98]; string
0x1800acf38  call    cs:__imp_WindowsDeleteString
0x1800acf3e  xor     esi, esi
0x1800acf40  mov     [rbp+57h+var_98], rsi
0x1800acf44  mov     [rbp+57h+var_40], rsi
0x1800acf48  lea     r9d, [rsi+9]; unsigned int
0x1800acf4c  lea     r8d, [rsi+0Ah]; unsigned int
0x1800acf50  lea     rdx, aAuthority; "Authority"
0x1800acf57  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800acf5b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800acf60  nop
0x1800acf61  lea     r8, [rbp+57h+var_98]
0x1800acf65  mov     rdx, [rbp+57h+var_40]
0x1800acf69  mov     rcx, rdi
0x1800acf6c  mov     rax, rbx
0x1800acf6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acf74  mov     r14d, eax
0x1800acf77  test    eax, eax
0x1800acf79  jns     loc_1800AD019
0x1800acf7f  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800acf84  lea     rsi, aImapviewLookup; "IMapView::Lookup"
0x1800acf8b  mov     rcx, [rax]
0x1800acf8e  xor     r13d, r13d
0x1800acf91  lea     rdi, aProcessaccount_0; "ProcessAccount"
0x1800acf98  lea     rbx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x."...
0x1800acf9f  cmp     [rcx], r13b
0x1800acfa2  jz      short loc_1800ACFF6
0x1800acfa4  mov     r9d, r14d
0x1800acfa7  mov     r8, rsi
0x1800acfaa  mov     rdx, rdi
0x1800acfad  mov     rcx, rbx; Format
0x1800acfb0  call    wprintf
0x1800acfb5  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800acfba  mov     rcx, [rax]
0x1800acfbd  cmp     [rcx+0Ch], r13b
0x1800acfc1  jz      short loc_1800ACFF6
0x1800acfc3  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800acfc8  mov     rcx, [rax]
0x1800acfcb  cmp     [rcx+0B8h], r13
0x1800acfd2  jz      short loc_1800ACFF6
0x1800acfd4  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800acfd9  mov     rcx, [rax]
0x1800acfdc  mov     dword ptr [rsp+0D0h+var_B0], r14d
0x1800acfe1  mov     r9, rsi
0x1800acfe4  mov     r8, rdi
0x1800acfe7  mov     rdx, rbx; Format
0x1800acfea  mov     rcx, [rcx+0B8h]; Stream
0x1800acff1  call    fwprintf_s
0x1800acff6  mov     r9d, r14d
0x1800acff9  mov     r8, rsi
0x1800acffc  mov     rdx, rdi
0x1800acfff  mov     rcx, rbx; unsigned __int16 *
0x1800ad002  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800ad007  xor     esi, esi
0x1800ad009  test    r12b, r12b
0x1800ad00c  jz      loc_1800AD2A3
0x1800ad012  jmp     loc_1800AD1A6
0x1800ad017  xor     esi, esi
0x1800ad019  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800ad01e  mov     rcx, [rax]
0x1800ad021  test    r12b, r12b
0x1800ad024  jz      loc_1800AD1F7
0x1800ad02a  cmp     [rcx+0Ch], sil
0x1800ad02e  jz      short loc_1800AD096
0x1800ad030  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800ad035  mov     rcx, [rax]
0x1800ad038  cmp     [rcx+0B8h], rsi
0x1800ad03f  jz      short loc_1800AD096
0x1800ad041  xor     edx, edx; length
0x1800ad043  mov     rcx, [rbp+57h+var_98]; string
0x1800ad047  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ad04d  mov     rsi, rax
0x1800ad050  xor     edx, edx; length
0x1800ad052  mov     rcx, [rbp+57h+var_90]; string
0x1800ad056  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ad05c  mov     rdi, rax
0x1800ad05f  xor     edx, edx; length
0x1800ad061  mov     rcx, [rbp+57h+string]; string
0x1800ad065  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ad06b  mov     rbx, rax
0x1800ad06e  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800ad073  mov     rcx, [rax]
0x1800ad076  mov     [rsp+0D0h+var_B0], rsi
0x1800ad07b  mov     r9, rdi
0x1800ad07e  mov     r8, rbx
0x1800ad081  lea     rdx, aRemovingAccoun; "Removing account: %s, user: %s, authori"...
0x1800ad088  mov     rcx, [rcx+0B8h]; Stream
0x1800ad08f  call    fwprintf_s
0x1800ad094  xor     esi, esi
0x1800ad096  xor     edx, edx; length
0x1800ad098  mov     rcx, [rbp+57h+var_98]; string
0x1800ad09c  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ad0a2  mov     rdi, rax
0x1800ad0a5  xor     edx, edx; length
0x1800ad0a7  mov     rcx, [rbp+57h+var_90]; string
0x1800ad0ab  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ad0b1  mov     rbx, rax
0x1800ad0b4  xor     edx, edx; length
0x1800ad0b6  mov     rcx, [rbp+57h+string]; string
0x1800ad0ba  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ad0c0  mov     r9, rdi
0x1800ad0c3  mov     r8, rbx
0x1800ad0c6  mov     rdx, rax
0x1800ad0c9  lea     rcx, aRemovingAccoun; "Removing account: %s, user: %s, authori"...
0x1800ad0d0  call    wprintf
0x1800ad0d5  mov     rax, [r13+0]
0x1800ad0d9  mov     rbx, [rax+78h]
0x1800ad0dd  lea     rcx, [rbp+57h+var_78]
0x1800ad0e1  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800ad0e6  lea     r8, [rbp+57h+var_78]
0x1800ad0ea  mov     rdx, [r15]
0x1800ad0ed  mov     rcx, r13
0x1800ad0f0  mov     rax, rbx
0x1800ad0f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad0f8  mov     r14d, eax
0x1800ad0fb  test    eax, eax
0x1800ad0fd  jns     short loc_1800AD10D
0x1800ad0ff  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800ad104  lea     r12, aItokenbrokerin_1; "ITokenBrokerInternalStatics::DeleteAcco"...
0x1800ad10b  jmp     short loc_1800AD12D
0x1800ad10d  mov     rcx, [rbp+57h+var_78]
0x1800ad111  call    ??$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)
0x1800ad116  mov     r14d, eax
0x1800ad119  test    eax, eax
0x1800ad11b  jns     loc_1800AD1A6
0x1800ad121  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800ad126  lea     r12, aWaitforcomplet; "WaitForCompletion"
0x1800ad12d  mov     rcx, [rax]
0x1800ad130  cmp     [rcx], sil
0x1800ad133  lea     rbx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x."...
0x1800ad13a  lea     rdi, aProcessaccount_0; "ProcessAccount"
0x1800ad141  jz      short loc_1800AD195
0x1800ad143  mov     r9d, r14d
0x1800ad146  mov     r8, r12
0x1800ad149  mov     rdx, rdi
0x1800ad14c  mov     rcx, rbx; Format
0x1800ad14f  call    wprintf
0x1800ad154  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800ad159  mov     rcx, [rax]
0x1800ad15c  cmp     [rcx+0Ch], sil
0x1800ad160  jz      short loc_1800AD195
0x1800ad162  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800ad167  mov     rcx, [rax]
0x1800ad16a  cmp     [rcx+0B8h], rsi
0x1800ad171  jz      short loc_1800AD195
0x1800ad173  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800ad178  mov     rcx, [rax]
0x1800ad17b  mov     dword ptr [rsp+0D0h+var_B0], r14d
0x1800ad180  mov     r9, r12
0x1800ad183  mov     r8, rdi
0x1800ad186  mov     rdx, rbx; Format
0x1800ad189  mov     rcx, [rcx+0B8h]; Stream
0x1800ad190  call    fwprintf_s
0x1800ad195  mov     r9d, r14d
0x1800ad198  mov     r8, r12
0x1800ad19b  mov     rdx, rdi
0x1800ad19e  mov     rcx, rbx; unsigned __int16 *
0x1800ad1a1  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800ad1a6  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800ad1ab  mov     rcx, [rax]
0x1800ad1ae  cmp     [rcx+0Ch], sil
0x1800ad1b2  jz      short loc_1800AD1E3
0x1800ad1b4  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800ad1b9  mov     rdx, [rax]
0x1800ad1bc  cmp     [rdx+0B8h], rsi
0x1800ad1c3  jz      short loc_1800AD1E3
0x1800ad1c5  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800ad1ca  mov     rcx, [rax]
0x1800ad1cd  mov     r8d, r14d
0x1800ad1d0  lea     rdx, aRemoveAccountR; "Remove account result: 0x%08x.\n"
0x1800ad1d7  mov     rcx, [rcx+0B8h]; Stream
0x1800ad1de  call    fwprintf_s
0x1800ad1e3  mov     edx, r14d
0x1800ad1e6  lea     rcx, aRemoveAccountR; "Remove account result: 0x%08x.\n"
0x1800ad1ed  call    wprintf
0x1800ad1f2  jmp     loc_1800AD2A3
0x1800ad1f7  cmp     [rcx+0Ch], sil
0x1800ad1fb  jz      short loc_1800AD263
0x1800ad1fd  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800ad202  mov     rcx, [rax]
0x1800ad205  cmp     [rcx+0B8h], rsi
0x1800ad20c  jz      short loc_1800AD263
0x1800ad20e  xor     edx, edx; length
0x1800ad210  mov     rcx, [rbp+57h+var_98]; string
0x1800ad214  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ad21a  mov     rsi, rax
0x1800ad21d  xor     edx, edx; length
0x1800ad21f  mov     rcx, [rbp+57h+var_90]; string
0x1800ad223  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ad229  mov     rdi, rax
0x1800ad22c  xor     edx, edx; length
  ... truncated ...
```
