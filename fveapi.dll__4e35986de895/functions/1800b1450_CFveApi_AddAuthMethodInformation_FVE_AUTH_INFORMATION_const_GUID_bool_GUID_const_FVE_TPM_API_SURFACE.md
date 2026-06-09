# CFveApi::AddAuthMethodInformation(_FVE_AUTH_INFORMATION const *,_GUID *,bool,_GUID const *,_FVE_TPM_API_SURFACE *)

- ea: `0x1800b1450`
- end: `0x1800b58f2`
- name: `?AddAuthMethodInformation@CFveApi@@QEAAJPEBU_FVE_AUTH_INFORMATION@@PEAU_GUID@@_NPEBU3@PEAU_FVE_TPM_API_SURFACE@@@Z`
- size: `17570`
- prototype: `__int64 __fastcall(CFveApi *this, const struct _FVE_AUTH_INFORMATION *, struct _GUID *, char, const struct _GUID *, struct _FVE_TPM_API_SURFACE *)`
- caller_count: `9`
- callee_count: `87`
- tags: `authz_impersonation, registry_config, service_task, installer_update`

## callers

- `0x1800403f0`
- `0x18004adb0`
- `0x18006cb80`
- `0x1800b58f8`
- `0x1800b5aa0`
- `0x1800bd808`
- `0x1800c1820`
- `0x1800d0dc8`
- `0x1800d0ff0`

## callees

- `0x180002f14`
- `0x180003284`
- `0x180008d70`
- `0x1800090c0`
- `0x180009130`
- `0x180009468`
- `0x18000ba30`
- `0x180017304`
- `0x180018b10`
- `0x180018c68`
- `0x180019128`
- `0x18001b260`
- `0x18001f010`
- `0x18001f044`
- `0x1800301c8`
- `0x180037edc`
- `0x180037f50`
- `0x18003d000`
- `0x18003e7a8`
- `0x18003ed0c`
- `0x180042cc4`
- `0x1800450c4`
- `0x180045444`
- `0x180046a90`
- `0x180047640`
- `0x180047a48`
- `0x180047fd8`
- `0x180048cc8`
- `0x180048db4`
- `0x180048ecc`
- `0x180049cc0`
- `0x18004ad74`
- `0x18004b050`
- `0x18004dba8`
- `0x18004e554`
- `0x18004f54c`
- `0x180050130`
- `0x180050154`
- `0x180053a20`
- `0x180053a80`
- `0x180053b5c`
- `0x180053bac`
- `0x180053e64`
- `0x180055c44`
- `0x180060196`
- `0x18006d8ac`
- `0x180070a0c`
- `0x180076b1c`
- `0x18007dfc8`
- `0x18007e388`

## import_xrefs

- `bcrypt!BCryptGetProperty` at `0x1800b1e57`
- `bcrypt!BCryptGetProperty` at `0x1800b1e57`
- `FVECERTS!FveCertIsValidCertInfo` at `0x1800b2010`
- `FVECERTS!FveCertIsValidCertInfo` at `0x1800b2010`
- `FVECERTS!FveCertFreeCertInfo` at `0x1800b5823`
- `FVECERTS!FveCertFreeCertInfo` at `0x180125f62`
- `FVECERTS!FveCertFreeCertInfo` at `0x1800b5823`
- `FVECERTS!FveCertFreeCertInfo` at `0x180125f62`
- `TpmCoreProvisioning!TpmGetTpmVersion` at `0x1800b1b2c`
- `TpmCoreProvisioning!TpmGetTpmVersion` at `0x1800b1b2c`
- `pcrpf!PpfFreePredictions` at `0x1800b5865`
- `pcrpf!PpfFreePredictions` at `0x180125fa5`
- `pcrpf!PpfFreePredictions` at `0x1800b5865`
- `pcrpf!PpfFreePredictions` at `0x180125fa5`

## string_xrefs

- `0x1800b4caf`: `VolumePath`
- `0x1800b504b`: `VolumePath`
- `0x1800b537b`: `VolumePath`
- `0x18012540d`: `VolumePath`
- `0x18012578a`: `VolumePath`
- `0x180125ac8`: `VolumePath`
- `0x1800b4e4a`: `ServiceName`
- `0x1801255be`: `ServiceName`
- `0x1800b18f4`: `ReadFipsSetting`
- `0x1800b1a38`: `ResolveVolumeMountName`
- `0x1800b1c67`: `AuthFlagsIdentitySet`
- `0x1800b2639`: `DatumKeyCreate`
- `0x1800b27a0`: `PPFveDatumKeyCreate`
- `0x1800b27dd`: `PPSaltFveDatumKeyCreate`
- `0x1800b1ec7`: `PKProtectorTemplate`
- `0x1800b2155`: `PKnbpFveCertCreateCertInfoFromBuffer`
- `0x1800b21b9`: `PKnbpFveDatumPublicKeyInfoCreate1`
- `0x1800b2252`: `PKnbpFveDatumPublicKeyInfoCreate2`
- `0x1800b2b83`: `DNGFveDatumKeyCreate`
- `0x1800b2bc3`: `CreateDpapiNgPublicKeyInfo`
- `0x1800b2ce8`: `ExternalKeyFveDatumKeyCreate`
- `0x1800b2d7e`: `TypePasswordFveDatumKeyCreate`
- `0x1800b315e`: `FveDatumUnicodeCreate`
- `0x1800b353a`: `CreateTpmContextWithTpmStateInfo`
- `0x1800b37f5`: `CreateTpmContext`
- `0x1800b3bd6`: `CreateTpmProtectorBindingDigestSourceData`
- `0x1800b413c`: `AdaRevertAndCheckIsSchemaExtInstalled`
- `0x1800b41b2`: `ADSchemaNotInstalled`
- `0x1800b44a6`: `AttemptAADBackup`
- `0x1800b45d4`: `AttemptADBackup`

## pseudocode

```c
__int64 __fastcall CFveApi::AddAuthMethodInformation(
        CFveApi *this,
        const struct _FVE_AUTH_INFORMATION *a2,
        struct _GUID *a3,
        char a4,
        const struct _GUID *a5,
        struct _FVE_TPM_API_SURFACE *a6)
{
  CFveApiBase *v8; // r13
  const wchar_t *v9; // rsi
  char v10; // r14
  __int64 v11; // rdx
  int FirmwareType; // ebx
  char v13; // r14
  int v14; // r15d
  int v15; // eax
  __int64 *v16; // r11
  unsigned int v17; // r12d
  __int64 v18; // r8
  struct _FVE_AUTH_INFORMATION *v19; // rdi
  __int64 v20; // r15
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // eax
  void *v26; // r12
  NTSTATUS Property; // eax
  char *v28; // rax
  struct _GUID *v29; // rdi
  int v30; // eax
  CFveApi *v31; // rcx
  unsigned int v32; // eax
  _DWORD *v33; // r13
  int IsValidCertInfo; // eax
  size_t v35; // rbx
  size_t v36; // r12
  int v37; // edi
  unsigned __int8 *v38; // rax
  char *v39; // rdi
  __int64 v40; // r9
  int v41; // eax
  int v42; // ecx
  int v43; // eax
  __int64 v44; // rdx
  int v45; // eax
  int v46; // ecx
  struct _GUID *v47; // r15
  __int64 v48; // rax
  struct _GUID *v49; // rcx
  int v50; // eax
  unsigned __int64 v51; // rax
  __int128 *v52; // rdx
  int v53; // eax
  int v54; // ecx
  int v55; // eax
  int v56; // eax
  __int64 v57; // r15
  int v58; // eax
  unsigned int v59; // eax
  unsigned int v60; // eax
  __int64 v61; // rcx
  struct _FVE_TPM_STATE_EX_ *v62; // rax
  _QWORD *v63; // rcx
  __int64 v64; // rdx
  __int64 v65; // r9
  int v66; // eax
  unsigned __int8 v67; // cl
  char v68; // al
  int v69; // eax
  unsigned __int64 v70; // r10
  __int128 *v71; // rdx
  int v72; // eax
  char v73; // di
  PVOID *v74; // rcx
  struct _FVE_AUTH_INFORMATION *v75; // rbx
  char v76; // bl
  int v77; // ebx
  _WORD *v78; // rcx
  int v79; // eax
  int v80; // edi
  PVOID *v81; // rcx
  CFveApiBase *v82; // rcx
  __int64 v83; // r8
  __int64 v84; // rdx
  __int64 v85; // rdx
  unsigned int v86; // ebx
  struct _FVE_TPM_API_SURFACE *v87; // rbx
  unsigned int v88; // edx
  unsigned __int64 v89; // rcx
  unsigned int v90; // eax
  int v91; // edx
  int v92; // eax
  int v93; // r8d
  char v94; // bl
  int DomainInfo; // eax
  char v96; // r14
  int v97; // eax
  PVOID *v98; // rcx
  int v99; // edi
  BOOL v100; // eax
  PVOID *v101; // rcx
  char v102; // al
  char v103; // di
  int v104; // eax
  struct _FVE_DATUM_VMK_INFO *v105; // rbx
  int v106; // eax
  struct _FVE_DATUM_VMK_INFO *v107; // rbx
  int Count; // eax
  PVOID *v109; // rcx
  __int16 v110; // r8
  int appended; // eax
  CFveApiBase *v112; // r14
  __int64 v113; // rax
  const unsigned __int16 *LoggingVolumePath; // rax
  const unsigned __int16 *v115; // rdx
  const unsigned __int16 *LoggingVolumeDriveLetter; // rax
  const unsigned __int16 *v117; // rdx
  const unsigned __int16 *LoggingServiceName; // rax
  const unsigned __int16 *v119; // rdx
  __int64 v120; // r9
  __int64 v121; // rcx
  const size_t *v122; // r8
  CFveApiBase *v123; // rdi
  __int64 v124; // rax
  const unsigned __int16 *v125; // rax
  const unsigned __int16 *v126; // rdx
  const unsigned __int16 *v127; // rax
  const unsigned __int16 *v128; // rdx
  __int64 v129; // rax
  const unsigned __int16 *v130; // rax
  const unsigned __int16 *v131; // rdx
  CFveApiBase *v132; // r13
  const unsigned __int16 *v133; // rax
  const unsigned __int16 *v134; // rdx
  unsigned int v135; // edx
  __int64 v136; // rax
  __int128 *v137; // rax
  __int64 v138; // rcx
  __int64 v139; // r8
  __int64 v140; // r9
  unsigned int pcbResult; // [rsp+20h] [rbp-A38h]
  unsigned int pcbResulta; // [rsp+20h] [rbp-A38h]
  unsigned int pcbResultb; // [rsp+20h] [rbp-A38h]
  unsigned int pcbResultc; // [rsp+20h] [rbp-A38h]
  unsigned int pcbResultd; // [rsp+20h] [rbp-A38h]
  unsigned int pcbResulte; // [rsp+20h] [rbp-A38h]
  const char *dwFlags; // [rsp+28h] [rbp-A30h]
  char v149; // [rsp+80h] [rbp-9D8h]
  unsigned int v150; // [rsp+88h] [rbp-9D0h]
  char v151; // [rsp+98h] [rbp-9C0h]
  char v152; // [rsp+99h] [rbp-9BFh]
  char v153; // [rsp+9Ah] [rbp-9BEh]
  char v154; // [rsp+9Bh] [rbp-9BDh]
  char v155; // [rsp+9Ch] [rbp-9BCh]
  bool v156; // [rsp+9Dh] [rbp-9BBh] BYREF
  char v157; // [rsp+9Eh] [rbp-9BAh]
  bool v158; // [rsp+9Fh] [rbp-9B9h] BYREF
  __int16 v159; // [rsp+A0h] [rbp-9B8h]
  int v160; // [rsp+A4h] [rbp-9B4h]
  bool v161[4]; // [rsp+A8h] [rbp-9B0h] BYREF
  unsigned __int16 v162[2]; // [rsp+ACh] [rbp-9ACh] BYREF
  bool v163; // [rsp+B0h] [rbp-9A8h] BYREF
  bool v164; // [rsp+B1h] [rbp-9A7h] BYREF
  char v165; // [rsp+B2h] [rbp-9A6h] BYREF
  bool v166; // [rsp+B3h] [rbp-9A5h] BYREF
  unsigned int v167; // [rsp+B4h] [rbp-9A4h]
  unsigned __int64 v168; // [rsp+B8h] [rbp-9A0h] BYREF
  bool v169; // [rsp+C0h] [rbp-998h] BYREF
  __int16 v170; // [rsp+C4h] [rbp-994h]
  unsigned __int8 v171; // [rsp+C8h] [rbp-990h]
  bool v172; // [rsp+C9h] [rbp-98Fh]
  enum _FIRMWARE_TYPE v173[2]; // [rsp+D0h] [rbp-988h] BYREF
  char v174; // [rsp+D8h] [rbp-980h]
  char v175; // [rsp+D9h] [rbp-97Fh]
  __int16 v176; // [rsp+DAh] [rbp-97Eh] BYREF
  __int16 v177; // [rsp+DCh] [rbp-97Ch] BYREF
  struct _FVE_DATUM_KEY *v178; // [rsp+E0h] [rbp-978h] BYREF
  CFveTpm *v179; // [rsp+E8h] [rbp-970h] BYREF
  int v180; // [rsp+F0h] [rbp-968h] BYREF
  int v181; // [rsp+F4h] [rbp-964h]
  unsigned __int16 v182[2]; // [rsp+F8h] [rbp-960h] BYREF
  unsigned __int16 v183; // [rsp+FCh] [rbp-95Ch] BYREF
  unsigned __int16 v184[2]; // [rsp+100h] [rbp-958h] BYREF
  unsigned __int16 v185[6]; // [rsp+104h] [rbp-954h] BYREF
  struct _GUID v186; // [rsp+110h] [rbp-948h] BYREF
  __int64 v187; // [rsp+120h] [rbp-938h]
  unsigned int v188; // [rsp+130h] [rbp-928h] BYREF
  int v189; // [rsp+134h] [rbp-924h]
  struct _FVE_DATUM_KEY *v190; // [rsp+138h] [rbp-920h] BYREF
  struct _FVE_DATUM_PUBLIC_KEY_INFO *v191; // [rsp+140h] [rbp-918h] BYREF
  char v192; // [rsp+148h] [rbp-910h]
  char v193; // [rsp+149h] [rbp-90Fh]
  unsigned __int8 v194; // [rsp+14Ah] [rbp-90Eh]
  char v195; // [rsp+14Bh] [rbp-90Dh]
  char v196; // [rsp+14Ch] [rbp-90Ch]
  char v197; // [rsp+14Dh] [rbp-90Bh]
  char v198; // [rsp+14Eh] [rbp-90Ah]
  CFveApiBase *v199; // [rsp+150h] [rbp-908h]
  int v200; // [rsp+158h] [rbp-900h]
  BOOL v201; // [rsp+15Ch] [rbp-8FCh]
  int v202; // [rsp+160h] [rbp-8F8h]
  int v203; // [rsp+164h] [rbp-8F4h]
  struct _FVE_AUTH_INFORMATION *v204; // [rsp+168h] [rbp-8F0h]
  unsigned int v205; // [rsp+170h] [rbp-8E8h]
  int v206; // [rsp+174h] [rbp-8E4h] BYREF
  int v207; // [rsp+178h] [rbp-8E0h]
  int v208; // [rsp+17Ch] [rbp-8DCh] BYREF
  int v209; // [rsp+180h] [rbp-8D8h] BYREF
  unsigned int v210; // [rsp+184h] [rbp-8D4h] BYREF
  unsigned int v211; // [rsp+188h] [rbp-8D0h] BYREF
  struct _GUID *v212; // [rsp+190h] [rbp-8C8h] BYREF
  const wchar_t *v213; // [rsp+198h] [rbp-8C0h] BYREF
  unsigned int v214[2]; // [rsp+1A0h] [rbp-8B8h] BYREF
  struct _FVE_TPM_API_SURFACE *v215; // [rsp+1A8h] [rbp-8B0h]
  int v216; // [rsp+1B0h] [rbp-8A8h]
  int v217; // [rsp+1B4h] [rbp-8A4h]
  unsigned int v218; // [rsp+1B8h] [rbp-8A0h] BYREF
  unsigned int v219; // [rsp+1BCh] [rbp-89Ch] BYREF
  int v220; // [rsp+1C0h] [rbp-898h]
  int v221; // [rsp+1C4h] [rbp-894h] BYREF
  struct _FVE_DATUM_EXPORTED_PUBLIC_KEY *v222; // [rsp+1C8h] [rbp-890h] BYREF
  void *lpMem; // [rsp+1D0h] [rbp-888h] BYREF
  __int128 v224; // [rsp+1D8h] [rbp-880h]
  __int128 v225; // [rsp+1E8h] [rbp-870h]
  __int64 v226; // [rsp+208h] [rbp-850h] BYREF
  struct _FVE_DATUM_ASYM_ENC_BLOB *v227; // [rsp+210h] [rbp-848h] BYREF
  __int64 v228; // [rsp+218h] [rbp-840h] BYREF
  void *v229; // [rsp+220h] [rbp-838h]
  __int64 v230; // [rsp+228h] [rbp-830h] BYREF
  unsigned __int8 *v231; // [rsp+230h] [rbp-828h]
  struct _FVE_CERT_INFO *v232; // [rsp+238h] [rbp-820h] BYREF
  unsigned int *v233; // [rsp+240h] [rbp-818h]
  struct _FVE_TPM_STATE_EX_ *v234; // [rsp+248h] [rbp-810h]
  struct _FVE_DATUM_EXPORTED_PUBLIC_KEY *v235; // [rsp+250h] [rbp-808h] BYREF
  int v236; // [rsp+258h] [rbp-800h]
  const size_t *v237; // [rsp+260h] [rbp-7F8h] BYREF
  void *v238; // [rsp+268h] [rbp-7F0h]
  struct CFvePolicy *v239; // [rsp+270h] [rbp-7E8h] BYREF
  int v240; // [rsp+278h] [rbp-7E0h]
  int v241; // [rsp+27Ch] [rbp-7DCh]
  BOOL v242; // [rsp+280h] [rbp-7D8h]
  struct _FVE_TPM_STATE_EX_ *v243; // [rsp+288h] [rbp-7D0h]
  struct _GUID *v244; // [rsp+290h] [rbp-7C8h]
  __int128 v245; // [rsp+298h] [rbp-7C0h] BYREF
  __int64 v246; // [rsp+2A8h] [rbp-7B0h]
  void *v247; // [rsp+2B0h] [rbp-7A8h]
  struct _GUID *v248; // [rsp+2B8h] [rbp-7A0h]
  struct _FVE_DATUM_VMK_INFO *v249; // [rsp+2C0h] [rbp-798h] BYREF
  __int64 *v250; // [rsp+2C8h] [rbp-790h] BYREF
  __int64 *v251; // [rsp+2D0h] [rbp-788h]
  _QWORD *v252; // [rsp+2D8h] [rbp-780h] BYREF
  _QWORD *v253; // [rsp+2E0h] [rbp-778h]
  __int64 v254; // [rsp+2E8h] [rbp-770h] BYREF
  __int64 *v255; // [rsp+2F0h] [rbp-768h]
  _QWORD *v256; // [rsp+2F8h] [rbp-760h] BYREF
  _QWORD **v257; // [rsp+300h] [rbp-758h]
  __int64 v258; // [rsp+308h] [rbp-750h] BYREF
  __int64 *v259; // [rsp+310h] [rbp-748h]
  _QWORD *v260; // [rsp+318h] [rbp-740h] BYREF
  _QWORD **v261; // [rsp+320h] [rbp-738h]
  void *v262; // [rsp+328h] [rbp-730h]
  __int64 v263; // [rsp+330h] [rbp-728h]
  __int128 v264; // [rsp+338h] [rbp-720h] BYREF
  __int128 v265; // [rsp+348h] [rbp-710h]
  __int128 v266; // [rsp+358h] [rbp-700h]
  __int128 v267; // [rsp+368h] [rbp-6F0h] BYREF
  _OWORD v268[3]; // [rsp+378h] [rbp-6E0h] BYREF
  _OWORD v269[3]; // [rsp+3A8h] [rbp-6B0h] BYREF
  _OWORD v270[3]; // [rsp+3D8h] [rbp-680h] BYREF
  char v271[4]; // [rsp+408h] [rbp-650h] BYREF
  unsigned __int16 v272; // [rsp+40Ch] [rbp-64Ch]
  __int16 v273; // [rsp+410h] [rbp-648h] BYREF
  unsigned int v274; // [rsp+414h] [rbp-644h] BYREF
  unsigned int v275; // [rsp+418h] [rbp-640h] BYREF
  __int64 v276; // [rsp+420h] [rbp-638h] BYREF
  int v277; // [rsp+428h] [rbp-630h]
  int v278; // [rsp+430h] [rbp-628h] BYREF
  int v279; // [rsp+434h] [rbp-624h] BYREF
  int v280; // [rsp+438h] [rbp-620h] BYREF
  int v281; // [rsp+43Ch] [rbp-61Ch] BYREF
  struct _GUID v282; // [rsp+440h] [rbp-618h] BYREF
  unsigned int v283; // [rsp+450h] [rbp-608h] BYREF
  UCHAR pbOutput[4]; // [rsp+454h] [rbp-604h] BYREF
  __int128 v285; // [rsp+458h] [rbp-600h] BYREF
  unsigned int v286; // [rsp+468h] [rbp-5F0h] BYREF
  ULONG v287; // [rsp+46Ch] [rbp-5ECh] BYREF
  _OWORD v288[3]; // [rsp+470h] [rbp-5E8h] BYREF
  _OWORD v289[3]; // [rsp+4A0h] [rbp-5B8h] BYREF
  _OWORD v290[3]; // [rsp+4D0h] [rbp-588h] BYREF
  _QWORD v291[6]; // [rsp+500h] [rbp-558h] BYREF
  _QWORD v292[6]; // [rsp+530h] [rbp-528h] BYREF
  _QWORD v293[6]; // [rsp+560h] [rbp-4F8h] BYREF
  _QWORD v294[6]; // [rsp+590h] [rbp-4C8h] BYREF
  _QWORD v295[6]; // [rsp+5C0h] [rbp-498h] BYREF
  _QWORD v296[6]; // [rsp+5F0h] [rbp-468h] BYREF
  _OWORD v297[3]; // [rsp+620h] [rbp-438h] BYREF
  _QWORD v298[6]; // [rsp+650h] [rbp-408h] BYREF
  _OWORD v299[3]; // [rsp+680h] [rbp-3D8h] BYREF
  _OWORD v300[3]; // [rsp+6B0h] [rbp-3A8h] BYREF
  _QWORD v301[6]; // [rsp+6E0h] [rbp-378h] BYREF
  _OWORD v302[3]; // [rsp+710h] [rbp-348h] BYREF
  _QWORD v303[6]; // [rsp+740h] [rbp-318h] BYREF
  __int128 v304; // [rsp+770h] [rbp-2E8h] BYREF
  __int128 v305; // [rsp+780h] [rbp-2D8h]
  __int128 v306; // [rsp+790h] [rbp-2C8h] BYREF
  _BYTE v307[12]; // [rsp+7A0h] [rbp-2B8h] BYREF
  __int16 v308; // [rsp+7ACh] [rbp-2ACh]
  void *Src; // [rsp+9F0h] [rbp-68h] BYREF
  __int128 v310; // [rsp+9F8h] [rbp-60h] BYREF
  __int64 v311; // [rsp+A08h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+A58h] [rbp+0h]

  v244 = a3;
  v204 = a2;
  v8 = this;
  v199 = this;
  v213 = (const wchar_t *)this;
  v215 = a6;
  memset(v268, 0, 44);
  memset(v270, 0, 44);
  memset(v269, 0, 44);
  v310 = 0;
  v311 = 0;
  v286 = 0;
  v285 = 0;
  v245 = 0;
  Src = 0;
  v264 = 0;
  v265 = 0;
  v266 = 0;
  memset_0(v307, 0, 0x248u);
  v306 = 0;
  v188 = -1;
  v219 = 0;
  v282 = 0;
  v218 = -1;
  v267 = 0;
  v9 = L"NA";
  v175 = 0;
  v150 = 0;
  v205 = 0;
  v168 = 0;
  v226 = 0;
  v178 = 0;
  v190 = 0;
  v230 = 0;
  v228 = 0;
  v249 = 0;
  *(_QWORD *)v214 = 0;
  v152 = 0;
  v154 = 0;
  v151 = 0;
  v157 = 0;
  v163 = 0;
  v155 = 0;
  v172 = 0;
  v271[0] = 0;
  v227 = 0;
  v222 = 0;
  v235 = 0;
  v191 = 0;
  v10 = 0;
  v149 = 0;
  v169 = 0;
  v161[0] = 0;
  v156 = 0;
  v233 = 0;
  v212 = 0;
  v179 = 0;
  v181 = 0;
  v238 = 0;
  *(_DWORD *)pbOutput = 0;
  v287 = 0;
  v184[0] = 0;
  v185[0] = 0;
  v182[0] = 0;
  v229 = 0;
  v180 = 0;
  v221 = 0;
  v171 = 1;
  v183 = 0;
  v232 = 0;
  v231 = 0;
  v162[0] = 17;
  v280 = 0;
  v203 = 0;
  v201 = 0;
  v164 = 0;
  v202 = 0;
  v236 = 0;
  v207 = 0;
  v189 = 0;
  v170 = 0;
  v173[0] = FirmwareTypeMax;
  v283 = 0;
  v166 = 0;
  v160 = 0;
  v159 = 0;
  v153 = 0;
  v158 = 0;
  v274 = 1;
  v272 = 0;
  v262 = 0;
  v263 = 0;
  v275 = 0;
  v239 = 0;
  v304 = 0;
  v305 = 0;
  v234 = 0;
  lpMem = 0;
  v276 = 0;
  v277 = 0;
  v224 = 0;
  v225 = 0;
  NgscbGet_TEST_BooleanOverride(L"GenerateZRP", &v163);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids);
  if ( *((_DWORD *)a2 + 1) != 1 )
  {
    v9 = L"InvalidArgAuthVersion";
LABEL_6:
    FirmwareType = -2147024809;
    goto LABEL_7;
  }
  if ( *(_DWORD *)a2 != 56 )
  {
    v9 = L"InvalidArgStructSize";
    goto LABEL_6;
  }
  v15 = (*(__int64 (__fastcall **)(CFveApiBase *, char *))(*(_QWORD *)v8 + 136LL))(v8, v271);
  FirmwareType = v15;
  v16 = 0;
  if ( v15 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        25,
        WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids,
        (unsigned int)v15);
      v16 = 0;
    }
    v9 = L"ReadFipsSetting";
    goto LABEL_15;
  }
  v17 = *((_DWORD *)a2 + 2) & 0x3FE0000;
  v150 = v17;
  v205 = v17;
  if ( *((_DWORD *)a2 + 2) != 0x10000 )
  {
    FirmwareType = CFveApiBase::LicenseCheck(v8, (wchar_t *)L"SecureStartupFeature-Enabled-Premium");
    if ( FirmwareType != -2144272294 )
    {
LABEL_23:
      v16 = 0;
LABEL_24:
      if ( FirmwareType < 0 )
      {
        v9 = L"LicenseCheckFailure";
LABEL_42:
        v13 = v149;
        v14 = 0;
        goto LABEL_706;
      }
      goto LABEL_44;
    }
    if ( (*((_DWORD *)v8 + 27) & 0x10000001) != 0 )
    {
      if ( v17 != 0x20000 && v17 != 0x80000 )
        goto LABEL_22;
      goto LABEL_26;
    }
    if ( (*((_BYTE *)v8 + 108) & 0x10) != 0 )
    {
      if ( v17 == 0x40000 )
      {
LABEL_26:
        FirmwareType = CFveApiBase::LicenseCheck(v8, (wchar_t *)L"SecureStartupFeature-Enabled-DeviceEncryption");
LABEL_22:
        v10 = 0;
        goto LABEL_23;
      }
    }
    else
    {
      if ( ((v17 - 0x40000) & 0xFFFBFFFF) == 0 )
        FirmwareType = CFveApiBase::LicenseCheck(v8, (wchar_t *)L"SecureStartupFeature-Enabled-DeviceEncryption");
      if ( FirmwareType == -2144272294 && v17 == 0x40000 && (*((_DWORD *)v8 + 27) & 0x10000001) == 0 )
      {
        FirmwareType = CFveApiBase::ResolveVolumeMountName(v8);
        v16 = 0;
        if ( FirmwareType >= 0 )
        {
          FirmwareType = IsVolumeVirtual(*((const unsigned __int16 **)v8 + 49), &v166);
          v16 = 0;
          if ( FirmwareType >= 0 )
          {
            if ( !v166 )
            {
              FirmwareType = -2144272294;
              v9 = L"NoFeatureLicense";
              goto LABEL_42;
            }
            v10 = 0;
            goto LABEL_24;
          }
          v9 = L"IsVolumeVirtual";
        }
        else
        {
          v9 = L"ResolveVolumeMountName";
        }
LABEL_37:
        v13 = 0;
        v14 = 0;
        goto LABEL_706;
      }
    }
    v10 = 0;
    goto LABEL_23;
  }
LABEL_44:
  if ( v17 == 0x20000 && *((_DWORD *)a2 + 2) != 0x10000 )
  {
    FirmwareType = FveGetFirmwareType(v173);
    v16 = 0;
    if ( FirmwareType < 0 )
    {
      v9 = L"FveGetFirmwareType";
      goto LABEL_37;
    }
    if ( v173[0] == FirmwareTypeBios )
    {
      FirmwareType = TpmGetTpmVersion(&v283);
      v16 = 0;
      if ( FirmwareType < 0 )
      {
        v9 = L"TpmGetTpmVersion";
        goto LABEL_37;
      }
      if ( v283 == 2 )
      {
        FirmwareType = -2144272312;
        v9 = L"FirmwareTypeNotSupported";
        goto LABEL_15;
      }
    }
  }
  if ( !a4 )
  {
    FirmwareType = CFveApi::GpCheckOnAddAuthMethodInformation(v8, a2);
    v16 = 0;
    if ( FirmwareType < 0 )
    {
      v9 = L"GpCheckOnAddAuthMethodInformation";
      goto LABEL_15;
    }
  }
  FirmwareType = CFveApiBase::CheckInited(v8);
  if ( FirmwareType < 0 )
  {
    v9 = L"CheckInited";
    goto LABEL_15;
  }
  FirmwareType = CFveApiBase::EnsureWeHaveVmkAndFvek(v8);
  v16 = 0;
  if ( FirmwareType < 0 )
  {
    v9 = L"EnsureWeHaveVmkAndFvek";
    goto LABEL_15;
  }
  if ( (*(unsigned __int8 (__fastcall **)(CFveApiBase *))(*(_QWORD *)v8 + 56LL))(v8) )
  {
    FirmwareType = CFveApiBase::EnsureWeHaveAutoUnlockMasterKey(v8, &v166);
    v16 = 0;
    if ( FirmwareType < 0 )
    {
      v9 = L"EnsureWeHaveAutoUnlockMasterKey";
      goto LABEL_15;
    }
  }
  FirmwareType = CFveApi::SetDescription(v8, 0, 1);
  v16 = 0;
  if ( FirmwareType < 0 )
  {
    v9 = L"SetDescription";
    goto LABEL_15;
  }
  if ( (*((_BYTE *)a2 + 8) & 1) != 0 )
  {
    v9 = L"AuthFlagsIdentitySet";
    FirmwareType = -2147024809;
    goto LABEL_15;
  }
  if ( (*((_DWORD *)a2 + 2) & 0x10000) != 0 )
  {
    FirmwareType = CFveApi::GpCheckOnDisable(v8);
    v16 = 0;
    if ( FirmwareType < 0 )
    {
      v9 = L"GpCheckOnDisable";
      goto LABEL_15;
    }
    FirmwareType = 0;
    v10 = 1;
    v149 = 1;
  }
  if ( !v10 )
  {
    FirmwareType = CFveApi::CheckAuthMethodsSupported(
                     v8,
                     *((_DWORD *)a2 + 3),
                     *((struct _FVE_AUTH_ELEMENT ***)a2 + 2),
                     *((_DWORD *)a2 + 2));
    v16 = 0;
    if ( FirmwareType < 0 )
    {
      v9 = L"CheckAuthMethodsSupported";
      goto LABEL_15;
    }
  }
  v11 = 0;
  v167 = 0;
  v18 = *((_QWORD *)&v225 + 1);
  *(_QWORD *)v173 = *((_QWORD *)&v225 + 1);
  v19 = v204;
  while ( (unsigned int)v11 < *((_DWORD *)v19 + 3) )
  {
    v20 = *(_QWORD *)(*((_QWORD *)v19 + 2) + 8LL * (unsigned int)v11);
    if ( !v20 )
      goto LABEL_284;
    if ( *(_DWORD *)v20 < 0x10u )
    {
      v9 = L"InvalidArgAuthHeaderSize";
LABEL_79:
      FirmwareType = -2147024809;
      goto LABEL_80;
    }
    if ( *(_DWORD *)(v20 + 4) != *((_DWORD *)v19 + 1) )
    {
      v9 = L"InvalidArgStructVersion";
      goto LABEL_79;
    }
    v21 = *(_DWORD *)(v20 + 12);
    if ( v21 > 8 )
    {
      v59 = v21 - 9;
      if ( !v59 )
      {
        if ( !v149 )
        {
          v9 = L"InvalidArgCK";
          goto LABEL_191;
        }
        if ( (*(_BYTE *)(v20 + 8) & 1) != 0 )
        {
          if ( *(_DWORD *)v20 < 0x18u )
          {
            v9 = L"InvalidArgCKFullSize";
LABEL_191:
            FirmwareType = -2147024809;
LABEL_80:
            v17 = v150;
            goto LABEL_42;
          }
          v67 = *(_BYTE *)(v20 + 16);
          v171 = v67;
          v194 = v67;
          v275 = *(_DWORD *)(v20 + 20);
          if ( v67 && (*((_DWORD *)v8 + 27) & 0x10000001) == 0 && ((*((_BYTE *)v8 + 108) & 0x10) != 0 || v67 <= 0xFDu) )
          {
            v9 = L"CKNotOSVolume";
            FirmwareType = -2144272344;
            goto LABEL_80;
          }
        }
        goto LABEL_150;
      }
      v60 = v59 - 1;
      if ( !v60 )
      {
        if ( v191 || v178 )
        {
          v9 = L"InvalidArgDNG";
          goto LABEL_191;
        }
        if ( (*(_BYTE *)(v20 + 8) & 1) == 0 )
        {
          v9 = L"InvalidArgFlagsFull";
          goto LABEL_191;
        }
        if ( *(_DWORD *)v20 < 0x14u )
        {
          v9 = L"InvalidArgDNGMinSize";
          goto LABEL_191;
        }
        v66 = FveDatumKeyCreate(8194, 0, 32, &v178);
        FirmwareType = FromNtStatus(v66);
        v16 = 0;
        if ( FirmwareType < 0 )
        {
          v9 = L"DNGFveDatumKeyCreate";
          goto LABEL_15;
        }
        FirmwareType = CFveApiBase::CreateDpapiNgPublicKeyInfo(
                         v8,
                         v178,
                         (const struct _FVE_AUTH_DPAPI_NG *)(v20 + 16),
                         &v191);
        v16 = 0;
        if ( FirmwareType < 0 )
        {
          v9 = L"CreateDpapiNgPublicKeyInfo";
          goto LABEL_80;
        }
        goto LABEL_149;
      }
      if ( v60 - 2 < 2 )
      {
        if ( v155 || v153 )
        {
          FirmwareType = -2147024809;
          v9 = L"InvalidArgTPMStateInfo";
          v63 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_80;
          v64 = 26;
          v65 = 2147942487LL;
LABEL_261:
          WPP_SF_d(v63[2], v64, WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids, v65);
          goto LABEL_7;
        }
        FirmwareType = CFveApiBase::HasTpmSecureKey(v8, v161);
        v16 = 0;
        if ( FirmwareType < 0 )
        {
LABEL_213:
          v9 = L"HasTpmSecureKey";
          goto LABEL_15;
        }
        if ( v161[0] )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids);
            v16 = 0;
          }
          FirmwareType = -2144272335;
          v9 = L"ProtectorExists";
          goto LABEL_15;
        }
        FirmwareType = CFveApiBase::HasPassphraseKey(v8, &v156);
        v16 = 0;
        if ( FirmwareType < 0 )
        {
LABEL_163:
          v9 = L"HasPassphraseKey";
          goto LABEL_15;
        }
        if ( v156 )
        {
          FirmwareType = -2144272212;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              28,
              WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids,
              2150695084LL);
            v16 = 0;
          }
          v9 = L"NoTPMPP";
          goto LABEL_15;
        }
        if ( *(_DWORD *)(v20 + 12) == 12 )
        {
          v61 = *(_QWORD *)(v20 + 16);
          if ( !v61 )
          {
            FirmwareType = -2147024809;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                29,
                WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids,
                2147942487LL);
              v16 = 0;
            }
            v9 = L"InvalidArgTpmStateInfo";
            goto LABEL_15;
          }
          LODWORD(v304) = 720897;
          *((_QWORD *)&v304 + 1) = *(_QWORD *)v61;
          *((_QWORD *)&v305 + 1) = *(_QWORD *)(v61 + 16);
          LODWORD(v305) = *(_DWORD *)(v61 + 8);
          v62 = (struct _FVE_TPM_STATE_EX_ *)&v304;
        }
        else
        {
          v11 = 1;
          if ( *(_WORD *)(v20 + 16) != 1 )
          {
            FirmwareType = -2147024809;
            v9 = L"InvalidArgTpmStateInfo";
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
              goto LABEL_80;
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids);
            goto LABEL_7;
          }
          v62 = *(struct _FVE_TPM_STATE_EX_ **)(v20 + 24);
        }
        v243 = v62;
        v234 = v62;
        v153 = 1;
        v193 = 1;
        goto LABEL_149;
      }
    }
    else
    {
      if ( v21 == 8 )
      {
        if ( v168 )
        {
          v9 = L"InvalidArgPPUserInput";
          goto LABEL_191;
        }
        FirmwareType = CFveApiBase::HasPassphraseKey(v8, &v156);
        v16 = 0;
        if ( FirmwareType < 0 )
          goto LABEL_163;
        if ( v156 )
        {
          FirmwareType = -2144272335;
          v9 = L"PPExists";
          goto LABEL_15;
        }
        FirmwareType = CFveApiBase::HasTpmSecureKey(v8, v161);
        v16 = 0;
        if ( FirmwareType < 0 )
          goto LABEL_213;
        if ( v161[0] )
        {
          FirmwareType = -2144272213;
          v9 = L"NoPPWithTPM";
          goto LABEL_15;
        }
        if ( (*(_BYTE *)(v20 + 8) & 1) == 0 )
        {
          v9 = L"InvalidArgPPMustSpecified";
          goto LABEL_101;
        }
        if ( *(_DWORD *)v20 < 0x242u )
        {
          FirmwareType = -2147024809;
          v9 = L"InvalidArgFlagFullPPSize";
          goto LABEL_15;
        }
        v55 = FveDatumKeyCreate(4097, v20 + 530, 32, &v226);
        FirmwareType = FromNtStatus(v55);
        v16 = 0;
        if ( FirmwareType < 0 )
        {
          v9 = L"PPFveDatumKeyCreate";
          goto LABEL_15;
        }
        v56 = FveDatumKeyCreate(4098, 0, 16, &v230);
        FirmwareType = FromNtStatus(v56);
        v16 = 0;
        if ( FirmwareType < 0 )
        {
          v9 = L"PPSaltFveDatumKeyCreate";
          goto LABEL_15;
        }
        v57 = v230;
        v58 = FveDatumStretchKey(v230 + 12, v226, &v168);
        FirmwareType = FromNtStatus(v58);
        v16 = 0;
        if ( FirmwareType < 0 )
        {
          v9 = L"PPFveDatumStretchKey";
          goto LABEL_80;
        }
        *(_QWORD *)&v225 = v57;
        goto LABEL_149;
      }
      v22 = v21 - 1;
      if ( !v22 )
      {
        if ( v168 )
        {
          v9 = L"InvalidArgRp";
          goto LABEL_191;
        }
        if ( (*(_BYTE *)(v20 + 8) & 1) != 0 )
        {
          if ( *(_DWORD *)v20 < 0x20u )
          {
            v9 = L"InvalidArgFlagFullPwdSize";
            goto LABEL_191;
          }
          v52 = (__int128 *)(v20 + 16);
        }
        else
        {
          if ( v271[0] )
            v18 = 10000;
          *(_QWORD *)v173 = v18;
          *((_QWORD *)&v225 + 1) = v18;
          if ( v163 )
            v52 = &v245;
          else
            v52 = 0;
        }
        v53 = FveDatumKeyCreate(4096, v52, 16, &v168);
        FirmwareType = FromNtStatus(v53);
        v16 = 0;
        if ( FirmwareType < 0 )
        {
          v9 = L"DatumKeyCreate";
          goto LABEL_15;
        }
        if ( v271[0] || (*(_BYTE *)(v20 + 8) & 0x10) != 0 )
        {
          *(_WORD *)(v168 + 10) |= 0x40u;
          HIWORD(v54) = HIWORD(v160);
          LOWORD(v54) = v160 | 0x40;
          v160 = v54;
          v159 = v54;
        }
        goto LABEL_149;
      }
      v23 = v22 - 1;
      if ( !v23 )
      {
        if ( v168 )
        {
          v9 = L"UserInputInvalidArgPin";
          goto LABEL_191;
        }
        if ( (*(_BYTE *)(v20 + 8) & 1) == 0 )
        {
          v9 = L"InvalidArgPinMustSpecified";
          goto LABEL_191;
        }
        if ( *(_DWORD *)v20 < 0x30u )
        {
          v9 = L"InvalidArgFlagFullPinSize";
          goto LABEL_191;
        }
        v50 = FveDatumKeyCreate(8196, v20 + 16, 32, &v168);
        FirmwareType = FromNtStatus(v50);
        v51 = v168;
        if ( (*(_BYTE *)(v20 + 8) & 2) != 0 )
        {
          *(_WORD *)(v168 + 10) |= 4u;
          v172 = 1;
          v192 = 1;
          HIWORD(v42) = HIWORD(v160);
          LOWORD(v42) = v160 | 4;
          v160 = v42;
          v159 = v42;
        }
        else
        {
          v42 = v160;
          if ( (*(_BYTE *)(v20 + 8) & 8) != 0 )
          {
            *(_WORD *)(v168 + 10) |= 0x10u;
            LOWORD(v42) = v42 | 0x10;
            v160 = v42;
            v159 = v42;
          }
        }
        v16 = 0;
        if ( v271[0] || (*(_BYTE *)(v20 + 8) & 0x10) != 0 )
        {
          *(_WORD *)(v51 + 10) |= 0x40u;
          LOWORD(v42) = v42 | 0x40;
LABEL_148:
          v160 = v42;
          v159 = v42;
        }
LABEL_149:
        v11 = v167;
        v18 = *(_QWORD *)v173;
        goto LABEL_150;
      }
      v24 = v23 - 1;
      if ( !v24 )
      {
        if ( v155 || v153 )
        {
          v9 = L"InvalidArgTypeTPM";
          goto LABEL_191;
        }
        FirmwareType = CFveApiBase::HasPassphraseKey(v8, &v156);
        v16 = 0;
        if ( FirmwareType < 0 )
          goto LABEL_163;
        if ( v156 )
        {
          FirmwareType = -2144272212;
          v9 = L"NoTPMWithPP";
          goto LABEL_15;
        }
        v11 = 1;
        if ( (*(_BYTE *)(v20 + 8) & 1) != 0 )
        {
          if ( *(_DWORD *)v20 < 0x24u )
          {
            FirmwareType = -2147024809;
            v9 = L"InvalidArgTPMFullSize";
            goto LABEL_15;
          }
          v233 = (unsigned int *)(v20 + 16);
          v246 = v20 + 16;
          v47 = (struct _GUID *)(v20 + 20);
          v48 = *(_QWORD *)&v47->Data1 - NullGuid;
          if ( *(_QWORD *)&v47->Data1 == NullGuid )
            v48 = *(_QWORD *)v47->Data4;
          v49 = v212;
          if ( v48 )
            v49 = v47;
          v212 = v49;
          v248 = v49;
        }
        v155 = 1;
        v174 = 1;
        goto LABEL_149;
      }
      v25 = v24 - 1;
      if ( !v25 )
      {
        if ( v178 )
        {
          v9 = L"ExternalKey";
          goto LABEL_191;
        }
        if ( (*(_BYTE *)(v20 + 8) & 1) != 0 )
        {
          if ( *(_DWORD *)v20 < 0x30u )
          {
            v9 = L"InvalidExternalKeyFullSize";
            goto LABEL_191;
          }
          v44 = v20 + 16;
        }
        else
        {
          v44 = 0;
        }
        v45 = FveDatumKeyCreate(8194, v44, 32, &v178);
        FirmwareType = FromNtStatus(v45);
        *((_WORD *)v178 + 5) |= *(_WORD *)(v20 + 8) & 0xFF00;
        HIWORD(v46) = HIWORD(v160);
        LOWORD(v46) = *(_WORD *)(v20 + 8) & 0xFF00 | v160;
        v160 = v46;
        v159 = v46;
        v16 = 0;
        goto LABEL_149;
      }
      if ( v25 == 1 )
      {
        if ( v238 )
        {
          v9 = L"InvalidArgPK";
          goto LABEL_191;
        }
        v11 = 1;
        if ( (*(_BYTE *)(v20 + 8) & 1) == 0 || *(_DWORD *)v20 < 0x28u )
        {
          v9 = L"InvalidArgPKFullSize";
          goto LABEL_191;
        }
        v26 = *(void **)(v20 + 16);
        v238 = v26;
        v247 = v26;
        if ( !v26 )
        {
          v9 = L"InvalidArgPKNoHandle";
          goto LABEL_191;
        }
        Property = BCryptGetProperty(v26, L"PrimitiveType", pbOutput, 4u, &v287, 0);
        FirmwareType = FromNtStatus(Property);
        v16 = 0;
        if ( FirmwareType < 0 )
        {
          v9 = L"BCryptGetProperty";
          goto LABEL_15;
        }
        if ( (unsigned int)(*(_DWORD *)pbOutput - 3) > 1 )
        {
          v9 = L"PKBcryptInterface";
          goto LABEL_101;
        }
        if ( *(_DWORD *)pbOutput == 4 )
        {
          v28 = (char *)CFveApiBase::ZeroAlloc(0x24u);
          v229 = v28;
          v16 = 0;
          if ( !v28 )
          {
            v9 = L"PKProtectorTemplate";
LABEL_105:
            FirmwareType = -2147024882;
            goto LABEL_15;
          }
          *(_DWORD *)(v28 + 2) = 0;
          v29 = (struct _GUID *)(v28 + 8);
          FirmwareType = GenGuid((struct _GUID *)(v28 + 8));
          v16 = 0;
          if ( FirmwareType < 0 )
          {
            v9 = L"PKGenGuid";
            goto LABEL_15;
          }
          v186 = *v29;
          v30 = CFveApiBase::DeriveIntermediateKeySecretAgreement(v8, v26, &v186, &v190, &v222, &v235);
        }
        else
        {
          v30 = CFveApiBase::DeriveIntermediateKey((CFveApiBase *)*(unsigned int *)pbOutput, v26, &v190, &v227, &v222);
        }
        FirmwareType = v30;
        v16 = 0;
        if ( v30 < 0 )
        {
          v9 = L"PKDeriveIntermediateKey";
          goto LABEL_15;
        }
        if ( *(_QWORD *)(v20 + 32) && (v31 = (CFveApi *)*(unsigned int *)(v20 + 24), (_DWORD)v31) )
        {
          if ( (*(_BYTE *)(v20 + 8) & 0x20) != 0 )
          {
            FirmwareType = CFveApi::PrepareNetworkProtectorSessionKeys(
                             v31,
                             v190,
                             v26,
                             0,
                             (unsigned __int8 **)&Src,
                             &v183);
            v16 = 0;
            if ( FirmwareType < 0 )
            {
              v9 = L"PKnbpSessionKeys";
              goto LABEL_15;
            }
            v32 = *(_DWORD *)(v20 + 24);
            if ( v32 < 0x11
              || (v33 = *(_DWORD **)(v20 + 32), v32 != v33[1])
              || (IsValidCertInfo = FveCertIsValidCertInfo(*(_QWORD *)(v20 + 32)), v16 = 0, !IsValidCertInfo) )
            {
              v9 = L"PKFveCertIsValidCertInfo";
              goto LABEL_101;
            }
            if ( v33[2] != 8 )
            {
              v9 = L"PKExpectednbpCert";
LABEL_101:
              FirmwareType = -2147024809;
              goto LABEL_15;
            }
            if ( (int)ULongToUShort(v33[3], v185) < 0 )
            {
              v9 = L"PKULongToUShort";
LABEL_124:
              FirmwareType = -2147024362;
              goto LABEL_15;
            }
            v35 = v185[0];
            if ( (int)UShortAdd(v185[0], v162[0], v162) < 0 )
            {
              v9 = L"PKnbpUShortAddThumbPrintSize";
              goto LABEL_124;
            }
            v36 = v183;
            if ( (int)UShortAdd(v183, v162[0], v162) < 0 )
            {
              v9 = L"PKnbpUShortAddSessionKeySize";
              goto LABEL_124;
            }
            v37 = v162[0];
            v38 = (unsigned __int8 *)CFveApiBase::ZeroAlloc(v162[0]);
            v11 = (__int64)v38;
            v231 = v38;
            v16 = 0;
            if ( !v38 )
            {
              v9 = L"PKnbpInfoOutOfMemory";
              goto LABEL_105;
            }
            *((_DWORD *)v38 + 1) = 1;
            *(_DWORD *)v38 = v37;
            *((_DWORD *)v38 + 2) = v35;
            *((_DWORD *)v38 + 3) = v35 + v36;
            v39 = (char *)(v38 + 16);
            memcpy_0(v38 + 16, v33 + 4, v35);
            memcpy_0(&v39[v35], Src, v36);
            FirmwareType = FveCertCreateCertInfoFromBuffer(v231, v162[0], v33[2], &v232);
            v16 = 0;
            if ( FirmwareType < 0 )
            {
              v9 = L"PKnbpFveCertCreateCertInfoFromBuffer";
              goto LABEL_15;
            }
            if ( (int)ULongToUShort(*((_DWORD *)v232 + 1), v182) < 0 )
            {
              v9 = L"PKnbpULongToUShort";
              goto LABEL_124;
            }
            v41 = FveDatumPublicKeyInfoCreate(v182[0], v40, &v191);
            FirmwareType = FromNtStatus(v41);
            v16 = 0;
            if ( FirmwareType < 0 )
            {
              v9 = L"PKnbpFveDatumPublicKeyInfoCreate1";
              goto LABEL_15;
            }
            *((_WORD *)v190 + 5) |= 0x80u;
            HIWORD(v42) = HIWORD(v160);
            LOWORD(v42) = v160 | 0x80;
            v160 = v42;
            v159 = v42;
            v8 = v199;
LABEL_146:
            v19 = v204;
            if ( (*(_BYTE *)(v20 + 8) & 4) != 0 )
            {
              *((_WORD *)v190 + 5) |= 8u;
              LOWORD(v42) = v42 | 8;
              goto LABEL_148;
            }
            goto LABEL_149;
          }
          if ( (int)ULongToUShort((unsigned int)v31, v184) < 0 )
          {
            v9 = L"PKOverflow";
            goto LABEL_124;
          }
          v43 = FveDatumPublicKeyInfoCreate(v184[0], *(_QWORD *)(v20 + 32), &v191);
          FirmwareType = FromNtStatus(v43);
          v16 = 0;
          if ( FirmwareType < 0 )
          {
            v9 = L"PKnbpFveDatumPublicKeyInfoCreate2";
            goto LABEL_15;
          }
        }
        else if ( (*(_BYTE *)(v20 + 8) & 0x20) != 0 )
        {
          v9 = L"PKnbpFlagInvalid";
          goto LABEL_101;
        }
        v42 = v160;
        goto LABEL_146;
      }
    }
    v9 = L"InvalidArgAuthElement";
    FirmwareType = -2147024809;
LABEL_150:
    if ( FirmwareType < 0 )
    {
      v9 = L"CatchAll";
      goto LABEL_80;
    }
LABEL_284:
    v11 = (unsigned int)(v11 + 1);
    v167 = v11;
  }
  v11 = v150;
  if ( (v150 & 0x20000) != 0 )
  {
    v68 = v155;
    if ( !v155 )
      v68 = 1;
    v155 = v68;
    v174 = v68;
  }
  if ( (v150 & 0x40000) != 0 && !v178 )
  {
    v69 = FveDatumKeyCreate(8194, 0, 32, &v178);
    FirmwareType = FromNtStatus(v69);
    v16 = 0;
    if ( FirmwareType < 0 )
    {
      v9 = L"ExternalKeyFveDatumKeyCreate";
      goto LABEL_15;
    }
    v18 = *(_QWORD *)v173;
    v11 = v150;
  }
  v70 = v168;
  if ( (v11 & 0x80000) != 0 )
  {
    if ( v168 )
    {
      if ( *(_WORD *)(v168 + 8) != 4096 )
      {
        FirmwareType = -2147024809;
        v9 = L"InvalidArgWrongPasswordType";
        goto LABEL_15;
      }
    }
    else
    {
      if ( v271[0] )
        v18 = 10000;
      *(_QWORD *)v173 = v18;
      *((_QWORD *)&v225 + 1) = v18;
      if ( v163 )
        v71 = &v245;
      else
        v71 = 0;
      v72 = FveDatumKeyCreate(4096, v71, (unsigned int)(v168 + 16), &v168);
      FirmwareType = FromNtStatus(v72);
      v16 = 0;
      if ( FirmwareType < 0 )
      {
        v9 = L"TypePasswordFveDatumKeyCreate";
        goto LABEL_15;
      }
    }
    if ( (*((_BYTE *)v19 + 8) & 8) != 0 )
    {
      v73 = 1;
      v152 = 1;
      v195 = 1;
      v74 = (PVOID *)WPP_GLOBAL_Control;
      v11 = (__int64)&WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids);
        goto LABEL_310;
      }
    }
    else
    {
      v73 = 0;
LABEL_310:
      v11 = (__int64)&WPP_GLOBAL_Control;
      v74 = (PVOID *)WPP_GLOBAL_Control;
    }
    v75 = v204;
    if ( (*((_BYTE *)v204 + 8) & 0x10) != 0 )
    {
      v154 = 1;
      v196 = 1;
      if ( v74 != &WPP_GLOBAL_Control && (*((_BYTE *)v74 + 28) & 8) != 0 )
      {
        WPP_SF_(v74[2], 32, WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids);
        v74 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
    if ( (*((_BYTE *)v75 + 8) & 0x20) != 0 )
    {
      v151 = 1;
      v197 = 1;
      if ( v74 != &WPP_GLOBAL_Control && (*((_BYTE *)v74 + 28) & 8) != 0 )
      {
        WPP_SF_(v74[2], 33, WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids);
        v74 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
    if ( (*((_BYTE *)v75 + 8) & 0x40) != 0 )
    {
      v76 = 1;
      v157 = 1;
      v198 = 1;
      if ( v74 != &WPP_GLOBAL_Control && (*((_BYTE *)v74 + 28) & 8) != 0 )
      {
        WPP_SF_(v74[2], 34, WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids);
        v74 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
    else
    {
      v76 = v157;
    }
    v16 = 0;
    if ( v73 && v154 )
    {
      if ( v74 != &WPP_GLOBAL_Control && (*((_BYTE *)v74 + 28) & 2) != 0 )
      {
        WPP_SF_(v74[2], 35, WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids);
        v16 = 0;
      }
      v9 = L"InvalidArgAdConflictPolicy";
      goto LABEL_101;
    }
    if ( v151 && v76 )
    {
      if ( v74 != &WPP_GLOBAL_Control && (*((_BYTE *)v74 + 28) & 2) != 0 )
      {
        WPP_SF_(v74[2], 36, WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids);
        v16 = 0;
      }
      FirmwareType = -2147024809;
      v9 = L"InvalidArgBackupTypes";
      goto LABEL_15;
    }
    if ( v271[0] )
    {
      if ( v74 != &WPP_GLOBAL_Control && (*((_BYTE *)v74 + 28) & 8) != 0 )
        WPP_SF_(v74[2], 37, WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids);
      v70 = v168;
      *(_WORD *)(v168 + 10) |= 0x40u;
      HIWORD(v77) = HIWORD(v160);
      LOWORD(v77) = v160 | 0x40;
      v160 = v77;
      v159 = v77;
      v74 = (PVOID *)WPP_GLOBAL_Control;
    }
    else
    {
      v70 = v168;
      v77 = v160;
    }
    v11 = v150;
    v19 = v204;
  }
  else
  {
    v74 = (PVOID *)WPP_GLOBAL_Control;
    v77 = v160;
  }
  if ( (v11 & 0x100000) != 0 )
  {
    v16 = 0;
    if ( !v70 )
    {
      v9 = L"InvalidArgUserInputPIN";
      goto LABEL_101;
    }
    if ( *(_WORD *)(v70 + 8) != 8196 )
    {
      v9 = L"InvalidArgUserInputPIN256";
      goto LABEL_101;
    }
    if ( v271[0] )
    {
      if ( v74 != &WPP_GLOBAL_Control && (*((_BYTE *)v74 + 28) & 8) != 0 )
      {
        WPP_SF_(v74[2], 38, WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids);
        v70 = v168;
        v11 = v150;
      }
      *(_WORD *)(v70 + 10) |= 0x40u;
      LOWORD(v77) = v77 | 0x40;
      v160 = v77;
      v159 = v77;
    }
  }
  v16 = 0;
  if ( (v11 & 0x800000) != 0 )
  {
    if ( !v70 )
    {
      v9 = L"InvalidArgUserInputPP";
      goto LABEL_101;
    }
    if ( *(_WORD *)(v70 + 8) != 8199 )
    {
      v9 = L"InvalidArgKeyTypePP256";
      goto LABEL_101;
    }
  }
  if ( (v11 & 0x200000) != 0 )
  {
    if ( (v11 & 0x1000000) != 0 )
    {
      v9 = L"InvalidArgPKDPNG";
      goto LABEL_101;
    }
    if ( !v238 )
    {
      v9 = L"InvalidArgPK";
      goto LABEL_101;
    }
  }
  if ( (v11 & 0x1000000) != 0 && (!v178 || !v191) )
  {
    v9 = L"InvalidArgPKDPNGExternalInfo";
    goto LABEL_101;
  }
  v78 = (_WORD *)*((_QWORD *)v19 + 3);
  if ( v78 && *v78 )
  {
    v79 = FveDatumUnicodeCreate(v78, &v228);
    FirmwareType = FromNtStatus(v79);
    v16 = 0;
    if ( FirmwareType < 0 )
    {
      v9 = L"FveDatumUnicodeCreate";
      goto LABEL_15;
    }
    v70 = v168;
  }
  if ( !v70 && !v178 && !v190 && !v155 && !v153 )
  {
    if ( !v149 )
    {
      v9 = L"InvalidArgDisabled";
      goto LABEL_101;
    }
    goto LABEL_381;
  }
  if ( v149 )
  {
LABEL_381:
    FirmwareType = CFveApiBase::HasObfuscatedKey(v8, &v169, 0);
    v16 = 0;
    if ( FirmwareType < 0 )
    {
      v9 = L"HasObfuscatedKey";
      goto LABEL_15;
    }
    if ( v169 )
    {
      v9 = L"HasClearKey";
      FirmwareType = 1;
      goto LABEL_15;
    }
  }
  FirmwareType = CFveApiBase::SetFlagsBasedOnState(v8, &v286);
  v16 = 0;
  if ( FirmwareType < 0 )
  {
    v9 = L"SetFlagsBasedOnState";
    goto LABEL_15;
  }
  v80 = 0;
  v200 = 0;
  if ( v149 )
  {
    v80 = 1;
    v200 = 1;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BitLocker_TPM_Bound_ClearKey>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BitLocker_TPM_Bound_ClearKey>::GetImpl'::`2'::impl) )
    {
      FirmwareType = CFveApiBase::UseTpmBoundClearKey(v8, v275, &v179);
      v16 = 0;
      if ( FirmwareType < 0 )
      {
        v9 = L"UseTpmBoundClearKey";
        goto LABEL_15;
      }
      if ( v179 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids);
        v80 = 5;
        v200 = 5;
        v308 = 10;
        LODWORD(v264) = 1;
        *((_QWORD *)&v264 + 1) = v307;
        *(_QWORD *)&v265 = v179;
        DWORD2(v265) = 0;
        *(_QWORD *)&v266 = 0;
        WORD4(v266) = 0;
      }
    }
  }
  if ( !v155 && !v153 )
    goto LABEL_493;
  FirmwareType = CFveApiBase::FveQueryConsiderTpmProtectorVersionUpgradeImpl((enum _FVE_DATA_TPM_PROTECTOR_VERSION *)&v274);
  v16 = 0;
  if ( FirmwareType < 0 )
  {
    v9 = L"TPMVersionUpgrade";
    goto LABEL_15;
  }
  v81 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids, v274);
    v81 = (PVOID *)WPP_GLOBAL_Control;
    v16 = 0;
  }
  v80 |= 2u;
  v200 = v80;
  if ( !v153 )
  {
    v11 = (__int64)a5;
    if ( a5
      && *(_QWORD *)&a5->Data1 == *(_QWORD *)&FVE_GUID_PROV_SCENARIO_TMCORE.Data1
      && *(_QWORD *)a5->Data4 == *(_QWORD *)FVE_GUID_PROV_SCENARIO_TMCORE.Data4 )
    {
      if ( v81 != &WPP_GLOBAL_Control && (*((_BYTE *)v81 + 28) & 8) != 0 )
        WPP_SF_(v81[2], 47, WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids);
    }
    else if ( (*((_DWORD *)v8 + 27) & 0x10000001) == 0 )
    {
      v9 = L"ForeignVolume";
      FirmwareType = -2144272349;
      goto LABEL_15;
    }
    FirmwareType = EnsureNoBootableCdDvdInserted();
    v16 = 0;
    if ( FirmwareType < 0 )
    {
      v9 = L"EnsureNoBootableCdDvdInserted";
      goto LABEL_15;
    }
    FirmwareType = CFveApiBase::GetPolicy(v8, &v239);
    v16 = 0;
    if ( FirmwareType < 0 )
    {
      v9 = L"GetPolicy";
      goto LABEL_15;
    }
    FirmwareType = CFveApiBase::CreateTpmContext(v8, v239, &v179);
    v16 = 0;
    if ( FirmwareType < 0 )
    {
      v9 = L"CreateTpmContext";
      goto LABEL_15;
    }
    if ( v233 )
    {
      FirmwareType = CFveTpm::SetCallerSuppliedPcrBitmap(v179, *v233, 2);
      if ( FirmwareType < 0 )
      {
        v85 = 3843;
LABEL_456:
        wil::details::in1diag3::Log_HrMsg(
          retaddr,
          (void *)v85,
          (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib\\authinfo.cpp",
          (const char *)(unsigned int)FirmwareType,
          (int)"SetCallerSuppliedPcrBitmap",
          dwFlags);
        v9 = L"SetCallerSuppliedPcrBitmap";
        goto LABEL_7;
      }
      if ( v212 )
      {
        FirmwareType = CFveApi::SetDefaultPcrProfile(v8, v212, *v233);
        if ( FirmwareType < 0 )
        {
          v84 = 3852;
          goto LABEL_438;
        }
      }
    }
    else
    {
      FirmwareType = CFveApi::GetDefaultPcrProfile(v8, &v186, &v218);
      if ( FirmwareType < 0 )
      {
        wil::details::in1diag3::Log_HrMsg(
          retaddr,
          (void *)0xF1B,
          (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib\\authinfo.cpp",
          (const char *)(unsigned int)FirmwareType,
          (int)"GetDefaultPcrProfile",
          dwFlags);
        v9 = L"GetDefaultPcrProfile";
        goto LABEL_7;
      }
      v86 = v218;
      if ( v218 != v188 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids, v218);
        FirmwareType = CFveTpm::SetCallerSuppliedPcrBitmap(v179, v86, 9);
        if ( FirmwareType < 0 )
        {
          v85 = 3878;
          goto LABEL_456;
        }
      }
    }
    v87 = v215;
    if ( v215 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids);
      FirmwareType = CFveTpm::SetTpmApiSurface(v179, v87);
      if ( FirmwareType < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            50,
            WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids,
            (unsigned int)FirmwareType);
        wil::details::in1diag3::Log_HrMsg(
          retaddr,
          (void *)0xF36,
          (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib\\authinfo.cpp",
          (const char *)(unsigned int)FirmwareType,
          (int)"SetTpmApiSurface",
          dwFlags);
        v9 = L"SetTpmApiSurface";
        goto LABEL_7;
      }
    }
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::GetImpl'::`2'::impl)
      || (*((_DWORD *)v8 + 27) & 0x10000001) != 0 )
    {
      goto LABEL_487;
    }
    FirmwareType = CFveApiBase::GetPredictionInstanceMapping(v8, (unsigned __int16 **)&lpMem);
    if ( FirmwareType >= 0 )
    {
      if ( lpMem && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids, lpMem);
      goto LABEL_487;
    }
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0xF47,
      (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib\\authinfo.cpp",
      (const char *)(unsigned int)FirmwareType,
      (int)"GetPredictionInstanceMapping",
      dwFlags);
    v63 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v64 = 51;
      v65 = (unsigned int)FirmwareType;
      goto LABEL_261;
    }
LABEL_7:
    v13 = v149;
    v14 = 0;
LABEL_704:
    v16 = 0;
    goto LABEL_705;
  }
  if ( v215 )
  {
    if ( v81 != &WPP_GLOBAL_Control && (*((_BYTE *)v81 + 28) & 2) != 0 )
    {
      WPP_SF_(v81[2], 41, WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids);
      v16 = 0;
    }
    v9 = L"pFveTpmApiSurface_CVM";
    goto LABEL_101;
  }
  FirmwareType = NgscbCheckPredictedTpmProtector(&v158);
  v16 = 0;
  if ( FirmwareType < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        42,
        WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids,
        (unsigned int)FirmwareType);
      v16 = 0;
    }
    v9 = L"NgscbCheckPredictedTpmProtector";
    goto LABEL_15;
  }
  if ( !v158 )
  {
    FirmwareType = -2144272155;
    v9 = L"PredictedTpmNotSupported";
    v11 = (__int64)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_15;
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      43,
      WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids,
      *((unsigned int *)v8 + 27));
    goto LABEL_7;
  }
  FirmwareType = CFveApiBase::CreateTpmContextWithTpmStateInfo(v82, v234, &v179);
  v16 = 0;
  if ( FirmwareType < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        44,
        WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids,
        (unsigned int)FirmwareType);
      v16 = 0;
    }
    v9 = L"CreateTpmContextWithTpmStateInfo";
    goto LABEL_15;
  }
  if ( (*((_DWORD *)v8 + 27) & 0x4000) != 0 )
  {
    v158 = 0;
    FirmwareType = NgscbCheckPredictedTpmProtectorForOsVolume(&v158);
    v16 = 0;
    if ( FirmwareType < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          45,
          WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids,
          (unsigned int)FirmwareType);
        v16 = 0;
      }
      v9 = L"NgscbCheckPredictedTpmProtectorForOsVolume";
      goto LABEL_15;
    }
    if ( !v158 )
    {
      FirmwareType = -2144272155;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          46,
          WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids,
          *((unsigned int *)v8 + 27));
        v16 = 0;
      }
      v9 = L"TPMprotectorNotSupported";
      goto LABEL_15;
    }
  }
  FirmwareType = CFveTpm::GetPcrProfileFromTpmStateInfo(v179, &v188, (enum ePcrBitmapSource *)&v219);
  if ( FirmwareType < 0 )
  {
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0xEBF,
      (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib\\authinfo.cpp",
      (const char *)(unsigned int)FirmwareType,
      (int)"GetPcrProfileFromTpmStateInfo",
      dwFlags);
    v9 = L"GetPcrProfileFromTpmStateInfo";
    goto LABEL_7;
  }
  v215 = (struct _FVE_TPM_API_SURFACE *)0x4A2B872EA2232265LL;
  v216 = 1895151265;
  v217 = -92335236;
  v282.Data1 = -1574755739;
  *(_DWORD *)&v282.Data2 = 1244366638;
  *(_DWORD *)v282.Data4 = 1895151265;
  *(_DWORD *)&v282.Data4[4] = -92335236;
  FirmwareType = CFveApi::SetDefaultPcrProfile(v8, &v282, v188);
  if ( FirmwareType < 0 )
  {
    v84 = 3785;
LABEL_438:
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)v84,
      (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib\\authinfo.cpp",
      (const char *)(unsigned int)FirmwareType,
      (int)"SetDefaultPcrProfile",
      dwFlags);
    v9 = L"SetDefaultPcrProfile";
    goto LABEL_7;
  }
LABEL_487:
  *(_QWORD *)&v267 = v234;
  *((_QWORD *)&v267 + 1) = __PAIR64__(v219, v188);
  pcbResult = (unsigned int)v233;
  LOBYTE(v83) = v153;
  FirmwareType = CreateTpmProtectorBindingDigestSourceData(v179, v274, v83, &v267);
  v16 = 0;
  if ( FirmwareType < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        53,
        WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids,
        (unsigned int)FirmwareType);
      v16 = 0;
    }
    v9 = L"CreateTpmProtectorBindingDigestSourceData";
    goto LABEL_15;
  }
  LODWORD(v264) = v274;
  *((_QWORD *)&v264 + 1) = v262;
  *(_QWORD *)&v265 = v179;
  DWORD2(v265) = 1;
  *(_QWORD *)&v266 = *((_QWORD *)v8 + 146);
  WORD4(v266) = v272;
LABEL_493:
  if ( v178 )
  {
    *(_QWORD *)&v270[0] = v178;
    DWORD2(v270[0]) = 2;
    *(_QWORD *)&v310 = v270;
    v88 = 1;
    v181 = 1;
    v220 = 1;
  }
  else
  {
    v88 = v181;
  }
  if ( v168 )
  {
    v89 = *((_QWORD *)&v224 + 1);
    if ( *(_WORD *)(v168 + 8) != 8199 )
      v89 = v168;
    *((_QWORD *)&v224 + 1) = v89;
    *(_QWORD *)&v268[0] = v168;
    *(_QWORD *)((char *)v268 + 12) = v224;
    *(_OWORD *)((char *)&v268[1] + 4) = __PAIR128__(v225, v89);
    *(_QWORD *)((char *)&v268[2] + 4) = *(_QWORD *)v173;
    DWORD2(v268[0]) = 1;
    *((_QWORD *)&v310 + v88++) = v268;
    v181 = v88;
    v220 = v88;
  }
  if ( v190 )
  {
    *(_QWORD *)&v269[0] = v190;
    DWORD2(v269[0]) = 2;
    *((_QWORD *)&v310 + v88) = v269;
    v181 = v88 + 1;
    v220 = v88 + 1;
  }
  FirmwareType = CFveApiBase::PrepareNonce(v8);
  v16 = 0;
  if ( FirmwareType < 0 )
  {
    v9 = L"PrepareNonce";
    goto LABEL_15;
  }
  v90 = (unsigned int)CFveApiBase::GetAndUseNonce(v8);
  v92 = FveBuildVmkInfoEx(
          v90,
          v91,
          (_DWORD)v229,
          (unsigned int)&v310,
          v181,
          (__int64)&v275,
          v228,
          (__int64)v227,
          (__int64)v222,
          (__int64)v235,
          (__int64)v191,
          (__int64)&v264,
          v80,
          (__int64)&v249,
          (__int64)&v306);
  FirmwareType = FromNtStatus(v92);
  v16 = 0;
  if ( FirmwareType < 0 )
  {
    if ( FirmwareType == (unsigned int)FromNtStatus(-1071579052) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        pcbResult = DWORD2(v306);
        WPP_SF_II(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids, v306);
      }
      v16 = 0;
    }
    else
    {
      v16 = 0;
      if ( v179 && *((int *)v179 + 11) < 0 )
        FirmwareType = *((_DWORD *)v179 + 11);
    }
    v9 = L"FveBuildVmkInfo";
    goto LABEL_15;
  }
  if ( (*((_WORD *)v249 + 17) & 0xFF00) != 0x800 )
    goto LABEL_652;
  if ( (*((_DWORD *)v8 + 26) & 0x8000) != 0 || (*((_BYTE *)v8 + 104) & 2) != 0 && (*((_BYTE *)v8 + 108) & 4) == 0 )
  {
    if ( v152 )
    {
      FirmwareType = -2144272383;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids, 2150694913LL);
        v16 = 0;
      }
      v9 = L"ADEnforcedNotEncrypted";
    }
    else
    {
      if ( !v151 )
        goto LABEL_652;
      FirmwareType = -2144272383;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids, 2150694913LL);
        v16 = 0;
      }
      v9 = L"AADEnforcedNotEncrypted";
    }
    goto LABEL_15;
  }
  FirmwareType = CFveApiBase::CheckADRecoveryInfoBackupPolicy(v8, (struct _ADA_GP_OPTIONS *)&v276);
  v16 = 0;
  if ( FirmwareType < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        55,
        WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids,
        (unsigned int)FirmwareType);
      v16 = 0;
    }
    v9 = L"CheckADRecoveryInfoBackupPolicy";
    goto LABEL_15;
  }
  v94 = v157;
  if ( !(_DWORD)v276 )
  {
    v109 = (PVOID *)WPP_GLOBAL_Control;
    v11 = (__int64)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids);
      v109 = (PVOID *)WPP_GLOBAL_Control;
      v16 = 0;
      v11 = (__int64)&WPP_GLOBAL_Control;
    }
    if ( v152 )
    {
      FirmwareType = -2144272171;
      if ( v109 != &WPP_GLOBAL_Control && (*((_BYTE *)v109 + 28) & 2) != 0 )
      {
        WPP_SF_d(v109[2], 74, WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids, 2150695125LL);
        v16 = 0;
      }
      v9 = L"ADForcedADBackupNotEnabled";
    }
    else
    {
      if ( !v151 )
        goto LABEL_652;
      FirmwareType = -2144272171;
      if ( v109 != &WPP_GLOBAL_Control && (*((_BYTE *)v109 + 28) & 2) != 0 )
      {
        WPP_SF_d(v109[2], 75, WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids, 2150695125LL);
        v16 = 0;
      }
      v9 = L"AADForcedADBackupNotEnabled";
    }
    goto LABEL_15;
  }
  if ( v277 && v154 && v157 )
  {
    FirmwareType = -2147024809;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids, 2147942487LL);
      v16 = 0;
    }
    v9 = L"BadProtectorFlag";
    goto LABEL_15;
  }
  if ( v154 )
  {
    v96 = v152;
    goto LABEL_572;
  }
  DomainInfo = FveDomain::GetDomainInfo(&v164, (struct _GUID *)v11);
  v202 = DomainInfo;
  v240 = DomainInfo;
  v16 = 0;
  if ( DomainInfo >= 0 )
  {
    if ( v164 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids);
      v97 = AdaRevertAndCheckIsSchemaExtInstalled(&v280);
      v203 = v97;
      v16 = 0;
      if ( v97 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            59,
            WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids,
            (unsigned int)v97);
          v97 = v203;
          v16 = 0;
        }
        v96 = v152;
        if ( !v152 )
        {
          if ( !v94 )
            goto LABEL_573;
          if ( !v277 )
            goto LABEL_572;
        }
        FirmwareType = v97;
        v9 = L"AdaRevertAndCheckIsSchemaExtInstalled";
        goto LABEL_15;
      }
      v96 = v152;
      if ( v280 )
        goto LABEL_572;
      if ( !v152 )
      {
        if ( !v94 )
          goto LABEL_573;
        if ( !v277 )
          goto LABEL_572;
      }
      FirmwareType = -2144272374;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids, 2150694922LL);
        v16 = 0;
      }
      v9 = L"ADSchemaNotInstalled";
    }
    else
    {
      v98 = (PVOID *)WPP_GLOBAL_Control;
      v11 = (__int64)&WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids);
        v98 = (PVOID *)WPP_GLOBAL_Control;
        v16 = 0;
        v11 = (__int64)&WPP_GLOBAL_Control;
      }
      v96 = v152;
      if ( !v152 )
      {
        if ( !v94 )
          goto LABEL_573;
        if ( !v277 )
          goto LABEL_572;
      }
      FirmwareType = -2145647536;
      if ( v98 != &WPP_GLOBAL_Control && (*((_BYTE *)v98 + 28) & 2) != 0 )
      {
        WPP_SF_d(v98[2], 62, WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids, 2149319760LL);
        v16 = 0;
      }
      v9 = L"NotADJoined";
    }
LABEL_15:
    v13 = v149;
    goto LABEL_16;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      57,
      WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids,
      (unsigned int)DomainInfo);
    DomainInfo = v202;
    v16 = 0;
  }
  v96 = v152;
  if ( v152 )
    goto LABEL_540;
  if ( v94 )
  {
    if ( v277 )
    {
LABEL_540:
      FirmwareType = DomainInfo;
      v9 = L"CheckIsMachineDomainJoined";
      goto LABEL_15;
    }
LABEL_572:
    if ( v94 )
    {
      v99 = v236;
      goto LABEL_598;
    }
  }
LABEL_573:
  v99 = FveDomain::CheckIsDeviceAzureJoined(0, 0);
  v241 = v99;
  v16 = 0;
  v100 = v99 == 0;
  v201 = v100;
  v242 = v100;
  if ( v99 >= 0 )
  {
    v101 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v101 = (PVOID *)WPP_GLOBAL_Control;
    v11 = (__int64)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        63,
        WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids,
        (unsigned int)v99);
      v101 = (PVOID *)WPP_GLOBAL_Control;
      v100 = v201;
      v16 = 0;
    }
    if ( v151 || v154 && v277 )
    {
      FirmwareType = v99;
      v9 = L"CheckIsDeviceAzureJoined";
      goto LABEL_15;
    }
  }
  if ( v99 < 0 )
  {
LABEL_598:
    v102 = v151;
  }
  else
  {
    if ( v100 )
    {
      if ( v101 != &WPP_GLOBAL_Control && (*((_BYTE *)v101 + 28) & 8) != 0 )
        WPP_SF_(v101[2], 64, WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids);
      goto LABEL_598;
    }
    v11 = (__int64)&WPP_GLOBAL_Control;
    if ( v101 != &WPP_GLOBAL_Control && (*((_BYTE *)v101 + 28) & 8) != 0 )
    {
      WPP_SF_(v101[2], 65, WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids);
      v101 = (PVOID *)WPP_GLOBAL_Control;
      v16 = 0;
      v11 = (__int64)&WPP_GLOBAL_Control;
    }
    v102 = v151;
    if ( v151 || v154 && v277 )
    {
      FirmwareType = -2145647536;
      if ( v101 != &WPP_GLOBAL_Control && (*((_BYTE *)v101 + 28) & 2) != 0 )
      {
        WPP_SF_d(v101[2], 66, WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids, 2149319760LL);
        v16 = 0;
      }
      v9 = L"NotAADJoined";
      goto LABEL_15;
    }
  }
  if ( v102 || !v94 && v99 >= 0 && v201 )
  {
    v170 = 1;
    FirmwareType = CFveApi::AttemptAADBackup(v8, v249, v93, 0, pcbResult);
    v16 = 0;
    if ( FirmwareType < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          67,
          WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids,
          (unsigned int)FirmwareType);
        v16 = 0;
      }
      v189 = 0;
      v170 = 0;
      v103 = v151;
      if ( v151 || v277 )
      {
        v9 = L"AttemptAADBackup";
        goto LABEL_15;
      }
      goto LABEL_615;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids);
    v189 = 2;
    v170 = 2;
  }
  v103 = v151;
LABEL_615:
  if ( v96 || !v154 && v202 >= 0 && v164 && v203 >= 0 && v280 )
  {
    FirmwareType = (*(__int64 (__fastcall **)(CFveApiBase *, struct _FVE_DATUM_VMK_INFO *, __int64 *))(*(_QWORD *)v8 + 312LL))(
                     v8,
                     v249,
                     &v276);
    v16 = 0;
    if ( FirmwareType >= 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids);
      v207 = 2;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          69,
          WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids,
          (unsigned int)FirmwareType);
        v16 = 0;
      }
      if ( v96 || (LOWORD(v207) = 0, v277) )
      {
        v9 = L"AttemptADBackup";
        goto LABEL_15;
      }
    }
  }
  if ( (_WORD)v189 )
  {
    v104 = FveSetRecoveryPasswordBackupInfoInVmkInfo((_DWORD)v249, 4, (unsigned __int16)v189, 0, (__int64)v214);
    FirmwareType = v104;
    v16 = 0;
    if ( v104 >= 0 )
    {
      v105 = *(struct _FVE_DATUM_VMK_INFO **)v214;
      if ( *(_QWORD *)v214 )
      {
        FveDatumFree(v249);
        v249 = v105;
        *(_QWORD *)v214 = 0;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          71,
          WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids,
          (unsigned int)v104);
        v16 = 0;
      }
      if ( v103 || v277 )
      {
        v9 = L"AADFveSetRecoveryPasswordBackupInfoInVmkInfo";
        goto LABEL_15;
      }
    }
  }
  if ( (_WORD)v207 )
  {
    v106 = FveSetRecoveryPasswordBackupInfoInVmkInfo((_DWORD)v249, 1, (unsigned __int16)v207, 0, (__int64)v214);
    FirmwareType = v106;
    v16 = 0;
    if ( v106 >= 0 )
    {
      v107 = *(struct _FVE_DATUM_VMK_INFO **)v214;
      if ( *(_QWORD *)v214 )
      {
        FveDatumFree(v249);
        v249 = v107;
        *(_QWORD *)v214 = 0;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          72,
          WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids,
          (unsigned int)v106);
        v16 = 0;
      }
      if ( v96 || v277 )
      {
        v9 = L"ADFveSetRecoveryPasswordBackupInfoInVmkInfo";
        goto LABEL_15;
      }
    }
  }
LABEL_652:
  v13 = v149;
  if ( v149 )
  {
    if ( (*((_BYTE *)v8 + 104) & 2) != 0 )
    {
      Count = FveDatasetGetCount(*((_QWORD *)v8 + 146), 2, 8, &v221);
      FirmwareType = FromNtStatus(Count);
      v16 = 0;
      if ( FirmwareType < 0 )
      {
        v9 = L"FveDatasetGetCount";
        goto LABEL_16;
      }
      if ( !v221 )
        *((_WORD *)v249 + 3) |= 2u;
    }
    v110 = v171;
    if ( v171 )
    {
      if ( (*((_DWORD *)v8 + 27) & 0x10000001) != 0 && (*((_WORD *)v249 + 3) & 2) == 0 )
      {
        *((_WORD *)v249 + 3) = (unsigned __int8)*((_WORD *)v249 + 3);
        *((_WORD *)v249 + 3) |= v110 << 8;
        *((_WORD *)v249 + 3) |= 4u;
      }
      if ( (*((_DWORD *)v8 + 27) & 0x10000011) == 0 )
      {
        if ( (_BYTE)v110 == 0xFF )
        {
          *((_WORD *)v249 + 3) |= 8u;
        }
        else if ( (_BYTE)v110 == 0xFE )
        {
          *((_WORD *)v249 + 3) = (unsigned __int8)*((_WORD *)v249 + 3);
          *((_WORD *)v249 + 3) |= 0x100u;
          *((_WORD *)v249 + 3) |= 4u;
          *((_WORD *)v249 + 3) |= 0x10u;
        }
      }
    }
  }
  appended = FveDatasetAppendDatum(*((_QWORD *)v8 + 146), v249, 2);
  FirmwareType = FromNtStatus(appended);
  v16 = 0;
  if ( FirmwareType < 0 )
  {
    v9 = L"FveDatasetAppendDatum";
    goto LABEL_16;
  }
  if ( !v155 && !v153 || (FirmwareType = CFveApi::KeyManagement(v8, v153 != 0 ? 128 : 8, 0), v16 = 0, FirmwareType >= 0) )
  {
    v14 = 1;
    FirmwareType = (*(__int64 (__fastcall **)(CFveApiBase *))(*(_QWORD *)v8 + 256LL))(v8);
    v16 = 0;
    if ( FirmwareType < 0 )
    {
      v9 = L"SetPagefileFlagIfOsVolume";
      goto LABEL_705;
    }
    if ( v244 )
      *v244 = *(struct _GUID *)((char *)v249 + 8);
    CFveApi::SqmOnProtectorAdd(v8, v204, v172);
    goto LABEL_704;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      78,
      WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids,
      v153 != 0 ? 128 : 8,
      FirmwareType);
    v16 = 0;
  }
  v9 = L"TPMKeyManagement";
LABEL_16:
  v14 = 0;
LABEL_705:
  v17 = v150;
LABEL_706:
  if ( !v14 )
    goto LABEL_728;
  if ( v13 )
  {
    v250 = v16;
    v251 = v16;
    *(_QWORD *)&v186.Data1 = v16;
    *(_QWORD *)v186.Data4 = v16;
    v187 = (__int64)v16;
    v112 = v199;
    v113 = *((_QWORD *)v199 + 146);
    v291[2] = L"IdentityGuid";
    v291[3] = L"GUID";
    v291[4] = v113 + 16;
    v291[5] = 16;
    v291[0] = &v252;
    v291[1] = &v252;
    v252 = v291;
    v253 = v291;
    memset(v297, 0, sizeof(v297));
    LoggingVolumePath = CFveApiBase::GetLoggingVolumePath(v199);
    FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)v297, v115, L"VolumePath", LoggingVolumePath, pcbResult);
    if ( (_QWORD **)*v253 == &v252 )
    {
      *(_QWORD *)&v297[0] = &v252;
      *((_QWORD *)&v297[0] + 1) = v253;
      *v253 = v297;
      v253 = v297;
      memset(v288, 0, sizeof(v288));
      LoggingVolumeDriveLetter = CFveApiBase::GetLoggingVolumeDriveLetter(v112);
      FveApiEventLogDeclareWSTRING(
        (struct _FVEAPI_EVENT_DATA *)v288,
        v117,
        L"VolumeDriveLetter",
        LoggingVolumeDriveLetter,
        pcbResulta);
      if ( (_QWORD **)*v253 == &v252 )
      {
        *(_QWORD *)&v288[0] = &v252;
        *((_QWORD *)&v288[0] + 1) = v253;
        *v253 = v288;
        v273 = v275;
        v298[2] = L"ClearKeyScenario";
        v298[3] = L"USHORT";
        v298[4] = &v273;
        v298[5] = 2;
        if ( *(_QWORD ***)&v288[0] == &v252 )
        {
          v298[0] = &v252;
          v298[1] = v288;
          *(_QWORD *)&v288[0] = v298;
          v253 = v298;
          memset(v299, 0, sizeof(v299));
          LoggingServiceName = CFveApiBase::GetLoggingServiceName(v112);
          FveApiEventLogDeclareWSTRING(
            (struct _FVEAPI_EVENT_DATA *)v299,
            v119,
            L"ServiceName",
            LoggingServiceName,
            pcbResultb);
          if ( (_QWORD **)*v253 == &v252 )
          {
            *(_QWORD *)&v299[0] = &v252;
            *((_QWORD *)&v299[0] + 1) = v253;
            *v253 = v299;
            v253 = v299;
            v251 = FVEAPI_OP_PROTECTION_DISABLE;
            FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)&v186, (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v250);
            FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v186);
            v120 = 0;
            if ( *((_WORD *)v112 + 203)
              && (unsigned int)dword_1801724E0 > 5
              && (unsigned __int8)tlgKeywordOn(&dword_1801724E0, 0x800000000000LL) )
            {
              v237 = v122;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
                v121,
                (int)byte_18015F0FB,
                (__int64)v122,
                v120,
                &v237);
              goto LABEL_721;
            }
            goto LABEL_722;
          }
        }
      }
    }
LABEL_727:
    __fastfail(3u);
  }
  CFveApiBase::FlagsToProtectorType(v17, (enum _FVE_PROTECTOR_TYPE *)&v180);
  v258 = 0;
  v259 = 0;
  *(_QWORD *)&v186.Data1 = 0;
  *(_QWORD *)v186.Data4 = 0;
  v187 = 0;
  v123 = v199;
  v124 = *((_QWORD *)v199 + 146);
  v292[2] = L"IdentityGuid";
  v292[3] = L"GUID";
  v292[4] = v124 + 16;
  v292[5] = 16;
  v292[0] = &v260;
  v292[1] = &v260;
  v260 = v292;
  v261 = (_QWORD **)v292;
  memset(v300, 0, sizeof(v300));
  v125 = CFveApiBase::GetLoggingVolumePath(v199);
  FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)v300, v126, L"VolumePath", v125, pcbResult);
  if ( *v261 != &v260 )
    goto LABEL_727;
  *(_QWORD *)&v300[0] = &v260;
  *((_QWORD *)&v300[0] + 1) = v261;
  *v261 = v300;
  v261 = (_QWORD **)v300;
  memset(v289, 0, sizeof(v289));
  v127 = CFveApiBase::GetLoggingVolumeDriveLetter(v123);
  FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)v289, v128, L"VolumeDriveLetter", v127, pcbResultd);
  if ( *v261 != &v260 )
    goto LABEL_727;
  *(_QWORD *)&v289[0] = &v260;
  *((_QWORD *)&v289[0] + 1) = v261;
  *v261 = v289;
  v301[2] = L"ProtectorGUID";
  v301[3] = L"GUID";
  v301[4] = (char *)v249 + 8;
  v301[5] = 16;
  if ( *(_QWORD ***)&v289[0] != &v260 )
    goto LABEL_727;
  v301[1] = v289;
  *(_QWORD *)&v289[0] = v301;
  v281 = v180;
  v293[2] = L"ProtectorType";
  v293[3] = L"ULONG";
  v293[4] = &v281;
  v293[5] = 4;
  v293[1] = v301;
  v301[0] = v293;
  v279 = 1;
  v294[2] = L"DatumDatasetVersion";
  v294[3] = L"INT32";
  v294[4] = &v279;
  v294[5] = 4;
  v294[0] = &v260;
  v294[1] = v293;
  v293[0] = v294;
  v261 = (_QWORD **)v294;
  v259 = FVEAPI_OP_PROTECTOR_CREATED;
  FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)&v186, (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v258);
  FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v186);
LABEL_721:
  v120 = 0;
LABEL_722:
  if ( (v160 & 0x40) != 0 )
  {
    v254 = v120;
    v255 = (__int64 *)v120;
    *(_QWORD *)&v186.Data1 = v120;
    *(_QWORD *)v186.Data4 = v120;
    v187 = v120;
    v129 = *((_QWORD *)v199 + 146);
    v295[2] = L"IdentityGuid";
    v295[3] = L"GUID";
    v295[4] = v129 + 16;
    v295[5] = 16;
    v295[0] = &v256;
    v295[1] = &v256;
    v256 = v295;
    v257 = (_QWORD **)v295;
    memset(v302, 0, sizeof(v302));
    v130 = CFveApiBase::GetLoggingVolumePath(v199);
    FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)v302, v131, L"VolumePath", v130, pcbResultc);
    if ( *v257 != &v256 )
      goto LABEL_727;
    *(_QWORD *)&v302[0] = &v256;
    *((_QWORD *)&v302[0] + 1) = v257;
    *v257 = v302;
    v257 = (_QWORD **)v302;
    memset(v290, 0, sizeof(v290));
    v132 = v199;
    v133 = CFveApiBase::GetLoggingVolumeDriveLetter(v199);
    FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)v290, v134, L"VolumeDriveLetter", v133, pcbResulte);
    if ( *v257 != &v256 )
      goto LABEL_727;
    *(_QWORD *)&v290[0] = &v256;
    *((_QWORD *)&v290[0] + 1) = v257;
    *v257 = v290;
    v303[2] = L"ProtectorGUID";
    v303[3] = L"GUID";
    v303[4] = (char *)v249 + 8;
    v303[5] = 16;
    if ( *(_QWORD ***)&v290[0] != &v256 )
      goto LABEL_727;
    v303[1] = v290;
    *(_QWORD *)&v290[0] = v303;
    v278 = v180;
    v296[2] = L"ProtectorType";
    v296[3] = L"ULONG";
    v296[4] = &v278;
    v296[5] = 4;
    v296[0] = &v256;
    v296[1] = v303;
    v303[0] = v296;
    v257 = (_QWORD **)v296;
    v255 = FVEAPI_OP_PBKDF2_PROTECTOR_CREATED;
    FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)&v186, (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v254);
    FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v186);
  }
  else
  {
LABEL_728:
    v132 = v199;
  }
  LOBYTE(v11) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADRecoveryPasswordDeletion>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_AADRecoveryPasswordDeletion>::GetImpl'::`2'::impl,
    v11);
  v285 = 0;
  v136 = *((_QWORD *)v132 + 146);
  if ( v136 )
    v137 = (__int128 *)(v136 + 16);
  else
    v137 = &v285;
  v285 = *v137;
  if ( (unsigned int)dword_1801724E0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1801724E0, 0x400000000000LL) )
  {
    v206 = 1;
    v211 = v274;
    v208 = FirmwareType;
    v213 = v9;
    v165 = 0;
    v176 = v189;
    v209 = *((_DWORD *)v132 + 26);
    v177 = v160;
    v210 = v150;
    v212 = (struct _GUID *)&v285;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v138,
      (int)byte_18015F021,
      v139,
      v140,
      (__int64 *)&v212,
      (__int64)&v210,
      (__int64)&v177,
      (__int64)&v209,
      (__int64)&v176,
      (__int64)&v165,
      (const size_t **)&v213,
      (__int64)&v208,
      (__int64)&v211,
      (__int64)&v206);
  }
  if ( v168 )
    FveDatumFree(v168);
  if ( v226 )
    FveDatumFree(v226);
  if ( v178 )
    FveDatumFree(v178);
  if ( v190 )
    FveDatumFree(v190);
  if ( v227 )
    FveDatumFree(v227);
  if ( v222 )
    FveDatumFree(v222);
  if ( v235 )
    FveDatumFree(v235);
  if ( v191 )
    FveDatumFree(v191);
  if ( v228 )
    FveDatumFree(v228);
  if ( v249 )
    FveDatumFree(v249);
  if ( v179 )
    CFveTpm::`scalar deleting destructor'(v179, v135);
  if ( v229 )
    CFveApiBase::ZeroFree(v229, 0x24u);
  if ( v230 )
    FveDatumFree(v230);
  if ( v231 )
    CFveApiBase::ZeroFree(v231, v162[0]);
  if ( v232 )
    FveCertFreeCertInfo(v232);
  if ( v262 )
  {
    CFveApiBase::ZeroFree(v262, 584LL * v272);
    v262 = 0;
  }
  if ( v263 )
  {
    PpfFreePredictions();
    v263 = 0;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::GetImpl'::`2'::impl)
    && lpMem )
  {
    CFveApiBase::FastFree(lpMem);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      80,
      WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids,
      (unsigned int)FirmwareType);
  return (unsigned int)FirmwareType;
}

```

## disassembly

```asm
0x1800b1450  mov     r11, rsp
0x1800b1453  push    rbx
0x1800b1454  push    rsi
0x1800b1455  push    rdi
0x1800b1456  push    r12
0x1800b1458  push    r13
0x1800b145a  push    r14
0x1800b145c  push    r15
0x1800b145e  sub     rsp, 0A20h
0x1800b1465  mov     rax, cs:__security_cookie
0x1800b146c  xor     rax, rsp
0x1800b146f  mov     [rsp+0A58h+var_48], rax
0x1800b1477  mov     dil, r9b
0x1800b147a  mov     [rsp+0A58h+var_7C8], r8
0x1800b1482  mov     r15, rdx
0x1800b1485  mov     [rsp+0A58h+var_8F0], rdx
0x1800b148d  mov     r13, rcx
0x1800b1490  mov     [rsp+0A58h+var_908], rcx
0x1800b1498  mov     [rsp+0A58h+var_8C0], rcx
0x1800b14a0  mov     rax, [rsp+0A58h+arg_28]
0x1800b14a8  mov     [rsp+0A58h+var_8B0], rax
0x1800b14b0  xorps   xmm0, xmm0
0x1800b14b3  xor     eax, eax
0x1800b14b5  movups  [rsp+0A58h+var_6E0], xmm0
0x1800b14bd  movups  xmmword ptr [rsp+0A58h+var_6D0], xmm0
0x1800b14c5  movups  xmmword ptr [rsp+0A58h+var_6D0+0Ch], xmm0
0x1800b14cd  xorps   xmm1, xmm1
0x1800b14d0  movups  [rsp+0A58h+var_680], xmm1
0x1800b14d8  movups  xmmword ptr [rsp+0A58h+var_670], xmm1
0x1800b14e0  movups  xmmword ptr [rsp+0A58h+var_670+0Ch], xmm1
0x1800b14e8  movups  [rsp+0A58h+var_6B0], xmm0
0x1800b14f0  movups  xmmword ptr [rsp+0A58h+var_6A0], xmm0
0x1800b14f8  movups  xmmword ptr [rsp+0A58h+var_6A0+0Ch], xmm0
0x1800b1500  movups  xmmword ptr [r11-60h], xmm0
0x1800b1505  mov     [r11-50h], rax
0x1800b1509  xor     r12d, r12d
0x1800b150c  mov     [r11-5F0h], r12d
0x1800b1513  movups  [rsp+0A58h+var_600], xmm0
0x1800b151b  movups  [rsp+0A58h+var_7C0], xmm1
0x1800b1523  mov     [r11-68h], r12
0x1800b1527  movups  [rsp+0A58h+var_720], xmm0
0x1800b152f  movups  [rsp+0A58h+var_710], xmm0
0x1800b1537  movups  [rsp+0A58h+var_700], xmm0
0x1800b153f  xor     edx, edx; Val
0x1800b1541  mov     r8d, 248h; Size
0x1800b1547  lea     rcx, [r11-2B8h]; void *
0x1800b154e  call    memset_0
0x1800b1553  xorps   xmm0, xmm0
0x1800b1556  movups  [rsp+0A58h+var_2C8], xmm0
0x1800b155e  or      eax, 0FFFFFFFFh
0x1800b1561  mov     [rsp+0A58h+var_928], eax
0x1800b1568  mov     [rsp+0A58h+var_89C], r12d
0x1800b1570  movups  xmmword ptr [rsp+0A58h+var_618.Data1], xmm0
0x1800b1578  mov     [rsp+0A58h+var_8A0], eax
0x1800b157f  xorps   xmm1, xmm1
0x1800b1582  movups  [rsp+0A58h+var_6F0], xmm1
0x1800b158a  lea     rsi, aNa; "NA"
0x1800b1591  mov     [rsp+0A58h+var_9C8], rsi
0x1800b1599  mov     [rsp+0A58h+var_97F], r12b
0x1800b15a1  mov     [rsp+0A58h+var_9D4], r12d
0x1800b15a9  mov     eax, r12d
0x1800b15ac  mov     [rsp+0A58h+var_9D0], eax
0x1800b15b3  mov     [rsp+0A58h+var_8E8], eax
0x1800b15ba  mov     [rsp+0A58h+var_9A0], r12
0x1800b15c2  mov     [rsp+0A58h+var_850], r12
0x1800b15ca  mov     [rsp+0A58h+var_978], r12
0x1800b15d2  mov     [rsp+0A58h+var_920], r12
0x1800b15da  mov     [rsp+0A58h+var_830], r12
0x1800b15e2  mov     [rsp+0A58h+var_840], r12
0x1800b15ea  mov     [rsp+0A58h+var_798], r12
0x1800b15f2  mov     qword ptr [rsp+0A58h+var_8B8], r12
0x1800b15fa  mov     [rsp+0A58h+var_9BF], r12b
0x1800b1602  mov     [rsp+0A58h+var_9BD], r12b
0x1800b160a  mov     [rsp+0A58h+var_9C0], r12b
0x1800b1612  mov     [rsp+0A58h+var_9BA], r12b
0x1800b161a  mov     [rsp+0A58h+var_9A8], r12b
0x1800b1622  mov     [rsp+0A58h+var_9BC], r12b
0x1800b162a  mov     [rsp+0A58h+var_98F], r12b
0x1800b1632  mov     [rsp+0A58h+var_650], r12b
0x1800b163a  mov     [rsp+0A58h+var_848], r12
0x1800b1642  mov     [rsp+0A58h+var_890], r12
0x1800b164a  mov     [rsp+0A58h+var_808], r12
0x1800b1652  mov     [rsp+0A58h+var_918], r12
0x1800b165a  mov     r14b, r12b
0x1800b165d  mov     [rsp+0A58h+var_9D8], r12b
0x1800b1665  mov     [rsp+0A58h+var_998], r12b
0x1800b166d  mov     [rsp+0A58h+var_9B0], r12b
0x1800b1675  mov     [rsp+0A58h+var_9BB], r12b
0x1800b167d  mov     [rsp+0A58h+var_818], r12
0x1800b1685  mov     [rsp+0A58h+var_8C8], r12
0x1800b168d  mov     [rsp+0A58h+var_970], r12
0x1800b1695  mov     [rsp+0A58h+var_964], r12d
0x1800b169d  mov     [rsp+0A58h+var_7F0], r12
0x1800b16a5  mov     dword ptr [rsp+0A58h+pbOutput], r12d
0x1800b16ad  mov     [rsp+0A58h+var_5EC], r12d
0x1800b16b5  mov     [rsp+0A58h+var_958], r12w
0x1800b16be  mov     [rsp+0A58h+var_954], r12w
0x1800b16c7  mov     [rsp+0A58h+var_960], r12w
0x1800b16d0  mov     [rsp+0A58h+var_838], r12
0x1800b16d8  mov     [rsp+0A58h+var_9CC], r12d
0x1800b16e0  mov     [rsp+0A58h+var_968], r12d
0x1800b16e8  mov     [rsp+0A58h+var_894], r12d
0x1800b16f0  lea     ebx, [r12+1]
0x1800b16f5  mov     [rsp+0A58h+var_990], bl
0x1800b16fc  mov     [rsp+0A58h+var_95C], r12w
0x1800b1705  mov     [rsp+0A58h+var_820], r12
0x1800b170d  mov     [rsp+0A58h+var_828], r12
0x1800b1715  lea     eax, [rbx+10h]
0x1800b1718  mov     [rsp+0A58h+var_9AC], ax
0x1800b1720  mov     [rsp+0A58h+var_620], r12d
0x1800b1728  mov     [rsp+0A58h+var_8F4], r12d
0x1800b1730  mov     [rsp+0A58h+var_8FC], r12d
0x1800b1738  mov     [rsp+0A58h+var_9A7], r12b
0x1800b1740  mov     [rsp+0A58h+var_8F8], r12d
0x1800b1748  mov     [rsp+0A58h+var_800], r12d
0x1800b1750  mov     [rsp+0A58h+var_8E0], r12d
0x1800b1758  mov     eax, r12d
0x1800b175b  mov     [rsp+0A58h+var_924], eax
0x1800b1762  mov     [rsp+0A58h+var_994], ax
0x1800b176a  mov     [rsp+0A58h+var_988], 3
0x1800b1775  mov     [rsp+0A58h+var_608], r12d
0x1800b177d  mov     [rsp+0A58h+var_9A5], r12b
0x1800b1785  mov     [rsp+0A58h+var_9B4], eax
0x1800b178c  mov     [rsp+0A58h+var_9B8], ax
0x1800b1794  mov     [rsp+0A58h+var_9BE], r12b
0x1800b179c  mov     [rsp+0A58h+var_9B9], r12b
0x1800b17a4  mov     [rsp+0A58h+var_644], ebx
0x1800b17ab  mov     [rsp+0A58h+var_64C], r12w
0x1800b17b4  mov     [rsp+0A58h+var_730], r12
0x1800b17bc  mov     [rsp+0A58h+var_728], r12
0x1800b17c4  mov     [rsp+0A58h+var_640], r12d
0x1800b17cc  mov     [rsp+0A58h+var_7E8], r12
0x1800b17d4  movups  [rsp+0A58h+var_2E8], xmm0
0x1800b17dc  movups  [rsp+0A58h+var_2D8], xmm0
0x1800b17e4  mov     [rsp+0A58h+var_810], r12
0x1800b17ec  mov     [rsp+0A58h+lpMem], r12
0x1800b17f4  mov     [rsp+0A58h+var_638], rax
0x1800b17fc  mov     [rsp+0A58h+var_630], eax
0x1800b1803  movups  [rsp+0A58h+var_880], xmm0
0x1800b180b  movups  [rsp+0A58h+var_870], xmm0
0x1800b1813  lea     rdx, [rsp+0A58h+var_9A8]; bool *
0x1800b181b  lea     rcx, aGeneratezrp; "GenerateZRP"
0x1800b1822  call    ?NgscbGet_TEST_BooleanOverride@@YA_NPEBGPEA_N@Z; NgscbGet_TEST_BooleanOverride(ushort const *,bool *)
0x1800b1827  lea     r12, WPP_GLOBAL_Control
0x1800b182e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b1835  cmp     rcx, r12
0x1800b1838  jz      short loc_1800B1854
0x1800b183a  test    byte ptr [rcx+1Ch], 20h
0x1800b183e  jz      short loc_1800B1854
0x1800b1840  lea     edx, [rbx+17h]
0x1800b1843  lea     r8, WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids
0x1800b184a  mov     rcx, [rcx+10h]
0x1800b184e  call    WPP_SF_
0x1800b1853  nop
0x1800b1854  cmp     [r15+4], ebx
0x1800b1858  jz      short loc_1800B188A
0x1800b185a  lea     rsi, aInvalidargauth; "InvalidArgAuthVersion"
0x1800b1861  mov     ebx, 80070057h
0x1800b1866  mov     [rsp+0A58h+var_9D4], ebx
0x1800b186d  mov     [rsp+0A58h+var_9C8], rsi
0x1800b1875  mov     r14b, [rsp+0A58h+var_9D8]
0x1800b187d  mov     r15d, [rsp+0A58h+var_9CC]
0x1800b1885  jmp     loc_1800B4BBA
0x1800b188a  cmp     dword ptr [r15], 38h ; '8'
0x1800b188e  jz      short loc_1800B1899
0x1800b1890  lea     rsi, aInvalidargstru; "InvalidArgStructSize"
0x1800b1897  jmp     short loc_1800B1861
0x1800b1899  mov     rax, [r13+0]
0x1800b189d  lea     rdx, [rsp+0A58h+var_650]
0x1800b18a5  mov     rcx, r13
0x1800b18a8  mov     rax, [rax+88h]
0x1800b18af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b18b4  mov     ebx, eax
0x1800b18b6  mov     [rsp+0A58h+var_9D4], eax
0x1800b18bd  xor     r11d, r11d
0x1800b18c0  test    eax, eax
0x1800b18c2  jns     short loc_1800B1918
0x1800b18c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b18cb  cmp     rcx, r12
0x1800b18ce  jz      short loc_1800B18F4
0x1800b18d0  lea     r12d, [r11+2]
0x1800b18d4  test    [rcx+1Ch], r12b
0x1800b18d8  jz      short loc_1800B18F4
0x1800b18da  lea     edx, [r11+19h]
0x1800b18de  mov     r9d, eax
0x1800b18e1  lea     r8, WPP_5e1fa37eb0e530d9bd71c2108c25ba67_Traceguids
0x1800b18e8  mov     rcx, [rcx+10h]
0x1800b18ec  call    WPP_SF_d
0x1800b18f1  xor     r11d, r11d
0x1800b18f4  lea     rsi, aReadfipssettin_0; "ReadFipsSetting"
0x1800b18fb  mov     [rsp+0A58h+var_9C8], rsi
0x1800b1903  mov     r14b, [rsp+0A58h+var_9D8]
0x1800b190b  mov     r15d, [rsp+0A58h+var_9CC]
0x1800b1913  jmp     loc_1800B4BBD
0x1800b1918  mov     r12d, [r15+8]
0x1800b191c  and     r12d, 3FE0000h
0x1800b1923  mov     [rsp+0A58h+var_9D0], r12d
0x1800b192b  mov     [rsp+0A58h+var_8E8], r12d
0x1800b1933  cmp     dword ptr [r15+8], 10000h
0x1800b193b  jz      loc_1800B1AD6
0x1800b1941  lea     rdx, aSecurestartupf_0; "SecureStartupFeature-Enabled-Premium"
0x1800b1948  mov     rcx, r13; this
0x1800b194b  call    ?LicenseCheck@CFveApiBase@@QEAAJPEBG@Z; CFveApiBase::LicenseCheck(ushort const *)
0x1800b1950  mov     ebx, eax
0x1800b1952  mov     [rsp+0A58h+var_9D4], eax
0x1800b1959  cmp     eax, 8031005Ah
0x1800b195e  jnz     short loc_1800B1986
0x1800b1960  mov     r14d, 10000001h
0x1800b1966  test    [r13+6Ch], r14d
0x1800b196a  jz      short loc_1800B19BD
0x1800b196c  cmp     r12d, 20000h
0x1800b1973  jz      short loc_1800B19A3
0x1800b1975  cmp     r12d, 80000h
0x1800b197c  jz      short loc_1800B19A3
0x1800b197e  mov     r14b, [rsp+0A58h+var_9D8]
0x1800b1986  mov     r10d, 10h
0x1800b198c  xor     r11d, r11d
0x1800b198f  test    ebx, ebx
0x1800b1991  jns     loc_1800B1AD6
0x1800b1997  lea     rsi, aLicensecheckfa; "LicenseCheckFailure"
0x1800b199e  jmp     loc_1800B1AAC
0x1800b19a3  lea     rdx, aSecurestartupf_2; "SecureStartupFeature-Enabled-DeviceEncr"...
0x1800b19aa  mov     rcx, r13; this
0x1800b19ad  call    ?LicenseCheck@CFveApiBase@@QEAAJPEBG@Z; CFveApiBase::LicenseCheck(ushort const *)
0x1800b19b2  mov     ebx, eax
0x1800b19b4  mov     [rsp+0A58h+var_9D4], eax
0x1800b19bb  jmp     short loc_1800B197E
0x1800b19bd  mov     r10d, 10h
0x1800b19c3  test    [r13+6Ch], r10b
0x1800b19c7  jz      short loc_1800B19DC
0x1800b19c9  cmp     r12d, 40000h
0x1800b19d0  jz      short loc_1800B19A3
0x1800b19d2  mov     r14b, [rsp+0A58h+var_9D8]
0x1800b19da  jmp     short loc_1800B198C
0x1800b19dc  lea     eax, [r12-40000h]
0x1800b19e4  test    eax, 0FFFBFFFFh
0x1800b19e9  jnz     short loc_1800B1A09
0x1800b19eb  lea     rdx, aSecurestartupf_2; "SecureStartupFeature-Enabled-DeviceEncr"...
0x1800b19f2  mov     rcx, r13; this
0x1800b19f5  call    ?LicenseCheck@CFveApiBase@@QEAAJPEBG@Z; CFveApiBase::LicenseCheck(ushort const *)
0x1800b19fa  mov     ebx, eax
0x1800b19fc  mov     [rsp+0A58h+var_9D4], eax
0x1800b1a03  mov     r10d, 10h
0x1800b1a09  cmp     ebx, 8031005Ah
0x1800b1a0f  jnz     short loc_1800B19D2
0x1800b1a11  cmp     r12d, 40000h
0x1800b1a18  jnz     short loc_1800B19D2
0x1800b1a1a  test    [r13+6Ch], r14d
0x1800b1a1e  jnz     short loc_1800B19D2
0x1800b1a20  mov     rcx, r13; this
0x1800b1a23  call    ?ResolveVolumeMountName@CFveApiBase@@QEAAJXZ; CFveApiBase::ResolveVolumeMountName(void)
0x1800b1a28  mov     ebx, eax
0x1800b1a2a  mov     [rsp+0A58h+var_9D4], eax
0x1800b1a31  xor     r11d, r11d
0x1800b1a34  test    eax, eax
0x1800b1a36  jns     short loc_1800B1A5C
0x1800b1a38  lea     rsi, aResolvevolumem; "ResolveVolumeMountName"
0x1800b1a3f  mov     [rsp+0A58h+var_9C8], rsi
0x1800b1a47  mov     r14b, [rsp+0A58h+var_9D8]
0x1800b1a4f  mov     r15d, [rsp+0A58h+var_9CC]
0x1800b1a57  jmp     loc_1800B4BC5
0x1800b1a5c  lea     rdx, [rsp+0A58h+var_9A5]; bool *
0x1800b1a64  mov     rcx, [r13+188h]; unsigned __int16 *
0x1800b1a6b  call    ?IsVolumeVirtual@@YAJPEBGPEA_N@Z; IsVolumeVirtual(ushort const *,bool *)
0x1800b1a70  mov     ebx, eax
0x1800b1a72  mov     [rsp+0A58h+var_9D4], eax
0x1800b1a79  xor     r11d, r11d
0x1800b1a7c  test    eax, eax
0x1800b1a7e  jns     short loc_1800B1A89
0x1800b1a80  lea     rsi, aIsvolumevirtua; "IsVolumeVirtual"
0x1800b1a87  jmp     short loc_1800B1A3F
0x1800b1a89  mov     r10d, 10h
0x1800b1a8f  cmp     [rsp+0A58h+var_9A5], r11b
0x1800b1a97  jnz     short loc_1800B1AC9
0x1800b1a99  mov     ebx, 8031005Ah
0x1800b1a9e  mov     [rsp+0A58h+var_9D4], ebx
0x1800b1aa5  lea     rsi, aNofeaturelicen; "NoFeatureLicense"
0x1800b1aac  mov     [rsp+0A58h+var_9C8], rsi
0x1800b1ab4  mov     r14b, [rsp+0A58h+var_9D8]
0x1800b1abc  mov     r15d, [rsp+0A58h+var_9CC]
0x1800b1ac4  jmp     loc_1800B4BCB
0x1800b1ac9  mov     r14b, [rsp+0A58h+var_9D8]
0x1800b1ad1  jmp     loc_1800B198F
0x1800b1ad6  cmp     r12d, 20000h
0x1800b1add  jnz     loc_1800B1B7C
0x1800b1ae3  cmp     dword ptr [r15+8], 10000h
0x1800b1aeb  jz      loc_1800B1B7C
0x1800b1af1  lea     rcx, [rsp+0A58h+var_988]; enum _FIRMWARE_TYPE *
0x1800b1af9  call    ?FveGetFirmwareType@@YAJPEAW4_FIRMWARE_TYPE@@@Z; FveGetFirmwareType(_FIRMWARE_TYPE *)
0x1800b1afe  mov     ebx, eax
0x1800b1b00  mov     [rsp+0A58h+var_9D4], eax
0x1800b1b07  xor     r11d, r11d
0x1800b1b0a  test    eax, eax
0x1800b1b0c  jns     short loc_1800B1B1A
0x1800b1b0e  lea     rsi, aFvegetfirmware_0; "FveGetFirmwareType"
0x1800b1b15  jmp     loc_1800B1A3F
0x1800b1b1a  cmp     [rsp+0A58h+var_988], 1
0x1800b1b22  jnz     short loc_1800B1B7C
0x1800b1b24  lea     rcx, [rsp+0A58h+var_608]
0x1800b1b2c  call    cs:__imp_?TpmGetTpmVersion@@YAJPEAI@Z; TpmGetTpmVersion(uint *)
  ... truncated ...
```
