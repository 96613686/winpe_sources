# WinMain

- ea: `0x1400a2dbc`
- end: `0x1400a38ed`
- name: `WinMain`
- size: `2865`
- prototype: `int __stdcall(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPSTR lpCmdLine, int nShowCmd)`
- caller_count: `1`
- callee_count: `104`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14011fb9c`

## callees

- `0x14003abe0`
- `0x14003f4d0`
- `0x140040dc0`
- `0x14004ec70`
- `0x14004f334`
- `0x140056aa0`
- `0x14005d4c0`
- `0x140060b60`
- `0x140061790`
- `0x140069060`
- `0x14007c0b0`
- `0x14007c0d0`
- `0x14007c110`
- `0x14007dd70`
- `0x14007f9ec`
- `0x140081e60`
- `0x140083a20`
- `0x140083a40`
- `0x140083b6e`
- `0x140084750`
- `0x140084760`
- `0x140084d00`
- `0x140084ed0`
- `0x140086090`
- `0x140086c50`
- `0x14008c8d1`
- `0x14008d6e0`
- `0x140090dec`
- `0x140093590`
- `0x1400a2413`
- `0x1400a2dbc`
- `0x1400a38f0`
- `0x1400a39e3`
- `0x1400a3a40`
- `0x1400a3a80`
- `0x1400a3a9c`
- `0x1400a3aa1`
- `0x1400a3ace`
- `0x1400a3af6`
- `0x1400a3b00`
- `0x1400a3d10`
- `0x1400a3db0`
- `0x1400a3e50`
- `0x1400a3e76`
- `0x1400a4080`
- `0x1400a421c`
- `0x1400a45e0`
- `0x1400a4dd0`
- `0x1400a4e7e`
- `0x1400a4f3c`

## import_xrefs

- `KERNEL32!DuplicateHandle` at `0x1400a3721`
- `KERNEL32!DuplicateHandle` at `0x1400a3721`
- `KERNEL32!GetCommandLineW` at `0x1400a2e83`
- `KERNEL32!GetCommandLineW` at `0x1400a2e83`
- `KERNEL32!GetCurrentProcess` at `0x1400a36ec`
- `KERNEL32!GetCurrentProcess` at `0x1400a36fa`
- `KERNEL32!GetCurrentProcess` at `0x1400a36e5`
- `KERNEL32!GetModuleFileNameW` at `0x1400a2f0c`
- `KERNEL32!GetModuleFileNameW` at `0x14015862c`
- `KERNEL32!GetModuleFileNameW` at `0x1400a2f0c`
- `KERNEL32!GetModuleFileNameW` at `0x14015862c`
- `KERNEL32!GetModuleHandleW` at `0x1400a33ae`
- `KERNEL32!GetModuleHandleW` at `0x1400a33ae`
- `KERNEL32!GetProcAddress` at `0x1400a33be`
- `KERNEL32!GetProcAddress` at `0x1400a33be`
- `KERNEL32!LoadLibraryExW` at `0x1400a2ede`
- `KERNEL32!LoadLibraryExW` at `0x1400a2ede`

## string_xrefs

- `0x1400a362e`: `no-periodic-tasks`
- `0x1401583eb`: `media.mojom.MediaFoundationServiceBroker`
- `0x14015850e`: `About to load main DLL.`
- `0x1400a3115`: `__COMPAT_LAYER`
- `0x14015887b`: `__COMPAT_LAYER`
- `0x140157d4f`: `profile-directory`
- `0x1400a2f8b`: `uninstall`
- `0x140158831`: `edge-skip-compat-layer-relaunch`

## pseudocode

```c
int __stdcall WinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPSTR lpCmdLine, int nShowCmd)
{
  __int64 p_Src; // r14
  __int64 ElfCommandLine; // rax
  __int64 v7; // rdi
  __int64 v8; // rbx
  LPWSTR CommandLineW; // rax
  __int64 v10; // rax
  DWORD ModuleFileNameW; // eax
  UINT v12; // ebp
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int16 v15; // r8
  __int16 v16; // r10
  wchar_t v17; // r8
  wchar_t v18; // r11
  __int64 v19; // r8
  char v20; // r15
  char v21; // r12
  __int64 v22; // rcx
  HINSTANCE v23; // rdi
  WCHAR *v24; // rbx
  unsigned int v25; // ebp
  __int64 v26; // rax
  char v27; // bp
  char v28; // al
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int128 *v33; // rax
  HMODULE ModuleHandleW; // rax
  unsigned __int8 (*ProcAddress)(void); // rax
  __int64 v36; // rax
  __int64 v37; // rcx
  __int128 *v38; // rax
  __int64 *v39; // r12
  __int64 *v40; // r13
  __int64 v41; // rax
  __int64 *v42; // rcx
  int v43; // eax
  const __m128i *v44; // rcx
  char v45; // bl
  HANDLE CurrentProcess; // rbx
  void *v47; // r14
  HANDLE v48; // rax
  void *v49; // rsi
  __int64 v50; // rax
  __int64 v51; // rdx
  void *v52; // rcx
  HINSTANCE v53; // rax
  __int64 v54; // rcx
  __int64 v56; // rax
  __int64 v57; // rdx
  _QWORD *v58; // rbp
  _QWORD *v59; // rax
  _QWORD *v60; // rax
  __int64 v61; // rax
  unsigned __int8 v62; // al
  unsigned int v63; // edi
  char v64; // bp
  __int128 *v65; // r12
  __int128 *p_TargetHandle; // r15
  __int128 *v67; // r14
  size_t v68; // r8
  unsigned __int64 v69; // r13
  size_t v70; // r8
  unsigned __int64 v71; // r12
  size_t v72; // r8
  unsigned __int64 v73; // r15
  __int64 v74; // rax
  char v75; // r12
  char v76; // r15
  __int64 v77; // rax
  __int64 v78; // rax
  __int64 v79; // r12
  __int64 v80; // rax
  HWND v81; // r12
  int v82; // ebp
  __int64 v83; // rax
  WCHAR *v84; // r15
  __int64 v85; // rax
  __int64 v86; // rcx
  char v87; // al
  const __m128i *v88; // rax
  __int128 *v89; // rsi
  __int128 *v90; // rbx
  __int128 *v91; // r12
  __int64 v92; // rax
  __int64 v93; // rax
  __int64 v94; // rax
  _WORD *v95; // rax
  __int64 v96; // rax
  __int64 v97; // rax
  __int64 v98; // r15
  __int64 v99; // [rsp+0h] [rbp-508h] BYREF
  const char *v100; // [rsp+40h] [rbp-4C8h]
  __int64 v101; // [rsp+48h] [rbp-4C0h]
  WCHAR *v102; // [rsp+50h] [rbp-4B8h]
  __int64 v103; // [rsp+58h] [rbp-4B0h]
  const char *v104; // [rsp+60h] [rbp-4A8h]
  __int64 v105; // [rsp+68h] [rbp-4A0h]
  __int128 Src; // [rsp+70h] [rbp-498h] BYREF
  __int128 v107; // [rsp+80h] [rbp-488h]
  __int128 v108; // [rsp+90h] [rbp-478h]
  __int64 v109; // [rsp+A0h] [rbp-468h]
  const char *v110; // [rsp+B0h] [rbp-458h]
  __int64 v111; // [rsp+B8h] [rbp-450h]
  _BYTE v112[16]; // [rsp+C0h] [rbp-448h] BYREF
  const char *v113; // [rsp+D0h] [rbp-438h]
  __int64 v114; // [rsp+D8h] [rbp-430h]
  const char *v115; // [rsp+E0h] [rbp-428h]
  __int64 v116; // [rsp+E8h] [rbp-420h]
  const char *v117; // [rsp+F0h] [rbp-418h]
  __int64 v118; // [rsp+F8h] [rbp-410h]
  const char *v119; // [rsp+100h] [rbp-408h]
  __int64 v120; // [rsp+108h] [rbp-400h]
  const char *v121; // [rsp+110h] [rbp-3F8h]
  __int64 v122; // [rsp+118h] [rbp-3F0h]
  const char *v123; // [rsp+120h] [rbp-3E8h]
  __int64 v124; // [rsp+128h] [rbp-3E0h]
  const char *v125; // [rsp+130h] [rbp-3D8h]
  __int64 v126; // [rsp+138h] [rbp-3D0h]
  const char *v127; // [rsp+140h] [rbp-3C8h]
  __int64 v128; // [rsp+148h] [rbp-3C0h]
  const char *v129; // [rsp+150h] [rbp-3B8h]
  __int64 v130; // [rsp+158h] [rbp-3B0h]
  const char *v131; // [rsp+160h] [rbp-3A8h]
  __int64 v132; // [rsp+168h] [rbp-3A0h]
  __int128 v133; // [rsp+170h] [rbp-398h] BYREF
  __int64 v134; // [rsp+180h] [rbp-388h]
  __int128 v135; // [rsp+190h] [rbp-378h] BYREF
  __int64 v136; // [rsp+1A0h] [rbp-368h]
  __int64 v137; // [rsp+1A8h] [rbp-360h]
  __int64 v138; // [rsp+1B0h] [rbp-358h]
  __int128 *v139; // [rsp+1B8h] [rbp-350h]
  __int64 v140; // [rsp+1C0h] [rbp-348h]
  _QWORD v141[5]; // [rsp+1C8h] [rbp-340h] BYREF
  _QWORD v142[5]; // [rsp+1F0h] [rbp-318h] BYREF
  WCHAR tstrFilename[8]; // [rsp+218h] [rbp-2F0h] BYREF
  __int64 v144; // [rsp+228h] [rbp-2E0h]
  __int128 v145; // [rsp+230h] [rbp-2D8h] BYREF
  __int64 v146; // [rsp+240h] [rbp-2C8h]
  __int128 v147; // [rsp+250h] [rbp-2B8h] BYREF
  __int64 v148; // [rsp+260h] [rbp-2A8h]
  __int128 TargetHandle; // [rsp+270h] [rbp-298h] BYREF
  __int64 v150; // [rsp+280h] [rbp-288h]
  WCHAR Filename[268]; // [rsp+290h] [rbp-278h] BYREF
  __int64 v152; // [rsp+4A8h] [rbp-60h]

  sub_1400A3AA1(1, hPrevInstance, lpCmdLine, nShowCmd);
  if ( (unsigned __int8)IsBrowserProcess() )
    LoadLibraryExW("v", 0, 0x800u);
  if ( (unsigned __int8)IsBrowserProcess() )
  {
    memset(Filename, 0, 0x20Au);
    ModuleFileNameW = GetModuleFileNameW(0, Filename, 0x105u);
    if ( ModuleFileNameW - 1 <= 0x103 )
    {
      *(_QWORD *)&v147 = Filename;
      *((_QWORD *)&v147 + 1) = ModuleFileNameW;
      sub_140056AA0(&TargetHandle);
      sub_140069060(&TargetHandle);
      sub_1400DD9E0((LPCWSTR)&Src);
      sub_140086C50(&Src);
      sub_140086C50(&TargetHandle);
    }
  }
  sub_1400A39E3();
  if ( (unsigned __int8)IsBrowserProcess() )
    sub_1400A3AF6();
  sub_1400A3A40();
  sub_1400A38F0();
  if ( (unsigned __int8)IsBrowserProcess() )
    EdgeElfBeaconDetect(1);
  if ( !(unsigned __int8)sub_140083A20() && !(unsigned __int8)sub_140083A40() )
  {
    ElfCommandLine = EdgeGetElfCommandLine();
    if ( !ElfCommandLine
      || (v7 = ElfCommandLine,
          v8 = sub_14011CB20(ElfCommandLine),
          v137 = v7,
          v138 = v8,
          sub_1400A3DB0(),
          (CommandLineW = GetCommandLineW()) == 0) )
    {
LABEL_148:
      BUG();
    }
    p_Src = (__int64)CommandLineW;
    if ( sub_14011CB20(CommandLineW) != v8 )
    {
LABEL_139:
      v56 = sub_140084750();
      LOBYTE(v57) = 1;
      sub_1402BC180(v56, v57);
      goto LABEL_50;
    }
    if ( v8 )
    {
      v10 = 0;
      while ( *(_WORD *)(p_Src + 2 * v10) == *(_WORD *)(v7 + 2 * v10) )
      {
        if ( v8 == ++v10 )
          goto LABEL_50;
      }
      goto LABEL_139;
    }
  }
LABEL_50:
  sub_1400A3B00(0, 0);
  v23 = (HINSTANCE)sub_140084750();
  LODWORD(v24) = sub_140084760(v23, "embedded-browser-webview");
  v25 = (unsigned int)v24;
  LOBYTE(v25) = IsBrowserProcess() & ((unsigned __int8)v24 ^ 1);
  v26 = sub_140100CB0();
  sub_1400A3A80(v26, v25);
  v27 = sub_140084760(v23, "headless");
  v28 = IsBrowserProcess();
  if ( (_BYTE)v24 || v27 || !v28 )
    SignalInitializeCrashReporting();
  v135 = 0;
  v136 = 0;
  sub_140100E30(v23, &v135);
  if ( !(unsigned __int8)sub_1400A3D10()
    || (unsigned __int8)sub_140084760(v23, "type")
    || (v12 = 1002, (unsigned __int8)sub_140084760(v23, "allow-run-as-system")) )
  {
    if ( (_QWORD)v135 == *((_QWORD *)&v135 + 1)
      || (unsigned __int8)sub_140084760(v23, "disable-wcos-default-browser-channel")
      || (unsigned __int8)sub_140084760(v23, "app-id")
      || !(unsigned __int8)sub_1400A3A9C()
      || (v87 = sub_1401FA1C8(v23), v12 = 0, !v87) )
    {
      if ( (_BYTE)v24
        || !(unsigned __int8)IsBrowserProcess()
        || !(unsigned __int8)sub_1400A3E76()
        || !(unsigned __int8)sub_1400A4F3C(&off_140419E10) )
      {
        goto LABEL_58;
      }
      p_Src = (__int64)v141;
      v141[0] = 0;
      sub_140101FE0(v141);
      *(_QWORD *)&v147 = "__COMPAT_LAYER";
      *((_QWORD *)&v147 + 1) = 14;
      v20 = 1;
      v21 = 0;
      if ( (unsigned __int8)sub_1400A96D0(v141[0]) )
      {
        v96 = sub_140084750();
        p_Src = (__int64)"edge-skip-compat-layer-relaunch";
        v21 = 0;
        v12 = 0;
        if ( !(unsigned __int8)sub_140084760(v96, "edge-skip-compat-layer-relaunch") )
        {
          memset(Filename, 0, 0xB0u);
          sub_1400D0250(Filename);
          sub_14007F9EC(&Src, L"__COMPAT_LAYER");
          v142[0] = &Src;
          *(_QWORD *)tstrFilename = &Filename[68];
          sub_1401FA4B8(tstrFilename, &TargetHandle, &Src);
          v97 = TargetHandle;
          if ( *(char *)(TargetHandle + 79) < 0 )
          {
            *(_QWORD *)(TargetHandle + 64) = 0;
            v95 = *(_WORD **)(v97 + 56);
          }
          else
          {
            *(_BYTE *)(TargetHandle + 79) = 0;
            v95 = (_WORD *)(v97 + 56);
          }
          *v95 = 0;
          if ( SBYTE7(v107) < 0 )
            sub_14003ABE0(Src, 2 * v107);
          v98 = sub_140084750();
          *(_QWORD *)&v145 = "edge-skip-compat-layer-relaunch";
          *((_QWORD *)&v145 + 1) = 31;
          sub_140118620(v98);
          p_Src = (__int64)&Src;
          Src = 0;
          sub_1400AD2B0(&Src, v98, Filename);
          v20 = 0;
          v12 = 15;
          if ( (unsigned __int8)sub_14007C0B0(&Src) )
            v12 = 0;
          sub_14007C0D0(&Src);
          sub_1400B5450(Filename);
          v21 = 1;
        }
      }
      else
      {
        v12 = 0;
      }
      v22 = v141[0];
      v141[0] = 0;
      if ( v22 )
        sub_14003ABE0(v22, 8);
      if ( v20 || !v21 )
      {
LABEL_58:
        p_Src = (__int64)&v133;
        v133 = 0;
        v134 = 0;
        v131 = "type";
        v132 = 4;
        sub_140093590(v23, &v133);
        nullsub_1(&v133);
        v29 = SHIBYTE(v134);
        if ( v134 < 0 )
          v29 = *((_QWORD *)&v133 + 1);
        if ( !v29 )
        {
          ModuleHandleW = GetModuleHandleW(0);
          ProcAddress = (unsigned __int8 (*)(void))GetProcAddress(ModuleHandleW, "IsSandboxedProcess");
          if ( ProcAddress )
          {
            if ( ProcAddress() )
            {
              __debugbreak();
              BUG();
            }
          }
        }
        if ( (_BYTE)v24 )
        {
          v65 = &Src;
          Src = 0;
          *(_QWORD *)&v107 = 0;
          v129 = "webview-exe-name";
          v130 = 16;
          sub_140093590(v23, &Src);
          p_TargetHandle = &TargetHandle;
          v150 = 0;
          TargetHandle = 0;
          v127 = "webview-exe-version";
          v128 = 19;
          sub_140093590(v23, &TargetHandle);
          v67 = &v147;
          v148 = 0;
          v147 = 0;
          v125 = "embedded-browser-webview-app-specific-id";
          v126 = 40;
          sub_140093590(v23, &v147);
          v68 = SBYTE7(v107);
          if ( SBYTE7(v107) < 0 )
            v68 = *((_QWORD *)&Src + 1);
          if ( v68 )
          {
            if ( SBYTE7(v107) < 0 )
              v65 = (__int128 *)Src;
            v69 = 64;
            if ( (unsigned int)v68 < 0x40 )
              v69 = (unsigned int)v68;
            if ( HIDWORD(v68) )
              v69 = 64;
            if ( v68 >= v69 )
              v68 = v69;
            memcpy(qword_140419D10, v65, v68);
            sub_140090DEC(&qword_140419CF0, (unsigned int)v69);
          }
          v70 = SHIBYTE(v150);
          if ( v150 < 0 )
            v70 = *((_QWORD *)&TargetHandle + 1);
          if ( v70 )
          {
            if ( v150 < 0 )
              p_TargetHandle = (__int128 *)TargetHandle;
            v71 = 64;
            if ( (unsigned int)v70 < 0x40 )
              v71 = (unsigned int)v70;
            if ( HIDWORD(v70) )
              v71 = 64;
            if ( v70 >= v71 )
              v70 = v71;
            memcpy(qword_140419D70, p_TargetHandle, v70);
            sub_140090DEC(&qword_140419D50, (unsigned int)v71);
          }
          v72 = SHIBYTE(v148);
          if ( v148 < 0 )
            v72 = *((_QWORD *)&v147 + 1);
          if ( v72 )
          {
            if ( v148 < 0 )
              v67 = (__int128 *)v147;
            v73 = 64;
            if ( (unsigned int)v72 < 0x40 )
              v73 = (unsigned int)v72;
            if ( HIDWORD(v72) )
              v73 = 64;
            if ( v72 >= v73 )
              v72 = v73;
            memcpy(qword_140419DD0, v67, v72);
            sub_140090DEC(&qword_140419DB0, (unsigned int)v73);
          }
          v74 = SHIBYTE(v134);
          if ( v134 < 0 )
            v74 = *((_QWORD *)&v133 + 1);
          p_Src = 0x7FFFFFFFFFFFFFFFLL;
          v75 = 0;
          v12 = 0;
          if ( !v74 )
          {
            v123 = "edge-webview-force-personal-context";
            v124 = 35;
            sub_140093590(v23, Filename);
            v76 = sub_14008C8D1(Filename, "2");
            if ( (Filename[11] & 0x8000u) != 0 )
              sub_14003ABE0(*(_QWORD *)Filename, *(_QWORD *)&Filename[8] & 0x7FFFFFFFFFFFFFFFLL);
            v75 = 0;
            v12 = 0;
            if ( v76 )
            {
              v77 = sub_140289840();
              *(_QWORD *)tstrFilename = 0;
              sub_14004F334(tstrFilename, v77);
              v78 = *(_QWORD *)tstrFilename;
              v12 = 15;
              if ( *(_QWORD *)tstrFilename != 0 && *(_DWORD *)tstrFilename < 0xFFFFFFF4 )
              {
                memset(Filename, 0, 0xB0u);
                sub_1400D0250(Filename);
                *(_QWORD *)&Filename[36] = *(_QWORD *)tstrFilename;
                v79 = sub_140084750();
                v121 = "edge-webview-force-personal-context";
                v122 = 35;
                sub_140112520(v79);
                v119 = "1";
                v120 = 1;
                v117 = "edge-webview-force-personal-context";
                v118 = 35;
                sub_140101D50(v79);
                v145 = 0;
                sub_1400AD2B0(&v145, v79, Filename);
                v12 = 15;
                if ( (unsigned __int8)sub_14007C0B0(&v145) )
                  v12 = 0;
                sub_14007C0D0(&v145);
                sub_1400B5450(Filename);
                v78 = *(_QWORD *)tstrFilename;
              }
              if ( v78 != 0 && (unsigned int)v78 < 0xFFFFFFF4 )
              {
                sub_14004EC70();
                sub_140060B60(*(_QWORD *)tstrFilename);
              }
              v75 = 1;
            }
          }
          if ( v148 < 0 )
            sub_14003ABE0(v147, v148 & 0x7FFFFFFFFFFFFFFFLL);
          if ( v150 < 0 )
            sub_14003ABE0(TargetHandle, v150 & 0x7FFFFFFFFFFFFFFFLL);
          if ( SBYTE7(v107) < 0 )
          {
            p_Src = v107 & 0x7FFFFFFFFFFFFFFFLL;
            sub_14003ABE0(Src, v107 & 0x7FFFFFFFFFFFFFFFLL);
          }
          if ( v75 )
            goto LABEL_126;
        }
        v30 = SHIBYTE(v134);
        if ( v134 < 0 )
          v30 = *((_QWORD *)&v133 + 1);
        if ( v30 || (unsigned __int8)sub_140084760(v23, "uninstall") )
          goto LABEL_65;
        v12 = 13;
        if ( ((*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(sub_140083B6E() + 8) + 16LL) + 12LL) == 1)
            & (unsigned __int8)~(_BYTE)v24) != 0
          || *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(sub_140083B6E() + 8) + 16LL) + 12LL) == 2
          && !(unsigned __int8)sub_14008D6E0() )
        {
          goto LABEL_126;
        }
        if ( (unsigned __int8)v24 | (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(sub_140083B6E() + 8) + 16LL) + 12LL) != 0) )
          goto LABEL_65;
        p_Src = (__int64)Filename;
        memset(Filename, 0, 24);
        sub_14003F4D0(Filename);
        if ( (unsigned __int8)sub_140081E60(1, Filename) )
        {
          p_Src = (__int64)&Src;
          sub_140061790(Filename);
          v13 = SBYTE7(v107);
          if ( SBYTE7(v107) < 0 )
            v13 = *((_QWORD *)&Src + 1);
          if ( v13 == 10 )
          {
            if ( SBYTE7(v107) < 0 )
              p_Src = Src;
            v14 = 0;
            do
            {
              v15 = *(_WORD *)(p_Src + v14 * 2);
              v16 = v15 + 32;
              if ( (unsigned __int16)(v15 - 65) >= 0x1Au )
                v16 = *(_WORD *)(p_Src + v14 * 2);
              v17 = aMsedgeExe_0[v14];
              v18 = v17 + 32;
              if ( (unsigned __int16)(v17 - 65) >= 0x1Au )
                v18 = aMsedgeExe_0[v14];
              if ( v16 != v18 )
                goto LABEL_155;
              v19 = p_Src + v14 * 2 + 2;
              ++v14;
            }
            while ( v19 != p_Src + 20 );
            sub_140086C50(&Src);
            sub_140086C50(Filename);
LABEL_65:
            if ( (unsigned __int8)sub_140084760(v23, "launcher") )
            {
              v115 = "launcher";
              v116 = 8;
              p_Src = (__int64)Filename;
              sub_140093590(v23, Filename);
              v64 = sub_14008C8D1(Filename, "on_logon_windows");
              if ( (Filename[11] & 0x8000u) != 0 )
                sub_14003ABE0(*(_QWORD *)Filename, *(_QWORD *)&Filename[8] & 0x7FFFFFFFFFFFFFFFLL);
              if ( v64 )
              {
                v12 = 1001;
                if ( !(unsigned __int8)sub_1402BE896() )
                  goto LABEL_126;
              }
            }
            p_Src = (__int64)&v133;
            sub_1400A4080(&v133, (unsigned int)v24);
            v31 = SHIBYTE(v134);
            if ( v134 < 0 )
              v31 = *((_QWORD *)&v133 + 1);
            if ( v31 != 16 )
              goto LABEL_69;
            if ( v134 < 0 )
              v44 = (const __m128i *)v133;
            else
              v44 = (const __m128i *)&v133;
            if ( _mm_movemask_epi8(_mm_cmpeq_epi8(_mm_loadu_si128((const __m128i *)xmmword_1403B5FE8), _mm_loadu_si128(v44))) == 0xFFFF )
            {
              sub_1400A5A2E(v23);
              if ( (unsigned __int8)sub_140084760(v23, "no-periodic-tasks") )
                goto LABEL_157;
              memset(Filename, 0, 72);
              sub_1400A3E50(Filename);
              v113 = "initial-client-data";
              v114 = 19;
              sub_140093590(v23, &Src);
              v45 = sub_1400A5306(Filename, &Src);
              if ( SBYTE7(v107) < 0 )
                sub_14003ABE0(Src, v107 & 0x7FFFFFFFFFFFFFFFLL);
              if ( v45
                && (*(_QWORD *)&TargetHandle = -1,
                    CurrentProcess = GetCurrentProcess(),
                    v47 = *(void **)&Filename[28],
                    v48 = GetCurrentProcess(),
                    DuplicateHandle(v48, v47, CurrentProcess, (LPHANDLE)&TargetHandle, 0x400u, 0, 2u)) )
              {
                Src = 0;
                sub_140084ED0(&Src, TargetHandle);
                v49 = operator new(0xA0u);
                sub_1400A4E7E(v49);
                sub_14007C110(v112, &Src);
                if ( (unsigned __int8)sub_1400A4DD0(v49, v112) )
                  sub_1400A51CC(v49);
                sub_14007C0D0(&Src);
              }
              else
              {
LABEL_157:
                v49 = 0;
              }
              v24 = Filename;
              memset(Filename, 0, 24);
              p_Src = (__int64)"user-data-dir";
              v110 = "user-data-dir";
              v111 = 13;
              sub_1401011C0(v23, Filename);
              v50 = sub_140084750();
              v12 = sub_1400A6487(v50, Filename, "type", "user-data-dir");
              if ( v12 == 0 || v49 == 0 )
              {
                sub_140086C50(Filename);
                if ( !v49 )
                  goto LABEL_126;
              }
              else
              {
                sub_1401FA660(v49);
                sub_140086C50(Filename);
              }
              sub_1400A421C(v49);
              v51 = 160;
              v52 = v49;
            }
            else
            {
              if ( v134 < 0 )
                v88 = (const __m128i *)v133;
              else
                v88 = (const __m128i *)&v133;
              if ( _mm_movemask_epi8(_mm_cmpeq_epi8(_mm_loadu_si128((const __m128i *)"fallback-handler"), _mm_loadu_si128(v88))) != 0xFFFF )
              {
LABEL_69:
                *(_QWORD *)&v145 = 0;
                sub_140084D00(&v145);
                SignalChromeElf();
                v109 = 0;
                v108 = 0;
                v107 = 0;
                Src = 0;
                sub_140100D60(&Src);
                v32 = SHIBYTE(v134);
                if ( v134 < 0 )
                  v32 = *((_QWORD *)&v133 + 1);
                if ( v32 == 7 )
                {
                  v33 = v134 < 0 ? (__int128 *)v133 : &v133;
                  if ( !(*(_DWORD *)"utility" ^ *(_DWORD *)v33 | *(_DWORD *)"lity" ^ *(_DWORD *)((char *)v33 + 3)) )
                  {
                    memset(Filename, 0, 24);
                    v104 = "utility-sub-type";
                    v105 = 16;
                    sub_140093590(v23, Filename);
                    if ( (Filename[11] & 0x8000u) != 0 )
                    {
                      if ( *(_QWORD *)&Filename[4] != 40
                        || memcmp(*(const void **)Filename, "media.mojom.MediaFoundationServiceBroker", 0x28u)
                        || (sub_1400C47A0(), (Filename[11] & 0x8000u) != 0) )
                      {
                        sub_14003ABE0(*(_QWORD *)Filename, *(_QWORD *)&Filename[8] & 0x7FFFFFFFFFFFFFFFLL);
                      }
                    }
                  }
                }
                if ( (unsigned __int8)sub_140083A20() )
                {
                  v84 = Filename;
                  memset(Filename, 0, 32);
                  sub_140289950(Filename);
                  if ( LOBYTE(Filename[12]) == 1 )
                  {
                    v85 = sub_140084750();
                    if ( !LOBYTE(Filename[12]) )
                      unknown_libname_25();
                    v86 = SHIBYTE(Filename[11]);
                    if ( (Filename[11] & 0x8000u) != 0 )
                    {
                      v86 = *(_QWORD *)&Filename[4];
                      v84 = *(WCHAR **)Filename;
                    }
                    v102 = v84;
                    v103 = v86;
                    v100 = "holographic-slate-id";
                    v101 = 20;
                    sub_140101D50(v85);
                    if ( LOBYTE(Filename[12]) == 1 && (Filename[11] & 0x8000u) != 0 )
                      sub_14003ABE0(*(_QWORD *)Filename, *(_QWORD *)&Filename[8] & 0x7FFFFFFFFFFFFFFFLL);
                  }
                }
                if ( (_BYTE)v24 )
                {
                  v83 = SHIBYTE(v134);
                  if ( v134 < 0 )
                    v83 = *((_QWORD *)&v133 + 1);
                  if ( v83 || !(unsigned __int8)sub_1401FA3C5(v145) )
                    goto LABEL_85;
                  goto LABEL_227;
                }
                if ( *((_QWORD *)v23 + 8) > 1u )
                  goto LABEL_85;
                goto LABEL_140;
              }
              memset(Filename, 0, 0x208u);
              if ( !GetModuleFileNameW(0, Filename, 0x104u) )
                __debugbreak();
              v89 = &Src;
              Src = 0;
              *(_QWORD *)&v107 = 0;
              v90 = &TargetHandle;
              v150 = 0;
              TargetHandle = 0;
              v91 = &v147;
              v148 = 0;
              v147 = 0;
              v146 = 0;
              v145 = 0;
              sub_14007F9EC(tstrFilename, Filename);
              sub_1402BE02E(tstrFilename, (__int64)&v147);
              if ( v144 < 0 )
                sub_14003ABE0(*(_QWORD *)tstrFilename, 2 * v144);
              v92 = SHIBYTE(v148);
              if ( v148 < 0 )
              {
                v92 = *((_QWORD *)&v147 + 1);
                v91 = (__int128 *)v147;
              }
              v142[3] = v91;
              v142[4] = v92;
              p_Src = (__int64)tstrFilename;
              sub_14005D4C0(tstrFilename);
              v93 = SHIBYTE(v150);
              if ( v150 < 0 )
              {
                v93 = *((_QWORD *)&TargetHandle + 1);
                v90 = (__int128 *)TargetHandle;
              }
              v141[3] = v90;
              v141[4] = v93;
              v24 = (WCHAR *)v142;
              sub_14005D4C0(v142);
              v94 = SBYTE7(v107);
              if ( SBYTE7(v107) < 0 )
              {
                v94 = *((_QWORD *)&Src + 1);
                v89 = (__int128 *)Src;
              }
              v139 = v89;
              v140 = v94;
              sub_14005D4C0(v141);
              v12 = sub_1402BE9F6(v23, v141, v142, tstrFilename);
              if ( v146 < 0 )
                sub_14003ABE0(v145, 2 * v146);
              if ( v148 < 0 )
                sub_14003ABE0(v147, 2 * v148);
              if ( v150 < 0 )
                sub_14003ABE0(TargetHandle, 2 * v150);
              if ( (SBYTE7(v107) & 0x80u) == 0 )
                goto LABEL_126;
              v52 = (void *)Src;
              v51 = 2 * v107;
            }
            sub_14003ABE0(v52, v51);
            goto LABEL_126;
          }
LABEL_155:
          sub_140086C50(&Src);
        }
        sub_140086C50(Filename);
        goto LABEL_126;
      }
    }
  }
  while ( 1 )
  {
    hInstance = (HINSTANCE)v135;
    if ( (_QWORD)v135 )
    {
      v53 = (HINSTANCE)*((_QWORD *)&v135 + 1);
      v54 = v135;
      if ( (_QWORD)v135 != *((_QWORD *)&v135 + 1) )
      {
        v23 = (HINSTANCE)*((_QWORD *)&v135 + 1);
        do
        {
          v23 -= 6;
          if ( !v23 )
            goto LABEL_148;
          if ( *((char *)v53 - 1) < 0 )
            sub_14003ABE0(*((_QWORD *)v53 - 3), 2LL * *((_QWORD *)v53 - 1));
          v53 = v23;
        }
        while ( v23 != hInstance );
        v54 = v135;
      }
      *((_QWORD *)&v135 + 1) = hInstance;
      sub_14003ABE0(v54, v136 - v54);
    }
    if ( _security_cookie == ((unsigned __int64)&v99 ^ v152) )
      return v12;
LABEL_140:
    v58 = (_QWORD *)*((_QWORD *)v23 + 6);
    if ( v58 == (_QWORD *)(v23 + 14) )
    {
LABEL_223:
      memset(Filename, 0, 24);
      sub_14003F4D0(Filename);
      if ( (unsigned __int8)sub_14011370B(Filename) && (sub_140111DF8(Filename), (v80 = sub_1400C1FD3(Filename)) != 0) )
      {
        v81 = (HWND)v80;
        sub_140084750();
        v82 = sub_1402BD0AB(v81);
        sub_140086C50(Filename);
        if ( !v82 )
        {
LABEL_227:
          v12 = 0;
          goto LABEL_125;
        }
      }
      else
      {
        sub_140086C50(Filename);
      }
    }
    else
    {
      while ( (unsigned __int8)sub_14008C8D1(v58 + 4, "profile-directory") )
      {
        v59 = (_QWORD *)v58[1];
        if ( v59 )
        {
          do
          {
            v58 = v59;
            v59 = (_QWORD *)*v59;
          }
          while ( v59 );
        }
        else
        {
          do
          {
            v60 = v58;
            v58 = (_QWORD *)v58[2];
          }
          while ( v60 != (_QWORD *)*v58 );
        }
        if ( v58 == (_QWORD *)(v23 + 14) )
          goto LABEL_223;
      }
    }
LABEL_85:
    v36 = SHIBYTE(v134);
    if ( v134 < 0 )
      v36 = *((_QWORD *)&v133 + 1);
    if ( !v36 )
    {
      v39 = (__int64 *)*((_QWORD *)v23 + 3);
      v40 = (__int64 *)*((_QWORD *)v23 + 4);
      if ( v39 == v40 )
        goto LABEL_107;
      while ( 1 )
      {
        *(_OWORD *)Filename = *(_OWORD *)&off_1403AA2F0;
        v41 = *((char *)v39 + 23);
        v42 = v39;
        if ( v41 < 0 )
        {
          v42 = (__int64 *)*v39;
          v41 = v39[1];
        }
        *(_QWORD *)&TargetHandle = v42;
        *((_QWORD *)&TargetHandle + 1) = v41;
        if ( (unsigned __int8)sub_1400D91B0(&TargetHandle, Filename, 0) )
          break;
        v39 += 3;
        if ( v39 == v40 )
          goto LABEL_107;
      }
      v61 = *((char *)v39 + 23);
      if ( v61 < 0 )
      {
        v61 = v39[1];
        v39 = (__int64 *)*v39;
      }
      if ( (unsigned __int64)v61 <= 9 )
        sub_1401FA4A3("string_view::substr");
      *(_DWORD *)tstrFilename = 0;
      *(_QWORD *)&v147 = (char *)v39 + 20;
      *((_QWORD *)&v147 + 1) = v61 - 10;
      v62 = sub_1400F4E30(&v147, tstrFilename);
      v63 = *(_DWORD *)tstrFilename;
      if ( ((*(_DWORD *)tstrFilename > 0) & v62) == 0 || v63 > 8 * (unsigned int)((int)sub_140086090() >= 22) + 8 )
      {
LABEL_107:
        v43 = sub_140086090();
        sub_1400A50F0(8 * (unsigned int)(v43 >= 22) + 8);
      }
    }
    if ( (int)sub_14007DD70("..\\..\\chrome\\app\\chrome_exe_main_win.cc", 40) > 0 )
    {
      sub_14010E170(Filename, "..\\..\\chrome\\app\\chrome_exe_main_win.cc", 823, 0xFFFFFFFFLL);
      sub_1400A2413(&Filename[8], "About to load main DLL.", 23);
      sub_14010E1D0(Filename);
    }
    v23 = (HINSTANCE)sub_1400A3ACE();
    v12 = sub_1400A45E0((__int64)v23, (__int64)hInstance, v145);
    if ( !(_BYTE)v24 )
      sub_140100D16(v23);
    if ( v23 )
      (**(void (__fastcall ***)(HINSTANCE, __int64))v23)(v23, 1);
    v37 = SHIBYTE(v134);
    if ( v134 < 0 )
      v37 = *((_QWORD *)&v133 + 1);
    if ( v37 == 7 )
    {
      if ( v134 < 0 )
        v38 = (__int128 *)v133;
      else
        v38 = &v133;
      if ( !(*(_DWORD *)"utility" ^ *(_DWORD *)v38 | *(_DWORD *)"lity" ^ *(_DWORD *)((char *)v38 + 3)) )
        goto LABEL_101;
    }
    else if ( v37 == 5 )
    {
      if ( v134 < 0 )
        p_Src = v133;
      if ( !(*(_DWORD *)p_Src ^ 0x70617070 | *(_BYTE *)(p_Src + 4) ^ 0x69) )
LABEL_101:
        sub_1400D92E0(v12);
    }
LABEL_125:
    sub_140101550(&Src);
LABEL_126:
    if ( v134 < 0 )
      sub_14003ABE0(v133, v134 & 0x7FFFFFFFFFFFFFFFLL);
  }
}

```

## disassembly

```asm
0x1400a2dbc  push    r15
0x1400a2dbe  push    r14
0x1400a2dc0  push    r13
0x1400a2dc2  push    r12
0x1400a2dc4  push    rsi
0x1400a2dc5  push    rdi
0x1400a2dc6  push    rbp
0x1400a2dc7  push    rbx
0x1400a2dc8  sub     rsp, 4C8h
0x1400a2dcf  movaps  [rsp+508h+var_58], xmm6
0x1400a2dd7  mov     rsi, rcx
0x1400a2dda  mov     rax, cs:__security_cookie
0x1400a2de1  xor     rax, rsp
0x1400a2de4  mov     [rsp+508h+var_60], rax
0x1400a2dec  mov     ecx, 1
0x1400a2df1  call    sub_1400A3AA1
0x1400a2df6  call    IsBrowserProcess
0x1400a2dfb  test    al, al
0x1400a2dfd  jnz     loc_1400A2ECF
0x1400a2e03  call    IsBrowserProcess
0x1400a2e08  test    al, al
0x1400a2e0a  jnz     loc_1400A2EE9
0x1400a2e10  call    sub_1400A39E3
0x1400a2e15  call    IsBrowserProcess
0x1400a2e1a  test    al, al
0x1400a2e1c  jnz     loc_1400A2EB6
0x1400a2e22  call    sub_1400A3A40
0x1400a2e27  call    sub_1400A38F0
0x1400a2e2c  call    IsBrowserProcess
0x1400a2e31  test    al, al
0x1400a2e33  jnz     loc_1400A2EC0
0x1400a2e39  call    sub_140083A20
0x1400a2e3e  test    al, al
0x1400a2e40  jnz     loc_1400A31B5
0x1400a2e46  call    sub_140083A40
0x1400a2e4b  test    al, al
0x1400a2e4d  jnz     loc_1400A31B5
0x1400a2e53  call    EdgeGetElfCommandLine
0x1400a2e58  test    rax, rax
0x1400a2e5b  jz      loc_140157D98
0x1400a2e61  mov     rdi, rax
0x1400a2e64  mov     rcx, rax
0x1400a2e67  call    sub_14011CB20
0x1400a2e6c  mov     rbx, rax
0x1400a2e6f  lea     rcx, [rsp+508h+var_360]
0x1400a2e77  mov     [rcx], rdi
0x1400a2e7a  mov     [rcx+8], rax
0x1400a2e7e  call    sub_1400A3DB0
0x1400a2e83  call    cs:GetCommandLineW
0x1400a2e89  test    rax, rax
0x1400a2e8c  jz      loc_140157D98
0x1400a2e92  mov     r14, rax
0x1400a2e95  mov     rcx, rax
0x1400a2e98  call    sub_14011CB20
0x1400a2e9d  cmp     rax, rbx
0x1400a2ea0  jnz     loc_140157D0F
0x1400a2ea6  test    rbx, rbx
0x1400a2ea9  jz      loc_1400A31B5
0x1400a2eaf  xor     eax, eax
0x1400a2eb1  jmp     loc_1400A2F6F
0x1400a2eb6  call    sub_1400A3AF6
0x1400a2ebb  jmp     loc_1400A2E22
0x1400a2ec0  mov     ecx, 1
0x1400a2ec5  call    EdgeElfBeaconDetect
0x1400a2eca  jmp     loc_1400A2E39
0x1400a2ecf  lea     rcx, aV_0; "v"
0x1400a2ed6  xor     edx, edx; hFile
0x1400a2ed8  mov     r8d, 800h; dwFlags
0x1400a2ede  call    cs:LoadLibraryExW
0x1400a2ee4  jmp     loc_1400A2E03
0x1400a2ee9  lea     rdi, [rsp+508h+Filename]
0x1400a2ef1  mov     r8d, 20Ah; Size
0x1400a2ef7  mov     rcx, rdi; Dst
0x1400a2efa  xor     edx, edx; Val
0x1400a2efc  call    memset
0x1400a2f01  xor     ecx, ecx; hModule
0x1400a2f03  mov     rdx, rdi; lpFilename
0x1400a2f06  mov     r8d, 105h; nSize
0x1400a2f0c  call    cs:GetModuleFileNameW
0x1400a2f12  lea     ecx, [rax-1]
0x1400a2f15  cmp     ecx, 103h
0x1400a2f1b  ja      loc_1400A2E10
0x1400a2f21  mov     eax, eax
0x1400a2f23  lea     rdx, [rsp+508h+var_2B8]
0x1400a2f2b  mov     [rdx], rdi
0x1400a2f2e  mov     [rdx+8], rax
0x1400a2f32  lea     rdi, [rsp+508h+TargetHandle]
0x1400a2f3a  mov     rcx, rdi
0x1400a2f3d  call    sub_140056AA0
0x1400a2f42  lea     rbx, [rsp+508h+Src]
0x1400a2f47  mov     rcx, rdi; Src
0x1400a2f4a  mov     rdx, rbx
0x1400a2f4d  call    sub_140069060
0x1400a2f52  mov     rcx, rbx; lpPathName
0x1400a2f55  call    sub_1400DD9E0
0x1400a2f5a  mov     rcx, rbx
0x1400a2f5d  call    sub_140086C50
0x1400a2f62  mov     rcx, rdi
0x1400a2f65  call    sub_140086C50
0x1400a2f6a  jmp     loc_1400A2E10
0x1400a2f6f  movzx   ecx, word ptr [r14+rax*2]
0x1400a2f74  cmp     cx, [rdi+rax*2]
0x1400a2f78  jnz     loc_140157D0F
0x1400a2f7e  inc     rax
0x1400a2f81  cmp     rbx, rax
0x1400a2f84  jnz     short loc_1400A2F6F
0x1400a2f86  jmp     loc_1400A31B5
0x1400a2f8b  lea     rdx, aUninstall; "uninstall"
0x1400a2f92  mov     rcx, rdi
0x1400a2f95  call    sub_140084760
0x1400a2f9a  test    al, al
0x1400a2f9c  jnz     loc_1400A32F8
0x1400a2fa2  call    sub_140083B6E
0x1400a2fa7  mov     rax, [rax+8]
0x1400a2fab  mov     rax, [rax+10h]
0x1400a2faf  cmp     dword ptr [rax+0Ch], 1
0x1400a2fb3  setz    al
0x1400a2fb6  mov     ecx, ebx
0x1400a2fb8  not     cl
0x1400a2fba  mov     ebp, 0Dh
0x1400a2fbf  test    cl, al
0x1400a2fc1  jnz     loc_1400A383E
0x1400a2fc7  call    sub_140083B6E
0x1400a2fcc  mov     rax, [rax+8]
0x1400a2fd0  mov     rax, [rax+10h]
0x1400a2fd4  cmp     dword ptr [rax+0Ch], 2
0x1400a2fd8  jz      loc_140158562
0x1400a2fde  call    sub_140083B6E
0x1400a2fe3  mov     rax, [rax+8]
0x1400a2fe7  mov     rax, [rax+10h]
0x1400a2feb  cmp     dword ptr [rax+0Ch], 0
0x1400a2fef  setnz   al
0x1400a2ff2  or      al, bl
0x1400a2ff4  jnz     loc_1400A32F8
0x1400a2ffa  pxor    xmm0, xmm0
0x1400a2ffe  lea     r14, [rsp+508h+Filename]
0x1400a3006  movdqa  xmmword ptr [r14], xmm0
0x1400a300b  mov     qword ptr [r14+10h], 0
0x1400a3013  mov     rcx, r14
0x1400a3016  call    sub_14003F4D0
0x1400a301b  mov     ecx, 1
0x1400a3020  mov     rdx, r14
0x1400a3023  call    sub_140081E60
0x1400a3028  test    al, al
0x1400a302a  jz      loc_140157E1F
0x1400a3030  lea     rcx, [rsp+508h+Filename]; Src
0x1400a3038  lea     r14, [rsp+508h+Src]
0x1400a303d  mov     rdx, r14
0x1400a3040  call    sub_140061790
0x1400a3045  movsx   rax, byte ptr [r14+17h]
0x1400a304a  mov     rcx, rax
0x1400a304d  test    rax, rax
0x1400a3050  jns     short loc_1400A3057
0x1400a3052  mov     rcx, [rsp+508h+var_490]
0x1400a3057  cmp     rcx, 0Ah
0x1400a305b  jnz     loc_140157E15
0x1400a3061  test    al, al
0x1400a3063  jns     short loc_1400A306A
0x1400a3065  mov     r14, [rsp+508h+Src]
0x1400a306a  lea     rax, [r14+14h]
0x1400a306e  xor     ecx, ecx
0x1400a3070  lea     rdx, aMsedgeExe_0; "msedge.exe"
0x1400a3077  movzx   r8d, word ptr [r14+rcx]
0x1400a307c  lea     r9d, [r8-41h]
0x1400a3080  lea     r10d, [r8+20h]
0x1400a3084  cmp     r9w, 1Ah
0x1400a3089  cmovnb  r10d, r8d
0x1400a308d  movzx   r8d, word ptr [rcx+rdx]
0x1400a3092  lea     r9d, [r8-41h]
0x1400a3096  lea     r11d, [r8+20h]
0x1400a309a  cmp     r9w, 1Ah
0x1400a309f  cmovnb  r11d, r8d
0x1400a30a3  cmp     r10w, r11w
0x1400a30a7  jnz     loc_140157E15
0x1400a30ad  lea     r8, [r14+rcx]
0x1400a30b1  add     r8, 2
0x1400a30b5  add     rcx, 2
0x1400a30b9  cmp     r8, rax
0x1400a30bc  jnz     short loc_1400A3077
0x1400a30be  lea     rcx, [rsp+508h+Src]
0x1400a30c3  call    sub_140086C50
0x1400a30c8  lea     rcx, [rsp+508h+Filename]
0x1400a30d0  call    sub_140086C50
0x1400a30d5  jmp     loc_1400A32F8
0x1400a30da  call    sub_1400A3E76
0x1400a30df  test    al, al
0x1400a30e1  jz      loc_1400A3270
0x1400a30e7  lea     rcx, off_140419E10
0x1400a30ee  call    sub_1400A4F3C
0x1400a30f3  test    al, al
0x1400a30f5  jz      loc_1400A3270
0x1400a30fb  lea     r14, [rsp+508h+var_340]
0x1400a3103  mov     qword ptr [r14], 0
0x1400a310a  mov     rcx, r14
0x1400a310d  call    sub_140101FE0
0x1400a3112  mov     rcx, [r14]
0x1400a3115  lea     rax, aCompatLayer; "__COMPAT_LAYER"
0x1400a311c  lea     rdx, [rsp+508h+var_2B8]
0x1400a3124  mov     [rdx], rax
0x1400a3127  mov     qword ptr [rdx+8], 0Eh
0x1400a312f  call    sub_1400A96D0
0x1400a3134  mov     r15b, 1
0x1400a3137  xor     r12d, r12d
0x1400a313a  test    al, al
0x1400a313c  jnz     loc_14015882C
0x1400a3142  xor     ebp, ebp
0x1400a3144  mov     rcx, [rsp+508h+var_340]
0x1400a314c  mov     [rsp+508h+var_340], 0
0x1400a3158  test    rcx, rcx
0x1400a315b  jz      short loc_1400A3167
0x1400a315d  mov     edx, 8
0x1400a3162  call    sub_14003ABE0
0x1400a3167  test    r15b, r15b
0x1400a316a  jnz     loc_1400A3270
0x1400a3170  jmp     loc_140158554
0x1400a3175  lea     rdx, aDisableWcosDef; "disable-wcos-default-browser-channel"
0x1400a317c  mov     rcx, rdi
0x1400a317f  call    sub_140084760
0x1400a3184  test    al, al
0x1400a3186  jnz     loc_1400A325F
0x1400a318c  lea     rdx, aAppId; "app-id"
0x1400a3193  mov     rcx, rdi
0x1400a3196  call    sub_140084760
0x1400a319b  test    al, al
0x1400a319d  jnz     loc_1400A325F
0x1400a31a3  call    sub_1400A3A9C
0x1400a31a8  test    al, al
0x1400a31aa  jz      loc_1400A325F
0x1400a31b0  jmp     loc_1401585BD
0x1400a31b5  xor     ecx, ecx
0x1400a31b7  xor     edx, edx
0x1400a31b9  call    sub_1400A3B00
0x1400a31be  call    sub_140084750
0x1400a31c3  mov     rdi, rax
0x1400a31c6  lea     rdx, aEmbeddedBrowse; "embedded-browser-webview"
0x1400a31cd  mov     rcx, rax
0x1400a31d0  call    sub_140084760
0x1400a31d5  mov     ebx, eax
0x1400a31d7  call    IsBrowserProcess
0x1400a31dc  mov     ebp, ebx
0x1400a31de  xor     bpl, 1
0x1400a31e2  and     bpl, al
0x1400a31e5  call    sub_140100CB0
0x1400a31ea  mov     rcx, rax
0x1400a31ed  mov     edx, ebp
0x1400a31ef  call    sub_1400A3A80
0x1400a31f4  lea     rdx, aHeadless; "headless"
0x1400a31fb  mov     rcx, rdi
0x1400a31fe  call    sub_140084760
0x1400a3203  mov     ebp, eax
0x1400a3205  call    IsBrowserProcess
0x1400a320a  test    bl, bl
0x1400a320c  jnz     short loc_1400A3217
0x1400a320e  test    bpl, bpl
0x1400a3211  jnz     short loc_1400A3217
0x1400a3213  test    al, al
0x1400a3215  jnz     short loc_1400A321C
0x1400a3217  call    SignalInitializeCrashReporting
0x1400a321c  pxor    xmm0, xmm0
0x1400a3220  lea     rdx, [rsp+508h+var_378]
0x1400a3228  movdqa  xmmword ptr [rdx], xmm0
0x1400a322c  mov     qword ptr [rdx+10h], 0
0x1400a3234  mov     rcx, rdi
0x1400a3237  call    sub_140100E30
0x1400a323c  call    sub_1400A3D10
0x1400a3241  test    al, al
0x1400a3243  jnz     loc_140157E38
0x1400a3249  mov     rax, [rsp+508h+var_378]
0x1400a3251  cmp     rax, [rsp+508h+var_370]
0x1400a3259  jnz     loc_1400A3175
0x1400a325f  test    bl, bl
0x1400a3261  jnz     short loc_1400A3270
0x1400a3263  call    IsBrowserProcess
0x1400a3268  test    al, al
0x1400a326a  jnz     loc_1400A30DA
0x1400a3270  pxor    xmm0, xmm0
0x1400a3274  lea     r14, [rsp+508h+var_398]
0x1400a327c  movdqa  xmmword ptr [r14], xmm0
0x1400a3281  mov     qword ptr [r14+10h], 0
0x1400a3289  lea     rax, aType; "type"
0x1400a3290  lea     r8, [rsp+508h+var_3A8]
0x1400a3298  mov     [r8], rax
0x1400a329b  mov     qword ptr [r8+8], 4
0x1400a32a3  mov     rcx, rdi
0x1400a32a6  mov     rdx, r14
0x1400a32a9  call    sub_140093590
0x1400a32ae  mov     rcx, r14
0x1400a32b1  call    nullsub_1
0x1400a32b6  movsx   rax, byte ptr [r14+17h]
0x1400a32bb  test    rax, rax
0x1400a32be  jns     short loc_1400A32C8
0x1400a32c0  mov     rax, [rsp+508h+var_390]
0x1400a32c8  test    rax, rax
0x1400a32cb  jz      loc_1400A33AC
0x1400a32d1  test    bl, bl
0x1400a32d3  jnz     loc_140157EED
0x1400a32d9  movsx   rax, [rsp+508h+var_381]
0x1400a32e2  test    rax, rax
0x1400a32e5  jns     short loc_1400A32EF
0x1400a32e7  mov     rax, [rsp+508h+var_390]
  ... truncated ...
```
