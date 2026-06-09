# Utils::ExecuteWmiMethod(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,Microsoft::WRL::ComPtr<IWbemClassObject> &)

- ea: `0x1800d10e8`
- end: `0x1800d2106`
- name: `?ExecuteWmiMethod@Utils@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@000AEAV?$ComPtr@UIWbemClassObject@@@WRL@Microsoft@@@Z`
- size: `4126`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18007e550`
- `0x1800c9100`

## callees

- `0x180008dc0`
- `0x180011ce4`
- `0x180014f2c`
- `0x180016748`
- `0x18007245c`
- `0x180072610`
- `0x1800d10e8`
- `0x1800d4240`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800d14ab`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800d1719`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800d14ab`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800d1719`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d11c9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d11c9`

## string_xrefs

- `0x1800d1170`: `__Path`
- `0x1800d13c9`: `onecore\base\appcompat\programs\devicecensus\dlls\utils.cpp`
- `0x1800d14c2`: `onecore\base\appcompat\programs\devicecensus\dlls\utils.cpp`
- `0x1800d163d`: `onecore\base\appcompat\programs\devicecensus\dlls\utils.cpp`
- `0x1800d1730`: `onecore\base\appcompat\programs\devicecensus\dlls\utils.cpp`
- `0x1800d1902`: `onecore\base\appcompat\programs\devicecensus\dlls\utils.cpp`
- `0x1800d1a06`: `onecore\base\appcompat\programs\devicecensus\dlls\utils.cpp`
- `0x1800d1b56`: `onecore\base\appcompat\programs\devicecensus\dlls\utils.cpp`
- `0x1800d1c91`: `onecore\base\appcompat\programs\devicecensus\dlls\utils.cpp`
- `0x1800d1dae`: `onecore\base\appcompat\programs\devicecensus\dlls\utils.cpp`
- `0x1800d1eef`: `onecore\base\appcompat\programs\devicecensus\dlls\utils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall Utils::ExecuteWmiMethod(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        __int64 *a5)
{
  HRESULT v9; // esi
  LPVOID v10; // rcx
  LPVOID v12; // rsi
  __int64 (__fastcall *v13)(LPVOID, __int64, _QWORD, _QWORD); // r13
  _bstr_t *v14; // rax
  __int64 v15; // rdx
  unsigned int v16; // ebx
  unsigned int v17; // edi
  LPVOID v18; // rcx
  LPVOID v19; // rcx
  HRESULT v20; // eax
  LPVOID v21; // rcx
  ULONG (__stdcall *Release)(IUnknown *); // r13
  _bstr_t *v23; // rax
  __int64 v24; // rbx
  const unsigned __int16 *v25; // rdx
  _bstr_t *v26; // rax
  __int64 v27; // rdx
  LPVOID v28; // rcx
  HRESULT v29; // eax
  LPVOID v30; // rcx
  char IsEnabled; // al
  ULONG (__stdcall *AddRef)(IUnknown *); // rsi
  int v33; // eax
  __int64 v34; // rcx
  __int64 v35; // rcx
  IUnknown *v36; // rcx
  IUnknown *v37; // rcx
  LPVOID v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rcx
  IUnknown *v41; // rcx
  IUnknown *v42; // rcx
  LPVOID v43; // rcx
  int v44; // eax
  __int64 v45; // rcx
  __int64 v46; // rcx
  IUnknown *v47; // rcx
  IUnknown *v48; // rcx
  LPVOID v49; // rcx
  IUnknown *v50; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rsi
  __int64 v52; // rcx
  _bstr_t *v53; // rax
  __int64 v54; // rdx
  __int64 v55; // rcx
  __int64 v56; // rcx
  IUnknown *v57; // rcx
  IUnknown *v58; // rcx
  LPVOID v59; // rcx
  __int64 v60; // rbx
  __int64 (__fastcall *v61)(__int64, __int64, _QWORD, _QWORD); // rsi
  __int64 v62; // rcx
  const unsigned __int16 *v63; // rdx
  _bstr_t *v64; // rax
  __int64 v65; // rdx
  __int64 v66; // rcx
  __int64 v67; // rcx
  IUnknown *v68; // rcx
  IUnknown *v69; // rcx
  LPVOID v70; // rcx
  __int64 v71; // rbx
  __int64 (__fastcall *v72)(__int64, __int64, _QWORD, __int128 *); // rsi
  const unsigned __int16 *v73; // rdx
  _bstr_t *v74; // rax
  __int64 v75; // rdx
  __int64 v76; // rcx
  __int64 v77; // rcx
  IUnknown *v78; // rcx
  IUnknown *v79; // rcx
  LPVOID v80; // rcx
  IUnknown *v81; // rbx
  HRESULT (__stdcall *v82)(IUnknown *, const IID *const, void **); // rsi
  __int64 v83; // rcx
  _bstr_t *v84; // rax
  __int64 v85; // r8
  __int64 v86; // rcx
  __int64 v87; // rcx
  IUnknown *v88; // rcx
  IUnknown *v89; // rcx
  LPVOID v90; // rcx
  __int64 v91; // rcx
  __int64 v92; // rcx
  IUnknown *v93; // rcx
  IUnknown *v94; // rcx
  LPVOID v95; // rcx
  __int64 v96; // rcx
  __int64 v97; // rcx
  IUnknown *v98; // rcx
  IUnknown *v99; // rcx
  LPVOID v100; // rcx
  int ppv; // [rsp+20h] [rbp-C1h]
  int ppva; // [rsp+20h] [rbp-C1h]
  __int64 v103; // [rsp+50h] [rbp-91h] BYREF
  IUnknown *pProxy; // [rsp+58h] [rbp-89h]
  IUnknown *v105; // [rsp+60h] [rbp-81h]
  int v106[2]; // [rsp+68h] [rbp-79h] BYREF
  LPVOID v107; // [rsp+70h] [rbp-71h] BYREF
  _BYTE v108[8]; // [rsp+78h] [rbp-69h] BYREF
  int v109; // [rsp+80h] [rbp-61h] BYREF
  _BYTE v110[8]; // [rsp+88h] [rbp-59h] BYREF
  __int128 v111; // [rsp+90h] [rbp-51h] BYREF
  __int64 v112; // [rsp+A0h] [rbp-41h]
  unsigned __int16 *v113[2]; // [rsp+A8h] [rbp-39h] BYREF
  __int128 v114; // [rsp+B8h] [rbp-29h]
  unsigned __int16 *v115[2]; // [rsp+C8h] [rbp-19h] BYREF
  __int128 v116; // [rsp+D8h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+57h]

  v107 = 0;
  pProxy = 0;
  v105 = 0;
  v103 = 0;
  *(_QWORD *)v106 = 0;
  *(_OWORD *)v115 = 0;
  v116 = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)v115, L"WQL", 3u);
  *(_OWORD *)v113 = 0;
  v114 = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)v113, L"__Path", 6u);
  v109 = 0;
  v111 = 0;
  v112 = 0;
  v9 = CoCreateInstance(&CLSID_WbemLocator, 0, 1u, &GUID_dc12a687_737f_11cf_884d_00aa004b2e24, &v107);
  if ( v9 < 0 )
  {
    std::wstring::~wstring((char **)v113);
    std::wstring::~wstring((char **)v115);
    v10 = v107;
    if ( v107 )
    {
      v107 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v10 + 16LL))(v10);
    }
    return (unsigned int)v9;
  }
  v12 = v107;
  v13 = *(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, _QWORD))(*(_QWORD *)v107 + 24LL);
  if ( *((_QWORD *)a2 + 3) > 7u )
    a2 = *(unsigned __int16 **)a2;
  v14 = _bstr_t::_bstr_t((_bstr_t *)v110, a2);
  if ( *(_QWORD *)v14 )
    v15 = **(_QWORD **)v14;
  else
    v15 = 0;
  v16 = v13(v12, v15, 0, 0);
  _bstr_t::~_bstr_t((_bstr_t *)v110);
  if ( (v16 & 0x80000000) != 0 )
  {
    v17 = -2147217394;
    if ( v16 == -2147217394 )
    {
      std::wstring::~wstring((char **)v113);
      std::wstring::~wstring((char **)v115);
      v18 = v107;
      if ( v107 )
      {
        v107 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v18 + 16LL))(v18);
      }
      return v17;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46A,
      (unsigned int)"onecore\\base\\appcompat\\programs\\devicecensus\\dlls\\utils.cpp",
      (const char *)v16,
      0);
    std::wstring::~wstring((char **)v113);
    std::wstring::~wstring((char **)v115);
    v19 = v107;
    if ( v107 )
    {
      v107 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v19 + 16LL))(v19);
    }
    return v16;
  }
  v20 = CoSetProxyBlanket(
          pProxy,
          0xFFFFFFFF,
          0xFFFFFFFF,
          (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
          0,
          3u,
          (RPC_AUTH_IDENTITY_HANDLE)0xFFFFFFFFFFFFFFFFLL,
          0x800u);
  v16 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x474,
      (unsigned int)"onecore\\base\\appcompat\\programs\\devicecensus\\dlls\\utils.cpp",
      (const char *)(unsigned int)v20,
      ppv);
    std::wstring::~wstring((char **)v113);
    std::wstring::~wstring((char **)v115);
    v21 = v107;
    if ( v107 )
    {
      v107 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v21 + 16LL))(v21);
    }
    return v16;
  }
  Release = pProxy->lpVtbl[6].Release;
  if ( *((_QWORD *)a1 + 3) > 7u )
    a1 = *(unsigned __int16 **)a1;
  v23 = _bstr_t::_bstr_t((_bstr_t *)v108, a1);
  if ( *(_QWORD *)v23 )
    v24 = **(_QWORD **)v23;
  else
    v24 = 0;
  v25 = (const unsigned __int16 *)v115;
  if ( *((_QWORD *)&v116 + 1) > 7u )
    v25 = v115[0];
  v26 = _bstr_t::_bstr_t((_bstr_t *)v110, v25);
  if ( *(_QWORD *)v26 )
    v27 = **(_QWORD **)v26;
  else
    v27 = 0;
  v16 = ((__int64 (__fastcall *)(IUnknown *, __int64, __int64, __int64))Release)(pProxy, v27, v24, 48);
  _bstr_t::~_bstr_t((_bstr_t *)v110);
  _bstr_t::~_bstr_t((_bstr_t *)v108);
  if ( (v16 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47A,
      (unsigned int)"onecore\\base\\appcompat\\programs\\devicecensus\\dlls\\utils.cpp",
      (const char *)v16,
      0);
    std::wstring::~wstring((char **)v113);
    std::wstring::~wstring((char **)v115);
    v28 = v107;
    if ( v107 )
    {
      v107 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v28 + 16LL))(v28);
    }
    return v16;
  }
  v29 = CoSetProxyBlanket(
          v105,
          0xFFFFFFFF,
          0xFFFFFFFF,
          (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
          0,
          3u,
          (RPC_AUTH_IDENTITY_HANDLE)0xFFFFFFFFFFFFFFFFLL,
          0x800u);
  v16 = v29;
  if ( v29 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x483,
      (unsigned int)"onecore\\base\\appcompat\\programs\\devicecensus\\dlls\\utils.cpp",
      (const char *)(unsigned int)v29,
      ppva);
    std::wstring::~wstring((char **)v113);
    std::wstring::~wstring((char **)v115);
    v30 = v107;
    if ( v107 )
    {
      v107 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v30 + 16LL))(v30);
    }
    return v16;
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Census_WMI_TPM>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Census_WMI_TPM>::GetImpl'::`2'::impl);
  AddRef = v105->lpVtbl[1].AddRef;
  if ( IsEnabled )
  {
    v33 = ((__int64 (__fastcall *)(IUnknown *, __int64, __int64, __int64 *))AddRef)(v105, 5000, 1, &v103);
    v16 = v33;
    if ( v33 < 0 )
    {
      v17 = -2147217389;
      if ( v33 == -2147217389 )
      {
        std::wstring::~wstring((char **)v113);
        std::wstring::~wstring((char **)v115);
        v34 = *(_QWORD *)v106;
        if ( *(_QWORD *)v106 )
        {
          *(_QWORD *)v106 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
        }
        v35 = v103;
        if ( v103 )
        {
          v103 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
        }
        v36 = v105;
        if ( v105 )
        {
          v105 = 0;
          ((void (__fastcall *)(IUnknown *))v36->lpVtbl->Release)(v36);
        }
        v37 = pProxy;
        if ( pProxy )
        {
          pProxy = 0;
          ((void (__fastcall *)(IUnknown *))v37->lpVtbl->Release)(v37);
        }
        v38 = v107;
        if ( v107 )
        {
          v107 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v38 + 16LL))(v38);
        }
        return v17;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x48D,
        (unsigned int)"onecore\\base\\appcompat\\programs\\devicecensus\\dlls\\utils.cpp",
        (const char *)(unsigned int)v33,
        (int)&v109);
      std::wstring::~wstring((char **)v113);
      std::wstring::~wstring((char **)v115);
      v39 = *(_QWORD *)v106;
      if ( *(_QWORD *)v106 )
      {
        *(_QWORD *)v106 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
      }
      v40 = v103;
      if ( v103 )
      {
        v103 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
      }
      v41 = v105;
      if ( v105 )
      {
        v105 = 0;
        ((void (__fastcall *)(IUnknown *))v41->lpVtbl->Release)(v41);
      }
      v42 = pProxy;
      if ( pProxy )
      {
        pProxy = 0;
        ((void (__fastcall *)(IUnknown *))v42->lpVtbl->Release)(v42);
      }
      v43 = v107;
      if ( v107 )
      {
        v107 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v43 + 16LL))(v43);
      }
      return v16;
    }
  }
  else
  {
    v44 = ((__int64 (__fastcall *)(IUnknown *, __int64, __int64, __int64 *))AddRef)(v105, 5000, 1, &v103);
    v16 = v44;
    if ( v44 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x494,
        (unsigned int)"onecore\\base\\appcompat\\programs\\devicecensus\\dlls\\utils.cpp",
        (const char *)(unsigned int)v44,
        (int)&v109);
      std::wstring::~wstring((char **)v113);
      std::wstring::~wstring((char **)v115);
      v45 = *(_QWORD *)v106;
      if ( *(_QWORD *)v106 )
      {
        *(_QWORD *)v106 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
      }
      v46 = v103;
      if ( v103 )
      {
        v103 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
      }
      v47 = v105;
      if ( v105 )
      {
        v105 = 0;
        ((void (__fastcall *)(IUnknown *))v47->lpVtbl->Release)(v47);
      }
      v48 = pProxy;
      if ( pProxy )
      {
        pProxy = 0;
        ((void (__fastcall *)(IUnknown *))v48->lpVtbl->Release)(v48);
      }
      v49 = v107;
      if ( v107 )
      {
        v107 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v49 + 16LL))(v49);
      }
      return v16;
    }
  }
  if ( !v109 || !v103 )
    goto LABEL_166;
  v50 = pProxy;
  QueryInterface = pProxy->lpVtbl[2].QueryInterface;
  v52 = *(_QWORD *)v106;
  if ( *(_QWORD *)v106 )
  {
    *(_QWORD *)v106 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
  }
  if ( *((_QWORD *)a3 + 3) > 7u )
    a3 = *(unsigned __int16 **)a3;
  v53 = _bstr_t::_bstr_t((_bstr_t *)v108, a3);
  if ( *(_QWORD *)v53 )
    v54 = **(_QWORD **)v53;
  else
    v54 = 0;
  v16 = ((__int64 (__fastcall *)(IUnknown *, __int64, _QWORD, _QWORD))QueryInterface)(v50, v54, 0, 0);
  _bstr_t::~_bstr_t((_bstr_t *)v108);
  if ( (v16 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4A0,
      (unsigned int)"onecore\\base\\appcompat\\programs\\devicecensus\\dlls\\utils.cpp",
      (const char *)v16,
      (int)v106);
    std::wstring::~wstring((char **)v113);
    std::wstring::~wstring((char **)v115);
    v55 = *(_QWORD *)v106;
    if ( *(_QWORD *)v106 )
    {
      *(_QWORD *)v106 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
    }
    v56 = v103;
    if ( v103 )
    {
      v103 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
    }
    v57 = v105;
    if ( v105 )
    {
      v105 = 0;
      ((void (__fastcall *)(IUnknown *))v57->lpVtbl->Release)(v57);
    }
    v58 = pProxy;
    if ( pProxy )
    {
      pProxy = 0;
      ((void (__fastcall *)(IUnknown *))v58->lpVtbl->Release)(v58);
    }
    v59 = v107;
    if ( v107 )
    {
      v107 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v59 + 16LL))(v59);
    }
    return v16;
  }
  v60 = *(_QWORD *)v106;
  if ( *(_QWORD *)v106 )
  {
    v61 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(**(_QWORD **)v106 + 152LL);
    v62 = *a5;
    if ( *a5 )
    {
      *a5 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
    }
    if ( *((_QWORD *)a4 + 3) <= 7u )
      v63 = a4;
    else
      v63 = *(const unsigned __int16 **)a4;
    v64 = _bstr_t::_bstr_t((_bstr_t *)v108, v63);
    if ( *(_QWORD *)v64 )
      v65 = **(_QWORD **)v64;
    else
      v65 = 0;
    v16 = v61(v60, v65, 0, 0);
    _bstr_t::~_bstr_t((_bstr_t *)v108);
    if ( (v16 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4AA,
        (unsigned int)"onecore\\base\\appcompat\\programs\\devicecensus\\dlls\\utils.cpp",
        (const char *)v16,
        (int)a5);
      std::wstring::~wstring((char **)v113);
      std::wstring::~wstring((char **)v115);
      v66 = *(_QWORD *)v106;
      if ( *(_QWORD *)v106 )
      {
        *(_QWORD *)v106 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
      }
      v67 = v103;
      if ( v103 )
      {
        v103 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
      }
      v68 = v105;
      if ( v105 )
      {
        v105 = 0;
        ((void (__fastcall *)(IUnknown *))v68->lpVtbl->Release)(v68);
      }
      v69 = pProxy;
      if ( pProxy )
      {
        pProxy = 0;
        ((void (__fastcall *)(IUnknown *))v69->lpVtbl->Release)(v69);
      }
      v70 = v107;
      if ( v107 )
      {
        v107 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v70 + 16LL))(v70);
      }
      return v16;
    }
    v71 = v103;
    v72 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int128 *))(*(_QWORD *)v103 + 32LL);
    v73 = (const unsigned __int16 *)v113;
    if ( *((_QWORD *)&v114 + 1) > 7u )
      v73 = v113[0];
    v74 = _bstr_t::_bstr_t((_bstr_t *)v108, v73);
    if ( *(_QWORD *)v74 )
      v75 = **(_QWORD **)v74;
    else
      v75 = 0;
    v16 = v72(v71, v75, 0, &v111);
    _bstr_t::~_bstr_t((_bstr_t *)v108);
    if ( (v16 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4B0,
        (unsigned int)"onecore\\base\\appcompat\\programs\\devicecensus\\dlls\\utils.cpp",
        (const char *)v16,
        0);
      std::wstring::~wstring((char **)v113);
      std::wstring::~wstring((char **)v115);
      v76 = *(_QWORD *)v106;
      if ( *(_QWORD *)v106 )
      {
        *(_QWORD *)v106 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
      }
      v77 = v103;
      if ( v103 )
      {
        v103 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
      }
      v78 = v105;
      if ( v105 )
      {
        v105 = 0;
        ((void (__fastcall *)(IUnknown *))v78->lpVtbl->Release)(v78);
      }
      v79 = pProxy;
      if ( pProxy )
      {
        pProxy = 0;
        ((void (__fastcall *)(IUnknown *))v79->lpVtbl->Release)(v79);
      }
      v80 = v107;
      if ( v107 )
      {
        v107 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v80 + 16LL))(v80);
      }
      return v16;
    }
    v81 = pProxy;
    v82 = pProxy->lpVtbl[8].QueryInterface;
    v83 = *a5;
    if ( *a5 )
    {
      *a5 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
    }
    if ( *((_QWORD *)a4 + 3) > 7u )
      a4 = *(unsigned __int16 **)a4;
    v84 = _bstr_t::_bstr_t((_bstr_t *)v108, a4);
    if ( *(_QWORD *)v84 )
      v85 = **(_QWORD **)v84;
    else
      v85 = 0;
    v16 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, __int64, _QWORD))v82)(v81, *((_QWORD *)&v111 + 1), v85, 0);
    _bstr_t::~_bstr_t((_bstr_t *)v108);
    if ( (v16 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4BB,
        (unsigned int)"onecore\\base\\appcompat\\programs\\devicecensus\\dlls\\utils.cpp",
        (const char *)v16,
        0);
      std::wstring::~wstring((char **)v113);
      std::wstring::~wstring((char **)v115);
      v86 = *(_QWORD *)v106;
      if ( *(_QWORD *)v106 )
      {
        *(_QWORD *)v106 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 16LL))(v86);
      }
      v87 = v103;
      if ( v103 )
      {
        v103 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v87 + 16LL))(v87);
      }
      v88 = v105;
      if ( v105 )
      {
        v105 = 0;
        ((void (__fastcall *)(IUnknown *))v88->lpVtbl->Release)(v88);
      }
      v89 = pProxy;
      if ( pProxy )
      {
        pProxy = 0;
        ((void (__fastcall *)(IUnknown *))v89->lpVtbl->Release)(v89);
      }
      v90 = v107;
      if ( v107 )
      {
        v107 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v90 + 16LL))(v90);
      }
      return v16;
    }
    std::wstring::~wstring((char **)v113);
    std::wstring::~wstring((char **)v115);
    v91 = *(_QWORD *)v106;
    if ( *(_QWORD *)v106 )
    {
      *(_QWORD *)v106 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
    }
    v92 = v103;
    if ( v103 )
    {
      v103 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
    }
    v93 = v105;
    if ( v105 )
    {
      v105 = 0;
      ((void (__fastcall *)(IUnknown *))v93->lpVtbl->Release)(v93);
    }
    v94 = pProxy;
    if ( pProxy )
    {
      pProxy = 0;
      ((void (__fastcall *)(IUnknown *))v94->lpVtbl->Release)(v94);
    }
    v95 = v107;
    if ( v107 )
    {
      v107 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v95 + 16LL))(v95);
    }
    return 0;
  }
  else
  {
LABEL_166:
    std::wstring::~wstring((char **)v113);
    std::wstring::~wstring((char **)v115);
    v96 = *(_QWORD *)v106;
    if ( *(_QWORD *)v106 )
    {
      *(_QWORD *)v106 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
    }
    v97 = v103;
    if ( v103 )
    {
      v103 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
    }
    v98 = v105;
    if ( v105 )
    {
      v105 = 0;
      ((void (__fastcall *)(IUnknown *))v98->lpVtbl->Release)(v98);
    }
    v99 = pProxy;
    if ( pProxy )
    {
      pProxy = 0;
      ((void (__fastcall *)(IUnknown *))v99->lpVtbl->Release)(v99);
    }
    v100 = v107;
    if ( v107 )
    {
      v107 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v100 + 16LL))(v100);
    }
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x1800d10e8  push    rbp
0x1800d10ea  push    rbx
0x1800d10eb  push    rsi
0x1800d10ec  push    rdi
0x1800d10ed  push    r12
0x1800d10ef  push    r13
0x1800d10f1  push    r14
0x1800d10f3  push    r15
0x1800d10f5  lea     rbp, [rsp-17h]
0x1800d10fa  sub     rsp, 0F8h
0x1800d1101  mov     rax, cs:__security_cookie
0x1800d1108  xor     rax, rsp
0x1800d110b  mov     [rbp+4Fh+var_48], rax
0x1800d110f  mov     rdi, r9
0x1800d1112  mov     r12, r8
0x1800d1115  mov     rbx, rdx
0x1800d1118  mov     r14, rcx
0x1800d111b  mov     r15, qword ptr [rbp+4Fh+arg_20]
0x1800d111f  xor     r13d, r13d
0x1800d1122  mov     [rbp+4Fh+var_C0], r13
0x1800d1126  mov     [rsp+130h+pProxy], r13
0x1800d112b  mov     [rsp+130h+var_D0], r13
0x1800d1130  mov     [rsp+130h+var_E0], r13
0x1800d1135  mov     qword ptr [rbp+4Fh+var_C8], r13
0x1800d1139  xorps   xmm0, xmm0
0x1800d113c  movups  xmmword ptr [rbp+4Fh+var_68], xmm0
0x1800d1140  xorps   xmm1, xmm1
0x1800d1143  movdqu  [rbp+4Fh+var_58], xmm1
0x1800d1148  lea     r8d, [r13+3]
0x1800d114c  lea     rdx, aWql; "WQL"
0x1800d1153  lea     rcx, [rbp+4Fh+var_68]
0x1800d1157  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800d115c  nop
0x1800d115d  xorps   xmm0, xmm0
0x1800d1160  movups  xmmword ptr [rbp+4Fh+var_88], xmm0
0x1800d1164  xorps   xmm1, xmm1
0x1800d1167  movdqu  [rbp+4Fh+var_78], xmm1
0x1800d116c  lea     r8d, [r13+6]
0x1800d1170  lea     rdx, aPath; "__Path"
0x1800d1177  lea     rcx, [rbp+4Fh+var_88]
0x1800d117b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800d1180  nop
0x1800d1181  mov     [rbp+4Fh+var_B0], r13d
0x1800d1185  xorps   xmm0, xmm0
0x1800d1188  xor     eax, eax
0x1800d118a  movups  [rbp+4Fh+var_A0], xmm0
0x1800d118e  mov     [rbp+4Fh+var_90], rax
0x1800d1192  mov     rcx, [rbp+4Fh+var_C0]
0x1800d1196  test    rcx, rcx
0x1800d1199  jz      short loc_1800D11AC
0x1800d119b  mov     [rbp+4Fh+var_C0], r13
0x1800d119f  mov     rax, [rcx]
0x1800d11a2  mov     rax, [rax+10h]
0x1800d11a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d11ab  nop
0x1800d11ac  lea     rax, [rbp+4Fh+var_C0]
0x1800d11b0  mov     [rsp+130h+ppv], rax; ppv
0x1800d11b5  lea     r9, _GUID_dc12a687_737f_11cf_884d_00aa004b2e24; riid
0x1800d11bc  xor     edx, edx; pUnkOuter
0x1800d11be  lea     r8d, [rdx+1]; dwClsContext
0x1800d11c2  lea     rcx, CLSID_WbemLocator; rclsid
0x1800d11c9  call    cs:__imp_CoCreateInstance
0x1800d11cf  mov     esi, eax
0x1800d11d1  test    eax, eax
0x1800d11d3  jns     loc_1800D127C
0x1800d11d9  lea     rcx, [rbp+4Fh+var_88]
0x1800d11dd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d11e2  nop
0x1800d11e3  lea     rcx, [rbp+4Fh+var_68]
0x1800d11e7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d11ec  nop
0x1800d11ed  mov     rcx, qword ptr [rbp+4Fh+var_C8]
0x1800d11f1  test    rcx, rcx
0x1800d11f4  jz      short loc_1800D1207
0x1800d11f6  mov     qword ptr [rbp+4Fh+var_C8], r13
0x1800d11fa  mov     rax, [rcx]
0x1800d11fd  mov     rax, [rax+10h]
0x1800d1201  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1206  nop
0x1800d1207  mov     rcx, [rsp+130h+var_E0]
0x1800d120c  test    rcx, rcx
0x1800d120f  jz      short loc_1800D1223
0x1800d1211  mov     [rsp+130h+var_E0], r13
0x1800d1216  mov     rax, [rcx]
0x1800d1219  mov     rax, [rax+10h]
0x1800d121d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1222  nop
0x1800d1223  mov     rcx, [rsp+130h+var_D0]
0x1800d1228  test    rcx, rcx
0x1800d122b  jz      short loc_1800D123F
0x1800d122d  mov     [rsp+130h+var_D0], r13
0x1800d1232  mov     rax, [rcx]
0x1800d1235  mov     rax, [rax+10h]
0x1800d1239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d123e  nop
0x1800d123f  mov     rcx, [rsp+130h+pProxy]
0x1800d1244  test    rcx, rcx
0x1800d1247  jz      short loc_1800D125B
0x1800d1249  mov     [rsp+130h+pProxy], r13
0x1800d124e  mov     rax, [rcx]
0x1800d1251  mov     rax, [rax+10h]
0x1800d1255  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d125a  nop
0x1800d125b  mov     rcx, [rbp+4Fh+var_C0]
0x1800d125f  test    rcx, rcx
0x1800d1262  jz      short loc_1800D1275
0x1800d1264  mov     [rbp+4Fh+var_C0], r13
0x1800d1268  mov     rax, [rcx]
0x1800d126b  mov     rax, [rax+10h]
0x1800d126f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1274  nop
0x1800d1275  mov     eax, esi
0x1800d1277  jmp     loc_1800D20E6
0x1800d127c  mov     rsi, [rbp+4Fh+var_C0]
0x1800d1280  mov     rax, [rsi]
0x1800d1283  mov     r13, [rax+18h]
0x1800d1287  mov     rcx, [rsp+130h+pProxy]
0x1800d128c  test    rcx, rcx
0x1800d128f  jz      short loc_1800D12A7
0x1800d1291  mov     [rsp+130h+pProxy], 0
0x1800d129a  mov     rax, [rcx]
0x1800d129d  mov     rax, [rax+10h]
0x1800d12a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d12a6  nop
0x1800d12a7  cmp     qword ptr [rbx+18h], 7
0x1800d12ac  jbe     short loc_1800D12B1
0x1800d12ae  mov     rbx, [rbx]
0x1800d12b1  mov     rdx, rbx; unsigned __int16 *
0x1800d12b4  lea     rcx, [rbp+4Fh+var_A8]; this
0x1800d12b8  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800d12bd  nop
0x1800d12be  mov     rcx, [rax]
0x1800d12c1  xor     r8d, r8d
0x1800d12c4  test    rcx, rcx
0x1800d12c7  jz      short loc_1800D12CE
0x1800d12c9  mov     rdx, [rcx]
0x1800d12cc  jmp     short loc_1800D12D1
0x1800d12ce  mov     rdx, r8
0x1800d12d1  lea     rax, [rsp+130h+pProxy]
0x1800d12d6  mov     [rsp+130h+var_F0], rax
0x1800d12db  mov     qword ptr [rsp+130h+dwCapabilities], r8
0x1800d12e0  mov     [rsp+130h+pAuthInfo], r8
0x1800d12e5  mov     [rsp+130h+dwImpLevel], r8d
0x1800d12ea  mov     [rsp+130h+ppv], r8; int
0x1800d12ef  xor     r9d, r9d
0x1800d12f2  mov     rcx, rsi
0x1800d12f5  mov     rax, r13
0x1800d12f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d12fd  mov     ebx, eax
0x1800d12ff  lea     rcx, [rbp+4Fh+var_A8]; this
0x1800d1303  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800d1308  xor     esi, esi
0x1800d130a  test    ebx, ebx
0x1800d130c  jns     loc_1800D147E
0x1800d1312  mov     edi, 8004100Eh
0x1800d1317  cmp     ebx, edi
0x1800d1319  jnz     loc_1800D13C2
0x1800d131f  lea     rcx, [rbp+4Fh+var_88]
0x1800d1323  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d1328  nop
0x1800d1329  lea     rcx, [rbp+4Fh+var_68]
0x1800d132d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d1332  nop
0x1800d1333  mov     rcx, qword ptr [rbp+4Fh+var_C8]
0x1800d1337  test    rcx, rcx
0x1800d133a  jz      short loc_1800D134D
0x1800d133c  mov     qword ptr [rbp+4Fh+var_C8], rsi
0x1800d1340  mov     rax, [rcx]
0x1800d1343  mov     rax, [rax+10h]
0x1800d1347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d134c  nop
0x1800d134d  mov     rcx, [rsp+130h+var_E0]
0x1800d1352  test    rcx, rcx
0x1800d1355  jz      short loc_1800D1369
0x1800d1357  mov     [rsp+130h+var_E0], rsi
0x1800d135c  mov     rax, [rcx]
0x1800d135f  mov     rax, [rax+10h]
0x1800d1363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1368  nop
0x1800d1369  mov     rcx, [rsp+130h+var_D0]
0x1800d136e  test    rcx, rcx
0x1800d1371  jz      short loc_1800D1385
0x1800d1373  mov     [rsp+130h+var_D0], rsi
0x1800d1378  mov     rax, [rcx]
0x1800d137b  mov     rax, [rax+10h]
0x1800d137f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1384  nop
0x1800d1385  mov     rcx, [rsp+130h+pProxy]
0x1800d138a  test    rcx, rcx
0x1800d138d  jz      short loc_1800D13A1
0x1800d138f  mov     [rsp+130h+pProxy], rsi
0x1800d1394  mov     rax, [rcx]
0x1800d1397  mov     rax, [rax+10h]
0x1800d139b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d13a0  nop
0x1800d13a1  mov     rcx, [rbp+4Fh+var_C0]
0x1800d13a5  test    rcx, rcx
0x1800d13a8  jz      short loc_1800D13BB
0x1800d13aa  mov     [rbp+4Fh+var_C0], rsi
0x1800d13ae  mov     rdx, [rcx]
0x1800d13b1  mov     rax, [rdx+10h]
0x1800d13b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d13ba  nop
0x1800d13bb  mov     eax, edi
0x1800d13bd  jmp     loc_1800D20E6
0x1800d13c2  mov     rcx, [rbp+57h]; this
0x1800d13c6  mov     r9d, ebx; char *
0x1800d13c9  lea     r8, aOnecoreBaseApp_9; "onecore\\base\\appcompat\\programs\\dev"...
0x1800d13d0  mov     edx, 46Ah; void *
0x1800d13d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d13da  nop
0x1800d13db  lea     rcx, [rbp+4Fh+var_88]
0x1800d13df  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d13e4  nop
0x1800d13e5  lea     rcx, [rbp+4Fh+var_68]
0x1800d13e9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d13ee  nop
0x1800d13ef  mov     rcx, qword ptr [rbp+4Fh+var_C8]
0x1800d13f3  test    rcx, rcx
0x1800d13f6  jz      short loc_1800D1409
0x1800d13f8  mov     qword ptr [rbp+4Fh+var_C8], rsi
0x1800d13fc  mov     rax, [rcx]
0x1800d13ff  mov     rax, [rax+10h]
0x1800d1403  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1408  nop
0x1800d1409  mov     rcx, [rsp+130h+var_E0]
0x1800d140e  test    rcx, rcx
0x1800d1411  jz      short loc_1800D1425
0x1800d1413  mov     [rsp+130h+var_E0], rsi
0x1800d1418  mov     rax, [rcx]
0x1800d141b  mov     rax, [rax+10h]
0x1800d141f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1424  nop
0x1800d1425  mov     rcx, [rsp+130h+var_D0]
0x1800d142a  test    rcx, rcx
0x1800d142d  jz      short loc_1800D1441
0x1800d142f  mov     [rsp+130h+var_D0], rsi
0x1800d1434  mov     rax, [rcx]
0x1800d1437  mov     rax, [rax+10h]
0x1800d143b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1440  nop
0x1800d1441  mov     rcx, [rsp+130h+pProxy]
0x1800d1446  test    rcx, rcx
0x1800d1449  jz      short loc_1800D145D
0x1800d144b  mov     [rsp+130h+pProxy], rsi
0x1800d1450  mov     rax, [rcx]
0x1800d1453  mov     rax, [rax+10h]
0x1800d1457  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d145c  nop
0x1800d145d  mov     rcx, [rbp+4Fh+var_C0]
0x1800d1461  test    rcx, rcx
0x1800d1464  jz      short loc_1800D1477
0x1800d1466  mov     [rbp+4Fh+var_C0], rsi
0x1800d146a  mov     rax, [rcx]
0x1800d146d  mov     rax, [rax+10h]
0x1800d1471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1476  nop
0x1800d1477  mov     eax, ebx
0x1800d1479  jmp     loc_1800D20E6
0x1800d147e  mov     [rsp+130h+dwCapabilities], 800h; dwCapabilities
0x1800d1486  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800d148a  mov     [rsp+130h+pAuthInfo], rax; pAuthInfo
0x1800d148f  mov     [rsp+130h+dwImpLevel], 3; dwImpLevel
0x1800d1497  mov     dword ptr [rsp+130h+ppv], esi; int
0x1800d149b  mov     r9, rax; pServerPrincName
0x1800d149e  or      eax, 0FFFFFFFFh
0x1800d14a1  mov     r8d, eax; dwAuthzSvc
0x1800d14a4  mov     edx, eax; dwAuthnSvc
0x1800d14a6  mov     rcx, [rsp+130h+pProxy]; pProxy
0x1800d14ab  call    cs:__imp_CoSetProxyBlanket
0x1800d14b1  mov     ebx, eax
0x1800d14b3  test    eax, eax
0x1800d14b5  jns     loc_1800D1575
0x1800d14bb  mov     rcx, [rbp+57h]; this
0x1800d14bf  mov     r9d, eax; char *
0x1800d14c2  lea     r8, aOnecoreBaseApp_9; "onecore\\base\\appcompat\\programs\\dev"...
0x1800d14c9  mov     edx, 474h; void *
0x1800d14ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d14d3  nop
0x1800d14d4  lea     rcx, [rbp+4Fh+var_88]
0x1800d14d8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d14dd  nop
0x1800d14de  lea     rcx, [rbp+4Fh+var_68]
0x1800d14e2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d14e7  nop
0x1800d14e8  mov     rcx, qword ptr [rbp+4Fh+var_C8]
0x1800d14ec  test    rcx, rcx
0x1800d14ef  jz      short loc_1800D1502
0x1800d14f1  mov     qword ptr [rbp+4Fh+var_C8], rsi
0x1800d14f5  mov     rax, [rcx]
0x1800d14f8  mov     rax, [rax+10h]
0x1800d14fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1501  nop
0x1800d1502  mov     rcx, [rsp+130h+var_E0]
0x1800d1507  test    rcx, rcx
0x1800d150a  jz      short loc_1800D151E
0x1800d150c  mov     [rsp+130h+var_E0], rsi
0x1800d1511  mov     rax, [rcx]
0x1800d1514  mov     rax, [rax+10h]
0x1800d1518  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
