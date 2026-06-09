# _dynamic_initializer_for__g_msgIdToNameMap__

- ea: `0x140025fb0`
- end: `0x1400269a9`
- name: `_dynamic_initializer_for__g_msgIdToNameMap__`
- size: `2553`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x140003160`
- `0x14000f630`
- `0x140017b90`
- `0x140026b04`

## string_xrefs

- `0x140025fdf`: `WM_MOVE`
- `0x1400260b8`: `WM_NCMOUSEMOVE`
- `0x1400262c3`: `WM_IME_STARTCOMPOSITION`
- `0x1400262e0`: `WM_IME_ENDCOMPOSITION`
- `0x1400262fd`: `WM_COMMAND`
- `0x14002631a`: `WM_SYSCOMMAND`
- `0x140026379`: `WM_MOUSEMOVE`
- `0x140026593`: `WM_NCPOINTERUPDATE`
- `0x1400265ea`: `WM_POINTERUPDATE`
- `0x14002689d`: `WM_TABLET_DELETED`

## pseudocode

```c
// Hidden C++ exception states: #wind=86
int dynamic_initializer_for__g_msgIdToNameMap__()
{
  _QWORD v1[2]; // [rsp+20h] [rbp-E0h] BYREF
  int v2; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v3[8]; // [rsp+38h] [rbp-C8h] BYREF
  int v4; // [rsp+40h] [rbp-C0h]
  _BYTE v5[8]; // [rsp+48h] [rbp-B8h] BYREF
  int v6; // [rsp+50h] [rbp-B0h]
  _BYTE v7[8]; // [rsp+58h] [rbp-A8h] BYREF
  int v8; // [rsp+60h] [rbp-A0h]
  _BYTE v9[8]; // [rsp+68h] [rbp-98h] BYREF
  int v10; // [rsp+70h] [rbp-90h]
  _BYTE v11[8]; // [rsp+78h] [rbp-88h] BYREF
  int v12; // [rsp+80h] [rbp-80h]
  _BYTE v13[8]; // [rsp+88h] [rbp-78h] BYREF
  int v14; // [rsp+90h] [rbp-70h]
  _BYTE v15[8]; // [rsp+98h] [rbp-68h] BYREF
  int v16; // [rsp+A0h] [rbp-60h]
  _BYTE v17[8]; // [rsp+A8h] [rbp-58h] BYREF
  int v18; // [rsp+B0h] [rbp-50h]
  _BYTE v19[8]; // [rsp+B8h] [rbp-48h] BYREF
  int v20; // [rsp+C0h] [rbp-40h]
  _BYTE v21[8]; // [rsp+C8h] [rbp-38h] BYREF
  int v22; // [rsp+D0h] [rbp-30h]
  _BYTE v23[8]; // [rsp+D8h] [rbp-28h] BYREF
  int v24; // [rsp+E0h] [rbp-20h]
  _BYTE v25[8]; // [rsp+E8h] [rbp-18h] BYREF
  int v26; // [rsp+F0h] [rbp-10h]
  _BYTE v27[8]; // [rsp+F8h] [rbp-8h] BYREF
  int v28; // [rsp+100h] [rbp+0h]
  _BYTE v29[8]; // [rsp+108h] [rbp+8h] BYREF
  int v30; // [rsp+110h] [rbp+10h]
  _BYTE v31[8]; // [rsp+118h] [rbp+18h] BYREF
  int v32; // [rsp+120h] [rbp+20h]
  _BYTE v33[8]; // [rsp+128h] [rbp+28h] BYREF
  int v34; // [rsp+130h] [rbp+30h]
  _BYTE v35[8]; // [rsp+138h] [rbp+38h] BYREF
  int v36; // [rsp+140h] [rbp+40h]
  _BYTE v37[8]; // [rsp+148h] [rbp+48h] BYREF
  int v38; // [rsp+150h] [rbp+50h]
  _BYTE v39[8]; // [rsp+158h] [rbp+58h] BYREF
  int v40; // [rsp+160h] [rbp+60h]
  _BYTE v41[8]; // [rsp+168h] [rbp+68h] BYREF
  int v42; // [rsp+170h] [rbp+70h]
  _BYTE v43[8]; // [rsp+178h] [rbp+78h] BYREF
  int v44; // [rsp+180h] [rbp+80h]
  _BYTE v45[8]; // [rsp+188h] [rbp+88h] BYREF
  int v46; // [rsp+190h] [rbp+90h]
  _BYTE v47[8]; // [rsp+198h] [rbp+98h] BYREF
  int v48; // [rsp+1A0h] [rbp+A0h]
  _BYTE v49[8]; // [rsp+1A8h] [rbp+A8h] BYREF
  int v50; // [rsp+1B0h] [rbp+B0h]
  _BYTE v51[8]; // [rsp+1B8h] [rbp+B8h] BYREF
  int v52; // [rsp+1C0h] [rbp+C0h]
  _BYTE v53[8]; // [rsp+1C8h] [rbp+C8h] BYREF
  int v54; // [rsp+1D0h] [rbp+D0h]
  _BYTE v55[8]; // [rsp+1D8h] [rbp+D8h] BYREF
  int v56; // [rsp+1E0h] [rbp+E0h]
  _BYTE v57[8]; // [rsp+1E8h] [rbp+E8h] BYREF
  int v58; // [rsp+1F0h] [rbp+F0h]
  _BYTE v59[8]; // [rsp+1F8h] [rbp+F8h] BYREF
  int v60; // [rsp+200h] [rbp+100h]
  _BYTE v61[8]; // [rsp+208h] [rbp+108h] BYREF
  int v62; // [rsp+210h] [rbp+110h]
  _BYTE v63[8]; // [rsp+218h] [rbp+118h] BYREF
  int v64; // [rsp+220h] [rbp+120h]
  _BYTE v65[8]; // [rsp+228h] [rbp+128h] BYREF
  int v66; // [rsp+230h] [rbp+130h]
  _BYTE v67[8]; // [rsp+238h] [rbp+138h] BYREF
  int v68; // [rsp+240h] [rbp+140h]
  _BYTE v69[8]; // [rsp+248h] [rbp+148h] BYREF
  int v70; // [rsp+250h] [rbp+150h]
  _BYTE v71[8]; // [rsp+258h] [rbp+158h] BYREF
  int v72; // [rsp+260h] [rbp+160h]
  _BYTE v73[8]; // [rsp+268h] [rbp+168h] BYREF
  int v74; // [rsp+270h] [rbp+170h]
  _BYTE v75[8]; // [rsp+278h] [rbp+178h] BYREF
  int v76; // [rsp+280h] [rbp+180h]
  _BYTE v77[8]; // [rsp+288h] [rbp+188h] BYREF
  int v78; // [rsp+290h] [rbp+190h]
  _BYTE v79[8]; // [rsp+298h] [rbp+198h] BYREF
  int v80; // [rsp+2A0h] [rbp+1A0h]
  _BYTE v81[8]; // [rsp+2A8h] [rbp+1A8h] BYREF
  int v82; // [rsp+2B0h] [rbp+1B0h]
  _BYTE v83[8]; // [rsp+2B8h] [rbp+1B8h] BYREF
  int v84; // [rsp+2C0h] [rbp+1C0h]
  _BYTE v85[8]; // [rsp+2C8h] [rbp+1C8h] BYREF
  int v86; // [rsp+2D0h] [rbp+1D0h]
  _BYTE v87[8]; // [rsp+2D8h] [rbp+1D8h] BYREF
  int v88; // [rsp+2E0h] [rbp+1E0h]
  _BYTE v89[8]; // [rsp+2E8h] [rbp+1E8h] BYREF
  int v90; // [rsp+2F0h] [rbp+1F0h]
  _BYTE v91[8]; // [rsp+2F8h] [rbp+1F8h] BYREF
  int v92; // [rsp+300h] [rbp+200h]
  _BYTE v93[8]; // [rsp+308h] [rbp+208h] BYREF
  int v94; // [rsp+310h] [rbp+210h]
  _BYTE v95[8]; // [rsp+318h] [rbp+218h] BYREF
  int v96; // [rsp+320h] [rbp+220h]
  _BYTE v97[8]; // [rsp+328h] [rbp+228h] BYREF
  int v98; // [rsp+330h] [rbp+230h]
  _BYTE v99[8]; // [rsp+338h] [rbp+238h] BYREF
  int v100; // [rsp+340h] [rbp+240h]
  _BYTE v101[8]; // [rsp+348h] [rbp+248h] BYREF
  int v102; // [rsp+350h] [rbp+250h]
  _BYTE v103[8]; // [rsp+358h] [rbp+258h] BYREF
  int v104; // [rsp+360h] [rbp+260h]
  _BYTE v105[8]; // [rsp+368h] [rbp+268h] BYREF
  int v106; // [rsp+370h] [rbp+270h]
  _BYTE v107[8]; // [rsp+378h] [rbp+278h] BYREF
  int v108; // [rsp+380h] [rbp+280h]
  _BYTE v109[8]; // [rsp+388h] [rbp+288h] BYREF
  int v110; // [rsp+390h] [rbp+290h]
  _BYTE v111[8]; // [rsp+398h] [rbp+298h] BYREF
  int v112; // [rsp+3A0h] [rbp+2A0h]
  _BYTE v113[8]; // [rsp+3A8h] [rbp+2A8h] BYREF
  int v114; // [rsp+3B0h] [rbp+2B0h]
  _BYTE v115[8]; // [rsp+3B8h] [rbp+2B8h] BYREF
  int v116; // [rsp+3C0h] [rbp+2C0h]
  _BYTE v117[8]; // [rsp+3C8h] [rbp+2C8h] BYREF
  int v118; // [rsp+3D0h] [rbp+2D0h]
  _BYTE v119[8]; // [rsp+3D8h] [rbp+2D8h] BYREF
  int v120; // [rsp+3E0h] [rbp+2E0h]
  _BYTE v121[8]; // [rsp+3E8h] [rbp+2E8h] BYREF
  int v122; // [rsp+3F0h] [rbp+2F0h]
  _BYTE v123[8]; // [rsp+3F8h] [rbp+2F8h] BYREF
  int v124; // [rsp+400h] [rbp+300h]
  _BYTE v125[8]; // [rsp+408h] [rbp+308h] BYREF
  int v126; // [rsp+410h] [rbp+310h]
  _BYTE v127[8]; // [rsp+418h] [rbp+318h] BYREF
  int v128; // [rsp+420h] [rbp+320h]
  _BYTE v129[8]; // [rsp+428h] [rbp+328h] BYREF
  int v130; // [rsp+430h] [rbp+330h]
  _BYTE v131[8]; // [rsp+438h] [rbp+338h] BYREF
  int v132; // [rsp+440h] [rbp+340h]
  _BYTE v133[8]; // [rsp+448h] [rbp+348h] BYREF
  int v134; // [rsp+450h] [rbp+350h]
  _BYTE v135[8]; // [rsp+458h] [rbp+358h] BYREF
  int v136; // [rsp+460h] [rbp+360h]
  _BYTE v137[8]; // [rsp+468h] [rbp+368h] BYREF
  int v138; // [rsp+470h] [rbp+370h]
  _BYTE v139[8]; // [rsp+478h] [rbp+378h] BYREF
  int v140; // [rsp+480h] [rbp+380h]
  _BYTE v141[8]; // [rsp+488h] [rbp+388h] BYREF
  int v142; // [rsp+490h] [rbp+390h]
  _BYTE v143[8]; // [rsp+498h] [rbp+398h] BYREF
  int v144; // [rsp+4A0h] [rbp+3A0h]
  _BYTE v145[8]; // [rsp+4A8h] [rbp+3A8h] BYREF
  int v146; // [rsp+4B0h] [rbp+3B0h]
  _BYTE v147[8]; // [rsp+4B8h] [rbp+3B8h] BYREF
  int v148; // [rsp+4C0h] [rbp+3C0h]
  _BYTE v149[8]; // [rsp+4C8h] [rbp+3C8h] BYREF
  int v150; // [rsp+4D0h] [rbp+3D0h]
  _BYTE v151[8]; // [rsp+4D8h] [rbp+3D8h] BYREF
  int v152; // [rsp+4E0h] [rbp+3E0h]
  _BYTE v153[8]; // [rsp+4E8h] [rbp+3E8h] BYREF
  int v154; // [rsp+4F0h] [rbp+3F0h]
  _BYTE v155[8]; // [rsp+4F8h] [rbp+3F8h] BYREF
  int v156; // [rsp+500h] [rbp+400h]
  _BYTE v157[8]; // [rsp+508h] [rbp+408h] BYREF
  int v158; // [rsp+510h] [rbp+410h]
  _BYTE v159[8]; // [rsp+518h] [rbp+418h] BYREF
  int v160; // [rsp+520h] [rbp+420h]
  _BYTE v161[8]; // [rsp+528h] [rbp+428h] BYREF
  int v162; // [rsp+530h] [rbp+430h]
  _BYTE v163[8]; // [rsp+538h] [rbp+438h] BYREF
  int v164; // [rsp+540h] [rbp+440h]
  _BYTE v165[8]; // [rsp+548h] [rbp+448h] BYREF
  int v166; // [rsp+550h] [rbp+450h]
  _BYTE v167[8]; // [rsp+558h] [rbp+458h] BYREF
  int v168; // [rsp+560h] [rbp+460h]
  _BYTE v169[8]; // [rsp+568h] [rbp+468h] BYREF
  int v170; // [rsp+570h] [rbp+470h]
  _BYTE v171[8]; // [rsp+578h] [rbp+478h] BYREF
  int v172; // [rsp+580h] [rbp+480h]
  _BYTE v173[8]; // [rsp+588h] [rbp+488h] BYREF
  char vars0; // [rsp+590h] [rbp+490h] BYREF

  v2 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v3,
    L"WM_NULL");
  v4 = 3;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v5,
    L"WM_MOVE");
  v6 = 5;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v7,
    L"WM_SIZE");
  v8 = 6;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v9,
    L"WM_ACTIVATE");
  v10 = 10;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v11,
    L"WM_ENABLE");
  v12 = 16;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v13,
    L"WM_CLOSE");
  v14 = 18;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v15,
    L"WM_QUIT");
  v16 = 70;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v17,
    L"WM_WINDOWPOSCHANGING");
  v18 = 71;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v19,
    L"WM_WINDOWPOSCHANGED");
  v20 = 78;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v21,
    L"WM_NOTIFY");
  v22 = 160;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v23,
    L"WM_NCMOUSEMOVE");
  v24 = 161;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v25,
    L"WM_NCLBUTTONDOWN");
  v26 = 162;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v27,
    L"WM_NCLBUTTONUP");
  v28 = 163;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v29,
    L"WM_NCLBUTTONDBLCLK");
  v30 = 164;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v31,
    L"WM_NCRBUTTONDOWN");
  v32 = 165;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v33,
    L"WM_NCRBUTTONUP");
  v34 = 166;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v35,
    L"WM_NCRBUTTONDBLCLK");
  v36 = 167;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v37,
    L"WM_NCMBUTTONDOWN");
  v38 = 168;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v39,
    L"WM_NCMBUTTONUP");
  v40 = 169;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v41,
    L"WM_NCMBUTTONDBLCLK");
  v42 = 171;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v43,
    L"WM_NCXBUTTONDOWN");
  v44 = 172;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v45,
    L"WM_NCXBUTTONUP");
  v46 = 173;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v47,
    L"WM_NCXBUTTONDBLCLK");
  v48 = 254;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v49,
    L"WM_INPUT_DEVICE_CHANGE");
  v50 = 255;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v51,
    L"WM_INPUT");
  v52 = 256;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v53,
    L"WM_KEYDOWN");
  v54 = 257;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v55,
    L"WM_KEYUP");
  v56 = 258;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v57,
    L"WM_CHAR");
  v58 = 260;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v59,
    L"WM_SYSKEYDOWN");
  v60 = 261;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v61,
    L"WM_SYSKEYUP");
  v62 = 269;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v63,
    L"WM_IME_STARTCOMPOSITION");
  v64 = 270;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v65,
    L"WM_IME_ENDCOMPOSITION");
  v66 = 273;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v67,
    L"WM_COMMAND");
  v68 = 274;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v69,
    L"WM_SYSCOMMAND");
  v70 = 275;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v71,
    L"WM_TIMER");
  v72 = 289;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v73,
    L"WM_ENTERIDLE");
  v74 = 512;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v75,
    L"WM_MOUSEMOVE");
  v76 = 513;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v77,
    L"WM_LBUTTONDOWN");
  v78 = 514;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v79,
    L"WM_LBUTTONUP");
  v80 = 515;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v81,
    L"WM_LBUTTONDBLCLK");
  v82 = 516;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v83,
    L"WM_RBUTTONDOWN");
  v84 = 517;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v85,
    L"WM_RBUTTONUP");
  v86 = 518;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v87,
    L"WM_RBUTTONDBLCLK");
  v88 = 519;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v89,
    L"WM_MBUTTONDOWN");
  v90 = 520;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v91,
    L"WM_MBUTTONUP");
  v92 = 521;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v93,
    L"WM_MBUTTONDBLCLK");
  v94 = 522;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v95,
    L"WM_MOUSEWHEEL");
  v96 = 526;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v97,
    L"WM_MOUSEHWHEEL");
  v98 = 528;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v99,
    L"WM_PARENTNOTIFY");
  v100 = 534;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v101,
    L"WM_MOVING");
  v102 = 537;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v103,
    L"WM_DEVICECHANGE");
  v104 = 568;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v105,
    L"WM_POINTERDEVICECHANGE");
  v106 = 569;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v107,
    L"WM_POINTERDEVICEINRANGE");
  v108 = 570;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v109,
    L"WM_POINTERDEVICEOUTOFRANGE");
  v110 = 577;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v111,
    L"WM_NCPOINTERUPDATE");
  v112 = 578;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v113,
    L"WM_NCPOINTERDOWN");
  v114 = 579;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v115,
    L"WM_NCPOINTERUP");
  v116 = 581;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v117,
    L"WM_POINTERUPDATE");
  v118 = 582;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v119,
    L"WM_POINTERDOWN");
  v120 = 583;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v121,
    L"WM_POINTERUP");
  v122 = 585;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v123,
    L"WM_POINTERENTER");
  v124 = 586;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v125,
    L"WM_POINTERLEAVE");
  v126 = 587;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v127,
    L"WM_POINTERACTIVATE");
  v128 = 588;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v129,
    L"WM_POINTERCAPTURECHANGED");
  v130 = 589;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v131,
    L"WM_TOUCHHITTESTING");
  v132 = 590;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v133,
    L"WM_POINTERWHEEL");
  v134 = 591;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v135,
    L"WM_POINTERHWHEEL");
  v136 = 641;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v137,
    L"WM_IME_SETCONTEXT");
  v138 = 642;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v139,
    L"WM_IME_NOTIFY");
  v140 = 643;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v141,
    L"WM_IME_CONTROL");
  v142 = 645;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v143,
    L"WM_IME_SELECT");
  v144 = 646;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v145,
    L"WM_IME_CHAR");
  v146 = 656;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v147,
    L"WM_IME_KEYDOWN");
  v148 = 657;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v149,
    L"WM_IME_KEYUP");
  v150 = 672;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v151,
    L"WM_NCMOUSEHOVER");
  v152 = 673;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v153,
    L"WM_MOUSEHOVER");
  v154 = 674;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v155,
    L"WM_NCMOUSELEAVE");
  v156 = 675;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v157,
    L"WM_MOUSELEAVE");
  v158 = 689;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v159,
    L"WM_WTSSESSION_CHANGE");
  v160 = 712;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v161,
    L"WM_TABLET_ADDED");
  v162 = 713;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v163,
    L"WM_TABLET_DELETED");
  v164 = 715;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v165,
    L"WM_TABLET_FLICK");
  v166 = 716;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v167,
    L"WM_TABLET_QUERYSYSTEMGESTURESTATUS");
  v168 = 718;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v169,
    L"WM_BRIGHTNESSCHANGED");
  v170 = 799;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v171,
    L"WM_DWMNCRENDERINGCHANGED");
  v172 = 800;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v173,
    L"WM_DWMCOLORIZATIONCOLORCHANGED");
  v1[0] = &v2;
  v1[1] = &vars0;
  std::unordered_map<unsigned long,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::unordered_map<unsigned long,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>(
    &g_msgIdToNameMap,
    v1);
  `eh vector destructor iterator'(&v2, 0x10u, 0x56u, (void (*)(void *))IsolationConfigInfo::~IsolationConfigInfo);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__g_msgIdToNameMap__);
}

```

## disassembly

```asm
0x140025fb0  push    rbp
0x140025fb2  lea     rbp, [rsp-490h]
0x140025fba  sub     rsp, 590h
0x140025fc1  and     [rsp+590h+var_560], 0
0x140025fc6  lea     rdx, aWmNull; "WM_NULL"
0x140025fcd  lea     rcx, [rsp+590h+var_558]
0x140025fd2  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140025fd7  mov     [rsp+590h+var_550], 3
0x140025fdf  lea     rdx, aWmMove; "WM_MOVE"
0x140025fe6  lea     rcx, [rsp+590h+var_548]
0x140025feb  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140025ff0  mov     [rsp+590h+var_540], 5
0x140025ff8  lea     rdx, aWmSize; "WM_SIZE"
0x140025fff  lea     rcx, [rsp+590h+var_538]
0x140026004  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140026009  mov     [rsp+590h+var_530], 6
0x140026011  lea     rdx, aWmActivate; "WM_ACTIVATE"
0x140026018  lea     rcx, [rsp+590h+var_528]
0x14002601d  nop     dword ptr [rax]
0x140026020  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140026025  mov     [rsp+590h+var_520], 0Ah
0x14002602d  lea     rdx, aWmEnable; "WM_ENABLE"
0x140026034  lea     rcx, [rsp+590h+var_518]
0x140026039  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14002603e  mov     [rbp+490h+var_510], 10h
0x140026045  lea     rdx, aWmClose; "WM_CLOSE"
0x14002604c  lea     rcx, [rbp+490h+var_508]
0x140026050  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140026055  mov     [rbp+490h+var_500], 12h
0x14002605c  lea     rdx, aWmQuit; "WM_QUIT"
0x140026063  lea     rcx, [rbp+490h+var_4F8]
0x140026067  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14002606c  mov     [rbp+490h+var_4F0], 46h ; 'F'
0x140026073  lea     rdx, aWmWindowposcha_0; "WM_WINDOWPOSCHANGING"
0x14002607a  lea     rcx, [rbp+490h+var_4E8]
0x14002607e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140026083  mov     [rbp+490h+var_4E0], 47h ; 'G'
0x14002608a  lea     rdx, aWmWindowposcha; "WM_WINDOWPOSCHANGED"
0x140026091  lea     rcx, [rbp+490h+var_4D8]
0x140026095  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14002609a  mov     [rbp+490h+var_4D0], 4Eh ; 'N'
0x1400260a1  lea     rdx, aWmNotify; "WM_NOTIFY"
0x1400260a8  lea     rcx, [rbp+490h+var_4C8]
0x1400260ac  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1400260b1  mov     [rbp+490h+var_4C0], 0A0h
0x1400260b8  lea     rdx, aWmNcmousemove; "WM_NCMOUSEMOVE"
0x1400260bf  lea     rcx, [rbp+490h+var_4B8]
0x1400260c3  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1400260c8  mov     [rbp+490h+var_4B0], 0A1h
0x1400260cf  lea     rdx, aWmNclbuttondow; "WM_NCLBUTTONDOWN"
0x1400260d6  lea     rcx, [rbp+490h+var_4A8]
0x1400260da  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1400260df  mov     [rbp+490h+var_4A0], 0A2h
0x1400260e6  lea     rdx, aWmNclbuttonup; "WM_NCLBUTTONUP"
0x1400260ed  lea     rcx, [rbp+490h+var_498]
0x1400260f1  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1400260f6  mov     [rbp+490h+var_490], 0A3h
0x1400260fd  lea     rdx, aWmNclbuttondbl; "WM_NCLBUTTONDBLCLK"
0x140026104  lea     rcx, [rbp+490h+var_488]
0x140026108  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14002610d  mov     [rbp+490h+var_480], 0A4h
0x140026114  lea     rdx, aWmNcrbuttondow; "WM_NCRBUTTONDOWN"
0x14002611b  lea     rcx, [rbp+490h+var_478]
0x14002611f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140026124  mov     [rbp+490h+var_470], 0A5h
0x14002612b  lea     rdx, aWmNcrbuttonup; "WM_NCRBUTTONUP"
0x140026132  lea     rcx, [rbp+490h+var_468]
0x140026136  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14002613b  mov     [rbp+490h+var_460], 0A6h
0x140026142  lea     rdx, aWmNcrbuttondbl; "WM_NCRBUTTONDBLCLK"
0x140026149  lea     rcx, [rbp+490h+var_458]
0x14002614d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140026152  mov     [rbp+490h+var_450], 0A7h
0x140026159  lea     rdx, aWmNcmbuttondow; "WM_NCMBUTTONDOWN"
0x140026160  lea     rcx, [rbp+490h+var_448]
0x140026164  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140026169  mov     [rbp+490h+var_440], 0A8h
0x140026170  lea     rdx, aWmNcmbuttonup; "WM_NCMBUTTONUP"
0x140026177  lea     rcx, [rbp+490h+var_438]
0x14002617b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140026180  mov     [rbp+490h+var_430], 0A9h
0x140026187  lea     rdx, aWmNcmbuttondbl; "WM_NCMBUTTONDBLCLK"
0x14002618e  lea     rcx, [rbp+490h+var_428]
0x140026192  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140026197  mov     [rbp+490h+var_420], 0ABh
0x14002619e  lea     rdx, aWmNcxbuttondow; "WM_NCXBUTTONDOWN"
0x1400261a5  lea     rcx, [rbp+490h+var_418]
0x1400261a9  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1400261ae  mov     [rbp+490h+var_410], 0ACh
0x1400261b8  lea     rdx, aWmNcxbuttonup; "WM_NCXBUTTONUP"
0x1400261bf  lea     rcx, [rbp+490h+var_408]
0x1400261c6  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1400261cb  mov     [rbp+490h+var_400], 0ADh
0x1400261d5  lea     rdx, aWmNcxbuttondbl; "WM_NCXBUTTONDBLCLK"
0x1400261dc  lea     rcx, [rbp+490h+var_3F8]
0x1400261e3  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1400261e8  mov     [rbp+490h+var_3F0], 0FEh
0x1400261f2  lea     rdx, aWmInputDeviceC; "WM_INPUT_DEVICE_CHANGE"
0x1400261f9  lea     rcx, [rbp+490h+var_3E8]
0x140026200  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140026205  mov     [rbp+490h+var_3E0], 0FFh
0x14002620f  lea     rdx, aWmInput; "WM_INPUT"
0x140026216  lea     rcx, [rbp+490h+var_3D8]
0x14002621d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140026222  mov     [rbp+490h+var_3D0], 100h
0x14002622c  lea     rdx, aWmKeydown; "WM_KEYDOWN"
0x140026233  lea     rcx, [rbp+490h+var_3C8]
0x14002623a  nop     word ptr [rax+rax+00h]
0x140026240  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140026245  mov     [rbp+490h+var_3C0], 101h
0x14002624f  lea     rdx, aWmKeyup; "WM_KEYUP"
0x140026256  lea     rcx, [rbp+490h+var_3B8]
0x14002625d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140026262  mov     [rbp+490h+var_3B0], 102h
0x14002626c  lea     rdx, aWmChar; "WM_CHAR"
0x140026273  lea     rcx, [rbp+490h+var_3A8]
0x14002627a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14002627f  mov     [rbp+490h+var_3A0], 104h
0x140026289  lea     rdx, aWmSyskeydown; "WM_SYSKEYDOWN"
0x140026290  lea     rcx, [rbp+490h+var_398]
0x140026297  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14002629c  mov     [rbp+490h+var_390], 105h
0x1400262a6  lea     rdx, aWmSyskeyup; "WM_SYSKEYUP"
0x1400262ad  lea     rcx, [rbp+490h+var_388]
0x1400262b4  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1400262b9  mov     [rbp+490h+var_380], 10Dh
0x1400262c3  lea     rdx, aWmImeStartcomp; "WM_IME_STARTCOMPOSITION"
0x1400262ca  lea     rcx, [rbp+490h+var_378]
0x1400262d1  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1400262d6  mov     [rbp+490h+var_370], 10Eh
0x1400262e0  lea     rdx, aWmImeEndcompos; "WM_IME_ENDCOMPOSITION"
0x1400262e7  lea     rcx, [rbp+490h+var_368]
0x1400262ee  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1400262f3  mov     [rbp+490h+var_360], 111h
0x1400262fd  lea     rdx, aWmCommand; "WM_COMMAND"
0x140026304  lea     rcx, [rbp+490h+var_358]
0x14002630b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140026310  mov     [rbp+490h+var_350], 112h
0x14002631a  lea     rdx, aWmSyscommand; "WM_SYSCOMMAND"
0x140026321  lea     rcx, [rbp+490h+var_348]
0x140026328  nop     dword ptr [rax+rax+00000000h]
0x140026330  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140026335  mov     [rbp+490h+var_340], 113h
0x14002633f  lea     rdx, aWmTimer; "WM_TIMER"
0x140026346  lea     rcx, [rbp+490h+var_338]
0x14002634d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140026352  mov     [rbp+490h+var_330], 121h
0x14002635c  lea     rdx, aWmEnteridle; "WM_ENTERIDLE"
0x140026363  lea     rcx, [rbp+490h+var_328]
0x14002636a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14002636f  mov     [rbp+490h+var_320], 200h
0x140026379  lea     rdx, aWmMousemove; "WM_MOUSEMOVE"
0x140026380  lea     rcx, [rbp+490h+var_318]
0x140026387  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14002638c  mov     [rbp+490h+var_310], 201h
0x140026396  lea     rdx, aWmLbuttondown; "WM_LBUTTONDOWN"
0x14002639d  lea     rcx, [rbp+490h+var_308]
0x1400263a4  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1400263a9  mov     [rbp+490h+var_300], 202h
0x1400263b3  lea     rdx, aWmLbuttonup; "WM_LBUTTONUP"
0x1400263ba  lea     rcx, [rbp+490h+var_2F8]
0x1400263c1  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1400263c6  mov     [rbp+490h+var_2F0], 203h
0x1400263d0  lea     rdx, aWmLbuttondblcl; "WM_LBUTTONDBLCLK"
0x1400263d7  lea     rcx, [rbp+490h+var_2E8]
0x1400263de  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1400263e3  mov     [rbp+490h+var_2E0], 204h
0x1400263ed  lea     rdx, aWmRbuttondown; "WM_RBUTTONDOWN"
0x1400263f4  lea     rcx, [rbp+490h+var_2D8]
0x1400263fb  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140026400  mov     [rbp+490h+var_2D0], 205h
0x14002640a  lea     rdx, aWmRbuttonup; "WM_RBUTTONUP"
0x140026411  lea     rcx, [rbp+490h+var_2C8]
0x140026418  nop     dword ptr [rax+rax+00000000h]
0x140026420  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140026425  mov     [rbp+490h+var_2C0], 206h
0x14002642f  lea     rdx, aWmRbuttondblcl; "WM_RBUTTONDBLCLK"
0x140026436  lea     rcx, [rbp+490h+var_2B8]
0x14002643d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140026442  mov     [rbp+490h+var_2B0], 207h
0x14002644c  lea     rdx, aWmMbuttondown; "WM_MBUTTONDOWN"
0x140026453  lea     rcx, [rbp+490h+var_2A8]
0x14002645a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14002645f  mov     [rbp+490h+var_2A0], 208h
0x140026469  lea     rdx, aWmMbuttonup; "WM_MBUTTONUP"
0x140026470  lea     rcx, [rbp+490h+var_298]
0x140026477  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14002647c  mov     [rbp+490h+var_290], 209h
0x140026486  lea     rdx, aWmMbuttondblcl; "WM_MBUTTONDBLCLK"
0x14002648d  lea     rcx, [rbp+490h+var_288]
0x140026494  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140026499  mov     [rbp+490h+var_280], 20Ah
0x1400264a3  lea     rdx, aWmMousewheel; "WM_MOUSEWHEEL"
0x1400264aa  lea     rcx, [rbp+490h+var_278]
0x1400264b1  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1400264b6  mov     [rbp+490h+var_270], 20Eh
0x1400264c0  lea     rdx, aWmMousehwheel; "WM_MOUSEHWHEEL"
0x1400264c7  lea     rcx, [rbp+490h+var_268]
0x1400264ce  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1400264d3  mov     [rbp+490h+var_260], 210h
0x1400264dd  lea     rdx, aWmParentnotify; "WM_PARENTNOTIFY"
0x1400264e4  lea     rcx, [rbp+490h+var_258]
0x1400264eb  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1400264f0  mov     [rbp+490h+var_250], 216h
0x1400264fa  lea     rdx, aWmMoving; "WM_MOVING"
0x140026501  lea     rcx, [rbp+490h+var_248]
0x140026508  nop     dword ptr [rax+rax+00000000h]
0x140026510  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140026515  mov     [rbp+490h+var_240], 219h
0x14002651f  lea     rdx, aWmDevicechange; "WM_DEVICECHANGE"
0x140026526  lea     rcx, [rbp+490h+var_238]
0x14002652d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140026532  mov     [rbp+490h+var_230], 238h
0x14002653c  lea     rdx, aWmPointerdevic_0; "WM_POINTERDEVICECHANGE"
0x140026543  lea     rcx, [rbp+490h+var_228]
0x14002654a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14002654f  mov     [rbp+490h+var_220], 239h
0x140026559  lea     rdx, aWmPointerdevic; "WM_POINTERDEVICEINRANGE"
0x140026560  lea     rcx, [rbp+490h+var_218]
0x140026567  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14002656c  mov     [rbp+490h+var_210], 23Ah
0x140026576  lea     rdx, aWmPointerdevic_1; "WM_POINTERDEVICEOUTOFRANGE"
0x14002657d  lea     rcx, [rbp+490h+var_208]
0x140026584  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140026589  mov     [rbp+490h+var_200], 241h
0x140026593  lea     rdx, aWmNcpointerupd; "WM_NCPOINTERUPDATE"
0x14002659a  lea     rcx, [rbp+490h+var_1F8]
0x1400265a1  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1400265a6  mov     [rbp+490h+var_1F0], 242h
0x1400265b0  lea     rdx, aWmNcpointerdow; "WM_NCPOINTERDOWN"
0x1400265b7  lea     rcx, [rbp+490h+var_1E8]
0x1400265be  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1400265c3  mov     [rbp+490h+var_1E0], 243h
0x1400265cd  lea     rdx, aWmNcpointerup; "WM_NCPOINTERUP"
0x1400265d4  lea     rcx, [rbp+490h+var_1D8]
0x1400265db  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1400265e0  mov     [rbp+490h+var_1D0], 245h
0x1400265ea  lea     rdx, aWmPointerupdat; "WM_POINTERUPDATE"
0x1400265f1  lea     rcx, [rbp+490h+var_1C8]
0x1400265f8  nop     dword ptr [rax+rax+00000000h]
0x140026600  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140026605  mov     [rbp+490h+var_1C0], 246h
0x14002660f  lea     rdx, aWmPointerdown; "WM_POINTERDOWN"
0x140026616  lea     rcx, [rbp+490h+var_1B8]
0x14002661d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140026622  mov     [rbp+490h+var_1B0], 247h
0x14002662c  lea     rdx, aWmPointerup; "WM_POINTERUP"
0x140026633  lea     rcx, [rbp+490h+var_1A8]
0x14002663a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14002663f  mov     [rbp+490h+var_1A0], 249h
0x140026649  lea     rdx, aWmPointerenter; "WM_POINTERENTER"
0x140026650  lea     rcx, [rbp+490h+var_198]
0x140026657  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14002665c  mov     [rbp+490h+var_190], 24Ah
0x140026666  lea     rdx, aWmPointerleave; "WM_POINTERLEAVE"
0x14002666d  lea     rcx, [rbp+490h+var_188]
0x140026674  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140026679  mov     [rbp+490h+var_180], 24Bh
0x140026683  lea     rdx, aWmPointeractiv; "WM_POINTERACTIVATE"
0x14002668a  lea     rcx, [rbp+490h+var_178]
0x140026691  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140026696  mov     [rbp+490h+var_170], 24Ch
0x1400266a0  lea     rdx, aWmPointercaptu; "WM_POINTERCAPTURECHANGED"
0x1400266a7  lea     rcx, [rbp+490h+var_168]
0x1400266ae  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1400266b3  mov     [rbp+490h+var_160], 24Dh
0x1400266bd  lea     rdx, aWmTouchhittest; "WM_TOUCHHITTESTING"
0x1400266c4  lea     rcx, [rbp+490h+var_158]
0x1400266cb  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1400266d0  mov     [rbp+490h+var_150], 24Eh
0x1400266da  lea     rdx, aWmPointerwheel; "WM_POINTERWHEEL"
0x1400266e1  lea     rcx, [rbp+490h+var_148]
0x1400266e8  nop     dword ptr [rax+rax+00000000h]
0x1400266f0  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1400266f5  mov     [rbp+490h+var_140], 24Fh
0x1400266ff  lea     rdx, aWmPointerhwhee; "WM_POINTERHWHEEL"
0x140026706  lea     rcx, [rbp+490h+var_138]
0x14002670d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140026712  mov     [rbp+490h+var_130], 281h
0x14002671c  lea     rdx, aWmImeSetcontex; "WM_IME_SETCONTEXT"
0x140026723  lea     rcx, [rbp+490h+var_128]
0x14002672a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14002672f  mov     [rbp+490h+var_120], 282h
0x140026739  lea     rdx, aWmImeNotify; "WM_IME_NOTIFY"
0x140026740  lea     rcx, [rbp+490h+var_118]
0x140026747  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14002674c  mov     [rbp+490h+var_110], 283h
0x140026756  lea     rdx, aWmImeControl; "WM_IME_CONTROL"
0x14002675d  lea     rcx, [rbp+490h+var_108]
0x140026764  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140026769  mov     [rbp+490h+var_100], 285h
0x140026773  lea     rdx, aWmImeSelect; "WM_IME_SELECT"
0x14002677a  lea     rcx, [rbp+490h+var_F8]
0x140026781  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140026786  mov     [rbp+490h+var_F0], 286h
0x140026790  lea     rdx, aWmImeChar; "WM_IME_CHAR"
0x140026797  lea     rcx, [rbp+490h+var_E8]
0x14002679e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1400267a3  mov     [rbp+490h+var_E0], 290h
0x1400267ad  lea     rdx, aWmImeKeydown; "WM_IME_KEYDOWN"
  ... truncated ...
```
