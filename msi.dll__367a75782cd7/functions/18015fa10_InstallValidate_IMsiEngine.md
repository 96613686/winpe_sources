# InstallValidate(IMsiEngine &)

- ea: `0x18015fa10`
- end: `0x180162b7f`
- name: `?InstallValidate@@YA?AW4iesEnum@@AEAVIMsiEngine@@@Z`
- size: `12655`
- prototype: ``
- caller_count: `0`
- callee_count: `42`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180025560`
- `0x180025a18`
- `0x180027b54`
- `0x180033e78`
- `0x180035a8c`
- `0x18004295c`
- `0x180061334`
- `0x1800620e4`
- `0x180066074`
- `0x180076e28`
- `0x18008af8c`
- `0x1800a5fc4`
- `0x1800ab728`
- `0x1800b8e10`
- `0x1800c2854`
- `0x1800cb888`
- `0x1800d6ff0`
- `0x1800da080`
- `0x1800e80a4`
- `0x180119a80`
- `0x18011fc38`
- `0x18013a830`
- `0x18014148c`
- `0x1801562b0`
- `0x18015fa10`
- `0x180162b88`
- `0x1801b7d08`
- `0x1801b7df4`
- `0x1801b8154`
- `0x1801b822c`
- `0x1801b824c`
- `0x1801b84fc`
- `0x1802047a0`
- `0x180204f48`
- `0x180218ac0`
- `0x1802220c8`
- `0x1802233e4`
- `0x180223770`
- `0x18023ed50`
- `0x18025ab2a`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `KERNEL32!Sleep` at `0x18016146d`
- `KERNEL32!Sleep` at `0x18016146d`
- `KERNEL32!GetCurrentProcessId` at `0x180160b1d`
- `KERNEL32!GetCurrentProcessId` at `0x180161838`
- `KERNEL32!GetCurrentProcessId` at `0x180160b1d`
- `KERNEL32!GetCurrentProcessId` at `0x180161838`

## string_xrefs

- `0x180160ad5`: `CLIENTPROCESSID`
- `0x180161848`: `CLIENTPROCESSID`
- `0x18016294e`: `REMOVE`
- `0x180162a95`: `REMOVE`
- `0x1801609c4`: `MSICLIENTUSESEXTERNALUI`
- `0x18015fadf`: `MsiRestartManagerSessionKey`
- `0x1801625cb`: `PROMPTROLLBACKCOST`
- `0x180160975`: `RESTART MANAGER: Failed to retrieve the list of applications that hold files in use; Windows Installer will use the built-in FilesInUse functionality. Error: %d`
- `0x18015fc9d`: ` SELECT `Feature`, `Action`, `ActionRequested`, `Installed` FROM `Feature``
- `0x18015fd49`: ` SELECT `Component`, `Action`, `ActionRequest`, `Installed`, `TrueInstallSt` FROM `Component``
- `0x18015fe56`: `Component`
- `0x18015feba`: `Reinstall`
- `0x18015ff70`: `Incomplete`
- `0x18015ff62`: `Bad Config`
- `0x180160304`: `%s: %s; Installed: %s;   Request: %s;   Action: %s;   Client State: %s`
- `0x18015ffd9`: `Advertised/Removed`
- `0x180160899`: `RESTART MANAGER: Failed to add file path resources; Windows Installer will use the built-in FilesInUse functionality. Error: %d`
- `0x1801603e1`: `%s: %s; Installed: %s;   Request: %s;   Action: %s`
- `0x180160a89`: `RESTART MANAGER: Will attempt to shut down and restart applications in no UI modes.`
- `0x180160a29`: `RESTART MANAGER: Will attempt to shut down and restart applications because the UI does not display any modal dialogs.`
- `0x180161e4c`: `RESTART MANAGER: Did detect that the client process of this installation holds file[s] in use, so a reboot will be necessary.`
- `0x180161e68`: `RESTART MANAGER: Did detect that Windows Installer service holds file[s] in use, so a reboot will be necessary.`
- `0x180160be3`: `RESTART MANAGER: Detected that the service %s will be stopped due to a service control action authored in the package before the files are updated. So, we will not attempt to stop this service using Restart Manager`
- `0x18016124b`: `MSIRMSHUTDOWN`
- `0x180162358`: `RESTART MANAGER: The user chose to go on with the installation, although a reboot will be required.`
- `0x180162528`: `RESTART MANAGER: The user chose to go on with the installation, although a reboot will be required.`
- `0x18016137f`: `RESTART MANAGER: Failed to shut down all applications in the service's session. Error: %d`
- `0x1801612bb`: `MSIDISABLERMRESTART`
- `0x1801613be`: `RESTART MANAGER: Successfully shut down all applications in the service's session that held files in use.`
- `0x180161917`: `msiexec`
- `0x1801629f2`: `Resolving source for application compatibility with this install.`
- `0x1801605f5`: `FilePath`
- `0x1801615a1`: `FilePath`
- `0x1801615d2`: `ProcessID`
- `0x18015fc31`: `MsiRMFilesInUse`

## pseudocode

```c
__int64 __fastcall InstallValidate(__int64 a1)
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
  __int64 v51; // rdi
  CRestartManagerWrapper *v52; // rcx
  unsigned int v53; // r14d
  __int64 (__fastcall *v54)(__int64, _QWORD, _QWORD, __int64); // r14
  __int64 v55; // rbx
  MsiString *v56; // rax
  __int64 v57; // rax
  __int64 v58; // rbx
  __int64 v59; // r14
  __int64 (__fastcall *v60)(__int64, _QWORD); // rbx
  unsigned int v61; // eax
  int v62; // eax
  __int64 v63; // r14
  __int64 (__fastcall *v64)(__int64, _QWORD); // rbx
  unsigned int v65; // eax
  __int64 v66; // r14
  signed int v67; // eax
  unsigned __int16 *v68; // rcx
  unsigned int v69; // eax
  unsigned __int64 v70; // kr00_8
  void *v71; // rax
  signed int i; // ebx
  int v73; // eax
  int v74; // r12d
  __int64 v75; // r14
  __int64 v76; // r12
  const struct IMsiString *v77; // rbx
  int v78; // eax
  unsigned int v79; // eax
  unsigned __int64 v80; // kr10_8
  __int64 v81; // rax
  int v82; // eax
  struct IMsiRecord *v83; // rax
  _QWORD *v84; // rbx
  unsigned int v85; // r14d
  unsigned int v86; // eax
  __int64 v87; // rax
  void *v88; // rcx
  unsigned int ApplicationsList; // eax
  __int64 (__fastcall *v90)(struct IMsiEngine *, _QWORD); // rbx
  MsiString *v91; // rax
  const unsigned __int16 *v92; // r9
  __int64 (__fastcall *v93)(struct IMsiEngine *, _QWORD); // rbx
  MsiString *v94; // rax
  int v95; // ebx
  __int64 v96; // rax
  __int64 (__fastcall *v97)(struct IMsiEngine *, _QWORD); // rbx
  MsiString *v98; // rax
  DWORD CurrentProcessId; // eax
  CRestartManagerWrapper *v100; // rbx
  unsigned int j; // eax
  CRestartManagerWrapper *v102; // rcx
  DWORD dwProcessId; // ecx
  int k; // edx
  unsigned int v105; // ebx
  void (__fastcall *v106)(_QWORD *, _QWORD, __int64); // r14
  __int64 v107; // rbx
  __int64 v108; // rdx
  __int64 v109; // rax
  void (__fastcall *v110)(_QWORD *, _QWORD, _QWORD); // rbx
  MsiString *v111; // rax
  MsiString *v112; // rax
  _QWORD *v113; // rbx
  MsiString *v114; // rax
  void (__fastcall *v115)(__int64, _QWORD, __int64); // r14
  __int64 v116; // rbx
  unsigned int v117; // r14d
  __int64 v118; // rax
  bool v119; // zf
  char v120; // bl
  int v121; // eax
  struct IMsiRecord *v122; // rax
  __int64 v123; // rdi
  int v124; // ebx
  int v125; // esi
  void (__fastcall *v126)(__int64, _QWORD, _QWORD); // rbx
  MsiString *v127; // rax
  __int64 v128; // rax
  void (__fastcall *v129)(struct IMsiEngine *, const WCHAR *, void **, void **); // rbx
  __int64 v130; // rax
  __int64 v131; // rbx
  __int64 v132; // rbx
  __int64 (__fastcall *v133)(struct IMsiEngine *, _QWORD); // rdi
  MsiString *v134; // rax
  int v135; // edi
  __int64 v136; // r8
  __int64 (__fastcall *v137)(struct IMsiEngine *, _QWORD); // rdi
  MsiString *v138; // rax
  __int64 (__fastcall *v139)(CRestartManagerWrapper *, _QWORD, __int64); // r14
  unsigned int v140; // eax
  __int64 v141; // r8
  unsigned int v142; // eax
  unsigned int v143; // edi
  int v144; // eax
  __int64 (__fastcall *v145)(__int64, _QWORD); // rbx
  MsiString *v146; // rax
  void (__fastcall *v147)(__int64, _QWORD, _QWORD, __int64); // rdi
  __int64 v148; // rbx
  MsiString *v149; // rax
  __int64 v150; // rdi
  __int64 (__fastcall *v151)(__int64, _QWORD); // rbx
  unsigned int v152; // eax
  int v153; // eax
  __int64 v154; // rdi
  __int64 (__fastcall *v155)(__int64, _QWORD); // rbx
  unsigned int v156; // eax
  int v157; // eax
  __int64 v158; // rdi
  __int64 (__fastcall *v159)(__int64, _QWORD); // rbx
  unsigned int v160; // eax
  unsigned int v161; // r14d
  __int64 v162; // rax
  _QWORD *v163; // rax
  _QWORD *v164; // rbx
  __int64 v165; // rax
  __int64 v166; // rdx
  __int64 v167; // rdi
  __int64 v168; // r12
  __int64 (__fastcall *v169)(__int64, __int64, __int64); // r14
  __int64 v170; // rax
  __int64 v171; // rax
  __int64 v172; // r14
  __int64 v173; // r15
  __int64 v174; // rax
  const unsigned __int16 *v175; // rax
  void *v176; // r14
  MsiString *v177; // rax
  signed int v178; // ecx
  __int64 v179; // rax
  __int64 v180; // rax
  MsiString *v181; // rax
  int v182; // ecx
  struct IMsiRecord *v183; // rax
  __int64 v184; // rcx
  __int64 *v185; // rcx
  const unsigned __int16 *v186; // r9
  struct IMsiRecord *v187; // rax
  CMsiBaselineManager *v188; // rsi
  __int64 v189; // rax
  int v190; // ebx
  int v191; // eax
  void *v192; // rax
  void *v193; // rdi
  __int64 v194; // r14
  __int64 (__fastcall *v195)(void *, _QWORD); // rbx
  unsigned int v196; // eax
  unsigned int v197; // esi
  __int64 (__fastcall *v198)(void *, _QWORD); // rbx
  unsigned int v199; // eax
  __int64 (__fastcall *v200)(void *, _QWORD); // rbx
  unsigned int v201; // eax
  int v202; // eax
  __int64 v203; // rbx
  unsigned __int64 v204; // rdi
  __int64 v205; // rax
  const struct IMsiString *MsiDirectory; // rdi
  __int64 (__fastcall *v207)(__int64, __int64, __int64); // rsi
  __int64 v208; // rbx
  __int64 v209; // rax
  CRestartManagerWrapper *v210; // rsi
  int v211; // ebx
  __int64 v212; // rax
  struct IMsiRecord *v213; // rax
  struct IMsiRecord *v214; // rax
  __int64 v215; // rcx
  struct IMsiRecord *v216; // rax
  __int64 v217; // rcx
  __int64 v218; // rbx
  __int64 v219; // rsi
  __int64 v220; // rax
  __int64 v221; // rdx
  __int64 v222; // rbx
  struct IMsiRecord *v223; // rdx
  const unsigned __int16 *v224; // rax
  int v225; // ecx
  int v226; // eax
  struct IMsiRecord *v227; // rax
  struct IMsiRecord *v228; // rax
  __int64 v229; // rcx
  __int64 v230; // rbx
  unsigned int v231; // edi
  void (__fastcall *v232)(struct IMsiEngine *, _QWORD, __int64); // rsi
  __int64 v233; // rdi
  MsiString *v234; // rax
  void (__fastcall *v235)(__int64); // rax
  unsigned __int8 v237; // [rsp+60h] [rbp-A0h]
  char v238; // [rsp+60h] [rbp-A0h]
  int v239; // [rsp+64h] [rbp-9Ch]
  signed int v240; // [rsp+64h] [rbp-9Ch]
  unsigned int v241; // [rsp+64h] [rbp-9Ch]
  unsigned int v242; // [rsp+64h] [rbp-9Ch]
  int v243; // [rsp+64h] [rbp-9Ch]
  unsigned int v244; // [rsp+64h] [rbp-9Ch]
  unsigned int v245; // [rsp+68h] [rbp-98h] BYREF
  signed int v246; // [rsp+6Ch] [rbp-94h]
  __int64 v247; // [rsp+70h] [rbp-90h] BYREF
  __int64 v248; // [rsp+78h] [rbp-88h] BYREF
  int v249; // [rsp+80h] [rbp-80h]
  unsigned int v250; // [rsp+84h] [rbp-7Ch] BYREF
  __int64 v251; // [rsp+88h] [rbp-78h] BYREF
  __int64 v252; // [rsp+90h] [rbp-70h] BYREF
  _QWORD *v253; // [rsp+98h] [rbp-68h] BYREF
  __int64 v254; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v255; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v256; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v257; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v258; // [rsp+C0h] [rbp-40h] BYREF
  struct IMsiEngine *v259; // [rsp+C8h] [rbp-38h] BYREF
  __int64 *v260; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v261; // [rsp+D8h] [rbp-28h] BYREF
  CRestartManagerWrapper *v262; // [rsp+E0h] [rbp-20h] BYREF
  void *v263; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v264; // [rsp+F0h] [rbp-10h] BYREF
  struct IMsiRecord *v265; // [rsp+F8h] [rbp-8h] BYREF
  void *v266; // [rsp+100h] [rbp+0h] BYREF
  _QWORD *v267; // [rsp+108h] [rbp+8h] BYREF
  __int64 v268; // [rsp+110h] [rbp+10h] BYREF
  void *v269; // [rsp+118h] [rbp+18h] BYREF
  __int64 v270; // [rsp+120h] [rbp+20h] BYREF
  void *v271; // [rsp+128h] [rbp+28h] BYREF
  __int64 v272; // [rsp+130h] [rbp+30h] BYREF
  int v273; // [rsp+138h] [rbp+38h] BYREF
  __int64 v274; // [rsp+140h] [rbp+40h] BYREF
  CMsiBaselineManager *v275; // [rsp+148h] [rbp+48h] BYREF
  __int64 v276; // [rsp+150h] [rbp+50h] BYREF
  __int64 v277; // [rsp+158h] [rbp+58h] BYREF
  void (__fastcall *v278)(__int64, __int64, _QWORD); // [rsp+160h] [rbp+60h]
  struct CMsiCustomActionManager *CustomActionManager; // [rsp+168h] [rbp+68h]
  __int64 v280; // [rsp+170h] [rbp+70h] BYREF
  __int64 v281; // [rsp+178h] [rbp+78h] BYREF
  __int64 v282; // [rsp+180h] [rbp+80h] BYREF
  __int64 v283; // [rsp+188h] [rbp+88h] BYREF
  __int64 v284; // [rsp+190h] [rbp+90h] BYREF
  __int64 v285; // [rsp+198h] [rbp+98h] BYREF
  __int64 v286; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v287; // [rsp+1A8h] [rbp+A8h] BYREF
  __int64 v288; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v289; // [rsp+1B8h] [rbp+B8h] BYREF
  __int64 v290; // [rsp+1C0h] [rbp+C0h] BYREF
  __int64 v291; // [rsp+1C8h] [rbp+C8h] BYREF
  void (__fastcall *v292)(_QWORD *, _QWORD, _QWORD); // [rsp+1D0h] [rbp+D0h]
  __int64 v293; // [rsp+1D8h] [rbp+D8h] BYREF
  _QWORD v294[14]; // [rsp+1E0h] [rbp+E0h]
  struct _RM_PROCESS_INFO v295; // [rsp+250h] [rbp+150h] BYREF
  __int128 v296; // [rsp+4F0h] [rbp+3F0h] BYREF
  __int64 v297; // [rsp+500h] [rbp+400h]
  __int128 v298; // [rsp+508h] [rbp+408h]
  int v299; // [rsp+518h] [rbp+418h]
  int v300; // [rsp+51Ch] [rbp+41Ch]
  __int64 v301; // [rsp+520h] [rbp+420h] BYREF
  int v302; // [rsp+528h] [rbp+428h]
  wchar_t v303; // [rsp+52Ch] [rbp+42Ch]
  __int128 v304; // [rsp+52Eh] [rbp+42Eh]
  __int64 v305; // [rsp+53Eh] [rbp+43Eh]
  int v306; // [rsp+546h] [rbp+446h]
  __int128 v307; // [rsp+54Ah] [rbp+44Ah]
  __int16 v308; // [rsp+55Ah] [rbp+45Ah]
  __int64 v309; // [rsp+55Ch] [rbp+45Ch]
  int v310; // [rsp+564h] [rbp+464h]
  unsigned __int16 v311; // [rsp+568h] [rbp+468h]
  __int128 v312; // [rsp+56Ah] [rbp+46Ah]
  __int128 v313; // [rsp+57Ah] [rbp+47Ah]
  int v314; // [rsp+58Ah] [rbp+48Ah]
  __int64 v315; // [rsp+58Eh] [rbp+48Eh]
  __int16 v316; // [rsp+596h] [rbp+496h]
  __int128 v317; // [rsp+598h] [rbp+498h]
  int v318; // [rsp+5A8h] [rbp+4A8h]
  __int64 v319; // [rsp+5ACh] [rbp+4ACh]
  __int16 v320; // [rsp+5B4h] [rbp+4B4h]
  __int128 v321; // [rsp+5B6h] [rbp+4B6h]
  __int64 v322; // [rsp+5C6h] [rbp+4C6h]
  int v323; // [rsp+5CEh] [rbp+4CEh]
  __int16 v324; // [rsp+5D2h] [rbp+4D2h]
  _BYTE v325[22]; // [rsp+5D4h] [rbp+4D4h]
  __int64 v326; // [rsp+5EAh] [rbp+4EAh]
  __int16 v327; // [rsp+5F2h] [rbp+4F2h]
  _BYTE v328[28]; // [rsp+5F4h] [rbp+4F4h] BYREF
  __int16 v329; // [rsp+610h] [rbp+510h]
  _BYTE v330[28]; // [rsp+612h] [rbp+512h] BYREF
  __int16 v331; // [rsp+62Eh] [rbp+52Eh]
  _BYTE v332[28]; // [rsp+630h] [rbp+530h] BYREF
  __int16 v333; // [rsp+64Ch] [rbp+54Ch]
  _BYTE v334[28]; // [rsp+64Eh] [rbp+54Eh] BYREF
  _BYTE v335[22]; // [rsp+66Ah] [rbp+56Ah]
  __int64 v336; // [rsp+680h] [rbp+580h]
  _BYTE v337[30]; // [rsp+688h] [rbp+588h]
  __int64 v338; // [rsp+6A6h] [rbp+5A6h]
  wchar_t v339; // [rsp+6AEh] [rbp+5AEh]
  __int128 v340; // [rsp+6B0h] [rbp+5B0h]
  int v341; // [rsp+6C0h] [rbp+5C0h]
  _OWORD v342[8]; // [rsp+6D0h] [rbp+5D0h] BYREF
  _QWORD v343[29]; // [rsp+750h] [rbp+650h] BYREF
  _BYTE v344[28]; // [rsp+838h] [rbp+738h]
  __int64 v345; // [rsp+854h] [rbp+754h]
  int v346; // [rsp+85Ch] [rbp+75Ch]

  v259 = (struct IMsiEngine *)a1;
  LODWORD(v248) = 0;
  v1 = (struct IMsiEngine *)a1;
  v2 = 2;
  if ( g_scServerContext == 2
    && !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 432LL))(a1)
    && qword_180309730 )
  {
    CMsiSQMSession::RecordInstallType(qword_180309730, v1);
  }
  v3 = (*(__int64 (__fastcall **)(struct IMsiEngine *))(*(_QWORD *)v1 + 56LL))(v1);
  v280 = v3;
  v276 = (*(__int64 (__fastcall **)(struct IMsiEngine *))(*(_QWORD *)v1 + 72LL))(v1);
  v4 = v276;
  CComPointer<IMsiSelectionManager>::CComPointer<IMsiSelectionManager>(
    (__int64)&v272,
    (void (__fastcall ***)(_QWORD, __int64, __int64))v1,
    (__int64)&IID_IMsiSelectionManager);
  if ( (*(unsigned int (__fastcall **)(struct IMsiEngine *))(*(_QWORD *)v1 + 312LL))(v1) == 2 )
    goto LABEL_324;
  v5 = *(void (__fastcall **)(struct IMsiEngine *, _QWORD, void ***))(*(_QWORD *)v1 + 160LL);
  v6 = MsiString::MsiString((MsiString *)&v258, L"MsiRestartManagerSessionKey");
  v5(v1, *(_QWORD *)v6, &g_MsiStringNull);
  (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v258 + 16LL))(v258);
  v257 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 48LL))(v3, 2);
  v247 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 48LL))(v3, 6);
  v254 = 0;
  v251 = 0;
  v8 = 0;
  v256 = v7;
  v9 = *(_QWORD *)v4;
  LOBYTE(v249) = 0;
  v10 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64))(v9 + 80);
  v11 = CComPointer<IEnumMsiRecord>::operator=(&v254);
  v12 = MsiString::MsiString((MsiString *)&v258, L"Dialog");
  v13 = v10(v4, *(_QWORD *)v12, 0, v11);
  v18 = 0;
  if ( !*(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v247, v13) )
  {
    v14 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v254 + 128LL))(v254, 0);
    if ( *(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v251, v14) )
    {
      v15 = v254;
      v16 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v254 + 96LL);
      v17 = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v4 + 120LL))(v4, L"Dialog");
      v8 = v16(v15, v17);
      if ( v8 )
        v18 = 1;
    }
  }
  (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v258 + 16LL))(v258);
  if ( v18 )
  {
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v251 + 48LL))(v251, v8);
    v19 = v251;
    v20 = *(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v251 + 96LL);
    v21 = MsiString::MsiString((MsiString *)&v258, L"MsiRMFilesInUse");
    v20(v19, v8, *(_QWORD *)v21);
    (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v258 + 16LL))(v258);
    v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v251 + 40LL))(v251);
    v23 = (unsigned __int8)v249;
    if ( v22 )
      v23 = 1;
    v249 = v23;
  }
  if ( FDiagnosticModeSet(10) )
  {
    v342[0] = *(_OWORD *)L" SELECT `Feature`, `Action`, `ActionRequested`, `Installed` FROM `Feature`";
    v342[2] = *(_OWORD *)L"`, `Action`, `ActionRequested`, `Installed` FROM `Feature`";
    v342[4] = *(_OWORD *)L"tionRequested`, `Installed` FROM `Feature`";
    v342[6] = *(_OWORD *)L"`Installed` FROM `Feature`";
    *(_OWORD *)v343 = *(_OWORD *)L" `Feature`";
    *(_QWORD *)((char *)&v343[1] + 6) = *(_QWORD *)L"re`";
    v342[1] = *(_OWORD *)L"`Feature`, `Action`, `ActionRequested`, `Installed` FROM `Feature`";
    v345 = 0;
    memset((char *)&v343[2] + 6, 0, 50);
    v346 = 0;
    v297 = 0;
    v299 = *(_DWORD *)L"t";
    v342[3] = *(_OWORD *)L"on`, `ActionRequested`, `Installed` FROM `Feature`";
    v300 = 0;
    *(_OWORD *)&v343[9] = *(_OWORD *)L" SELECT `Component`, `Action`, `ActionRequest`, `Installed`, `TrueInstallSt` FROM `Component`";
    v302 = *(_DWORD *)L"nt";
    v342[5] = *(_OWORD *)L"ested`, `Installed` FROM `Feature`";
    v303 = aAbsent[6];
    *(_OWORD *)&v343[13] = *(_OWORD *)L"nt`, `Action`, `ActionRequest`, `Installed`, `TrueInstallSt` FROM `Component`";
    v306 = *(_DWORD *)L"l";
    v342[7] = *(_OWORD *)L"ed` FROM `Feature`";
    v308 = 0;
    *(_OWORD *)&v343[17] = *(_OWORD *)L"ActionRequest`, `Installed`, `TrueInstallSt` FROM `Component`";
    v310 = *(_DWORD *)L"ce";
    *(_OWORD *)&v343[11] = *(_OWORD *)L"`Component`, `Action`, `ActionRequest`, `Installed`, `TrueInstallSt` FROM `Component`";
    *(_OWORD *)&v343[21] = *(_OWORD *)L"`Installed`, `TrueInstallSt` FROM `Component`";
    *(_OWORD *)&v343[15] = *(_OWORD *)L"tion`, `ActionRequest`, `Installed`, `TrueInstallSt` FROM `Component`";
    *(_OWORD *)&v343[25] = *(_OWORD *)L"ueInstallSt` FROM `Component`";
    *(_OWORD *)&v343[19] = *(_OWORD *)L"quest`, `Installed`, `TrueInstallSt` FROM `Component`";
    *(_OWORD *)v344 = *(_OWORD *)L"M `Component`";
    *(_OWORD *)&v343[23] = *(_OWORD *)L"ed`, `TrueInstallSt` FROM `Component`";
    v296 = *(_OWORD *)L"Feature";
    *(_OWORD *)&v343[27] = *(_OWORD *)L"lSt` FROM `Component`";
    v298 = *(_OWORD *)L"Component";
    *(_OWORD *)&v344[12] = *(_OWORD *)L"ponent`";
    v301 = *(_QWORD *)L"Absent";
    v305 = *(_QWORD *)L"Local";
    v304 = 0;
    v307 = 0;
    v309 = *(_QWORD *)L"Source";
    v311 = aSource_1[6];
    v314 = *(_DWORD *)L"l";
    v315 = 0;
    v316 = 0;
    v318 = *(_DWORD *)L"e";
    v319 = 0;
    v320 = 0;
    v322 = 0;
    v323 = 0;
    v324 = 0;
    v326 = 0;
    v327 = 0;
    v329 = 0;
    v331 = 0;
    v333 = 0;
    v336 = 0;
    v339 = aNull_1[4];
    v341 = 0;
    v294[0] = L"Not Used";
    v294[1] = L"Bad Config";
    v294[2] = L"Incomplete";
    v294[3] = L"Source Absent";
    v312 = 0;
    v294[4] = L"More Data";
    v294[5] = L"Invalid Arg";
    v294[6] = L"Unknown";
    v317 = *(_OWORD *)L"Advertise";
    v294[7] = L"Broken";
    v294[8] = L"Advertised/Removed";
    v313 = *(_OWORD *)L"Reinstall";
    v294[9] = L"Absent";
    v321 = *(_OWORD *)L"Current";
    v294[10] = L"Local";
    v294[11] = L"Source";
    *(_OWORD *)v325 = *(_OWORD *)L"FileAbsent";
    *(_QWORD *)&v325[14] = *(_QWORD *)L"ent";
    memset(v328, 0, sizeof(v328));
    memset(v330, 0, sizeof(v330));
    memset(v332, 0, sizeof(v332));
    memset(v334, 0, sizeof(v334));
    *(_OWORD *)v335 = *(_OWORD *)L"HKCRAbsent";
    *(_QWORD *)&v335[14] = *(_QWORD *)L"ent";
    *(_OWORD *)v337 = *(_OWORD *)L"HKCRFileAbsent";
    v338 = *(_QWORD *)L"Null";
    *(_OWORD *)&v337[14] = *(_OWORD *)L"eAbsent";
    v340 = 0;
    v24 = 0;
    v294[12] = L"Default";
    v260 = 0;
    v294[13] = L"Null";
    v264 = 0;
    v246 = 0;
    while ( 1 )
    {
      v25 = (unsigned int)v24;
      v26 = *(__int64 (__fastcall **)(struct IMsiEngine *, _QWORD, char *, __int64, __int64))(*(_QWORD *)v1 + 136LL);
      v27 = CComPointer<IEnumMsiRecord>::operator=(&v264);
      v28 = v26(v1, 0, (char *)v342 + 200 * (unsigned int)v24, 1, v27);
      CComPointer<IMsiDatabase>::operator=(&v247, v28);
      if ( v247 )
        goto LABEL_40;
      v29 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v264 + 24LL))(v264, 0);
      CComPointer<IMsiDatabase>::operator=(&v247, v29);
      if ( v247 )
        goto LABEL_39;
      while ( 1 )
      {
        v30 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v264 + 56LL))(v264);
        if ( !*(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v260, v30) )
          break;
        v31 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v260 + 72))(v260, 1);
        v32 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v260 + 56))(v260, 2);
        if ( v32 == 0x80000000 )
          v32 = 13;
        v33 = *v260;
        LODWORD(v252) = v32;
        v34 = (*(__int64 (__fastcall **)(__int64 *, __int64))(v33 + 56))(v260, 3);
        if ( v34 == 0x80000000 )
          v34 = 13;
        v250 = v34;
        v35 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v260 + 56))(v260, 4);
        if ( v35 == 0x80000000 )
          v35 = 13;
        v239 = v35;
        if ( IsLoggingModeSet(v36) && (_DWORD)v25 == 1 )
        {
          v37 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v260 + 56))(v260, 5);
          if ( v37 == 0x80000000 )
          {
            v245 = 13;
          }
          else
          {
            v38 = v37 + 7 < 0;
            v39 = v37 + 7;
            v245 = v39;
            if ( v38 || v39 >= 0xE )
              goto LABEL_36;
          }
          v40 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v31 + 80LL))(v31);
          v41 = StringCbPrintfW(
                  (unsigned __int16 *)&v295,
                  0x200u,
                  L"%s: %s; Installed: %s;   Request: %s;   Action: %s;   Client State: %s",
                  (char *)&v296 + 24 * v25,
                  v40,
                  (char *)&v301 + 30 * v239,
                  (char *)&v301 + 30 * (int)v250,
                  (char *)&v301 + 30 * (int)v252,
                  v294[v245]);
        }
        else
        {
          v42 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v31 + 80LL))(v31);
          v41 = StringCbPrintfW(
                  (unsigned __int16 *)&v295,
                  0x200u,
                  L"%s: %s; Installed: %s;   Request: %s;   Action: %s",
                  (char *)&v296 + 24 * v25,
                  v42,
                  (char *)&v301 + 30 * v239,
                  (char *)&v301 + 30 * (int)v250,
                  (char *)&v301 + 30 * v32);
        }
        if ( v41 >= 0 )
        {
          if ( g_dmDiagnosticMode )
            DebugString(
              10,
              0,
              0,
              (const unsigned __int16 *)&v295,
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
      v1 = v259;
      v24 = v246;
LABEL_39:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v264 + 80LL))(v264);
LABEL_40:
      v246 = ++v24;
      if ( v24 >= 2 )
      {
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v264);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v260);
        v4 = v276;
        v3 = v280;
        break;
      }
    }
  }
  if ( byte_180309723 )
    goto LABEL_312;
  v43 = *(_QWORD *)v1;
  v44 = 1;
  v250 = 0;
  (*(void (__fastcall **)(struct IMsiEngine *, __int64, __int64))(v43 + 104))(v1, 4096, 1);
  if ( g_scServerContext == 2 )
  {
    CustomActionManager = GetCustomActionManager(v1);
    v45 = (*(__int64 (__fastcall **)(struct IMsiEngine *))(*(_QWORD *)v1 + 784LL))(v1);
    Instance = (CRestartManagerWrapper *)CRestartManagerWrapper::GetInstance(v45 != 0);
    v262 = Instance;
  }
  else
  {
    Instance = 0;
    CustomActionManager = 0;
    v262 = 0;
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
      v273 = 0;
      v48 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v272 + 280LL))(v272, &v273);
      if ( *(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v247, v48) )
      {
        v49 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v247 + 56LL))(v247, 1);
        if ( v49 == 3 )
          goto LABEL_225;
        if ( v49 != 2731 )
        {
          v2 = (*(__int64 (__fastcall **)(struct IMsiEngine *, __int64))(*(_QWORD *)v1 + 208LL))(v1, v247);
          goto LABEL_225;
        }
      }
      if ( v273 )
        goto LABEL_225;
    }
    v50 = 0;
    v51 = 0;
    v253 = 0;
    v255 = 0;
    v248 = 0;
    if ( !Instance || !CRestartManagerWrapper::IsEnabled(Instance) )
      goto LABEL_177;
    if ( g_scServerContext == 2 )
    {
      v53 = 0;
      if ( !CRestartManagerWrapper::IsEnabled(v52) )
        goto LABEL_87;
      v260 = 0;
      v264 = 0;
      v54 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64))(*(_QWORD *)v4 + 80LL);
      v55 = CComPointer<IEnumMsiRecord>::operator=(&v260);
      v56 = MsiString::MsiString((MsiString *)&v281, L"FilesInUse");
      v57 = v54(v4, *(_QWORD *)v56, 0, v55);
      v58 = *(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v264, v57);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v281 + 16LL))(v281);
      v53 = 0;
      if ( v58 )
        goto LABEL_85;
      v59 = (__int64)v260;
      v60 = *(__int64 (__fastcall **)(__int64, _QWORD))(*v260 + 96);
      v61 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v4 + 120LL))(v4, L"FilePath");
      v62 = v60(v59, v61);
      v63 = (__int64)v260;
      LODWORD(v252) = v62;
      v64 = *(__int64 (__fastcall **)(__int64, _QWORD))(*v260 + 96);
      v65 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v4 + 120LL))(v4, L"FileName");
      LODWORD(v261) = v64(v63, v65);
      v268 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v260 + 128))(v260, 0);
      v66 = v268;
      if ( v268 )
      {
        v67 = (*(__int64 (__fastcall **)(__int64 *))(*v260 + 64))(v260);
        v68 = (unsigned __int16 *)v67;
        v246 = v67;
        v70 = v67;
        v69 = 8 * v67;
        v258 = v68;
        if ( !is_mul_ok(v70, 8u) )
          v69 = -1;
        v71 = (void *)operator new(v69);
        v266 = v71;
        if ( v71 )
        {
          memset_0(v71, 0, 8LL * (_QWORD)v258);
          for ( i = 0; ; i = v240 + 1 )
          {
            v240 = i;
            v73 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v66 + 40LL))(v66);
            v74 = v246;
            if ( !v73 || i >= v246 )
              break;
            v75 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v66 + 64LL))(v66, (unsigned int)v252);
            v76 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v268 + 64LL))(v268, (unsigned int)v261);
            v77 = (const struct IMsiString *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v75 + 168LL))(
                                               v75,
                                               v76);
            v78 = (*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v77 + 56LL))(v77);
            v80 = v78 + 1LL;
            v79 = 2 * (v78 + 1);
            if ( !is_mul_ok(v80, 2u) )
              v79 = -1;
            v81 = operator new(v79);
            *((_QWORD *)v266 + v240) = v81;
            if ( !v81 )
            {
              v83 = PostError(2346, L"FilesInUse");
              goto LABEL_73;
            }
            v258 = (unsigned __int16 *)(*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v77 + 80LL))(v77);
            v82 = (*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v77 + 56LL))(v77);
            if ( (int)StringCchCopyW(*((unsigned __int16 **)v266 + v240), v82 + 1, v258) < 0 )
            {
              v83 = PostError(1322, v77);
LABEL_73:
              CComPointer<IMsiDatabase>::operator=(&v264, v83);
              (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v77 + 16LL))(v77);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
              v74 = v246;
              break;
            }
            (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v77 + 16LL))(v77);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
            v66 = v268;
          }
          v84 = v266;
          v85 = 0;
          if ( !v264 )
          {
            v86 = (**(__int64 (__fastcall ***)(CRestartManagerWrapper *, void *, _QWORD))v262)(
                    v262,
                    v266,
                    (unsigned int)v74);
            if ( v86 )
            {
              if ( g_dmDiagnosticMode )
                DebugString(
                  10,
                  0,
                  0,
                  L"RESTART MANAGER: Failed to add file path resources; Windows Installer will use the built-in FilesInUse"
                   " functionality. Error: %d",
                  (const unsigned __int16 *)v86,
                  L"(NULL)",
                  L"(NULL)",
                  L"(NULL)",
                  L"(NULL)",
                  L"(NULL)",
                  0,
                  0);
            }
          }
          if ( v74 > 0 )
          {
            do
            {
              v87 = v85;
              v88 = (void *)v84[v85];
              if ( v88 )
              {
                operator delete(v88);
                v87 = v85;
              }
              ++v85;
              v84[v87] = 0;
            }
            while ( (int)v85 < v74 );
            v4 = v276;
          }
          operator delete(v84);
          v53 = 0;
          if ( !v264 )
          {
            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v268);
            v1 = v259;
LABEL_85:
            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v264);
            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v260);
            Instance = v262;
            goto LABEL_87;
          }
          v2 = (*(__int64 (__fastcall **)(struct IMsiEngine *))(*(_QWORD *)v259 + 208LL))(v259);
LABEL_230:
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v268);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v264);
          v185 = (__int64 *)&v260;
          goto LABEL_231;
        }
        v182 = 2346;
      }
      else
      {
        v182 = 2283;
      }
      v183 = PostError(v182, L"FilesInUse");
      v184 = *(_QWORD *)v1;
      v265 = v183;
      v2 = (*(__int64 (__fastcall **)(struct IMsiEngine *, struct IMsiRecord *))(v184 + 208))(v1, v183);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v265);
      goto LABEL_230;
    }
    v53 = 0;
LABEL_87:
    LODWORD(v252) = -1;
    v245 = 0;
    ApplicationsList = CRestartManagerWrapper::GetApplicationsList(Instance, (enum TRI *)&v252, &v245);
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
      goto LABEL_177;
    }
    if ( !v245 )
      goto LABEL_177;
    LODWORD(v268) = ServiceActionOrderCausesReboot(v1);
    v237 = 0;
    v90 = *(__int64 (__fastcall **)(struct IMsiEngine *, _QWORD))(*(_QWORD *)v1 + 192LL);
    v91 = MsiString::MsiString((MsiString *)&v282, L"MSICLIENTUSESEXTERNALUI");
    LODWORD(v90) = v90(v1, *(_QWORD *)v91);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v282 + 16LL))(v282);
    if ( (_DWORD)v90 == 1 )
      goto LABEL_101;
    if ( HIBYTE(word_180309778) )
    {
      if ( g_dmDiagnosticMode )
      {
        v92 = L"RESTART MANAGER: Will attempt to shut down and restart applications because the UI does not display any modal dialogs.";
LABEL_99:
        DebugString(10, 0, 0, v92, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
      }
    }
    else
    {
      v93 = *(__int64 (__fastcall **)(struct IMsiEngine *, _QWORD))(*(_QWORD *)v1 + 192LL);
      v94 = MsiString::MsiString((MsiString *)&v283, L"CLIENTUILEVEL");
      v95 = v93(v1, *(_QWORD *)v94);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v283 + 16LL))(v283);
      if ( v95 != 3 && v95 != 0x2000 )
        goto LABEL_101;
      if ( g_dmDiagnosticMode )
      {
        v92 = L"RESTART MANAGER: Will attempt to shut down and restart applications in no UI modes.";
        goto LABEL_99;
      }
    }
    v237 = 1;
LABEL_101:
    v96 = *(_QWORD *)v1;
    v241 = 0;
    v245 = 0;
    v97 = *(__int64 (__fastcall **)(struct IMsiEngine *, _QWORD))(v96 + 192);
    v98 = MsiString::MsiString((MsiString *)&v284, L"CLIENTPROCESSID");
    LODWORD(v261) = v97(v1, *(_QWORD *)v98);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v284 + 16LL))(v284);
    CurrentProcessId = GetCurrentProcessId();
    v295.Process.dwProcessId = 0;
    LODWORD(v252) = CurrentProcessId;
    memset_0(&v295.Process.ProcessStartTime, 0, 0x298u);
    v100 = v262;
    for ( j = 0; ; j = v246 + 1 )
    {
      v246 = j;
      if ( CRestartManagerWrapper::EnumApplications(v100, j, &v295) )
        goto LABEL_133;
      CRestartManagerWrapper::ReportDetectedApplication(v102, &v295);
      dwProcessId = v295.Process.dwProcessId;
      if ( v295.Process.dwProcessId == (_DWORD)v252 )
      {
        if ( !g_dmDiagnosticMode )
          goto LABEL_242;
        v186 = L"RESTART MANAGER: Did detect that Windows Installer service holds file[s] in use, so a reboot will be necessary.";
        goto LABEL_241;
      }
      if ( v295.Process.dwProcessId == (_DWORD)v261 )
      {
        if ( !g_dmDiagnosticMode )
          goto LABEL_242;
        v186 = L"RESTART MANAGER: Did detect that the client process of this installation holds file[s] in use, so a reboo"
                "t will be necessary.";
        goto LABEL_241;
      }
      if ( CustomActionManager && v295.Process.dwProcessId )
      {
        for ( k = 0; ; ++k )
        {
          if ( k >= 10 )
            goto LABEL_111;
          if ( *((_DWORD *)CustomActionManager + 4 * k + 3) == v295.Process.dwProcessId )
            break;
        }
        if ( g_dmDiagnosticMode )
          DebugString(
            10,
            0,
            0,
            L"RESTART MANAGER: Did detect that the custom action server with process ID %d holds file[s] in use, so a rebo"
             "ot will be necessary.",
            (const unsigned __int16 *)v295.Process.dwProcessId,
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
LABEL_242:
        if ( (_BYTE)v249 )
        {
          v187 = PostError(1610);
          CComPointer<IMsiDatabase>::operator=(&v247, v187);
          v2 = 2;
          if ( (*(unsigned int (__fastcall **)(struct IMsiEngine *, __int64, __int64))(*(_QWORD *)v1 + 24LL))(
                 v1,
                 50331969,
                 v247) == 2 )
            goto LABEL_232;
          if ( g_dmDiagnosticMode )
LABEL_283:
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
LABEL_247:
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v248);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v255);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v253);
        v2 = 2;
LABEL_248:
        (*(void (__fastcall **)(struct IMsiEngine *, __int64, _QWORD))(*(_QWORD *)v1 + 104LL))(v1, 4096, 0);
        v188 = (CMsiBaselineManager *)(*(__int64 (__fastcall **)(struct IMsiEngine *))(*(_QWORD *)v1 + 672LL))(v1);
        v275 = v188;
        v189 = *(_QWORD *)v1;
        v250 = 0;
        if ( ((*(__int64 (__fastcall **)(struct IMsiEngine *))(v189 + 96))(v1) & 1) == 0
          && v188
          && CMsiBaselineManager::CheckBaselineAgainstPolicy(v188, &v250) )
        {
          v265 = (struct IMsiRecord *)(*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v272 + 288LL))(
                                        v272,
                                        8,
                                        v250);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v265);
        }
        v190 = 1;
LABEL_253:
        if ( v190 )
        {
          if ( (*(unsigned int (__fastcall **)(struct IMsiEngine *))(*(_QWORD *)v1 + 312LL))(v1) == 2 )
            goto LABEL_225;
          LODWORD(v268) = 0;
          LODWORD(v261) = 0;
          v191 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64 *))(*(_QWORD *)v272 + 184LL))(
                   v272,
                   &v268,
                   &v261);
          if ( (_DWORD)v261 )
            goto LABEL_225;
          if ( v191 == 1 )
          {
            v192 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v272 + 48LL))(v272);
            v266 = v192;
            v193 = v192;
            if ( v192 )
            {
              v267 = (_QWORD *)(*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)v192 + 128LL))(v192, 0);
              v194 = (__int64)v267;
              if ( !v267 )
              {
                v228 = PostError(2283, L"FilesInUse");
                v229 = *(_QWORD *)v1;
                v265 = v228;
                v2 = (*(__int64 (__fastcall **)(struct IMsiEngine *, struct IMsiRecord *))(v229 + 208))(v1, v228);
                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v265);
                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v267);
                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v266);
                goto LABEL_225;
              }
              v195 = *(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)v193 + 96LL);
              v196 = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v4 + 120LL))(v4, L"VolumeObject");
              v197 = v195(v193, v196);
              LODWORD(v252) = v197;
              v198 = *(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)v193 + 96LL);
              v199 = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v4 + 120LL))(v4, L"VolumeCost");
              LODWORD(v255) = v198(v193, v199);
              v200 = *(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)v193 + 96LL);
              v201 = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v4 + 120LL))(
                       v4,
                       L"NoRbVolumeCost");
              v202 = v200(v193, v201);
              v190 = 0;
              LODWORD(v253) = v202;
              v249 = 0;
              while ( 1 )
              {
LABEL_260:
                if ( v190 || !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v194 + 40LL))(v194) )
                {
                  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v267);
                  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v266);
                  v2 = 2;
                  goto LABEL_253;
                }
                v203 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v194 + 80LL))(v194, v197);
                v259 = (struct IMsiEngine *)v203;
                v204 = (*(int (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v194 + 56LL))(v194, (unsigned int)v255) / 2;
                v205 = *(_QWORD *)v194;
                v245 = v204;
                LODWORD(v248) = (*(__int64 (__fastcall **)(__int64, _QWORD))(v205 + 56))(v194, (unsigned int)v253);
                v258 = (unsigned __int16 *)((unsigned __int64)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v203 + 72LL))(v203) >> 1);
                if ( v204 <= (unsigned __int64)v258 )
                  goto LABEL_306;
                MsiDirectory = GetMsiDirectory();
                v262 = 0;
                v207 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v3 + 128LL);
                v208 = CComPointer<IEnumMsiRecord>::operator=(&v262);
                v209 = (*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)MsiDirectory + 80LL))(MsiDirectory);
                v263 = (void *)v207(v3, v209, v208);
                if ( v263 )
                  break;
                v210 = v262;
                v211 = (*(__int64 (__fastcall **)(struct IMsiEngine *))(*(_QWORD *)v259 + 96LL))(v259);
                if ( (*(unsigned int (__fastcall **)(CRestartManagerWrapper *))(*(_QWORD *)v210 + 96LL))(v210) != v211
                  || !v275
                  || !CMsiBaselineManager::DisableBaselineForCostReasons(v275, &v250) )
                {
                  break;
                }
                v212 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v272 + 288LL))(v272, 8, v250);
                CComPointer<IMsiDatabase>::operator=(&v263, v212);
                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v263);
                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v262);
                (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)MsiDirectory + 16LL))(MsiDirectory);
                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v259);
                v190 = v249;
                v197 = v252;
              }
              v218 = (__int64)v259;
              v219 = (*(__int64 (__fastcall **)(struct IMsiEngine *, const wchar_t *))(*(_QWORD *)v1 + 184LL))(
                       v1,
                       L"PROMPTROLLBACKCOST");
              v246 = (*(__int64 (__fastcall **)(__int64, __int64, const wchar_t *))(*(_QWORD *)v219 + 200LL))(
                       v219,
                       1,
                       L"D");
              v243 = (*(__int64 (__fastcall **)(__int64, __int64, const wchar_t *))(*(_QWORD *)v219 + 200LL))(
                       v219,
                       1,
                       L"F");
              v220 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v218 + 168LL))(v218);
              v222 = v220;
              if ( (_DWORD)v268 == 1 || v243 )
              {
                v244 = 117440517;
                if ( v246 )
                {
                  v221 = (unsigned int)((int)v248 >> 31);
                  LODWORD(v221) = (int)v248 % 2;
                  v245 = (int)v248 / 2;
                }
                v224 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v220 + 80LL))(
                                                   v220,
                                                   v221);
                v225 = 1601;
              }
              else
              {
                if ( v246 )
                {
                  v244 = 0;
                  v249 = 0;
                  (*(void (__fastcall **)(struct IMsiEngine *, __int64))(*(_QWORD *)v1 + 104LL))(v1, 8);
                  v223 = 0;
                  goto LABEL_297;
                }
                v244 = 117440514;
                v224 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v220 + 80LL))(v220);
                v225 = 1605;
              }
              v223 = PostOutOfDiskSpaceError(v225, v224, v245, (unsigned __int64)v258);
LABEL_297:
              CComPointer<IMsiDatabase>::operator=(&v247, v223);
              if ( v247 )
              {
                v226 = (*(__int64 (__fastcall **)(struct IMsiEngine *, _QWORD))(*(_QWORD *)v1 + 24LL))(v1, v244);
                switch ( v226 )
                {
                  case 2:
                  case 3:
                    v227 = PostError(1602);
                    CComPointer<IMsiDatabase>::operator=(&v247, v227);
                    if ( (*(unsigned int (__fastcall **)(struct IMsiEngine *, __int64, __int64))(*(_QWORD *)v1 + 24LL))(
                           v1,
                           50331908,
                           v247) != 7 )
                    {
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v222 + 16LL))(v222);
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v219 + 16LL))(v219);
                      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v263);
                      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v262);
                      (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)MsiDirectory + 16LL))(MsiDirectory);
                      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v259);
                      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v267);
                      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v266);
                      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v251);
                      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v254);
                      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v256);
                      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v247);
                      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v257);
                      v2 = 2;
                      goto LABEL_324;
                    }
                    break;
                  case 4:
                    break;
                  case 5:
                    v249 = 0;
                    (*(void (__fastcall **)(struct IMsiEngine *, __int64, _QWORD))(*(_QWORD *)v1 + 104LL))(v1, 8, 0);
                    goto LABEL_305;
                  default:
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v222 + 16LL))(v222);
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v219 + 16LL))(v219);
                    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v263);
                    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v262);
                    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)MsiDirectory + 16LL))(MsiDirectory);
                    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v259);
                    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v267);
                    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v266);
                    goto LABEL_281;
                }
                v249 = 1;
              }
LABEL_305:
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v222 + 16LL))(v222);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v219 + 16LL))(v219);
              CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v263);
              CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v262);
              (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)MsiDirectory + 16LL))(MsiDirectory);
              v197 = v252;
LABEL_306:
              CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v259);
              v190 = v249;
              goto LABEL_260;
            }
            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v266);
          }
        }
LABEL_312:
        v230 = (*(__int64 (__fastcall **)(struct IMsiEngine *, const unsigned __int16 *))(*(_QWORD *)v1 + 184LL))(
                 v1,
                 L"REMOVE");
        if ( !(*(unsigned int (__fastcall **)(__int64, _QWORD, const unsigned __int16 *))(*(_QWORD *)v230 + 200LL))(
                v230,
                0,
                L"ALL") )
        {
          if ( (*(unsigned int (__fastcall **)(__int64, __int64, const unsigned __int16 *))(*(_QWORD *)v230 + 200LL))(
                 v230,
                 1,
                 L"ALL")
            || !(unsigned int)FFeaturesInstalled(v1, 0) )
          {
            v232 = *(void (__fastcall **)(struct IMsiEngine *, _QWORD, __int64))(*(_QWORD *)v1 + 160LL);
            v233 = *(_QWORD *)MsiString::MsiString((MsiString *)&v275, L"ALL");
            v234 = MsiString::MsiString((MsiString *)&v265, L"REMOVE");
            v232(v1, *(_QWORD *)v234, v233);
            (*(void (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)v265 + 16LL))(v265);
            (*(void (__fastcall **)(CMsiBaselineManager *))(*(_QWORD *)v275 + 16LL))(v275);
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
            v231 = ResolveSource(v1);
            if ( v231 != 1 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v230 + 16LL))(v230);
              CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v251);
              CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v254);
              CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v256);
              CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v247);
              CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v257);
              v2 = v231;
              goto LABEL_324;
            }
          }
        }
        v119 = (*(unsigned int (__fastcall **)(struct IMsiEngine *))(*(_QWORD *)v1 + 312LL))(v1) == 2;
        v235 = *(void (__fastcall **)(__int64))(*(_QWORD *)v230 + 16LL);
        if ( !v119 )
        {
          v235(v230);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v251);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v254);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v256);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v247);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v257);
          v2 = 1;
          goto LABEL_324;
        }
        v235(v230);
        goto LABEL_225;
      }
LABEL_111:
      if ( (_DWORD)v268 )
        goto LABEL_116;
      if ( (unsigned int)ServiceUpdateCausesReboot(v1, v295.strServiceShortName) )
        break;
      if ( g_dmDiagnosticMode )
        DebugString(
          10,
          0,
          0,
          L"RESTART MANAGER: Detected that the service %s will be stopped due to a service control action authored in the "
           "package before the files are updated. So, we will not attempt to stop this service using Restart Manager",
          v295.strServiceShortName,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
LABEL_131:
      ;
    }
    dwProcessId = v295.Process.dwProcessId;
LABEL_116:
    if ( v295.ApplicationType == RmCritical )
    {
      if ( !g_dmDiagnosticMode )
        goto LABEL_242;
      v186 = L"RESTART MANAGER: Did detect that a critical application holds file[s] in use, so a reboot will be necessary.";
LABEL_241:
      DebugString(10, 0, 0, v186, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
      goto LABEL_242;
    }
    v105 = v241;
    if ( (v241 & 7) == 0 )
    {
      v267 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v3 + 48LL))(v3, v241 + 8);
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v267 + 200LL))(v267, v50);
      CComPointer<IXMLDOMElement>::operator=(&v253, &v267);
      v50 = v253;
      if ( !v241 )
      {
        v106 = *(void (__fastcall **)(_QWORD *, _QWORD, __int64))(*v253 + 120LL);
        v107 = (*(__int64 (__fastcall **)(struct IMsiEngine *, __int64))(*(_QWORD *)v1 + 416LL))(v1, 1607);
        v106(v50, 0, v107);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v107 + 16LL))(v107);
        v53 = v245;
        v105 = 0;
      }
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v267);
      dwProcessId = v295.Process.dwProcessId;
    }
    v263 = &MsiString::s_NullString;
    v108 = v105 + 1;
    v245 = v105 + 1;
    v109 = *v50;
    if ( v295.strAppName[0] )
    {
      v113 = v50;
      (*(void (__fastcall **)(_QWORD *, __int64, WCHAR *))(v109 + 128))(v50, v108, v295.strAppName);
      MsiString::operator=(&v263, v295.strAppName);
      MsiString::operator+=(&v263, L" (Process Id: ");
      v114 = MsiString::MsiString((MsiString *)&v293, v295.Process.dwProcessId);
      MsiString::operator+=(&v263, v114);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v293 + 16LL))(v293);
      MsiString::operator+=(&v263, L")");
    }
    else
    {
      v110 = *(void (__fastcall **)(_QWORD *, _QWORD, _QWORD))(v109 + 120);
      v111 = MsiString::MsiString((MsiString *)&v285, dwProcessId);
      v110(v50, v245, *(_QWORD *)v111);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v285 + 16LL))(v285);
      MsiString::operator=(&v263, L"Process Id: ");
      v112 = MsiString::MsiString((MsiString *)&v286, v295.Process.dwProcessId);
      MsiString::operator+=(&v263, v112);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v286 + 16LL))(v286);
      v113 = v50;
    }
    v241 = v245 + 1;
    (*(void (__fastcall **)(_QWORD *, _QWORD, void *))(*v113 + 120LL))(v113, v245 + 1, v263);
    if ( v53 && v53 + 3 <= (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v51 + 24LL))(v51) )
      goto LABEL_130;
    if ( v53 + 9 <= 0xFFFF )
    {
      v267 = (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 48LL))(v3);
      (*(void (__fastcall **)(_QWORD *, __int64))(*v267 + 200LL))(v267, v51);
      CComPointer<IXMLDOMElement>::operator=(&v255, &v267);
      v51 = v255;
      if ( !v53 )
      {
        v115 = *(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v255 + 120LL);
        v116 = (*(__int64 (__fastcall **)(struct IMsiEngine *, __int64))(*(_QWORD *)v1 + 416LL))(v1, 1607);
        v115(v51, 0, v116);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v116 + 16LL))(v116);
        (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v51 + 104LL))(v51, 1, v237);
        v53 = 1;
      }
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v267);
LABEL_130:
      v117 = v53 + 1;
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v51 + 104LL))(v51, v117++, v295.Process.dwProcessId);
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v51 + 104LL))(
        v51,
        v117,
        v295.Process.ProcessStartTime.dwHighDateTime);
      v118 = *(_QWORD *)v51;
      v53 = v117 + 1;
      v245 = v53;
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(v118 + 104))(
        v51,
        v53,
        v295.Process.ProcessStartTime.dwLowDateTime);
      memset_0(&v295, 0, sizeof(v295));
      (*(void (__fastcall **)(void *))(*(_QWORD *)v263 + 16LL))(v263);
      v100 = v262;
      goto LABEL_131;
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)v263 + 16LL))(v263);
    v100 = v262;
LABEL_133:
    if ( !v51 )
      goto LABEL_247;
    v119 = (*((_BYTE *)v100 + 784) & 8) == 0;
    v120 = v249;
    if ( !v119 && !(_BYTE)v249 )
      goto LABEL_146;
    v121 = (*(__int64 (__fastcall **)(struct IMsiEngine *, __int64, __int64))(*(_QWORD *)v1 + 24LL))(v1, 419430400, v51);
    if ( v121 != 7 )
    {
      if ( v121 != 1 )
      {
        v2 = 2;
        if ( v121 == 2 )
          goto LABEL_232;
        if ( v121 == 5 )
        {
          if ( g_dmDiagnosticMode )
            goto LABEL_283;
          goto LABEL_247;
        }
        if ( (v121 & 0xFFFFFFFB) != 0 )
        {
          if ( v121 != 0x3FFF && g_dmDiagnosticMode )
            DebugString(
              10,
              0,
              0,
              L"RESTART MANAGER: %s is an unexpected return value for imtRMFilesInUse message!",
              (const unsigned __int16 *)v121,
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              0,
              0);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v248);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v255);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v253);
LABEL_281:
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v251);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v254);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v256);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v247);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v257);
          v2 = 3;
          goto LABEL_324;
        }
        goto LABEL_146;
      }
LABEL_153:
      v128 = *(_QWORD *)v1;
      v252 = 0;
      v269 = &MsiString::s_NullString;
      v271 = &MsiString::s_NullString;
      v129 = *(void (__fastcall **)(struct IMsiEngine *, const WCHAR *, void **, void **))(v128 + 792);
      (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
      v271 = &MsiString::s_NullString;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v269 + 16LL))(v269);
      v269 = &MsiString::s_NullString;
      v129(v1, L"ShutdownApplications", &v269, &v271);
      v130 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 48LL))(v3, 3);
      CComPointer<IMsiDatabase>::operator=(&v252, v130);
      v131 = v252;
      (*(void (__fastcall **)(__int64, __int64, const WCHAR *))(*(_QWORD *)v252 + 128LL))(
        v252,
        1,
        L"ShutdownApplications");
      v2 = 2;
      (*(void (__fastcall **)(__int64, __int64, void *))(*(_QWORD *)v131 + 120LL))(v131, 2, v269);
      (*(void (__fastcall **)(__int64, __int64, void *))(*(_QWORD *)v131 + 120LL))(v131, 3, v271);
      if ( (*(unsigned int (__fastcall **)(struct IMsiEngine *, __int64, __int64))(*(_QWORD *)v1 + 24LL))(
             v1,
             0x8000000,
             v131) != 2 )
      {
        v132 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 48LL))(v3, 3);
        v261 = v132;
        (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v132 + 104LL))(v132, 1, 3);
        v133 = *(__int64 (__fastcall **)(struct IMsiEngine *, _QWORD))(*(_QWORD *)v1 + 192LL);
        v134 = MsiString::MsiString((MsiString *)&v287, L"MSIRMSHUTDOWN");
        LODWORD(v133) = v133(v1, *(_QWORD *)v134);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v287 + 16LL))(v287);
        v135 = (_DWORD)v133 - 1;
        if ( v135 )
        {
          if ( v135 == 1 )
            v136 = 16;
          else
            v136 = 0;
        }
        else
        {
          v136 = 1;
        }
        (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v132 + 104LL))(v132, 2, v136);
        v137 = *(__int64 (__fastcall **)(struct IMsiEngine *, _QWORD))(*(_QWORD *)v1 + 192LL);
        v138 = MsiString::MsiString((MsiString *)&v288, L"MSIDISABLERMRESTART");
        LODWORD(v137) = v137(v1, *(_QWORD *)v138);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v288 + 16LL))(v288);
        (*(void (__fastcall **)(__int64, __int64, bool))(*(_QWORD *)v132 + 104LL))(v132, 3, (_DWORD)v137 == 1);
        v139 = *(__int64 (__fastcall **)(CRestartManagerWrapper *, _QWORD, __int64))(*(_QWORD *)v262 + 16LL);
        LOBYTE(v137) = (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v132 + 56LL))(v132, 3) == 1;
        v140 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v132 + 56LL))(v132, 2);
        LOBYTE(v141) = (_BYTE)v137;
        v142 = v139(v262, v140, v141);
        v143 = v142;
        if ( v142 )
        {
          if ( g_dmDiagnosticMode )
            DebugString(
              10,
              0,
              0,
              L"RESTART MANAGER: Failed to shut down all applications in the service's session. Error: %d",
              (const unsigned __int16 *)v142,
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
        v144 = (*(__int64 (__fastcall **)(struct IMsiEngine *, __int64, __int64))(*(_QWORD *)v1 + 24LL))(
                 v1,
                 402653184,
                 v132);
        if ( !v237 || v144 == 1 && !v143 )
        {
          if ( v144 != 1 )
            goto LABEL_175;
          (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v132 + 104LL))(v132, 1, 4);
          while ( 1 )
          {
            v144 = (*(__int64 (__fastcall **)(struct IMsiEngine *, __int64, __int64))(*(_QWORD *)v1 + 24LL))(
                     v1,
                     402653184,
                     v132);
            if ( v144 != 4 )
              break;
            Sleep(0x1F4u);
          }
          if ( (v144 != 1 || v143) && !v237 )
          {
LABEL_175:
            if ( v144 != 7 && !v143 )
            {
              CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v261);
              (*(void (__fastcall **)(void *))(*(_QWORD *)v271 + 16LL))(v271);
              (*(void (__fastcall **)(void *))(*(_QWORD *)v269 + 16LL))(v269);
              CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v252);
              goto LABEL_146;
            }
            if ( (_BYTE)v249 )
            {
              v213 = PostError(1611);
              CComPointer<IMsiDatabase>::operator=(&v247, v213);
              v2 = 2;
              if ( (*(unsigned int (__fastcall **)(struct IMsiEngine *, __int64, __int64))(*(_QWORD *)v1 + 24LL))(
                     v1,
                     50331953,
                     v247) != 2 )
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
                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v261);
                (*(void (__fastcall **)(void *))(*(_QWORD *)v271 + 16LL))(v271);
                (*(void (__fastcall **)(void *))(*(_QWORD *)v269 + 16LL))(v269);
                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v252);
                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v248);
                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v255);
                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v253);
                goto LABEL_248;
              }
              CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v261);
              goto LABEL_271;
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
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v261);
        (*(void (__fastcall **)(void *))(*(_QWORD *)v271 + 16LL))(v271);
        (*(void (__fastcall **)(void *))(*(_QWORD *)v269 + 16LL))(v269);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v252);
        goto LABEL_247;
      }
LABEL_271:
      (*(void (__fastcall **)(void *))(*(_QWORD *)v271 + 16LL))(v271);
      (*(void (__fastcall **)(void *))(*(_QWORD *)v269 + 16LL))(v269);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v252);
      goto LABEL_232;
    }
    if ( v237 )
      goto LABEL_153;
    if ( v120 )
    {
      v122 = PostError(1610);
      CComPointer<IMsiDatabase>::operator=(&v247, v122);
      v2 = 2;
      if ( (*(unsigned int (__fastcall **)(struct IMsiEngine *, __int64, __int64))(*(_QWORD *)v1 + 24LL))(
             v1,
             50331969,
             v247) == 2 )
        goto LABEL_232;
      if ( g_dmDiagnosticMode )
        goto LABEL_283;
      goto LABEL_247;
    }
LABEL_146:
    if ( v50 )
    {
LABEL_147:
      v123 = v248;
      goto LABEL_148;
    }
LABEL_177:
    v145 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v4 + 72LL);
    v146 = MsiString::MsiString((MsiString *)&v289, L"FilesInUse");
    LODWORD(v145) = v145(v4, *(_QWORD *)v146);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v289 + 16LL))(v289);
    if ( !(_DWORD)v145 )
      goto LABEL_147;
    v270 = 0;
    v147 = *(void (__fastcall **)(__int64, _QWORD, _QWORD, __int64))(*(_QWORD *)v4 + 80LL);
    v148 = CComPointer<IEnumMsiRecord>::operator=(&v270);
    v149 = MsiString::MsiString((MsiString *)&v290, L"FilesInUse");
    v147(v4, *(_QWORD *)v149, 0, v148);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v290 + 16LL))(v290);
    v150 = v270;
    v151 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v270 + 96LL);
    v152 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v4 + 120LL))(v4, L"FileName");
    v153 = v151(v150, v152);
    v154 = v270;
    LODWORD(v268) = v153;
    v155 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v270 + 96LL);
    v156 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v4 + 120LL))(v4, L"FilePath");
    v157 = v155(v154, v156);
    v158 = v270;
    LODWORD(v261) = v157;
    v159 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v270 + 96LL);
    v160 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v4 + 120LL))(v4, L"ProcessID");
    v161 = v159(v158, v160);
    v245 = v161;
    v162 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v270 + 128LL))(v270, 0);
    CComPointer<IMsiDatabase>::operator=(&v248, v162);
    v123 = v248;
    if ( !v248 )
    {
      v216 = PostError(2283, L"FilesInUse");
      v217 = *(_QWORD *)v1;
      v265 = v216;
      v2 = (*(__int64 (__fastcall **)(struct IMsiEngine *, struct IMsiRecord *))(v217 + 208))(v1, v216);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v265);
      goto LABEL_287;
    }
    v163 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v270 + 128LL))(v270, 0);
    v267 = v163;
    v164 = v163;
    if ( !v163 )
    {
      v214 = PostError(2283, L"FilesInUse");
      v215 = *(_QWORD *)v1;
      v265 = v214;
      v2 = (*(__int64 (__fastcall **)(struct IMsiEngine *, struct IMsiRecord *))(v215 + 208))(v1, v214);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v265);
      goto LABEL_285;
    }
    v165 = *v163;
    v166 = v161 ? (unsigned int)(1 << (v161 - 1)) : 0LL;
    (*(void (__fastcall **)(_QWORD *, __int64))(v165 + 48))(v164, v166);
    v252 = v3;
    InstallValidate_::_256_::CEnsureReleaseFileUseObj::StartAfresh(&v252);
    v246 = 0;
    v2 = 2;
LABEL_184:
    if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v123 + 40LL))(v123) )
      break;
    if ( v50 && g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        L"%d application(s) had been reported to have files in use.",
        (const unsigned __int16 *)(v246 / 2),
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    InstallValidate_::_256_::CEnsureReleaseFileUseObj::StartAfresh(&v252);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v267);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v270);
LABEL_148:
    v124 = 0;
    v245 = 0;
    if ( v50 )
    {
      v125 = (*(__int64 (__fastcall **)(struct IMsiEngine *, __int64, _QWORD *))(*(_QWORD *)v1 + 24LL))(
               v1,
               83886080,
               v50);
      if ( v123 )
      {
        v126 = *(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v4 + 96LL);
        v127 = MsiString::MsiString((MsiString *)&v265, L"FilesInUse");
        v126(v4, *(_QWORD *)v127, 0);
        (*(void (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)v265 + 16LL))(v265);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v123 + 32LL))(v123);
        while ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v123 + 40LL))(v123) )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v123 + 184LL))(v123);
        v124 = 0;
      }
      v2 = 2;
      if ( v125 == 4 )
      {
        v124 = 1;
        v245 = 1;
      }
      else if ( v125 == 2 )
      {
        goto LABEL_232;
      }
    }
    else
    {
      v2 = 2;
    }
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v248);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v255);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v253);
    if ( !v124 )
      goto LABEL_248;
    Instance = v262;
    v44 = v245;
  }
  if ( (*(unsigned int (__fastcall **)(struct IMsiEngine *))(*(_QWORD *)v1 + 312LL))(v1) == 2 )
    goto LABEL_190;
  if ( (*(unsigned int (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v123 + 56LL))(v123, v245) != 0x80000000 )
    goto LABEL_184;
  v167 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v123 + 64LL))(v123, (unsigned int)v268);
  v168 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v248 + 64LL))(v248, (unsigned int)v261);
  v274 = 0;
  v169 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v3 + 176LL);
  v170 = CComPointer<IEnumMsiRecord>::operator=(&v274);
  v171 = v169(v3, v167, v170);
  CComPointer<IMsiDatabase>::operator=(&v247, v171);
  if ( !v247 )
  {
    v172 = v274;
    if ( v274 )
    {
      v173 = v256;
      v266 = 0;
      while ( 1 )
      {
        v258 = *(unsigned __int16 **)(*(_QWORD *)v172 + 24LL);
        v174 = CComPointer<IEnumMsiRecord>::operator=(&v266);
        if ( ((unsigned int (__fastcall *)(__int64, __int64, __int64))v258)(v172, 1, v174) )
          break;
        v175 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)v266 + 80LL))(v266, 1);
        MsiString::MsiString((MsiString *)&v277, v175);
        v176 = &MsiString::s_NullString;
        v242 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)v266 + 56LL))(v266, 2);
        if ( v242 == GetCurrentProcessId()
          || (v250 |= 2u,
              v258 = *(unsigned __int16 **)(*(_QWORD *)v259 + 192LL),
              v177 = MsiString::MsiString((MsiString *)&v291, L"CLIENTPROCESSID"),
              v238 = 1,
              v242 == ((unsigned int (__fastcall *)(struct IMsiEngine *, _QWORD))v258)(v259, *(_QWORD *)v177)) )
        {
          v238 = 0;
        }
        if ( (v250 & 2) != 0 )
        {
          v250 &= ~2u;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v291 + 16LL))(v291);
        }
        if ( v238 )
        {
          v176 = (void *)(*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v277 + 176LL))(v277, 6, 92);
          (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
          if ( !(*(unsigned int (__fastcall **)(void *, __int64, const wchar_t *))(*(_QWORD *)v176 + 200LL))(
                  v176,
                  3,
                  L"explorer")
            && !(*(unsigned int (__fastcall **)(void *, __int64, const wchar_t *))(*(_QWORD *)v176 + 200LL))(
                  v176,
                  3,
                  L"msiexec") )
          {
            (*(void (__fastcall **)(_QWORD *))(*v164 + 32LL))(v164);
            (*(void (__fastcall **)(_QWORD *, _QWORD, __int64))(*v164 + 96LL))(v164, (unsigned int)v268, v167);
            (*(void (__fastcall **)(_QWORD *, _QWORD, __int64))(*v164 + 96LL))(v164, (unsigned int)v261, v168);
            (*(void (__fastcall **)(_QWORD *, _QWORD, _QWORD))(*v164 + 88LL))(v164, v245, v242);
            if ( !(*(unsigned int (__fastcall **)(_QWORD *))(*v164 + 40LL))(v164) )
            {
              (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v248 + 88LL))(v248, v245, v242);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v248 + 136LL))(v248);
              v178 = v246;
              if ( !(v246 % 8) )
              {
                v258 = (unsigned __int16 *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v3 + 48LL))(
                                             v3,
                                             (unsigned int)(v246 + 8));
                (*(void (__fastcall **)(unsigned __int16 *, _QWORD *))(*(_QWORD *)v258 + 200LL))(v258, v50);
                CComPointer<IXMLDOMElement>::operator=(&v253, &v258);
                v50 = v253;
                if ( !v246 )
                {
                  v292 = *(void (__fastcall **)(_QWORD *, _QWORD, _QWORD))(*v253 + 120LL);
                  v278 = (void (__fastcall *)(__int64, __int64, _QWORD))(*(__int64 (__fastcall **)(struct IMsiEngine *, __int64))(*(_QWORD *)v259 + 416LL))(
                                                                          v259,
                                                                          1607);
                  v292(v50, 0, v278);
                  (*(void (__fastcall **)(void (__fastcall *)(__int64, __int64, _QWORD)))(*(_QWORD *)v278 + 16LL))(v278);
                }
                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v258);
                v178 = v246;
              }
              v179 = *v50;
              v246 = v178 + 1;
              (*(void (__fastcall **)(_QWORD *, _QWORD, __int64))(v179 + 120))(v50, (unsigned int)(v178 + 1), v277);
              v180 = *v50;
              (*(void (__fastcall **)(_QWORD *, _QWORD, _QWORD))(v180 + 104))(v50, (unsigned int)++v246, v242);
            }
          }
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v173 + 160LL))(v173);
        (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v173 + 104LL))(v173, 1, 1603);
        (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v173 + 120LL))(v173, 2, v168);
        (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v173 + 120LL))(v173, 3, v167);
        (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v173 + 120LL))(v173, 4, v277);
        (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v173 + 104LL))(v173, 5, v242);
        v278 = *(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v173 + 120LL);
        v181 = MsiString::MsiString((MsiString *)&v275, L"(not determined yet)");
        v278(v173, 6, *(_QWORD *)v181);
        (*(void (__fastcall **)(CMsiBaselineManager *))(*(_QWORD *)v275 + 16LL))(v275);
        (*(void (__fastcall **)(struct IMsiEngine *, __int64, __int64))(*(_QWORD *)v259 + 24LL))(v259, 0x4000000, v173);
        (*(void (__fastcall **)(void *))(*(_QWORD *)v176 + 16LL))(v176);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v277 + 16LL))(v277);
        v172 = v274;
      }
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v266);
      v4 = v276;
    }
    v2 = 2;
    goto LABEL_211;
  }
  v2 = 2;
  if ( (*(unsigned int (__fastcall **)(struct IMsiEngine *, __int64))(*(_QWORD *)v259 + 24LL))(v259, 0x4000000) != 2 )
  {
LABEL_211:
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v274);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v168 + 16LL))(v168);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v167 + 16LL))(v167);
    v1 = v259;
    v123 = v248;
    goto LABEL_184;
  }
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v274);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v168 + 16LL))(v168);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v167 + 16LL))(v167);
LABEL_190:
  InstallValidate_::_256_::CEnsureReleaseFileUseObj::StartAfresh(&v252);
LABEL_285:
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v267);
LABEL_287:
  v185 = &v270;
LABEL_231:
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v185);
LABEL_232:
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v248);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v255);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v253);
LABEL_225:
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v251);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v254);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v256);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v247);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v257);
LABEL_324:
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v272);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v276);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v280);
  return v2;
}

```

## disassembly

```asm
0x18015fa10  push    rbp
0x18015fa12  push    rbx
0x18015fa13  push    rsi
0x18015fa14  push    rdi
0x18015fa15  push    r12
0x18015fa17  push    r13
0x18015fa19  push    r14
0x18015fa1b  push    r15
0x18015fa1d  lea     rbp, [rsp-778h]
0x18015fa25  sub     rsp, 878h
0x18015fa2c  mov     rax, cs:__security_cookie
0x18015fa33  xor     rax, rsp
0x18015fa36  mov     [rbp+7B0h+var_50], rax
0x18015fa3d  xor     edi, edi
0x18015fa3f  mov     [rbp+7B0h+var_7E8], rcx
0x18015fa43  mov     dword ptr [rsp+8B0h+var_838], edi
0x18015fa47  mov     r12, rcx
0x18015fa4a  lea     r14d, [rdi+2]
0x18015fa4e  cmp     cs:?g_scServerContext@@3W4scEnum@@A, r14d; scEnum g_scServerContext
0x18015fa55  jnz     short loc_18015FA7E
0x18015fa57  mov     rax, [rcx]
0x18015fa5a  mov     rax, [rax+1B0h]
0x18015fa61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015fa66  test    al, al
0x18015fa68  jnz     short loc_18015FA7E
0x18015fa6a  mov     rcx, cs:qword_180309730; this
0x18015fa71  test    rcx, rcx
0x18015fa74  jz      short loc_18015FA7E
0x18015fa76  mov     rdx, r12; struct IMsiEngine *
0x18015fa79  call    ?RecordInstallType@CMsiSQMSession@@QEAAXAEAVIMsiEngine@@@Z; CMsiSQMSession::RecordInstallType(IMsiEngine &)
0x18015fa7e  mov     rax, [r12]
0x18015fa82  mov     rcx, r12
0x18015fa85  mov     rax, [rax+38h]
0x18015fa89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015fa8e  mov     r13, rax
0x18015fa91  mov     [rbp+7B0h+var_740], rax
0x18015fa95  mov     rax, [r12]
0x18015fa99  mov     rcx, r12
0x18015fa9c  mov     rax, [rax+48h]
0x18015faa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015faa5  lea     r8, IID_IMsiSelectionManager
0x18015faac  mov     [rbp+7B0h+var_760], rax
0x18015fab0  mov     rdx, r12
0x18015fab3  lea     rcx, [rbp+7B0h+var_780]
0x18015fab7  mov     r15, rax
0x18015faba  call    ??0?$CComPointer@VIMsiSelectionManager@@@@QEAA@AEAUIUnknown@@AEBU_GUID@@@Z; CComPointer<IMsiSelectionManager>::CComPointer<IMsiSelectionManager>(IUnknown &,_GUID const &)
0x18015fabf  mov     rax, [r12]
0x18015fac3  mov     rcx, r12
0x18015fac6  mov     rax, [rax+138h]
0x18015facd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015fad2  cmp     eax, r14d
0x18015fad5  jz      loc_180162B3E
0x18015fadb  mov     rax, [r12]
0x18015fadf  lea     rdx, aMsirestartmana_0; "MsiRestartManagerSessionKey"
0x18015fae6  lea     rcx, [rbp+7B0h+var_7F0]; this
0x18015faea  mov     rbx, [rax+0A0h]
0x18015faf1  call    ??0MsiString@@QEAA@AEBG@Z; MsiString::MsiString(ushort const &)
0x18015faf6  lea     r8, ?g_MsiStringNull@@3VCMsiStringNull@@B; CMsiStringNull const g_MsiStringNull
0x18015fafd  mov     rcx, r12
0x18015fb00  mov     rdx, [rax]
0x18015fb03  mov     rax, rbx
0x18015fb06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015fb0b  mov     rcx, [rbp+7B0h+var_7F0]
0x18015fb0f  mov     rax, [rcx]
0x18015fb12  mov     rax, [rax+10h]
0x18015fb16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015fb1b  mov     rax, [r13+0]
0x18015fb1f  mov     edx, r14d
0x18015fb22  mov     rcx, r13
0x18015fb25  mov     rax, [rax+30h]
0x18015fb29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015fb2e  mov     [rbp+7B0h+var_7F8], rax
0x18015fb32  mov     edx, 6
0x18015fb37  mov     [rsp+8B0h+var_840], rdi
0x18015fb3c  mov     rcx, r13
0x18015fb3f  mov     rax, [r13+0]
0x18015fb43  mov     rax, [rax+30h]
0x18015fb47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015fb4c  mov     [rbp+7B0h+var_810], rdi
0x18015fb50  lea     rcx, [rbp+7B0h+var_810]
0x18015fb54  mov     [rbp+7B0h+var_828], rdi
0x18015fb58  mov     esi, edi
0x18015fb5a  mov     [rbp+7B0h+var_800], rax
0x18015fb5e  mov     rax, [r15]
0x18015fb61  mov     byte ptr [rbp+7B0h+var_830], dil
0x18015fb65  mov     rdi, [rax+50h]
0x18015fb69  call    ??4?$CComPointer@VIEnumMsiRecord@@@@QEAAAEAV0@PEAVIEnumMsiRecord@@@Z; CComPointer<IEnumMsiRecord>::operator=(IEnumMsiRecord *)
0x18015fb6e  lea     rdx, aDialog; "Dialog"
0x18015fb75  mov     rbx, rax
0x18015fb78  lea     rcx, [rbp+7B0h+var_7F0]; this
0x18015fb7c  call    ??0MsiString@@QEAA@AEBG@Z; MsiString::MsiString(ushort const &)
0x18015fb81  mov     r9, rbx
0x18015fb84  xor     r8d, r8d
0x18015fb87  mov     rcx, r15
0x18015fb8a  mov     rdx, [rax]
0x18015fb8d  mov     rax, rdi
0x18015fb90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015fb95  mov     rdx, rax
0x18015fb98  lea     rcx, [rsp+8B0h+var_840]
0x18015fb9d  call    ??4?$CComPointer@VIMsiDatabase@@@@QEAAAEAV0@PEAVIMsiDatabase@@@Z; CComPointer<IMsiDatabase>::operator=(IMsiDatabase *)
0x18015fba2  cmp     [rax], rsi
0x18015fba5  jnz     short loc_18015FC05
0x18015fba7  mov     rcx, [rbp+7B0h+var_810]
0x18015fbab  xor     edx, edx
0x18015fbad  mov     rax, [rcx]
0x18015fbb0  mov     rax, [rax+80h]
0x18015fbb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015fbbc  mov     rdx, rax
0x18015fbbf  lea     rcx, [rbp+7B0h+var_828]
0x18015fbc3  call    ??4?$CComPointer@VIMsiDatabase@@@@QEAAAEAV0@PEAVIMsiDatabase@@@Z; CComPointer<IMsiDatabase>::operator=(IMsiDatabase *)
0x18015fbc8  cmp     [rax], rsi
0x18015fbcb  jz      short loc_18015FC05
0x18015fbcd  mov     rdi, [rbp+7B0h+var_810]
0x18015fbd1  lea     rdx, aDialog_0; "Dialog"
0x18015fbd8  mov     rcx, r15
0x18015fbdb  mov     rax, [rdi]
0x18015fbde  mov     rbx, [rax+60h]
0x18015fbe2  mov     rax, [r15]
0x18015fbe5  mov     rax, [rax+78h]
0x18015fbe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015fbee  mov     edx, eax
0x18015fbf0  mov     rcx, rdi
0x18015fbf3  mov     rax, rbx
0x18015fbf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015fbfb  mov     esi, eax
0x18015fbfd  test    eax, eax
0x18015fbff  jz      short loc_18015FC05
0x18015fc01  mov     bl, 1
0x18015fc03  jmp     short loc_18015FC07
0x18015fc05  xor     bl, bl
0x18015fc07  mov     rcx, [rbp+7B0h+var_7F0]
0x18015fc0b  mov     rax, [rcx]
0x18015fc0e  mov     rax, [rax+10h]
0x18015fc12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015fc17  test    bl, bl
0x18015fc19  jz      short loc_18015FC8B
0x18015fc1b  mov     rcx, [rbp+7B0h+var_828]
0x18015fc1f  mov     edx, esi
0x18015fc21  mov     rax, [rcx]
0x18015fc24  mov     rax, [rax+30h]
0x18015fc28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015fc2d  mov     rdi, [rbp+7B0h+var_828]
0x18015fc31  lea     rdx, aMsirmfilesinus; "MsiRMFilesInUse"
0x18015fc38  lea     rcx, [rbp+7B0h+var_7F0]; this
0x18015fc3c  mov     rax, [rdi]
0x18015fc3f  mov     rbx, [rax+60h]
0x18015fc43  call    ??0MsiString@@QEAA@PEBG@Z; MsiString::MsiString(ushort const *)
0x18015fc48  mov     edx, esi
0x18015fc4a  mov     rcx, rdi
0x18015fc4d  mov     r8, [rax]
0x18015fc50  mov     rax, rbx
0x18015fc53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015fc58  mov     rcx, [rbp+7B0h+var_7F0]
0x18015fc5c  mov     rax, [rcx]
0x18015fc5f  mov     rax, [rax+10h]
0x18015fc63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015fc68  mov     rcx, [rbp+7B0h+var_828]
0x18015fc6c  mov     rax, [rcx]
0x18015fc6f  mov     rax, [rax+28h]
0x18015fc73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015fc78  mov     ecx, [rbp+7B0h+var_830]
0x18015fc7b  test    eax, eax
0x18015fc7d  movzx   ecx, cl
0x18015fc80  mov     eax, 1
0x18015fc85  cmovnz  ecx, eax
0x18015fc88  mov     [rbp+7B0h+var_830], ecx
0x18015fc8b  mov     ecx, 0Ah; int
0x18015fc90  call    ?FDiagnosticModeSet@@YA_NH@Z; FDiagnosticModeSet(int)
0x18015fc95  test    al, al
0x18015fc97  jz      loc_180160445
0x18015fc9d  movaps  xmm0, xmmword ptr cs:aSelectFeatureA; " SELECT `Feature`, `Action`, `ActionReq"...
0x18015fca4  movaps  xmm1, xmmword ptr cs:aSelectFeatureA+10h; "`Feature`, `Action`, `ActionRequested`,"...
0x18015fcab  mov     rax, qword ptr cs:aSelectFeatureA+8Eh; "re`"
0x18015fcb2  movups  [rbp+7B0h+var_1E0], xmm0
0x18015fcb9  movaps  xmm0, xmmword ptr cs:aSelectFeatureA+20h; "`, `Action`, `ActionRequested`, `Instal"...
0x18015fcc0  movups  [rbp+7B0h+var_1C0], xmm0
0x18015fcc7  movaps  xmm0, xmmword ptr cs:aSelectFeatureA+40h; "tionRequested`, `Installed` FROM `Featu"...
0x18015fcce  movups  [rbp+7B0h+var_1A0], xmm0
0x18015fcd5  movaps  xmm0, xmmword ptr cs:aSelectFeatureA+60h; "`Installed` FROM `Feature`"
0x18015fcdc  movups  [rbp+7B0h+var_180], xmm0
0x18015fce3  movaps  xmm0, xmmword ptr cs:aSelectFeatureA+80h; " `Feature`"
0x18015fcea  movups  xmmword ptr [rbp+7B0h+var_160], xmm0
0x18015fcf1  mov     qword ptr [rbp+7B0h+var_160+0Eh], rax
0x18015fcf8  xor     eax, eax
0x18015fcfa  xorps   xmm0, xmm0
0x18015fcfd  mov     [rbp+7B0h+var_11A], ax
0x18015fd04  movups  [rbp+7B0h+var_1D0], xmm1
0x18015fd0b  mov     [rbp+7B0h+var_5C], rax
0x18015fd12  movaps  xmm1, xmmword ptr cs:aSelectFeatureA+30h; "on`, `ActionRequested`, `Installed` FRO"...
0x18015fd19  movups  [rbp+7B0h+var_14A], xmm0
0x18015fd20  mov     [rbp+7B0h+var_54], eax
0x18015fd26  movups  [rbp+7B0h+var_13A], xmm0
0x18015fd2d  mov     [rbp+7B0h+var_3B0], rax
0x18015fd34  mov     eax, dword ptr cs:aComponent+10h; "t"
0x18015fd3a  movups  [rbp+7B0h+var_12A], xmm0
0x18015fd41  mov     [rbp+7B0h+var_398], eax
0x18015fd47  xor     eax, eax
0x18015fd49  movaps  xmm0, xmmword ptr cs:aSelectComponen_13; " SELECT `Component`, `Action`, `ActionR"...
0x18015fd50  movups  [rbp+7B0h+var_1B0], xmm1
0x18015fd57  mov     [rbp+7B0h+var_394], eax
0x18015fd5d  mov     eax, dword ptr cs:aAbsent+8; "nt"
0x18015fd63  movaps  xmm1, xmmword ptr cs:aSelectFeatureA+50h; "ested`, `Installed` FROM `Feature`"
0x18015fd6a  movups  [rbp+7B0h+var_118], xmm0
0x18015fd71  mov     [rbp+7B0h+var_388], eax
0x18015fd77  movzx   eax, word ptr cs:aAbsent+0Ch; ""
0x18015fd7e  movaps  xmm0, xmmword ptr cs:aSelectComponen_13+20h; "nt`, `Action`, `ActionRequest`, `Instal"...
0x18015fd85  movups  [rbp+7B0h+var_190], xmm1
0x18015fd8c  mov     [rbp+7B0h+var_384], ax
0x18015fd93  movaps  xmm1, xmmword ptr cs:aSelectFeatureA+70h; "ed` FROM `Feature`"
0x18015fd9a  mov     eax, dword ptr cs:aLocal+8; "l"
0x18015fda0  movups  [rbp+7B0h+var_F8], xmm0
0x18015fda7  mov     [rbp+7B0h+var_36A], eax
0x18015fdad  xor     eax, eax
0x18015fdaf  movaps  xmm0, xmmword ptr cs:aSelectComponen_13+40h; "ActionRequest`, `Installed`, `TrueInsta"...
0x18015fdb6  movups  [rbp+7B0h+var_170], xmm1
0x18015fdbd  mov     [rbp+7B0h+var_356], ax
0x18015fdc4  movaps  xmm1, xmmword ptr cs:aSelectComponen_13+10h; "`Component`, `Action`, `ActionRequest`,"...
0x18015fdcb  mov     eax, dword ptr cs:aSource_1+8; "ce"
0x18015fdd1  movups  [rbp+7B0h+var_D8], xmm0
0x18015fdd8  mov     [rbp+7B0h+var_34C], eax
0x18015fdde  movaps  xmm0, xmmword ptr cs:aSelectComponen_13+60h; "`Installed`, `TrueInstallSt` FROM `Comp"...
0x18015fde5  movzx   eax, word ptr cs:aSource_1+0Ch; ""
0x18015fdec  movups  [rbp+7B0h+var_108], xmm1
0x18015fdf3  movaps  xmm1, xmmword ptr cs:aSelectComponen_13+30h; "tion`, `ActionRequest`, `Installed`, `T"...
0x18015fdfa  movups  [rbp+7B0h+var_B8], xmm0
0x18015fe01  movaps  xmm0, xmmword ptr cs:aSelectComponen_13+80h; "ueInstallSt` FROM `Component`"
0x18015fe08  movups  [rbp+7B0h+var_E8], xmm1
0x18015fe0f  movaps  xmm1, xmmword ptr cs:aSelectComponen_13+50h; "quest`, `Installed`, `TrueInstallSt` FR"...
0x18015fe16  movups  [rbp+7B0h+var_98], xmm0
0x18015fe1d  movaps  xmm0, xmmword ptr cs:aSelectComponen_13+0A0h; "M `Component`"
0x18015fe24  movups  [rbp+7B0h+var_C8], xmm1
0x18015fe2b  movaps  xmm1, xmmword ptr cs:aSelectComponen_13+70h; "ed`, `TrueInstallSt` FROM `Component`"
0x18015fe32  movups  xmmword ptr [rbp+7B0h+var_78], xmm0
0x18015fe39  movups  xmm0, xmmword ptr cs:aFeature; "Feature"
0x18015fe40  movups  [rbp+7B0h+var_A8], xmm1
0x18015fe47  movaps  xmm1, xmmword ptr cs:aSelectComponen_13+90h; "lSt` FROM `Component`"
0x18015fe4e  movdqu  [rbp+7B0h+var_3C0], xmm0
0x18015fe56  movups  xmm0, xmmword ptr cs:aComponent; "Component"
0x18015fe5d  movups  [rbp+7B0h+var_88], xmm1
0x18015fe64  movups  xmm1, xmmword ptr cs:aSelectComponen_13+0ACh; "ponent`"
0x18015fe6b  movups  [rbp+7B0h+var_3A8], xmm0
0x18015fe72  movsd   xmm0, qword ptr cs:aAbsent; "Absent"
0x18015fe7a  movups  xmmword ptr [rbp+7B0h+var_78+0Ch], xmm1
0x18015fe81  movsd   xmm1, qword ptr cs:aLocal; "Local"
0x18015fe89  movsd   [rbp+7B0h+var_390], xmm0
0x18015fe91  xorps   xmm0, xmm0
0x18015fe94  movsd   [rbp+7B0h+var_372], xmm1
0x18015fe9c  movsd   xmm1, qword ptr cs:aSource_1; "Source"
0x18015fea4  movups  [rbp+7B0h+var_382], xmm0
0x18015feab  movups  [rbp+7B0h+var_366], xmm0
0x18015feb2  movsd   [rbp+7B0h+var_354], xmm1
0x18015feba  movups  xmm1, xmmword ptr cs:aReinstall_1; "Reinstall"
0x18015fec1  mov     [rbp+7B0h+var_348], ax
0x18015fec8  mov     eax, dword ptr cs:aReinstall_1+10h; "l"
0x18015fece  mov     [rbp+7B0h+var_326], eax
0x18015fed4  xor     eax, eax
0x18015fed6  mov     [rbp+7B0h+var_322], rax
0x18015fedd  mov     [rbp+7B0h+var_31A], ax
0x18015fee4  mov     eax, dword ptr cs:aAdvertise+10h; "e"
0x18015feea  mov     [rbp+7B0h+var_308], eax
0x18015fef0  xor     eax, eax
0x18015fef2  mov     [rbp+7B0h+var_304], rax
0x18015fef9  mov     [rbp+7B0h+var_2FC], ax
0x18015ff00  mov     [rbp+7B0h+var_2EA], rax
0x18015ff07  mov     [rbp+7B0h+var_2E2], eax
0x18015ff0d  mov     [rbp+7B0h+var_2DE], ax
0x18015ff14  mov     [rbp+7B0h+var_2C6], rax
0x18015ff1b  mov     [rbp+7B0h+var_2BE], ax
0x18015ff22  mov     [rbp+7B0h+var_2A0], ax
0x18015ff29  mov     [rbp+7B0h+var_282], ax
0x18015ff30  mov     [rbp+7B0h+var_264], ax
0x18015ff37  mov     [rbp+7B0h+var_230], rax
0x18015ff3e  movzx   eax, word ptr cs:aNull_1+8; ""
0x18015ff45  mov     [rbp+7B0h+var_202], ax
0x18015ff4c  xor     eax, eax
0x18015ff4e  mov     [rbp+7B0h+var_1F0], eax
0x18015ff54  lea     rax, aNotUsed; "Not Used"
0x18015ff5b  mov     [rbp+7B0h+var_6D0], rax
0x18015ff62  lea     rax, aBadConfig; "Bad Config"
0x18015ff69  mov     [rbp+7B0h+var_6C8], rax
0x18015ff70  lea     rax, aIncomplete; "Incomplete"
0x18015ff77  mov     [rbp+7B0h+var_6C0], rax
0x18015ff7e  lea     rax, aSourceAbsent; "Source Absent"
0x18015ff85  mov     [rbp+7B0h+var_6B8], rax
0x18015ff8c  lea     rax, aMoreData; "More Data"
0x18015ff93  movups  [rbp+7B0h+var_346], xmm0
0x18015ff9a  mov     [rbp+7B0h+var_6B0], rax
0x18015ffa1  lea     rax, aInvalidArg; "Invalid Arg"
0x18015ffa8  movups  xmm0, xmmword ptr cs:aAdvertise; "Advertise"
0x18015ffaf  mov     [rbp+7B0h+var_6A8], rax
0x18015ffb6  lea     rax, aUnknown_2; "Unknown"
0x18015ffbd  mov     [rbp+7B0h+var_6A0], rax
0x18015ffc4  lea     rax, aBroken; "Broken"
0x18015ffcb  movups  [rbp+7B0h+var_318], xmm0
0x18015ffd2  mov     [rbp+7B0h+var_698], rax
0x18015ffd9  lea     rax, aAdvertisedRemo; "Advertised/Removed"
0x18015ffe0  movups  xmm0, xmmword ptr cs:aCurrent; "Current"
0x18015ffe7  mov     [rbp+7B0h+var_690], rax
0x18015ffee  lea     rax, aAbsent; "Absent"
0x18015fff5  movups  [rbp+7B0h+var_336], xmm1
  ... truncated ...
```
