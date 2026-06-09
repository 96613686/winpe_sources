# GetUserGuid(void *,ushort * *)

- ea: `0x180012508`
- end: `0x180012795`
- name: `?GetUserGuid@@YAJPEAXPEAPEAG@Z`
- size: `653`
- prototype: `__int64 __fastcall(void *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180013db0`
- `0x1800516b4`
- `0x180051820`

## callees

- `0x180005370`
- `0x180005dd0`
- `0x180007b58`
- `0x180012508`
- `0x1800127a0`
- `0x180012974`
- `0x180012ac8`
- `0x18002793c`
- `0x18002df48`
- `0x180030ad0`
- `0x180032894`
- `0x180032900`
- `0x180035860`
- `0x18003bc70`
- `0x180040bcc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180012641`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180012641`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800125ad`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800125ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001255f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800125dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800126e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012761`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001255f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800125dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800126e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012761`

## string_xrefs

- `0x1800125c1`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x18001260e`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x180012669`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x1800126b5`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x18001272f`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x180012655`: `User SID matches local system, returning Invalid Arg.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetUserGuid(void *a1, unsigned __int16 **a2)
{
  const char *v4; // r9
  unsigned int LastError; // ebx
  int UserSid; // eax
  PSID v8; // rbx
  int v9; // eax
  unsigned int v10; // edi
  int UserNameAlloc; // eax
  int v12; // edx
  int nSubAuthority2; // [rsp+20h] [rbp-29h]
  const char *nSubAuthority3; // [rsp+28h] [rbp-21h]
  HLOCAL hMem; // [rsp+60h] [rbp+17h] BYREF
  PSID pSid1; // [rsp+68h] [rbp+1Fh] BYREF
  __int64 v17; // [rsp+70h] [rbp+27h] BYREF
  char v18; // [rsp+78h] [rbp+2Fh]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+80h] [rbp+37h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  *a2 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  hMem = 0;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &hMem) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x99,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
                  v4);
    if ( hMem )
      LocalFree(hMem);
    return LastError;
  }
  pSid1 = 0;
  UserSid = GetUserSid(a1, &pSid1);
  LastError = UserSid;
  if ( UserSid < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9C,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
      (const char *)(unsigned int)UserSid,
      nSubAuthority2);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pSid1);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&hMem);
    return LastError;
  }
  v8 = pSid1;
  if ( EqualSid(pSid1, hMem) )
  {
    LastError = -2147024809;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x9E,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
      (const char *)0x80070057LL,
      (int)"User SID matches local system, returning Invalid Arg.",
      nSubAuthority3);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pSid1);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&hMem);
    return LastError;
  }
  v17 = 0;
  v18 = 0;
  v9 = CAutoImpersonate::ImpersonateUser((CAutoImpersonate *)&v17, a1);
  v10 = v9;
  if ( v9 >= 0 )
  {
    UserNameAlloc = GetUserNameAlloc(NameUniqueId, a2);
    if ( (unsigned int)(UserNameAlloc + 2147023564) > 0x17
      || (v12 = 8912897, !_bittest(&v12, UserNameAlloc + 2147023564)) )
    {
      if ( UserNameAlloc != -2147024846 && UserNameAlloc != -2147023684 && UserNameAlloc < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xAF,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
          (const char *)(unsigned int)UserNameAlloc,
          nSubAuthority2);
    }
    CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&v17);
    if ( v8 )
      ResultFromHeapFree(v8);
    if ( hMem )
      LocalFree(hMem);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
      (const char *)(unsigned int)v9,
      nSubAuthority2);
    CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&v17);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pSid1);
    if ( hMem )
      LocalFree(hMem);
    return v10;
  }
}

```

## disassembly

```asm
0x180012508  mov     [rsp-8+arg_10], rbx
0x18001250d  mov     [rsp-8+arg_18], rsi
0x180012512  push    rbp
0x180012513  push    rdi
0x180012514  push    r14
0x180012516  lea     rbp, [rsp-47h]
0x18001251b  sub     rsp, 90h
0x180012522  mov     rax, cs:__security_cookie
0x180012529  xor     rax, rsp
0x18001252c  mov     [rbp+57h+var_18], rax
0x180012530  mov     rsi, rdx
0x180012533  mov     rdi, rcx
0x180012536  xor     r14d, r14d
0x180012539  mov     [rdx], r14
0x18001253c  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r14d
0x180012540  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x180012546  mov     [rbp+57h+hMem], r14
0x18001254a  mov     rbx, [rbp+57h+hMem]
0x18001254e  test    rbx, rbx
0x180012551  jz      short loc_180012575
0x180012553  lea     rcx, [rbp+57h+pSid1]; this
0x180012557  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001255c  mov     rcx, rbx; hMem
0x18001255f  call    cs:__imp_LocalFree
0x180012566  nop     dword ptr [rax+rax+00h]
0x18001256b  lea     rcx, [rbp+57h+pSid1]; this
0x18001256f  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180012574  nop
0x180012575  mov     [rbp+57h+hMem], r14
0x180012579  lea     rax, [rbp+57h+hMem]
0x18001257d  mov     [rsp+0A0h+pSid], rax; pSid
0x180012582  mov     [rsp+0A0h+nSubAuthority7], r14d; nSubAuthority7
0x180012587  mov     [rsp+0A0h+nSubAuthority6], r14d; nSubAuthority6
0x18001258c  mov     [rsp+0A0h+nSubAuthority5], r14d; nSubAuthority5
0x180012591  mov     [rsp+0A0h+nSubAuthority4], r14d; nSubAuthority4
0x180012596  mov     dword ptr [rsp+0A0h+nSubAuthority3], r14d; char *
0x18001259b  mov     [rsp+0A0h+nSubAuthority2], r14d; int
0x1800125a0  xor     r9d, r9d; nSubAuthority1
0x1800125a3  lea     r8d, [r9+12h]; nSubAuthority0
0x1800125a7  mov     dl, 1; nSubAuthorityCount
0x1800125a9  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1800125ad  call    cs:__imp_AllocateAndInitializeSid
0x1800125b4  nop     dword ptr [rax+rax+00h]
0x1800125b9  test    eax, eax
0x1800125bb  jnz     short loc_1800125F1
0x1800125bd  mov     rcx, [rbp+5Fh]; this
0x1800125c1  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800125c8  mov     edx, 99h; void *
0x1800125cd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800125d2  mov     ebx, eax
0x1800125d4  mov     rcx, [rbp+57h+hMem]; hMem
0x1800125d8  test    rcx, rcx
0x1800125db  jz      short loc_1800125EA
0x1800125dd  call    cs:__imp_LocalFree
0x1800125e4  nop     dword ptr [rax+rax+00h]
0x1800125e9  nop
0x1800125ea  mov     eax, ebx
0x1800125ec  jmp     loc_180012770
0x1800125f1  mov     [rbp+57h+pSid1], r14
0x1800125f5  lea     rdx, [rbp+57h+pSid1]; void **
0x1800125f9  mov     rcx, rdi; TokenHandle
0x1800125fc  call    ?GetUserSid@@YAJPEAXPEAPEAX@Z; GetUserSid(void *,void * *)
0x180012601  mov     ebx, eax
0x180012603  test    eax, eax
0x180012605  jns     short loc_180012636
0x180012607  mov     rcx, [rbp+5Fh]; this
0x18001260b  mov     r9d, eax; char *
0x18001260e  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\p"...
0x180012615  mov     edx, 9Ch; void *
0x18001261a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001261f  nop
0x180012620  lea     rcx, [rbp+57h+pSid1]
0x180012624  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AJPEAX@Z$1?ResultFromHeapFree@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180012629  nop
0x18001262a  lea     rcx, [rbp+57h+hMem]
0x18001262e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180012633  nop
0x180012634  jmp     short loc_1800125EA
0x180012636  mov     rdx, [rbp+57h+hMem]; pSid2
0x18001263a  mov     rbx, [rbp+57h+pSid1]
0x18001263e  mov     rcx, rbx; pSid1
0x180012641  call    cs:__imp_EqualSid
0x180012648  nop     dword ptr [rax+rax+00h]
0x18001264d  test    eax, eax
0x18001264f  jz      short loc_180012694
0x180012651  mov     rcx, [rbp+5Fh]; this
0x180012655  lea     rax, aUserSidMatches; "User SID matches local system, returnin"...
0x18001265c  mov     qword ptr [rsp+0A0h+nSubAuthority2], rax; int
0x180012661  mov     ebx, 80070057h
0x180012666  mov     r9d, ebx; char *
0x180012669  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\p"...
0x180012670  mov     edx, 9Eh; void *
0x180012675  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001267a  nop
0x18001267b  lea     rcx, [rbp+57h+pSid1]
0x18001267f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AJPEAX@Z$1?ResultFromHeapFree@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180012684  nop
0x180012685  lea     rcx, [rbp+57h+hMem]
0x180012689  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18001268e  nop
0x18001268f  jmp     loc_1800125EA
0x180012694  mov     [rbp+57h+var_30], r14
0x180012698  mov     [rbp+57h+var_28], r14b
0x18001269c  mov     rdx, rdi; void *
0x18001269f  lea     rcx, [rbp+57h+var_30]; this
0x1800126a3  call    ?ImpersonateUser@CAutoImpersonate@@QEAAJPEAX@Z; CAutoImpersonate::ImpersonateUser(void *)
0x1800126a8  mov     edi, eax
0x1800126aa  test    eax, eax
0x1800126ac  jns     short loc_1800126F4
0x1800126ae  mov     rcx, [rbp+5Fh]; this
0x1800126b2  mov     r9d, eax; char *
0x1800126b5  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800126bc  mov     edx, 0A5h; void *
0x1800126c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800126c6  lea     rcx, [rbp+57h+var_30]; this
0x1800126ca  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x1800126cf  nop
0x1800126d0  lea     rcx, [rbp+57h+pSid1]
0x1800126d4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AJPEAX@Z$1?ResultFromHeapFree@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800126d9  nop
0x1800126da  mov     rcx, [rbp+57h+hMem]; hMem
0x1800126de  test    rcx, rcx
0x1800126e1  jz      short loc_1800126F0
0x1800126e3  call    cs:__imp_LocalFree
0x1800126ea  nop     dword ptr [rax+rax+00h]
0x1800126ef  nop
0x1800126f0  mov     eax, edi
0x1800126f2  jmp     short loc_180012770
0x1800126f4  mov     rdx, rsi; unsigned __int16 **
0x1800126f7  mov     ecx, 6; NameFormat
0x1800126fc  call    ?GetUserNameAlloc@@YAJW4EXTENDED_NAME_FORMAT@@PEAPEAG@Z; GetUserNameAlloc(EXTENDED_NAME_FORMAT,ushort * *)
0x180012701  lea     ecx, [rax+7FF8FACCh]
0x180012707  cmp     ecx, 17h
0x18001270a  ja      short loc_180012716
0x18001270c  mov     edx, 880001h
0x180012711  bt      edx, ecx
0x180012714  jb      short loc_180012740
0x180012716  cmp     eax, 80070032h
0x18001271b  jz      short loc_180012740
0x18001271d  cmp     eax, 800704BCh
0x180012722  jz      short loc_180012740
0x180012724  mov     rcx, [rbp+5Fh]; this
0x180012728  test    eax, eax
0x18001272a  jns     short loc_180012740
0x18001272c  mov     r9d, eax; char *
0x18001272f  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\p"...
0x180012736  mov     edx, 0AFh; void *
0x18001273b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180012740  lea     rcx, [rbp+57h+var_30]; this
0x180012744  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x180012749  nop
0x18001274a  test    rbx, rbx
0x18001274d  jz      short loc_180012758
0x18001274f  mov     rcx, rbx; lpMem
0x180012752  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180012757  nop
0x180012758  mov     rcx, [rbp+57h+hMem]; hMem
0x18001275c  test    rcx, rcx
0x18001275f  jz      short loc_18001276E
0x180012761  call    cs:__imp_LocalFree
0x180012768  nop     dword ptr [rax+rax+00h]
0x18001276d  nop
0x18001276e  xor     eax, eax
0x180012770  mov     rcx, [rbp+57h+var_18]
0x180012774  xor     rcx, rsp; StackCookie
0x180012777  call    __security_check_cookie
0x18001277c  lea     r11, [rsp+0A0h+var_10]
0x180012784  mov     rbx, [r11+30h]
0x180012788  mov     rsi, [r11+38h]
0x18001278c  mov     rsp, r11
0x18001278f  pop     r14
0x180012791  pop     rdi
0x180012792  pop     rbp
0x180012793  retn
```
