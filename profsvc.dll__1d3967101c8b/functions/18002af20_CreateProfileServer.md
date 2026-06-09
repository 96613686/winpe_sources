# CreateProfileServer

- ea: `0x18002af20`
- end: `0x18002b194`
- name: `CreateProfileServer`
- size: `628`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x1800090d8`
- `0x180018bcc`
- `0x18001a110`
- `0x180024dd4`
- `0x180025254`
- `0x18002af20`
- `0x18002b19c`
- `0x18002b1c8`
- `0x18002d2d8`
- `0x18002db38`
- `0x18002ed00`
- `0x18003a730`
- `0x180049e7c`
- `0x18004ac30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002b0e4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002b124`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002b0e4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002b124`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18002b000`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18002b000`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002afc8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002afc8`

## string_xrefs

- `0x18002afd9`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`
- `0x18002b011`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`
- `0x18002b073`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`
- `0x18002b0cb`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`
- `0x18002b14e`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`
- `0x18002af54`: `CreateActivity`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CreateProfileServer(
        __int64 a1,
        const WCHAR *a2,
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
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-C8h] BYREF
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
LABEL_28:
    LastError = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profrpc.cpp",
      (const char *)0x80070057LL,
      v16);
    goto LABEL_29;
  }
  if ( !a3 )
  {
    v8 = 621;
    goto LABEL_28;
  }
  if ( !a4 || a5 - 1 > 0x103 )
  {
    v8 = 625;
    goto LABEL_28;
  }
  Sid = 0;
  if ( !ConvertStringSidToSidW(a2, &Sid) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x274,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profrpc.cpp",
                  v9);
LABEL_9:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&Sid);
    goto LABEL_29;
  }
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
  if ( v11 < 0 )
  {
    v12 = 634;
LABEL_14:
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
  v11 = _CheckAdmin();
  LastError = v11;
  if ( v11 < 0 )
  {
    v12 = 636;
    goto LABEL_14;
  }
  SRWLock = 0;
  ProfileP = CProfMgrAutoLock::Lock((CProfMgrAutoLock *)&SRWLock, a2);
  LastError = ProfileP;
  if ( ProfileP < 0 )
  {
    v14 = 640;
    goto LABEL_20;
  }
  ProfileP = CreateProfileP(a2, Sid, a3, a4, a5);
  LastError = ProfileP;
  if ( ProfileP < 0 )
  {
    v14 = 643;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profrpc.cpp",
      (const char *)(unsigned int)ProfileP,
      v16);
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    goto LABEL_15;
  }
  wil::ActivityBase<ProfileServiceLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v24);
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  CThreadContext::~CThreadContext((CThreadContext *)&v19);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&Sid);
  LastError = 0;
LABEL_29:
  ProfileServiceTelemetry::CreateActivity::~CreateActivity((ProfileServiceTelemetry::CreateActivity *)v24);
  return LastError;
}

```

## disassembly

```asm
0x18002af20  mov     [rsp-8+arg_0], rbx
0x18002af25  push    rbp
0x18002af26  push    rsi
0x18002af27  push    rdi
0x18002af28  push    r14
0x18002af2a  push    r15
0x18002af2c  lea     rbp, [rsp-0D0h]
0x18002af34  sub     rsp, 1D0h
0x18002af3b  mov     rax, cs:__security_cookie
0x18002af42  xor     rax, rsp
0x18002af45  mov     [rbp+0F0h+var_30], rax
0x18002af4c  mov     rdi, rdx
0x18002af4f  lea     rcx, [rsp+1F0h+var_180]; struct wil::details::IFailureCallback *
0x18002af54  lea     rdx, aCreateactivity; "CreateActivity"
0x18002af5b  mov     r15, r9
0x18002af5e  mov     r14, r8
0x18002af61  call    ??0?$ActivityBase@VProfileServiceLogging@@$00$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ProfileServiceLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileServiceLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18002af66  lea     rax, ??_7CreateActivity@ProfileServiceTelemetry@@6B@; const ProfileServiceTelemetry::CreateActivity::`vftable'
0x18002af6d  lea     rcx, [rsp+1F0h+var_180]; this
0x18002af72  mov     [rsp+1F0h+var_180], rax
0x18002af77  call    ?StartActivity@CreateActivity@ProfileServiceTelemetry@@QEAAXXZ; ProfileServiceTelemetry::CreateActivity::StartActivity(void)
0x18002af7c  test    rdi, rdi
0x18002af7f  jnz     short loc_18002AF8B
0x18002af81  mov     edx, 26Ch
0x18002af86  jmp     loc_18002B147
0x18002af8b  test    r14, r14
0x18002af8e  jnz     short loc_18002AF9A
0x18002af90  mov     edx, 26Dh
0x18002af95  jmp     loc_18002B147
0x18002af9a  test    r15, r15
0x18002af9d  jz      loc_18002B142
0x18002afa3  mov     esi, [rbp+0F0h+arg_20]
0x18002afa9  lea     eax, [rsi-1]
0x18002afac  cmp     eax, 103h
0x18002afb1  ja      loc_18002B142
0x18002afb7  lea     rdx, [rsp+1F0h+Sid]; Sid
0x18002afbc  mov     [rsp+1F0h+Sid], 0
0x18002afc5  mov     rcx, rdi; StringSid
0x18002afc8  call    cs:__imp_ConvertStringSidToSidW
0x18002afce  test    eax, eax
0x18002afd0  jnz     short loc_18002AFFB
0x18002afd2  mov     rcx, [rbp+0F8h]; this
0x18002afd9  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002afe0  mov     edx, 274h; void *
0x18002afe5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002afea  mov     ebx, eax
0x18002afec  lea     rcx, [rsp+1F0h+Sid]
0x18002aff1  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002aff6  jmp     loc_18002B162
0x18002affb  mov     rcx, [rsp+1F0h+Sid]; pSid
0x18002b000  call    cs:__imp_IsValidSid
0x18002b006  test    eax, eax
0x18002b008  jnz     short loc_18002B02C
0x18002b00a  mov     rcx, [rbp+0F8h]; this
0x18002b011  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002b018  mov     ebx, 80070057h
0x18002b01d  mov     edx, 276h; void *
0x18002b022  mov     r9d, ebx; char *
0x18002b025  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b02a  jmp     short loc_18002AFEC
0x18002b02c  xorps   xmm0, xmm0
0x18002b02f  mov     [rsp+1F0h+var_1B0], 0
0x18002b037  lea     rcx, [rsp+1F0h+var_1B0]; this
0x18002b03c  mov     [rsp+1F0h+var_1A8], 0
0x18002b045  movdqu  [rsp+1F0h+var_190], xmm0
0x18002b04b  mov     [rsp+1F0h+var_1A0], 0
0x18002b054  mov     [rsp+1F0h+var_198], 0
0x18002b05c  call    ?ImpersonateRpcClient@CThreadContext@@QEAAJXZ; CThreadContext::ImpersonateRpcClient(void)
0x18002b061  mov     ebx, eax
0x18002b063  test    eax, eax
0x18002b065  jns     short loc_18002B091
0x18002b067  mov     edx, 27Ah; void *
0x18002b06c  mov     rcx, [rbp+0F8h]; this
0x18002b073  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002b07a  mov     r9d, eax; char *
0x18002b07d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b082  lea     rcx, [rsp+1F0h+var_1B0]; this
0x18002b087  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x18002b08c  jmp     loc_18002AFEC
0x18002b091  call    ?_CheckAdmin@@YAJXZ; _CheckAdmin(void)
0x18002b096  mov     ebx, eax
0x18002b098  test    eax, eax
0x18002b09a  jns     short loc_18002B0A3
0x18002b09c  mov     edx, 27Ch
0x18002b0a1  jmp     short loc_18002B06C
0x18002b0a3  mov     rdx, rdi; unsigned __int16 *
0x18002b0a6  mov     [rsp+1F0h+SRWLock], 0
0x18002b0af  lea     rcx, [rsp+1F0h+SRWLock]; this
0x18002b0b4  call    ?Lock@CProfMgrAutoLock@@QEAAJPEBG@Z; CProfMgrAutoLock::Lock(ushort const *)
0x18002b0b9  mov     ebx, eax
0x18002b0bb  test    eax, eax
0x18002b0bd  jns     short loc_18002B0EC
0x18002b0bf  mov     edx, 280h; void *
0x18002b0c4  mov     rcx, [rbp+0F8h]; this
0x18002b0cb  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002b0d2  mov     r9d, eax; char *
0x18002b0d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b0da  mov     rcx, [rsp+1F0h+SRWLock]; SRWLock
0x18002b0df  test    rcx, rcx
0x18002b0e2  jz      short loc_18002B082
0x18002b0e4  call    cs:__imp_ReleaseSRWLockExclusive
0x18002b0ea  jmp     short loc_18002B082
0x18002b0ec  mov     rdx, [rsp+1F0h+Sid]; void *
0x18002b0f1  mov     r9, r15; unsigned __int16 *
0x18002b0f4  mov     r8, r14; unsigned __int16 *
0x18002b0f7  mov     [rsp+1F0h+var_1D0], esi; unsigned int
0x18002b0fb  mov     rcx, rdi; unsigned __int16 *
0x18002b0fe  call    ?CreateProfileP@@YAJPEBGPEAX0PEAGK@Z; CreateProfileP(ushort const *,void *,ushort const *,ushort *,ulong)
0x18002b103  mov     ebx, eax
0x18002b105  test    eax, eax
0x18002b107  jns     short loc_18002B110
0x18002b109  mov     edx, 283h
0x18002b10e  jmp     short loc_18002B0C4
0x18002b110  lea     rcx, [rsp+1F0h+var_180]
0x18002b115  call    ?Stop@?$ActivityBase@VProfileServiceLogging@@$00$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ProfileServiceLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18002b11a  mov     rcx, [rsp+1F0h+SRWLock]; SRWLock
0x18002b11f  test    rcx, rcx
0x18002b122  jz      short loc_18002B12A
0x18002b124  call    cs:__imp_ReleaseSRWLockExclusive
0x18002b12a  lea     rcx, [rsp+1F0h+var_1B0]; this
0x18002b12f  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x18002b134  lea     rcx, [rsp+1F0h+Sid]
0x18002b139  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002b13e  xor     ebx, ebx
0x18002b140  jmp     short loc_18002B162
0x18002b142  mov     edx, 271h; void *
0x18002b147  mov     rcx, [rbp+0F8h]; this
0x18002b14e  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002b155  mov     ebx, 80070057h
0x18002b15a  mov     r9d, ebx; char *
0x18002b15d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b162  lea     rcx, [rsp+1F0h+var_180]; this
0x18002b167  call    ??1CreateActivity@ProfileServiceTelemetry@@QEAA@XZ; ProfileServiceTelemetry::CreateActivity::~CreateActivity(void)
0x18002b16c  mov     eax, ebx
0x18002b16e  mov     rcx, [rbp+0F0h+var_30]
0x18002b175  xor     rcx, rsp; StackCookie
0x18002b178  call    __security_check_cookie
0x18002b17d  mov     rbx, [rsp+1F0h+arg_0]
0x18002b185  add     rsp, 1D0h
0x18002b18c  pop     r15
0x18002b18e  pop     r14
0x18002b190  pop     rdi
0x18002b191  pop     rsi
0x18002b192  pop     rbp
0x18002b193  retn
```
