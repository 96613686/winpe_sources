# CDXGISwapChain::PresentImplCore(SPresentArgsCore<CDXGISwapChainWrapper> const *,uint,tagRECT const *,uint,DXGI_SCROLL_RECT const *,IDXGIResource *,CDXGISwapChain::PresentResultActions &)

- ea: `0x180008d40`
- end: `0x18000c198`
- name: `?PresentImplCore@CDXGISwapChain@@QEAAJPEBU?$SPresentArgsCore@UCDXGISwapChainWrapper@@@@IPEBUtagRECT@@IPEBUDXGI_SCROLL_RECT@@PEAUIDXGIResource@@AEAUPresentResultActions@1@@Z`
- size: `13400`
- prototype: `__int64 __usercall@<rax>(CDXGISwapChain *this@<rcx>, int, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `66`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180007b54`
- `0x180007f40`

## callees

- `0x1800088ac`
- `0x1800088f0`
- `0x180008d40`
- `0x18000c6b0`
- `0x18000cb1c`
- `0x18000cb70`
- `0x18000ce70`
- `0x18000d1f0`
- `0x180010d80`
- `0x1800111c8`
- `0x180011afc`
- `0x180012260`
- `0x180012b30`
- `0x180012bd0`
- `0x180012c70`
- `0x180012ef4`
- `0x1800137c0`
- `0x1800137f0`
- `0x180013cf4`
- `0x180013fcc`
- `0x180014040`
- `0x1800141ec`
- `0x180014590`
- `0x180014730`
- `0x180014750`
- `0x1800147b4`
- `0x180014df0`
- `0x180015578`
- `0x180022594`
- `0x18002282c`
- `0x1800228a8`
- `0x180022b70`
- `0x180022e38`
- `0x1800262c4`
- `0x180033bd0`
- `0x180037850`
- `0x180037e50`
- `0x1800385a4`
- `0x180038870`
- `0x180038cc0`
- `0x180038cf0`
- `0x180038d18`
- `0x180038da4`
- `0x180043208`
- `0x180043374`
- `0x18004bc5c`
- `0x18004cc40`
- `0x18005b284`
- `0x18005c890`
- `0x180060074`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000a850`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000a850`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800093d9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000a46e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800093d9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000a46e`
- `ext-ms-win-dwmapidxgi-ext-l1-1-0!DwmpDxgiIsThreadDesktopComposited` at `0x18000b8ff`
- `ext-ms-win-dwmapidxgi-ext-l1-1-0!DwmpDxgiIsThreadDesktopComposited` at `0x18000b8ff`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!UnionRect` at `0x18000b71a`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!UnionRect` at `0x18000b71a`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IsRectEmpty` at `0x18000ae29`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IsRectEmpty` at `0x18000ae29`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowInfo` at `0x18000961e`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowInfo` at `0x18000961e`
- `ext-ms-win-ntuser-window-l1-1-1!GetAncestor` at `0x18000b1ca`
- `ext-ms-win-ntuser-window-l1-1-1!GetAncestor` at `0x18000b1ca`
- `ext-ms-win-ntuser-window-l1-1-1!GetWindowDisplayAffinity` at `0x18000b1ea`
- `ext-ms-win-ntuser-window-l1-1-1!GetWindowDisplayAffinity` at `0x18000b380`
- `ext-ms-win-ntuser-window-l1-1-1!GetWindowDisplayAffinity` at `0x18000b3a5`
- `ext-ms-win-ntuser-window-l1-1-1!GetWindowDisplayAffinity` at `0x18000bf3b`
- `ext-ms-win-ntuser-window-l1-1-1!GetWindowDisplayAffinity` at `0x18000b1ea`
- `ext-ms-win-ntuser-window-l1-1-1!GetWindowDisplayAffinity` at `0x18000b380`
- `ext-ms-win-ntuser-window-l1-1-1!GetWindowDisplayAffinity` at `0x18000b3a5`
- `ext-ms-win-ntuser-window-l1-1-1!GetWindowDisplayAffinity` at `0x18000bf3b`
- `ext-ms-win-ntuser-window-l1-1-1!SetWindowDisplayAffinity` at `0x18000b202`
- `ext-ms-win-ntuser-window-l1-1-1!SetWindowDisplayAffinity` at `0x18000b38f`
- `ext-ms-win-ntuser-window-l1-1-1!SetWindowDisplayAffinity` at `0x18000b202`
- `ext-ms-win-ntuser-window-l1-1-1!SetWindowDisplayAffinity` at `0x18000b38f`
- `api-ms-win-dx-d3dkmt-l1-1-1!D3DKMTSetVidPnSourceHwProtection` at `0x18000c096`
- `api-ms-win-dx-d3dkmt-l1-1-1!D3DKMTSetVidPnSourceHwProtection` at `0x18000c096`

## string_xrefs

- `0x18000a7e1`: `Hybrid present: iGPU removed, removing dGPU`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall CDXGISwapChain::PresentImplCore(
        CDXGIBaseAdapter **this,
        _DWORD *a2,
        unsigned int a3,
        RECT *a4,
        int a5,
        __int64 a6,
        __int64 a7,
        _BYTE *a8)
{
  _DWORD *v8; // rsi
  CDXGIBaseAdapter **v9; // r13
  unsigned int v10; // ebx
  __int64 result; // rax
  CModule *v12; // rcx
  bool v13; // r9
  bool v14; // sf
  int v15; // r14d
  unsigned int v16; // ebx
  CDXGIBaseAdapter *v17; // rcx
  void (__fastcall ***v18)(_QWORD); // rdx
  signed int v19; // eax
  unsigned __int64 v20; // rcx
  LONG top; // r9d
  unsigned int v22; // r12d
  _QWORD *v23; // rdi
  HWND v24; // rcx
  HWND v25; // rcx
  unsigned __int64 v26; // r15
  _BYTE *v27; // r15
  int v28; // ecx
  int v29; // ecx
  HWND *v30; // rdi
  HWND v31; // rcx
  char v32; // r12
  int v33; // r8d
  int v34; // r9d
  int v35; // r10d
  int v36; // r11d
  int v37; // edi
  unsigned __int64 v38; // rcx
  const char *Name; // rax
  LONG *v40; // r8
  unsigned int v41; // ecx
  unsigned int v42; // eax
  int v43; // edi
  char v44; // r15
  int v45; // ecx
  int v46; // ecx
  __int64 v47; // rcx
  char v48; // r14
  CDXGISwapChain *v49; // rcx
  __int64 *v50; // rdx
  CModule *v51; // rcx
  struct DXGI_SCROLL_RECT *v52; // rcx
  unsigned int v53; // edi
  unsigned int v54; // eax
  CModule *v55; // rcx
  bool v56; // si
  CDXGIBaseAdapter *v57; // rdi
  int v58; // eax
  int SwapchainBufferForProtection; // edi
  bool v60; // sf
  int v61; // ecx
  int v62; // ecx
  const struct _LUID *v63; // r8
  CDXGIBaseAdapter *v64; // rdx
  __int64 v65; // rax
  const struct SAdapterDesc *v66; // rcx
  int v67; // edx
  int v68; // edx
  unsigned int v69; // eax
  CModule *v70; // rcx
  CDXGIBaseAdapter *v71; // rax
  CModule *v72; // rcx
  bool v73; // r9
  bool v74; // sf
  CModule *v75; // rcx
  bool v76; // si
  CDXGIOutput *v77; // rdi
  CDXGIBaseAdapter *v78; // rax
  int v79; // edx
  int v80; // eax
  int v81; // ecx
  unsigned int v82; // r8d
  int v83; // eax
  bool v84; // di
  unsigned int v85; // r8d
  int v86; // ecx
  unsigned int v87; // eax
  int v88; // eax
  int v89; // eax
  struct IDXGIResource *v90; // r15
  CDXGIBaseAdapter *v91; // r12
  CDXGIBaseAdapter *v92; // r14
  CDXGIBaseAdapter *v93; // rsi
  const struct DXGI_SCROLL_RECT *v94; // rdx
  struct IDXGIResource *CurrentProxySurface; // rdi
  const struct DXGI_SCROLL_RECT *v96; // rax
  const struct DXGI_SCROLL_RECT *v97; // rcx
  unsigned int v98; // eax
  CModule *v99; // rcx
  unsigned int v100; // eax
  unsigned int v101; // eax
  CModule *v102; // rcx
  int v103; // ecx
  int v104; // ecx
  unsigned int v105; // r8d
  int v106; // edi
  int v107; // eax
  int v108; // edx
  const struct _LUID *v109; // r8
  CDXGIBaseAdapter *v110; // rdx
  __int64 v111; // rax
  const struct SAdapterDesc *v112; // rcx
  int v113; // eax
  _BYTE *v114; // r15
  unsigned int v115; // eax
  CModule *v116; // rcx
  CDXGIBaseAdapter *v117; // rax
  CDXGIBaseAdapter *v118; // rax
  const struct DXGI_SCROLL_RECT *v119; // rcx
  unsigned int v120; // edi
  unsigned int v121; // eax
  CModule *v122; // rcx
  CModule *v123; // rcx
  CDXGIBaseAdapter *v124; // rax
  int v125; // ecx
  unsigned int v126; // eax
  int v127; // edi
  HWND v128; // rcx
  bool v129; // di
  unsigned int v130; // edi
  CDXGIOutput *v131; // rcx
  CDXGIBaseAdapter *v132; // r8
  CDXGIBaseAdapter *v133; // rax
  CDXGIBaseAdapter *v134; // rdi
  CDXGIBaseAdapter *v135; // rcx
  __int64 v136; // rcx
  struct IDXGIResource *v137; // r13
  __int64 (__fastcall ***v138)(_QWORD, GUID *, CDXGIBaseAdapter **); // r9
  signed int v139; // r13d
  CModule *v140; // rcx
  struct IDXGIResource *v141; // r13
  bool v142; // di
  unsigned int v143; // eax
  int v144; // eax
  unsigned int v145; // eax
  unsigned int v146; // eax
  CModule *v147; // rcx
  int v148; // edi
  const struct _LUID *v149; // r8
  CDXGIBaseAdapter *v150; // rdx
  __int64 v151; // rax
  const struct SAdapterDesc *v152; // rcx
  CDXGIBaseAdapter *v153; // rax
  __int64 v154; // rdx
  int v155; // ecx
  unsigned int v156; // eax
  int v157; // edi
  unsigned int v158; // eax
  CModule *v159; // rcx
  bool v160; // r9
  BOOL IsMaximizedWindowedFullscreenEnabled; // r15d
  CDXGIFactory *v162; // rdi
  HANDLE CurrentProcess; // rax
  signed int v164; // eax
  CDXGIBaseAdapter *v165; // rax
  __int64 v166; // rdx
  int v167; // ecx
  unsigned int v168; // eax
  int v169; // eax
  const struct _LUID *v170; // r8
  const struct _LUID *v171; // r8
  CDXGIBaseAdapter *v172; // rdx
  __int64 v173; // rax
  const struct SAdapterDesc *v174; // rcx
  unsigned int v175; // r15d
  LONG right; // r12d
  float v177; // xmm6_4
  LONG bottom; // r10d
  float v179; // xmm7_4
  LONG left; // r13d
  __int64 v181; // r8
  LONG v182; // ecx
  LONG *p_right; // rdx
  LONG v184; // eax
  bool v185; // cc
  LONG v186; // eax
  LONG v187; // edx
  LONG *p_bottom; // r11
  LONG v189; // eax
  LONG *v190; // rdi
  LONG v191; // ecx
  __int64 v192; // rdx
  LONG *v193; // r8
  LONG v194; // eax
  LONG v195; // eax
  LONG *v196; // rdi
  float v197; // xmm0_4
  LONG v198; // ecx
  LONG v199; // eax
  LONG v200; // eax
  unsigned int v201; // eax
  CDXGIBaseAdapter *v202; // rdx
  __int64 v203; // rax
  const struct SAdapterDesc *v204; // rcx
  RECT *v205; // rdi
  struct IDXGIResource *v206; // rdi
  unsigned int v207; // r10d
  int v208; // eax
  int v209; // ecx
  CDXGIBaseAdapter *v210; // rsi
  BOOL IsFullscreenDDAAllowed; // edi
  struct IUnknown *v212; // rax
  signed int v213; // eax
  signed int IndirectBuffer; // eax
  CModule *v215; // rcx
  bool v216; // r9
  const struct _LUID *AdapterDesc; // rax
  const struct ResizeBuffersTelemetryInfo *v218; // r9
  CDXGIOutput *v219; // rax
  struct IDXGIResource *v220; // rdi
  int v221; // ecx
  bool v222; // di
  unsigned int v223; // eax
  HWND Ancestor; // rax
  HWND v225; // rcx
  CModule *v226; // rcx
  bool v227; // r9
  CDXGIBaseAdapter *v228; // rax
  struct IDXGIResource *v229; // rax
  __int64 v230; // rdx
  int v231; // r8d
  __int64 v232; // r10
  __int64 (__fastcall *v233)(__int64, CDXGIBaseAdapter *, _QWORD, _QWORD, _DWORD, struct IDXGIResource *, _QWORD, __int64, _QWORD, _DWORD, int); // r11
  unsigned int v234; // eax
  CModule *v235; // rcx
  bool v236; // r9
  __int64 v237; // rdx
  __int64 v238; // rcx
  int v239; // ecx
  int v240; // eax
  CDXGIBaseAdapter *v241; // rdi
  CDXGIBaseAdapter *v242; // rcx
  unsigned int v243; // eax
  unsigned int v244; // edi
  LONG v245; // r8d
  unsigned int v246; // r9d
  unsigned int v247; // edx
  unsigned int v248; // ecx
  unsigned int v249; // eax
  unsigned int v250; // eax
  const struct DXGI_SCROLL_RECT *v251; // rcx
  RECT *v252; // rsi
  unsigned int v253; // edi
  unsigned int v254; // eax
  CModule *v255; // rcx
  __int64 *v256; // rax
  unsigned int v257; // eax
  CModule *v258; // rcx
  unsigned int j; // edi
  CModule *v260; // rcx
  bool v261; // r9
  char v262; // r14
  char v263; // al
  __int64 v264; // r9
  unsigned int v265; // edx
  int v266; // ecx
  int v267; // ecx
  CModule *v268; // rcx
  bool v269; // r9
  unsigned int v270; // eax
  __int64 i; // rdi
  unsigned int v272; // eax
  const struct _LUID *v273; // r8
  CDXGIBaseAdapter *v274; // rdx
  __int64 v275; // rax
  const struct SAdapterDesc *v276; // rcx
  CModule *v277; // rcx
  bool v278; // r9
  int v279; // eax
  CDXGIBaseAdapter *v280; // rdi
  CDXGIBaseAdapter *v281; // rcx
  unsigned int v282; // eax
  __int64 v283; // rcx
  unsigned __int64 v284; // rax
  __int64 v285; // rdx
  __int64 v286; // rcx
  int v287; // edx
  int v288; // ecx
  int v289; // eax
  unsigned int v290; // r9d
  struct IDXGIResource *v291; // rdx
  CDXGIBaseAdapter *v292; // rcx
  CDXGIOutput *v293; // rcx
  __int64 v294; // rcx
  struct CDXGIOutput *v295; // r8
  struct tagRECT *v296; // [rsp+30h] [rbp-D8h]
  enum DXGI_FORMAT v297[2]; // [rsp+38h] [rbp-D0h]
  bool v298[8]; // [rsp+78h] [rbp-90h] BYREF
  struct IDXGIResource *v299; // [rsp+80h] [rbp-88h] BYREF
  signed int v300; // [rsp+88h] [rbp-80h]
  unsigned int v301; // [rsp+8Ch] [rbp-7Ch]
  DWORD pdwAffinity; // [rsp+90h] [rbp-78h] BYREF
  char v303; // [rsp+94h] [rbp-74h]
  bool v304; // [rsp+95h] [rbp-73h]
  unsigned int v305; // [rsp+98h] [rbp-70h]
  _DWORD v306[3]; // [rsp+9Ch] [rbp-6Ch] BYREF
  unsigned int v307; // [rsp+A8h] [rbp-60h]
  _BYTE *v308; // [rsp+B0h] [rbp-58h]
  unsigned int v309; // [rsp+B8h] [rbp-50h]
  CDXGIBaseAdapter *v310; // [rsp+C0h] [rbp-48h] BYREF
  RECT *lprc; // [rsp+C8h] [rbp-40h]
  __int64 v312; // [rsp+D0h] [rbp-38h]
  int v313; // [rsp+D8h] [rbp-30h]
  void *lpVtbl; // [rsp+E0h] [rbp-28h]
  __int64 v315; // [rsp+E8h] [rbp-20h] BYREF
  unsigned __int64 v316; // [rsp+F0h] [rbp-18h] BYREF
  CModule *v317; // [rsp+F8h] [rbp-10h] BYREF
  _DWORD v318[2]; // [rsp+100h] [rbp-8h] BYREF
  CDXGIBaseAdapter **v319; // [rsp+108h] [rbp+0h]
  __int64 v320; // [rsp+110h] [rbp+8h]
  unsigned __int64 v321; // [rsp+118h] [rbp+10h]
  CModule *v322; // [rsp+120h] [rbp+18h] BYREF
  CDXGIBaseAdapter **v323; // [rsp+128h] [rbp+20h] BYREF
  _QWORD *p_lpVtbl; // [rsp+130h] [rbp+28h] BYREF
  unsigned __int64 v325; // [rsp+138h] [rbp+30h]
  struct IDXGIResource *v326; // [rsp+140h] [rbp+38h]
  CDXGIBaseAdapter *v327; // [rsp+148h] [rbp+40h]
  CDXGIBaseAdapter *v328; // [rsp+150h] [rbp+48h] BYREF
  char v329; // [rsp+158h] [rbp+50h]
  struct IDXGIResource *v330; // [rsp+160h] [rbp+58h]
  char v331[8]; // [rsp+168h] [rbp+60h] BYREF
  void (__fastcall ***v332)(_QWORD); // [rsp+170h] [rbp+68h]
  __int128 v333; // [rsp+178h] [rbp+70h] BYREF
  __int128 v334; // [rsp+188h] [rbp+80h] BYREF
  __int128 v335; // [rsp+198h] [rbp+90h] BYREF
  __int128 v336; // [rsp+1A8h] [rbp+A0h]
  void (__fastcall ***v337)(_QWORD); // [rsp+1B8h] [rbp+B0h]
  char v338; // [rsp+1C0h] [rbp+B8h]
  _DWORD v339[2]; // [rsp+1C8h] [rbp+C0h] BYREF
  CDXGIBaseAdapter *v340; // [rsp+1D0h] [rbp+C8h]
  int v341; // [rsp+1D8h] [rbp+D0h]
  __int64 v342; // [rsp+1DCh] [rbp+D4h]
  _DWORD v343[5]; // [rsp+1E4h] [rbp+DCh] BYREF
  __int64 v344; // [rsp+1F8h] [rbp+F0h] BYREF
  int v345; // [rsp+200h] [rbp+F8h]
  int v346; // [rsp+204h] [rbp+FCh]
  int v347; // [rsp+208h] [rbp+100h]
  RECT *v348; // [rsp+210h] [rbp+108h]
  int v349; // [rsp+218h] [rbp+110h]
  int v350; // [rsp+21Ch] [rbp+114h]
  unsigned int v351; // [rsp+220h] [rbp+118h]
  int v352; // [rsp+330h] [rbp+228h]
  CDXGIBaseAdapter *v353; // [rsp+348h] [rbp+240h]
  unsigned __int64 v354; // [rsp+350h] [rbp+248h]
  _DWORD v355[260]; // [rsp+358h] [rbp+250h] BYREF
  __int128 *v356; // [rsp+768h] [rbp+660h]
  int v357; // [rsp+770h] [rbp+668h]
  int v358; // [rsp+774h] [rbp+66Ch]
  struct tagRECT v359; // [rsp+7A8h] [rbp+6A0h] BYREF
  CDXGIBaseAdapter *v360; // [rsp+7B8h] [rbp+6B0h] BYREF
  BOOL v361; // [rsp+7C0h] [rbp+6B8h]
  tagWINDOWINFO pwi; // [rsp+7C8h] [rbp+6C0h] BYREF
  _DWORD v363[2]; // [rsp+808h] [rbp+700h] BYREF
  __int128 v364; // [rsp+810h] [rbp+708h]
  __int128 v365; // [rsp+820h] [rbp+718h]
  __int128 v366; // [rsp+830h] [rbp+728h]
  char v367[4]; // [rsp+848h] [rbp+740h] BYREF
  struct tagRECT rcDst[16]; // [rsp+84Ch] [rbp+744h] BYREF

  lprc = a4;
  v307 = a3;
  v8 = a2;
  v321 = (unsigned __int64)a2;
  v9 = this;
  v319 = this;
  v312 = a6;
  v308 = a8;
  v320 = a7;
  v301 = 0;
  if ( *((_BYTE *)this + 666) && !*((_BYTE *)this + 667) )
  {
    AdapterDesc = (const struct _LUID *)CDXGIBaseAdapter::InternalGetAdapterDesc(this[40]);
    CDXGITelemetryHelper::LogResizeBuffers(
      (CDXGITelemetryHelper *)*((unsigned int *)v9 + 94),
      (const struct CDXGISwapChain *)v9,
      AdapterDesc + 37,
      v218,
      *((_DWORD *)v9 + 94),
      *((_DWORD *)v9 + 95),
      *((enum DXGI_FORMAT *)v9 + 98));
    *((_BYTE *)v9 + 666) = 0;
  }
  v309 = v8[2];
  v10 = v8[1];
  v305 = v10;
  *(_DWORD *)v298 = 0;
  (*(void (__fastcall **)(CDXGIBaseAdapter *, __int64 *))(*(_QWORD *)v9[33] + 104LL))(v9[33], &v315);
  LOBYTE(v306[0]) = 0;
  result = CDXGISwapChain::ValidatePresent((CDXGISwapChain *)v9, a5, a6, (__int64)&v315, a7, (__int64)v306);
  *(_DWORD *)v298 = result;
  v14 = (int)result < 0;
  if ( (_DWORD)result )
  {
    CModule::RecordJournalImpl(v12, result, "Non-zero return value", v13);
    result = *(unsigned int *)v298;
    v14 = *(int *)v298 < 0;
  }
  if ( !v14 )
  {
    v15 = v10 & 1;
    if ( (v10 & 1) != 0 )
      goto LABEL_6;
    v71 = v9[266];
    if ( !v71
      || !*((_DWORD *)v71 + 109)
      || *((_DWORD *)v71 + 108) != 3
      || CDXGISwapChain::IsMaximizedWindowedFullscreenEnabled((CDXGISwapChain *)v9) )
    {
      goto LABEL_6;
    }
    result = CDXGISwapChain::PrepareIndirectPresent((CDXGISwapChain *)v9, v8[3]);
    *(_DWORD *)v298 = result;
    v74 = (int)result < 0;
    if ( (_DWORD)result )
    {
      CModule::RecordJournalImpl(v72, result, "Non-zero return value", v73);
      result = *(unsigned int *)v298;
      v74 = *(int *)v298 < 0;
    }
    if ( !v74 )
    {
LABEL_6:
      v16 = 0;
      v304 = 0;
      if ( LOBYTE(v306[0]) )
      {
        v307 = 0;
        lprc = 0;
      }
      v17 = v9[29];
      v18 = (void (__fastcall ***)(_QWORD))((char *)v17 + 264);
      if ( !v17 )
        v18 = 0;
      v332 = v18;
      v337 = v18;
      (**v18)(v18);
      v338 = 1;
      *((_DWORD *)v9 + 395) = 1;
      v364 = 0;
      v365 = 0;
      v366 = 0;
      v363[0] = *((_DWORD *)v9 + 62);
      v363[1] = 3;
      v19 = (*((__int64 (__fastcall **)(_DWORD *))v9[40] + 38))(v363);
      if ( v19 >= 0 )
      {
        if ( (v364 & 1) != 0 )
        {
          *(_DWORD *)v298 = 142213125;
          CModule::RecordJournalImpl((CModule *)v20, 0x87A0005u, "Non-zero return value", top);
          v16 = 142213125;
          CModule::RecordJournalImpl(v226, 0x87A0005u, "Non-zero return value", v227);
          if ( v9[97] )
          {
            v228 = v9[266];
            if ( *((_QWORD *)v228 + 64) )
            {
              *((_BYTE *)v228 + 12880) = 1;
              CDXGIOutput::ReleaseOwnershipImpl(v9[266], *((_DWORD *)v9 + 82) == 0);
            }
          }
        }
      }
      else
      {
        CModule::RecordJournalImpl((CModule *)v20, v19, "OsThunkDDIGetDeviceState", top);
      }
      v22 = -2005270494;
      if ( !v15 )
        goto LABEL_13;
      v113 = *((_DWORD *)v9 + 82);
      if ( v113 )
      {
        if ( v113 == 1 )
        {
          *(_DWORD *)v298 = 0;
          goto LABEL_14;
        }
        goto LABEL_13;
      }
      if ( *(_DWORD *)v298 )
        goto LABEL_58;
      v153 = v9[266];
      v154 = *((_QWORD *)v153 + 21);
      if ( !*(_QWORD *)(v154 + 352) )
        goto LABEL_378;
      if ( *((_BYTE *)v153 + 264) || (v20 = *((unsigned int *)v153 + 64), (_DWORD)v20 == -1) )
      {
        v158 = -2005270494;
        goto LABEL_379;
      }
      LODWORD(v299) = 0;
      HIDWORD(v299) = v20;
      v155 = *((_DWORD *)v153 + 109);
      if ( !v155 )
        v155 = *(_DWORD *)(v154 + 220);
      LODWORD(v299) = v155;
      v156 = (*(__int64 (__fastcall **)(struct IDXGIResource **))(v154 + 352))(&v299);
      v157 = v156;
      if ( !v156 || v156 == -1073741811 || v156 == -1073741130 )
      {
        if ( v156 == -1073741130 )
        {
          v158 = -2005270523;
          goto LABEL_379;
        }
      }
      else
      {
        v20 = v156 + 1071775739;
        if ( (unsigned int)v20 > 1 )
        {
          if ( v156 != -2145517568 )
          {
            CModule::RecordJournalImpl((CModule *)v20, v156, "Contract breached!", top);
            goto LABEL_377;
          }
          goto LABEL_418;
        }
      }
      if ( v156 != -1071775738 )
      {
        if ( v156 == -1071775739 )
        {
          v158 = 142213127;
          goto LABEL_379;
        }
LABEL_377:
        v158 = NTStatusToHResult(v157);
        if ( v158 )
        {
LABEL_379:
          *(_DWORD *)v298 = v158;
          if ( !v158 )
            goto LABEL_14;
          CModule::RecordJournalImpl((CModule *)v20, v158, "Non-zero return value", top);
LABEL_13:
          if ( !*(_DWORD *)v298 )
          {
LABEL_14:
            v23 = v9 + 97;
            v24 = (HWND)v9[97];
            if ( v24 )
            {
              v114 = v308;
              v115 = CDXGIFactory::CheckOcclusion(v24, (HWND)v9[42], v308 + 2, v308 + 3);
              *(_DWORD *)v298 = v115;
              if ( v115 )
                CModule::RecordJournalImpl(v116, v115, "Non-zero return value", top);
              v117 = v9[266];
              if ( *((_BYTE *)v117 + 12880) )
              {
                if ( !v15 )
                {
                  *((_BYTE *)v117 + 12880) = 0;
                  *v114 = 1;
                  *(_DWORD *)v298 = 142213125;
                  CModule::RecordJournalImpl(v116, 0x87A0005u, "Non-zero return value", top);
                  if ( !CDXGISwapChain::IsWindowedInternal((CDXGISwapChain *)v9) )
                    goto LABEL_82;
                }
              }
            }
            else
            {
              v25 = (HWND)v9[42];
              if ( v25 )
              {
                v67 = *((_DWORD *)v9 + 107);
                if ( !v67 || (v68 = v67 - 1) == 0 || (unsigned int)(v68 - 2) >= 2 )
                {
                  v69 = CDXGIFactory::CheckOcclusion(v25, (HWND)v9[42], v308 + 2, v308 + 3);
                  *(_DWORD *)v298 = v69;
                  if ( v69 )
                    CModule::RecordJournalImpl(v70, v69, "Non-zero return value", top);
                }
              }
            }
            v20 = *((unsigned int *)v9 + 1140);
            if ( (_DWORD)v20 )
            {
              v20 = (unsigned int)(v20 - 1);
              if ( (_DWORD)v20 )
              {
                v20 = (unsigned int)(v20 - 2);
                if ( (unsigned int)v20 < 2 )
                {
                  v16 = *(_DWORD *)v298;
                  if ( *(_DWORD *)v298 )
                    CModule::RecordJournalImpl((CModule *)v20, *(unsigned int *)v298, "Non-zero return value", top);
                }
              }
            }
LABEL_19:
            if ( !*(_DWORD *)v298 )
            {
              if ( v15 )
              {
                v27 = v308;
LABEL_26:
                v20 = *((unsigned int *)v9 + 82);
                if ( (((_DWORD)v20 - 2) & 0xFFFFFFFD) == 0 )
                {
                  if ( *((_DWORD *)v9 + 111)
                    || (_DWORD)v20 == 2
                    && (*((_BYTE *)v9 + 665)
                     || *((char *)v9 + 288) < 0
                     || (!*((_BYTE *)v9 + 2530) ? (v149 = 0) : (v149 = (const struct _LUID *)(v9 + 317)),
                         (v150 = v9[40], v151 = *((unsigned int *)v150 + 187), (_DWORD)v151 == -1)
                       ? (v152 = (CDXGIBaseAdapter *)((char *)v150 + 752))
                       : (v152 = (const struct SAdapterDesc *)(*(_QWORD *)(*((_QWORD *)v150 + 21) + 280LL) + 536 * v151)),
                         MaximizedWindowedModeFullscreenEnabled(v152, v9[29], v149) || *((_BYTE *)v9 + 2114))) )
                  {
                    v28 = *((_DWORD *)v9 + 1140);
                    if ( !v28 || (v29 = v28 - 1) == 0 || (v20 = (unsigned int)(v29 - 2), (unsigned int)v20 >= 2) )
                    {
                      if ( (v315 & 1) != 0 || (*((_BYTE *)v9 + 436) & 0x20) != 0 )
                      {
                        pdwAffinity = 0;
                        v30 = (HWND *)(v9 + 113);
                        if ( !v9[113] )
                        {
                          Ancestor = GetAncestor((HWND)v9[42], 2u);
                          *v30 = Ancestor;
                          if ( Ancestor )
                          {
                            v225 = Ancestor;
                          }
                          else
                          {
                            v225 = (HWND)v9[42];
                            *v30 = v225;
                          }
                          GetWindowDisplayAffinity(v225, &pdwAffinity);
                          if ( (pdwAffinity & 1) == 0 )
                            SetWindowDisplayAffinity(*v30, pdwAffinity | 1);
                        }
                      }
                      else
                      {
                        pdwAffinity = 0;
                        v30 = (HWND *)(v9 + 113);
                        v31 = (HWND)v9[113];
                        if ( v31 )
                        {
                          GetWindowDisplayAffinity(v31, &pdwAffinity);
                          SetWindowDisplayAffinity(*v30, pdwAffinity & 0xFFFFFFFE);
                          *v30 = 0;
                        }
                      }
                      v20 = (unsigned __int64)*v30;
                      if ( *v30 )
                      {
                        pdwAffinity = 0;
                        GetWindowDisplayAffinity((HWND)v20, &pdwAffinity);
                        if ( (pdwAffinity & 1) == 0 )
                        {
                          DXGI_SDK_MSG_SWAPCHAIN(
                            v9[38],
                            DXGI_MSG_IDXGISwapChain_Present_ProtectedContentInWindowedModeWithDWMOffOrInvalidDisplayAffinity);
                          *(_DWORD *)v298 = -2005270486;
                          CModule::RecordJournalImpl(v235, 0x887A002A, "Non-zero return value", v236);
                        }
                      }
                    }
                  }
                }
LABEL_36:
                if ( v15 )
                {
                  if ( (*(int (__fastcall **)(CDXGIBaseAdapter *))(*(_QWORD *)v9[33] + 176LL))(v9[33]) < 0 )
                  {
                    *(_DWORD *)v298 = -2005270523;
                    CModule::RecordJournalImpl(v75, 0x887A0005, "Non-zero return value", top);
                  }
                  else
                  {
                    LODWORD(v50) = *(_DWORD *)v298;
                    if ( *(_DWORD *)v298 )
                      CModule::RecordJournalImpl(v75, *(unsigned int *)v298, "Non-zero return value", top);
                  }
                  goto LABEL_81;
                }
                if ( (*(_DWORD *)v298 == 142213121 || *(_DWORD *)v298 == 142213122) && !*((_DWORD *)v9 + 111) )
                {
                  if ( v9[42] )
                  {
                    v27[1] = 1;
                    if ( !CDXGISwapChain::IsWindowedInternal((CDXGISwapChain *)v9) )
                    {
LABEL_82:
                      if ( *(int *)v298 < 0 )
                        goto LABEL_102;
LABEL_83:
                      if ( ((_BYTE)v9[55] & 4) != 0 || (v305 & 3) != 0 )
                        goto LABEL_100;
                      if ( v9[565] && v9[266] )
                      {
                        if ( v16 )
                        {
                          if ( ((v16 - 142213121) & 0xFFFFFFFB) != 0 )
                            CModule::RecordJournalImpl((CModule *)v20, v16, "Contract breached!", top);
                        }
                        else if ( (unsigned int)(*(_DWORD *)v298 - 142213125) > 3 && *(_DWORD *)v298 != 142213121 )
                        {
                          goto LABEL_86;
                        }
                        IndirectBuffer = CDXGISwapChain::ReleaseLastIndirectBuffer(
                                           (CDXGISwapChain *)v9,
                                           (unsigned int)v50,
                                           v40);
                        if ( IndirectBuffer < 0 )
                        {
                          *(_DWORD *)v298 = IndirectBuffer;
                          CModule::RecordJournalImpl(v215, IndirectBuffer, "Non-zero return value", v216);
                        }
                      }
LABEL_86:
                      v56 = v304;
                      if ( v304 )
                        v57 = v9[237];
                      else
                        v57 = 0;
                      QueryPerformanceCounter((LARGE_INTEGER *)v9 + 201);
                      v20 = v321;
                      if ( (*(_BYTE *)(v321 + 4) & 0x20) != 0 )
                        v58 = 1;
                      else
                        v58 = (*((_BYTE *)v9 + 1964) != 0) + 1;
                      *((_DWORD *)v9 + 178) = v58;
                      if ( (*(_DWORD *)(v20 + 4) & 2) != 0 )
                        goto LABEL_97;
                      v323 = v9;
                      p_lpVtbl = &v323;
                      v325 = v20;
                      CRotateBackBufferIdentities<CDXGISwapChainWrapper>::RotateBackBufferIdentities(&p_lpVtbl, v56);
                      v20 = *((unsigned int *)v9 + 1140);
                      if ( (_DWORD)v20 )
                      {
                        v20 = (unsigned int)(v20 - 1);
                        if ( (_DWORD)v20 )
                        {
                          v20 = (unsigned int)(v20 - 2);
                          if ( (unsigned int)v20 < 2 )
                          {
                            if ( *((_DWORD *)v9 + 111)
                              || *((_DWORD *)v9 + 82) == 2
                              && (*((_BYTE *)v9 + 665)
                               || *((char *)v9 + 288) < 0
                               || (!*((_BYTE *)v9 + 2530) ? (v273 = 0) : (v273 = (const struct _LUID *)(v9 + 317)),
                                   (v274 = v9[40], v275 = *((unsigned int *)v274 + 187), (_DWORD)v275 == -1)
                                 ? (v276 = (CDXGIBaseAdapter *)((char *)v274 + 752))
                                 : (v276 = (const struct SAdapterDesc *)(*(_QWORD *)(*((_QWORD *)v274 + 21) + 280LL)
                                                                       + 536 * v275)),
                                   MaximizedWindowedModeFullscreenEnabled(v276, v9[29], v273) || *((_BYTE *)v9 + 2114))) )
                            {
                              if ( (*((_BYTE *)v9 + 1564) & 1) != 0 )
                              {
                                if ( v57 )
                                {
                                  v270 = (*(__int64 (__fastcall **)(CDXGIBaseAdapter *, CDXGIBaseAdapter *, _QWORD, _QWORD))(*(_QWORD *)v9[33] + 32LL))(
                                           v9[33],
                                           v57,
                                           0,
                                           0);
                                  dxgi_check<DXGIContract<Valid<0>,Valid<2289696773>,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp>>(v270);
                                }
                                for ( i = 0; (unsigned int)i < *((_DWORD *)v9 + 529); i = (unsigned int)(i + 1) )
                                {
                                  v272 = (*(__int64 (__fastcall **)(CDXGIBaseAdapter *, CDXGIBaseAdapter *, _QWORD, _QWORD))(*(_QWORD *)v9[33] + 32LL))(
                                           v9[33],
                                           v9[i + 220],
                                           0,
                                           0);
                                  dxgi_check<DXGIContract<Valid<0>,Valid<2289696773>,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp>>(v272);
                                }
                              }
                            }
                          }
                        }
                      }
                      if ( !v9[565]
                        || !v9[266]
                        || (SwapchainBufferForProtection = CDXGISwapChain::AcquireNextIndirectBuffer((CDXGISwapChain *)v9),
                            SwapchainBufferForProtection >= 0) )
                      {
                        SwapchainBufferForProtection = 0;
                        if ( *((_DWORD *)v9 + 527) )
                        {
                          v293 = v9[266];
                          if ( v293 )
                          {
                            v360 = 0;
                            v361 = 0;
                            LODWORD(v360) = CDXGIOutput::GetAdapterHandle(v293);
                            HIDWORD(v360) = *(_DWORD *)(v294 + 256);
                            v361 = *((_BYTE *)v9 + 2106) != 0;
                            D3DKMTSetVidPnSourceHwProtection(&v360);
                          }
                          if ( *((_BYTE *)v9 + 2112) )
                          {
                            if ( (Microsoft_Windows_DXGIEnableBits & 2) != 0 )
                              McTemplateU0pq_EtwEventWriteTransfer(
                                v293,
                                EventSetHardwareProtectionOnSwapChainBuffer,
                                v9,
                                *((unsigned __int8 *)v9 + 2106));
                            SwapchainBufferForProtection = (*(__int64 (__fastcall **)(CDXGIBaseAdapter *, CDXGIBaseAdapter *, _QWORD))(*(_QWORD *)v9[33] + 304LL))(
                                                             v9[33],
                                                             v9[220],
                                                             *((unsigned __int8 *)v9 + 2106));
                          }
                          else
                          {
                            if ( (Microsoft_Windows_DXGIEnableBits & 2) != 0 )
                              McTemplateU0pq_EtwEventWriteTransfer(
                                v293,
                                EventReCreateSwapChainBufferForHardwareProtection,
                                v9,
                                *((unsigned __int8 *)v9 + 2106));
                            SwapchainBufferForProtection = CDXGISwapChain::ReCreateSwapchainBufferForProtection(
                                                             (CDXGISwapChain *)v9,
                                                             (struct IDXGIResource *)v9[220]);
                            if ( v9[565] )
                            {
                              v295 = v9[266];
                              if ( v295 )
                              {
                                v298[5] = 0;
                                CDXGISwapChain::SetupIndirectSwapChain((CDXGISwapChain *)v9, 1, v295, &v298[5]);
                              }
                            }
                          }
                          if ( SwapchainBufferForProtection < 0 )
                          {
                            if ( (Microsoft_Windows_DXGIEnableBits & 2) != 0 )
                              McTemplateU0pq_EtwEventWriteTransfer(
                                v20,
                                EventSetHardwareProtectionFailure,
                                v9,
                                (unsigned int)SwapchainBufferForProtection);
                            (*(void (__fastcall **)(CDXGIBaseAdapter *, __int64))(*(_QWORD *)v9[33] + 264LL))(
                              v9[33],
                              2289696816LL);
                            SwapchainBufferForProtection = -2005270523;
                          }
                          --*((_DWORD *)v9 + 527);
                        }
                      }
                      if ( SwapchainBufferForProtection >= 0 )
                      {
LABEL_97:
                        SwapchainBufferForProtection = *(_DWORD *)v298;
                        if ( !*(_DWORD *)v298 )
                        {
LABEL_99:
                          if ( !v9[565] || !v9[266] )
                            goto LABEL_100;
                          v60 = *(int *)v298 < 0;
                          if ( *(_DWORD *)v298 )
                          {
LABEL_101:
                            if ( v60 )
                              goto LABEL_102;
                            goto LABEL_141;
                          }
                          if ( *((_DWORD *)v9 + 82) )
                          {
LABEL_141:
                            if ( v16 )
                            {
                              if ( ((v16 - 142213121) & 0xFFFFFFFB) != 0 )
                              {
                                CModule::RecordJournalImpl((CModule *)v20, v16, "Contract breached!", top);
                                CModule::RecordJournalImpl(v260, v16, "Contract breached!", v261);
                              }
                              *(_DWORD *)v298 = v16;
                              CModule::RecordJournalImpl((CModule *)v20, v16, "Non-zero return value", top);
                            }
LABEL_102:
                            v61 = *((_DWORD *)v9 + 1140);
                            if ( (!v61 || (v62 = v61 - 1) == 0 || (unsigned int)(v62 - 2) >= 2)
                              && *(_DWORD *)v298 == 142213121 )
                            {
                              if ( !*((_DWORD *)xmmword_180109A10 + 53) )
                              {
LABEL_108:
                                (*v332)[1](v332);
                                return *(unsigned int *)v298;
                              }
                              DXGI_SDK_MSG_SWAPCHAIN(
                                v9[38],
                                DXGI_MSG_IDXGISwapChain_Present_BlitModelUsedWhileRegisteredForOcclusionStatusEvents);
                            }
                            if ( *(_DWORD *)v298 == -2005270523 )
                              *((_DWORD *)v9 + 395) = 0;
                            goto LABEL_108;
                          }
                          if ( a5 || v307 != 1 || (v205 = lprc, !IsRectEmpty(lprc)) || v205->left || v205->top )
                          {
                            *((_DWORD *)v9 + 1136) = 0;
                            if ( !*((_DWORD *)v9 + 1135) )
                            {
LABEL_100:
                              v60 = *(int *)v298 < 0;
                              goto LABEL_101;
                            }
                          }
                          else if ( ++*((_DWORD *)v9 + 1136) >= *((_DWORD *)v9 + 1135) )
                          {
                            goto LABEL_100;
                          }
                          *(_DWORD *)v298 = 142213167;
                          CModule::RecordJournalImpl((CModule *)v20, 0x87A002Fu, "Non-zero return value", top);
                          goto LABEL_100;
                        }
                      }
                      else
                      {
                        *(_DWORD *)v298 = SwapchainBufferForProtection;
                      }
                      CModule::RecordJournalImpl(
                        (CModule *)v20,
                        SwapchainBufferForProtection,
                        "Non-zero return value",
                        top);
                      goto LABEL_99;
                    }
                  }
                }
                if ( (v8[1] & 8) != 0 && CDXGISwapChain::IsWaitForQueuedPresentPending((CDXGISwapChain *)v9) )
                {
                  *(_DWORD *)v298 = -2005270518;
                  CModule::RecordJournalImpl((CModule *)v20, 0x887A000A, "Non-zero return value", top);
                }
                if ( !v16 )
                  goto LABEL_41;
                if ( ((v16 - 142213121) & 0xFFFFFFFB) != 0 )
                  CModule::RecordJournalImpl((CModule *)v20, v16, "Contract breached!", top);
                if ( (unsigned __int8)CDXGISwapChain::IsFlipModel<0>(v9) && CDXGISwapChain::IsWindowedInternal(v49) )
                  v32 = 1;
                else
LABEL_41:
                  v32 = 0;
                if ( *(_DWORD *)v298 != 142213122 && *(_DWORD *)v298 && (!v32 || *(_DWORD *)v298 == -2005270518) )
                {
LABEL_67:
                  (*(void (__fastcall **)(CDXGIBaseAdapter *, _QWORD))(*(_QWORD *)v9[33] + 112LL))(v9[33], 0);
                  goto LABEL_81;
                }
                if ( *((_BYTE *)v9 + 2103) )
                {
                  *((_BYTE *)v9 + 2103) = 0;
                  v33 = *((_DWORD *)v9 + 109);
                  v34 = *((_DWORD *)v9 + 103);
                  v35 = *((_DWORD *)v9 + 102);
                  v36 = *((_DWORD *)v9 + 100);
                  v37 = *((_DWORD *)v9 + 99);
                  v38 = *((int *)v9 + 98);
                  if ( v38 >= 0x74 || *((_DWORD *)&CD3D11FormatHelper::s_FormatDetail + 10 * v38) == -1 )
                    Name = "Unrecognized";
                  else
                    Name = CD3D11FormatHelper::GetName((enum DXGI_FORMAT)v38, (bool)&CD3D11FormatHelper::s_FormatDetail);
                  StringCbPrintfA(
                    v367,
                    0x100u,
                    "DXGI_SWAP_CHAIN_DESC::BufferDesc = { %d, %d, { %d, %d }, %s, %d, %d }; DXGI_SWAP_CHAIN_DESC::SampleD"
                    "esc = { %d, %d }; DXGI_SWAP_CHAIN_DESC::Flags = %#x;",
                    *((_DWORD *)v9 + 94),
                    *((_DWORD *)v9 + 95),
                    *((_DWORD *)v9 + 96),
                    *((_DWORD *)v9 + 97),
                    Name,
                    v37,
                    v36,
                    v35,
                    v34,
                    v33);
                  DXGI_SDK_MSG_SWAPCHAIN(v9[38], DXGI_MSG_IDXGISwapChain_Present_NonOptimalFSConfiguration, v367);
                }
                CDXGISwapChain::IncrementPresentCount((CDXGISwapChain *)v9);
                v41 = *((_DWORD *)v9 + 234);
                v42 = v41 + 1;
                if ( v41 >= v41 + 1 )
                  v42 = *((_DWORD *)v9 + 234);
                *((_DWORD *)v9 + 234) = v42;
                memset(&pwi.rcWindow, 0, 56);
                pwi.cbSize = 60;
                if ( v9[42] && (unsigned __int8)IsDwmSetWindowAttributePresent() && !GetWindowInfo((HWND)v9[42], &pwi) )
                  goto LABEL_81;
                v359 = 0;
                v43 = 0;
                v316 = 0;
                v44 = 0;
                if ( *((_DWORD *)v9 + 111) )
                  goto LABEL_53;
                if ( *((_DWORD *)v9 + 82) == 2 )
                {
                  if ( *((_BYTE *)v9 + 665) || *((char *)v9 + 288) < 0 )
                    goto LABEL_53;
                  v109 = (const struct _LUID *)(v9 + 317);
                  if ( !*((_BYTE *)v9 + 2530) )
                    v109 = 0;
                  v110 = v9[40];
                  v111 = *((unsigned int *)v110 + 187);
                  v112 = (_DWORD)v111 == -1
                       ? (CDXGIBaseAdapter *)((char *)v110 + 752)
                       : (const struct SAdapterDesc *)(*(_QWORD *)(*((_QWORD *)v110 + 21) + 280LL) + 536 * v111);
                  if ( MaximizedWindowedModeFullscreenEnabled(v112, v9[29], v109) || *((_BYTE *)v9 + 2114) )
                  {
LABEL_53:
                    v45 = *((_DWORD *)v9 + 1140);
                    if ( v45 && (v46 = v45 - 1) != 0 && (v47 = (unsigned int)(v46 - 2), (unsigned int)v47 < 2) )
                    {
                      v43 = 6;
                      v262 = *((_BYTE *)v9 + 940) & 1;
                      if ( v9[153]
                        && ((v306[1] = 1, !(unsigned __int8)IsDwmpDxgiIsThreadDesktopCompositedPresent())
                         || (int)DwmpDxgiIsThreadDesktopComposited(&v306[1]) < 0
                         || v306[1]) )
                      {
                        v263 = 1;
                        v264 = 1;
                      }
                      else
                      {
                        v263 = 0;
                        v264 = 0;
                      }
                      *((_BYTE *)v9 + 940) &= ~1u;
                      *((_BYTE *)v9 + 940) |= v263;
                      if ( v262 != v263 )
                      {
                        *((_BYTE *)v9 + 1584) = 1;
                        if ( (Microsoft_Windows_DXGIEnableBits & 2) != 0 )
                          McTemplateU0pq_EtwEventWriteTransfer(v47, EventDWMRedirectionChange, v9, v264);
                      }
                      if ( (*((_BYTE *)v9 + 940) & 1) == 0 && ((*((_DWORD *)v9 + 82) - 3) & 0xFFFFFFFD) != 0 )
                      {
                        if ( (v315 & 1) != 0 )
                        {
                          DXGI_SDK_MSG_SWAPCHAIN(
                            v9[38],
                            DXGI_MSG_IDXGISwapChain_Present_ProtectedContentInWindowedModeWithDWMOffOrInvalidDisplayAffinity,
                            v40,
                            v264);
                          *(_DWORD *)v298 = -2005270486;
                          CModule::RecordJournalImpl(v268, 0x887A002A, "Non-zero return value", v269);
                        }
                        else
                        {
                          v43 = 5;
                        }
                      }
                      v265 = v309;
                      if ( v309 == 1 && (byte_180109BBE & 2) != 0 )
                        v265 = !CDXGISwapChain::IsOutputVariableRefreshRate((CDXGISwapChain *)v9);
                      if ( *((_DWORD *)v9 + 111) == 1 )
                      {
                        v266 = *((_DWORD *)v9 + 107);
                        if ( !v266 || (v267 = v266 - 1) == 0 || (unsigned int)(v267 - 2) >= 2 )
                        {
                          v48 = v305;
                          if ( v265 )
                            v44 = 1;
LABEL_70:
                          pdwAffinity = 1;
                          memset_0(v367, 0, 0x104u);
                          if ( *(int *)v298 < 0 )
                            goto LABEL_81;
                          switch ( v43 )
                          {
                            case 4:
                              goto LABEL_67;
                            case 6:
                              v52 = (struct DXGI_SCROLL_RECT *)v312;
                              if ( !a5 )
                                v52 = 0;
                              v53 = v309;
                              v54 = CDXGISwapChain::FlipPresentToDWM(
                                      (CDXGISwapChain *)v9,
                                      (__int64)&pdwAffinity,
                                      v307,
                                      (__int64)lprc,
                                      v52,
                                      (__int64)&v315);
                              *(_DWORD *)v298 = v54;
                              if ( v54 )
                                CModule::RecordJournalImpl(v55, v54, "Non-zero return value", top);
                              if ( *(_DWORD *)v298 == 142213124 )
                              {
                                *((_BYTE *)v9 + 1584) = 1;
                                *(_DWORD *)v298 = 0;
                              }
                              if ( v44 )
                                CDXGISwapChain::ExplicitSynch((CDXGISwapChain *)v9, v53);
                              goto LABEL_81;
                            case 1:
                              v245 = pwi.rcClient.left - pwi.rcWindow.left;
                              v246 = pwi.rcClient.top - pwi.rcWindow.top;
                              v247 = pwi.rcClient.right - pwi.rcWindow.left;
                              v248 = pwi.rcClient.bottom - pwi.rcWindow.top;
                              v249 = *((_DWORD *)v9 + 228);
                              if ( v249 < pwi.rcClient.left - pwi.rcWindow.left )
                                v245 = *((_DWORD *)v9 + 228);
                              v359.left = v245;
                              if ( v249 < v247 )
                                v247 = v249;
                              v359.right = v247;
                              v250 = *((_DWORD *)v9 + 229);
                              if ( v250 < v246 )
                                v246 = *((_DWORD *)v9 + 229);
                              v359.top = v246;
                              if ( v250 < v248 )
                                v248 = v250;
                              v359.bottom = v248;
                              v251 = (const struct DXGI_SCROLL_RECT *)v312;
                              if ( !a5 )
                                v251 = 0;
                              v252 = lprc;
                              v253 = v307;
                              v254 = CDXGISwapChain::ComposePartialPresentation(
                                       (CDXGISwapChain *)v9,
                                       (struct _D3DKMT_DIRTYREGIONS *)v367,
                                       v48,
                                       &pdwAffinity,
                                       v307,
                                       (struct IDXGIResource *)lprc,
                                       v251);
                              *(_DWORD *)v298 = v254;
                              if ( v254 )
                                CModule::RecordJournalImpl(v255, v254, "Non-zero return value", top);
                              if ( *(int *)v298 >= 0 )
                              {
                                v256 = qword_1800D6050;
                                if ( (v48 & 0x10) == 0 )
                                  v256 = qword_1800D57B0;
                                v257 = CDXGISwapChain::EmulateDirtyRectPresentVistaBlt(
                                         (CDXGISwapChain *)v9,
                                         v252,
                                         v253,
                                         &v359,
                                         (const struct SUBRESOURCE_BLT_MAP *)v256,
                                         v316);
                                *(_DWORD *)v298 = v257;
                                if ( v257 )
                                  CModule::RecordJournalImpl(v258, v257, "Non-zero return value", top);
                                if ( *(_DWORD *)v367 )
                                {
                                  for ( j = 1; j < *(_DWORD *)v367; ++j )
                                    UnionRect(rcDst, rcDst, &rcDst[j]);
                                  *(_DWORD *)v367 = 1;
                                  CDXGISwapChain::TransformDirtyRegions(
                                    (CDXGISwapChain *)v9,
                                    (struct _D3DKMT_DIRTYREGIONS *)v367,
                                    &v359);
                                }
                              }
                              goto LABEL_81;
                          }
                          if ( v32 )
                          {
                            if ( !v16 || v16 == 142213125 )
                            {
                              *(_DWORD *)v298 = v16;
                              if ( v16 )
                                CModule::RecordJournalImpl(v51, v16, "Non-zero return value", top);
                            }
                            else if ( v16 == 142213121 )
                            {
                              *(_DWORD *)v298 = 142213121;
                              CModule::RecordJournalImpl(v51, 0x87A0001u, "Non-zero return value", top);
                            }
                            else
                            {
                              CModule::RecordJournalImpl(v51, v16, "Contract breached!", top);
                              *(_DWORD *)v298 = v16;
                              CModule::RecordJournalImpl(v277, v16, "Non-zero return value", v278);
                            }
                            goto LABEL_81;
                          }
                          if ( *((_DWORD *)v9 + 111)
                            || *((_DWORD *)v9 + 82) == 2
                            && (*((_BYTE *)v9 + 665)
                             || *((char *)v9 + 288) < 0
                             || (*((_BYTE *)v9 + 2530) ? (v170 = (const struct _LUID *)(v9 + 317)) : (v170 = 0),
                                 (v202 = v9[40], v203 = *((unsigned int *)v202 + 187), (_DWORD)v203 == -1)
                               ? (v204 = (CDXGIBaseAdapter *)((char *)v202 + 752))
                               : (v204 = (const struct SAdapterDesc *)(*(_QWORD *)(*((_QWORD *)v202 + 21) + 280LL)
                                                                     + 536 * v203)),
                                 MaximizedWindowedModeFullscreenEnabled(v204, v9[29], v170) || *((_BYTE *)v9 + 2114))) )
                          {
                            if ( *((_DWORD *)v9 + 98) == 89 )
                            {
                              *(_DWORD *)v298 = -2005270524;
                              CModule::RecordJournalImpl(v51, 0x887A0004, "Non-zero return value", top);
                              goto LABEL_81;
                            }
                          }
                          v76 = (unsigned int)(v43 - 2) <= 1;
                          BYTE1(v306[0]) = v76;
                          v335 = 0;
                          v336 = 0;
                          v339[1] = 0;
                          memset_0(v343, 0, 0x5BCu);
                          v339[0] = 0;
                          v342 = 0;
                          v340 = v9[42];
                          v77 = 0;
                          v341 = -1;
                          v78 = v9[266];
                          if ( v78 )
                          {
                            v77 = v9[266];
                            v341 = *((_DWORD *)v78 + 64);
                          }
                          v79 = 0;
                          if ( (v48 & 0x40) != 0 )
                          {
                            v77 = v9[267];
                            v341 = *((_DWORD *)v77 + 64);
                            v79 = 256;
                          }
                          v343[0] = 0;
                          v344 = 0;
                          v345 = *((_DWORD *)v9 + 94);
                          v346 = *((_DWORD *)v9 + 95);
                          v348 = (RECT *)&v344;
                          v347 = 1;
                          v80 = *((_DWORD *)v9 + 98);
                          if ( v80 != 67 && v80 != 10 || v9[237] && IsColorFormatLinear(*((enum DXGI_FORMAT *)v9 + 496)) )
                            v81 = 4225;
                          else
                            v81 = 6273;
                          v349 = *((_DWORD *)v9 + 393);
                          v82 = v79 | v81 | (!v76 << 13);
                          v351 = v82;
                          v83 = *((_DWORD *)v9 + 82);
                          if ( v83 == 1 )
                          {
                            v351 = v82 | ((v48 & 0x80 | 0x40) << 17);
                            v82 = v351 & 0xFDFFFFFF | ((IsRemoteDevice() & 1) << 25);
                            v351 = v82;
                            v83 = *((_DWORD *)v9 + 82);
                          }
                          if ( *((_DWORD *)v9 + 111) )
                          {
LABEL_159:
                            if ( *((_DWORD *)v9 + 82) != 1 || !v77 || !CDXGIOutput::IsIndirectOutput(v77) )
                            {
LABEL_160:
                              v303 = 0;
                              v84 = *((_DWORD *)v9 + 82) != 1;
                              v298[5] = 0;
                              v20 = (unsigned __int64)qword_1800D57B0;
                              if ( *((_DWORD *)v9 + 111) || !v9[237] )
                              {
LABEL_171:
                                if ( !v76 && v84 )
                                {
                                  CDXGISwapChain::ExplicitSynch((CDXGISwapChain *)v9, v309);
                                  v82 = v351;
                                }
                                v304 = (v82 & 4) != 0
                                    && !v9[238]
                                    && ((v20 = *((unsigned int *)v9 + 1140), !(_DWORD)v20)
                                     || (v20 = (unsigned int)(v20 - 1), (_DWORD)v20) && (_DWORD)v20 != 2
                                     || *((_DWORD *)v9 + 1141) != 1);
                                if ( (v82 & 1) != 0 && *((_BYTE *)v9 + 1964) && (v48 & 0x10) != 0 )
                                  v82 |= 0x100000u;
                                LOBYTE(v20) = 0;
                                v89 = v48 & 2;
                                v313 = v89;
                                v90 = v330;
                                v326 = v330;
                                v91 = v327;
                                v92 = v360;
                                v93 = (CDXGIBaseAdapter *)v323;
                                while ( 1 )
                                {
                                  v298[4] = v20;
                                  v50 = &v344;
                                  v348 = (RECT *)&v344;
                                  v347 = 1;
                                  v40 = (LONG *)(v82 & 0xFFFFFFBF);
                                  v351 = (unsigned int)v40;
                                  if ( !v89 )
                                    break;
                                  if ( ((unsigned __int8)v40 & 4) == 0 )
                                  {
                                    *(_DWORD *)v298 = 0;
                                    goto LABEL_267;
                                  }
                                  v206 = (struct IDXGIResource *)v320;
                                  if ( !v320 )
                                    v206 = (struct IDXGIResource *)v9[237];
                                  v299 = v206;
                                  v207 = v309;
                                  v300 = v309;
                                  v208 = *((_DWORD *)v9 + 557);
                                  if ( v208 )
                                  {
                                    v358 = *((_DWORD *)v9 + 557);
                                    LODWORD(v40) = (unsigned int)v40 | 0x8000000;
                                    v351 = (unsigned int)v40;
                                  }
                                  if ( *((_DWORD *)v9 + 82) )
                                  {
                                    if ( !v208
                                      && CDXGISwapChain::IsVariableRefreshRateOverrideEligible(
                                           (CDXGISwapChain *)v9,
                                           v309) )
                                    {
                                      v207 = 0;
                                      v300 = 0;
                                      if ( (Microsoft_Windows_DXGIEnableBits & 2) != 0 )
                                      {
                                        McTemplateU0ppq_EtwEventWriteTransfer(v238, v237, v9, v9[266]);
                                        LODWORD(v40) = v351;
                                        v207 = v300;
                                      }
                                    }
                                    v239 = 256;
                                    if ( v207 > 1 )
                                      v239 = 0;
                                    v240 = 130;
                                    if ( v207 )
                                      v240 = 2;
                                    v209 = v240 | v239;
                                  }
                                  else
                                  {
                                    v209 = 514;
                                    if ( !*((_BYTE *)v9 + 4556) )
                                      v209 = 2;
                                  }
                                  v306[1] = v209;
                                  if ( *((_BYTE *)v9 + 2529) )
                                  {
                                    v290 = v209;
                                    v105 = v207;
                                    v291 = v206;
                                    goto LABEL_699;
                                  }
                                  v241 = v9[33];
                                  if ( *((_BYTE *)v9 + 2532) && ((unsigned int)v40 & 0x10000) != 0 )
                                  {
                                    v279 = CDXGISwapChain::PrepareWindowedBltCrossAdapterSurface((CDXGISwapChain *)v9);
                                    v244 = v279;
                                    if ( v279 < 0 )
                                    {
                                      *(_DWORD *)v298 = v279;
                                      goto LABEL_265;
                                    }
                                    v242 = v9[439];
                                    v241 = v9[34];
                                  }
                                  else
                                  {
                                    v242 = (CDXGIBaseAdapter *)v299;
                                  }
                                  v322 = 0;
                                  (**(void (__fastcall ***)(CDXGIBaseAdapter *, GUID *, CModule **))v242)(
                                    v242,
                                    &GUID_79d2046c_22ef_451b_9e74_2245d9c760ea,
                                    &v322);
                                  v333 = 0;
                                  (*(void (__fastcall **)(CModule *, __int128 *))(*(_QWORD *)v322 + 24LL))(v322, &v333);
                                  DWORD2(v333) = 0;
                                  v297[0] = v300;
                                  LODWORD(v296) = v306[1];
                                  v243 = (*(__int64 (__fastcall **)(CDXGIBaseAdapter *, __int128 *, __int64, _QWORD, _DWORD *, struct tagRECT *, enum DXGI_FORMAT *, _QWORD))(*(_QWORD *)v241 + 24LL))(
                                           v241,
                                           &v333,
                                           1,
                                           0,
                                           v339,
                                           v296,
                                           *(enum DXGI_FORMAT **)v297,
                                           0);
                                  v244 = dxgi_check<DXGIContract<Valid<0>,Valid<2147942414>,Valid<2289696773>,Valid<142213126>,Valid<142213127>,Valid<2289696778>,Valid<142213121>,Valid<142213130>,Valid<142213167>,Valid<2289696769>,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp>>(v243);
                                  v123 = v322;
                                  if ( v322 )
                                    (*(void (__fastcall **)(CModule *))(*(_QWORD *)v322 + 16LL))(v322);
LABEL_264:
                                  *(_DWORD *)v298 = v244;
                                  if ( v244 )
                                    goto LABEL_265;
LABEL_266:
                                  v20 = v298[4];
LABEL_267:
                                  if ( *((_DWORD *)v9 + 111) )
                                    goto LABEL_331;
                                  if ( *(_DWORD *)v298 == 142213127 )
                                  {
                                    v219 = v9[266];
                                    v310 = v219;
                                    if ( !v219 )
                                      goto LABEL_758;
                                    v220 = (struct IDXGIResource *)v9[237];
                                    if ( !v220 || (_BYTE)v20 )
                                      goto LABEL_758;
                                    if ( *((_BYTE *)v9 + 2529) )
                                    {
                                      v90 = (struct IDXGIResource *)v9[*((unsigned int *)v9 + 874) + 318];
                                      v326 = v90;
                                      v330 = v90;
                                      if ( v90 )
                                      {
                                        ((void (__fastcall *)(struct IDXGIResource *))v90->lpVtbl->AddRef)(v90);
                                        v219 = v310;
                                      }
                                      v221 = v301 | 1;
                                      v220 = v90;
                                    }
                                    else
                                    {
                                      v91 = v9[237];
                                      v327 = v91;
                                      ((void (__fastcall *)(struct IDXGIResource *))v220->lpVtbl->AddRef)(v220);
                                      v221 = v301 | 2;
                                      v219 = v310;
                                    }
                                    v301 = v221;
                                    v222 = (int)CDXGIOutput::SetDisplaySurfaceInternal(v219, v220) >= 0;
                                    v223 = v301;
                                    if ( (v301 & 2) != 0 )
                                    {
                                      v223 = v301 & 0xFFFFFFFD;
                                      v301 &= ~2u;
                                      if ( v91 )
                                      {
                                        (*(void (__fastcall **)(CDXGIBaseAdapter *))(*(_QWORD *)v91 + 16LL))(v91);
                                        v223 = v301;
                                      }
                                    }
                                    if ( (v223 & 1) != 0 )
                                    {
                                      v301 = v223 & 0xFFFFFFFE;
                                      if ( v90 )
                                        ((void (__fastcall *)(struct IDXGIResource *))v90->lpVtbl->Release)(v90);
                                    }
                                    if ( !v222 )
                                    {
LABEL_758:
                                      if ( v9[42] )
                                      {
LABEL_529:
                                        v308[1] = 1;
                                        *(_DWORD *)v298 = 0;
                                        goto LABEL_83;
                                      }
LABEL_331:
                                      if ( *(_DWORD *)v298 == 142213126 )
                                      {
                                        *(_DWORD *)v298 = 0;
                                        goto LABEL_333;
                                      }
LABEL_332:
                                      if ( *(_DWORD *)v298 == -2005270527 )
                                      {
                                        if ( *((_DWORD *)v9 + 82) )
                                        {
                                          MicrosoftTelemetryAssertTriggeredNoArgs(v20);
                                          goto LABEL_333;
                                        }
                                      }
                                      else
                                      {
LABEL_333:
                                        if ( *(int *)v298 >= 0 )
                                        {
                                          QueryPerformanceCounter((LARGE_INTEGER *)v9 + 201);
                                          if ( !v320 )
                                          {
                                            LODWORD(v50) = v305;
                                            v144 = (v305 & 0x20) != 0 ? 1 : (*((_BYTE *)v9 + 1964) != 0) + 1;
                                            *((_DWORD *)v9 + 178) = v144;
                                            if ( ((unsigned __int8)v50 & 2) == 0 && v298[5] && *((char *)v9 + 288) >= 0 )
                                            {
                                              v145 = (*(__int64 (__fastcall **)(CDXGIBaseAdapter *, CDXGIBaseAdapter *, CDXGIBaseAdapter **, __int64))(*(_QWORD *)v9[33] + 32LL))(
                                                       v9[33],
                                                       v9[237],
                                                       v9 + 238,
                                                       1);
                                              v146 = dxgi_check<DXGIContract<Valid<0>,Valid<2289696773>,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp>>(v145);
                                              v148 = v146;
                                              if ( v146 )
                                              {
                                                CModule::RecordJournalImpl(v147, v146, "Non-zero return value", top);
                                                if ( v148 < 0 )
                                                  *(_DWORD *)v298 = v148;
                                              }
                                            }
                                          }
                                        }
                                      }
LABEL_81:
                                      v20 = (unsigned __int64)v9[34];
                                      if ( v20
                                        && (*(int (__fastcall **)(unsigned __int64))(*(_QWORD *)v20 + 176LL))(v20) < 0 )
                                      {
                                        *(_DWORD *)v298 = -2005270523;
                                        CModule::RecordJournalImpl(
                                          (CModule *)v20,
                                          0x887A0005,
                                          "Non-zero return value",
                                          top);
                                        if ( *(int *)v298 < 0 )
                                          CModule::RecordJournalImpl(
                                            v159,
                                            *(unsigned int *)v298,
                                            "Hybrid present: iGPU removed, removing dGPU",
                                            v160);
                                        (*(void (__fastcall **)(CDXGIBaseAdapter *))(*(_QWORD *)v9[33] + 264LL))(v9[33]);
                                      }
                                      goto LABEL_82;
                                    }
                                    LOBYTE(v20) = 1;
                                    v82 = v351;
                                    v89 = v313;
                                  }
                                  else
                                  {
                                    if ( *(_DWORD *)v298 != 142213121 )
                                      goto LABEL_331;
                                    if ( v9[42] )
                                      goto LABEL_529;
                                    v124 = v9[266];
                                    if ( !v124 )
                                      goto LABEL_332;
                                    v50 = (__int64 *)*((_QWORD *)v124 + 21);
                                    if ( v50[44] )
                                    {
                                      if ( *((_BYTE *)v124 + 264) )
                                        goto LABEL_332;
                                      v20 = *((unsigned int *)v124 + 64);
                                      if ( (_DWORD)v20 == -1 )
                                        goto LABEL_332;
                                      v318[0] = 0;
                                      v318[1] = v20;
                                      v125 = *((_DWORD *)v124 + 109);
                                      if ( !v125 )
                                        v125 = *((_DWORD *)v50 + 55);
                                      v318[0] = v125;
                                      v126 = ((__int64 (__fastcall *)(_DWORD *))v50[44])(v318);
                                      v127 = v126;
                                      if ( !v126 || v126 == -1073741811 || v126 == -1073741130 )
                                      {
                                        if ( v126 == -1073741130 )
                                          goto LABEL_331;
                                      }
                                      else
                                      {
                                        v20 = v126 + 1071775739;
                                        if ( (unsigned int)v20 > 1 )
                                        {
                                          if ( v126 == -2145517568 )
                                            goto LABEL_331;
                                          CModule::RecordJournalImpl((CModule *)v20, v126, "Contract breached!", top);
LABEL_283:
                                          if ( (unsigned int)NTStatusToHResult(v127) )
                                            goto LABEL_331;
                                          goto LABEL_284;
                                        }
                                      }
                                      if ( v126 == -1071775738 || v126 == -1071775739 )
                                        goto LABEL_331;
                                      goto LABEL_283;
                                    }
LABEL_284:
                                    if ( !v9[237] || v298[4] )
                                      goto LABEL_331;
                                    lpVtbl = v9[266];
                                    v128 = (HWND)v9[42];
                                    v129 = 0;
                                    if ( v128 )
                                    {
                                      v306[1] = 0;
                                      if ( GetWindowDisplayAffinity(v128, &v306[1]) )
                                      {
                                        if ( v306[1] == 1 )
                                          v129 = 1;
                                      }
                                    }
                                    if ( *((_BYTE *)v9 + 664) )
                                    {
                                      (*(void (__fastcall **)(CDXGIBaseAdapter *, char *))(*(_QWORD *)v9[33] + 104LL))(
                                        v9[33],
                                        v331);
                                      if ( (v331[0] & 1) == 0 && !v129 )
                                      {
LABEL_735:
                                        v300 = 1;
                                        goto LABEL_291;
                                      }
                                    }
                                    else if ( (*((_BYTE *)v9 + 436) & 0x20) == 0 && !v129 )
                                    {
                                      goto LABEL_735;
                                    }
                                    v300 = 0;
LABEL_291:
                                    if ( v9[42] || ((_BYTE)v9[55] & 8) != 0 )
                                      v130 = CDXGISwapChain::IsMaximizedWindowedFullscreenEnabled((CDXGISwapChain *)v9)
                                           + 2;
                                    else
                                      v130 = 1;
                                    v131 = v9[266];
                                    if ( v131 && CDXGIOutput::IsIndirectOutput(v131) )
                                    {
                                      v292 = v9[566];
                                      v299 = (struct IDXGIResource *)v292;
                                      v310 = v292;
                                      if ( v292 )
                                      {
                                        (*(void (__fastcall **)(CDXGIBaseAdapter *))(*(_QWORD *)v292 + 8LL))(v292);
                                        v292 = (CDXGIBaseAdapter *)v299;
                                      }
                                      else
                                      {
                                        v299 = 0;
                                      }
                                      if ( v292 )
                                        (*(void (__fastcall **)(CDXGIBaseAdapter *))(*(_QWORD *)v292 + 8LL))(v292);
                                      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v310);
                                      if ( v299 )
                                        ((void (__fastcall *)(struct IDXGIResource *))v299->lpVtbl->Release)(v299);
                                    }
                                    else
                                    {
                                      if ( *((_BYTE *)v9 + 2529) )
                                        v132 = v9[34];
                                      else
                                        v132 = v9[33];
                                      v299 = (struct IDXGIResource *)v132;
                                    }
                                    if ( (int)CDXGIOutput::TakeOwnershipImpl(lpVtbl, v299, 0, v130, v300) < 0 )
                                      goto LABEL_331;
                                    v133 = v9[266];
                                    v299 = (struct IDXGIResource *)v133;
                                    if ( *((_BYTE *)v9 + 2529) )
                                    {
                                      v92 = v9[*((unsigned int *)v9 + 874) + 318];
                                      v360 = v92;
                                      if ( v92 )
                                      {
                                        (*(void (__fastcall **)(CDXGIBaseAdapter *))(*(_QWORD *)v92 + 8LL))(v92);
                                        v133 = (CDXGIBaseAdapter *)v299;
                                      }
                                      v301 |= 4u;
                                      v134 = v92;
                                    }
                                    else
                                    {
                                      v93 = v9[237];
                                      v323 = (CDXGIBaseAdapter **)v93;
                                      if ( v93 )
                                      {
                                        (*(void (__fastcall **)(CDXGIBaseAdapter *))(*(_QWORD *)v93 + 8LL))(v93);
                                        v133 = (CDXGIBaseAdapter *)v299;
                                      }
                                      v301 |= 8u;
                                      v134 = v93;
                                    }
                                    v135 = v133 ? (CDXGIBaseAdapter *)((char *)v133 + 152) : 0LL;
                                    v310 = v135;
                                    v328 = v135;
                                    (**(void (__fastcall ***)(CDXGIBaseAdapter *))v135)(v135);
                                    v329 = 1;
                                    if ( v299[64].lpVtbl && (unsigned int)(HIDWORD(v299[65].lpVtbl) - 1) <= 1 )
                                    {
                                      (*(void (__fastcall **)(CDXGIBaseAdapter *))(*(_QWORD *)v310 + 8LL))(v310);
                                      v329 = 0;
                                      if ( v134 )
                                      {
                                        LODWORD(v366) = 0;
                                        v306[1] = 44;
                                        if ( (*(int (__fastcall **)(CDXGIBaseAdapter *, __int64 *, _DWORD *, _DWORD *))(*(_QWORD *)v134 + 40LL))(
                                               v134,
                                               qword_1800D5848,
                                               &v306[1],
                                               v363) >= 0
                                          && v306[1] == 44 )
                                        {
                                          lpVtbl = (void *)CDXGIIUnknownNotifier<void,CDXGIOutput>::New(v136, v299);
                                          v300 = (*(__int64 (__fastcall **)(CDXGIBaseAdapter *, GUID *, void *))(*(_QWORD *)v134 + 32LL))(
                                                   v134,
                                                   &GUID_ae02eedb_c735_4690_8d52_5a8dc20213aa,
                                                   lpVtbl);
                                          if ( v300 < 0 )
                                          {
                                            operator delete(lpVtbl, 0x28u);
                                          }
                                          else
                                          {
                                            v137 = v299;
                                            ((void (__fastcall *)(struct IDXGIResource *))v299[19].lpVtbl->QueryInterface)(&v299[19]);
                                            lpVtbl = v137[64].lpVtbl;
                                            ((void (__fastcall *)(struct IDXGIResource *))v137[19].lpVtbl->AddRef)(&v137[19]);
                                            if ( !lpVtbl || CDXGIOutput::IsIndirectOutput((CDXGIOutput *)v137) )
                                              goto LABEL_321;
                                            v310 = 0;
                                            v139 = (**v138)(v138, &GUID_b898d4fd_b5b3_4ffc_8694_0259864ffcf8, &v310);
                                            v300 = v139;
                                            if ( v139 >= 0 )
                                            {
                                              v139 = (*(__int64 (__fastcall **)(CDXGIBaseAdapter *, CDXGIBaseAdapter *))(*(_QWORD *)v310 + 64LL))(
                                                       v310,
                                                       v134);
                                              v300 = v139;
                                              if ( !(unsigned __int8)DXGIContract<Valid<0>,Valid<2147942414>,Valid<2289696773>,Valid<2147500037>,Valid<2289696805>,Valid<2289436794>,Valid<2147500034>,Valid<2147500035>,Valid<2289696770>,Valid<2147942487>,Valid<2289696771>,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp>::Validate((unsigned int)v139) )
                                                CModule::RecordJournalImpl(v140, v139, "Contract breached!", top);
                                            }
                                            v20 = (unsigned __int64)v310;
                                            if ( v310 )
                                              (*(void (__fastcall **)(CDXGIBaseAdapter *))(*(_QWORD *)v310 + 16LL))(v310);
                                            if ( v139 >= 0 )
                                            {
LABEL_321:
                                              v141 = v299;
                                              ((void (__fastcall *)(struct IDXGIResource *))v299[19].lpVtbl->QueryInterface)(&v299[19]);
                                              v141[1611].lpVtbl = (struct IDXGIResourceVtbl *)v134;
                                              ((void (__fastcall *)(struct IDXGIResource *))v141[19].lpVtbl->AddRef)(&v141[19]);
                                            }
                                            v9 = v319;
                                          }
                                          LODWORD(v134) = v300;
                                        }
                                        else
                                        {
                                          DXGI_SDK_MSG(
                                            (struct CDXGIFactory *)v299[21].lpVtbl[1].GetUsage,
                                            DXGI_MSG_IDXGIOutput_SetDisplaySurface_pPrimaryIsInvalid);
                                          LODWORD(v134) = -2147024809;
                                        }
                                      }
                                      else
                                      {
                                        LOBYTE(v325) = 0;
                                        p_lpVtbl = &v299[19].lpVtbl;
                                        CThreadLock<0>::TakeLock(&p_lpVtbl);
                                        v299[1611].lpVtbl = 0;
                                        CThreadLock<0>::ReleaseLock(&p_lpVtbl);
                                      }
                                    }
                                    else
                                    {
                                      DXGI_SDK_MSG(
                                        (struct CDXGIFactory *)v299[21].lpVtbl[1].GetUsage,
                                        DXGI_MSG_IDXGIOutput_SetDisplaySurface_NoOwnerDevice);
                                      CThreadLock<0>::ReleaseLock(&v328);
                                      LODWORD(v134) = -2005270527;
                                    }
                                    v142 = (int)v134 >= 0;
                                    v143 = v301;
                                    if ( (v301 & 8) != 0 )
                                    {
                                      v143 = v301 & 0xFFFFFFF7;
                                      v301 &= ~8u;
                                      if ( v93 )
                                      {
                                        (*(void (__fastcall **)(CDXGIBaseAdapter *))(*(_QWORD *)v93 + 16LL))(v93);
                                        v143 = v301;
                                      }
                                    }
                                    if ( (v143 & 4) != 0 )
                                    {
                                      v301 = v143 & 0xFFFFFFFB;
                                      if ( v92 )
                                        (*(void (__fastcall **)(CDXGIBaseAdapter *))(*(_QWORD *)v92 + 16LL))(v92);
                                    }
                                    if ( !v142 )
                                      goto LABEL_331;
                                    LOBYTE(v20) = 1;
                                    v82 = v351;
                                    v89 = v313;
                                  }
                                }
                                v94 = 0;
                                if ( v9[42] )
                                {
                                  *(_QWORD *)&v359.left = 0;
                                  v359.right = pwi.rcClient.right - pwi.rcClient.left;
                                  v359.bottom = pwi.rcClient.bottom - pwi.rcClient.top;
                                }
                                if ( v303 )
                                  v310 = v9[237];
                                else
                                  v310 = 0;
                                *(_DWORD *)v298 = 0;
                                if ( v9[238] )
                                  CurrentProxySurface = CDXGISwapChain::GetCurrentProxySurface((CDXGISwapChain *)v9);
                                else
                                  CurrentProxySurface = (struct IDXGIResource *)v9[220];
                                v299 = CurrentProxySurface;
                                if ( BYTE1(v306[0]) )
                                {
                                  v310 = v9[110];
                                  v351 = (unsigned int)v40
                                       ^ ((unsigned int)v40
                                        ^ (*((unsigned __int8 *)v9 + 2528) << 26))
                                       & 0x4000000
                                       | 0x10000;
                                  v352 = 3;
                                  v353 = v9[109];
                                  v354 = v316;
                                  v119 = (const struct DXGI_SCROLL_RECT *)v312;
                                  if ( !a5 )
                                    v119 = v94;
                                  v120 = v307;
                                  v121 = CDXGISwapChain::ComposePartialPresentation(
                                           (CDXGISwapChain *)v9,
                                           (struct _D3DKMT_DIRTYREGIONS *)v355,
                                           v305,
                                           &pdwAffinity,
                                           v307,
                                           (struct IDXGIResource *)lprc,
                                           v119);
                                  *(_DWORD *)v298 = v121;
                                  if ( v121 )
                                    CModule::RecordJournalImpl(v122, v121, "Non-zero return value", top);
                                  if ( *(int *)v298 >= 0 && v120 )
                                  {
                                    if ( v355[0] )
                                    {
                                      v175 = 0;
                                      right = v359.right;
                                      v177 = (float)(v359.right - v359.left) / (float)*((int *)v9 + 94);
                                      bottom = v359.bottom;
                                      top = v359.top;
                                      v179 = (float)(v359.bottom - v359.top) / (float)*((int *)v9 + 95);
                                      left = v359.left;
                                      do
                                      {
                                        v181 = 4LL * v175;
                                        *(_QWORD *)&v306[1] = v181 * 4;
                                        v182 = left + (int)(float)((float)(int)v355[v181 + 1] * v177);
                                        v355[v181 + 1] = v182;
                                        p_right = &v359.right;
                                        if ( right >= v182 )
                                          p_right = &v355[v181 + 1];
                                        v184 = right;
                                        if ( right >= v182 )
                                          v184 = v182;
                                        v185 = v184 < left;
                                        v186 = left;
                                        if ( !v185 )
                                          v186 = *p_right;
                                        v355[v181 + 1] = v186;
                                        v187 = top + (int)(float)((float)(int)v355[v181 + 2] * v179);
                                        v355[4 * v175 + 2] = v187;
                                        p_bottom = &v359.bottom;
                                        if ( bottom >= v187 )
                                          p_bottom = &v355[v181 + 2];
                                        v189 = bottom;
                                        if ( bottom >= v187 )
                                          v189 = v187;
                                        if ( v189 >= top )
                                          top = *p_bottom;
                                        v355[4 * v175 + 2] = top;
                                        v190 = &v355[v181 + 3];
                                        v191 = left + (int)o_ceilf_0((float)(int)v355[v181 + 3] * v177);
                                        v192 = *(_QWORD *)&v306[1];
                                        *(_DWORD *)((char *)&v355[3] + *(_QWORD *)&v306[1]) = v191;
                                        v193 = &v359.right;
                                        if ( right >= v191 )
                                          v193 = v190;
                                        v194 = right;
                                        if ( right >= v191 )
                                          v194 = v191;
                                        v185 = v194 < left;
                                        v195 = left;
                                        if ( !v185 )
                                          v195 = *v193;
                                        *(_DWORD *)((char *)&v355[3] + v192) = v195;
                                        v196 = (_DWORD *)((char *)&v355[4] + v192);
                                        v197 = o_ceilf_0((float)*(int *)((char *)&v355[4] + v192) * v179);
                                        top = v359.top;
                                        v198 = v359.top + (int)v197;
                                        v50 = *(__int64 **)&v306[1];
                                        *(_DWORD *)((char *)&v355[4] + *(_QWORD *)&v306[1]) = v198;
                                        v40 = &v359.bottom;
                                        bottom = v359.bottom;
                                        if ( v359.bottom >= v198 )
                                          v40 = v196;
                                        v199 = v359.bottom;
                                        if ( v359.bottom >= v198 )
                                          v199 = v198;
                                        v185 = v199 < top;
                                        v200 = top;
                                        if ( !v185 )
                                          v200 = *v40;
                                        *(_DWORD *)((char *)&v355[4] + (_QWORD)v50) = v200;
                                        ++v175;
                                      }
                                      while ( v175 < v355[0] );
                                      v90 = v326;
                                      v91 = v327;
                                      v9 = v319;
                                      v120 = v307;
                                      v343[1] = v359.left;
                                      v343[2] = top;
                                      v343[3] = v359.right;
                                      v343[4] = bottom;
                                      v351 |= 0x40u;
                                    }
                                    v348 = lprc;
                                    v347 = v120;
                                  }
                                  v350 = 1;
                                  CurrentProxySurface = v299;
                                  goto LABEL_202;
                                }
                                if ( *((_DWORD *)v9 + 82) <= 1u && (v307 || a5) )
                                {
                                  v351 = (unsigned int)v40 | 0x400000;
                                  LODWORD(v335) = v307;
                                  *((_QWORD *)&v335 + 1) = lprc;
                                  LODWORD(v336) = a5;
                                  v96 = (const struct DXGI_SCROLL_RECT *)v312;
                                  *((_QWORD *)&v336 + 1) = v312;
                                  v356 = &v335;
                                }
                                else
                                {
                                  v96 = (const struct DXGI_SCROLL_RECT *)v312;
                                }
                                pdwAffinity |= 2u;
                                v97 = v96;
                                if ( !a5 )
                                  v97 = v94;
                                v98 = CDXGISwapChain::ComposePartialPresentation(
                                        (CDXGISwapChain *)v9,
                                        (struct _D3DKMT_DIRTYREGIONS *)v367,
                                        v305,
                                        &pdwAffinity,
                                        v307,
                                        (struct IDXGIResource *)lprc,
                                        v97);
                                *(_DWORD *)v298 = v98;
                                if ( v98 )
                                  CModule::RecordJournalImpl(v99, v98, "Non-zero return value", top);
                                if ( *(int *)v298 >= 0
                                  && (*((_DWORD *)v9 + 111)
                                   || CDXGISwapChain::IsMaximizedWindowedFullscreenEnabled((CDXGISwapChain *)v9)) )
                                {
                                  v100 = v307;
                                  if ( (v307 || a5 || *((_DWORD *)v9 + 1143) == 1) && *((_DWORD *)v9 + 82) > 1u )
                                  {
                                    if ( a5 )
                                    {
                                      if ( *((_DWORD *)v9 + 1143) != 1 )
                                      {
                                        v348 = rcDst;
                                        v100 = *(_DWORD *)v367;
LABEL_198:
                                        v347 = v100;
                                        goto LABEL_199;
                                      }
                                    }
                                    else if ( *((_DWORD *)v9 + 1143) != 1 )
                                    {
                                      v348 = lprc;
                                      goto LABEL_198;
                                    }
                                    CDXGISwapChain::EmulateScalingNone(
                                      (CDXGISwapChain *)v9,
                                      (struct _D3DKMT_PRESENT *)v339,
                                      (struct _D3DKMT_DIRTYREGIONS *)v367,
                                      &v359);
                                  }
                                }
LABEL_199:
                                v40 = (LONG *)v9[282];
                                if ( v40 )
                                {
                                  v297[1] = DXGI_FORMAT_UNKNOWN;
                                  HIDWORD(v296) = HIDWORD(v9[282]);
                                  v101 = (*(__int64 (__fastcall **)(CDXGIBaseAdapter *, CDXGIBaseAdapter *, _QWORD))(*(_QWORD *)v9[33] + 56LL))(
                                           v9[33],
                                           v9[220],
                                           0);
                                  if ( v101
                                    && v101 != -2147467263
                                    && v101 != -2147024809
                                    && v101 != -2005270523
                                    && v101 != -2005270527 )
                                  {
                                    CModule::RecordJournalImpl(v102, v101, "Contract breached!", top);
                                  }
                                  CurrentProxySurface = (struct IDXGIResource *)v9[282];
                                }
LABEL_202:
                                if ( v320 )
                                  CurrentProxySurface = (struct IDXGIResource *)v320;
                                v299 = CurrentProxySurface;
                                if ( *(int *)v298 < 0 )
                                  goto LABEL_266;
                                v103 = *((_DWORD *)v9 + 107);
                                if ( v103 )
                                {
                                  v104 = v103 - 1;
                                  if ( v104 )
                                  {
                                    if ( (unsigned int)(v104 - 2) < 2 )
                                      (*(void (__fastcall **)(CDXGIBaseAdapter *, _QWORD, CDXGIBaseAdapter **, __int64, int))(*(_QWORD *)v9[33] + 96LL))(
                                        v9[33],
                                        0,
                                        v9 + 220,
                                        1,
                                        1);
                                  }
                                }
                                v105 = 0;
                                if ( ((v351 >> 2) & 1) != 0 )
                                  v105 = v309;
                                v300 = v105;
                                v106 = ((v351 >> 2) & 1) + 1;
                                v107 = *((_DWORD *)v9 + 557);
                                if ( v107 )
                                {
                                  v358 = *((_DWORD *)v9 + 557);
                                  v351 |= 0x8000000u;
                                }
                                if ( (v106 & 2) != 0 )
                                {
                                  if ( *((_DWORD *)v9 + 82) )
                                  {
                                    if ( !v107
                                      && CDXGISwapChain::IsVariableRefreshRateOverrideEligible(
                                           (CDXGISwapChain *)v9,
                                           v105) )
                                    {
                                      v105 = 0;
                                      v300 = 0;
                                      if ( (Microsoft_Windows_DXGIEnableBits & 2) != 0 )
                                      {
                                        McTemplateU0ppq_EtwEventWriteTransfer(v286, v285, v9, v9[266]);
                                        v105 = v300;
                                      }
                                    }
                                    v287 = 256;
                                    if ( v105 > 1 )
                                      v287 = 0;
                                    v288 = 128;
                                    if ( v105 )
                                      v288 = 0;
                                    v108 = v106 | v288 | v287;
                                  }
                                  else
                                  {
                                    v108 = v106 | (*((_BYTE *)v9 + 4556) != 0 ? 0x200 : 0);
                                  }
                                }
                                else
                                {
                                  v108 = v106;
                                }
                                v306[1] = v108;
                                if ( *((_BYTE *)v9 + 2529) )
                                {
                                  v290 = v108;
                                  v291 = v299;
LABEL_699:
                                  v244 = CDXGISwapChain::FlipHybridPrimary(
                                           (CDXGISwapChain *)v9,
                                           v291,
                                           v105,
                                           v290,
                                           (struct _D3DKMT_PRESENT *)v339);
                                  goto LABEL_264;
                                }
                                v280 = v9[33];
                                if ( *((_BYTE *)v9 + 2532) && (v351 & 0x10000) != 0 )
                                {
                                  v289 = CDXGISwapChain::PrepareWindowedBltCrossAdapterSurface((CDXGISwapChain *)v9);
                                  v244 = v289;
                                  if ( v289 < 0 )
                                  {
                                    *(_DWORD *)v298 = v289;
LABEL_265:
                                    CModule::RecordJournalImpl(v123, v244, "Non-zero return value", top);
                                    goto LABEL_266;
                                  }
                                  v281 = v9[439];
                                  v280 = v9[34];
                                }
                                else
                                {
                                  v281 = (CDXGIBaseAdapter *)v299;
                                }
                                v317 = 0;
                                (**(void (__fastcall ***)(CDXGIBaseAdapter *, GUID *, CModule **))v281)(
                                  v281,
                                  &GUID_79d2046c_22ef_451b_9e74_2245d9c760ea,
                                  &v317);
                                v334 = 0;
                                (*(void (__fastcall **)(CModule *, __int128 *))(*(_QWORD *)v317 + 24LL))(v317, &v334);
                                DWORD2(v334) = 0;
                                v297[0] = v300;
                                LODWORD(v296) = v306[1];
                                v282 = (*(__int64 (__fastcall **)(CDXGIBaseAdapter *, __int128 *, __int64, CDXGIBaseAdapter *, _DWORD *, struct tagRECT *, enum DXGI_FORMAT *, _QWORD))(*(_QWORD *)v280 + 24LL))(
                                         v280,
                                         &v334,
                                         1,
                                         v310,
                                         v339,
                                         v296,
                                         *(enum DXGI_FORMAT **)v297,
                                         0);
                                v244 = v282;
                                if ( v282 != -2147024882 )
                                {
                                  v284 = v282 - 142213121;
                                  if ( (unsigned int)v284 > 0x2E || (v283 = 0x400000000261LL, !_bittest64(&v283, v284)) )
                                  {
                                    if ( v244 )
                                    {
                                      if ( v244 + 2005270527 > 9
                                        || (v283 = 529, !_bittest((const int *)&v283, v244 + 2005270527)) )
                                      {
                                        CModule::RecordJournalImpl((CModule *)v283, v244, "Contract breached!", top);
                                      }
                                    }
                                  }
                                }
                                v123 = v317;
                                if ( v317 )
                                  (*(void (__fastcall **)(CModule *))(*(_QWORD *)v317 + 16LL))(v317);
                                goto LABEL_264;
                              }
                              if ( !*((_BYTE *)v9 + 2102) )
                              {
                                v303 = 1;
                                goto LABEL_166;
                              }
                              v303 = 0;
                              v85 = v82 & 0xFFFFFFFE;
                              v86 = v85 | 4;
                              if ( ((_BYTE)v9[246] & 4) != 0 )
                              {
                                if ( (v48 & 0x20) != 0 )
                                {
                                  v86 = v85 | 0x40004;
                                }
                                else if ( (v48 & 0x10) != 0 )
                                {
                                  v86 = v85 | 0xA0004;
                                }
                                else
                                {
                                  v86 = v85 | 0x20004;
                                }
                              }
                              v82 = v86 & 0xFFFFFF07 | (2 * (v48 & 8 | (2 * (v48 & 2 | (2 * (v48 & 4))))));
                              v351 = v82;
                              v87 = v309;
                              if ( v309 != 1 )
                              {
                                if ( v309 )
                                {
                                  switch ( v309 )
                                  {
                                    case 2u:
                                      v87 = 2;
                                      goto LABEL_165;
                                    case 3u:
                                      v87 = 3;
                                      goto LABEL_165;
                                    case 4u:
                                      v87 = 4;
                                      goto LABEL_165;
                                  }
                                }
                                v87 = 0;
                              }
LABEL_165:
                              v350 = v87;
                              v84 = 0;
                              v20 = (unsigned __int64)qword_1800D57B0;
LABEL_166:
                              if ( v9[238] )
                              {
                                v229 = CDXGISwapChain::GetCurrentProxySurface((CDXGISwapChain *)v9);
                                v234 = v233(v232, v9[220], 0, 0, 0, v229, 0, v230, 0, 0, v231);
                                dxgi_check<DXGIContract<Valid<0>,Valid<2147500033>,Valid<2147942487>,Valid<2289696773>,Valid<2289696769>,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp>>(v234);
                                v298[5] = 1;
                                v82 = v351;
                              }
                              if ( *((_DWORD *)v9 + 500) == 1 || ((_BYTE)v9[246] & 2) != 0 )
                                v88 = 0;
                              else
                                v88 = 0x2000;
                              v82 = v88 | v82 & 0xFFFFDFFF;
                              v351 = v82;
                              goto LABEL_171;
                            }
LABEL_250:
                            v351 = v82 | 0x10000000;
                            v357 = (*(__int64 (__fastcall **)(CDXGIBaseAdapter *))(*(_QWORD *)v9[566] + 64LL))(v9[566]);
                            v82 = v351;
                            goto LABEL_160;
                          }
                          if ( v83 == 2 )
                          {
                            if ( *((_BYTE *)v9 + 665) || *((char *)v9 + 288) < 0 )
                              goto LABEL_159;
                            v171 = (const struct _LUID *)(v9 + 317);
                            if ( !*((_BYTE *)v9 + 2530) )
                              v171 = 0;
                            v172 = v9[40];
                            v173 = *((unsigned int *)v172 + 187);
                            if ( (_DWORD)v173 == -1 )
                              v174 = (CDXGIBaseAdapter *)((char *)v172 + 752);
                            else
                              v174 = (const struct SAdapterDesc *)(*(_QWORD *)(*((_QWORD *)v172 + 21) + 280LL)
                                                                 + 536 * v173);
                            if ( MaximizedWindowedModeFullscreenEnabled(v174, v9[29], v171) || *((_BYTE *)v9 + 2114) )
                            {
LABEL_415:
                              v82 = v351;
                              goto LABEL_159;
                            }
                            v82 = v351;
                          }
                          v118 = v9[266];
                          if ( !v118 || !*((_DWORD *)v118 + 109) || *((_DWORD *)v118 + 108) != 3 )
                            goto LABEL_159;
                          if ( !CDXGISwapChain::IsMaximizedWindowedFullscreenEnabled((CDXGISwapChain *)v9) )
                          {
                            v82 = v351;
                            goto LABEL_250;
                          }
                          goto LABEL_415;
                        }
                      }
                    }
                    else if ( *((_BYTE *)v9 + 896) )
                    {
                      v48 = v305;
                      v43 = CDXGISwapChain::PrepareWindowedBltPresent(
                              (CDXGISwapChain *)v9,
                              (__int64)v298,
                              (__int64)&v316);
                      goto LABEL_70;
                    }
                  }
                }
                v48 = v305;
                goto LABEL_70;
              }
              v26 = (unsigned __int64)v9[35];
              if ( *((_DWORD *)v9 + 82) == 2
                && (*((_BYTE *)v9 + 665)
                 || *((char *)v9 + 288) < 0
                 || (!*((_BYTE *)v9 + 2530) ? (v63 = 0) : (v63 = (const struct _LUID *)(v9 + 317)),
                     (v64 = v9[40], v65 = *((unsigned int *)v64 + 187), (_DWORD)v65 == -1)
                   ? (v66 = (CDXGIBaseAdapter *)((char *)v64 + 752))
                   : (v66 = (const struct SAdapterDesc *)(*(_QWORD *)(*((_QWORD *)v64 + 21) + 280LL) + 536 * v65)),
                     MaximizedWindowedModeFullscreenEnabled(v66, v9[29], v63) || *((_BYTE *)v9 + 2114))) )
              {
                v23 = v9 + 97;
              }
              else if ( v26 < 0x2000100000000LL )
              {
                goto LABEL_24;
              }
              if ( *v23 && *((_QWORD *)v9[266] + 64) )
              {
                IsMaximizedWindowedFullscreenEnabled = CDXGISwapChain::IsMaximizedWindowedFullscreenEnabled((CDXGISwapChain *)v9);
                v306[1] = 0;
                v162 = v9[29];
                CurrentProcess = GetCurrentProcess();
                v164 = CDXGIFactory::ApplicationPresentationModeImpl(
                         v162,
                         (HWND)v9[42],
                         CurrentProcess,
                         (enum DXGI_APPLICATION_PRESENT_MODE *)&v306[1],
                         &GUID_NULL,
                         0);
                if ( v164 < 0 )
                {
                  CModule::RecordJournalImpl(
                    (CModule *)v20,
                    v164,
                    "Failed to determine if ownership is still taken",
                    top);
                  goto LABEL_534;
                }
                if ( v306[1] != IsMaximizedWindowedFullscreenEnabled + 1 )
                {
                  if ( !IsMaximizedWindowedFullscreenEnabled )
                  {
                    CModule::RecordJournalImpl(
                      (CModule *)v20,
                      0x87A0001u,
                      "Leaving fullscreen due to loss of ownership.",
                      top);
                    v27 = v308;
                    v308[1] = 1;
                    goto LABEL_468;
                  }
                  CDXGIOutput::ReleaseOwnershipImpl(v9[266], 0);
                  v210 = v9[266];
                  IsFullscreenDDAAllowed = CDXGISwapChain::IsFullscreenDDAAllowed((CDXGISwapChain *)v9);
                  v212 = CDXGISwapChain::ChildDeviceInternal((CDXGISwapChain *)v9, v9[266]);
                  v213 = CDXGIOutput::TakeOwnershipImpl(v210, v212, v9, 3, IsFullscreenDDAAllowed);
                  if ( v213 )
                  {
                    if ( v213 < 0 )
                      CModule::RecordJournalImpl((CModule *)v20, v213, "Failed to reacquire emulated ownership", top);
                    v27 = v308;
                    v308[1] = 1;
                    v8 = (_DWORD *)v321;
LABEL_468:
                    if ( v27[1] && !CDXGISwapChain::IsWindowedInternal((CDXGISwapChain *)v9) )
                      goto LABEL_82;
LABEL_25:
                    if ( *(_DWORD *)v298 )
                      goto LABEL_36;
                    goto LABEL_26;
                  }
                  v8 = (_DWORD *)v321;
LABEL_534:
                  v27 = v308;
                  goto LABEL_468;
                }
                v165 = v9[266];
                v166 = *((_QWORD *)v165 + 21);
                if ( *(_QWORD *)(v166 + 352) )
                {
                  if ( !*((_BYTE *)v165 + 264) )
                  {
                    v20 = *((unsigned int *)v165 + 64);
                    if ( (_DWORD)v20 != -1 )
                    {
                      LODWORD(v299) = 0;
                      HIDWORD(v299) = v20;
                      v167 = *((_DWORD *)v165 + 109);
                      if ( !v167 )
                        v167 = *(_DWORD *)(v166 + 220);
                      LODWORD(v299) = v167;
                      v168 = (*(__int64 (__fastcall **)(struct IDXGIResource **))(v166 + 352))(&v299);
                      v169 = dxgi_check<DXGIContract<Valid<0>,Valid<3221225485>,Valid<3221226166>,Valid<3223191558>,Valid<3223191557>,Valid<2149449728>,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp,NoOp>>(v168);
                      switch ( v169 )
                      {
                        case -2145517568:
                          if ( CDXGISwapChain::IsMaximizedWindowedFullscreenEnabled((CDXGISwapChain *)v9) )
                            goto LABEL_534;
                          v201 = CDXGIOutput::WaitForLinkConfigDone(v9[266]);
                          goto LABEL_465;
                        case -1071775738:
                          v22 = 142213121;
                          break;
                        case -1071775739:
                          v22 = 142213127;
                          break;
                        case -1073741130:
                          v22 = -2005270523;
                          break;
                        default:
                          v201 = NTStatusToHResult(v169);
LABEL_465:
                          v22 = v201;
                          break;
                      }
                    }
                  }
                }
                else
                {
                  v22 = 0;
                }
                if ( v22 )
                {
                  CModule::RecordJournalImpl((CModule *)v20, v22, "Leaving fullscreen due to monitor power state.", top);
                  v27 = v308;
                  v308[1] = 1;
                  goto LABEL_468;
                }
                goto LABEL_534;
              }
            }
LABEL_24:
            v27 = v308;
            goto LABEL_25;
          }
LABEL_58:
          v23 = v9 + 97;
          goto LABEL_19;
        }
LABEL_378:
        v158 = CDXGIOutput::CheckExclusiveOwnership(v9[266]);
        goto LABEL_379;
      }
LABEL_418:
      v158 = 142213121;
      goto LABEL_379;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180008d40  mov     rax, rsp
0x180008d43  push    rbp
0x180008d44  push    rbx
0x180008d45  push    rsi
0x180008d46  push    rdi
0x180008d47  push    r12
0x180008d49  push    r13
0x180008d4b  push    r14
0x180008d4d  push    r15
0x180008d4f  lea     rbp, [rax-8C8h]
0x180008d56  sub     rsp, 988h
0x180008d5d  movaps  xmmword ptr [rax-58h], xmm6
0x180008d61  movaps  xmmword ptr [rax-68h], xmm7
0x180008d65  mov     rax, cs:__security_cookie
0x180008d6c  xor     rax, rsp
0x180008d6f  mov     [rbp+8C0h+var_70], rax
0x180008d76  mov     r15, r9
0x180008d79  mov     [rbp+8C0h+lprc], r9
0x180008d7d  mov     edi, r8d
0x180008d80  mov     [rbp+8C0h+var_920], r8d
0x180008d84  mov     rsi, rdx
0x180008d87  mov     [rbp+8C0h+var_8B0], rdx
0x180008d8b  mov     r13, rcx
0x180008d8e  mov     [rbp+8C0h+var_8C0], rcx
0x180008d92  mov     r14, [rbp+8C0h+arg_28]
0x180008d99  mov     [rbp+8C0h+var_8F8], r14
0x180008d9d  mov     rax, [rbp+8C0h+arg_38]
0x180008da4  mov     [rbp+8C0h+var_918], rax
0x180008da8  mov     r12, [rbp+8C0h+arg_30]
0x180008daf  mov     [rbp+8C0h+var_8B8], r12
0x180008db3  mov     [rbp+8C0h+var_93C], 0
0x180008dba  cmp     byte ptr [rcx+29Ah], 0
0x180008dc1  jnz     loc_18000AFF2
0x180008dc7  mov     eax, [rsi+8]
0x180008dca  mov     [rbp+8C0h+var_910], eax
0x180008dcd  mov     ebx, [rsi+4]
0x180008dd0  mov     [rbp+8C0h+var_930], ebx
0x180008dd3  mov     dword ptr [rsp+9C0h+var_950], 0
0x180008ddb  mov     rcx, [r13+108h]
0x180008de2  mov     rax, [rcx]
0x180008de5  lea     rdx, [rbp+8C0h+var_8E0]
0x180008de9  mov     rax, [rax+68h]
0x180008ded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008df2  mov     [rbp+8C0h+var_92C], 0
0x180008df6  lea     rax, [rbp+8C0h+var_92C]
0x180008dfa  mov     [rsp+9C0h+var_980], rax; __int64
0x180008dff  mov     [rsp+9C0h+var_988], r12; __int64
0x180008e04  lea     rax, [rbp+8C0h+var_8E0]
0x180008e08  mov     qword ptr [rsp+9C0h+var_990], rax; __int64
0x180008e0d  mov     [rsp+9C0h+var_998], r14; __int64
0x180008e12  mov     eax, [rbp+8C0h+arg_20]
0x180008e18  mov     dword ptr [rsp+9C0h+var_9A0], eax; int
0x180008e1c  mov     r9, r15
0x180008e1f  mov     r8d, edi
0x180008e22  mov     rdx, rsi
0x180008e25  mov     rcx, r13; this
0x180008e28  call    ?ValidatePresent@CDXGISwapChain@@QEAAJPEBU?$SPresentArgsCore@UCDXGISwapChainWrapper@@@@IPEBUtagRECT@@IPEBUDXGI_SCROLL_RECT@@AEBUDXGI_INTERNAL_CONTENT_PROTECTION@@PEAUIDXGIResource@@AEA_N@Z; CDXGISwapChain::ValidatePresent(SPresentArgsCore<CDXGISwapChainWrapper> const *,uint,tagRECT const *,uint,DXGI_SCROLL_RECT const *,DXGI_INTERNAL_CONTENT_PROTECTION const &,IDXGIResource *,bool &)
0x180008e2d  mov     dword ptr [rsp+9C0h+var_950], eax
0x180008e31  test    eax, eax
0x180008e33  jz      short loc_180008E49
0x180008e35  lea     r8, aNonZeroReturnV; "Non-zero return value"
0x180008e3c  mov     edx, eax; unsigned int
0x180008e3e  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x180008e43  mov     eax, dword ptr [rsp+9C0h+var_950]
0x180008e47  test    eax, eax
0x180008e49  js      loc_1800094F4
0x180008e4f  mov     r14d, ebx
0x180008e52  and     r14d, 1
0x180008e56  jz      loc_180009686
0x180008e5c  xor     edi, edi
0x180008e5e  mov     ebx, edi
0x180008e60  mov     [rbp+8C0h+var_933], bl
0x180008e63  cmp     [rbp+8C0h+var_92C], dil
0x180008e67  jz      short loc_180008E70
0x180008e69  mov     [rbp+8C0h+var_920], edi
0x180008e6c  mov     [rbp+8C0h+lprc], rdi
0x180008e70  mov     rcx, [r13+0E8h]
0x180008e77  lea     rdx, [rcx+108h]
0x180008e7e  test    rcx, rcx
0x180008e81  cmovz   rdx, rdi
0x180008e85  mov     [rbp+8C0h+var_858], rdx
0x180008e89  mov     [rbp+8C0h+var_810], rdx
0x180008e90  mov     rax, [rdx]
0x180008e93  mov     rcx, rdx
0x180008e96  mov     rax, [rax]
0x180008e99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e9e  mov     [rbp+8C0h+var_808], 1
0x180008ea5  mov     dword ptr [r13+62Ch], 1
0x180008eb0  xorps   xmm0, xmm0
0x180008eb3  movdqu  [rbp+8C0h+var_1B8], xmm0
0x180008ebb  xorps   xmm1, xmm1
0x180008ebe  movdqu  [rbp+8C0h+var_1A8], xmm1
0x180008ec6  movdqu  [rbp+8C0h+var_198], xmm0
0x180008ece  mov     eax, [r13+0F8h]
0x180008ed5  mov     [rbp+8C0h+var_1C0], eax
0x180008edb  mov     [rbp+8C0h+var_1BC], 3
0x180008ee5  mov     rax, [r13+140h]
0x180008eec  lea     rcx, [rbp+8C0h+var_1C0]
0x180008ef3  mov     rax, [rax+130h]
0x180008efa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008eff  test    eax, eax
0x180008f01  jns     loc_18000B22D
0x180008f07  lea     r8, aOsthunkddigetd; "OsThunkDDIGetDeviceState"
0x180008f0e  mov     edx, eax; unsigned int
0x180008f10  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x180008f15  mov     r12d, 887A0022h
0x180008f1b  test    r14d, r14d
0x180008f1e  jnz     loc_180009D7D
0x180008f24  cmp     dword ptr [rsp+9C0h+var_950], 0
0x180008f29  jnz     loc_180009241
0x180008f2f  lea     rdi, [r13+308h]
0x180008f36  mov     rcx, [rdi]; HWND
0x180008f39  test    rcx, rcx
0x180008f3c  jnz     loc_180009DA7
0x180008f42  mov     rcx, [r13+150h]; HWND
0x180008f49  test    rcx, rcx
0x180008f4c  jnz     loc_180009631
0x180008f52  mov     ecx, [r13+11D0h]
0x180008f59  test    ecx, ecx
0x180008f5b  jz      short loc_180008F74
0x180008f5d  sub     ecx, 1
0x180008f60  jz      short loc_180008F74
0x180008f62  sub     ecx, 2; this
0x180008f65  jz      loc_18000B870
0x180008f6b  cmp     ecx, 1
0x180008f6e  jz      loc_18000B870
0x180008f74  cmp     dword ptr [rsp+9C0h+var_950], 0
0x180008f79  jnz     short loc_180008FB2
0x180008f7b  test    r14d, r14d
0x180008f7e  jnz     loc_180009D9E
0x180008f84  mov     r15, [r13+118h]
0x180008f8b  cmp     dword ptr [r13+148h], 2
0x180008f93  jz      loc_180009543
0x180008f99  mov     rax, 2000100000000h
0x180008fa3  cmp     r15, rax
0x180008fa6  jb      short loc_180008FB2
0x180008fa8  cmp     qword ptr [rdi], 0
0x180008fac  jnz     loc_18000A821
0x180008fb2  mov     r15, [rbp+8C0h+var_918]
0x180008fb6  cmp     dword ptr [rsp+9C0h+var_950], 0
0x180008fbb  jnz     short loc_180009034
0x180008fbd  mov     ecx, [r13+148h]
0x180008fc4  lea     eax, [rcx-2]
0x180008fc7  test    eax, 0FFFFFFFDh
0x180008fcc  jnz     short loc_180009034
0x180008fce  cmp     dword ptr [r13+1BCh], 0
0x180008fd6  jz      loc_18000A5A4
0x180008fdc  mov     ecx, [r13+11D0h]
0x180008fe3  test    ecx, ecx
0x180008fe5  jz      short loc_180008FF6
0x180008fe7  sub     ecx, 1
0x180008fea  jz      short loc_180008FF6
0x180008fec  sub     ecx, 2
0x180008fef  jz      short loc_180009034
0x180008ff1  cmp     ecx, 1
0x180008ff4  jz      short loc_180009034
0x180008ff6  test    byte ptr [rbp+8C0h+var_8E0], 1
0x180008ffa  jnz     loc_18000B1A7
0x180009000  test    byte ptr [r13+1B4h], 20h
0x180009008  jnz     loc_18000B1A7
0x18000900e  xor     r12d, r12d
0x180009011  mov     [rbp+8C0h+pdwAffinity], r12d
0x180009015  lea     rdi, [r13+388h]
0x18000901c  mov     rcx, [rdi]; hWnd
0x18000901f  test    rcx, rcx
0x180009022  jnz     loc_18000B37C
0x180009028  mov     rcx, [rdi]; this
0x18000902b  test    rcx, rcx
0x18000902e  jnz     loc_18000B39D
0x180009034  test    r14d, r14d
0x180009037  jnz     loc_18000972A
0x18000903d  mov     eax, dword ptr [rsp+9C0h+var_950]
0x180009041  sub     eax, 87A0001h
0x180009046  jz      loc_18000AFBC
0x18000904c  cmp     eax, 1
0x18000904f  jz      loc_18000AFBC
0x180009055  mov     eax, [rsi+4]
0x180009058  test    al, 8
0x18000905a  jnz     loc_18000AC2B
0x180009060  test    ebx, ebx
0x180009062  jnz     loc_18000924D
0x180009068  xor     r12b, r12b
0x18000906b  mov     eax, dword ptr [rsp+9C0h+var_950]
0x18000906f  cmp     eax, 87A0002h
0x180009074  jz      short loc_18000907E
0x180009076  test    eax, eax
0x180009078  jnz     loc_18000928F
0x18000907e  cmp     byte ptr [r13+837h], 0
0x180009086  jz      loc_180009157
0x18000908c  mov     byte ptr [r13+837h], 0
0x180009094  mov     r8d, [r13+1B4h]
0x18000909b  mov     r9d, [r13+19Ch]
0x1800090a2  mov     r10d, [r13+198h]
0x1800090a9  mov     r11d, [r13+190h]
0x1800090b0  mov     edi, [r13+18Ch]
0x1800090b7  movsxd  rcx, dword ptr [r13+188h]; enum DXGI_FORMAT
0x1800090be  cmp     rcx, 74h ; 't'
0x1800090c2  jnb     loc_180009283
0x1800090c8  lea     rax, [rcx+rcx*4]
0x1800090cc  lea     rdx, ?s_FormatDetail@CD3D11FormatHelper@@0QBUFORMAT_DETAIL@1@B; bool
0x1800090d3  cmp     dword ptr [rdx+rax*8], 0FFFFFFFFh
0x1800090d7  jz      loc_180009283
0x1800090dd  call    ?GetName@CD3D11FormatHelper@@SAPEBDW4DXGI_FORMAT@@_N@Z; CD3D11FormatHelper::GetName(DXGI_FORMAT,bool)
0x1800090e2  mov     [rsp+60h], r8d
0x1800090e7  mov     [rsp+9C0h+var_968], r9d
0x1800090ec  mov     [rsp+9C0h+var_970], r10d
0x1800090f1  mov     [rsp+9C0h+var_978], r11d
0x1800090f6  mov     dword ptr [rsp+9C0h+var_980], edi
0x1800090fa  mov     [rsp+9C0h+var_988], rax
0x1800090ff  mov     eax, [r13+184h]
0x180009106  mov     [rsp+9C0h+var_990], eax
0x18000910a  mov     eax, [r13+180h]
0x180009111  mov     dword ptr [rsp+9C0h+var_998], eax
0x180009115  mov     eax, [r13+17Ch]
0x18000911c  mov     dword ptr [rsp+9C0h+var_9A0], eax
0x180009120  mov     r9d, [r13+178h]
0x180009127  lea     r8, aDxgiSwapChainD; "DXGI_SWAP_CHAIN_DESC::BufferDesc = { %d"...
0x18000912e  mov     edx, 100h; unsigned __int64
0x180009133  lea     rcx, [rbp+8C0h+var_180]; char *
0x18000913a  call    ?StringCbPrintfA@@YAJPEAD_KPEBDZZ; StringCbPrintfA(char *,unsigned __int64,char const *,...)
0x18000913f  lea     r8, [rbp+8C0h+var_180]
0x180009146  mov     edx, 62h ; 'b'; enum DXGI_Message_Id
0x18000914b  mov     rcx, [r13+130h]; struct IDXGIDebugProducer *
0x180009152  call    ?DXGI_SDK_MSG_SWAPCHAIN@@YAXPEAUIDXGIDebugProducer@@W4DXGI_Message_Id@@ZZ; DXGI_SDK_MSG_SWAPCHAIN(IDXGIDebugProducer *,DXGI_Message_Id,...)
0x180009157  mov     rcx, r13; this
0x18000915a  call    ?IncrementPresentCount@CDXGISwapChain@@QEAAXXZ; CDXGISwapChain::IncrementPresentCount(void)
0x18000915f  mov     ecx, [r13+3A8h]
0x180009166  lea     eax, [rcx+1]
0x180009169  cmp     ecx, eax
0x18000916b  cmovnb  eax, ecx
0x18000916e  mov     [r13+3A8h], eax
0x180009175  xorps   xmm0, xmm0
0x180009178  movdqu  xmmword ptr [rbp+8C0h+pwi.rcWindow.left], xmm0
0x180009180  xorps   xmm1, xmm1
0x180009183  movdqu  xmmword ptr [rbp+8C0h+pwi.rcClient.left], xmm1
0x18000918b  movdqu  xmmword ptr [rbp+8C0h+pwi.dwStyle], xmm0
0x180009193  xor     r14d, r14d
0x180009196  mov     qword ptr [rbp+8C0h+pwi.cyWindowBorders], r14
0x18000919d  mov     [rbp+8C0h+pwi.cbSize], 3Ch ; '<'
0x1800091a7  cmp     [r13+150h], r14
0x1800091ae  jnz     loc_180009603
0x1800091b4  xorps   xmm0, xmm0
0x1800091b7  movups  xmmword ptr [rbp+8C0h+var_220.left], xmm0
0x1800091be  mov     edi, r14d
0x1800091c1  mov     [rbp+8C0h+var_8D8], r14
0x1800091c5  xor     r15b, r15b
0x1800091c8  cmp     [r13+1BCh], r14d
0x1800091cf  jz      loc_1800092B9
0x1800091d5  mov     ecx, [r13+11D0h]
0x1800091dc  test    ecx, ecx
0x1800091de  jz      short loc_1800091F7
0x1800091e0  sub     ecx, 1
0x1800091e3  jz      short loc_1800091F7
0x1800091e5  sub     ecx, 2
0x1800091e8  jz      loc_18000B8CC
0x1800091ee  cmp     ecx, 1
0x1800091f1  jz      loc_18000B8CC
0x1800091f7  cmp     [r13+380h], dil
0x1800091fe  jz      loc_1800092C7
0x180009204  mov     r14d, [rbp+8C0h+var_930]
0x180009208  mov     r8d, r14d
0x18000920b  shr     r8d, 1
0x18000920e  and     r8b, 1
0x180009212  mov     edx, r14d
0x180009215  shr     edx, 6
0x180009218  and     dl, 1
0x18000921b  lea     rax, [rbp+8C0h+var_8D8]
0x18000921f  mov     [rsp+9C0h+var_998], rax; __int64
0x180009224  lea     rax, [rsp+9C0h+var_950]
0x180009229  mov     [rsp+9C0h+var_9A0], rax; __int64
0x18000922e  mov     r9d, [rbp+8C0h+var_910]
0x180009232  mov     rcx, r13; this
0x180009235  call    ?PrepareWindowedBltPresent@CDXGISwapChain@@QEAA?AW4PresentPath@1@_N0IAEAV?$DXGITrack@J@@AEA_K@Z; CDXGISwapChain::PrepareWindowedBltPresent(bool,bool,uint,DXGITrack<long> &,unsigned __int64 &)
0x18000923a  mov     edi, eax
0x18000923c  jmp     loc_1800092CB
0x180009241  lea     rdi, [r13+308h]
0x180009248  jmp     loc_180008F74
0x18000924d  lea     eax, [rbx-87A0001h]
0x180009253  test    eax, 0FFFFFFFBh
0x180009258  jnz     loc_18000AE8C
0x18000925e  mov     rcx, r13
0x180009261  call    ??$IsFlipModel@$0A@@CDXGISwapChain@@QEBA_NXZ; CDXGISwapChain::IsFlipModel<0>(void)
0x180009266  test    al, al
0x180009268  jz      loc_180009068
0x18000926e  call    ?IsWindowedInternal@CDXGISwapChain@@QEBA_NXZ; CDXGISwapChain::IsWindowedInternal(void)
0x180009273  test    al, al
0x180009275  jz      loc_180009068
0x18000927b  mov     r12b, 1
0x18000927e  jmp     loc_18000906B
0x180009283  lea     rax, aUnrecognized; "Unrecognized"
0x18000928a  jmp     loc_1800090E2
0x18000928f  test    r12b, r12b
0x180009292  jz      short loc_18000929F
0x180009294  cmp     eax, 887A000Ah
0x180009299  jnz     loc_18000907E
0x18000929f  mov     rcx, [r13+108h]
0x1800092a6  mov     rax, [rcx]
0x1800092a9  xor     edx, edx
0x1800092ab  mov     rax, [rax+70h]
0x1800092af  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
