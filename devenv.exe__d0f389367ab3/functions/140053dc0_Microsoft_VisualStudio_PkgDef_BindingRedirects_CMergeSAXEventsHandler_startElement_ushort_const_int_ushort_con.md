# Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeSAXEventsHandler::startElement(ushort const *,int,ushort const *,int,ushort const *,int,ISAXAttributes *)

- ea: `0x140053dc0`
- end: `0x140054faa`
- name: `?startElement@CMergeSAXEventsHandler@BindingRedirects@PkgDef@VisualStudio@Microsoft@@UEAAJPEBGH0H0HPEAUISAXAttributes@@@Z`
- size: `4586`
- prototype: `__int64 __fastcall(Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeSAXEventsHandler *__hidden this, const unsigned __int16 *, int, const unsigned __int16 *, int, const unsigned __int16 *, int, struct ISAXAttributes *)`
- caller_count: `0`
- callee_count: `25`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x140001020`
- `0x140001040`
- `0x140002160`
- `0x140002c10`
- `0x140002f00`
- `0x140003160`
- `0x140004950`
- `0x140007740`
- `0x140010138`
- `0x140010378`
- `0x14001fa6c`
- `0x140033ab0`
- `0x14003b95c`
- `0x1400451e0`
- `0x140046514`
- `0x14004cfd8`
- `0x14004d098`
- `0x14004d190`
- `0x140050084`
- `0x140053dc0`
- `0x140054fac`
- `0x140055058`
- `0x1400595a4`
- `0x14006044c`
- `0x140060558`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x140053e57`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x140053e85`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x140054221`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x140054b57`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x140053e57`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x140053e85`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x140054221`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x140054b57`

## string_xrefs

- `0x140053f74`: `publicKeyToken`
- `0x1400543ca`: `Could not set public key token for binding redirect`
- `0x140054d37`: `Could not retrieve attribute value for file path`
- `0x140054dc0`: `Could not set file path for code base`
- `0x140053faa`: `Could not set public key token for assembly identity`

## pseudocode

```c
__int64 __fastcall Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeSAXEventsHandler::startElement(
        Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeSAXEventsHandler *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned __int16 *a4,
        unsigned int a5,
        const unsigned __int16 *a6,
        int a7,
        struct ISAXAttributes *a8)
{
  unsigned __int16 *v8; // rdi
  struct ISAXAttributes *v9; // rsi
  unsigned int v11; // r12d
  int v12; // r15d
  struct ATL::IAtlStringMgr *Instance; // rax
  wchar_t *v14; // r14
  struct ATL::IAtlStringMgr *v15; // rax
  struct ATL::IAtlStringMgr *v16; // rax
  unsigned __int16 *v17; // rbx
  struct ATL::IAtlStringMgr *v18; // rax
  unsigned __int16 *v19; // rdi
  __int64 v20; // rcx
  int AttributeValue; // eax
  wchar_t *v22; // rsi
  const unsigned __int16 *v23; // rcx
  __int64 v24; // r8
  int v25; // eax
  Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase *v26; // rcx
  __int64 Lower; // rax
  wchar_t *v28; // rdx
  int v29; // eax
  __int64 v30; // r8
  wchar_t *v31; // rax
  __int64 v32; // rax
  void (__fastcall ***v33)(_QWORD, __int64); // rcx
  Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase *v34; // rax
  Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase *v35; // rbx
  __int64 v36; // rax
  void (__fastcall ***v37)(_QWORD, __int64); // rcx
  struct ATL::IAtlStringMgr *v38; // rax
  __int64 v39; // rax
  __int64 v40; // rcx
  __int64 v41; // rdx
  struct ATL::IAtlStringMgr *v42; // rax
  __int64 v43; // rax
  const wchar_t *v44; // r8
  unsigned __int16 *v45; // rbx
  volatile signed __int32 *v46; // rdx
  __int64 v47; // r8
  Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase *v48; // rcx
  __int64 v49; // rax
  __int64 v50; // rbx
  struct ATL::IAtlStringMgr *v51; // rax
  __int64 v52; // rax
  wchar_t *v53; // rdx
  __int64 v54; // rdx
  struct ATL::IAtlStringMgr *v55; // rax
  __int64 v56; // r8
  struct ATL::IAtlStringMgr *v57; // rax
  struct ATL::IAtlStringMgr *v58; // rax
  __int64 v59; // rax
  wchar_t *v60; // rdi
  __int64 v61; // rcx
  int v62; // eax
  unsigned __int16 *v63; // rsi
  struct ATL::IAtlStringMgr *v64; // rax
  __int64 v65; // rax
  const wchar_t *v66; // r8
  __int64 v67; // rcx
  struct ATL::IAtlStringMgr *v68; // rax
  unsigned __int16 *v69; // rbx
  wchar_t *v70; // rcx
  wchar_t *v71; // rax
  wchar_t *v72; // rdx
  unsigned __int16 *v73; // rdx
  volatile signed __int32 *v74; // rdx
  int v75; // r12d
  int v76; // ebx
  wchar_t *v77; // rdx
  unsigned __int16 *v78; // rdx
  wchar_t *v79; // rdx
  volatile signed __int32 *v80; // rdx
  wchar_t *v81; // rdx
  wchar_t *v82; // rdx
  Microsoft::VisualStudio::PkgDef::BindingRedirects::CBindingRedirect *v83; // rax
  Microsoft::VisualStudio::PkgDef::BindingRedirects::CBindingRedirect *v84; // rbx
  __int64 v85; // rax
  void (__fastcall ***v86)(_QWORD, __int64); // rcx
  unsigned __int16 *v87; // rdx
  unsigned __int16 *v88; // rdx
  Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase *v89; // rax
  Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase *v90; // rbx
  __int64 v91; // rax
  void (__fastcall ***v92)(_QWORD, __int64); // rcx
  struct ATL::IAtlStringMgr *v93; // rax
  __int64 v94; // rax
  __int64 v95; // rcx
  struct ATL::IAtlStringMgr *v96; // rax
  struct ATL::IAtlStringMgr *v97; // rax
  unsigned __int16 *v98; // rdi
  struct ATL::IAtlStringMgr *v99; // rax
  volatile signed __int32 *v100; // r12
  __int64 v101; // rcx
  int v102; // eax
  unsigned __int16 *v103; // rsi
  struct ATL::IAtlStringMgr *v104; // rax
  __int64 v105; // rax
  const wchar_t *v106; // r8
  struct ATL::IAtlStringMgr *v107; // rax
  _DWORD *v108; // rcx
  struct ATL::IAtlStringMgr *v109; // rax
  unsigned __int16 *v110; // rbx
  struct ATL::IAtlStringMgr *v111; // rax
  unsigned __int16 *v112; // rbx
  wchar_t *v113; // rdx
  __int64 v114; // r8
  wchar_t *v115; // rdx
  unsigned __int16 *v117; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v118; // [rsp+48h] [rbp-B8h] BYREF
  int v119; // [rsp+50h] [rbp-B0h] BYREF
  int v120; // [rsp+58h] [rbp-A8h] BYREF
  int v121; // [rsp+5Ch] [rbp-A4h]
  int v122; // [rsp+60h] [rbp-A0h]
  int v123; // [rsp+64h] [rbp-9Ch]
  wchar_t *Str; // [rsp+68h] [rbp-98h] BYREF
  int v125; // [rsp+70h] [rbp-90h]
  int v126; // [rsp+74h] [rbp-8Ch]
  unsigned int v127; // [rsp+78h] [rbp-88h]
  struct ISAXAttributes *v128; // [rsp+80h] [rbp-80h]
  int v129; // [rsp+88h] [rbp-78h]
  int v130; // [rsp+8Ch] [rbp-74h]
  int v131; // [rsp+90h] [rbp-70h]
  int v132; // [rsp+94h] [rbp-6Ch]
  int v133; // [rsp+98h] [rbp-68h]
  int v134; // [rsp+A0h] [rbp-60h] BYREF
  int v135; // [rsp+A4h] [rbp-5Ch]
  int v136; // [rsp+A8h] [rbp-58h]
  int v137; // [rsp+ACh] [rbp-54h]
  unsigned int v138; // [rsp+B0h] [rbp-50h]
  const unsigned __int16 *v139; // [rsp+B8h] [rbp-48h]
  const unsigned __int16 *v140; // [rsp+C0h] [rbp-40h]
  wchar_t *String1; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int16 *v142[2]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v143[3]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v144[8]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v145[8]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v146[16]; // [rsp+108h] [rbp+8h] BYREF
  wchar_t *v147; // [rsp+118h] [rbp+18h]
  int v148; // [rsp+120h] [rbp+20h]
  int v149; // [rsp+124h] [rbp+24h]
  int v150; // [rsp+130h] [rbp+30h]
  int v151; // [rsp+134h] [rbp+34h]
  int v152; // [rsp+138h] [rbp+38h]
  int v153; // [rsp+13Ch] [rbp+3Ch]
  int v154; // [rsp+140h] [rbp+40h]
  int v155; // [rsp+144h] [rbp+44h]
  int v156; // [rsp+148h] [rbp+48h]
  int v157; // [rsp+14Ch] [rbp+4Ch]

  v8 = a4;
  v9 = a8;
  v11 = a5;
  v12 = 0;
  v117 = a4;
  v138 = a3;
  v140 = a2;
  v127 = a5;
  v139 = a6;
  v128 = a8;
  if ( !*((_QWORD *)this + 21) )
    return (unsigned int)v12;
  String1 = 0;
  Instance = ATL::CAtlStringMgr::GetInstance();
  ATL::CSimpleStringT<unsigned short,0>::CSimpleStringT<unsigned short,0>(&String1, v8, a5, Instance);
  v14 = String1;
  if ( !_wcsicmp(String1, L"dependentAssembly") )
  {
    *((_BYTE *)this + 192) = 1;
    goto LABEL_50;
  }
  if ( *((_BYTE *)this + 192) )
  {
    if ( !_wcsicmp(v14, L"assemblyIdentity") )
    {
      memset_0(v143, 0, 0x50u);
      Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase::CCodeBase((Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase *)v143);
      v15 = ATL::CAtlStringMgr::GetInstance();
      if ( !v15
        || (String1 = (wchar_t *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v15 + 24LL))(v15)
                                + 24),
            (v16 = ATL::CAtlStringMgr::GetInstance()) == 0)
        || (v17 = (unsigned __int16 *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v16 + 24LL))(v16)
                                     + 24),
            v118 = v17,
            (v18 = ATL::CAtlStringMgr::GetInstance()) == 0) )
      {
        ATL::AtlThrowImpl(-2147467259);
      }
      v19 = (unsigned __int16 *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v18 + 24LL))(v18)
                               + 24);
      v142[0] = v19;
      AttributeValue = Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeSAXEventsHandler::GetAttributeValue(
                         v20,
                         a8,
                         L"name",
                         &String1);
      v22 = String1;
      v12 = AttributeValue;
      if ( AttributeValue < 0 )
      {
        v23 = L"Couldn't find name for assembly identity";
LABEL_27:
        _mm_lfence();
        CLogger::LogError(v23, v12, 0);
        if ( _InterlockedDecrement((volatile signed __int32 *)v19 - 2) <= 0 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v19 - 3) + 8LL))(*((_QWORD *)v19 - 3));
        }
        if ( _InterlockedDecrement((volatile signed __int32 *)v17 - 2) <= 0 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v17 - 3) + 8LL))(*((_QWORD *)v17 - 3));
        }
        if ( _InterlockedDecrement((volatile signed __int32 *)v22 - 2) <= 0 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v22 - 3) + 8LL))(*((_QWORD *)v22 - 3));
        }
LABEL_170:
        Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase::~CCodeBase((Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase *)v143);
LABEL_52:
        if ( _InterlockedDecrement((volatile signed __int32 *)v14 - 2) <= 0 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v14 - 3) + 8LL))(*((_QWORD *)v14 - 3));
        }
        return (unsigned int)v12;
      }
      if ( !String1 )
      {
        v23 = L"Could not set name for assembly identity";
LABEL_26:
        v12 = -2147467261;
        goto LABEL_27;
      }
      v24 = -1;
      do
        ++v24;
      while ( String1[v24] );
      ATL::CSimpleStringT<unsigned short,0>::SetString(v144, String1);
      v12 = 0;
      _mm_lfence();
      v25 = Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeSAXEventsHandler::GetAttributeValue(
              0,
              v128,
              L"publicKeyToken",
              &v118);
      v17 = v118;
      if ( !v25 )
      {
        if ( !v118 )
        {
          v12 = -2147467261;
LABEL_20:
          v23 = L"Could not set public key token for assembly identity";
          goto LABEL_27;
        }
        if ( !Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase::IsValidPublicKeyToken(v26, v118) )
        {
          v12 = -2147024809;
          goto LABEL_20;
        }
        String1 = 0;
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &String1,
          v17);
        Lower = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::MakeLower(&String1);
        ATL::CSimpleStringT<unsigned short,0>::operator=(v145, Lower);
        v28 = String1 - 12;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)String1 - 2, 0xFFFFFFFF) <= 1 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v28 + 8LL))(*(_QWORD *)v28);
        }
      }
      _mm_lfence();
      v29 = Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeSAXEventsHandler::GetAttributeValue(
              v26,
              v128,
              L"culture",
              v142);
      v19 = v142[0];
      if ( !v29 )
      {
        if ( !v142[0] )
        {
          v23 = L"Could not set culture for assembly identity";
          goto LABEL_26;
        }
        v30 = -1;
        do
          ++v30;
        while ( v142[0][v30] );
        ATL::CSimpleStringT<unsigned short,0>::SetString(v146, v142[0]);
        v12 = 0;
      }
      v31 = (wchar_t *)operator new(0x50u);
      String1 = v31;
      if ( v31 )
      {
        memset_0(v31, 0, 0x50u);
        v32 = Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase::CCodeBase(
                (Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase *)String1,
                (const struct Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase *)v143);
      }
      else
      {
        v32 = 0;
      }
      v33 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 22);
      *((_QWORD *)this + 22) = v32;
      if ( v33 )
        (**v33)(v33, 1);
      if ( _InterlockedDecrement((volatile signed __int32 *)v19 - 2) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v19 - 3) + 8LL))(*((_QWORD *)v19 - 3));
      }
      if ( _InterlockedDecrement((volatile signed __int32 *)v17 - 2) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v17 - 3) + 8LL))(*((_QWORD *)v17 - 3));
      }
      if ( _InterlockedDecrement((volatile signed __int32 *)v22 - 2) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v22 - 3) + 8LL))(*((_QWORD *)v22 - 3));
      }
      goto LABEL_48;
    }
    if ( *((_BYTE *)this + 192) )
    {
      if ( !_wcsicmp(v14, L"bindingRedirect") )
      {
        if ( !*((_QWORD *)this + 22) )
        {
          v34 = (Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase *)operator new(0x50u);
          v35 = v34;
          if ( v34 )
          {
            memset_0(v34, 0, 0x50u);
            v36 = Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase::CCodeBase(v35);
          }
          else
          {
            v36 = 0;
          }
          v37 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 22);
          *((_QWORD *)this + 22) = v36;
          if ( v37 )
            (**v37)(v37, 1);
        }
        memset_0(v143, 0, 0x70u);
        Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase::CCodeBase((Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase *)v143);
        v143[0] = &Microsoft::VisualStudio::PkgDef::BindingRedirects::CBindingRedirect::`vftable';
        v153 = -1;
        v152 = -1;
        v151 = -1;
        v150 = -1;
        v157 = -1;
        v156 = -1;
        v155 = -1;
        v154 = -1;
        v38 = ATL::CAtlStringMgr::GetInstance();
        if ( !v38 )
          goto LABEL_222;
        v39 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v38 + 24LL))(v38);
        v40 = *((_QWORD *)this + 22);
        v142[0] = (unsigned __int16 *)(v39 + 24);
        (*(void (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v40 + 16LL))(v40, v142);
        v41 = *(_QWORD *)(*((_QWORD *)this + 22) + 24LL);
        if ( !v41 )
        {
          v12 = -2147467261;
          v42 = ATL::CAtlStringMgr::GetInstance();
          if ( v42 )
          {
            _mm_lfence();
            v43 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v42 + 24LL))(v42);
            v44 = L"Could not set name for binding redirect";
LABEL_66:
            v117 = (unsigned __int16 *)(v43 + 24);
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
              &v117,
              L"%s: %s",
              v44,
              v142[0]);
            v45 = v117;
            CLogger::LogError(v117, v12, 0);
            v46 = (volatile signed __int32 *)(v45 - 12);
LABEL_166:
            if ( _InterlockedDecrement(v46 + 4) <= 0 )
            {
              _mm_lfence();
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v46 + 8LL))(*(_QWORD *)v46);
            }
            v88 = v142[0] - 12;
            if ( _InterlockedDecrement((volatile signed __int32 *)v142[0] - 2) <= 0 )
            {
              _mm_lfence();
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v88 + 8LL))(*(_QWORD *)v88);
            }
            goto LABEL_170;
          }
          goto LABEL_222;
        }
        v47 = -1;
        do
          ++v47;
        while ( *(_WORD *)(v41 + 2 * v47) );
        ATL::CSimpleStringT<unsigned short,0>::SetString(v144, v41);
        v49 = *((_QWORD *)this + 22);
        v50 = *(_QWORD *)(v49 + 32);
        if ( !v50 )
        {
          v12 = -2147467261;
          goto LABEL_73;
        }
        if ( !Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase::IsValidPublicKeyToken(
                v48,
                *(const unsigned __int16 **)(v49 + 32)) )
        {
          v12 = -2147024809;
LABEL_73:
          v51 = ATL::CAtlStringMgr::GetInstance();
          if ( v51 )
          {
            _mm_lfence();
            v43 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v51 + 24LL))(v51);
            v44 = L"Could not set public key token for binding redirect";
            goto LABEL_66;
          }
LABEL_222:
          ATL::AtlThrowImpl(-2147467259);
        }
        String1 = 0;
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &String1,
          v50);
        v52 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::MakeLower(&String1);
        ATL::CSimpleStringT<unsigned short,0>::operator=(v145, v52);
        v53 = String1 - 12;
        if ( _InterlockedDecrement((volatile signed __int32 *)String1 - 2) <= 0 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v53 + 8LL))(*(_QWORD *)v53);
        }
        v54 = *(_QWORD *)(*((_QWORD *)this + 22) + 40LL);
        if ( !v54 )
        {
          v12 = -2147467261;
          v55 = ATL::CAtlStringMgr::GetInstance();
          if ( v55 )
          {
            _mm_lfence();
            v43 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v55 + 24LL))(v55);
            v44 = L"Could not set culture for binding redirect";
            goto LABEL_66;
          }
          goto LABEL_222;
        }
        v56 = -1;
        do
          ++v56;
        while ( *(_WORD *)(v54 + 2 * v56) );
        ATL::CSimpleStringT<unsigned short,0>::SetString(v146, v54);
        v57 = ATL::CAtlStringMgr::GetInstance();
        if ( !v57 )
          goto LABEL_222;
        v118 = (unsigned __int16 *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v57 + 24LL))(v57)
                                  + 24);
        v58 = ATL::CAtlStringMgr::GetInstance();
        if ( !v58 )
          goto LABEL_222;
        v59 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v58 + 24LL))(v58);
        v126 = -1;
        v125 = -1;
        v60 = (wchar_t *)(v59 + 24);
        Str = (wchar_t *)-1LL;
        String1 = (wchar_t *)(v59 + 24);
        v62 = Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeSAXEventsHandler::GetAttributeValue(
                v61,
                a8,
                L"newVersion",
                &v118);
        v63 = v118;
        v12 = v62;
        if ( v62 < 0 )
        {
          v64 = ATL::CAtlStringMgr::GetInstance();
          if ( !v64 )
            goto LABEL_222;
          _mm_lfence();
          v65 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v64 + 24LL))(v64);
          v66 = L"Could not retrieve attribute value for new version";
LABEL_90:
          v117 = (unsigned __int16 *)(v65 + 24);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
            &v117,
            L"%s: %s",
            v66,
            v142[0]);
          v69 = v117;
          CLogger::LogError(v117, v12, 0);
          if ( _InterlockedDecrement((volatile signed __int32 *)v69 - 2) <= 0 )
          {
            _mm_lfence();
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v69 - 3) + 8LL))(*((_QWORD *)v69 - 3));
          }
          goto LABEL_163;
        }
        v12 = Microsoft::VisualStudio::PkgDef::BindingRedirects::CVersion::Parse(
                v118,
                (struct Microsoft::VisualStudio::PkgDef::BindingRedirects::CVersion *)&Str);
        if ( v12 < 0 )
        {
          v68 = ATL::CAtlStringMgr::GetInstance();
          if ( !v68 )
            goto LABEL_222;
          _mm_lfence();
          v65 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v68 + 24LL))(v68);
          v66 = L"Could not parse new version from binding redirect";
          goto LABEL_90;
        }
        v149 = v126;
        v148 = v125;
        v147 = Str;
        _mm_lfence();
        v12 = Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeSAXEventsHandler::GetAttributeValue(
                v67,
                v128,
                L"oldVersion",
                &String1);
        if ( v12 < 0 )
        {
          _mm_lfence();
          v117 = (unsigned __int16 *)v142;
          lambda_6dbbf39a89cf1e629d1f0c6cb070f089_::operator()(&v117, (unsigned int)v12);
          v60 = String1;
LABEL_163:
          if ( _InterlockedDecrement((volatile signed __int32 *)v60 - 2) <= 0 )
          {
            _mm_lfence();
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v60 - 3) + 8LL))(*((_QWORD *)v60 - 3));
          }
          v46 = (volatile signed __int32 *)(v63 - 12);
          goto LABEL_166;
        }
        v60 = String1;
        if ( !String1 )
        {
          v12 = -2147467261;
LABEL_162:
          _mm_lfence();
          v117 = (unsigned __int16 *)v142;
          lambda_dd836415e530998cb32852f5c6ac647a_::operator()(&v117, (unsigned int)v12);
          goto LABEL_163;
        }
        Str = 0;
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &Str,
          String1);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Remove(
          &Str,
          32);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Remove(&Str, 9);
        v70 = Str;
        if ( *((int *)Str - 4) > 0 )
        {
          v71 = wcschr_0(Str, 0x2Du);
          v70 = Str;
          if ( v71 )
          {
            if ( (unsigned int)(v71 - Str) != -1 )
            {
              v119 = 0;
              v118 = 0;
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
                &Str,
                &v118,
                L"-",
                &v119);
              if ( *((int *)v118 - 4) <= 0 || v119 == -1 )
              {
                v80 = (volatile signed __int32 *)(v118 - 12);
              }
              else
              {
                String1 = 0;
                ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
                  &Str,
                  &String1,
                  L"-",
                  &v119);
                if ( *((int *)String1 - 4) > 0 && v119 != -1 )
                {
                  v137 = -1;
                  v136 = -1;
                  v135 = -1;
                  v134 = -1;
                  v12 = Microsoft::VisualStudio::PkgDef::BindingRedirects::CVersion::Parse(
                          v118,
                          (struct Microsoft::VisualStudio::PkgDef::BindingRedirects::CVersion *)&v134);
                  if ( v12 >= 0 )
                  {
                    v123 = -1;
                    v122 = -1;
                    v121 = -1;
                    v120 = -1;
                    v12 = Microsoft::VisualStudio::PkgDef::BindingRedirects::CVersion::Parse(
                            String1,
                            (struct Microsoft::VisualStudio::PkgDef::BindingRedirects::CVersion *)&v120);
                    if ( v12 >= 0 )
                    {
                      v75 = v137;
                      if ( v137 >= 0 )
                      {
                        v119 = v136;
                        if ( v136 >= 0 )
                        {
                          v76 = v135;
                          if ( v135 >= 0 )
                          {
                            v129 = v134;
                            if ( v134 >= 0 )
                            {
                              v130 = v123;
                              if ( v123 >= 0 )
                              {
                                v131 = v122;
                                if ( v122 >= 0 )
                                {
                                  v132 = v121;
                                  if ( v121 >= 0 )
                                  {
                                    v133 = v120;
                                    if ( v120 >= 0
                                      && v123 >= v137
                                      && (v123 > v137
                                       || v122 >= v136 && (v122 > v136 || v121 >= v135 && (v121 > v135 || v120 >= v134))) )
                                    {
                                      v77 = String1 - 12;
                                      if ( _InterlockedExchangeAdd((volatile signed __int32 *)String1 - 2, 0xFFFFFFFF) <= 1 )
                                      {
                                        _mm_lfence();
                                        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v77 + 8LL))(*(_QWORD *)v77);
                                      }
                                      v78 = v118 - 12;
                                      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v118 - 2, 0xFFFFFFFF) <= 1 )
                                      {
                                        _mm_lfence();
                                        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v78 + 8LL))(*(_QWORD *)v78);
                                      }
                                      goto LABEL_147;
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                      v12 = -2147024809;
                    }
                  }
                  v72 = String1 - 12;
                  if ( _InterlockedDecrement((volatile signed __int32 *)String1 - 2) <= 0 )
                  {
                    _mm_lfence();
                    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v72 + 8LL))(*(_QWORD *)v72);
                  }
                  v73 = v118 - 12;
                  if ( _InterlockedDecrement((volatile signed __int32 *)v118 - 2) <= 0 )
                  {
                    _mm_lfence();
                    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v73 + 8LL))(*(_QWORD *)v73);
                  }
                  goto LABEL_108;
                }
                v79 = String1 - 12;
                if ( _InterlockedDecrement((volatile signed __int32 *)String1 - 2) <= 0 )
                {
                  _mm_lfence();
                  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v79 + 8LL))(*(_QWORD *)v79);
                }
                v80 = (volatile signed __int32 *)(v118 - 12);
              }
              if ( _InterlockedDecrement(v80 + 4) <= 0 )
              {
                _mm_lfence();
                (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v80 + 8LL))(*(_QWORD *)v80);
              }
              v81 = Str - 12;
              if ( _InterlockedDecrement((volatile signed __int32 *)Str - 2) <= 0 )
              {
                _mm_lfence();
                (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v81 + 8LL))(*(_QWORD *)v81);
              }
              v12 = -2147024809;
              goto LABEL_162;
            }
          }
        }
        v123 = -1;
        v122 = -1;
        v121 = -1;
        v120 = -1;
        v12 = Microsoft::VisualStudio::PkgDef::BindingRedirects::CVersion::Parse(
                v70,
                (struct Microsoft::VisualStudio::PkgDef::BindingRedirects::CVersion *)&v120);
        if ( v12 >= 0 )
        {
          v75 = v123;
          if ( v123 >= 0 )
          {
            v119 = v122;
            if ( v122 >= 0 )
            {
              v76 = v121;
              if ( v121 >= 0 )
              {
                v129 = v120;
                if ( v120 >= 0 )
                {
                  v130 = v123;
                  v131 = v122;
                  v132 = v121;
                  v133 = v120;
LABEL_147:
                  v82 = Str - 12;
                  if ( _InterlockedExchangeAdd((volatile signed __int32 *)Str - 2, 0xFFFFFFFF) <= 1 )
                  {
                    _mm_lfence();
                    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v82 + 8LL))(*(_QWORD *)v82);
                  }
                  v12 = 0;
                  v152 = v119;
                  v150 = v129;
                  v157 = v130;
                  v156 = v131;
                  v155 = v132;
                  v153 = v75;
                  v154 = v133;
                  v151 = v76;
                  v83 = (Microsoft::VisualStudio::PkgDef::BindingRedirects::CBindingRedirect *)operator new(0x70u);
                  v84 = v83;
                  if ( v83 )
                  {
                    memset_0(v83, 0, 0x70u);
                    v85 = Microsoft::VisualStudio::PkgDef::BindingRedirects::CBindingRedirect::CBindingRedirect(
                            v84,
                            (const struct Microsoft::VisualStudio::PkgDef::BindingRedirects::CBindingRedirect *)v143);
                  }
                  else
                  {
                    v85 = 0;
                  }
                  v86 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 23);
                  *((_QWORD *)this + 23) = v85;
                  if ( v86 )
                    (**v86)(v86, 1);
                  if ( _InterlockedDecrement((volatile signed __int32 *)v60 - 2) <= 0 )
                  {
                    _mm_lfence();
                    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v60 - 3) + 8LL))(*((_QWORD *)v60 - 3));
                  }
                  if ( _InterlockedDecrement((volatile signed __int32 *)v63 - 2) <= 0 )
                  {
                    _mm_lfence();
                    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v63 - 3) + 8LL))(*((_QWORD *)v63 - 3));
                  }
                  v87 = v142[0] - 12;
                  if ( _InterlockedDecrement((volatile signed __int32 *)v142[0] - 2) <= 0 )
                  {
                    _mm_lfence();
                    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v87 + 8LL))(*(_QWORD *)v87);
                  }
LABEL_48:
                  Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase::~CCodeBase((Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase *)v143);
LABEL_49:
                  v11 = v127;
                  v8 = v117;
                  v9 = v128;
                  goto LABEL_50;
                }
              }
            }
          }
          v12 = -2147024809;
          v74 = (volatile signed __int32 *)(Str - 12);
LABEL_109:
          if ( _InterlockedDecrement(v74 + 4) <= 0 )
          {
            _mm_lfence();
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v74 + 8LL))(*(_QWORD *)v74);
          }
          goto LABEL_162;
        }
LABEL_108:
        v74 = (volatile signed __int32 *)(Str - 12);
        goto LABEL_109;
      }
      if ( *((_BYTE *)this + 192) )
      {
        if ( _wcsicmp(v14, L"codeBase") )
        {
LABEL_50:
          if ( *((_BYTE *)this + 192) )
            goto LABEL_217;
          goto LABEL_51;
        }
        if ( !*((_QWORD *)this + 22) )
        {
          v89 = (Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase *)operator new(0x50u);
          v90 = v89;
          if ( v89 )
          {
            memset_0(v89, 0, 0x50u);
            v91 = Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase::CCodeBase(v90);
          }
          else
          {
            v91 = 0;
          }
          v92 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 22);
          *((_QWORD *)this + 22) = v91;
          if ( v92 )
            (**v92)(v92, 1);
        }
        v93 = ATL::CAtlStringMgr::GetInstance();
        if ( !v93 )
          goto LABEL_220;
        v94 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v93 + 24LL))(v93);
        v95 = *((_QWORD *)this + 22);
        String1 = (wchar_t *)(v94 + 24);
        (*(void (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v95 + 16LL))(v95, &String1);
        v96 = ATL::CAtlStringMgr::GetInstance();
        if ( !v96 )
          goto LABEL_220;
        v142[0] = (unsigned __int16 *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v96 + 24LL))(v96)
                                     + 24);
        v97 = ATL::CAtlStringMgr::GetInstance();
        if ( !v97 )
          goto LABEL_220;
        v98 = (unsigned __int16 *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v97 + 24LL))(v97)
                                 + 24);
        v123 = -1;
        v122 = -1;
        v121 = -1;
        v120 = -1;
        v118 = v98;
        v99 = ATL::CAtlStringMgr::GetInstance();
        if ( !v99 )
          goto LABEL_220;
        v100 = (volatile signed __int32 *)(*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v99 + 24LL))(v99);
        v102 = Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeSAXEventsHandler::GetAttributeValue(
                 v101,
                 a8,
                 L"version",
                 v142);
        v103 = v142[0];
        v12 = v102;
        if ( v102 < 0 )
        {
          v104 = ATL::CAtlStringMgr::GetInstance();
          if ( v104 )
          {
            _mm_lfence();
            v105 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v104 + 24LL))(v104);
            v106 = L"Could not retrieve attribute value for new version";
            goto LABEL_197;
          }
LABEL_220:
          ATL::AtlThrowImpl(-2147467259);
        }
        v12 = Microsoft::VisualStudio::PkgDef::BindingRedirects::CVersion::Parse(
                v142[0],
                (struct Microsoft::VisualStudio::PkgDef::BindingRedirects::CVersion *)&v120);
        if ( v12 >= 0 )
        {
          v108 = (_DWORD *)*((_QWORD *)this + 22);
          v108[17] = v123;
          v108[16] = v122;
          v108[15] = v121;
          v108[14] = v120;
          _mm_lfence();
          v12 = Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeSAXEventsHandler::GetAttributeValue(
                  v108,
                  v128,
                  L"href",
                  &v118);
          if ( v12 < 0 )
          {
            v109 = ATL::CAtlStringMgr::GetInstance();
            if ( v109 )
            {
              _mm_lfence();
              v117 = (unsigned __int16 *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v109 + 24LL))(v109)
                                        + 24);
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
                &v117,
                L"%s: %s",
                L"Could not retrieve attribute value for file path",
                String1);
              v110 = v117;
              CLogger::LogError(v117, v12, 0);
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)v110 - 2, 0xFFFFFFFF) <= 1 )
              {
                _mm_lfence();
                (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v110 - 3) + 8LL))(*((_QWORD *)v110 - 3));
              }
              v98 = v118;
              goto LABEL_199;
            }
            goto LABEL_220;
          }
          v98 = v118;
          if ( v118 )
          {
            v114 = -1;
            do
              ++v114;
            while ( v118[v114] );
            ATL::CSimpleStringT<unsigned short,0>::SetString(*((_QWORD *)this + 22) + 48LL, v118);
            v12 = 0;
            if ( _InterlockedExchangeAdd(v100 + 4, 0xFFFFFFFF) <= 1 )
            {
              _mm_lfence();
              (*(void (__fastcall **)(_QWORD, volatile signed __int32 *))(**(_QWORD **)v100 + 8LL))(
                *(_QWORD *)v100,
                v100);
            }
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v98 - 2, 0xFFFFFFFF) <= 1 )
            {
              _mm_lfence();
              (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v98 - 3) + 8LL))(*((_QWORD *)v98 - 3));
            }
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v103 - 2, 0xFFFFFFFF) <= 1 )
            {
              _mm_lfence();
              (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v103 - 3) + 8LL))(*((_QWORD *)v103 - 3));
            }
            v115 = String1 - 12;
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)String1 - 2, 0xFFFFFFFF) <= 1 )
            {
              _mm_lfence();
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v115 + 8LL))(*(_QWORD *)v115);
            }
            goto LABEL_49;
          }
          v12 = -2147467261;
          v111 = ATL::CAtlStringMgr::GetInstance();
          if ( !v111 )
            goto LABEL_220;
          _mm_lfence();
          v105 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v111 + 24LL))(v111);
          v106 = L"Could not set file path for code base";
        }
        else
        {
          v107 = ATL::CAtlStringMgr::GetInstance();
          if ( !v107 )
            goto LABEL_220;
          _mm_lfence();
          v105 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v107 + 24LL))(v107);
          v106 = L"Could not parse version from code base";
        }
LABEL_197:
        v117 = (unsigned __int16 *)(v105 + 24);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          &v117,
          L"%s: %s",
          v106,
          String1);
        v112 = v117;
        CLogger::LogError(v117, v12, 0);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v112 - 2, 0xFFFFFFFF) <= 1 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v112 - 3) + 8LL))(*((_QWORD *)v112 - 3));
        }
LABEL_199:
        if ( _InterlockedExchangeAdd(v100 + 4, 0xFFFFFFFF) <= 1 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD, volatile signed __int32 *))(**(_QWORD **)v100 + 8LL))(*(_QWORD *)v100, v100);
        }
        if ( _InterlockedDecrement((volatile signed __int32 *)v98 - 2) <= 0 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v98 - 3) + 8LL))(*((_QWORD *)v98 - 3));
        }
        if ( _InterlockedDecrement((volatile signed __int32 *)v103 - 2) <= 0 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v103 - 3) + 8LL))(*((_QWORD *)v103 - 3));
        }
        v113 = String1 - 12;
        if ( _InterlockedDecrement((volatile signed __int32 *)String1 - 2) <= 0 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v113 + 8LL))(*(_QWORD *)v113);
        }
        goto LABEL_52;
      }
    }
  }
LABEL_51:
  v12 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, _QWORD, unsigned __int16 *, unsigned int, const unsigned __int16 *, int, struct ISAXAttributes *))(**((_QWORD **)this + 21) + 64LL))(
          *((_QWORD *)this + 21),
          v140,
          v138,
          v8,
          v11,
          v139,
          a7,
          v9);
  if ( v12 < 0 )
    goto LABEL_52;
LABEL_217:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v14 - 2, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v14 - 3) + 8LL))(*((_QWORD *)v14 - 3));
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140053dc0  push    rbp
0x140053dc2  push    rbx
0x140053dc3  push    rsi
0x140053dc4  push    rdi
0x140053dc5  push    r12
0x140053dc7  push    r13
0x140053dc9  push    r14
0x140053dcb  push    r15
0x140053dcd  lea     rbp, [rsp-68h]
0x140053dd2  sub     rsp, 168h
0x140053dd9  mov     rax, cs:__security_cookie
0x140053de0  xor     rax, rsp
0x140053de3  mov     [rbp+0A0h+var_50], rax
0x140053de7  mov     rax, [rbp+0A0h+arg_28]
0x140053dee  xor     ebx, ebx
0x140053df0  mov     rdi, r9
0x140053df3  mov     rsi, [rbp+0A0h+arg_38]
0x140053dfa  mov     r13, rcx
0x140053dfd  mov     r12d, [rbp+0A0h+arg_20]
0x140053e04  mov     r15d, ebx
0x140053e07  mov     [rsp+1A0h+var_160], r9
0x140053e0c  mov     [rbp+0A0h+var_F0], r8d
0x140053e10  mov     [rbp+0A0h+var_E0], rdx
0x140053e14  mov     [rsp+1A0h+var_128], r12d
0x140053e19  mov     [rbp+0A0h+var_E8], rax
0x140053e1d  mov     [rbp+0A0h+var_120], rsi
0x140053e21  cmp     [rcx+0A8h], rbx
0x140053e28  jz      loc_140054F66
0x140053e2e  mov     [rbp+0A0h+String1], rbx
0x140053e32  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x140053e37  mov     r9, rax
0x140053e3a  lea     rcx, [rbp+0A0h+String1]
0x140053e3e  mov     r8d, r12d
0x140053e41  mov     rdx, rdi
0x140053e44  call    ??0?$CSimpleStringT@G$0A@@ATL@@QEAA@PEBGHPEAUIAtlStringMgr@1@@Z; ATL::CSimpleStringT<ushort,0>::CSimpleStringT<ushort,0>(ushort const *,int,ATL::IAtlStringMgr *)
0x140053e49  mov     r14, [rbp+0A0h+String1]
0x140053e4d  lea     rdx, aDependentassem; "dependentAssembly"
0x140053e54  mov     rcx, r14; String1
0x140053e57  call    cs:__imp__wcsicmp
0x140053e5d  test    eax, eax
0x140053e5f  jnz     short loc_140053E6E
0x140053e61  mov     byte ptr [r13+0C0h], 1
0x140053e69  jmp     loc_140054193
0x140053e6e  cmp     [r13+0C0h], bl
0x140053e75  jz      loc_1400541A0
0x140053e7b  lea     rdx, aAssemblyidenti; "assemblyIdentity"
0x140053e82  mov     rcx, r14; String1
0x140053e85  call    cs:__imp__wcsicmp
0x140053e8b  test    eax, eax
0x140053e8d  jnz     loc_14005420E
0x140053e93  lea     r12d, [rax+50h]
0x140053e97  xor     edx, edx; Val
0x140053e99  mov     r8d, r12d; Size
0x140053e9c  lea     rcx, [rbp+0A0h+var_C0]; void *
0x140053ea0  call    memset_0
0x140053ea5  lea     rcx, [rbp+0A0h+var_C0]; this
0x140053ea9  call    ??0CCodeBase@BindingRedirects@PkgDef@VisualStudio@Microsoft@@QEAA@XZ; Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase::CCodeBase(void)
0x140053eae  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x140053eb3  test    rax, rax
0x140053eb6  jz      loc_140054F94
0x140053ebc  mov     rdx, [rax]
0x140053ebf  mov     rcx, rax
0x140053ec2  call    qword ptr [rdx+18h]
0x140053ec5  add     rax, 18h
0x140053ec9  mov     [rbp+0A0h+String1], rax
0x140053ecd  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x140053ed2  test    rax, rax
0x140053ed5  jz      loc_140054F94
0x140053edb  mov     rdx, [rax]
0x140053ede  mov     rcx, rax
0x140053ee1  call    qword ptr [rdx+18h]
0x140053ee4  lea     rbx, [rax+18h]
0x140053ee8  mov     [rsp+1A0h+var_158], rbx
0x140053eed  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x140053ef2  test    rax, rax
0x140053ef5  jz      loc_140054F94
0x140053efb  mov     rdx, [rax]
0x140053efe  mov     rcx, rax
0x140053f01  call    qword ptr [rdx+18h]
0x140053f04  lea     r9, [rbp+0A0h+String1]
0x140053f08  mov     rdx, rsi
0x140053f0b  lea     r8, aName; "name"
0x140053f12  lea     rdi, [rax+18h]
0x140053f16  mov     [rbp+0A0h+var_D0], rdi
0x140053f1a  call    ?GetAttributeValue@CMergeSAXEventsHandler@BindingRedirects@PkgDef@VisualStudio@Microsoft@@AEBAJPEAUISAXAttributes@@QEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeSAXEventsHandler::GetAttributeValue(ISAXAttributes *,ushort const * const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x140053f1f  mov     rsi, [rbp+0A0h+String1]
0x140053f23  xor     edx, edx
0x140053f25  mov     r15d, eax
0x140053f28  test    eax, eax
0x140053f2a  jns     short loc_140053F38
0x140053f2c  lea     rcx, aCouldnTFindNam; "Couldn't find name for assembly identit"...
0x140053f33  jmp     loc_140054039
0x140053f38  test    rsi, rsi
0x140053f3b  jnz     short loc_140053F49
0x140053f3d  lea     rcx, aCouldNotSetNam; "Could not set name for assembly identit"...
0x140053f44  jmp     loc_140054033
0x140053f49  or      r8, 0FFFFFFFFFFFFFFFFh
0x140053f4d  inc     r8
0x140053f50  cmp     [rsi+r8*2], dx
0x140053f55  jnz     short loc_140053F4D
0x140053f57  mov     rdx, rsi
0x140053f5a  lea     rcx, [rbp+0A0h+var_A8]
0x140053f5e  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140053f63  xor     ecx, ecx
0x140053f65  mov     r15d, ecx
0x140053f68  lfence
0x140053f6b  mov     rdx, [rbp+0A0h+var_120]
0x140053f6f  lea     r9, [rsp+1A0h+var_158]
0x140053f74  lea     r8, aPublickeytoken; "publicKeyToken"
0x140053f7b  call    ?GetAttributeValue@CMergeSAXEventsHandler@BindingRedirects@PkgDef@VisualStudio@Microsoft@@AEBAJPEAUISAXAttributes@@QEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeSAXEventsHandler::GetAttributeValue(ISAXAttributes *,ushort const * const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x140053f80  mov     rbx, [rsp+1A0h+var_158]
0x140053f85  test    eax, eax
0x140053f87  jnz     short loc_140053FFE
0x140053f89  test    rbx, rbx
0x140053f8c  jnz     short loc_140053F96
0x140053f8e  mov     r15d, 80004003h
0x140053f94  jmp     short loc_140053FAA
0x140053f96  mov     rdx, rbx; unsigned __int16 *
0x140053f99  call    ?IsValidPublicKeyToken@CCodeBase@BindingRedirects@PkgDef@VisualStudio@Microsoft@@AEBA_NPEBG@Z; Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase::IsValidPublicKeyToken(ushort const *)
0x140053f9e  xor     edx, edx
0x140053fa0  test    al, al
0x140053fa2  jnz     short loc_140053FB6
0x140053fa4  mov     r15d, 80070057h
0x140053faa  lea     rcx, aCouldNotSetPub_0; "Could not set public key token for asse"...
0x140053fb1  jmp     loc_140054039
0x140053fb6  mov     [rbp+0A0h+String1], rdx
0x140053fba  lea     rcx, [rbp+0A0h+String1]
0x140053fbe  mov     rdx, rbx
0x140053fc1  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140053fc6  lea     rcx, [rbp+0A0h+String1]
0x140053fca  call    ?MakeLower@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::MakeLower(void)
0x140053fcf  mov     rdx, rax
0x140053fd2  lea     rcx, [rbp+0A0h+var_A0]
0x140053fd6  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x140053fdb  mov     rdx, [rbp+0A0h+String1]
0x140053fdf  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140053fe3  or      eax, 0FFFFFFFFh
0x140053fe6  lock xadd [rdx+10h], eax
0x140053feb  xor     edi, edi
0x140053fed  sub     eax, 1
0x140053ff0  jg      short loc_140053FFE
0x140053ff2  lfence
0x140053ff5  mov     rcx, [rdx]
0x140053ff8  mov     rax, [rcx]
0x140053ffb  call    qword ptr [rax+8]
0x140053ffe  lfence
0x140054001  mov     rdx, [rbp+0A0h+var_120]
0x140054005  lea     r9, [rbp+0A0h+var_D0]
0x140054009  lea     r8, aCulture; "culture"
0x140054010  call    ?GetAttributeValue@CMergeSAXEventsHandler@BindingRedirects@PkgDef@VisualStudio@Microsoft@@AEBAJPEAUISAXAttributes@@QEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeSAXEventsHandler::GetAttributeValue(ISAXAttributes *,ushort const * const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x140054015  mov     rdi, [rbp+0A0h+var_D0]
0x140054019  xor     ecx, ecx
0x14005401b  test    eax, eax
0x14005401d  jnz     loc_1400540D0
0x140054023  test    rdi, rdi
0x140054026  jnz     loc_1400540B1
0x14005402c  lea     rcx, aCouldNotSetCul_0; "Could not set culture for assembly iden"...
0x140054033  mov     r15d, 80004003h
0x140054039  lfence
0x14005403c  xor     r8d, r8d; unsigned __int16 *
0x14005403f  mov     edx, r15d; int
0x140054042  call    ?LogError@CLogger@@SAXPEBGJ0@Z; CLogger::LogError(ushort const *,long,ushort const *)
0x140054047  or      r12, 0FFFFFFFFFFFFFFFFh
0x14005404b  lea     rdx, [rdi-18h]
0x14005404f  mov     eax, r12d
0x140054052  lock xadd [rdx+10h], eax
0x140054057  add     eax, r12d
0x14005405a  test    eax, eax
0x14005405c  jg      short loc_14005406A
0x14005405e  lfence
0x140054061  mov     rcx, [rdx]
0x140054064  mov     rax, [rcx]
0x140054067  call    qword ptr [rax+8]
0x14005406a  lea     rdx, [rbx-18h]
0x14005406e  mov     eax, r12d
0x140054071  lock xadd [rdx+10h], eax
0x140054076  add     eax, r12d
0x140054079  test    eax, eax
0x14005407b  jg      short loc_140054089
0x14005407d  lfence
0x140054080  mov     rcx, [rdx]
0x140054083  mov     rax, [rcx]
0x140054086  call    qword ptr [rax+8]
0x140054089  lea     rdx, [rsi-18h]
0x14005408d  mov     eax, r12d
0x140054090  lock xadd [rdx+10h], eax
0x140054095  add     eax, r12d
0x140054098  test    eax, eax
0x14005409a  jg      short loc_1400540A8
0x14005409c  lfence
0x14005409f  mov     rcx, [rdx]
0x1400540a2  mov     rax, [rcx]
0x1400540a5  call    qword ptr [rax+8]
0x1400540a8  lea     rcx, [rbp+0A0h+var_C0]
0x1400540ac  jmp     loc_140054B36
0x1400540b1  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400540b5  inc     r8
0x1400540b8  cmp     [rdi+r8*2], cx
0x1400540bd  jnz     short loc_1400540B5
0x1400540bf  mov     rdx, rdi
0x1400540c2  lea     rcx, [rbp+0A0h+var_98]
0x1400540c6  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1400540cb  xor     ecx, ecx
0x1400540cd  mov     r15d, ecx
0x1400540d0  mov     rcx, r12; Size
0x1400540d3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400540d8  xor     ecx, ecx
0x1400540da  mov     [rbp+0A0h+String1], rax
0x1400540de  test    rax, rax
0x1400540e1  jz      short loc_1400540FF
0x1400540e3  mov     r8, r12; Size
0x1400540e6  xor     edx, edx; Val
0x1400540e8  mov     rcx, rax; void *
0x1400540eb  call    memset_0
0x1400540f0  mov     rcx, [rbp+0A0h+String1]; this
0x1400540f4  lea     rdx, [rbp+0A0h+var_C0]; struct Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase *
0x1400540f8  call    ??0CCodeBase@BindingRedirects@PkgDef@VisualStudio@Microsoft@@QEAA@AEBV01234@@Z; Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase::CCodeBase(Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase const &)
0x1400540fd  jmp     short loc_140054102
0x1400540ff  mov     rax, rcx
0x140054102  mov     rcx, [r13+0B0h]
0x140054109  mov     [r13+0B0h], rax
0x140054110  test    rcx, rcx
0x140054113  jz      short loc_14005411F
0x140054115  mov     rax, [rcx]
0x140054118  mov     edx, 1
0x14005411d  call    qword ptr [rax]
0x14005411f  lea     rdx, [rdi-18h]
0x140054123  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140054127  mov     eax, edi
0x140054129  lock xadd [rdx+10h], eax
0x14005412e  add     eax, edi
0x140054130  test    eax, eax
0x140054132  jg      short loc_140054140
0x140054134  lfence
0x140054137  mov     rcx, [rdx]
0x14005413a  mov     rax, [rcx]
0x14005413d  call    qword ptr [rax+8]
0x140054140  lea     rdx, [rbx-18h]
0x140054144  mov     eax, edi
0x140054146  lock xadd [rdx+10h], eax
0x14005414b  add     eax, edi
0x14005414d  xor     ebx, ebx
0x14005414f  test    eax, eax
0x140054151  jg      short loc_14005415F
0x140054153  lfence
0x140054156  mov     rcx, [rdx]
0x140054159  mov     rax, [rcx]
0x14005415c  call    qword ptr [rax+8]
0x14005415f  lea     rdx, [rsi-18h]
0x140054163  mov     eax, edi
0x140054165  lock xadd [rdx+10h], eax
0x14005416a  add     eax, edi
0x14005416c  test    eax, eax
0x14005416e  jg      short loc_14005417C
0x140054170  lfence
0x140054173  mov     rcx, [rdx]
0x140054176  mov     rax, [rcx]
0x140054179  call    qword ptr [rax+8]
0x14005417c  lea     rcx, [rbp+0A0h+var_C0]; this
0x140054180  call    ??1CCodeBase@BindingRedirects@PkgDef@VisualStudio@Microsoft@@UEAA@XZ; Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase::~CCodeBase(void)
0x140054185  mov     r12d, [rsp+1A0h+var_128]
0x14005418a  mov     rdi, [rsp+1A0h+var_160]
0x14005418f  mov     rsi, [rbp+0A0h+var_120]
0x140054193  cmp     [r13+0C0h], bl
0x14005419a  jnz     loc_140054F49
0x1400541a0  mov     rcx, [r13+0A8h]
0x1400541a7  mov     r9, rdi
0x1400541aa  mov     eax, [rbp+0A0h+arg_30]
0x1400541b0  mov     r8d, [rbp+0A0h+var_F0]
0x1400541b4  mov     rdx, [rbp+0A0h+var_E0]
0x1400541b8  mov     r10, [rcx]
0x1400541bb  mov     [rsp+1A0h+var_168], rsi
0x1400541c0  mov     [rsp+1A0h+var_170], eax
0x1400541c4  mov     rax, [rbp+0A0h+var_E8]
0x1400541c8  mov     [rsp+1A0h+var_178], rax
0x1400541cd  mov     [rsp+1A0h+var_180], r12d
0x1400541d2  call    qword ptr [r10+40h]
0x1400541d6  mov     r15d, eax
0x1400541d9  test    eax, eax
0x1400541db  jns     loc_140054F49
0x1400541e1  or      r12, 0FFFFFFFFFFFFFFFFh
0x1400541e5  lea     rdx, [r14-18h]
0x1400541e9  mov     ecx, r12d
0x1400541ec  lock xadd [rdx+10h], ecx
0x1400541f1  add     ecx, r12d
0x1400541f4  test    ecx, ecx
0x1400541f6  jg      loc_140054F66
0x1400541fc  lfence
0x1400541ff  mov     rcx, [rdx]
0x140054202  mov     r8, [rcx]
0x140054205  call    qword ptr [r8+8]
0x140054209  jmp     loc_140054F66
0x14005420e  cmp     [r13+0C0h], bl
0x140054215  jz      short loc_1400541A0
0x140054217  lea     rdx, aBindingredirec; "bindingRedirect"
0x14005421e  mov     rcx, r14; String1
0x140054221  call    cs:__imp__wcsicmp
0x140054227  test    eax, eax
0x140054229  jnz     loc_140054B40
0x14005422f  cmp     [r13+0B0h], rbx
  ... truncated ...
```
