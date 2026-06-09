# TryActivateDesktopAppXApplication

- ea: `0x180094dc0`
- end: `0x180095b40`
- name: `TryActivateDesktopAppXApplication`
- size: `3456`
- prototype: ``
- caller_count: `0`
- callee_count: `22`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180004f70`
- `0x1800059a8`
- `0x18000ff24`
- `0x180012fb8`
- `0x180039d1c`
- `0x18003fd60`
- `0x1800401d4`
- `0x1800417a8`
- `0x18009322c`
- `0x180093880`
- `0x1800939d0`
- `0x180093a78`
- `0x180093ba4`
- `0x180093fb4`
- `0x180094378`
- `0x1800944e0`
- `0x180094dc0`
- `0x180098fbc`
- `0x1800b1b68`
- `0x1800b5490`
- `0x1800bde50`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18009551d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18009551d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18009556d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18009556d`

## string_xrefs

- `0x180095435`: `The attempt to repair the app failed after an unsuccessful launch.`
- `0x180095188`: `Failed to repair package %ws. Extended error code: 0x%x`
- `0x180095204`: `Still failed after successfully repairing the package %ws`
- `0x180094f31`: `onecore\base\appmodel\execmodel\desktopappx\desktoplib\desktopaamextensions.cpp`
- `0x180094f6d`: `onecore\base\appmodel\execmodel\desktopappx\desktoplib\desktopaamextensions.cpp`
- `0x180094fa9`: `onecore\base\appmodel\execmodel\desktopappx\desktoplib\desktopaamextensions.cpp`
- `0x180094fe5`: `onecore\base\appmodel\execmodel\desktopappx\desktoplib\desktopaamextensions.cpp`
- `0x180095021`: `onecore\base\appmodel\execmodel\desktopappx\desktoplib\desktopaamextensions.cpp`
- `0x18009509a`: `onecore\base\appmodel\execmodel\desktopappx\desktoplib\desktopaamextensions.cpp`
- `0x1800950d7`: `onecore\base\appmodel\execmodel\desktopappx\desktoplib\desktopaamextensions.cpp`
- `0x180095141`: `onecore\base\appmodel\execmodel\desktopappx\desktoplib\desktopaamextensions.cpp`
- `0x180095197`: `onecore\base\appmodel\execmodel\desktopappx\desktoplib\desktopaamextensions.cpp`
- `0x180095213`: `onecore\base\appmodel\execmodel\desktopappx\desktoplib\desktopaamextensions.cpp`
- `0x180095253`: `onecore\base\appmodel\execmodel\desktopappx\desktoplib\desktopaamextensions.cpp`
- `0x1800952eb`: `onecore\base\appmodel\execmodel\desktopappx\desktoplib\desktopaamextensions.cpp`
- `0x180095412`: `onecore\base\appmodel\execmodel\desktopappx\desktoplib\desktopaamextensions.cpp`
- `0x180095444`: `onecore\base\appmodel\execmodel\desktopappx\desktoplib\desktopaamextensions.cpp`
- `0x180095471`: `onecore\base\appmodel\execmodel\desktopappx\desktoplib\desktopaamextensions.cpp`
- `0x18009558a`: `onecore\base\appmodel\execmodel\desktopappx\desktoplib\desktopaamextensions.cpp`
- `0x18009567c`: `onecore\base\appmodel\execmodel\desktopappx\desktoplib\desktopaamextensions.cpp`
- `0x18009574e`: `onecore\base\appmodel\execmodel\desktopappx\desktoplib\desktopaamextensions.cpp`
- `0x180095132`: `Try to repair package %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=11 #try_helpers=1
__int64 __fastcall TryActivateDesktopAppXApplication(__int64 a1, struct DESKTOP_APPX_ACTIVATION_RESULT *a2)
{
  struct DESKTOP_APPX_ACTIVATION_RESULT *v2; // r13
  __int64 v4; // rax
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rcx
  __int64 v9; // rcx
  const char *v10; // rbx
  int v11; // r15d
  int v12; // r15d
  unsigned int v13; // r10d
  int v14; // eax
  int v15; // r15d
  _BYTE *v16; // rax
  char **v17; // rcx
  int v18; // eax
  int v19; // eax
  char **v20; // rdx
  __int64 v21; // r8
  HRESULT v22; // eax
  int v23; // edx
  unsigned int v24; // r8d
  HSTRING v25; // rbx
  char *v26; // rcx
  int ActivationFactory; // eax
  unsigned int v28; // ebx
  char *v29; // rcx
  char *v30; // rdi
  __int64 (__fastcall *v31)(char *, _QWORD, __int64 *); // rbx
  char **v32; // rdx
  __int64 v33; // rax
  int v34; // eax
  __int64 v35; // rcx
  char *v36; // rcx
  int v37; // eax
  unsigned int v38; // ebx
  __int64 v39; // rcx
  char *v40; // rcx
  const unsigned __int16 *v41; // r8
  struct IInspectable *v42; // rax
  const char *v43; // r9
  __int64 v44; // rcx
  char *v45; // rcx
  const unsigned __int16 *v46; // rdi
  const unsigned __int16 *v47; // rbx
  const unsigned __int16 *v48; // r9
  char **v49; // r8
  const unsigned __int16 *v50; // rdx
  const unsigned __int16 *v51; // rcx
  const unsigned __int16 *v52; // r9
  char **v53; // r8
  int v54; // [rsp+20h] [rbp-498h]
  int v55; // [rsp+20h] [rbp-498h]
  int v56; // [rsp+20h] [rbp-498h]
  char *v57; // [rsp+28h] [rbp-490h]
  char *v58; // [rsp+28h] [rbp-490h]
  char v59; // [rsp+88h] [rbp-430h]
  unsigned int v60; // [rsp+90h] [rbp-428h]
  _BYTE v61[8]; // [rsp+A0h] [rbp-418h] BYREF
  char *v62; // [rsp+A8h] [rbp-410h] BYREF
  int v63; // [rsp+B0h] [rbp-408h]
  __int64 v64; // [rsp+B8h] [rbp-400h] BYREF
  struct PackageInformation *v65; // [rsp+C0h] [rbp-3F8h] BYREF
  unsigned int v66[2]; // [rsp+C8h] [rbp-3F0h] BYREF
  unsigned int v67[2]; // [rsp+D0h] [rbp-3E8h]
  char **v68; // [rsp+D8h] [rbp-3E0h] BYREF
  unsigned __int16 *v69[2]; // [rsp+E0h] [rbp-3D8h] BYREF
  struct IInspectable *v70[2]; // [rsp+F0h] [rbp-3C8h]
  unsigned int v71[4]; // [rsp+100h] [rbp-3B8h]
  __int64 v72; // [rsp+110h] [rbp-3A8h]
  __int64 v73; // [rsp+118h] [rbp-3A0h]
  struct DESKTOP_APPX_ACTIVATION_RESULT *v74; // [rsp+120h] [rbp-398h]
  _OWORD v75[5]; // [rsp+130h] [rbp-388h] BYREF
  int v76; // [rsp+180h] [rbp-338h]
  _BYTE v77[12]; // [rsp+184h] [rbp-334h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+190h] [rbp-328h] BYREF
  HSTRING string; // [rsp+1A8h] [rbp-310h] BYREF
  unsigned __int16 *v80[3]; // [rsp+1B0h] [rbp-308h] BYREF
  unsigned __int64 v81; // [rsp+1C8h] [rbp-2F0h]
  char *v82[3]; // [rsp+230h] [rbp-288h] BYREF
  unsigned __int64 v83; // [rsp+248h] [rbp-270h]
  unsigned __int16 *v84[3]; // [rsp+250h] [rbp-268h] BYREF
  unsigned __int64 v85; // [rsp+268h] [rbp-250h]
  unsigned __int16 *v86[3]; // [rsp+2B0h] [rbp-208h] BYREF
  unsigned __int64 v87; // [rsp+2C8h] [rbp-1F0h]
  unsigned int v88; // [rsp+2D0h] [rbp-1E8h]
  unsigned int v89; // [rsp+2D4h] [rbp-1E4h]
  unsigned int v90; // [rsp+2D8h] [rbp-1E0h]
  unsigned int v91; // [rsp+2DCh] [rbp-1DCh]
  bool v92; // [rsp+2E1h] [rbp-1D7h]
  void **v93; // [rsp+340h] [rbp-178h] BYREF
  int v94; // [rsp+348h] [rbp-170h] BYREF
  char v95; // [rsp+34Ch] [rbp-16Ch]
  int v96; // [rsp+370h] [rbp-148h] BYREF
  const char *v97; // [rsp+378h] [rbp-140h]
  __int64 v98; // [rsp+380h] [rbp-138h]
  char v99; // [rsp+388h] [rbp-130h]
  int v100; // [rsp+390h] [rbp-128h]
  _BYTE v101[168]; // [rsp+398h] [rbp-120h] BYREF
  int v102; // [rsp+440h] [rbp-78h]
  __int64 v103; // [rsp+448h] [rbp-70h]
  int *v104; // [rsp+450h] [rbp-68h]
  __int64 v105; // [rsp+458h] [rbp-60h]
  __int64 v106; // [rsp+460h] [rbp-58h]
  void ***v107; // [rsp+468h] [rbp-50h]
  __int64 v108; // [rsp+470h] [rbp-48h]
  int v109; // [rsp+478h] [rbp-40h]
  int *v110; // [rsp+480h] [rbp-38h]
  char v111; // [rsp+488h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+4B8h] [rbp+0h]

  v2 = a2;
  v74 = a2;
  v94 = 0;
  v95 = 0;
  v99 = 0;
  v96 = 0;
  v97 = "TryActivateDesktopAppXApplication";
  v98 = 0;
  v100 = 0;
  *(_OWORD *)&v101[152] = 0;
  memset_0(v101, 0, 0x98u);
  v102 = 1;
  v103 = 0;
  v104 = &v94;
  v105 = 0;
  v106 = 0;
  v107 = &v93;
  v108 = 0;
  v109 = 0;
  v110 = &v96;
  v111 = 0;
  v93 = &DesktopAppXProvider::TryActivateDesktopAppXApplication::`vftable';
  DesktopAppXProvider::TryActivateDesktopAppXApplication::StartActivity(
    (DesktopAppXProvider::TryActivateDesktopAppXApplication *)&v93,
    *(const unsigned __int16 **)a1);
  *(_OWORD *)v69 = *(_OWORD *)a1;
  *(_OWORD *)v70 = *(_OWORD *)(a1 + 16);
  *(_OWORD *)v71 = *(_OWORD *)(a1 + 32);
  v73 = *(_QWORD *)(a1 + 56);
  v72 = 0;
  v4 = *(_QWORD *)(a1 + 40);
  if ( (v4 & 0x4E0) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBC,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\desktoplib\\desktopaamextensions.cpp",
      (const char *)0x80070057LL,
      v54);
    DesktopAppXProvider::TryActivateDesktopAppXApplication::~TryActivateDesktopAppXApplication((DesktopAppXProvider::TryActivateDesktopAppXApplication *)&v93);
    return 2147942487LL;
  }
  if ( (v4 & 0x100) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBD,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\desktoplib\\desktopaamextensions.cpp",
      (const char *)0x80070057LL,
      v54);
    DesktopAppXProvider::TryActivateDesktopAppXApplication::~TryActivateDesktopAppXApplication((DesktopAppXProvider::TryActivateDesktopAppXApplication *)&v93);
    return 2147942487LL;
  }
  if ( (v4 & 0x800) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBE,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\desktoplib\\desktopaamextensions.cpp",
      (const char *)0x80070057LL,
      v54);
    DesktopAppXProvider::TryActivateDesktopAppXApplication::~TryActivateDesktopAppXApplication((DesktopAppXProvider::TryActivateDesktopAppXApplication *)&v93);
    return 2147942487LL;
  }
  if ( (v4 & 0x1000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBF,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\desktoplib\\desktopaamextensions.cpp",
      (const char *)0x80070057LL,
      v54);
    DesktopAppXProvider::TryActivateDesktopAppXApplication::~TryActivateDesktopAppXApplication((DesktopAppXProvider::TryActivateDesktopAppXApplication *)&v93);
    return 2147942487LL;
  }
  if ( (v4 & 0x2000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC0,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\desktoplib\\desktopaamextensions.cpp",
      (const char *)0x80070057LL,
      v54);
    DesktopAppXProvider::TryActivateDesktopAppXApplication::~TryActivateDesktopAppXApplication((DesktopAppXProvider::TryActivateDesktopAppXApplication *)&v93);
    return 2147942487LL;
  }
  ActivationProperties::ActivationProperties((ActivationProperties *)v80);
  *(_QWORD *)v66 = 0;
  *(_QWORD *)v67 = 0;
  v6 = EvaluateApplicationLaunch(
         (const struct DESKTOP_APPX_ACTIVATION_PARAMS *)v69,
         (struct ActivationProperties *)v80,
         v2,
         (struct AppDeploymentInfo *)v66);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xC4,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\desktoplib\\desktopaamextensions.cpp",
      (const char *)(unsigned int)v6,
      v54);
    if ( v7 != -2144927148 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE5,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\desktoplib\\desktopaamextensions.cpp",
        (const char *)v7,
        v55);
      ActivationProperties::~ActivationProperties((ActivationProperties *)v80);
      DesktopAppXProvider::TryActivateDesktopAppXApplication::~TryActivateDesktopAppXApplication((DesktopAppXProvider::TryActivateDesktopAppXApplication *)&v93);
      return v7;
    }
    MicrosoftTelemetryAssertTriggeredNoArgs(v8);
    if ( !v82[2] )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v9);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD5,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\desktoplib\\desktopaamextensions.cpp",
        (const char *)0x80270254LL,
        v55);
      ActivationProperties::~ActivationProperties((ActivationProperties *)v80);
      DesktopAppXProvider::TryActivateDesktopAppXApplication::~TryActivateDesktopAppXApplication((DesktopAppXProvider::TryActivateDesktopAppXApplication *)&v93);
      return 2150040148LL;
    }
    v10 = (const char *)v82;
    if ( v83 > 7 )
      v10 = v82[0];
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0xD9,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\desktoplib\\desktopaamextensions.cpp",
      (const char *)0x80270254LL,
      (int)"Try to repair package %ws",
      v10);
    LODWORD(v62) = 0;
    v11 = RepairPackage((const unsigned __int16 *)v10, (int *)&v62);
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xDC,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\desktoplib\\desktopaamextensions.cpp",
        (const char *)(unsigned int)v11,
        (int)"Failed to repair package %ws. Extended error code: 0x%x",
        v10,
        (_DWORD)v62);
      ActivationProperties::~ActivationProperties((ActivationProperties *)v80);
      DesktopAppXProvider::TryActivateDesktopAppXApplication::~TryActivateDesktopAppXApplication((DesktopAppXProvider::TryActivateDesktopAppXApplication *)&v93);
      return (unsigned int)v11;
    }
    v12 = EvaluateApplicationLaunch(
            (const struct DESKTOP_APPX_ACTIVATION_PARAMS *)v69,
            (struct ActivationProperties *)v80,
            v2,
            (struct AppDeploymentInfo *)v66);
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xE0,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\desktoplib\\desktopaamextensions.cpp",
        (const char *)(unsigned int)v12,
        (int)"Still failed after successfully repairing the package %ws",
        v10);
      ActivationProperties::~ActivationProperties((ActivationProperties *)v80);
      DesktopAppXProvider::TryActivateDesktopAppXApplication::~TryActivateDesktopAppXApplication((DesktopAppXProvider::TryActivateDesktopAppXApplication *)&v93);
      return (unsigned int)v12;
    }
  }
  if ( *(_DWORD *)v2 == 1 )
  {
    v13 = v90;
LABEL_95:
    v50 = (const unsigned __int16 *)v86;
    if ( v87 > 7 )
      v50 = v86[0];
    v51 = (const unsigned __int16 *)v80;
    if ( v81 > 7 )
      v51 = v80[0];
    v52 = (const unsigned __int16 *)v84;
    if ( v85 > 7 )
      v52 = v84[0];
    v53 = v82;
    if ( v83 > 7 )
      v53 = (char **)v82[0];
    DesktopAppXProvider::TryActivateDesktopAppXApplication::Stop(
      (DesktopAppXProvider::TryActivateDesktopAppXApplication *)&v93,
      v69[0],
      (const unsigned __int16 *)v53,
      v52,
      v51,
      v50,
      v88,
      v89,
      v91,
      v92,
      v13,
      v71[2],
      *(_DWORD *)v2,
      v66[0],
      v66[1],
      v67[0],
      v67[1],
      v59,
      v60);
    ActivationProperties::~ActivationProperties((ActivationProperties *)v80);
    DesktopAppXProvider::TryActivateDesktopAppXApplication::~TryActivateDesktopAppXApplication((DesktopAppXProvider::TryActivateDesktopAppXApplication *)&v93);
    return 0;
  }
  if ( (v71[2] & 0x4000) != 0 )
  {
    v13 = v90;
    if ( v90 != 2 )
      goto LABEL_95;
  }
  v14 = InternalTryActivateDesktopAppXApplication(
          (const struct DESKTOP_APPX_ACTIVATION_PARAMS *)v69,
          (struct ActivationProperties *)v80,
          v2,
          0);
  v15 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xFC,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\desktoplib\\desktopaamextensions.cpp",
      (const char *)(unsigned int)v14,
      v54);
    if ( v15 != -2147023673 && v15 != -2147009250 )
    {
      v75[0] = _mm_load_si128((const __m128i *)&_xmm);
      v75[1] = _mm_load_si128((const __m128i *)&_xmm);
      v75[2] = _mm_load_si128((const __m128i *)&_xmm);
      v75[3] = _mm_load_si128((const __m128i *)&_xmm);
      v75[4] = _mm_load_si128((const __m128i *)&_xmm);
      v76 = -2147012894;
      v16 = v75;
      v63 = v15;
      while ( v15 != *(_DWORD *)v16 )
      {
        v16 += 4;
        if ( v16 == v77 )
        {
          if ( v15 == -2144927148 || v15 == -2147009195 )
            MicrosoftTelemetryAssertTriggeredNoArgs(v77);
          LODWORD(v62) = 0;
          v17 = v82;
          if ( v83 > 7 )
            v17 = (char **)v82[0];
          v18 = RepairPackage((const unsigned __int16 *)v17, (int *)&v62);
          if ( v18 < 0 )
          {
            wil::details::in1diag3::Log_HrMsg(
              retaddr,
              (void *)0x110,
              (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\desktoplib\\desktopaamextensions.cpp",
              (const char *)(unsigned int)v18,
              (int)"The attempt to repair the app failed after an unsuccessful launch.",
              v57);
            wil::details::in1diag3::Log_HrMsg(
              retaddr,
              (void *)0x111,
              (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\desktoplib\\desktopaamextensions.cpp",
              (const char *)(unsigned int)v62,
              (int)"Extended Error Code.",
              v58);
          }
          else
          {
            v19 = InternalTryActivateDesktopAppXApplication(
                    (const struct DESKTOP_APPX_ACTIVATION_PARAMS *)v69,
                    (struct ActivationProperties *)v80,
                    v2,
                    1);
            v15 = v19;
            if ( v19 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x117,
                (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\desktoplib\\desktopaamextensions.cpp",
                (const char *)(unsigned int)v19,
                v56);
            v63 = v15;
          }
          break;
        }
      }
      if ( v15 < 0 )
      {
        v20 = v82;
        if ( v83 > 7 )
          v20 = (char **)v82[0];
        memset(&hstringHeader, 0, sizeof(hstringHeader));
        string = 0;
        v21 = -1;
        do
          ++v21;
        while ( *((_WORD *)v20 + v21) );
        std::wstring::_Construct<1,unsigned short const *>(&hstringHeader, v20, v21);
        CreatePackageInformation(&v65, &hstringHeader);
        v62 = 0;
        string = 0;
        v22 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.Package", 0x28u, &hstringHeader, &string);
        if ( v22 < 0 )
        {
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v22, v23, v24);
          JUMPOUT(0x180095B3ELL);
        }
        v25 = string;
        v26 = v62;
        if ( v62 )
        {
          v62 = 0;
          (*(void (__fastcall **)(char *))(*(_QWORD *)v26 + 16LL))(v26);
        }
        ActivationFactory = RoGetActivationFactory(v25, &GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419, &v62);
        v28 = ActivationFactory;
        if ( ActivationFactory < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x126,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\desktoplib\\desktopaamextensions.cpp",
            (const char *)(unsigned int)ActivationFactory,
            v56);
          v29 = v62;
          if ( v62 )
          {
            v62 = 0;
            (*(void (__fastcall **)(char *))(*(_QWORD *)v29 + 16LL))(v29);
          }
          if ( v65 )
            (**(void (__fastcall ***)(struct PackageInformation *, __int64))v65)(v65, 1);
LABEL_54:
          ActivationProperties::~ActivationProperties((ActivationProperties *)v80);
          DesktopAppXProvider::TryActivateDesktopAppXApplication::~TryActivateDesktopAppXApplication((DesktopAppXProvider::TryActivateDesktopAppXApplication *)&v93);
          return v28;
        }
        v64 = 0;
        v30 = v62;
        v31 = *(__int64 (__fastcall **)(char *, _QWORD, __int64 *))(*(_QWORD *)v62 + 176LL);
        v32 = v82;
        if ( v83 > 7 )
          v32 = (char **)v82[0];
        v68 = v32;
        v33 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v68);
        v34 = v31(v30, *(_QWORD *)(v33 + 24), &v64);
        v28 = v34;
        if ( v34 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x128,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\desktoplib\\desktopaamextensions.cpp",
            (const char *)(unsigned int)v34,
            v56);
          v35 = v64;
          if ( v64 )
          {
            v64 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
          }
          v36 = v62;
          if ( v62 )
          {
            v62 = 0;
            (*(void (__fastcall **)(char *))(*(_QWORD *)v36 + 16LL))(v36);
          }
          if ( v65 )
            (**(void (__fastcall ***)(struct PackageInformation *, __int64))v65)(v65, 1);
          goto LABEL_54;
        }
        v61[0] = 0;
        v37 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v64 + 320LL))(v64, v61);
        v38 = v37;
        if ( v37 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x12A,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\desktoplib\\desktopaamextensions.cpp",
            (const char *)(unsigned int)v37,
            v56);
          v39 = v64;
          if ( v64 )
          {
            v64 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
          }
          v40 = v62;
          if ( v62 )
          {
            v62 = 0;
            (*(void (__fastcall **)(char *))(*(_QWORD *)v40 + 16LL))(v40);
          }
          if ( v65 )
            (**(void (__fastcall ***)(struct PackageInformation *, __int64))v65)(v65, 1);
          ActivationProperties::~ActivationProperties((ActivationProperties *)v80);
          DesktopAppXProvider::TryActivateDesktopAppXApplication::~TryActivateDesktopAppXApplication((DesktopAppXProvider::TryActivateDesktopAppXApplication *)&v93);
          return v38;
        }
        if ( v65 && (v61[0] || *(_QWORD *)v71) )
        {
          if ( LODWORD(v69[1]) == 1 )
          {
            v41 = (const unsigned __int16 *)v70[0];
            v42 = v70[1];
          }
          else
          {
            v41 = 0;
            v42 = 0;
          }
          try
          {
            CreateAndLaunchAppActivationErrorHandler(v65, v69[0], v41, (v71[2] & 1) << 29, v42, v15);
          }
          catch ( ... )
          {
            wil::details::in1diag3::Log_CaughtException(
              retaddr,
              (void *)0x140,
              (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\desktoplib\\desktopaamextensions.cpp",
              v43);
            v15 = v63;
            v2 = v74;
          }
        }
        v44 = v64;
        if ( v64 )
        {
          v64 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
        }
        v45 = v62;
        if ( v62 )
        {
          v62 = 0;
          (*(void (__fastcall **)(char *))(*(_QWORD *)v45 + 16LL))(v45);
        }
        if ( v65 )
          (**(void (__fastcall ***)(struct PackageInformation *, __int64))v65)(v65, 1);
      }
    }
  }
  v46 = (const unsigned __int16 *)v86;
  if ( v87 > 7 )
    v46 = v86[0];
  v47 = (const unsigned __int16 *)v80;
  if ( v81 > 7 )
    v47 = v80[0];
  v48 = (const unsigned __int16 *)v84;
  if ( v85 > 7 )
    v48 = v84[0];
  v49 = v82;
  if ( v83 > 7 )
    v49 = (char **)v82[0];
  DesktopAppXProvider::TryActivateDesktopAppXApplication::Stop(
    (DesktopAppXProvider::TryActivateDesktopAppXApplication *)&v93,
    v69[0],
    (const unsigned __int16 *)v49,
    v48,
    v47,
    v46,
    v88,
    v89,
    v92,
    v90 != 0,
    v71[2],
    *(_DWORD *)v2,
    v66[0],
    v66[1],
    v67[0],
    v67[1],
    v15,
    v59,
    v60);
  ActivationProperties::~ActivationProperties((ActivationProperties *)v80);
  DesktopAppXProvider::TryActivateDesktopAppXApplication::~TryActivateDesktopAppXApplication((DesktopAppXProvider::TryActivateDesktopAppXApplication *)&v93);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180094dc0  mov     r11, rsp
0x180094dc3  mov     [r11+18h], rbx
0x180094dc7  mov     [r11+20h], rsi
0x180094dcb  push    rdi
0x180094dcc  push    r13
0x180094dce  push    r15
0x180094dd0  sub     rsp, 4A0h
0x180094dd7  mov     rax, cs:__security_cookie
0x180094dde  xor     rax, rsp
0x180094de1  mov     [rsp+4B8h+var_28], rax
0x180094de9  mov     r13, rdx
0x180094dec  mov     rbx, rcx
0x180094def  mov     [rsp+4B8h+var_398], rdx
0x180094df7  xor     esi, esi
0x180094df9  mov     [rsp+4B8h+var_170], esi
0x180094e00  mov     [rsp+4B8h+var_16C], sil
0x180094e08  mov     [rsp+4B8h+var_130], sil
0x180094e10  mov     [rsp+4B8h+var_148], esi
0x180094e17  lea     rax, aTryactivatedes_0; "TryActivateDesktopAppXApplication"
0x180094e1e  mov     [r11-140h], rax
0x180094e25  mov     [r11-138h], rsi
0x180094e2c  mov     [rsp+4B8h+var_128], esi
0x180094e33  xorps   xmm0, xmm0
0x180094e36  movdqa  [rsp+4B8h+var_88], xmm0
0x180094e3f  xor     edx, edx; Val
0x180094e41  mov     r8d, 98h; Size
0x180094e47  lea     rcx, [r11-120h]; void *
0x180094e4e  call    memset_0
0x180094e53  mov     [rsp+4B8h+var_78], 1
0x180094e5e  xor     eax, eax
0x180094e60  mov     [rsp+4B8h+var_70], rax
0x180094e68  lea     rax, [rsp+4B8h+var_170]
0x180094e70  mov     [rsp+4B8h+var_68], rax
0x180094e78  mov     [rsp+4B8h+var_60], rsi
0x180094e80  mov     [rsp+4B8h+var_58], rsi
0x180094e88  lea     rax, [rsp+4B8h+var_178]
0x180094e90  mov     [rsp+4B8h+var_50], rax
0x180094e98  mov     [rsp+4B8h+var_48], rsi
0x180094ea0  mov     [rsp+4B8h+var_40], esi
0x180094ea7  lea     rax, [rsp+4B8h+var_148]
0x180094eaf  mov     [rsp+4B8h+var_38], rax
0x180094eb7  mov     [rsp+4B8h+var_30], sil
0x180094ebf  lea     rax, ??_7TryActivateDesktopAppXApplication@DesktopAppXProvider@@6B@; const DesktopAppXProvider::TryActivateDesktopAppXApplication::`vftable'
0x180094ec6  mov     [rsp+4B8h+var_178], rax
0x180094ece  mov     rdx, [rbx]; unsigned __int16 *
0x180094ed1  lea     rcx, [rsp+4B8h+var_178]; this
0x180094ed9  call    ?StartActivity@TryActivateDesktopAppXApplication@DesktopAppXProvider@@QEAAXPEBG@Z; DesktopAppXProvider::TryActivateDesktopAppXApplication::StartActivity(ushort const *)
0x180094ede  nop
0x180094edf  movups  xmm0, xmmword ptr [rbx]
0x180094ee2  movaps  xmmword ptr [rsp+4B8h+var_3D8], xmm0
0x180094eea  movups  xmm1, xmmword ptr [rbx+10h]
0x180094eee  movaps  xmmword ptr [rsp+4B8h+var_3C8], xmm1
0x180094ef6  movups  xmm2, xmmword ptr [rbx+20h]
0x180094efa  movaps  xmmword ptr [rsp+4B8h+var_3B8], xmm2
0x180094f02  movups  xmm0, xmmword ptr [rbx+30h]
0x180094f06  movaps  [rsp+4B8h+var_3A8], xmm0
0x180094f0e  mov     qword ptr [rsp+4B8h+var_3A8], rsi
0x180094f16  mov     rax, [rbx+28h]
0x180094f1a  test    eax, 4E0h
0x180094f1f  jz      short loc_180094F57
0x180094f21  mov     rcx, [rsp+4B8h]; this
0x180094f29  mov     ebx, 80070057h
0x180094f2e  mov     r9d, ebx; char *
0x180094f31  lea     r8, aOnecoreBaseApp_59; "onecore\\base\\appmodel\\execmodel\\des"...
0x180094f38  mov     edx, 0BCh; void *
0x180094f3d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180094f42  nop
0x180094f43  lea     rcx, [rsp+4B8h+var_178]; this
0x180094f4b  call    ??1TryActivateDesktopAppXApplication@DesktopAppXProvider@@QEAA@XZ; DesktopAppXProvider::TryActivateDesktopAppXApplication::~TryActivateDesktopAppXApplication(void)
0x180094f50  mov     eax, ebx
0x180094f52  jmp     loc_180095B0D
0x180094f57  bt      eax, 8
0x180094f5b  jnb     short loc_180094F93
0x180094f5d  mov     rcx, [rsp+4B8h]; this
0x180094f65  mov     ebx, 80070057h
0x180094f6a  mov     r9d, ebx; char *
0x180094f6d  lea     r8, aOnecoreBaseApp_59; "onecore\\base\\appmodel\\execmodel\\des"...
0x180094f74  mov     edx, 0BDh; void *
0x180094f79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180094f7e  nop
0x180094f7f  lea     rcx, [rsp+4B8h+var_178]; this
0x180094f87  call    ??1TryActivateDesktopAppXApplication@DesktopAppXProvider@@QEAA@XZ; DesktopAppXProvider::TryActivateDesktopAppXApplication::~TryActivateDesktopAppXApplication(void)
0x180094f8c  mov     eax, ebx
0x180094f8e  jmp     loc_180095B0D
0x180094f93  bt      eax, 0Bh
0x180094f97  jnb     short loc_180094FCF
0x180094f99  mov     rcx, [rsp+4B8h]; this
0x180094fa1  mov     ebx, 80070057h
0x180094fa6  mov     r9d, ebx; char *
0x180094fa9  lea     r8, aOnecoreBaseApp_59; "onecore\\base\\appmodel\\execmodel\\des"...
0x180094fb0  mov     edx, 0BEh; void *
0x180094fb5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180094fba  nop
0x180094fbb  lea     rcx, [rsp+4B8h+var_178]; this
0x180094fc3  call    ??1TryActivateDesktopAppXApplication@DesktopAppXProvider@@QEAA@XZ; DesktopAppXProvider::TryActivateDesktopAppXApplication::~TryActivateDesktopAppXApplication(void)
0x180094fc8  mov     eax, ebx
0x180094fca  jmp     loc_180095B0D
0x180094fcf  bt      eax, 0Ch
0x180094fd3  jnb     short loc_18009500B
0x180094fd5  mov     rcx, [rsp+4B8h]; this
0x180094fdd  mov     ebx, 80070057h
0x180094fe2  mov     r9d, ebx; char *
0x180094fe5  lea     r8, aOnecoreBaseApp_59; "onecore\\base\\appmodel\\execmodel\\des"...
0x180094fec  mov     edx, 0BFh; void *
0x180094ff1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180094ff6  nop
0x180094ff7  lea     rcx, [rsp+4B8h+var_178]; this
0x180094fff  call    ??1TryActivateDesktopAppXApplication@DesktopAppXProvider@@QEAA@XZ; DesktopAppXProvider::TryActivateDesktopAppXApplication::~TryActivateDesktopAppXApplication(void)
0x180095004  mov     eax, ebx
0x180095006  jmp     loc_180095B0D
0x18009500b  bt      eax, 0Dh
0x18009500f  jnb     short loc_180095047
0x180095011  mov     rcx, [rsp+4B8h]; this
0x180095019  mov     ebx, 80070057h
0x18009501e  mov     r9d, ebx; char *
0x180095021  lea     r8, aOnecoreBaseApp_59; "onecore\\base\\appmodel\\execmodel\\des"...
0x180095028  mov     edx, 0C0h; void *
0x18009502d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180095032  nop
0x180095033  lea     rcx, [rsp+4B8h+var_178]; this
0x18009503b  call    ??1TryActivateDesktopAppXApplication@DesktopAppXProvider@@QEAA@XZ; DesktopAppXProvider::TryActivateDesktopAppXApplication::~TryActivateDesktopAppXApplication(void)
0x180095040  mov     eax, ebx
0x180095042  jmp     loc_180095B0D
0x180095047  lea     rcx, [rsp+4B8h+var_308]; this
0x18009504f  call    ??0ActivationProperties@@QEAA@XZ; ActivationProperties::ActivationProperties(void)
0x180095054  nop
0x180095055  mov     qword ptr [rsp+4B8h+var_3F0], rsi
0x18009505d  mov     qword ptr [rsp+4B8h+var_3E8], rsi
0x180095065  lea     r9, [rsp+4B8h+var_3F0]; struct AppDeploymentInfo *
0x18009506d  mov     r8, r13; struct DESKTOP_APPX_ACTIVATION_RESULT *
0x180095070  lea     rdx, [rsp+4B8h+var_308]; struct ActivationProperties *
0x180095078  lea     rcx, [rsp+4B8h+var_3D8]; struct DESKTOP_APPX_ACTIVATION_PARAMS *
0x180095080  call    ?EvaluateApplicationLaunch@@YAJPEBUDESKTOP_APPX_ACTIVATION_PARAMS@@AEAUActivationProperties@@PEAUDESKTOP_APPX_ACTIVATION_RESULT@@PEAUAppDeploymentInfo@@@Z; EvaluateApplicationLaunch(DESKTOP_APPX_ACTIVATION_PARAMS const *,ActivationProperties &,DESKTOP_APPX_ACTIVATION_RESULT *,AppDeploymentInfo *)
0x180095085  mov     ebx, eax
0x180095087  mov     rcx, [rsp+4B8h]; this
0x18009508f  test    eax, eax
0x180095091  jns     loc_180095287
0x180095097  mov     r9d, eax; char *
0x18009509a  lea     r8, aOnecoreBaseApp_59; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800950a1  mov     edx, 0C4h; void *
0x1800950a6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800950ab  mov     edi, 80270254h
0x1800950b0  cmp     ebx, edi
0x1800950b2  jnz     loc_180095248
0x1800950b8  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "false", "EvaluateApplicationLaunch failed with E_APPLICATION_NOT_REGISTERED")
0x1800950bd  cmp     [rsp+4B8h+var_278], rsi
0x1800950c5  jnz     short loc_18009510B
0x1800950c7  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "false", "EvaluateApplicationLaunch failed before resolving package full name. No retry.")
0x1800950cc  mov     rcx, [rsp+4B8h]; this
0x1800950d4  mov     r9d, edi; char *
0x1800950d7  lea     r8, aOnecoreBaseApp_59; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800950de  mov     edx, 0D5h; void *
0x1800950e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800950e8  nop
0x1800950e9  lea     rcx, [rsp+4B8h+var_308]; this
0x1800950f1  call    ??1ActivationProperties@@QEAA@XZ; ActivationProperties::~ActivationProperties(void)
0x1800950f6  nop
0x1800950f7  lea     rcx, [rsp+4B8h+var_178]; this
0x1800950ff  call    ??1TryActivateDesktopAppXApplication@DesktopAppXProvider@@QEAA@XZ; DesktopAppXProvider::TryActivateDesktopAppXApplication::~TryActivateDesktopAppXApplication(void)
0x180095104  mov     eax, edi
0x180095106  jmp     loc_180095B0D
0x18009510b  lea     rbx, [rsp+4B8h+var_288]
0x180095113  cmp     [rsp+4B8h+var_270], 7
0x18009511c  cmova   rbx, [rsp+4B8h+var_288]
0x180095125  mov     rcx, [rsp+4B8h]; this
0x18009512d  mov     [rsp+4B8h+var_490], rbx; char *
0x180095132  lea     rax, aTryToRepairPac; "Try to repair package %ws"
0x180095139  mov     [rsp+4B8h+var_498], rax; int
0x18009513e  mov     r9d, edi; char *
0x180095141  lea     r8, aOnecoreBaseApp_59; "onecore\\base\\appmodel\\execmodel\\des"...
0x180095148  mov     edx, 0D9h; void *
0x18009514d  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180095152  mov     dword ptr [rsp+4B8h+var_410], esi
0x180095159  lea     rdx, [rsp+4B8h+var_410]; int *
0x180095161  mov     rcx, rbx; unsigned __int16 *
0x180095164  call    ?RepairPackage@@YAJPEBGPEAJ@Z; RepairPackage(ushort const *,long *)
0x180095169  mov     r15d, eax
0x18009516c  test    eax, eax
0x18009516e  jns     short loc_1800951CC
0x180095170  mov     rcx, [rsp+4B8h]; this
0x180095178  mov     edx, dword ptr [rsp+4B8h+var_410]
0x18009517f  mov     [rsp+4B8h+var_488], edx
0x180095183  mov     [rsp+4B8h+var_490], rbx; char *
0x180095188  lea     rax, aFailedToRepair; "Failed to repair package %ws. Extended "...
0x18009518f  mov     [rsp+4B8h+var_498], rax; int
0x180095194  mov     r9d, r15d; char *
0x180095197  lea     r8, aOnecoreBaseApp_59; "onecore\\base\\appmodel\\execmodel\\des"...
0x18009519e  mov     edx, 0DCh; void *
0x1800951a3  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800951a8  nop
0x1800951a9  lea     rcx, [rsp+4B8h+var_308]; this
0x1800951b1  call    ??1ActivationProperties@@QEAA@XZ; ActivationProperties::~ActivationProperties(void)
0x1800951b6  nop
0x1800951b7  lea     rcx, [rsp+4B8h+var_178]; this
0x1800951bf  call    ??1TryActivateDesktopAppXApplication@DesktopAppXProvider@@QEAA@XZ; DesktopAppXProvider::TryActivateDesktopAppXApplication::~TryActivateDesktopAppXApplication(void)
0x1800951c4  mov     eax, r15d
0x1800951c7  jmp     loc_180095B0D
0x1800951cc  lea     r9, [rsp+4B8h+var_3F0]; struct AppDeploymentInfo *
0x1800951d4  mov     r8, r13; struct DESKTOP_APPX_ACTIVATION_RESULT *
0x1800951d7  lea     rdx, [rsp+4B8h+var_308]; struct ActivationProperties *
0x1800951df  lea     rcx, [rsp+4B8h+var_3D8]; struct DESKTOP_APPX_ACTIVATION_PARAMS *
0x1800951e7  call    ?EvaluateApplicationLaunch@@YAJPEBUDESKTOP_APPX_ACTIVATION_PARAMS@@AEAUActivationProperties@@PEAUDESKTOP_APPX_ACTIVATION_RESULT@@PEAUAppDeploymentInfo@@@Z; EvaluateApplicationLaunch(DESKTOP_APPX_ACTIVATION_PARAMS const *,ActivationProperties &,DESKTOP_APPX_ACTIVATION_RESULT *,AppDeploymentInfo *)
0x1800951ec  mov     r15d, eax
0x1800951ef  test    eax, eax
0x1800951f1  jns     loc_18009528C
0x1800951f7  mov     rcx, [rsp+4B8h]; this
0x1800951ff  mov     [rsp+4B8h+var_490], rbx; char *
0x180095204  lea     rax, aStillFailedAft; "Still failed after successfully repairi"...
0x18009520b  mov     [rsp+4B8h+var_498], rax; int
0x180095210  mov     r9d, r15d; char *
0x180095213  lea     r8, aOnecoreBaseApp_59; "onecore\\base\\appmodel\\execmodel\\des"...
0x18009521a  mov     edx, 0E0h; void *
0x18009521f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180095224  nop
0x180095225  lea     rcx, [rsp+4B8h+var_308]; this
0x18009522d  call    ??1ActivationProperties@@QEAA@XZ; ActivationProperties::~ActivationProperties(void)
0x180095232  nop
0x180095233  lea     rcx, [rsp+4B8h+var_178]; this
0x18009523b  call    ??1TryActivateDesktopAppXApplication@DesktopAppXProvider@@QEAA@XZ; DesktopAppXProvider::TryActivateDesktopAppXApplication::~TryActivateDesktopAppXApplication(void)
0x180095240  mov     eax, r15d
0x180095243  jmp     loc_180095B0D
0x180095248  mov     rcx, [rsp+4B8h]; this
0x180095250  mov     r9d, ebx; char *
0x180095253  lea     r8, aOnecoreBaseApp_59; "onecore\\base\\appmodel\\execmodel\\des"...
0x18009525a  mov     edx, 0E5h; void *
0x18009525f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180095264  nop
0x180095265  lea     rcx, [rsp+4B8h+var_308]; this
0x18009526d  call    ??1ActivationProperties@@QEAA@XZ; ActivationProperties::~ActivationProperties(void)
0x180095272  nop
0x180095273  lea     rcx, [rsp+4B8h+var_178]; this
0x18009527b  call    ??1TryActivateDesktopAppXApplication@DesktopAppXProvider@@QEAA@XZ; DesktopAppXProvider::TryActivateDesktopAppXApplication::~TryActivateDesktopAppXApplication(void)
0x180095280  mov     eax, ebx
0x180095282  jmp     loc_180095B0D
0x180095287  mov     edi, 80270254h
0x18009528c  mov     ebx, [r13+0]
0x180095290  mov     r11, qword ptr [rsp+4B8h+var_3B8+8]
0x180095298  cmp     ebx, 1
0x18009529b  jz      loc_1800959EE
0x1800952a1  bt      r11d, 0Eh
0x1800952a6  jnb     short loc_1800952BA
0x1800952a8  mov     r10d, [rsp+4B8h+var_1E0]
0x1800952b0  cmp     r10d, 2
0x1800952b4  jnz     loc_1800959F6
0x1800952ba  xor     r9d, r9d; bool
0x1800952bd  mov     r8, r13; struct DESKTOP_APPX_ACTIVATION_RESULT *
0x1800952c0  lea     rdx, [rsp+4B8h+var_308]; struct ActivationProperties *
0x1800952c8  lea     rcx, [rsp+4B8h+var_3D8]; struct DESKTOP_APPX_ACTIVATION_PARAMS *
0x1800952d0  call    ?InternalTryActivateDesktopAppXApplication@@YAJPEBUDESKTOP_APPX_ACTIVATION_PARAMS@@AEAUActivationProperties@@PEAUDESKTOP_APPX_ACTIVATION_RESULT@@_N@Z; InternalTryActivateDesktopAppXApplication(DESKTOP_APPX_ACTIVATION_PARAMS const *,ActivationProperties &,DESKTOP_APPX_ACTIVATION_RESULT *,bool)
0x1800952d5  mov     r15d, eax
0x1800952d8  mov     rcx, [rsp+4B8h]; this
0x1800952e0  test    eax, eax
0x1800952e2  jns     loc_1800958C9
0x1800952e8  mov     r9d, eax; char *
0x1800952eb  lea     r8, aOnecoreBaseApp_59; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800952f2  mov     edx, 0FCh; void *
0x1800952f7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800952fc  cmp     r15d, 800704C7h
0x180095303  jz      loc_1800958C9
0x180095309  cmp     r15d, 80073D1Eh
0x180095310  jz      loc_1800958C9
0x180095316  movdqa  xmm0, cs:__xmm@87e10bd0c0ea0001800704cfc03f6603
0x18009531e  movdqa  [rsp+4B8h+var_388], xmm0
0x180095327  movdqa  xmm1, cs:__xmm@803f8067803f9008803f8008803f700f
0x18009532f  movdqa  [rsp+4B8h+var_378], xmm1
0x180095338  movdqa  xmm0, cs:__xmm@803f8001803f81f5803f800787e107d7
0x180095340  movdqa  [rsp+4B8h+var_368], xmm0
0x180095349  movdqa  xmm1, cs:__xmm@803f9009803f800e803f800b803f9007
0x180095351  movdqa  [rsp+4B8h+var_358], xmm1
0x18009535a  movdqa  xmm0, cs:__xmm@80072ee780072f8f80072efe80072efd
0x180095362  movdqa  [rsp+4B8h+var_348], xmm0
0x18009536b  mov     [rsp+4B8h+var_338], 80072EE2h
0x180095376  lea     rax, [rsp+4B8h+var_388]
0x18009537e  mov     [rsp+4B8h+var_408], r15d
0x180095386  cmp     r15d, [rax]
0x180095389  jz      loc_180095482
0x18009538f  add     rax, 4
0x180095393  lea     rcx, [rsp+4B8h+var_334]
0x18009539b  cmp     rax, rcx
0x18009539e  jnz     short loc_180095386
0x1800953a0  cmp     r15d, edi
0x1800953a3  jz      short loc_1800953AE
0x1800953a5  cmp     r15d, 80073D55h
0x1800953ac  jnz     short loc_1800953B3
0x1800953ae  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "hr != E_APPLICATION_NOT_REGISTERED && hr != HRESULT_FROM_WIN32(APPMODEL_ERROR_PACKAGE_RUNTIME_CORRUPT)")
0x1800953b3  mov     dword ptr [rsp+4B8h+var_410], esi
0x1800953ba  lea     rcx, [rsp+4B8h+var_288]
0x1800953c2  cmp     [rsp+4B8h+var_270], 7
0x1800953cb  cmova   rcx, [rsp+4B8h+var_288]; unsigned __int16 *
0x1800953d4  lea     rdx, [rsp+4B8h+var_410]; int *
0x1800953dc  call    ?RepairPackage@@YAJPEBGPEAJ@Z; RepairPackage(ushort const *,long *)
0x1800953e1  test    eax, eax
0x1800953e3  js      short loc_18009542D
0x1800953e5  mov     r9b, 1; bool
0x1800953e8  mov     r8, r13; struct DESKTOP_APPX_ACTIVATION_RESULT *
0x1800953eb  lea     rdx, [rsp+4B8h+var_308]; struct ActivationProperties *
0x1800953f3  lea     rcx, [rsp+4B8h+var_3D8]; struct DESKTOP_APPX_ACTIVATION_PARAMS *
0x1800953fb  call    ?InternalTryActivateDesktopAppXApplication@@YAJPEBUDESKTOP_APPX_ACTIVATION_PARAMS@@AEAUActivationProperties@@PEAUDESKTOP_APPX_ACTIVATION_RESULT@@_N@Z; InternalTryActivateDesktopAppXApplication(DESKTOP_APPX_ACTIVATION_PARAMS const *,ActivationProperties &,DESKTOP_APPX_ACTIVATION_RESULT *,bool)
0x180095400  mov     r15d, eax
0x180095403  mov     rcx, [rsp+4B8h]; this
  ... truncated ...
```
