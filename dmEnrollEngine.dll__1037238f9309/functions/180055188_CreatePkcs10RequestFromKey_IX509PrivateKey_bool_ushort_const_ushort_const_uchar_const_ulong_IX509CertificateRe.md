# CreatePkcs10RequestFromKey(IX509PrivateKey *,bool,ushort const *,ushort const *,uchar const *,ulong,IX509CertificateRequestPkcs10 * *)

- ea: `0x180055188`
- end: `0x180055af6`
- name: `?CreatePkcs10RequestFromKey@@YAJPEAUIX509PrivateKey@@_NPEBG2PEBEKPEAPEAUIX509CertificateRequestPkcs10@@@Z`
- size: `2414`
- prototype: `int(struct IX509PrivateKey *, bool, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int8 *, unsigned int, struct IX509CertificateRequestPkcs10 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001b3ac`

## callees

- `0x1800140d0`
- `0x180020cb4`
- `0x18003c968`
- `0x18003dba8`
- `0x180055188`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800551f8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800552d4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005542e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800554e5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800555c5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800556ec`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180055781`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180055958`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800551f8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800552d4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005542e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800554e5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800555c5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800556ec`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180055781`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180055958`
- `OLEAUT32!__imp_SysAllocString` at `0x180055282`
- `OLEAUT32!__imp_SysAllocString` at `0x180055474`
- `OLEAUT32!__imp_SysAllocString` at `0x180055732`
- `OLEAUT32!__imp_SysAllocString` at `0x180055913`
- `OLEAUT32!__imp_SysAllocString` at `0x180055282`
- `OLEAUT32!__imp_SysAllocString` at `0x180055474`
- `OLEAUT32!__imp_SysAllocString` at `0x180055732`
- `OLEAUT32!__imp_SysAllocString` at `0x180055913`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180055831`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180055831`

## string_xrefs

- `0x180055500`: `CoCreateInstance IObjectId`
- `0x18005579c`: `CoCreateInstance IObjectId`
- `0x180055973`: `CoCreateInstance IObjectId`
- `0x180055217`: `CoCreateInstance IX509CertificateRequestPkcs10`
- `0x1800551ba`: `CreatePkcs10RequestFromKey`
- `0x1800552ef`: `CoCreateInstance IX500DistinguishedName`
- `0x180055449`: `CoCreateInstance IX509ExtensionEnhancedKeyUsage`
- `0x180055707`: `CoCreateInstance IX509ExtensionEnhancedKeyUsage`
- `0x1800553e3`: `IX500DistinguishedName->get_X509Extensions`
- `0x1800555dd`: `CoCreateInstance IObjectIds`
- `0x18005568c`: `IX509Extensions->Add`
- `0x1800558d7`: `IX509Extensions->Add`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall CreatePkcs10RequestFromKey(
        struct IX509PrivateKey *a1,
        unsigned __int8 a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const CHAR *psz,
        UINT len,
        struct IX509CertificateRequestPkcs10 **a7)
{
  int v9; // esi
  HRESULT v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rcx
  unsigned int v14; // ebx
  int v15; // eax
  __int64 v16; // rcx
  OLECHAR *v17; // rbx
  HRESULT v18; // eax
  __int64 v19; // rcx
  HRESULT v20; // edi
  int v21; // eax
  __int64 v22; // rcx
  const wchar_t *v23; // r8
  LPVOID v24; // rdi
  __int64 (__fastcall *v25)(LPVOID, __int64 *); // rbx
  int v26; // eax
  __int64 v27; // rcx
  const wchar_t *v28; // r8
  HRESULT v29; // eax
  __int64 v30; // rcx
  BSTR v31; // rbx
  HRESULT v32; // eax
  __int64 v33; // rcx
  int v34; // eax
  __int64 v35; // rcx
  HRESULT v36; // eax
  __int64 v37; // rcx
  const wchar_t *v38; // r8
  HRESULT v39; // eax
  __int64 v40; // rcx
  BSTR v41; // rbx
  HRESULT v42; // eax
  __int64 v43; // rcx
  int v44; // eax
  __int64 v45; // rcx
  OLECHAR *v46; // rax
  int v47; // eax
  __int64 v48; // rcx
  const wchar_t *v49; // r8
  OLECHAR *v50; // rbx
  HRESULT v51; // eax
  __int64 v52; // rcx
  int v53; // eax
  __int64 v54; // rcx
  const wchar_t *v55; // r8
  struct IX509CertificateRequestPkcs10 *v56; // rcx
  HRESULT v58; // [rsp+30h] [rbp-61h] BYREF
  LPVOID v59; // [rsp+38h] [rbp-59h] BYREF
  __int64 v60; // [rsp+40h] [rbp-51h] BYREF
  OLECHAR *v61; // [rsp+48h] [rbp-49h] BYREF
  LPVOID v62; // [rsp+50h] [rbp-41h] BYREF
  LPVOID v63; // [rsp+58h] [rbp-39h] BYREF
  LPVOID v64; // [rsp+60h] [rbp-31h] BYREF
  LPVOID v65; // [rsp+68h] [rbp-29h] BYREF
  LPVOID v66; // [rsp+70h] [rbp-21h] BYREF
  LPVOID ppv; // [rsp+78h] [rbp-19h] BYREF
  OLECHAR *v68; // [rsp+80h] [rbp-11h] BYREF
  LPVOID v69; // [rsp+88h] [rbp-9h] BYREF
  _QWORD v70[8]; // [rsp+90h] [rbp-1h] BYREF

  v9 = a2;
  v58 = 0;
  ppv = 0;
  v70[0] = "CreatePkcs10RequestFromKey";
  v70[1] = &v58;
  Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&ppv);
  v11 = CoCreateInstance(
          &GUID_884e2042_217d_11da_b2a4_000e7bbb2b09,
          0,
          1u,
          &GUID_728ab342_217d_11da_b2a4_000e7bbb2b09,
          &ppv);
  v14 = v11;
  v58 = v11;
  if ( v11 < 0 )
  {
    if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
    {
      McTemplateU0zq_EventWriteTransfer(
        v13,
        FunctionFailedEvent,
        L"CoCreateInstance IX509CertificateRequestPkcs10",
        (unsigned int)v11);
      v14 = v58;
    }
    goto LABEL_104;
  }
  v15 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, struct IX509PrivateKey *, _QWORD))(*(_QWORD *)ppv + 264LL))(
          ppv,
          (unsigned int)(v9 + 1),
          a1,
          0);
  v58 = v15;
  if ( v15 >= 0 )
  {
    v17 = SysAllocString(a3);
    v61 = v17;
    if ( !v17 )
    {
LABEL_9:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v61);
      v14 = -2147024882;
      goto LABEL_104;
    }
    v59 = 0;
    Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v59);
    v18 = CoCreateInstance(
            &GUID_884e2003_217d_11da_b2a4_000e7bbb2b09,
            0,
            1u,
            &GUID_728ab303_217d_11da_b2a4_000e7bbb2b09,
            &v59);
    v20 = v18;
    v58 = v18;
    if ( v18 < 0 )
    {
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
      {
        McTemplateU0zq_EventWriteTransfer(
          v19,
          FunctionFailedEvent,
          L"CoCreateInstance IX500DistinguishedName",
          (unsigned int)v18);
        v20 = v58;
      }
      goto LABEL_13;
    }
    v21 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, _QWORD))(*(_QWORD *)v59 + 64LL))(v59, v17, 0);
    v14 = v21;
    v58 = v21;
    if ( v21 < 0 )
    {
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) == 0 )
      {
LABEL_103:
        Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v59);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v61);
        goto LABEL_104;
      }
      v23 = L"IX500DistinguishedName->Encode";
LABEL_17:
      McTemplateU0zq_EventWriteTransfer(v22, FunctionFailedEvent, v23, (unsigned int)v21);
      v14 = v58;
      goto LABEL_103;
    }
    v21 = (*(__int64 (__fastcall **)(LPVOID, LPVOID))(*(_QWORD *)ppv + 368LL))(ppv, v59);
    v14 = v21;
    v58 = v21;
    if ( v21 < 0 )
    {
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) == 0 )
        goto LABEL_103;
      v23 = L"IX500DistinguishedName->put_Subject";
      goto LABEL_17;
    }
    v60 = 0;
    v24 = ppv;
    v25 = *(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 432LL);
    Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v60);
    v26 = v25(v24, &v60);
    v14 = v26;
    v58 = v26;
    if ( v26 < 0 )
    {
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
      {
        v28 = L"IX500DistinguishedName->get_X509Extensions";
LABEL_24:
        McTemplateU0zq_EventWriteTransfer(v27, FunctionFailedEvent, v28, (unsigned int)v26);
        v14 = v58;
        goto LABEL_102;
      }
      goto LABEL_102;
    }
    v64 = 0;
    Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v64);
    v29 = CoCreateInstance(
            &GUID_884e2010_217d_11da_b2a4_000e7bbb2b09,
            0,
            1u,
            &GUID_728ab310_217d_11da_b2a4_000e7bbb2b09,
            &v64);
    v14 = v29;
    v58 = v29;
    if ( v29 < 0 )
    {
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
      {
        McTemplateU0zq_EventWriteTransfer(
          v30,
          FunctionFailedEvent,
          L"CoCreateInstance IX509ExtensionEnhancedKeyUsage",
          (unsigned int)v29);
        v14 = v58;
      }
      goto LABEL_28;
    }
    v31 = SysAllocString(L"1.3.6.1.5.5.7.3.2");
    v62 = v31;
    if ( !v31 )
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((OLECHAR **)&v62);
      Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v64);
LABEL_31:
      Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v60);
      Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v59);
      goto LABEL_9;
    }
    v66 = 0;
    Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v66);
    v32 = CoCreateInstance(
            &GUID_884e2000_217d_11da_b2a4_000e7bbb2b09,
            0,
            1u,
            &GUID_728ab300_217d_11da_b2a4_000e7bbb2b09,
            &v66);
    v20 = v32;
    v58 = v32;
    if ( v32 < 0 )
    {
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
      {
        McTemplateU0zq_EventWriteTransfer(v33, FunctionFailedEvent, L"CoCreateInstance IObjectId", (unsigned int)v32);
        v20 = v58;
      }
      Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v66);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((OLECHAR **)&v62);
      Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v64);
LABEL_36:
      Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v60);
LABEL_13:
      Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v59);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v61);
      v14 = v20;
      goto LABEL_104;
    }
    v34 = (*(__int64 (__fastcall **)(LPVOID, BSTR))(*(_QWORD *)v66 + 64LL))(v66, v31);
    v14 = v34;
    v58 = v34;
    if ( v34 < 0 )
    {
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
      {
        McTemplateU0zq_EventWriteTransfer(
          v35,
          FunctionFailedEvent,
          L"IObjectId->InitializeFromValue",
          (unsigned int)v34);
        v14 = v58;
      }
      goto LABEL_40;
    }
    v69 = 0;
    Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v69);
    v36 = CoCreateInstance(
            &GUID_884e2001_217d_11da_b2a4_000e7bbb2b09,
            0,
            1u,
            &GUID_728ab301_217d_11da_b2a4_000e7bbb2b09,
            &v69);
    v14 = v36;
    v58 = v36;
    if ( v36 < 0 )
    {
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) == 0 )
      {
LABEL_45:
        Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v69);
LABEL_40:
        Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v66);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((OLECHAR **)&v62);
LABEL_28:
        Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v64);
        goto LABEL_102;
      }
      v38 = L"CoCreateInstance IObjectIds";
LABEL_44:
      McTemplateU0zq_EventWriteTransfer(v37, FunctionFailedEvent, v38, (unsigned int)v36);
      v14 = v58;
      goto LABEL_45;
    }
    v36 = (*(__int64 (__fastcall **)(LPVOID, LPVOID))(*(_QWORD *)v69 + 80LL))(v69, v66);
    v14 = v36;
    v58 = v36;
    if ( v36 < 0 )
    {
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) == 0 )
        goto LABEL_45;
      v38 = L"IObjectIds->Add";
      goto LABEL_44;
    }
    v36 = (*(__int64 (__fastcall **)(LPVOID, LPVOID))(*(_QWORD *)v64 + 96LL))(v64, v69);
    v14 = v36;
    v58 = v36;
    if ( v36 < 0 )
    {
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) == 0 )
        goto LABEL_45;
      v38 = L"IObjectIds->InitializeEncode";
      goto LABEL_44;
    }
    v36 = (*(__int64 (__fastcall **)(__int64, LPVOID))(*(_QWORD *)v60 + 80LL))(v60, v64);
    v14 = v36;
    v58 = v36;
    if ( v36 < 0 )
    {
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) == 0 )
        goto LABEL_45;
      v38 = L"IX509Extensions->Add";
      goto LABEL_44;
    }
    Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v69);
    Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v66);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((OLECHAR **)&v62);
    Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v64);
    v65 = 0;
    Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v65);
    v39 = CoCreateInstance(
            &GUID_884e200d_217d_11da_b2a4_000e7bbb2b09,
            0,
            1u,
            &GUID_728ab30d_217d_11da_b2a4_000e7bbb2b09,
            &v65);
    v14 = v39;
    v58 = v39;
    if ( v39 < 0 )
    {
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
      {
        McTemplateU0zq_EventWriteTransfer(
          v40,
          FunctionFailedEvent,
          L"CoCreateInstance IX509ExtensionEnhancedKeyUsage",
          (unsigned int)v39);
        v14 = v58;
      }
      goto LABEL_58;
    }
    v41 = SysAllocString(L"1.3.6.1.4.1.311.66.1.0");
    v63 = v41;
    if ( !v41 )
    {
LABEL_60:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((OLECHAR **)&v63);
      Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v65);
      goto LABEL_31;
    }
    v62 = 0;
    Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v62);
    v42 = CoCreateInstance(
            &GUID_884e2000_217d_11da_b2a4_000e7bbb2b09,
            0,
            1u,
            &GUID_728ab300_217d_11da_b2a4_000e7bbb2b09,
            &v62);
    v20 = v42;
    v58 = v42;
    if ( v42 < 0 )
    {
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
      {
        McTemplateU0zq_EventWriteTransfer(v43, FunctionFailedEvent, L"CoCreateInstance IObjectId", (unsigned int)v42);
        v20 = v58;
      }
      Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v62);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((OLECHAR **)&v63);
      Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v65);
      goto LABEL_36;
    }
    v44 = (*(__int64 (__fastcall **)(LPVOID, BSTR))(*(_QWORD *)v62 + 64LL))(v62, v41);
    v14 = v44;
    v58 = v44;
    if ( v44 < 0 )
    {
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
      {
        McTemplateU0zq_EventWriteTransfer(
          v45,
          FunctionFailedEvent,
          L"IObjectId->InitializeFromValue",
          (unsigned int)v44);
        v14 = v58;
      }
      goto LABEL_68;
    }
    v46 = SysAllocStringByteLen(psz, len);
    v68 = v46;
    if ( !v46 )
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v68);
      Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v62);
      goto LABEL_60;
    }
    v47 = (*(__int64 (__fastcall **)(LPVOID, LPVOID, __int64, OLECHAR *))(*(_QWORD *)v65 + 56LL))(v65, v62, 2, v46);
    v14 = v47;
    v58 = v47;
    if ( v47 < 0 )
    {
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) == 0 )
      {
LABEL_75:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v68);
LABEL_68:
        Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v62);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((OLECHAR **)&v63);
LABEL_58:
        Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v65);
        goto LABEL_102;
      }
      v49 = L"IObjectIds->InitializeEncode";
LABEL_74:
      McTemplateU0zq_EventWriteTransfer(v48, FunctionFailedEvent, v49, (unsigned int)v47);
      v14 = v58;
      goto LABEL_75;
    }
    v47 = (*(__int64 (__fastcall **)(__int64, LPVOID))(*(_QWORD *)v60 + 80LL))(v60, v65);
    v14 = v47;
    v58 = v47;
    if ( v47 < 0 )
    {
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) == 0 )
        goto LABEL_75;
      v49 = L"IX509Extensions->Add";
      goto LABEL_74;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v68);
    Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v62);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((OLECHAR **)&v63);
    Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v65);
    if ( a4 )
    {
      v50 = SysAllocString(a4);
      v68 = v50;
      if ( !v50 )
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v68);
        goto LABEL_31;
      }
      v63 = 0;
      Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v63);
      v51 = CoCreateInstance(
              &GUID_884e2000_217d_11da_b2a4_000e7bbb2b09,
              0,
              1u,
              &GUID_728ab300_217d_11da_b2a4_000e7bbb2b09,
              &v63);
      v20 = v51;
      v58 = v51;
      if ( v51 < 0 )
      {
        if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
        {
          McTemplateU0zq_EventWriteTransfer(v52, FunctionFailedEvent, L"CoCreateInstance IObjectId", (unsigned int)v51);
          v20 = v58;
        }
        Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v63);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v68);
        goto LABEL_36;
      }
      v53 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *))(*(_QWORD *)v63 + 64LL))(v63, v50);
      v14 = v53;
      v58 = v53;
      if ( v53 < 0 )
      {
        if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) == 0 )
        {
LABEL_90:
          Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v63);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v68);
          goto LABEL_102;
        }
        v55 = L"IObjectId->InitializeFromValue";
LABEL_89:
        McTemplateU0zq_EventWriteTransfer(v54, FunctionFailedEvent, v55, (unsigned int)v53);
        v14 = v58;
        goto LABEL_90;
      }
      v53 = (*(__int64 (__fastcall **)(LPVOID, LPVOID))(*(_QWORD *)ppv + 224LL))(ppv, v63);
      v14 = v53;
      v58 = v53;
      if ( v53 < 0 )
      {
        if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) == 0 )
          goto LABEL_90;
        v55 = L"IX509CertificateRequestPkcs10->put_HashAlgorithm";
        goto LABEL_89;
      }
      Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v63);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v68);
    }
    v26 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 160LL))(ppv, 1);
    v14 = v26;
    v58 = v26;
    if ( v26 < 0 )
    {
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) == 0 )
        goto LABEL_102;
      v28 = L"IX509CertificateRequestPkcs10->put_SuppressDefaults";
      goto LABEL_24;
    }
    v26 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 64LL))(ppv);
    v14 = v26;
    v58 = v26;
    if ( v26 >= 0 )
    {
      v56 = (struct IX509CertificateRequestPkcs10 *)ppv;
      ppv = 0;
      *a7 = v56;
      goto LABEL_102;
    }
    if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
    {
      v28 = L"IX509CertificateRequestPkcs10->Encode";
      goto LABEL_24;
    }
LABEL_102:
    Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v60);
    goto LABEL_103;
  }
  if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
  {
    McTemplateU0zq_EventWriteTransfer(
      v16,
      FunctionFailedEvent,
      L"IX509CertificateRequestPkcs10->InitializeFromPrivateKey",
      (unsigned int)v15);
    v15 = v58;
  }
  v14 = v15;
LABEL_104:
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v70, v12);
  Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&ppv);
  return v14;
}

```

## disassembly

```asm
0x180055188  push    rbp
0x18005518a  push    rbx
0x18005518b  push    rsi
0x18005518c  push    rdi
0x18005518d  push    r13
0x18005518f  push    r14
0x180055191  push    r15
0x180055193  lea     rbp, [rsp-0Fh]
0x180055198  sub     rsp, 0A0h
0x18005519f  mov     r15, r9
0x1800551a2  mov     rdi, r8
0x1800551a5  movzx   esi, dl
0x1800551a8  mov     r14, rcx
0x1800551ab  mov     [rbp+3Fh+var_A0], 0
0x1800551b2  mov     [rbp+3Fh+var_58], 0
0x1800551ba  lea     rax, aCreatepkcs10re_0; "CreatePkcs10RequestFromKey"
0x1800551c1  mov     [rbp+3Fh+var_40], rax
0x1800551c5  lea     rax, [rbp+3Fh+var_A0]
0x1800551c9  mov     [rbp+3Fh+var_38], rax
0x1800551cd  lea     rcx, [rbp+3Fh+var_58]
0x1800551d1  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x1800551d6  lea     rax, [rbp+3Fh+var_58]
0x1800551da  mov     [rsp+0D0h+ppv], rax; ppv
0x1800551df  lea     r9, _GUID_728ab342_217d_11da_b2a4_000e7bbb2b09; riid
0x1800551e6  mov     r13d, 1
0x1800551ec  mov     r8d, r13d; dwClsContext
0x1800551ef  xor     edx, edx; pUnkOuter
0x1800551f1  lea     rcx, _GUID_884e2042_217d_11da_b2a4_000e7bbb2b09; rclsid
0x1800551f8  call    cs:__imp_CoCreateInstance
0x1800551fe  mov     ebx, eax
0x180055200  mov     [rbp+3Fh+var_A0], eax
0x180055203  test    eax, eax
0x180055205  jns     short loc_180055232
0x180055207  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x18005520e  jz      loc_180055ACF
0x180055214  mov     r9d, eax
0x180055217  lea     r8, aCocreateinstan_2; "CoCreateInstance IX509CertificateReques"...
0x18005521e  lea     rdx, FunctionFailedEvent
0x180055225  call    McTemplateU0zq_EventWriteTransfer
0x18005522a  mov     ebx, [rbp+3Fh+var_A0]
0x18005522d  jmp     loc_180055ACF
0x180055232  mov     rcx, [rbp+3Fh+var_58]
0x180055236  mov     rax, [rcx]
0x180055239  lea     edx, [rsi+r13]
0x18005523d  xor     r9d, r9d
0x180055240  mov     r8, r14
0x180055243  mov     rax, [rax+108h]
0x18005524a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005524f  mov     [rbp+3Fh+var_A0], eax
0x180055252  test    eax, eax
0x180055254  jns     short loc_18005527F
0x180055256  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x18005525d  jz      short loc_180055278
0x18005525f  mov     r9d, eax
0x180055262  lea     r8, aIx509certifica_6; "IX509CertificateRequestPkcs10->Initiali"...
0x180055269  lea     rdx, FunctionFailedEvent
0x180055270  call    McTemplateU0zq_EventWriteTransfer
0x180055275  mov     eax, [rbp+3Fh+var_A0]
0x180055278  mov     ebx, eax
0x18005527a  jmp     loc_180055ACF
0x18005527f  mov     rcx, rdi; psz
0x180055282  call    cs:__imp_SysAllocString
0x180055288  mov     rbx, rax
0x18005528b  mov     [rbp+3Fh+var_88], rax
0x18005528f  test    rax, rax
0x180055292  jnz     short loc_1800552A7
0x180055294  lea     rcx, [rbp+3Fh+var_88]
0x180055298  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005529d  mov     ebx, 8007000Eh
0x1800552a2  jmp     loc_180055ACF
0x1800552a7  mov     [rbp+3Fh+var_98], 0
0x1800552af  lea     rcx, [rbp+3Fh+var_98]
0x1800552b3  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x1800552b8  lea     rax, [rbp+3Fh+var_98]
0x1800552bc  mov     [rsp+0D0h+ppv], rax; ppv
0x1800552c1  lea     r9, _GUID_728ab303_217d_11da_b2a4_000e7bbb2b09; riid
0x1800552c8  mov     r8d, r13d; dwClsContext
0x1800552cb  xor     edx, edx; pUnkOuter
0x1800552cd  lea     rcx, _GUID_884e2003_217d_11da_b2a4_000e7bbb2b09; rclsid
0x1800552d4  call    cs:__imp_CoCreateInstance
0x1800552da  mov     edi, eax
0x1800552dc  mov     [rbp+3Fh+var_A0], eax
0x1800552df  test    eax, eax
0x1800552e1  jns     short loc_18005531F
0x1800552e3  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x1800552ea  jz      short loc_180055305
0x1800552ec  mov     r9d, eax
0x1800552ef  lea     r8, aCocreateinstan_1; "CoCreateInstance IX500DistinguishedName"
0x1800552f6  lea     rdx, FunctionFailedEvent
0x1800552fd  call    McTemplateU0zq_EventWriteTransfer
0x180055302  mov     edi, [rbp+3Fh+var_A0]
0x180055305  lea     rcx, [rbp+3Fh+var_98]
0x180055309  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x18005530e  nop
0x18005530f  lea     rcx, [rbp+3Fh+var_88]
0x180055313  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180055318  mov     ebx, edi
0x18005531a  jmp     loc_180055ACF
0x18005531f  mov     rcx, [rbp+3Fh+var_98]
0x180055323  mov     rax, [rcx]
0x180055326  xor     r8d, r8d
0x180055329  mov     rdx, rbx
0x18005532c  mov     rax, [rax+40h]
0x180055330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055335  mov     ebx, eax
0x180055337  mov     [rbp+3Fh+var_A0], eax
0x18005533a  test    eax, eax
0x18005533c  jns     short loc_180055369
0x18005533e  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x180055345  jz      loc_180055ABB
0x18005534b  lea     r8, aIx500distingui_1; "IX500DistinguishedName->Encode"
0x180055352  mov     r9d, eax
0x180055355  lea     rdx, FunctionFailedEvent
0x18005535c  call    McTemplateU0zq_EventWriteTransfer
0x180055361  mov     ebx, [rbp+3Fh+var_A0]
0x180055364  jmp     loc_180055ABB
0x180055369  mov     rcx, [rbp+3Fh+var_58]
0x18005536d  mov     rax, [rcx]
0x180055370  mov     rdx, [rbp+3Fh+var_98]
0x180055374  mov     rax, [rax+170h]
0x18005537b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055380  mov     ebx, eax
0x180055382  mov     [rbp+3Fh+var_A0], eax
0x180055385  test    eax, eax
0x180055387  jns     short loc_18005539F
0x180055389  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x180055390  jz      loc_180055ABB
0x180055396  lea     r8, aIx500distingui; "IX500DistinguishedName->put_Subject"
0x18005539d  jmp     short loc_180055352
0x18005539f  mov     [rbp+3Fh+var_90], 0
0x1800553a7  mov     rdi, [rbp+3Fh+var_58]
0x1800553ab  mov     rax, [rdi]
0x1800553ae  mov     rbx, [rax+1B0h]
0x1800553b5  lea     rcx, [rbp+3Fh+var_90]
0x1800553b9  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x1800553be  lea     rdx, [rbp+3Fh+var_90]
0x1800553c2  mov     rcx, rdi
0x1800553c5  mov     rax, rbx
0x1800553c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800553cd  mov     ebx, eax
0x1800553cf  mov     [rbp+3Fh+var_A0], eax
0x1800553d2  test    eax, eax
0x1800553d4  jns     short loc_180055401
0x1800553d6  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x1800553dd  jz      loc_180055AB1
0x1800553e3  lea     r8, aIx500distingui_0; "IX500DistinguishedName->get_X509Extensi"...
0x1800553ea  mov     r9d, eax
0x1800553ed  lea     rdx, FunctionFailedEvent
0x1800553f4  call    McTemplateU0zq_EventWriteTransfer
0x1800553f9  mov     ebx, [rbp+3Fh+var_A0]
0x1800553fc  jmp     loc_180055AB1
0x180055401  mov     [rbp+3Fh+var_70], 0
0x180055409  lea     rcx, [rbp+3Fh+var_70]
0x18005540d  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x180055412  lea     rax, [rbp+3Fh+var_70]
0x180055416  mov     [rsp+0D0h+ppv], rax; ppv
0x18005541b  lea     r9, _GUID_728ab310_217d_11da_b2a4_000e7bbb2b09; riid
0x180055422  mov     r8d, r13d; dwClsContext
0x180055425  xor     edx, edx; pUnkOuter
0x180055427  lea     rcx, _GUID_884e2010_217d_11da_b2a4_000e7bbb2b09; rclsid
0x18005542e  call    cs:__imp_CoCreateInstance
0x180055434  mov     ebx, eax
0x180055436  mov     [rbp+3Fh+var_A0], eax
0x180055439  test    eax, eax
0x18005543b  jns     short loc_18005546D
0x18005543d  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x180055444  jz      short loc_18005545F
0x180055446  mov     r9d, eax
0x180055449  lea     r8, aCocreateinstan_5; "CoCreateInstance IX509ExtensionEnhanced"...
0x180055450  lea     rdx, FunctionFailedEvent
0x180055457  call    McTemplateU0zq_EventWriteTransfer
0x18005545c  mov     ebx, [rbp+3Fh+var_A0]
0x18005545f  lea     rcx, [rbp+3Fh+var_70]
0x180055463  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x180055468  jmp     loc_180055AB1
0x18005546d  lea     rcx, a136155732; "1.3.6.1.5.5.7.3.2"
0x180055474  call    cs:__imp_SysAllocString
0x18005547a  mov     rbx, rax
0x18005547d  mov     [rbp+3Fh+var_80], rax
0x180055481  test    rax, rax
0x180055484  jnz     short loc_1800554B2
0x180055486  lea     rcx, [rbp+3Fh+var_80]
0x18005548a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005548f  nop
0x180055490  lea     rcx, [rbp+3Fh+var_70]
0x180055494  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x180055499  nop
0x18005549a  lea     rcx, [rbp+3Fh+var_90]
0x18005549e  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x1800554a3  nop
0x1800554a4  lea     rcx, [rbp+3Fh+var_98]
0x1800554a8  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x1800554ad  jmp     loc_180055294
0x1800554b2  mov     [rbp+3Fh+var_60], 0
0x1800554ba  lea     rcx, [rbp+3Fh+var_60]
0x1800554be  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x1800554c3  lea     rax, [rbp+3Fh+var_60]
0x1800554c7  mov     [rsp+0D0h+ppv], rax; ppv
0x1800554cc  lea     rsi, _GUID_728ab300_217d_11da_b2a4_000e7bbb2b09
0x1800554d3  mov     r9, rsi; riid
0x1800554d6  mov     r8d, r13d; dwClsContext
0x1800554d9  xor     edx, edx; pUnkOuter
0x1800554db  lea     r14, _GUID_884e2000_217d_11da_b2a4_000e7bbb2b09
0x1800554e2  mov     rcx, r14; rclsid
0x1800554e5  call    cs:__imp_CoCreateInstance
0x1800554eb  mov     edi, eax
0x1800554ed  mov     [rbp+3Fh+var_A0], eax
0x1800554f0  test    eax, eax
0x1800554f2  jns     short loc_180055542
0x1800554f4  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x1800554fb  jz      short loc_180055516
0x1800554fd  mov     r9d, eax
0x180055500  lea     r8, aCocreateinstan_3; "CoCreateInstance IObjectId"
0x180055507  lea     rdx, FunctionFailedEvent
0x18005550e  call    McTemplateU0zq_EventWriteTransfer
0x180055513  mov     edi, [rbp+3Fh+var_A0]
0x180055516  lea     rcx, [rbp+3Fh+var_60]
0x18005551a  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x18005551f  nop
0x180055520  lea     rcx, [rbp+3Fh+var_80]
0x180055524  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180055529  nop
0x18005552a  lea     rcx, [rbp+3Fh+var_70]
0x18005552e  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x180055533  nop
0x180055534  lea     rcx, [rbp+3Fh+var_90]
0x180055538  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x18005553d  jmp     loc_180055305
0x180055542  mov     rcx, [rbp+3Fh+var_60]
0x180055546  mov     rax, [rcx]
0x180055549  mov     rdx, rbx
0x18005554c  mov     rax, [rax+40h]
0x180055550  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055555  mov     ebx, eax
0x180055557  mov     [rbp+3Fh+var_A0], eax
0x18005555a  test    eax, eax
0x18005555c  jns     short loc_180055598
0x18005555e  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x180055565  jz      short loc_180055580
0x180055567  mov     r9d, eax
0x18005556a  lea     r8, aIobjectidIniti; "IObjectId->InitializeFromValue"
0x180055571  lea     rdx, FunctionFailedEvent
0x180055578  call    McTemplateU0zq_EventWriteTransfer
0x18005557d  mov     ebx, [rbp+3Fh+var_A0]
0x180055580  lea     rcx, [rbp+3Fh+var_60]
0x180055584  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x180055589  nop
0x18005558a  lea     rcx, [rbp+3Fh+var_80]
0x18005558e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180055593  jmp     loc_18005545F
0x180055598  mov     [rbp+3Fh+var_48], 0
0x1800555a0  lea     rcx, [rbp+3Fh+var_48]
0x1800555a4  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x1800555a9  lea     rax, [rbp+3Fh+var_48]
0x1800555ad  mov     [rsp+0D0h+ppv], rax; ppv
0x1800555b2  lea     r9, _GUID_728ab301_217d_11da_b2a4_000e7bbb2b09; riid
0x1800555b9  mov     r8d, r13d; dwClsContext
0x1800555bc  xor     edx, edx; pUnkOuter
0x1800555be  lea     rcx, _GUID_884e2001_217d_11da_b2a4_000e7bbb2b09; rclsid
0x1800555c5  call    cs:__imp_CoCreateInstance
0x1800555cb  mov     ebx, eax
0x1800555cd  mov     [rbp+3Fh+var_A0], eax
0x1800555d0  test    eax, eax
0x1800555d2  jns     short loc_180055604
0x1800555d4  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x1800555db  jz      short loc_1800555F6
0x1800555dd  lea     r8, aCocreateinstan; "CoCreateInstance IObjectIds"
0x1800555e4  mov     r9d, eax
0x1800555e7  lea     rdx, FunctionFailedEvent
0x1800555ee  call    McTemplateU0zq_EventWriteTransfer
0x1800555f3  mov     ebx, [rbp+3Fh+var_A0]
0x1800555f6  lea     rcx, [rbp+3Fh+var_48]
0x1800555fa  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x1800555ff  jmp     loc_180055580
0x180055604  mov     rcx, [rbp+3Fh+var_48]
0x180055608  mov     rax, [rcx]
0x18005560b  mov     rdx, [rbp+3Fh+var_60]
0x18005560f  mov     rax, [rax+50h]
0x180055613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055618  mov     ebx, eax
0x18005561a  mov     [rbp+3Fh+var_A0], eax
0x18005561d  test    eax, eax
0x18005561f  jns     short loc_180055633
0x180055621  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x180055628  jz      short loc_1800555F6
0x18005562a  lea     r8, aIobjectidsAdd; "IObjectIds->Add"
0x180055631  jmp     short loc_1800555E4
0x180055633  mov     rcx, [rbp+3Fh+var_70]
0x180055637  mov     rax, [rcx]
0x18005563a  mov     rdx, [rbp+3Fh+var_48]
0x18005563e  mov     rax, [rax+60h]
0x180055642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055647  mov     ebx, eax
0x180055649  mov     [rbp+3Fh+var_A0], eax
0x18005564c  test    eax, eax
0x18005564e  jns     short loc_180055662
0x180055650  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x180055657  jz      short loc_1800555F6
0x180055659  lea     r8, aIobjectidsInit; "IObjectIds->InitializeEncode"
0x180055660  jmp     short loc_1800555E4
  ... truncated ...
```
