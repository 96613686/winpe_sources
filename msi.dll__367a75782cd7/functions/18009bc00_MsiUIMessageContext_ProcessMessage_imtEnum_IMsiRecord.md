# MsiUIMessageContext::ProcessMessage(imtEnum,IMsiRecord *)

- ea: `0x18009bc00`
- end: `0x18009d629`
- name: `?ProcessMessage@MsiUIMessageContext@@AEAA?AW4imsEnum@@W4imtEnum@@PEAVIMsiRecord@@@Z`
- size: `6697`
- prototype: ``
- caller_count: `4`
- callee_count: `39`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18003ca18`
- `0x18009ae60`
- `0x18009b280`
- `0x1801c59e0`

## callees

- `0x180025560`
- `0x180025688`
- `0x180025a18`
- `0x180035a8c`
- `0x18003bccc`
- `0x18004295c`
- `0x18004ceb0`
- `0x180066074`
- `0x18006ef7c`
- `0x18008af8c`
- `0x18009bc00`
- `0x18009d630`
- `0x18009d810`
- `0x18009d9e8`
- `0x18009da6c`
- `0x18009dadc`
- `0x18009e43c`
- `0x1800a5fc4`
- `0x1800b8e10`
- `0x1801123bc`
- `0x18012cfdc`
- `0x1801382d4`
- `0x1801532b4`
- `0x1801b7c2c`
- `0x1801b7c9c`
- `0x1801b7d08`
- `0x1801b7df4`
- `0x1801b8154`
- `0x1801b822c`
- `0x1801b824c`
- `0x1801b84fc`
- `0x1801b895c`
- `0x1801c2dec`
- `0x1801c3780`
- `0x180200b44`
- `0x18021896c`
- `0x18025ab2a`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18009d368`
- `KERNEL32!GetProcAddress` at `0x18009d368`
- `KERNEL32!lstrlenW` at `0x18009bf75`
- `KERNEL32!lstrlenW` at `0x18009d484`
- `KERNEL32!lstrlenW` at `0x18009d4da`
- `KERNEL32!lstrlenW` at `0x18009d530`
- `KERNEL32!lstrlenW` at `0x18009d586`
- `KERNEL32!lstrlenW` at `0x18009d5d9`
- `KERNEL32!lstrlenW` at `0x18009bf75`
- `KERNEL32!lstrlenW` at `0x18009d484`
- `KERNEL32!lstrlenW` at `0x18009d4da`
- `KERNEL32!lstrlenW` at `0x18009d530`
- `KERNEL32!lstrlenW` at `0x18009d586`
- `KERNEL32!lstrlenW` at `0x18009d5d9`
- `GDI32!RemoveFontResourceW` at `0x18009c413`
- `GDI32!RemoveFontResourceW` at `0x18009c413`
- `GDI32!AddFontResourceW` at `0x18009c25b`
- `GDI32!AddFontResourceW` at `0x18009c25b`

## string_xrefs

- `0x18009c90b`: `RESTART MANAGER: Session opened.`
- `0x18009c8cf`: `RESTART MANAGER: Failed to open session; Windows Installer will use the built-in FilesInUse functionality. Error: %d`
- `0x18009ca48`: `RESTART MANAGER: Failed to add process ID %d resource; Windows Installer will use the built-in FilesInUse functionality. Error: %d`
- `0x18009caee`: `RESTART MANAGER: Failed to retrieve the list of applications that hold files in use; Windows Installer will use the built-in FilesInUse functionality. Error: %d`
- `0x18009cdea`: `RESTART MANAGER: Did not detect any app that holds files in use. Windows Installer will use the built-in FilesInUse functionality.`
- `0x18009d01f`: `Install server not responding`
- `0x18009d349`: `MsiHnd.dll`
- `0x18009d359`: `DllGetClassObject`

## pseudocode

```c
__int64 __fastcall MsiUIMessageContext::ProcessMessage(__int64 a1, int a2, struct IMsiRecord *a3)
{
  HANDLE v4; // r8
  unsigned int v5; // esi
  unsigned int v6; // r13d
  CRestartManagerWrapper *v8; // rcx
  int v9; // edi
  int v10; // r14d
  unsigned int v11; // ebx
  void (*v12)(void); // rax
  __int64 v14; // rcx
  unsigned int v15; // r13d
  unsigned int v16; // r13d
  unsigned int v17; // r13d
  __int64 v18; // rcx
  unsigned int v19; // r13d
  unsigned int v20; // r13d
  unsigned int v21; // r13d
  unsigned int v22; // r13d
  const WCHAR *v23; // rcx
  int v24; // eax
  unsigned __int16 *v25; // rax
  unsigned int v26; // r13d
  unsigned int v27; // r13d
  unsigned int v28; // r13d
  __int64 v29; // rcx
  char v30; // al
  unsigned int v31; // edi
  CRestartManagerWrapper *Instance; // rax
  struct IMsiRecord **v33; // rax
  bool v34; // si
  int v35; // edx
  CMsiEmbeddedUIManager *v36; // rcx
  int v37; // edx
  int v38; // edx
  int v39; // edx
  int v40; // edx
  __int64 (*v41)(void); // rbx
  unsigned int v42; // eax
  const WCHAR *v43; // rax
  CRestartManagerWrapper *v44; // rax
  __int64 v45; // rdx
  __int64 v46; // rcx
  int v47; // eax
  CRestartManagerWrapper *v48; // rax
  CRestartManagerWrapper *v49; // rsi
  __int64 v50; // rcx
  __int64 (__fastcall *v51)(CRestartManagerWrapper *, _QWORD, __int64); // rdi
  bool v52; // bl
  unsigned int v53; // eax
  __int64 v54; // r8
  unsigned int v55; // eax
  const WCHAR *v56; // rax
  bool v57; // zf
  __int64 v58; // rax
  void *v59; // rax
  __int64 v60; // rcx
  void *v61; // rdi
  __int64 (*v62)(void); // rdi
  unsigned int v63; // ebx
  unsigned int v64; // eax
  __int64 (*v65)(void); // r14
  __int64 v66; // rsi
  __int64 v67; // rdi
  unsigned int v68; // ebx
  unsigned int v69; // eax
  int v70; // edx
  int v71; // edx
  int v72; // edx
  int v73; // edx
  CRestartManagerWrapper *v74; // rax
  unsigned int v75; // eax
  CMsiSQMSession *v76; // rsi
  unsigned int v77; // ebx
  unsigned int v78; // eax
  struct IMsiRecord *v79; // rax
  __int64 v80; // r8
  struct IMsiRecord *v81; // rbx
  __int64 v82; // rax
  __int64 v83; // rcx
  __int64 *p_NoDataRecord; // rcx
  CRestartManagerWrapper *v85; // rax
  unsigned int started; // eax
  int v87; // eax
  CRestartManagerWrapper *v88; // rcx
  unsigned int v89; // eax
  char v90; // al
  CRestartManagerWrapper *v91; // rcx
  unsigned int v92; // r8d
  unsigned int ApplicationsList; // eax
  unsigned int v94; // eax
  unsigned int v95; // esi
  unsigned int v96; // eax
  void *v97; // rdi
  WCHAR *strAppName; // rdx
  unsigned int v99; // ecx
  __int64 v100; // rsi
  void (__fastcall *v101)(__int64, _QWORD, __int64); // rdi
  __int64 v102; // rbx
  __int64 v103; // rdi
  void (__fastcall *v104)(__int64, _QWORD, _QWORD); // rbx
  MsiString *v105; // rax
  int v106; // eax
  unsigned int v107; // r13d
  unsigned int v108; // r13d
  unsigned int v109; // r13d
  unsigned int v110; // r13d
  void (__fastcall *v111)(struct IMsiRecord *, _QWORD, _QWORD); // rbx
  MsiString *v112; // rax
  const wchar_t *v113; // r14
  void (__fastcall *v114)(struct IMsiRecord *, _QWORD, _QWORD); // rdi
  MsiString *v115; // rax
  struct IMsiRecord *v116; // rbx
  void (__fastcall *v117)(struct IMsiRecord *, _QWORD, _QWORD); // rdi
  MsiString *v118; // rax
  __int64 v119; // rcx
  void (__fastcall *v120)(struct IMsiRecord *, _QWORD, _QWORD); // rdi
  MsiString *v121; // rax
  struct IMsiRecord *v122; // rax
  const unsigned __int16 *v123; // rdx
  struct IMsiRecord *v124; // rbx
  void (__fastcall *v125)(struct IMsiRecord *, _QWORD, _QWORD); // rdi
  MsiString *v126; // rax
  __int64 v127; // rcx
  __int64 v128; // rcx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  __int64 v131; // r8
  int v132; // eax
  struct IMsiRecord *Record; // rbx
  __int64 v134; // rcx
  const WCHAR *v135; // rcx
  int v136; // eax
  const WCHAR *v137; // rcx
  int v138; // eax
  const WCHAR *v139; // rcx
  int v140; // eax
  const WCHAR *v141; // rcx
  int v142; // eax
  const WCHAR *v143; // rcx
  int v144; // eax
  bool v145[4]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v146; // [rsp+64h] [rbp-9Ch]
  unsigned int v147; // [rsp+68h] [rbp-98h] BYREF
  int i; // [rsp+6Ch] [rbp-94h] BYREF
  struct IMsiRecord *NoDataRecord; // [rsp+70h] [rbp-90h] BYREF
  struct IMsiRecord *v150; // [rsp+78h] [rbp-88h] BYREF
  void *v151; // [rsp+80h] [rbp-80h] BYREF
  struct IMsiRecord *v152; // [rsp+88h] [rbp-78h] BYREF
  CRestartManagerWrapper *v153; // [rsp+90h] [rbp-70h] BYREF
  int v154; // [rsp+98h] [rbp-68h]
  int v155; // [rsp+9Ch] [rbp-64h]
  unsigned int v156; // [rsp+A0h] [rbp-60h]
  int v157; // [rsp+A4h] [rbp-5Ch]
  int v158; // [rsp+A8h] [rbp-58h]
  _RM_PROCESS_INFO v159; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 *v160; // [rsp+350h] [rbp+250h] BYREF
  int v161; // [rsp+358h] [rbp+258h]
  char *v162; // [rsp+360h] [rbp+260h] BYREF
  int v163; // [rsp+368h] [rbp+268h]
  int v164; // [rsp+36Ch] [rbp+26Ch]
  char v165; // [rsp+370h] [rbp+270h] BYREF
  _BYTE v166[96]; // [rsp+380h] [rbp+280h] BYREF

  v155 = a2;
  v4 = 0;
  v5 = a2 & 0x1FFFFFFF;
  v150 = 0;
  v157 = a2 & 0x1FFFFFFF;
  v6 = (a2 & 0x1FFFFFFFu) >> 24;
  v8 = (CRestartManagerWrapper *)v6;
  v9 = 1 << ((a2 & 0x1FFFFFFFu) >> 24);
  v10 = a2 & 0x40000000;
  v158 = a2 & 0x40000000;
  v11 = 0;
  v156 = 0;
  v154 = v9;
  if ( (v9 & 0xF000FFF) == 0 )
  {
    v14 = *(_QWORD *)(a1 + 168);
    if ( !v14 )
    {
      if ( v6 > 0x11 )
      {
        v15 = v6 - 18;
        if ( v15 )
        {
          v16 = v15 - 1;
          if ( v16 )
          {
            v17 = v16 - 1;
            if ( v17 )
            {
              if ( v17 == 1 )
              {
                v137 = *(const WCHAR **)(a1 + 8);
                if ( !v137 )
                  goto LABEL_308;
                v138 = lstrlenW(v137);
                if ( !(unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(
                                         &g_rgchScriptInProgress,
                                         (unsigned int)(v138 + 1),
                                         0) )
                  goto LABEL_127;
                if ( (int)StringCchCopyW(g_rgchScriptInProgress, dword_1803062F8, *(const unsigned __int16 **)(a1 + 8)) < 0 )
                {
LABEL_308:
                  v25 = g_rgchScriptInProgress;
                  goto LABEL_321;
                }
              }
            }
            else
            {
              v139 = *(const WCHAR **)(a1 + 8);
              if ( !v139 )
                goto LABEL_312;
              v140 = lstrlenW(v139);
              if ( !(unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(
                                       &g_rgchBannerText,
                                       (unsigned int)(v140 + 1),
                                       0) )
                goto LABEL_127;
              if ( (int)StringCchCopyW(g_rgchBannerText, dword_1803062D8, *(const unsigned __int16 **)(a1 + 8)) < 0 )
              {
LABEL_312:
                v25 = g_rgchBannerText;
                goto LABEL_321;
              }
            }
          }
          else
          {
            v141 = *(const WCHAR **)(a1 + 8);
            if ( !v141 )
              goto LABEL_316;
            v142 = lstrlenW(v141);
            if ( !(unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(
                                     &g_rgchFatalException,
                                     (unsigned int)(v142 + 1),
                                     0) )
              goto LABEL_127;
            if ( (int)StringCchCopyW(g_rgchFatalException, dword_1803062B8, *(const unsigned __int16 **)(a1 + 8)) < 0 )
            {
LABEL_316:
              v25 = g_rgchFatalException;
              goto LABEL_321;
            }
          }
        }
        else
        {
          v143 = *(const WCHAR **)(a1 + 8);
          if ( !v143 )
            goto LABEL_320;
          v144 = lstrlenW(v143);
          if ( !(unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(
                                   &g_rgchFatalTimedOut,
                                   (unsigned int)(v144 + 1),
                                   0) )
            goto LABEL_127;
          if ( (int)StringCchCopyW(g_rgchFatalTimedOut, dword_180306298, *(const unsigned __int16 **)(a1 + 8)) < 0 )
          {
LABEL_320:
            v25 = g_rgchFatalTimedOut;
            goto LABEL_321;
          }
        }
LABEL_40:
        *(_QWORD *)(a1 + 8) = 0;
        goto LABEL_30;
      }
      if ( v6 == 17 )
      {
        v135 = *(const WCHAR **)(a1 + 8);
        if ( v135 )
        {
          v136 = lstrlenW(v135);
          if ( !(unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(
                                   &g_rgchFatalOutOfMemory,
                                   (unsigned int)(v136 + 1),
                                   0) )
            goto LABEL_127;
          if ( (int)StringCchCopyW(g_rgchFatalOutOfMemory, dword_180306278, *(const unsigned __int16 **)(a1 + 8)) >= 0 )
            goto LABEL_40;
        }
        v25 = g_rgchFatalOutOfMemory;
        goto LABEL_321;
      }
      v19 = v6 - 12;
      if ( !v19 )
      {
        v151 = 0;
        Library = (HMODULE)IsolationAwareLoadLibraryExW(L"MsiHnd.dll");
        *(_QWORD *)(a1 + 120) = Library;
        ProcAddress = GetProcAddress(Library, "DllGetClassObject");
        v153 = 0;
        if ( ProcAddress
          && !((unsigned int (__fastcall *)(GUID *, GUID *, CRestartManagerWrapper **))ProcAddress)(
                &IID_IMsiHandler,
                &IID_IUnknown,
                &v153) )
        {
          (*(void (__fastcall **)(CRestartManagerWrapper *, _QWORD, GUID *, void **))(*(_QWORD *)v153 + 24LL))(
            v153,
            0,
            &IID_IMsiHandler,
            &v151);
          (*(void (__fastcall **)(CRestartManagerWrapper *))(*(_QWORD *)v153 + 16LL))(v153);
        }
        if ( !v151 )
          goto LABEL_95;
        v131 = *(unsigned int *)(a1 + 188);
        v145[0] = 0;
        v132 = (*(__int64 (__fastcall **)(void *, _QWORD, __int64, HWND, bool *))(*(_QWORD *)v151 + 24LL))(
                 v151,
                 *(_QWORD *)a1,
                 v131,
                 qword_180309948,
                 v145);
        *(_QWORD *)a1 = 0;
        if ( !v132 )
        {
          (*(void (__fastcall **)(void *))(*(_QWORD *)v151 + 16LL))(v151);
          v151 = 0;
          if ( !v145[0] )
            goto LABEL_95;
LABEL_298:
          v31 = 1;
          goto LABEL_128;
        }
        v31 = 1;
        Record = CreateRecord(1u);
        v152 = Record;
        (*(void (__fastcall **)(struct IMsiRecord *, __int64, __int64))(*(_QWORD *)Record + 104LL))(Record, 1, 3);
        CBasicUI::Message(v134, 184549376, Record);
        p_NoDataRecord = (__int64 *)&v152;
        *(_QWORD *)(a1 + 272) = v151;
        goto LABEL_300;
      }
      v20 = v19 - 1;
      if ( !v20 )
      {
        v128 = *(_QWORD *)(a1 + 272);
        if ( v128 )
        {
          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v128 + 56LL))(v128, 0);
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 272) + 16LL))(*(_QWORD *)(a1 + 272));
          *(_QWORD *)(a1 + 272) = 0;
        }
        goto LABEL_298;
      }
      v21 = v20 - 1;
      if ( !v21 )
      {
        if ( !*(_QWORD *)(a1 + 272) || !*(_QWORD *)(a1 + 8) )
          goto LABEL_95;
        if ( (v9 & dword_180309978) != 0 )
        {
          NoDataRecord = MsiUIMessageContext::GetNoDataRecord((MsiUIMessageContext *)a1);
          (*(void (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)NoDataRecord + 8LL))(NoDataRecord);
          v120 = *(void (__fastcall **)(struct IMsiRecord *, _QWORD, _QWORD))(*(_QWORD *)NoDataRecord + 120LL);
          v121 = MsiString::MsiString((MsiString *)&v152, *(const unsigned __int16 **)(a1 + 8));
          v120(NoDataRecord, 0, *(_QWORD *)v121);
          (*(void (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)v152 + 16LL))(v152);
          v11 = CMsiAPIMessageRec::Message(g_messageRec, 234881024, NoDataRecord);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&NoDataRecord);
          if ( v11 )
            goto LABEL_40;
          v9 = v154;
        }
        if ( (dword_1803097B8 & 0x4000) == 0
          || (v11 = CMsiAPIMessage::Message(g_message, 234881024, *(_QWORD *)(a1 + 8))) == 0 )
        {
          if ( !g_pEmbeddedUI )
            goto LABEL_289;
          if ( (v9 & *((_DWORD *)g_pEmbeddedUI + 272)) == 0 )
            goto LABEL_289;
          v122 = CreateRecord(0);
          v123 = *(const unsigned __int16 **)(a1 + 8);
          v124 = v122;
          NoDataRecord = v122;
          v125 = *(void (__fastcall **)(struct IMsiRecord *, _QWORD, _QWORD))(*(_QWORD *)v122 + 120LL);
          v126 = MsiString::MsiString((MsiString *)&v152, v123);
          v125(v124, 0, *(_QWORD *)v126);
          (*(void (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)v152 + 16LL))(v152);
          v11 = CMsiEmbeddedUIManager::Message(v127, v5, v124);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&NoDataRecord);
          if ( !v11 )
LABEL_289:
            v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 272) + 40LL))(
                    *(_QWORD *)(a1 + 272),
                    *(_QWORD *)(a1 + 8));
        }
        goto LABEL_40;
      }
      v22 = v21 - 1;
      if ( v22 )
      {
        if ( v22 != 1 )
          goto LABEL_40;
        v23 = *(const WCHAR **)(a1 + 8);
        if ( v23 )
        {
          v24 = lstrlenW(v23);
          if ( !(unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(
                                   &g_rgchTimeRemaining,
                                   (unsigned int)(v24 + 1),
                                   0) )
            goto LABEL_127;
          if ( (int)StringCchCopyW(g_rgchTimeRemaining, dword_180306258, *(const unsigned __int16 **)(a1 + 8)) >= 0 )
            goto LABEL_40;
        }
        v25 = g_rgchTimeRemaining;
LABEL_321:
        *v25 = 0;
        goto LABEL_40;
      }
      if ( v5 == 251658244 )
      {
        if ( (g_dwLogMode & 0x400) != 0 || (dword_1803097B8 & 0x10) != 0 || (v106 = 7, (dword_180309978 & 0x10) != 0) )
          v106 = 6;
        goto LABEL_221;
      }
      v29 = v5 - 251658256;
      if ( v5 == 251658256 )
      {
        v113 = g_rgchFatalException;
      }
      else
      {
        v29 = v5 - 251658288;
        if ( v5 == 251658288 )
        {
          v113 = g_rgchFatalOutOfMemory;
        }
        else if ( v5 == 251658533 )
        {
          v113 = g_rgchFatalTimedOut;
        }
        else
        {
          v113 = &Default;
        }
      }
      if ( !*v113 )
      {
        v113 = L"Install server not responding";
        if ( v5 != 251658533 )
          v113 = L"Unexpected Termination";
      }
      if ( (v9 & dword_180309978) != 0 )
      {
        NoDataRecord = MsiUIMessageContext::GetNoDataRecord((MsiUIMessageContext *)a1);
        (*(void (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)NoDataRecord + 8LL))(NoDataRecord);
        v114 = *(void (__fastcall **)(struct IMsiRecord *, _QWORD, _QWORD))(*(_QWORD *)NoDataRecord + 120LL);
        v115 = MsiString::MsiString((MsiString *)&v152, v113);
        v114(NoDataRecord, 0, *(_QWORD *)v115);
        (*(void (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)v152 + 16LL))(v152);
        v11 = CMsiAPIMessageRec::Message(g_messageRec, v5, NoDataRecord);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&NoDataRecord);
        if ( v11 )
          goto LABEL_268;
        v9 = v154;
      }
      if ( ((v9 & dword_1803097B8) == 0 || (v11 = CMsiAPIMessage::Message(g_message, v5, v113)) == 0)
        && g_pEmbeddedUI
        && (v9 & *((_DWORD *)g_pEmbeddedUI + 272)) != 0 )
      {
        v116 = CreateRecord(0);
        NoDataRecord = v116;
        v117 = *(void (__fastcall **)(struct IMsiRecord *, _QWORD, _QWORD))(*(_QWORD *)v116 + 120LL);
        v118 = MsiString::MsiString((MsiString *)&v152, v113);
        v117(v116, 0, *(_QWORD *)v118);
        (*(void (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)v152 + 16LL))(v152);
        v11 = CMsiEmbeddedUIManager::Message(v119, v5, v116);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&NoDataRecord);
      }
LABEL_268:
      if ( (g_dwLogMode & 1) != 0 && hObject )
        WriteLog(v113);
      if ( v5 == 251658533 )
      {
        v30 = HIBYTE(dword_1803070BE);
        if ( !HIBYTE(dword_1803070BE) )
          goto LABEL_271;
        if ( (int)++*(_DWORD *)(a1 + 200) <= 10 )
        {
LABEL_82:
          v31 = 4;
LABEL_128:
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v150);
          return v31;
        }
      }
      v30 = HIBYTE(dword_1803070BE);
LABEL_271:
      if ( !v11 && !v30 )
        v11 = CBasicUI::FatalError(v29, v5, v113);
      v31 = v11;
      goto LABEL_128;
    }
    if ( v6 <= 0x12 )
    {
      if ( v6 != 18 )
      {
        v107 = v6 - 12;
        if ( !v107 )
          return 0;
        v108 = v107 - 1;
        if ( !v108 )
          return 0;
        v109 = v108 - 1;
        if ( v109 )
        {
          v110 = v109 - 1;
          if ( !v110 )
          {
            v31 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v14 + 32LL))(v14, v5);
            if ( v31 == 2 )
              MsiUIMessageContext::CancelAllSynchronousIo((MsiUIMessageContext *)a1);
            goto LABEL_128;
          }
          if ( v110 - 1 > 1 )
            goto LABEL_247;
        }
      }
    }
    else
    {
      v26 = v6 - 19;
      if ( v26 )
      {
        v27 = v26 - 1;
        if ( v27 )
        {
          v28 = v27 - 1;
          if ( v28 )
          {
            if ( v28 - 1 <= 1 )
              return 0;
LABEL_247:
            if ( !a3 )
              a3 = MsiUIMessageContext::GetNoDataRecord((MsiUIMessageContext *)a1);
            goto LABEL_242;
          }
        }
      }
    }
    a3 = MsiUIMessageContext::GetNoDataRecord((MsiUIMessageContext *)a1);
    v111 = *(void (__fastcall **)(struct IMsiRecord *, _QWORD, _QWORD))(*(_QWORD *)a3 + 120LL);
    v112 = MsiString::MsiString((MsiString *)&v152, *(const unsigned __int16 **)(a1 + 8));
    v111(a3, 0, *(_QWORD *)v112);
    (*(void (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)v152 + 16LL))(v152);
LABEL_242:
    v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct IMsiRecord *))(**(_QWORD **)(a1 + 168) + 24LL))(
            *(_QWORD *)(a1 + 168),
            v5,
            a3);
    if ( v11 == 2 )
      MsiUIMessageContext::CancelAllSynchronousIo((MsiUIMessageContext *)a1);
    (*(void (__fastcall **)(struct IMsiRecord *, _QWORD))(*(_QWORD *)a3 + 96LL))(a3, 0);
    goto LABEL_40;
  }
  if ( *(_BYTE *)(a1 + 148) )
  {
    if ( (v9 & 0x20000EF) != 0 )
    {
      *(_BYTE *)(a1 + 148) = 0;
      if ( (a2 & 1) != 0 )
      {
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v150);
        return 2;
      }
    }
  }
  if ( !a3 )
  {
    a3 = MsiUIMessageContext::GetNoDataRecord((MsiUIMessageContext *)a1);
    v4 = 0;
  }
  if ( *(_QWORD *)(a1 + 168) )
  {
    if ( g_pEmbeddedUI && (v9 & *((_DWORD *)g_pEmbeddedUI + 272)) != 0 )
    {
      v11 = CMsiEmbeddedUIManager::Message(v8, v5, a3);
      if ( v11 == 2 )
      {
        MsiUIMessageContext::CancelAllSynchronousIo((MsiUIMessageContext *)a1);
        if ( v150 )
          (*(void (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)v150 + 16LL))(v150);
        return 2;
      }
      if ( v11 )
      {
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v150);
        return v11;
      }
    }
    v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct IMsiRecord *))(**(_QWORD **)(a1 + 168) + 24LL))(
            *(_QWORD *)(a1 + 168),
            v10 | v5,
            a3);
    if ( v11 == 2 )
      MsiUIMessageContext::CancelAllSynchronousIo((MsiUIMessageContext *)a1);
    if ( v150 )
    {
      v12 = *(void (**)(void))(*(_QWORD *)v150 + 16LL);
      goto LABEL_11;
    }
    return v11;
  }
  if ( v5 == 83886080 )
  {
    Instance = (CRestartManagerWrapper *)CRestartManagerWrapper::GetInstance(*(_BYTE *)(a1 + 249) != 0);
    if ( Instance && CRestartManagerWrapper::IsEnabled(Instance) )
      goto LABEL_16;
    v33 = (struct IMsiRecord **)CComPointer<IEnumMsiRecord>::operator=(&v150);
    GetWindowTitles(a3, v33);
    v4 = 0;
    if ( v150 )
    {
      a3 = v150;
      goto LABEL_16;
    }
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        L"No window with title could be found for FilesInUse",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    goto LABEL_95;
  }
  if ( v6 == 24 )
  {
    v34 = 1;
    v35 = (*(__int64 (__fastcall **)(struct IMsiRecord *, __int64))(*(_QWORD *)a3 + 56LL))(a3, 1);
    if ( v35 <= 6 )
    {
      if ( v35 == 6 )
      {
        v31 = 1;
        if ( !g_pEmbeddedUI
          || !*((_DWORD *)g_pEmbeddedUI + 272)
          || CMsiEmbeddedUIManager::SendEEUICADetailsToServer(v36) )
        {
          goto LABEL_128;
        }
        if ( g_dmDiagnosticMode )
          DebugString(
            10,
            0,
            0,
            L"EEUI - Unable to send CA details to server",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
      }
      else if ( v35 )
      {
        v37 = v35 - 1;
        if ( v37 )
        {
          v38 = v37 - 1;
          if ( v38 )
          {
            v39 = v38 - 1;
            if ( v39 )
            {
              v40 = v39 - 1;
              if ( v40 )
              {
                if ( v40 == 1 && (*(unsigned int (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)a3 + 24LL))(a3) == 2 )
                {
                  v41 = USER32::AllowSetForegroundWindow;
                  v42 = (*(__int64 (__fastcall **)(struct IMsiRecord *, __int64))(*(_QWORD *)a3 + 56LL))(a3, 2);
                  ((void (__fastcall *)(_QWORD))v41)(v42);
LABEL_108:
                  v31 = 1;
                  goto LABEL_128;
                }
              }
              else
              {
                v44 = (CRestartManagerWrapper *)CRestartManagerWrapper::GetInstance(*(_BYTE *)(a1 + 249) != 0);
                if ( v44 && CRestartManagerWrapper::IsEnabled(v44) )
                {
                  v47 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v46 + 32LL))(v45);
                  if ( v47 != 1 )
                  {
                    v31 = 1;
                    if ( v47 != 3 )
                      goto LABEL_128;
                    goto LABEL_82;
                  }
                  goto LABEL_201;
                }
              }
            }
            else
            {
              v48 = (CRestartManagerWrapper *)CRestartManagerWrapper::GetInstance(*(_BYTE *)(a1 + 249) != 0);
              v49 = v48;
              if ( v48 && CRestartManagerWrapper::IsEnabled(v48) )
              {
                v51 = *(__int64 (__fastcall **)(CRestartManagerWrapper *, _QWORD, __int64))(*(_QWORD *)v50 + 16LL);
                v52 = (*(unsigned int (__fastcall **)(struct IMsiRecord *, __int64))(*(_QWORD *)a3 + 56LL))(a3, 3) == 1;
                v53 = (*(__int64 (__fastcall **)(struct IMsiRecord *, __int64))(*(_QWORD *)a3 + 56LL))(a3, 2);
                LOBYTE(v54) = v52;
                v55 = v51(v49, v53, v54);
                if ( v55 )
                {
                  if ( g_dmDiagnosticMode )
                    DebugString(
                      10,
                      0,
                      0,
                      L"RESTART MANAGER: Failed to shut down all applications. Error: %d",
                      (const unsigned __int16 *)v55,
                      L"(NULL)",
                      L"(NULL)",
                      L"(NULL)",
                      L"(NULL)",
                      L"(NULL)",
                      0,
                      0);
                }
                else if ( g_dmDiagnosticMode )
                {
                  DebugString(
                    10,
                    0,
                    0,
                    L"RESTART MANAGER: Successfully shut down all applications that held files in use.",
                    L"(NULL)",
                    L"(NULL)",
                    L"(NULL)",
                    L"(NULL)",
                    L"(NULL)",
                    L"(NULL)",
                    0,
                    0);
                }
                v31 = 7;
                if ( (*(unsigned int (__fastcall **)(CRestartManagerWrapper *))(*(_QWORD *)v49 + 32LL))(v49) != 1 )
                  v31 = 1;
                goto LABEL_128;
              }
            }
          }
          else if ( (*(unsigned int (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)a3 + 24LL))(a3) == 2 )
          {
            v56 = (const WCHAR *)(*(__int64 (__fastcall **)(struct IMsiRecord *, __int64))(*(_QWORD *)a3 + 80LL))(a3, 2);
            RemoveFontResourceW(v56);
            goto LABEL_108;
          }
        }
        else if ( (*(unsigned int (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)a3 + 24LL))(a3) == 2 )
        {
          v43 = (const WCHAR *)(*(__int64 (__fastcall **)(struct IMsiRecord *, __int64))(*(_QWORD *)a3 + 80LL))(a3, 2);
          AddFontResourceW(v43);
          goto LABEL_108;
        }
      }
      else
      {
        v57 = (*(unsigned int (__fastcall **)(struct IMsiRecord *, __int64))(*(_QWORD *)a3 + 56LL))(a3, 2) == 0x4000000;
        v58 = *(_QWORD *)a3;
        if ( !v57 )
        {
          v65 = SHELL32::SHChangeNotify;
          v66 = (*(__int64 (__fastcall **)(struct IMsiRecord *, __int64))(v58 + 80))(a3, 5);
          v67 = (*(__int64 (__fastcall **)(struct IMsiRecord *, __int64))(*(_QWORD *)a3 + 80LL))(a3, 4);
          v68 = (*(__int64 (__fastcall **)(struct IMsiRecord *, __int64))(*(_QWORD *)a3 + 56LL))(a3, 3);
          v69 = (*(__int64 (__fastcall **)(struct IMsiRecord *, __int64))(*(_QWORD *)a3 + 56LL))(a3, 2);
          ((void (__fastcall *)(_QWORD, _QWORD, __int64, __int64))v65)(v69, v68, v67, v66);
          goto LABEL_298;
        }
        if ( (*(unsigned int (__fastcall **)(struct IMsiRecord *))(v58 + 24))(a3) == 5 )
        {
          memset_0(v166, 0, 0x52u);
          v160 = 0;
          v161 = 0;
          v59 = (void *)(*(__int64 (__fastcall **)(struct IMsiRecord *, __int64))(*(_QWORD *)a3 + 64LL))(a3, 4);
          v60 = *(_QWORD *)a3;
          v61 = v59;
          v151 = v59;
          NoDataRecord = (struct IMsiRecord *)(*(__int64 (__fastcall **)(struct IMsiRecord *, __int64))(v60 + 64))(
                                                a3,
                                                5);
          if ( v61 )
            v34 = (*(unsigned int (__fastcall **)(void *, _BYTE *, __int64))(*(_QWORD *)v61 + 64LL))(v61, v166, 82) != 82;
          if ( NoDataRecord
            && (*(unsigned int (__fastcall **)(struct IMsiRecord *, unsigned __int16 **, __int64))(*(_QWORD *)NoDataRecord
                                                                                                 + 64LL))(
                 NoDataRecord,
                 &v160,
                 12) == 12
            && !v34 )
          {
            v62 = SHELL32::SHChangeNotify;
            v63 = (*(__int64 (__fastcall **)(struct IMsiRecord *, __int64))(*(_QWORD *)a3 + 56LL))(a3, 3);
            v64 = (*(__int64 (__fastcall **)(struct IMsiRecord *, __int64))(*(_QWORD *)a3 + 56LL))(a3, 2);
            ((void (__fastcall *)(_QWORD, _QWORD, unsigned __int16 **, _BYTE *))v62)(v64, v63, &v160, v166);
            v31 = 1;
          }
          else
          {
            v31 = 0x3FFF;
          }
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&NoDataRecord);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v151);
          goto LABEL_128;
        }
      }
LABEL_127:
      v31 = 0x3FFF;
      goto LABEL_128;
    }
    v31 = 0;
    v70 = v35 - 7;
    if ( v70 )
    {
      v71 = v70 - 1;
      if ( v71 )
      {
        v72 = v71 - 1;
        if ( !v72 )
        {
          v31 = 1;
          v76 = qword_180309730;
          if ( qword_180309730 )
          {
            v77 = (*(__int64 (__fastcall **)(struct IMsiRecord *, __int64))(*(_QWORD *)a3 + 56LL))(a3, 3);
            v78 = (*(__int64 (__fastcall **)(struct IMsiRecord *, __int64))(*(_QWORD *)a3 + 56LL))(a3, 2);
            CMsiSQMSession::RecordDWORD(v76, v78, v77);
          }
          goto LABEL_128;
        }
        v73 = v72 - 1;
        if ( !v73 )
        {
          *(_BYTE *)(a1 + 249) = 1;
          v74 = (CRestartManagerWrapper *)CRestartManagerWrapper::GetInstance(1);
          if ( v74 && *((_DWORD *)v74 + 2) != -1 )
          {
            v75 = CRestartManagerWrapper::EndSession(v74);
            if ( v75 != 1626 )
            {
              if ( v75 )
              {
                if ( g_dmDiagnosticMode )
                  DebugString(
                    10,
                    0,
                    0,
                    L"RESTART MANAGER: Failed while closing session. Error: %d",
                    (const unsigned __int16 *)v75,
                    L"(NULL)",
                    L"(NULL)",
                    L"(NULL)",
                    L"(NULL)",
                    L"(NULL)",
                    0,
                    0);
              }
              else if ( g_dmDiagnosticMode )
              {
                DebugString(
                  10,
                  0,
                  0,
                  L"RESTART MANAGER: Session closed.",
                  L"(NULL)",
                  L"(NULL)",
                  L"(NULL)",
                  L"(NULL)",
                  L"(NULL)",
                  L"(NULL)",
                  0,
                  0);
              }
            }
            CRestartManagerWrapper::DestroyInstance(1);
          }
          goto LABEL_128;
        }
        if ( v73 == 1 )
        {
          *(_BYTE *)(a1 + 249) = 0;
          goto LABEL_128;
        }
        goto LABEL_127;
      }
      v31 = 1;
      v79 = CreateRecord(1u);
      v80 = 4;
    }
    else
    {
      v31 = 1;
      v79 = CreateRecord(1u);
      v80 = 3;
    }
    v81 = v79;
    v82 = *(_QWORD *)v79;
    NoDataRecord = v81;
    (*(void (__fastcall **)(struct IMsiRecord *, __int64, __int64))(v82 + 104))(v81, 1, v80);
    CBasicUI::Message(v83, 184549376, v81);
    p_NoDataRecord = (__int64 *)&NoDataRecord;
LABEL_300:
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(p_NoDataRecord);
    goto LABEL_128;
  }
  if ( v5 != 419430400 )
    goto LABEL_16;
  i = (*(__int64 (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)a3 + 24LL))(a3);
  v57 = *(_BYTE *)(a1 + 249) == 0;
  v145[0] = i < 2;
  v85 = (CRestartManagerWrapper *)CRestartManagerWrapper::GetInstance(!v57);
  v153 = v85;
  if ( !v85 || i < 2 )
    goto LABEL_82;
  if ( *((_DWORD *)v85 + 2) == -1 )
  {
    v163 = 1;
    v162 = &v165;
    v164 = 1;
    started = CRestartManagerWrapper::StartSession(v85);
    if ( started )
    {
      v145[0] = 1;
      if ( g_dmDiagnosticMode )
        DebugString(
          10,
          0,
          0,
          L"RESTART MANAGER: Failed to open session; Windows Installer will use the built-in FilesInUse functionality. Error: %d",
          (const unsigned __int16 *)started,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
    }
    else if ( g_dmDiagnosticMode )
    {
      DebugString(
        10,
        0,
        0,
        L"RESTART MANAGER: Session opened.",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    }
    CAPITempBuffer<unsigned short,1>::Destroy(&v162);
    if ( v145[0] )
      goto LABEL_82;
    v145[0] = 0;
  }
  else
  {
    CRestartManagerWrapper::Reset(v85);
  }
  if ( !CRestartManagerWrapper::IsEnabled(v153) )
    goto LABEL_82;
  v147 = 0;
  v87 = 2;
  while ( 1 )
  {
    v146 = v87;
    i = v87 + 2;
    if ( v87 + 2 > (*(unsigned int (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)a3 + 24LL))(a3) )
    {
      v90 = v145[0];
      goto LABEL_187;
    }
    v160 = 0;
    v161 = 0;
    LODWORD(v160) = (*(__int64 (__fastcall **)(struct IMsiRecord *, _QWORD))(*(_QWORD *)a3 + 56LL))(a3, v146);
    v161 = (*(__int64 (__fastcall **)(struct IMsiRecord *, _QWORD))(*(_QWORD *)a3 + 56LL))(a3, v146 + 1);
    HIDWORD(v160) = (*(__int64 (__fastcall **)(struct IMsiRecord *, _QWORD))(*(_QWORD *)a3 + 56LL))(a3, (unsigned int)i);
    if ( !CRestartManagerWrapper::IsEnabled(v153) )
    {
      v90 = 1;
      goto LABEL_188;
    }
    v89 = (*(__int64 (__fastcall **)(CRestartManagerWrapper *, unsigned __int16 **, _QWORD))(*(_QWORD *)v88 + 8LL))(
            v88,
            &v160,
            0);
    if ( v89 )
      break;
    v87 = v146 + 3;
    ++v147;
  }
  if ( g_dmDiagnosticMode )
    DebugString(
      10,
      0,
      0,
      L"RESTART MANAGER: Failed to add process ID %d resource; Windows Installer will use the built-in FilesInUse function"
       "ality. Error: %d",
      (const unsigned __int16 *)(unsigned int)v160,
      (const unsigned __int16 *)v89,
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      0,
      0);
  v90 = 1;
LABEL_187:
  v88 = v153;
LABEL_188:
  if ( !v147 || v90 || !CRestartManagerWrapper::IsEnabled(v88) )
    goto LABEL_82;
  v147 = v92;
  i = -1;
  ApplicationsList = CRestartManagerWrapper::GetApplicationsList(v91, (enum TRI *)&i, &v147);
  if ( ApplicationsList )
  {
    if ( g_dmDiagnosticMode )
      DebugString(
        10,
        0,
        0,
        L"RESTART MANAGER: Failed to retrieve the list of applications that hold files in use; Windows Installer will use "
         "the built-in FilesInUse functionality. Error: %d",
        (const unsigned __int16 *)ApplicationsList,
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    goto LABEL_82;
  }
  if ( i == 1 )
  {
LABEL_201:
    v31 = 7;
    goto LABEL_128;
  }
  if ( !v147 )
  {
LABEL_216:
    if ( g_dmDiagnosticMode )
      DebugString(
        10,
        0,
        0,
        L"RESTART MANAGER: Did not detect any app that holds files in use. Windows Installer will use the built-in FilesIn"
         "Use functionality.",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    goto LABEL_82;
  }
  if ( (*(unsigned int (__fastcall **)(struct IMsiRecord *, __int64, _QWORD))(*(_QWORD *)a3 + 56LL))(a3, 1, 0) == 1 )
    goto LABEL_298;
  v146 = 0;
  v159.Process.dwProcessId = 0;
  memset_0(&v159.Process.ProcessStartTime, 0, 0x298u);
  v94 = 0;
  v147 = 0;
  v95 = 0;
  for ( i = 0; ; ++i )
  {
    v96 = CRestartManagerWrapper::EnumApplications(v153, v94, &v159);
    v4 = 0;
    if ( v96 )
      break;
    CRestartManagerWrapper::ReportDetectedApplication(v8, &v159);
    v97 = &MsiString::s_NullString;
    v151 = &MsiString::s_NullString;
    if ( v159.strAppName[0] )
    {
      strAppName = v159.strAppName;
    }
    else
    {
      if ( !v159.strServiceShortName[0] )
      {
        if ( g_dmDiagnosticMode )
        {
          DebugString(
            10,
            0,
            0,
            L"RESTART MANAGER: Did not detect any name for process Id %d, so it will not be displayed in the UI!",
            (const unsigned __int16 *)v159.Process.dwProcessId,
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
          v97 = v151;
        }
        memset_0(&v159, 0, sizeof(v159));
        (*(void (__fastcall **)(void *))(*(_QWORD *)v97 + 16LL))(v97);
        goto LABEL_213;
      }
      strAppName = v159.strServiceShortName;
    }
    MsiString::operator=(&v151, strAppName);
    v99 = v146;
    if ( (v146 & 7) == 0 )
    {
      if ( v146 + 8 > 0xFFFF )
      {
        (*(void (__fastcall **)(void *))(*(_QWORD *)v151 + 16LL))(v151);
        v4 = 0;
        break;
      }
      NoDataRecord = (struct IMsiRecord *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 216) + 48LL))(*(_QWORD *)(a1 + 216));
      (*(void (__fastcall **)(struct IMsiRecord *, struct IMsiRecord *))(*(_QWORD *)NoDataRecord + 200LL))(
        NoDataRecord,
        v150);
      CComPointer<IXMLDOMElement>::operator=(&v150, &NoDataRecord);
      if ( !v146 )
      {
        v100 = (__int64)v150;
        v101 = *(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v150 + 120LL);
        v102 = (*(__int64 (__fastcall **)(struct IMsiRecord *, _QWORD))(*(_QWORD *)a3 + 72LL))(a3, 0);
        v101(v100, 0, v102);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v102 + 16LL))(v102);
        v95 = v147;
      }
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&NoDataRecord);
      v99 = v146;
    }
    v103 = (__int64)v150;
    v146 = v99 + 1;
    v104 = *(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v150 + 120LL);
    v105 = MsiString::MsiString((MsiString *)&v152, v159.Process.dwProcessId);
    v104(v103, v146, *(_QWORD *)v105);
    (*(void (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)v152 + 16LL))(v152);
    (*(void (__fastcall **)(struct IMsiRecord *, _QWORD, void *))(*(_QWORD *)v150 + 120LL))(v150, ++v146, v151);
    memset_0(&v159, 0, sizeof(v159));
    v147 = ++v95;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v151 + 16LL))(v151);
LABEL_213:
    v94 = i + 1;
  }
  a3 = v150;
  v11 = v156;
  v5 = v157;
  v9 = v154;
  if ( !v147 )
    goto LABEL_216;
LABEL_16:
  if ( v158 != (_DWORD)v4 )
  {
    if ( (unsigned int)(*(_DWORD *)(a1 + 188) - 2) <= 1 )
    {
      v106 = CBasicUI::Message(v8, v5 | 0x40000000, a3);
LABEL_221:
      v31 = v106;
      goto LABEL_128;
    }
LABEL_95:
    v31 = 0;
    goto LABEL_128;
  }
  if ( v6 - 1 <= 1 && hObject == v4 )
  {
    MsiUIMessageContext::InitializeLog((MsiUIMessageContext *)a1, 1, 0);
    v4 = 0;
  }
  if ( (v9 & 0x311) != 0 && v155 >= (int)v4 && ((v9 & g_dwLogMode) != 0 || v5 == 67108880) )
    LogRecord(a3);
  if ( ((v9 & dword_180309978) == 0 || (v11 = CMsiAPIMessageRec::Message(g_messageRec, v5, a3)) == 0)
    && ((v9 & dword_1803097B8) == 0
     || (v9 & 0x300) != 0
     && (*(unsigned int (__fastcall **)(struct IMsiRecord *, _QWORD, HANDLE))(*(_QWORD *)a3 + 32LL))(a3, 0, v4)
     || (v11 = CMsiAPIMessage::Message(g_message, v5, a3)) == 0)
    && g_pEmbeddedUI
    && (v9 & *((_DWORD *)g_pEmbeddedUI + 272)) != 0 )
  {
    v11 = CMsiEmbeddedUIManager::Message(0, v5, a3);
  }
  if ( (v6 == 26 || v6 == 27) && !v11 )
    v11 = 1;
  if ( (!HIBYTE(dword_1803070BE) && !v11 || v6 == 11 || byte_1803070C2 && v6 == 6 && !v11)
    && ((v9 & 0x300) == 0 || !(*(unsigned int (__fastcall **)(struct IMsiRecord *, _QWORD))(*(_QWORD *)a3 + 32LL))(
                                a3,
                                0)) )
  {
    v18 = *(_QWORD *)(a1 + 272);
    if ( v18 )
      v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IMsiRecord *))(*(_QWORD *)v18 + 32LL))(v18, v5, a3);
    if ( !v11 || v6 == 11 )
      v11 = CBasicUI::Message(0, v5, a3);
  }
  if ( ((unsigned __int8)v9 & (unsigned __int8)g_dwLogMode & 0x8E) != 0 && v155 >= 0 )
    LogRecord(a3);
  if ( (v9 & 0x700) != 0 && *(_BYTE *)(a1 + 148) )
  {
    v11 = 2;
    *(_BYTE *)(a1 + 148) = 0;
  }
LABEL_30:
  if ( v150 )
  {
    v12 = *(void (**)(void))(*(_QWORD *)v150 + 16LL);
LABEL_11:
    v12();
  }
  return v11;
}

```

## disassembly

```asm
0x18009bc00  mov     [rsp-8+arg_18], rbx
0x18009bc05  push    rbp
0x18009bc06  push    rsi
0x18009bc07  push    rdi
0x18009bc08  push    r12
0x18009bc0a  push    r13
0x18009bc0c  push    r14
0x18009bc0e  push    r15
0x18009bc10  lea     rbp, [rsp-2F0h]
0x18009bc18  sub     rsp, 3F0h
0x18009bc1f  mov     rax, cs:__security_cookie
0x18009bc26  xor     rax, rsp
0x18009bc29  mov     [rbp+320h+var_40], rax
0x18009bc30  mov     r15, r8
0x18009bc33  mov     [rbp+320h+var_384], edx
0x18009bc36  xor     r8d, r8d
0x18009bc39  mov     esi, edx
0x18009bc3b  and     esi, 1FFFFFFFh
0x18009bc41  mov     [rsp+420h+var_3A8], r8
0x18009bc46  mov     r13d, esi
0x18009bc49  mov     [rbp+320h+var_37C], esi
0x18009bc4c  shr     r13d, 18h
0x18009bc50  mov     r12, rcx
0x18009bc53  lea     eax, [r8+1]
0x18009bc57  mov     ecx, r13d
0x18009bc5a  mov     edi, eax
0x18009bc5c  mov     r14d, edx
0x18009bc5f  shl     edi, cl
0x18009bc61  and     r14d, 40000000h
0x18009bc68  mov     [rbp+320h+var_378], r14d
0x18009bc6c  mov     ebx, r8d
0x18009bc6f  mov     [rbp+320h+var_380], ebx
0x18009bc72  mov     [rbp+320h+var_388], edi
0x18009bc75  test    edi, 0F000FFFh
0x18009bc7b  jz      loc_18009BE32
0x18009bc81  cmp     [r12+94h], r8b
0x18009bc89  jnz     loc_18009C09F
0x18009bc8f  test    r15, r15
0x18009bc92  jz      loc_18009C0CB
0x18009bc98  cmp     [r12+0A8h], r8
0x18009bca0  jz      short loc_18009BD1F
0x18009bca2  mov     rax, cs:?g_pEmbeddedUI@@3PEAVCMsiEmbeddedUIManager@@EA; CMsiEmbeddedUIManager * g_pEmbeddedUI
0x18009bca9  test    rax, rax
0x18009bcac  jnz     loc_18009C0DE
0x18009bcb2  mov     rcx, [r12+0A8h]
0x18009bcba  or      esi, r14d
0x18009bcbd  mov     r8, r15
0x18009bcc0  mov     edx, esi
0x18009bcc2  mov     rax, [rcx]
0x18009bcc5  mov     rax, [rax+18h]
0x18009bcc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009bcce  mov     ebx, eax
0x18009bcd0  cmp     eax, 2
0x18009bcd3  jnz     short loc_18009BCDD
0x18009bcd5  mov     rcx, r12; this
0x18009bcd8  call    ?CancelAllSynchronousIo@MsiUIMessageContext@@QEAAIXZ; MsiUIMessageContext::CancelAllSynchronousIo(void)
0x18009bcdd  mov     rcx, [rsp+420h+var_3A8]
0x18009bce2  test    rcx, rcx
0x18009bce5  jz      short loc_18009BCF3
0x18009bce7  mov     rdx, [rcx]
0x18009bcea  mov     rax, [rdx+10h]
0x18009bcee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009bcf3  mov     eax, ebx
0x18009bcf5  mov     rcx, [rbp+320h+var_40]
0x18009bcfc  xor     rcx, rsp; StackCookie
0x18009bcff  call    __security_check_cookie
0x18009bd04  mov     rbx, [rsp+420h+arg_18]
0x18009bd0c  add     rsp, 3F0h
0x18009bd13  pop     r15
0x18009bd15  pop     r14
0x18009bd17  pop     r13
0x18009bd19  pop     r12
0x18009bd1b  pop     rdi
0x18009bd1c  pop     rsi
0x18009bd1d  pop     rbp
0x18009bd1e  retn
0x18009bd1f  mov     r14d, 2
0x18009bd25  cmp     esi, 5000000h
0x18009bd2b  jz      loc_18009C106
0x18009bd31  cmp     r13d, 18h
0x18009bd35  jz      loc_18009C1B1
0x18009bd3b  cmp     esi, 19000000h
0x18009bd41  jz      loc_18009C82D
0x18009bd47  cmp     [rbp+320h+var_378], r8d
0x18009bd4b  jnz     loc_18009CE28
0x18009bd51  lea     eax, [r13-1]
0x18009bd55  mov     ecx, 1
0x18009bd5a  cmp     eax, ecx
0x18009bd5c  jbe     loc_18009C034
0x18009bd62  test    edi, 311h
0x18009bd68  jnz     loc_18009BE7C
0x18009bd6e  test    cs:dword_180309978, edi
0x18009bd74  jz      short loc_18009BD91
0x18009bd76  mov     r8, r15
0x18009bd79  lea     rcx, ?g_messageRec@@3VCMsiAPIMessageRec@@A; CMsiAPIMessageRec g_messageRec
0x18009bd80  mov     edx, esi
0x18009bd82  call    ?Message@CMsiAPIMessageRec@@QEBA?AW4imsEnum@@W4imtEnum@@AEAVIMsiRecord@@@Z; CMsiAPIMessageRec::Message(imtEnum,IMsiRecord &)
0x18009bd87  mov     ebx, eax
0x18009bd89  test    eax, eax
0x18009bd8b  jnz     loc_18009BF30
0x18009bd91  test    cs:dword_1803097B8, edi
0x18009bd97  jnz     loc_18009CE58
0x18009bd9d  mov     rax, cs:?g_pEmbeddedUI@@3PEAVCMsiEmbeddedUIManager@@EA; CMsiEmbeddedUIManager * g_pEmbeddedUI
0x18009bda4  xor     ecx, ecx
0x18009bda6  test    rax, rax
0x18009bda9  jnz     loc_18009CE82
0x18009bdaf  cmp     r13d, 1Ah
0x18009bdb3  jz      loc_18009CE9F
0x18009bdb9  cmp     r13d, 1Bh
0x18009bdbd  jz      loc_18009CE9F
0x18009bdc3  cmp     byte ptr cs:dword_1803070BE+3, cl
0x18009bdc9  jz      loc_18009BEA7
0x18009bdcf  cmp     r13d, 0Bh
0x18009bdd3  jz      loc_18009BEAF
0x18009bdd9  cmp     cs:byte_1803070C2, cl
0x18009bddf  jnz     loc_18009CEAE
0x18009bde5  mov     eax, cs:?g_dwLogMode@@3KA; ulong g_dwLogMode
0x18009bdeb  and     eax, edi
0x18009bded  test    al, 8Eh
0x18009bdef  jnz     loc_18009CEC5
0x18009bdf5  test    edi, 700h
0x18009bdfb  jnz     short loc_18009BE17
0x18009bdfd  mov     rcx, [rsp+420h+var_3A8]
0x18009be02  test    rcx, rcx
0x18009be05  jz      loc_18009BCF3
0x18009be0b  mov     rax, [rcx]
0x18009be0e  mov     rax, [rax+10h]
0x18009be12  jmp     loc_18009BCEE
0x18009be17  cmp     byte ptr [r12+94h], 0
0x18009be20  jz      short loc_18009BDFD
0x18009be22  mov     ebx, r14d
0x18009be25  xor     r14d, r14d
0x18009be28  mov     [r12+94h], r14b
0x18009be30  jmp     short loc_18009BDFD
0x18009be32  mov     rcx, [r12+0A8h]
0x18009be3a  xor     r14d, r14d
0x18009be3d  test    rcx, rcx
0x18009be40  jnz     loc_18009BFC1
0x18009be46  cmp     r13d, 11h
0x18009be4a  jbe     loc_18009BF37
0x18009be50  sub     r13d, 12h
0x18009be54  jz      loc_18009D5CF
0x18009be5a  sub     r13d, eax
0x18009be5d  jz      loc_18009D57C
0x18009be63  sub     r13d, eax
0x18009be66  jz      loc_18009D526
0x18009be6c  cmp     r13d, eax
0x18009be6f  jz      loc_18009D4D0
0x18009be75  mov     [r12+8], r14
0x18009be7a  jmp     short loc_18009BDFD
0x18009be7c  cmp     [rbp+320h+var_384], r8d
0x18009be80  jl      loc_18009BD6E
0x18009be86  test    cs:?g_dwLogMode@@3KA, edi; ulong g_dwLogMode
0x18009be8c  jnz     short loc_18009BE9A
0x18009be8e  cmp     esi, 4000010h
0x18009be94  jnz     loc_18009BD6E
0x18009be9a  mov     rcx, r15; struct IMsiRecord *
0x18009be9d  call    ?LogRecord@@YA_NAEAVIMsiRecord@@@Z; LogRecord(IMsiRecord &)
0x18009bea2  jmp     loc_18009BD6E
0x18009bea7  test    ebx, ebx
0x18009bea9  jnz     loc_18009BDCF
0x18009beaf  test    edi, 300h
0x18009beb5  jz      short loc_18009BED2
0x18009beb7  mov     rax, [r15]
0x18009beba  xor     edx, edx
0x18009bebc  mov     rcx, r15
0x18009bebf  mov     rax, [rax+20h]
0x18009bec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009bec8  xor     ecx, ecx
0x18009beca  test    eax, eax
0x18009becc  jnz     loc_18009BDE5
0x18009bed2  mov     rcx, [r12+110h]
0x18009beda  test    rcx, rcx
0x18009bedd  jz      short loc_18009BEF2
0x18009bedf  mov     rax, [rcx]
0x18009bee2  mov     r8, r15
0x18009bee5  mov     edx, esi
0x18009bee7  mov     rax, [rax+20h]
0x18009beeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009bef0  mov     ebx, eax
0x18009bef2  xor     ecx, ecx
0x18009bef4  test    ebx, ebx
0x18009bef6  jz      short loc_18009BF02
0x18009bef8  cmp     r13d, 0Bh
0x18009befc  jnz     loc_18009BDE5
0x18009bf02  mov     r8, r15
0x18009bf05  mov     edx, esi
0x18009bf07  call    ?Message@CBasicUI@@QEAA?AW4imsEnum@@W4imtEnum@@AEAVIMsiRecord@@@Z; CBasicUI::Message(imtEnum,IMsiRecord &)
0x18009bf0c  mov     ebx, eax
0x18009bf0e  xor     ecx, ecx
0x18009bf10  jmp     loc_18009BDE5
0x18009bf15  mov     r8, r15
0x18009bf18  lea     rcx, ?g_message@@3VCMsiAPIMessage@@A; CMsiAPIMessage g_message
0x18009bf1f  mov     edx, esi
0x18009bf21  call    ?Message@CMsiAPIMessage@@QEBA?AW4imsEnum@@W4imtEnum@@AEAVIMsiRecord@@@Z; CMsiAPIMessage::Message(imtEnum,IMsiRecord &)
0x18009bf26  mov     ebx, eax
0x18009bf28  test    eax, eax
0x18009bf2a  jz      loc_18009BD9D
0x18009bf30  xor     ecx, ecx
0x18009bf32  jmp     loc_18009BDAF
0x18009bf37  jz      loc_18009D47A
0x18009bf3d  sub     r13d, 0Ch
0x18009bf41  jz      loc_18009D349
0x18009bf47  sub     r13d, eax
0x18009bf4a  jz      loc_18009D309
0x18009bf50  sub     r13d, eax
0x18009bf53  jz      loc_18009D1A5
0x18009bf59  sub     r13d, eax
0x18009bf5c  jz      loc_18009CFCB
0x18009bf62  cmp     r13d, eax
0x18009bf65  jnz     loc_18009BE75
0x18009bf6b  mov     rcx, [r12+8]; lpString
0x18009bf70  test    rcx, rcx
0x18009bf73  jz      short loc_18009BFB5
0x18009bf75  call    cs:__imp_lstrlenW
0x18009bf7b  xor     r8d, r8d
0x18009bf7e  lea     rcx, ?g_rgchTimeRemaining@@3V?$CAPITempBuffer@G$00@@A; CAPITempBuffer<ushort,1> g_rgchTimeRemaining
0x18009bf85  lea     edx, [rax+1]
0x18009bf88  call    ?SetSize@?$CAPITempBuffer@G$00@@QEAA_NH_N@Z; CAPITempBuffer<ushort,1>::SetSize(int,bool)
0x18009bf8d  test    al, al
0x18009bf8f  jz      loc_18009C436
0x18009bf95  movsxd  rdx, cs:dword_180306258; unsigned __int64
0x18009bf9c  mov     r8, [r12+8]; unsigned __int16 *
0x18009bfa1  mov     rcx, cs:?g_rgchTimeRemaining@@3V?$CAPITempBuffer@G$00@@A; unsigned __int16 *
0x18009bfa8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18009bfad  test    eax, eax
0x18009bfaf  jns     loc_18009BE75
0x18009bfb5  mov     rax, cs:?g_rgchTimeRemaining@@3V?$CAPITempBuffer@G$00@@A; CAPITempBuffer<ushort,1> g_rgchTimeRemaining
0x18009bfbc  jmp     loc_18009D620
0x18009bfc1  cmp     r13d, 12h
0x18009bfc5  jbe     loc_18009CEDB
0x18009bfcb  sub     r13d, 13h
0x18009bfcf  jz      loc_18009CF0C
0x18009bfd5  sub     r13d, eax
0x18009bfd8  jz      loc_18009CF0C
0x18009bfde  sub     r13d, eax
0x18009bfe1  jz      loc_18009CF0C
0x18009bfe7  sub     r13d, eax
0x18009bfea  jnz     loc_18009CFB0
0x18009bff0  xor     eax, eax
0x18009bff2  jmp     loc_18009BCF5
0x18009bff7  mov     r8, r15
0x18009bffa  mov     edx, esi
0x18009bffc  call    ?Message@CMsiEmbeddedUIManager@@QEAA?AW4imsEnum@@W4imtEnum@@AEAVIMsiRecord@@@Z; CMsiEmbeddedUIManager::Message(imtEnum,IMsiRecord &)
0x18009c001  mov     ebx, eax
0x18009c003  cmp     eax, 2
0x18009c006  jnz     loc_18009C0EF
0x18009c00c  mov     rcx, r12; this
0x18009c00f  call    ?CancelAllSynchronousIo@MsiUIMessageContext@@QEAAIXZ; MsiUIMessageContext::CancelAllSynchronousIo(void)
0x18009c014  mov     rcx, [rsp+420h+var_3A8]
0x18009c019  test    rcx, rcx
0x18009c01c  jz      short loc_18009C02A
0x18009c01e  mov     rax, [rcx]
0x18009c021  mov     rax, [rax+10h]
0x18009c025  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c02a  mov     eax, 2
0x18009c02f  jmp     loc_18009BCF5
0x18009c034  cmp     cs:hObject, r8
0x18009c03b  jnz     loc_18009BD62
0x18009c041  mov     dl, cl; bool
0x18009c043  xor     r8d, r8d; struct CEngineMainThreadData *
0x18009c046  mov     rcx, r12; this
0x18009c049  call    ?InitializeLog@MsiUIMessageContext@@AEAA_N_NPEBUCEngineMainThreadData@@@Z; MsiUIMessageContext::InitializeLog(bool,CEngineMainThreadData const *)
0x18009c04e  xor     r8d, r8d
0x18009c051  jmp     loc_18009BD62
0x18009c056  cmp     cs:hObject, r15
0x18009c05d  jz      short loc_18009C067
0x18009c05f  mov     rcx, r14; Src
0x18009c062  call    ?WriteLog@@YA_NPEBG@Z; WriteLog(ushort const *)
0x18009c067  cmp     esi, r13d
0x18009c06a  jnz     loc_18009D150
0x18009c070  mov     al, byte ptr cs:dword_1803070BE+3
0x18009c076  test    al, al
0x18009c078  jz      loc_18009D156
0x18009c07e  inc     dword ptr [r12+0C8h]
0x18009c086  cmp     dword ptr [r12+0C8h], 0Ah
0x18009c08f  jg      loc_18009D150
0x18009c095  mov     edi, 4
0x18009c09a  jmp     loc_18009C43B
0x18009c09f  test    edi, 20000EFh
0x18009c0a5  jz      loc_18009BC8F
0x18009c0ab  mov     [r12+94h], r8b
0x18009c0b3  test    al, sil
0x18009c0b6  jz      loc_18009BC8F
0x18009c0bc  lea     rcx, [rsp+420h+var_3A8]
0x18009c0c1  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x18009c0c6  jmp     loc_18009C02A
0x18009c0cb  mov     rcx, r12; this
0x18009c0ce  call    ?GetNoDataRecord@MsiUIMessageContext@@QEAAPEAVIMsiRecord@@XZ; MsiUIMessageContext::GetNoDataRecord(void)
0x18009c0d3  mov     r15, rax
0x18009c0d6  xor     r8d, r8d
0x18009c0d9  jmp     loc_18009BC98
0x18009c0de  test    [rax+440h], edi
0x18009c0e4  jz      loc_18009BCB2
0x18009c0ea  jmp     loc_18009BFF7
0x18009c0ef  test    ebx, ebx
0x18009c0f1  jz      loc_18009BCB2
0x18009c0f7  lea     rcx, [rsp+420h+var_3A8]
0x18009c0fc  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x18009c101  jmp     loc_18009BCF3
  ... truncated ...
```
