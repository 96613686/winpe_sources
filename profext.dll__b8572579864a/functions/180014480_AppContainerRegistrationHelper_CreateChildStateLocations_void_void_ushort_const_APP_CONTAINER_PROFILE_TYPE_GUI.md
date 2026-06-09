# AppContainerRegistrationHelper::CreateChildStateLocations(void *,void *,ushort const *,APP_CONTAINER_PROFILE_TYPE,_GUID const *)

- ea: `0x180014480`
- end: `0x180014749`
- name: `?CreateChildStateLocations@AppContainerRegistrationHelper@@CAJPEAX0PEBGW4APP_CONTAINER_PROFILE_TYPE@@PEBU_GUID@@@Z`
- size: `713`
- prototype: `static int __high(void *, void *, const unsigned __int16 *, enum APP_CONTAINER_PROFILE_TYPE, const struct _GUID *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180009504`

## callees

- `0x180002030`
- `0x1800044e0`
- `0x1800045bc`
- `0x180006400`
- `0x18000f41c`
- `0x18000f6cc`
- `0x180014480`
- `0x180014750`
- `0x180022830`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180014513`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180014513`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18001456a`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18001456a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800144c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800144c9`

## string_xrefs

- `0x18001452d`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x1800145b7`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18001460d`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180014665`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180014601`: `Name %ls path %ls`
- `0x1800146b2`: `\TempState`
- `0x18001465e`: `Name %ls path %ls dir %ls`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AppContainerRegistrationHelper::CreateChildStateLocations(
        void *a1,
        void *a2,
        const char *a3,
        int a4,
        struct _GUID *a5)
{
  struct _ACL *v9; // rax
  struct _ACL *v10; // rbx
  int LastErrorMsg; // edi
  __int64 v12; // rdx
  __int64 v13; // r9
  __int64 v14; // rdx
  struct _ACL *v15; // rax
  struct _ACL *v17; // [rsp+40h] [rbp-C0h] BYREF
  struct _ACL v18[66]; // [rsp+50h] [rbp-B0h] BYREF
  struct _ACL v19[66]; // [rsp+260h] [rbp+160h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4C8h] [rbp+3C8h]

  v9 = (struct _ACL *)CoTaskMemAlloc(0x58u);
  v10 = v9;
  v17 = v9;
  if ( v9 )
  {
    if ( !InitializeAcl(v9, 0x58u, 2u) )
    {
      v12 = 1233;
LABEL_5:
      LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                       retaddr,
                       (void *)v12,
                       (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
                       "Name %ls size %d",
                       a3,
                       88);
      goto LABEL_25;
    }
    if ( !AddAccessAllowedAceEx(v10, 2u, 0x23u, 0x1F01FFu, a2) )
    {
      v12 = 1241;
      goto LABEL_5;
    }
    LastErrorMsg = AppContainerRegistrationHelper::DeriveTopLevelFolderPath(a1, a3, (unsigned __int16 *)v18, v13, a4);
    if ( LastErrorMsg < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x4E3,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)(unsigned int)LastErrorMsg,
        (int)"Name %ls",
        a3);
      goto LABEL_25;
    }
    LastErrorMsg = StringCchCopyW((unsigned __int16 *)v19, 0x104u, (const unsigned __int16 *)v18);
    if ( LastErrorMsg >= 0 )
    {
      LastErrorMsg = StringCchCatW((unsigned __int16 *)v18, 0x104u, L"\\LocalState");
      if ( LastErrorMsg < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x4E9,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
          (const char *)(unsigned int)LastErrorMsg,
          (int)"Name %ls path %ls dir %ls",
          a3,
          v18,
          L"\\LocalState",
          v17);
        goto LABEL_25;
      }
      LastErrorMsg = AppContainerRegistrationHelper::CreateFolder(v18, 0, 0x2000u, v10, a5);
      if ( LastErrorMsg >= 0 )
      {
        LastErrorMsg = StringCchCatW((unsigned __int16 *)v19, 0x104u, L"\\TempState");
        if ( LastErrorMsg < 0 )
        {
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x4F4,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
            (const char *)(unsigned int)LastErrorMsg,
            (int)"Name %ls path %ls dir %ls",
            a3,
            v19,
            L"\\TempState",
            v17);
          goto LABEL_25;
        }
        LastErrorMsg = AppContainerRegistrationHelper::CreateFolder(v19, 0, 0x2000u, v10, a5);
        if ( LastErrorMsg >= 0 )
        {
          LastErrorMsg = 0;
          goto LABEL_25;
        }
        v15 = v19;
        v14 = 1276;
LABEL_13:
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)v14,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
          (const char *)(unsigned int)LastErrorMsg,
          (int)"Name %ls path %ls",
          a3,
          v15);
        goto LABEL_25;
      }
      v14 = 1265;
    }
    else
    {
      v14 = 1254;
    }
    v15 = v18;
    goto LABEL_13;
  }
  LastErrorMsg = -2147024882;
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0x4CE,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
    (const char *)0x8007000ELL,
    (int)"Name %ls size %d",
    a3,
    88);
LABEL_25:
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v17);
  return (unsigned int)LastErrorMsg;
}

```

## disassembly

```asm
0x180014480  push    rbp
0x180014482  push    rbx
0x180014483  push    rsi
0x180014484  push    rdi
0x180014485  push    r12
0x180014487  push    r13
0x180014489  push    r14
0x18001448b  push    r15
0x18001448d  lea     rbp, [rsp-388h]
0x180014495  sub     rsp, 488h
0x18001449c  mov     rax, cs:__security_cookie
0x1800144a3  xor     rax, rsp
0x1800144a6  mov     [rbp+3C0h+var_50], rax
0x1800144ad  mov     r15d, r9d
0x1800144b0  mov     rsi, r8
0x1800144b3  mov     r12, rdx
0x1800144b6  mov     rdi, rcx
0x1800144b9  mov     r14, [rbp+3C0h+arg_20]
0x1800144c0  mov     r13d, 58h ; 'X'
0x1800144c6  mov     ecx, r13d; cb
0x1800144c9  call    cs:__imp_CoTaskMemAlloc
0x1800144d0  nop     dword ptr [rax+rax+00h]
0x1800144d5  mov     rbx, rax
0x1800144d8  mov     [rsp+4C0h+var_480], rax
0x1800144dd  test    rax, rax
0x1800144e0  jnz     short loc_180014507
0x1800144e2  mov     dword ptr [rsp+4C0h+var_490], r13d
0x1800144e7  mov     [rsp+4C0h+var_498], rsi
0x1800144ec  lea     r9, aNameLsSizeD; "Name %ls size %d"
0x1800144f3  mov     [rsp+4C0h+pSid], r9
0x1800144f8  mov     edi, 8007000Eh
0x1800144fd  mov     edx, 4CEh
0x180014502  jmp     loc_18001460D
0x180014507  mov     r8d, 2; dwAclRevision
0x18001450d  mov     edx, r13d; nAclLength
0x180014510  mov     rcx, rbx; pAcl
0x180014513  call    cs:__imp_InitializeAcl
0x18001451a  nop     dword ptr [rax+rax+00h]
0x18001451f  test    eax, eax
0x180014521  jnz     short loc_180014553
0x180014523  mov     edx, 4D1h; void *
0x180014528  mov     dword ptr [rsp+4C0h+var_498], r13d
0x18001452d  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180014534  lea     r9, aNameLsSizeD; "Name %ls size %d"
0x18001453b  mov     [rsp+4C0h+pSid], rsi; char *
0x180014540  mov     rcx, [rbp+3C8h]; this
0x180014547  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18001454c  mov     edi, eax
0x18001454e  jmp     loc_180014719
0x180014553  mov     [rsp+4C0h+pSid], r12; pSid
0x180014558  mov     edx, 2; dwAceRevision
0x18001455d  mov     r9d, 1F01FFh; AccessMask
0x180014563  lea     r8d, [rdx+21h]; AceFlags
0x180014567  mov     rcx, rbx; pAcl
0x18001456a  call    cs:__imp_AddAccessAllowedAceEx
0x180014571  nop     dword ptr [rax+rax+00h]
0x180014576  test    eax, eax
0x180014578  jnz     short loc_180014581
0x18001457a  mov     edx, 4D9h
0x18001457f  jmp     short loc_180014528
0x180014581  mov     dword ptr [rsp+4C0h+pSid], r15d
0x180014586  lea     r8, [rsp+4C0h+var_470]
0x18001458b  mov     rdx, rsi
0x18001458e  mov     rcx, rdi
0x180014591  call    ?DeriveTopLevelFolderPath@AppContainerRegistrationHelper@@CAJPEAXPEBGPEAG_KW4APP_CONTAINER_PROFILE_TYPE@@@Z; AppContainerRegistrationHelper::DeriveTopLevelFolderPath(void *,ushort const *,ushort *,unsigned __int64,APP_CONTAINER_PROFILE_TYPE)
0x180014596  mov     edi, eax
0x180014598  test    eax, eax
0x18001459a  jns     short loc_1800145CD
0x18001459c  mov     rcx, [rbp+3C8h]; this
0x1800145a3  mov     [rsp+4C0h+var_498], rsi; char *
0x1800145a8  lea     rax, aNameLs; "Name %ls"
0x1800145af  mov     [rsp+4C0h+pSid], rax; int
0x1800145b4  mov     r9d, edi; char *
0x1800145b7  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800145be  mov     edx, 4E3h; void *
0x1800145c3  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800145c8  jmp     loc_180014719
0x1800145cd  lea     r8, [rsp+4C0h+var_470]; unsigned __int16 *
0x1800145d2  mov     r15d, 104h
0x1800145d8  mov     edx, r15d; unsigned __int64
0x1800145db  lea     rcx, [rbp+3C0h+var_260]; unsigned __int16 *
0x1800145e2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800145e7  mov     edi, eax
0x1800145e9  test    eax, eax
0x1800145eb  jns     short loc_180014628
0x1800145ed  mov     edx, 4E6h; void *
0x1800145f2  lea     rax, [rsp+4C0h+var_470]
0x1800145f7  mov     [rsp+4C0h+var_490], rax
0x1800145fc  mov     [rsp+4C0h+var_498], rsi; char *
0x180014601  lea     rax, aNameLsPathLs; "Name %ls path %ls"
0x180014608  mov     [rsp+4C0h+pSid], rax; int
0x18001460d  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180014614  mov     r9d, edi; char *
0x180014617  mov     rcx, [rbp+3C8h]; this
0x18001461e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180014623  jmp     loc_180014719
0x180014628  lea     r12, aLocalstate; "\\LocalState"
0x18001462f  mov     r8, r12; unsigned __int16 *
0x180014632  mov     rdx, r15; unsigned __int64
0x180014635  lea     rcx, [rsp+4C0h+var_470]; unsigned __int16 *
0x18001463a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001463f  mov     edi, eax
0x180014641  test    eax, eax
0x180014643  jns     short loc_180014685
0x180014645  mov     [rsp+4C0h+var_488], r12
0x18001464a  lea     rax, [rsp+4C0h+var_470]
0x18001464f  mov     edx, 4E9h; void *
0x180014654  mov     [rsp+4C0h+var_490], rax
0x180014659  mov     [rsp+4C0h+var_498], rsi; char *
0x18001465e  lea     rax, aNameLsPathLsDi_0; "Name %ls path %ls dir %ls"
0x180014665  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001466c  mov     r9d, edi; char *
0x18001466f  mov     [rsp+4C0h+pSid], rax; int
0x180014674  mov     rcx, [rbp+3C8h]; this
0x18001467b  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180014680  jmp     loc_180014719
0x180014685  mov     [rsp+4C0h+pSid], r14; struct _GUID *
0x18001468a  mov     r9, rbx; pDacl
0x18001468d  mov     r12d, 2000h
0x180014693  mov     r8d, r12d; dwFileAttributes
0x180014696  xor     edx, edx; unsigned __int16 *
0x180014698  lea     rcx, [rsp+4C0h+var_470]; char *
0x18001469d  call    ?CreateFolder@AppContainerRegistrationHelper@@CAJPEBG0KPEAU_ACL@@PEBU_GUID@@@Z; AppContainerRegistrationHelper::CreateFolder(ushort const *,ushort const *,ulong,_ACL *,_GUID const *)
0x1800146a2  mov     edi, eax
0x1800146a4  test    eax, eax
0x1800146a6  jns     short loc_1800146B2
0x1800146a8  mov     edx, 4F1h
0x1800146ad  jmp     loc_1800145F2
0x1800146b2  lea     r13, aTempstate; "\\TempState"
0x1800146b9  mov     r8, r13; unsigned __int16 *
0x1800146bc  mov     rdx, r15; unsigned __int64
0x1800146bf  lea     rcx, [rbp+3C0h+var_260]; unsigned __int16 *
0x1800146c6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800146cb  mov     edi, eax
0x1800146cd  test    eax, eax
0x1800146cf  jns     short loc_1800146E7
0x1800146d1  mov     [rsp+4C0h+var_488], r13
0x1800146d6  lea     rax, [rbp+3C0h+var_260]
0x1800146dd  mov     edx, 4F4h
0x1800146e2  jmp     loc_180014654
0x1800146e7  mov     [rsp+4C0h+pSid], r14; struct _GUID *
0x1800146ec  mov     r9, rbx; pDacl
0x1800146ef  mov     r8d, r12d; dwFileAttributes
0x1800146f2  xor     edx, edx; unsigned __int16 *
0x1800146f4  lea     rcx, [rbp+3C0h+var_260]; char *
0x1800146fb  call    ?CreateFolder@AppContainerRegistrationHelper@@CAJPEBG0KPEAU_ACL@@PEBU_GUID@@@Z; AppContainerRegistrationHelper::CreateFolder(ushort const *,ushort const *,ulong,_ACL *,_GUID const *)
0x180014700  mov     edi, eax
0x180014702  test    eax, eax
0x180014704  jns     short loc_180014717
0x180014706  lea     rax, [rbp+3C0h+var_260]
0x18001470d  mov     edx, 4FCh
0x180014712  jmp     loc_1800145F7
0x180014717  xor     edi, edi
0x180014719  lea     rcx, [rsp+4C0h+var_480]
0x18001471e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180014723  mov     eax, edi
0x180014725  mov     rcx, [rbp+3C0h+var_50]
0x18001472c  xor     rcx, rsp; StackCookie
0x18001472f  call    __security_check_cookie
0x180014734  add     rsp, 488h
0x18001473b  pop     r15
0x18001473d  pop     r14
0x18001473f  pop     r13
0x180014741  pop     r12
0x180014743  pop     rdi
0x180014744  pop     rsi
0x180014745  pop     rbx
0x180014746  pop     rbp
0x180014747  retn
```
