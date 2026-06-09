# helium::UseTrackingSemaphore::UseTrackingSemaphore(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,void *)

- ea: `0x1800240f0`
- end: `0x1800243ba`
- name: `??0UseTrackingSemaphore@helium@@AEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z`
- size: `714`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180024600`
- `0x1800246e8`

## callees

- `0x1800053a0`
- `0x18000f2e0`
- `0x180011820`
- `0x18001366c`
- `0x18001513c`
- `0x18002031c`
- `0x180020338`
- `0x1800217f0`
- `0x180023e90`
- `0x180024030`
- `0x1800240f0`
- `0x1800248cc`
- `0x180096668`
- `0x180096894`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18002428d`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18002428d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800242a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800242a1`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800241a9`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800241a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180024196`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180024196`
- `ntdll!NtQueryInformationToken` at `0x180024177`
- `ntdll!NtQueryInformationToken` at `0x180024177`
- `msvcp_win!??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18002433d`
- `msvcp_win!??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18002433d`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x1800241e5`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x1800241e5`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18002434d`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18002434d`

## string_xrefs

- `0x1800242d9`: `Failed to create UseTrackingSemaphore: %ls (session:%d userToken:%d effectiveTokenSession:%d`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall helium::UseTrackingSemaphore::UseTrackingSemaphore(__int64 a1, _QWORD *a2, __int64 a3)
{
  unsigned __int8 v6; // bl
  __int64 v7; // rcx
  NTSTATUS v8; // eax
  DWORD CurrentProcessId; // eax
  const char *v10; // r9
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // r8
  int v15; // r13d
  BOOL v16; // r12d
  LPCWSTR *v17; // r15
  const WCHAR *v18; // r9
  HANDLE Semaphore; // rdi
  int ReturnLength; // [rsp+20h] [rbp-E0h]
  unsigned int TokenInformation; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pSessionId; // [rsp+54h] [rbp-ACh] BYREF
  DWORD v24; // [rsp+58h] [rbp-A8h]
  ULONG v25; // [rsp+5Ch] [rbp-A4h] BYREF
  __int64 v26; // [rsp+60h] [rbp-A0h]
  _BYTE v27[24]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v28[2]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v29[8]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v30[8]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v31[120]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v32[104]; // [rsp+118h] [rbp+18h] BYREF
  LPCWSTR lpName[3]; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int64 v34; // [rsp+198h] [rbp+98h]
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  v26 = a1;
  v6 = 0;
  *(_BYTE *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  ImpersonationReverter::Revert(v27);
  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v28);
  TokenInformation = 0;
  v25 = 0;
  v7 = a3;
  if ( !a3 )
    v7 = -6;
  v8 = NtQueryInformationToken((HANDLE)v7, TokenSessionId, &TokenInformation, 4u, &v25);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0x29,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\usetrackingsemaphore.cpp",
      (const char *)(unsigned int)v8,
      ReturnLength);
  pSessionId = 0;
  CurrentProcessId = GetCurrentProcessId();
  if ( !ProcessIdToSessionId(CurrentProcessId, &pSessionId) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x2C,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\usetrackingsemaphore.cpp",
      v10);
  if ( pSessionId != TokenInformation )
  {
    v11 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v29, L"Session\\");
    v12 = std::basic_ostream<unsigned short>::operator<<(v11, TokenInformation);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v12, L"\\");
  }
  v13 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v29, L"DaxUseSemaphore_");
  v14 = a2[2];
  if ( a2[3] > 7u )
    a2 = (_QWORD *)*a2;
  std::_Insert_string<unsigned short,std::char_traits<unsigned short>,unsigned __int64>(v13, a2, v14);
  std::basic_stringbuf<unsigned short>::str(v30, lpName);
  v15 = TokenInformation;
  v16 = a3 != 0;
  v24 = pSessionId;
  v17 = lpName;
  if ( v34 > 7 )
    v17 = (LPCWSTR *)lpName[0];
  v18 = (const WCHAR *)lpName;
  if ( v34 > 7 )
    v18 = lpName[0];
  Semaphore = CreateSemaphoreExW(0, 0, 0x7FFFFFFF, v18, 0, 0x100002u);
  if ( Semaphore )
  {
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      a1 + 8,
      Semaphore);
    v6 = 1;
  }
  wil::details::in1diag3::Throw_GetLastErrorIfFalseMsg(
    retaddr,
    (void *)0x38,
    (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\usetrackingsemaphore.cpp",
    (const char *)v6,
    (bool)"Failed to create UseTrackingSemaphore: %ls (session:%d userToken:%d effectiveTokenSession:%d",
    (const char *)v17,
    v24,
    v16,
    v15);
  std::wstring::~wstring(lpName);
  *(_QWORD *)((char *)v28 + *(int *)(v28[0] + 4LL)) = &std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vftable';
  *(_DWORD *)&v27[*(int *)(v28[0] + 4LL) + 20] = *(_DWORD *)(v28[0] + 4LL) - 152;
  std::basic_stringbuf<unsigned short>::~basic_stringbuf<unsigned short>(v30);
  std::basic_iostream<unsigned short>::~basic_iostream<unsigned short,std::char_traits<unsigned short>>(v31);
  std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v32);
  ImpersonationReverter::~ImpersonationReverter((ImpersonationReverter *)v27);
  return a1;
}

```

## disassembly

```asm
0x1800240f0  mov     [rsp-8+arg_18], rbx
0x1800240f5  push    rbp
0x1800240f6  push    rsi
0x1800240f7  push    rdi
0x1800240f8  push    r12
0x1800240fa  push    r13
0x1800240fc  push    r14
0x1800240fe  push    r15
0x180024100  lea     rbp, [rsp-0B0h]
0x180024108  sub     rsp, 1B0h
0x18002410f  mov     rax, cs:__security_cookie
0x180024116  xor     rax, rsp
0x180024119  mov     [rbp+0E0h+var_40], rax
0x180024120  mov     r15, r8
0x180024123  mov     rdi, rdx
0x180024126  mov     rsi, rcx
0x180024129  mov     [rsp+1E0h+var_180], rcx
0x18002412e  xor     ebx, ebx
0x180024130  mov     [rcx], bl
0x180024132  mov     [rcx+8], rbx
0x180024136  lea     rcx, [rsp+1E0h+var_178]
0x18002413b  call    ?Revert@ImpersonationReverter@@SA?AU1@XZ; ImpersonationReverter::Revert(void)
0x180024140  nop
0x180024141  lea     rcx, [rbp+0E0h+var_160]
0x180024145  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x18002414a  nop
0x18002414b  mov     [rsp+1E0h+TokenInformation], ebx
0x18002414f  mov     [rsp+1E0h+var_184], ebx
0x180024153  mov     rcx, r15
0x180024156  lea     rax, [rbx-6]
0x18002415a  test    r15, r15
0x18002415d  cmovz   rcx, rax; TokenHandle
0x180024161  lea     rax, [rsp+1E0h+var_184]
0x180024166  mov     [rsp+1E0h+ReturnLength], rax; int
0x18002416b  lea     r9d, [rbx+4]; TokenInformationLength
0x18002416f  lea     r8, [rsp+1E0h+TokenInformation]; TokenInformation
0x180024174  lea     edx, [rbx+0Ch]; TokenInformationClass
0x180024177  call    cs:__imp_NtQueryInformationToken
0x18002417e  nop     dword ptr [rax+rax+00h]
0x180024183  mov     rcx, [rbp+0E8h]; this
0x18002418a  test    eax, eax
0x18002418c  js      loc_1800243A5
0x180024192  mov     [rsp+1E0h+pSessionId], ebx
0x180024196  call    cs:__imp_GetCurrentProcessId
0x18002419d  nop     dword ptr [rax+rax+00h]
0x1800241a2  mov     ecx, eax; dwProcessId
0x1800241a4  lea     rdx, [rsp+1E0h+pSessionId]; pSessionId
0x1800241a9  call    cs:__imp_ProcessIdToSessionId
0x1800241b0  nop     dword ptr [rax+rax+00h]
0x1800241b5  mov     rcx, [rbp+0E8h]; this
0x1800241bc  test    eax, eax
0x1800241be  jz      loc_180024393
0x1800241c4  mov     eax, [rsp+1E0h+TokenInformation]
0x1800241c8  cmp     [rsp+1E0h+pSessionId], eax
0x1800241cc  jz      short loc_180024200
0x1800241ce  lea     rdx, aSession; "Session\\"
0x1800241d5  lea     rcx, [rbp+0E0h+var_150]
0x1800241d9  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1800241de  mov     edx, [rsp+1E0h+TokenInformation]
0x1800241e2  mov     rcx, rax
0x1800241e5  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x1800241ec  nop     dword ptr [rax+rax+00h]
0x1800241f1  mov     rcx, rax
0x1800241f4  lea     rdx, asc_1800D5864; "\\"
0x1800241fb  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180024200  lea     rdx, aDaxusesemaphor; "DaxUseSemaphore_"
0x180024207  lea     rcx, [rbp+0E0h+var_150]
0x18002420b  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180024210  mov     r8, [rdi+10h]
0x180024214  cmp     qword ptr [rdi+18h], 7
0x180024219  jbe     short loc_18002421E
0x18002421b  mov     rdi, [rdi]
0x18002421e  mov     rdx, rdi
0x180024221  mov     rcx, rax
0x180024224  call    ??$_Insert_string@GU?$char_traits@G@std@@_K@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@QEBG_K@Z; std::_Insert_string<ushort,std::char_traits<ushort>,unsigned __int64>(std::basic_ostream<ushort> &,ushort const * const,unsigned __int64)
0x180024229  lea     rdx, [rbp+0E0h+lpName]
0x180024230  lea     rcx, [rbp+0E0h+var_148]
0x180024234  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x180024239  nop
0x18002423a  mov     r13d, [rsp+1E0h+TokenInformation]
0x18002423f  mov     r12d, ebx
0x180024242  test    r15, r15
0x180024245  setnz   r12b
0x180024249  mov     eax, [rsp+1E0h+pSessionId]
0x18002424d  mov     [rsp+1E0h+var_188], eax
0x180024251  lea     r15, [rbp+0E0h+lpName]
0x180024258  cmp     [rbp+0E0h+var_48], 7
0x180024260  cmova   r15, [rbp+0E0h+lpName]
0x180024268  lea     r9, [rbp+0E0h+lpName]
0x18002426f  cmova   r9, [rbp+0E0h+lpName]; lpName
0x180024277  mov     [rsp+1E0h+dwDesiredAccess], 100002h; dwDesiredAccess
0x18002427f  mov     dword ptr [rsp+1E0h+ReturnLength], ebx; dwFlags
0x180024283  xor     edx, edx; lInitialCount
0x180024285  xor     ecx, ecx; lpSemaphoreAttributes
0x180024287  mov     r8d, 7FFFFFFFh; lMaximumCount
0x18002428d  call    cs:__imp_CreateSemaphoreExW
0x180024294  nop     dword ptr [rax+rax+00h]
0x180024299  mov     rdi, rax
0x18002429c  test    rax, rax
0x18002429f  jz      short loc_1800242BB
0x1800242a1  call    cs:__imp_GetLastError
0x1800242a8  nop     dword ptr [rax+rax+00h]
0x1800242ad  mov     rdx, rdi
0x1800242b0  lea     rcx, [rsi+8]
0x1800242b4  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800242b9  mov     bl, 1
0x1800242bb  mov     rcx, [rbp+0E8h]; this
0x1800242c2  mov     [rsp+1E0h+var_1A0], r13d
0x1800242c7  mov     [rsp+1E0h+var_1A8], r12d
0x1800242cc  mov     eax, [rsp+1E0h+var_188]
0x1800242d0  mov     [rsp+1E0h+var_1B0], eax
0x1800242d4  mov     qword ptr [rsp+1E0h+dwDesiredAccess], r15; char *
0x1800242d9  lea     rax, aFailedToCreate_0; "Failed to create UseTrackingSemaphore: "...
0x1800242e0  mov     [rsp+1E0h+ReturnLength], rax; bool
0x1800242e5  movzx   r9d, bl; char *
0x1800242e9  lea     r8, aOnecoreBaseApp_53; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800242f0  mov     edx, 38h ; '8'; void *
0x1800242f5  call    ?Throw_GetLastErrorIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfFalseMsg(void *,uint,char const *,bool,char const *,...)
0x1800242fa  nop
0x1800242fb  lea     rcx, [rbp+0E0h+lpName]; void *
0x180024302  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180024307  nop
0x180024308  mov     rax, [rbp+0E0h+var_160]
0x18002430c  movsxd  rcx, dword ptr [rax+4]
0x180024310  lea     rax, ??_7?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vftable'
0x180024317  mov     [rbp+rcx+0E0h+var_160], rax
0x18002431c  mov     rcx, [rbp+0E0h+var_160]
0x180024320  movsxd  rdx, dword ptr [rcx+4]
0x180024324  lea     r8d, [rdx-98h]
0x18002432b  mov     [rsp+rdx+1E0h+var_164], r8d
0x180024330  lea     rcx, [rbp+0E0h+var_148]
0x180024334  call    ??1?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEAA@XZ; std::basic_stringbuf<ushort>::~basic_stringbuf<ushort>(void)
0x180024339  lea     rcx, [rbp+0E0h+var_140]
0x18002433d  call    cs:__imp_??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_iostream<ushort>::~basic_iostream<ushort,std::char_traits<ushort>>(void)
0x180024344  nop     dword ptr [rax+rax+00h]
0x180024349  lea     rcx, [rbp+0E0h+var_C8]
0x18002434d  call    cs:__imp_??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ios<ushort>::~basic_ios<ushort,std::char_traits<ushort>>(void)
0x180024354  nop     dword ptr [rax+rax+00h]
0x180024359  nop
0x18002435a  lea     rcx, [rsp+1E0h+var_178]; this
0x18002435f  call    ??1ImpersonationReverter@@QEAA@XZ; ImpersonationReverter::~ImpersonationReverter(void)
0x180024364  nop
0x180024365  mov     rax, rsi
0x180024368  mov     rcx, [rbp+0E0h+var_40]
0x18002436f  xor     rcx, rsp; StackCookie
0x180024372  call    __security_check_cookie
0x180024377  mov     rbx, [rsp+1E0h+arg_18]
0x18002437f  add     rsp, 1B0h
0x180024386  pop     r15
0x180024388  pop     r14
0x18002438a  pop     r13
0x18002438c  pop     r12
0x18002438e  pop     rdi
0x18002438f  pop     rsi
0x180024390  pop     rbp
0x180024391  retn
0x180024393  lea     r8, aOnecoreBaseApp_53; "onecore\\base\\appmodel\\execmodel\\des"...
0x18002439a  mov     edx, 2Ch ; ','; void *
0x18002439f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800243a5  mov     r9d, eax; char *
0x1800243a8  lea     r8, aOnecoreBaseApp_53; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800243af  mov     edx, 29h ; ')'; void *
0x1800243b4  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
```
