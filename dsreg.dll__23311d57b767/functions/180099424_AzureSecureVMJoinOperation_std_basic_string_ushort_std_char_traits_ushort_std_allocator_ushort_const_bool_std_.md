# AzureSecureVMJoinOperation(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,struct_dsreg_server_response *)

- ea: `0x180099424`
- end: `0x18009b41b`
- name: `?AzureSecureVMJoinOperation@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N0PEAUstruct_dsreg_server_response@@@Z`
- size: `8183`
- prototype: `__int64 __fastcall(__int64, char, const wchar_t *, struct struct_dsreg_server_response *)`
- caller_count: `1`
- callee_count: `56`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18009b940`

## callees

- `0x1800012a4`
- `0x180002c98`
- `0x1800084f4`
- `0x18000ab70`
- `0x18000bac0`
- `0x18000db10`
- `0x18000eda4`
- `0x18000f4a0`
- `0x180012948`
- `0x180012c7c`
- `0x18001378c`
- `0x180016b90`
- `0x180017e18`
- `0x180017e90`
- `0x18001dfcc`
- `0x1800204f0`
- `0x18002927c`
- `0x18002b9b4`
- `0x18002c1d0`
- `0x18002c894`
- `0x18002dde4`
- `0x180030c5c`
- `0x1800319ac`
- `0x180034684`
- `0x1800360e8`
- `0x180036b74`
- `0x180037134`
- `0x1800373cc`
- `0x180037544`
- `0x180037b40`
- `0x180038dc4`
- `0x18003d11c`
- `0x18003dab8`
- `0x18003e11c`
- `0x180040614`
- `0x18004090c`
- `0x180040d38`
- `0x1800422e0`
- `0x180042370`
- `0x1800423e4`
- `0x18004271c`
- `0x180043ef8`
- `0x180044300`
- `0x180046ae8`
- `0x180046b3c`
- `0x180055174`
- `0x18006c144`
- `0x180098078`
- `0x180099370`
- `0x1800993bc`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180099628`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180099656`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18009988e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180099628`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180099656`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18009988e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18009a9b8`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18009af5a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18009a9b8`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18009af5a`

## string_xrefs

- `0x180099767`: `ReadBoolOption`
- `0x180099bc5`: `Device is already joined to Azure AD.\n`
- `0x180099cab`: `%s: AzureSecureVMJoin failed. VM already joined but not in SecureVM state, but the command specifies MDM enrollment to be performed. This is not supported. Unjoin the device and retry the command.\n`
- `0x180099c93`: `AzureSecureVMJoin failed. VM is already joined and is in SecureVM state, but MDM enrollment is requested.`
- `0x180099d3d`: `%s: AzureSecureVMJoin failed. VM is already joined but not in SecureVM state.\n`
- `0x180099d25`: `AzureSecureVMJoin failed. VM is already joined but no in SecureVM state.`
- `0x180099d97`: `AzureSecureVMJoin failed. VM is joined to Active Directory and cannot be switched to SecureVM state.`
- `0x180099dc5`: `Joining device to Azure AD with MSI credential.\nGetting Azure VM metadata.\n`
- `0x180099daf`: `%s: AzureSecureVMJoin failed. VM is joined to Active Directory and cannot be switched to SecureVM state.\n`
- `0x180099fd4`: `Getting Tenant ID from MSI.\n`
- `0x18009a466`: `%s: DsrCmdAzureHelper::GetMsiAccessToken failed 0x%08x.\n`
- `0x18009a3e9`: `Getting MSI token for app %s.\n`
- `0x18009a4f7`: `DsrCmdAzureHelper::GetMsiAccessToken failed`
- `0x18009a4de`: `DsrCmdAzureHelper::GetMsiAccessToken`
- `0x18009a51e`: `Starting join process with MSI credential.\n`
- `0x18009a840`: `%s: Discovery of MDM URLs (DeviceEnroller::GetDeviceOnlyWamToken) failed with error 0x%08x. AAD logs may contain more details on the failure. Additional information: %s\n`
- `0x18009a88f`: `%s: Discovery of MDM URLs (DeviceEnroller::GetDeviceOnlyWamToken) failed with error 0x%08x. AAD logs may contain more details on the failure. Additional information: %s\n`
- `0x18009a8bc`: `%s: Discovery of MDM URLs (DeviceEnroller::GetDeviceOnlyWamToken) failed with error 0x%08x. AAD logs may contain more details on the failure. Additional information: %s\n`
- `0x18009a8e7`: `DeviceEnroller::GetDeviceOnlyWamToken(MDM_URL_Discovery) failed`
- `0x18009aad7`: `DeviceEnroller::GetDeviceOnlyWamToken(MDM_URL_Discovery) failed`
- `0x18009a8ce`: `DeviceEnroller::GetDeviceOnlyWamToken(MDM_URL_Discovery)`
- `0x18009aabe`: `DeviceEnroller::GetDeviceOnlyWamToken(MDM_URL_Discovery)`
- `0x18009aa09`: `%s: Discovery of MDM URLs failed (no MDM URLs retruned by the AAD server). Verify MDM configuration in the tenant is correct and/or specified MDM app ID (%s) is correct and it's successfully resolved by AAD server\n`
- `0x18009ae7d`: `DeviceEnroller::GetDeviceOnlyWamToken(MMDM_Token)`
- `0x18009adf8`: `%s: Getting token for MDM enrollment (DeviceEnroller::GetDeviceOnlyWamToken) failed with error 0x%08x. AAD logs may contain more details on the failure. Additional information: %s\n`
- `0x18009ae44`: `%s: Getting token for MDM enrollment (DeviceEnroller::GetDeviceOnlyWamToken) failed with error 0x%08x. AAD logs may contain more details on the failure. Additional information: %s\n`
- `0x18009ae6b`: `%s: Getting token for MDM enrollment (DeviceEnroller::GetDeviceOnlyWamToken) failed with error 0x%08x. AAD logs may contain more details on the failure. Additional information: %s\n`
- `0x18009af75`: `Access token for MDM enrollment acquired successfully.\nStarting MDM enrollment...\n`
- `0x18009ae96`: `DeviceEnroller::GetDeviceOnlyWamToken(MMDM_Token) failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AzureSecureVMJoinOperation(
        __int64 a1,
        char a2,
        const wchar_t *a3,
        struct struct_dsreg_server_response *a4)
{
  unsigned int v6; // r14d
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 v9; // rcx
  WCHAR *v10; // r13
  __int64 v11; // rdx
  __int64 v12; // rcx
  _QWORD *CurrentRef; // rax
  __int64 v14; // rdx
  _QWORD *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rcx
  _QWORD *v22; // rax
  __int64 v23; // rdx
  _QWORD *v24; // rax
  __int64 v25; // rcx
  __int64 v26; // rax
  int v27; // eax
  BOOL v28; // ebx
  const wchar_t *v29; // rdx
  __int64 v30; // r8
  __int64 v31; // rdx
  __int64 v32; // rcx
  unsigned int IsDeviceJoined; // edi
  __int64 v34; // r8
  const wchar_t *v35; // rdx
  __int64 v36; // rdx
  __int64 v37; // rcx
  _BYTE **v38; // rax
  const wchar_t *v39; // rbx
  __int64 v40; // rdx
  __int64 v41; // rcx
  _QWORD *v42; // rax
  __int64 v43; // rdx
  _QWORD *v44; // rax
  __int64 v45; // rdx
  __int64 v46; // rax
  unsigned int v47; // ebx
  __int64 v48; // r9
  unsigned __int16 *v49; // rax
  char **v50; // rax
  char **v51; // rax
  char **v52; // rax
  char **v53; // rax
  _QWORD *v54; // rax
  char **v55; // rax
  __int64 String; // rax
  const unsigned __int16 *v57; // rbx
  __int64 v58; // rax
  const unsigned __int16 *v59; // rdx
  __int64 v61; // rdx
  __int64 v62; // rcx
  _QWORD *v63; // rax
  __int64 v64; // rdx
  _QWORD *v65; // rax
  __int64 v66; // rcx
  __int64 v67; // rax
  __int64 v68; // rdx
  __int64 v69; // rcx
  __int64 v70; // rdx
  __int64 v71; // rcx
  _BYTE **v72; // rax
  const wchar_t *v73; // rbx
  __int64 v74; // rdx
  __int64 v75; // rcx
  _QWORD *v76; // rax
  __int64 v77; // rdx
  _QWORD *v78; // rax
  __int64 v79; // rcx
  __int64 v80; // rax
  __int64 v81; // rdx
  __int64 v82; // rcx
  __int64 v83; // rdx
  __int64 v84; // rcx
  __int64 v85; // rdx
  __int64 v86; // rcx
  __int64 v87; // rdx
  __int64 v88; // rcx
  _QWORD *v89; // rax
  __int64 v90; // rdx
  _QWORD *v91; // rax
  __int64 v92; // rcx
  __int64 v93; // rax
  bool v94; // r14
  __int64 v95; // rdx
  __int64 v96; // rdx
  __int64 v97; // rcx
  __int64 v98; // rdx
  __int64 v99; // rcx
  _QWORD *v100; // rax
  __int64 v101; // rdx
  _QWORD *v102; // rax
  __int64 v103; // rdx
  __int64 v104; // rax
  __int64 v105; // r8
  const wchar_t *v106; // rdx
  _QWORD *v107; // rdx
  __int64 v108; // r8
  __int64 v109; // rdx
  __int64 v110; // rcx
  _QWORD *v111; // rdx
  __int64 v112; // rdx
  __int64 v113; // rcx
  _QWORD *v114; // rax
  __int64 v115; // rdx
  _QWORD *v116; // rax
  __int64 v117; // rdx
  _QWORD *v118; // rbx
  __int64 v119; // rax
  _QWORD *v120; // rdx
  __int64 v121; // rdx
  __int64 v122; // rcx
  __int64 v123; // rdx
  __int64 v124; // rcx
  _QWORD *v125; // rax
  __int64 v126; // rdx
  _QWORD *v127; // rax
  __int64 v128; // rcx
  __int64 v129; // rax
  __int64 v130; // rdx
  __int64 v131; // rdx
  __int64 v132; // rcx
  __int64 v133; // rdx
  __int64 v134; // rcx
  _QWORD *v135; // rax
  __int64 v136; // rdx
  _QWORD *v137; // rax
  __int64 v138; // rdx
  __int64 v139; // rax
  unsigned __int16 *v140; // rdx
  __int64 v141; // rdx
  __int64 v142; // rcx
  _QWORD *v143; // rax
  __int64 v144; // rdx
  _QWORD *v145; // rax
  __int64 v146; // rdx
  unsigned __int16 *v147; // rbx
  __int64 v148; // rax
  unsigned __int16 *v149; // rdx
  __int64 v150; // rdx
  __int64 v151; // rcx
  unsigned __int16 *v152; // rdx
  __int64 v153; // rdx
  __int64 v154; // rcx
  _QWORD *v155; // rax
  __int64 v156; // rdx
  _QWORD *v157; // rax
  __int64 v158; // rdx
  unsigned __int16 *v159; // rbx
  __int64 v160; // rax
  unsigned __int16 *v161; // rdx
  __int64 v162; // rdx
  __int64 v163; // rcx
  unsigned __int16 *v164; // r8
  __int64 v165; // rdx
  __int64 v166; // rcx
  _QWORD *v167; // rax
  __int64 v168; // rdx
  _QWORD *v169; // rax
  __int64 v170; // rdx
  unsigned __int16 *v171; // rbx
  __int64 v172; // rax
  unsigned __int16 *v173; // r8
  __int64 v174; // rax
  __int64 v175; // rax
  std::_Ref_count_base *v176; // r13
  __int64 v177; // rsi
  __int64 v178; // r8
  __int64 v179; // rdx
  __int64 v180; // rcx
  __int64 v181; // rdx
  __int64 v182; // rcx
  _QWORD *v183; // rax
  __int64 v184; // rdx
  _QWORD *v185; // rax
  __int64 v186; // rcx
  __int64 v187; // rax
  __int64 v188; // r8
  __int64 v189; // rdx
  __int64 v190; // rcx
  __int64 v191; // rdx
  __int64 v192; // rcx
  _QWORD *v193; // rax
  __int64 v194; // rdx
  _QWORD *v195; // rax
  __int64 v196; // rdx
  __int64 v197; // rax
  __int64 v198; // r8
  const wchar_t *v199; // rdx
  __int64 v200; // rdx
  __int64 v201; // rcx
  _QWORD *v202; // rax
  __int64 v203; // rdx
  _QWORD *v204; // rax
  __int64 v205; // rcx
  __int64 v206; // rax
  _QWORD *v207; // r8
  _QWORD *v208; // r9
  _QWORD **v209; // rax
  __int64 v210; // r8
  unsigned __int16 *v211; // r9
  __int64 v212; // rdx
  __int64 v213; // rcx
  __int64 v214; // rdx
  __int64 v215; // rcx
  _QWORD *v216; // rax
  __int64 v217; // rdx
  _QWORD *v218; // rax
  __int64 v219; // rdx
  __int64 v220; // rax
  const wchar_t *v221; // rdx
  unsigned __int16 **v222; // rdx
  __int64 v223; // r8
  __int64 v224; // rdx
  __int64 v225; // rcx
  unsigned __int16 **v226; // rdx
  __int64 v227; // rdx
  __int64 v228; // rcx
  _QWORD *v229; // rax
  __int64 v230; // rdx
  _QWORD *v231; // rax
  __int64 v232; // rdx
  unsigned __int16 **v233; // rbx
  __int64 v234; // rax
  unsigned __int16 **v235; // rdx
  unsigned __int16 *v236; // r12
  const wchar_t *v237; // r8
  __int64 v238; // rdx
  __int64 v239; // rcx
  unsigned __int16 **v240; // r9
  __int64 v241; // rdx
  __int64 v242; // rcx
  _QWORD *v243; // rax
  __int64 v244; // rdx
  _QWORD *v245; // rax
  __int64 v246; // rdx
  unsigned __int16 **v247; // rbx
  __int64 v248; // rax
  unsigned __int16 **v249; // r9
  const unsigned __int16 *v250; // rdx
  __int64 v251; // rdx
  __int64 v252; // rcx
  unsigned __int32 v253; // ebx
  __int64 v254; // rdx
  __int64 v255; // rcx
  _QWORD *v256; // rax
  __int64 v257; // rdx
  _QWORD *v258; // rax
  __int64 v259; // rdx
  __int64 v260; // rax
  unsigned __int32 v261; // ebx
  const unsigned __int16 *v262; // rdx
  __int64 v263; // rdx
  __int64 v264; // rcx
  unsigned __int16 **v265; // r8
  __int64 v266; // rdx
  __int64 v267; // rcx
  _QWORD *v268; // rax
  __int64 v269; // rdx
  _QWORD *v270; // rax
  __int64 v271; // rdx
  unsigned __int16 **v272; // rbx
  __int64 v273; // rax
  unsigned __int16 **v274; // r8
  const unsigned __int16 *v275; // r8
  unsigned __int16 **v276; // rdx
  __int64 v277; // rdx
  __int64 v278; // rcx
  _QWORD *v279; // rax
  __int64 v280; // rdx
  _QWORD *v281; // rax
  __int64 v282; // rdx
  unsigned __int16 **v283; // rbx
  __int64 v284; // rax
  unsigned __int16 **v285; // rdx
  unsigned __int16 **v286; // rax
  unsigned __int16 **v287; // rcx
  __int16 v288; // cx
  int v289; // r8d
  int v290; // edx
  int v291; // ebx
  __int64 v292; // rdx
  __int64 v293; // rcx
  __int64 v294; // rax
  __int64 v295; // rax
  int *v296; // rdx
  __int64 v297; // rdx
  __int64 v298; // rcx
  _QWORD *v299; // rax
  __int64 v300; // rdx
  _QWORD *v301; // rax
  __int64 v302; // rdx
  int *v303; // rbx
  __int64 v304; // rax
  int *v305; // rdx
  __int64 v306; // rdx
  __int64 v307; // rcx
  int *v308; // rdx
  unsigned __int16 **v309; // r9
  __int64 v310; // rdx
  __int64 v311; // rcx
  _QWORD *v312; // rax
  __int64 v313; // rdx
  _QWORD *v314; // rax
  __int64 v315; // rdx
  unsigned __int16 **v316; // rbx
  __int64 v317; // rax
  unsigned __int16 **v318; // r9
  const unsigned __int16 *v319; // rdx
  __int64 v320; // rdx
  __int64 v321; // rcx
  unsigned __int32 v322; // ebx
  __int64 v323; // rdx
  __int64 v324; // rcx
  _QWORD *v325; // rax
  __int64 v326; // rdx
  _QWORD *v327; // rax
  __int64 v328; // rdx
  __int64 v329; // rax
  unsigned __int32 v330; // ebx
  __int64 v331; // rdx
  __int64 v332; // rcx
  _QWORD *v333; // rax
  __int64 v334; // rdx
  _QWORD *v335; // rax
  __int64 v336; // rcx
  __int64 v337; // rax
  __int64 *v338; // rax
  int *v339; // r9
  unsigned __int16 **v340; // r8
  __int64 v341; // rdx
  __int64 v342; // rcx
  unsigned __int16 **v343; // r9
  __int64 v344; // rdx
  __int64 v345; // rcx
  _QWORD *v346; // rax
  __int64 v347; // rdx
  _QWORD *v348; // rax
  __int64 v349; // rdx
  unsigned __int16 **v350; // rbx
  __int64 v351; // rax
  unsigned __int16 **v352; // r9
  __int64 v353; // rdx
  __int64 v354; // rcx
  __int64 v355; // rdx
  __int64 v356; // rcx
  _QWORD *v357; // rax
  __int64 v358; // rdx
  _QWORD *v359; // rax
  __int64 v360; // rcx
  __int64 v361; // rax
  const unsigned __int16 *v362; // rcx
  __int64 v363; // rdx
  __int64 v364; // rcx
  __int64 v365; // rdx
  __int64 v366; // rcx
  _QWORD *v367; // rax
  __int64 v368; // rdx
  _QWORD *v369; // rax
  __int64 v370; // rcx
  __int64 v371; // rax
  const unsigned __int16 *v372; // r8
  __int64 v373; // rdx
  __int64 v374; // rcx
  _QWORD *v375; // rax
  __int64 v376; // rdx
  _QWORD *v377; // rax
  __int64 v378; // rcx
  __int64 v379; // rax
  __int64 v380; // rdx
  __int64 v381; // rcx
  _QWORD *v382; // rax
  __int64 v383; // rdx
  _QWORD *v384; // rax
  __int64 v385; // rcx
  __int64 v386; // rax
  const unsigned __int16 *v387; // rcx
  int *v388; // [rsp+20h] [rbp-E0h]
  bool v389; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v390; // [rsp+84h] [rbp-7Ch] BYREF
  char **v391; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v392; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v393; // [rsp+98h] [rbp-68h] BYREF
  int v394[2]; // [rsp+A0h] [rbp-60h] BYREF
  void *Block[2]; // [rsp+A8h] [rbp-58h] BYREF
  void *v396[2]; // [rsp+B8h] [rbp-48h]
  void *v397[2]; // [rsp+C8h] [rbp-38h]
  void *v398; // [rsp+D8h] [rbp-28h]
  std::_Ref_count_base *v399[2]; // [rsp+E0h] [rbp-20h] BYREF
  char **v400; // [rsp+F0h] [rbp-10h] BYREF
  char **v401; // [rsp+F8h] [rbp-8h] BYREF
  char **v402; // [rsp+100h] [rbp+0h] BYREF
  _QWORD *v403; // [rsp+108h] [rbp+8h] BYREF
  char **v404; // [rsp+110h] [rbp+10h] BYREF
  WCHAR *v405; // [rsp+118h] [rbp+18h] BYREF
  struct struct_dsreg_server_response *v406; // [rsp+120h] [rbp+20h]
  __m128i si128; // [rsp+128h] [rbp+28h]
  int v408; // [rsp+138h] [rbp+38h]
  __m128i v409; // [rsp+13Ch] [rbp+3Ch]
  int **v410; // [rsp+150h] [rbp+50h]
  unsigned __int16 *Src[3]; // [rsp+158h] [rbp+58h] BYREF
  unsigned __int64 v412; // [rsp+170h] [rbp+70h]
  unsigned __int16 v413[8]; // [rsp+178h] [rbp+78h] BYREF
  __int64 v414; // [rsp+188h] [rbp+88h]
  unsigned __int64 v415; // [rsp+190h] [rbp+90h]
  unsigned __int16 *v416[3]; // [rsp+198h] [rbp+98h] BYREF
  unsigned __int64 v417; // [rsp+1B0h] [rbp+B0h]
  unsigned __int16 *v418[3]; // [rsp+1B8h] [rbp+B8h] BYREF
  unsigned __int64 v419; // [rsp+1D0h] [rbp+D0h]
  int v420[6]; // [rsp+1D8h] [rbp+D8h] BYREF
  unsigned __int64 v421; // [rsp+1F0h] [rbp+F0h]
  _QWORD v422[3]; // [rsp+1F8h] [rbp+F8h] BYREF
  unsigned __int64 v423; // [rsp+210h] [rbp+110h]
  int v424; // [rsp+218h] [rbp+118h] BYREF
  char v425; // [rsp+21Ch] [rbp+11Ch]
  GUID ActivityId; // [rsp+220h] [rbp+120h] BYREF
  GUID v427; // [rsp+230h] [rbp+130h] BYREF
  __int64 v428[4]; // [rsp+240h] [rbp+140h] BYREF
  _QWORD v429[4]; // [rsp+260h] [rbp+160h] BYREF
  unsigned __int16 *v430[3]; // [rsp+280h] [rbp+180h] BYREF
  unsigned __int64 v431; // [rsp+298h] [rbp+198h]
  char *v432[4]; // [rsp+2A0h] [rbp+1A0h] BYREF
  char *v433[4]; // [rsp+2C0h] [rbp+1C0h] BYREF
  char *v434[4]; // [rsp+2E0h] [rbp+1E0h] BYREF
  char *v435[4]; // [rsp+300h] [rbp+200h] BYREF
  char *v436[4]; // [rsp+320h] [rbp+220h] BYREF
  __int64 v437[4]; // [rsp+340h] [rbp+240h] BYREF
  _QWORD v438[4]; // [rsp+360h] [rbp+260h] BYREF
  int v439[6]; // [rsp+380h] [rbp+280h] BYREF
  WCHAR *v440; // [rsp+398h] [rbp+298h]
  _BYTE v441[32]; // [rsp+3B0h] [rbp+2B0h] BYREF
  _BYTE v442[32]; // [rsp+3D0h] [rbp+2D0h] BYREF

  v406 = a4;
  LODWORD(v391) = 0;
  v6 = 0;
  v390 = 0;
  *(_OWORD *)v399 = 0;
  std::wstring::wstring((__int64)v422);
  std::wstring::wstring((__int64)v438);
  std::wstring::wstring(v413, v7);
  std::wstring::wstring((__int64)v418);
  *(_OWORD *)Block = 0;
  *(_OWORD *)v396 = 0;
  *(_OWORD *)v397 = 0;
  v398 = 0;
  DsrCmdDeviceEnroller::DsrCmdDeviceEnroller((DsrCmdDeviceEnroller *)v439);
  v10 = (WCHAR *)&cchOriginalDestLength;
  if ( v440 )
    v10 = v440;
  v392 = v10;
  if ( **(_BYTE **)CmdOptions::GetCurrentRef(v9, v8) )
  {
    wprintf(L"%s: ClientRequestId: %s\n", L"AzureSecureVMJoinOperation", v10);
    CurrentRef = (_QWORD *)CmdOptions::GetCurrentRef(v12, v11);
    if ( *(_BYTE *)(*CurrentRef + 12LL) )
    {
      v15 = (_QWORD *)CmdOptions::GetCurrentRef(*CurrentRef, v14);
      if ( *(_QWORD *)(*v15 + 184LL) )
      {
        v17 = CmdOptions::GetCurrentRef(*v15, v16);
        fwprintf_s(
          *(FILE *const *)(*(_QWORD *)v17 + 184LL),
          L"%s: ClientRequestId: %s\n",
          L"AzureSecureVMJoinOperation",
          v10);
      }
    }
  }
  Logger::TraceInformation(L"%s: ClientRequestId: %s\n", L"AzureSecureVMJoinOperation", v10);
  v410 = g_hcdjAzureSecureVMJoinTraceLoggingProvider;
  TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_18013D8B8);
  v424 = 0;
  v425 = 0;
  std::wstring::wstring((__int64)v429, (__int64)L"undefined");
  std::wstring::wstring((__int64)v430, (__int64)L"undefined");
  std::wstring::wstring((__int64)v432, (__int64)L"undefined");
  std::wstring::wstring((__int64)v433, (__int64)L"undefined");
  std::wstring::wstring((__int64)v434, (__int64)L"undefined");
  std::wstring::wstring((__int64)v435, (__int64)L"undefined");
  std::wstring::wstring((__int64)v436, (__int64)L"undefined");
  if ( (unsigned int)dword_18013D8B8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18013D8B8, 0x400000000000LL) )
  {
    EventActivityIdControl(3u, &ActivityId);
    v427 = ActivityId;
    EventActivityIdControl(4u, &v427);
    v425 = 1;
  }
  else
  {
    ActivityId = 0;
  }
  v424 = 1;
  if ( (unsigned int)dword_18013D8B8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18013D8B8, 0x400000000000LL) )
  {
    *(_QWORD *)v394 = 50331648;
    if ( v425 )
      _tlgGuidIsZero(&v427);
    v388 = v394;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
      (__int64)&dword_18013D8B8,
      (__int64)&word_18012B3EE);
  }
  if ( **(_BYTE **)CmdOptions::GetCurrentRef(v19, v18) )
  {
    wprintf(L"Checking device join status...\n");
    v22 = (_QWORD *)CmdOptions::GetCurrentRef(v21, v20);
    if ( *(_BYTE *)(*v22 + 12LL) )
    {
      v24 = (_QWORD *)CmdOptions::GetCurrentRef(*v22, v23);
      if ( *(_QWORD *)(*v24 + 184LL) )
      {
        v26 = CmdOptions::GetCurrentRef(v25, *v24);
        fwprintf_s(*(FILE *const *)(*(_QWORD *)v26 + 184LL), L"Checking device join status...\n");
      }
    }
  }
  Logger::TraceInformation(L"Checking device join status...\n");
  v393 = 0;
  v394[0] = 0;
  v389 = 0;
  v27 = ReadBoolOption(L"ArcEnabledVM", &v389);
  if ( v27 < 0 )
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"IsArcDeviceEnabled",
      L"ReadBoolOption",
      (unsigned int)v27);
  v28 = v389;
  v29 = L"Arc-Enabled device";
  if ( !v389 )
    v29 = L"Azure device";
  v30 = -1;
  do
    ++v30;
  while ( v29[v30] );
  std::wstring::_Assign<unsigned short>(v436, v29, (char *)v30);
  IsDeviceJoined = DsrIsDeviceJoinedEx(&v393, 0, 0);
  if ( (IsDeviceJoined & 0x80000000) != 0 )
  {
    std::wstring::_Assign<unsigned short>(v432, L"DsrIsDeviceJoined", (char *)0x11);
    v34 = 45;
    v35 = L"AzureSecureVMJoin::DsrIsDeviceJoined failed.\n";
LABEL_28:
    std::wstring::_Assign<unsigned short>((char **)v430, v35, (char *)v34);
    v38 = (_BYTE **)CmdOptions::GetCurrentRef(v37, v36);
    v39 = L"%s: AzureSecureVMJoin::DsrIsDeviceJoined failed 0x%08x.\n";
    goto LABEL_29;
  }
  if ( v393 )
  {
    if ( **(_BYTE **)CmdOptions::GetCurrentRef(v32, v31) )
    {
      wprintf(L"Device is already joined to Azure AD.\n");
      v63 = (_QWORD *)CmdOptions::GetCurrentRef(v62, v61);
      if ( *(_BYTE *)(*v63 + 12LL) )
      {
        v65 = (_QWORD *)CmdOptions::GetCurrentRef(*v63, v64);
        if ( *(_QWORD *)(*v65 + 184LL) )
        {
          v67 = CmdOptions::GetCurrentRef(v66, *v65);
          fwprintf_s(*(FILE *const *)(*(_QWORD *)v67 + 184LL), L"Device is already joined to Azure AD.\n");
        }
      }
    }
    Logger::TraceInformation(L"Device is already joined to Azure AD.\n");
    v392 = 0;
    *(_QWORD *)v394 = 0;
    IsDeviceJoined = DsrGetJoinInfoEx(1, v394, &v392);
    std::wstring::_Assign<unsigned short>(v432, L"Dsreg::DsrGetJoinInfoEx", (char *)0x17);
    if ( (IsDeviceJoined & 0x80000000) != 0 )
    {
      v38 = (_BYTE **)CmdOptions::GetCurrentRef(v69, v68);
      v39 = L"%s: AzureSecureVMJoin::DsrGetJoinInfoEx failed 0x%08x.\n";
LABEL_29:
      if ( **v38 )
      {
        wprintf(v39, L"AzureSecureVMJoinOperation", IsDeviceJoined);
        v42 = (_QWORD *)CmdOptions::GetCurrentRef(v41, v40);
        if ( *(_BYTE *)(*v42 + 12LL) )
        {
          v44 = (_QWORD *)CmdOptions::GetCurrentRef(*v42, v43);
          if ( *(_QWORD *)(*v44 + 184LL) )
          {
            v46 = CmdOptions::GetCurrentRef(*v44, v45);
            fwprintf_s(*(FILE *const *)(*(_QWORD *)v46 + 184LL), v39, L"AzureSecureVMJoinOperation", IsDeviceJoined);
          }
        }
      }
      Logger::TraceError(v39, L"AzureSecureVMJoinOperation", IsDeviceJoined);
      goto LABEL_34;
    }
    if ( v392 && (v392[124] & 1) != 0 )
    {
      IsDeviceJoined = 0;
      if ( a2 )
      {
        IsDeviceJoined = -2145648524;
        std::wstring::_Assign<unsigned short>(
          (char **)v430,
          L"AzureSecureVMJoin failed. VM is already joined and is in SecureVM state, but MDM enrollment is requested.",
          (char *)0x69);
        v72 = (_BYTE **)CmdOptions::GetCurrentRef(v71, v70);
        v73 = L"%s: AzureSecureVMJoin failed. VM already joined but not in SecureVM state, but the command specifies MDM e"
               "nrollment to be performed. This is not supported. Unjoin the device and retry the command.\n";
        goto LABEL_76;
      }
LABEL_34:
      v47 = 0;
      goto LABEL_35;
    }
    IsDeviceJoined = -2145648572;
    std::wstring::_Assign<unsigned short>(
      (char **)v430,
      L"AzureSecureVMJoin failed. VM is already joined but no in SecureVM state.",
      (char *)0x48);
    v72 = (_BYTE **)CmdOptions::GetCurrentRef(v82, v81);
    v73 = L"%s: AzureSecureVMJoin failed. VM is already joined but not in SecureVM state.\n";
LABEL_76:
    if ( **v72 )
    {
      wprintf(v73, L"AzureSecureVMJoinOperation");
      v76 = (_QWORD *)CmdOptions::GetCurrentRef(v75, v74);
      if ( *(_BYTE *)(*v76 + 12LL) )
      {
        v78 = (_QWORD *)CmdOptions::GetCurrentRef(*v76, v77);
        if ( *(_QWORD *)(*v78 + 184LL) )
        {
          v80 = CmdOptions::GetCurrentRef(v79, *v78);
          fwprintf_s(*(FILE *const *)(*(_QWORD *)v80 + 184LL), v73, L"AzureSecureVMJoinOperation");
        }
      }
    }
    Logger::TraceError(v73, L"AzureSecureVMJoinOperation");
    goto LABEL_34;
  }
  IsDeviceJoined = IsLocalMachineDomainJoined(v394, 0);
  if ( (IsDeviceJoined & 0x80000000) != 0 )
  {
    std::wstring::_Assign<unsigned short>(v432, L"IsLocalMachineDomainJoined", (char *)0x1A);
    v34 = 35;
    v35 = L"IsLocalMachineDomainJoined failed.\n";
    goto LABEL_28;
  }
  if ( v394[0] )
  {
    IsDeviceJoined = -2145648523;
    std::wstring::_Assign<unsigned short>(
      (char **)v430,
      L"AzureSecureVMJoin failed. VM is joined to Active Directory and cannot be switched to SecureVM state.",
      (char *)0x64);
    v72 = (_BYTE **)CmdOptions::GetCurrentRef(v86, v85);
    v73 = L"%s: AzureSecureVMJoin failed. VM is joined to Active Directory and cannot be switched to SecureVM state.\n";
    goto LABEL_76;
  }
  if ( **(_BYTE **)CmdOptions::GetCurrentRef(v84, v83) )
  {
    wprintf(L"Joining device to Azure AD with MSI credential.\nGetting Azure VM metadata.\n");
    v89 = (_QWORD *)CmdOptions::GetCurrentRef(v88, v87);
    if ( *(_BYTE *)(*v89 + 12LL) )
    {
      v91 = (_QWORD *)CmdOptions::GetCurrentRef(*v89, v90);
      if ( *(_QWORD *)(*v91 + 184LL) )
      {
        v93 = CmdOptions::GetCurrentRef(v92, *v91);
        fwprintf_s(
          *(FILE *const *)(*(_QWORD *)v93 + 184LL),
          L"Joining device to Azure AD with MSI credential.\nGetting Azure VM metadata.\n");
      }
    }
  }
  Logger::TraceInformation(L"Joining device to Azure AD with MSI credential.\nGetting Azure VM metadata.\n");
  v94 = v28;
  LOBYTE(v95) = v28;
  IsDeviceJoined = DsrCmdAzureHelper::GetAzureResourceId(v422, v95);
  if ( (IsDeviceJoined & 0x80000000) != 0 )
  {
    if ( **(_BYTE **)CmdOptions::GetCurrentRef(v97, v96) )
    {
      wprintf(
        L"%s: DsrCmdAzureHelper::GetAzureResourceId failed 0x%08x.\n",
        L"AzureSecureVMJoinOperation",
        IsDeviceJoined);
      v100 = (_QWORD *)CmdOptions::GetCurrentRef(v99, v98);
      if ( *(_BYTE *)(*v100 + 12LL) )
      {
        v102 = (_QWORD *)CmdOptions::GetCurrentRef(*v100, v101);
        if ( *(_QWORD *)(*v102 + 184LL) )
        {
          v104 = CmdOptions::GetCurrentRef(*v102, v103);
          fwprintf_s(
            *(FILE *const *)(*(_QWORD *)v104 + 184LL),
            L"%s: DsrCmdAzureHelper::GetAzureResourceId failed 0x%08x.\n",
            L"AzureSecureVMJoinOperation",
            IsDeviceJoined);
        }
      }
    }
    Logger::TraceError(
      L"%s: DsrCmdAzureHelper::GetAzureResourceId failed 0x%08x.\n",
      L"AzureSecureVMJoinOperation",
      IsDeviceJoined);
    std::wstring::_Assign<unsigned short>(v432, L"DsrCmdAzureHelper::GetAzureResourceId", (char *)0x25);
    v105 = 44;
    v106 = L"DsrCmdAzureHelper::GetAzureResourceId failed";
LABEL_96:
    std::wstring::_Assign<unsigned short>((char **)v430, v106, (char *)v105);
    v6 = 0;
    goto LABEL_34;
  }
  v107 = v422;
  if ( v423 > 7 )
    v107 = (_QWORD *)v422[0];
  v108 = -1;
  do
    ++v108;
  while ( *((_WORD *)v107 + v108) );
  std::wstring::_Assign<unsigned short>(v434, v107, (char *)v108);
  if ( **(_BYTE **)CmdOptions::GetCurrentRef(v110, v109) )
  {
    v111 = v422;
    if ( v423 > 7 )
      v111 = (_QWORD *)v422[0];
    wprintf(L"Azure resource Id:%s\n", v111);
    v114 = (_QWORD *)CmdOptions::GetCurrentRef(v113, v112);
    if ( *(_BYTE *)(*v114 + 12LL) )
    {
      v116 = (_QWORD *)CmdOptions::GetCurrentRef(*v114, v115);
      if ( *(_QWORD *)(*v116 + 184LL) )
      {
        v118 = v422;
        if ( v423 > 7 )
          v118 = (_QWORD *)v422[0];
        v119 = CmdOptions::GetCurrentRef(*v116, v117);
        fwprintf_s(*(FILE *const *)(*(_QWORD *)v119 + 184LL), L"Azure resource Id:%s\n", v118);
      }
    }
  }
  v120 = v422;
  if ( v423 > 7 )
    v120 = (_QWORD *)v422[0];
  Logger::TraceVerbose((wchar_t *)L"Azure resource Id:%s\n", v120);
  if ( v414 )
  {
    if ( **(_BYTE **)CmdOptions::GetCurrentRef(v122, v121) )
    {
      v140 = v413;
      if ( v415 > 7 )
        v140 = *(unsigned __int16 **)v413;
      wprintf(L"Use passed in Tenant ID '%s'.\n", v140);
      v143 = (_QWORD *)CmdOptions::GetCurrentRef(v142, v141);
      if ( *(_BYTE *)(*v143 + 12LL) )
      {
        v145 = (_QWORD *)CmdOptions::GetCurrentRef(*v143, v144);
        if ( *(_QWORD *)(*v145 + 184LL) )
        {
          v147 = v413;
          if ( v415 > 7 )
            v147 = *(unsigned __int16 **)v413;
          v148 = CmdOptions::GetCurrentRef(*v145, v146);
          fwprintf_s(*(FILE *const *)(*(_QWORD *)v148 + 184LL), L"Use passed in Tenant ID '%s'.\n", v147);
        }
      }
    }
    v149 = v413;
    if ( v415 > 7 )
      v149 = *(unsigned __int16 **)v413;
    Logger::TraceInformation(L"Use passed in Tenant ID '%s'.\n", v149);
  }
  else
  {
    if ( **(_BYTE **)CmdOptions::GetCurrentRef(v122, v121) )
    {
      wprintf(L"Getting Tenant ID from MSI.\n");
      v125 = (_QWORD *)CmdOptions::GetCurrentRef(v124, v123);
      if ( *(_BYTE *)(*v125 + 12LL) )
      {
        v127 = (_QWORD *)CmdOptions::GetCurrentRef(*v125, v126);
        if ( *(_QWORD *)(*v127 + 184LL) )
        {
          v129 = CmdOptions::GetCurrentRef(v128, *v127);
          fwprintf_s(*(FILE *const *)(*(_QWORD *)v129 + 184LL), L"Getting Tenant ID from MSI.\n");
        }
      }
    }
    Logger::TraceInformation(L"Getting Tenant ID from MSI.\n");
    LOBYTE(v130) = v94;
    IsDeviceJoined = DsrCmdAzureHelper::GetTenantId(v413, v130);
    if ( (IsDeviceJoined & 0x80000000) != 0 )
    {
      if ( **(_BYTE **)CmdOptions::GetCurrentRef(v132, v131) )
      {
        wprintf(L"%s: DsrCmdAzureHelper::GetTenantId failed 0x%08x.\n", L"AzureSecureVMJoinOperation", IsDeviceJoined);
        v135 = (_QWORD *)CmdOptions::GetCurrentRef(v134, v133);
        if ( *(_BYTE *)(*v135 + 12LL) )
        {
          v137 = (_QWORD *)CmdOptions::GetCurrentRef(*v135, v136);
          if ( *(_QWORD *)(*v137 + 184LL) )
          {
            v139 = CmdOptions::GetCurrentRef(*v137, v138);
            fwprintf_s(
              *(FILE *const *)(*(_QWORD *)v139 + 184LL),
              L"%s: DsrCmdAzureHelper::GetTenantId failed 0x%08x.\n",
              L"AzureSecureVMJoinOperation",
              IsDeviceJoined);
          }
        }
      }
      Logger::TraceError(
        L"%s: DsrCmdAzureHelper::GetTenantId failed 0x%08x.\n",
        L"AzureSecureVMJoinOperation",
        IsDeviceJoined);
      std::wstring::_Assign<unsigned short>(v432, L"DsrCmdAzureHelper::GetTenantId", (char *)0x1E);
      v105 = 37;
      v106 = L"DsrCmdAzureHelper::GetTenantId failed";
      goto LABEL_96;
    }
  }
  std::wstring::operator=(v429, v413);
  if ( **(_BYTE **)CmdOptions::GetCurrentRef(v151, v150) )
  {
    v152 = v413;
    if ( v415 > 7 )
      v152 = *(unsigned __int16 **)v413;
    wprintf(L"Discover tenant info with Tenant ID %s.\n", v152);
    v155 = (_QWORD *)CmdOptions::GetCurrentRef(v154, v153);
    if ( *(_BYTE *)(*v155 + 12LL) )
    {
      v157 = (_QWORD *)CmdOptions::GetCurrentRef(*v155, v156);
      if ( *(_QWORD *)(*v157 + 184LL) )
      {
        v159 = v413;
        if ( v415 > 7 )
          v159 = *(unsigned __int16 **)v413;
        v160 = CmdOptions::GetCurrentRef(*v157, v158);
        fwprintf_s(*(FILE *const *)(*(_QWORD *)v160 + 184LL), L"Discover tenant info with Tenant ID %s.\n", v159);
      }
    }
  }
  v161 = v413;
  if ( v415 > 7 )
    v161 = *(unsigned __int16 **)v413;
  Logger::TraceInformation(L"Discover tenant info with Tenant ID %s.\n", v161);
  IsDeviceJoined = TenantInfo::Discover(v413);
  if ( (IsDeviceJoined & 0x80000000) == 0 )
  {
    operator delete(Block[0]);
    Block[0] = 0;
    operator delete(Block[1]);
    Block[1] = 0;
    LODWORD(v396[0]) = 0;
    operator delete(v396[1]);
    v396[1] = 0;
    operator delete(v397[0]);
    v397[0] = 0;
    operator delete(v397[1]);
    v397[1] = 0;
    operator delete(v398);
    v398 = 0;
    v176 = v399[0];
    v177 = *(_QWORD *)(*(_QWORD *)v399[0] + 56LL);
    v178 = -1;
    do
      ++v178;
    while ( *(_WORD *)(v177 + 2 * v178) );
    std::wstring::_Assign<unsigned short>(v433, *(const void **)(*(_QWORD *)v399[0] + 56LL), (char *)v178);
    if ( **(_BYTE **)CmdOptions::GetCurrentRef(v180, v179) )
    {
      wprintf(L"Getting MSI token for app %s.\n", v177);
      v183 = (_QWORD *)CmdOptions::GetCurrentRef(v182, v181);
      if ( *(_BYTE *)(*v183 + 12LL) )
      {
        v185 = (_QWORD *)CmdOptions::GetCurrentRef(*v183, v184);
        if ( *(_QWORD *)(*v185 + 184LL) )
        {
          v187 = CmdOptions::GetCurrentRef(v186, *v185);
          fwprintf_s(*(FILE *const *)(*(_QWORD *)v187 + 184LL), L"Getting MSI token for app %s.\n", v177);
        }
      }
    }
    Logger::TraceInformation(L"Getting MSI token for app %s.\n", v177);
    LOBYTE(v188) = v94;
    IsDeviceJoined = DsrCmdAzureHelper::GetMsiAccessToken(v177, v438, v188);
    if ( (IsDeviceJoined & 0x80000000) != 0 )
    {
      if ( **(_BYTE **)CmdOptions::GetCurrentRef(v190, v189) )
      {
        wprintf(
          L"%s: DsrCmdAzureHelper::GetMsiAccessToken failed 0x%08x.\n",
          L"AzureSecureVMJoinOperation",
          IsDeviceJoined);
        v193 = (_QWORD *)CmdOptions::GetCurrentRef(v192, v191);
        if ( *(_BYTE *)(*v193 + 12LL) )
        {
          v195 = (_QWORD *)CmdOptions::GetCurrentRef(*v193, v194);
          if ( *(_QWORD *)(*v195 + 184LL) )
          {
            v197 = CmdOptions::GetCurrentRef(*v195, v196);
            fwprintf_s(
              *(FILE *const *)(*(_QWORD *)v197 + 184LL),
              L"%s: DsrCmdAzureHelper::GetMsiAccessToken failed 0x%08x.\n",
              L"AzureSecureVMJoinOperation",
              IsDeviceJoined);
          }
        }
      }
      Logger::TraceError(
        L"%s: DsrCmdAzureHelper::GetMsiAccessToken failed 0x%08x.\n",
        L"AzureSecureVMJoinOperation",
        IsDeviceJoined);
      std::wstring::_Assign<unsigned short>(v432, L"DsrCmdAzureHelper::GetMsiAccessToken", (char *)0x24);
      v198 = 43;
      v199 = L"DsrCmdAzureHelper::GetMsiAccessToken failed";
LABEL_167:
      std::wstring::_Assign<unsigned short>((char **)v430, v199, (char *)v198);
      v6 = 0;
      v10 = v392;
      goto LABEL_34;
    }
    if ( **(_BYTE **)CmdOptions::GetCurrentRef(v190, v189) )
    {
      wprintf(L"Starting join process with MSI credential.\n");
      v202 = (_QWORD *)CmdOptions::GetCurrentRef(v201, v200);
      if ( *(_BYTE *)(*v202 + 12LL) )
      {
        v204 = (_QWORD *)CmdOptions::GetCurrentRef(*v202, v203);
        if ( *(_QWORD *)(*v204 + 184LL) )
        {
          v206 = CmdOptions::GetCurrentRef(v205, *v204);
          fwprintf_s(*(FILE *const *)(*(_QWORD *)v206 + 184LL), L"Starting join process with MSI credential.\n");
        }
      }
    }
    Logger::TraceInformation(L"Starting join process with MSI credential.\n");
    v207 = v422;
    if ( v423 > 7 )
      v207 = (_QWORD *)v422[0];
    v208 = v438;
    if ( v438[3] > 7u )
      v208 = (_QWORD *)v438[0];
    v209 = (_QWORD **)std::shared_ptr<TenantInfo>::shared_ptr<TenantInfo>(Src, v399, v207, v208, v388);
    IsDeviceJoined = DsrCmdDeviceEnroller::AutoEnroll((DsrCmdDeviceEnroller *)v439, 0xCu, v209, v211, v210, Block);
    if ( (IsDeviceJoined & 0x80000000) != 0 )
    {
      if ( **(_BYTE **)CmdOptions::GetCurrentRef(v213, v212) )
      {
        wprintf(L"%s: DeviceEnroller::AutoEnroll failed 0x%08x.\n", L"AzureSecureVMJoinOperation", IsDeviceJoined);
        v216 = (_QWORD *)CmdOptions::GetCurrentRef(v215, v214);
        if ( *(_BYTE *)(*v216 + 12LL) )
        {
          v218 = (_QWORD *)CmdOptions::GetCurrentRef(*v216, v217);
          if ( *(_QWORD *)(*v218 + 184LL) )
          {
            v220 = CmdOptions::GetCurrentRef(*v218, v219);
            fwprintf_s(
              *(FILE *const *)(*(_QWORD *)v220 + 184LL),
              L"%s: DeviceEnroller::AutoEnroll failed 0x%08x.\n",
              L"AzureSecureVMJoinOperation",
              IsDeviceJoined);
          }
        }
      }
      Logger::TraceError(
        L"%s: DeviceEnroller::AutoEnroll failed 0x%08x.\n",
        L"AzureSecureVMJoinOperation",
        IsDeviceJoined);
      std::wstring::_Assign<unsigned short>(v432, L"DeviceEnroller::AutoEnroll", (char *)0x1A);
      v198 = 33;
      v199 = L"DeviceEnroller::AutoEnroll failed";
      goto LABEL_167;
    }
    Logger::WriteDsRegCmdAzureSecureVMJoinSuccessEvent();
    if ( !a2 )
    {
      v6 = 0;
LABEL_358:
      IsDeviceJoined = 0;
      v10 = v392;
      v47 = (unsigned int)v391;
      goto LABEL_35;
    }
    std::wstring::wstring((__int64)v428);
    std::wstring::wstring((__int64)Src);
    if ( *((_QWORD *)a3 + 2) )
    {
      if ( *((_QWORD *)a3 + 3) <= 7u )
        v221 = a3;
      else
        v221 = *(const wchar_t **)a3;
    }
    else
    {
      v221 = L"N/A";
    }
    std::wstring::wstring((__int64)v416, (__int64)v221);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v408 = 20;
    v409 = _mm_load_si128((const __m128i *)&_xmm);
    v222 = v416;
    if ( v417 > 7 )
      v222 = (unsigned __int16 **)v416[0];
    v223 = -1;
    do
      ++v223;
    while ( *((_WORD *)v222 + v223) );
    std::wstring::_Assign<unsigned short>(v435, v222, (char *)v223);
    if ( **(_BYTE **)CmdOptions::GetCurrentRef(v225, v224) )
    {
      v226 = v416;
      if ( v417 > 7 )
        v226 = (unsigned __int16 **)v416[0];
      wprintf(L"Starting MDM URLs discovery (MDM app ID is: %s).\n", v226);
      v229 = (_QWORD *)CmdOptions::GetCurrentRef(v228, v227);
      if ( *(_BYTE *)(*v229 + 12LL) )
      {
        v231 = (_QWORD *)CmdOptions::GetCurrentRef(*v229, v230);
        if ( *(_QWORD *)(*v231 + 184LL) )
        {
          v233 = v416;
          if ( v417 > 7 )
            v233 = (unsigned __int16 **)v416[0];
          v234 = CmdOptions::GetCurrentRef(*v231, v232);
          fwprintf_s(
            *(FILE *const *)(*(_QWORD *)v234 + 184LL),
            L"Starting MDM URLs discovery (MDM app ID is: %s).\n",
            v233);
        }
      }
    }
    v235 = v416;
    if ( v417 > 7 )
      v235 = (unsigned __int16 **)v416[0];
    Logger::TraceInformation(L"Starting MDM URLs discovery (MDM app ID is: %s).\n", v235);
    v6 = v390;
    v236 = v392;
    do
    {
      if ( *((_QWORD *)a3 + 2) )
      {
        if ( *((_QWORD *)a3 + 3) <= 7u )
          LODWORD(v237) = (_DWORD)a3;
        else
          v237 = *(const wchar_t **)a3;
      }
      else
      {
        LODWORD(v237) = 0;
      }
      IsDeviceJoined = DsrCmdDeviceEnroller::GetDeviceOnlyWamToken(
                         (int)v439,
                         v177,
                         (int)v237,
                         0,
                         (__int64)v418,
                         (__int64)v428,
                         Src);
      if ( (IsDeviceJoined & 0x80000000) == 0 )
        break;
      if ( **(_BYTE **)CmdOptions::GetCurrentRef(v239, v238) )
      {
        v240 = Src;
        if ( v412 > 7 )
          v240 = (unsigned __int16 **)Src[0];
        wprintf(
          L"%s: Discovery of MDM URLs (DeviceEnroller::GetDeviceOnlyWamToken) failed with error 0x%08x. AAD logs may conta"
           "in more details on the failure. Additional information: %s\n",
          L"AzureSecureVMJoinOperation",
          IsDeviceJoined,
          v240);
        v243 = (_QWORD *)CmdOptions::GetCurrentRef(v242, v241);
        if ( *(_BYTE *)(*v243 + 12LL) )
        {
          v245 = (_QWORD *)CmdOptions::GetCurrentRef(*v243, v244);
          if ( *(_QWORD *)(*v245 + 184LL) )
          {
            v247 = Src;
            if ( v412 > 7 )
              v247 = (unsigned __int16 **)Src[0];
            v248 = CmdOptions::GetCurrentRef(*v245, v246);
            fwprintf_s(
              *(FILE *const *)(*(_QWORD *)v248 + 184LL),
              L"%s: Discovery of MDM URLs (DeviceEnroller::GetDeviceOnlyWamToken) failed with error 0x%08x. AAD logs may c"
               "ontain more details on the failure. Additional information: %s\n",
              L"AzureSecureVMJoinOperation",
              IsDeviceJoined,
              v247);
          }
        }
      }
      v249 = Src;
      if ( v412 > 7 )
        v249 = (unsigned __int16 **)Src[0];
      Logger::TraceError(
        L"%s: Discovery of MDM URLs (DeviceEnroller::GetDeviceOnlyWamToken) failed with error 0x%08x. AAD logs may contain"
         " more details on the failure. Additional information: %s\n",
        L"AzureSecureVMJoinOperation",
        IsDeviceJoined,
        v249);
      std::wstring::_Assign<unsigned short>(
        v432,
        L"DeviceEnroller::GetDeviceOnlyWamToken(MDM_URL_Discovery)",
        (char *)0x38);
      std::wstring::_Assign<unsigned short>(
        (char **)v430,
        L"DeviceEnroller::GetDeviceOnlyWamToken(MDM_URL_Discovery) failed",
        (char *)0x3F);
      if ( IsDeviceJoined != -2145648528 )
      {
        v275 = (const unsigned __int16 *)Src;
        if ( v412 > 7 )
          v275 = Src[0];
        Logger::WriteDsRegCmdAzureSecureVMMDMUrlDiscoveryFailedEvent(IsDeviceJoined, v236, v275);
LABEL_247:
        std::wstring::_Tidy_deallocate((__int64)v416);
        std::wstring::_Tidy_deallocate((__int64)Src);
LABEL_326:
        v10 = v392;
LABEL_327:
        std::wstring::_Tidy_deallocate((__int64)v428);
        if ( **(_BYTE **)CmdOptions::GetCurrentRef(v354, v353) )
        {
          wprintf(L"Rolling back device join.\n");
          v357 = (_QWORD *)CmdOptions::GetCurrentRef(v356, v355);
          if ( *(_BYTE *)(*v357 + 12LL) )
          {
            v359 = (_QWORD *)CmdOptions::GetCurrentRef(*v357, v358);
            if ( *(_QWORD *)(*v359 + 184LL) )
            {
              v361 = CmdOptions::GetCurrentRef(v360, *v359);
              fwprintf_s(*(FILE *const *)(*(_QWORD *)v361 + 184LL), L"Rolling back device join.\n");
            }
          }
        }
        Logger::TraceInformation(L"Rolling back device join.\n");
        v362 = (const unsigned __int16 *)v418;
        if ( v419 > 7 )
          v362 = v418[0];
        Logger::WriteDsRegCmdAzureSecureVMMDMEnrollFailedEvent(v362);
        operator delete(Block[0]);
        Block[0] = 0;
        operator delete(Block[1]);
        Block[1] = 0;
        LODWORD(v396[0]) = 0;
        operator delete(v396[1]);
        v396[1] = 0;
        operator delete(v397[0]);
        v397[0] = 0;
        operator delete(v397[1]);
        v397[1] = 0;
        operator delete(v398);
        v398 = 0;
        v47 = DsrCmdDeviceEnroller::Leave((DsrCmdDeviceEnroller *)v439, 0, 0);
        if ( (v47 & 0x80000000) == 0 )
        {
          if ( **(_BYTE **)CmdOptions::GetCurrentRef(v364, v363) )
          {
            wprintf(L"Device successfully unjoined from Azure AD.\n");
            v375 = (_QWORD *)CmdOptions::GetCurrentRef(v374, v373);
            if ( *(_BYTE *)(*v375 + 12LL) )
            {
              v377 = (_QWORD *)CmdOptions::GetCurrentRef(*v375, v376);
              if ( *(_QWORD *)(*v377 + 184LL) )
              {
                v379 = CmdOptions::GetCurrentRef(v378, *v377);
                fwprintf_s(*(FILE *const *)(*(_QWORD *)v379 + 184LL), L"Device successfully unjoined from Azure AD.\n");
              }
            }
          }
          Logger::TraceInformation(L"Device successfully unjoined from Azure AD.\n");
        }
        else
        {
          if ( **(_BYTE **)CmdOptions::GetCurrentRef(v364, v363) )
          {
            wprintf(
              L"WARNING! Device unjoin from Azure AD failed with error 0x%08x. The device may be in an inconsistent state!\n",
              v47);
            v367 = (_QWORD *)CmdOptions::GetCurrentRef(v366, v365);
            if ( *(_BYTE *)(*v367 + 12LL) )
            {
              v369 = (_QWORD *)CmdOptions::GetCurrentRef(*v367, v368);
              if ( *(_QWORD *)(*v369 + 184LL) )
              {
                v371 = CmdOptions::GetCurrentRef(v370, *v369);
                fwprintf_s(
                  *(FILE *const *)(*(_QWORD *)v371 + 184LL),
                  L"WARNING! Device unjoin from Azure AD failed with error 0x%08x. The device may be in an inconsistent state!\n",
                  v47);
              }
            }
          }
          Logger::TraceInformation(
            L"WARNING! Device unjoin from Azure AD failed with error 0x%08x. The device may be in an inconsistent state!\n",
            v47);
        }
        goto LABEL_35;
      }
      if ( v6 >= 9 )
      {
        Logger::WriteDsRegCmdAzureSecureVMAllMDMUrlDiscoveryAttemptsFailedEvent();
        IsDeviceJoined = -2145648522;
        goto LABEL_247;
      }
      v250 = (const unsigned __int16 *)Src;
      if ( v412 > 7 )
        v250 = Src[0];
      Logger::WriteDsRegCmdAzureSecureVMMDMUrlDiscoveryAttemptFailedEvent(v236, v250);
      if ( **(_BYTE **)CmdOptions::GetCurrentRef(v252, v251) )
      {
        v253 = si128.m128i_u32[v6];
        wprintf(L"%s: Retrying in %d second(s)...\n", L"AzureSecureVMJoinOperation", v253);
        v256 = (_QWORD *)CmdOptions::GetCurrentRef(v255, v254);
        if ( *(_BYTE *)(*v256 + 12LL) )
        {
          v258 = (_QWORD *)CmdOptions::GetCurrentRef(*v256, v257);
          if ( *(_QWORD *)(*v258 + 184LL) )
          {
            v260 = CmdOptions::GetCurrentRef(*v258, v259);
            fwprintf_s(
              *(FILE *const *)(*(_QWORD *)v260 + 184LL),
              L"%s: Retrying in %d second(s)...\n",
              L"AzureSecureVMJoinOperation",
              v253);
          }
        }
      }
      v261 = si128.m128i_u32[v6];
      Logger::TraceError(L"%s: Retrying in %d second(s)...\n", L"AzureSecureVMJoinOperation", v261);
      Sleep(1000 * v261);
      ++v6;
    }
    while ( v6 <= 9 );
    if ( !v418[2] )
    {
      v262 = (const unsigned __int16 *)v416;
      if ( v417 > 7 )
        v262 = v416[0];
      v10 = v236;
      Logger::WriteDsRegCmdAzureSecureVMNoMDMUrlsDiscoveredEvent(v236, v262);
      if ( **(_BYTE **)CmdOptions::GetCurrentRef(v264, v263) )
      {
        v265 = v416;
        if ( v417 > 7 )
          v265 = (unsigned __int16 **)v416[0];
        wprintf(
          L"%s: Discovery of MDM URLs failed (no MDM URLs retruned by the AAD server). Verify MDM configuration in the ten"
           "ant is correct and/or specified MDM app ID (%s) is correct and it's successfully resolved by AAD server\n",
          L"AzureSecureVMJoinOperation",
          v265);
        v268 = (_QWORD *)CmdOptions::GetCurrentRef(v267, v266);
        if ( *(_BYTE *)(*v268 + 12LL) )
        {
          v270 = (_QWORD *)CmdOptions::GetCurrentRef(*v268, v269);
          if ( *(_QWORD *)(*v270 + 184LL) )
          {
            v272 = v416;
            if ( v417 > 7 )
              v272 = (unsigned __int16 **)v416[0];
            v273 = CmdOptions::GetCurrentRef(*v270, v271);
            fwprintf_s(
              *(FILE *const *)(*(_QWORD *)v273 + 184LL),
              L"%s: Discovery of MDM URLs failed (no MDM URLs retruned by the AAD server). Verify MDM configuration in the"
               " tenant is correct and/or specified MDM app ID (%s) is correct and it's successfully resolved by AAD server\n",
              L"AzureSecureVMJoinOperation",
              v272);
          }
        }
      }
      v274 = v416;
      if ( v417 > 7 )
        v274 = (unsigned __int16 **)v416[0];
      Logger::TraceError(
        L"%s: Discovery of MDM URLs failed (no MDM URLs retruned by the AAD server). Verify MDM configuration in the tenan"
         "t is correct and/or specified MDM app ID (%s) is correct and it's successfully resolved by AAD server\n",
        L"AzureSecureVMJoinOperation",
        v274);
      std::wstring::_Assign<unsigned short>(
        v432,
        L"DeviceEnroller::GetDeviceOnlyWamToken(MDM_URL_Discovery)",
        (char *)0x38);
      std::wstring::_Assign<unsigned short>(
        (char **)v430,
        L"DeviceEnroller::GetDeviceOnlyWamToken(MDM_URL_Discovery) failed",
        (char *)0x3F);
      IsDeviceJoined = -2145648526;
LABEL_242:
      std::wstring::_Tidy_deallocate((__int64)v416);
      std::wstring::_Tidy_deallocate((__int64)Src);
      goto LABEL_327;
    }
    if ( **(_BYTE **)CmdOptions::GetCurrentRef(v239, v238) )
    {
      v276 = v418;
      if ( v419 > 7 )
        v276 = (unsigned __int16 **)v418[0];
      wprintf(L"MDM Enrollment URL: %s\n", v276);
      v279 = (_QWORD *)CmdOptions::GetCurrentRef(v278, v277);
      if ( *(_BYTE *)(*v279 + 12LL) )
      {
        v281 = (_QWORD *)CmdOptions::GetCurrentRef(*v279, v280);
        if ( *(_QWORD *)(*v281 + 184LL) )
        {
          v283 = v418;
          if ( v419 > 7 )
            v283 = (unsigned __int16 **)v418[0];
          v284 = CmdOptions::GetCurrentRef(*v281, v282);
          fwprintf_s(*(FILE *const *)(*(_QWORD *)v284 + 184LL), L"MDM Enrollment URL: %s\n", v283);
        }
      }
    }
    v285 = v418;
    if ( v419 > 7 )
      v285 = (unsigned __int16 **)v418[0];
    Logger::TraceInformation(L"MDM Enrollment URL: %s\n", v285);
    if ( v419 <= 7 )
    {
      v287 = v418;
      v286 = v418;
    }
    else
    {
      v286 = (unsigned __int16 **)v418[0];
      if ( !v418[0] )
      {
LABEL_268:
        v291 = -1;
LABEL_269:
        std::wstring::wstring(v420, v418);
        std::wstring::wstring((__int64)v437);
        if ( v291 > 0 )
        {
          v294 = std::wstring::wstring(v442, v418, 0, v291 + 1);
          v295 = std::operator+<unsigned short>(v441, v294, L"/");
          std::wstring::operator=((__int64)v420, v295);
          std::wstring::_Tidy_deallocate((__int64)v441);
          std::wstring::_Tidy_deallocate((__int64)v442);
        }
        if ( **(_BYTE **)CmdOptions::GetCurrentRef(v293, v292) )
        {
          v296 = v420;
          if ( v421 > 7 )
            v296 = *(int **)v420;
          wprintf(L"MDM resource ID: %s\n", v296);
          v299 = (_QWORD *)CmdOptions::GetCurrentRef(v298, v297);
          if ( *(_BYTE *)(*v299 + 12LL) )
          {
            v301 = (_QWORD *)CmdOptions::GetCurrentRef(*v299, v300);
            if ( *(_QWORD *)(*v301 + 184LL) )
            {
              v303 = v420;
              if ( v421 > 7 )
                v303 = *(int **)v420;
              v304 = CmdOptions::GetCurrentRef(*v301, v302);
              fwprintf_s(*(FILE *const *)(*(_QWORD *)v304 + 184LL), L"MDM resource ID: %s\n", v303);
            }
          }
        }
        v305 = v420;
        if ( v421 > 7 )
          v305 = *(int **)v420;
        Logger::TraceInformation(L"MDM resource ID: %s\n", v305);
        if ( v6 <= 9 )
        {
          while ( 1 )
          {
            v308 = v420;
            if ( v421 > 7 )
              LODWORD(v308) = v420[0];
            IsDeviceJoined = DsrCmdDeviceEnroller::GetDeviceOnlyWamToken(
                               (int)v439,
                               (int)v308,
                               0,
                               1,
                               (__int64)v437,
                               (__int64)v428,
                               Src);
            if ( (IsDeviceJoined & 0x80000000) == 0 )
              goto LABEL_304;
            if ( **(_BYTE **)CmdOptions::GetCurrentRef(v307, v306) )
            {
              v309 = Src;
              if ( v412 > 7 )
                v309 = (unsigned __int16 **)Src[0];
              wprintf(
                L"%s: Getting token for MDM enrollment (DeviceEnroller::GetDeviceOnlyWamToken) failed with error 0x%08x. A"
                 "AD logs may contain more details on the failure. Additional information: %s\n",
                L"AzureSecureVMJoinOperation",
                IsDeviceJoined,
                v309);
              v312 = (_QWORD *)CmdOptions::GetCurrentRef(v311, v310);
              if ( *(_BYTE *)(*v312 + 12LL) )
              {
                v314 = (_QWORD *)CmdOptions::GetCurrentRef(*v312, v313);
                if ( *(_QWORD *)(*v314 + 184LL) )
                {
                  v316 = Src;
                  if ( v412 > 7 )
                    v316 = (unsigned __int16 **)Src[0];
                  v317 = CmdOptions::GetCurrentRef(*v314, v315);
                  fwprintf_s(
                    *(FILE *const *)(*(_QWORD *)v317 + 184LL),
                    L"%s: Getting token for MDM enrollment (DeviceEnroller::GetDeviceOnlyWamToken) failed with error 0x%08"
                     "x. AAD logs may contain more details on the failure. Additional information: %s\n",
                    L"AzureSecureVMJoinOperation",
                    IsDeviceJoined,
                    v316);
                }
              }
            }
            v318 = Src;
            if ( v412 > 7 )
              v318 = (unsigned __int16 **)Src[0];
            Logger::TraceError(
              L"%s: Getting token for MDM enrollment (DeviceEnroller::GetDeviceOnlyWamToken) failed with error 0x%08x. AAD"
               " logs may contain more details on the failure. Additional information: %s\n",
              L"AzureSecureVMJoinOperation",
              IsDeviceJoined,
              v318);
            std::wstring::_Assign<unsigned short>(
              v432,
              L"DeviceEnroller::GetDeviceOnlyWamToken(MMDM_Token)",
              (char *)0x31);
            std::wstring::_Assign<unsigned short>(
              (char **)v430,
              L"DeviceEnroller::GetDeviceOnlyWamToken(MMDM_Token) failed",
              (char *)0x38);
            if ( IsDeviceJoined != -2145648528 )
              break;
            if ( v6 >= 9 )
            {
              Logger::WriteDsRegCmdAzureSecureVMAllMDMTokenRequestAttemptsFailedEvent();
              IsDeviceJoined = -2145648516;
              v10 = v392;
LABEL_344:
              std::wstring::_Tidy_deallocate((__int64)v437);
              std::wstring::_Tidy_deallocate((__int64)v420);
              goto LABEL_242;
            }
            v319 = (const unsigned __int16 *)Src;
            if ( v412 > 7 )
              v319 = Src[0];
            Logger::WriteDsRegCmdAzureSecureVMMDMTokenRequestAttemptFailedEvent(v236, v319);
            if ( **(_BYTE **)CmdOptions::GetCurrentRef(v321, v320) )
            {
              v322 = si128.m128i_u32[v6];
              wprintf(L"%s: Retrying in %d second(s)...\n", L"AzureSecureVMJoinOperation", v322);
              v325 = (_QWORD *)CmdOptions::GetCurrentRef(v324, v323);
              if ( *(_BYTE *)(*v325 + 12LL) )
              {
                v327 = (_QWORD *)CmdOptions::GetCurrentRef(*v325, v326);
                if ( *(_QWORD *)(*v327 + 184LL) )
                {
                  v329 = CmdOptions::GetCurrentRef(*v327, v328);
                  fwprintf_s(
                    *(FILE *const *)(*(_QWORD *)v329 + 184LL),
                    L"%s: Retrying in %d second(s)...\n",
                    L"AzureSecureVMJoinOperation",
                    v322);
                }
              }
            }
            v330 = si128.m128i_u32[v6];
            Logger::TraceError(L"%s: Retrying in %d second(s)...\n", L"AzureSecureVMJoinOperation", v330);
            Sleep(1000 * v330);
            if ( ++v6 > 9 )
              goto LABEL_304;
          }
          v372 = (const unsigned __int16 *)Src;
          if ( v412 > 7 )
            v372 = Src[0];
          v10 = v392;
          Logger::WriteDsRegCmdAzureSecureVMMDMTokenRequestFailedEvent(IsDeviceJoined, v392, v372);
          goto LABEL_344;
        }
LABEL_304:
        if ( **(_BYTE **)CmdOptions::GetCurrentRef(v307, v306) )
        {
          wprintf(L"Access token for MDM enrollment acquired successfully.\nStarting MDM enrollment...\n");
          v333 = (_QWORD *)CmdOptions::GetCurrentRef(v332, v331);
          if ( *(_BYTE *)(*v333 + 12LL) )
          {
            v335 = (_QWORD *)CmdOptions::GetCurrentRef(*v333, v334);
            if ( *(_QWORD *)(*v335 + 184LL) )
            {
              v337 = CmdOptions::GetCurrentRef(v336, *v335);
              fwprintf_s(
                *(FILE *const *)(*(_QWORD *)v337 + 184LL),
                L"Access token for MDM enrollment acquired successfully.\nStarting MDM enrollment...\n");
            }
          }
        }
        Logger::TraceInformation(L"Access token for MDM enrollment acquired successfully.\nStarting MDM enrollment...\n");
        v338 = v428;
        if ( v428[3] > 7uLL )
          v338 = (__int64 *)v428[0];
        v339 = v420;
        if ( v421 > 7 )
          v339 = *(int **)v420;
        v340 = v418;
        if ( v419 > 7 )
          v340 = (unsigned __int16 **)v418[0];
        IsDeviceJoined = DsrCmdDeviceEnroller::EnrollToMdm(
                           v439,
                           *(_QWORD *)(*(_QWORD *)v176 + 176LL),
                           v340,
                           v339,
                           v338,
                           Src);
        if ( (IsDeviceJoined & 0x80000000) != 0 )
        {
          if ( **(_BYTE **)CmdOptions::GetCurrentRef(v342, v341) )
          {
            v343 = Src;
            if ( v412 > 7 )
              v343 = (unsigned __int16 **)Src[0];
            wprintf(
              L"%s: MDM enrollment (DeviceEnroller::EnrollToMdm) failed with error 0x%08x. MDM logs may contain more detai"
               "ls on the failure. Additional information: %s\n",
              L"AzureSecureVMJoinOperation",
              IsDeviceJoined,
              v343);
            v346 = (_QWORD *)CmdOptions::GetCurrentRef(v345, v344);
            if ( *(_BYTE *)(*v346 + 12LL) )
            {
              v348 = (_QWORD *)CmdOptions::GetCurrentRef(*v346, v347);
              if ( *(_QWORD *)(*v348 + 184LL) )
              {
                v350 = Src;
                if ( v412 > 7 )
                  v350 = (unsigned __int16 **)Src[0];
                v351 = CmdOptions::GetCurrentRef(*v348, v349);
                fwprintf_s(
                  *(FILE *const *)(*(_QWORD *)v351 + 184LL),
                  L"%s: MDM enrollment (DeviceEnroller::EnrollToMdm) failed with error 0x%08x. MDM logs may contain more d"
                   "etails on the failure. Additional information: %s\n",
                  L"AzureSecureVMJoinOperation",
                  IsDeviceJoined,
                  v350);
              }
            }
          }
          v352 = Src;
          if ( v412 > 7 )
            v352 = (unsigned __int16 **)Src[0];
          Logger::TraceError(
            L"%s: MDM enrollment (DeviceEnroller::EnrollToMdm) failed with error 0x%08x. MDM logs may contain more details"
             " on the failure. Additional information: %s\n",
            L"AzureSecureVMJoinOperation",
            IsDeviceJoined,
            v352);
          std::wstring::_Assign<unsigned short>(v432, L"DeviceEnroller::EnrollToMdm()", (char *)0x1D);
          std::wstring::_Assign<unsigned short>((char **)v430, L"DeviceEnroller::EnrollToMdm() failed", (char *)0x24);
          std::wstring::_Tidy_deallocate((__int64)v437);
          std::wstring::_Tidy_deallocate((__int64)v420);
          std::wstring::_Tidy_deallocate((__int64)v416);
          std::wstring::_Tidy_deallocate((__int64)Src);
          goto LABEL_326;
        }
        if ( **(_BYTE **)CmdOptions::GetCurrentRef(v342, v341) )
        {
          wprintf(L"MDM enrollment succeeded.\n");
          v382 = (_QWORD *)CmdOptions::GetCurrentRef(v381, v380);
          if ( *(_BYTE *)(*v382 + 12LL) )
          {
            v384 = (_QWORD *)CmdOptions::GetCurrentRef(*v382, v383);
            if ( *(_QWORD *)(*v384 + 184LL) )
            {
              v386 = CmdOptions::GetCurrentRef(v385, *v384);
              fwprintf_s(*(FILE *const *)(*(_QWORD *)v386 + 184LL), L"MDM enrollment succeeded.\n");
            }
          }
        }
        Logger::TraceInformation(L"MDM enrollment succeeded.\n");
        v387 = (const unsigned __int16 *)v418;
        if ( v419 > 7 )
          v387 = v418[0];
        Logger::WriteDsRegCmdAzureSecureVMMDMEnrollSuccessEvent(v387);
        std::wstring::_Tidy_deallocate((__int64)v437);
        std::wstring::_Tidy_deallocate((__int64)v420);
        std::wstring::_Tidy_deallocate((__int64)v416);
        std::wstring::_Tidy_deallocate((__int64)Src);
        std::wstring::_Tidy_deallocate((__int64)v428);
        goto LABEL_358;
      }
      v287 = (unsigned __int16 **)v418[0];
    }
    v288 = *(_WORD *)v287;
    if ( v288 )
    {
      v289 = 0;
      v290 = 0;
      do
      {
        if ( v288 == 47 && ++v290 == 3 )
        {
          v291 = v289 - 1;
          goto LABEL_269;
        }
        v291 = v289++;
        v286 = (unsigned __int16 **)((char *)v286 + 2);
        v288 = *(_WORD *)v286;
      }
      while ( *(_WORD *)v286 );
      if ( v290 == 2 )
        goto LABEL_269;
    }
    goto LABEL_268;
  }
  if ( **(_BYTE **)CmdOptions::GetCurrentRef(v163, v162) )
  {
    v164 = v413;
    if ( v415 > 7 )
      v164 = *(unsigned __int16 **)v413;
    wprintf(
      L"%s: TenantInfo::Discover with tenantId '%s' failed 0x%08x.\n",
      L"AzureSecureVMJoinOperation",
      v164,
      IsDeviceJoined,
      v388);
    v167 = (_QWORD *)CmdOptions::GetCurrentRef(v166, v165);
    if ( *(_BYTE *)(*v167 + 12LL) )
    {
      v169 = (_QWORD *)CmdOptions::GetCurrentRef(*v167, v168);
      if ( *(_QWORD *)(*v169 + 184LL) )
      {
        v171 = v413;
        if ( v415 > 7 )
          v171 = *(unsigned __int16 **)v413;
        v172 = CmdOptions::GetCurrentRef(*v169, v170);
        LODWORD(v388) = IsDeviceJoined;
        fwprintf_s(
          *(FILE *const *)(*(_QWORD *)v172 + 184LL),
          L"%s: TenantInfo::Discover with tenantId '%s' failed 0x%08x.\n",
          L"AzureSecureVMJoinOperation",
          v171,
          v388);
      }
    }
  }
  v173 = v413;
  if ( v415 > 7 )
    v173 = *(unsigned __int16 **)v413;
  Logger::TraceError(
    L"%s: TenantInfo::Discover with tenantId '%s' failed 0x%08x.\n",
    L"AzureSecureVMJoinOperation",
    v173,
    IsDeviceJoined,
    v388);
  std::wstring::_Assign<unsigned short>(v432, L"TenantInfo::Discover", (char *)0x14);
  v174 = std::operator+<unsigned short>(v428, L"TenantInfo::Discover with tenantId ", v413);
  v175 = std::operator+<unsigned short>(v437, v174, L" failed");
  std::wstring::operator=((__int64)v430, v175);
  std::wstring::_Tidy_deallocate((__int64)v437);
  std::wstring::_Tidy_deallocate((__int64)v428);
  v6 = v390;
  v47 = v390;
LABEL_35:
  if ( v425 )
    EventActivityIdControl(4u, &v427);
  v424 = 2;
  if ( (unsigned int)dword_18013D8B8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18013D8B8, 0x400000000000LL) )
  {
    v49 = (unsigned __int16 *)v430;
    if ( v431 > 7 )
      v49 = v430[0];
    v392 = v49;
    v394[0] = v6;
    v50 = v435;
    if ( v435[3] > (char *)7 )
      v50 = (char **)v435[0];
    v391 = v50;
    v51 = v433;
    if ( v433[3] > (char *)7 )
      v51 = (char **)v433[0];
    v400 = v51;
    v52 = v434;
    if ( v434[3] > (char *)7 )
      v52 = (char **)v434[0];
    v401 = v52;
    v53 = v432;
    if ( v432[3] > (char *)7 )
      v53 = (char **)v432[0];
    v402 = v53;
    v54 = v429;
    if ( v429[3] > 7u )
      v54 = (_QWORD *)v429[0];
    v403 = v54;
    v55 = v436;
    if ( v436[3] > (char *)7 )
      v55 = (char **)v436[0];
    v404 = v55;
    v405 = v10;
    v393 = v47;
    v390 = IsDeviceJoined;
    Src[0] = (unsigned __int16 *)50331648;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      (__int64)&dword_18013D8B8,
      (__int64)&byte_18012B587,
      (__int64)&ActivityId,
      v48,
      (__int64)Src,
      (__int64)&v390,
      (__int64)&v393,
      &v405,
      &v404,
      &v403,
      &v402,
      &v401,
      &v400,
      &v391,
      (__int64)v394,
      &v392);
  }
  if ( (IsDeviceJoined & 0x80000000) != 0 )
  {
    String = AzureSecureVMJoinTelemetryInfo::getString(v429, v441);
    v57 = (const unsigned __int16 *)String;
    if ( *(_QWORD *)(String + 24) > 7u )
      v57 = *(const unsigned __int16 **)String;
    v58 = std::operator+<unsigned short>(v442, L"AzureSecureVMJoin-", v432);
    if ( *(_QWORD *)(v58 + 24) > 7u )
      v58 = *(_QWORD *)v58;
    v59 = (const unsigned __int16 *)v430;
    if ( v431 > 7 )
      v59 = v430[0];
    Logger::WriteDsRegCmdJoinFailureEvent(IsDeviceJoined, v59, L"Managed", (const unsigned __int16 *)v58, v57);
    std::wstring::_Tidy_deallocate((__int64)v442);
    std::wstring::_Tidy_deallocate((__int64)v441);
  }
  DsregServerResponse::MoveTo((DsregServerResponse *)Block, v406);
  AzureSecureVMJoinTelemetryInfo::~AzureSecureVMJoinTelemetryInfo((AzureSecureVMJoinTelemetryInfo *)v429);
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjAzureSecureVMJoinTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjAzureSecureVMJoinTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>((__int64)&v424);
  TraceLoggingUnregister_EventUnregister(&dword_18013D8B8);
  DsrCmdDeviceEnroller::~DsrCmdDeviceEnroller((DsrCmdDeviceEnroller *)v439);
  operator delete(Block[0]);
  Block[0] = 0;
  operator delete(Block[1]);
  Block[1] = 0;
  LODWORD(v396[0]) = 0;
  operator delete(v396[1]);
  v396[1] = 0;
  operator delete(v397[0]);
  v397[0] = 0;
  operator delete(v397[1]);
  v397[1] = 0;
  operator delete(v398);
  v398 = 0;
  std::wstring::_Tidy_deallocate((__int64)v418);
  std::wstring::_Tidy_deallocate((__int64)v413);
  std::wstring::_Tidy_deallocate((__int64)v438);
  std::wstring::_Tidy_deallocate((__int64)v422);
  if ( v399[1] )
    std::_Ref_count_base::_Decref(v399[1]);
  return IsDeviceJoined;
}

```

## disassembly

```asm
0x180099424  mov     [rsp-8+arg_8], rbx
0x180099429  push    rbp
0x18009942a  push    rsi
0x18009942b  push    rdi
0x18009942c  push    r12
0x18009942e  push    r13
0x180099430  push    r14
0x180099432  push    r15
0x180099434  lea     rbp, [rsp-300h]
0x18009943c  sub     rsp, 400h
0x180099443  mov     rax, cs:__security_cookie
0x18009944a  xor     rax, rsp
0x18009944d  mov     [rbp+330h+var_40], rax
0x180099454  mov     [rbp+330h+var_310], r9
0x180099458  mov     r15, r8
0x18009945b  mov     r12b, dl
0x18009945e  mov     rdx, rcx
0x180099461  xor     edi, edi
0x180099463  mov     dword ptr [rbp+330h+var_3A8], edi
0x180099466  mov     r14d, edi
0x180099469  mov     [rbp+330h+var_3AC], edi
0x18009946c  xorps   xmm0, xmm0
0x18009946f  movdqu  xmmword ptr [rbp+330h+var_350], xmm0
0x180099474  lea     rcx, [rbp+330h+var_238]
0x18009947b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180099480  nop
0x180099481  lea     rcx, [rbp+330h+var_D0]
0x180099488  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18009948d  nop
0x18009948e  lea     rcx, [rbp+330h+var_2B8]
0x180099492  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180099497  nop
0x180099498  lea     rcx, [rbp+330h+var_278]
0x18009949f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800994a4  nop
0x1800994a5  xorps   xmm1, xmm1
0x1800994a8  xor     eax, eax
0x1800994aa  movups  xmmword ptr [rbp+330h+Block], xmm1
0x1800994ae  movups  xmmword ptr [rbp+330h+var_378], xmm1
0x1800994b2  movups  xmmword ptr [rbp+330h+var_368], xmm1
0x1800994b6  mov     [rbp+330h+var_358], rax
0x1800994ba  lea     rcx, [rbp+330h+var_B0]; this
0x1800994c1  call    ??0DsrCmdDeviceEnroller@@QEAA@XZ; DsrCmdDeviceEnroller::DsrCmdDeviceEnroller(void)
0x1800994c6  nop
0x1800994c7  lea     rsi, cchOriginalDestLength
0x1800994ce  mov     r13, rsi
0x1800994d1  mov     rax, [rbp+330h+var_98]
0x1800994d8  test    rax, rax
0x1800994db  cmovnz  r13, rax
0x1800994df  mov     [rbp+330h+var_3A0], r13
0x1800994e3  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800994e8  mov     rcx, [rax]
0x1800994eb  lea     rbx, aAzuresecurevmj_3; "AzureSecureVMJoinOperation"
0x1800994f2  cmp     [rcx], dil
0x1800994f5  jz      short loc_180099549
0x1800994f7  mov     r8, r13
0x1800994fa  mov     rdx, rbx
0x1800994fd  lea     rcx, aSClientrequest_0; "%s: ClientRequestId: %s\n"
0x180099504  call    wprintf
0x180099509  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18009950e  mov     rcx, [rax]
0x180099511  cmp     [rcx+0Ch], dil
0x180099515  jz      short loc_180099549
0x180099517  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18009951c  mov     rcx, [rax]
0x18009951f  cmp     [rcx+0B8h], rdi
0x180099526  jz      short loc_180099549
0x180099528  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18009952d  mov     rcx, [rax]
0x180099530  mov     r9, r13
0x180099533  mov     r8, rbx
0x180099536  lea     rdx, aSClientrequest_0; "%s: ClientRequestId: %s\n"
0x18009953d  mov     rcx, [rcx+0B8h]; Stream
0x180099544  call    fwprintf_s
0x180099549  mov     r8, r13
0x18009954c  mov     rdx, rbx
0x18009954f  lea     rcx, aSClientrequest_0; "%s: ClientRequestId: %s\n"
0x180099556  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18009955b  lea     rax, g_hcdjAzureSecureVMJoinTraceLoggingProvider
0x180099562  mov     [rbp+330h+var_2E0], rax
0x180099566  lea     rcx, dword_18013D8B8; CallbackContext
0x18009956d  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180099572  nop
0x180099573  mov     [rbp+330h+var_218], edi
0x180099579  mov     [rbp+330h+var_214], dil
0x180099580  lea     rbx, aUndefined; "undefined"
0x180099587  mov     rdx, rbx
0x18009958a  lea     rcx, [rbp+330h+var_1D0]
0x180099591  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180099596  nop
0x180099597  mov     rdx, rbx
0x18009959a  lea     rcx, [rbp+330h+var_1B0]
0x1800995a1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800995a6  nop
0x1800995a7  mov     rdx, rbx
0x1800995aa  lea     rcx, [rbp+330h+var_190]
0x1800995b1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800995b6  nop
0x1800995b7  mov     rdx, rbx
0x1800995ba  lea     rcx, [rbp+330h+var_170]
0x1800995c1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800995c6  nop
0x1800995c7  mov     rdx, rbx
0x1800995ca  lea     rcx, [rbp+330h+var_150]
0x1800995d1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800995d6  nop
0x1800995d7  mov     rdx, rbx
0x1800995da  lea     rcx, [rbp+330h+var_130]
0x1800995e1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800995e6  nop
0x1800995e7  mov     rdx, rbx
0x1800995ea  lea     rcx, [rbp+330h+var_110]
0x1800995f1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800995f6  nop
0x1800995f7  mov     eax, cs:dword_18013D8B8
0x1800995fd  cmp     eax, 5
0x180099600  jbe     short loc_180099665
0x180099602  mov     rdx, 400000000000h
0x18009960c  lea     rcx, dword_18013D8B8
0x180099613  call    _tlgKeywordOn
0x180099618  test    al, al
0x18009961a  jz      short loc_180099665
0x18009961c  lea     rdx, [rbp+330h+ActivityId]; ActivityId
0x180099623  mov     ecx, 3; ControlCode
0x180099628  call    cs:__imp_EventActivityIdControl
0x18009962e  mov     rax, qword ptr [rbp+330h+ActivityId.Data1]
0x180099635  mov     qword ptr [rbp+330h+var_200.Data1], rax
0x18009963c  mov     rax, qword ptr [rbp+330h+ActivityId.Data4]
0x180099643  mov     qword ptr [rbp+330h+var_200.Data4], rax
0x18009964a  lea     rdx, [rbp+330h+var_200]; ActivityId
0x180099651  mov     ecx, 4; ControlCode
0x180099656  call    cs:__imp_EventActivityIdControl
0x18009965c  mov     [rbp+330h+var_214], 1
0x180099663  jmp     short loc_18009966F
0x180099665  xorps   xmm0, xmm0
0x180099668  movups  xmmword ptr [rbp+330h+ActivityId.Data1], xmm0
0x18009966f  mov     [rbp+330h+var_218], 1
0x180099679  mov     eax, cs:dword_18013D8B8
0x18009967f  cmp     eax, 5
0x180099682  jbe     short loc_1800996EC
0x180099684  mov     rdx, 400000000000h
0x18009968e  lea     rcx, dword_18013D8B8
0x180099695  call    _tlgKeywordOn
0x18009969a  test    al, al
0x18009969c  jz      short loc_1800996EC
0x18009969e  mov     qword ptr [rbp+330h+var_390], 3000000h
0x1800996a6  cmp     [rbp+330h+var_214], dil
0x1800996ad  jz      short loc_1800996C6
0x1800996af  lea     rcx, [rbp+330h+var_200]; struct _GUID *
0x1800996b6  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1800996bb  test    al, al
0x1800996bd  lea     r9, [rbp+330h+var_200]
0x1800996c4  jz      short loc_1800996C9
0x1800996c6  mov     r9, rdi
0x1800996c9  lea     rax, [rbp+330h+var_390]
0x1800996cd  mov     [rsp+430h+var_410], rax
0x1800996d2  lea     r8, [rbp+330h+ActivityId]
0x1800996d9  lea     rdx, word_18012B3EE
0x1800996e0  lea     rcx, dword_18013D8B8
0x1800996e7  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x1800996ec  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800996f1  mov     rcx, [rax]
0x1800996f4  lea     rbx, aCheckingDevice; "Checking device join status...\n"
0x1800996fb  cmp     [rcx], dil
0x1800996fe  jz      short loc_18009973E
0x180099700  mov     rcx, rbx; Format
0x180099703  call    wprintf
0x180099708  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18009970d  mov     rcx, [rax]
0x180099710  cmp     [rcx+0Ch], dil
0x180099714  jz      short loc_18009973E
0x180099716  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18009971b  mov     rdx, [rax]
0x18009971e  cmp     [rdx+0B8h], rdi
0x180099725  jz      short loc_18009973E
0x180099727  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18009972c  mov     rcx, [rax]
0x18009972f  mov     rdx, rbx; Format
0x180099732  mov     rcx, [rcx+0B8h]; Stream
0x180099739  call    fwprintf_s
0x18009973e  mov     rcx, rbx; unsigned __int16 *
0x180099741  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x180099746  mov     [rbp+330h+var_398], edi
0x180099749  mov     [rbp+330h+var_390], edi
0x18009974c  mov     [rbp+330h+var_3B0], dil
0x180099750  lea     rdx, [rbp+330h+var_3B0]; bool *
0x180099754  lea     rcx, aArcenabledvm; "ArcEnabledVM"
0x18009975b  call    ?ReadBoolOption@@YAJPEBGPEA_N@Z; ReadBoolOption(ushort const *,bool *)
0x180099760  test    eax, eax
0x180099762  jns     short loc_180099781
0x180099764  mov     r9d, eax
0x180099767  lea     r8, aReadbooloption; "ReadBoolOption"
0x18009976e  lea     rdx, aIsarcdeviceena; "IsArcDeviceEnabled"
0x180099775  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18009977c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180099781  movzx   ebx, [rbp+330h+var_3B0]
0x180099785  lea     rax, aAzureDevice; "Azure device"
0x18009978c  lea     rdx, aArcEnabledDevi; "Arc-Enabled device"
0x180099793  test    ebx, ebx
0x180099795  cmovz   rdx, rax
0x180099799  or      r8, 0FFFFFFFFFFFFFFFFh
0x18009979d  inc     r8
0x1800997a0  cmp     [rdx+r8*2], di
0x1800997a5  jnz     short loc_18009979D
0x1800997a7  lea     rcx, [rbp+330h+var_110]
0x1800997ae  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800997b3  xor     r8d, r8d
0x1800997b6  xor     edx, edx
0x1800997b8  lea     rcx, [rbp+330h+var_398]
0x1800997bc  call    DsrIsDeviceJoinedEx
0x1800997c1  mov     edi, eax
0x1800997c3  xor     eax, eax
0x1800997c5  test    edi, edi
0x1800997c7  jns     loc_180099BB4
0x1800997cd  lea     r8d, [rax+11h]
0x1800997d1  lea     rdx, aDsrisdevicejoi_2; "DsrIsDeviceJoined"
0x1800997d8  lea     rcx, [rbp+330h+var_190]
0x1800997df  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800997e4  mov     r8d, 2Dh ; '-'
0x1800997ea  lea     rdx, aAzuresecurevmj_5; "AzureSecureVMJoin::DsrIsDeviceJoined fa"...
0x1800997f1  lea     rcx, [rbp+330h+var_1B0]
0x1800997f8  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800997fd  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180099802  xor     esi, esi
0x180099804  lea     rbx, aSAzuresecurevm_3; "%s: AzureSecureVMJoin::DsrIsDeviceJoine"...
0x18009980b  mov     rcx, [rax]
0x18009980e  cmp     [rcx], sil
0x180099811  jz      short loc_180099865
0x180099813  mov     r8d, edi
0x180099816  lea     rdx, aAzuresecurevmj_3; "AzureSecureVMJoinOperation"
0x18009981d  mov     rcx, rbx; Format
0x180099820  call    wprintf
0x180099825  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18009982a  mov     rcx, [rax]
0x18009982d  cmp     [rcx+0Ch], sil
0x180099831  jz      short loc_180099865
0x180099833  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180099838  mov     rcx, [rax]
0x18009983b  cmp     [rcx+0B8h], rsi
0x180099842  jz      short loc_180099865
0x180099844  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180099849  mov     rcx, [rax]
0x18009984c  mov     r9d, edi
0x18009984f  lea     r8, aAzuresecurevmj_3; "AzureSecureVMJoinOperation"
0x180099856  mov     rdx, rbx; Format
0x180099859  mov     rcx, [rcx+0B8h]; Stream
0x180099860  call    fwprintf_s
0x180099865  mov     r8d, edi
0x180099868  lea     rdx, aAzuresecurevmj_3; "AzureSecureVMJoinOperation"
0x18009986f  mov     rcx, rbx; unsigned __int16 *
0x180099872  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180099877  mov     ebx, esi
0x180099879  cmp     [rbp+330h+var_214], sil
0x180099880  jz      short loc_180099894
0x180099882  lea     rdx, [rbp+330h+var_200]; ActivityId
0x180099889  mov     ecx, 4; ControlCode
0x18009988e  call    cs:__imp_EventActivityIdControl
0x180099894  mov     [rbp+330h+var_218], 2
0x18009989e  mov     eax, cs:dword_18013D8B8
0x1800998a4  cmp     eax, 5
0x1800998a7  jbe     loc_180099A24
0x1800998ad  mov     rdx, 400000000000h
0x1800998b7  lea     rcx, dword_18013D8B8
0x1800998be  call    _tlgKeywordOn
0x1800998c3  test    al, al
0x1800998c5  jz      loc_180099A24
0x1800998cb  lea     rax, [rbp+330h+var_1B0]
0x1800998d2  cmp     [rbp+330h+var_198], 7
0x1800998da  cmova   rax, [rbp+330h+var_1B0]
0x1800998e2  mov     [rbp+330h+var_3A0], rax
0x1800998e6  mov     [rbp+330h+var_390], r14d
0x1800998ea  lea     rax, [rbp+330h+var_130]
0x1800998f1  cmp     [rbp+330h+var_118], 7
0x1800998f9  cmova   rax, [rbp+330h+var_130]
0x180099901  mov     [rbp+330h+var_3A8], rax
0x180099905  lea     rax, [rbp+330h+var_170]
0x18009990c  cmp     [rbp+330h+var_158], 7
0x180099914  cmova   rax, [rbp+330h+var_170]
0x18009991c  mov     [rbp+330h+var_340], rax
0x180099920  lea     rax, [rbp+330h+var_150]
0x180099927  cmp     [rbp+330h+var_138], 7
0x18009992f  cmova   rax, [rbp+330h+var_150]
0x180099937  mov     [rbp+330h+var_338], rax
0x18009993b  lea     rax, [rbp+330h+var_190]
0x180099942  cmp     [rbp+330h+var_178], 7
0x18009994a  cmova   rax, [rbp+330h+var_190]
0x180099952  mov     [rbp+330h+var_330], rax
0x180099956  lea     rax, [rbp+330h+var_1D0]
0x18009995d  cmp     [rbp+330h+var_1B8], 7
0x180099965  cmova   rax, [rbp+330h+var_1D0]
0x18009996d  mov     [rbp+330h+var_328], rax
0x180099971  lea     rax, [rbp+330h+var_110]
0x180099978  cmp     [rbp+330h+var_F8], 7
0x180099980  cmova   rax, [rbp+330h+var_110]
0x180099988  mov     [rbp+330h+var_320], rax
0x18009998c  mov     [rbp+330h+var_318], r13
0x180099990  mov     [rbp+330h+var_398], ebx
0x180099993  mov     [rbp+330h+var_3AC], edi
0x180099996  mov     [rbp+330h+var_2D8], 3000000h
0x18009999e  lea     rax, [rbp+330h+var_3A0]
  ... truncated ...
```
