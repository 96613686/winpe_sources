# NetworkIncident::Repair(_GUID *,long *,uint,NDFRepairState)

- ea: `0x18000e034`
- end: `0x18000ec46`
- name: `?Repair@NetworkIncident@@QEAAJPEAU_GUID@@PEAJIW4NDFRepairState@@@Z`
- size: `3090`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001bb00`

## callees

- `0x180005350`
- `0x18000579c`
- `0x180006d58`
- `0x180006df8`
- `0x180006f04`
- `0x1800083a0`
- `0x1800083e0`
- `0x180008d38`
- `0x180009e58`
- `0x18000acb4`
- `0x18000bca0`
- `0x18000d55c`
- `0x18000d7c4`
- `0x18000e034`
- `0x180010254`
- `0x180013c3c`
- `0x18001b3a8`
- `0x1800263e0`
- `0x18002b928`
- `0x18002ba00`
- `0x18002bc48`
- `0x18002c2fc`
- `0x18002c840`
- `0x18002f010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000e261`
- `KERNEL32!EnterCriticalSection` at `0x18000e261`
- `KERNEL32!LeaveCriticalSection` at `0x18000e27d`
- `KERNEL32!LeaveCriticalSection` at `0x18000e27d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e676`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e676`

## string_xrefs

- `0x18000e7d7`: `Could not update the progress string. HRESULT: 0x%x`
- `0x18000e331`: `Got client call for repair %s from %s`
- `0x18000e43d`: `The repair was a help topic or info only. Nothing was executed.`
- `0x18000e47d`: `The repair was skipped by the user. Nothing was executed.`
- `0x18000e4a6`: `The repair was shown to the user. Waiting to get execute call.`
- `0x18000e4c6`: `The repair will be executed.`
- `0x18000e550`: `User is locally logged in, will execute repair as service.`
- `0x18000e598`: `User is not locally logged in, will execute the repair as the user.`
- `0x18000e7fc`: `Failed to retrieve repair title for progress text. Error: 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall NetworkIncident::Repair(__int64 a1, _QWORD *a2, int *a3, unsigned int a4, int a5)
{
  unsigned __int64 v5; // rbx
  ProblemInstance ***v7; // rdi
  unsigned int *v8; // r14
  struct NetworkDiagnosticsEngine *v9; // rax
  __int64 v11; // r8
  ProblemInstance **v12; // rdi
  unsigned int v13; // ecx
  unsigned int v14; // r14d
  __int64 v15; // r12
  __int64 v16; // r13
  ProblemInstance *v17; // rbx
  __int64 v18; // rcx
  _QWORD *v19; // rbx
  enum tagREPAIR_STATUS v20; // ebx
  int v21; // eax
  _QWORD *v22; // r13
  _QWORD *v23; // rdi
  _QWORD *v24; // r14
  ProblemInstance *v25; // rcx
  __int64 v26; // r9
  DiagnosticsClient **v27; // rdi
  _QWORD *v28; // rbx
  _QWORD *v29; // rax
  int v30; // r14d
  _WORD *v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // rcx
  int v34; // edi
  _QWORD *v35; // r12
  unsigned int *v36; // rax
  __int64 v37; // r8
  ProblemInstance ***v38; // r9
  __int64 v39; // rcx
  const wchar_t *v40; // r8
  ProblemInstance *v41; // rcx
  const unsigned __int16 *v42; // rbx
  int v43; // eax
  int ReplacedText; // r12d
  void *v45; // rbx
  __int64 v46; // r8
  unsigned int v47; // eax
  __int64 v48; // rdx
  volatile signed __int32 *v49; // rcx
  char *v50; // rbx
  int *v51; // rdi
  volatile signed __int32 *v52; // rbx
  __int64 v53; // r8
  _QWORD *v54; // rdi
  volatile signed __int32 *v55; // rcx
  int *v56; // r12
  volatile signed __int32 *v57; // rbx
  _QWORD *v58; // rbx
  __int64 v59; // rcx
  __int64 v60; // r8
  unsigned int v61; // edi
  ProblemInstance ***v62; // rdx
  __int64 v63; // rcx
  unsigned int *v64; // rbx
  __int64 v65; // rcx
  __int64 v66; // rax
  __int64 v67; // r8
  __int64 v68; // rdi
  _QWORD *v69; // rbx
  __int64 v70; // rcx
  ProblemInstance ***v71; // [rsp+30h] [rbp-148h]
  unsigned int *v72; // [rsp+38h] [rbp-140h]
  LPVOID pv; // [rsp+40h] [rbp-138h] BYREF
  _QWORD *v74; // [rsp+48h] [rbp-130h] BYREF
  _QWORD *v75; // [rsp+50h] [rbp-128h]
  int v76; // [rsp+58h] [rbp-120h]
  WINBOOL IsMember; // [rsp+5Ch] [rbp-11Ch] BYREF
  _QWORD *v78; // [rsp+60h] [rbp-118h]
  DiagnosticsClient **v79; // [rsp+68h] [rbp-110h] BYREF
  _QWORD *v80; // [rsp+70h] [rbp-108h] BYREF
  int v81; // [rsp+78h] [rbp-100h]
  _WORD *v82; // [rsp+80h] [rbp-F8h]
  _QWORD v83[3]; // [rsp+88h] [rbp-F0h] BYREF
  __int64 v84; // [rsp+A0h] [rbp-D8h]
  __int64 v85; // [rsp+A8h] [rbp-D0h]
  DiagnosisTextParserImpl *v86; // [rsp+B0h] [rbp-C8h] BYREF
  _QWORD *v87; // [rsp+B8h] [rbp-C0h]
  __int64 v88; // [rsp+C0h] [rbp-B8h] BYREF
  int *v89; // [rsp+C8h] [rbp-B0h]
  __int128 v90; // [rsp+D0h] [rbp-A8h] BYREF
  unsigned __int64 v91; // [rsp+E0h] [rbp-98h]
  __int64 v92; // [rsp+F0h] [rbp-88h] BYREF
  unsigned int *v93; // [rsp+F8h] [rbp-80h]
  ProblemInstance ***v94; // [rsp+100h] [rbp-78h]
  _QWORD *v95; // [rsp+108h] [rbp-70h]
  _QWORD *v96; // [rsp+110h] [rbp-68h]
  _QWORD v97[2]; // [rsp+118h] [rbp-60h] BYREF
  unsigned __int64 v98; // [rsp+128h] [rbp-50h]
  const ATL::CAtlException *v99; // [rsp+130h] [rbp-48h] BYREF

  v5 = a4;
  v89 = a3;
  v74 = a2;
  v75 = (_QWORD *)a1;
  v95 = (_QWORD *)a1;
  v97[0] = a3;
  v7 = (ProblemInstance ***)(a1 + 200);
  v71 = (ProblemInstance ***)(a1 + 200);
  *(_QWORD *)(a1 + 200) = 0;
  v8 = (unsigned int *)(a1 + 208);
  v72 = (unsigned int *)(a1 + 208);
  *(_DWORD *)(a1 + 208) = 0;
  v9 = NetworkDiagnosticsEngine::Instance();
  ++*(_DWORD *)(a1 + 108);
  v82 = (_WORD *)(a1 + 92);
  *(_WORD *)(a1 + 92) = 1;
  if ( !v9 )
    return 2147500037LL;
  v96 = (_QWORD *)(a1 + 32);
  if ( v5 >= (__int64)(*(_QWORD *)(a1 + 40) - *(_QWORD *)(a1 + 32)) >> 3 )
    return 2147942487LL;
  v94 = v7;
  v93 = v8;
  std::queue<int>::queue<int,std::deque<int>>(v83);
  v76 = 0;
  v88 = 8 * v5;
  std::deque<ProblemNode *>::push_back(v83, 8 * v5 + *(_QWORD *)(a1 + 32));
  while ( 1 )
  {
    if ( !v85 )
    {
      v22 = v75;
      v29 = v75 + 2;
      v78 = v75 + 2;
      v23 = v75 + 27;
      v75 += 27;
      v24 = v74;
      goto LABEL_35;
    }
    std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ProblemNode *>>>::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ProblemNode *>>>(
      (std::_Iterator_base12 *)&v90,
      v84,
      (const struct std::_Container_base12 *)v83);
    if ( (_QWORD)v90 )
      v11 = *(_QWORD *)v90;
    else
      v11 = 0;
    v12 = *(ProblemInstance ***)(*(_QWORD *)(*(_QWORD *)(v11 + 8) + 8 * ((v91 >> 1) & (*(_QWORD *)(v11 + 16) - 1LL)))
                               + 8 * (v91 & 1));
    if ( v85 )
    {
      if ( --v85 )
        ++v84;
      else
        v84 = 0;
    }
    *((_DWORD *)v12 + 24) = 5;
    v13 = *((_DWORD *)*v12 + 26);
    if ( v13 )
      break;
LABEL_19:
    v17 = *(ProblemInstance **)v12[8];
    while ( v17 != v12[8] )
    {
      v18 = *((_QWORD *)v17 + 2);
      v17 = *(ProblemInstance **)v17;
      v79 = (DiagnosticsClient **)v18;
      if ( *(_DWORD *)(v18 + 96) != 5 )
        std::deque<ProblemNode *>::push_back(v83, &v79);
    }
  }
  v14 = 0;
  v15 = *((_QWORD *)*v12 + 14);
  while ( 1 )
  {
    v16 = 112LL * v14;
    if ( *(_QWORD *)(v15 + v16) == *v74 && *(_QWORD *)(v15 + v16 + 8) == v74[1] )
      break;
    if ( ++v14 >= v13 )
      goto LABEL_19;
  }
  *v71 = v12;
  v19 = v75;
  EnterCriticalSection((LPCRITICAL_SECTION)(v75 + 39));
  v78 = v75 + 2;
  v75[2] = v12;
  LeaveCriticalSection((LPCRITICAL_SECTION)(v19 + 39));
  *v72 = v14;
  v20 = RS_UNREPAIRED;
  if ( a5 != 2 )
  {
    if ( (v21 = *(_DWORD *)(v15 + v16 + 40), (v21 & 0x2000000) != 0)
      || *(_DWORD *)(v15 + v16 + 56) == 3 && (v21 & 0x400000) == 0
      || (v21 & 0x20000) != 0 )
    {
      v76 = 1;
    }
  }
  v22 = v75;
  v23 = v75 + 27;
  v75 = v23;
  if ( !*v23 )
  {
    v75 = v23;
    v29 = v78;
    v24 = v74;
    goto LABEL_36;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v79);
  v24 = v74;
  v90 = *(_OWORD *)v74;
  AttributeConverter::GuidToString((unsigned int *)&v90, (__int64)&v79);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v80);
  v25 = **v71;
  v26 = *((_QWORD *)v25 + 2);
  if ( !*(_DWORD *)(v26 - 16) )
    v26 = *(_QWORD *)v25;
  v27 = v79;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
    (__int64)&v80,
    (__int64)L"Got client call for repair %s from %s",
    v79,
    v26);
  v28 = v80;
  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD *, _QWORD))(*(_QWORD *)*v75 + 112LL))(
    *v75,
    0,
    v80,
    *((_QWORD *)**v71 + 5));
  ATL::CStringData::Release((ATL::CStringData *)(v28 - 3));
  ATL::CStringData::Release((ATL::CStringData *)(v27 - 3));
  v29 = v78;
  v23 = v75;
LABEL_35:
  v20 = RS_UNREPAIRED;
LABEL_36:
  v80 = v29;
  v87 = v23;
  if ( *v71 )
  {
    v31 = v82;
    *(_QWORD *)&v90 = v82;
    if ( *(_DWORD *)(*v29 + 32LL) != 6 )
    {
      v32 = v22[15];
      if ( v32 )
      {
        if ( !a5 )
        {
          (*(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v32 + 80LL))(v32, v24);
          v31 = v82;
        }
      }
    }
    v33 = *v23;
    if ( v76 )
    {
      *v31 = 11;
      (*(void (__fastcall **)(__int64, __int64, const wchar_t *))(*(_QWORD *)v33 + 96LL))(
        v33,
        2,
        L"The repair was a help topic or info only. Nothing was executed.");
      v20 = RS_REPAIRED;
      v30 = 0;
      if ( a5 == 2 )
        goto LABEL_119;
      goto LABEL_114;
    }
    v30 = 0;
    if ( a5 == 1 )
    {
      v34 = 12;
      *v31 = 12;
      (*(void (__fastcall **)(__int64, __int64, const wchar_t *))(*(_QWORD *)v33 + 96LL))(
        v33,
        2,
        L"The repair was skipped by the user. Nothing was executed.");
LABEL_115:
      if ( v20 != RS_REPAIRED )
        v34 = 10;
      *(_DWORD *)(*v78 + 32LL) = v34;
      if ( a5 != 1 )
      {
        v61 = 1;
        v62 = v71;
        if ( *((int *)**v71 + 61) >= 0 )
        {
          if ( v20 == RS_REPAIRED )
          {
            v30 = 0;
            v61 = (v76 != 0) + 3;
          }
          else if ( v30 >= 0 )
          {
            v30 = -2147467259;
          }
        }
        else
        {
          v30 = *((_DWORD *)**v71 + 61);
        }
        goto LABEL_127;
      }
      v61 = 6;
LABEL_120:
      v62 = v71;
LABEL_127:
      v63 = v22[15];
      v64 = v72;
      if ( v63 )
        (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v63 + 208LL))(
          v63,
          *((_QWORD *)**v62 + 14) + 112LL * *v72,
          *((unsigned int *)**v62 + 54),
          v61);
      if ( *((_DWORD *)v22 + 6) == 13 )
      {
        v30 = -2147467260;
      }
      else
      {
        if ( v30 < 0 || v61 - 6 <= 1 )
        {
          v65 = v85;
          v66 = v84;
          while ( v65 )
          {
            if ( --v65 )
              ++v66;
            else
              v66 = 0;
            v84 = v66;
          }
          v85 = 0;
          std::deque<ProblemNode *>::push_back(v83, *v96 + v88);
          while ( v85 )
          {
            std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ProblemNode *>>>::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ProblemNode *>>>(
              (std::_Iterator_base12 *)v97,
              v84,
              (const struct std::_Container_base12 *)v83);
            if ( v97[0] )
              v67 = *(_QWORD *)v97[0];
            else
              v67 = 0;
            v68 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v67 + 8) + 8 * ((*(_QWORD *)(v67 + 16) - 1LL) & (v98 >> 1)))
                            + 8 * (v98 & 1));
            if ( v85 )
            {
              if ( --v85 )
                ++v84;
              else
                v84 = 0;
            }
            *(_DWORD *)(v68 + 96) = 4;
            v69 = **(_QWORD ***)(v68 + 64);
            while ( v69 != *(_QWORD **)(v68 + 64) )
            {
              v70 = v69[2];
              v69 = (_QWORD *)*v69;
              v88 = v70;
              if ( *(_DWORD *)(v70 + 96) == 5 )
                std::deque<ProblemNode *>::push_back(v83, &v88);
            }
          }
          v64 = v72;
        }
        if ( v76 || a5 )
        {
          *v71 = 0;
          *v64 = 0;
        }
      }
      goto LABEL_156;
    }
    if ( a5 == 2 )
    {
      *v31 = 14;
      (*(void (__fastcall **)(__int64, __int64, const wchar_t *))(*(_QWORD *)v33 + 96LL))(
        v33,
        2,
        L"The repair was shown to the user. Waiting to get execute call.");
LABEL_119:
      v61 = 7;
      goto LABEL_120;
    }
    (*(void (__fastcall **)(__int64, __int64, const wchar_t *))(*(_QWORD *)v33 + 96LL))(
      v33,
      2,
      L"The repair will be executed.");
    v35 = v22 + 10;
    v79 = (DiagnosticsClient **)(v22 + 10);
    v30 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v22[10] + 56LL))(v22[10]);
    if ( v30 < 0 )
      goto LABEL_112;
    v81 = 1;
    v36 = v72;
    v37 = 112LL * *v72;
    v38 = v71;
    v39 = *((_QWORD *)**v71 + 14);
    if ( (*(_DWORD *)(v37 + v39 + 40) & 0x10000) == 0 )
    {
LABEL_65:
      IsMember = v30;
      if ( !*v35 )
      {
LABEL_101:
        v58 = v78;
LABEL_102:
        if ( (byte_180041BC1 & 4) != 0 )
          McGenEventWrite_EventWriteTransfer(v39, StartNDFRepair, v37, 1, v97);
        *(_DWORD *)(*v58 + 32LL) = 5;
        v20 = ProblemInstance::Repair(**v71, v89, *((enum tagPROBLEM_TYPE *)*v71 + 7), *v72);
        if ( (byte_180041BC1 & 4) != 0 )
          McGenEventWrite_EventWriteTransfer(v59, StopNDFRepair, v60, 1, v97);
        if ( v81 )
          (*(void (__fastcall **)(DiagnosticsClient *))(*(_QWORD *)*v79 + 64LL))(*v79);
        if ( v20 == RS_REPAIRED )
        {
          *v82 = 4;
          _InterlockedExchange((volatile __int32 *)v22 + 6, 8);
LABEL_114:
          v34 = 12;
          goto LABEL_115;
        }
        if ( v20 == RS_DEFERRED )
        {
          *(_DWORD *)(*v78 + 32LL) = 6;
          v30 = -2147483638;
          goto LABEL_156;
        }
LABEL_112:
        *v82 = 1;
        if ( *v23 )
          (*(void (__fastcall **)(_QWORD, ProblemInstance *, __int64))(*(_QWORD *)*v23 + 88LL))(
            *v23,
            **v71,
            *((_QWORD *)**v71 + 14) + 112LL * *v72);
        goto LABEL_114;
      }
      v41 = **v38;
      v42 = *(const unsigned __int16 **)(112LL * *v36 + *((_QWORD *)v41 + 14) + 24);
      try
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v74);
        DiagnosisTextParser::DiagnosisTextParser((DiagnosisTextParser *)&v86);
        v43 = DiagnosisTextParser::SetXML((DiagnosisTextParser *)&v86, v42);
        ReplacedText = v43;
        if ( v43 )
        {
          if ( v43 == 1 )
          {
            if ( v42 )
            {
              v53 = -1;
              do
                ++v53;
              while ( v42[v53] );
            }
            else
            {
              v53 = 0;
            }
            ATL::CSimpleStringT<unsigned short,0>::SetString(&v74, v42, v53);
            goto LABEL_75;
          }
        }
        else
        {
          pv = 0;
          ReplacedText = DiagnosisTextParser::GetReplacedText(&v86, (unsigned __int16 **)&pv);
          if ( ReplacedText >= 0 )
          {
            v45 = pv;
            if ( pv )
            {
              v46 = -1;
              do
                ++v46;
              while ( *((_WORD *)pv + v46) );
            }
            else
            {
              v46 = 0;
            }
            ATL::CSimpleStringT<unsigned short,0>::SetString(&v74, pv, v46);
            CoTaskMemFree(v45);
          }
        }
        if ( ReplacedText < 0 )
        {
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&pv);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
            (__int64)&pv,
            (__int64)L"Failed to retrieve repair title for progress text. Error: 0x%x",
            (unsigned int)ReplacedText);
          v50 = (char *)pv;
          (*(void (__fastcall **)(_QWORD, __int64, LPVOID))(*(_QWORD *)*v23 + 96LL))(*v23, 2, pv);
          v54 = v74;
LABEL_98:
          ATL::CStringData::Release((ATL::CStringData *)(v50 - 24));
          if ( ReplacedText < 0 )
            DiagnosticsClient::SetProgress(*v79, &dword_180033E1C);
          DiagnosisTextParser::~DiagnosisTextParser((DiagnosisTextParser *)&v86);
          ATL::CStringData::Release((ATL::CStringData *)(v54 - 3));
          v23 = v75;
          goto LABEL_159;
        }
LABEL_75:
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&pv);
        v47 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Find(&v74);
        if ( v47 == -1 )
        {
          v54 = v74;
          v55 = (volatile signed __int32 *)(v74 - 3);
          v50 = (char *)pv;
          v56 = (int *)((char *)pv - 24);
          if ( v74 - 3 != (_QWORD *)((char *)pv - 24) )
          {
            if ( v56[4] >= 0 && *(_QWORD *)v55 == *(_QWORD *)v56 )
            {
              v57 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v55);
              ATL::CStringData::Release((ATL::CStringData *)v56);
              v50 = (char *)(v57 + 6);
              pv = v50;
            }
            else
            {
              ATL::CSimpleStringT<unsigned short,0>::SetString(&pv, v74, *((unsigned int *)v74 - 4));
              v50 = (char *)pv;
            }
          }
        }
        else
        {
          v48 = *(_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Left(
                             &v74,
                             &v92,
                             v47);
          v49 = (volatile signed __int32 *)(v48 - 24);
          v50 = (char *)pv;
          v51 = (int *)((char *)pv - 24);
          if ( (_BYTE *)(v48 - 24) != (char *)pv - 24 )
          {
            if ( v51[4] >= 0 && *(_QWORD *)v49 == *(_QWORD *)v51 )
            {
              v52 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v49);
              ATL::CStringData::Release((ATL::CStringData *)v51);
              v50 = (char *)(v52 + 6);
              pv = v50;
            }
            else
            {
              ATL::CSimpleStringT<unsigned short,0>::SetString(&pv, v48, *(unsigned int *)(v48 - 16));
              v50 = (char *)pv;
            }
          }
          ATL::CStringData::Release((ATL::CStringData *)(v92 - 24));
          v54 = v74;
        }
        ReplacedText = DiagnosticsClient::SetProgress(*v79, (const unsigned __int16 *)0xC9, v50);
        if ( ReplacedText < 0 )
        {
          if ( *v75 )
            (*(void (**)(_QWORD, _QWORD, const wchar_t *, ...))(*(_QWORD *)*v75 + 104LL))(
              *v75,
              0,
              L"Could not update the progress string. HRESULT: 0x%x",
              (unsigned int)ReplacedText);
          ReplacedText = 0;
        }
        goto LABEL_98;
      }
      catch ( const ATL::CAtlException *v99 )
      {
        v30 = IsMember;
        v23 = v87;
        v72 = v93;
        v58 = v80;
        v78 = v80;
        v82 = (_WORD *)v90;
        v71 = v94;
        v22 = v95;
        v89 = (int *)v97[0];
        goto LABEL_102;
      }
LABEL_159:
      goto LABEL_101;
    }
    IsMember = 0;
    v30 = IsPhysicallyLoggedOn(&IsMember);
    v39 = *v23;
    if ( v30 < 0 )
    {
      if ( v39 )
      {
        v40 = L"Check for physically logged on user failed. HRESULT: 0x%x";
        goto LABEL_63;
      }
    }
    else
    {
      if ( !IsMember )
      {
        if ( v39 )
          (*(void (__fastcall **)(__int64, __int64, const wchar_t *))(*(_QWORD *)v39 + 96LL))(
            v39,
            2,
            L"User is not locally logged in, will execute the repair as the user.");
        goto LABEL_64;
      }
      if ( v39 )
        (*(void (__fastcall **)(__int64, __int64, const wchar_t *))(*(_QWORD *)v39 + 96LL))(
          v39,
          2,
          L"User is locally logged in, will execute repair as service.");
      v30 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v35 + 64LL))(*v35);
      if ( v30 < 0 )
      {
        v39 = *v23;
        if ( *v23 )
        {
          v40 = L"RevertToSelf failed. HRESULT: 0x%x";
LABEL_63:
          (*(void (__fastcall **)(__int64, __int64, const wchar_t *, _QWORD))(*(_QWORD *)v39 + 104LL))(
            v39,
            2,
            v40,
            (unsigned int)v30);
          goto LABEL_64;
        }
      }
      v81 = 0;
    }
LABEL_64:
    v36 = v72;
    v38 = v71;
    goto LABEL_65;
  }
  v30 = -2147024809;
LABEL_156:
  std::deque<ProblemNode *>::~deque<ProblemNode *>((__int64)v83);
  return (unsigned int)v30;
}

```

## disassembly

```asm
0x18000e034  push    rbx
0x18000e036  push    rsi
0x18000e037  push    rdi
0x18000e038  push    r12
0x18000e03a  push    r13
0x18000e03c  push    r14
0x18000e03e  push    r15
0x18000e040  sub     rsp, 140h
0x18000e047  mov     rax, cs:__security_cookie
0x18000e04e  xor     rax, rsp
0x18000e051  mov     [rsp+178h+var_40], rax
0x18000e059  mov     ebx, r9d
0x18000e05c  mov     rax, r8
0x18000e05f  mov     [rsp+178h+var_B0], rax
0x18000e067  mov     [rsp+178h+var_130], rdx
0x18000e06c  mov     r13, rcx
0x18000e06f  mov     [rsp+178h+var_128], rcx
0x18000e074  mov     [rsp+178h+var_70], rcx
0x18000e07c  mov     [rsp+178h+var_60], rax
0x18000e084  lea     rdi, [rcx+0C8h]
0x18000e08b  mov     [rsp+178h+var_148], rdi
0x18000e090  xor     esi, esi
0x18000e092  mov     [rdi], rsi
0x18000e095  lea     r14, [rcx+0D0h]
0x18000e09c  mov     [rsp+178h+var_140], r14
0x18000e0a1  mov     [r14], esi
0x18000e0a4  call    ?Instance@NetworkDiagnosticsEngine@@SAPEAV1@XZ; NetworkDiagnosticsEngine::Instance(void)
0x18000e0a9  lea     r15d, [rsi+1]
0x18000e0ad  add     [r13+6Ch], r15d
0x18000e0b1  lea     rcx, [r13+5Ch]
0x18000e0b5  mov     [rsp+178h+var_F8], rcx
0x18000e0bd  mov     [rcx], r15w
0x18000e0c1  test    rax, rax
0x18000e0c4  jnz     short loc_18000E0D0
0x18000e0c6  mov     eax, 80004005h
0x18000e0cb  jmp     loc_18000EC23
0x18000e0d0  lea     r12, [r13+20h]
0x18000e0d4  mov     [rsp+178h+var_68], r12
0x18000e0dc  mov     rax, [r12+8]
0x18000e0e1  sub     rax, [r12]
0x18000e0e5  sar     rax, 3
0x18000e0e9  cmp     rbx, rax
0x18000e0ec  jb      short loc_18000E0F8
0x18000e0ee  mov     eax, 80070057h
0x18000e0f3  jmp     loc_18000EC23
0x18000e0f8  mov     [rsp+178h+var_78], rdi
0x18000e100  mov     [rsp+178h+var_80], r14
0x18000e108  lea     rcx, [rsp+178h+var_F0]
0x18000e110  call    ??0?$queue@HV?$deque@HV?$allocator@H@std@@@std@@@std@@QEAA@XZ; std::queue<int>::queue<int,std::deque<int>>(void)
0x18000e115  nop
0x18000e116  mov     [rsp+178h+var_120], esi
0x18000e11a  lea     rcx, ds:0[rbx*8]
0x18000e122  mov     [rsp+178h+var_B8], rcx
0x18000e12a  mov     rdx, [r12]
0x18000e12e  add     rdx, rcx
0x18000e131  lea     rcx, [rsp+178h+var_F0]
0x18000e139  call    ?push_back@?$deque@PEAVProblemNode@@V?$allocator@PEAVProblemNode@@@std@@@std@@QEAAXAEBQEAVProblemNode@@@Z; std::deque<ProblemNode *>::push_back(ProblemNode * const &)
0x18000e13e  cmp     [rsp+178h+var_D0], rsi
0x18000e146  jz      loc_18000E3A0
0x18000e14c  lea     r8, [rsp+178h+var_F0]
0x18000e154  mov     rdx, [rsp+178h+var_D8]
0x18000e15c  lea     rcx, [rsp+178h+var_A8]
0x18000e164  call    ??0?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@PEAVProblemNode@@@std@@@std@@@std@@QEAA@_KPEBU_Container_base12@1@@Z; std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ProblemNode *>>>::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ProblemNode *>>>(unsigned __int64,std::_Container_base12 const *)
0x18000e169  nop
0x18000e16a  mov     r8, qword ptr [rsp+178h+var_A8]
0x18000e172  test    r8, r8
0x18000e175  jnz     short loc_18000E17C
0x18000e177  mov     r8, rsi
0x18000e17a  jmp     short loc_18000E17F
0x18000e17c  mov     r8, [r8]
0x18000e17f  mov     rdx, [rsp+178h+var_98]
0x18000e187  mov     rcx, [r8+10h]
0x18000e18b  sub     rcx, r15
0x18000e18e  mov     rax, rdx
0x18000e191  shr     rax, 1
0x18000e194  and     rcx, rax
0x18000e197  mov     rax, [r8+8]
0x18000e19b  and     rdx, r15
0x18000e19e  mov     rax, [rax+rcx*8]
0x18000e1a2  mov     rdi, [rax+rdx*8]
0x18000e1a6  mov     rax, [rsp+178h+var_D0]
0x18000e1ae  test    rax, rax
0x18000e1b1  jz      short loc_18000E1D3
0x18000e1b3  sub     rax, 1
0x18000e1b7  mov     [rsp+178h+var_D0], rax
0x18000e1bf  jnz     short loc_18000E1CB
0x18000e1c1  mov     [rsp+178h+var_D8], rsi
0x18000e1c9  jmp     short loc_18000E1D3
0x18000e1cb  add     [rsp+178h+var_D8], r15
0x18000e1d3  mov     dword ptr [rdi+60h], 5
0x18000e1da  mov     r12, [rdi]
0x18000e1dd  mov     ecx, [r12+68h]
0x18000e1e2  test    ecx, ecx
0x18000e1e4  jz      short loc_18000E216
0x18000e1e6  mov     r14d, esi
0x18000e1e9  mov     r12, [r12+70h]
0x18000e1ee  mov     rdx, [rsp+178h+var_130]
0x18000e1f3  mov     eax, r14d
0x18000e1f6  imul    r13, rax, 70h ; 'p'
0x18000e1fa  mov     rax, [r12+r13]
0x18000e1fe  cmp     rax, [rdx]
0x18000e201  jnz     short loc_18000E20E
0x18000e203  mov     rax, [r12+r13+8]
0x18000e208  cmp     rax, [rdx+8]
0x18000e20c  jz      short loc_18000E24D
0x18000e20e  add     r14d, r15d
0x18000e211  cmp     r14d, ecx
0x18000e214  jb      short loc_18000E1F3
0x18000e216  mov     rbx, [rdi+40h]
0x18000e21a  mov     rbx, [rbx]
0x18000e21d  cmp     rbx, [rdi+40h]
0x18000e221  jz      loc_18000E13E
0x18000e227  mov     rcx, [rbx+10h]
0x18000e22b  mov     rbx, [rbx]
0x18000e22e  mov     [rsp+178h+var_110], rcx
0x18000e233  cmp     dword ptr [rcx+60h], 5
0x18000e237  jz      short loc_18000E21D
0x18000e239  lea     rdx, [rsp+178h+var_110]
0x18000e23e  lea     rcx, [rsp+178h+var_F0]
0x18000e246  call    ?push_back@?$deque@PEAVProblemNode@@V?$allocator@PEAVProblemNode@@@std@@@std@@QEAAXAEBQEAVProblemNode@@@Z; std::deque<ProblemNode *>::push_back(ProblemNode * const &)
0x18000e24b  jmp     short loc_18000E21D
0x18000e24d  mov     rax, [rsp+178h+var_148]
0x18000e252  mov     [rax], rdi
0x18000e255  mov     rbx, [rsp+178h+var_128]
0x18000e25a  lea     rcx, [rbx+138h]; lpCriticalSection
0x18000e261  call    cs:__imp_EnterCriticalSection
0x18000e267  mov     rax, rbx
0x18000e26a  add     rax, 10h
0x18000e26e  mov     [rsp+178h+var_118], rax
0x18000e273  mov     [rax], rdi
0x18000e276  lea     rcx, [rbx+138h]; lpCriticalSection
0x18000e27d  call    cs:__imp_LeaveCriticalSection
0x18000e283  mov     r9, [rsp+178h+var_140]
0x18000e288  mov     [r9], r14d
0x18000e28b  mov     ebx, 2
0x18000e290  cmp     [rsp+178h+arg_20], ebx
0x18000e297  jz      short loc_18000E2BD
0x18000e299  mov     eax, [r12+r13+28h]
0x18000e29e  bt      eax, 19h
0x18000e2a2  jb      short loc_18000E2B8
0x18000e2a4  cmp     dword ptr [r12+r13+38h], 3
0x18000e2aa  jnz     short loc_18000E2B2
0x18000e2ac  bt      eax, 16h
0x18000e2b0  jnb     short loc_18000E2B8
0x18000e2b2  bt      eax, 11h
0x18000e2b6  jnb     short loc_18000E2BD
0x18000e2b8  mov     [rsp+178h+var_120], r15d
0x18000e2bd  mov     r13, [rsp+178h+var_128]
0x18000e2c2  lea     rdi, [r13+0D8h]
0x18000e2c9  mov     [rsp+178h+var_128], rdi
0x18000e2ce  cmp     [rdi], rsi
0x18000e2d1  jz      loc_18000E38A
0x18000e2d7  lea     rcx, [rsp+178h+var_110]
0x18000e2dc  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18000e2e1  nop
0x18000e2e2  mov     r14, [rsp+178h+var_130]
0x18000e2e7  movups  xmm0, xmmword ptr [r14]
0x18000e2eb  movdqu  [rsp+178h+var_A8], xmm0
0x18000e2f4  lea     rdx, [rsp+178h+var_110]
0x18000e2f9  lea     rcx, [rsp+178h+var_A8]
0x18000e301  call    ?GuidToString@AttributeConverter@@SAXU_GUID@@PEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; AttributeConverter::GuidToString(_GUID,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x18000e306  lea     rcx, [rsp+178h+var_108]
0x18000e30b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18000e310  nop
0x18000e311  mov     rbx, [rsp+178h+var_148]
0x18000e316  mov     rax, [rbx]
0x18000e319  mov     rcx, [rax]
0x18000e31c  mov     r9, [rcx+10h]
0x18000e320  cmp     [r9-10h], esi
0x18000e324  jnz     short loc_18000E329
0x18000e326  mov     r9, [rcx]
0x18000e329  mov     rdi, [rsp+178h+var_110]
0x18000e32e  mov     r8, rdi
0x18000e331  lea     rdx, aGotClientCallF; "Got client call for repair %s from %s"
0x18000e338  lea     rcx, [rsp+178h+var_108]
0x18000e33d  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18000e342  mov     rax, [rsp+178h+var_128]
0x18000e347  mov     rcx, [rax]
0x18000e34a  mov     rdx, [rcx]
0x18000e34d  mov     rax, [rbx]
0x18000e350  mov     r9, [rax]
0x18000e353  mov     rax, [rdx+70h]
0x18000e357  mov     r9, [r9+28h]
0x18000e35b  mov     rbx, [rsp+178h+var_108]
0x18000e360  mov     r8, rbx
0x18000e363  xor     edx, edx
0x18000e365  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e36a  nop
0x18000e36b  lea     rcx, [rbx-18h]; this
0x18000e36f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000e374  nop
0x18000e375  lea     rcx, [rdi-18h]; this
0x18000e379  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000e37e  mov     rax, [rsp+178h+var_118]
0x18000e383  mov     rdi, [rsp+178h+var_128]
0x18000e388  jmp     short loc_18000E3BF
0x18000e38a  mov     [rsp+178h+var_128], rdi
0x18000e38f  mov     rax, [rsp+178h+var_118]
0x18000e394  mov     [rsp+178h+var_118], rax
0x18000e399  mov     r14, [rsp+178h+var_130]
0x18000e39e  jmp     short loc_18000E3C4
0x18000e3a0  mov     r13, [rsp+178h+var_128]
0x18000e3a5  lea     rax, [r13+10h]
0x18000e3a9  mov     [rsp+178h+var_118], rax
0x18000e3ae  lea     rdi, [r13+0D8h]
0x18000e3b5  mov     [rsp+178h+var_128], rdi
0x18000e3ba  mov     r14, [rsp+178h+var_130]
0x18000e3bf  mov     ebx, 2
0x18000e3c4  mov     [rsp+178h+var_108], rax
0x18000e3c9  mov     [rsp+178h+var_C0], rdi
0x18000e3d1  mov     rcx, [rsp+178h+var_148]
0x18000e3d6  cmp     [rcx], rsi
0x18000e3d9  jnz     short loc_18000E3E6
0x18000e3db  mov     r14d, 80070057h
0x18000e3e1  jmp     loc_18000EC13
0x18000e3e6  mov     rdx, [rsp+178h+var_F8]
0x18000e3ee  mov     qword ptr [rsp+178h+var_A8], rdx
0x18000e3f6  mov     rax, [rax]
0x18000e3f9  mov     r12d, [rsp+178h+arg_20]
0x18000e401  cmp     dword ptr [rax+20h], 6
0x18000e405  jz      short loc_18000E42C
0x18000e407  mov     rcx, [r13+78h]
0x18000e40b  test    rcx, rcx
0x18000e40e  jz      short loc_18000E42C
0x18000e410  test    r12d, r12d
0x18000e413  jnz     short loc_18000E42C
0x18000e415  mov     rax, [rcx]
0x18000e418  mov     rdx, r14
0x18000e41b  mov     rax, [rax+50h]
0x18000e41f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e424  mov     rdx, [rsp+178h+var_F8]
0x18000e42c  mov     rcx, [rdi]
0x18000e42f  cmp     [rsp+178h+var_120], esi
0x18000e433  jz      short loc_18000E46A
0x18000e435  mov     word ptr [rdx], 0Bh
0x18000e43a  mov     rax, [rcx]
0x18000e43d  lea     r8, aTheRepairWasAH; "The repair was a help topic or info onl"...
0x18000e444  mov     edx, ebx
0x18000e446  mov     rax, [rax+60h]
0x18000e44a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e44f  mov     ebx, r15d
0x18000e452  mov     r14d, esi
0x18000e455  cmp     r12d, 2
0x18000e459  mov     r12d, 4
0x18000e45f  jnz     loc_18000E9F0
0x18000e465  jmp     loc_18000EA23
0x18000e46a  mov     r14d, esi
0x18000e46d  cmp     r12d, r15d
0x18000e470  jnz     short loc_18000E499
0x18000e472  mov     edi, 0Ch
0x18000e477  mov     [rdx], di
0x18000e47a  mov     rax, [rcx]
0x18000e47d  lea     r8, aTheRepairWasSk; "The repair was skipped by the user. Not"...
0x18000e484  lea     edx, [rdi-0Ah]
0x18000e487  mov     rax, [rax+60h]
0x18000e48b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e490  lea     r12d, [rdi-8]
0x18000e494  jmp     loc_18000E9F5
0x18000e499  cmp     r12d, ebx
0x18000e49c  jnz     short loc_18000E4C3
0x18000e49e  mov     word ptr [rdx], 0Eh
0x18000e4a3  mov     rax, [rcx]
0x18000e4a6  lea     r8, aTheRepairWasSh; "The repair was shown to the user. Waiti"...
0x18000e4ad  mov     edx, ebx
0x18000e4af  mov     rax, [rax+60h]
0x18000e4b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4b8  mov     r12d, 4
0x18000e4be  jmp     loc_18000EA23
0x18000e4c3  mov     rax, [rcx]
0x18000e4c6  lea     r8, aTheRepairWillB; "The repair will be executed."
0x18000e4cd  mov     edx, ebx
0x18000e4cf  mov     rax, [rax+60h]
0x18000e4d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4d8  lea     r12, [r13+50h]
0x18000e4dc  mov     [rsp+178h+var_110], r12
0x18000e4e1  mov     rcx, [r12]
0x18000e4e5  mov     rax, [rcx]
0x18000e4e8  mov     rax, [rax+38h]
0x18000e4ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4f1  mov     r14d, eax
0x18000e4f4  test    eax, eax
0x18000e4f6  js      loc_18000E9B0
0x18000e4fc  mov     [rsp+178h+var_100], r15d
0x18000e501  mov     rax, [rsp+178h+var_140]
0x18000e506  mov     ecx, [rax]
0x18000e508  imul    r8, rcx, 70h ; 'p'
0x18000e50c  mov     r9, [rsp+178h+var_148]
0x18000e511  mov     rcx, [r9]
0x18000e514  mov     rdx, [rcx]
0x18000e517  mov     rcx, [rdx+70h]
0x18000e51b  test    dword ptr [r8+rcx+28h], 10000h
0x18000e524  jz      loc_18000E5D3
0x18000e52a  mov     [rsp+178h+IsMember], esi
0x18000e52e  lea     rcx, [rsp+178h+IsMember]; IsMember
0x18000e533  call    ?IsPhysicallyLoggedOn@@YAJPEAH@Z; IsPhysicallyLoggedOn(int *)
0x18000e538  mov     r14d, eax
0x18000e53b  mov     rcx, [rdi]
0x18000e53e  test    eax, eax
0x18000e540  js      short loc_18000E5AC
0x18000e542  cmp     [rsp+178h+IsMember], esi
  ... truncated ...
```
