# TryGetFileTypeAssocFromStateRepository(ushort const *,Windows::Internal::StateRepository::IFileTypeAssociation * *)

- ea: `0x180027bc0`
- end: `0x1800286bf`
- name: `?TryGetFileTypeAssocFromStateRepository@@YAJPEBGPEAPEAUIFileTypeAssociation@StateRepository@Internal@Windows@@@Z`
- size: `2815`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct Windows::Internal::StateRepository::IFileTypeAssociation **)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180027758`

## callees

- `0x180003f94`
- `0x180004148`
- `0x180025dd4`
- `0x180027bc0`
- `0x1800286c8`
- `0x1800299d0`
- `0x18002d070`
- `0x18005cdd8`
- `0x180060c38`
- `0x180067f38`
- `0x18006ed20`
- `0x18006fb8c`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180028567`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180028567`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002820f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180028600`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002820f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180028600`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027e84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027fd6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800282ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028372`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002851b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027e84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027fd6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800282ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028372`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002851b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180027c19`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180027c19`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027db3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027e07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027e53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027f1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028123`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800281ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800282b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800283fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028451`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800284a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800285a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002866e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002869b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027db3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027e07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027e53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027f1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028123`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800281ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800282b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800283fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028451`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800284a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800285a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002866e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002869b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180027ddc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180028150`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180028427`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180027ddc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180028150`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180028427`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180027c42`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180027c42`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 __fastcall TryGetFileTypeAssocFromStateRepository(
        const unsigned __int16 *a1,
        struct Windows::Internal::StateRepository::IFileTypeAssociation **a2)
{
  unsigned int v4; // r13d
  HRESULT v5; // eax
  HSTRING v6; // rbx
  int ActivationFactory; // eax
  unsigned int v8; // ebx
  bool v9; // si
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, _QWORD, _QWORD, __int64 *); // rbx
  __int64 v12; // rax
  int v13; // eax
  int v14; // eax
  unsigned int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rcx
  unsigned int j; // esi
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, _QWORD, struct Windows::Internal::StateRepository::IFileTypeAssociation **); // rbx
  int v22; // eax
  struct Windows::Internal::StateRepository::IFileTypeAssociation *v23; // rdi
  __int64 (__fastcall *v24)(struct Windows::Internal::StateRepository::IFileTypeAssociation *, HSTRING *); // rbx
  int v25; // eax
  PCWSTR v26; // rax
  unsigned __int16 *v27; // rcx
  signed __int64 v28; // rax
  int v29; // r8d
  int v30; // edx
  struct Windows::Internal::StateRepository::IFileTypeAssociation *v31; // rcx
  struct Windows::Internal::StateRepository::IFileTypeAssociation *v32; // rcx
  struct Windows::Internal::StateRepository::IFileTypeAssociation *v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  int v36; // eax
  unsigned int v37; // esi
  int v38; // eax
  __int64 v39; // rdx
  struct Windows::Internal::StateRepository::IFileTypeAssociation *v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rcx
  __int64 (__fastcall *v43)(__int64, _QWORD, __int64 *); // rbx
  __int64 v44; // rax
  __int64 v45; // rcx
  __int64 v46; // rcx
  char **Reserved1; // r14
  unsigned __int64 v48; // rsi
  HSTRING v49; // r15
  __int64 v50; // rdi
  __int64 (__fastcall *v51)(__int64, _QWORD, __int64 *); // rbx
  int v52; // eax
  __int64 v53; // rdi
  __int64 (__fastcall *v54)(__int64, HSTRING *); // rbx
  int v55; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v57; // rdx
  __int64 v58; // rcx
  int v59; // eax
  unsigned __int64 v60; // rbx
  unsigned __int64 v61; // rdi
  LPCWCH *v62; // rax
  __int64 v63; // rcx
  int v64; // eax
  unsigned __int64 v65; // r15
  unsigned __int64 v66; // r12
  int v67; // edi
  __int64 v68; // rcx
  __int64 v69; // rcx
  __int64 v70; // rcx
  __int64 v71; // rcx
  __int64 v72; // rcx
  __int64 v73; // rcx
  __int64 v74; // rdi
  __int64 (__fastcall *v75)(__int64, _QWORD, __int64 *); // rbx
  int v76; // eax
  __int64 v77; // rdi
  __int64 (__fastcall *v78)(__int64, LPCWCH *); // rbx
  int v79; // eax
  PCWSTR v80; // rax
  char *v81; // rcx
  char *v82; // rax
  int v83; // r8d
  int v84; // edx
  __int64 v85; // rcx
  unsigned int i; // esi
  __int64 v87; // rcx
  __int64 v88; // rcx
  __int64 v89; // rcx
  __int64 v90; // rcx
  __int64 v91; // rcx
  const WCHAR *v92; // r13
  __int64 *v93; // rcx
  char *v94; // r14
  BOOL bIgnoreCase; // [rsp+20h] [rbp-69h]
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-59h] BYREF
  HSTRING string; // [rsp+48h] [rbp-41h] BYREF
  LPCWCH lpString2; // [rsp+50h] [rbp-39h] BYREF
  __int64 v99; // [rsp+58h] [rbp-31h] BYREF
  __int64 v100; // [rsp+60h] [rbp-29h] BYREF
  struct Windows::Internal::StateRepository::IFileTypeAssociation *v101; // [rsp+68h] [rbp-21h] BYREF
  unsigned int v102; // [rsp+70h] [rbp-19h] BYREF
  __int64 v103; // [rsp+78h] [rbp-11h] BYREF
  LPVOID pv; // [rsp+80h] [rbp-9h] BYREF
  HSTRING v105; // [rsp+88h] [rbp-1h] BYREF
  __int64 v106; // [rsp+90h] [rbp+7h] BYREF
  HSTRING v107; // [rsp+98h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v107 = (HSTRING)a2;
  lpString2 = a1;
  v4 = 0;
  *a2 = 0;
  v100 = 0;
  string = 0;
  v5 = WindowsCreateStringReference(
         L"Windows.Internal.StateRepository.FileTypeAssociation",
         0x34u,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v6 = string;
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v100);
  ActivationFactory = RoGetActivationFactory(v6, &GUID_8645456f_d9a2_4b82_afec_58f0e8df0acf, &v100);
  v8 = ActivationFactory;
  if ( ActivationFactory == -2147221164 )
    goto LABEL_11;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x43,
      (unsigned int)"onecoreuap\\shell\\propsys\\getpropertystore.cpp",
      (const char *)(unsigned int)ActivationFactory,
      bIgnoreCase);
LABEL_40:
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v100);
    return v8;
  }
  v99 = 0;
  v9 = IsLocalSystem();
  v10 = v100;
  if ( v9 )
  {
    v43 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v100 + 184LL);
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v99);
    v44 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &lpString2);
    v38 = v43(v10, *(_QWORD *)(v44 + 24), &v99);
    v8 = v38;
    if ( v38 < 0 )
    {
      v39 = 77;
LABEL_44:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v39,
        (unsigned int)"onecoreuap\\shell\\propsys\\getpropertystore.cpp",
        (const char *)(unsigned int)v38,
        bIgnoreCase);
LABEL_93:
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v99);
      goto LABEL_40;
    }
  }
  else
  {
    v11 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v100 + 216LL);
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v99);
    v12 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &lpString2);
    v13 = v11(v10, 0, *(_QWORD *)(v12 + 24), &v99);
    v8 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x49,
        (unsigned int)"onecoreuap\\shell\\propsys\\getpropertystore.cpp",
        (const char *)(unsigned int)v13,
        bIgnoreCase);
      v45 = v99;
      if ( v99 )
      {
        v99 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
      }
      v46 = v100;
      if ( v100 )
      {
        v100 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
      }
      return v8;
    }
  }
  v102 = 0;
  v14 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v99 + 56LL))(v99, &v102);
  v8 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x51,
      (unsigned int)"onecoreuap\\shell\\propsys\\getpropertystore.cpp",
      (const char *)(unsigned int)v14,
      bIgnoreCase);
    v34 = v99;
    if ( v99 )
    {
      v99 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    }
    v35 = v100;
    if ( v100 )
    {
      v100 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    }
    return v8;
  }
  v15 = v102;
  if ( v102 <= 1 )
  {
    if ( v102 == 1 )
    {
      v38 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct Windows::Internal::StateRepository::IFileTypeAssociation **))(*(_QWORD *)v99 + 48LL))(
              v99,
              0,
              a2);
      v8 = v38;
      if ( v38 < 0 )
      {
        v39 = 146;
        goto LABEL_44;
      }
    }
    goto LABEL_9;
  }
  pv = 0;
  if ( v9 )
  {
LABEL_62:
    Reserved1 = 0;
    memset(&hstringHeader, 0, sizeof(hstringHeader));
    v48 = 0;
    v49 = 0;
    string = 0;
    while ( 1 )
    {
      LODWORD(v101) = v4;
      if ( v4 >= v15 )
        break;
      v106 = 0;
      v50 = v99;
      v51 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v99 + 48LL);
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v106);
      v52 = v51(v50, v4, &v106);
      v8 = v52;
      if ( v52 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x71,
          (unsigned int)"onecoreuap\\shell\\propsys\\getpropertystore.cpp",
          (const char *)(unsigned int)v52,
          bIgnoreCase);
        v71 = v106;
        if ( v106 )
        {
          v106 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
        }
        CSimplePointerArray<unsigned short,CTPolicyCoTaskMem<unsigned short>,CSimpleArrayCaseInsensitiveOrdinalStringCompareHelper>::~CSimplePointerArray<unsigned short,CTPolicyCoTaskMem<unsigned short>,CSimpleArrayCaseInsensitiveOrdinalStringCompareHelper>(&hstringHeader);
        if ( pv )
          CoTaskMemFree(pv);
        v72 = v99;
        if ( v99 )
        {
          v99 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
        }
        v73 = v100;
        if ( v100 )
        {
          v100 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
        }
        return v8;
      }
      v105 = 0;
      v53 = v106;
      v54 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v106 + 120LL);
      WindowsDeleteString(0);
      v105 = 0;
      v55 = v54(v53, &v105);
      v8 = v55;
      if ( v55 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x74,
          (unsigned int)"onecoreuap\\shell\\propsys\\getpropertystore.cpp",
          (const char *)(unsigned int)v55,
          bIgnoreCase);
        WindowsDeleteString(v105);
        v105 = 0;
        v68 = v106;
        if ( v106 )
        {
          v106 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
        }
        CSimplePointerArray<unsigned short,CTPolicyCoTaskMem<unsigned short>,CSimpleArrayCaseInsensitiveOrdinalStringCompareHelper>::~CSimplePointerArray<unsigned short,CTPolicyCoTaskMem<unsigned short>,CSimpleArrayCaseInsensitiveOrdinalStringCompareHelper>(&hstringHeader);
        if ( pv )
          CoTaskMemFree(pv);
        v69 = v99;
        if ( v99 )
        {
          v99 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
        }
        v70 = v100;
        if ( v100 )
        {
          v100 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 16LL))(v70);
        }
        return v8;
      }
      lpString2 = 0;
      StringRawBuffer = WindowsGetStringRawBuffer(v105, 0);
      v59 = _AllocString<CTCoAllocPolicy>(v58, v57, StringRawBuffer, &lpString2);
      v8 = v59;
      if ( v59 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x77,
          (unsigned int)"onecoreuap\\shell\\propsys\\getpropertystore.cpp",
          (const char *)(unsigned int)v59,
          bIgnoreCase);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpString2);
        WindowsDeleteString(v105);
        v105 = 0;
        v93 = &v106;
LABEL_150:
        Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(v93);
        goto LABEL_91;
      }
      v60 = 0;
      if ( v48 )
      {
        v64 = 0;
        v65 = 0;
        v60 = 0;
        v66 = v48 - 1;
        v67 = 0;
        while ( v67 >= 0 )
        {
          v60 = (v66 + v65) >> 1;
          v64 = CompareStringOrdinal((LPCWCH)Reserved1[v60], -1, lpString2, -1, 1) - 2;
          if ( v64 <= 0 )
          {
            if ( v64 >= 0 )
            {
              if ( v60 )
              {
                v92 = lpString2;
                do
                {
                  if ( CompareStringOrdinal((LPCWCH)Reserved1[v60 - 1], -1, v92, -1, 1) != 2 )
                    break;
                  --v60;
                }
                while ( v60 );
                v4 = (unsigned int)v101;
              }
              goto LABEL_88;
            }
            v65 = v60 + 1;
          }
          else if ( v60 )
          {
            v66 = v60 - 1;
          }
          else
          {
            v67 = -2147319765;
          }
          if ( v66 < v65 )
            v67 = -2147319765;
        }
        if ( v64 < 0 )
          v60 = v65;
LABEL_88:
        v49 = string;
      }
      v61 = v60 + 1;
      if ( v60 < v48 )
        v61 = v48 + 1;
      if ( v61 > (unsigned __int64)v49 )
      {
        v36 = CTSimpleArray<ATL::CComPtr<ParsedPropertyDescription>,4294967294,CTPolicyCoTaskMem<ATL::CComPtr<ParsedPropertyDescription>>,CSimpleArrayStandardCompareHelper<ATL::CComPtr<ParsedPropertyDescription>>,CSimpleArrayStandardMergeHelper<ATL::CComPtr<ParsedPropertyDescription>>>::_EnsureCapacity(
                &hstringHeader,
                v61);
        v37 = v36;
        if ( v36 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x78,
            (unsigned int)"onecoreuap\\shell\\propsys\\getpropertystore.cpp",
            (const char *)(unsigned int)v36,
            bIgnoreCase);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpString2);
          WindowsDeleteString(v105);
          v105 = 0;
          Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v106);
          CSimplePointerArray<unsigned short,CTPolicyCoTaskMem<unsigned short>,CSimpleArrayCaseInsensitiveOrdinalStringCompareHelper>::~CSimplePointerArray<unsigned short,CTPolicyCoTaskMem<unsigned short>,CSimpleArrayCaseInsensitiveOrdinalStringCompareHelper>(&hstringHeader);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pv);
          Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v99);
          v8 = v37;
          goto LABEL_40;
        }
        v48 = *(_QWORD *)&hstringHeader.Reserved.Reserved2[8];
        Reserved1 = (char **)hstringHeader.Reserved.Reserved1;
        v49 = string;
      }
      if ( v60 < v48 )
        memmove_0(&Reserved1[v60 + 1], &Reserved1[v60], 8 * (v48 - v60));
      v48 = v61;
      *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = v61;
      v62 = (LPCWCH *)&Reserved1[v60];
      if ( v62 )
        *v62 = lpString2;
      WindowsDeleteString(v105);
      v105 = 0;
      v63 = v106;
      if ( v106 )
      {
        v106 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
      }
      ++v4;
      v15 = v102;
    }
    if ( !v48 )
    {
      v8 = -2147316575;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7D,
        (unsigned int)"onecoreuap\\shell\\propsys\\getpropertystore.cpp",
        (const char *)0x80028CA1LL,
        bIgnoreCase);
LABEL_91:
      CSimplePointerArray<unsigned short,CTPolicyCoTaskMem<unsigned short>,CSimpleArrayCaseInsensitiveOrdinalStringCompareHelper>::~CSimplePointerArray<unsigned short,CTPolicyCoTaskMem<unsigned short>,CSimpleArrayCaseInsensitiveOrdinalStringCompareHelper>(&hstringHeader);
LABEL_92:
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pv);
      goto LABEL_93;
    }
    v94 = *Reserved1;
    for ( i = 0; ; ++i )
    {
      if ( i >= v15 )
        goto LABEL_126;
      v103 = 0;
      v74 = v99;
      v75 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v99 + 48LL);
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v103);
      v76 = v75(v74, i, &v103);
      v8 = v76;
      if ( v76 < 0 )
        break;
      lpString2 = 0;
      v77 = v103;
      v78 = *(__int64 (__fastcall **)(__int64, LPCWCH *))(*(_QWORD *)v103 + 120LL);
      WindowsDeleteString(0);
      lpString2 = 0;
      v79 = v78(v77, &lpString2);
      v8 = v79;
      if ( v79 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x86,
          (unsigned int)"onecoreuap\\shell\\propsys\\getpropertystore.cpp",
          (const char *)(unsigned int)v79,
          bIgnoreCase);
        WindowsDeleteString((HSTRING)lpString2);
        lpString2 = 0;
        v93 = &v103;
        goto LABEL_150;
      }
      v80 = WindowsGetStringRawBuffer((HSTRING)lpString2, 0);
      v81 = v94;
      v82 = (char *)((char *)v80 - v94);
      do
      {
        v83 = *(unsigned __int16 *)&v82[(_QWORD)v81];
        v84 = *(unsigned __int16 *)v81 - v83;
        if ( v84 )
          break;
        v81 += 2;
      }
      while ( v83 );
      if ( !v84 )
      {
        v87 = v103;
        if ( v103 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v103 + 8LL))(v103);
          v87 = v103;
        }
        *(_QWORD *)v107 = v87;
        WindowsDeleteString((HSTRING)lpString2);
        lpString2 = 0;
        v88 = v103;
        if ( v103 )
        {
          v103 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
        }
LABEL_126:
        CSimplePointerArray<unsigned short,CTPolicyCoTaskMem<unsigned short>,CSimpleArrayCaseInsensitiveOrdinalStringCompareHelper>::~CSimplePointerArray<unsigned short,CTPolicyCoTaskMem<unsigned short>,CSimpleArrayCaseInsensitiveOrdinalStringCompareHelper>(&hstringHeader);
        goto LABEL_31;
      }
      WindowsDeleteString((HSTRING)lpString2);
      lpString2 = 0;
      v85 = v103;
      if ( v103 )
      {
        v103 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
      }
      v15 = v102;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x83,
      (unsigned int)"onecoreuap\\shell\\propsys\\getpropertystore.cpp",
      (const char *)(unsigned int)v76,
      bIgnoreCase);
    v89 = v103;
    if ( v103 )
    {
      v103 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v89 + 16LL))(v89);
    }
    CSimplePointerArray<unsigned short,CTPolicyCoTaskMem<unsigned short>,CSimpleArrayCaseInsensitiveOrdinalStringCompareHelper>::~CSimplePointerArray<unsigned short,CTPolicyCoTaskMem<unsigned short>,CSimpleArrayCaseInsensitiveOrdinalStringCompareHelper>(&hstringHeader);
    if ( pv )
      CoTaskMemFree(pv);
    v90 = v99;
    if ( v99 )
    {
      v99 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
    }
    v91 = v100;
    if ( v100 )
    {
      v100 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
    }
    return v8;
  }
  if ( (int)GetDefaultProgIdForFileType(a1, (unsigned __int16 **)&pv) < 0 )
  {
    v15 = v102;
    goto LABEL_62;
  }
  for ( j = 0; j < v102; ++j )
  {
    v101 = 0;
    v20 = v99;
    v21 = *(__int64 (__fastcall **)(__int64, _QWORD, struct Windows::Internal::StateRepository::IFileTypeAssociation **))(*(_QWORD *)v99 + 48LL);
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v101);
    v22 = v21(v20, j, &v101);
    v8 = v22;
    if ( v22 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5E,
        (unsigned int)"onecoreuap\\shell\\propsys\\getpropertystore.cpp",
        (const char *)(unsigned int)v22,
        bIgnoreCase);
      v40 = v101;
      if ( v101 )
      {
        v101 = 0;
        (*(void (__fastcall **)(struct Windows::Internal::StateRepository::IFileTypeAssociation *))(*(_QWORD *)v40 + 16LL))(v40);
      }
      if ( pv )
        CoTaskMemFree(pv);
      v41 = v99;
      if ( v99 )
      {
        v99 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
      }
      v42 = v100;
      if ( v100 )
      {
        v100 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
      }
      return v8;
    }
    v107 = 0;
    v23 = v101;
    v24 = *(__int64 (__fastcall **)(struct Windows::Internal::StateRepository::IFileTypeAssociation *, HSTRING *))(*(_QWORD *)v101 + 120LL);
    WindowsDeleteString(0);
    v107 = 0;
    v25 = v24(v23, &v107);
    v8 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x61,
        (unsigned int)"onecoreuap\\shell\\propsys\\getpropertystore.cpp",
        (const char *)(unsigned int)v25,
        bIgnoreCase);
      WindowsDeleteString(v107);
      v107 = 0;
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v101);
      goto LABEL_92;
    }
    v26 = WindowsGetStringRawBuffer(v107, 0);
    v27 = (unsigned __int16 *)pv;
    v28 = (char *)v26 - (_BYTE *)pv;
    do
    {
      v29 = *(unsigned __int16 *)((char *)v27 + v28);
      v30 = *v27 - v29;
      if ( v30 )
        break;
      ++v27;
    }
    while ( v29 );
    if ( !v30 )
    {
      v32 = v101;
      if ( v101 )
      {
        (*(void (__fastcall **)(struct Windows::Internal::StateRepository::IFileTypeAssociation *))(*(_QWORD *)v101 + 8LL))(v101);
        v32 = v101;
      }
      *a2 = v32;
      WindowsDeleteString(v107);
      v107 = 0;
      v33 = v101;
      if ( v101 )
      {
        v101 = 0;
        (*(void (__fastcall **)(struct Windows::Internal::StateRepository::IFileTypeAssociation *))(*(_QWORD *)v33 + 16LL))(v33);
      }
      break;
    }
    WindowsDeleteString(v107);
    v107 = 0;
    v31 = v101;
    if ( v101 )
    {
      v101 = 0;
      (*(void (__fastcall **)(struct Windows::Internal::StateRepository::IFileTypeAssociation *))(*(_QWORD *)v31 + 16LL))(v31);
    }
  }
LABEL_31:
  if ( pv )
    CoTaskMemFree(pv);
LABEL_9:
  v16 = v99;
  if ( v99 )
  {
    v99 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  }
LABEL_11:
  v17 = v100;
  if ( v100 )
  {
    v100 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  return 0;
}

```

## disassembly

```asm
0x180027bc0  mov     [rsp-8+arg_10], rbx
0x180027bc5  push    rbp
0x180027bc6  push    rsi
0x180027bc7  push    rdi
0x180027bc8  push    r12
0x180027bca  push    r13
0x180027bcc  push    r14
0x180027bce  push    r15
0x180027bd0  lea     rbp, [rsp-27h]
0x180027bd5  sub     rsp, 0B0h
0x180027bdc  mov     rax, cs:__security_cookie
0x180027be3  xor     rax, rsp
0x180027be6  mov     [rbp+57h+var_40], rax
0x180027bea  mov     r12, rdx
0x180027bed  mov     [rbp+57h+var_48], rdx
0x180027bf1  mov     r14, rcx
0x180027bf4  mov     [rbp+57h+lpString2], rcx
0x180027bf8  xor     r13d, r13d
0x180027bfb  mov     [rdx], r13
0x180027bfe  mov     [rbp+57h+var_80], r13
0x180027c02  mov     [rbp+57h+string], r13
0x180027c06  lea     r9, [rbp+57h+string]; string
0x180027c0a  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180027c0e  lea     edx, [r13+34h]; length
0x180027c12  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_FileTypeAssociation@@3QBGB; "Windows.Internal.StateRepository.FileTy"...
0x180027c19  call    cs:__imp_WindowsCreateStringReference
0x180027c1f  test    eax, eax
0x180027c21  js      loc_18002855B
0x180027c27  mov     rbx, [rbp+57h+string]
0x180027c2b  lea     rcx, [rbp+57h+var_80]
0x180027c2f  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180027c34  lea     r8, [rbp+57h+var_80]
0x180027c38  lea     rdx, _GUID_8645456f_d9a2_4b82_afec_58f0e8df0acf
0x180027c3f  mov     rcx, rbx
0x180027c42  call    cs:__imp_RoGetActivationFactory
0x180027c48  mov     ebx, eax
0x180027c4a  cmp     eax, 80040154h
0x180027c4f  jz      loc_18002805E
0x180027c55  test    eax, eax
0x180027c57  js      loc_18002856E
0x180027c5d  mov     [rbp+57h+var_88], r13
0x180027c61  call    ?IsLocalSystem@@YA_NXZ; IsLocalSystem(void)
0x180027c66  mov     sil, al
0x180027c69  mov     rdi, [rbp+57h+var_80]
0x180027c6d  test    al, al
0x180027c6f  jnz     loc_180028016
0x180027c75  mov     rcx, [rdi]
0x180027c78  mov     rbx, [rcx+0D8h]
0x180027c7f  lea     rcx, [rbp+57h+var_88]
0x180027c83  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180027c88  lea     rdx, [rbp+57h+lpString2]
0x180027c8c  lea     rcx, [rbp+57h+hstringHeader]
0x180027c90  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180027c95  nop
0x180027c96  lea     r9, [rbp+57h+var_88]
0x180027c9a  mov     r8, [rax+18h]
0x180027c9e  xor     edx, edx
0x180027ca0  mov     rcx, rdi
0x180027ca3  mov     rax, rbx
0x180027ca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027cab  mov     ebx, eax
0x180027cad  test    eax, eax
0x180027caf  js      loc_180028063
0x180027cb5  mov     [rbp+57h+var_70], r13d
0x180027cb9  mov     rcx, [rbp+57h+var_88]
0x180027cbd  mov     rax, [rcx]
0x180027cc0  lea     rdx, [rbp+57h+var_70]
0x180027cc4  mov     rax, [rax+38h]
0x180027cc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ccd  mov     ebx, eax
0x180027ccf  test    eax, eax
0x180027cd1  js      loc_180027E8F
0x180027cd7  mov     eax, [rbp+57h+var_70]
0x180027cda  cmp     eax, 1
0x180027cdd  ja      short loc_180027D42
0x180027cdf  jz      loc_180027F5E
0x180027ce5  mov     rcx, [rbp+57h+var_88]
0x180027ce9  test    rcx, rcx
0x180027cec  jz      short loc_180027CFF
0x180027cee  mov     [rbp+57h+var_88], r13
0x180027cf2  mov     rax, [rcx]
0x180027cf5  mov     rax, [rax+10h]
0x180027cf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027cfe  nop
0x180027cff  mov     rcx, [rbp+57h+var_80]
0x180027d03  test    rcx, rcx
0x180027d06  jz      short loc_180027D19
0x180027d08  mov     [rbp+57h+var_80], r13
0x180027d0c  mov     rax, [rcx]
0x180027d0f  mov     rax, [rax+10h]
0x180027d13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d18  nop
0x180027d19  xor     eax, eax
0x180027d1b  mov     rcx, [rbp+57h+var_40]
0x180027d1f  xor     rcx, rsp; StackCookie
0x180027d22  call    __security_check_cookie
0x180027d27  mov     rbx, [rsp+0E0h+arg_10]
0x180027d2f  add     rsp, 0B0h
0x180027d36  pop     r15
0x180027d38  pop     r14
0x180027d3a  pop     r13
0x180027d3c  pop     r12
0x180027d3e  pop     rdi
0x180027d3f  pop     rsi
0x180027d40  pop     rbp
0x180027d41  retn
0x180027d42  mov     [rbp+57h+pv], r13
0x180027d46  test    sil, sil
0x180027d49  jnz     loc_1800280B5
0x180027d4f  lea     rdx, [rbp+57h+pv]; unsigned __int16 **
0x180027d53  mov     rcx, r14; unsigned __int16 *
0x180027d56  call    ?GetDefaultProgIdForFileType@@YAJPEBGPEAPEAG@Z; GetDefaultProgIdForFileType(ushort const *,ushort * *)
0x180027d5b  test    eax, eax
0x180027d5d  js      loc_1800285C0
0x180027d63  mov     esi, r13d
0x180027d66  cmp     esi, [rbp+57h+var_70]
0x180027d69  jnb     loc_180027E77
0x180027d6f  mov     [rbp+57h+var_78], r13
0x180027d73  mov     rdi, [rbp+57h+var_88]
0x180027d77  mov     rax, [rdi]
0x180027d7a  mov     rbx, [rax+30h]
0x180027d7e  lea     rcx, [rbp+57h+var_78]
0x180027d82  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180027d87  lea     r8, [rbp+57h+var_78]
0x180027d8b  mov     edx, esi
0x180027d8d  mov     rcx, rdi
0x180027d90  mov     rax, rbx
0x180027d93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d98  mov     ebx, eax
0x180027d9a  test    eax, eax
0x180027d9c  js      loc_180027F9A
0x180027da2  mov     [rbp+57h+var_48], r13
0x180027da6  mov     rdi, [rbp+57h+var_78]
0x180027daa  mov     rax, [rdi]
0x180027dad  mov     rbx, [rax+78h]
0x180027db1  xor     ecx, ecx; string
0x180027db3  call    cs:__imp_WindowsDeleteString
0x180027db9  mov     [rbp+57h+var_48], r13
0x180027dbd  lea     rdx, [rbp+57h+var_48]
0x180027dc1  mov     rcx, rdi
0x180027dc4  mov     rax, rbx
0x180027dc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027dcc  mov     ebx, eax
0x180027dce  test    eax, eax
0x180027dd0  js      loc_18002858B
0x180027dd6  xor     edx, edx; length
0x180027dd8  mov     rcx, [rbp+57h+var_48]; string
0x180027ddc  call    cs:__imp_WindowsGetStringRawBuffer
0x180027de2  mov     rcx, [rbp+57h+pv]
0x180027de6  sub     rax, rcx
0x180027de9  movzx   edx, word ptr [rcx]
0x180027dec  movzx   r8d, word ptr [rcx+rax]
0x180027df1  sub     edx, r8d
0x180027df4  jnz     short loc_180027DFF
0x180027df6  add     rcx, 2
0x180027dfa  test    r8d, r8d
0x180027dfd  jnz     short loc_180027DE9
0x180027dff  test    edx, edx
0x180027e01  jz      short loc_180027E32
0x180027e03  mov     rcx, [rbp+57h+var_48]; string
0x180027e07  call    cs:__imp_WindowsDeleteString
0x180027e0d  mov     [rbp+57h+var_48], r13
0x180027e11  mov     rcx, [rbp+57h+var_78]
0x180027e15  test    rcx, rcx
0x180027e18  jz      short loc_180027E2B
0x180027e1a  mov     [rbp+57h+var_78], r13
0x180027e1e  mov     rax, [rcx]
0x180027e21  mov     rax, [rax+10h]
0x180027e25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e2a  nop
0x180027e2b  inc     esi
0x180027e2d  jmp     loc_180027D66
0x180027e32  mov     rcx, [rbp+57h+var_78]
0x180027e36  test    rcx, rcx
0x180027e39  jz      short loc_180027E4B
0x180027e3b  mov     rax, [rcx]
0x180027e3e  mov     rax, [rax+8]
0x180027e42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e47  mov     rcx, [rbp+57h+var_78]
0x180027e4b  mov     [r12], rcx
0x180027e4f  mov     rcx, [rbp+57h+var_48]; string
0x180027e53  call    cs:__imp_WindowsDeleteString
0x180027e59  mov     [rbp+57h+var_48], r13
0x180027e5d  mov     rcx, [rbp+57h+var_78]
0x180027e61  test    rcx, rcx
0x180027e64  jz      short loc_180027E77
0x180027e66  mov     [rbp+57h+var_78], r13
0x180027e6a  mov     rax, [rcx]
0x180027e6d  mov     rax, [rax+10h]
0x180027e71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e76  nop
0x180027e77  mov     rcx, [rbp+57h+pv]; pv
0x180027e7b  test    rcx, rcx
0x180027e7e  jz      loc_180027CE5
0x180027e84  call    cs:__imp_CoTaskMemFree
0x180027e8a  jmp     loc_180027CE5
0x180027e8f  mov     rcx, [rbp+5Fh]; this
0x180027e93  mov     r9d, ebx; char *
0x180027e96  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\propsys\\getproperty"...
0x180027e9d  mov     edx, 51h ; 'Q'; void *
0x180027ea2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027ea7  nop
0x180027ea8  mov     rcx, [rbp+57h+var_88]
0x180027eac  test    rcx, rcx
0x180027eaf  jz      short loc_180027EC2
0x180027eb1  mov     [rbp+57h+var_88], r13
0x180027eb5  mov     rax, [rcx]
0x180027eb8  mov     rax, [rax+10h]
0x180027ebc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ec1  nop
0x180027ec2  mov     rcx, [rbp+57h+var_80]
0x180027ec6  test    rcx, rcx
0x180027ec9  jz      short loc_180027EDC
0x180027ecb  mov     [rbp+57h+var_80], r13
0x180027ecf  mov     rax, [rcx]
0x180027ed2  mov     rax, [rax+10h]
0x180027ed6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027edb  nop
0x180027edc  jmp     short loc_180027F57
0x180027ede  mov     rdx, rdi
0x180027ee1  lea     rcx, [rbp+57h+hstringHeader]
0x180027ee5  call    ?_EnsureCapacity@?$CTSimpleArray@V?$CComPtr@UParsedPropertyDescription@@@ATL@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@V?$CComPtr@UParsedPropertyDescription@@@ATL@@@@V?$CSimpleArrayStandardCompareHelper@V?$CComPtr@UParsedPropertyDescription@@@ATL@@@@V?$CSimpleArrayStandardMergeHelper@V?$CComPtr@UParsedPropertyDescription@@@ATL@@@@@@QEAAJ_K0@Z; CTSimpleArray<ATL::CComPtr<ParsedPropertyDescription>,4294967294,CTPolicyCoTaskMem<ATL::CComPtr<ParsedPropertyDescription>>,CSimpleArrayStandardCompareHelper<ATL::CComPtr<ParsedPropertyDescription>>,CSimpleArrayStandardMergeHelper<ATL::CComPtr<ParsedPropertyDescription>>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x180027eea  mov     esi, eax
0x180027eec  test    eax, eax
0x180027eee  jns     loc_18002861A
0x180027ef4  mov     rcx, [rbp+5Fh]; this
0x180027ef8  mov     r9d, eax; char *
0x180027efb  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\propsys\\getproperty"...
0x180027f02  mov     edx, 78h ; 'x'; void *
0x180027f07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027f0c  nop
0x180027f0d  lea     rcx, [rbp+57h+lpString2]
0x180027f11  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180027f16  nop
0x180027f17  mov     rcx, [rbp+57h+var_58]; string
0x180027f1b  call    cs:__imp_WindowsDeleteString
0x180027f21  mov     [rbp+57h+var_58], r12
0x180027f25  lea     rcx, [rbp+57h+var_50]
0x180027f29  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180027f2e  nop
0x180027f2f  lea     rcx, [rbp+57h+hstringHeader]
0x180027f33  call    ??1?$CSimplePointerArray@GV?$CTPolicyCoTaskMem@G@@VCSimpleArrayCaseInsensitiveOrdinalStringCompareHelper@@@@QEAA@XZ; CSimplePointerArray<ushort,CTPolicyCoTaskMem<ushort>,CSimpleArrayCaseInsensitiveOrdinalStringCompareHelper>::~CSimplePointerArray<ushort,CTPolicyCoTaskMem<ushort>,CSimpleArrayCaseInsensitiveOrdinalStringCompareHelper>(void)
0x180027f38  nop
0x180027f39  lea     rcx, [rbp+57h+pv]
0x180027f3d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180027f42  nop
0x180027f43  lea     rcx, [rbp+57h+var_88]
0x180027f47  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180027f4c  mov     ebx, esi
0x180027f4e  lea     rcx, [rbp+57h+var_80]
0x180027f52  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180027f57  mov     eax, ebx
0x180027f59  jmp     loc_180027D1B
0x180027f5e  mov     rcx, [rbp+57h+var_88]
0x180027f62  mov     rax, [rcx]
0x180027f65  mov     r8, r12
0x180027f68  xor     edx, edx
0x180027f6a  mov     rax, [rax+30h]
0x180027f6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027f73  mov     ebx, eax
0x180027f75  test    eax, eax
0x180027f77  jns     loc_180027CE5
0x180027f7d  mov     edx, 92h; void *
0x180027f82  mov     r9d, eax; char *
0x180027f85  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\propsys\\getproperty"...
0x180027f8c  mov     rcx, [rbp+5Fh]; this
0x180027f90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027f95  jmp     loc_18002828A
0x180027f9a  mov     rcx, [rbp+5Fh]; this
0x180027f9e  mov     r9d, ebx; char *
0x180027fa1  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\propsys\\getproperty"...
0x180027fa8  mov     edx, 5Eh ; '^'; void *
0x180027fad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027fb2  nop
0x180027fb3  mov     rcx, [rbp+57h+var_78]
0x180027fb7  test    rcx, rcx
0x180027fba  jz      short loc_180027FCD
0x180027fbc  mov     [rbp+57h+var_78], r13
0x180027fc0  mov     rax, [rcx]
0x180027fc3  mov     rax, [rax+10h]
0x180027fc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027fcc  nop
0x180027fcd  mov     rcx, [rbp+57h+pv]; pv
0x180027fd1  test    rcx, rcx
0x180027fd4  jz      short loc_180027FDD
0x180027fd6  call    cs:__imp_CoTaskMemFree
0x180027fdc  nop
0x180027fdd  mov     rcx, [rbp+57h+var_88]
0x180027fe1  test    rcx, rcx
0x180027fe4  jz      short loc_180027FF7
0x180027fe6  mov     [rbp+57h+var_88], r13
0x180027fea  mov     rax, [rcx]
0x180027fed  mov     rax, [rax+10h]
0x180027ff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ff6  nop
0x180027ff7  mov     rcx, [rbp+57h+var_80]
0x180027ffb  test    rcx, rcx
0x180027ffe  jz      short loc_180028011
0x180028000  mov     [rbp+57h+var_80], r13
0x180028004  mov     rax, [rcx]
  ... truncated ...
```
