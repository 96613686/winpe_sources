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
- `0x18057f0dc`: `Invalid size for TS_RAIL_ORDER_LOCALMOVESIZE [%d]`
- `0x18057f117`: `LocalMoveSizeRailOrderReceived: WindowId=0x%x, IsStart=%hu, Type=0x%hx, X=%hi, Y=%hi`
- `0x18057f2c7`: `Failed to create RemoteAppMoveSizeInfo`
- `0x18057eab9`: `m_remoteAppPlugin.get()`
- `0x18057eb09`: `m_spRemoteAppPlugin`
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
- `0x1805800b9`: `CreateCachedIcon failed`
- `0x180580d0d`: `CreateCachedIcon failed`
- `0x180581157`: `CreateCachedIcon failed`
- `0x180584025`: `CreateCachedIcon failed`
- `0x180584bdb`: `CreateCachedIcon failed`
- `0x18058026c`: `Failed to UpdateOverlayIcon`
- `0x180580699`: `UpdateOverlayIcon failed`
- `0x18057f4fe`: `UpdateAppID failed`
- `0x1805809e7`: `UpdateAppID failed`
- `0x180580896`: `GetAppIdRespExRailOrderReceived: WindowId=0x%x, CensoredAppId=%s, ProcessId=%u, CensoredProcessImageName=%s`
- `0x180581e64`: `Invalid size of TS_RAIL_ORDER_WINDOW_CREATE_BODY PDU`
- `0x180581f1f`: `Invalid size of TS_RAIL_ORDER_WINDOW_CREATE_BODY PDU`
- `0x18058235e`: `CreateWindowRepresentation failed`
- `0x180582590`: `WindowCreateRailOrderReceived: WindowId=0x%x, FieldsValidFlags=0x%x, WindowOwnerId=0x%x, Style=0x%08x, StyleEx=0x%08x, ShowState=%hhu, EnforceServerZOrder=%hhu, TitleBytes=%hu, Title=%s, OffsetX=%i, OffsetY=%i, Width=%i, Height=%i, WindowClientDeltaX=%i, WindowClientDeltaY=%i, ResizeMarginLeft=%i, ResizeMarginTop=%i, ResizeMarginRight=%i, ResizeMarginBottom=%i, NumVisibilityRects=%hu`
- `0x1805827c2`: `WindowCreateRailOrderReceived_VisibilityRect[%i]: WindowId=0x%x, Left=%i, Top=%i, Right=%i, Bottom=%i`
- `0x180581dc4`: `WindowChangeRailOrderReceived: WindowsId=0x%x, FieldsValidFlags=0x%x, WindowOwnerId=0x%x, Style=0x%08x, StyleEx=0x%08x, ShowState=%hhu, EnforceServerZOrder=%hhu, TitleBytes=%hu, Title=%s`
- `0x18057fb42`: `Invalid size for TS_RAIL_ORDER_COMPARTMENTINFO [%d]`
- `0x18057fb65`: `CompartmentInfoRailOrderReceived: Open=%d, ConversionMode=0x%x, SentenceMode=0x%x, KanaOn=%d`
- `0x180580d9c`: `UpdateIcon failed`
- `0x1805811e5`: `UpdateIcon failed`
- `0x180580ac3`: `Invalid size of TS_RAIL_ORDER_WINDOW_CACHED_ICON PDU`
- `0x180580b6f`: `WindowCachedIconRailOrderReceived: WindowId=0x%x, NumIcons=%hhu, CacheEntry=0x%hx, CacheId=0x%hhx, IconFlags=0x%hhx`
- `0x180583e7e`: `Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Create PDU`
- `0x180584572`: `Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Create PDU`
- `0x18058460f`: `Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Create PDU`
- `0x180584a37`: `Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Create PDU`
- `0x180584c23`: `Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Create PDU`
- `0x180584cd3`: `Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Create PDU`
- `0x180584790`: `CreateShellNotifyInfo failed`
- `0x180583d31`: `CreateShellNotifyInfo->SetTip failed`
- `0x1805848f6`: `CreateShellNotifyInfo->SetTip failed`
- `0x180581231`: `Invalid size of TS_RAIL_ORDER_WINDOW_DELETE_BODY PDU`
- `0x1805812b3`: `WindowDeleteRailOrderReceived: WindowId=0x%x`
- `0x18058149d`: `DeleteWindow failed`
- `0x180581057`: `WindowIconRailOrderReceived: WindowId=0x%x, NumIcons=%hhu, CacheEntry=0x%hx, CacheId=0x%hhx, IconFlags=0x%hhx, Width=%hu, Height=%hu, Bpp=%hhu, ColorTableBytes=%hu, BitsMaskBytes=%u, BitsColorBytes=%u`
- `0x180583f92`: `NotifyIconChangeRailOrderReceived_Cached: WindowId=0x%x, NotifyIconId=0x%x, NumIcons=%hhu, IsCachedIcon=%hhu, StateFlags=0x%x, PDUFlags=0x%x, ToolTipBytes=%hu, ToolTip=%s, CacheEntry=0x%hx, CacheId=0x%hhx, IconFlags=0x%hhx`
- `0x1805842a9`: `NotifyIconChangeRailOrderReceived_NonCached: WindowId=0x%x, NotifyIconId=0x%x, NumIcons=%hhu, IsCachedIcon=%hhu,StateFlags=0x%x, PDUFlags=0x%x, ToolTipBytes=%hu, ToolTip=%s, CacheEntry=0x%hx, CacheId=0x%hhx, IconFlags=0x%hhx, Width=%hu, Height=%hu, Bpp=%hhu, ColorTableBytes=%hu, BitsMaskBytes=%u, BitsColorBytes=%u`
- `0x180584483`: `NotifyIconChangeRailOrderReceived_NoIcons: WindowId=0x%x, NotifyIconId=0x%x, NumIcons=%hhu, IsCachedIcon=%hhu, StateFlags=0x%x, PDUFlags=0x%x, ToolTipBytes=%hu, ToolTip=%s`
- `0x1805837ea`: `RdpX_Strings_CreateConstXChar16StringWithSpecifiedSize failed`
- `0x180583894`: `RdpX_Strings_CreateConstXChar16StringWithSpecifiedSize failed`
- `0x180583dc1`: `RdpX_Strings_CreateConstXChar16StringWithSpecifiedSize failed`
- `0x18058497f`: `RdpX_Strings_CreateConstXChar16StringWithSpecifiedSize failed`
- `0x180583e34`: `CreateShellNotifyInfo->SetWSNState failed`
- `0x1805849eb`: `CreateShellNotifyInfo->SetWSNState failed`
- `0x180584b4f`: `NotifyIconCreateRailOrderReceived_Cached: WindowId=0x%x, NotifyIconId=0x%x, NumIcons=%hhu, IsCachedIcon=%hhu, StateFlags=0x%x, PDUFlags=0x%x, ToolTipBytes=%hu, ToolTip=%s, CacheEntry=0x%hx, CacheId=0x%hhx, IconFlags=0x%hhx`
- `0x180584e65`: `NotifyIconCreateRailOrderReceived_NonCached: WindowId=0x%x, NotifyIconId=0x%x, NumIcons=%hhu, IsCachedIcon=%hhu, StateFlags=0x%x, PDUFlags=0x%x, ToolTipBytes=%hu, ToolTip=%s, CacheEntry=0x%hx, CacheId=0x%hhx, IconFlags=0x%hhx, Width=%hu, Height=%hu, Bpp=%hhu, ColorTableBytes=%hu, BitsMaskBytes=%u, BitsColorBytes=%u`
- `0x18058503b`: `NotifyIconCreateRailOrderReceived_NoIcons: WindowId=0x%x, NotifyIconId=0x%x, NumIcons=%hhu, IsCachedIcon=%hhu, StateFlags=0x%x, PDUFlags=0x%x, ToolTipBytes=%hu, ToolTip=%s`
- `0x1805832ee`: `Invalid size of TS_RAIL_ORDER_NOTIFYICON_DELETE PDU`
- `0x180583378`: `NotifyIconDeleteRailOrderReceived: WindowId=0x%x, NotifyIconId=0x%x`

## pseudocode

```c
__int64 __fastcall RdpRemoteAppCore::OnRailPdu(
        RdpRemoteAppCore *this,
        struct tagTS_RAIL_PDU *a2,
        __int64 a3,
        __int64 a4)
{
  unsigned int v4; // ebx
  struct tagTS_RAIL_PDU *v5; // r13
  RdpRemoteAppCore *v6; // rdi
  int ActivityIdPrefix; // eax
  int v8; // edx
  const char *v9; // rcx
  int RemoteAppWindow; // esi
  const struct tagTS_RAIL_PDU *v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  unsigned int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rdx
  __int64 v23; // rdx
  HKEY v24; // rax
  unsigned int v25; // eax
  int v26; // ebx
  unsigned int v27; // eax
  int v28; // eax
  const wchar_t *v29; // rdx
  __int64 v30; // r8
  __int64 v31; // rcx
  HKEY v32; // rax
  int v33; // ebx
  unsigned int v34; // eax
  int v35; // ebx
  unsigned int v36; // eax
  __int64 v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // r8
  __int64 v40; // r9
  int v41; // eax
  struct RdpXInterfaceRemoteAppWindow *v42; // rcx
  struct RdpInterfaceDesktopRemoteAppWindow *v43; // rax
  __int64 v44; // rdx
  __int64 v45; // rcx
  __int64 v46; // r9
  __int64 v47; // r8
  int v48; // r15d
  int v49; // eax
  int v50; // r9d
  int v51; // edx
  __int64 v52; // rcx
  __int64 v53; // rcx
  HKEY v54; // rax
  int v55; // ebx
  int v56; // edi
  int v57; // esi
  unsigned int v58; // eax
  int v59; // ebx
  unsigned int v60; // eax
  __int64 v61; // rdx
  __int64 v62; // rcx
  __int64 v63; // r8
  __int64 v64; // r9
  int v65; // eax
  __int64 *v66; // rcx
  __int64 v67; // rax
  struct RdpInterfaceDesktopRemoteAppWindow *v68; // rax
  __int64 v69; // rdx
  __int64 v70; // rcx
  __int64 v71; // r8
  __int64 v72; // r9
  __int64 *v73; // r10
  int v74; // r15d
  int v75; // eax
  unsigned int v76; // eax
  __int64 v77; // rdx
  __int64 v78; // rcx
  __int64 v79; // r8
  __int64 v80; // r9
  int v81; // eax
  __int64 v82; // rcx
  int v83; // ecx
  __int64 v84; // r9
  unsigned int v85; // eax
  int v86; // ebx
  unsigned int v87; // eax
  int v88; // ebx
  unsigned int v89; // eax
  const unsigned __int16 *v90; // rax
  __int64 v91; // rdx
  __int64 v92; // rcx
  __int64 v93; // r8
  __int64 v94; // r9
  int v95; // eax
  __int64 v96; // rdx
  __int64 v97; // rdx
  __int64 v98; // rdx
  __int64 v99; // rdx
  __int64 v100; // rdx
  __int64 v101; // rcx
  __int64 v102; // r8
  __int64 v103; // r9
  unsigned int v104; // eax
  int v105; // ebx
  __int64 v106; // rax
  HKEY v107; // rax
  unsigned int v108; // eax
  int v109; // esi
  unsigned int v110; // eax
  __int64 v111; // r8
  const wchar_t *v112; // rdx
  __int64 v113; // rcx
  __int64 v114; // rdx
  __int64 v115; // rcx
  __int64 v116; // r8
  __int64 v117; // r9
  int v118; // ebx
  unsigned int v119; // eax
  struct RdpInterfaceDesktopRemoteAppWindow *DesktopRemoteAppWindow; // rax
  __int64 v121; // rcx
  HKEY v122; // rax
  unsigned int v123; // eax
  int v124; // ebx
  unsigned int v125; // eax
  unsigned int v126; // eax
  __int64 v127; // rdx
  int v128; // ebx
  __int64 v129; // r8
  __int64 v130; // r9
  int v131; // eax
  __int64 v132; // rdx
  int v133; // esi
  __int64 v134; // r8
  __int64 v135; // r9
  int v136; // eax
  unsigned int (*v137)(void); // rax
  HKEY v139; // rax
  unsigned int v140; // eax
  int v141; // ebx
  unsigned int v142; // eax
  int v143; // edx
  bool v144; // zf
  int v145; // r8d
  HKEY v146; // rax
  unsigned int v147; // eax
  int v148; // ebx
  unsigned int v149; // eax
  __int64 v150; // r8
  __int64 v151; // r9
  int v152; // ecx
  __int64 v153; // rcx
  __int64 v154; // rdx
  __int64 v155; // rcx
  __int64 v156; // r8
  __int64 v157; // r9
  int v158; // ebx
  unsigned int v159; // eax
  struct RdpXInterfaceRemoteAppWindow *v160; // rcx
  __int64 v161; // rdx
  __int64 v162; // rcx
  __int64 v163; // r8
  __int64 v164; // r9
  int v165; // ebx
  unsigned int v166; // eax
  RdpRemoteAppCore *v167; // rbx
  __int64 v168; // rdx
  __int64 v169; // rcx
  __int64 v170; // r8
  __int64 v171; // r9
  int v172; // eax
  int v173; // edx
  const char *v174; // rcx
  __int64 v175; // rcx
  struct ITSWndPluginEx *v176; // rcx
  __int64 v177; // rcx
  __int64 v178; // rdx
  __int64 v179; // rcx
  __int64 v180; // r8
  __int64 v181; // r9
  int v182; // ebx
  unsigned int v183; // eax
  unsigned int v184; // eax
  __int64 v185; // rdx
  __int64 v186; // rdx
  __int64 v187; // rcx
  __int64 v188; // r8
  __int64 v189; // r9
  __int64 v190; // rdx
  __int64 v191; // r8
  int v192; // eax
  __int64 v193; // rcx
  __int64 v194; // rdx
  __int64 v195; // rcx
  __int64 v196; // r8
  __int64 v197; // r9
  struct RdpInterfaceDesktopRemoteAppWindow *v198; // rax
  __int64 v199; // rdx
  int v200; // ebx
  __int64 v201; // r8
  __int64 v202; // r9
  int v203; // eax
  unsigned int v204; // eax
  __int64 v205; // rdx
  int v206; // ebx
  __int64 v207; // r8
  __int64 v208; // r9
  int v209; // eax
  __int64 v210; // rcx
  struct ITSWndPluginEx *v211; // rcx
  __int64 v212; // rcx
  __int64 v213; // rcx
  unsigned int v214; // eax
  __int64 v215; // rdx
  __int64 v216; // rcx
  __int64 v217; // r8
  __int64 v218; // r9
  int v219; // ebx
  unsigned int v220; // eax
  struct RdpInterfaceDesktopRemoteAppWindow *v221; // rax
  __int64 v222; // rcx
  unsigned int v223; // eax
  __int64 v224; // rdx
  int v225; // ebx
  __int64 v226; // r8
  __int64 v227; // r9
  int v228; // eax
  __int64 v229; // rdx
  __int64 v230; // rcx
  __int64 v231; // r8
  __int64 v232; // r9
  int v233; // ebx
  unsigned int v234; // eax
  struct RdpInterfaceDesktopRemoteAppWindow *v235; // rax
  unsigned int v236; // eax
  __int64 v237; // rdx
  int v238; // ebx
  __int64 v239; // r8
  __int64 v240; // r9
  int v241; // eax
  unsigned int v242; // eax
  __int64 v243; // rdx
  int v244; // ebx
  __int64 v245; // r8
  __int64 v246; // r9
  int v247; // eax
  __int64 v248; // rcx
  int v249; // ebx
  unsigned int v250; // eax
  int v251; // ebx
  int v252; // edi
  int v253; // eax
  const unsigned __int16 *FileNameW; // rax
  int v255; // ebx
  const unsigned __int16 *v256; // rdi
  const unsigned __int16 *v257; // rax
  RdpRemoteAppCore *v258; // rbx
  __int64 v259; // rdx
  __int64 v260; // rcx
  __int64 v261; // r8
  __int64 v262; // r9
  int v263; // ebx
  unsigned int v264; // eax
  __int64 v265; // rdx
  int updated; // edi
  __int64 v267; // r8
  __int64 v268; // r9
  int v269; // eax
  __int64 v270; // rdx
  __int64 v271; // rcx
  __int64 v272; // r8
  __int64 v273; // r9
  int v274; // eax
  __int64 v275; // rdx
  __int64 v276; // rcx
  __int64 v277; // r8
  __int64 v278; // r9
  unsigned int v279; // eax
  char *v280; // rcx
  struct RdpXInterfaceRemoteAppWindow **v281; // rax
  __int64 v282; // rdx
  __int64 v283; // rcx
  __int64 v284; // r8
  __int64 v285; // r9
  int v286; // ebx
  unsigned int v287; // eax
  struct ITSWndPluginEx **v288; // rax
  __int64 v289; // rdx
  __int64 v290; // rcx
  __int64 v291; // r8
  __int64 v292; // r9
  int v293; // eax
  int v294; // edx
  const char *v295; // rcx
  __int64 v296; // rdi
  __int64 (__fastcall *v297)(__int64, _QWORD, _QWORD, void *); // rbx
  void *v298; // rax
  __int64 v299; // rdx
  __int64 v300; // rcx
  __int64 v301; // r8
  __int64 v302; // r9
  __int64 v303; // rsi
  BOOL v304; // ebx
  __int64 (__fastcall *v305)(__int64, __int64, BOOL); // rdi
  __int64 v306; // rax
  __int64 v307; // rdx
  __int64 v308; // rcx
  __int64 v309; // r8
  __int64 v310; // r9
  __int64 v311; // rdx
  __int64 v312; // rcx
  __int64 v313; // r8
  __int64 v314; // r9
  unsigned int v315; // eax
  __int64 v316; // rdx
  struct RdpXInterfaceRemoteAppWindow **v317; // rax
  __int64 v318; // rdx
  __int64 v319; // rcx
  __int64 v320; // r8
  __int64 v321; // r9
  int v322; // ebx
  unsigned int v323; // eax
  struct ITSWndPluginEx **v324; // rax
  int WndPlugin; // eax
  __int64 v326; // rdx
  __int64 v327; // rcx
  __int64 v328; // r8
  __int64 v329; // r9
  int v330; // eax
  int v331; // edx
  const char *v332; // rcx
  unsigned __int16 v333; // r14
  int v334; // esi
  __int64 v335; // rcx
  unsigned int v336; // esi
  __int64 v337; // rdi
  __int64 v338; // rbx
  __int64 v339; // r14
  __int64 (__fastcall *v340)(__int64, _QWORD, _QWORD, __int64, _DWORD, _DWORD, char *, _DWORD, __int64, _DWORD, __int64, _DWORD, void *); // rsi
  void *v341; // rax
  __int64 v342; // r9
  __int64 v343; // rdx
  __int64 v344; // rcx
  __int64 v345; // r8
  __int64 v346; // r9
  __int64 v347; // rsi
  __int64 (__fastcall *v348)(__int64, __int64, _QWORD); // rdi
  unsigned int v349; // ebx
  __int64 v350; // rax
  __int64 v351; // rdx
  __int64 v352; // rcx
  __int64 v353; // r8
  __int64 v354; // r9
  __int64 v355; // rdx
  __int64 v356; // rcx
  __int64 v357; // r8
  __int64 v358; // r9
  unsigned int v359; // eax
  struct RdpXInterfaceRemoteAppWindow **v360; // rax
  __int64 v361; // rdx
  __int64 v362; // rcx
  __int64 v363; // r8
  __int64 v364; // r9
  int v365; // ebx
  unsigned int v366; // eax
  struct ITSWndPluginEx **v367; // rax
  __int64 v368; // rdx
  __int64 v369; // rcx
  __int64 v370; // r8
  __int64 v371; // r9
  int v372; // eax
  int v373; // edx
  const char *v374; // rcx
  __int64 v375; // rdi
  __int64 v376; // rax
  int v377; // ebx
  __int64 v378; // rax
  __int64 v379; // rdi
  __int64 (__fastcall *v380)(__int64, _QWORD); // rbx
  __int64 v381; // rax
  unsigned int v382; // eax
  unsigned int v383; // eax
  __int64 v384; // rdx
  __int64 v385; // rcx
  __int64 v386; // r8
  __int64 v387; // r9
  __int64 v388; // rdx
  __int64 v389; // r8
  __int64 v390; // r9
  __int64 v391; // rcx
  unsigned int v392; // eax
  __int64 v393; // rdx
  unsigned int v394; // r14d
  __int64 v395; // rdx
  __int64 v396; // rcx
  __int64 v397; // r8
  __int64 v398; // r9
  unsigned int v399; // eax
  struct RdpXInterfaceRemoteAppWindow **v400; // rax
  __int64 v401; // rdx
  __int64 v402; // rcx
  __int64 v403; // r8
  __int64 v404; // r9
  int v405; // ebx
  unsigned int v406; // eax
  __int64 v407; // rax
  int v408; // r14d
  int v409; // esi
  int v410; // edi
  int v411; // ebx
  __int64 *v412; // rax
  __int64 v413; // rcx
  __int64 v414; // rax
  __int64 v415; // rax
  __int64 v416; // rax
  __int64 v417; // rax
  __int64 v418; // rax
  __int64 v419; // rax
  __int64 v420; // rax
  __int64 v421; // rdx
  __int64 v422; // rcx
  char *v423; // rdi
  __int64 v424; // r8
  __int64 v425; // r9
  unsigned int v426; // eax
  int v427; // esi
  RdpRemoteAppCore *v428; // r14
  __int64 v429; // rdx
  __int64 v430; // rax
  __int64 v431; // rax
  __int64 v432; // rax
  __int64 v433; // rdx
  __int64 v434; // r8
  __int64 v435; // r9
  __int64 v436; // rcx
  unsigned int v437; // eax
  __int64 v438; // rdx
  unsigned int v439; // r14d
  unsigned int v440; // eax
  struct RdpXInterfaceRemoteAppWindow **v441; // rax
  __int64 v442; // rdx
  __int64 v443; // rcx
  __int64 v444; // r8
  __int64 v445; // r9
  int v446; // ebx
  unsigned int v447; // eax
  __int64 v448; // rax
  __int64 v449; // rax
  __int64 v450; // rax
  __int64 v451; // rax
  __int64 v452; // rax
  __int64 v453; // rdx
  __int64 v454; // r8
  __int64 v455; // r9
  __int64 v456; // rcx
  unsigned int v457; // eax
  __int64 v458; // rdx
  int v459; // eax
  unsigned int v460; // r15d
  unsigned int v461; // r14d
  unsigned int v462; // eax
  struct ITSWndPluginEx **v463; // rax
  int v464; // r14d
  __int64 v465; // rdx
  __int64 v466; // rcx
  __int64 v467; // r8
  __int64 v468; // r9
  int v469; // eax
  struct RdpXInterfaceRemoteAppWindow **v470; // rax
  void *v471; // rax
  unsigned int WindowCallbacks; // eax
  __int64 v473; // rdx
  __int64 v474; // rcx
  __int64 v475; // r8
  __int64 v476; // r9
  int v477; // eax
  int v478; // edx
  const char *v479; // rcx
  void *v480; // rax
  unsigned int Object; // eax
  __int64 v482; // rdx
  __int64 v483; // rcx
  __int64 v484; // r8
  __int64 v485; // r9
  __int64 v486; // rdi
  __int64 (__fastcall *v487)(__int64, void *); // rbx
  void *v488; // rax
  __int64 v489; // rdx
  __int64 v490; // rcx
  __int64 v491; // r8
  __int64 v492; // r9
  __int64 v493; // rdi
  __int64 (__fastcall *v494)(__int64, __int64); // rbx
  __int64 v495; // rax
  unsigned int v496; // eax
  __int64 v497; // rdx
  __int64 v498; // rcx
  __int64 v499; // r8
  __int64 v500; // r9
  __int64 v501; // r15
  __int64 (__fastcall *v502)(__int64, __int64, _QWORD, __int64, __int128 *, void *); // r14
  void *v503; // rbx
  __int64 v504; // rax
  unsigned int v505; // esi
  __int64 v506; // rdi
  __int64 v507; // rax
  unsigned int v508; // eax
  __int64 v509; // rdx
  __int64 v510; // rcx
  __int64 v511; // r8
  __int64 v512; // r9
  __int64 v513; // rdi
  __int64 (__fastcall *v514)(__int64, bool); // rbx
  __int64 v515; // rax
  int v516; // eax
  unsigned int v517; // eax
  __int64 v518; // rax
  __int64 v519; // rax
  __int64 v520; // rax
  __int64 v521; // rax
  __int64 v522; // rax
  __int64 v523; // rax
  int v524; // r15d
  int v525; // r14d
  int v526; // ebx
  __int64 *v527; // rax
  __int64 v528; // rcx
  __int64 v529; // rax
  __int64 v530; // rax
  __int64 v531; // rax
  __int64 v532; // rdx
  __int64 v533; // rcx
  char *v534; // rbx
  __int64 v535; // r8
  __int64 v536; // r9
  unsigned int v537; // eax
  __int64 v538; // rdx
  __int64 v539; // rax
  __int64 v540; // rax
  __int64 v541; // rax
  __int64 v542; // rdi
  void (__fastcall *v543)(__int64, _QWORD); // rbx
  __int64 v544; // rax
  unsigned int v545; // eax
  __int64 v546; // rax
  __int64 v547; // rdx
  __int64 v548; // rcx
  __int64 v549; // r8
  __int64 v550; // r9
  unsigned int v551; // eax
  struct RdpXInterfaceRemoteAppWindow **v552; // rax
  __int64 v553; // rdx
  __int64 v554; // rcx
  __int64 v555; // r8
  __int64 v556; // r9
  int v557; // ebx
  unsigned int v558; // eax
  int v559; // ebx
  unsigned int v560; // eax
  __int64 v561; // rax
  int v562; // ebx
  unsigned int v563; // eax
  __int64 v564; // rax
  __int64 v565; // rdx
  __int64 v566; // rdx
  __int64 v567; // rcx
  __int64 v568; // r8
  __int64 v569; // r9
  unsigned int v570; // eax
  char *v571; // rcx
  struct ITSWndPluginEx **v572; // rax
  __int64 v573; // rdx
  __int64 v574; // rcx
  __int64 v575; // r8
  __int64 v576; // r9
  int v577; // eax
  unsigned int v578; // eax
  __int64 v579; // rax
  __int64 v580; // rdx
  HKEY v581; // rax
  unsigned int v582; // eax
  unsigned int v583; // eax
  __int64 v584; // rax
  RdpRemoteAppCore *v585; // rbx
  __int64 v586; // rax
  unsigned int v587; // r15d
  __int64 v588; // rdi
  __int64 (__fastcall *v589)(__int64, _QWORD, void *); // rbx
  void *v590; // rax
  __int64 v591; // rdx
  __int64 v592; // rcx
  int v593; // ebx
  __int64 v594; // r8
  __int64 v595; // r9
  __int64 v596; // rax
  unsigned int v597; // eax
  __int64 v598; // rax
  unsigned int v599; // eax
  __int64 v600; // rax
  __int64 v601; // rdx
  __int64 v602; // rcx
  __int64 v603; // r8
  __int64 v604; // r9
  unsigned int v605; // eax
  __int64 v606; // rdx
  unsigned int v607; // eax
  unsigned int v608; // esi
  wchar_t *v609; // rcx
  size_t v610; // rdx
  unsigned int v611; // eax
  int v612; // esi
  unsigned int v613; // ebx
  __int64 v614; // r9
  const unsigned __int16 *v615; // r8
  __int64 v616; // rdx
  __int64 v617; // rcx
  __int64 v618; // r8
  __int64 v619; // r9
  int v620; // eax
  struct ITSWndPluginEx **v621; // rax
  __int64 v622; // rdx
  __int64 v623; // rcx
  __int64 v624; // r8
  __int64 v625; // r9
  int v626; // eax
  unsigned int v627; // ebx
  __int64 v628; // rax
  __int64 v629; // rdx
  __int64 v630; // rcx
  __int64 v631; // r8
  __int64 v632; // r9
  unsigned int v633; // eax
  char *v634; // rcx
  struct ITSWndPluginEx **v635; // rax
  __int64 v636; // rdx
  __int64 v637; // rcx
  __int64 v638; // r8
  __int64 v639; // r9
  int v640; // eax
  int v641; // edx
  const char *v642; // rcx
  __int64 v643; // rdi
  __int64 (__fastcall *v644)(__int64, _QWORD, _QWORD, void *); // rbx
  void *v645; // rax
  __int64 v646; // rdx
  __int64 v647; // rcx
  __int64 v648; // r8
  __int64 v649; // r9
  __int64 v650; // rax
  __int64 v651; // rax
  struct RdpXInterfaceShellNotifyInformation *v652; // rbx
  __int64 v653; // rax
  unsigned int v654; // eax
  __int64 v655; // rdx
  __int64 v656; // rcx
  __int64 v657; // r8
  __int64 v658; // r9
  __int64 v659; // rcx
  __int64 v660; // r8
  __int64 v661; // r9
  __int64 v662; // rdx
  unsigned int v663; // eax
  __int64 v664; // rdx
  __int64 v665; // rcx
  unsigned int v666; // esi
  struct ITSWndPluginEx **v667; // rax
  __int64 v668; // rdx
  __int64 v669; // rcx
  __int64 v670; // r8
  __int64 v671; // r9
  int v672; // eax
  int v673; // edx
  const char *v674; // rcx
  __int64 v675; // rdi
  __int64 (__fastcall *v676)(__int64, _QWORD, _QWORD, void *); // rbx
  void *v677; // rax
  __int64 v678; // rdx
  __int64 v679; // rcx
  __int64 v680; // r8
  __int64 v681; // r9
  __int64 v682; // rax
  __int64 v683; // rbx
  char *v684; // r14
  void *v685; // rax
  unsigned int ConstXChar16StringWithSpecifiedSize; // eax
  __int64 v687; // rdx
  __int64 v688; // rcx
  __int64 v689; // r8
  __int64 v690; // r9
  int v691; // eax
  char *v692; // r15
  void *v693; // rax
  unsigned int v694; // eax
  __int64 v695; // rdx
  __int64 v696; // rcx
  __int64 v697; // r8
  __int64 v698; // r9
  int v699; // eax
  int v700; // edx
  const char *v701; // rcx
  const wchar_t *v702; // rbx
  __int64 v703; // rax
  const wchar_t *v704; // rsi
  __int64 v705; // rax
  __int64 v706; // rax
  __int64 v707; // rdx
  __int64 v708; // rcx
  __int64 v709; // r8
  __int64 v710; // r9
  struct RdpXInterfaceShellNotifyInformation *v711; // rbx
  __int64 v712; // rax
  unsigned int v713; // eax
  __int64 v714; // rdx
  __int64 v715; // rcx
  __int64 v716; // r8
  __int64 v717; // r9
  __int64 v718; // rdx
  __int64 v719; // r8
  __int64 v720; // r9
  __int64 v721; // rcx
  unsigned int v722; // eax
  __int64 v723; // rdx
  unsigned int v724; // r14d
  struct ITSWndPluginEx **v725; // rax
  __int64 v726; // rdx
  __int64 v727; // rcx
  __int64 v728; // r8
  __int64 v729; // r9
  int v730; // eax
  int v731; // edx
  const char *v732; // rcx
  __int64 v733; // rdi
  __int64 (__fastcall *v734)(__int64, _QWORD, _QWORD, void *); // rbx
  void *v735; // rax
  int v736; // eax
  __int64 v737; // rdx
  __int64 v738; // rcx
  __int64 v739; // r8
  __int64 v740; // r9
  unsigned __int16 v741; // di
  __int64 v742; // rax
  __int64 v743; // rax
  __int64 v744; // rdx
  __int64 v745; // rcx
  __int64 v746; // r8
  __int64 v747; // r9
  int v748; // eax
  int v749; // edx
  const char *v750; // rcx
  void *v751; // rax
  unsigned int v752; // eax
  __int64 v753; // rdx
  __int64 v754; // rcx
  __int64 v755; // r8
  __int64 v756; // r9
  __int64 v757; // rax
  __int64 v758; // rdx
  __int64 v759; // rcx
  __int64 v760; // r8
  __int64 v761; // r9
  __int64 v762; // rdx
  __int64 v763; // rcx
  __int64 v764; // r8
  __int64 v765; // r9
  __int64 v766; // rsi
  unsigned int v767; // eax
  unsigned int v768; // ebx
  RdpRemoteAppCore *v769; // r14
  unsigned int v770; // eax
  __int64 v771; // rdx
  int v772; // r15d
  __int64 v773; // rax
  const wchar_t *v774; // rbx
  __int64 v775; // rdi
  __int64 (__fastcall *v776)(__int64, _QWORD, _QWORD, void *); // rbx
  void *v777; // rax
  __int64 v778; // rdx
  __int64 v779; // rcx
  __int64 v780; // r8
  __int64 v781; // r9
  int v782; // eax
  int v783; // edx
  const char *v784; // rcx
  unsigned int v785; // ebx
  __int64 v786; // rdx
  __int64 v787; // r8
  __int64 v788; // rcx
  int v789; // eax
  unsigned int v790; // ebx
  __int64 v791; // rax
  const wchar_t *v792; // rbx
  __int64 v793; // rdi
  __int64 (__fastcall *v794)(__int64, _QWORD, _QWORD, char *, _DWORD, _DWORD, char *, int, RdpRemoteAppCore *, _DWORD, char *, _DWORD, void *); // rbx
  void *v795; // rax
  char *v796; // r9
  __int64 v797; // rdx
  __int64 v798; // rcx
  __int64 v799; // r8
  __int64 v800; // r9
  __int64 v801; // rdi
  __int64 (__fastcall *v802)(__int64, __int64); // rbx
  __int64 v803; // rax
  __int64 v804; // rdx
  __int64 v805; // rcx
  __int64 v806; // r8
  __int64 v807; // r9
  __int64 v808; // rax
  const wchar_t *v809; // rbx
  __int64 v810; // rax
  struct RdpXInterfaceShellNotifyInformation *v811; // rbx
  __int64 v812; // rax
  unsigned int v813; // eax
  __int64 v814; // rdx
  __int64 v815; // rcx
  __int64 v816; // r8
  __int64 v817; // r9
  __int64 v818; // rdx
  __int64 v819; // r8
  __int64 v820; // r9
  __int64 v821; // rcx
  unsigned int v822; // eax
  __int64 v823; // rdx
  unsigned int v824; // r15d
  struct ITSWndPluginEx **v825; // rax
  __int64 v826; // rdx
  __int64 v827; // rcx
  __int64 v828; // r8
  __int64 v829; // r9
  int v830; // eax
  int v831; // edx
  const char *v832; // rcx
  __int64 v833; // rdi
  int (__fastcall *v834)(__int64, _QWORD, _QWORD, void *); // rbx
  void *v835; // rax
  __int64 v836; // rdx
  __int64 v837; // rcx
  __int64 v838; // r8
  __int64 v839; // r9
  __int64 v840; // rdi
  __int64 (__fastcall *v841)(__int64, _QWORD, _QWORD, void *); // rbx
  void *v842; // rax
  __int64 v843; // rdx
  __int64 v844; // rcx
  __int64 v845; // r8
  __int64 v846; // r9
  __int64 v847; // rax
  int v848; // ebx
  int v849; // edi
  unsigned int v850; // eax
  __int64 v851; // rax
  __int64 v852; // rax
  __int64 v853; // rax
  __int64 v854; // rax
  __int64 v855; // rax
  __int64 v856; // rdx
  __int64 v857; // rcx
  __int64 v858; // r8
  __int64 v859; // r9
  int v860; // eax
  int v861; // edx
  const char *v862; // rcx
  void *v863; // rax
  unsigned int v864; // eax
  __int64 v865; // rdx
  __int64 v866; // rcx
  __int64 v867; // r8
  __int64 v868; // r9
  __int64 v869; // rax
  __int64 v870; // rdx
  __int64 v871; // rcx
  __int64 v872; // r8
  __int64 v873; // r9
  __int64 v874; // rdx
  __int64 v875; // rcx
  __int64 v876; // r8
  __int64 v877; // r9
  __int64 v878; // rsi
  unsigned int v879; // eax
  unsigned int v880; // edi
  RdpRemoteAppCore *v881; // r15
  unsigned int v882; // eax
  __int64 v883; // rdx
  __int64 v884; // rax
  const wchar_t *v885; // rbx
  __int64 v886; // rdi
  __int64 (__fastcall *v887)(__int64, _QWORD, _QWORD, void *); // rbx
  void *v888; // rax
  __int64 v889; // rdx
  __int64 v890; // rcx
  __int64 v891; // r8
  __int64 v892; // r9
  int v893; // eax
  int v894; // edx
  const char *v895; // rcx
  unsigned int v896; // edi
  __int64 v897; // r9
  __int64 v898; // r8
  __int64 v899; // rcx
  unsigned int v900; // edi
  __int64 v901; // rax
  const wchar_t *v902; // rbx
  __int64 v903; // rdi
  __int64 (__fastcall *v904)(__int64, _QWORD, _QWORD, __int64, _DWORD, _DWORD, char *, _DWORD, __int64, _DWORD, __int64, _DWORD, void *); // rbx
  void *v905; // rax
  __int64 v906; // r9
  __int64 v907; // rdx
  __int64 v908; // rcx
  __int64 v909; // r8
  __int64 v910; // r9
  __int64 v911; // rdi
  __int64 (__fastcall *v912)(__int64, __int64); // rbx
  __int64 v913; // rax
  __int64 v914; // rdx
  __int64 v915; // rcx
  __int64 v916; // r8
  __int64 v917; // r9
  __int64 v918; // rax
  const wchar_t *v919; // rbx
  struct RdpXInterfaceShellNotifyInformation *v920; // rbx
  __int64 v921; // rax
  unsigned int v922; // eax
  __int64 v923; // rdx
  __int64 v924; // rcx
  __int64 v925; // r8
  __int64 v926; // r9
  HKEY v927; // rdx
  unsigned int v928; // eax
  __int64 v929; // rsi
  unsigned int v930; // eax
  __int64 v931; // r15
  unsigned int v932; // eax
  int v933; // edx
  char *v934; // rcx
  unsigned int v935; // esi
  size_t cchToCopy; // [rsp+20h] [rbp-120h]
  size_t cchToCopya; // [rsp+20h] [rbp-120h]
  size_t cchToCopyb; // [rsp+20h] [rbp-120h]
  size_t cchToCopyc; // [rsp+20h] [rbp-120h]
  unsigned __int16 *v941; // [rsp+28h] [rbp-118h]
  unsigned __int16 *v942; // [rsp+28h] [rbp-118h]
  unsigned __int16 *v943; // [rsp+28h] [rbp-118h]
  unsigned __int16 *v944; // [rsp+28h] [rbp-118h]
  unsigned __int16 *v945; // [rsp+28h] [rbp-118h]
  unsigned __int16 *v946; // [rsp+28h] [rbp-118h]
  unsigned __int16 *v947; // [rsp+28h] [rbp-118h]
  unsigned __int16 *v948; // [rsp+28h] [rbp-118h]
  unsigned __int16 *v949; // [rsp+28h] [rbp-118h]
  int v950; // [rsp+28h] [rbp-118h]
  __int64 v951; // [rsp+30h] [rbp-110h]
  __int64 v952; // [rsp+30h] [rbp-110h]
  __int64 v953; // [rsp+30h] [rbp-110h]
  __int64 v954; // [rsp+38h] [rbp-108h]
  __int64 v955; // [rsp+38h] [rbp-108h]
  __int64 v956; // [rsp+40h] [rbp-100h]
  __int64 v957; // [rsp+40h] [rbp-100h]
  char v958[8]; // [rsp+C0h] [rbp-80h] BYREF
  char v959[8]; // [rsp+C8h] [rbp-78h] BYREF
  char v960[8]; // [rsp+D0h] [rbp-70h] BYREF
  int v961; // [rsp+D8h] [rbp-68h]
  char v962[8]; // [rsp+E0h] [rbp-60h] BYREF
  struct ITSWndPluginEx *v963; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v964; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v965; // [rsp+F8h] [rbp-48h] BYREF
  char v966[8]; // [rsp+100h] [rbp-40h] BYREF
  char v967[8]; // [rsp+108h] [rbp-38h] BYREF
  struct RdpXInterfaceRemoteAppWindow *v968; // [rsp+110h] [rbp-30h] BYREF
  char v969[8]; // [rsp+118h] [rbp-28h] BYREF
  _BYTE v970[16]; // [rsp+120h] [rbp-20h] BYREF
  RdpRemoteAppCore *v971; // [rsp+130h] [rbp-10h] BYREF
  int v972; // [rsp+138h] [rbp-8h]
  int v973; // [rsp+13Ch] [rbp-4h]
  char v974[8]; // [rsp+140h] [rbp+0h] BYREF
  char v975[8]; // [rsp+148h] [rbp+8h] BYREF
  __int64 v976; // [rsp+150h] [rbp+10h] BYREF
  int v977; // [rsp+158h] [rbp+18h]
  int v978; // [rsp+15Ch] [rbp+1Ch]
  char v979[8]; // [rsp+160h] [rbp+20h] BYREF
  char v980[8]; // [rsp+168h] [rbp+28h] BYREF
  unsigned int v981; // [rsp+170h] [rbp+30h]
  int v982; // [rsp+174h] [rbp+34h]
  int v983; // [rsp+178h] [rbp+38h]
  __int64 *v984; // [rsp+180h] [rbp+40h] BYREF
  struct RdpXInterfaceRemoteAppWindow *v985; // [rsp+188h] [rbp+48h] BYREF
  char v986[8]; // [rsp+190h] [rbp+50h] BYREF
  char v987[8]; // [rsp+198h] [rbp+58h] BYREF
  char v988[8]; // [rsp+1A0h] [rbp+60h] BYREF
  char v989[8]; // [rsp+1A8h] [rbp+68h] BYREF
  char v990[8]; // [rsp+1B0h] [rbp+70h] BYREF
  __int64 v991; // [rsp+1B8h] [rbp+78h] BYREF
  struct RdpXInterfaceRemoteAppWindow *v992; // [rsp+1C0h] [rbp+80h] BYREF
  char v993[8]; // [rsp+1C8h] [rbp+88h] BYREF
  char v994[8]; // [rsp+1D0h] [rbp+90h] BYREF
  char v995[8]; // [rsp+1D8h] [rbp+98h] BYREF
  __int64 v996; // [rsp+1E0h] [rbp+A0h] BYREF
  char v997[8]; // [rsp+1E8h] [rbp+A8h] BYREF
  char v998[8]; // [rsp+1F0h] [rbp+B0h] BYREF
  char v999[8]; // [rsp+1F8h] [rbp+B8h] BYREF
  char v1000[8]; // [rsp+200h] [rbp+C0h] BYREF
  char v1001[8]; // [rsp+208h] [rbp+C8h] BYREF
  char v1002[8]; // [rsp+210h] [rbp+D0h] BYREF
  __int64 v1003; // [rsp+218h] [rbp+D8h] BYREF
  struct RdpXInterfaceRemoteAppWindow *v1004; // [rsp+220h] [rbp+E0h] BYREF
  struct RdpXInterfaceRemoteAppWindow *v1005; // [rsp+228h] [rbp+E8h] BYREF
  char v1006[8]; // [rsp+230h] [rbp+F0h] BYREF
  char v1007[8]; // [rsp+238h] [rbp+F8h] BYREF
  int v1008; // [rsp+240h] [rbp+100h]
  int v1009; // [rsp+244h] [rbp+104h]
  int v1010; // [rsp+248h] [rbp+108h]
  int v1011; // [rsp+24Ch] [rbp+10Ch]
  unsigned int v1012; // [rsp+250h] [rbp+110h]
  int v1013; // [rsp+254h] [rbp+114h]
  int v1014; // [rsp+258h] [rbp+118h]
  char v1015[8]; // [rsp+260h] [rbp+120h] BYREF
  char v1016[8]; // [rsp+268h] [rbp+128h] BYREF
  char v1017[8]; // [rsp+270h] [rbp+130h] BYREF
  __int64 v1018; // [rsp+278h] [rbp+138h] BYREF
  __int64 v1019; // [rsp+280h] [rbp+140h] BYREF
  struct RdpXInterfaceRemoteAppWindow *v1020; // [rsp+288h] [rbp+148h] BYREF
  struct RdpXInterfaceRemoteAppWindow *v1021; // [rsp+290h] [rbp+150h] BYREF
  struct RdpXInterfaceRemoteAppWindow *v1022; // [rsp+298h] [rbp+158h] BYREF
  char v1023[8]; // [rsp+2A0h] [rbp+160h] BYREF
  struct RdpXInterfaceRemoteAppWindow *v1024; // [rsp+2A8h] [rbp+168h] BYREF
  char v1025[8]; // [rsp+2B0h] [rbp+170h] BYREF
  unsigned __int16 *v1026; // [rsp+2B8h] [rbp+178h] BYREF
  unsigned __int64 v1027; // [rsp+2C0h] [rbp+180h] BYREF
  _DWORD v1028[2]; // [rsp+2C8h] [rbp+188h] BYREF
  int v1029; // [rsp+2D0h] [rbp+190h]
  int v1030; // [rsp+2D4h] [rbp+194h]
  __int128 v1031; // [rsp+2D8h] [rbp+198h] BYREF
  _DWORD v1032[4]; // [rsp+2E8h] [rbp+1A8h] BYREF
  _DWORD v1033[4]; // [rsp+2F8h] [rbp+1B8h] BYREF
  __int128 v1034; // [rsp+308h] [rbp+1C8h] BYREF
  _OWORD v1035[2]; // [rsp+318h] [rbp+1D8h] BYREF
  __int64 v1036; // [rsp+338h] [rbp+1F8h]
  unsigned __int16 Destination[264]; // [rsp+340h] [rbp+200h] BYREF
  unsigned __int16 v1038[264]; // [rsp+550h] [rbp+410h] BYREF
  wchar_t pszDest[264]; // [rsp+760h] [rbp+620h] BYREF
  wchar_t v1040[264]; // [rsp+970h] [rbp+830h] BYREF

  v4 = a3;
  v971 = this;
  v5 = a2;
  v6 = this;
  if ( !*((_QWORD *)this + 13) )
  {
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147467261;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(this, a2, a3, a4);
    v8 = 62;
    v9 = "m_spTsClientPlatformInstance";
LABEL_6:
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v8,
      (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
      ActivityIdPrefix,
      (__int64)v9);
    return (unsigned int)-2147467261;
  }
  LOBYTE(a2) = 3;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_RailV2ConnectionInfoDisclosure>::__private_IsEnabledPreCheck(
    `wil::Feature<__WilFeatureTraits_Feature_EnableRailV2>::GetImpl'::`2'::impl,
    a2);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableRailV2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnableRailV2>::GetImpl'::`2'::impl) )
  {
    if ( !*((_QWORD *)v6 + 12) )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)-2147467261;
      }
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(v12, v11, v13, v14);
      v8 = 63;
      v9 = "m_remoteAppPlugin.get()";
      goto LABEL_6;
    }
  }
  else if ( !*((_QWORD *)v6 + 11) )
  {
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147467261;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(v12, v11, v13, v14);
    v8 = 64;
    v9 = "m_spRemoteAppPlugin";
    goto LABEL_6;
  }
  if ( v4 < 4 )
  {
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147467259;
    }
    v15 = RdpX_GetActivityIdPrefix(v12, v11, v13, v14);
    v16 = 65;
LABEL_24:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v15);
    return (unsigned int)-2147467259;
  }
  if ( v4 < *((unsigned __int16 *)v5 + 1) )
  {
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147467259;
    }
    v15 = RdpX_GetActivityIdPrefix(v12, v11, v13, v14);
    v16 = 66;
    goto LABEL_24;
  }
  RDPRailTraceLogging::TraceRailPDU(v5, v11);
  v20 = *(unsigned __int16 *)v5;
  if ( (unsigned int)v20 > 0x80 )
    goto LABEL_1160;
  if ( (_DWORD)v20 == 128 )
    goto LABEL_1134;
  if ( (unsigned int)v20 > 0x18 )
  {
    if ( (unsigned int)v20 <= 0x21 )
    {
      if ( (_DWORD)v20 == 33 )
      {
        RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v1023);
        if ( *((_WORD *)v5 + 1) >= 0xEu
          || (RdpRemoteAppCore::LogRemoteAppError(
                (char *)v6 + 16,
                L"Invalid size of TS_RAIL_ORDER_WINDOW_APPBAR_INFO_BODY PDU",
                2147549183LL,
                0,
                0),
              *((_WORD *)v5 + 1) >= 0xEu) )
        {
          LODWORD(cchToCopy) = *((_DWORD *)v5 + 2);
          RdpRemoteAppCore::LogRemoteAppEventF(
            (char *)v6 + 16,
            L"WindowAppBarInfoRailOrderReceived: WindowId=0x%x, FieldsValidFlags=0x%x, ShouldRegisterAppBar=%hhu, AppBarEdge=%hhu",
            0,
            *((unsigned int *)v5 + 1),
            cchToCopy,
            *((unsigned __int8 *)v5 + 12),
            *((unsigned __int8 *)v5 + 13));
          v552 = (struct RdpXInterfaceRemoteAppWindow **)CacCommon::Rect<int>::Rect<int>(v1023);
          RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow(
                              (RdpRemoteAppCore *)((char *)v6 - 48),
                              *((_DWORD *)v5 + 1),
                              v552);
          if ( RemoteAppWindow >= 0 )
          {
            if ( (*((_BYTE *)v5 + 8) & 0x40) != 0 )
            {
              if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                v559 = *((unsigned __int8 *)v5 + 12);
                v560 = RdpX_GetActivityIdPrefix(v554, v553, v555, v556);
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  163,
                  &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                  v560,
                  v559);
              }
              v561 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v1023);
              (*(void (__fastcall **)(__int64, bool))(*(_QWORD *)v561 + 344LL))(v561, *((_BYTE *)v5 + 12) == 1);
            }
            if ( (*((_BYTE *)v5 + 8) & 1) != 0 )
            {
              if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                v562 = *((unsigned __int8 *)v5 + 13);
                v563 = RdpX_GetActivityIdPrefix(v554, v553, v555, v556);
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  164,
                  &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                  v563,
                  v562);
              }
              v564 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v1023);
              LOBYTE(v565) = *((_BYTE *)v5 + 13);
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v564 + 352LL))(v564, v565);
            }
          }
          else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                 && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v557 = *((_DWORD *)v5 + 1);
            v558 = RdpX_GetActivityIdPrefix(v554, v553, v555, v556);
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              162,
              &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v558,
              v557);
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v551 = RdpX_GetActivityIdPrefix(v548, v547, v549, v550);
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              161,
              &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v551,
              -2147418113);
          }
          RemoteAppWindow = -2147418113;
        }
        v280 = v1023;
        goto LABEL_629;
      }
      RemoteAppWindow = 0;
      if ( (_DWORD)v20 != 27 )
      {
        if ( (_DWORD)v20 != 28 )
        {
          if ( (_DWORD)v20 != 29 )
          {
            if ( (_DWORD)v20 != 30 )
            {
              if ( (_DWORD)v20 != 31 )
              {
                if ( (_DWORD)v20 != 32 )
                  goto LABEL_1160;
                RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v998);
                RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v997);
                RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v1007);
                if ( *((_WORD *)v5 + 1) < 0x10u )
                {
                  RdpRemoteAppCore::LogRemoteAppError(
                    (char *)v6 + 16,
                    L"Invalid size of TS_RAIL_ORDER_WINDOW_CACHED_ICON PDU",
                    2147549183LL,
                    0,
                    0);
                  if ( *((_WORD *)v5 + 1) < 0x10u )
                  {
                    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      v279 = RdpX_GetActivityIdPrefix(v276, v275, v277, v278);
                      WPP_SF_Dd(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        156,
                        &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                        v279,
                        -2147418113);
                    }
                    RemoteAppWindow = -2147418113;
                    goto LABEL_434;
                  }
                }
                LODWORD(cchToCopy) = *((unsigned __int8 *)v5 + 8);
                RdpRemoteAppCore::LogRemoteAppEventF(
                  (char *)v6 + 16,
                  L"WindowCachedIconRailOrderReceived: WindowId=0x%x, NumIcons=%hhu, CacheEntry=0x%hx, CacheId=0x%hhx, IconFlags=0x%hhx",
                  0,
                  *((unsigned int *)v5 + 1),
                  cchToCopy,
                  *((unsigned __int16 *)v5 + 6),
                  *((unsigned __int8 *)v5 + 14),
                  *((unsigned __int8 *)v5 + 15));
                v281 = (struct RdpXInterfaceRemoteAppWindow **)CacCommon::Rect<int>::Rect<int>(v998);
                RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow(
                                    (RdpRemoteAppCore *)((char *)v6 - 48),
                                    *((_DWORD *)v5 + 1),
                                    v281);
                if ( RemoteAppWindow < 0 )
                {
                  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                    && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v286 = *((_DWORD *)v5 + 1);
                    v287 = RdpX_GetActivityIdPrefix(v283, v282, v284, v285);
                    WPP_SF_Dd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      157,
                      &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                      v287,
                      v286);
                  }
                  goto LABEL_434;
                }
                v288 = (struct ITSWndPluginEx **)CacCommon::Rect<int>::Rect<int>(v997);
                RemoteAppWindow = RdpRemoteAppCore::GetWndPlugin((RdpRemoteAppCore *)((char *)v6 - 48), v288);
                if ( RemoteAppWindow >= 0 )
                {
                  v296 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v997);
                  v297 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, void *))(*(_QWORD *)v296 + 56LL);
                  v298 = CacCommon::Rect<int>::Rect<int>(v1007);
                  RemoteAppWindow = v297(v296, *((unsigned __int8 *)v5 + 14), *((unsigned __int16 *)v5 + 6), v298);
                  if ( RemoteAppWindow >= 0 )
                  {
                    v303 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v998);
                    v304 = *((_BYTE *)v5 + 15) == 1;
                    v305 = *(__int64 (__fastcall **)(__int64, __int64, BOOL))(*(_QWORD *)v303 + 88LL);
                    v306 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v1007);
                    RemoteAppWindow = v305(v303, v306, v304);
                    if ( RemoteAppWindow >= 0
                      || WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                    {
                      goto LABEL_434;
                    }
                    v293 = RdpX_GetActivityIdPrefix(v308, v307, v309, v310);
                    v294 = 160;
                    v295 = "UpdateIcon failed";
                  }
                  else
                  {
                    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                    {
                      goto LABEL_434;
                    }
                    v293 = RdpX_GetActivityIdPrefix(v300, v299, v301, v302);
                    v294 = 159;
                    v295 = "CreateCachedIcon failed";
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
                  v293 = RdpX_GetActivityIdPrefix(v290, v289, v291, v292);
                  v294 = 158;
                  v295 = "GetWndPlugin failed";
                }
                LODWORD(v946) = RemoteAppWindow;
                WPP_SF_DsD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v294,
                  (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                  v293,
                  (__int64)v295,
                  v946);
LABEL_434:
                RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v1007);
                TCntPtr<ITSViewerRecorder>::SafeRelease(v997);
                v280 = v998;
LABEL_629:
                RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v280);
                return (unsigned int)RemoteAppWindow;
              }
              RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v995);
              RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v994);
              RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v993);
              LOWORD(v961) = 32;
              if ( *((_WORD *)v5 + 1) < 0x20u )
              {
                RdpRemoteAppCore::LogRemoteAppError(
                  (char *)v6 + 16,
                  L"Invalid size of TS_RAIL_ORDER_WINDOW_ICON_BODY PDU",
                  2147549183LL,
                  0,
                  0);
                if ( *((_WORD *)v5 + 1) < 0x20u )
                {
                  if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                    || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                  {
                    goto LABEL_463;
                  }
                  v315 = RdpX_GetActivityIdPrefix(v312, v311, v313, v314);
                  v316 = 150;
LABEL_462:
                  WPP_SF_Dd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    v316,
                    &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                    v315,
                    -2147418113);
LABEL_463:
                  RemoteAppWindow = -2147418113;
LABEL_464:
                  RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v993);
                  TCntPtr<ITSViewerRecorder>::SafeRelease(v994);
                  v280 = v995;
                  goto LABEL_629;
                }
              }
              v317 = (struct RdpXInterfaceRemoteAppWindow **)CacCommon::Rect<int>::Rect<int>(v995);
              RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow(
                                  (RdpRemoteAppCore *)((char *)v6 - 48),
                                  *((_DWORD *)v5 + 1),
                                  v317);
              if ( RemoteAppWindow < 0 )
              {
                if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                  && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v322 = *((_DWORD *)v5 + 1);
                  v323 = RdpX_GetActivityIdPrefix(v319, v318, v320, v321);
                  WPP_SF_Dd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    151,
                    &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                    v323,
                    v322);
                }
                goto LABEL_464;
              }
              v324 = (struct ITSWndPluginEx **)CacCommon::Rect<int>::Rect<int>(v994);
              WndPlugin = RdpRemoteAppCore::GetWndPlugin((RdpRemoteAppCore *)((char *)v6 - 48), v324);
              RemoteAppWindow = WndPlugin;
              if ( WndPlugin >= 0 )
              {
                if ( (*((_BYTE *)v5 + 15) & 2) != 0 )
                {
                  LOBYTE(WndPlugin) = *((_BYTE *)v5 + 20);
                  v333 = *((_WORD *)v5 + 11);
                  LOWORD(v961) = WndPlugin;
                }
                else
                {
                  v333 = 0;
                }
                v334 = *((_DWORD *)v5 + 6) + 32;
                v335 = (unsigned int)v333 + *((_DWORD *)v5 + 7);
                LODWORD(v976) = v333;
                v336 = v335 + v334;
                if ( *((unsigned __int16 *)v5 + 1) < v336 )
                  RdpRemoteAppCore::LogRemoteAppError(
                    (char *)v6 + 16,
                    L"Invalid size of TS_RAIL_ORDER_WINDOW_ICON_BODY PDU",
                    2147549183LL,
                    0,
                    0);
                if ( *((unsigned __int16 *)v5 + 1) < v336 )
                {
                  if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                    || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                  {
                    goto LABEL_463;
                  }
                  v315 = RdpX_GetActivityIdPrefix(v335, v326, v328, v329);
                  v316 = 153;
                  goto LABEL_462;
                }
                LODWORD(cchToCopy) = *((unsigned __int8 *)v5 + 8);
                RdpRemoteAppCore::LogRemoteAppEventF(
                  (char *)v971 + 16,
                  L"WindowIconRailOrderReceived: WindowId=0x%x, NumIcons=%hhu, CacheEntry=0x%hx, CacheId=0x%hhx, IconFlags"
                   "=0x%hhx, Width=%hu, Height=%hu, Bpp=%hhu, ColorTableBytes=%hu, BitsMaskBytes=%u, BitsColorBytes=%u",
                  0,
                  *((unsigned int *)v5 + 1),
                  cchToCopy,
                  *((unsigned __int16 *)v5 + 6),
                  *((unsigned __int8 *)v5 + 14),
                  *((unsigned __int8 *)v5 + 15),
                  *((unsigned __int16 *)v5 + 8),
                  *((unsigned __int16 *)v5 + 9),
                  *((unsigned __int8 *)v5 + 20),
                  *((unsigned __int16 *)v5 + 11),
                  *((_DWORD *)v5 + 6),
                  *((_DWORD *)v5 + 7));
                v337 = (__int64)v5 + v333 + 32;
                v338 = v337 + *((unsigned int *)v5 + 6);
                v339 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v994);
                v340 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64, _DWORD, _DWORD, char *, _DWORD, __int64, _DWORD, __int64, _DWORD, void *))(*(_QWORD *)v339 + 64LL);
                v341 = CacCommon::Rect<int>::Rect<int>(v993);
                v342 = *((unsigned __int16 *)v5 + 9);
                LOBYTE(v342) = v961;
                RemoteAppWindow = v340(
                                    v339,
                                    *((unsigned __int8 *)v5 + 14),
                                    *((unsigned __int16 *)v5 + 6),
                                    v342,
                                    *((unsigned __int16 *)v5 + 8),
                                    *((unsigned __int16 *)v5 + 9),
                                    (char *)v5 + 32,
                                    v976,
                                    v337,
                                    *((_DWORD *)v5 + 6),
                                    v338,
                                    *((_DWORD *)v5 + 7),
                                    v341);
                if ( RemoteAppWindow >= 0 )
                {
                  v347 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v995);
                  v348 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v347 + 88LL);
                  v349 = *((_BYTE *)v5 + 15) & 1;
                  v350 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v993);
                  RemoteAppWindow = v348(v347, v350, v349);
                  if ( RemoteAppWindow >= 0
                    || WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                    || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                  {
                    goto LABEL_464;
                  }
                  v330 = RdpX_GetActivityIdPrefix(v352, v351, v353, v354);
                  v331 = 155;
                  v332 = "UpdateIcon failed";
                }
                else
                {
                  if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                    || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                  {
                    goto LABEL_464;
                  }
                  v330 = RdpX_GetActivityIdPrefix(v344, v343, v345, v346);
                  v331 = 154;
                  v332 = "CreateCachedIcon failed";
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
                v330 = RdpX_GetActivityIdPrefix(v327, v326, v328, v329);
                v331 = 152;
                v332 = "GetWndPlugin failed";
              }
              LODWORD(v941) = RemoteAppWindow;
              WPP_SF_DsD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v331,
                (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                v330,
                (__int64)v332,
                v941);
              goto LABEL_464;
            }
            RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v1000);
            RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v999);
            if ( *((_WORD *)v5 + 1) < 8u )
            {
              RdpRemoteAppCore::LogRemoteAppError(
                (char *)v6 + 16,
                L"Invalid size of TS_RAIL_ORDER_WINDOW_DELETE_BODY PDU",
                2147549183LL,
                0,
                0);
              if ( *((_WORD *)v5 + 1) < 8u )
              {
                if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                  && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v359 = RdpX_GetActivityIdPrefix(v356, v355, v357, v358);
                  WPP_SF_Dd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    146,
                    &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                    v359,
                    -2147418113);
                }
                RemoteAppWindow = -2147418113;
                goto LABEL_503;
              }
            }
            RdpRemoteAppCore::LogRemoteAppEventF(
              (char *)v6 + 16,
              L"WindowDeleteRailOrderReceived: WindowId=0x%x",
              0,
              *((unsigned int *)v5 + 1));
            v360 = (struct RdpXInterfaceRemoteAppWindow **)CacCommon::Rect<int>::Rect<int>(v1000);
            RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow(
                                (RdpRemoteAppCore *)((char *)v6 - 48),
                                *((_DWORD *)v5 + 1),
                                v360);
            if ( RemoteAppWindow < 0 )
            {
              if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v365 = *((_DWORD *)v5 + 1);
                v366 = RdpX_GetActivityIdPrefix(v362, v361, v363, v364);
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  147,
                  &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                  v366,
                  v365);
              }
              goto LABEL_503;
            }
            v367 = (struct ITSWndPluginEx **)CacCommon::Rect<int>::Rect<int>(v999);
            RemoteAppWindow = RdpRemoteAppCore::GetWndPlugin((RdpRemoteAppCore *)((char *)v6 - 48), v367);
            if ( RemoteAppWindow >= 0 )
            {
              v375 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v1000);
              v376 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v999);
              v377 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v376 + 88LL))(v376);
              if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v375 + 72LL))(v375) == v377 )
              {
                v378 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v999);
                (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v378 + 96LL))(v378, 0);
              }
              v379 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *((char *)v971 + 128);
              v380 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v379 + 64LL);
              v381 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v1000);
              v382 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v381 + 72LL))(v381);
              v383 = v380(v379, v382);
              RemoteAppWindow = MapXResultToHR(v383);
              if ( RemoteAppWindow >= 0
                || WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_503;
              }
              v372 = RdpX_GetActivityIdPrefix(v385, v384, v386, v387);
              v373 = 149;
              v374 = "DeleteWindow failed";
            }
            else
            {
              if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_503;
              }
              v372 = RdpX_GetActivityIdPrefix(v369, v368, v370, v371);
              v373 = 148;
              v374 = "GetWndPlugin failed";
            }
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v373,
              (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v372,
              (__int64)v374,
              RemoteAppWindow);
LABEL_503:
            TCntPtr<ITSViewerRecorder>::SafeRelease(v999);
            v280 = v1000;
            goto LABEL_629;
          }
          RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v966);
          v971 = (RdpRemoteAppCore *)((char *)v6 + 16);
          if ( *((_WORD *)v5 + 1) < 0x58u )
            RdpRemoteAppCore::LogRemoteAppError(
              (char *)v6 + 16,
              L"Invalid size of TS_RAIL_ORDER_WINDOW_GEOMETRY_BODY PDU",
              2147549183LL,
              0,
              0);
          v391 = *((unsigned __int16 *)v5 + 1);
          if ( (unsigned int)v391 < 0x58 )
          {
            if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
              || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_530;
            }
            v392 = RdpX_GetActivityIdPrefix(v391, v388, v389, v390);
            v393 = 141;
LABEL_529:
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v393,
              &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v392,
              -2147418113);
LABEL_530:
            RemoteAppWindow = -2147418113;
LABEL_531:
            v280 = v966;
            goto LABEL_629;
          }
          v394 = 16 * *((unsigned __int16 *)v5 + 34) + 72;
          if ( (unsigned int)v391 < v394 )
            RdpRemoteAppCore::LogRemoteAppError(
              (char *)v6 + 16,
              L"Invalid size of TS_RAIL_ORDER_WINDOW_GEOMETRY_BODY PDU",
              2147549183LL,
              0,
              0);
          if ( *((unsigned __int16 *)v5 + 1) < v394 )
          {
            if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
              || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_530;
            }
            v392 = RdpX_GetActivityIdPrefix(v391, v388, v389, v390);
            v393 = 142;
            goto LABEL_529;
          }
          LODWORD(cchToCopy) = *((_DWORD *)v5 + 2);
          RdpRemoteAppCore::LogRemoteAppEventF(
            (char *)v6 + 16,
            L"WindowGeometryRailOrderReceived: WindowId=0x%x, FieldsValidFlags=0x%x, Style=0x%08x, StyleEx=0x%08x, ShowSta"
             "te=%hhu, OffsetX=%i, OffsetY=%i, Width=%i, Height=%i, WindowClientDeltaX=%i, WindowClientDeltaY=%i, ResizeM"
             "arginLeft=%i, ResizeMarginTop=%i, ResizeMarginRight=%i, ResizeMarginBottom=%i, NumVisibilityRects=%hu",
            0,
            *((unsigned int *)v5 + 1),
            cchToCopy,
            *((_DWORD *)v5 + 3),
            *((_DWORD *)v5 + 4),
            *((unsigned __int8 *)v5 + 20),
            *((_DWORD *)v5 + 7),
            *((_DWORD *)v5 + 8),
            *((_DWORD *)v5 + 9),
            *((_DWORD *)v5 + 10),
            *((_DWORD *)v5 + 11),
            *((_DWORD *)v5 + 12),
            *((_DWORD *)v5 + 13),
            *((_DWORD *)v5 + 15),
            *((_DWORD *)v5 + 14),
            *((_DWORD *)v5 + 16),
            *((unsigned __int16 *)v5 + 34));
          if ( *((_DWORD *)v5 + 1) == -1 )
          {
            if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
              && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              v399 = RdpX_GetActivityIdPrefix(v396, v395, v397, v398);
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 143, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v399);
            }
            goto LABEL_531;
          }
          v400 = (struct RdpXInterfaceRemoteAppWindow **)CacCommon::Rect<int>::Rect<int>(v966);
          RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow(
                              (RdpRemoteAppCore *)((char *)v6 - 48),
                              *((_DWORD *)v5 + 1),
                              v400);
          if ( RemoteAppWindow < 0 )
          {
            if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
              && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v405 = *((_DWORD *)v5 + 1);
              v406 = RdpX_GetActivityIdPrefix(v402, v401, v403, v404);
              WPP_SF_Dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                144,
                &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                v406,
                v405);
            }
            goto LABEL_531;
          }
          if ( (*((_BYTE *)v5 + 8) & 8) != 0 )
          {
            v407 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v966);
            (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v407 + 80LL))(
              v407,
              *((unsigned int *)v5 + 3),
              *((unsigned int *)v5 + 4));
          }
          if ( *((char *)v5 + 8) < 0 )
          {
            v408 = *((_DWORD *)v5 + 13);
            if ( v408 >= 0 )
            {
              v409 = *((_DWORD *)v5 + 14);
              if ( v409 >= 0 )
              {
                v410 = *((_DWORD *)v5 + 15);
                if ( v410 >= 0 )
                {
                  v411 = *((_DWORD *)v5 + 16);
                  if ( v411 >= 0 )
                  {
                    v412 = (__int64 *)RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v966);
                    v976 = __PAIR64__(v409, v408);
                    v977 = v410;
                    v413 = *v412;
                    v978 = v411;
                    (*(void (__fastcall **)(__int64 *, __int64 *, _QWORD))(v413 + 336))(v412, &v976, 0);
                  }
                }
              }
            }
          }
          if ( (*((_DWORD *)v5 + 2) & 0x8000) != 0 )
          {
            v414 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v966);
            (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v414 + 256LL))(
              v414,
              *((unsigned int *)v5 + 11),
              *((unsigned int *)v5 + 12));
            if ( (*((_DWORD *)v5 + 2) & 0x800) != 0 )
            {
              v415 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v966);
              (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v415 + 224LL))(
                v415,
                (unsigned int)(*((_DWORD *)v5 + 7) + *((_DWORD *)v5 + 11)),
                (unsigned int)(*((_DWORD *)v5 + 8) + *((_DWORD *)v5 + 12)));
            }
          }
          if ( (*((_DWORD *)v5 + 2) & 0x800) != 0 )
          {
            if ( (*((_DWORD *)v5 + 2) & 0x400) != 0 )
            {
              v1033[0] = *((_DWORD *)v5 + 7);
              v1033[1] = *((_DWORD *)v5 + 8);
              v1033[2] = *((_DWORD *)v5 + 9);
              v1033[3] = *((_DWORD *)v5 + 10);
              v416 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v966);
              (*(void (__fastcall **)(__int64, _DWORD *, _QWORD))(*(_QWORD *)v416 + 248LL))(v416, v1033, 0);
              v417 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v966);
              (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v417 + 160LL))(
                v417,
                *((int *)v5 + 7),
                *((int *)v5 + 8));
              goto LABEL_566;
            }
            v418 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v966);
            (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v418 + 232LL))(
              v418,
              *((unsigned int *)v5 + 7),
              *((unsigned int *)v5 + 8),
              0);
            v419 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v966);
            (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v419 + 160LL))(
              v419,
              *((int *)v5 + 7),
              *((int *)v5 + 8));
          }
          if ( (*((_DWORD *)v5 + 2) & 0x400) != 0 )
          {
            v420 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v966);
            (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v420 + 240LL))(
              v420,
              *((unsigned int *)v5 + 9),
              *((unsigned int *)v5 + 10),
              0);
          }
LABEL_566:
          if ( (*((_DWORD *)v5 + 2) & 0x100) != 0 )
          {
            v423 = (char *)operator new(saturated_mul(*((unsigned __int16 *)v5 + 34), 0x10u));
            if ( !v423 )
            {
              if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v426 = RdpX_GetActivityIdPrefix(v422, v421, v424, v425);
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  145,
                  &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                  v426,
                  -2147024882);
              }
              RemoteAppWindow = -2147024882;
              goto LABEL_531;
            }
            v427 = 0;
            if ( *((_WORD *)v5 + 34) )
            {
              v428 = v971;
              do
              {
                v429 = 16LL * v427;
                *(_DWORD *)&v423[v429] = *(_DWORD *)((char *)v5 + v429 + 72);
                *(_DWORD *)&v423[v429 + 4] = *(_DWORD *)((char *)v5 + v429 + 76);
                *(_DWORD *)&v423[v429 + 8] = *((_DWORD *)v5 + 4 * v427 + 20) - *(_DWORD *)((char *)v5 + v429 + 72);
                *(_DWORD *)&v423[v429 + 12] = *(_DWORD *)((char *)v5 + v429 + 84) - *(_DWORD *)((char *)v5 + v429 + 76);
                LODWORD(v956) = *(_DWORD *)((char *)v5 + v429 + 84);
                LODWORD(v954) = *((_DWORD *)v5 + 4 * v427 + 20);
                LODWORD(v952) = *(_DWORD *)((char *)v5 + v429 + 76);
                LODWORD(v947) = *(_DWORD *)((char *)v5 + v429 + 72);
                LODWORD(cchToCopya) = *((_DWORD *)v5 + 1);
                RdpRemoteAppCore::LogRemoteAppEventF(
                  v428,
                  L"WindowGeometryRailOrderReceived_VisibilityRect[%i]: WindowId=0x%x, Left=%i, Top=%i, Right=%i, Bottom=%i",
                  0,
                  (unsigned int)v427++,
                  cchToCopya,
                  v947,
                  v952,
                  v954,
                  v956);
              }
              while ( v427 < *((unsigned __int16 *)v5 + 34) );
            }
            v430 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v966);
            (*(void (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v430 + 176LL))(
              v430,
              *((unsigned __int16 *)v5 + 34),
              v423);
            v431 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v966);
            (*(void (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v431 + 168LL))(
              v431,
              *((unsigned __int16 *)v5 + 34),
              v423);
            operator delete(v423);
          }
          if ( (*((_BYTE *)v5 + 8) & 0x10) != 0 )
          {
            v432 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v966);
            (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v432 + 128LL))(v432, *((unsigned __int8 *)v5 + 20));
          }
          RemoteAppWindow = 0;
          goto LABEL_531;
        }
        RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v979);
        if ( *((_WORD *)v5 + 1) < 0x1Eu )
          RdpRemoteAppCore::LogRemoteAppError(
            (char *)v6 + 16,
            L"Invalid size of TS_RAIL_ORDER_WINDOW_CHANGE_BODY PDU",
            2147549183LL,
            0,
            0);
        v436 = *((unsigned __int16 *)v5 + 1);
        if ( (unsigned int)v436 >= 0x1E )
        {
          v439 = *((unsigned __int16 *)v5 + 13) + 28;
          if ( (unsigned int)v436 < v439 )
            RdpRemoteAppCore::LogRemoteAppError(
              (char *)v6 + 16,
              L"Invalid size of TS_RAIL_ORDER_WINDOW_CHANGE_BODY PDU",
              2147549183LL,
              0,
              0);
          if ( *((unsigned __int16 *)v5 + 1) >= v439 )
          {
            if ( *((_DWORD *)v5 + 1) == -1 )
            {
              if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                v440 = RdpX_GetActivityIdPrefix(v436, v433, v434, v435);
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  139,
                  &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                  v440);
              }
            }
            else
            {
              v441 = (struct RdpXInterfaceRemoteAppWindow **)CacCommon::Rect<int>::Rect<int>(v979);
              RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow(
                                  (RdpRemoteAppCore *)((char *)v6 - 48),
                                  *((_DWORD *)v5 + 1),
                                  v441);
              if ( RemoteAppWindow >= 0 )
              {
                if ( (*((_BYTE *)v5 + 8) & 2) != 0 )
                {
                  v448 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v979);
                  (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v448 + 120LL))(v448, *((unsigned int *)v5 + 3));
                }
                if ( (*((_BYTE *)v5 + 8) & 8) != 0 )
                {
                  v449 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v979);
                  (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v449 + 80LL))(
                    v449,
                    *((unsigned int *)v5 + 4),
                    *((unsigned int *)v5 + 5));
                }
                if ( (*((_DWORD *)v5 + 2) & 0x80000) != 0 )
                {
                  v450 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v979);
                  (*(void (__fastcall **)(__int64, bool))(*(_QWORD *)v450 + 312LL))(v450, *((_BYTE *)v5 + 25) == 1);
                }
                memset_0(Destination, 0, 0x20Au);
                if ( (*((_BYTE *)v5 + 8) & 4) != 0 && *((_WORD *)v5 + 13) )
                {
                  memcpy_s(Destination, 0x208u, (char *)v5 + 28, *((unsigned __int16 *)v5 + 13));
                  v451 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v979);
                  (*(void (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v451 + 104LL))(v451, Destination);
                }
                CUT::ObfuscateFilePathW(Destination);
                LODWORD(cchToCopy) = *((_DWORD *)v5 + 2);
                RdpRemoteAppCore::LogRemoteAppEventF(
                  (char *)v6 + 16,
                  L"WindowChangeRailOrderReceived: WindowsId=0x%x, FieldsValidFlags=0x%x, WindowOwnerId=0x%x, Style=0x%08x"
                   ", StyleEx=0x%08x, ShowState=%hhu, EnforceServerZOrder=%hhu, TitleBytes=%hu, Title=%s",
                  0,
                  *((unsigned int *)v5 + 1),
                  cchToCopy,
                  *((_DWORD *)v5 + 3),
                  *((_DWORD *)v5 + 4),
                  *((_DWORD *)v5 + 5),
                  *((unsigned __int8 *)v5 + 24),
                  *((unsigned __int8 *)v5 + 25),
                  *((unsigned __int16 *)v5 + 13),
                  Destination);
                if ( (*((_BYTE *)v5 + 8) & 0x10) != 0 )
                {
                  v452 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v979);
                  (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v452 + 128LL))(
                    v452,
                    *((unsigned __int8 *)v5 + 24));
                }
                RemoteAppWindow = 0;
              }
              else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                     && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
                     && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v446 = *((_DWORD *)v5 + 1);
                v447 = RdpX_GetActivityIdPrefix(v443, v442, v444, v445);
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  140,
                  &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                  v447,
                  v446);
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
            v280 = v979;
            goto LABEL_629;
          }
          v437 = RdpX_GetActivityIdPrefix(v436, v433, v434, v435);
          v438 = 138;
        }
        else
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_588;
          }
          v437 = RdpX_GetActivityIdPrefix(v436, v433, v434, v435);
          v438 = 137;
        }
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v438,
          &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v437,
          -2147418113);
        goto LABEL_588;
      }
      RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v958);
      RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v974);
      v1031 = 0;
      if ( *((_WORD *)v5 + 1) < 0x58u )
        RdpRemoteAppCore::LogRemoteAppError(
          (char *)v6 + 16,
          L"Invalid size of TS_RAIL_ORDER_WINDOW_CREATE_BODY PDU",
          2147549183LL,
          0,
          0);
      v456 = *((unsigned __int16 *)v5 + 1);
      if ( (unsigned int)v456 < 0x58 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_627;
        }
        v457 = RdpX_GetActivityIdPrefix(v456, v453, v454, v455);
        v458 = 127;
LABEL_626:
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v458,
          &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v457,
          -2147418113);
LABEL_627:
        RemoteAppWindow = -2147418113;
LABEL_628:
        TCntPtr<ITSViewerRecorder>::SafeRelease(v974);
        v280 = v958;
        goto LABEL_629;
      }
      if ( *((_WORD *)v5 + 34) )
        v459 = *((unsigned __int16 *)v5 + 34) - 1;
      else
        v459 = 0;
      v460 = 16 * v459 + 84;
      v461 = v460 + *((unsigned __int16 *)v5 + 13) + 4;
      LODWORD(v976) = v460;
      if ( (unsigned int)v456 < v461 )
        RdpRemoteAppCore::LogRemoteAppError(
          (char *)v6 + 16,
          L"Invalid size of TS_RAIL_ORDER_WINDOW_CREATE_BODY PDU",
          2147549183LL,
          0,
          0);
      if ( *((unsigned __int16 *)v5 + 1) < v461 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_627;
        }
        v457 = RdpX_GetActivityIdPrefix(v456, v453, v454, v455);
        v458 = 128;
        goto LABEL_626;
      }
      if ( *((_DWORD *)v5 + 1) == -1 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v462 = RdpX_GetActivityIdPrefix(v456, v453, v454, v455);
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 129, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v462);
        }
        goto LABEL_628;
      }
      v463 = (struct ITSWndPluginEx **)CacCommon::Rect<int>::Rect<int>(v974);
      v464 = 0;
      RemoteAppWindow = RdpRemoteAppCore::GetWndPlugin((RdpRemoteAppCore *)((char *)v6 - 48), v463);
      if ( RemoteAppWindow < 0 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v469 = RdpX_GetActivityIdPrefix(v466, v465, v467, v468);
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            130,
            (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
            v469,
            (__int64)"GetWndPlugin failed",
            RemoteAppWindow);
        }
        goto LABEL_628;
      }
      v470 = (struct RdpXInterfaceRemoteAppWindow **)CacCommon::Rect<int>::Rect<int>(v958);
      RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow(
                          (RdpRemoteAppCore *)((char *)v6 - 48),
                          *((_DWORD *)v5 + 1),
                          v470);
      if ( RemoteAppWindow < 0 )
      {
        RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v1002);
        RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v990);
        RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v1001);
        v1034 = 0;
        v471 = CacCommon::Rect<int>::Rect<int>(v1002);
        WindowCallbacks = RdpRemoteAppCore::CreateWindowCallbacks((char *)v6 + 16, *((unsigned int *)v5 + 1), v471);
        RemoteAppWindow = MapXResultToHR(WindowCallbacks);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_657;
          }
          v477 = RdpX_GetActivityIdPrefix(v474, v473, v475, v476);
          v478 = 131;
          v479 = "CreateWindowCallbacks failed";
LABEL_656:
          LODWORD(v941) = RemoteAppWindow;
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v478,
            (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
            v477,
            (__int64)v479,
            v941);
LABEL_657:
          ComPlainSmartPtr<IRdpBaseCoreApi>::~ComPlainSmartPtr<IRdpBaseCoreApi>(v1001);
          RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v990);
          RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v1002);
          goto LABEL_628;
        }
        v480 = CacCommon::Rect<int>::Rect<int>(v990);
        Object = RdpX_CreateObject(0, 0, 67, 105, v480);
        RemoteAppWindow = MapXResultToHR(Object);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_657;
          }
          v477 = RdpX_GetActivityIdPrefix(v483, v482, v484, v485);
          v478 = 132;
          v479 = "RdpXBaseCoreApiAdaptor RdpX_CreateObject failed";
          goto LABEL_656;
        }
        v486 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *((char *)v6 + 104);
        v487 = *(__int64 (__fastcall **)(__int64, void *))(*(_QWORD *)v486 + 216LL);
        v488 = CacCommon::Rect<int>::Rect<int>(v1001);
        RemoteAppWindow = v487(v486, v488);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_657;
          }
          v477 = RdpX_GetActivityIdPrefix(v490, v489, v491, v492);
          v478 = 133;
          v479 = "Failed to get base core Api";
          goto LABEL_656;
        }
        v493 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v990);
        v494 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v493 + 24LL);
        v495 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v1001);
        v496 = v494(v493, v495);
        RemoteAppWindow = MapXResultToHR(v496);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_657;
          }
          v477 = RdpX_GetActivityIdPrefix(v498, v497, v499, v500);
          v478 = 134;
          v479 = "SetCoreApi failed";
          goto LABEL_656;
        }
        v501 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *((char *)v971 + 128);
        v502 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64, __int128 *, void *))(*(_QWORD *)v501 + 48LL);
        v503 = CacCommon::Rect<int>::Rect<int>(v958);
        v504 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v1002);
        v505 = *((_DWORD *)v5 + 1);
        v506 = v504;
        v507 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v990);
        v508 = v502(v501, v507, v505, v506, &v1034, v503);
        v464 = 0;
        RemoteAppWindow = MapXResultToHR(v508);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_657;
          }
          v477 = RdpX_GetActivityIdPrefix(v510, v509, v511, v512);
          v478 = 135;
          v479 = "CreateWindowRepresentation failed";
          goto LABEL_656;
        }
        v513 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v958);
        v514 = *(__int64 (__fastcall **)(__int64, bool))(*(_QWORD *)v513 + 320LL);
        v515 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v974);
        v516 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v515 + 136LL))(v515);
        v517 = v514(v513, v516 != 0);
        RemoteAppWindow = MapXResultToHR(v517);
        v518 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v958);
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v518 + 120LL))(v518, *((unsigned int *)v5 + 3));
        ComPlainSmartPtr<IRdpBaseCoreApi>::~ComPlainSmartPtr<IRdpBaseCoreApi>(v1001);
        RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v990);
        RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v1002);
        v6 = v971;
        v460 = v976;
      }
      v519 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v974);
      if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v519 + 136LL))(v519) )
      {
        v520 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v958);
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v520 + 200LL))(v520, 2);
      }
      v521 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v958);
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v521 + 80LL))(
        v521,
        *((unsigned int *)v5 + 4),
        *((unsigned int *)v5 + 5));
      v522 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v958);
      (*(void (__fastcall **)(__int64, bool))(*(_QWORD *)v522 + 312LL))(v522, *((_BYTE *)v5 + 25) == 1);
      memset_0(v1038, 0, 0x20Au);
      if ( *((_WORD *)v5 + 13) > 2u )
      {
        memcpy_s(v1038, 0x208u, (char *)v5 + v460 + 4, *((unsigned __int16 *)v5 + 13));
        v523 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v958);
        (*(void (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v523 + 104LL))(v523, v1038);
      }
      CUT::ObfuscateFilePathW(v1038);
      LODWORD(v941) = *((_DWORD *)v5 + 3);
      LODWORD(cchToCopy) = *((_DWORD *)v5 + 2);
      RdpRemoteAppCore::LogRemoteAppEventF(
        (char *)v6 + 16,
        L"WindowCreateRailOrderReceived: WindowId=0x%x, FieldsValidFlags=0x%x, WindowOwnerId=0x%x, Style=0x%08x, StyleEx=0"
         "x%08x, ShowState=%hhu, EnforceServerZOrder=%hhu, TitleBytes=%hu, Title=%s, OffsetX=%i, OffsetY=%i, Width=%i, He"
         "ight=%i, WindowClientDeltaX=%i, WindowClientDeltaY=%i, ResizeMarginLeft=%i, ResizeMarginTop=%i, ResizeMarginRig"
         "ht=%i, ResizeMarginBottom=%i, NumVisibilityRects=%hu",
        0,
        *((unsigned int *)v5 + 1),
        cchToCopy,
        v941,
        *((_DWORD *)v5 + 4),
        *((_DWORD *)v5 + 5),
        *((unsigned __int8 *)v5 + 24),
        *((unsigned __int8 *)v5 + 25),
        *((unsigned __int16 *)v5 + 13),
        v1038,
        *((_DWORD *)v5 + 7),
        *((_DWORD *)v5 + 8),
        *((_DWORD *)v5 + 9),
        *((_DWORD *)v5 + 10),
        *((_DWORD *)v5 + 11),
        *((_DWORD *)v5 + 12),
        *((_DWORD *)v5 + 13),
        *((_DWORD *)v5 + 15),
        *((_DWORD *)v5 + 14),
        *((_DWORD *)v5 + 16),
        *((unsigned __int16 *)v5 + 34));
      LODWORD(v976) = *((_DWORD *)v5 + 13);
      if ( (int)v976 >= 0 )
      {
        v524 = *((_DWORD *)v5 + 14);
        if ( v524 >= 0 )
        {
          v525 = *((_DWORD *)v5 + 15);
          if ( v525 >= 0 )
          {
            v526 = *((_DWORD *)v5 + 16);
            if ( v526 >= 0 )
            {
              v527 = (__int64 *)RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v958);
              v971 = (RdpRemoteAppCore *)__PAIR64__(v524, v976);
              v972 = v525;
              v528 = *v527;
              v973 = v526;
              (*(void (__fastcall **)(__int64 *, RdpRemoteAppCore **, _QWORD))(v528 + 336))(v527, &v971, 0);
            }
          }
          v464 = 0;
        }
      }
      v529 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v958);
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v529 + 224LL))(
        v529,
        (unsigned int)(*((_DWORD *)v5 + 7) + *((_DWORD *)v5 + 11)),
        (unsigned int)(*((_DWORD *)v5 + 8) + *((_DWORD *)v5 + 12)));
      v530 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v958);
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v530 + 256LL))(
        v530,
        *((unsigned int *)v5 + 11),
        *((unsigned int *)v5 + 12));
      v1031 = *(_OWORD *)((char *)v5 + 28);
      v531 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v958);
      (*(void (__fastcall **)(__int64, __int128 *, _QWORD))(*(_QWORD *)v531 + 248LL))(v531, &v1031, 0);
      v534 = (char *)operator new(saturated_mul(*((unsigned __int16 *)v5 + 34), 0x10u));
      if ( v534 )
      {
        if ( *((_WORD *)v5 + 34) )
        {
          do
          {
            v538 = 16LL * v464;
            *(_DWORD *)&v534[v538] = *(_DWORD *)((char *)v5 + v538 + 72);
            *(_DWORD *)&v534[v538 + 4] = *(_DWORD *)((char *)v5 + v538 + 76);
            *(_DWORD *)&v534[v538 + 8] = *((_DWORD *)v5 + 4 * v464 + 20) - *(_DWORD *)((char *)v5 + v538 + 72);
            *(_DWORD *)&v534[v538 + 12] = *(_DWORD *)((char *)v5 + v538 + 84) - *(_DWORD *)((char *)v5 + v538 + 76);
            LODWORD(v957) = *(_DWORD *)((char *)v5 + v538 + 84);
            LODWORD(v955) = *((_DWORD *)v5 + 4 * v464 + 20);
            LODWORD(v953) = *(_DWORD *)((char *)v5 + v538 + 76);
            LODWORD(v948) = *(_DWORD *)((char *)v5 + v538 + 72);
            LODWORD(cchToCopyb) = *((_DWORD *)v5 + 1);
            RdpRemoteAppCore::LogRemoteAppEventF(
              (char *)v6 + 16,
              L"WindowCreateRailOrderReceived_VisibilityRect[%i]: WindowId=0x%x, Left=%i, Top=%i, Right=%i, Bottom=%i",
              0,
              (unsigned int)v464++,
              cchToCopyb,
              v948,
              v953,
              v955,
              v957);
          }
          while ( v464 < *((unsigned __int16 *)v5 + 34) );
        }
        v539 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v958);
        (*(void (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v539 + 176LL))(
          v539,
          *((unsigned __int16 *)v5 + 34),
          v534);
        v540 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v958);
        (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v540 + 160LL))(
          v540,
          *((int *)v5 + 7),
          *((int *)v5 + 8));
        v541 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v958);
        (*(void (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v541 + 168LL))(
          v541,
          *((unsigned __int16 *)v5 + 34),
          v534);
        operator delete(v534);
        if ( RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *((char *)v6 + 136) )
        {
          v542 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *((char *)v6 + 136);
          v543 = *(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v542 + 40LL);
          v544 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v958);
          v545 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v544 + 72LL))(v544);
          v543(v542, v545);
        }
        v546 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v958);
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v546 + 128LL))(v546, *((unsigned __int8 *)v5 + 24));
      }
      else
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v537 = RdpX_GetActivityIdPrefix(v533, v532, v535, v536);
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            136,
            &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
            v537,
            -2147024882);
        }
        RemoteAppWindow = -2147024882;
      }
      goto LABEL_628;
    }
    if ( (_DWORD)v20 != 34 )
    {
      if ( (_DWORD)v20 != 35 )
      {
        if ( (_DWORD)v20 != 36 )
        {
          if ( (_DWORD)v20 != 37 )
          {
            if ( (_DWORD)v20 != 38 )
            {
              if ( (_DWORD)v20 != 39 )
                goto LABEL_1160;
              RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v986);
              if ( *((_WORD *)v5 + 1) != 8 )
              {
                RdpRemoteAppCore::LogRemoteAppError(
                  (char *)v6 + 16,
                  L"Invalid size of TS_RAIL_ORDER_SYNC_STATE_BODY PDU",
                  2147549183LL,
                  0,
                  0);
                if ( *((_WORD *)v5 + 1) != 8 )
                {
                  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                    && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v570 = RdpX_GetActivityIdPrefix(v567, v566, v568, v569);
                    WPP_SF_Dd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      120,
                      &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                      v570,
                      -2147418113);
                  }
                  RemoteAppWindow = -2147418113;
LABEL_738:
                  v571 = v986;
LABEL_739:
                  TCntPtr<ITSViewerRecorder>::SafeRelease(v571);
                  return (unsigned int)RemoteAppWindow;
                }
              }
              RdpRemoteAppCore::LogRemoteAppEventF(
                (char *)v6 + 16,
                L"SyncStateRailOrderReceived: SyncFlags=0x%x",
                0,
                *((unsigned int *)v5 + 1));
              v572 = (struct ITSWndPluginEx **)CacCommon::Rect<int>::Rect<int>(v986);
              RemoteAppWindow = RdpRemoteAppCore::GetWndPlugin((RdpRemoteAppCore *)((char *)v6 - 48), v572);
              if ( RemoteAppWindow < 0 )
              {
                if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                  && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v577 = RdpX_GetActivityIdPrefix(v574, v573, v575, v576);
                  WPP_SF_DsD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    121,
                    (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                    v577,
                    (__int64)"GetWndPlugin failed",
                    RemoteAppWindow);
                }
                goto LABEL_738;
              }
              if ( (*((_BYTE *)v5 + 4) & 1) != 0 )
              {
                if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                  && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
                {
                  v578 = RdpX_GetActivityIdPrefix(v574, v573, v575, v576);
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    122,
                    &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                    v578);
                }
                v579 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v986);
                v580 = 0;
              }
              else
              {
                if ( (*((_BYTE *)v5 + 4) & 2) == 0 )
                  goto LABEL_774;
                v581 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                  && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
                {
                  v582 = RdpX_GetActivityIdPrefix(v574, v573, v575, v576);
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    123,
                    &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                    v582);
                  v581 = WPP_GLOBAL_Control;
                }
                if ( (*((_BYTE *)v5 + 4) & 8) != 0 )
                {
                  if ( v581 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v581[7] & 1) != 0 && *((_BYTE *)v581 + 25) >= 3u )
                  {
                    v583 = RdpX_GetActivityIdPrefix(v574, v573, v575, v576);
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      124,
                      &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                      v583);
                  }
                  v584 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v986);
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v584 + 120LL))(v584);
                  if ( (unsigned int)RdpRemoteAppCore::IsRemoteAppV2Enabled((char *)v6 + 16) )
                  {
                    v585 = (RdpRemoteAppCore *)((char *)v6 + 128);
                    v971 = (RdpRemoteAppCore *)((char *)v6 + 128);
                    v586 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *((char *)v6 + 128);
                    LODWORD(v976) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v586 + 120LL))(v586);
                    v587 = 0;
                    if ( (_DWORD)v976 )
                    {
                      while ( 1 )
                      {
                        RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v1025);
                        v588 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v585);
                        v589 = *(__int64 (__fastcall **)(__int64, _QWORD, void *))(*(_QWORD *)v588 + 128LL);
                        v590 = CacCommon::Rect<int>::Rect<int>(v1025);
                        v593 = v589(v588, v587, v590);
                        if ( v593 )
                          break;
                        v596 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v1025);
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v596 + 384LL))(v596);
                        RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v1025);
                        v585 = v971;
                        if ( ++v587 >= (unsigned int)v976 )
                          goto LABEL_772;
                      }
                      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                        && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                      {
                        v597 = RdpX_GetActivityIdPrefix(v592, v591, v594, v595);
                        WPP_SF_DLD(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          125,
                          &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                          v597,
                          v593,
                          v593);
                      }
                      RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v1025);
                      goto LABEL_738;
                    }
                  }
                }
                else
                {
                  v598 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v986);
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v598 + 144LL))(v598);
                }
LABEL_772:
                v579 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v986);
                v580 = 1;
              }
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v579 + 112LL))(v579, v580);
LABEL_774:
              if ( (*((_BYTE *)v5 + 4) & 4) != 0 )
              {
                if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                  && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
                {
                  v599 = RdpX_GetActivityIdPrefix(v574, v573, v575, v576);
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    126,
                    &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                    v599);
                }
                v600 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v986);
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v600 + 128LL))(v600);
              }
              goto LABEL_738;
            }
            RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v1015);
            if ( *((_WORD *)v5 + 1) >= 0x14u
              || (RdpRemoteAppCore::LogRemoteAppError(
                    (char *)v6 + 16,
                    L"Invalid size of TS_RAIL_ORDER_ZORDER_BODY PDU",
                    2147549183LL,
                    0,
                    0),
                  *((_WORD *)v5 + 1) >= 0x14u) )
            {
              if ( *((_DWORD *)v5 + 1) > 0x100u )
                RdpRemoteAppCore::LogRemoteAppError(
                  (char *)v6 + 16,
                  L"numWindows in TS_RAIL_ORDER_ZORDER_BODY PDU is unexpectedly big",
                  2147549183LL,
                  0,
                  0);
              v607 = *((_DWORD *)v5 + 1);
              if ( v607 <= 0x100 )
              {
                v608 = 4 * v607 + 16;
                if ( *((unsigned __int16 *)v5 + 1) < v608 )
                  RdpRemoteAppCore::LogRemoteAppError(
                    (char *)v6 + 16,
                    L"Invalid size of TS_RAIL_ORDER_ZORDER_BODY PDU",
                    2147549183LL,
                    0,
                    0);
                if ( *((unsigned __int16 *)v5 + 1) >= v608 )
                {
                  memset_0(v1040, 0, 0x208u);
                  v609 = v1040;
                  v610 = 260;
                  v1026 = v1040;
                  v1027 = 260;
                  v611 = *((_DWORD *)v5 + 1);
                  if ( v611 )
                  {
                    v612 = 0;
                    v613 = 0;
                    while ( 1 )
                    {
                      v614 = v611;
                      if ( v612 < 0 )
                        break;
                      v615 = L"0x%x,";
                      if ( v613 >= v611 - 1 )
                        v615 = L"0x%x";
                      LODWORD(v951) = *((_DWORD *)v5 + v613 + 4);
                      v612 = StringCchPrintfExW(v609, v610, &v1026, &v1027, 0, v615, v951);
                      if ( v612 < 0
                        && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                      {
                        v620 = RdpX_GetActivityIdPrefix(v617, v616, v618, v619);
                        LODWORD(v941) = v612;
                        WPP_SF_DsD(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          209,
                          (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                          v620,
                          (__int64)"StringCchPrintfEx failed",
                          v941);
                      }
                      v611 = *((_DWORD *)v5 + 1);
                      ++v613;
                      v614 = v611;
                      if ( v613 >= v611 )
                        break;
                      v609 = v1026;
                      v610 = v1027;
                    }
                  }
                  else
                  {
                    v614 = 0;
                  }
                  LODWORD(v941) = *((_DWORD *)v5 + 3);
                  LODWORD(cchToCopy) = *((_DWORD *)v5 + 2);
                  RdpRemoteAppCore::LogRemoteAppEventF(
                    (char *)v6 + 16,
                    L"ZOrderRailOrderReceived: NumWindows=%u, FieldsValidFlags=0x%x, ActiveWindowId=0x%x, WindowIds=[%s]",
                    0,
                    v614,
                    cchToCopy,
                    v941,
                    v1040);
                  v621 = (struct ITSWndPluginEx **)CacCommon::Rect<int>::Rect<int>(v1015);
                  RemoteAppWindow = RdpRemoteAppCore::GetWndPlugin((RdpRemoteAppCore *)((char *)v6 - 48), v621);
                  if ( RemoteAppWindow >= 0 )
                  {
                    v627 = (*((_DWORD *)v5 + 2) >> 4) & 2 | 1;
                    if ( (*((_BYTE *)v5 + 8) & 0x10) == 0 )
                      v627 = (*((_DWORD *)v5 + 2) >> 4) & 2;
                    if ( v627 )
                    {
                      v628 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v1015);
                      (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, __int64))(*(_QWORD *)v628 + 104LL))(
                        v628,
                        v627,
                        *((unsigned int *)v5 + 3),
                        *((unsigned int *)v5 + 1),
                        (__int64)v5 + 16);
                    }
                  }
                  else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                         && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v626 = RdpX_GetActivityIdPrefix(v623, v622, v624, v625);
                    LODWORD(v949) = RemoteAppWindow;
                    WPP_SF_DsD(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      210,
                      (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                      v626,
                      (__int64)"GetWndPlugin failed",
                      v949);
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
                  v571 = v1015;
                  goto LABEL_739;
                }
                v605 = RdpX_GetActivityIdPrefix(v602, v601, v603, v604);
                v606 = 208;
              }
              else
              {
                if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                  || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_787;
                }
                v605 = RdpX_GetActivityIdPrefix(v602, v601, v603, v604);
                v606 = 207;
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
              v605 = RdpX_GetActivityIdPrefix(v602, v601, v603, v604);
              v606 = 206;
            }
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v606,
              &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v605,
              -2147418113);
            goto LABEL_787;
          }
          RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v987);
          RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v1016);
          if ( *((_WORD *)v5 + 1) != 12 )
          {
            RdpRemoteAppCore::LogRemoteAppError(
              (char *)v6 + 16,
              L"Invalid size of TS_RAIL_ORDER_NOTIFYICON_DELETE PDU",
              2147549183LL,
              0,
              0);
            if ( *((_WORD *)v5 + 1) != 12 )
            {
              if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v633 = RdpX_GetActivityIdPrefix(v630, v629, v631, v632);
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  202,
                  &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                  v633,
                  -2147418113);
              }
              RemoteAppWindow = -2147418113;
              goto LABEL_832;
            }
          }
          LODWORD(cchToCopy) = *((_DWORD *)v5 + 2);
          RdpRemoteAppCore::LogRemoteAppEventF(
            (char *)v6 + 16,
            L"NotifyIconDeleteRailOrderReceived: WindowId=0x%x, NotifyIconId=0x%x",
            0,
            *((unsigned int *)v5 + 1),
            cchToCopy);
          v635 = (struct ITSWndPluginEx **)CacCommon::Rect<int>::Rect<int>(v1016);
          RemoteAppWindow = RdpRemoteAppCore::GetWndPlugin((RdpRemoteAppCore *)((char *)v6 - 48), v635);
          if ( RemoteAppWindow >= 0 )
          {
            v643 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v1016);
            v644 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, void *))(*(_QWORD *)v643 + 72LL);
            v645 = CacCommon::Rect<int>::Rect<int>(v987);
            RemoteAppWindow = v644(v643, *((unsigned int *)v5 + 1), *((unsigned int *)v5 + 2), v645);
            if ( RemoteAppWindow >= 0 )
            {
              v650 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v987);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v650 + 128LL))(v650);
              v651 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v987);
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v651 + 120LL))(v651, 2);
              v652 = (struct RdpXInterfaceShellNotifyInformation *)RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v987);
              v653 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v987);
              v654 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v653 + 72LL))(v653);
              RemoteAppWindow = RdpRemoteAppCore::OnShellNotifyInformation(v971, v654, v652);
              if ( RemoteAppWindow >= 0
                || WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_832;
              }
              v640 = RdpX_GetActivityIdPrefix(v656, v655, v657, v658);
              v641 = 205;
              v642 = "OnShellNotifyInformation failed";
            }
            else
            {
              if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_832;
              }
              v640 = RdpX_GetActivityIdPrefix(v647, v646, v648, v649);
              v641 = 204;
              v642 = "FindShellNotifyInfo failed";
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
            v640 = RdpX_GetActivityIdPrefix(v637, v636, v638, v639);
            v641 = 203;
            v642 = "GetWndPlugin failed";
          }
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v641,
            (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
            v640,
            (__int64)v642,
            RemoteAppWindow);
LABEL_832:
          TCntPtr<ITSViewerRecorder>::SafeRelease(v1016);
          v634 = v987;
LABEL_1025:
          RdpXSPtr<RdpXTapVcCallbackItem>::SafeRelease(v634);
          return (unsigned int)RemoteAppWindow;
        }
        RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v975);
        RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v980);
        if ( *((_WORD *)v5 + 1) < 0x14u )
          RdpRemoteAppCore::LogRemoteAppError(
            (char *)v6 + 16,
            L"Invalid size of TS_RAIL_ORDER_NOTIFYICON_TOAST_BODY",
            2147549183LL,
            0,
            0);
        v662 = *((unsigned __int16 *)v5 + 1);
        if ( (unsigned int)v662 < 0x14 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_857;
          }
          v663 = RdpX_GetActivityIdPrefix(v659, v662, v660, v661);
          v664 = 194;
LABEL_856:
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v664,
            &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
            v663,
            -2147418113);
LABEL_857:
          RemoteAppWindow = -2147418113;
LABEL_858:
          TCntPtr<ITSViewerRecorder>::SafeRelease(v980);
          v634 = v975;
          goto LABEL_1025;
        }
        v665 = *((unsigned __int16 *)v5 + 8);
        v666 = v665 + *((unsigned __int16 *)v5 + 9) + 20;
        if ( (unsigned int)v662 < v666 )
          RdpRemoteAppCore::LogRemoteAppError(
            (char *)v6 + 16,
            L"Invalid size of TS_RAIL_ORDER_NOTIFYICON_TOAST_BODY PDU",
            2147549183LL,
            0,
            0);
        if ( *((unsigned __int16 *)v5 + 1) < v666 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_857;
          }
          v663 = RdpX_GetActivityIdPrefix(v665, v662, v660, v661);
          v664 = 195;
          goto LABEL_856;
        }
        v667 = (struct ITSWndPluginEx **)CacCommon::Rect<int>::Rect<int>(v980);
        RemoteAppWindow = RdpRemoteAppCore::GetWndPlugin((RdpRemoteAppCore *)((char *)v6 - 48), v667);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_858;
          }
          v672 = RdpX_GetActivityIdPrefix(v669, v668, v670, v671);
          v673 = 196;
          v674 = "GetWndPlugin failed";
          goto LABEL_871;
        }
        v675 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v980);
        v676 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, void *))(*(_QWORD *)v675 + 72LL);
        v677 = CacCommon::Rect<int>::Rect<int>(v975);
        RemoteAppWindow = v676(v675, *((unsigned int *)v5 + 1), *((unsigned int *)v5 + 2), v677);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_858;
          }
          v672 = RdpX_GetActivityIdPrefix(v679, v678, v680, v681);
          v673 = 197;
          v674 = "FindShellNotifyInfo failed";
LABEL_871:
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v673,
            (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
            v672,
            (__int64)v674,
            RemoteAppWindow);
          goto LABEL_858;
        }
        v682 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v975);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v682 + 128LL))(v682);
        v683 = *((unsigned __int16 *)v5 + 8);
        v684 = (char *)v5 + 20;
        RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v1006);
        v685 = CacCommon::Rect<int>::Rect<int>(v1006);
        ConstXChar16StringWithSpecifiedSize = RdpX_Strings_CreateConstXChar16StringWithSpecifiedSize(
                                                *((unsigned __int16 *)v5 + 8) >> 1,
                                                (char *)v5 + 20,
                                                v685);
        RemoteAppWindow = MapXResultToHR(ConstXChar16StringWithSpecifiedSize);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v691 = RdpX_GetActivityIdPrefix(v688, v687, v689, v690);
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              198,
              (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v691,
              (__int64)"RdpX_Strings_CreateConstXChar16StringWithSpecifiedSize failed",
              RemoteAppWindow);
          }
          goto LABEL_882;
        }
        v692 = &v684[v683];
        RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v1017);
        v693 = CacCommon::Rect<int>::Rect<int>(v1017);
        v694 = RdpX_Strings_CreateConstXChar16StringWithSpecifiedSize(
                 *((unsigned __int16 *)v5 + 9) >> 1,
                 &v684[v683],
                 v693);
        RemoteAppWindow = MapXResultToHR(v694);
        if ( RemoteAppWindow >= 0 )
        {
          v702 = &sourceString;
          if ( RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v1017) )
          {
            v703 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v1017);
            v704 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v703 + 24LL))(v703);
          }
          else
          {
            v704 = &sourceString;
          }
          if ( RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v1006) )
          {
            v705 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v1006);
            v702 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v705 + 24LL))(v705);
          }
          LODWORD(cchToCopy) = *((_DWORD *)v5 + 2);
          RdpRemoteAppCore::LogRemoteAppEventF(
            (char *)v971 + 16,
            L"NotifyIconToastRailOrderReceived: WindowId=0x%x, NotifyIconId=0x%x, ToastFlags=0x%x, Toast=%s, ToastTitle=%s",
            0,
            *((unsigned int *)v5 + 1),
            cchToCopy,
            *((_DWORD *)v5 + 3),
            v702,
            v704);
          v706 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v975);
          LOWORD(v950) = *((_WORD *)v5 + 9) >> 1;
          RemoteAppWindow = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, __int64, int, char *))(*(_QWORD *)v706 + 96LL))(
                              v706,
                              0,
                              *((unsigned int *)v5 + 3),
                              *((_WORD *)v5 + 8) >> 1,
                              (__int64)v5 + 20,
                              v950,
                              v692);
          if ( RemoteAppWindow >= 0 )
          {
            v711 = (struct RdpXInterfaceShellNotifyInformation *)RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v975);
            v712 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v975);
            v713 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v712 + 72LL))(v712);
            RemoteAppWindow = RdpRemoteAppCore::OnShellNotifyInformation(v971, v713, v711);
            if ( RemoteAppWindow >= 0
              || WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
              || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_889;
            }
            v699 = RdpX_GetActivityIdPrefix(v715, v714, v716, v717);
            v700 = 201;
            v701 = "OnShellNotifyInformation failed";
          }
          else
          {
            if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
              || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_889;
            }
            v699 = RdpX_GetActivityIdPrefix(v708, v707, v709, v710);
            v700 = 200;
            v701 = "spShellNotify->SetInfo failed";
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
          v699 = RdpX_GetActivityIdPrefix(v696, v695, v697, v698);
          v700 = 199;
          v701 = "RdpX_Strings_CreateConstXChar16StringWithSpecifiedSize failed";
        }
        LODWORD(v941) = RemoteAppWindow;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v700,
          (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v699,
          (__int64)v701,
          v941);
LABEL_889:
        RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v1017);
LABEL_882:
        RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v1006);
        goto LABEL_858;
      }
      RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v960);
      RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v967);
      if ( *((_WORD *)v5 + 1) < 0x18u )
        RdpRemoteAppCore::LogRemoteAppError(
          (char *)v6 + 16,
          L"Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Change PDU",
          2147549183LL,
          0,
          0);
      v721 = *((unsigned __int16 *)v5 + 1);
      if ( (unsigned int)v721 < 0x18 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_913;
        }
        v722 = RdpX_GetActivityIdPrefix(v721, v718, v719, v720);
        v723 = 180;
LABEL_912:
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v723,
          &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v722,
          -2147418113);
LABEL_913:
        RemoteAppWindow = -2147418113;
LABEL_914:
        TCntPtr<ITSViewerRecorder>::SafeRelease(v967);
        v634 = v960;
        goto LABEL_1025;
      }
      v724 = *((unsigned __int16 *)v5 + 6) + 24;
      if ( (unsigned int)v721 < v724 )
        RdpRemoteAppCore::LogRemoteAppError(
          (char *)v6 + 16,
          L"Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Change PDU",
          2147549183LL,
          0,
          0);
      if ( *((unsigned __int16 *)v5 + 1) < v724 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_913;
        }
        v722 = RdpX_GetActivityIdPrefix(v721, v718, v719, v720);
        v723 = 181;
        goto LABEL_912;
      }
      v725 = (struct ITSWndPluginEx **)CacCommon::Rect<int>::Rect<int>(v967);
      RemoteAppWindow = RdpRemoteAppCore::GetWndPlugin((RdpRemoteAppCore *)((char *)v6 - 48), v725);
      if ( RemoteAppWindow < 0 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_914;
        }
        v730 = RdpX_GetActivityIdPrefix(v727, v726, v728, v729);
        v731 = 182;
        v732 = "GetWndPlugin failed";
        goto LABEL_927;
      }
      v733 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v967);
      v734 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, void *))(*(_QWORD *)v733 + 72LL);
      v735 = CacCommon::Rect<int>::Rect<int>(v960);
      v736 = v734(v733, *((unsigned int *)v5 + 1), *((unsigned int *)v5 + 2), v735);
      v741 = 0;
      RemoteAppWindow = v736;
      if ( v736 < 0 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_914;
        }
        v730 = RdpX_GetActivityIdPrefix(v738, v737, v739, v740);
        v731 = 183;
        v732 = "FindShellNotifyInfo failed";
LABEL_927:
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v731,
          (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v730,
          (__int64)v732,
          RemoteAppWindow);
        goto LABEL_914;
      }
      v742 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v960);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v742 + 128LL))(v742);
      RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v969);
      if ( *((_WORD *)v5 + 6) )
      {
        v743 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v960);
        RemoteAppWindow = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v743 + 88LL))(
                            v743,
                            *((_WORD *)v5 + 6) >> 1,
                            (__int64)v5 + 24);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_940;
          }
          v748 = RdpX_GetActivityIdPrefix(v745, v744, v746, v747);
          v749 = 184;
          v750 = "CreateShellNotifyInfo->SetTip failed";
          goto LABEL_939;
        }
        v751 = CacCommon::Rect<int>::Rect<int>(v969);
        v752 = RdpX_Strings_CreateConstXChar16StringWithSpecifiedSize(
                 *((unsigned __int16 *)v5 + 6) >> 1,
                 (char *)v5 + 24,
                 v751);
        RemoteAppWindow = MapXResultToHR(v752);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_940;
          }
          v748 = RdpX_GetActivityIdPrefix(v754, v753, v755, v756);
          v749 = 185;
          v750 = "RdpX_Strings_CreateConstXChar16StringWithSpecifiedSize failed";
          goto LABEL_939;
        }
      }
      if ( (*((_BYTE *)v5 + 20) & 4) != 0 )
      {
        v757 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v960);
        RemoteAppWindow = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v757 + 104LL))(
                            v757,
                            *((unsigned int *)v5 + 4));
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_940;
          }
          v748 = RdpX_GetActivityIdPrefix(v759, v758, v760, v761);
          v749 = 186;
          v750 = "CreateShellNotifyInfo->SetWSNState failed";
          goto LABEL_939;
        }
      }
      if ( *((_BYTE *)v5 + 14) )
      {
        RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v988);
        v766 = *((unsigned __int16 *)v5 + 6);
        v767 = *((unsigned __int16 *)v5 + 1);
        if ( *((_BYTE *)v5 + 15) )
        {
          v768 = v724 + 4;
          v769 = v971;
          if ( v767 < v768 )
            RdpRemoteAppCore::LogRemoteAppError(
              (char *)v971 + 16,
              L"Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Create PDU",
              2147549183LL,
              0,
              0);
          if ( *((unsigned __int16 *)v5 + 1) < v768 )
          {
            if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
              || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_962;
            }
            v770 = RdpX_GetActivityIdPrefix(v763, v762, v764, v765);
            v771 = 187;
LABEL_961:
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v771,
              &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v770,
              -2147418113);
LABEL_962:
            RemoteAppWindow = -2147418113;
LABEL_963:
            RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v988);
            goto LABEL_940;
          }
          v772 = *((unsigned __int8 *)v5 + v766 + 27);
          LODWORD(v976) = *((unsigned __int8 *)v5 + v766 + 26);
          v961 = *(unsigned __int16 *)((char *)v5 + v766 + 24);
          if ( RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v969) )
          {
            v773 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v969);
            v774 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v773 + 24LL))(v773);
          }
          else
          {
            v774 = &sourceString;
          }
          LODWORD(cchToCopy) = *((_DWORD *)v5 + 2);
          RdpRemoteAppCore::LogRemoteAppEventF(
            (char *)v769 + 16,
            L"NotifyIconChangeRailOrderReceived_Cached: WindowId=0x%x, NotifyIconId=0x%x, NumIcons=%hhu, IsCachedIcon=%hhu"
             ", StateFlags=0x%x, PDUFlags=0x%x, ToolTipBytes=%hu, ToolTip=%s, CacheEntry=0x%hx, CacheId=0x%hhx, IconFlags=0x%hhx",
            0,
            *((unsigned int *)v5 + 1),
            cchToCopy,
            *((unsigned __int8 *)v5 + 14),
            *((unsigned __int8 *)v5 + 15),
            *((_DWORD *)v5 + 4),
            *((_DWORD *)v5 + 5),
            *((unsigned __int16 *)v5 + 6),
            v774,
            v961,
            v976,
            v772);
          v775 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v967);
          v776 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, void *))(*(_QWORD *)v775 + 56LL);
          v777 = CacCommon::Rect<int>::Rect<int>(v988);
          RemoteAppWindow = v776(
                              v775,
                              *((unsigned __int8 *)v5 + v766 + 26),
                              *(unsigned __int16 *)((char *)v5 + v766 + 24),
                              v777);
          if ( RemoteAppWindow < 0 )
          {
            if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
              || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_963;
            }
            v782 = RdpX_GetActivityIdPrefix(v779, v778, v780, v781);
            v783 = 188;
            goto LABEL_972;
          }
        }
        else
        {
          v785 = v724 + 20;
          v769 = v971;
          if ( v767 < v785 )
            RdpRemoteAppCore::LogRemoteAppError(
              (char *)v971 + 16,
              L"Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Change PDU",
              2147549183LL,
              0,
              0);
          v786 = *((unsigned __int16 *)v5 + 1);
          if ( (unsigned int)v786 < v785 )
          {
            if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
              || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_962;
            }
            v770 = RdpX_GetActivityIdPrefix(v763, v786, v764, v765);
            v771 = 189;
            goto LABEL_961;
          }
          if ( (*((_BYTE *)v5 + v766 + 27) & 2) != 0 )
          {
            LOBYTE(v763) = *((_BYTE *)v5 + v766 + 32);
            v741 = *(_WORD *)((char *)v5 + v766 + 34);
            LOWORD(v961) = v763;
          }
          else
          {
            LOWORD(v961) = 32;
          }
          v787 = *(unsigned int *)((char *)v5 + v766 + 36);
          v788 = v741;
          v789 = v741 + *(_DWORD *)((char *)v5 + v766 + 40);
          v981 = v787;
          v982 = v741;
          v790 = v787 + v789 + v785;
          if ( (unsigned int)v786 < v790 )
            RdpRemoteAppCore::LogRemoteAppError(
              (char *)v769 + 16,
              L"Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Change PDU",
              2147549183LL,
              0,
              0);
          if ( *((unsigned __int16 *)v5 + 1) < v790 )
          {
            if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
              || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_962;
            }
            v770 = RdpX_GetActivityIdPrefix(v788, v786, v787, v765);
            v771 = 190;
            goto LABEL_961;
          }
          v971 = (struct tagTS_RAIL_PDU *)((char *)v5 + v766 + v741 + 44);
          LODWORD(v976) = *(_DWORD *)((char *)v5 + v766 + 40);
          v1012 = *(_DWORD *)((char *)v5 + v766 + 36);
          v1008 = *(unsigned __int16 *)((char *)v5 + v766 + 34);
          v1009 = *((unsigned __int8 *)v5 + v766 + 32);
          v1010 = *(unsigned __int16 *)((char *)v5 + v766 + 30);
          v1011 = *(unsigned __int16 *)((char *)v5 + v766 + 28);
          v1014 = *((unsigned __int8 *)v5 + v766 + 27);
          v1013 = *((unsigned __int8 *)v5 + v766 + 26);
          v983 = *(unsigned __int16 *)((char *)v5 + v766 + 24);
          if ( RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v969) )
          {
            v791 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v969);
            v792 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v791 + 24LL))(v791);
          }
          else
          {
            v792 = &sourceString;
          }
          LODWORD(cchToCopy) = *((_DWORD *)v5 + 2);
          RdpRemoteAppCore::LogRemoteAppEventF(
            (char *)v769 + 16,
            L"NotifyIconChangeRailOrderReceived_NonCached: WindowId=0x%x, NotifyIconId=0x%x, NumIcons=%hhu, IsCachedIcon=%"
             "hhu,StateFlags=0x%x, PDUFlags=0x%x, ToolTipBytes=%hu, ToolTip=%s, CacheEntry=0x%hx, CacheId=0x%hhx, IconFla"
             "gs=0x%hhx, Width=%hu, Height=%hu, Bpp=%hhu, ColorTableBytes=%hu, BitsMaskBytes=%u, BitsColorBytes=%u",
            0,
            *((unsigned int *)v5 + 1),
            cchToCopy,
            *((unsigned __int8 *)v5 + 14),
            *((unsigned __int8 *)v5 + 15),
            *((_DWORD *)v5 + 4),
            *((_DWORD *)v5 + 5),
            *((unsigned __int16 *)v5 + 6),
            v792,
            v983,
            v1013,
            v1014,
            v1011,
            v1010,
            v1009,
            v1008,
            v1012,
            v976);
          v793 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v967);
          v794 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, char *, _DWORD, _DWORD, char *, int, RdpRemoteAppCore *, _DWORD, char *, _DWORD, void *))(*(_QWORD *)v793 + 64LL);
          v795 = CacCommon::Rect<int>::Rect<int>(v988);
          v796 = (char *)v971 + v981;
          LOBYTE(v796) = v961;
          RemoteAppWindow = v794(
                              v793,
                              *((unsigned __int8 *)v5 + v766 + 26),
                              *(unsigned __int16 *)((char *)v5 + v766 + 24),
                              v796,
                              *(unsigned __int16 *)((char *)v5 + v766 + 28),
                              *(unsigned __int16 *)((char *)v5 + v766 + 30),
                              (char *)v5 + v766 + 44,
                              v982,
                              v971,
                              *(_DWORD *)((char *)v5 + v766 + 36),
                              (char *)v971 + v981,
                              *(_DWORD *)((char *)v5 + v766 + 40),
                              v795);
          if ( RemoteAppWindow < 0 )
          {
            if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
              || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_963;
            }
            v782 = RdpX_GetActivityIdPrefix(v798, v797, v799, v800);
            v783 = 191;
LABEL_972:
            v784 = "CreateCachedIcon failed";
LABEL_973:
            LODWORD(v941) = RemoteAppWindow;
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v783,
              (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v782,
              (__int64)v784,
              v941);
            goto LABEL_963;
          }
        }
        v801 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v960);
        v802 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v801 + 80LL);
        v803 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v988);
        RemoteAppWindow = v802(v801, v803);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_963;
          }
          v782 = RdpX_GetActivityIdPrefix(v805, v804, v806, v807);
          v783 = 192;
          v784 = "spShellNotify->SetIcon failed";
          goto LABEL_973;
        }
        RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v988);
      }
      else
      {
        v769 = v971;
        if ( RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v969) )
        {
          v808 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v969);
          v809 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v808 + 24LL))(v808);
        }
        else
        {
          v809 = &sourceString;
        }
        LODWORD(cchToCopy) = *((_DWORD *)v5 + 2);
        RdpRemoteAppCore::LogRemoteAppEventF(
          (char *)v769 + 16,
          L"NotifyIconChangeRailOrderReceived_NoIcons: WindowId=0x%x, NotifyIconId=0x%x, NumIcons=%hhu, IsCachedIcon=%hhu,"
           " StateFlags=0x%x, PDUFlags=0x%x, ToolTipBytes=%hu, ToolTip=%s",
          0,
          *((unsigned int *)v5 + 1),
          cchToCopy,
          *((unsigned __int8 *)v5 + 14),
          *((unsigned __int8 *)v5 + 15),
          *((_DWORD *)v5 + 4),
          *((_DWORD *)v5 + 5),
          *((unsigned __int16 *)v5 + 6),
          v809);
      }
      v810 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v960);
      if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v810 + 72LL))(v810) )
        goto LABEL_940;
      v811 = (struct RdpXInterfaceShellNotifyInformation *)RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v960);
      v812 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v960);
      v813 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v812 + 72LL))(v812);
      RemoteAppWindow = RdpRemoteAppCore::OnShellNotifyInformation(v769, v813, v811);
      if ( RemoteAppWindow >= 0
        || WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_940;
      }
      v748 = RdpX_GetActivityIdPrefix(v815, v814, v816, v817);
      v749 = 193;
      v750 = "OnShellNotifyInformation failed";
LABEL_939:
      LODWORD(v941) = RemoteAppWindow;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v749,
        (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
        v748,
        (__int64)v750,
        v941);
LABEL_940:
      RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v969);
      goto LABEL_914;
    }
    RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v959);
    RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v962);
    if ( *((_WORD *)v5 + 1) < 0x18u )
      RdpRemoteAppCore::LogRemoteAppError(
        (char *)v6 + 16,
        L"Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Create PDU",
        2147549183LL,
        0,
        0);
    v821 = *((unsigned __int16 *)v5 + 1);
    if ( (unsigned int)v821 < 0x18 )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_1023;
      }
      v822 = RdpX_GetActivityIdPrefix(v821, v818, v819, v820);
      v823 = 165;
LABEL_1022:
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v823,
        &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
        v822,
        -2147418113);
LABEL_1023:
      RemoteAppWindow = -2147418113;
LABEL_1024:
      TCntPtr<ITSViewerRecorder>::SafeRelease(v962);
      v634 = v959;
      goto LABEL_1025;
    }
    v824 = *((unsigned __int16 *)v5 + 6) + 24;
    if ( (unsigned int)v821 < v824 )
      RdpRemoteAppCore::LogRemoteAppError(
        (char *)v6 + 16,
        L"Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Create PDU",
        2147549183LL,
        0,
        0);
    if ( *((unsigned __int16 *)v5 + 1) < v824 )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_1023;
      }
      v822 = RdpX_GetActivityIdPrefix(v821, v818, v819, v820);
      v823 = 166;
      goto LABEL_1022;
    }
    v825 = (struct ITSWndPluginEx **)CacCommon::Rect<int>::Rect<int>(v962);
    RemoteAppWindow = RdpRemoteAppCore::GetWndPlugin((RdpRemoteAppCore *)((char *)v6 - 48), v825);
    if ( RemoteAppWindow < 0 )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_1024;
      }
      v830 = RdpX_GetActivityIdPrefix(v827, v826, v828, v829);
      v831 = 167;
      v832 = "GetWndPlugin failed";
      goto LABEL_1038;
    }
    v833 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v962);
    v834 = *(int (__fastcall **)(__int64, _QWORD, _QWORD, void *))(*(_QWORD *)v833 + 72LL);
    v835 = CacCommon::Rect<int>::Rect<int>(v959);
    if ( v834(v833, *((unsigned int *)v5 + 1), *((unsigned int *)v5 + 2), v835) >= 0 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v848 = *((_DWORD *)v5 + 2);
        v849 = *((_DWORD *)v5 + 1);
        v850 = RdpX_GetActivityIdPrefix(v837, v836, v838, v839);
        WPP_SF_DLD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          169,
          &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v850,
          v849,
          v848);
      }
      v851 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v959);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v851 + 128LL))(v851);
    }
    else
    {
      v840 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v962);
      v841 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, void *))(*(_QWORD *)v840 + 80LL);
      v842 = CacCommon::Rect<int>::Rect<int>(v959);
      RemoteAppWindow = v841(v840, *((unsigned int *)v5 + 1), *((unsigned int *)v5 + 2), v842);
      if ( RemoteAppWindow < 0 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_1024;
        }
        v830 = RdpX_GetActivityIdPrefix(v844, v843, v845, v846);
        v831 = 168;
        v832 = "CreateShellNotifyInfo failed";
LABEL_1038:
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v831,
          (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v830,
          (__int64)v832,
          RemoteAppWindow);
        goto LABEL_1024;
      }
      v847 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v959);
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v847 + 120LL))(v847, 1);
    }
    v852 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v962);
    if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v852 + 136LL))(v852) )
    {
      v853 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v959);
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v853 + 136LL))(v853, 2);
    }
    v854 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v959);
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v854 + 112LL))(v854, 4);
    RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v970);
    if ( *((_WORD *)v5 + 6) )
    {
      v855 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v959);
      RemoteAppWindow = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v855 + 88LL))(
                          v855,
                          *((_WORD *)v5 + 6) >> 1,
                          (__int64)v5 + 24);
      if ( RemoteAppWindow < 0 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_1060;
        }
        v860 = RdpX_GetActivityIdPrefix(v857, v856, v858, v859);
        v861 = 170;
        v862 = "CreateShellNotifyInfo->SetTip failed";
        goto LABEL_1059;
      }
      v863 = CacCommon::Rect<int>::Rect<int>(v970);
      v864 = RdpX_Strings_CreateConstXChar16StringWithSpecifiedSize(
               *((unsigned __int16 *)v5 + 6) >> 1,
               (char *)v5 + 24,
               v863);
      RemoteAppWindow = MapXResultToHR(v864);
      if ( RemoteAppWindow < 0 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_1060;
        }
        v860 = RdpX_GetActivityIdPrefix(v866, v865, v867, v868);
        v861 = 171;
        v862 = "RdpX_Strings_CreateConstXChar16StringWithSpecifiedSize failed";
        goto LABEL_1059;
      }
    }
    if ( (*((_BYTE *)v5 + 20) & 4) != 0 )
    {
      v869 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v959);
      RemoteAppWindow = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v869 + 104LL))(
                          v869,
                          *((unsigned int *)v5 + 4));
      if ( RemoteAppWindow < 0 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_1060;
        }
        v860 = RdpX_GetActivityIdPrefix(v871, v870, v872, v873);
        v861 = 172;
        v862 = "CreateShellNotifyInfo->SetWSNState failed";
        goto LABEL_1059;
      }
    }
    if ( *((_BYTE *)v5 + 14) )
    {
      RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v989);
      v878 = *((unsigned __int16 *)v5 + 6);
      v879 = *((unsigned __int16 *)v5 + 1);
      if ( *((_BYTE *)v5 + 15) )
      {
        v880 = v824 + 4;
        v881 = v971;
        if ( v879 < v880 )
          RdpRemoteAppCore::LogRemoteAppError(
            (char *)v971 + 16,
            L"Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Create PDU",
            2147549183LL,
            0,
            0);
        if ( *((unsigned __int16 *)v5 + 1) < v880 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_1082;
          }
          v882 = RdpX_GetActivityIdPrefix(v875, v874, v876, v877);
          v883 = 173;
LABEL_1081:
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v883,
            &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
            v882,
            -2147418113);
LABEL_1082:
          RemoteAppWindow = -2147418113;
LABEL_1083:
          RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v989);
          goto LABEL_1060;
        }
        v982 = *((unsigned __int8 *)v5 + v878 + 27);
        v981 = *((unsigned __int8 *)v5 + v878 + 26);
        v983 = *(unsigned __int16 *)((char *)v5 + v878 + 24);
        if ( RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v970) )
        {
          v884 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v970);
          v885 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v884 + 24LL))(v884);
        }
        else
        {
          v885 = &sourceString;
        }
        LODWORD(v941) = *((unsigned __int8 *)v5 + 14);
        LODWORD(cchToCopy) = *((_DWORD *)v5 + 2);
        RdpRemoteAppCore::LogRemoteAppEventF(
          (char *)v881 + 16,
          L"NotifyIconCreateRailOrderReceived_Cached: WindowId=0x%x, NotifyIconId=0x%x, NumIcons=%hhu, IsCachedIcon=%hhu, "
           "StateFlags=0x%x, PDUFlags=0x%x, ToolTipBytes=%hu, ToolTip=%s, CacheEntry=0x%hx, CacheId=0x%hhx, IconFlags=0x%hhx",
          0,
          *((unsigned int *)v5 + 1),
          cchToCopy,
          v941,
          *((unsigned __int8 *)v5 + 15),
          *((_DWORD *)v5 + 4),
          *((_DWORD *)v5 + 5),
          *((unsigned __int16 *)v5 + 6),
          v885,
          v983,
          v981,
          v982);
        v886 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v962);
        v887 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, void *))(*(_QWORD *)v886 + 56LL);
        v888 = CacCommon::Rect<int>::Rect<int>(v989);
        RemoteAppWindow = v887(
                            v886,
                            *((unsigned __int8 *)v5 + v878 + 26),
                            *(unsigned __int16 *)((char *)v5 + v878 + 24),
                            v888);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_1083;
          }
          v893 = RdpX_GetActivityIdPrefix(v890, v889, v891, v892);
          v894 = 174;
          goto LABEL_1092;
        }
      }
      else
      {
        v896 = v824 + 20;
        v881 = v971;
        if ( v879 < v896 )
          RdpRemoteAppCore::LogRemoteAppError(
            (char *)v971 + 16,
            L"Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Create PDU",
            2147549183LL,
            0,
            0);
        v897 = *((unsigned __int16 *)v5 + 1);
        if ( (unsigned int)v897 < v896 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_1082;
          }
          v882 = RdpX_GetActivityIdPrefix(v875, v874, v876, v897);
          v883 = 175;
          goto LABEL_1081;
        }
        if ( (*((_BYTE *)v5 + v878 + 27) & 2) != 0 )
        {
          LOBYTE(v874) = *((_BYTE *)v5 + v878 + 32);
          v898 = *(unsigned __int16 *)((char *)v5 + v878 + 34);
          LOWORD(v961) = v874;
        }
        else
        {
          v898 = 0;
          LOWORD(v961) = 32;
        }
        v1012 = *(_DWORD *)((char *)v5 + v878 + 36);
        v899 = (unsigned __int16)v898 + v1012;
        LODWORD(v976) = v898;
        v900 = *(_DWORD *)((char *)v5 + v878 + 40) + v899 + v896;
        LODWORD(v971) = (unsigned __int16)v898;
        if ( (unsigned int)v897 < v900 )
        {
          RdpRemoteAppCore::LogRemoteAppError(
            (char *)v881 + 16,
            L"Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Create PDU",
            2147549183LL,
            0,
            0);
          v898 = (unsigned int)v976;
        }
        if ( *((unsigned __int16 *)v5 + 1) < v900 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_1082;
          }
          v882 = RdpX_GetActivityIdPrefix(v899, v874, v898, v897);
          v883 = 176;
          goto LABEL_1081;
        }
        v976 = (__int64)v5 + v878 + (unsigned __int16)v898 + 44;
        v982 = *(_DWORD *)((char *)v5 + v878 + 40);
        v981 = *(_DWORD *)((char *)v5 + v878 + 36);
        v983 = *(unsigned __int16 *)((char *)v5 + v878 + 34);
        v1013 = *((unsigned __int8 *)v5 + v878 + 32);
        v1014 = *(unsigned __int16 *)((char *)v5 + v878 + 30);
        v1011 = *(unsigned __int16 *)((char *)v5 + v878 + 28);
        v1010 = *((unsigned __int8 *)v5 + v878 + 27);
        v1009 = *((unsigned __int8 *)v5 + v878 + 26);
        v1008 = *(unsigned __int16 *)((char *)v5 + v878 + 24);
        if ( RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v970) )
        {
          v901 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v970);
          v902 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v901 + 24LL))(v901);
        }
        else
        {
          v902 = &sourceString;
        }
        LODWORD(v941) = *((unsigned __int8 *)v5 + 14);
        LODWORD(cchToCopy) = *((_DWORD *)v5 + 2);
        RdpRemoteAppCore::LogRemoteAppEventF(
          (char *)v881 + 16,
          L"NotifyIconCreateRailOrderReceived_NonCached: WindowId=0x%x, NotifyIconId=0x%x, NumIcons=%hhu, IsCachedIcon=%hh"
           "u, StateFlags=0x%x, PDUFlags=0x%x, ToolTipBytes=%hu, ToolTip=%s, CacheEntry=0x%hx, CacheId=0x%hhx, IconFlags="
           "0x%hhx, Width=%hu, Height=%hu, Bpp=%hhu, ColorTableBytes=%hu, BitsMaskBytes=%u, BitsColorBytes=%u",
          0,
          *((unsigned int *)v5 + 1),
          cchToCopy,
          v941,
          *((unsigned __int8 *)v5 + 15),
          *((_DWORD *)v5 + 4),
          *((_DWORD *)v5 + 5),
          *((unsigned __int16 *)v5 + 6),
          v902,
          v1008,
          v1009,
          v1010,
          v1011,
          v1014,
          v1013,
          v983,
          v981,
          v982);
        v903 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v962);
        v904 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64, _DWORD, _DWORD, char *, _DWORD, __int64, _DWORD, __int64, _DWORD, void *))(*(_QWORD *)v903 + 64LL);
        v905 = CacCommon::Rect<int>::Rect<int>(v989);
        v906 = v976 + v1012;
        LOBYTE(v906) = v961;
        RemoteAppWindow = v904(
                            v903,
                            *((unsigned __int8 *)v5 + v878 + 26),
                            *(unsigned __int16 *)((char *)v5 + v878 + 24),
                            v906,
                            *(unsigned __int16 *)((char *)v5 + v878 + 28),
                            *(unsigned __int16 *)((char *)v5 + v878 + 30),
                            (char *)v5 + v878 + 44,
                            (_DWORD)v971,
                            v976,
                            *(_DWORD *)((char *)v5 + v878 + 36),
                            v976 + v1012,
                            *(_DWORD *)((char *)v5 + v878 + 40),
                            v905);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_1083;
          }
          v893 = RdpX_GetActivityIdPrefix(v908, v907, v909, v910);
          v894 = 177;
LABEL_1092:
          v895 = "CreateCachedIcon failed";
LABEL_1093:
          LODWORD(v941) = RemoteAppWindow;
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v894,
            (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
            v893,
            (__int64)v895,
            v941);
          goto LABEL_1083;
        }
      }
      v911 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v959);
      v912 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v911 + 80LL);
      v913 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v989);
      RemoteAppWindow = v912(v911, v913);
      if ( RemoteAppWindow < 0 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_1083;
        }
        v893 = RdpX_GetActivityIdPrefix(v915, v914, v916, v917);
        v894 = 178;
        v895 = "spShellNotify->SetIcon failed";
        goto LABEL_1093;
      }
      RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v989);
    }
    else
    {
      v881 = v971;
      if ( RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v970) )
      {
        v918 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v970);
        v919 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v918 + 24LL))(v918);
      }
      else
      {
        v919 = &sourceString;
      }
      LODWORD(v941) = *((unsigned __int8 *)v5 + 14);
      LODWORD(cchToCopy) = *((_DWORD *)v5 + 2);
      RdpRemoteAppCore::LogRemoteAppEventF(
        (char *)v881 + 16,
        L"NotifyIconCreateRailOrderReceived_NoIcons: WindowId=0x%x, NotifyIconId=0x%x, NumIcons=%hhu, IsCachedIcon=%hhu, S"
         "tateFlags=0x%x, PDUFlags=0x%x, ToolTipBytes=%hu, ToolTip=%s",
        0,
        *((unsigned int *)v5 + 1),
        cchToCopy,
        v941,
        *((unsigned __int8 *)v5 + 15),
        *((_DWORD *)v5 + 4),
        *((_DWORD *)v5 + 5),
        *((unsigned __int16 *)v5 + 6),
        v919);
    }
    v920 = (struct RdpXInterfaceShellNotifyInformation *)RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v959);
    v921 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v959);
    v922 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v921 + 72LL))(v921);
    RemoteAppWindow = RdpRemoteAppCore::OnShellNotifyInformation(v881, v922, v920);
    if ( RemoteAppWindow >= 0
      || WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_1060;
    }
    v860 = RdpX_GetActivityIdPrefix(v924, v923, v925, v926);
    v861 = 179;
    v862 = "OnShellNotifyInformation failed";
LABEL_1059:
    LODWORD(v941) = RemoteAppWindow;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v861,
      (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
      v860,
      (__int64)v862,
      v941);
LABEL_1060:
    RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v970);
    goto LABEL_1024;
  }
  if ( (_DWORD)v20 == 24 )
  {
    v249 = *((unsigned __int16 *)v5 + 1);
    if ( (_WORD)v249 != 1052 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v250 = RdpX_GetActivityIdPrefix(v20, v17, v18, v19);
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v250, v249);
      }
      v28 = *((unsigned __int16 *)v5 + 1);
      v29 = L"Invalid size for TS_RAIL_ORDER_GET_APPID_RESP_EX [%d]";
      RemoteAppWindow = -2147467259;
      v30 = 2147500037LL;
      goto LABEL_1165;
    }
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v251 = *((_DWORD *)v5 + 132);
      v252 = *((_DWORD *)v5 + 1);
      v253 = RdpX_GetActivityIdPrefix(v20, v17, v18, v19);
      WPP_SF_DDDS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        86,
        (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
        v253,
        v252,
        v251,
        (__int64)v5 + 532);
    }
    FileNameW = CUT::PathFindFileNameW((const unsigned __int16 *)v5 + 266);
    v255 = *((_DWORD *)v5 + 132);
    v256 = FileNameW;
    v257 = CUT::PathFindFileNameW((const unsigned __int16 *)v5 + 4);
    LODWORD(v941) = v255;
    RdpRemoteAppCore::LogRemoteAppEventF(
      (char *)v971 + 16,
      L"GetAppIdRespExRailOrderReceived: WindowId=0x%x, CensoredAppId=%s, ProcessId=%u, CensoredProcessImageName=%s",
      0,
      *((unsigned int *)v5 + 1),
      v257,
      v941,
      v256);
    v258 = (RdpRemoteAppCore *)((char *)v971 - 48);
    v992 = 0;
    RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow(
                        (RdpRemoteAppCore *)((char *)v971 - 48),
                        *((_DWORD *)v5 + 1),
                        &v992);
    if ( RemoteAppWindow >= 0 )
    {
      updated = RdpRemoteAppCore::UpdateProcessInfo(
                  v258,
                  v992,
                  *((_DWORD *)v5 + 132),
                  (const unsigned __int16 *)v5 + 266);
      if ( updated < 0
        && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v269 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v265, v267, v268);
        LODWORD(v945) = updated;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          88,
          (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v269,
          (__int64)"Failed to set process info",
          v945);
      }
      RemoteAppWindow = RdpRemoteAppCore::UpdateAppID(v258, v992, (const unsigned __int16 *)v5 + 4);
      if ( RemoteAppWindow < 0
        && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v274 = RdpX_GetActivityIdPrefix(v271, v270, v272, v273);
        LODWORD(v945) = RemoteAppWindow;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          89,
          (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v274,
          (__int64)"UpdateAppID failed",
          v945);
      }
      v42 = v992;
      if ( v992 )
      {
        v992 = 0;
        goto LABEL_106;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v263 = *((_DWORD *)v5 + 1);
        v264 = RdpX_GetActivityIdPrefix(v260, v259, v261, v262);
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v264, v263);
      }
      v42 = v992;
      if ( v992 )
      {
        v992 = 0;
        goto LABEL_106;
      }
    }
    return (unsigned int)RemoteAppWindow;
  }
  if ( (unsigned int)v20 > 0xF )
  {
    v96 = (unsigned int)(v20 - 16);
    if ( (_DWORD)v20 != 16 )
    {
      v97 = (unsigned int)(v20 - 18);
      if ( (_DWORD)v20 == 18 )
      {
        v139 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v140 = RdpX_GetActivityIdPrefix(v20, v97, v18, v19);
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 112, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v140);
          v139 = WPP_GLOBAL_Control;
        }
        v141 = *((unsigned __int16 *)v5 + 1);
        if ( (_WORD)v141 != 20 )
        {
          if ( v139 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v139[7] & 1) != 0 && *((_BYTE *)v139 + 25) >= 2u )
          {
            v142 = RdpX_GetActivityIdPrefix(v20, v97, v18, v19);
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              113,
              &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v142,
              v141);
          }
          v28 = *((unsigned __int16 *)v5 + 1);
          v29 = L"Invalid size for TS_RAIL_ORDER_COMPARTMENTINFO [%d]";
          RemoteAppWindow = -2147467259;
          v30 = 2147500037LL;
          goto LABEL_1165;
        }
        RdpRemoteAppCore::LogRemoteAppEventF(
          (char *)v6 + 16,
          L"CompartmentInfoRailOrderReceived: Open=%d, ConversionMode=0x%x, SentenceMode=0x%x, KanaOn=%d",
          0,
          *((unsigned int *)v5 + 1),
          *((_DWORD *)v5 + 2),
          *((_DWORD *)v5 + 3),
          *((_DWORD *)v5 + 4));
        if ( *((_QWORD *)v6 + 17) )
        {
          v143 = *((_DWORD *)v5 + 1);
          v144 = *((_DWORD *)v5 + 4) == 0;
          v145 = *((_DWORD *)v5 + 3);
          v1032[1] = *((_DWORD *)v5 + 2);
          v1032[2] = v145;
          v1032[3] = !v144;
          v1032[0] = v143 != 0;
          (*(void (__fastcall **)(_QWORD, _DWORD *))(**((_QWORD **)v6 + 17) + 48LL))(*((_QWORD *)v6 + 17), v1032);
        }
        return 0;
      }
      v21 = (unsigned int)(v20 - 19);
      if ( (_DWORD)v20 == 19 )
        goto LABEL_197;
      v98 = (unsigned int)(v20 - 20);
      if ( (_DWORD)v20 == 20 )
      {
        v122 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v123 = RdpX_GetActivityIdPrefix(v20, v98, v18, v19);
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 114, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v123);
          v122 = WPP_GLOBAL_Control;
        }
        v124 = *((unsigned __int16 *)v5 + 1);
        if ( v124 == 8 )
        {
          RdpRemoteAppCore::LogRemoteAppEventF(
            (char *)v6 + 16,
            L"ZOrderSyncRailOrderReceived: MarkerWindowId=0x%x",
            0,
            *((unsigned int *)v5 + 1));
          RemoteAppWindow = 0;
          *((_DWORD *)v6 + 55) = *((_DWORD *)v5 + 1);
          return (unsigned int)RemoteAppWindow;
        }
        if ( v122 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v122[7] & 0x40) != 0 && *((_BYTE *)v122 + 25) >= 2u )
        {
          v125 = RdpX_GetActivityIdPrefix(v20, v98, v18, v19);
          WPP_SF_DdL(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            115,
            &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
            v125,
            v124,
            8);
        }
        RemoteAppWindow = -2147418113;
        LODWORD(v941) = 8;
        v111 = 2147549183LL;
        v112 = L"Invalid size for TS_RAIL_ORDER_ZORDER_SYNC: [%d]. Expected size: [%lu]";
LABEL_1150:
        LODWORD(cchToCopy) = *((unsigned __int16 *)v5 + 1);
        RdpRemoteAppCore::LogRemoteAppErrorF((char *)v6 + 16, v112, v111, 0, cchToCopy, v941);
        return (unsigned int)RemoteAppWindow;
      }
      v99 = (unsigned int)(v20 - 21);
      if ( (_DWORD)v20 != 21 )
      {
        if ( (_DWORD)v20 != 22 )
          goto LABEL_1160;
        RemoteAppWindow = 0;
        if ( *((_WORD *)v5 + 1) == 8
          || (RdpRemoteAppCore::LogRemoteAppError(
                (char *)v6 + 16,
                L"Invalid size of TS_RAIL_ORDER_POWER_DISPLAY_REQUEST_BODY PDU",
                2147549183LL,
                0,
                0),
              *((_WORD *)v5 + 1) == 8) )
        {
          RdpRemoteAppCore::LogRemoteAppEventF(
            (char *)v6 + 16,
            L"PowerDisplayRequestRailOrderReceived: Active=%d",
            0,
            *((unsigned int *)v5 + 1));
          v105 = *((_DWORD *)v5 + 1);
          if ( RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *((char *)v6 + 120) )
          {
            v106 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *((char *)v6 + 120);
            (*(void (__fastcall **)(__int64, bool))(*(_QWORD *)v106 + 184LL))(v106, v105 != 0);
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v104 = RdpX_GetActivityIdPrefix(v101, v100, v102, v103);
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              119,
              &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v104,
              -2147418113);
          }
          return (unsigned int)-2147418113;
        }
        return (unsigned int)RemoteAppWindow;
      }
      v107 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v108 = RdpX_GetActivityIdPrefix(v20, v99, v18, v19);
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 116, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v108);
        v107 = WPP_GLOBAL_Control;
      }
      v109 = *((unsigned __int16 *)v5 + 1);
      if ( v109 != 9 )
      {
        if ( v107 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v107[7] & 0x40) != 0 && *((_BYTE *)v107 + 25) >= 2u )
        {
          v110 = RdpX_GetActivityIdPrefix(v20, v99, v18, v19);
          WPP_SF_DdL(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            117,
            &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
            v110,
            v109,
            9);
        }
        RemoteAppWindow = -2147418113;
        LODWORD(v941) = 9;
        v111 = 2147549183LL;
        v112 = L"Invalid size for TS_RAIL_ORDER_CLOAK: [%d]. Expected size: [%lu]";
        goto LABEL_1150;
      }
      RdpRemoteAppCore::LogRemoteAppEventF(
        (char *)v6 + 16,
        L"CloakRailOrderReceived: WindowId=0x%x, Cloaked=%d",
        0,
        *((unsigned int *)v5 + 1),
        *((unsigned __int8 *)v5 + 8));
      v113 = *((_QWORD *)v6 + 15);
      if ( v113 && (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v113 + 120LL))(v113) )
      {
        v1024 = 0;
        v1019 = 0;
        RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow(
                            (RdpRemoteAppCore *)((char *)v6 - 48),
                            *((_DWORD *)v5 + 1),
                            &v1024);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v118 = *((_DWORD *)v5 + 1);
            v119 = RdpX_GetActivityIdPrefix(v115, v114, v116, v117);
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              118,
              &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v119,
              v118);
          }
          v42 = v1024;
          if ( v1024 )
          {
            v1024 = 0;
            goto LABEL_106;
          }
          return (unsigned int)RemoteAppWindow;
        }
        DesktopRemoteAppWindow = RdpRemoteAppCore::GetDesktopRemoteAppWindow(
                                   (RdpRemoteAppCore *)((char *)v6 - 48),
                                   v1024);
        RdpXSPtr<RdpXInterfaceLayerManager>::operator=(&v1019, DesktopRemoteAppWindow);
        if ( v1019 )
        {
          (*(void (__fastcall **)(__int64, bool))(*(_QWORD *)v1019 + 440LL))(v1019, *((_BYTE *)v5 + 8) != 0);
          v121 = v1019;
          if ( v1019 )
          {
            v1019 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v121 + 8LL))(v121);
          }
        }
        RdpXSPtr<RdpXTapVcCallbackItem>::SafeRelease(&v1024);
      }
      return 0;
    }
    v146 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v147 = RdpX_GetActivityIdPrefix(v20, v96, v18, v19);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v147);
      v146 = WPP_GLOBAL_Control;
    }
    v148 = *((unsigned __int16 *)v5 + 1);
    if ( (unsigned __int16)v148 < 0x10u )
    {
      if ( v146 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v146[7] & 1) != 0 && *((_BYTE *)v146 + 25) >= 2u )
      {
        v149 = RdpX_GetActivityIdPrefix(v20, v96, v18, v19);
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v149, v148);
      }
      v28 = *((unsigned __int16 *)v5 + 1);
      v29 = L"Invalid size for TS_RAIL_ORDER_TASKBARINFO [%d]";
      RemoteAppWindow = -2147467259;
      v30 = 2147500037LL;
      goto LABEL_1165;
    }
    RdpRemoteAppCore::LogRemoteAppEventF(
      (char *)v6 + 16,
      L"TaskbarInfoRailOrderReceived: Message=0x%x, WindowIdTab=0x%x, Body=0x%x",
      0,
      *((unsigned int *)v5 + 1),
      *((_DWORD *)v5 + 2),
      *((_DWORD *)v5 + 3));
    v151 = *((unsigned int *)v5 + 2);
    v1028[1] = *((_DWORD *)v5 + 2);
    v152 = *((_DWORD *)v5 + 1);
    v1028[0] = v152;
    if ( v152 == 5 )
    {
      v1030 = *((_DWORD *)v5 + 3);
      v1029 = 0;
      goto LABEL_242;
    }
    if ( (unsigned int)(v152 - 1) <= 3 )
    {
      v1029 = *((_DWORD *)v5 + 3);
      v1030 = 0;
LABEL_242:
      v153 = *((_QWORD *)v6 + 15);
      if ( v153 )
        (*(void (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v153 + 160LL))(v153, v1028);
      return 0;
    }
    if ( v152 == 6 )
    {
      v1020 = 0;
      RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow((RdpRemoteAppCore *)((char *)v6 - 48), v151, &v1020);
      if ( RemoteAppWindow < 0 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v158 = *((_DWORD *)v5 + 2);
          v159 = RdpX_GetActivityIdPrefix(v155, v154, v156, v157);
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            95,
            &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
            v159,
            v158);
        }
        v42 = v1020;
        if ( v1020 )
        {
          v1020 = 0;
          goto LABEL_106;
        }
        return (unsigned int)RemoteAppWindow;
      }
      (*(void (__fastcall **)(struct RdpXInterfaceRemoteAppWindow *, __int64))(*(_QWORD *)v1020 + 264LL))(
        v1020,
        0x100000);
      v160 = v1020;
      if ( v1020 )
      {
        v1020 = 0;
LABEL_387:
        (*(void (__fastcall **)(struct RdpXInterfaceRemoteAppWindow *))(*(_QWORD *)v160 + 8LL))(v160);
        return 0;
      }
      return 0;
    }
    if ( v152 == 7 )
    {
      v1021 = 0;
      RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow((RdpRemoteAppCore *)((char *)v6 - 48), v151, &v1021);
      if ( RemoteAppWindow < 0 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v165 = *((_DWORD *)v5 + 2);
          v166 = RdpX_GetActivityIdPrefix(v162, v161, v163, v164);
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            96,
            &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
            v166,
            v165);
        }
        v42 = v1021;
        if ( v1021 )
        {
          v1021 = 0;
          goto LABEL_106;
        }
        return (unsigned int)RemoteAppWindow;
      }
      (*(void (__fastcall **)(struct RdpXInterfaceRemoteAppWindow *, __int64))(*(_QWORD *)v1021 + 264LL))(
        v1021,
        0x200000);
      v160 = v1021;
      if ( v1021 )
      {
        v1021 = 0;
        goto LABEL_387;
      }
      return 0;
    }
    if ( v152 != 8 )
    {
      if ( v152 == 9 )
      {
        v1005 = 0;
        v991 = 0;
        v213 = (unsigned int)*((unsigned __int16 *)v5 + 6) + 14;
        if ( *((unsigned __int16 *)v5 + 1) >= (unsigned int)v213 )
        {
          RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow((RdpRemoteAppCore *)((char *)v6 - 48), v151, &v1005);
          if ( RemoteAppWindow >= 0 )
          {
            v221 = RdpRemoteAppCore::GetDesktopRemoteAppWindow((RdpRemoteAppCore *)((char *)v6 - 48), v1005);
            RdpXSPtr<RdpXInterfaceLayerManager>::operator=(&v991, v221);
            v222 = v991;
            if ( v991 )
            {
              if ( (unsigned __int16)(*((_WORD *)v5 + 6) - 3) <= 0x205u )
              {
                v223 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v991 + 424LL))(
                         v991,
                         (__int64)v5 + 14,
                         *((unsigned __int16 *)v5 + 6) >> 1);
                v225 = MapXResultToHR(v223);
                if ( v225 < 0
                  && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                  && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v228 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v224, v226, v227);
                  LODWORD(v944) = v225;
                  WPP_SF_DsD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    108,
                    (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                    v228,
                    (__int64)"SetOverlayDesc failed",
                    v944);
                }
                v222 = v991;
              }
              if ( v222 )
              {
                v991 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v222 + 8LL))(v222);
              }
            }
            v160 = v1005;
            if ( !v1005 )
              return 0;
            v1005 = 0;
            goto LABEL_387;
          }
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v219 = *((_DWORD *)v5 + 2);
            v220 = RdpX_GetActivityIdPrefix(v216, v215, v217, v218);
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              107,
              &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v220,
              v219);
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v214 = RdpX_GetActivityIdPrefix(v213, 0, v150, v151);
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              106,
              &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v214,
              -2147418113);
          }
          RemoteAppWindow = -2147418113;
        }
        v42 = v1005;
        if ( !v1005 )
          return (unsigned int)RemoteAppWindow;
        v1005 = 0;
        goto LABEL_106;
      }
      if ( v152 == 10 )
      {
        v1022 = 0;
        v996 = 0;
        RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow((RdpRemoteAppCore *)((char *)v6 - 48), v151, &v1022);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v233 = *((_DWORD *)v5 + 2);
            v234 = RdpX_GetActivityIdPrefix(v230, v229, v231, v232);
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              109,
              &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v234,
              v233);
          }
          v42 = v1022;
          if ( v1022 )
          {
            v1022 = 0;
            goto LABEL_106;
          }
          return (unsigned int)RemoteAppWindow;
        }
        v235 = RdpRemoteAppCore::GetDesktopRemoteAppWindow((RdpRemoteAppCore *)((char *)v6 - 48), v1022);
        RdpXSPtr<RdpXInterfaceLayerManager>::operator=(&v996, v235);
        if ( v996 )
        {
          v236 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v996 + 416LL))(v996, 0);
          v238 = MapXResultToHR(v236);
          if ( v238 < 0
            && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v241 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v237, v239, v240);
            LODWORD(v944) = v238;
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              110,
              (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v241,
              (__int64)"UpdateOverlayIcon failed",
              v944);
          }
          v242 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v996 + 424LL))(v996, 0, 0);
          v244 = MapXResultToHR(v242);
          if ( v244 < 0
            && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v247 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v243, v245, v246);
            LODWORD(v944) = v244;
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              111,
              (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v247,
              (__int64)"SetOverlayDesc failed",
              v944);
          }
          v248 = v996;
          if ( v996 )
          {
            v996 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v248 + 8LL))(v248);
          }
        }
        v160 = v1022;
        if ( v1022 )
        {
          v1022 = 0;
          goto LABEL_387;
        }
      }
      return 0;
    }
    v167 = (RdpRemoteAppCore *)((char *)v6 - 48);
    v968 = 0;
    v965 = 0;
    v963 = 0;
    v964 = 0;
    v971 = (RdpRemoteAppCore *)((char *)v6 - 48);
    RemoteAppWindow = RdpRemoteAppCore::GetWndPlugin((RdpRemoteAppCore *)((char *)v6 - 48), &v963);
    if ( RemoteAppWindow < 0 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v172 = RdpX_GetActivityIdPrefix(v169, v168, v170, v171);
        v173 = 97;
        v174 = "GetWndPlugin failed";
LABEL_271:
        LODWORD(v944) = RemoteAppWindow;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v173,
          (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v172,
          (__int64)v174,
          v944);
      }
LABEL_272:
      v175 = v964;
      if ( v964 )
      {
        v964 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v175 + 8LL))(v175);
      }
      v176 = v963;
      if ( v963 )
      {
        v963 = 0;
        (*(void (__fastcall **)(struct ITSWndPluginEx *))(*(_QWORD *)v176 + 16LL))(v176);
      }
      v177 = v965;
      if ( v965 )
      {
        v965 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v177 + 8LL))(v177);
      }
      v42 = v968;
      if ( v968 )
      {
        v968 = 0;
        goto LABEL_106;
      }
      return (unsigned int)RemoteAppWindow;
    }
    RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow(v167, *((_DWORD *)v5 + 2), &v968);
    if ( RemoteAppWindow < 0 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v182 = *((_DWORD *)v5 + 2);
        v183 = RdpX_GetActivityIdPrefix(v179, v178, v180, v181);
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v183, v182);
      }
      goto LABEL_272;
    }
    if ( *((_BYTE *)v5 + 13) )
    {
      if ( *((_WORD *)v5 + 1) < 0x14u )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_292;
        }
        v184 = RdpX_GetActivityIdPrefix(v179, v178, v180, v181);
        v185 = 99;
LABEL_291:
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v185,
          &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v184,
          -2147418113);
LABEL_292:
        RemoteAppWindow = -2147418113;
        goto LABEL_272;
      }
      RemoteAppWindow = (*(__int64 (__fastcall **)(struct ITSWndPluginEx *, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v963 + 56LL))(
                          v963,
                          *((unsigned __int8 *)v5 + 18),
                          *((unsigned __int16 *)v5 + 8),
                          &v964);
      if ( RemoteAppWindow < 0 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_272;
        }
        v172 = RdpX_GetActivityIdPrefix(v187, v186, v188, v189);
        v173 = 100;
        goto LABEL_298;
      }
    }
    else
    {
      if ( *((_WORD *)v5 + 1) < 0x24u )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_292;
        }
        v184 = RdpX_GetActivityIdPrefix(v179, v178, v180, v181);
        v185 = 101;
        goto LABEL_291;
      }
      if ( (*((_BYTE *)v5 + 19) & 2) != 0 )
      {
        LOBYTE(v181) = *((_BYTE *)v5 + 24);
        v190 = *((unsigned __int16 *)v5 + 13);
      }
      else
      {
        v190 = 0;
        LOWORD(v181) = 32;
      }
      v191 = *((unsigned int *)v5 + 7);
      v192 = v191 + *((_DWORD *)v5 + 8) + 36;
      LODWORD(v976) = (unsigned __int16)v190;
      v193 = v192 + (unsigned int)(unsigned __int16)v190;
      if ( *((unsigned __int16 *)v5 + 1) < (unsigned int)v193 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_292;
        }
        v184 = RdpX_GetActivityIdPrefix(v193, v190, v191, v181);
        v185 = 102;
        goto LABEL_291;
      }
      RemoteAppWindow = (*(__int64 (__fastcall **)(struct ITSWndPluginEx *, _QWORD, _QWORD, __int64, _DWORD, _DWORD, __int64, _DWORD, __int64, _DWORD, __int64, _DWORD, __int64 *))(*(_QWORD *)v963 + 64LL))(
                          v963,
                          *((unsigned __int8 *)v5 + 18),
                          *((unsigned __int16 *)v5 + 8),
                          v181,
                          *((unsigned __int16 *)v5 + 10),
                          *((unsigned __int16 *)v5 + 11),
                          (__int64)v5 + 36,
                          v976,
                          (__int64)v5 + (unsigned __int16)v190 + 36,
                          *((_DWORD *)v5 + 7),
                          (__int64)v5 + (unsigned __int16)v190 + v191 + 36,
                          *((_DWORD *)v5 + 8),
                          &v964);
      if ( RemoteAppWindow < 0 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_272;
        }
        v172 = RdpX_GetActivityIdPrefix(v195, v194, v196, v197);
        v173 = 103;
LABEL_298:
        v174 = "CreateCachedIcon failed";
        goto LABEL_271;
      }
      v167 = v971;
    }
    v198 = RdpRemoteAppCore::GetDesktopRemoteAppWindow(v167, v968);
    RdpXSPtr<RdpXInterfaceLayerManager>::operator=(&v965, v198);
    if ( v965 )
    {
      v200 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v965 + 416LL))(v965, v964);
      if ( v200 < 0
        && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v203 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v199, v201, v202);
        LODWORD(v944) = v200;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          104,
          (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v203,
          (__int64)"Failed to UpdateOverlayIcon",
          v944);
      }
      v204 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v965 + 424LL))(v965, 0, 0);
      v206 = MapXResultToHR(v204);
      if ( v206 < 0
        && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v209 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v205, v207, v208);
        LODWORD(v944) = v206;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          105,
          (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v209,
          (__int64)"Failed to reset the old overlay description",
          v944);
      }
    }
    v210 = v964;
    if ( v964 )
    {
      v964 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v210 + 8LL))(v210);
    }
    v211 = v963;
    if ( v963 )
    {
      v963 = 0;
      (*(void (__fastcall **)(struct ITSWndPluginEx *))(*(_QWORD *)v211 + 16LL))(v211);
    }
    v212 = v965;
    if ( v965 )
    {
      v965 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v212 + 8LL))(v212);
    }
    v160 = v968;
    if ( !v968 )
      return 0;
    v968 = 0;
    goto LABEL_387;
  }
  if ( (_DWORD)v20 == 15 )
  {
    v86 = *((unsigned __int16 *)v5 + 1);
    if ( (_WORD)v86 != 528 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v87 = RdpX_GetActivityIdPrefix(v20, v17, v18, v19);
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v87, v86);
      }
      v28 = *((unsigned __int16 *)v5 + 1);
      v29 = L"Invalid size for TS_RAIL_ORDER_GET_APPID_RESP [%d]";
      RemoteAppWindow = -2147467259;
      v30 = 2147500037LL;
      goto LABEL_1165;
    }
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v88 = *((_DWORD *)v5 + 1);
      v89 = RdpX_GetActivityIdPrefix(v20, v17, v18, v19);
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v89, v88);
    }
    v90 = CUT::PathFindFileNameW((const unsigned __int16 *)v5 + 4);
    RdpRemoteAppCore::LogRemoteAppEventF(
      (char *)v6 + 16,
      L"GetAppIdRespRailOrderReceived: WindowId=0x%x, CensoredAppId=%s",
      0,
      *((unsigned int *)v5 + 1),
      v90);
    RemoteAppWindow = RdpRemoteAppCore::UpdateAppID(
                        (RdpRemoteAppCore *)((char *)v6 - 48),
                        *((_DWORD *)v5 + 1),
                        (const unsigned __int16 *)v5 + 4);
    if ( RemoteAppWindow < 0
      && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v95 = RdpX_GetActivityIdPrefix(v92, v91, v93, v94);
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        84,
        (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
        v95,
        (__int64)"UpdateAppID failed",
        RemoteAppWindow);
    }
    return (unsigned int)RemoteAppWindow;
  }
  if ( (_DWORD)v20 == 3 )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v85 = RdpX_GetActivityIdPrefix(v20, (unsigned int)(v20 - 3), v18, v19);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v85);
    }
    RdpRemoteAppCore::OnRailOrderSysParam((RdpRemoteAppCore *)((char *)v6 - 48), v5);
    return 0;
  }
  v21 = (unsigned int)(v20 - 5);
  if ( (_DWORD)v20 == 5 )
  {
LABEL_197:
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v126 = RdpX_GetActivityIdPrefix(v20, v21, v18, v19);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v126);
    }
    LOBYTE(v21) = 3;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_RailV2ConnectionInfoDisclosure>::__private_IsEnabledPreCheck(
      `wil::Feature<__WilFeatureTraits_Feature_RailV2ConnectionInfoDisclosure>::GetImpl'::`2'::impl,
      v21);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_RailV2ConnectionInfoDisclosure>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_RailV2ConnectionInfoDisclosure>::GetImpl'::`2'::impl) )
    {
      v128 = RdpRemoteAppCore::SetV2CoreProperty((RdpRemoteAppCore *)((char *)v6 - 48), 4u);
      if ( v128 < 0
        && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v131 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v127, v129, v130);
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          68,
          (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v131,
          (__int64)"Failed to set the V2 core property",
          v128);
      }
    }
    v133 = RdpRemoteAppCore::ReceiveHandshake((RdpRemoteAppCore *)((char *)v6 - 48), v5, (unsigned int *)v6 + 43);
    if ( v133 >= 0 )
    {
      return (unsigned int)RdpRemoteAppCore::OnHandshakeOrCaps((RdpRemoteAppCore *)((char *)v6 - 48), 1);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v136 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v132, v134, v135);
        LODWORD(v941) = v133;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          69,
          (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v136,
          (__int64)"RemoteAppHandshake::ReceiveHandshake failed",
          v941);
      }
      LOBYTE(v132) = 3;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_RailV2ConnectionInfoDisclosure>::__private_IsEnabledPreCheck(
        `wil::Feature<__WilFeatureTraits_Feature_EnableRailV2>::GetImpl'::`2'::impl,
        v132);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableRailV2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnableRailV2>::GetImpl'::`2'::impl) )
        v137 = *(unsigned int (**)(void))(**((_QWORD **)v6 + 12) + 56LL);
      else
        v137 = *(unsigned int (**)(void))(**((_QWORD **)v6 + 11) + 48LL);
      return v137();
    }
  }
  if ( (_DWORD)v20 == 7 )
  {
LABEL_1134:
    v927 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v928 = RdpX_GetActivityIdPrefix(v20, WPP_GLOBAL_Control, v18, v19);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v928);
      v927 = WPP_GLOBAL_Control;
    }
    v929 = *((unsigned __int16 *)v5 + 1);
    if ( (unsigned __int16)v929 < 0x10u )
    {
      if ( v927 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v927[7] & 1) != 0 && *((_BYTE *)v927 + 25) >= 2u )
      {
        v930 = RdpX_GetActivityIdPrefix(v20, v927, v18, v19);
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v930);
      }
      RemoteAppWindow = -2147467259;
      RdpRemoteAppCore::LogRemoteAppError((char *)v6 + 16, L"TS_RAIL_ORDER_EXEC_RESULT too short", 2147500037LL, 0, 0);
      return (unsigned int)RemoteAppWindow;
    }
    v931 = *((unsigned __int16 *)v5 + 7);
    if ( v929 != v931 + 16 )
    {
      if ( v927 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v927[7] & 1) != 0 && *((_BYTE *)v927 + 25) >= 2u )
      {
        v932 = RdpX_GetActivityIdPrefix(v931 + 16, v927, v18, v19);
        WPP_SF_DLD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          72,
          &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v932,
          v929,
          v931 + 16);
      }
      RemoteAppWindow = -2147467259;
      v111 = 2147500037LL;
      v941 = (unsigned __int16 *)(*((unsigned __int16 *)v5 + 7) + 16LL);
      v112 = L"TS_RAIL_ORDER_EXEC_RESULT wrong size got[%u] expected[%u]";
      goto LABEL_1150;
    }
    memset_0(pszDest, 0, 0x208u);
    StringCopyWorkerW_0(
      pszDest,
      0x104u,
      0,
      (STRSAFE_PCNZWCH)v5 + 8,
      (unsigned __int64)*((unsigned __int16 *)v5 + 7) >> 1);
    v933 = *((_DWORD *)v5 + 2);
    v934 = (char *)v6 + 16;
    if ( *((_WORD *)v5 + 3) )
    {
      if ( v933 )
      {
        if ( v933 > 0 )
          v935 = (unsigned __int16)v933 | 0x80070000;
        else
          v935 = *((_DWORD *)v5 + 2);
      }
      else
      {
        v935 = -2147467259;
      }
      RdpRemoteAppCore::LogRemoteAppErrorF(
        v934,
        L"ExecResultRailOrderReceived_Error: ApplicationName=%s, Flags=0x%hx, Result=0x%hx, RawResult=0x%x",
        v935,
        1,
        pszDest,
        *((unsigned __int16 *)v5 + 2),
        *((unsigned __int16 *)v5 + 3),
        *((_DWORD *)v5 + 2));
    }
    else
    {
      LODWORD(cchToCopyc) = *((unsigned __int16 *)v5 + 2);
      RdpRemoteAppCore::LogRemoteAppEventF(
        v934,
        L"ExecResultRailOrderReceived: ApplicationName=%s, Flags=0x%hx, Result=0x%hx, RawResult=0x%x",
        0,
        pszDest,
        cchToCopyc,
        0,
        *((_DWORD *)v5 + 2));
    }
    return (unsigned int)RdpRemoteAppCore::OnExecResult(
                           (RdpRemoteAppCore *)((char *)v6 - 48),
                           (struct tagTS_RAIL_PDU *)((char *)v5 + 4));
  }
  v22 = (unsigned int)(v20 - 9);
  if ( (_DWORD)v20 == 9 )
  {
    v54 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v55 = *((unsigned __int16 *)v5 + 5);
      v56 = *((unsigned __int16 *)v5 + 4);
      v57 = *((_DWORD *)v5 + 1);
      v58 = RdpX_GetActivityIdPrefix(v20, v22, v18, v19);
      WPP_SF_DDDd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        73,
        &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
        v58,
        v57,
        v56,
        v55);
      v54 = WPP_GLOBAL_Control;
      v6 = v971;
    }
    v59 = *((unsigned __int16 *)v5 + 1);
    if ( (_WORD)v59 != 16 )
    {
      if ( v54 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v54[7] & 1) != 0 && *((_BYTE *)v54 + 25) >= 2u )
      {
        v60 = RdpX_GetActivityIdPrefix(v20, v22, v18, v19);
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v60, v59);
      }
      v28 = *((unsigned __int16 *)v5 + 1);
      v29 = L"Invalid size for TS_RAIL_ORDER_LOCALMOVESIZE [%d]";
      RemoteAppWindow = -2147467259;
      v30 = 2147500037LL;
      goto LABEL_1165;
    }
    LODWORD(v951) = *((__int16 *)v5 + 6);
    LODWORD(v941) = *((unsigned __int16 *)v5 + 5);
    LODWORD(cchToCopy) = *((unsigned __int16 *)v5 + 4);
    RdpRemoteAppCore::LogRemoteAppEventF(
      (char *)v6 + 16,
      L"LocalMoveSizeRailOrderReceived: WindowId=0x%x, IsStart=%hu, Type=0x%hx, X=%hi, Y=%hi",
      0,
      *((unsigned int *)v5 + 1),
      cchToCopy,
      v941,
      v951,
      *((__int16 *)v5 + 7));
    v985 = 0;
    v984 = 0;
    RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow(
                        (RdpRemoteAppCore *)((char *)v6 - 48),
                        *((_DWORD *)v5 + 1),
                        &v985);
    if ( RemoteAppWindow >= 0 )
    {
      v68 = RdpRemoteAppCore::GetDesktopRemoteAppWindow((RdpRemoteAppCore *)((char *)v6 - 48), v985);
      RdpXSPtr<RdpXInterfaceLayerManager>::operator=(&v984, v68);
      v73 = v984;
      if ( !v984 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control )
        {
          v74 = (_DWORD)v984 + 8;
          if ( ((unsigned __int8)((_BYTE)v984 + 8) & (_BYTE)WPP_GLOBAL_Control[7]) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v75 = RdpX_GetActivityIdPrefix(v70, v69, v71, v72);
            LODWORD(v943) = 1;
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v74 + 68,
              (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v75,
              (__int64)"spDesktopRemoteAppWindow",
              v943);
            v73 = v984;
          }
        }
        RemoteAppWindow = 1;
        if ( !v73 )
          goto LABEL_104;
        v984 = 0;
        v67 = *v73;
        goto LABEL_103;
      }
      if ( *((_WORD *)v5 + 4) )
      {
        v1018 = 0;
        v76 = RemoteAppMoveSizeInfo::CreateInstance((char *)v5 + 4, &v1018);
        RemoteAppWindow = MapXResultToHR(v76);
        if ( RemoteAppWindow >= 0 )
        {
          (*(void (__fastcall **)(__int64 *, __int64))(*v984 + 392))(v984, v1018);
        }
        else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
               && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v81 = RdpX_GetActivityIdPrefix(v78, v77, v79, v80);
          LODWORD(v943) = RemoteAppWindow;
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            77,
            (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
            v81,
            (__int64)"Failed to create RemoteAppMoveSizeInfo",
            v943);
        }
        v82 = v1018;
        if ( v1018 )
        {
          v1018 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 8LL))(v82);
        }
      }
      else
      {
        if ( *((_WORD *)v5 + 5) == 9 )
        {
          v83 = *((__int16 *)v5 + 7);
          v84 = (unsigned int)*((__int16 *)v5 + 6);
        }
        else
        {
          v83 = -1;
          v84 = 0xFFFFFFFFLL;
        }
        (*(void (__fastcall **)(__int64 *, __int64, _QWORD, __int64, int))(*v984 + 400))(v984, 1, 0, v84, v83);
      }
    }
    else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
           && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v65 = RdpX_GetActivityIdPrefix(v62, v61, v63, v64);
      LODWORD(v943) = RemoteAppWindow;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        75,
        (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
        v65,
        (__int64)"Failed to find window",
        v943);
    }
    v66 = v984;
    if ( !v984 )
    {
LABEL_104:
      v42 = v985;
      if ( !v985 )
        return (unsigned int)RemoteAppWindow;
      v985 = 0;
      goto LABEL_106;
    }
    v984 = 0;
    v67 = *v66;
LABEL_103:
    (*(void (**)(void))(v67 + 8))();
    goto LABEL_104;
  }
  v23 = (unsigned int)(v20 - 10);
  if ( (_DWORD)v20 != 10 )
  {
    if ( (_DWORD)v20 == 13 )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v25 = RdpX_GetActivityIdPrefix(v20, v23, v18, v19);
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v25);
        v24 = WPP_GLOBAL_Control;
      }
      v26 = *((unsigned __int16 *)v5 + 1);
      if ( (_WORD)v26 != 8 )
      {
        if ( v24 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v24[7] & 1) != 0 && *((_BYTE *)v24 + 25) >= 2u )
        {
          v27 = RdpX_GetActivityIdPrefix(v20, v23, v18, v19);
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v27, v26);
        }
        v28 = *((unsigned __int16 *)v5 + 1);
        v29 = L"Invalid size for TS_RAIL_ORDER_LANGBARINFO [%d]";
        RemoteAppWindow = -2147467259;
        v30 = 2147500037LL;
LABEL_1165:
        LODWORD(cchToCopy) = v28;
        RdpRemoteAppCore::LogRemoteAppErrorF((char *)v6 + 16, v29, v30, 0, cchToCopy);
        return (unsigned int)RemoteAppWindow;
      }
      RdpRemoteAppCore::LogRemoteAppEventF(
        (char *)v6 + 16,
        L"LangBarInfoRailOrderReceived: Status=0x%x",
        0,
        *((unsigned int *)v5 + 1));
      v31 = *((_QWORD *)v6 + 17);
      if ( v31 )
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v31 + 24LL))(v31, *((unsigned int *)v5 + 1));
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
        *(unsigned __int16 *)v5);
    }
    v28 = *(unsigned __int16 *)v5;
    v29 = L"Unknown orderType[0x%x]";
    RemoteAppWindow = -2147418113;
    v30 = 2147549183LL;
    goto LABEL_1165;
  }
  v32 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v33 = *((_DWORD *)v5 + 1);
    v34 = RdpX_GetActivityIdPrefix(v20, v23, v18, v19);
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v34, v33);
    v32 = WPP_GLOBAL_Control;
  }
  v35 = *((unsigned __int16 *)v5 + 1);
  if ( (_WORD)v35 != 24 )
  {
    if ( v32 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v32[7] & 1) != 0 && *((_BYTE *)v32 + 25) >= 2u )
    {
      v36 = RdpX_GetActivityIdPrefix(v20, v23, v18, v19);
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v36, v35);
    }
    v28 = *((unsigned __int16 *)v5 + 1);
    v29 = L"Invalid size for TS_RAIL_ORDER_MINMAXINFO [%d]";
    RemoteAppWindow = -2147467259;
    v30 = 2147500037LL;
    goto LABEL_1165;
  }
  LODWORD(cchToCopy) = *((__int16 *)v5 + 4);
  RdpRemoteAppCore::LogRemoteAppEventF(
    (char *)v971 + 16,
    L"MinMaxInfoRailOrderReceived: WindowId=0x%x, MaxWidth=%hi, MaxHeight=%hi, MaxPosX=%hi, MaxPosY=%hi, MinTrackWidth=%hi"
     ", MinTrackHeight=%hi, MaxTrackWidth=%hi, MaxTraceHeight=%hi",
    0,
    *((unsigned int *)v5 + 1),
    cchToCopy,
    *((__int16 *)v5 + 5),
    *((__int16 *)v5 + 6),
    *((__int16 *)v5 + 7),
    *((__int16 *)v5 + 8),
    *((__int16 *)v5 + 9),
    *((__int16 *)v5 + 10),
    *((__int16 *)v5 + 11));
  v1004 = 0;
  v1003 = 0;
  RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow(
                      (RdpRemoteAppCore *)((char *)v971 - 48),
                      *((_DWORD *)v5 + 1),
                      &v1004);
  if ( RemoteAppWindow < 0 )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v41 = RdpX_GetActivityIdPrefix(v38, v37, v39, v40);
      LODWORD(v942) = RemoteAppWindow;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        80,
        (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
        v41,
        (__int64)"Failed to find window",
        v942);
    }
LABEL_71:
    v42 = v1004;
    if ( !v1004 )
      return (unsigned int)RemoteAppWindow;
    v1004 = 0;
LABEL_106:
    (*(void (__fastcall **)(struct RdpXInterfaceRemoteAppWindow *))(*(_QWORD *)v42 + 8LL))(v42);
    return (unsigned int)RemoteAppWindow;
  }
  v43 = RdpRemoteAppCore::GetDesktopRemoteAppWindow((RdpRemoteAppCore *)((char *)v971 - 48), v1004);
  RdpXSPtr<RdpXInterfaceLayerManager>::operator=(&v1003, v43);
  v47 = v1003;
  if ( !v1003 )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control )
    {
      v48 = v1003 + 8;
      if ( ((unsigned __int8)(v1003 + 8) & (_BYTE)WPP_GLOBAL_Control[7]) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v49 = RdpX_GetActivityIdPrefix(v45, v44, 0, v46);
        LODWORD(v942) = 1;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v48 + 73,
          (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v49,
          (__int64)"spDesktopRemoteAppWindow",
          v942);
        v47 = v1003;
      }
    }
    RemoteAppWindow = 1;
    if ( v47 )
    {
      v1003 = 0;
      (*(void (**)(void))(*(_QWORD *)v47 + 8LL))();
    }
    goto LABEL_71;
  }
  v50 = 0;
  v1036 = 0;
  memset(v1035, 0, sizeof(v1035));
  do
  {
    v51 = *((__int16 *)v5 + (unsigned int)v50 + 4);
    v52 = 4 * v50++ + 8;
    *(_DWORD *)((char *)v1035 + v52) = v51;
  }
  while ( v50 < 8 );
  (*(void (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)v47 + 408LL))(v47, v1035);
  v53 = v1003;
  if ( v1003 )
  {
    v1003 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 8LL))(v53);
  }
  v42 = v1004;
  if ( v1004 )
  {
    v1004 = 0;
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
