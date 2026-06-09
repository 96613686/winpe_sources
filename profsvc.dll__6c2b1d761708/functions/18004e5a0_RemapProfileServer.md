# RemapProfileServer

- ea: `0x18004e5a0`
- end: `0x18004e902`
- name: `RemapProfileServer`
- size: `866`
- prototype: `__int64 __fastcall(__int64, char, const unsigned __int16 *, const WCHAR *)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18001c358`
- `0x18001db10`
- `0x180023950`
- `0x1800275fc`
- `0x18002793c`
- `0x18002837c`
- `0x18002df48`
- `0x18002fa8c`
- `0x180030ad0`
- `0x18003bc70`
- `0x18004c390`
- `0x18004c6a0`
- `0x18004d40c`
- `0x18004d4a8`
- `0x18004e5a0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004e7af`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004e7af`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18004e6b5`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18004e736`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18004e6b5`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18004e736`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18004e772`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18004e772`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18004e677`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18004e6f8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18004e677`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18004e6f8`

## string_xrefs

- `0x18004e68e`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`
- `0x18004e6cc`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`
- `0x18004e70f`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`
- `0x18004e752`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`
- `0x18004e7df`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`
- `0x18004e8c3`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`

## pseudocode

```c
__int64 __fastcall RemapProfileServer(__int64 a1, char a2, const unsigned __int16 *a3, const WCHAR *a4)
{
  int v7; // eax
  unsigned int LastError; // ebx
  __int64 v9; // r9
  __int64 v10; // rdx
  int v11; // eax
  const char *v12; // r9
  const char *v13; // r9
  __int64 v14; // rdx
  int v15; // eax
  __int64 v16; // rdx
  int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  int bIgnoreCasea; // [rsp+20h] [rbp-E0h]
  PSID Sid; // [rsp+30h] [rbp-D0h] BYREF
  PSID pSid; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v22; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v23; // [rsp+48h] [rbp-B8h] BYREF
  int v24; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v25; // [rsp+58h] [rbp-A8h]
  __int64 v26; // [rsp+60h] [rbp-A0h]
  int v27; // [rsp+68h] [rbp-98h]
  __int128 v28; // [rsp+70h] [rbp-90h]
  _QWORD v29[42]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+108h]

  wil::ActivityBase<ProfileServiceLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileServiceLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v29);
  v29[0] = &ProfileServiceTelemetry::RemapProfileActivity::`vftable';
  ProfileServiceTelemetry::RemapProfileActivity::StartActivity((ProfileServiceTelemetry::RemapProfileActivity *)v29);
  v24 = 0;
  v25 = 0;
  v28 = 0;
  v26 = 0;
  v27 = 0;
  v7 = CThreadContext::ImpersonateRpcClient((CThreadContext *)&v24);
  LastError = v7;
  if ( v7 < 0 )
  {
    v9 = (unsigned int)v7;
    v10 = 548;
LABEL_34:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profrpc.cpp",
      (const char *)v9,
      bIgnoreCase);
    goto LABEL_35;
  }
  v11 = _CheckAdmin();
  LastError = v11;
  if ( v11 < 0 )
  {
    v9 = (unsigned int)v11;
    v10 = 550;
    goto LABEL_34;
  }
  if ( !a3 || !a4 )
  {
    LastError = -2147024809;
    v10 = 553;
    v9 = 2147942487LL;
    goto LABEL_34;
  }
  Sid = 0;
  if ( ConvertStringSidToSidW(a3, &Sid) )
  {
    if ( !IsValidSid(Sid) )
    {
      LastError = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x22E,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profrpc.cpp",
        (const char *)0x80070057LL,
        bIgnoreCase);
      goto LABEL_9;
    }
    pSid = 0;
    if ( !ConvertStringSidToSidW(a4, &pSid) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x231,
                    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profrpc.cpp",
                    v13);
LABEL_14:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pSid);
      goto LABEL_9;
    }
    if ( !IsValidSid(pSid) )
    {
      v14 = 562;
LABEL_17:
      LastError = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profrpc.cpp",
        (const char *)0x80070057LL,
        bIgnoreCase);
      goto LABEL_14;
    }
    if ( EqualSid(Sid, pSid) )
    {
      v14 = 565;
      goto LABEL_17;
    }
    v23 = 0;
    v22 = 0;
    if ( CompareStringOrdinal(a3, -1, a4, -1, 1) == 1 )
    {
      v15 = CProfMgrAutoLock::Lock((CProfMgrAutoLock *)&v23, a3);
      LastError = v15;
      if ( v15 < 0 )
      {
        v16 = 576;
LABEL_23:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v16,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profrpc.cpp",
          (const char *)(unsigned int)v15,
          bIgnoreCasea);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v22);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v23);
        goto LABEL_14;
      }
      v15 = CProfMgrAutoLock::Lock((CProfMgrAutoLock *)&v22, a4);
      LastError = v15;
      if ( v15 < 0 )
      {
        v16 = 577;
        goto LABEL_23;
      }
    }
    else
    {
      v15 = CProfMgrAutoLock::Lock((CProfMgrAutoLock *)&v23, a4);
      LastError = v15;
      if ( v15 < 0 )
      {
        v16 = 581;
        goto LABEL_23;
      }
      v15 = CProfMgrAutoLock::Lock((CProfMgrAutoLock *)&v22, a3);
      LastError = v15;
      if ( v15 < 0 )
      {
        v16 = 582;
        goto LABEL_23;
      }
    }
    v15 = RemapProfileP(a2, Sid, pSid, a3, a4);
    LastError = v15;
    if ( v15 >= 0 )
    {
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v22);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v23);
      wil::ActivityBase<ProfileServiceLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v29);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pSid);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&Sid);
      LastError = 0;
      goto LABEL_35;
    }
    v16 = 586;
    goto LABEL_23;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x22D,
                (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profrpc.cpp",
                v12);
LABEL_9:
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&Sid);
LABEL_35:
  CThreadContext::~CThreadContext((CThreadContext *)&v24);
  ProfileServiceTelemetry::RemapProfileActivity::~RemapProfileActivity((ProfileServiceTelemetry::RemapProfileActivity *)v29);
  return LastError;
}

```

## disassembly

```asm
0x18004e5a0  push    rbp
0x18004e5a2  push    rbx
0x18004e5a3  push    rsi
0x18004e5a4  push    rdi
0x18004e5a5  push    r14
0x18004e5a7  lea     rbp, [rsp-0E0h]
0x18004e5af  sub     rsp, 1E0h
0x18004e5b6  mov     rax, cs:__security_cookie
0x18004e5bd  xor     rax, rsp
0x18004e5c0  mov     [rbp+100h+var_30], rax
0x18004e5c7  mov     r14d, edx
0x18004e5ca  lea     rcx, [rbp+100h+var_180]; struct wil::details::IFailureCallback *
0x18004e5ce  lea     rdx, aRemapprofileac; "RemapProfileActivity"
0x18004e5d5  mov     rsi, r9
0x18004e5d8  mov     rdi, r8
0x18004e5db  call    ??0?$ActivityBase@VProfileServiceLogging@@$00$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ProfileServiceLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileServiceLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18004e5e0  lea     rax, ??_7RemapProfileActivity@ProfileServiceTelemetry@@6B@; const ProfileServiceTelemetry::RemapProfileActivity::`vftable'
0x18004e5e7  lea     rcx, [rbp+100h+var_180]; this
0x18004e5eb  mov     [rbp+100h+var_180], rax
0x18004e5ef  call    ?StartActivity@RemapProfileActivity@ProfileServiceTelemetry@@QEAAXXZ; ProfileServiceTelemetry::RemapProfileActivity::StartActivity(void)
0x18004e5f4  xorps   xmm0, xmm0
0x18004e5f7  mov     [rsp+200h+var_1B0], 0
0x18004e5ff  lea     rcx, [rsp+200h+var_1B0]; this
0x18004e604  mov     [rsp+200h+var_1A8], 0
0x18004e60d  movdqu  [rsp+200h+var_190], xmm0
0x18004e613  mov     [rsp+200h+var_1A0], 0
0x18004e61c  mov     [rsp+200h+var_198], 0
0x18004e624  call    ?ImpersonateRpcClient@CThreadContext@@QEAAJXZ; CThreadContext::ImpersonateRpcClient(void)
0x18004e629  mov     ebx, eax
0x18004e62b  test    eax, eax
0x18004e62d  jns     short loc_18004E63C
0x18004e62f  mov     r9d, eax
0x18004e632  mov     edx, 224h
0x18004e637  jmp     loc_18004E8BC
0x18004e63c  call    ?_CheckAdmin@@YAJXZ; _CheckAdmin(void)
0x18004e641  mov     ebx, eax
0x18004e643  test    eax, eax
0x18004e645  jns     short loc_18004E654
0x18004e647  mov     r9d, eax
0x18004e64a  mov     edx, 226h
0x18004e64f  jmp     loc_18004E8BC
0x18004e654  test    rdi, rdi
0x18004e657  jz      loc_18004E8AF
0x18004e65d  test    rsi, rsi
0x18004e660  jz      loc_18004E8AF
0x18004e666  lea     rdx, [rsp+200h+Sid]; Sid
0x18004e66b  mov     [rsp+200h+Sid], 0
0x18004e674  mov     rcx, rdi; StringSid
0x18004e677  call    cs:__imp_ConvertStringSidToSidW
0x18004e67e  nop     dword ptr [rax+rax+00h]
0x18004e683  test    eax, eax
0x18004e685  jnz     short loc_18004E6B0
0x18004e687  mov     rcx, [rbp+108h]; this
0x18004e68e  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004e695  mov     edx, 22Dh; void *
0x18004e69a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004e69f  mov     ebx, eax
0x18004e6a1  lea     rcx, [rsp+200h+Sid]
0x18004e6a6  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18004e6ab  jmp     loc_18004E8CF
0x18004e6b0  mov     rcx, [rsp+200h+Sid]; pSid
0x18004e6b5  call    cs:__imp_IsValidSid
0x18004e6bc  nop     dword ptr [rax+rax+00h]
0x18004e6c1  test    eax, eax
0x18004e6c3  jnz     short loc_18004E6E7
0x18004e6c5  mov     rcx, [rbp+108h]; this
0x18004e6cc  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004e6d3  mov     ebx, 80070057h
0x18004e6d8  mov     edx, 22Eh; void *
0x18004e6dd  mov     r9d, ebx; char *
0x18004e6e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e6e5  jmp     short loc_18004E6A1
0x18004e6e7  lea     rdx, [rsp+200h+pSid]; Sid
0x18004e6ec  mov     [rsp+200h+pSid], 0
0x18004e6f5  mov     rcx, rsi; StringSid
0x18004e6f8  call    cs:__imp_ConvertStringSidToSidW
0x18004e6ff  nop     dword ptr [rax+rax+00h]
0x18004e704  test    eax, eax
0x18004e706  jnz     short loc_18004E731
0x18004e708  mov     rcx, [rbp+108h]; this
0x18004e70f  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004e716  mov     edx, 231h; void *
0x18004e71b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004e720  mov     ebx, eax
0x18004e722  lea     rcx, [rsp+200h+pSid]
0x18004e727  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18004e72c  jmp     loc_18004E6A1
0x18004e731  mov     rcx, [rsp+200h+pSid]; pSid
0x18004e736  call    cs:__imp_IsValidSid
0x18004e73d  nop     dword ptr [rax+rax+00h]
0x18004e742  test    eax, eax
0x18004e744  jnz     short loc_18004E768
0x18004e746  mov     edx, 232h; void *
0x18004e74b  mov     rcx, [rbp+108h]; this
0x18004e752  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004e759  mov     ebx, 80070057h
0x18004e75e  mov     r9d, ebx; char *
0x18004e761  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e766  jmp     short loc_18004E722
0x18004e768  mov     rdx, [rsp+200h+pSid]; pSid2
0x18004e76d  mov     rcx, [rsp+200h+Sid]; pSid1
0x18004e772  call    cs:__imp_EqualSid
0x18004e779  nop     dword ptr [rax+rax+00h]
0x18004e77e  test    eax, eax
0x18004e780  jz      short loc_18004E789
0x18004e782  mov     edx, 235h
0x18004e787  jmp     short loc_18004E74B
0x18004e789  or      edx, 0FFFFFFFFh; cchCount1
0x18004e78c  mov     [rsp+200h+var_1B8], 0
0x18004e795  mov     r9d, edx; cchCount2
0x18004e798  mov     [rsp+200h+var_1C0], 0
0x18004e7a1  mov     r8, rsi; lpString2
0x18004e7a4  mov     [rsp+200h+bIgnoreCase], 1; int
0x18004e7ac  mov     rcx, rdi; lpString1
0x18004e7af  call    cs:__imp_CompareStringOrdinal
0x18004e7b6  nop     dword ptr [rax+rax+00h]
0x18004e7bb  lea     rcx, [rsp+200h+var_1B8]; this
0x18004e7c0  cmp     eax, 1
0x18004e7c3  jnz     short loc_18004E821
0x18004e7c5  mov     rdx, rdi; unsigned __int16 *
0x18004e7c8  call    ?Lock@CProfMgrAutoLock@@QEAAJPEBG@Z; CProfMgrAutoLock::Lock(ushort const *)
0x18004e7cd  mov     ebx, eax
0x18004e7cf  test    eax, eax
0x18004e7d1  jns     short loc_18004E807
0x18004e7d3  mov     edx, 240h; void *
0x18004e7d8  mov     rcx, [rbp+108h]; this
0x18004e7df  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004e7e6  mov     r9d, eax; char *
0x18004e7e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e7ee  lea     rcx, [rsp+200h+var_1C0]
0x18004e7f3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18004e7f8  lea     rcx, [rsp+200h+var_1B8]
0x18004e7fd  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18004e802  jmp     loc_18004E722
0x18004e807  mov     rdx, rsi; unsigned __int16 *
0x18004e80a  lea     rcx, [rsp+200h+var_1C0]; this
0x18004e80f  call    ?Lock@CProfMgrAutoLock@@QEAAJPEBG@Z; CProfMgrAutoLock::Lock(ushort const *)
0x18004e814  mov     ebx, eax
0x18004e816  test    eax, eax
0x18004e818  jns     short loc_18004E850
0x18004e81a  mov     edx, 241h
0x18004e81f  jmp     short loc_18004E7D8
0x18004e821  mov     rdx, rsi; unsigned __int16 *
0x18004e824  call    ?Lock@CProfMgrAutoLock@@QEAAJPEBG@Z; CProfMgrAutoLock::Lock(ushort const *)
0x18004e829  mov     ebx, eax
0x18004e82b  test    eax, eax
0x18004e82d  jns     short loc_18004E836
0x18004e82f  mov     edx, 245h
0x18004e834  jmp     short loc_18004E7D8
0x18004e836  mov     rdx, rdi; unsigned __int16 *
0x18004e839  lea     rcx, [rsp+200h+var_1C0]; this
0x18004e83e  call    ?Lock@CProfMgrAutoLock@@QEAAJPEBG@Z; CProfMgrAutoLock::Lock(ushort const *)
0x18004e843  mov     ebx, eax
0x18004e845  test    eax, eax
0x18004e847  jns     short loc_18004E850
0x18004e849  mov     edx, 246h
0x18004e84e  jmp     short loc_18004E7D8
0x18004e850  mov     r8, [rsp+200h+pSid]; void *
0x18004e855  mov     r9, rdi; unsigned __int16 *
0x18004e858  mov     rdx, [rsp+200h+Sid]; void *
0x18004e85d  mov     ecx, r14d; unsigned int
0x18004e860  mov     qword ptr [rsp+200h+bIgnoreCase], rsi; unsigned __int16 *
0x18004e865  call    ?RemapProfileP@@YAJKPEAX0PEBG1@Z; RemapProfileP(ulong,void *,void *,ushort const *,ushort const *)
0x18004e86a  mov     ebx, eax
0x18004e86c  test    eax, eax
0x18004e86e  jns     short loc_18004E87A
0x18004e870  mov     edx, 24Ah
0x18004e875  jmp     loc_18004E7D8
0x18004e87a  lea     rcx, [rsp+200h+var_1C0]
0x18004e87f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18004e884  lea     rcx, [rsp+200h+var_1B8]
0x18004e889  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18004e88e  lea     rcx, [rbp+100h+var_180]
0x18004e892  call    ?Stop@?$ActivityBase@VProfileServiceLogging@@$00$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ProfileServiceLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18004e897  lea     rcx, [rsp+200h+pSid]
0x18004e89c  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18004e8a1  lea     rcx, [rsp+200h+Sid]
0x18004e8a6  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18004e8ab  xor     ebx, ebx
0x18004e8ad  jmp     short loc_18004E8CF
0x18004e8af  mov     ebx, 80070057h
0x18004e8b4  mov     edx, 229h; void *
0x18004e8b9  mov     r9d, ebx; char *
0x18004e8bc  mov     rcx, [rbp+108h]; this
0x18004e8c3  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004e8ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e8cf  lea     rcx, [rsp+200h+var_1B0]; this
0x18004e8d4  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x18004e8d9  lea     rcx, [rbp+100h+var_180]; this
0x18004e8dd  call    ??1RemapProfileActivity@ProfileServiceTelemetry@@QEAA@XZ; ProfileServiceTelemetry::RemapProfileActivity::~RemapProfileActivity(void)
0x18004e8e2  mov     eax, ebx
0x18004e8e4  mov     rcx, [rbp+100h+var_30]
0x18004e8eb  xor     rcx, rsp; StackCookie
0x18004e8ee  call    __security_check_cookie
0x18004e8f3  add     rsp, 1E0h
0x18004e8fa  pop     r14
0x18004e8fc  pop     rdi
0x18004e8fd  pop     rsi
0x18004e8fe  pop     rbx
0x18004e8ff  pop     rbp
0x18004e900  retn
```
