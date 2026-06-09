# udk::CopilotPlusDetection::details::QueryDriverVersionUsingSetupDi(DXCoreHardwareIDParts const &)

- ea: `0x140098cd8`
- end: `0x140099318`
- name: `?QueryDriverVersionUsingSetupDi@details@CopilotPlusDetection@udk@@YA@AEBUDXCoreHardwareIDParts@@@Z`
- size: `1600`
- prototype: `__int64 __fastcall(udk::CopilotPlusDetection::details *__hidden this, const struct DXCoreHardwareIDParts *)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14016ef64`
- `0x14016f134`

## callees

- `0x14000a150`
- `0x14000a3e0`
- `0x140019308`
- `0x1400645f0`
- `0x140097a34`
- `0x140098cd8`
- `0x1400a2774`
- `0x1400da860`
- `0x140103db0`
- `0x1401040e0`
- `0x140115828`
- `0x140135388`
- `0x1401879cc`
- `0x1401db010`

## import_xrefs

- `msvcp_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x140099124`
- `msvcp_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x140099124`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x14009913e`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x14009913e`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x14009910b`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x14009910b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400990cd`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400990cd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140098d56`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140098d87`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140098db8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140098de9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140098e1c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140098d56`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140098d87`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140098db8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140098de9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140098e1c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140098d2d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140098d2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140099274`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140099274`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140098ffc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140098ffc`

## string_xrefs

- `0x140098d26`: `setupapi.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
udk::CopilotPlusDetection::details *__fastcall udk::CopilotPlusDetection::details::QueryDriverVersionUsingSetupDi(
        udk::CopilotPlusDetection::details *this,
        const struct DXCoreHardwareIDParts *a2)
{
  HMODULE Library; // rax
  const char *v5; // r9
  HMODULE v6; // rbx
  const char *v7; // r9
  FARPROC ProcAddress; // r14
  const char *v9; // r9
  FARPROC v10; // r13
  const char *v11; // r9
  FARPROC v12; // r12
  const char *v13; // r9
  const char *v14; // r9
  __int64 v15; // rax
  __int64 v16; // r15
  unsigned int v17; // esi
  wchar_t *v18; // r14
  const char *v19; // r9
  __int64 trivial_2; // rbx
  __int64 v21; // rax
  __int64 v22; // rcx
  const WCHAR *v23; // r8
  const WCHAR *v24; // rcx
  const char *v25; // r9
  __int16 v26; // ax
  unsigned __int64 v27; // rsi
  unsigned __int64 i; // rbx
  _DWORD *v29; // rax
  const wchar_t *v30; // r12
  __int16 v31; // cx
  wchar_t *v32; // r14
  unsigned __int64 v33; // rdx
  __int16 v34; // ax
  const char *v36; // r9
  __int128 v37; // [rsp+50h] [rbp-138h] BYREF
  __int64 v38; // [rsp+60h] [rbp-128h]
  wchar_t *EndPtr; // [rsp+68h] [rbp-120h] BYREF
  int v40; // [rsp+70h] [rbp-118h] BYREF
  _QWORD v41[2]; // [rsp+78h] [rbp-110h] BYREF
  _DWORD *v42; // [rsp+88h] [rbp-100h]
  __int64 v43; // [rsp+90h] [rbp-F8h]
  FARPROC v44; // [rsp+98h] [rbp-F0h]
  char v45; // [rsp+A0h] [rbp-E8h]
  FARPROC v46; // [rsp+A8h] [rbp-E0h]
  _DWORD v47[4]; // [rsp+B0h] [rbp-D8h] BYREF
  LPCWCH lpString1[2]; // [rsp+C0h] [rbp-C8h] BYREF
  int cchCount2[2]; // [rsp+D0h] [rbp-B8h]
  unsigned __int64 v50; // [rsp+D8h] [rbp-B0h]
  _OWORD v51[2]; // [rsp+E0h] [rbp-A8h] BYREF
  wchar_t *String[4]; // [rsp+100h] [rbp-88h] BYREF
  _WORD v53[24]; // [rsp+120h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]

  v41[1] = this;
  udk::CopilotPlusDetection::HardwareRequirementsTelemetry::NpuDriverVersionFallbackUsed<unsigned int const &,unsigned int const &>(
    a2,
    (char *)a2 + 4);
  Library = LoadLibraryExW(L"setupapi.dll", 0, 0x800u);
  v6 = Library;
  v41[0] = Library;
  if ( !Library )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x86,
      (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
      v5);
  ProcAddress = GetProcAddress(Library, "SetupDiGetClassDevsW");
  if ( !ProcAddress )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x89,
      (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
      v7);
  v10 = GetProcAddress(v6, "SetupDiDestroyDeviceInfoList");
  if ( !v10 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x8B,
      (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
      v9);
  v12 = GetProcAddress(v6, "SetupDiEnumDeviceInfo");
  if ( !v12 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x8D,
      (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
      v11);
  EndPtr = (wchar_t *)GetProcAddress(v6, "SetupDiGetDeviceInstanceIdW");
  if ( !EndPtr )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x8F,
      (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
      v13);
  v46 = GetProcAddress(v6, "SetupDiGetDevicePropertyW");
  if ( !v46 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x91,
      (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
      v14);
  udk::npu_detection::HardwareIdToVendorProductString(lpString1, a2);
  v47[0] = -266691245;
  v47[1] = 1221738486;
  v47[2] = -1480026209;
  v47[3] = 216091392;
  v15 = ((__int64 (__fastcall *)(_DWORD *, _QWORD, _QWORD, __int64))ProcAddress)(v47, 0, 0, 2);
  v16 = v15;
  if ( v15 != -1 )
  {
    v43 = v15;
    v44 = v10;
    v45 = 1;
    memset(v51, 0, sizeof(v51));
    LODWORD(v51[0]) = 32;
    v17 = 0;
    v18 = EndPtr;
    while ( ((unsigned int (__fastcall *)(__int64, _QWORD, _OWORD *))v12)(v16, v17, v51) )
    {
      v37 = 0;
      v38 = 0;
      std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(&v37);
      if ( !((unsigned int (__fastcall *)(__int64, _OWORD *, _QWORD, __int64, _QWORD))v18)(
              v16,
              v51,
              v37,
              (__int64)(*((_QWORD *)&v37 + 1) - v37) >> 1,
              0) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0xAB,
          (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
          v19);
      trivial_2 = _std_find_trivial_2(v37, *((_QWORD *)&v37 + 1), 0);
      v21 = _std_find_trivial_2(v37, trivial_2, 92);
      if ( v21 != *((_QWORD *)&v37 + 1) && trivial_2 != *((_QWORD *)&v37 + 1) )
      {
        v22 = v21 + 2;
        if ( v21 + 2 != trivial_2 && (unsigned __int64)((trivial_2 - v22) >> 1) >= *(_QWORD *)cchCount2 )
        {
          v23 = (const WCHAR *)(v37 + 2 * ((v22 - (__int64)v37) >> 1));
          v24 = (const WCHAR *)lpString1;
          if ( v50 > 7 )
            v24 = lpString1[0];
          if ( CompareStringOrdinal(v24, cchCount2[0], v23, cchCount2[0], 1) == 2 )
          {
            v40 = 0;
            if ( !((unsigned int (__fastcall *)(__int64, _OWORD *, const DEVPROPKEY *, int *))v46)(
                    v16,
                    v51,
                    &DEVPKEY_Device_DriverVersion,
                    &v40) )
              wil::details::in1diag3::Throw_GetLastError(
                retaddr,
                (void *)0xC2,
                (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
                v25);
            v26 = 0;
            v46 = 0;
            v27 = 0;
            for ( i = 0; i < 4; ++i )
            {
              if ( v27 >= 0x18 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0xCB,
                  (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
                  (const char *)0x80070057LL,
                  (int)v53);
              std::wstring::wstring(String, &v53[v27]);
              v29 = (_DWORD *)_o__errno();
              v42 = v29;
              v30 = (const wchar_t *)String;
              if ( String[3] > (wchar_t *)7 )
                v30 = String[0];
              EndPtr = 0;
              *v29 = 0;
              v31 = wcstol(v30, &EndPtr, 10);
              v32 = EndPtr;
              if ( v30 == EndPtr )
                std::_Xinvalid_argument("invalid stoi argument");
              if ( *v42 == 34 )
                std::_Xout_of_range("stoi argument out of range");
              *((_WORD *)&v47[-2] + i) = v31;
              std::wstring::~wstring(String);
              v33 = v32 - v30 + v27;
              v34 = v53[v33];
              if ( i == 3 )
              {
                if ( v34 )
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0xDB,
                    (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
                    (const char *)0x80070057LL,
                    (int)v53);
              }
              else
              {
                if ( v34 != 46 )
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0xD3,
                    (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
                    (const char *)0x80070057LL,
                    (int)v53);
                v27 = v33 + 1;
              }
              v26 = (__int16)v46;
            }
            *(_WORD *)this = HIWORD(v46);
            *((_WORD *)this + 1) = WORD2(v46);
            *((_WORD *)this + 2) = WORD1(v46);
            *((_WORD *)this + 3) = v26;
            if ( (_QWORD)v37 )
            {
              std::_Deallocate<16>(v37, 2 * ((v38 - (__int64)v37) >> 1));
              v37 = 0;
              v38 = 0;
            }
            ((void (__fastcall *)(__int64))v10)(v16);
            std::wstring::~wstring(lpString1);
            wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(v41);
            return this;
          }
        }
      }
      ++v17;
      if ( (_QWORD)v37 )
        std::_Deallocate<16>(v37, 2 * ((v38 - (__int64)v37) >> 1));
    }
    if ( GetLastError() != 259 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xE5,
        (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
        v36);
    ((void (__fastcall *)(__int64))v10)(v16);
  }
  udk::CopilotPlusDetection::HardwareRequirementsTelemetry::NpuDriverVersionFallbackFailed();
  *(_QWORD *)this = 0;
  std::wstring::~wstring(lpString1);
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(v41);
  return this;
}

```

## disassembly

```asm
0x140098cd8  mov     [rsp+arg_10], rbx
0x140098cdd  mov     [rsp+arg_18], rsi
0x140098ce2  push    rdi
0x140098ce3  push    r12
0x140098ce5  push    r13
0x140098ce7  push    r14
0x140098ce9  push    r15
0x140098ceb  sub     rsp, 160h
0x140098cf2  mov     rax, cs:__security_cookie
0x140098cf9  xor     rax, rsp
0x140098cfc  mov     [rsp+188h+var_38], rax
0x140098d04  mov     rsi, rdx
0x140098d07  mov     rdi, rcx
0x140098d0a  mov     [rsp+188h+var_108], rcx
0x140098d12  add     rdx, 4
0x140098d16  mov     rcx, rsi
0x140098d19  call    ??$NpuDriverVersionFallbackUsed@AEBIAEBI@HardwareRequirementsTelemetry@CopilotPlusDetection@udk@@SAXAEBI0@Z; udk::CopilotPlusDetection::HardwareRequirementsTelemetry::NpuDriverVersionFallbackUsed<uint const &,uint const &>(uint const &,uint const &)
0x140098d1e  xor     edx, edx; hFile
0x140098d20  mov     r8d, 800h; dwFlags
0x140098d26  lea     rcx, aSetupapiDll; "setupapi.dll"
0x140098d2d  call    cs:__imp_LoadLibraryExW
0x140098d33  mov     rbx, rax
0x140098d36  mov     [rsp+188h+var_110], rax
0x140098d3b  mov     rcx, [rsp+188h]; this
0x140098d43  test    rax, rax
0x140098d46  jz      loc_1400992D0
0x140098d4c  lea     rdx, aSetupdigetclas; "SetupDiGetClassDevsW"
0x140098d53  mov     rcx, rax; hModule
0x140098d56  call    cs:__imp_GetProcAddress
0x140098d5c  mov     r14, rax
0x140098d5f  mov     rcx, [rsp+188h]; this
0x140098d67  test    rax, rax
0x140098d6a  jnz     short loc_140098D7D
0x140098d6c  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x140098d73  mov     edx, 89h; void *
0x140098d78  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140098d7d  lea     rdx, aSetupdidestroy; "SetupDiDestroyDeviceInfoList"
0x140098d84  mov     rcx, rbx; hModule
0x140098d87  call    cs:__imp_GetProcAddress
0x140098d8d  mov     r13, rax
0x140098d90  mov     rcx, [rsp+188h]; this
0x140098d98  test    rax, rax
0x140098d9b  jnz     short loc_140098DAE
0x140098d9d  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x140098da4  mov     edx, 8Bh; void *
0x140098da9  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140098dae  lea     rdx, aSetupdienumdev; "SetupDiEnumDeviceInfo"
0x140098db5  mov     rcx, rbx; hModule
0x140098db8  call    cs:__imp_GetProcAddress
0x140098dbe  mov     r12, rax
0x140098dc1  mov     rcx, [rsp+188h]; this
0x140098dc9  test    rax, rax
0x140098dcc  jnz     short loc_140098DDF
0x140098dce  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x140098dd5  mov     edx, 8Dh; void *
0x140098dda  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140098ddf  lea     rdx, aSetupdigetdevi_0; "SetupDiGetDeviceInstanceIdW"
0x140098de6  mov     rcx, rbx; hModule
0x140098de9  call    cs:__imp_GetProcAddress
0x140098def  mov     [rsp+188h+EndPtr], rax
0x140098df4  mov     rcx, [rsp+188h]; this
0x140098dfc  test    rax, rax
0x140098dff  jnz     short loc_140098E12
0x140098e01  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x140098e08  mov     edx, 8Fh; void *
0x140098e0d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140098e12  lea     rdx, aSetupdigetdevi; "SetupDiGetDevicePropertyW"
0x140098e19  mov     rcx, rbx; hModule
0x140098e1c  call    cs:__imp_GetProcAddress
0x140098e22  mov     [rsp+188h+var_E0], rax
0x140098e2a  mov     rcx, [rsp+188h]; this
0x140098e32  xor     ebx, ebx
0x140098e34  test    rax, rax
0x140098e37  jnz     short loc_140098E4A
0x140098e39  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x140098e40  mov     edx, 91h; void *
0x140098e45  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140098e4a  mov     rdx, rsi
0x140098e4d  lea     rcx, [rsp+188h+lpString1]
0x140098e55  call    ?HardwareIdToVendorProductString@npu_detection@udk@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBUDXCoreHardwareIDParts@@@Z; udk::npu_detection::HardwareIdToVendorProductString(DXCoreHardwareIDParts const &)
0x140098e5a  nop
0x140098e5b  mov     [rsp+188h+var_D8], 0F01A9D53h
0x140098e66  mov     [rsp+188h+var_D4], 48D23FF6h
0x140098e71  mov     [rsp+188h+var_D0], 0A7C8979Fh
0x140098e7c  mov     [rsp+188h+var_CC], 0CE14B00h
0x140098e87  mov     r9d, 2
0x140098e8d  xor     r8d, r8d
0x140098e90  xor     edx, edx
0x140098e92  lea     rcx, [rsp+188h+var_D8]
0x140098e9a  mov     rax, r14
0x140098e9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140098ea2  mov     r15, rax
0x140098ea5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140098ea9  jz      loc_1400992A7
0x140098eaf  mov     [rsp+188h+var_F8], rax
0x140098eb7  mov     [rsp+188h+var_F0], r13
0x140098ebf  mov     [rsp+188h+var_E8], 1
0x140098ec7  xorps   xmm0, xmm0
0x140098eca  movups  [rsp+188h+var_A8], xmm0
0x140098ed2  movups  [rsp+188h+var_98], xmm0
0x140098eda  mov     dword ptr [rsp+188h+var_A8], 20h ; ' '
0x140098ee5  mov     esi, ebx
0x140098ee7  mov     r14, [rsp+188h+EndPtr]
0x140098eec  lea     r8, [rsp+188h+var_A8]
0x140098ef4  mov     edx, esi
0x140098ef6  mov     rcx, r15
0x140098ef9  mov     rax, r12
0x140098efc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140098f01  test    eax, eax
0x140098f03  jz      loc_140099274
0x140098f09  xorps   xmm0, xmm0
0x140098f0c  movdqu  [rsp+188h+var_138], xmm0
0x140098f12  mov     [rsp+188h+var_128], rbx
0x140098f17  lea     rcx, [rsp+188h+var_138]
0x140098f1c  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x140098f21  mov     r8, qword ptr [rsp+188h+var_138]
0x140098f26  mov     r9, qword ptr [rsp+188h+var_138+8]
0x140098f2b  sub     r9, r8
0x140098f2e  sar     r9, 1
0x140098f31  mov     qword ptr [rsp+188h+bIgnoreCase], rbx
0x140098f36  lea     rdx, [rsp+188h+var_A8]
0x140098f3e  mov     rcx, r15
0x140098f41  mov     rax, r14
0x140098f44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140098f49  mov     rcx, [rsp+188h]; this
0x140098f51  test    eax, eax
0x140098f53  jnz     short loc_140098F66
0x140098f55  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x140098f5c  mov     edx, 0ABh; void *
0x140098f61  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140098f66  xor     r8d, r8d
0x140098f69  mov     rdx, qword ptr [rsp+188h+var_138+8]
0x140098f6e  mov     rcx, qword ptr [rsp+188h+var_138]
0x140098f73  call    __std_find_trivial_2
0x140098f78  mov     rbx, rax
0x140098f7b  mov     r8d, 5Ch ; '\'
0x140098f81  mov     rdx, rax
0x140098f84  mov     rcx, qword ptr [rsp+188h+var_138]
0x140098f89  call    __std_find_trivial_2
0x140098f8e  cmp     rax, qword ptr [rsp+188h+var_138+8]
0x140098f93  jz      loc_14009924A
0x140098f99  cmp     rbx, qword ptr [rsp+188h+var_138+8]
0x140098f9e  jz      loc_14009924A
0x140098fa4  lea     rcx, [rax+2]
0x140098fa8  cmp     rcx, rbx
0x140098fab  jz      loc_14009924A
0x140098fb1  sub     rbx, rcx
0x140098fb4  sar     rbx, 1
0x140098fb7  mov     rdx, qword ptr [rsp+188h+cchCount2]; cchCount1
0x140098fbf  cmp     rbx, rdx
0x140098fc2  jb      loc_14009924A
0x140098fc8  mov     rax, qword ptr [rsp+188h+var_138]
0x140098fcd  sub     rcx, rax
0x140098fd0  sar     rcx, 1
0x140098fd3  lea     r8, [rax+rcx*2]; lpString2
0x140098fd7  lea     rcx, [rsp+188h+lpString1]
0x140098fdf  cmp     [rsp+188h+var_B0], 7
0x140098fe8  cmova   rcx, [rsp+188h+lpString1]; lpString1
0x140098ff1  mov     [rsp+188h+bIgnoreCase], 1; bIgnoreCase
0x140098ff9  mov     r9d, edx; cchCount2
0x140098ffc  call    cs:__imp_CompareStringOrdinal
0x140099002  cmp     eax, 2
0x140099005  jnz     loc_14009924A
0x14009900b  xor     r14d, r14d
0x14009900e  mov     [rsp+188h+var_118], r14d
0x140099013  mov     [rsp+188h+var_150], r14d
0x140099018  mov     [rsp+188h+var_158], r14
0x14009901d  mov     [rsp+188h+var_160], 30h ; '0'
0x140099025  lea     rax, [rsp+188h+var_68]
0x14009902d  mov     qword ptr [rsp+188h+bIgnoreCase], rax; int
0x140099032  lea     r9, [rsp+188h+var_118]
0x140099037  lea     r8, DEVPKEY_Device_DriverVersion
0x14009903e  lea     rdx, [rsp+188h+var_A8]
0x140099046  mov     rcx, r15
0x140099049  mov     rax, [rsp+188h+var_E0]
0x140099051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140099056  mov     rcx, [rsp+188h]; this
0x14009905e  test    eax, eax
0x140099060  jnz     short loc_140099073
0x140099062  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x140099069  mov     edx, 0C2h; void *
0x14009906e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140099073  mov     rax, r14
0x140099076  mov     [rsp+188h+var_E0], rax
0x14009907e  mov     rsi, r14
0x140099081  mov     rbx, r14
0x140099084  cmp     rbx, 4
0x140099088  jnb     loc_1400991CC
0x14009908e  mov     rcx, [rsp+188h]; this
0x140099096  cmp     rsi, 18h
0x14009909a  jb      short loc_1400990B3
0x14009909c  mov     r9d, 80070057h; char *
0x1400990a2  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x1400990a9  mov     edx, 0CBh; void *
0x1400990ae  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400990b3  lea     rdx, [rsp+188h+var_68]
0x1400990bb  lea     rdx, [rdx+rsi*2]
0x1400990bf  lea     rcx, [rsp+188h+String]
0x1400990c7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1400990cc  nop
0x1400990cd  call    cs:__imp__o__errno
0x1400990d3  mov     [rsp+188h+var_100], rax
0x1400990db  lea     r12, [rsp+188h+String]
0x1400990e3  cmp     [rsp+188h+var_70], 7
0x1400990ec  cmova   r12, [rsp+188h+String]
0x1400990f5  mov     [rsp+188h+EndPtr], r14
0x1400990fa  mov     [rax], r14d
0x1400990fd  mov     r8d, 0Ah; Radix
0x140099103  lea     rdx, [rsp+188h+EndPtr]; EndPtr
0x140099108  mov     rcx, r12; String
0x14009910b  call    cs:__imp_wcstol
0x140099111  mov     ecx, eax
0x140099113  mov     r14, [rsp+188h+EndPtr]
0x140099118  cmp     r12, r14
0x14009911b  jnz     short loc_14009912A
0x14009911d  lea     rcx, aInvalidStoiArg; "invalid stoi argument"
0x140099124  call    cs:__imp_?_Xinvalid_argument@std@@YAXPEBD@Z; std::_Xinvalid_argument(char const *)
0x14009912a  mov     rax, [rsp+188h+var_100]
0x140099132  cmp     dword ptr [rax], 22h ; '"'
0x140099135  jnz     short loc_140099144
0x140099137  lea     rcx, aStoiArgumentOu; "stoi argument out of range"
0x14009913e  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x140099144  sub     r14, r12
0x140099147  sar     r14, 1
0x14009914a  mov     word ptr [rsp+rbx*2+188h+var_E0], cx
0x140099152  lea     rcx, [rsp+188h+String]; void *
0x14009915a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14009915f  lea     rdx, [r14+rsi]
0x140099163  movzx   eax, [rsp+rdx*2+188h+var_68]
0x14009916b  mov     rcx, [rsp+188h]; this
0x140099173  cmp     rbx, 3
0x140099177  jz      short loc_1400991AD
0x140099179  cmp     ax, 2Eh ; '.'
0x14009917d  jz      short loc_140099196
0x14009917f  mov     r9d, 80070057h; char *
0x140099185  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x14009918c  mov     edx, 0D3h; void *
0x140099191  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140099196  lea     rsi, [rdx+1]
0x14009919a  xor     r14d, r14d
0x14009919d  inc     rbx
0x1400991a0  mov     rax, [rsp+188h+var_E0]
0x1400991a8  jmp     loc_140099084
0x1400991ad  xor     r14d, r14d
0x1400991b0  test    ax, ax
0x1400991b3  jz      short loc_14009919D
0x1400991b5  mov     r9d, 80070057h; char *
0x1400991bb  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x1400991c2  mov     edx, 0DBh; void *
0x1400991c7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400991cc  movzx   ecx, word ptr [rsp+188h+var_E0+6]
0x1400991d4  mov     [rdi], cx
0x1400991d7  movzx   ecx, word ptr [rsp+188h+var_E0+4]
0x1400991df  mov     [rdi+2], cx
0x1400991e3  movzx   ecx, word ptr [rsp+188h+var_E0+2]
0x1400991eb  mov     [rdi+4], cx
0x1400991ef  mov     [rdi+6], ax
0x1400991f3  mov     rcx, qword ptr [rsp+188h+var_138]
0x1400991f8  test    rcx, rcx
0x1400991fb  jz      short loc_14009921E
0x1400991fd  mov     rdx, [rsp+188h+var_128]
0x140099202  sub     rdx, rcx
0x140099205  sar     rdx, 1
0x140099208  add     rdx, rdx
0x14009920b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x140099210  xorps   xmm0, xmm0
0x140099213  movdqu  [rsp+188h+var_138], xmm0
0x140099219  mov     [rsp+188h+var_128], r14
0x14009921e  mov     rcx, r15
0x140099221  mov     rax, r13
0x140099224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140099229  nop
0x14009922a  lea     rcx, [rsp+188h+lpString1]; void *
0x140099232  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140099237  nop
0x140099238  lea     rcx, [rsp+188h+var_110]
0x14009923d  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x140099242  mov     rax, rdi
0x140099245  jmp     loc_1400992EA
0x14009924a  inc     esi
0x14009924c  mov     rcx, qword ptr [rsp+188h+var_138]
0x140099251  xor     ebx, ebx
0x140099253  test    rcx, rcx
0x140099256  jz      loc_140098EEC
0x14009925c  mov     rdx, [rsp+188h+var_128]
0x140099261  sub     rdx, rcx
0x140099264  sar     rdx, 1
0x140099267  add     rdx, rdx
0x14009926a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x14009926f  jmp     loc_140098EEC
0x140099274  call    cs:__imp_GetLastError
0x14009927a  cmp     eax, 103h
0x14009927f  jz      short loc_14009929B
0x140099281  mov     rcx, [rsp+188h]; this
0x140099289  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x140099290  mov     edx, 0E5h; void *
0x140099295  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14009929b  mov     rcx, r15
0x14009929e  mov     rax, r13
0x1400992a1  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
