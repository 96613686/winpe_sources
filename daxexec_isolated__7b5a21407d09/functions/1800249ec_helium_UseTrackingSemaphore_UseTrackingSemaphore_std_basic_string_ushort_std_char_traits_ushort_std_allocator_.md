# helium::UseTrackingSemaphore::UseTrackingSemaphore(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,void *)

- ea: `0x1800249ec`
- end: `0x180024d0e`
- name: `??0UseTrackingSemaphore@helium@@AEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z`
- size: `802`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180024fa0`
- `0x180025074`

## callees

- `0x180004f70`
- `0x180010d94`
- `0x180013510`
- `0x18001544c`
- `0x180016da0`
- `0x1800210fc`
- `0x180021118`
- `0x180022044`
- `0x180024778`
- `0x180024924`
- `0x1800249ec`
- `0x180025278`
- `0x180097fb8`
- `0x180098250`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180024b90`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180024b90`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024be9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024be9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024ba4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024bb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024ba4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024bb9`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180024aab`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180024aab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180024a98`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180024a98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024bcb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024bcb`
- `ntdll!NtQueryInformationToken` at `0x180024a78`
- `ntdll!NtQueryInformationToken` at `0x180024a78`
- `msvcp_win!??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180024c7f`
- `msvcp_win!??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180024c7f`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x180024ae7`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x180024ae7`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180024c8f`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180024c8f`

## string_xrefs

- `0x180024cd5`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180024c1b`: `Failed to create UseTrackingSemaphore: %ls (session:%d userToken:%d effectiveTokenSession:%d`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall helium::UseTrackingSemaphore::UseTrackingSemaphore(__int64 a1, _QWORD *a2, __int64 a3)
{
  __int64 v6; // rcx
  NTSTATUS v7; // eax
  DWORD CurrentProcessId; // eax
  const char *v9; // r9
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // r8
  int v14; // r13d
  BOOL v15; // r12d
  DWORD v16; // r15d
  LPCWSTR *v17; // rdi
  const WCHAR *v18; // r9
  HANDLE Semaphore; // rax
  HANDLE v20; // r14
  void *v21; // rbx
  DWORD LastError; // r15d
  const char *v23; // r9
  int ReturnLength; // [rsp+20h] [rbp-E0h]
  unsigned int TokenInformation; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pSessionId; // [rsp+54h] [rbp-ACh] BYREF
  DWORD v28; // [rsp+58h] [rbp-A8h]
  ULONG v29; // [rsp+5Ch] [rbp-A4h] BYREF
  __int64 v30; // [rsp+60h] [rbp-A0h]
  _BYTE v31[24]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v32[2]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v33[8]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v34[8]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v35[120]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v36[104]; // [rsp+118h] [rbp+18h] BYREF
  LPCWSTR lpName[4]; // [rsp+180h] [rbp+80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  v30 = a1;
  *(_BYTE *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  ImpersonationReverter::Revert(v31);
  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v32);
  TokenInformation = 0;
  v29 = 0;
  v6 = a3;
  if ( !a3 )
    v6 = -6;
  v7 = NtQueryInformationToken((HANDLE)v6, TokenSessionId, &TokenInformation, 4u, &v29);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0x29,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\usetrackingsemaphore.cpp",
      (const char *)(unsigned int)v7,
      ReturnLength);
  pSessionId = 0;
  CurrentProcessId = GetCurrentProcessId();
  if ( !ProcessIdToSessionId(CurrentProcessId, &pSessionId) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x2C,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\usetrackingsemaphore.cpp",
      v9);
  if ( pSessionId != TokenInformation )
  {
    v10 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v33, L"Session\\");
    v11 = std::basic_ostream<unsigned short>::operator<<(v10, TokenInformation);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v11, L"\\");
  }
  v12 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v33, L"DaxUseSemaphore_");
  v13 = a2[2];
  if ( a2[3] > 7u )
    a2 = (_QWORD *)*a2;
  std::_Insert_string<unsigned short,std::char_traits<unsigned short>,unsigned __int64>(v12, a2, v13);
  std::basic_stringbuf<unsigned short>::str(v34, lpName);
  v14 = TokenInformation;
  v15 = a3 != 0;
  v16 = pSessionId;
  v28 = pSessionId;
  if ( lpName[3] > (LPCWSTR)7 )
  {
    v17 = (LPCWSTR *)lpName[0];
    v18 = lpName[0];
  }
  else
  {
    v17 = lpName;
    v18 = (const WCHAR *)lpName;
  }
  Semaphore = CreateSemaphoreExW(0, 0, 0x7FFFFFFF, v18, 0, 0x100002u);
  v20 = Semaphore;
  if ( Semaphore )
  {
    GetLastError();
    v21 = *(void **)(a1 + 8);
    if ( v21 )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v21) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v23);
      SetLastError(LastError);
      v16 = v28;
    }
    *(_QWORD *)(a1 + 8) = v20;
    LOBYTE(Semaphore) = 1;
  }
  wil::details::in1diag3::Throw_GetLastErrorIfFalseMsg(
    retaddr,
    (void *)0x38,
    (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\usetrackingsemaphore.cpp",
    (const char *)(unsigned __int8)Semaphore,
    (bool)"Failed to create UseTrackingSemaphore: %ls (session:%d userToken:%d effectiveTokenSession:%d",
    (const char *)v17,
    v16,
    v15,
    v14);
  std::wstring::~wstring(lpName);
  *(_QWORD *)((char *)v32 + *(int *)(v32[0] + 4LL)) = &std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vftable';
  *(_DWORD *)&v31[*(int *)(v32[0] + 4LL) + 20] = *(_DWORD *)(v32[0] + 4LL) - 152;
  std::basic_stringbuf<unsigned short>::~basic_stringbuf<unsigned short>(v34);
  std::basic_iostream<unsigned short>::~basic_iostream<unsigned short,std::char_traits<unsigned short>>(v35);
  std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v36);
  ImpersonationReverter::~ImpersonationReverter((ImpersonationReverter *)v31);
  return a1;
}

```

## disassembly

```asm
0x1800249ec  mov     [rsp-8+arg_18], rbx
0x1800249f1  push    rbp
0x1800249f2  push    rsi
0x1800249f3  push    rdi
0x1800249f4  push    r12
0x1800249f6  push    r13
0x1800249f8  push    r14
0x1800249fa  push    r15
0x1800249fc  lea     rbp, [rsp-0B0h]
0x180024a04  sub     rsp, 1B0h
0x180024a0b  mov     rax, cs:__security_cookie
0x180024a12  xor     rax, rsp
0x180024a15  mov     [rbp+0E0h+var_40], rax
0x180024a1c  mov     rdi, r8
0x180024a1f  mov     rbx, rdx
0x180024a22  mov     rsi, rcx
0x180024a25  mov     [rsp+1E0h+var_180], rcx
0x180024a2a  xor     r14d, r14d
0x180024a2d  mov     [rcx], r14b
0x180024a30  mov     [rcx+8], r14
0x180024a34  lea     rcx, [rsp+1E0h+var_178]
0x180024a39  call    ?Revert@ImpersonationReverter@@SA?AU1@XZ; ImpersonationReverter::Revert(void)
0x180024a3e  nop
0x180024a3f  lea     rcx, [rbp+0E0h+var_160]
0x180024a43  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x180024a48  nop
0x180024a49  mov     [rsp+1E0h+TokenInformation], r14d
0x180024a4e  mov     [rsp+1E0h+var_184], r14d
0x180024a53  mov     rcx, rdi
0x180024a56  lea     rax, [r14-6]
0x180024a5a  test    rdi, rdi
0x180024a5d  cmovz   rcx, rax; TokenHandle
0x180024a61  lea     rax, [rsp+1E0h+var_184]
0x180024a66  mov     [rsp+1E0h+ReturnLength], rax; int
0x180024a6b  lea     r9d, [r14+4]; TokenInformationLength
0x180024a6f  lea     r8, [rsp+1E0h+TokenInformation]; TokenInformation
0x180024a74  lea     edx, [r14+0Ch]; TokenInformationClass
0x180024a78  call    cs:__imp_NtQueryInformationToken
0x180024a7f  nop     dword ptr [rax+rax+00h]
0x180024a84  mov     rcx, [rbp+0E8h]; this
0x180024a8b  test    eax, eax
0x180024a8d  js      loc_180024CE7
0x180024a93  mov     [rsp+1E0h+pSessionId], r14d
0x180024a98  call    cs:__imp_GetCurrentProcessId
0x180024a9f  nop     dword ptr [rax+rax+00h]
0x180024aa4  mov     ecx, eax; dwProcessId
0x180024aa6  lea     rdx, [rsp+1E0h+pSessionId]; pSessionId
0x180024aab  call    cs:__imp_ProcessIdToSessionId
0x180024ab2  nop     dword ptr [rax+rax+00h]
0x180024ab7  mov     rcx, [rbp+0E8h]; this
0x180024abe  test    eax, eax
0x180024ac0  jz      loc_180024CFC
0x180024ac6  mov     eax, [rsp+1E0h+TokenInformation]
0x180024aca  cmp     [rsp+1E0h+pSessionId], eax
0x180024ace  jz      short loc_180024B02
0x180024ad0  lea     rdx, aSession; "Session\\"
0x180024ad7  lea     rcx, [rbp+0E0h+var_150]
0x180024adb  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180024ae0  mov     edx, [rsp+1E0h+TokenInformation]
0x180024ae4  mov     rcx, rax
0x180024ae7  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x180024aee  nop     dword ptr [rax+rax+00h]
0x180024af3  mov     rcx, rax
0x180024af6  lea     rdx, S; "\\"
0x180024afd  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180024b02  lea     rdx, aDaxusesemaphor; "DaxUseSemaphore_"
0x180024b09  lea     rcx, [rbp+0E0h+var_150]
0x180024b0d  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180024b12  mov     r8, [rbx+10h]
0x180024b16  cmp     qword ptr [rbx+18h], 7
0x180024b1b  jbe     short loc_180024B20
0x180024b1d  mov     rbx, [rbx]
0x180024b20  mov     rdx, rbx
0x180024b23  mov     rcx, rax
0x180024b26  call    ??$_Insert_string@GU?$char_traits@G@std@@_K@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@QEBG_K@Z; std::_Insert_string<ushort,std::char_traits<ushort>,unsigned __int64>(std::basic_ostream<ushort> &,ushort const * const,unsigned __int64)
0x180024b2b  lea     rdx, [rbp+0E0h+lpName]
0x180024b32  lea     rcx, [rbp+0E0h+var_148]
0x180024b36  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x180024b3b  nop
0x180024b3c  mov     r13d, [rsp+1E0h+TokenInformation]
0x180024b41  mov     r12d, r14d
0x180024b44  test    rdi, rdi
0x180024b47  setnz   r12b
0x180024b4b  mov     r15d, [rsp+1E0h+pSessionId]
0x180024b50  mov     [rsp+1E0h+var_188], r15d
0x180024b55  cmp     [rbp+0E0h+var_48], 7
0x180024b5d  ja      short loc_180024B6F
0x180024b5f  lea     rdi, [rbp+0E0h+lpName]
0x180024b66  lea     r9, [rbp+0E0h+lpName]
0x180024b6d  jmp     short loc_180024B79
0x180024b6f  mov     rdi, [rbp+0E0h+lpName]
0x180024b76  mov     r9, rdi; lpName
0x180024b79  mov     [rsp+1E0h+dwDesiredAccess], 100002h; dwDesiredAccess
0x180024b81  mov     dword ptr [rsp+1E0h+ReturnLength], r14d; dwFlags
0x180024b86  xor     edx, edx; lInitialCount
0x180024b88  xor     ecx, ecx; lpSemaphoreAttributes
0x180024b8a  mov     r8d, 7FFFFFFFh; lMaximumCount
0x180024b90  call    cs:__imp_CreateSemaphoreExW
0x180024b97  nop     dword ptr [rax+rax+00h]
0x180024b9c  mov     r14, rax
0x180024b9f  test    rax, rax
0x180024ba2  jz      short loc_180024C00
0x180024ba4  call    cs:__imp_GetLastError
0x180024bab  nop     dword ptr [rax+rax+00h]
0x180024bb0  mov     rbx, [rsi+8]
0x180024bb4  test    rbx, rbx
0x180024bb7  jz      short loc_180024BFA
0x180024bb9  call    cs:__imp_GetLastError
0x180024bc0  nop     dword ptr [rax+rax+00h]
0x180024bc5  mov     r15d, eax
0x180024bc8  mov     rcx, rbx; hObject
0x180024bcb  call    cs:__imp_CloseHandle
0x180024bd2  nop     dword ptr [rax+rax+00h]
0x180024bd7  mov     rcx, [rbp+0E8h]; this
0x180024bde  test    eax, eax
0x180024be0  jz      loc_180024CD5
0x180024be6  mov     ecx, r15d; dwErrCode
0x180024be9  call    cs:__imp_SetLastError
0x180024bf0  nop     dword ptr [rax+rax+00h]
0x180024bf5  mov     r15d, [rsp+1E0h+var_188]
0x180024bfa  mov     [rsi+8], r14
0x180024bfe  mov     al, 1
0x180024c00  mov     rcx, [rbp+0E8h]; this
0x180024c07  mov     [rsp+1E0h+var_1A0], r13d
0x180024c0c  mov     [rsp+1E0h+var_1A8], r12d
0x180024c11  mov     [rsp+1E0h+var_1B0], r15d
0x180024c16  mov     qword ptr [rsp+1E0h+dwDesiredAccess], rdi; char *
0x180024c1b  lea     rdx, aFailedToCreate_0; "Failed to create UseTrackingSemaphore: "...
0x180024c22  mov     [rsp+1E0h+ReturnLength], rdx; bool
0x180024c27  movzx   r9d, al; char *
0x180024c2b  lea     r8, aOnecoreBaseApp_54; "onecore\\base\\appmodel\\execmodel\\des"...
0x180024c32  mov     edx, 38h ; '8'; void *
0x180024c37  call    ?Throw_GetLastErrorIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfFalseMsg(void *,uint,char const *,bool,char const *,...)
0x180024c3c  nop
0x180024c3d  lea     rcx, [rbp+0E0h+lpName]; void *
0x180024c44  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180024c49  nop
0x180024c4a  mov     rax, [rbp+0E0h+var_160]
0x180024c4e  movsxd  rcx, dword ptr [rax+4]
0x180024c52  lea     rax, ??_7?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vftable'
0x180024c59  mov     [rbp+rcx+0E0h+var_160], rax
0x180024c5e  mov     rcx, [rbp+0E0h+var_160]
0x180024c62  movsxd  rdx, dword ptr [rcx+4]
0x180024c66  lea     r8d, [rdx-98h]
0x180024c6d  mov     [rsp+rdx+1E0h+var_164], r8d
0x180024c72  lea     rcx, [rbp+0E0h+var_148]
0x180024c76  call    ??1?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEAA@XZ; std::basic_stringbuf<ushort>::~basic_stringbuf<ushort>(void)
0x180024c7b  lea     rcx, [rbp+0E0h+var_140]
0x180024c7f  call    cs:__imp_??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_iostream<ushort>::~basic_iostream<ushort,std::char_traits<ushort>>(void)
0x180024c86  nop     dword ptr [rax+rax+00h]
0x180024c8b  lea     rcx, [rbp+0E0h+var_C8]
0x180024c8f  call    cs:__imp_??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ios<ushort>::~basic_ios<ushort,std::char_traits<ushort>>(void)
0x180024c96  nop     dword ptr [rax+rax+00h]
0x180024c9b  nop
0x180024c9c  lea     rcx, [rsp+1E0h+var_178]; this
0x180024ca1  call    ??1ImpersonationReverter@@QEAA@XZ; ImpersonationReverter::~ImpersonationReverter(void)
0x180024ca6  nop
0x180024ca7  mov     rax, rsi
0x180024caa  mov     rcx, [rbp+0E0h+var_40]
0x180024cb1  xor     rcx, rsp; StackCookie
0x180024cb4  call    __security_check_cookie
0x180024cb9  mov     rbx, [rsp+1E0h+arg_18]
0x180024cc1  add     rsp, 1B0h
0x180024cc8  pop     r15
0x180024cca  pop     r14
0x180024ccc  pop     r13
0x180024cce  pop     r12
0x180024cd0  pop     rdi
0x180024cd1  pop     rsi
0x180024cd2  pop     rbp
0x180024cd3  retn
0x180024cd5  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180024cdc  mov     edx, 0A0Bh; void *
0x180024ce1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180024ce7  mov     r9d, eax; char *
0x180024cea  lea     r8, aOnecoreBaseApp_54; "onecore\\base\\appmodel\\execmodel\\des"...
0x180024cf1  mov     edx, 29h ; ')'; void *
0x180024cf6  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x180024cfc  lea     r8, aOnecoreBaseApp_54; "onecore\\base\\appmodel\\execmodel\\des"...
0x180024d03  mov     edx, 2Ch ; ','; void *
0x180024d08  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
