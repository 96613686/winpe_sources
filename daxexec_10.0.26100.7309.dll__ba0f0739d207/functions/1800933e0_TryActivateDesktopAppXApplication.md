# TryActivateDesktopAppXApplication

- ea: `0x1800933e0`
- end: `0x180094165`
- name: `TryActivateDesktopAppXApplication`
- size: `3461`
- prototype: ``
- caller_count: `0`
- callee_count: `22`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800053a0`
- `0x180006158`
- `0x18000e234`
- `0x180011300`
- `0x180038318`
- `0x18003ddd0`
- `0x18003e244`
- `0x18003fa14`
- `0x180091bb4`
- `0x180092224`
- `0x180092364`
- `0x18009240c`
- `0x180092534`
- `0x1800928f0`
- `0x18009292c`
- `0x180092a88`
- `0x1800933e0`
- `0x180097688`
- `0x1800af978`
- `0x1800b3374`
- `0x1800bbfc0`
- `0x1800cc010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180093b31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180093b31`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180093b81`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180093b81`

## string_xrefs

- `0x180093549`: `onecore\base\appmodel\execmodel\desktopappx\desktoplib\desktopaamextensions.cpp`
- `0x180093585`: `onecore\base\appmodel\execmodel\desktopappx\desktoplib\desktopaamextensions.cpp`
- `0x1800935c1`: `onecore\base\appmodel\execmodel\desktopappx\desktoplib\desktopaamextensions.cpp`
- `0x1800935fd`: `onecore\base\appmodel\execmodel\desktopappx\desktoplib\desktopaamextensions.cpp`
- `0x180093639`: `onecore\base\appmodel\execmodel\desktopappx\desktoplib\desktopaamextensions.cpp`
- `0x1800936b2`: `onecore\base\appmodel\execmodel\desktopappx\desktoplib\desktopaamextensions.cpp`
- `0x1800936ef`: `onecore\base\appmodel\execmodel\desktopappx\desktoplib\desktopaamextensions.cpp`
- `0x180093759`: `onecore\base\appmodel\execmodel\desktopappx\desktoplib\desktopaamextensions.cpp`
- `0x1800937af`: `onecore\base\appmodel\execmodel\desktopappx\desktoplib\desktopaamextensions.cpp`
- `0x18009382b`: `onecore\base\appmodel\execmodel\desktopappx\desktoplib\desktopaamextensions.cpp`
- `0x18009386b`: `onecore\base\appmodel\execmodel\desktopappx\desktoplib\desktopaamextensions.cpp`
- `0x180093902`: `onecore\base\appmodel\execmodel\desktopappx\desktoplib\desktopaamextensions.cpp`
- `0x180093a26`: `onecore\base\appmodel\execmodel\desktopappx\desktoplib\desktopaamextensions.cpp`
- `0x180093a58`: `onecore\base\appmodel\execmodel\desktopappx\desktoplib\desktopaamextensions.cpp`
- `0x180093a85`: `onecore\base\appmodel\execmodel\desktopappx\desktoplib\desktopaamextensions.cpp`
- `0x180093b9e`: `onecore\base\appmodel\execmodel\desktopappx\desktoplib\desktopaamextensions.cpp`
- `0x180093c90`: `onecore\base\appmodel\execmodel\desktopappx\desktoplib\desktopaamextensions.cpp`
- `0x180093d62`: `onecore\base\appmodel\execmodel\desktopappx\desktoplib\desktopaamextensions.cpp`
- `0x18009374a`: `Try to repair package %ws`
- `0x180093a49`: `The attempt to repair the app failed after an unsuccessful launch.`
- `0x1800937a0`: `Failed to repair package %ws. Extended error code: 0x%x`
- `0x18009381c`: `Still failed after successfully repairing the package %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=11 #try_helpers=1
__int64 __fastcall TryActivateDesktopAppXApplication(__int64 a1, struct DESKTOP_APPX_ACTIVATION_RESULT *a2)
{
  struct DESKTOP_APPX_ACTIVATION_RESULT *v2; // r13
  __int64 v4; // rax
  int v6; // eax
  unsigned int v7; // ebx
  const char *v8; // rbx
  int v9; // r15d
  int v10; // r15d
  unsigned int v11; // r10d
  int v12; // eax
  int v13; // ebx
  int v14; // r15d
  char *v15; // rax
  char **v16; // rcx
  int v17; // eax
  int v18; // eax
  char **v19; // rdx
  __int64 v20; // r8
  HRESULT v21; // eax
  int v22; // edx
  unsigned int v23; // r8d
  HSTRING v24; // rbx
  char *v25; // rcx
  int ActivationFactory; // eax
  unsigned int v27; // ebx
  char *v28; // rcx
  char *v29; // rbx
  __int64 (__fastcall *v30)(char *, _QWORD, __int64 *); // rdi
  char **v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  __int64 v34; // rcx
  char *v35; // rcx
  int v36; // eax
  unsigned int v37; // ebx
  __int64 v38; // rcx
  char *v39; // rcx
  struct PackageInformation *v40; // rcx
  const unsigned __int16 *v41; // r8
  struct IInspectable *v42; // rax
  const char *v43; // r9
  __int64 v44; // rdx
  char *v45; // rdx
  const unsigned __int16 *v46; // rbx
  const unsigned __int16 *v47; // r11
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
  unsigned __int16 *v70[2]; // [rsp+F0h] [rbp-3C8h]
  unsigned int v71[4]; // [rsp+100h] [rbp-3B8h]
  __int64 v72; // [rsp+110h] [rbp-3A8h]
  __int64 v73; // [rsp+118h] [rbp-3A0h]
  struct DESKTOP_APPX_ACTIVATION_RESULT *v74; // [rsp+120h] [rbp-398h]
  HSTRING_HEADER hstringHeader; // [rsp+128h] [rbp-390h] BYREF
  HSTRING string; // [rsp+140h] [rbp-378h] BYREF
  unsigned __int16 *v77[3]; // [rsp+150h] [rbp-368h] BYREF
  unsigned __int64 v78; // [rsp+168h] [rbp-350h]
  char *v79[3]; // [rsp+1D0h] [rbp-2E8h] BYREF
  unsigned __int64 v80; // [rsp+1E8h] [rbp-2D0h]
  unsigned __int16 *v81[3]; // [rsp+1F0h] [rbp-2C8h] BYREF
  unsigned __int64 v82; // [rsp+208h] [rbp-2B0h]
  unsigned __int16 *v83[3]; // [rsp+250h] [rbp-268h] BYREF
  unsigned __int64 v84; // [rsp+268h] [rbp-250h]
  unsigned int v85; // [rsp+270h] [rbp-248h]
  unsigned int v86; // [rsp+274h] [rbp-244h]
  unsigned int v87; // [rsp+278h] [rbp-240h]
  unsigned int v88; // [rsp+27Ch] [rbp-23Ch]
  bool v89; // [rsp+281h] [rbp-237h]
  void **v90; // [rsp+2E0h] [rbp-1D8h] BYREF
  int v91; // [rsp+2E8h] [rbp-1D0h] BYREF
  char v92; // [rsp+2ECh] [rbp-1CCh]
  int v93; // [rsp+310h] [rbp-1A8h] BYREF
  const char *v94; // [rsp+318h] [rbp-1A0h]
  __int64 v95; // [rsp+320h] [rbp-198h]
  char v96; // [rsp+328h] [rbp-190h]
  int v97; // [rsp+330h] [rbp-188h]
  _BYTE v98[168]; // [rsp+338h] [rbp-180h] BYREF
  int v99; // [rsp+3E0h] [rbp-D8h]
  __int64 v100; // [rsp+3E8h] [rbp-D0h]
  int *v101; // [rsp+3F0h] [rbp-C8h]
  __int64 v102; // [rsp+3F8h] [rbp-C0h]
  __int64 v103; // [rsp+400h] [rbp-B8h]
  void ***v104; // [rsp+408h] [rbp-B0h]
  __int64 v105; // [rsp+410h] [rbp-A8h]
  int v106; // [rsp+418h] [rbp-A0h]
  int *v107; // [rsp+420h] [rbp-98h]
  _OWORD v108[5]; // [rsp+430h] [rbp-88h] BYREF
  int v109; // [rsp+480h] [rbp-38h]
  char v110; // [rsp+484h] [rbp-34h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4B8h] [rbp+0h]

  v2 = a2;
  v74 = a2;
  v91 = 0;
  v92 = 0;
  v96 = 0;
  v93 = 0;
  v94 = "TryActivateDesktopAppXApplication";
  v95 = 0;
  v97 = 0;
  *(_OWORD *)&v98[152] = 0;
  memset_0(v98, 0, 0x98u);
  v99 = 1;
  v100 = 0;
  v101 = &v91;
  v102 = 0;
  v103 = 0;
  v104 = &v90;
  v105 = 0;
  v106 = 0;
  v107 = &v93;
  v90 = &DesktopAppXProvider::TryActivateDesktopAppXApplication::`vftable';
  DesktopAppXProvider::TryActivateDesktopAppXApplication::StartActivity(
    (DesktopAppXProvider::TryActivateDesktopAppXApplication *)&v90,
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
    DesktopAppXProvider::TryActivateDesktopAppXApplication::~TryActivateDesktopAppXApplication((DesktopAppXProvider::TryActivateDesktopAppXApplication *)&v90);
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
    DesktopAppXProvider::TryActivateDesktopAppXApplication::~TryActivateDesktopAppXApplication((DesktopAppXProvider::TryActivateDesktopAppXApplication *)&v90);
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
    DesktopAppXProvider::TryActivateDesktopAppXApplication::~TryActivateDesktopAppXApplication((DesktopAppXProvider::TryActivateDesktopAppXApplication *)&v90);
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
    DesktopAppXProvider::TryActivateDesktopAppXApplication::~TryActivateDesktopAppXApplication((DesktopAppXProvider::TryActivateDesktopAppXApplication *)&v90);
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
    DesktopAppXProvider::TryActivateDesktopAppXApplication::~TryActivateDesktopAppXApplication((DesktopAppXProvider::TryActivateDesktopAppXApplication *)&v90);
    return 2147942487LL;
  }
  ActivationProperties::ActivationProperties((ActivationProperties *)v77);
  *(_QWORD *)v66 = 0;
  *(_QWORD *)v67 = 0;
  v6 = EvaluateApplicationLaunch(
         (const struct DESKTOP_APPX_ACTIVATION_PARAMS *)v69,
         (struct ActivationProperties *)v77,
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
      ActivationProperties::~ActivationProperties((ActivationProperties *)v77);
      DesktopAppXProvider::TryActivateDesktopAppXApplication::~TryActivateDesktopAppXApplication((DesktopAppXProvider::TryActivateDesktopAppXApplication *)&v90);
      return v7;
    }
    MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( !v79[2] )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD5,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\desktoplib\\desktopaamextensions.cpp",
        (const char *)0x80270254LL,
        v55);
      ActivationProperties::~ActivationProperties((ActivationProperties *)v77);
      DesktopAppXProvider::TryActivateDesktopAppXApplication::~TryActivateDesktopAppXApplication((DesktopAppXProvider::TryActivateDesktopAppXApplication *)&v90);
      return 2150040148LL;
    }
    v8 = (const char *)v79;
    if ( v80 > 7 )
      v8 = v79[0];
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0xD9,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\desktoplib\\desktopaamextensions.cpp",
      (const char *)0x80270254LL,
      (int)"Try to repair package %ws",
      v8);
    LODWORD(v62) = 0;
    v9 = RepairPackage((const unsigned __int16 *)v8, (int *)&v62);
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xDC,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\desktoplib\\desktopaamextensions.cpp",
        (const char *)(unsigned int)v9,
        (int)"Failed to repair package %ws. Extended error code: 0x%x",
        v8,
        (_DWORD)v62);
      ActivationProperties::~ActivationProperties((ActivationProperties *)v77);
      DesktopAppXProvider::TryActivateDesktopAppXApplication::~TryActivateDesktopAppXApplication((DesktopAppXProvider::TryActivateDesktopAppXApplication *)&v90);
      return (unsigned int)v9;
    }
    v10 = EvaluateApplicationLaunch(
            (const struct DESKTOP_APPX_ACTIVATION_PARAMS *)v69,
            (struct ActivationProperties *)v77,
            v2,
            (struct AppDeploymentInfo *)v66);
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xE0,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\desktoplib\\desktopaamextensions.cpp",
        (const char *)(unsigned int)v10,
        (int)"Still failed after successfully repairing the package %ws",
        v8);
      ActivationProperties::~ActivationProperties((ActivationProperties *)v77);
      DesktopAppXProvider::TryActivateDesktopAppXApplication::~TryActivateDesktopAppXApplication((DesktopAppXProvider::TryActivateDesktopAppXApplication *)&v90);
      return (unsigned int)v10;
    }
  }
  if ( *(_DWORD *)v2 == 1 )
  {
    v11 = v87;
LABEL_96:
    v50 = (const unsigned __int16 *)v83;
    if ( v84 > 7 )
      v50 = v83[0];
    v51 = (const unsigned __int16 *)v77;
    if ( v78 > 7 )
      v51 = v77[0];
    v52 = (const unsigned __int16 *)v81;
    if ( v82 > 7 )
      v52 = v81[0];
    v53 = v79;
    if ( v80 > 7 )
      v53 = (char **)v79[0];
    DesktopAppXProvider::TryActivateDesktopAppXApplication::Stop(
      (DesktopAppXProvider::TryActivateDesktopAppXApplication *)&v90,
      v69[0],
      (const unsigned __int16 *)v53,
      v52,
      v51,
      v50,
      v85,
      v86,
      v88,
      v89,
      v11,
      v71[2],
      *(_DWORD *)v2,
      v66[0],
      v66[1],
      v67[0],
      v67[1],
      v59,
      v60);
    ActivationProperties::~ActivationProperties((ActivationProperties *)v77);
    DesktopAppXProvider::TryActivateDesktopAppXApplication::~TryActivateDesktopAppXApplication((DesktopAppXProvider::TryActivateDesktopAppXApplication *)&v90);
    return 0;
  }
  if ( (v71[2] & 0x4000) != 0 )
  {
    v11 = v87;
    if ( v87 != 2 )
      goto LABEL_96;
  }
  v12 = InternalTryActivateDesktopAppXApplication(
          (const struct DESKTOP_APPX_ACTIVATION_PARAMS *)v69,
          (struct ActivationProperties *)v77,
          v2,
          0);
  v13 = v12;
  if ( v12 >= 0 )
  {
    v14 = v12;
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xFC,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\desktoplib\\desktopaamextensions.cpp",
      (const char *)(unsigned int)v12,
      v54);
    v14 = v13;
    if ( v13 != -2147023673 && v13 != -2147009250 )
    {
      v108[0] = _mm_load_si128((const __m128i *)&_xmm);
      v108[1] = _mm_load_si128((const __m128i *)&_xmm);
      v108[2] = _mm_load_si128((const __m128i *)&_xmm);
      v108[3] = _mm_load_si128((const __m128i *)&_xmm);
      v108[4] = _mm_load_si128((const __m128i *)&_xmm);
      v109 = -2147012894;
      v15 = (char *)v108;
      v63 = v13;
      while ( v13 != *(_DWORD *)v15 )
      {
        v15 += 4;
        if ( v15 == &v110 )
        {
          if ( v13 == -2144927148 || v13 == -2147009195 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
          LODWORD(v62) = 0;
          v16 = v79;
          if ( v80 > 7 )
            v16 = (char **)v79[0];
          v17 = RepairPackage((const unsigned __int16 *)v16, (int *)&v62);
          if ( v17 < 0 )
          {
            wil::details::in1diag3::Log_HrMsg(
              retaddr,
              (void *)0x110,
              (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\desktoplib\\desktopaamextensions.cpp",
              (const char *)(unsigned int)v17,
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
            v18 = InternalTryActivateDesktopAppXApplication(
                    (const struct DESKTOP_APPX_ACTIVATION_PARAMS *)v69,
                    (struct ActivationProperties *)v77,
                    v2,
                    1);
            v14 = v18;
            if ( v18 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x117,
                (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\desktoplib\\desktopaamextensions.cpp",
                (const char *)(unsigned int)v18,
                v56);
            v63 = v14;
          }
          break;
        }
      }
      if ( v14 < 0 )
      {
        v19 = v79;
        if ( v80 > 7 )
          v19 = (char **)v79[0];
        memset(&hstringHeader, 0, sizeof(hstringHeader));
        string = 0;
        v20 = -1;
        do
          ++v20;
        while ( *((_WORD *)v19 + v20) );
        std::wstring::_Construct<1,unsigned short const *>(&hstringHeader, v19, v20);
        CreatePackageInformation(&v65, &hstringHeader);
        v62 = 0;
        string = 0;
        v21 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.Package", 0x28u, &hstringHeader, &string);
        if ( v21 < 0 )
        {
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v21, v22, v23);
          JUMPOUT(0x180094163LL);
        }
        v24 = string;
        v25 = v62;
        if ( v62 )
        {
          v62 = 0;
          (*(void (__fastcall **)(char *))(*(_QWORD *)v25 + 16LL))(v25);
        }
        ActivationFactory = RoGetActivationFactory(v24, &GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419, &v62);
        v27 = ActivationFactory;
        if ( ActivationFactory < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x126,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\desktoplib\\desktopaamextensions.cpp",
            (const char *)(unsigned int)ActivationFactory,
            v56);
          v28 = v62;
          if ( v62 )
          {
            v62 = 0;
            (*(void (__fastcall **)(char *))(*(_QWORD *)v28 + 16LL))(v28);
          }
          if ( v65 )
            (**(void (__fastcall ***)(struct PackageInformation *, __int64))v65)(v65, 1);
LABEL_54:
          ActivationProperties::~ActivationProperties((ActivationProperties *)v77);
          DesktopAppXProvider::TryActivateDesktopAppXApplication::~TryActivateDesktopAppXApplication((DesktopAppXProvider::TryActivateDesktopAppXApplication *)&v90);
          return v27;
        }
        v64 = 0;
        v29 = v62;
        v30 = *(__int64 (__fastcall **)(char *, _QWORD, __int64 *))(*(_QWORD *)v62 + 176LL);
        v31 = v79;
        if ( v80 > 7 )
          v31 = (char **)v79[0];
        v68 = v31;
        v32 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v68);
        v33 = v30(v29, *(_QWORD *)(v32 + 24), &v64);
        v27 = v33;
        if ( v33 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x128,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\desktoplib\\desktopaamextensions.cpp",
            (const char *)(unsigned int)v33,
            v56);
          v34 = v64;
          if ( v64 )
          {
            v64 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
          }
          v35 = v62;
          if ( v62 )
          {
            v62 = 0;
            (*(void (__fastcall **)(char *))(*(_QWORD *)v35 + 16LL))(v35);
          }
          if ( v65 )
            (**(void (__fastcall ***)(struct PackageInformation *, __int64))v65)(v65, 1);
          goto LABEL_54;
        }
        v61[0] = 0;
        v36 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v64 + 320LL))(v64, v61);
        v37 = v36;
        if ( v36 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x12A,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\desktoplib\\desktopaamextensions.cpp",
            (const char *)(unsigned int)v36,
            v56);
          v38 = v64;
          if ( v64 )
          {
            v64 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
          }
          v39 = v62;
          if ( v62 )
          {
            v62 = 0;
            (*(void (__fastcall **)(char *))(*(_QWORD *)v39 + 16LL))(v39);
          }
          if ( v65 )
            (**(void (__fastcall ***)(struct PackageInformation *, __int64))v65)(v65, 1);
          ActivationProperties::~ActivationProperties((ActivationProperties *)v77);
          DesktopAppXProvider::TryActivateDesktopAppXApplication::~TryActivateDesktopAppXApplication((DesktopAppXProvider::TryActivateDesktopAppXApplication *)&v90);
          return v37;
        }
        v40 = v65;
        if ( v65 && (v61[0] || *(_QWORD *)v71) )
        {
          v41 = 0;
          v42 = 0;
          if ( LODWORD(v69[1]) == 1 )
          {
            v41 = v70[0];
            v42 = (struct IInspectable *)v70[1];
          }
          try
          {
            CreateAndLaunchAppActivationErrorHandler(v65, v69[0], v41, (v71[2] & 1) << 29, v42, v14);
          }
          catch ( ... )
          {
            wil::details::in1diag3::Log_CaughtException(
              retaddr,
              (void *)0x140,
              (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\desktoplib\\desktopaamextensions.cpp",
              v43);
            v14 = v63;
            v2 = v74;
          }
          v40 = v65;
        }
        v44 = v64;
        if ( v64 )
        {
          v64 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
          v40 = v65;
        }
        v45 = v62;
        if ( v62 )
        {
          v62 = 0;
          (*(void (__fastcall **)(char *))(*(_QWORD *)v45 + 16LL))(v45);
          v40 = v65;
        }
        if ( v40 )
          (**(void (__fastcall ***)(struct PackageInformation *, __int64))v40)(v40, 1);
      }
    }
  }
  v46 = (const unsigned __int16 *)v83;
  if ( v84 > 7 )
    v46 = v83[0];
  v47 = (const unsigned __int16 *)v77;
  if ( v78 > 7 )
    v47 = v77[0];
  v48 = (const unsigned __int16 *)v81;
  if ( v82 > 7 )
    v48 = v81[0];
  v49 = v79;
  if ( v80 > 7 )
    v49 = (char **)v79[0];
  DesktopAppXProvider::TryActivateDesktopAppXApplication::Stop(
    (DesktopAppXProvider::TryActivateDesktopAppXApplication *)&v90,
    v69[0],
    (const unsigned __int16 *)v49,
    v48,
    v47,
    v46,
    v85,
    v86,
    v89,
    v87 != 0,
    v71[2],
    *(_DWORD *)v2,
    v66[0],
    v66[1],
    v67[0],
    v67[1],
    v14,
    v59,
    v60);
  ActivationProperties::~ActivationProperties((ActivationProperties *)v77);
  DesktopAppXProvider::TryActivateDesktopAppXApplication::~TryActivateDesktopAppXApplication((DesktopAppXProvider::TryActivateDesktopAppXApplication *)&v90);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800933e0  mov     r11, rsp
0x1800933e3  mov     [r11+18h], rbx
0x1800933e7  mov     [r11+20h], rsi
0x1800933eb  push    rdi
0x1800933ec  push    r13
0x1800933ee  push    r15
0x1800933f0  sub     rsp, 4A0h
0x1800933f7  mov     rax, cs:__security_cookie
0x1800933fe  xor     rax, rsp
0x180093401  mov     [rsp+4B8h+var_28], rax
0x180093409  mov     r13, rdx
0x18009340c  mov     rbx, rcx
0x18009340f  mov     [rsp+4B8h+var_398], rdx
0x180093417  xor     esi, esi
0x180093419  mov     [rsp+4B8h+var_1D0], esi
0x180093420  mov     [rsp+4B8h+var_1CC], sil
0x180093428  mov     [rsp+4B8h+var_190], sil
0x180093430  mov     [rsp+4B8h+var_1A8], esi
0x180093437  lea     rax, aTryactivatedes_0; "TryActivateDesktopAppXApplication"
0x18009343e  mov     [r11-1A0h], rax
0x180093445  mov     [r11-198h], rsi
0x18009344c  mov     [rsp+4B8h+var_188], esi
0x180093453  xorps   xmm0, xmm0
0x180093456  movdqa  [rsp+4B8h+var_E8], xmm0
0x18009345f  xor     edx, edx; Val
0x180093461  mov     r8d, 98h; Size
0x180093467  lea     rcx, [r11-180h]; void *
0x18009346e  call    memset_0
0x180093473  mov     [rsp+4B8h+var_D8], 1
0x18009347e  xor     eax, eax
0x180093480  mov     [rsp+4B8h+var_D0], rax
0x180093488  lea     rax, [rsp+4B8h+var_1D0]
0x180093490  mov     [rsp+4B8h+var_C8], rax
0x180093498  mov     [rsp+4B8h+var_C0], rsi
0x1800934a0  mov     [rsp+4B8h+var_B8], rsi
0x1800934a8  lea     rax, [rsp+4B8h+var_1D8]
0x1800934b0  mov     [rsp+4B8h+var_B0], rax
0x1800934b8  mov     [rsp+4B8h+var_A8], rsi
0x1800934c0  mov     [rsp+4B8h+var_A0], esi
0x1800934c7  lea     rax, [rsp+4B8h+var_1A8]
0x1800934cf  mov     [rsp+4B8h+var_98], rax
0x1800934d7  lea     rax, ??_7TryActivateDesktopAppXApplication@DesktopAppXProvider@@6B@; const DesktopAppXProvider::TryActivateDesktopAppXApplication::`vftable'
0x1800934de  mov     [rsp+4B8h+var_1D8], rax
0x1800934e6  mov     rdx, [rbx]; unsigned __int16 *
0x1800934e9  lea     rcx, [rsp+4B8h+var_1D8]; this
0x1800934f1  call    ?StartActivity@TryActivateDesktopAppXApplication@DesktopAppXProvider@@QEAAXPEBG@Z; DesktopAppXProvider::TryActivateDesktopAppXApplication::StartActivity(ushort const *)
0x1800934f6  nop
0x1800934f7  movups  xmm0, xmmword ptr [rbx]
0x1800934fa  movaps  xmmword ptr [rsp+4B8h+var_3D8], xmm0
0x180093502  movups  xmm1, xmmword ptr [rbx+10h]
0x180093506  movaps  xmmword ptr [rsp+4B8h+var_3C8], xmm1
0x18009350e  movups  xmm2, xmmword ptr [rbx+20h]
0x180093512  movaps  xmmword ptr [rsp+4B8h+var_3B8], xmm2
0x18009351a  movups  xmm0, xmmword ptr [rbx+30h]
0x18009351e  movaps  [rsp+4B8h+var_3A8], xmm0
0x180093526  mov     qword ptr [rsp+4B8h+var_3A8], rsi
0x18009352e  mov     rax, [rbx+28h]
0x180093532  test    eax, 4E0h
0x180093537  jz      short loc_18009356F
0x180093539  mov     rcx, [rsp+4B8h]; this
0x180093541  mov     ebx, 80070057h
0x180093546  mov     r9d, ebx; char *
0x180093549  lea     r8, aOnecoreBaseApp_58; "onecore\\base\\appmodel\\execmodel\\des"...
0x180093550  mov     edx, 0BCh; void *
0x180093555  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009355a  nop
0x18009355b  lea     rcx, [rsp+4B8h+var_1D8]; this
0x180093563  call    ??1TryActivateDesktopAppXApplication@DesktopAppXProvider@@QEAA@XZ; DesktopAppXProvider::TryActivateDesktopAppXApplication::~TryActivateDesktopAppXApplication(void)
0x180093568  mov     eax, ebx
0x18009356a  jmp     loc_180094132
0x18009356f  bt      eax, 8
0x180093573  jnb     short loc_1800935AB
0x180093575  mov     rcx, [rsp+4B8h]; this
0x18009357d  mov     ebx, 80070057h
0x180093582  mov     r9d, ebx; char *
0x180093585  lea     r8, aOnecoreBaseApp_58; "onecore\\base\\appmodel\\execmodel\\des"...
0x18009358c  mov     edx, 0BDh; void *
0x180093591  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180093596  nop
0x180093597  lea     rcx, [rsp+4B8h+var_1D8]; this
0x18009359f  call    ??1TryActivateDesktopAppXApplication@DesktopAppXProvider@@QEAA@XZ; DesktopAppXProvider::TryActivateDesktopAppXApplication::~TryActivateDesktopAppXApplication(void)
0x1800935a4  mov     eax, ebx
0x1800935a6  jmp     loc_180094132
0x1800935ab  bt      eax, 0Bh
0x1800935af  jnb     short loc_1800935E7
0x1800935b1  mov     rcx, [rsp+4B8h]; this
0x1800935b9  mov     ebx, 80070057h
0x1800935be  mov     r9d, ebx; char *
0x1800935c1  lea     r8, aOnecoreBaseApp_58; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800935c8  mov     edx, 0BEh; void *
0x1800935cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800935d2  nop
0x1800935d3  lea     rcx, [rsp+4B8h+var_1D8]; this
0x1800935db  call    ??1TryActivateDesktopAppXApplication@DesktopAppXProvider@@QEAA@XZ; DesktopAppXProvider::TryActivateDesktopAppXApplication::~TryActivateDesktopAppXApplication(void)
0x1800935e0  mov     eax, ebx
0x1800935e2  jmp     loc_180094132
0x1800935e7  bt      eax, 0Ch
0x1800935eb  jnb     short loc_180093623
0x1800935ed  mov     rcx, [rsp+4B8h]; this
0x1800935f5  mov     ebx, 80070057h
0x1800935fa  mov     r9d, ebx; char *
0x1800935fd  lea     r8, aOnecoreBaseApp_58; "onecore\\base\\appmodel\\execmodel\\des"...
0x180093604  mov     edx, 0BFh; void *
0x180093609  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009360e  nop
0x18009360f  lea     rcx, [rsp+4B8h+var_1D8]; this
0x180093617  call    ??1TryActivateDesktopAppXApplication@DesktopAppXProvider@@QEAA@XZ; DesktopAppXProvider::TryActivateDesktopAppXApplication::~TryActivateDesktopAppXApplication(void)
0x18009361c  mov     eax, ebx
0x18009361e  jmp     loc_180094132
0x180093623  bt      eax, 0Dh
0x180093627  jnb     short loc_18009365F
0x180093629  mov     rcx, [rsp+4B8h]; this
0x180093631  mov     ebx, 80070057h
0x180093636  mov     r9d, ebx; char *
0x180093639  lea     r8, aOnecoreBaseApp_58; "onecore\\base\\appmodel\\execmodel\\des"...
0x180093640  mov     edx, 0C0h; void *
0x180093645  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009364a  nop
0x18009364b  lea     rcx, [rsp+4B8h+var_1D8]; this
0x180093653  call    ??1TryActivateDesktopAppXApplication@DesktopAppXProvider@@QEAA@XZ; DesktopAppXProvider::TryActivateDesktopAppXApplication::~TryActivateDesktopAppXApplication(void)
0x180093658  mov     eax, ebx
0x18009365a  jmp     loc_180094132
0x18009365f  lea     rcx, [rsp+4B8h+var_368]; this
0x180093667  call    ??0ActivationProperties@@QEAA@XZ; ActivationProperties::ActivationProperties(void)
0x18009366c  nop
0x18009366d  mov     qword ptr [rsp+4B8h+var_3F0], rsi
0x180093675  mov     qword ptr [rsp+4B8h+var_3E8], rsi
0x18009367d  lea     r9, [rsp+4B8h+var_3F0]; struct AppDeploymentInfo *
0x180093685  mov     r8, r13; struct DESKTOP_APPX_ACTIVATION_RESULT *
0x180093688  lea     rdx, [rsp+4B8h+var_368]; struct ActivationProperties *
0x180093690  lea     rcx, [rsp+4B8h+var_3D8]; struct DESKTOP_APPX_ACTIVATION_PARAMS *
0x180093698  call    ?EvaluateApplicationLaunch@@YAJPEBUDESKTOP_APPX_ACTIVATION_PARAMS@@AEAUActivationProperties@@PEAUDESKTOP_APPX_ACTIVATION_RESULT@@PEAUAppDeploymentInfo@@@Z; EvaluateApplicationLaunch(DESKTOP_APPX_ACTIVATION_PARAMS const *,ActivationProperties &,DESKTOP_APPX_ACTIVATION_RESULT *,AppDeploymentInfo *)
0x18009369d  mov     ebx, eax
0x18009369f  mov     rcx, [rsp+4B8h]; this
0x1800936a7  test    eax, eax
0x1800936a9  jns     loc_18009389F
0x1800936af  mov     r9d, eax; char *
0x1800936b2  lea     r8, aOnecoreBaseApp_58; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800936b9  mov     edx, 0C4h; void *
0x1800936be  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800936c3  mov     edi, 80270254h
0x1800936c8  cmp     ebx, edi
0x1800936ca  jnz     loc_180093860
0x1800936d0  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "false", "EvaluateApplicationLaunch failed with E_APPLICATION_NOT_REGISTERED")
0x1800936d5  cmp     [rsp+4B8h+var_2D8], rsi
0x1800936dd  jnz     short loc_180093723
0x1800936df  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "false", "EvaluateApplicationLaunch failed before resolving package full name. No retry.")
0x1800936e4  mov     rcx, [rsp+4B8h]; this
0x1800936ec  mov     r9d, edi; char *
0x1800936ef  lea     r8, aOnecoreBaseApp_58; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800936f6  mov     edx, 0D5h; void *
0x1800936fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180093700  nop
0x180093701  lea     rcx, [rsp+4B8h+var_368]; this
0x180093709  call    ??1ActivationProperties@@QEAA@XZ; ActivationProperties::~ActivationProperties(void)
0x18009370e  nop
0x18009370f  lea     rcx, [rsp+4B8h+var_1D8]; this
0x180093717  call    ??1TryActivateDesktopAppXApplication@DesktopAppXProvider@@QEAA@XZ; DesktopAppXProvider::TryActivateDesktopAppXApplication::~TryActivateDesktopAppXApplication(void)
0x18009371c  mov     eax, edi
0x18009371e  jmp     loc_180094132
0x180093723  lea     rbx, [rsp+4B8h+var_2E8]
0x18009372b  cmp     [rsp+4B8h+var_2D0], 7
0x180093734  cmova   rbx, [rsp+4B8h+var_2E8]
0x18009373d  mov     rcx, [rsp+4B8h]; this
0x180093745  mov     [rsp+4B8h+var_490], rbx; char *
0x18009374a  lea     rax, aTryToRepairPac; "Try to repair package %ws"
0x180093751  mov     [rsp+4B8h+var_498], rax; int
0x180093756  mov     r9d, edi; char *
0x180093759  lea     r8, aOnecoreBaseApp_58; "onecore\\base\\appmodel\\execmodel\\des"...
0x180093760  mov     edx, 0D9h; void *
0x180093765  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18009376a  mov     dword ptr [rsp+4B8h+var_410], esi
0x180093771  lea     rdx, [rsp+4B8h+var_410]; int *
0x180093779  mov     rcx, rbx; unsigned __int16 *
0x18009377c  call    ?RepairPackage@@YAJPEBGPEAJ@Z; RepairPackage(ushort const *,long *)
0x180093781  mov     r15d, eax
0x180093784  test    eax, eax
0x180093786  jns     short loc_1800937E4
0x180093788  mov     rcx, [rsp+4B8h]; this
0x180093790  mov     edx, dword ptr [rsp+4B8h+var_410]
0x180093797  mov     [rsp+4B8h+var_488], edx
0x18009379b  mov     [rsp+4B8h+var_490], rbx; char *
0x1800937a0  lea     rax, aFailedToRepair; "Failed to repair package %ws. Extended "...
0x1800937a7  mov     [rsp+4B8h+var_498], rax; int
0x1800937ac  mov     r9d, r15d; char *
0x1800937af  lea     r8, aOnecoreBaseApp_58; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800937b6  mov     edx, 0DCh; void *
0x1800937bb  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800937c0  nop
0x1800937c1  lea     rcx, [rsp+4B8h+var_368]; this
0x1800937c9  call    ??1ActivationProperties@@QEAA@XZ; ActivationProperties::~ActivationProperties(void)
0x1800937ce  nop
0x1800937cf  lea     rcx, [rsp+4B8h+var_1D8]; this
0x1800937d7  call    ??1TryActivateDesktopAppXApplication@DesktopAppXProvider@@QEAA@XZ; DesktopAppXProvider::TryActivateDesktopAppXApplication::~TryActivateDesktopAppXApplication(void)
0x1800937dc  mov     eax, r15d
0x1800937df  jmp     loc_180094132
0x1800937e4  lea     r9, [rsp+4B8h+var_3F0]; struct AppDeploymentInfo *
0x1800937ec  mov     r8, r13; struct DESKTOP_APPX_ACTIVATION_RESULT *
0x1800937ef  lea     rdx, [rsp+4B8h+var_368]; struct ActivationProperties *
0x1800937f7  lea     rcx, [rsp+4B8h+var_3D8]; struct DESKTOP_APPX_ACTIVATION_PARAMS *
0x1800937ff  call    ?EvaluateApplicationLaunch@@YAJPEBUDESKTOP_APPX_ACTIVATION_PARAMS@@AEAUActivationProperties@@PEAUDESKTOP_APPX_ACTIVATION_RESULT@@PEAUAppDeploymentInfo@@@Z; EvaluateApplicationLaunch(DESKTOP_APPX_ACTIVATION_PARAMS const *,ActivationProperties &,DESKTOP_APPX_ACTIVATION_RESULT *,AppDeploymentInfo *)
0x180093804  mov     r15d, eax
0x180093807  test    eax, eax
0x180093809  jns     loc_1800938A4
0x18009380f  mov     rcx, [rsp+4B8h]; this
0x180093817  mov     [rsp+4B8h+var_490], rbx; char *
0x18009381c  lea     rax, aStillFailedAft; "Still failed after successfully repairi"...
0x180093823  mov     [rsp+4B8h+var_498], rax; int
0x180093828  mov     r9d, r15d; char *
0x18009382b  lea     r8, aOnecoreBaseApp_58; "onecore\\base\\appmodel\\execmodel\\des"...
0x180093832  mov     edx, 0E0h; void *
0x180093837  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18009383c  nop
0x18009383d  lea     rcx, [rsp+4B8h+var_368]; this
0x180093845  call    ??1ActivationProperties@@QEAA@XZ; ActivationProperties::~ActivationProperties(void)
0x18009384a  nop
0x18009384b  lea     rcx, [rsp+4B8h+var_1D8]; this
0x180093853  call    ??1TryActivateDesktopAppXApplication@DesktopAppXProvider@@QEAA@XZ; DesktopAppXProvider::TryActivateDesktopAppXApplication::~TryActivateDesktopAppXApplication(void)
0x180093858  mov     eax, r15d
0x18009385b  jmp     loc_180094132
0x180093860  mov     rcx, [rsp+4B8h]; this
0x180093868  mov     r9d, ebx; char *
0x18009386b  lea     r8, aOnecoreBaseApp_58; "onecore\\base\\appmodel\\execmodel\\des"...
0x180093872  mov     edx, 0E5h; void *
0x180093877  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009387c  nop
0x18009387d  lea     rcx, [rsp+4B8h+var_368]; this
0x180093885  call    ??1ActivationProperties@@QEAA@XZ; ActivationProperties::~ActivationProperties(void)
0x18009388a  nop
0x18009388b  lea     rcx, [rsp+4B8h+var_1D8]; this
0x180093893  call    ??1TryActivateDesktopAppXApplication@DesktopAppXProvider@@QEAA@XZ; DesktopAppXProvider::TryActivateDesktopAppXApplication::~TryActivateDesktopAppXApplication(void)
0x180093898  mov     eax, ebx
0x18009389a  jmp     loc_180094132
0x18009389f  mov     edi, 80270254h
0x1800938a4  mov     ebx, [r13+0]
0x1800938a8  mov     r11, qword ptr [rsp+4B8h+var_3B8+8]
0x1800938b0  cmp     ebx, 1
0x1800938b3  jz      loc_180094013
0x1800938b9  bt      r11d, 0Eh
0x1800938be  jnb     short loc_1800938D2
0x1800938c0  mov     r10d, [rsp+4B8h+var_240]
0x1800938c8  cmp     r10d, 2
0x1800938cc  jnz     loc_18009401B
0x1800938d2  xor     r9d, r9d; bool
0x1800938d5  mov     r8, r13; struct DESKTOP_APPX_ACTIVATION_RESULT *
0x1800938d8  lea     rdx, [rsp+4B8h+var_368]; struct ActivationProperties *
0x1800938e0  lea     rcx, [rsp+4B8h+var_3D8]; struct DESKTOP_APPX_ACTIVATION_PARAMS *
0x1800938e8  call    ?InternalTryActivateDesktopAppXApplication@@YAJPEBUDESKTOP_APPX_ACTIVATION_PARAMS@@AEAUActivationProperties@@PEAUDESKTOP_APPX_ACTIVATION_RESULT@@_N@Z; InternalTryActivateDesktopAppXApplication(DESKTOP_APPX_ACTIVATION_PARAMS const *,ActivationProperties &,DESKTOP_APPX_ACTIVATION_RESULT *,bool)
0x1800938ed  mov     ebx, eax
0x1800938ef  mov     rcx, [rsp+4B8h]; this
0x1800938f7  test    eax, eax
0x1800938f9  jns     loc_180093EEC
0x1800938ff  mov     r9d, eax; char *
0x180093902  lea     r8, aOnecoreBaseApp_58; "onecore\\base\\appmodel\\execmodel\\des"...
0x180093909  mov     edx, 0FCh; void *
0x18009390e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180093913  mov     r15d, ebx
0x180093916  cmp     ebx, 800704C7h
0x18009391c  jz      loc_180093EEF
0x180093922  cmp     ebx, 80073D1Eh
0x180093928  jz      loc_180093EEF
0x18009392e  movdqa  xmm0, cs:__xmm@87e10bd0c0ea0001800704cfc03f6603
0x180093936  movdqa  [rsp+4B8h+var_88], xmm0
0x18009393f  movdqa  xmm1, cs:__xmm@803f8067803f9008803f8008803f700f
0x180093947  movdqa  [rsp+4B8h+var_78], xmm1
0x180093950  movdqa  xmm0, cs:__xmm@803f8001803f81f5803f800787e107d7
0x180093958  movdqa  [rsp+4B8h+var_68], xmm0
0x180093961  movdqa  xmm1, cs:__xmm@803f9009803f800e803f800b803f9007
0x180093969  movdqa  [rsp+4B8h+var_58], xmm1
0x180093972  movdqa  xmm0, cs:__xmm@80072ee780072f8f80072efe80072efd
0x18009397a  movdqa  [rsp+4B8h+var_48], xmm0
0x180093983  mov     [rsp+4B8h+var_38], 80072EE2h
0x18009398e  lea     rax, [rsp+4B8h+var_88]
0x180093996  mov     [rsp+4B8h+var_408], ebx
0x18009399d  cmp     ebx, [rax]
0x18009399f  jz      loc_180093A96
0x1800939a5  add     rax, 4
0x1800939a9  lea     rcx, [rsp+4B8h+var_34]
0x1800939b1  cmp     rax, rcx
0x1800939b4  jnz     short loc_18009399D
0x1800939b6  cmp     ebx, edi
0x1800939b8  jz      short loc_1800939C2
0x1800939ba  cmp     ebx, 80073D55h
0x1800939c0  jnz     short loc_1800939C7
0x1800939c2  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "hr != E_APPLICATION_NOT_REGISTERED && hr != HRESULT_FROM_WIN32(APPMODEL_ERROR_PACKAGE_RUNTIME_CORRUPT)")
0x1800939c7  mov     dword ptr [rsp+4B8h+var_410], esi
0x1800939ce  lea     rcx, [rsp+4B8h+var_2E8]
0x1800939d6  cmp     [rsp+4B8h+var_2D0], 7
0x1800939df  cmova   rcx, [rsp+4B8h+var_2E8]; unsigned __int16 *
0x1800939e8  lea     rdx, [rsp+4B8h+var_410]; int *
0x1800939f0  call    ?RepairPackage@@YAJPEBGPEAJ@Z; RepairPackage(ushort const *,long *)
0x1800939f5  test    eax, eax
0x1800939f7  js      short loc_180093A41
0x1800939f9  mov     r9b, 1; bool
0x1800939fc  mov     r8, r13; struct DESKTOP_APPX_ACTIVATION_RESULT *
0x1800939ff  lea     rdx, [rsp+4B8h+var_368]; struct ActivationProperties *
0x180093a07  lea     rcx, [rsp+4B8h+var_3D8]; struct DESKTOP_APPX_ACTIVATION_PARAMS *
0x180093a0f  call    ?InternalTryActivateDesktopAppXApplication@@YAJPEBUDESKTOP_APPX_ACTIVATION_PARAMS@@AEAUActivationProperties@@PEAUDESKTOP_APPX_ACTIVATION_RESULT@@_N@Z; InternalTryActivateDesktopAppXApplication(DESKTOP_APPX_ACTIVATION_PARAMS const *,ActivationProperties &,DESKTOP_APPX_ACTIVATION_RESULT *,bool)
0x180093a14  mov     r15d, eax
0x180093a17  mov     rcx, [rsp+4B8h]; this
  ... truncated ...
```
