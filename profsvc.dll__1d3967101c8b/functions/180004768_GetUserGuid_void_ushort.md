# GetUserGuid(void *,ushort * *)

- ea: `0x180004768`
- end: `0x1800049d4`
- name: `?GetUserGuid@@YAJPEAXPEAPEAG@Z`
- size: `620`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001f0c0`
- `0x18004e444`
- `0x18004e5b0`

## callees

- `0x180004170`
- `0x180004768`
- `0x1800049e0`
- `0x180008200`
- `0x1800084a0`
- `0x18000a320`
- `0x180025254`
- `0x18002541c`
- `0x18002d2d8`
- `0x18002db38`
- `0x18002f8e0`
- `0x180030e58`
- `0x180030ebc`
- `0x18003a730`
- `0x18003f42c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000488f`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000488f`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180004807`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180004807`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800047bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004831`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000492f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800049a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800047bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004831`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000492f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800049a7`

## string_xrefs

- `0x180004815`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x18000485c`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x1800048b1`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x1800048fd`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x180004975`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x18000489d`: `User SID matches local system, returning Invalid Arg.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetUserGuid(HANDLE TokenHandle, unsigned __int16 **a2)
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
  UserSid = GetUserSid(TokenHandle, &pSid1);
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
  v9 = CAutoImpersonate::ImpersonateUser((CAutoImpersonate *)&v17, TokenHandle);
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
          (int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
          (const char *)(unsigned int)UserNameAlloc);
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
    if ( v8 )
      ResultFromHeapFree(v8);
    if ( hMem )
      LocalFree(hMem);
    return v10;
  }
}

```

## disassembly

```asm
0x180004768  mov     [rsp-8+arg_10], rbx
0x18000476d  mov     [rsp-8+arg_18], rsi
0x180004772  push    rbp
0x180004773  push    rdi
0x180004774  push    r14
0x180004776  lea     rbp, [rsp-47h]
0x18000477b  sub     rsp, 90h
0x180004782  mov     rax, cs:__security_cookie
0x180004789  xor     rax, rsp
0x18000478c  mov     [rbp+57h+var_18], rax
0x180004790  mov     rsi, rdx
0x180004793  mov     rdi, rcx
0x180004796  xor     r14d, r14d
0x180004799  mov     [rdx], r14
0x18000479c  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r14d
0x1800047a0  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x1800047a6  mov     [rbp+57h+hMem], r14
0x1800047aa  mov     rbx, [rbp+57h+hMem]
0x1800047ae  test    rbx, rbx
0x1800047b1  jz      short loc_1800047CF
0x1800047b3  lea     rcx, [rbp+57h+pSid1]; this
0x1800047b7  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800047bc  mov     rcx, rbx; hMem
0x1800047bf  call    cs:__imp_LocalFree
0x1800047c5  lea     rcx, [rbp+57h+pSid1]; this
0x1800047c9  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800047ce  nop
0x1800047cf  mov     [rbp+57h+hMem], r14
0x1800047d3  lea     rax, [rbp+57h+hMem]
0x1800047d7  mov     [rsp+0A0h+pSid], rax; pSid
0x1800047dc  mov     [rsp+0A0h+nSubAuthority7], r14d; nSubAuthority7
0x1800047e1  mov     [rsp+0A0h+nSubAuthority6], r14d; nSubAuthority6
0x1800047e6  mov     [rsp+0A0h+nSubAuthority5], r14d; nSubAuthority5
0x1800047eb  mov     [rsp+0A0h+nSubAuthority4], r14d; nSubAuthority4
0x1800047f0  mov     dword ptr [rsp+0A0h+nSubAuthority3], r14d; char *
0x1800047f5  mov     [rsp+0A0h+nSubAuthority2], r14d; int
0x1800047fa  xor     r9d, r9d; nSubAuthority1
0x1800047fd  lea     r8d, [r9+12h]; nSubAuthority0
0x180004801  mov     dl, 1; nSubAuthorityCount
0x180004803  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180004807  call    cs:__imp_AllocateAndInitializeSid
0x18000480d  test    eax, eax
0x18000480f  jnz     short loc_18000483F
0x180004811  mov     rcx, [rbp+5Fh]; this
0x180004815  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000481c  mov     edx, 99h; void *
0x180004821  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180004826  mov     ebx, eax
0x180004828  mov     rcx, [rbp+57h+hMem]; hMem
0x18000482c  test    rcx, rcx
0x18000482f  jz      short loc_180004838
0x180004831  call    cs:__imp_LocalFree
0x180004837  nop
0x180004838  mov     eax, ebx
0x18000483a  jmp     loc_1800049B0
0x18000483f  mov     [rbp+57h+pSid1], r14
0x180004843  lea     rdx, [rbp+57h+pSid1]; void **
0x180004847  mov     rcx, rdi; TokenHandle
0x18000484a  call    ?GetUserSid@@YAJPEAXPEAPEAX@Z; GetUserSid(void *,void * *)
0x18000484f  mov     ebx, eax
0x180004851  test    eax, eax
0x180004853  jns     short loc_180004884
0x180004855  mov     rcx, [rbp+5Fh]; this
0x180004859  mov     r9d, eax; char *
0x18000485c  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\p"...
0x180004863  mov     edx, 9Ch; void *
0x180004868  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000486d  nop
0x18000486e  lea     rcx, [rbp+57h+pSid1]
0x180004872  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AJPEAX@Z$1?ResultFromHeapFree@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180004877  nop
0x180004878  lea     rcx, [rbp+57h+hMem]
0x18000487c  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180004881  nop
0x180004882  jmp     short loc_180004838
0x180004884  mov     rdx, [rbp+57h+hMem]; pSid2
0x180004888  mov     rbx, [rbp+57h+pSid1]
0x18000488c  mov     rcx, rbx; pSid1
0x18000488f  call    cs:__imp_EqualSid
0x180004895  test    eax, eax
0x180004897  jz      short loc_1800048DC
0x180004899  mov     rcx, [rbp+5Fh]; this
0x18000489d  lea     rax, aUserSidMatches; "User SID matches local system, returnin"...
0x1800048a4  mov     qword ptr [rsp+0A0h+nSubAuthority2], rax; int
0x1800048a9  mov     ebx, 80070057h
0x1800048ae  mov     r9d, ebx; char *
0x1800048b1  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800048b8  mov     edx, 9Eh; void *
0x1800048bd  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800048c2  nop
0x1800048c3  lea     rcx, [rbp+57h+pSid1]
0x1800048c7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AJPEAX@Z$1?ResultFromHeapFree@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800048cc  nop
0x1800048cd  lea     rcx, [rbp+57h+hMem]
0x1800048d1  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800048d6  nop
0x1800048d7  jmp     loc_180004838
0x1800048dc  mov     [rbp+57h+var_30], r14
0x1800048e0  mov     [rbp+57h+var_28], r14b
0x1800048e4  mov     rdx, rdi; void *
0x1800048e7  lea     rcx, [rbp+57h+var_30]; this
0x1800048eb  call    ?ImpersonateUser@CAutoImpersonate@@QEAAJPEAX@Z; CAutoImpersonate::ImpersonateUser(void *)
0x1800048f0  mov     edi, eax
0x1800048f2  test    eax, eax
0x1800048f4  jns     short loc_18000493A
0x1800048f6  mov     rcx, [rbp+5Fh]; this
0x1800048fa  mov     r9d, eax; char *
0x1800048fd  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\p"...
0x180004904  mov     edx, 0A5h; void *
0x180004909  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000490e  lea     rcx, [rbp+57h+var_30]; this
0x180004912  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x180004917  nop
0x180004918  test    rbx, rbx
0x18000491b  jz      short loc_180004926
0x18000491d  mov     rcx, rbx; lpMem
0x180004920  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180004925  nop
0x180004926  mov     rcx, [rbp+57h+hMem]; hMem
0x18000492a  test    rcx, rcx
0x18000492d  jz      short loc_180004936
0x18000492f  call    cs:__imp_LocalFree
0x180004935  nop
0x180004936  mov     eax, edi
0x180004938  jmp     short loc_1800049B0
0x18000493a  mov     rdx, rsi; unsigned __int16 **
0x18000493d  mov     ecx, 6; NameFormat
0x180004942  call    ?GetUserNameAlloc@@YAJW4EXTENDED_NAME_FORMAT@@PEAPEAG@Z; GetUserNameAlloc(EXTENDED_NAME_FORMAT,ushort * *)
0x180004947  lea     ecx, [rax+7FF8FACCh]
0x18000494d  cmp     ecx, 17h
0x180004950  ja      short loc_18000495C
0x180004952  mov     edx, 880001h
0x180004957  bt      edx, ecx
0x18000495a  jb      short loc_180004986
0x18000495c  cmp     eax, 80070032h
0x180004961  jz      short loc_180004986
0x180004963  cmp     eax, 800704BCh
0x180004968  jz      short loc_180004986
0x18000496a  mov     rcx, [rbp+5Fh]; this
0x18000496e  test    eax, eax
0x180004970  jns     short loc_180004986
0x180004972  mov     r9d, eax; char *
0x180004975  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000497c  mov     edx, 0AFh; void *
0x180004981  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180004986  lea     rcx, [rbp+57h+var_30]; this
0x18000498a  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x18000498f  nop
0x180004990  test    rbx, rbx
0x180004993  jz      short loc_18000499E
0x180004995  mov     rcx, rbx; lpMem
0x180004998  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x18000499d  nop
0x18000499e  mov     rcx, [rbp+57h+hMem]; hMem
0x1800049a2  test    rcx, rcx
0x1800049a5  jz      short loc_1800049AE
0x1800049a7  call    cs:__imp_LocalFree
0x1800049ad  nop
0x1800049ae  xor     eax, eax
0x1800049b0  mov     rcx, [rbp+57h+var_18]
0x1800049b4  xor     rcx, rsp; StackCookie
0x1800049b7  call    __security_check_cookie
0x1800049bc  lea     r11, [rsp+0A0h+var_10]
0x1800049c4  mov     rbx, [r11+30h]
0x1800049c8  mov     rsi, [r11+38h]
0x1800049cc  mov     rsp, r11
0x1800049cf  pop     r14
0x1800049d1  pop     rdi
0x1800049d2  pop     rbp
0x1800049d3  retn
```
