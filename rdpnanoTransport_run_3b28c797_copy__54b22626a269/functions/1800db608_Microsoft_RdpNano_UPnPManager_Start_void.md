# Microsoft::RdpNano::UPnPManager::Start(void)

- ea: `0x1800db608`
- end: `0x1800dbaa9`
- name: `?Start@UPnPManager@RdpNano@Microsoft@@QEAAXXZ`
- size: `1185`
- prototype: `void __fastcall(Microsoft::RdpNano::UPnPManager *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800b9d9c`

## callees

- `0x180015738`
- `0x180015bb8`
- `0x180017404`
- `0x180024700`
- `0x180027b84`
- `0x1800b9798`
- `0x1800d2f14`
- `0x1800d2f8c`
- `0x1800d30c8`
- `0x1800d6154`
- `0x1800db4bc`
- `0x1800db608`
- `0x1802e9e58`
- `0x1802ea490`
- `0x18032f050`
- `0x18032f0b0`
- `0x18032f100`
- `0x1803304e0`
- `0x180330b40`
- `0x180375c40`

## string_xrefs

- `0x1800db93e`: `C:\__w\1\s\externals\vcpkg_installed\x64-windows-static\include\wil\result_macros.h`
- `0x1800db96d`: `C:\__w\1\s\rdpnanodll\upnp\upnpmanager.cpp`
- `0x1800dba17`: `C:\__w\1\s\rdpnanodll\upnp\upnpmanager.cpp`
- `0x1800db982`: `Failed to create async search`

## pseudocode

```c
// Hidden C++ exception states: #wind=25
void __fastcall Microsoft::RdpNano::UPnPManager::Start(Microsoft::RdpNano::UPnPManager *this)
{
  Microsoft::RdpNano::UPnPManager *v1; // r14
  __int64 *v2; // rax
  __int64 v3; // r8
  _QWORD *v4; // rsi
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r9
  __int64 v8; // rax
  __int64 (__fastcall ***v9)(_QWORD, GUID *, __int64); // r9
  int v10; // eax
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rcx
  _QWORD *v15; // rdi
  char *v16; // rcx
  __int64 v17; // r15
  __int64 v18; // r13
  _bstr_t::Data_t *v19; // rax
  unsigned int *v20; // r12
  int v21; // esi
  __int64 v22; // rcx
  _QWORD *v23; // rdx
  __int64 v24; // rcx
  Microsoft::Basix *v25; // rcx
  const struct std::error_category *v26; // rax
  Microsoft::Basix *v27; // rcx
  const struct std::error_category *v28; // rax
  __int64 Description; // rbx
  volatile signed __int32 *v30; // rbx
  Microsoft::RdpNano::UPnPManager *v31; // rbx
  __int64 v32; // rax
  int v33; // [rsp+20h] [rbp-228h]
  _bstr_t::Data_t *v34; // [rsp+30h] [rbp-218h] BYREF
  char v35; // [rsp+38h] [rbp-210h]
  __int128 v36; // [rsp+40h] [rbp-208h] BYREF
  __int128 v37; // [rsp+50h] [rbp-1F8h] BYREF
  __int64 v38; // [rsp+60h] [rbp-1E8h]
  __int64 v39; // [rsp+68h] [rbp-1E0h]
  Microsoft::RdpNano::UPnPManager *v40; // [rsp+70h] [rbp-1D8h]
  _BYTE v41[32]; // [rsp+78h] [rbp-1D0h] BYREF
  wil::ResultException *v42; // [rsp+98h] [rbp-1B0h] BYREF
  _BYTE v43[32]; // [rsp+A0h] [rbp-1A8h] BYREF
  _BYTE v44[32]; // [rsp+C0h] [rbp-188h] BYREF
  _BYTE pExceptionObject[144]; // [rsp+E0h] [rbp-168h] BYREF
  _BYTE v46[144]; // [rsp+170h] [rbp-D8h] BYREF
  _QWORD *v47; // [rsp+200h] [rbp-48h] BYREF
  __int128 v48; // [rsp+208h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+0h]

  v1 = this;
  v40 = this;
  v2 = wil::CoCreateInstance<IUPnPDeviceFinder,wil::err_exception_policy>(&v37, &CLSID_UPnPDeviceFinder, 1u);
  v4 = (_QWORD *)((char *)v1 + 16);
  v47 = (_QWORD *)((char *)v1 + 16);
  v5 = *v2;
  *v2 = 0;
  v6 = *((_QWORD *)v1 + 2);
  *((_QWORD *)v1 + 2) = v5;
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  if ( (_QWORD)v37 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v37 + 16LL))(v37);
  try
  {
    v7 = *v4;
    v34 = 0;
    v8 = (*(__int64 (__fastcall **)(_bstr_t::Data_t **, __int64, __int64, __int64))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)(
           &v34,
           v5,
           v3,
           v7);
    v10 = (**v9)(v9, &GUID_8dcc8327_dbe9_48e6_846c_33725865d50c, v8);
    if ( v10 < 0 )
    {
      _mm_lfence();
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1C89,
        (unsigned int)"C:\\__w\\1\\s\\externals\\vcpkg_installed\\x64-windows-static\\include\\wil\\result_macros.h",
        (const char *)(unsigned int)v10,
        v33);
    }
    (*(void (__fastcall **)(_bstr_t::Data_t *))(*(_QWORD *)v34 + 24LL))(v34);
    if ( v34 )
      (*(void (__fastcall **)(_bstr_t::Data_t *))(*(_QWORD *)v34 + 16LL))(v34);
  }
  catch ( wil::ResultException *v42 )
  {
    v48 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v48);
    if ( (_QWORD)v48 && *(_BYTE *)(v48 + 128) )
    {
      *(_QWORD *)&v36 = v41;
      Description = Microsoft::Basix::Exception::CreateDescription(v41, v42);
      v37 = 0;
      v38 = 0;
      v39 = 0;
      std::string::_Construct<1,char const *>(&v37, "Failed to disable eventing: %s", (const char *)0x1E);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,std::string>(
        &v48,
        "RDPNANO",
        &v37,
        Description);
      std::string::_Tidy_deallocate(&v37);
    }
    v30 = (volatile signed __int32 *)*((_QWORD *)&v48 + 1);
    if ( *((_QWORD *)&v48 + 1)
      && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v48 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v30)(v30);
      if ( _InterlockedExchangeAdd(v30 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v30 + 8LL))(v30);
    }
    v4 = v47;
    v1 = v40;
  }
  try
  {
    v34 = 0;
    v11 = std::operator+<char>(v41, &qword_18053D300, "1");
    if ( *(_QWORD *)(v11 + 24) > 0xFu )
      v11 = *(_QWORD *)v11;
    _bstr_t::_bstr_t((_bstr_t *)&v34, (const char *)v11);
    std::string::_Tidy_deallocate(v41);
    v47 = 0;
    v12 = Microsoft::Basix::SharedFromThisVirtualBase::GetWeakPtr<Microsoft::RdpNano::UPnPManager>(
            (char *)v1 + *(int *)(*(_QWORD *)v1 + 4LL),
            &v48);
    Microsoft::Basix::WinUtils::ComObject<Microsoft::RdpNano::UPnPManager::DeviceCallback,IUPnPDeviceFinderAddCallbackWithInterface,IUPnPDeviceFinderCallback>::Create<std::weak_ptr<Microsoft::RdpNano::UPnPManager>>(
      &v47,
      v12);
    v14 = *((_QWORD *)&v48 + 1);
    if ( *((_QWORD *)&v48 + 1)
      && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v48 + 1) + 12LL), 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
    }
    v15 = v47;
    *(_QWORD *)&v48 = v47;
    if ( v47 )
    {
      v16 = (char *)v47 + *(int *)(v47[2] + 4LL) + 16;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v16 + 8LL))(v16);
    }
    v17 = *v4;
    *(_QWORD *)&v36 = *(_QWORD *)(*(_QWORD *)*v4 + 64LL);
    LOBYTE(v13) = v35;
    wil::com_ptr_t<IUnknown,wil::err_exception_policy>::com_ptr_t<IUnknown,wil::err_exception_policy>(&v37, v15, v13);
    v18 = v37;
    v19 = v34;
    if ( v34
      || ((v19 = (_bstr_t::Data_t *)operator new(0x18u), (v34 = v19) == 0)
        ? (v19 = 0)
        : (_bstr_t::Data_t *)(*((_QWORD *)v19 + 2) = 1, *((_QWORD *)v19 + 1) = 0, *(_QWORD *)v19 = 0),
          (v34 = v19) != 0) )
    {
      v20 = (unsigned int *)((char *)v1 + 24);
      LODWORD(v1) = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, __int64, char *))v36)(
                      v17,
                      *(_QWORD *)v19,
                      0,
                      v18,
                      (char *)v1 + 24);
      if ( (_QWORD)v37 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v37 + 16LL))(v37);
      if ( (int)v1 >= 0 )
      {
        _mm_lfence();
        v21 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v4 + 72LL))(*v4, *v20);
        if ( v21 < 0 )
        {
          std::string::string(v44, (const char *)&Str1);
          std::string::string(v43, "C:\\__w\\1\\s\\rdpnanodll\\upnp\\upnpmanager.cpp");
          std::string::string(v41, "Failed to start async search");
          v28 = Microsoft::Basix::WindowsCategory(v27);
          _mm_lfence();
          v36 = *(_OWORD *)std::error_code::error_code((std::error_code *)&v37, v21, v28);
          Microsoft::Basix::SystemException::SystemException(
            (unsigned int)v46,
            (unsigned int)&v36,
            (unsigned int)v41,
            (unsigned int)v43,
            783,
            (__int64)v44);
          throw (Microsoft::Basix::SystemException *)v46;
        }
        if ( v15 )
        {
          v22 = (__int64)v15 + *(int *)(v15[2] + 4LL) + 16;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
        }
        v23 = v47;
        if ( v47 )
        {
          v47 = 0;
          v24 = (__int64)v23 + *(int *)(v23[2] + 4LL) + 16;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
        }
        if ( v34 )
          _bstr_t::Data_t::Release(v34);
        return;
      }
    }
    else
    {
      _com_issue_error(-2147024882);
    }
    std::string::string(v41, (const char *)&Str1);
    std::string::string(v43, "C:\\__w\\1\\s\\rdpnanodll\\upnp\\upnpmanager.cpp");
    std::string::string(v44, "Failed to create async search");
    v26 = Microsoft::Basix::WindowsCategory(v25);
    _mm_lfence();
    v36 = *(_OWORD *)std::error_code::error_code((std::error_code *)&v37, (int)v1, v26);
    Microsoft::Basix::SystemException::SystemException(
      (unsigned int)pExceptionObject,
      (unsigned int)&v36,
      (unsigned int)v44,
      (unsigned int)v43,
      782,
      (__int64)v41);
    throw (Microsoft::Basix::SystemException *)pExceptionObject;
  }
  catch ( std::exception )
  {
    v31 = v40;
    v32 = boost::movelib::iterator_to_raw_pointer<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger> *>((char *)v40 + 16);
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v32 + 80LL))(v32, *((unsigned int *)v31 + 6));
    wil::com_ptr_t<IUPnPDeviceFinder,wil::err_exception_policy>::operator=((char *)v31 + 16, 0);
    throw;
  }
}

```

## disassembly

```asm
0x1800db608  mov     [rsp+arg_8], rbx
0x1800db60d  mov     [rsp+arg_10], rsi
0x1800db612  push    rdi
0x1800db613  push    r12
0x1800db615  push    r13
0x1800db617  push    r14
0x1800db619  push    r15
0x1800db61b  mov     eax, 220h
0x1800db620  call    _alloca_probe
0x1800db625  sub     rsp, rax
0x1800db628  mov     rax, cs:__security_cookie
0x1800db62f  xor     rax, rsp
0x1800db632  mov     [rsp+248h+var_30], rax
0x1800db63a  mov     r14, rcx
0x1800db63d  mov     [rsp+248h+var_1D8], rcx
0x1800db642  xor     ebx, ebx
0x1800db644  lea     r8d, [rbx+1]
0x1800db648  lea     rdx, CLSID_UPnPDeviceFinder
0x1800db64f  lea     rcx, [rsp+248h+var_1F8]
0x1800db654  call    ??$CoCreateInstance@UIUPnPDeviceFinder@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIUPnPDeviceFinder@@Uerr_exception_policy@wil@@@0@AEBU_GUID@@K@Z; wil::CoCreateInstance<IUPnPDeviceFinder,wil::err_exception_policy>(_GUID const &,ulong)
0x1800db659  lea     rsi, [r14+10h]
0x1800db65d  mov     [rsp+248h+var_48], rsi
0x1800db665  mov     rdx, [rax]
0x1800db668  mov     [rax], rbx
0x1800db66b  mov     rcx, [rsi]
0x1800db66e  mov     [rsi], rdx
0x1800db671  test    rcx, rcx
0x1800db674  jz      short loc_1800DB684
0x1800db676  mov     rax, [rcx]
0x1800db679  mov     rax, [rax+10h]
0x1800db67d  call    cs:__guard_dispatch_icall_fptr
0x1800db683  nop
0x1800db684  mov     rcx, qword ptr [rsp+248h+var_1F8]
0x1800db689  test    rcx, rcx
0x1800db68c  jz      short loc_1800DB69C
0x1800db68e  mov     rax, [rcx]
0x1800db691  mov     rax, [rax+10h]
0x1800db695  call    cs:__guard_dispatch_icall_fptr
0x1800db69b  nop
0x1800db69c  mov     r9, [rsi]
0x1800db69f  mov     [rsp+248h+var_218], rbx
0x1800db6a4  lea     rcx, [rsp+248h+var_218]
0x1800db6a9  call    near ptr ??$launder@USecurityCookieHash@RdpNano@Microsoft@@@core@boost@@YAPEAUSecurityCookieHash@RdpNano@Microsoft@@PEAU234@@Z.Data1; boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>(Microsoft::RdpNano::SecurityCookieHash *)
0x1800db6ae  mov     r8, rax
0x1800db6b1  mov     rax, [r9]
0x1800db6b4  lea     rdx, _GUID_8dcc8327_dbe9_48e6_846c_33725865d50c
0x1800db6bb  mov     rcx, r9
0x1800db6be  mov     rax, [rax]
0x1800db6c1  call    cs:__guard_dispatch_icall_fptr
0x1800db6c7  mov     rcx, [rsp+248h]; this
0x1800db6cf  test    eax, eax
0x1800db6d1  js      loc_1800DB938
0x1800db6d7  mov     rcx, [rsp+248h+var_218]
0x1800db6dc  mov     rax, [rcx]
0x1800db6df  mov     rax, [rax+18h]
0x1800db6e3  call    cs:__guard_dispatch_icall_fptr
0x1800db6e9  nop
0x1800db6ea  mov     rcx, [rsp+248h+var_218]
0x1800db6ef  test    rcx, rcx
0x1800db6f2  jz      short loc_1800DB702
0x1800db6f4  mov     rax, [rcx]
0x1800db6f7  mov     rax, [rax+10h]
0x1800db6fb  call    cs:__guard_dispatch_icall_fptr
0x1800db701  nop
0x1800db702  jmp     short loc_1800DB713
0x1800db704  xor     ebx, ebx
0x1800db706  mov     rsi, [rsp+248h+var_48]
0x1800db70e  mov     r14, [rsp+248h+var_1D8]
0x1800db713  mov     [rsp+248h+var_218], rbx
0x1800db718  lea     r8, a1; "1"
0x1800db71f  lea     rdx, qword_18053D300
0x1800db726  lea     rcx, [rsp+248h+var_1D0]
0x1800db72b  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@AEBV10@QEBD@Z; std::operator+<char>(std::string const &,char const * const)
0x1800db730  nop
0x1800db731  cmp     qword ptr [rax+18h], 0Fh
0x1800db736  jbe     short loc_1800DB73B
0x1800db738  mov     rax, [rax]
0x1800db73b  mov     rdx, rax; char *
0x1800db73e  lea     rcx, [rsp+248h+var_218]; this
0x1800db743  call    ??0_bstr_t@@QEAA@PEBD@Z; _bstr_t::_bstr_t(char const *)
0x1800db748  nop
0x1800db749  lea     rcx, [rsp+248h+var_1D0]
0x1800db74e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800db753  mov     [rsp+248h+var_48], rbx
0x1800db75b  mov     rax, [r14]
0x1800db75e  movsxd  rcx, dword ptr [rax+4]
0x1800db762  add     rcx, r14
0x1800db765  lea     rdx, [rsp+248h+var_40]
0x1800db76d  call    ??$GetWeakPtr@VUPnPManager@RdpNano@Microsoft@@@SharedFromThisVirtualBase@Basix@Microsoft@@QEAA?AV?$weak_ptr@VUPnPManager@RdpNano@Microsoft@@@std@@XZ; Microsoft::Basix::SharedFromThisVirtualBase::GetWeakPtr<Microsoft::RdpNano::UPnPManager>(void)
0x1800db772  nop
0x1800db773  mov     rdx, rax
0x1800db776  lea     rcx, [rsp+248h+var_48]
0x1800db77e  call    ??$Create@V?$weak_ptr@VUPnPManager@RdpNano@Microsoft@@@std@@@?$ComObject@VDeviceCallback@UPnPManager@RdpNano@Microsoft@@UIUPnPDeviceFinderAddCallbackWithInterface@@UIUPnPDeviceFinderCallback@@@WinUtils@Basix@Microsoft@@SA?AV?$ComPtr@VDeviceCallback@UPnPManager@RdpNano@Microsoft@@@WRL@3@$$QEAV?$weak_ptr@VUPnPManager@RdpNano@Microsoft@@@std@@@Z; Microsoft::Basix::WinUtils::ComObject<Microsoft::RdpNano::UPnPManager::DeviceCallback,IUPnPDeviceFinderAddCallbackWithInterface,IUPnPDeviceFinderCallback>::Create<std::weak_ptr<Microsoft::RdpNano::UPnPManager>>(std::weak_ptr<Microsoft::RdpNano::UPnPManager> &&)
0x1800db783  nop
0x1800db784  mov     rcx, [rsp+248h+var_38]
0x1800db78c  test    rcx, rcx
0x1800db78f  jz      short loc_1800DB7AB
0x1800db791  or      eax, 0FFFFFFFFh
0x1800db794  lock xadd [rcx+0Ch], eax
0x1800db799  cmp     eax, 1
0x1800db79c  jnz     short loc_1800DB7AB
0x1800db79e  mov     rax, [rcx]
0x1800db7a1  mov     rax, [rax+8]
0x1800db7a5  call    cs:__guard_dispatch_icall_fptr
0x1800db7ab  mov     rdi, [rsp+248h+var_48]
0x1800db7b3  mov     [rsp+248h+var_40], rdi
0x1800db7bb  test    rdi, rdi
0x1800db7be  jz      short loc_1800DB7DD
0x1800db7c0  mov     rax, [rdi+10h]
0x1800db7c4  movsxd  rcx, dword ptr [rax+4]
0x1800db7c8  add     rcx, 10h
0x1800db7cc  add     rcx, rdi
0x1800db7cf  mov     rax, [rcx]
0x1800db7d2  mov     rax, [rax+8]
0x1800db7d6  call    cs:__guard_dispatch_icall_fptr
0x1800db7dc  nop
0x1800db7dd  mov     r15, [rsi]
0x1800db7e0  mov     rax, [r15]
0x1800db7e3  mov     rax, [rax+40h]
0x1800db7e7  mov     qword ptr [rsp+248h+var_208], rax
0x1800db7ec  mov     r8b, [rsp+248h+var_210]
0x1800db7f1  mov     rdx, rdi
0x1800db7f4  lea     rcx, [rsp+248h+var_1F8]
0x1800db7f9  call    ??$?0VDeviceCallback@UPnPManager@RdpNano@Microsoft@@@?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAVDeviceCallback@UPnPManager@RdpNano@Microsoft@@U?$integral_constant@D$0A@@wistd@@@Z; wil::com_ptr_t<IUnknown,wil::err_exception_policy>::com_ptr_t<IUnknown,wil::err_exception_policy>(Microsoft::RdpNano::UPnPManager::DeviceCallback *,wistd::integral_constant<char,0>)
0x1800db7fe  nop
0x1800db7ff  mov     r13, qword ptr [rsp+248h+var_1F8]
0x1800db804  mov     rax, [rsp+248h+var_218]
0x1800db809  test    rax, rax
0x1800db80c  jnz     short loc_1800DB842
0x1800db80e  lea     ecx, [rax+18h]; Size
0x1800db811  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800db816  mov     [rsp+248h+var_218], rax
0x1800db81b  test    rax, rax
0x1800db81e  jz      short loc_1800DB831
0x1800db820  mov     qword ptr [rax+10h], 1
0x1800db828  mov     [rax+8], rbx
0x1800db82c  mov     [rax], rbx
0x1800db82f  jmp     short loc_1800DB834
0x1800db831  mov     rax, rbx
0x1800db834  mov     [rsp+248h+var_218], rax
0x1800db839  test    rax, rax
0x1800db83c  jz      loc_1800DB950
0x1800db842  lea     r12, [r14+18h]
0x1800db846  mov     [rsp+248h+var_228], r12
0x1800db84b  mov     r9, r13
0x1800db84e  xor     r8d, r8d
0x1800db851  mov     rdx, [rax]
0x1800db854  mov     rcx, r15
0x1800db857  mov     rax, qword ptr [rsp+248h+var_208]
0x1800db85c  call    cs:__guard_dispatch_icall_fptr
0x1800db862  mov     r14d, eax
0x1800db865  mov     rcx, qword ptr [rsp+248h+var_1F8]
0x1800db86a  test    rcx, rcx
0x1800db86d  jz      short loc_1800DB87D
0x1800db86f  mov     rdx, [rcx]
0x1800db872  mov     rax, [rdx+10h]
0x1800db876  call    cs:__guard_dispatch_icall_fptr
0x1800db87c  nop
0x1800db87d  test    r14d, r14d
0x1800db880  js      loc_1800DB95B
0x1800db886  lfence
0x1800db889  mov     rcx, [rsi]
0x1800db88c  mov     rax, [rcx]
0x1800db88f  mov     edx, [r12]
0x1800db893  mov     rax, [rax+48h]
0x1800db897  call    cs:__guard_dispatch_icall_fptr
0x1800db89d  mov     esi, eax
0x1800db89f  test    eax, eax
0x1800db8a1  js      loc_1800DBA02
0x1800db8a7  test    rdi, rdi
0x1800db8aa  jz      short loc_1800DB8C9
0x1800db8ac  mov     rax, [rdi+10h]
0x1800db8b0  movsxd  rcx, dword ptr [rax+4]
0x1800db8b4  add     rcx, 10h
0x1800db8b8  add     rcx, rdi
0x1800db8bb  mov     rax, [rcx]
0x1800db8be  mov     rax, [rax+10h]
0x1800db8c2  call    cs:__guard_dispatch_icall_fptr
0x1800db8c8  nop
0x1800db8c9  mov     rdx, [rsp+248h+var_48]
0x1800db8d1  test    rdx, rdx
0x1800db8d4  jz      short loc_1800DB8FB
0x1800db8d6  mov     [rsp+248h+var_48], rbx
0x1800db8de  mov     rax, [rdx+10h]
0x1800db8e2  movsxd  rcx, dword ptr [rax+4]
0x1800db8e6  add     rdx, 10h
0x1800db8ea  add     rcx, rdx
0x1800db8ed  mov     rax, [rcx]
0x1800db8f0  mov     rax, [rax+10h]
0x1800db8f4  call    cs:__guard_dispatch_icall_fptr
0x1800db8fa  nop
0x1800db8fb  mov     rcx, [rsp+248h+var_218]; this
0x1800db900  test    rcx, rcx
0x1800db903  jz      short loc_1800DB90B
0x1800db905  call    ?Release@Data_t@_bstr_t@@QEAAKXZ; _bstr_t::Data_t::Release(void)
0x1800db90a  nop
0x1800db90b  mov     rcx, [rsp+248h+var_30]
0x1800db913  xor     rcx, rsp; StackCookie
0x1800db916  call    __security_check_cookie
0x1800db91b  lea     r11, [rsp+248h+var_28]
0x1800db923  mov     rbx, [r11+38h]
0x1800db927  mov     rsi, [r11+40h]
0x1800db92b  mov     rsp, r11
0x1800db92e  pop     r15
0x1800db930  pop     r14
0x1800db932  pop     r13
0x1800db934  pop     r12
0x1800db936  pop     rdi
0x1800db937  retn
0x1800db938  lfence
0x1800db93b  mov     r9d, eax; char *
0x1800db93e  lea     r8, aCW1SExternalsV_12; "C:\\__w\\1\\s\\externals\\vcpkg_install"...
0x1800db945  mov     edx, 1C89h; void *
0x1800db94a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800db950  mov     ecx, 8007000Eh; int
0x1800db955  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800db95a  nop
0x1800db95b  lea     rdx, Str1
0x1800db962  lea     rcx, [rsp+248h+var_1D0]
0x1800db967  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800db96c  nop
0x1800db96d  lea     rdx, aCW1SRdpnanodll_13; "C:\\__w\\1\\s\\rdpnanodll\\upnp\\upnpma"...
0x1800db974  lea     rcx, [rsp+248h+var_1A8]
0x1800db97c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800db981  nop
0x1800db982  lea     rdx, aFailedToCreate_0; "Failed to create async search"
0x1800db989  lea     rcx, [rsp+248h+var_188]
0x1800db991  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800db996  nop
0x1800db997  call    ?WindowsCategory@Basix@Microsoft@@YAAEBVerror_category@std@@XZ; Microsoft::Basix::WindowsCategory(void)
0x1800db99c  lfence
0x1800db99f  mov     r8, rax; struct std::error_category *
0x1800db9a2  mov     edx, r14d; int
0x1800db9a5  lea     rcx, [rsp+248h+var_1F8]; this
0x1800db9aa  call    ??0error_code@std@@QEAA@HAEBVerror_category@1@@Z; std::error_code::error_code(int,std::error_category const &)
0x1800db9af  movups  xmm0, xmmword ptr [rax]
0x1800db9b2  movdqu  [rsp+248h+var_208], xmm0
0x1800db9b8  lea     rax, [rsp+248h+var_1D0]
0x1800db9bd  mov     [rsp+248h+var_220], rax
0x1800db9c2  mov     [rsp+248h+var_228], 30Eh
0x1800db9cb  lea     r9, [rsp+248h+var_1A8]
0x1800db9d3  lea     r8, [rsp+248h+var_188]
0x1800db9db  lea     rdx, [rsp+248h+var_208]
0x1800db9e0  lea     rcx, [rsp+248h+pExceptionObject]
0x1800db9e8  call    ??0SystemException@Basix@Microsoft@@QEAA@Verror_code@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@1_K1@Z; Microsoft::Basix::SystemException::SystemException(std::error_code,std::string const &,std::string const &,unsigned __int64,std::string const &)
0x1800db9ed  lea     rdx, _TI6?AVSystemException@Basix@Microsoft@@; pThrowInfo
0x1800db9f4  lea     rcx, [rsp+248h+pExceptionObject]; pExceptionObject
0x1800db9fc  call    _CxxThrowException
0x1800dba02  lea     rdx, Str1
0x1800dba09  lea     rcx, [rsp+248h+var_188]
0x1800dba11  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800dba16  nop
0x1800dba17  lea     rdx, aCW1SRdpnanodll_13; "C:\\__w\\1\\s\\rdpnanodll\\upnp\\upnpma"...
0x1800dba1e  lea     rcx, [rsp+248h+var_1A8]
0x1800dba26  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800dba2b  nop
0x1800dba2c  lea     rdx, aFailedToStartA; "Failed to start async search"
0x1800dba33  lea     rcx, [rsp+248h+var_1D0]
0x1800dba38  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800dba3d  nop
0x1800dba3e  call    ?WindowsCategory@Basix@Microsoft@@YAAEBVerror_category@std@@XZ; Microsoft::Basix::WindowsCategory(void)
0x1800dba43  lfence
0x1800dba46  mov     r8, rax; struct std::error_category *
0x1800dba49  mov     edx, esi; int
0x1800dba4b  lea     rcx, [rsp+248h+var_1F8]; this
0x1800dba50  call    ??0error_code@std@@QEAA@HAEBVerror_category@1@@Z; std::error_code::error_code(int,std::error_category const &)
0x1800dba55  movups  xmm0, xmmword ptr [rax]
0x1800dba58  movdqu  [rsp+248h+var_208], xmm0
0x1800dba5e  lea     rax, [rsp+248h+var_188]
0x1800dba66  mov     [rsp+248h+var_220], rax
0x1800dba6b  mov     [rsp+248h+var_228], 30Fh
0x1800dba74  lea     r9, [rsp+248h+var_1A8]
0x1800dba7c  lea     r8, [rsp+248h+var_1D0]
0x1800dba81  lea     rdx, [rsp+248h+var_208]
0x1800dba86  lea     rcx, [rsp+248h+var_D8]
0x1800dba8e  call    ??0SystemException@Basix@Microsoft@@QEAA@Verror_code@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@1_K1@Z; Microsoft::Basix::SystemException::SystemException(std::error_code,std::string const &,std::string const &,unsigned __int64,std::string const &)
0x1800dba93  lea     rdx, _TI6?AVSystemException@Basix@Microsoft@@; pThrowInfo
0x1800dba9a  lea     rcx, [rsp+248h+var_D8]; pExceptionObject
0x1800dbaa2  call    _CxxThrowException
```
