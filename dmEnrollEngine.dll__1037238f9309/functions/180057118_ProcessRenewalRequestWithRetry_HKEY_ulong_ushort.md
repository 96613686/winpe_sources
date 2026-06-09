# ProcessRenewalRequestWithRetry(HKEY__ *,ulong,ushort * *)

- ea: `0x180057118`
- end: `0x180057669`
- name: `?ProcessRenewalRequestWithRetry@@YAJPEAUHKEY__@@KPEAPEAG@Z`
- size: `1361`
- prototype: `__int64 __fastcall(HKEY, unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001b3ac`

## callees

- `0x18000e508`
- `0x180011938`
- `0x18001aec8`
- `0x180020cb4`
- `0x18002e1a0`
- `0x18003aabc`
- `0x18003c968`
- `0x18003dba8`
- `0x180045e08`
- `0x180054f1c`
- `0x180057118`
- `0x18005792c`
- `0x180057994`
- `0x180058b20`
- `0x1800728e0`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180057238`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180057238`
- `OLEAUT32!__imp_SysAllocString` at `0x180057174`
- `OLEAUT32!__imp_SysAllocString` at `0x180057174`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x18005716a`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x18005716a`

## string_xrefs

- `0x18005724d`: `CoCreateInstance IX509CertificateRequestPkcs7`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall ProcessRenewalRequestWithRetry(HKEY a1, char a2, unsigned __int16 **a3)
{
  OLECHAR *v6; // rbx
  unsigned int v7; // edi
  int v8; // edi
  CEnrollmentLogger *v9; // rax
  __int64 v10; // rcx
  HRESULT v11; // eax
  __int64 v12; // rcx
  const wchar_t *v13; // r8
  CEnrollmentLogger *Logger; // rax
  LPVOID v15; // rdi
  __int64 (__fastcall *v16)(LPVOID, __int64, __int64); // rbx
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // rcx
  unsigned int v20; // esi
  unsigned __int16 *v21; // rax
  LPVOID v22; // rdi
  __int64 (__fastcall *v23)(LPVOID, _QWORD, _QWORD); // rbx
  int v24; // eax
  __int64 v25; // rdx
  __int64 (__fastcall ***v26)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v27)(_QWORD, GUID *, __int64 *); // rbx
  int v28; // eax
  __int64 v29; // rdi
  __int64 (__fastcall *v30)(__int64, __int64 *); // rbx
  int v31; // eax
  __int64 v32; // rdi
  __int64 (__fastcall *v33)(__int64, __int64); // rbx
  __int64 v34; // rax
  int v35; // eax
  __int64 v36; // rdi
  __int64 (__fastcall *v37)(__int64, __int64); // rbx
  __int64 v38; // rax
  int v39; // eax
  __int64 v40; // rdx
  int ppv; // [rsp+20h] [rbp-E0h]
  LPVOID v43; // [rsp+40h] [rbp-C0h] BYREF
  __int64 (__fastcall ***v44)(_QWORD, GUID *, __int64 *); // [rsp+48h] [rbp-B8h] BYREF
  __int64 v45; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v46; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v47; // [rsp+60h] [rbp-A0h] BYREF
  int v48; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v49; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v50; // [rsp+78h] [rbp-88h] BYREF
  OLECHAR *v51; // [rsp+80h] [rbp-80h] BYREF
  LPVOID *v52; // [rsp+88h] [rbp-78h] BYREF
  struct IX509CertificateRequestPkcs7 *v53; // [rsp+90h] [rbp-70h] BYREF
  char v54; // [rsp+98h] [rbp-68h]
  OLECHAR psz[48]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  v50 = 0;
  psz[0] = 0;
  OmaDmRegistryGetString(a1, 0, L"DMPCertThumbPrint", psz, 0x2Au);
  v6 = SysAllocString(psz);
  v51 = v6;
  if ( v6 )
  {
    v43 = 0;
    v52 = &v43;
    v53 = 0;
    v54 = 1;
    v8 = SetUpLimitedCertRequest(a1, v6, a2, &v53);
    wil::details::out_param_t<wil::com_ptr_t<IX509CertificateRequestPkcs7,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<IX509CertificateRequestPkcs7,wil::err_exception_policy>>((__int64 **)&v52);
    if ( v8 >= 0 )
    {
      Logger = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogLimitedRenewStatus(Logger, 0);
    }
    else
    {
      v9 = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogLimitedRenewStatus(v9, v8);
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
        McTemplateU0zq_EventWriteTransfer(v10, FunctionFailedEvent, L"SetUpLimitedCertRequest", (unsigned int)v8);
      wil::com_ptr_t<IX509CertificateRequestPkcs7,wil::err_exception_policy>::reset(&v43);
      wil::com_ptr_t<IX509CertificateRequestPkcs7,wil::err_exception_policy>::reset(&v43);
      v11 = CoCreateInstance(
              &GUID_884e2044_217d_11da_b2a4_000e7bbb2b09,
              0,
              1u,
              &GUID_728ab344_217d_11da_b2a4_000e7bbb2b09,
              &v43);
      v7 = v11;
      if ( v11 < 0 )
      {
        if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) == 0 )
        {
LABEL_10:
          wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>((__int64 *)&v43);
          goto LABEL_49;
        }
        v13 = L"CoCreateInstance IX509CertificateRequestPkcs7";
LABEL_9:
        McTemplateU0zq_EventWriteTransfer(v12, FunctionFailedEvent, v13, (unsigned int)v11);
        goto LABEL_10;
      }
      ppv = 12;
      v11 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64, OLECHAR *))(*(_QWORD *)v43 + 264LL))(
              v43,
              (unsigned int)((a2 & 4) != 0) + 1,
              1,
              v6);
      v7 = v11;
      if ( v11 < 0 )
      {
        if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) == 0 )
          goto LABEL_10;
        v13 = L"IX509CertificateRequestPkcs7->InitializeFromCertificate";
        goto LABEL_9;
      }
    }
    v11 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v43 + 160LL))(v43, 1);
    v7 = v11;
    if ( v11 < 0 )
    {
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) == 0 )
        goto LABEL_10;
      v13 = L"IX509CertificateRequestPkcs7->put_SuppressDefaults";
      goto LABEL_9;
    }
    v11 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)v43 + 64LL))(v43);
    v7 = v11;
    if ( v11 < 0 )
    {
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) == 0 )
        goto LABEL_10;
      v13 = L"IX509CertificateRequestPkcs7->Encode";
      goto LABEL_9;
    }
    v15 = v43;
    v16 = *(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v43 + 248LL);
    v17 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&v50);
    v18 = v16(v15, 1, v17);
    v20 = v18;
    if ( v18 < 0 )
    {
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
        McTemplateU0zq_EventWriteTransfer(
          v19,
          FunctionFailedEvent,
          L"IX509CertificateRequestPkcs7->get_RawData",
          (unsigned int)v18);
      goto LABEL_48;
    }
    v21 = HeapStrDup(v50);
    *a3 = v21;
    if ( v21 )
    {
      v44 = 0;
      v22 = v43;
      v23 = *(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD))(*(_QWORD *)v43 + 80LL);
      Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v44);
      v24 = v23(v22, 0, &v44);
      v7 = v24;
      if ( v24 < 0 )
      {
        v25 = 2404;
LABEL_27:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v25,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\certrequest.cpp",
          (const char *)(unsigned int)v24,
          ppv);
LABEL_28:
        Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v44);
        goto LABEL_10;
      }
      v48 = 0;
      v24 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), int *))(*v44)[11])(v44, &v48);
      v7 = v24;
      if ( v24 < 0 )
      {
        v25 = 2407;
        goto LABEL_27;
      }
      if ( v48 != 1 )
      {
        Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v44);
        wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>((__int64 *)&v43);
        v7 = -2147418113;
        goto LABEL_49;
      }
      v46 = 0;
      v26 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v44;
      v27 = **v44;
      Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v46);
      v28 = v27(v26, &GUID_728ab342_217d_11da_b2a4_000e7bbb2b09, &v46);
      v7 = v28;
      if ( v28 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x971,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\certrequest.cpp",
          (const char *)(unsigned int)v28,
          ppv);
LABEL_35:
        Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v46);
        goto LABEL_28;
      }
      v45 = 0;
      v29 = v46;
      v30 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v46 + 328LL);
      Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v45);
      v31 = v30(v29, &v45);
      v7 = v31;
      if ( v31 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x974,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\certrequest.cpp",
          (const char *)(unsigned int)v31,
          ppv);
LABEL_38:
        Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v45);
        goto LABEL_35;
      }
      v47 = 0;
      v32 = v45;
      v33 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v45 + 120LL);
      v34 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&v47);
      v35 = v33(v32, v34);
      v7 = v35;
      if ( v35 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x977,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\certrequest.cpp",
          (const char *)(unsigned int)v35,
          ppv);
LABEL_41:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v47);
        goto LABEL_38;
      }
      v49 = 0;
      v36 = v45;
      v37 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v45 + 200LL);
      v38 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&v49);
      v39 = v37(v36, v38);
      v7 = v39;
      if ( v39 < 0 )
      {
        v40 = 2426;
LABEL_44:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v40,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\certrequest.cpp",
          (const char *)(unsigned int)v39,
          ppv);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v49);
        goto LABEL_41;
      }
      v39 = SetNewContainerAndProvider(a1, v47, v49);
      v7 = v39;
      if ( v39 < 0 )
      {
        v40 = 2428;
        goto LABEL_44;
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v49);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v47);
      Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v45);
      Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v46);
      Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v44);
    }
LABEL_48:
    wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>((__int64 *)&v43);
    v7 = v20;
    goto LABEL_49;
  }
  v7 = -2147024882;
LABEL_49:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v51);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v50);
  return v7;
}

```

## disassembly

```asm
0x180057118  mov     [rsp-8+arg_18], rbx
0x18005711d  push    rbp
0x18005711e  push    rsi
0x18005711f  push    rdi
0x180057120  push    r14
0x180057122  push    r15
0x180057124  lea     rbp, [rsp-10h]
0x180057129  sub     rsp, 110h
0x180057130  mov     rax, cs:__security_cookie
0x180057137  xor     rax, rsp
0x18005713a  mov     [rbp+30h+var_30], rax
0x18005713e  mov     r15, r8
0x180057141  mov     esi, edx
0x180057143  mov     r14, rcx
0x180057146  mov     [rsp+130h+var_B8], 0
0x18005714f  xor     eax, eax
0x180057151  mov     [rbp+30h+psz], ax
0x180057155  mov     dword ptr [rsp+130h+ppv], 2Ah ; '*'; int
0x18005715d  lea     r9, [rbp+30h+psz]
0x180057161  lea     r8, aDmpcertthumbpr; "DMPCertThumbPrint"
0x180057168  xor     edx, edx
0x18005716a  call    cs:__imp_?OmaDmRegistryGetString@@YAJPEAUHKEY__@@PEBG1PEAGI@Z; OmaDmRegistryGetString(HKEY__ *,ushort const *,ushort const *,ushort *,uint)
0x180057170  lea     rcx, [rbp+30h+psz]; psz
0x180057174  call    cs:__imp_SysAllocString
0x18005717a  mov     rbx, rax
0x18005717d  mov     [rbp+30h+var_B0], rax
0x180057181  test    rax, rax
0x180057184  jnz     short loc_180057190
0x180057186  mov     edi, 8007000Eh
0x18005718b  jmp     loc_180057630
0x180057190  mov     [rsp+130h+var_F0], 0
0x180057199  lea     rax, [rsp+130h+var_F0]
0x18005719e  mov     [rbp+30h+var_A8], rax
0x1800571a2  mov     [rbp+30h+var_A0], 0
0x1800571aa  mov     [rbp+30h+var_98], 1
0x1800571ae  lea     r9, [rbp+30h+var_A0]; struct IX509CertificateRequestPkcs7 **
0x1800571b2  mov     r8d, esi; unsigned int
0x1800571b5  mov     rdx, rbx; unsigned __int16 *
0x1800571b8  mov     rcx, r14; HKEY
0x1800571bb  call    ?SetUpLimitedCertRequest@@YAJPEAUHKEY__@@PEAGKPEAPEAUIX509CertificateRequestPkcs7@@@Z; SetUpLimitedCertRequest(HKEY__ *,ushort *,ulong,IX509CertificateRequestPkcs7 * *)
0x1800571c0  mov     edi, eax
0x1800571c2  lea     rcx, [rbp+30h+var_A8]
0x1800571c6  call    ??1?$out_param_t@V?$com_ptr_t@UIX509CertificateRequestPkcs7@@Uerr_exception_policy@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::com_ptr_t<IX509CertificateRequestPkcs7,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<IX509CertificateRequestPkcs7,wil::err_exception_policy>>(void)
0x1800571cb  mov     ecx, edi
0x1800571cd  shr     ecx, 1Fh
0x1800571d0  test    cl, cl
0x1800571d2  jz      loc_1800572C5
0x1800571d8  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x1800571dd  mov     edx, edi; int
0x1800571df  mov     rcx, rax; this
0x1800571e2  call    ?LogLimitedRenewStatus@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogLimitedRenewStatus(long)
0x1800571e7  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x1800571ee  jz      short loc_180057206
0x1800571f0  mov     r9d, edi
0x1800571f3  lea     r8, aSetuplimitedce; "SetUpLimitedCertRequest"
0x1800571fa  lea     rdx, FunctionFailedEvent
0x180057201  call    McTemplateU0zq_EventWriteTransfer
0x180057206  lea     rcx, [rsp+130h+var_F0]
0x18005720b  call    ?reset@?$com_ptr_t@UIX509CertificateRequestPkcs7@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IX509CertificateRequestPkcs7,wil::err_exception_policy>::reset(void)
0x180057210  lea     rcx, [rsp+130h+var_F0]
0x180057215  call    ?reset@?$com_ptr_t@UIX509CertificateRequestPkcs7@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IX509CertificateRequestPkcs7,wil::err_exception_policy>::reset(void)
0x18005721a  lea     rax, [rsp+130h+var_F0]
0x18005721f  mov     [rsp+130h+ppv], rax; ppv
0x180057224  lea     r9, _GUID_728ab344_217d_11da_b2a4_000e7bbb2b09; riid
0x18005722b  xor     edx, edx; pUnkOuter
0x18005722d  lea     r8d, [rdx+1]; dwClsContext
0x180057231  lea     rcx, _GUID_884e2044_217d_11da_b2a4_000e7bbb2b09; rclsid
0x180057238  call    cs:__imp_CoCreateInstance
0x18005723e  mov     edi, eax
0x180057240  test    eax, eax
0x180057242  jns     short loc_180057273
0x180057244  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x18005724b  jz      short loc_180057264
0x18005724d  lea     r8, aCocreateinstan_0; "CoCreateInstance IX509CertificateReques"...
0x180057254  mov     r9d, eax
0x180057257  lea     rdx, FunctionFailedEvent
0x18005725e  call    McTemplateU0zq_EventWriteTransfer
0x180057263  nop
0x180057264  lea     rcx, [rsp+130h+var_F0]
0x180057269  call    ??1?$com_ptr_t@UIXMLDOMNodeList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(void)
0x18005726e  jmp     loc_180057630
0x180057273  mov     rcx, [rsp+130h+var_F0]
0x180057278  mov     rax, [rcx]
0x18005727b  mov     r8d, 1
0x180057281  and     sil, 4
0x180057285  neg     sil
0x180057288  sbb     edx, edx
0x18005728a  neg     edx
0x18005728c  inc     edx
0x18005728e  mov     [rsp+130h+var_108], 2
0x180057296  mov     dword ptr [rsp+130h+ppv], 0Ch
0x18005729e  mov     r9, rbx
0x1800572a1  mov     rax, [rax+108h]
0x1800572a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800572ad  mov     edi, eax
0x1800572af  test    eax, eax
0x1800572b1  jns     short loc_1800572D4
0x1800572b3  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x1800572ba  jz      short loc_180057264
0x1800572bc  lea     r8, aIx509certifica_2; "IX509CertificateRequestPkcs7->Initializ"...
0x1800572c3  jmp     short loc_180057254
0x1800572c5  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x1800572ca  xor     edx, edx; int
0x1800572cc  mov     rcx, rax; this
0x1800572cf  call    ?LogLimitedRenewStatus@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogLimitedRenewStatus(long)
0x1800572d4  mov     rcx, [rsp+130h+var_F0]
0x1800572d9  mov     rax, [rcx]
0x1800572dc  mov     esi, 1
0x1800572e1  mov     edx, esi
0x1800572e3  mov     rax, [rax+0A0h]
0x1800572ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800572ef  mov     edi, eax
0x1800572f1  test    eax, eax
0x1800572f3  jns     short loc_18005730E
0x1800572f5  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x1800572fc  jz      loc_180057264
0x180057302  lea     r8, aIx509certifica_5; "IX509CertificateRequestPkcs7->put_Suppr"...
0x180057309  jmp     loc_180057254
0x18005730e  mov     rcx, [rsp+130h+var_F0]
0x180057313  mov     rax, [rcx]
0x180057316  mov     rax, [rax+40h]
0x18005731a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005731f  mov     edi, eax
0x180057321  test    eax, eax
0x180057323  jns     short loc_18005733E
0x180057325  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x18005732c  jz      loc_180057264
0x180057332  lea     r8, aIx509certifica_4; "IX509CertificateRequestPkcs7->Encode"
0x180057339  jmp     loc_180057254
0x18005733e  mov     rdi, [rsp+130h+var_F0]
0x180057343  mov     rax, [rdi]
0x180057346  mov     rbx, [rax+0F8h]
0x18005734d  lea     rcx, [rsp+130h+var_B8]
0x180057352  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x180057357  mov     r8, rax
0x18005735a  mov     edx, esi
0x18005735c  mov     rcx, rdi
0x18005735f  mov     rax, rbx
0x180057362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057367  mov     esi, eax
0x180057369  test    eax, eax
0x18005736b  jns     short loc_180057395
0x18005736d  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x180057374  jz      loc_180057624
0x18005737a  mov     r9d, eax
0x18005737d  lea     r8, aIx509certifica_7; "IX509CertificateRequestPkcs7->get_RawDa"...
0x180057384  lea     rdx, FunctionFailedEvent
0x18005738b  call    McTemplateU0zq_EventWriteTransfer
0x180057390  jmp     loc_180057624
0x180057395  mov     rcx, [rsp+130h+var_B8]; unsigned __int16 *
0x18005739a  call    ?HeapStrDup@@YAPEAGPEBG@Z; HeapStrDup(ushort const *)
0x18005739f  mov     [r15], rax
0x1800573a2  test    rax, rax
0x1800573a5  jz      loc_180057624
0x1800573ab  mov     [rsp+130h+var_E8], 0
0x1800573b4  mov     rdi, [rsp+130h+var_F0]
0x1800573b9  mov     rax, [rdi]
0x1800573bc  mov     rbx, [rax+50h]
0x1800573c0  lea     rcx, [rsp+130h+var_E8]
0x1800573c5  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x1800573ca  lea     r8, [rsp+130h+var_E8]
0x1800573cf  xor     edx, edx
0x1800573d1  mov     rcx, rdi
0x1800573d4  mov     rax, rbx
0x1800573d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800573dc  mov     edi, eax
0x1800573de  test    eax, eax
0x1800573e0  jns     short loc_18005740A
0x1800573e2  mov     edx, 964h; void *
0x1800573e7  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800573ee  mov     r9d, eax; char *
0x1800573f1  mov     rcx, [rbp+38h]; this
0x1800573f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800573fa  nop
0x1800573fb  lea     rcx, [rsp+130h+var_E8]
0x180057400  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x180057405  jmp     loc_180057264
0x18005740a  mov     [rsp+130h+var_C8], 0
0x180057412  mov     rcx, [rsp+130h+var_E8]
0x180057417  mov     rax, [rcx]
0x18005741a  lea     rdx, [rsp+130h+var_C8]
0x18005741f  mov     rax, [rax+58h]
0x180057423  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057428  mov     edi, eax
0x18005742a  test    eax, eax
0x18005742c  jns     short loc_180057435
0x18005742e  mov     edx, 967h
0x180057433  jmp     short loc_1800573E7
0x180057435  cmp     [rsp+130h+var_C8], 1
0x18005743a  jz      short loc_18005745B
0x18005743c  lea     rcx, [rsp+130h+var_E8]
0x180057441  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x180057446  nop
0x180057447  lea     rcx, [rsp+130h+var_F0]
0x18005744c  call    ??1?$com_ptr_t@UIXMLDOMNodeList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(void)
0x180057451  mov     edi, 8000FFFFh
0x180057456  jmp     loc_180057630
0x18005745b  mov     [rsp+130h+var_D8], 0
0x180057464  mov     rdi, [rsp+130h+var_E8]
0x180057469  mov     rax, [rdi]
0x18005746c  mov     rbx, [rax]
0x18005746f  lea     rcx, [rsp+130h+var_D8]
0x180057474  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x180057479  lea     r8, [rsp+130h+var_D8]
0x18005747e  lea     rdx, _GUID_728ab342_217d_11da_b2a4_000e7bbb2b09
0x180057485  mov     rcx, rdi
0x180057488  mov     rax, rbx
0x18005748b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057490  mov     edi, eax
0x180057492  test    eax, eax
0x180057494  jns     short loc_1800574BE
0x180057496  mov     rcx, [rbp+38h]; this
0x18005749a  mov     r9d, eax; char *
0x18005749d  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800574a4  mov     edx, 971h; void *
0x1800574a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800574ae  nop
0x1800574af  lea     rcx, [rsp+130h+var_D8]
0x1800574b4  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x1800574b9  jmp     loc_1800573FB
0x1800574be  mov     [rsp+130h+var_E0], 0
0x1800574c7  mov     rdi, [rsp+130h+var_D8]
0x1800574cc  mov     rax, [rdi]
0x1800574cf  mov     rbx, [rax+148h]
0x1800574d6  lea     rcx, [rsp+130h+var_E0]
0x1800574db  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x1800574e0  lea     rdx, [rsp+130h+var_E0]
0x1800574e5  mov     rcx, rdi
0x1800574e8  mov     rax, rbx
0x1800574eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800574f0  mov     edi, eax
0x1800574f2  test    eax, eax
0x1800574f4  jns     short loc_18005751B
0x1800574f6  mov     rcx, [rbp+38h]; this
0x1800574fa  mov     r9d, eax; char *
0x1800574fd  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180057504  mov     edx, 974h; void *
0x180057509  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005750e  nop
0x18005750f  lea     rcx, [rsp+130h+var_E0]
0x180057514  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x180057519  jmp     short loc_1800574AF
0x18005751b  mov     [rsp+130h+var_D0], 0
0x180057524  mov     rdi, [rsp+130h+var_E0]
0x180057529  mov     rax, [rdi]
0x18005752c  mov     rbx, [rax+78h]
0x180057530  lea     rcx, [rsp+130h+var_D0]
0x180057535  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x18005753a  mov     rdx, rax
0x18005753d  mov     rcx, rdi
0x180057540  mov     rax, rbx
0x180057543  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057548  mov     edi, eax
0x18005754a  test    eax, eax
0x18005754c  jns     short loc_180057573
0x18005754e  mov     rcx, [rbp+38h]; this
0x180057552  mov     r9d, eax; char *
0x180057555  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18005755c  mov     edx, 977h; void *
0x180057561  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180057566  nop
0x180057567  lea     rcx, [rsp+130h+var_D0]
0x18005756c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180057571  jmp     short loc_18005750F
0x180057573  mov     [rsp+130h+var_C0], 0
0x18005757c  mov     rdi, [rsp+130h+var_E0]
0x180057581  mov     rax, [rdi]
0x180057584  mov     rbx, [rax+0C8h]
0x18005758b  lea     rcx, [rsp+130h+var_C0]
0x180057590  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x180057595  mov     rdx, rax
0x180057598  mov     rcx, rdi
0x18005759b  mov     rax, rbx
0x18005759e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800575a3  mov     edi, eax
0x1800575a5  test    eax, eax
0x1800575a7  jns     short loc_1800575CE
0x1800575a9  mov     edx, 97Ah; void *
0x1800575ae  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800575b5  mov     r9d, eax; char *
0x1800575b8  mov     rcx, [rbp+38h]; this
0x1800575bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800575c1  nop
0x1800575c2  lea     rcx, [rsp+130h+var_C0]
0x1800575c7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800575cc  jmp     short loc_180057567
0x1800575ce  mov     r8, [rsp+130h+var_C0]; unsigned __int16 *
0x1800575d3  mov     rdx, [rsp+130h+var_D0]; unsigned __int16 *
0x1800575d8  mov     rcx, r14; HKEY
0x1800575db  call    ?SetNewContainerAndProvider@@YAJPEAUHKEY__@@PEAGPEBG@Z; SetNewContainerAndProvider(HKEY__ *,ushort *,ushort const *)
0x1800575e0  mov     edi, eax
0x1800575e2  test    eax, eax
0x1800575e4  jns     short loc_1800575ED
0x1800575e6  mov     edx, 97Ch
0x1800575eb  jmp     short loc_1800575AE
0x1800575ed  lea     rcx, [rsp+130h+var_C0]
0x1800575f2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800575f7  nop
0x1800575f8  lea     rcx, [rsp+130h+var_D0]
0x1800575fd  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
  ... truncated ...
```
