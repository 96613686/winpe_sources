# CUiccHandler2::GetKeys(IMVKey * * *,ulong *)

- ea: `0x18002eb90`
- end: `0x18002ff08`
- name: `?GetKeys@CUiccHandler2@@UEAAJPEAPEAPEAUIMVKey@@PEAK@Z`
- size: `4984`
- prototype: `__int64 __fastcall(CUiccHandler2 *this, LPVOID *, unsigned int *)`
- caller_count: `0`
- callee_count: `24`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000108c`
- `0x1800017c4`
- `0x1800076a4`
- `0x1800087b8`
- `0x18000dfb0`
- `0x18000e1f8`
- `0x18000e308`
- `0x180012e18`
- `0x180012e30`
- `0x180013b68`
- `0x180014a6c`
- `0x180015270`
- `0x180015c3c`
- `0x180025ee8`
- `0x18002b040`
- `0x18002b1a0`
- `0x18002b394`
- `0x18002b3e8`
- `0x18002b4e8`
- `0x18002dd18`
- `0x18002eb90`
- `0x18003774c`
- `0x18003b9a0`
- `0x18003f010`

## import_xrefs

- `msvcp110_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18002eef9`
- `msvcp110_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18002eef9`
- `msvcrt!_wcsicmp` at `0x18002ee1d`
- `msvcrt!_wcsicmp` at `0x18002ee4d`
- `msvcrt!_wcsicmp` at `0x18002fb3c`
- `msvcrt!_wcsicmp` at `0x18002fb69`
- `msvcrt!_wcsicmp` at `0x18002ee1d`
- `msvcrt!_wcsicmp` at `0x18002ee4d`
- `msvcrt!_wcsicmp` at `0x18002fb3c`
- `msvcrt!_wcsicmp` at `0x18002fb69`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002eec7`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002eee5`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002ef7c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002ef9a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002f170`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002f23b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002f2cd`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002f3e9`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002f50f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002fc27`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002fc5c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002fc8c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002fcbc`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002fd05`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002fe2b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002eec7`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002eee5`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002ef7c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002ef9a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002f170`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002f23b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002f2cd`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002f3e9`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002f50f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002fc27`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002fc5c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002fc8c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002fcbc`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002fd05`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002fe2b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002f750`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002f750`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fc0d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fc0d`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18002ef28`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18002ef28`

## pseudocode

```c
__int64 __fastcall CUiccHandler2::GetKeys(CUiccHandler2 *this, LPVOID *a2, unsigned int *a3)
{
  __int64 result; // rax
  __int64 *v6; // rax
  unsigned __int64 v7; // rdx
  __int64 v8; // rdi
  __int64 v9; // rbx
  __int64 v10; // r13
  __int64 v11; // r14
  __int64 *v12; // rax
  _DWORD *v13; // rsi
  __int64 **v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 i; // rcx
  __int64 j; // rcx
  __int64 *v19; // rdi
  __int64 *v20; // rbx
  __int64 v21; // rax
  __int64 v22; // r8
  int v23; // eax
  unsigned int v24; // ebx
  const char *v25; // r9
  __int64 *v26; // rax
  HRESULT ClassObject; // eax
  unsigned int v28; // ebx
  __int64 v29; // rcx
  __int64 v30; // r9
  _QWORD *v31; // r8
  __int64 v32; // rax
  __int64 v33; // r8
  __int64 v34; // rcx
  unsigned __int64 v35; // r12
  const WCHAR *v36; // rdi
  const WCHAR **v37; // rbx
  const WCHAR *v38; // r9
  _QWORD *v39; // rax
  __int64 v40; // rax
  __int64 v41; // r8
  __int64 v42; // rcx
  void **v43; // r9
  _QWORD *v44; // rax
  __int64 v45; // rax
  __int64 v46; // r8
  __int64 v47; // rcx
  void **v48; // r9
  _QWORD *v49; // rax
  __int64 v50; // rax
  __int64 v51; // r8
  __int64 v52; // rcx
  void **v53; // rdx
  __int64 v54; // r15
  void **v55; // r9
  _QWORD *v56; // rax
  __int64 v57; // rax
  __int64 v58; // r8
  __int64 v59; // rcx
  void **v60; // rdx
  void **v61; // r9
  _QWORD *v62; // rax
  __int64 v63; // rax
  __int64 v64; // r8
  __int64 v65; // rcx
  int v66; // r14d
  void **v67; // rdx
  void **v68; // r9
  _QWORD *v69; // rax
  __int64 v70; // rax
  __int64 v71; // r8
  __int64 v72; // rcx
  _QWORD *v73; // rax
  __int64 v74; // rax
  __int64 v75; // r8
  __int64 v76; // rcx
  unsigned __int64 v77; // r8
  __int64 v78; // rcx
  _QWORD *v79; // rbx
  _QWORD *v80; // rdi
  void **v81; // r9
  _QWORD *v82; // r8
  __int64 v83; // rax
  __int64 v84; // r8
  __int64 v85; // rcx
  unsigned __int16 *v86; // rbx
  LSTATUS ValueW; // eax
  int v88; // r10d
  __int64 v89; // rdi
  void **v90; // rdx
  void **v91; // r8
  void **v92; // r9
  void **v93; // r11
  void *v94; // r12
  __int64 v95; // rbx
  __int64 v96; // rax
  const WCHAR *v97; // rcx
  __int64 v98; // rax
  int v99; // eax
  __int64 v100; // rax
  int v101; // eax
  __int64 v102; // rax
  int v103; // eax
  __int64 v104; // rax
  int v105; // eax
  __m128i v106; // xmm6
  unsigned int v107; // r13d
  const unsigned __int16 near *const *v108; // r14
  __int64 *v109; // rax
  _QWORD *v110; // r15
  __int64 v111; // rbx
  __int64 *v112; // rdi
  unsigned int v113; // ebx
  bool v114; // sf
  int v115; // eax
  unsigned int v116; // r12d
  unsigned int v117; // edi
  __int64 v118; // rcx
  __int64 v119; // rcx
  __int64 v120; // rdx
  const unsigned __int16 *v121; // rdx
  __int64 v122; // rcx
  __int64 v123; // rax
  __int64 v124; // rdx
  __int64 v125; // rdx
  __int64 v126; // rdx
  __int64 v127; // rdx
  __int64 v128; // rcx
  __int64 v129; // rdx
  void **v130; // rax
  char *v131; // rdx
  void **v132; // rax
  __int64 v133; // rdx
  int ppv; // [rsp+20h] [rbp-2E8h]
  int ppva; // [rsp+20h] [rbp-2E8h]
  int ppvb; // [rsp+20h] [rbp-2E8h]
  char v137; // [rsp+40h] [rbp-2C8h] BYREF
  __int64 *v138; // [rsp+48h] [rbp-2C0h] BYREF
  __int64 *v139; // [rsp+50h] [rbp-2B8h]
  __int64 v140; // [rsp+58h] [rbp-2B0h] BYREF
  DWORD pcbData[4]; // [rsp+60h] [rbp-2A8h] BYREF
  LPVOID pv[2]; // [rsp+70h] [rbp-298h] BYREF
  __int64 pvData; // [rsp+80h] [rbp-288h] BYREF
  const WCHAR *v144; // [rsp+88h] [rbp-280h] BYREF
  __int64 v145; // [rsp+90h] [rbp-278h] BYREF
  __int16 v146; // [rsp+98h] [rbp-270h] BYREF
  unsigned __int16 *v147; // [rsp+A0h] [rbp-268h] BYREF
  __int64 v148; // [rsp+A8h] [rbp-260h] BYREF
  __int64 v149; // [rsp+B0h] [rbp-258h] BYREF
  __int64 v150; // [rsp+B8h] [rbp-250h] BYREF
  unsigned int *v151; // [rsp+C0h] [rbp-248h]
  LPVOID *v152; // [rsp+C8h] [rbp-240h]
  void *v153[2]; // [rsp+D0h] [rbp-238h] BYREF
  __int64 v154; // [rsp+E0h] [rbp-228h]
  unsigned __int64 v155; // [rsp+E8h] [rbp-220h]
  void *v156[2]; // [rsp+F0h] [rbp-218h] BYREF
  __int64 v157; // [rsp+100h] [rbp-208h]
  unsigned __int64 v158; // [rsp+108h] [rbp-200h]
  void *v159[2]; // [rsp+110h] [rbp-1F8h] BYREF
  __int64 v160; // [rsp+120h] [rbp-1E8h]
  unsigned __int64 v161; // [rsp+128h] [rbp-1E0h]
  void *v162[2]; // [rsp+130h] [rbp-1D8h] BYREF
  __int64 v163; // [rsp+140h] [rbp-1C8h]
  unsigned __int64 v164; // [rsp+148h] [rbp-1C0h]
  void *v165[2]; // [rsp+150h] [rbp-1B8h] BYREF
  __int64 v166; // [rsp+160h] [rbp-1A8h]
  unsigned __int64 v167; // [rsp+168h] [rbp-1A0h]
  void *v168[2]; // [rsp+170h] [rbp-198h] BYREF
  __int64 v169; // [rsp+180h] [rbp-188h]
  unsigned __int64 v170; // [rsp+188h] [rbp-180h]
  unsigned __int16 *v171[3]; // [rsp+190h] [rbp-178h] BYREF
  unsigned __int64 v172; // [rsp+1A8h] [rbp-160h]
  char v173[32]; // [rsp+1B0h] [rbp-158h] BYREF
  char *v174; // [rsp+1D0h] [rbp-138h]
  __int64 v175; // [rsp+1D8h] [rbp-130h]
  const WCHAR *v176; // [rsp+1E0h] [rbp-128h]
  int v177; // [rsp+1E8h] [rbp-120h]
  int v178; // [rsp+1ECh] [rbp-11Ch]
  __int64 *p_pvData; // [rsp+1F0h] [rbp-118h]
  __int64 v180; // [rsp+1F8h] [rbp-110h]
  DWORD *v181; // [rsp+200h] [rbp-108h]
  __int64 v182; // [rsp+208h] [rbp-100h]
  __int16 *v183; // [rsp+210h] [rbp-F8h]
  __int64 v184; // [rsp+218h] [rbp-F0h]
  __int64 v185; // [rsp+220h] [rbp-E8h]
  __int64 v186; // [rsp+228h] [rbp-E0h]
  LPVOID *v187; // [rsp+230h] [rbp-D8h]
  __int64 v188; // [rsp+238h] [rbp-D0h]
  void *v189; // [rsp+240h] [rbp-C8h]
  __int64 v190; // [rsp+248h] [rbp-C0h]
  const WCHAR **v191; // [rsp+250h] [rbp-B8h]
  __int64 v192; // [rsp+258h] [rbp-B0h]
  void **v193; // [rsp+260h] [rbp-A8h]
  int v194; // [rsp+268h] [rbp-A0h]
  int v195; // [rsp+26Ch] [rbp-9Ch]
  void **v196; // [rsp+270h] [rbp-98h]
  int v197; // [rsp+278h] [rbp-90h]
  int v198; // [rsp+27Ch] [rbp-8Ch]
  void **v199; // [rsp+280h] [rbp-88h]
  int v200; // [rsp+288h] [rbp-80h]
  int v201; // [rsp+28Ch] [rbp-7Ch]
  void **v202; // [rsp+290h] [rbp-78h]
  int v203; // [rsp+298h] [rbp-70h]
  int v204; // [rsp+29Ch] [rbp-6Ch]
  __int64 *v205; // [rsp+2A0h] [rbp-68h]
  __int64 v206; // [rsp+2A8h] [rbp-60h]
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+0h]

  v151 = a3;
  v152 = a2;
  v147 = (unsigned __int16 *)this;
  if ( (unsigned int)dword_180052170 > 4 )
  {
    v144 = L"UICCHandler2";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)&dword_180052170,
      (__int64)&word_1800494B6,
      0,
      0,
      &v144);
    a3 = v151;
  }
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD1,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\uicchandler2.cpp",
      (const char *)0x80004003LL,
      ppv);
    return 2147500035LL;
  }
  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD2,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\uicchandler2.cpp",
      (const char *)0x80004003LL,
      ppv);
    return 2147500035LL;
  }
  try
  {
    v6 = (__int64 *)*((_QWORD *)this + 6);
    v7 = *((unsigned int *)this + 7);
    v8 = *v6;
    v148 = v8;
    if ( 0xAAAAAAAAAAAAAAABuLL * ((v6[1] - v8) >> 4) <= v7 )
      std::vector<UiccKeySet>::_Xran();
    v9 = 48 * v7;
    pvData = 48 * v7;
    v10 = *(_QWORD *)(48 * v7 + v8);
    v11 = *(unsigned int *)(48 * v7 + v8 + 40);
    v144 = *(const WCHAR **)(v10 + 56);
    v172 = 7;
    v171[2] = 0;
    LOWORD(v171[0]) = 0;
    std::wstring::assign(v171, (char *)L"UICCHandler2", 0xCu);
    v139 = 0;
    std::_Tree_alloc<0,std::_Tree_base_types<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>>>::_Buyheadnode();
    v138 = v12;
    v13 = *(_DWORD **)(v9 + v8 + 24);
    if ( v13 )
    {
      if ( *((_DWORD *)this + 6) != 18 && v13[4] )
      {
        std::wstring::assign(v171, (char *)L"Selected Profile Keys", 0x15u);
        v14 = *(__int64 ***)(v9 + v8 + 24);
        if ( &v138 != v14 )
        {
          std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::clear(&v138);
          v15 = std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::_Copy_nodes<std::integral_constant<bool,0>>(
                  (__int64 *)&v138,
                  (*v14)[1],
                  (__int64)v138,
                  v137);
          v138[1] = v15;
          v139 = v14[1];
          v16 = v138[1];
          if ( *(_BYTE *)(v16 + 25) )
          {
            *v138 = (__int64)v138;
            v138[2] = (__int64)v138;
          }
          else
          {
            for ( i = *(_QWORD *)v16; !*(_BYTE *)(i + 25); i = *(_QWORD *)i )
              v16 = i;
            *v138 = v16;
            for ( j = v138[1]; !*(_BYTE *)(*(_QWORD *)(j + 16) + 25LL); j = *(_QWORD *)(j + 16) )
              ;
            v138[2] = j;
          }
        }
LABEL_28:
        v23 = MvSetUIStatus(this, 3);
        v24 = v23;
        if ( v23 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xED,
            (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\uicchandler2.cpp",
            (const char *)(unsigned int)v23,
            ppv);
          std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::clear(&v138);
          operator delete(v138);
          if ( v172 >= 8 )
            operator delete(v171[0]);
          return v24;
        }
        goto LABEL_33;
      }
      v19 = *(__int64 **)v13;
      v20 = *(__int64 **)(*(_QWORD *)v13 + 8LL);
      while ( !*((_BYTE *)v20 + 25) )
      {
        if ( _wcsicmp((const wchar_t *)v20[4], L"uiname") >= 0 )
        {
          v19 = v20;
          v20 = (__int64 *)*v20;
        }
        else
        {
          v20 = (__int64 *)v20[2];
        }
      }
      if ( v19 != *(__int64 **)v13 && _wcsicmp(L"uiname", (const wchar_t *)v19[4]) >= 0 )
      {
        v21 = std::_Tree_buy<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>>::_Buynode<unsigned short const (&)[7],Microsoft::WRL::ComPtr<IMVKey> const &>(
                (__int64)&v138,
                (__int64)L"uiname",
                v19 + 5);
        std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::_Insert_nohint<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>> &,std::_Tree_node<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>,void *> *>(
          &v138,
          (__int64)pv,
          v22,
          (const wchar_t **)(v21 + 32),
          (_QWORD *)v21);
        goto LABEL_28;
      }
      std::_Xout_of_range("invalid map<K, T> key");
    }
LABEL_33:
    v140 = 0;
    v26 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IClassFactory>>(&v140);
    ClassObject = CoGetClassObject(
                    &GUID_38be0989_9830_49a8_985b_7741219fd0fb,
                    1u,
                    0,
                    &GUID_00000001_0000_0000_c000_000000000046,
                    (LPVOID *)v26);
    v28 = ClassObject;
    if ( ClassObject < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF3,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\uicchandler2.cpp",
        (const char *)(unsigned int)ClassObject,
        ppva);
      v29 = v140;
      if ( v140 )
      {
        v140 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      }
      std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::clear(&v138);
      operator delete(v138);
      if ( v172 >= 8 )
        operator delete(v171[0]);
      return v28;
    }
    if ( *(_QWORD *)(v10 + 24) < 8u )
      v30 = v10;
    else
      v30 = *(_QWORD *)v10;
    v31 = CreateKey(pcbData, &v140, (__int64)L"ICCID", v30);
    v32 = std::_Tree_buy<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>>::_Buynode<unsigned short const (&)[10],Microsoft::WRL::ComPtr<IMVKey>>(
            (__int64)&v138,
            (__int64)L"ICCID",
            v31);
    std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::_Insert_nohint<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>> &,std::_Tree_node<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>,void *> *>(
      &v138,
      (__int64)pv,
      v33,
      (const wchar_t **)(v32 + 32),
      (_QWORD *)v32);
    v34 = *(_QWORD *)pcbData;
    if ( *(_QWORD *)pcbData )
    {
      *(_QWORD *)pcbData = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    }
    v35 = 48 * v11;
    v36 = v144;
    v37 = (const WCHAR **)&v144[48 * v11 + 16];
    pv[0] = v37;
    if ( (unsigned __int64)v37[3] < 8 )
      v38 = &v144[48 * v11 + 16];
    else
      v38 = *v37;
    v39 = CreateKey(pcbData, &v140, (__int64)L"IMSI", (__int64)v38);
    v40 = std::_Tree_buy<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>>::_Buynode<unsigned short const (&)[10],Microsoft::WRL::ComPtr<IMVKey>>(
            (__int64)&v138,
            (__int64)L"IMSI",
            v39);
    std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::_Insert_nohint<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>> &,std::_Tree_node<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>,void *> *>(
      &v138,
      (__int64)&v145,
      v41,
      (const wchar_t **)(v40 + 32),
      (_QWORD *)v40);
    v42 = *(_QWORD *)pcbData;
    if ( *(_QWORD *)pcbData )
    {
      *(_QWORD *)pcbData = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    }
    v155 = 7;
    v154 = 0;
    LOWORD(v153[0]) = 0;
    std::wstring::assign(v153, (void **)v37, 0, 3u);
    v43 = v153;
    if ( v155 >= 8 )
      v43 = (void **)v153[0];
    v44 = CreateKey(pcbData, &v140, (__int64)L"MCC", (__int64)v43);
    v45 = std::_Tree_buy<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>>::_Buynode<unsigned short const (&)[10],Microsoft::WRL::ComPtr<IMVKey>>(
            (__int64)&v138,
            (__int64)L"MCC",
            v44);
    std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::_Insert_nohint<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>> &,std::_Tree_node<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>,void *> *>(
      &v138,
      (__int64)&v145,
      v46,
      (const wchar_t **)(v45 + 32),
      (_QWORD *)v45);
    v47 = *(_QWORD *)pcbData;
    if ( *(_QWORD *)pcbData )
    {
      *(_QWORD *)pcbData = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    }
    if ( v155 >= 8 )
      operator delete(v153[0]);
    v155 = 7;
    v154 = 0;
    LOWORD(v153[0]) = 0;
    std::wstring::assign(v153, (void **)v37, 3u, *(_QWORD *)&v36[v35 + 44]);
    v48 = v153;
    if ( v155 >= 8 )
      v48 = (void **)v153[0];
    v49 = CreateKey(pcbData, &v140, (__int64)L"MNC", (__int64)v48);
    v50 = std::_Tree_buy<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>>::_Buynode<unsigned short const (&)[10],Microsoft::WRL::ComPtr<IMVKey>>(
            (__int64)&v138,
            (__int64)L"MNC",
            v49);
    std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::_Insert_nohint<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>> &,std::_Tree_node<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>,void *> *>(
      &v138,
      (__int64)&v145,
      v51,
      (const wchar_t **)(v50 + 32),
      (_QWORD *)v50);
    v52 = *(_QWORD *)pcbData;
    if ( *(_QWORD *)pcbData )
    {
      *(_QWORD *)pcbData = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
    }
    if ( v155 >= 8 )
      operator delete(v153[0]);
    v161 = 7;
    v160 = 0;
    LOWORD(v159[0]) = 0;
    std::wstring::assign(v159, (char *)&Src, 0);
    v53 = v159;
    if ( *(_QWORD *)&v36[v35 + 32] )
      v53 = *(void ***)&v36[v35 + 32];
    v170 = 7;
    v169 = 0;
    LOWORD(v168[0]) = 0;
    v54 = -1;
    std::wstring::assign(v168, v53, 0, 0xFFFFFFFFFFFFFFFFuLL);
    if ( v161 >= 8 )
      operator delete(v159[0]);
    v161 = 7;
    v160 = 0;
    LOWORD(v159[0]) = 0;
    v55 = v168;
    if ( v170 >= 8 )
      v55 = (void **)v168[0];
    v56 = CreateKey(pcbData, &v140, (__int64)L"SPN", (__int64)v55);
    v57 = std::_Tree_buy<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>>::_Buynode<unsigned short const (&)[10],Microsoft::WRL::ComPtr<IMVKey>>(
            (__int64)&v138,
            (__int64)L"SPN",
            v56);
    std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::_Insert_nohint<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>> &,std::_Tree_node<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>,void *> *>(
      &v138,
      (__int64)&v145,
      v58,
      (const wchar_t **)(v57 + 32),
      (_QWORD *)v57);
    v59 = *(_QWORD *)pcbData;
    if ( *(_QWORD *)pcbData )
    {
      *(_QWORD *)pcbData = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
    }
    v155 = 7;
    v154 = 0;
    LOWORD(v153[0]) = 0;
    std::wstring::assign(v153, (char *)&Src, 0);
    v60 = v153;
    if ( *(_QWORD *)&v36[v35 + 36] )
      v60 = *(void ***)&v36[v35 + 36];
    v167 = 7;
    v166 = 0;
    LOWORD(v165[0]) = 0;
    std::wstring::assign(v165, v60, 0, 0xFFFFFFFFFFFFFFFFuLL);
    if ( v155 >= 8 )
      operator delete(v153[0]);
    v155 = 7;
    v154 = 0;
    LOWORD(v153[0]) = 0;
    v61 = v165;
    if ( v167 >= 8 )
      v61 = (void **)v165[0];
    v62 = CreateKey(pcbData, &v140, (__int64)L"PNN", (__int64)v61);
    v63 = std::_Tree_buy<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>>::_Buynode<unsigned short const (&)[10],Microsoft::WRL::ComPtr<IMVKey>>(
            (__int64)&v138,
            (__int64)L"PNN",
            v62);
    std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::_Insert_nohint<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>> &,std::_Tree_node<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>,void *> *>(
      &v138,
      (__int64)&v145,
      v64,
      (const wchar_t **)(v63 + 32),
      (_QWORD *)v63);
    v65 = *(_QWORD *)pcbData;
    if ( *(_QWORD *)pcbData )
    {
      *(_QWORD *)pcbData = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
    }
    v161 = 7;
    v160 = 0;
    LOWORD(v159[0]) = 0;
    v66 = 2;
    std::wstring::assign(v159, (char *)L"FF", 2u);
    v67 = v159;
    if ( *(_QWORD *)&v36[v35 + 40] )
      v67 = *(void ***)&v36[v35 + 40];
    v164 = 7;
    v163 = 0;
    LOWORD(v162[0]) = 0;
    std::wstring::assign(v162, v67, 0, 0xFFFFFFFFFFFFFFFFuLL);
    if ( v161 >= 8 )
      operator delete(v159[0]);
    v161 = 7;
    v160 = 0;
    LOWORD(v159[0]) = 0;
    v68 = v162;
    if ( v164 >= 8 )
      v68 = (void **)v162[0];
    v69 = CreateKey(&v149, &v140, (__int64)L"GID1", (__int64)v68);
    v70 = std::_Tree_buy<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>>::_Buynode<unsigned short const (&)[10],Microsoft::WRL::ComPtr<IMVKey>>(
            (__int64)&v138,
            (__int64)L"GID1",
            v69);
    std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::_Insert_nohint<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>> &,std::_Tree_node<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>,void *> *>(
      &v138,
      (__int64)&v145,
      v71,
      (const wchar_t **)(v70 + 32),
      (_QWORD *)v70);
    v72 = v149;
    if ( v149 )
    {
      v149 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
    }
    if ( *(_BYTE *)(v10 + 105) )
    {
      v73 = CreateKey(&v150, &v140, (__int64)L"ESIM_PROV", (__int64)L"1");
      v74 = std::_Tree_buy<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>>::_Buynode<unsigned short const (&)[10],Microsoft::WRL::ComPtr<IMVKey>>(
              (__int64)&v138,
              (__int64)L"ESIM_PROV",
              v73);
      std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::_Insert_nohint<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>> &,std::_Tree_node<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>,void *> *>(
        &v138,
        (__int64)&v145,
        v75,
        (const wchar_t **)(v74 + 32),
        (_QWORD *)v74);
      v76 = v150;
      if ( v150 )
      {
        v150 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
      }
    }
    v77 = 7;
    v158 = 7;
    v78 = 0;
    v157 = 0;
    LOWORD(v156[0]) = 0;
    v79 = *(_QWORD **)(v10 + 32);
    v80 = *(_QWORD **)(v10 + 40);
    while ( v79 != v80 )
    {
      if ( v78 )
      {
        v130 = v156;
        if ( v77 >= 8 )
          v130 = (void **)v156[0];
        v131 = (char *)v130 + 2 * v78;
        v132 = v156;
        if ( v77 >= 8 )
          v132 = (void **)v156[0];
        if ( v131 )
          v133 = (v131 - (char *)v132) >> 1;
        else
          v133 = 0;
        std::wstring::insert(v156, v133, 1);
      }
      std::wstring::append(v156, v79, 0, 0xFFFFFFFFFFFFFFFFuLL);
      v79 += 4;
      v77 = v158;
      v78 = v157;
    }
    if ( v78 )
    {
      v81 = v156;
      if ( v77 >= 8 )
        v81 = (void **)v156[0];
      v82 = CreateKey(&v145, &v140, (__int64)L"LANG", (__int64)v81);
      v83 = std::_Tree_buy<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>>::_Buynode<unsigned short const (&)[10],Microsoft::WRL::ComPtr<IMVKey>>(
              (__int64)&v138,
              (__int64)L"LANG",
              v82);
      std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::_Insert_nohint<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>> &,std::_Tree_node<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>,void *> *>(
        &v138,
        (__int64)pcbData,
        v84,
        (const wchar_t **)(v83 + 32),
        (_QWORD *)v83);
      v85 = v145;
      if ( v145 )
      {
        v145 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
      }
    }
    if ( *(_BYTE *)(pvData + v148 + 16) )
    {
      v86 = v147;
      if ( *((_QWORD *)v147 + 10) )
      {
        LODWORD(pvData) = 0;
        pcbData[0] = 4;
        ValueW = RegGetValueW(
                   HKEY_LOCAL_MACHINE,
                   gc_wszRegMultivariantStatus,
                   L"OneTimeProvisioning",
                   0x18u,
                   0,
                   &pvData,
                   pcbData);
        if ( !ValueW || (v88 = 0, ValueW == 2) )
          v88 = pvData;
        v89 = *((_QWORD *)v86 + 10);
        if ( (unsigned int)dword_180052170 > 4
          && (qword_180052180 & 0x400000000000LL) != 0
          && (qword_180052188 & 0x400000000000LL) == qword_180052188 )
        {
          v148 = 0x2000000;
          v90 = v156;
          if ( v158 >= 8 )
            v90 = (void **)v156[0];
          v91 = v162;
          if ( v164 >= 8 )
            v91 = (void **)v162[0];
          v92 = v165;
          if ( v167 >= 8 )
            v92 = (void **)v165[0];
          v93 = v168;
          if ( v170 >= 8 )
            v93 = (void **)v168[0];
          v144 = *(const WCHAR **)&v144[v35 + 44];
          v94 = pv[0];
          if ( *((_QWORD *)pv[0] + 3) >= 8u )
            v94 = *(void **)pv[0];
          pv[0] = v94;
          LOWORD(pv[1]) = 18;
          if ( *(_QWORD *)(v10 + 24) < 8u )
            v95 = v10;
          else
            v95 = *(_QWORD *)v10;
          v145 = v95;
          v146 = 16;
          pcbData[0] = *((_DWORD *)v147 + 7);
          LODWORD(pvData) = *(_DWORD *)(v10 + 96);
          v96 = *(_QWORD *)(v10 + 80);
          if ( *(_QWORD *)(v96 + 24) < 8u )
            v96 = v10 + 80;
          v97 = *(const WCHAR **)v96;
          v137 = v88 == 0;
          v205 = &v148;
          v206 = 8;
          if ( v90 )
          {
            v98 = -1;
            do
              ++v98;
            while ( *((_WORD *)v90 + v98) );
            v99 = 2 * v98 + 2;
          }
          else
          {
            v90 = (void **)&Src;
            v99 = 2;
          }
          v202 = v90;
          v203 = v99;
          v204 = 0;
          if ( v91 )
          {
            v100 = -1;
            do
              ++v100;
            while ( *((_WORD *)v91 + v100) );
            v101 = 2 * v100 + 2;
          }
          else
          {
            v91 = (void **)&Src;
            v101 = 2;
          }
          v199 = v91;
          v200 = v101;
          v201 = 0;
          if ( v92 )
          {
            v102 = -1;
            do
              ++v102;
            while ( *((_WORD *)v92 + v102) );
            v103 = 2 * v102 + 2;
          }
          else
          {
            v92 = (void **)&Src;
            v103 = 2;
          }
          v196 = v92;
          v197 = v103;
          v198 = 0;
          if ( v93 )
          {
            v104 = -1;
            do
              ++v104;
            while ( *((_WORD *)v93 + v104) );
            v105 = 2 * v104 + 2;
          }
          else
          {
            v93 = (void **)&Src;
            v105 = 2;
          }
          v193 = v93;
          v194 = v105;
          v195 = 0;
          v191 = &v144;
          v192 = 8;
          v187 = &pv[1];
          v188 = 2;
          v189 = v94;
          v190 = 18;
          v183 = &v146;
          v184 = 2;
          v185 = v95;
          v186 = 16;
          v181 = pcbData;
          v182 = 4;
          p_pvData = &pvData;
          v180 = 4;
          if ( v97 )
          {
            do
              ++v54;
            while ( v97[v54] );
            v66 = 2 * v54 + 2;
          }
          else
          {
            v97 = &Src;
          }
          v176 = v97;
          v177 = v66;
          v178 = 0;
          v174 = &v137;
          v175 = 1;
          tlgWriteTransfer_EventWriteTransfer(&dword_180052170, qword_1800499F8, v89 + 8, 0, 16, v173);
        }
      }
    }
    pv[0] = 0;
    LODWORD(pv[1]) = 0;
    co_array_t<IMVKey *>::allocate((__int64)pv, (unsigned __int64)v139);
    v106 = *(__m128i *)pv;
    v107 = 0;
    v108 = off_180040F00;
    v109 = v138;
    v110 = pv[0];
    while ( 1 )
    {
      if ( v108 == &off_180040F50 )
      {
        co_array_t<IMVKey *>::allocate((__int64)pv, v107);
        *v152 = pv[0];
        *v151 = (unsigned int)pv[1];
        pv[0] = 0;
        LODWORD(pv[1]) = 0;
        __1__unique_struct_U__co_array_t_PEAUIMVKey____P6AXPEAU1___E_1_FreeMvKeyArray__YAX0_Z__T_0A__wil__QEAA_XZ((__int64)pv);
        LOBYTE(v124) = 1;
        std::wstring::_Tidy(v156, v124, 0);
        LOBYTE(v125) = 1;
        std::wstring::_Tidy(v162, v125, 0);
        LOBYTE(v126) = 1;
        std::wstring::_Tidy(v165, v126, 0);
        LOBYTE(v127) = 1;
        std::wstring::_Tidy(v168, v127, 0);
        v128 = v140;
        if ( v140 )
        {
          v140 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v128 + 16LL))(v128);
        }
        std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::clear(&v138);
        operator delete(v138);
        LOBYTE(v129) = 1;
        std::wstring::_Tidy(v171, v129, 0);
        return 0;
      }
      v111 = v109[1];
      v112 = v109;
      if ( !*(_BYTE *)(v111 + 25) )
      {
        do
        {
          if ( _wcsicmp(*(const wchar_t **)(v111 + 32), *v108) >= 0 )
          {
            v112 = (__int64 *)v111;
            v111 = *(_QWORD *)v111;
          }
          else
          {
            v111 = *(_QWORD *)(v111 + 16);
          }
        }
        while ( !*(_BYTE *)(v111 + 25) );
        v109 = v138;
      }
      if ( v112 == v109 )
      {
        v113 = 0;
      }
      else
      {
        v113 = 0;
        v114 = _wcsicmp(*v108, (const wchar_t *)v112[4]) < 0;
        v109 = v138;
        if ( !v114 )
          goto LABEL_156;
      }
      v112 = v109;
LABEL_156:
      if ( v109 != v112 )
      {
        v147 = 0;
        v115 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v112[5] + 48LL))(v112[5], &v147);
        v116 = v115;
        if ( v115 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x13F,
            (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\uicchandler2.cpp",
            (const char *)(unsigned int)v115,
            ppvb);
          if ( v106.m128i_i64[0] )
          {
            v117 = _mm_cvtsi128_si32(_mm_srli_si128(v106, 8));
            if ( v117 )
            {
              do
              {
                v118 = v110[v113];
                if ( v118 )
                {
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v118 + 16LL))(v118);
                  v110[v113] = 0;
                }
                ++v113;
              }
              while ( v113 < v117 );
            }
            CoTaskMemFree(v110);
          }
          if ( v158 >= 8 )
            operator delete(v156[0]);
          v158 = 7;
          v157 = 0;
          LOWORD(v156[0]) = 0;
          if ( v164 >= 8 )
            operator delete(v162[0]);
          v164 = 7;
          v163 = 0;
          LOWORD(v162[0]) = 0;
          if ( v167 >= 8 )
            operator delete(v165[0]);
          v167 = 7;
          v166 = 0;
          LOWORD(v165[0]) = 0;
          if ( v170 >= 8 )
            operator delete(v168[0]);
          v170 = 7;
          v169 = 0;
          LOWORD(v168[0]) = 0;
          v119 = v140;
          if ( v140 )
          {
            v140 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v119 + 16LL))(v119);
          }
          std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::clear(&v138);
          operator delete(v138);
          LOBYTE(v120) = 1;
          std::wstring::_Tidy(v171, v120, 0);
          return v116;
        }
        v121 = (const unsigned __int16 *)v171;
        if ( v172 >= 8 )
          v121 = v171[0];
        LogHandlerKeysReturned(L"UICCHandler2", v121, *v108, v147);
        v122 = v112[5];
        v112[5] = 0;
        v123 = v107++;
        *(_QWORD *)(v106.m128i_i64[0] + 8 * v123) = v122;
        v109 = v138;
      }
      ++v108;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x149,
                           (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\uicchandler2.cpp",
                           v25);
  }
  return result;
}

```

## disassembly

```asm
0x18002eb90  mov     r11, rsp
0x18002eb93  push    rbx
0x18002eb94  push    rsi
0x18002eb95  push    rdi
0x18002eb96  push    r12
0x18002eb98  push    r13
0x18002eb9a  push    r14
0x18002eb9c  push    r15
0x18002eb9e  sub     rsp, 2D0h
0x18002eba5  movaps  xmmword ptr [r11-48h], xmm6
0x18002ebaa  mov     rax, cs:__security_cookie
0x18002ebb1  xor     rax, rsp
0x18002ebb4  mov     [rsp+308h+var_58], rax
0x18002ebbc  mov     [rsp+308h+var_248], r8
0x18002ebc4  mov     rbx, rdx
0x18002ebc7  mov     [rsp+308h+var_240], rdx
0x18002ebcf  mov     r15, rcx
0x18002ebd2  mov     [rsp+308h+var_268], rcx
0x18002ebda  xor     r12d, r12d
0x18002ebdd  mov     eax, cs:dword_180052170
0x18002ebe3  cmp     eax, 4
0x18002ebe6  jbe     short loc_18002EC25
0x18002ebe8  lea     rsi, ?c_uiccHandler2@@3QBGB; "UICCHandler2"
0x18002ebef  mov     [r11-280h], rsi
0x18002ebf6  lea     rax, [r11-280h]
0x18002ebfd  mov     [rsp+308h+ppv], rax
0x18002ec02  xor     r9d, r9d
0x18002ec05  xor     r8d, r8d
0x18002ec08  lea     rdx, word_1800494B6
0x18002ec0f  lea     rcx, dword_180052170
0x18002ec16  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18002ec1b  mov     r8, [rsp+308h+var_248]
0x18002ec23  jmp     short loc_18002EC2C
0x18002ec25  lea     rsi, ?c_uiccHandler2@@3QBGB; "UICCHandler2"
0x18002ec2c  test    rbx, rbx
0x18002ec2f  jnz     short loc_18002EC59
0x18002ec31  mov     rcx, [rsp+308h]; this
0x18002ec39  mov     ebx, 80004003h
0x18002ec3e  mov     r9d, ebx; char *
0x18002ec41  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002ec48  mov     edx, 0D1h; void *
0x18002ec4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ec52  mov     eax, ebx
0x18002ec54  jmp     loc_18002FED6
0x18002ec59  test    r8, r8
0x18002ec5c  jnz     short loc_18002EC86
0x18002ec5e  mov     rcx, [rsp+308h]; this
0x18002ec66  mov     ebx, 80004003h
0x18002ec6b  mov     r9d, ebx; char *
0x18002ec6e  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002ec75  mov     edx, 0D2h; void *
0x18002ec7a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ec7f  mov     eax, ebx
0x18002ec81  jmp     loc_18002FED6
0x18002ec86  mov     rax, [r15+30h]
0x18002ec8a  mov     edx, [r15+1Ch]
0x18002ec8e  mov     rdi, [rax]
0x18002ec91  mov     [rsp+308h+var_260], rdi
0x18002ec99  mov     rcx, [rax+8]
0x18002ec9d  sub     rcx, rdi
0x18002eca0  sar     rcx, 4
0x18002eca4  mov     rax, 0AAAAAAAAAAAAAAABh
0x18002ecae  imul    rcx, rax
0x18002ecb2  cmp     rcx, rdx
0x18002ecb5  jbe     loc_18002FF01
0x18002ecbb  lea     rbx, [rdx+rdx*2]
0x18002ecbf  shl     rbx, 4
0x18002ecc3  mov     [rsp+308h+var_288], rbx
0x18002eccb  mov     r13, [rbx+rdi]
0x18002eccf  mov     r14d, [rbx+rdi+28h]
0x18002ecd4  mov     rax, [r13+38h]
0x18002ecd8  mov     [rsp+308h+var_280], rax
0x18002ece0  mov     [rsp+308h+var_160], 7
0x18002ecec  mov     [rsp+308h+var_168], r12
0x18002ecf4  mov     word ptr [rsp+308h+var_178], r12w
0x18002ecfd  mov     r8d, 0Ch
0x18002ed03  mov     rdx, rsi; Src
0x18002ed06  lea     rcx, [rsp+308h+var_178]; void *
0x18002ed0e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18002ed13  nop
0x18002ed14  mov     [rsp+308h+var_2C0], r12
0x18002ed19  mov     [rsp+308h+var_2B8], r12
0x18002ed1e  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@V?$allocator@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>>>::_Buyheadnode(void)
0x18002ed23  mov     [rsp+308h+var_2C0], rax
0x18002ed28  mov     rsi, [rbx+rdi+18h]
0x18002ed2d  test    rsi, rsi
0x18002ed30  jz      loc_18002EEFF
0x18002ed36  cmp     dword ptr [r15+18h], 12h
0x18002ed3b  jz      loc_18002EE09
0x18002ed41  cmp     [rsi+10h], r12d
0x18002ed45  jz      loc_18002EE09
0x18002ed4b  mov     r8d, 15h
0x18002ed51  lea     rdx, aSelectedProfil; "Selected Profile Keys"
0x18002ed58  lea     rcx, [rsp+308h+var_178]; void *
0x18002ed60  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18002ed65  mov     rbx, [rbx+rdi+18h]
0x18002ed6a  lea     rax, [rsp+308h+var_2C0]
0x18002ed6f  cmp     rax, rbx
0x18002ed72  jz      loc_18002EE88
0x18002ed78  lea     rcx, [rsp+308h+var_2C0]
0x18002ed7d  call    ?clear@?$_Tree@V?$_Tmap_traits@PEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@Ukeyname_less@@V?$allocator@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@@std@@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::clear(void)
0x18002ed82  mov     rdx, [rbx]
0x18002ed85  mov     r9b, [rsp+308h+var_2C8]
0x18002ed8a  mov     r8, [rsp+308h+var_2C0]
0x18002ed8f  mov     rdx, [rdx+8]
0x18002ed93  lea     rcx, [rsp+308h+var_2C0]
0x18002ed98  call    ??$_Copy_nodes@U?$integral_constant@_N$0A@@std@@@?$_Tree@V?$_Tmap_traits@PEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@Ukeyname_less@@V?$allocator@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEAAPEAU?$_Tree_node@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@PEAX@1@PEAU21@0U?$integral_constant@_N$0A@@1@@Z; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::_Copy_nodes<std::integral_constant<bool,0>>(std::_Tree_node<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>,void *> *,std::_Tree_node<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>,void *> *,std::integral_constant<bool,0>)
0x18002ed9d  mov     rcx, [rsp+308h+var_2C0]
0x18002eda2  mov     [rcx+8], rax
0x18002eda6  mov     rax, [rbx+8]
0x18002edaa  mov     [rsp+308h+var_2B8], rax
0x18002edaf  mov     r8, [rsp+308h+var_2C0]
0x18002edb4  mov     rdx, [r8+8]
0x18002edb8  cmp     [rdx+19h], r12b
0x18002edbc  jnz     short loc_18002EDFB
0x18002edbe  mov     rcx, [rdx]
0x18002edc1  cmp     [rcx+19h], r12b
0x18002edc5  jnz     short loc_18002EDD6
0x18002edc7  mov     rdx, rcx
0x18002edca  mov     rax, [rcx]
0x18002edcd  mov     rcx, rax
0x18002edd0  cmp     [rax+19h], r12b
0x18002edd4  jz      short loc_18002EDC7
0x18002edd6  mov     [r8], rdx
0x18002edd9  mov     rdx, [rsp+308h+var_2C0]
0x18002edde  mov     rcx, [rdx+8]
0x18002ede2  jmp     short loc_18002EDE8
0x18002ede4  mov     rcx, [rcx+10h]
0x18002ede8  mov     rax, [rcx+10h]
0x18002edec  cmp     [rax+19h], r12b
0x18002edf0  jz      short loc_18002EDE4
0x18002edf2  mov     [rdx+10h], rcx
0x18002edf6  jmp     loc_18002EE88
0x18002edfb  mov     [r8], r8
0x18002edfe  mov     rax, [rsp+308h+var_2C0]
0x18002ee03  mov     [rax+10h], rax
0x18002ee07  jmp     short loc_18002EE88
0x18002ee09  mov     rdi, [rsi]
0x18002ee0c  mov     rbx, [rdi+8]
0x18002ee10  jmp     short loc_18002EE33
0x18002ee12  lea     rdx, ?gc_wszUIName@@3QBGB; "uiname"
0x18002ee19  mov     rcx, [rbx+20h]; String1
0x18002ee1d  call    cs:__imp__wcsicmp
0x18002ee23  test    eax, eax
0x18002ee25  jns     short loc_18002EE2D
0x18002ee27  mov     rbx, [rbx+10h]
0x18002ee2b  jmp     short loc_18002EE33
0x18002ee2d  mov     rdi, rbx
0x18002ee30  mov     rbx, [rbx]
0x18002ee33  cmp     [rbx+19h], r12b
0x18002ee37  jz      short loc_18002EE12
0x18002ee39  cmp     rdi, [rsi]
0x18002ee3c  jz      loc_18002EEF2
0x18002ee42  mov     rdx, [rdi+20h]; String2
0x18002ee46  lea     rcx, ?gc_wszUIName@@3QBGB; "uiname"
0x18002ee4d  call    cs:__imp__wcsicmp
0x18002ee53  test    eax, eax
0x18002ee55  js      loc_18002EEF2
0x18002ee5b  lea     r8, [rdi+28h]
0x18002ee5f  lea     rdx, ?gc_wszUIName@@3QBGB; "uiname"
0x18002ee66  lea     rcx, [rsp+308h+var_2C0]
0x18002ee6b  call    ??$_Buynode@AEAY06$$CBGAEBV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@?$_Tree_buy@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@V?$allocator@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@PEAX@1@AEAY06$$CBGAEBV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@Z; std::_Tree_buy<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>>::_Buynode<ushort const (&)[7],Microsoft::WRL::ComPtr<IMVKey> const &>(ushort const (&)[7],Microsoft::WRL::ComPtr<IMVKey> const &)
0x18002ee70  lea     r9, [rax+20h]
0x18002ee74  mov     [rsp+308h+ppv], rax; int
0x18002ee79  lea     rdx, [rsp+308h+pv]
0x18002ee7e  lea     rcx, [rsp+308h+var_2C0]
0x18002ee83  call    ??$_Insert_nohint@AEAU?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@PEAU?$_Tree_node@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@PEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@Ukeyname_less@@V?$allocator@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@@std@@@std@@@std@@_N@1@_NAEAU?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@1@PEAU?$_Tree_node@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@PEAX@1@@Z; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::_Insert_nohint<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>,void *> *>(bool,std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>,void *> *)
0x18002ee88  mov     edx, 3
0x18002ee8d  mov     rcx, r15
0x18002ee90  call    ?MvSetUIStatus@@YAJPEAUIMVHandler@@W4__MIDL___MIDL_itf_mvengine_0000_0000_0002@@@Z; MvSetUIStatus(IMVHandler *,__MIDL___MIDL_itf_mvengine_0000_0000_0002)
0x18002ee95  mov     ebx, eax
0x18002ee97  test    eax, eax
0x18002ee99  jns     short loc_18002EEFF
0x18002ee9b  mov     rcx, [rsp+308h]; this
0x18002eea3  mov     r9d, eax; char *
0x18002eea6  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002eead  mov     edx, 0EDh; void *
0x18002eeb2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002eeb7  nop
0x18002eeb8  lea     rcx, [rsp+308h+var_2C0]
0x18002eebd  call    ?clear@?$_Tree@V?$_Tmap_traits@PEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@Ukeyname_less@@V?$allocator@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@@std@@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::clear(void)
0x18002eec2  mov     rcx, [rsp+308h+var_2C0]
0x18002eec7  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002eecd  nop
0x18002eece  mov     esi, 8
0x18002eed3  cmp     [rsp+308h+var_160], rsi
0x18002eedb  jb      short loc_18002EEEB
0x18002eedd  mov     rcx, [rsp+308h+var_178]
0x18002eee5  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002eeeb  mov     eax, ebx
0x18002eeed  jmp     loc_18002FED6
0x18002eef2  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x18002eef9  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x18002eeff  mov     [rsp+308h+var_2B0], r12
0x18002ef04  lea     rcx, [rsp+308h+var_2B0]
0x18002ef09  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIClassFactory@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIClassFactory@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IClassFactory>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IClassFactory>>)
0x18002ef0e  mov     [rsp+308h+ppv], rax; int
0x18002ef13  lea     r9, _GUID_00000001_0000_0000_c000_000000000046; riid
0x18002ef1a  xor     r8d, r8d; pvReserved
0x18002ef1d  lea     edx, [r8+1]; dwClsContext
0x18002ef21  lea     rcx, _GUID_38be0989_9830_49a8_985b_7741219fd0fb; rclsid
0x18002ef28  call    cs:__imp_CoGetClassObject
0x18002ef2e  mov     ebx, eax
0x18002ef30  test    eax, eax
0x18002ef32  jns     short loc_18002EFA7
0x18002ef34  mov     rcx, [rsp+308h]; this
0x18002ef3c  mov     r9d, eax; char *
0x18002ef3f  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002ef46  mov     edx, 0F3h; void *
0x18002ef4b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ef50  nop
0x18002ef51  mov     rcx, [rsp+308h+var_2B0]
0x18002ef56  test    rcx, rcx
0x18002ef59  jz      short loc_18002EF6D
0x18002ef5b  mov     [rsp+308h+var_2B0], r12
0x18002ef60  mov     rax, [rcx]
0x18002ef63  mov     rax, [rax+10h]
0x18002ef67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef6c  nop
0x18002ef6d  lea     rcx, [rsp+308h+var_2C0]
0x18002ef72  call    ?clear@?$_Tree@V?$_Tmap_traits@PEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@Ukeyname_less@@V?$allocator@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@@std@@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::clear(void)
0x18002ef77  mov     rcx, [rsp+308h+var_2C0]
0x18002ef7c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002ef82  nop
0x18002ef83  mov     esi, 8
0x18002ef88  cmp     [rsp+308h+var_160], rsi
0x18002ef90  jb      short loc_18002EFA0
0x18002ef92  mov     rcx, [rsp+308h+var_178]
0x18002ef9a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002efa0  mov     eax, ebx
0x18002efa2  jmp     loc_18002FED6
0x18002efa7  mov     esi, 8
0x18002efac  cmp     [r13+18h], rsi
0x18002efb0  jb      short loc_18002EFB8
0x18002efb2  mov     r9, [r13+0]
0x18002efb6  jmp     short loc_18002EFBB
0x18002efb8  mov     r9, r13
0x18002efbb  lea     r8, c_wszICCIDAttribute; "ICCID"
0x18002efc2  lea     rdx, [rsp+308h+var_2B0]
0x18002efc7  lea     rcx, [rsp+308h+var_2A8]
0x18002efcc  call    ?CreateKey@@YA?AV?$ComPtr@UIMVKey@@@WRL@Microsoft@@AEBV?$ComPtr@UIClassFactory@@@23@PEBG1@Z; CreateKey(Microsoft::WRL::ComPtr<IClassFactory> const &,ushort const *,ushort const *)
0x18002efd1  nop
0x18002efd2  mov     r8, rax
0x18002efd5  lea     rdx, c_wszICCIDAttribute; "ICCID"
0x18002efdc  lea     rcx, [rsp+308h+var_2C0]
0x18002efe1  call    ??$_Buynode@AEAY09$$CBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@?$_Tree_buy@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@V?$allocator@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@PEAX@1@AEAY09$$CBG$$QEAV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@Z; std::_Tree_buy<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>>::_Buynode<ushort const (&)[10],Microsoft::WRL::ComPtr<IMVKey>>(ushort const (&)[10],Microsoft::WRL::ComPtr<IMVKey> &&)
0x18002efe6  lea     r9, [rax+20h]
0x18002efea  mov     [rsp+308h+ppv], rax
0x18002efef  lea     rdx, [rsp+308h+pv]
0x18002eff4  lea     rcx, [rsp+308h+var_2C0]
0x18002eff9  call    ??$_Insert_nohint@AEAU?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@PEAU?$_Tree_node@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@PEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@Ukeyname_less@@V?$allocator@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@@std@@@std@@@std@@_N@1@_NAEAU?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@1@PEAU?$_Tree_node@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@PEAX@1@@Z; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::_Insert_nohint<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>,void *> *>(bool,std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>,void *> *)
0x18002effe  nop
0x18002efff  mov     rcx, qword ptr [rsp+308h+var_2A8]
0x18002f004  test    rcx, rcx
0x18002f007  jz      short loc_18002F01B
0x18002f009  mov     qword ptr [rsp+308h+var_2A8], r12
0x18002f00e  mov     rax, [rcx]
0x18002f011  mov     rax, [rax+10h]
0x18002f015  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f01a  nop
0x18002f01b  lea     r12, [r14+r14*2]
0x18002f01f  shl     r12, 5
0x18002f023  mov     rdi, [rsp+308h+var_280]
0x18002f02b  lea     rbx, [rdi+20h]
0x18002f02f  add     rbx, r12
0x18002f032  mov     [rsp+308h+pv], rbx
0x18002f037  cmp     [rbx+18h], rsi
0x18002f03b  jb      short loc_18002F042
0x18002f03d  mov     r9, [rbx]
0x18002f040  jmp     short loc_18002F045
0x18002f042  mov     r9, rbx
0x18002f045  lea     r8, c_wszIMSIAttribute; "IMSI"
0x18002f04c  lea     rdx, [rsp+308h+var_2B0]
0x18002f051  lea     rcx, [rsp+308h+var_2A8]
0x18002f056  call    ?CreateKey@@YA?AV?$ComPtr@UIMVKey@@@WRL@Microsoft@@AEBV?$ComPtr@UIClassFactory@@@23@PEBG1@Z; CreateKey(Microsoft::WRL::ComPtr<IClassFactory> const &,ushort const *,ushort const *)
0x18002f05b  nop
0x18002f05c  mov     r8, rax
0x18002f05f  lea     rdx, c_wszIMSIAttribute; "IMSI"
0x18002f066  lea     rcx, [rsp+308h+var_2C0]
0x18002f06b  call    ??$_Buynode@AEAY09$$CBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@?$_Tree_buy@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@V?$allocator@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@PEAX@1@AEAY09$$CBG$$QEAV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@Z; std::_Tree_buy<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>>::_Buynode<ushort const (&)[10],Microsoft::WRL::ComPtr<IMVKey>>(ushort const (&)[10],Microsoft::WRL::ComPtr<IMVKey> &&)
0x18002f070  lea     r9, [rax+20h]
0x18002f074  mov     [rsp+308h+ppv], rax
0x18002f079  lea     rdx, [rsp+308h+var_278]
0x18002f081  lea     rcx, [rsp+308h+var_2C0]
0x18002f086  call    ??$_Insert_nohint@AEAU?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@PEAU?$_Tree_node@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@PEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@Ukeyname_less@@V?$allocator@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@@std@@@std@@@std@@_N@1@_NAEAU?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@1@PEAU?$_Tree_node@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@PEAX@1@@Z; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::_Insert_nohint<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>,void *> *>(bool,std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>,void *> *)
0x18002f08b  nop
0x18002f08c  mov     rcx, qword ptr [rsp+308h+var_2A8]
0x18002f091  xor     r14d, r14d
0x18002f094  test    rcx, rcx
0x18002f097  jz      short loc_18002F0AB
0x18002f099  mov     qword ptr [rsp+308h+var_2A8], r14
0x18002f09e  mov     rax, [rcx]
0x18002f0a1  mov     rax, [rax+10h]
0x18002f0a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f0aa  nop
0x18002f0ab  mov     r15d, 7
0x18002f0b1  mov     [rsp+308h+var_220], r15
0x18002f0b9  mov     [rsp+308h+var_228], r14
0x18002f0c1  mov     word ptr [rsp+308h+var_238], r14w
0x18002f0ca  lea     r9d, [r15-4]
  ... truncated ...
```
