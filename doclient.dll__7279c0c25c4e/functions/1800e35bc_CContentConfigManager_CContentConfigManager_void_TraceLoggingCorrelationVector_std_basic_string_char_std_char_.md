# CContentConfigManager::CContentConfigManager(void *,TraceLoggingCorrelationVector *,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x1800e35bc`
- end: `0x1800e39e4`
- name: `??0CContentConfigManager@@QEAA@PEAXPEAVTraceLoggingCorrelationVector@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@22@Z`
- size: `1064`
- prototype: `struct CContentConfigManager *__fastcall(struct CContentConfigManager *, HANDLE hExistingToken, TraceLoggingCorrelationVector *this, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18002d4ec`

## callees

- `0x180007ca4`
- `0x18000cea4`
- `0x18000f014`
- `0x180026ea8`
- `0x180027188`
- `0x18004406c`
- `0x18007ca54`
- `0x1800a1ea4`
- `0x1800ab528`
- `0x1800bdab8`
- `0x1800d7274`
- `0x1800e35bc`
- `0x1800e49b0`
- `0x1800e5024`
- `0x1800e96f4`
- `0x1800f0d60`
- `0x1800f82f0`
- `0x1800f8314`
- `0x1800f8320`
- `0x180108e50`
- `0x180108ed0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e37e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e37e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e37d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e37d5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e37e8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e37e8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e37bc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e37bc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800e3789`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800e3789`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800e380b`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800e380b`

## string_xrefs

- `0x1800e3819`: `DuplicateToken failed`
- `0x1800e3757`: `CContentConfigManager::CContentConfigManager`
- `0x1800e3828`: `C:\__w\1\s\src\DeliveryOptimization\ConfigManagement\ContentConfigManager.cpp`
- `0x1800e39d2`: `C:\__w\1\s\src\DeliveryOptimization\ConfigManagement\ContentConfigManager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
struct CContentConfigManager *__fastcall CContentConfigManager::CContentConfigManager(
        struct CContentConfigManager *a1,
        HANDLE hExistingToken,
        TraceLoggingCorrelationVector *this,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  const char *v10; // r15
  void **v11; // rsi
  int ServiceEndpoints; // eax
  void *v13; // rdi
  DWORD LastError; // ebx
  unsigned int v15; // eax
  struct CGlobalObjects *v16; // rax
  void (__fastcall ***v17)(_QWORD, __int64); // rcx
  void *v18; // rdi
  CDiscoveryProvider *v19; // rax
  void (__fastcall ***v20)(_QWORD, __int64); // rcx
  bool v21; // dl
  struct TraceLoggingCorrelationVector *v22; // rax
  void *v23; // rcx
  int TokenType; // [rsp+20h] [rbp-118h]
  const char *phNewToken; // [rsp+28h] [rbp-110h]
  _QWORD *v27; // [rsp+30h] [rbp-108h]
  void *v28; // [rsp+30h] [rbp-108h]
  char v29[144]; // [rsp+50h] [rbp-E8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  *(_QWORD *)a1 = &CContentConfigManager::`vftable';
  *((_QWORD *)a1 + 1) = *((_QWORD *)CGlobalObjects::Instance() + 2);
  *((_QWORD *)a1 + 2) = 0;
  *((_QWORD *)a1 + 3) = 0;
  *((_QWORD *)a1 + 4) = 0;
  *((_QWORD *)a1 + 5) = 0;
  v10 = (char *)a1 + 48;
  std::string::string((__int64)a1 + 48, a4);
  std::string::string((__int64)a1 + 80, a5);
  std::string::string((__int64)a1 + 112, a6);
  *((_QWORD *)a1 + 18) = 0;
  *(_OWORD *)((char *)a1 + 152) = 0;
  *((_QWORD *)a1 + 21) = 0;
  *((_QWORD *)a1 + 22) = 15;
  *((_BYTE *)a1 + 152) = 0;
  *(_OWORD *)((char *)a1 + 184) = 0;
  *((_QWORD *)a1 + 25) = 0;
  *((_QWORD *)a1 + 26) = 15;
  *((_BYTE *)a1 + 184) = 0;
  *((_DWORD *)a1 + 54) = -1;
  COrderedTaskExecutor::COrderedTaskExecutor((struct CContentConfigManager *)((char *)a1 + 224));
  v11 = (void **)((char *)a1 + 328);
  *((_QWORD *)a1 + 41) = 0;
  *((_QWORD *)a1 + 42) = 258;
  *(_OWORD *)((char *)a1 + 360) = 0;
  *(_OWORD *)((char *)a1 + 376) = 0;
  *(_OWORD *)((char *)a1 + 392) = 0;
  *(_OWORD *)((char *)a1 + 344) = 0;
  *((_DWORD *)a1 + 102) = -1;
  *((_DWORD *)a1 + 103) = 0;
  CGlobalConfigManager::GetGeoCacheId(*((_QWORD *)a1 + 1), (char *)a1 + 416);
  *((_QWORD *)a1 + 56) = 0;
  *((_BYTE *)a1 + 456) = 0;
  CContentConfigManager::SetExperimentId(a1, *(_DWORD *)(*((_QWORD *)a1 + 1) + 680LL));
  if ( *((_QWORD *)a1 + 9) > 0xFu )
    v10 = *(const char **)v10;
  LogMessage(5u, "CContentConfigManager::CContentConfigManager", 0x27u, "New CCM for file %s", v10);
  if ( *((_QWORD *)a1 + 12) )
    StripUrlQueryParams((char *)a1 + 80);
  AcquireSRWLockExclusive((PSRWLOCK)a1 + 18);
  ServiceEndpoints = CContentConfigManager::_GetServiceEndpoints(a1);
  if ( ServiceEndpoints < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x31,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\ConfigManagement\\ContentConfigManager.cpp",
      (const char *)(unsigned int)ServiceEndpoints,
      TokenType);
  ReleaseSRWLockExclusive((PSRWLOCK)a1 + 18);
  if ( hExistingToken )
  {
    v13 = *v11;
    if ( *v11 && v13 != (void *)-1LL )
    {
      LastError = GetLastError();
      CloseHandle(v13);
      SetLastError(LastError);
    }
    *v11 = 0;
    v15 = DuplicateTokenEx(hExistingToken, 0xEu, 0, SecurityImpersonation, TokenImpersonation, (PHANDLE)a1 + 41);
    wil::details::in1diag3::Log_IfWin32BoolFalseMsg(
      retaddr,
      (void *)0x3F,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\ConfigManagement\\ContentConfigManager.cpp",
      (const char *)v15,
      (int)"DuplicateToken failed",
      phNewToken);
  }
  v27 = operator new(0x138u);
  memset(v27, 0, 0x138u);
  v16 = CGlobalObjects::Instance();
  CServiceConfigProvider::CServiceConfigProvider(v27, 3, *((_QWORD *)v16 + 2));
  *v27 = &CContentPolicyProvider::`vftable';
  *((_OWORD *)v27 + 11) = 0;
  v27[24] = 0;
  v27[25] = 15;
  *((_BYTE *)v27 + 176) = 0;
  v27[26] = 0;
  v27[27] = 0;
  v27[28] = 0;
  *(_OWORD *)(v27 + 29) = 0;
  v27[31] = 0;
  v27[32] = 7;
  *((_WORD *)v27 + 116) = 0;
  *(_OWORD *)(v27 + 33) = 0;
  *(_OWORD *)(v27 + 35) = 0;
  *((_DWORD *)v27 + 74) = 0;
  v27[38] = a1;
  v17 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)a1 + 2);
  *((_QWORD *)a1 + 2) = v27;
  if ( v17 )
    (**v17)(v17, 1);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_v15_57241951_ReorganizeDiscCall>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_v15_57241951_ReorganizeDiscCall>::GetImpl'::`2'::impl) )
  {
    v18 = *v11;
    v28 = operator new(0x1C0u);
    memset(v28, 0, 0x1C0u);
    v19 = CDiscoveryProvider::CDiscoveryProvider((CDiscoveryProvider *)v28, a1, v18, this);
    v20 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)a1 + 3);
    *((_QWORD *)a1 + 3) = v19;
    if ( v20 )
      (**v20)(v20, 1);
  }
  if ( this )
  {
    TraceLoggingCorrelationVector::Increment(this, v29);
    v22 = TraceLoggingCorrelationVector::Extend(v29, v21);
    v23 = (void *)*((_QWORD *)a1 + 5);
    *((_QWORD *)a1 + 5) = v22;
    if ( v23 )
      operator delete(v23);
  }
  return a1;
}

```

## disassembly

```asm
0x1800e35bc  push    rbx
0x1800e35be  push    rbp
0x1800e35bf  push    rsi
0x1800e35c0  push    rdi
0x1800e35c1  push    r12
0x1800e35c3  push    r13
0x1800e35c5  push    r14
0x1800e35c7  push    r15
0x1800e35c9  sub     rsp, 0F8h
0x1800e35d0  mov     rax, cs:__security_cookie
0x1800e35d7  xor     rax, rsp
0x1800e35da  mov     [rsp+138h+var_58], rax
0x1800e35e2  mov     rdi, r9
0x1800e35e5  mov     rbp, r8
0x1800e35e8  mov     r12, rdx
0x1800e35eb  mov     r14, rcx
0x1800e35ee  mov     [rsp+138h+var_F8], rcx
0x1800e35f3  mov     rbx, [rsp+138h+arg_20]
0x1800e35fb  mov     rsi, [rsp+138h+arg_28]
0x1800e3603  xor     r13d, r13d
0x1800e3606  lea     rax, ??_7CContentConfigManager@@6B@; const CContentConfigManager::`vftable'
0x1800e360d  mov     [rcx], rax
0x1800e3610  call    ?Instance@CGlobalObjects@@SAAEAV1@XZ; CGlobalObjects::Instance(void)
0x1800e3615  mov     rax, [rax+10h]
0x1800e3619  mov     [r14+8], rax
0x1800e361d  mov     [r14+10h], r13
0x1800e3621  mov     [r14+18h], r13
0x1800e3625  mov     [r14+20h], r13
0x1800e3629  mov     [r14+28h], r13
0x1800e362d  lea     r15, [r14+30h]
0x1800e3631  mov     rdx, rdi
0x1800e3634  mov     rcx, r15
0x1800e3637  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x1800e363c  nop
0x1800e363d  lea     rcx, [r14+50h]
0x1800e3641  mov     rdx, rbx
0x1800e3644  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x1800e3649  nop
0x1800e364a  lea     rcx, [r14+70h]
0x1800e364e  mov     rdx, rsi
0x1800e3651  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x1800e3656  nop
0x1800e3657  lea     rbx, [r14+90h]
0x1800e365e  mov     [rbx], r13
0x1800e3661  lea     rdi, [r14+98h]
0x1800e3668  xorps   xmm0, xmm0
0x1800e366b  movups  xmmword ptr [rdi], xmm0
0x1800e366e  mov     [rdi+10h], r13
0x1800e3672  lea     eax, [r13+0Fh]
0x1800e3676  mov     [rdi+18h], rax
0x1800e367a  mov     [rdi], r13b
0x1800e367d  lea     r13, [r14+0B8h]
0x1800e3684  movups  xmmword ptr [r13+0], xmm0
0x1800e3689  mov     qword ptr [r13+10h], 0
0x1800e3691  mov     [r13+18h], rax
0x1800e3695  mov     byte ptr [r13+0], 0
0x1800e369a  mov     dword ptr [r14+0D8h], 0FFFFFFFFh
0x1800e36a5  lea     rcx, [r14+0E0h]; this
0x1800e36ac  call    ??0COrderedTaskExecutor@@QEAA@XZ; COrderedTaskExecutor::COrderedTaskExecutor(void)
0x1800e36b1  nop
0x1800e36b2  lea     rsi, [r14+148h]
0x1800e36b9  mov     qword ptr [rsi], 0
0x1800e36c0  mov     qword ptr [r14+150h], 102h
0x1800e36cb  xorps   xmm0, xmm0
0x1800e36ce  movups  xmmword ptr [r14+168h], xmm0
0x1800e36d6  movups  xmmword ptr [r14+178h], xmm0
0x1800e36de  movups  xmmword ptr [r14+188h], xmm0
0x1800e36e6  xorps   xmm1, xmm1
0x1800e36e9  movdqu  xmmword ptr [r14+158h], xmm1
0x1800e36f2  mov     dword ptr [r14+198h], 0FFFFFFFFh
0x1800e36fd  mov     dword ptr [r14+19Ch], 0
0x1800e3708  lea     rdx, [r14+1A0h]
0x1800e370f  mov     rcx, [r14+8]
0x1800e3713  call    ?GetGeoCacheId@CGlobalConfigManager@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; CGlobalConfigManager::GetGeoCacheId(void)
0x1800e3718  nop
0x1800e3719  xor     eax, eax
0x1800e371b  mov     [r14+1C0h], rax
0x1800e3722  mov     [r14+1C8h], al
0x1800e3729  mov     rdx, [r14+8]
0x1800e372d  mov     edx, [rdx+2A8h]; unsigned int
0x1800e3733  mov     rcx, r14; this
0x1800e3736  call    ?SetExperimentId@CContentConfigManager@@QEAA_NI@Z; CContentConfigManager::SetExperimentId(uint)
0x1800e373b  cmp     qword ptr [r15+18h], 0Fh
0x1800e3740  jbe     short loc_1800E3745
0x1800e3742  mov     r15, [r15]
0x1800e3745  mov     qword ptr [rsp+138h+TokenType], r15; int
0x1800e374a  lea     r9, aNewCcmForFileS; "New CCM for file %s"
0x1800e3751  mov     r8d, 27h ; '''; unsigned int
0x1800e3757  lea     rdx, aCcontentconfig_6; "CContentConfigManager::CContentConfigMa"...
0x1800e375e  lea     ecx, [r8-22h]; unsigned __int8
0x1800e3762  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x1800e3767  xor     r15d, r15d
0x1800e376a  cmp     [r14+60h], r15
0x1800e376e  jz      short loc_1800E3779
0x1800e3770  lea     rcx, [r14+50h]
0x1800e3774  call    ?StripUrlQueryParams@@YAXAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; StripUrlQueryParams(std::string &)
0x1800e3779  xorps   xmm0, xmm0
0x1800e377c  movups  [rsp+138h+var_108], xmm0
0x1800e3781  mov     qword ptr [rsp+138h+var_108], rbx
0x1800e3786  mov     rcx, rbx; SRWLock
0x1800e3789  call    cs:__imp_AcquireSRWLockExclusive
0x1800e378f  mov     byte ptr [rsp+138h+var_108+8], 1
0x1800e3794  lea     r9, [r14+0D8h]
0x1800e379b  mov     r8, r13
0x1800e379e  mov     rdx, rdi
0x1800e37a1  mov     rcx, r14
0x1800e37a4  call    ?_GetServiceEndpoints@CContentConfigManager@@AEBAJAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@0AEAI@Z; CContentConfigManager::_GetServiceEndpoints(std::string &,std::string &,uint &)
0x1800e37a9  mov     rcx, [rsp+138h]; this
0x1800e37b1  test    eax, eax
0x1800e37b3  js      loc_1800E39CF
0x1800e37b9  mov     rcx, rbx; SRWLock
0x1800e37bc  call    cs:__imp_ReleaseSRWLockExclusive
0x1800e37c2  test    r12, r12
0x1800e37c5  jz      short loc_1800E3839
0x1800e37c7  mov     rdi, [rsi]
0x1800e37ca  test    rdi, rdi
0x1800e37cd  jz      short loc_1800E37EE
0x1800e37cf  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800e37d3  jz      short loc_1800E37EE
0x1800e37d5  call    cs:__imp_GetLastError
0x1800e37db  mov     ebx, eax
0x1800e37dd  mov     rcx, rdi; hObject
0x1800e37e0  call    cs:__imp_CloseHandle
0x1800e37e6  mov     ecx, ebx; dwErrCode
0x1800e37e8  call    cs:__imp_SetLastError
0x1800e37ee  mov     [rsi], r15
0x1800e37f1  mov     [rsp+138h+phNewToken], rsi; char *
0x1800e37f6  mov     r9d, 2; ImpersonationLevel
0x1800e37fc  mov     [rsp+138h+TokenType], r9d; TokenType
0x1800e3801  xor     r8d, r8d; lpTokenAttributes
0x1800e3804  lea     edx, [r9+0Ch]; dwDesiredAccess
0x1800e3808  mov     rcx, r12; hExistingToken
0x1800e380b  call    cs:__imp_DuplicateTokenEx
0x1800e3811  mov     rcx, [rsp+138h]; this
0x1800e3819  lea     rdx, aDuplicatetoken; "DuplicateToken failed"
0x1800e3820  mov     qword ptr [rsp+138h+TokenType], rdx; int
0x1800e3825  mov     r9d, eax; char *
0x1800e3828  lea     r8, aCW1SSrcDeliver_9; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800e382f  mov     edx, 3Fh ; '?'; void *
0x1800e3834  call    ?Log_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Log_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x1800e3839  mov     edi, 138h
0x1800e383e  mov     ecx, edi; Size
0x1800e3840  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800e3845  mov     rbx, rax
0x1800e3848  mov     qword ptr [rsp+138h+var_108], rax
0x1800e384d  mov     r8d, edi; Size
0x1800e3850  xor     edx, edx; Val
0x1800e3852  mov     rcx, rax; void *
0x1800e3855  call    memset
0x1800e385a  call    ?Instance@CGlobalObjects@@SAAEAV1@XZ; CGlobalObjects::Instance(void)
0x1800e385f  mov     r12d, 1
0x1800e3865  mov     r9d, r12d
0x1800e3868  mov     r8, [rax+10h]
0x1800e386c  lea     edx, [r12+2]
0x1800e3871  mov     rcx, rbx
0x1800e3874  call    ??0CServiceConfigProvider@@QEAA@W4_ConfigProviderType@@AEAVCGlobalConfigManager@@W4RetryStrategy@CPeriodicOpTracker@@@Z; CServiceConfigProvider::CServiceConfigProvider(_ConfigProviderType,CGlobalConfigManager &,CPeriodicOpTracker::RetryStrategy)
0x1800e3879  lea     rax, ??_7CContentPolicyProvider@@6B@; const CContentPolicyProvider::`vftable'
0x1800e3880  mov     [rbx], rax
0x1800e3883  xorps   xmm0, xmm0
0x1800e3886  movups  xmmword ptr [rbx+0B0h], xmm0
0x1800e388d  mov     [rbx+0C0h], r15
0x1800e3894  mov     qword ptr [rbx+0C8h], 0Fh
0x1800e389f  mov     [rbx+0B0h], r15b
0x1800e38a6  mov     [rbx+0D0h], r15
0x1800e38ad  mov     [rbx+0D8h], r15
0x1800e38b4  mov     [rbx+0E0h], r15
0x1800e38bb  movups  xmmword ptr [rbx+0E8h], xmm0
0x1800e38c2  mov     [rbx+0F8h], r15
0x1800e38c9  mov     qword ptr [rbx+100h], 7
0x1800e38d4  mov     [rbx+0E8h], r15w
0x1800e38dc  movups  xmmword ptr [rbx+108h], xmm0
0x1800e38e3  movups  xmmword ptr [rbx+118h], xmm0
0x1800e38ea  mov     [rbx+128h], r15d
0x1800e38f1  mov     [rbx+130h], r14
0x1800e38f8  mov     rcx, [r14+10h]
0x1800e38fc  mov     [r14+10h], rbx
0x1800e3900  test    rcx, rcx
0x1800e3903  jz      short loc_1800E3913
0x1800e3905  mov     rax, [rcx]
0x1800e3908  mov     edx, r12d
0x1800e390b  mov     rax, [rax]
0x1800e390e  call    _guard_dispatch_icall
0x1800e3913  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_v15_57241951_ReorganizeDiscCall@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_v15_57241951_ReorganizeDiscCall@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_v15_57241951_ReorganizeDiscCall> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_v15_57241951_ReorganizeDiscCall>::GetImpl(void)'::`2'::impl
0x1800e391a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_v15_57241951_ReorganizeDiscCall@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_v15_57241951_ReorganizeDiscCall>::__private_IsEnabled(void)
0x1800e391f  test    al, al
0x1800e3921  jnz     short loc_1800E3974
0x1800e3923  mov     rdi, [rsi]
0x1800e3926  mov     esi, 1C0h
0x1800e392b  mov     ecx, esi; Size
0x1800e392d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800e3932  mov     rbx, rax
0x1800e3935  mov     qword ptr [rsp+138h+var_108], rax
0x1800e393a  mov     r8d, esi; Size
0x1800e393d  xor     edx, edx; Val
0x1800e393f  mov     rcx, rax; void *
0x1800e3942  call    memset
0x1800e3947  mov     r9, rbp; struct TraceLoggingCorrelationVector *
0x1800e394a  mov     r8, rdi; void *
0x1800e394d  mov     rdx, r14; struct CContentConfigManager *
0x1800e3950  mov     rcx, rbx; this
0x1800e3953  call    ??0CDiscoveryProvider@@QEAA@AEAVCContentConfigManager@@PEAXPEAVTraceLoggingCorrelationVector@@@Z; CDiscoveryProvider::CDiscoveryProvider(CContentConfigManager &,void *,TraceLoggingCorrelationVector *)
0x1800e3958  nop
0x1800e3959  mov     rcx, [r14+18h]
0x1800e395d  mov     [r14+18h], rax
0x1800e3961  test    rcx, rcx
0x1800e3964  jz      short loc_1800E3974
0x1800e3966  mov     rax, [rcx]
0x1800e3969  mov     edx, r12d
0x1800e396c  mov     rax, [rax]
0x1800e396f  call    _guard_dispatch_icall
0x1800e3974  test    rbp, rbp
0x1800e3977  jz      short loc_1800E39A8
0x1800e3979  lea     rdx, [rsp+138h+var_E8]; char *
0x1800e397e  mov     rcx, rbp; this
0x1800e3981  call    ?Increment@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::Increment(char *)
0x1800e3986  lea     rcx, [rsp+138h+var_E8]; char *
0x1800e398b  call    ?Extend@TraceLoggingCorrelationVector@@SAPEAV1@PEBD_N@Z; TraceLoggingCorrelationVector::Extend(char const *,bool)
0x1800e3990  mov     rcx, [r14+28h]; Block
0x1800e3994  mov     [r14+28h], rax
0x1800e3998  test    rcx, rcx
0x1800e399b  jz      short loc_1800E39A8
0x1800e399d  mov     edx, 90h
0x1800e39a2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800e39a7  nop
0x1800e39a8  mov     rax, r14
0x1800e39ab  mov     rcx, [rsp+138h+var_58]
0x1800e39b3  xor     rcx, rsp; StackCookie
0x1800e39b6  call    __security_check_cookie
0x1800e39bb  add     rsp, 0F8h
0x1800e39c2  pop     r15
0x1800e39c4  pop     r14
0x1800e39c6  pop     r13
0x1800e39c8  pop     r12
0x1800e39ca  pop     rdi
0x1800e39cb  pop     rsi
0x1800e39cc  pop     rbp
0x1800e39cd  pop     rbx
0x1800e39ce  retn
0x1800e39cf  mov     r9d, eax; char *
0x1800e39d2  lea     r8, aCW1SSrcDeliver_9; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800e39d9  mov     edx, 31h ; '1'; void *
0x1800e39de  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
