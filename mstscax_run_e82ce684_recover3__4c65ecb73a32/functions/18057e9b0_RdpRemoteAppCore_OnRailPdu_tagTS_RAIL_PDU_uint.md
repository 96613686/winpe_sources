# RdpRemoteAppCore::OnRailPdu(tagTS_RAIL_PDU *,uint)

- ea: `0x18057e9b0`
- end: `0x18058536b`
- name: `?OnRailPdu@RdpRemoteAppCore@@UEAAJPEAUtagTS_RAIL_PDU@@I@Z`
- size: `27067`
- prototype: `__int64 __fastcall(RdpRemoteAppCore *this, struct tagTS_RAIL_PDU *, __int64, __int64)`
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
// Hidden C++ exception states: #wind=1
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
  __int64 v121; // rdx
  __int64 v122; // rcx
  HKEY v123; // rax
  unsigned int v124; // eax
  int v125; // ebx
  unsigned int v126; // eax
  unsigned int v127; // eax
  __int64 v128; // rdx
  int v129; // ebx
  __int64 v130; // r8
  __int64 v131; // r9
  int v132; // eax
  __int64 v133; // rdx
  int v134; // esi
  __int64 v135; // r8
  __int64 v136; // r9
  int v137; // eax
  unsigned int (*v138)(void); // rax
  HKEY v140; // rax
  unsigned int v141; // eax
  int v142; // ebx
  unsigned int v143; // eax
  int v144; // edx
  bool v145; // zf
  int v146; // r8d
  HKEY v147; // rax
  unsigned int v148; // eax
  int v149; // ebx
  unsigned int v150; // eax
  __int64 v151; // r8
  __int64 v152; // r9
  int v153; // ecx
  __int64 v154; // rcx
  __int64 v155; // rdx
  __int64 v156; // rcx
  __int64 v157; // r8
  __int64 v158; // r9
  int v159; // ebx
  unsigned int v160; // eax
  struct RdpXInterfaceRemoteAppWindow *v161; // rcx
  __int64 v162; // rdx
  __int64 v163; // rcx
  __int64 v164; // r8
  __int64 v165; // r9
  int v166; // ebx
  unsigned int v167; // eax
  RdpRemoteAppCore *v168; // rbx
  __int64 v169; // rdx
  __int64 v170; // rcx
  __int64 v171; // r8
  __int64 v172; // r9
  int v173; // eax
  int v174; // edx
  const char *v175; // rcx
  __int64 v176; // rcx
  struct ITSWndPluginEx *v177; // rcx
  __int64 v178; // rcx
  __int64 v179; // rdx
  __int64 v180; // rcx
  __int64 v181; // r8
  __int64 v182; // r9
  int v183; // ebx
  unsigned int v184; // eax
  unsigned int v185; // eax
  __int64 v186; // rdx
  __int64 v187; // rdx
  __int64 v188; // rcx
  __int64 v189; // r8
  __int64 v190; // r9
  __int64 v191; // rdx
  __int64 v192; // r8
  int v193; // eax
  __int64 v194; // rcx
  __int64 v195; // rdx
  __int64 v196; // rcx
  __int64 v197; // r8
  __int64 v198; // r9
  struct RdpInterfaceDesktopRemoteAppWindow *v199; // rax
  __int64 v200; // rdx
  int v201; // ebx
  __int64 v202; // r8
  __int64 v203; // r9
  int v204; // eax
  unsigned int v205; // eax
  __int64 v206; // rdx
  int v207; // ebx
  __int64 v208; // r8
  __int64 v209; // r9
  int v210; // eax
  __int64 v211; // rcx
  struct ITSWndPluginEx *v212; // rcx
  __int64 v213; // rcx
  __int64 v214; // rcx
  unsigned int v215; // eax
  __int64 v216; // rdx
  __int64 v217; // rcx
  __int64 v218; // r8
  __int64 v219; // r9
  int v220; // ebx
  unsigned int v221; // eax
  struct RdpInterfaceDesktopRemoteAppWindow *v222; // rax
  __int64 v223; // rcx
  unsigned int v224; // eax
  __int64 v225; // rdx
  int v226; // ebx
  __int64 v227; // r8
  __int64 v228; // r9
  int v229; // eax
  __int64 v230; // rdx
  __int64 v231; // rcx
  __int64 v232; // r8
  __int64 v233; // r9
  int v234; // ebx
  unsigned int v235; // eax
  struct RdpInterfaceDesktopRemoteAppWindow *v236; // rax
  unsigned int v237; // eax
  __int64 v238; // rdx
  int v239; // ebx
  __int64 v240; // r8
  __int64 v241; // r9
  int v242; // eax
  unsigned int v243; // eax
  __int64 v244; // rdx
  int v245; // ebx
  __int64 v246; // r8
  __int64 v247; // r9
  int v248; // eax
  __int64 v249; // rcx
  int v250; // ebx
  unsigned int v251; // eax
  int v252; // ebx
  int v253; // edi
  int v254; // eax
  const unsigned __int16 *FileNameW; // rax
  int v256; // ebx
  const unsigned __int16 *v257; // rdi
  const unsigned __int16 *v258; // rax
  RdpRemoteAppCore *v259; // rbx
  __int64 v260; // rdx
  __int64 v261; // rcx
  __int64 v262; // r8
  __int64 v263; // r9
  int v264; // ebx
  unsigned int v265; // eax
  __int64 v266; // rdx
  int updated; // edi
  __int64 v268; // r8
  __int64 v269; // r9
  int v270; // eax
  __int64 v271; // rdx
  __int64 v272; // rcx
  __int64 v273; // r8
  __int64 v274; // r9
  int v275; // eax
  __int64 v276; // rdx
  __int64 v277; // rcx
  __int64 v278; // r8
  __int64 v279; // r9
  unsigned int v280; // eax
  char *v281; // rcx
  struct RdpXInterfaceRemoteAppWindow **v282; // rax
  __int64 v283; // rdx
  __int64 v284; // rcx
  __int64 v285; // r8
  __int64 v286; // r9
  int v287; // ebx
  unsigned int v288; // eax
  struct ITSWndPluginEx **v289; // rax
  __int64 v290; // rdx
  __int64 v291; // rcx
  __int64 v292; // r8
  __int64 v293; // r9
  int v294; // eax
  int v295; // edx
  const char *v296; // rcx
  __int64 v297; // rdi
  __int64 (__fastcall *v298)(__int64, _QWORD, _QWORD, void *); // rbx
  void *v299; // rax
  __int64 v300; // rdx
  __int64 v301; // rcx
  __int64 v302; // r8
  __int64 v303; // r9
  __int64 v304; // rsi
  BOOL v305; // ebx
  __int64 (__fastcall *v306)(__int64, __int64, BOOL); // rdi
  __int64 v307; // rax
  __int64 v308; // rdx
  __int64 v309; // rcx
  __int64 v310; // r8
  __int64 v311; // r9
  __int64 v312; // rdx
  __int64 v313; // rcx
  __int64 v314; // r8
  __int64 v315; // r9
  unsigned int v316; // eax
  __int64 v317; // rdx
  struct RdpXInterfaceRemoteAppWindow **v318; // rax
  __int64 v319; // rdx
  __int64 v320; // rcx
  __int64 v321; // r8
  __int64 v322; // r9
  int v323; // ebx
  unsigned int v324; // eax
  struct ITSWndPluginEx **v325; // rax
  int WndPlugin; // eax
  __int64 v327; // rdx
  __int64 v328; // rcx
  __int64 v329; // r8
  __int64 v330; // r9
  int v331; // eax
  int v332; // edx
  const char *v333; // rcx
  unsigned __int16 v334; // r14
  int v335; // esi
  __int64 v336; // rcx
  unsigned int v337; // esi
  __int64 v338; // rdi
  __int64 v339; // rbx
  __int64 v340; // r14
  __int64 (__fastcall *v341)(__int64, _QWORD, _QWORD, __int64, _DWORD, _DWORD, char *, _DWORD, __int64, _DWORD, __int64, _DWORD, void *); // rsi
  void *v342; // rax
  __int64 v343; // r9
  __int64 v344; // rdx
  __int64 v345; // rcx
  __int64 v346; // r8
  __int64 v347; // r9
  __int64 v348; // rsi
  __int64 (__fastcall *v349)(__int64, __int64, _QWORD); // rdi
  unsigned int v350; // ebx
  __int64 v351; // rax
  __int64 v352; // rdx
  __int64 v353; // rcx
  __int64 v354; // r8
  __int64 v355; // r9
  __int64 v356; // rdx
  __int64 v357; // rcx
  __int64 v358; // r8
  __int64 v359; // r9
  unsigned int v360; // eax
  struct RdpXInterfaceRemoteAppWindow **v361; // rax
  __int64 v362; // rdx
  __int64 v363; // rcx
  __int64 v364; // r8
  __int64 v365; // r9
  int v366; // ebx
  unsigned int v367; // eax
  struct ITSWndPluginEx **v368; // rax
  __int64 v369; // rdx
  __int64 v370; // rcx
  __int64 v371; // r8
  __int64 v372; // r9
  int v373; // eax
  int v374; // edx
  const char *v375; // rcx
  __int64 v376; // rdi
  __int64 v377; // rax
  int v378; // ebx
  __int64 v379; // rax
  __int64 v380; // rdi
  __int64 (__fastcall *v381)(__int64, _QWORD); // rbx
  __int64 v382; // rax
  unsigned int v383; // eax
  unsigned int v384; // eax
  __int64 v385; // rdx
  __int64 v386; // rcx
  __int64 v387; // r8
  __int64 v388; // r9
  __int64 v389; // rdx
  __int64 v390; // r8
  __int64 v391; // r9
  __int64 v392; // rcx
  unsigned int v393; // eax
  __int64 v394; // rdx
  unsigned int v395; // r14d
  __int64 v396; // rdx
  __int64 v397; // rcx
  __int64 v398; // r8
  __int64 v399; // r9
  unsigned int v400; // eax
  struct RdpXInterfaceRemoteAppWindow **v401; // rax
  __int64 v402; // rdx
  __int64 v403; // rcx
  __int64 v404; // r8
  __int64 v405; // r9
  int v406; // ebx
  unsigned int v407; // eax
  __int64 v408; // rax
  int v409; // r14d
  int v410; // esi
  int v411; // edi
  int v412; // ebx
  __int64 *v413; // rax
  __int64 v414; // rcx
  __int64 v415; // rax
  __int64 v416; // rax
  __int64 v417; // rax
  __int64 v418; // rax
  __int64 v419; // rax
  __int64 v420; // rax
  __int64 v421; // rax
  __int64 v422; // rdx
  __int64 v423; // rcx
  char *v424; // rdi
  __int64 v425; // r8
  __int64 v426; // r9
  unsigned int v427; // eax
  int v428; // esi
  RdpRemoteAppCore *v429; // r14
  __int64 v430; // rdx
  __int64 v431; // rax
  __int64 v432; // rax
  __int64 v433; // rax
  __int64 v434; // rdx
  __int64 v435; // r8
  __int64 v436; // r9
  __int64 v437; // rcx
  unsigned int v438; // eax
  __int64 v439; // rdx
  unsigned int v440; // r14d
  unsigned int v441; // eax
  struct RdpXInterfaceRemoteAppWindow **v442; // rax
  __int64 v443; // rdx
  __int64 v444; // rcx
  __int64 v445; // r8
  __int64 v446; // r9
  int v447; // ebx
  unsigned int v448; // eax
  __int64 v449; // rax
  __int64 v450; // rax
  __int64 v451; // rax
  __int64 v452; // rax
  __int64 v453; // rax
  __int64 v454; // rdx
  __int64 v455; // r8
  __int64 v456; // r9
  __int64 v457; // rcx
  unsigned int v458; // eax
  __int64 v459; // rdx
  int v460; // eax
  unsigned int v461; // r15d
  unsigned int v462; // r14d
  unsigned int v463; // eax
  struct ITSWndPluginEx **v464; // rax
  int v465; // r14d
  __int64 v466; // rdx
  __int64 v467; // rcx
  __int64 v468; // r8
  __int64 v469; // r9
  int v470; // eax
  struct RdpXInterfaceRemoteAppWindow **v471; // rax
  void *v472; // rax
  unsigned int WindowCallbacks; // eax
  __int64 v474; // rdx
  __int64 v475; // rcx
  __int64 v476; // r8
  __int64 v477; // r9
  int v478; // eax
  int v479; // edx
  const char *v480; // rcx
  void *v481; // rax
  unsigned int Object; // eax
  __int64 v483; // rdx
  __int64 v484; // rcx
  __int64 v485; // r8
  __int64 v486; // r9
  __int64 v487; // rdi
  __int64 (__fastcall *v488)(__int64, void *); // rbx
  void *v489; // rax
  __int64 v490; // rdx
  __int64 v491; // rcx
  __int64 v492; // r8
  __int64 v493; // r9
  __int64 v494; // rdi
  __int64 (__fastcall *v495)(__int64, __int64); // rbx
  __int64 v496; // rax
  unsigned int v497; // eax
  __int64 v498; // rdx
  __int64 v499; // rcx
  __int64 v500; // r8
  __int64 v501; // r9
  __int64 v502; // r15
  __int64 (__fastcall *v503)(__int64, __int64, _QWORD, __int64, __int128 *, void *); // r14
  void *v504; // rbx
  __int64 v505; // rax
  unsigned int v506; // esi
  __int64 v507; // rdi
  __int64 v508; // rax
  unsigned int v509; // eax
  __int64 v510; // rdx
  __int64 v511; // rcx
  __int64 v512; // r8
  __int64 v513; // r9
  __int64 v514; // rdi
  __int64 (__fastcall *v515)(__int64, bool); // rbx
  __int64 v516; // rax
  int v517; // eax
  unsigned int v518; // eax
  __int64 v519; // rax
  __int64 v520; // rax
  __int64 v521; // rax
  __int64 v522; // rax
  __int64 v523; // rax
  __int64 v524; // rax
  int v525; // r15d
  int v526; // r14d
  int v527; // ebx
  __int64 *v528; // rax
  __int64 v529; // rcx
  __int64 v530; // rax
  __int64 v531; // rax
  __int64 v532; // rax
  __int64 v533; // rdx
  __int64 v534; // rcx
  char *v535; // rbx
  __int64 v536; // r8
  __int64 v537; // r9
  unsigned int v538; // eax
  __int64 v539; // rdx
  __int64 v540; // rax
  __int64 v541; // rax
  __int64 v542; // rax
  __int64 v543; // rdi
  void (__fastcall *v544)(__int64, _QWORD); // rbx
  __int64 v545; // rax
  unsigned int v546; // eax
  __int64 v547; // rax
  __int64 v548; // rdx
  __int64 v549; // rcx
  __int64 v550; // r8
  __int64 v551; // r9
  unsigned int v552; // eax
  struct RdpXInterfaceRemoteAppWindow **v553; // rax
  __int64 v554; // rdx
  __int64 v555; // rcx
  __int64 v556; // r8
  __int64 v557; // r9
  int v558; // ebx
  unsigned int v559; // eax
  int v560; // ebx
  unsigned int v561; // eax
  __int64 v562; // rax
  int v563; // ebx
  unsigned int v564; // eax
  __int64 v565; // rax
  __int64 v566; // rdx
  __int64 v567; // rdx
  __int64 v568; // rcx
  __int64 v569; // r8
  __int64 v570; // r9
  unsigned int v571; // eax
  char *v572; // rcx
  struct ITSWndPluginEx **v573; // rax
  __int64 v574; // rdx
  __int64 v575; // rcx
  __int64 v576; // r8
  __int64 v577; // r9
  int v578; // eax
  unsigned int v579; // eax
  __int64 v580; // rax
  __int64 v581; // rdx
  HKEY v582; // rax
  unsigned int v583; // eax
  unsigned int v584; // eax
  __int64 v585; // rax
  RdpRemoteAppCore *v586; // rbx
  __int64 v587; // rax
  unsigned int v588; // r15d
  __int64 v589; // rdi
  __int64 (__fastcall *v590)(__int64, _QWORD, void *); // rbx
  void *v591; // rax
  __int64 v592; // rdx
  __int64 v593; // rcx
  int v594; // ebx
  __int64 v595; // r8
  __int64 v596; // r9
  __int64 v597; // rax
  unsigned int v598; // eax
  __int64 v599; // rax
  unsigned int v600; // eax
  __int64 v601; // rax
  __int64 v602; // rdx
  __int64 v603; // rcx
  __int64 v604; // r8
  __int64 v605; // r9
  unsigned int v606; // eax
  __int64 v607; // rdx
  unsigned int v608; // eax
  unsigned int v609; // esi
  wchar_t *v610; // rcx
  size_t v611; // rdx
  unsigned int v612; // eax
  int v613; // esi
  unsigned int v614; // ebx
  __int64 v615; // r9
  const unsigned __int16 *v616; // r8
  __int64 v617; // rdx
  __int64 v618; // rcx
  __int64 v619; // r8
  __int64 v620; // r9
  int v621; // eax
  struct ITSWndPluginEx **v622; // rax
  __int64 v623; // rdx
  __int64 v624; // rcx
  __int64 v625; // r8
  __int64 v626; // r9
  int v627; // eax
  unsigned int v628; // ebx
  __int64 v629; // rax
  __int64 v630; // rdx
  __int64 v631; // rcx
  __int64 v632; // r8
  __int64 v633; // r9
  unsigned int v634; // eax
  __int64 v635; // rdx
  char *v636; // rcx
  struct ITSWndPluginEx **v637; // rax
  __int64 v638; // rdx
  __int64 v639; // rcx
  __int64 v640; // r8
  __int64 v641; // r9
  int v642; // eax
  int v643; // edx
  const char *v644; // rcx
  __int64 v645; // rdi
  __int64 (__fastcall *v646)(__int64, _QWORD, _QWORD, void *); // rbx
  void *v647; // rax
  __int64 v648; // rdx
  __int64 v649; // rcx
  __int64 v650; // r8
  __int64 v651; // r9
  __int64 v652; // rax
  __int64 v653; // rax
  struct RdpXInterfaceShellNotifyInformation *v654; // rbx
  __int64 v655; // rax
  unsigned int v656; // eax
  __int64 v657; // rdx
  __int64 v658; // rcx
  __int64 v659; // r8
  __int64 v660; // r9
  __int64 v661; // rcx
  __int64 v662; // r8
  __int64 v663; // r9
  __int64 v664; // rdx
  unsigned int v665; // eax
  __int64 v666; // rdx
  __int64 v667; // rcx
  unsigned int v668; // esi
  struct ITSWndPluginEx **v669; // rax
  __int64 v670; // rdx
  __int64 v671; // rcx
  __int64 v672; // r8
  __int64 v673; // r9
  int v674; // eax
  int v675; // edx
  const char *v676; // rcx
  __int64 v677; // rdi
  __int64 (__fastcall *v678)(__int64, _QWORD, _QWORD, void *); // rbx
  void *v679; // rax
  __int64 v680; // rdx
  __int64 v681; // rcx
  __int64 v682; // r8
  __int64 v683; // r9
  __int64 v684; // rax
  __int64 v685; // rbx
  char *v686; // r14
  void *v687; // rax
  unsigned int ConstXChar16StringWithSpecifiedSize; // eax
  __int64 v689; // rdx
  __int64 v690; // rcx
  __int64 v691; // r8
  __int64 v692; // r9
  int v693; // eax
  char *v694; // r15
  void *v695; // rax
  unsigned int v696; // eax
  __int64 v697; // rdx
  __int64 v698; // rcx
  __int64 v699; // r8
  __int64 v700; // r9
  int v701; // eax
  int v702; // edx
  const char *v703; // rcx
  const wchar_t *v704; // rbx
  __int64 v705; // rax
  const wchar_t *v706; // rsi
  __int64 v707; // rax
  __int64 v708; // rax
  __int64 v709; // rdx
  __int64 v710; // rcx
  __int64 v711; // r8
  __int64 v712; // r9
  struct RdpXInterfaceShellNotifyInformation *v713; // rbx
  __int64 v714; // rax
  unsigned int v715; // eax
  __int64 v716; // rdx
  __int64 v717; // rcx
  __int64 v718; // r8
  __int64 v719; // r9
  __int64 v720; // rdx
  __int64 v721; // r8
  __int64 v722; // r9
  __int64 v723; // rcx
  unsigned int v724; // eax
  __int64 v725; // rdx
  unsigned int v726; // r14d
  struct ITSWndPluginEx **v727; // rax
  __int64 v728; // rdx
  __int64 v729; // rcx
  __int64 v730; // r8
  __int64 v731; // r9
  int v732; // eax
  int v733; // edx
  const char *v734; // rcx
  __int64 v735; // rdi
  __int64 (__fastcall *v736)(__int64, _QWORD, _QWORD, void *); // rbx
  void *v737; // rax
  int v738; // eax
  __int64 v739; // rdx
  __int64 v740; // rcx
  __int64 v741; // r8
  __int64 v742; // r9
  unsigned __int16 v743; // di
  __int64 v744; // rax
  __int64 v745; // rax
  __int64 v746; // rdx
  __int64 v747; // rcx
  __int64 v748; // r8
  __int64 v749; // r9
  int v750; // eax
  int v751; // edx
  const char *v752; // rcx
  void *v753; // rax
  unsigned int v754; // eax
  __int64 v755; // rdx
  __int64 v756; // rcx
  __int64 v757; // r8
  __int64 v758; // r9
  __int64 v759; // rax
  __int64 v760; // rdx
  __int64 v761; // rcx
  __int64 v762; // r8
  __int64 v763; // r9
  __int64 v764; // rdx
  __int64 v765; // rcx
  __int64 v766; // r8
  __int64 v767; // r9
  __int64 v768; // rsi
  unsigned int v769; // eax
  unsigned int v770; // ebx
  RdpRemoteAppCore *v771; // r14
  unsigned int v772; // eax
  __int64 v773; // rdx
  int v774; // r15d
  __int64 v775; // rax
  const wchar_t *v776; // rbx
  __int64 v777; // rdi
  __int64 (__fastcall *v778)(__int64, _QWORD, _QWORD, void *); // rbx
  void *v779; // rax
  __int64 v780; // rdx
  __int64 v781; // rcx
  __int64 v782; // r8
  __int64 v783; // r9
  int v784; // eax
  int v785; // edx
  const char *v786; // rcx
  unsigned int v787; // ebx
  __int64 v788; // rdx
  __int64 v789; // r8
  __int64 v790; // rcx
  int v791; // eax
  unsigned int v792; // ebx
  __int64 v793; // rax
  const wchar_t *v794; // rbx
  __int64 v795; // rdi
  __int64 (__fastcall *v796)(__int64, _QWORD, _QWORD, char *, _DWORD, _DWORD, char *, int, RdpRemoteAppCore *, _DWORD, char *, _DWORD, void *); // rbx
  void *v797; // rax
  char *v798; // r9
  __int64 v799; // rdx
  __int64 v800; // rcx
  __int64 v801; // r8
  __int64 v802; // r9
  __int64 v803; // rdi
  __int64 (__fastcall *v804)(__int64, __int64); // rbx
  __int64 v805; // rax
  __int64 v806; // rdx
  __int64 v807; // rcx
  __int64 v808; // r8
  __int64 v809; // r9
  __int64 v810; // rax
  const wchar_t *v811; // rbx
  __int64 v812; // rax
  struct RdpXInterfaceShellNotifyInformation *v813; // rbx
  __int64 v814; // rax
  unsigned int v815; // eax
  __int64 v816; // rdx
  __int64 v817; // rcx
  __int64 v818; // r8
  __int64 v819; // r9
  __int64 v820; // rdx
  __int64 v821; // r8
  __int64 v822; // r9
  __int64 v823; // rcx
  unsigned int v824; // eax
  __int64 v825; // rdx
  unsigned int v826; // r15d
  struct ITSWndPluginEx **v827; // rax
  __int64 v828; // rdx
  __int64 v829; // rcx
  __int64 v830; // r8
  __int64 v831; // r9
  int v832; // eax
  int v833; // edx
  const char *v834; // rcx
  __int64 v835; // rdi
  int (__fastcall *v836)(__int64, _QWORD, _QWORD, void *); // rbx
  void *v837; // rax
  __int64 v838; // rdx
  __int64 v839; // rcx
  __int64 v840; // r8
  __int64 v841; // r9
  __int64 v842; // rdi
  __int64 (__fastcall *v843)(__int64, _QWORD, _QWORD, void *); // rbx
  void *v844; // rax
  __int64 v845; // rdx
  __int64 v846; // rcx
  __int64 v847; // r8
  __int64 v848; // r9
  __int64 v849; // rax
  int v850; // ebx
  int v851; // edi
  unsigned int v852; // eax
  __int64 v853; // rax
  __int64 v854; // rax
  __int64 v855; // rax
  __int64 v856; // rax
  __int64 v857; // rax
  __int64 v858; // rdx
  __int64 v859; // rcx
  __int64 v860; // r8
  __int64 v861; // r9
  int v862; // eax
  int v863; // edx
  const char *v864; // rcx
  void *v865; // rax
  unsigned int v866; // eax
  __int64 v867; // rdx
  __int64 v868; // rcx
  __int64 v869; // r8
  __int64 v870; // r9
  __int64 v871; // rax
  __int64 v872; // rdx
  __int64 v873; // rcx
  __int64 v874; // r8
  __int64 v875; // r9
  __int64 v876; // rdx
  __int64 v877; // rcx
  __int64 v878; // r8
  __int64 v879; // r9
  __int64 v880; // rsi
  unsigned int v881; // eax
  unsigned int v882; // edi
  RdpRemoteAppCore *v883; // r15
  unsigned int v884; // eax
  __int64 v885; // rdx
  __int64 v886; // rax
  const wchar_t *v887; // rbx
  __int64 v888; // rdi
  __int64 (__fastcall *v889)(__int64, _QWORD, _QWORD, void *); // rbx
  void *v890; // rax
  __int64 v891; // rdx
  __int64 v892; // rcx
  __int64 v893; // r8
  __int64 v894; // r9
  int v895; // eax
  int v896; // edx
  const char *v897; // rcx
  unsigned int v898; // edi
  __int64 v899; // r9
  __int64 v900; // r8
  __int64 v901; // rcx
  unsigned int v902; // edi
  __int64 v903; // rax
  const wchar_t *v904; // rbx
  __int64 v905; // rdi
  __int64 (__fastcall *v906)(__int64, _QWORD, _QWORD, __int64, _DWORD, _DWORD, char *, _DWORD, __int64, _DWORD, __int64, _DWORD, void *); // rbx
  void *v907; // rax
  __int64 v908; // r9
  __int64 v909; // rdx
  __int64 v910; // rcx
  __int64 v911; // r8
  __int64 v912; // r9
  __int64 v913; // rdi
  __int64 (__fastcall *v914)(__int64, __int64); // rbx
  __int64 v915; // rax
  __int64 v916; // rdx
  __int64 v917; // rcx
  __int64 v918; // r8
  __int64 v919; // r9
  __int64 v920; // rax
  const wchar_t *v921; // rbx
  struct RdpXInterfaceShellNotifyInformation *v922; // rbx
  __int64 v923; // rax
  unsigned int v924; // eax
  __int64 v925; // rdx
  __int64 v926; // rcx
  __int64 v927; // r8
  __int64 v928; // r9
  HKEY v929; // rdx
  unsigned int v930; // eax
  __int64 v931; // rsi
  unsigned int v932; // eax
  __int64 v933; // r15
  unsigned int v934; // eax
  int v935; // edx
  char *v936; // rcx
  unsigned int v937; // esi
  size_t cchToCopy; // [rsp+20h] [rbp-120h]
  size_t cchToCopya; // [rsp+20h] [rbp-120h]
  size_t cchToCopyb; // [rsp+20h] [rbp-120h]
  size_t cchToCopyc; // [rsp+20h] [rbp-120h]
  unsigned __int16 *v943; // [rsp+28h] [rbp-118h]
  unsigned __int16 *v944; // [rsp+28h] [rbp-118h]
  unsigned __int16 *v945; // [rsp+28h] [rbp-118h]
  unsigned __int16 *v946; // [rsp+28h] [rbp-118h]
  unsigned __int16 *v947; // [rsp+28h] [rbp-118h]
  unsigned __int16 *v948; // [rsp+28h] [rbp-118h]
  unsigned __int16 *v949; // [rsp+28h] [rbp-118h]
  unsigned __int16 *v950; // [rsp+28h] [rbp-118h]
  unsigned __int16 *v951; // [rsp+28h] [rbp-118h]
  int v952; // [rsp+28h] [rbp-118h]
  __int64 v953; // [rsp+30h] [rbp-110h]
  __int64 v954; // [rsp+30h] [rbp-110h]
  __int64 v955; // [rsp+30h] [rbp-110h]
  __int64 v956; // [rsp+38h] [rbp-108h]
  __int64 v957; // [rsp+38h] [rbp-108h]
  __int64 v958; // [rsp+40h] [rbp-100h]
  __int64 v959; // [rsp+40h] [rbp-100h]
  char v960[8]; // [rsp+C0h] [rbp-80h] BYREF
  char v961[8]; // [rsp+C8h] [rbp-78h] BYREF
  char v962[8]; // [rsp+D0h] [rbp-70h] BYREF
  int v963; // [rsp+D8h] [rbp-68h]
  char v964[8]; // [rsp+E0h] [rbp-60h] BYREF
  struct ITSWndPluginEx *v965; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v966; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v967; // [rsp+F8h] [rbp-48h] BYREF
  char v968[8]; // [rsp+100h] [rbp-40h] BYREF
  char v969[8]; // [rsp+108h] [rbp-38h] BYREF
  struct RdpXInterfaceRemoteAppWindow *v970; // [rsp+110h] [rbp-30h] BYREF
  char v971[8]; // [rsp+118h] [rbp-28h] BYREF
  _BYTE v972[16]; // [rsp+120h] [rbp-20h] BYREF
  RdpRemoteAppCore *v973; // [rsp+130h] [rbp-10h] BYREF
  int v974; // [rsp+138h] [rbp-8h]
  int v975; // [rsp+13Ch] [rbp-4h]
  char v976[8]; // [rsp+140h] [rbp+0h] BYREF
  char v977[8]; // [rsp+148h] [rbp+8h] BYREF
  __int64 v978; // [rsp+150h] [rbp+10h] BYREF
  int v979; // [rsp+158h] [rbp+18h]
  int v980; // [rsp+15Ch] [rbp+1Ch]
  char v981[8]; // [rsp+160h] [rbp+20h] BYREF
  char v982[8]; // [rsp+168h] [rbp+28h] BYREF
  unsigned int v983; // [rsp+170h] [rbp+30h]
  int v984; // [rsp+174h] [rbp+34h]
  int v985; // [rsp+178h] [rbp+38h]
  __int64 *v986; // [rsp+180h] [rbp+40h] BYREF
  struct RdpXInterfaceRemoteAppWindow *v987; // [rsp+188h] [rbp+48h] BYREF
  char v988[8]; // [rsp+190h] [rbp+50h] BYREF
  char v989[8]; // [rsp+198h] [rbp+58h] BYREF
  char v990[8]; // [rsp+1A0h] [rbp+60h] BYREF
  char v991[8]; // [rsp+1A8h] [rbp+68h] BYREF
  char v992[8]; // [rsp+1B0h] [rbp+70h] BYREF
  __int64 v993; // [rsp+1B8h] [rbp+78h] BYREF
  struct RdpXInterfaceRemoteAppWindow *v994; // [rsp+1C0h] [rbp+80h] BYREF
  char v995[8]; // [rsp+1C8h] [rbp+88h] BYREF
  char v996[8]; // [rsp+1D0h] [rbp+90h] BYREF
  char v997[8]; // [rsp+1D8h] [rbp+98h] BYREF
  __int64 v998; // [rsp+1E0h] [rbp+A0h] BYREF
  char v999[8]; // [rsp+1E8h] [rbp+A8h] BYREF
  char v1000[8]; // [rsp+1F0h] [rbp+B0h] BYREF
  char v1001[8]; // [rsp+1F8h] [rbp+B8h] BYREF
  char v1002[8]; // [rsp+200h] [rbp+C0h] BYREF
  char v1003[8]; // [rsp+208h] [rbp+C8h] BYREF
  char v1004[8]; // [rsp+210h] [rbp+D0h] BYREF
  __int64 v1005; // [rsp+218h] [rbp+D8h] BYREF
  struct RdpXInterfaceRemoteAppWindow *v1006; // [rsp+220h] [rbp+E0h] BYREF
  struct RdpXInterfaceRemoteAppWindow *v1007; // [rsp+228h] [rbp+E8h] BYREF
  char v1008[8]; // [rsp+230h] [rbp+F0h] BYREF
  char v1009[8]; // [rsp+238h] [rbp+F8h] BYREF
  int v1010; // [rsp+240h] [rbp+100h]
  int v1011; // [rsp+244h] [rbp+104h]
  int v1012; // [rsp+248h] [rbp+108h]
  int v1013; // [rsp+24Ch] [rbp+10Ch]
  unsigned int v1014; // [rsp+250h] [rbp+110h]
  int v1015; // [rsp+254h] [rbp+114h]
  int v1016; // [rsp+258h] [rbp+118h]
  char v1017[8]; // [rsp+260h] [rbp+120h] BYREF
  char v1018[8]; // [rsp+268h] [rbp+128h] BYREF
  char v1019[8]; // [rsp+270h] [rbp+130h] BYREF
  __int64 v1020; // [rsp+278h] [rbp+138h] BYREF
  __int64 v1021; // [rsp+280h] [rbp+140h] BYREF
  struct RdpXInterfaceRemoteAppWindow *v1022; // [rsp+288h] [rbp+148h] BYREF
  struct RdpXInterfaceRemoteAppWindow *v1023; // [rsp+290h] [rbp+150h] BYREF
  struct RdpXInterfaceRemoteAppWindow *v1024; // [rsp+298h] [rbp+158h] BYREF
  char v1025[8]; // [rsp+2A0h] [rbp+160h] BYREF
  struct RdpXInterfaceRemoteAppWindow *v1026; // [rsp+2A8h] [rbp+168h] BYREF
  char v1027[8]; // [rsp+2B0h] [rbp+170h] BYREF
  unsigned __int16 *v1028; // [rsp+2B8h] [rbp+178h] BYREF
  unsigned __int64 v1029; // [rsp+2C0h] [rbp+180h] BYREF
  _DWORD v1030[2]; // [rsp+2C8h] [rbp+188h] BYREF
  int v1031; // [rsp+2D0h] [rbp+190h]
  int v1032; // [rsp+2D4h] [rbp+194h]
  __int128 v1033; // [rsp+2D8h] [rbp+198h] BYREF
  _DWORD v1034[4]; // [rsp+2E8h] [rbp+1A8h] BYREF
  _DWORD v1035[4]; // [rsp+2F8h] [rbp+1B8h] BYREF
  __int128 v1036; // [rsp+308h] [rbp+1C8h] BYREF
  _OWORD v1037[2]; // [rsp+318h] [rbp+1D8h] BYREF
  __int64 v1038; // [rsp+338h] [rbp+1F8h]
  unsigned __int16 Destination[264]; // [rsp+340h] [rbp+200h] BYREF
  unsigned __int16 v1040[264]; // [rsp+550h] [rbp+410h] BYREF
  wchar_t pszDest[264]; // [rsp+760h] [rbp+620h] BYREF
  wchar_t v1042[264]; // [rsp+970h] [rbp+830h] BYREF

  v4 = a3;
  v973 = this;
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
        RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v1025);
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
          v553 = (struct RdpXInterfaceRemoteAppWindow **)CacCommon::Rect<int>::Rect<int>(v1025);
          RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow(
                              (RdpRemoteAppCore *)((char *)v6 - 48),
                              *((_DWORD *)v5 + 1),
                              v553);
          if ( RemoteAppWindow >= 0 )
          {
            if ( (*((_BYTE *)v5 + 8) & 0x40) != 0 )
            {
              if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                v560 = *((unsigned __int8 *)v5 + 12);
                v561 = RdpX_GetActivityIdPrefix(v555, v554, v556, v557);
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  163,
                  &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                  v561,
                  v560);
              }
              v562 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v1025);
              (*(void (__fastcall **)(__int64, bool))(*(_QWORD *)v562 + 344LL))(v562, *((_BYTE *)v5 + 12) == 1);
            }
            if ( (*((_BYTE *)v5 + 8) & 1) != 0 )
            {
              if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                v563 = *((unsigned __int8 *)v5 + 13);
                v564 = RdpX_GetActivityIdPrefix(v555, v554, v556, v557);
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  164,
                  &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                  v564,
                  v563);
              }
              v565 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v1025);
              LOBYTE(v566) = *((_BYTE *)v5 + 13);
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v565 + 352LL))(v565, v566);
            }
          }
          else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                 && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v558 = *((_DWORD *)v5 + 1);
            v559 = RdpX_GetActivityIdPrefix(v555, v554, v556, v557);
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              162,
              &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v559,
              v558);
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v552 = RdpX_GetActivityIdPrefix(v549, v548, v550, v551);
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              161,
              &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v552,
              -2147418113);
          }
          RemoteAppWindow = -2147418113;
        }
        v281 = v1025;
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
                RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v1000);
                RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v999);
                RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v1009);
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
                      v280 = RdpX_GetActivityIdPrefix(v277, v276, v278, v279);
                      WPP_SF_Dd(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        156,
                        &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                        v280,
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
                v282 = (struct RdpXInterfaceRemoteAppWindow **)CacCommon::Rect<int>::Rect<int>(v1000);
                RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow(
                                    (RdpRemoteAppCore *)((char *)v6 - 48),
                                    *((_DWORD *)v5 + 1),
                                    v282);
                if ( RemoteAppWindow < 0 )
                {
                  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                    && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v287 = *((_DWORD *)v5 + 1);
                    v288 = RdpX_GetActivityIdPrefix(v284, v283, v285, v286);
                    WPP_SF_Dd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      157,
                      &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                      v288,
                      v287);
                  }
                  goto LABEL_434;
                }
                v289 = (struct ITSWndPluginEx **)CacCommon::Rect<int>::Rect<int>(v999);
                RemoteAppWindow = RdpRemoteAppCore::GetWndPlugin((RdpRemoteAppCore *)((char *)v6 - 48), v289);
                if ( RemoteAppWindow >= 0 )
                {
                  v297 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v999);
                  v298 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, void *))(*(_QWORD *)v297 + 56LL);
                  v299 = CacCommon::Rect<int>::Rect<int>(v1009);
                  RemoteAppWindow = v298(v297, *((unsigned __int8 *)v5 + 14), *((unsigned __int16 *)v5 + 6), v299);
                  if ( RemoteAppWindow >= 0 )
                  {
                    v304 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v1000);
                    v305 = *((_BYTE *)v5 + 15) == 1;
                    v306 = *(__int64 (__fastcall **)(__int64, __int64, BOOL))(*(_QWORD *)v304 + 88LL);
                    v307 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v1009);
                    RemoteAppWindow = v306(v304, v307, v305);
                    if ( RemoteAppWindow >= 0
                      || WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                    {
                      goto LABEL_434;
                    }
                    v294 = RdpX_GetActivityIdPrefix(v309, v308, v310, v311);
                    v295 = 160;
                    v296 = "UpdateIcon failed";
                  }
                  else
                  {
                    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                    {
                      goto LABEL_434;
                    }
                    v294 = RdpX_GetActivityIdPrefix(v301, v300, v302, v303);
                    v295 = 159;
                    v296 = "CreateCachedIcon failed";
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
                  v294 = RdpX_GetActivityIdPrefix(v291, v290, v292, v293);
                  v295 = 158;
                  v296 = "GetWndPlugin failed";
                }
                LODWORD(v948) = RemoteAppWindow;
                WPP_SF_DsD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v295,
                  (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                  v294,
                  (__int64)v296,
                  v948);
LABEL_434:
                RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v1009);
                TCntPtr<ITSViewerRecorder>::SafeRelease(v999);
                v281 = v1000;
LABEL_629:
                RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v281);
                return (unsigned int)RemoteAppWindow;
              }
              RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v997);
              RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v996);
              RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v995);
              LOWORD(v963) = 32;
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
                  v316 = RdpX_GetActivityIdPrefix(v313, v312, v314, v315);
                  v317 = 150;
LABEL_462:
                  WPP_SF_Dd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    v317,
                    &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                    v316,
                    -2147418113);
LABEL_463:
                  RemoteAppWindow = -2147418113;
LABEL_464:
                  RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v995);
                  TCntPtr<ITSViewerRecorder>::SafeRelease(v996);
                  v281 = v997;
                  goto LABEL_629;
                }
              }
              v318 = (struct RdpXInterfaceRemoteAppWindow **)CacCommon::Rect<int>::Rect<int>(v997);
              RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow(
                                  (RdpRemoteAppCore *)((char *)v6 - 48),
                                  *((_DWORD *)v5 + 1),
                                  v318);
              if ( RemoteAppWindow < 0 )
              {
                if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                  && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v323 = *((_DWORD *)v5 + 1);
                  v324 = RdpX_GetActivityIdPrefix(v320, v319, v321, v322);
                  WPP_SF_Dd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    151,
                    &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                    v324,
                    v323);
                }
                goto LABEL_464;
              }
              v325 = (struct ITSWndPluginEx **)CacCommon::Rect<int>::Rect<int>(v996);
              WndPlugin = RdpRemoteAppCore::GetWndPlugin((RdpRemoteAppCore *)((char *)v6 - 48), v325);
              RemoteAppWindow = WndPlugin;
              if ( WndPlugin >= 0 )
              {
                if ( (*((_BYTE *)v5 + 15) & 2) != 0 )
                {
                  LOBYTE(WndPlugin) = *((_BYTE *)v5 + 20);
                  v334 = *((_WORD *)v5 + 11);
                  LOWORD(v963) = WndPlugin;
                }
                else
                {
                  v334 = 0;
                }
                v335 = *((_DWORD *)v5 + 6) + 32;
                v336 = (unsigned int)v334 + *((_DWORD *)v5 + 7);
                LODWORD(v978) = v334;
                v337 = v336 + v335;
                if ( *((unsigned __int16 *)v5 + 1) < v337 )
                  RdpRemoteAppCore::LogRemoteAppError(
                    (char *)v6 + 16,
                    L"Invalid size of TS_RAIL_ORDER_WINDOW_ICON_BODY PDU",
                    2147549183LL,
                    0,
                    0);
                if ( *((unsigned __int16 *)v5 + 1) < v337 )
                {
                  if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                    || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                  {
                    goto LABEL_463;
                  }
                  v316 = RdpX_GetActivityIdPrefix(v336, v327, v329, v330);
                  v317 = 153;
                  goto LABEL_462;
                }
                LODWORD(cchToCopy) = *((unsigned __int8 *)v5 + 8);
                RdpRemoteAppCore::LogRemoteAppEventF(
                  (char *)v973 + 16,
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
                v338 = (__int64)v5 + v334 + 32;
                v339 = v338 + *((unsigned int *)v5 + 6);
                v340 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v996);
                v341 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64, _DWORD, _DWORD, char *, _DWORD, __int64, _DWORD, __int64, _DWORD, void *))(*(_QWORD *)v340 + 64LL);
                v342 = CacCommon::Rect<int>::Rect<int>(v995);
                v343 = *((unsigned __int16 *)v5 + 9);
                LOBYTE(v343) = v963;
                RemoteAppWindow = v341(
                                    v340,
                                    *((unsigned __int8 *)v5 + 14),
                                    *((unsigned __int16 *)v5 + 6),
                                    v343,
                                    *((unsigned __int16 *)v5 + 8),
                                    *((unsigned __int16 *)v5 + 9),
                                    (char *)v5 + 32,
                                    v978,
                                    v338,
                                    *((_DWORD *)v5 + 6),
                                    v339,
                                    *((_DWORD *)v5 + 7),
                                    v342);
                if ( RemoteAppWindow >= 0 )
                {
                  v348 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v997);
                  v349 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v348 + 88LL);
                  v350 = *((_BYTE *)v5 + 15) & 1;
                  v351 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v995);
                  RemoteAppWindow = v349(v348, v351, v350);
                  if ( RemoteAppWindow >= 0
                    || WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                    || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                  {
                    goto LABEL_464;
                  }
                  v331 = RdpX_GetActivityIdPrefix(v353, v352, v354, v355);
                  v332 = 155;
                  v333 = "UpdateIcon failed";
                }
                else
                {
                  if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                    || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                  {
                    goto LABEL_464;
                  }
                  v331 = RdpX_GetActivityIdPrefix(v345, v344, v346, v347);
                  v332 = 154;
                  v333 = "CreateCachedIcon failed";
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
                v331 = RdpX_GetActivityIdPrefix(v328, v327, v329, v330);
                v332 = 152;
                v333 = "GetWndPlugin failed";
              }
              LODWORD(v943) = RemoteAppWindow;
              WPP_SF_DsD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v332,
                (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                v331,
                (__int64)v333,
                v943);
              goto LABEL_464;
            }
            RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v1002);
            RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v1001);
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
                  v360 = RdpX_GetActivityIdPrefix(v357, v356, v358, v359);
                  WPP_SF_Dd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    146,
                    &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                    v360,
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
            v361 = (struct RdpXInterfaceRemoteAppWindow **)CacCommon::Rect<int>::Rect<int>(v1002);
            RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow(
                                (RdpRemoteAppCore *)((char *)v6 - 48),
                                *((_DWORD *)v5 + 1),
                                v361);
            if ( RemoteAppWindow < 0 )
            {
              if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v366 = *((_DWORD *)v5 + 1);
                v367 = RdpX_GetActivityIdPrefix(v363, v362, v364, v365);
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  147,
                  &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                  v367,
                  v366);
              }
              goto LABEL_503;
            }
            v368 = (struct ITSWndPluginEx **)CacCommon::Rect<int>::Rect<int>(v1001);
            RemoteAppWindow = RdpRemoteAppCore::GetWndPlugin((RdpRemoteAppCore *)((char *)v6 - 48), v368);
            if ( RemoteAppWindow >= 0 )
            {
              v376 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v1002);
              v377 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v1001);
              v378 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v377 + 88LL))(v377);
              if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v376 + 72LL))(v376) == v378 )
              {
                v379 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v1001);
                (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v379 + 96LL))(v379, 0);
              }
              v380 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *((char *)v973 + 128);
              v381 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v380 + 64LL);
              v382 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v1002);
              v383 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v382 + 72LL))(v382);
              v384 = v381(v380, v383);
              RemoteAppWindow = MapXResultToHR(v384);
              if ( RemoteAppWindow >= 0
                || WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_503;
              }
              v373 = RdpX_GetActivityIdPrefix(v386, v385, v387, v388);
              v374 = 149;
              v375 = "DeleteWindow failed";
            }
            else
            {
              if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_503;
              }
              v373 = RdpX_GetActivityIdPrefix(v370, v369, v371, v372);
              v374 = 148;
              v375 = "GetWndPlugin failed";
            }
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v374,
              (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v373,
              (__int64)v375,
              RemoteAppWindow);
LABEL_503:
            TCntPtr<ITSViewerRecorder>::SafeRelease(v1001);
            v281 = v1002;
            goto LABEL_629;
          }
          RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v968);
          v973 = (RdpRemoteAppCore *)((char *)v6 + 16);
          if ( *((_WORD *)v5 + 1) < 0x58u )
            RdpRemoteAppCore::LogRemoteAppError(
              (char *)v6 + 16,
              L"Invalid size of TS_RAIL_ORDER_WINDOW_GEOMETRY_BODY PDU",
              2147549183LL,
              0,
              0);
          v392 = *((unsigned __int16 *)v5 + 1);
          if ( (unsigned int)v392 < 0x58 )
          {
            if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
              || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_530;
            }
            v393 = RdpX_GetActivityIdPrefix(v392, v389, v390, v391);
            v394 = 141;
LABEL_529:
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v394,
              &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v393,
              -2147418113);
LABEL_530:
            RemoteAppWindow = -2147418113;
LABEL_531:
            v281 = v968;
            goto LABEL_629;
          }
          v395 = 16 * *((unsigned __int16 *)v5 + 34) + 72;
          if ( (unsigned int)v392 < v395 )
            RdpRemoteAppCore::LogRemoteAppError(
              (char *)v6 + 16,
              L"Invalid size of TS_RAIL_ORDER_WINDOW_GEOMETRY_BODY PDU",
              2147549183LL,
              0,
              0);
          if ( *((unsigned __int16 *)v5 + 1) < v395 )
          {
            if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
              || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_530;
            }
            v393 = RdpX_GetActivityIdPrefix(v392, v389, v390, v391);
            v394 = 142;
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
              v400 = RdpX_GetActivityIdPrefix(v397, v396, v398, v399);
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 143, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v400);
            }
            goto LABEL_531;
          }
          v401 = (struct RdpXInterfaceRemoteAppWindow **)CacCommon::Rect<int>::Rect<int>(v968);
          RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow(
                              (RdpRemoteAppCore *)((char *)v6 - 48),
                              *((_DWORD *)v5 + 1),
                              v401);
          if ( RemoteAppWindow < 0 )
          {
            if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
              && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v406 = *((_DWORD *)v5 + 1);
              v407 = RdpX_GetActivityIdPrefix(v403, v402, v404, v405);
              WPP_SF_Dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                144,
                &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                v407,
                v406);
            }
            goto LABEL_531;
          }
          if ( (*((_BYTE *)v5 + 8) & 8) != 0 )
          {
            v408 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v968);
            (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v408 + 80LL))(
              v408,
              *((unsigned int *)v5 + 3),
              *((unsigned int *)v5 + 4));
          }
          if ( *((char *)v5 + 8) < 0 )
          {
            v409 = *((_DWORD *)v5 + 13);
            if ( v409 >= 0 )
            {
              v410 = *((_DWORD *)v5 + 14);
              if ( v410 >= 0 )
              {
                v411 = *((_DWORD *)v5 + 15);
                if ( v411 >= 0 )
                {
                  v412 = *((_DWORD *)v5 + 16);
                  if ( v412 >= 0 )
                  {
                    v413 = (__int64 *)RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v968);
                    v978 = __PAIR64__(v410, v409);
                    v979 = v411;
                    v414 = *v413;
                    v980 = v412;
                    (*(void (__fastcall **)(__int64 *, __int64 *, _QWORD))(v414 + 336))(v413, &v978, 0);
                  }
                }
              }
            }
          }
          if ( (*((_DWORD *)v5 + 2) & 0x8000) != 0 )
          {
            v415 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v968);
            (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v415 + 256LL))(
              v415,
              *((unsigned int *)v5 + 11),
              *((unsigned int *)v5 + 12));
            if ( (*((_DWORD *)v5 + 2) & 0x800) != 0 )
            {
              v416 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v968);
              (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v416 + 224LL))(
                v416,
                (unsigned int)(*((_DWORD *)v5 + 7) + *((_DWORD *)v5 + 11)),
                (unsigned int)(*((_DWORD *)v5 + 8) + *((_DWORD *)v5 + 12)));
            }
          }
          if ( (*((_DWORD *)v5 + 2) & 0x800) != 0 )
          {
            if ( (*((_DWORD *)v5 + 2) & 0x400) != 0 )
            {
              v1035[0] = *((_DWORD *)v5 + 7);
              v1035[1] = *((_DWORD *)v5 + 8);
              v1035[2] = *((_DWORD *)v5 + 9);
              v1035[3] = *((_DWORD *)v5 + 10);
              v417 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v968);
              (*(void (__fastcall **)(__int64, _DWORD *, _QWORD))(*(_QWORD *)v417 + 248LL))(v417, v1035, 0);
              v418 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v968);
              (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v418 + 160LL))(
                v418,
                *((int *)v5 + 7),
                *((int *)v5 + 8));
              goto LABEL_566;
            }
            v419 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v968);
            (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v419 + 232LL))(
              v419,
              *((unsigned int *)v5 + 7),
              *((unsigned int *)v5 + 8),
              0);
            v420 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v968);
            (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v420 + 160LL))(
              v420,
              *((int *)v5 + 7),
              *((int *)v5 + 8));
          }
          if ( (*((_DWORD *)v5 + 2) & 0x400) != 0 )
          {
            v421 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v968);
            (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v421 + 240LL))(
              v421,
              *((unsigned int *)v5 + 9),
              *((unsigned int *)v5 + 10),
              0);
          }
LABEL_566:
          if ( (*((_DWORD *)v5 + 2) & 0x100) != 0 )
          {
            v424 = (char *)operator new(saturated_mul(*((unsigned __int16 *)v5 + 34), 0x10u));
            if ( !v424 )
            {
              if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v427 = RdpX_GetActivityIdPrefix(v423, v422, v425, v426);
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  145,
                  &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                  v427,
                  -2147024882);
              }
              RemoteAppWindow = -2147024882;
              goto LABEL_531;
            }
            v428 = 0;
            if ( *((_WORD *)v5 + 34) )
            {
              v429 = v973;
              do
              {
                v430 = 16LL * v428;
                *(_DWORD *)&v424[v430] = *(_DWORD *)((char *)v5 + v430 + 72);
                *(_DWORD *)&v424[v430 + 4] = *(_DWORD *)((char *)v5 + v430 + 76);
                *(_DWORD *)&v424[v430 + 8] = *((_DWORD *)v5 + 4 * v428 + 20) - *(_DWORD *)((char *)v5 + v430 + 72);
                *(_DWORD *)&v424[v430 + 12] = *(_DWORD *)((char *)v5 + v430 + 84) - *(_DWORD *)((char *)v5 + v430 + 76);
                LODWORD(v958) = *(_DWORD *)((char *)v5 + v430 + 84);
                LODWORD(v956) = *((_DWORD *)v5 + 4 * v428 + 20);
                LODWORD(v954) = *(_DWORD *)((char *)v5 + v430 + 76);
                LODWORD(v949) = *(_DWORD *)((char *)v5 + v430 + 72);
                LODWORD(cchToCopya) = *((_DWORD *)v5 + 1);
                RdpRemoteAppCore::LogRemoteAppEventF(
                  v429,
                  L"WindowGeometryRailOrderReceived_VisibilityRect[%i]: WindowId=0x%x, Left=%i, Top=%i, Right=%i, Bottom=%i",
                  0,
                  (unsigned int)v428++,
                  cchToCopya,
                  v949,
                  v954,
                  v956,
                  v958);
              }
              while ( v428 < *((unsigned __int16 *)v5 + 34) );
            }
            v431 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v968);
            (*(void (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v431 + 176LL))(
              v431,
              *((unsigned __int16 *)v5 + 34),
              v424);
            v432 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v968);
            (*(void (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v432 + 168LL))(
              v432,
              *((unsigned __int16 *)v5 + 34),
              v424);
            operator delete(v424);
          }
          if ( (*((_BYTE *)v5 + 8) & 0x10) != 0 )
          {
            v433 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v968);
            (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v433 + 128LL))(v433, *((unsigned __int8 *)v5 + 20));
          }
          RemoteAppWindow = 0;
          goto LABEL_531;
        }
        RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v981);
        if ( *((_WORD *)v5 + 1) < 0x1Eu )
          RdpRemoteAppCore::LogRemoteAppError(
            (char *)v6 + 16,
            L"Invalid size of TS_RAIL_ORDER_WINDOW_CHANGE_BODY PDU",
            2147549183LL,
            0,
            0);
        v437 = *((unsigned __int16 *)v5 + 1);
        if ( (unsigned int)v437 >= 0x1E )
        {
          v440 = *((unsigned __int16 *)v5 + 13) + 28;
          if ( (unsigned int)v437 < v440 )
            RdpRemoteAppCore::LogRemoteAppError(
              (char *)v6 + 16,
              L"Invalid size of TS_RAIL_ORDER_WINDOW_CHANGE_BODY PDU",
              2147549183LL,
              0,
              0);
          if ( *((unsigned __int16 *)v5 + 1) >= v440 )
          {
            if ( *((_DWORD *)v5 + 1) == -1 )
            {
              if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                v441 = RdpX_GetActivityIdPrefix(v437, v434, v435, v436);
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  139,
                  &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                  v441);
              }
            }
            else
            {
              v442 = (struct RdpXInterfaceRemoteAppWindow **)CacCommon::Rect<int>::Rect<int>(v981);
              RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow(
                                  (RdpRemoteAppCore *)((char *)v6 - 48),
                                  *((_DWORD *)v5 + 1),
                                  v442);
              if ( RemoteAppWindow >= 0 )
              {
                if ( (*((_BYTE *)v5 + 8) & 2) != 0 )
                {
                  v449 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v981);
                  (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v449 + 120LL))(v449, *((unsigned int *)v5 + 3));
                }
                if ( (*((_BYTE *)v5 + 8) & 8) != 0 )
                {
                  v450 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v981);
                  (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v450 + 80LL))(
                    v450,
                    *((unsigned int *)v5 + 4),
                    *((unsigned int *)v5 + 5));
                }
                if ( (*((_DWORD *)v5 + 2) & 0x80000) != 0 )
                {
                  v451 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v981);
                  (*(void (__fastcall **)(__int64, bool))(*(_QWORD *)v451 + 312LL))(v451, *((_BYTE *)v5 + 25) == 1);
                }
                memset_0(Destination, 0, 0x20Au);
                if ( (*((_BYTE *)v5 + 8) & 4) != 0 && *((_WORD *)v5 + 13) )
                {
                  memcpy_s(Destination, 0x208u, (char *)v5 + 28, *((unsigned __int16 *)v5 + 13));
                  v452 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v981);
                  (*(void (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v452 + 104LL))(v452, Destination);
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
                  v453 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v981);
                  (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v453 + 128LL))(
                    v453,
                    *((unsigned __int8 *)v5 + 24));
                }
                RemoteAppWindow = 0;
              }
              else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                     && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
                     && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v447 = *((_DWORD *)v5 + 1);
                v448 = RdpX_GetActivityIdPrefix(v444, v443, v445, v446);
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  140,
                  &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                  v448,
                  v447);
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
            v281 = v981;
            goto LABEL_629;
          }
          v438 = RdpX_GetActivityIdPrefix(v437, v434, v435, v436);
          v439 = 138;
        }
        else
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_588;
          }
          v438 = RdpX_GetActivityIdPrefix(v437, v434, v435, v436);
          v439 = 137;
        }
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v439,
          &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v438,
          -2147418113);
        goto LABEL_588;
      }
      RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v960);
      RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v976);
      v1033 = 0;
      if ( *((_WORD *)v5 + 1) < 0x58u )
        RdpRemoteAppCore::LogRemoteAppError(
          (char *)v6 + 16,
          L"Invalid size of TS_RAIL_ORDER_WINDOW_CREATE_BODY PDU",
          2147549183LL,
          0,
          0);
      v457 = *((unsigned __int16 *)v5 + 1);
      if ( (unsigned int)v457 < 0x58 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_627;
        }
        v458 = RdpX_GetActivityIdPrefix(v457, v454, v455, v456);
        v459 = 127;
LABEL_626:
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v459,
          &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v458,
          -2147418113);
LABEL_627:
        RemoteAppWindow = -2147418113;
LABEL_628:
        TCntPtr<ITSViewerRecorder>::SafeRelease(v976);
        v281 = v960;
        goto LABEL_629;
      }
      if ( *((_WORD *)v5 + 34) )
        v460 = *((unsigned __int16 *)v5 + 34) - 1;
      else
        v460 = 0;
      v461 = 16 * v460 + 84;
      v462 = v461 + *((unsigned __int16 *)v5 + 13) + 4;
      LODWORD(v978) = v461;
      if ( (unsigned int)v457 < v462 )
        RdpRemoteAppCore::LogRemoteAppError(
          (char *)v6 + 16,
          L"Invalid size of TS_RAIL_ORDER_WINDOW_CREATE_BODY PDU",
          2147549183LL,
          0,
          0);
      if ( *((unsigned __int16 *)v5 + 1) < v462 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_627;
        }
        v458 = RdpX_GetActivityIdPrefix(v457, v454, v455, v456);
        v459 = 128;
        goto LABEL_626;
      }
      if ( *((_DWORD *)v5 + 1) == -1 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v463 = RdpX_GetActivityIdPrefix(v457, v454, v455, v456);
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 129, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v463);
        }
        goto LABEL_628;
      }
      v464 = (struct ITSWndPluginEx **)CacCommon::Rect<int>::Rect<int>(v976);
      v465 = 0;
      RemoteAppWindow = RdpRemoteAppCore::GetWndPlugin((RdpRemoteAppCore *)((char *)v6 - 48), v464);
      if ( RemoteAppWindow < 0 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v470 = RdpX_GetActivityIdPrefix(v467, v466, v468, v469);
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            130,
            (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
            v470,
            (__int64)"GetWndPlugin failed",
            RemoteAppWindow);
        }
        goto LABEL_628;
      }
      v471 = (struct RdpXInterfaceRemoteAppWindow **)CacCommon::Rect<int>::Rect<int>(v960);
      RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow(
                          (RdpRemoteAppCore *)((char *)v6 - 48),
                          *((_DWORD *)v5 + 1),
                          v471);
      if ( RemoteAppWindow < 0 )
      {
        RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v1004);
        RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v992);
        RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v1003);
        v1036 = 0;
        v472 = CacCommon::Rect<int>::Rect<int>(v1004);
        WindowCallbacks = RdpRemoteAppCore::CreateWindowCallbacks((char *)v6 + 16, *((unsigned int *)v5 + 1), v472);
        RemoteAppWindow = MapXResultToHR(WindowCallbacks);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_657;
          }
          v478 = RdpX_GetActivityIdPrefix(v475, v474, v476, v477);
          v479 = 131;
          v480 = "CreateWindowCallbacks failed";
LABEL_656:
          LODWORD(v943) = RemoteAppWindow;
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v479,
            (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
            v478,
            (__int64)v480,
            v943);
LABEL_657:
          ComPlainSmartPtr<IRdpBaseCoreApi>::~ComPlainSmartPtr<IRdpBaseCoreApi>(v1003);
          RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v992);
          RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v1004);
          goto LABEL_628;
        }
        v481 = CacCommon::Rect<int>::Rect<int>(v992);
        Object = RdpX_CreateObject(0, 0, 67, 105, v481);
        RemoteAppWindow = MapXResultToHR(Object);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_657;
          }
          v478 = RdpX_GetActivityIdPrefix(v484, v483, v485, v486);
          v479 = 132;
          v480 = "RdpXBaseCoreApiAdaptor RdpX_CreateObject failed";
          goto LABEL_656;
        }
        v487 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *((char *)v6 + 104);
        v488 = *(__int64 (__fastcall **)(__int64, void *))(*(_QWORD *)v487 + 216LL);
        v489 = CacCommon::Rect<int>::Rect<int>(v1003);
        RemoteAppWindow = v488(v487, v489);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_657;
          }
          v478 = RdpX_GetActivityIdPrefix(v491, v490, v492, v493);
          v479 = 133;
          v480 = "Failed to get base core Api";
          goto LABEL_656;
        }
        v494 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v992);
        v495 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v494 + 24LL);
        v496 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v1003);
        v497 = v495(v494, v496);
        RemoteAppWindow = MapXResultToHR(v497);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_657;
          }
          v478 = RdpX_GetActivityIdPrefix(v499, v498, v500, v501);
          v479 = 134;
          v480 = "SetCoreApi failed";
          goto LABEL_656;
        }
        v502 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *((char *)v973 + 128);
        v503 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64, __int128 *, void *))(*(_QWORD *)v502 + 48LL);
        v504 = CacCommon::Rect<int>::Rect<int>(v960);
        v505 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v1004);
        v506 = *((_DWORD *)v5 + 1);
        v507 = v505;
        v508 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v992);
        v509 = v503(v502, v508, v506, v507, &v1036, v504);
        v465 = 0;
        RemoteAppWindow = MapXResultToHR(v509);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_657;
          }
          v478 = RdpX_GetActivityIdPrefix(v511, v510, v512, v513);
          v479 = 135;
          v480 = "CreateWindowRepresentation failed";
          goto LABEL_656;
        }
        v514 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v960);
        v515 = *(__int64 (__fastcall **)(__int64, bool))(*(_QWORD *)v514 + 320LL);
        v516 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v976);
        v517 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v516 + 136LL))(v516);
        v518 = v515(v514, v517 != 0);
        RemoteAppWindow = MapXResultToHR(v518);
        v519 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v960);
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v519 + 120LL))(v519, *((unsigned int *)v5 + 3));
        ComPlainSmartPtr<IRdpBaseCoreApi>::~ComPlainSmartPtr<IRdpBaseCoreApi>(v1003);
        RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v992);
        RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v1004);
        v6 = v973;
        v461 = v978;
      }
      v520 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v976);
      if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v520 + 136LL))(v520) )
      {
        v521 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v960);
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v521 + 200LL))(v521, 2);
      }
      v522 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v960);
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v522 + 80LL))(
        v522,
        *((unsigned int *)v5 + 4),
        *((unsigned int *)v5 + 5));
      v523 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v960);
      (*(void (__fastcall **)(__int64, bool))(*(_QWORD *)v523 + 312LL))(v523, *((_BYTE *)v5 + 25) == 1);
      memset_0(v1040, 0, 0x20Au);
      if ( *((_WORD *)v5 + 13) > 2u )
      {
        memcpy_s(v1040, 0x208u, (char *)v5 + v461 + 4, *((unsigned __int16 *)v5 + 13));
        v524 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v960);
        (*(void (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v524 + 104LL))(v524, v1040);
      }
      CUT::ObfuscateFilePathW(v1040);
      LODWORD(v943) = *((_DWORD *)v5 + 3);
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
        v943,
        *((_DWORD *)v5 + 4),
        *((_DWORD *)v5 + 5),
        *((unsigned __int8 *)v5 + 24),
        *((unsigned __int8 *)v5 + 25),
        *((unsigned __int16 *)v5 + 13),
        v1040,
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
      LODWORD(v978) = *((_DWORD *)v5 + 13);
      if ( (int)v978 >= 0 )
      {
        v525 = *((_DWORD *)v5 + 14);
        if ( v525 >= 0 )
        {
          v526 = *((_DWORD *)v5 + 15);
          if ( v526 >= 0 )
          {
            v527 = *((_DWORD *)v5 + 16);
            if ( v527 >= 0 )
            {
              v528 = (__int64 *)RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v960);
              v973 = (RdpRemoteAppCore *)__PAIR64__(v525, v978);
              v974 = v526;
              v529 = *v528;
              v975 = v527;
              (*(void (__fastcall **)(__int64 *, RdpRemoteAppCore **, _QWORD))(v529 + 336))(v528, &v973, 0);
            }
          }
          v465 = 0;
        }
      }
      v530 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v960);
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v530 + 224LL))(
        v530,
        (unsigned int)(*((_DWORD *)v5 + 7) + *((_DWORD *)v5 + 11)),
        (unsigned int)(*((_DWORD *)v5 + 8) + *((_DWORD *)v5 + 12)));
      v531 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v960);
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v531 + 256LL))(
        v531,
        *((unsigned int *)v5 + 11),
        *((unsigned int *)v5 + 12));
      v1033 = *(_OWORD *)((char *)v5 + 28);
      v532 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v960);
      (*(void (__fastcall **)(__int64, __int128 *, _QWORD))(*(_QWORD *)v532 + 248LL))(v532, &v1033, 0);
      v535 = (char *)operator new(saturated_mul(*((unsigned __int16 *)v5 + 34), 0x10u));
      if ( v535 )
      {
        if ( *((_WORD *)v5 + 34) )
        {
          do
          {
            v539 = 16LL * v465;
            *(_DWORD *)&v535[v539] = *(_DWORD *)((char *)v5 + v539 + 72);
            *(_DWORD *)&v535[v539 + 4] = *(_DWORD *)((char *)v5 + v539 + 76);
            *(_DWORD *)&v535[v539 + 8] = *((_DWORD *)v5 + 4 * v465 + 20) - *(_DWORD *)((char *)v5 + v539 + 72);
            *(_DWORD *)&v535[v539 + 12] = *(_DWORD *)((char *)v5 + v539 + 84) - *(_DWORD *)((char *)v5 + v539 + 76);
            LODWORD(v959) = *(_DWORD *)((char *)v5 + v539 + 84);
            LODWORD(v957) = *((_DWORD *)v5 + 4 * v465 + 20);
            LODWORD(v955) = *(_DWORD *)((char *)v5 + v539 + 76);
            LODWORD(v950) = *(_DWORD *)((char *)v5 + v539 + 72);
            LODWORD(cchToCopyb) = *((_DWORD *)v5 + 1);
            RdpRemoteAppCore::LogRemoteAppEventF(
              (char *)v6 + 16,
              L"WindowCreateRailOrderReceived_VisibilityRect[%i]: WindowId=0x%x, Left=%i, Top=%i, Right=%i, Bottom=%i",
              0,
              (unsigned int)v465++,
              cchToCopyb,
              v950,
              v955,
              v957,
              v959);
          }
          while ( v465 < *((unsigned __int16 *)v5 + 34) );
        }
        v540 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v960);
        (*(void (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v540 + 176LL))(
          v540,
          *((unsigned __int16 *)v5 + 34),
          v535);
        v541 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v960);
        (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v541 + 160LL))(
          v541,
          *((int *)v5 + 7),
          *((int *)v5 + 8));
        v542 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v960);
        (*(void (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v542 + 168LL))(
          v542,
          *((unsigned __int16 *)v5 + 34),
          v535);
        operator delete(v535);
        if ( RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *((char *)v6 + 136) )
        {
          v543 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *((char *)v6 + 136);
          v544 = *(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v543 + 40LL);
          v545 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v960);
          v546 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v545 + 72LL))(v545);
          v544(v543, v546);
        }
        v547 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v960);
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v547 + 128LL))(v547, *((unsigned __int8 *)v5 + 24));
      }
      else
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v538 = RdpX_GetActivityIdPrefix(v534, v533, v536, v537);
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            136,
            &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
            v538,
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
              RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v988);
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
                    v571 = RdpX_GetActivityIdPrefix(v568, v567, v569, v570);
                    WPP_SF_Dd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      120,
                      &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                      v571,
                      -2147418113);
                  }
                  RemoteAppWindow = -2147418113;
LABEL_738:
                  v572 = v988;
LABEL_739:
                  TCntPtr<ITSViewerRecorder>::SafeRelease(v572);
                  return (unsigned int)RemoteAppWindow;
                }
              }
              RdpRemoteAppCore::LogRemoteAppEventF(
                (char *)v6 + 16,
                L"SyncStateRailOrderReceived: SyncFlags=0x%x",
                0,
                *((unsigned int *)v5 + 1));
              v573 = (struct ITSWndPluginEx **)CacCommon::Rect<int>::Rect<int>(v988);
              RemoteAppWindow = RdpRemoteAppCore::GetWndPlugin((RdpRemoteAppCore *)((char *)v6 - 48), v573);
              if ( RemoteAppWindow < 0 )
              {
                if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                  && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v578 = RdpX_GetActivityIdPrefix(v575, v574, v576, v577);
                  WPP_SF_DsD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    121,
                    (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                    v578,
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
                  v579 = RdpX_GetActivityIdPrefix(v575, v574, v576, v577);
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    122,
                    &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                    v579);
                }
                v580 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v988);
                v581 = 0;
              }
              else
              {
                if ( (*((_BYTE *)v5 + 4) & 2) == 0 )
                  goto LABEL_774;
                v582 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                  && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
                {
                  v583 = RdpX_GetActivityIdPrefix(v575, v574, v576, v577);
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    123,
                    &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                    v583);
                  v582 = WPP_GLOBAL_Control;
                }
                if ( (*((_BYTE *)v5 + 4) & 8) != 0 )
                {
                  if ( v582 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v582[7] & 1) != 0 && *((_BYTE *)v582 + 25) >= 3u )
                  {
                    v584 = RdpX_GetActivityIdPrefix(v575, v574, v576, v577);
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      124,
                      &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                      v584);
                  }
                  v585 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v988);
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v585 + 120LL))(v585);
                  if ( (unsigned int)RdpRemoteAppCore::IsRemoteAppV2Enabled((char *)v6 + 16) )
                  {
                    v586 = (RdpRemoteAppCore *)((char *)v6 + 128);
                    v973 = (RdpRemoteAppCore *)((char *)v6 + 128);
                    v587 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *((char *)v6 + 128);
                    LODWORD(v978) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v587 + 120LL))(v587);
                    v588 = 0;
                    if ( (_DWORD)v978 )
                    {
                      while ( 1 )
                      {
                        RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v1027);
                        v589 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v586);
                        v590 = *(__int64 (__fastcall **)(__int64, _QWORD, void *))(*(_QWORD *)v589 + 128LL);
                        v591 = CacCommon::Rect<int>::Rect<int>(v1027);
                        v594 = v590(v589, v588, v591);
                        if ( v594 )
                          break;
                        v597 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v1027);
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v597 + 384LL))(v597);
                        RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v1027);
                        v586 = v973;
                        if ( ++v588 >= (unsigned int)v978 )
                          goto LABEL_772;
                      }
                      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                        && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                      {
                        v598 = RdpX_GetActivityIdPrefix(v593, v592, v595, v596);
                        WPP_SF_DLD(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          125,
                          &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                          v598,
                          v594,
                          v594);
                      }
                      RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v1027);
                      goto LABEL_738;
                    }
                  }
                }
                else
                {
                  v599 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v988);
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v599 + 144LL))(v599);
                }
LABEL_772:
                v580 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v988);
                v581 = 1;
              }
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v580 + 112LL))(v580, v581);
LABEL_774:
              if ( (*((_BYTE *)v5 + 4) & 4) != 0 )
              {
                if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                  && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
                {
                  v600 = RdpX_GetActivityIdPrefix(v575, v574, v576, v577);
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    126,
                    &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                    v600);
                }
                v601 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v988);
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v601 + 128LL))(v601);
              }
              goto LABEL_738;
            }
            RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v1017);
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
              v608 = *((_DWORD *)v5 + 1);
              if ( v608 <= 0x100 )
              {
                v609 = 4 * v608 + 16;
                if ( *((unsigned __int16 *)v5 + 1) < v609 )
                  RdpRemoteAppCore::LogRemoteAppError(
                    (char *)v6 + 16,
                    L"Invalid size of TS_RAIL_ORDER_ZORDER_BODY PDU",
                    2147549183LL,
                    0,
                    0);
                if ( *((unsigned __int16 *)v5 + 1) >= v609 )
                {
                  memset_0(v1042, 0, 0x208u);
                  v610 = v1042;
                  v611 = 260;
                  v1028 = v1042;
                  v1029 = 260;
                  v612 = *((_DWORD *)v5 + 1);
                  if ( v612 )
                  {
                    v613 = 0;
                    v614 = 0;
                    while ( 1 )
                    {
                      v615 = v612;
                      if ( v613 < 0 )
                        break;
                      v616 = L"0x%x,";
                      if ( v614 >= v612 - 1 )
                        v616 = L"0x%x";
                      LODWORD(v953) = *((_DWORD *)v5 + v614 + 4);
                      v613 = StringCchPrintfExW(v610, v611, &v1028, &v1029, 0, v616, v953);
                      if ( v613 < 0
                        && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                      {
                        v621 = RdpX_GetActivityIdPrefix(v618, v617, v619, v620);
                        LODWORD(v943) = v613;
                        WPP_SF_DsD(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          209,
                          (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                          v621,
                          (__int64)"StringCchPrintfEx failed",
                          v943);
                      }
                      v612 = *((_DWORD *)v5 + 1);
                      ++v614;
                      v615 = v612;
                      if ( v614 >= v612 )
                        break;
                      v610 = v1028;
                      v611 = v1029;
                    }
                  }
                  else
                  {
                    v615 = 0;
                  }
                  LODWORD(v943) = *((_DWORD *)v5 + 3);
                  LODWORD(cchToCopy) = *((_DWORD *)v5 + 2);
                  RdpRemoteAppCore::LogRemoteAppEventF(
                    (char *)v6 + 16,
                    L"ZOrderRailOrderReceived: NumWindows=%u, FieldsValidFlags=0x%x, ActiveWindowId=0x%x, WindowIds=[%s]",
                    0,
                    v615,
                    cchToCopy,
                    v943,
                    v1042);
                  v622 = (struct ITSWndPluginEx **)CacCommon::Rect<int>::Rect<int>(v1017);
                  RemoteAppWindow = RdpRemoteAppCore::GetWndPlugin((RdpRemoteAppCore *)((char *)v6 - 48), v622);
                  if ( RemoteAppWindow >= 0 )
                  {
                    v628 = (*((_DWORD *)v5 + 2) >> 4) & 2 | 1;
                    if ( (*((_BYTE *)v5 + 8) & 0x10) == 0 )
                      v628 = (*((_DWORD *)v5 + 2) >> 4) & 2;
                    if ( v628 )
                    {
                      v629 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v1017);
                      (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, __int64))(*(_QWORD *)v629 + 104LL))(
                        v629,
                        v628,
                        *((unsigned int *)v5 + 3),
                        *((unsigned int *)v5 + 1),
                        (__int64)v5 + 16);
                    }
                  }
                  else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                         && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v627 = RdpX_GetActivityIdPrefix(v624, v623, v625, v626);
                    LODWORD(v951) = RemoteAppWindow;
                    WPP_SF_DsD(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      210,
                      (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                      v627,
                      (__int64)"GetWndPlugin failed",
                      v951);
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
                  v572 = v1017;
                  goto LABEL_739;
                }
                v606 = RdpX_GetActivityIdPrefix(v603, v602, v604, v605);
                v607 = 208;
              }
              else
              {
                if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                  || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_787;
                }
                v606 = RdpX_GetActivityIdPrefix(v603, v602, v604, v605);
                v607 = 207;
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
              v606 = RdpX_GetActivityIdPrefix(v603, v602, v604, v605);
              v607 = 206;
            }
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v607,
              &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v606,
              -2147418113);
            goto LABEL_787;
          }
          RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v989);
          RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v1018);
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
                v634 = RdpX_GetActivityIdPrefix(v631, v630, v632, v633);
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  202,
                  &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                  v634,
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
          v637 = (struct ITSWndPluginEx **)CacCommon::Rect<int>::Rect<int>(v1018);
          RemoteAppWindow = RdpRemoteAppCore::GetWndPlugin((RdpRemoteAppCore *)((char *)v6 - 48), v637);
          if ( RemoteAppWindow >= 0 )
          {
            v645 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v1018);
            v646 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, void *))(*(_QWORD *)v645 + 72LL);
            v647 = CacCommon::Rect<int>::Rect<int>(v989);
            RemoteAppWindow = v646(v645, *((unsigned int *)v5 + 1), *((unsigned int *)v5 + 2), v647);
            if ( RemoteAppWindow >= 0 )
            {
              v652 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v989);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v652 + 128LL))(v652);
              v653 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v989);
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v653 + 120LL))(v653, 2);
              v654 = (struct RdpXInterfaceShellNotifyInformation *)RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v989);
              v655 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v989);
              v656 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v655 + 72LL))(v655);
              RemoteAppWindow = RdpRemoteAppCore::OnShellNotifyInformation(v973, v656, v654);
              if ( RemoteAppWindow >= 0
                || WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_832;
              }
              v642 = RdpX_GetActivityIdPrefix(v658, v657, v659, v660);
              v643 = 205;
              v644 = "OnShellNotifyInformation failed";
            }
            else
            {
              if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_832;
              }
              v642 = RdpX_GetActivityIdPrefix(v649, v648, v650, v651);
              v643 = 204;
              v644 = "FindShellNotifyInfo failed";
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
            v642 = RdpX_GetActivityIdPrefix(v639, v638, v640, v641);
            v643 = 203;
            v644 = "GetWndPlugin failed";
          }
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v643,
            (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
            v642,
            (__int64)v644,
            RemoteAppWindow);
LABEL_832:
          TCntPtr<ITSViewerRecorder>::SafeRelease(v1018);
          v636 = v989;
LABEL_1025:
          RdpXSPtr<RdpXTapVcCallbackItem>::SafeRelease(v636, v635);
          return (unsigned int)RemoteAppWindow;
        }
        RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v977);
        RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v982);
        if ( *((_WORD *)v5 + 1) < 0x14u )
          RdpRemoteAppCore::LogRemoteAppError(
            (char *)v6 + 16,
            L"Invalid size of TS_RAIL_ORDER_NOTIFYICON_TOAST_BODY",
            2147549183LL,
            0,
            0);
        v664 = *((unsigned __int16 *)v5 + 1);
        if ( (unsigned int)v664 < 0x14 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_857;
          }
          v665 = RdpX_GetActivityIdPrefix(v661, v664, v662, v663);
          v666 = 194;
LABEL_856:
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v666,
            &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
            v665,
            -2147418113);
LABEL_857:
          RemoteAppWindow = -2147418113;
LABEL_858:
          TCntPtr<ITSViewerRecorder>::SafeRelease(v982);
          v636 = v977;
          goto LABEL_1025;
        }
        v667 = *((unsigned __int16 *)v5 + 8);
        v668 = v667 + *((unsigned __int16 *)v5 + 9) + 20;
        if ( (unsigned int)v664 < v668 )
          RdpRemoteAppCore::LogRemoteAppError(
            (char *)v6 + 16,
            L"Invalid size of TS_RAIL_ORDER_NOTIFYICON_TOAST_BODY PDU",
            2147549183LL,
            0,
            0);
        if ( *((unsigned __int16 *)v5 + 1) < v668 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_857;
          }
          v665 = RdpX_GetActivityIdPrefix(v667, v664, v662, v663);
          v666 = 195;
          goto LABEL_856;
        }
        v669 = (struct ITSWndPluginEx **)CacCommon::Rect<int>::Rect<int>(v982);
        RemoteAppWindow = RdpRemoteAppCore::GetWndPlugin((RdpRemoteAppCore *)((char *)v6 - 48), v669);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_858;
          }
          v674 = RdpX_GetActivityIdPrefix(v671, v670, v672, v673);
          v675 = 196;
          v676 = "GetWndPlugin failed";
          goto LABEL_871;
        }
        v677 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v982);
        v678 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, void *))(*(_QWORD *)v677 + 72LL);
        v679 = CacCommon::Rect<int>::Rect<int>(v977);
        RemoteAppWindow = v678(v677, *((unsigned int *)v5 + 1), *((unsigned int *)v5 + 2), v679);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_858;
          }
          v674 = RdpX_GetActivityIdPrefix(v681, v680, v682, v683);
          v675 = 197;
          v676 = "FindShellNotifyInfo failed";
LABEL_871:
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v675,
            (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
            v674,
            (__int64)v676,
            RemoteAppWindow);
          goto LABEL_858;
        }
        v684 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v977);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v684 + 128LL))(v684);
        v685 = *((unsigned __int16 *)v5 + 8);
        v686 = (char *)v5 + 20;
        RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v1008);
        v687 = CacCommon::Rect<int>::Rect<int>(v1008);
        ConstXChar16StringWithSpecifiedSize = RdpX_Strings_CreateConstXChar16StringWithSpecifiedSize(
                                                *((unsigned __int16 *)v5 + 8) >> 1,
                                                (char *)v5 + 20,
                                                v687);
        RemoteAppWindow = MapXResultToHR(ConstXChar16StringWithSpecifiedSize);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v693 = RdpX_GetActivityIdPrefix(v690, v689, v691, v692);
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              198,
              (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v693,
              (__int64)"RdpX_Strings_CreateConstXChar16StringWithSpecifiedSize failed",
              RemoteAppWindow);
          }
          goto LABEL_882;
        }
        v694 = &v686[v685];
        RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v1019);
        v695 = CacCommon::Rect<int>::Rect<int>(v1019);
        v696 = RdpX_Strings_CreateConstXChar16StringWithSpecifiedSize(
                 *((unsigned __int16 *)v5 + 9) >> 1,
                 &v686[v685],
                 v695);
        RemoteAppWindow = MapXResultToHR(v696);
        if ( RemoteAppWindow >= 0 )
        {
          v704 = &sourceString;
          if ( RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v1019) )
          {
            v705 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v1019);
            v706 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v705 + 24LL))(v705);
          }
          else
          {
            v706 = &sourceString;
          }
          if ( RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v1008) )
          {
            v707 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v1008);
            v704 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v707 + 24LL))(v707);
          }
          LODWORD(cchToCopy) = *((_DWORD *)v5 + 2);
          RdpRemoteAppCore::LogRemoteAppEventF(
            (char *)v973 + 16,
            L"NotifyIconToastRailOrderReceived: WindowId=0x%x, NotifyIconId=0x%x, ToastFlags=0x%x, Toast=%s, ToastTitle=%s",
            0,
            *((unsigned int *)v5 + 1),
            cchToCopy,
            *((_DWORD *)v5 + 3),
            v704,
            v706);
          v708 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v977);
          LOWORD(v952) = *((_WORD *)v5 + 9) >> 1;
          RemoteAppWindow = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, __int64, int, char *))(*(_QWORD *)v708 + 96LL))(
                              v708,
                              0,
                              *((unsigned int *)v5 + 3),
                              *((_WORD *)v5 + 8) >> 1,
                              (__int64)v5 + 20,
                              v952,
                              v694);
          if ( RemoteAppWindow >= 0 )
          {
            v713 = (struct RdpXInterfaceShellNotifyInformation *)RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v977);
            v714 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v977);
            v715 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v714 + 72LL))(v714);
            RemoteAppWindow = RdpRemoteAppCore::OnShellNotifyInformation(v973, v715, v713);
            if ( RemoteAppWindow >= 0
              || WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
              || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_889;
            }
            v701 = RdpX_GetActivityIdPrefix(v717, v716, v718, v719);
            v702 = 201;
            v703 = "OnShellNotifyInformation failed";
          }
          else
          {
            if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
              || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_889;
            }
            v701 = RdpX_GetActivityIdPrefix(v710, v709, v711, v712);
            v702 = 200;
            v703 = "spShellNotify->SetInfo failed";
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
          v701 = RdpX_GetActivityIdPrefix(v698, v697, v699, v700);
          v702 = 199;
          v703 = "RdpX_Strings_CreateConstXChar16StringWithSpecifiedSize failed";
        }
        LODWORD(v943) = RemoteAppWindow;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v702,
          (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v701,
          (__int64)v703,
          v943);
LABEL_889:
        RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v1019);
LABEL_882:
        RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v1008);
        goto LABEL_858;
      }
      RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v962);
      RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v969);
      if ( *((_WORD *)v5 + 1) < 0x18u )
        RdpRemoteAppCore::LogRemoteAppError(
          (char *)v6 + 16,
          L"Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Change PDU",
          2147549183LL,
          0,
          0);
      v723 = *((unsigned __int16 *)v5 + 1);
      if ( (unsigned int)v723 < 0x18 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_913;
        }
        v724 = RdpX_GetActivityIdPrefix(v723, v720, v721, v722);
        v725 = 180;
LABEL_912:
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v725,
          &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v724,
          -2147418113);
LABEL_913:
        RemoteAppWindow = -2147418113;
LABEL_914:
        TCntPtr<ITSViewerRecorder>::SafeRelease(v969);
        v636 = v962;
        goto LABEL_1025;
      }
      v726 = *((unsigned __int16 *)v5 + 6) + 24;
      if ( (unsigned int)v723 < v726 )
        RdpRemoteAppCore::LogRemoteAppError(
          (char *)v6 + 16,
          L"Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Change PDU",
          2147549183LL,
          0,
          0);
      if ( *((unsigned __int16 *)v5 + 1) < v726 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_913;
        }
        v724 = RdpX_GetActivityIdPrefix(v723, v720, v721, v722);
        v725 = 181;
        goto LABEL_912;
      }
      v727 = (struct ITSWndPluginEx **)CacCommon::Rect<int>::Rect<int>(v969);
      RemoteAppWindow = RdpRemoteAppCore::GetWndPlugin((RdpRemoteAppCore *)((char *)v6 - 48), v727);
      if ( RemoteAppWindow < 0 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_914;
        }
        v732 = RdpX_GetActivityIdPrefix(v729, v728, v730, v731);
        v733 = 182;
        v734 = "GetWndPlugin failed";
        goto LABEL_927;
      }
      v735 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v969);
      v736 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, void *))(*(_QWORD *)v735 + 72LL);
      v737 = CacCommon::Rect<int>::Rect<int>(v962);
      v738 = v736(v735, *((unsigned int *)v5 + 1), *((unsigned int *)v5 + 2), v737);
      v743 = 0;
      RemoteAppWindow = v738;
      if ( v738 < 0 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_914;
        }
        v732 = RdpX_GetActivityIdPrefix(v740, v739, v741, v742);
        v733 = 183;
        v734 = "FindShellNotifyInfo failed";
LABEL_927:
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v733,
          (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v732,
          (__int64)v734,
          RemoteAppWindow);
        goto LABEL_914;
      }
      v744 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v962);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v744 + 128LL))(v744);
      RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v971);
      if ( *((_WORD *)v5 + 6) )
      {
        v745 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v962);
        RemoteAppWindow = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v745 + 88LL))(
                            v745,
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
          v750 = RdpX_GetActivityIdPrefix(v747, v746, v748, v749);
          v751 = 184;
          v752 = "CreateShellNotifyInfo->SetTip failed";
          goto LABEL_939;
        }
        v753 = CacCommon::Rect<int>::Rect<int>(v971);
        v754 = RdpX_Strings_CreateConstXChar16StringWithSpecifiedSize(
                 *((unsigned __int16 *)v5 + 6) >> 1,
                 (char *)v5 + 24,
                 v753);
        RemoteAppWindow = MapXResultToHR(v754);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_940;
          }
          v750 = RdpX_GetActivityIdPrefix(v756, v755, v757, v758);
          v751 = 185;
          v752 = "RdpX_Strings_CreateConstXChar16StringWithSpecifiedSize failed";
          goto LABEL_939;
        }
      }
      if ( (*((_BYTE *)v5 + 20) & 4) != 0 )
      {
        v759 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v962);
        RemoteAppWindow = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v759 + 104LL))(
                            v759,
                            *((unsigned int *)v5 + 4));
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_940;
          }
          v750 = RdpX_GetActivityIdPrefix(v761, v760, v762, v763);
          v751 = 186;
          v752 = "CreateShellNotifyInfo->SetWSNState failed";
          goto LABEL_939;
        }
      }
      if ( *((_BYTE *)v5 + 14) )
      {
        RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v990);
        v768 = *((unsigned __int16 *)v5 + 6);
        v769 = *((unsigned __int16 *)v5 + 1);
        if ( *((_BYTE *)v5 + 15) )
        {
          v770 = v726 + 4;
          v771 = v973;
          if ( v769 < v770 )
            RdpRemoteAppCore::LogRemoteAppError(
              (char *)v973 + 16,
              L"Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Create PDU",
              2147549183LL,
              0,
              0);
          if ( *((unsigned __int16 *)v5 + 1) < v770 )
          {
            if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
              || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_962;
            }
            v772 = RdpX_GetActivityIdPrefix(v765, v764, v766, v767);
            v773 = 187;
LABEL_961:
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v773,
              &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v772,
              -2147418113);
LABEL_962:
            RemoteAppWindow = -2147418113;
LABEL_963:
            RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v990);
            goto LABEL_940;
          }
          v774 = *((unsigned __int8 *)v5 + v768 + 27);
          LODWORD(v978) = *((unsigned __int8 *)v5 + v768 + 26);
          v963 = *(unsigned __int16 *)((char *)v5 + v768 + 24);
          if ( RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v971) )
          {
            v775 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v971);
            v776 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v775 + 24LL))(v775);
          }
          else
          {
            v776 = &sourceString;
          }
          LODWORD(cchToCopy) = *((_DWORD *)v5 + 2);
          RdpRemoteAppCore::LogRemoteAppEventF(
            (char *)v771 + 16,
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
            v776,
            v963,
            v978,
            v774);
          v777 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v969);
          v778 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, void *))(*(_QWORD *)v777 + 56LL);
          v779 = CacCommon::Rect<int>::Rect<int>(v990);
          RemoteAppWindow = v778(
                              v777,
                              *((unsigned __int8 *)v5 + v768 + 26),
                              *(unsigned __int16 *)((char *)v5 + v768 + 24),
                              v779);
          if ( RemoteAppWindow < 0 )
          {
            if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
              || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_963;
            }
            v784 = RdpX_GetActivityIdPrefix(v781, v780, v782, v783);
            v785 = 188;
            goto LABEL_972;
          }
        }
        else
        {
          v787 = v726 + 20;
          v771 = v973;
          if ( v769 < v787 )
            RdpRemoteAppCore::LogRemoteAppError(
              (char *)v973 + 16,
              L"Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Change PDU",
              2147549183LL,
              0,
              0);
          v788 = *((unsigned __int16 *)v5 + 1);
          if ( (unsigned int)v788 < v787 )
          {
            if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
              || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_962;
            }
            v772 = RdpX_GetActivityIdPrefix(v765, v788, v766, v767);
            v773 = 189;
            goto LABEL_961;
          }
          if ( (*((_BYTE *)v5 + v768 + 27) & 2) != 0 )
          {
            LOBYTE(v765) = *((_BYTE *)v5 + v768 + 32);
            v743 = *(_WORD *)((char *)v5 + v768 + 34);
            LOWORD(v963) = v765;
          }
          else
          {
            LOWORD(v963) = 32;
          }
          v789 = *(unsigned int *)((char *)v5 + v768 + 36);
          v790 = v743;
          v791 = v743 + *(_DWORD *)((char *)v5 + v768 + 40);
          v983 = v789;
          v984 = v743;
          v792 = v789 + v791 + v787;
          if ( (unsigned int)v788 < v792 )
            RdpRemoteAppCore::LogRemoteAppError(
              (char *)v771 + 16,
              L"Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Change PDU",
              2147549183LL,
              0,
              0);
          if ( *((unsigned __int16 *)v5 + 1) < v792 )
          {
            if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
              || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_962;
            }
            v772 = RdpX_GetActivityIdPrefix(v790, v788, v789, v767);
            v773 = 190;
            goto LABEL_961;
          }
          v973 = (struct tagTS_RAIL_PDU *)((char *)v5 + v768 + v743 + 44);
          LODWORD(v978) = *(_DWORD *)((char *)v5 + v768 + 40);
          v1014 = *(_DWORD *)((char *)v5 + v768 + 36);
          v1010 = *(unsigned __int16 *)((char *)v5 + v768 + 34);
          v1011 = *((unsigned __int8 *)v5 + v768 + 32);
          v1012 = *(unsigned __int16 *)((char *)v5 + v768 + 30);
          v1013 = *(unsigned __int16 *)((char *)v5 + v768 + 28);
          v1016 = *((unsigned __int8 *)v5 + v768 + 27);
          v1015 = *((unsigned __int8 *)v5 + v768 + 26);
          v985 = *(unsigned __int16 *)((char *)v5 + v768 + 24);
          if ( RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v971) )
          {
            v793 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v971);
            v794 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v793 + 24LL))(v793);
          }
          else
          {
            v794 = &sourceString;
          }
          LODWORD(cchToCopy) = *((_DWORD *)v5 + 2);
          RdpRemoteAppCore::LogRemoteAppEventF(
            (char *)v771 + 16,
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
            v794,
            v985,
            v1015,
            v1016,
            v1013,
            v1012,
            v1011,
            v1010,
            v1014,
            v978);
          v795 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v969);
          v796 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, char *, _DWORD, _DWORD, char *, int, RdpRemoteAppCore *, _DWORD, char *, _DWORD, void *))(*(_QWORD *)v795 + 64LL);
          v797 = CacCommon::Rect<int>::Rect<int>(v990);
          v798 = (char *)v973 + v983;
          LOBYTE(v798) = v963;
          RemoteAppWindow = v796(
                              v795,
                              *((unsigned __int8 *)v5 + v768 + 26),
                              *(unsigned __int16 *)((char *)v5 + v768 + 24),
                              v798,
                              *(unsigned __int16 *)((char *)v5 + v768 + 28),
                              *(unsigned __int16 *)((char *)v5 + v768 + 30),
                              (char *)v5 + v768 + 44,
                              v984,
                              v973,
                              *(_DWORD *)((char *)v5 + v768 + 36),
                              (char *)v973 + v983,
                              *(_DWORD *)((char *)v5 + v768 + 40),
                              v797);
          if ( RemoteAppWindow < 0 )
          {
            if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
              || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_963;
            }
            v784 = RdpX_GetActivityIdPrefix(v800, v799, v801, v802);
            v785 = 191;
LABEL_972:
            v786 = "CreateCachedIcon failed";
LABEL_973:
            LODWORD(v943) = RemoteAppWindow;
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v785,
              (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v784,
              (__int64)v786,
              v943);
            goto LABEL_963;
          }
        }
        v803 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v962);
        v804 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v803 + 80LL);
        v805 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v990);
        RemoteAppWindow = v804(v803, v805);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_963;
          }
          v784 = RdpX_GetActivityIdPrefix(v807, v806, v808, v809);
          v785 = 192;
          v786 = "spShellNotify->SetIcon failed";
          goto LABEL_973;
        }
        RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v990);
      }
      else
      {
        v771 = v973;
        if ( RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v971) )
        {
          v810 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v971);
          v811 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v810 + 24LL))(v810);
        }
        else
        {
          v811 = &sourceString;
        }
        LODWORD(cchToCopy) = *((_DWORD *)v5 + 2);
        RdpRemoteAppCore::LogRemoteAppEventF(
          (char *)v771 + 16,
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
          v811);
      }
      v812 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v962);
      if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v812 + 72LL))(v812) )
        goto LABEL_940;
      v813 = (struct RdpXInterfaceShellNotifyInformation *)RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v962);
      v814 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v962);
      v815 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v814 + 72LL))(v814);
      RemoteAppWindow = RdpRemoteAppCore::OnShellNotifyInformation(v771, v815, v813);
      if ( RemoteAppWindow >= 0
        || WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_940;
      }
      v750 = RdpX_GetActivityIdPrefix(v817, v816, v818, v819);
      v751 = 193;
      v752 = "OnShellNotifyInformation failed";
LABEL_939:
      LODWORD(v943) = RemoteAppWindow;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v751,
        (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
        v750,
        (__int64)v752,
        v943);
LABEL_940:
      RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v971);
      goto LABEL_914;
    }
    RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v961);
    RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v964);
    if ( *((_WORD *)v5 + 1) < 0x18u )
      RdpRemoteAppCore::LogRemoteAppError(
        (char *)v6 + 16,
        L"Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Create PDU",
        2147549183LL,
        0,
        0);
    v823 = *((unsigned __int16 *)v5 + 1);
    if ( (unsigned int)v823 < 0x18 )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_1023;
      }
      v824 = RdpX_GetActivityIdPrefix(v823, v820, v821, v822);
      v825 = 165;
LABEL_1022:
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v825,
        &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
        v824,
        -2147418113);
LABEL_1023:
      RemoteAppWindow = -2147418113;
LABEL_1024:
      TCntPtr<ITSViewerRecorder>::SafeRelease(v964);
      v636 = v961;
      goto LABEL_1025;
    }
    v826 = *((unsigned __int16 *)v5 + 6) + 24;
    if ( (unsigned int)v823 < v826 )
      RdpRemoteAppCore::LogRemoteAppError(
        (char *)v6 + 16,
        L"Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Create PDU",
        2147549183LL,
        0,
        0);
    if ( *((unsigned __int16 *)v5 + 1) < v826 )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_1023;
      }
      v824 = RdpX_GetActivityIdPrefix(v823, v820, v821, v822);
      v825 = 166;
      goto LABEL_1022;
    }
    v827 = (struct ITSWndPluginEx **)CacCommon::Rect<int>::Rect<int>(v964);
    RemoteAppWindow = RdpRemoteAppCore::GetWndPlugin((RdpRemoteAppCore *)((char *)v6 - 48), v827);
    if ( RemoteAppWindow < 0 )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_1024;
      }
      v832 = RdpX_GetActivityIdPrefix(v829, v828, v830, v831);
      v833 = 167;
      v834 = "GetWndPlugin failed";
      goto LABEL_1038;
    }
    v835 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v964);
    v836 = *(int (__fastcall **)(__int64, _QWORD, _QWORD, void *))(*(_QWORD *)v835 + 72LL);
    v837 = CacCommon::Rect<int>::Rect<int>(v961);
    if ( v836(v835, *((unsigned int *)v5 + 1), *((unsigned int *)v5 + 2), v837) >= 0 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v850 = *((_DWORD *)v5 + 2);
        v851 = *((_DWORD *)v5 + 1);
        v852 = RdpX_GetActivityIdPrefix(v839, v838, v840, v841);
        WPP_SF_DLD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          169,
          &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v852,
          v851,
          v850);
      }
      v853 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v961);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v853 + 128LL))(v853);
    }
    else
    {
      v842 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v964);
      v843 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, void *))(*(_QWORD *)v842 + 80LL);
      v844 = CacCommon::Rect<int>::Rect<int>(v961);
      RemoteAppWindow = v843(v842, *((unsigned int *)v5 + 1), *((unsigned int *)v5 + 2), v844);
      if ( RemoteAppWindow < 0 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_1024;
        }
        v832 = RdpX_GetActivityIdPrefix(v846, v845, v847, v848);
        v833 = 168;
        v834 = "CreateShellNotifyInfo failed";
LABEL_1038:
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v833,
          (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v832,
          (__int64)v834,
          RemoteAppWindow);
        goto LABEL_1024;
      }
      v849 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v961);
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v849 + 120LL))(v849, 1);
    }
    v854 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v964);
    if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v854 + 136LL))(v854) )
    {
      v855 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v961);
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v855 + 136LL))(v855, 2);
    }
    v856 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v961);
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v856 + 112LL))(v856, 4);
    RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v972);
    if ( *((_WORD *)v5 + 6) )
    {
      v857 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v961);
      RemoteAppWindow = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v857 + 88LL))(
                          v857,
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
        v862 = RdpX_GetActivityIdPrefix(v859, v858, v860, v861);
        v863 = 170;
        v864 = "CreateShellNotifyInfo->SetTip failed";
        goto LABEL_1059;
      }
      v865 = CacCommon::Rect<int>::Rect<int>(v972);
      v866 = RdpX_Strings_CreateConstXChar16StringWithSpecifiedSize(
               *((unsigned __int16 *)v5 + 6) >> 1,
               (char *)v5 + 24,
               v865);
      RemoteAppWindow = MapXResultToHR(v866);
      if ( RemoteAppWindow < 0 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_1060;
        }
        v862 = RdpX_GetActivityIdPrefix(v868, v867, v869, v870);
        v863 = 171;
        v864 = "RdpX_Strings_CreateConstXChar16StringWithSpecifiedSize failed";
        goto LABEL_1059;
      }
    }
    if ( (*((_BYTE *)v5 + 20) & 4) != 0 )
    {
      v871 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v961);
      RemoteAppWindow = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v871 + 104LL))(
                          v871,
                          *((unsigned int *)v5 + 4));
      if ( RemoteAppWindow < 0 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_1060;
        }
        v862 = RdpX_GetActivityIdPrefix(v873, v872, v874, v875);
        v863 = 172;
        v864 = "CreateShellNotifyInfo->SetWSNState failed";
        goto LABEL_1059;
      }
    }
    if ( *((_BYTE *)v5 + 14) )
    {
      RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>::RdpXSPtr<RdpXInterfaceShellNotifyInformationInternal>(v991);
      v880 = *((unsigned __int16 *)v5 + 6);
      v881 = *((unsigned __int16 *)v5 + 1);
      if ( *((_BYTE *)v5 + 15) )
      {
        v882 = v826 + 4;
        v883 = v973;
        if ( v881 < v882 )
          RdpRemoteAppCore::LogRemoteAppError(
            (char *)v973 + 16,
            L"Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Create PDU",
            2147549183LL,
            0,
            0);
        if ( *((unsigned __int16 *)v5 + 1) < v882 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_1082;
          }
          v884 = RdpX_GetActivityIdPrefix(v877, v876, v878, v879);
          v885 = 173;
LABEL_1081:
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v885,
            &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
            v884,
            -2147418113);
LABEL_1082:
          RemoteAppWindow = -2147418113;
LABEL_1083:
          RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v991);
          goto LABEL_1060;
        }
        v984 = *((unsigned __int8 *)v5 + v880 + 27);
        v983 = *((unsigned __int8 *)v5 + v880 + 26);
        v985 = *(unsigned __int16 *)((char *)v5 + v880 + 24);
        if ( RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v972) )
        {
          v886 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v972);
          v887 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v886 + 24LL))(v886);
        }
        else
        {
          v887 = &sourceString;
        }
        LODWORD(v943) = *((unsigned __int8 *)v5 + 14);
        LODWORD(cchToCopy) = *((_DWORD *)v5 + 2);
        RdpRemoteAppCore::LogRemoteAppEventF(
          (char *)v883 + 16,
          L"NotifyIconCreateRailOrderReceived_Cached: WindowId=0x%x, NotifyIconId=0x%x, NumIcons=%hhu, IsCachedIcon=%hhu, "
           "StateFlags=0x%x, PDUFlags=0x%x, ToolTipBytes=%hu, ToolTip=%s, CacheEntry=0x%hx, CacheId=0x%hhx, IconFlags=0x%hhx",
          0,
          *((unsigned int *)v5 + 1),
          cchToCopy,
          v943,
          *((unsigned __int8 *)v5 + 15),
          *((_DWORD *)v5 + 4),
          *((_DWORD *)v5 + 5),
          *((unsigned __int16 *)v5 + 6),
          v887,
          v985,
          v983,
          v984);
        v888 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v964);
        v889 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, void *))(*(_QWORD *)v888 + 56LL);
        v890 = CacCommon::Rect<int>::Rect<int>(v991);
        RemoteAppWindow = v889(
                            v888,
                            *((unsigned __int8 *)v5 + v880 + 26),
                            *(unsigned __int16 *)((char *)v5 + v880 + 24),
                            v890);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_1083;
          }
          v895 = RdpX_GetActivityIdPrefix(v892, v891, v893, v894);
          v896 = 174;
          goto LABEL_1092;
        }
      }
      else
      {
        v898 = v826 + 20;
        v883 = v973;
        if ( v881 < v898 )
          RdpRemoteAppCore::LogRemoteAppError(
            (char *)v973 + 16,
            L"Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Create PDU",
            2147549183LL,
            0,
            0);
        v899 = *((unsigned __int16 *)v5 + 1);
        if ( (unsigned int)v899 < v898 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_1082;
          }
          v884 = RdpX_GetActivityIdPrefix(v877, v876, v878, v899);
          v885 = 175;
          goto LABEL_1081;
        }
        if ( (*((_BYTE *)v5 + v880 + 27) & 2) != 0 )
        {
          LOBYTE(v876) = *((_BYTE *)v5 + v880 + 32);
          v900 = *(unsigned __int16 *)((char *)v5 + v880 + 34);
          LOWORD(v963) = v876;
        }
        else
        {
          v900 = 0;
          LOWORD(v963) = 32;
        }
        v1014 = *(_DWORD *)((char *)v5 + v880 + 36);
        v901 = (unsigned __int16)v900 + v1014;
        LODWORD(v978) = v900;
        v902 = *(_DWORD *)((char *)v5 + v880 + 40) + v901 + v898;
        LODWORD(v973) = (unsigned __int16)v900;
        if ( (unsigned int)v899 < v902 )
        {
          RdpRemoteAppCore::LogRemoteAppError(
            (char *)v883 + 16,
            L"Invalid size of TS_RAIL_ORDER_NOTIFYICON_BODY for Create PDU",
            2147549183LL,
            0,
            0);
          v900 = (unsigned int)v978;
        }
        if ( *((unsigned __int16 *)v5 + 1) < v902 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_1082;
          }
          v884 = RdpX_GetActivityIdPrefix(v901, v876, v900, v899);
          v885 = 176;
          goto LABEL_1081;
        }
        v978 = (__int64)v5 + v880 + (unsigned __int16)v900 + 44;
        v984 = *(_DWORD *)((char *)v5 + v880 + 40);
        v983 = *(_DWORD *)((char *)v5 + v880 + 36);
        v985 = *(unsigned __int16 *)((char *)v5 + v880 + 34);
        v1015 = *((unsigned __int8 *)v5 + v880 + 32);
        v1016 = *(unsigned __int16 *)((char *)v5 + v880 + 30);
        v1013 = *(unsigned __int16 *)((char *)v5 + v880 + 28);
        v1012 = *((unsigned __int8 *)v5 + v880 + 27);
        v1011 = *((unsigned __int8 *)v5 + v880 + 26);
        v1010 = *(unsigned __int16 *)((char *)v5 + v880 + 24);
        if ( RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v972) )
        {
          v903 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v972);
          v904 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v903 + 24LL))(v903);
        }
        else
        {
          v904 = &sourceString;
        }
        LODWORD(v943) = *((unsigned __int8 *)v5 + 14);
        LODWORD(cchToCopy) = *((_DWORD *)v5 + 2);
        RdpRemoteAppCore::LogRemoteAppEventF(
          (char *)v883 + 16,
          L"NotifyIconCreateRailOrderReceived_NonCached: WindowId=0x%x, NotifyIconId=0x%x, NumIcons=%hhu, IsCachedIcon=%hh"
           "u, StateFlags=0x%x, PDUFlags=0x%x, ToolTipBytes=%hu, ToolTip=%s, CacheEntry=0x%hx, CacheId=0x%hhx, IconFlags="
           "0x%hhx, Width=%hu, Height=%hu, Bpp=%hhu, ColorTableBytes=%hu, BitsMaskBytes=%u, BitsColorBytes=%u",
          0,
          *((unsigned int *)v5 + 1),
          cchToCopy,
          v943,
          *((unsigned __int8 *)v5 + 15),
          *((_DWORD *)v5 + 4),
          *((_DWORD *)v5 + 5),
          *((unsigned __int16 *)v5 + 6),
          v904,
          v1010,
          v1011,
          v1012,
          v1013,
          v1016,
          v1015,
          v985,
          v983,
          v984);
        v905 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v964);
        v906 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64, _DWORD, _DWORD, char *, _DWORD, __int64, _DWORD, __int64, _DWORD, void *))(*(_QWORD *)v905 + 64LL);
        v907 = CacCommon::Rect<int>::Rect<int>(v991);
        v908 = v978 + v1014;
        LOBYTE(v908) = v963;
        RemoteAppWindow = v906(
                            v905,
                            *((unsigned __int8 *)v5 + v880 + 26),
                            *(unsigned __int16 *)((char *)v5 + v880 + 24),
                            v908,
                            *(unsigned __int16 *)((char *)v5 + v880 + 28),
                            *(unsigned __int16 *)((char *)v5 + v880 + 30),
                            (char *)v5 + v880 + 44,
                            (_DWORD)v973,
                            v978,
                            *(_DWORD *)((char *)v5 + v880 + 36),
                            v978 + v1014,
                            *(_DWORD *)((char *)v5 + v880 + 40),
                            v907);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_1083;
          }
          v895 = RdpX_GetActivityIdPrefix(v910, v909, v911, v912);
          v896 = 177;
LABEL_1092:
          v897 = "CreateCachedIcon failed";
LABEL_1093:
          LODWORD(v943) = RemoteAppWindow;
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v896,
            (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
            v895,
            (__int64)v897,
            v943);
          goto LABEL_1083;
        }
      }
      v913 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v961);
      v914 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v913 + 80LL);
      v915 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v991);
      RemoteAppWindow = v914(v913, v915);
      if ( RemoteAppWindow < 0 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_1083;
        }
        v895 = RdpX_GetActivityIdPrefix(v917, v916, v918, v919);
        v896 = 178;
        v897 = "spShellNotify->SetIcon failed";
        goto LABEL_1093;
      }
      RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v991);
    }
    else
    {
      v883 = v973;
      if ( RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v972) )
      {
        v920 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v972);
        v921 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v920 + 24LL))(v920);
      }
      else
      {
        v921 = &sourceString;
      }
      LODWORD(v943) = *((unsigned __int8 *)v5 + 14);
      LODWORD(cchToCopy) = *((_DWORD *)v5 + 2);
      RdpRemoteAppCore::LogRemoteAppEventF(
        (char *)v883 + 16,
        L"NotifyIconCreateRailOrderReceived_NoIcons: WindowId=0x%x, NotifyIconId=0x%x, NumIcons=%hhu, IsCachedIcon=%hhu, S"
         "tateFlags=0x%x, PDUFlags=0x%x, ToolTipBytes=%hu, ToolTip=%s",
        0,
        *((unsigned int *)v5 + 1),
        cchToCopy,
        v943,
        *((unsigned __int8 *)v5 + 15),
        *((_DWORD *)v5 + 4),
        *((_DWORD *)v5 + 5),
        *((unsigned __int16 *)v5 + 6),
        v921);
    }
    v922 = (struct RdpXInterfaceShellNotifyInformation *)RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v961);
    v923 = RdpXSPtr<RdpXInterfaceIcon>::operator RdpXInterfaceIcon *(v961);
    v924 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v923 + 72LL))(v923);
    RemoteAppWindow = RdpRemoteAppCore::OnShellNotifyInformation(v883, v924, v922);
    if ( RemoteAppWindow >= 0
      || WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_1060;
    }
    v862 = RdpX_GetActivityIdPrefix(v926, v925, v927, v928);
    v863 = 179;
    v864 = "OnShellNotifyInformation failed";
LABEL_1059:
    LODWORD(v943) = RemoteAppWindow;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v863,
      (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
      v862,
      (__int64)v864,
      v943);
LABEL_1060:
    RdpXSPtr<RdpXInterfaceRemoteAppWindow>::~RdpXSPtr<RdpXInterfaceRemoteAppWindow>(v972);
    goto LABEL_1024;
  }
  if ( (_DWORD)v20 == 24 )
  {
    v250 = *((unsigned __int16 *)v5 + 1);
    if ( (_WORD)v250 != 1052 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v251 = RdpX_GetActivityIdPrefix(v20, v17, v18, v19);
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v251, v250);
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
      v252 = *((_DWORD *)v5 + 132);
      v253 = *((_DWORD *)v5 + 1);
      v254 = RdpX_GetActivityIdPrefix(v20, v17, v18, v19);
      WPP_SF_DDDS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        86,
        (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
        v254,
        v253,
        v252,
        (__int64)v5 + 532);
    }
    FileNameW = CUT::PathFindFileNameW((const unsigned __int16 *)v5 + 266);
    v256 = *((_DWORD *)v5 + 132);
    v257 = FileNameW;
    v258 = CUT::PathFindFileNameW((const unsigned __int16 *)v5 + 4);
    LODWORD(v943) = v256;
    RdpRemoteAppCore::LogRemoteAppEventF(
      (char *)v973 + 16,
      L"GetAppIdRespExRailOrderReceived: WindowId=0x%x, CensoredAppId=%s, ProcessId=%u, CensoredProcessImageName=%s",
      0,
      *((unsigned int *)v5 + 1),
      v258,
      v943,
      v257);
    v259 = (RdpRemoteAppCore *)((char *)v973 - 48);
    v994 = 0;
    RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow(
                        (RdpRemoteAppCore *)((char *)v973 - 48),
                        *((_DWORD *)v5 + 1),
                        &v994);
    if ( RemoteAppWindow >= 0 )
    {
      updated = RdpRemoteAppCore::UpdateProcessInfo(
                  v259,
                  v994,
                  *((_DWORD *)v5 + 132),
                  (const unsigned __int16 *)v5 + 266);
      if ( updated < 0
        && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v270 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v266, v268, v269);
        LODWORD(v947) = updated;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          88,
          (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v270,
          (__int64)"Failed to set process info",
          v947);
      }
      RemoteAppWindow = RdpRemoteAppCore::UpdateAppID(v259, v994, (const unsigned __int16 *)v5 + 4);
      if ( RemoteAppWindow < 0
        && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v275 = RdpX_GetActivityIdPrefix(v272, v271, v273, v274);
        LODWORD(v947) = RemoteAppWindow;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          89,
          (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v275,
          (__int64)"UpdateAppID failed",
          v947);
      }
      v42 = v994;
      if ( v994 )
      {
        v994 = 0;
        goto LABEL_106;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v264 = *((_DWORD *)v5 + 1);
        v265 = RdpX_GetActivityIdPrefix(v261, v260, v262, v263);
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v265, v264);
      }
      v42 = v994;
      if ( v994 )
      {
        v994 = 0;
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
        v140 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v141 = RdpX_GetActivityIdPrefix(v20, v97, v18, v19);
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 112, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v141);
          v140 = WPP_GLOBAL_Control;
        }
        v142 = *((unsigned __int16 *)v5 + 1);
        if ( (_WORD)v142 != 20 )
        {
          if ( v140 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v140[7] & 1) != 0 && *((_BYTE *)v140 + 25) >= 2u )
          {
            v143 = RdpX_GetActivityIdPrefix(v20, v97, v18, v19);
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              113,
              &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v143,
              v142);
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
          v144 = *((_DWORD *)v5 + 1);
          v145 = *((_DWORD *)v5 + 4) == 0;
          v146 = *((_DWORD *)v5 + 3);
          v1034[1] = *((_DWORD *)v5 + 2);
          v1034[2] = v146;
          v1034[3] = !v145;
          v1034[0] = v144 != 0;
          (*(void (__fastcall **)(_QWORD, _DWORD *))(**((_QWORD **)v6 + 17) + 48LL))(*((_QWORD *)v6 + 17), v1034);
        }
        return 0;
      }
      v21 = (unsigned int)(v20 - 19);
      if ( (_DWORD)v20 == 19 )
        goto LABEL_197;
      v98 = (unsigned int)(v20 - 20);
      if ( (_DWORD)v20 == 20 )
      {
        v123 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v124 = RdpX_GetActivityIdPrefix(v20, v98, v18, v19);
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 114, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v124);
          v123 = WPP_GLOBAL_Control;
        }
        v125 = *((unsigned __int16 *)v5 + 1);
        if ( v125 == 8 )
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
        if ( v123 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v123[7] & 0x40) != 0 && *((_BYTE *)v123 + 25) >= 2u )
        {
          v126 = RdpX_GetActivityIdPrefix(v20, v98, v18, v19);
          WPP_SF_DdL(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            115,
            &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
            v126,
            v125,
            8);
        }
        RemoteAppWindow = -2147418113;
        LODWORD(v943) = 8;
        v111 = 2147549183LL;
        v112 = L"Invalid size for TS_RAIL_ORDER_ZORDER_SYNC: [%d]. Expected size: [%lu]";
LABEL_1150:
        LODWORD(cchToCopy) = *((unsigned __int16 *)v5 + 1);
        RdpRemoteAppCore::LogRemoteAppErrorF((char *)v6 + 16, v112, v111, 0, cchToCopy, v943);
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
        LODWORD(v943) = 9;
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
        v1026 = 0;
        v1021 = 0;
        RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow(
                            (RdpRemoteAppCore *)((char *)v6 - 48),
                            *((_DWORD *)v5 + 1),
                            &v1026);
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
          v42 = v1026;
          if ( v1026 )
          {
            v1026 = 0;
            goto LABEL_106;
          }
          return (unsigned int)RemoteAppWindow;
        }
        DesktopRemoteAppWindow = RdpRemoteAppCore::GetDesktopRemoteAppWindow(
                                   (RdpRemoteAppCore *)((char *)v6 - 48),
                                   v1026);
        RdpXSPtr<RdpXInterfaceLayerManager>::operator=(&v1021, DesktopRemoteAppWindow);
        if ( v1021 )
        {
          (*(void (__fastcall **)(__int64, bool))(*(_QWORD *)v1021 + 440LL))(v1021, *((_BYTE *)v5 + 8) != 0);
          v122 = v1021;
          if ( v1021 )
          {
            v1021 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v122 + 8LL))(v122);
          }
        }
        RdpXSPtr<RdpXTapVcCallbackItem>::SafeRelease(&v1026, v121);
      }
      return 0;
    }
    v147 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v148 = RdpX_GetActivityIdPrefix(v20, v96, v18, v19);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v148);
      v147 = WPP_GLOBAL_Control;
    }
    v149 = *((unsigned __int16 *)v5 + 1);
    if ( (unsigned __int16)v149 < 0x10u )
    {
      if ( v147 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v147[7] & 1) != 0 && *((_BYTE *)v147 + 25) >= 2u )
      {
        v150 = RdpX_GetActivityIdPrefix(v20, v96, v18, v19);
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v150, v149);
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
    v152 = *((unsigned int *)v5 + 2);
    v1030[1] = *((_DWORD *)v5 + 2);
    v153 = *((_DWORD *)v5 + 1);
    v1030[0] = v153;
    if ( v153 == 5 )
    {
      v1032 = *((_DWORD *)v5 + 3);
      v1031 = 0;
      goto LABEL_242;
    }
    if ( (unsigned int)(v153 - 1) <= 3 )
    {
      v1031 = *((_DWORD *)v5 + 3);
      v1032 = 0;
LABEL_242:
      v154 = *((_QWORD *)v6 + 15);
      if ( v154 )
        (*(void (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v154 + 160LL))(v154, v1030);
      return 0;
    }
    if ( v153 == 6 )
    {
      v1022 = 0;
      RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow((RdpRemoteAppCore *)((char *)v6 - 48), v152, &v1022);
      if ( RemoteAppWindow < 0 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v159 = *((_DWORD *)v5 + 2);
          v160 = RdpX_GetActivityIdPrefix(v156, v155, v157, v158);
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            95,
            &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
            v160,
            v159);
        }
        v42 = v1022;
        if ( v1022 )
        {
          v1022 = 0;
          goto LABEL_106;
        }
        return (unsigned int)RemoteAppWindow;
      }
      (*(void (__fastcall **)(struct RdpXInterfaceRemoteAppWindow *, __int64))(*(_QWORD *)v1022 + 264LL))(
        v1022,
        0x100000);
      v161 = v1022;
      if ( v1022 )
      {
        v1022 = 0;
LABEL_387:
        (*(void (__fastcall **)(struct RdpXInterfaceRemoteAppWindow *))(*(_QWORD *)v161 + 8LL))(v161);
        return 0;
      }
      return 0;
    }
    if ( v153 == 7 )
    {
      v1023 = 0;
      RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow((RdpRemoteAppCore *)((char *)v6 - 48), v152, &v1023);
      if ( RemoteAppWindow < 0 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v166 = *((_DWORD *)v5 + 2);
          v167 = RdpX_GetActivityIdPrefix(v163, v162, v164, v165);
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            96,
            &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
            v167,
            v166);
        }
        v42 = v1023;
        if ( v1023 )
        {
          v1023 = 0;
          goto LABEL_106;
        }
        return (unsigned int)RemoteAppWindow;
      }
      (*(void (__fastcall **)(struct RdpXInterfaceRemoteAppWindow *, __int64))(*(_QWORD *)v1023 + 264LL))(
        v1023,
        0x200000);
      v161 = v1023;
      if ( v1023 )
      {
        v1023 = 0;
        goto LABEL_387;
      }
      return 0;
    }
    if ( v153 != 8 )
    {
      if ( v153 == 9 )
      {
        v1007 = 0;
        v993 = 0;
        v214 = (unsigned int)*((unsigned __int16 *)v5 + 6) + 14;
        if ( *((unsigned __int16 *)v5 + 1) >= (unsigned int)v214 )
        {
          RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow((RdpRemoteAppCore *)((char *)v6 - 48), v152, &v1007);
          if ( RemoteAppWindow >= 0 )
          {
            v222 = RdpRemoteAppCore::GetDesktopRemoteAppWindow((RdpRemoteAppCore *)((char *)v6 - 48), v1007);
            RdpXSPtr<RdpXInterfaceLayerManager>::operator=(&v993, v222);
            v223 = v993;
            if ( v993 )
            {
              if ( (unsigned __int16)(*((_WORD *)v5 + 6) - 3) <= 0x205u )
              {
                v224 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v993 + 424LL))(
                         v993,
                         (__int64)v5 + 14,
                         *((unsigned __int16 *)v5 + 6) >> 1);
                v226 = MapXResultToHR(v224);
                if ( v226 < 0
                  && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                  && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v229 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v225, v227, v228);
                  LODWORD(v946) = v226;
                  WPP_SF_DsD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    108,
                    (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
                    v229,
                    (__int64)"SetOverlayDesc failed",
                    v946);
                }
                v223 = v993;
              }
              if ( v223 )
              {
                v993 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v223 + 8LL))(v223);
              }
            }
            v161 = v1007;
            if ( !v1007 )
              return 0;
            v1007 = 0;
            goto LABEL_387;
          }
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v220 = *((_DWORD *)v5 + 2);
            v221 = RdpX_GetActivityIdPrefix(v217, v216, v218, v219);
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              107,
              &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v221,
              v220);
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v215 = RdpX_GetActivityIdPrefix(v214, 0, v151, v152);
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              106,
              &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v215,
              -2147418113);
          }
          RemoteAppWindow = -2147418113;
        }
        v42 = v1007;
        if ( !v1007 )
          return (unsigned int)RemoteAppWindow;
        v1007 = 0;
        goto LABEL_106;
      }
      if ( v153 == 10 )
      {
        v1024 = 0;
        v998 = 0;
        RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow((RdpRemoteAppCore *)((char *)v6 - 48), v152, &v1024);
        if ( RemoteAppWindow < 0 )
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v234 = *((_DWORD *)v5 + 2);
            v235 = RdpX_GetActivityIdPrefix(v231, v230, v232, v233);
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              109,
              &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v235,
              v234);
          }
          v42 = v1024;
          if ( v1024 )
          {
            v1024 = 0;
            goto LABEL_106;
          }
          return (unsigned int)RemoteAppWindow;
        }
        v236 = RdpRemoteAppCore::GetDesktopRemoteAppWindow((RdpRemoteAppCore *)((char *)v6 - 48), v1024);
        RdpXSPtr<RdpXInterfaceLayerManager>::operator=(&v998, v236);
        if ( v998 )
        {
          v237 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v998 + 416LL))(v998, 0);
          v239 = MapXResultToHR(v237);
          if ( v239 < 0
            && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v242 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v238, v240, v241);
            LODWORD(v946) = v239;
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              110,
              (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v242,
              (__int64)"UpdateOverlayIcon failed",
              v946);
          }
          v243 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v998 + 424LL))(v998, 0, 0);
          v245 = MapXResultToHR(v243);
          if ( v245 < 0
            && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v248 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v244, v246, v247);
            LODWORD(v946) = v245;
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              111,
              (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v248,
              (__int64)"SetOverlayDesc failed",
              v946);
          }
          v249 = v998;
          if ( v998 )
          {
            v998 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v249 + 8LL))(v249);
          }
        }
        v161 = v1024;
        if ( v1024 )
        {
          v1024 = 0;
          goto LABEL_387;
        }
      }
      return 0;
    }
    v168 = (RdpRemoteAppCore *)((char *)v6 - 48);
    v970 = 0;
    v967 = 0;
    v965 = 0;
    v966 = 0;
    v973 = (RdpRemoteAppCore *)((char *)v6 - 48);
    RemoteAppWindow = RdpRemoteAppCore::GetWndPlugin((RdpRemoteAppCore *)((char *)v6 - 48), &v965);
    if ( RemoteAppWindow < 0 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v173 = RdpX_GetActivityIdPrefix(v170, v169, v171, v172);
        v174 = 97;
        v175 = "GetWndPlugin failed";
LABEL_271:
        LODWORD(v946) = RemoteAppWindow;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v174,
          (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v173,
          (__int64)v175,
          v946);
      }
LABEL_272:
      v176 = v966;
      if ( v966 )
      {
        v966 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v176 + 8LL))(v176);
      }
      v177 = v965;
      if ( v965 )
      {
        v965 = 0;
        (*(void (__fastcall **)(struct ITSWndPluginEx *))(*(_QWORD *)v177 + 16LL))(v177);
      }
      v178 = v967;
      if ( v967 )
      {
        v967 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v178 + 8LL))(v178);
      }
      v42 = v970;
      if ( v970 )
      {
        v970 = 0;
        goto LABEL_106;
      }
      return (unsigned int)RemoteAppWindow;
    }
    RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow(v168, *((_DWORD *)v5 + 2), &v970);
    if ( RemoteAppWindow < 0 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v183 = *((_DWORD *)v5 + 2);
        v184 = RdpX_GetActivityIdPrefix(v180, v179, v181, v182);
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v184, v183);
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
        v185 = RdpX_GetActivityIdPrefix(v180, v179, v181, v182);
        v186 = 99;
LABEL_291:
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v186,
          &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v185,
          -2147418113);
LABEL_292:
        RemoteAppWindow = -2147418113;
        goto LABEL_272;
      }
      RemoteAppWindow = (*(__int64 (__fastcall **)(struct ITSWndPluginEx *, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v965 + 56LL))(
                          v965,
                          *((unsigned __int8 *)v5 + 18),
                          *((unsigned __int16 *)v5 + 8),
                          &v966);
      if ( RemoteAppWindow < 0 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_272;
        }
        v173 = RdpX_GetActivityIdPrefix(v188, v187, v189, v190);
        v174 = 100;
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
        v185 = RdpX_GetActivityIdPrefix(v180, v179, v181, v182);
        v186 = 101;
        goto LABEL_291;
      }
      if ( (*((_BYTE *)v5 + 19) & 2) != 0 )
      {
        LOBYTE(v182) = *((_BYTE *)v5 + 24);
        v191 = *((unsigned __int16 *)v5 + 13);
      }
      else
      {
        v191 = 0;
        LOWORD(v182) = 32;
      }
      v192 = *((unsigned int *)v5 + 7);
      v193 = v192 + *((_DWORD *)v5 + 8) + 36;
      LODWORD(v978) = (unsigned __int16)v191;
      v194 = v193 + (unsigned int)(unsigned __int16)v191;
      if ( *((unsigned __int16 *)v5 + 1) < (unsigned int)v194 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_292;
        }
        v185 = RdpX_GetActivityIdPrefix(v194, v191, v192, v182);
        v186 = 102;
        goto LABEL_291;
      }
      RemoteAppWindow = (*(__int64 (__fastcall **)(struct ITSWndPluginEx *, _QWORD, _QWORD, __int64, _DWORD, _DWORD, __int64, _DWORD, __int64, _DWORD, __int64, _DWORD, __int64 *))(*(_QWORD *)v965 + 64LL))(
                          v965,
                          *((unsigned __int8 *)v5 + 18),
                          *((unsigned __int16 *)v5 + 8),
                          v182,
                          *((unsigned __int16 *)v5 + 10),
                          *((unsigned __int16 *)v5 + 11),
                          (__int64)v5 + 36,
                          v978,
                          (__int64)v5 + (unsigned __int16)v191 + 36,
                          *((_DWORD *)v5 + 7),
                          (__int64)v5 + (unsigned __int16)v191 + v192 + 36,
                          *((_DWORD *)v5 + 8),
                          &v966);
      if ( RemoteAppWindow < 0 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_272;
        }
        v173 = RdpX_GetActivityIdPrefix(v196, v195, v197, v198);
        v174 = 103;
LABEL_298:
        v175 = "CreateCachedIcon failed";
        goto LABEL_271;
      }
      v168 = v973;
    }
    v199 = RdpRemoteAppCore::GetDesktopRemoteAppWindow(v168, v970);
    RdpXSPtr<RdpXInterfaceLayerManager>::operator=(&v967, v199);
    if ( v967 )
    {
      v201 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v967 + 416LL))(v967, v966);
      if ( v201 < 0
        && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v204 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v200, v202, v203);
        LODWORD(v946) = v201;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          104,
          (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v204,
          (__int64)"Failed to UpdateOverlayIcon",
          v946);
      }
      v205 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v967 + 424LL))(v967, 0, 0);
      v207 = MapXResultToHR(v205);
      if ( v207 < 0
        && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v210 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v206, v208, v209);
        LODWORD(v946) = v207;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          105,
          (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v210,
          (__int64)"Failed to reset the old overlay description",
          v946);
      }
    }
    v211 = v966;
    if ( v966 )
    {
      v966 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v211 + 8LL))(v211);
    }
    v212 = v965;
    if ( v965 )
    {
      v965 = 0;
      (*(void (__fastcall **)(struct ITSWndPluginEx *))(*(_QWORD *)v212 + 16LL))(v212);
    }
    v213 = v967;
    if ( v967 )
    {
      v967 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v213 + 8LL))(v213);
    }
    v161 = v970;
    if ( !v970 )
      return 0;
    v970 = 0;
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
      v127 = RdpX_GetActivityIdPrefix(v20, v21, v18, v19);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v127);
    }
    LOBYTE(v21) = 3;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_RailV2ConnectionInfoDisclosure>::__private_IsEnabledPreCheck(
      `wil::Feature<__WilFeatureTraits_Feature_RailV2ConnectionInfoDisclosure>::GetImpl'::`2'::impl,
      v21);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_RailV2ConnectionInfoDisclosure>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_RailV2ConnectionInfoDisclosure>::GetImpl'::`2'::impl) )
    {
      v129 = RdpRemoteAppCore::SetV2CoreProperty((RdpRemoteAppCore *)((char *)v6 - 48), 4u);
      if ( v129 < 0
        && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v132 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v128, v130, v131);
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          68,
          (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v132,
          (__int64)"Failed to set the V2 core property",
          v129);
      }
    }
    v134 = RdpRemoteAppCore::ReceiveHandshake((RdpRemoteAppCore *)((char *)v6 - 48), v5, (unsigned int *)v6 + 43);
    if ( v134 >= 0 )
    {
      return (unsigned int)RdpRemoteAppCore::OnHandshakeOrCaps((RdpRemoteAppCore *)((char *)v6 - 48), 1);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v137 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v133, v135, v136);
        LODWORD(v943) = v134;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          69,
          (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v137,
          (__int64)"RemoteAppHandshake::ReceiveHandshake failed",
          v943);
      }
      LOBYTE(v133) = 3;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_RailV2ConnectionInfoDisclosure>::__private_IsEnabledPreCheck(
        `wil::Feature<__WilFeatureTraits_Feature_EnableRailV2>::GetImpl'::`2'::impl,
        v133);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableRailV2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnableRailV2>::GetImpl'::`2'::impl) )
        v138 = *(unsigned int (**)(void))(**((_QWORD **)v6 + 12) + 56LL);
      else
        v138 = *(unsigned int (**)(void))(**((_QWORD **)v6 + 11) + 48LL);
      return v138();
    }
  }
  if ( (_DWORD)v20 == 7 )
  {
LABEL_1134:
    v929 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v930 = RdpX_GetActivityIdPrefix(v20, WPP_GLOBAL_Control, v18, v19);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v930);
      v929 = WPP_GLOBAL_Control;
    }
    v931 = *((unsigned __int16 *)v5 + 1);
    if ( (unsigned __int16)v931 < 0x10u )
    {
      if ( v929 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v929[7] & 1) != 0 && *((_BYTE *)v929 + 25) >= 2u )
      {
        v932 = RdpX_GetActivityIdPrefix(v20, v929, v18, v19);
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids, v932);
      }
      RemoteAppWindow = -2147467259;
      RdpRemoteAppCore::LogRemoteAppError((char *)v6 + 16, L"TS_RAIL_ORDER_EXEC_RESULT too short", 2147500037LL, 0, 0);
      return (unsigned int)RemoteAppWindow;
    }
    v933 = *((unsigned __int16 *)v5 + 7);
    if ( v931 != v933 + 16 )
    {
      if ( v929 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v929[7] & 1) != 0 && *((_BYTE *)v929 + 25) >= 2u )
      {
        v934 = RdpX_GetActivityIdPrefix(v933 + 16, v929, v18, v19);
        WPP_SF_DLD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          72,
          &WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v934,
          v931,
          v933 + 16);
      }
      RemoteAppWindow = -2147467259;
      v111 = 2147500037LL;
      v943 = (unsigned __int16 *)(*((unsigned __int16 *)v5 + 7) + 16LL);
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
    v935 = *((_DWORD *)v5 + 2);
    v936 = (char *)v6 + 16;
    if ( *((_WORD *)v5 + 3) )
    {
      if ( v935 )
      {
        if ( v935 > 0 )
          v937 = (unsigned __int16)v935 | 0x80070000;
        else
          v937 = *((_DWORD *)v5 + 2);
      }
      else
      {
        v937 = -2147467259;
      }
      RdpRemoteAppCore::LogRemoteAppErrorF(
        v936,
        L"ExecResultRailOrderReceived_Error: ApplicationName=%s, Flags=0x%hx, Result=0x%hx, RawResult=0x%x",
        v937,
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
        v936,
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
      v6 = v973;
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
    LODWORD(v953) = *((__int16 *)v5 + 6);
    LODWORD(v943) = *((unsigned __int16 *)v5 + 5);
    LODWORD(cchToCopy) = *((unsigned __int16 *)v5 + 4);
    RdpRemoteAppCore::LogRemoteAppEventF(
      (char *)v6 + 16,
      L"LocalMoveSizeRailOrderReceived: WindowId=0x%x, IsStart=%hu, Type=0x%hx, X=%hi, Y=%hi",
      0,
      *((unsigned int *)v5 + 1),
      cchToCopy,
      v943,
      v953,
      *((__int16 *)v5 + 7));
    v987 = 0;
    v986 = 0;
    RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow(
                        (RdpRemoteAppCore *)((char *)v6 - 48),
                        *((_DWORD *)v5 + 1),
                        &v987);
    if ( RemoteAppWindow >= 0 )
    {
      v68 = RdpRemoteAppCore::GetDesktopRemoteAppWindow((RdpRemoteAppCore *)((char *)v6 - 48), v987);
      RdpXSPtr<RdpXInterfaceLayerManager>::operator=(&v986, v68);
      v73 = v986;
      if ( !v986 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control )
        {
          v74 = (_DWORD)v986 + 8;
          if ( ((unsigned __int8)((_BYTE)v986 + 8) & (_BYTE)WPP_GLOBAL_Control[7]) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v75 = RdpX_GetActivityIdPrefix(v70, v69, v71, v72);
            LODWORD(v945) = 1;
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v74 + 68,
              (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
              v75,
              (__int64)"spDesktopRemoteAppWindow",
              v945);
            v73 = v986;
          }
        }
        RemoteAppWindow = 1;
        if ( !v73 )
          goto LABEL_104;
        v986 = 0;
        v67 = *v73;
        goto LABEL_103;
      }
      if ( *((_WORD *)v5 + 4) )
      {
        v1020 = 0;
        v76 = RemoteAppMoveSizeInfo::CreateInstance((char *)v5 + 4, &v1020);
        RemoteAppWindow = MapXResultToHR(v76);
        if ( RemoteAppWindow >= 0 )
        {
          (*(void (__fastcall **)(__int64 *, __int64))(*v986 + 392))(v986, v1020);
        }
        else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
               && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v81 = RdpX_GetActivityIdPrefix(v78, v77, v79, v80);
          LODWORD(v945) = RemoteAppWindow;
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            77,
            (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
            v81,
            (__int64)"Failed to create RemoteAppMoveSizeInfo",
            v945);
        }
        v82 = v1020;
        if ( v1020 )
        {
          v1020 = 0;
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
        (*(void (__fastcall **)(__int64 *, __int64, _QWORD, __int64, int))(*v986 + 400))(v986, 1, 0, v84, v83);
      }
    }
    else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
           && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v65 = RdpX_GetActivityIdPrefix(v62, v61, v63, v64);
      LODWORD(v945) = RemoteAppWindow;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        75,
        (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
        v65,
        (__int64)"Failed to find window",
        v945);
    }
    v66 = v986;
    if ( !v986 )
    {
LABEL_104:
      v42 = v987;
      if ( !v987 )
        return (unsigned int)RemoteAppWindow;
      v987 = 0;
      goto LABEL_106;
    }
    v986 = 0;
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
    (char *)v973 + 16,
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
  v1006 = 0;
  v1005 = 0;
  RemoteAppWindow = RdpRemoteAppCore::GetRemoteAppWindow(
                      (RdpRemoteAppCore *)((char *)v973 - 48),
                      *((_DWORD *)v5 + 1),
                      &v1006);
  if ( RemoteAppWindow < 0 )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v41 = RdpX_GetActivityIdPrefix(v38, v37, v39, v40);
      LODWORD(v944) = RemoteAppWindow;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        80,
        (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
        v41,
        (__int64)"Failed to find window",
        v944);
    }
LABEL_71:
    v42 = v1006;
    if ( !v1006 )
      return (unsigned int)RemoteAppWindow;
    v1006 = 0;
LABEL_106:
    (*(void (__fastcall **)(struct RdpXInterfaceRemoteAppWindow *))(*(_QWORD *)v42 + 8LL))(v42);
    return (unsigned int)RemoteAppWindow;
  }
  v43 = RdpRemoteAppCore::GetDesktopRemoteAppWindow((RdpRemoteAppCore *)((char *)v973 - 48), v1006);
  RdpXSPtr<RdpXInterfaceLayerManager>::operator=(&v1005, v43);
  v47 = v1005;
  if ( !v1005 )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control )
    {
      v48 = v1005 + 8;
      if ( ((unsigned __int8)(v1005 + 8) & (_BYTE)WPP_GLOBAL_Control[7]) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v49 = RdpX_GetActivityIdPrefix(v45, v44, 0, v46);
        LODWORD(v944) = 1;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v48 + 73,
          (unsigned int)&WPP_a69e6f844fd4332c62efc64ae25c8f1d_Traceguids,
          v49,
          (__int64)"spDesktopRemoteAppWindow",
          v944);
        v47 = v1005;
      }
    }
    RemoteAppWindow = 1;
    if ( v47 )
    {
      v1005 = 0;
      (*(void (**)(void))(*(_QWORD *)v47 + 8LL))();
    }
    goto LABEL_71;
  }
  v50 = 0;
  v1038 = 0;
  memset(v1037, 0, sizeof(v1037));
  do
  {
    v51 = *((__int16 *)v5 + (unsigned int)v50 + 4);
    v52 = 4 * v50++ + 8;
    *(_DWORD *)((char *)v1037 + v52) = v51;
  }
  while ( v50 < 8 );
  (*(void (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)v47 + 408LL))(v47, v1037);
  v53 = v1005;
  if ( v1005 )
  {
    v1005 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 8LL))(v53);
  }
  v42 = v1006;
  if ( v1006 )
  {
    v1006 = 0;
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
