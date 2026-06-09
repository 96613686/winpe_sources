# MsiUIMessageContext::ProcessMessage(imtEnum,IMsiRecord *)

- ea: `0x180009c38`
- end: `0x18000b698`
- name: `?ProcessMessage@MsiUIMessageContext@@AEAA?AW4imsEnum@@W4imtEnum@@PEAVIMsiRecord@@@Z`
- size: `6752`
- prototype: ``
- caller_count: `4`
- callee_count: `39`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180008d90`
- `0x180009268`
- `0x1800202e4`
- `0x1801ce0a0`

## callees

- `0x180003b10`
- `0x180005af8`
- `0x1800091e4`
- `0x180009c38`
- `0x18000b6a0`
- `0x18000b8bc`
- `0x18000c4bc`
- `0x180014160`
- `0x180014288`
- `0x18001f57c`
- `0x18004a014`
- `0x18004dcac`
- `0x180081de0`
- `0x18008c93c`
- `0x180094efc`
- `0x1800a5de8`
- `0x1800a5e58`
- `0x1800ae46c`
- `0x1800b988c`
- `0x1800c0678`
- `0x180132eb0`
- `0x18013d008`
- `0x180158c04`
- `0x1801bfadc`
- `0x1801bfb54`
- `0x1801bfbd0`
- `0x1801bfcc8`
- `0x1801c004c`
- `0x1801c012c`
- `0x1801c014c`
- `0x1801c03fc`
- `0x1801c08ec`
- `0x1801cb4c4`
- `0x1801cbd44`
- `0x180209d8c`
- `0x18022255c`
- `0x1802651ea`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000b3b3`
- `KERNEL32!GetProcAddress` at `0x18000b3b3`
- `KERNEL32!lstrlenW` at `0x180009fae`
- `KERNEL32!lstrlenW` at `0x18000b4d5`
- `KERNEL32!lstrlenW` at `0x18000b531`
- `KERNEL32!lstrlenW` at `0x18000b58d`
- `KERNEL32!lstrlenW` at `0x18000b5e9`
- `KERNEL32!lstrlenW` at `0x18000b642`
- `KERNEL32!lstrlenW` at `0x180009fae`
- `KERNEL32!lstrlenW` at `0x18000b4d5`
- `KERNEL32!lstrlenW` at `0x18000b531`
- `KERNEL32!lstrlenW` at `0x18000b58d`
- `KERNEL32!lstrlenW` at `0x18000b5e9`
- `KERNEL32!lstrlenW` at `0x18000b642`
- `GDI32!RemoveFontResourceW` at `0x18000a458`
- `GDI32!RemoveFontResourceW` at `0x18000a458`
- `GDI32!AddFontResourceW` at `0x18000a29a`
- `GDI32!AddFontResourceW` at `0x18000a29a`

## string_xrefs

- `0x18000a956`: `RESTART MANAGER: Session opened.`
- `0x18000a91a`: `RESTART MANAGER: Failed to open session; Windows Installer will use the built-in FilesInUse functionality. Error: %d`
- `0x18000aa93`: `RESTART MANAGER: Failed to add process ID %d resource; Windows Installer will use the built-in FilesInUse functionality. Error: %d`
- `0x18000ab39`: `RESTART MANAGER: Failed to retrieve the list of applications that hold files in use; Windows Installer will use the built-in FilesInUse functionality. Error: %d`
- `0x18000ae35`: `RESTART MANAGER: Did not detect any app that holds files in use. Windows Installer will use the built-in FilesInUse functionality.`
- `0x18000b06a`: `Install server not responding`
- `0x18000b394`: `MsiHnd.dll`
- `0x18000b3a4`: `DllGetClassObject`

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
  __int64 v59; // rax
  __int64 v60; // rcx
  __int64 v61; // rdi
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
  struct IMsiRecord **p_NoDataRecord; // rcx
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
  struct IMsiRecord *v100; // rsi
  void (__fastcall *v101)(struct IMsiRecord *, _QWORD, __int64); // rdi
  __int64 v102; // rbx
  struct IMsiRecord *v103; // rdi
  void (__fastcall *v104)(struct IMsiRecord *, _QWORD, _QWORD); // rbx
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
                if ( (int)StringCchCopyW(g_rgchScriptInProgress, dword_1803102D0, *(const unsigned __int16 **)(a1 + 8)) < 0 )
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
              if ( (int)StringCchCopyW(g_rgchBannerText, dword_1803102B8, *(const unsigned __int16 **)(a1 + 8)) < 0 )
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
            if ( (int)StringCchCopyW(g_rgchFatalException, dword_1803102A0, *(const unsigned __int16 **)(a1 + 8)) < 0 )
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
          if ( (int)StringCchCopyW(g_rgchFatalTimedOut, dword_180310288, *(const unsigned __int16 **)(a1 + 8)) < 0 )
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
          if ( (int)StringCchCopyW(g_rgchFatalOutOfMemory, dword_180310270, *(const unsigned __int16 **)(a1 + 8)) >= 0 )
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
                 qword_1803138F8,
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
        p_NoDataRecord = &v152;
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
        if ( (v9 & dword_180313928) != 0 )
        {
          NoDataRecord = MsiUIMessageContext::GetNoDataRecord((MsiUIMessageContext *)a1);
          (*(void (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)NoDataRecord + 8LL))(NoDataRecord);
          v120 = *(void (__fastcall **)(struct IMsiRecord *, _QWORD, _QWORD))(*(_QWORD *)NoDataRecord + 120LL);
          v121 = MsiString::MsiString((MsiString *)&v152, *(const unsigned __int16 **)(a1 + 8));
          v120(NoDataRecord, 0, *(_QWORD *)v121);
          (*(void (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)v152 + 16LL))(v152);
          v11 = CMsiAPIMessageRec::Message(g_messageRec, 234881024, NoDataRecord);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&NoDataRecord);
          if ( v11 )
            goto LABEL_40;
          v9 = v154;
        }
        if ( (dword_180313768 & 0x4000) == 0
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
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&NoDataRecord);
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
          if ( (int)StringCchCopyW(g_rgchTimeRemaining, dword_180310258, *(const unsigned __int16 **)(a1 + 8)) >= 0 )
            goto LABEL_40;
        }
        v25 = g_rgchTimeRemaining;
LABEL_321:
        *v25 = 0;
        goto LABEL_40;
      }
      if ( v5 == 251658244 )
      {
        if ( (g_dwLogMode & 0x400) != 0 || (dword_180313768 & 0x10) != 0 || (v106 = 7, (dword_180313928 & 0x10) != 0) )
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
      if ( (v9 & dword_180313928) != 0 )
      {
        NoDataRecord = MsiUIMessageContext::GetNoDataRecord((MsiUIMessageContext *)a1);
        (*(void (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)NoDataRecord + 8LL))(NoDataRecord);
        v114 = *(void (__fastcall **)(struct IMsiRecord *, _QWORD, _QWORD))(*(_QWORD *)NoDataRecord + 120LL);
        v115 = MsiString::MsiString((MsiString *)&v152, v113);
        v114(NoDataRecord, 0, *(_QWORD *)v115);
        (*(void (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)v152 + 16LL))(v152);
        v11 = CMsiAPIMessageRec::Message(g_messageRec, v5, NoDataRecord);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&NoDataRecord);
        if ( v11 )
          goto LABEL_268;
        v9 = v154;
      }
      if ( ((v9 & dword_180313768) == 0 || (v11 = CMsiAPIMessage::Message(g_message, v5, v113)) == 0)
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
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&NoDataRecord);
      }
LABEL_268:
      if ( (g_dwLogMode & 1) != 0 && hObject )
        WriteLog(v113);
      if ( v5 == 251658533 )
      {
        v30 = HIBYTE(dword_18031107E);
        if ( !HIBYTE(dword_18031107E) )
          goto LABEL_271;
        if ( (int)++*(_DWORD *)(a1 + 200) <= 10 )
        {
LABEL_82:
          v31 = 4;
LABEL_128:
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v150);
          return v31;
        }
      }
      v30 = HIBYTE(dword_18031107E);
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
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v150);
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
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v150);
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
          v59 = (*(__int64 (__fastcall **)(struct IMsiRecord *, __int64))(*(_QWORD *)a3 + 64LL))(a3, 4);
          v60 = *(_QWORD *)a3;
          v61 = v59;
          v151 = (void *)v59;
          NoDataRecord = (struct IMsiRecord *)(*(__int64 (__fastcall **)(struct IMsiRecord *, __int64))(v60 + 64))(
                                                a3,
                                                5);
          if ( v61 )
            v34 = (*(unsigned int (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)v61 + 64LL))(v61, v166, 82) != 82;
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
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&NoDataRecord);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v151);
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
          v76 = qword_1803136E0;
          if ( qword_1803136E0 )
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
    p_NoDataRecord = &NoDataRecord;
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
        v100 = v150;
        v101 = *(void (__fastcall **)(struct IMsiRecord *, _QWORD, __int64))(*(_QWORD *)v150 + 120LL);
        v102 = (*(__int64 (__fastcall **)(struct IMsiRecord *, _QWORD))(*(_QWORD *)a3 + 72LL))(a3, 0);
        v101(v100, 0, v102);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v102 + 16LL))(v102);
        v95 = v147;
      }
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&NoDataRecord);
      v99 = v146;
    }
    v103 = v150;
    v146 = v99 + 1;
    v104 = *(void (__fastcall **)(struct IMsiRecord *, _QWORD, _QWORD))(*(_QWORD *)v150 + 120LL);
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
  if ( ((v9 & dword_180313928) == 0 || (v11 = CMsiAPIMessageRec::Message(g_messageRec, v5, a3)) == 0)
    && ((v9 & dword_180313768) == 0
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
  if ( (!HIBYTE(dword_18031107E) && !v11 || v6 == 11 || byte_180311082 && v6 == 6 && !v11)
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
0x180009c38  mov     [rsp-8+arg_18], rbx
0x180009c3d  push    rbp
0x180009c3e  push    rsi
0x180009c3f  push    rdi
0x180009c40  push    r12
0x180009c42  push    r13
0x180009c44  push    r14
0x180009c46  push    r15
0x180009c48  lea     rbp, [rsp-2F0h]
0x180009c50  sub     rsp, 3F0h
0x180009c57  mov     rax, cs:__security_cookie
0x180009c5e  xor     rax, rsp
0x180009c61  mov     [rbp+320h+var_40], rax
0x180009c68  mov     r15, r8
0x180009c6b  mov     [rbp+320h+var_384], edx
0x180009c6e  xor     r8d, r8d
0x180009c71  mov     esi, edx
0x180009c73  and     esi, 1FFFFFFFh
0x180009c79  mov     [rsp+420h+var_3A8], r8
0x180009c7e  mov     r13d, esi
0x180009c81  mov     [rbp+320h+var_37C], esi
0x180009c84  shr     r13d, 18h
0x180009c88  mov     r12, rcx
0x180009c8b  lea     eax, [r8+1]
0x180009c8f  mov     ecx, r13d
0x180009c92  mov     edi, eax
0x180009c94  mov     r14d, edx
0x180009c97  shl     edi, cl
0x180009c99  and     r14d, 40000000h
0x180009ca0  mov     [rbp+320h+var_378], r14d
0x180009ca4  mov     ebx, r8d
0x180009ca7  mov     [rbp+320h+var_380], ebx
0x180009caa  mov     [rbp+320h+var_388], edi
0x180009cad  test    edi, 0F000FFFh
0x180009cb3  jz      loc_180009E6B
0x180009cb9  cmp     [r12+94h], r8b
0x180009cc1  jnz     loc_18000A0DE
0x180009cc7  test    r15, r15
0x180009cca  jz      loc_18000A10A
0x180009cd0  cmp     [r12+0A8h], r8
0x180009cd8  jz      short loc_180009D58
0x180009cda  mov     rax, cs:?g_pEmbeddedUI@@3PEAVCMsiEmbeddedUIManager@@EA; CMsiEmbeddedUIManager * g_pEmbeddedUI
0x180009ce1  test    rax, rax
0x180009ce4  jnz     loc_18000A11D
0x180009cea  mov     rcx, [r12+0A8h]
0x180009cf2  or      esi, r14d
0x180009cf5  mov     r8, r15
0x180009cf8  mov     edx, esi
0x180009cfa  mov     rax, [rcx]
0x180009cfd  mov     rax, [rax+18h]
0x180009d01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d06  mov     ebx, eax
0x180009d08  cmp     eax, 2
0x180009d0b  jnz     short loc_180009D15
0x180009d0d  mov     rcx, r12; this
0x180009d10  call    ?CancelAllSynchronousIo@MsiUIMessageContext@@QEAAIXZ; MsiUIMessageContext::CancelAllSynchronousIo(void)
0x180009d15  mov     rcx, [rsp+420h+var_3A8]
0x180009d1a  test    rcx, rcx
0x180009d1d  jz      short loc_180009D2B
0x180009d1f  mov     rdx, [rcx]
0x180009d22  mov     rax, [rdx+10h]
0x180009d26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d2b  mov     eax, ebx
0x180009d2d  mov     rcx, [rbp+320h+var_40]
0x180009d34  xor     rcx, rsp; StackCookie
0x180009d37  call    __security_check_cookie
0x180009d3c  mov     rbx, [rsp+420h+arg_18]
0x180009d44  add     rsp, 3F0h
0x180009d4b  pop     r15
0x180009d4d  pop     r14
0x180009d4f  pop     r13
0x180009d51  pop     r12
0x180009d53  pop     rdi
0x180009d54  pop     rsi
0x180009d55  pop     rbp
0x180009d56  retn
0x180009d58  mov     r14d, 2
0x180009d5e  cmp     esi, 5000000h
0x180009d64  jz      loc_18000A145
0x180009d6a  cmp     r13d, 18h
0x180009d6e  jz      loc_18000A1F0
0x180009d74  cmp     esi, 19000000h
0x180009d7a  jz      loc_18000A878
0x180009d80  cmp     [rbp+320h+var_378], r8d
0x180009d84  jnz     loc_18000AE73
0x180009d8a  lea     eax, [r13-1]
0x180009d8e  mov     ecx, 1
0x180009d93  cmp     eax, ecx
0x180009d95  jbe     loc_18000A073
0x180009d9b  test    edi, 311h
0x180009da1  jnz     loc_180009EB5
0x180009da7  test    cs:dword_180313928, edi
0x180009dad  jz      short loc_180009DCA
0x180009daf  mov     r8, r15
0x180009db2  lea     rcx, ?g_messageRec@@3VCMsiAPIMessageRec@@A; CMsiAPIMessageRec g_messageRec
0x180009db9  mov     edx, esi
0x180009dbb  call    ?Message@CMsiAPIMessageRec@@QEBA?AW4imsEnum@@W4imtEnum@@AEAVIMsiRecord@@@Z; CMsiAPIMessageRec::Message(imtEnum,IMsiRecord &)
0x180009dc0  mov     ebx, eax
0x180009dc2  test    eax, eax
0x180009dc4  jnz     loc_180009F69
0x180009dca  test    cs:dword_180313768, edi
0x180009dd0  jnz     loc_18000AEA3
0x180009dd6  mov     rax, cs:?g_pEmbeddedUI@@3PEAVCMsiEmbeddedUIManager@@EA; CMsiEmbeddedUIManager * g_pEmbeddedUI
0x180009ddd  xor     ecx, ecx
0x180009ddf  test    rax, rax
0x180009de2  jnz     loc_18000AECD
0x180009de8  cmp     r13d, 1Ah
0x180009dec  jz      loc_18000AEEA
0x180009df2  cmp     r13d, 1Bh
0x180009df6  jz      loc_18000AEEA
0x180009dfc  cmp     byte ptr cs:dword_18031107E+3, cl
0x180009e02  jz      loc_180009EE0
0x180009e08  cmp     r13d, 0Bh
0x180009e0c  jz      loc_180009EE8
0x180009e12  cmp     cs:byte_180311082, cl
0x180009e18  jnz     loc_18000AEF9
0x180009e1e  mov     eax, cs:?g_dwLogMode@@3KA; ulong g_dwLogMode
0x180009e24  and     eax, edi
0x180009e26  test    al, 8Eh
0x180009e28  jnz     loc_18000AF10
0x180009e2e  test    edi, 700h
0x180009e34  jnz     short loc_180009E50
0x180009e36  mov     rcx, [rsp+420h+var_3A8]
0x180009e3b  test    rcx, rcx
0x180009e3e  jz      loc_180009D2B
0x180009e44  mov     rax, [rcx]
0x180009e47  mov     rax, [rax+10h]
0x180009e4b  jmp     loc_180009D26
0x180009e50  cmp     byte ptr [r12+94h], 0
0x180009e59  jz      short loc_180009E36
0x180009e5b  mov     ebx, r14d
0x180009e5e  xor     r14d, r14d
0x180009e61  mov     [r12+94h], r14b
0x180009e69  jmp     short loc_180009E36
0x180009e6b  mov     rcx, [r12+0A8h]
0x180009e73  xor     r14d, r14d
0x180009e76  test    rcx, rcx
0x180009e79  jnz     loc_18000A000
0x180009e7f  cmp     r13d, 11h
0x180009e83  jbe     loc_180009F70
0x180009e89  sub     r13d, 12h
0x180009e8d  jz      loc_18000B638
0x180009e93  sub     r13d, eax
0x180009e96  jz      loc_18000B5DF
0x180009e9c  sub     r13d, eax
0x180009e9f  jz      loc_18000B583
0x180009ea5  cmp     r13d, eax
0x180009ea8  jz      loc_18000B527
0x180009eae  mov     [r12+8], r14
0x180009eb3  jmp     short loc_180009E36
0x180009eb5  cmp     [rbp+320h+var_384], r8d
0x180009eb9  jl      loc_180009DA7
0x180009ebf  test    cs:?g_dwLogMode@@3KA, edi; ulong g_dwLogMode
0x180009ec5  jnz     short loc_180009ED3
0x180009ec7  cmp     esi, 4000010h
0x180009ecd  jnz     loc_180009DA7
0x180009ed3  mov     rcx, r15; struct IMsiRecord *
0x180009ed6  call    ?LogRecord@@YA_NAEAVIMsiRecord@@@Z; LogRecord(IMsiRecord &)
0x180009edb  jmp     loc_180009DA7
0x180009ee0  test    ebx, ebx
0x180009ee2  jnz     loc_180009E08
0x180009ee8  test    edi, 300h
0x180009eee  jz      short loc_180009F0B
0x180009ef0  mov     rax, [r15]
0x180009ef3  xor     edx, edx
0x180009ef5  mov     rcx, r15
0x180009ef8  mov     rax, [rax+20h]
0x180009efc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f01  xor     ecx, ecx
0x180009f03  test    eax, eax
0x180009f05  jnz     loc_180009E1E
0x180009f0b  mov     rcx, [r12+110h]
0x180009f13  test    rcx, rcx
0x180009f16  jz      short loc_180009F2B
0x180009f18  mov     rax, [rcx]
0x180009f1b  mov     r8, r15
0x180009f1e  mov     edx, esi
0x180009f20  mov     rax, [rax+20h]
0x180009f24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f29  mov     ebx, eax
0x180009f2b  xor     ecx, ecx
0x180009f2d  test    ebx, ebx
0x180009f2f  jz      short loc_180009F3B
0x180009f31  cmp     r13d, 0Bh
0x180009f35  jnz     loc_180009E1E
0x180009f3b  mov     r8, r15
0x180009f3e  mov     edx, esi
0x180009f40  call    ?Message@CBasicUI@@QEAA?AW4imsEnum@@W4imtEnum@@AEAVIMsiRecord@@@Z; CBasicUI::Message(imtEnum,IMsiRecord &)
0x180009f45  mov     ebx, eax
0x180009f47  xor     ecx, ecx
0x180009f49  jmp     loc_180009E1E
0x180009f4e  mov     r8, r15
0x180009f51  lea     rcx, ?g_message@@3VCMsiAPIMessage@@A; CMsiAPIMessage g_message
0x180009f58  mov     edx, esi
0x180009f5a  call    ?Message@CMsiAPIMessage@@QEBA?AW4imsEnum@@W4imtEnum@@AEAVIMsiRecord@@@Z; CMsiAPIMessage::Message(imtEnum,IMsiRecord &)
0x180009f5f  mov     ebx, eax
0x180009f61  test    eax, eax
0x180009f63  jz      loc_180009DD6
0x180009f69  xor     ecx, ecx
0x180009f6b  jmp     loc_180009DE8
0x180009f70  jz      loc_18000B4CB
0x180009f76  sub     r13d, 0Ch
0x180009f7a  jz      loc_18000B394
0x180009f80  sub     r13d, eax
0x180009f83  jz      loc_18000B354
0x180009f89  sub     r13d, eax
0x180009f8c  jz      loc_18000B1F0
0x180009f92  sub     r13d, eax
0x180009f95  jz      loc_18000B016
0x180009f9b  cmp     r13d, eax
0x180009f9e  jnz     loc_180009EAE
0x180009fa4  mov     rcx, [r12+8]; lpString
0x180009fa9  test    rcx, rcx
0x180009fac  jz      short loc_180009FF4
0x180009fae  call    cs:__imp_lstrlenW
0x180009fb5  nop     dword ptr [rax+rax+00h]
0x180009fba  xor     r8d, r8d
0x180009fbd  lea     rcx, ?g_rgchTimeRemaining@@3V?$CAPITempBuffer@G$00@@A; CAPITempBuffer<ushort,1> g_rgchTimeRemaining
0x180009fc4  lea     edx, [rax+1]
0x180009fc7  call    ?SetSize@?$CAPITempBuffer@G$00@@QEAA_NH_N@Z; CAPITempBuffer<ushort,1>::SetSize(int,bool)
0x180009fcc  test    al, al
0x180009fce  jz      loc_18000A481
0x180009fd4  movsxd  rdx, cs:dword_180310258; unsigned __int64
0x180009fdb  mov     r8, [r12+8]; unsigned __int16 *
0x180009fe0  mov     rcx, cs:?g_rgchTimeRemaining@@3V?$CAPITempBuffer@G$00@@A; unsigned __int16 *
0x180009fe7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180009fec  test    eax, eax
0x180009fee  jns     loc_180009EAE
0x180009ff4  mov     rax, cs:?g_rgchTimeRemaining@@3V?$CAPITempBuffer@G$00@@A; CAPITempBuffer<ushort,1> g_rgchTimeRemaining
0x180009ffb  jmp     loc_18000B68F
0x18000a000  cmp     r13d, 12h
0x18000a004  jbe     loc_18000AF26
0x18000a00a  sub     r13d, 13h
0x18000a00e  jz      loc_18000AF57
0x18000a014  sub     r13d, eax
0x18000a017  jz      loc_18000AF57
0x18000a01d  sub     r13d, eax
0x18000a020  jz      loc_18000AF57
0x18000a026  sub     r13d, eax
0x18000a029  jnz     loc_18000AFFB
0x18000a02f  xor     eax, eax
0x18000a031  jmp     loc_180009D2D
0x18000a036  mov     r8, r15
0x18000a039  mov     edx, esi
0x18000a03b  call    ?Message@CMsiEmbeddedUIManager@@QEAA?AW4imsEnum@@W4imtEnum@@AEAVIMsiRecord@@@Z; CMsiEmbeddedUIManager::Message(imtEnum,IMsiRecord &)
0x18000a040  mov     ebx, eax
0x18000a042  cmp     eax, 2
0x18000a045  jnz     loc_18000A12E
0x18000a04b  mov     rcx, r12; this
0x18000a04e  call    ?CancelAllSynchronousIo@MsiUIMessageContext@@QEAAIXZ; MsiUIMessageContext::CancelAllSynchronousIo(void)
0x18000a053  mov     rcx, [rsp+420h+var_3A8]
0x18000a058  test    rcx, rcx
0x18000a05b  jz      short loc_18000A069
0x18000a05d  mov     rax, [rcx]
0x18000a060  mov     rax, [rax+10h]
0x18000a064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a069  mov     eax, 2
0x18000a06e  jmp     loc_180009D2D
0x18000a073  cmp     cs:hObject, r8
0x18000a07a  jnz     loc_180009D9B
0x18000a080  mov     dl, cl; bool
0x18000a082  xor     r8d, r8d; struct CEngineMainThreadData *
0x18000a085  mov     rcx, r12; this
0x18000a088  call    ?InitializeLog@MsiUIMessageContext@@AEAA_N_NPEBUCEngineMainThreadData@@@Z; MsiUIMessageContext::InitializeLog(bool,CEngineMainThreadData const *)
0x18000a08d  xor     r8d, r8d
0x18000a090  jmp     loc_180009D9B
0x18000a095  cmp     cs:hObject, r15
0x18000a09c  jz      short loc_18000A0A6
0x18000a09e  mov     rcx, r14; Src
0x18000a0a1  call    ?WriteLog@@YA_NPEBG@Z; WriteLog(ushort const *)
0x18000a0a6  cmp     esi, r13d
0x18000a0a9  jnz     loc_18000B19B
0x18000a0af  mov     al, byte ptr cs:dword_18031107E+3
0x18000a0b5  test    al, al
0x18000a0b7  jz      loc_18000B1A1
0x18000a0bd  inc     dword ptr [r12+0C8h]
0x18000a0c5  cmp     dword ptr [r12+0C8h], 0Ah
0x18000a0ce  jg      loc_18000B19B
0x18000a0d4  mov     edi, 4
0x18000a0d9  jmp     loc_18000A486
0x18000a0de  test    edi, 20000EFh
0x18000a0e4  jz      loc_180009CC7
0x18000a0ea  mov     [r12+94h], r8b
0x18000a0f2  test    al, sil
0x18000a0f5  jz      loc_180009CC7
0x18000a0fb  lea     rcx, [rsp+420h+var_3A8]
0x18000a100  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x18000a105  jmp     loc_18000A069
0x18000a10a  mov     rcx, r12; this
0x18000a10d  call    ?GetNoDataRecord@MsiUIMessageContext@@QEAAPEAVIMsiRecord@@XZ; MsiUIMessageContext::GetNoDataRecord(void)
0x18000a112  mov     r15, rax
0x18000a115  xor     r8d, r8d
0x18000a118  jmp     loc_180009CD0
0x18000a11d  test    [rax+440h], edi
0x18000a123  jz      loc_180009CEA
0x18000a129  jmp     loc_18000A036
0x18000a12e  test    ebx, ebx
0x18000a130  jz      loc_180009CEA
0x18000a136  lea     rcx, [rsp+420h+var_3A8]
0x18000a13b  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
  ... truncated ...
```
