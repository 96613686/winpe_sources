# EnsureSessionUserHasAccess

- ea: `0x180028514`
- end: `0x1800287d3`
- name: `EnsureSessionUserHasAccess`
- size: `703`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1800287dc`

## callees

- `0x180006954`
- `0x180006974`
- `0x18000918c`
- `0x180009eb0`
- `0x180028514`
- `0x18003586a`
- `0x1800358a0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800285a9`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002878a`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800285a9`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002878a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800285cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028714`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028773`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800287ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800285cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028714`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028773`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800287ac`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180028669`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180028669`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x180028576`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x180028576`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x180028615`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x180028615`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180028752`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180028752`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1800286dc`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1800286dc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 EnsureSessionUserHasAccess()
{
  WCHAR *v0; // rcx
  HRESULT v1; // eax
  unsigned int v2; // ebx
  const WCHAR *v4; // rcx
  DWORD NamedSecurityInfoW; // eax
  int LastError; // eax
  const char *v7; // r9
  DWORD v8; // eax
  __int64 v9; // rdx
  WCHAR *v10; // rcx
  int ppsidGroup; // [rsp+20h] [rbp-E0h]
  unsigned int ppsidGroupa; // [rsp+20h] [rbp-E0h]
  HLOCAL hMem; // [rsp+40h] [rbp-C0h] BYREF
  PACL NewAcl; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cbSid; // [rsp+50h] [rbp-B0h] BYREF
  PACL OldAcl; // [rsp+58h] [rbp-A8h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+60h] [rbp-A0h] BYREF
  PWSTR pszPath[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v19; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v20; // [rsp+A8h] [rbp-58h]
  _BYTE pSid[80]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  hMem = 0;
  OldAcl = 0;
  v20 = 7;
  v19 = 0;
  LOWORD(pszPath[0]) = 0;
  std::wstring::assign(pszPath);
  v0 = (WCHAR *)pszPath;
  if ( v20 >= 8 )
    v0 = pszPath[0];
  v1 = PathCchRemoveFileSpec(v0, v19 + 1);
  v2 = v1;
  if ( v1 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\assetnode.cpp",
      (const char *)(unsigned int)v1,
      ppsidGroup);
LABEL_5:
    if ( v20 >= 8 )
      operator delete(pszPath[0]);
    v20 = 7;
    v19 = 0;
    LOWORD(pszPath[0]) = 0;
    if ( hMem )
      LocalFree(hMem);
    return v2;
  }
  v4 = (const WCHAR *)pszPath;
  if ( v20 >= 8 )
    v4 = pszPath[0];
  NamedSecurityInfoW = GetNamedSecurityInfoW(v4, SE_FILE_OBJECT, 4u, 0, 0, &OldAcl, 0, &hMem);
  if ( NamedSecurityInfoW )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x20,
                  (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\assetnode.cpp",
                  (const char *)NamedSecurityInfoW,
                  ppsidGroupa);
LABEL_14:
    v2 = LastError;
    goto LABEL_5;
  }
  memset_0(pSid, 0, 0x44u);
  cbSid = 68;
  if ( !CreateWellKnownSid(WinAccountProtectedUsersSid|WinCreatorGroupSid, 0, pSid, &cbSid) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x26,
                  (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\assetnode.cpp",
                  v7);
    goto LABEL_14;
  }
  memset(&pListOfExplicitEntries.grfInheritance + 1, 0, 20);
  *(_QWORD *)&pListOfExplicitEntries.Trustee.TrusteeType = 5;
  pListOfExplicitEntries.grfAccessPermissions = 0x10000000;
  pListOfExplicitEntries.grfAccessMode = GRANT_ACCESS;
  pListOfExplicitEntries.grfInheritance = 3;
  pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)pSid;
  NewAcl = 0;
  v8 = SetEntriesInAclW(1u, &pListOfExplicitEntries, OldAcl, &NewAcl);
  if ( v8 )
  {
    v9 = 49;
    goto LABEL_19;
  }
  v10 = (WCHAR *)pszPath;
  if ( v20 >= 8 )
    v10 = pszPath[0];
  v8 = SetNamedSecurityInfoW(v10, SE_FILE_OBJECT, 4u, 0, 0, NewAcl, 0);
  if ( v8 )
  {
    v9 = 58;
LABEL_19:
    v2 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v9,
           (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\assetnode.cpp",
           (const char *)v8,
           ppsidGroupa);
    if ( NewAcl )
      LocalFree(NewAcl);
    goto LABEL_5;
  }
  if ( NewAcl )
    LocalFree(NewAcl);
  if ( v20 >= 8 )
    operator delete(pszPath[0]);
  v20 = 7;
  v19 = 0;
  LOWORD(pszPath[0]) = 0;
  if ( hMem )
    LocalFree(hMem);
  return 0;
}

```

## disassembly

```asm
0x180028514  push    rbp
0x180028516  push    rbx
0x180028517  push    rsi
0x180028518  push    rdi
0x180028519  lea     rbp, [rsp-18h]
0x18002851e  sub     rsp, 118h
0x180028525  mov     rax, cs:__security_cookie
0x18002852c  xor     rax, rsp
0x18002852f  mov     [rbp+30h+var_30], rax
0x180028533  xor     edi, edi
0x180028535  mov     [rsp+130h+hMem], rdi
0x18002853a  mov     [rsp+130h+OldAcl], rdi
0x18002853f  lea     esi, [rdi+7]
0x180028542  mov     [rbp+30h+var_88], rsi
0x180028546  mov     [rbp+30h+var_90], rdi
0x18002854a  mov     word ptr [rbp+30h+pszPath], di
0x18002854e  or      r9, 0FFFFFFFFFFFFFFFFh
0x180028552  xor     r8d, r8d
0x180028555  mov     rdx, rcx
0x180028558  lea     rcx, [rbp+30h+pszPath]; void *
0x18002855c  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180028561  mov     rdx, [rbp+30h+var_90]
0x180028565  lea     rcx, [rbp+30h+pszPath]
0x180028569  cmp     [rbp+30h+var_88], 8
0x18002856e  cmovnb  rcx, [rbp+30h+pszPath]; pszPath
0x180028573  inc     rdx; cchPath
0x180028576  call    cs:__imp_PathCchRemoveFileSpec
0x18002857d  nop     dword ptr [rax+rax+00h]
0x180028582  mov     ebx, eax
0x180028584  test    eax, eax
0x180028586  jns     short loc_1800285DE
0x180028588  mov     rcx, [rbp+38h]; this
0x18002858c  mov     r9d, eax; char *
0x18002858f  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\prov\\provcsp\\asset"...
0x180028596  lea     edx, [rdi+16h]; void *
0x180028599  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002859e  cmp     [rbp+30h+var_88], 8
0x1800285a3  jb      short loc_1800285B5
0x1800285a5  mov     rcx, [rbp+30h+pszPath]
0x1800285a9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800285b0  nop     dword ptr [rax+rax+00h]
0x1800285b5  mov     [rbp+30h+var_88], rsi
0x1800285b9  mov     [rbp+30h+var_90], rdi
0x1800285bd  mov     word ptr [rbp+30h+pszPath], di
0x1800285c1  mov     rcx, [rsp+130h+hMem]; hMem
0x1800285c6  test    rcx, rcx
0x1800285c9  jz      short loc_1800285D7
0x1800285cb  call    cs:__imp_LocalFree
0x1800285d2  nop     dword ptr [rax+rax+00h]
0x1800285d7  mov     eax, ebx
0x1800285d9  jmp     loc_1800287BA
0x1800285de  lea     rcx, [rbp+30h+pszPath]
0x1800285e2  cmp     [rbp+30h+var_88], 8
0x1800285e7  cmovnb  rcx, [rbp+30h+pszPath]; pObjectName
0x1800285ec  lea     rax, [rsp+130h+hMem]
0x1800285f1  mov     [rsp+130h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x1800285f6  mov     [rsp+130h+ppSacl], rdi; ppSacl
0x1800285fb  lea     rax, [rsp+130h+OldAcl]
0x180028600  mov     [rsp+130h+ppDacl], rax; ppDacl
0x180028605  mov     [rsp+130h+ppsidGroup], rdi; unsigned int
0x18002860a  xor     r9d, r9d; ppsidOwner
0x18002860d  lea     edx, [r9+1]; ObjectType
0x180028611  lea     r8d, [r9+4]; SecurityInfo
0x180028615  call    cs:__imp_GetNamedSecurityInfoW
0x18002861c  nop     dword ptr [rax+rax+00h]
0x180028621  test    eax, eax
0x180028623  jz      short loc_180028644
0x180028625  mov     rcx, [rbp+38h]; this
0x180028629  mov     r9d, eax; char *
0x18002862c  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\prov\\provcsp\\asset"...
0x180028633  mov     edx, 20h ; ' '; void *
0x180028638  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002863d  mov     ebx, eax
0x18002863f  jmp     loc_18002859E
0x180028644  mov     ebx, 44h ; 'D'
0x180028649  mov     r8d, ebx; Size
0x18002864c  xor     edx, edx; Val
0x18002864e  lea     rcx, [rbp+30h+pSid]; void *
0x180028652  call    memset_0
0x180028657  mov     [rsp+130h+cbSid], ebx
0x18002865b  lea     r9, [rsp+130h+cbSid]; cbSid
0x180028660  lea     r8, [rbp+30h+pSid]; pSid
0x180028664  xor     edx, edx; DomainSid
0x180028666  lea     ecx, [rbx+2Bh]; WellKnownSidType
0x180028669  call    cs:__imp_CreateWellKnownSid
0x180028670  nop     dword ptr [rax+rax+00h]
0x180028675  test    eax, eax
0x180028677  jnz     short loc_18002868E
0x180028679  mov     rcx, [rbp+38h]; this
0x18002867d  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\prov\\provcsp\\asset"...
0x180028684  lea     edx, [rbx-1Eh]; void *
0x180028687  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002868c  jmp     short loc_18002863D
0x18002868e  xorps   xmm0, xmm0
0x180028691  movdqu  xmmword ptr [rsp+130h+pListOfExplicitEntries+0Ch], xmm0
0x180028697  mov     qword ptr [rbp+30h+pListOfExplicitEntries.Trustee.TrusteeType], 5
0x18002869f  mov     [rsp+130h+pListOfExplicitEntries.grfAccessPermissions], 10000000h
0x1800286a7  mov     [rsp+130h+pListOfExplicitEntries.grfAccessMode], 1
0x1800286af  mov     [rsp+130h+pListOfExplicitEntries.grfInheritance], 3
0x1800286b7  mov     [rsp+130h+pListOfExplicitEntries.Trustee.TrusteeForm], edi
0x1800286bb  lea     rax, [rbp+30h+pSid]
0x1800286bf  mov     [rbp+30h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x1800286c3  mov     [rsp+130h+NewAcl], rdi
0x1800286c8  lea     r9, [rsp+130h+NewAcl]; NewAcl
0x1800286cd  mov     r8, [rsp+130h+OldAcl]; OldAcl
0x1800286d2  lea     rdx, [rsp+130h+pListOfExplicitEntries]; pListOfExplicitEntries
0x1800286d7  mov     ecx, 1; cCountOfExplicitEntries
0x1800286dc  call    cs:__imp_SetEntriesInAclW
0x1800286e3  nop     dword ptr [rax+rax+00h]
0x1800286e8  test    eax, eax
0x1800286ea  jz      short loc_180028725
0x1800286ec  mov     edx, 31h ; '1'; void *
0x1800286f1  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\prov\\provcsp\\asset"...
0x1800286f8  mov     r9d, eax; char *
0x1800286fb  mov     rcx, [rbp+38h]; this
0x1800286ff  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180028704  mov     ebx, eax
0x180028706  mov     rcx, [rsp+130h+NewAcl]; hMem
0x18002870b  test    rcx, rcx
0x18002870e  jz      loc_18002859E
0x180028714  call    cs:__imp_LocalFree
0x18002871b  nop     dword ptr [rax+rax+00h]
0x180028720  jmp     loc_18002859E
0x180028725  mov     rax, [rsp+130h+NewAcl]
0x18002872a  lea     rcx, [rbp+30h+pszPath]
0x18002872e  cmp     [rbp+30h+var_88], 8
0x180028733  cmovnb  rcx, [rbp+30h+pszPath]; pObjectName
0x180028738  mov     [rsp+130h+ppSacl], rdi; pSacl
0x18002873d  mov     [rsp+130h+ppDacl], rax; pDacl
0x180028742  mov     [rsp+130h+ppsidGroup], rdi; psidGroup
0x180028747  xor     r9d, r9d; psidOwner
0x18002874a  lea     edx, [r9+1]; ObjectType
0x18002874e  lea     r8d, [r9+4]; SecurityInfo
0x180028752  call    cs:__imp_SetNamedSecurityInfoW
0x180028759  nop     dword ptr [rax+rax+00h]
0x18002875e  test    eax, eax
0x180028760  jz      short loc_180028769
0x180028762  mov     edx, 3Ah ; ':'
0x180028767  jmp     short loc_1800286F1
0x180028769  mov     rcx, [rsp+130h+NewAcl]; hMem
0x18002876e  test    rcx, rcx
0x180028771  jz      short loc_18002877F
0x180028773  call    cs:__imp_LocalFree
0x18002877a  nop     dword ptr [rax+rax+00h]
0x18002877f  cmp     [rbp+30h+var_88], 8
0x180028784  jb      short loc_180028796
0x180028786  mov     rcx, [rbp+30h+pszPath]
0x18002878a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180028791  nop     dword ptr [rax+rax+00h]
0x180028796  mov     [rbp+30h+var_88], rsi
0x18002879a  mov     [rbp+30h+var_90], rdi
0x18002879e  mov     word ptr [rbp+30h+pszPath], di
0x1800287a2  mov     rcx, [rsp+130h+hMem]; hMem
0x1800287a7  test    rcx, rcx
0x1800287aa  jz      short loc_1800287B8
0x1800287ac  call    cs:__imp_LocalFree
0x1800287b3  nop     dword ptr [rax+rax+00h]
0x1800287b8  xor     eax, eax
0x1800287ba  mov     rcx, [rbp+30h+var_30]
0x1800287be  xor     rcx, rsp; StackCookie
0x1800287c1  call    __security_check_cookie
0x1800287c6  add     rsp, 118h
0x1800287cd  pop     rdi
0x1800287ce  pop     rsi
0x1800287cf  pop     rbx
0x1800287d0  pop     rbp
0x1800287d1  retn
```
