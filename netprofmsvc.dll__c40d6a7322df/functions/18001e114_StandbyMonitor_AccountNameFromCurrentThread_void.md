# StandbyMonitor::AccountNameFromCurrentThread(void)

- ea: `0x18001e114`
- end: `0x18001e4b4`
- name: `?AccountNameFromCurrentThread@StandbyMonitor@@YA@XZ`
- size: `928`
- prototype: `__int64 __fastcall(StandbyMonitor *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001e0d0`
- `0x180121380`

## callees

- `0x180015410`
- `0x180015608`
- `0x180015ab0`
- `0x18001e114`
- `0x18001e4bc`
- `0x18001e920`
- `0x18006f500`
- `0x1800a88a0`
- `0x1800a8d64`
- `0x1800baf04`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e22b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e22b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001e149`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001e149`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001e160`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001e160`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e494`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e49f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e494`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e49f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001e18e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001e18e`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001e1c6`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001e1c6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e19a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e19a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e266`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e3d9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e266`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e3d9`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalA` at `0x18001e21d`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalA` at `0x18001e36a`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalA` at `0x18001e21d`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalA` at `0x18001e36a`

## string_xrefs

- `0x18001e2c7`: `onecore\net\netprofiles\service\src\standby\lib\standbymonitorshim.cpp`
- `0x18001e41a`: `onecore\net\netprofiles\service\src\standby\lib\standbymonitorshim.cpp`
- `0x18001e42f`: `onecore\net\netprofiles\service\src\standby\lib\standbymonitorshim.cpp`
- `0x18001e441`: `onecore\net\netprofiles\service\src\standby\lib\standbymonitorshim.cpp`
- `0x18001e453`: `onecore\net\netprofiles\service\src\standby\lib\standbymonitorshim.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
StandbyMonitor *__fastcall StandbyMonitor::AccountNameFromCurrentThread(StandbyMonitor *this)
{
  HANDLE CurrentThread; // rax
  BOOL v3; // eax
  const char *v4; // r9
  DWORD LengthSid; // esi
  HLOCAL v6; // rax
  void *v7; // rbx
  const char *v8; // r9
  __int64 v9; // rdx
  const char *v10; // r9
  void *v11; // rcx
  StandbyMonitor *result; // rax
  __int64 v13; // rdx
  CHAR *v14; // r9
  CHAR *v15; // rdx
  const char *v16; // r9
  __m128i si128; // xmm0
  void *v18; // rcx
  int cchReferencedDomainName; // [rsp+20h] [rbp-98h]
  int cchReferencedDomainNamea; // [rsp+20h] [rbp-98h]
  void *Block; // [rsp+30h] [rbp-88h] BYREF
  StandbyMonitor *v22; // [rsp+38h] [rbp-80h]
  HLOCAL v23; // [rsp+48h] [rbp-70h]
  DWORD v24; // [rsp+50h] [rbp-68h] BYREF
  DWORD cchName; // [rsp+54h] [rbp-64h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+58h] [rbp-60h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp-58h] BYREF
  LPSTR Name[2]; // [rsp+68h] [rbp-50h] BYREF
  __m128i v29; // [rsp+78h] [rbp-40h]
  LPSTR ReferencedDomainName[2]; // [rsp+88h] [rbp-30h] BYREF
  __m128i v31; // [rsp+98h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v22 = this;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  v3 = OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle);
  try
  {
    if ( !v3 )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x2E,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\standby\\lib\\standbymonitorshim.cpp",
        v4);
    wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(&Block, TokenHandle);
    LengthSid = GetLengthSid(*(PSID *)Block);
    v6 = LocalAlloc(0, LengthSid);
    v7 = v6;
    v23 = v6;
    if ( !v6 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x32,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\standby\\lib\\standbymonitorshim.cpp",
        (const char *)0x80070008LL,
        cchReferencedDomainName);
    if ( !CopySid(LengthSid, v6, *(PSID *)Block) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x33,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\standby\\lib\\standbymonitorshim.cpp",
        v8);
    cchName = 0;
    v24 = 0;
    peUse = SidTypeInvalid;
    if ( LookupAccountSidLocalA(v7, 0, &cchName, 0, &v24, &peUse) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3A,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\standby\\lib\\standbymonitorshim.cpp",
        (const char *)0x8000FFFFLL,
        cchReferencedDomainNamea);
    if ( GetLastError() == 122 )
    {
      *(_OWORD *)Name = 0;
      v29 = 0;
      std::string::_Construct<0,char>(Name, v9, cchName);
      *(_OWORD *)ReferencedDomainName = 0;
      v31 = 0;
      std::string::_Construct<0,char>(ReferencedDomainName, v13, v24);
      v14 = (CHAR *)ReferencedDomainName;
      if ( v31.m128i_i64[1] > 0xFuLL )
        v14 = ReferencedDomainName[0];
      v15 = (CHAR *)Name;
      if ( v29.m128i_i64[1] > 0xFuLL )
        v15 = Name[0];
      if ( !LookupAccountSidLocalA(v7, v15, &cchName, v14, &v24, &peUse) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x40,
          (unsigned int)"onecore\\net\\netprofiles\\service\\src\\standby\\lib\\standbymonitorshim.cpp",
          v16);
      std::string::string(this, Name);
      if ( v31.m128i_i64[1] > 0xFuLL )
        std::_Deallocate<16>(ReferencedDomainName[0], v31.m128i_i64[1] + 1);
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      v31 = si128;
      LOBYTE(ReferencedDomainName[0]) = 0;
      if ( v29.m128i_i64[1] > 0xFuLL )
      {
        std::_Deallocate<16>(Name[0], v29.m128i_i64[1] + 1);
        si128 = _mm_load_si128((const __m128i *)&_xmm);
      }
      v29 = si128;
      LOBYTE(Name[0]) = 0;
      LocalFree(v7);
      v18 = Block;
      Block = 0;
      if ( v18 )
        operator delete(v18);
      if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(TokenHandle);
      result = this;
    }
    else
    {
      *(_OWORD *)this = 0;
      *((_QWORD *)this + 2) = 0;
      *((_QWORD *)this + 3) = 0;
      std::string::_Construct<1,char const *>(this, &Src, 0);
      LocalFree(v7);
      v11 = Block;
      Block = 0;
      if ( v11 )
        operator delete(v11);
      if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(TokenHandle);
      result = this;
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x47,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\standby\\lib\\standbymonitorshim.cpp",
      v10);
    std::literals::string_literals::operator"" s(v22, &Src, 0);
    return v22;
  }
  return result;
}

```

## disassembly

```asm
0x18001e114  mov     [rsp+arg_8], rbx
0x18001e119  mov     [rsp+arg_10], rsi
0x18001e11e  push    rdi
0x18001e11f  sub     rsp, 0B0h
0x18001e126  mov     rax, cs:__security_cookie
0x18001e12d  xor     rax, rsp
0x18001e130  mov     [rsp+0B8h+var_10], rax
0x18001e138  mov     rdi, rcx
0x18001e13b  mov     [rsp+0B8h+var_80], rcx
0x18001e140  mov     [rsp+0B8h+TokenHandle], 0
0x18001e149  call    cs:__imp_GetCurrentThread
0x18001e14f  lea     r9, [rsp+0B8h+TokenHandle]; TokenHandle
0x18001e154  mov     edx, 8; DesiredAccess
0x18001e159  lea     r8d, [rdx-7]; OpenAsSelf
0x18001e15d  mov     rcx, rax; ThreadHandle
0x18001e160  call    cs:__imp_OpenThreadToken
0x18001e166  mov     rcx, [rsp+0B8h]; this
0x18001e16e  test    eax, eax
0x18001e170  jz      loc_18001E42F
0x18001e176  mov     rdx, [rsp+0B8h+TokenHandle]
0x18001e17b  lea     rcx, [rsp+0B8h+Block]
0x18001e180  call    ??$GetTokenInfoWrap@U_TOKEN_USER@@Uerr_exception_policy@wil@@$0A@@details@wil@@YA?AV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(void *)
0x18001e185  nop
0x18001e186  mov     rcx, [rsp+0B8h+Block]
0x18001e18b  mov     rcx, [rcx]; pSid
0x18001e18e  call    cs:__imp_GetLengthSid
0x18001e194  mov     esi, eax
0x18001e196  mov     edx, eax; uBytes
0x18001e198  xor     ecx, ecx; uFlags
0x18001e19a  call    cs:__imp_LocalAlloc
0x18001e1a0  mov     rbx, rax
0x18001e1a3  mov     [rsp+0B8h+var_70], rax
0x18001e1a8  mov     rcx, [rsp+0B8h]; this
0x18001e1b0  test    rax, rax
0x18001e1b3  jz      loc_18001E2C1
0x18001e1b9  mov     r8, [rsp+0B8h+Block]
0x18001e1be  mov     r8, [r8]; pSourceSid
0x18001e1c1  mov     rdx, rax; pDestinationSid
0x18001e1c4  mov     ecx, esi; nDestinationSidLength
0x18001e1c6  call    cs:__imp_CopySid
0x18001e1cc  mov     rcx, [rsp+0B8h]; this
0x18001e1d4  test    eax, eax
0x18001e1d6  jz      loc_18001E441
0x18001e1dc  mov     [rsp+0B8h+cchName], 0
0x18001e1e4  mov     [rsp+0B8h+var_68], 0
0x18001e1ec  mov     [rsp+0B8h+var_60], 7
0x18001e1f4  mov     rsi, [rsp+0B8h]
0x18001e1fc  lea     rax, [rsp+0B8h+var_60]
0x18001e201  mov     [rsp+0B8h+peUse], rax; peUse
0x18001e206  lea     rax, [rsp+0B8h+var_68]
0x18001e20b  mov     [rsp+0B8h+cchReferencedDomainName], rax; int
0x18001e210  xor     r9d, r9d; ReferencedDomainName
0x18001e213  lea     r8, [rsp+0B8h+cchName]; cchName
0x18001e218  xor     edx, edx; Name
0x18001e21a  mov     rcx, rbx; Sid
0x18001e21d  call    cs:__imp_LookupAccountSidLocalA
0x18001e223  test    eax, eax
0x18001e225  jnz     loc_18001E414
0x18001e22b  call    cs:__imp_GetLastError
0x18001e231  xorps   xmm0, xmm0
0x18001e234  cmp     eax, 7Ah ; 'z'
0x18001e237  jz      loc_18001E2D8
0x18001e23d  movups  xmmword ptr [rdi], xmm0
0x18001e240  mov     qword ptr [rdi+10h], 0
0x18001e248  mov     qword ptr [rdi+18h], 0
0x18001e250  xor     r8d, r8d
0x18001e253  lea     rdx, Src
0x18001e25a  mov     rcx, rdi
0x18001e25d  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18001e262  nop
0x18001e263  mov     rcx, rbx; hMem
0x18001e266  call    cs:__imp_LocalFree
0x18001e26c  nop
0x18001e26d  mov     rcx, [rsp+0B8h+Block]; Block
0x18001e272  mov     [rsp+0B8h+Block], 0
0x18001e27b  test    rcx, rcx
0x18001e27e  jz      short loc_18001E286
0x18001e280  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001e285  nop
0x18001e286  mov     rcx, [rsp+0B8h+TokenHandle]; hObject
0x18001e28b  lea     rax, [rcx-1]
0x18001e28f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001e293  jbe     loc_18001E49F
0x18001e299  mov     rax, rdi
0x18001e29c  mov     rcx, [rsp+0B8h+var_10]
0x18001e2a4  xor     rcx, rsp; StackCookie
0x18001e2a7  call    __security_check_cookie
0x18001e2ac  lea     r11, [rsp+0B8h+var_8]
0x18001e2b4  mov     rbx, [r11+18h]
0x18001e2b8  mov     rsi, [r11+20h]
0x18001e2bc  mov     rsp, r11
0x18001e2bf  pop     rdi
0x18001e2c0  retn
0x18001e2c1  mov     r9d, 80070008h; char *
0x18001e2c7  lea     r8, aOnecoreNetNetp_32; "onecore\\net\\netprofiles\\service\\src"...
0x18001e2ce  mov     edx, 32h ; '2'; void *
0x18001e2d3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001e2d8  movups  xmmword ptr [rsp+0B8h+Name], xmm0
0x18001e2dd  xorps   xmm1, xmm1
0x18001e2e0  movdqu  [rsp+0B8h+var_40], xmm1
0x18001e2e6  mov     r8d, [rsp+0B8h+cchName]
0x18001e2eb  lea     rcx, [rsp+0B8h+Name]
0x18001e2f0  call    ??$_Construct@$0A@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXD_K@Z; std::string::_Construct<0,char>(char,unsigned __int64)
0x18001e2f5  nop
0x18001e2f6  xorps   xmm0, xmm0
0x18001e2f9  movups  xmmword ptr [rsp+0B8h+ReferencedDomainName], xmm0
0x18001e301  xorps   xmm1, xmm1
0x18001e304  movdqu  [rsp+0B8h+var_20], xmm1
0x18001e30d  mov     r8d, [rsp+0B8h+var_68]
0x18001e312  lea     rcx, [rsp+0B8h+ReferencedDomainName]
0x18001e31a  call    ??$_Construct@$0A@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXD_K@Z; std::string::_Construct<0,char>(char,unsigned __int64)
0x18001e31f  nop
0x18001e320  lea     r9, [rsp+0B8h+ReferencedDomainName]
0x18001e328  cmp     qword ptr [rsp+0B8h+var_20+8], 0Fh
0x18001e331  cmova   r9, [rsp+0B8h+ReferencedDomainName]; ReferencedDomainName
0x18001e33a  lea     rdx, [rsp+0B8h+Name]
0x18001e33f  cmp     qword ptr [rsp+0B8h+var_40+8], 0Fh
0x18001e348  cmova   rdx, [rsp+0B8h+Name]; Name
0x18001e34e  lea     rax, [rsp+0B8h+var_60]
0x18001e353  mov     [rsp+0B8h+peUse], rax; peUse
0x18001e358  lea     rax, [rsp+0B8h+var_68]
0x18001e35d  mov     [rsp+0B8h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18001e362  lea     r8, [rsp+0B8h+cchName]; cchName
0x18001e367  mov     rcx, rbx; Sid
0x18001e36a  call    cs:__imp_LookupAccountSidLocalA
0x18001e370  mov     rcx, [rsp+0B8h]; this
0x18001e378  test    eax, eax
0x18001e37a  jz      loc_18001E453
0x18001e380  lea     rdx, [rsp+0B8h+Name]
0x18001e385  mov     rcx, rdi
0x18001e388  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@$$QEAV01@@Z; std::string::string(std::string &&)
0x18001e38d  nop
0x18001e38e  mov     rdx, qword ptr [rsp+0B8h+var_20+8]
0x18001e396  cmp     rdx, 0Fh
0x18001e39a  ja      loc_18001E465
0x18001e3a0  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x18001e3a8  movdqu  [rsp+0B8h+var_20], xmm0
0x18001e3b1  mov     byte ptr [rsp+0B8h+ReferencedDomainName], 0
0x18001e3b9  mov     rdx, qword ptr [rsp+0B8h+var_40+8]
0x18001e3c1  cmp     rdx, 0Fh
0x18001e3c5  ja      loc_18001E47A
0x18001e3cb  movdqu  [rsp+0B8h+var_40], xmm0
0x18001e3d1  mov     byte ptr [rsp+0B8h+Name], 0
0x18001e3d6  mov     rcx, rbx; hMem
0x18001e3d9  call    cs:__imp_LocalFree
0x18001e3df  nop
0x18001e3e0  mov     rcx, [rsp+0B8h+Block]; Block
0x18001e3e5  mov     [rsp+0B8h+Block], 0
0x18001e3ee  test    rcx, rcx
0x18001e3f1  jz      short loc_18001E3F9
0x18001e3f3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001e3f8  nop
0x18001e3f9  mov     rcx, [rsp+0B8h+TokenHandle]; hObject
0x18001e3fe  lea     rdx, [rcx-1]
0x18001e402  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001e406  jbe     loc_18001E494
0x18001e40c  mov     rax, rdi
0x18001e40f  jmp     loc_18001E29C
0x18001e414  mov     r9d, 8000FFFFh; char *
0x18001e41a  lea     r8, aOnecoreNetNetp_32; "onecore\\net\\netprofiles\\service\\src"...
0x18001e421  mov     edx, 3Ah ; ':'; void *
0x18001e426  mov     rcx, rsi; this
0x18001e429  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001e42f  lea     r8, aOnecoreNetNetp_32; "onecore\\net\\netprofiles\\service\\src"...
0x18001e436  mov     edx, 2Eh ; '.'; void *
0x18001e43b  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18001e441  lea     r8, aOnecoreNetNetp_32; "onecore\\net\\netprofiles\\service\\src"...
0x18001e448  mov     edx, 33h ; '3'; void *
0x18001e44d  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18001e453  lea     r8, aOnecoreNetNetp_32; "onecore\\net\\netprofiles\\service\\src"...
0x18001e45a  mov     edx, 40h ; '@'; void *
0x18001e45f  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18001e465  inc     rdx
0x18001e468  mov     rcx, [rsp+0B8h+ReferencedDomainName]
0x18001e470  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001e475  jmp     loc_18001E3A0
0x18001e47a  inc     rdx
0x18001e47d  mov     rcx, [rsp+0B8h+Name]
0x18001e482  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001e487  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x18001e48f  jmp     loc_18001E3CB
0x18001e494  call    cs:__imp_CloseHandle
0x18001e49a  jmp     loc_18001E40C
0x18001e49f  call    cs:__imp_CloseHandle
0x18001e4a5  jmp     loc_18001E299
0x18001e4aa  mov     rax, [rsp+0B8h+var_80]
0x18001e4af  jmp     loc_18001E29C
```
