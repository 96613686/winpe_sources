# udk::CopilotPlusDetection::details::QueryDriverVersionUsingSetupDi(DXCoreHardwareIDParts const &)

- ea: `0x14009e378`
- end: `0x14009e9ac`
- name: `?QueryDriverVersionUsingSetupDi@details@CopilotPlusDetection@udk@@YA@AEBUDXCoreHardwareIDParts@@@Z`
- size: `1588`
- prototype: `__int64 __fastcall(udk::CopilotPlusDetection::details *__hidden this, const struct DXCoreHardwareIDParts *)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14017a68c`
- `0x14017a86c`

## callees

- `0x140006edc`
- `0x14000d980`
- `0x14000dc10`
- `0x140067e90`
- `0x14009d028`
- `0x14009e378`
- `0x14009ece4`
- `0x1400a87d4`
- `0x1400e2020`
- `0x14010e160`
- `0x140120110`
- `0x1401413f4`
- `0x140147e2c`
- `0x140193b50`
- `0x1401d9010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14009e3cd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14009e3cd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14009e3fc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14009e433`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14009e46a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14009e4a1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14009e4dd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14009e3fc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14009e433`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14009e46a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14009e4a1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14009e4dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14009e902`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14009e902`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14009e6ea`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14009e6ea`

## string_xrefs

- `0x14009e3c6`: `setupapi.dll`

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
  FARPROC v12; // r12
  const char *v13; // r9
  const char *v14; // r9
  FARPROC v15; // r13
  __int64 v16; // rax
  __int64 v17; // r14
  unsigned int i; // esi
  const char *v19; // r9
  __int64 v20; // rbx
  __int64 v21; // rax
  const WCHAR *v22; // rcx
  const char *v23; // r9
  __int16 v24; // ax
  unsigned __int64 v25; // rbx
  unsigned __int64 j; // rsi
  __int64 v27; // rbx
  const char *v29; // r9
  int v30; // [rsp+50h] [rbp-138h] BYREF
  __int64 v31; // [rsp+58h] [rbp-130h] BYREF
  __int128 v32; // [rsp+60h] [rbp-128h] BYREF
  __int64 v33; // [rsp+70h] [rbp-118h]
  _QWORD v34[2]; // [rsp+78h] [rbp-110h] BYREF
  _QWORD v35[3]; // [rsp+88h] [rbp-100h] BYREF
  char v36; // [rsp+A0h] [rbp-E8h]
  FARPROC v37; // [rsp+A8h] [rbp-E0h]
  _DWORD v38[4]; // [rsp+B0h] [rbp-D8h] BYREF
  LPCWCH lpString1[2]; // [rsp+C0h] [rbp-C8h] BYREF
  int cchCount2[2]; // [rsp+D0h] [rbp-B8h]
  unsigned __int64 v41; // [rsp+D8h] [rbp-B0h]
  _OWORD v42[2]; // [rsp+E0h] [rbp-A8h] BYREF
  wchar_t String[16]; // [rsp+100h] [rbp-88h] BYREF
  _WORD v44[24]; // [rsp+120h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]

  v34[1] = this;
  udk::CopilotPlusDetection::HardwareRequirementsTelemetry::NpuDriverVersionFallbackUsed<unsigned int const &,unsigned int const &>(
    a2,
    (char *)a2 + 4);
  Library = LoadLibraryExW(L"setupapi.dll", 0, 0x800u);
  v6 = Library;
  v34[0] = Library;
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
  v37 = GetProcAddress(v6, "SetupDiGetDeviceInstanceIdW");
  if ( !v37 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x8F,
      (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
      v13);
  v15 = GetProcAddress(v6, "SetupDiGetDevicePropertyW");
  if ( !v15 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x91,
      (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
      v14);
  udk::npu_detection::HardwareIdToVendorProductString(lpString1, a2);
  v38[0] = -266691245;
  v38[1] = 1221738486;
  v38[2] = -1480026209;
  v38[3] = 216091392;
  v16 = ((__int64 (__fastcall *)(_DWORD *, _QWORD, _QWORD, __int64))ProcAddress)(v38, 0, 0, 2);
  v17 = v16;
  if ( v16 != -1 )
  {
    v35[1] = v16;
    v35[2] = v10;
    v36 = 1;
    memset(v42, 0, sizeof(v42));
    LODWORD(v42[0]) = 32;
    for ( i = 0; ((unsigned int (__fastcall *)(__int64, _QWORD, _OWORD *))v12)(v17, i, v42); ++i )
    {
      v32 = 0;
      v33 = 0;
      std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(&v32);
      if ( !((unsigned int (__fastcall *)(__int64, _OWORD *, _QWORD, __int64, _QWORD))v37)(
              v17,
              v42,
              v32,
              (__int64)(*((_QWORD *)&v32 + 1) - v32) >> 1,
              0) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0xAB,
          (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
          v19);
      LOWORD(v30) = 0;
      std::find<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<unsigned short>>>,unsigned short>(
        v35,
        v32,
        *((_QWORD *)&v32 + 1),
        &v30);
      LOWORD(v30) = 92;
      v20 = v35[0];
      std::find<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<unsigned short>>>,unsigned short>(
        &v31,
        v32,
        v35[0],
        &v30);
      if ( v31 != *((_QWORD *)&v32 + 1) && v20 != *((_QWORD *)&v32 + 1) )
      {
        v21 = v31 + 2;
        v31 = v21;
        if ( v21 != v20 && (unsigned __int64)((v20 - v21) >> 1) >= *(_QWORD *)cchCount2 )
        {
          v22 = (const WCHAR *)lpString1;
          if ( v41 > 7 )
            v22 = lpString1[0];
          if ( CompareStringOrdinal(v22, cchCount2[0], (LPCWCH)(v32 + 2 * ((v21 - (__int64)v32) >> 1)), cchCount2[0], 1) == 2 )
          {
            v30 = 0;
            if ( !((unsigned int (__fastcall *)(__int64, _OWORD *, const DEVPROPKEY *, int *))v15)(
                    v17,
                    v42,
                    &DEVPKEY_Device_DriverVersion,
                    &v30) )
              wil::details::in1diag3::Throw_GetLastError(
                retaddr,
                (void *)0xC2,
                (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
                v23);
            v24 = 0;
            v37 = 0;
            v25 = 0;
            for ( j = 0; j < 4; ++j )
            {
              if ( v25 >= 0x18 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0xCB,
                  (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
                  (const char *)0x80070057LL,
                  (int)v44);
              v31 = 0;
              std::wstring::wstring(String, &v44[v25]);
              *((_WORD *)&v38[-2] + j) = std::stoi(String);
              std::wstring::~wstring(String);
              if ( j == 3 )
              {
                if ( v44[v25 + v31] )
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0xDB,
                    (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
                    (const char *)0x80070057LL,
                    (int)v44);
              }
              else
              {
                v27 = v31 + v25;
                if ( v44[v27] != 46 )
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0xD3,
                    (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
                    (const char *)0x80070057LL,
                    (int)v44);
                v25 = v27 + 1;
              }
              v24 = (__int16)v37;
            }
            *(_WORD *)this = HIWORD(v37);
            *((_WORD *)this + 1) = WORD2(v37);
            *((_WORD *)this + 2) = WORD1(v37);
            *((_WORD *)this + 3) = v24;
            if ( (_QWORD)v32 )
            {
              std::_Deallocate<16>(v32, 2 * ((v33 - (__int64)v32) >> 1));
              v32 = 0;
              v33 = 0;
            }
            ((void (__fastcall *)(__int64))v10)(v17);
            std::wstring::~wstring(lpString1);
            wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(v34);
            return this;
          }
        }
      }
      if ( (_QWORD)v32 )
        std::_Deallocate<16>(v32, 2 * ((v33 - (__int64)v32) >> 1));
    }
    if ( GetLastError() != 259 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xE5,
        (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
        v29);
    ((void (__fastcall *)(__int64))v10)(v17);
  }
  udk::CopilotPlusDetection::HardwareRequirementsTelemetry::NpuDriverVersionFallbackFailed();
  *(_QWORD *)this = 0;
  std::wstring::~wstring(lpString1);
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(v34);
  return this;
}

```

## disassembly

```asm
0x14009e378  mov     [rsp+arg_10], rbx
0x14009e37d  mov     [rsp+arg_18], rsi
0x14009e382  push    rdi
0x14009e383  push    r12
0x14009e385  push    r13
0x14009e387  push    r14
0x14009e389  push    r15
0x14009e38b  sub     rsp, 160h
0x14009e392  mov     rax, cs:__security_cookie
0x14009e399  xor     rax, rsp
0x14009e39c  mov     [rsp+188h+var_38], rax
0x14009e3a4  mov     rsi, rdx
0x14009e3a7  mov     rdi, rcx
0x14009e3aa  mov     [rsp+188h+var_108], rcx
0x14009e3b2  add     rdx, 4
0x14009e3b6  mov     rcx, rsi
0x14009e3b9  call    ??$NpuDriverVersionFallbackUsed@AEBIAEBI@HardwareRequirementsTelemetry@CopilotPlusDetection@udk@@SAXAEBI0@Z; udk::CopilotPlusDetection::HardwareRequirementsTelemetry::NpuDriverVersionFallbackUsed<uint const &,uint const &>(uint const &,uint const &)
0x14009e3be  xor     edx, edx; hFile
0x14009e3c0  mov     r8d, 800h; dwFlags
0x14009e3c6  lea     rcx, aSetupapiDll; "setupapi.dll"
0x14009e3cd  call    cs:__imp_LoadLibraryExW
0x14009e3d4  nop     dword ptr [rax+rax+00h]
0x14009e3d9  mov     rbx, rax
0x14009e3dc  mov     [rsp+188h+var_110], rax
0x14009e3e1  mov     rcx, [rsp+188h]; this
0x14009e3e9  test    rax, rax
0x14009e3ec  jz      loc_14009E964
0x14009e3f2  lea     rdx, aSetupdigetclas; "SetupDiGetClassDevsW"
0x14009e3f9  mov     rcx, rax; hModule
0x14009e3fc  call    cs:__imp_GetProcAddress
0x14009e403  nop     dword ptr [rax+rax+00h]
0x14009e408  mov     r14, rax
0x14009e40b  mov     rcx, [rsp+188h]; this
0x14009e413  test    rax, rax
0x14009e416  jnz     short loc_14009E429
0x14009e418  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x14009e41f  mov     edx, 89h; void *
0x14009e424  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14009e429  lea     rdx, aSetupdidestroy; "SetupDiDestroyDeviceInfoList"
0x14009e430  mov     rcx, rbx; hModule
0x14009e433  call    cs:__imp_GetProcAddress
0x14009e43a  nop     dword ptr [rax+rax+00h]
0x14009e43f  mov     r15, rax
0x14009e442  mov     rcx, [rsp+188h]; this
0x14009e44a  test    rax, rax
0x14009e44d  jnz     short loc_14009E460
0x14009e44f  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x14009e456  mov     edx, 8Bh; void *
0x14009e45b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14009e460  lea     rdx, aSetupdienumdev; "SetupDiEnumDeviceInfo"
0x14009e467  mov     rcx, rbx; hModule
0x14009e46a  call    cs:__imp_GetProcAddress
0x14009e471  nop     dword ptr [rax+rax+00h]
0x14009e476  mov     r12, rax
0x14009e479  mov     rcx, [rsp+188h]; this
0x14009e481  test    rax, rax
0x14009e484  jnz     short loc_14009E497
0x14009e486  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x14009e48d  mov     edx, 8Dh; void *
0x14009e492  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14009e497  lea     rdx, aSetupdigetdevi_0; "SetupDiGetDeviceInstanceIdW"
0x14009e49e  mov     rcx, rbx; hModule
0x14009e4a1  call    cs:__imp_GetProcAddress
0x14009e4a8  nop     dword ptr [rax+rax+00h]
0x14009e4ad  mov     [rsp+188h+var_E0], rax
0x14009e4b5  mov     rcx, [rsp+188h]; this
0x14009e4bd  test    rax, rax
0x14009e4c0  jnz     short loc_14009E4D3
0x14009e4c2  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x14009e4c9  mov     edx, 8Fh; void *
0x14009e4ce  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14009e4d3  lea     rdx, aSetupdigetdevi; "SetupDiGetDevicePropertyW"
0x14009e4da  mov     rcx, rbx; hModule
0x14009e4dd  call    cs:__imp_GetProcAddress
0x14009e4e4  nop     dword ptr [rax+rax+00h]
0x14009e4e9  mov     r13, rax
0x14009e4ec  mov     rcx, [rsp+188h]; this
0x14009e4f4  xor     ebx, ebx
0x14009e4f6  test    rax, rax
0x14009e4f9  jnz     short loc_14009E50C
0x14009e4fb  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x14009e502  mov     edx, 91h; void *
0x14009e507  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14009e50c  mov     rdx, rsi
0x14009e50f  lea     rcx, [rsp+188h+lpString1]
0x14009e517  call    ?HardwareIdToVendorProductString@npu_detection@udk@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBUDXCoreHardwareIDParts@@@Z; udk::npu_detection::HardwareIdToVendorProductString(DXCoreHardwareIDParts const &)
0x14009e51c  nop
0x14009e51d  mov     [rsp+188h+var_D8], 0F01A9D53h
0x14009e528  mov     [rsp+188h+var_D4], 48D23FF6h
0x14009e533  mov     [rsp+188h+var_D0], 0A7C8979Fh
0x14009e53e  mov     [rsp+188h+var_CC], 0CE14B00h
0x14009e549  mov     r9d, 2
0x14009e54f  xor     r8d, r8d
0x14009e552  xor     edx, edx
0x14009e554  lea     rcx, [rsp+188h+var_D8]
0x14009e55c  mov     rax, r14
0x14009e55f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009e564  mov     r14, rax
0x14009e567  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14009e56b  jz      loc_14009E93B
0x14009e571  mov     [rsp+188h+var_F8], rax
0x14009e579  mov     [rsp+188h+var_F0], r15
0x14009e581  mov     [rsp+188h+var_E8], 1
0x14009e589  xorps   xmm0, xmm0
0x14009e58c  movups  [rsp+188h+var_A8], xmm0
0x14009e594  movups  [rsp+188h+var_98], xmm0
0x14009e59c  mov     dword ptr [rsp+188h+var_A8], 20h ; ' '
0x14009e5a7  mov     esi, ebx
0x14009e5a9  lea     r8, [rsp+188h+var_A8]
0x14009e5b1  mov     edx, esi
0x14009e5b3  mov     rcx, r14
0x14009e5b6  mov     rax, r12
0x14009e5b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009e5be  test    eax, eax
0x14009e5c0  jz      loc_14009E902
0x14009e5c6  xorps   xmm0, xmm0
0x14009e5c9  movdqu  [rsp+188h+var_128], xmm0
0x14009e5cf  mov     [rsp+188h+var_118], rbx
0x14009e5d4  lea     rcx, [rsp+188h+var_128]
0x14009e5d9  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x14009e5de  mov     r8, qword ptr [rsp+188h+var_128]
0x14009e5e3  mov     r9, qword ptr [rsp+188h+var_128+8]
0x14009e5e8  sub     r9, r8
0x14009e5eb  sar     r9, 1
0x14009e5ee  mov     qword ptr [rsp+188h+bIgnoreCase], rbx
0x14009e5f3  lea     rdx, [rsp+188h+var_A8]
0x14009e5fb  mov     rcx, r14
0x14009e5fe  mov     rax, [rsp+188h+var_E0]
0x14009e606  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009e60b  mov     rcx, [rsp+188h]; this
0x14009e613  test    eax, eax
0x14009e615  jnz     short loc_14009E628
0x14009e617  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x14009e61e  mov     edx, 0ABh; void *
0x14009e623  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14009e628  mov     word ptr [rsp+188h+var_138], bx
0x14009e62d  lea     r9, [rsp+188h+var_138]
0x14009e632  mov     r8, qword ptr [rsp+188h+var_128+8]
0x14009e637  mov     rdx, qword ptr [rsp+188h+var_128]
0x14009e63c  lea     rcx, [rsp+188h+var_100]
0x14009e644  call    ??$find@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@G@std@@@std@@@std@@G@std@@YA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@G@std@@@std@@@0@V10@V10@AEBG@Z; std::find<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ushort>>>,ushort>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ushort>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ushort>>>,ushort const &)
0x14009e649  mov     eax, 5Ch ; '\'
0x14009e64e  mov     word ptr [rsp+188h+var_138], ax
0x14009e653  mov     rbx, [rsp+188h+var_100]
0x14009e65b  lea     r9, [rsp+188h+var_138]
0x14009e660  mov     r8, rbx
0x14009e663  mov     rdx, qword ptr [rsp+188h+var_128]
0x14009e668  lea     rcx, [rsp+188h+var_130]
0x14009e66d  call    ??$find@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@G@std@@@std@@@std@@G@std@@YA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@G@std@@@std@@@0@V10@V10@AEBG@Z; std::find<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ushort>>>,ushort>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ushort>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ushort>>>,ushort const &)
0x14009e672  mov     rax, [rsp+188h+var_130]
0x14009e677  cmp     rax, qword ptr [rsp+188h+var_128+8]
0x14009e67c  jz      loc_14009E8D8
0x14009e682  cmp     rbx, qword ptr [rsp+188h+var_128+8]
0x14009e687  jz      loc_14009E8D8
0x14009e68d  add     rax, 2
0x14009e691  mov     [rsp+188h+var_130], rax
0x14009e696  cmp     rax, rbx
0x14009e699  jz      loc_14009E8D8
0x14009e69f  sub     rbx, rax
0x14009e6a2  sar     rbx, 1
0x14009e6a5  mov     rdx, qword ptr [rsp+188h+cchCount2]; cchCount1
0x14009e6ad  cmp     rbx, rdx
0x14009e6b0  jb      loc_14009E8D8
0x14009e6b6  mov     rcx, qword ptr [rsp+188h+var_128]
0x14009e6bb  sub     rax, rcx
0x14009e6be  sar     rax, 1
0x14009e6c1  lea     r8, [rcx+rax*2]; lpString2
0x14009e6c5  lea     rcx, [rsp+188h+lpString1]
0x14009e6cd  cmp     [rsp+188h+var_B0], 7
0x14009e6d6  cmova   rcx, [rsp+188h+lpString1]; lpString1
0x14009e6df  mov     [rsp+188h+bIgnoreCase], 1; bIgnoreCase
0x14009e6e7  mov     r9d, edx; cchCount2
0x14009e6ea  call    cs:__imp_CompareStringOrdinal
0x14009e6f1  nop     dword ptr [rax+rax+00h]
0x14009e6f6  cmp     eax, 2
0x14009e6f9  jnz     loc_14009E8D8
0x14009e6ff  xor     r12d, r12d
0x14009e702  mov     [rsp+188h+var_138], r12d
0x14009e707  mov     [rsp+188h+var_150], r12d
0x14009e70c  mov     [rsp+188h+var_158], r12
0x14009e711  mov     [rsp+188h+var_160], 30h ; '0'
0x14009e719  lea     rax, [rsp+188h+var_68]
0x14009e721  mov     qword ptr [rsp+188h+bIgnoreCase], rax; int
0x14009e726  lea     r9, [rsp+188h+var_138]
0x14009e72b  lea     r8, DEVPKEY_Device_DriverVersion
0x14009e732  lea     rdx, [rsp+188h+var_A8]
0x14009e73a  mov     rcx, r14
0x14009e73d  mov     rax, r13
0x14009e740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009e745  mov     rcx, [rsp+188h]; this
0x14009e74d  test    eax, eax
0x14009e74f  jnz     short loc_14009E762
0x14009e751  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x14009e758  mov     edx, 0C2h; void *
0x14009e75d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14009e762  mov     rax, r12
0x14009e765  mov     [rsp+188h+var_E0], rax
0x14009e76d  mov     rbx, r12
0x14009e770  mov     rsi, r12
0x14009e773  cmp     rsi, 4
0x14009e777  jnb     loc_14009E85A
0x14009e77d  mov     rcx, [rsp+188h]; this
0x14009e785  cmp     rbx, 18h
0x14009e789  jb      short loc_14009E7A2
0x14009e78b  mov     r9d, 80070057h; char *
0x14009e791  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x14009e798  mov     edx, 0CBh; void *
0x14009e79d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009e7a2  mov     [rsp+188h+var_130], r12
0x14009e7a7  lea     rdx, [rsp+188h+var_68]
0x14009e7af  lea     rdx, [rdx+rbx*2]
0x14009e7b3  lea     rcx, [rsp+188h+String]
0x14009e7bb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14009e7c0  nop
0x14009e7c1  lea     rdx, [rsp+188h+var_130]
0x14009e7c6  lea     rcx, [rsp+188h+String]; String
0x14009e7ce  call    ?stoi@std@@YAHAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@PEA_KH@Z; std::stoi(std::wstring const &,unsigned __int64 *,int)
0x14009e7d3  mov     word ptr [rsp+rsi*2+188h+var_E0], ax
0x14009e7db  lea     rcx, [rsp+188h+String]; void *
0x14009e7e3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14009e7e8  mov     rcx, [rsp+188h]; this
0x14009e7f0  cmp     rsi, 3
0x14009e7f4  jz      short loc_14009E830
0x14009e7f6  add     rbx, [rsp+188h+var_130]
0x14009e7fb  cmp     [rsp+rbx*2+188h+var_68], 2Eh ; '.'
0x14009e804  jz      short loc_14009E81D
0x14009e806  mov     r9d, 80070057h; char *
0x14009e80c  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x14009e813  mov     edx, 0D3h; void *
0x14009e818  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009e81d  inc     rbx
0x14009e820  inc     rsi
0x14009e823  mov     rax, [rsp+188h+var_E0]
0x14009e82b  jmp     loc_14009E773
0x14009e830  mov     rdx, [rsp+188h+var_130]
0x14009e835  add     rdx, rbx
0x14009e838  cmp     [rsp+rdx*2+188h+var_68], r12w
0x14009e841  jz      short loc_14009E820
0x14009e843  mov     r9d, 80070057h; char *
0x14009e849  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x14009e850  mov     edx, 0DBh; void *
0x14009e855  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009e85a  movzx   ecx, word ptr [rsp+188h+var_E0+6]
0x14009e862  mov     [rdi], cx
0x14009e865  movzx   ecx, word ptr [rsp+188h+var_E0+4]
0x14009e86d  mov     [rdi+2], cx
0x14009e871  movzx   ecx, word ptr [rsp+188h+var_E0+2]
0x14009e879  mov     [rdi+4], cx
0x14009e87d  mov     [rdi+6], ax
0x14009e881  mov     rcx, qword ptr [rsp+188h+var_128]
0x14009e886  test    rcx, rcx
0x14009e889  jz      short loc_14009E8AC
0x14009e88b  mov     rdx, [rsp+188h+var_118]
0x14009e890  sub     rdx, rcx
0x14009e893  sar     rdx, 1
0x14009e896  add     rdx, rdx
0x14009e899  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x14009e89e  xorps   xmm0, xmm0
0x14009e8a1  movdqu  [rsp+188h+var_128], xmm0
0x14009e8a7  mov     [rsp+188h+var_118], r12
0x14009e8ac  mov     rcx, r14
0x14009e8af  mov     rax, r15
0x14009e8b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009e8b7  nop
0x14009e8b8  lea     rcx, [rsp+188h+lpString1]; void *
0x14009e8c0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14009e8c5  nop
0x14009e8c6  lea     rcx, [rsp+188h+var_110]
0x14009e8cb  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x14009e8d0  mov     rax, rdi
0x14009e8d3  jmp     loc_14009E97E
0x14009e8d8  inc     esi
0x14009e8da  mov     rcx, qword ptr [rsp+188h+var_128]
0x14009e8df  xor     ebx, ebx
0x14009e8e1  test    rcx, rcx
0x14009e8e4  jz      loc_14009E5A9
0x14009e8ea  mov     rdx, [rsp+188h+var_118]
0x14009e8ef  sub     rdx, rcx
0x14009e8f2  sar     rdx, 1
0x14009e8f5  add     rdx, rdx
0x14009e8f8  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x14009e8fd  jmp     loc_14009E5A9
0x14009e902  call    cs:__imp_GetLastError
0x14009e909  nop     dword ptr [rax+rax+00h]
0x14009e90e  cmp     eax, 103h
0x14009e913  jz      short loc_14009E92F
0x14009e915  mov     rcx, [rsp+188h]; this
0x14009e91d  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x14009e924  mov     edx, 0E5h; void *
0x14009e929  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14009e92f  mov     rcx, r14
0x14009e932  mov     rax, r15
0x14009e935  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009e93a  nop
0x14009e93b  call    ?NpuDriverVersionFallbackFailed@HardwareRequirementsTelemetry@CopilotPlusDetection@udk@@SAXXZ; udk::CopilotPlusDetection::HardwareRequirementsTelemetry::NpuDriverVersionFallbackFailed(void)
0x14009e940  mov     qword ptr [rdi], 0
0x14009e947  lea     rcx, [rsp+188h+lpString1]; void *
0x14009e94f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14009e954  nop
0x14009e955  lea     rcx, [rsp+188h+var_110]
  ... truncated ...
```
