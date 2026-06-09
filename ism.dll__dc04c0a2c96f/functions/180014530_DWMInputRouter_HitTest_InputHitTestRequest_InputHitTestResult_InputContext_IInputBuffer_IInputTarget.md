# DWMInputRouter::HitTest(_InputHitTestRequest *,_InputHitTestResult *,InputContext *,IInputBuffer *,IInputTarget * *)

- ea: `0x180014530`
- end: `0x1800150b1`
- name: `?HitTest@DWMInputRouter@@UEAAJPEAU_InputHitTestRequest@@PEAU_InputHitTestResult@@PEAVInputContext@@PEAUIInputBuffer@@PEAPEAUIInputTarget@@@Z`
- size: `2945`
- prototype: `__int64 __fastcall(DWMInputRouter *__hidden this, struct _InputHitTestRequest *, struct _InputHitTestResult *, struct InputContext *, struct IInputBuffer *, struct IInputTarget **)`
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180135f10`

## callees

- `0x18000dcd4`
- `0x1800108cc`
- `0x180012b74`
- `0x180013ef4`
- `0x180014530`
- `0x1800150b8`
- `0x1800150f0`
- `0x180015b50`
- `0x180016aa0`
- `0x1800170a0`
- `0x180017714`
- `0x180017888`
- `0x1800179e0`
- `0x180023080`
- `0x18003b57c`
- `0x18007c390`
- `0x18008dcac`
- `0x18008e194`
- `0x180094fc8`
- `0x1800af59c`
- `0x1800c0328`
- `0x1800f0990`
- `0x1800f0a90`
- `0x1800f0acc`
- `0x1801a0250`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180014e2d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180014e36`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180014e2d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180014e36`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180014746`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180014921`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180014746`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180014921`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180014e60`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180014e60`
- `CoreMessaging!CoreUICreate` at `0x180014f66`
- `CoreMessaging!CoreUICreate` at `0x180014f66`
- `win32u!NtCloseCompositionInputSink` at `0x180014d51`
- `win32u!NtCloseCompositionInputSink` at `0x180014d51`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall DWMInputRouter::HitTest(
        DWMInputRouter *this,
        struct _InputHitTestRequest *a2,
        struct _InputHitTestResult *a3,
        struct InputContext *a4,
        struct IInputBuffer *a5,
        struct IInputTarget **a6)
{
  struct _InputHitTestRequest *v7; // r14
  int v9; // r13d
  struct IInputSiteHierarchyManager *v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rcx
  int v13; // esi
  struct InputContext **v14; // rbx
  __int128 v15; // xmm6
  __int128 v16; // xmm7
  __int128 v17; // xmm8
  __int128 v18; // xmm9
  struct InputContext **v19; // rdi
  __int64 v20; // rcx
  int v21; // ebx
  struct InputContext *v22; // rax
  struct InputContext *v23; // rcx
  unsigned int v24; // edi
  unsigned int v25; // r13d
  int v26; // eax
  int v27; // edx
  int v28; // ecx
  struct InputContext *v29; // r13
  _QWORD *v30; // rax
  __int64 v31; // rdx
  __int64 v32; // r11
  int v33; // ebx
  unsigned int v34; // r12d
  void *v35; // r15
  struct InputContext **v36; // r14
  struct InputContext **v37; // rbx
  struct InputContext *v38; // rdi
  struct InputContext *j; // rsi
  __int64 v40; // rcx
  struct InputContext *v41; // rcx
  void *v42; // rdx
  struct InputContext *v43; // rdx
  __int64 v45; // rdx
  __int64 v46; // rax
  __int64 v47; // rdi
  __int64 v48; // rax
  __int64 v49; // r14
  int (__fastcall *v50)(_QWORD, _QWORD, _QWORD); // rax
  int v51; // eax
  int v52; // eax
  HANDLE v53; // rax
  struct InputContext *v54; // r13
  struct InputContext *v55; // rax
  __int64 v56; // rdx
  __int64 v57; // rbx
  __int64 v58; // r13
  struct InputContext ****v59; // rdi
  struct InputContext **v60; // rax
  struct InputContext *v61; // rdi
  struct InputContext *v62; // rax
  HANDLE CurrentProcess; // rbx
  HANDLE v64; // rax
  const char *v65; // r9
  char *InitialTargetFromHitTestResult; // rax
  __int64 v67; // rcx
  __int64 v68; // rdx
  __int64 v69; // rcx
  int v70; // eax
  struct InputSystemServerConnection **v71; // rax
  struct InputSystemServerConnection *v72; // rcx
  Microsoft::Bamo::BaseBamoConnection *v73; // rcx
  __int64 v74; // rcx
  struct IInputSiteHierarchyManager **v75; // rax
  struct IInputSiteHierarchyManager *v76; // rcx
  unsigned int v77; // ebx
  struct ViewHierarchyWithWindowManager *ViewHierarchy; // rax
  int dwDesiredAccess; // [rsp+28h] [rbp-E0h]
  __int64 v80; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v81; // [rsp+50h] [rbp-B8h]
  Microsoft::Bamo::BaseBamoConnection *v82; // [rsp+58h] [rbp-B0h] BYREF
  struct InputContext *v83; // [rsp+60h] [rbp-A8h] BYREF
  struct InputContext *v84; // [rsp+68h] [rbp-A0h] BYREF
  void *v85; // [rsp+70h] [rbp-98h] BYREF
  int (__fastcall *v86)(_QWORD, _QWORD, _QWORD); // [rsp+78h] [rbp-90h]
  struct InputContext *i; // [rsp+80h] [rbp-88h]
  struct InputContext **v88; // [rsp+88h] [rbp-80h] BYREF
  int (__fastcall ***v89)(_QWORD, _QWORD, _QWORD); // [rsp+98h] [rbp-70h]
  struct _InputHitTestRequest *v90; // [rsp+A0h] [rbp-68h]
  struct IInputTarget **v91; // [rsp+A8h] [rbp-60h]
  struct IInputBuffer *v92; // [rsp+B0h] [rbp-58h]
  char v93; // [rsp+B8h] [rbp-50h] BYREF
  int v94; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v95; // [rsp+CCh] [rbp-3Ch]
  __int128 v96; // [rsp+D4h] [rbp-34h]
  __int128 v97; // [rsp+E4h] [rbp-24h]
  __int128 v98; // [rsp+F4h] [rbp-14h]
  __int128 v99; // [rsp+104h] [rbp-4h]
  _BYTE v100[28]; // [rsp+114h] [rbp+Ch] BYREF
  int v101; // [rsp+130h] [rbp+28h]
  int v102; // [rsp+134h] [rbp+2Ch]
  __int64 v103; // [rsp+138h] [rbp+30h]
  __int128 v104; // [rsp+140h] [rbp+38h]
  char v105[8]; // [rsp+158h] [rbp+50h] BYREF
  HANDLE hSourceHandle; // [rsp+160h] [rbp+58h]
  __int128 v107; // [rsp+168h] [rbp+60h]
  __int128 v108; // [rsp+178h] [rbp+70h]
  __int128 v109; // [rsp+188h] [rbp+80h]
  __int128 v110; // [rsp+198h] [rbp+90h]
  __int64 v111; // [rsp+1A8h] [rbp+A0h]
  char v112; // [rsp+1B0h] [rbp+A8h]
  int v113; // [rsp+1B4h] [rbp+ACh]
  void *v114; // [rsp+1B8h] [rbp+B0h] BYREF
  struct InputContext **v115; // [rsp+1C0h] [rbp+B8h]
  __int64 v116; // [rsp+1C8h] [rbp+C0h]
  _DWORD v117[4]; // [rsp+1D8h] [rbp+D0h] BYREF
  __int64 v118; // [rsp+1E8h] [rbp+E0h]
  int v119; // [rsp+1F0h] [rbp+E8h]
  int v120; // [rsp+1F4h] [rbp+ECh]
  int v121; // [rsp+1F8h] [rbp+F0h]
  __int16 v122; // [rsp+1FCh] [rbp+F4h]
  __int16 v123; // [rsp+1FEh] [rbp+F6h]
  int v124; // [rsp+200h] [rbp+F8h]
  __int64 v125; // [rsp+204h] [rbp+FCh]
  int v126; // [rsp+20Ch] [rbp+104h]
  __int64 v127; // [rsp+210h] [rbp+108h]
  wil::details::in1diag3 *retaddr; // [rsp+2A0h] [rbp+198h]

  v84 = a4;
  v7 = a2;
  v90 = a2;
  v85 = this;
  v92 = a5;
  v91 = a6;
  v9 = 0;
  v96 = 0;
  v97 = 0;
  v98 = 0;
  v99 = 0;
  memset(v100, 0, sizeof(v100));
  v104 = 0;
  v94 = *(_DWORD *)a2;
  v95 = *(_QWORD *)((char *)a2 + 20);
  v101 = *((_DWORD *)a2 + 16);
  v102 = 0;
  v103 = *(_QWORD *)((char *)a2 + 68);
  v10 = ISMStatics::s_inputSiteHierarchyManager;
  if ( !ISMStatics::s_inputSiteHierarchyManager )
  {
    v75 = (struct IInputSiteHierarchyManager **)InputSiteHierarchyManager::Create(&v83);
    v76 = *v75;
    *v75 = 0;
    ISMStatics::s_inputSiteHierarchyManager = v76;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v83);
    v10 = ISMStatics::s_inputSiteHierarchyManager;
  }
  if ( !ISMStatics::s_inputSystemBamoConnection )
  {
    v80 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v80);
    v70 = CoreUICreate(&v80);
    if ( v70 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x33,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\utilities\\ismstatics\\ismstatics.cpp",
        (const char *)(unsigned int)v70,
        dwDesiredAccess);
    v71 = (struct InputSystemServerConnection **)InputSystemServerConnection::Create((unsigned int)&v82);
    v72 = *v71;
    *v71 = 0;
    ISMStatics::s_inputSystemBamoConnection = v72;
    v73 = v82;
    if ( v82 )
    {
      v82 = 0;
      Microsoft::Bamo::BaseBamoConnection::Release(v73);
    }
    v74 = v80;
    if ( v80 )
    {
      v80 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
    }
  }
  v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)ISMStatics::s_inputSystemBamoConnection + 31) + 8LL)
                                           + 152LL))(*((_QWORD *)ISMStatics::s_inputSystemBamoConnection + 31) + 8LL);
  HitTestHelper::HitTestRequestWithRetry(
    &v105,
    (__int128 *)&v94,
    *((__int64 (__fastcall ****)(_QWORD, __int128 *))this + 23),
    v11,
    (__int64)v10);
  if ( v105 )
  {
    v13 = 2;
    v14 = v115;
    switch ( *(_DWORD *)v7 )
    {
      case 4:
        LODWORD(v81) = 2;
        break;
      case 2:
        LODWORD(v82) = 0;
        LODWORD(v81) = 8;
        if ( (unsigned __int8)DWMInputRouter::CheckForVirtualTouchpadFromInputSiteList(v12, v115 - 3, &v82) )
        {
          *((_DWORD *)a3 + 26) = (_DWORD)v82;
          *((_DWORD *)a3 + 25) = 0;
          v53 = hSourceHandle;
          hSourceHandle = 0;
          goto LABEL_106;
        }
        break;
      case 3:
        LODWORD(v81) = 16;
        break;
      case 5:
        LODWORD(v81) = 32;
        break;
      default:
        LODWORD(v81) = 0;
        break;
    }
    *(_QWORD *)a3 = v111;
    v15 = v107;
    *((_OWORD *)a3 + 1) = v107;
    v16 = v108;
    *((_OWORD *)a3 + 2) = v108;
    v17 = v109;
    *((_OWORD *)a3 + 3) = v109;
    v18 = v110;
    *((_OWORD *)a3 + 4) = v110;
    *((_DWORD *)a3 + 20) = v113;
    LODWORD(v82) = 0;
    v19 = v14 - 3;
    v88 = v14 - 3;
    InputSiteManager::GetInputSiteForLeafmostViewFromInputSiteList(&v80, v14 - 3);
    v20 = v80;
    if ( v80 )
    {
      if ( !*(_BYTE *)(v80 + 480) )
        std::_Throw_bad_optional_access();
      LODWORD(v82) = *LegacyInputSinkData::GetViewInstanceId((LegacyInputSinkData *)(v80 + 48));
      v20 = v80;
    }
    if ( v20 )
    {
      v80 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
    v21 = 0;
    v22 = *v19;
    v23 = v19[1];
    for ( i = v23; ; v23 = i )
    {
      v83 = v22;
      if ( v22 == v23 )
      {
        if ( !v9 )
          v9 = 1;
        if ( !v21 )
          v21 = 2;
        goto LABEL_16;
      }
      v45 = 0;
      v80 = 0;
      v46 = *(_QWORD *)v22;
      v47 = *(_QWORD *)(v46 + 488);
      v48 = *(_QWORD *)(v46 + 496);
      if ( v47 != v48 )
      {
        v49 = v48;
        while ( 1 )
        {
          v89 = *(int (__fastcall ****)(_QWORD, _QWORD, _QWORD))(v47 + 8);
          v50 = **v89;
          v86 = v50;
          if ( v45 )
          {
            v80 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
            v50 = v86;
          }
          if ( v50(v89, &GUID_4753c172_9138_4064_8603_1556e98a010f, &v80) >= 0 )
            break;
          v47 += 16;
          if ( v47 == v49 )
            break;
          v45 = v80;
        }
        v45 = v80;
        v7 = v90;
      }
      if ( v45 )
      {
        if ( !v9 )
        {
          v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v45 + 24LL))(v45);
          v45 = v80;
        }
        if ( !v21 )
        {
          v21 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v45 + 32LL))(v45);
          v45 = v80;
        }
        if ( v9 && v21 )
          break;
      }
      if ( v45 )
      {
        v80 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
      }
      v22 = (struct InputContext *)((char *)v83 + 8);
    }
    if ( v45 )
    {
      v80 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    }
LABEL_16:
    if ( v9 == 2 )
    {
      v24 = 1;
    }
    else
    {
      v24 = 0;
      if ( v9 == 3 )
        v24 = 2;
    }
    if ( v21 == 1 )
      v24 |= 4u;
    if ( !InitOnceExecuteOnce(&gInitOnce, InitEditionOnceCallback, 0, 0) )
      __fastfail(7u);
    if ( ((1LL << gdwDeviceFamily) & 0x1C000) != 0 && (v24 & 2) != 0 )
    {
      v77 = v24 & 0xFFFFFFFD;
      ViewHierarchy = ISMStatics::GetViewHierarchy();
      v25 = (unsigned int)v82;
      v24 = v24 & 0xFFFFFFFC | 1;
      if ( !ViewHelper::IsViewPartOfForegroundApplication(ViewHierarchy, (unsigned int)v82) )
        v24 = v77;
    }
    else
    {
      v25 = (unsigned int)v82;
    }
    *((_QWORD *)a3 + 11) = v25;
    *((_DWORD *)a3 + 24) = v24;
    if ( (_DWORD)v81 )
    {
      v117[3] = 0;
      v119 = 0;
      v123 = 0;
      v127 = 0;
      v26 = *(_DWORD *)v7;
      v120 = v26;
      if ( v26 == 4 )
      {
        v27 = 2;
      }
      else
      {
        v51 = v26 - 2;
        if ( v51 )
        {
          v52 = v51 - 1;
          if ( v52 )
          {
            if ( v52 == 2 )
            {
              v27 = 0x1000000;
              if ( !*((_DWORD *)v7 + 4) )
                v27 = 32;
            }
            else
            {
              v27 = 0;
            }
          }
          else
          {
            v27 = 16;
          }
        }
        else
        {
          v27 = 8;
        }
      }
      v117[0] = v27;
      v117[1] = *((_DWORD *)v7 + 8);
      v117[2] = *((_DWORD *)v7 + 10);
      v118 = *((_QWORD *)v7 + 6);
      v125 = *(_QWORD *)((char *)v7 + 20);
      v121 = *((_DWORD *)v7 + 1);
      v122 = *((_WORD *)v7 + 4);
      v28 = *((_DWORD *)v7 + 3);
      v126 = *((_DWORD *)v7 + 14);
      if ( v27 == 2 )
        v28 = 1;
      v124 = v28;
      v29 = v84;
      *((_DWORD *)v84 + 24) = v24;
      *((_QWORD *)v29 + 11) = *((_QWORD *)a3 + 11);
      if ( (char *)hSourceHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        v54 = *v88;
        v55 = v88[1];
        for ( i = v55; ; v55 = i )
        {
          v83 = v54;
          if ( v54 == v55 )
          {
            v61 = 0;
            v83 = 0;
            v62 = 0;
            goto LABEL_121;
          }
          v56 = 0;
          v80 = 0;
          v57 = *(_QWORD *)(*(_QWORD *)v54 + 488LL);
          if ( v57 != *(_QWORD *)(*(_QWORD *)v54 + 496LL) )
          {
            v58 = *(_QWORD *)(*(_QWORD *)v54 + 496LL);
            while ( 1 )
            {
              v59 = *(struct InputContext *****)(v57 + 8);
              v60 = **v59;
              v88 = v60;
              if ( v56 )
              {
                v80 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
                v60 = v88;
              }
              if ( ((int (__fastcall *)(struct InputContext ****, GUID *, __int64 *))v60)(
                     v59,
                     &GUID_8ddffe9c_458e_6d51_c227_1374408f672c,
                     &v80) >= 0 )
                break;
              v57 += 16;
              if ( v57 == v58 )
                break;
              v56 = v80;
            }
            v54 = v83;
            if ( v80 )
              break;
          }
          v54 = (struct InputContext *)((char *)v54 + 8);
        }
        v83 = *(struct InputContext **)v83;
        v61 = v83;
        wil::com_ptr_t<AsyncHRESULTPrincipal,wil::err_exception_policy>::~com_ptr_t<AsyncHRESULTPrincipal,wil::err_exception_policy>(&v83);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v80);
        v62 = v61;
LABEL_121:
        if ( v62 )
        {
          v112 = 0;
          v113 = 0;
          *((_DWORD *)a3 + 20) = 0;
        }
        CurrentProcess = GetCurrentProcess();
        v64 = GetCurrentProcess();
        if ( !DuplicateHandle(v64, hSourceHandle, CurrentProcess, (LPHANDLE)a3 + 1, 0, 0, 2u) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x645,
            (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
            v65);
        InitialTargetFromHitTestResult = (char *)DWMInputRouter::GetInitialTargetFromHitTestResult(
                                                   (_DWORD)v85,
                                                   (unsigned int)&v80,
                                                   v117[0],
                                                   (unsigned int)&v105,
                                                   0);
        v29 = v84;
        v67 = 0;
        if ( &v93 != InitialTargetFromHitTestResult )
        {
          v67 = *(_QWORD *)InitialTargetFromHitTestResult;
          *(_QWORD *)InitialTargetFromHitTestResult = 0;
        }
        v68 = *((_QWORD *)v29 + 2);
        *((_QWORD *)v29 + 2) = v67;
        if ( v68 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
        v69 = v80;
        if ( v80 )
        {
          v80 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
        }
        if ( (_DWORD)v81 != 2 && (_DWORD)v81 != 32 )
        {
          LODWORD(v82) = v124;
          std::unordered_map<unsigned long,Microsoft::WRL::ComPtr<IInputTarget>>::_Insert_or_assign<unsigned long,Microsoft::WRL::ComPtr<IInputTarget> &>(
            (char *)v29 + 24,
            &v88,
            &v82,
            (char *)v29 + 16);
        }
        if ( v61 )
          (*(void (__fastcall **)(struct InputContext *))(*(_QWORD *)v61 + 16LL))(v61);
        v18 = v110;
        v17 = v109;
        v16 = v108;
        v15 = v107;
      }
      LODWORD(v81) = 0;
      v30 = operator new(0x78u);
      *(_BYTE *)v30 = v105;
      v30[1] = hSourceHandle;
      hSourceHandle = 0;
      *((_OWORD *)v30 + 1) = v15;
      *((_OWORD *)v30 + 2) = v16;
      *((_OWORD *)v30 + 3) = v17;
      *((_OWORD *)v30 + 4) = v18;
      v30[10] = v111;
      *((_BYTE *)v30 + 88) = v112;
      *((_DWORD *)v30 + 23) = v113;
      std::vector<InputProvider>::vector<InputProvider>(v30 + 12, &v114);
      v31 = *((_QWORD *)v29 + 22);
      *((_QWORD *)v29 + 22) = v32;
      if ( v31 )
        std::default_delete<HitTestResult>::operator()();
      LODWORD(v82) = 0;
      if ( (int)ContextualProcessorManager::OnHitTest(
                  *((ContextualProcessorManager **)v85 + 32),
                  (struct HitTestInfo *)v117,
                  v29,
                  v92,
                  v91,
                  (enum ContextualProcessorState *)&v82) >= 0 )
        v33 = (int)v82;
      else
        v33 = 0;
      if ( v112 && (*(_DWORD *)v7 != 4 || (*((_BYTE *)v7 + 64) & 1) != 0) )
      {
        v13 = 3;
      }
      else
      {
        if ( !InitOnceExecuteOnce(&gInitOnce, InitEditionOnceCallback, 0, 0) )
          __fastfail(7u);
        if ( ((1LL << gdwDeviceFamily) & 0x1820) == 0 || *(_DWORD *)v7 != 4 )
        {
          v13 = 0;
          if ( v33 )
          {
            LOBYTE(v13) = v33 != 3;
            ++v13;
          }
        }
      }
      *((_DWORD *)a3 + 25) = v13;
      v34 = v81;
      goto LABEL_40;
    }
    *((_DWORD *)a3 + 25) = 0;
    v53 = hSourceHandle;
    hSourceHandle = 0;
LABEL_106:
    *((_QWORD *)a3 + 1) = v53;
    HitTestResult::~HitTestResult((HitTestResult *)&v105);
    return 0;
  }
  v34 = -2147467259;
LABEL_40:
  v35 = v114;
  if ( v114 )
  {
    v36 = v115;
    v37 = (struct InputContext **)v114;
    if ( v114 != v115 )
    {
      do
      {
        v38 = *v37;
        if ( *v37 )
        {
          for ( j = v37[1]; v38 != j; v38 = (struct InputContext *)((char *)v38 + 8) )
          {
            v40 = *(_QWORD *)v38;
            if ( *(_QWORD *)v38 )
            {
              *(_QWORD *)v38 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
            }
          }
          v41 = *v37;
          v42 = (void *)((v37[2] - *v37) & 0xFFFFFFFFFFFFFFF8uLL);
          v85 = v42;
          v84 = v41;
          if ( (unsigned __int64)v42 >= 0x1000 )
          {
            std::_Adjust_manually_vector_aligned((void **)&v84, (unsigned __int64 *)&v85);
            v42 = v85;
            v41 = v84;
          }
          operator delete(v41, (const struct std::nothrow_t *)v42);
          *v37 = 0;
          v37[1] = 0;
          v37[2] = 0;
        }
        v37 += 3;
      }
      while ( v37 != v36 );
    }
    v43 = (struct InputContext *)(8 * ((v116 - (__int64)v35) >> 3));
    v84 = v43;
    v85 = v35;
    if ( (unsigned __int64)v43 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(&v85, (unsigned __int64 *)&v84);
      v35 = v85;
      v43 = v84;
    }
    operator delete(v35, v43);
  }
  if ( (char *)hSourceHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    NtCloseCompositionInputSink(hSourceHandle);
  return v34;
}

```

## disassembly

```asm
0x180014530  mov     rax, rsp
0x180014533  mov     [rax+10h], rbx
0x180014537  push    rbp
0x180014538  push    rsi
0x180014539  push    rdi
0x18001453a  push    r12
0x18001453c  push    r13
0x18001453e  push    r14
0x180014540  push    r15
0x180014542  lea     rbp, [rax-198h]
0x180014549  sub     rsp, 260h
0x180014550  movaps  xmmword ptr [rax-48h], xmm6
0x180014554  movaps  xmmword ptr [rax-58h], xmm7
0x180014558  movaps  xmmword ptr [rax-68h], xmm8
0x18001455d  movaps  xmmword ptr [rax-78h], xmm9
0x180014562  mov     rax, cs:__security_cookie
0x180014569  xor     rax, rsp
0x18001456c  mov     [rbp+190h+var_80], rax
0x180014573  mov     [rsp+290h+var_230], r9
0x180014578  mov     r12, r8
0x18001457b  mov     r14, rdx
0x18001457e  mov     [rbp+190h+var_1F8], rdx
0x180014582  mov     rdi, rcx
0x180014585  mov     [rsp+290h+var_228], rcx
0x18001458a  mov     rax, [rbp+190h+arg_20]
0x180014591  mov     [rbp+190h+var_1E8], rax
0x180014595  mov     rax, [rbp+190h+arg_28]
0x18001459c  mov     [rbp+190h+var_1F0], rax
0x1800145a0  xor     r13d, r13d
0x1800145a3  xorps   xmm0, xmm0
0x1800145a6  movups  [rbp+190h+var_1C4], xmm0
0x1800145aa  movups  [rbp+190h+var_1B4], xmm0
0x1800145ae  movups  [rbp+190h+var_1A4], xmm0
0x1800145b2  movups  [rbp+190h+var_194], xmm0
0x1800145b6  movups  xmmword ptr [rbp+190h+var_184], xmm0
0x1800145ba  movups  xmmword ptr [rbp+190h+var_184+0Ch], xmm0
0x1800145be  movups  [rbp+190h+var_158], xmm0
0x1800145c2  mov     eax, [rdx]
0x1800145c4  mov     [rbp+190h+var_1D0], eax
0x1800145c7  mov     rax, [rdx+14h]
0x1800145cb  mov     [rbp+190h+var_1CC], rax
0x1800145cf  mov     eax, [rdx+40h]
0x1800145d2  mov     [rbp+190h+var_168], eax
0x1800145d5  mov     [rbp+190h+var_164], r13d
0x1800145d9  mov     rax, [rdx+44h]
0x1800145dd  mov     [rbp+190h+var_160], rax
0x1800145e1  mov     rbx, cs:?s_inputSiteHierarchyManager@ISMStatics@@0PEAUIInputSiteHierarchyManager@@EA; IInputSiteHierarchyManager * ISMStatics::s_inputSiteHierarchyManager
0x1800145e8  test    rbx, rbx
0x1800145eb  jz      loc_180014FDE
0x1800145f1  cmp     cs:?s_inputSystemBamoConnection@ISMStatics@@0PEAVInputSystemServerConnection@@EA, r13; InputSystemServerConnection * ISMStatics::s_inputSystemBamoConnection
0x1800145f8  jz      loc_180014F52
0x1800145fe  mov     rax, cs:?s_inputSystemBamoConnection@ISMStatics@@0PEAVInputSystemServerConnection@@EA; InputSystemServerConnection * ISMStatics::s_inputSystemBamoConnection
0x180014605  mov     rcx, [rax+0F8h]
0x18001460c  add     rcx, 8
0x180014610  mov     rax, [rcx]
0x180014613  mov     rax, [rax+98h]
0x18001461a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001461f  mov     qword ptr [rsp+290h+dwDesiredAccess], rbx
0x180014624  mov     r9, rax
0x180014627  mov     r8, [rdi+0B8h]
0x18001462e  lea     rdx, [rbp+190h+var_1D0]
0x180014632  lea     rcx, [rbp+190h+var_140]
0x180014636  call    ?HitTestRequestWithRetry@HitTestHelper@@SA?AUHitTestResult@@AEBUHitTestRequest@1@PEAUIDWMInputProxy@@PEAVInputSiteManager@@PEAUIInputSiteHierarchyManager@@@Z; HitTestHelper::HitTestRequestWithRetry(HitTestHelper::HitTestRequest const &,IDWMInputProxy *,InputSiteManager *,IInputSiteHierarchyManager *)
0x18001463b  nop
0x18001463c  cmp     [rbp+190h+var_140], 0
0x180014640  jz      loc_180014B71
0x180014646  mov     eax, [r14]
0x180014649  mov     esi, 2
0x18001464e  mov     rbx, [rbp+190h+var_D8]
0x180014655  cmp     eax, 4
0x180014658  jnz     loc_180014BEE
0x18001465e  mov     dword ptr [rsp+290h+var_248], esi
0x180014662  mov     rax, [rbp+190h+var_F0]
0x180014669  mov     [r12], rax
0x18001466d  movaps  xmm6, [rbp+190h+var_130]
0x180014671  movups  xmmword ptr [r12+10h], xmm6
0x180014677  movaps  xmm7, [rbp+190h+var_120]
0x18001467b  movups  xmmword ptr [r12+20h], xmm7
0x180014681  movaps  xmm8, [rbp+190h+var_110]
0x180014689  movups  xmmword ptr [r12+30h], xmm8
0x18001468f  movaps  xmm9, [rbp+190h+var_100]
0x180014697  movups  xmmword ptr [r12+40h], xmm9
0x18001469d  mov     eax, [rbp+190h+var_E4]
0x1800146a3  mov     [r12+50h], eax
0x1800146a8  mov     dword ptr [rsp+290h+var_240], r13d
0x1800146ad  lea     rdi, [rbx-18h]
0x1800146b1  mov     [rbp+190h+var_210], rdi
0x1800146b5  mov     rdx, rdi
0x1800146b8  lea     rcx, [rsp+290h+var_250]
0x1800146bd  call    ?GetInputSiteForLeafmostViewFromInputSiteList@InputSiteManager@@SA?AV?$ComPtr@VInputSite@@@WRL@Microsoft@@AEBV?$vector@V?$ComPtr@VInputSite@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VInputSite@@@WRL@Microsoft@@@std@@@std@@@Z; InputSiteManager::GetInputSiteForLeafmostViewFromInputSiteList(std::vector<Microsoft::WRL::ComPtr<InputSite>> const &)
0x1800146c2  nop
0x1800146c3  mov     rcx, [rsp+290h+var_250]
0x1800146c8  test    rcx, rcx
0x1800146cb  jnz     loc_180014C9E
0x1800146d1  test    rcx, rcx
0x1800146d4  jz      short loc_1800146E8
0x1800146d6  mov     [rsp+290h+var_250], r13
0x1800146db  mov     rax, [rcx]
0x1800146de  mov     rax, [rax+10h]
0x1800146e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800146e7  nop
0x1800146e8  xor     ebx, ebx
0x1800146ea  mov     rax, [rdi]
0x1800146ed  mov     rcx, [rdi+8]
0x1800146f1  mov     [rsp+290h+var_218], rcx
0x1800146f6  mov     [rsp+290h+var_238], rax
0x1800146fb  mov     r15d, 1
0x180014701  cmp     rax, rcx
0x180014704  jnz     loc_180014AA4
0x18001470a  test    r13d, r13d
0x18001470d  jnz     short loc_180014712
0x18001470f  mov     r13d, r15d
0x180014712  test    ebx, ebx
0x180014714  cmovz   ebx, esi
0x180014717  cmp     r13d, 2
0x18001471b  jz      loc_180014BE6
0x180014721  xor     edi, edi
0x180014723  cmp     r13d, 3
0x180014727  cmovz   edi, esi
0x18001472a  cmp     ebx, 1
0x18001472d  jnz     short loc_180014732
0x18001472f  or      edi, 4
0x180014732  xor     r9d, r9d; Context
0x180014735  xor     r8d, r8d; Parameter
0x180014738  lea     rdx, ?InitEditionOnceCallback@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18001473f  lea     rcx, ?gInitOnce@@3T_RTL_RUN_ONCE@@A; InitOnce
0x180014746  call    cs:__imp_InitOnceExecuteOnce
0x18001474c  test    eax, eax
0x18001474e  jz      loc_180014C68
0x180014754  mov     ecx, cs:?gdwDeviceFamily@@3KA; ulong gdwDeviceFamily
0x18001475a  mov     rax, r15
0x18001475d  shl     rax, cl
0x180014760  test    rax, 1C000h
0x180014766  jnz     loc_18001500B
0x18001476c  mov     r13d, dword ptr [rsp+290h+var_240]
0x180014771  mov     eax, r13d
0x180014774  mov     [r12+58h], rax
0x180014779  mov     [r12+60h], edi
0x18001477e  cmp     dword ptr [rsp+290h+var_248], 0
0x180014783  jz      loc_180014D20
0x180014789  xor     ebx, ebx
0x18001478b  mov     [rbp+190h+var_B4], ebx
0x180014791  mov     [rbp+190h+var_A8], ebx
0x180014797  mov     [rbp+190h+var_9A], bx
0x18001479e  mov     [rbp+190h+var_88], rbx
0x1800147a5  mov     eax, [r14]
0x1800147a8  mov     [rbp+190h+var_A4], eax
0x1800147ae  cmp     eax, 4
0x1800147b1  jnz     loc_180014C08
0x1800147b7  mov     edx, esi
0x1800147b9  mov     [rbp+190h+var_C0], edx
0x1800147bf  mov     eax, [r14+20h]
0x1800147c3  mov     [rbp+190h+var_BC], eax
0x1800147c9  mov     eax, [r14+28h]
0x1800147cd  mov     [rbp+190h+var_B8], eax
0x1800147d3  mov     rax, [r14+30h]
0x1800147d7  mov     [rbp+190h+var_B0], rax
0x1800147de  mov     rax, [r14+14h]
0x1800147e2  mov     [rbp+190h+var_94], rax
0x1800147e9  mov     eax, [r14+4]
0x1800147ed  mov     [rbp+190h+var_A0], eax
0x1800147f3  movzx   eax, word ptr [r14+8]
0x1800147f8  mov     [rbp+190h+var_9C], ax
0x1800147ff  mov     ecx, [r14+0Ch]
0x180014803  mov     eax, [r14+38h]
0x180014807  mov     [rbp+190h+var_8C], eax
0x18001480d  cmp     edx, 2
0x180014810  cmovz   ecx, r15d
0x180014814  mov     [rbp+190h+var_98], ecx
0x18001481a  mov     r13, [rsp+290h+var_230]
0x18001481f  mov     [r13+60h], edi
0x180014823  mov     rax, [r12+58h]
0x180014828  mov     [r13+58h], rax
0x18001482c  mov     rax, [rbp+190h+hSourceHandle]
0x180014830  dec     rax
0x180014833  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180014837  jbe     loc_180014D5C
0x18001483d  mov     dword ptr [rsp+290h+var_248], ebx
0x180014841  mov     ecx, 78h ; 'x'; Size
0x180014846  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001484b  mov     r11, rax
0x18001484e  movzx   eax, [rbp+190h+var_140]
0x180014852  mov     [r11], al
0x180014855  mov     rax, [rbp+190h+hSourceHandle]
0x180014859  mov     [r11+8], rax
0x18001485d  mov     [rbp+190h+hSourceHandle], rbx
0x180014861  movups  xmmword ptr [r11+10h], xmm6
0x180014866  movups  xmmword ptr [r11+20h], xmm7
0x18001486b  movups  xmmword ptr [r11+30h], xmm8
0x180014870  movups  xmmword ptr [r11+40h], xmm9
0x180014875  mov     rax, [rbp+190h+var_F0]
0x18001487c  mov     [r11+50h], rax
0x180014880  movzx   eax, [rbp+190h+var_E8]
0x180014887  mov     [r11+58h], al
0x18001488b  mov     eax, [rbp+190h+var_E4]
0x180014891  mov     [r11+5Ch], eax
0x180014895  lea     rcx, [r11+60h]
0x180014899  lea     rdx, [rbp+190h+var_E0]
0x1800148a0  call    ??0?$vector@UInputProvider@@V?$allocator@UInputProvider@@@std@@@std@@QEAA@$$QEAV01@@Z; std::vector<InputProvider>::vector<InputProvider>(std::vector<InputProvider> &&)
0x1800148a5  mov     rdx, [r13+0B0h]
0x1800148ac  mov     [r13+0B0h], r11
0x1800148b3  test    rdx, rdx
0x1800148b6  jnz     loc_18001508F
0x1800148bc  mov     dword ptr [rsp+290h+var_240], ebx
0x1800148c0  lea     rax, [rsp+290h+var_240]
0x1800148c5  mov     qword ptr [rsp+290h+bInheritHandle], rax; enum ContextualProcessorState *
0x1800148ca  mov     rax, [rbp+190h+var_1F0]
0x1800148ce  mov     qword ptr [rsp+290h+dwDesiredAccess], rax; struct IInputTarget **
0x1800148d3  mov     r9, [rbp+190h+var_1E8]; struct IInputBuffer *
0x1800148d7  mov     r8, r13; struct InputContext *
0x1800148da  lea     rdx, [rbp+190h+var_C0]; struct HitTestInfo *
0x1800148e1  mov     rax, [rsp+290h+var_228]
0x1800148e6  mov     rcx, [rax+100h]; this
0x1800148ed  call    ?OnHitTest@ContextualProcessorManager@@QEAAJPEAUHitTestInfo@@PEAVInputContext@@PEAUIInputBuffer@@PEAPEAUIInputTarget@@PEAW4ContextualProcessorState@@@Z; ContextualProcessorManager::OnHitTest(HitTestInfo *,InputContext *,IInputBuffer *,IInputTarget * *,ContextualProcessorState *)
0x1800148f2  xor     r13d, r13d
0x1800148f5  test    eax, eax
0x1800148f7  jns     loc_180015099
0x1800148fd  mov     ebx, r13d
0x180014900  cmp     [rbp+190h+var_E8], 0
0x180014907  jnz     loc_180014CDE
0x18001490d  xor     r9d, r9d; Context
0x180014910  xor     r8d, r8d; Parameter
0x180014913  lea     rdx, ?InitEditionOnceCallback@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18001491a  lea     rcx, ?gInitOnce@@3T_RTL_RUN_ONCE@@A; InitOnce
0x180014921  call    cs:__imp_InitOnceExecuteOnce
0x180014927  test    eax, eax
0x180014929  jz      loc_180014C74
0x18001492f  mov     ecx, cs:?gdwDeviceFamily@@3KA; ulong gdwDeviceFamily
0x180014935  shl     r15, cl
0x180014938  test    r15, 1820h
0x18001493f  jnz     loc_180014D11
0x180014945  mov     esi, r13d
0x180014948  test    ebx, ebx
0x18001494a  jnz     loc_1800150A2
0x180014950  mov     [r12+64h], esi
0x180014955  mov     r12d, dword ptr [rsp+290h+var_248]
0x18001495a  mov     r15, [rbp+190h+var_E0]
0x180014961  test    r15, r15
0x180014964  jz      loc_180014A33
0x18001496a  mov     r14, [rbp+190h+var_D8]
0x180014971  mov     rbx, r15
0x180014974  cmp     r15, r14
0x180014977  jz      short loc_1800149F0
0x180014979  nop     dword ptr [rax+00000000h]
0x180014980  mov     rdi, [rbx]
0x180014983  test    rdi, rdi
0x180014986  jz      short loc_1800149E7
0x180014988  mov     rsi, [rbx+8]
0x18001498c  cmp     rdi, rsi
0x18001498f  jz      short loc_1800149B2
0x180014991  mov     rcx, [rdi]
0x180014994  test    rcx, rcx
0x180014997  jz      short loc_1800149A9
0x180014999  mov     [rdi], r13
0x18001499c  mov     rax, [rcx]
0x18001499f  mov     rax, [rax+10h]
0x1800149a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149a8  nop
0x1800149a9  add     rdi, 8
0x1800149ad  cmp     rdi, rsi
0x1800149b0  jnz     short loc_180014991
0x1800149b2  mov     rcx, [rbx]; void *
0x1800149b5  mov     rdx, [rbx+10h]
0x1800149b9  sub     rdx, rcx
0x1800149bc  and     rdx, 0FFFFFFFFFFFFFFF8h; struct std::nothrow_t *
0x1800149c0  mov     [rsp+290h+var_228], rdx
0x1800149c5  mov     [rsp+290h+var_230], rcx
0x1800149ca  cmp     rdx, 1000h
0x1800149d1  jnb     loc_180014A86
0x1800149d7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800149dc  mov     [rbx], r13
0x1800149df  mov     [rbx+8], r13
0x1800149e3  mov     [rbx+10h], r13
0x1800149e7  add     rbx, 18h
0x1800149eb  cmp     rbx, r14
0x1800149ee  jnz     short loc_180014980
0x1800149f0  mov     rax, [rbp+190h+var_D0]
0x1800149f7  sub     rax, r15
0x1800149fa  sar     rax, 3
0x1800149fe  mov     rcx, 0AAAAAAAAAAAAAAABh
0x180014a08  imul    rax, rcx
0x180014a0c  lea     rdx, [rax+rax*2]
0x180014a10  shl     rdx, 3; struct std::nothrow_t *
0x180014a14  mov     [rsp+290h+var_230], rdx
0x180014a19  mov     [rsp+290h+var_228], r15
0x180014a1e  cmp     rdx, 1000h
0x180014a25  jnb     loc_180014C80
0x180014a2b  mov     rcx, r15; void *
0x180014a2e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180014a33  mov     rcx, [rbp+190h+hSourceHandle]
0x180014a37  lea     rdx, [rcx-1]
0x180014a3b  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180014a3f  jbe     loc_180014D51
0x180014a45  mov     eax, r12d
0x180014a48  mov     rcx, [rbp+190h+var_80]
0x180014a4f  xor     rcx, rsp; StackCookie
0x180014a52  call    __security_check_cookie
0x180014a57  lea     r11, [rsp+290h+var_30]
0x180014a5f  mov     rbx, [r11+48h]
0x180014a63  movaps  xmm6, xmmword ptr [r11-10h]
  ... truncated ...
```
