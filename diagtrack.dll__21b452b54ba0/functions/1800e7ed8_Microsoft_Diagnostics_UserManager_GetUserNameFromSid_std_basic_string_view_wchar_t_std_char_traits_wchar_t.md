# Microsoft::Diagnostics::UserManager::GetUserNameFromSid(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)

- ea: `0x1800e7ed8`
- end: `0x1800e81c7`
- name: `?GetUserNameFromSid@UserManager@Diagnostics@Microsoft@@AEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@5@@Z`
- size: `751`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800e778c`

## callees

- `0x18002abb4`
- `0x18002be90`
- `0x18002bfc0`
- `0x18002df00`
- `0x1800a8ed4`
- `0x1800cf7d8`
- `0x1800e7ed8`
- `0x18010e55c`
- `0x18010f9b8`
- `0x1801a9494`
- `0x1801b2084`
- `0x18020aac0`
- `0x180369010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e802e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e802e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800e7f70`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800e8185`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800e7fbd`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800e7fbd`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800e8024`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800e811d`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800e8024`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800e811d`

## string_xrefs

- `0x1800e7f15`: `onecore\base\telemetry\utc\service\engine\usermanager.cpp`
- `0x1800e7fcf`: `onecore\base\telemetry\utc\service\engine\usermanager.cpp`
- `0x1800e8055`: `onecore\base\telemetry\utc\service\engine\usermanager.cpp`
- `0x1800e812f`: `onecore\base\telemetry\utc\service\engine\usermanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::UserManager::GetUserNameFromSid(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned __int64 v5; // r8
  const WCHAR *v6; // rcx
  const char *v7; // r9
  signed int LastError; // eax
  const char *v9; // r9
  WCHAR *v10; // rax
  WCHAR *v11; // r8
  const char *v12; // r9
  int ReferencedDomainName; // [rsp+20h] [rbp-D8h]
  int ReferencedDomainNamea; // [rsp+20h] [rbp-D8h]
  DWORD cchReferencedDomainName; // [rsp+40h] [rbp-B8h] BYREF
  DWORD cchName; // [rsp+44h] [rbp-B4h] BYREF
  PSID Sid; // [rsp+48h] [rbp-B0h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+50h] [rbp-A8h] BYREF
  __int64 v20; // [rsp+58h] [rbp-A0h]
  LPWSTR Name[2]; // [rsp+80h] [rbp-78h] BYREF
  __int128 v22; // [rsp+90h] [rbp-68h]
  LPWSTR v23[2]; // [rsp+A0h] [rbp-58h] BYREF
  __int128 v24; // [rsp+B0h] [rbp-48h]
  LPCWSTR StringSid[2]; // [rsp+C0h] [rbp-38h] BYREF
  __int128 v26; // [rsp+D0h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v20 = a2;
  v5 = *(_QWORD *)(a3 + 8);
  if ( !v5 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x51F,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\usermanager.cpp",
      (const char *)0x8000FFFFLL,
      ReferencedDomainName);
  Sid = 0;
  *(_OWORD *)StringSid = 0;
  v26 = 0;
  std::wstring::_Construct<1,wchar_t *>(StringSid, *(const void **)a3, v5);
  Sid = 0;
  v6 = (const WCHAR *)StringSid;
  if ( *((_QWORD *)&v26 + 1) > 7u )
    v6 = StringSid[0];
  if ( !ConvertStringSidToSidW(v6, &Sid) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x524,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\usermanager.cpp",
      v7);
  cchName = 0;
  cchReferencedDomainName = 0;
  peUse = SidTypeUnknown;
  if ( !LookupAccountSidW(0, Sid, 0, &cchName, 0, &cchReferencedDomainName, &peUse) )
  {
    LastError = GetLastError();
    v9 = LastError > 0
       ? (const char *)((unsigned __int16)LastError | 0x80070000)
       : (const char *)(unsigned int)LastError;
    if ( LastError != 122 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x533,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\usermanager.cpp",
        v9,
        ReferencedDomainNamea);
  }
  *(_OWORD *)Name = 0;
  v22 = 0;
  std::wstring::_Construct<0,wchar_t>(Name, 0, cchName - 1);
  *(_OWORD *)v23 = 0;
  v24 = 0;
  std::wstring::_Construct<0,wchar_t>(v23, 0, cchReferencedDomainName - 1);
  v10 = (WCHAR *)v23;
  if ( *((_QWORD *)&v24 + 1) > 7u )
    v10 = v23[0];
  v11 = (WCHAR *)Name;
  if ( *((_QWORD *)&v22 + 1) > 7u )
    v11 = Name[0];
  if ( !LookupAccountSidW(0, Sid, v11, &cchName, v10, &cchReferencedDomainName, &peUse) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x540,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\usermanager.cpp",
      v12);
  std::wstring::wstring(a2, Name);
  std::wstring::_Tidy_deallocate(v23);
  std::wstring::_Tidy_deallocate(Name);
  std::wstring::_Tidy_deallocate(StringSid);
  if ( Sid )
    LocalFree(Sid);
  return a2;
}

```

## disassembly

```asm
0x1800e7ed8  push    rbx
0x1800e7eda  sub     rsp, 0F0h
0x1800e7ee1  mov     rax, cs:__security_cookie
0x1800e7ee8  xor     rax, rsp
0x1800e7eeb  mov     [rsp+0F8h+var_18], rax
0x1800e7ef3  mov     rax, r8
0x1800e7ef6  mov     rbx, rdx
0x1800e7ef9  mov     [rsp+0F8h+var_A0], rdx
0x1800e7efe  mov     r8, [r8+8]
0x1800e7f02  mov     rcx, [rsp+0F8h]; this
0x1800e7f0a  test    r8, r8
0x1800e7f0d  jnz     short loc_1800E7F26
0x1800e7f0f  mov     r9d, 8000FFFFh; char *
0x1800e7f15  lea     r8, aOnecoreBaseTel_119; "onecore\\base\\telemetry\\utc\\service"...
0x1800e7f1c  mov     edx, 51Fh; void *
0x1800e7f21  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e7f26  mov     [rsp+0F8h+Sid], 0
0x1800e7f2f  xorps   xmm0, xmm0
0x1800e7f32  movups  xmmword ptr [rsp+0F8h+StringSid], xmm0
0x1800e7f3a  xorps   xmm1, xmm1
0x1800e7f3d  movdqu  [rsp+0F8h+var_28], xmm1
0x1800e7f46  mov     rdx, [rax]
0x1800e7f49  lea     rcx, [rsp+0F8h+StringSid]
0x1800e7f51  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x1800e7f56  nop
0x1800e7f57  mov     rax, [rsp+0F8h+Sid]
0x1800e7f5c  test    rax, rax
0x1800e7f5f  jz      short loc_1800E7F95
0x1800e7f61  mov     [rsp+0F8h+var_90], rax
0x1800e7f66  lea     rcx, [rsp+0F8h+var_80]; this
0x1800e7f6b  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800e7f70  mov     rax, cs:__imp_LocalFree
0x1800e7f77  mov     [rsp+0F8h+var_88], rax
0x1800e7f7c  lea     rdx, [rsp+0F8h+var_90]
0x1800e7f81  lea     rcx, [rsp+0F8h+var_88]
0x1800e7f86  call    ??$invoke@P6APEAXPEAX@ZAEAPEAX@wistd@@YAPEAX$$QEAP6APEAXPEAX@ZAEAPEAX@Z; wistd::invoke<void * (*)(void *),void * &>(void * (*&&)(void *),void * &)
0x1800e7f8b  lea     rcx, [rsp+0F8h+var_80]; this
0x1800e7f90  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800e7f95  mov     [rsp+0F8h+Sid], 0
0x1800e7f9e  lea     rcx, [rsp+0F8h+StringSid]
0x1800e7fa6  cmp     qword ptr [rsp+0F8h+var_28+8], 7
0x1800e7faf  cmova   rcx, [rsp+0F8h+StringSid]; StringSid
0x1800e7fb8  lea     rdx, [rsp+0F8h+Sid]; Sid
0x1800e7fbd  call    cs:__imp_ConvertStringSidToSidW
0x1800e7fc3  mov     rcx, [rsp+0F8h]; this
0x1800e7fcb  test    eax, eax
0x1800e7fcd  jnz     short loc_1800E7FE0
0x1800e7fcf  lea     r8, aOnecoreBaseTel_119; "onecore\\base\\telemetry\\utc\\service"...
0x1800e7fd6  mov     edx, 524h; void *
0x1800e7fdb  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800e7fe0  mov     [rsp+0F8h+cchName], 0
0x1800e7fe8  mov     [rsp+0F8h+var_B8], 0
0x1800e7ff0  mov     [rsp+0F8h+var_A8], 8
0x1800e7ff8  lea     rax, [rsp+0F8h+var_A8]
0x1800e7ffd  mov     [rsp+0F8h+peUse], rax; peUse
0x1800e8002  lea     rax, [rsp+0F8h+var_B8]
0x1800e8007  mov     [rsp+0F8h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800e800c  mov     [rsp+0F8h+ReferencedDomainName], 0; int
0x1800e8015  lea     r9, [rsp+0F8h+cchName]; cchName
0x1800e801a  xor     r8d, r8d; Name
0x1800e801d  mov     rdx, [rsp+0F8h+Sid]; Sid
0x1800e8022  xor     ecx, ecx; lpSystemName
0x1800e8024  call    cs:__imp_LookupAccountSidW
0x1800e802a  test    eax, eax
0x1800e802c  jnz     short loc_1800E8066
0x1800e802e  call    cs:__imp_GetLastError
0x1800e8034  test    eax, eax
0x1800e8036  jg      short loc_1800E803D
0x1800e8038  mov     r9d, eax
0x1800e803b  jmp     short loc_1800E8048
0x1800e803d  movzx   r9d, ax
0x1800e8041  or      r9d, 80070000h; char *
0x1800e8048  mov     rcx, [rsp+0F8h]; this
0x1800e8050  cmp     eax, 7Ah ; 'z'
0x1800e8053  jz      short loc_1800E8066
0x1800e8055  lea     r8, aOnecoreBaseTel_119; "onecore\\base\\telemetry\\utc\\service"...
0x1800e805c  mov     edx, 533h; void *
0x1800e8061  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e8066  xorps   xmm0, xmm0
0x1800e8069  movups  xmmword ptr [rsp+0F8h+Name], xmm0
0x1800e8071  xorps   xmm1, xmm1
0x1800e8074  movdqu  [rsp+0F8h+var_68], xmm1
0x1800e807d  mov     r8d, [rsp+0F8h+cchName]
0x1800e8082  dec     r8d
0x1800e8085  xor     edx, edx
0x1800e8087  lea     rcx, [rsp+0F8h+Name]
0x1800e808f  call    ??$_Construct@$0A@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAX_W_K@Z; std::wstring::_Construct<0,wchar_t>(wchar_t,unsigned __int64)
0x1800e8094  nop
0x1800e8095  xorps   xmm0, xmm0
0x1800e8098  movups  xmmword ptr [rsp+0F8h+var_58], xmm0
0x1800e80a0  xorps   xmm1, xmm1
0x1800e80a3  movdqu  [rsp+0F8h+var_48], xmm1
0x1800e80ac  mov     r8d, [rsp+0F8h+var_B8]
0x1800e80b1  dec     r8d
0x1800e80b4  xor     edx, edx
0x1800e80b6  lea     rcx, [rsp+0F8h+var_58]
0x1800e80be  call    ??$_Construct@$0A@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAX_W_K@Z; std::wstring::_Construct<0,wchar_t>(wchar_t,unsigned __int64)
0x1800e80c3  nop
0x1800e80c4  lea     rax, [rsp+0F8h+var_58]
0x1800e80cc  cmp     qword ptr [rsp+0F8h+var_48+8], 7
0x1800e80d5  cmova   rax, [rsp+0F8h+var_58]
0x1800e80de  lea     r8, [rsp+0F8h+Name]
0x1800e80e6  cmp     qword ptr [rsp+0F8h+var_68+8], 7
0x1800e80ef  cmova   r8, [rsp+0F8h+Name]; Name
0x1800e80f8  lea     rcx, [rsp+0F8h+var_A8]
0x1800e80fd  mov     [rsp+0F8h+peUse], rcx; peUse
0x1800e8102  lea     rcx, [rsp+0F8h+var_B8]
0x1800e8107  mov     [rsp+0F8h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x1800e810c  mov     [rsp+0F8h+ReferencedDomainName], rax; ReferencedDomainName
0x1800e8111  lea     r9, [rsp+0F8h+cchName]; cchName
0x1800e8116  mov     rdx, [rsp+0F8h+Sid]; Sid
0x1800e811b  xor     ecx, ecx; lpSystemName
0x1800e811d  call    cs:__imp_LookupAccountSidW
0x1800e8123  mov     rcx, [rsp+0F8h]; this
0x1800e812b  test    eax, eax
0x1800e812d  jnz     short loc_1800E8140
0x1800e812f  lea     r8, aOnecoreBaseTel_119; "onecore\\base\\telemetry\\utc\\service"...
0x1800e8136  mov     edx, 540h; void *
0x1800e813b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800e8140  lea     rdx, [rsp+0F8h+Name]
0x1800e8148  mov     rcx, rbx
0x1800e814b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1800e8150  nop
0x1800e8151  lea     rcx, [rsp+0F8h+var_58]
0x1800e8159  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e815e  nop
0x1800e815f  lea     rcx, [rsp+0F8h+Name]
0x1800e8167  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e816c  nop
0x1800e816d  lea     rcx, [rsp+0F8h+StringSid]
0x1800e8175  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e817a  nop
0x1800e817b  mov     rcx, [rsp+0F8h+Sid]
0x1800e8180  test    rcx, rcx
0x1800e8183  jz      short loc_1800E8192
0x1800e8185  mov     rax, cs:__imp_LocalFree
0x1800e818c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e8191  nop
0x1800e8192  mov     rax, rbx
0x1800e8195  jmp     short loc_1800E81AD
0x1800e8197  lea     rdx, qword_180462670
0x1800e819e  mov     rcx, [rsp+0F8h+var_A0]
0x1800e81a3  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800e81a8  mov     rax, [rsp+0F8h+var_A0]
0x1800e81ad  mov     rcx, [rsp+0F8h+var_18]
0x1800e81b5  xor     rcx, rsp; StackCookie
0x1800e81b8  call    __security_check_cookie
0x1800e81bd  add     rsp, 0F0h
0x1800e81c4  pop     rbx
0x1800e81c5  retn
```
