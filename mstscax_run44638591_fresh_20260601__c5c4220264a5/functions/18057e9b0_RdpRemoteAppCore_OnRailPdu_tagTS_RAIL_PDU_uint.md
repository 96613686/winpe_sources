# RdpRemoteAppCore::OnRailPdu(tagTS_RAIL_PDU *,uint)

- ea: `0x18057e9b0`
- end: `0x18058536b`
- name: `?OnRailPdu@RdpRemoteAppCore@@UEAAJPEAUtagTS_RAIL_PDU@@I@Z`
- size: `27067`
- prototype: `int(RdpRemoteAppCore *__hidden this, struct tagTS_RAIL_PDU *, unsigned int)`
- caller_count: `0`
- callee_count: `52`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180017fb8`
- `0x1800186a0`
- `0x18001f5d0`
- `0x18002a334`
- `0x18002a374`
- `0x180039c98`
- `0x18005e07c`
- `0x1800806f0`
- `0x18008fe60`
- `0x1800a64c0`
- `0x1800c8d94`
- `0x1800c90ac`
- `0x1800da7d0`
- `0x1800dafe4`
- `0x1800e9b1c`
- `0x1800f72f4`
- `0x1800f7748`
- `0x180102570`
- `0x180102700`
- `0x1801031a4`
- `0x18012962c`
- `0x18012966c`
- `0x18012dd50`
- `0x18014c050`
- `0x1801a00b8`
- `0x1801a0164`
- `0x1801a04d4`
- `0x1801bc9c8`
- `0x180263a40`
- `0x1802d64bc`
- `0x1804f0fe8`
- `0x18052b0e8`
- `0x18057c6b0`
- `0x18057cd10`
- `0x18057cf00`
- `0x18057d5e0`
- `0x18057d640`
- `0x18057d6f0`
- `0x18057d9d0`
- `0x18057e304`
- `0x18057e4bc`
- `0x18057e9b0`
- `0x180585380`
- `0x180589558`
- `0x18058b8d0`
- `0x18058bf24`
- `0x18058c034`
- `0x18058c1a4`
- `0x18058cbbc`
- `0x180688f3e`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180581d61`
- `msvcrt!memcpy_s` at `0x1805824c7`
- `msvcrt!memcpy_s` at `0x180581d61`
- `msvcrt!memcpy_s` at `0x1805824c7`

## string_xrefs

- `0x1805820fe`: `CreateWindowCallbacks failed`
- `0x1805821a8`: `RdpXBaseCoreApiAdaptor RdpX_CreateObject failed`
- `0x18057eb09`: `m_spRemoteAppPlugin`
- `0x18057f0dc`: `Invalid size for TS_RAIL_ORDER_LOCALMOVESIZE [%d]`
- `0x18057eab9`: `m_remoteAppPlugin.get()`
- `0x180580896`: `GetAppIdRespExRailOrderReceived: WindowId=0x%x, CensoredAppId=%s, ProcessId=%u, CensoredProcessImageName=%s`
- `0x18057fc80`: `Invalid size for TS_RAIL_ORDER_TASKBARINFO [%d]`
- `0x18057fca3`: `TaskbarInfoRailOrderReceived: Message=0x%x, WindowIdTab=0x%x, Body=0x%x`
- `0x18057ff0b`: `GetWndPlugin failed`
- `0x180580c63`: `GetWndPlugin failed`
- `0x180580f49`: `GetWndPlugin failed`
- `0x180581384`: `GetWndPlugin failed`
- `0x180582026`: `GetWndPlugin failed`
- `0x180582c3a`: `GetWndPlugin failed`
- `0x18058322e`: `GetWndPlugin failed`
- `0x1805833d8`: `GetWndPlugin failed`
- `0x1805836b4`: `GetWndPlugin failed`
- `0x180583bf5`: `GetWndPlugin failed`
- `0x1805846b2`: `GetWndPlugin failed`
- `0x18057f117`: `LocalMoveSizeRailOrderReceived: WindowId=0x%x, IsStart=%hu, Type=0x%hx, X=%hi, Y=%hi`
- `0x18057f2c7`: `Failed to create RemoteAppMoveSizeInfo`
- `0x18057f4fe`: `UpdateAppID failed`
- `0x1805809e7`: `UpdateAppID failed`
- `0x180581e64`: `Invalid size of TS_RAIL_ORDER_WINDOW_CREATE_BODY PDU`
- `0x180581f1f`: `Invalid size of TS_RAIL_ORDER_WINDOW_CREATE_BODY PDU`
- `0x1805800b9`: `CreateCachedIcon failed`
- `0x180580d0d`: `CreateCachedIcon failed`
- `0x180581157`: `CreateCachedIcon failed`
- `0x180584025`: `CreateCachedIcon failed`
- `0x180584bdb`: `CreateCachedIcon failed`
- `0x18058026c`: `Failed to UpdateOverlayIcon`
- `0x180580699`: `UpdateOverlayIcon failed`
- `0x18057fb42`: `Invalid size for TS_RAIL_ORDER_COMPARTMENTINFO [%d]`
- `0x18057fb65`: `CompartmentInfoRailOrderReceived: Open=%d, ConversionMode=0x%x, SentenceMode=0x%x, KanaOn=%d`
- `0x180581231`: `Invalid size of TS_RAIL_ORDER_WINDOW_DELETE_BODY PDU`
- `0x1805812b3`: `WindowDeleteRailOrderReceived: WindowId=0x%x`
- `0x18058149d`: `DeleteWindow failed`
- `0x180581057`: `WindowIconRailOrderReceived: WindowId=0x%x, NumIcons=%hhu, CacheEntry=0x%hx, CacheId=0x%hhx, IconFlags=0x%hhx, Width=%hu, Height=%hu, Bpp=%hhu, ColorTableBytes=%hu, BitsMaskBytes=%u, BitsColorBytes=%u`
- `0x180580d9c`: `UpdateIcon failed`
- `0x1805811e5`: `UpdateIcon failed`
- `0x180580ac3`: `Invalid size of TS_RAIL_ORDER_WINDOW_CACHED_ICON PDU`
- `0x180580b6f`: `WindowCachedIconRailOrderReceived: WindowId=0x%x, NumIcons=%hhu, CacheEntry=0x%hx, CacheId=0x%hhx, IconFlags=0x%hhx`
- `0x18058235e`: `CreateWindowRepresentation failed`
- `0x180582590`: `WindowCreateRailOrderReceived: WindowId=0x%x, FieldsValidFlags=0x%x, WindowOwnerId=0x%x, Style=0x%08x, StyleEx=0x%08x, ShowState=%hhu, EnforceServerZOrder=%hhu, TitleBytes=%hu, Title=%s, OffsetX=%i, OffsetY=%i, Width=%i, Height=%i, WindowClientDeltaX=%i, WindowClientDeltaY=%i, ResizeMarginLeft=%i, ResizeMarginTop=%i, ResizeMarginRight=%i, ResizeMarginBottom=%i, NumVisibilityRects=%hu`
- `0x1805827c2`: `WindowCreateRailOrderReceived_VisibilityRect[%i]: WindowId=0x%x, Left=%i, Top=%i, Right=%i, Bottom=%i`
- `0x180581dc4`: `WindowChangeRailOrderReceived: WindowsId=0x%x, FieldsValidFlags=0x%x, WindowOwnerId=0x%x, Style=0x%08x, StyleEx=0x%08x, ShowState=%hhu, EnforceServerZOrder=%hhu, TitleBytes=%hu, Title=%s`
- `0x180584e65`: `NotifyIconCreateRailOrderReceived_NonCached: WindowId=0x%x, NotifyIconId=0x%x, NumIcons=%hhu, IsCachedIcon=%hhu, StateFlags=0x%x, PDUFlags=0x%x, ToolTipBytes=%hu, ToolTip=%s, CacheEntry=0x%hx, CacheId=0x%hhx, IconFlags=0x%hhx, Width=%hu, Height=%hu, Bpp=%hhu, ColorTableBytes=%hu, BitsMaskBytes=%u, BitsColorBytes=%u`
- `0x18058503b`: `NotifyIconCreateRailOrderReceived_NoIcons: WindowId=0x%x, NotifyIconId=0x%x, NumIcons=%hhu, IsCachedIcon=%hhu, StateFlags=0x%x, PDUFlags=0x%x, ToolTipBytes=%hu, ToolTip=%s`
- `0x180583f92`: `NotifyIconChangeRailOrderReceived_Cached: WindowId=0x%x, NotifyIconId=0x%x, NumIcons=%hhu, IsCachedIcon=%hhu, StateFlags=0x%x, PDUFlags=0x%x, ToolTipBytes=%hu, ToolTip=%s, CacheEntry=0x%hx, CacheId=0x%hhx, IconFlags=0x%hhx`
- `0x1805842a9`: `NotifyIconChangeRailOrderReceived_NonCached: WindowId=0x%x, NotifyIconId=0x%x, NumIcons=%hhu, IsCachedIcon=%hhu,StateFlags=0x%x, PDUFlags=0x%x, ToolTipBytes=%hu, ToolTip=%s, CacheEntry=0x%hx, CacheId=0x%hhx, IconFlags=0x%hhx, Width=%hu, Height=%hu, Bpp=%hhu, ColorTableBytes=%hu, BitsMaskBytes=%u, BitsColorBytes=%u`
- `0x180583e7e`: `Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Create PDU`
- `0x180584572`: `Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Create PDU`
- `0x18058460f`: `Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Create PDU`
- `0x180584a37`: `Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Create PDU`
- `0x180584c23`: `Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Create PDU`
- `0x180584cd3`: `Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Create PDU`
- `0x180584790`: `CreateShellNotifyInfo failed`
- `0x180583d31`: `CreateShellNotifyInfo->SetTip failed`
- `0x1805848f6`: `CreateShellNotifyInfo->SetTip failed`
- `0x1805837ea`: `RdpX_Strings_CreateConstXChar16StringWithSpecifiedSize failed`
- `0x180583894`: `RdpX_Strings_CreateConstXChar16StringWithSpecifiedSize failed`
- `0x180583dc1`: `RdpX_Strings_CreateConstXChar16StringWithSpecifiedSize failed`
- `0x18058497f`: `RdpX_Strings_CreateConstXChar16StringWithSpecifiedSize failed`
- `0x180583e34`: `CreateShellNotifyInfo->SetWSNState failed`
- `0x1805849eb`: `CreateShellNotifyInfo->SetWSNState failed`
- `0x180584b4f`: `NotifyIconCreateRailOrderReceived_Cached: WindowId=0x%x, NotifyIconId=0x%x, NumIcons=%hhu, IsCachedIcon=%hhu, StateFlags=0x%x, PDUFlags=0x%x, ToolTipBytes=%hu, ToolTip=%s, CacheEntry=0x%hx, CacheId=0x%hhx, IconFlags=0x%hhx`
- `0x180584483`: `NotifyIconChangeRailOrderReceived_NoIcons: WindowId=0x%x, NotifyIconId=0x%x, NumIcons=%hhu, IsCachedIcon=%hhu, StateFlags=0x%x, PDUFlags=0x%x, ToolTipBytes=%hu, ToolTip=%s`
- `0x1805832ee`: `Invalid size of TS_RAIL_ORDER_NOTIFYICON_DELETE PDU`
- `0x180583378`: `NotifyIconDeleteRailOrderReceived: WindowId=0x%x, NotifyIconId=0x%x`

## pseudocode

```c
__int64 __fastcall RdpRemoteAppCore::OnRailPdu(RdpRemoteAppCore *this, struct tagTS_RAIL_PDU *a2, __int64 a3)
{
  unsigned int v3; // ebx
  struct tagTS_RAIL_PDU *v4; // r13
  RdpRemoteAppCore *v5; // rdi
  int ActivityIdPrefix; // eax
  int v7; // edx
  const char *v8; // rcx
  int RemoteAppWindow; // esi
  const struct tagTS_RAIL_PDU *v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  unsigned int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // rdx
  HKEY v21; // rax
  unsigned int v22; // eax
  int v23; // ebx
  unsigned int v24; // eax
  int v25; // eax
  const wchar_t *v26; // rdx
  __int64 v27; // r8
  __int64 v28; // rcx
  HKEY v29; // rax
  int v30; // ebx
  unsigned int v31; // eax
  int v32; // ebx
  unsigned int v33; // eax
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // r8
  int v37; // eax
  struct RdpXInterfaceRemoteAppWindow *v38; // rcx
  struct RdpInterfaceDesktopRemoteAppWindow *v39; // rax
  __int64 v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // r8
  int v43; // r15d
  int v44; // eax
  int v45; // r9d
  int v46; // edx
  __int64 v47; // rcx
  __int64 v48; // rcx
  HKEY v49; // rax
  int v50; // ebx
  int v51; // edi
  int v52; // esi
  unsigned int v53; // eax
  int v54; // ebx
  unsigned int v55; // eax
  __int64 v56; // rdx
  __int64 v57; // rcx
  __int64 v58; // r8
  int v59; // eax
  __int64 *v60; // rcx
  __int64 v61; // rax
  struct RdpInterfaceDesktopRemoteAppWindow *v62; // rax
  __int64 v63; // rdx
  __int64 v64; // rcx
  __int64 v65; // r8
  __int64 *v66; // r10
  int v67; // r15d
  int v68; // eax
  unsigned int v69; // eax
  __int64 v70; // rdx
  __int64 v71; // rcx
  __int64 v72; // r8
  int v73; // eax
  __int64 v74; // rcx
  int v75; // ecx
  __int64 v76; // r9
  unsigned int v77; // eax
  int v78; // ebx
  unsigned int v79; // eax
  int v80; // ebx
  unsigned int v81; // eax
  const unsigned __int16 *v82; // rax
  __int64 v83; // rdx
  __int64 v84; // rcx
  __int64 v85; // r8
  int v86; // eax
  __int64 v87; // rdx
  __int64 v88; // rdx
  __int64 v89; // rdx
  __int64 v90; // rdx
  __int64 v91; // rdx
  __int64 v92; // rcx
  __int64 v93; // r8
  unsigned int v94; // eax
  int v95; // ebx
  __int64 v96; // rax
  HKEY v97; // rax
  unsigned int v98; // eax
  int v99; // esi
  unsigned int v100; // eax
  __int64 v101; // r8
  const wchar_t *v102; // rdx
  __int64 v103; // rcx
  __int64 v104; // rdx
  __int64 v105; // rcx
  __int64 v106; // r8
  int v107; // ebx
  unsigned int v108; // eax
  struct RdpInterfaceDesktopRemoteAppWindow *DesktopRemoteAppWindow; // rax
  __int64 v110; // rcx
  HKEY v111; // rax
  unsigned int v112; // eax
  int v113; // ebx
  unsigned int v114; // eax
  unsigned int v115; // eax
  __int64 v116; // rdx
  int v117; // ebx
  __int64 v118; // r8
  int v119; // eax
  __int64 v120; // rdx
  int v121; // esi
  __int64 v122; // r8
  int v123; // eax
  unsigned int (*v124)(void); // rax
  HKEY v126; // rax
  unsigned int v127; // eax
  int v128; // ebx
  unsigned int v129; // eax
  int v130; // edx
  bool v131; // zf
  int v132; // r8d
  HKEY v133; // rax
  unsigned int v134; // eax
  int v135; // ebx
  unsigned int v136; // eax
  __int64 v137; // r8
  unsigned int v138; // r9d
  int v139; // ecx
  __int64 v140; // rcx
  __int64 v141; // rdx
  __int64 v142; // rcx
  __int64 v143; // r8
  int v144; // ebx
  unsigned int v145; // eax
  struct RdpXInterfaceRemoteAppWindow *v146; // rcx
  __int64 v147; // rdx
  __int64 v148; // rcx
  __int64 v149; // r8
  int v150; // ebx
  unsigned int v151; // eax
  RdpRemoteAppCore *v152; // rbx
  __int64 v153; // rdx
  __int64 v154; // rcx
  __int64 v155; // r8
  int v156; // eax
  int v157; // edx
  const char *v158; // rcx
  __int64 v159; // rcx
  struct ITSWndPluginEx *v160; // rcx
  __int64 v161; // rcx
  __int64 v162; // rdx
  __int64 v163; // rcx
  __int64 v164; // r8
  __int64 v165; // r9
  int v166; // ebx
  unsigned int v167; // eax
  unsigned int v168; // eax
  __int64 v169; // rdx
  __int64 v170; // rdx
  __int64 v171; // rcx
  __int64 v172; // r8
  __int64 v173; // rdx
  __int64 v174; // r8
  int v175; // eax
  __int64 v176; // rcx
  __int64 v177; // rdx
  __int64 v178; // rcx
  __int64 v179; // r8
  struct RdpInterfaceDesktopRemoteAppWindow *v180; // rax
  __int64 v181; // rdx
  int v182; // ebx
  __int64 v183; // r8
  int v184; // eax
  unsigned int v185; // eax
  __int64 v186; // rdx
  int v187; // ebx
  __int64 v188; // r8
  int v189; // eax
  __int64 v190; // rcx
  struct ITSWndPluginEx *v191; // rcx
  __int64 v192; // rcx
  __int64 v193; // rcx
  unsigned int v194; // eax
  __int64 v195; // rdx
  __int64 v196; // rcx
  __int64 v197; // r8
  int v198; // ebx
  unsigned int v199; // eax
  struct RdpInterfaceDesktopRemoteAppWindow *v200; // rax
  __int64 v201; // rcx
  unsigned int v202; // eax
  __int64 v203; // rdx
  int v204; // ebx
  __int64 v205; // r8
  int v206; // eax
  __int64 v207; // rdx
  __int64 v208; // rcx
  __int64 v209; // r8
  int v210; // ebx
  unsigned int v211; // eax
  struct RdpInterfaceDesktopRemoteAppWindow *v212; // rax
  unsigned int v213; // eax
  __int64 v214; // rdx
  int v215; // ebx
  __int64 v216; // r8
  int v217; // eax
  unsigned int v218; // eax
  __int64 v219; // rdx
  int v220; // ebx
  __int64 v221; // r8
  int v222; // eax
  __int64 v223; // rcx
  int v224; // ebx
  unsigned int v225; // eax
  int v226; // ebx
  int v227; // edi
  int v228; // eax
  const unsigned __int16 *FileNameW; // rax
  int v230; // ebx
  const unsigned __int16 *v231; // rdi
  const unsigned __int16 *v232; // rax
  RdpRemoteAppCore *v233; // rbx
  __int64 v234; // rdx
  __int64 v235; // rcx
  __int64 v236; // r8
  int v237; // ebx
  unsigned int v238; // eax
  __int64 v239; // rdx
  int updated; // edi
  __int64 v241; // r8
  int v242; // eax
  __int64 v243; // rdx
  __int64 v244; // rcx
  __int64 v245; // r8
  int v246; // eax
  __int64 v247; // rdx
  __int64 v248; // rcx
  __int64 v249; // r8
  unsigned int v250; // eax
  char *v251; // rcx
  struct RdpXInterfaceRemoteAppWindow **v252; // rax
  __int64 v253; // rdx
  __int64 v254; // rcx
  __int64 v255; // r8
  int v256; // ebx
  unsigned int v257; // eax
  struct ITSWndPluginEx **v258; // rax
  __int64 v259; // rdx
  __int64 v260; // rcx
  __int64 v261; // r8
  int v262; // eax
  int v263; // edx
  const char *v264; // rcx
  __int64 v265; // rdi
  __int64 (__fastcall *v266)(__int64, _QWORD, _QWORD, void *); // rbx
  void *v267; // rax
  __int64 v268; // rdx
  __int64 v269; // rcx
  __int64 v270; // r8
  __int64 v271; // rsi
  BOOL v272; // ebx
  __int64 (__fastcall *v273)(__int64, __int64, BOOL); // rdi
  __int64 v274; // rax
  __int64 v275; // rdx
  __int64 v276; // rcx
  __int64 v277; // r8
  __int64 v278; // rdx
  __int64 v279; // rcx
  __int64 v280; // r8
  unsigned int v281; // eax
  __int64 v282; // rdx
  struct RdpXInterfaceRemoteAppWindow **v283; // rax
  __int64 v284; // rdx
  __int64 v285; // rcx
  __int64 v286; // r8
  int v287; // ebx
  unsigned int v288; // eax
  struct ITSWndPluginEx **v289; // rax
  int WndPlugin; // eax
  __int64 v291; // rdx
  __int64 v292; // rcx
  __int64 v293; // r8
  int v294; // eax
  int v295; // edx
  const char *v296; // rcx
  unsigned __int16 v297; // r14
  int v298; // esi
  __int64 v299; // rcx
  unsigned int v300; // esi
  __int64 v301; // rdi
  __int64 v302; // rbx
  __int64 v303; // r14
  __int64 (__fastcall *v304)(__int64, _QWORD, _QWORD, __int64, _DWORD, _DWORD, char *, _DWORD, __int64, _DWORD, __int64, _DWORD, void *); // rsi
  void *v305; // rax
  __int64 v306; // r9
  __int64 v307; // rdx
  __int64 v308; // rcx
  __int64 v309; // r8
  __int64 v310; // rsi
  __int64 (__fastcall *v311)(__int64, __int64, _QWORD); // rdi
  unsigned int v312; // ebx
  __int64 v313; // rax
  __int64 v314; // rdx
  __int64 v315; // rcx
  __int64 v316; // r8
  __int64 v317; // rdx
  __int64 v318; // rcx
  __int64 v319; // r8
  unsigned int v320; // eax
  struct RdpXInterfaceRemoteAppWindow **v321; // rax
  __int64 v322; // rdx
  __int64 v323; // rcx
  __int64 v324; // r8
  int v325; // ebx
  unsigned int v326; // eax
  struct ITSWndPluginEx **v327; // rax
  __int64 v328; // rdx
  __int64 v329; // rcx
  __int64 v330; // r8
  int v331; // eax
  int v332; // edx
  const char *v333; // rcx
  __int64 v334; // rdi
  __int64 v335; // rax
  int v336; // ebx
  __int64 v337; // rax
  __int64 v338; // rdi
  __int64 (__fastcall *v339)(__int64, _QWORD); // rbx
  __int64 v340; // rax
  unsigned int v341; // eax
  unsigned int v342; // eax
  __int64 v343; // rdx
  __int64 v344; // rcx
  __int64 v345; // r8
  __int64 v346; // rdx
  __int64 v347; // r8
  __int64 v348; // rcx
  unsigned int v349; // eax
  __int64 v350; // rdx
  unsigned int v351; // r14d
  __int64 v352; // rdx
  __int64 v353; // rcx
  __int64 v354; // r8
  unsigned int v355; // eax
  struct RdpXInterfaceRemoteAppWindow **v356; // rax
  __int64 v357; // rdx
  __int64 v358; // rcx
  __int64 v359; // r8
  int v360; // ebx
  unsigned int v361; // eax
  __int64 v362; // rax
  int v363; // r14d
  int v364; // esi
  int v365; // edi
  int v366; // ebx
  __int64 *v367; // rax
  __int64 v368; // rcx
  __int64 v369; // rax
  __int64 v370; // rax
  __int64 v371; // rax
  __int64 v372; // rax
  __int64 v373; // rax
  __int64 v374; // rax
  __int64 v375; // rax
  __int64 v376; // rdx
  __int64 v377; // rcx
  char *v378; // rdi
  __int64 v379; // r8
  unsigned int v380; // eax
  int v381; // esi
  RdpRemoteAppCore *v382; // r14
  __int64 v383; // rdx
  __int64 v384; // rax
  __int64 v385; // rax
  __int64 v386; // rax
  __int64 v387; // rdx
  __int64 v388; // r8
  __int64 v389; // rcx
  unsigned int v390; // eax
  __int64 v391; // rdx
  unsigned int v392; // r14d
  unsigned int v393; // eax
  struct RdpXInterfaceRemoteAppWindow **v394; // rax
  __int64 v395; // rdx
  __int64 v396; // rcx
  __int64 v397; // r8
  int v398; // ebx
  unsigned int v399; // eax
  __int64 v400; // rax
  __int64 v401; // rax
  __int64 v402; // rax
  __int64 v403; // rax
  __int64 v404; // rax
  __int64 v405; // rdx
  __int64 v406; // r8
  __int64 v407; // rcx
  unsigned int v408; // eax
  __int64 v409; // rdx
  int v410; // eax
  unsigned int v411; // r15d
  unsigned int v412; // r14d
  unsigned int v413; // eax
  struct ITSWndPluginEx **v414; // rax
  int v415; // r14d
  __int64 v416; // rdx
  __int64 v417; // rcx
  __int64 v418; // r8
  int v419; // eax
  struct RdpXInterfaceRemoteAppWindow **v420; // rax
  void *v421; // rax
  unsigned int WindowCallbacks; // eax
  __int64 v423; // rdx
  __int64 v424; // rcx
  __int64 v425; // r8
  int v426; // eax
  int v427; // edx
  const char *v428; // rcx
  void *v429; // rax
  unsigned int Object; // eax
  __int64 v431; // rdx
  __int64 v432; // rcx
  __int64 v433; // r8
  __int64 v434; // rdi
  __int64 (__fastcall *v435)(__int64, void *); // rbx
  void *v436; // rax
  __int64 v437; // rdx
  __int64 v438; // rcx
  __int64 v439; // r8
  __int64 v440; // rdi
  __int64 (__fastcall *v441)(__int64, __int64); // rbx
  __int64 v442; // rax
  unsigned int v443; // eax
  __int64 v444; // rdx
  __int64 v445; // rcx
  __int64 v446; // r8
  __int64 v447; // r15
  __int64 (__fastcall *v448)(__int64, __int64, _QWORD, __int64, __int128 *, void *); // r14
  void *v449; // rbx
  __int64 v450; // rax
  unsigned int v451; // esi
  __int64 v452; // rdi
  __int64 v453; // rax
  unsigned int v454; // eax
  __int64 v455; // rdx
  __int64 v456; // rcx
  __int64 v457; // r8
  __int64 v458; // rdi
  __int64 (__fastcall *v459)(__int64, bool); // rbx
  __int64 v460; // rax
  int v461; // eax
  unsigned int v462; // eax
  __int64 v463; // rax
  __int64 v464; // rax
  __int64 v465; // rax
  __int64 v466; // rax
  __int64 v467; // rax
  __int64 v468; // rax
  int v469; // r15d
  int v470; // r14d
  int v471; // ebx
  __int64 *v472; // rax
  __int64 v473; // rcx
  __int64 v474; // rax
  __int64 v475; // rax
  __int64 v476; // rax
  __int64 v477; // rdx
  __int64 v478; // rcx
  char *v479; // rbx
  __int64 v480; // r8
  unsigned int v481; // eax
  __int64 v482; // rdx
  __int64 v483; // rax
  __int64 v484; // rax
  __int64 v485; // rax
  __int64 v486; // rdi
  void (__fastcall *v487)(__int64, _QWORD); // rbx
  __int64 v488; // rax
  unsigned int v489; // eax
  __int64 v490; // rax
  __int64 v491; // rdx
  __int64 v492; // rcx
  __int64 v493; // r8
  unsigned int v494; // eax
  struct RdpXInterfaceRemoteAppWindow **v495; // rax
  __int64 v496; // rdx
  __int64 v497; // rcx
  __int64 v498; // r8
  int v499; // ebx
  unsigned int v500; // eax
  int v501; // ebx
  unsigned int v502; // eax
  __int64 v503; // rax
  int v504; // ebx
  unsigned int v505; // eax
  __int64 v506; // rax
  __int64 v507; // rdx
  __int64 v508; // rdx
  __int64 v509; // rcx
  __int64 v510; // r8
  unsigned int v511; // eax
  char *v512; // rcx
  struct ITSWndPluginEx **v513; // rax
  __int64 v514; // rdx
  __int64 v515; // rcx
  __int64 v516; // r8
  int v517; // eax
  unsigned int v518; // eax
  __int64 v519; // rax
  __int64 v520; // rdx
  HKEY v521; // rax
  unsigned int v522; // eax
  unsigned int v523; // eax
  __int64 v524; // rax
  RdpRemoteAppCore *v525; // rbx
  __int64 v526; // rax
  unsigned int v527; // r15d
  __int64 v528; // rdi
  __int64 (__fastcall *v529)(__int64, _QWORD, void *); // rbx
  void *v530; // rax
  __int64 v531; // rdx
  __int64 v532; // rcx
  int v533; // ebx
  __int64 v534; // r8
  __int64 v535; // rax
  unsigned int v536; // eax
  __int64 v537; // rax
  unsigned int v538; // eax
  __int64 v539; // rax
  __int64 v540; // rdx
  __int64 v541; // rcx
  __int64 v542; // r8
  unsigned int v543; // eax
  __int64 v544; // rdx
  unsigned int v545; // eax
  unsigned int v546; // esi
  wchar_t *v547; // rcx
  size_t v548; // rdx
  unsigned int v549; // eax
  int v550; // esi
  unsigned int v551; // ebx
  __int64 v552; // r9
  const unsigned __int16 *v553; // r8
  __int64 v554; // rdx
  __int64 v555; // rcx
  __int64 v556; // r8
  int v557; // eax
  struct ITSWndPluginEx **v558; // rax
  __int64 v559; // rdx
  __int64 v560; // rcx
  __int64 v561; // r8
  int v562; // eax
  unsigned int v563; // ebx
  __int64 v564; // rax
  __int64 v565; // rdx
  __int64 v566; // rcx
  __int64 v567; // r8
  unsigned int v568; // eax
  char *v569; // rcx
  struct ITSWndPluginEx **v570; // rax
  __int64 v571; // rdx
  __int64 v572; // rcx
  __int64 v573; // r8
  int v574; // eax
  int v575; // edx
  const char *v576; // rcx
  __int64 v577; // rdi
  __int64 (__fastcall *v578)(__int64, _QWORD, _QWORD, void *); // rbx
  void *v579; // rax
  __int64 v580; // rdx
  __int64 v581; // rcx
  __int64 v582; // r8
  __int64 v583; // rax
  __int64 v584; // rax
  struct RdpXInterfaceShellNotifyInformation *v585; // rbx
  __int64 v586; // rax
  unsigned int v587; // eax
  __int64 v588; // rdx
  __int64 v589; // rcx
  __int64 v590; // r8
  __int64 v591; // rcx
  __int64 v592; // r8
  __int64 v593; // rdx
  unsigned int v594; // eax
  __int64 v595; // rdx
  __int64 v596; // rcx
  unsigned int v597; // esi
  struct ITSWndPluginEx **v598; // rax
  __int64 v599; // rdx
  __int64 v600; // rcx
  __int64 v601; // r8
  int v602; // eax
  int v603; // edx
  const char *v604; // rcx
  __int64 v605; // rdi
  __int64 (__fastcall *v606)(__int64, _QWORD, _QWORD, void *); // rbx
  void *v607; // rax
  __int64 v608; // rdx
  __int64 v609; // rcx
  __int64 v610; // r8
  __int64 v611; // rax
  __int64 v612; // rbx
  char *v613; // r14
  void *v614; // rax
  unsigned int ConstXChar16StringWithSpecifiedSize; // eax
  __int64 v616; // rdx
  __int64 v617; // rcx
  __int64 v618; // r8
  int v619; // eax
  char *v620; // r15
  void *v621; // rax
  unsigned int v622; // eax
  __int64 v623; // rdx
  __int64 v624; // rcx
  __int64 v625; // r8
  int v626; // eax
  int v627; // edx
  const char *v628; // rcx
  const wchar_t *v629; // rbx
  __int64 v630; // rax
  const wchar_t *v631; // rsi
  __int64 v632; // rax
  __int64 v633; // rax
  __int64 v634; // rdx
  __int64 v635; // rcx
  __int64 v636; // r8
  struct RdpXInterfaceShellNotifyInformation *v637; // rbx
  __int64 v638; // rax
  unsigned int v639; // eax
  __int64 v640; // rdx
  __int64 v641; // rcx
  __int64 v642; // r8
  __int64 v643; // rdx
  __int64 v644; // r8
  __int64 v645; // rcx
  unsigned int v646; // eax
  __int64 v647; // rdx
  unsigned int v648; // r14d
  struct ITSWndPluginEx **v649; // rax
  __int64 v650; // rdx
  __int64 v651; // rcx
  __int64 v652; // r8
  int v653; // eax
  int v654; // edx
  const char *v655; // rcx
  __int64 v656; // rdi
  __int64 (__fastcall *v657)(__int64, _QWORD, _QWORD, void *); // rbx
  void *v658; // rax
  int v659; // eax
  __int64 v660; // rdx
  __int64 v661; // rcx
  __int64 v662; // r8
  unsigned __int16 v663; // di
  __int64 v664; // rax
  __int64 v665; // rax
  __int64 v666; // rdx
  __int64 v667; // rcx
  __int64 v668; // r8
  int v669; // eax
  int v670; // edx
  const char *v671; // rcx
  void *v672; // rax
  unsigned int v673; // eax
  __int64 v674; // rdx
  __int64 v675; // rcx
  __int64 v676; // r8
  __int64 v677; // rax
  __int64 v678; // rdx
  __int64 v679; // rcx
  __int64 v680; // r8
  __int64 v681; // rdx
  __int64 v682; // rcx
  __int64 v683; // r8
  __int64 v684; // rsi
  unsigned int v685; // eax
  unsigned int v686; // ebx
  RdpRemoteAppCore *v687; // r14
  unsigned int v688; // eax
  __int64 v689; // rdx
  int v690; // r15d
  __int64 v691; // rax
  const wchar_t *v692; // rbx
  __int64 v693; // rdi
  __int64 (__fastcall *v694)(__int64, _QWORD, _QWORD, void *); // rbx
  void *v695; // rax
  __int64 v696; // rdx
  __int64 v697; // rcx
  __int64 v698; // r8
  int v699; // eax
  int v700; // edx
  const char *v701; // rcx
  unsigned int v702; // ebx
  __int64 v703; // rdx
  __int64 v704; // r8
  __int64 v705; // rcx
  int v706; // eax
  unsigned int v707; // ebx
  __int64 v708; // rax
  const wchar_t *v709; // rbx
  __int64 v710; // rdi
  __int64 (__fastcall *v711)(__int64, _QWORD, _QWORD, char *, _DWORD, _DWORD, char *, int, RdpRemoteAppCore *, _DWORD, char *, _DWORD, void *); // rbx
  void *v712; // rax
  char *v713; // r9
  __int64 v714; // rdx
  __int64 v715; // rcx
  __int64 v716; // r8
  __int64 v717; // rdi
  __int64 (__fastcall *v718)(__int64, __int64); // rbx
  __int64 v719; // rax
  __int64 v720; // rdx
  __int64 v721; // rcx
  __int64 v722; // r8
  __int64 v723; // rax
  const wchar_t *v724; // rbx
  __int64 v725; // rax
  struct RdpXInterfaceShellNotifyInformation *v726; // rbx
  __int64 v727; // rax
  unsigned int v728; // eax
  __int64 v729; // rdx
  __int64 v730; // rcx
  __int64 v731; // r8
  __int64 v732; // rdx
  __int64 v733; // r8
  __int64 v734; // rcx
  unsigned int v735; // eax
  __int64 v736; // rdx
  unsigned int v737; // r15d
  struct ITSWndPluginEx **v738; // rax
  __int64 v739; // rdx
  __int64 v740; // rcx
  __int64 v741; // r8
  int v742; // eax
  int v743; // edx
  const char *v744; // rcx
  __int64 v745; // rdi
  int (__fastcall *v746)(__int64, _QWORD, _QWORD, void *); // rbx
  void *v747; // rax
  __int64 v748; // rdx
  __int64 v749; // rcx
  __int64 v750; // r8
  __int64 v751; // rdi
  __int64 (__fastcall *v752)(__int64, _QWORD, _QWORD, void *); // rbx
  void *v753; // rax
  __int64 v754; // rdx
  __int64 v755; // rcx
  __int64 v756; // r8
  __int64 v757; // rax
  int v758; // ebx
  int v759; // edi
  unsigned int v760; // eax
  __int64 v761; // rax
  __int64 v762; // rax
  __int64 v763; // rax
  __int64 v764; // rax
  __int64 v765; // rax
  __int64 v766; // rdx
  __int64 v767; // rcx
  __int64 v768; // r8
  int v769; // eax
  int v770; // edx
  const char *v771; // rcx
  void *v772; // rax
  unsigned int v773; // eax
  __int64 v774; // rdx
  __int64 v775; // rcx
  __int64 v776; // r8
  __int64 v777; // rax
  __int64 v778; // rdx
  __int64 v779; // rcx
  __int64 v780; // r8
  __int64 v781; // rdx
  __int64 v782; // rcx
  __int64 v783; // r8
  __int64 v784; // rsi
  unsigned int v785; // eax
  unsigned int v786; // edi
  RdpRemoteAppCore *v787; // r15
  unsigned int v788; // eax
  __int64 v789; // rdx
  __int64 v790; // rax
  const wchar_t *v791; // rbx
  __int64 v792; // rdi
  __int64 (__fastcall *v793)(__int64, _QWORD, _QWORD, void *); // rbx
  void *v794; // rax
  __int64 v795; // rdx
  __int64 v796; // rcx
  __int64 v797; // r8
  int v798; // eax
  int v799; // edx
  const char *v800; // rcx
  unsigned int v801; // edi
  unsigned int v802; // r9d
  __int64 v803; // r8
  __int64 v804; // rcx
  unsigned int v805; // edi
  __int64 v806; // rax
  const wchar_t *v807; // rbx
  __int64 v808; // rdi
  __int64 (__fastcall *v809)(__int64, _QWORD, _QWORD, __int64, _DWORD, _DWORD, char *, _DWORD, __int64, _DWORD, __int64, _DWORD, void *); // rbx
  void *v810; // rax
  __int64 v811; // r9
  __int64 v812; // rdx
  __int64 v813; // rcx
  __int64 v814; // r8
  __int64 v815; // rdi
  __int64 (__fastcall *v816)(__int64, __int64); // rbx
  __int64 v817; // rax
  __int64 v818; // rdx
  __int64 v819; // rcx
  __int64 v820; // r8
  __int64 v821; // rax
  const wchar_t *v822; // rbx
  struct RdpXInterfaceShellNotifyInformation *v823; // rbx
  __int64 v824; // rax
  unsigned int v825; // eax
  __int64 v826; // rdx
  __int64 v827; // rcx
  __int64 v828; // r8
  HKEY v829; // rdx
  unsigned int v830; // eax
  __int64 v831; // rsi
  unsigned int v832; // eax
  __int64 v833; // r15
  unsigned int v834; // eax
  int v835; // edx
  char *v836; // rcx
  unsigned int v837; // esi
  size_t cchToCopy; // [rsp+20h] [rbp-120h]
  size_t cchToCopya; // [rsp+20h] [rbp-120h]
  size_t cchToCopyb; // [rsp+20h] [rbp-120h]
  size_t cchToCopyc; // [rsp+20h] [rbp-120h]
  unsigned __int16 *v843; // [rsp+28h] [rbp-118h]
  unsigned __int16 *v844; // [rsp+28h] [rbp-118h]
  unsigned __int16 *v845; // [rsp+28h] [rbp-118h]
  unsigned __int16 *v846; // [rsp+28h] [rbp-118h]
  unsigned __int16 *v847; // [rsp+28h] [rbp-118h]
  unsigned __int16 *v848; // [rsp+28h] [rbp-118h]
  unsigned __int16 *v849; // [rsp+28h] [rbp-118h]
  unsigned __int16 *v850; // [rsp+28h] [rbp-118h]
  unsigned __int16 *v851; // [rsp+28h] [rbp-118h]
  int v852; // [rsp+28h] [rbp-118h]
  __int64 v853; // [rsp+30h] [rbp-110h]
  __int64 v854; // [rsp+30h] [rbp-110h]
  __int64 v855; // [rsp+30h] [rbp-110h]
  __int64 v856; // [rsp+38h] [rbp-108h]
  __int64 v857; // [rsp+38h] [rbp-108h]
  __int64 v858; // [rsp+40h] [rbp-100h]
  __int64 v859; // [rsp+40h] [rbp-100h]
  char v860[8]; // [rsp+C0h] [rbp-80h] BYREF
  char v861[8]; // [rsp+C8h] [rbp-78h] BYREF
  char v862[8]; // [rsp+D0h] [rbp-70h] BYREF
  int v863; // [rsp+D8h] [rbp-68h]
  char v864[8]; // [rsp+E0h] [rbp-60h] BYREF
  struct ITSWndPluginEx *v865; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v866; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v867; // [rsp+F8h] [rbp-48h] BYREF
  char v868[8]; // [rsp+100h] [rbp-40h] BYREF
  char v869[8]; // [rsp+108h] [rbp-38h] BYREF
  struct RdpXInterfaceRemoteAppWindow *v870; // [rsp+110h] [rbp-30h] BYREF
  char v871[8]; // [rsp+118h] [rbp-28h] BYREF
  _BYTE v872[16]; // [rsp+120h] [rbp-20h] BYREF
  RdpRemoteAppCore *v873; // [rsp+130h] [rbp-10h] BYREF
  int v874; // [rsp+138h] [rbp-8h]
  int v875; // [rsp+13Ch] [rbp-4h]
  char v876[8]; // [rsp+140h] [rbp+0h] BYREF
  char v877[8]; // [rsp+148h] [rbp+8h] BYREF
  __int64 v878; // [rsp+150h] [rbp+10h] BYREF
  int v879; // [rsp+158h] [rbp+18h]
  int v880; // [rsp+15Ch] [rbp+1Ch]
  char v881[8]; // [rsp+160h] [rbp+20h] BYREF
  char v882[8]; // [rsp+168h] [rbp+28h] BYREF
  unsigned int v883; // [rsp+170h] [rbp+30h]
  int v884; // [rsp+174h] [rbp+34h]
  int v885; // [rsp+178h] [rbp+38h]
  __int64 *v886; // [rsp+180h] [rbp+40h] BYREF
  struct RdpXInterfaceRemoteAppWindow *v887; // [rsp+188h] [rbp+48h] BYREF
  char v888[8]; // [rsp+190h] [rbp+50h] BYREF
  char v889[8]; // [rsp+198h] [rbp+58h] BYREF
  char v890[8]; // [rsp+1A0h] [rbp+60h] BYREF
  char v891[8]; // [rsp+1A8h] [rbp+68h] BYREF
  char v892[8]; // [rsp+1B0h] [rbp+70h] BYREF
  __int64 v893; // [rsp+1B8h] [rbp+78h] BYREF
  struct RdpXInterfaceRemoteAppWindow *v894; // [rsp+1C0h] [rbp+80h] BYREF
  char v895[8]; // [rsp+1C8h] [rbp+88h] BYREF
  char v896[8]; // [rsp+1D0h] [rbp+90h] BYREF
  char v897[8]; // [rsp+1D8h] [rbp+98h] BYREF
  __int64 v898; // [rsp+1E0h] [rbp+A0h] BYREF
  char v899[8]; // [rsp+1E8h] [rbp+A8h] BYREF
  char v900[8]; // [rsp+1F0h] [rbp+B0h] BYREF
  char v901[8]; // [rsp+1F8h] [rbp+B8h] BYREF
  char v902[8]; // [rsp+200h] [rbp+C0h] BYREF
  char v903[8]; // [rsp+208h] [rbp+C8h] BYREF
  char v904[8]; // [rsp+210h] [rbp+D0h] BYREF
  __int64 v905; // [rsp+218h] [rbp+D8h] BYREF
  struct RdpXInterfaceRemoteAppWindow *v906; // [rsp+220h] [rbp+E0h] BYREF
  struct RdpXInterfaceRemoteAppWindow *v907; // [rsp+228h] [rbp+E8h] BYREF
  char v908[8]; // [rsp+230h] [rbp+F0h] BYREF
  char v909[8]; // [rsp+238h] [rbp+F8h] BYREF
  int v910; // [rsp+240h] [rbp+100h]
  int v911; // [rsp+244h] [rbp+104h]
  int v912; // [rsp+248h] [rbp+108h]
  int v913; // [rsp+24Ch] [rbp+10Ch]
  unsigned int v914; // [rsp+250h] [rbp+110h]
  int v915; // [rsp+254h] [rbp+114h]
  int v916; // [rsp+258h] [rbp+118h]
  char v917[8]; // [rsp+260h] [rbp+120h] BYREF
  char v918[8]; // [rsp+268h] [rbp+128h] BYREF
  char v919[8]; // [rsp+270h] [rbp+130h] BYREF
  __int64 v920; // [rsp+278h] [rbp+138h] BYREF
  __int64 v921; // [rsp+280h] [rbp+140h] BYREF
  struct RdpXInterfaceRemoteAppWindow *v922; // [rsp+288h] [rbp+148h] BYREF
  struct RdpXInterfaceRemoteAppWindow *v923; // [rsp+290h] [rbp+150h] BYREF
  struct RdpXInterfaceRemoteAppWindow *v924; // [rsp+298h] [rbp+158h] BYREF
  char v925[8]; // [rsp+2A0h] [rbp+160h] BYREF
  struct RdpXInterfaceRemoteAppWindow *v926; // [rsp+2A8h] [rbp+168h] BYREF
  char v927[8]; // [rsp+2B0h] [rbp+170h] BYREF
  unsigned __int16 *v928; // [rsp+2B8h] [rbp+178h] BYREF
  unsigned __int64 v929; // [rsp+2C0h] [rbp+180h] BYREF
  _DWORD v930[2]; // [rsp+2C8h] [rbp+188h] BYREF
  int v931; // [rsp+2D0h] [rbp+190h]
  int v932; // [rsp+2D4h] [rbp+194h]
  __int128 v933; // [rsp+2D8h] [rbp+198h] BYREF
  _DWORD v934[4]; // [rsp+2E8h] [rbp+1A8h] BYREF
  _DWORD v935[4]; // [rsp+2F8h] [rbp+1B8h] BYREF
  __int128 v936; // [rsp+308h] [rbp+1C8h] BYREF
  _OWORD v937[2]; // [rsp+318h] [rbp+1D8h] BYREF
  __int64 v938; // [rsp+338h] [rbp+1F8h]
  unsigned __int16 Destination[264]; // [rsp+340h] [rbp+200h] BYREF
  unsigned __int16 v940[264]; // [rsp+550h] [rbp+410h] BYREF
  wchar_t pszDest[264]; // [rsp+760h] [rbp+620h] BYREF
  wchar_t v942[264]; // [rsp+970h] [rbp+830h] BYREF

  v3 = a3;
  v873 = this;
  v4 = a2;
  v5 = this;
  if ( !*((_QWORD *)this + 13) )
  {
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147467261;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(this, a2, a3);
    v7 = 62;
    v8 = "m_spTsClientPlatformInstance";
LABEL_6:
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
      ActivityIdPrefix,
      (__int64)v8);
    return (unsigned int)-2147467261;
  }
  LOBYTE(a2) = 3;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_RailV2ConnectionInfoDisclosure>::__private_IsEnabledPreCheck(
    `wil::Feature<__WilFeatureTraits_Feature_EnableRailV2>::GetImpl'::`2'::impl,
    a2);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableRailV2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnableRailV2>::GetImpl'::`2'::impl) )
  {
    if ( !*((_QWORD *)v5 + 12) )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)-2147467261;
      }
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(v11, v10, v12);
      v7 = 63;
      v8 = "m_remoteAppPlugin.get()";
      goto LABEL_6;
    }
  }
  else if ( !*((_QWORD *)v5 + 11) )
  {
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147467261;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(v11, v10, v12);
    v7 = 64;
    v8 = "m_spRemoteAppPlugin";
    goto LABEL_6;
  }
  if ( v3 < 4 )
  {
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147467259;
    }
    v13 = RdpX_GetActivityIdPrefix(v11, v10, v12);
    v14 = 65;
LABEL_24:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v13);
    return (unsigned int)-2147467259;
  }
  if ( v3 < *((unsigned __int16 *)v4 + 1) )
  {
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147467259;
    }
    v13 = RdpX_GetActivityIdPrefix(v11, v10, v12);
    v14 = 66;
    goto LABEL_24;
  }
  RDPRailTraceLogging::TraceRailPDU(v4, v10);
  v17 = *(unsigned __int16 *)v4;
  if ( (unsigned int)v17 > 0x80 )
    goto LABEL_1160;
  if ( (_DWORD)v17 == 128 )
    goto LABEL_1134;
  if ( (unsigned int)v17 > 0x18 )
  {
    if ( (unsigned int)v17 <= 0x21 )
    {
      if ( (_DWORD)v17 == 33 )
      {
        RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v925);
        if ( *((_WORD *)v4 + 1) >= 0xEu
          || (RdpRemoteAppCore::LogRemoteAppError(
                (char *)v5 + 16,
                L"Invalid size of TS_RAIL_ORDER_WINDOW_APPBAR_INFO_BODY PDU",
                2147549183LL,
                0,
                0),
              *((_WORD *)v4 + 1) >= 0xEu) )
        {
          LODWORD(cchToCopy) = *((_DWORD *)v4 + 2);
          RdpRemoteAppCore::LogRemoteAppEventF(
            (char *)v5 + 16,
            L"WindowAppBarInfoRailOrderReceived: WindowId=0x%x, FieldsValidFlags=0x%x, ShouldRegisterAppBar=%hhu, AppBarEdge=%hhu",
            0,
            *((unsigned int *)v4 + 1),
            cchToCopy,
            *((unsigned __int8 *)v4 + 12),
            *((unsigned __int8 *)v4 + 13));
          v495 = (struct RdpXInterfaceRemoteAppWindow **)CacCommon::Rect<int>::Rect<int>(v925);
          RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow(
                              (RdpRemoteAppCore *)((char *)v5 - 48),
                              *((_DWORD *)v4 + 1),
                              v495);
          if ( RemoteAppWindow >= 0 )
          {
            if ( (*((_BYTE *)v4 + 8) & 0x40) != 0 )
            {
              if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                v501 = *((unsigned __int8 *)v4 + 12);
                v502 = RdpX_GetActivityIdPrefix(v497, v496, v498);
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  163,
                  &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                  v502,
                  v501);
              }
              v503 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v925);
              (*(void (__fastcall **)(__int64, bool))(*(_QWORD *)v503 + 344LL))(v503, *((_BYTE *)v4 + 12) == 1);
            }
            if ( (*((_BYTE *)v4 + 8) & 1) != 0 )
            {
              if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                v504 = *((unsigned __int8 *)v4 + 13);
                v505 = RdpX_GetActivityIdPrefix(v497, v496, v498);
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  164,
                  &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                  v505,
                  v504);
              }
              v506 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v925);
              LOBYTE(v507) = *((_BYTE *)v4 + 13);
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v506 + 352LL))(v506, v507);
            }
          }
          else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                 && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v499 = *((_DWORD *)v4 + 1);
            v500 = RdpX_GetActivityIdPrefix(v497, v496, v498);
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              162,
              &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v500,
              v499);
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v494 = RdpX_GetActivityIdPrefix(v492, v491, v493);
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              161,
              &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v494,
              -2147418113);
          }
          RemoteAppWindow = -2147418113;
        }
        v251 = v925;
        goto LABEL_629;
      }
      RemoteAppWindow = 0;
      if ( (_DWORD)v17 != 27 )
      {
        if ( (_DWORD)v17 != 28 )
        {
          if ( (_DWORD)v17 != 29 )
          {
            if ( (_DWORD)v17 != 30 )
            {
              if ( (_DWORD)v17 != 31 )
              {
                if ( (_DWORD)v17 != 32 )
                  goto LABEL_1160;
                RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v900);
                RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v899);
                RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v909);
                if ( *((_WORD *)v4 + 1) < 0x10u )
                {
                  RdpRemoteAppCore::LogRemoteAppError(
                    (char *)v5 + 16,
                    L"Invalid size of TS_RAIL_ORDER_WINDOW_CACHED_ICON PDU",
                    2147549183LL,
                    0,
                    0);
                  if ( *((_WORD *)v4 + 1) < 0x10u )
                  {
                    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      v250 = RdpX_GetActivityIdPrefix(v248, v247, v249);
                      WPP_SF_Dd(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        156,
                        &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                        v250,
                        -2147418113);
                    }
                    RemoteAppWindow = -2147418113;
                    goto LABEL_434;
                  }
                }
                LODWORD(cchToCopy) = *((unsigned __int8 *)v4 + 8);
                RdpRemoteAppCore::LogRemoteAppEventF(
                  (char *)v5 + 16,
                  L"WindowCachedIconRailOrderReceived: WindowId=0x%x, NumIcons=%hhu, CacheEntry=0x%hx, CacheId=0x%hhx, IconFlags=0x%hhx",
                  0,
                  *((unsigned int *)v4 + 1),
                  cchToCopy,
                  *((unsigned __int16 *)v4 + 6),
                  *((unsigned __int8 *)v4 + 14),
                  *((unsigned __int8 *)v4 + 15));
                v252 = (struct RdpXInterfaceRemoteAppWindow **)CacCommon::Rect<int>::Rect<int>(v900);
                RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow(
                                    (RdpRemoteAppCore *)((char *)v5 - 48),
                                    *((_DWORD *)v4 + 1),
                                    v252);
                if ( RemoteAppWindow < 0 )
                {
                  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                    && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v256 = *((_DWORD *)v4 + 1);
                    v257 = RdpX_GetActivityIdPrefix(v254, v253, v255);
                    WPP_SF_Dd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      157,
                      &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                      v257,
                      v256);
                  }
                  goto LABEL_434;
                }
                v258 = (struct ITSWndPluginEx **)CacCommon::Rect<int>::Rect<int>(v899);
                RemoteAppWindow = RdpRemoteAppCore::GetWndPlugin((RdpRemoteAppCore *)((char *)v5 - 48), v258);
                if ( RemoteAppWindow >= 0 )
                {
                  v265 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v899);
                  v266 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, void *))(*(_QWORD *)v265 + 56LL);
                  v267 = CacCommon::Rect<int>::Rect<int>(v909);
                  RemoteAppWindow = v266(v265, *((unsigned __int8 *)v4 + 14), *((unsigned __int16 *)v4 + 6), v267);
                  if ( RemoteAppWindow >= 0 )
                  {
                    v271 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v900);
                    v272 = *((_BYTE *)v4 + 15) == 1;
                    v273 = *(__int64 (__fastcall **)(__int64, __int64, BOOL))(*(_QWORD *)v271 + 88LL);
                    v274 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v909);
                    RemoteAppWindow = v273(v271, v274, v272);
                    if ( RemoteAppWindow >= 0
                      || WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                    {
                      goto LABEL_434;
                    }
                    v262 = RdpX_GetActivityIdPrefix(v276, v275, v277);
                    v263 = 160;
                    v264 = "UpdateIcon failed";
                  }
                  else
                  {
                    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                    {
                      goto LABEL_434;
                    }
                    v262 = RdpX_GetActivityIdPrefix(v269, v268, v270);
                    v263 = 159;
                    v264 = "CreateCachedIcon failed";
                  }
                }
                else
                {
                  if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                    || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                  {
                    goto LABEL_434;
                  }
                  v262 = RdpX_GetActivityIdPrefix(v260, v259, v261);
                  v263 = 158;
                  v264 = "GetWndPlugin failed";
                }
                LODWORD(v848) = RemoteAppWindow;
                WPP_SF_DsD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v263,
                  (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                  v262,
                  (__int64)v264,
                  v848);
LABEL_434:
                RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v909);
                TCntPtr<ITSViewerRecorder>::SafeRelease(v899);
                v251 = v900;
LABEL_629:
                RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v251);
                return (unsigned int)RemoteAppWindow;
              }
              RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v897);
              RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v896);
              RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v895);
              LOWORD(v863) = 32;
              if ( *((_WORD *)v4 + 1) < 0x20u )
              {
                RdpRemoteAppCore::LogRemoteAppError(
                  (char *)v5 + 16,
                  L"Invalid size of TS_RAIL_ORDER_WINDOW_ICON_BODY PDU",
                  2147549183LL,
                  0,
                  0);
                if ( *((_WORD *)v4 + 1) < 0x20u )
                {
                  if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                    || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                  {
                    goto LABEL_463;
                  }
                  v281 = RdpX_GetActivityIdPrefix(v279, v278, v280);
                  v282 = 150;
LABEL_462:
                  WPP_SF_Dd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    v282,
                    &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                    v281,
                    -2147418113);
LABEL_463:
                  RemoteAppWindow = -2147418113;
LABEL_464:
                  RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v895);
                  TCntPtr<ITSViewerRecorder>::SafeRelease(v896);
                  v251 = v897;
                  goto LABEL_629;
                }
              }
              v283 = (struct RdpXInterfaceRemoteAppWindow **)CacCommon::Rect<int>::Rect<int>(v897);
              RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow(
                                  (RdpRemoteAppCore *)((char *)v5 - 48),
                                  *((_DWORD *)v4 + 1),
                                  v283);
              if ( RemoteAppWindow < 0 )
              {
                if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                  && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v287 = *((_DWORD *)v4 + 1);
                  v288 = RdpX_GetActivityIdPrefix(v285, v284, v286);
                  WPP_SF_Dd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    151,
                    &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                    v288,
                    v287);
                }
                goto LABEL_464;
              }
              v289 = (struct ITSWndPluginEx **)CacCommon::Rect<int>::Rect<int>(v896);
              WndPlugin = RdpRemoteAppCore::GetWndPlugin((RdpRemoteAppCore *)((char *)v5 - 48), v289);
              RemoteAppWindow = WndPlugin;
              if ( WndPlugin >= 0 )
              {
                if ( (*((_BYTE *)v4 + 15) & 2) != 0 )
                {
                  LOBYTE(WndPlugin) = *((_BYTE *)v4 + 20);
                  v297 = *((_WORD *)v4 + 11);
                  LOWORD(v863) = WndPlugin;
                }
                else
                {
                  v297 = 0;
                }
                v298 = *((_DWORD *)v4 + 6) + 32;
                v299 = (unsigned int)v297 + *((_DWORD *)v4 + 7);
                LODWORD(v878) = v297;
                v300 = v299 + v298;
                if ( *((unsigned __int16 *)v4 + 1) < v300 )
                  RdpRemoteAppCore::LogRemoteAppError(
                    (char *)v5 + 16,
                    L"Invalid size of TS_RAIL_ORDER_WINDOW_ICON_BODY PDU",
                    2147549183LL,
                    0,
                    0);
                if ( *((unsigned __int16 *)v4 + 1) < v300 )
                {
                  if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                    || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                  {
                    goto LABEL_463;
                  }
                  v281 = RdpX_GetActivityIdPrefix(v299, v291, v293);
                  v282 = 153;
                  goto LABEL_462;
                }
                LODWORD(cchToCopy) = *((unsigned __int8 *)v4 + 8);
                RdpRemoteAppCore::LogRemoteAppEventF(
                  (char *)v873 + 16,
                  L"WindowIconRailOrderReceived: WindowId=0x%x, NumIcons=%hhu, CacheEntry=0x%hx, CacheId=0x%hhx, IconFlags"
                   "=0x%hhx, Width=%hu, Height=%hu, Bpp=%hhu, ColorTableBytes=%hu, BitsMaskBytes=%u, BitsColorBytes=%u",
                  0,
                  *((unsigned int *)v4 + 1),
                  cchToCopy,
                  *((unsigned __int16 *)v4 + 6),
                  *((unsigned __int8 *)v4 + 14),
                  *((unsigned __int8 *)v4 + 15),
                  *((unsigned __int16 *)v4 + 8),
                  *((unsigned __int16 *)v4 + 9),
                  *((unsigned __int8 *)v4 + 20),
                  *((unsigned __int16 *)v4 + 11),
                  *((_DWORD *)v4 + 6),
                  *((_DWORD *)v4 + 7));
                v301 = (__int64)v4 + v297 + 32;
                v302 = v301 + *((unsigned int *)v4 + 6);
                v303 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v896);
                v304 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64, _DWORD, _DWORD, char *, _DWORD, __int64, _DWORD, __int64, _DWORD, void *))(*(_QWORD *)v303 + 64LL);
                v305 = CacCommon::Rect<int>::Rect<int>(v895);
                v306 = *((unsigned __int16 *)v4 + 9);
                LOBYTE(v306) = v863;
                RemoteAppWindow = v304(
                                    v303,
                                    *((unsigned __int8 *)v4 + 14),
                                    *((unsigned __int16 *)v4 + 6),
                                    v306,
                                    *((unsigned __int16 *)v4 + 8),
                                    *((unsigned __int16 *)v4 + 9),
                                    (char *)v4 + 32,
                                    v878,
                                    v301,
                                    *((_DWORD *)v4 + 6),
                                    v302,
                                    *((_DWORD *)v4 + 7),
                                    v305);
                if ( RemoteAppWindow >= 0 )
                {
                  v310 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v897);
                  v311 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v310 + 88LL);
                  v312 = *((_BYTE *)v4 + 15) & 1;
                  v313 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v895);
                  RemoteAppWindow = v311(v310, v313, v312);
                  if ( RemoteAppWindow >= 0
                    || WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                    || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                  {
                    goto LABEL_464;
                  }
                  v294 = RdpX_GetActivityIdPrefix(v315, v314, v316);
                  v295 = 155;
                  v296 = "UpdateIcon failed";
                }
                else
                {
                  if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                    || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                  {
                    goto LABEL_464;
                  }
                  v294 = RdpX_GetActivityIdPrefix(v308, v307, v309);
                  v295 = 154;
                  v296 = "CreateCachedIcon failed";
                }
              }
              else
              {
                if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                  || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_464;
                }
                v294 = RdpX_GetActivityIdPrefix(v292, v291, v293);
                v295 = 152;
                v296 = "GetWndPlugin failed";
              }
              LODWORD(v843) = RemoteAppWindow;
              WPP_SF_DsD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v295,
                (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                v294,
                (__int64)v296,
                v843);
              goto LABEL_464;
            }
            RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v902);
            RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v901);
            if ( *((_WORD *)v4 + 1) < 8u )
            {
              RdpRemoteAppCore::LogRemoteAppError(
                (char *)v5 + 16,
                L"Invalid size of TS_RAIL_ORDER_WINDOW_DELETE_BODY PDU",
                2147549183LL,
                0,
                0);
              if ( *((_WORD *)v4 + 1) < 8u )
              {
                if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                  && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v320 = RdpX_GetActivityIdPrefix(v318, v317, v319);
                  WPP_SF_Dd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    146,
                    &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                    v320,
                    -2147418113);
                }
                RemoteAppWindow = -2147418113;
                goto LABEL_503;
              }
            }
            RdpRemoteAppCore::LogRemoteAppEventF(
              (char *)v5 + 16,
              L"WindowDeleteRailOrderReceived: WindowId=0x%x",
              0,
              *((unsigned int *)v4 + 1));
            v321 = (struct RdpXInterfaceRemoteAppWindow **)CacCommon::Rect<int>::Rect<int>(v902);
            RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow(
                                (RdpRemoteAppCore *)((char *)v5 - 48),
                                *((_DWORD *)v4 + 1),
                                v321);
            if ( RemoteAppWindow < 0 )
            {
              if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v325 = *((_DWORD *)v4 + 1);
                v326 = RdpX_GetActivityIdPrefix(v323, v322, v324);
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  147,
                  &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                  v326,
                  v325);
              }
              goto LABEL_503;
            }
            v327 = (struct ITSWndPluginEx **)CacCommon::Rect<int>::Rect<int>(v901);
            RemoteAppWindow = RdpRemoteAppCore::GetWndPlugin((RdpRemoteAppCore *)((char *)v5 - 48), v327);
            if ( RemoteAppWindow >= 0 )
            {
              v334 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v902);
              v335 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v901);
              v336 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v335 + 88LL))(v335);
              if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v334 + 72LL))(v334) == v336 )
              {
                v337 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v901);
                (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v337 + 96LL))(v337, 0);
              }
              v338 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *((char *)v873 + 128);
              v339 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v338 + 64LL);
              v340 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v902);
              v341 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v340 + 72LL))(v340);
              v342 = v339(v338, v341);
              RemoteAppWindow = MapXResultToHR(v342);
              if ( RemoteAppWindow >= 0
                || WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_503;
              }
              v331 = RdpX_GetActivityIdPrefix(v344, v343, v345);
              v332 = 149;
              v333 = "DeleteWindow failed";
            }
            else
            {
              if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_503;
              }
              v331 = RdpX_GetActivityIdPrefix(v329, v328, v330);
              v332 = 148;
              v333 = "GetWndPlugin failed";
            }
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v332,
              (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v331,
              (__int64)v333,
              RemoteAppWindow);
LABEL_503:
            TCntPtr<ITSViewerRecorder>::SafeRelease(v901);
            v251 = v902;
            goto LABEL_629;
          }
          RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v868);
          v873 = (RdpRemoteAppCore *)((char *)v5 + 16);
          if ( *((_WORD *)v4 + 1) < 0x58u )
            RdpRemoteAppCore::LogRemoteAppError(
              (char *)v5 + 16,
              L"Invalid size of TS_RAIL_ORDER_WINDOW_GEOMETRY_BODY PDU",
              2147549183LL,
              0,
              0);
          v348 = *((unsigned __int16 *)v4 + 1);
          if ( (unsigned int)v348 < 0x58 )
          {
            if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
              || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_530;
            }
            v349 = RdpX_GetActivityIdPrefix(v348, v346, v347);
            v350 = 141;
LABEL_529:
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v350,
              &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v349,
              -2147418113);
LABEL_530:
            RemoteAppWindow = -2147418113;
LABEL_531:
            v251 = v868;
            goto LABEL_629;
          }
          v351 = 16 * *((unsigned __int16 *)v4 + 34) + 72;
          if ( (unsigned int)v348 < v351 )
            RdpRemoteAppCore::LogRemoteAppError(
              (char *)v5 + 16,
              L"Invalid size of TS_RAIL_ORDER_WINDOW_GEOMETRY_BODY PDU",
              2147549183LL,
              0,
              0);
          if ( *((unsigned __int16 *)v4 + 1) < v351 )
          {
            if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
              || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_530;
            }
            v349 = RdpX_GetActivityIdPrefix(v348, v346, v347);
            v350 = 142;
            goto LABEL_529;
          }
          LODWORD(cchToCopy) = *((_DWORD *)v4 + 2);
          RdpRemoteAppCore::LogRemoteAppEventF(
            (char *)v5 + 16,
            L"WindowGeometryRailOrderReceived: WindowId=0x%x, FieldsValidFlags=0x%x, Style=0x%08x, StyleEx=0x%08x, ShowSta"
             "te=%hhu, OffsetX=%i, OffsetY=%i, Width=%i, Height=%i, WindowClientDeltaX=%i, WindowClientDeltaY=%i, ResizeM"
             "arginLeft=%i, ResizeMarginTop=%i, ResizeMarginRight=%i, ResizeMarginBottom=%i, NumVisibilityRects=%hu",
            0,
            *((unsigned int *)v4 + 1),
            cchToCopy,
            *((_DWORD *)v4 + 3),
            *((_DWORD *)v4 + 4),
            *((unsigned __int8 *)v4 + 20),
            *((_DWORD *)v4 + 7),
            *((_DWORD *)v4 + 8),
            *((_DWORD *)v4 + 9),
            *((_DWORD *)v4 + 10),
            *((_DWORD *)v4 + 11),
            *((_DWORD *)v4 + 12),
            *((_DWORD *)v4 + 13),
            *((_DWORD *)v4 + 15),
            *((_DWORD *)v4 + 14),
            *((_DWORD *)v4 + 16),
            *((unsigned __int16 *)v4 + 34));
          if ( *((_DWORD *)v4 + 1) == -1 )
          {
            if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
              && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              v355 = RdpX_GetActivityIdPrefix(v353, v352, v354);
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 143, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v355);
            }
            goto LABEL_531;
          }
          v356 = (struct RdpXInterfaceRemoteAppWindow **)CacCommon::Rect<int>::Rect<int>(v868);
          RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow(
                              (RdpRemoteAppCore *)((char *)v5 - 48),
                              *((_DWORD *)v4 + 1),
                              v356);
          if ( RemoteAppWindow < 0 )
          {
            if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
              && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v360 = *((_DWORD *)v4 + 1);
              v361 = RdpX_GetActivityIdPrefix(v358, v357, v359);
              WPP_SF_Dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                144,
                &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                v361,
                v360);
            }
            goto LABEL_531;
          }
          if ( (*((_BYTE *)v4 + 8) & 8) != 0 )
          {
            v362 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v868);
            (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v362 + 80LL))(
              v362,
              *((unsigned int *)v4 + 3),
              *((unsigned int *)v4 + 4));
          }
          if ( *((char *)v4 + 8) < 0 )
          {
            v363 = *((_DWORD *)v4 + 13);
            if ( v363 >= 0 )
            {
              v364 = *((_DWORD *)v4 + 14);
              if ( v364 >= 0 )
              {
                v365 = *((_DWORD *)v4 + 15);
                if ( v365 >= 0 )
                {
                  v366 = *((_DWORD *)v4 + 16);
                  if ( v366 >= 0 )
                  {
                    v367 = (__int64 *)RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v868);
                    v878 = __PAIR64__(v364, v363);
                    v879 = v365;
                    v368 = *v367;
                    v880 = v366;
                    (*(void (__fastcall **)(__int64 *, __int64 *, _QWORD))(v368 + 336))(v367, &v878, 0);
                  }
                }
              }
            }
          }
          if ( (*((_DWORD *)v4 + 2) & 0x8000) != 0 )
          {
            v369 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v868);
            (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v369 + 256LL))(
              v369,
              *((unsigned int *)v4 + 11),
              *((unsigned int *)v4 + 12));
            if ( (*((_DWORD *)v4 + 2) & 0x800) != 0 )
            {
              v370 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v868);
              (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v370 + 224LL))(
                v370,
                (unsigned int)(*((_DWORD *)v4 + 7) + *((_DWORD *)v4 + 11)),
                (unsigned int)(*((_DWORD *)v4 + 8) + *((_DWORD *)v4 + 12)));
            }
          }
          if ( (*((_DWORD *)v4 + 2) & 0x800) != 0 )
          {
            if ( (*((_DWORD *)v4 + 2) & 0x400) != 0 )
            {
              v935[0] = *((_DWORD *)v4 + 7);
              v935[1] = *((_DWORD *)v4 + 8);
              v935[2] = *((_DWORD *)v4 + 9);
              v935[3] = *((_DWORD *)v4 + 10);
              v371 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v868);
              (*(void (__fastcall **)(__int64, _DWORD *, _QWORD))(*(_QWORD *)v371 + 248LL))(v371, v935, 0);
              v372 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v868);
              (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v372 + 160LL))(
                v372,
                *((int *)v4 + 7),
                *((int *)v4 + 8));
              goto LABEL_566;
            }
            v373 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v868);
            (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v373 + 232LL))(
              v373,
              *((unsigned int *)v4 + 7),
              *((unsigned int *)v4 + 8),
              0);
            v374 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v868);
            (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v374 + 160LL))(
              v374,
              *((int *)v4 + 7),
              *((int *)v4 + 8));
          }
          if ( (*((_DWORD *)v4 + 2) & 0x400) != 0 )
          {
            v375 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v868);
            (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v375 + 240LL))(
              v375,
              *((unsigned int *)v4 + 9),
              *((unsigned int *)v4 + 10),
              0);
          }
LABEL_566:
          if ( (*((_DWORD *)v4 + 2) & 0x100) != 0 )
          {
            v378 = (char *)operator new(saturated_mul(*((unsigned __int16 *)v4 + 34), 0x10u));
            if ( !v378 )
            {
              if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v380 = RdpX_GetActivityIdPrefix(v377, v376, v379);
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  145,
                  &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                  v380,
                  -2147024882);
              }
              RemoteAppWindow = -2147024882;
              goto LABEL_531;
            }
            v381 = 0;
            if ( *((_WORD *)v4 + 34) )
            {
              v382 = v873;
              do
              {
                v383 = 16LL * v381;
                *(_DWORD *)&v378[v383] = *(_DWORD *)((char *)v4 + v383 + 72);
                *(_DWORD *)&v378[v383 + 4] = *(_DWORD *)((char *)v4 + v383 + 76);
                *(_DWORD *)&v378[v383 + 8] = *((_DWORD *)v4 + 4 * v381 + 20) - *(_DWORD *)((char *)v4 + v383 + 72);
                *(_DWORD *)&v378[v383 + 12] = *(_DWORD *)((char *)v4 + v383 + 84) - *(_DWORD *)((char *)v4 + v383 + 76);
                LODWORD(v858) = *(_DWORD *)((char *)v4 + v383 + 84);
                LODWORD(v856) = *((_DWORD *)v4 + 4 * v381 + 20);
                LODWORD(v854) = *(_DWORD *)((char *)v4 + v383 + 76);
                LODWORD(v849) = *(_DWORD *)((char *)v4 + v383 + 72);
                LODWORD(cchToCopya) = *((_DWORD *)v4 + 1);
                RdpRemoteAppCore::LogRemoteAppEventF(
                  v382,
                  L"WindowGeometryRailOrderReceived_VisibilityRect[%i]: WindowId=0x%x, Left=%i, Top=%i, Right=%i, Bottom=%i",
                  0,
                  (unsigned int)v381++,
                  cchToCopya,
                  v849,
                  v854,
                  v856,
                  v858);
              }
              while ( v381 < *((unsigned __int16 *)v4 + 34) );
            }
            v384 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v868);
            (*(void (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v384 + 176LL))(
              v384,
              *((unsigned __int16 *)v4 + 34),
              v378);
            v385 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v868);
            (*(void (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v385 + 168LL))(
              v385,
              *((unsigned __int16 *)v4 + 34),
              v378);
            operator delete(v378);
          }
          if ( (*((_BYTE *)v4 + 8) & 0x10) != 0 )
          {
            v386 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v868);
            (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v386 + 128LL))(v386, *((unsigned __int8 *)v4 + 20));
          }
          RemoteAppWindow = 0;
          goto LABEL_531;
        }
        RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v881);
        if ( *((_WORD *)v4 + 1) < 0x1Eu )
          RdpRemoteAppCore::LogRemoteAppError(
            (char *)v5 + 16,
            L"Invalid size of TS_RAIL_ORDER_WINDOW_CHANGE_BODY PDU",
            2147549183LL,
            0,
            0);
        v389 = *((unsigned __int16 *)v4 + 1);
        if ( (unsigned int)v389 >= 0x1E )
        {
          v392 = *((unsigned __int16 *)v4 + 13) + 28;
          if ( (unsigned int)v389 < v392 )
            RdpRemoteAppCore::LogRemoteAppError(
              (char *)v5 + 16,
              L"Invalid size of TS_RAIL_ORDER_WINDOW_CHANGE_BODY PDU",
              2147549183LL,
              0,
              0);
          if ( *((unsigned __int16 *)v4 + 1) >= v392 )
          {
            if ( *((_DWORD *)v4 + 1) == -1 )
            {
              if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                v393 = RdpX_GetActivityIdPrefix(v389, v387, v388);
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  139,
                  &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                  v393);
              }
            }
            else
            {
              v394 = (struct RdpXInterfaceRemoteAppWindow **)CacCommon::Rect<int>::Rect<int>(v881);
              RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow(
                                  (RdpRemoteAppCore *)((char *)v5 - 48),
                                  *((_DWORD *)v4 + 1),
                                  v394);
              if ( RemoteAppWindow >= 0 )
              {
                if ( (*((_BYTE *)v4 + 8) & 2) != 0 )
                {
                  v400 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v881);
                  (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v400 + 120LL))(v400, *((unsigned int *)v4 + 3));
                }
                if ( (*((_BYTE *)v4 + 8) & 8) != 0 )
                {
                  v401 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v881);
                  (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v401 + 80LL))(
                    v401,
                    *((unsigned int *)v4 + 4),
                    *((unsigned int *)v4 + 5));
                }
                if ( (*((_DWORD *)v4 + 2) & 0x80000) != 0 )
                {
                  v402 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v881);
                  (*(void (__fastcall **)(__int64, bool))(*(_QWORD *)v402 + 312LL))(v402, *((_BYTE *)v4 + 25) == 1);
                }
                memset_0(Destination, 0, 0x20Au);
                if ( (*((_BYTE *)v4 + 8) & 4) != 0 && *((_WORD *)v4 + 13) )
                {
                  memcpy_s(Destination, 0x208u, (char *)v4 + 28, *((unsigned __int16 *)v4 + 13));
                  v403 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v881);
                  (*(void (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v403 + 104LL))(v403, Destination);
                }
                CUT::ObfuscateFilePathW(Destination);
                LODWORD(cchToCopy) = *((_DWORD *)v4 + 2);
                RdpRemoteAppCore::LogRemoteAppEventF(
                  (char *)v5 + 16,
                  L"WindowChangeRailOrderReceived: WindowsId=0x%x, FieldsValidFlags=0x%x, WindowOwnerId=0x%x, Style=0x%08x"
                   ", StyleEx=0x%08x, ShowState=%hhu, EnforceServerZOrder=%hhu, TitleBytes=%hu, Title=%s",
                  0,
                  *((unsigned int *)v4 + 1),
                  cchToCopy,
                  *((_DWORD *)v4 + 3),
                  *((_DWORD *)v4 + 4),
                  *((_DWORD *)v4 + 5),
                  *((unsigned __int8 *)v4 + 24),
                  *((unsigned __int8 *)v4 + 25),
                  *((unsigned __int16 *)v4 + 13),
                  Destination);
                if ( (*((_BYTE *)v4 + 8) & 0x10) != 0 )
                {
                  v404 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v881);
                  (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v404 + 128LL))(
                    v404,
                    *((unsigned __int8 *)v4 + 24));
                }
                RemoteAppWindow = 0;
              }
              else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                     && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
                     && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v398 = *((_DWORD *)v4 + 1);
                v399 = RdpX_GetActivityIdPrefix(v396, v395, v397);
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  140,
                  &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                  v399,
                  v398);
              }
            }
            goto LABEL_589;
          }
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
LABEL_588:
            RemoteAppWindow = -2147418113;
LABEL_589:
            v251 = v881;
            goto LABEL_629;
          }
          v390 = RdpX_GetActivityIdPrefix(v389, v387, v388);
          v391 = 138;
        }
        else
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_588;
          }
          v390 = RdpX_GetActivityIdPrefix(v389, v387, v388);
          v391 = 137;
        }
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v391,
          &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v390,
          -2147418113);
        goto LABEL_588;
      }
      RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v860);
      RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v876);
      v933 = 0;
      if ( *((_WORD *)v4 + 1) < 0x58u )
        RdpRemoteAppCore::LogRemoteAppError(
          (char *)v5 + 16,
          L"Invalid size of TS_RAIL_ORDER_WINDOW_CREATE_BODY PDU",
          2147549183LL,
          0,
          0);
      v407 = *((unsigned __int16 *)v4 + 1);
      if ( (unsigned int)v407 < 0x58 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_627;
        }
        v408 = RdpX_GetActivityIdPrefix(v407, v405, v406);
        v409 = 127;
LABEL_626:
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v409,
          &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v408,
          -2147418113);
LABEL_627:
        RemoteAppWindow = -2147418113;
LABEL_628:
        TCntPtr<ITSViewerRecorder>::SafeRelease(v876);
        v251 = v860;
        goto LABEL_629;
      }
      if ( *((_WORD *)v4 + 34) )
        v410 = *((unsigned __int16 *)v4 + 34) - 1;
      else
        v410 = 0;
      v411 = 16 * v410 + 84;
      v412 = v411 + *((unsigned __int16 *)v4 + 13) + 4;
      LODWORD(v878) = v411;
      if ( (unsigned int)v407 < v412 )
        RdpRemoteAppCore::LogRemoteAppError(
          (char *)v5 + 16,
          L"Invalid size of TS_RAIL_ORDER_WINDOW_CREATE_BODY PDU",
          2147549183LL,
          0,
          0);
      if ( *((unsigned __int16 *)v4 + 1) < v412 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_627;
        }
        v408 = RdpX_GetActivityIdPrefix(v407, v405, v406);
        v409 = 128;
        goto LABEL_626;
      }
      if ( *((_DWORD *)v4 + 1) == -1 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v413 = RdpX_GetActivityIdPrefix(v407, v405, v406);
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 129, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v413);
        }
        goto LABEL_628;
      }
      v414 = (struct ITSWndPluginEx **)CacCommon::Rect<int>::Rect<int>(v876);
      v415 = 0;
      RemoteAppWindow = RdpRemoteAppCore::GetWndPlugin((RdpRemoteAppCore *)((char *)v5 - 48), v414);
      if ( RemoteAppWindow < 0 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v419 = RdpX_GetActivityIdPrefix(v417, v416, v418);
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            130,
            (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
            v419,
            (__int64)"GetWndPlugin failed",
            RemoteAppWindow);
        }
        goto LABEL_628;
      }
      v420 = (struct RdpXInterfaceRemoteAppWindow **)CacCommon::Rect<int>::Rect<int>(v860);
      RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow(
                          (RdpRemoteAppCore *)((char *)v5 - 48),
                          *((_DWORD *)v4 + 1),
                          v420);
      if ( RemoteAppWindow < 0 )
      {
        RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v904);
        RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v892);
        RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v903);
        v936 = 0;
        v421 = CacCommon::Rect<int>::Rect<int>(v904);
        WindowCallbacks = RdpRemoteAppCore::CreateWindowCallbacks((char *)v5 + 16, *((unsigned int *)v4 + 1), v421);
        RemoteAppWindow = MapXResultToHR(WindowCallbacks);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_657;
          }
          v426 = RdpX_GetActivityIdPrefix(v424, v423, v425);
          v427 = 131;
          v428 = "CreateWindowCallbacks failed";
LABEL_656:
          LODWORD(v843) = RemoteAppWindow;
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v427,
            (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
            v426,
            (__int64)v428,
            v843);
LABEL_657:
          ComPlainSmartPtr<IRdpBaseCoreApi>::~ComPlainSmartPtr<IRdpBaseCoreApi>(v903);
          RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v892);
          RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v904);
          goto LABEL_628;
        }
        v429 = CacCommon::Rect<int>::Rect<int>(v892);
        Object = RdpX_CreateObject(0, 0, 67, 105, v429);
        RemoteAppWindow = MapXResultToHR(Object);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_657;
          }
          v426 = RdpX_GetActivityIdPrefix(v432, v431, v433);
          v427 = 132;
          v428 = "RdpXBaseCoreApiAdaptor RdpX_CreateObject failed";
          goto LABEL_656;
        }
        v434 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *((char *)v5 + 104);
        v435 = *(__int64 (__fastcall **)(__int64, void *))(*(_QWORD *)v434 + 216LL);
        v436 = CacCommon::Rect<int>::Rect<int>(v903);
        RemoteAppWindow = v435(v434, v436);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_657;
          }
          v426 = RdpX_GetActivityIdPrefix(v438, v437, v439);
          v427 = 133;
          v428 = "Failed to get base core Api";
          goto LABEL_656;
        }
        v440 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v892);
        v441 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v440 + 24LL);
        v442 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v903);
        v443 = v441(v440, v442);
        RemoteAppWindow = MapXResultToHR(v443);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_657;
          }
          v426 = RdpX_GetActivityIdPrefix(v445, v444, v446);
          v427 = 134;
          v428 = "SetCoreApi failed";
          goto LABEL_656;
        }
        v447 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *((char *)v873 + 128);
        v448 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64, __int128 *, void *))(*(_QWORD *)v447 + 48LL);
        v449 = CacCommon::Rect<int>::Rect<int>(v860);
        v450 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v904);
        v451 = *((_DWORD *)v4 + 1);
        v452 = v450;
        v453 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v892);
        v454 = v448(v447, v453, v451, v452, &v936, v449);
        v415 = 0;
        RemoteAppWindow = MapXResultToHR(v454);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_657;
          }
          v426 = RdpX_GetActivityIdPrefix(v456, v455, v457);
          v427 = 135;
          v428 = "CreateWindowRepresentation failed";
          goto LABEL_656;
        }
        v458 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v860);
        v459 = *(__int64 (__fastcall **)(__int64, bool))(*(_QWORD *)v458 + 320LL);
        v460 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v876);
        v461 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v460 + 136LL))(v460);
        v462 = v459(v458, v461 != 0);
        RemoteAppWindow = MapXResultToHR(v462);
        v463 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v860);
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v463 + 120LL))(v463, *((unsigned int *)v4 + 3));
        ComPlainSmartPtr<IRdpBaseCoreApi>::~ComPlainSmartPtr<IRdpBaseCoreApi>(v903);
        RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v892);
        RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v904);
        v5 = v873;
        v411 = v878;
      }
      v464 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v876);
      if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v464 + 136LL))(v464) )
      {
        v465 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v860);
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v465 + 200LL))(v465, 2);
      }
      v466 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v860);
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v466 + 80LL))(
        v466,
        *((unsigned int *)v4 + 4),
        *((unsigned int *)v4 + 5));
      v467 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v860);
      (*(void (__fastcall **)(__int64, bool))(*(_QWORD *)v467 + 312LL))(v467, *((_BYTE *)v4 + 25) == 1);
      memset_0(v940, 0, 0x20Au);
      if ( *((_WORD *)v4 + 13) > 2u )
      {
        memcpy_s(v940, 0x208u, (char *)v4 + v411 + 4, *((unsigned __int16 *)v4 + 13));
        v468 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v860);
        (*(void (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v468 + 104LL))(v468, v940);
      }
      CUT::ObfuscateFilePathW(v940);
      LODWORD(v843) = *((_DWORD *)v4 + 3);
      LODWORD(cchToCopy) = *((_DWORD *)v4 + 2);
      RdpRemoteAppCore::LogRemoteAppEventF(
        (char *)v5 + 16,
        L"WindowCreateRailOrderReceived: WindowId=0x%x, FieldsValidFlags=0x%x, WindowOwnerId=0x%x, Style=0x%08x, StyleEx=0"
         "x%08x, ShowState=%hhu, EnforceServerZOrder=%hhu, TitleBytes=%hu, Title=%s, OffsetX=%i, OffsetY=%i, Width=%i, He"
         "ight=%i, WindowClientDeltaX=%i, WindowClientDeltaY=%i, ResizeMarginLeft=%i, ResizeMarginTop=%i, ResizeMarginRig"
         "ht=%i, ResizeMarginBottom=%i, NumVisibilityRects=%hu",
        0,
        *((unsigned int *)v4 + 1),
        cchToCopy,
        v843,
        *((_DWORD *)v4 + 4),
        *((_DWORD *)v4 + 5),
        *((unsigned __int8 *)v4 + 24),
        *((unsigned __int8 *)v4 + 25),
        *((unsigned __int16 *)v4 + 13),
        v940,
        *((_DWORD *)v4 + 7),
        *((_DWORD *)v4 + 8),
        *((_DWORD *)v4 + 9),
        *((_DWORD *)v4 + 10),
        *((_DWORD *)v4 + 11),
        *((_DWORD *)v4 + 12),
        *((_DWORD *)v4 + 13),
        *((_DWORD *)v4 + 15),
        *((_DWORD *)v4 + 14),
        *((_DWORD *)v4 + 16),
        *((unsigned __int16 *)v4 + 34));
      LODWORD(v878) = *((_DWORD *)v4 + 13);
      if ( (int)v878 >= 0 )
      {
        v469 = *((_DWORD *)v4 + 14);
        if ( v469 >= 0 )
        {
          v470 = *((_DWORD *)v4 + 15);
          if ( v470 >= 0 )
          {
            v471 = *((_DWORD *)v4 + 16);
            if ( v471 >= 0 )
            {
              v472 = (__int64 *)RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v860);
              v873 = (RdpRemoteAppCore *)__PAIR64__(v469, v878);
              v874 = v470;
              v473 = *v472;
              v875 = v471;
              (*(void (__fastcall **)(__int64 *, RdpRemoteAppCore **, _QWORD))(v473 + 336))(v472, &v873, 0);
            }
          }
          v415 = 0;
        }
      }
      v474 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v860);
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v474 + 224LL))(
        v474,
        (unsigned int)(*((_DWORD *)v4 + 7) + *((_DWORD *)v4 + 11)),
        (unsigned int)(*((_DWORD *)v4 + 8) + *((_DWORD *)v4 + 12)));
      v475 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v860);
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v475 + 256LL))(
        v475,
        *((unsigned int *)v4 + 11),
        *((unsigned int *)v4 + 12));
      v933 = *(_OWORD *)((char *)v4 + 28);
      v476 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v860);
      (*(void (__fastcall **)(__int64, __int128 *, _QWORD))(*(_QWORD *)v476 + 248LL))(v476, &v933, 0);
      v479 = (char *)operator new(saturated_mul(*((unsigned __int16 *)v4 + 34), 0x10u));
      if ( v479 )
      {
        if ( *((_WORD *)v4 + 34) )
        {
          do
          {
            v482 = 16LL * v415;
            *(_DWORD *)&v479[v482] = *(_DWORD *)((char *)v4 + v482 + 72);
            *(_DWORD *)&v479[v482 + 4] = *(_DWORD *)((char *)v4 + v482 + 76);
            *(_DWORD *)&v479[v482 + 8] = *((_DWORD *)v4 + 4 * v415 + 20) - *(_DWORD *)((char *)v4 + v482 + 72);
            *(_DWORD *)&v479[v482 + 12] = *(_DWORD *)((char *)v4 + v482 + 84) - *(_DWORD *)((char *)v4 + v482 + 76);
            LODWORD(v859) = *(_DWORD *)((char *)v4 + v482 + 84);
            LODWORD(v857) = *((_DWORD *)v4 + 4 * v415 + 20);
            LODWORD(v855) = *(_DWORD *)((char *)v4 + v482 + 76);
            LODWORD(v850) = *(_DWORD *)((char *)v4 + v482 + 72);
            LODWORD(cchToCopyb) = *((_DWORD *)v4 + 1);
            RdpRemoteAppCore::LogRemoteAppEventF(
              (char *)v5 + 16,
              L"WindowCreateRailOrderReceived_VisibilityRect[%i]: WindowId=0x%x, Left=%i, Top=%i, Right=%i, Bottom=%i",
              0,
              (unsigned int)v415++,
              cchToCopyb,
              v850,
              v855,
              v857,
              v859);
          }
          while ( v415 < *((unsigned __int16 *)v4 + 34) );
        }
        v483 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v860);
        (*(void (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v483 + 176LL))(
          v483,
          *((unsigned __int16 *)v4 + 34),
          v479);
        v484 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v860);
        (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v484 + 160LL))(
          v484,
          *((int *)v4 + 7),
          *((int *)v4 + 8));
        v485 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v860);
        (*(void (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v485 + 168LL))(
          v485,
          *((unsigned __int16 *)v4 + 34),
          v479);
        operator delete(v479);
        if ( RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *((char *)v5 + 136) )
        {
          v486 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *((char *)v5 + 136);
          v487 = *(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v486 + 40LL);
          v488 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v860);
          v489 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v488 + 72LL))(v488);
          v487(v486, v489);
        }
        v490 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v860);
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v490 + 128LL))(v490, *((unsigned __int8 *)v4 + 24));
      }
      else
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v481 = RdpX_GetActivityIdPrefix(v478, v477, v480);
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            136,
            &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
            v481,
            -2147024882);
        }
        RemoteAppWindow = -2147024882;
      }
      goto LABEL_628;
    }
    if ( (_DWORD)v17 != 34 )
    {
      if ( (_DWORD)v17 != 35 )
      {
        if ( (_DWORD)v17 != 36 )
        {
          if ( (_DWORD)v17 != 37 )
          {
            if ( (_DWORD)v17 != 38 )
            {
              if ( (_DWORD)v17 != 39 )
                goto LABEL_1160;
              RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v888);
              if ( *((_WORD *)v4 + 1) != 8 )
              {
                RdpRemoteAppCore::LogRemoteAppError(
                  (char *)v5 + 16,
                  L"Invalid size of TS_RAIL_ORDER_SYNC_STATE_BODY PDU",
                  2147549183LL,
                  0,
                  0);
                if ( *((_WORD *)v4 + 1) != 8 )
                {
                  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                    && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v511 = RdpX_GetActivityIdPrefix(v509, v508, v510);
                    WPP_SF_Dd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      120,
                      &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                      v511,
                      -2147418113);
                  }
                  RemoteAppWindow = -2147418113;
LABEL_738:
                  v512 = v888;
LABEL_739:
                  TCntPtr<ITSViewerRecorder>::SafeRelease(v512);
                  return (unsigned int)RemoteAppWindow;
                }
              }
              RdpRemoteAppCore::LogRemoteAppEventF(
                (char *)v5 + 16,
                L"SyncStateRailOrderReceived: SyncFlags=0x%x",
                0,
                *((unsigned int *)v4 + 1));
              v513 = (struct ITSWndPluginEx **)CacCommon::Rect<int>::Rect<int>(v888);
              RemoteAppWindow = RdpRemoteAppCore::GetWndPlugin((RdpRemoteAppCore *)((char *)v5 - 48), v513);
              if ( RemoteAppWindow < 0 )
              {
                if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                  && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v517 = RdpX_GetActivityIdPrefix(v515, v514, v516);
                  WPP_SF_DsD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    121,
                    (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                    v517,
                    (__int64)"GetWndPlugin failed",
                    RemoteAppWindow);
                }
                goto LABEL_738;
              }
              if ( (*((_BYTE *)v4 + 4) & 1) != 0 )
              {
                if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                  && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
                {
                  v518 = RdpX_GetActivityIdPrefix(v515, v514, v516);
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    122,
                    &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                    v518);
                }
                v519 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v888);
                v520 = 0;
              }
              else
              {
                if ( (*((_BYTE *)v4 + 4) & 2) == 0 )
                  goto LABEL_774;
                v521 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                  && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
                {
                  v522 = RdpX_GetActivityIdPrefix(v515, v514, v516);
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    123,
                    &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                    v522);
                  v521 = WPP_GLOBAL_Control;
                }
                if ( (*((_BYTE *)v4 + 4) & 8) != 0 )
                {
                  if ( v521 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v521[7] & 1) != 0 && *((_BYTE *)v521 + 25) >= 3u )
                  {
                    v523 = RdpX_GetActivityIdPrefix(v515, v514, v516);
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      124,
                      &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                      v523);
                  }
                  v524 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v888);
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v524 + 120LL))(v524);
                  if ( (unsigned int)RdpRemoteAppCore::IsRemoteAppV2Enabled((char *)v5 + 16) )
                  {
                    v525 = (RdpRemoteAppCore *)((char *)v5 + 128);
                    v873 = (RdpRemoteAppCore *)((char *)v5 + 128);
                    v526 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *((char *)v5 + 128);
                    LODWORD(v878) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v526 + 120LL))(v526);
                    v527 = 0;
                    if ( (_DWORD)v878 )
                    {
                      while ( 1 )
                      {
                        RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v927);
                        v528 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v525);
                        v529 = *(__int64 (__fastcall **)(__int64, _QWORD, void *))(*(_QWORD *)v528 + 128LL);
                        v530 = CacCommon::Rect<int>::Rect<int>(v927);
                        v533 = v529(v528, v527, v530);
                        if ( v533 )
                          break;
                        v535 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v927);
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v535 + 384LL))(v535);
                        RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v927);
                        v525 = v873;
                        if ( ++v527 >= (unsigned int)v878 )
                          goto LABEL_772;
                      }
                      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                        && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                      {
                        v536 = RdpX_GetActivityIdPrefix(v532, v531, v534);
                        WPP_SF_DLD(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          125,
                          &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                          v536,
                          v533,
                          v533);
                      }
                      RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v927);
                      goto LABEL_738;
                    }
                  }
                }
                else
                {
                  v537 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v888);
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v537 + 144LL))(v537);
                }
LABEL_772:
                v519 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v888);
                v520 = 1;
              }
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v519 + 112LL))(v519, v520);
LABEL_774:
              if ( (*((_BYTE *)v4 + 4) & 4) != 0 )
              {
                if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                  && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
                {
                  v538 = RdpX_GetActivityIdPrefix(v515, v514, v516);
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    126,
                    &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                    v538);
                }
                v539 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v888);
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v539 + 128LL))(v539);
              }
              goto LABEL_738;
            }
            RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v917);
            if ( *((_WORD *)v4 + 1) >= 0x14u
              || (RdpRemoteAppCore::LogRemoteAppError(
                    (char *)v5 + 16,
                    L"Invalid size of TS_RAIL_ORDER_ZORDER_BODY PDU",
                    2147549183LL,
                    0,
                    0),
                  *((_WORD *)v4 + 1) >= 0x14u) )
            {
              if ( *((_DWORD *)v4 + 1) > 0x100u )
                RdpRemoteAppCore::LogRemoteAppError(
                  (char *)v5 + 16,
                  L"numWindows in TS_RAIL_ORDER_ZORDER_BODY PDU is unexpectedly big",
                  2147549183LL,
                  0,
                  0);
              v545 = *((_DWORD *)v4 + 1);
              if ( v545 <= 0x100 )
              {
                v546 = 4 * v545 + 16;
                if ( *((unsigned __int16 *)v4 + 1) < v546 )
                  RdpRemoteAppCore::LogRemoteAppError(
                    (char *)v5 + 16,
                    L"Invalid size of TS_RAIL_ORDER_ZORDER_BODY PDU",
                    2147549183LL,
                    0,
                    0);
                if ( *((unsigned __int16 *)v4 + 1) >= v546 )
                {
                  memset_0(v942, 0, 0x208u);
                  v547 = v942;
                  v548 = 260;
                  v928 = v942;
                  v929 = 260;
                  v549 = *((_DWORD *)v4 + 1);
                  if ( v549 )
                  {
                    v550 = 0;
                    v551 = 0;
                    while ( 1 )
                    {
                      v552 = v549;
                      if ( v550 < 0 )
                        break;
                      v553 = L"0x%x,";
                      if ( v551 >= v549 - 1 )
                        v553 = L"0x%x";
                      LODWORD(v853) = *((_DWORD *)v4 + v551 + 4);
                      v550 = StringCchPrintfExW(v547, v548, &v928, &v929, 0, v553, v853);
                      if ( v550 < 0
                        && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                      {
                        v557 = RdpX_GetActivityIdPrefix(v555, v554, v556);
                        LODWORD(v843) = v550;
                        WPP_SF_DsD(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          209,
                          (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                          v557,
                          (__int64)"StringCchPrintfEx failed",
                          v843);
                      }
                      v549 = *((_DWORD *)v4 + 1);
                      ++v551;
                      v552 = v549;
                      if ( v551 >= v549 )
                        break;
                      v547 = v928;
                      v548 = v929;
                    }
                  }
                  else
                  {
                    v552 = 0;
                  }
                  LODWORD(v843) = *((_DWORD *)v4 + 3);
                  LODWORD(cchToCopy) = *((_DWORD *)v4 + 2);
                  RdpRemoteAppCore::LogRemoteAppEventF(
                    (char *)v5 + 16,
                    L"ZOrderRailOrderReceived: NumWindows=%u, FieldsValidFlags=0x%x, ActiveWindowId=0x%x, WindowIds=[%s]",
                    0,
                    v552,
                    cchToCopy,
                    v843,
                    v942);
                  v558 = (struct ITSWndPluginEx **)CacCommon::Rect<int>::Rect<int>(v917);
                  RemoteAppWindow = RdpRemoteAppCore::GetWndPlugin((RdpRemoteAppCore *)((char *)v5 - 48), v558);
                  if ( RemoteAppWindow >= 0 )
                  {
                    v563 = (*((_DWORD *)v4 + 2) >> 4) & 2 | 1;
                    if ( (*((_BYTE *)v4 + 8) & 0x10) == 0 )
                      v563 = (*((_DWORD *)v4 + 2) >> 4) & 2;
                    if ( v563 )
                    {
                      v564 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v917);
                      (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, __int64))(*(_QWORD *)v564 + 104LL))(
                        v564,
                        v563,
                        *((unsigned int *)v4 + 3),
                        *((unsigned int *)v4 + 1),
                        (__int64)v4 + 16);
                    }
                  }
                  else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                         && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v562 = RdpX_GetActivityIdPrefix(v560, v559, v561);
                    LODWORD(v851) = RemoteAppWindow;
                    WPP_SF_DsD(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      210,
                      (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                      v562,
                      (__int64)"GetWndPlugin failed",
                      v851);
                  }
                  goto LABEL_788;
                }
                if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                  || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
LABEL_787:
                  RemoteAppWindow = -2147418113;
LABEL_788:
                  v512 = v917;
                  goto LABEL_739;
                }
                v543 = RdpX_GetActivityIdPrefix(v541, v540, v542);
                v544 = 208;
              }
              else
              {
                if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                  || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_787;
                }
                v543 = RdpX_GetActivityIdPrefix(v541, v540, v542);
                v544 = 207;
              }
            }
            else
            {
              if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_787;
              }
              v543 = RdpX_GetActivityIdPrefix(v541, v540, v542);
              v544 = 206;
            }
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v544,
              &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v543,
              -2147418113);
            goto LABEL_787;
          }
          RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v889);
          RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v918);
          if ( *((_WORD *)v4 + 1) != 12 )
          {
            RdpRemoteAppCore::LogRemoteAppError(
              (char *)v5 + 16,
              L"Invalid size of TS_RAIL_ORDER_NOTIFYICON_DELETE PDU",
              2147549183LL,
              0,
              0);
            if ( *((_WORD *)v4 + 1) != 12 )
            {
              if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v568 = RdpX_GetActivityIdPrefix(v566, v565, v567);
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  202,
                  &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                  v568,
                  -2147418113);
              }
              RemoteAppWindow = -2147418113;
              goto LABEL_832;
            }
          }
          LODWORD(cchToCopy) = *((_DWORD *)v4 + 2);
          RdpRemoteAppCore::LogRemoteAppEventF(
            (char *)v5 + 16,
            L"NotifyIconDeleteRailOrderReceived: WindowId=0x%x, NotifyIconId=0x%x",
            0,
            *((unsigned int *)v4 + 1),
            cchToCopy);
          v570 = (struct ITSWndPluginEx **)CacCommon::Rect<int>::Rect<int>(v918);
          RemoteAppWindow = RdpRemoteAppCore::GetWndPlugin((RdpRemoteAppCore *)((char *)v5 - 48), v570);
          if ( RemoteAppWindow >= 0 )
          {
            v577 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v918);
            v578 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, void *))(*(_QWORD *)v577 + 72LL);
            v579 = CacCommon::Rect<int>::Rect<int>(v889);
            RemoteAppWindow = v578(v577, *((unsigned int *)v4 + 1), *((unsigned int *)v4 + 2), v579);
            if ( RemoteAppWindow >= 0 )
            {
              v583 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v889);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v583 + 128LL))(v583);
              v584 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v889);
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v584 + 120LL))(v584, 2);
              v585 = (struct RdpXInterfaceShellNotifyInformation *)RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v889);
              v586 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v889);
              v587 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v586 + 72LL))(v586);
              RemoteAppWindow = RdpRemoteAppCore::OnShellNotifyInformation(v873, v587, v585);
              if ( RemoteAppWindow >= 0
                || WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_832;
              }
              v574 = RdpX_GetActivityIdPrefix(v589, v588, v590);
              v575 = 205;
              v576 = "OnShellNotifyInformation failed";
            }
            else
            {
              if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_832;
              }
              v574 = RdpX_GetActivityIdPrefix(v581, v580, v582);
              v575 = 204;
              v576 = "FindShellNotifyInfo failed";
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
              || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_832;
            }
            v574 = RdpX_GetActivityIdPrefix(v572, v571, v573);
            v575 = 203;
            v576 = "GetWndPlugin failed";
          }
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v575,
            (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
            v574,
            (__int64)v576,
            RemoteAppWindow);
LABEL_832:
          TCntPtr<ITSViewerRecorder>::SafeRelease(v918);
          v569 = v889;
LABEL_1025:
          RdpXSPtr<RdpXTapVcCallbackItem>::SafeRelease(v569);
          return (unsigned int)RemoteAppWindow;
        }
        RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v877);
        RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v882);
        if ( *((_WORD *)v4 + 1) < 0x14u )
          RdpRemoteAppCore::LogRemoteAppError(
            (char *)v5 + 16,
            L"Invalid size of TS_RAIL_ORDER_NOTIFYICON_TOAST_BODY",
            2147549183LL,
            0,
            0);
        v593 = *((unsigned __int16 *)v4 + 1);
        if ( (unsigned int)v593 < 0x14 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_857;
          }
          v594 = RdpX_GetActivityIdPrefix(v591, v593, v592);
          v595 = 194;
LABEL_856:
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v595,
            &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
            v594,
            -2147418113);
LABEL_857:
          RemoteAppWindow = -2147418113;
LABEL_858:
          TCntPtr<ITSViewerRecorder>::SafeRelease(v882);
          v569 = v877;
          goto LABEL_1025;
        }
        v596 = *((unsigned __int16 *)v4 + 8);
        v597 = v596 + *((unsigned __int16 *)v4 + 9) + 20;
        if ( (unsigned int)v593 < v597 )
          RdpRemoteAppCore::LogRemoteAppError(
            (char *)v5 + 16,
            L"Invalid size of TS_RAIL_ORDER_NOTIFYICON_TOAST_BODY PDU",
            2147549183LL,
            0,
            0);
        if ( *((unsigned __int16 *)v4 + 1) < v597 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_857;
          }
          v594 = RdpX_GetActivityIdPrefix(v596, v593, v592);
          v595 = 195;
          goto LABEL_856;
        }
        v598 = (struct ITSWndPluginEx **)CacCommon::Rect<int>::Rect<int>(v882);
        RemoteAppWindow = RdpRemoteAppCore::GetWndPlugin((RdpRemoteAppCore *)((char *)v5 - 48), v598);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_858;
          }
          v602 = RdpX_GetActivityIdPrefix(v600, v599, v601);
          v603 = 196;
          v604 = "GetWndPlugin failed";
          goto LABEL_871;
        }
        v605 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v882);
        v606 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, void *))(*(_QWORD *)v605 + 72LL);
        v607 = CacCommon::Rect<int>::Rect<int>(v877);
        RemoteAppWindow = v606(v605, *((unsigned int *)v4 + 1), *((unsigned int *)v4 + 2), v607);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_858;
          }
          v602 = RdpX_GetActivityIdPrefix(v609, v608, v610);
          v603 = 197;
          v604 = "FindShellNotifyInfo failed";
LABEL_871:
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v603,
            (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
            v602,
            (__int64)v604,
            RemoteAppWindow);
          goto LABEL_858;
        }
        v611 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v877);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v611 + 128LL))(v611);
        v612 = *((unsigned __int16 *)v4 + 8);
        v613 = (char *)v4 + 20;
        RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v908);
        v614 = CacCommon::Rect<int>::Rect<int>(v908);
        ConstXChar16StringWithSpecifiedSize = RdpX_Strings_CreateConstXChar16StringWithSpecifiedSize(
                                                *((unsigned __int16 *)v4 + 8) >> 1,
                                                (char *)v4 + 20,
                                                v614);
        RemoteAppWindow = MapXResultToHR(ConstXChar16StringWithSpecifiedSize);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v619 = RdpX_GetActivityIdPrefix(v617, v616, v618);
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              198,
              (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v619,
              (__int64)"RdpX_Strings_CreateConstXChar16StringWithSpecifiedSize failed",
              RemoteAppWindow);
          }
          goto LABEL_882;
        }
        v620 = &v613[v612];
        RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v919);
        v621 = CacCommon::Rect<int>::Rect<int>(v919);
        v622 = RdpX_Strings_CreateConstXChar16StringWithSpecifiedSize(
                 *((unsigned __int16 *)v4 + 9) >> 1,
                 &v613[v612],
                 v621);
        RemoteAppWindow = MapXResultToHR(v622);
        if ( RemoteAppWindow >= 0 )
        {
          v629 = &sourceString;
          if ( RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v919) )
          {
            v630 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v919);
            v631 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v630 + 24LL))(v630);
          }
          else
          {
            v631 = &sourceString;
          }
          if ( RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v908) )
          {
            v632 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v908);
            v629 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v632 + 24LL))(v632);
          }
          LODWORD(cchToCopy) = *((_DWORD *)v4 + 2);
          RdpRemoteAppCore::LogRemoteAppEventF(
            (char *)v873 + 16,
            L"NotifyIconToastRailOrderReceived: WindowId=0x%x, NotifyIconId=0x%x, ToastFlags=0x%x, Toast=%s, ToastTitle=%s",
            0,
            *((unsigned int *)v4 + 1),
            cchToCopy,
            *((_DWORD *)v4 + 3),
            v629,
            v631);
          v633 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v877);
          LOWORD(v852) = *((_WORD *)v4 + 9) >> 1;
          RemoteAppWindow = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, __int64, int, char *))(*(_QWORD *)v633 + 96LL))(
                              v633,
                              0,
                              *((unsigned int *)v4 + 3),
                              *((_WORD *)v4 + 8) >> 1,
                              (__int64)v4 + 20,
                              v852,
                              v620);
          if ( RemoteAppWindow >= 0 )
          {
            v637 = (struct RdpXInterfaceShellNotifyInformation *)RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v877);
            v638 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v877);
            v639 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v638 + 72LL))(v638);
            RemoteAppWindow = RdpRemoteAppCore::OnShellNotifyInformation(v873, v639, v637);
            if ( RemoteAppWindow >= 0
              || WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
              || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_889;
            }
            v626 = RdpX_GetActivityIdPrefix(v641, v640, v642);
            v627 = 201;
            v628 = "OnShellNotifyInformation failed";
          }
          else
          {
            if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
              || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_889;
            }
            v626 = RdpX_GetActivityIdPrefix(v635, v634, v636);
            v627 = 200;
            v628 = "spShellNotify->SetInfo failed";
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_889;
          }
          v626 = RdpX_GetActivityIdPrefix(v624, v623, v625);
          v627 = 199;
          v628 = "RdpX_Strings_CreateConstXChar16StringWithSpecifiedSize failed";
        }
        LODWORD(v843) = RemoteAppWindow;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v627,
          (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v626,
          (__int64)v628,
          v843);
LABEL_889:
        RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v919);
LABEL_882:
        RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v908);
        goto LABEL_858;
      }
      RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v862);
      RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v869);
      if ( *((_WORD *)v4 + 1) < 0x18u )
        RdpRemoteAppCore::LogRemoteAppError(
          (char *)v5 + 16,
          L"Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Change PDU",
          2147549183LL,
          0,
          0);
      v645 = *((unsigned __int16 *)v4 + 1);
      if ( (unsigned int)v645 < 0x18 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_913;
        }
        v646 = RdpX_GetActivityIdPrefix(v645, v643, v644);
        v647 = 180;
LABEL_912:
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v647,
          &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v646,
          -2147418113);
LABEL_913:
        RemoteAppWindow = -2147418113;
LABEL_914:
        TCntPtr<ITSViewerRecorder>::SafeRelease(v869);
        v569 = v862;
        goto LABEL_1025;
      }
      v648 = *((unsigned __int16 *)v4 + 6) + 24;
      if ( (unsigned int)v645 < v648 )
        RdpRemoteAppCore::LogRemoteAppError(
          (char *)v5 + 16,
          L"Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Change PDU",
          2147549183LL,
          0,
          0);
      if ( *((unsigned __int16 *)v4 + 1) < v648 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_913;
        }
        v646 = RdpX_GetActivityIdPrefix(v645, v643, v644);
        v647 = 181;
        goto LABEL_912;
      }
      v649 = (struct ITSWndPluginEx **)CacCommon::Rect<int>::Rect<int>(v869);
      RemoteAppWindow = RdpRemoteAppCore::GetWndPlugin((RdpRemoteAppCore *)((char *)v5 - 48), v649);
      if ( RemoteAppWindow < 0 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_914;
        }
        v653 = RdpX_GetActivityIdPrefix(v651, v650, v652);
        v654 = 182;
        v655 = "GetWndPlugin failed";
        goto LABEL_927;
      }
      v656 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v869);
      v657 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, void *))(*(_QWORD *)v656 + 72LL);
      v658 = CacCommon::Rect<int>::Rect<int>(v862);
      v659 = v657(v656, *((unsigned int *)v4 + 1), *((unsigned int *)v4 + 2), v658);
      v663 = 0;
      RemoteAppWindow = v659;
      if ( v659 < 0 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_914;
        }
        v653 = RdpX_GetActivityIdPrefix(v661, v660, v662);
        v654 = 183;
        v655 = "FindShellNotifyInfo failed";
LABEL_927:
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v654,
          (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v653,
          (__int64)v655,
          RemoteAppWindow);
        goto LABEL_914;
      }
      v664 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v862);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v664 + 128LL))(v664);
      RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v871);
      if ( *((_WORD *)v4 + 6) )
      {
        v665 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v862);
        RemoteAppWindow = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v665 + 88LL))(
                            v665,
                            *((_WORD *)v4 + 6) >> 1,
                            (__int64)v4 + 24);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_940;
          }
          v669 = RdpX_GetActivityIdPrefix(v667, v666, v668);
          v670 = 184;
          v671 = "CreateShellNotifyInfo->SetTip failed";
          goto LABEL_939;
        }
        v672 = CacCommon::Rect<int>::Rect<int>(v871);
        v673 = RdpX_Strings_CreateConstXChar16StringWithSpecifiedSize(
                 *((unsigned __int16 *)v4 + 6) >> 1,
                 (char *)v4 + 24,
                 v672);
        RemoteAppWindow = MapXResultToHR(v673);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_940;
          }
          v669 = RdpX_GetActivityIdPrefix(v675, v674, v676);
          v670 = 185;
          v671 = "RdpX_Strings_CreateConstXChar16StringWithSpecifiedSize failed";
          goto LABEL_939;
        }
      }
      if ( (*((_BYTE *)v4 + 20) & 4) != 0 )
      {
        v677 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v862);
        RemoteAppWindow = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v677 + 104LL))(
                            v677,
                            *((unsigned int *)v4 + 4));
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_940;
          }
          v669 = RdpX_GetActivityIdPrefix(v679, v678, v680);
          v670 = 186;
          v671 = "CreateShellNotifyInfo->SetWSNState failed";
          goto LABEL_939;
        }
      }
      if ( *((_BYTE *)v4 + 14) )
      {
        RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v890);
        v684 = *((unsigned __int16 *)v4 + 6);
        v685 = *((unsigned __int16 *)v4 + 1);
        if ( *((_BYTE *)v4 + 15) )
        {
          v686 = v648 + 4;
          v687 = v873;
          if ( v685 < v686 )
            RdpRemoteAppCore::LogRemoteAppError(
              (char *)v873 + 16,
              L"Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Create PDU",
              2147549183LL,
              0,
              0);
          if ( *((unsigned __int16 *)v4 + 1) < v686 )
          {
            if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
              || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_962;
            }
            v688 = RdpX_GetActivityIdPrefix(v682, v681, v683);
            v689 = 187;
LABEL_961:
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v689,
              &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v688,
              -2147418113);
LABEL_962:
            RemoteAppWindow = -2147418113;
LABEL_963:
            RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v890);
            goto LABEL_940;
          }
          v690 = *((unsigned __int8 *)v4 + v684 + 27);
          LODWORD(v878) = *((unsigned __int8 *)v4 + v684 + 26);
          v863 = *(unsigned __int16 *)((char *)v4 + v684 + 24);
          if ( RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v871) )
          {
            v691 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v871);
            v692 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v691 + 24LL))(v691);
          }
          else
          {
            v692 = &sourceString;
          }
          LODWORD(cchToCopy) = *((_DWORD *)v4 + 2);
          RdpRemoteAppCore::LogRemoteAppEventF(
            (char *)v687 + 16,
            L"NotifyIconChangeRailOrderReceived_Cached: WindowId=0x%x, NotifyIconId=0x%x, NumIcons=%hhu, IsCachedIcon=%hhu"
             ", StateFlags=0x%x, PDUFlags=0x%x, ToolTipBytes=%hu, ToolTip=%s, CacheEntry=0x%hx, CacheId=0x%hhx, IconFlags=0x%hhx",
            0,
            *((unsigned int *)v4 + 1),
            cchToCopy,
            *((unsigned __int8 *)v4 + 14),
            *((unsigned __int8 *)v4 + 15),
            *((_DWORD *)v4 + 4),
            *((_DWORD *)v4 + 5),
            *((unsigned __int16 *)v4 + 6),
            v692,
            v863,
            v878,
            v690);
          v693 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v869);
          v694 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, void *))(*(_QWORD *)v693 + 56LL);
          v695 = CacCommon::Rect<int>::Rect<int>(v890);
          RemoteAppWindow = v694(
                              v693,
                              *((unsigned __int8 *)v4 + v684 + 26),
                              *(unsigned __int16 *)((char *)v4 + v684 + 24),
                              v695);
          if ( RemoteAppWindow < 0 )
          {
            if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
              || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_963;
            }
            v699 = RdpX_GetActivityIdPrefix(v697, v696, v698);
            v700 = 188;
            goto LABEL_972;
          }
        }
        else
        {
          v702 = v648 + 20;
          v687 = v873;
          if ( v685 < v702 )
            RdpRemoteAppCore::LogRemoteAppError(
              (char *)v873 + 16,
              L"Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Change PDU",
              2147549183LL,
              0,
              0);
          v703 = *((unsigned __int16 *)v4 + 1);
          if ( (unsigned int)v703 < v702 )
          {
            if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
              || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_962;
            }
            v688 = RdpX_GetActivityIdPrefix(v682, v703, v683);
            v689 = 189;
            goto LABEL_961;
          }
          if ( (*((_BYTE *)v4 + v684 + 27) & 2) != 0 )
          {
            LOBYTE(v682) = *((_BYTE *)v4 + v684 + 32);
            v663 = *(_WORD *)((char *)v4 + v684 + 34);
            LOWORD(v863) = v682;
          }
          else
          {
            LOWORD(v863) = 32;
          }
          v704 = *(unsigned int *)((char *)v4 + v684 + 36);
          v705 = v663;
          v706 = v663 + *(_DWORD *)((char *)v4 + v684 + 40);
          v883 = v704;
          v884 = v663;
          v707 = v704 + v706 + v702;
          if ( (unsigned int)v703 < v707 )
            RdpRemoteAppCore::LogRemoteAppError(
              (char *)v687 + 16,
              L"Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Change PDU",
              2147549183LL,
              0,
              0);
          if ( *((unsigned __int16 *)v4 + 1) < v707 )
          {
            if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
              || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_962;
            }
            v688 = RdpX_GetActivityIdPrefix(v705, v703, v704);
            v689 = 190;
            goto LABEL_961;
          }
          v873 = (struct tagTS_RAIL_PDU *)((char *)v4 + v684 + v663 + 44);
          LODWORD(v878) = *(_DWORD *)((char *)v4 + v684 + 40);
          v914 = *(_DWORD *)((char *)v4 + v684 + 36);
          v910 = *(unsigned __int16 *)((char *)v4 + v684 + 34);
          v911 = *((unsigned __int8 *)v4 + v684 + 32);
          v912 = *(unsigned __int16 *)((char *)v4 + v684 + 30);
          v913 = *(unsigned __int16 *)((char *)v4 + v684 + 28);
          v916 = *((unsigned __int8 *)v4 + v684 + 27);
          v915 = *((unsigned __int8 *)v4 + v684 + 26);
          v885 = *(unsigned __int16 *)((char *)v4 + v684 + 24);
          if ( RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v871) )
          {
            v708 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v871);
            v709 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v708 + 24LL))(v708);
          }
          else
          {
            v709 = &sourceString;
          }
          LODWORD(cchToCopy) = *((_DWORD *)v4 + 2);
          RdpRemoteAppCore::LogRemoteAppEventF(
            (char *)v687 + 16,
            L"NotifyIconChangeRailOrderReceived_NonCached: WindowId=0x%x, NotifyIconId=0x%x, NumIcons=%hhu, IsCachedIcon=%"
             "hhu,StateFlags=0x%x, PDUFlags=0x%x, ToolTipBytes=%hu, ToolTip=%s, CacheEntry=0x%hx, CacheId=0x%hhx, IconFla"
             "gs=0x%hhx, Width=%hu, Height=%hu, Bpp=%hhu, ColorTableBytes=%hu, BitsMaskBytes=%u, BitsColorBytes=%u",
            0,
            *((unsigned int *)v4 + 1),
            cchToCopy,
            *((unsigned __int8 *)v4 + 14),
            *((unsigned __int8 *)v4 + 15),
            *((_DWORD *)v4 + 4),
            *((_DWORD *)v4 + 5),
            *((unsigned __int16 *)v4 + 6),
            v709,
            v885,
            v915,
            v916,
            v913,
            v912,
            v911,
            v910,
            v914,
            v878);
          v710 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v869);
          v711 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, char *, _DWORD, _DWORD, char *, int, RdpRemoteAppCore *, _DWORD, char *, _DWORD, void *))(*(_QWORD *)v710 + 64LL);
          v712 = CacCommon::Rect<int>::Rect<int>(v890);
          v713 = (char *)v873 + v883;
          LOBYTE(v713) = v863;
          RemoteAppWindow = v711(
                              v710,
                              *((unsigned __int8 *)v4 + v684 + 26),
                              *(unsigned __int16 *)((char *)v4 + v684 + 24),
                              v713,
                              *(unsigned __int16 *)((char *)v4 + v684 + 28),
                              *(unsigned __int16 *)((char *)v4 + v684 + 30),
                              (char *)v4 + v684 + 44,
                              v884,
                              v873,
                              *(_DWORD *)((char *)v4 + v684 + 36),
                              (char *)v873 + v883,
                              *(_DWORD *)((char *)v4 + v684 + 40),
                              v712);
          if ( RemoteAppWindow < 0 )
          {
            if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
              || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_963;
            }
            v699 = RdpX_GetActivityIdPrefix(v715, v714, v716);
            v700 = 191;
LABEL_972:
            v701 = "CreateCachedIcon failed";
LABEL_973:
            LODWORD(v843) = RemoteAppWindow;
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v700,
              (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v699,
              (__int64)v701,
              v843);
            goto LABEL_963;
          }
        }
        v717 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v862);
        v718 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v717 + 80LL);
        v719 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v890);
        RemoteAppWindow = v718(v717, v719);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_963;
          }
          v699 = RdpX_GetActivityIdPrefix(v721, v720, v722);
          v700 = 192;
          v701 = "spShellNotify->SetIcon failed";
          goto LABEL_973;
        }
        RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v890);
      }
      else
      {
        v687 = v873;
        if ( RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v871) )
        {
          v723 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v871);
          v724 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v723 + 24LL))(v723);
        }
        else
        {
          v724 = &sourceString;
        }
        LODWORD(cchToCopy) = *((_DWORD *)v4 + 2);
        RdpRemoteAppCore::LogRemoteAppEventF(
          (char *)v687 + 16,
          L"NotifyIconChangeRailOrderReceived_NoIcons: WindowId=0x%x, NotifyIconId=0x%x, NumIcons=%hhu, IsCachedIcon=%hhu,"
           " StateFlags=0x%x, PDUFlags=0x%x, ToolTipBytes=%hu, ToolTip=%s",
          0,
          *((unsigned int *)v4 + 1),
          cchToCopy,
          *((unsigned __int8 *)v4 + 14),
          *((unsigned __int8 *)v4 + 15),
          *((_DWORD *)v4 + 4),
          *((_DWORD *)v4 + 5),
          *((unsigned __int16 *)v4 + 6),
          v724);
      }
      v725 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v862);
      if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v725 + 72LL))(v725) )
        goto LABEL_940;
      v726 = (struct RdpXInterfaceShellNotifyInformation *)RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v862);
      v727 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v862);
      v728 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v727 + 72LL))(v727);
      RemoteAppWindow = RdpRemoteAppCore::OnShellNotifyInformation(v687, v728, v726);
      if ( RemoteAppWindow >= 0
        || WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_940;
      }
      v669 = RdpX_GetActivityIdPrefix(v730, v729, v731);
      v670 = 193;
      v671 = "OnShellNotifyInformation failed";
LABEL_939:
      LODWORD(v843) = RemoteAppWindow;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v670,
        (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
        v669,
        (__int64)v671,
        v843);
LABEL_940:
      RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v871);
      goto LABEL_914;
    }
    RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v861);
    RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v864);
    if ( *((_WORD *)v4 + 1) < 0x18u )
      RdpRemoteAppCore::LogRemoteAppError(
        (char *)v5 + 16,
        L"Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Create PDU",
        2147549183LL,
        0,
        0);
    v734 = *((unsigned __int16 *)v4 + 1);
    if ( (unsigned int)v734 < 0x18 )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_1023;
      }
      v735 = RdpX_GetActivityIdPrefix(v734, v732, v733);
      v736 = 165;
LABEL_1022:
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v736,
        &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
        v735,
        -2147418113);
LABEL_1023:
      RemoteAppWindow = -2147418113;
LABEL_1024:
      TCntPtr<ITSViewerRecorder>::SafeRelease(v864);
      v569 = v861;
      goto LABEL_1025;
    }
    v737 = *((unsigned __int16 *)v4 + 6) + 24;
    if ( (unsigned int)v734 < v737 )
      RdpRemoteAppCore::LogRemoteAppError(
        (char *)v5 + 16,
        L"Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Create PDU",
        2147549183LL,
        0,
        0);
    if ( *((unsigned __int16 *)v4 + 1) < v737 )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_1023;
      }
      v735 = RdpX_GetActivityIdPrefix(v734, v732, v733);
      v736 = 166;
      goto LABEL_1022;
    }
    v738 = (struct ITSWndPluginEx **)CacCommon::Rect<int>::Rect<int>(v864);
    RemoteAppWindow = RdpRemoteAppCore::GetWndPlugin((RdpRemoteAppCore *)((char *)v5 - 48), v738);
    if ( RemoteAppWindow < 0 )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_1024;
      }
      v742 = RdpX_GetActivityIdPrefix(v740, v739, v741);
      v743 = 167;
      v744 = "GetWndPlugin failed";
      goto LABEL_1038;
    }
    v745 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v864);
    v746 = *(int (__fastcall **)(__int64, _QWORD, _QWORD, void *))(*(_QWORD *)v745 + 72LL);
    v747 = CacCommon::Rect<int>::Rect<int>(v861);
    if ( v746(v745, *((unsigned int *)v4 + 1), *((unsigned int *)v4 + 2), v747) >= 0 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v758 = *((_DWORD *)v4 + 2);
        v759 = *((_DWORD *)v4 + 1);
        v760 = RdpX_GetActivityIdPrefix(v749, v748, v750);
        WPP_SF_DLD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          169,
          &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v760,
          v759,
          v758);
      }
      v761 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v861);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v761 + 128LL))(v761);
    }
    else
    {
      v751 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v864);
      v752 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, void *))(*(_QWORD *)v751 + 80LL);
      v753 = CacCommon::Rect<int>::Rect<int>(v861);
      RemoteAppWindow = v752(v751, *((unsigned int *)v4 + 1), *((unsigned int *)v4 + 2), v753);
      if ( RemoteAppWindow < 0 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_1024;
        }
        v742 = RdpX_GetActivityIdPrefix(v755, v754, v756);
        v743 = 168;
        v744 = "CreateShellNotifyInfo failed";
LABEL_1038:
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v743,
          (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v742,
          (__int64)v744,
          RemoteAppWindow);
        goto LABEL_1024;
      }
      v757 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v861);
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v757 + 120LL))(v757, 1);
    }
    v762 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v864);
    if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v762 + 136LL))(v762) )
    {
      v763 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v861);
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v763 + 136LL))(v763, 2);
    }
    v764 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v861);
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v764 + 112LL))(v764, 4);
    RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v872);
    if ( *((_WORD *)v4 + 6) )
    {
      v765 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v861);
      RemoteAppWindow = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v765 + 88LL))(
                          v765,
                          *((_WORD *)v4 + 6) >> 1,
                          (__int64)v4 + 24);
      if ( RemoteAppWindow < 0 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_1060;
        }
        v769 = RdpX_GetActivityIdPrefix(v767, v766, v768);
        v770 = 170;
        v771 = "CreateShellNotifyInfo->SetTip failed";
        goto LABEL_1059;
      }
      v772 = CacCommon::Rect<int>::Rect<int>(v872);
      v773 = RdpX_Strings_CreateConstXChar16StringWithSpecifiedSize(
               *((unsigned __int16 *)v4 + 6) >> 1,
               (char *)v4 + 24,
               v772);
      RemoteAppWindow = MapXResultToHR(v773);
      if ( RemoteAppWindow < 0 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_1060;
        }
        v769 = RdpX_GetActivityIdPrefix(v775, v774, v776);
        v770 = 171;
        v771 = "RdpX_Strings_CreateConstXChar16StringWithSpecifiedSize failed";
        goto LABEL_1059;
      }
    }
    if ( (*((_BYTE *)v4 + 20) & 4) != 0 )
    {
      v777 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v861);
      RemoteAppWindow = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v777 + 104LL))(
                          v777,
                          *((unsigned int *)v4 + 4));
      if ( RemoteAppWindow < 0 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_1060;
        }
        v769 = RdpX_GetActivityIdPrefix(v779, v778, v780);
        v770 = 172;
        v771 = "CreateShellNotifyInfo->SetWSNState failed";
        goto LABEL_1059;
      }
    }
    if ( *((_BYTE *)v4 + 14) )
    {
      RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v891);
      v784 = *((unsigned __int16 *)v4 + 6);
      v785 = *((unsigned __int16 *)v4 + 1);
      if ( *((_BYTE *)v4 + 15) )
      {
        v786 = v737 + 4;
        v787 = v873;
        if ( v785 < v786 )
          RdpRemoteAppCore::LogRemoteAppError(
            (char *)v873 + 16,
            L"Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Create PDU",
            2147549183LL,
            0,
            0);
        if ( *((unsigned __int16 *)v4 + 1) < v786 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_1082;
          }
          v788 = RdpX_GetActivityIdPrefix(v782, v781, v783);
          v789 = 173;
LABEL_1081:
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v789,
            &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
            v788,
            -2147418113);
LABEL_1082:
          RemoteAppWindow = -2147418113;
LABEL_1083:
          RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v891);
          goto LABEL_1060;
        }
        v884 = *((unsigned __int8 *)v4 + v784 + 27);
        v883 = *((unsigned __int8 *)v4 + v784 + 26);
        v885 = *(unsigned __int16 *)((char *)v4 + v784 + 24);
        if ( RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v872) )
        {
          v790 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v872);
          v791 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v790 + 24LL))(v790);
        }
        else
        {
          v791 = &sourceString;
        }
        LODWORD(v843) = *((unsigned __int8 *)v4 + 14);
        LODWORD(cchToCopy) = *((_DWORD *)v4 + 2);
        RdpRemoteAppCore::LogRemoteAppEventF(
          (char *)v787 + 16,
          L"NotifyIconCreateRailOrderReceived_Cached: WindowId=0x%x, NotifyIconId=0x%x, NumIcons=%hhu, IsCachedIcon=%hhu, "
           "StateFlags=0x%x, PDUFlags=0x%x, ToolTipBytes=%hu, ToolTip=%s, CacheEntry=0x%hx, CacheId=0x%hhx, IconFlags=0x%hhx",
          0,
          *((unsigned int *)v4 + 1),
          cchToCopy,
          v843,
          *((unsigned __int8 *)v4 + 15),
          *((_DWORD *)v4 + 4),
          *((_DWORD *)v4 + 5),
          *((unsigned __int16 *)v4 + 6),
          v791,
          v885,
          v883,
          v884);
        v792 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v864);
        v793 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, void *))(*(_QWORD *)v792 + 56LL);
        v794 = CacCommon::Rect<int>::Rect<int>(v891);
        RemoteAppWindow = v793(
                            v792,
                            *((unsigned __int8 *)v4 + v784 + 26),
                            *(unsigned __int16 *)((char *)v4 + v784 + 24),
                            v794);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_1083;
          }
          v798 = RdpX_GetActivityIdPrefix(v796, v795, v797);
          v799 = 174;
          goto LABEL_1092;
        }
      }
      else
      {
        v801 = v737 + 20;
        v787 = v873;
        if ( v785 < v801 )
          RdpRemoteAppCore::LogRemoteAppError(
            (char *)v873 + 16,
            L"Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Create PDU",
            2147549183LL,
            0,
            0);
        v802 = *((unsigned __int16 *)v4 + 1);
        if ( v802 < v801 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_1082;
          }
          v788 = RdpX_GetActivityIdPrefix(v782, v781, v783);
          v789 = 175;
          goto LABEL_1081;
        }
        if ( (*((_BYTE *)v4 + v784 + 27) & 2) != 0 )
        {
          LOBYTE(v781) = *((_BYTE *)v4 + v784 + 32);
          v803 = *(unsigned __int16 *)((char *)v4 + v784 + 34);
          LOWORD(v863) = v781;
        }
        else
        {
          v803 = 0;
          LOWORD(v863) = 32;
        }
        v914 = *(_DWORD *)((char *)v4 + v784 + 36);
        v804 = (unsigned __int16)v803 + v914;
        LODWORD(v878) = v803;
        v805 = *(_DWORD *)((char *)v4 + v784 + 40) + v804 + v801;
        LODWORD(v873) = (unsigned __int16)v803;
        if ( v802 < v805 )
        {
          RdpRemoteAppCore::LogRemoteAppError(
            (char *)v787 + 16,
            L"Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Create PDU",
            2147549183LL,
            0,
            0);
          v803 = (unsigned int)v878;
        }
        if ( *((unsigned __int16 *)v4 + 1) < v805 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_1082;
          }
          v788 = RdpX_GetActivityIdPrefix(v804, v781, v803);
          v789 = 176;
          goto LABEL_1081;
        }
        v878 = (__int64)v4 + v784 + (unsigned __int16)v803 + 44;
        v884 = *(_DWORD *)((char *)v4 + v784 + 40);
        v883 = *(_DWORD *)((char *)v4 + v784 + 36);
        v885 = *(unsigned __int16 *)((char *)v4 + v784 + 34);
        v915 = *((unsigned __int8 *)v4 + v784 + 32);
        v916 = *(unsigned __int16 *)((char *)v4 + v784 + 30);
        v913 = *(unsigned __int16 *)((char *)v4 + v784 + 28);
        v912 = *((unsigned __int8 *)v4 + v784 + 27);
        v911 = *((unsigned __int8 *)v4 + v784 + 26);
        v910 = *(unsigned __int16 *)((char *)v4 + v784 + 24);
        if ( RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v872) )
        {
          v806 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v872);
          v807 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v806 + 24LL))(v806);
        }
        else
        {
          v807 = &sourceString;
        }
        LODWORD(v843) = *((unsigned __int8 *)v4 + 14);
        LODWORD(cchToCopy) = *((_DWORD *)v4 + 2);
        RdpRemoteAppCore::LogRemoteAppEventF(
          (char *)v787 + 16,
          L"NotifyIconCreateRailOrderReceived_NonCached: WindowId=0x%x, NotifyIconId=0x%x, NumIcons=%hhu, IsCachedIcon=%hh"
           "u, StateFlags=0x%x, PDUFlags=0x%x, ToolTipBytes=%hu, ToolTip=%s, CacheEntry=0x%hx, CacheId=0x%hhx, IconFlags="
           "0x%hhx, Width=%hu, Height=%hu, Bpp=%hhu, ColorTableBytes=%hu, BitsMaskBytes=%u, BitsColorBytes=%u",
          0,
          *((unsigned int *)v4 + 1),
          cchToCopy,
          v843,
          *((unsigned __int8 *)v4 + 15),
          *((_DWORD *)v4 + 4),
          *((_DWORD *)v4 + 5),
          *((unsigned __int16 *)v4 + 6),
          v807,
          v910,
          v911,
          v912,
          v913,
          v916,
          v915,
          v885,
          v883,
          v884);
        v808 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v864);
        v809 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64, _DWORD, _DWORD, char *, _DWORD, __int64, _DWORD, __int64, _DWORD, void *))(*(_QWORD *)v808 + 64LL);
        v810 = CacCommon::Rect<int>::Rect<int>(v891);
        v811 = v878 + v914;
        LOBYTE(v811) = v863;
        RemoteAppWindow = v809(
                            v808,
                            *((unsigned __int8 *)v4 + v784 + 26),
                            *(unsigned __int16 *)((char *)v4 + v784 + 24),
                            v811,
                            *(unsigned __int16 *)((char *)v4 + v784 + 28),
                            *(unsigned __int16 *)((char *)v4 + v784 + 30),
                            (char *)v4 + v784 + 44,
                            (_DWORD)v873,
                            v878,
                            *(_DWORD *)((char *)v4 + v784 + 36),
                            v878 + v914,
                            *(_DWORD *)((char *)v4 + v784 + 40),
                            v810);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_1083;
          }
          v798 = RdpX_GetActivityIdPrefix(v813, v812, v814);
          v799 = 177;
LABEL_1092:
          v800 = "CreateCachedIcon failed";
LABEL_1093:
          LODWORD(v843) = RemoteAppWindow;
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v799,
            (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
            v798,
            (__int64)v800,
            v843);
          goto LABEL_1083;
        }
      }
      v815 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v861);
      v816 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v815 + 80LL);
      v817 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v891);
      RemoteAppWindow = v816(v815, v817);
      if ( RemoteAppWindow < 0 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_1083;
        }
        v798 = RdpX_GetActivityIdPrefix(v819, v818, v820);
        v799 = 178;
        v800 = "spShellNotify->SetIcon failed";
        goto LABEL_1093;
      }
      RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v891);
    }
    else
    {
      v787 = v873;
      if ( RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v872) )
      {
        v821 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v872);
        v822 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v821 + 24LL))(v821);
      }
      else
      {
        v822 = &sourceString;
      }
      LODWORD(v843) = *((unsigned __int8 *)v4 + 14);
      LODWORD(cchToCopy) = *((_DWORD *)v4 + 2);
      RdpRemoteAppCore::LogRemoteAppEventF(
        (char *)v787 + 16,
        L"NotifyIconCreateRailOrderReceived_NoIcons: WindowId=0x%x, NotifyIconId=0x%x, NumIcons=%hhu, IsCachedIcon=%hhu, S"
         "tateFlags=0x%x, PDUFlags=0x%x, ToolTipBytes=%hu, ToolTip=%s",
        0,
        *((unsigned int *)v4 + 1),
        cchToCopy,
        v843,
        *((unsigned __int8 *)v4 + 15),
        *((_DWORD *)v4 + 4),
        *((_DWORD *)v4 + 5),
        *((unsigned __int16 *)v4 + 6),
        v822);
    }
    v823 = (struct RdpXInterfaceShellNotifyInformation *)RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v861);
    v824 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v861);
    v825 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v824 + 72LL))(v824);
    RemoteAppWindow = RdpRemoteAppCore::OnShellNotifyInformation(v787, v825, v823);
    if ( RemoteAppWindow >= 0
      || WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_1060;
    }
    v769 = RdpX_GetActivityIdPrefix(v827, v826, v828);
    v770 = 179;
    v771 = "OnShellNotifyInformation failed";
LABEL_1059:
    LODWORD(v843) = RemoteAppWindow;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v770,
      (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
      v769,
      (__int64)v771,
      v843);
LABEL_1060:
    RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v872);
    goto LABEL_1024;
  }
  if ( (_DWORD)v17 == 24 )
  {
    v224 = *((unsigned __int16 *)v4 + 1);
    if ( (_WORD)v224 != 1052 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v225 = RdpX_GetActivityIdPrefix(v17, v15, v16);
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v225, v224);
      }
      v25 = *((unsigned __int16 *)v4 + 1);
      v26 = L"Invalid size for TS_RAIL_ORDER_GET_APPID_RESP_EX [%d]";
      RemoteAppWindow = -2147467259;
      v27 = 2147500037LL;
      goto LABEL_1165;
    }
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v226 = *((_DWORD *)v4 + 132);
      v227 = *((_DWORD *)v4 + 1);
      v228 = RdpX_GetActivityIdPrefix(v17, v15, v16);
      WPP_SF_DDDS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        86,
        (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
        v228,
        v227,
        v226,
        (__int64)v4 + 532);
    }
    FileNameW = CUT::PathFindFileNameW((const unsigned __int16 *)v4 + 266);
    v230 = *((_DWORD *)v4 + 132);
    v231 = FileNameW;
    v232 = CUT::PathFindFileNameW((const unsigned __int16 *)v4 + 4);
    LODWORD(v843) = v230;
    RdpRemoteAppCore::LogRemoteAppEventF(
      (char *)v873 + 16,
      L"GetAppIdRespExRailOrderReceived: WindowId=0x%x, CensoredAppId=%s, ProcessId=%u, CensoredProcessImageName=%s",
      0,
      *((unsigned int *)v4 + 1),
      v232,
      v843,
      v231);
    v233 = (RdpRemoteAppCore *)((char *)v873 - 48);
    v894 = 0;
    RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow(
                        (RdpRemoteAppCore *)((char *)v873 - 48),
                        *((_DWORD *)v4 + 1),
                        &v894);
    if ( RemoteAppWindow >= 0 )
    {
      updated = RdpRemoteAppCore::UpdateProcessInfo(
                  v233,
                  v894,
                  *((_DWORD *)v4 + 132),
                  (const unsigned __int16 *)v4 + 266);
      if ( updated < 0
        && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v242 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v239, v241);
        LODWORD(v847) = updated;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          88,
          (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v242,
          (__int64)"Failed to set process info",
          v847);
      }
      RemoteAppWindow = RdpRemoteAppCore::UpdateAppID(v233, v894, (const unsigned __int16 *)v4 + 4);
      if ( RemoteAppWindow < 0
        && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v246 = RdpX_GetActivityIdPrefix(v244, v243, v245);
        LODWORD(v847) = RemoteAppWindow;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          89,
          (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v246,
          (__int64)"UpdateAppID failed",
          v847);
      }
      v38 = v894;
      if ( v894 )
      {
        v894 = 0;
        goto LABEL_106;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v237 = *((_DWORD *)v4 + 1);
        v238 = RdpX_GetActivityIdPrefix(v235, v234, v236);
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v238, v237);
      }
      v38 = v894;
      if ( v894 )
      {
        v894 = 0;
        goto LABEL_106;
      }
    }
    return (unsigned int)RemoteAppWindow;
  }
  if ( (unsigned int)v17 > 0xF )
  {
    v87 = (unsigned int)(v17 - 16);
    if ( (_DWORD)v17 != 16 )
    {
      v88 = (unsigned int)(v17 - 18);
      if ( (_DWORD)v17 == 18 )
      {
        v126 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v127 = RdpX_GetActivityIdPrefix(v17, v88, v16);
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 112, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v127);
          v126 = WPP_GLOBAL_Control;
        }
        v128 = *((unsigned __int16 *)v4 + 1);
        if ( (_WORD)v128 != 20 )
        {
          if ( v126 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v126[7] & 1) != 0 && *((_BYTE *)v126 + 25) >= 2u )
          {
            v129 = RdpX_GetActivityIdPrefix(v17, v88, v16);
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              113,
              &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v129,
              v128);
          }
          v25 = *((unsigned __int16 *)v4 + 1);
          v26 = L"Invalid size for TS_RAIL_ORDER_COMPARTMENTINFO [%d]";
          RemoteAppWindow = -2147467259;
          v27 = 2147500037LL;
          goto LABEL_1165;
        }
        RdpRemoteAppCore::LogRemoteAppEventF(
          (char *)v5 + 16,
          L"CompartmentInfoRailOrderReceived: Open=%d, ConversionMode=0x%x, SentenceMode=0x%x, KanaOn=%d",
          0,
          *((unsigned int *)v4 + 1),
          *((_DWORD *)v4 + 2),
          *((_DWORD *)v4 + 3),
          *((_DWORD *)v4 + 4));
        if ( *((_QWORD *)v5 + 17) )
        {
          v130 = *((_DWORD *)v4 + 1);
          v131 = *((_DWORD *)v4 + 4) == 0;
          v132 = *((_DWORD *)v4 + 3);
          v934[1] = *((_DWORD *)v4 + 2);
          v934[2] = v132;
          v934[3] = !v131;
          v934[0] = v130 != 0;
          (*(void (__fastcall **)(_QWORD, _DWORD *))(**((_QWORD **)v5 + 17) + 48LL))(*((_QWORD *)v5 + 17), v934);
        }
        return 0;
      }
      v18 = (unsigned int)(v17 - 19);
      if ( (_DWORD)v17 == 19 )
        goto LABEL_197;
      v89 = (unsigned int)(v17 - 20);
      if ( (_DWORD)v17 == 20 )
      {
        v111 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v112 = RdpX_GetActivityIdPrefix(v17, v89, v16);
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 114, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v112);
          v111 = WPP_GLOBAL_Control;
        }
        v113 = *((unsigned __int16 *)v4 + 1);
        if ( v113 == 8 )
        {
          RdpRemoteAppCore::LogRemoteAppEventF(
            (char *)v5 + 16,
            L"ZOrderSyncRailOrderReceived: MarkerWindowId=0x%x",
            0,
            *((unsigned int *)v4 + 1));
          RemoteAppWindow = 0;
          *((_DWORD *)v5 + 55) = *((_DWORD *)v4 + 1);
          return (unsigned int)RemoteAppWindow;
        }
        if ( v111 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v111[7] & 0x40) != 0 && *((_BYTE *)v111 + 25) >= 2u )
        {
          v114 = RdpX_GetActivityIdPrefix(v17, v89, v16);
          WPP_SF_DdL(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            115,
            &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
            v114,
            v113,
            8);
        }
        RemoteAppWindow = -2147418113;
        LODWORD(v843) = 8;
        v101 = 2147549183LL;
        v102 = L"Invalid size for TS_RAIL_ORDER_ZORDER_SYNC: [%d]. Expected size: [%lu]";
LABEL_1150:
        LODWORD(cchToCopy) = *((unsigned __int16 *)v4 + 1);
        RdpRemoteAppCore::LogRemoteAppErrorF((char *)v5 + 16, v102, v101, 0, cchToCopy, v843);
        return (unsigned int)RemoteAppWindow;
      }
      v90 = (unsigned int)(v17 - 21);
      if ( (_DWORD)v17 != 21 )
      {
        if ( (_DWORD)v17 != 22 )
          goto LABEL_1160;
        RemoteAppWindow = 0;
        if ( *((_WORD *)v4 + 1) == 8
          || (RdpRemoteAppCore::LogRemoteAppError(
                (char *)v5 + 16,
                L"Invalid size of TS_RAIL_ORDER_POWER_DISPLAY_REQUEST_BODY PDU",
                2147549183LL,
                0,
                0),
              *((_WORD *)v4 + 1) == 8) )
        {
          RdpRemoteAppCore::LogRemoteAppEventF(
            (char *)v5 + 16,
            L"PowerDisplayRequestRailOrderReceived: Active=%d",
            0,
            *((unsigned int *)v4 + 1));
          v95 = *((_DWORD *)v4 + 1);
          if ( RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *((char *)v5 + 120) )
          {
            v96 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *((char *)v5 + 120);
            (*(void (__fastcall **)(__int64, bool))(*(_QWORD *)v96 + 184LL))(v96, v95 != 0);
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v94 = RdpX_GetActivityIdPrefix(v92, v91, v93);
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              119,
              &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v94,
              -2147418113);
          }
          return (unsigned int)-2147418113;
        }
        return (unsigned int)RemoteAppWindow;
      }
      v97 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v98 = RdpX_GetActivityIdPrefix(v17, v90, v16);
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 116, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v98);
        v97 = WPP_GLOBAL_Control;
      }
      v99 = *((unsigned __int16 *)v4 + 1);
      if ( v99 != 9 )
      {
        if ( v97 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v97[7] & 0x40) != 0 && *((_BYTE *)v97 + 25) >= 2u )
        {
          v100 = RdpX_GetActivityIdPrefix(v17, v90, v16);
          WPP_SF_DdL(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            117,
            &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
            v100,
            v99,
            9);
        }
        RemoteAppWindow = -2147418113;
        LODWORD(v843) = 9;
        v101 = 2147549183LL;
        v102 = L"Invalid size for TS_RAIL_ORDER_CLOAK: [%d]. Expected size: [%lu]";
        goto LABEL_1150;
      }
      RdpRemoteAppCore::LogRemoteAppEventF(
        (char *)v5 + 16,
        L"CloakRailOrderReceived: WindowId=0x%x, Cloaked=%d",
        0,
        *((unsigned int *)v4 + 1),
        *((unsigned __int8 *)v4 + 8));
      v103 = *((_QWORD *)v5 + 15);
      if ( v103 && (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v103 + 120LL))(v103) )
      {
        v926 = 0;
        v921 = 0;
        RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow(
                            (RdpRemoteAppCore *)((char *)v5 - 48),
                            *((_DWORD *)v4 + 1),
                            &v926);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v107 = *((_DWORD *)v4 + 1);
            v108 = RdpX_GetActivityIdPrefix(v105, v104, v106);
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              118,
              &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v108,
              v107);
          }
          v38 = v926;
          if ( v926 )
          {
            v926 = 0;
            goto LABEL_106;
          }
          return (unsigned int)RemoteAppWindow;
        }
        DesktopRemoteAppWindow = RdpRemoteAppCore::GetDesktopRemoteAppWindow(
                                   (RdpRemoteAppCore *)((char *)v5 - 48),
                                   v926);
        RdpXSPtr<RdpXInterfaceLayerManager>::operator=(&v921, DesktopRemoteAppWindow);
        if ( v921 )
        {
          (*(void (__fastcall **)(__int64, bool))(*(_QWORD *)v921 + 440LL))(v921, *((_BYTE *)v4 + 8) != 0);
          v110 = v921;
          if ( v921 )
          {
            v921 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v110 + 8LL))(v110);
          }
        }
        RdpXSPtr<RdpXTapVcCallbackItem>::SafeRelease(&v926);
      }
      return 0;
    }
    v133 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v134 = RdpX_GetActivityIdPrefix(v17, v87, v16);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v134);
      v133 = WPP_GLOBAL_Control;
    }
    v135 = *((unsigned __int16 *)v4 + 1);
    if ( (unsigned __int16)v135 < 0x10u )
    {
      if ( v133 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v133[7] & 1) != 0 && *((_BYTE *)v133 + 25) >= 2u )
      {
        v136 = RdpX_GetActivityIdPrefix(v17, v87, v16);
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v136, v135);
      }
      v25 = *((unsigned __int16 *)v4 + 1);
      v26 = L"Invalid size for TS_RAIL_ORDER_TASKBARINFO [%d]";
      RemoteAppWindow = -2147467259;
      v27 = 2147500037LL;
      goto LABEL_1165;
    }
    RdpRemoteAppCore::LogRemoteAppEventF(
      (char *)v5 + 16,
      L"TaskbarInfoRailOrderReceived: Message=0x%x, WindowIdTab=0x%x, Body=0x%x",
      0,
      *((unsigned int *)v4 + 1),
      *((_DWORD *)v4 + 2),
      *((_DWORD *)v4 + 3));
    v138 = *((_DWORD *)v4 + 2);
    v930[1] = v138;
    v139 = *((_DWORD *)v4 + 1);
    v930[0] = v139;
    if ( v139 == 5 )
    {
      v932 = *((_DWORD *)v4 + 3);
      v931 = 0;
      goto LABEL_242;
    }
    if ( (unsigned int)(v139 - 1) <= 3 )
    {
      v931 = *((_DWORD *)v4 + 3);
      v932 = 0;
LABEL_242:
      v140 = *((_QWORD *)v5 + 15);
      if ( v140 )
        (*(void (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v140 + 160LL))(v140, v930);
      return 0;
    }
    if ( v139 == 6 )
    {
      v922 = 0;
      RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow((RdpRemoteAppCore *)((char *)v5 - 48), v138, &v922);
      if ( RemoteAppWindow < 0 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v144 = *((_DWORD *)v4 + 2);
          v145 = RdpX_GetActivityIdPrefix(v142, v141, v143);
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            95,
            &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
            v145,
            v144);
        }
        v38 = v922;
        if ( v922 )
        {
          v922 = 0;
          goto LABEL_106;
        }
        return (unsigned int)RemoteAppWindow;
      }
      (*(void (__fastcall **)(struct RdpXInterfaceRemoteAppWindow *, __int64))(*(_QWORD *)v922 + 264LL))(v922, 0x100000);
      v146 = v922;
      if ( v922 )
      {
        v922 = 0;
LABEL_387:
        (*(void (__fastcall **)(struct RdpXInterfaceRemoteAppWindow *))(*(_QWORD *)v146 + 8LL))(v146);
        return 0;
      }
      return 0;
    }
    if ( v139 == 7 )
    {
      v923 = 0;
      RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow((RdpRemoteAppCore *)((char *)v5 - 48), v138, &v923);
      if ( RemoteAppWindow < 0 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v150 = *((_DWORD *)v4 + 2);
          v151 = RdpX_GetActivityIdPrefix(v148, v147, v149);
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            96,
            &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
            v151,
            v150);
        }
        v38 = v923;
        if ( v923 )
        {
          v923 = 0;
          goto LABEL_106;
        }
        return (unsigned int)RemoteAppWindow;
      }
      (*(void (__fastcall **)(struct RdpXInterfaceRemoteAppWindow *, __int64))(*(_QWORD *)v923 + 264LL))(v923, 0x200000);
      v146 = v923;
      if ( v923 )
      {
        v923 = 0;
        goto LABEL_387;
      }
      return 0;
    }
    if ( v139 != 8 )
    {
      if ( v139 == 9 )
      {
        v907 = 0;
        v893 = 0;
        v193 = (unsigned int)*((unsigned __int16 *)v4 + 6) + 14;
        if ( *((unsigned __int16 *)v4 + 1) >= (unsigned int)v193 )
        {
          RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow((RdpRemoteAppCore *)((char *)v5 - 48), v138, &v907);
          if ( RemoteAppWindow >= 0 )
          {
            v200 = RdpRemoteAppCore::GetDesktopRemoteAppWindow((RdpRemoteAppCore *)((char *)v5 - 48), v907);
            RdpXSPtr<RdpXInterfaceLayerManager>::operator=(&v893, v200);
            v201 = v893;
            if ( v893 )
            {
              if ( (unsigned __int16)(*((_WORD *)v4 + 6) - 3) <= 0x205u )
              {
                v202 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v893 + 424LL))(
                         v893,
                         (__int64)v4 + 14,
                         *((unsigned __int16 *)v4 + 6) >> 1);
                v204 = MapXResultToHR(v202);
                if ( v204 < 0
                  && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                  && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v206 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v203, v205);
                  LODWORD(v846) = v204;
                  WPP_SF_DsD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    108,
                    (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                    v206,
                    (__int64)"SetOverlayDesc failed",
                    v846);
                }
                v201 = v893;
              }
              if ( v201 )
              {
                v893 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v201 + 8LL))(v201);
              }
            }
            v146 = v907;
            if ( !v907 )
              return 0;
            v907 = 0;
            goto LABEL_387;
          }
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v198 = *((_DWORD *)v4 + 2);
            v199 = RdpX_GetActivityIdPrefix(v196, v195, v197);
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              107,
              &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v199,
              v198);
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v194 = RdpX_GetActivityIdPrefix(v193, 0, v137);
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              106,
              &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v194,
              -2147418113);
          }
          RemoteAppWindow = -2147418113;
        }
        v38 = v907;
        if ( !v907 )
          return (unsigned int)RemoteAppWindow;
        v907 = 0;
        goto LABEL_106;
      }
      if ( v139 == 10 )
      {
        v924 = 0;
        v898 = 0;
        RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow((RdpRemoteAppCore *)((char *)v5 - 48), v138, &v924);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v210 = *((_DWORD *)v4 + 2);
            v211 = RdpX_GetActivityIdPrefix(v208, v207, v209);
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              109,
              &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v211,
              v210);
          }
          v38 = v924;
          if ( v924 )
          {
            v924 = 0;
            goto LABEL_106;
          }
          return (unsigned int)RemoteAppWindow;
        }
        v212 = RdpRemoteAppCore::GetDesktopRemoteAppWindow((RdpRemoteAppCore *)((char *)v5 - 48), v924);
        RdpXSPtr<RdpXInterfaceLayerManager>::operator=(&v898, v212);
        if ( v898 )
        {
          v213 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v898 + 416LL))(v898, 0);
          v215 = MapXResultToHR(v213);
          if ( v215 < 0
            && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v217 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v214, v216);
            LODWORD(v846) = v215;
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              110,
              (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v217,
              (__int64)"UpdateOverlayIcon failed",
              v846);
          }
          v218 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v898 + 424LL))(v898, 0, 0);
          v220 = MapXResultToHR(v218);
          if ( v220 < 0
            && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v222 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v219, v221);
            LODWORD(v846) = v220;
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              111,
              (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v222,
              (__int64)"SetOverlayDesc failed",
              v846);
          }
          v223 = v898;
          if ( v898 )
          {
            v898 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v223 + 8LL))(v223);
          }
        }
        v146 = v924;
        if ( v924 )
        {
          v924 = 0;
          goto LABEL_387;
        }
      }
      return 0;
    }
    v152 = (RdpRemoteAppCore *)((char *)v5 - 48);
    v870 = 0;
    v867 = 0;
    v865 = 0;
    v866 = 0;
    v873 = (RdpRemoteAppCore *)((char *)v5 - 48);
    RemoteAppWindow = RdpRemoteAppCore::GetWndPlugin((RdpRemoteAppCore *)((char *)v5 - 48), &v865);
    if ( RemoteAppWindow < 0 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v156 = RdpX_GetActivityIdPrefix(v154, v153, v155);
        v157 = 97;
        v158 = "GetWndPlugin failed";
LABEL_271:
        LODWORD(v846) = RemoteAppWindow;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v157,
          (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v156,
          (__int64)v158,
          v846);
      }
LABEL_272:
      v159 = v866;
      if ( v866 )
      {
        v866 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v159 + 8LL))(v159);
      }
      v160 = v865;
      if ( v865 )
      {
        v865 = 0;
        (*(void (__fastcall **)(struct ITSWndPluginEx *))(*(_QWORD *)v160 + 16LL))(v160);
      }
      v161 = v867;
      if ( v867 )
      {
        v867 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v161 + 8LL))(v161);
      }
      v38 = v870;
      if ( v870 )
      {
        v870 = 0;
        goto LABEL_106;
      }
      return (unsigned int)RemoteAppWindow;
    }
    RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow(v152, *((_DWORD *)v4 + 2), &v870);
    if ( RemoteAppWindow < 0 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v166 = *((_DWORD *)v4 + 2);
        v167 = RdpX_GetActivityIdPrefix(v163, v162, v164);
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v167, v166);
      }
      goto LABEL_272;
    }
    if ( *((_BYTE *)v4 + 13) )
    {
      if ( *((_WORD *)v4 + 1) < 0x14u )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_292;
        }
        v168 = RdpX_GetActivityIdPrefix(v163, v162, v164);
        v169 = 99;
LABEL_291:
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v169,
          &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v168,
          -2147418113);
LABEL_292:
        RemoteAppWindow = -2147418113;
        goto LABEL_272;
      }
      RemoteAppWindow = (*(__int64 (__fastcall **)(struct ITSWndPluginEx *, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v865 + 56LL))(
                          v865,
                          *((unsigned __int8 *)v4 + 18),
                          *((unsigned __int16 *)v4 + 8),
                          &v866);
      if ( RemoteAppWindow < 0 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_272;
        }
        v156 = RdpX_GetActivityIdPrefix(v171, v170, v172);
        v157 = 100;
        goto LABEL_298;
      }
    }
    else
    {
      if ( *((_WORD *)v4 + 1) < 0x24u )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_292;
        }
        v168 = RdpX_GetActivityIdPrefix(v163, v162, v164);
        v169 = 101;
        goto LABEL_291;
      }
      if ( (*((_BYTE *)v4 + 19) & 2) != 0 )
      {
        LOBYTE(v165) = *((_BYTE *)v4 + 24);
        v173 = *((unsigned __int16 *)v4 + 13);
      }
      else
      {
        v173 = 0;
        LOWORD(v165) = 32;
      }
      v174 = *((unsigned int *)v4 + 7);
      v175 = v174 + *((_DWORD *)v4 + 8) + 36;
      LODWORD(v878) = (unsigned __int16)v173;
      v176 = v175 + (unsigned int)(unsigned __int16)v173;
      if ( *((unsigned __int16 *)v4 + 1) < (unsigned int)v176 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_292;
        }
        v168 = RdpX_GetActivityIdPrefix(v176, v173, v174);
        v169 = 102;
        goto LABEL_291;
      }
      RemoteAppWindow = (*(__int64 (__fastcall **)(struct ITSWndPluginEx *, _QWORD, _QWORD, __int64, _DWORD, _DWORD, __int64, _DWORD, __int64, _DWORD, __int64, _DWORD, __int64 *))(*(_QWORD *)v865 + 64LL))(
                          v865,
                          *((unsigned __int8 *)v4 + 18),
                          *((unsigned __int16 *)v4 + 8),
                          v165,
                          *((unsigned __int16 *)v4 + 10),
                          *((unsigned __int16 *)v4 + 11),
                          (__int64)v4 + 36,
                          v878,
                          (__int64)v4 + (unsigned __int16)v173 + 36,
                          *((_DWORD *)v4 + 7),
                          (__int64)v4 + (unsigned __int16)v173 + v174 + 36,
                          *((_DWORD *)v4 + 8),
                          &v866);
      if ( RemoteAppWindow < 0 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_272;
        }
        v156 = RdpX_GetActivityIdPrefix(v178, v177, v179);
        v157 = 103;
LABEL_298:
        v158 = "CreateCachedIcon failed";
        goto LABEL_271;
      }
      v152 = v873;
    }
    v180 = RdpRemoteAppCore::GetDesktopRemoteAppWindow(v152, v870);
    RdpXSPtr<RdpXInterfaceLayerManager>::operator=(&v867, v180);
    if ( v867 )
    {
      v182 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v867 + 416LL))(v867, v866);
      if ( v182 < 0
        && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v184 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v181, v183);
        LODWORD(v846) = v182;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          104,
          (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v184,
          (__int64)"Failed to UpdateOverlayIcon",
          v846);
      }
      v185 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v867 + 424LL))(v867, 0, 0);
      v187 = MapXResultToHR(v185);
      if ( v187 < 0
        && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v189 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v186, v188);
        LODWORD(v846) = v187;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          105,
          (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v189,
          (__int64)"Failed to reset the old overlay description",
          v846);
      }
    }
    v190 = v866;
    if ( v866 )
    {
      v866 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v190 + 8LL))(v190);
    }
    v191 = v865;
    if ( v865 )
    {
      v865 = 0;
      (*(void (__fastcall **)(struct ITSWndPluginEx *))(*(_QWORD *)v191 + 16LL))(v191);
    }
    v192 = v867;
    if ( v867 )
    {
      v867 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v192 + 8LL))(v192);
    }
    v146 = v870;
    if ( !v870 )
      return 0;
    v870 = 0;
    goto LABEL_387;
  }
  if ( (_DWORD)v17 == 15 )
  {
    v78 = *((unsigned __int16 *)v4 + 1);
    if ( (_WORD)v78 != 528 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v79 = RdpX_GetActivityIdPrefix(v17, v15, v16);
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v79, v78);
      }
      v25 = *((unsigned __int16 *)v4 + 1);
      v26 = L"Invalid size for TS_RAIL_ORDER_GET_APPID_RESP [%d]";
      RemoteAppWindow = -2147467259;
      v27 = 2147500037LL;
      goto LABEL_1165;
    }
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v80 = *((_DWORD *)v4 + 1);
      v81 = RdpX_GetActivityIdPrefix(v17, v15, v16);
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v81, v80);
    }
    v82 = CUT::PathFindFileNameW((const unsigned __int16 *)v4 + 4);
    RdpRemoteAppCore::LogRemoteAppEventF(
      (char *)v5 + 16,
      L"GetAppIdRespRailOrderReceived: WindowId=0x%x, CensoredAppId=%s",
      0,
      *((unsigned int *)v4 + 1),
      v82);
    RemoteAppWindow = RdpRemoteAppCore::UpdateAppID(
                        (RdpRemoteAppCore *)((char *)v5 - 48),
                        *((_DWORD *)v4 + 1),
                        (const unsigned __int16 *)v4 + 4);
    if ( RemoteAppWindow < 0
      && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v86 = RdpX_GetActivityIdPrefix(v84, v83, v85);
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        84,
        (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
        v86,
        (__int64)"UpdateAppID failed",
        RemoteAppWindow);
    }
    return (unsigned int)RemoteAppWindow;
  }
  if ( (_DWORD)v17 == 3 )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v77 = RdpX_GetActivityIdPrefix(v17, (unsigned int)(v17 - 3), v16);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v77);
    }
    RdpRemoteAppCore::OnRailOrderSysParam((RdpRemoteAppCore *)((char *)v5 - 48), v4);
    return 0;
  }
  v18 = (unsigned int)(v17 - 5);
  if ( (_DWORD)v17 == 5 )
  {
LABEL_197:
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v115 = RdpX_GetActivityIdPrefix(v17, v18, v16);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v115);
    }
    LOBYTE(v18) = 3;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_RailV2ConnectionInfoDisclosure>::__private_IsEnabledPreCheck(
      `wil::Feature<__WilFeatureTraits_Feature_RailV2ConnectionInfoDisclosure>::GetImpl'::`2'::impl,
      v18);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_RailV2ConnectionInfoDisclosure>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_RailV2ConnectionInfoDisclosure>::GetImpl'::`2'::impl) )
    {
      v117 = RdpRemoteAppCore::SetV2CoreProperty((RdpRemoteAppCore *)((char *)v5 - 48), 4u);
      if ( v117 < 0
        && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v119 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v116, v118);
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          68,
          (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v119,
          (__int64)"Failed to set the V2 core property",
          v117);
      }
    }
    v121 = RdpRemoteAppCore::ReceiveHandshake((RdpRemoteAppCore *)((char *)v5 - 48), v4, (unsigned int *)v5 + 43);
    if ( v121 >= 0 )
    {
      return (unsigned int)RdpRemoteAppCore::OnHandshakeOrCaps((RdpRemoteAppCore *)((char *)v5 - 48), 1);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v123 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v120, v122);
        LODWORD(v843) = v121;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          69,
          (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v123,
          (__int64)"RemoteAppHandshake::ReceiveHandshake failed",
          v843);
      }
      LOBYTE(v120) = 3;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_RailV2ConnectionInfoDisclosure>::__private_IsEnabledPreCheck(
        `wil::Feature<__WilFeatureTraits_Feature_EnableRailV2>::GetImpl'::`2'::impl,
        v120);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableRailV2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnableRailV2>::GetImpl'::`2'::impl) )
        v124 = *(unsigned int (**)(void))(**((_QWORD **)v5 + 12) + 56LL);
      else
        v124 = *(unsigned int (**)(void))(**((_QWORD **)v5 + 11) + 48LL);
      return v124();
    }
  }
  if ( (_DWORD)v17 == 7 )
  {
LABEL_1134:
    v829 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v830 = RdpX_GetActivityIdPrefix(v17, WPP_GLOBAL_Control, v16);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v830);
      v829 = WPP_GLOBAL_Control;
    }
    v831 = *((unsigned __int16 *)v4 + 1);
    if ( (unsigned __int16)v831 < 0x10u )
    {
      if ( v829 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v829[7] & 1) != 0 && *((_BYTE *)v829 + 25) >= 2u )
      {
        v832 = RdpX_GetActivityIdPrefix(v17, v829, v16);
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v832);
      }
      RemoteAppWindow = -2147467259;
      RdpRemoteAppCore::LogRemoteAppError((char *)v5 + 16, L"TS_RAIL_ORDER_EXEC_RESULT too short", 2147500037LL, 0, 0);
      return (unsigned int)RemoteAppWindow;
    }
    v833 = *((unsigned __int16 *)v4 + 7);
    if ( v831 != v833 + 16 )
    {
      if ( v829 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v829[7] & 1) != 0 && *((_BYTE *)v829 + 25) >= 2u )
      {
        v834 = RdpX_GetActivityIdPrefix(v833 + 16, v829, v16);
        WPP_SF_DLD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          72,
          &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v834,
          v831,
          v833 + 16);
      }
      RemoteAppWindow = -2147467259;
      v101 = 2147500037LL;
      v843 = (unsigned __int16 *)(*((unsigned __int16 *)v4 + 7) + 16LL);
      v102 = L"TS_RAIL_ORDER_EXEC_RESULT wrong size got[%u] expected[%u]";
      goto LABEL_1150;
    }
    memset_0(pszDest, 0, 0x208u);
    StringCopyWorkerW_0(
      pszDest,
      0x104u,
      0,
      (STRSAFE_PCNZWCH)v4 + 8,
      (unsigned __int64)*((unsigned __int16 *)v4 + 7) >> 1);
    v835 = *((_DWORD *)v4 + 2);
    v836 = (char *)v5 + 16;
    if ( *((_WORD *)v4 + 3) )
    {
      if ( v835 )
      {
        if ( v835 > 0 )
          v837 = (unsigned __int16)v835 | 0x80070000;
        else
          v837 = *((_DWORD *)v4 + 2);
      }
      else
      {
        v837 = -2147467259;
      }
      RdpRemoteAppCore::LogRemoteAppErrorF(
        v836,
        L"ExecResultRailOrderReceived_Error: ApplicationName=%s, Flags=0x%hx, Result=0x%hx, RawResult=0x%x",
        v837,
        1,
        pszDest,
        *((unsigned __int16 *)v4 + 2),
        *((unsigned __int16 *)v4 + 3),
        *((_DWORD *)v4 + 2));
    }
    else
    {
      LODWORD(cchToCopyc) = *((unsigned __int16 *)v4 + 2);
      RdpRemoteAppCore::LogRemoteAppEventF(
        v836,
        L"ExecResultRailOrderReceived: ApplicationName=%s, Flags=0x%hx, Result=0x%hx, RawResult=0x%x",
        0,
        pszDest,
        cchToCopyc,
        0,
        *((_DWORD *)v4 + 2));
    }
    return (unsigned int)RdpRemoteAppCore::OnExecResult(
                           (RdpRemoteAppCore *)((char *)v5 - 48),
                           (struct tagTS_RAIL_PDU *)((char *)v4 + 4));
  }
  v19 = (unsigned int)(v17 - 9);
  if ( (_DWORD)v17 == 9 )
  {
    v49 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v50 = *((unsigned __int16 *)v4 + 5);
      v51 = *((unsigned __int16 *)v4 + 4);
      v52 = *((_DWORD *)v4 + 1);
      v53 = RdpX_GetActivityIdPrefix(v17, v19, v16);
      WPP_SF_DDDd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        73,
        &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
        v53,
        v52,
        v51,
        v50);
      v49 = WPP_GLOBAL_Control;
      v5 = v873;
    }
    v54 = *((unsigned __int16 *)v4 + 1);
    if ( (_WORD)v54 != 16 )
    {
      if ( v49 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v49[7] & 1) != 0 && *((_BYTE *)v49 + 25) >= 2u )
      {
        v55 = RdpX_GetActivityIdPrefix(v17, v19, v16);
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v55, v54);
      }
      v25 = *((unsigned __int16 *)v4 + 1);
      v26 = L"Invalid size for TS_RAIL_ORDER_LOCALMOVESIZE [%d]";
      RemoteAppWindow = -2147467259;
      v27 = 2147500037LL;
      goto LABEL_1165;
    }
    LODWORD(v853) = *((__int16 *)v4 + 6);
    LODWORD(v843) = *((unsigned __int16 *)v4 + 5);
    LODWORD(cchToCopy) = *((unsigned __int16 *)v4 + 4);
    RdpRemoteAppCore::LogRemoteAppEventF(
      (char *)v5 + 16,
      L"LocalMoveSizeRailOrderReceived: WindowId=0x%x, IsStart=%hu, Type=0x%hx, X=%hi, Y=%hi",
      0,
      *((unsigned int *)v4 + 1),
      cchToCopy,
      v843,
      v853,
      *((__int16 *)v4 + 7));
    v887 = 0;
    v886 = 0;
    RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow(
                        (RdpRemoteAppCore *)((char *)v5 - 48),
                        *((_DWORD *)v4 + 1),
                        &v887);
    if ( RemoteAppWindow >= 0 )
    {
      v62 = RdpRemoteAppCore::GetDesktopRemoteAppWindow((RdpRemoteAppCore *)((char *)v5 - 48), v887);
      RdpXSPtr<RdpXInterfaceLayerManager>::operator=(&v886, v62);
      v66 = v886;
      if ( !v886 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control )
        {
          v67 = (_DWORD)v886 + 8;
          if ( ((unsigned __int8)((_BYTE)v886 + 8) & (_BYTE)WPP_GLOBAL_Control[7]) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v68 = RdpX_GetActivityIdPrefix(v64, v63, v65);
            LODWORD(v845) = 1;
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v67 + 68,
              (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v68,
              (__int64)"spDesktopRemoteAppWindow",
              v845);
            v66 = v886;
          }
        }
        RemoteAppWindow = 1;
        if ( !v66 )
          goto LABEL_104;
        v886 = 0;
        v61 = *v66;
        goto LABEL_103;
      }
      if ( *((_WORD *)v4 + 4) )
      {
        v920 = 0;
        v69 = RemoteAppMoveSizeInfo::CreateInstance((char *)v4 + 4, &v920);
        RemoteAppWindow = MapXResultToHR(v69);
        if ( RemoteAppWindow >= 0 )
        {
          (*(void (__fastcall **)(__int64 *, __int64))(*v886 + 392))(v886, v920);
        }
        else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
               && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v73 = RdpX_GetActivityIdPrefix(v71, v70, v72);
          LODWORD(v845) = RemoteAppWindow;
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            77,
            (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
            v73,
            (__int64)"Failed to create RemoteAppMoveSizeInfo",
            v845);
        }
        v74 = v920;
        if ( v920 )
        {
          v920 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 8LL))(v74);
        }
      }
      else
      {
        if ( *((_WORD *)v4 + 5) == 9 )
        {
          v75 = *((__int16 *)v4 + 7);
          v76 = (unsigned int)*((__int16 *)v4 + 6);
        }
        else
        {
          v75 = -1;
          v76 = 0xFFFFFFFFLL;
        }
        (*(void (__fastcall **)(__int64 *, __int64, _QWORD, __int64, int))(*v886 + 400))(v886, 1, 0, v76, v75);
      }
    }
    else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
           && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v59 = RdpX_GetActivityIdPrefix(v57, v56, v58);
      LODWORD(v845) = RemoteAppWindow;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        75,
        (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
        v59,
        (__int64)"Failed to find window",
        v845);
    }
    v60 = v886;
    if ( !v886 )
    {
LABEL_104:
      v38 = v887;
      if ( !v887 )
        return (unsigned int)RemoteAppWindow;
      v887 = 0;
      goto LABEL_106;
    }
    v886 = 0;
    v61 = *v60;
LABEL_103:
    (*(void (**)(void))(v61 + 8))();
    goto LABEL_104;
  }
  v20 = (unsigned int)(v17 - 10);
  if ( (_DWORD)v17 != 10 )
  {
    if ( (_DWORD)v17 == 13 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v22 = RdpX_GetActivityIdPrefix(v17, v20, v16);
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v22);
        v21 = WPP_GLOBAL_Control;
      }
      v23 = *((unsigned __int16 *)v4 + 1);
      if ( (_WORD)v23 != 8 )
      {
        if ( v21 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v21[7] & 1) != 0 && *((_BYTE *)v21 + 25) >= 2u )
        {
          v24 = RdpX_GetActivityIdPrefix(v17, v20, v16);
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v24, v23);
        }
        v25 = *((unsigned __int16 *)v4 + 1);
        v26 = L"Invalid size for TS_RAIL_ORDER_LANGBARINFO [%d]";
        RemoteAppWindow = -2147467259;
        v27 = 2147500037LL;
LABEL_1165:
        LODWORD(cchToCopy) = v25;
        RdpRemoteAppCore::LogRemoteAppErrorF((char *)v5 + 16, v26, v27, 0, cchToCopy);
        return (unsigned int)RemoteAppWindow;
      }
      RdpRemoteAppCore::LogRemoteAppEventF(
        (char *)v5 + 16,
        L"LangBarInfoRailOrderReceived: Status=0x%x",
        0,
        *((unsigned int *)v4 + 1));
      v28 = *((_QWORD *)v5 + 17);
      if ( v28 )
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v28 + 24LL))(v28, *((unsigned int *)v4 + 1));
      return 0;
    }
LABEL_1160:
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        211,
        &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
        *(unsigned __int16 *)v4);
    }
    v25 = *(unsigned __int16 *)v4;
    v26 = L"Unknown orderType[0x%x]";
    RemoteAppWindow = -2147418113;
    v27 = 2147549183LL;
    goto LABEL_1165;
  }
  v29 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v30 = *((_DWORD *)v4 + 1);
    v31 = RdpX_GetActivityIdPrefix(v17, v20, v16);
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v31, v30);
    v29 = WPP_GLOBAL_Control;
  }
  v32 = *((unsigned __int16 *)v4 + 1);
  if ( (_WORD)v32 != 24 )
  {
    if ( v29 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v29[7] & 1) != 0 && *((_BYTE *)v29 + 25) >= 2u )
    {
      v33 = RdpX_GetActivityIdPrefix(v17, v20, v16);
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v33, v32);
    }
    v25 = *((unsigned __int16 *)v4 + 1);
    v26 = L"Invalid size for TS_RAIL_ORDER_MINMAXINFO [%d]";
    RemoteAppWindow = -2147467259;
    v27 = 2147500037LL;
    goto LABEL_1165;
  }
  LODWORD(cchToCopy) = *((__int16 *)v4 + 4);
  RdpRemoteAppCore::LogRemoteAppEventF(
    (char *)v873 + 16,
    L"MinMaxInfoRailOrderReceived: WindowId=0x%x, MaxWidth=%hi, MaxHeight=%hi, MaxPosX=%hi, MaxPosY=%hi, MinTrackWidth=%hi"
     ", MinTrackHeight=%hi, MaxTrackWidth=%hi, MaxTraceHeight=%hi",
    0,
    *((unsigned int *)v4 + 1),
    cchToCopy,
    *((__int16 *)v4 + 5),
    *((__int16 *)v4 + 6),
    *((__int16 *)v4 + 7),
    *((__int16 *)v4 + 8),
    *((__int16 *)v4 + 9),
    *((__int16 *)v4 + 10),
    *((__int16 *)v4 + 11));
  v906 = 0;
  v905 = 0;
  RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow(
                      (RdpRemoteAppCore *)((char *)v873 - 48),
                      *((_DWORD *)v4 + 1),
                      &v906);
  if ( RemoteAppWindow < 0 )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v37 = RdpX_GetActivityIdPrefix(v35, v34, v36);
      LODWORD(v844) = RemoteAppWindow;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        80,
        (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
        v37,
        (__int64)"Failed to find window",
        v844);
    }
LABEL_71:
    v38 = v906;
    if ( !v906 )
      return (unsigned int)RemoteAppWindow;
    v906 = 0;
LABEL_106:
    (*(void (__fastcall **)(struct RdpXInterfaceRemoteAppWindow *))(*(_QWORD *)v38 + 8LL))(v38);
    return (unsigned int)RemoteAppWindow;
  }
  v39 = RdpRemoteAppCore::GetDesktopRemoteAppWindow((RdpRemoteAppCore *)((char *)v873 - 48), v906);
  RdpXSPtr<RdpXInterfaceLayerManager>::operator=(&v905, v39);
  v42 = v905;
  if ( !v905 )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control )
    {
      v43 = v905 + 8;
      if ( ((unsigned __int8)(v905 + 8) & (_BYTE)WPP_GLOBAL_Control[7]) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v44 = RdpX_GetActivityIdPrefix(v41, v40, 0);
        LODWORD(v844) = 1;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v43 + 73,
          (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v44,
          (__int64)"spDesktopRemoteAppWindow",
          v844);
        v42 = v905;
      }
    }
    RemoteAppWindow = 1;
    if ( v42 )
    {
      v905 = 0;
      (*(void (**)(void))(*(_QWORD *)v42 + 8LL))();
    }
    goto LABEL_71;
  }
  v45 = 0;
  v938 = 0;
  memset(v937, 0, sizeof(v937));
  do
  {
    v46 = *((__int16 *)v4 + (unsigned int)v45 + 4);
    v47 = 4 * v45++ + 8;
    *(_DWORD *)((char *)v937 + v47) = v46;
  }
  while ( v45 < 8 );
  (*(void (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)v42 + 408LL))(v42, v937);
  v48 = v905;
  if ( v905 )
  {
    v905 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 8LL))(v48);
  }
  v38 = v906;
  if ( v906 )
  {
    v906 = 0;
    goto LABEL_106;
  }
  return (unsigned int)RemoteAppWindow;
}

```

## disassembly

```asm
0x18057e9b0  mov     [rsp-8+arg_10], rbx
0x18057e9b5  push    rbp
0x18057e9b6  push    rsi
0x18057e9b7  push    rdi
0x18057e9b8  push    r12
0x18057e9ba  push    r13
0x18057e9bc  push    r14
0x18057e9be  push    r15
0x18057e9c0  lea     rbp, [rsp-0A50h]
0x18057e9c8  sub     rsp, 0B90h
0x18057e9cf  mov     rax, cs:__security_cookie
0x18057e9d6  xor     rax, rsp
0x18057e9d9  mov     [rbp+0A80h+var_40], rax
0x18057e9e0  mov     ebx, r8d
0x18057e9e3  mov     [rbp+0A80h+var_A90], rcx
0x18057e9e7  mov     r13, rdx
0x18057e9ea  mov     rdi, rcx
0x18057e9ed  xor     r15d, r15d
0x18057e9f0  cmp     [rcx+68h], r15
0x18057e9f4  jnz     short loc_18057EA58
0x18057e9f6  mov     rax, cs:WPP_GLOBAL_Control
0x18057e9fd  lea     r14, WPP_GLOBAL_Control
0x18057ea04  cmp     rax, r14
0x18057ea07  jz      short loc_18057EA4E
0x18057ea09  mov     r15d, 8
0x18057ea0f  test    [rax+1Ch], r15b
0x18057ea13  jz      short loc_18057EA4E
0x18057ea15  lea     r12d, [r15-6]
0x18057ea19  cmp     [rax+19h], r12b
0x18057ea1d  jb      short loc_18057EA4E
0x18057ea1f  call    RdpX_GetActivityIdPrefix
0x18057ea24  lea     edx, [r15+36h]
0x18057ea28  lea     rcx, aMSptsclientpla; "m_spTsClientPlatformInstance"
0x18057ea2f  mov     [rsp+0BC0h+cchToCopy], rcx
0x18057ea34  lea     r8, WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids
0x18057ea3b  mov     rcx, cs:WPP_GLOBAL_Control
0x18057ea42  mov     r9d, eax
0x18057ea45  mov     rcx, [rcx+10h]
0x18057ea49  call    WPP_SF_Ds
0x18057ea4e  mov     esi, 80004003h
0x18057ea53  jmp     loc_18058533F
0x18057ea58  mov     r14d, 3
0x18057ea5e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnableRailV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnableRailV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableRailV2> `wil::Feature<__WilFeatureTraits_Feature_EnableRailV2>::GetImpl(void)'::`2'::impl
0x18057ea65  mov     dl, r14b
0x18057ea68  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_RailV2ConnectionInfoDisclosure@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RailV2ConnectionInfoDisclosure>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x18057ea6d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnableRailV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnableRailV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableRailV2> `wil::Feature<__WilFeatureTraits_Feature_EnableRailV2>::GetImpl(void)'::`2'::impl
0x18057ea74  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnableRailV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableRailV2>::__private_IsEnabled(void)
0x18057ea79  test    al, al
0x18057ea7b  jz      short loc_18057EAC5
0x18057ea7d  cmp     [rdi+60h], r15
0x18057ea81  jnz     loc_18057EB15
0x18057ea87  mov     rax, cs:WPP_GLOBAL_Control
0x18057ea8e  lea     r14, WPP_GLOBAL_Control
0x18057ea95  cmp     rax, r14
0x18057ea98  jz      short loc_18057EA4E
0x18057ea9a  mov     r15d, 8
0x18057eaa0  test    [rax+1Ch], r15b
0x18057eaa4  jz      short loc_18057EA4E
0x18057eaa6  lea     r12d, [r15-6]
0x18057eaaa  cmp     [rax+19h], r12b
0x18057eaae  jb      short loc_18057EA4E
0x18057eab0  call    RdpX_GetActivityIdPrefix
0x18057eab5  lea     edx, [r15+37h]
0x18057eab9  lea     rcx, aMRemoteappplug; "m_remoteAppPlugin.get()"
0x18057eac0  jmp     loc_18057EA2F
0x18057eac5  cmp     [rdi+58h], r15
0x18057eac9  jnz     short loc_18057EB15
0x18057eacb  mov     rax, cs:WPP_GLOBAL_Control
0x18057ead2  lea     r14, WPP_GLOBAL_Control
0x18057ead9  cmp     rax, r14
0x18057eadc  jz      loc_18057EA4E
0x18057eae2  mov     r15d, 8
0x18057eae8  test    [rax+1Ch], r15b
0x18057eaec  jz      loc_18057EA4E
0x18057eaf2  lea     r12d, [r15-6]
0x18057eaf6  cmp     [rax+19h], r12b
0x18057eafa  jb      loc_18057EA4E
0x18057eb00  call    RdpX_GetActivityIdPrefix
0x18057eb05  lea     edx, [r15+38h]
0x18057eb09  lea     rcx, aMSpremoteapppl; "m_spRemoteAppPlugin"
0x18057eb10  jmp     loc_18057EA2F
0x18057eb15  mov     esi, 4
0x18057eb1a  cmp     ebx, esi
0x18057eb1c  jnb     short loc_18057EB6D
0x18057eb1e  mov     rax, cs:WPP_GLOBAL_Control
0x18057eb25  lea     r14, WPP_GLOBAL_Control
0x18057eb2c  cmp     rax, r14
0x18057eb2f  jz      short loc_18057EB63
0x18057eb31  test    byte ptr [rax+1Ch], 1
0x18057eb35  jz      short loc_18057EB63
0x18057eb37  lea     r12d, [rsi-2]
0x18057eb3b  cmp     [rax+19h], r12b
0x18057eb3f  jb      short loc_18057EB63
0x18057eb41  call    RdpX_GetActivityIdPrefix
0x18057eb46  lea     edx, [rsi+3Dh]
0x18057eb49  mov     rcx, cs:WPP_GLOBAL_Control
0x18057eb50  lea     r8, WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids
0x18057eb57  mov     r9d, eax
0x18057eb5a  mov     rcx, [rcx+10h]
0x18057eb5e  call    WPP_SF_d
0x18057eb63  mov     esi, 80004005h
0x18057eb68  jmp     loc_18058533F
0x18057eb6d  movzx   eax, word ptr [r13+2]
0x18057eb72  cmp     ebx, eax
0x18057eb74  jnb     short loc_18057EBA7
0x18057eb76  mov     rax, cs:WPP_GLOBAL_Control
0x18057eb7d  lea     r14, WPP_GLOBAL_Control
0x18057eb84  cmp     rax, r14
0x18057eb87  jz      short loc_18057EB63
0x18057eb89  test    byte ptr [rax+1Ch], 1
0x18057eb8d  jz      short loc_18057EB63
0x18057eb8f  mov     r12d, 2
0x18057eb95  cmp     [rax+19h], r12b
0x18057eb99  jb      short loc_18057EB63
0x18057eb9b  call    RdpX_GetActivityIdPrefix
0x18057eba0  lea     edx, [r12+40h]
0x18057eba5  jmp     short loc_18057EB49
0x18057eba7  mov     rcx, r13; this
0x18057ebaa  call    ?TraceRailPDU@RDPRailTraceLogging@@YAXAEBUtagTS_RAIL_PDU@@@Z; RDPRailTraceLogging::TraceRailPDU(tagTS_RAIL_PDU const &)
0x18057ebaf  movzx   ecx, word ptr [r13+0]
0x18057ebb4  mov     eax, 80h
0x18057ebb9  cmp     ecx, eax
0x18057ebbb  ja      loc_1805852E1
0x18057ebc1  lea     r12d, [rax-7Eh]
0x18057ebc5  jz      loc_1805850D1
0x18057ebcb  lea     ebx, [rax-68h]
0x18057ebce  cmp     ecx, ebx
0x18057ebd0  ja      loc_180580A30
0x18057ebd6  jz      loc_18058079C
0x18057ebdc  cmp     ecx, 0Fh
0x18057ebdf  ja      loc_18057F531
0x18057ebe5  jz      loc_18057F3D2
0x18057ebeb  mov     edx, ecx
0x18057ebed  sub     edx, r14d
0x18057ebf0  jz      loc_18057F37B
0x18057ebf6  sub     edx, r12d
0x18057ebf9  jz      loc_18057F92F
0x18057ebff  sub     edx, r12d
0x18057ec02  jz      loc_1805850D1
0x18057ec08  sub     edx, r12d
0x18057ec0b  jz      loc_18057F026
0x18057ec11  sub     edx, 1
0x18057ec14  jz      loc_18057ED0C
0x18057ec1a  cmp     edx, r14d
0x18057ec1d  jnz     loc_1805852E1
0x18057ec23  mov     rax, cs:WPP_GLOBAL_Control
0x18057ec2a  lea     r14, WPP_GLOBAL_Control
0x18057ec31  cmp     rax, r14
0x18057ec34  jz      short loc_18057EC6B
0x18057ec36  test    byte ptr [rax+1Ch], 1
0x18057ec3a  jz      short loc_18057EC6B
0x18057ec3c  cmp     [rax+19h], sil
0x18057ec40  jb      short loc_18057EC6B
0x18057ec42  call    RdpX_GetActivityIdPrefix
0x18057ec47  mov     rcx, cs:WPP_GLOBAL_Control
0x18057ec4e  lea     edx, [rbx+43h]
0x18057ec51  mov     r9d, eax
0x18057ec54  lea     r8, WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids
0x18057ec5b  mov     rcx, [rcx+10h]
0x18057ec5f  call    WPP_SF_d
0x18057ec64  mov     rax, cs:WPP_GLOBAL_Control
0x18057ec6b  movzx   ebx, word ptr [r13+2]
0x18057ec70  mov     r15d, 8
0x18057ec76  cmp     bx, r15w
0x18057ec7a  jz      short loc_18057ECD0
0x18057ec7c  cmp     rax, r14
0x18057ec7f  jz      short loc_18057ECB4
0x18057ec81  test    byte ptr [rax+1Ch], 1
0x18057ec85  jz      short loc_18057ECB4
0x18057ec87  cmp     [rax+19h], r12b
0x18057ec8b  jb      short loc_18057ECB4
0x18057ec8d  call    RdpX_GetActivityIdPrefix
0x18057ec92  mov     rcx, cs:WPP_GLOBAL_Control
0x18057ec99  lea     edx, [r15+54h]
0x18057ec9d  mov     r9d, eax
0x18057eca0  mov     dword ptr [rsp+0BC0h+cchToCopy], ebx
0x18057eca4  lea     r8, WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids
0x18057ecab  mov     rcx, [rcx+10h]
0x18057ecaf  call    WPP_SF_Dd
0x18057ecb4  movzx   eax, word ptr [r13+2]
0x18057ecb9  lea     rdx, aInvalidSizeFor_6; "Invalid size for TS_RAIL_ORDER_LANGBARI"...
0x18057ecc0  mov     esi, 80004005h
0x18057ecc5  mov     r8d, 80004005h
0x18057eccb  jmp     loc_18058532F
0x18057ecd0  mov     r9d, [r13+4]
0x18057ecd4  lea     rcx, [rdi+10h]
0x18057ecd8  xor     r8d, r8d
0x18057ecdb  lea     rdx, aLangbarinforai; "LangBarInfoRailOrderReceived: Status=0x"...
0x18057ece2  call    ?LogRemoteAppEventF@RdpRemoteAppCore@@UEAAXPEBGW4_XBool32@@ZZ; RdpRemoteAppCore::LogRemoteAppEventF(ushort const *,_XBool32,...)
0x18057ece7  mov     rcx, [rdi+88h]
0x18057ecee  xor     ebx, ebx
0x18057ecf0  test    rcx, rcx
0x18057ecf3  jz      short loc_18057ED05
0x18057ecf5  mov     rax, [rcx]
0x18057ecf8  mov     edx, [r13+4]
0x18057ecfc  mov     rax, [rax+18h]
0x18057ed00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18057ed05  mov     esi, ebx
0x18057ed07  jmp     loc_18058533F
0x18057ed0c  mov     rax, cs:WPP_GLOBAL_Control
0x18057ed13  lea     r14, WPP_GLOBAL_Control
0x18057ed1a  cmp     rax, r14
0x18057ed1d  jz      short loc_18057ED5E
0x18057ed1f  test    byte ptr [rax+1Ch], 1
0x18057ed23  jz      short loc_18057ED5E
0x18057ed25  cmp     [rax+19h], sil
0x18057ed29  jb      short loc_18057ED5E
0x18057ed2b  mov     ebx, [r13+4]
0x18057ed2f  call    RdpX_GetActivityIdPrefix
0x18057ed34  mov     rcx, cs:WPP_GLOBAL_Control
0x18057ed3b  lea     r8, WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids
0x18057ed42  mov     edx, 4Eh ; 'N'
0x18057ed47  mov     dword ptr [rsp+0BC0h+cchToCopy], ebx
0x18057ed4b  mov     r9d, eax
0x18057ed4e  mov     rcx, [rcx+10h]
0x18057ed52  call    WPP_SF_Dd
0x18057ed57  mov     rax, cs:WPP_GLOBAL_Control
0x18057ed5e  movzx   ebx, word ptr [r13+2]
0x18057ed63  mov     esi, 18h
0x18057ed68  cmp     bx, si
0x18057ed6b  jz      short loc_18057EDC0
0x18057ed6d  cmp     rax, r14
0x18057ed70  jz      short loc_18057EDA4
0x18057ed72  test    byte ptr [rax+1Ch], 1
0x18057ed76  jz      short loc_18057EDA4
0x18057ed78  cmp     [rax+19h], r12b
0x18057ed7c  jb      short loc_18057EDA4
0x18057ed7e  call    RdpX_GetActivityIdPrefix
0x18057ed83  mov     rcx, cs:WPP_GLOBAL_Control
0x18057ed8a  lea     edx, [rsi+37h]
0x18057ed8d  mov     r9d, eax
0x18057ed90  mov     dword ptr [rsp+0BC0h+cchToCopy], ebx
0x18057ed94  lea     r8, WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids
0x18057ed9b  mov     rcx, [rcx+10h]
0x18057ed9f  call    WPP_SF_Dd
0x18057eda4  movzx   eax, word ptr [r13+2]
0x18057eda9  lea     rdx, aInvalidSizeFor_2; "Invalid size for TS_RAIL_ORDER_MINMAXIN"...
0x18057edb0  mov     esi, 80004005h
0x18057edb5  mov     r8d, 80004005h
0x18057edbb  jmp     loc_18058532F
0x18057edc0  movsx   edx, word ptr [r13+14h]
0x18057edc5  movsx   r8d, word ptr [r13+12h]
0x18057edca  movsx   r9d, word ptr [r13+10h]
0x18057edcf  movsx   eax, word ptr [r13+16h]
0x18057edd4  movsx   r10d, word ptr [r13+0Eh]
0x18057edd9  movsx   r11d, word ptr [r13+0Ch]
0x18057edde  movsx   ebx, word ptr [r13+0Ah]
0x18057ede3  movsx   edi, word ptr [r13+8]
0x18057ede8  mov     rsi, [rbp+0A80h+var_A90]
0x18057edec  mov     dword ptr [rsp+0BC0h+var_B68], eax
0x18057edf0  mov     dword ptr [rsp+0BC0h+var_B70], edx
0x18057edf4  lea     rdx, aMinmaxinforail; "MinMaxInfoRailOrderReceived: WindowId=0"...
0x18057edfb  mov     [rsp+0BC0h+var_B78], r8d
0x18057ee00  xor     r8d, r8d
0x18057ee03  mov     dword ptr [rsp+0BC0h+var_B80], r9d
0x18057ee08  lea     rcx, [rsi+10h]
0x18057ee0c  mov     r9d, [r13+4]
0x18057ee10  mov     dword ptr [rsp+0BC0h+var_B88], r10d
0x18057ee15  mov     dword ptr [rsp+0BC0h+var_B90], r11d
0x18057ee1a  mov     dword ptr [rsp+0BC0h+var_B98], ebx
0x18057ee1e  mov     dword ptr [rsp+0BC0h+cchToCopy], edi
0x18057ee22  call    ?LogRemoteAppEventF@RdpRemoteAppCore@@UEAAXPEBGW4_XBool32@@ZZ; RdpRemoteAppCore::LogRemoteAppEventF(ushort const *,_XBool32,...)
0x18057ee27  mov     [rbp+0A80h+var_9A0], r15
0x18057ee2e  lea     rbx, [rsi-30h]
0x18057ee32  mov     [rbp+0A80h+var_9A8], r15
0x18057ee39  lea     r8, [rbp+0A80h+var_9A0]; struct RdpXInterfaceRemoteAppWindow **
0x18057ee40  mov     edx, [r13+4]; unsigned int
0x18057ee44  mov     rcx, rbx; this
0x18057ee47  call    ?GetRemoteAppWindow@RdpRemoteAppCore@@IEAAJKPEAPEAURdpXInterfaceRemoteAppWindow@@@Z; RdpRemoteAppCore::GetRemoteAppWindow(ulong,RdpXInterfaceRemoteAppWindow * *)
0x18057ee4c  mov     esi, eax
0x18057ee4e  test    eax, eax
0x18057ee50  jns     loc_18057EEE5
0x18057ee56  mov     rax, cs:WPP_GLOBAL_Control
0x18057ee5d  cmp     rax, r14
0x18057ee60  jz      short loc_18057EEAA
0x18057ee62  mov     r15d, 8
0x18057ee68  test    [rax+1Ch], r15b
0x18057ee6c  jz      short loc_18057EEA7
0x18057ee6e  cmp     [rax+19h], r12b
0x18057ee72  jb      short loc_18057EEA7
0x18057ee74  call    RdpX_GetActivityIdPrefix
0x18057ee79  lea     rcx, aFailedToFindWi; "Failed to find window"
0x18057ee80  mov     dword ptr [rsp+0BC0h+var_B98], esi
0x18057ee84  mov     [rsp+0BC0h+cchToCopy], rcx
0x18057ee89  lea     edx, [r15+48h]
0x18057ee8d  mov     rcx, cs:WPP_GLOBAL_Control
0x18057ee94  lea     r8, WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids
0x18057ee9b  mov     r9d, eax
0x18057ee9e  mov     rcx, [rcx+10h]
0x18057eea2  call    WPP_SF_DsD
0x18057eea7  xor     r15d, r15d
0x18057eeaa  mov     rcx, [rbp+0A80h+var_9A8]
0x18057eeb1  test    rcx, rcx
0x18057eeb4  jz      short loc_18057EEC9
0x18057eeb6  mov     [rbp+0A80h+var_9A8], r15
0x18057eebd  mov     rax, [rcx]
0x18057eec0  mov     rax, [rax+8]
0x18057eec4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18057eec9  mov     rcx, [rbp+0A80h+var_9A0]
0x18057eed0  test    rcx, rcx
  ... truncated ...
```
