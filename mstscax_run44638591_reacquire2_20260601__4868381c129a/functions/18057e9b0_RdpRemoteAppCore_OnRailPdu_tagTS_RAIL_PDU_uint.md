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
  int v116; // eax
  __int64 v117; // rdx
  __int64 v118; // r8
  char v119; // bl
  int v120; // eax
  int v121; // eax
  __int64 v122; // rdx
  __int64 v123; // r8
  char v124; // si
  int v125; // eax
  unsigned int (*v126)(void); // rax
  HKEY v128; // rax
  unsigned int v129; // eax
  int v130; // ebx
  unsigned int v131; // eax
  int v132; // edx
  bool v133; // zf
  int v134; // r8d
  HKEY v135; // rax
  unsigned int v136; // eax
  int v137; // ebx
  unsigned int v138; // eax
  __int64 v139; // r8
  unsigned int v140; // r9d
  int v141; // ecx
  __int64 v142; // rcx
  __int64 v143; // rdx
  __int64 v144; // rcx
  __int64 v145; // r8
  int v146; // ebx
  unsigned int v147; // eax
  struct RdpXInterfaceRemoteAppWindow *v148; // rcx
  __int64 v149; // rdx
  __int64 v150; // rcx
  __int64 v151; // r8
  int v152; // ebx
  unsigned int v153; // eax
  RdpRemoteAppCore *v154; // rbx
  __int64 v155; // rdx
  __int64 v156; // rcx
  __int64 v157; // r8
  int v158; // eax
  int v159; // edx
  const char *v160; // rcx
  __int64 v161; // rcx
  struct ITSWndPluginEx *v162; // rcx
  __int64 v163; // rcx
  __int64 v164; // rdx
  __int64 v165; // rcx
  __int64 v166; // r8
  __int64 v167; // r9
  int v168; // ebx
  unsigned int v169; // eax
  unsigned int v170; // eax
  __int64 v171; // rdx
  __int64 v172; // rdx
  __int64 v173; // rcx
  __int64 v174; // r8
  __int64 v175; // rdx
  __int64 v176; // r8
  int v177; // eax
  __int64 v178; // rcx
  __int64 v179; // rdx
  __int64 v180; // rcx
  __int64 v181; // r8
  struct RdpInterfaceDesktopRemoteAppWindow *v182; // rax
  int v183; // eax
  __int64 v184; // rdx
  __int64 v185; // r8
  char v186; // bl
  int v187; // eax
  unsigned int v188; // eax
  int v189; // eax
  __int64 v190; // rdx
  __int64 v191; // r8
  char v192; // bl
  int v193; // eax
  __int64 v194; // rcx
  struct ITSWndPluginEx *v195; // rcx
  __int64 v196; // rcx
  __int64 v197; // rcx
  unsigned int v198; // eax
  __int64 v199; // rdx
  __int64 v200; // rcx
  __int64 v201; // r8
  int v202; // ebx
  unsigned int v203; // eax
  struct RdpInterfaceDesktopRemoteAppWindow *v204; // rax
  __int64 v205; // rcx
  unsigned int v206; // eax
  int v207; // eax
  __int64 v208; // rdx
  __int64 v209; // r8
  char v210; // bl
  int v211; // eax
  __int64 v212; // rdx
  __int64 v213; // rcx
  __int64 v214; // r8
  int v215; // ebx
  unsigned int v216; // eax
  struct RdpInterfaceDesktopRemoteAppWindow *v217; // rax
  unsigned int v218; // eax
  int v219; // eax
  __int64 v220; // rdx
  __int64 v221; // r8
  char v222; // bl
  int v223; // eax
  unsigned int v224; // eax
  int v225; // eax
  __int64 v226; // rdx
  __int64 v227; // r8
  char v228; // bl
  int v229; // eax
  __int64 v230; // rcx
  int v231; // ebx
  unsigned int v232; // eax
  int v233; // ebx
  int v234; // edi
  int v235; // eax
  const unsigned __int16 *FileNameW; // rax
  int v237; // ebx
  const unsigned __int16 *v238; // rdi
  const unsigned __int16 *v239; // rax
  RdpRemoteAppCore *v240; // rbx
  __int64 v241; // rdx
  __int64 v242; // rcx
  __int64 v243; // r8
  int v244; // ebx
  unsigned int v245; // eax
  int updated; // eax
  __int64 v247; // rdx
  __int64 v248; // r8
  char v249; // di
  int v250; // eax
  __int64 v251; // rdx
  __int64 v252; // rcx
  __int64 v253; // r8
  int v254; // eax
  __int64 v255; // rdx
  __int64 v256; // rcx
  __int64 v257; // r8
  unsigned int v258; // eax
  char *v259; // rcx
  struct RdpXInterfaceRemoteAppWindow **v260; // rax
  __int64 v261; // rdx
  __int64 v262; // rcx
  __int64 v263; // r8
  int v264; // ebx
  unsigned int v265; // eax
  struct ITSWndPluginEx **v266; // rax
  __int64 v267; // rdx
  __int64 v268; // rcx
  __int64 v269; // r8
  int v270; // eax
  int v271; // edx
  const char *v272; // rcx
  __int64 v273; // rdi
  __int64 (__fastcall *v274)(__int64, _QWORD, _QWORD, void *); // rbx
  void *v275; // rax
  __int64 v276; // rdx
  __int64 v277; // rcx
  __int64 v278; // r8
  __int64 v279; // rsi
  BOOL v280; // ebx
  __int64 (__fastcall *v281)(__int64, __int64, BOOL); // rdi
  __int64 v282; // rax
  __int64 v283; // rdx
  __int64 v284; // rcx
  __int64 v285; // r8
  __int64 v286; // rdx
  __int64 v287; // rcx
  __int64 v288; // r8
  unsigned int v289; // eax
  __int64 v290; // rdx
  struct RdpXInterfaceRemoteAppWindow **v291; // rax
  __int64 v292; // rdx
  __int64 v293; // rcx
  __int64 v294; // r8
  int v295; // ebx
  unsigned int v296; // eax
  struct ITSWndPluginEx **v297; // rax
  int WndPlugin; // eax
  __int64 v299; // rdx
  __int64 v300; // rcx
  __int64 v301; // r8
  int v302; // eax
  int v303; // edx
  const char *v304; // rcx
  unsigned __int16 v305; // r14
  int v306; // esi
  __int64 v307; // rcx
  unsigned int v308; // esi
  __int64 v309; // rdi
  __int64 v310; // rbx
  __int64 v311; // r14
  __int64 (__fastcall *v312)(__int64, _QWORD, _QWORD, __int64, _DWORD, _DWORD, char *, _DWORD, __int64, _DWORD, __int64, _DWORD, void *); // rsi
  void *v313; // rax
  __int64 v314; // r9
  __int64 v315; // rdx
  __int64 v316; // rcx
  __int64 v317; // r8
  __int64 v318; // rsi
  __int64 (__fastcall *v319)(__int64, __int64, _QWORD); // rdi
  unsigned int v320; // ebx
  __int64 v321; // rax
  __int64 v322; // rdx
  __int64 v323; // rcx
  __int64 v324; // r8
  __int64 v325; // rdx
  __int64 v326; // rcx
  __int64 v327; // r8
  unsigned int v328; // eax
  struct RdpXInterfaceRemoteAppWindow **v329; // rax
  __int64 v330; // rdx
  __int64 v331; // rcx
  __int64 v332; // r8
  int v333; // ebx
  unsigned int v334; // eax
  struct ITSWndPluginEx **v335; // rax
  __int64 v336; // rdx
  __int64 v337; // rcx
  __int64 v338; // r8
  int v339; // eax
  int v340; // edx
  const char *v341; // rcx
  __int64 v342; // rdi
  __int64 v343; // rax
  int v344; // ebx
  __int64 v345; // rax
  __int64 v346; // rdi
  __int64 (__fastcall *v347)(__int64, _QWORD); // rbx
  __int64 v348; // rax
  unsigned int v349; // eax
  unsigned int v350; // eax
  __int64 v351; // rdx
  __int64 v352; // rcx
  __int64 v353; // r8
  __int64 v354; // rdx
  __int64 v355; // r8
  __int64 v356; // rcx
  unsigned int v357; // eax
  __int64 v358; // rdx
  unsigned int v359; // r14d
  __int64 v360; // rdx
  __int64 v361; // rcx
  __int64 v362; // r8
  unsigned int v363; // eax
  struct RdpXInterfaceRemoteAppWindow **v364; // rax
  __int64 v365; // rdx
  __int64 v366; // rcx
  __int64 v367; // r8
  int v368; // ebx
  unsigned int v369; // eax
  __int64 v370; // rax
  int v371; // r14d
  int v372; // esi
  int v373; // edi
  int v374; // ebx
  __int64 *v375; // rax
  __int64 v376; // rcx
  __int64 v377; // rax
  __int64 v378; // rax
  __int64 v379; // rax
  __int64 v380; // rax
  __int64 v381; // rax
  __int64 v382; // rax
  __int64 v383; // rax
  __int64 v384; // rdx
  __int64 v385; // rcx
  char *v386; // rdi
  __int64 v387; // r8
  unsigned int v388; // eax
  int v389; // esi
  RdpRemoteAppCore *v390; // r14
  __int64 v391; // rdx
  __int64 v392; // rax
  __int64 v393; // rax
  __int64 v394; // rax
  __int64 v395; // rdx
  __int64 v396; // r8
  __int64 v397; // rcx
  unsigned int v398; // eax
  __int64 v399; // rdx
  unsigned int v400; // r14d
  unsigned int v401; // eax
  struct RdpXInterfaceRemoteAppWindow **v402; // rax
  __int64 v403; // rdx
  __int64 v404; // rcx
  __int64 v405; // r8
  int v406; // ebx
  unsigned int v407; // eax
  __int64 v408; // rax
  __int64 v409; // rax
  __int64 v410; // rax
  __int64 v411; // rax
  __int64 v412; // rax
  __int64 v413; // rdx
  __int64 v414; // r8
  __int64 v415; // rcx
  unsigned int v416; // eax
  __int64 v417; // rdx
  int v418; // eax
  unsigned int v419; // r15d
  unsigned int v420; // r14d
  unsigned int v421; // eax
  struct ITSWndPluginEx **v422; // rax
  int v423; // r14d
  __int64 v424; // rdx
  __int64 v425; // rcx
  __int64 v426; // r8
  int v427; // eax
  struct RdpXInterfaceRemoteAppWindow **v428; // rax
  void *v429; // rax
  unsigned int WindowCallbacks; // eax
  __int64 v431; // rdx
  __int64 v432; // rcx
  __int64 v433; // r8
  int v434; // eax
  int v435; // edx
  const char *v436; // rcx
  void *v437; // rax
  unsigned int Object; // eax
  __int64 v439; // rdx
  __int64 v440; // rcx
  __int64 v441; // r8
  __int64 v442; // rdi
  __int64 (__fastcall *v443)(__int64, void *); // rbx
  void *v444; // rax
  __int64 v445; // rdx
  __int64 v446; // rcx
  __int64 v447; // r8
  __int64 v448; // rdi
  __int64 (__fastcall *v449)(__int64, __int64); // rbx
  __int64 v450; // rax
  unsigned int v451; // eax
  __int64 v452; // rdx
  __int64 v453; // rcx
  __int64 v454; // r8
  __int64 v455; // r15
  __int64 (__fastcall *v456)(__int64, __int64, _QWORD, __int64, __int128 *, void *); // r14
  void *v457; // rbx
  __int64 v458; // rax
  unsigned int v459; // esi
  __int64 v460; // rdi
  __int64 v461; // rax
  unsigned int v462; // eax
  __int64 v463; // rdx
  __int64 v464; // rcx
  __int64 v465; // r8
  __int64 v466; // rdi
  __int64 (__fastcall *v467)(__int64, bool); // rbx
  __int64 v468; // rax
  int v469; // eax
  unsigned int v470; // eax
  __int64 v471; // rax
  __int64 v472; // rax
  __int64 v473; // rax
  __int64 v474; // rax
  __int64 v475; // rax
  __int64 v476; // rax
  int v477; // r15d
  int v478; // r14d
  int v479; // ebx
  __int64 *v480; // rax
  __int64 v481; // rcx
  __int64 v482; // rax
  __int64 v483; // rax
  __int64 v484; // rax
  __int64 v485; // rdx
  __int64 v486; // rcx
  char *v487; // rbx
  __int64 v488; // r8
  unsigned int v489; // eax
  __int64 v490; // rdx
  __int64 v491; // rax
  __int64 v492; // rax
  __int64 v493; // rax
  __int64 v494; // rdi
  void (__fastcall *v495)(__int64, _QWORD); // rbx
  __int64 v496; // rax
  unsigned int v497; // eax
  __int64 v498; // rax
  __int64 v499; // rdx
  __int64 v500; // rcx
  __int64 v501; // r8
  unsigned int v502; // eax
  struct RdpXInterfaceRemoteAppWindow **v503; // rax
  __int64 v504; // rdx
  __int64 v505; // rcx
  __int64 v506; // r8
  int v507; // ebx
  unsigned int v508; // eax
  int v509; // ebx
  unsigned int v510; // eax
  __int64 v511; // rax
  int v512; // ebx
  unsigned int v513; // eax
  __int64 v514; // rax
  __int64 v515; // rdx
  __int64 v516; // rdx
  __int64 v517; // rcx
  __int64 v518; // r8
  unsigned int v519; // eax
  char *v520; // rcx
  struct ITSWndPluginEx **v521; // rax
  __int64 v522; // rdx
  __int64 v523; // rcx
  __int64 v524; // r8
  int v525; // eax
  unsigned int v526; // eax
  __int64 v527; // rax
  __int64 v528; // rdx
  HKEY v529; // rax
  unsigned int v530; // eax
  unsigned int v531; // eax
  __int64 v532; // rax
  RdpRemoteAppCore *v533; // rbx
  __int64 v534; // rax
  unsigned int v535; // r15d
  __int64 v536; // rdi
  __int64 (__fastcall *v537)(__int64, _QWORD, void *); // rbx
  void *v538; // rax
  __int64 v539; // rdx
  __int64 v540; // rcx
  int v541; // ebx
  __int64 v542; // r8
  __int64 v543; // rax
  unsigned int v544; // eax
  __int64 v545; // rax
  unsigned int v546; // eax
  __int64 v547; // rax
  __int64 v548; // rdx
  __int64 v549; // rcx
  __int64 v550; // r8
  unsigned int v551; // eax
  __int64 v552; // rdx
  unsigned int v553; // eax
  unsigned int v554; // esi
  wchar_t *v555; // rcx
  size_t v556; // rdx
  unsigned int v557; // eax
  int v558; // esi
  unsigned int v559; // ebx
  __int64 v560; // r9
  const unsigned __int16 *v561; // r8
  __int64 v562; // rdx
  __int64 v563; // rcx
  __int64 v564; // r8
  int v565; // eax
  struct ITSWndPluginEx **v566; // rax
  __int64 v567; // rdx
  __int64 v568; // rcx
  __int64 v569; // r8
  int v570; // eax
  unsigned int v571; // ebx
  __int64 v572; // rax
  __int64 v573; // rdx
  __int64 v574; // rcx
  __int64 v575; // r8
  unsigned int v576; // eax
  char *v577; // rcx
  struct ITSWndPluginEx **v578; // rax
  __int64 v579; // rdx
  __int64 v580; // rcx
  __int64 v581; // r8
  int v582; // eax
  int v583; // edx
  const char *v584; // rcx
  __int64 v585; // rdi
  __int64 (__fastcall *v586)(__int64, _QWORD, _QWORD, void *); // rbx
  void *v587; // rax
  __int64 v588; // rdx
  __int64 v589; // rcx
  __int64 v590; // r8
  __int64 v591; // rax
  __int64 v592; // rax
  struct RdpXInterfaceShellNotifyInformation *v593; // rbx
  __int64 v594; // rax
  unsigned int v595; // eax
  __int64 v596; // rdx
  __int64 v597; // rcx
  __int64 v598; // r8
  __int64 v599; // rcx
  __int64 v600; // r8
  __int64 v601; // rdx
  unsigned int v602; // eax
  __int64 v603; // rdx
  __int64 v604; // rcx
  unsigned int v605; // esi
  struct ITSWndPluginEx **v606; // rax
  __int64 v607; // rdx
  __int64 v608; // rcx
  __int64 v609; // r8
  int v610; // eax
  int v611; // edx
  const char *v612; // rcx
  __int64 v613; // rdi
  __int64 (__fastcall *v614)(__int64, _QWORD, _QWORD, void *); // rbx
  void *v615; // rax
  __int64 v616; // rdx
  __int64 v617; // rcx
  __int64 v618; // r8
  __int64 v619; // rax
  __int64 v620; // rbx
  char *v621; // r14
  void *v622; // rax
  unsigned int ConstXChar16StringWithSpecifiedSize; // eax
  __int64 v624; // rdx
  __int64 v625; // rcx
  __int64 v626; // r8
  int v627; // eax
  char *v628; // r15
  void *v629; // rax
  unsigned int v630; // eax
  __int64 v631; // rdx
  __int64 v632; // rcx
  __int64 v633; // r8
  int v634; // eax
  int v635; // edx
  const char *v636; // rcx
  const wchar_t *v637; // rbx
  __int64 v638; // rax
  const wchar_t *v639; // rsi
  __int64 v640; // rax
  __int64 v641; // rax
  __int64 v642; // rdx
  __int64 v643; // rcx
  __int64 v644; // r8
  struct RdpXInterfaceShellNotifyInformation *v645; // rbx
  __int64 v646; // rax
  unsigned int v647; // eax
  __int64 v648; // rdx
  __int64 v649; // rcx
  __int64 v650; // r8
  __int64 v651; // rdx
  __int64 v652; // r8
  __int64 v653; // rcx
  unsigned int v654; // eax
  __int64 v655; // rdx
  unsigned int v656; // r14d
  struct ITSWndPluginEx **v657; // rax
  __int64 v658; // rdx
  __int64 v659; // rcx
  __int64 v660; // r8
  int v661; // eax
  int v662; // edx
  const char *v663; // rcx
  __int64 v664; // rdi
  __int64 (__fastcall *v665)(__int64, _QWORD, _QWORD, void *); // rbx
  void *v666; // rax
  int v667; // eax
  __int64 v668; // rdx
  __int64 v669; // rcx
  __int64 v670; // r8
  unsigned __int16 v671; // di
  __int64 v672; // rax
  __int64 v673; // rax
  __int64 v674; // rdx
  __int64 v675; // rcx
  __int64 v676; // r8
  int v677; // eax
  int v678; // edx
  const char *v679; // rcx
  void *v680; // rax
  unsigned int v681; // eax
  __int64 v682; // rdx
  __int64 v683; // rcx
  __int64 v684; // r8
  __int64 v685; // rax
  __int64 v686; // rdx
  __int64 v687; // rcx
  __int64 v688; // r8
  __int64 v689; // rdx
  __int64 v690; // rcx
  __int64 v691; // r8
  __int64 v692; // rsi
  unsigned int v693; // eax
  unsigned int v694; // ebx
  RdpRemoteAppCore *v695; // r14
  unsigned int v696; // eax
  __int64 v697; // rdx
  int v698; // r15d
  __int64 v699; // rax
  const wchar_t *v700; // rbx
  __int64 v701; // rdi
  __int64 (__fastcall *v702)(__int64, _QWORD, _QWORD, void *); // rbx
  void *v703; // rax
  __int64 v704; // rdx
  __int64 v705; // rcx
  __int64 v706; // r8
  int v707; // eax
  int v708; // edx
  const char *v709; // rcx
  unsigned int v710; // ebx
  __int64 v711; // rdx
  __int64 v712; // r8
  __int64 v713; // rcx
  int v714; // eax
  unsigned int v715; // ebx
  __int64 v716; // rax
  const wchar_t *v717; // rbx
  __int64 v718; // rdi
  __int64 (__fastcall *v719)(__int64, _QWORD, _QWORD, char *, _DWORD, _DWORD, char *, int, RdpRemoteAppCore *, _DWORD, char *, _DWORD, void *); // rbx
  void *v720; // rax
  char *v721; // r9
  __int64 v722; // rdx
  __int64 v723; // rcx
  __int64 v724; // r8
  __int64 v725; // rdi
  __int64 (__fastcall *v726)(__int64, __int64); // rbx
  __int64 v727; // rax
  __int64 v728; // rdx
  __int64 v729; // rcx
  __int64 v730; // r8
  __int64 v731; // rax
  const wchar_t *v732; // rbx
  __int64 v733; // rax
  struct RdpXInterfaceShellNotifyInformation *v734; // rbx
  __int64 v735; // rax
  unsigned int v736; // eax
  __int64 v737; // rdx
  __int64 v738; // rcx
  __int64 v739; // r8
  __int64 v740; // rdx
  __int64 v741; // r8
  __int64 v742; // rcx
  unsigned int v743; // eax
  __int64 v744; // rdx
  unsigned int v745; // r15d
  struct ITSWndPluginEx **v746; // rax
  __int64 v747; // rdx
  __int64 v748; // rcx
  __int64 v749; // r8
  int v750; // eax
  int v751; // edx
  const char *v752; // rcx
  __int64 v753; // rdi
  int (__fastcall *v754)(__int64, _QWORD, _QWORD, void *); // rbx
  void *v755; // rax
  __int64 v756; // rdi
  __int64 (__fastcall *v757)(__int64, _QWORD, _QWORD, void *); // rbx
  void *v758; // rax
  __int64 v759; // rdx
  __int64 v760; // rcx
  __int64 v761; // r8
  __int64 v762; // rax
  int v763; // ebx
  int v764; // edi
  unsigned int v765; // eax
  __int64 v766; // rax
  __int64 v767; // rax
  __int64 v768; // rax
  __int64 v769; // rax
  __int64 v770; // rax
  __int64 v771; // rdx
  __int64 v772; // rcx
  __int64 v773; // r8
  int v774; // eax
  int v775; // edx
  const char *v776; // rcx
  void *v777; // rax
  unsigned int v778; // eax
  __int64 v779; // rdx
  __int64 v780; // rcx
  __int64 v781; // r8
  __int64 v782; // rax
  __int64 v783; // rdx
  __int64 v784; // rcx
  __int64 v785; // r8
  __int64 v786; // rdx
  __int64 v787; // rcx
  __int64 v788; // r8
  __int64 v789; // rsi
  unsigned int v790; // eax
  unsigned int v791; // edi
  RdpRemoteAppCore *v792; // r15
  unsigned int v793; // eax
  __int64 v794; // rdx
  __int64 v795; // rax
  const wchar_t *v796; // rbx
  __int64 v797; // rdi
  __int64 (__fastcall *v798)(__int64, _QWORD, _QWORD, void *); // rbx
  void *v799; // rax
  __int64 v800; // rdx
  __int64 v801; // rcx
  __int64 v802; // r8
  int v803; // eax
  int v804; // edx
  const char *v805; // rcx
  unsigned int v806; // edi
  unsigned int v807; // r9d
  __int64 v808; // r8
  __int64 v809; // rcx
  unsigned int v810; // edi
  __int64 v811; // rax
  const wchar_t *v812; // rbx
  __int64 v813; // rdi
  __int64 (__fastcall *v814)(__int64, _QWORD, _QWORD, __int64, _DWORD, _DWORD, char *, _DWORD, __int64, _DWORD, __int64, _DWORD, void *); // rbx
  void *v815; // rax
  __int64 v816; // r9
  __int64 v817; // rdi
  __int64 (__fastcall *v818)(__int64, __int64); // rbx
  __int64 v819; // rax
  __int64 v820; // rdx
  __int64 v821; // rcx
  __int64 v822; // r8
  __int64 v823; // rax
  const wchar_t *v824; // rbx
  struct RdpXInterfaceShellNotifyInformation *v825; // rbx
  __int64 v826; // rax
  unsigned int v827; // eax
  __int64 v828; // rdx
  __int64 v829; // rcx
  __int64 v830; // r8
  HKEY v831; // rdx
  unsigned int v832; // eax
  __int64 v833; // rsi
  unsigned int v834; // eax
  __int64 v835; // r15
  unsigned int v836; // eax
  int v837; // edx
  char *v838; // rcx
  unsigned int v839; // esi
  size_t cchToCopy; // [rsp+20h] [rbp-120h]
  size_t cchToCopya; // [rsp+20h] [rbp-120h]
  size_t cchToCopyb; // [rsp+20h] [rbp-120h]
  size_t cchToCopyc; // [rsp+20h] [rbp-120h]
  unsigned __int16 *v845; // [rsp+28h] [rbp-118h]
  unsigned __int16 *v846; // [rsp+28h] [rbp-118h]
  unsigned __int16 *v847; // [rsp+28h] [rbp-118h]
  int v848; // [rsp+28h] [rbp-118h]
  __int64 v849; // [rsp+30h] [rbp-110h]
  __int64 v850; // [rsp+30h] [rbp-110h]
  __int64 v851; // [rsp+30h] [rbp-110h]
  __int64 v852; // [rsp+38h] [rbp-108h]
  __int64 v853; // [rsp+38h] [rbp-108h]
  __int64 v854; // [rsp+40h] [rbp-100h]
  __int64 v855; // [rsp+40h] [rbp-100h]
  char v856[8]; // [rsp+C0h] [rbp-80h] BYREF
  char v857[8]; // [rsp+C8h] [rbp-78h] BYREF
  char v858[8]; // [rsp+D0h] [rbp-70h] BYREF
  int v859; // [rsp+D8h] [rbp-68h]
  char v860[8]; // [rsp+E0h] [rbp-60h] BYREF
  struct ITSWndPluginEx *v861; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v862; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v863; // [rsp+F8h] [rbp-48h] BYREF
  char v864[8]; // [rsp+100h] [rbp-40h] BYREF
  char v865[8]; // [rsp+108h] [rbp-38h] BYREF
  struct RdpXInterfaceRemoteAppWindow *v866; // [rsp+110h] [rbp-30h] BYREF
  char v867[8]; // [rsp+118h] [rbp-28h] BYREF
  _BYTE v868[16]; // [rsp+120h] [rbp-20h] BYREF
  RdpRemoteAppCore *v869; // [rsp+130h] [rbp-10h] BYREF
  int v870; // [rsp+138h] [rbp-8h]
  int v871; // [rsp+13Ch] [rbp-4h]
  char v872[8]; // [rsp+140h] [rbp+0h] BYREF
  char v873[8]; // [rsp+148h] [rbp+8h] BYREF
  __int64 v874; // [rsp+150h] [rbp+10h] BYREF
  int v875; // [rsp+158h] [rbp+18h]
  int v876; // [rsp+15Ch] [rbp+1Ch]
  char v877[8]; // [rsp+160h] [rbp+20h] BYREF
  char v878[8]; // [rsp+168h] [rbp+28h] BYREF
  unsigned int v879; // [rsp+170h] [rbp+30h]
  int v880; // [rsp+174h] [rbp+34h]
  int v881; // [rsp+178h] [rbp+38h]
  __int64 *v882; // [rsp+180h] [rbp+40h] BYREF
  struct RdpXInterfaceRemoteAppWindow *v883; // [rsp+188h] [rbp+48h] BYREF
  char v884[8]; // [rsp+190h] [rbp+50h] BYREF
  char v885[8]; // [rsp+198h] [rbp+58h] BYREF
  char v886[8]; // [rsp+1A0h] [rbp+60h] BYREF
  char v887[8]; // [rsp+1A8h] [rbp+68h] BYREF
  char v888[8]; // [rsp+1B0h] [rbp+70h] BYREF
  __int64 v889; // [rsp+1B8h] [rbp+78h] BYREF
  struct RdpXInterfaceRemoteAppWindow *v890; // [rsp+1C0h] [rbp+80h] BYREF
  char v891[8]; // [rsp+1C8h] [rbp+88h] BYREF
  char v892[8]; // [rsp+1D0h] [rbp+90h] BYREF
  char v893[8]; // [rsp+1D8h] [rbp+98h] BYREF
  __int64 v894; // [rsp+1E0h] [rbp+A0h] BYREF
  char v895[8]; // [rsp+1E8h] [rbp+A8h] BYREF
  char v896[8]; // [rsp+1F0h] [rbp+B0h] BYREF
  char v897[8]; // [rsp+1F8h] [rbp+B8h] BYREF
  char v898[8]; // [rsp+200h] [rbp+C0h] BYREF
  char v899[8]; // [rsp+208h] [rbp+C8h] BYREF
  char v900[8]; // [rsp+210h] [rbp+D0h] BYREF
  __int64 v901; // [rsp+218h] [rbp+D8h] BYREF
  struct RdpXInterfaceRemoteAppWindow *v902; // [rsp+220h] [rbp+E0h] BYREF
  struct RdpXInterfaceRemoteAppWindow *v903; // [rsp+228h] [rbp+E8h] BYREF
  char v904[8]; // [rsp+230h] [rbp+F0h] BYREF
  char v905[8]; // [rsp+238h] [rbp+F8h] BYREF
  int v906; // [rsp+240h] [rbp+100h]
  int v907; // [rsp+244h] [rbp+104h]
  int v908; // [rsp+248h] [rbp+108h]
  int v909; // [rsp+24Ch] [rbp+10Ch]
  unsigned int v910; // [rsp+250h] [rbp+110h]
  int v911; // [rsp+254h] [rbp+114h]
  int v912; // [rsp+258h] [rbp+118h]
  char v913[8]; // [rsp+260h] [rbp+120h] BYREF
  char v914[8]; // [rsp+268h] [rbp+128h] BYREF
  char v915[8]; // [rsp+270h] [rbp+130h] BYREF
  __int64 v916; // [rsp+278h] [rbp+138h] BYREF
  __int64 v917; // [rsp+280h] [rbp+140h] BYREF
  struct RdpXInterfaceRemoteAppWindow *v918; // [rsp+288h] [rbp+148h] BYREF
  struct RdpXInterfaceRemoteAppWindow *v919; // [rsp+290h] [rbp+150h] BYREF
  struct RdpXInterfaceRemoteAppWindow *v920; // [rsp+298h] [rbp+158h] BYREF
  char v921[8]; // [rsp+2A0h] [rbp+160h] BYREF
  struct RdpXInterfaceRemoteAppWindow *v922; // [rsp+2A8h] [rbp+168h] BYREF
  char v923[8]; // [rsp+2B0h] [rbp+170h] BYREF
  unsigned __int16 *v924; // [rsp+2B8h] [rbp+178h] BYREF
  unsigned __int64 v925; // [rsp+2C0h] [rbp+180h] BYREF
  _DWORD v926[2]; // [rsp+2C8h] [rbp+188h] BYREF
  int v927; // [rsp+2D0h] [rbp+190h]
  int v928; // [rsp+2D4h] [rbp+194h]
  __int128 v929; // [rsp+2D8h] [rbp+198h] BYREF
  _DWORD v930[4]; // [rsp+2E8h] [rbp+1A8h] BYREF
  _DWORD v931[4]; // [rsp+2F8h] [rbp+1B8h] BYREF
  __int128 v932; // [rsp+308h] [rbp+1C8h] BYREF
  _OWORD v933[2]; // [rsp+318h] [rbp+1D8h] BYREF
  __int64 v934; // [rsp+338h] [rbp+1F8h]
  unsigned __int16 Destination[264]; // [rsp+340h] [rbp+200h] BYREF
  unsigned __int16 v936[264]; // [rsp+550h] [rbp+410h] BYREF
  wchar_t pszDest[264]; // [rsp+760h] [rbp+620h] BYREF
  wchar_t v938[264]; // [rsp+970h] [rbp+830h] BYREF

  v3 = a3;
  v869 = this;
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
    ActivityIdPrefix = ((__int64 (*)(void))RdpX_GetActivityIdPrefix)();
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
        RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v921);
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
          v503 = (struct RdpXInterfaceRemoteAppWindow **)CacCommon::Rect<int>::Rect<int>(v921);
          RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow(
                              (RdpRemoteAppCore *)((char *)v5 - 48),
                              *((_DWORD *)v4 + 1),
                              v503);
          if ( RemoteAppWindow >= 0 )
          {
            if ( (*((_BYTE *)v4 + 8) & 0x40) != 0 )
            {
              if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                v509 = *((unsigned __int8 *)v4 + 12);
                v510 = RdpX_GetActivityIdPrefix(v505, v504, v506);
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  163,
                  &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                  v510,
                  v509);
              }
              v511 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v921);
              (*(void (__fastcall **)(__int64, bool))(*(_QWORD *)v511 + 344LL))(v511, *((_BYTE *)v4 + 12) == 1);
            }
            if ( (*((_BYTE *)v4 + 8) & 1) != 0 )
            {
              if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                v512 = *((unsigned __int8 *)v4 + 13);
                v513 = RdpX_GetActivityIdPrefix(v505, v504, v506);
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  164,
                  &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                  v513,
                  v512);
              }
              v514 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v921);
              LOBYTE(v515) = *((_BYTE *)v4 + 13);
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v514 + 352LL))(v514, v515);
            }
          }
          else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                 && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v507 = *((_DWORD *)v4 + 1);
            v508 = RdpX_GetActivityIdPrefix(v505, v504, v506);
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              162,
              &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v508,
              v507);
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v502 = RdpX_GetActivityIdPrefix(v500, v499, v501);
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              161,
              &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v502,
              -2147418113);
          }
          RemoteAppWindow = -2147418113;
        }
        v259 = v921;
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
                RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v896);
                RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v895);
                RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v905);
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
                      v258 = RdpX_GetActivityIdPrefix(v256, v255, v257);
                      WPP_SF_Dd(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        156,
                        &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                        v258,
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
                v260 = (struct RdpXInterfaceRemoteAppWindow **)CacCommon::Rect<int>::Rect<int>(v896);
                RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow(
                                    (RdpRemoteAppCore *)((char *)v5 - 48),
                                    *((_DWORD *)v4 + 1),
                                    v260);
                if ( RemoteAppWindow < 0 )
                {
                  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                    && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v264 = *((_DWORD *)v4 + 1);
                    v265 = RdpX_GetActivityIdPrefix(v262, v261, v263);
                    WPP_SF_Dd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      157,
                      &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                      v265,
                      v264);
                  }
                  goto LABEL_434;
                }
                v266 = (struct ITSWndPluginEx **)CacCommon::Rect<int>::Rect<int>(v895);
                RemoteAppWindow = RdpRemoteAppCore::GetWndPlugin((RdpRemoteAppCore *)((char *)v5 - 48), v266);
                if ( RemoteAppWindow >= 0 )
                {
                  v273 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v895);
                  v274 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, void *))(*(_QWORD *)v273 + 56LL);
                  v275 = CacCommon::Rect<int>::Rect<int>(v905);
                  RemoteAppWindow = v274(v273, *((unsigned __int8 *)v4 + 14), *((unsigned __int16 *)v4 + 6), v275);
                  if ( RemoteAppWindow >= 0 )
                  {
                    v279 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v896);
                    v280 = *((_BYTE *)v4 + 15) == 1;
                    v281 = *(__int64 (__fastcall **)(__int64, __int64, BOOL))(*(_QWORD *)v279 + 88LL);
                    v282 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v905);
                    RemoteAppWindow = v281(v279, v282, v280);
                    if ( RemoteAppWindow >= 0
                      || WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                    {
                      goto LABEL_434;
                    }
                    v270 = RdpX_GetActivityIdPrefix(v284, v283, v285);
                    v271 = 160;
                    v272 = "UpdateIcon failed";
                  }
                  else
                  {
                    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                    {
                      goto LABEL_434;
                    }
                    v270 = RdpX_GetActivityIdPrefix(v277, v276, v278);
                    v271 = 159;
                    v272 = "CreateCachedIcon failed";
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
                  v270 = RdpX_GetActivityIdPrefix(v268, v267, v269);
                  v271 = 158;
                  v272 = "GetWndPlugin failed";
                }
                WPP_SF_DsD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v271,
                  (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                  v270,
                  (__int64)v272,
                  RemoteAppWindow);
LABEL_434:
                RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v905);
                TCntPtr<ITSViewerRecorder>::SafeRelease(v895);
                v259 = v896;
LABEL_629:
                RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v259);
                return (unsigned int)RemoteAppWindow;
              }
              RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v893);
              RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v892);
              RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v891);
              LOWORD(v859) = 32;
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
                  v289 = RdpX_GetActivityIdPrefix(v287, v286, v288);
                  v290 = 150;
LABEL_462:
                  WPP_SF_Dd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    v290,
                    &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                    v289,
                    -2147418113);
LABEL_463:
                  RemoteAppWindow = -2147418113;
LABEL_464:
                  RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v891);
                  TCntPtr<ITSViewerRecorder>::SafeRelease(v892);
                  v259 = v893;
                  goto LABEL_629;
                }
              }
              v291 = (struct RdpXInterfaceRemoteAppWindow **)CacCommon::Rect<int>::Rect<int>(v893);
              RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow(
                                  (RdpRemoteAppCore *)((char *)v5 - 48),
                                  *((_DWORD *)v4 + 1),
                                  v291);
              if ( RemoteAppWindow < 0 )
              {
                if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                  && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v295 = *((_DWORD *)v4 + 1);
                  v296 = RdpX_GetActivityIdPrefix(v293, v292, v294);
                  WPP_SF_Dd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    151,
                    &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                    v296,
                    v295);
                }
                goto LABEL_464;
              }
              v297 = (struct ITSWndPluginEx **)CacCommon::Rect<int>::Rect<int>(v892);
              WndPlugin = RdpRemoteAppCore::GetWndPlugin((RdpRemoteAppCore *)((char *)v5 - 48), v297);
              RemoteAppWindow = WndPlugin;
              if ( WndPlugin >= 0 )
              {
                if ( (*((_BYTE *)v4 + 15) & 2) != 0 )
                {
                  LOBYTE(WndPlugin) = *((_BYTE *)v4 + 20);
                  v305 = *((_WORD *)v4 + 11);
                  LOWORD(v859) = WndPlugin;
                }
                else
                {
                  v305 = 0;
                }
                v306 = *((_DWORD *)v4 + 6) + 32;
                v307 = (unsigned int)v305 + *((_DWORD *)v4 + 7);
                LODWORD(v874) = v305;
                v308 = v307 + v306;
                if ( *((unsigned __int16 *)v4 + 1) < v308 )
                  RdpRemoteAppCore::LogRemoteAppError(
                    (char *)v5 + 16,
                    L"Invalid size of TS_RAIL_ORDER_WINDOW_ICON_BODY PDU",
                    2147549183LL,
                    0,
                    0);
                if ( *((unsigned __int16 *)v4 + 1) < v308 )
                {
                  if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                    || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                  {
                    goto LABEL_463;
                  }
                  v289 = RdpX_GetActivityIdPrefix(v307, v299, v301);
                  v290 = 153;
                  goto LABEL_462;
                }
                LODWORD(cchToCopy) = *((unsigned __int8 *)v4 + 8);
                RdpRemoteAppCore::LogRemoteAppEventF(
                  (char *)v869 + 16,
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
                v309 = (__int64)v4 + v305 + 32;
                v310 = v309 + *((unsigned int *)v4 + 6);
                v311 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v892);
                v312 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64, _DWORD, _DWORD, char *, _DWORD, __int64, _DWORD, __int64, _DWORD, void *))(*(_QWORD *)v311 + 64LL);
                v313 = CacCommon::Rect<int>::Rect<int>(v891);
                v314 = *((unsigned __int16 *)v4 + 9);
                LOBYTE(v314) = v859;
                RemoteAppWindow = v312(
                                    v311,
                                    *((unsigned __int8 *)v4 + 14),
                                    *((unsigned __int16 *)v4 + 6),
                                    v314,
                                    *((unsigned __int16 *)v4 + 8),
                                    *((unsigned __int16 *)v4 + 9),
                                    (char *)v4 + 32,
                                    v874,
                                    v309,
                                    *((_DWORD *)v4 + 6),
                                    v310,
                                    *((_DWORD *)v4 + 7),
                                    v313);
                if ( RemoteAppWindow >= 0 )
                {
                  v318 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v893);
                  v319 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v318 + 88LL);
                  v320 = *((_BYTE *)v4 + 15) & 1;
                  v321 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v891);
                  RemoteAppWindow = v319(v318, v321, v320);
                  if ( RemoteAppWindow >= 0
                    || WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                    || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                  {
                    goto LABEL_464;
                  }
                  v302 = RdpX_GetActivityIdPrefix(v323, v322, v324);
                  v303 = 155;
                  v304 = "UpdateIcon failed";
                }
                else
                {
                  if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                    || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                  {
                    goto LABEL_464;
                  }
                  v302 = RdpX_GetActivityIdPrefix(v316, v315, v317);
                  v303 = 154;
                  v304 = "CreateCachedIcon failed";
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
                v302 = RdpX_GetActivityIdPrefix(v300, v299, v301);
                v303 = 152;
                v304 = "GetWndPlugin failed";
              }
              WPP_SF_DsD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v303,
                (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                v302,
                (__int64)v304,
                RemoteAppWindow);
              goto LABEL_464;
            }
            RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v898);
            RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v897);
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
                  v328 = RdpX_GetActivityIdPrefix(v326, v325, v327);
                  WPP_SF_Dd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    146,
                    &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                    v328,
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
            v329 = (struct RdpXInterfaceRemoteAppWindow **)CacCommon::Rect<int>::Rect<int>(v898);
            RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow(
                                (RdpRemoteAppCore *)((char *)v5 - 48),
                                *((_DWORD *)v4 + 1),
                                v329);
            if ( RemoteAppWindow < 0 )
            {
              if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v333 = *((_DWORD *)v4 + 1);
                v334 = RdpX_GetActivityIdPrefix(v331, v330, v332);
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  147,
                  &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                  v334,
                  v333);
              }
              goto LABEL_503;
            }
            v335 = (struct ITSWndPluginEx **)CacCommon::Rect<int>::Rect<int>(v897);
            RemoteAppWindow = RdpRemoteAppCore::GetWndPlugin((RdpRemoteAppCore *)((char *)v5 - 48), v335);
            if ( RemoteAppWindow >= 0 )
            {
              v342 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v898);
              v343 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v897);
              v344 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v343 + 88LL))(v343);
              if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v342 + 72LL))(v342) == v344 )
              {
                v345 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v897);
                (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v345 + 96LL))(v345, 0);
              }
              v346 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *((char *)v869 + 128);
              v347 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v346 + 64LL);
              v348 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v898);
              v349 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v348 + 72LL))(v348);
              v350 = v347(v346, v349);
              RemoteAppWindow = MapXResultToHR(v350);
              if ( RemoteAppWindow >= 0
                || WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_503;
              }
              v339 = RdpX_GetActivityIdPrefix(v352, v351, v353);
              v340 = 149;
              v341 = "DeleteWindow failed";
            }
            else
            {
              if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_503;
              }
              v339 = RdpX_GetActivityIdPrefix(v337, v336, v338);
              v340 = 148;
              v341 = "GetWndPlugin failed";
            }
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v340,
              (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v339,
              (__int64)v341,
              RemoteAppWindow);
LABEL_503:
            TCntPtr<ITSViewerRecorder>::SafeRelease(v897);
            v259 = v898;
            goto LABEL_629;
          }
          RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v864);
          v869 = (RdpRemoteAppCore *)((char *)v5 + 16);
          if ( *((_WORD *)v4 + 1) < 0x58u )
            RdpRemoteAppCore::LogRemoteAppError(
              (char *)v5 + 16,
              L"Invalid size of TS_RAIL_ORDER_WINDOW_GEOMETRY_BODY PDU",
              2147549183LL,
              0,
              0);
          v356 = *((unsigned __int16 *)v4 + 1);
          if ( (unsigned int)v356 < 0x58 )
          {
            if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
              || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_530;
            }
            v357 = RdpX_GetActivityIdPrefix(v356, v354, v355);
            v358 = 141;
LABEL_529:
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v358,
              &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v357,
              -2147418113);
LABEL_530:
            RemoteAppWindow = -2147418113;
LABEL_531:
            v259 = v864;
            goto LABEL_629;
          }
          v359 = 16 * *((unsigned __int16 *)v4 + 34) + 72;
          if ( (unsigned int)v356 < v359 )
            RdpRemoteAppCore::LogRemoteAppError(
              (char *)v5 + 16,
              L"Invalid size of TS_RAIL_ORDER_WINDOW_GEOMETRY_BODY PDU",
              2147549183LL,
              0,
              0);
          if ( *((unsigned __int16 *)v4 + 1) < v359 )
          {
            if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
              || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_530;
            }
            v357 = RdpX_GetActivityIdPrefix(v356, v354, v355);
            v358 = 142;
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
              v363 = RdpX_GetActivityIdPrefix(v361, v360, v362);
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 143, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v363);
            }
            goto LABEL_531;
          }
          v364 = (struct RdpXInterfaceRemoteAppWindow **)CacCommon::Rect<int>::Rect<int>(v864);
          RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow(
                              (RdpRemoteAppCore *)((char *)v5 - 48),
                              *((_DWORD *)v4 + 1),
                              v364);
          if ( RemoteAppWindow < 0 )
          {
            if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
              && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v368 = *((_DWORD *)v4 + 1);
              v369 = RdpX_GetActivityIdPrefix(v366, v365, v367);
              WPP_SF_Dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                144,
                &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                v369,
                v368);
            }
            goto LABEL_531;
          }
          if ( (*((_BYTE *)v4 + 8) & 8) != 0 )
          {
            v370 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v864);
            (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v370 + 80LL))(
              v370,
              *((unsigned int *)v4 + 3),
              *((unsigned int *)v4 + 4));
          }
          if ( *((char *)v4 + 8) < 0 )
          {
            v371 = *((_DWORD *)v4 + 13);
            if ( v371 >= 0 )
            {
              v372 = *((_DWORD *)v4 + 14);
              if ( v372 >= 0 )
              {
                v373 = *((_DWORD *)v4 + 15);
                if ( v373 >= 0 )
                {
                  v374 = *((_DWORD *)v4 + 16);
                  if ( v374 >= 0 )
                  {
                    v375 = (__int64 *)RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v864);
                    v874 = __PAIR64__(v372, v371);
                    v875 = v373;
                    v376 = *v375;
                    v876 = v374;
                    (*(void (__fastcall **)(__int64 *, __int64 *, _QWORD))(v376 + 336))(v375, &v874, 0);
                  }
                }
              }
            }
          }
          if ( (*((_DWORD *)v4 + 2) & 0x8000) != 0 )
          {
            v377 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v864);
            (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v377 + 256LL))(
              v377,
              *((unsigned int *)v4 + 11),
              *((unsigned int *)v4 + 12));
            if ( (*((_DWORD *)v4 + 2) & 0x800) != 0 )
            {
              v378 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v864);
              (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v378 + 224LL))(
                v378,
                (unsigned int)(*((_DWORD *)v4 + 7) + *((_DWORD *)v4 + 11)),
                (unsigned int)(*((_DWORD *)v4 + 8) + *((_DWORD *)v4 + 12)));
            }
          }
          if ( (*((_DWORD *)v4 + 2) & 0x800) != 0 )
          {
            if ( (*((_DWORD *)v4 + 2) & 0x400) != 0 )
            {
              v931[0] = *((_DWORD *)v4 + 7);
              v931[1] = *((_DWORD *)v4 + 8);
              v931[2] = *((_DWORD *)v4 + 9);
              v931[3] = *((_DWORD *)v4 + 10);
              v379 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v864);
              (*(void (__fastcall **)(__int64, _DWORD *, _QWORD))(*(_QWORD *)v379 + 248LL))(v379, v931, 0);
              v380 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v864);
              (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v380 + 160LL))(
                v380,
                *((int *)v4 + 7),
                *((int *)v4 + 8));
              goto LABEL_566;
            }
            v381 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v864);
            (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v381 + 232LL))(
              v381,
              *((unsigned int *)v4 + 7),
              *((unsigned int *)v4 + 8),
              0);
            v382 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v864);
            (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v382 + 160LL))(
              v382,
              *((int *)v4 + 7),
              *((int *)v4 + 8));
          }
          if ( (*((_DWORD *)v4 + 2) & 0x400) != 0 )
          {
            v383 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v864);
            (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v383 + 240LL))(
              v383,
              *((unsigned int *)v4 + 9),
              *((unsigned int *)v4 + 10),
              0);
          }
LABEL_566:
          if ( (*((_DWORD *)v4 + 2) & 0x100) != 0 )
          {
            v386 = (char *)operator new(saturated_mul(*((unsigned __int16 *)v4 + 34), 0x10u));
            if ( !v386 )
            {
              if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v388 = RdpX_GetActivityIdPrefix(v385, v384, v387);
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  145,
                  &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                  v388,
                  -2147024882);
              }
              RemoteAppWindow = -2147024882;
              goto LABEL_531;
            }
            v389 = 0;
            if ( *((_WORD *)v4 + 34) )
            {
              v390 = v869;
              do
              {
                v391 = 16LL * v389;
                *(_DWORD *)&v386[v391] = *(_DWORD *)((char *)v4 + v391 + 72);
                *(_DWORD *)&v386[v391 + 4] = *(_DWORD *)((char *)v4 + v391 + 76);
                *(_DWORD *)&v386[v391 + 8] = *((_DWORD *)v4 + 4 * v389 + 20) - *(_DWORD *)((char *)v4 + v391 + 72);
                *(_DWORD *)&v386[v391 + 12] = *(_DWORD *)((char *)v4 + v391 + 84) - *(_DWORD *)((char *)v4 + v391 + 76);
                LODWORD(v854) = *(_DWORD *)((char *)v4 + v391 + 84);
                LODWORD(v852) = *((_DWORD *)v4 + 4 * v389 + 20);
                LODWORD(v850) = *(_DWORD *)((char *)v4 + v391 + 76);
                LODWORD(v846) = *(_DWORD *)((char *)v4 + v391 + 72);
                LODWORD(cchToCopya) = *((_DWORD *)v4 + 1);
                RdpRemoteAppCore::LogRemoteAppEventF(
                  v390,
                  L"WindowGeometryRailOrderReceived_VisibilityRect[%i]: WindowId=0x%x, Left=%i, Top=%i, Right=%i, Bottom=%i",
                  0,
                  (unsigned int)v389++,
                  cchToCopya,
                  v846,
                  v850,
                  v852,
                  v854);
              }
              while ( v389 < *((unsigned __int16 *)v4 + 34) );
            }
            v392 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v864);
            (*(void (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v392 + 176LL))(
              v392,
              *((unsigned __int16 *)v4 + 34),
              v386);
            v393 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v864);
            (*(void (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v393 + 168LL))(
              v393,
              *((unsigned __int16 *)v4 + 34),
              v386);
            operator delete(v386);
          }
          if ( (*((_BYTE *)v4 + 8) & 0x10) != 0 )
          {
            v394 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v864);
            (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v394 + 128LL))(v394, *((unsigned __int8 *)v4 + 20));
          }
          RemoteAppWindow = 0;
          goto LABEL_531;
        }
        RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v877);
        if ( *((_WORD *)v4 + 1) < 0x1Eu )
          RdpRemoteAppCore::LogRemoteAppError(
            (char *)v5 + 16,
            L"Invalid size of TS_RAIL_ORDER_WINDOW_CHANGE_BODY PDU",
            2147549183LL,
            0,
            0);
        v397 = *((unsigned __int16 *)v4 + 1);
        if ( (unsigned int)v397 >= 0x1E )
        {
          v400 = *((unsigned __int16 *)v4 + 13) + 28;
          if ( (unsigned int)v397 < v400 )
            RdpRemoteAppCore::LogRemoteAppError(
              (char *)v5 + 16,
              L"Invalid size of TS_RAIL_ORDER_WINDOW_CHANGE_BODY PDU",
              2147549183LL,
              0,
              0);
          if ( *((unsigned __int16 *)v4 + 1) >= v400 )
          {
            if ( *((_DWORD *)v4 + 1) == -1 )
            {
              if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                v401 = RdpX_GetActivityIdPrefix(v397, v395, v396);
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  139,
                  &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                  v401);
              }
            }
            else
            {
              v402 = (struct RdpXInterfaceRemoteAppWindow **)CacCommon::Rect<int>::Rect<int>(v877);
              RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow(
                                  (RdpRemoteAppCore *)((char *)v5 - 48),
                                  *((_DWORD *)v4 + 1),
                                  v402);
              if ( RemoteAppWindow >= 0 )
              {
                if ( (*((_BYTE *)v4 + 8) & 2) != 0 )
                {
                  v408 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v877);
                  (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v408 + 120LL))(v408, *((unsigned int *)v4 + 3));
                }
                if ( (*((_BYTE *)v4 + 8) & 8) != 0 )
                {
                  v409 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v877);
                  (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v409 + 80LL))(
                    v409,
                    *((unsigned int *)v4 + 4),
                    *((unsigned int *)v4 + 5));
                }
                if ( (*((_DWORD *)v4 + 2) & 0x80000) != 0 )
                {
                  v410 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v877);
                  (*(void (__fastcall **)(__int64, bool))(*(_QWORD *)v410 + 312LL))(v410, *((_BYTE *)v4 + 25) == 1);
                }
                memset_0(Destination, 0, 0x20Au);
                if ( (*((_BYTE *)v4 + 8) & 4) != 0 && *((_WORD *)v4 + 13) )
                {
                  memcpy_s(Destination, 0x208u, (char *)v4 + 28, *((unsigned __int16 *)v4 + 13));
                  v411 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v877);
                  (*(void (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v411 + 104LL))(v411, Destination);
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
                  v412 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v877);
                  (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v412 + 128LL))(
                    v412,
                    *((unsigned __int8 *)v4 + 24));
                }
                RemoteAppWindow = 0;
              }
              else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                     && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
                     && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v406 = *((_DWORD *)v4 + 1);
                v407 = RdpX_GetActivityIdPrefix(v404, v403, v405);
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  140,
                  &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                  v407,
                  v406);
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
            v259 = v877;
            goto LABEL_629;
          }
          v398 = RdpX_GetActivityIdPrefix(v397, v395, v396);
          v399 = 138;
        }
        else
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_588;
          }
          v398 = RdpX_GetActivityIdPrefix(v397, v395, v396);
          v399 = 137;
        }
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v399,
          &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v398,
          -2147418113);
        goto LABEL_588;
      }
      RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v856);
      RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v872);
      v929 = 0;
      if ( *((_WORD *)v4 + 1) < 0x58u )
        RdpRemoteAppCore::LogRemoteAppError(
          (char *)v5 + 16,
          L"Invalid size of TS_RAIL_ORDER_WINDOW_CREATE_BODY PDU",
          2147549183LL,
          0,
          0);
      v415 = *((unsigned __int16 *)v4 + 1);
      if ( (unsigned int)v415 < 0x58 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_627;
        }
        v416 = RdpX_GetActivityIdPrefix(v415, v413, v414);
        v417 = 127;
LABEL_626:
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v417,
          &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v416,
          -2147418113);
LABEL_627:
        RemoteAppWindow = -2147418113;
LABEL_628:
        TCntPtr<ITSViewerRecorder>::SafeRelease(v872);
        v259 = v856;
        goto LABEL_629;
      }
      if ( *((_WORD *)v4 + 34) )
        v418 = *((unsigned __int16 *)v4 + 34) - 1;
      else
        v418 = 0;
      v419 = 16 * v418 + 84;
      v420 = v419 + *((unsigned __int16 *)v4 + 13) + 4;
      LODWORD(v874) = v419;
      if ( (unsigned int)v415 < v420 )
        RdpRemoteAppCore::LogRemoteAppError(
          (char *)v5 + 16,
          L"Invalid size of TS_RAIL_ORDER_WINDOW_CREATE_BODY PDU",
          2147549183LL,
          0,
          0);
      if ( *((unsigned __int16 *)v4 + 1) < v420 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_627;
        }
        v416 = RdpX_GetActivityIdPrefix(v415, v413, v414);
        v417 = 128;
        goto LABEL_626;
      }
      if ( *((_DWORD *)v4 + 1) == -1 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v421 = RdpX_GetActivityIdPrefix(v415, v413, v414);
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 129, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v421);
        }
        goto LABEL_628;
      }
      v422 = (struct ITSWndPluginEx **)CacCommon::Rect<int>::Rect<int>(v872);
      v423 = 0;
      RemoteAppWindow = RdpRemoteAppCore::GetWndPlugin((RdpRemoteAppCore *)((char *)v5 - 48), v422);
      if ( RemoteAppWindow < 0 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v427 = RdpX_GetActivityIdPrefix(v425, v424, v426);
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            130,
            (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
            v427,
            (__int64)"GetWndPlugin failed",
            RemoteAppWindow);
        }
        goto LABEL_628;
      }
      v428 = (struct RdpXInterfaceRemoteAppWindow **)CacCommon::Rect<int>::Rect<int>(v856);
      RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow(
                          (RdpRemoteAppCore *)((char *)v5 - 48),
                          *((_DWORD *)v4 + 1),
                          v428);
      if ( RemoteAppWindow < 0 )
      {
        RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v900);
        RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v888);
        RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v899);
        v932 = 0;
        v429 = CacCommon::Rect<int>::Rect<int>(v900);
        WindowCallbacks = RdpRemoteAppCore::CreateWindowCallbacks((char *)v5 + 16, *((unsigned int *)v4 + 1), v429);
        RemoteAppWindow = MapXResultToHR(WindowCallbacks);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_657;
          }
          v434 = RdpX_GetActivityIdPrefix(v432, v431, v433);
          v435 = 131;
          v436 = "CreateWindowCallbacks failed";
LABEL_656:
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v435,
            (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
            v434,
            (__int64)v436,
            RemoteAppWindow);
LABEL_657:
          ComPlainSmartPtr<IRdpBaseCoreApi>::~ComPlainSmartPtr<IRdpBaseCoreApi>(v899);
          RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v888);
          RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v900);
          goto LABEL_628;
        }
        v437 = CacCommon::Rect<int>::Rect<int>(v888);
        Object = RdpX_CreateObject(0, 0, 67, 105, v437);
        RemoteAppWindow = MapXResultToHR(Object);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_657;
          }
          v434 = RdpX_GetActivityIdPrefix(v440, v439, v441);
          v435 = 132;
          v436 = "RdpXBaseCoreApiAdaptor RdpX_CreateObject failed";
          goto LABEL_656;
        }
        v442 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *((char *)v5 + 104);
        v443 = *(__int64 (__fastcall **)(__int64, void *))(*(_QWORD *)v442 + 216LL);
        v444 = CacCommon::Rect<int>::Rect<int>(v899);
        RemoteAppWindow = v443(v442, v444);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_657;
          }
          v434 = RdpX_GetActivityIdPrefix(v446, v445, v447);
          v435 = 133;
          v436 = "Failed to get base core Api";
          goto LABEL_656;
        }
        v448 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v888);
        v449 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v448 + 24LL);
        v450 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v899);
        v451 = v449(v448, v450);
        RemoteAppWindow = MapXResultToHR(v451);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_657;
          }
          v434 = RdpX_GetActivityIdPrefix(v453, v452, v454);
          v435 = 134;
          v436 = "SetCoreApi failed";
          goto LABEL_656;
        }
        v455 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *((char *)v869 + 128);
        v456 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64, __int128 *, void *))(*(_QWORD *)v455 + 48LL);
        v457 = CacCommon::Rect<int>::Rect<int>(v856);
        v458 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v900);
        v459 = *((_DWORD *)v4 + 1);
        v460 = v458;
        v461 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v888);
        v462 = v456(v455, v461, v459, v460, &v932, v457);
        v423 = 0;
        RemoteAppWindow = MapXResultToHR(v462);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_657;
          }
          v434 = RdpX_GetActivityIdPrefix(v464, v463, v465);
          v435 = 135;
          v436 = "CreateWindowRepresentation failed";
          goto LABEL_656;
        }
        v466 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v856);
        v467 = *(__int64 (__fastcall **)(__int64, bool))(*(_QWORD *)v466 + 320LL);
        v468 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v872);
        v469 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v468 + 136LL))(v468);
        v470 = v467(v466, v469 != 0);
        RemoteAppWindow = MapXResultToHR(v470);
        v471 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v856);
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v471 + 120LL))(v471, *((unsigned int *)v4 + 3));
        ComPlainSmartPtr<IRdpBaseCoreApi>::~ComPlainSmartPtr<IRdpBaseCoreApi>(v899);
        RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v888);
        RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v900);
        v5 = v869;
        v419 = v874;
      }
      v472 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v872);
      if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v472 + 136LL))(v472) )
      {
        v473 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v856);
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v473 + 200LL))(v473, 2);
      }
      v474 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v856);
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v474 + 80LL))(
        v474,
        *((unsigned int *)v4 + 4),
        *((unsigned int *)v4 + 5));
      v475 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v856);
      (*(void (__fastcall **)(__int64, bool))(*(_QWORD *)v475 + 312LL))(v475, *((_BYTE *)v4 + 25) == 1);
      memset_0(v936, 0, 0x20Au);
      if ( *((_WORD *)v4 + 13) > 2u )
      {
        memcpy_s(v936, 0x208u, (char *)v4 + v419 + 4, *((unsigned __int16 *)v4 + 13));
        v476 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v856);
        (*(void (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v476 + 104LL))(v476, v936);
      }
      CUT::ObfuscateFilePathW(v936);
      LODWORD(v845) = *((_DWORD *)v4 + 3);
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
        v845,
        *((_DWORD *)v4 + 4),
        *((_DWORD *)v4 + 5),
        *((unsigned __int8 *)v4 + 24),
        *((unsigned __int8 *)v4 + 25),
        *((unsigned __int16 *)v4 + 13),
        v936,
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
      LODWORD(v874) = *((_DWORD *)v4 + 13);
      if ( (int)v874 >= 0 )
      {
        v477 = *((_DWORD *)v4 + 14);
        if ( v477 >= 0 )
        {
          v478 = *((_DWORD *)v4 + 15);
          if ( v478 >= 0 )
          {
            v479 = *((_DWORD *)v4 + 16);
            if ( v479 >= 0 )
            {
              v480 = (__int64 *)RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v856);
              v869 = (RdpRemoteAppCore *)__PAIR64__(v477, v874);
              v870 = v478;
              v481 = *v480;
              v871 = v479;
              (*(void (__fastcall **)(__int64 *, RdpRemoteAppCore **, _QWORD))(v481 + 336))(v480, &v869, 0);
            }
          }
          v423 = 0;
        }
      }
      v482 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v856);
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v482 + 224LL))(
        v482,
        (unsigned int)(*((_DWORD *)v4 + 7) + *((_DWORD *)v4 + 11)),
        (unsigned int)(*((_DWORD *)v4 + 8) + *((_DWORD *)v4 + 12)));
      v483 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v856);
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v483 + 256LL))(
        v483,
        *((unsigned int *)v4 + 11),
        *((unsigned int *)v4 + 12));
      v929 = *(_OWORD *)((char *)v4 + 28);
      v484 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v856);
      (*(void (__fastcall **)(__int64, __int128 *, _QWORD))(*(_QWORD *)v484 + 248LL))(v484, &v929, 0);
      v487 = (char *)operator new(saturated_mul(*((unsigned __int16 *)v4 + 34), 0x10u));
      if ( v487 )
      {
        if ( *((_WORD *)v4 + 34) )
        {
          do
          {
            v490 = 16LL * v423;
            *(_DWORD *)&v487[v490] = *(_DWORD *)((char *)v4 + v490 + 72);
            *(_DWORD *)&v487[v490 + 4] = *(_DWORD *)((char *)v4 + v490 + 76);
            *(_DWORD *)&v487[v490 + 8] = *((_DWORD *)v4 + 4 * v423 + 20) - *(_DWORD *)((char *)v4 + v490 + 72);
            *(_DWORD *)&v487[v490 + 12] = *(_DWORD *)((char *)v4 + v490 + 84) - *(_DWORD *)((char *)v4 + v490 + 76);
            LODWORD(v855) = *(_DWORD *)((char *)v4 + v490 + 84);
            LODWORD(v853) = *((_DWORD *)v4 + 4 * v423 + 20);
            LODWORD(v851) = *(_DWORD *)((char *)v4 + v490 + 76);
            LODWORD(v847) = *(_DWORD *)((char *)v4 + v490 + 72);
            LODWORD(cchToCopyb) = *((_DWORD *)v4 + 1);
            RdpRemoteAppCore::LogRemoteAppEventF(
              (char *)v5 + 16,
              L"WindowCreateRailOrderReceived_VisibilityRect[%i]: WindowId=0x%x, Left=%i, Top=%i, Right=%i, Bottom=%i",
              0,
              (unsigned int)v423++,
              cchToCopyb,
              v847,
              v851,
              v853,
              v855);
          }
          while ( v423 < *((unsigned __int16 *)v4 + 34) );
        }
        v491 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v856);
        (*(void (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v491 + 176LL))(
          v491,
          *((unsigned __int16 *)v4 + 34),
          v487);
        v492 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v856);
        (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v492 + 160LL))(
          v492,
          *((int *)v4 + 7),
          *((int *)v4 + 8));
        v493 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v856);
        (*(void (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v493 + 168LL))(
          v493,
          *((unsigned __int16 *)v4 + 34),
          v487);
        operator delete(v487);
        if ( RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *((char *)v5 + 136) )
        {
          v494 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *((char *)v5 + 136);
          v495 = *(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v494 + 40LL);
          v496 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v856);
          v497 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v496 + 72LL))(v496);
          v495(v494, v497);
        }
        v498 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v856);
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v498 + 128LL))(v498, *((unsigned __int8 *)v4 + 24));
      }
      else
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v489 = RdpX_GetActivityIdPrefix(v486, v485, v488);
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            136,
            &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
            v489,
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
              RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v884);
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
                    v519 = RdpX_GetActivityIdPrefix(v517, v516, v518);
                    WPP_SF_Dd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      120,
                      &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                      v519,
                      -2147418113);
                  }
                  RemoteAppWindow = -2147418113;
LABEL_738:
                  v520 = v884;
LABEL_739:
                  TCntPtr<ITSViewerRecorder>::SafeRelease(v520);
                  return (unsigned int)RemoteAppWindow;
                }
              }
              RdpRemoteAppCore::LogRemoteAppEventF(
                (char *)v5 + 16,
                L"SyncStateRailOrderReceived: SyncFlags=0x%x",
                0,
                *((unsigned int *)v4 + 1));
              v521 = (struct ITSWndPluginEx **)CacCommon::Rect<int>::Rect<int>(v884);
              RemoteAppWindow = RdpRemoteAppCore::GetWndPlugin((RdpRemoteAppCore *)((char *)v5 - 48), v521);
              if ( RemoteAppWindow < 0 )
              {
                if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                  && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v525 = RdpX_GetActivityIdPrefix(v523, v522, v524);
                  WPP_SF_DsD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    121,
                    (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                    v525,
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
                  v526 = RdpX_GetActivityIdPrefix(v523, v522, v524);
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    122,
                    &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                    v526);
                }
                v527 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v884);
                v528 = 0;
              }
              else
              {
                if ( (*((_BYTE *)v4 + 4) & 2) == 0 )
                  goto LABEL_774;
                v529 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                  && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
                {
                  v530 = RdpX_GetActivityIdPrefix(v523, v522, v524);
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    123,
                    &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                    v530);
                  v529 = WPP_GLOBAL_Control;
                }
                if ( (*((_BYTE *)v4 + 4) & 8) != 0 )
                {
                  if ( v529 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v529[7] & 1) != 0 && *((_BYTE *)v529 + 25) >= 3u )
                  {
                    v531 = RdpX_GetActivityIdPrefix(v523, v522, v524);
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      124,
                      &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                      v531);
                  }
                  v532 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v884);
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v532 + 120LL))(v532);
                  if ( (unsigned int)RdpRemoteAppCore::IsRemoteAppV2Enabled((char *)v5 + 16) )
                  {
                    v533 = (RdpRemoteAppCore *)((char *)v5 + 128);
                    v869 = (RdpRemoteAppCore *)((char *)v5 + 128);
                    v534 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *((char *)v5 + 128);
                    LODWORD(v874) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v534 + 120LL))(v534);
                    v535 = 0;
                    if ( (_DWORD)v874 )
                    {
                      while ( 1 )
                      {
                        RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v923);
                        v536 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v533);
                        v537 = *(__int64 (__fastcall **)(__int64, _QWORD, void *))(*(_QWORD *)v536 + 128LL);
                        v538 = CacCommon::Rect<int>::Rect<int>(v923);
                        v541 = v537(v536, v535, v538);
                        if ( v541 )
                          break;
                        v543 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v923);
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v543 + 384LL))(v543);
                        RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v923);
                        v533 = v869;
                        if ( ++v535 >= (unsigned int)v874 )
                          goto LABEL_772;
                      }
                      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                        && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                      {
                        v544 = RdpX_GetActivityIdPrefix(v540, v539, v542);
                        WPP_SF_DLD(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          125,
                          &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                          v544,
                          v541,
                          v541);
                      }
                      RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v923);
                      goto LABEL_738;
                    }
                  }
                }
                else
                {
                  v545 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v884);
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v545 + 144LL))(v545);
                }
LABEL_772:
                v527 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v884);
                v528 = 1;
              }
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v527 + 112LL))(v527, v528);
LABEL_774:
              if ( (*((_BYTE *)v4 + 4) & 4) != 0 )
              {
                if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                  && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
                {
                  v546 = RdpX_GetActivityIdPrefix(v523, v522, v524);
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    126,
                    &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                    v546);
                }
                v547 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v884);
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v547 + 128LL))(v547);
              }
              goto LABEL_738;
            }
            RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v913);
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
              v553 = *((_DWORD *)v4 + 1);
              if ( v553 <= 0x100 )
              {
                v554 = 4 * v553 + 16;
                if ( *((unsigned __int16 *)v4 + 1) < v554 )
                  RdpRemoteAppCore::LogRemoteAppError(
                    (char *)v5 + 16,
                    L"Invalid size of TS_RAIL_ORDER_ZORDER_BODY PDU",
                    2147549183LL,
                    0,
                    0);
                if ( *((unsigned __int16 *)v4 + 1) >= v554 )
                {
                  memset_0(v938, 0, 0x208u);
                  v555 = v938;
                  v556 = 260;
                  v924 = v938;
                  v925 = 260;
                  v557 = *((_DWORD *)v4 + 1);
                  if ( v557 )
                  {
                    v558 = 0;
                    v559 = 0;
                    while ( 1 )
                    {
                      v560 = v557;
                      if ( v558 < 0 )
                        break;
                      v561 = L"0x%x,";
                      if ( v559 >= v557 - 1 )
                        v561 = L"0x%x";
                      LODWORD(v849) = *((_DWORD *)v4 + v559 + 4);
                      v558 = StringCchPrintfExW(v555, v556, &v924, &v925, 0, v561, v849);
                      if ( v558 < 0
                        && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                      {
                        v565 = RdpX_GetActivityIdPrefix(v563, v562, v564);
                        WPP_SF_DsD(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          209,
                          (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                          v565,
                          (__int64)"StringCchPrintfEx failed",
                          v558);
                      }
                      v557 = *((_DWORD *)v4 + 1);
                      ++v559;
                      v560 = v557;
                      if ( v559 >= v557 )
                        break;
                      v555 = v924;
                      v556 = v925;
                    }
                  }
                  else
                  {
                    v560 = 0;
                  }
                  LODWORD(v845) = *((_DWORD *)v4 + 3);
                  LODWORD(cchToCopy) = *((_DWORD *)v4 + 2);
                  RdpRemoteAppCore::LogRemoteAppEventF(
                    (char *)v5 + 16,
                    L"ZOrderRailOrderReceived: NumWindows=%u, FieldsValidFlags=0x%x, ActiveWindowId=0x%x, WindowIds=[%s]",
                    0,
                    v560,
                    cchToCopy,
                    v845,
                    v938);
                  v566 = (struct ITSWndPluginEx **)CacCommon::Rect<int>::Rect<int>(v913);
                  RemoteAppWindow = RdpRemoteAppCore::GetWndPlugin((RdpRemoteAppCore *)((char *)v5 - 48), v566);
                  if ( RemoteAppWindow >= 0 )
                  {
                    v571 = (*((_DWORD *)v4 + 2) >> 4) & 2 | 1;
                    if ( (*((_BYTE *)v4 + 8) & 0x10) == 0 )
                      v571 = (*((_DWORD *)v4 + 2) >> 4) & 2;
                    if ( v571 )
                    {
                      v572 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v913);
                      (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, __int64))(*(_QWORD *)v572 + 104LL))(
                        v572,
                        v571,
                        *((unsigned int *)v4 + 3),
                        *((unsigned int *)v4 + 1),
                        (__int64)v4 + 16);
                    }
                  }
                  else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                         && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v570 = RdpX_GetActivityIdPrefix(v568, v567, v569);
                    WPP_SF_DsD(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      210,
                      (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                      v570,
                      (__int64)"GetWndPlugin failed",
                      RemoteAppWindow);
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
                  v520 = v913;
                  goto LABEL_739;
                }
                v551 = RdpX_GetActivityIdPrefix(v549, v548, v550);
                v552 = 208;
              }
              else
              {
                if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                  || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_787;
                }
                v551 = RdpX_GetActivityIdPrefix(v549, v548, v550);
                v552 = 207;
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
              v551 = RdpX_GetActivityIdPrefix(v549, v548, v550);
              v552 = 206;
            }
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v552,
              &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v551,
              -2147418113);
            goto LABEL_787;
          }
          RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v885);
          RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v914);
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
                v576 = RdpX_GetActivityIdPrefix(v574, v573, v575);
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  202,
                  &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                  v576,
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
          v578 = (struct ITSWndPluginEx **)CacCommon::Rect<int>::Rect<int>(v914);
          RemoteAppWindow = RdpRemoteAppCore::GetWndPlugin((RdpRemoteAppCore *)((char *)v5 - 48), v578);
          if ( RemoteAppWindow >= 0 )
          {
            v585 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v914);
            v586 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, void *))(*(_QWORD *)v585 + 72LL);
            v587 = CacCommon::Rect<int>::Rect<int>(v885);
            RemoteAppWindow = v586(v585, *((unsigned int *)v4 + 1), *((unsigned int *)v4 + 2), v587);
            if ( RemoteAppWindow >= 0 )
            {
              v591 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v885);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v591 + 128LL))(v591);
              v592 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v885);
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v592 + 120LL))(v592, 2);
              v593 = (struct RdpXInterfaceShellNotifyInformation *)RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v885);
              v594 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v885);
              v595 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v594 + 72LL))(v594);
              RemoteAppWindow = RdpRemoteAppCore::OnShellNotifyInformation(v869, v595, v593);
              if ( RemoteAppWindow >= 0
                || WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_832;
              }
              v582 = RdpX_GetActivityIdPrefix(v597, v596, v598);
              v583 = 205;
              v584 = "OnShellNotifyInformation failed";
            }
            else
            {
              if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_832;
              }
              v582 = RdpX_GetActivityIdPrefix(v589, v588, v590);
              v583 = 204;
              v584 = "FindShellNotifyInfo failed";
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
            v582 = RdpX_GetActivityIdPrefix(v580, v579, v581);
            v583 = 203;
            v584 = "GetWndPlugin failed";
          }
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v583,
            (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
            v582,
            (__int64)v584,
            RemoteAppWindow);
LABEL_832:
          TCntPtr<ITSViewerRecorder>::SafeRelease(v914);
          v577 = v885;
LABEL_1025:
          RdpXSPtr<RdpXTapVcCallbackItem>::SafeRelease(v577);
          return (unsigned int)RemoteAppWindow;
        }
        RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v873);
        RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v878);
        if ( *((_WORD *)v4 + 1) < 0x14u )
          RdpRemoteAppCore::LogRemoteAppError(
            (char *)v5 + 16,
            L"Invalid size of TS_RAIL_ORDER_NOTIFYICON_TOAST_BODY",
            2147549183LL,
            0,
            0);
        v601 = *((unsigned __int16 *)v4 + 1);
        if ( (unsigned int)v601 < 0x14 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_857;
          }
          v602 = RdpX_GetActivityIdPrefix(v599, v601, v600);
          v603 = 194;
LABEL_856:
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v603,
            &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
            v602,
            -2147418113);
LABEL_857:
          RemoteAppWindow = -2147418113;
LABEL_858:
          TCntPtr<ITSViewerRecorder>::SafeRelease(v878);
          v577 = v873;
          goto LABEL_1025;
        }
        v604 = *((unsigned __int16 *)v4 + 8);
        v605 = v604 + *((unsigned __int16 *)v4 + 9) + 20;
        if ( (unsigned int)v601 < v605 )
          RdpRemoteAppCore::LogRemoteAppError(
            (char *)v5 + 16,
            L"Invalid size of TS_RAIL_ORDER_NOTIFYICON_TOAST_BODY PDU",
            2147549183LL,
            0,
            0);
        if ( *((unsigned __int16 *)v4 + 1) < v605 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_857;
          }
          v602 = RdpX_GetActivityIdPrefix(v604, v601, v600);
          v603 = 195;
          goto LABEL_856;
        }
        v606 = (struct ITSWndPluginEx **)CacCommon::Rect<int>::Rect<int>(v878);
        RemoteAppWindow = RdpRemoteAppCore::GetWndPlugin((RdpRemoteAppCore *)((char *)v5 - 48), v606);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_858;
          }
          v610 = RdpX_GetActivityIdPrefix(v608, v607, v609);
          v611 = 196;
          v612 = "GetWndPlugin failed";
          goto LABEL_871;
        }
        v613 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v878);
        v614 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, void *))(*(_QWORD *)v613 + 72LL);
        v615 = CacCommon::Rect<int>::Rect<int>(v873);
        RemoteAppWindow = v614(v613, *((unsigned int *)v4 + 1), *((unsigned int *)v4 + 2), v615);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_858;
          }
          v610 = RdpX_GetActivityIdPrefix(v617, v616, v618);
          v611 = 197;
          v612 = "FindShellNotifyInfo failed";
LABEL_871:
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v611,
            (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
            v610,
            (__int64)v612,
            RemoteAppWindow);
          goto LABEL_858;
        }
        v619 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v873);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v619 + 128LL))(v619);
        v620 = *((unsigned __int16 *)v4 + 8);
        v621 = (char *)v4 + 20;
        RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v904);
        v622 = CacCommon::Rect<int>::Rect<int>(v904);
        ConstXChar16StringWithSpecifiedSize = RdpX_Strings_CreateConstXChar16StringWithSpecifiedSize(
                                                *((unsigned __int16 *)v4 + 8) >> 1,
                                                (char *)v4 + 20,
                                                v622);
        RemoteAppWindow = MapXResultToHR(ConstXChar16StringWithSpecifiedSize);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v627 = RdpX_GetActivityIdPrefix(v625, v624, v626);
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              198,
              (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v627,
              (__int64)"RdpX_Strings_CreateConstXChar16StringWithSpecifiedSize failed",
              RemoteAppWindow);
          }
          goto LABEL_882;
        }
        v628 = &v621[v620];
        RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v915);
        v629 = CacCommon::Rect<int>::Rect<int>(v915);
        v630 = RdpX_Strings_CreateConstXChar16StringWithSpecifiedSize(
                 *((unsigned __int16 *)v4 + 9) >> 1,
                 &v621[v620],
                 v629);
        RemoteAppWindow = MapXResultToHR(v630);
        if ( RemoteAppWindow >= 0 )
        {
          v637 = &sourceString;
          if ( RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v915) )
          {
            v638 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v915);
            v639 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v638 + 24LL))(v638);
          }
          else
          {
            v639 = &sourceString;
          }
          if ( RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v904) )
          {
            v640 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v904);
            v637 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v640 + 24LL))(v640);
          }
          LODWORD(cchToCopy) = *((_DWORD *)v4 + 2);
          RdpRemoteAppCore::LogRemoteAppEventF(
            (char *)v869 + 16,
            L"NotifyIconToastRailOrderReceived: WindowId=0x%x, NotifyIconId=0x%x, ToastFlags=0x%x, Toast=%s, ToastTitle=%s",
            0,
            *((unsigned int *)v4 + 1),
            cchToCopy,
            *((_DWORD *)v4 + 3),
            v637,
            v639);
          v641 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v873);
          LOWORD(v848) = *((_WORD *)v4 + 9) >> 1;
          RemoteAppWindow = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, __int64, int, char *))(*(_QWORD *)v641 + 96LL))(
                              v641,
                              0,
                              *((unsigned int *)v4 + 3),
                              *((_WORD *)v4 + 8) >> 1,
                              (__int64)v4 + 20,
                              v848,
                              v628);
          if ( RemoteAppWindow >= 0 )
          {
            v645 = (struct RdpXInterfaceShellNotifyInformation *)RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v873);
            v646 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v873);
            v647 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v646 + 72LL))(v646);
            RemoteAppWindow = RdpRemoteAppCore::OnShellNotifyInformation(v869, v647, v645);
            if ( RemoteAppWindow >= 0
              || WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
              || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_889;
            }
            v634 = RdpX_GetActivityIdPrefix(v649, v648, v650);
            v635 = 201;
            v636 = "OnShellNotifyInformation failed";
          }
          else
          {
            if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
              || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_889;
            }
            v634 = RdpX_GetActivityIdPrefix(v643, v642, v644);
            v635 = 200;
            v636 = "spShellNotify->SetInfo failed";
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
          v634 = RdpX_GetActivityIdPrefix(v632, v631, v633);
          v635 = 199;
          v636 = "RdpX_Strings_CreateConstXChar16StringWithSpecifiedSize failed";
        }
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v635,
          (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v634,
          (__int64)v636,
          RemoteAppWindow);
LABEL_889:
        RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v915);
LABEL_882:
        RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v904);
        goto LABEL_858;
      }
      RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v858);
      RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v865);
      if ( *((_WORD *)v4 + 1) < 0x18u )
        RdpRemoteAppCore::LogRemoteAppError(
          (char *)v5 + 16,
          L"Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Change PDU",
          2147549183LL,
          0,
          0);
      v653 = *((unsigned __int16 *)v4 + 1);
      if ( (unsigned int)v653 < 0x18 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_913;
        }
        v654 = RdpX_GetActivityIdPrefix(v653, v651, v652);
        v655 = 180;
LABEL_912:
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v655,
          &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v654,
          -2147418113);
LABEL_913:
        RemoteAppWindow = -2147418113;
LABEL_914:
        TCntPtr<ITSViewerRecorder>::SafeRelease(v865);
        v577 = v858;
        goto LABEL_1025;
      }
      v656 = *((unsigned __int16 *)v4 + 6) + 24;
      if ( (unsigned int)v653 < v656 )
        RdpRemoteAppCore::LogRemoteAppError(
          (char *)v5 + 16,
          L"Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Change PDU",
          2147549183LL,
          0,
          0);
      if ( *((unsigned __int16 *)v4 + 1) < v656 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_913;
        }
        v654 = RdpX_GetActivityIdPrefix(v653, v651, v652);
        v655 = 181;
        goto LABEL_912;
      }
      v657 = (struct ITSWndPluginEx **)CacCommon::Rect<int>::Rect<int>(v865);
      RemoteAppWindow = RdpRemoteAppCore::GetWndPlugin((RdpRemoteAppCore *)((char *)v5 - 48), v657);
      if ( RemoteAppWindow < 0 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_914;
        }
        v661 = RdpX_GetActivityIdPrefix(v659, v658, v660);
        v662 = 182;
        v663 = "GetWndPlugin failed";
        goto LABEL_927;
      }
      v664 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v865);
      v665 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, void *))(*(_QWORD *)v664 + 72LL);
      v666 = CacCommon::Rect<int>::Rect<int>(v858);
      v667 = v665(v664, *((unsigned int *)v4 + 1), *((unsigned int *)v4 + 2), v666);
      v671 = 0;
      RemoteAppWindow = v667;
      if ( v667 < 0 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_914;
        }
        v661 = RdpX_GetActivityIdPrefix(v669, v668, v670);
        v662 = 183;
        v663 = "FindShellNotifyInfo failed";
LABEL_927:
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v662,
          (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v661,
          (__int64)v663,
          RemoteAppWindow);
        goto LABEL_914;
      }
      v672 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v858);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v672 + 128LL))(v672);
      RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v867);
      if ( *((_WORD *)v4 + 6) )
      {
        v673 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v858);
        RemoteAppWindow = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v673 + 88LL))(
                            v673,
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
          v677 = RdpX_GetActivityIdPrefix(v675, v674, v676);
          v678 = 184;
          v679 = "CreateShellNotifyInfo->SetTip failed";
          goto LABEL_939;
        }
        v680 = CacCommon::Rect<int>::Rect<int>(v867);
        v681 = RdpX_Strings_CreateConstXChar16StringWithSpecifiedSize(
                 *((unsigned __int16 *)v4 + 6) >> 1,
                 (char *)v4 + 24,
                 v680);
        RemoteAppWindow = MapXResultToHR(v681);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_940;
          }
          v677 = RdpX_GetActivityIdPrefix(v683, v682, v684);
          v678 = 185;
          v679 = "RdpX_Strings_CreateConstXChar16StringWithSpecifiedSize failed";
          goto LABEL_939;
        }
      }
      if ( (*((_BYTE *)v4 + 20) & 4) != 0 )
      {
        v685 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v858);
        RemoteAppWindow = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v685 + 104LL))(
                            v685,
                            *((unsigned int *)v4 + 4));
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_940;
          }
          v677 = RdpX_GetActivityIdPrefix(v687, v686, v688);
          v678 = 186;
          v679 = "CreateShellNotifyInfo->SetWSNState failed";
          goto LABEL_939;
        }
      }
      if ( *((_BYTE *)v4 + 14) )
      {
        RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v886);
        v692 = *((unsigned __int16 *)v4 + 6);
        v693 = *((unsigned __int16 *)v4 + 1);
        if ( *((_BYTE *)v4 + 15) )
        {
          v694 = v656 + 4;
          v695 = v869;
          if ( v693 < v694 )
            RdpRemoteAppCore::LogRemoteAppError(
              (char *)v869 + 16,
              L"Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Create PDU",
              2147549183LL,
              0,
              0);
          if ( *((unsigned __int16 *)v4 + 1) < v694 )
          {
            if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
              || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_962;
            }
            v696 = RdpX_GetActivityIdPrefix(v690, v689, v691);
            v697 = 187;
LABEL_961:
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v697,
              &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v696,
              -2147418113);
LABEL_962:
            RemoteAppWindow = -2147418113;
LABEL_963:
            RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v886);
            goto LABEL_940;
          }
          v698 = *((unsigned __int8 *)v4 + v692 + 27);
          LODWORD(v874) = *((unsigned __int8 *)v4 + v692 + 26);
          v859 = *(unsigned __int16 *)((char *)v4 + v692 + 24);
          if ( RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v867) )
          {
            v699 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v867);
            v700 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v699 + 24LL))(v699);
          }
          else
          {
            v700 = &sourceString;
          }
          LODWORD(cchToCopy) = *((_DWORD *)v4 + 2);
          RdpRemoteAppCore::LogRemoteAppEventF(
            (char *)v695 + 16,
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
            v700,
            v859,
            v874,
            v698);
          v701 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v865);
          v702 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, void *))(*(_QWORD *)v701 + 56LL);
          v703 = CacCommon::Rect<int>::Rect<int>(v886);
          RemoteAppWindow = v702(
                              v701,
                              *((unsigned __int8 *)v4 + v692 + 26),
                              *(unsigned __int16 *)((char *)v4 + v692 + 24),
                              v703);
          if ( RemoteAppWindow < 0 )
          {
            if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
              || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_963;
            }
            v707 = RdpX_GetActivityIdPrefix(v705, v704, v706);
            v708 = 188;
            goto LABEL_972;
          }
        }
        else
        {
          v710 = v656 + 20;
          v695 = v869;
          if ( v693 < v710 )
            RdpRemoteAppCore::LogRemoteAppError(
              (char *)v869 + 16,
              L"Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Change PDU",
              2147549183LL,
              0,
              0);
          v711 = *((unsigned __int16 *)v4 + 1);
          if ( (unsigned int)v711 < v710 )
          {
            if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
              || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_962;
            }
            v696 = RdpX_GetActivityIdPrefix(v690, v711, v691);
            v697 = 189;
            goto LABEL_961;
          }
          if ( (*((_BYTE *)v4 + v692 + 27) & 2) != 0 )
          {
            LOBYTE(v690) = *((_BYTE *)v4 + v692 + 32);
            v671 = *(_WORD *)((char *)v4 + v692 + 34);
            LOWORD(v859) = v690;
          }
          else
          {
            LOWORD(v859) = 32;
          }
          v712 = *(unsigned int *)((char *)v4 + v692 + 36);
          v713 = v671;
          v714 = v671 + *(_DWORD *)((char *)v4 + v692 + 40);
          v879 = v712;
          v880 = v671;
          v715 = v712 + v714 + v710;
          if ( (unsigned int)v711 < v715 )
            RdpRemoteAppCore::LogRemoteAppError(
              (char *)v695 + 16,
              L"Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Change PDU",
              2147549183LL,
              0,
              0);
          if ( *((unsigned __int16 *)v4 + 1) < v715 )
          {
            if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
              || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_962;
            }
            v696 = RdpX_GetActivityIdPrefix(v713, v711, v712);
            v697 = 190;
            goto LABEL_961;
          }
          v869 = (struct tagTS_RAIL_PDU *)((char *)v4 + v692 + v671 + 44);
          LODWORD(v874) = *(_DWORD *)((char *)v4 + v692 + 40);
          v910 = *(_DWORD *)((char *)v4 + v692 + 36);
          v906 = *(unsigned __int16 *)((char *)v4 + v692 + 34);
          v907 = *((unsigned __int8 *)v4 + v692 + 32);
          v908 = *(unsigned __int16 *)((char *)v4 + v692 + 30);
          v909 = *(unsigned __int16 *)((char *)v4 + v692 + 28);
          v912 = *((unsigned __int8 *)v4 + v692 + 27);
          v911 = *((unsigned __int8 *)v4 + v692 + 26);
          v881 = *(unsigned __int16 *)((char *)v4 + v692 + 24);
          if ( RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v867) )
          {
            v716 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v867);
            v717 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v716 + 24LL))(v716);
          }
          else
          {
            v717 = &sourceString;
          }
          LODWORD(cchToCopy) = *((_DWORD *)v4 + 2);
          RdpRemoteAppCore::LogRemoteAppEventF(
            (char *)v695 + 16,
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
            v717,
            v881,
            v911,
            v912,
            v909,
            v908,
            v907,
            v906,
            v910,
            v874);
          v718 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v865);
          v719 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, char *, _DWORD, _DWORD, char *, int, RdpRemoteAppCore *, _DWORD, char *, _DWORD, void *))(*(_QWORD *)v718 + 64LL);
          v720 = CacCommon::Rect<int>::Rect<int>(v886);
          v721 = (char *)v869 + v879;
          LOBYTE(v721) = v859;
          RemoteAppWindow = v719(
                              v718,
                              *((unsigned __int8 *)v4 + v692 + 26),
                              *(unsigned __int16 *)((char *)v4 + v692 + 24),
                              v721,
                              *(unsigned __int16 *)((char *)v4 + v692 + 28),
                              *(unsigned __int16 *)((char *)v4 + v692 + 30),
                              (char *)v4 + v692 + 44,
                              v880,
                              v869,
                              *(_DWORD *)((char *)v4 + v692 + 36),
                              (char *)v869 + v879,
                              *(_DWORD *)((char *)v4 + v692 + 40),
                              v720);
          if ( RemoteAppWindow < 0 )
          {
            if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
              || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_963;
            }
            v707 = RdpX_GetActivityIdPrefix(v723, v722, v724);
            v708 = 191;
LABEL_972:
            v709 = "CreateCachedIcon failed";
LABEL_973:
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v708,
              (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v707,
              (__int64)v709,
              RemoteAppWindow);
            goto LABEL_963;
          }
        }
        v725 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v858);
        v726 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v725 + 80LL);
        v727 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v886);
        RemoteAppWindow = v726(v725, v727);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_963;
          }
          v707 = RdpX_GetActivityIdPrefix(v729, v728, v730);
          v708 = 192;
          v709 = "spShellNotify->SetIcon failed";
          goto LABEL_973;
        }
        RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v886);
      }
      else
      {
        v695 = v869;
        if ( RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v867) )
        {
          v731 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v867);
          v732 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v731 + 24LL))(v731);
        }
        else
        {
          v732 = &sourceString;
        }
        LODWORD(cchToCopy) = *((_DWORD *)v4 + 2);
        RdpRemoteAppCore::LogRemoteAppEventF(
          (char *)v695 + 16,
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
          v732);
      }
      v733 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v858);
      if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v733 + 72LL))(v733) )
        goto LABEL_940;
      v734 = (struct RdpXInterfaceShellNotifyInformation *)RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v858);
      v735 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v858);
      v736 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v735 + 72LL))(v735);
      RemoteAppWindow = RdpRemoteAppCore::OnShellNotifyInformation(v695, v736, v734);
      if ( RemoteAppWindow >= 0
        || WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_940;
      }
      v677 = RdpX_GetActivityIdPrefix(v738, v737, v739);
      v678 = 193;
      v679 = "OnShellNotifyInformation failed";
LABEL_939:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v678,
        (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
        v677,
        (__int64)v679,
        RemoteAppWindow);
LABEL_940:
      RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v867);
      goto LABEL_914;
    }
    RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v857);
    RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v860);
    if ( *((_WORD *)v4 + 1) < 0x18u )
      RdpRemoteAppCore::LogRemoteAppError(
        (char *)v5 + 16,
        L"Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Create PDU",
        2147549183LL,
        0,
        0);
    v742 = *((unsigned __int16 *)v4 + 1);
    if ( (unsigned int)v742 < 0x18 )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_1023;
      }
      v743 = RdpX_GetActivityIdPrefix(v742, v740, v741);
      v744 = 165;
LABEL_1022:
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v744,
        &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
        v743,
        -2147418113);
LABEL_1023:
      RemoteAppWindow = -2147418113;
LABEL_1024:
      TCntPtr<ITSViewerRecorder>::SafeRelease(v860);
      v577 = v857;
      goto LABEL_1025;
    }
    v745 = *((unsigned __int16 *)v4 + 6) + 24;
    if ( (unsigned int)v742 < v745 )
      RdpRemoteAppCore::LogRemoteAppError(
        (char *)v5 + 16,
        L"Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Create PDU",
        2147549183LL,
        0,
        0);
    if ( *((unsigned __int16 *)v4 + 1) < v745 )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_1023;
      }
      v743 = RdpX_GetActivityIdPrefix(v742, v740, v741);
      v744 = 166;
      goto LABEL_1022;
    }
    v746 = (struct ITSWndPluginEx **)CacCommon::Rect<int>::Rect<int>(v860);
    RemoteAppWindow = RdpRemoteAppCore::GetWndPlugin((RdpRemoteAppCore *)((char *)v5 - 48), v746);
    if ( RemoteAppWindow < 0 )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_1024;
      }
      v750 = RdpX_GetActivityIdPrefix(v748, v747, v749);
      v751 = 167;
      v752 = "GetWndPlugin failed";
      goto LABEL_1038;
    }
    v753 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v860);
    v754 = *(int (__fastcall **)(__int64, _QWORD, _QWORD, void *))(*(_QWORD *)v753 + 72LL);
    v755 = CacCommon::Rect<int>::Rect<int>(v857);
    if ( v754(v753, *((unsigned int *)v4 + 1), *((unsigned int *)v4 + 2), v755) >= 0 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v763 = *((_DWORD *)v4 + 2);
        v764 = *((_DWORD *)v4 + 1);
        v765 = ((__int64 (*)(void))RdpX_GetActivityIdPrefix)();
        WPP_SF_DLD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          169,
          &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v765,
          v764,
          v763);
      }
      v766 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v857);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v766 + 128LL))(v766);
    }
    else
    {
      v756 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v860);
      v757 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, void *))(*(_QWORD *)v756 + 80LL);
      v758 = CacCommon::Rect<int>::Rect<int>(v857);
      RemoteAppWindow = v757(v756, *((unsigned int *)v4 + 1), *((unsigned int *)v4 + 2), v758);
      if ( RemoteAppWindow < 0 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_1024;
        }
        v750 = RdpX_GetActivityIdPrefix(v760, v759, v761);
        v751 = 168;
        v752 = "CreateShellNotifyInfo failed";
LABEL_1038:
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v751,
          (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v750,
          (__int64)v752,
          RemoteAppWindow);
        goto LABEL_1024;
      }
      v762 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v857);
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v762 + 120LL))(v762, 1);
    }
    v767 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v860);
    if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v767 + 136LL))(v767) )
    {
      v768 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v857);
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v768 + 136LL))(v768, 2);
    }
    v769 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v857);
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v769 + 112LL))(v769, 4);
    RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v868);
    if ( *((_WORD *)v4 + 6) )
    {
      v770 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v857);
      RemoteAppWindow = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v770 + 88LL))(
                          v770,
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
        v774 = RdpX_GetActivityIdPrefix(v772, v771, v773);
        v775 = 170;
        v776 = "CreateShellNotifyInfo->SetTip failed";
        goto LABEL_1059;
      }
      v777 = CacCommon::Rect<int>::Rect<int>(v868);
      v778 = RdpX_Strings_CreateConstXChar16StringWithSpecifiedSize(
               *((unsigned __int16 *)v4 + 6) >> 1,
               (char *)v4 + 24,
               v777);
      RemoteAppWindow = MapXResultToHR(v778);
      if ( RemoteAppWindow < 0 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_1060;
        }
        v774 = RdpX_GetActivityIdPrefix(v780, v779, v781);
        v775 = 171;
        v776 = "RdpX_Strings_CreateConstXChar16StringWithSpecifiedSize failed";
        goto LABEL_1059;
      }
    }
    if ( (*((_BYTE *)v4 + 20) & 4) != 0 )
    {
      v782 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v857);
      RemoteAppWindow = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v782 + 104LL))(
                          v782,
                          *((unsigned int *)v4 + 4));
      if ( RemoteAppWindow < 0 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_1060;
        }
        v774 = RdpX_GetActivityIdPrefix(v784, v783, v785);
        v775 = 172;
        v776 = "CreateShellNotifyInfo->SetWSNState failed";
        goto LABEL_1059;
      }
    }
    if ( *((_BYTE *)v4 + 14) )
    {
      RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v887);
      v789 = *((unsigned __int16 *)v4 + 6);
      v790 = *((unsigned __int16 *)v4 + 1);
      if ( *((_BYTE *)v4 + 15) )
      {
        v791 = v745 + 4;
        v792 = v869;
        if ( v790 < v791 )
          RdpRemoteAppCore::LogRemoteAppError(
            (char *)v869 + 16,
            L"Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Create PDU",
            2147549183LL,
            0,
            0);
        if ( *((unsigned __int16 *)v4 + 1) < v791 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_1082;
          }
          v793 = RdpX_GetActivityIdPrefix(v787, v786, v788);
          v794 = 173;
LABEL_1081:
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v794,
            &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
            v793,
            -2147418113);
LABEL_1082:
          RemoteAppWindow = -2147418113;
LABEL_1083:
          RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v887);
          goto LABEL_1060;
        }
        v880 = *((unsigned __int8 *)v4 + v789 + 27);
        v879 = *((unsigned __int8 *)v4 + v789 + 26);
        v881 = *(unsigned __int16 *)((char *)v4 + v789 + 24);
        if ( RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v868) )
        {
          v795 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v868);
          v796 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v795 + 24LL))(v795);
        }
        else
        {
          v796 = &sourceString;
        }
        LODWORD(v845) = *((unsigned __int8 *)v4 + 14);
        LODWORD(cchToCopy) = *((_DWORD *)v4 + 2);
        RdpRemoteAppCore::LogRemoteAppEventF(
          (char *)v792 + 16,
          L"NotifyIconCreateRailOrderReceived_Cached: WindowId=0x%x, NotifyIconId=0x%x, NumIcons=%hhu, IsCachedIcon=%hhu, "
           "StateFlags=0x%x, PDUFlags=0x%x, ToolTipBytes=%hu, ToolTip=%s, CacheEntry=0x%hx, CacheId=0x%hhx, IconFlags=0x%hhx",
          0,
          *((unsigned int *)v4 + 1),
          cchToCopy,
          v845,
          *((unsigned __int8 *)v4 + 15),
          *((_DWORD *)v4 + 4),
          *((_DWORD *)v4 + 5),
          *((unsigned __int16 *)v4 + 6),
          v796,
          v881,
          v879,
          v880);
        v797 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v860);
        v798 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, void *))(*(_QWORD *)v797 + 56LL);
        v799 = CacCommon::Rect<int>::Rect<int>(v887);
        RemoteAppWindow = v798(
                            v797,
                            *((unsigned __int8 *)v4 + v789 + 26),
                            *(unsigned __int16 *)((char *)v4 + v789 + 24),
                            v799);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_1083;
          }
          v803 = RdpX_GetActivityIdPrefix(v801, v800, v802);
          v804 = 174;
          goto LABEL_1092;
        }
      }
      else
      {
        v806 = v745 + 20;
        v792 = v869;
        if ( v790 < v806 )
          RdpRemoteAppCore::LogRemoteAppError(
            (char *)v869 + 16,
            L"Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Create PDU",
            2147549183LL,
            0,
            0);
        v807 = *((unsigned __int16 *)v4 + 1);
        if ( v807 < v806 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_1082;
          }
          v793 = RdpX_GetActivityIdPrefix(v787, v786, v788);
          v794 = 175;
          goto LABEL_1081;
        }
        if ( (*((_BYTE *)v4 + v789 + 27) & 2) != 0 )
        {
          LOBYTE(v786) = *((_BYTE *)v4 + v789 + 32);
          v808 = *(unsigned __int16 *)((char *)v4 + v789 + 34);
          LOWORD(v859) = v786;
        }
        else
        {
          v808 = 0;
          LOWORD(v859) = 32;
        }
        v910 = *(_DWORD *)((char *)v4 + v789 + 36);
        v809 = (unsigned __int16)v808 + v910;
        LODWORD(v874) = v808;
        v810 = *(_DWORD *)((char *)v4 + v789 + 40) + v809 + v806;
        LODWORD(v869) = (unsigned __int16)v808;
        if ( v807 < v810 )
        {
          RdpRemoteAppCore::LogRemoteAppError(
            (char *)v792 + 16,
            L"Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Create PDU",
            2147549183LL,
            0,
            0);
          v808 = (unsigned int)v874;
        }
        if ( *((unsigned __int16 *)v4 + 1) < v810 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_1082;
          }
          v793 = RdpX_GetActivityIdPrefix(v809, v786, v808);
          v794 = 176;
          goto LABEL_1081;
        }
        v874 = (__int64)v4 + v789 + (unsigned __int16)v808 + 44;
        v880 = *(_DWORD *)((char *)v4 + v789 + 40);
        v879 = *(_DWORD *)((char *)v4 + v789 + 36);
        v881 = *(unsigned __int16 *)((char *)v4 + v789 + 34);
        v911 = *((unsigned __int8 *)v4 + v789 + 32);
        v912 = *(unsigned __int16 *)((char *)v4 + v789 + 30);
        v909 = *(unsigned __int16 *)((char *)v4 + v789 + 28);
        v908 = *((unsigned __int8 *)v4 + v789 + 27);
        v907 = *((unsigned __int8 *)v4 + v789 + 26);
        v906 = *(unsigned __int16 *)((char *)v4 + v789 + 24);
        if ( RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v868) )
        {
          v811 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v868);
          v812 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v811 + 24LL))(v811);
        }
        else
        {
          v812 = &sourceString;
        }
        LODWORD(v845) = *((unsigned __int8 *)v4 + 14);
        LODWORD(cchToCopy) = *((_DWORD *)v4 + 2);
        RdpRemoteAppCore::LogRemoteAppEventF(
          (char *)v792 + 16,
          L"NotifyIconCreateRailOrderReceived_NonCached: WindowId=0x%x, NotifyIconId=0x%x, NumIcons=%hhu, IsCachedIcon=%hh"
           "u, StateFlags=0x%x, PDUFlags=0x%x, ToolTipBytes=%hu, ToolTip=%s, CacheEntry=0x%hx, CacheId=0x%hhx, IconFlags="
           "0x%hhx, Width=%hu, Height=%hu, Bpp=%hhu, ColorTableBytes=%hu, BitsMaskBytes=%u, BitsColorBytes=%u",
          0,
          *((unsigned int *)v4 + 1),
          cchToCopy,
          v845,
          *((unsigned __int8 *)v4 + 15),
          *((_DWORD *)v4 + 4),
          *((_DWORD *)v4 + 5),
          *((unsigned __int16 *)v4 + 6),
          v812,
          v906,
          v907,
          v908,
          v909,
          v912,
          v911,
          v881,
          v879,
          v880);
        v813 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v860);
        v814 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64, _DWORD, _DWORD, char *, _DWORD, __int64, _DWORD, __int64, _DWORD, void *))(*(_QWORD *)v813 + 64LL);
        v815 = CacCommon::Rect<int>::Rect<int>(v887);
        v816 = v874 + v910;
        LOBYTE(v816) = v859;
        RemoteAppWindow = v814(
                            v813,
                            *((unsigned __int8 *)v4 + v789 + 26),
                            *(unsigned __int16 *)((char *)v4 + v789 + 24),
                            v816,
                            *(unsigned __int16 *)((char *)v4 + v789 + 28),
                            *(unsigned __int16 *)((char *)v4 + v789 + 30),
                            (char *)v4 + v789 + 44,
                            (_DWORD)v869,
                            v874,
                            *(_DWORD *)((char *)v4 + v789 + 36),
                            v874 + v910,
                            *(_DWORD *)((char *)v4 + v789 + 40),
                            v815);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_1083;
          }
          v803 = ((__int64 (*)(void))RdpX_GetActivityIdPrefix)();
          v804 = 177;
LABEL_1092:
          v805 = "CreateCachedIcon failed";
LABEL_1093:
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v804,
            (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
            v803,
            (__int64)v805,
            RemoteAppWindow);
          goto LABEL_1083;
        }
      }
      v817 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v857);
      v818 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v817 + 80LL);
      v819 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v887);
      RemoteAppWindow = v818(v817, v819);
      if ( RemoteAppWindow < 0 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_1083;
        }
        v803 = RdpX_GetActivityIdPrefix(v821, v820, v822);
        v804 = 178;
        v805 = "spShellNotify->SetIcon failed";
        goto LABEL_1093;
      }
      RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v887);
    }
    else
    {
      v792 = v869;
      if ( RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v868) )
      {
        v823 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v868);
        v824 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v823 + 24LL))(v823);
      }
      else
      {
        v824 = &sourceString;
      }
      LODWORD(v845) = *((unsigned __int8 *)v4 + 14);
      LODWORD(cchToCopy) = *((_DWORD *)v4 + 2);
      RdpRemoteAppCore::LogRemoteAppEventF(
        (char *)v792 + 16,
        L"NotifyIconCreateRailOrderReceived_NoIcons: WindowId=0x%x, NotifyIconId=0x%x, NumIcons=%hhu, IsCachedIcon=%hhu, S"
         "tateFlags=0x%x, PDUFlags=0x%x, ToolTipBytes=%hu, ToolTip=%s",
        0,
        *((unsigned int *)v4 + 1),
        cchToCopy,
        v845,
        *((unsigned __int8 *)v4 + 15),
        *((_DWORD *)v4 + 4),
        *((_DWORD *)v4 + 5),
        *((unsigned __int16 *)v4 + 6),
        v824);
    }
    v825 = (struct RdpXInterfaceShellNotifyInformation *)RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v857);
    v826 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v857);
    v827 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v826 + 72LL))(v826);
    RemoteAppWindow = RdpRemoteAppCore::OnShellNotifyInformation(v792, v827, v825);
    if ( RemoteAppWindow >= 0
      || WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_1060;
    }
    v774 = RdpX_GetActivityIdPrefix(v829, v828, v830);
    v775 = 179;
    v776 = "OnShellNotifyInformation failed";
LABEL_1059:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v775,
      (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
      v774,
      (__int64)v776,
      RemoteAppWindow);
LABEL_1060:
    RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v868);
    goto LABEL_1024;
  }
  if ( (_DWORD)v17 == 24 )
  {
    v231 = *((unsigned __int16 *)v4 + 1);
    if ( (_WORD)v231 != 1052 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v232 = RdpX_GetActivityIdPrefix(v17, v15, v16);
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v232, v231);
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
      v233 = *((_DWORD *)v4 + 132);
      v234 = *((_DWORD *)v4 + 1);
      v235 = RdpX_GetActivityIdPrefix(v17, v15, v16);
      WPP_SF_DDDS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        86,
        (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
        v235,
        v234,
        v233,
        (__int64)v4 + 532);
    }
    FileNameW = CUT::PathFindFileNameW((const unsigned __int16 *)v4 + 266);
    v237 = *((_DWORD *)v4 + 132);
    v238 = FileNameW;
    v239 = CUT::PathFindFileNameW((const unsigned __int16 *)v4 + 4);
    LODWORD(v845) = v237;
    RdpRemoteAppCore::LogRemoteAppEventF(
      (char *)v869 + 16,
      L"GetAppIdRespExRailOrderReceived: WindowId=0x%x, CensoredAppId=%s, ProcessId=%u, CensoredProcessImageName=%s",
      0,
      *((unsigned int *)v4 + 1),
      v239,
      v845,
      v238);
    v240 = (RdpRemoteAppCore *)((char *)v869 - 48);
    v890 = 0;
    RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow(
                        (RdpRemoteAppCore *)((char *)v869 - 48),
                        *((_DWORD *)v4 + 1),
                        &v890);
    if ( RemoteAppWindow >= 0 )
    {
      updated = RdpRemoteAppCore::UpdateProcessInfo(
                  v240,
                  v890,
                  *((_DWORD *)v4 + 132),
                  (const unsigned __int16 *)v4 + 266);
      v249 = updated;
      if ( updated < 0
        && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v250 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v247, v248);
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          88,
          (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v250,
          (__int64)"Failed to set process info",
          v249);
      }
      RemoteAppWindow = RdpRemoteAppCore::UpdateAppID(v240, v890, (const unsigned __int16 *)v4 + 4);
      if ( RemoteAppWindow < 0
        && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v254 = RdpX_GetActivityIdPrefix(v252, v251, v253);
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          89,
          (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v254,
          (__int64)"UpdateAppID failed",
          RemoteAppWindow);
      }
      v38 = v890;
      if ( v890 )
      {
        v890 = 0;
        goto LABEL_106;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v244 = *((_DWORD *)v4 + 1);
        v245 = RdpX_GetActivityIdPrefix(v242, v241, v243);
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v245, v244);
      }
      v38 = v890;
      if ( v890 )
      {
        v890 = 0;
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
        v128 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v129 = RdpX_GetActivityIdPrefix(v17, v88, v16);
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 112, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v129);
          v128 = WPP_GLOBAL_Control;
        }
        v130 = *((unsigned __int16 *)v4 + 1);
        if ( (_WORD)v130 != 20 )
        {
          if ( v128 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v128[7] & 1) != 0 && *((_BYTE *)v128 + 25) >= 2u )
          {
            v131 = RdpX_GetActivityIdPrefix(v17, v88, v16);
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              113,
              &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v131,
              v130);
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
          v132 = *((_DWORD *)v4 + 1);
          v133 = *((_DWORD *)v4 + 4) == 0;
          v134 = *((_DWORD *)v4 + 3);
          v930[1] = *((_DWORD *)v4 + 2);
          v930[2] = v134;
          v930[3] = !v133;
          v930[0] = v132 != 0;
          (*(void (__fastcall **)(_QWORD, _DWORD *))(**((_QWORD **)v5 + 17) + 48LL))(*((_QWORD *)v5 + 17), v930);
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
        LODWORD(v845) = 8;
        v101 = 2147549183LL;
        v102 = L"Invalid size for TS_RAIL_ORDER_ZORDER_SYNC: [%d]. Expected size: [%lu]";
LABEL_1150:
        LODWORD(cchToCopy) = *((unsigned __int16 *)v4 + 1);
        RdpRemoteAppCore::LogRemoteAppErrorF((char *)v5 + 16, v102, v101, 0, cchToCopy, v845);
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
        LODWORD(v845) = 9;
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
        v922 = 0;
        v917 = 0;
        RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow(
                            (RdpRemoteAppCore *)((char *)v5 - 48),
                            *((_DWORD *)v4 + 1),
                            &v922);
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
          v38 = v922;
          if ( v922 )
          {
            v922 = 0;
            goto LABEL_106;
          }
          return (unsigned int)RemoteAppWindow;
        }
        DesktopRemoteAppWindow = RdpRemoteAppCore::GetDesktopRemoteAppWindow(
                                   (RdpRemoteAppCore *)((char *)v5 - 48),
                                   v922);
        RdpXSPtr<RdpXInterfaceLayerManager>::operator=(&v917, DesktopRemoteAppWindow);
        if ( v917 )
        {
          (*(void (__fastcall **)(__int64, bool))(*(_QWORD *)v917 + 440LL))(v917, *((_BYTE *)v4 + 8) != 0);
          v110 = v917;
          if ( v917 )
          {
            v917 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v110 + 8LL))(v110);
          }
        }
        RdpXSPtr<RdpXTapVcCallbackItem>::SafeRelease(&v922);
      }
      return 0;
    }
    v135 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v136 = RdpX_GetActivityIdPrefix(v17, v87, v16);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v136);
      v135 = WPP_GLOBAL_Control;
    }
    v137 = *((unsigned __int16 *)v4 + 1);
    if ( (unsigned __int16)v137 < 0x10u )
    {
      if ( v135 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v135[7] & 1) != 0 && *((_BYTE *)v135 + 25) >= 2u )
      {
        v138 = RdpX_GetActivityIdPrefix(v17, v87, v16);
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v138, v137);
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
    v140 = *((_DWORD *)v4 + 2);
    v926[1] = v140;
    v141 = *((_DWORD *)v4 + 1);
    v926[0] = v141;
    if ( v141 == 5 )
    {
      v928 = *((_DWORD *)v4 + 3);
      v927 = 0;
      goto LABEL_242;
    }
    if ( (unsigned int)(v141 - 1) <= 3 )
    {
      v927 = *((_DWORD *)v4 + 3);
      v928 = 0;
LABEL_242:
      v142 = *((_QWORD *)v5 + 15);
      if ( v142 )
        (*(void (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v142 + 160LL))(v142, v926);
      return 0;
    }
    if ( v141 == 6 )
    {
      v918 = 0;
      RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow((RdpRemoteAppCore *)((char *)v5 - 48), v140, &v918);
      if ( RemoteAppWindow < 0 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v146 = *((_DWORD *)v4 + 2);
          v147 = RdpX_GetActivityIdPrefix(v144, v143, v145);
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            95,
            &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
            v147,
            v146);
        }
        v38 = v918;
        if ( v918 )
        {
          v918 = 0;
          goto LABEL_106;
        }
        return (unsigned int)RemoteAppWindow;
      }
      (*(void (__fastcall **)(struct RdpXInterfaceRemoteAppWindow *, __int64))(*(_QWORD *)v918 + 264LL))(v918, 0x100000);
      v148 = v918;
      if ( v918 )
      {
        v918 = 0;
LABEL_387:
        (*(void (__fastcall **)(struct RdpXInterfaceRemoteAppWindow *))(*(_QWORD *)v148 + 8LL))(v148);
        return 0;
      }
      return 0;
    }
    if ( v141 == 7 )
    {
      v919 = 0;
      RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow((RdpRemoteAppCore *)((char *)v5 - 48), v140, &v919);
      if ( RemoteAppWindow < 0 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v152 = *((_DWORD *)v4 + 2);
          v153 = RdpX_GetActivityIdPrefix(v150, v149, v151);
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            96,
            &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
            v153,
            v152);
        }
        v38 = v919;
        if ( v919 )
        {
          v919 = 0;
          goto LABEL_106;
        }
        return (unsigned int)RemoteAppWindow;
      }
      (*(void (__fastcall **)(struct RdpXInterfaceRemoteAppWindow *, __int64))(*(_QWORD *)v919 + 264LL))(v919, 0x200000);
      v148 = v919;
      if ( v919 )
      {
        v919 = 0;
        goto LABEL_387;
      }
      return 0;
    }
    if ( v141 != 8 )
    {
      if ( v141 == 9 )
      {
        v903 = 0;
        v889 = 0;
        v197 = (unsigned int)*((unsigned __int16 *)v4 + 6) + 14;
        if ( *((unsigned __int16 *)v4 + 1) >= (unsigned int)v197 )
        {
          RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow((RdpRemoteAppCore *)((char *)v5 - 48), v140, &v903);
          if ( RemoteAppWindow >= 0 )
          {
            v204 = RdpRemoteAppCore::GetDesktopRemoteAppWindow((RdpRemoteAppCore *)((char *)v5 - 48), v903);
            RdpXSPtr<RdpXInterfaceLayerManager>::operator=(&v889, v204);
            v205 = v889;
            if ( v889 )
            {
              if ( (unsigned __int16)(*((_WORD *)v4 + 6) - 3) <= 0x205u )
              {
                v206 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v889 + 424LL))(
                         v889,
                         (__int64)v4 + 14,
                         *((unsigned __int16 *)v4 + 6) >> 1);
                v207 = MapXResultToHR(v206);
                v210 = v207;
                if ( v207 < 0
                  && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                  && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v211 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v208, v209);
                  WPP_SF_DsD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    108,
                    (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                    v211,
                    (__int64)"SetOverlayDesc failed",
                    v210);
                }
                v205 = v889;
              }
              if ( v205 )
              {
                v889 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v205 + 8LL))(v205);
              }
            }
            v148 = v903;
            if ( !v903 )
              return 0;
            v903 = 0;
            goto LABEL_387;
          }
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v202 = *((_DWORD *)v4 + 2);
            v203 = RdpX_GetActivityIdPrefix(v200, v199, v201);
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              107,
              &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v203,
              v202);
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v198 = RdpX_GetActivityIdPrefix(v197, 0, v139);
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              106,
              &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v198,
              -2147418113);
          }
          RemoteAppWindow = -2147418113;
        }
        v38 = v903;
        if ( !v903 )
          return (unsigned int)RemoteAppWindow;
        v903 = 0;
        goto LABEL_106;
      }
      if ( v141 == 10 )
      {
        v920 = 0;
        v894 = 0;
        RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow((RdpRemoteAppCore *)((char *)v5 - 48), v140, &v920);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v215 = *((_DWORD *)v4 + 2);
            v216 = RdpX_GetActivityIdPrefix(v213, v212, v214);
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              109,
              &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v216,
              v215);
          }
          v38 = v920;
          if ( v920 )
          {
            v920 = 0;
            goto LABEL_106;
          }
          return (unsigned int)RemoteAppWindow;
        }
        v217 = RdpRemoteAppCore::GetDesktopRemoteAppWindow((RdpRemoteAppCore *)((char *)v5 - 48), v920);
        RdpXSPtr<RdpXInterfaceLayerManager>::operator=(&v894, v217);
        if ( v894 )
        {
          v218 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v894 + 416LL))(v894, 0);
          v219 = MapXResultToHR(v218);
          v222 = v219;
          if ( v219 < 0
            && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v223 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v220, v221);
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              110,
              (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v223,
              (__int64)"UpdateOverlayIcon failed",
              v222);
          }
          v224 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v894 + 424LL))(v894, 0, 0);
          v225 = MapXResultToHR(v224);
          v228 = v225;
          if ( v225 < 0
            && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v229 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v226, v227);
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              111,
              (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v229,
              (__int64)"SetOverlayDesc failed",
              v228);
          }
          v230 = v894;
          if ( v894 )
          {
            v894 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v230 + 8LL))(v230);
          }
        }
        v148 = v920;
        if ( v920 )
        {
          v920 = 0;
          goto LABEL_387;
        }
      }
      return 0;
    }
    v154 = (RdpRemoteAppCore *)((char *)v5 - 48);
    v866 = 0;
    v863 = 0;
    v861 = 0;
    v862 = 0;
    v869 = (RdpRemoteAppCore *)((char *)v5 - 48);
    RemoteAppWindow = RdpRemoteAppCore::GetWndPlugin((RdpRemoteAppCore *)((char *)v5 - 48), &v861);
    if ( RemoteAppWindow < 0 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v158 = RdpX_GetActivityIdPrefix(v156, v155, v157);
        v159 = 97;
        v160 = "GetWndPlugin failed";
LABEL_271:
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v159,
          (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v158,
          (__int64)v160,
          RemoteAppWindow);
      }
LABEL_272:
      v161 = v862;
      if ( v862 )
      {
        v862 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v161 + 8LL))(v161);
      }
      v162 = v861;
      if ( v861 )
      {
        v861 = 0;
        (*(void (__fastcall **)(struct ITSWndPluginEx *))(*(_QWORD *)v162 + 16LL))(v162);
      }
      v163 = v863;
      if ( v863 )
      {
        v863 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v163 + 8LL))(v163);
      }
      v38 = v866;
      if ( v866 )
      {
        v866 = 0;
        goto LABEL_106;
      }
      return (unsigned int)RemoteAppWindow;
    }
    RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow(v154, *((_DWORD *)v4 + 2), &v866);
    if ( RemoteAppWindow < 0 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v168 = *((_DWORD *)v4 + 2);
        v169 = RdpX_GetActivityIdPrefix(v165, v164, v166);
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v169, v168);
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
        v170 = RdpX_GetActivityIdPrefix(v165, v164, v166);
        v171 = 99;
LABEL_291:
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v171,
          &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v170,
          -2147418113);
LABEL_292:
        RemoteAppWindow = -2147418113;
        goto LABEL_272;
      }
      RemoteAppWindow = (*(__int64 (__fastcall **)(struct ITSWndPluginEx *, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v861 + 56LL))(
                          v861,
                          *((unsigned __int8 *)v4 + 18),
                          *((unsigned __int16 *)v4 + 8),
                          &v862);
      if ( RemoteAppWindow < 0 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_272;
        }
        v158 = RdpX_GetActivityIdPrefix(v173, v172, v174);
        v159 = 100;
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
        v170 = RdpX_GetActivityIdPrefix(v165, v164, v166);
        v171 = 101;
        goto LABEL_291;
      }
      if ( (*((_BYTE *)v4 + 19) & 2) != 0 )
      {
        LOBYTE(v167) = *((_BYTE *)v4 + 24);
        v175 = *((unsigned __int16 *)v4 + 13);
      }
      else
      {
        v175 = 0;
        LOWORD(v167) = 32;
      }
      v176 = *((unsigned int *)v4 + 7);
      v177 = v176 + *((_DWORD *)v4 + 8) + 36;
      LODWORD(v874) = (unsigned __int16)v175;
      v178 = v177 + (unsigned int)(unsigned __int16)v175;
      if ( *((unsigned __int16 *)v4 + 1) < (unsigned int)v178 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_292;
        }
        v170 = RdpX_GetActivityIdPrefix(v178, v175, v176);
        v171 = 102;
        goto LABEL_291;
      }
      RemoteAppWindow = (*(__int64 (__fastcall **)(struct ITSWndPluginEx *, _QWORD, _QWORD, __int64, _DWORD, _DWORD, __int64, _DWORD, __int64, _DWORD, __int64, _DWORD, __int64 *))(*(_QWORD *)v861 + 64LL))(
                          v861,
                          *((unsigned __int8 *)v4 + 18),
                          *((unsigned __int16 *)v4 + 8),
                          v167,
                          *((unsigned __int16 *)v4 + 10),
                          *((unsigned __int16 *)v4 + 11),
                          (__int64)v4 + 36,
                          v874,
                          (__int64)v4 + (unsigned __int16)v175 + 36,
                          *((_DWORD *)v4 + 7),
                          (__int64)v4 + (unsigned __int16)v175 + v176 + 36,
                          *((_DWORD *)v4 + 8),
                          &v862);
      if ( RemoteAppWindow < 0 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_272;
        }
        v158 = RdpX_GetActivityIdPrefix(v180, v179, v181);
        v159 = 103;
LABEL_298:
        v160 = "CreateCachedIcon failed";
        goto LABEL_271;
      }
      v154 = v869;
    }
    v182 = RdpRemoteAppCore::GetDesktopRemoteAppWindow(v154, v866);
    RdpXSPtr<RdpXInterfaceLayerManager>::operator=(&v863, v182);
    if ( v863 )
    {
      v183 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v863 + 416LL))(v863, v862);
      v186 = v183;
      if ( v183 < 0
        && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v187 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v184, v185);
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          104,
          (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v187,
          (__int64)"Failed to UpdateOverlayIcon",
          v186);
      }
      v188 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v863 + 424LL))(v863, 0, 0);
      v189 = MapXResultToHR(v188);
      v192 = v189;
      if ( v189 < 0
        && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v193 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v190, v191);
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          105,
          (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v193,
          (__int64)"Failed to reset the old overlay description",
          v192);
      }
    }
    v194 = v862;
    if ( v862 )
    {
      v862 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v194 + 8LL))(v194);
    }
    v195 = v861;
    if ( v861 )
    {
      v861 = 0;
      (*(void (__fastcall **)(struct ITSWndPluginEx *))(*(_QWORD *)v195 + 16LL))(v195);
    }
    v196 = v863;
    if ( v863 )
    {
      v863 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v196 + 8LL))(v196);
    }
    v148 = v866;
    if ( !v866 )
      return 0;
    v866 = 0;
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
      v116 = RdpRemoteAppCore::SetV2CoreProperty((RdpRemoteAppCore *)((char *)v5 - 48), 4u);
      v119 = v116;
      if ( v116 < 0
        && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v120 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v117, v118);
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          68,
          (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v120,
          (__int64)"Failed to set the V2 core property",
          v119);
      }
    }
    v121 = RdpRemoteAppCore::ReceiveHandshake((RdpRemoteAppCore *)((char *)v5 - 48), v4, (unsigned int *)v5 + 43);
    v124 = v121;
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
        v125 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v122, v123);
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          69,
          (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v125,
          (__int64)"RemoteAppHandshake::ReceiveHandshake failed",
          v124);
      }
      LOBYTE(v122) = 3;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_RailV2ConnectionInfoDisclosure>::__private_IsEnabledPreCheck(
        `wil::Feature<__WilFeatureTraits_Feature_EnableRailV2>::GetImpl'::`2'::impl,
        v122);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableRailV2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnableRailV2>::GetImpl'::`2'::impl) )
        v126 = *(unsigned int (**)(void))(**((_QWORD **)v5 + 12) + 56LL);
      else
        v126 = *(unsigned int (**)(void))(**((_QWORD **)v5 + 11) + 48LL);
      return v126();
    }
  }
  if ( (_DWORD)v17 == 7 )
  {
LABEL_1134:
    v831 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v832 = RdpX_GetActivityIdPrefix(v17, WPP_GLOBAL_Control, v16);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v832);
      v831 = WPP_GLOBAL_Control;
    }
    v833 = *((unsigned __int16 *)v4 + 1);
    if ( (unsigned __int16)v833 < 0x10u )
    {
      if ( v831 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v831[7] & 1) != 0 && *((_BYTE *)v831 + 25) >= 2u )
      {
        v834 = RdpX_GetActivityIdPrefix(v17, v831, v16);
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v834);
      }
      RemoteAppWindow = -2147467259;
      RdpRemoteAppCore::LogRemoteAppError((char *)v5 + 16, L"TS_RAIL_ORDER_EXEC_RESULT too short", 2147500037LL, 0, 0);
      return (unsigned int)RemoteAppWindow;
    }
    v835 = *((unsigned __int16 *)v4 + 7);
    if ( v833 != v835 + 16 )
    {
      if ( v831 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v831[7] & 1) != 0 && *((_BYTE *)v831 + 25) >= 2u )
      {
        v836 = RdpX_GetActivityIdPrefix(v835 + 16, v831, v16);
        WPP_SF_DLD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          72,
          &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v836,
          v833,
          v835 + 16);
      }
      RemoteAppWindow = -2147467259;
      v101 = 2147500037LL;
      v845 = (unsigned __int16 *)(*((unsigned __int16 *)v4 + 7) + 16LL);
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
    v837 = *((_DWORD *)v4 + 2);
    v838 = (char *)v5 + 16;
    if ( *((_WORD *)v4 + 3) )
    {
      if ( v837 )
      {
        if ( v837 > 0 )
          v839 = (unsigned __int16)v837 | 0x80070000;
        else
          v839 = *((_DWORD *)v4 + 2);
      }
      else
      {
        v839 = -2147467259;
      }
      RdpRemoteAppCore::LogRemoteAppErrorF(
        v838,
        L"ExecResultRailOrderReceived_Error: ApplicationName=%s, Flags=0x%hx, Result=0x%hx, RawResult=0x%x",
        v839,
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
        v838,
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
      v5 = v869;
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
    LODWORD(v849) = *((__int16 *)v4 + 6);
    LODWORD(v845) = *((unsigned __int16 *)v4 + 5);
    LODWORD(cchToCopy) = *((unsigned __int16 *)v4 + 4);
    RdpRemoteAppCore::LogRemoteAppEventF(
      (char *)v5 + 16,
      L"LocalMoveSizeRailOrderReceived: WindowId=0x%x, IsStart=%hu, Type=0x%hx, X=%hi, Y=%hi",
      0,
      *((unsigned int *)v4 + 1),
      cchToCopy,
      v845,
      v849,
      *((__int16 *)v4 + 7));
    v883 = 0;
    v882 = 0;
    RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow(
                        (RdpRemoteAppCore *)((char *)v5 - 48),
                        *((_DWORD *)v4 + 1),
                        &v883);
    if ( RemoteAppWindow >= 0 )
    {
      v62 = RdpRemoteAppCore::GetDesktopRemoteAppWindow((RdpRemoteAppCore *)((char *)v5 - 48), v883);
      RdpXSPtr<RdpXInterfaceLayerManager>::operator=(&v882, v62);
      v66 = v882;
      if ( !v882 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control )
        {
          v67 = (_DWORD)v882 + 8;
          if ( ((unsigned __int8)((_BYTE)v882 + 8) & (_BYTE)WPP_GLOBAL_Control[7]) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v68 = RdpX_GetActivityIdPrefix(v64, v63, v65);
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v67 + 68,
              (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v68,
              (__int64)"spDesktopRemoteAppWindow",
              1);
            v66 = v882;
          }
        }
        RemoteAppWindow = 1;
        if ( !v66 )
          goto LABEL_104;
        v882 = 0;
        v61 = *v66;
        goto LABEL_103;
      }
      if ( *((_WORD *)v4 + 4) )
      {
        v916 = 0;
        v69 = RemoteAppMoveSizeInfo::CreateInstance((char *)v4 + 4, &v916);
        RemoteAppWindow = MapXResultToHR(v69);
        if ( RemoteAppWindow >= 0 )
        {
          (*(void (__fastcall **)(__int64 *, __int64))(*v882 + 392))(v882, v916);
        }
        else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
               && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v73 = RdpX_GetActivityIdPrefix(v71, v70, v72);
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            77,
            (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
            v73,
            (__int64)"Failed to create RemoteAppMoveSizeInfo",
            RemoteAppWindow);
        }
        v74 = v916;
        if ( v916 )
        {
          v916 = 0;
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
        (*(void (__fastcall **)(__int64 *, __int64, _QWORD, __int64, int))(*v882 + 400))(v882, 1, 0, v76, v75);
      }
    }
    else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
           && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v59 = RdpX_GetActivityIdPrefix(v57, v56, v58);
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        75,
        (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
        v59,
        (__int64)"Failed to find window",
        RemoteAppWindow);
    }
    v60 = v882;
    if ( !v882 )
    {
LABEL_104:
      v38 = v883;
      if ( !v883 )
        return (unsigned int)RemoteAppWindow;
      v883 = 0;
      goto LABEL_106;
    }
    v882 = 0;
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
    (char *)v869 + 16,
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
  v902 = 0;
  v901 = 0;
  RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow(
                      (RdpRemoteAppCore *)((char *)v869 - 48),
                      *((_DWORD *)v4 + 1),
                      &v902);
  if ( RemoteAppWindow < 0 )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v37 = RdpX_GetActivityIdPrefix(v35, v34, v36);
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        80,
        (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
        v37,
        (__int64)"Failed to find window",
        RemoteAppWindow);
    }
LABEL_71:
    v38 = v902;
    if ( !v902 )
      return (unsigned int)RemoteAppWindow;
    v902 = 0;
LABEL_106:
    (*(void (__fastcall **)(struct RdpXInterfaceRemoteAppWindow *))(*(_QWORD *)v38 + 8LL))(v38);
    return (unsigned int)RemoteAppWindow;
  }
  v39 = RdpRemoteAppCore::GetDesktopRemoteAppWindow((RdpRemoteAppCore *)((char *)v869 - 48), v902);
  RdpXSPtr<RdpXInterfaceLayerManager>::operator=(&v901, v39);
  v42 = v901;
  if ( !v901 )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control )
    {
      v43 = v901 + 8;
      if ( ((unsigned __int8)(v901 + 8) & (_BYTE)WPP_GLOBAL_Control[7]) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v44 = RdpX_GetActivityIdPrefix(v41, v40, 0);
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v43 + 73,
          (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v44,
          (__int64)"spDesktopRemoteAppWindow",
          1);
        v42 = v901;
      }
    }
    RemoteAppWindow = 1;
    if ( v42 )
    {
      v901 = 0;
      (*(void (**)(void))(*(_QWORD *)v42 + 8LL))();
    }
    goto LABEL_71;
  }
  v45 = 0;
  v934 = 0;
  memset(v933, 0, sizeof(v933));
  do
  {
    v46 = *((__int16 *)v4 + (unsigned int)v45 + 4);
    v47 = 4 * v45++ + 8;
    *(_DWORD *)((char *)v933 + v47) = v46;
  }
  while ( v45 < 8 );
  (*(void (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)v42 + 408LL))(v42, v933);
  v48 = v901;
  if ( v901 )
  {
    v901 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 8LL))(v48);
  }
  v38 = v902;
  if ( v902 )
  {
    v902 = 0;
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
