# CreateProfileServer

- ea: `0x18004e150`
- end: `0x18004e3c5`
- name: `CreateProfileServer`
- size: `629`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, unsigned int)`
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
- `0x180030050`
- `0x180030ad0`
- `0x18003bc70`
- `0x18004c390`
- `0x18004c648`
- `0x18004d1d4`
- `0x18004d4a8`
- `0x18004e150`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18004e236`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18004e236`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18004e1f8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18004e1f8`

## string_xrefs

- `0x18004e20f`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`
- `0x18004e24d`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`
- `0x18004e2af`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`
- `0x18004e307`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`
- `0x18004e37e`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`
- `0x18004e184`: `CreateActivity`

## pseudocode

```c
__int64 __fastcall CreateProfileServer(
        __int64 a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned int a5)
{
  __int64 v8; // rdx
  const char *v9; // r9
  unsigned int LastError; // ebx
  int v11; // eax
  __int64 v12; // rdx
  int ProfileP; // eax
  __int64 v14; // rdx
  unsigned int v16; // [rsp+20h] [rbp-E0h]
  PSID Sid; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v18; // [rsp+38h] [rbp-C8h] BYREF
  int v19; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v20; // [rsp+48h] [rbp-B8h]
  __int64 v21; // [rsp+50h] [rbp-B0h]
  int v22; // [rsp+58h] [rbp-A8h]
  __int128 v23; // [rsp+60h] [rbp-A0h]
  _QWORD v24[42]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]

  wil::ActivityBase<ProfileServiceLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileServiceLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v24);
  v24[0] = &ProfileServiceTelemetry::CreateActivity::`vftable';
  ProfileServiceTelemetry::CreateActivity::StartActivity((ProfileServiceTelemetry::CreateActivity *)v24);
  if ( !a2 )
  {
    v8 = 620;
LABEL_25:
    LastError = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profrpc.cpp",
      (const char *)0x80070057LL,
      v16);
    goto LABEL_26;
  }
  if ( !a3 )
  {
    v8 = 621;
    goto LABEL_25;
  }
  if ( !a4 || a5 - 1 > 0x103 )
  {
    v8 = 625;
    goto LABEL_25;
  }
  Sid = 0;
  if ( ConvertStringSidToSidW(a2, &Sid) )
  {
    if ( !IsValidSid(Sid) )
    {
      LastError = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x276,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profrpc.cpp",
        (const char *)0x80070057LL,
        v16);
      goto LABEL_9;
    }
    v19 = 0;
    v20 = 0;
    v23 = 0;
    v21 = 0;
    v22 = 0;
    v11 = CThreadContext::ImpersonateRpcClient((CThreadContext *)&v19);
    LastError = v11;
    if ( v11 >= 0 )
    {
      v11 = _CheckAdmin();
      LastError = v11;
      if ( v11 >= 0 )
      {
        v18 = 0;
        ProfileP = CProfMgrAutoLock::Lock((CProfMgrAutoLock *)&v18, a2);
        LastError = ProfileP;
        if ( ProfileP >= 0 )
        {
          ProfileP = CreateProfileP(a2, Sid, a3, a4, a5);
          LastError = ProfileP;
          if ( ProfileP >= 0 )
          {
            wil::ActivityBase<ProfileServiceLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v24);
            wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v18);
            CThreadContext::~CThreadContext((CThreadContext *)&v19);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&Sid);
            LastError = 0;
            goto LABEL_26;
          }
          v14 = 643;
        }
        else
        {
          v14 = 640;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v14,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profrpc.cpp",
          (const char *)(unsigned int)ProfileP,
          v16);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v18);
        goto LABEL_15;
      }
      v12 = 636;
    }
    else
    {
      v12 = 634;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profrpc.cpp",
      (const char *)(unsigned int)v11,
      v16);
LABEL_15:
    CThreadContext::~CThreadContext((CThreadContext *)&v19);
    goto LABEL_9;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x274,
                (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profrpc.cpp",
                v9);
LABEL_9:
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&Sid);
LABEL_26:
  ProfileServiceTelemetry::CreateActivity::~CreateActivity((ProfileServiceTelemetry::CreateActivity *)v24);
  return LastError;
}

```

## disassembly

```asm
0x18004e150  mov     [rsp-8+arg_0], rbx
0x18004e155  push    rbp
0x18004e156  push    rsi
0x18004e157  push    rdi
0x18004e158  push    r14
0x18004e15a  push    r15
0x18004e15c  lea     rbp, [rsp-0D0h]
0x18004e164  sub     rsp, 1D0h
0x18004e16b  mov     rax, cs:__security_cookie
0x18004e172  xor     rax, rsp
0x18004e175  mov     [rbp+0F0h+var_30], rax
0x18004e17c  mov     rdi, rdx
0x18004e17f  lea     rcx, [rsp+1F0h+var_180]; struct wil::details::IFailureCallback *
0x18004e184  lea     rdx, aCreateactivity; "CreateActivity"
0x18004e18b  mov     r15, r9
0x18004e18e  mov     r14, r8
0x18004e191  call    ??0?$ActivityBase@VProfileServiceLogging@@$00$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ProfileServiceLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileServiceLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18004e196  lea     rax, ??_7CreateActivity@ProfileServiceTelemetry@@6B@; const ProfileServiceTelemetry::CreateActivity::`vftable'
0x18004e19d  lea     rcx, [rsp+1F0h+var_180]; this
0x18004e1a2  mov     [rsp+1F0h+var_180], rax
0x18004e1a7  call    ?StartActivity@CreateActivity@ProfileServiceTelemetry@@QEAAXXZ; ProfileServiceTelemetry::CreateActivity::StartActivity(void)
0x18004e1ac  test    rdi, rdi
0x18004e1af  jnz     short loc_18004E1BB
0x18004e1b1  mov     edx, 26Ch
0x18004e1b6  jmp     loc_18004E377
0x18004e1bb  test    r14, r14
0x18004e1be  jnz     short loc_18004E1CA
0x18004e1c0  mov     edx, 26Dh
0x18004e1c5  jmp     loc_18004E377
0x18004e1ca  test    r15, r15
0x18004e1cd  jz      loc_18004E372
0x18004e1d3  mov     esi, [rbp+0F0h+arg_20]
0x18004e1d9  lea     eax, [rsi-1]
0x18004e1dc  cmp     eax, 103h
0x18004e1e1  ja      loc_18004E372
0x18004e1e7  lea     rdx, [rsp+1F0h+Sid]; Sid
0x18004e1ec  mov     [rsp+1F0h+Sid], 0
0x18004e1f5  mov     rcx, rdi; StringSid
0x18004e1f8  call    cs:__imp_ConvertStringSidToSidW
0x18004e1ff  nop     dword ptr [rax+rax+00h]
0x18004e204  test    eax, eax
0x18004e206  jnz     short loc_18004E231
0x18004e208  mov     rcx, [rbp+0F8h]; this
0x18004e20f  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004e216  mov     edx, 274h; void *
0x18004e21b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004e220  mov     ebx, eax
0x18004e222  lea     rcx, [rsp+1F0h+Sid]
0x18004e227  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18004e22c  jmp     loc_18004E392
0x18004e231  mov     rcx, [rsp+1F0h+Sid]; pSid
0x18004e236  call    cs:__imp_IsValidSid
0x18004e23d  nop     dword ptr [rax+rax+00h]
0x18004e242  test    eax, eax
0x18004e244  jnz     short loc_18004E268
0x18004e246  mov     rcx, [rbp+0F8h]; this
0x18004e24d  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004e254  mov     ebx, 80070057h
0x18004e259  mov     edx, 276h; void *
0x18004e25e  mov     r9d, ebx; char *
0x18004e261  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e266  jmp     short loc_18004E222
0x18004e268  xorps   xmm0, xmm0
0x18004e26b  mov     [rsp+1F0h+var_1B0], 0
0x18004e273  lea     rcx, [rsp+1F0h+var_1B0]; this
0x18004e278  mov     [rsp+1F0h+var_1A8], 0
0x18004e281  movdqu  [rsp+1F0h+var_190], xmm0
0x18004e287  mov     [rsp+1F0h+var_1A0], 0
0x18004e290  mov     [rsp+1F0h+var_198], 0
0x18004e298  call    ?ImpersonateRpcClient@CThreadContext@@QEAAJXZ; CThreadContext::ImpersonateRpcClient(void)
0x18004e29d  mov     ebx, eax
0x18004e29f  test    eax, eax
0x18004e2a1  jns     short loc_18004E2CD
0x18004e2a3  mov     edx, 27Ah; void *
0x18004e2a8  mov     rcx, [rbp+0F8h]; this
0x18004e2af  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004e2b6  mov     r9d, eax; char *
0x18004e2b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e2be  lea     rcx, [rsp+1F0h+var_1B0]; this
0x18004e2c3  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x18004e2c8  jmp     loc_18004E222
0x18004e2cd  call    ?_CheckAdmin@@YAJXZ; _CheckAdmin(void)
0x18004e2d2  mov     ebx, eax
0x18004e2d4  test    eax, eax
0x18004e2d6  jns     short loc_18004E2DF
0x18004e2d8  mov     edx, 27Ch
0x18004e2dd  jmp     short loc_18004E2A8
0x18004e2df  mov     rdx, rdi; unsigned __int16 *
0x18004e2e2  mov     [rsp+1F0h+var_1B8], 0
0x18004e2eb  lea     rcx, [rsp+1F0h+var_1B8]; this
0x18004e2f0  call    ?Lock@CProfMgrAutoLock@@QEAAJPEBG@Z; CProfMgrAutoLock::Lock(ushort const *)
0x18004e2f5  mov     ebx, eax
0x18004e2f7  test    eax, eax
0x18004e2f9  jns     short loc_18004E322
0x18004e2fb  mov     edx, 280h; void *
0x18004e300  mov     rcx, [rbp+0F8h]; this
0x18004e307  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004e30e  mov     r9d, eax; char *
0x18004e311  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e316  lea     rcx, [rsp+1F0h+var_1B8]
0x18004e31b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18004e320  jmp     short loc_18004E2BE
0x18004e322  mov     rdx, [rsp+1F0h+Sid]; void *
0x18004e327  mov     r9, r15; unsigned __int16 *
0x18004e32a  mov     r8, r14; unsigned __int16 *
0x18004e32d  mov     [rsp+1F0h+var_1D0], esi; unsigned int
0x18004e331  mov     rcx, rdi; unsigned __int16 *
0x18004e334  call    ?CreateProfileP@@YAJPEBGPEAX0PEAGK@Z; CreateProfileP(ushort const *,void *,ushort const *,ushort *,ulong)
0x18004e339  mov     ebx, eax
0x18004e33b  test    eax, eax
0x18004e33d  jns     short loc_18004E346
0x18004e33f  mov     edx, 283h
0x18004e344  jmp     short loc_18004E300
0x18004e346  lea     rcx, [rsp+1F0h+var_180]
0x18004e34b  call    ?Stop@?$ActivityBase@VProfileServiceLogging@@$00$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ProfileServiceLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18004e350  lea     rcx, [rsp+1F0h+var_1B8]
0x18004e355  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18004e35a  lea     rcx, [rsp+1F0h+var_1B0]; this
0x18004e35f  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x18004e364  lea     rcx, [rsp+1F0h+Sid]
0x18004e369  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18004e36e  xor     ebx, ebx
0x18004e370  jmp     short loc_18004E392
0x18004e372  mov     edx, 271h; void *
0x18004e377  mov     rcx, [rbp+0F8h]; this
0x18004e37e  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004e385  mov     ebx, 80070057h
0x18004e38a  mov     r9d, ebx; char *
0x18004e38d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e392  lea     rcx, [rsp+1F0h+var_180]; this
0x18004e397  call    ??1CreateActivity@ProfileServiceTelemetry@@QEAA@XZ; ProfileServiceTelemetry::CreateActivity::~CreateActivity(void)
0x18004e39c  mov     eax, ebx
0x18004e39e  mov     rcx, [rbp+0F0h+var_30]
0x18004e3a5  xor     rcx, rsp; StackCookie
0x18004e3a8  call    __security_check_cookie
0x18004e3ad  mov     rbx, [rsp+1F0h+arg_0]
0x18004e3b5  add     rsp, 1D0h
0x18004e3bc  pop     r15
0x18004e3be  pop     r14
0x18004e3c0  pop     rdi
0x18004e3c1  pop     rsi
0x18004e3c2  pop     rbp
0x18004e3c3  retn
```
