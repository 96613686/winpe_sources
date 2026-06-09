# cdp::UserAuthManager::XboxUserManagerProxy::SignInCompleteHandler(IInspectable *,Windows::System::Internal::ISignInCompleteEventArgs *)

- ea: `0x1802cb3d0`
- end: `0x1802cb909`
- name: `?SignInCompleteHandler@XboxUserManagerProxy@UserAuthManager@cdp@@QEAAJPEAUIInspectable@@PEAUISignInCompleteEventArgs@Internal@System@Windows@@@Z`
- size: `1337`
- prototype: `__int64 __fastcall(cdp::UserAuthManager::XboxUserManagerProxy *__hidden this, struct IInspectable *, struct Windows::System::Internal::ISignInCompleteEventArgs *)`
- caller_count: `0`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000aec4`
- `0x18000b724`
- `0x18000d098`
- `0x1800110f8`
- `0x180013da0`
- `0x18001ce80`
- `0x1800624cc`
- `0x180114c58`
- `0x18011d5d0`
- `0x18011d808`
- `0x180194418`
- `0x1801f6fb0`
- `0x1802ca47c`
- `0x1802ca584`
- `0x1802ca5d4`
- `0x1802cb0a0`
- `0x1802cb3d0`
- `0x180354010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x1802cb8bb`
- `msvcp_win!_Mtx_unlock` at `0x1802cb8bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802cb778`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802cb897`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802cb778`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802cb897`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802cb7f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802cb7f8`

## string_xrefs

- `0x1802cb450`: `SignOutCompletedHandler received a null argument`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall cdp::UserAuthManager::XboxUserManagerProxy::SignInCompleteHandler(
        cdp::UserAuthManager::XboxUserManagerProxy *this,
        struct IInspectable *a2,
        struct Windows::System::Internal::ISignInCompleteEventArgs *a3)
{
  struct _Mtx_internal_imp_t *v5; // r14
  __int64 v6; // rdx
  __int64 v7; // rdx
  int v8; // eax
  __int64 v9; // rax
  int v10; // eax
  __int64 v11; // rax
  int v12; // eax
  __int64 v13; // rax
  __int64 v14; // rdi
  void (__fastcall *v15)(__int64, _QWORD, __int64 *); // rbx
  int v16; // eax
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // rax
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, _QWORD, __int64 *); // rbx
  const unsigned __int16 (*v22)[11]; // rdx
  _QWORD *v23; // rax
  int v24; // eax
  __int64 v25; // rax
  int v26; // eax
  __int64 v27; // rax
  __int64 v28; // rdi
  __int64 (__fastcall *v29)(__int64, HSTRING *); // rbx
  int v30; // eax
  __int64 v31; // rax
  PCWSTR StringRawBuffer; // rdx
  __int64 v33; // rdx
  __int64 v34; // rax
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v38; // rax
  int v39; // [rsp+28h] [rbp-E0h]
  __int64 v40; // [rsp+30h] [rbp-D8h]
  const char *v41; // [rsp+30h] [rbp-D8h] BYREF
  int v42; // [rsp+38h] [rbp-D0h]
  unsigned int v43; // [rsp+50h] [rbp-B8h] BYREF
  int v44; // [rsp+54h] [rbp-B4h] BYREF
  HSTRING string; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v46; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v47; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v48; // [rsp+70h] [rbp-98h] BYREF
  __int64 v49; // [rsp+78h] [rbp-90h] BYREF
  __int64 v50; // [rsp+80h] [rbp-88h] BYREF
  __int64 v51; // [rsp+88h] [rbp-80h] BYREF
  const char *v52; // [rsp+90h] [rbp-78h] BYREF
  std::_Ref_count_base *v53; // [rsp+98h] [rbp-70h]
  char *v54; // [rsp+A0h] [rbp-68h]
  char *v55; // [rsp+A8h] [rbp-60h]
  HSTRING v56[7]; // [rsp+B0h] [rbp-58h] BYREF

  v46 = 0;
  v43 = 0;
  v44 = 0;
  v5 = (cdp::UserAuthManager::XboxUserManagerProxy *)((char *)this + 24);
  v54 = (char *)this + 24;
  v55 = (char *)this + 24;
  std::_Mutex_base::lock((cdp::UserAuthManager::XboxUserManagerProxy *)((char *)this + 24));
  try
  {
    if ( *((_BYTE *)this + 16) )
    {
      if ( !a3 )
      {
        v52 = ".\\userauthmanager.cpp";
        LODWORD(v53) = 253;
        v7 = cdp::MakeException<std::invalid_argument,>(&v41, v6, "SignOutCompletedHandler received a null argument");
        cdp::CdpThrow<std::invalid_argument>(&v52, v7);
      }
      v8 = (*(__int64 (__fastcall **)(struct Windows::System::Internal::ISignInCompleteEventArgs *, __int64 *))(*(_QWORD *)a3 + 48LL))(
             a3,
             &v46);
      if ( v8 < 0 )
      {
        v41 = ".\\userauthmanager.cpp";
        v42 = 254;
        v9 = cdp::MakeException<cdp::hresult_exception,>(
               v56,
               &v41,
               (unsigned int)v8,
               "Failed to get sign in result data");
        cdp::CdpThrow<cdp::hresult_exception>(&v41, v9);
      }
      v10 = (*(__int64 (__fastcall **)(__int64, unsigned int *, _QWORD))(*(_QWORD *)v46 + 80LL))(
              v46,
              &v43,
              (unsigned int)v8);
      if ( v10 < 0 )
      {
        v41 = ".\\userauthmanager.cpp";
        v42 = 255;
        v11 = cdp::MakeException<cdp::hresult_exception,>(v56, &v41, (unsigned int)v10, "Failed to get console user id");
        cdp::CdpThrow<cdp::hresult_exception>(&v41, v11);
      }
      v12 = (*(__int64 (__fastcall **)(__int64, int *, _QWORD))(*(_QWORD *)v46 + 64LL))(v46, &v44, (unsigned int)v10);
      if ( v12 < 0 )
      {
        v41 = ".\\userauthmanager.cpp";
        v42 = 256;
        v13 = cdp::MakeException<cdp::hresult_exception,>(v56, &v41, (unsigned int)v12, "User failed to sign in");
        cdp::CdpThrow<cdp::hresult_exception>(&v41, v13);
      }
      if ( v44 >= 0 )
      {
        v50 = 0;
        v14 = *((_QWORD *)this + 16);
        v15 = *(void (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v14 + 96LL);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v50);
        v15(v14, v43, &v50);
        if ( v50 )
        {
          string = 0;
          v49 = 0;
          v47 = 0;
          v48 = 0;
          v51 = 0;
          v16 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v50 + 88LL))(v50, &v49);
          if ( v16 < 0 )
          {
            v41 = ".\\userauthmanager.cpp";
            v42 = 271;
            v17 = cdp::MakeException<cdp::hresult_exception,>(v56, &v41, (unsigned int)v16, "Couldn't get Properties");
            cdp::CdpThrow<cdp::hresult_exception>(&v41, v17);
          }
          v18 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
                  &v49,
                  &v47);
          if ( v18 < 0 )
          {
            v41 = ".\\userauthmanager.cpp";
            v42 = 272;
            v19 = cdp::MakeException<cdp::hresult_exception,>(
                    v56,
                    &v41,
                    (unsigned int)v18,
                    "Couldn't get Properties as PropertyMap");
            cdp::CdpThrow<cdp::hresult_exception>(&v41, v19);
          }
          v20 = v47;
          v21 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v47 + 48LL);
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v48);
          v23 = (_QWORD *)Windows::Internal::StringReference::StringReference(v56, v22);
          v24 = v21(v20, *v23, &v48);
          if ( v24 < 0 )
          {
            v41 = ".\\userauthmanager.cpp";
            v42 = 273;
            v25 = cdp::MakeException<cdp::hresult_exception,>(v56, &v41, (unsigned int)v24, "Couldn't get xuid");
            cdp::CdpThrow<cdp::hresult_exception>(&v41, v25);
          }
          v26 = Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(&v48, &v51);
          if ( v26 < 0 )
          {
            v41 = ".\\userauthmanager.cpp";
            v42 = 274;
            v27 = cdp::MakeException<cdp::hresult_exception,>(
                    v56,
                    &v41,
                    (unsigned int)v26,
                    "Couldn't convert inspectable to propvalue");
            cdp::CdpThrow<cdp::hresult_exception>(&v41, v27);
          }
          v28 = v51;
          v29 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v51 + 152LL);
          WindowsDeleteString(string);
          string = 0;
          v30 = v29(v28, &string);
          if ( v30 < 0 )
          {
            v41 = ".\\userauthmanager.cpp";
            v42 = 275;
            v31 = cdp::MakeException<cdp::hresult_exception,>(v56, &v41, (unsigned int)v30, "Couldn't get xuid string.");
            cdp::CdpThrow<cdp::hresult_exception>(&v41, v31);
          }
          std::weak_ptr<cdp::ProximalConnector>::lock(this, &v52);
          if ( v52 )
          {
            StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
            v33 = std::wstring::wstring(v56, StringRawBuffer);
            v34 = cdp::ToUtf8(&v41, v33);
            cdp::UserAuthManager::OnXboxUserSignIn(v52, v43, v34);
            std::wstring::_Tidy_deallocate(v56);
          }
          if ( v53 )
            std::_Ref_count_base::_Decref(v53);
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v51);
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v48);
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v47);
          v35 = v49;
          if ( v49 )
          {
            v49 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
          }
          WindowsDeleteString(string);
        }
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v50);
      }
    }
  }
  catch ( ... )
  {
    LODWORD(v38) = GetCurrentThreadId();
    v47 = v38;
    LODWORD(string) = 286;
    cdp::CatchAllToHR<char const (&)[36],int,unsigned __int64>(
      &v44,
      "{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\":\"Could not u"
      "pdate user state on sign in\"}",
      (unsigned int)".\\userauthmanager.cpp",
      (const char *)&string,
      (const char *)&v47,
      v39,
      v40);
  }
  _Mtx_unlock(v5);
  v36 = v46;
  if ( v46 )
  {
    v46 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  }
  return 0;
}

```

## disassembly

```asm
0x1802cb3d0  mov     r11, rsp
0x1802cb3d3  mov     [r11+10h], rbx
0x1802cb3d7  mov     [r11+20h], rsi
0x1802cb3db  push    rdi
0x1802cb3dc  push    r14
0x1802cb3de  push    r15
0x1802cb3e0  sub     rsp, 0F0h
0x1802cb3e7  mov     rax, cs:__security_cookie
0x1802cb3ee  xor     rax, rsp
0x1802cb3f1  mov     [rsp+108h+var_20], rax
0x1802cb3f9  mov     rbx, r8
0x1802cb3fc  mov     r15, rcx
0x1802cb3ff  xor     esi, esi
0x1802cb401  mov     [rsp+108h+var_A8], rsi
0x1802cb406  mov     [rsp+108h+var_B8], esi
0x1802cb40a  mov     [rsp+108h+var_B4], esi
0x1802cb40e  lea     r14, [rcx+18h]
0x1802cb412  mov     [rsp+108h+var_68], r14
0x1802cb41a  mov     [r11-60h], r14
0x1802cb41e  mov     rcx, r14; this
0x1802cb421  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1802cb426  nop
0x1802cb427  cmp     [r15+10h], sil
0x1802cb42b  jz      loc_1802CB8AC
0x1802cb431  test    rbx, rbx
0x1802cb434  jnz     short loc_1802CB473
0x1802cb436  lea     rax, aUserauthmanage; ".\\userauthmanager.cpp"
0x1802cb43d  mov     [rsp+108h+var_78], rax
0x1802cb445  mov     dword ptr [rsp+108h+var_70], 0FDh
0x1802cb450  lea     r8, aSignoutcomplet; "SignOutCompletedHandler received a null"...
0x1802cb457  lea     rcx, [rsp+108h+var_D8]
0x1802cb45c  call    ??$MakeException@Vinvalid_argument@std@@$$V@cdp@@YA?AVinvalid_argument@std@@AEBUCDPSourceLocationInfo@0@PEBD@Z; cdp::MakeException<std::invalid_argument,>(cdp::CDPSourceLocationInfo const &,char const *)
0x1802cb461  nop
0x1802cb462  mov     rdx, rax
0x1802cb465  lea     rcx, [rsp+108h+var_78]
0x1802cb46d  call    ??$CdpThrow@Vinvalid_argument@std@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVinvalid_argument@std@@@Z; cdp::CdpThrow<std::invalid_argument>(cdp::CDPSourceLocationInfo const &,std::invalid_argument &&)
0x1802cb473  mov     rax, [rbx]
0x1802cb476  lea     rdx, [rsp+108h+var_A8]
0x1802cb47b  mov     rcx, rbx
0x1802cb47e  mov     rax, [rax+30h]
0x1802cb482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802cb487  mov     r8d, eax
0x1802cb48a  test    eax, eax
0x1802cb48c  jns     short loc_1802CB4CA
0x1802cb48e  lea     rax, aUserauthmanage; ".\\userauthmanager.cpp"
0x1802cb495  mov     [rsp+108h+var_D8], rax
0x1802cb49a  mov     [rsp+108h+var_D0], 0FEh
0x1802cb4a2  lea     r9, aFailedToGetSig; "Failed to get sign in result data"
0x1802cb4a9  lea     rdx, [rsp+108h+var_D8]
0x1802cb4ae  lea     rcx, [rsp+108h+var_58]
0x1802cb4b6  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x1802cb4bb  nop
0x1802cb4bc  mov     rdx, rax
0x1802cb4bf  lea     rcx, [rsp+108h+var_D8]
0x1802cb4c4  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1802cb4ca  mov     rcx, [rsp+108h+var_A8]
0x1802cb4cf  mov     rax, [rcx]
0x1802cb4d2  lea     rdx, [rsp+108h+var_B8]
0x1802cb4d7  mov     rax, [rax+50h]
0x1802cb4db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802cb4e0  mov     r8d, eax
0x1802cb4e3  test    eax, eax
0x1802cb4e5  jns     short loc_1802CB523
0x1802cb4e7  lea     rax, aUserauthmanage; ".\\userauthmanager.cpp"
0x1802cb4ee  mov     [rsp+108h+var_D8], rax
0x1802cb4f3  mov     [rsp+108h+var_D0], 0FFh
0x1802cb4fb  lea     r9, aFailedToGetCon_0; "Failed to get console user id"
0x1802cb502  lea     rdx, [rsp+108h+var_D8]
0x1802cb507  lea     rcx, [rsp+108h+var_58]
0x1802cb50f  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x1802cb514  nop
0x1802cb515  mov     rdx, rax
0x1802cb518  lea     rcx, [rsp+108h+var_D8]
0x1802cb51d  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1802cb523  mov     rcx, [rsp+108h+var_A8]
0x1802cb528  mov     rax, [rcx]
0x1802cb52b  lea     rdx, [rsp+108h+var_B4]
0x1802cb530  mov     rax, [rax+40h]
0x1802cb534  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802cb539  mov     r8d, eax
0x1802cb53c  test    eax, eax
0x1802cb53e  jns     short loc_1802CB57C
0x1802cb540  lea     rax, aUserauthmanage; ".\\userauthmanager.cpp"
0x1802cb547  mov     [rsp+108h+var_D8], rax
0x1802cb54c  mov     [rsp+108h+var_D0], 100h
0x1802cb554  lea     r9, aUserFailedToSi; "User failed to sign in"
0x1802cb55b  lea     rdx, [rsp+108h+var_D8]
0x1802cb560  lea     rcx, [rsp+108h+var_58]
0x1802cb568  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x1802cb56d  nop
0x1802cb56e  mov     rdx, rax
0x1802cb571  lea     rcx, [rsp+108h+var_D8]
0x1802cb576  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1802cb57c  cmp     [rsp+108h+var_B4], esi
0x1802cb580  jl      loc_1802CB8AC
0x1802cb586  mov     [rsp+108h+var_88], rsi
0x1802cb58e  mov     rdi, [r15+80h]
0x1802cb595  mov     rax, [rdi]
0x1802cb598  mov     rbx, [rax+60h]
0x1802cb59c  lea     rcx, [rsp+108h+var_88]
0x1802cb5a4  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1802cb5a9  lea     r8, [rsp+108h+var_88]
0x1802cb5b1  mov     edx, [rsp+108h+var_B8]
0x1802cb5b5  mov     rcx, rdi
0x1802cb5b8  mov     rax, rbx
0x1802cb5bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802cb5c0  mov     rcx, [rsp+108h+var_88]
0x1802cb5c8  test    rcx, rcx
0x1802cb5cb  jz      loc_1802CB89E
0x1802cb5d1  mov     [rsp+108h+string], rsi
0x1802cb5d6  mov     [rsp+108h+var_90], rsi
0x1802cb5db  mov     [rsp+108h+var_A0], rsi
0x1802cb5e0  mov     [rsp+108h+var_98], rsi
0x1802cb5e5  mov     [rsp+108h+var_80], rsi
0x1802cb5ed  mov     rax, [rcx]
0x1802cb5f0  lea     rdx, [rsp+108h+var_90]
0x1802cb5f5  mov     rax, [rax+58h]
0x1802cb5f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802cb5fe  mov     r8d, eax
0x1802cb601  test    eax, eax
0x1802cb603  jns     short loc_1802CB641
0x1802cb605  lea     rax, aUserauthmanage; ".\\userauthmanager.cpp"
0x1802cb60c  mov     [rsp+108h+var_D8], rax
0x1802cb611  mov     [rsp+108h+var_D0], 10Fh
0x1802cb619  lea     r9, aCouldnTGetProp_0; "Couldn't get Properties"
0x1802cb620  lea     rdx, [rsp+108h+var_D8]
0x1802cb625  lea     rcx, [rsp+108h+var_58]
0x1802cb62d  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x1802cb632  nop
0x1802cb633  mov     rdx, rax
0x1802cb636  lea     rcx, [rsp+108h+var_D8]
0x1802cb63b  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1802cb641  lea     rdx, [rsp+108h+var_A0]
0x1802cb646  lea     rcx, [rsp+108h+var_90]
0x1802cb64b  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x1802cb650  mov     r8d, eax
0x1802cb653  test    eax, eax
0x1802cb655  jns     short loc_1802CB693
0x1802cb657  lea     rax, aUserauthmanage; ".\\userauthmanager.cpp"
0x1802cb65e  mov     [rsp+108h+var_D8], rax
0x1802cb663  mov     [rsp+108h+var_D0], 110h
0x1802cb66b  lea     r9, aCouldnTGetProp; "Couldn't get Properties as PropertyMap"
0x1802cb672  lea     rdx, [rsp+108h+var_D8]
0x1802cb677  lea     rcx, [rsp+108h+var_58]
0x1802cb67f  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x1802cb684  nop
0x1802cb685  mov     rdx, rax
0x1802cb688  lea     rcx, [rsp+108h+var_D8]
0x1802cb68d  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1802cb693  mov     rdi, [rsp+108h+var_A0]
0x1802cb698  mov     rax, [rdi]
0x1802cb69b  mov     rbx, [rax+30h]
0x1802cb69f  lea     rcx, [rsp+108h+var_98]
0x1802cb6a4  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1802cb6a9  lea     rcx, [rsp+108h+var_58]; string
0x1802cb6b1  call    ??$?0$0L@@StringReference@Internal@Windows@@QEAA@AEAY0L@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[11])
0x1802cb6b6  lea     r8, [rsp+108h+var_98]
0x1802cb6bb  mov     rdx, [rax]
0x1802cb6be  mov     rcx, rdi
0x1802cb6c1  mov     rax, rbx
0x1802cb6c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802cb6c9  mov     r8d, eax
0x1802cb6cc  test    eax, eax
0x1802cb6ce  jns     short loc_1802CB70C
0x1802cb6d0  lea     rax, aUserauthmanage; ".\\userauthmanager.cpp"
0x1802cb6d7  mov     [rsp+108h+var_D8], rax
0x1802cb6dc  mov     [rsp+108h+var_D0], 111h
0x1802cb6e4  lea     r9, aCouldnTGetXuid_0; "Couldn't get xuid"
0x1802cb6eb  lea     rdx, [rsp+108h+var_D8]
0x1802cb6f0  lea     rcx, [rsp+108h+var_58]
0x1802cb6f8  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x1802cb6fd  nop
0x1802cb6fe  mov     rdx, rax
0x1802cb701  lea     rcx, [rsp+108h+var_D8]
0x1802cb706  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1802cb70c  lea     rdx, [rsp+108h+var_80]
0x1802cb714  lea     rcx, [rsp+108h+var_98]
0x1802cb719  call    ??$As@UIPropertyValue@Foundation@Windows@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIPropertyValue@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValue>>)
0x1802cb71e  mov     r8d, eax
0x1802cb721  test    eax, eax
0x1802cb723  jns     short loc_1802CB761
0x1802cb725  lea     rax, aUserauthmanage; ".\\userauthmanager.cpp"
0x1802cb72c  mov     [rsp+108h+var_D8], rax
0x1802cb731  mov     [rsp+108h+var_D0], 112h
0x1802cb739  lea     r9, aCouldnTConvert_0; "Couldn't convert inspectable to propval"...
0x1802cb740  lea     rdx, [rsp+108h+var_D8]
0x1802cb745  lea     rcx, [rsp+108h+var_58]
0x1802cb74d  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x1802cb752  nop
0x1802cb753  mov     rdx, rax
0x1802cb756  lea     rcx, [rsp+108h+var_D8]
0x1802cb75b  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1802cb761  mov     rdi, [rsp+108h+var_80]
0x1802cb769  mov     rax, [rdi]
0x1802cb76c  mov     rbx, [rax+98h]
0x1802cb773  mov     rcx, [rsp+108h+string]; string
0x1802cb778  call    cs:__imp_WindowsDeleteString
0x1802cb77e  mov     [rsp+108h+string], rsi
0x1802cb783  lea     rdx, [rsp+108h+string]
0x1802cb788  mov     rcx, rdi
0x1802cb78b  mov     rax, rbx
0x1802cb78e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802cb793  mov     r8d, eax
0x1802cb796  test    eax, eax
0x1802cb798  jns     short loc_1802CB7D6
0x1802cb79a  lea     rax, aUserauthmanage; ".\\userauthmanager.cpp"
0x1802cb7a1  mov     [rsp+108h+var_D8], rax
0x1802cb7a6  mov     [rsp+108h+var_D0], 113h
0x1802cb7ae  lea     r9, aCouldnTGetXuid; "Couldn't get xuid string."
0x1802cb7b5  lea     rdx, [rsp+108h+var_D8]
0x1802cb7ba  lea     rcx, [rsp+108h+var_58]
0x1802cb7c2  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x1802cb7c7  nop
0x1802cb7c8  mov     rdx, rax
0x1802cb7cb  lea     rcx, [rsp+108h+var_D8]
0x1802cb7d0  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1802cb7d6  lea     rdx, [rsp+108h+var_78]
0x1802cb7de  mov     rcx, r15
0x1802cb7e1  call    ?lock@?$weak_ptr@VProximalConnector@cdp@@@std@@QEBA?AV?$shared_ptr@VProximalConnector@cdp@@@2@XZ; std::weak_ptr<cdp::ProximalConnector>::lock(void)
0x1802cb7e6  nop
0x1802cb7e7  cmp     [rsp+108h+var_78], rsi
0x1802cb7ef  jz      short loc_1802CB83F
0x1802cb7f1  xor     edx, edx; length
0x1802cb7f3  mov     rcx, [rsp+108h+string]; string
0x1802cb7f8  call    cs:__imp_WindowsGetStringRawBuffer
0x1802cb7fe  mov     rdx, rax
0x1802cb801  lea     rcx, [rsp+108h+var_58]
0x1802cb809  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1802cb80e  nop
0x1802cb80f  mov     rdx, rax
0x1802cb812  lea     rcx, [rsp+108h+var_D8]
0x1802cb817  call    ?ToUtf8@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; cdp::ToUtf8(std::wstring const &)
0x1802cb81c  mov     r8, rax
0x1802cb81f  mov     edx, [rsp+108h+var_B8]
0x1802cb823  mov     rcx, [rsp+108h+var_78]
0x1802cb82b  call    ?OnXboxUserSignIn@UserAuthManager@cdp@@AEAAXIV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; cdp::UserAuthManager::OnXboxUserSignIn(uint,std::string)
0x1802cb830  nop
0x1802cb831  lea     rcx, [rsp+108h+var_58]
0x1802cb839  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1802cb83e  nop
0x1802cb83f  mov     rcx, [rsp+108h+var_70]; this
0x1802cb847  test    rcx, rcx
0x1802cb84a  jz      short loc_1802CB852
0x1802cb84c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1802cb851  nop
0x1802cb852  lea     rcx, [rsp+108h+var_80]
0x1802cb85a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1802cb85f  nop
0x1802cb860  lea     rcx, [rsp+108h+var_98]
0x1802cb865  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1802cb86a  nop
0x1802cb86b  lea     rcx, [rsp+108h+var_A0]
0x1802cb870  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1802cb875  nop
0x1802cb876  mov     rcx, [rsp+108h+var_90]
0x1802cb87b  test    rcx, rcx
0x1802cb87e  jz      short loc_1802CB892
0x1802cb880  mov     [rsp+108h+var_90], rsi
0x1802cb885  mov     rax, [rcx]
0x1802cb888  mov     rax, [rax+10h]
0x1802cb88c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802cb891  nop
0x1802cb892  mov     rcx, [rsp+108h+string]; string
0x1802cb897  call    cs:__imp_WindowsDeleteString
0x1802cb89d  nop
0x1802cb89e  lea     rcx, [rsp+108h+var_88]
0x1802cb8a6  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1802cb8ab  nop
0x1802cb8ac  jmp     short loc_1802CB8B8
0x1802cb8ae  xor     esi, esi
0x1802cb8b0  mov     r14, [rsp+108h+var_68]
0x1802cb8b8  mov     rcx, r14; _Mtx_t
0x1802cb8bb  call    cs:__imp__Mtx_unlock
0x1802cb8c1  nop
0x1802cb8c2  mov     rcx, [rsp+108h+var_A8]
0x1802cb8c7  test    rcx, rcx
0x1802cb8ca  jz      short loc_1802CB8DE
0x1802cb8cc  mov     [rsp+108h+var_A8], rsi
0x1802cb8d1  mov     rax, [rcx]
0x1802cb8d4  mov     rax, [rax+10h]
0x1802cb8d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802cb8dd  nop
0x1802cb8de  xor     eax, eax
0x1802cb8e0  mov     rcx, [rsp+108h+var_20]
0x1802cb8e8  xor     rcx, rsp; StackCookie
0x1802cb8eb  call    __security_check_cookie
0x1802cb8f0  lea     r11, [rsp+108h+var_18]
0x1802cb8f8  mov     rbx, [r11+28h]
0x1802cb8fc  mov     rsi, [r11+38h]
0x1802cb900  mov     rsp, r11
0x1802cb903  pop     r15
0x1802cb905  pop     r14
0x1802cb907  pop     rdi
0x1802cb908  retn
```
