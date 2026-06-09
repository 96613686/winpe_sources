# udk::CopilotPlusDetection::details::QueryDriverVersionUsingSetupDi(DXCoreHardwareIDParts const &)

- ea: `0x1800e866c`
- end: `0x1800e8d07`
- name: `?QueryDriverVersionUsingSetupDi@details@CopilotPlusDetection@udk@@YA@AEBUDXCoreHardwareIDParts@@@Z`
- size: `1691`
- prototype: `__int64 __fastcall(udk::CopilotPlusDetection::details *__hidden this, const struct DXCoreHardwareIDParts *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180170b50`

## callees

- `0x180012120`
- `0x18001b470`
- `0x18001d8a0`
- `0x1800a3a38`
- `0x1800d6b3c`
- `0x1800e2374`
- `0x1800e866c`
- `0x1800e95f0`
- `0x1800ea250`
- `0x1801244c0`
- `0x18012540e`
- `0x180128f80`
- `0x18016ac94`
- `0x180170a5c`
- `0x180171f58`
- `0x180241010`

## import_xrefs

- `msvcp_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x1800e8b10`
- `msvcp_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x1800e8b10`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1800e8b24`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1800e8b24`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x1800e8af9`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x1800e8af9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800e8ac0`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800e8ac0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800e86c1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800e86c1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e86ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e871b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e8754`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e8785`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e87b8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e86ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e871b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e8754`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e8785`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e87b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e8c63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e8c63`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800e89f4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800e89f4`

## string_xrefs

- `0x1800e86ba`: `setupapi.dll`

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
  FARPROC v10; // r15
  const char *v11; // r9
  FARPROC v12; // r13
  const char *v13; // r9
  const char *v14; // r9
  __int64 v15; // rax
  __int64 v16; // r12
  unsigned int i; // r14d
  char *v18; // rsi
  unsigned __int64 v19; // rcx
  size_t v20; // rbx
  int v21; // eax
  const char *v22; // r9
  unsigned __int64 v23; // rsi
  char *trivial_2; // rbx
  char *v25; // rax
  char *v26; // rcx
  const WCHAR *v27; // r8
  const WCHAR *v28; // rcx
  const char *v29; // r9
  __int16 v30; // ax
  unsigned __int64 j; // rbx
  _DWORD *v32; // rax
  _DWORD *v33; // r13
  const wchar_t *v34; // r15
  __int16 v35; // ax
  wchar_t *v36; // r14
  unsigned __int64 v37; // rdx
  __int16 v38; // ax
  const char *v40; // r9
  void *v41[2]; // [rsp+50h] [rbp-138h] BYREF
  __int64 v42; // [rsp+60h] [rbp-128h]
  wchar_t *EndPtr; // [rsp+68h] [rbp-120h] BYREF
  int v44; // [rsp+70h] [rbp-118h] BYREF
  _QWORD v45[2]; // [rsp+78h] [rbp-110h] BYREF
  void (__fastcall *v46)(__int64); // [rsp+88h] [rbp-100h]
  __int64 v47; // [rsp+90h] [rbp-F8h]
  FARPROC v48; // [rsp+98h] [rbp-F0h]
  char v49; // [rsp+A0h] [rbp-E8h]
  FARPROC v50; // [rsp+A8h] [rbp-E0h]
  _DWORD v51[4]; // [rsp+B0h] [rbp-D8h] BYREF
  LPCWCH lpString1[2]; // [rsp+C0h] [rbp-C8h] BYREF
  int cchCount2[2]; // [rsp+D0h] [rbp-B8h]
  unsigned __int64 v54; // [rsp+D8h] [rbp-B0h]
  _OWORD v55[2]; // [rsp+E0h] [rbp-A8h] BYREF
  wchar_t *String[4]; // [rsp+100h] [rbp-88h] BYREF
  _WORD v57[24]; // [rsp+120h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]

  v45[1] = this;
  udk::CopilotPlusDetection::HardwareRequirementsTelemetry::NpuDriverVersionFallbackUsed<unsigned int const &,unsigned int const &>(
    a2,
    (char *)a2 + 4);
  Library = LoadLibraryExW(L"setupapi.dll", 0, 0x800u);
  v6 = Library;
  v45[0] = Library;
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
  v46 = (void (__fastcall *)(__int64))v10;
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
  v50 = GetProcAddress(v6, "SetupDiGetDevicePropertyW");
  if ( !v50 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x91,
      (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
      v14);
  udk::npu_detection::HardwareIdToVendorProductString(lpString1, a2);
  v51[0] = -266691245;
  v51[1] = 1221738486;
  v51[2] = -1480026209;
  v51[3] = 216091392;
  v15 = ((__int64 (__fastcall *)(_DWORD *, _QWORD, _QWORD, __int64))ProcAddress)(v51, 0, 0, 2);
  v16 = v15;
  if ( v15 == -1 )
    goto LABEL_58;
  v47 = v15;
  v48 = v10;
  v49 = 1;
  memset(v55, 0, sizeof(v55));
  LODWORD(v55[0]) = 32;
  for ( i = 0; ((unsigned int (__fastcall *)(__int64, _QWORD, _OWORD *))v12)(v16, i, v55); ++i )
  {
    std::vector<unique_ptr_bytes_buffer>::vector<unique_ptr_bytes_buffer>(v41);
    v18 = (char *)v41[1];
    v19 = ((char *)v41[1] - (char *)v41[0]) >> 1;
    if ( v19 <= 0xC8 )
    {
      if ( v19 >= 0xC8 )
        goto LABEL_22;
      if ( (unsigned __int64)((signed __int64)(v42 - (unsigned __int64)v41[0]) >> 1) < 0xC8 )
      {
        std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(v41);
        v18 = (char *)v41[1];
        goto LABEL_22;
      }
      v20 = 2 * (200 - v19);
      memset_0(v41[1], 0, v20);
      v18 += v20;
    }
    else
    {
      v18 = (char *)v41[0] + 400;
    }
    v41[1] = v18;
LABEL_22:
    v21 = ((__int64 (__fastcall *)(__int64, _OWORD *, void *, _QWORD, _QWORD))EndPtr)(
            v16,
            v55,
            v41[0],
            (unsigned int)((v18 - (char *)v41[0]) >> 1),
            0);
    v23 = 0;
    if ( !v21 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xAB,
        (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
        v22);
    trivial_2 = (char *)_std_find_trivial_2(v41[0], v41[1], 0);
    v25 = (char *)_std_find_trivial_2(v41[0], trivial_2, 92);
    if ( v25 != v41[1] && trivial_2 != v41[1] )
    {
      v26 = v25 + 2;
      if ( v25 + 2 != trivial_2 && (unsigned __int64)((trivial_2 - v26) >> 1) >= *(_QWORD *)cchCount2 )
      {
        v27 = (const WCHAR *)((char *)v41[0] + 2 * ((v26 - (char *)v41[0]) >> 1));
        v28 = (const WCHAR *)lpString1;
        if ( v54 > 7 )
          v28 = lpString1[0];
        if ( CompareStringOrdinal(v28, cchCount2[0], v27, cchCount2[0], 1) == 2 )
        {
          v44 = 0;
          if ( !((unsigned int (__fastcall *)(__int64, _OWORD *, const DEVPROPKEY *, int *))v50)(
                  v16,
                  v55,
                  &DEVPKEY_Device_DriverVersion,
                  &v44) )
            wil::details::in1diag3::Throw_GetLastError(
              retaddr,
              (void *)0xC2,
              (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
              v29);
          v30 = 0;
          v50 = 0;
          for ( j = 0; j < 4; ++j )
          {
            if ( v23 >= 0x18 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0xCB,
                (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
                (const char *)0x80070057LL,
                (int)v57);
            std::wstring::wstring(String, &v57[v23]);
            v32 = (_DWORD *)_o__errno();
            v33 = v32;
            v34 = (const wchar_t *)String;
            if ( String[3] > (wchar_t *)7 )
              v34 = String[0];
            EndPtr = 0;
            *v32 = 0;
            v35 = wcstol(v34, &EndPtr, 10);
            v36 = EndPtr;
            if ( v34 == EndPtr )
              std::_Xinvalid_argument("invalid stoi argument");
            if ( *v33 == 34 )
              std::_Xout_of_range("stoi argument out of range");
            *((_WORD *)&v51[-2] + j) = v35;
            ReIndexPatternInfo::~ReIndexPatternInfo((ReIndexPatternInfo *)String);
            v37 = v36 - v34 + v23;
            v38 = v57[v37];
            if ( j == 3 )
            {
              if ( v38 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0xDB,
                  (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
                  (const char *)0x80070057LL,
                  (int)v57);
            }
            else
            {
              if ( v38 != 46 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0xD3,
                  (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
                  (const char *)0x80070057LL,
                  (int)v57);
              v23 = v37 + 1;
            }
            v30 = (__int16)v50;
          }
          *(_WORD *)this = HIWORD(v50);
          *((_WORD *)this + 1) = WORD2(v50);
          *((_WORD *)this + 2) = WORD1(v50);
          *((_WORD *)this + 3) = v30;
          if ( v41[0] )
          {
            std::_Deallocate<16>(v41[0], 2 * ((signed __int64)(v42 - (unsigned __int64)v41[0]) >> 1));
            *(_OWORD *)v41 = 0;
            v42 = 0;
          }
          v46(v16);
          ReIndexPatternInfo::~ReIndexPatternInfo((ReIndexPatternInfo *)lpString1);
          wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(v45);
          return this;
        }
      }
    }
    if ( v41[0] )
      std::_Deallocate<16>(v41[0], 2 * ((signed __int64)(v42 - (unsigned __int64)v41[0]) >> 1));
  }
  if ( GetLastError() != 259 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xE5,
      (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
      v40);
  ((void (__fastcall *)(__int64))v10)(v16);
LABEL_58:
  udk::CopilotPlusDetection::HardwareRequirementsTelemetry::NpuDriverVersionFallbackFailed();
  *(_QWORD *)this = 0;
  ReIndexPatternInfo::~ReIndexPatternInfo((ReIndexPatternInfo *)lpString1);
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(v45);
  return this;
}

```

## disassembly

```asm
0x1800e866c  mov     [rsp+arg_10], rbx
0x1800e8671  mov     [rsp+arg_18], rsi
0x1800e8676  push    rdi
0x1800e8677  push    r12
0x1800e8679  push    r13
0x1800e867b  push    r14
0x1800e867d  push    r15
0x1800e867f  sub     rsp, 160h
0x1800e8686  mov     rax, cs:__security_cookie
0x1800e868d  xor     rax, rsp
0x1800e8690  mov     [rsp+188h+var_38], rax
0x1800e8698  mov     rsi, rdx
0x1800e869b  mov     rdi, rcx
0x1800e869e  mov     [rsp+188h+var_108], rcx
0x1800e86a6  add     rdx, 4
0x1800e86aa  mov     rcx, rsi
0x1800e86ad  call    ??$NpuDriverVersionFallbackUsed@AEBIAEBI@HardwareRequirementsTelemetry@CopilotPlusDetection@udk@@SAXAEBI0@Z; udk::CopilotPlusDetection::HardwareRequirementsTelemetry::NpuDriverVersionFallbackUsed<uint const &,uint const &>(uint const &,uint const &)
0x1800e86b2  xor     edx, edx; hFile
0x1800e86b4  mov     r8d, 800h; dwFlags
0x1800e86ba  lea     rcx, aSetupapiDll; "setupapi.dll"
0x1800e86c1  call    cs:__imp_LoadLibraryExW
0x1800e86c7  mov     rbx, rax
0x1800e86ca  mov     [rsp+188h+var_110], rax
0x1800e86cf  mov     rcx, [rsp+188h]; this
0x1800e86d7  test    rax, rax
0x1800e86da  jz      loc_1800E8CBF
0x1800e86e0  lea     rdx, aSetupdigetclas; "SetupDiGetClassDevsW"
0x1800e86e7  mov     rcx, rax; hModule
0x1800e86ea  call    cs:__imp_GetProcAddress
0x1800e86f0  mov     r14, rax
0x1800e86f3  mov     rcx, [rsp+188h]; this
0x1800e86fb  test    rax, rax
0x1800e86fe  jnz     short loc_1800E8711
0x1800e8700  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x1800e8707  mov     edx, 89h; void *
0x1800e870c  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800e8711  lea     rdx, aSetupdidestroy; "SetupDiDestroyDeviceInfoList"
0x1800e8718  mov     rcx, rbx; hModule
0x1800e871b  call    cs:__imp_GetProcAddress
0x1800e8721  mov     r15, rax
0x1800e8724  mov     [rsp+188h+var_100], rax
0x1800e872c  mov     rcx, [rsp+188h]; this
0x1800e8734  test    rax, rax
0x1800e8737  jnz     short loc_1800E874A
0x1800e8739  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x1800e8740  mov     edx, 8Bh; void *
0x1800e8745  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800e874a  lea     rdx, aSetupdienumdev; "SetupDiEnumDeviceInfo"
0x1800e8751  mov     rcx, rbx; hModule
0x1800e8754  call    cs:__imp_GetProcAddress
0x1800e875a  mov     r13, rax
0x1800e875d  mov     rcx, [rsp+188h]; this
0x1800e8765  test    rax, rax
0x1800e8768  jnz     short loc_1800E877B
0x1800e876a  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x1800e8771  mov     edx, 8Dh; void *
0x1800e8776  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800e877b  lea     rdx, aSetupdigetdevi_0; "SetupDiGetDeviceInstanceIdW"
0x1800e8782  mov     rcx, rbx; hModule
0x1800e8785  call    cs:__imp_GetProcAddress
0x1800e878b  mov     [rsp+188h+EndPtr], rax
0x1800e8790  mov     rcx, [rsp+188h]; this
0x1800e8798  test    rax, rax
0x1800e879b  jnz     short loc_1800E87AE
0x1800e879d  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x1800e87a4  mov     edx, 8Fh; void *
0x1800e87a9  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800e87ae  lea     rdx, aSetupdigetdevi; "SetupDiGetDevicePropertyW"
0x1800e87b5  mov     rcx, rbx; hModule
0x1800e87b8  call    cs:__imp_GetProcAddress
0x1800e87be  mov     [rsp+188h+var_E0], rax
0x1800e87c6  mov     rcx, [rsp+188h]; this
0x1800e87ce  test    rax, rax
0x1800e87d1  jnz     short loc_1800E87E4
0x1800e87d3  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x1800e87da  mov     edx, 91h; void *
0x1800e87df  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800e87e4  mov     rdx, rsi
0x1800e87e7  lea     rcx, [rsp+188h+lpString1]
0x1800e87ef  call    ?HardwareIdToVendorProductString@npu_detection@udk@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBUDXCoreHardwareIDParts@@@Z; udk::npu_detection::HardwareIdToVendorProductString(DXCoreHardwareIDParts const &)
0x1800e87f4  nop
0x1800e87f5  mov     [rsp+188h+var_D8], 0F01A9D53h
0x1800e8800  mov     [rsp+188h+var_D4], 48D23FF6h
0x1800e880b  mov     [rsp+188h+var_D0], 0A7C8979Fh
0x1800e8816  mov     ebx, 0C8h
0x1800e881b  xor     esi, esi
0x1800e881d  mov     [rsp+188h+var_CC], 0CE14B00h
0x1800e8828  lea     r9d, [rsi+2]
0x1800e882c  xor     r8d, r8d
0x1800e882f  xor     edx, edx
0x1800e8831  lea     rcx, [rsp+188h+var_D8]
0x1800e8839  mov     rax, r14
0x1800e883c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e8841  mov     r12, rax
0x1800e8844  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800e8848  jz      loc_1800E8C96
0x1800e884e  mov     [rsp+188h+var_F8], rax
0x1800e8856  mov     [rsp+188h+var_F0], r15
0x1800e885e  mov     [rsp+188h+var_E8], 1
0x1800e8866  xorps   xmm0, xmm0
0x1800e8869  movups  [rsp+188h+var_A8], xmm0
0x1800e8871  movups  [rsp+188h+var_98], xmm0
0x1800e8879  mov     dword ptr [rsp+188h+var_A8], 20h ; ' '
0x1800e8884  mov     r14d, esi
0x1800e8887  lea     r8, [rsp+188h+var_A8]
0x1800e888f  mov     edx, r14d
0x1800e8892  mov     rcx, r12
0x1800e8895  mov     rax, r13
0x1800e8898  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e889d  test    eax, eax
0x1800e889f  jz      loc_1800E8C63
0x1800e88a5  lea     rcx, [rsp+188h+var_138]; void *
0x1800e88aa  call    ??0?$vector@Uunique_ptr_bytes_buffer@@V?$allocator@Uunique_ptr_bytes_buffer@@@std@@@std@@QEAA@XZ; std::vector<unique_ptr_bytes_buffer>::vector<unique_ptr_bytes_buffer>(void)
0x1800e88af  nop
0x1800e88b0  mov     rdx, [rsp+188h+var_138]
0x1800e88b5  mov     rsi, [rsp+188h+var_138+8]
0x1800e88ba  mov     rcx, rsi
0x1800e88bd  sub     rcx, rdx
0x1800e88c0  sar     rcx, 1
0x1800e88c3  cmp     rcx, rbx
0x1800e88c6  jbe     short loc_1800E88D1
0x1800e88c8  lea     rsi, [rdx+190h]
0x1800e88cf  jmp     short loc_1800E890E
0x1800e88d1  jnb     short loc_1800E8913
0x1800e88d3  mov     rax, [rsp+188h+var_128]
0x1800e88d8  sub     rax, rdx
0x1800e88db  sar     rax, 1
0x1800e88de  cmp     rax, rbx
0x1800e88e1  jnb     short loc_1800E88F4
0x1800e88e3  lea     rcx, [rsp+188h+var_138]
0x1800e88e8  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@_WV?$allocator@_W@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800e88ed  mov     rsi, [rsp+188h+var_138+8]
0x1800e88f2  jmp     short loc_1800E8913
0x1800e88f4  mov     rax, rbx
0x1800e88f7  sub     rax, rcx
0x1800e88fa  lea     rbx, [rax+rax]
0x1800e88fe  mov     r8, rbx; Size
0x1800e8901  xor     edx, edx; Val
0x1800e8903  mov     rcx, rsi; void *
0x1800e8906  call    memset_0
0x1800e890b  add     rsi, rbx
0x1800e890e  mov     [rsp+188h+var_138+8], rsi
0x1800e8913  mov     r8, [rsp+188h+var_138]
0x1800e8918  sub     rsi, r8
0x1800e891b  sar     rsi, 1
0x1800e891e  mov     qword ptr [rsp+188h+bIgnoreCase], 0
0x1800e8927  mov     r9d, esi
0x1800e892a  lea     rdx, [rsp+188h+var_A8]
0x1800e8932  mov     rcx, r12
0x1800e8935  mov     rax, [rsp+188h+EndPtr]
0x1800e893a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e893f  mov     rcx, [rsp+188h]; this
0x1800e8947  xor     esi, esi
0x1800e8949  test    eax, eax
0x1800e894b  jnz     short loc_1800E895E
0x1800e894d  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x1800e8954  mov     edx, 0ABh; void *
0x1800e8959  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800e895e  xor     r8d, r8d
0x1800e8961  mov     rdx, [rsp+188h+var_138+8]
0x1800e8966  mov     rcx, [rsp+188h+var_138]
0x1800e896b  call    __std_find_trivial_2
0x1800e8970  mov     rbx, rax
0x1800e8973  mov     r8d, 5Ch ; '\'
0x1800e8979  mov     rdx, rax
0x1800e897c  mov     rcx, [rsp+188h+var_138]
0x1800e8981  call    __std_find_trivial_2
0x1800e8986  cmp     rax, [rsp+188h+var_138+8]
0x1800e898b  jz      loc_1800E8C35
0x1800e8991  cmp     rbx, [rsp+188h+var_138+8]
0x1800e8996  jz      loc_1800E8C35
0x1800e899c  lea     rcx, [rax+2]
0x1800e89a0  cmp     rcx, rbx
0x1800e89a3  jz      loc_1800E8C35
0x1800e89a9  sub     rbx, rcx
0x1800e89ac  sar     rbx, 1
0x1800e89af  mov     rdx, qword ptr [rsp+188h+cchCount2]; cchCount1
0x1800e89b7  cmp     rbx, rdx
0x1800e89ba  jb      loc_1800E8C35
0x1800e89c0  mov     rax, [rsp+188h+var_138]
0x1800e89c5  sub     rcx, rax
0x1800e89c8  sar     rcx, 1
0x1800e89cb  lea     r8, [rax+rcx*2]; lpString2
0x1800e89cf  lea     rcx, [rsp+188h+lpString1]
0x1800e89d7  cmp     [rsp+188h+var_B0], 7
0x1800e89e0  cmova   rcx, [rsp+188h+lpString1]; lpString1
0x1800e89e9  mov     [rsp+188h+bIgnoreCase], 1; bIgnoreCase
0x1800e89f1  mov     r9d, edx; cchCount2
0x1800e89f4  call    cs:__imp_CompareStringOrdinal
0x1800e89fa  cmp     eax, 2
0x1800e89fd  jnz     loc_1800E8C35
0x1800e8a03  mov     [rsp+188h+var_118], esi
0x1800e8a07  mov     [rsp+188h+var_150], esi
0x1800e8a0b  mov     [rsp+188h+var_158], rsi
0x1800e8a10  mov     [rsp+188h+var_160], 30h ; '0'
0x1800e8a18  lea     rax, [rsp+188h+var_68]
0x1800e8a20  mov     qword ptr [rsp+188h+bIgnoreCase], rax; int
0x1800e8a25  lea     r9, [rsp+188h+var_118]
0x1800e8a2a  lea     r8, DEVPKEY_Device_DriverVersion
0x1800e8a31  lea     rdx, [rsp+188h+var_A8]
0x1800e8a39  mov     rcx, r12
0x1800e8a3c  mov     rax, [rsp+188h+var_E0]
0x1800e8a44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e8a49  mov     rcx, [rsp+188h]; this
0x1800e8a51  test    eax, eax
0x1800e8a53  jnz     short loc_1800E8A66
0x1800e8a55  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x1800e8a5c  mov     edx, 0C2h; void *
0x1800e8a61  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800e8a66  mov     rax, rsi
0x1800e8a69  mov     [rsp+188h+var_E0], rax
0x1800e8a71  xor     r14d, r14d
0x1800e8a74  mov     ebx, r14d
0x1800e8a77  cmp     rbx, 4
0x1800e8a7b  jnb     loc_1800E8BB2
0x1800e8a81  mov     rcx, [rsp+188h]; this
0x1800e8a89  cmp     rsi, 18h
0x1800e8a8d  jb      short loc_1800E8AA6
0x1800e8a8f  mov     r9d, 80070057h; char *
0x1800e8a95  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x1800e8a9c  mov     edx, 0CBh; void *
0x1800e8aa1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e8aa6  lea     rdx, [rsp+188h+var_68]
0x1800e8aae  lea     rdx, [rdx+rsi*2]
0x1800e8ab2  lea     rcx, [rsp+188h+String]
0x1800e8aba  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800e8abf  nop
0x1800e8ac0  call    cs:__imp__o__errno
0x1800e8ac6  mov     r13, rax
0x1800e8ac9  lea     r15, [rsp+188h+String]
0x1800e8ad1  cmp     [rsp+188h+var_70], 7
0x1800e8ada  cmova   r15, [rsp+188h+String]
0x1800e8ae3  mov     [rsp+188h+EndPtr], r14
0x1800e8ae8  mov     [rax], r14d
0x1800e8aeb  mov     r8d, 0Ah; Radix
0x1800e8af1  lea     rdx, [rsp+188h+EndPtr]; EndPtr
0x1800e8af6  mov     rcx, r15; String
0x1800e8af9  call    cs:__imp_wcstol
0x1800e8aff  mov     r14, [rsp+188h+EndPtr]
0x1800e8b04  cmp     r15, r14
0x1800e8b07  jnz     short loc_1800E8B16
0x1800e8b09  lea     rcx, aInvalidStoiArg; "invalid stoi argument"
0x1800e8b10  call    cs:__imp_?_Xinvalid_argument@std@@YAXPEBD@Z; std::_Xinvalid_argument(char const *)
0x1800e8b16  cmp     dword ptr [r13+0], 22h ; '"'
0x1800e8b1b  jnz     short loc_1800E8B2A
0x1800e8b1d  lea     rcx, aStoiArgumentOu; "stoi argument out of range"
0x1800e8b24  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x1800e8b2a  sub     r14, r15
0x1800e8b2d  sar     r14, 1
0x1800e8b30  mov     word ptr [rsp+rbx*2+188h+var_E0], ax
0x1800e8b38  lea     rcx, [rsp+188h+String]; this
0x1800e8b40  call    ??1ReIndexPatternInfo@@QEAA@XZ; ReIndexPatternInfo::~ReIndexPatternInfo(void)
0x1800e8b45  lea     rdx, [r14+rsi]
0x1800e8b49  movzx   eax, [rsp+rdx*2+188h+var_68]
0x1800e8b51  mov     rcx, [rsp+188h]; this
0x1800e8b59  cmp     rbx, 3
0x1800e8b5d  jz      short loc_1800E8B93
0x1800e8b5f  cmp     ax, 2Eh ; '.'
0x1800e8b63  jz      short loc_1800E8B7C
0x1800e8b65  mov     r9d, 80070057h; char *
0x1800e8b6b  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x1800e8b72  mov     edx, 0D3h; void *
0x1800e8b77  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e8b7c  lea     rsi, [rdx+1]
0x1800e8b80  xor     r14d, r14d
0x1800e8b83  inc     rbx
0x1800e8b86  mov     rax, [rsp+188h+var_E0]
0x1800e8b8e  jmp     loc_1800E8A77
0x1800e8b93  xor     r14d, r14d
0x1800e8b96  test    ax, ax
0x1800e8b99  jz      short loc_1800E8B83
0x1800e8b9b  mov     r9d, 80070057h; char *
0x1800e8ba1  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x1800e8ba8  mov     edx, 0DBh; void *
0x1800e8bad  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e8bb2  movzx   ecx, word ptr [rsp+188h+var_E0+6]
0x1800e8bba  mov     [rdi], cx
0x1800e8bbd  movzx   ecx, word ptr [rsp+188h+var_E0+4]
0x1800e8bc5  mov     [rdi+2], cx
0x1800e8bc9  movzx   ecx, word ptr [rsp+188h+var_E0+2]
0x1800e8bd1  mov     [rdi+4], cx
0x1800e8bd5  mov     [rdi+6], ax
0x1800e8bd9  mov     rcx, [rsp+188h+var_138]
0x1800e8bde  test    rcx, rcx
0x1800e8be1  jz      short loc_1800E8C04
0x1800e8be3  mov     rdx, [rsp+188h+var_128]
0x1800e8be8  sub     rdx, rcx
0x1800e8beb  sar     rdx, 1
0x1800e8bee  add     rdx, rdx
0x1800e8bf1  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800e8bf6  xorps   xmm0, xmm0
0x1800e8bf9  movdqu  xmmword ptr [rsp+188h+var_138], xmm0
0x1800e8bff  mov     [rsp+188h+var_128], r14
0x1800e8c04  mov     rcx, r12
0x1800e8c07  mov     rax, [rsp+188h+var_100]
0x1800e8c0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e8c14  nop
0x1800e8c15  lea     rcx, [rsp+188h+lpString1]; this
0x1800e8c1d  call    ??1ReIndexPatternInfo@@QEAA@XZ; ReIndexPatternInfo::~ReIndexPatternInfo(void)
0x1800e8c22  nop
  ... truncated ...
```
