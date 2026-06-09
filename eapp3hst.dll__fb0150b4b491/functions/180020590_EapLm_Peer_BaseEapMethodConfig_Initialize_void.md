# EapLm::Peer::BaseEapMethodConfig::Initialize(void)

- ea: `0x180020590`
- end: `0x1800213a2`
- name: `?Initialize@BaseEapMethodConfig@Peer@EapLm@@UEAAXXZ`
- size: `3602`
- prototype: `void __fastcall(EapLm::Peer::BaseEapMethodConfig *__hidden this)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, loader_planting`

## callees

- `0x1800017a0`
- `0x18000213c`
- `0x180003e38`
- `0x18000bba8`
- `0x18000eb74`
- `0x180012d18`
- `0x180012e50`
- `0x180012ed0`
- `0x180013188`
- `0x180015534`
- `0x180016b4c`
- `0x18001fdd8`
- `0x18001fea8`
- `0x18001fee0`
- `0x180020264`
- `0x180020590`
- `0x1800213a8`
- `0x18002e290`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180020637`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180020637`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021379`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021379`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180020605`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180020605`

## string_xrefs

- `0x18002061c`: `GetSystemDirectory failed`
- `0x180020629`: `\eappgnui.dll`

## pseudocode

```c
void __fastcall EapLm::Peer::BaseEapMethodConfig::Initialize(EapLm::Peer::BaseEapMethodConfig *this)
{
  int v2; // r15d
  __int64 v3; // rax
  void *Module; // rax
  int v5; // r12d
  char *v6; // rbx
  char *v7; // rdi
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rsi
  __int64 v11; // rax
  __int64 v12; // rdx
  int v13; // edi
  __int64 v14; // rax
  __int64 v15; // rdx
  int v16; // ebx
  int v17; // eax
  char *v18; // r13
  _BYTE *v19; // rax
  int v20; // r12d
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rsi
  __int64 v24; // rax
  __int64 v25; // rdx
  int v26; // edi
  __int64 v27; // rax
  __int64 v28; // rdx
  int v29; // ebx
  int v30; // eax
  _BYTE *v31; // rax
  int v32; // r12d
  __int64 v33; // rax
  __int64 v34; // rdx
  __int64 v35; // rsi
  __int64 v36; // rax
  __int64 v37; // rdx
  int v38; // edi
  __int64 v39; // rax
  __int64 v40; // rdx
  int v41; // ebx
  int v42; // eax
  _BYTE *v43; // rax
  int v44; // r12d
  __int64 v45; // rax
  __int64 v46; // rdx
  __int64 v47; // rsi
  __int64 v48; // rax
  __int64 v49; // rdx
  int v50; // edi
  __int64 v51; // rax
  __int64 v52; // rdx
  int v53; // ebx
  int v54; // eax
  _BYTE *v55; // rax
  int v56; // r12d
  __int64 v57; // rax
  __int64 v58; // rdx
  __int64 v59; // rsi
  __int64 v60; // rax
  __int64 v61; // rdx
  int v62; // edi
  __int64 v63; // rax
  __int64 v64; // rdx
  int v65; // ebx
  int v66; // eax
  _BYTE *v67; // rax
  int v68; // r12d
  __int64 v69; // rax
  __int64 v70; // rdx
  __int64 v71; // rsi
  __int64 v72; // rax
  __int64 v73; // rdx
  int v74; // edi
  __int64 v75; // rax
  __int64 v76; // rdx
  int v77; // ebx
  int v78; // eax
  _BYTE *v79; // rax
  int v80; // edi
  __int64 v81; // rax
  __int64 v82; // rdx
  __int64 v83; // rax
  __int64 v84; // rax
  __int64 v85; // rdx
  __int64 v86; // rdx
  int v87; // esi
  const wchar_t *v88; // rax
  int v89; // ebx
  int v90; // eax
  void *v91; // rax
  int v92; // r15d
  __int64 v93; // rax
  __int64 v94; // rdx
  __int64 v95; // rsi
  __int64 v96; // rax
  __int64 v97; // rdx
  int v98; // edi
  __int64 v99; // rax
  __int64 v100; // rdx
  int v101; // ebx
  int v102; // eax
  void *v103; // rax
  int v104; // r15d
  __int64 v105; // rax
  __int64 v106; // rdx
  __int64 v107; // rsi
  __int64 v108; // rax
  __int64 v109; // rdx
  int v110; // edi
  __int64 v111; // rax
  __int64 v112; // rdx
  int v113; // ebx
  int v114; // eax
  void *v115; // rax
  int v116; // r15d
  __int64 v117; // rax
  __int64 v118; // rdx
  __int64 v119; // rsi
  __int64 v120; // rax
  __int64 v121; // rdx
  int v122; // edi
  __int64 v123; // rax
  __int64 v124; // rdx
  int v125; // ebx
  int v126; // eax
  void *v127; // rax
  int v128; // r15d
  __int64 v129; // rax
  __int64 v130; // rdx
  __int64 v131; // rsi
  __int64 v132; // rax
  __int64 v133; // rdx
  int v134; // edi
  __int64 v135; // rax
  __int64 v136; // rdx
  int v137; // ebx
  int v138; // eax
  void *v139; // rax
  int v140; // r15d
  __int64 v141; // rax
  __int64 v142; // rdx
  __int64 v143; // rsi
  __int64 v144; // rax
  __int64 v145; // rdx
  int v146; // edi
  __int64 v147; // rax
  __int64 v148; // rdx
  int v149; // ebx
  int v150; // eax
  void *v151; // rax
  int v152; // r15d
  __int64 v153; // rax
  __int64 v154; // rdx
  __int64 v155; // rsi
  __int64 v156; // rax
  __int64 v157; // rdx
  int v158; // edi
  __int64 v159; // rax
  __int64 v160; // rdx
  int v161; // ebx
  int v162; // eax
  void *v163; // rax
  int v164; // r15d
  __int64 v165; // rax
  __int64 v166; // rdx
  __int64 v167; // rsi
  __int64 v168; // rax
  __int64 v169; // rdx
  int v170; // edi
  __int64 v171; // rax
  __int64 v172; // rdx
  int v173; // ebx
  int v174; // eax
  void *v175; // rax
  int v176; // r15d
  __int64 v177; // rax
  __int64 v178; // rdx
  __int64 v179; // rsi
  __int64 v180; // rax
  __int64 v181; // rdx
  int v182; // edi
  __int64 v183; // rax
  __int64 v184; // rdx
  int v185; // ebx
  int v186; // eax
  __int64 v187; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE *v188; // [rsp+38h] [rbp-C8h]
  _BYTE *v189; // [rsp+40h] [rbp-C0h]
  _BYTE *v190; // [rsp+48h] [rbp-B8h]
  _BYTE *v191; // [rsp+50h] [rbp-B0h]
  void *v192; // [rsp+58h] [rbp-A8h]
  _BYTE v193[32]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v194[32]; // [rsp+80h] [rbp-80h] BYREF
  int v195; // [rsp+A0h] [rbp-60h]
  _BYTE v196[32]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v197[32]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v198; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v199[32]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v200[32]; // [rsp+110h] [rbp+10h] BYREF
  WCHAR Buffer[264]; // [rsp+130h] [rbp+30h] BYREF

  LOBYTE(v2) = 0;
  v195 = 0;
  if ( !*((_BYTE *)this + 64) )
  {
    LockSentry<CriticalSection,0>::LockSentry<CriticalSection,0>(&v198, (char *)this + 72);
    if ( !*((_BYTE *)this + 64) )
    {
      memset_0(Buffer, 0, 0x208u);
      if ( !GetSystemDirectoryW(Buffer, 0x104u) )
        EapHost::EapException::Throw(L"GetSystemDirectory failed", L"*", -2147024809);
      _o_wcscat_s(Buffer, 260, L"\\eappgnui.dll");
      v3 = std::_WChar_traits<wchar_t>::length(Buffer);
      std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Assign<wchar_t>(
        (char *)this + 424,
        Buffer,
        v3);
      EapLm::Peer::BaseEapMethodConfig::LoadConfig(this);
      Module = HeapAllocator::Alloc(0x110u);
      v5 = (int)Module;
      v187 = (__int64)Module;
      v6 = (char *)this + 1000;
      v7 = (char *)this + 968;
      if ( Module )
      {
        v188 = v196;
        v8 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 1000);
        v10 = ConvertWideCharToMultiByte(v196, v9, v8);
        v189 = v197;
        v11 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 968);
        v13 = ConvertWideCharToMultiByte(v197, v12, v11);
        v190 = v193;
        v14 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 744);
        v16 = ConvertWideCharToMultiByte(v193, v15, v14);
        v17 = std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
                v194,
                (char *)this + 328);
        v18 = (char *)this + 16;
        Module = (void *)EapLm::DelayLoadModule::DelayLoadModule(v5, v17, v16, v13, v10, (__int64)this + 16);
        v6 = (char *)this + 1000;
        v7 = (char *)this + 968;
      }
      else
      {
        v18 = (char *)this + 16;
      }
      v187 = (__int64)Module;
      std::unique_ptr<EapLm::DelayLoadModule>::operator=<std::default_delete<EapLm::DelayLoadModule>,0>(
        (char *)this + 128,
        &v187);
      std::unique_ptr<EapLm::DelayLoadModule>::~unique_ptr<EapLm::DelayLoadModule>(&v187);
      v19 = HeapAllocator::Alloc(0x110u);
      v20 = (int)v19;
      v191 = v19;
      if ( v19 )
      {
        v190 = v194;
        v21 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v6);
        v23 = ConvertWideCharToMultiByte(v194, v22, v21);
        v189 = v193;
        v24 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v7);
        v26 = ConvertWideCharToMultiByte(v193, v25, v24);
        v188 = v197;
        v27 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 776);
        v29 = ConvertWideCharToMultiByte(v197, v28, v27);
        v30 = std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
                v196,
                (char *)this + 328);
        v19 = (_BYTE *)EapLm::DelayLoadModule::DelayLoadModule(v20, v30, v29, v26, v23, (__int64)v18);
      }
      v187 = (__int64)v19;
      std::unique_ptr<EapLm::DelayLoadModule>::operator=<std::default_delete<EapLm::DelayLoadModule>,0>(
        (char *)this + 136,
        &v187);
      std::unique_ptr<EapLm::DelayLoadModule>::~unique_ptr<EapLm::DelayLoadModule>(&v187);
      v31 = HeapAllocator::Alloc(0x110u);
      v32 = (int)v31;
      v191 = v31;
      if ( v31 )
      {
        v190 = v194;
        v33 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 1000);
        v35 = ConvertWideCharToMultiByte(v194, v34, v33);
        v189 = v193;
        v36 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 968);
        v38 = ConvertWideCharToMultiByte(v193, v37, v36);
        v188 = v197;
        v39 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 808);
        v41 = ConvertWideCharToMultiByte(v197, v40, v39);
        v42 = std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
                v196,
                (char *)this + 328);
        v31 = (_BYTE *)EapLm::DelayLoadModule::DelayLoadModule(v32, v42, v41, v38, v35, (__int64)v18);
      }
      v187 = (__int64)v31;
      std::unique_ptr<EapLm::DelayLoadModule>::operator=<std::default_delete<EapLm::DelayLoadModule>,0>(
        (char *)this + 144,
        &v187);
      std::unique_ptr<EapLm::DelayLoadModule>::~unique_ptr<EapLm::DelayLoadModule>(&v187);
      v43 = HeapAllocator::Alloc(0x110u);
      v44 = (int)v43;
      v191 = v43;
      if ( v43 )
      {
        v190 = v194;
        v45 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 1000);
        v47 = ConvertWideCharToMultiByte(v194, v46, v45);
        v189 = v193;
        v48 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 968);
        v50 = ConvertWideCharToMultiByte(v193, v49, v48);
        v188 = v197;
        v51 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 840);
        v53 = ConvertWideCharToMultiByte(v197, v52, v51);
        v54 = std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
                v196,
                (char *)this + 360);
        v43 = (_BYTE *)EapLm::DelayLoadModule::DelayLoadModule(v44, v54, v53, v50, v47, (__int64)v18);
      }
      v187 = (__int64)v43;
      std::unique_ptr<EapLm::DelayLoadModule>::operator=<std::default_delete<EapLm::DelayLoadModule>,0>(
        (char *)this + 152,
        &v187);
      std::unique_ptr<EapLm::DelayLoadModule>::~unique_ptr<EapLm::DelayLoadModule>(&v187);
      v55 = HeapAllocator::Alloc(0x110u);
      v56 = (int)v55;
      v191 = v55;
      if ( v55 )
      {
        v190 = v194;
        v57 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 1000);
        v59 = ConvertWideCharToMultiByte(v194, v58, v57);
        v189 = v193;
        v60 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 968);
        v62 = ConvertWideCharToMultiByte(v193, v61, v60);
        v188 = v197;
        v63 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 872);
        v65 = ConvertWideCharToMultiByte(v197, v64, v63);
        v66 = std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
                v196,
                (char *)this + 328);
        v55 = (_BYTE *)EapLm::DelayLoadModule::DelayLoadModule(v56, v66, v65, v62, v59, (__int64)v18);
      }
      v187 = (__int64)v55;
      std::unique_ptr<EapLm::DelayLoadModule>::operator=<std::default_delete<EapLm::DelayLoadModule>,0>(
        (char *)this + 160,
        &v187);
      std::unique_ptr<EapLm::DelayLoadModule>::~unique_ptr<EapLm::DelayLoadModule>(&v187);
      v67 = HeapAllocator::Alloc(0x110u);
      v68 = (int)v67;
      v191 = v67;
      if ( v67 )
      {
        v190 = v194;
        v69 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 1000);
        v71 = ConvertWideCharToMultiByte(v194, v70, v69);
        v189 = v193;
        v72 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 968);
        v74 = ConvertWideCharToMultiByte(v193, v73, v72);
        v188 = v197;
        v75 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 904);
        v77 = ConvertWideCharToMultiByte(v197, v76, v75);
        v78 = std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
                v196,
                (char *)this + 328);
        v67 = (_BYTE *)EapLm::DelayLoadModule::DelayLoadModule(v68, v78, v77, v74, v71, (__int64)v18);
      }
      v187 = (__int64)v67;
      std::unique_ptr<EapLm::DelayLoadModule>::operator=<std::default_delete<EapLm::DelayLoadModule>,0>(
        (char *)this + 168,
        &v187);
      std::unique_ptr<EapLm::DelayLoadModule>::~unique_ptr<EapLm::DelayLoadModule>(&v187);
      v79 = HeapAllocator::Alloc(0x110u);
      v80 = (int)v79;
      v191 = v79;
      if ( v79 )
      {
        v190 = v194;
        v81 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 1000);
        v187 = ConvertWideCharToMultiByte(v194, v82, v81);
        v189 = v193;
        if ( *((_BYTE *)this + 257) )
        {
          v83 = std::basic_string<char,std::char_traits<char>,StdAllocator<char>>::basic_string<char,std::char_traits<char>,StdAllocator<char>>(
                  v200,
                  "EapPeerFreeMemory");
          v2 = 1;
        }
        else
        {
          v84 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 968);
          v83 = ConvertWideCharToMultiByte(v199, v85, v84);
          v2 = 2;
        }
        v195 = v2;
        v87 = std::basic_string<char,std::char_traits<char>,StdAllocator<char>>::basic_string<char,std::char_traits<char>,StdAllocator<char>>(
                v193,
                v83);
        v188 = v197;
        if ( *((_BYTE *)this + 257) )
          v88 = L"EapPeerInvokeIdentityUI";
        else
          v88 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 936);
        v89 = ConvertWideCharToMultiByte(v197, v86, v88);
        v90 = std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
                v196,
                (char *)this + (*((_BYTE *)this + 257) != 0 ? 424LL : 392LL));
        v79 = (_BYTE *)EapLm::DelayLoadModule::DelayLoadModule(v80, v90, v89, v87, v187, (__int64)v18);
      }
      v187 = (__int64)v79;
      std::unique_ptr<EapLm::DelayLoadModule>::operator=<std::default_delete<EapLm::DelayLoadModule>,0>(
        (char *)this + 176,
        &v187);
      std::unique_ptr<EapLm::DelayLoadModule>::~unique_ptr<EapLm::DelayLoadModule>(&v187);
      if ( (v2 & 2) != 0 )
      {
        LOBYTE(v2) = v2 & 0xFD;
        std::basic_string<char,std::char_traits<char>,StdAllocator<char>>::_Tidy_deallocate(v199);
      }
      if ( (v2 & 1) != 0 )
        std::basic_string<char,std::char_traits<char>,StdAllocator<char>>::_Tidy_deallocate(v200);
      v91 = HeapAllocator::Alloc(0x110u);
      v92 = (int)v91;
      v192 = v91;
      if ( v91 )
      {
        v191 = v200;
        v93 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 1000);
        v95 = ConvertWideCharToMultiByte(v200, v94, v93);
        v190 = v199;
        v96 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 968);
        v98 = ConvertWideCharToMultiByte(v199, v97, v96);
        v189 = v194;
        v99 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 1032);
        v101 = ConvertWideCharToMultiByte(v194, v100, v99);
        v102 = std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
                 v193,
                 (char *)this + 328);
        v91 = (void *)EapLm::DelayLoadModule::DelayLoadModule(v92, v102, v101, v98, v95, (__int64)v18);
      }
      v187 = (__int64)v91;
      std::unique_ptr<EapLm::DelayLoadModule>::operator=<std::default_delete<EapLm::DelayLoadModule>,0>(
        (char *)this + 184,
        &v187);
      std::unique_ptr<EapLm::DelayLoadModule>::~unique_ptr<EapLm::DelayLoadModule>(&v187);
      v103 = HeapAllocator::Alloc(0x110u);
      v104 = (int)v103;
      v192 = v103;
      if ( v103 )
      {
        v191 = v200;
        v105 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 1000);
        v107 = ConvertWideCharToMultiByte(v200, v106, v105);
        v190 = v199;
        v108 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 968);
        v110 = ConvertWideCharToMultiByte(v199, v109, v108);
        v189 = v194;
        v111 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 1064);
        v113 = ConvertWideCharToMultiByte(v194, v112, v111);
        v114 = std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
                 v193,
                 (char *)this + 328);
        v103 = (void *)EapLm::DelayLoadModule::DelayLoadModule(v104, v114, v113, v110, v107, (__int64)v18);
      }
      v187 = (__int64)v103;
      std::unique_ptr<EapLm::DelayLoadModule>::operator=<std::default_delete<EapLm::DelayLoadModule>,0>(
        (char *)this + 192,
        &v187);
      std::unique_ptr<EapLm::DelayLoadModule>::~unique_ptr<EapLm::DelayLoadModule>(&v187);
      v115 = HeapAllocator::Alloc(0x110u);
      v116 = (int)v115;
      v192 = v115;
      if ( v115 )
      {
        v191 = v200;
        v117 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 1000);
        v119 = ConvertWideCharToMultiByte(v200, v118, v117);
        v190 = v199;
        v120 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 968);
        v122 = ConvertWideCharToMultiByte(v199, v121, v120);
        v189 = v194;
        v123 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 1096);
        v125 = ConvertWideCharToMultiByte(v194, v124, v123);
        v126 = std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
                 v193,
                 (char *)this + 328);
        v115 = (void *)EapLm::DelayLoadModule::DelayLoadModule(v116, v126, v125, v122, v119, (__int64)v18);
      }
      v187 = (__int64)v115;
      std::unique_ptr<EapLm::DelayLoadModule>::operator=<std::default_delete<EapLm::DelayLoadModule>,0>(
        (char *)this + 200,
        &v187);
      std::unique_ptr<EapLm::DelayLoadModule>::~unique_ptr<EapLm::DelayLoadModule>(&v187);
      v127 = HeapAllocator::Alloc(0x110u);
      v128 = (int)v127;
      v192 = v127;
      if ( v127 )
      {
        v191 = v200;
        v129 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 1000);
        v131 = ConvertWideCharToMultiByte(v200, v130, v129);
        v190 = v199;
        v132 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 968);
        v134 = ConvertWideCharToMultiByte(v199, v133, v132);
        v189 = v194;
        v135 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 1128);
        v137 = ConvertWideCharToMultiByte(v194, v136, v135);
        v138 = std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
                 v193,
                 (char *)this + 328);
        v127 = (void *)EapLm::DelayLoadModule::DelayLoadModule(v128, v138, v137, v134, v131, (__int64)v18);
      }
      v187 = (__int64)v127;
      std::unique_ptr<EapLm::DelayLoadModule>::operator=<std::default_delete<EapLm::DelayLoadModule>,0>(
        (char *)this + 208,
        &v187);
      std::unique_ptr<EapLm::DelayLoadModule>::~unique_ptr<EapLm::DelayLoadModule>(&v187);
      v139 = HeapAllocator::Alloc(0x110u);
      v140 = (int)v139;
      v192 = v139;
      if ( v139 )
      {
        v191 = v200;
        v141 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 1000);
        v143 = ConvertWideCharToMultiByte(v200, v142, v141);
        v190 = v199;
        v144 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 968);
        v146 = ConvertWideCharToMultiByte(v199, v145, v144);
        v189 = v194;
        v147 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 1160);
        v149 = ConvertWideCharToMultiByte(v194, v148, v147);
        v150 = std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
                 v193,
                 (char *)this + 328);
        v139 = (void *)EapLm::DelayLoadModule::DelayLoadModule(v140, v150, v149, v146, v143, (__int64)v18);
      }
      v187 = (__int64)v139;
      std::unique_ptr<EapLm::DelayLoadModule>::operator=<std::default_delete<EapLm::DelayLoadModule>,0>(
        (char *)this + 216,
        &v187);
      std::unique_ptr<EapLm::DelayLoadModule>::~unique_ptr<EapLm::DelayLoadModule>(&v187);
      v151 = HeapAllocator::Alloc(0x110u);
      v152 = (int)v151;
      v192 = v151;
      if ( v151 )
      {
        v191 = v200;
        v153 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 1000);
        v155 = ConvertWideCharToMultiByte(v200, v154, v153);
        v190 = v199;
        v156 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 968);
        v158 = ConvertWideCharToMultiByte(v199, v157, v156);
        v189 = v194;
        v159 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 1192);
        v161 = ConvertWideCharToMultiByte(v194, v160, v159);
        v162 = std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
                 v193,
                 (char *)this + 328);
        v151 = (void *)EapLm::DelayLoadModule::DelayLoadModule(v152, v162, v161, v158, v155, (__int64)v18);
      }
      v187 = (__int64)v151;
      std::unique_ptr<EapLm::DelayLoadModule>::operator=<std::default_delete<EapLm::DelayLoadModule>,0>(
        (char *)this + 224,
        &v187);
      std::unique_ptr<EapLm::DelayLoadModule>::~unique_ptr<EapLm::DelayLoadModule>(&v187);
      v163 = HeapAllocator::Alloc(0x110u);
      v164 = (int)v163;
      v192 = v163;
      if ( v163 )
      {
        v191 = v200;
        v165 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 1000);
        v167 = ConvertWideCharToMultiByte(v200, v166, v165);
        v190 = v199;
        v168 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 968);
        v170 = ConvertWideCharToMultiByte(v199, v169, v168);
        v189 = v194;
        v171 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 1224);
        v173 = ConvertWideCharToMultiByte(v194, v172, v171);
        v174 = std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
                 v193,
                 (char *)this + 328);
        v163 = (void *)EapLm::DelayLoadModule::DelayLoadModule(v164, v174, v173, v170, v167, (__int64)v18);
      }
      v187 = (__int64)v163;
      std::unique_ptr<EapLm::DelayLoadModule>::operator=<std::default_delete<EapLm::DelayLoadModule>,0>(
        (char *)this + 232,
        &v187);
      std::unique_ptr<EapLm::DelayLoadModule>::~unique_ptr<EapLm::DelayLoadModule>(&v187);
      v175 = HeapAllocator::Alloc(0x110u);
      v176 = (int)v175;
      v192 = v175;
      if ( v175 )
      {
        v191 = v200;
        v177 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 1000);
        v179 = ConvertWideCharToMultiByte(v200, v178, v177);
        v190 = v199;
        v180 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 968);
        v182 = ConvertWideCharToMultiByte(v199, v181, v180);
        v189 = v194;
        v183 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 1256);
        v185 = ConvertWideCharToMultiByte(v194, v184, v183);
        v186 = std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
                 v193,
                 (char *)this + 328);
        v175 = (void *)EapLm::DelayLoadModule::DelayLoadModule(v176, v186, v185, v182, v179, (__int64)v18);
      }
      v187 = (__int64)v175;
      std::unique_ptr<EapLm::DelayLoadModule>::operator=<std::default_delete<EapLm::DelayLoadModule>,0>(
        (char *)this + 240,
        &v187);
      std::unique_ptr<EapLm::DelayLoadModule>::~unique_ptr<EapLm::DelayLoadModule>(&v187);
      *((_BYTE *)this + 256) = 1;
      *((_BYTE *)this + 64) = 1;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v198 + 16));
  }
}

```

## disassembly

```asm
0x180020590  push    rbp
0x180020592  push    rbx
0x180020593  push    rsi
0x180020594  push    rdi
0x180020595  push    r12
0x180020597  push    r13
0x180020599  push    r14
0x18002059b  push    r15
0x18002059d  lea     rbp, [rsp-258h]
0x1800205a5  sub     rsp, 358h
0x1800205ac  mov     rax, cs:__security_cookie
0x1800205b3  xor     rax, rsp
0x1800205b6  mov     [rbp+290h+var_50], rax
0x1800205bd  mov     r14, rcx
0x1800205c0  xor     r15d, r15d
0x1800205c3  mov     [rbp+290h+var_2F0], r15d
0x1800205c7  cmp     [rcx+40h], r15b
0x1800205cb  jnz     loc_18002137F
0x1800205d1  lea     rdx, [rcx+48h]
0x1800205d5  lea     rcx, [rbp+290h+var_2A8]
0x1800205d9  call    ??0?$LockSentry@VCriticalSection@@$0A@@@QEAA@AEAVCriticalSection@@@Z; LockSentry<CriticalSection,0>::LockSentry<CriticalSection,0>(CriticalSection &)
0x1800205de  nop
0x1800205df  cmp     [r14+40h], r15b
0x1800205e3  jnz     loc_180021371
0x1800205e9  xor     edx, edx; Val
0x1800205eb  mov     r8d, 208h; Size
0x1800205f1  lea     rcx, [rbp+290h+Buffer]; void *
0x1800205f5  call    memset_0
0x1800205fa  mov     ebx, 104h
0x1800205ff  mov     edx, ebx; uSize
0x180020601  lea     rcx, [rbp+290h+Buffer]; lpBuffer
0x180020605  call    cs:__imp_GetSystemDirectoryW
0x18002060b  test    eax, eax
0x18002060d  jnz     short loc_180020629
0x18002060f  mov     r8d, 80070057h; int
0x180020615  lea     rdx, asc_18003C940; "*"
0x18002061c  lea     rcx, aGetsystemdirec; "GetSystemDirectory failed"
0x180020623  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
0x180020629  lea     r8, aEappgnuiDll; "\\eappgnui.dll"
0x180020630  mov     rdx, rbx
0x180020633  lea     rcx, [rbp+290h+Buffer]
0x180020637  call    cs:__imp__o_wcscat_s
0x18002063d  lea     rcx, [rbp+290h+Buffer]
0x180020641  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x180020646  mov     r8, rax
0x180020649  lea     rcx, [r14+1A8h]
0x180020650  lea     rdx, [rbp+290h+Buffer]
0x180020654  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAAEAV01@QEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x180020659  mov     rcx, r14; this
0x18002065c  call    ?LoadConfig@BaseEapMethodConfig@Peer@EapLm@@IEAAXXZ; EapLm::Peer::BaseEapMethodConfig::LoadConfig(void)
0x180020661  mov     ecx, 110h; unsigned __int64
0x180020666  call    ?Alloc@HeapAllocator@@SAPEAX_K@Z; HeapAllocator::Alloc(unsigned __int64)
0x18002066b  mov     r12, rax
0x18002066e  mov     [rsp+390h+var_360], rax
0x180020673  lea     rbx, [r14+3E8h]
0x18002067a  lea     rdi, [r14+3C8h]
0x180020681  test    rax, rax
0x180020684  jz      loc_18002072F
0x18002068a  lea     rax, [rbp+290h+var_2E8]
0x18002068e  mov     [rsp+390h+var_358], rax
0x180020693  mov     rcx, rbx
0x180020696  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002069b  mov     r8, rax
0x18002069e  lea     rcx, [rbp+290h+var_2E8]
0x1800206a2  call    ?ConvertWideCharToMultiByte@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$StdAllocator@D@@@std@@IPEB_W@Z; ConvertWideCharToMultiByte(uint,wchar_t const *)
0x1800206a7  mov     rsi, rax
0x1800206aa  lea     rax, [rbp+290h+var_2C8]
0x1800206ae  mov     [rsp+390h+var_350], rax
0x1800206b3  mov     rcx, rdi
0x1800206b6  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800206bb  mov     r8, rax
0x1800206be  lea     rcx, [rbp+290h+var_2C8]
0x1800206c2  call    ?ConvertWideCharToMultiByte@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$StdAllocator@D@@@std@@IPEB_W@Z; ConvertWideCharToMultiByte(uint,wchar_t const *)
0x1800206c7  mov     rdi, rax
0x1800206ca  lea     rax, [rsp+390h+var_330]
0x1800206cf  mov     [rsp+390h+var_348], rax
0x1800206d4  lea     rcx, [r14+2E8h]
0x1800206db  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800206e0  mov     r8, rax
0x1800206e3  lea     rcx, [rsp+390h+var_330]
0x1800206e8  call    ?ConvertWideCharToMultiByte@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$StdAllocator@D@@@std@@IPEB_W@Z; ConvertWideCharToMultiByte(uint,wchar_t const *)
0x1800206ed  mov     rbx, rax
0x1800206f0  lea     rdx, [r14+148h]
0x1800206f7  lea     rcx, [rbp+290h+var_310]
0x1800206fb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@AEBV01@@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x180020700  lea     r13, [r14+10h]
0x180020704  mov     [rsp+390h+var_368], r13
0x180020709  mov     [rsp+390h+var_370], rsi
0x18002070e  mov     r9, rdi
0x180020711  mov     r8, rbx
0x180020714  mov     rdx, rax
0x180020717  mov     rcx, r12
0x18002071a  call    ??0DelayLoadModule@EapLm@@QEAA@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$basic_string@DU?$char_traits@D@std@@V?$StdAllocator@D@@@3@11AEBU_EAP_METHOD_TYPE@@@Z; EapLm::DelayLoadModule::DelayLoadModule(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,std::basic_string<char,std::char_traits<char>,StdAllocator<char>>,std::basic_string<char,std::char_traits<char>,StdAllocator<char>>,std::basic_string<char,std::char_traits<char>,StdAllocator<char>>,_EAP_METHOD_TYPE const &)
0x18002071f  lea     rbx, [r14+3E8h]
0x180020726  lea     rdi, [r14+3C8h]
0x18002072d  jmp     short loc_180020733
0x18002072f  lea     r13, [r14+10h]
0x180020733  mov     [rsp+390h+var_360], rax
0x180020738  lea     rcx, [r14+80h]
0x18002073f  lea     rdx, [rsp+390h+var_360]
0x180020744  call    ??$?4U?$default_delete@VDelayLoadModule@EapLm@@@std@@$0A@@?$unique_ptr@VDelayLoadModule@EapLm@@U?$default_delete@VDelayLoadModule@EapLm@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<EapLm::DelayLoadModule>::operator=<std::default_delete<EapLm::DelayLoadModule>,0>(std::unique_ptr<EapLm::DelayLoadModule> &&)
0x180020749  lea     rcx, [rsp+390h+var_360]
0x18002074e  call    ??1?$unique_ptr@VDelayLoadModule@EapLm@@U?$default_delete@VDelayLoadModule@EapLm@@@std@@@std@@QEAA@XZ; std::unique_ptr<EapLm::DelayLoadModule>::~unique_ptr<EapLm::DelayLoadModule>(void)
0x180020753  mov     ecx, 110h; unsigned __int64
0x180020758  call    ?Alloc@HeapAllocator@@SAPEAX_K@Z; HeapAllocator::Alloc(unsigned __int64)
0x18002075d  mov     r12, rax
0x180020760  mov     [rsp+390h+var_340], rax
0x180020765  test    rax, rax
0x180020768  jz      loc_180020801
0x18002076e  lea     rax, [rbp+290h+var_310]
0x180020772  mov     [rsp+390h+var_348], rax
0x180020777  mov     rcx, rbx
0x18002077a  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002077f  mov     r8, rax
0x180020782  lea     rcx, [rbp+290h+var_310]
0x180020786  call    ?ConvertWideCharToMultiByte@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$StdAllocator@D@@@std@@IPEB_W@Z; ConvertWideCharToMultiByte(uint,wchar_t const *)
0x18002078b  mov     rsi, rax
0x18002078e  lea     rax, [rsp+390h+var_330]
0x180020793  mov     [rsp+390h+var_350], rax
0x180020798  mov     rcx, rdi
0x18002079b  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800207a0  mov     r8, rax
0x1800207a3  lea     rcx, [rsp+390h+var_330]
0x1800207a8  call    ?ConvertWideCharToMultiByte@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$StdAllocator@D@@@std@@IPEB_W@Z; ConvertWideCharToMultiByte(uint,wchar_t const *)
0x1800207ad  mov     rdi, rax
0x1800207b0  lea     rax, [rbp+290h+var_2C8]
0x1800207b4  mov     [rsp+390h+var_358], rax
0x1800207b9  lea     rcx, [r14+308h]
0x1800207c0  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800207c5  mov     r8, rax
0x1800207c8  lea     rcx, [rbp+290h+var_2C8]
0x1800207cc  call    ?ConvertWideCharToMultiByte@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$StdAllocator@D@@@std@@IPEB_W@Z; ConvertWideCharToMultiByte(uint,wchar_t const *)
0x1800207d1  mov     rbx, rax
0x1800207d4  lea     rdx, [r14+148h]
0x1800207db  lea     rcx, [rbp+290h+var_2E8]
0x1800207df  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@AEBV01@@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x1800207e4  nop
0x1800207e5  mov     [rsp+390h+var_368], r13
0x1800207ea  mov     [rsp+390h+var_370], rsi
0x1800207ef  mov     r9, rdi
0x1800207f2  mov     r8, rbx
0x1800207f5  mov     rdx, rax
0x1800207f8  mov     rcx, r12
0x1800207fb  call    ??0DelayLoadModule@EapLm@@QEAA@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$basic_string@DU?$char_traits@D@std@@V?$StdAllocator@D@@@3@11AEBU_EAP_METHOD_TYPE@@@Z; EapLm::DelayLoadModule::DelayLoadModule(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,std::basic_string<char,std::char_traits<char>,StdAllocator<char>>,std::basic_string<char,std::char_traits<char>,StdAllocator<char>>,std::basic_string<char,std::char_traits<char>,StdAllocator<char>>,_EAP_METHOD_TYPE const &)
0x180020800  nop
0x180020801  mov     [rsp+390h+var_360], rax
0x180020806  lea     rcx, [r14+88h]
0x18002080d  lea     rdx, [rsp+390h+var_360]
0x180020812  call    ??$?4U?$default_delete@VDelayLoadModule@EapLm@@@std@@$0A@@?$unique_ptr@VDelayLoadModule@EapLm@@U?$default_delete@VDelayLoadModule@EapLm@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<EapLm::DelayLoadModule>::operator=<std::default_delete<EapLm::DelayLoadModule>,0>(std::unique_ptr<EapLm::DelayLoadModule> &&)
0x180020817  lea     rcx, [rsp+390h+var_360]
0x18002081c  call    ??1?$unique_ptr@VDelayLoadModule@EapLm@@U?$default_delete@VDelayLoadModule@EapLm@@@std@@@std@@QEAA@XZ; std::unique_ptr<EapLm::DelayLoadModule>::~unique_ptr<EapLm::DelayLoadModule>(void)
0x180020821  mov     ecx, 110h; unsigned __int64
0x180020826  call    ?Alloc@HeapAllocator@@SAPEAX_K@Z; HeapAllocator::Alloc(unsigned __int64)
0x18002082b  mov     r12, rax
0x18002082e  mov     [rsp+390h+var_340], rax
0x180020833  test    rax, rax
0x180020836  jz      loc_1800208D7
0x18002083c  lea     rax, [rbp+290h+var_310]
0x180020840  mov     [rsp+390h+var_348], rax
0x180020845  lea     rcx, [r14+3E8h]
0x18002084c  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180020851  mov     r8, rax
0x180020854  lea     rcx, [rbp+290h+var_310]
0x180020858  call    ?ConvertWideCharToMultiByte@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$StdAllocator@D@@@std@@IPEB_W@Z; ConvertWideCharToMultiByte(uint,wchar_t const *)
0x18002085d  mov     rsi, rax
0x180020860  lea     rax, [rsp+390h+var_330]
0x180020865  mov     [rsp+390h+var_350], rax
0x18002086a  lea     rcx, [r14+3C8h]
0x180020871  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180020876  mov     r8, rax
0x180020879  lea     rcx, [rsp+390h+var_330]
0x18002087e  call    ?ConvertWideCharToMultiByte@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$StdAllocator@D@@@std@@IPEB_W@Z; ConvertWideCharToMultiByte(uint,wchar_t const *)
0x180020883  mov     rdi, rax
0x180020886  lea     rax, [rbp+290h+var_2C8]
0x18002088a  mov     [rsp+390h+var_358], rax
0x18002088f  lea     rcx, [r14+328h]
0x180020896  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002089b  mov     r8, rax
0x18002089e  lea     rcx, [rbp+290h+var_2C8]
0x1800208a2  call    ?ConvertWideCharToMultiByte@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$StdAllocator@D@@@std@@IPEB_W@Z; ConvertWideCharToMultiByte(uint,wchar_t const *)
0x1800208a7  mov     rbx, rax
0x1800208aa  lea     rdx, [r14+148h]
0x1800208b1  lea     rcx, [rbp+290h+var_2E8]
0x1800208b5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@AEBV01@@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x1800208ba  nop
0x1800208bb  mov     [rsp+390h+var_368], r13
0x1800208c0  mov     [rsp+390h+var_370], rsi
0x1800208c5  mov     r9, rdi
0x1800208c8  mov     r8, rbx
0x1800208cb  mov     rdx, rax
0x1800208ce  mov     rcx, r12
0x1800208d1  call    ??0DelayLoadModule@EapLm@@QEAA@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$basic_string@DU?$char_traits@D@std@@V?$StdAllocator@D@@@3@11AEBU_EAP_METHOD_TYPE@@@Z; EapLm::DelayLoadModule::DelayLoadModule(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,std::basic_string<char,std::char_traits<char>,StdAllocator<char>>,std::basic_string<char,std::char_traits<char>,StdAllocator<char>>,std::basic_string<char,std::char_traits<char>,StdAllocator<char>>,_EAP_METHOD_TYPE const &)
0x1800208d6  nop
0x1800208d7  mov     [rsp+390h+var_360], rax
0x1800208dc  lea     rcx, [r14+90h]
0x1800208e3  lea     rdx, [rsp+390h+var_360]
0x1800208e8  call    ??$?4U?$default_delete@VDelayLoadModule@EapLm@@@std@@$0A@@?$unique_ptr@VDelayLoadModule@EapLm@@U?$default_delete@VDelayLoadModule@EapLm@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<EapLm::DelayLoadModule>::operator=<std::default_delete<EapLm::DelayLoadModule>,0>(std::unique_ptr<EapLm::DelayLoadModule> &&)
0x1800208ed  lea     rcx, [rsp+390h+var_360]
0x1800208f2  call    ??1?$unique_ptr@VDelayLoadModule@EapLm@@U?$default_delete@VDelayLoadModule@EapLm@@@std@@@std@@QEAA@XZ; std::unique_ptr<EapLm::DelayLoadModule>::~unique_ptr<EapLm::DelayLoadModule>(void)
0x1800208f7  mov     ecx, 110h; unsigned __int64
0x1800208fc  call    ?Alloc@HeapAllocator@@SAPEAX_K@Z; HeapAllocator::Alloc(unsigned __int64)
0x180020901  mov     r12, rax
0x180020904  mov     [rsp+390h+var_340], rax
0x180020909  test    rax, rax
0x18002090c  jz      loc_1800209AD
0x180020912  lea     rax, [rbp+290h+var_310]
0x180020916  mov     [rsp+390h+var_348], rax
0x18002091b  lea     rcx, [r14+3E8h]
0x180020922  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180020927  mov     r8, rax
0x18002092a  lea     rcx, [rbp+290h+var_310]
0x18002092e  call    ?ConvertWideCharToMultiByte@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$StdAllocator@D@@@std@@IPEB_W@Z; ConvertWideCharToMultiByte(uint,wchar_t const *)
0x180020933  mov     rsi, rax
0x180020936  lea     rax, [rsp+390h+var_330]
0x18002093b  mov     [rsp+390h+var_350], rax
0x180020940  lea     rcx, [r14+3C8h]
0x180020947  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002094c  mov     r8, rax
0x18002094f  lea     rcx, [rsp+390h+var_330]
0x180020954  call    ?ConvertWideCharToMultiByte@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$StdAllocator@D@@@std@@IPEB_W@Z; ConvertWideCharToMultiByte(uint,wchar_t const *)
0x180020959  mov     rdi, rax
0x18002095c  lea     rax, [rbp+290h+var_2C8]
0x180020960  mov     [rsp+390h+var_358], rax
0x180020965  lea     rcx, [r14+348h]
0x18002096c  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180020971  mov     r8, rax
0x180020974  lea     rcx, [rbp+290h+var_2C8]
0x180020978  call    ?ConvertWideCharToMultiByte@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$StdAllocator@D@@@std@@IPEB_W@Z; ConvertWideCharToMultiByte(uint,wchar_t const *)
0x18002097d  mov     rbx, rax
0x180020980  lea     rdx, [r14+168h]
0x180020987  lea     rcx, [rbp+290h+var_2E8]
0x18002098b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@AEBV01@@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x180020990  nop
0x180020991  mov     [rsp+390h+var_368], r13
0x180020996  mov     [rsp+390h+var_370], rsi
0x18002099b  mov     r9, rdi
0x18002099e  mov     r8, rbx
0x1800209a1  mov     rdx, rax
0x1800209a4  mov     rcx, r12
0x1800209a7  call    ??0DelayLoadModule@EapLm@@QEAA@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$basic_string@DU?$char_traits@D@std@@V?$StdAllocator@D@@@3@11AEBU_EAP_METHOD_TYPE@@@Z; EapLm::DelayLoadModule::DelayLoadModule(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,std::basic_string<char,std::char_traits<char>,StdAllocator<char>>,std::basic_string<char,std::char_traits<char>,StdAllocator<char>>,std::basic_string<char,std::char_traits<char>,StdAllocator<char>>,_EAP_METHOD_TYPE const &)
0x1800209ac  nop
0x1800209ad  mov     [rsp+390h+var_360], rax
0x1800209b2  lea     rcx, [r14+98h]
0x1800209b9  lea     rdx, [rsp+390h+var_360]
0x1800209be  call    ??$?4U?$default_delete@VDelayLoadModule@EapLm@@@std@@$0A@@?$unique_ptr@VDelayLoadModule@EapLm@@U?$default_delete@VDelayLoadModule@EapLm@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<EapLm::DelayLoadModule>::operator=<std::default_delete<EapLm::DelayLoadModule>,0>(std::unique_ptr<EapLm::DelayLoadModule> &&)
0x1800209c3  lea     rcx, [rsp+390h+var_360]
0x1800209c8  call    ??1?$unique_ptr@VDelayLoadModule@EapLm@@U?$default_delete@VDelayLoadModule@EapLm@@@std@@@std@@QEAA@XZ; std::unique_ptr<EapLm::DelayLoadModule>::~unique_ptr<EapLm::DelayLoadModule>(void)
0x1800209cd  mov     ecx, 110h; unsigned __int64
0x1800209d2  call    ?Alloc@HeapAllocator@@SAPEAX_K@Z; HeapAllocator::Alloc(unsigned __int64)
0x1800209d7  mov     r12, rax
0x1800209da  mov     [rsp+390h+var_340], rax
0x1800209df  test    rax, rax
0x1800209e2  jz      loc_180020A83
0x1800209e8  lea     rax, [rbp+290h+var_310]
0x1800209ec  mov     [rsp+390h+var_348], rax
0x1800209f1  lea     rcx, [r14+3E8h]
0x1800209f8  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800209fd  mov     r8, rax
0x180020a00  lea     rcx, [rbp+290h+var_310]
0x180020a04  call    ?ConvertWideCharToMultiByte@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$StdAllocator@D@@@std@@IPEB_W@Z; ConvertWideCharToMultiByte(uint,wchar_t const *)
0x180020a09  mov     rsi, rax
0x180020a0c  lea     rax, [rsp+390h+var_330]
0x180020a11  mov     [rsp+390h+var_350], rax
0x180020a16  lea     rcx, [r14+3C8h]
0x180020a1d  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180020a22  mov     r8, rax
0x180020a25  lea     rcx, [rsp+390h+var_330]
0x180020a2a  call    ?ConvertWideCharToMultiByte@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$StdAllocator@D@@@std@@IPEB_W@Z; ConvertWideCharToMultiByte(uint,wchar_t const *)
0x180020a2f  mov     rdi, rax
0x180020a32  lea     rax, [rbp+290h+var_2C8]
0x180020a36  mov     [rsp+390h+var_358], rax
0x180020a3b  lea     rcx, [r14+368h]
0x180020a42  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180020a47  mov     r8, rax
0x180020a4a  lea     rcx, [rbp+290h+var_2C8]
0x180020a4e  call    ?ConvertWideCharToMultiByte@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$StdAllocator@D@@@std@@IPEB_W@Z; ConvertWideCharToMultiByte(uint,wchar_t const *)
0x180020a53  mov     rbx, rax
0x180020a56  lea     rdx, [r14+148h]
0x180020a5d  lea     rcx, [rbp+290h+var_2E8]
0x180020a61  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@AEBV01@@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x180020a66  nop
0x180020a67  mov     [rsp+390h+var_368], r13
0x180020a6c  mov     [rsp+390h+var_370], rsi
0x180020a71  mov     r9, rdi
0x180020a74  mov     r8, rbx
0x180020a77  mov     rdx, rax
0x180020a7a  mov     rcx, r12
0x180020a7d  call    ??0DelayLoadModule@EapLm@@QEAA@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$basic_string@DU?$char_traits@D@std@@V?$StdAllocator@D@@@3@11AEBU_EAP_METHOD_TYPE@@@Z; EapLm::DelayLoadModule::DelayLoadModule(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,std::basic_string<char,std::char_traits<char>,StdAllocator<char>>,std::basic_string<char,std::char_traits<char>,StdAllocator<char>>,std::basic_string<char,std::char_traits<char>,StdAllocator<char>>,_EAP_METHOD_TYPE const &)
0x180020a82  nop
0x180020a83  mov     [rsp+390h+var_360], rax
0x180020a88  lea     rcx, [r14+0A0h]
0x180020a8f  lea     rdx, [rsp+390h+var_360]
0x180020a94  call    ??$?4U?$default_delete@VDelayLoadModule@EapLm@@@std@@$0A@@?$unique_ptr@VDelayLoadModule@EapLm@@U?$default_delete@VDelayLoadModule@EapLm@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<EapLm::DelayLoadModule>::operator=<std::default_delete<EapLm::DelayLoadModule>,0>(std::unique_ptr<EapLm::DelayLoadModule> &&)
0x180020a99  lea     rcx, [rsp+390h+var_360]
0x180020a9e  call    ??1?$unique_ptr@VDelayLoadModule@EapLm@@U?$default_delete@VDelayLoadModule@EapLm@@@std@@@std@@QEAA@XZ; std::unique_ptr<EapLm::DelayLoadModule>::~unique_ptr<EapLm::DelayLoadModule>(void)
0x180020aa3  mov     ecx, 110h; unsigned __int64
0x180020aa8  call    ?Alloc@HeapAllocator@@SAPEAX_K@Z; HeapAllocator::Alloc(unsigned __int64)
0x180020aad  mov     r12, rax
0x180020ab0  mov     [rsp+390h+var_340], rax
0x180020ab5  test    rax, rax
  ... truncated ...
```
