# CDownloadManager::CreateJob(char const *,bool,_GUID &,std::shared_ptr<CBackgroundCopyJob> &)

- ea: `0x18009672c`
- end: `0x18009691c`
- name: `?CreateJob@CDownloadManager@@QEAAJPEBD_NAEAU_GUID@@AEAV?$shared_ptr@VCBackgroundCopyJob@@@std@@@Z`
- size: `496`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015a70`
- `0x180016e90`

## callees

- `0x18000933c`
- `0x18000a4fc`
- `0x18007ca54`
- `0x18007e3cc`
- `0x18009672c`
- `0x180097200`
- `0x1800a1ea4`
- `0x1800c6380`
- `0x1800d6360`
- `0x1800d64d8`
- `0x1800d89d8`
- `0x1800f82f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180096790`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800967e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800968e3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180096790`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800967e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800968e3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180096771`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800967c2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800968c4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180096771`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800967c2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800968c4`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180096841`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180096841`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x1800967d7`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x1800968da`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x1800967d7`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x1800968da`

## string_xrefs

- `0x1800968af`: `CDownloadManager::CreateJob`
- `0x1800968a2`: `Create job name = %s, jobId = %s, hr = %x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDownloadManager::CreateJob(
        struct CDownloadManager *a1,
        char *a2,
        __int64 a3,
        struct _GUID *a4,
        __int64 a5)
{
  char *v8; // rbx
  volatile __int32 *v9; // rdi
  NetworkCompliance *v10; // rcx
  int v11; // eax
  unsigned int v12; // esi
  bool v13; // zf
  __int64 result; // rax
  int v15; // eax
  HRESULT Job; // edi
  CGlobalConfigManager *v17; // rdi
  const char *v18; // r9
  int v19; // [rsp+20h] [rbp-A8h]
  GUID pguid; // [rsp+50h] [rbp-78h] BYREF
  char v21[40]; // [rsp+60h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v8 = (char *)a1 + 32;
  AcquireSRWLockExclusive((PSRWLOCK)a1 + 4);
  ++*((_DWORD *)v8 + 3);
  v9 = (volatile __int32 *)(v8 + 8);
  if ( *((_DWORD *)v8 + 3) == 1 )
    _InterlockedExchange(v9, 0);
  ReleaseSRWLockExclusive((PSRWLOCK)v8);
  v11 = NetworkCompliance::VerifyCaller(v10);
  v12 = v11;
  if ( v11 >= 0 )
  {
    v15 = CDeliveryOptimizationManager::WaitForInitAndCheckShutdown(*((CDeliveryOptimizationManager **)a1 + 6));
    try
    {
      Job = v15;
      if ( v15 >= 0 )
      {
        v17 = (CGlobalConfigManager *)*((_QWORD *)CGlobalObjects::Instance() + 2);
        CGlobalConfigManager::RefreshRemoteProviders(v17, 0);
        if ( (unsigned int)CGlobalConfigManager::GetDownloadMode(v17, 0, 0) == 100
          || CGlobalConfigManager::BranchCacheBypass(v17, a2) )
        {
          Job = -2133839870;
        }
        else
        {
          pguid = 0;
          Job = CoCreateGuid(&pguid);
          if ( Job >= 0 )
          {
            Job = CDownloadManager::_InternalCreateJob(a1, a5);
            if ( Job >= 0 )
              *a4 = pguid;
          }
        }
      }
      CGuidToString::CGuidToString((CGuidToString *)v21, a4);
      LogMessage(4u, "CDownloadManager::CreateJob", 0xB7u, "Create job name = %s, jobId = %s, hr = %x", a2, v21, Job);
      AcquireSRWLockExclusive((PSRWLOCK)v8);
      v13 = (*((_DWORD *)v8 + 3))-- == 1;
      if ( v13 )
      {
        *((_DWORD *)v8 + 2) = 1;
        WakeByAddressAll(v8 + 8);
      }
      ReleaseSRWLockExclusive((PSRWLOCK)v8);
      result = (unsigned int)Job;
    }
    catch ( std::bad_alloc )
    {
      return 2147942414LL;
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0xBA,
                             (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\DownloadManager.cpp",
                             v18);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x93,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\DownloadManager.cpp",
      (const char *)(unsigned int)v11,
      v19);
    AcquireSRWLockExclusive((PSRWLOCK)v8);
    v13 = (*((_DWORD *)v8 + 3))-- == 1;
    if ( v13 )
    {
      *v9 = 1;
      WakeByAddressAll(v8 + 8);
    }
    ReleaseSRWLockExclusive((PSRWLOCK)v8);
    return v12;
  }
  return result;
}

```

## disassembly

```asm
0x18009672c  push    rbx
0x18009672e  push    rsi
0x18009672f  push    rdi
0x180096730  push    r12
0x180096732  push    r13
0x180096734  push    r14
0x180096736  push    r15
0x180096738  sub     rsp, 90h
0x18009673f  mov     rax, cs:__security_cookie
0x180096746  xor     rax, rsp
0x180096749  mov     [rsp+0C8h+var_40], rax
0x180096751  mov     r12, r9
0x180096754  mov     r13b, r8b
0x180096757  mov     r15, rdx
0x18009675a  mov     r14, rcx
0x18009675d  mov     rax, [rsp+0C8h+arg_20]
0x180096765  mov     [rsp+0C8h+var_88], rax
0x18009676a  lea     rbx, [rcx+20h]
0x18009676e  mov     rcx, rbx; SRWLock
0x180096771  call    cs:__imp_AcquireSRWLockExclusive
0x180096777  inc     dword ptr [rbx+0Ch]
0x18009677a  lea     rdi, [rbx+8]
0x18009677e  cmp     dword ptr [rbx+0Ch], 1
0x180096782  jnz     short loc_180096788
0x180096784  xor     eax, eax
0x180096786  xchg    eax, [rdi]
0x180096788  mov     [rsp+0C8h+var_80], rbx
0x18009678d  mov     rcx, rbx; SRWLock
0x180096790  call    cs:__imp_ReleaseSRWLockExclusive
0x180096796  nop
0x180096797  call    ?VerifyCaller@NetworkCompliance@@YAJXZ; NetworkCompliance::VerifyCaller(void)
0x18009679c  mov     esi, eax
0x18009679e  test    eax, eax
0x1800967a0  jns     short loc_1800967ED
0x1800967a2  mov     rcx, [rsp+0C8h]; this
0x1800967aa  mov     r9d, eax; char *
0x1800967ad  lea     r8, aCW1SSrcDeliver_99; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800967b4  mov     edx, 93h; void *
0x1800967b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800967be  nop
0x1800967bf  mov     rcx, rbx; SRWLock
0x1800967c2  call    cs:__imp_AcquireSRWLockExclusive
0x1800967c8  add     dword ptr [rbx+0Ch], 0FFFFFFFFh
0x1800967cc  jnz     short loc_1800967DD
0x1800967ce  mov     dword ptr [rdi], 1
0x1800967d4  mov     rcx, rdi; Address
0x1800967d7  call    cs:__imp_WakeByAddressAll
0x1800967dd  mov     rcx, rbx; SRWLock
0x1800967e0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800967e6  mov     eax, esi
0x1800967e8  jmp     loc_1800968F8
0x1800967ed  mov     rcx, [r14+30h]; this
0x1800967f1  call    ?WaitForInitAndCheckShutdown@CDeliveryOptimizationManager@@QEBAJXZ; CDeliveryOptimizationManager::WaitForInitAndCheckShutdown(void)
0x1800967f6  mov     edi, eax
0x1800967f8  test    eax, eax
0x1800967fa  js      loc_180096882
0x180096800  call    ?Instance@CGlobalObjects@@SAAEAV1@XZ; CGlobalObjects::Instance(void)
0x180096805  mov     rdi, [rax+10h]
0x180096809  xor     edx, edx; void *
0x18009680b  mov     rcx, rdi; this
0x18009680e  call    ?RefreshRemoteProviders@CGlobalConfigManager@@QEAAXPEAX@Z; CGlobalConfigManager::RefreshRemoteProviders(void *)
0x180096813  xor     r8d, r8d
0x180096816  xor     edx, edx
0x180096818  mov     rcx, rdi
0x18009681b  call    ?GetDownloadMode@CGlobalConfigManager@@QEAA?AW4_DownloadMode@@PEA_NPEAW4_ConfigProviderType@@@Z; CGlobalConfigManager::GetDownloadMode(bool *,_ConfigProviderType *)
0x180096820  cmp     eax, 64h ; 'd'
0x180096823  jz      short loc_18009687D
0x180096825  mov     rdx, r15; char *
0x180096828  mov     rcx, rdi; this
0x18009682b  call    ?BranchCacheBypass@CGlobalConfigManager@@QEBA_NPEBD@Z; CGlobalConfigManager::BranchCacheBypass(char const *)
0x180096830  test    al, al
0x180096832  jnz     short loc_18009687D
0x180096834  xorps   xmm0, xmm0
0x180096837  movups  xmmword ptr [rsp+0C8h+pguid.Data1], xmm0
0x18009683c  lea     rcx, [rsp+0C8h+pguid]; pguid
0x180096841  call    cs:__imp_CoCreateGuid
0x180096847  mov     edi, eax
0x180096849  test    eax, eax
0x18009684b  js      short loc_180096882
0x18009684d  mov     rax, [rsp+0C8h+var_88]
0x180096852  mov     [rsp+0C8h+var_A8], rax; __int64
0x180096857  mov     r9b, r13b
0x18009685a  lea     r8, [rsp+0C8h+pguid]
0x18009685f  mov     rdx, r15
0x180096862  mov     rcx, r14; struct CDownloadManager *
0x180096865  call    ?_InternalCreateJob@CDownloadManager@@AEAAJPEBDAEBU_GUID@@_NPEAV?$shared_ptr@VCBackgroundCopyJob@@@std@@@Z; CDownloadManager::_InternalCreateJob(char const *,_GUID const &,bool,std::shared_ptr<CBackgroundCopyJob> *)
0x18009686a  mov     edi, eax
0x18009686c  test    eax, eax
0x18009686e  js      short loc_180096882
0x180096870  movups  xmm0, xmmword ptr [rsp+0C8h+pguid.Data1]
0x180096875  movdqu  xmmword ptr [r12], xmm0
0x18009687b  jmp     short loc_180096882
0x18009687d  mov     edi, 80D03002h
0x180096882  mov     rdx, r12; struct _GUID *
0x180096885  lea     rcx, [rsp+0C8h+var_68]; this
0x18009688a  call    ??0CGuidToString@@QEAA@AEBU_GUID@@@Z; CGuidToString::CGuidToString(_GUID const &)
0x18009688f  mov     [rsp+0C8h+var_98], edi
0x180096893  lea     rax, [rsp+0C8h+var_68]
0x180096898  mov     [rsp+0C8h+var_A0], rax
0x18009689d  mov     [rsp+0C8h+var_A8], r15
0x1800968a2  lea     r9, aCreateJobNameS; "Create job name = %s, jobId = %s, hr = "...
0x1800968a9  mov     r8d, 0B7h; unsigned int
0x1800968af  lea     rdx, aCdownloadmanag; "CDownloadManager::CreateJob"
0x1800968b6  mov     ecx, 4; unsigned __int8
0x1800968bb  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x1800968c0  nop
0x1800968c1  mov     rcx, rbx; SRWLock
0x1800968c4  call    cs:__imp_AcquireSRWLockExclusive
0x1800968ca  add     dword ptr [rbx+0Ch], 0FFFFFFFFh
0x1800968ce  jnz     short loc_1800968E0
0x1800968d0  lea     rcx, [rbx+8]; Address
0x1800968d4  mov     dword ptr [rcx], 1
0x1800968da  call    cs:__imp_WakeByAddressAll
0x1800968e0  mov     rcx, rbx; SRWLock
0x1800968e3  call    cs:__imp_ReleaseSRWLockExclusive
0x1800968e9  mov     eax, edi
0x1800968eb  jmp     short loc_1800968F8
0x1800968ed  mov     eax, dword ptr [rsp+0C8h+var_88]
0x1800968f1  jmp     short loc_1800968F8
0x1800968f3  mov     eax, 8007000Eh
0x1800968f8  mov     rcx, [rsp+0C8h+var_40]
0x180096900  xor     rcx, rsp; StackCookie
0x180096903  call    __security_check_cookie
0x180096908  add     rsp, 90h
0x18009690f  pop     r15
0x180096911  pop     r14
0x180096913  pop     r13
0x180096915  pop     r12
0x180096917  pop     rdi
0x180096918  pop     rsi
0x180096919  pop     rbx
0x18009691a  retn
```
