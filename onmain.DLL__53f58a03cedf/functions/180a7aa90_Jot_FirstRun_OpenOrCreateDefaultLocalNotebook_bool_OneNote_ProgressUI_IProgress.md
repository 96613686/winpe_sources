# Jot::FirstRun::OpenOrCreateDefaultLocalNotebook(bool,OneNote::ProgressUI::IProgress *)

- ea: `0x180a7aa90`
- end: `0x180a7c369`
- name: `?OpenOrCreateDefaultLocalNotebook@FirstRun@Jot@@YAX_NPEAUIProgress@ProgressUI@OneNote@@@Z`
- size: `6361`
- prototype: `void __fastcall(Jot::FirstRun *__hidden this, bool, struct OneNote::ProgressUI::IProgress *)`
- caller_count: `1`
- callee_count: `45`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180a84e74`

## callees

- `0x18002efb0`
- `0x18002fcf4`
- `0x1800314b8`
- `0x180032260`
- `0x180045f48`
- `0x1800737a0`
- `0x1800798a0`
- `0x18007d75c`
- `0x18009342c`
- `0x180093480`
- `0x1800943d4`
- `0x1800af0bc`
- `0x1800b4e20`
- `0x1800d9608`
- `0x180140590`
- `0x1801536d4`
- `0x180185350`
- `0x180198a50`
- `0x180198ae0`
- `0x1801a36e0`
- `0x1801b0214`
- `0x18027de34`
- `0x1802a65c0`
- `0x1802b0cb8`
- `0x1802e2190`
- `0x1802e26a0`
- `0x1802e4a58`
- `0x1802e4c00`
- `0x1802e5170`
- `0x1802e5190`
- `0x1803213e0`
- `0x1803bfac4`
- `0x1804811f8`
- `0x1804d1ff8`
- `0x1806ca7a0`
- `0x18079ba70`
- `0x18080ac50`
- `0x180821bd0`
- `0x180830670`
- `0x1808cc080`
- `0x180a77e5c`
- `0x180a7aa90`
- `0x180c3a360`
- `0x180ccadd0`
- `0x180ccb4d8`

## import_xrefs

- `MSVCP140!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180a7b9cb`
- `MSVCP140!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180a7c308`
- `MSVCP140!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180a7b9cb`
- `MSVCP140!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180a7c308`
- `MSVCP140!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180a7b5ef`
- `MSVCP140!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180a7b97d`
- `MSVCP140!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180a7c2c7`
- `MSVCP140!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180a7b5ef`
- `MSVCP140!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180a7b97d`
- `MSVCP140!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180a7c2c7`
- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180a7ab04`
- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180a7ab04`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180a7c176`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180a7c318`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180a7c176`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180a7c318`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180a7b9b0`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180a7c2ed`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180a7b9b0`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180a7c2ed`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180a7ab61`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180a7af96`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180a7ab61`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180a7af96`

## string_xrefs

- `0x180a7bb10`: `FirstRun: Opening existing notebook...`
- `0x180a7ba52`: `FirstRun: Notebook created.`
- `0x180a7ad9e`: `ValidFilePath`
- `0x180a7b509`: `ValidFilePath`
- `0x180a7b6cb`: `ValidFilePath`
- `0x180a7bbe6`: `ValidFilePath`
- `0x180a7bda8`: `ValidFilePath`
- `0x180a7c2ae`: `FirstRun: Quick Notes setup complete.`
- `0x180a7bbff`: `OpeningDefaultLocalNotebook`
- `0x180a7ba8f`: `FirstRun: Unable to create a valid local notebook.`
- `0x180a7be5c`: `NotebookStateOpenedLocalNotebook`
- `0x180a7bdc1`: `AfterOpeningDefaultLocalNotebook`
- `0x180a7c08d`: `FirstRunLocalQuickNoteSetupCompleted`
- `0x180a7b936`: `FirstRun: Failed to create the local notebook folder`
- `0x180a7b6e4`: `AttemptingCreateNewNotebookInDefaultLocalFolder`
- `0x180a7b893`: `NotebookStateCreatedLocalNotebook`
- `0x180a7b071`: `AttemptingMatchNotebookAgainstKnownDefaultNotebook`

## pseudocode

```c
void __fastcall Jot::FirstRun::OpenOrCreateDefaultLocalNotebook(
        Jot::FirstRun *this,
        __int64 a2,
        struct OneNote::ProgressUI::IProgress *a3)
{
  __int64 StringFromTheResourceDll; // rax
  unsigned int v5; // r9d
  struct Jot::IFolderProxy **v6; // rdx
  void (__fastcall *v7)(__int64, __int64 *, _QWORD *, _QWORD, _QWORD, _BYTE); // rbx
  _QWORD *v8; // rax
  __int64 v9; // rax
  __int64 v10; // r15
  __int64 v11; // rax
  bool v12; // r8
  unsigned int v13; // r9d
  void *v14; // rbx
  __int64 v15; // rdi
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rsi
  __int64 v20; // rax
  unsigned __int64 v21; // rsi
  struct OneNote::ProgressUI::IProgress **v22; // rax
  void **v23; // r13
  void **v24; // rax
  void (__fastcall ***v25)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v26; // rax
  _QWORD *v27; // rax
  void (__fastcall ***v28)(_QWORD, GUID *, _QWORD *); // rsi
  _QWORD *v29; // rax
  __int64 v30; // rax
  _QWORD *FolderProxy; // rax
  __int64 v32; // rcx
  bool v33; // si
  _QWORD *v34; // rdx
  __int128 *v35; // rcx
  __int64 v36; // rsi
  __int64 v37; // rcx
  unsigned int v38; // r9d
  _QWORD *v39; // rdx
  __int128 *v40; // rcx
  __int64 v41; // rsi
  __int64 v42; // rcx
  _QWORD *v43; // rdx
  __int128 *v44; // rcx
  __int64 v45; // rsi
  __int64 v46; // rcx
  __int64 v47; // rax
  __int64 v48; // rax
  __int64 v49; // rax
  __int64 v50; // r8
  __int64 v51; // rax
  __int64 v52; // rbx
  unsigned __int8 (__fastcall *v53)(__int64, _QWORD, _QWORD); // rdi
  _QWORD *v54; // rax
  unsigned int v55; // r9d
  const void *v56; // rax
  __int64 v57; // rax
  unsigned int v58; // r9d
  __int64 v59; // rax
  __int64 v60; // rax
  __int64 v61; // r8
  _QWORD *v62; // r8
  unsigned __int64 *v63; // rax
  unsigned __int64 v64; // rcx
  __int64 v65; // rax
  __int64 v66; // rbx
  __int64 (__fastcall *v67)(__int64, __int128 *, unsigned __int64 *, _QWORD, int, int, __int64, char); // rdi
  Jot *v68; // rbx
  unsigned int v69; // r9d
  Jot *v70; // rcx
  Jot *v71; // rbx
  struct Jot::IGraphNode *v72; // rdx
  const void *v73; // rax
  const void *v74; // rax
  Jot *v75; // rbx
  struct Jot::IGraphNode *v76; // rdx
  __int64 v77; // r8
  __int64 *v78; // rax
  __int64 v79; // rbx
  __int64 v80; // rax
  __int64 v81; // rax
  __int64 v82; // rax
  __int64 v83; // rax
  __int64 v84; // r8
  _QWORD *v85; // rax
  Jot *v86; // rbx
  Jot *v87; // rcx
  __int64 *v88; // rax
  __int64 v89; // rax
  __int64 v90; // rax
  char v91; // al
  __int64 v92; // rax
  __int64 v93; // r8
  Jot *v94; // rdi
  struct Jot::IGraphNode *v95; // rdx
  __int64 v96; // rax
  Jot *v97; // rdi
  struct Jot::IGraphNode *v98; // rdx
  __int64 v99; // rdi
  _QWORD *v100; // rax
  __int64 v101; // rax
  __int64 v102; // rax
  unsigned int v103; // r9d
  struct Jot::IGraphNode *v104; // rdx
  struct Jot::IPersistableGraphNode *v105; // rax
  __int64 *v106; // rax
  __int64 v107; // rdi
  unsigned int v108; // r9d
  const wchar_t *v110; // r8
  unsigned int v111; // r9d
  int v112; // [rsp+20h] [rbp-378h]
  int v113; // [rsp+20h] [rbp-378h]
  int v114; // [rsp+20h] [rbp-378h]
  int v115; // [rsp+28h] [rbp-370h]
  int v116; // [rsp+28h] [rbp-370h]
  int v117; // [rsp+28h] [rbp-370h]
  __int64 v118; // [rsp+30h] [rbp-368h]
  _BYTE v119[4]; // [rsp+50h] [rbp-348h] BYREF
  int v120; // [rsp+54h] [rbp-344h] BYREF
  __int64 v121; // [rsp+58h] [rbp-340h] BYREF
  Jot *v122; // [rsp+60h] [rbp-338h] BYREF
  _QWORD v123[2]; // [rsp+68h] [rbp-330h] BYREF
  void **v124; // [rsp+78h] [rbp-320h] BYREF
  const char *v125; // [rsp+80h] [rbp-318h]
  void ***v126; // [rsp+88h] [rbp-310h]
  __int64 v127; // [rsp+90h] [rbp-308h] BYREF
  unsigned __int64 v128; // [rsp+98h] [rbp-300h] BYREF
  __int64 v129; // [rsp+A0h] [rbp-2F8h] BYREF
  __int64 v130; // [rsp+A8h] [rbp-2F0h] BYREF
  __int64 v131; // [rsp+B0h] [rbp-2E8h]
  __int128 v132; // [rsp+B8h] [rbp-2E0h] BYREF
  __m128i si128; // [rsp+C8h] [rbp-2D0h] BYREF
  __int64 v134; // [rsp+D8h] [rbp-2C0h] BYREF
  _BYTE v135[16]; // [rsp+E0h] [rbp-2B8h] BYREF
  _QWORD *v136; // [rsp+F0h] [rbp-2A8h] BYREF
  __int64 v137; // [rsp+F8h] [rbp-2A0h] BYREF
  char ***v138; // [rsp+100h] [rbp-298h] BYREF
  const char *v139; // [rsp+108h] [rbp-290h]
  _BYTE v140[48]; // [rsp+110h] [rbp-288h] BYREF
  _BYTE v141[40]; // [rsp+140h] [rbp-258h] BYREF
  _QWORD v142[2]; // [rsp+168h] [rbp-230h] BYREF
  _QWORD v143[2]; // [rsp+178h] [rbp-220h] BYREF
  _QWORD v144[2]; // [rsp+188h] [rbp-210h] BYREF
  char v145[48]; // [rsp+198h] [rbp-200h] BYREF
  char v146[8]; // [rsp+1C8h] [rbp-1D0h] BYREF
  __int128 v147; // [rsp+1D0h] [rbp-1C8h] BYREF
  __int64 v148; // [rsp+1E0h] [rbp-1B8h]
  unsigned __int64 v149; // [rsp+1E8h] [rbp-1B0h]
  void **v150; // [rsp+1F0h] [rbp-1A8h] BYREF
  void **v151; // [rsp+1F8h] [rbp-1A0h]
  __int64 *v152; // [rsp+200h] [rbp-198h]
  _QWORD v153[3]; // [rsp+210h] [rbp-188h] BYREF
  unsigned __int64 v154; // [rsp+228h] [rbp-170h]
  _QWORD v155[4]; // [rsp+230h] [rbp-168h] BYREF
  _QWORD v156[4]; // [rsp+250h] [rbp-148h] BYREF
  _BYTE pExceptionObject[80]; // [rsp+270h] [rbp-128h] BYREF
  _BYTE v158[80]; // [rsp+2C0h] [rbp-D8h] BYREF
  _BYTE v159[80]; // [rsp+310h] [rbp-88h] BYREF
  char v160; // [rsp+3A0h] [rbp+8h]

  v160 = (char)this;
  StringFromTheResourceDll = Jot::LoadStringFromTheResourceDll(v155, 2070339700);
  OneNote::ProgressUI::CProgressLock::CProgressLock(v135, a2, StringFromTheResourceDll, 3);
  si128 = 0;
  __ExceptionPtrCreate(&si128);
  if ( Jot::ShouldLogTtid((Jot *)0x40A6C7, 0x10168u, 2u, v5) )
    Jot::Log_Impl<wchar_t [63],>((Jot *)0x40A6C7, 0x10168u, 2u);
  v134 = 0;
  if ( !Jot::FGetMyDocumentsFolder((Jot *)&v134, v6) )
  {
    CrashWithRecovery(0x1350195u, 0);
    __debugbreak();
  }
  v7 = *(void (__fastcall **)(__int64, __int64 *, _QWORD *, _QWORD, _QWORD, _BYTE))(*(_QWORD *)v134 + 80LL);
  v8 = (_QWORD *)Jot::LoadStringFromTheResourceDll(&v147, 1258855830);
  if ( v8[3] > 7u )
    v8 = (_QWORD *)*v8;
  v7(v134, &v130, v8, 0, 0, 0);
  std::wstring::~wstring(&v147);
  v9 = Jot::LoadStringFromTheResourceDll(&v150, 3920257527LL);
  OneNote::ProgressUI::CProgressLock::SetWorkTitle(v135, v9);
  Jot::LoadStringFromTheResourceDll(v153, 3863265580LL);
  Jot::LoadStringFromTheResourceDll(v155, 3427458819LL);
  Jot::LoadStringFromTheResourceDll(v156, 2200353092LL);
  v10 = 0;
  v131 = 0;
  v120 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v130 + 24LL))(v130);
  if ( (*(unsigned __int8 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v11 + 80LL))(v11, 0, 600000000) )
  {
    v14 = 0;
    v129 = 0;
    v137 = 0;
    Jot::GetQuickNotesSection((Jot *)&v137, 0, v12);
    v15 = v137;
    if ( v137 )
    {
      Jot::GetThicketFolderForFile_MaybeNull(&v121, v137);
      v16 = v121;
      if ( v121 )
      {
        v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v121 + 24LL))(v121);
        MsoCF::CIPtr<CsiCell::ICellStorage,CsiCell::ICellStorage>::Assign(&v129, v17);
        v14 = (void *)v129;
        v16 = v121;
      }
      if ( v16 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    (*(void (__fastcall **)(__int64, void ***, _QWORD))(*(_QWORD *)v130 + 32LL))(v130, &v150, 0);
    OneNote::ProgressUI::CProgressLock::MakeProgress((OneNote::ProgressUI::CProgressLock *)v135, 1u);
    v18 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v130 + 24LL))(v130);
    (*(void (__fastcall **)(__int64, __int128 *, _QWORD))(*(_QWORD *)v18 + 112LL))(v18, &v147, 0);
    v121 = v151 - v150;
    v19 = Jot::Logging::details::LogDataValidated<unsigned __int64>(v140, "NotebookCount", &v121);
    v119[0] = v148 != 0;
    v20 = Jot::Logging::details::LogDataValidated<bool>(v145, "ValidFilePath", v119);
    *(_QWORD *)&v132 = &off_1811FD410;
    *((_QWORD *)&v132 + 1) = "LocalNotebookFolderRetrieved";
    v123[0] = v20;
    v123[1] = v19;
    v124 = &Mso::Logging::CompositeStructuredTrace::`vftable';
    v125 = (const char *)v123;
    v126 = &v124;
    Jot::Logging::details::SendStructuredTraceTag(504903455, 50, &v132, &v124);
    std::unique_ptr<std::wstring const>::~unique_ptr<std::wstring const,std::default_delete<std::wstring const>>(v146);
    std::unique_ptr<std::wstring const>::~unique_ptr<std::wstring const,std::default_delete<std::wstring const>>(v141);
    std::wstring::~wstring(&v147);
    if ( v150 != v151 )
    {
      v21 = 0x64uLL / (v151 - v150);
      v128 = v21;
      v22 = (struct OneNote::ProgressUI::IProgress **)OneNote::ProgressUI::CProgressLock::CreateChildProgress(
                                                        v135,
                                                        &v136,
                                                        1);
      OneNote::ProgressUI::CProgressLock::CProgressLock((OneNote::ProgressUI::CProgressLock *)&v124, *v22, 0x64u);
      if ( v136 )
        (*(void (__fastcall **)(_QWORD *))(*v136 + 16LL))(v136);
      v23 = v150;
      v24 = v151;
      v123[0] = v151;
      while ( v23 != v24 )
      {
        OneNote::ProgressUI::CProgressLock::MakeProgress((OneNote::ProgressUI::CProgressLock *)&v124, v21);
        if ( (*(unsigned __int8 (__fastcall **)(void *))(*(_QWORD *)*v23 + 176LL))(*v23) )
        {
          if ( (*(unsigned __int8 (__fastcall **)(void *, _QWORD, __int64))(*(_QWORD *)*v23 + 80LL))(*v23, 0, 600000000) )
          {
            v25 = (void (__fastcall ***)(_QWORD, GUID *, __int64 *))*v23;
            if ( *v23 != v14 )
            {
              v26 = 0;
              v127 = 0;
              if ( v25 )
              {
                (**v25)(v25, &GUID_4735b3bf_db6a_44c3_942e_6c16a8b935ce, &v127);
                v26 = v127;
              }
              if ( v26 )
              {
                v27 = (_QWORD *)sub_1800314B8();
                if ( !(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v27 + 152LL))(*v27) )
                {
                  CrashWithRecovery(0x27D00CAu, 0);
                  __debugbreak();
                }
                v28 = (void (__fastcall ***)(_QWORD, GUID *, _QWORD *))*v23;
                v29 = (_QWORD *)sub_1800314B8();
                v30 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v29 + 152LL))(*v29);
                Jot::FindNotebookContaining(&v121, v30, v28);
                if ( !(unsigned __int8)Jot::CNodeRef<Jot::CSemNotebookTrait>::IsValid(&v121) )
                  goto LABEL_33;
                FolderProxy = (_QWORD *)Jot::NotebookEditor::GetFolderProxy(&v132, &v121, 0);
                v32 = v127;
                v33 = v127 != *FolderProxy;
                if ( (_QWORD)v132 )
                {
                  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v132 + 16LL))(v132);
                  v32 = v127;
                }
                if ( v33 )
                {
                  if ( v121 )
                  {
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v121 + 16LL))(v121);
                    v32 = v127;
                  }
                }
                else
                {
LABEL_33:
                  (*(void (__fastcall **)(void *, __int128 *))(*(_QWORD *)*v23 + 128LL))(*v23, &v147);
                  v138 = &off_1811FD410;
                  v139 = "AttemptingMatchNotebookAgainstKnownDefaultNotebook";
                  Jot::Logging::LogTraceTag<>(504903454, &v138, 50);
                  if ( v120 < 4 )
                  {
                    v34 = v153;
                    if ( v154 > 7 )
                      v34 = (_QWORD *)v153[0];
                    v35 = &v147;
                    if ( v149 > 7 )
                      v35 = (__int128 *)v147;
                    if ( (unsigned __int8)MsoCF::AreEqualStrings(v35, v34, 1) )
                    {
                      v138 = &off_1811FD410;
                      v139 = "MatchedAndSelectedDefaultWebNotebook";
                      Jot::Logging::LogTraceTag<>(504903453, &v138, 50);
                      v36 = v127;
                      if ( v127 )
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v127 + 8LL))(v127);
                      v37 = v10;
                      v10 = v36;
                      v131 = v36;
                      if ( v37 )
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
                      v120 = 4;
                      std::wstring::~wstring(&v147);
                      if ( v121 )
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v121 + 16LL))(v121);
                      if ( v127 )
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v127 + 16LL))(v127);
                      break;
                    }
                  }
                  if ( v120 >= 3 )
                    goto LABEL_186;
                  v39 = v156;
                  if ( v156[3] > 7u )
                    v39 = (_QWORD *)v156[0];
                  v40 = &v147;
                  if ( v149 > 7 )
                    v40 = (__int128 *)v147;
                  if ( (unsigned __int8)MsoCF::AreEqualStrings(v40, v39, 1) )
                  {
                    v142[0] = &off_1811FD410;
                    v142[1] = "MatchedAndSelectedDefaultWebNotebookLegacy14";
                    Jot::Logging::LogTraceTag<>(504903452, v142, 50);
                    v41 = v127;
                    if ( v127 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v127 + 8LL))(v127);
                    v42 = v10;
                    v10 = v41;
                    v131 = v41;
                    if ( v42 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
                    v120 = 3;
                  }
                  else
                  {
LABEL_186:
                    if ( v120 >= 2 )
                      goto LABEL_74;
                    v43 = v155;
                    if ( v155[3] > 7u )
                      v43 = (_QWORD *)v155[0];
                    v44 = &v147;
                    if ( v149 > 7 )
                      v44 = (__int128 *)v147;
                    if ( (unsigned __int8)MsoCF::AreEqualStrings(v44, v43, 1) )
                    {
                      v143[0] = &off_1811FD410;
                      v143[1] = "MatchedAndSelectedDefaultWebNotebookLegacy15B1";
                      Jot::Logging::LogTraceTag<>(504903451, v143, 50);
                      v45 = v127;
                      if ( v127 )
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v127 + 8LL))(v127);
                      v46 = v10;
                      v10 = v45;
                      v131 = v45;
                      if ( v46 )
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
                      v120 = 2;
                    }
                    else
                    {
LABEL_74:
                      v144[0] = &off_1811FD410;
                      v144[1] = "NoDefaultNotebookMatchOrBetterPreviousMatch";
                      Jot::Logging::LogTraceTag<>(504903450, v144, 50);
                    }
                  }
                  std::wstring::~wstring(&v147);
                  if ( v121 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v121 + 16LL))(v121);
                  v32 = v127;
                }
                if ( v32 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
                LODWORD(v21) = v128;
              }
            }
          }
        }
        ++v23;
        v24 = (void **)v123[0];
      }
      OneNote::ProgressUI::CProgressLock::~CProgressLock((OneNote::ProgressUI::CProgressLock *)&v124);
    }
    std::vector<MsoCF::CIRef<Jot::IFolderProxy>>::~vector<MsoCF::CIRef<Jot::IFolderProxy>>(&v150);
    if ( v15 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    if ( v14 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v14 + 16LL))(v14);
  }
  else if ( Jot::ShouldLogTtid((Jot *)0x40A6D7, 0x10168u, 2u, v13) )
  {
    Jot::Log_Impl<wchar_t [63],>((Jot *)0x40A6D7, 0x10168u, 2u);
  }
  v122 = 0;
  if ( v10 )
  {
    if ( Jot::ShouldLogTtid((Jot *)0x40A705, 0x10168u, 2u, v38) )
      Jot::Log_Impl<wchar_t [79],>((Jot *)0x40A705, 0x10168u);
    v80 = Jot::LoadStringFromTheResourceDll(&v147, 288398267);
    OneNote::ProgressUI::CProgressLock::SetWorkTitle(v135, v80);
    v147 = 0;
    v148 = 0;
    v149 = 7;
    LOWORD(v147) = 0;
    v81 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 24LL))(v10);
    v82 = (*(__int64 (__fastcall **)(__int64, void ***, _QWORD))(*(_QWORD *)v81 + 112LL))(v81, &v150, 0);
    std::wstring::operator=(&v147, v82);
    std::wstring::~wstring(&v150);
    v119[0] = v148 != 0;
    v83 = Jot::Logging::details::LogDataValidated<bool>(v140, "ValidFilePath", v119);
    v124 = (void **)&off_1811FD410;
    v125 = "OpeningDefaultLocalNotebook";
    Jot::Logging::LogTraceTag<Jot::Logging::details::StructuredTraceKeyHolder<Jot::Logging::details::StructuredTraceImplementation<bool>,bool>>(
      504903446,
      &v124,
      v84,
      v83);
    std::unique_ptr<std::wstring const>::~unique_ptr<std::wstring const,std::default_delete<std::wstring const>>(v141);
    std::wstring::~wstring(&v147);
    v85 = (_QWORD *)sub_1800314B8();
    LOBYTE(v115) = 1;
    LOBYTE(v112) = 0;
    v86 = *(Jot **)(*(__int64 (__fastcall **)(_QWORD, _QWORD *, __int64, _QWORD, int, int, char, char, _QWORD))(*(_QWORD *)*v85 + 360LL))(
                     *v85,
                     v123,
                     v10,
                     0,
                     v112,
                     v115,
                     1,
                     1,
                     0);
    MsoCF::CIPtr<Jot::IGraphNode,Jot::IGraphNode>::AddRef(v86);
    v87 = v122;
    v122 = v86;
    if ( v87 )
      (*(void (__fastcall **)(Jot *))(*(_QWORD *)v87 + 16LL))(v87);
    if ( v123[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v123[0] + 16LL))(v123[0]);
    v88 = (__int64 *)Jot::NotebookEditor::GetFolderProxy(v123, &v122, 0);
    v79 = *v88;
    *v88 = 0;
    v131 = v79;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    if ( v123[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v123[0] + 16LL))(v123[0]);
    v147 = 0;
    v148 = 0;
    v149 = 7;
    LOWORD(v147) = 0;
    if ( !v79
      || (v89 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v79 + 24LL))(v79),
          v90 = (*(__int64 (__fastcall **)(__int64, void ***, _QWORD))(*(_QWORD *)v89 + 112LL))(v89, &v150, 0),
          std::wstring::operator=(&v147, v90),
          std::wstring::~wstring(&v150),
          v91 = 1,
          !v148) )
    {
      v91 = 0;
    }
    v119[0] = v91;
    v92 = Jot::Logging::details::LogDataValidated<bool>(v140, "ValidFilePath", v119);
    v124 = (void **)&off_1811FD410;
    v125 = "AfterOpeningDefaultLocalNotebook";
    Jot::Logging::LogTraceTag<Jot::Logging::details::StructuredTraceKeyHolder<Jot::Logging::details::StructuredTraceImplementation<bool>,bool>>(
      504903445,
      &v124,
      v93,
      v92);
    std::unique_ptr<std::wstring const>::~unique_ptr<std::wstring const,std::default_delete<std::wstring const>>(v141);
    std::wstring::~wstring(&v147);
  }
  else
  {
    if ( Jot::ShouldLogTtid((Jot *)0x40A6D9, 0x10168u, 2u, v38) )
      Jot::Log_Impl<wchar_t [63],>((Jot *)0x40A6D9, 0x10168u, 2u);
    v47 = Jot::LoadStringFromTheResourceDll(&v147, 1715752470);
    OneNote::ProgressUI::CProgressLock::SetWorkTitle(v135, v47);
    v48 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v130 + 24LL))(v130);
    (*(void (__fastcall **)(__int64, __int128 *, _QWORD))(*(_QWORD *)v48 + 112LL))(v48, &v147, 0);
    v119[0] = v148 != 0;
    v49 = Jot::Logging::details::LogDataValidated<bool>(v140, "ValidFilePath", v119);
    v124 = (void **)&off_1811FD410;
    v125 = "EnsureLocalNotebookFolderExist";
    Jot::Logging::LogTraceTag<Jot::Logging::details::StructuredTraceKeyHolder<Jot::Logging::details::StructuredTraceImplementation<bool>,bool>>(
      504903449,
      &v124,
      v50,
      v49);
    std::unique_ptr<std::wstring const>::~unique_ptr<std::wstring const,std::default_delete<std::wstring const>>(v141);
    std::wstring::~wstring(&v147);
    v51 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v130 + 24LL))(v130);
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v51 + 56LL))(v51, &v121);
    v52 = v121;
    v53 = *(unsigned __int8 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v121 + 72LL);
    v54 = (_QWORD *)MsoCF::CTickCountBase<Jot::GetTickCountAPIs>::After(v123, 600000000);
    if ( !v53(v52, *v54, 0)
      || !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v121 + 32LL))(v121)
      || (v56 = (const void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v121 + 80LL))(v121),
          __ExceptionPtrToBool(v56)) )
    {
      if ( Jot::ShouldLogTtid((Jot *)0x40A6DD, 0x10168u, 2u, v55) )
        Jot::Log_Impl<wchar_t [63],>((Jot *)0x40A6DD, 0x10168u, 2u);
      if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v121 + 32LL))(v121) )
      {
        v73 = (const void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v121 + 80LL))(v121);
        if ( __ExceptionPtrToBool(v73) )
        {
          v74 = (const void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v121 + 80LL))(v121);
          v132 = 0;
          __ExceptionPtrCopy(&v132, v74);
          v123[0] = &v132;
          __ExceptionPtrRethrow(&v132);
        }
      }
      Jot::ErrNotebookManagement_NewNotebookFailed::ErrNotebookManagement_NewNotebookFailed(v158, 17080972);
      throw (Jot::ErrNotebookManagement_NewNotebookFailed *)v158;
    }
    v57 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v130 + 24LL))(v130);
    if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v57 + 64LL))(v57) )
    {
      if ( Jot::ShouldLogTtid((Jot *)0x40A6DF, 0x10168u, 2u, v58) )
        Jot::Log_Impl<wchar_t [63],>((Jot *)0x40A6DF, 0x10168u, 2u);
      Jot::ErrNotebookManagement_NewNotebookFailed::ErrNotebookManagement_NewNotebookFailed(pExceptionObject, 17080973);
      throw (Jot::ErrNotebookManagement_NewNotebookFailed *)pExceptionObject;
    }
    v59 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v130 + 24LL))(v130);
    (*(void (__fastcall **)(__int64, __int128 *, _QWORD))(*(_QWORD *)v59 + 112LL))(v59, &v147, 0);
    v119[0] = v148 != 0;
    v60 = Jot::Logging::details::LogDataValidated<bool>(v140, "ValidFilePath", v119);
    v124 = (void **)&off_1811FD410;
    v125 = "AttemptingCreateNewNotebookInDefaultLocalFolder";
    Jot::Logging::LogTraceTag<Jot::Logging::details::StructuredTraceKeyHolder<Jot::Logging::details::StructuredTraceImplementation<bool>,bool>>(
      504903448,
      &v124,
      v61,
      v60);
    std::unique_ptr<std::wstring const>::~unique_ptr<std::wstring const,std::default_delete<std::wstring const>>(v141);
    std::wstring::~wstring(&v147);
    v62 = v153;
    if ( v154 > 7 )
      v62 = (_QWORD *)v153[0];
    LOBYTE(v115) = 0;
    v63 = (unsigned __int64 *)(*(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD *, _QWORD, _QWORD, int))(*(_QWORD *)v130 + 80LL))(
                                v130,
                                v123,
                                v62,
                                0,
                                0,
                                v115);
    v128 = 0;
    v64 = *v63;
    *v63 = 0;
    v128 = v64;
    if ( v123[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v123[0] + 16LL))(v123[0]);
    v65 = sub_1800314B8();
    v66 = *(_QWORD *)v65;
    v67 = *(__int64 (__fastcall **)(__int64, __int128 *, unsigned __int64 *, _QWORD, int, int, __int64, char))(**(_QWORD **)v65 + 312LL);
    v118 = *(_QWORD *)OneNote::ProgressUI::CProgressLock::CreateChildProgress(v135, &v136, 1);
    LOBYTE(v116) = 0;
    LOBYTE(v113) = 0;
    v68 = *(Jot **)v67(v66, &v132, &v128, 0, v113, v116, v118, 1);
    MsoCF::CIPtr<Jot::IGraphNode,Jot::IGraphNode>::AddRef(v68);
    v70 = v122;
    v122 = v68;
    if ( v70 )
      (*(void (__fastcall **)(Jot *))(*(_QWORD *)v70 + 16LL))(v70);
    if ( (_QWORD)v132 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v132 + 16LL))(v132);
    if ( v136 )
      (*(void (__fastcall **)(_QWORD *))(*v136 + 16LL))(v136);
    v71 = v122;
    if ( v122
      && (*(unsigned __int8 (__fastcall **)(Jot *))(*(_QWORD *)v122 + 168LL))(v122)
      && !Jot::GraphSpaceEditor::IsMarkedForPendingDelete(v71, v72) )
    {
      v124 = (void **)&off_1811FD410;
      v125 = "NotebookStateCreatedLocalNotebook";
      Jot::Logging::LogTraceTag<>(587792585, &v124, 50);
      LODWORD(v129) = Jot::ThemeColors::GetColor(9);
      BYTE4(v129) = 1;
      Jot::NotebookEditor::SetColor(&v122, v129);
    }
    if ( v128 )
      (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v128 + 16LL))(v128);
    if ( v121 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v121 + 16LL))(v121);
    v75 = v122;
    if ( v122
      && (*(unsigned __int8 (__fastcall **)(Jot *))(*(_QWORD *)v122 + 168LL))(v122)
      && !Jot::GraphSpaceEditor::IsMarkedForPendingDelete(v75, v76) )
    {
      if ( Jot::ShouldLogTtid((Jot *)0x40A701, 0x10168u, 2u, v69) )
        Jot::Log_Impl<wchar_t [63],>((Jot *)0x40A701, 0x10168u, 2u);
    }
    else if ( Jot::ShouldLogTtid((Jot *)0x40A703, 0x10168u, 2u, v69) )
    {
      Jot::Log_Impl<wchar_t [79],>((Jot *)0x40A703, 0x10168u);
    }
    LOBYTE(v77) = 1;
    v78 = (__int64 *)Jot::NotebookEditor::GetFolderProxy(v123, &v122, v77);
    v79 = *v78;
    *v78 = 0;
    v131 = v79;
    if ( v123[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v123[0] + 16LL))(v123[0]);
  }
  v94 = v122;
  if ( v122
    && (*(unsigned __int8 (__fastcall **)(Jot *))(*(_QWORD *)v122 + 168LL))(v122)
    && !Jot::GraphSpaceEditor::IsMarkedForPendingDelete(v94, v95) )
  {
    v96 = Jot::Logging::details::LogDataValidated<int>(v140, "MatchLevel", &v120);
    v124 = (void **)&off_1811FD410;
    v125 = "NotebookStateOpenedLocalNotebook";
    v129 = v96;
    v150 = &Mso::Logging::CompositeStructuredTrace::`vftable';
    v151 = (void **)&v129;
    v152 = &v130;
    Jot::Logging::details::SendStructuredTraceTag(587792584, 50, &v124, &v150);
    std::unique_ptr<std::wstring const>::~unique_ptr<std::wstring const,std::default_delete<std::wstring const>>(v141);
  }
  OneNote::ProgressUI::CProgressLock::MakeProgress((OneNote::ProgressUI::CProgressLock *)v135, 1u);
  v97 = v122;
  if ( !v122
    || !(*(unsigned __int8 (__fastcall **)(Jot *))(*(_QWORD *)v122 + 168LL))(v122)
    || Jot::GraphSpaceEditor::IsMarkedForPendingDelete(v97, v98) )
  {
    Jot::ErrNotebookManagement_NewNotebookFailed::ErrNotebookManagement_NewNotebookFailed(v159, 17080975);
    throw (Jot::ErrNotebookManagement_NewNotebookFailed *)v159;
  }
  v136 = v123;
  v99 = Jot::CNodeRef<Jot::CSemPageContentTrait>::CNodeRef<Jot::CSemPageContentTrait>(v123, &v122);
  v100 = (_QWORD *)sub_1800314B8();
  v101 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v100 + 160LL))(*v100, &v132);
  Jot::RootEditor::SetLastViewedNotebook(v101, v99);
  v102 = Jot::LoadStringFromTheResourceDll(&v147, 1925444872);
  OneNote::ProgressUI::CProgressLock::SetWorkTitle(v135, v102);
  if ( !v160 )
    goto LABEL_167;
  if ( Jot::ShouldLogTtid((Jot *)0x40A711, 0x10168u, 2u, v103) )
    Jot::Log_Impl<wchar_t [63],>((Jot *)0x40A711, 0x10168u, 2u);
  v105 = Jot::AsPersistableGraphNode(v122, v104);
  (*(void (__fastcall **)(struct Jot::IPersistableGraphNode *, __int64 *))(*(_QWORD *)v105 + 56LL))(v105, &v129);
  if ( v129 )
  {
    LOBYTE(v117) = 0;
    LOBYTE(v114) = 0;
    v106 = (__int64 *)(*(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD, _QWORD, int, int))(*(_QWORD *)v129 + 80LL))(
                        v129,
                        v123,
                        0,
                        0,
                        v114,
                        v117);
    v107 = *v106;
    *v106 = 0;
    *(_QWORD *)&v132 = v107;
    if ( v123[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v123[0] + 16LL))(v123[0]);
    v124 = (void **)&off_1811FD410;
    v125 = "FirstRunLocalQuickNoteSetupQueued";
    Jot::Logging::LogTraceTag<>(509112527, &v124, 50);
    Jot::QuickNotes::BeginUpdateQuickNotesLocationFirstRun(v107, &v122);
    v124 = (void **)&off_1811FD410;
    v125 = "FirstRunLocalQuickNoteSetupCompleted";
    Jot::Logging::LogTraceTag<>(509112526, &v124, 50);
    if ( v107 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v107 + 16LL))(v107);
    if ( v129 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v129 + 16LL))(v129);
    if ( v122 )
      (*(void (__fastcall **)(Jot *))(*(_QWORD *)v122 + 16LL))(v122);
    if ( v79 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
    std::wstring::~wstring(v156);
    std::wstring::~wstring(v155);
    std::wstring::~wstring(v153);
    if ( v130 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v130 + 16LL))(v130);
    if ( v134 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v134 + 16LL))(v134);
  }
  else
  {
LABEL_167:
    if ( v122 )
      (*(void (__fastcall **)(Jot *))(*(_QWORD *)v122 + 16LL))(v122);
    if ( v79 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
    std::wstring::~wstring(v156);
    std::wstring::~wstring(v155);
    std::wstring::~wstring(v153);
    if ( v130 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v130 + 16LL))(v130);
    if ( v134 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v134 + 16LL))(v134);
    if ( Jot::ShouldLogTtid((Jot *)0x2375C782, 0x10168u, 2u, v108) )
      Jot::Log_Impl<wchar_t [79],>((Jot *)0x2375C782, 0x10168u);
    Jot::QuickNotes::EnsureQuickNotesSetupInternal(0, 0, v110);
    if ( Jot::ShouldLogTtid((Jot *)0x2375C781, 0x10168u, 2u, v111) )
      Jot::Log_Impl<wchar_t [38],>((Jot *)0x2375C781);
    if ( __ExceptionPtrToBool(&si128) )
    {
      v132 = 0;
      __ExceptionPtrCopy(&v132, &si128);
      v123[0] = &v132;
      __ExceptionPtrRethrow(&v132);
    }
  }
  __ExceptionPtrDestroy(&si128);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  OneNote::ProgressUI::CProgressLock::~CProgressLock((OneNote::ProgressUI::CProgressLock *)v135);
}

```

## disassembly

```asm
0x180a7aa90  mov     [rsp+arg_10], rbx
0x180a7aa95  mov     [rsp+arg_18], rsi
0x180a7aa9a  mov     [rsp+arg_0], cl
0x180a7aa9e  push    rdi
0x180a7aa9f  push    r12
0x180a7aaa1  push    r13
0x180a7aaa3  push    r14
0x180a7aaa5  push    r15
0x180a7aaa7  sub     rsp, 370h
0x180a7aaae  mov     rax, cs:__security_cookie
0x180a7aab5  xor     rax, rsp
0x180a7aab8  mov     [rsp+398h+var_38], rax
0x180a7aac0  mov     rbx, rdx
0x180a7aac3  xor     r14d, r14d
0x180a7aac6  mov     edx, 7B66E074h
0x180a7aacb  lea     rcx, [rsp+398h+var_168]
0x180a7aad3  call    ?LoadStringFromTheResourceDll@Jot@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z; Jot::LoadStringFromTheResourceDll(uint)
0x180a7aad8  lea     r9d, [r14+3]
0x180a7aadc  mov     r8, rax
0x180a7aadf  mov     rdx, rbx
0x180a7aae2  lea     rcx, [rsp+398h+var_2B8]
0x180a7aaea  call    ??0CProgressLock@ProgressUI@OneNote@@QEAA@PEAUIProgress@12@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z; OneNote::ProgressUI::CProgressLock::CProgressLock(OneNote::ProgressUI::IProgress *,std::wstring,uint)
0x180a7aaef  nop
0x180a7aaf0  xorps   xmm0, xmm0
0x180a7aaf3  movdqu  [rsp+398h+var_2D0], xmm0
0x180a7aafc  lea     rcx, [rsp+398h+var_2D0]
0x180a7ab04  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180a7ab0a  mov     edx, 10168h; unsigned int
0x180a7ab0f  mov     ebx, 40A6C7h
0x180a7ab14  lea     r8d, [r14+2]; unsigned int
0x180a7ab18  mov     ecx, ebx; this
0x180a7ab1a  call    ?ShouldLogTtid@Jot@@YA_NKII@Z; Jot::ShouldLogTtid(ulong,uint,uint)
0x180a7ab1f  nop
0x180a7ab20  test    al, al
0x180a7ab22  jz      short loc_180A7AB3C
0x180a7ab24  lea     r9, aFirstrunRetrei; "FirstRun: Retreiving local notebook fol"...
0x180a7ab2b  mov     edx, 10168h; unsigned int
0x180a7ab30  lea     r8d, [r14+2]; unsigned int
0x180a7ab34  mov     ecx, ebx; this
0x180a7ab36  call    ??$Log_Impl@$$BY0DP@_W$$V@Jot@@YAXKIW4LogMessageSeverity@0@AEAY0DP@$$CB_W@Z; Jot::Log_Impl<wchar_t [63],>(ulong,uint,Jot::LogMessageSeverity,wchar_t const (&)[63])
0x180a7ab3b  nop
0x180a7ab3c  jmp     short loc_180A7AB41
0x180a7ab3e  xor     r14d, r14d
0x180a7ab41  mov     [rsp+398h+var_2C0], r14
0x180a7ab49  lea     rcx, [rsp+398h+var_2C0]; this
0x180a7ab51  call    ?FGetMyDocumentsFolder@Jot@@YA_NPEAPEAUIFolderProxy@1@@Z; Jot::FGetMyDocumentsFolder(Jot::IFolderProxy * *)
0x180a7ab56  test    al, al
0x180a7ab58  jnz     short loc_180A7AB68
0x180a7ab5a  xor     edx, edx
0x180a7ab5c  mov     ecx, 1350195h
0x180a7ab61  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180a7ab67  int     3; Trap to Debugger
0x180a7ab68  mov     rax, [rsp+398h+var_2C0]
0x180a7ab70  mov     rcx, [rax]
0x180a7ab73  mov     rbx, [rcx+50h]
0x180a7ab77  mov     edx, 4B089D96h
0x180a7ab7c  lea     rcx, [rsp+398h+var_1C8]
0x180a7ab84  call    ?LoadStringFromTheResourceDll@Jot@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z; Jot::LoadStringFromTheResourceDll(uint)
0x180a7ab89  nop
0x180a7ab8a  cmp     qword ptr [rax+18h], 7
0x180a7ab8f  jbe     short loc_180A7AB94
0x180a7ab91  mov     rax, [rax]
0x180a7ab94  mov     [rsp+398h+var_370], r14b
0x180a7ab99  mov     [rsp+398h+var_378], r14
0x180a7ab9e  xor     r9d, r9d
0x180a7aba1  mov     r8, rax
0x180a7aba4  lea     rdx, [rsp+398h+var_2F0]
0x180a7abac  mov     rcx, [rsp+398h+var_2C0]
0x180a7abb4  mov     rax, rbx
0x180a7abb7  call    cs:__guard_dispatch_icall_fptr
0x180a7abbd  nop
0x180a7abbe  lea     rcx, [rsp+398h+var_1C8]; void *
0x180a7abc6  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180a7abcb  mov     edx, 0E9AA61F7h
0x180a7abd0  lea     rcx, [rsp+398h+var_1A8]
0x180a7abd8  call    ?LoadStringFromTheResourceDll@Jot@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z; Jot::LoadStringFromTheResourceDll(uint)
0x180a7abdd  mov     rdx, rax
0x180a7abe0  lea     rcx, [rsp+398h+var_2B8]
0x180a7abe8  call    ?SetWorkTitle@CProgressLock@ProgressUI@OneNote@@QEAAXV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; OneNote::ProgressUI::CProgressLock::SetWorkTitle(std::wstring)
0x180a7abed  mov     edx, 0E644C12Ch
0x180a7abf2  lea     rcx, [rsp+398h+var_188]
0x180a7abfa  call    ?LoadStringFromTheResourceDll@Jot@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z; Jot::LoadStringFromTheResourceDll(uint)
0x180a7abff  nop
0x180a7ac00  mov     edx, 0CC4ADF03h
0x180a7ac05  lea     rcx, [rsp+398h+var_168]
0x180a7ac0d  call    ?LoadStringFromTheResourceDll@Jot@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z; Jot::LoadStringFromTheResourceDll(uint)
0x180a7ac12  nop
0x180a7ac13  mov     edx, 8326B944h
0x180a7ac18  lea     rcx, [rsp+398h+var_148]
0x180a7ac20  call    ?LoadStringFromTheResourceDll@Jot@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z; Jot::LoadStringFromTheResourceDll(uint)
0x180a7ac25  nop
0x180a7ac26  mov     r15, r14
0x180a7ac29  mov     [rsp+398h+var_2E8], r14
0x180a7ac31  mov     [rsp+398h+var_344], r14d
0x180a7ac36  mov     rcx, [rsp+398h+var_2F0]
0x180a7ac3e  mov     rax, [rcx]
0x180a7ac41  mov     rax, [rax+18h]
0x180a7ac45  call    cs:__guard_dispatch_icall_fptr
0x180a7ac4b  mov     r9, rax
0x180a7ac4e  mov     rcx, [rax]
0x180a7ac51  mov     rax, [rcx+50h]
0x180a7ac55  xor     edx, edx
0x180a7ac57  mov     r8d, 23C34600h
0x180a7ac5d  mov     rcx, r9
0x180a7ac60  call    cs:__guard_dispatch_icall_fptr
0x180a7ac66  test    al, al
0x180a7ac68  jz      loc_180A7B3FF
0x180a7ac6e  mov     rbx, r14
0x180a7ac71  mov     [rsp+398h+var_2F8], rbx
0x180a7ac79  mov     [rsp+398h+var_2A0], r14
0x180a7ac81  xor     edx, edx; struct Jot::IFileProxy **
0x180a7ac83  lea     rcx, [rsp+398h+var_2A0]; this
0x180a7ac8b  call    ?GetQuickNotesSection@Jot@@YAXPEAPEAUIFileProxy@1@_N@Z; Jot::GetQuickNotesSection(Jot::IFileProxy * *,bool)
0x180a7ac90  mov     rdi, [rsp+398h+var_2A0]
0x180a7ac98  test    rdi, rdi
0x180a7ac9b  jz      short loc_180A7ACF1
0x180a7ac9d  mov     rdx, rdi
0x180a7aca0  lea     rcx, [rsp+398h+var_340]
0x180a7aca5  call    ?GetThicketFolderForFile_MaybeNull@Jot@@YA?AV?$CIPtr@UIFolderProxy@Jot@@U12@@MsoCF@@PEAUIFileProxy@1@@Z; Jot::GetThicketFolderForFile_MaybeNull(Jot::IFileProxy *)
0x180a7acaa  nop
0x180a7acab  mov     rcx, [rsp+398h+var_340]
0x180a7acb0  test    rcx, rcx
0x180a7acb3  jz      short loc_180A7ACDF
0x180a7acb5  mov     rax, [rcx]
0x180a7acb8  mov     rax, [rax+18h]
0x180a7acbc  call    cs:__guard_dispatch_icall_fptr
0x180a7acc2  mov     rdx, rax
0x180a7acc5  lea     rcx, [rsp+398h+var_2F8]
0x180a7accd  call    ?Assign@?$CIPtr@UICellStorage@CsiCell@@U12@@MsoCF@@QEAAXPEAUICellStorage@CsiCell@@@Z; MsoCF::CIPtr<CsiCell::ICellStorage,CsiCell::ICellStorage>::Assign(CsiCell::ICellStorage *)
0x180a7acd2  mov     rbx, [rsp+398h+var_2F8]
0x180a7acda  mov     rcx, [rsp+398h+var_340]
0x180a7acdf  test    rcx, rcx
0x180a7ace2  jz      short loc_180A7ACF1
0x180a7ace4  mov     rax, [rcx]
0x180a7ace7  mov     rax, [rax+10h]
0x180a7aceb  call    cs:__guard_dispatch_icall_fptr
0x180a7acf1  mov     rcx, [rsp+398h+var_2F0]
0x180a7acf9  mov     rax, [rcx]
0x180a7acfc  xor     r8d, r8d
0x180a7acff  lea     rdx, [rsp+398h+var_1A8]
0x180a7ad07  mov     rax, [rax+20h]
0x180a7ad0b  call    cs:__guard_dispatch_icall_fptr
0x180a7ad11  nop
0x180a7ad12  mov     edx, 1; unsigned int
0x180a7ad17  lea     rcx, [rsp+398h+var_2B8]; this
0x180a7ad1f  call    ?MakeProgress@CProgressLock@ProgressUI@OneNote@@UEAAXI@Z; OneNote::ProgressUI::CProgressLock::MakeProgress(uint)
0x180a7ad24  mov     rcx, [rsp+398h+var_2F0]
0x180a7ad2c  mov     rax, [rcx]
0x180a7ad2f  mov     rax, [rax+18h]
0x180a7ad33  call    cs:__guard_dispatch_icall_fptr
0x180a7ad39  mov     r9, rax
0x180a7ad3c  mov     rcx, [rax]
0x180a7ad3f  mov     rax, [rcx+70h]
0x180a7ad43  xor     r8d, r8d
0x180a7ad46  lea     rdx, [rsp+398h+var_1C8]
0x180a7ad4e  mov     rcx, r9
0x180a7ad51  call    cs:__guard_dispatch_icall_fptr
0x180a7ad57  mov     rax, [rsp+398h+var_1A0]
0x180a7ad5f  sub     rax, [rsp+398h+var_1A8]
0x180a7ad67  sar     rax, 3
0x180a7ad6b  mov     [rsp+398h+var_340], rax
0x180a7ad70  lea     r8, [rsp+398h+var_340]
0x180a7ad75  lea     rdx, aNotebookcount_0; "NotebookCount"
0x180a7ad7c  lea     rcx, [rsp+398h+var_288]
0x180a7ad84  call    ??$LogDataValidated@_K@details@Logging@Jot@@YA?A_PPEBDAEB_KW4DataClassifications@1Mso@@@Z
0x180a7ad89  mov     rsi, rax
0x180a7ad8c  cmp     [rsp+398h+var_1B8], r14
0x180a7ad94  setnz   [rsp+398h+var_348]
0x180a7ad99  lea     r8, [rsp+398h+var_348]
0x180a7ad9e  lea     rdx, aValidfilepath; "ValidFilePath"
0x180a7ada5  lea     rcx, [rsp+398h+var_200]
0x180a7adad  call    ??$LogDataValidated@_N@details@Logging@Jot@@YA?A_PPEBDAEB_NW4DataClassifications@1Mso@@@Z
0x180a7adb2  lea     r12, off_1811FD410
0x180a7adb9  mov     qword ptr [rsp+398h+var_2E0], r12
0x180a7adc1  lea     rcx, aLocalnotebookf; "LocalNotebookFolderRetrieved"
0x180a7adc8  mov     qword ptr [rsp+398h+var_2E0+8], rcx
0x180a7add0  mov     [rsp+398h+var_330], rax
0x180a7add5  mov     [rsp+398h+var_328], rsi
0x180a7adda  lea     rsi, ??_7CompositeStructuredTrace@Logging@Mso@@6B@; const Mso::Logging::CompositeStructuredTrace::`vftable'
0x180a7ade1  mov     [rsp+398h+var_320], rsi
0x180a7ade6  lea     rax, [rsp+398h+var_330]
0x180a7adeb  mov     [rsp+398h+var_318], rax
0x180a7adf3  lea     rax, [rsp+398h+var_320]
0x180a7adf8  mov     [rsp+398h+var_310], rax
0x180a7ae00  lea     r9, [rsp+398h+var_320]
0x180a7ae05  lea     r8, [rsp+398h+var_2E0]
0x180a7ae0d  mov     edx, 32h ; '2'
0x180a7ae12  mov     ecx, 1E18371Fh
0x180a7ae17  call    ?SendStructuredTraceTag@details@Logging@Jot@@YAXKW4Severity@2Mso@@AEBUEventName@Telemetry@5@AEBUIStructuredTrace@25@@Z; Jot::Logging::details::SendStructuredTraceTag(ulong,Mso::Logging::Severity,Mso::Telemetry::EventName const &,Mso::Logging::IStructuredTrace const &)
0x180a7ae1c  lea     rcx, [rsp+398h+var_1D0]
0x180a7ae24  call    ??1?$unique_ptr@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::wstring const>::~unique_ptr<std::wstring const,std::default_delete<std::wstring const>>(void)
0x180a7ae29  lea     rcx, [rsp+398h+var_258]
0x180a7ae31  call    ??1?$unique_ptr@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::wstring const>::~unique_ptr<std::wstring const,std::default_delete<std::wstring const>>(void)
0x180a7ae36  lea     rcx, [rsp+398h+var_1C8]; void *
0x180a7ae3e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180a7ae43  mov     rcx, [rsp+398h+var_1A0]
0x180a7ae4b  cmp     [rsp+398h+var_1A8], rcx
0x180a7ae53  jz      loc_180A7B1AF
0x180a7ae59  sub     rcx, [rsp+398h+var_1A8]
0x180a7ae61  sar     rcx, 3
0x180a7ae65  xor     edx, edx
0x180a7ae67  lea     r13d, [rdx+64h]
0x180a7ae6b  mov     eax, r13d
0x180a7ae6e  div     rcx
0x180a7ae71  mov     rsi, rax
0x180a7ae74  mov     [rsp+398h+var_300], rax
0x180a7ae7c  lea     r8d, [r13-63h]
0x180a7ae80  lea     rdx, [rsp+398h+var_2A8]
0x180a7ae88  lea     rcx, [rsp+398h+var_2B8]
0x180a7ae90  call    ?CreateChildProgress@CProgressLock@ProgressUI@OneNote@@UEAA?AV?$CIPtr@UIProgress@ProgressUI@OneNote@@U123@@MsoCF@@I@Z; OneNote::ProgressUI::CProgressLock::CreateChildProgress(uint)
0x180a7ae95  nop
0x180a7ae96  mov     r8d, r13d; unsigned int
0x180a7ae99  mov     rdx, [rax]; struct OneNote::ProgressUI::IProgress *
0x180a7ae9c  lea     rcx, [rsp+398h+var_320]; this
0x180a7aea1  call    ??0CProgressLock@ProgressUI@OneNote@@QEAA@PEAUIProgress@12@I@Z; OneNote::ProgressUI::CProgressLock::CProgressLock(OneNote::ProgressUI::IProgress *,uint)
0x180a7aea6  nop
0x180a7aea7  mov     rcx, [rsp+398h+var_2A8]
0x180a7aeaf  test    rcx, rcx
0x180a7aeb2  jz      short loc_180A7AEC1
0x180a7aeb4  mov     rax, [rcx]
0x180a7aeb7  mov     rax, [rax+10h]
0x180a7aebb  call    cs:__guard_dispatch_icall_fptr
0x180a7aec1  mov     r13, [rsp+398h+var_1A8]
0x180a7aec9  mov     rax, [rsp+398h+var_1A0]
0x180a7aed1  mov     [rsp+398h+var_330], rax
0x180a7aed6  cmp     r13, rax
0x180a7aed9  jz      loc_180A7B19E
0x180a7aedf  mov     edx, esi; unsigned int
0x180a7aee1  lea     rcx, [rsp+398h+var_320]; this
0x180a7aee6  call    ?MakeProgress@CProgressLock@ProgressUI@OneNote@@UEAAXI@Z; OneNote::ProgressUI::CProgressLock::MakeProgress(uint)
0x180a7aeeb  mov     rcx, [r13+0]
0x180a7aeef  mov     rax, [rcx]
0x180a7aef2  mov     rax, [rax+0B0h]
0x180a7aef9  call    cs:__guard_dispatch_icall_fptr
0x180a7aeff  test    al, al
0x180a7af01  jz      loc_180A7B3F1
0x180a7af07  mov     rcx, [r13+0]
0x180a7af0b  mov     rax, [rcx]
0x180a7af0e  xor     edx, edx
0x180a7af10  mov     r8d, 23C34600h
0x180a7af16  mov     rax, [rax+50h]
0x180a7af1a  call    cs:__guard_dispatch_icall_fptr
0x180a7af20  test    al, al
0x180a7af22  jz      loc_180A7B3F1
0x180a7af28  mov     rcx, [r13+0]
0x180a7af2c  cmp     rcx, rbx
0x180a7af2f  jz      loc_180A7B3F1
0x180a7af35  mov     rax, r14
0x180a7af38  mov     [rsp+398h+var_308], rax
0x180a7af40  test    rcx, rcx
0x180a7af43  jz      short loc_180A7AF68
0x180a7af45  mov     rax, [rcx]
0x180a7af48  lea     r8, [rsp+398h+var_308]
0x180a7af50  lea     rdx, _GUID_4735b3bf_db6a_44c3_942e_6c16a8b935ce
0x180a7af57  mov     rax, [rax]
0x180a7af5a  call    cs:__guard_dispatch_icall_fptr
0x180a7af60  mov     rax, [rsp+398h+var_308]
0x180a7af68  test    rax, rax
0x180a7af6b  jnz     short loc_180A7AF72
0x180a7af6d  jmp     loc_180A7B3F1
0x180a7af72  call    sub_1800314B8
0x180a7af77  mov     rcx, [rax]
0x180a7af7a  mov     rax, [rcx]
0x180a7af7d  mov     rax, [rax+98h]
0x180a7af84  call    cs:__guard_dispatch_icall_fptr
0x180a7af8a  test    rax, rax
0x180a7af8d  jnz     short loc_180A7AF9D
0x180a7af8f  xor     edx, edx
0x180a7af91  mov     ecx, 27D00CAh
0x180a7af96  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180a7af9c  int     3; Trap to Debugger
0x180a7af9d  mov     rsi, [r13+0]
0x180a7afa1  call    sub_1800314B8
0x180a7afa6  mov     rcx, [rax]
0x180a7afa9  mov     rax, [rcx]
0x180a7afac  mov     rax, [rax+98h]
0x180a7afb3  call    cs:__guard_dispatch_icall_fptr
0x180a7afb9  mov     r8, rsi
0x180a7afbc  mov     rdx, rax
0x180a7afbf  lea     rcx, [rsp+398h+var_340]
0x180a7afc4  call    ?FindNotebookContaining@Jot@@YA?AV?$CNodeRef@VCSemNotebookTrait@Jot@@@1@AEAUIGraphSpace@1@PEAUIFileProxy@1@@Z; Jot::FindNotebookContaining(Jot::IGraphSpace &,Jot::IFileProxy *)
0x180a7afc9  nop
0x180a7afca  lea     rcx, [rsp+398h+var_340]
0x180a7afcf  call    ?IsValid@?$CNodeRef@VCSemNotebookTrait@Jot@@@Jot@@QEBA_NXZ; Jot::CNodeRef<Jot::CSemNotebookTrait>::IsValid(void)
0x180a7afd4  test    al, al
0x180a7afd6  jz      short loc_180A7B04D
0x180a7afd8  xor     r8d, r8d
0x180a7afdb  lea     rdx, [rsp+398h+var_340]
0x180a7afe0  lea     rcx, [rsp+398h+var_2E0]
0x180a7afe8  call    ?GetFolderProxy@NotebookEditor@Jot@@YA?AV?$CIPtr@UIFolderProxy@Jot@@U12@@MsoCF@@AEBV?$CNodeRef@VCSemNotebookTrait@Jot@@@2@_N@Z; Jot::NotebookEditor::GetFolderProxy(Jot::CNodeRef<Jot::CSemNotebookTrait> const &,bool)
0x180a7afed  mov     rcx, [rsp+398h+var_308]
0x180a7aff5  cmp     rcx, [rax]
0x180a7aff8  setnz   sil
0x180a7affc  mov     rdx, qword ptr [rsp+398h+var_2E0]
0x180a7b004  test    rdx, rdx
0x180a7b007  jz      short loc_180A7B021
0x180a7b009  mov     rax, [rdx]
0x180a7b00c  mov     rcx, rdx
0x180a7b00f  mov     rax, [rax+10h]
0x180a7b013  call    cs:__guard_dispatch_icall_fptr
  ... truncated ...
```
