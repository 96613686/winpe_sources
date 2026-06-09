# RepoMan::FileSystem::GetTrustLevelOnFile(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x18018d138`
- end: `0x18018da7f`
- name: `?GetTrustLevelOnFile@FileSystem@RepoMan@@YA?AW4TrustResult@12@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `2375`
- prototype: `__int64 __fastcall(LPCCH lpMultiByteStr)`
- caller_count: `2`
- callee_count: `21`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800b8f08`
- `0x18018dbc0`

## callees

- `0x180002010`
- `0x180002874`
- `0x1800028e8`
- `0x180002aec`
- `0x180002ea0`
- `0x1800030d0`
- `0x1800136dc`
- `0x180024a68`
- `0x180024b44`
- `0x18002f940`
- `0x18002f9b0`
- `0x18002fdf0`
- `0x18018b53c`
- `0x18018ce58`
- `0x18018d138`
- `0x18018f6b0`
- `0x1801916bc`
- `0x180198f88`
- `0x18019a840`
- `0x18019a984`
- `0x18019f7a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18018d1dc`
- `KERNEL32!GetLastError` at `0x18018d472`
- `KERNEL32!GetLastError` at `0x18018d583`
- `KERNEL32!GetLastError` at `0x18018d81f`
- `KERNEL32!GetLastError` at `0x18018d1dc`
- `KERNEL32!GetLastError` at `0x18018d472`
- `KERNEL32!GetLastError` at `0x18018d583`
- `KERNEL32!GetLastError` at `0x18018d81f`
- `KERNEL32!CreateFileW` at `0x18018d370`
- `KERNEL32!CreateFileW` at `0x18018d370`
- `KERNEL32!GetProcAddress` at `0x18018d2f3`
- `KERNEL32!GetProcAddress` at `0x18018d306`
- `KERNEL32!GetProcAddress` at `0x18018d2f3`
- `KERNEL32!GetProcAddress` at `0x18018d306`
- `KERNEL32!GetModuleHandleW` at `0x18018d185`
- `KERNEL32!GetModuleHandleW` at `0x18018d185`

## string_xrefs

- `0x18018d2e9`: `SetCachedSigningLevel`
- `0x18018d17e`: `kernel32.dll`
- `0x18018d963`: `GetTrustLevelOnFile failed getting proc addr for get/set cached signing level.`
- `0x18018d2fc`: `GetCachedSigningLevel`

## pseudocode

```c
// Hidden C++ exception states: #wind=14 #try_helpers=1
char __fastcall RepoMan::FileSystem::GetTrustLevelOnFile(LPCCH lpMultiByteStr)
{
  HMODULE ModuleHandleW; // rax
  HMODULE v3; // rbx
  int v4; // eax
  DWORD LastError; // eax
  FARPROC ProcAddress; // r14
  FARPROC v8; // rax
  unsigned int (__fastcall *v9)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD); // rsi
  const WCHAR *v10; // rcx
  int v11; // eax
  DWORD v12; // eax
  int v13; // eax
  DWORD v14; // esi
  int v15; // eax
  int v16; // eax
  DWORD v17; // eax
  int v18; // eax
  int v19; // [rsp+40h] [rbp-208h] BYREF
  int v20; // [rsp+44h] [rbp-204h] BYREF
  _QWORD v21[3]; // [rsp+48h] [rbp-200h] BYREF
  _BYTE v22[16]; // [rsp+60h] [rbp-1E8h] BYREF
  _BYTE v23[8]; // [rsp+70h] [rbp-1D8h] BYREF
  _BYTE v24[128]; // [rsp+78h] [rbp-1D0h] BYREF
  _QWORD v25[15]; // [rsp+F8h] [rbp-150h] BYREF
  _BYTE v26[48]; // [rsp+170h] [rbp-D8h] BYREF
  __int64 v27; // [rsp+1A0h] [rbp-A8h] BYREF
  char v28; // [rsp+1A8h] [rbp-A0h] BYREF
  __m128i v29; // [rsp+1B0h] [rbp-98h] BYREF
  __int64 v30; // [rsp+1C0h] [rbp-88h] BYREF
  __int64 *v31; // [rsp+1C8h] [rbp-80h]
  __m128i si128; // [rsp+1D0h] [rbp-78h]
  LPCWSTR lpFileName[4]; // [rsp+1E0h] [rbp-68h] BYREF
  _BYTE v34[8]; // [rsp+200h] [rbp-48h] BYREF
  char v35; // [rsp+208h] [rbp-40h] BYREF
  char v36; // [rsp+210h] [rbp-38h] BYREF
  _BYTE v37[8]; // [rsp+218h] [rbp-30h] BYREF
  _BYTE v38[8]; // [rsp+220h] [rbp-28h] BYREF
  __int64 v39; // [rsp+228h] [rbp-20h] BYREF

  v21[1] = lpMultiByteStr;
  if ( !(unsigned __int8)RepoMan::FileSystem::CanBeSigned() )
    return -124;
  ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
  v3 = ModuleHandleW;
  if ( !ModuleHandleW )
  {
    RepoMan::Logger::Now(&v27);
    v4 = RepoMan::Global::Version(&v30);
    RepoMan::Logger::CreateValue((unsigned int)&v28, 1, 1, v4, 0);
    std::string::_Tidy_deallocate(&v30);
    LastError = GetLastError();
    RepoMan::Logger::ErrorCode(&v29, LastError);
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v22);
    std::operator<<<std::char_traits<char>>(
      (__int64)v23,
      (__int64)"GetTrustLevelOnFile failed getting module handle to kernel32");
    std::stringbuf::str(v24, &v30);
    RepoMan::Logger::CreateValue((unsigned int)&v29.m128i_u32[2], 1, 8, (unsigned int)&v30, 0);
    std::string::_Tidy_deallocate(&v30);
    v30 = 19937;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v25);
    v25[0] = &std::ios_base::`vftable';
    std::ios_base::_Ios_base_dtor((struct std::ios_base *)v25);
    v30 = (__int64)&v27;
    v31 = &v30;
    RepoMan::Logger::WriteEvent(4, &v30);
    `eh vector destructor iterator'(
      &v27,
      8u,
      4u,
      RepoMan::ILogger::Ptr<RepoMan::ILogger::IValue>::~Ptr<RepoMan::ILogger::IValue>);
    return -124;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "SetCachedSigningLevel");
  v8 = GetProcAddress(v3, "GetCachedSigningLevel");
  v9 = (unsigned int (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))v8;
  if ( ProcAddress && v8 )
  {
    RepoMan::utf8_to_wstring((LPWSTR)lpFileName, lpMultiByteStr);
    v10 = (const WCHAR *)lpFileName;
    if ( lpFileName[3] > (LPCWSTR)7 )
      v10 = lpFileName[0];
    v21[0] = CreateFileW(v10, 0x80000000, 5u, 0, 3u, 0x80u, 0);
    if ( v21[0] == -1 )
    {
      RepoMan::Logger::Now(v34);
      v11 = RepoMan::Global::Version(&v27);
      RepoMan::Logger::CreateValue((unsigned int)&v35, 1, 1, v11, 0);
      std::string::_Tidy_deallocate(&v27);
      std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v22);
      std::operator<<<std::char_traits<char>>((__int64)v23, (__int64)"GetTrustLevelOnFile could not obtain file handle");
      std::stringbuf::str(v24, &v27);
      RepoMan::Logger::CreateValue((unsigned int)&v36, 1, 8, (unsigned int)&v27, 0);
      std::string::_Tidy_deallocate(&v27);
      v27 = 19937;
      v29 = _mm_load_si128((const __m128i *)&_xmm);
      std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v25);
      v25[0] = &std::ios_base::`vftable';
      std::ios_base::_Ios_base_dtor((struct std::ios_base *)v25);
      v12 = GetLastError();
      RepoMan::Logger::ErrorCode(v37, v12);
      RepoMan::Logger::URI(v38, lpMultiByteStr);
      v30 = (__int64)v34;
      v31 = &v39;
      RepoMan::Logger::WriteEvent(2, &v30);
      `eh vector destructor iterator'(
        v34,
        8u,
        5u,
        RepoMan::ILogger::Ptr<RepoMan::ILogger::IValue>::~Ptr<RepoMan::ILogger::IValue>);
      std::wstring::_Tidy_deallocate(lpFileName);
      return -124;
    }
    v30 = (__int64)v21;
    sub_18018F6B0(v26, &v30);
    v20 = 0;
    v19 = 0;
    if ( !v9(v21[0], &v20, &v19, 0, 0, 0) || (v13 = v19) == 0 )
    {
      if ( !((unsigned int (__fastcall *)(_QWORD *, __int64, __int64, _QWORD))ProcAddress)(v21, 1, 5, v21[0]) )
      {
        v14 = GetLastError();
        if ( v14 != 577 )
        {
          RepoMan::Logger::Now(v34);
          v15 = RepoMan::Global::Version(&v27);
          RepoMan::Logger::CreateValue((unsigned int)&v35, 1, 1, v15, 0);
          std::string::_Tidy_deallocate(&v27);
          std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v22);
          std::operator<<<std::char_traits<char>>(
            (__int64)v23,
            (__int64)"GetTrustLevelOnFile failed setting the signing level");
          std::stringbuf::str(v24, &v27);
          RepoMan::Logger::CreateValue((unsigned int)&v36, 1, 8, (unsigned int)&v27, 0);
          std::string::_Tidy_deallocate(&v27);
          v27 = 19937;
          v29 = _mm_load_si128((const __m128i *)&_xmm);
          std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v25);
          v25[0] = &std::ios_base::`vftable';
          std::ios_base::_Ios_base_dtor((struct std::ios_base *)v25);
          RepoMan::Logger::ErrorCode(v37, v14);
          RepoMan::Logger::URI(v38, lpMultiByteStr);
          v30 = (__int64)v34;
          v31 = &v39;
          RepoMan::Logger::WriteEvent(2, &v30);
          `eh vector destructor iterator'(
            v34,
            8u,
            5u,
            RepoMan::ILogger::Ptr<RepoMan::ILogger::IValue>::~Ptr<RepoMan::ILogger::IValue>);
        }
        goto LABEL_19;
      }
      if ( !v9(v21[0], &v20, &v19, 0, 0, 0) )
      {
        RepoMan::Logger::Now(v34);
        v16 = RepoMan::Global::Version(&v27);
        RepoMan::Logger::CreateValue((unsigned int)&v35, 1, 1, v16, 0);
        std::string::_Tidy_deallocate(&v27);
        std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v22);
        std::operator<<<std::char_traits<char>>(
          (__int64)v23,
          (__int64)"GetTrustLevelOnFile failed to get level after setting it");
        std::stringbuf::str(v24, &v27);
        RepoMan::Logger::CreateValue((unsigned int)&v36, 1, 8, (unsigned int)&v27, 0);
        std::string::_Tidy_deallocate(&v27);
        v27 = 19937;
        v29 = _mm_load_si128((const __m128i *)&_xmm);
        std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v25);
        v25[0] = &std::ios_base::`vftable';
        std::ios_base::_Ios_base_dtor((struct std::ios_base *)v25);
        v17 = GetLastError();
        RepoMan::Logger::ErrorCode(v37, v17);
        RepoMan::Logger::URI(v38, lpMultiByteStr);
        v30 = (__int64)v34;
        v31 = &v39;
        RepoMan::Logger::WriteEvent(2, &v30);
        `eh vector destructor iterator'(
          v34,
          8u,
          5u,
          RepoMan::ILogger::Ptr<RepoMan::ILogger::IValue>::~Ptr<RepoMan::ILogger::IValue>);
        RepoMan::Meta::ScopeGuard::~ScopeGuard((RepoMan::Meta::ScopeGuard *)v26);
        std::wstring::_Tidy_deallocate(lpFileName);
        return -124;
      }
      v13 = v19;
    }
    if ( v13 == 1 )
    {
LABEL_19:
      RepoMan::Meta::ScopeGuard::~ScopeGuard((RepoMan::Meta::ScopeGuard *)v26);
      std::wstring::_Tidy_deallocate(lpFileName);
      return -124;
    }
    if ( v13 )
    {
      RepoMan::Meta::ScopeGuard::~ScopeGuard((RepoMan::Meta::ScopeGuard *)v26);
      std::wstring::_Tidy_deallocate(lpFileName);
      return 1;
    }
    else
    {
      RepoMan::Meta::ScopeGuard::~ScopeGuard((RepoMan::Meta::ScopeGuard *)v26);
      std::wstring::_Tidy_deallocate(lpFileName);
      return -126;
    }
  }
  else
  {
    RepoMan::Logger::Now(&v27);
    v18 = RepoMan::Global::Version(&v30);
    RepoMan::Logger::CreateValue((unsigned int)&v28, 1, 1, v18, 0);
    std::string::_Tidy_deallocate(&v30);
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v22);
    std::operator<<<std::char_traits<char>>(
      (__int64)v23,
      (__int64)"GetTrustLevelOnFile failed getting proc addr for get/set cached signing level.");
    std::stringbuf::str(v24, &v30);
    RepoMan::Logger::CreateValue((unsigned int)&v29, 1, 8, (unsigned int)&v30, 0);
    std::string::_Tidy_deallocate(&v30);
    v30 = 19937;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v25);
    v25[0] = &std::ios_base::`vftable';
    std::ios_base::_Ios_base_dtor((struct std::ios_base *)v25);
    v30 = (__int64)&v27;
    v31 = &v29.m128i_i64[1];
    RepoMan::Logger::WriteEvent(4, &v30);
    `eh vector destructor iterator'(
      &v27,
      8u,
      3u,
      RepoMan::ILogger::Ptr<RepoMan::ILogger::IValue>::~Ptr<RepoMan::ILogger::IValue>);
    return -124;
  }
}

```

## disassembly

```asm
0x18018d138  mov     [rsp+arg_8], rbx
0x18018d13d  mov     [rsp+arg_10], rsi
0x18018d142  mov     [rsp+arg_18], rdi
0x18018d147  push    r12
0x18018d149  push    r14
0x18018d14b  push    r15
0x18018d14d  sub     rsp, 230h
0x18018d154  mov     rax, cs:__security_cookie
0x18018d15b  xor     rax, rsp
0x18018d15e  mov     [rsp+248h+var_20], rax
0x18018d166  mov     rdi, rcx
0x18018d169  mov     [rsp+248h+var_1F8], rcx
0x18018d16e  xor     r15d, r15d
0x18018d171  call    ?CanBeSigned@FileSystem@RepoMan@@YA_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; RepoMan::FileSystem::CanBeSigned(std::string const &)
0x18018d176  test    al, al
0x18018d178  jz      loc_18018DA4D
0x18018d17e  lea     rcx, ModuleName; "kernel32.dll"
0x18018d185  call    cs:__imp_GetModuleHandleW
0x18018d18b  mov     rbx, rax
0x18018d18e  test    rax, rax
0x18018d191  jnz     loc_18018D2E9
0x18018d197  lea     rcx, [rsp+248h+var_A8]
0x18018d19f  call    ?Now@Logger@RepoMan@@SA?AV?$Ptr@VIValue@ILogger@RepoMan@@@ILogger@2@XZ; RepoMan::Logger::Now(void)
0x18018d1a4  lea     rcx, [rsp+248h+var_88]
0x18018d1ac  call    ?Version@Global@RepoMan@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; RepoMan::Global::Version(void)
0x18018d1b1  mov     qword ptr [rsp+248h+dwCreationDisposition], r15
0x18018d1b6  mov     r9, rax
0x18018d1b9  lea     ebx, [r15+1]
0x18018d1bd  mov     r8d, ebx
0x18018d1c0  mov     edx, ebx
0x18018d1c2  lea     rcx, [rsp+248h+var_A0]
0x18018d1ca  call    ?CreateValue@Logger@RepoMan@@SA?AV?$Ptr@VIValue@ILogger@RepoMan@@@ILogger@2@W4ValueType@42@W4Id@42@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_K@Z; RepoMan::Logger::CreateValue(RepoMan::ILogger::ValueType,RepoMan::ILogger::Id,std::string const &,unsigned __int64)
0x18018d1cf  lea     rcx, [rsp+248h+var_88]
0x18018d1d7  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18018d1dc  call    cs:__imp_GetLastError
0x18018d1e2  mov     edx, eax
0x18018d1e4  lea     rcx, [rsp+248h+var_98]
0x18018d1ec  call    ?ErrorCode@Logger@RepoMan@@SA?AV?$Ptr@VIValue@ILogger@RepoMan@@@ILogger@2@I@Z; RepoMan::Logger::ErrorCode(uint)
0x18018d1f1  nop
0x18018d1f2  lea     rcx, [rsp+248h+var_1E8]
0x18018d1f7  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x18018d1fc  lea     rdx, aGettrustlevelo_0; "GetTrustLevelOnFile failed getting modu"...
0x18018d203  lea     rcx, [rsp+248h+var_1D8]
0x18018d208  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18018d20d  lea     rdx, [rsp+248h+var_88]
0x18018d215  lea     rcx, [rsp+248h+var_1D0]
0x18018d21a  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEGBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x18018d21f  mov     qword ptr [rsp+248h+dwCreationDisposition], r15
0x18018d224  lea     r9, [rsp+248h+var_88]
0x18018d22c  lea     r14d, [r15+8]
0x18018d230  mov     r8d, r14d
0x18018d233  mov     edx, ebx
0x18018d235  lea     rcx, [rsp+248h+var_98+8]
0x18018d23d  call    ?CreateValue@Logger@RepoMan@@SA?AV?$Ptr@VIValue@ILogger@RepoMan@@@ILogger@2@W4ValueType@42@W4Id@42@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_K@Z; RepoMan::Logger::CreateValue(RepoMan::ILogger::ValueType,RepoMan::ILogger::Id,std::string const &,unsigned __int64)
0x18018d242  lea     rcx, [rsp+248h+var_88]
0x18018d24a  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18018d24f  mov     [rsp+248h+var_88], 4DE1h
0x18018d25b  movdqa  xmm0, cs:__xmm@000000000000001f0000000000000000
0x18018d263  movdqu  [rsp+248h+var_78], xmm0
0x18018d26c  lea     rcx, [rsp+248h+var_150]
0x18018d274  call    ??1?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@UEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x18018d279  nop
0x18018d27a  lea     rax, ??_7ios_base@std@@6B@; const std::ios_base::`vftable'
0x18018d281  mov     [rsp+248h+var_150], rax
0x18018d289  lea     rcx, [rsp+248h+var_150]; this
0x18018d291  call    ?_Ios_base_dtor@ios_base@std@@CAXPEAV12@@Z; std::ios_base::_Ios_base_dtor(std::ios_base *)
0x18018d296  nop
0x18018d297  lea     rax, [rsp+248h+var_A8]
0x18018d29f  mov     [rsp+248h+var_88], rax
0x18018d2a7  lea     rax, [rsp+248h+var_88]
0x18018d2af  mov     [rsp+248h+var_80], rax
0x18018d2b7  lea     rdx, [rsp+248h+var_88]
0x18018d2bf  lea     ecx, [rbx+3]
0x18018d2c2  call    ?WriteEvent@Logger@RepoMan@@SAXW4Verbosity@ILogger@2@V?$initializer_list@V?$Ptr@VIValue@ILogger@RepoMan@@@ILogger@RepoMan@@@std@@@Z; RepoMan::Logger::WriteEvent(RepoMan::ILogger::Verbosity,std::initializer_list<RepoMan::ILogger::Ptr<RepoMan::ILogger::IValue>>)
0x18018d2c7  lea     r9, ??1?$Ptr@VIValue@ILogger@RepoMan@@@ILogger@RepoMan@@QEAA@XZ; void (*)(void *)
0x18018d2ce  lea     r8d, [r15+4]; unsigned __int64
0x18018d2d2  mov     edx, r14d; unsigned __int64
0x18018d2d5  lea     rcx, [rsp+248h+var_A8]; void *
0x18018d2dd  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18018d2e2  mov     al, 84h
0x18018d2e4  jmp     loc_18018DA4F
0x18018d2e9  lea     rdx, aSetcachedsigni; "SetCachedSigningLevel"
0x18018d2f0  mov     rcx, rbx; hModule
0x18018d2f3  call    cs:__imp_GetProcAddress
0x18018d2f9  mov     r14, rax
0x18018d2fc  lea     rdx, aGetcachedsigni; "GetCachedSigningLevel"
0x18018d303  mov     rcx, rbx; hModule
0x18018d306  call    cs:__imp_GetProcAddress
0x18018d30c  mov     rsi, rax
0x18018d30f  test    r14, r14
0x18018d312  jz      loc_18018D912
0x18018d318  test    rax, rax
0x18018d31b  jz      loc_18018D912
0x18018d321  mov     rdx, rdi; lpMultiByteStr
0x18018d324  lea     rcx, [rsp+248h+lpFileName]; lpWideCharStr
0x18018d32c  call    ?utf8_to_wstring@RepoMan@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@@Z; RepoMan::utf8_to_wstring(std::string const &)
0x18018d331  nop
0x18018d332  lea     rcx, [rsp+248h+lpFileName]
0x18018d33a  cmp     [rsp+248h+var_50], 7
0x18018d343  cmova   rcx, [rsp+248h+lpFileName]; lpFileName
0x18018d34c  mov     [rsp+248h+hTemplateFile], r15; hTemplateFile
0x18018d351  mov     [rsp+248h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18018d359  mov     [rsp+248h+dwCreationDisposition], 3; dwCreationDisposition
0x18018d361  xor     r9d, r9d; lpSecurityAttributes
0x18018d364  lea     r12d, [r9+5]
0x18018d368  mov     r8d, r12d; dwShareMode
0x18018d36b  mov     edx, 80000000h; dwDesiredAccess
0x18018d370  call    cs:__imp_CreateFileW
0x18018d376  mov     [rsp+248h+var_200], rax
0x18018d37b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18018d37f  jnz     loc_18018D4F6
0x18018d385  lea     rcx, [rsp+248h+var_48]
0x18018d38d  call    ?Now@Logger@RepoMan@@SA?AV?$Ptr@VIValue@ILogger@RepoMan@@@ILogger@2@XZ; RepoMan::Logger::Now(void)
0x18018d392  lea     rcx, [rsp+248h+var_A8]
0x18018d39a  call    ?Version@Global@RepoMan@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; RepoMan::Global::Version(void)
0x18018d39f  mov     qword ptr [rsp+248h+dwCreationDisposition], r15
0x18018d3a4  mov     r9, rax
0x18018d3a7  lea     ebx, [r12-4]
0x18018d3ac  mov     r8d, ebx
0x18018d3af  mov     edx, ebx
0x18018d3b1  lea     rcx, [rsp+248h+var_40]
0x18018d3b9  call    ?CreateValue@Logger@RepoMan@@SA?AV?$Ptr@VIValue@ILogger@RepoMan@@@ILogger@2@W4ValueType@42@W4Id@42@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_K@Z; RepoMan::Logger::CreateValue(RepoMan::ILogger::ValueType,RepoMan::ILogger::Id,std::string const &,unsigned __int64)
0x18018d3be  lea     rcx, [rsp+248h+var_A8]
0x18018d3c6  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18018d3cb  nop
0x18018d3cc  lea     rcx, [rsp+248h+var_1E8]
0x18018d3d1  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x18018d3d6  lea     rdx, aGettrustlevelo_2; "GetTrustLevelOnFile could not obtain fi"...
0x18018d3dd  lea     rcx, [rsp+248h+var_1D8]
0x18018d3e2  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18018d3e7  lea     rdx, [rsp+248h+var_A8]
0x18018d3ef  lea     rcx, [rsp+248h+var_1D0]
0x18018d3f4  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEGBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x18018d3f9  mov     qword ptr [rsp+248h+dwCreationDisposition], r15
0x18018d3fe  lea     r9, [rsp+248h+var_A8]
0x18018d406  lea     r14d, [r12+3]
0x18018d40b  mov     r8d, r14d
0x18018d40e  mov     edx, ebx
0x18018d410  lea     rcx, [rsp+248h+var_38]
0x18018d418  call    ?CreateValue@Logger@RepoMan@@SA?AV?$Ptr@VIValue@ILogger@RepoMan@@@ILogger@2@W4ValueType@42@W4Id@42@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_K@Z; RepoMan::Logger::CreateValue(RepoMan::ILogger::ValueType,RepoMan::ILogger::Id,std::string const &,unsigned __int64)
0x18018d41d  lea     rcx, [rsp+248h+var_A8]
0x18018d425  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18018d42a  mov     [rsp+248h+var_A8], 4DE1h
0x18018d436  movdqa  xmm0, cs:__xmm@000000000000001f0000000000000000
0x18018d43e  movdqu  [rsp+248h+var_98], xmm0
0x18018d447  lea     rcx, [rsp+248h+var_150]
0x18018d44f  call    ??1?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@UEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x18018d454  nop
0x18018d455  lea     rax, ??_7ios_base@std@@6B@; const std::ios_base::`vftable'
0x18018d45c  mov     [rsp+248h+var_150], rax
0x18018d464  lea     rcx, [rsp+248h+var_150]; this
0x18018d46c  call    ?_Ios_base_dtor@ios_base@std@@CAXPEAV12@@Z; std::ios_base::_Ios_base_dtor(std::ios_base *)
0x18018d471  nop
0x18018d472  call    cs:__imp_GetLastError
0x18018d478  mov     edx, eax
0x18018d47a  lea     rcx, [rsp+248h+var_30]
0x18018d482  call    ?ErrorCode@Logger@RepoMan@@SA?AV?$Ptr@VIValue@ILogger@RepoMan@@@ILogger@2@I@Z; RepoMan::Logger::ErrorCode(uint)
0x18018d487  mov     rdx, rdi
0x18018d48a  lea     rcx, [rsp+248h+var_28]
0x18018d492  call    ?URI@Logger@RepoMan@@SA?AV?$Ptr@VIValue@ILogger@RepoMan@@@ILogger@2@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; RepoMan::Logger::URI(std::string const &)
0x18018d497  lea     rax, [rsp+248h+var_48]
0x18018d49f  mov     [rsp+248h+var_88], rax
0x18018d4a7  lea     rax, [rsp+248h+var_20]
0x18018d4af  mov     [rsp+248h+var_80], rax
0x18018d4b7  lea     rdx, [rsp+248h+var_88]
0x18018d4bf  lea     ecx, [rbx+1]
0x18018d4c2  call    ?WriteEvent@Logger@RepoMan@@SAXW4Verbosity@ILogger@2@V?$initializer_list@V?$Ptr@VIValue@ILogger@RepoMan@@@ILogger@RepoMan@@@std@@@Z; RepoMan::Logger::WriteEvent(RepoMan::ILogger::Verbosity,std::initializer_list<RepoMan::ILogger::Ptr<RepoMan::ILogger::IValue>>)
0x18018d4c7  lea     r9, ??1?$Ptr@VIValue@ILogger@RepoMan@@@ILogger@RepoMan@@QEAA@XZ; void (*)(void *)
0x18018d4ce  mov     r8d, r12d; unsigned __int64
0x18018d4d1  mov     edx, r14d; unsigned __int64
0x18018d4d4  lea     rcx, [rsp+248h+var_48]; void *
0x18018d4dc  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18018d4e1  nop
0x18018d4e2  lea     rcx, [rsp+248h+lpFileName]
0x18018d4ea  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18018d4ef  mov     al, 84h
0x18018d4f1  jmp     loc_18018DA4F
0x18018d4f6  lea     rax, [rsp+248h+var_200]
0x18018d4fb  mov     [rsp+248h+var_88], rax
0x18018d503  lea     rdx, [rsp+248h+var_88]
0x18018d50b  lea     rcx, [rsp+248h+var_D8]
0x18018d513  call    sub_18018F6B0
0x18018d518  nop
0x18018d519  mov     [rsp+248h+var_204], r15d
0x18018d51e  mov     [rsp+248h+var_208], r15d
0x18018d523  mov     qword ptr [rsp+248h+dwFlagsAndAttributes], r15
0x18018d528  mov     qword ptr [rsp+248h+dwCreationDisposition], r15
0x18018d52d  xor     r9d, r9d
0x18018d530  lea     r8, [rsp+248h+var_208]
0x18018d535  lea     rdx, [rsp+248h+var_204]
0x18018d53a  mov     rcx, [rsp+248h+var_200]
0x18018d53f  mov     rax, rsi
0x18018d542  call    cs:__guard_dispatch_icall_fptr
0x18018d548  test    eax, eax
0x18018d54a  jz      short loc_18018D55E
0x18018d54c  mov     eax, [rsp+248h+var_208]
0x18018d550  test    eax, eax
0x18018d552  jz      short loc_18018D55E
0x18018d554  mov     ebx, 1
0x18018d559  jmp     loc_18018D8B6
0x18018d55e  mov     r9, [rsp+248h+var_200]
0x18018d563  mov     r8d, r12d
0x18018d566  mov     ebx, 1
0x18018d56b  mov     edx, ebx
0x18018d56d  lea     rcx, [rsp+248h+var_200]
0x18018d572  mov     rax, r14
0x18018d575  call    cs:__guard_dispatch_icall_fptr
0x18018d57b  test    eax, eax
0x18018d57d  jnz     loc_18018D709
0x18018d583  call    cs:__imp_GetLastError
0x18018d589  mov     esi, eax
0x18018d58b  cmp     eax, 241h
0x18018d590  jz      loc_18018D6E7
0x18018d596  lea     rcx, [rsp+248h+var_48]
0x18018d59e  call    ?Now@Logger@RepoMan@@SA?AV?$Ptr@VIValue@ILogger@RepoMan@@@ILogger@2@XZ; RepoMan::Logger::Now(void)
0x18018d5a3  lea     rcx, [rsp+248h+var_A8]
0x18018d5ab  call    ?Version@Global@RepoMan@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; RepoMan::Global::Version(void)
0x18018d5b0  mov     qword ptr [rsp+248h+dwCreationDisposition], r15
0x18018d5b5  mov     r9, rax
0x18018d5b8  mov     r8d, ebx
0x18018d5bb  mov     edx, ebx
0x18018d5bd  lea     rcx, [rsp+248h+var_40]
0x18018d5c5  call    ?CreateValue@Logger@RepoMan@@SA?AV?$Ptr@VIValue@ILogger@RepoMan@@@ILogger@2@W4ValueType@42@W4Id@42@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_K@Z; RepoMan::Logger::CreateValue(RepoMan::ILogger::ValueType,RepoMan::ILogger::Id,std::string const &,unsigned __int64)
0x18018d5ca  lea     rcx, [rsp+248h+var_A8]
0x18018d5d2  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18018d5d7  nop
0x18018d5d8  lea     rcx, [rsp+248h+var_1E8]
0x18018d5dd  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x18018d5e2  lea     rdx, aGettrustlevelo; "GetTrustLevelOnFile failed setting the "...
0x18018d5e9  lea     rcx, [rsp+248h+var_1D8]
0x18018d5ee  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18018d5f3  lea     rdx, [rsp+248h+var_A8]
0x18018d5fb  lea     rcx, [rsp+248h+var_1D0]
0x18018d600  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEGBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x18018d605  mov     qword ptr [rsp+248h+dwCreationDisposition], r15
0x18018d60a  lea     r9, [rsp+248h+var_A8]
0x18018d612  lea     r14d, [rbx+7]
0x18018d616  mov     r8d, r14d
0x18018d619  mov     edx, ebx
0x18018d61b  lea     rcx, [rsp+248h+var_38]
0x18018d623  call    ?CreateValue@Logger@RepoMan@@SA?AV?$Ptr@VIValue@ILogger@RepoMan@@@ILogger@2@W4ValueType@42@W4Id@42@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_K@Z; RepoMan::Logger::CreateValue(RepoMan::ILogger::ValueType,RepoMan::ILogger::Id,std::string const &,unsigned __int64)
0x18018d628  lea     rcx, [rsp+248h+var_A8]
0x18018d630  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18018d635  mov     [rsp+248h+var_A8], 4DE1h
0x18018d641  movdqa  xmm0, cs:__xmm@000000000000001f0000000000000000
0x18018d649  movdqu  [rsp+248h+var_98], xmm0
0x18018d652  lea     rcx, [rsp+248h+var_150]
0x18018d65a  call    ??1?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@UEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x18018d65f  nop
0x18018d660  lea     rax, ??_7ios_base@std@@6B@; const std::ios_base::`vftable'
0x18018d667  mov     [rsp+248h+var_150], rax
0x18018d66f  lea     rcx, [rsp+248h+var_150]; this
0x18018d677  call    ?_Ios_base_dtor@ios_base@std@@CAXPEAV12@@Z; std::ios_base::_Ios_base_dtor(std::ios_base *)
0x18018d67c  nop
0x18018d67d  mov     edx, esi
0x18018d67f  lea     rcx, [rsp+248h+var_30]
0x18018d687  call    ?ErrorCode@Logger@RepoMan@@SA?AV?$Ptr@VIValue@ILogger@RepoMan@@@ILogger@2@I@Z; RepoMan::Logger::ErrorCode(uint)
0x18018d68c  mov     rdx, rdi
0x18018d68f  lea     rcx, [rsp+248h+var_28]
0x18018d697  call    ?URI@Logger@RepoMan@@SA?AV?$Ptr@VIValue@ILogger@RepoMan@@@ILogger@2@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; RepoMan::Logger::URI(std::string const &)
0x18018d69c  lea     rax, [rsp+248h+var_48]
0x18018d6a4  mov     [rsp+248h+var_88], rax
0x18018d6ac  lea     rax, [rsp+248h+var_20]
0x18018d6b4  mov     [rsp+248h+var_80], rax
0x18018d6bc  lea     rdx, [rsp+248h+var_88]
0x18018d6c4  lea     ecx, [rbx+1]
0x18018d6c7  call    ?WriteEvent@Logger@RepoMan@@SAXW4Verbosity@ILogger@2@V?$initializer_list@V?$Ptr@VIValue@ILogger@RepoMan@@@ILogger@RepoMan@@@std@@@Z; RepoMan::Logger::WriteEvent(RepoMan::ILogger::Verbosity,std::initializer_list<RepoMan::ILogger::Ptr<RepoMan::ILogger::IValue>>)
0x18018d6cc  lea     r9, ??1?$Ptr@VIValue@ILogger@RepoMan@@@ILogger@RepoMan@@QEAA@XZ; void (*)(void *)
0x18018d6d3  mov     r8, r12; unsigned __int64
0x18018d6d6  mov     edx, r14d; unsigned __int64
0x18018d6d9  lea     rcx, [rsp+248h+var_48]; void *
0x18018d6e1  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18018d6e6  nop
0x18018d6e7  lea     rcx, [rsp+248h+var_D8]; this
0x18018d6ef  call    ??1ScopeGuard@Meta@RepoMan@@QEAA@XZ; RepoMan::Meta::ScopeGuard::~ScopeGuard(void)
0x18018d6f4  nop
0x18018d6f5  lea     rcx, [rsp+248h+lpFileName]
0x18018d6fd  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18018d702  mov     al, 84h
0x18018d704  jmp     loc_18018DA4F
0x18018d709  mov     qword ptr [rsp+248h+dwFlagsAndAttributes], r15
0x18018d70e  mov     qword ptr [rsp+248h+dwCreationDisposition], r15
0x18018d713  xor     r9d, r9d
0x18018d716  lea     r8, [rsp+248h+var_208]
0x18018d71b  lea     rdx, [rsp+248h+var_204]
0x18018d720  mov     rcx, [rsp+248h+var_200]
0x18018d725  mov     rax, rsi
0x18018d728  call    cs:__guard_dispatch_icall_fptr
0x18018d72e  test    eax, eax
0x18018d730  jnz     loc_18018D8B2
0x18018d736  lea     rcx, [rsp+248h+var_48]
0x18018d73e  call    ?Now@Logger@RepoMan@@SA?AV?$Ptr@VIValue@ILogger@RepoMan@@@ILogger@2@XZ; RepoMan::Logger::Now(void)
0x18018d743  lea     rcx, [rsp+248h+var_A8]
0x18018d74b  call    ?Version@Global@RepoMan@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; RepoMan::Global::Version(void)
0x18018d750  mov     qword ptr [rsp+248h+dwCreationDisposition], r15
0x18018d755  mov     r9, rax
0x18018d758  mov     r8d, ebx
0x18018d75b  mov     edx, ebx
0x18018d75d  lea     rcx, [rsp+248h+var_40]
0x18018d765  call    ?CreateValue@Logger@RepoMan@@SA?AV?$Ptr@VIValue@ILogger@RepoMan@@@ILogger@2@W4ValueType@42@W4Id@42@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_K@Z; RepoMan::Logger::CreateValue(RepoMan::ILogger::ValueType,RepoMan::ILogger::Id,std::string const &,unsigned __int64)
  ... truncated ...
```
