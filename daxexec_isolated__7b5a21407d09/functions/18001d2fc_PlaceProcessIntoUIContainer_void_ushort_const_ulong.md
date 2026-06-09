# PlaceProcessIntoUIContainer(void *,ushort const *,ulong)

- ea: `0x18001d2fc`
- end: `0x18001d647`
- name: `?PlaceProcessIntoUIContainer@@YAXPEAXPEBGK@Z`
- size: `843`
- prototype: `void __fastcall(HANDLE hProcess, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800234e0`

## callees

- `0x180004f70`
- `0x1800125f4`
- `0x180013510`
- `0x1800136dc`
- `0x18001624c`
- `0x18001d2fc`
- `0x1800210fc`
- `0x180021118`
- `0x1800213d0`
- `0x18002211c`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d37f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d37f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d4d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d4d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d4b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d4b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d569`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d569`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d4c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d57f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d4c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d57f`
- `ntdll!NtQueryInformationProcess` at `0x18001d3dc`
- `ntdll!NtQueryInformationProcess` at `0x18001d3dc`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18001d35e`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18001d35e`
- `api-ms-win-core-job-l2-1-0!CreateJobObjectW` at `0x18001d513`
- `api-ms-win-core-job-l2-1-0!CreateJobObjectW` at `0x18001d513`
- `api-ms-win-core-job-l2-1-0!AssignProcessToJobObject` at `0x18001d543`
- `api-ms-win-core-job-l2-1-0!AssignProcessToJobObject` at `0x18001d543`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001d48a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001d48a`

## string_xrefs

- `0x18001d60e`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18001d5bd`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x18001d5d2`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x18001d5e4`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x18001d5f9`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x18001d620`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x18001d635`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x18001d357`: `user32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall PlaceProcessIntoUIContainer(HANDLE hProcess, const unsigned __int16 *a2, unsigned int a3)
{
  HMODULE LibraryW; // rax
  const char *v7; // r9
  const char *v8; // r9
  NTSTATUS v9; // eax
  __int64 v10; // rax
  int v11; // eax
  const char *v12; // r9
  PSECURITY_DESCRIPTOR v13; // r14
  _QWORD *v14; // rdi
  void *v15; // rsi
  DWORD LastError; // ebx
  const WCHAR *v17; // rdx
  unsigned __int16 *v18; // rbx
  const char *v19; // r9
  const char *v20; // r9
  int ReturnLength; // [rsp+20h] [rbp-89h]
  HLOCAL hMem; // [rsp+38h] [rbp-71h] BYREF
  __int64 ProcessInformation; // [rsp+40h] [rbp-69h] BYREF
  const unsigned __int16 *v24; // [rsp+48h] [rbp-61h] BYREF
  struct _SECURITY_ATTRIBUTES JobAttributes; // [rsp+50h] [rbp-59h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor[2]; // [rsp+68h] [rbp-41h] BYREF
  __m128i si128; // [rsp+78h] [rbp-31h]
  LPCWSTR lpName[2]; // [rsp+88h] [rbp-21h] BYREF
  __int64 v29; // [rsp+98h] [rbp-11h]
  unsigned __int64 v30; // [rsp+A0h] [rbp-9h]
  _BYTE v31[32]; // [rsp+A8h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v24 = a2;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SysSetJobUILimits>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SysSetJobUILimits>::GetImpl'::`2'::impl) )
  {
    if ( !qword_180109D58 )
    {
      LibraryW = LoadLibraryW(L"user32.dll");
      if ( !LibraryW )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x1F3,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
          v7);
      qword_180109D58 = (__int64)GetProcAddress(LibraryW, (LPCSTR)0xAFE);
      if ( !qword_180109D58 )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x1F5,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
          v8);
    }
    *(_OWORD *)lpName = 0;
    v29 = 0;
    v30 = 7;
    LOWORD(lpName[0]) = 0;
    if ( a2 )
    {
      ProcessInformation = 0;
      v9 = NtQueryInformationProcess(hProcess, ProcessLUIDDeviceMapsEnabled|0x40, &ProcessInformation, 8u, 0);
      if ( v9 < 0 )
        wil::details::in1diag3::Throw_NtStatus(
          retaddr,
          (void *)0x201,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
          (const char *)(unsigned int)v9,
          ReturnLength);
      v10 = std::to_wstring(v31);
      *(_OWORD *)SecurityDescriptor = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(SecurityDescriptor[0]) = 0;
      v11 = wil::str_concat_nothrow<std::wstring,unsigned short const *,unsigned short [2],std::wstring>(
              SecurityDescriptor,
              &v24,
              L"_",
              v10);
      if ( v11 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x7B3,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          (const char *)(unsigned int)v11,
          ReturnLength);
      std::wstring::operator=(lpName, SecurityDescriptor);
      std::wstring::~wstring(SecurityDescriptor);
      std::wstring::~wstring(v31);
    }
    hMem = 0;
    SecurityDescriptor[0] = &hMem;
    SecurityDescriptor[1] = 0;
    si128.m128i_i8[0] = 1;
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
            L"D:(A;;GA;;;SY)(A;;0x0004;;;ME)S:(ML;;NW;;;ME)",
            1u,
            &SecurityDescriptor[1],
            0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x215,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
        v12);
    if ( si128.m128i_i8[0] )
    {
      v13 = SecurityDescriptor[1];
      v14 = SecurityDescriptor[0];
      v15 = *(void **)SecurityDescriptor[0];
      if ( *(_QWORD *)SecurityDescriptor[0] )
      {
        LastError = GetLastError();
        LocalFree(v15);
        SetLastError(LastError);
      }
      *v14 = v13;
    }
    *(_QWORD *)&JobAttributes.nLength = 24;
    *(_QWORD *)&JobAttributes.bInheritHandle = 0;
    JobAttributes.lpSecurityDescriptor = hMem;
    if ( v29 )
    {
      v17 = (const WCHAR *)lpName;
      if ( v30 > 7 )
        v17 = lpName[0];
    }
    else
    {
      v17 = 0;
    }
    v18 = (unsigned __int16 *)CreateJobObjectW(&JobAttributes, v17);
    v24 = v18;
    if ( (((unsigned __int64)v18 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x231,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
        v19);
    if ( !AssignProcessToJobObject(v18, hProcess) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x237,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
        v20);
    ((void (__fastcall *)(unsigned __int16 *, _QWORD))qword_180109D58)(v18, a3);
    CloseHandle(v18);
    if ( hMem )
      LocalFree(hMem);
    std::wstring::~wstring(lpName);
  }
}

```

## disassembly

```asm
0x18001d2fc  mov     [rsp-8+arg_18], rbx
0x18001d301  push    rbp
0x18001d302  push    rsi
0x18001d303  push    rdi
0x18001d304  push    r12
0x18001d306  push    r13
0x18001d308  push    r14
0x18001d30a  push    r15
0x18001d30c  lea     rbp, [rsp-27h]
0x18001d311  sub     rsp, 0D0h
0x18001d318  mov     rax, cs:__security_cookie
0x18001d31f  xor     rax, rsp
0x18001d322  mov     [rbp+57h+var_38], rax
0x18001d326  mov     r12d, r8d
0x18001d329  mov     rbx, rdx
0x18001d32c  mov     r15, rcx
0x18001d32f  mov     [rbp+57h+var_B8], rdx
0x18001d333  xor     r13d, r13d
0x18001d336  mov     [rbp+57h+var_D0], r13d
0x18001d33a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SysSetJobUILimits@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SysSetJobUILimits@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SysSetJobUILimits> `wil::Feature<__WilFeatureTraits_Feature_SysSetJobUILimits>::GetImpl(void)'::`2'::impl
0x18001d341  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SysSetJobUILimits@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SysSetJobUILimits>::__private_IsEnabled(void)
0x18001d346  test    al, al
0x18001d348  jz      loc_18001D595
0x18001d34e  cmp     cs:qword_180109D58, r13
0x18001d355  jnz     short loc_18001D39F
0x18001d357  lea     rcx, LibFileName; "user32.dll"
0x18001d35e  call    cs:__imp_LoadLibraryW
0x18001d365  nop     dword ptr [rax+rax+00h]
0x18001d36a  mov     rcx, [rbp+5Fh]; this
0x18001d36e  test    rax, rax
0x18001d371  jz      loc_18001D5D2
0x18001d377  mov     edx, 0AFEh; lpProcName
0x18001d37c  mov     rcx, rax; hModule
0x18001d37f  call    cs:__imp_GetProcAddress
0x18001d386  nop     dword ptr [rax+rax+00h]
0x18001d38b  mov     cs:qword_180109D58, rax
0x18001d392  mov     rcx, [rbp+5Fh]; this
0x18001d396  test    rax, rax
0x18001d399  jz      loc_18001D5E4
0x18001d39f  xorps   xmm0, xmm0
0x18001d3a2  movups  xmmword ptr [rbp+57h+lpName], xmm0
0x18001d3a6  mov     [rbp+57h+var_68], r13
0x18001d3aa  mov     [rbp+57h+var_60], 7
0x18001d3b2  mov     word ptr [rbp+57h+lpName], r13w
0x18001d3b7  mov     edi, 1
0x18001d3bc  test    rbx, rbx
0x18001d3bf  jz      loc_18001D462
0x18001d3c5  mov     [rbp+57h+ProcessInformation], r13
0x18001d3c9  mov     qword ptr [rsp+100h+ReturnLength], r13; int
0x18001d3ce  lea     r9d, [rdi+7]; ProcessInformationLength
0x18001d3d2  lea     r8, [rbp+57h+ProcessInformation]; ProcessInformation
0x18001d3d6  lea     edx, [rdi+5Bh]; ProcessInformationClass
0x18001d3d9  mov     rcx, r15; ProcessHandle
0x18001d3dc  call    cs:__imp_NtQueryInformationProcess
0x18001d3e3  nop     dword ptr [rax+rax+00h]
0x18001d3e8  mov     rcx, [rbp+5Fh]; this
0x18001d3ec  test    eax, eax
0x18001d3ee  js      loc_18001D5F6
0x18001d3f4  mov     rdx, [rbp+57h+ProcessInformation]
0x18001d3f8  lea     rcx, [rbp+57h+var_58]; void *
0x18001d3fc  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::to_wstring(unsigned __int64)
0x18001d401  nop
0x18001d402  xorps   xmm0, xmm0
0x18001d405  movups  xmmword ptr [rbp+57h+SecurityDescriptor], xmm0
0x18001d409  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001d411  movdqu  [rbp+57h+var_88], xmm1
0x18001d416  mov     word ptr [rbp+57h+SecurityDescriptor], r13w
0x18001d41b  mov     [rbp+57h+var_D0], edi
0x18001d41e  mov     r9, rax
0x18001d421  lea     r8, asc_1800D7B48; "_"
0x18001d428  lea     rdx, [rbp+57h+var_B8]
0x18001d42c  lea     rcx, [rbp+57h+SecurityDescriptor]
0x18001d430  call    ??$str_concat_nothrow@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG$$BY01GV12@@wil@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBQEBGAEAY01$$CBGAEBV12@@Z; wil::str_concat_nothrow<std::wstring,ushort const *,ushort [2],std::wstring>(std::wstring &,ushort const * const &,ushort const (&)[2],std::wstring const &)
0x18001d435  mov     rcx, [rbp+5Fh]; this
0x18001d439  test    eax, eax
0x18001d43b  js      loc_18001D60B
0x18001d441  lea     rdx, [rbp+57h+SecurityDescriptor]
0x18001d445  lea     rcx, [rbp+57h+lpName]
0x18001d449  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001d44e  nop
0x18001d44f  lea     rcx, [rbp+57h+SecurityDescriptor]; void *
0x18001d453  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d458  nop
0x18001d459  lea     rcx, [rbp+57h+var_58]; void *
0x18001d45d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d462  mov     [rbp+57h+hMem], r13
0x18001d466  lea     rax, [rbp+57h+hMem]
0x18001d46a  mov     [rbp+57h+SecurityDescriptor], rax
0x18001d46e  mov     [rbp+57h+SecurityDescriptor+8], r13
0x18001d472  mov     byte ptr [rbp+57h+var_88], dil
0x18001d476  mov     rbx, [rbp+5Fh]
0x18001d47a  xor     r9d, r9d; SecurityDescriptorSize
0x18001d47d  lea     r8, [rbp+57h+SecurityDescriptor+8]; SecurityDescriptor
0x18001d481  mov     edx, edi; StringSDRevision
0x18001d483  lea     rcx, aDAGaSyA0x0004M; "D:(A;;GA;;;SY)(A;;0x0004;;;ME)S:(ML;;NW"...
0x18001d48a  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18001d491  nop     dword ptr [rax+rax+00h]
0x18001d496  test    eax, eax
0x18001d498  jz      loc_18001D620
0x18001d49e  cmp     byte ptr [rbp+57h+var_88], r13b
0x18001d4a2  jz      short loc_18001D4E2
0x18001d4a4  mov     r14, [rbp+57h+SecurityDescriptor+8]
0x18001d4a8  mov     rdi, [rbp+57h+SecurityDescriptor]
0x18001d4ac  mov     rsi, [rdi]
0x18001d4af  test    rsi, rsi
0x18001d4b2  jz      short loc_18001D4DF
0x18001d4b4  call    cs:__imp_GetLastError
0x18001d4bb  nop     dword ptr [rax+rax+00h]
0x18001d4c0  mov     ebx, eax
0x18001d4c2  mov     rcx, rsi; hMem
0x18001d4c5  call    cs:__imp_LocalFree
0x18001d4cc  nop     dword ptr [rax+rax+00h]
0x18001d4d1  mov     ecx, ebx; dwErrCode
0x18001d4d3  call    cs:__imp_SetLastError
0x18001d4da  nop     dword ptr [rax+rax+00h]
0x18001d4df  mov     [rdi], r14
0x18001d4e2  mov     qword ptr [rbp+57h+JobAttributes.nLength], 18h
0x18001d4ea  mov     qword ptr [rbp+57h+JobAttributes.bInheritHandle], r13
0x18001d4ee  mov     rax, [rbp+57h+hMem]
0x18001d4f2  mov     [rbp+57h+JobAttributes.lpSecurityDescriptor], rax
0x18001d4f6  cmp     [rbp+57h+var_68], r13
0x18001d4fa  jnz     short loc_18001D501
0x18001d4fc  mov     rdx, r13
0x18001d4ff  jmp     short loc_18001D50F
0x18001d501  lea     rdx, [rbp+57h+lpName]
0x18001d505  cmp     [rbp+57h+var_60], 7
0x18001d50a  cmova   rdx, [rbp+57h+lpName]; lpName
0x18001d50f  lea     rcx, [rbp+57h+JobAttributes]; lpJobAttributes
0x18001d513  call    cs:__imp_CreateJobObjectW
0x18001d51a  nop     dword ptr [rax+rax+00h]
0x18001d51f  mov     rbx, rax
0x18001d522  mov     [rbp+57h+var_B8], rax
0x18001d526  mov     rcx, [rbp+5Fh]; this
0x18001d52a  inc     rax
0x18001d52d  test    rax, 0FFFFFFFFFFFFFFFEh
0x18001d533  jz      loc_18001D635
0x18001d539  mov     rdi, [rbp+5Fh]
0x18001d53d  mov     rdx, r15; hProcess
0x18001d540  mov     rcx, rbx; hJob
0x18001d543  call    cs:__imp_AssignProcessToJobObject
0x18001d54a  nop     dword ptr [rax+rax+00h]
0x18001d54f  test    eax, eax
0x18001d551  jz      short loc_18001D5BD
0x18001d553  mov     edx, r12d
0x18001d556  mov     rcx, rbx
0x18001d559  mov     rax, cs:qword_180109D58
0x18001d560  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d565  nop
0x18001d566  mov     rcx, rbx; hObject
0x18001d569  call    cs:__imp_CloseHandle
0x18001d570  nop     dword ptr [rax+rax+00h]
0x18001d575  nop
0x18001d576  mov     rcx, [rbp+57h+hMem]; hMem
0x18001d57a  test    rcx, rcx
0x18001d57d  jz      short loc_18001D58C
0x18001d57f  call    cs:__imp_LocalFree
0x18001d586  nop     dword ptr [rax+rax+00h]
0x18001d58b  nop
0x18001d58c  lea     rcx, [rbp+57h+lpName]; void *
0x18001d590  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d595  mov     rcx, [rbp+57h+var_38]
0x18001d599  xor     rcx, rsp; StackCookie
0x18001d59c  call    __security_check_cookie
0x18001d5a1  mov     rbx, [rsp+100h+arg_18]
0x18001d5a9  add     rsp, 0D0h
0x18001d5b0  pop     r15
0x18001d5b2  pop     r14
0x18001d5b4  pop     r13
0x18001d5b6  pop     r12
0x18001d5b8  pop     rdi
0x18001d5b9  pop     rsi
0x18001d5ba  pop     rbp
0x18001d5bb  retn
0x18001d5bd  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\execmodel\\des"...
0x18001d5c4  mov     edx, 237h; void *
0x18001d5c9  mov     rcx, rdi; this
0x18001d5cc  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18001d5d2  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\execmodel\\des"...
0x18001d5d9  mov     edx, 1F3h; void *
0x18001d5de  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18001d5e4  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\execmodel\\des"...
0x18001d5eb  mov     edx, 1F5h; void *
0x18001d5f0  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18001d5f6  mov     r9d, eax; char *
0x18001d5f9  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\execmodel\\des"...
0x18001d600  mov     edx, 201h; void *
0x18001d605  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x18001d60b  mov     r9d, eax; char *
0x18001d60e  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001d615  mov     edx, 7B3h; void *
0x18001d61a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001d620  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\execmodel\\des"...
0x18001d627  mov     edx, 215h; void *
0x18001d62c  mov     rcx, rbx; this
0x18001d62f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18001d635  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\execmodel\\des"...
0x18001d63c  mov     edx, 231h; void *
0x18001d641  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
