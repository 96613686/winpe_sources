# cdp::UserAuthManager::XboxUserManagerProxy::GetSignedInUserForXuid(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1801ee99c`
- end: `0x1801eefa0`
- name: `?GetSignedInUserForXuid@XboxUserManagerProxy@UserAuthManager@cdp@@QEAA?AV?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1540`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1801edd9c`

## callees

- `0x1800110f8`
- `0x18001ce80`
- `0x1800624cc`
- `0x180114c58`
- `0x1801ee99c`
- `0x1801f6fb0`
- `0x1802ca47c`
- `0x1802ca5d4`
- `0x1802cab84`
- `0x1802cad0c`
- `0x1802cb02c`
- `0x180354010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801eede7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801eede7`
- `msvcp_win!_Mtx_unlock` at `0x1801eef73`
- `msvcp_win!_Mtx_unlock` at `0x1801eef73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801eed5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801eee56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801eeef8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801eed5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801eee56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801eeef8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801eedcd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801eedcd`

## string_xrefs

- `0x1801eeb89`: `Couldn't copy xbox user data out`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
HSTRING *__fastcall cdp::UserAuthManager::XboxUserManagerProxy::GetSignedInUserForXuid(
        __int64 a1,
        HSTRING *a2,
        _QWORD *a3)
{
  struct _Mtx_internal_imp_t *v6; // rdi
  __int64 v7; // rsi
  __int64 (__fastcall *v8)(__int64, __int64, __int64 *); // rbx
  int v9; // eax
  __int64 v10; // rax
  __int64 v11; // rbx
  int v12; // eax
  int v13; // eax
  __int64 v14; // rax
  unsigned int i; // r15d
  int v16; // eax
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // rax
  HSTRING v20; // rsi
  __int64 (__fastcall *v21)(HSTRING, _QWORD, __int64 *); // rbx
  const unsigned __int16 (*v22)[11]; // rdx
  _QWORD *v23; // rax
  int v24; // eax
  __int64 v25; // rax
  __int64 v26; // rbx
  int v27; // eax
  int v28; // eax
  __int64 v29; // rax
  __int64 v30; // rsi
  __int64 (__fastcall *v31)(__int64, HSTRING *); // rbx
  int v32; // eax
  __int64 v33; // rax
  PCWSTR StringRawBuffer; // rax
  _QWORD *v35; // rcx
  HSTRING v36; // rbx
  __int64 v37; // rax
  __int64 v38; // rdx
  HSTRING v40; // rax
  int v41; // [rsp+28h] [rbp-100h]
  __int64 v42; // [rsp+30h] [rbp-F8h]
  unsigned int v43; // [rsp+30h] [rbp-F8h] BYREF
  HSTRING string; // [rsp+38h] [rbp-F0h] BYREF
  int v45; // [rsp+40h] [rbp-E8h] BYREF
  HSTRING v46; // [rsp+48h] [rbp-E0h] BYREF
  __int64 v47; // [rsp+50h] [rbp-D8h] BYREF
  __int64 v48; // [rsp+58h] [rbp-D0h] BYREF
  __int64 v49; // [rsp+60h] [rbp-C8h] BYREF
  __int64 v50; // [rsp+68h] [rbp-C0h] BYREF
  __int64 v51; // [rsp+70h] [rbp-B8h] BYREF
  int v52; // [rsp+78h] [rbp-B0h]
  __int64 v53; // [rsp+80h] [rbp-A8h]
  HSTRING *v54; // [rsp+88h] [rbp-A0h]
  _BYTE v55[56]; // [rsp+90h] [rbp-98h] BYREF
  HSTRING v56; // [rsp+C8h] [rbp-60h] BYREF
  int v57; // [rsp+D0h] [rbp-58h]

  v54 = a2;
  *a2 = 0;
  v52 = 1;
  v6 = (struct _Mtx_internal_imp_t *)(a1 + 24);
  v53 = a1 + 24;
  std::_Mutex_base::lock((std::_Mutex_base *)(a1 + 24));
  try
  {
    if ( *(_BYTE *)(a1 + 16) )
    {
      v51 = 0;
      v49 = 0;
      v43 = 0;
      v7 = *(_QWORD *)(a1 + 120);
      v8 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v7 + 64LL);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v51);
      v9 = v8(v7, 1, &v51);
      if ( v9 < 0 )
      {
        v56 = (HSTRING)".\\userauthmanager.cpp";
        v57 = 175;
        v10 = cdp::MakeException<cdp::hresult_exception,>(
                v55,
                &v56,
                (unsigned int)v9,
                "UserStatics::FindAllAsyncByType call creation failed.");
        cdp::CdpThrow<cdp::hresult_exception>(&v56, v10);
      }
      v11 = v51;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v49);
      v12 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>>(v11);
      if ( v12 < 0
        || (v12 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v11 + 64LL))(v11, &v49), v12 < 0) )
      {
        v56 = (HSTRING)".\\userauthmanager.cpp";
        v57 = 177;
        v38 = cdp::MakeException<cdp::hresult_exception,>(
                v55,
                &v56,
                (unsigned int)v12,
                "Couldn't get user list from xbox user manager");
        cdp::CdpThrow<cdp::hresult_exception>(&v56, v38);
      }
      v13 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v49 + 56LL))(v49, &v43);
      if ( v13 < 0 )
      {
        v56 = (HSTRING)".\\userauthmanager.cpp";
        v57 = 178;
        v14 = cdp::MakeException<cdp::hresult_exception,>(
                v55,
                &v56,
                (unsigned int)v13,
                "Couldn't get user list size from xbox user manager");
        cdp::CdpThrow<cdp::hresult_exception>(&v56, v14);
      }
      for ( i = 0; i < v43; ++i )
      {
        v46 = 0;
        string = 0;
        v48 = 0;
        v47 = 0;
        v50 = 0;
        v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v49 + 48LL))(v49, i, &v46);
        if ( v16 < 0 )
        {
          v56 = (HSTRING)".\\userauthmanager.cpp";
          v57 = 189;
          v17 = cdp::MakeException<cdp::hresult_exception,>(
                  v55,
                  &v56,
                  (unsigned int)v16,
                  "Couldn't copy xbox user data out");
          cdp::CdpThrow<cdp::hresult_exception>(&v56, v17);
        }
        v18 = (*(__int64 (__fastcall **)(HSTRING, int *))(*(_QWORD *)v46 + 56LL))(v46, &v45);
        if ( v18 < 0 )
        {
          v56 = (HSTRING)".\\userauthmanager.cpp";
          v57 = 190;
          v19 = cdp::MakeException<cdp::hresult_exception,>(
                  v55,
                  &v56,
                  (unsigned int)v18,
                  "Couldn't get signed in state for user");
          cdp::CdpThrow<cdp::hresult_exception>(&v56, v19);
        }
        if ( v45 == 2 )
        {
          v20 = v46;
          v21 = *(__int64 (__fastcall **)(HSTRING, _QWORD, __int64 *))(*(_QWORD *)v46 + 72LL);
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v48);
          v23 = (_QWORD *)Windows::Internal::StringReference::StringReference(&v56, v22);
          v24 = v21(v20, *v23, &v48);
          if ( v24 < 0 )
          {
            v56 = (HSTRING)".\\userauthmanager.cpp";
            v57 = 195;
            v25 = cdp::MakeException<cdp::hresult_exception,>(
                    v55,
                    &v56,
                    (unsigned int)v24,
                    "User::GetPropertyAsync call creation failed.");
            cdp::CdpThrow<cdp::hresult_exception>(&v56, v25);
          }
          v26 = v48;
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v47);
          v27 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<IInspectable *>,Windows::Foundation::IAsyncOperation<IInspectable *>>(v26);
          if ( v27 < 0
            || (v27 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v26 + 64LL))(v26, &v47), v27 < 0) )
          {
            v56 = (HSTRING)".\\userauthmanager.cpp";
            v57 = 196;
            v37 = cdp::MakeException<cdp::hresult_exception,>(v55, &v56, (unsigned int)v27, "Couldn't get Properties");
            cdp::CdpThrow<cdp::hresult_exception>(&v56, v37);
          }
          v28 = Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(&v47, &v50);
          if ( v28 < 0 )
          {
            v56 = (HSTRING)".\\userauthmanager.cpp";
            v57 = 197;
            v29 = cdp::MakeException<cdp::hresult_exception,>(
                    v55,
                    &v56,
                    (unsigned int)v28,
                    "Couldn't convert inspectable to propvalue");
            cdp::CdpThrow<cdp::hresult_exception>(&v56, v29);
          }
          v30 = v50;
          v31 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v50 + 152LL);
          WindowsDeleteString(string);
          string = 0;
          v32 = v31(v30, &string);
          if ( v32 < 0 )
          {
            v56 = (HSTRING)".\\userauthmanager.cpp";
            v57 = 198;
            v33 = cdp::MakeException<cdp::hresult_exception,>(v55, &v56, (unsigned int)v32, "Couldn't get xuid string.");
            cdp::CdpThrow<cdp::hresult_exception>(&v56, v33);
          }
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          v35 = a3[3] <= 7u ? a3 : (_QWORD *)*a3;
          if ( !(unsigned int)_o__wcsicmp(v35, StringRawBuffer) )
          {
            v36 = v46;
            if ( *a2 != v46 )
            {
              v56 = v46;
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalAddRef(&v56);
              v56 = *a2;
              *a2 = v36;
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v56);
            }
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v50);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v47);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v48);
            WindowsDeleteString(string);
            string = 0;
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v46);
            break;
          }
        }
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v50);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v47);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v48);
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v46);
      }
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v49);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v51);
    }
  }
  catch ( ... )
  {
    v43 = -2147418113;
    LODWORD(v40) = GetCurrentThreadId();
    v56 = v40;
    v45 = 209;
    cdp::CatchAllToHR<char const (&)[36],int,unsigned __int64>(
      &v43,
      "{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\":\"Couldn't se"
      "arch UserManager to check signed in status\"}",
      (unsigned int)".\\userauthmanager.cpp",
      (const char *)&v45,
      (const char *)&v56,
      v41,
      v42);
  }
  _Mtx_unlock(v6);
  return a2;
}

```

## disassembly

```asm
0x1801ee99c  push    rbx
0x1801ee99e  push    rsi
0x1801ee99f  push    rdi
0x1801ee9a0  push    r12
0x1801ee9a2  push    r13
0x1801ee9a4  push    r14
0x1801ee9a6  push    r15
0x1801ee9a8  sub     rsp, 0F0h
0x1801ee9af  mov     rax, cs:__security_cookie
0x1801ee9b6  xor     rax, rsp
0x1801ee9b9  mov     [rsp+128h+var_40], rax
0x1801ee9c1  mov     r12, r8
0x1801ee9c4  mov     r14, rdx
0x1801ee9c7  mov     rsi, rcx
0x1801ee9ca  mov     [rsp+128h+var_A0], rdx
0x1801ee9d2  xor     r13d, r13d
0x1801ee9d5  mov     [rsp+128h+var_B0], r13d
0x1801ee9da  mov     [rdx], r13
0x1801ee9dd  lea     r15d, [r13+1]
0x1801ee9e1  mov     [rsp+128h+var_B0], r15d
0x1801ee9e6  lea     rdi, [rcx+18h]
0x1801ee9ea  mov     [rsp+128h+var_A8], rdi
0x1801ee9f2  mov     rcx, rdi; this
0x1801ee9f5  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1801ee9fa  nop
0x1801ee9fb  cmp     [rsi+10h], r13b
0x1801ee9ff  jz      loc_1801EEE82
0x1801eea05  mov     [rsp+128h+var_B8], r13
0x1801eea0a  mov     [rsp+128h+var_C8], r13
0x1801eea0f  mov     [rsp+128h+var_F8], r13d
0x1801eea14  mov     rsi, [rsi+78h]
0x1801eea18  mov     rax, [rsi]
0x1801eea1b  mov     rbx, [rax+40h]
0x1801eea1f  lea     rcx, [rsp+128h+var_B8]
0x1801eea24  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1801eea29  lea     r8, [rsp+128h+var_B8]
0x1801eea2e  mov     edx, r15d
0x1801eea31  mov     rcx, rsi
0x1801eea34  mov     rax, rbx
0x1801eea37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801eea3c  test    eax, eax
0x1801eea3e  jns     short loc_1801EEA8B
0x1801eea40  lea     rcx, aUserauthmanage; ".\\userauthmanager.cpp"
0x1801eea47  mov     [rsp+128h+var_60], rcx
0x1801eea4f  mov     [rsp+128h+var_58], 0AFh
0x1801eea5a  lea     r9, aUserstaticsFin_1; "UserStatics::FindAllAsyncByType call cr"...
0x1801eea61  mov     r8d, eax
0x1801eea64  lea     rdx, [rsp+128h+var_60]
0x1801eea6c  lea     rcx, [rsp+128h+var_98]
0x1801eea74  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x1801eea79  nop
0x1801eea7a  mov     rdx, rax
0x1801eea7d  lea     rcx, [rsp+128h+var_60]
0x1801eea85  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1801eea8b  mov     rbx, [rsp+128h+var_B8]
0x1801eea90  lea     rcx, [rsp+128h+var_C8]
0x1801eea95  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1801eea9a  mov     rcx, rbx
0x1801eea9d  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *> *,tagCOWAIT_FLAGS,void *)
0x1801eeaa2  test    eax, eax
0x1801eeaa4  js      loc_1801EEF15
0x1801eeaaa  mov     rax, [rbx]
0x1801eeaad  lea     rdx, [rsp+128h+var_C8]
0x1801eeab2  mov     rcx, rbx
0x1801eeab5  mov     rax, [rax+40h]
0x1801eeab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801eeabe  test    eax, eax
0x1801eeac0  js      loc_1801EEF15
0x1801eeac6  mov     rcx, [rsp+128h+var_C8]
0x1801eeacb  mov     rax, [rcx]
0x1801eeace  lea     rdx, [rsp+128h+var_F8]
0x1801eead3  mov     rax, [rax+38h]
0x1801eead7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801eeadc  test    eax, eax
0x1801eeade  jns     short loc_1801EEB2B
0x1801eeae0  lea     rcx, aUserauthmanage; ".\\userauthmanager.cpp"
0x1801eeae7  mov     [rsp+128h+var_60], rcx
0x1801eeaef  mov     [rsp+128h+var_58], 0B2h
0x1801eeafa  lea     r9, aCouldnTGetUser; "Couldn't get user list size from xbox u"...
0x1801eeb01  mov     r8d, eax
0x1801eeb04  lea     rdx, [rsp+128h+var_60]
0x1801eeb0c  lea     rcx, [rsp+128h+var_98]
0x1801eeb14  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x1801eeb19  nop
0x1801eeb1a  mov     rdx, rax
0x1801eeb1d  lea     rcx, [rsp+128h+var_60]
0x1801eeb25  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1801eeb2b  mov     r15d, r13d
0x1801eeb2e  cmp     r15d, [rsp+128h+var_F8]
0x1801eeb33  jnb     loc_1801EEE6C
0x1801eeb39  mov     [rsp+128h+var_E0], r13
0x1801eeb3e  mov     [rsp+128h+string], r13
0x1801eeb43  mov     [rsp+128h+var_D0], r13
0x1801eeb48  mov     [rsp+128h+var_D8], r13
0x1801eeb4d  mov     [rsp+128h+var_C0], r13
0x1801eeb52  mov     rcx, [rsp+128h+var_C8]
0x1801eeb57  mov     rax, [rcx]
0x1801eeb5a  lea     r8, [rsp+128h+var_E0]
0x1801eeb5f  mov     edx, r15d
0x1801eeb62  mov     rax, [rax+30h]
0x1801eeb66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801eeb6b  test    eax, eax
0x1801eeb6d  jns     short loc_1801EEBBA
0x1801eeb6f  lea     rcx, aUserauthmanage; ".\\userauthmanager.cpp"
0x1801eeb76  mov     [rsp+128h+var_60], rcx
0x1801eeb7e  mov     [rsp+128h+var_58], 0BDh
0x1801eeb89  lea     r9, aCouldnTCopyXbo; "Couldn't copy xbox user data out"
0x1801eeb90  mov     r8d, eax
0x1801eeb93  lea     rdx, [rsp+128h+var_60]
0x1801eeb9b  lea     rcx, [rsp+128h+var_98]
0x1801eeba3  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x1801eeba8  nop
0x1801eeba9  mov     rdx, rax
0x1801eebac  lea     rcx, [rsp+128h+var_60]
0x1801eebb4  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1801eebba  mov     rcx, [rsp+128h+var_E0]
0x1801eebbf  mov     rax, [rcx]
0x1801eebc2  lea     rdx, [rsp+128h+var_E8]
0x1801eebc7  mov     rax, [rax+38h]
0x1801eebcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801eebd0  test    eax, eax
0x1801eebd2  jns     short loc_1801EEC1F
0x1801eebd4  lea     rcx, aUserauthmanage; ".\\userauthmanager.cpp"
0x1801eebdb  mov     [rsp+128h+var_60], rcx
0x1801eebe3  mov     [rsp+128h+var_58], 0BEh
0x1801eebee  lea     r9, aCouldnTGetSign; "Couldn't get signed in state for user"
0x1801eebf5  mov     r8d, eax
0x1801eebf8  lea     rdx, [rsp+128h+var_60]
0x1801eec00  lea     rcx, [rsp+128h+var_98]
0x1801eec08  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x1801eec0d  nop
0x1801eec0e  mov     rdx, rax
0x1801eec11  lea     rcx, [rsp+128h+var_60]
0x1801eec19  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1801eec1f  cmp     [rsp+128h+var_E8], 2
0x1801eec24  jnz     loc_1801EEED2
0x1801eec2a  mov     rsi, [rsp+128h+var_E0]
0x1801eec2f  mov     rax, [rsi]
0x1801eec32  mov     rbx, [rax+48h]
0x1801eec36  lea     rcx, [rsp+128h+var_D0]
0x1801eec3b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1801eec40  lea     rcx, [rsp+128h+var_60]; string
0x1801eec48  call    ??$?0$0L@@StringReference@Internal@Windows@@QEAA@AEAY0L@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[11])
0x1801eec4d  lea     r8, [rsp+128h+var_D0]
0x1801eec52  mov     rdx, [rax]
0x1801eec55  mov     rcx, rsi
0x1801eec58  mov     rax, rbx
0x1801eec5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801eec60  test    eax, eax
0x1801eec62  jns     short loc_1801EECAF
0x1801eec64  lea     rcx, aUserauthmanage; ".\\userauthmanager.cpp"
0x1801eec6b  mov     [rsp+128h+var_60], rcx
0x1801eec73  mov     [rsp+128h+var_58], 0C3h
0x1801eec7e  lea     r9, aUserGetpropert; "User::GetPropertyAsync call creation fa"...
0x1801eec85  mov     r8d, eax
0x1801eec88  lea     rdx, [rsp+128h+var_60]
0x1801eec90  lea     rcx, [rsp+128h+var_98]
0x1801eec98  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x1801eec9d  nop
0x1801eec9e  mov     rdx, rax
0x1801eeca1  lea     rcx, [rsp+128h+var_60]
0x1801eeca9  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1801eecaf  mov     rbx, [rsp+128h+var_D0]
0x1801eecb4  lea     rcx, [rsp+128h+var_D8]
0x1801eecb9  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1801eecbe  mov     rcx, rbx
0x1801eecc1  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUIInspectable@@@Foundation@Windows@@U?$IAsyncOperation@PEAUIInspectable@@@23@@@YAJPEAU?$IAsyncOperation@PEAUIInspectable@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<IInspectable *>,Windows::Foundation::IAsyncOperation<IInspectable *>>(Windows::Foundation::IAsyncOperation<IInspectable *> *,tagCOWAIT_FLAGS,void *)
0x1801eecc6  test    eax, eax
0x1801eecc8  js      loc_1801EEE87
0x1801eecce  mov     rax, [rbx]
0x1801eecd1  lea     rdx, [rsp+128h+var_D8]
0x1801eecd6  mov     rcx, rbx
0x1801eecd9  mov     rax, [rax+40h]
0x1801eecdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801eece2  test    eax, eax
0x1801eece4  js      loc_1801EEE87
0x1801eecea  lea     rdx, [rsp+128h+var_C0]
0x1801eecef  lea     rcx, [rsp+128h+var_D8]
0x1801eecf4  call    ??$As@UIPropertyValue@Foundation@Windows@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIPropertyValue@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValue>>)
0x1801eecf9  test    eax, eax
0x1801eecfb  jns     short loc_1801EED48
0x1801eecfd  lea     rcx, aUserauthmanage; ".\\userauthmanager.cpp"
0x1801eed04  mov     [rsp+128h+var_60], rcx
0x1801eed0c  mov     [rsp+128h+var_58], 0C5h
0x1801eed17  lea     r9, aCouldnTConvert_0; "Couldn't convert inspectable to propval"...
0x1801eed1e  mov     r8d, eax
0x1801eed21  lea     rdx, [rsp+128h+var_60]
0x1801eed29  lea     rcx, [rsp+128h+var_98]
0x1801eed31  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x1801eed36  nop
0x1801eed37  mov     rdx, rax
0x1801eed3a  lea     rcx, [rsp+128h+var_60]
0x1801eed42  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1801eed48  mov     rsi, [rsp+128h+var_C0]
0x1801eed4d  mov     rax, [rsi]
0x1801eed50  mov     rbx, [rax+98h]
0x1801eed57  mov     rcx, [rsp+128h+string]; string
0x1801eed5c  call    cs:__imp_WindowsDeleteString
0x1801eed62  mov     [rsp+128h+string], r13
0x1801eed67  lea     rdx, [rsp+128h+string]
0x1801eed6c  mov     rcx, rsi
0x1801eed6f  mov     rax, rbx
0x1801eed72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801eed77  test    eax, eax
0x1801eed79  jns     short loc_1801EEDC6
0x1801eed7b  lea     rcx, aUserauthmanage; ".\\userauthmanager.cpp"
0x1801eed82  mov     [rsp+128h+var_60], rcx
0x1801eed8a  mov     [rsp+128h+var_58], 0C6h
0x1801eed95  lea     r9, aCouldnTGetXuid; "Couldn't get xuid string."
0x1801eed9c  mov     r8d, eax
0x1801eed9f  lea     rdx, [rsp+128h+var_60]
0x1801eeda7  lea     rcx, [rsp+128h+var_98]
0x1801eedaf  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x1801eedb4  nop
0x1801eedb5  mov     rdx, rax
0x1801eedb8  lea     rcx, [rsp+128h+var_60]
0x1801eedc0  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1801eedc6  xor     edx, edx; length
0x1801eedc8  mov     rcx, [rsp+128h+string]; string
0x1801eedcd  call    cs:__imp_WindowsGetStringRawBuffer
0x1801eedd3  cmp     qword ptr [r12+18h], 7
0x1801eedd9  jbe     short loc_1801EEDE1
0x1801eeddb  mov     rcx, [r12]
0x1801eeddf  jmp     short loc_1801EEDE4
0x1801eede1  mov     rcx, r12
0x1801eede4  mov     rdx, rax
0x1801eede7  call    cs:__imp__o__wcsicmp
0x1801eeded  test    eax, eax
0x1801eedef  jnz     loc_1801EEED2
0x1801eedf5  mov     rbx, [rsp+128h+var_E0]
0x1801eedfa  cmp     [r14], rbx
0x1801eedfd  jz      short loc_1801EEE30
0x1801eedff  mov     [rsp+128h+var_60], rbx
0x1801eee07  lea     rcx, [rsp+128h+var_60]
0x1801eee0f  call    ?InternalAddRef@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalAddRef(void)
0x1801eee14  mov     rax, [r14]
0x1801eee17  mov     [rsp+128h+var_60], rax
0x1801eee1f  mov     [r14], rbx
0x1801eee22  lea     rcx, [rsp+128h+var_60]
0x1801eee2a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1801eee2f  nop
0x1801eee30  lea     rcx, [rsp+128h+var_C0]
0x1801eee35  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1801eee3a  nop
0x1801eee3b  lea     rcx, [rsp+128h+var_D8]
0x1801eee40  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1801eee45  nop
0x1801eee46  lea     rcx, [rsp+128h+var_D0]
0x1801eee4b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1801eee50  nop
0x1801eee51  mov     rcx, [rsp+128h+string]; string
0x1801eee56  call    cs:__imp_WindowsDeleteString
0x1801eee5c  mov     [rsp+128h+string], r13
0x1801eee61  lea     rcx, [rsp+128h+var_E0]
0x1801eee66  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1801eee6b  nop
0x1801eee6c  lea     rcx, [rsp+128h+var_C8]
0x1801eee71  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1801eee76  nop
0x1801eee77  lea     rcx, [rsp+128h+var_B8]
0x1801eee7c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1801eee81  nop
0x1801eee82  jmp     loc_1801EEF70
0x1801eee87  lea     rcx, aUserauthmanage; ".\\userauthmanager.cpp"
0x1801eee8e  mov     [rsp+128h+var_60], rcx
0x1801eee96  mov     [rsp+128h+var_58], 0C4h
0x1801eeea1  lea     r9, aCouldnTGetProp_0; "Couldn't get Properties"
0x1801eeea8  mov     r8d, eax
0x1801eeeab  lea     rdx, [rsp+128h+var_60]
0x1801eeeb3  lea     rcx, [rsp+128h+var_98]
0x1801eeebb  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x1801eeec0  nop
0x1801eeec1  mov     rdx, rax
0x1801eeec4  lea     rcx, [rsp+128h+var_60]
0x1801eeecc  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1801eeed2  lea     rcx, [rsp+128h+var_C0]
0x1801eeed7  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1801eeedc  nop
0x1801eeedd  lea     rcx, [rsp+128h+var_D8]
0x1801eeee2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1801eeee7  nop
0x1801eeee8  lea     rcx, [rsp+128h+var_D0]
0x1801eeeed  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1801eeef2  nop
0x1801eeef3  mov     rcx, [rsp+128h+string]; string
0x1801eeef8  call    cs:__imp_WindowsDeleteString
0x1801eeefe  mov     [rsp+128h+string], r13
0x1801eef03  lea     rcx, [rsp+128h+var_E0]
0x1801eef08  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1801eef0d  inc     r15d
0x1801eef10  jmp     loc_1801EEB2E
0x1801eef15  lea     rcx, aUserauthmanage; ".\\userauthmanager.cpp"
0x1801eef1c  mov     [rsp+128h+var_60], rcx
0x1801eef24  mov     [rsp+128h+var_58], 0B1h
0x1801eef2f  lea     r9, aCouldnTGetUser_1; "Couldn't get user list from xbox user m"...
0x1801eef36  mov     r8d, eax
0x1801eef39  lea     rdx, [rsp+128h+var_60]
0x1801eef41  lea     rcx, [rsp+128h+var_98]
0x1801eef49  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x1801eef4e  nop
  ... truncated ...
```
