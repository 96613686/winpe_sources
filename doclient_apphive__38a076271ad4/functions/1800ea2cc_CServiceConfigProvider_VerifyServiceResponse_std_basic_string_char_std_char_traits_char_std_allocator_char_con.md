# CServiceConfigProvider::_VerifyServiceResponse(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,HttpResponseInfo const &)

- ea: `0x1800ea2cc`
- end: `0x1800eaa56`
- name: `?_VerifyServiceResponse@CServiceConfigProvider@@AEAAJAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@0AEBUHttpResponseInfo@@@Z`
- size: `1930`
- prototype: `__int64 __fastcall(CServiceConfigProvider *this)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, service_task`

## callers

- `0x1800e9994`

## callees

- `0x18000933c`
- `0x180009380`
- `0x1800095a0`
- `0x18000c4b0`
- `0x18000d228`
- `0x180019a84`
- `0x180027334`
- `0x1800397c4`
- `0x18003d7d4`
- `0x18004be34`
- `0x1800604f8`
- `0x1800a1ea4`
- `0x1800adb38`
- `0x1800ae90c`
- `0x1800aec0c`
- `0x1800bb468`
- `0x1800dbb34`
- `0x1800dbdf8`
- `0x1800e9584`
- `0x1800ea2cc`
- `0x1800eaa5c`
- `0x1800f82f0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800ea36e`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800ea87c`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800ea937`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800ea36e`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800ea87c`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800ea937`
- `bcrypt!BCryptDestroyHash` at `0x1800ea7ac`
- `bcrypt!BCryptDestroyHash` at `0x1800ea8da`
- `bcrypt!BCryptDestroyHash` at `0x1800ea9c3`
- `bcrypt!BCryptDestroyHash` at `0x1800ea7ac`
- `bcrypt!BCryptDestroyHash` at `0x1800ea8da`
- `bcrypt!BCryptDestroyHash` at `0x1800ea9c3`

## string_xrefs

- `0x1800ea473`: `C:\__w\1\s\src\DeliveryOptimization\ConfigManagement\ServiceConfigProvider.cpp`
- `0x1800ea4d2`: `C:\__w\1\s\src\DeliveryOptimization\ConfigManagement\ServiceConfigProvider.cpp`
- `0x1800ea77f`: `C:\__w\1\s\src\DeliveryOptimization\ConfigManagement\ServiceConfigProvider.cpp`
- `0x1800ea8ad`: `C:\__w\1\s\src\DeliveryOptimization\ConfigManagement\ServiceConfigProvider.cpp`
- `0x1800ea3d5`: `Skipping JSON response check for service %s (last check was at %s)`
- `0x1800ea3e2`: `CServiceConfigProvider::_VerifyServiceResponse`
- `0x1800ea98c`: `CServiceConfigProvider::_VerifyServiceResponse`
- `0x1800ea97f`: `JSON response for service %s was successfully verified (last check is set at %s)`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CServiceConfigProvider::_VerifyServiceResponse(
        CServiceConfigProvider *this,
        __int64 a2,
        _QWORD *a3,
        __int64 a4)
{
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  __int64 v11; // rdx
  __int64 Config; // rdi
  signed __int64 v13; // r8
  __int64 v14; // rdx
  const char *v15; // rax
  const char *v16; // r8
  const char *v17; // r9
  __int64 result; // rax
  int v19; // eax
  unsigned int v20; // edi
  int Header; // eax
  unsigned int v22; // edi
  __int64 v23; // rax
  _OWORD *v24; // rax
  char v25; // di
  __int128 v26; // xmm6
  size_t v27; // rcx
  void **Src; // rax
  __int64 v29; // rax
  void **v30; // rdx
  int v31; // eax
  unsigned int v32; // edi
  int v33; // ecx
  int v34; // ecx
  int v35; // ecx
  __int64 v36; // rdx
  __int64 v37; // rdi
  __int64 v38; // rdi
  const char *v39; // rax
  const char *v40; // r8
  int Size; // [rsp+20h] [rbp-1A8h]
  int Sizea; // [rsp+20h] [rbp-1A8h]
  __int64 v43; // [rsp+40h] [rbp-188h] BYREF
  int v44; // [rsp+48h] [rbp-180h]
  _BYTE v45[32]; // [rsp+50h] [rbp-178h] BYREF
  _OWORD v46[2]; // [rsp+70h] [rbp-158h] BYREF
  _OWORD v47[2]; // [rsp+90h] [rbp-138h] BYREF
  BCRYPT_HASH_HANDLE hHash[2]; // [rsp+B0h] [rbp-118h] BYREF
  __int128 v49; // [rsp+C0h] [rbp-108h] BYREF
  __int64 v50; // [rsp+D0h] [rbp-F8h]
  void *v51[2]; // [rsp+D8h] [rbp-F0h] BYREF
  unsigned __int64 v52[2]; // [rsp+E8h] [rbp-E0h]
  __int128 v53; // [rsp+F8h] [rbp-D0h] BYREF
  __m128i si128; // [rsp+108h] [rbp-C0h]
  _OWORD v55[2]; // [rsp+118h] [rbp-B0h] BYREF
  _OWORD v56[2]; // [rsp+138h] [rbp-90h] BYREF
  void *v57[2]; // [rsp+158h] [rbp-70h] BYREF
  __int128 v58; // [rsp+168h] [rbp-60h]
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+0h]

  try
  {
    v44 = 0;
    if ( *((_QWORD *)this + 21) == 0x7FFFFFFFFFFFFFFFLL )
      goto LABEL_14;
    v8 = *((_DWORD *)this + 2);
    if ( v8 )
    {
      v9 = v8 - 2;
      if ( !v9 )
      {
        v11 = 152;
        goto LABEL_11;
      }
      v10 = v9 - 1;
      if ( !v10 )
      {
        v11 = 150;
        goto LABEL_11;
      }
      if ( v10 == 1 )
      {
        v11 = 151;
LABEL_11:
        Config = (unsigned int)CGlobalConfigManager::GetConfigValue<unsigned int>(*((_QWORD *)this + 11), v11);
        v43 = 0;
        GetSystemTimePreciseAsFileTime(&v43);
        v13 = (unsigned int)v43 + ((unsigned __int64)HIDWORD(v43) << 32) - 116444736000000000LL;
        v14 = *((_QWORD *)this + 21) + 10000000 * Config;
        if ( v14 != v13 && v14 >= v13 )
        {
          SysTimePointToUTCString(v45);
          v15 = CServiceConfigProvider::_ServiceName(this);
          LogMessage(
            4u,
            "CServiceConfigProvider::_VerifyServiceResponse",
            0xDDu,
            "Skipping JSON response check for service %s (last check was at %s)",
            v15,
            v16);
          std::string::~string(v45);
          return 0;
        }
LABEL_14:
        v53 = 0;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        LOBYTE(v53) = 0;
        v55[0] = 0;
        v55[1] = si128;
        LOBYTE(v55[0]) = 0;
        v19 = HttpResponseInfo::ExtractHeader(a4, "DO-Timestamp", &v53);
        v20 = v19;
        if ( v19 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xE3,
            (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\ConfigManagement\\ServiceConfigProvider.cpp",
            (const char *)(unsigned int)v19,
            Size);
          std::string::~string(v55);
          std::string::~string(&v53);
          return v20;
        }
        Header = HttpResponseInfo::ExtractHeader(a4, "DO-Content-Sig", v55);
        v22 = Header;
        if ( Header < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xE4,
            (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\ConfigManagement\\ServiceConfigProvider.cpp",
            (const char *)(unsigned int)Header,
            Size);
          std::string::~string(v55);
          std::string::~string(&v53);
          return v22;
        }
        v23 = std::string::find(a3, "?", 0);
        if ( v23 == -1 )
        {
          memset(v46, 0, sizeof(v46));
          std::string::_Construct<1,char const *>(v46, &word_180129F2A);
          v24 = v46;
          v25 = 2;
        }
        else
        {
          memset(v47, 0, sizeof(v47));
          if ( a3[2] < (unsigned __int64)(v23 + 1) )
            std::_String_val<std::_Simple_types<char>>::_Xran();
          if ( a3[3] > 0xFu )
            a3 = (_QWORD *)*a3;
          std::string::_Construct<1,char const *>(v47, (char *)a3 + v23 + 1);
          v24 = v47;
          v25 = 17;
        }
        *(_OWORD *)v57 = *v24;
        v26 = v24[1];
        v58 = v26;
        *(_BYTE *)v24 = 0;
        *((_QWORD *)v24 + 2) = 0;
        *((_QWORD *)v24 + 3) = 15;
        if ( (v25 & 2) != 0 )
        {
          v25 &= ~2u;
          std::string::~string(v46);
        }
        if ( (v25 & 1) != 0 )
          std::string::~string(v47);
        v27 = *(_QWORD *)(a2 + 16);
        if ( 0x7FFFFFFFFFFFFFFFLL - v27 < (unsigned __int64)v26 )
          std::_Xlen_string();
        Src = v57;
        if ( *((_QWORD *)&v58 + 1) > 0xFu )
          Src = (void **)v57[0];
        std::string::string(v45, v27, Src, v26);
        v29 = std::string::append(v45, &v53);
        *(_OWORD *)v51 = 0;
        *(_OWORD *)v52 = 0;
        *(_OWORD *)v51 = *(_OWORD *)v29;
        *(_OWORD *)v52 = *(_OWORD *)(v29 + 16);
        *(_BYTE *)v29 = 0;
        *(_QWORD *)(v29 + 16) = 0;
        *(_QWORD *)(v29 + 24) = 15;
        std::string::~string(v45);
        v49 = 0;
        v50 = 0;
        *(_OWORD *)hHash = 0;
        CHash::CHash(hHash);
        v30 = v51;
        if ( v52[1] > 0xF )
          v30 = (void **)v51[0];
        CHash::Hash((CHash *)hHash, v30, v52[0]);
        v56[0] = 0;
        v56[1] = _mm_load_si128((const __m128i *)&_xmm);
        LOBYTE(v56[0]) = 0;
        CGlobalConfigManager::_GetConfigOverrideFromProvider<std::string>(
          *((_QWORD *)this + 11),
          1,
          17,
          (unsigned int)v56,
          0);
        v31 = VerifyHashSignature(&v49, v55, v56);
        v32 = v31;
        if ( v31 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x101,
            (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\ConfigManagement\\ServiceConfigProvider.cpp",
            (const char *)(unsigned int)v31,
            Sizea);
          std::string::~string(v56);
          if ( hHash[0] )
            BCryptDestroyHash(hHash[0]);
          std::vector<unsigned char>::_Tidy(&v49);
          std::string::~string(v51);
          std::string::~string(v57);
          std::string::~string(v55);
          std::string::~string(&v53);
          return v32;
        }
        if ( !(unsigned __int8)CGlobalConfigManager::GetConfigValue<bool>(*((_QWORD *)this + 11), 140, 0) )
        {
LABEL_50:
          v43 = 0;
          GetSystemTimePreciseAsFileTime(&v43);
          *((_QWORD *)this + 21) = (unsigned int)v43 + ((unsigned __int64)HIDWORD(v43) << 32) - 116444736000000000LL;
          SysTimePointToUTCString(v45);
          v39 = CServiceConfigProvider::_ServiceName(this);
          LogMessage(
            4u,
            "CServiceConfigProvider::_VerifyServiceResponse",
            0x11Cu,
            "JSON response for service %s was successfully verified (last check is set at %s)",
            v39,
            v40);
          std::string::~string(v45);
          std::string::~string(v56);
          if ( hHash[0] )
            BCryptDestroyHash(hHash[0]);
          std::vector<unsigned char>::_Tidy(&v49);
          std::string::~string(v51);
          std::string::~string(v57);
          std::string::~string(v55);
          std::string::~string(&v53);
          return 0;
        }
        v33 = *((_DWORD *)this + 2);
        if ( v33 )
        {
          v34 = v33 - 2;
          if ( !v34 )
          {
            v36 = 144;
            goto LABEL_46;
          }
          v35 = v34 - 1;
          if ( !v35 )
          {
            v36 = 142;
            goto LABEL_46;
          }
          if ( v35 == 1 )
          {
            v36 = 143;
            goto LABEL_46;
          }
        }
        v36 = 141;
LABEL_46:
        v37 = (unsigned int)CGlobalConfigManager::GetConfigValue<unsigned int>(*((_QWORD *)this + 11), v36);
        v38 = *(_QWORD *)UTCDateTimeStringToSysTimePoint(&v43, &v53) + 10000000 * v37;
        v43 = 0;
        GetSystemTimePreciseAsFileTime(&v43);
        if ( v38 < (__int64)((unsigned int)v43 + ((unsigned __int64)HIDWORD(v43) << 32) - 116444736000000000LL) )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x114,
            (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\ConfigManagement\\ServiceConfigProvider.cpp",
            (const char *)0x80071131LL,
            Sizea);
          std::string::~string(v56);
          if ( hHash[0] )
            BCryptDestroyHash(hHash[0]);
          std::vector<unsigned char>::_Tidy(&v49);
          std::string::~string(v51);
          std::string::~string(v57);
          std::string::~string(v55);
          std::string::~string(&v53);
          return 2147946801LL;
        }
        goto LABEL_50;
      }
    }
    v11 = 149;
    goto LABEL_11;
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x11F,
                           (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\ConfigManagement\\ServiceConfigProvider.cpp",
                           v17);
  }
  return result;
}

```

## disassembly

```asm
0x1800ea2cc  mov     rax, rsp
0x1800ea2cf  push    rbx
0x1800ea2d0  push    rsi
0x1800ea2d1  push    rdi
0x1800ea2d2  push    r12
0x1800ea2d4  push    r13
0x1800ea2d6  push    r14
0x1800ea2d8  push    r15
0x1800ea2da  sub     rsp, 190h
0x1800ea2e1  movaps  xmmword ptr [rax-48h], xmm6
0x1800ea2e5  mov     rax, cs:__security_cookie
0x1800ea2ec  xor     rax, rsp
0x1800ea2ef  mov     [rsp+1C8h+var_50], rax
0x1800ea2f7  mov     r12, r9
0x1800ea2fa  mov     rsi, r8
0x1800ea2fd  mov     r14, rdx
0x1800ea300  mov     rbx, rcx
0x1800ea303  mov     [rsp+1C8h+var_180], 0
0x1800ea30b  mov     r15, 7FFFFFFFFFFFFFFFh
0x1800ea315  cmp     [rcx+0A8h], r15
0x1800ea31c  jz      loc_1800EA404
0x1800ea322  mov     ecx, [rcx+8]
0x1800ea325  test    ecx, ecx
0x1800ea327  jz      short loc_1800EA34D
0x1800ea329  sub     ecx, 2
0x1800ea32c  jz      short loc_1800EA346
0x1800ea32e  sub     ecx, 1
0x1800ea331  jz      short loc_1800EA33F
0x1800ea333  cmp     ecx, 1
0x1800ea336  jnz     short loc_1800EA34D
0x1800ea338  mov     edx, 97h
0x1800ea33d  jmp     short loc_1800EA352
0x1800ea33f  mov     edx, 96h
0x1800ea344  jmp     short loc_1800EA352
0x1800ea346  mov     edx, 98h
0x1800ea34b  jmp     short loc_1800EA352
0x1800ea34d  mov     edx, 95h
0x1800ea352  xor     r8d, r8d
0x1800ea355  mov     rcx, [rbx+58h]
0x1800ea359  call    ??$GetConfigValue@I@CGlobalConfigManager@@QEBAIW4Index@DOConfig@@PEAW4_ConfigProviderType@@@Z; CGlobalConfigManager::GetConfigValue<uint>(DOConfig::Index,_ConfigProviderType *)
0x1800ea35e  mov     edi, eax
0x1800ea360  mov     [rsp+1C8h+var_188], 0
0x1800ea369  lea     rcx, [rsp+1C8h+var_188]
0x1800ea36e  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x1800ea374  mov     r8d, dword ptr [rsp+1C8h+var_188+4]
0x1800ea379  shl     r8, 20h
0x1800ea37d  mov     edx, dword ptr [rsp+1C8h+var_188]
0x1800ea381  mov     r13, 0FE624E212AC18000h
0x1800ea38b  add     r8, r13
0x1800ea38e  add     r8, rdx
0x1800ea391  imul    rdx, rdi, 989680h
0x1800ea398  mov     rax, [rbx+0A8h]
0x1800ea39f  add     rdx, rax
0x1800ea3a2  cmp     rdx, r8
0x1800ea3a5  jz      short loc_1800EA40E
0x1800ea3a7  jl      short loc_1800EA40E
0x1800ea3a9  mov     rdx, rax
0x1800ea3ac  lea     rcx, [rsp+1C8h+var_178]
0x1800ea3b1  call    ?SysTimePointToUTCString@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@2@@Z; SysTimePointToUTCString(std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>)
0x1800ea3b6  mov     r8, rax
0x1800ea3b9  cmp     qword ptr [rax+18h], 0Fh
0x1800ea3be  jbe     short loc_1800EA3C3
0x1800ea3c0  mov     r8, [rax]
0x1800ea3c3  mov     rcx, rbx; this
0x1800ea3c6  call    ?_ServiceName@CServiceConfigProvider@@AEBAPEBDXZ; CServiceConfigProvider::_ServiceName(void)
0x1800ea3cb  mov     [rsp+1C8h+Src], r8
0x1800ea3d0  mov     [rsp+1C8h+Size], rax
0x1800ea3d5  lea     r9, aSkippingJsonRe; "Skipping JSON response check for servic"...
0x1800ea3dc  mov     r8d, 0DDh; unsigned int
0x1800ea3e2  lea     rdx, aCserviceconfig_1; "CServiceConfigProvider::_VerifyServiceR"...
0x1800ea3e9  mov     ecx, 4; unsigned __int8
0x1800ea3ee  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x1800ea3f3  lea     rcx, [rsp+1C8h+var_178]; void *
0x1800ea3f8  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800ea3fd  xor     eax, eax
0x1800ea3ff  jmp     loc_1800EAA1E
0x1800ea404  mov     r13, 0FE624E212AC18000h
0x1800ea40e  xorps   xmm0, xmm0
0x1800ea411  movups  [rsp+1C8h+var_D0], xmm0
0x1800ea419  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x1800ea421  movdqu  [rsp+1C8h+var_C0], xmm1
0x1800ea42a  mov     byte ptr [rsp+1C8h+var_D0], 0
0x1800ea432  movups  [rsp+1C8h+var_B0], xmm0
0x1800ea43a  movdqu  [rsp+1C8h+var_A0], xmm1
0x1800ea443  mov     byte ptr [rsp+1C8h+var_B0], 0
0x1800ea44b  lea     r8, [rsp+1C8h+var_D0]
0x1800ea453  lea     rdx, aDoTimestamp; "DO-Timestamp"
0x1800ea45a  mov     rcx, r12
0x1800ea45d  call    ?ExtractHeader@HttpResponseInfo@@QEBAJPEBDAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; HttpResponseInfo::ExtractHeader(char const *,std::string &)
0x1800ea462  mov     edi, eax
0x1800ea464  test    eax, eax
0x1800ea466  jns     short loc_1800EA4A7
0x1800ea468  mov     rcx, [rsp+1C8h]; this
0x1800ea470  mov     r9d, eax; char *
0x1800ea473  lea     r8, aCW1SSrcDeliver_6; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800ea47a  mov     edx, 0E3h; void *
0x1800ea47f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ea484  nop
0x1800ea485  lea     rcx, [rsp+1C8h+var_B0]; void *
0x1800ea48d  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800ea492  nop
0x1800ea493  lea     rcx, [rsp+1C8h+var_D0]; void *
0x1800ea49b  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800ea4a0  mov     eax, edi
0x1800ea4a2  jmp     loc_1800EAA1E
0x1800ea4a7  lea     r8, [rsp+1C8h+var_B0]
0x1800ea4af  lea     rdx, aDoContentSig; "DO-Content-Sig"
0x1800ea4b6  mov     rcx, r12
0x1800ea4b9  call    ?ExtractHeader@HttpResponseInfo@@QEBAJPEBDAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; HttpResponseInfo::ExtractHeader(char const *,std::string &)
0x1800ea4be  mov     edi, eax
0x1800ea4c0  xor     r12d, r12d
0x1800ea4c3  test    eax, eax
0x1800ea4c5  jns     short loc_1800EA506
0x1800ea4c7  mov     rcx, [rsp+1C8h]; this
0x1800ea4cf  mov     r9d, eax; char *
0x1800ea4d2  lea     r8, aCW1SSrcDeliver_6; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800ea4d9  mov     edx, 0E4h; void *
0x1800ea4de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ea4e3  nop
0x1800ea4e4  lea     rcx, [rsp+1C8h+var_B0]; void *
0x1800ea4ec  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800ea4f1  nop
0x1800ea4f2  lea     rcx, [rsp+1C8h+var_D0]; void *
0x1800ea4fa  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800ea4ff  mov     eax, edi
0x1800ea501  jmp     loc_1800EAA1E
0x1800ea506  xor     r8d, r8d
0x1800ea509  lea     rdx, asc_180141778; "?"
0x1800ea510  mov     rcx, rsi
0x1800ea513  call    ?find@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA_KQEBD_K@Z; std::string::find(char const * const,unsigned __int64)
0x1800ea518  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800ea51c  xorps   xmm0, xmm0
0x1800ea51f  xorps   xmm1, xmm1
0x1800ea522  cmp     rax, r8
0x1800ea525  jz      short loc_1800EA57D
0x1800ea527  lea     rcx, [rax+1]
0x1800ea52b  movups  [rsp+1C8h+var_138], xmm0
0x1800ea533  movdqu  [rsp+1C8h+var_128], xmm1
0x1800ea53c  mov     rax, [rsi+10h]
0x1800ea540  cmp     rax, rcx
0x1800ea543  jb      loc_1800EAA49
0x1800ea549  sub     rax, rcx
0x1800ea54c  cmp     rax, r8
0x1800ea54f  cmovb   r8, rax
0x1800ea553  cmp     qword ptr [rsi+18h], 0Fh
0x1800ea558  jbe     short loc_1800EA55D
0x1800ea55a  mov     rsi, [rsi]
0x1800ea55d  lea     rdx, [rsi+rcx]
0x1800ea561  lea     rcx, [rsp+1C8h+var_138]
0x1800ea569  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800ea56e  lea     rax, [rsp+1C8h+var_138]
0x1800ea576  mov     edi, 11h
0x1800ea57b  jmp     short loc_1800EA5A9
0x1800ea57d  movups  [rsp+1C8h+var_158], xmm0
0x1800ea582  movdqu  [rsp+1C8h+var_148], xmm1
0x1800ea58b  xor     r8d, r8d
0x1800ea58e  lea     rdx, word_180129F2A
0x1800ea595  lea     rcx, [rsp+1C8h+var_158]
0x1800ea59a  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800ea59f  lea     rax, [rsp+1C8h+var_158]
0x1800ea5a4  mov     edi, 2
0x1800ea5a9  movups  xmm0, xmmword ptr [rax]
0x1800ea5ac  movups  xmmword ptr [rsp+1C8h+var_70], xmm0
0x1800ea5b4  movups  xmm6, xmmword ptr [rax+10h]
0x1800ea5b8  movups  [rsp+1C8h+var_60], xmm6
0x1800ea5c0  mov     [rax], r12b
0x1800ea5c3  mov     [rax+10h], r12
0x1800ea5c7  mov     qword ptr [rax+18h], 0Fh
0x1800ea5cf  test    dil, 2
0x1800ea5d3  jz      short loc_1800EA5E3
0x1800ea5d5  and     edi, 0FFFFFFFDh
0x1800ea5d8  lea     rcx, [rsp+1C8h+var_158]; void *
0x1800ea5dd  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800ea5e2  nop
0x1800ea5e3  test    dil, 1
0x1800ea5e7  jz      short loc_1800EA5F6
0x1800ea5e9  lea     rcx, [rsp+1C8h+var_138]; void *
0x1800ea5f1  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800ea5f6  mov     rcx, [r14+10h]
0x1800ea5fa  sub     r15, rcx
0x1800ea5fd  movq    rdx, xmm6
0x1800ea602  cmp     r15, rdx
0x1800ea605  jb      loc_1800EAA4F
0x1800ea60b  cmp     qword ptr [r14+18h], 0Fh
0x1800ea610  jbe     short loc_1800EA615
0x1800ea612  mov     r14, [r14]
0x1800ea615  lea     rax, [rsp+1C8h+var_70]
0x1800ea61d  cmp     qword ptr [rsp+1C8h+var_60+8], 0Fh
0x1800ea626  cmova   rax, [rsp+1C8h+var_70]
0x1800ea62f  mov     [rsp+1C8h+var_198], rdx; size_t
0x1800ea634  mov     [rsp+1C8h+Src], rax; Src
0x1800ea639  mov     [rsp+1C8h+Size], rcx; Size
0x1800ea63e  mov     r9, r14
0x1800ea641  lea     rcx, [rsp+1C8h+var_178]; void *
0x1800ea646  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBD_K23@Z; std::string::string(std::_String_constructor_concat_tag,std::string const &,char const * const,unsigned __int64,char const * const,unsigned __int64)
0x1800ea64b  nop
0x1800ea64c  lea     rdx, [rsp+1C8h+var_D0]
0x1800ea654  lea     rcx, [rsp+1C8h+var_178]
0x1800ea659  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@@Z; std::string::append(std::string const &)
0x1800ea65e  xorps   xmm0, xmm0
0x1800ea661  movups  xmmword ptr [rsp+1C8h+var_F0], xmm0
0x1800ea669  xorps   xmm1, xmm1
0x1800ea66c  movdqu  xmmword ptr [rsp+1C8h+var_E0], xmm1
0x1800ea675  movups  xmm0, xmmword ptr [rax]
0x1800ea678  movups  xmmword ptr [rsp+1C8h+var_F0], xmm0
0x1800ea680  movups  xmm1, xmmword ptr [rax+10h]
0x1800ea684  movups  xmmword ptr [rsp+1C8h+var_E0], xmm1
0x1800ea68c  mov     [rax], r12b
0x1800ea68f  mov     [rax+10h], r12
0x1800ea693  mov     qword ptr [rax+18h], 0Fh
0x1800ea69b  lea     rcx, [rsp+1C8h+var_178]; void *
0x1800ea6a0  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800ea6a5  xorps   xmm0, xmm0
0x1800ea6a8  xorps   xmm1, xmm1
0x1800ea6ab  movdqu  [rsp+1C8h+var_108], xmm1
0x1800ea6b4  mov     [rsp+1C8h+var_F8], r12
0x1800ea6bc  movups  xmmword ptr [rsp+1C8h+hHash], xmm0
0x1800ea6c4  lea     rcx, [rsp+1C8h+hHash]; phHash
0x1800ea6cc  call    ??0CHash@@QEAA@XZ; CHash::CHash(void)
0x1800ea6d1  nop
0x1800ea6d2  lea     rdx, [rsp+1C8h+var_F0]
0x1800ea6da  cmp     [rsp+1C8h+var_E0+8], 0Fh
0x1800ea6e3  cmova   rdx, [rsp+1C8h+var_F0]; void *
0x1800ea6ec  lea     r9, [rsp+1C8h+var_108]
0x1800ea6f4  mov     r8, [rsp+1C8h+var_E0]; unsigned __int64
0x1800ea6fc  lea     rcx, [rsp+1C8h+hHash]; this
0x1800ea704  call    ?Hash@CHash@@QEAAXPEBX_KAEAV?$vector@EV?$allocator@E@std@@@std@@@Z; CHash::Hash(void const *,unsigned __int64,std::vector<uchar> &)
0x1800ea709  xorps   xmm0, xmm0
0x1800ea70c  movups  [rsp+1C8h+var_90], xmm0
0x1800ea714  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x1800ea71c  movdqu  [rsp+1C8h+var_80], xmm1
0x1800ea725  mov     byte ptr [rsp+1C8h+var_90], r12b
0x1800ea72d  mov     [rsp+1C8h+Size], r12; int
0x1800ea732  lea     r9, [rsp+1C8h+var_90]
0x1800ea73a  mov     edx, 1
0x1800ea73f  lea     r8d, [rdx+10h]
0x1800ea743  mov     rcx, [rbx+58h]
0x1800ea747  call    ??$_GetConfigOverrideFromProvider@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@CGlobalConfigManager@@AEBAJW4_ConfigProviderType@@IAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAW41@@Z; CGlobalConfigManager::_GetConfigOverrideFromProvider<std::string>(_ConfigProviderType,uint,std::string &,_ConfigProviderType *)
0x1800ea74c  nop
0x1800ea74d  lea     r8, [rsp+1C8h+var_90]
0x1800ea755  lea     rdx, [rsp+1C8h+var_B0]
0x1800ea75d  lea     rcx, [rsp+1C8h+var_108]
0x1800ea765  call    ?VerifyHashSignature@@YAJAEAV?$vector@EV?$allocator@E@std@@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@1@Z; VerifyHashSignature(std::vector<uchar> &,std::string const &,std::string const &)
0x1800ea76a  mov     edi, eax
0x1800ea76c  test    eax, eax
0x1800ea76e  jns     loc_1800EA7FF
0x1800ea774  mov     rcx, [rsp+1C8h]; this
0x1800ea77c  mov     r9d, eax; char *
0x1800ea77f  lea     r8, aCW1SSrcDeliver_6; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800ea786  mov     edx, 101h; void *
0x1800ea78b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ea790  nop
0x1800ea791  lea     rcx, [rsp+1C8h+var_90]; void *
0x1800ea799  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800ea79e  nop
0x1800ea79f  mov     rcx, [rsp+1C8h+hHash]; hHash
0x1800ea7a7  test    rcx, rcx
0x1800ea7aa  jz      short loc_1800EA7B3
0x1800ea7ac  call    cs:__imp_BCryptDestroyHash
0x1800ea7b2  nop
0x1800ea7b3  lea     rcx, [rsp+1C8h+var_108]
0x1800ea7bb  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800ea7c0  nop
0x1800ea7c1  lea     rcx, [rsp+1C8h+var_F0]; void *
0x1800ea7c9  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800ea7ce  nop
0x1800ea7cf  lea     rcx, [rsp+1C8h+var_70]; void *
0x1800ea7d7  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800ea7dc  nop
0x1800ea7dd  lea     rcx, [rsp+1C8h+var_B0]; void *
0x1800ea7e5  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800ea7ea  nop
0x1800ea7eb  lea     rcx, [rsp+1C8h+var_D0]; void *
0x1800ea7f3  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800ea7f8  mov     eax, edi
0x1800ea7fa  jmp     loc_1800EAA1E
0x1800ea7ff  xor     r8d, r8d
0x1800ea802  mov     edx, 8Ch
0x1800ea807  mov     rcx, [rbx+58h]
0x1800ea80b  call    ??$GetConfigValue@_N@CGlobalConfigManager@@QEBA_NW4Index@DOConfig@@PEAW4_ConfigProviderType@@@Z; CGlobalConfigManager::GetConfigValue<bool>(DOConfig::Index,_ConfigProviderType *)
0x1800ea810  test    al, al
0x1800ea812  jz      loc_1800EA92D
0x1800ea818  mov     ecx, [rbx+8]
0x1800ea81b  test    ecx, ecx
0x1800ea81d  jz      short loc_1800EA843
0x1800ea81f  sub     ecx, 2
0x1800ea822  jz      short loc_1800EA83C
0x1800ea824  sub     ecx, 1
0x1800ea827  jz      short loc_1800EA835
0x1800ea829  cmp     ecx, 1
0x1800ea82c  jnz     short loc_1800EA843
0x1800ea82e  mov     edx, 8Fh
0x1800ea833  jmp     short loc_1800EA848
0x1800ea835  mov     edx, 8Eh
0x1800ea83a  jmp     short loc_1800EA848
0x1800ea83c  mov     edx, 90h
0x1800ea841  jmp     short loc_1800EA848
0x1800ea843  mov     edx, 8Dh
0x1800ea848  xor     r8d, r8d
0x1800ea84b  mov     rcx, [rbx+58h]
  ... truncated ...
```
