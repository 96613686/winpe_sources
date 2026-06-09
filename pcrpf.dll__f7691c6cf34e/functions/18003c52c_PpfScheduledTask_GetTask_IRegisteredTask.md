# PpfScheduledTask::GetTask(IRegisteredTask * *)

- ea: `0x18003c52c`
- end: `0x18003fb2c`
- name: `?GetTask@PpfScheduledTask@@AEAAJPEAPEAUIRegisteredTask@@@Z`
- size: `13824`
- prototype: `__int64 __fastcall(const unsigned __int16 **this, struct IRegisteredTask **)`
- caller_count: `4`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003c02c`
- `0x18003c280`
- `0x18003fb34`
- `0x18003fcac`

## callees

- `0x180003270`
- `0x18000367c`
- `0x180003cf0`
- `0x180009c64`
- `0x18000a66c`
- `0x18002d5ec`
- `0x18003be70`
- `0x18003bf88`
- `0x18003c52c`
- `0x180054854`
- `0x180059010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18003c7a3`
- `OLEAUT32!__imp_SysAllocString` at `0x18003c83e`
- `OLEAUT32!__imp_SysAllocString` at `0x18003c915`
- `OLEAUT32!__imp_SysAllocString` at `0x18003c961`
- `OLEAUT32!__imp_SysAllocString` at `0x18003ccdb`
- `OLEAUT32!__imp_SysAllocString` at `0x18003cdd1`
- `OLEAUT32!__imp_SysAllocString` at `0x18003cff3`
- `OLEAUT32!__imp_SysAllocString` at `0x18003c7a3`
- `OLEAUT32!__imp_SysAllocString` at `0x18003c83e`
- `OLEAUT32!__imp_SysAllocString` at `0x18003c915`
- `OLEAUT32!__imp_SysAllocString` at `0x18003c961`
- `OLEAUT32!__imp_SysAllocString` at `0x18003ccdb`
- `OLEAUT32!__imp_SysAllocString` at `0x18003cdd1`
- `OLEAUT32!__imp_SysAllocString` at `0x18003cff3`
- `OLEAUT32!__imp_VariantInit` at `0x18003c60e`
- `OLEAUT32!__imp_VariantInit` at `0x18003c62a`
- `OLEAUT32!__imp_VariantInit` at `0x18003c646`
- `OLEAUT32!__imp_VariantInit` at `0x18003c660`
- `OLEAUT32!__imp_VariantInit` at `0x18003f305`
- `OLEAUT32!__imp_VariantInit` at `0x18003f31f`
- `OLEAUT32!__imp_VariantInit` at `0x18003f33b`
- `OLEAUT32!__imp_VariantInit` at `0x18003c60e`
- `OLEAUT32!__imp_VariantInit` at `0x18003c62a`
- `OLEAUT32!__imp_VariantInit` at `0x18003c646`
- `OLEAUT32!__imp_VariantInit` at `0x18003c660`
- `OLEAUT32!__imp_VariantInit` at `0x18003f305`
- `OLEAUT32!__imp_VariantInit` at `0x18003f31f`
- `OLEAUT32!__imp_VariantInit` at `0x18003f33b`
- `OLEAUT32!__imp_VariantClear` at `0x18003c6d6`
- `OLEAUT32!__imp_VariantClear` at `0x18003c6ee`
- `OLEAUT32!__imp_VariantClear` at `0x18003c706`
- `OLEAUT32!__imp_VariantClear` at `0x18003c71e`
- `OLEAUT32!__imp_VariantClear` at `0x18003c9ae`
- `OLEAUT32!__imp_VariantClear` at `0x18003ce1e`
- `OLEAUT32!__imp_VariantClear` at `0x18003f3ee`
- `OLEAUT32!__imp_VariantClear` at `0x18003f406`
- `OLEAUT32!__imp_VariantClear` at `0x18003f41e`
- `OLEAUT32!__imp_VariantClear` at `0x18003c6d6`
- `OLEAUT32!__imp_VariantClear` at `0x18003c6ee`
- `OLEAUT32!__imp_VariantClear` at `0x18003c706`
- `OLEAUT32!__imp_VariantClear` at `0x18003c71e`
- `OLEAUT32!__imp_VariantClear` at `0x18003c9ae`
- `OLEAUT32!__imp_VariantClear` at `0x18003ce1e`
- `OLEAUT32!__imp_VariantClear` at `0x18003f3ee`
- `OLEAUT32!__imp_VariantClear` at `0x18003f406`
- `OLEAUT32!__imp_VariantClear` at `0x18003f41e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003c5ae`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003c5ae`

## string_xrefs

- `0x18003c5ca`: `onecore\base\ngscb\pcrpf\helperlib\task.cpp`
- `0x18003c740`: `onecore\base\ngscb\pcrpf\helperlib\task.cpp`
- `0x18003c7e4`: `onecore\base\ngscb\pcrpf\helperlib\task.cpp`
- `0x18003c7f4`: `Creating PCRPF tasks folder`
- `0x18003cb13`: `Creating scheduled task: %ws, callback: %ws`
- `0x18003c7fb`: `PpfScheduledTask::GetTask`
- `0x18003cb1a`: `PpfScheduledTask::GetTask`
- `0x18003e757`: `%windir%\system32\rundll32.exe`
- `0x18003e8ea`: `%%windir%%\system32\pcrpf.dll,%ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall PpfScheduledTask::GetTask(const unsigned __int16 **this, struct IRegisteredTask **a2)
{
  HRESULT v4; // eax
  unsigned int v5; // edi
  LPVOID v6; // rcx
  LPVOID v8; // rdi
  __int64 (__fastcall *v9)(LPVOID, VARIANTARG *, __int128 *, int *); // rbx
  __int128 v10; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v12; // xmm8
  IRecordInfo *v13; // xmm9_8
  __int128 v14; // xmm6
  IRecordInfo *v15; // xmm7_8
  HRESULT v16; // eax
  HRESULT v17; // eax
  HRESULT v18; // eax
  HRESULT v19; // eax
  LPVOID v20; // rcx
  LPVOID v21; // rdi
  __int64 v22; // rsi
  BSTR *v23; // rbx
  BSTR v24; // rax
  LPVOID v25; // rsi
  __int64 v26; // r15
  BSTR *v27; // rdi
  BSTR v28; // rax
  __int64 *v29; // rcx
  __int64 v30; // rcx
  LPVOID v31; // rcx
  __int64 *v32; // rsi
  __int64 v33; // r15
  __int64 v34; // rcx
  BSTR v35; // rax
  __int128 v36; // xmm6
  IRecordInfo *v37; // xmm7_8
  BSTR *v38; // rdi
  BSTR v39; // rax
  HRESULT v40; // eax
  __int64 *v41; // rcx
  __int64 v42; // rcx
  LPVOID v43; // rcx
  __int64 *v44; // rcx
  __int64 v45; // rdi
  __int64 (__fastcall *v46)(__int64, __int64, struct IRegisteredTask **); // rsi
  _bstr_t *v47; // rax
  __int64 v48; // rdx
  __int64 v49; // rcx
  LPVOID v50; // rcx
  int v51; // eax
  __int64 v52; // rcx
  struct IRegisteredTask *v53; // rcx
  __int64 v54; // rcx
  LPVOID v55; // rcx
  int v56; // eax
  _QWORD *v57; // rcx
  __int64 v58; // rcx
  struct IRegisteredTask *v59; // rcx
  __int64 v60; // rcx
  LPVOID v61; // rcx
  _QWORD *v62; // rsi
  __int64 v63; // r15
  BSTR *v64; // rdi
  BSTR v65; // rax
  _QWORD *v66; // rcx
  __int64 v67; // rcx
  struct IRegisteredTask *v68; // rcx
  __int64 v69; // rcx
  LPVOID v70; // rcx
  _QWORD *v71; // rdi
  __int64 v72; // rsi
  BSTR v73; // rax
  HRESULT v74; // eax
  _QWORD *v75; // rcx
  __int64 v76; // rcx
  struct IRegisteredTask *v77; // rcx
  __int64 v78; // rcx
  LPVOID v79; // rcx
  int v80; // eax
  __int64 *v81; // rcx
  _QWORD *v82; // rcx
  __int64 v83; // rcx
  struct IRegisteredTask *v84; // rcx
  __int64 v85; // rcx
  LPVOID v86; // rcx
  __int64 *v87; // rsi
  __int64 v88; // r15
  BSTR *v89; // rdi
  BSTR v90; // rax
  __int64 *v91; // rcx
  _QWORD *v92; // rcx
  __int64 v93; // rcx
  struct IRegisteredTask *v94; // rcx
  __int64 v95; // rcx
  LPVOID v96; // rcx
  int v97; // eax
  __int64 *v98; // rcx
  _QWORD *v99; // rcx
  __int64 v100; // rcx
  struct IRegisteredTask *v101; // rcx
  __int64 v102; // rcx
  LPVOID v103; // rcx
  int v104; // eax
  __int64 v105; // rcx
  __int64 *v106; // rcx
  _QWORD *v107; // rcx
  __int64 v108; // rcx
  struct IRegisteredTask *v109; // rcx
  __int64 v110; // rcx
  LPVOID v111; // rcx
  int v112; // eax
  __int64 v113; // rcx
  __int64 *v114; // rcx
  _QWORD *v115; // rcx
  __int64 v116; // rcx
  struct IRegisteredTask *v117; // rcx
  __int64 v118; // rcx
  LPVOID v119; // rcx
  int v120; // eax
  __int64 v121; // rcx
  __int64 *v122; // rcx
  _QWORD *v123; // rcx
  __int64 v124; // rcx
  struct IRegisteredTask *v125; // rcx
  __int64 v126; // rcx
  LPVOID v127; // rcx
  int v128; // eax
  __int64 v129; // rcx
  __int64 *v130; // rcx
  _QWORD *v131; // rcx
  __int64 v132; // rcx
  struct IRegisteredTask *v133; // rcx
  __int64 v134; // rcx
  LPVOID v135; // rcx
  int v136; // eax
  __int64 v137; // rcx
  __int64 *v138; // rcx
  _QWORD *v139; // rcx
  __int64 v140; // rcx
  struct IRegisteredTask *v141; // rcx
  __int64 v142; // rcx
  LPVOID v143; // rcx
  int v144; // eax
  __int64 v145; // rcx
  __int64 *v146; // rcx
  _QWORD *v147; // rcx
  __int64 v148; // rcx
  struct IRegisteredTask *v149; // rcx
  __int64 v150; // rcx
  LPVOID v151; // rcx
  int v152; // eax
  __int64 v153; // rcx
  __int64 *v154; // rcx
  _QWORD *v155; // rcx
  __int64 v156; // rcx
  struct IRegisteredTask *v157; // rcx
  __int64 v158; // rcx
  LPVOID v159; // rcx
  int v160; // eax
  __int64 v161; // rcx
  __int64 v162; // rcx
  __int64 *v163; // rcx
  _QWORD *v164; // rcx
  __int64 v165; // rcx
  struct IRegisteredTask *v166; // rcx
  __int64 v167; // rcx
  LPVOID v168; // rcx
  int v169; // eax
  __int64 v170; // rcx
  __int64 v171; // rcx
  __int64 *v172; // rcx
  _QWORD *v173; // rcx
  __int64 v174; // rcx
  struct IRegisteredTask *v175; // rcx
  __int64 v176; // rcx
  LPVOID v177; // rcx
  int v178; // eax
  __int64 v179; // rcx
  __int64 v180; // rcx
  __int64 *v181; // rcx
  _QWORD *v182; // rcx
  __int64 v183; // rcx
  struct IRegisteredTask *v184; // rcx
  __int64 v185; // rcx
  LPVOID v186; // rcx
  int v187; // eax
  __int64 v188; // rcx
  __int64 v189; // rcx
  __int64 *v190; // rcx
  _QWORD *v191; // rcx
  __int64 v192; // rcx
  struct IRegisteredTask *v193; // rcx
  __int64 v194; // rcx
  LPVOID v195; // rcx
  int v196; // eax
  __int64 v197; // rcx
  __int64 v198; // rcx
  __int64 *v199; // rcx
  _QWORD *v200; // rcx
  __int64 v201; // rcx
  struct IRegisteredTask *v202; // rcx
  __int64 v203; // rcx
  LPVOID v204; // rcx
  int v205; // eax
  __int64 v206; // rcx
  __int64 v207; // rcx
  __int64 *v208; // rcx
  _QWORD *v209; // rcx
  __int64 v210; // rcx
  struct IRegisteredTask *v211; // rcx
  __int64 v212; // rcx
  LPVOID v213; // rcx
  int v214; // eax
  __int64 v215; // rcx
  __int64 v216; // rcx
  __int64 v217; // rcx
  __int64 *v218; // rcx
  _QWORD *v219; // rcx
  __int64 v220; // rcx
  struct IRegisteredTask *v221; // rcx
  __int64 v222; // rcx
  LPVOID v223; // rcx
  int v224; // eax
  __int64 v225; // rcx
  __int64 v226; // rcx
  __int64 v227; // rcx
  __int64 *v228; // rcx
  _QWORD *v229; // rcx
  __int64 v230; // rcx
  struct IRegisteredTask *v231; // rcx
  __int64 v232; // rcx
  LPVOID v233; // rcx
  int v234; // eax
  __int64 v235; // rcx
  __int64 v236; // rcx
  __int64 v237; // rcx
  __int64 *v238; // rcx
  _QWORD *v239; // rcx
  __int64 v240; // rcx
  struct IRegisteredTask *v241; // rcx
  __int64 v242; // rcx
  LPVOID v243; // rcx
  int v244; // eax
  __int64 v245; // rcx
  __int64 v246; // rcx
  __int64 v247; // rcx
  __int64 v248; // rcx
  __int64 *v249; // rcx
  _QWORD *v250; // rcx
  __int64 v251; // rcx
  struct IRegisteredTask *v252; // rcx
  __int64 v253; // rcx
  LPVOID v254; // rcx
  int v255; // eax
  __int64 (__fastcall ***v256)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v257; // rcx
  __int64 v258; // rcx
  __int64 v259; // rcx
  __int64 v260; // rcx
  __int64 *v261; // rcx
  _QWORD *v262; // rcx
  __int64 v263; // rcx
  struct IRegisteredTask *v264; // rcx
  __int64 v265; // rcx
  LPVOID v266; // rcx
  int v267; // eax
  __int64 v268; // rcx
  __int64 (__fastcall ***v269)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v270; // rcx
  __int64 v271; // rcx
  __int64 v272; // rcx
  __int64 v273; // rcx
  __int64 *v274; // rcx
  _QWORD *v275; // rcx
  __int64 v276; // rcx
  struct IRegisteredTask *v277; // rcx
  __int64 v278; // rcx
  LPVOID v279; // rcx
  int v280; // eax
  __int64 v281; // rcx
  __int64 (__fastcall ***v282)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v283; // rcx
  __int64 v284; // rcx
  __int64 v285; // rcx
  __int64 v286; // rcx
  __int64 *v287; // rcx
  _QWORD *v288; // rcx
  __int64 v289; // rcx
  struct IRegisteredTask *v290; // rcx
  __int64 v291; // rcx
  LPVOID v292; // rcx
  int v293; // eax
  __int64 v294; // rcx
  __int64 (__fastcall ***v295)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v296; // rcx
  __int64 v297; // rcx
  __int64 v298; // rcx
  __int64 v299; // rcx
  __int64 *v300; // rcx
  _QWORD *v301; // rcx
  __int64 v302; // rcx
  struct IRegisteredTask *v303; // rcx
  __int64 v304; // rcx
  LPVOID v305; // rcx
  int v306; // eax
  __int64 v307; // rcx
  __int64 (__fastcall ***v308)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v309; // rcx
  __int64 v310; // rcx
  __int64 v311; // rcx
  __int64 v312; // rcx
  __int64 *v313; // rcx
  _QWORD *v314; // rcx
  __int64 v315; // rcx
  struct IRegisteredTask *v316; // rcx
  __int64 v317; // rcx
  LPVOID v318; // rcx
  int v319; // eax
  __int64 v320; // rcx
  __int64 v321; // rcx
  __int64 (__fastcall ***v322)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v323; // rcx
  __int64 v324; // rcx
  __int64 v325; // rcx
  __int64 v326; // rcx
  __int64 *v327; // rcx
  _QWORD *v328; // rcx
  __int64 v329; // rcx
  struct IRegisteredTask *v330; // rcx
  __int64 v331; // rcx
  LPVOID v332; // rcx
  int v333; // eax
  __int64 (__fastcall ***v334)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v335; // rcx
  __int64 v336; // rcx
  __int64 (__fastcall ***v337)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v338; // rcx
  __int64 v339; // rcx
  __int64 v340; // rcx
  __int64 v341; // rcx
  __int64 *v342; // rcx
  _QWORD *v343; // rcx
  __int64 v344; // rcx
  struct IRegisteredTask *v345; // rcx
  __int64 v346; // rcx
  LPVOID v347; // rcx
  int v348; // eax
  __int64 *v349; // rcx
  __int64 (__fastcall ***v350)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v351; // rcx
  __int64 v352; // rcx
  __int64 (__fastcall ***v353)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v354; // rcx
  __int64 v355; // rcx
  __int64 v356; // rcx
  __int64 v357; // rcx
  __int64 *v358; // rcx
  _QWORD *v359; // rcx
  __int64 v360; // rcx
  struct IRegisteredTask *v361; // rcx
  __int64 v362; // rcx
  LPVOID v363; // rcx
  int v364; // eax
  __int64 *v365; // rcx
  __int64 (__fastcall ***v366)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v367; // rcx
  __int64 v368; // rcx
  __int64 (__fastcall ***v369)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v370; // rcx
  __int64 v371; // rcx
  __int64 v372; // rcx
  __int64 v373; // rcx
  __int64 *v374; // rcx
  _QWORD *v375; // rcx
  __int64 v376; // rcx
  struct IRegisteredTask *v377; // rcx
  __int64 v378; // rcx
  LPVOID v379; // rcx
  __int64 v380; // rdi
  __int64 (__fastcall *v381)(__int64, __int64, __int64, __int64); // r15
  __int128 v382; // xmm6
  IRecordInfo *v383; // xmm7_8
  __int128 v384; // xmm8
  IRecordInfo *v385; // xmm9_8
  __int128 v386; // xmm10
  IRecordInfo *v387; // xmm11_8
  __int64 v388; // rsi
  _bstr_t *v389; // rax
  __int64 v390; // rdx
  HRESULT v391; // eax
  HRESULT v392; // eax
  HRESULT v393; // eax
  BSTR *v394; // rcx
  __int64 *v395; // rcx
  __int64 (__fastcall ***v396)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v397; // rcx
  __int64 v398; // rcx
  __int64 (__fastcall ***v399)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v400; // rcx
  __int64 v401; // rcx
  __int64 v402; // rcx
  __int64 v403; // rcx
  __int64 *v404; // rcx
  _QWORD *v405; // rcx
  __int64 v406; // rcx
  struct IRegisteredTask *v407; // rcx
  __int64 v408; // rcx
  LPVOID v409; // rcx
  __int64 v410; // rdi
  __int64 (__fastcall *v411)(__int64, __int64, struct IRegisteredTask **); // rsi
  struct IRegisteredTask *v412; // rcx
  _bstr_t *v413; // rax
  __int64 v414; // rdx
  BSTR *v415; // rcx
  __int64 *v416; // rcx
  __int64 (__fastcall ***v417)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v418; // rcx
  __int64 v419; // rcx
  __int64 (__fastcall ***v420)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v421; // rcx
  __int64 v422; // rcx
  __int64 v423; // rcx
  __int64 v424; // rcx
  __int64 *v425; // rcx
  _QWORD *v426; // rcx
  __int64 v427; // rcx
  struct IRegisteredTask *v428; // rcx
  __int64 v429; // rcx
  LPVOID v430; // rcx
  BSTR *v431; // rcx
  __int64 *v432; // rcx
  __int64 (__fastcall ***v433)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v434; // rcx
  __int64 v435; // rcx
  __int64 (__fastcall ***v436)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v437; // rcx
  __int64 v438; // rcx
  __int64 v439; // rcx
  __int64 v440; // rcx
  __int64 *v441; // rcx
  _QWORD *v442; // rcx
  __int64 v443; // rcx
  struct IRegisteredTask *v444; // rax
  __int64 v445; // rcx
  LPVOID v446; // rcx
  struct IRegisteredTask *v447; // rcx
  __int64 v448; // rcx
  LPVOID v449; // rcx
  int ppv; // [rsp+28h] [rbp-E0h]
  LPVOID *ppva; // [rsp+28h] [rbp-E0h]
  LPVOID v452; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v453; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v454; // [rsp+68h] [rbp-A0h] BYREF
  struct IRegisteredTask *v455; // [rsp+70h] [rbp-98h] BYREF
  _QWORD *v456; // [rsp+78h] [rbp-90h] BYREF
  __int64 v457; // [rsp+80h] [rbp-88h] BYREF
  __int64 *v458; // [rsp+88h] [rbp-80h] BYREF
  __int64 v459; // [rsp+90h] [rbp-78h] BYREF
  __int64 v460; // [rsp+98h] [rbp-70h] BYREF
  __int64 v461; // [rsp+A0h] [rbp-68h] BYREF
  __int64 (__fastcall ***v462)(_QWORD, GUID *, __int64 *); // [rsp+A8h] [rbp-60h] BYREF
  __int64 v463; // [rsp+B0h] [rbp-58h] BYREF
  __int64 *v464; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v465; // [rsp+C0h] [rbp-48h] BYREF
  BSTR *v466; // [rsp+C8h] [rbp-40h] BYREF
  __int64 (__fastcall ***v467)(_QWORD, GUID *, __int64 **); // [rsp+D0h] [rbp-38h] BYREF
  BSTR *v468; // [rsp+D8h] [rbp-30h] BYREF
  VARIANTARG v469; // [rsp+E0h] [rbp-28h] BYREF
  VARIANTARG v470; // [rsp+F8h] [rbp-10h] BYREF
  VARIANTARG v471; // [rsp+118h] [rbp+10h] BYREF
  VARIANTARG v472; // [rsp+130h] [rbp+28h] BYREF
  VARIANTARG pvarg; // [rsp+148h] [rbp+40h] BYREF
  int v474[4]; // [rsp+168h] [rbp+60h] BYREF
  IRecordInfo *v475; // [rsp+178h] [rbp+70h]
  __int128 v476; // [rsp+188h] [rbp+80h] BYREF
  IRecordInfo *v477; // [rsp+198h] [rbp+90h]
  int v478[4]; // [rsp+1A8h] [rbp+A0h] BYREF
  IRecordInfo *v479; // [rsp+1B8h] [rbp+B0h]
  unsigned __int16 v480[264]; // [rsp+1C8h] [rbp+C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+480h] [rbp+378h]

  *a2 = 0;
  v452 = 0;
  v4 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, &v452);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
      (const char *)(unsigned int)v4,
      ppv);
    v6 = v452;
    if ( v452 )
    {
      v452 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 16LL))(v6);
    }
    return v5;
  }
  v8 = v452;
  v9 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, int *))(*(_QWORD *)v452 + 80LL);
  VariantInit(&pvarg);
  v10 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v472);
  v12 = *(_OWORD *)&v472.vt;
  v13 = v472.pRecInfo;
  VariantInit(&v471);
  v14 = *(_OWORD *)&v471.vt;
  v15 = v471.pRecInfo;
  VariantInit(&v469);
  *(_OWORD *)v478 = v10;
  v479 = pRecInfo;
  *(_OWORD *)v474 = v12;
  v475 = v13;
  v476 = v14;
  v477 = v15;
  v470 = v469;
  v5 = v9(v8, &v470, &v476, v474);
  v16 = VariantClear(&v469);
  if ( v16 < 0 )
    _com_issue_error(v16);
  v17 = VariantClear(&v471);
  if ( v17 < 0 )
    _com_issue_error(v17);
  v18 = VariantClear(&v472);
  if ( v18 < 0 )
    _com_issue_error(v18);
  v19 = VariantClear(&pvarg);
  if ( v19 < 0 )
    _com_issue_error(v19);
  if ( (v5 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x15,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
      (const char *)v5,
      (int)v478);
    v20 = v452;
    if ( v452 )
    {
      v452 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v20 + 16LL))(v20);
    }
    return v5;
  }
  v453 = 0;
  v21 = v452;
  v22 = *(_QWORD *)v452;
  v23 = (BSTR *)operator new(0x18u);
  v468 = v23;
  v23[1] = 0;
  *((_DWORD *)v23 + 4) = 1;
  v24 = SysAllocString(L"\\Microsoft\\Windows\\PCRPF");
  *v23 = v24;
  if ( !v24 )
    _com_issue_error(-2147024882);
  v466 = v23;
  v5 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int64 *))(v22 + 56))(v21, v24, &v453);
  _bstr_t::~_bstr_t((_bstr_t *)&v466);
  if ( v5 + 2147024894 > 1 )
  {
    if ( (v5 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x21,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
        (const char *)v5,
        (int)v478);
      v49 = v453;
      if ( v453 )
      {
        v453 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
      }
      v50 = v452;
      if ( v452 )
      {
        v452 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v50 + 16LL))(v50);
      }
      return v5;
    }
  }
  else
  {
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
      0x1Bu,
      "PpfScheduledTask::GetTask",
      "Creating PCRPF tasks folder");
    v464 = 0;
    v25 = v452;
    v26 = *(_QWORD *)v452;
    v27 = (BSTR *)operator new(0x18u);
    v468 = v27;
    v27[1] = 0;
    *((_DWORD *)v27 + 4) = 1;
    v28 = SysAllocString(L"\\");
    *v27 = v28;
    if ( !v28 )
      _com_issue_error(-2147024882);
    v466 = v27;
    v5 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int64 **))(v26 + 56))(v25, v28, &v464);
    _bstr_t::~_bstr_t((_bstr_t *)&v466);
    if ( (v5 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1D,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
        (const char *)v5,
        (int)v478);
      v29 = v464;
      if ( v464 )
      {
        v464 = 0;
        (*(void (__fastcall **)(__int64 *))(*v29 + 16))(v29);
      }
      v30 = v453;
      if ( v453 )
      {
        v453 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
      }
      v31 = v452;
      if ( v452 )
      {
        v452 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v31 + 16LL))(v31);
      }
      return v5;
    }
    v32 = v464;
    v33 = *v464;
    v34 = v453;
    if ( v453 )
    {
      v453 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    }
    v35 = SysAllocString(&Format);
    if ( !v35 )
      _com_issue_error(-2147024882);
    v469.vt = 8;
    v469.llVal = (LONGLONG)v35;
    v36 = *(_OWORD *)&v469.vt;
    v37 = v469.pRecInfo;
    v38 = (BSTR *)operator new(0x18u);
    v468 = v38;
    v38[1] = 0;
    *((_DWORD *)v38 + 4) = 1;
    v39 = SysAllocString(L"\\Microsoft\\Windows\\PCRPF");
    *v38 = v39;
    if ( !v39 )
      _com_issue_error(-2147024882);
    v466 = v38;
    *(_OWORD *)&v470.vt = v36;
    v470.pRecInfo = v37;
    v5 = (*(__int64 (__fastcall **)(__int64 *, BSTR, VARIANTARG *, __int64 *))(v33 + 88))(v32, v39, &v470, &v453);
    _bstr_t::~_bstr_t((_bstr_t *)&v466);
    v40 = VariantClear(&v469);
    if ( v40 < 0 )
      _com_issue_error(v40);
    if ( (v5 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1E,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
        (const char *)v5,
        (int)v478);
      v41 = v464;
      if ( v464 )
      {
        v464 = 0;
        (*(void (__fastcall **)(__int64 *))(*v41 + 16))(v41);
      }
      v42 = v453;
      if ( v453 )
      {
        v453 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
      }
      v43 = v452;
      if ( v452 )
      {
        v452 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v43 + 16LL))(v43);
      }
      return v5;
    }
    v44 = v464;
    if ( v464 )
    {
      v464 = 0;
      (*(void (__fastcall **)(__int64 *))(*v44 + 16))(v44);
    }
  }
  v455 = 0;
  v45 = v453;
  v46 = *(__int64 (__fastcall **)(__int64, __int64, struct IRegisteredTask **))(*(_QWORD *)v453 + 104LL);
  v47 = _bstr_t::_bstr_t((_bstr_t *)&v466, this[1]);
  if ( *(_QWORD *)v47 )
    v48 = **(_QWORD **)v47;
  else
    v48 = 0;
  v5 = v46(v45, v48, &v455);
  _bstr_t::~_bstr_t((_bstr_t *)&v466);
  if ( v5 + 2147024894 > 1 )
  {
    if ( (v5 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x73,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
        (const char *)v5,
        (int)v478);
      v447 = v455;
      if ( v455 )
      {
        v455 = 0;
        ((void (__fastcall *)(struct IRegisteredTask *))v447->lpVtbl->Release)(v447);
      }
      v448 = v453;
      if ( v453 )
      {
        v453 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v448 + 16LL))(v448);
      }
      v449 = v452;
      if ( v452 )
      {
        v452 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v449 + 16LL))(v449);
      }
      return v5;
    }
  }
  else
  {
    ppva = (LPVOID *)this[1];
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
      0x27u,
      "PpfScheduledTask::GetTask",
      "Creating scheduled task: %ws, callback: %ws");
    v454 = 0;
    v51 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)v452 + 72LL))(v452, 0, &v454);
    v5 = v51;
    if ( v51 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x29,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
        (const char *)(unsigned int)v51,
        (int)ppva);
      v52 = v454;
      if ( v454 )
      {
        v454 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
      }
      v53 = v455;
      if ( v455 )
      {
        v455 = 0;
        ((void (__fastcall *)(struct IRegisteredTask *))v53->lpVtbl->Release)(v53);
      }
      v54 = v453;
      if ( v453 )
      {
        v453 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
      }
      v55 = v452;
      if ( v452 )
      {
        v452 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v55 + 16LL))(v55);
      }
      return v5;
    }
    v456 = 0;
    v56 = (*(__int64 (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v454 + 56LL))(v454, &v456);
    v5 = v56;
    if ( v56 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2D,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
        (const char *)(unsigned int)v56,
        (int)ppva);
      v57 = v456;
      if ( v456 )
      {
        v456 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v57 + 16LL))(v57);
      }
      v58 = v454;
      if ( v454 )
      {
        v454 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
      }
      v59 = v455;
      if ( v455 )
      {
        v455 = 0;
        ((void (__fastcall *)(struct IRegisteredTask *))v59->lpVtbl->Release)(v59);
      }
      v60 = v453;
      if ( v453 )
      {
        v453 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
      }
      v61 = v452;
      if ( v452 )
      {
        v452 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v61 + 16LL))(v61);
      }
      return v5;
    }
    v62 = v456;
    v63 = *v456;
    v64 = (BSTR *)operator new(0x18u);
    v468 = v64;
    v64[1] = 0;
    *((_DWORD *)v64 + 4) = 1;
    v65 = SysAllocString(L"Microsoft Corporation");
    *v64 = v65;
    if ( !v65 )
      _com_issue_error(-2147024882);
    v468 = v64;
    v5 = (*(__int64 (__fastcall **)(_QWORD *, BSTR))(v63 + 80))(v62, v65);
    _bstr_t::~_bstr_t((_bstr_t *)&v468);
    if ( (v5 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2E,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
        (const char *)v5,
        (int)ppva);
      v66 = v456;
      if ( v456 )
      {
        v456 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v66 + 16LL))(v66);
      }
      v67 = v454;
      if ( v454 )
      {
        v454 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
      }
      v68 = v455;
      if ( v455 )
      {
        v455 = 0;
        ((void (__fastcall *)(struct IRegisteredTask *))v68->lpVtbl->Release)(v68);
      }
      v69 = v453;
      if ( v453 )
      {
        v453 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
      }
      v70 = v452;
      if ( v452 )
      {
        v452 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v70 + 16LL))(v70);
      }
      return v5;
    }
    v71 = v456;
    v72 = *v456;
    v73 = SysAllocString(L"D:P(A;;GA;;;SY)(A;;GA;;;BA)(A;;GRGX;;;AU)");
    if ( !v73 )
      _com_issue_error(-2147024882);
    v469.vt = 8;
    v469.llVal = (LONGLONG)v73;
    v470 = v469;
    v5 = (*(__int64 (__fastcall **)(_QWORD *, VARIANTARG *))(v72 + 176))(v71, &v470);
    v74 = VariantClear(&v469);
    if ( v74 < 0 )
      _com_issue_error(v74);
    if ( (v5 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x32,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
        (const char *)v5,
        (int)ppva);
      v75 = v456;
      if ( v456 )
      {
        v456 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v75 + 16LL))(v75);
      }
      v76 = v454;
      if ( v454 )
      {
        v454 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
      }
      v77 = v455;
      if ( v455 )
      {
        v455 = 0;
        ((void (__fastcall *)(struct IRegisteredTask *))v77->lpVtbl->Release)(v77);
      }
      v78 = v453;
      if ( v453 )
      {
        v453 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
      }
      v79 = v452;
      if ( v452 )
      {
        v452 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v79 + 16LL))(v79);
      }
      return v5;
    }
    v458 = 0;
    v80 = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v454 + 120LL))(v454, &v458);
    v5 = v80;
    if ( v80 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x36,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
        (const char *)(unsigned int)v80,
        (int)ppva);
      v81 = v458;
      if ( v458 )
      {
        v458 = 0;
        (*(void (__fastcall **)(__int64 *))(*v81 + 16))(v81);
      }
      v82 = v456;
      if ( v456 )
      {
        v456 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v82 + 16LL))(v82);
      }
      v83 = v454;
      if ( v454 )
      {
        v454 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
      }
      v84 = v455;
      if ( v455 )
      {
        v455 = 0;
        ((void (__fastcall *)(struct IRegisteredTask *))v84->lpVtbl->Release)(v84);
      }
      v85 = v453;
      if ( v453 )
      {
        v453 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
      }
      v86 = v452;
      if ( v452 )
      {
        v452 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v86 + 16LL))(v86);
      }
      return v5;
    }
    v87 = v458;
    v88 = *v458;
    v89 = (BSTR *)operator new(0x18u);
    v468 = v89;
    v89[1] = 0;
    *((_DWORD *)v89 + 4) = 1;
    v90 = SysAllocString(L"SYSTEM");
    *v89 = v90;
    if ( !v90 )
      _com_issue_error(-2147024882);
    v468 = v89;
    v5 = (*(__int64 (__fastcall **)(__int64 *, BSTR))(v88 + 96))(v87, v90);
    _bstr_t::~_bstr_t((_bstr_t *)&v468);
    if ( (v5 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x37,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
        (const char *)v5,
        (int)ppva);
      v91 = v458;
      if ( v458 )
      {
        v458 = 0;
        (*(void (__fastcall **)(__int64 *))(*v91 + 16))(v91);
      }
      v92 = v456;
      if ( v456 )
      {
        v456 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v92 + 16LL))(v92);
      }
      v93 = v454;
      if ( v454 )
      {
        v454 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
      }
      v94 = v455;
      if ( v455 )
      {
        v455 = 0;
        ((void (__fastcall *)(struct IRegisteredTask *))v94->lpVtbl->Release)(v94);
      }
      v95 = v453;
      if ( v453 )
      {
        v453 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
      }
      v96 = v452;
      if ( v452 )
      {
        v452 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v96 + 16LL))(v96);
      }
      return v5;
    }
    v97 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v458 + 144))(v458, 1);
    v5 = v97;
    if ( v97 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x38,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
        (const char *)(unsigned int)v97,
        (int)ppva);
      v98 = v458;
      if ( v458 )
      {
        v458 = 0;
        (*(void (__fastcall **)(__int64 *))(*v98 + 16))(v98);
      }
      v99 = v456;
      if ( v456 )
      {
        v456 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v99 + 16LL))(v99);
      }
      v100 = v454;
      if ( v454 )
      {
        v454 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v100 + 16LL))(v100);
      }
      v101 = v455;
      if ( v455 )
      {
        v455 = 0;
        ((void (__fastcall *)(struct IRegisteredTask *))v101->lpVtbl->Release)(v101);
      }
      v102 = v453;
      if ( v453 )
      {
        v453 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v102 + 16LL))(v102);
      }
      v103 = v452;
      if ( v452 )
      {
        v452 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v103 + 16LL))(v103);
      }
      return v5;
    }
    v457 = 0;
    v104 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v454 + 88LL))(v454, &v457);
    v5 = v104;
    if ( v104 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3C,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
        (const char *)(unsigned int)v104,
        (int)ppva);
      v105 = v457;
      if ( v457 )
      {
        v457 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v105 + 16LL))(v105);
      }
      v106 = v458;
      if ( v458 )
      {
        v458 = 0;
        (*(void (__fastcall **)(__int64 *))(*v106 + 16))(v106);
      }
      v107 = v456;
      if ( v456 )
      {
        v456 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v107 + 16LL))(v107);
      }
      v108 = v454;
      if ( v454 )
      {
        v454 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v108 + 16LL))(v108);
      }
      v109 = v455;
      if ( v455 )
      {
        v455 = 0;
        ((void (__fastcall *)(struct IRegisteredTask *))v109->lpVtbl->Release)(v109);
      }
      v110 = v453;
      if ( v453 )
      {
        v453 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v110 + 16LL))(v110);
      }
      v111 = v452;
      if ( v452 )
      {
        v452 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v111 + 16LL))(v111);
      }
      return v5;
    }
    v112 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v457 + 112LL))(v457, 2);
    v5 = v112;
    if ( v112 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3D,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
        (const char *)(unsigned int)v112,
        (int)ppva);
      v113 = v457;
      if ( v457 )
      {
        v457 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v113 + 16LL))(v113);
      }
      v114 = v458;
      if ( v458 )
      {
        v458 = 0;
        (*(void (__fastcall **)(__int64 *))(*v114 + 16))(v114);
      }
      v115 = v456;
      if ( v456 )
      {
        v456 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v115 + 16LL))(v115);
      }
      v116 = v454;
      if ( v454 )
      {
        v454 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v116 + 16LL))(v116);
      }
      v117 = v455;
      if ( v455 )
      {
        v455 = 0;
        ((void (__fastcall *)(struct IRegisteredTask *))v117->lpVtbl->Release)(v117);
      }
      v118 = v453;
      if ( v453 )
      {
        v453 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v118 + 16LL))(v118);
      }
      v119 = v452;
      if ( v452 )
      {
        v452 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v119 + 16LL))(v119);
      }
      return v5;
    }
    v120 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v457 + 144LL))(v457, 0);
    v5 = v120;
    if ( v120 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3E,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
        (const char *)(unsigned int)v120,
        (int)ppva);
      v121 = v457;
      if ( v457 )
      {
        v457 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v121 + 16LL))(v121);
      }
      v122 = v458;
      if ( v458 )
      {
        v458 = 0;
        (*(void (__fastcall **)(__int64 *))(*v122 + 16))(v122);
      }
      v123 = v456;
      if ( v456 )
      {
        v456 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v123 + 16LL))(v123);
      }
      v124 = v454;
      if ( v454 )
      {
        v454 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v124 + 16LL))(v124);
      }
      v125 = v455;
      if ( v455 )
      {
        v455 = 0;
        ((void (__fastcall *)(struct IRegisteredTask *))v125->lpVtbl->Release)(v125);
      }
      v126 = v453;
      if ( v453 )
      {
        v453 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v126 + 16LL))(v126);
      }
      v127 = v452;
      if ( v452 )
      {
        v452 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v127 + 16LL))(v127);
      }
      return v5;
    }
    v128 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v457 + 128LL))(v457, 0);
    v5 = v128;
    if ( v128 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3F,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
        (const char *)(unsigned int)v128,
        (int)ppva);
      v129 = v457;
      if ( v457 )
      {
        v457 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v129 + 16LL))(v129);
      }
      v130 = v458;
      if ( v458 )
      {
        v458 = 0;
        (*(void (__fastcall **)(__int64 *))(*v130 + 16))(v130);
      }
      v131 = v456;
      if ( v456 )
      {
        v456 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v131 + 16LL))(v131);
      }
      v132 = v454;
      if ( v454 )
      {
        v454 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v132 + 16LL))(v132);
      }
      v133 = v455;
      if ( v455 )
      {
        v455 = 0;
        ((void (__fastcall *)(struct IRegisteredTask *))v133->lpVtbl->Release)(v133);
      }
      v134 = v453;
      if ( v453 )
      {
        v453 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v134 + 16LL))(v134);
      }
      v135 = v452;
      if ( v452 )
      {
        v452 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v135 + 16LL))(v135);
      }
      return v5;
    }
    v136 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v457 + 160LL))(v457, 0);
    v5 = v136;
    if ( v136 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x40,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
        (const char *)(unsigned int)v136,
        (int)ppva);
      v137 = v457;
      if ( v457 )
      {
        v457 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v137 + 16LL))(v137);
      }
      v138 = v458;
      if ( v458 )
      {
        v458 = 0;
        (*(void (__fastcall **)(__int64 *))(*v138 + 16))(v138);
      }
      v139 = v456;
      if ( v456 )
      {
        v456 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v139 + 16LL))(v139);
      }
      v140 = v454;
      if ( v454 )
      {
        v454 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v140 + 16LL))(v140);
      }
      v141 = v455;
      if ( v455 )
      {
        v455 = 0;
        ((void (__fastcall *)(struct IRegisteredTask *))v141->lpVtbl->Release)(v141);
      }
      v142 = v453;
      if ( v453 )
      {
        v453 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v142 + 16LL))(v142);
      }
      v143 = v452;
      if ( v452 )
      {
        v452 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v143 + 16LL))(v143);
      }
      return v5;
    }
    v144 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v457 + 176LL))(v457, 0);
    v5 = v144;
    if ( v144 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x41,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
        (const char *)(unsigned int)v144,
        (int)ppva);
      v145 = v457;
      if ( v457 )
      {
        v457 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v145 + 16LL))(v145);
      }
      v146 = v458;
      if ( v458 )
      {
        v458 = 0;
        (*(void (__fastcall **)(__int64 *))(*v146 + 16))(v146);
      }
      v147 = v456;
      if ( v456 )
      {
        v456 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v147 + 16LL))(v147);
      }
      v148 = v454;
      if ( v454 )
      {
        v454 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v148 + 16LL))(v148);
      }
      v149 = v455;
      if ( v455 )
      {
        v455 = 0;
        ((void (__fastcall *)(struct IRegisteredTask *))v149->lpVtbl->Release)(v149);
      }
      v150 = v453;
      if ( v453 )
      {
        v453 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v150 + 16LL))(v150);
      }
      v151 = v452;
      if ( v452 )
      {
        v452 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v151 + 16LL))(v151);
      }
      return v5;
    }
    v152 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v457 + 208LL))(v457, 0);
    v5 = v152;
    if ( v152 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x42,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
        (const char *)(unsigned int)v152,
        (int)ppva);
      v153 = v457;
      if ( v457 )
      {
        v457 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v153 + 16LL))(v153);
      }
      v154 = v458;
      if ( v458 )
      {
        v458 = 0;
        (*(void (__fastcall **)(__int64 *))(*v154 + 16))(v154);
      }
      v155 = v456;
      if ( v456 )
      {
        v456 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v155 + 16LL))(v155);
      }
      v156 = v454;
      if ( v454 )
      {
        v454 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v156 + 16LL))(v156);
      }
      v157 = v455;
      if ( v455 )
      {
        v455 = 0;
        ((void (__fastcall *)(struct IRegisteredTask *))v157->lpVtbl->Release)(v157);
      }
      v158 = v453;
      if ( v453 )
      {
        v453 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v158 + 16LL))(v158);
      }
      v159 = v452;
      if ( v452 )
      {
        v452 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v159 + 16LL))(v159);
      }
      return v5;
    }
    v459 = 0;
    v160 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v457 + 312LL))(v457, &v459);
    v5 = v160;
    if ( v160 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x44,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
        (const char *)(unsigned int)v160,
        (int)ppva);
      v161 = v459;
      if ( v459 )
      {
        v459 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v161 + 16LL))(v161);
      }
      v162 = v457;
      if ( v457 )
      {
        v457 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v162 + 16LL))(v162);
      }
      v163 = v458;
      if ( v458 )
      {
        v458 = 0;
        (*(void (__fastcall **)(__int64 *))(*v163 + 16))(v163);
      }
      v164 = v456;
      if ( v456 )
      {
        v456 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v164 + 16LL))(v164);
      }
      v165 = v454;
      if ( v454 )
      {
        v454 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v165 + 16LL))(v165);
      }
      v166 = v455;
      if ( v455 )
      {
        v455 = 0;
        ((void (__fastcall *)(struct IRegisteredTask *))v166->lpVtbl->Release)(v166);
      }
      v167 = v453;
      if ( v453 )
      {
        v453 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v167 + 16LL))(v167);
      }
      v168 = v452;
      if ( v452 )
      {
        v452 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v168 + 16LL))(v168);
      }
      return v5;
    }
    v169 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v459 + 96LL))(v459, 0);
    v5 = v169;
    if ( v169 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x45,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
        (const char *)(unsigned int)v169,
        (int)ppva);
      v170 = v459;
      if ( v459 )
      {
        v459 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v170 + 16LL))(v170);
      }
      v171 = v457;
      if ( v457 )
      {
        v457 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v171 + 16LL))(v171);
      }
      v172 = v458;
      if ( v458 )
      {
        v458 = 0;
        (*(void (__fastcall **)(__int64 *))(*v172 + 16))(v172);
      }
      v173 = v456;
      if ( v456 )
      {
        v456 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v173 + 16LL))(v173);
      }
      v174 = v454;
      if ( v454 )
      {
        v454 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v174 + 16LL))(v174);
      }
      v175 = v455;
      if ( v455 )
      {
        v455 = 0;
        ((void (__fastcall *)(struct IRegisteredTask *))v175->lpVtbl->Release)(v175);
      }
      v176 = v453;
      if ( v453 )
      {
        v453 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v176 + 16LL))(v176);
      }
      v177 = v452;
      if ( v452 )
      {
        v452 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v177 + 16LL))(v177);
      }
      return v5;
    }
    v178 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v459 + 112LL))(v459, 0);
    v5 = v178;
    if ( v178 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x46,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
        (const char *)(unsigned int)v178,
        (int)ppva);
      v179 = v459;
      if ( v459 )
      {
        v459 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v179 + 16LL))(v179);
      }
      v180 = v457;
      if ( v457 )
      {
        v457 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v180 + 16LL))(v180);
      }
      v181 = v458;
      if ( v458 )
      {
        v458 = 0;
        (*(void (__fastcall **)(__int64 *))(*v181 + 16))(v181);
      }
      v182 = v456;
      if ( v456 )
      {
        v456 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v182 + 16LL))(v182);
      }
      v183 = v454;
      if ( v454 )
      {
        v454 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v183 + 16LL))(v183);
      }
      v184 = v455;
      if ( v455 )
      {
        v455 = 0;
        ((void (__fastcall *)(struct IRegisteredTask *))v184->lpVtbl->Release)(v184);
      }
      v185 = v453;
      if ( v453 )
      {
        v453 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v185 + 16LL))(v185);
      }
      v186 = v452;
      if ( v452 )
      {
        v452 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v186 + 16LL))(v186);
      }
      return v5;
    }
    v187 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v457 + 64LL))(v457, 0xFFFFFFFFLL);
    v5 = v187;
    if ( v187 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x47,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
        (const char *)(unsigned int)v187,
        (int)ppva);
      v188 = v459;
      if ( v459 )
      {
        v459 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v188 + 16LL))(v188);
      }
      v189 = v457;
      if ( v457 )
      {
        v457 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v189 + 16LL))(v189);
      }
      v190 = v458;
      if ( v458 )
      {
        v458 = 0;
        (*(void (__fastcall **)(__int64 *))(*v190 + 16))(v190);
      }
      v191 = v456;
      if ( v456 )
      {
        v456 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v191 + 16LL))(v191);
      }
      v192 = v454;
      if ( v454 )
      {
        v454 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v192 + 16LL))(v192);
      }
      v193 = v455;
      if ( v455 )
      {
        v455 = 0;
        ((void (__fastcall *)(struct IRegisteredTask *))v193->lpVtbl->Release)(v193);
      }
      v194 = v453;
      if ( v453 )
      {
        v453 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v194 + 16LL))(v194);
      }
      v195 = v452;
      if ( v452 )
      {
        v452 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v195 + 16LL))(v195);
      }
      return v5;
    }
    v196 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v457 + 304LL))(v457, 0);
    v5 = v196;
    if ( v196 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x48,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
        (const char *)(unsigned int)v196,
        (int)ppva);
      v197 = v459;
      if ( v459 )
      {
        v459 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v197 + 16LL))(v197);
      }
      v198 = v457;
      if ( v457 )
      {
        v457 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v198 + 16LL))(v198);
      }
      v199 = v458;
      if ( v458 )
      {
        v458 = 0;
        (*(void (__fastcall **)(__int64 *))(*v199 + 16))(v199);
      }
      v200 = v456;
      if ( v456 )
      {
        v456 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v200 + 16LL))(v200);
      }
      v201 = v454;
      if ( v454 )
      {
        v454 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v201 + 16LL))(v201);
      }
      v202 = v455;
      if ( v455 )
      {
        v455 = 0;
        ((void (__fastcall *)(struct IRegisteredTask *))v202->lpVtbl->Release)(v202);
      }
      v203 = v453;
      if ( v453 )
      {
        v453 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v203 + 16LL))(v203);
      }
      v204 = v452;
      if ( v452 )
      {
        v452 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v204 + 16LL))(v204);
      }
      return v5;
    }
    v205 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v457 + 336LL))(v457, 0);
    v5 = v205;
    if ( v205 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x49,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
        (const char *)(unsigned int)v205,
        (int)ppva);
      v206 = v459;
      if ( v459 )
      {
        v459 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v206 + 16LL))(v206);
      }
      v207 = v457;
      if ( v457 )
      {
        v457 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v207 + 16LL))(v207);
      }
      v208 = v458;
      if ( v458 )
      {
        v458 = 0;
        (*(void (__fastcall **)(__int64 *))(*v208 + 16))(v208);
      }
      v209 = v456;
      if ( v456 )
      {
        v456 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v209 + 16LL))(v209);
      }
      v210 = v454;
      if ( v454 )
      {
        v454 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v210 + 16LL))(v210);
      }
      v211 = v455;
      if ( v455 )
      {
        v455 = 0;
        ((void (__fastcall *)(struct IRegisteredTask *))v211->lpVtbl->Release)(v211);
      }
      v212 = v453;
      if ( v453 )
      {
        v453 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v212 + 16LL))(v212);
      }
      v213 = v452;
      if ( v452 )
      {
        v452 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v213 + 16LL))(v213);
      }
      return v5;
    }
    v460 = 0;
    v214 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v457)(
             v457,
             &GUID_0ad9d0d7_0c7f_4ebb_9a5f_d1c648dca528,
             &v460);
    v5 = v214;
    if ( v214 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4B,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
        (const char *)(unsigned int)v214,
        (int)ppva);
      v215 = v460;
      if ( v460 )
      {
        v460 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v215 + 16LL))(v215);
      }
      v216 = v459;
      if ( v459 )
      {
        v459 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v216 + 16LL))(v216);
      }
      v217 = v457;
      if ( v457 )
      {
        v457 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v217 + 16LL))(v217);
      }
      v218 = v458;
      if ( v458 )
      {
        v458 = 0;
        (*(void (__fastcall **)(__int64 *))(*v218 + 16))(v218);
      }
      v219 = v456;
      if ( v456 )
      {
        v456 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v219 + 16LL))(v219);
      }
      v220 = v454;
      if ( v454 )
      {
        v454 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v220 + 16LL))(v220);
      }
      v221 = v455;
      if ( v455 )
      {
        v455 = 0;
        ((void (__fastcall *)(struct IRegisteredTask *))v221->lpVtbl->Release)(v221);
      }
      v222 = v453;
      if ( v453 )
      {
        v453 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v222 + 16LL))(v222);
      }
      v223 = v452;
      if ( v452 )
      {
        v452 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v223 + 16LL))(v223);
      }
      return v5;
    }
    v224 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v460 + 384LL))(v460, 0);
    v5 = v224;
    if ( v224 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4C,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
        (const char *)(unsigned int)v224,
        (int)ppva);
      v225 = v460;
      if ( v460 )
      {
        v460 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v225 + 16LL))(v225);
      }
      v226 = v459;
      if ( v459 )
      {
        v459 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v226 + 16LL))(v226);
      }
      v227 = v457;
      if ( v457 )
      {
        v457 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v227 + 16LL))(v227);
      }
      v228 = v458;
      if ( v458 )
      {
        v458 = 0;
        (*(void (__fastcall **)(__int64 *))(*v228 + 16))(v228);
      }
      v229 = v456;
      if ( v456 )
      {
        v456 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v229 + 16LL))(v229);
      }
      v230 = v454;
      if ( v454 )
      {
        v454 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v230 + 16LL))(v230);
      }
      v231 = v455;
      if ( v455 )
      {
        v455 = 0;
        ((void (__fastcall *)(struct IRegisteredTask *))v231->lpVtbl->Release)(v231);
      }
      v232 = v453;
      if ( v453 )
      {
        v453 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v232 + 16LL))(v232);
      }
      v233 = v452;
      if ( v452 )
      {
        v452 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v233 + 16LL))(v233);
      }
      return v5;
    }
    v234 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v460 + 400LL))(v460, 0xFFFFFFFFLL);
    v5 = v234;
    if ( v234 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4D,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
        (const char *)(unsigned int)v234,
        (int)ppva);
      v235 = v460;
      if ( v460 )
      {
        v460 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v235 + 16LL))(v235);
      }
      v236 = v459;
      if ( v459 )
      {
        v459 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v236 + 16LL))(v236);
      }
      v237 = v457;
      if ( v457 )
      {
        v457 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v237 + 16LL))(v237);
      }
      v238 = v458;
      if ( v458 )
      {
        v458 = 0;
        (*(void (__fastcall **)(__int64 *))(*v238 + 16))(v238);
      }
      v239 = v456;
      if ( v456 )
      {
        v456 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v239 + 16LL))(v239);
      }
      v240 = v454;
      if ( v454 )
      {
        v454 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v240 + 16LL))(v240);
      }
      v241 = v455;
      if ( v455 )
      {
        v455 = 0;
        ((void (__fastcall *)(struct IRegisteredTask *))v241->lpVtbl->Release)(v241);
      }
      v242 = v453;
      if ( v453 )
      {
        v453 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v242 + 16LL))(v242);
      }
      v243 = v452;
      if ( v452 )
      {
        v452 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v243 + 16LL))(v243);
      }
      return v5;
    }
    v461 = 0;
    v244 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v454 + 136LL))(v454, &v461);
    v5 = v244;
    if ( v244 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x51,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
        (const char *)(unsigned int)v244,
        (int)ppva);
      v245 = v461;
      if ( v461 )
      {
        v461 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v245 + 16LL))(v245);
      }
      v246 = v460;
      if ( v460 )
      {
        v460 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v246 + 16LL))(v246);
      }
      v247 = v459;
      if ( v459 )
      {
        v459 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v247 + 16LL))(v247);
      }
      v248 = v457;
      if ( v457 )
      {
        v457 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v248 + 16LL))(v248);
      }
      v249 = v458;
      if ( v458 )
      {
        v458 = 0;
        (*(void (__fastcall **)(__int64 *))(*v249 + 16))(v249);
      }
      v250 = v456;
      if ( v456 )
      {
        v456 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v250 + 16LL))(v250);
      }
      v251 = v454;
      if ( v454 )
      {
        v454 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v251 + 16LL))(v251);
      }
      v252 = v455;
      if ( v455 )
      {
        v455 = 0;
        ((void (__fastcall *)(struct IRegisteredTask *))v252->lpVtbl->Release)(v252);
      }
      v253 = v453;
      if ( v453 )
      {
        v453 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v253 + 16LL))(v253);
      }
      v254 = v452;
      if ( v452 )
      {
        v452 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v254 + 16LL))(v254);
      }
      return v5;
    }
    v462 = 0;
    v255 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v461 + 96LL))(v461, 0, &v462);
    v5 = v255;
    if ( v255 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x53,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
        (const char *)(unsigned int)v255,
        (int)ppva);
      v256 = v462;
      if ( v462 )
      {
        v462 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v256)[2])(v256);
      }
      v257 = v461;
      if ( v461 )
      {
        v461 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v257 + 16LL))(v257);
      }
      v258 = v460;
      if ( v460 )
      {
        v460 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v258 + 16LL))(v258);
      }
      v259 = v459;
      if ( v459 )
      {
        v459 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v259 + 16LL))(v259);
      }
      v260 = v457;
      if ( v457 )
      {
        v457 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v260 + 16LL))(v260);
      }
      v261 = v458;
      if ( v458 )
      {
        v458 = 0;
        (*(void (__fastcall **)(__int64 *))(*v261 + 16))(v261);
      }
      v262 = v456;
      if ( v456 )
      {
        v456 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v262 + 16LL))(v262);
      }
      v263 = v454;
      if ( v454 )
      {
        v454 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v263 + 16LL))(v263);
      }
      v264 = v455;
      if ( v455 )
      {
        v455 = 0;
        ((void (__fastcall *)(struct IRegisteredTask *))v264->lpVtbl->Release)(v264);
      }
      v265 = v453;
      if ( v453 )
      {
        v453 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v265 + 16LL))(v265);
      }
      v266 = v452;
      if ( v452 )
      {
        v452 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v266 + 16LL))(v266);
      }
      return v5;
    }
    v463 = 0;
    v267 = (**v462)(v462, &GUID_4c3d624d_fd6b_49a3_b9b7_09cb3cd3f047, &v463);
    v5 = v267;
    if ( v267 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x55,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
        (const char *)(unsigned int)v267,
        (int)ppva);
      v268 = v463;
      if ( v463 )
      {
        v463 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v268 + 16LL))(v268);
      }
      v269 = v462;
      if ( v462 )
      {
        v462 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v269)[2])(v269);
      }
      v270 = v461;
      if ( v461 )
      {
        v461 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v270 + 16LL))(v270);
      }
      v271 = v460;
      if ( v460 )
      {
        v460 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v271 + 16LL))(v271);
      }
      v272 = v459;
      if ( v459 )
      {
        v459 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v272 + 16LL))(v272);
      }
      v273 = v457;
      if ( v457 )
      {
        v457 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v273 + 16LL))(v273);
      }
      v274 = v458;
      if ( v458 )
      {
        v458 = 0;
        (*(void (__fastcall **)(__int64 *))(*v274 + 16))(v274);
      }
      v275 = v456;
      if ( v456 )
      {
        v456 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v275 + 16LL))(v275);
      }
      v276 = v454;
      if ( v454 )
      {
        v454 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v276 + 16LL))(v276);
      }
      v277 = v455;
      if ( v455 )
      {
        v455 = 0;
        ((void (__fastcall *)(struct IRegisteredTask *))v277->lpVtbl->Release)(v277);
      }
      v278 = v453;
      if ( v453 )
      {
        v453 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v278 + 16LL))(v278);
      }
      v279 = v452;
      if ( v452 )
      {
        v452 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v279 + 16LL))(v279);
      }
      return v5;
    }
    v280 = (*(__int64 (**)(__int64, const wchar_t *, ...))(*(_QWORD *)v463 + 88LL))(
             v463,
             L"%windir%\\system32\\rundll32.exe");
    v5 = v280;
    if ( v280 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x56,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
        (const char *)(unsigned int)v280,
        (int)ppva);
      v281 = v463;
      if ( v463 )
      {
        v463 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v281 + 16LL))(v281);
      }
      v282 = v462;
      if ( v462 )
      {
        v462 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v282)[2])(v282);
      }
      v283 = v461;
      if ( v461 )
      {
        v461 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v283 + 16LL))(v283);
      }
      v284 = v460;
      if ( v460 )
      {
        v460 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v284 + 16LL))(v284);
      }
      v285 = v459;
      if ( v459 )
      {
        v459 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v285 + 16LL))(v285);
      }
      v286 = v457;
      if ( v457 )
      {
        v457 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v286 + 16LL))(v286);
      }
      v287 = v458;
      if ( v458 )
      {
        v458 = 0;
        (*(void (__fastcall **)(__int64 *))(*v287 + 16))(v287);
      }
      v288 = v456;
      if ( v456 )
      {
        v456 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v288 + 16LL))(v288);
      }
      v289 = v454;
      if ( v454 )
      {
        v454 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v289 + 16LL))(v289);
      }
      v290 = v455;
      if ( v455 )
      {
        v455 = 0;
        ((void (__fastcall *)(struct IRegisteredTask *))v290->lpVtbl->Release)(v290);
      }
      v291 = v453;
      if ( v453 )
      {
        v453 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v291 + 16LL))(v291);
      }
      v292 = v452;
      if ( v452 )
      {
        v452 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v292 + 16LL))(v292);
      }
      return v5;
    }
    memset_0(v480, 0, 0x208u);
    v293 = StringCchPrintfW(v480, 0x104u, L"%%windir%%\\system32\\pcrpf.dll,%ws", this[2]);
    v5 = v293;
    if ( v293 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x58,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
        (const char *)(unsigned int)v293,
        (int)ppva);
      v294 = v463;
      if ( v463 )
      {
        v463 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v294 + 16LL))(v294);
      }
      v295 = v462;
      if ( v462 )
      {
        v462 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v295)[2])(v295);
      }
      v296 = v461;
      if ( v461 )
      {
        v461 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v296 + 16LL))(v296);
      }
      v297 = v460;
      if ( v460 )
      {
        v460 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v297 + 16LL))(v297);
      }
      v298 = v459;
      if ( v459 )
      {
        v459 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v298 + 16LL))(v298);
      }
      v299 = v457;
      if ( v457 )
      {
        v457 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v299 + 16LL))(v299);
      }
      v300 = v458;
      if ( v458 )
      {
        v458 = 0;
        (*(void (__fastcall **)(__int64 *))(*v300 + 16))(v300);
      }
      v301 = v456;
      if ( v456 )
      {
        v456 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v301 + 16LL))(v301);
      }
      v302 = v454;
      if ( v454 )
      {
        v454 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v302 + 16LL))(v302);
      }
      v303 = v455;
      if ( v455 )
      {
        v455 = 0;
        ((void (__fastcall *)(struct IRegisteredTask *))v303->lpVtbl->Release)(v303);
      }
      v304 = v453;
      if ( v453 )
      {
        v453 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v304 + 16LL))(v304);
      }
      v305 = v452;
      if ( v452 )
      {
        v452 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v305 + 16LL))(v305);
      }
      return v5;
    }
    v306 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v463 + 104LL))(v463, v480);
    v5 = v306;
    if ( v306 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x59,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
        (const char *)(unsigned int)v306,
        (int)ppva);
      v307 = v463;
      if ( v463 )
      {
        v463 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v307 + 16LL))(v307);
      }
      v308 = v462;
      if ( v462 )
      {
        v462 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v308)[2])(v308);
      }
      v309 = v461;
      if ( v461 )
      {
        v461 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v309 + 16LL))(v309);
      }
      v310 = v460;
      if ( v460 )
      {
        v460 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v310 + 16LL))(v310);
      }
      v311 = v459;
      if ( v459 )
      {
        v459 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v311 + 16LL))(v311);
      }
      v312 = v457;
      if ( v457 )
      {
        v457 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v312 + 16LL))(v312);
      }
      v313 = v458;
      if ( v458 )
      {
        v458 = 0;
        (*(void (__fastcall **)(__int64 *))(*v313 + 16))(v313);
      }
      v314 = v456;
      if ( v456 )
      {
        v456 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v314 + 16LL))(v314);
      }
      v315 = v454;
      if ( v454 )
      {
        v454 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v315 + 16LL))(v315);
      }
      v316 = v455;
      if ( v455 )
      {
        v455 = 0;
        ((void (__fastcall *)(struct IRegisteredTask *))v316->lpVtbl->Release)(v316);
      }
      v317 = v453;
      if ( v453 )
      {
        v453 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v317 + 16LL))(v317);
      }
      v318 = v452;
      if ( v452 )
      {
        v452 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v318 + 16LL))(v318);
      }
      return v5;
    }
    v465 = 0;
    v319 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v454 + 72LL))(v454, &v465);
    v5 = v319;
    if ( v319 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5D,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
        (const char *)(unsigned int)v319,
        (int)ppva);
      v320 = v465;
      if ( v465 )
      {
        v465 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v320 + 16LL))(v320);
      }
      v321 = v463;
      if ( v463 )
      {
        v463 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v321 + 16LL))(v321);
      }
      v322 = v462;
      if ( v462 )
      {
        v462 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v322)[2])(v322);
      }
      v323 = v461;
      if ( v461 )
      {
        v461 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v323 + 16LL))(v323);
      }
      v324 = v460;
      if ( v460 )
      {
        v460 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v324 + 16LL))(v324);
      }
      v325 = v459;
      if ( v459 )
      {
        v459 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v325 + 16LL))(v325);
      }
      v326 = v457;
      if ( v457 )
      {
        v457 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v326 + 16LL))(v326);
      }
      v327 = v458;
      if ( v458 )
      {
        v458 = 0;
        (*(void (__fastcall **)(__int64 *))(*v327 + 16))(v327);
      }
      v328 = v456;
      if ( v456 )
      {
        v456 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v328 + 16LL))(v328);
      }
      v329 = v454;
      if ( v454 )
      {
        v454 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v329 + 16LL))(v329);
      }
      v330 = v455;
      if ( v455 )
      {
        v455 = 0;
        ((void (__fastcall *)(struct IRegisteredTask *))v330->lpVtbl->Release)(v330);
      }
      v331 = v453;
      if ( v453 )
      {
        v453 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v331 + 16LL))(v331);
      }
      v332 = v452;
      if ( v452 )
      {
        v452 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v332 + 16LL))(v332);
      }
      return v5;
    }
    v467 = 0;
    v333 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v465 + 80LL))(v465, 8, &v467);
    v5 = v333;
    if ( v333 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5F,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
        (const char *)(unsigned int)v333,
        (int)ppva);
      v334 = (__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *))v467;
      if ( v467 )
      {
        v467 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v334)[2])(v334);
      }
      v335 = v465;
      if ( v465 )
      {
        v465 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v335 + 16LL))(v335);
      }
      v336 = v463;
      if ( v463 )
      {
        v463 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v336 + 16LL))(v336);
      }
      v337 = v462;
      if ( v462 )
      {
        v462 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v337)[2])(v337);
      }
      v338 = v461;
      if ( v461 )
      {
        v461 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v338 + 16LL))(v338);
      }
      v339 = v460;
      if ( v460 )
      {
        v460 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v339 + 16LL))(v339);
      }
      v340 = v459;
      if ( v459 )
      {
        v459 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v340 + 16LL))(v340);
      }
      v341 = v457;
      if ( v457 )
      {
        v457 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v341 + 16LL))(v341);
      }
      v342 = v458;
      if ( v458 )
      {
        v458 = 0;
        (*(void (__fastcall **)(__int64 *))(*v342 + 16))(v342);
      }
      v343 = v456;
      if ( v456 )
      {
        v456 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v343 + 16LL))(v343);
      }
      v344 = v454;
      if ( v454 )
      {
        v454 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v344 + 16LL))(v344);
      }
      v345 = v455;
      if ( v455 )
      {
        v455 = 0;
        ((void (__fastcall *)(struct IRegisteredTask *))v345->lpVtbl->Release)(v345);
      }
      v346 = v453;
      if ( v453 )
      {
        v453 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v346 + 16LL))(v346);
      }
      v347 = v452;
      if ( v452 )
      {
        v452 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v347 + 16LL))(v347);
      }
      return v5;
    }
    v464 = 0;
    v348 = (**v467)(v467, &GUID_2a9c35da_d357_41f4_bbc1_207ac1b1f3cb, &v464);
    v5 = v348;
    if ( v348 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x61,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
        (const char *)(unsigned int)v348,
        (int)ppva);
      v349 = v464;
      if ( v464 )
      {
        v464 = 0;
        (*(void (__fastcall **)(__int64 *))(*v349 + 16))(v349);
      }
      v350 = (__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *))v467;
      if ( v467 )
      {
        v467 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v350)[2])(v350);
      }
      v351 = v465;
      if ( v465 )
      {
        v465 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v351 + 16LL))(v351);
      }
      v352 = v463;
      if ( v463 )
      {
        v463 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v352 + 16LL))(v352);
      }
      v353 = v462;
      if ( v462 )
      {
        v462 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v353)[2])(v353);
      }
      v354 = v461;
      if ( v461 )
      {
        v461 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v354 + 16LL))(v354);
      }
      v355 = v460;
      if ( v460 )
      {
        v460 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v355 + 16LL))(v355);
      }
      v356 = v459;
      if ( v459 )
      {
        v459 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v356 + 16LL))(v356);
      }
      v357 = v457;
      if ( v457 )
      {
        v457 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v357 + 16LL))(v357);
      }
      v358 = v458;
      if ( v458 )
      {
        v458 = 0;
        (*(void (__fastcall **)(__int64 *))(*v358 + 16))(v358);
      }
      v359 = v456;
      if ( v456 )
      {
        v456 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v359 + 16LL))(v359);
      }
      v360 = v454;
      if ( v454 )
      {
        v454 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v360 + 16LL))(v360);
      }
      v361 = v455;
      if ( v455 )
      {
        v455 = 0;
        ((void (__fastcall *)(struct IRegisteredTask *))v361->lpVtbl->Release)(v361);
      }
      v362 = v453;
      if ( v453 )
      {
        v453 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v362 + 16LL))(v362);
      }
      v363 = v452;
      if ( v452 )
      {
        v452 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v363 + 16LL))(v363);
      }
      return v5;
    }
    v364 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v464 + 152))(v464, 0xFFFFFFFFLL);
    v5 = v364;
    if ( v364 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x62,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
        (const char *)(unsigned int)v364,
        (int)ppva);
      v365 = v464;
      if ( v464 )
      {
        v464 = 0;
        (*(void (__fastcall **)(__int64 *))(*v365 + 16))(v365);
      }
      v366 = (__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *))v467;
      if ( v467 )
      {
        v467 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v366)[2])(v366);
      }
      v367 = v465;
      if ( v465 )
      {
        v465 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v367 + 16LL))(v367);
      }
      v368 = v463;
      if ( v463 )
      {
        v463 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v368 + 16LL))(v368);
      }
      v369 = v462;
      if ( v462 )
      {
        v462 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v369)[2])(v369);
      }
      v370 = v461;
      if ( v461 )
      {
        v461 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v370 + 16LL))(v370);
      }
      v371 = v460;
      if ( v460 )
      {
        v460 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v371 + 16LL))(v371);
      }
      v372 = v459;
      if ( v459 )
      {
        v459 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v372 + 16LL))(v372);
      }
      v373 = v457;
      if ( v457 )
      {
        v457 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v373 + 16LL))(v373);
      }
      v374 = v458;
      if ( v458 )
      {
        v458 = 0;
        (*(void (__fastcall **)(__int64 *))(*v374 + 16))(v374);
      }
      v375 = v456;
      if ( v456 )
      {
        v456 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v375 + 16LL))(v375);
      }
      v376 = v454;
      if ( v454 )
      {
        v454 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v376 + 16LL))(v376);
      }
      v377 = v455;
      if ( v455 )
      {
        v455 = 0;
        ((void (__fastcall *)(struct IRegisteredTask *))v377->lpVtbl->Release)(v377);
      }
      v378 = v453;
      if ( v453 )
      {
        v453 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v378 + 16LL))(v378);
      }
      v379 = v452;
      if ( v452 )
      {
        v452 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v379 + 16LL))(v379);
      }
      return v5;
    }
    v466 = 0;
    v380 = v453;
    v381 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v453 + 136LL);
    VariantInit(&v471);
    v382 = *(_OWORD *)&v471.vt;
    v383 = v471.pRecInfo;
    VariantInit(&v472);
    v384 = *(_OWORD *)&v472.vt;
    v385 = v472.pRecInfo;
    VariantInit(&pvarg);
    v386 = *(_OWORD *)&pvarg.vt;
    v387 = pvarg.pRecInfo;
    v388 = v454;
    v389 = _bstr_t::_bstr_t((_bstr_t *)&v468, this[1]);
    if ( *(_QWORD *)v389 )
      v390 = **(_QWORD **)v389;
    else
      v390 = 0;
    *(_OWORD *)&v470.vt = v382;
    v470.pRecInfo = v383;
    v476 = v384;
    v477 = v385;
    *(_OWORD *)v474 = v386;
    v475 = v387;
    v5 = v381(v380, v390, v388, 2);
    _bstr_t::~_bstr_t((_bstr_t *)&v468);
    v391 = VariantClear(&pvarg);
    if ( v391 < 0 )
      _com_issue_error(v391);
    v392 = VariantClear(&v472);
    if ( v392 < 0 )
      _com_issue_error(v392);
    v393 = VariantClear(&v471);
    if ( v393 < 0 )
      _com_issue_error(v393);
    if ( (v5 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6E,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
        (const char *)v5,
        (int)v474);
      v394 = v466;
      if ( v466 )
      {
        v466 = 0;
        (*((void (__fastcall **)(BSTR *))*v394 + 2))(v394);
      }
      v395 = v464;
      if ( v464 )
      {
        v464 = 0;
        (*(void (__fastcall **)(__int64 *))(*v395 + 16))(v395);
      }
      v396 = (__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *))v467;
      if ( v467 )
      {
        v467 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v396)[2])(v396);
      }
      v397 = v465;
      if ( v465 )
      {
        v465 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v397 + 16LL))(v397);
      }
      v398 = v463;
      if ( v463 )
      {
        v463 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v398 + 16LL))(v398);
      }
      v399 = v462;
      if ( v462 )
      {
        v462 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v399)[2])(v399);
      }
      v400 = v461;
      if ( v461 )
      {
        v461 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v400 + 16LL))(v400);
      }
      v401 = v460;
      if ( v460 )
      {
        v460 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v401 + 16LL))(v401);
      }
      v402 = v459;
      if ( v459 )
      {
        v459 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v402 + 16LL))(v402);
      }
      v403 = v457;
      if ( v457 )
      {
        v457 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v403 + 16LL))(v403);
      }
      v404 = v458;
      if ( v458 )
      {
        v458 = 0;
        (*(void (__fastcall **)(__int64 *))(*v404 + 16))(v404);
      }
      v405 = v456;
      if ( v456 )
      {
        v456 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v405 + 16LL))(v405);
      }
      v406 = v454;
      if ( v454 )
      {
        v454 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v406 + 16LL))(v406);
      }
      v407 = v455;
      if ( v455 )
      {
        v455 = 0;
        ((void (__fastcall *)(struct IRegisteredTask *))v407->lpVtbl->Release)(v407);
      }
      v408 = v453;
      if ( v453 )
      {
        v453 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v408 + 16LL))(v408);
      }
      v409 = v452;
      if ( v452 )
      {
        v452 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v409 + 16LL))(v409);
      }
      return v5;
    }
    v410 = v453;
    v411 = *(__int64 (__fastcall **)(__int64, __int64, struct IRegisteredTask **))(*(_QWORD *)v453 + 104LL);
    v412 = v455;
    if ( v455 )
    {
      v455 = 0;
      ((void (__fastcall *)(struct IRegisteredTask *))v412->lpVtbl->Release)(v412);
    }
    v413 = _bstr_t::_bstr_t((_bstr_t *)&v468, this[1]);
    if ( *(_QWORD *)v413 )
      v414 = **(_QWORD **)v413;
    else
      v414 = 0;
    v5 = v411(v410, v414, &v455);
    _bstr_t::~_bstr_t((_bstr_t *)&v468);
    if ( (v5 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x70,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
        (const char *)v5,
        (int)v474);
      v415 = v466;
      if ( v466 )
      {
        v466 = 0;
        (*((void (__fastcall **)(BSTR *))*v415 + 2))(v415);
      }
      v416 = v464;
      if ( v464 )
      {
        v464 = 0;
        (*(void (__fastcall **)(__int64 *))(*v416 + 16))(v416);
      }
      v417 = (__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *))v467;
      if ( v467 )
      {
        v467 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v417)[2])(v417);
      }
      v418 = v465;
      if ( v465 )
      {
        v465 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v418 + 16LL))(v418);
      }
      v419 = v463;
      if ( v463 )
      {
        v463 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v419 + 16LL))(v419);
      }
      v420 = v462;
      if ( v462 )
      {
        v462 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v420)[2])(v420);
      }
      v421 = v461;
      if ( v461 )
      {
        v461 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v421 + 16LL))(v421);
      }
      v422 = v460;
      if ( v460 )
      {
        v460 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v422 + 16LL))(v422);
      }
      v423 = v459;
      if ( v459 )
      {
        v459 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v423 + 16LL))(v423);
      }
      v424 = v457;
      if ( v457 )
      {
        v457 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v424 + 16LL))(v424);
      }
      v425 = v458;
      if ( v458 )
      {
        v458 = 0;
        (*(void (__fastcall **)(__int64 *))(*v425 + 16))(v425);
      }
      v426 = v456;
      if ( v456 )
      {
        v456 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v426 + 16LL))(v426);
      }
      v427 = v454;
      if ( v454 )
      {
        v454 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v427 + 16LL))(v427);
      }
      v428 = v455;
      if ( v455 )
      {
        v455 = 0;
        ((void (__fastcall *)(struct IRegisteredTask *))v428->lpVtbl->Release)(v428);
      }
      v429 = v453;
      if ( v453 )
      {
        v453 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v429 + 16LL))(v429);
      }
      v430 = v452;
      if ( v452 )
      {
        v452 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v430 + 16LL))(v430);
      }
      return v5;
    }
    v431 = v466;
    if ( v466 )
    {
      v466 = 0;
      (*((void (__fastcall **)(BSTR *))*v431 + 2))(v431);
    }
    v432 = v464;
    if ( v464 )
    {
      v464 = 0;
      (*(void (__fastcall **)(__int64 *))(*v432 + 16))(v432);
    }
    v433 = (__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *))v467;
    if ( v467 )
    {
      v467 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v433)[2])(v433);
    }
    v434 = v465;
    if ( v465 )
    {
      v465 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v434 + 16LL))(v434);
    }
    v435 = v463;
    if ( v463 )
    {
      v463 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v435 + 16LL))(v435);
    }
    v436 = v462;
    if ( v462 )
    {
      v462 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v436)[2])(v436);
    }
    v437 = v461;
    if ( v461 )
    {
      v461 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v437 + 16LL))(v437);
    }
    v438 = v460;
    if ( v460 )
    {
      v460 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v438 + 16LL))(v438);
    }
    v439 = v459;
    if ( v459 )
    {
      v459 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v439 + 16LL))(v439);
    }
    v440 = v457;
    if ( v457 )
    {
      v457 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v440 + 16LL))(v440);
    }
    v441 = v458;
    if ( v458 )
    {
      v458 = 0;
      (*(void (__fastcall **)(__int64 *))(*v441 + 16))(v441);
    }
    v442 = v456;
    if ( v456 )
    {
      v456 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v442 + 16LL))(v442);
    }
    v443 = v454;
    if ( v454 )
    {
      v454 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v443 + 16LL))(v443);
    }
  }
  v444 = v455;
  v455 = 0;
  *a2 = v444;
  v445 = v453;
  if ( v453 )
  {
    v453 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v445 + 16LL))(v445);
  }
  v446 = v452;
  if ( v452 )
  {
    v452 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v446 + 16LL))(v446);
  }
  return 0;
}

```

## disassembly

```asm
0x18003c52c  mov     rax, rsp
0x18003c52f  mov     [rax+18h], rbx
0x18003c533  push    rbp
0x18003c534  push    rsi
0x18003c535  push    rdi
0x18003c536  push    r12
0x18003c538  push    r13
0x18003c53a  push    r14
0x18003c53c  push    r15
0x18003c53e  lea     rbp, [rax-378h]
0x18003c545  sub     rsp, 440h
0x18003c54c  movaps  xmmword ptr [rax-48h], xmm6
0x18003c550  movaps  xmmword ptr [rax-58h], xmm7
0x18003c554  movaps  xmmword ptr [rax-68h], xmm8
0x18003c559  movaps  xmmword ptr [rax-78h], xmm9
0x18003c55e  movaps  xmmword ptr [rax-88h], xmm10
0x18003c566  movaps  xmmword ptr [rax-98h], xmm11
0x18003c56e  mov     rax, cs:__security_cookie
0x18003c575  xor     rax, rsp
0x18003c578  mov     [rbp+370h+var_A0], rax
0x18003c57f  mov     r12, rdx
0x18003c582  mov     r14, rcx
0x18003c585  xor     r13d, r13d
0x18003c588  mov     [rdx], r13
0x18003c58b  mov     [rsp+470h+var_420], r13
0x18003c590  lea     rax, [rsp+470h+var_420]
0x18003c595  mov     [rsp+470h+ppv], rax; int
0x18003c59a  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x18003c5a1  xor     edx, edx; pUnkOuter
0x18003c5a3  lea     r8d, [r13+1]; dwClsContext
0x18003c5a7  lea     rcx, CLSID_TaskScheduler; rclsid
0x18003c5ae  call    cs:__imp_CoCreateInstance
0x18003c5b5  nop     dword ptr [rax+rax+00h]
0x18003c5ba  mov     edi, eax
0x18003c5bc  test    eax, eax
0x18003c5be  jns     short loc_18003C5FE
0x18003c5c0  mov     rcx, [rbp+378h]; this
0x18003c5c7  mov     r9d, eax; char *
0x18003c5ca  lea     r8, aOnecoreBaseNgs_5; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18003c5d1  lea     edx, [r13+14h]; void *
0x18003c5d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c5da  nop
0x18003c5db  mov     rcx, [rsp+470h+var_420]
0x18003c5e0  test    rcx, rcx
0x18003c5e3  jz      short loc_18003C5F7
0x18003c5e5  mov     [rsp+470h+var_420], r13
0x18003c5ea  mov     rax, [rcx]
0x18003c5ed  mov     rax, [rax+10h]
0x18003c5f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c5f6  nop
0x18003c5f7  mov     eax, edi
0x18003c5f9  jmp     loc_18003F9D5
0x18003c5fe  mov     rdi, [rsp+470h+var_420]
0x18003c603  mov     rax, [rdi]
0x18003c606  mov     rbx, [rax+50h]
0x18003c60a  lea     rcx, [rbp+370h+pvarg]; pvarg
0x18003c60e  call    cs:__imp_VariantInit
0x18003c615  nop     dword ptr [rax+rax+00h]
0x18003c61a  nop
0x18003c61b  movups  xmm10, xmmword ptr [rbp+370h+pvarg]
0x18003c620  movsd   xmm11, qword ptr [rbp+370h+pvarg+10h]
0x18003c626  lea     rcx, [rbp+370h+var_348]; pvarg
0x18003c62a  call    cs:__imp_VariantInit
0x18003c631  nop     dword ptr [rax+rax+00h]
0x18003c636  nop
0x18003c637  movups  xmm8, xmmword ptr [rbp+370h+var_348]
0x18003c63c  movsd   xmm9, qword ptr [rbp+370h+var_348+10h]
0x18003c642  lea     rcx, [rbp+370h+var_360]; pvarg
0x18003c646  call    cs:__imp_VariantInit
0x18003c64d  nop     dword ptr [rax+rax+00h]
0x18003c652  nop
0x18003c653  movups  xmm6, xmmword ptr [rbp+370h+var_360]
0x18003c657  movsd   xmm7, qword ptr [rbp+370h+var_360+10h]
0x18003c65c  lea     rcx, [rbp+370h+var_398]; pvarg
0x18003c660  call    cs:__imp_VariantInit
0x18003c667  nop     dword ptr [rax+rax+00h]
0x18003c66c  nop
0x18003c66d  movups  xmm0, xmmword ptr [rbp+370h+var_398]
0x18003c671  movsd   xmm1, qword ptr [rbp+370h+var_398+10h]
0x18003c676  movaps  xmmword ptr [rbp+370h+var_2D0], xmm10
0x18003c67e  movsd   [rbp+370h+var_2C0], xmm11
0x18003c687  movaps  xmmword ptr [rbp+370h+var_310], xmm8
0x18003c68c  movsd   [rbp+370h+var_300], xmm9
0x18003c692  movaps  [rbp+370h+var_2F0], xmm6
0x18003c699  movsd   [rbp+370h+var_2E0], xmm7
0x18003c6a1  movaps  [rbp+370h+var_380], xmm0
0x18003c6a5  movsd   [rbp+370h+var_370], xmm1
0x18003c6aa  lea     rax, [rbp+370h+var_2D0]
0x18003c6b1  mov     [rsp+470h+ppv], rax; int
0x18003c6b6  lea     r9, [rbp+370h+var_310]
0x18003c6ba  lea     r8, [rbp+370h+var_2F0]
0x18003c6c1  lea     rdx, [rbp+370h+var_380]
0x18003c6c5  mov     rcx, rdi
0x18003c6c8  mov     rax, rbx
0x18003c6cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c6d0  mov     edi, eax
0x18003c6d2  lea     rcx, [rbp+370h+var_398]; pvarg
0x18003c6d6  call    cs:__imp_VariantClear
0x18003c6dd  nop     dword ptr [rax+rax+00h]
0x18003c6e2  test    eax, eax
0x18003c6e4  js      loc_18003FA9F
0x18003c6ea  lea     rcx, [rbp+370h+var_360]; pvarg
0x18003c6ee  call    cs:__imp_VariantClear
0x18003c6f5  nop     dword ptr [rax+rax+00h]
0x18003c6fa  test    eax, eax
0x18003c6fc  js      loc_18003FAA7
0x18003c702  lea     rcx, [rbp+370h+var_348]; pvarg
0x18003c706  call    cs:__imp_VariantClear
0x18003c70d  nop     dword ptr [rax+rax+00h]
0x18003c712  test    eax, eax
0x18003c714  js      loc_18003FAAF
0x18003c71a  lea     rcx, [rbp+370h+pvarg]; pvarg
0x18003c71e  call    cs:__imp_VariantClear
0x18003c725  nop     dword ptr [rax+rax+00h]
0x18003c72a  test    eax, eax
0x18003c72c  js      loc_18003FAB7
0x18003c732  test    edi, edi
0x18003c734  jns     short loc_18003C773
0x18003c736  mov     rcx, [rbp+378h]; this
0x18003c73d  mov     r9d, edi; char *
0x18003c740  lea     r8, aOnecoreBaseNgs_5; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18003c747  mov     edx, 15h; void *
0x18003c74c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c751  nop
0x18003c752  mov     rcx, [rsp+470h+var_420]
0x18003c757  test    rcx, rcx
0x18003c75a  jz      short loc_18003C76E
0x18003c75c  mov     [rsp+470h+var_420], r13
0x18003c761  mov     rax, [rcx]
0x18003c764  mov     rax, [rax+10h]
0x18003c768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c76d  nop
0x18003c76e  jmp     loc_18003C5F7
0x18003c773  mov     [rsp+470h+var_418], r13
0x18003c778  mov     rdi, [rsp+470h+var_420]
0x18003c77d  mov     rsi, [rdi]
0x18003c780  mov     ecx, 18h; Size
0x18003c785  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003c78a  mov     rbx, rax
0x18003c78d  mov     [rbp+370h+var_3A0], rax
0x18003c791  mov     [rax+8], r13
0x18003c795  mov     dword ptr [rax+10h], 1
0x18003c79c  lea     rcx, psz; "\\Microsoft\\Windows\\PCRPF"
0x18003c7a3  call    cs:__imp_SysAllocString
0x18003c7aa  nop     dword ptr [rax+rax+00h]
0x18003c7af  mov     [rbx], rax
0x18003c7b2  test    rax, rax
0x18003c7b5  jz      loc_18003FABF
0x18003c7bb  mov     [rbp+370h+var_3B0], rbx
0x18003c7bf  lea     r8, [rsp+470h+var_418]
0x18003c7c4  mov     rdx, rax
0x18003c7c7  mov     rcx, rdi
0x18003c7ca  mov     rax, [rsi+38h]
0x18003c7ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c7d3  mov     edi, eax
0x18003c7d5  lea     rcx, [rbp+370h+var_3B0]; this
0x18003c7d9  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18003c7de  lea     ecx, [rdi+7FF8FFFEh]
0x18003c7e4  lea     rbx, aOnecoreBaseNgs_5; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18003c7eb  cmp     ecx, 1
0x18003c7ee  ja      loc_18003CA7B
0x18003c7f4  lea     r9, aCreatingPcrpfT; "Creating PCRPF tasks folder"
0x18003c7fb  lea     r8, aPpfscheduledta_2; "PpfScheduledTask::GetTask"
0x18003c802  mov     edx, 1Bh; unsigned int
0x18003c807  mov     rcx, rbx; char *
0x18003c80a  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18003c80f  mov     [rbp+370h+var_3C0], r13
0x18003c813  mov     rsi, [rsp+470h+var_420]
0x18003c818  mov     r15, [rsi]
0x18003c81b  mov     ecx, 18h; Size
0x18003c820  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003c825  mov     rdi, rax
0x18003c828  mov     [rbp+370h+var_3A0], rax
0x18003c82c  mov     [rax+8], r13
0x18003c830  mov     dword ptr [rax+10h], 1
0x18003c837  lea     rcx, asc_18005C2E0; "\\"
0x18003c83e  call    cs:__imp_SysAllocString
0x18003c845  nop     dword ptr [rax+rax+00h]
0x18003c84a  mov     [rdi], rax
0x18003c84d  test    rax, rax
0x18003c850  jz      loc_18003FACA
0x18003c856  mov     [rbp+370h+var_3B0], rdi
0x18003c85a  lea     r8, [rbp+370h+var_3C0]
0x18003c85e  mov     rdx, rax
0x18003c861  mov     rcx, rsi
0x18003c864  mov     rax, [r15+38h]
0x18003c868  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c86d  mov     edi, eax
0x18003c86f  lea     rcx, [rbp+370h+var_3B0]; this
0x18003c873  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18003c878  test    edi, edi
0x18003c87a  jns     short loc_18003C8EB
0x18003c87c  mov     rcx, [rbp+378h]; this
0x18003c883  mov     r9d, edi; char *
0x18003c886  mov     r8, rbx; unsigned int
0x18003c889  mov     edx, 1Dh; void *
0x18003c88e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c893  nop
0x18003c894  mov     rcx, [rbp+370h+var_3C0]
0x18003c898  test    rcx, rcx
0x18003c89b  jz      short loc_18003C8AE
0x18003c89d  mov     [rbp+370h+var_3C0], r13
0x18003c8a1  mov     rax, [rcx]
0x18003c8a4  mov     rax, [rax+10h]
0x18003c8a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c8ad  nop
0x18003c8ae  mov     rcx, [rsp+470h+var_418]
0x18003c8b3  test    rcx, rcx
0x18003c8b6  jz      short loc_18003C8CA
0x18003c8b8  mov     [rsp+470h+var_418], r13
0x18003c8bd  mov     rax, [rcx]
0x18003c8c0  mov     rax, [rax+10h]
0x18003c8c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c8c9  nop
0x18003c8ca  mov     rcx, [rsp+470h+var_420]
0x18003c8cf  test    rcx, rcx
0x18003c8d2  jz      short loc_18003C8E6
0x18003c8d4  mov     [rsp+470h+var_420], r13
0x18003c8d9  mov     rax, [rcx]
0x18003c8dc  mov     rax, [rax+10h]
0x18003c8e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c8e5  nop
0x18003c8e6  jmp     loc_18003C5F7
0x18003c8eb  mov     rsi, [rbp+370h+var_3C0]
0x18003c8ef  mov     r15, [rsi]
0x18003c8f2  mov     rcx, [rsp+470h+var_418]
0x18003c8f7  test    rcx, rcx
0x18003c8fa  jz      short loc_18003C90E
0x18003c8fc  mov     [rsp+470h+var_418], r13
0x18003c901  mov     rax, [rcx]
0x18003c904  mov     rax, [rax+10h]
0x18003c908  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c90d  nop
0x18003c90e  lea     rcx, Format; psz
0x18003c915  call    cs:__imp_SysAllocString
0x18003c91c  nop     dword ptr [rax+rax+00h]
0x18003c921  test    rax, rax
0x18003c924  jz      loc_18003FAD5
0x18003c92a  mov     edx, 8
0x18003c92f  mov     word ptr [rbp+370h+var_398], dx
0x18003c933  mov     qword ptr [rbp+370h+var_398+8], rax
0x18003c937  movups  xmm6, xmmword ptr [rbp+370h+var_398]
0x18003c93b  movsd   xmm7, qword ptr [rbp+370h+var_398+10h]
0x18003c940  lea     ecx, [rdx+10h]; Size
0x18003c943  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003c948  mov     rdi, rax
0x18003c94b  mov     [rbp+370h+var_3A0], rax
0x18003c94f  mov     [rax+8], r13
0x18003c953  mov     dword ptr [rax+10h], 1
0x18003c95a  lea     rcx, psz; "\\Microsoft\\Windows\\PCRPF"
0x18003c961  call    cs:__imp_SysAllocString
0x18003c968  nop     dword ptr [rax+rax+00h]
0x18003c96d  mov     [rdi], rax
0x18003c970  test    rax, rax
0x18003c973  jz      loc_18003FAE0
0x18003c979  mov     [rbp+370h+var_3B0], rdi
0x18003c97d  movaps  [rbp+370h+var_380], xmm6
0x18003c981  movsd   [rbp+370h+var_370], xmm7
0x18003c986  lea     r9, [rsp+470h+var_418]
0x18003c98b  lea     r8, [rbp+370h+var_380]
0x18003c98f  mov     rdx, rax
0x18003c992  mov     rcx, rsi
0x18003c995  mov     rax, [r15+58h]
0x18003c999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c99e  mov     edi, eax
0x18003c9a0  lea     rcx, [rbp+370h+var_3B0]; this
0x18003c9a4  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18003c9a9  nop
0x18003c9aa  lea     rcx, [rbp+370h+var_398]; pvarg
0x18003c9ae  call    cs:__imp_VariantClear
0x18003c9b5  nop     dword ptr [rax+rax+00h]
0x18003c9ba  test    eax, eax
0x18003c9bc  js      loc_18003FAEB
0x18003c9c2  test    edi, edi
0x18003c9c4  jns     short loc_18003CA35
0x18003c9c6  mov     rcx, [rbp+378h]; this
0x18003c9cd  mov     r9d, edi; char *
0x18003c9d0  mov     r8, rbx; unsigned int
0x18003c9d3  mov     edx, 1Eh; void *
0x18003c9d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c9dd  nop
0x18003c9de  mov     rcx, [rbp+370h+var_3C0]
0x18003c9e2  test    rcx, rcx
0x18003c9e5  jz      short loc_18003C9F8
0x18003c9e7  mov     [rbp+370h+var_3C0], r13
0x18003c9eb  mov     rax, [rcx]
0x18003c9ee  mov     rax, [rax+10h]
0x18003c9f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c9f7  nop
0x18003c9f8  mov     rcx, [rsp+470h+var_418]
0x18003c9fd  test    rcx, rcx
0x18003ca00  jz      short loc_18003CA14
0x18003ca02  mov     [rsp+470h+var_418], r13
0x18003ca07  mov     rax, [rcx]
0x18003ca0a  mov     rax, [rax+10h]
0x18003ca0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ca13  nop
0x18003ca14  mov     rcx, [rsp+470h+var_420]
0x18003ca19  test    rcx, rcx
0x18003ca1c  jz      short loc_18003CA30
  ... truncated ...
```
