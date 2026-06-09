# RemapProfileServer

- ea: `0x18002bb60`
- end: `0x18002bed6`
- name: `RemapProfileServer`
- size: `886`
- prototype: `__int64 __fastcall(__int64, unsigned int, const WCHAR *, const WCHAR *)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x1800090d8`
- `0x180018bcc`
- `0x18001a110`
- `0x180024dd4`
- `0x180025254`
- `0x18002b1c8`
- `0x18002bb60`
- `0x18002bedc`
- `0x18002d2d8`
- `0x18002db38`
- `0x18002e0cc`
- `0x18003a730`
- `0x180049e7c`
- `0x18004ae54`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002bd9c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002bddf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002be4d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002be5d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002bd9c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002bddf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002be4d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002be5d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002bd51`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002bd51`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18002bc6f`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18002bce4`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18002bc6f`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18002bce4`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002bd1a`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002bd1a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002bc37`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002bcac`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002bc37`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002bcac`

## string_xrefs

- `0x18002bc48`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`
- `0x18002bc80`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`
- `0x18002bcbd`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`
- `0x18002bcfa`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`
- `0x18002bd7f`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`
- `0x18002bdc6`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`
- `0x18002be98`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`

## pseudocode

```c
__int64 __fastcall RemapProfileServer(__int64 a1, unsigned int a2, const WCHAR *a3, const WCHAR *a4)
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
  int v17; // eax
  __int64 v18; // rdx
  int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  int bIgnoreCasea; // [rsp+20h] [rbp-E0h]
  PSID Sid; // [rsp+30h] [rbp-D0h] BYREF
  PSID pSid; // [rsp+38h] [rbp-C8h] BYREF
  PSRWLOCK SRWLock; // [rsp+40h] [rbp-C0h] BYREF
  PSRWLOCK v25; // [rsp+48h] [rbp-B8h] BYREF
  int v26; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v27; // [rsp+58h] [rbp-A8h]
  __int64 v28; // [rsp+60h] [rbp-A0h]
  int v29; // [rsp+68h] [rbp-98h]
  __int128 v30; // [rsp+70h] [rbp-90h]
  _QWORD v31[42]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+108h]

  wil::ActivityBase<ProfileServiceLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileServiceLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v31);
  v31[0] = &ProfileServiceTelemetry::RemapProfileActivity::`vftable';
  ProfileServiceTelemetry::RemapProfileActivity::StartActivity((ProfileServiceTelemetry::RemapProfileActivity *)v31);
  v26 = 0;
  v27 = 0;
  v30 = 0;
  v28 = 0;
  v29 = 0;
  v7 = CThreadContext::ImpersonateRpcClient((CThreadContext *)&v26);
  LastError = v7;
  if ( v7 < 0 )
  {
    v9 = (unsigned int)v7;
    v10 = 548;
LABEL_42:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profrpc.cpp",
      (const char *)v9,
      bIgnoreCase);
    goto LABEL_43;
  }
  v11 = _CheckAdmin();
  LastError = v11;
  if ( v11 < 0 )
  {
    v9 = (unsigned int)v11;
    v10 = 550;
    goto LABEL_42;
  }
  if ( !a3 || !a4 )
  {
    LastError = -2147024809;
    v10 = 553;
    v9 = 2147942487LL;
    goto LABEL_42;
  }
  Sid = 0;
  if ( !ConvertStringSidToSidW(a3, &Sid) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x22D,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profrpc.cpp",
                  v12);
LABEL_9:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&Sid);
    goto LABEL_43;
  }
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
  SRWLock = 0;
  v25 = 0;
  if ( CompareStringOrdinal(a3, -1, a4, -1, 1) == 1 )
  {
    v15 = CProfMgrAutoLock::Lock((CProfMgrAutoLock *)&SRWLock, a3);
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
LABEL_24:
      if ( SRWLock )
        ReleaseSRWLockExclusive(SRWLock);
      goto LABEL_14;
    }
    v17 = CProfMgrAutoLock::Lock((CProfMgrAutoLock *)&v25, a4);
    LastError = v17;
    if ( v17 < 0 )
    {
      v18 = 577;
      goto LABEL_28;
    }
  }
  else
  {
    v15 = CProfMgrAutoLock::Lock((CProfMgrAutoLock *)&SRWLock, a4);
    LastError = v15;
    if ( v15 < 0 )
    {
      v16 = 581;
      goto LABEL_23;
    }
    v17 = CProfMgrAutoLock::Lock((CProfMgrAutoLock *)&v25, a3);
    LastError = v17;
    if ( v17 < 0 )
    {
      v18 = 582;
      goto LABEL_28;
    }
  }
  v17 = RemapProfileP(a2, Sid, pSid, a3, a4);
  LastError = v17;
  if ( v17 < 0 )
  {
    v18 = 586;
LABEL_28:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profrpc.cpp",
      (const char *)(unsigned int)v17,
      bIgnoreCasea);
    if ( v25 )
      ReleaseSRWLockExclusive(v25);
    goto LABEL_24;
  }
  if ( v25 )
    ReleaseSRWLockExclusive(v25);
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  wil::ActivityBase<ProfileServiceLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v31);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pSid);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&Sid);
  LastError = 0;
LABEL_43:
  CThreadContext::~CThreadContext((CThreadContext *)&v26);
  ProfileServiceTelemetry::RemapProfileActivity::~RemapProfileActivity((ProfileServiceTelemetry::RemapProfileActivity *)v31);
  return LastError;
}

```

## disassembly

```asm
0x18002bb60  push    rbp
0x18002bb62  push    rbx
0x18002bb63  push    rsi
0x18002bb64  push    rdi
0x18002bb65  push    r14
0x18002bb67  lea     rbp, [rsp-0E0h]
0x18002bb6f  sub     rsp, 1E0h
0x18002bb76  mov     rax, cs:__security_cookie
0x18002bb7d  xor     rax, rsp
0x18002bb80  mov     [rbp+100h+var_30], rax
0x18002bb87  mov     r14d, edx
0x18002bb8a  lea     rcx, [rbp+100h+var_180]; struct wil::details::IFailureCallback *
0x18002bb8e  lea     rdx, aRemapprofileac; "RemapProfileActivity"
0x18002bb95  mov     rsi, r9
0x18002bb98  mov     rdi, r8
0x18002bb9b  call    ??0?$ActivityBase@VProfileServiceLogging@@$00$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ProfileServiceLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileServiceLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18002bba0  lea     rax, ??_7RemapProfileActivity@ProfileServiceTelemetry@@6B@; const ProfileServiceTelemetry::RemapProfileActivity::`vftable'
0x18002bba7  lea     rcx, [rbp+100h+var_180]; this
0x18002bbab  mov     [rbp+100h+var_180], rax
0x18002bbaf  call    ?StartActivity@RemapProfileActivity@ProfileServiceTelemetry@@QEAAXXZ; ProfileServiceTelemetry::RemapProfileActivity::StartActivity(void)
0x18002bbb4  xorps   xmm0, xmm0
0x18002bbb7  mov     [rsp+200h+var_1B0], 0
0x18002bbbf  lea     rcx, [rsp+200h+var_1B0]; this
0x18002bbc4  mov     [rsp+200h+var_1A8], 0
0x18002bbcd  movdqu  [rsp+200h+var_190], xmm0
0x18002bbd3  mov     [rsp+200h+var_1A0], 0
0x18002bbdc  mov     [rsp+200h+var_198], 0
0x18002bbe4  call    ?ImpersonateRpcClient@CThreadContext@@QEAAJXZ; CThreadContext::ImpersonateRpcClient(void)
0x18002bbe9  mov     ebx, eax
0x18002bbeb  test    eax, eax
0x18002bbed  jns     short loc_18002BBFC
0x18002bbef  mov     r9d, eax
0x18002bbf2  mov     edx, 224h
0x18002bbf7  jmp     loc_18002BE91
0x18002bbfc  call    ?_CheckAdmin@@YAJXZ; _CheckAdmin(void)
0x18002bc01  mov     ebx, eax
0x18002bc03  test    eax, eax
0x18002bc05  jns     short loc_18002BC14
0x18002bc07  mov     r9d, eax
0x18002bc0a  mov     edx, 226h
0x18002bc0f  jmp     loc_18002BE91
0x18002bc14  test    rdi, rdi
0x18002bc17  jz      loc_18002BE84
0x18002bc1d  test    rsi, rsi
0x18002bc20  jz      loc_18002BE84
0x18002bc26  lea     rdx, [rsp+200h+Sid]; Sid
0x18002bc2b  mov     [rsp+200h+Sid], 0
0x18002bc34  mov     rcx, rdi; StringSid
0x18002bc37  call    cs:__imp_ConvertStringSidToSidW
0x18002bc3d  test    eax, eax
0x18002bc3f  jnz     short loc_18002BC6A
0x18002bc41  mov     rcx, [rbp+108h]; this
0x18002bc48  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002bc4f  mov     edx, 22Dh; void *
0x18002bc54  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002bc59  mov     ebx, eax
0x18002bc5b  lea     rcx, [rsp+200h+Sid]
0x18002bc60  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002bc65  jmp     loc_18002BEA4
0x18002bc6a  mov     rcx, [rsp+200h+Sid]; pSid
0x18002bc6f  call    cs:__imp_IsValidSid
0x18002bc75  test    eax, eax
0x18002bc77  jnz     short loc_18002BC9B
0x18002bc79  mov     rcx, [rbp+108h]; this
0x18002bc80  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002bc87  mov     ebx, 80070057h
0x18002bc8c  mov     edx, 22Eh; void *
0x18002bc91  mov     r9d, ebx; char *
0x18002bc94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bc99  jmp     short loc_18002BC5B
0x18002bc9b  lea     rdx, [rsp+200h+pSid]; Sid
0x18002bca0  mov     [rsp+200h+pSid], 0
0x18002bca9  mov     rcx, rsi; StringSid
0x18002bcac  call    cs:__imp_ConvertStringSidToSidW
0x18002bcb2  test    eax, eax
0x18002bcb4  jnz     short loc_18002BCDF
0x18002bcb6  mov     rcx, [rbp+108h]; this
0x18002bcbd  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002bcc4  mov     edx, 231h; void *
0x18002bcc9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002bcce  mov     ebx, eax
0x18002bcd0  lea     rcx, [rsp+200h+pSid]
0x18002bcd5  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002bcda  jmp     loc_18002BC5B
0x18002bcdf  mov     rcx, [rsp+200h+pSid]; pSid
0x18002bce4  call    cs:__imp_IsValidSid
0x18002bcea  test    eax, eax
0x18002bcec  jnz     short loc_18002BD10
0x18002bcee  mov     edx, 232h; void *
0x18002bcf3  mov     rcx, [rbp+108h]; this
0x18002bcfa  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002bd01  mov     ebx, 80070057h
0x18002bd06  mov     r9d, ebx; char *
0x18002bd09  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bd0e  jmp     short loc_18002BCD0
0x18002bd10  mov     rdx, [rsp+200h+pSid]; pSid2
0x18002bd15  mov     rcx, [rsp+200h+Sid]; pSid1
0x18002bd1a  call    cs:__imp_EqualSid
0x18002bd20  test    eax, eax
0x18002bd22  jz      short loc_18002BD2B
0x18002bd24  mov     edx, 235h
0x18002bd29  jmp     short loc_18002BCF3
0x18002bd2b  or      edx, 0FFFFFFFFh; cchCount1
0x18002bd2e  mov     [rsp+200h+SRWLock], 0
0x18002bd37  mov     r9d, edx; cchCount2
0x18002bd3a  mov     [rsp+200h+var_1B8], 0
0x18002bd43  mov     r8, rsi; lpString2
0x18002bd46  mov     [rsp+200h+bIgnoreCase], 1; int
0x18002bd4e  mov     rcx, rdi; lpString1
0x18002bd51  call    cs:__imp_CompareStringOrdinal
0x18002bd57  lea     rcx, [rsp+200h+SRWLock]; this
0x18002bd5c  cmp     eax, 1
0x18002bd5f  jnz     loc_18002BDE7
0x18002bd65  mov     rdx, rdi; unsigned __int16 *
0x18002bd68  call    ?Lock@CProfMgrAutoLock@@QEAAJPEBG@Z; CProfMgrAutoLock::Lock(ushort const *)
0x18002bd6d  mov     ebx, eax
0x18002bd6f  test    eax, eax
0x18002bd71  jns     short loc_18002BDA7
0x18002bd73  mov     edx, 240h; void *
0x18002bd78  mov     rcx, [rbp+108h]; this
0x18002bd7f  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002bd86  mov     r9d, eax; char *
0x18002bd89  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bd8e  mov     rcx, [rsp+200h+SRWLock]; SRWLock
0x18002bd93  test    rcx, rcx
0x18002bd96  jz      loc_18002BCD0
0x18002bd9c  call    cs:__imp_ReleaseSRWLockExclusive
0x18002bda2  jmp     loc_18002BCD0
0x18002bda7  mov     rdx, rsi; unsigned __int16 *
0x18002bdaa  lea     rcx, [rsp+200h+var_1B8]; this
0x18002bdaf  call    ?Lock@CProfMgrAutoLock@@QEAAJPEBG@Z; CProfMgrAutoLock::Lock(ushort const *)
0x18002bdb4  mov     ebx, eax
0x18002bdb6  test    eax, eax
0x18002bdb8  jns     short loc_18002BE19
0x18002bdba  mov     edx, 241h; void *
0x18002bdbf  mov     rcx, [rbp+108h]; this
0x18002bdc6  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002bdcd  mov     r9d, eax; char *
0x18002bdd0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bdd5  mov     rcx, [rsp+200h+var_1B8]; SRWLock
0x18002bdda  test    rcx, rcx
0x18002bddd  jz      short loc_18002BD8E
0x18002bddf  call    cs:__imp_ReleaseSRWLockExclusive
0x18002bde5  jmp     short loc_18002BD8E
0x18002bde7  mov     rdx, rsi; unsigned __int16 *
0x18002bdea  call    ?Lock@CProfMgrAutoLock@@QEAAJPEBG@Z; CProfMgrAutoLock::Lock(ushort const *)
0x18002bdef  mov     ebx, eax
0x18002bdf1  test    eax, eax
0x18002bdf3  jns     short loc_18002BDFF
0x18002bdf5  mov     edx, 245h
0x18002bdfa  jmp     loc_18002BD78
0x18002bdff  mov     rdx, rdi; unsigned __int16 *
0x18002be02  lea     rcx, [rsp+200h+var_1B8]; this
0x18002be07  call    ?Lock@CProfMgrAutoLock@@QEAAJPEBG@Z; CProfMgrAutoLock::Lock(ushort const *)
0x18002be0c  mov     ebx, eax
0x18002be0e  test    eax, eax
0x18002be10  jns     short loc_18002BE19
0x18002be12  mov     edx, 246h
0x18002be17  jmp     short loc_18002BDBF
0x18002be19  mov     r8, [rsp+200h+pSid]; void *
0x18002be1e  mov     r9, rdi; unsigned __int16 *
0x18002be21  mov     rdx, [rsp+200h+Sid]; void *
0x18002be26  mov     ecx, r14d; unsigned int
0x18002be29  mov     qword ptr [rsp+200h+bIgnoreCase], rsi; unsigned __int16 *
0x18002be2e  call    ?RemapProfileP@@YAJKPEAX0PEBG1@Z; RemapProfileP(ulong,void *,void *,ushort const *,ushort const *)
0x18002be33  mov     ebx, eax
0x18002be35  test    eax, eax
0x18002be37  jns     short loc_18002BE43
0x18002be39  mov     edx, 24Ah
0x18002be3e  jmp     loc_18002BDBF
0x18002be43  mov     rcx, [rsp+200h+var_1B8]; SRWLock
0x18002be48  test    rcx, rcx
0x18002be4b  jz      short loc_18002BE53
0x18002be4d  call    cs:__imp_ReleaseSRWLockExclusive
0x18002be53  mov     rcx, [rsp+200h+SRWLock]; SRWLock
0x18002be58  test    rcx, rcx
0x18002be5b  jz      short loc_18002BE63
0x18002be5d  call    cs:__imp_ReleaseSRWLockExclusive
0x18002be63  lea     rcx, [rbp+100h+var_180]
0x18002be67  call    ?Stop@?$ActivityBase@VProfileServiceLogging@@$00$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ProfileServiceLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18002be6c  lea     rcx, [rsp+200h+pSid]
0x18002be71  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002be76  lea     rcx, [rsp+200h+Sid]
0x18002be7b  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002be80  xor     ebx, ebx
0x18002be82  jmp     short loc_18002BEA4
0x18002be84  mov     ebx, 80070057h
0x18002be89  mov     edx, 229h; void *
0x18002be8e  mov     r9d, ebx; char *
0x18002be91  mov     rcx, [rbp+108h]; this
0x18002be98  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002be9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bea4  lea     rcx, [rsp+200h+var_1B0]; this
0x18002bea9  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x18002beae  lea     rcx, [rbp+100h+var_180]; this
0x18002beb2  call    ??1RemapProfileActivity@ProfileServiceTelemetry@@QEAA@XZ; ProfileServiceTelemetry::RemapProfileActivity::~RemapProfileActivity(void)
0x18002beb7  mov     eax, ebx
0x18002beb9  mov     rcx, [rbp+100h+var_30]
0x18002bec0  xor     rcx, rsp; StackCookie
0x18002bec3  call    __security_check_cookie
0x18002bec8  add     rsp, 1E0h
0x18002becf  pop     r14
0x18002bed1  pop     rdi
0x18002bed2  pop     rsi
0x18002bed3  pop     rbx
0x18002bed4  pop     rbp
0x18002bed5  retn
```
