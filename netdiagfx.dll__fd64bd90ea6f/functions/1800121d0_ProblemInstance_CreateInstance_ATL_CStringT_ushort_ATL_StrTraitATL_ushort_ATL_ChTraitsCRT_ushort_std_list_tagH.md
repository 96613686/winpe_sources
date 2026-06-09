# ProblemInstance::CreateInstance(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,std::list<tagHELPER_ATTRIBUTE,std::allocator<tagHELPER_ATTRIBUTE>> *,_GUID,ATL::CFileTime,ATL::CFileTime,bool,SQMSession *)

- ea: `0x1800121d0`
- end: `0x180012b3e`
- name: `?CreateInstance@ProblemInstance@@SAPEAV1@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV?$list@UtagHELPER_ATTRIBUTE@@V?$allocator@UtagHELPER_ATTRIBUTE@@@std@@@std@@U_GUID@@VCFileTime@3@3_NPEAVSQMSession@@@Z`
- size: `2414`
- prototype: `__int64 __fastcall(_QWORD *, __int64 **, __int128 *, size_t, size_t, char, void *)`
- caller_count: `2`
- callee_count: `26`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000cba0`
- `0x18000d028`

## callees

- `0x180001ff4`
- `0x1800020d6`
- `0x1800035a8`
- `0x1800040b4`
- `0x1800056bc`
- `0x18000579c`
- `0x180006d58`
- `0x180006f04`
- `0x180006fa0`
- `0x180007014`
- `0x180008480`
- `0x18000bca0`
- `0x1800102fc`
- `0x180010460`
- `0x1800117e8`
- `0x180011b70`
- `0x180011c20`
- `0x180012180`
- `0x1800121d0`
- `0x180013724`
- `0x180015308`
- `0x18001b3a8`
- `0x18001dfa4`
- `0x18002c802`
- `0x18002c840`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800127df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012836`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800128ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800127df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012836`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800128ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800124c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012962`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001297e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012ada`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800124c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012962`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001297e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012ada`

## string_xrefs

- `0x18001235d`: `CreateInstance failed for %s, HR: %x`
- `0x180012412`: `CreateProtectedHelperInstance failed for %s`
- `0x180012923`: `Initialize failed for %s while copying attributes, HR: %x`

## pseudocode

```c
__int64 __fastcall ProblemInstance::CreateInstance(
        _QWORD *a1,
        __int64 **a2,
        __int128 *a3,
        size_t a4,
        size_t a5,
        char a6,
        void *a7)
{
  _QWORD *v9; // r15
  __int64 v10; // rsi
  __int64 v11; // r14
  __int64 ProblemInstance; // rax
  int v13; // esi
  _QWORD *ClassFactory; // rax
  _QWORD *v15; // r13
  __int64 v16; // rbx
  int v17; // r15d
  struct NetworkDiagnosticsEngine *v18; // rbx
  int v19; // ebx
  struct INetDiagHelper *v20; // r15
  ProtectedNetDiagHelper *v21; // rax
  ProtectedNetDiagHelper *v22; // r12
  struct NetworkDiagnosticsEngine *v23; // rbx
  _OWORD *v24; // rsi
  __int64 (__fastcall *v25)(ProtectedNetDiagHelper *, _QWORD, _OWORD *); // rbx
  unsigned int v26; // eax
  int v27; // r15d
  unsigned int v28; // edx
  __int64 v29; // r9
  struct NetworkDiagnosticsEngine *v30; // rbx
  unsigned int v31; // edx
  struct NetworkDiagnosticsEngine *v32; // rbx
  void *v33; // rax
  __int64 v34; // rdx
  __int64 v35; // rbx
  __int64 v36; // r8
  __int64 v37; // rdx
  void *v38; // rax
  unsigned __int64 v39; // r11
  __int64 v40; // rax
  __int64 **v41; // rax
  __int64 *v42; // rbx
  const unsigned __int16 *v43; // rax
  unsigned __int64 v44; // r15
  void *v45; // rax
  _DWORD *v46; // r15
  void *v47; // rax
  const unsigned __int16 *v48; // rax
  unsigned __int64 v49; // r15
  void *v50; // rcx
  unsigned int v51; // edx
  void *v52; // rcx
  __int128 v53; // xmm0
  int v54; // ebx
  __int64 v56; // [rsp+20h] [rbp-E0h]
  struct NetworkDiagnosticsEngine *v58; // [rsp+38h] [rbp-C8h] BYREF
  void *v59; // [rsp+40h] [rbp-C0h] BYREF
  __int64 **v60; // [rsp+48h] [rbp-B8h]
  LPVOID pv; // [rsp+50h] [rbp-B0h]
  size_t Size[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v63; // [rsp+70h] [rbp-90h] BYREF
  __int128 v64; // [rsp+80h] [rbp-80h] BYREF
  struct INetDiagHelper *v65; // [rsp+90h] [rbp-70h] BYREF
  LPVOID v66; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 v67[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v68; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD *v69; // [rsp+C0h] [rbp-40h]
  unsigned __int16 v70[8]; // [rsp+D0h] [rbp-30h] BYREF
  LPVOID v71[2]; // [rsp+E0h] [rbp-20h]
  __int128 v72; // [rsp+F0h] [rbp-10h]
  __int128 v73; // [rsp+100h] [rbp+0h]
  __int128 v74; // [rsp+110h] [rbp+10h]
  __int128 v75; // [rsp+120h] [rbp+20h]
  __int128 v76; // [rsp+130h] [rbp+30h]
  __int128 v77; // [rsp+140h] [rbp+40h]
  __int128 v78; // [rsp+150h] [rbp+50h]
  unsigned __int16 v79[128]; // [rsp+1D0h] [rbp+D0h] BYREF

  v67[0] = (unsigned __int64)a3;
  v60 = a2;
  v9 = a1;
  v69 = a1;
  pv = a7;
  v58 = NetworkDiagnosticsEngine::Instance();
  v63 = 0;
  if ( v58 )
  {
    v11 = 0;
    if ( NetworkDiagnosticsEngine::Instance() )
      v11 = *(_QWORD *)NetworkDiagnosticsEngine::Instance();
    *(_QWORD *)&v68 = a4;
    *((_QWORD *)&v68 + 1) = a5;
    Size[0] = a4;
    Size[1] = a5;
    v64 = *a3;
    ProblemInstance = NetworkDiagnosticsEngine::FindProblemInstance(v58, v9, v60, &v64, Size);
    v10 = ProblemInstance;
    if ( ProblemInstance )
    {
      *(_QWORD *)(ProblemInstance + 336) = a7;
      goto LABEL_92;
    }
    v13 = (int)a1;
    ClassFactory = (_QWORD *)HelperClassRepository::GetClassFactory(
                               *((_QWORD *)v58 + 5),
                               (_DWORD)a1,
                               (_DWORD)v60,
                               (unsigned int)&v63,
                               a6,
                               (__int64)a7);
    v15 = ClassFactory;
    if ( !ClassFactory )
      goto LABEL_8;
    *(_QWORD *)&v64 = ClassFactory;
    *(_QWORD *)&v63 = ClassFactory[2];
    v59 = (void *)ClassFactory[3];
    v16 = *ClassFactory;
    v65 = 0;
    v17 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, struct INetDiagHelper **))(*(_QWORD *)v16 + 24LL))(
            v16,
            0,
            &IID_INetDiagHelper,
            &v65);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    if ( v17 < 0 )
    {
      if ( v11 )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v58);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          &v58,
          L"CreateInstance failed for %s, HR: %x",
          *a1,
          (unsigned int)v17);
        v18 = v58;
        (*(void (__fastcall **)(__int64, __int64, struct NetworkDiagnosticsEngine *))(*(_QWORD *)v11 + 96LL))(
          v11,
          1,
          v58);
        ATL::CStringData::Release((struct NetworkDiagnosticsEngine *)((char *)v18 - 24));
      }
      TSimpleDeallocator<unsigned short *,void,void *,&void CoTaskMemFree(void *)>::~TSimpleDeallocator<unsigned short *,void,void *,&void CoTaskMemFree(void *)>(&v59);
      TSimpleDeallocator<unsigned short *,void,void *,&void CoTaskMemFree(void *)>::~TSimpleDeallocator<unsigned short *,void,void *,&void CoTaskMemFree(void *)>((void **)&v63);
      TSimpleDeallocator<unsigned short *,void,void *,&void CoTaskMemFree(void *)>::~TSimpleDeallocator<unsigned short *,void,void *,&void CoTaskMemFree(void *)>((void **)&v64);
LABEL_8:
      v10 = 0;
LABEL_91:
      v9 = a1;
      goto LABEL_92;
    }
    v19 = *((_DWORD *)v15 + 2);
    v20 = v65;
    v21 = (ProtectedNetDiagHelper *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
    Size[0] = (size_t)v21;
    if ( v21 )
      v22 = ProtectedNetDiagHelper::ProtectedNetDiagHelper(v21, v20, v19);
    else
      v22 = 0;
    if ( !v22 )
    {
      if ( v11 )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v58);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          &v58,
          L"CreateProtectedHelperInstance failed for %s",
          *a1);
        v23 = v58;
        (*(void (__fastcall **)(__int64, __int64, struct NetworkDiagnosticsEngine *))(*(_QWORD *)v11 + 96LL))(
          v11,
          1,
          v58);
        ATL::CStringData::Release((struct NetworkDiagnosticsEngine *)((char *)v23 - 24));
      }
      ((void (__fastcall *)(struct INetDiagHelper *))v65->lpVtbl->Release)(v65);
LABEL_20:
      TSimpleDeallocator<unsigned short *,void,void *,&void CoTaskMemFree(void *)>::~TSimpleDeallocator<unsigned short *,void,void *,&void CoTaskMemFree(void *)>(&v59);
      TSimpleDeallocator<unsigned short *,void,void *,&void CoTaskMemFree(void *)>::~TSimpleDeallocator<unsigned short *,void,void *,&void CoTaskMemFree(void *)>((void **)&v63);
      TSimpleDeallocator<unsigned short *,void,void *,&void CoTaskMemFree(void *)>::~TSimpleDeallocator<unsigned short *,void,void *,&void CoTaskMemFree(void *)>((void **)&v64);
      v10 = 0;
      goto LABEL_91;
    }
    if ( v60 )
    {
      v24 = ListToArray<tagHELPER_ATTRIBUTE>((__int64)v60);
      v25 = **(__int64 (__fastcall ***)(ProtectedNetDiagHelper *, _QWORD, _OWORD *))v22;
      v26 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>((unsigned __int64)v60[1]);
      v27 = v25(v22, v26, v24);
      CoTaskMemFree(v24);
      if ( v27 < 0 )
      {
        if ( v11 )
        {
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v58);
          v29 = (unsigned int)v27;
          v9 = a1;
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
            &v58,
            L"Initialize failed for %s, HR: %x",
            *a1,
            v29);
          v30 = v58;
          (*(void (__fastcall **)(__int64, __int64, struct NetworkDiagnosticsEngine *))(*(_QWORD *)v11 + 96LL))(
            v11,
            1,
            v58);
          ATL::CStringData::Release((struct NetworkDiagnosticsEngine *)((char *)v30 - 24));
LABEL_26:
          ProtectedNetDiagHelper::`scalar deleting destructor'(v22, v28);
          TSimpleDeallocator<unsigned short *,void,void *,&void CoTaskMemFree(void *)>::~TSimpleDeallocator<unsigned short *,void,void *,&void CoTaskMemFree(void *)>(&v59);
          TSimpleDeallocator<unsigned short *,void,void *,&void CoTaskMemFree(void *)>::~TSimpleDeallocator<unsigned short *,void,void *,&void CoTaskMemFree(void *)>((void **)&v63);
          TSimpleDeallocator<unsigned short *,void,void *,&void CoTaskMemFree(void *)>::~TSimpleDeallocator<unsigned short *,void,void *,&void CoTaskMemFree(void *)>((void **)&v64);
          v10 = 0;
          goto LABEL_92;
        }
LABEL_25:
        v9 = a1;
        goto LABEL_26;
      }
      v13 = (int)a1;
    }
    else
    {
      v27 = (**(__int64 (__fastcall ***)(ProtectedNetDiagHelper *, _QWORD, _QWORD))v22)(v22, 0, 0);
      if ( v27 < 0 )
      {
        if ( v11 )
        {
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v58);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
            &v58,
            L"Initialize failed for %s, HR: %x",
            *a1,
            (unsigned int)v27);
          v32 = v58;
          (*(void (__fastcall **)(__int64, __int64, struct NetworkDiagnosticsEngine *))(*(_QWORD *)v11 + 96LL))(
            v11,
            1,
            v58);
          ATL::CStringData::Release((struct NetworkDiagnosticsEngine *)((char *)v32 - 24));
        }
        ProtectedNetDiagHelper::`scalar deleting destructor'(v22, v31);
        goto LABEL_20;
      }
    }
    v33 = operator new(0x158u, (const struct std::nothrow_t *)&std::nothrow);
    Size[0] = (size_t)v33;
    if ( v33 )
    {
      *(_OWORD *)v67 = *(_OWORD *)v67[0];
      v10 = ProblemInstance::ProblemInstance((_DWORD)v33, v13, (_DWORD)v22, (unsigned int)v67, (__int64)pv);
    }
    else
    {
      v10 = 0;
    }
    if ( !v10 )
    {
      if ( v11 )
      {
        memset_0(v70, 0, 0x100u);
        v9 = a1;
        StringCchPrintfW(v70, 0x80u, L"Initialize failed for %s. Out of memory.", *a1);
        (*(void (__fastcall **)(__int64, __int64, unsigned __int16 *))(*(_QWORD *)v11 + 96LL))(v11, 1, v70);
        goto LABEL_26;
      }
      goto LABEL_25;
    }
    v34 = v15[2];
    v35 = -1;
    if ( v34 )
    {
      v36 = -1;
      do
        ++v36;
      while ( *(_WORD *)(v34 + 2 * v36) );
      ATL::CSimpleStringT<unsigned short,0>::SetString(v10 + 16, v34, v36);
    }
    v37 = v15[3];
    if ( v37 )
    {
      do
        ++v35;
      while ( *(_WORD *)(v37 + 2 * v35) );
      ATL::CSimpleStringT<unsigned short,0>::SetString(v10 + 24, v37, (unsigned int)v35);
    }
    if ( !v60 )
    {
LABEL_82:
      v53 = v68;
      *(_OWORD *)(v10 + 48) = v68;
      *(_QWORD *)(v10 + 64) = a5;
      v68 = v53;
      v54 = ((__int64 (__fastcall *)(struct INetDiagHelper *, __int128 *))v65->lpVtbl->SetLifeTime)(v65, &v68);
      if ( (int)(v54 + 0x80000000) < 0 || v54 == -2147467263 )
      {
        CProblemInstanceCache::Add(*((CProblemInstanceCache **)v58 + 6), (const FILETIME *)v10);
        v66 = 0;
        if ( (*(int (__fastcall **)(ProtectedNetDiagHelper *, LPVOID *))(*(_QWORD *)v22 + 8LL))(v22, &v66) >= 0 && v66 )
        {
          *(_DWORD *)(v10 + 224) = *(_DWORD *)v66;
          *(_DWORD *)(v10 + 228) = *((_DWORD *)v66 + 1);
          CoTaskMemFree(v66);
        }
        TSimpleDeallocator<unsigned short *,void,void *,&void CoTaskMemFree(void *)>::~TSimpleDeallocator<unsigned short *,void,void *,&void CoTaskMemFree(void *)>(&v59);
        TSimpleDeallocator<unsigned short *,void,void *,&void CoTaskMemFree(void *)>::~TSimpleDeallocator<unsigned short *,void,void *,&void CoTaskMemFree(void *)>((void **)&v63);
        TSimpleDeallocator<unsigned short *,void,void *,&void CoTaskMemFree(void *)>::~TSimpleDeallocator<unsigned short *,void,void *,&void CoTaskMemFree(void *)>((void **)&v64);
        goto LABEL_91;
      }
      if ( v11 )
      {
        memset_0(v79, 0, sizeof(v79));
        LODWORD(v56) = v54;
        v9 = a1;
        StringCchPrintfW(v79, 0x80u, L"SetLifeTime failed for %s, HR: %x", *a1, v56);
        (*(void (__fastcall **)(__int64, __int64, unsigned __int16 *))(*(_QWORD *)v11 + 96LL))(v11, 1, v79);
      }
      else
      {
        v9 = a1;
      }
      goto LABEL_81;
    }
    memset_0(v70, 0, 0x90u);
    v38 = operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
    Size[0] = (size_t)v38;
    v39 = 0;
    if ( v38 )
    {
      v40 = std::list<tagHELPER_ATTRIBUTE>::list<tagHELPER_ATTRIBUTE>(v38);
      v39 = 0;
    }
    else
    {
      v40 = 0;
    }
    *(_QWORD *)(v10 + 40) = v40;
    if ( !v40 )
    {
      v27 = -2147024882;
      pv = *(LPVOID *)v70;
LABEL_73:
      if ( v11 )
      {
        memset_0(v79, 0, sizeof(v79));
        LODWORD(v56) = v27;
        v9 = a1;
        StringCchPrintfW(v79, 0x80u, L"Initialize failed for %s while copying attributes, HR: %x", *a1, v56);
        (*(void (__fastcall **)(__int64, __int64, unsigned __int16 *))(*(_QWORD *)v11 + 96LL))(v11, 1, v79);
      }
      else
      {
        v9 = a1;
      }
      CoTaskMemFree(pv);
      if ( *(_DWORD *)&v70[4] == 10 )
      {
        v52 = v71[0];
        goto LABEL_80;
      }
      if ( *(_DWORD *)&v70[4] == 14 )
      {
        v52 = v71[1];
LABEL_80:
        CoTaskMemFree(v52);
      }
LABEL_81:
      ProblemInstance::`scalar deleting destructor'((ProblemInstance *)v10, v51);
      TSimpleDeallocator<unsigned short *,void,void *,&void CoTaskMemFree(void *)>::~TSimpleDeallocator<unsigned short *,void,void *,&void CoTaskMemFree(void *)>(&v59);
      TSimpleDeallocator<unsigned short *,void,void *,&void CoTaskMemFree(void *)>::~TSimpleDeallocator<unsigned short *,void,void *,&void CoTaskMemFree(void *)>((void **)&v63);
      TSimpleDeallocator<unsigned short *,void,void *,&void CoTaskMemFree(void *)>::~TSimpleDeallocator<unsigned short *,void,void *,&void CoTaskMemFree(void *)>((void **)&v64);
      v10 = 0;
      goto LABEL_92;
    }
    v41 = v60;
    v42 = *v60;
    while ( 1 )
    {
      v42 = (__int64 *)*v42;
      if ( v42 == *v41 )
        goto LABEL_82;
      *(_OWORD *)v70 = *((_OWORD *)v42 + 1);
      *(_OWORD *)v71 = *((_OWORD *)v42 + 2);
      v72 = *((_OWORD *)v42 + 3);
      v73 = *((_OWORD *)v42 + 4);
      v74 = *((_OWORD *)v42 + 5);
      v75 = *((_OWORD *)v42 + 6);
      v76 = *((_OWORD *)v42 + 7);
      v77 = *((_OWORD *)v42 + 8);
      v78 = *((_OWORD *)v42 + 9);
      pv = 0;
      if ( *((_DWORD *)v42 + 6) == 10 )
      {
        v71[0] = 0;
        v43 = (const unsigned __int16 *)v42[4];
        Size[0] = (size_t)v43;
        if ( !v43 )
          goto LABEL_64;
        v67[0] = 0;
        v27 = StringCchLengthW(v43, 0xFFFEu, v67);
        if ( v27 < 0 )
          goto LABEL_65;
        v44 = v67[0];
        v45 = CoTaskMemAlloc(2 * v67[0] + 2);
        v71[0] = v45;
        v39 = 0;
        if ( !v45 )
        {
LABEL_57:
          v27 = -2147024882;
          goto LABEL_65;
        }
        v27 = StringCchCopyW((unsigned __int16 *)v45, v44 + 1, (const unsigned __int16 *)Size[0]);
      }
      else
      {
        if ( *((_DWORD *)v42 + 6) != 14 )
          goto LABEL_65;
        LODWORD(v71[0]) = 0;
        v71[1] = 0;
        v46 = v42 + 4;
        if ( v42 == (__int64 *)-32LL || *v46 >= 0xFFFFu )
        {
LABEL_64:
          v27 = -2147024809;
          goto LABEL_65;
        }
        Size[0] = (unsigned int)*v46;
        v47 = CoTaskMemAlloc(LODWORD(Size[0]));
        v71[1] = v47;
        v39 = 0;
        if ( !v47 )
          goto LABEL_57;
        memcpy_0(v47, (const void *)v42[5], Size[0]);
        LODWORD(v71[0]) = *v46;
        v39 = 0;
        v27 = 0;
      }
LABEL_65:
      if ( v27 < 0 )
        goto LABEL_73;
      v48 = (const unsigned __int16 *)v42[2];
      Size[0] = (size_t)v48;
      if ( !v48 )
      {
        v27 = -2147024809;
        goto LABEL_73;
      }
      v67[0] = v39;
      v27 = StringCchLengthW(v48, 0xFFFEu, v67);
      if ( v27 < 0 )
        goto LABEL_73;
      v49 = v67[0];
      v50 = CoTaskMemAlloc(2 * v67[0] + 2);
      pv = v50;
      *(_QWORD *)v70 = v50;
      if ( !v50 )
      {
        v27 = -2147024882;
        goto LABEL_73;
      }
      v27 = StringCchCopyW((unsigned __int16 *)v50, v49 + 1, (const unsigned __int16 *)Size[0]);
      if ( v27 < 0 )
        goto LABEL_73;
      std::list<tagHELPER_ATTRIBUTE>::push_back(*(_QWORD *)(v10 + 40), v70);
      v41 = v60;
      v39 = 0;
    }
  }
  v10 = 0;
LABEL_92:
  ATL::CStringData::Release((ATL::CStringData *)(*v9 - 24LL));
  return v10;
}

```

## disassembly

```asm
0x1800121d0  mov     [rsp-8+arg_18], rbx
0x1800121d5  push    rbp
0x1800121d6  push    rsi
0x1800121d7  push    rdi
0x1800121d8  push    r12
0x1800121da  push    r13
0x1800121dc  push    r14
0x1800121de  push    r15
0x1800121e0  lea     rbp, [rsp-1E0h]
0x1800121e8  sub     rsp, 2E0h
0x1800121ef  mov     rax, cs:__security_cookie
0x1800121f6  xor     rax, rsp
0x1800121f9  mov     [rbp+210h+var_40], rax
0x180012200  mov     rbx, r9
0x180012203  mov     rsi, r8
0x180012206  mov     [rbp+210h+var_270], r8
0x18001220a  mov     [rsp+310h+var_2C8], rdx
0x18001220f  mov     r15, rcx
0x180012212  mov     [rsp+310h+var_2E0], rcx
0x180012217  mov     [rbp+210h+var_250], rcx
0x18001221b  mov     r13b, [rbp+210h+arg_28]
0x180012222  mov     r12, [rbp+210h+arg_30]
0x180012229  mov     [rsp+310h+pv], r12
0x18001222e  call    ?Instance@NetworkDiagnosticsEngine@@SAPEAV1@XZ; NetworkDiagnosticsEngine::Instance(void)
0x180012233  mov     [rsp+310h+var_2D8], rax
0x180012238  xorps   xmm0, xmm0
0x18001223b  movups  [rsp+310h+var_2A0], xmm0
0x180012240  xor     edi, edi
0x180012242  test    rax, rax
0x180012245  jnz     short loc_18001224E
0x180012247  mov     esi, edi
0x180012249  jmp     loc_180012B05
0x18001224e  mov     r14, rdi
0x180012251  call    ?Instance@NetworkDiagnosticsEngine@@SAPEAV1@XZ; NetworkDiagnosticsEngine::Instance(void)
0x180012256  test    rax, rax
0x180012259  jz      short loc_180012263
0x18001225b  call    ?Instance@NetworkDiagnosticsEngine@@SAPEAV1@XZ; NetworkDiagnosticsEngine::Instance(void)
0x180012260  mov     r14, [rax]
0x180012263  mov     qword ptr [rbp+210h+var_260], rbx
0x180012267  mov     rdi, [rbp+210h+arg_20]
0x18001226e  mov     qword ptr [rbp+210h+var_260+8], rdi
0x180012272  mov     [rsp+310h+Size], rbx
0x180012277  mov     [rsp+310h+var_2A8], rdi
0x18001227c  movaps  xmm0, xmmword ptr [rsi]
0x18001227f  movdqa  [rbp+210h+var_290], xmm0
0x180012284  lea     rax, [rsp+310h+Size]
0x180012289  mov     [rsp+310h+var_2F0], rax
0x18001228e  lea     r9, [rbp+210h+var_290]
0x180012292  mov     rbx, [rsp+310h+var_2C8]
0x180012297  mov     r8, rbx
0x18001229a  mov     rdx, r15
0x18001229d  mov     rcx, [rsp+310h+var_2D8]
0x1800122a2  call    ?FindProblemInstance@NetworkDiagnosticsEngine@@QEAAPEAVProblemInstance@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV?$list@UtagHELPER_ATTRIBUTE@@V?$allocator@UtagHELPER_ATTRIBUTE@@@std@@@std@@U_GUID@@UtagLIFE_TIME@@@Z; NetworkDiagnosticsEngine::FindProblemInstance(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,std::list<tagHELPER_ATTRIBUTE> *,_GUID,tagLIFE_TIME)
0x1800122a7  mov     rsi, rax
0x1800122aa  test    rax, rax
0x1800122ad  jz      short loc_1800122BB
0x1800122af  mov     [rax+150h], r12
0x1800122b6  jmp     loc_180012B05
0x1800122bb  mov     [rsp+310h+var_2E8], r12
0x1800122c0  mov     byte ptr [rsp+310h+var_2F0], r13b
0x1800122c5  lea     r9, [rsp+310h+var_2A0]
0x1800122ca  mov     r8, rbx
0x1800122cd  mov     rsi, [rsp+310h+var_2E0]
0x1800122d2  mov     rdx, rsi
0x1800122d5  mov     rax, [rsp+310h+var_2D8]
0x1800122da  mov     rcx, [rax+28h]
0x1800122de  call    ?GetClassFactory@HelperClassRepository@@QEAAPEAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV?$list@UtagHELPER_ATTRIBUTE@@V?$allocator@UtagHELPER_ATTRIBUTE@@@std@@@std@@PEAU_GUID@@_NPEAVSQMSession@@@Z; HelperClassRepository::GetClassFactory(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,std::list<tagHELPER_ATTRIBUTE> *,_GUID *,bool,SQMSession *)
0x1800122e3  mov     r13, rax
0x1800122e6  xor     r12d, r12d
0x1800122e9  test    rax, rax
0x1800122ec  jnz     short loc_1800122F6
0x1800122ee  mov     rsi, r12
0x1800122f1  jmp     loc_180012B00
0x1800122f6  mov     qword ptr [rbp+210h+var_290], r13
0x1800122fa  mov     rax, [rax+10h]
0x1800122fe  mov     qword ptr [rsp+310h+var_2A0], rax
0x180012303  mov     rax, [r13+18h]
0x180012307  mov     [rsp+310h+var_2D0], rax
0x18001230c  mov     rbx, [r13+0]
0x180012310  mov     [rbp+210h+var_280], r12
0x180012314  mov     rax, [rbx]
0x180012317  lea     r9, [rbp+210h+var_280]
0x18001231b  lea     r8, IID_INetDiagHelper
0x180012322  xor     edx, edx
0x180012324  mov     rcx, rbx
0x180012327  mov     rax, [rax+18h]
0x18001232b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012330  mov     r15d, eax
0x180012333  mov     rdx, [rbx]
0x180012336  mov     rcx, rbx
0x180012339  mov     rax, [rdx+10h]
0x18001233d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012342  test    r15d, r15d
0x180012345  jns     short loc_1800123B9
0x180012347  test    r14, r14
0x18001234a  jz      short loc_180012395
0x18001234c  lea     rcx, [rsp+310h+var_2D8]
0x180012351  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180012356  nop
0x180012357  mov     r9d, r15d
0x18001235a  mov     r8, [rsi]
0x18001235d  lea     rdx, aCreateinstance_0; "CreateInstance failed for %s, HR: %x"
0x180012364  lea     rcx, [rsp+310h+var_2D8]
0x180012369  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18001236e  mov     rax, [r14]
0x180012371  mov     rbx, [rsp+310h+var_2D8]
0x180012376  mov     r8, rbx
0x180012379  mov     edx, 1
0x18001237e  mov     rcx, r14
0x180012381  mov     rax, [rax+60h]
0x180012385  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001238a  nop
0x18001238b  lea     rcx, [rbx-18h]; this
0x18001238f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180012394  nop
0x180012395  lea     rcx, [rsp+310h+var_2D0]
0x18001239a  call    ??1?$TSimpleDeallocator@PEAGXPEAX$1?CoTaskMemFree@@YAXPEAX@Z@@QEAA@XZ; TSimpleDeallocator<ushort *,void,void *,&CoTaskMemFree(void *)>::~TSimpleDeallocator<ushort *,void,void *,&CoTaskMemFree(void *)>(void)
0x18001239f  nop
0x1800123a0  lea     rcx, [rsp+310h+var_2A0]
0x1800123a5  call    ??1?$TSimpleDeallocator@PEAGXPEAX$1?CoTaskMemFree@@YAXPEAX@Z@@QEAA@XZ; TSimpleDeallocator<ushort *,void,void *,&CoTaskMemFree(void *)>::~TSimpleDeallocator<ushort *,void,void *,&CoTaskMemFree(void *)>(void)
0x1800123aa  nop
0x1800123ab  lea     rcx, [rbp+210h+var_290]
0x1800123af  call    ??1?$TSimpleDeallocator@PEAGXPEAX$1?CoTaskMemFree@@YAXPEAX@Z@@QEAA@XZ; TSimpleDeallocator<ushort *,void,void *,&CoTaskMemFree(void *)>::~TSimpleDeallocator<ushort *,void,void *,&CoTaskMemFree(void *)>(void)
0x1800123b4  jmp     loc_1800122EE
0x1800123b9  mov     ebx, [r13+8]
0x1800123bd  mov     r15, [rbp+210h+var_280]
0x1800123c1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800123c8  mov     ecx, 28h ; '('; unsigned __int64
0x1800123cd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800123d2  mov     [rsp+310h+Size], rax
0x1800123d7  test    rax, rax
0x1800123da  jz      short loc_1800123F1
0x1800123dc  mov     r8d, ebx; int
0x1800123df  mov     rdx, r15; struct INetDiagHelper *
0x1800123e2  mov     rcx, rax; this
0x1800123e5  call    ??0ProtectedNetDiagHelper@@QEAA@PEAUINetDiagHelper@@H@Z; ProtectedNetDiagHelper::ProtectedNetDiagHelper(INetDiagHelper *,int)
0x1800123ea  mov     r12, rax
0x1800123ed  xor     ebx, ebx
0x1800123ef  jmp     short loc_1800123F6
0x1800123f1  xor     ebx, ebx
0x1800123f3  mov     r12d, ebx
0x1800123f6  test    r12, r12
0x1800123f9  jnz     loc_180012483
0x1800123ff  test    r14, r14
0x180012402  jz      short loc_18001244B
0x180012404  lea     rcx, [rsp+310h+var_2D8]
0x180012409  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001240e  nop
0x18001240f  mov     r8, [rsi]
0x180012412  lea     rdx, aCreateprotecte; "CreateProtectedHelperInstance failed fo"...
0x180012419  lea     rcx, [rsp+310h+var_2D8]
0x18001241e  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180012423  mov     rax, [r14]
0x180012426  mov     rbx, [rsp+310h+var_2D8]
0x18001242b  mov     r8, rbx
0x18001242e  lea     edx, [r12+1]
0x180012433  mov     rcx, r14
0x180012436  mov     rax, [rax+60h]
0x18001243a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001243f  nop
0x180012440  lea     rcx, [rbx-18h]; this
0x180012444  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180012449  xor     ebx, ebx
0x18001244b  mov     rcx, [rbp+210h+var_280]
0x18001244f  mov     rax, [rcx]
0x180012452  mov     rax, [rax+10h]
0x180012456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001245b  nop
0x18001245c  lea     rcx, [rsp+310h+var_2D0]
0x180012461  call    ??1?$TSimpleDeallocator@PEAGXPEAX$1?CoTaskMemFree@@YAXPEAX@Z@@QEAA@XZ; TSimpleDeallocator<ushort *,void,void *,&CoTaskMemFree(void *)>::~TSimpleDeallocator<ushort *,void,void *,&CoTaskMemFree(void *)>(void)
0x180012466  nop
0x180012467  lea     rcx, [rsp+310h+var_2A0]
0x18001246c  call    ??1?$TSimpleDeallocator@PEAGXPEAX$1?CoTaskMemFree@@YAXPEAX@Z@@QEAA@XZ; TSimpleDeallocator<ushort *,void,void *,&CoTaskMemFree(void *)>::~TSimpleDeallocator<ushort *,void,void *,&CoTaskMemFree(void *)>(void)
0x180012471  nop
0x180012472  lea     rcx, [rbp+210h+var_290]
0x180012476  call    ??1?$TSimpleDeallocator@PEAGXPEAX$1?CoTaskMemFree@@YAXPEAX@Z@@QEAA@XZ; TSimpleDeallocator<ushort *,void,void *,&CoTaskMemFree(void *)>::~TSimpleDeallocator<ushort *,void,void *,&CoTaskMemFree(void *)>(void)
0x18001247b  mov     rsi, rbx
0x18001247e  jmp     loc_180012B00
0x180012483  mov     r15, [rsp+310h+var_2C8]
0x180012488  test    r15, r15
0x18001248b  jz      loc_18001255E
0x180012491  mov     rcx, r15
0x180012494  call    ??$ListToArray@UtagHELPER_ATTRIBUTE@@@@YAPEAUtagHELPER_ATTRIBUTE@@PEAV?$list@UtagHELPER_ATTRIBUTE@@V?$allocator@UtagHELPER_ATTRIBUTE@@@std@@@std@@@Z; ListToArray<tagHELPER_ATTRIBUTE>(std::list<tagHELPER_ATTRIBUTE> *)
0x180012499  mov     rsi, rax
0x18001249c  mov     rcx, [r12]
0x1800124a0  mov     rbx, [rcx]
0x1800124a3  mov     rcx, [r15+8]
0x1800124a7  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x1800124ac  mov     r8, rsi
0x1800124af  mov     edx, eax
0x1800124b1  mov     rcx, r12
0x1800124b4  mov     rax, rbx
0x1800124b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124bc  mov     r15d, eax
0x1800124bf  mov     rcx, rsi; pv
0x1800124c2  call    cs:__imp_CoTaskMemFree
0x1800124c8  xor     ebx, ebx
0x1800124ca  test    r15d, r15d
0x1800124cd  jns     loc_1800125D5
0x1800124d3  test    r14, r14
0x1800124d6  jz      short loc_180012529
0x1800124d8  lea     rcx, [rsp+310h+var_2D8]
0x1800124dd  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800124e2  nop
0x1800124e3  mov     r9d, r15d
0x1800124e6  mov     r15, [rsp+310h+var_2E0]
0x1800124eb  mov     r8, [r15]
0x1800124ee  lea     rdx, aInitializeFail; "Initialize failed for %s, HR: %x"
0x1800124f5  lea     rcx, [rsp+310h+var_2D8]
0x1800124fa  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x1800124ff  mov     rax, [r14]
0x180012502  mov     rbx, [rsp+310h+var_2D8]
0x180012507  mov     r8, rbx
0x18001250a  mov     edx, 1
0x18001250f  mov     rcx, r14
0x180012512  mov     rax, [rax+60h]
0x180012516  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001251b  nop
0x18001251c  lea     rcx, [rbx-18h]; this
0x180012520  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180012525  xor     ebx, ebx
0x180012527  jmp     short loc_18001252E
0x180012529  mov     r15, [rsp+310h+var_2E0]
0x18001252e  mov     rcx, r12; this
0x180012531  call    ??_GProtectedNetDiagHelper@@QEAAPEAXI@Z; ProtectedNetDiagHelper::`scalar deleting destructor'(uint)
0x180012536  nop
0x180012537  lea     rcx, [rsp+310h+var_2D0]
0x18001253c  call    ??1?$TSimpleDeallocator@PEAGXPEAX$1?CoTaskMemFree@@YAXPEAX@Z@@QEAA@XZ; TSimpleDeallocator<ushort *,void,void *,&CoTaskMemFree(void *)>::~TSimpleDeallocator<ushort *,void,void *,&CoTaskMemFree(void *)>(void)
0x180012541  nop
0x180012542  lea     rcx, [rsp+310h+var_2A0]
0x180012547  call    ??1?$TSimpleDeallocator@PEAGXPEAX$1?CoTaskMemFree@@YAXPEAX@Z@@QEAA@XZ; TSimpleDeallocator<ushort *,void,void *,&CoTaskMemFree(void *)>::~TSimpleDeallocator<ushort *,void,void *,&CoTaskMemFree(void *)>(void)
0x18001254c  nop
0x18001254d  lea     rcx, [rbp+210h+var_290]
0x180012551  call    ??1?$TSimpleDeallocator@PEAGXPEAX$1?CoTaskMemFree@@YAXPEAX@Z@@QEAA@XZ; TSimpleDeallocator<ushort *,void,void *,&CoTaskMemFree(void *)>::~TSimpleDeallocator<ushort *,void,void *,&CoTaskMemFree(void *)>(void)
0x180012556  mov     rsi, rbx
0x180012559  jmp     loc_180012B05
0x18001255e  mov     rax, [r12]
0x180012562  xor     r8d, r8d
0x180012565  xor     edx, edx
0x180012567  mov     rcx, r12
0x18001256a  mov     rax, [rax]
0x18001256d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012572  mov     r15d, eax
0x180012575  test    eax, eax
0x180012577  jns     short loc_1800125DA
0x180012579  test    r14, r14
0x18001257c  jz      short loc_1800125C8
0x18001257e  lea     rcx, [rsp+310h+var_2D8]
0x180012583  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180012588  nop
0x180012589  mov     r9d, r15d
0x18001258c  mov     r8, [rsi]
0x18001258f  lea     rdx, aInitializeFail; "Initialize failed for %s, HR: %x"
0x180012596  lea     rcx, [rsp+310h+var_2D8]
0x18001259b  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x1800125a0  mov     rax, [r14]
0x1800125a3  mov     rbx, [rsp+310h+var_2D8]
0x1800125a8  mov     r8, rbx
0x1800125ab  mov     edx, 1
0x1800125b0  mov     rcx, r14
0x1800125b3  mov     rax, [rax+60h]
0x1800125b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125bc  nop
0x1800125bd  lea     rcx, [rbx-18h]; this
0x1800125c1  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800125c6  xor     ebx, ebx
0x1800125c8  mov     rcx, r12; this
0x1800125cb  call    ??_GProtectedNetDiagHelper@@QEAAPEAXI@Z; ProtectedNetDiagHelper::`scalar deleting destructor'(uint)
0x1800125d0  jmp     loc_18001245C
0x1800125d5  mov     rsi, [rsp+310h+var_2E0]
0x1800125da  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800125e1  mov     ecx, 158h; unsigned __int64
0x1800125e6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800125eb  mov     [rsp+310h+Size], rax
0x1800125f0  test    rax, rax
0x1800125f3  jz      short loc_180012622
0x1800125f5  mov     rcx, [rbp+210h+var_270]
0x1800125f9  movaps  xmm0, xmmword ptr [rcx]
0x1800125fc  movdqa  xmmword ptr [rbp+210h+var_270], xmm0
0x180012601  mov     rcx, [rsp+310h+pv]
0x180012606  mov     [rsp+310h+var_2F0], rcx
0x18001260b  lea     r9, [rbp+210h+var_270]
0x18001260f  mov     r8, r12
0x180012612  mov     rdx, rsi
0x180012615  mov     rcx, rax
0x180012618  call    ??0ProblemInstance@@AEAA@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVProtectedNetDiagHelper@@U_GUID@@PEAVSQMSession@@@Z; ProblemInstance::ProblemInstance(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ProtectedNetDiagHelper *,_GUID,SQMSession *)
0x18001261d  mov     rsi, rax
0x180012620  jmp     short loc_180012625
0x180012622  mov     rsi, rbx
0x180012625  test    rsi, rsi
0x180012628  jnz     short loc_18001267C
0x18001262a  test    r14, r14
0x18001262d  jz      loc_180012529
0x180012633  xor     edx, edx; Val
0x180012635  mov     r8d, 100h; Size
0x18001263b  lea     rcx, [rbp+210h+var_240]; void *
0x18001263f  call    memset_0
0x180012644  mov     r15, [rsp+310h+var_2E0]
0x180012649  mov     r9, [r15]
0x18001264c  lea     r8, aInitializeFail_1; "Initialize failed for %s. Out of memory"...
  ... truncated ...
```
