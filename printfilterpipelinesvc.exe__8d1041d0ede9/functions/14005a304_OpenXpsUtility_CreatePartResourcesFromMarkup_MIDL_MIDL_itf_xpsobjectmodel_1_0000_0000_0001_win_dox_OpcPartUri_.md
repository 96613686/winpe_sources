# OpenXpsUtility::CreatePartResourcesFromMarkup(__MIDL___MIDL_itf_xpsobjectmodel_1_0000_0000_0001,win_dox::OpcPartUri const &,IStream * &,win_scope::scope<IXpsOMPartResources *,win_scope::const_policies<win_scope::com_policies>> &)

- ea: `0x14005a304`
- end: `0x14005afa9`
- name: `?CreatePartResourcesFromMarkup@OpenXpsUtility@@YAXW4__MIDL___MIDL_itf_xpsobjectmodel_1_0000_0000_0001@@AEBVOpcPartUri@win_dox@@AEAPEAUIStream@@AEAV?$scope@PEAUIXpsOMPartResources@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@@Z`
- size: `3237`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14005afb0`
- `0x14005baac`

## callees

- `0x140002070`
- `0x140015104`
- `0x14001525c`
- `0x140015980`
- `0x14001b334`
- `0x14001bd50`
- `0x140020d70`
- `0x140026400`
- `0x140027ea4`
- `0x140027f20`
- `0x140041030`
- `0x14004650c`
- `0x140047030`
- `0x14004709c`
- `0x140048010`
- `0x1400520ec`
- `0x140055c44`
- `0x14005a15c`
- `0x14005a304`
- `0x14005b650`
- `0x14005bc8c`
- `0x140063010`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x14005ae9a`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x14005ae9a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14005a4dd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14005a6a5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14005abc4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14005abd9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14005ac1a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14005a4dd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14005a6a5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14005abc4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14005abd9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14005ac1a`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x14005a3be`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x14005a3be`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14005a376`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14005a376`
- `XmlLite!CreateXmlReader` at `0x14005a3f5`
- `XmlLite!CreateXmlReader` at `0x14005a3f5`

## string_xrefs

- `0x14005a4d2`: `FontUri`

## pseudocode

```c
// Hidden C++ exception states: #wind=46
void __fastcall OpenXpsUtility::CreatePartResourcesFromMarkup(__int64 a1, __int64 a2, const char *a3, __int64 **a4)
{
  HRESULT v7; // eax
  int v8; // edx
  const char *v9; // r8
  unsigned int v10; // r9d
  LPVOID *v11; // rax
  HRESULT v12; // eax
  int v13; // edx
  const char *v14; // r8
  unsigned int v15; // r9d
  HRESULT v16; // eax
  int v17; // edx
  const char *v18; // r8
  unsigned int v19; // r9d
  int v20; // eax
  int v21; // edx
  const char *v22; // r8
  unsigned int v23; // r9d
  int v24; // eax
  int v25; // edx
  const char *v26; // r8
  unsigned int v27; // r9d
  int v28; // eax
  int v29; // edx
  const char *v30; // r8
  unsigned int v31; // r9d
  int v32; // eax
  int v33; // edx
  const char *v34; // r8
  unsigned int v35; // r9d
  __int64 *v36; // rcx
  __int64 v37; // rax
  int v38; // eax
  int v39; // edx
  const char *v40; // r8
  unsigned int v41; // r9d
  __int64 *v42; // rbx
  __int64 v43; // rdi
  __int64 v44; // rcx
  _QWORD *v45; // rax
  int v46; // eax
  int v47; // edx
  const char *v48; // r8
  unsigned int v49; // r9d
  __int64 v50; // rcx
  LPVOID v51; // rdi
  __int64 v52; // rax
  __int64 (__fastcall *v53)(LPVOID, LPSTREAM, __int64, _QWORD, LPVOID *, __int64 *); // rbx
  _QWORD *v54; // rax
  int v55; // eax
  int v56; // edx
  const char *v57; // r8
  unsigned int v58; // r9d
  int v59; // eax
  int v60; // edx
  const char *v61; // r8
  unsigned int v62; // r9d
  int v63; // eax
  int v64; // edx
  const char *v65; // r8
  unsigned int v66; // r9d
  int v67; // ebx
  size_t v68; // rdi
  unsigned __int64 v69; // rsi
  const wchar_t *v70; // rbx
  const wchar_t *v71; // rcx
  __int128 *v72; // rcx
  int v73; // edx
  unsigned __int64 v74; // rbx
  const char *v75; // r8
  unsigned int v76; // r9d
  __int128 *v77; // rdx
  __int128 *v78; // rax
  __int64 v79; // r8
  __int128 *v80; // rax
  __int128 *v81; // r9
  __int64 *v82; // rcx
  __int64 v83; // rax
  int v84; // eax
  int v85; // edx
  const char *v86; // r8
  unsigned int v87; // r9d
  __int64 *v88; // rbx
  __int64 v89; // rdi
  __int64 v90; // rcx
  _QWORD *Interface; // rax
  int v92; // eax
  int v93; // edx
  const char *v94; // r8
  unsigned int v95; // r9d
  __int64 v96; // rcx
  LPVOID v97; // rdi
  __int64 v98; // rax
  __int64 (__fastcall *v99)(LPVOID, LPSTREAM, _QWORD, __int64 *); // rbx
  _QWORD *v100; // rax
  int v101; // eax
  int v102; // edx
  const char *v103; // r8
  unsigned int v104; // r9d
  int v105; // eax
  int v106; // edx
  const char *v107; // r8
  unsigned int v108; // r9d
  __int64 v109; // r8
  unsigned int v110; // esi
  _QWORD *v111; // rcx
  int v112; // eax
  int v113; // eax
  int v114; // eax
  _QWORD *v115; // r9
  __int64 *v116; // rcx
  __int64 v117; // rax
  int v118; // eax
  int v119; // edx
  const char *v120; // r8
  unsigned int v121; // r9d
  __int64 *v122; // rbx
  __int64 v123; // rdi
  __int64 v124; // rcx
  _QWORD *v125; // rax
  int v126; // eax
  int v127; // edx
  const char *v128; // r8
  unsigned int v129; // r9d
  __int64 v130; // rcx
  LPVOID v131; // rdi
  __int64 v132; // rax
  __int64 (__fastcall *v133)(LPVOID, LPSTREAM, _QWORD, _QWORD, __int64 *); // rbx
  _QWORD *v134; // rax
  int v135; // eax
  int v136; // edx
  const char *v137; // r8
  unsigned int v138; // r9d
  int v139; // eax
  int v140; // edx
  const char *v141; // r8
  unsigned int v142; // r9d
  _QWORD *v143; // rcx
  _QWORD *v144; // rcx
  int v145; // eax
  int v146; // edx
  const char *v147; // r8
  unsigned int v148; // r9d
  __int64 v149; // r8
  unsigned __int64 v150; // r8
  _QWORD *v151; // r9
  __int64 *v152; // rcx
  __int64 v153; // rax
  int v154; // eax
  int v155; // edx
  const char *v156; // r8
  unsigned int v157; // r9d
  __int64 *v158; // rbx
  __int64 v159; // rdi
  __int64 v160; // rcx
  _QWORD *v161; // rax
  int v162; // eax
  int v163; // edx
  const char *v164; // r8
  unsigned int v165; // r9d
  __int64 v166; // rcx
  LPVOID v167; // rdi
  __int64 v168; // rax
  __int64 (__fastcall *v169)(LPVOID, LPSTREAM, _QWORD, __int64 *); // rbx
  _QWORD *v170; // rax
  int v171; // eax
  int v172; // edx
  const char *v173; // r8
  unsigned int v174; // r9d
  int v175; // eax
  int v176; // edx
  const char *v177; // r8
  unsigned int v178; // r9d
  int v179; // eax
  int v180; // edx
  const char *v181; // r8
  unsigned int v182; // r9d
  LPVOID *ppv; // [rsp+20h] [rbp-E0h]
  void *ppvObject; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v185; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v186; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v187; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v188; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v189; // [rsp+68h] [rbp-98h] BYREF
  LPSTREAM ppstm; // [rsp+70h] [rbp-90h] BYREF
  __int64 *v191; // [rsp+78h] [rbp-88h] BYREF
  __int64 *v192; // [rsp+80h] [rbp-80h] BYREF
  __int64 *v193; // [rsp+88h] [rbp-78h] BYREF
  __int64 *v194; // [rsp+90h] [rbp-70h] BYREF
  LPVOID v195; // [rsp+98h] [rbp-68h] BYREF
  int v196; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v197; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v198[8]; // [rsp+B0h] [rbp-50h] BYREF
  LPVOID v199; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v200; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v201; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v202; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v203; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v204; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v205; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v206; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v207[24]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v208[24]; // [rsp+110h] [rbp+10h] BYREF
  __int128 v209; // [rsp+128h] [rbp+28h] BYREF
  unsigned __int64 v210; // [rsp+138h] [rbp+38h]
  unsigned __int64 v211; // [rsp+140h] [rbp+40h]
  _QWORD v212[3]; // [rsp+148h] [rbp+48h] BYREF
  unsigned __int64 v213; // [rsp+160h] [rbp+60h]
  _QWORD v214[3]; // [rsp+168h] [rbp+68h] BYREF
  unsigned __int64 v215; // [rsp+180h] [rbp+80h]
  __int128 v216; // [rsp+188h] [rbp+88h] BYREF
  __int128 v217; // [rsp+198h] [rbp+98h]

  if ( !*(_QWORD *)a3 )
    SplException::RealThrowFromHR((SplException *)0x80070057LL, a2, a3, (unsigned int)a4);
  v195 = 0;
  v7 = CoCreateInstance(
         &GUID_e974d26d_3d9b_4d47_88cc_3872f2dc3585,
         0,
         1u,
         &GUID_0a91b617_d612_4181_bf7c_be5824e9cc8f,
         &v195);
  if ( v7 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v7, v8, v9, v10);
  v11 = win_musl::CreateComObject<IOpcFactory>(&v199);
  win_dox::OpcFactory::OpcFactory((__int64)v198, v11);
  ppstm = 0;
  win_scope::detail::scope_helper<IByteReceiver *,win_scope::const_policies<win_scope::com_policies>>::reset(&ppstm, 0);
  ppstm = 0;
  v12 = CreateStreamOnHGlobal(0, 1, &ppstm);
  if ( v12 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v12, v13, v14, v15);
  ppvObject = 0;
  win_scope::detail::scope_helper<IOpcFactory *,win_scope::const_policies<win_scope::com_policies>>::reset(
    &ppvObject,
    0);
  ppvObject = 0;
  v16 = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  if ( v16 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v16, v17, v18, v19);
  v20 = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)ppvObject + 24LL))(ppvObject, *(_QWORD *)a3);
  if ( v20 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v20, v21, v22, v23);
  v196 = 0;
LABEL_12:
  while ( !(*(unsigned int (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 48LL))(ppvObject, &v196) )
  {
    if ( v196 == 1 )
    {
      v189 = 0;
      v197 = 0;
      v24 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 64LL))(ppvObject);
      if ( v24 < 0 )
        SplException::RealThrowFromHR((SplException *)(unsigned int)v24, v25, v26, v27);
      if ( !v24 )
      {
        while ( 1 )
        {
          if ( (*(unsigned int (__fastcall **)(void *))(*(_QWORD *)ppvObject + 152LL))(ppvObject) )
            goto LABEL_37;
          v28 = (*(__int64 (__fastcall **)(void *, __int64 *, _QWORD))(*(_QWORD *)ppvObject + 112LL))(
                  ppvObject,
                  &v197,
                  0);
          if ( v28 < 0 )
            SplException::RealThrowFromHR((SplException *)(unsigned int)v28, v29, v30, v31);
          v32 = (*(__int64 (__fastcall **)(void *, __int64 *, _QWORD))(*(_QWORD *)ppvObject + 128LL))(
                  ppvObject,
                  &v189,
                  0);
          if ( v32 < 0 )
            SplException::RealThrowFromHR((SplException *)(unsigned int)v32, v33, v34, v35);
          if ( !(unsigned int)_o__wcsicmp(v197, L"FontUri") )
            break;
          if ( !(unsigned int)_o__wcsicmp(v197, L"ImageSource") )
          {
            std::wstring::wstring((__int64)v214, (__int64)L"{ColorConvertedBitmap");
            v68 = v214[2];
            v69 = -1;
            do
              ++v69;
            while ( *(_WORD *)(v189 + 2 * v69) );
            std::wstring::wstring(v212);
            if ( v68 >= v69 )
              goto LABEL_84;
            v70 = (const wchar_t *)v189;
            std::_String_val<std::_Simple_types<wchar_t>>::_Check_offset(v214, 0);
            v71 = (const wchar_t *)v214;
            if ( v215 > 7 )
              v71 = (const wchar_t *)v214[0];
            if ( std::_Traits_compare<std::char_traits<wchar_t>>(v71, v68, v70, v68) )
            {
LABEL_84:
              v109 = -1;
              do
                ++v109;
              while ( *(_WORD *)(v189 + 2 * v109) );
              std::wstring::_Assign<wchar_t>(v212, v189);
            }
            else
            {
              while ( *(_WORD *)(v189 + 2 * v68) == 32 )
                ++v68;
              v209 = 0;
              v210 = 0;
              v211 = 0;
              std::wstring::_Construct<1,wchar_t *>(&v209, v189 + 2 * v68, v69 - v68 - 1);
              v72 = &v209;
              if ( v211 > 7 )
                v72 = (__int128 *)v209;
              v74 = std::_Traits_find_ch<std::char_traits<wchar_t>>(v72, v210);
              if ( v74 == -1 )
                SplException::RealThrowFromHR((SplException *)0x8052000CLL, v73, v75, v76);
              std::_String_val<std::_Simple_types<wchar_t>>::_Check_offset(&v209, 0);
              v77 = &v209;
              if ( v211 > 7 )
                v77 = (__int128 *)v209;
              std::wstring::_Assign<wchar_t>(v212, v77);
              while ( 1 )
              {
                if ( v210 <= v74 )
                {
                  std::_Xout_of_range("invalid string position");
                  __debugbreak();
                }
                v78 = &v209;
                if ( v211 > 7 )
                  v78 = (__int128 *)v209;
                if ( *((_WORD *)v78 + v74) != 32 )
                  break;
                ++v74;
              }
              v216 = 0;
              v217 = 0;
              std::_String_val<std::_Simple_types<wchar_t>>::_Check_offset(&v209, v74);
              v79 = -1;
              if ( v210 - v74 != -1 )
                v79 = v210 - v74;
              v80 = &v209;
              if ( v211 > 7 )
                v80 = (__int128 *)v209;
              std::wstring::_Construct<1,wchar_t *>(&v216, (char *)v80 + 2 * v74, v79);
              v81 = &v216;
              if ( *((_QWORD *)&v217 + 1) > 7u )
                v81 = (__int128 *)v216;
              OpenXpsUtility::MakeAbsolutePartUri(v207, v198, a2, v81);
              v186 = 0;
              v192 = 0;
              v82 = *a4;
              v83 = **a4;
              v192 = 0;
              v84 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v83 + 40))(v82, &v192);
              if ( v84 < 0 )
                SplException::RealThrowFromHR((SplException *)(unsigned int)v84, v85, v86, v87);
              v88 = v192;
              v89 = *v192;
              v90 = v186;
              v186 = 0;
              if ( v90 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
              v186 = 0;
              Interface = (_QWORD *)win_dox::OpcPartUri::GetInterface(v207, &v202);
              v92 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v89 + 72))(v88, *Interface, &v186);
              if ( v92 < 0 )
                SplException::RealThrowFromHR((SplException *)(unsigned int)v92, v93, v94, v95);
              if ( v202 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v202 + 16LL))(v202);
                v202 = 0;
              }
              v96 = v186;
              if ( !v186 )
              {
                v97 = v195;
                v98 = *(_QWORD *)v195;
                v186 = 0;
                v99 = *(__int64 (__fastcall **)(LPVOID, LPSTREAM, _QWORD, __int64 *))(v98 + 192);
                v100 = (_QWORD *)win_dox::OpcPartUri::GetInterface(v207, &v203);
                v101 = v99(v97, ppstm, *v100, &v186);
                if ( v101 < 0 )
                  SplException::RealThrowFromHR((SplException *)(unsigned int)v101, v102, v103, v104);
                if ( v203 )
                {
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v203 + 16LL))(v203);
                  v203 = 0;
                }
                v105 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v192 + 64))(v192, v186);
                if ( v105 < 0 )
                  SplException::RealThrowFromHR((SplException *)(unsigned int)v105, v106, v107, v108);
                v96 = v186;
              }
              if ( v192 )
              {
                (*(void (__fastcall **)(__int64 *))(*v192 + 16))(v192);
                v192 = 0;
                v96 = v186;
              }
              if ( v96 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
                v186 = 0;
              }
              win_dox::OpcPartUri::~OpcPartUri((win_dox::OpcPartUri *)v207);
              std::wstring::_Tidy_deallocate(&v216);
              std::wstring::_Tidy_deallocate(&v209);
            }
            v110 = 1;
            v111 = v212;
            if ( v213 > 7 )
              v111 = (_QWORD *)v212[0];
            v112 = OpenXpsUtility::GetResourceTypeFromSuffix(v111) - 1;
            if ( v112 )
            {
              v113 = v112 - 1;
              if ( v113 )
              {
                v114 = v113 - 1;
                if ( v114 )
                {
                  if ( v114 == 1 )
                    v110 = 4;
                }
                else
                {
                  v110 = 3;
                }
              }
              else
              {
                v110 = 2;
              }
            }
            else
            {
              v110 = 1;
            }
            v115 = v212;
            if ( v213 > 7 )
              v115 = (_QWORD *)v212[0];
            OpenXpsUtility::MakeAbsolutePartUri(v208, v198, a2, v115);
            v187 = 0;
            v193 = 0;
            v116 = *a4;
            v117 = **a4;
            v193 = 0;
            v118 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v117 + 32))(v116, &v193);
            if ( v118 < 0 )
              SplException::RealThrowFromHR((SplException *)(unsigned int)v118, v119, v120, v121);
            v122 = v193;
            v123 = *v193;
            v124 = v187;
            v187 = 0;
            if ( v124 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v124 + 16LL))(v124);
            v187 = 0;
            v125 = (_QWORD *)win_dox::OpcPartUri::GetInterface(v208, &v204);
            v126 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v123 + 72))(v122, *v125, &v187);
            if ( v126 < 0 )
              SplException::RealThrowFromHR((SplException *)(unsigned int)v126, v127, v128, v129);
            if ( v204 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v204 + 16LL))(v204);
              v204 = 0;
            }
            v130 = v187;
            if ( !v187 )
            {
              v131 = v195;
              v132 = *(_QWORD *)v195;
              v187 = 0;
              v133 = *(__int64 (__fastcall **)(LPVOID, LPSTREAM, _QWORD, _QWORD, __int64 *))(v132 + 216);
              v134 = (_QWORD *)win_dox::OpcPartUri::GetInterface(v208, &v205);
              v135 = v133(v131, ppstm, v110, *v134, &v187);
              if ( v135 < 0 )
                SplException::RealThrowFromHR((SplException *)(unsigned int)v135, v136, v137, v138);
              if ( v205 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v205 + 16LL))(v205);
                v205 = 0;
              }
              v139 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v193 + 64))(v193, v187);
              if ( v139 < 0 )
                SplException::RealThrowFromHR((SplException *)(unsigned int)v139, v140, v141, v142);
              v130 = v187;
            }
            if ( v193 )
            {
              (*(void (__fastcall **)(__int64 *))(*v193 + 16))(v193);
              v193 = 0;
              v130 = v187;
            }
            if ( v130 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v130 + 16LL))(v130);
              v187 = 0;
            }
            win_dox::OpcPartUri::~OpcPartUri((win_dox::OpcPartUri *)v208);
            std::wstring::_Tidy_deallocate(v212);
            v143 = v214;
            goto LABEL_116;
          }
          if ( (unsigned int)_o__wcsicmp(v197, L"Color") && (unsigned int)_o__wcsicmp(v197, L"Fill") )
            goto LABEL_37;
          std::wstring::wstring(v212);
          std::wstring::assign(v212, v189, 12);
          v144 = v212;
          if ( v213 > 7 )
            v144 = (_QWORD *)v212[0];
          if ( (unsigned int)_o__wcsicmp(v144, L"ContextColor") )
          {
            v145 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 72LL))(ppvObject);
            v67 = v145;
            if ( v145 < 0 )
              SplException::RealThrowFromHR((SplException *)(unsigned int)v145, v146, v147, v148);
          }
          else
          {
            v149 = 13;
            if ( *(_WORD *)(v189 + 26) )
            {
              do
              {
                if ( *(_WORD *)(v189 + 2 * v149) == 32 )
                  break;
                ++v149;
              }
              while ( *(_WORD *)(v189 + 2 * v149) );
            }
            std::wstring::wstring(v214);
            if ( v150 > 0xD )
            {
              std::wstring::assign(v214, v189 + 26, v150 - 13);
              v151 = v214;
              if ( v215 > 7 )
                v151 = (_QWORD *)v214[0];
              OpenXpsUtility::MakeAbsolutePartUri(v208, v198, a2, v151);
              v188 = 0;
              v194 = 0;
              v152 = *a4;
              v153 = **a4;
              v194 = 0;
              v154 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v153 + 40))(v152, &v194);
              if ( v154 < 0 )
                SplException::RealThrowFromHR((SplException *)(unsigned int)v154, v155, v156, v157);
              v158 = v194;
              v159 = *v194;
              v160 = v188;
              v188 = 0;
              if ( v160 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v160 + 16LL))(v160);
              v188 = 0;
              v161 = (_QWORD *)win_dox::OpcPartUri::GetInterface(v208, &v206);
              v162 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v159 + 72))(v158, *v161, &v188);
              if ( v162 < 0 )
                SplException::RealThrowFromHR((SplException *)(unsigned int)v162, v163, v164, v165);
              if ( v206 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v206 + 16LL))(v206);
                v206 = 0;
              }
              v166 = v188;
              if ( !v188 )
              {
                v167 = v195;
                v168 = *(_QWORD *)v195;
                v188 = 0;
                v169 = *(__int64 (__fastcall **)(LPVOID, LPSTREAM, _QWORD, __int64 *))(v168 + 192);
                v170 = (_QWORD *)win_dox::OpcPartUri::GetInterface(v208, &v199);
                v171 = v169(v167, ppstm, *v170, &v188);
                if ( v171 < 0 )
                  SplException::RealThrowFromHR((SplException *)(unsigned int)v171, v172, v173, v174);
                if ( v199 )
                {
                  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v199 + 16LL))(v199);
                  v199 = 0;
                }
                v175 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v194 + 64))(v194, v188);
                if ( v175 < 0 )
                  SplException::RealThrowFromHR((SplException *)(unsigned int)v175, v176, v177, v178);
                v166 = v188;
              }
              if ( v194 )
              {
                (*(void (__fastcall **)(__int64 *))(*v194 + 16))(v194);
                v194 = 0;
                v166 = v188;
              }
              if ( v166 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v166 + 16LL))(v166);
                v188 = 0;
              }
              win_dox::OpcPartUri::~OpcPartUri((win_dox::OpcPartUri *)v208);
              std::wstring::_Tidy_deallocate(v214);
              v143 = v212;
LABEL_116:
              std::wstring::_Tidy_deallocate(v143);
LABEL_37:
              v63 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 72LL))(ppvObject);
              v67 = v63;
              if ( v63 < 0 )
                SplException::RealThrowFromHR((SplException *)(unsigned int)v63, v64, v65, v66);
              goto LABEL_38;
            }
            v179 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 72LL))(ppvObject);
            v67 = v179;
            if ( v179 < 0 )
              SplException::RealThrowFromHR((SplException *)(unsigned int)v179, v180, v181, v182);
            std::wstring::_Tidy_deallocate(v214);
          }
          std::wstring::_Tidy_deallocate(v212);
LABEL_38:
          if ( v67 )
            goto LABEL_12;
        }
        OpenXpsUtility::MakeAbsolutePartUri(v207, v198, a2, v189);
        v185 = 0;
        v191 = 0;
        v36 = *a4;
        v37 = **a4;
        v191 = 0;
        v38 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v37 + 24))(v36, &v191);
        if ( v38 < 0 )
          SplException::RealThrowFromHR((SplException *)(unsigned int)v38, v39, v40, v41);
        v42 = v191;
        v43 = *v191;
        v44 = v185;
        v185 = 0;
        if ( v44 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
        v185 = 0;
        v45 = (_QWORD *)win_dox::OpcPartUri::GetInterface(v207, &v200);
        v46 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v43 + 72))(v42, *v45, &v185);
        if ( v46 < 0 )
          SplException::RealThrowFromHR((SplException *)(unsigned int)v46, v47, v48, v49);
        if ( v200 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v200 + 16LL))(v200);
          v200 = 0;
        }
        v50 = v185;
        if ( !v185 )
        {
          v51 = v195;
          v52 = *(_QWORD *)v195;
          v185 = 0;
          v53 = *(__int64 (__fastcall **)(LPVOID, LPSTREAM, __int64, _QWORD, LPVOID *, __int64 *))(v52 + 232);
          v54 = (_QWORD *)win_dox::OpcPartUri::GetInterface(v207, &v201);
          LODWORD(ppv) = 0;
          v55 = v53(v51, ppstm, 1, *v54, ppv, &v185);
          if ( v55 < 0 )
            SplException::RealThrowFromHR((SplException *)(unsigned int)v55, v56, v57, v58);
          if ( v201 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v201 + 16LL))(v201);
            v201 = 0;
          }
          v59 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v191 + 56))(v191, v185);
          if ( v59 < 0 )
            SplException::RealThrowFromHR((SplException *)(unsigned int)v59, v60, v61, v62);
          v50 = v185;
        }
        if ( v191 )
        {
          (*(void (__fastcall **)(__int64 *))(*v191 + 16))(v191);
          v191 = 0;
          v50 = v185;
        }
        if ( v50 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
          v185 = 0;
        }
        win_dox::OpcPartUri::~OpcPartUri((win_dox::OpcPartUri *)v207);
        goto LABEL_37;
      }
    }
  }
  win_scope::detail::scope_helper<IOpcFactory *,win_scope::const_policies<win_scope::com_policies>>::reset(
    &ppvObject,
    0);
  if ( ppvObject )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    ppvObject = 0;
  }
  if ( ppstm )
  {
    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    ppstm = 0;
  }
  win_dox::Uri::~Uri((win_dox::Uri *)v198);
  if ( v195 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v195 + 16LL))(v195);
}

```

## disassembly

```asm
0x14005a304  mov     [rsp-8+arg_0], rbx
0x14005a309  push    rbp
0x14005a30a  push    rsi
0x14005a30b  push    rdi
0x14005a30c  push    r12
0x14005a30e  push    r13
0x14005a310  push    r14
0x14005a312  push    r15
0x14005a314  lea     rbp, [rsp-0B0h]
0x14005a31c  sub     rsp, 1B0h
0x14005a323  mov     rax, cs:__security_cookie
0x14005a32a  xor     rax, rsp
0x14005a32d  mov     [rbp+0E0h+var_38], rax
0x14005a334  mov     r15, r9
0x14005a337  mov     rbx, r8
0x14005a33a  mov     r14, rdx
0x14005a33d  xor     r12d, r12d
0x14005a340  cmp     [r8], r12
0x14005a343  jnz     short loc_14005A350
0x14005a345  mov     ecx, 80070057h; this
0x14005a34a  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x14005a350  mov     [rbp+0E0h+var_148], r12
0x14005a354  lea     rax, [rbp+0E0h+var_148]
0x14005a358  mov     [rsp+1E0h+ppv], rax; ppv
0x14005a35d  lea     r9, _GUID_0a91b617_d612_4181_bf7c_be5824e9cc8f; riid
0x14005a364  mov     r13d, 1
0x14005a36a  mov     r8d, r13d; dwClsContext
0x14005a36d  xor     edx, edx; pUnkOuter
0x14005a36f  lea     rcx, _GUID_e974d26d_3d9b_4d47_88cc_3872f2dc3585; rclsid
0x14005a376  call    cs:__imp_CoCreateInstance
0x14005a37c  test    eax, eax
0x14005a37e  jns     short loc_14005A388
0x14005a380  mov     ecx, eax; this
0x14005a382  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x14005a388  lea     rcx, [rbp+0E0h+var_128]; ppv
0x14005a38c  call    ??$CreateComObject@UIOpcFactory@@@win_musl@@YA?AV?$scope@PEAUIOpcFactory@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@AEBU_GUID@@K@Z; win_musl::CreateComObject<IOpcFactory>(_GUID const &,ulong)
0x14005a391  mov     rdx, rax
0x14005a394  lea     rcx, [rbp+0E0h+var_130]
0x14005a398  call    ??$?0V?$scope@PEAUIOpcFactory@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@@OpcFactory@win_dox@@QEAA@V?$scope@PEAUIOpcFactory@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@@Z; win_dox::OpcFactory::OpcFactory(win_scope::scope<IOpcFactory *,win_scope::const_policies<win_scope::com_policies>>)
0x14005a39d  nop
0x14005a39e  mov     [rsp+1E0h+ppstm], r12
0x14005a3a3  xor     edx, edx
0x14005a3a5  lea     rcx, [rsp+1E0h+ppstm]
0x14005a3aa  call    ?reset@?$scope_helper@PEAUIByteReceiver@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@detail@win_scope@@SAXAEAV?$scope@PEAUIByteReceiver@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@3@PEAUIByteReceiver@@@Z; win_scope::detail::scope_helper<IByteReceiver *,win_scope::const_policies<win_scope::com_policies>>::reset(win_scope::scope<IByteReceiver *,win_scope::const_policies<win_scope::com_policies>> &,IByteReceiver *)
0x14005a3af  mov     [rsp+1E0h+ppstm], r12
0x14005a3b4  lea     r8, [rsp+1E0h+ppstm]; ppstm
0x14005a3b9  mov     edx, r13d; fDeleteOnRelease
0x14005a3bc  xor     ecx, ecx; hGlobal
0x14005a3be  call    cs:__imp_CreateStreamOnHGlobal
0x14005a3c4  test    eax, eax
0x14005a3c6  jns     short loc_14005A3D0
0x14005a3c8  mov     ecx, eax; this
0x14005a3ca  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x14005a3d0  mov     [rsp+1E0h+ppvObject], r12
0x14005a3d5  xor     edx, edx
0x14005a3d7  lea     rcx, [rsp+1E0h+ppvObject]
0x14005a3dc  call    ?reset@?$scope_helper@PEAUIOpcFactory@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@detail@win_scope@@SAXAEAV?$scope@PEAUIOpcFactory@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@3@PEAUIOpcFactory@@@Z; win_scope::detail::scope_helper<IOpcFactory *,win_scope::const_policies<win_scope::com_policies>>::reset(win_scope::scope<IOpcFactory *,win_scope::const_policies<win_scope::com_policies>> &,IOpcFactory *)
0x14005a3e1  mov     [rsp+1E0h+ppvObject], r12
0x14005a3e6  xor     r8d, r8d; pMalloc
0x14005a3e9  lea     rdx, [rsp+1E0h+ppvObject]; ppvObject
0x14005a3ee  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x14005a3f5  call    cs:__imp_CreateXmlReader
0x14005a3fb  test    eax, eax
0x14005a3fd  jns     short loc_14005A407
0x14005a3ff  mov     ecx, eax; this
0x14005a401  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x14005a407  mov     rcx, [rsp+1E0h+ppvObject]
0x14005a40c  mov     rax, [rcx]
0x14005a40f  mov     rdx, [rbx]
0x14005a412  mov     rax, [rax+18h]
0x14005a416  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a41b  test    eax, eax
0x14005a41d  jns     short loc_14005A427
0x14005a41f  mov     ecx, eax; this
0x14005a421  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x14005a427  mov     [rbp+0E0h+var_140], r12d
0x14005a42b  mov     rcx, [rsp+1E0h+ppvObject]
0x14005a430  mov     rax, [rcx]
0x14005a433  lea     rdx, [rbp+0E0h+var_140]
0x14005a437  mov     rax, [rax+30h]
0x14005a43b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a440  test    eax, eax
0x14005a442  jnz     loc_14005AF1C
0x14005a448  cmp     [rbp+0E0h+var_140], r13d
0x14005a44c  jnz     short loc_14005A42B
0x14005a44e  mov     [rsp+1E0h+var_178], r12
0x14005a453  mov     [rbp+0E0h+var_138], r12
0x14005a457  mov     rcx, [rsp+1E0h+ppvObject]
0x14005a45c  mov     rax, [rcx]
0x14005a45f  mov     rax, [rax+40h]
0x14005a463  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a468  test    eax, eax
0x14005a46a  js      loc_14005AF14
0x14005a470  jnz     short loc_14005A42B
0x14005a472  mov     rcx, [rsp+1E0h+ppvObject]
0x14005a477  mov     rax, [rcx]
0x14005a47a  mov     rax, [rax+98h]
0x14005a481  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a486  test    eax, eax
0x14005a488  jnz     loc_14005A672
0x14005a48e  mov     rcx, [rsp+1E0h+ppvObject]
0x14005a493  mov     rax, [rcx]
0x14005a496  xor     r8d, r8d
0x14005a499  lea     rdx, [rbp+0E0h+var_138]
0x14005a49d  mov     rax, [rax+70h]
0x14005a4a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a4a6  test    eax, eax
0x14005a4a8  js      loc_14005AF04
0x14005a4ae  mov     rcx, [rsp+1E0h+ppvObject]
0x14005a4b3  mov     rax, [rcx]
0x14005a4b6  xor     r8d, r8d
0x14005a4b9  lea     rdx, [rsp+1E0h+var_178]
0x14005a4be  mov     rax, [rax+80h]
0x14005a4c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a4ca  test    eax, eax
0x14005a4cc  js      loc_14005AEFC
0x14005a4d2  lea     rdx, aFonturi; "FontUri"
0x14005a4d9  mov     rcx, [rbp+0E0h+var_138]
0x14005a4dd  call    cs:__imp__o__wcsicmp
0x14005a4e3  test    eax, eax
0x14005a4e5  jnz     loc_14005A69A
0x14005a4eb  mov     r9, [rsp+1E0h+var_178]
0x14005a4f0  mov     r8, r14
0x14005a4f3  lea     rdx, [rbp+0E0h+var_130]
0x14005a4f7  lea     rcx, [rbp+0E0h+var_E8]
0x14005a4fb  call    ?MakeAbsolutePartUri@OpenXpsUtility@@YA?AVOpcPartUri@win_dox@@AEAVOpcFactory@3@AEBV23@PEB_W@Z; OpenXpsUtility::MakeAbsolutePartUri(win_dox::OpcFactory &,win_dox::OpcPartUri const &,wchar_t const *)
0x14005a500  nop
0x14005a501  mov     [rsp+1E0h+var_198], r12
0x14005a506  mov     [rsp+1E0h+var_168], r12
0x14005a50b  mov     rcx, [r15]
0x14005a50e  mov     rax, [rcx]
0x14005a511  mov     [rsp+1E0h+var_168], r12
0x14005a516  lea     rdx, [rsp+1E0h+var_168]
0x14005a51b  mov     rax, [rax+18h]
0x14005a51f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a524  test    eax, eax
0x14005a526  js      loc_14005AE6B
0x14005a52c  mov     rbx, [rsp+1E0h+var_168]
0x14005a531  mov     rdi, [rbx]
0x14005a534  mov     rcx, [rsp+1E0h+var_198]
0x14005a539  mov     [rsp+1E0h+var_198], r12
0x14005a53e  test    rcx, rcx
0x14005a541  jz      short loc_14005A550
0x14005a543  mov     rax, [rcx]
0x14005a546  mov     rax, [rax+10h]
0x14005a54a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a54f  nop
0x14005a550  mov     [rsp+1E0h+var_198], r12
0x14005a555  lea     rdx, [rbp+0E0h+var_120]
0x14005a559  lea     rcx, [rbp+0E0h+var_E8]
0x14005a55d  call    ?GetInterface@OpcPartUri@win_dox@@QEBA?AV?$scope@PEAUIOpcPartUri@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@XZ; win_dox::OpcPartUri::GetInterface(void)
0x14005a562  nop
0x14005a563  lea     r8, [rsp+1E0h+var_198]
0x14005a568  mov     rdx, [rax]
0x14005a56b  mov     rcx, rbx
0x14005a56e  mov     rax, [rdi+48h]
0x14005a572  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a577  test    eax, eax
0x14005a579  js      loc_14005AE63
0x14005a57f  mov     rcx, [rbp+0E0h+var_120]
0x14005a583  test    rcx, rcx
0x14005a586  jz      short loc_14005A598
0x14005a588  mov     rax, [rcx]
0x14005a58b  mov     rax, [rax+10h]
0x14005a58f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a594  mov     [rbp+0E0h+var_120], r12
0x14005a598  mov     rcx, [rsp+1E0h+var_198]
0x14005a59d  test    rcx, rcx
0x14005a5a0  jnz     loc_14005A630
0x14005a5a6  mov     rdi, [rbp+0E0h+var_148]
0x14005a5aa  mov     rax, [rdi]
0x14005a5ad  mov     [rsp+1E0h+var_198], r12
0x14005a5b2  mov     rbx, [rax+0E8h]
0x14005a5b9  lea     rdx, [rbp+0E0h+var_118]
0x14005a5bd  lea     rcx, [rbp+0E0h+var_E8]
0x14005a5c1  call    ?GetInterface@OpcPartUri@win_dox@@QEBA?AV?$scope@PEAUIOpcPartUri@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@XZ; win_dox::OpcPartUri::GetInterface(void)
0x14005a5c6  nop
0x14005a5c7  lea     rcx, [rsp+1E0h+var_198]
0x14005a5cc  mov     [rsp+1E0h+var_1B8], rcx
0x14005a5d1  mov     dword ptr [rsp+1E0h+ppv], r12d
0x14005a5d6  mov     r9, [rax]
0x14005a5d9  mov     r8d, r13d
0x14005a5dc  mov     rdx, [rsp+1E0h+ppstm]
0x14005a5e1  mov     rcx, rdi
0x14005a5e4  mov     rax, rbx
0x14005a5e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a5ec  test    eax, eax
0x14005a5ee  js      loc_14005AE5B
0x14005a5f4  mov     rcx, [rbp+0E0h+var_118]
0x14005a5f8  test    rcx, rcx
0x14005a5fb  jz      short loc_14005A60D
0x14005a5fd  mov     rax, [rcx]
0x14005a600  mov     rax, [rax+10h]
0x14005a604  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a609  mov     [rbp+0E0h+var_118], r12
0x14005a60d  mov     rcx, [rsp+1E0h+var_168]
0x14005a612  mov     rax, [rcx]
0x14005a615  mov     rdx, [rsp+1E0h+var_198]
0x14005a61a  mov     rax, [rax+38h]
0x14005a61e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a623  test    eax, eax
0x14005a625  js      loc_14005AE53
0x14005a62b  mov     rcx, [rsp+1E0h+var_198]
0x14005a630  mov     rdx, [rsp+1E0h+var_168]
0x14005a635  test    rdx, rdx
0x14005a638  jz      short loc_14005A653
0x14005a63a  mov     rax, [rdx]
0x14005a63d  mov     rcx, rdx
0x14005a640  mov     rax, [rax+10h]
0x14005a644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a649  mov     [rsp+1E0h+var_168], r12
0x14005a64e  mov     rcx, [rsp+1E0h+var_198]
0x14005a653  test    rcx, rcx
0x14005a656  jz      short loc_14005A669
0x14005a658  mov     rax, [rcx]
0x14005a65b  mov     rax, [rax+10h]
0x14005a65f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a664  mov     [rsp+1E0h+var_198], r12
0x14005a669  lea     rcx, [rbp+0E0h+var_E8]; this
0x14005a66d  call    ??1OpcPartUri@win_dox@@QEAA@XZ; win_dox::OpcPartUri::~OpcPartUri(void)
0x14005a672  mov     rcx, [rsp+1E0h+ppvObject]
0x14005a677  mov     rax, [rcx]
0x14005a67a  mov     rax, [rax+48h]
0x14005a67e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a683  mov     ebx, eax
0x14005a685  test    eax, eax
0x14005a687  js      loc_14005AF0C
0x14005a68d  test    ebx, ebx
0x14005a68f  jz      loc_14005A472
0x14005a695  jmp     loc_14005A42B
0x14005a69a  lea     rdx, aImagesource; "ImageSource"
0x14005a6a1  mov     rcx, [rbp+0E0h+var_138]
0x14005a6a5  call    cs:__imp__o__wcsicmp
0x14005a6ab  test    eax, eax
0x14005a6ad  jnz     loc_14005ABB9
0x14005a6b3  lea     rdx, aColorconverted; "{ColorConvertedBitmap"
0x14005a6ba  lea     rcx, [rbp+0E0h+var_78]
0x14005a6be  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x14005a6c3  nop
0x14005a6c4  mov     rdi, [rbp+0E0h+var_68]
0x14005a6c8  mov     rax, [rsp+1E0h+var_178]
0x14005a6cd  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14005a6d1  inc     rsi
0x14005a6d4  cmp     [rax+rsi*2], r12w
0x14005a6d9  jnz     short loc_14005A6D1
0x14005a6db  lea     rcx, [rbp+0E0h+var_98]
0x14005a6df  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x14005a6e4  nop
0x14005a6e5  cmp     rdi, rsi
0x14005a6e8  jnb     loc_14005A9BE
0x14005a6ee  mov     rbx, [rsp+1E0h+var_178]
0x14005a6f3  xor     edx, edx
0x14005a6f5  lea     rcx, [rbp+0E0h+var_78]
0x14005a6f9  call    ?_Check_offset@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAX_K@Z; std::_String_val<std::_Simple_types<wchar_t>>::_Check_offset(unsigned __int64)
0x14005a6fe  lea     rcx, [rbp+0E0h+var_78]
0x14005a702  cmp     [rbp+0E0h+var_60], 7
0x14005a70a  cmova   rcx, [rbp+0E0h+var_78]
0x14005a70f  mov     r9, rdi
0x14005a712  mov     r8, rbx
0x14005a715  mov     rdx, rdi
0x14005a718  call    ??$_Traits_compare@U?$char_traits@_W@std@@@std@@YAHQEB_W_K01@Z; std::_Traits_compare<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x14005a71d  test    eax, eax
0x14005a71f  jnz     loc_14005A9BE
0x14005a725  mov     rax, [rsp+1E0h+var_178]
0x14005a72a  jmp     short loc_14005A72F
0x14005a72c  add     rdi, r13
0x14005a72f  cmp     word ptr [rax+rdi*2], 20h ; ' '
0x14005a734  jz      short loc_14005A72C
0x14005a736  xorps   xmm0, xmm0
0x14005a739  movups  [rbp+0E0h+var_B8], xmm0
0x14005a73d  mov     [rbp+0E0h+var_A8], r12
0x14005a741  mov     [rbp+0E0h+var_A0], r12
0x14005a745  sub     rsi, rdi
0x14005a748  sub     rsi, r13
0x14005a74b  lea     rdx, [rax+rdi*2]
0x14005a74f  mov     r8, rsi
0x14005a752  lea     rcx, [rbp+0E0h+var_B8]
0x14005a756  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x14005a75b  nop
0x14005a75c  lea     rcx, [rbp+0E0h+var_B8]
0x14005a760  cmp     [rbp+0E0h+var_A0], 7
0x14005a765  cmova   rcx, qword ptr [rbp+0E0h+var_B8]
0x14005a76a  mov     rdx, [rbp+0E0h+var_A8]
0x14005a76e  call    ??$_Traits_find_ch@U?$char_traits@_W@std@@@std@@YA_KQEB_W_K1_W@Z; std::_Traits_find_ch<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,unsigned __int64,wchar_t)
0x14005a773  mov     rbx, rax
0x14005a776  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14005a77a  jz      loc_14005AEA1
0x14005a780  xor     edx, edx
0x14005a782  lea     rcx, [rbp+0E0h+var_B8]
0x14005a786  call    ?_Check_offset@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAX_K@Z; std::_String_val<std::_Simple_types<wchar_t>>::_Check_offset(unsigned __int64)
0x14005a78b  mov     r8, rbx
0x14005a78e  cmp     [rbp+0E0h+var_A8], rbx
0x14005a792  cmovb   r8, [rbp+0E0h+var_A8]
0x14005a797  lea     rdx, [rbp+0E0h+var_B8]
0x14005a79b  cmp     [rbp+0E0h+var_A0], 7
0x14005a7a0  cmova   rdx, qword ptr [rbp+0E0h+var_B8]
0x14005a7a5  lea     rcx, [rbp+0E0h+var_98]
0x14005a7a9  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x14005a7ae  cmp     [rbp+0E0h+var_A8], rbx
0x14005a7b2  jbe     loc_14005AE93
  ... truncated ...
```
