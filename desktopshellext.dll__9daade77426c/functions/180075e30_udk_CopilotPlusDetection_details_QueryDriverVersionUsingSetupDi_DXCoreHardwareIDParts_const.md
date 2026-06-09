# udk::CopilotPlusDetection::details::QueryDriverVersionUsingSetupDi(DXCoreHardwareIDParts const &)

- ea: `0x180075e30`
- end: `0x180076407`
- name: `?QueryDriverVersionUsingSetupDi@details@CopilotPlusDetection@udk@@YA@AEBUDXCoreHardwareIDParts@@@Z`
- size: `1495`
- prototype: `__int64 __fastcall(udk::CopilotPlusDetection::details *__hidden this, const struct DXCoreHardwareIDParts *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800746a0`

## callees

- `0x18000bdf0`
- `0x180015618`
- `0x18001a18c`
- `0x18001c240`
- `0x18001c608`
- `0x18002661c`
- `0x18002a3d0`
- `0x18002cbb0`
- `0x180034e40`
- `0x18006c938`
- `0x18006d9bc`
- `0x18006f800`
- `0x180075d98`
- `0x180075e30`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180075eae`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180075edf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180075f10`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180075f41`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180075f74`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180075eae`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180075edf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180075f10`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180075f41`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180075f74`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180075e85`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180075e85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076363`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076363`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180076151`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180076151`

## string_xrefs

- `0x180075e7e`: `setupapi.dll`

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
  __int64 trivial_2; // rbx
  __int64 v21; // rax
  __int64 v22; // rcx
  const WCHAR *v23; // r8
  const WCHAR *v24; // rcx
  const char *v25; // r9
  __int16 v26; // ax
  unsigned __int64 v27; // rbx
  unsigned __int64 j; // rsi
  const char *v30; // r9
  FARPROC v31; // [rsp+50h] [rbp-128h]
  __int128 v32; // [rsp+58h] [rbp-120h] BYREF
  __int64 v33; // [rsp+68h] [rbp-110h]
  int v34; // [rsp+70h] [rbp-108h] BYREF
  _QWORD v35[4]; // [rsp+78h] [rbp-100h] BYREF
  char v36; // [rsp+98h] [rbp-E0h]
  __int64 v37; // [rsp+A0h] [rbp-D8h]
  _DWORD v38[4]; // [rsp+A8h] [rbp-D0h] BYREF
  LPCWCH lpString1[2]; // [rsp+B8h] [rbp-C0h] BYREF
  int cchCount2[2]; // [rsp+C8h] [rbp-B0h]
  unsigned __int64 v41; // [rsp+D0h] [rbp-A8h]
  _OWORD v42[2]; // [rsp+D8h] [rbp-A0h] BYREF
  wchar_t String[16]; // [rsp+F8h] [rbp-80h] BYREF
  _WORD v44[24]; // [rsp+118h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+0h]

  v35[1] = this;
  udk::CopilotPlusDetection::HardwareRequirementsTelemetry::NpuDriverVersionFallbackUsed<unsigned int const &,unsigned int const &>(
    a2,
    (char *)a2 + 4);
  Library = LoadLibraryExW(L"setupapi.dll", 0, 0x800u);
  v6 = Library;
  v35[0] = Library;
  if ( !Library )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x86,
      (unsigned int)"OneCore\\Internal\\Shell\\inc\\CopilotPlusPCDetection.h",
      v5);
  ProcAddress = GetProcAddress(Library, "SetupDiGetClassDevsW");
  if ( !ProcAddress )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x89,
      (unsigned int)"OneCore\\Internal\\Shell\\inc\\CopilotPlusPCDetection.h",
      v7);
  v10 = GetProcAddress(v6, "SetupDiDestroyDeviceInfoList");
  if ( !v10 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x8B,
      (unsigned int)"OneCore\\Internal\\Shell\\inc\\CopilotPlusPCDetection.h",
      v9);
  v12 = GetProcAddress(v6, "SetupDiEnumDeviceInfo");
  if ( !v12 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x8D,
      (unsigned int)"OneCore\\Internal\\Shell\\inc\\CopilotPlusPCDetection.h",
      v11);
  v31 = GetProcAddress(v6, "SetupDiGetDeviceInstanceIdW");
  if ( !v31 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x8F,
      (unsigned int)"OneCore\\Internal\\Shell\\inc\\CopilotPlusPCDetection.h",
      v13);
  v15 = GetProcAddress(v6, "SetupDiGetDevicePropertyW");
  if ( !v15 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x91,
      (unsigned int)"OneCore\\Internal\\Shell\\inc\\CopilotPlusPCDetection.h",
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
    v35[2] = v16;
    v35[3] = v10;
    v36 = 1;
    memset(v42, 0, sizeof(v42));
    LODWORD(v42[0]) = 32;
    for ( i = 0; ((unsigned int (__fastcall *)(__int64, _QWORD, _OWORD *))v12)(v17, i, v42); ++i )
    {
      v32 = 0;
      v33 = 0;
      std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(&v32, 200);
      if ( !((unsigned int (__fastcall *)(__int64, _OWORD *, _QWORD, __int64, _QWORD))v31)(
              v17,
              v42,
              v32,
              (__int64)(*((_QWORD *)&v32 + 1) - v32) >> 1,
              0) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0xAB,
          (unsigned int)"OneCore\\Internal\\Shell\\inc\\CopilotPlusPCDetection.h",
          v19);
      trivial_2 = _std_find_trivial_2(v32, *((_QWORD *)&v32 + 1), 0);
      v21 = _std_find_trivial_2(v32, trivial_2, 92);
      if ( v21 != *((_QWORD *)&v32 + 1) && trivial_2 != *((_QWORD *)&v32 + 1) )
      {
        v22 = v21 + 2;
        if ( v21 + 2 != trivial_2 && (unsigned __int64)((trivial_2 - v22) >> 1) >= *(_QWORD *)cchCount2 )
        {
          v23 = (const WCHAR *)(v32 + 2 * ((v22 - (__int64)v32) >> 1));
          v24 = (const WCHAR *)lpString1;
          if ( v41 > 7 )
            v24 = lpString1[0];
          if ( CompareStringOrdinal(v24, cchCount2[0], v23, cchCount2[0], 1) == 2 )
          {
            v34 = 0;
            if ( !((unsigned int (__fastcall *)(__int64, _OWORD *, const DEVPROPKEY *, int *))v15)(
                    v17,
                    v42,
                    &DEVPKEY_Device_DriverVersion,
                    &v34) )
              wil::details::in1diag3::Throw_GetLastError(
                retaddr,
                (void *)0xC2,
                (unsigned int)"OneCore\\Internal\\Shell\\inc\\CopilotPlusPCDetection.h",
                v25);
            v26 = 0;
            v37 = 0;
            v27 = 0;
            for ( j = 0; j < 4; ++j )
            {
              if ( v27 >= 0x18 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0xCB,
                  (unsigned int)"OneCore\\Internal\\Shell\\inc\\CopilotPlusPCDetection.h",
                  (const char *)0x80070057LL,
                  (int)v44);
              std::wstring::wstring(String, &v44[v27]);
              *((_WORD *)&v38[-2] + j) = std::stoi(String);
              std::wstring::~wstring(String);
              if ( j == 3 )
              {
                if ( v44[v27] )
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0xDB,
                    (unsigned int)"OneCore\\Internal\\Shell\\inc\\CopilotPlusPCDetection.h",
                    (const char *)0x80070057LL,
                    (int)v44);
              }
              else
              {
                if ( v44[v27] != 46 )
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0xD3,
                    (unsigned int)"OneCore\\Internal\\Shell\\inc\\CopilotPlusPCDetection.h",
                    (const char *)0x80070057LL,
                    (int)v44);
                ++v27;
              }
              v26 = v37;
            }
            *(_WORD *)this = HIWORD(v37);
            *((_WORD *)this + 1) = WORD2(v37);
            *((_WORD *)this + 2) = WORD1(v37);
            *((_WORD *)this + 3) = v26;
            if ( (_QWORD)v32 )
            {
              std::_Deallocate<16>(v32, 2 * ((v33 - (__int64)v32) >> 1));
              v32 = 0;
              v33 = 0;
            }
            ((void (__fastcall *)(__int64))v10)(v17);
            std::wstring::~wstring(lpString1);
            wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(v35);
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
        (unsigned int)"OneCore\\Internal\\Shell\\inc\\CopilotPlusPCDetection.h",
        v30);
    ((void (__fastcall *)(__int64))v10)(v17);
  }
  udk::CopilotPlusDetection::HardwareRequirementsTelemetry::NpuDriverVersionFallbackFailed();
  *(_QWORD *)this = 0;
  std::wstring::~wstring(lpString1);
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(v35);
  return this;
}

```

## disassembly

```asm
0x180075e30  mov     [rsp+arg_10], rbx
0x180075e35  mov     [rsp+arg_18], rsi
0x180075e3a  push    rdi
0x180075e3b  push    r12
0x180075e3d  push    r13
0x180075e3f  push    r14
0x180075e41  push    r15
0x180075e43  sub     rsp, 150h
0x180075e4a  mov     rax, cs:__security_cookie
0x180075e51  xor     rax, rsp
0x180075e54  mov     [rsp+178h+var_30], rax
0x180075e5c  mov     rsi, rdx
0x180075e5f  mov     rdi, rcx
0x180075e62  mov     [rsp+178h+var_F8], rcx
0x180075e6a  add     rdx, 4
0x180075e6e  mov     rcx, rsi
0x180075e71  call    ??$NpuDriverVersionFallbackUsed@AEBIAEBI@HardwareRequirementsTelemetry@CopilotPlusDetection@udk@@SAXAEBI0@Z; udk::CopilotPlusDetection::HardwareRequirementsTelemetry::NpuDriverVersionFallbackUsed<uint const &,uint const &>(uint const &,uint const &)
0x180075e76  xor     edx, edx; hFile
0x180075e78  mov     r8d, 800h; dwFlags
0x180075e7e  lea     rcx, aSetupapiDll; "setupapi.dll"
0x180075e85  call    cs:__imp_LoadLibraryExW
0x180075e8b  mov     rbx, rax
0x180075e8e  mov     [rsp+178h+var_100], rax
0x180075e93  mov     rcx, [rsp+178h]; this
0x180075e9b  test    rax, rax
0x180075e9e  jz      loc_1800763BF
0x180075ea4  lea     rdx, aSetupdigetclas; "SetupDiGetClassDevsW"
0x180075eab  mov     rcx, rax; hModule
0x180075eae  call    cs:__imp_GetProcAddress
0x180075eb4  mov     r14, rax
0x180075eb7  mov     rcx, [rsp+178h]; this
0x180075ebf  test    rax, rax
0x180075ec2  jnz     short loc_180075ED5
0x180075ec4  lea     r8, aOnecoreInterna_4; "OneCore\\Internal\\Shell\\inc\\CopilotP"...
0x180075ecb  mov     edx, 89h; void *
0x180075ed0  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180075ed5  lea     rdx, aSetupdidestroy; "SetupDiDestroyDeviceInfoList"
0x180075edc  mov     rcx, rbx; hModule
0x180075edf  call    cs:__imp_GetProcAddress
0x180075ee5  mov     r15, rax
0x180075ee8  mov     rcx, [rsp+178h]; this
0x180075ef0  test    rax, rax
0x180075ef3  jnz     short loc_180075F06
0x180075ef5  lea     r8, aOnecoreInterna_4; "OneCore\\Internal\\Shell\\inc\\CopilotP"...
0x180075efc  mov     edx, 8Bh; void *
0x180075f01  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180075f06  lea     rdx, aSetupdienumdev; "SetupDiEnumDeviceInfo"
0x180075f0d  mov     rcx, rbx; hModule
0x180075f10  call    cs:__imp_GetProcAddress
0x180075f16  mov     r12, rax
0x180075f19  mov     rcx, [rsp+178h]; this
0x180075f21  test    rax, rax
0x180075f24  jnz     short loc_180075F37
0x180075f26  lea     r8, aOnecoreInterna_4; "OneCore\\Internal\\Shell\\inc\\CopilotP"...
0x180075f2d  mov     edx, 8Dh; void *
0x180075f32  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180075f37  lea     rdx, aSetupdigetdevi_0; "SetupDiGetDeviceInstanceIdW"
0x180075f3e  mov     rcx, rbx; hModule
0x180075f41  call    cs:__imp_GetProcAddress
0x180075f47  mov     [rsp+178h+var_128], rax
0x180075f4c  mov     rcx, [rsp+178h]; this
0x180075f54  test    rax, rax
0x180075f57  jnz     short loc_180075F6A
0x180075f59  lea     r8, aOnecoreInterna_4; "OneCore\\Internal\\Shell\\inc\\CopilotP"...
0x180075f60  mov     edx, 8Fh; void *
0x180075f65  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180075f6a  lea     rdx, aSetupdigetdevi; "SetupDiGetDevicePropertyW"
0x180075f71  mov     rcx, rbx; hModule
0x180075f74  call    cs:__imp_GetProcAddress
0x180075f7a  mov     r13, rax
0x180075f7d  mov     rcx, [rsp+178h]; this
0x180075f85  xor     ebx, ebx
0x180075f87  test    rax, rax
0x180075f8a  jnz     short loc_180075F9D
0x180075f8c  lea     r8, aOnecoreInterna_4; "OneCore\\Internal\\Shell\\inc\\CopilotP"...
0x180075f93  mov     edx, 91h; void *
0x180075f98  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180075f9d  mov     rdx, rsi
0x180075fa0  lea     rcx, [rsp+178h+lpString1]
0x180075fa8  call    ?HardwareIdToVendorProductString@npu_detection@udk@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBUDXCoreHardwareIDParts@@@Z; udk::npu_detection::HardwareIdToVendorProductString(DXCoreHardwareIDParts const &)
0x180075fad  nop
0x180075fae  mov     [rsp+178h+var_D0], 0F01A9D53h
0x180075fb9  mov     [rsp+178h+var_CC], 48D23FF6h
0x180075fc4  mov     [rsp+178h+var_C8], 0A7C8979Fh
0x180075fcf  mov     [rsp+178h+var_C4], 0CE14B00h
0x180075fda  mov     r9d, 2
0x180075fe0  xor     r8d, r8d
0x180075fe3  xor     edx, edx
0x180075fe5  lea     rcx, [rsp+178h+var_D0]
0x180075fed  mov     rax, r14
0x180075ff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075ff5  mov     r14, rax
0x180075ff8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180075ffc  jz      loc_180076396
0x180076002  mov     [rsp+178h+var_F0], rax
0x18007600a  mov     [rsp+178h+var_E8], r15
0x180076012  mov     [rsp+178h+var_E0], 1
0x18007601a  xorps   xmm0, xmm0
0x18007601d  movups  [rsp+178h+var_A0], xmm0
0x180076025  movups  [rsp+178h+var_90], xmm0
0x18007602d  mov     dword ptr [rsp+178h+var_A0], 20h ; ' '
0x180076038  mov     esi, ebx
0x18007603a  lea     r8, [rsp+178h+var_A0]
0x180076042  mov     edx, esi
0x180076044  mov     rcx, r14
0x180076047  mov     rax, r12
0x18007604a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007604f  test    eax, eax
0x180076051  jz      loc_180076363
0x180076057  xorps   xmm0, xmm0
0x18007605a  movdqu  [rsp+178h+var_120], xmm0
0x180076060  mov     [rsp+178h+var_110], rbx
0x180076065  mov     edx, 0C8h
0x18007606a  lea     rcx, [rsp+178h+var_120]
0x18007606f  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180076074  mov     r8, qword ptr [rsp+178h+var_120]
0x180076079  mov     r9, qword ptr [rsp+178h+var_120+8]
0x18007607e  sub     r9, r8
0x180076081  sar     r9, 1
0x180076084  mov     qword ptr [rsp+178h+bIgnoreCase], rbx
0x180076089  lea     rdx, [rsp+178h+var_A0]
0x180076091  mov     rcx, r14
0x180076094  mov     rax, [rsp+178h+var_128]
0x180076099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007609e  mov     rcx, [rsp+178h]; this
0x1800760a6  test    eax, eax
0x1800760a8  jnz     short loc_1800760BB
0x1800760aa  lea     r8, aOnecoreInterna_4; "OneCore\\Internal\\Shell\\inc\\CopilotP"...
0x1800760b1  mov     edx, 0ABh; void *
0x1800760b6  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800760bb  xor     r8d, r8d
0x1800760be  mov     rdx, qword ptr [rsp+178h+var_120+8]
0x1800760c3  mov     rcx, qword ptr [rsp+178h+var_120]
0x1800760c8  call    __std_find_trivial_2
0x1800760cd  mov     rbx, rax
0x1800760d0  mov     r8d, 5Ch ; '\'
0x1800760d6  mov     rdx, rax
0x1800760d9  mov     rcx, qword ptr [rsp+178h+var_120]
0x1800760de  call    __std_find_trivial_2
0x1800760e3  cmp     rax, qword ptr [rsp+178h+var_120+8]
0x1800760e8  jz      loc_180076339
0x1800760ee  cmp     rbx, qword ptr [rsp+178h+var_120+8]
0x1800760f3  jz      loc_180076339
0x1800760f9  lea     rcx, [rax+2]
0x1800760fd  cmp     rcx, rbx
0x180076100  jz      loc_180076339
0x180076106  sub     rbx, rcx
0x180076109  sar     rbx, 1
0x18007610c  mov     rdx, qword ptr [rsp+178h+cchCount2]; cchCount1
0x180076114  cmp     rbx, rdx
0x180076117  jb      loc_180076339
0x18007611d  mov     rax, qword ptr [rsp+178h+var_120]
0x180076122  sub     rcx, rax
0x180076125  sar     rcx, 1
0x180076128  lea     r8, [rax+rcx*2]; lpString2
0x18007612c  lea     rcx, [rsp+178h+lpString1]
0x180076134  cmp     [rsp+178h+var_A8], 7
0x18007613d  cmova   rcx, [rsp+178h+lpString1]; lpString1
0x180076146  mov     [rsp+178h+bIgnoreCase], 1; bIgnoreCase
0x18007614e  mov     r9d, edx; cchCount2
0x180076151  call    cs:__imp_CompareStringOrdinal
0x180076157  cmp     eax, 2
0x18007615a  jnz     loc_180076339
0x180076160  xor     r12d, r12d
0x180076163  mov     [rsp+178h+var_108], r12d
0x180076168  mov     [rsp+178h+var_140], r12d
0x18007616d  mov     [rsp+178h+var_148], r12
0x180076172  mov     [rsp+178h+var_150], 30h ; '0'
0x18007617a  lea     rax, [rsp+178h+var_60]
0x180076182  mov     qword ptr [rsp+178h+bIgnoreCase], rax; int
0x180076187  lea     r9, [rsp+178h+var_108]
0x18007618c  lea     r8, DEVPKEY_Device_DriverVersion
0x180076193  lea     rdx, [rsp+178h+var_A0]
0x18007619b  mov     rcx, r14
0x18007619e  mov     rax, r13
0x1800761a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800761a6  mov     rcx, [rsp+178h]; this
0x1800761ae  test    eax, eax
0x1800761b0  jnz     short loc_1800761C3
0x1800761b2  lea     r8, aOnecoreInterna_4; "OneCore\\Internal\\Shell\\inc\\CopilotP"...
0x1800761b9  mov     edx, 0C2h; void *
0x1800761be  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800761c3  mov     rax, r12
0x1800761c6  mov     [rsp+178h+var_D8], rax
0x1800761ce  mov     rbx, r12
0x1800761d1  mov     rsi, r12
0x1800761d4  cmp     rsi, 4
0x1800761d8  jnb     loc_1800762BB
0x1800761de  mov     rcx, [rsp+178h]; this
0x1800761e6  cmp     rbx, 18h
0x1800761ea  jb      short loc_180076203
0x1800761ec  mov     r9d, 80070057h; char *
0x1800761f2  lea     r8, aOnecoreInterna_4; "OneCore\\Internal\\Shell\\inc\\CopilotP"...
0x1800761f9  mov     edx, 0CBh; void *
0x1800761fe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180076203  mov     [rsp+178h+var_128], r12
0x180076208  lea     rdx, [rsp+178h+var_60]
0x180076210  lea     rdx, [rdx+rbx*2]
0x180076214  lea     rcx, [rsp+178h+String]
0x18007621c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180076221  nop
0x180076222  lea     rdx, [rsp+178h+var_128]
0x180076227  lea     rcx, [rsp+178h+String]; String
0x18007622f  call    ?stoi@std@@YAHAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@PEA_KH@Z; std::stoi(std::wstring const &,unsigned __int64 *,int)
0x180076234  mov     word ptr [rsp+rsi*2+178h+var_D8], ax
0x18007623c  lea     rcx, [rsp+178h+String]
0x180076244  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180076249  mov     rcx, [rsp+178h]; this
0x180076251  cmp     rsi, 3
0x180076255  jz      short loc_180076291
0x180076257  add     rbx, [rsp+178h+var_128]
0x18007625c  cmp     [rsp+rbx*2+178h+var_60], 2Eh ; '.'
0x180076265  jz      short loc_18007627E
0x180076267  mov     r9d, 80070057h; char *
0x18007626d  lea     r8, aOnecoreInterna_4; "OneCore\\Internal\\Shell\\inc\\CopilotP"...
0x180076274  mov     edx, 0D3h; void *
0x180076279  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007627e  inc     rbx
0x180076281  inc     rsi
0x180076284  mov     rax, [rsp+178h+var_D8]
0x18007628c  jmp     loc_1800761D4
0x180076291  mov     rdx, [rsp+178h+var_128]
0x180076296  add     rdx, rbx
0x180076299  cmp     [rsp+rdx*2+178h+var_60], r12w
0x1800762a2  jz      short loc_180076281
0x1800762a4  mov     r9d, 80070057h; char *
0x1800762aa  lea     r8, aOnecoreInterna_4; "OneCore\\Internal\\Shell\\inc\\CopilotP"...
0x1800762b1  mov     edx, 0DBh; void *
0x1800762b6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800762bb  movzx   ecx, word ptr [rsp+178h+var_D8+6]
0x1800762c3  mov     [rdi], cx
0x1800762c6  movzx   ecx, word ptr [rsp+178h+var_D8+4]
0x1800762ce  mov     [rdi+2], cx
0x1800762d2  movzx   ecx, word ptr [rsp+178h+var_D8+2]
0x1800762da  mov     [rdi+4], cx
0x1800762de  mov     [rdi+6], ax
0x1800762e2  mov     rcx, qword ptr [rsp+178h+var_120]
0x1800762e7  test    rcx, rcx
0x1800762ea  jz      short loc_18007630D
0x1800762ec  mov     rdx, [rsp+178h+var_110]
0x1800762f1  sub     rdx, rcx
0x1800762f4  sar     rdx, 1
0x1800762f7  add     rdx, rdx
0x1800762fa  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800762ff  xorps   xmm0, xmm0
0x180076302  movdqu  [rsp+178h+var_120], xmm0
0x180076308  mov     [rsp+178h+var_110], r12
0x18007630d  mov     rcx, r14
0x180076310  mov     rax, r15
0x180076313  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076318  nop
0x180076319  lea     rcx, [rsp+178h+lpString1]
0x180076321  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180076326  nop
0x180076327  lea     rcx, [rsp+178h+var_100]
0x18007632c  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180076331  mov     rax, rdi
0x180076334  jmp     loc_1800763D9
0x180076339  inc     esi
0x18007633b  mov     rcx, qword ptr [rsp+178h+var_120]
0x180076340  xor     ebx, ebx
0x180076342  test    rcx, rcx
0x180076345  jz      loc_18007603A
0x18007634b  mov     rdx, [rsp+178h+var_110]
0x180076350  sub     rdx, rcx
0x180076353  sar     rdx, 1
0x180076356  add     rdx, rdx
0x180076359  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18007635e  jmp     loc_18007603A
0x180076363  call    cs:__imp_GetLastError
0x180076369  cmp     eax, 103h
0x18007636e  jz      short loc_18007638A
0x180076370  mov     rcx, [rsp+178h]; this
0x180076378  lea     r8, aOnecoreInterna_4; "OneCore\\Internal\\Shell\\inc\\CopilotP"...
0x18007637f  mov     edx, 0E5h; void *
0x180076384  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18007638a  mov     rcx, r14
0x18007638d  mov     rax, r15
0x180076390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076395  nop
0x180076396  call    ?NpuDriverVersionFallbackFailed@HardwareRequirementsTelemetry@CopilotPlusDetection@udk@@SAXXZ; udk::CopilotPlusDetection::HardwareRequirementsTelemetry::NpuDriverVersionFallbackFailed(void)
0x18007639b  mov     qword ptr [rdi], 0
0x1800763a2  lea     rcx, [rsp+178h+lpString1]
0x1800763aa  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800763af  nop
0x1800763b0  lea     rcx, [rsp+178h+var_100]
0x1800763b5  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800763ba  mov     rax, rdi
0x1800763bd  jmp     short loc_1800763D9
0x1800763bf  lea     r8, aOnecoreInterna_4; "OneCore\\Internal\\Shell\\inc\\CopilotP"...
0x1800763c6  mov     edx, 86h; void *
0x1800763cb  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800763d1  mov     rax, [rsp+178h+var_F8]
0x1800763d9  mov     rcx, [rsp+178h+var_30]
0x1800763e1  xor     rcx, rsp; StackCookie
0x1800763e4  call    __security_check_cookie
0x1800763e9  lea     r11, [rsp+178h+var_28]
0x1800763f1  mov     rbx, [r11+40h]
0x1800763f5  mov     rsi, [r11+48h]
0x1800763f9  mov     rsp, r11
  ... truncated ...
```
