# CWapDPU::ProcessData(uchar *,ulong,uchar * *,ulong *)

- ea: `0x180029240`
- end: `0x18002aa97`
- name: `?ProcessData@CWapDPU@@UEAAJPEAEKPEAPEAEPEAK@Z`
- size: `6231`
- prototype: `__int64 __fastcall(CWapDPU *this, unsigned __int16 *, unsigned int, unsigned __int8 **)`
- caller_count: `0`
- callee_count: `41`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001280`
- `0x180001950`
- `0x180001a44`
- `0x180002550`
- `0x180003420`
- `0x1800034d0`
- `0x1800110bc`
- `0x18001165c`
- `0x1800116a0`
- `0x1800118a0`
- `0x180011d6c`
- `0x180011d9c`
- `0x18001286c`
- `0x180013890`
- `0x180013930`
- `0x180013a10`
- `0x180013c04`
- `0x180013c88`
- `0x180014330`
- `0x180014c60`
- `0x18001770c`
- `0x18001e1a8`
- `0x180022874`
- `0x180023b0c`
- `0x180023ed4`
- `0x180024028`
- `0x180024308`
- `0x180028620`
- `0x1800287c0`
- `0x180028914`
- `0x180028fdc`
- `0x180029240`
- `0x18002aadc`
- `0x18002abf0`
- `0x18002b260`
- `0x18002b2f8`
- `0x18002bd20`
- `0x18002c710`
- `0x18002d7b4`
- `0x18002d810`
- `0x180030010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x18002948b`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x1800294ac`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x18002948b`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x1800294ac`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800293c3`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002a8f7`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800293c3`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002a8f7`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a5ea`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a63a`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a5ea`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a63a`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a058`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a174`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a1e3`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a26b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a5c4`
- `OLEAUT32!__imp_SysFreeString` at `0x18002aa28`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a058`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a174`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a1e3`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a26b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a5c4`
- `OLEAUT32!__imp_SysFreeString` at `0x18002aa28`
- `OLEAUT32!__imp_VariantInit` at `0x1800293d7`
- `OLEAUT32!__imp_VariantInit` at `0x1800293d7`
- `OLEAUT32!__imp_VariantClear` at `0x18002a61f`
- `OLEAUT32!__imp_VariantClear` at `0x18002a9e3`
- `OLEAUT32!__imp_VariantClear` at `0x18002a61f`
- `OLEAUT32!__imp_VariantClear` at `0x18002a9e3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800292b5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800292b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a21f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002aa64`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a21f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002aa64`
- `dmEnrollEngine!GetEnrollmentType` at `0x1800297c7`
- `dmEnrollEngine!GetEnrollmentType` at `0x1800297c7`
- `XmlLite!CreateXmlReader` at `0x18002941c`
- `XmlLite!CreateXmlReader` at `0x18002941c`
- `XmlLite!CreateXmlReaderInputWithEncodingName` at `0x18002957f`
- `XmlLite!CreateXmlReaderInputWithEncodingName` at `0x18002957f`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1800294db`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1800294db`
- `RPCRT4!UuidFromStringW` at `0x180029796`
- `RPCRT4!UuidFromStringW` at `0x180029796`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWapDPU::ProcessData(CWapDPU *this, unsigned __int16 *a2, unsigned int a3, unsigned __int8 **a4)
{
  unsigned __int64 v4; // r12
  CWapDPU *v6; // r13
  CWapDPU *v7; // rbx
  struct _RTL_CRITICAL_SECTION *v8; // rdi
  OLECHAR *v9; // rsi
  _QWORD *v10; // rax
  _QWORD *v11; // rax
  int v12; // r8d
  int v13; // r9d
  HRESULT v14; // r14d
  unsigned __int64 v15; // rdx
  const BYTE *v16; // r10
  const BYTE *v17; // r12
  int v18; // eax
  unsigned __int64 v19; // rdx
  BSTR v20; // rbx
  IUnknown *v21; // rax
  __int64 v22; // rcx
  _QWORD *v23; // rbx
  _QWORD *v24; // rdx
  int v25; // r12d
  _QWORD *v26; // rax
  char v27; // bl
  __int64 *v28; // rax
  __int64 v29; // r14
  __int64 v30; // rbx
  int v31; // eax
  int v32; // r14d
  unsigned __int16 *v33; // rcx
  int v34; // ebx
  int v35; // eax
  _QWORD *v36; // r12
  int v37; // eax
  _QWORD *v38; // rax
  bool v39; // bl
  int v40; // eax
  _QWORD *v41; // rdx
  __int64 v42; // rbx
  __int64 v43; // r12
  UUID *p_Src; // r8
  _QWORD *v45; // rdx
  int v46; // ecx
  int v47; // r8d
  int v48; // r9d
  struct IMCSFDatastore *v49; // rbx
  int v50; // eax
  unsigned int v51; // ebx
  _QWORD *v53; // r14
  struct IUnknown *v54; // rdx
  _QWORD *v55; // rax
  bool v56; // bl
  int v57; // eax
  CWapDPU *v58; // rax
  _QWORD *v59; // rbx
  __int64 v60; // rcx
  __int64 (__fastcall *v61)(__int64, _QWORD *, _QWORD *); // r9
  _QWORD *v62; // r8
  _QWORD *v63; // rdx
  const OLECHAR *v64; // rcx
  BSTR v65; // rax
  const OLECHAR *v66; // rcx
  __int64 v67; // rcx
  __int64 (__fastcall *v68)(_QWORD, _QWORD, _QWORD, _QWORD); // rax
  _QWORD *v69; // rbx
  _QWORD *v70; // rdx
  __int64 v71; // rax
  __int16 *v72; // rdx
  __int64 v73; // rcx
  __int16 v74; // ax
  __int64 v75; // rcx
  int v76; // r8d
  int v77; // r9d
  wil *v78; // rcx
  int v79; // ecx
  int v80; // r8d
  int v81; // r9d
  int v82; // r8d
  int v83; // r9d
  wil *v84; // rcx
  int v85; // ecx
  int v86; // r8d
  int v87; // r9d
  int v88; // r8d
  int v89; // r9d
  int pwszBaseUri; // [rsp+20h] [rbp-568h]
  int v92; // [rsp+48h] [rbp-540h] BYREF
  int v93; // [rsp+4Ch] [rbp-53Ch]
  struct IUnknown *v94; // [rsp+50h] [rbp-538h] BYREF
  int v95; // [rsp+58h] [rbp-530h] BYREF
  BSTR v96; // [rsp+60h] [rbp-528h] BYREF
  unsigned int v97; // [rsp+68h] [rbp-520h] BYREF
  int v98; // [rsp+6Ch] [rbp-51Ch]
  void *ppvObject; // [rsp+70h] [rbp-518h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp-510h] BYREF
  int v101; // [rsp+80h] [rbp-508h] BYREF
  int v102; // [rsp+84h] [rbp-504h]
  unsigned int v103; // [rsp+88h] [rbp-500h]
  BSTR v104; // [rsp+90h] [rbp-4F8h] BYREF
  UINT cbInit[2]; // [rsp+98h] [rbp-4F0h] BYREF
  int v106; // [rsp+A0h] [rbp-4E8h] BYREF
  int v107; // [rsp+A4h] [rbp-4E4h] BYREF
  unsigned int v108; // [rsp+A8h] [rbp-4E0h]
  int v109; // [rsp+ACh] [rbp-4DCh] BYREF
  int v110; // [rsp+B0h] [rbp-4D8h]
  unsigned int v111; // [rsp+B4h] [rbp-4D4h] BYREF
  struct IMCSFDatastore *v112; // [rsp+B8h] [rbp-4D0h] BYREF
  __int128 v113; // [rsp+C0h] [rbp-4C8h] BYREF
  unsigned __int16 *v114; // [rsp+D0h] [rbp-4B8h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+D8h] [rbp-4B0h]
  unsigned __int16 *v116; // [rsp+E0h] [rbp-4A8h]
  IXmlReaderInput *ppInput; // [rsp+E8h] [rbp-4A0h] BYREF
  const char *v118; // [rsp+F0h] [rbp-498h] BYREF
  __int64 v119; // [rsp+F8h] [rbp-490h] BYREF
  IUnknown *v120; // [rsp+100h] [rbp-488h] BYREF
  __int64 v121; // [rsp+108h] [rbp-480h] BYREF
  CWapDPU *v122; // [rsp+110h] [rbp-478h]
  char v123[8]; // [rsp+118h] [rbp-470h] BYREF
  char v124[8]; // [rsp+120h] [rbp-468h] BYREF
  char v125[8]; // [rsp+128h] [rbp-460h] BYREF
  char v126[8]; // [rsp+130h] [rbp-458h] BYREF
  char v127[8]; // [rsp+138h] [rbp-450h] BYREF
  char v128[8]; // [rsp+140h] [rbp-448h] BYREF
  char v129[8]; // [rsp+148h] [rbp-440h] BYREF
  char v130[8]; // [rsp+150h] [rbp-438h] BYREF
  char v131[8]; // [rsp+158h] [rbp-430h] BYREF
  char v132[8]; // [rsp+160h] [rbp-428h] BYREF
  VARIANTARG pvarg; // [rsp+168h] [rbp-420h] BYREF
  VARIANTARG v134; // [rsp+180h] [rbp-408h] BYREF
  char v135[8]; // [rsp+1A0h] [rbp-3E8h] BYREF
  char v136[8]; // [rsp+1A8h] [rbp-3E0h] BYREF
  const std::exception *v137; // [rsp+1B0h] [rbp-3D8h] BYREF
  const ATL::CAtlException *v138; // [rsp+1B8h] [rbp-3D0h] BYREF
  const std::exception *v139; // [rsp+1C0h] [rbp-3C8h] BYREF
  const ATL::CAtlException *v140; // [rsp+1C8h] [rbp-3C0h] BYREF
  char v141[16]; // [rsp+1D0h] [rbp-3B8h] BYREF
  _BYTE v142[32]; // [rsp+1E0h] [rbp-3A8h] BYREF
  _QWORD v143[4]; // [rsp+200h] [rbp-388h] BYREF
  _QWORD v144[4]; // [rsp+220h] [rbp-368h] BYREF
  UUID Src; // [rsp+240h] [rbp-348h] BYREF
  unsigned __int64 v146; // [rsp+258h] [rbp-330h]
  UUID Uuid; // [rsp+260h] [rbp-328h] BYREF
  _BYTE v148[16]; // [rsp+270h] [rbp-318h] BYREF
  __int64 v149; // [rsp+280h] [rbp-308h]
  _BYTE v150[16]; // [rsp+290h] [rbp-2F8h] BYREF
  __int64 v151; // [rsp+2A0h] [rbp-2E8h]
  _BYTE v152[16]; // [rsp+2B0h] [rbp-2D8h] BYREF
  __int64 v153; // [rsp+2C0h] [rbp-2C8h]
  GUID ActivityId; // [rsp+2D0h] [rbp-2B8h] BYREF
  __int64 v155; // [rsp+2E0h] [rbp-2A8h] BYREF
  __int16 v156; // [rsp+2E8h] [rbp-2A0h]
  __int128 v157; // [rsp+4F0h] [rbp-98h]
  _BYTE v158[32]; // [rsp+500h] [rbp-88h] BYREF
  int *v159; // [rsp+520h] [rbp-68h]
  __int64 v160; // [rsp+528h] [rbp-60h]
  __int64 *v161; // [rsp+530h] [rbp-58h]
  __int64 v162; // [rsp+538h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+588h] [rbp+0h]

  v4 = a3;
  v103 = a3;
  v116 = a2;
  v6 = this;
  v108 = a3;
  v122 = this;
  v7 = this;
  v114 = a2;
  v97 = 0;
  v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 72);
  v121 = (__int64)this + 72;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  lpCriticalSection = v8;
  ppvObject = 0;
  v109 = 0;
  v106 = 0;
  v120 = 0;
  *(_QWORD *)cbInit = 0;
  ppInput = 0;
  bstrString = 0;
  v9 = 0;
  v104 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v94 = 0;
  v157 = 0;
  v10 = operator new(0x48u);
  *v10 = v10;
  v10[1] = v10;
  v10[2] = v10;
  *((_WORD *)v10 + 12) = 257;
  *(_QWORD *)&v157 = v10;
  v156 = 0;
  v155 = 0;
  v101 = 1;
  v110 = 0;
  v112 = 0;
  v107 = 0;
  v113 = 0;
  v11 = operator new(0x28u);
  *v11 = v11;
  v11[1] = v11;
  v11[2] = v11;
  *((_WORD *)v11 + 12) = 257;
  *(_QWORD *)&v113 = v11;
  ActivityId = 0;
  EventActivityIdControl(1u, &ActivityId);
  VariantInit(&pvarg);
  if ( !a2 || (_DWORD)v4 == 1 )
  {
    v14 = -2147024809;
    goto LABEL_19;
  }
  if ( !*((_QWORD *)v7 + 1) || !*((_QWORD *)v6 + 4) )
  {
    v14 = -2147418113;
    goto LABEL_19;
  }
  v14 = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  if ( v14 < 0
    || (v14 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 4), v14 < 0)
    || (!(_DWORD)v4 ? (v15 = 0x7FFFFFFF) : (v15 = v4 >> 1),
        v14 = StringCchLengthW(v116, v15, (unsigned __int64 *)&bstrString),
        v14 < 0) )
  {
LABEL_19:
    v22 = *((_QWORD *)v6 + 4);
    if ( v22 && *((_QWORD *)v6 + 2) )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 112LL))(v22);
    if ( *((_QWORD *)v6 + 2) )
    {
      v23 = (_QWORD *)*((_QWORD *)v7 + 15);
      while ( 1 )
      {
        v23 = (_QWORD *)*v23;
        if ( v23 == *((_QWORD **)this + 15) )
          break;
        v24 = v23 + 2;
        if ( v23[5] > 7u )
          v24 = (_QWORD *)*v24;
        (*(void (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)v6 + 2) + 104LL))(*((_QWORD *)v6 + 2), v24);
      }
      v9 = v104;
    }
    if ( (unsigned int)dword_18003E080 > 2 )
    {
      v74 = v103;
      if ( v103 > 0xFFFF )
        v74 = -1;
      *(_QWORD *)&Uuid.Data1 = v116;
      *(_WORD *)Uuid.Data4 = v74;
      v92 = v14;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperArray<1>>(
        (int)v116,
        (int)&byte_180037A8F,
        v12,
        v13,
        (__int64)&v92,
        (__int64)&Uuid);
    }
    v75 = *((_QWORD *)v6 + 1);
    if ( v75 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 72LL))(v75);
LABEL_178:
    *((_DWORD *)v6 + 10) = v14;
    EventActivityIdControl(2u, &ActivityId);
    if ( (unsigned int)dword_18003E080 > 5 )
    {
      v92 = v14;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (int)&dword_18003E080,
        (int)word_1800379B2,
        v76,
        v77,
        (__int64)&v92);
    }
    if ( v110 && (unsigned int)dword_18003E080 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18003E080, 0x400000000000LL) )
    {
      v121 = 0x2000000;
      v92 = v14;
      v161 = &v121;
      v162 = 8;
      v159 = &v92;
      v160 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_18003E080, &unk_180037918, 0, 0, 4, v158);
    }
    VariantClear(&pvarg);
    std::_Tree<std::_Tset_traits<ATL::CAdapt<ATL::CComPtr<IDomNode>>,std::less<ATL::CAdapt<ATL::CComPtr<IDomNode>>>,std::allocator<ATL::CAdapt<ATL::CComPtr<IDomNode>>>,0>>::~_Tree<std::_Tset_traits<ATL::CAdapt<ATL::CComPtr<IDomNode>>,std::less<ATL::CAdapt<ATL::CComPtr<IDomNode>>>,std::allocator<ATL::CAdapt<ATL::CComPtr<IDomNode>>>,0>>(&v113);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v112);
    CWapNodeValidator::~CWapNodeValidator((CWapNodeValidator *)&v155);
    wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(&v94);
    SysFreeString(v9);
    wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(&ppInput);
    wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(&v120);
    wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(&ppvObject);
    if ( v8 )
      LeaveCriticalSection(v8);
    return (unsigned int)v14;
  }
  v17 = v16;
  v18 = _o_iswspace(*(unsigned __int16 *)v16);
  v20 = bstrString;
  while ( v18 )
  {
    v17 += 2;
    v20 = (BSTR)((char *)v20 - 1);
    v18 = _o_iswspace(*(unsigned __int16 *)v17);
  }
  v14 = ULongLongMult((unsigned __int64)v20, v19, (unsigned __int64 *)cbInit);
  if ( v14 < 0 )
    goto LABEL_18;
  v21 = (IUnknown *)SHCreateMemStream(v17, cbInit[0]);
  v120 = v21;
  if ( !v21 )
  {
LABEL_17:
    v14 = -2147024882;
LABEL_18:
    v7 = this;
    goto LABEL_19;
  }
  v14 = CreateXmlReaderInputWithEncodingName(v21, 0, L"UTF-16", 0, 0, &ppInput);
  if ( v14 < 0 )
    goto LABEL_18;
  v14 = (*(__int64 (__fastcall **)(void *, IXmlReaderInput *))(*(_QWORD *)ppvObject + 24LL))(ppvObject, ppInput);
  if ( v14 < 0 )
    goto LABEL_18;
  v93 = 0;
  v102 = 0;
  std::wstring::wstring(v150, L"OMADM::WapEnrollmentProvisioning");
  v25 = 1;
  v98 = 1;
  v97 = 1;
  if ( *(_QWORD *)std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(
                    (char *)v6 + 112,
                    &v96,
                    v150) == *((_QWORD *)this + 15)
    || (std::wstring::wstring(v148, L"OMADM::WapEnrollmentProvisioning"),
        v25 = 3,
        v98 = 3,
        v97 = 3,
        v26 = (_QWORD *)std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Try_emplace<std::wstring,>(
                          (char *)v6 + 112,
                          &Uuid,
                          v148),
        v27 = 1,
        (unsigned int)std::wstring::compare(*v26 + 48LL, L"True")) )
  {
    v27 = 0;
  }
  if ( (v25 & 2) != 0 )
  {
    v25 &= ~2u;
    v98 = v25;
    std::wstring::_Tidy_deallocate(v148);
  }
  if ( (v25 & 1) != 0 )
  {
    v25 &= ~1u;
    v98 = v25;
    std::wstring::_Tidy_deallocate(v150);
  }
  if ( v27 )
  {
    v95 = 1;
  }
  else
  {
    v95 = 0;
    std::wstring::wstring(v148, L"PackageID");
    v28 = (__int64 *)std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(
                       (char *)v6 + 112,
                       &v96,
                       v148);
    v29 = *((_QWORD *)this + 15);
    v30 = *v28;
    std::wstring::_Tidy_deallocate(v148);
    if ( v30 != v29 )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v112);
      v31 = LoadCKSReader(&v112);
      v32 = v102;
      if ( v31 >= 0 )
        v32 = 1;
      v102 = v32;
    }
  }
  std::wstring::wstring(v148, L"OMADM::AccountID");
  std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(
    (char *)v6 + 112,
    &v96,
    v148);
  std::wstring::_Tidy_deallocate(v148);
  if ( v96 != *((BSTR *)this + 15) )
  {
    Uuid = 0;
    v33 = v96 + 24;
    if ( *((_QWORD *)v96 + 9) > 7u )
      v33 = *(unsigned __int16 **)v33;
    if ( !UuidFromStringW(v33, &Uuid) )
    {
      Src = Uuid;
      GetEnrollmentType(&Src, &v107);
    }
  }
  while ( 2 )
  {
    v34 = v93;
    while ( 1 )
    {
      v35 = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 48LL))(ppvObject, &v106);
      v14 = v35;
      if ( v35 )
      {
        if ( v35 < 0 )
        {
          v7 = this;
          if ( (unsigned int)(v35 + 1072894464) <= 0x92 )
            v14 = -2046820328;
          goto LABEL_19;
        }
        if ( (unsigned int)dword_18003E080 > 5 )
        {
          v92 = v35;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (int)&dword_18003E080,
            (int)&word_180037B7E,
            v12,
            v13,
            (__int64)&v92);
        }
        if ( !*((_QWORD *)v6 + 2) || v34 )
        {
          v14 = -2147418113;
          goto LABEL_18;
        }
        v14 = (*(__int64 (__fastcall **)(CWapDPU *, _QWORD, _QWORD))(*(_QWORD *)v6 + 24LL))(v6, 0, 0);
        if ( v14 < 0 )
          goto LABEL_18;
        v58 = this;
        v59 = (_QWORD *)*((_QWORD *)this + 15);
        while ( 1 )
        {
          v59 = (_QWORD *)*v59;
          if ( v59 == *((_QWORD **)v58 + 15) )
            break;
          v60 = *((_QWORD *)v6 + 2);
          v61 = *(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD *))(*(_QWORD *)v60 + 96LL);
          v96 = (BSTR)(v59 + 6);
          v62 = v59 + 6;
          if ( v59[9] > 7u )
            v62 = (_QWORD *)v59[6];
          v114 = (unsigned __int16 *)(v59 + 2);
          v63 = v59 + 2;
          if ( v59[5] > 7u )
            v63 = (_QWORD *)v59[2];
          v14 = v61(v60, v63, v62);
          if ( v14 < 0 )
            goto LABEL_18;
          SysFreeString(v9);
          v104 = 0;
          v64 = v114;
          if ( v59[5] > 7u )
            v64 = *(const OLECHAR **)v114;
          v65 = SysAllocString(v64);
          ATL::CComBSTR::operator=(&v104, v65);
          v9 = v104;
          if ( !v104 )
            goto LABEL_17;
          VariantClear(&pvarg);
          v66 = v96;
          if ( v59[9] > 7u )
            v66 = *(const OLECHAR **)v96;
          pvarg.llVal = (LONGLONG)SysAllocString(v66);
          pvarg.vt = 8;
          v67 = *((_QWORD *)v6 + 1);
          v134 = pvarg;
          v14 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, VARIANTARG *))(*(_QWORD *)v67 + 104LL))(v67, v9, &v134);
          if ( v14 < 0 )
            goto LABEL_18;
          v58 = this;
        }
        v14 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v6 + 1) + 56LL))(*((_QWORD *)v6 + 1));
        if ( v14 < 0 )
          goto LABEL_18;
        v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v6 + 2) + 264LL))(
                *((_QWORD *)v6 + 2),
                *((_QWORD *)v6 + 1));
        if ( (unsigned int)dword_18003E080 > 5 )
        {
          v92 = v14;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (int)&dword_18003E080,
            (int)&unk_180037BA8,
            v12,
            v13,
            (__int64)&v92);
        }
        if ( v14 < 0 )
          goto LABEL_18;
        v68 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))*((_QWORD *)v6 + 8);
        if ( v68 )
        {
          v14 = v68(*((_QWORD *)v6 + 6), *((_QWORD *)v6 + 2), *((_QWORD *)v6 + 4), *((_QWORD *)v6 + 1));
          if ( v14 < 0 )
            goto LABEL_18;
        }
        v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, int *))(**((_QWORD **)v6 + 4) + 104LL))(
                *((_QWORD *)v6 + 4),
                *((_QWORD *)v6 + 2),
                &v109);
        if ( v14 < 0 )
          goto LABEL_18;
        (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v6 + 4) + 112LL))(
          *((_QWORD *)v6 + 4),
          *((_QWORD *)v6 + 2));
        v69 = (_QWORD *)*((_QWORD *)this + 15);
        while ( 1 )
        {
          v69 = (_QWORD *)*v69;
          if ( v69 == *((_QWORD **)this + 15) )
            break;
          v70 = v69 + 2;
          if ( v69[5] > 7u )
            v70 = (_QWORD *)*v70;
          (*(void (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)v6 + 2) + 104LL))(*((_QWORD *)v6 + 2), v70);
        }
        v71 = **((_QWORD **)v6 + 1);
        v8 = (struct _RTL_CRITICAL_SECTION *)v121;
        if ( v109 )
        {
          v14 = (*(__int64 (**)(void))(v71 + 64))();
          if ( v14 < 0 )
            goto LABEL_18;
          v14 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v6 + 1) + 24LL))(*((_QWORD *)v6 + 1));
          if ( (unsigned int)dword_18003E080 <= 4 )
          {
LABEL_166:
            v73 = *((_QWORD *)v6 + 4);
            if ( v73 )
            {
              *((_QWORD *)v6 + 4) = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
            }
            if ( v14 >= 0 )
              goto LABEL_178;
            goto LABEL_18;
          }
          v72 = (__int16 *)&byte_18003795F;
        }
        else
        {
          v14 = (*(__int64 (**)(void))(v71 + 72))();
          if ( (unsigned int)dword_18003E080 <= 4 )
            goto LABEL_166;
          v72 = &word_1800378E6;
        }
        v92 = v14;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (int)&dword_18003E080,
          (int)v72,
          v12,
          v13,
          (__int64)&v92);
        goto LABEL_166;
      }
      if ( v106 == 1 )
        break;
      if ( v106 == 3 )
      {
        v14 = -2147024809;
        goto LABEL_18;
      }
      if ( v106 == 15 )
      {
        ATL::CComPtrBase<IDomNode>::Release(&v94);
        v36 = (_QWORD *)((char *)v6 + 24);
        v37 = (*(__int64 (__fastcall **)(_QWORD, struct IUnknown **))(**((_QWORD **)v6 + 3) + 144LL))(
                *((_QWORD *)v6 + 3),
                &v94);
        v14 = v37;
        if ( v37 == -2147023728 )
        {
          if ( *v36 )
            ATL::AtlComPtrAssign((struct IUnknown **)v6 + 3, 0);
        }
        else
        {
          if ( v37 < 0 )
            goto LABEL_18;
          ATL::CComPtrBase<IDomNode>::CComPtrBase<IDomNode>(v123, *v36);
          v38 = (_QWORD *)std::_Tree<std::_Tset_traits<ATL::CAdapt<ATL::CComPtr<IDomNode>>,std::less<ATL::CAdapt<ATL::CComPtr<IDomNode>>>,std::allocator<ATL::CAdapt<ATL::CComPtr<IDomNode>>>,0>>::find(
                            &v113,
                            v135,
                            v123);
          v39 = *v38 != (_QWORD)v113;
          wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(v123);
          if ( v39 )
          {
            ATL::CComPtrBase<IDomNode>::CComPtrBase<IDomNode>(v132, *v36);
            ATL::CComPtrBase<IDomNode>::CComPtrBase<IDomNode>(v130, v94);
            v40 = CWapDPU::RemoveNonSupportedNode(v130, v132);
            v14 = v40;
            if ( v40 < 0 )
            {
              CWapNodeValidator::SetNodeRemovalError((CWapNodeValidator *)&v155, v40);
              goto LABEL_18;
            }
            ATL::CComPtrBase<IDomNode>::CComPtrBase<IDomNode>(v128, *v36);
            std::_Tree<std::_Tset_traits<ATL::CAdapt<ATL::CComPtr<IDomNode>>,std::less<ATL::CAdapt<ATL::CComPtr<IDomNode>>>,std::allocator<ATL::CAdapt<ATL::CComPtr<IDomNode>>>,0>>::erase(
              &v113,
              v128);
            wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(v128);
            CWapNodeValidator::IncrementNodeRemovalCount((CWapNodeValidator *)&v155);
          }
          if ( (struct IUnknown *)*v36 != v94 )
            ATL::AtlComPtrAssign((struct IUnknown **)v6 + 3, v94);
          v34 = v93;
        }
        v93 = --v34;
        v25 = v98;
      }
    }
    std::wstring::wstring(v144);
    *(_QWORD *)cbInit = 0;
    v97 = 0;
    std::wstring::wstring(v143);
    std::wstring::wstring(v142);
    v119 = 0;
    v111 = 0;
    v92 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 160LL))(ppvObject);
    if ( !v92 )
      v93 = v34 + 1;
    v14 = (*(__int64 (__fastcall **)(void *, UINT *, unsigned int *))(*(_QWORD *)ppvObject + 112LL))(
            ppvObject,
            cbInit,
            &v97);
    if ( v14 < 0 )
      goto LABEL_92;
    std::wstring::_Assign<unsigned short>(v144, *(_QWORD *)cbInit, v97);
    ATL::CComPtrBase<IDomNode>::Release(&v94);
    v41 = v144;
    if ( v144[3] > 7u )
      v41 = (_QWORD *)v144[0];
    v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *, struct IUnknown **, _QWORD))(**((_QWORD **)v6 + 4) + 120LL))(
            *((_QWORD *)v6 + 4),
            v41,
            &v94,
            *((_QWORD *)v6 + 3));
    if ( v14 < 0 )
      goto LABEL_92;
    v14 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 64LL))(ppvObject);
    if ( !v14 )
    {
      while ( 1 )
      {
        v14 = (*(__int64 (__fastcall **)(void *, UINT *, unsigned int *))(*(_QWORD *)ppvObject + 112LL))(
                ppvObject,
                cbInit,
                &v97);
        if ( v14 < 0 )
          goto LABEL_92;
        std::wstring::_Assign<unsigned short>(v143, *(_QWORD *)cbInit, v97);
        v14 = (*(__int64 (__fastcall **)(void *, __int64 *, unsigned int *))(*(_QWORD *)ppvObject + 128LL))(
                ppvObject,
                &v119,
                &v111);
        if ( v14 < 0 )
          goto LABEL_92;
        std::wstring::_Assign<unsigned short>(v142, v119, v111);
        std::wstring::wstring(&Src);
        std::wstring::wstring(v150, L"$(__");
        std::wstring::wstring(v152, L")");
        v42 = std::wstring::find(v142, v150, 0);
        v43 = std::wstring::find(v142, v152, v42);
        while ( v42 != -1 && v43 != -1 )
        {
          std::wstring::append(&Src);
          std::wstring::substr(v142, v148, v151 + v42, v43 - v151 - v42);
          if ( !v149
            || *((_QWORD *)this + 15) == *(_QWORD *)std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(
                                                      (char *)v6 + 112,
                                                      v136,
                                                      v148) )
          {
            std::wstring::substr(v142, v158, v42, v153 + v43 - v42);
            std::wstring::_Append<unsigned short>(&Src);
            std::wstring::_Tidy_deallocate(v158);
          }
          else
          {
            std::wstring::_Append<unsigned short>(&Src);
          }
          v42 = std::wstring::find(v142, v150, v43 + v153);
          v43 = std::wstring::find(v142, v152, v42);
          std::wstring::_Tidy_deallocate(v148);
        }
        std::wstring::append(&Src);
        p_Src = &Src;
        if ( v146 > 7 )
          p_Src = *(UUID **)&Src.Data1;
        v45 = v143;
        if ( v143[3] > 7u )
          v45 = (_QWORD *)v143[0];
        v14 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD *, UUID *))v94->lpVtbl[4].QueryInterface)(
                v94,
                v45,
                p_Src);
        if ( v14 < 0 )
        {
          std::wstring::_Tidy_deallocate(v152);
          std::wstring::_Tidy_deallocate(v150);
          std::wstring::_Tidy_deallocate(&Src);
          std::wstring::_Tidy_deallocate(v142);
          std::wstring::_Tidy_deallocate(v143);
          std::wstring::_Tidy_deallocate(v144);
          v7 = this;
          goto LABEL_19;
        }
        std::wstring::_Tidy_deallocate(v152);
        std::wstring::_Tidy_deallocate(v150);
        std::wstring::_Tidy_deallocate(&Src);
        v14 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 72LL))(ppvObject);
        if ( v14 )
        {
          v25 = v98;
          break;
        }
      }
    }
    if ( v14 < 0 )
    {
LABEL_92:
      std::wstring::_Tidy_deallocate(v142);
      std::wstring::_Tidy_deallocate(v143);
      std::wstring::_Tidy_deallocate(v144);
      v7 = this;
      goto LABEL_19;
    }
    if ( v95 )
    {
      ATL::CComPtrBase<IDomNode>::CComPtrBase<IDomNode>(v129, v94);
      v14 = CWapNodeValidator::ValidateNode((CWapNodeValidator *)&v155);
      if ( v14 >= 0 )
      {
        if ( !v101 )
        {
          if ( __eh34_try(0, 1) )
          {
            __eh34_scope_strut(1);
            ATL::CComPtrBase<IDomNode>::CComPtrBase<IDomNode>(v131, v94);
            std::_Tree<std::_Tset_traits<ATL::CAdapt<ATL::CComPtr<IDomNode>>,std::less<ATL::CAdapt<ATL::CComPtr<IDomNode>>>,std::allocator<ATL::CAdapt<ATL::CComPtr<IDomNode>>>,0>>::insert<0,0>(
              &v113,
              v141,
              v131);
            wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(v131);
          }
          if ( __eh34_catch(1) )
          {
            if ( __eh34_catch_type(1, &std::exception `RTTI Type Descriptor', &v137) )
            {
              if ( (unsigned int)dword_18003E080 > 5
                && (unsigned __int8)tlgKeywordOn(&dword_18003E080, 0x200000000000LL) )
              {
                v96 = (BSTR)(*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v137 + 8LL))(v137);
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
                  v79,
                  (int)byte_180037BFB,
                  v80,
                  v81,
                  (__int64)&v96);
              }
              v93 = wil::ResultFromCaughtException(v78);
              __eh34_try_continuation(1, &std::exception `RTTI Type Descriptor', &loc_180029F83);
              std::wstring::_Tidy_deallocate(v142);
              std::wstring::_Tidy_deallocate(v143);
              std::wstring::_Tidy_deallocate(v144);
              goto LABEL_114;
            }
            if ( __eh34_catch_type(1, &ATL::CAtlException `RTTI Type Descriptor', &v138) )
            {
              v93 = *(_DWORD *)v138;
              if ( (unsigned int)dword_18003E080 > 5
                && (unsigned __int8)tlgKeywordOn(&dword_18003E080, 0x200000000000LL) )
              {
                v95 = v82;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                  (int)&dword_18003E080,
                  (int)byte_180037B0D,
                  v82,
                  v83,
                  (__int64)&v95);
              }
              __eh34_try_continuation(1, &ATL::CAtlException `RTTI Type Descriptor', &loc_180029FB2);
              std::wstring::_Tidy_deallocate(v142);
              std::wstring::_Tidy_deallocate(v143);
              std::wstring::_Tidy_deallocate(v144);
              goto LABEL_114;
            }
          }
        }
LABEL_111:
        v53 = (_QWORD *)((char *)v6 + 24);
        v54 = v94;
        if ( *((_QWORD *)v6 + 3) )
        {
          if ( !v92 )
            goto LABEL_117;
          ATL::CComPtrBase<IDomNode>::CComPtrBase<IDomNode>(v126, v94);
          v55 = (_QWORD *)std::_Tree<std::_Tset_traits<ATL::CAdapt<ATL::CComPtr<IDomNode>>,std::less<ATL::CAdapt<ATL::CComPtr<IDomNode>>>,std::allocator<ATL::CAdapt<ATL::CComPtr<IDomNode>>>,0>>::find(
                            &v113,
                            &Uuid,
                            v126);
          v56 = *v55 != (_QWORD)v113;
          v25 &= ~4u;
          v98 = v25;
          wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(v126);
          if ( v56 )
          {
            ATL::CComPtrBase<IDomNode>::CComPtrBase<IDomNode>(v127, v94);
            ATL::CComPtrBase<IDomNode>::CComPtrBase<IDomNode>(&v118, *v53);
            v57 = CWapDPU::RemoveNonSupportedNode(&v118, v127);
            v14 = v57;
            if ( v57 < 0 )
            {
              CWapNodeValidator::SetNodeRemovalError((CWapNodeValidator *)&v155, v57);
              std::wstring::_Tidy_deallocate(v142);
              std::wstring::_Tidy_deallocate(v143);
              std::wstring::_Tidy_deallocate(v144);
              v7 = this;
              goto LABEL_19;
            }
            ATL::CComPtrBase<IDomNode>::CComPtrBase<IDomNode>(&v96, v94);
            std::_Tree<std::_Tset_traits<ATL::CAdapt<ATL::CComPtr<IDomNode>>,std::less<ATL::CAdapt<ATL::CComPtr<IDomNode>>>,std::allocator<ATL::CAdapt<ATL::CComPtr<IDomNode>>>,0>>::erase(
              &v113,
              &v96);
            wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(&v96);
            CWapNodeValidator::IncrementNodeRemovalCount((CWapNodeValidator *)&v155);
          }
        }
        else
        {
          if ( *((struct IUnknown **)v6 + 2) != v94 )
          {
            ATL::AtlComPtrAssign((struct IUnknown **)v6 + 2, v94);
            v54 = v94;
          }
LABEL_117:
          if ( (struct IUnknown *)*v53 != v54 )
            ATL::AtlComPtrAssign((struct IUnknown **)v6 + 3, v54);
        }
        std::wstring::_Tidy_deallocate(v142);
        std::wstring::_Tidy_deallocate(v143);
        std::wstring::_Tidy_deallocate(v144);
        continue;
      }
      bstrString = 0;
      ((void (__fastcall *)(struct IUnknown *, BSTR *))v94->lpVtbl[3].AddRef)(v94, &bstrString);
      if ( (unsigned int)dword_18003E080 > 2 )
      {
        v95 = v14;
        v96 = bstrString;
        v118 = "ValidateNode failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          v46,
          (int)&word_180037ABE,
          v47,
          v48,
          (__int64)&v118,
          (__int64)&v96,
          (__int64)&v95);
      }
      SysFreeString(bstrString);
      std::wstring::_Tidy_deallocate(v142);
      std::wstring::_Tidy_deallocate(v143);
      std::wstring::_Tidy_deallocate(v144);
      v7 = this;
      goto LABEL_19;
    }
    break;
  }
  if ( !v102 )
    goto LABEL_111;
  v49 = v112;
  ATL::CComPtrBase<IDomNode>::CComPtrBase<IDomNode>(v124, v94);
  if ( (int)ValidateProvisioningNode(v124, v49, &v101) < 0 || v101 )
    goto LABEL_111;
  ATL::CComPtrBase<IDomNode>::CComPtrBase<IDomNode>(v125, v94);
  if ( __eh34_try(0, 3) )
  {
    __eh34_scope_strut(3);
    std::_Tree<std::_Tset_traits<ATL::CAdapt<ATL::CComPtr<IDomNode>>,std::less<ATL::CAdapt<ATL::CComPtr<IDomNode>>>,std::allocator<ATL::CAdapt<ATL::CComPtr<IDomNode>>>,0>>::insert<0,0>(
      &v113,
      &v134,
      v125);
    wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(v125);
    bstrString = 0;
    v50 = ((__int64 (__fastcall *)(struct IUnknown *, BSTR *))v94->lpVtbl[3].AddRef)(v94, &bstrString);
  }
  if ( __eh34_catch(3) )
  {
    if ( __eh34_catch_type(3, &std::exception `RTTI Type Descriptor', &v139) )
    {
      if ( (unsigned int)dword_18003E080 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18003E080, 0x200000000000LL) )
      {
        v96 = (BSTR)(*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v139 + 8LL))(v139);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v85,
          (int)&word_180037B46,
          v86,
          v87,
          (__int64)&v96);
      }
      v93 = wil::ResultFromCaughtException(v84);
      __eh34_try_continuation(3, &std::exception `RTTI Type Descriptor', &loc_18002A2A6);
      std::wstring::_Tidy_deallocate(v142);
      std::wstring::_Tidy_deallocate(v143);
      std::wstring::_Tidy_deallocate(v144);
LABEL_114:
      v14 = v93;
      v8 = lpCriticalSection;
      v9 = v104;
      v6 = v122;
      if ( v93 >= 0 )
        goto LABEL_178;
      v103 = v108;
      v116 = v114;
      v7 = v122;
      goto LABEL_19;
    }
    if ( __eh34_catch_type(3, &ATL::CAtlException `RTTI Type Descriptor', &v140) )
    {
      v93 = *(_DWORD *)v140;
      if ( (unsigned int)dword_18003E080 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18003E080, 0x200000000000LL) )
      {
        v95 = v88;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (int)&dword_18003E080,
          (int)byte_1800379D9,
          v88,
          v89,
          (__int64)&v95);
      }
      __eh34_try_continuation(3, &ATL::CAtlException `RTTI Type Descriptor', &loc_18002A2D2);
      std::wstring::_Tidy_deallocate(v142);
      std::wstring::_Tidy_deallocate(v143);
      std::wstring::_Tidy_deallocate(v144);
      goto LABEL_114;
    }
  }
  v51 = v50;
  if ( v50 >= 0 )
  {
    if ( (Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(PROVISIONING_DIAGNOSTICS_Context, ProvXMLSettingRemoved, bstrString);
    v110 = 1;
    SysFreeString(bstrString);
    goto LABEL_111;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x250,
    (unsigned int)"onecoreuap\\admin\\dm\\coredpus\\wapdpu\\wapdpuimpl.cpp",
    (const char *)(unsigned int)v50,
    pwszBaseUri);
  SysFreeString(bstrString);
  std::wstring::_Tidy_deallocate(v142);
  std::wstring::_Tidy_deallocate(v143);
  std::wstring::_Tidy_deallocate(v144);
  std::_Tree<std::_Tset_traits<ATL::CAdapt<ATL::CComPtr<IDomNode>>,std::less<ATL::CAdapt<ATL::CComPtr<IDomNode>>>,std::allocator<ATL::CAdapt<ATL::CComPtr<IDomNode>>>,0>>::~_Tree<std::_Tset_traits<ATL::CAdapt<ATL::CComPtr<IDomNode>>,std::less<ATL::CAdapt<ATL::CComPtr<IDomNode>>>,std::allocator<ATL::CAdapt<ATL::CComPtr<IDomNode>>>,0>>(&v113);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v112);
  CWapNodeValidator::~CWapNodeValidator((CWapNodeValidator *)&v155);
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(&v94);
  SysFreeString(0);
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(&ppInput);
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(&v120);
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(&ppvObject);
  if ( v8 )
  {
    LeaveCriticalSection(v8);
    lpCriticalSection = 0;
  }
  return v51;
}

```

## disassembly

```asm
0x180029240  push    rbx
0x180029242  push    rsi
0x180029243  push    rdi
0x180029244  push    r12
0x180029246  push    r13
0x180029248  push    r14
0x18002924a  push    r15
0x18002924c  sub     rsp, 550h
0x180029253  mov     rax, cs:__security_cookie
0x18002925a  xor     rax, rsp
0x18002925d  mov     [rsp+588h+var_48], rax
0x180029265  mov     r12d, r8d
0x180029268  mov     [rsp+588h+var_500], r12d
0x180029270  mov     r14, rdx
0x180029273  mov     [rsp+588h+var_4A8], rdx
0x18002927b  mov     r13, rcx
0x18002927e  mov     [rsp+588h+var_4E0], r12d
0x180029286  mov     [rsp+588h+var_478], rcx
0x18002928e  mov     rbx, rcx
0x180029291  mov     [rsp+588h+var_548], rcx
0x180029296  mov     [rsp+588h+var_4B8], rdx
0x18002929e  xor     r15d, r15d
0x1800292a1  mov     [rsp+588h+var_520], r15d
0x1800292a6  lea     rdi, [rcx+48h]
0x1800292aa  mov     [rsp+588h+var_480], rdi
0x1800292b2  mov     rcx, rdi; lpCriticalSection
0x1800292b5  call    cs:__imp_EnterCriticalSection
0x1800292bc  nop     dword ptr [rax+rax+00h]
0x1800292c1  mov     [rsp+588h+lpCriticalSection], rdi
0x1800292c9  mov     [rsp+588h+ppvObject], r15
0x1800292ce  mov     [rsp+588h+var_4DC], r15d
0x1800292d6  mov     [rsp+588h+var_4E8], r15d
0x1800292de  mov     [rsp+588h+var_488], r15
0x1800292e6  mov     qword ptr [rsp+588h+cbInit], r15
0x1800292ee  mov     [rsp+588h+var_4A0], r15
0x1800292f6  mov     [rsp+588h+bstrString], r15
0x1800292fb  mov     esi, r15d
0x1800292fe  mov     [rsp+588h+var_4F8], r15
0x180029306  xorps   xmm0, xmm0
0x180029309  xor     eax, eax
0x18002930b  movups  xmmword ptr [rsp+588h+pvarg], xmm0
0x180029313  mov     qword ptr [rsp+588h+pvarg+10h], rax
0x18002931b  mov     [rsp+588h+var_538], r15
0x180029320  movdqa  [rsp+588h+var_98], xmm0
0x180029329  lea     ecx, [rax+48h]; Size
0x18002932c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180029331  mov     [rax], rax
0x180029334  mov     [rax+8], rax
0x180029338  mov     [rax+10h], rax
0x18002933c  lea     ecx, [r15+1]
0x180029340  mov     word ptr [rax+18h], 101h
0x180029346  mov     qword ptr [rsp+588h+var_98], rax
0x18002934e  mov     [rsp+588h+var_2A0], r15w
0x180029357  mov     [rsp+588h+var_2A8], r15
0x18002935f  mov     [rsp+588h+var_508], ecx
0x180029366  mov     [rsp+588h+var_4D8], r15d
0x18002936e  mov     [rsp+588h+var_4D0], r15
0x180029376  mov     [rsp+588h+var_4E4], r15d
0x18002937e  xorps   xmm0, xmm0
0x180029381  movdqu  [rsp+588h+var_4C8], xmm0
0x18002938a  lea     ecx, [r15+28h]; Size
0x18002938e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180029393  mov     [rax], rax
0x180029396  mov     [rax+8], rax
0x18002939a  mov     [rax+10h], rax
0x18002939e  lea     ecx, [r15+1]; ControlCode
0x1800293a2  mov     word ptr [rax+18h], 101h
0x1800293a8  mov     qword ptr [rsp+588h+var_4C8], rax
0x1800293b0  xorps   xmm0, xmm0
0x1800293b3  movups  xmmword ptr [rsp+588h+ActivityId.Data1], xmm0
0x1800293bb  lea     rdx, [rsp+588h+ActivityId]; ActivityId
0x1800293c3  call    cs:__imp_EventActivityIdControl
0x1800293ca  nop     dword ptr [rax+rax+00h]
0x1800293cf  lea     rcx, [rsp+588h+pvarg]; pvarg
0x1800293d7  call    cs:__imp_VariantInit
0x1800293de  nop     dword ptr [rax+rax+00h]
0x1800293e3  test    r14, r14
0x1800293e6  jz      loc_18002A860
0x1800293ec  cmp     r12d, 1
0x1800293f0  jz      loc_18002A860
0x1800293f6  cmp     [rbx+8], r15
0x1800293fa  jnz     short loc_180029407
0x1800293fc  mov     r14d, 8000FFFFh
0x180029402  jmp     loc_180029500
0x180029407  cmp     [r13+20h], r15
0x18002940b  jz      short loc_1800293FC
0x18002940d  xor     r8d, r8d; pMalloc
0x180029410  lea     rdx, [rsp+588h+ppvObject]; ppvObject
0x180029415  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x18002941c  call    cs:__imp_CreateXmlReader
0x180029423  nop     dword ptr [rax+rax+00h]
0x180029428  mov     r14d, eax
0x18002942b  test    eax, eax
0x18002942d  js      loc_180029500
0x180029433  mov     rcx, [rsp+588h+ppvObject]
0x180029438  mov     rax, [rcx]
0x18002943b  xor     r8d, r8d
0x18002943e  lea     edx, [r8+4]
0x180029442  mov     rax, [rax+28h]
0x180029446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002944b  mov     r14d, eax
0x18002944e  test    eax, eax
0x180029450  js      loc_180029500
0x180029456  test    r12d, r12d
0x180029459  jz      short loc_180029463
0x18002945b  mov     rdx, r12
0x18002945e  shr     rdx, 1
0x180029461  jmp     short loc_180029468
0x180029463  mov     edx, 7FFFFFFFh; unsigned __int64
0x180029468  lea     r8, [rsp+588h+bstrString]; unsigned __int64 *
0x18002946d  mov     r10, [rsp+588h+var_4A8]
0x180029475  mov     rcx, r10; unsigned __int16 *
0x180029478  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18002947d  mov     r14d, eax
0x180029480  test    eax, eax
0x180029482  js      short loc_180029500
0x180029484  mov     r12, r10
0x180029487  movzx   ecx, word ptr [r10]
0x18002948b  call    cs:__imp__o_iswspace
0x180029492  nop     dword ptr [rax+rax+00h]
0x180029497  mov     rbx, [rsp+588h+bstrString]
0x18002949c  test    eax, eax
0x18002949e  jz      short loc_1800294BA
0x1800294a0  add     r12, 2
0x1800294a4  dec     rbx
0x1800294a7  movzx   ecx, word ptr [r12]
0x1800294ac  call    cs:__imp__o_iswspace
0x1800294b3  nop     dword ptr [rax+rax+00h]
0x1800294b8  jmp     short loc_18002949C
0x1800294ba  lea     r8, [rsp+588h+cbInit]; unsigned __int64 *
0x1800294c2  mov     rcx, rbx; unsigned __int64
0x1800294c5  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800294ca  mov     r14d, eax
0x1800294cd  test    eax, eax
0x1800294cf  js      short loc_1800294FB
0x1800294d1  mov     edx, [rsp+588h+cbInit]; cbInit
0x1800294d8  mov     rcx, r12; pInit
0x1800294db  call    cs:__imp_SHCreateMemStream
0x1800294e2  nop     dword ptr [rax+rax+00h]
0x1800294e7  nop
0x1800294e8  mov     [rsp+588h+var_488], rax
0x1800294f0  test    rax, rax
0x1800294f3  jnz     short loc_18002955E
0x1800294f5  mov     r14d, 8007000Eh
0x1800294fb  mov     rbx, [rsp+588h+var_548]
0x180029500  mov     rcx, [r13+20h]
0x180029504  test    rcx, rcx
0x180029507  jz      short loc_18002951E
0x180029509  mov     rdx, [r13+10h]
0x18002950d  test    rdx, rdx
0x180029510  jz      short loc_18002951E
0x180029512  mov     rax, [rcx]
0x180029515  mov     rax, [rax+70h]
0x180029519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002951e  cmp     [r13+10h], r15
0x180029522  jz      loc_18002A873
0x180029528  mov     rbx, [rbx+78h]
0x18002952c  mov     rsi, [rsp+588h+var_548]
0x180029531  mov     rbx, [rbx]
0x180029534  cmp     rbx, [rsi+78h]
0x180029538  jz      loc_18002A86B
0x18002953e  mov     rcx, [r13+10h]
0x180029542  mov     rax, [rcx]
0x180029545  lea     rdx, [rbx+10h]
0x180029549  cmp     qword ptr [rbx+28h], 7
0x18002954e  jbe     short loc_180029553
0x180029550  mov     rdx, [rdx]
0x180029553  mov     rax, [rax+68h]
0x180029557  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002955c  jmp     short loc_180029531
0x18002955e  lea     rcx, [rsp+588h+var_4A0]
0x180029566  mov     [rsp+588h+ppInput], rcx; ppInput
0x18002956b  mov     [rsp+588h+pwszBaseUri], r15; int
0x180029570  xor     r9d, r9d; fEncodingHint
0x180029573  lea     r8, pwszEncodingName; "UTF-16"
0x18002957a  xor     edx, edx; pMalloc
0x18002957c  mov     rcx, rax; pInputStream
0x18002957f  call    cs:__imp_CreateXmlReaderInputWithEncodingName
0x180029586  nop     dword ptr [rax+rax+00h]
0x18002958b  mov     r14d, eax
0x18002958e  test    eax, eax
0x180029590  js      loc_1800294FB
0x180029596  mov     rcx, [rsp+588h+ppvObject]
0x18002959b  mov     rax, [rcx]
0x18002959e  mov     rdx, [rsp+588h+var_4A0]
0x1800295a6  mov     rax, [rax+18h]
0x1800295aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800295af  mov     r14d, eax
0x1800295b2  test    eax, eax
0x1800295b4  js      loc_1800294FB
0x1800295ba  mov     [rsp+588h+var_53C], r15d
0x1800295bf  mov     [rsp+588h+var_504], r15d
0x1800295c7  lea     rdx, aOmadmWapenroll; "OMADM::WapEnrollmentProvisioning"
0x1800295ce  lea     rcx, [rsp+588h+var_2F8]
0x1800295d6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800295db  nop
0x1800295dc  mov     r12d, 1
0x1800295e2  mov     [rsp+588h+var_51C], r12d
0x1800295e7  mov     [rsp+588h+var_520], r12d
0x1800295ec  lea     r8, [rsp+588h+var_2F8]
0x1800295f4  lea     rdx, [rsp+588h+var_528]
0x1800295f9  lea     rcx, [r13+70h]
0x1800295fd  call    ?find@?$_Hash@V?$_Hmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@stdext@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(std::wstring const &)
0x180029602  mov     r14, [rsp+588h+var_548]
0x180029607  mov     rcx, [r14+78h]
0x18002960b  cmp     [rax], rcx
0x18002960e  jz      short loc_180029667
0x180029610  lea     rdx, aOmadmWapenroll; "OMADM::WapEnrollmentProvisioning"
0x180029617  lea     rcx, [rsp+588h+var_318]
0x18002961f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180029624  nop
0x180029625  mov     r12d, 3
0x18002962b  mov     [rsp+588h+var_51C], r12d
0x180029630  mov     [rsp+588h+var_520], r12d
0x180029635  lea     r8, [rsp+588h+var_318]
0x18002963d  lea     rdx, [rsp+588h+Uuid]
0x180029645  lea     rcx, [r13+70h]
0x180029649  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$_Hash@V?$_Hmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@stdext@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Try_emplace<std::wstring,>(std::wstring &&)
0x18002964e  mov     rcx, [rax]
0x180029651  add     rcx, 30h ; '0'
0x180029655  lea     rdx, aTrue_0; "True"
0x18002965c  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x180029661  test    eax, eax
0x180029663  mov     bl, 1
0x180029665  jz      short loc_18002966A
0x180029667  mov     bl, r15b
0x18002966a  test    r12b, 2
0x18002966e  jz      short loc_180029687
0x180029670  and     r12d, 0FFFFFFFDh
0x180029674  mov     [rsp+588h+var_51C], r12d
0x180029679  lea     rcx, [rsp+588h+var_318]; void *
0x180029681  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029686  nop
0x180029687  test    r12b, 1
0x18002968b  jz      short loc_1800296A3
0x18002968d  and     r12d, 0FFFFFFFEh
0x180029691  mov     [rsp+588h+var_51C], r12d
0x180029696  lea     rcx, [rsp+588h+var_2F8]; void *
0x18002969e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800296a3  test    bl, bl
0x1800296a5  jz      short loc_1800296B1
0x1800296a7  mov     [rsp+588h+var_530], 1
0x1800296af  jmp     short loc_18002972E
0x1800296b1  mov     [rsp+588h+var_530], r15d
0x1800296b6  lea     rdx, aPackageid; "PackageID"
0x1800296bd  lea     rcx, [rsp+588h+var_318]
0x1800296c5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800296ca  lea     r8, [rsp+588h+var_318]
0x1800296d2  lea     rdx, [rsp+588h+var_528]
0x1800296d7  lea     rcx, [r13+70h]
0x1800296db  call    ?find@?$_Hash@V?$_Hmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@stdext@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(std::wstring const &)
0x1800296e0  mov     r14, [r14+78h]
0x1800296e4  mov     rbx, [rax]
0x1800296e7  lea     rcx, [rsp+588h+var_318]; void *
0x1800296ef  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800296f4  cmp     rbx, r14
0x1800296f7  jz      short loc_18002972E
0x1800296f9  lea     rcx, [rsp+588h+var_4D0]
0x180029701  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029706  lea     rcx, [rsp+588h+var_4D0]; struct IMCSFDatastore **
0x18002970e  call    ?LoadCKSReader@@YAJPEAPEAUIMCSFDatastore@@@Z; LoadCKSReader(IMCSFDatastore * *)
0x180029713  mov     r14d, [rsp+588h+var_504]
0x18002971b  test    eax, eax
0x18002971d  mov     eax, 1
0x180029722  cmovns  r14d, eax
0x180029726  mov     [rsp+588h+var_504], r14d
0x18002972e  lea     rdx, aOmadmAccountid; "OMADM::AccountID"
0x180029735  lea     rcx, [rsp+588h+var_318]
0x18002973d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180029742  lea     r8, [rsp+588h+var_318]
0x18002974a  lea     rdx, [rsp+588h+var_528]
0x18002974f  lea     rcx, [r13+70h]
0x180029753  call    ?find@?$_Hash@V?$_Hmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@stdext@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(std::wstring const &)
0x180029758  lea     rcx, [rsp+588h+var_318]; void *
0x180029760  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029765  mov     rax, [rsp+588h+var_528]
0x18002976a  mov     rcx, [rsp+588h+var_548]
0x18002976f  cmp     rax, [rcx+78h]
0x180029773  jz      short loc_1800297D3
0x180029775  xorps   xmm0, xmm0
0x180029778  movups  xmmword ptr [rsp+588h+Uuid.Data1], xmm0
0x180029780  lea     rcx, [rax+30h]
0x180029784  cmp     qword ptr [rcx+18h], 7
0x180029789  jbe     short loc_18002978E
0x18002978b  mov     rcx, [rcx]; StringUuid
0x18002978e  lea     rdx, [rsp+588h+Uuid]; Uuid
0x180029796  call    cs:__imp_UuidFromStringW
0x18002979d  nop     dword ptr [rax+rax+00h]
0x1800297a2  test    eax, eax
0x1800297a4  jnz     short loc_1800297D3
0x1800297a6  movaps  xmm0, xmmword ptr [rsp+588h+Uuid.Data1]
0x1800297ae  movdqa  xmmword ptr [rsp+588h+Src.Data1], xmm0
0x1800297b7  lea     rdx, [rsp+588h+var_4E4]
0x1800297bf  lea     rcx, [rsp+588h+Src]
0x1800297c7  call    cs:__imp_GetEnrollmentType
0x1800297ce  nop     dword ptr [rax+rax+00h]
0x1800297d3  mov     ebx, [rsp+588h+var_53C]
0x1800297d7  mov     rcx, [rsp+588h+ppvObject]
0x1800297dc  mov     rax, [rcx]
0x1800297df  lea     rdx, [rsp+588h+var_4E8]
  ... truncated ...
```
