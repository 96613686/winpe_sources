# dxc::TextConvertor::FindOrCreateFontResource(IDWriteFontFace *,ushort const *,uint,bool)

- ea: `0x1801e6ff8`
- end: `0x1801e794b`
- name: `?FindOrCreateFontResource@TextConvertor@dxc@@AEAA?AV?$scope@PEAUIXpsOMFontResource@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@PEAUIDWriteFontFace@@PEBGI_N@Z`
- size: `2387`
- prototype: ``
- caller_count: `1`
- callee_count: `32`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1802561f8`

## callees

- `0x1800152a0`
- `0x18003b3a4`
- `0x180050430`
- `0x180159950`
- `0x1801e6748`
- `0x1801e6ddc`
- `0x1801e6f3c`
- `0x1801e6fb4`
- `0x1801e6ff8`
- `0x1801e7954`
- `0x1801e797c`
- `0x1801e79a4`
- `0x1801e7a2c`
- `0x1801e7a38`
- `0x1801e8e00`
- `0x1801e94c0`
- `0x1801edd7c`
- `0x1801ef5a8`
- `0x180214888`
- `0x18025acec`
- `0x18025acf8`
- `0x18025b100`
- `0x18025bb98`
- `0x180297828`
- `0x18029cdc4`
- `0x18029dbf8`
- `0x18029dc94`
- `0x18029ec84`
- `0x18029ecdc`
- `0x18029ef74`
- `0x18029f0dc`
- `0x180307010`

## import_xrefs

- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801e7635`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801e7635`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateDCW` at `0x1801e7603`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateDCW` at `0x1801e7603`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x1801e774e`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x1801e774e`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1801e775d`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1801e775d`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1801e7258`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1801e7258`
- `ext-ms-win-gdi-font-l1-1-0!GetFontFileInfo` at `0x1801e76bb`
- `ext-ms-win-gdi-font-l1-1-0!GetFontFileInfo` at `0x1801e76bb`
- `ext-ms-win-gdi-font-l1-1-0!GetFontRealizationInfo` at `0x1801e765f`
- `ext-ms-win-gdi-font-l1-1-0!GetFontRealizationInfo` at `0x1801e765f`
- `ext-ms-win-gdi-font-l1-1-0!CreateFontIndirectW` at `0x1801e75c3`
- `ext-ms-win-gdi-font-l1-1-0!CreateFontIndirectW` at `0x1801e75c3`

## pseudocode

```c
// Hidden C++ exception states: #wind=28
_QWORD **__fastcall dxc::TextConvertor::FindOrCreateFontResource(
        __int64 a1,
        _QWORD **a2,
        struct IDWriteFontFace *a3,
        unsigned __int16 *a4,
        unsigned int a5,
        char a6)
{
  int v9; // eax
  int v10; // edx
  const char *v11; // r8
  int v12; // r9d
  int v13; // edi
  __int64 (__fastcall *v14)(struct IDWriteFontFace *, int *, struct IDWriteFontFile **); // rbx
  int v15; // eax
  const char *v16; // rdx
  dxc *v17; // rcx
  const char *v18; // r8
  int v19; // r9d
  int v20; // eax
  int v21; // edx
  const char *v22; // r8
  int v23; // r9d
  int v24; // eax
  int v25; // edx
  const char *v26; // r8
  int v27; // r9d
  char v28; // r13
  unsigned int v29; // eax
  unsigned int v30; // ebx
  dxc::TextConvertor **v31; // rax
  __int64 v32; // rax
  HRESULT v33; // eax
  int v34; // edx
  const char *v35; // r8
  int v36; // r9d
  __int64 v37; // rsi
  __int64 (__fastcall *v38)(__int64, LPSTREAM, _QWORD, dxc::TextConvertor *, _DWORD, int (__fastcall ****)(_QWORD, GUID *, dxc::TextConvertor **)); // rdi
  dxc::TextConvertor *v39; // rbx
  dxc::TextConvertor *v40; // rcx
  char FSTypeMask; // al
  int v42; // edx
  int v43; // ebx
  const char *v44; // r8
  int v45; // r9d
  dxc::TextConvertor *v46; // rcx
  bool v47; // r12
  __int64 v48; // rax
  int v49; // r15d
  int (__fastcall ***v50)(_QWORD, GUID *, dxc::TextConvertor **); // rbx
  __int64 v51; // rcx
  int v52; // eax
  int v53; // edx
  const char *v54; // r8
  int v55; // r9d
  __int64 v56; // rbx
  __int64 (__fastcall *v57)(__int64, __int64 *); // rdi
  int v58; // eax
  int v59; // edx
  const char *v60; // r8
  int v61; // r9d
  __int64 v62; // rbx
  __int64 (__fastcall *v63)(__int64, __int64 *, _QWORD); // rdi
  int v64; // eax
  int v65; // edx
  const char *v66; // r8
  int v67; // r9d
  __int64 v68; // rbx
  int (__fastcall *v69)(__int64, struct IDWriteFontFace *, __int64 *); // rdi
  int v70; // eax
  int v71; // edx
  __int64 v72; // rcx
  const char *v73; // r8
  int v74; // r9d
  __int64 v75; // rax
  HFONT v76; // rax
  HFONT v77; // rsi
  HDC v78; // rdi
  HDC DCW; // rax
  char *v80; // rax
  int v81; // edx
  const char *v82; // r8
  int v83; // r9d
  char *v84; // rbx
  char *v85; // rax
  int v86; // ecx
  char v87; // al
  __int64 v88; // rax
  __int64 v89; // rax
  _QWORD **v90; // rbx
  __int64 v92; // [rsp+40h] [rbp-C0h] BYREF
  dxc::TextConvertor *v93; // [rsp+48h] [rbp-B8h] BYREF
  struct IDWriteFontFile *v94; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v95; // [rsp+58h] [rbp-A8h] BYREF
  LPSTREAM ppstm; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v97; // [rsp+68h] [rbp-98h] BYREF
  __int64 v98; // [rsp+70h] [rbp-90h] BYREF
  __int64 v99; // [rsp+78h] [rbp-88h] BYREF
  __int64 v100; // [rsp+80h] [rbp-80h] BYREF
  int v101; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v102; // [rsp+8Ch] [rbp-74h] BYREF
  char v103[8]; // [rsp+90h] [rbp-70h] BYREF
  int (__fastcall ***v104)(_QWORD, GUID *, dxc::TextConvertor **); // [rsp+98h] [rbp-68h] BYREF
  __int64 v105; // [rsp+A0h] [rbp-60h] BYREF
  char v106[16]; // [rsp+A8h] [rbp-58h] BYREF
  int v107; // [rsp+B8h] [rbp-48h]
  HDC hdc; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v109; // [rsp+C8h] [rbp-38h] BYREF
  char *v110; // [rsp+D0h] [rbp-30h]
  __int64 v111; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD **v112; // [rsp+E0h] [rbp-20h]
  unsigned __int16 *v113; // [rsp+F0h] [rbp-10h]
  _QWORD **v114; // [rsp+F8h] [rbp-8h]
  char *v115; // [rsp+100h] [rbp+0h] BYREF
  __int64 v116; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v117[24]; // [rsp+118h] [rbp+18h] BYREF
  __int16 v118; // [rsp+130h] [rbp+30h]
  _QWORD v119[4]; // [rsp+138h] [rbp+38h] BYREF
  __int128 v120; // [rsp+158h] [rbp+58h] BYREF
  __int64 v121; // [rsp+168h] [rbp+68h]
  LOGFONTW lf; // [rsp+170h] [rbp+70h] BYREF

  v113 = a4;
  v114 = a2;
  v112 = a2;
  v97 = 0;
  win_scope::detail::scope_helper<IXpsOMLinearGradientBrush *,win_scope::const_policies<win_scope::com_policies>>::reset(
    &v97,
    0);
  v97 = 0;
  v9 = (**(__int64 (__fastcall ***)(struct IDWriteFontFace *, GUID *, __int64 *))a3)(
         a3,
         &GUID_ba6f3da5_0780_4422_9fae_eab429b786b4,
         &v97);
  if ( v9 < 0 )
    dxc::ThrowHRExceptionPage((dxc *)(unsigned int)v9, v10, v11, v12);
  v13 = (*(__int64 (__fastcall **)(struct IDWriteFontFace *))(*(_QWORD *)a3 + 24LL))(a3);
  v107 = v13;
  v101 = 1;
  v94 = 0;
  v14 = *(__int64 (__fastcall **)(struct IDWriteFontFace *, int *, struct IDWriteFontFile **))(*(_QWORD *)a3 + 32LL);
  ppstm = 0;
  win_scope::scope<RefCountedObject<D2DFactoryLocking<MultiThreadedTrait>,LockingRequired,DeleteOnZeroReference> *,win_scope::const_policies<win_scope::com_policies>>::Swap<win_scope::const_policies<win_scope::com_policies>>(
    &ppstm,
    &v94);
  if ( ppstm )
    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
  v94 = 0;
  v15 = v14(a3, &v101, &v94);
  if ( v15 < 0 )
    dxc::ThrowHRExceptionPage((dxc *)(unsigned int)v15, (int)v16, v18, v19);
  if ( v101 != 1 )
    dxc::ThrowLogicException(v17, v16, (int)v18);
  v111 = 0;
  v102 = 0;
  v20 = (*(__int64 (__fastcall **)(struct IDWriteFontFile *, __int64 *, unsigned int *))(*(_QWORD *)v94 + 24LL))(
          v94,
          &v111,
          &v102);
  if ( v20 < 0 )
    dxc::ThrowHRExceptionPage((dxc *)(unsigned int)v20, v21, v22, v23);
  v116 = 0;
  std::vector<float,NonThrowingNewStlAllocator<float>>::vector<float,NonThrowingNewStlAllocator<float>>(v117);
  v118 = 0;
  std::vector<float,NonThrowingNewStlAllocator<float>>::vector<float,NonThrowingNewStlAllocator<float>>(v119);
  std::vector<unsigned char,NonThrowingNewStlAllocator<unsigned char>>::assign<unsigned char *,0>(
    v117,
    v111,
    v111 + v102);
  v24 = (*(__int64 (__fastcall **)(struct IDWriteFontFile *, __int64 *))(*(_QWORD *)v94 + 32LL))(v94, &v116);
  if ( v24 < 0 )
    dxc::ThrowHRExceptionPage((dxc *)(unsigned int)v24, v25, v26, v27);
  if ( v13 == 2 )
  {
    v28 = 1;
    if ( a6 )
      v118 = (*(__int64 (__fastcall **)(struct IDWriteFontFace *))(*(_QWORD *)a3 + 40LL))(a3);
  }
  else
  {
    v28 = 0;
  }
  v29 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v97 + 520LL))(v97);
  v30 = v29;
  if ( v29 )
  {
    std::vector<int,NonThrowingNewStlAllocator<int>>::resize(v119, v29);
    (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v97 + 528LL))(v97, v119[0], v30);
  }
  v112 = (_QWORD **)(a1 + 32);
  std::_Tree<std::_Tmap_traits<dxc::TextConvertor::TFontResourceKey,dxc::TextConvertor::TFontResourceData,dxc::TextConvertor::FontResKeyLess,NonThrowingNewStlAllocator<std::pair<dxc::TextConvertor::TFontResourceKey const,dxc::TextConvertor::TFontResourceData>>,0>>::find(
    a1 + 32,
    &v93,
    &v116);
  v31 = (dxc::TextConvertor **)std::vector<dxc::CCoordinate>::begin(a1 + 32, &hdc);
  if ( v93 == *v31 )
  {
    ppstm = 0;
    win_scope::close<IStream *,win_scope::const_policies<win_scope::com_policies>>(&ppstm);
    ppstm = 0;
    v33 = CreateStreamOnHGlobal(0, 1, &ppstm);
    if ( v33 < 0 )
      dxc::ThrowHRExceptionPage((dxc *)(unsigned int)v33, v34, v35, v36);
    v103[0] = 0;
    v104 = 0;
    v105 = 0;
    std::set<unsigned short,std::less<unsigned short>,NonThrowingNewStlAllocator<unsigned short>>::set<unsigned short,std::less<unsigned short>,NonThrowingNewStlAllocator<unsigned short>>(v106);
    v37 = *(_QWORD *)(*(_QWORD *)(a1 + 24) + 16LL);
    v38 = *(__int64 (__fastcall **)(__int64, LPSTREAM, _QWORD, dxc::TextConvertor *, _DWORD, int (__fastcall ****)(_QWORD, GUID *, dxc::TextConvertor **)))(*(_QWORD *)v37 + 232LL);
    win_scope::detail::scope_helper<IXpsOMLinearGradientBrush *,win_scope::const_policies<win_scope::com_policies>>::reset(
      &v104,
      0);
    v104 = 0;
    dxc::CreateUniquePartUri(&v93, *(_QWORD *)(a1 + 24) + 16LL, L"/Resources/Fonts/", L"odttf");
    v39 = v93;
    FSTypeMask = dxc::TextConvertor::GetFSTypeMask(v40, a3);
    v43 = v38(v37, ppstm, (FSTypeMask & 4 | 8u) >> 2, v39, 0, &v104);
    if ( v93 )
      (*(void (__fastcall **)(dxc::TextConvertor *))(*(_QWORD *)v93 + 16LL))(v93);
    if ( v43 < 0 )
      dxc::ThrowHRExceptionPage((dxc *)(unsigned int)v43, v42, v44, v45);
    win_scope::detail::scope_helper<IXpsOMLinearGradientBrush *,win_scope::const_policies<win_scope::com_policies>>::reset(
      &v105,
      0);
    v105 = 0;
    (**(void (__fastcall ***)(struct IDWriteFontFace *, GUID *, __int64 *))a3)(
      a3,
      &GUID_ba6f3da5_0780_4422_9fae_eab429b786b4,
      &v105);
    v47 = 1;
    v48 = *(_QWORD *)(a1 + 24);
    v49 = 0;
    if ( !*(_BYTE *)(v48 + 97) || (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v97 + 512LL))(v97) )
      goto LABEL_96;
    v93 = 0;
    v50 = v104;
    v95 = 0;
    win_scope::scope<RefCountedObject<D2DFactoryLocking<MultiThreadedTrait>,LockingRequired,DeleteOnZeroReference> *,win_scope::const_policies<win_scope::com_policies>>::Swap<win_scope::const_policies<win_scope::com_policies>>(
      &v95,
      &v93);
    if ( v95 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
    v93 = 0;
    if ( (**v50)(v50, &GUID_f46f0ccb_ff7f_4884_9a78_33f68af18961, &v93) >= 0 )
    {
      v95 = 0;
      v92 = 0;
      win_scope::scope<RefCountedObject<D2DFactoryLocking<MultiThreadedTrait>,LockingRequired,DeleteOnZeroReference> *,win_scope::const_policies<win_scope::com_policies>>::Swap<win_scope::const_policies<win_scope::com_policies>>(
        &v92,
        &v95);
      v51 = v92;
      if ( v92 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
      v95 = 0;
      v52 = DWriteCreateFactory(v51, &GUID_b859ee5a_d838_4b5b_a2e8_1adc7d93db48, &v95);
      if ( v52 < 0 )
        dxc::ThrowHRExceptionPage((dxc *)(unsigned int)v52, v53, v54, v55);
      v100 = 0;
      v56 = v95;
      v57 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v95 + 136LL);
      v92 = 0;
      win_scope::scope<RefCountedObject<D2DFactoryLocking<MultiThreadedTrait>,LockingRequired,DeleteOnZeroReference> *,win_scope::const_policies<win_scope::com_policies>>::Swap<win_scope::const_policies<win_scope::com_policies>>(
        &v92,
        &v100);
      if ( v92 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
      v100 = 0;
      v58 = v57(v56, &v100);
      if ( v58 < 0 )
        dxc::ThrowHRExceptionPage((dxc *)(unsigned int)v58, v59, v60, v61);
      v99 = 0;
      v62 = v95;
      v63 = *(__int64 (__fastcall **)(__int64, __int64 *, _QWORD))(*(_QWORD *)v95 + 24LL);
      v92 = 0;
      win_scope::scope<RefCountedObject<D2DFactoryLocking<MultiThreadedTrait>,LockingRequired,DeleteOnZeroReference> *,win_scope::const_policies<win_scope::com_policies>>::Swap<win_scope::const_policies<win_scope::com_policies>>(
        &v92,
        &v99);
      if ( v92 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
      v99 = 0;
      v64 = v63(v62, &v99, 0);
      if ( v64 < 0 )
        dxc::ThrowHRExceptionPage((dxc *)(unsigned int)v64, v65, v66, v67);
      v98 = 0;
      v68 = v99;
      v69 = *(int (__fastcall **)(__int64, struct IDWriteFontFace *, __int64 *))(*(_QWORD *)v99 + 48LL);
      v92 = 0;
      win_scope::scope<RefCountedObject<D2DFactoryLocking<MultiThreadedTrait>,LockingRequired,DeleteOnZeroReference> *,win_scope::const_policies<win_scope::com_policies>>::Swap<win_scope::const_policies<win_scope::com_policies>>(
        &v92,
        &v98);
      if ( v92 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
      v98 = 0;
      if ( v69(v68, a3, &v98) >= 0 )
      {
        memset_0(&lf, 0, sizeof(lf));
        LODWORD(v92) = 0;
        v70 = (*(__int64 (__fastcall **)(__int64, __int64, LOGFONTW *, __int64 *))(*(_QWORD *)v100 + 32LL))(
                v100,
                v98,
                &lf,
                &v92);
        if ( v70 < 0 )
          dxc::ThrowHRExceptionPage((dxc *)(unsigned int)v70, v71, v73, v74);
        if ( (_DWORD)v92 )
        {
          dxc::TextConvertor::GetSystemFontFilePath(v72, &v109, v94);
          v75 = v109;
          if ( v109 && v110 && dword_1805DC170 != -1 )
          {
            v76 = CreateFontIndirectW(&lf);
            v77 = 0;
            if ( v76 )
              v77 = v76;
            v119[3] = v77;
            v78 = 0;
            hdc = 0;
            if ( v77 )
            {
              if ( dword_1805DC170 != -1 )
              {
                DCW = CreateDCW(L"DISPLAY", 0, 0, 0);
                win_scope::detail::scope_helper<HDC__ *,win_scope::const_policies<win_scope::types_6<win_scope::close_function<int (*)(HDC__ *),&int DeleteDC(HDC__ *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_nothrow>>>::reset(
                  &hdc,
                  DCW);
                v78 = hdc;
                if ( hdc )
                {
                  if ( dword_1805DC170 != -1 )
                  {
                    if ( SelectObject(hdc, v77) )
                    {
                      v120 = 0;
                      v121 = 0;
                      LODWORD(v120) = 24;
                      if ( (unsigned int)GetFontRealizationInfo(v78, &v120) )
                      {
                        if ( (_DWORD)v121 == 1 )
                        {
                          v80 = (char *)operator new[](0x220u);
                          v84 = 0;
                          if ( v80 )
                            v84 = v80;
                          v115 = v84;
                          if ( v84
                            && dword_1805DC170 != -1
                            && (unsigned int)GetFontFileInfo(HIDWORD(v120), 0, v84, 256, 0) )
                          {
                            v85 = v110;
                            v82 = (const char *)(v84 + 16 - v110);
                            do
                            {
                              v86 = *(unsigned __int16 *)&v82[(_QWORD)v85];
                              v81 = *(unsigned __int16 *)v85 - v86;
                              if ( v81 )
                                break;
                              v85 += 2;
                            }
                            while ( v86 );
                            if ( !v81 )
                            {
                              v49 = (*(__int64 (__fastcall **)(dxc::TextConvertor *, LOGFONTW *))(*(_QWORD *)v93 + 32LL))(
                                      v93,
                                      &lf);
                              if ( v49 >= 0 )
                              {
                                v49 = (*(__int64 (__fastcall **)(dxc::TextConvertor *, struct IDWriteFontFace *))(*(_QWORD *)v93 + 48LL))(
                                        v93,
                                        a3);
                                v47 = v49 < 0;
                              }
                            }
                          }
                          if ( v84 )
                            operator delete(v84);
                          if ( v49 < 0 )
                            dxc::ThrowHRExceptionPage((dxc *)(unsigned int)v49, v81, v82, v83);
                        }
                      }
                    }
                  }
                }
              }
            }
            if ( v78 )
              DeleteDC(v78);
            if ( v77 )
              DeleteObject(v77);
            v75 = v109;
          }
          if ( v75 && v110 )
            win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<dxc::CDxcVisual *>(&v109);
        }
      }
      if ( v98 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
        v98 = 0;
      }
      if ( v99 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v99 + 16LL))(v99);
        v99 = 0;
      }
      if ( v100 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v100 + 16LL))(v100);
        v100 = 0;
      }
      if ( v95 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
    }
    v46 = v93;
    if ( v93 )
      (*(void (__fastcall **)(dxc::TextConvertor *))(*(_QWORD *)v93 + 16LL))(v93);
    if ( v47 )
LABEL_96:
      dxc::TextConvertor::CopyFontDataToStream(v46, v94, ppstm);
    v87 = v103[0];
    if ( v28 )
    {
      v87 = v103[0] | 2;
      v103[0] |= 2u;
    }
    if ( !v107 )
    {
      v87 |= 0x20u;
      v103[0] = v87;
    }
    if ( v47 && a6 && (v28 || v107 == 1) )
      v103[0] = v87 | 1;
    if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v97 + 512LL))(v97) )
      v103[0] |= 0x10u;
    dxc::TextConvertor::TFontResourceData::AddGlyphIndices((dxc::TextConvertor::TFontResourceData *)v103, v113, a5);
    v88 = std::pair<dxc::TextConvertor::TFontResourceKey const,dxc::TextConvertor::TFontResourceData>::pair<dxc::TextConvertor::TFontResourceKey const,dxc::TextConvertor::TFontResourceData>(
            &lf,
            &v116,
            v103);
    v93 = *(dxc::TextConvertor **)std::_Tree<std::_Tmap_traits<dxc::TextConvertor::TFontResourceKey,dxc::TextConvertor::TFontResourceData,dxc::TextConvertor::FontResKeyLess,NonThrowingNewStlAllocator<std::pair<dxc::TextConvertor::TFontResourceKey const,dxc::TextConvertor::TFontResourceData>>,0>>::insert(
                                    v112,
                                    &v115,
                                    **v112,
                                    v88);
    std::pair<dxc::TextConvertor::TFontResourceKey const,dxc::TextConvertor::TFontResourceData>::~pair<dxc::TextConvertor::TFontResourceKey const,dxc::TextConvertor::TFontResourceData>((dxc::TextConvertor::TFontResourceKey *)&lf);
    dxc::TextConvertor::TFontResourceData::~TFontResourceData((dxc::TextConvertor::TFontResourceData *)v103);
    if ( ppstm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
  }
  else
  {
    v32 = std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,win_scope::scope<IXpsOMImageResource *,win_scope::const_policies<win_scope::com_policies>>>>>>::operator->(&v93);
    dxc::TextConvertor::TFontResourceData::AddGlyphIndices((dxc::TextConvertor::TFontResourceData *)(v32 + 64), a4, a5);
  }
  v89 = std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,win_scope::scope<IXpsOMImageResource *,win_scope::const_policies<win_scope::com_policies>>>>>>::operator->(&v93);
  v90 = v114;
  win_scope::scope<IXpsOMCanvas *,win_scope::const_policies<win_scope::com_policies>>::scope<IXpsOMCanvas *,win_scope::const_policies<win_scope::com_policies>>(
    v114,
    v89 + 72);
  dxc::TextConvertor::TFontResourceKey::~TFontResourceKey((dxc::TextConvertor::TFontResourceKey *)&v116);
  if ( v94 )
  {
    (*(void (__fastcall **)(struct IDWriteFontFile *))(*(_QWORD *)v94 + 16LL))(v94);
    v94 = 0;
  }
  if ( v97 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
  return v90;
}

```

## disassembly

```asm
0x1801e6ff8  push    rbp
0x1801e6ffa  push    rbx
0x1801e6ffb  push    rsi
0x1801e6ffc  push    rdi
0x1801e6ffd  push    r12
0x1801e6fff  push    r13
0x1801e7001  push    r14
0x1801e7003  push    r15
0x1801e7005  lea     rbp, [rsp-0F8h]
0x1801e700d  sub     rsp, 1F8h
0x1801e7014  mov     rax, cs:__security_cookie
0x1801e701b  xor     rax, rsp
0x1801e701e  mov     [rbp+130h+var_50], rax
0x1801e7025  mov     rsi, r9
0x1801e7028  mov     [rbp+130h+var_140], r9
0x1801e702c  mov     r14, r8
0x1801e702f  mov     [rbp+130h+var_138], rdx
0x1801e7033  mov     r15, rcx
0x1801e7036  mov     [rbp+130h+var_150], rdx
0x1801e703a  xor     r12d, r12d
0x1801e703d  mov     [rsp+230h+var_1C8], r12
0x1801e7042  xor     edx, edx
0x1801e7044  lea     rcx, [rsp+230h+var_1C8]
0x1801e7049  call    ?reset@?$scope_helper@PEAUIXpsOMLinearGradientBrush@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@detail@win_scope@@SAXAEAV?$scope@PEAUIXpsOMLinearGradientBrush@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@3@PEAUIXpsOMLinearGradientBrush@@@Z; win_scope::detail::scope_helper<IXpsOMLinearGradientBrush *,win_scope::const_policies<win_scope::com_policies>>::reset(win_scope::scope<IXpsOMLinearGradientBrush *,win_scope::const_policies<win_scope::com_policies>> &,IXpsOMLinearGradientBrush *)
0x1801e704e  mov     [rsp+230h+var_1C8], r12
0x1801e7053  mov     rax, [r14]
0x1801e7056  lea     r8, [rsp+230h+var_1C8]
0x1801e705b  lea     rdx, _GUID_ba6f3da5_0780_4422_9fae_eab429b786b4
0x1801e7062  mov     rcx, r14
0x1801e7065  mov     rax, [rax]
0x1801e7068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e706d  test    eax, eax
0x1801e706f  jns     short loc_1801E7079
0x1801e7071  mov     ecx, eax; this
0x1801e7073  call    ?ThrowHRExceptionPage@dxc@@YAXJPEBDH@Z; dxc::ThrowHRExceptionPage(long,char const *,int)
0x1801e7079  mov     rax, [r14]
0x1801e707c  mov     rcx, r14
0x1801e707f  mov     rax, [rax+18h]
0x1801e7083  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e7088  mov     edi, eax
0x1801e708a  mov     [rbp+130h+var_178], eax
0x1801e708d  mov     [rbp+130h+var_1A8], 1
0x1801e7094  mov     [rsp+230h+var_1E0], r12
0x1801e7099  mov     rax, [r14]
0x1801e709c  mov     rbx, [rax+20h]
0x1801e70a0  mov     [rsp+230h+ppstm], r12
0x1801e70a5  lea     rdx, [rsp+230h+var_1E0]
0x1801e70aa  lea     rcx, [rsp+230h+ppstm]
0x1801e70af  call    ??$Swap@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@?$scope@PEAV?$RefCountedObject@V?$D2DFactoryLocking@VMultiThreadedTrait@@@@ULockingRequired@@UDeleteOnZeroReference@@@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@AEAAXAEAV01@@Z; win_scope::scope<RefCountedObject<D2DFactoryLocking<MultiThreadedTrait>,LockingRequired,DeleteOnZeroReference> *,win_scope::const_policies<win_scope::com_policies>>::Swap<win_scope::const_policies<win_scope::com_policies>>(win_scope::scope<RefCountedObject<D2DFactoryLocking<MultiThreadedTrait>,LockingRequired,DeleteOnZeroReference> *,win_scope::const_policies<win_scope::com_policies>> &)
0x1801e70b4  nop
0x1801e70b5  mov     rcx, [rsp+230h+ppstm]
0x1801e70ba  test    rcx, rcx
0x1801e70bd  jz      short loc_1801E70CC
0x1801e70bf  mov     rax, [rcx]
0x1801e70c2  mov     rax, [rax+10h]
0x1801e70c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e70cb  nop
0x1801e70cc  mov     [rsp+230h+var_1E0], r12
0x1801e70d1  lea     r8, [rsp+230h+var_1E0]
0x1801e70d6  lea     rdx, [rbp+130h+var_1A8]
0x1801e70da  mov     rcx, r14
0x1801e70dd  mov     rax, rbx
0x1801e70e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e70e5  test    eax, eax
0x1801e70e7  jns     short loc_1801E70F1
0x1801e70e9  mov     ecx, eax; this
0x1801e70eb  call    ?ThrowHRExceptionPage@dxc@@YAXJPEBDH@Z; dxc::ThrowHRExceptionPage(long,char const *,int)
0x1801e70f1  cmp     [rbp+130h+var_1A8], 1
0x1801e70f5  jz      short loc_1801E70FD
0x1801e70f7  call    ?ThrowLogicException@dxc@@YAXPEBDH@Z; dxc::ThrowLogicException(char const *,int)
0x1801e70fd  mov     [rbp+130h+var_158], r12
0x1801e7101  mov     [rbp+130h+var_1A4], r12d
0x1801e7105  mov     rcx, [rsp+230h+var_1E0]
0x1801e710a  mov     rax, [rcx]
0x1801e710d  lea     r8, [rbp+130h+var_1A4]
0x1801e7111  lea     rdx, [rbp+130h+var_158]
0x1801e7115  mov     rax, [rax+18h]
0x1801e7119  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e711e  test    eax, eax
0x1801e7120  jns     short loc_1801E712A
0x1801e7122  mov     ecx, eax; this
0x1801e7124  call    ?ThrowHRExceptionPage@dxc@@YAXJPEBDH@Z; dxc::ThrowHRExceptionPage(long,char const *,int)
0x1801e712a  mov     [rbp+130h+var_120], r12
0x1801e712e  lea     rcx, [rbp+130h+var_118]
0x1801e7132  call    ??0?$vector@MV?$NonThrowingNewStlAllocator@M@@@std@@QEAA@XZ; std::vector<float,NonThrowingNewStlAllocator<float>>::vector<float,NonThrowingNewStlAllocator<float>>(void)
0x1801e7137  mov     [rbp+130h+var_100], r12w
0x1801e713c  lea     rcx, [rbp+130h+var_F8]
0x1801e7140  call    ??0?$vector@MV?$NonThrowingNewStlAllocator@M@@@std@@QEAA@XZ; std::vector<float,NonThrowingNewStlAllocator<float>>::vector<float,NonThrowingNewStlAllocator<float>>(void)
0x1801e7145  nop
0x1801e7146  mov     r8d, [rbp+130h+var_1A4]
0x1801e714a  mov     rdx, [rbp+130h+var_158]
0x1801e714e  add     r8, rdx
0x1801e7151  lea     rcx, [rbp+130h+var_118]
0x1801e7155  call    ??$assign@PEAE$0A@@?$vector@EV?$NonThrowingNewStlAllocator@E@@@std@@QEAAXPEAE0@Z; std::vector<uchar,NonThrowingNewStlAllocator<uchar>>::assign<uchar *,0>(uchar *,uchar *)
0x1801e715a  mov     rcx, [rsp+230h+var_1E0]
0x1801e715f  mov     rax, [rcx]
0x1801e7162  lea     rdx, [rbp+130h+var_120]
0x1801e7166  mov     rax, [rax+20h]
0x1801e716a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e716f  test    eax, eax
0x1801e7171  jns     short loc_1801E717B
0x1801e7173  mov     ecx, eax; this
0x1801e7175  call    ?ThrowHRExceptionPage@dxc@@YAXJPEBDH@Z; dxc::ThrowHRExceptionPage(long,char const *,int)
0x1801e717b  cmp     edi, 2
0x1801e717e  jnz     short loc_1801E71A1
0x1801e7180  mov     r13b, 1
0x1801e7183  cmp     [rbp+130h+arg_28], r12b
0x1801e718a  jz      short loc_1801E71A4
0x1801e718c  mov     rax, [r14]
0x1801e718f  mov     rcx, r14
0x1801e7192  mov     rax, [rax+28h]
0x1801e7196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e719b  mov     [rbp+130h+var_100], ax
0x1801e719f  jmp     short loc_1801E71A4
0x1801e71a1  mov     r13b, r12b
0x1801e71a4  mov     rcx, [rsp+230h+var_1C8]
0x1801e71a9  mov     rax, [rcx]
0x1801e71ac  mov     rax, [rax+208h]
0x1801e71b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e71b8  mov     ebx, eax
0x1801e71ba  test    eax, eax
0x1801e71bc  jz      short loc_1801E71E4
0x1801e71be  mov     edx, ebx
0x1801e71c0  lea     rcx, [rbp+130h+var_F8]
0x1801e71c4  call    ?resize@?$vector@HV?$NonThrowingNewStlAllocator@H@@@std@@QEAAX_K@Z; std::vector<int,NonThrowingNewStlAllocator<int>>::resize(unsigned __int64)
0x1801e71c9  mov     rcx, [rsp+230h+var_1C8]
0x1801e71ce  mov     rax, [rcx]
0x1801e71d1  mov     r8d, ebx
0x1801e71d4  mov     rdx, [rbp+130h+var_F8]
0x1801e71d8  mov     rax, [rax+210h]
0x1801e71df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e71e4  lea     rbx, [r15+20h]
0x1801e71e8  mov     [rbp+130h+var_150], rbx
0x1801e71ec  lea     r8, [rbp+130h+var_120]
0x1801e71f0  lea     rdx, [rsp+230h+var_1E8]
0x1801e71f5  mov     rcx, rbx
0x1801e71f8  call    ?find@?$_Tree@V?$_Tmap_traits@UTFontResourceKey@TextConvertor@dxc@@UTFontResourceData@23@UFontResKeyLess@23@V?$NonThrowingNewStlAllocator@U?$pair@$$CBUTFontResourceKey@TextConvertor@dxc@@UTFontResourceData@23@@std@@@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUTFontResourceKey@TextConvertor@dxc@@UTFontResourceData@23@@std@@@std@@@std@@@2@AEBUTFontResourceKey@TextConvertor@dxc@@@Z; std::_Tree<std::_Tmap_traits<dxc::TextConvertor::TFontResourceKey,dxc::TextConvertor::TFontResourceData,dxc::TextConvertor::FontResKeyLess,NonThrowingNewStlAllocator<std::pair<dxc::TextConvertor::TFontResourceKey const,dxc::TextConvertor::TFontResourceData>>,0>>::find(dxc::TextConvertor::TFontResourceKey const &)
0x1801e71fd  lea     rdx, [rbp+130h+hdc]
0x1801e7201  mov     rcx, rbx
0x1801e7204  call    ?begin@?$vector@UCCoordinate@dxc@@V?$allocator@UCCoordinate@dxc@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UCCoordinate@dxc@@@std@@@std@@@2@XZ; std::vector<dxc::CCoordinate>::begin(void)
0x1801e7209  mov     rcx, [rax]
0x1801e720c  cmp     [rsp+230h+var_1E8], rcx
0x1801e7211  jz      short loc_1801E7238
0x1801e7213  lea     rcx, [rsp+230h+var_1E8]
0x1801e7218  call    ??C?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$scope@PEAUIXpsOMImageResource@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CB_KV?$scope@PEAUIXpsOMImageResource@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@@1@XZ; std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,win_scope::scope<IXpsOMImageResource *,win_scope::const_policies<win_scope::com_policies>>>>>>::operator->(void)
0x1801e721d  lea     rcx, [rax+40h]; this
0x1801e7221  mov     r8d, [rbp+130h+arg_20]; unsigned int
0x1801e7228  mov     rdx, rsi; unsigned __int16 *
0x1801e722b  call    ?AddGlyphIndices@TFontResourceData@TextConvertor@dxc@@QEAAXPEBGI@Z; dxc::TextConvertor::TFontResourceData::AddGlyphIndices(ushort const *,uint)
0x1801e7230  xor     r15d, r15d
0x1801e7233  jmp     loc_1801E78CE
0x1801e7238  mov     [rsp+230h+ppstm], r12
0x1801e723d  lea     rcx, [rsp+230h+ppstm]
0x1801e7242  call    ??$close@PEAUIStream@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@YAXAEAV?$scope@PEAUIStream@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@0@@Z; win_scope::close<IStream *,win_scope::const_policies<win_scope::com_policies>>(win_scope::scope<IStream *,win_scope::const_policies<win_scope::com_policies>> &)
0x1801e7247  mov     [rsp+230h+ppstm], r12
0x1801e724c  lea     r8, [rsp+230h+ppstm]; ppstm
0x1801e7251  mov     edx, 1; fDeleteOnRelease
0x1801e7256  xor     ecx, ecx; hGlobal
0x1801e7258  call    cs:__imp_CreateStreamOnHGlobal
0x1801e725e  test    eax, eax
0x1801e7260  jns     short loc_1801E726A
0x1801e7262  mov     ecx, eax; this
0x1801e7264  call    ?ThrowHRExceptionPage@dxc@@YAXJPEBDH@Z; dxc::ThrowHRExceptionPage(long,char const *,int)
0x1801e726a  mov     [rbp+130h+var_1A0], r12b
0x1801e726e  mov     [rbp+130h+var_198], r12
0x1801e7272  mov     [rbp+130h+var_190], r12
0x1801e7276  lea     rcx, [rbp+130h+var_188]
0x1801e727a  call    ??0?$set@GU?$less@G@std@@V?$NonThrowingNewStlAllocator@G@@@std@@QEAA@XZ; std::set<ushort,std::less<ushort>,NonThrowingNewStlAllocator<ushort>>::set<ushort,std::less<ushort>,NonThrowingNewStlAllocator<ushort>>(void)
0x1801e727f  nop
0x1801e7280  mov     rax, [r15+18h]
0x1801e7284  mov     rsi, [rax+10h]
0x1801e7288  mov     rax, [rsi]
0x1801e728b  mov     rdi, [rax+0E8h]
0x1801e7292  xor     edx, edx
0x1801e7294  lea     rcx, [rbp+130h+var_198]
0x1801e7298  call    ?reset@?$scope_helper@PEAUIXpsOMLinearGradientBrush@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@detail@win_scope@@SAXAEAV?$scope@PEAUIXpsOMLinearGradientBrush@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@3@PEAUIXpsOMLinearGradientBrush@@@Z; win_scope::detail::scope_helper<IXpsOMLinearGradientBrush *,win_scope::const_policies<win_scope::com_policies>>::reset(win_scope::scope<IXpsOMLinearGradientBrush *,win_scope::const_policies<win_scope::com_policies>> &,IXpsOMLinearGradientBrush *)
0x1801e729d  mov     [rbp+130h+var_198], r12
0x1801e72a1  mov     rdx, [r15+18h]
0x1801e72a5  add     rdx, 10h
0x1801e72a9  lea     r9, aOdttf; "odttf"
0x1801e72b0  lea     r8, aResourcesFonts; "/Resources/Fonts/"
0x1801e72b7  lea     rcx, [rsp+230h+var_1E8]
0x1801e72bc  call    ?CreateUniquePartUri@dxc@@YA?AV?$scope@PEAUIOpcPartUri@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@AEBV?$scope@PEAUIXpsOMObjectFactory@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@3@PEB_W1@Z; dxc::CreateUniquePartUri(win_scope::scope<IXpsOMObjectFactory *,win_scope::const_policies<win_scope::com_policies>> const &,wchar_t const *,wchar_t const *)
0x1801e72c1  nop
0x1801e72c2  mov     rbx, [rsp+230h+var_1E8]
0x1801e72c7  mov     rdx, r14; struct IDWriteFontFace *
0x1801e72ca  call    ?GetFSTypeMask@TextConvertor@dxc@@AEAAIPEAUIDWriteFontFace@@@Z; dxc::TextConvertor::GetFSTypeMask(IDWriteFontFace *)
0x1801e72cf  and     eax, 4
0x1801e72d2  or      eax, 8
0x1801e72d5  shr     eax, 2
0x1801e72d8  lea     rcx, [rbp+130h+var_198]
0x1801e72dc  mov     [rsp+230h+var_208], rcx
0x1801e72e1  mov     dword ptr [rsp+230h+var_210], r12d
0x1801e72e6  mov     r9, rbx
0x1801e72e9  mov     r8d, eax
0x1801e72ec  mov     rdx, [rsp+230h+ppstm]
0x1801e72f1  mov     rcx, rsi
0x1801e72f4  mov     rax, rdi
0x1801e72f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e72fc  mov     ebx, eax
0x1801e72fe  mov     rcx, [rsp+230h+var_1E8]
0x1801e7303  test    rcx, rcx
0x1801e7306  jz      short loc_1801E7315
0x1801e7308  mov     rax, [rcx]
0x1801e730b  mov     rax, [rax+10h]
0x1801e730f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e7314  nop
0x1801e7315  test    ebx, ebx
0x1801e7317  jns     short loc_1801E7321
0x1801e7319  mov     ecx, ebx; this
0x1801e731b  call    ?ThrowHRExceptionPage@dxc@@YAXJPEBDH@Z; dxc::ThrowHRExceptionPage(long,char const *,int)
0x1801e7321  xor     edx, edx
0x1801e7323  lea     rcx, [rbp+130h+var_190]
0x1801e7327  call    ?reset@?$scope_helper@PEAUIXpsOMLinearGradientBrush@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@detail@win_scope@@SAXAEAV?$scope@PEAUIXpsOMLinearGradientBrush@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@3@PEAUIXpsOMLinearGradientBrush@@@Z; win_scope::detail::scope_helper<IXpsOMLinearGradientBrush *,win_scope::const_policies<win_scope::com_policies>>::reset(win_scope::scope<IXpsOMLinearGradientBrush *,win_scope::const_policies<win_scope::com_policies>> &,IXpsOMLinearGradientBrush *)
0x1801e732c  mov     [rbp+130h+var_190], r12
0x1801e7330  mov     rax, [r14]
0x1801e7333  lea     r8, [rbp+130h+var_190]
0x1801e7337  lea     rdx, _GUID_ba6f3da5_0780_4422_9fae_eab429b786b4
0x1801e733e  mov     rcx, r14
0x1801e7341  mov     rax, [rax]
0x1801e7344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e7349  mov     r12b, 1
0x1801e734c  mov     rax, [r15+18h]
0x1801e7350  xor     r15d, r15d
0x1801e7353  cmp     [rax+61h], r15b
0x1801e7357  jz      loc_1801E77FF
0x1801e735d  mov     rcx, [rsp+230h+var_1C8]
0x1801e7362  mov     rax, [rcx]
0x1801e7365  mov     rax, [rax+200h]
0x1801e736c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e7371  test    eax, eax
0x1801e7373  jnz     loc_1801E77FF
0x1801e7379  mov     [rsp+230h+var_1E8], r15
0x1801e737e  mov     rbx, [rbp+130h+var_198]
0x1801e7382  mov     [rsp+230h+var_1D8], r15
0x1801e7387  lea     rdx, [rsp+230h+var_1E8]
0x1801e738c  lea     rcx, [rsp+230h+var_1D8]
0x1801e7391  call    ??$Swap@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@?$scope@PEAV?$RefCountedObject@V?$D2DFactoryLocking@VMultiThreadedTrait@@@@ULockingRequired@@UDeleteOnZeroReference@@@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@AEAAXAEAV01@@Z; win_scope::scope<RefCountedObject<D2DFactoryLocking<MultiThreadedTrait>,LockingRequired,DeleteOnZeroReference> *,win_scope::const_policies<win_scope::com_policies>>::Swap<win_scope::const_policies<win_scope::com_policies>>(win_scope::scope<RefCountedObject<D2DFactoryLocking<MultiThreadedTrait>,LockingRequired,DeleteOnZeroReference> *,win_scope::const_policies<win_scope::com_policies>> &)
0x1801e7396  nop
0x1801e7397  mov     rcx, [rsp+230h+var_1D8]
0x1801e739c  test    rcx, rcx
0x1801e739f  jz      short loc_1801E73AE
0x1801e73a1  mov     rax, [rcx]
0x1801e73a4  mov     rax, [rax+10h]
0x1801e73a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e73ad  nop
0x1801e73ae  mov     [rsp+230h+var_1E8], r15
0x1801e73b3  mov     rax, [rbx]
0x1801e73b6  lea     r8, [rsp+230h+var_1E8]
0x1801e73bb  lea     rdx, _GUID_f46f0ccb_ff7f_4884_9a78_33f68af18961
0x1801e73c2  mov     rcx, rbx
0x1801e73c5  mov     rax, [rax]
0x1801e73c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e73cd  test    eax, eax
0x1801e73cf  js      loc_1801E77E3
0x1801e73d5  mov     [rsp+230h+var_1D8], r15
0x1801e73da  mov     [rsp+230h+var_1F0], r15
0x1801e73df  lea     rdx, [rsp+230h+var_1D8]
0x1801e73e4  lea     rcx, [rsp+230h+var_1F0]
0x1801e73e9  call    ??$Swap@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@?$scope@PEAV?$RefCountedObject@V?$D2DFactoryLocking@VMultiThreadedTrait@@@@ULockingRequired@@UDeleteOnZeroReference@@@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@AEAAXAEAV01@@Z; win_scope::scope<RefCountedObject<D2DFactoryLocking<MultiThreadedTrait>,LockingRequired,DeleteOnZeroReference> *,win_scope::const_policies<win_scope::com_policies>>::Swap<win_scope::const_policies<win_scope::com_policies>>(win_scope::scope<RefCountedObject<D2DFactoryLocking<MultiThreadedTrait>,LockingRequired,DeleteOnZeroReference> *,win_scope::const_policies<win_scope::com_policies>> &)
0x1801e73ee  nop
0x1801e73ef  mov     rcx, [rsp+230h+var_1F0]
0x1801e73f4  test    rcx, rcx
0x1801e73f7  jz      short loc_1801E7406
0x1801e73f9  mov     rax, [rcx]
0x1801e73fc  mov     rax, [rax+10h]
0x1801e7400  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e7405  nop
0x1801e7406  mov     [rsp+230h+var_1D8], r15
0x1801e740b  lea     r8, [rsp+230h+var_1D8]
0x1801e7410  lea     rdx, _GUID_b859ee5a_d838_4b5b_a2e8_1adc7d93db48
0x1801e7417  call    DWriteCreateFactory
0x1801e741c  test    eax, eax
0x1801e741e  jns     short loc_1801E7428
0x1801e7420  mov     ecx, eax; this
0x1801e7422  call    ?ThrowHRExceptionPage@dxc@@YAXJPEBDH@Z; dxc::ThrowHRExceptionPage(long,char const *,int)
0x1801e7428  mov     [rbp+130h+var_1B0], r15
0x1801e742c  mov     rbx, [rsp+230h+var_1D8]
0x1801e7431  mov     rax, [rbx]
0x1801e7434  mov     rdi, [rax+88h]
0x1801e743b  mov     [rsp+230h+var_1F0], r15
0x1801e7440  lea     rdx, [rbp+130h+var_1B0]
0x1801e7444  lea     rcx, [rsp+230h+var_1F0]
0x1801e7449  call    ??$Swap@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@?$scope@PEAV?$RefCountedObject@V?$D2DFactoryLocking@VMultiThreadedTrait@@@@ULockingRequired@@UDeleteOnZeroReference@@@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@AEAAXAEAV01@@Z; win_scope::scope<RefCountedObject<D2DFactoryLocking<MultiThreadedTrait>,LockingRequired,DeleteOnZeroReference> *,win_scope::const_policies<win_scope::com_policies>>::Swap<win_scope::const_policies<win_scope::com_policies>>(win_scope::scope<RefCountedObject<D2DFactoryLocking<MultiThreadedTrait>,LockingRequired,DeleteOnZeroReference> *,win_scope::const_policies<win_scope::com_policies>> &)
0x1801e744e  nop
0x1801e744f  mov     rcx, [rsp+230h+var_1F0]
0x1801e7454  test    rcx, rcx
0x1801e7457  jz      short loc_1801E7466
0x1801e7459  mov     rax, [rcx]
0x1801e745c  mov     rax, [rax+10h]
0x1801e7460  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e7465  nop
0x1801e7466  mov     [rbp+130h+var_1B0], r15
0x1801e746a  lea     rdx, [rbp+130h+var_1B0]
0x1801e746e  mov     rcx, rbx
0x1801e7471  mov     rax, rdi
0x1801e7474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e7479  test    eax, eax
0x1801e747b  jns     short loc_1801E7485
0x1801e747d  mov     ecx, eax; this
  ... truncated ...
```
