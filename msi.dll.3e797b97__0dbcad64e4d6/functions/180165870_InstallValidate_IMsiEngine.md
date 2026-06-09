# InstallValidate(IMsiEngine &)

- ea: `0x180165870`
- end: `0x1801689f2`
- name: `?InstallValidate@@YA?AW4iesEnum@@AEAVIMsiEngine@@@Z`
- size: `12674`
- prototype: ``
- caller_count: `0`
- callee_count: `42`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180003b10`
- `0x180005af8`
- `0x18000c4bc`
- `0x180014160`
- `0x180018ee0`
- `0x180019cc0`
- `0x18002e870`
- `0x180058790`
- `0x180061c4c`
- `0x18006fa2c`
- `0x180081de0`
- `0x18008c93c`
- `0x180097c78`
- `0x1800a19e0`
- `0x1800ae46c`
- `0x1800c0678`
- `0x1800d04fc`
- `0x1800dcef8`
- `0x1800ee66c`
- `0x18011f49c`
- `0x180125b1c`
- `0x18013fa30`
- `0x18014676c`
- `0x18015bd44`
- `0x180165870`
- `0x1801689f8`
- `0x1801bfbd0`
- `0x1801bfcc8`
- `0x1801c004c`
- `0x1801c012c`
- `0x1801c014c`
- `0x1801c03fc`
- `0x18020dad4`
- `0x18020e27c`
- `0x1802226b0`
- `0x18022bd48`
- `0x18022d09c`
- `0x18022d428`
- `0x180248ee0`
- `0x1802651ea`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `KERNEL32!Sleep` at `0x1801672d3`
- `KERNEL32!Sleep` at `0x1801672d3`
- `KERNEL32!GetCurrentProcessId` at `0x18016697d`
- `KERNEL32!GetCurrentProcessId` at `0x1801676a4`
- `KERNEL32!GetCurrentProcessId` at `0x18016697d`
- `KERNEL32!GetCurrentProcessId` at `0x1801676a4`

## string_xrefs

- `0x180166935`: `CLIENTPROCESSID`
- `0x1801676ba`: `CLIENTPROCESSID`
- `0x1801687c0`: `REMOVE`
- `0x180168907`: `REMOVE`
- `0x180166824`: `MSICLIENTUSESEXTERNALUI`
- `0x18016593f`: `MsiRestartManagerSessionKey`
- `0x18016843d`: `PROMPTROLLBACKCOST`
- `0x1801667d5`: `RESTART MANAGER: Failed to retrieve the list of applications that hold files in use; Windows Installer will use the built-in FilesInUse functionality. Error: %d`
- `0x180165afd`: ` SELECT `Feature`, `Action`, `ActionRequested`, `Installed` FROM `Feature``
- `0x180165ba9`: ` SELECT `Component`, `Action`, `ActionRequest`, `Installed`, `TrueInstallSt` FROM `Component``
- `0x180165cb6`: `Component`
- `0x180165d1a`: `Reinstall`
- `0x180165dd0`: `Incomplete`
- `0x180165dc2`: `Bad Config`
- `0x180166164`: `%s: %s; Installed: %s;   Request: %s;   Action: %s;   Client State: %s`
- `0x180165e39`: `Advertised/Removed`
- `0x1801666f9`: `RESTART MANAGER: Failed to add file path resources; Windows Installer will use the built-in FilesInUse functionality. Error: %d`
- `0x180166241`: `%s: %s; Installed: %s;   Request: %s;   Action: %s`
- `0x1801668e9`: `RESTART MANAGER: Will attempt to shut down and restart applications in no UI modes.`
- `0x180166889`: `RESTART MANAGER: Will attempt to shut down and restart applications because the UI does not display any modal dialogs.`
- `0x180167cbe`: `RESTART MANAGER: Did detect that the client process of this installation holds file[s] in use, so a reboot will be necessary.`
- `0x180167cda`: `RESTART MANAGER: Did detect that Windows Installer service holds file[s] in use, so a reboot will be necessary.`
- `0x180166a49`: `RESTART MANAGER: Detected that the service %s will be stopped due to a service control action authored in the package before the files are updated. So, we will not attempt to stop this service using Restart Manager`
- `0x1801670b1`: `MSIRMSHUTDOWN`
- `0x1801681ca`: `RESTART MANAGER: The user chose to go on with the installation, although a reboot will be required.`
- `0x18016839a`: `RESTART MANAGER: The user chose to go on with the installation, although a reboot will be required.`
- `0x1801671e5`: `RESTART MANAGER: Failed to shut down all applications in the service's session. Error: %d`
- `0x180167121`: `MSIDISABLERMRESTART`
- `0x180167224`: `RESTART MANAGER: Successfully shut down all applications in the service's session that held files in use.`
- `0x180167789`: `msiexec`
- `0x180168864`: `Resolving source for application compatibility with this install.`
- `0x180166455`: `FilePath`
- `0x18016740d`: `FilePath`
- `0x18016743e`: `ProcessID`
- `0x180165a91`: `MsiRMFilesInUse`

## pseudocode

```c
__int64 __fastcall InstallValidate(struct IMsiEngine *a1)
{
  struct IMsiEngine *v1; // r12
  unsigned int v2; // r14d
  __int64 v3; // r13
  __int64 v4; // r15
  void (__fastcall *v5)(struct IMsiEngine *, _QWORD, void ***); // rbx
  MsiString *v6; // rax
  __int64 v7; // rax
  unsigned int v8; // esi
  __int64 v9; // rax
  __int64 (__fastcall *v10)(__int64, _QWORD, _QWORD, __int64); // rdi
  __int64 v11; // rbx
  MsiString *v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, _QWORD); // rbx
  unsigned int v17; // eax
  bool v18; // bl
  __int64 v19; // rdi
  void (__fastcall *v20)(__int64, _QWORD, _QWORD); // rbx
  MsiString *v21; // rax
  int v22; // eax
  int v23; // ecx
  int v24; // edi
  __int64 v25; // rsi
  __int64 (__fastcall *v26)(struct IMsiEngine *, _QWORD, char *, __int64, __int64); // rbx
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rbx
  int v32; // edi
  __int64 v33; // rax
  unsigned int v34; // eax
  int v35; // eax
  enum tagINSTALLOGMODE v36; // ecx
  int v37; // eax
  bool v38; // sf
  unsigned int v39; // eax
  __int64 v40; // rax
  int v41; // eax
  __int64 v42; // rax
  __int64 v43; // rax
  unsigned int v44; // edi
  char v45; // al
  CRestartManagerWrapper *Instance; // rbx
  CRestartManagerWrapper *v47; // rcx
  __int64 v48; // rax
  int v49; // eax
  _QWORD *v50; // rsi
  __int64 *v51; // rdi
  CRestartManagerWrapper *v52; // rcx
  unsigned int v53; // r14d
  __int64 (__fastcall *v54)(__int64, _QWORD, _QWORD, __int64); // r14
  __int64 v55; // rbx
  MsiString *v56; // rax
  __int64 v57; // rax
  __int64 v58; // rbx
  __int64 *v59; // r14
  __int64 (__fastcall *v60)(__int64 *, _QWORD); // rbx
  unsigned int v61; // eax
  int v62; // eax
  __int64 *v63; // r14
  __int64 (__fastcall *v64)(__int64 *, _QWORD); // rbx
  unsigned int v65; // eax
  __int64 v66; // r14
  void *v67; // rax
  signed int i; // ebx
  int v69; // eax
  int v70; // r12d
  __int64 v71; // r14
  __int64 v72; // r12
  const struct IMsiString *v73; // rbx
  unsigned __int64 v74; // rax
  void *v75; // rax
  int v76; // eax
  struct IMsiRecord *v77; // rax
  _QWORD *v78; // rbx
  unsigned int v79; // r14d
  unsigned int v80; // eax
  __int64 v81; // rax
  void *v82; // rcx
  unsigned int ApplicationsList; // eax
  __int64 (__fastcall *v84)(struct IMsiEngine *, _QWORD); // rbx
  MsiString *v85; // rax
  const unsigned __int16 *v86; // r9
  __int64 (__fastcall *v87)(struct IMsiEngine *, _QWORD); // rbx
  MsiString *v88; // rax
  int v89; // ebx
  __int64 v90; // rax
  __int64 (__fastcall *v91)(struct IMsiEngine *, _QWORD); // rbx
  MsiString *v92; // rax
  DWORD CurrentProcessId; // eax
  CRestartManagerWrapper *v94; // rbx
  unsigned int j; // eax
  CRestartManagerWrapper *v96; // rcx
  DWORD dwProcessId; // ecx
  int k; // edx
  unsigned int v99; // ebx
  void (__fastcall *v100)(_QWORD *, _QWORD, __int64); // r14
  __int64 v101; // rbx
  __int64 v102; // rdx
  __int64 v103; // rax
  void (__fastcall *v104)(_QWORD *, _QWORD, _QWORD); // rbx
  MsiString *v105; // rax
  MsiString *v106; // rax
  _QWORD *v107; // rbx
  MsiString *v108; // rax
  void (__fastcall *v109)(__int64 *, _QWORD, __int64); // r14
  __int64 v110; // rbx
  unsigned int v111; // r14d
  __int64 v112; // rax
  bool v113; // zf
  char v114; // bl
  int v115; // eax
  struct IMsiRecord *v116; // rax
  __int64 v117; // rdi
  int v118; // ebx
  int v119; // esi
  void (__fastcall *v120)(__int64, _QWORD, _QWORD); // rbx
  MsiString *v121; // rax
  __int64 v122; // rax
  void (__fastcall *v123)(struct IMsiEngine *, const WCHAR *, void **, void **); // rbx
  __int64 v124; // rax
  __int64 v125; // rbx
  __int64 v126; // rbx
  __int64 (__fastcall *v127)(struct IMsiEngine *, _QWORD); // rdi
  MsiString *v128; // rax
  int v129; // edi
  __int64 v130; // r8
  __int64 (__fastcall *v131)(struct IMsiEngine *, _QWORD); // rdi
  MsiString *v132; // rax
  __int64 (__fastcall *v133)(CRestartManagerWrapper *, _QWORD, __int64); // r14
  unsigned int v134; // eax
  __int64 v135; // r8
  unsigned int v136; // eax
  unsigned int v137; // edi
  int v138; // eax
  __int64 (__fastcall *v139)(__int64, _QWORD); // rbx
  MsiString *v140; // rax
  void (__fastcall *v141)(__int64, _QWORD, _QWORD, __int64); // rdi
  __int64 v142; // rbx
  MsiString *v143; // rax
  __int64 v144; // rdi
  __int64 (__fastcall *v145)(__int64, _QWORD); // rbx
  unsigned int v146; // eax
  int v147; // eax
  __int64 v148; // rdi
  __int64 (__fastcall *v149)(__int64, _QWORD); // rbx
  unsigned int v150; // eax
  int v151; // eax
  __int64 v152; // rdi
  __int64 (__fastcall *v153)(__int64, _QWORD); // rbx
  unsigned int v154; // eax
  unsigned int v155; // r14d
  __int64 v156; // rax
  _QWORD *v157; // rax
  _QWORD *v158; // rbx
  __int64 v159; // rax
  __int64 v160; // rdx
  __int64 v161; // rdi
  __int64 v162; // r12
  __int64 (__fastcall *v163)(__int64, __int64, __int64); // r14
  __int64 v164; // rax
  __int64 v165; // rax
  __int64 v166; // r14
  __int64 v167; // r15
  __int64 v168; // rax
  const unsigned __int16 *v169; // rax
  void *v170; // r14
  MsiString *v171; // rax
  signed int v172; // ecx
  __int64 v173; // rax
  __int64 v174; // rax
  MsiString *v175; // rax
  int v176; // ecx
  struct IMsiRecord *v177; // rax
  __int64 v178; // rcx
  __int64 *v179; // rcx
  const unsigned __int16 *v180; // r9
  struct IMsiRecord *v181; // rax
  CMsiBaselineManager *v182; // rsi
  __int64 v183; // rax
  int v184; // ebx
  int v185; // eax
  void *v186; // rax
  void *v187; // rdi
  __int64 v188; // r14
  __int64 (__fastcall *v189)(void *, _QWORD); // rbx
  unsigned int v190; // eax
  unsigned int v191; // esi
  __int64 (__fastcall *v192)(void *, _QWORD); // rbx
  unsigned int v193; // eax
  __int64 (__fastcall *v194)(void *, _QWORD); // rbx
  unsigned int v195; // eax
  int v196; // eax
  __int64 v197; // rbx
  unsigned __int64 v198; // rdi
  __int64 v199; // rax
  const struct IMsiString *MsiDirectory; // rdi
  __int64 (__fastcall *v201)(__int64, __int64, __int64); // rsi
  __int64 v202; // rbx
  __int64 v203; // rax
  CRestartManagerWrapper *v204; // rsi
  int v205; // ebx
  __int64 v206; // rax
  struct IMsiRecord *v207; // rax
  struct IMsiRecord *v208; // rax
  __int64 v209; // rcx
  struct IMsiRecord *v210; // rax
  __int64 v211; // rcx
  struct IMsiEngine *v212; // rbx
  __int64 v213; // rsi
  __int64 v214; // rax
  __int64 v215; // rdx
  __int64 v216; // rbx
  struct IMsiRecord *v217; // rdx
  const unsigned __int16 *v218; // rax
  int v219; // ecx
  int v220; // eax
  struct IMsiRecord *v221; // rax
  struct IMsiRecord *v222; // rax
  __int64 v223; // rcx
  __int64 v224; // rbx
  unsigned int v225; // edi
  void (__fastcall *v226)(struct IMsiEngine *, _QWORD, __int64); // rsi
  __int64 v227; // rdi
  MsiString *v228; // rax
  void (__fastcall *v229)(__int64); // rax
  unsigned __int8 v231; // [rsp+60h] [rbp-A0h]
  char v232; // [rsp+60h] [rbp-A0h]
  int v233; // [rsp+64h] [rbp-9Ch]
  signed int v234; // [rsp+64h] [rbp-9Ch]
  unsigned int v235; // [rsp+64h] [rbp-9Ch]
  unsigned int v236; // [rsp+64h] [rbp-9Ch]
  int v237; // [rsp+64h] [rbp-9Ch]
  unsigned int v238; // [rsp+64h] [rbp-9Ch]
  unsigned int v239; // [rsp+68h] [rbp-98h] BYREF
  signed int v240; // [rsp+6Ch] [rbp-94h]
  __int64 v241; // [rsp+70h] [rbp-90h] BYREF
  __int64 v242; // [rsp+78h] [rbp-88h] BYREF
  int v243; // [rsp+80h] [rbp-80h]
  unsigned int v244; // [rsp+84h] [rbp-7Ch] BYREF
  __int64 v245; // [rsp+88h] [rbp-78h] BYREF
  __int64 v246; // [rsp+90h] [rbp-70h] BYREF
  _QWORD *v247; // [rsp+98h] [rbp-68h] BYREF
  __int64 v248; // [rsp+A0h] [rbp-60h] BYREF
  __int64 *v249; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v250; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v251; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v252; // [rsp+C0h] [rbp-40h] BYREF
  struct IMsiEngine *v253; // [rsp+C8h] [rbp-38h] BYREF
  __int64 *v254; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v255; // [rsp+D8h] [rbp-28h] BYREF
  CRestartManagerWrapper *v256; // [rsp+E0h] [rbp-20h] BYREF
  void *v257; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v258; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v259; // [rsp+F8h] [rbp-8h] BYREF
  void *v260; // [rsp+100h] [rbp+0h] BYREF
  __int64 v261; // [rsp+108h] [rbp+8h] BYREF
  __int64 v262; // [rsp+110h] [rbp+10h] BYREF
  void *v263; // [rsp+118h] [rbp+18h] BYREF
  __int64 v264; // [rsp+120h] [rbp+20h] BYREF
  void *v265; // [rsp+128h] [rbp+28h] BYREF
  __int64 v266; // [rsp+130h] [rbp+30h] BYREF
  int v267; // [rsp+138h] [rbp+38h] BYREF
  __int64 v268; // [rsp+140h] [rbp+40h] BYREF
  CMsiBaselineManager *v269; // [rsp+148h] [rbp+48h] BYREF
  __int64 v270; // [rsp+150h] [rbp+50h] BYREF
  __int64 v271; // [rsp+158h] [rbp+58h] BYREF
  void (__fastcall *v272)(__int64, __int64, _QWORD); // [rsp+160h] [rbp+60h]
  struct CMsiCustomActionManager *CustomActionManager; // [rsp+168h] [rbp+68h]
  __int64 v274; // [rsp+170h] [rbp+70h] BYREF
  __int64 v275; // [rsp+178h] [rbp+78h] BYREF
  __int64 v276; // [rsp+180h] [rbp+80h] BYREF
  __int64 v277; // [rsp+188h] [rbp+88h] BYREF
  __int64 v278; // [rsp+190h] [rbp+90h] BYREF
  __int64 v279; // [rsp+198h] [rbp+98h] BYREF
  __int64 v280; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v281; // [rsp+1A8h] [rbp+A8h] BYREF
  __int64 v282; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v283; // [rsp+1B8h] [rbp+B8h] BYREF
  __int64 v284; // [rsp+1C0h] [rbp+C0h] BYREF
  __int64 v285; // [rsp+1C8h] [rbp+C8h] BYREF
  void (__fastcall *v286)(_QWORD *, _QWORD, _QWORD); // [rsp+1D0h] [rbp+D0h]
  __int64 v287; // [rsp+1D8h] [rbp+D8h] BYREF
  _QWORD v288[14]; // [rsp+1E0h] [rbp+E0h]
  struct _RM_PROCESS_INFO v289; // [rsp+250h] [rbp+150h] BYREF
  __int128 v290; // [rsp+4F0h] [rbp+3F0h] BYREF
  __int64 v291; // [rsp+500h] [rbp+400h]
  __int128 v292; // [rsp+508h] [rbp+408h]
  int v293; // [rsp+518h] [rbp+418h]
  int v294; // [rsp+51Ch] [rbp+41Ch]
  __int64 v295; // [rsp+520h] [rbp+420h] BYREF
  int v296; // [rsp+528h] [rbp+428h]
  wchar_t v297; // [rsp+52Ch] [rbp+42Ch]
  __int128 v298; // [rsp+52Eh] [rbp+42Eh]
  __int64 v299; // [rsp+53Eh] [rbp+43Eh]
  int v300; // [rsp+546h] [rbp+446h]
  __int128 v301; // [rsp+54Ah] [rbp+44Ah]
  __int16 v302; // [rsp+55Ah] [rbp+45Ah]
  __int64 v303; // [rsp+55Ch] [rbp+45Ch]
  int v304; // [rsp+564h] [rbp+464h]
  unsigned __int16 v305; // [rsp+568h] [rbp+468h]
  __int128 v306; // [rsp+56Ah] [rbp+46Ah]
  __int128 v307; // [rsp+57Ah] [rbp+47Ah]
  int v308; // [rsp+58Ah] [rbp+48Ah]
  __int64 v309; // [rsp+58Eh] [rbp+48Eh]
  __int16 v310; // [rsp+596h] [rbp+496h]
  __int128 v311; // [rsp+598h] [rbp+498h]
  int v312; // [rsp+5A8h] [rbp+4A8h]
  __int64 v313; // [rsp+5ACh] [rbp+4ACh]
  __int16 v314; // [rsp+5B4h] [rbp+4B4h]
  __int128 v315; // [rsp+5B6h] [rbp+4B6h]
  __int64 v316; // [rsp+5C6h] [rbp+4C6h]
  int v317; // [rsp+5CEh] [rbp+4CEh]
  __int16 v318; // [rsp+5D2h] [rbp+4D2h]
  _BYTE v319[22]; // [rsp+5D4h] [rbp+4D4h]
  __int64 v320; // [rsp+5EAh] [rbp+4EAh]
  __int16 v321; // [rsp+5F2h] [rbp+4F2h]
  _BYTE v322[28]; // [rsp+5F4h] [rbp+4F4h] BYREF
  __int16 v323; // [rsp+610h] [rbp+510h]
  _BYTE v324[28]; // [rsp+612h] [rbp+512h] BYREF
  __int16 v325; // [rsp+62Eh] [rbp+52Eh]
  _BYTE v326[28]; // [rsp+630h] [rbp+530h] BYREF
  __int16 v327; // [rsp+64Ch] [rbp+54Ch]
  _BYTE v328[28]; // [rsp+64Eh] [rbp+54Eh] BYREF
  _BYTE v329[22]; // [rsp+66Ah] [rbp+56Ah]
  __int64 v330; // [rsp+680h] [rbp+580h]
  _BYTE v331[30]; // [rsp+688h] [rbp+588h]
  __int64 v332; // [rsp+6A6h] [rbp+5A6h]
  wchar_t v333; // [rsp+6AEh] [rbp+5AEh]
  __int128 v334; // [rsp+6B0h] [rbp+5B0h]
  int v335; // [rsp+6C0h] [rbp+5C0h]
  _OWORD v336[8]; // [rsp+6D0h] [rbp+5D0h] BYREF
  _QWORD v337[29]; // [rsp+750h] [rbp+650h] BYREF
  _BYTE v338[28]; // [rsp+838h] [rbp+738h]
  __int64 v339; // [rsp+854h] [rbp+754h]
  int v340; // [rsp+85Ch] [rbp+75Ch]

  v253 = a1;
  LODWORD(v242) = 0;
  v1 = a1;
  v2 = 2;
  if ( g_scServerContext == 2
    && !(*(unsigned __int8 (__fastcall **)(struct IMsiEngine *))(*(_QWORD *)a1 + 432LL))(a1)
    && qword_1803136E0 )
  {
    CMsiSQMSession::RecordInstallType(qword_1803136E0, v1);
  }
  v3 = (*(__int64 (__fastcall **)(struct IMsiEngine *))(*(_QWORD *)v1 + 56LL))(v1);
  v274 = v3;
  v270 = (*(__int64 (__fastcall **)(struct IMsiEngine *))(*(_QWORD *)v1 + 72LL))(v1);
  v4 = v270;
  CComPointer<IMsiSelectionManager>::CComPointer<IMsiSelectionManager>(&v266, v1, &IID_IMsiSelectionManager);
  if ( (*(unsigned int (__fastcall **)(struct IMsiEngine *))(*(_QWORD *)v1 + 312LL))(v1) == 2 )
    goto LABEL_320;
  v5 = *(void (__fastcall **)(struct IMsiEngine *, _QWORD, void ***))(*(_QWORD *)v1 + 160LL);
  v6 = MsiString::MsiString((MsiString *)&v252, L"MsiRestartManagerSessionKey");
  v5(v1, *(_QWORD *)v6, &g_MsiStringNull);
  (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v252 + 16LL))(v252);
  v251 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 48LL))(v3, 2);
  v241 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 48LL))(v3, 6);
  v248 = 0;
  v245 = 0;
  v8 = 0;
  v250 = v7;
  v9 = *(_QWORD *)v4;
  LOBYTE(v243) = 0;
  v10 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64))(v9 + 80);
  v11 = CComPointer<IEnumMsiRecord>::operator=(&v248);
  v12 = MsiString::MsiString((MsiString *)&v252, L"Dialog");
  v13 = v10(v4, *(_QWORD *)v12, 0, v11);
  v18 = 0;
  if ( !*(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v241, v13) )
  {
    v14 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v248 + 128LL))(v248, 0);
    if ( *(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v245, v14) )
    {
      v15 = v248;
      v16 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v248 + 96LL);
      v17 = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v4 + 120LL))(v4, L"Dialog");
      v8 = v16(v15, v17);
      if ( v8 )
        v18 = 1;
    }
  }
  (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v252 + 16LL))(v252);
  if ( v18 )
  {
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v245 + 48LL))(v245, v8);
    v19 = v245;
    v20 = *(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v245 + 96LL);
    v21 = MsiString::MsiString((MsiString *)&v252, L"MsiRMFilesInUse");
    v20(v19, v8, *(_QWORD *)v21);
    (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v252 + 16LL))(v252);
    v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v245 + 40LL))(v245);
    v23 = (unsigned __int8)v243;
    if ( v22 )
      v23 = 1;
    v243 = v23;
  }
  if ( FDiagnosticModeSet(10) )
  {
    v336[0] = *(_OWORD *)L" SELECT `Feature`, `Action`, `ActionRequested`, `Installed` FROM `Feature`";
    v336[2] = *(_OWORD *)L"`, `Action`, `ActionRequested`, `Installed` FROM `Feature`";
    v336[4] = *(_OWORD *)L"tionRequested`, `Installed` FROM `Feature`";
    v336[6] = *(_OWORD *)L"`Installed` FROM `Feature`";
    *(_OWORD *)v337 = *(_OWORD *)L" `Feature`";
    *(_QWORD *)((char *)&v337[1] + 6) = *(_QWORD *)L"re`";
    v336[1] = *(_OWORD *)L"`Feature`, `Action`, `ActionRequested`, `Installed` FROM `Feature`";
    v339 = 0;
    memset((char *)&v337[2] + 6, 0, 50);
    v340 = 0;
    v291 = 0;
    v293 = *(_DWORD *)L"t";
    v336[3] = *(_OWORD *)L"on`, `ActionRequested`, `Installed` FROM `Feature`";
    v294 = 0;
    *(_OWORD *)&v337[9] = *(_OWORD *)L" SELECT `Component`, `Action`, `ActionRequest`, `Installed`, `TrueInstallSt` FROM `Component`";
    v296 = *(_DWORD *)L"nt";
    v336[5] = *(_OWORD *)L"ested`, `Installed` FROM `Feature`";
    v297 = aAbsent[6];
    *(_OWORD *)&v337[13] = *(_OWORD *)L"nt`, `Action`, `ActionRequest`, `Installed`, `TrueInstallSt` FROM `Component`";
    v300 = *(_DWORD *)L"l";
    v336[7] = *(_OWORD *)L"ed` FROM `Feature`";
    v302 = 0;
    *(_OWORD *)&v337[17] = *(_OWORD *)L"ActionRequest`, `Installed`, `TrueInstallSt` FROM `Component`";
    v304 = *(_DWORD *)L"ce";
    *(_OWORD *)&v337[11] = *(_OWORD *)L"`Component`, `Action`, `ActionRequest`, `Installed`, `TrueInstallSt` FROM `Component`";
    *(_OWORD *)&v337[21] = *(_OWORD *)L"`Installed`, `TrueInstallSt` FROM `Component`";
    *(_OWORD *)&v337[15] = *(_OWORD *)L"tion`, `ActionRequest`, `Installed`, `TrueInstallSt` FROM `Component`";
    *(_OWORD *)&v337[25] = *(_OWORD *)L"ueInstallSt` FROM `Component`";
    *(_OWORD *)&v337[19] = *(_OWORD *)L"quest`, `Installed`, `TrueInstallSt` FROM `Component`";
    *(_OWORD *)v338 = *(_OWORD *)L"M `Component`";
    *(_OWORD *)&v337[23] = *(_OWORD *)L"ed`, `TrueInstallSt` FROM `Component`";
    v290 = *(_OWORD *)L"Feature";
    *(_OWORD *)&v337[27] = *(_OWORD *)L"lSt` FROM `Component`";
    v292 = *(_OWORD *)L"Component";
    *(_OWORD *)&v338[12] = *(_OWORD *)L"ponent`";
    v295 = *(_QWORD *)L"Absent";
    v299 = *(_QWORD *)L"Local";
    v298 = 0;
    v301 = 0;
    v303 = *(_QWORD *)L"Source";
    v305 = aSource_1[6];
    v308 = *(_DWORD *)L"l";
    v309 = 0;
    v310 = 0;
    v312 = *(_DWORD *)L"e";
    v313 = 0;
    v314 = 0;
    v316 = 0;
    v317 = 0;
    v318 = 0;
    v320 = 0;
    v321 = 0;
    v323 = 0;
    v325 = 0;
    v327 = 0;
    v330 = 0;
    v333 = aNull_1[4];
    v335 = 0;
    v288[0] = L"Not Used";
    v288[1] = L"Bad Config";
    v288[2] = L"Incomplete";
    v288[3] = L"Source Absent";
    v306 = 0;
    v288[4] = L"More Data";
    v288[5] = L"Invalid Arg";
    v288[6] = L"Unknown";
    v311 = *(_OWORD *)L"Advertise";
    v288[7] = L"Broken";
    v288[8] = L"Advertised/Removed";
    v307 = *(_OWORD *)L"Reinstall";
    v288[9] = L"Absent";
    v315 = *(_OWORD *)L"Current";
    v288[10] = L"Local";
    v288[11] = L"Source";
    *(_OWORD *)v319 = *(_OWORD *)L"FileAbsent";
    *(_QWORD *)&v319[14] = *(_QWORD *)L"ent";
    memset(v322, 0, sizeof(v322));
    memset(v324, 0, sizeof(v324));
    memset(v326, 0, sizeof(v326));
    memset(v328, 0, sizeof(v328));
    *(_OWORD *)v329 = *(_OWORD *)L"HKCRAbsent";
    *(_QWORD *)&v329[14] = *(_QWORD *)L"ent";
    *(_OWORD *)v331 = *(_OWORD *)L"HKCRFileAbsent";
    v332 = *(_QWORD *)L"Null";
    *(_OWORD *)&v331[14] = *(_OWORD *)L"eAbsent";
    v334 = 0;
    v24 = 0;
    v288[12] = L"Default";
    v254 = 0;
    v288[13] = L"Null";
    v258 = 0;
    v240 = 0;
    while ( 1 )
    {
      v25 = (unsigned int)v24;
      v26 = *(__int64 (__fastcall **)(struct IMsiEngine *, _QWORD, char *, __int64, __int64))(*(_QWORD *)v1 + 136LL);
      v27 = CComPointer<IEnumMsiRecord>::operator=(&v258);
      v28 = v26(v1, 0, (char *)v336 + 200 * (unsigned int)v24, 1, v27);
      CComPointer<IMsiDatabase>::operator=(&v241, v28);
      if ( v241 )
        goto LABEL_40;
      v29 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v258 + 24LL))(v258, 0);
      CComPointer<IMsiDatabase>::operator=(&v241, v29);
      if ( v241 )
        goto LABEL_39;
      while ( 1 )
      {
        v30 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v258 + 56LL))(v258);
        if ( !*(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v254, v30) )
          break;
        v31 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v254 + 72))(v254, 1);
        v32 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v254 + 56))(v254, 2);
        if ( v32 == 0x80000000 )
          v32 = 13;
        v33 = *v254;
        LODWORD(v246) = v32;
        v34 = (*(__int64 (__fastcall **)(__int64 *, __int64))(v33 + 56))(v254, 3);
        if ( v34 == 0x80000000 )
          v34 = 13;
        v244 = v34;
        v35 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v254 + 56))(v254, 4);
        if ( v35 == 0x80000000 )
          v35 = 13;
        v233 = v35;
        if ( IsLoggingModeSet(v36) && (_DWORD)v25 == 1 )
        {
          v37 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v254 + 56))(v254, 5);
          if ( v37 == 0x80000000 )
          {
            v239 = 13;
          }
          else
          {
            v38 = v37 + 7 < 0;
            v39 = v37 + 7;
            v239 = v39;
            if ( v38 || v39 >= 0xE )
              goto LABEL_36;
          }
          v40 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v31 + 80LL))(v31);
          v41 = StringCbPrintfW(
                  (unsigned __int16 *)&v289,
                  0x200u,
                  L"%s: %s; Installed: %s;   Request: %s;   Action: %s;   Client State: %s",
                  (char *)&v290 + 24 * v25,
                  v40,
                  (char *)&v295 + 30 * v233,
                  (char *)&v295 + 30 * (int)v244,
                  (char *)&v295 + 30 * (int)v246,
                  v288[v239]);
        }
        else
        {
          v42 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v31 + 80LL))(v31);
          v41 = StringCbPrintfW(
                  (unsigned __int16 *)&v289,
                  0x200u,
                  L"%s: %s; Installed: %s;   Request: %s;   Action: %s",
                  (char *)&v290 + 24 * v25,
                  v42,
                  (char *)&v295 + 30 * v233,
                  (char *)&v295 + 30 * (int)v244,
                  (char *)&v295 + 30 * v32);
        }
        if ( v41 >= 0 )
        {
          if ( g_dmDiagnosticMode )
            DebugString(
              10,
              0,
              0,
              (const unsigned __int16 *)&v289,
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              0,
              0);
        }
LABEL_36:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
      }
      v1 = v253;
      v24 = v240;
LABEL_39:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v258 + 80LL))(v258);
LABEL_40:
      v240 = ++v24;
      if ( v24 >= 2 )
      {
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v258);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v254);
        v4 = v270;
        v3 = v274;
        break;
      }
    }
  }
  if ( byte_1803136D3 )
    goto LABEL_308;
  v43 = *(_QWORD *)v1;
  v44 = 1;
  v244 = 0;
  (*(void (__fastcall **)(struct IMsiEngine *, __int64, __int64))(v43 + 104))(v1, 4096, 1);
  if ( g_scServerContext == 2 )
  {
    CustomActionManager = GetCustomActionManager(v1);
    v45 = (*(__int64 (__fastcall **)(struct IMsiEngine *))(*(_QWORD *)v1 + 784LL))(v1);
    Instance = (CRestartManagerWrapper *)CRestartManagerWrapper::GetInstance(v45 != 0);
    v256 = Instance;
  }
  else
  {
    Instance = 0;
    CustomActionManager = 0;
    v256 = 0;
  }
  while ( 1 )
  {
    if ( !Instance )
      goto LABEL_50;
    if ( CRestartManagerWrapper::IsEnabled(Instance) )
      CRestartManagerWrapper::Reset(v47);
    if ( v44 )
    {
LABEL_50:
      v267 = 0;
      v48 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v266 + 280LL))(v266, &v267);
      if ( *(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v241, v48) )
      {
        v49 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v241 + 56LL))(v241, 1);
        if ( v49 == 3 )
          goto LABEL_221;
        if ( v49 != 2731 )
        {
          v2 = (*(__int64 (__fastcall **)(struct IMsiEngine *, __int64))(*(_QWORD *)v1 + 208LL))(v1, v241);
          goto LABEL_221;
        }
      }
      if ( v267 )
        goto LABEL_221;
    }
    v50 = 0;
    v51 = 0;
    v247 = 0;
    v249 = 0;
    v242 = 0;
    if ( !Instance || !CRestartManagerWrapper::IsEnabled(Instance) )
      goto LABEL_173;
    if ( g_scServerContext == 2 )
    {
      v53 = 0;
      if ( !CRestartManagerWrapper::IsEnabled(v52) )
        goto LABEL_83;
      v254 = 0;
      v258 = 0;
      v54 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64))(*(_QWORD *)v4 + 80LL);
      v55 = CComPointer<IEnumMsiRecord>::operator=(&v254);
      v56 = MsiString::MsiString((MsiString *)&v275, L"FilesInUse");
      v57 = v54(v4, *(_QWORD *)v56, 0, v55);
      v58 = *(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v258, v57);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v275 + 16LL))(v275);
      v53 = 0;
      if ( v58 )
        goto LABEL_81;
      v59 = v254;
      v60 = *(__int64 (__fastcall **)(__int64 *, _QWORD))(*v254 + 96);
      v61 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v4 + 120LL))(v4, L"FilePath");
      v62 = v60(v59, v61);
      v63 = v254;
      LODWORD(v246) = v62;
      v64 = *(__int64 (__fastcall **)(__int64 *, _QWORD))(*v254 + 96);
      v65 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v4 + 120LL))(v4, L"FileName");
      LODWORD(v255) = v64(v63, v65);
      v262 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v254 + 128))(v254, 0);
      v66 = v262;
      if ( v262 )
      {
        v240 = (*(__int64 (__fastcall **)(__int64 *))(*v254 + 64))(v254);
        v252 = (unsigned __int16 *)v240;
        v67 = operator new(saturated_mul(v240, 8u));
        v260 = v67;
        if ( v67 )
        {
          memset_0(v67, 0, 8LL * (_QWORD)v252);
          for ( i = 0; ; i = v234 + 1 )
          {
            v234 = i;
            v69 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v66 + 40LL))(v66);
            v70 = v240;
            if ( !v69 || i >= v240 )
              break;
            v71 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v66 + 64LL))(v66, (unsigned int)v246);
            v72 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v262 + 64LL))(v262, (unsigned int)v255);
            v73 = (const struct IMsiString *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v71 + 168LL))(
                                               v71,
                                               v72);
            v74 = saturated_mul(
                    (*(int (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v73 + 56LL))(v73) + 1LL,
                    2u);
            v75 = operator new(v74);
            *((_QWORD *)v260 + v234) = v75;
            if ( !v75 )
            {
              v77 = PostError(2346, L"FilesInUse");
              goto LABEL_69;
            }
            v252 = (unsigned __int16 *)(*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v73 + 80LL))(v73);
            v76 = (*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v73 + 56LL))(v73);
            if ( (int)StringCchCopyW(*((unsigned __int16 **)v260 + v234), v76 + 1, v252) < 0 )
            {
              v77 = PostError(1322, v73);
LABEL_69:
              CComPointer<IMsiDatabase>::operator=(&v258, v77);
              (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v73 + 16LL))(v73);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
              v70 = v240;
              break;
            }
            (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v73 + 16LL))(v73);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
            v66 = v262;
          }
          v78 = v260;
          v79 = 0;
          if ( !v258 )
          {
            v80 = (**(__int64 (__fastcall ***)(CRestartManagerWrapper *, void *, _QWORD))v256)(
                    v256,
                    v260,
                    (unsigned int)v70);
            if ( v80 )
            {
              if ( g_dmDiagnosticMode )
                DebugString(
                  10,
                  0,
                  0,
                  L"RESTART MANAGER: Failed to add file path resources; Windows Installer will use the built-in FilesInUse"
                   " functionality. Error: %d",
                  (const unsigned __int16 *)v80,
                  L"(NULL)",
                  L"(NULL)",
                  L"(NULL)",
                  L"(NULL)",
                  L"(NULL)",
                  0,
                  0);
            }
          }
          if ( v70 > 0 )
          {
            do
            {
              v81 = v79;
              v82 = (void *)v78[v79];
              if ( v82 )
              {
                operator delete(v82);
                v81 = v79;
              }
              ++v79;
              v78[v81] = 0;
            }
            while ( (int)v79 < v70 );
            v4 = v270;
          }
          operator delete(v78);
          v53 = 0;
          if ( !v258 )
          {
            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v262);
            v1 = v253;
LABEL_81:
            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v258);
            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v254);
            Instance = v256;
            goto LABEL_83;
          }
          v2 = (*(__int64 (__fastcall **)(struct IMsiEngine *))(*(_QWORD *)v253 + 208LL))(v253);
LABEL_226:
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v262);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v258);
          v179 = (__int64 *)&v254;
          goto LABEL_227;
        }
        v176 = 2346;
      }
      else
      {
        v176 = 2283;
      }
      v177 = PostError(v176, L"FilesInUse");
      v178 = *(_QWORD *)v1;
      v259 = (__int64)v177;
      v2 = (*(__int64 (__fastcall **)(struct IMsiEngine *, struct IMsiRecord *))(v178 + 208))(v1, v177);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v259);
      goto LABEL_226;
    }
    v53 = 0;
LABEL_83:
    LODWORD(v246) = -1;
    v239 = 0;
    ApplicationsList = CRestartManagerWrapper::GetApplicationsList(Instance, (enum TRI *)&v246, &v239);
    if ( ApplicationsList )
    {
      if ( g_dmDiagnosticMode )
        DebugString(
          10,
          0,
          0,
          L"RESTART MANAGER: Failed to retrieve the list of applications that hold files in use; Windows Installer will us"
           "e the built-in FilesInUse functionality. Error: %d",
          (const unsigned __int16 *)ApplicationsList,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      goto LABEL_173;
    }
    if ( !v239 )
      goto LABEL_173;
    LODWORD(v262) = ServiceActionOrderCausesReboot(v1);
    v231 = 0;
    v84 = *(__int64 (__fastcall **)(struct IMsiEngine *, _QWORD))(*(_QWORD *)v1 + 192LL);
    v85 = MsiString::MsiString((MsiString *)&v276, L"MSICLIENTUSESEXTERNALUI");
    LODWORD(v84) = v84(v1, *(_QWORD *)v85);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v276 + 16LL))(v276);
    if ( (_DWORD)v84 == 1 )
      goto LABEL_97;
    if ( HIBYTE(word_180313728) )
    {
      if ( g_dmDiagnosticMode )
      {
        v86 = L"RESTART MANAGER: Will attempt to shut down and restart applications because the UI does not display any modal dialogs.";
LABEL_95:
        DebugString(10, 0, 0, v86, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
      }
    }
    else
    {
      v87 = *(__int64 (__fastcall **)(struct IMsiEngine *, _QWORD))(*(_QWORD *)v1 + 192LL);
      v88 = MsiString::MsiString((MsiString *)&v277, L"CLIENTUILEVEL");
      v89 = v87(v1, *(_QWORD *)v88);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v277 + 16LL))(v277);
      if ( v89 != 3 && v89 != 0x2000 )
        goto LABEL_97;
      if ( g_dmDiagnosticMode )
      {
        v86 = L"RESTART MANAGER: Will attempt to shut down and restart applications in no UI modes.";
        goto LABEL_95;
      }
    }
    v231 = 1;
LABEL_97:
    v90 = *(_QWORD *)v1;
    v235 = 0;
    v239 = 0;
    v91 = *(__int64 (__fastcall **)(struct IMsiEngine *, _QWORD))(v90 + 192);
    v92 = MsiString::MsiString((MsiString *)&v278, L"CLIENTPROCESSID");
    LODWORD(v255) = v91(v1, *(_QWORD *)v92);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v278 + 16LL))(v278);
    CurrentProcessId = GetCurrentProcessId();
    v289.Process.dwProcessId = 0;
    LODWORD(v246) = CurrentProcessId;
    memset_0(&v289.Process.ProcessStartTime, 0, 0x298u);
    v94 = v256;
    for ( j = 0; ; j = v240 + 1 )
    {
      v240 = j;
      if ( CRestartManagerWrapper::EnumApplications(v94, j, &v289) )
        goto LABEL_129;
      CRestartManagerWrapper::ReportDetectedApplication(v96, &v289);
      dwProcessId = v289.Process.dwProcessId;
      if ( v289.Process.dwProcessId == (_DWORD)v246 )
      {
        if ( !g_dmDiagnosticMode )
          goto LABEL_238;
        v180 = L"RESTART MANAGER: Did detect that Windows Installer service holds file[s] in use, so a reboot will be necessary.";
        goto LABEL_237;
      }
      if ( v289.Process.dwProcessId == (_DWORD)v255 )
      {
        if ( !g_dmDiagnosticMode )
          goto LABEL_238;
        v180 = L"RESTART MANAGER: Did detect that the client process of this installation holds file[s] in use, so a reboo"
                "t will be necessary.";
        goto LABEL_237;
      }
      if ( CustomActionManager && v289.Process.dwProcessId )
      {
        for ( k = 0; ; ++k )
        {
          if ( k >= 10 )
            goto LABEL_107;
          if ( *((_DWORD *)CustomActionManager + 4 * k + 3) == v289.Process.dwProcessId )
            break;
        }
        if ( g_dmDiagnosticMode )
          DebugString(
            10,
            0,
            0,
            L"RESTART MANAGER: Did detect that the custom action server with process ID %d holds file[s] in use, so a rebo"
             "ot will be necessary.",
            (const unsigned __int16 *)v289.Process.dwProcessId,
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
LABEL_238:
        if ( (_BYTE)v243 )
        {
          v181 = PostError(1610);
          CComPointer<IMsiDatabase>::operator=(&v241, v181);
          v2 = 2;
          if ( (*(unsigned int (__fastcall **)(struct IMsiEngine *, __int64, __int64))(*(_QWORD *)v1 + 24LL))(
                 v1,
                 50331969,
                 v241) == 2 )
            goto LABEL_228;
          if ( g_dmDiagnosticMode )
LABEL_279:
            DebugString(
              10,
              0,
              0,
              L"RESTART MANAGER: The user chose to go on with the installation, although a reboot will be required.",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              0,
              0);
        }
LABEL_243:
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v242);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v249);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v247);
        v2 = 2;
LABEL_244:
        (*(void (__fastcall **)(struct IMsiEngine *, __int64, _QWORD))(*(_QWORD *)v1 + 104LL))(v1, 4096, 0);
        v182 = (CMsiBaselineManager *)(*(__int64 (__fastcall **)(struct IMsiEngine *))(*(_QWORD *)v1 + 672LL))(v1);
        v269 = v182;
        v183 = *(_QWORD *)v1;
        v244 = 0;
        if ( ((*(__int64 (__fastcall **)(struct IMsiEngine *))(v183 + 96))(v1) & 1) == 0
          && v182
          && CMsiBaselineManager::CheckBaselineAgainstPolicy(v182, &v244) )
        {
          v259 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v266 + 288LL))(v266, 8, v244);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v259);
        }
        v184 = 1;
LABEL_249:
        if ( v184 )
        {
          if ( (*(unsigned int (__fastcall **)(struct IMsiEngine *))(*(_QWORD *)v1 + 312LL))(v1) == 2 )
            goto LABEL_221;
          LODWORD(v262) = 0;
          LODWORD(v255) = 0;
          v185 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64 *))(*(_QWORD *)v266 + 184LL))(
                   v266,
                   &v262,
                   &v255);
          if ( (_DWORD)v255 )
            goto LABEL_221;
          if ( v185 == 1 )
          {
            v186 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v266 + 48LL))(v266);
            v260 = v186;
            v187 = v186;
            if ( v186 )
            {
              v261 = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)v186 + 128LL))(v186, 0);
              v188 = v261;
              if ( !v261 )
              {
                v222 = PostError(2283, L"FilesInUse");
                v223 = *(_QWORD *)v1;
                v259 = (__int64)v222;
                v2 = (*(__int64 (__fastcall **)(struct IMsiEngine *, struct IMsiRecord *))(v223 + 208))(v1, v222);
                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v259);
                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v261);
                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v260);
                goto LABEL_221;
              }
              v189 = *(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)v187 + 96LL);
              v190 = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v4 + 120LL))(v4, L"VolumeObject");
              v191 = v189(v187, v190);
              LODWORD(v246) = v191;
              v192 = *(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)v187 + 96LL);
              v193 = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v4 + 120LL))(v4, L"VolumeCost");
              LODWORD(v249) = v192(v187, v193);
              v194 = *(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)v187 + 96LL);
              v195 = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v4 + 120LL))(
                       v4,
                       L"NoRbVolumeCost");
              v196 = v194(v187, v195);
              v184 = 0;
              LODWORD(v247) = v196;
              v243 = 0;
              while ( 1 )
              {
LABEL_256:
                if ( v184 || !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v188 + 40LL))(v188) )
                {
                  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v261);
                  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v260);
                  v2 = 2;
                  goto LABEL_249;
                }
                v197 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v188 + 80LL))(v188, v191);
                v253 = (struct IMsiEngine *)v197;
                v198 = (*(int (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v188 + 56LL))(v188, (unsigned int)v249) / 2;
                v199 = *(_QWORD *)v188;
                v239 = v198;
                LODWORD(v242) = (*(__int64 (__fastcall **)(__int64, _QWORD))(v199 + 56))(v188, (unsigned int)v247);
                v252 = (unsigned __int16 *)((unsigned __int64)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v197 + 72LL))(v197) >> 1);
                if ( v198 <= (unsigned __int64)v252 )
                  goto LABEL_302;
                MsiDirectory = GetMsiDirectory();
                v256 = 0;
                v201 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v3 + 128LL);
                v202 = CComPointer<IEnumMsiRecord>::operator=(&v256);
                v203 = (*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)MsiDirectory + 80LL))(MsiDirectory);
                v257 = (void *)v201(v3, v203, v202);
                if ( v257 )
                  break;
                v204 = v256;
                v205 = (*(__int64 (__fastcall **)(struct IMsiEngine *))(*(_QWORD *)v253 + 96LL))(v253);
                if ( (*(unsigned int (__fastcall **)(CRestartManagerWrapper *))(*(_QWORD *)v204 + 96LL))(v204) != v205
                  || !v269
                  || !CMsiBaselineManager::DisableBaselineForCostReasons(v269, &v244) )
                {
                  break;
                }
                v206 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v266 + 288LL))(v266, 8, v244);
                CComPointer<IMsiDatabase>::operator=(&v257, v206);
                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v257);
                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v256);
                (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)MsiDirectory + 16LL))(MsiDirectory);
                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v253);
                v184 = v243;
                v191 = v246;
              }
              v212 = v253;
              v213 = (*(__int64 (__fastcall **)(struct IMsiEngine *, const wchar_t *))(*(_QWORD *)v1 + 184LL))(
                       v1,
                       L"PROMPTROLLBACKCOST");
              v240 = (*(__int64 (__fastcall **)(__int64, __int64, const wchar_t *))(*(_QWORD *)v213 + 200LL))(
                       v213,
                       1,
                       L"D");
              v237 = (*(__int64 (__fastcall **)(__int64, __int64, const wchar_t *))(*(_QWORD *)v213 + 200LL))(
                       v213,
                       1,
                       L"F");
              v214 = (*(__int64 (__fastcall **)(struct IMsiEngine *))(*(_QWORD *)v212 + 168LL))(v212);
              v216 = v214;
              if ( (_DWORD)v262 == 1 || v237 )
              {
                v238 = 117440517;
                if ( v240 )
                {
                  v215 = (unsigned int)((int)v242 >> 31);
                  LODWORD(v215) = (int)v242 % 2;
                  v239 = (int)v242 / 2;
                }
                v218 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v214 + 80LL))(
                                                   v214,
                                                   v215);
                v219 = 1601;
              }
              else
              {
                if ( v240 )
                {
                  v238 = 0;
                  v243 = 0;
                  (*(void (__fastcall **)(struct IMsiEngine *, __int64))(*(_QWORD *)v1 + 104LL))(v1, 8);
                  v217 = 0;
                  goto LABEL_293;
                }
                v238 = 117440514;
                v218 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v214 + 80LL))(v214);
                v219 = 1605;
              }
              v217 = PostOutOfDiskSpaceError(v219, v218, v239, (unsigned __int64)v252);
LABEL_293:
              CComPointer<IMsiDatabase>::operator=(&v241, v217);
              if ( v241 )
              {
                v220 = (*(__int64 (__fastcall **)(struct IMsiEngine *, _QWORD))(*(_QWORD *)v1 + 24LL))(v1, v238);
                switch ( v220 )
                {
                  case 2:
                  case 3:
                    v221 = PostError(1602);
                    CComPointer<IMsiDatabase>::operator=(&v241, v221);
                    if ( (*(unsigned int (__fastcall **)(struct IMsiEngine *, __int64, __int64))(*(_QWORD *)v1 + 24LL))(
                           v1,
                           50331908,
                           v241) != 7 )
                    {
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v216 + 16LL))(v216);
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v213 + 16LL))(v213);
                      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v257);
                      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v256);
                      (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)MsiDirectory + 16LL))(MsiDirectory);
                      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v253);
                      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v261);
                      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v260);
                      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v245);
                      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v248);
                      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v250);
                      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v241);
                      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v251);
                      v2 = 2;
                      goto LABEL_320;
                    }
                    break;
                  case 4:
                    break;
                  case 5:
                    v243 = 0;
                    (*(void (__fastcall **)(struct IMsiEngine *, __int64, _QWORD))(*(_QWORD *)v1 + 104LL))(v1, 8, 0);
                    goto LABEL_301;
                  default:
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v216 + 16LL))(v216);
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v213 + 16LL))(v213);
                    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v257);
                    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v256);
                    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)MsiDirectory + 16LL))(MsiDirectory);
                    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v253);
                    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v261);
                    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v260);
                    goto LABEL_277;
                }
                v243 = 1;
              }
LABEL_301:
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v216 + 16LL))(v216);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v213 + 16LL))(v213);
              CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v257);
              CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v256);
              (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)MsiDirectory + 16LL))(MsiDirectory);
              v191 = v246;
LABEL_302:
              CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v253);
              v184 = v243;
              goto LABEL_256;
            }
            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v260);
          }
        }
LABEL_308:
        v224 = (*(__int64 (__fastcall **)(struct IMsiEngine *, const unsigned __int16 *))(*(_QWORD *)v1 + 184LL))(
                 v1,
                 L"REMOVE");
        if ( !(*(unsigned int (__fastcall **)(__int64, _QWORD, const unsigned __int16 *))(*(_QWORD *)v224 + 200LL))(
                v224,
                0,
                L"ALL") )
        {
          if ( (*(unsigned int (__fastcall **)(__int64, __int64, const unsigned __int16 *))(*(_QWORD *)v224 + 200LL))(
                 v224,
                 1,
                 L"ALL")
            || !(unsigned int)FFeaturesInstalled(v1, 0) )
          {
            v226 = *(void (__fastcall **)(struct IMsiEngine *, _QWORD, __int64))(*(_QWORD *)v1 + 160LL);
            v227 = *(_QWORD *)MsiString::MsiString((MsiString *)&v269, L"ALL");
            v228 = MsiString::MsiString((MsiString *)&v259, L"REMOVE");
            v226(v1, *(_QWORD *)v228, v227);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v259 + 16LL))(v259);
            (*(void (__fastcall **)(CMsiBaselineManager *))(*(_QWORD *)v269 + 16LL))(v269);
          }
          else if ( (*(unsigned __int8 (__fastcall **)(struct IMsiEngine *, __int64))(*(_QWORD *)v1 + 592LL))(v1, 1) )
          {
            if ( g_dmDiagnosticMode )
              DebugString(
                9,
                0,
                0,
                L"Resolving source for application compatibility with this install.",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                0,
                0);
            v225 = ResolveSource(v1);
            if ( v225 != 1 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v224 + 16LL))(v224);
              CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v245);
              CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v248);
              CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v250);
              CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v241);
              CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v251);
              v2 = v225;
              goto LABEL_320;
            }
          }
        }
        v113 = (*(unsigned int (__fastcall **)(struct IMsiEngine *))(*(_QWORD *)v1 + 312LL))(v1) == 2;
        v229 = *(void (__fastcall **)(__int64))(*(_QWORD *)v224 + 16LL);
        if ( !v113 )
        {
          v229(v224);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v245);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v248);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v250);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v241);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v251);
          v2 = 1;
          goto LABEL_320;
        }
        v229(v224);
        goto LABEL_221;
      }
LABEL_107:
      if ( (_DWORD)v262 )
        goto LABEL_112;
      if ( (unsigned int)ServiceUpdateCausesReboot(v1, v289.strServiceShortName) )
        break;
      if ( g_dmDiagnosticMode )
        DebugString(
          10,
          0,
          0,
          L"RESTART MANAGER: Detected that the service %s will be stopped due to a service control action authored in the "
           "package before the files are updated. So, we will not attempt to stop this service using Restart Manager",
          v289.strServiceShortName,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
LABEL_127:
      ;
    }
    dwProcessId = v289.Process.dwProcessId;
LABEL_112:
    if ( v289.ApplicationType == RmCritical )
    {
      if ( !g_dmDiagnosticMode )
        goto LABEL_238;
      v180 = L"RESTART MANAGER: Did detect that a critical application holds file[s] in use, so a reboot will be necessary.";
LABEL_237:
      DebugString(10, 0, 0, v180, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
      goto LABEL_238;
    }
    v99 = v235;
    if ( (v235 & 7) == 0 )
    {
      v261 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v3 + 48LL))(v3, v235 + 8);
      (*(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v261 + 200LL))(v261, v50);
      CComPointer<IXMLDOMElement>::operator=(&v247, &v261);
      v50 = v247;
      if ( !v235 )
      {
        v100 = *(void (__fastcall **)(_QWORD *, _QWORD, __int64))(*v247 + 120LL);
        v101 = (*(__int64 (__fastcall **)(struct IMsiEngine *, __int64))(*(_QWORD *)v1 + 416LL))(v1, 1607);
        v100(v50, 0, v101);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v101 + 16LL))(v101);
        v53 = v239;
        v99 = 0;
      }
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v261);
      dwProcessId = v289.Process.dwProcessId;
    }
    v257 = &MsiString::s_NullString;
    v102 = v99 + 1;
    v239 = v99 + 1;
    v103 = *v50;
    if ( v289.strAppName[0] )
    {
      v107 = v50;
      (*(void (__fastcall **)(_QWORD *, __int64, WCHAR *))(v103 + 128))(v50, v102, v289.strAppName);
      MsiString::operator=(&v257, v289.strAppName);
      MsiString::operator+=(&v257, L" (Process Id: ");
      v108 = MsiString::MsiString((MsiString *)&v287, v289.Process.dwProcessId);
      MsiString::operator+=(&v257, v108);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v287 + 16LL))(v287);
      MsiString::operator+=(&v257, L")");
    }
    else
    {
      v104 = *(void (__fastcall **)(_QWORD *, _QWORD, _QWORD))(v103 + 120);
      v105 = MsiString::MsiString((MsiString *)&v279, dwProcessId);
      v104(v50, v239, *(_QWORD *)v105);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v279 + 16LL))(v279);
      MsiString::operator=(&v257, L"Process Id: ");
      v106 = MsiString::MsiString((MsiString *)&v280, v289.Process.dwProcessId);
      MsiString::operator+=(&v257, v106);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v280 + 16LL))(v280);
      v107 = v50;
    }
    v235 = v239 + 1;
    (*(void (__fastcall **)(_QWORD *, _QWORD, void *))(*v107 + 120LL))(v107, v239 + 1, v257);
    if ( v53 && v53 + 3 <= (*(unsigned int (__fastcall **)(__int64 *))(*v51 + 24))(v51) )
      goto LABEL_126;
    if ( v53 + 9 <= 0xFFFF )
    {
      v261 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 48LL))(v3);
      (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v261 + 200LL))(v261, v51);
      CComPointer<IXMLDOMElement>::operator=(&v249, &v261);
      v51 = v249;
      if ( !v53 )
      {
        v109 = *(void (__fastcall **)(__int64 *, _QWORD, __int64))(*v249 + 120);
        v110 = (*(__int64 (__fastcall **)(struct IMsiEngine *, __int64))(*(_QWORD *)v1 + 416LL))(v1, 1607);
        v109(v51, 0, v110);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v110 + 16LL))(v110);
        (*(void (__fastcall **)(__int64 *, __int64, _QWORD))(*v51 + 104))(v51, 1, v231);
        v53 = 1;
      }
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v261);
LABEL_126:
      v111 = v53 + 1;
      (*(void (__fastcall **)(__int64 *, _QWORD, _QWORD))(*v51 + 104))(v51, v111++, v289.Process.dwProcessId);
      (*(void (__fastcall **)(__int64 *, _QWORD, _QWORD))(*v51 + 104))(
        v51,
        v111,
        v289.Process.ProcessStartTime.dwHighDateTime);
      v112 = *v51;
      v53 = v111 + 1;
      v239 = v53;
      (*(void (__fastcall **)(__int64 *, _QWORD, _QWORD))(v112 + 104))(
        v51,
        v53,
        v289.Process.ProcessStartTime.dwLowDateTime);
      memset_0(&v289, 0, sizeof(v289));
      (*(void (__fastcall **)(void *))(*(_QWORD *)v257 + 16LL))(v257);
      v94 = v256;
      goto LABEL_127;
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)v257 + 16LL))(v257);
    v94 = v256;
LABEL_129:
    if ( !v51 )
      goto LABEL_243;
    v113 = (*((_BYTE *)v94 + 784) & 8) == 0;
    v114 = v243;
    if ( !v113 && !(_BYTE)v243 )
      goto LABEL_142;
    v115 = (*(__int64 (__fastcall **)(struct IMsiEngine *, __int64, __int64 *))(*(_QWORD *)v1 + 24LL))(
             v1,
             419430400,
             v51);
    if ( v115 != 7 )
    {
      if ( v115 != 1 )
      {
        v2 = 2;
        if ( v115 == 2 )
          goto LABEL_228;
        if ( v115 == 5 )
        {
          if ( g_dmDiagnosticMode )
            goto LABEL_279;
          goto LABEL_243;
        }
        if ( (v115 & 0xFFFFFFFB) != 0 )
        {
          if ( v115 != 0x3FFF && g_dmDiagnosticMode )
            DebugString(
              10,
              0,
              0,
              L"RESTART MANAGER: %s is an unexpected return value for imtRMFilesInUse message!",
              (const unsigned __int16 *)v115,
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              0,
              0);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v242);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v249);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v247);
LABEL_277:
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v245);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v248);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v250);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v241);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v251);
          v2 = 3;
          goto LABEL_320;
        }
        goto LABEL_142;
      }
LABEL_149:
      v122 = *(_QWORD *)v1;
      v246 = 0;
      v263 = &MsiString::s_NullString;
      v265 = &MsiString::s_NullString;
      v123 = *(void (__fastcall **)(struct IMsiEngine *, const WCHAR *, void **, void **))(v122 + 792);
      (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
      v265 = &MsiString::s_NullString;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v263 + 16LL))(v263);
      v263 = &MsiString::s_NullString;
      v123(v1, L"ShutdownApplications", &v263, &v265);
      v124 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 48LL))(v3, 3);
      CComPointer<IMsiDatabase>::operator=(&v246, v124);
      v125 = v246;
      (*(void (__fastcall **)(__int64, __int64, const WCHAR *))(*(_QWORD *)v246 + 128LL))(
        v246,
        1,
        L"ShutdownApplications");
      v2 = 2;
      (*(void (__fastcall **)(__int64, __int64, void *))(*(_QWORD *)v125 + 120LL))(v125, 2, v263);
      (*(void (__fastcall **)(__int64, __int64, void *))(*(_QWORD *)v125 + 120LL))(v125, 3, v265);
      if ( (*(unsigned int (__fastcall **)(struct IMsiEngine *, __int64, __int64))(*(_QWORD *)v1 + 24LL))(
             v1,
             0x8000000,
             v125) != 2 )
      {
        v126 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 48LL))(v3, 3);
        v255 = v126;
        (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v126 + 104LL))(v126, 1, 3);
        v127 = *(__int64 (__fastcall **)(struct IMsiEngine *, _QWORD))(*(_QWORD *)v1 + 192LL);
        v128 = MsiString::MsiString((MsiString *)&v281, L"MSIRMSHUTDOWN");
        LODWORD(v127) = v127(v1, *(_QWORD *)v128);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v281 + 16LL))(v281);
        v129 = (_DWORD)v127 - 1;
        if ( v129 )
        {
          if ( v129 == 1 )
            v130 = 16;
          else
            v130 = 0;
        }
        else
        {
          v130 = 1;
        }
        (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v126 + 104LL))(v126, 2, v130);
        v131 = *(__int64 (__fastcall **)(struct IMsiEngine *, _QWORD))(*(_QWORD *)v1 + 192LL);
        v132 = MsiString::MsiString((MsiString *)&v282, L"MSIDISABLERMRESTART");
        LODWORD(v131) = v131(v1, *(_QWORD *)v132);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v282 + 16LL))(v282);
        (*(void (__fastcall **)(__int64, __int64, bool))(*(_QWORD *)v126 + 104LL))(v126, 3, (_DWORD)v131 == 1);
        v133 = *(__int64 (__fastcall **)(CRestartManagerWrapper *, _QWORD, __int64))(*(_QWORD *)v256 + 16LL);
        LOBYTE(v131) = (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v126 + 56LL))(v126, 3) == 1;
        v134 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v126 + 56LL))(v126, 2);
        LOBYTE(v135) = (_BYTE)v131;
        v136 = v133(v256, v134, v135);
        v137 = v136;
        if ( v136 )
        {
          if ( g_dmDiagnosticMode )
            DebugString(
              10,
              0,
              0,
              L"RESTART MANAGER: Failed to shut down all applications in the service's session. Error: %d",
              (const unsigned __int16 *)v136,
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
            L"RESTART MANAGER: Successfully shut down all applications in the service's session that held files in use.",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        }
        v138 = (*(__int64 (__fastcall **)(struct IMsiEngine *, __int64, __int64))(*(_QWORD *)v1 + 24LL))(
                 v1,
                 402653184,
                 v126);
        if ( !v231 || v138 == 1 && !v137 )
        {
          if ( v138 != 1 )
            goto LABEL_171;
          (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v126 + 104LL))(v126, 1, 4);
          while ( 1 )
          {
            v138 = (*(__int64 (__fastcall **)(struct IMsiEngine *, __int64, __int64))(*(_QWORD *)v1 + 24LL))(
                     v1,
                     402653184,
                     v126);
            if ( v138 != 4 )
              break;
            Sleep(0x1F4u);
          }
          if ( (v138 != 1 || v137) && !v231 )
          {
LABEL_171:
            if ( v138 != 7 && !v137 )
            {
              CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v255);
              (*(void (__fastcall **)(void *))(*(_QWORD *)v265 + 16LL))(v265);
              (*(void (__fastcall **)(void *))(*(_QWORD *)v263 + 16LL))(v263);
              CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v246);
              goto LABEL_142;
            }
            if ( (_BYTE)v243 )
            {
              v207 = PostError(1611);
              CComPointer<IMsiDatabase>::operator=(&v241, v207);
              v2 = 2;
              if ( (*(unsigned int (__fastcall **)(struct IMsiEngine *, __int64, __int64))(*(_QWORD *)v1 + 24LL))(
                     v1,
                     50331953,
                     v241) != 2 )
              {
                if ( g_dmDiagnosticMode )
                  DebugString(
                    10,
                    0,
                    0,
                    L"RESTART MANAGER: The user chose to go on with the installation, although a reboot will be required.",
                    L"(NULL)",
                    L"(NULL)",
                    L"(NULL)",
                    L"(NULL)",
                    L"(NULL)",
                    L"(NULL)",
                    0,
                    0);
                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v255);
                (*(void (__fastcall **)(void *))(*(_QWORD *)v265 + 16LL))(v265);
                (*(void (__fastcall **)(void *))(*(_QWORD *)v263 + 16LL))(v263);
                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v246);
                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v242);
                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v249);
                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v247);
                goto LABEL_244;
              }
              CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v255);
              goto LABEL_267;
            }
            if ( g_dmDiagnosticMode )
              DebugString(
                10,
                0,
                0,
                L"RESTART MANAGER: Failed to shutdown all applications. Might result in a reboot.",
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
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v255);
        (*(void (__fastcall **)(void *))(*(_QWORD *)v265 + 16LL))(v265);
        (*(void (__fastcall **)(void *))(*(_QWORD *)v263 + 16LL))(v263);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v246);
        goto LABEL_243;
      }
LABEL_267:
      (*(void (__fastcall **)(void *))(*(_QWORD *)v265 + 16LL))(v265);
      (*(void (__fastcall **)(void *))(*(_QWORD *)v263 + 16LL))(v263);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v246);
      goto LABEL_228;
    }
    if ( v231 )
      goto LABEL_149;
    if ( v114 )
    {
      v116 = PostError(1610);
      CComPointer<IMsiDatabase>::operator=(&v241, v116);
      v2 = 2;
      if ( (*(unsigned int (__fastcall **)(struct IMsiEngine *, __int64, __int64))(*(_QWORD *)v1 + 24LL))(
             v1,
             50331969,
             v241) == 2 )
        goto LABEL_228;
      if ( g_dmDiagnosticMode )
        goto LABEL_279;
      goto LABEL_243;
    }
LABEL_142:
    if ( v50 )
    {
LABEL_143:
      v117 = v242;
      goto LABEL_144;
    }
LABEL_173:
    v139 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v4 + 72LL);
    v140 = MsiString::MsiString((MsiString *)&v283, L"FilesInUse");
    LODWORD(v139) = v139(v4, *(_QWORD *)v140);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v283 + 16LL))(v283);
    if ( !(_DWORD)v139 )
      goto LABEL_143;
    v264 = 0;
    v141 = *(void (__fastcall **)(__int64, _QWORD, _QWORD, __int64))(*(_QWORD *)v4 + 80LL);
    v142 = CComPointer<IEnumMsiRecord>::operator=(&v264);
    v143 = MsiString::MsiString((MsiString *)&v284, L"FilesInUse");
    v141(v4, *(_QWORD *)v143, 0, v142);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v284 + 16LL))(v284);
    v144 = v264;
    v145 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v264 + 96LL);
    v146 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v4 + 120LL))(v4, L"FileName");
    v147 = v145(v144, v146);
    v148 = v264;
    LODWORD(v262) = v147;
    v149 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v264 + 96LL);
    v150 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v4 + 120LL))(v4, L"FilePath");
    v151 = v149(v148, v150);
    v152 = v264;
    LODWORD(v255) = v151;
    v153 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v264 + 96LL);
    v154 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v4 + 120LL))(v4, L"ProcessID");
    v155 = v153(v152, v154);
    v239 = v155;
    v156 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v264 + 128LL))(v264, 0);
    CComPointer<IMsiDatabase>::operator=(&v242, v156);
    v117 = v242;
    if ( !v242 )
    {
      v210 = PostError(2283, L"FilesInUse");
      v211 = *(_QWORD *)v1;
      v259 = (__int64)v210;
      v2 = (*(__int64 (__fastcall **)(struct IMsiEngine *, struct IMsiRecord *))(v211 + 208))(v1, v210);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v259);
      goto LABEL_283;
    }
    v157 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v264 + 128LL))(v264, 0);
    v261 = (__int64)v157;
    v158 = v157;
    if ( !v157 )
    {
      v208 = PostError(2283, L"FilesInUse");
      v209 = *(_QWORD *)v1;
      v259 = (__int64)v208;
      v2 = (*(__int64 (__fastcall **)(struct IMsiEngine *, struct IMsiRecord *))(v209 + 208))(v1, v208);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v259);
      goto LABEL_281;
    }
    v159 = *v157;
    v160 = v155 ? (unsigned int)(1 << (v155 - 1)) : 0LL;
    (*(void (__fastcall **)(_QWORD *, __int64))(v159 + 48))(v158, v160);
    v246 = v3;
    InstallValidate_::_256_::CEnsureReleaseFileUseObj::StartAfresh(&v246);
    v240 = 0;
    v2 = 2;
LABEL_180:
    if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v117 + 40LL))(v117) )
      break;
    if ( v50 && g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        L"%d application(s) had been reported to have files in use.",
        (const unsigned __int16 *)(v240 / 2),
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    InstallValidate_::_256_::CEnsureReleaseFileUseObj::StartAfresh(&v246);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v261);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v264);
LABEL_144:
    v118 = 0;
    v239 = 0;
    if ( v50 )
    {
      v119 = (*(__int64 (__fastcall **)(struct IMsiEngine *, __int64, _QWORD *))(*(_QWORD *)v1 + 24LL))(
               v1,
               83886080,
               v50);
      if ( v117 )
      {
        v120 = *(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v4 + 96LL);
        v121 = MsiString::MsiString((MsiString *)&v259, L"FilesInUse");
        v120(v4, *(_QWORD *)v121, 0);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v259 + 16LL))(v259);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v117 + 32LL))(v117);
        while ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v117 + 40LL))(v117) )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v117 + 184LL))(v117);
        v118 = 0;
      }
      v2 = 2;
      if ( v119 == 4 )
      {
        v118 = 1;
        v239 = 1;
      }
      else if ( v119 == 2 )
      {
        goto LABEL_228;
      }
    }
    else
    {
      v2 = 2;
    }
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v242);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v249);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v247);
    if ( !v118 )
      goto LABEL_244;
    Instance = v256;
    v44 = v239;
  }
  if ( (*(unsigned int (__fastcall **)(struct IMsiEngine *))(*(_QWORD *)v1 + 312LL))(v1) == 2 )
    goto LABEL_186;
  if ( (*(unsigned int (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v117 + 56LL))(v117, v239) != 0x80000000 )
    goto LABEL_180;
  v161 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v117 + 64LL))(v117, (unsigned int)v262);
  v162 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v242 + 64LL))(v242, (unsigned int)v255);
  v268 = 0;
  v163 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v3 + 176LL);
  v164 = CComPointer<IEnumMsiRecord>::operator=(&v268);
  v165 = v163(v3, v161, v164);
  CComPointer<IMsiDatabase>::operator=(&v241, v165);
  if ( !v241 )
  {
    v166 = v268;
    if ( v268 )
    {
      v167 = v250;
      v260 = 0;
      while ( 1 )
      {
        v252 = *(unsigned __int16 **)(*(_QWORD *)v166 + 24LL);
        v168 = CComPointer<IEnumMsiRecord>::operator=(&v260);
        if ( ((unsigned int (__fastcall *)(__int64, __int64, __int64))v252)(v166, 1, v168) )
          break;
        v169 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)v260 + 80LL))(v260, 1);
        MsiString::MsiString((MsiString *)&v271, v169);
        v170 = &MsiString::s_NullString;
        v236 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)v260 + 56LL))(v260, 2);
        if ( v236 == GetCurrentProcessId()
          || (v244 |= 2u,
              v252 = *(unsigned __int16 **)(*(_QWORD *)v253 + 192LL),
              v171 = MsiString::MsiString((MsiString *)&v285, L"CLIENTPROCESSID"),
              v232 = 1,
              v236 == ((unsigned int (__fastcall *)(struct IMsiEngine *, _QWORD))v252)(v253, *(_QWORD *)v171)) )
        {
          v232 = 0;
        }
        if ( (v244 & 2) != 0 )
        {
          v244 &= ~2u;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v285 + 16LL))(v285);
        }
        if ( v232 )
        {
          v170 = (void *)(*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v271 + 176LL))(v271, 6, 92);
          (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
          if ( !(*(unsigned int (__fastcall **)(void *, __int64, const wchar_t *))(*(_QWORD *)v170 + 200LL))(
                  v170,
                  3,
                  L"explorer")
            && !(*(unsigned int (__fastcall **)(void *, __int64, const wchar_t *))(*(_QWORD *)v170 + 200LL))(
                  v170,
                  3,
                  L"msiexec") )
          {
            (*(void (__fastcall **)(_QWORD *))(*v158 + 32LL))(v158);
            (*(void (__fastcall **)(_QWORD *, _QWORD, __int64))(*v158 + 96LL))(v158, (unsigned int)v262, v161);
            (*(void (__fastcall **)(_QWORD *, _QWORD, __int64))(*v158 + 96LL))(v158, (unsigned int)v255, v162);
            (*(void (__fastcall **)(_QWORD *, _QWORD, _QWORD))(*v158 + 88LL))(v158, v239, v236);
            if ( !(*(unsigned int (__fastcall **)(_QWORD *))(*v158 + 40LL))(v158) )
            {
              (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v242 + 88LL))(v242, v239, v236);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v242 + 136LL))(v242);
              v172 = v240;
              if ( !(v240 % 8) )
              {
                v252 = (unsigned __int16 *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v3 + 48LL))(
                                             v3,
                                             (unsigned int)(v240 + 8));
                (*(void (__fastcall **)(unsigned __int16 *, _QWORD *))(*(_QWORD *)v252 + 200LL))(v252, v50);
                CComPointer<IXMLDOMElement>::operator=(&v247, &v252);
                v50 = v247;
                if ( !v240 )
                {
                  v286 = *(void (__fastcall **)(_QWORD *, _QWORD, _QWORD))(*v247 + 120LL);
                  v272 = (void (__fastcall *)(__int64, __int64, _QWORD))(*(__int64 (__fastcall **)(struct IMsiEngine *, __int64))(*(_QWORD *)v253 + 416LL))(
                                                                          v253,
                                                                          1607);
                  v286(v50, 0, v272);
                  (*(void (__fastcall **)(void (__fastcall *)(__int64, __int64, _QWORD)))(*(_QWORD *)v272 + 16LL))(v272);
                }
                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v252);
                v172 = v240;
              }
              v173 = *v50;
              v240 = v172 + 1;
              (*(void (__fastcall **)(_QWORD *, _QWORD, __int64))(v173 + 120))(v50, (unsigned int)(v172 + 1), v271);
              v174 = *v50;
              (*(void (__fastcall **)(_QWORD *, _QWORD, _QWORD))(v174 + 104))(v50, (unsigned int)++v240, v236);
            }
          }
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v167 + 160LL))(v167);
        (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v167 + 104LL))(v167, 1, 1603);
        (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v167 + 120LL))(v167, 2, v162);
        (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v167 + 120LL))(v167, 3, v161);
        (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v167 + 120LL))(v167, 4, v271);
        (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v167 + 104LL))(v167, 5, v236);
        v272 = *(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v167 + 120LL);
        v175 = MsiString::MsiString((MsiString *)&v269, L"(not determined yet)");
        v272(v167, 6, *(_QWORD *)v175);
        (*(void (__fastcall **)(CMsiBaselineManager *))(*(_QWORD *)v269 + 16LL))(v269);
        (*(void (__fastcall **)(struct IMsiEngine *, __int64, __int64))(*(_QWORD *)v253 + 24LL))(v253, 0x4000000, v167);
        (*(void (__fastcall **)(void *))(*(_QWORD *)v170 + 16LL))(v170);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v271 + 16LL))(v271);
        v166 = v268;
      }
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v260);
      v4 = v270;
    }
    v2 = 2;
    goto LABEL_207;
  }
  v2 = 2;
  if ( (*(unsigned int (__fastcall **)(struct IMsiEngine *, __int64))(*(_QWORD *)v253 + 24LL))(v253, 0x4000000) != 2 )
  {
LABEL_207:
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v268);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v162 + 16LL))(v162);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v161 + 16LL))(v161);
    v1 = v253;
    v117 = v242;
    goto LABEL_180;
  }
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v268);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v162 + 16LL))(v162);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v161 + 16LL))(v161);
LABEL_186:
  InstallValidate_::_256_::CEnsureReleaseFileUseObj::StartAfresh(&v246);
LABEL_281:
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v261);
LABEL_283:
  v179 = &v264;
LABEL_227:
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v179);
LABEL_228:
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v242);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v249);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v247);
LABEL_221:
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v245);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v248);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v250);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v241);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v251);
LABEL_320:
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v266);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v270);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v274);
  return v2;
}

```

## disassembly

```asm
0x180165870  push    rbp
0x180165872  push    rbx
0x180165873  push    rsi
0x180165874  push    rdi
0x180165875  push    r12
0x180165877  push    r13
0x180165879  push    r14
0x18016587b  push    r15
0x18016587d  lea     rbp, [rsp-778h]
0x180165885  sub     rsp, 878h
0x18016588c  mov     rax, cs:__security_cookie
0x180165893  xor     rax, rsp
0x180165896  mov     [rbp+7B0h+var_50], rax
0x18016589d  xor     edi, edi
0x18016589f  mov     [rbp+7B0h+var_7E8], rcx
0x1801658a3  mov     dword ptr [rsp+8B0h+var_838], edi
0x1801658a7  mov     r12, rcx
0x1801658aa  lea     r14d, [rdi+2]
0x1801658ae  cmp     cs:?g_scServerContext@@3W4scEnum@@A, r14d; scEnum g_scServerContext
0x1801658b5  jnz     short loc_1801658DE
0x1801658b7  mov     rax, [rcx]
0x1801658ba  mov     rax, [rax+1B0h]
0x1801658c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801658c6  test    al, al
0x1801658c8  jnz     short loc_1801658DE
0x1801658ca  mov     rcx, cs:qword_1803136E0; this
0x1801658d1  test    rcx, rcx
0x1801658d4  jz      short loc_1801658DE
0x1801658d6  mov     rdx, r12; struct IMsiEngine *
0x1801658d9  call    ?RecordInstallType@CMsiSQMSession@@QEAAXAEAVIMsiEngine@@@Z; CMsiSQMSession::RecordInstallType(IMsiEngine &)
0x1801658de  mov     rax, [r12]
0x1801658e2  mov     rcx, r12
0x1801658e5  mov     rax, [rax+38h]
0x1801658e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801658ee  mov     r13, rax
0x1801658f1  mov     [rbp+7B0h+var_740], rax
0x1801658f5  mov     rax, [r12]
0x1801658f9  mov     rcx, r12
0x1801658fc  mov     rax, [rax+48h]
0x180165900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180165905  lea     r8, IID_IMsiSelectionManager
0x18016590c  mov     [rbp+7B0h+var_760], rax
0x180165910  mov     rdx, r12
0x180165913  lea     rcx, [rbp+7B0h+var_780]
0x180165917  mov     r15, rax
0x18016591a  call    ??0?$CComPointer@VIMsiSelectionManager@@@@QEAA@AEAUIUnknown@@AEBU_GUID@@@Z; CComPointer<IMsiSelectionManager>::CComPointer<IMsiSelectionManager>(IUnknown &,_GUID const &)
0x18016591f  mov     rax, [r12]
0x180165923  mov     rcx, r12
0x180165926  mov     rax, [rax+138h]
0x18016592d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180165932  cmp     eax, r14d
0x180165935  jz      loc_1801689B0
0x18016593b  mov     rax, [r12]
0x18016593f  lea     rdx, aMsirestartmana_0; "MsiRestartManagerSessionKey"
0x180165946  lea     rcx, [rbp+7B0h+var_7F0]; this
0x18016594a  mov     rbx, [rax+0A0h]
0x180165951  call    ??0MsiString@@QEAA@AEBG@Z; MsiString::MsiString(ushort const &)
0x180165956  lea     r8, ?g_MsiStringNull@@3VCMsiStringNull@@B; CMsiStringNull const g_MsiStringNull
0x18016595d  mov     rcx, r12
0x180165960  mov     rdx, [rax]
0x180165963  mov     rax, rbx
0x180165966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016596b  mov     rcx, [rbp+7B0h+var_7F0]
0x18016596f  mov     rax, [rcx]
0x180165972  mov     rax, [rax+10h]
0x180165976  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016597b  mov     rax, [r13+0]
0x18016597f  mov     edx, r14d
0x180165982  mov     rcx, r13
0x180165985  mov     rax, [rax+30h]
0x180165989  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016598e  mov     [rbp+7B0h+var_7F8], rax
0x180165992  mov     edx, 6
0x180165997  mov     [rsp+8B0h+var_840], rdi
0x18016599c  mov     rcx, r13
0x18016599f  mov     rax, [r13+0]
0x1801659a3  mov     rax, [rax+30h]
0x1801659a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801659ac  mov     [rbp+7B0h+var_810], rdi
0x1801659b0  lea     rcx, [rbp+7B0h+var_810]
0x1801659b4  mov     [rbp+7B0h+var_828], rdi
0x1801659b8  mov     esi, edi
0x1801659ba  mov     [rbp+7B0h+var_800], rax
0x1801659be  mov     rax, [r15]
0x1801659c1  mov     byte ptr [rbp+7B0h+var_830], dil
0x1801659c5  mov     rdi, [rax+50h]
0x1801659c9  call    ??4?$CComPointer@VIEnumMsiRecord@@@@QEAAAEAV0@PEAVIEnumMsiRecord@@@Z; CComPointer<IEnumMsiRecord>::operator=(IEnumMsiRecord *)
0x1801659ce  lea     rdx, aDialog; "Dialog"
0x1801659d5  mov     rbx, rax
0x1801659d8  lea     rcx, [rbp+7B0h+var_7F0]; this
0x1801659dc  call    ??0MsiString@@QEAA@AEBG@Z; MsiString::MsiString(ushort const &)
0x1801659e1  mov     r9, rbx
0x1801659e4  xor     r8d, r8d
0x1801659e7  mov     rcx, r15
0x1801659ea  mov     rdx, [rax]
0x1801659ed  mov     rax, rdi
0x1801659f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801659f5  mov     rdx, rax
0x1801659f8  lea     rcx, [rsp+8B0h+var_840]
0x1801659fd  call    ??4?$CComPointer@VIMsiDatabase@@@@QEAAAEAV0@PEAVIMsiDatabase@@@Z; CComPointer<IMsiDatabase>::operator=(IMsiDatabase *)
0x180165a02  cmp     [rax], rsi
0x180165a05  jnz     short loc_180165A65
0x180165a07  mov     rcx, [rbp+7B0h+var_810]
0x180165a0b  xor     edx, edx
0x180165a0d  mov     rax, [rcx]
0x180165a10  mov     rax, [rax+80h]
0x180165a17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180165a1c  mov     rdx, rax
0x180165a1f  lea     rcx, [rbp+7B0h+var_828]
0x180165a23  call    ??4?$CComPointer@VIMsiDatabase@@@@QEAAAEAV0@PEAVIMsiDatabase@@@Z; CComPointer<IMsiDatabase>::operator=(IMsiDatabase *)
0x180165a28  cmp     [rax], rsi
0x180165a2b  jz      short loc_180165A65
0x180165a2d  mov     rdi, [rbp+7B0h+var_810]
0x180165a31  lea     rdx, aDialog_0; "Dialog"
0x180165a38  mov     rcx, r15
0x180165a3b  mov     rax, [rdi]
0x180165a3e  mov     rbx, [rax+60h]
0x180165a42  mov     rax, [r15]
0x180165a45  mov     rax, [rax+78h]
0x180165a49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180165a4e  mov     edx, eax
0x180165a50  mov     rcx, rdi
0x180165a53  mov     rax, rbx
0x180165a56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180165a5b  mov     esi, eax
0x180165a5d  test    eax, eax
0x180165a5f  jz      short loc_180165A65
0x180165a61  mov     bl, 1
0x180165a63  jmp     short loc_180165A67
0x180165a65  xor     bl, bl
0x180165a67  mov     rcx, [rbp+7B0h+var_7F0]
0x180165a6b  mov     rax, [rcx]
0x180165a6e  mov     rax, [rax+10h]
0x180165a72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180165a77  test    bl, bl
0x180165a79  jz      short loc_180165AEB
0x180165a7b  mov     rcx, [rbp+7B0h+var_828]
0x180165a7f  mov     edx, esi
0x180165a81  mov     rax, [rcx]
0x180165a84  mov     rax, [rax+30h]
0x180165a88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180165a8d  mov     rdi, [rbp+7B0h+var_828]
0x180165a91  lea     rdx, aMsirmfilesinus; "MsiRMFilesInUse"
0x180165a98  lea     rcx, [rbp+7B0h+var_7F0]; this
0x180165a9c  mov     rax, [rdi]
0x180165a9f  mov     rbx, [rax+60h]
0x180165aa3  call    ??0MsiString@@QEAA@PEBG@Z; MsiString::MsiString(ushort const *)
0x180165aa8  mov     edx, esi
0x180165aaa  mov     rcx, rdi
0x180165aad  mov     r8, [rax]
0x180165ab0  mov     rax, rbx
0x180165ab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180165ab8  mov     rcx, [rbp+7B0h+var_7F0]
0x180165abc  mov     rax, [rcx]
0x180165abf  mov     rax, [rax+10h]
0x180165ac3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180165ac8  mov     rcx, [rbp+7B0h+var_828]
0x180165acc  mov     rax, [rcx]
0x180165acf  mov     rax, [rax+28h]
0x180165ad3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180165ad8  mov     ecx, [rbp+7B0h+var_830]
0x180165adb  test    eax, eax
0x180165add  movzx   ecx, cl
0x180165ae0  mov     eax, 1
0x180165ae5  cmovnz  ecx, eax
0x180165ae8  mov     [rbp+7B0h+var_830], ecx
0x180165aeb  mov     ecx, 0Ah; int
0x180165af0  call    ?FDiagnosticModeSet@@YA_NH@Z; FDiagnosticModeSet(int)
0x180165af5  test    al, al
0x180165af7  jz      loc_1801662A5
0x180165afd  movaps  xmm0, xmmword ptr cs:aSelectFeatureA; " SELECT `Feature`, `Action`, `ActionReq"...
0x180165b04  movaps  xmm1, xmmword ptr cs:aSelectFeatureA+10h; "`Feature`, `Action`, `ActionRequested`,"...
0x180165b0b  mov     rax, qword ptr cs:aSelectFeatureA+8Eh; "re`"
0x180165b12  movups  [rbp+7B0h+var_1E0], xmm0
0x180165b19  movaps  xmm0, xmmword ptr cs:aSelectFeatureA+20h; "`, `Action`, `ActionRequested`, `Instal"...
0x180165b20  movups  [rbp+7B0h+var_1C0], xmm0
0x180165b27  movaps  xmm0, xmmword ptr cs:aSelectFeatureA+40h; "tionRequested`, `Installed` FROM `Featu"...
0x180165b2e  movups  [rbp+7B0h+var_1A0], xmm0
0x180165b35  movaps  xmm0, xmmword ptr cs:aSelectFeatureA+60h; "`Installed` FROM `Feature`"
0x180165b3c  movups  [rbp+7B0h+var_180], xmm0
0x180165b43  movaps  xmm0, xmmword ptr cs:aSelectFeatureA+80h; " `Feature`"
0x180165b4a  movups  xmmword ptr [rbp+7B0h+var_160], xmm0
0x180165b51  mov     qword ptr [rbp+7B0h+var_160+0Eh], rax
0x180165b58  xor     eax, eax
0x180165b5a  xorps   xmm0, xmm0
0x180165b5d  mov     [rbp+7B0h+var_11A], ax
0x180165b64  movups  [rbp+7B0h+var_1D0], xmm1
0x180165b6b  mov     [rbp+7B0h+var_5C], rax
0x180165b72  movaps  xmm1, xmmword ptr cs:aSelectFeatureA+30h; "on`, `ActionRequested`, `Installed` FRO"...
0x180165b79  movups  [rbp+7B0h+var_14A], xmm0
0x180165b80  mov     [rbp+7B0h+var_54], eax
0x180165b86  movups  [rbp+7B0h+var_13A], xmm0
0x180165b8d  mov     [rbp+7B0h+var_3B0], rax
0x180165b94  mov     eax, dword ptr cs:aComponent+10h; "t"
0x180165b9a  movups  [rbp+7B0h+var_12A], xmm0
0x180165ba1  mov     [rbp+7B0h+var_398], eax
0x180165ba7  xor     eax, eax
0x180165ba9  movaps  xmm0, xmmword ptr cs:aSelectComponen_13; " SELECT `Component`, `Action`, `ActionR"...
0x180165bb0  movups  [rbp+7B0h+var_1B0], xmm1
0x180165bb7  mov     [rbp+7B0h+var_394], eax
0x180165bbd  mov     eax, dword ptr cs:aAbsent+8; "nt"
0x180165bc3  movaps  xmm1, xmmword ptr cs:aSelectFeatureA+50h; "ested`, `Installed` FROM `Feature`"
0x180165bca  movups  [rbp+7B0h+var_118], xmm0
0x180165bd1  mov     [rbp+7B0h+var_388], eax
0x180165bd7  movzx   eax, word ptr cs:aAbsent+0Ch; ""
0x180165bde  movaps  xmm0, xmmword ptr cs:aSelectComponen_13+20h; "nt`, `Action`, `ActionRequest`, `Instal"...
0x180165be5  movups  [rbp+7B0h+var_190], xmm1
0x180165bec  mov     [rbp+7B0h+var_384], ax
0x180165bf3  movaps  xmm1, xmmword ptr cs:aSelectFeatureA+70h; "ed` FROM `Feature`"
0x180165bfa  mov     eax, dword ptr cs:aLocal+8; "l"
0x180165c00  movups  [rbp+7B0h+var_F8], xmm0
0x180165c07  mov     [rbp+7B0h+var_36A], eax
0x180165c0d  xor     eax, eax
0x180165c0f  movaps  xmm0, xmmword ptr cs:aSelectComponen_13+40h; "ActionRequest`, `Installed`, `TrueInsta"...
0x180165c16  movups  [rbp+7B0h+var_170], xmm1
0x180165c1d  mov     [rbp+7B0h+var_356], ax
0x180165c24  movaps  xmm1, xmmword ptr cs:aSelectComponen_13+10h; "`Component`, `Action`, `ActionRequest`,"...
0x180165c2b  mov     eax, dword ptr cs:aSource_1+8; "ce"
0x180165c31  movups  [rbp+7B0h+var_D8], xmm0
0x180165c38  mov     [rbp+7B0h+var_34C], eax
0x180165c3e  movaps  xmm0, xmmword ptr cs:aSelectComponen_13+60h; "`Installed`, `TrueInstallSt` FROM `Comp"...
0x180165c45  movzx   eax, word ptr cs:aSource_1+0Ch; ""
0x180165c4c  movups  [rbp+7B0h+var_108], xmm1
0x180165c53  movaps  xmm1, xmmword ptr cs:aSelectComponen_13+30h; "tion`, `ActionRequest`, `Installed`, `T"...
0x180165c5a  movups  [rbp+7B0h+var_B8], xmm0
0x180165c61  movaps  xmm0, xmmword ptr cs:aSelectComponen_13+80h; "ueInstallSt` FROM `Component`"
0x180165c68  movups  [rbp+7B0h+var_E8], xmm1
0x180165c6f  movaps  xmm1, xmmword ptr cs:aSelectComponen_13+50h; "quest`, `Installed`, `TrueInstallSt` FR"...
0x180165c76  movups  [rbp+7B0h+var_98], xmm0
0x180165c7d  movaps  xmm0, xmmword ptr cs:aSelectComponen_13+0A0h; "M `Component`"
0x180165c84  movups  [rbp+7B0h+var_C8], xmm1
0x180165c8b  movaps  xmm1, xmmword ptr cs:aSelectComponen_13+70h; "ed`, `TrueInstallSt` FROM `Component`"
0x180165c92  movups  xmmword ptr [rbp+7B0h+var_78], xmm0
0x180165c99  movups  xmm0, xmmword ptr cs:aFeature; "Feature"
0x180165ca0  movups  [rbp+7B0h+var_A8], xmm1
0x180165ca7  movaps  xmm1, xmmword ptr cs:aSelectComponen_13+90h; "lSt` FROM `Component`"
0x180165cae  movdqu  [rbp+7B0h+var_3C0], xmm0
0x180165cb6  movups  xmm0, xmmword ptr cs:aComponent; "Component"
0x180165cbd  movups  [rbp+7B0h+var_88], xmm1
0x180165cc4  movups  xmm1, xmmword ptr cs:aSelectComponen_13+0ACh; "ponent`"
0x180165ccb  movups  [rbp+7B0h+var_3A8], xmm0
0x180165cd2  movsd   xmm0, qword ptr cs:aAbsent; "Absent"
0x180165cda  movups  xmmword ptr [rbp+7B0h+var_78+0Ch], xmm1
0x180165ce1  movsd   xmm1, qword ptr cs:aLocal; "Local"
0x180165ce9  movsd   [rbp+7B0h+var_390], xmm0
0x180165cf1  xorps   xmm0, xmm0
0x180165cf4  movsd   [rbp+7B0h+var_372], xmm1
0x180165cfc  movsd   xmm1, qword ptr cs:aSource_1; "Source"
0x180165d04  movups  [rbp+7B0h+var_382], xmm0
0x180165d0b  movups  [rbp+7B0h+var_366], xmm0
0x180165d12  movsd   [rbp+7B0h+var_354], xmm1
0x180165d1a  movups  xmm1, xmmword ptr cs:aReinstall_1; "Reinstall"
0x180165d21  mov     [rbp+7B0h+var_348], ax
0x180165d28  mov     eax, dword ptr cs:aReinstall_1+10h; "l"
0x180165d2e  mov     [rbp+7B0h+var_326], eax
0x180165d34  xor     eax, eax
0x180165d36  mov     [rbp+7B0h+var_322], rax
0x180165d3d  mov     [rbp+7B0h+var_31A], ax
0x180165d44  mov     eax, dword ptr cs:aAdvertise+10h; "e"
0x180165d4a  mov     [rbp+7B0h+var_308], eax
0x180165d50  xor     eax, eax
0x180165d52  mov     [rbp+7B0h+var_304], rax
0x180165d59  mov     [rbp+7B0h+var_2FC], ax
0x180165d60  mov     [rbp+7B0h+var_2EA], rax
0x180165d67  mov     [rbp+7B0h+var_2E2], eax
0x180165d6d  mov     [rbp+7B0h+var_2DE], ax
0x180165d74  mov     [rbp+7B0h+var_2C6], rax
0x180165d7b  mov     [rbp+7B0h+var_2BE], ax
0x180165d82  mov     [rbp+7B0h+var_2A0], ax
0x180165d89  mov     [rbp+7B0h+var_282], ax
0x180165d90  mov     [rbp+7B0h+var_264], ax
0x180165d97  mov     [rbp+7B0h+var_230], rax
0x180165d9e  movzx   eax, word ptr cs:aNull_1+8; ""
0x180165da5  mov     [rbp+7B0h+var_202], ax
0x180165dac  xor     eax, eax
0x180165dae  mov     [rbp+7B0h+var_1F0], eax
0x180165db4  lea     rax, aNotUsed; "Not Used"
0x180165dbb  mov     [rbp+7B0h+var_6D0], rax
0x180165dc2  lea     rax, aBadConfig; "Bad Config"
0x180165dc9  mov     [rbp+7B0h+var_6C8], rax
0x180165dd0  lea     rax, aIncomplete; "Incomplete"
0x180165dd7  mov     [rbp+7B0h+var_6C0], rax
0x180165dde  lea     rax, aSourceAbsent; "Source Absent"
0x180165de5  mov     [rbp+7B0h+var_6B8], rax
0x180165dec  lea     rax, aMoreData; "More Data"
0x180165df3  movups  [rbp+7B0h+var_346], xmm0
0x180165dfa  mov     [rbp+7B0h+var_6B0], rax
0x180165e01  lea     rax, aInvalidArg; "Invalid Arg"
0x180165e08  movups  xmm0, xmmword ptr cs:aAdvertise; "Advertise"
0x180165e0f  mov     [rbp+7B0h+var_6A8], rax
0x180165e16  lea     rax, aUnknown_2; "Unknown"
0x180165e1d  mov     [rbp+7B0h+var_6A0], rax
0x180165e24  lea     rax, aBroken; "Broken"
0x180165e2b  movups  [rbp+7B0h+var_318], xmm0
0x180165e32  mov     [rbp+7B0h+var_698], rax
0x180165e39  lea     rax, aAdvertisedRemo; "Advertised/Removed"
0x180165e40  movups  xmm0, xmmword ptr cs:aCurrent; "Current"
0x180165e47  mov     [rbp+7B0h+var_690], rax
0x180165e4e  lea     rax, aAbsent; "Absent"
0x180165e55  movups  [rbp+7B0h+var_336], xmm1
  ... truncated ...
```
