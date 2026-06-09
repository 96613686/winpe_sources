# DAS::Dispatcher::Watchdog::CheckForStuckThreads(ulong)

- ea: `0x180047e74`
- end: `0x1800480c8`
- name: `?CheckForStuckThreads@Watchdog@Dispatcher@DAS@@QEAAXK@Z`
- size: `596`
- prototype: `void __fastcall(RTL_SRWLOCK *this)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18001958c`
- `0x180048e24`

## callees

- `0x180019adc`
- `0x18001dfe0`
- `0x18003bc80`
- `0x180044c70`
- `0x180045df0`
- `0x180047b04`
- `0x180047e74`
- `0x180048984`
- `0x180049450`
- `0x1800497c0`
- `0x1800499e0`
- `0x180049bbc`
- `0x18004c204`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800480aa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800480aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180047f51`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180047f51`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180047ea1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180047ea1`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180047ebd`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180047f1a`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180047ebd`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180047f1a`
- `faultrep!ReportCoreHang` at `0x18004805b`
- `faultrep!ReportCoreHang` at `0x18004805b`

## string_xrefs

- `0x180048036`: `onecore\base\devices\association\service\lib\dispatcher.cpp`

## pseudocode

```c
void __fastcall DAS::Dispatcher::Watchdog::CheckForStuckThreads(RTL_SRWLOCK *this)
{
  unsigned int v2; // esi
  unsigned int v3; // r8d
  const char *v4; // r9
  __int64 v5; // rax
  unsigned int v6; // r8d
  const char *v7; // r9
  int v8; // ecx
  DWORD CurrentProcessId; // edi
  int v10; // r8d
  int v11; // r9d
  unsigned __int64 v12; // rbx
  int HostPids; // eax
  wil::details::in1diag3 *v14; // rcx
  __int64 v15; // rdx
  int v16; // eax
  unsigned int v17; // r8d
  int v18; // [rsp+20h] [rbp-89h]
  DWORD v19; // [rsp+50h] [rbp-59h] BYREF
  char v20; // [rsp+54h] [rbp-55h] BYREF
  struct _FILETIME FileTime; // [rsp+58h] [rbp-51h] BYREF
  struct _FILETIME v22; // [rsp+60h] [rbp-49h] BYREF
  unsigned __int64 v23; // [rsp+68h] [rbp-41h]
  __int64 v24; // [rsp+70h] [rbp-39h] BYREF
  PSRWLOCK SRWLock; // [rsp+78h] [rbp-31h] BYREF
  _QWORD v26[4]; // [rsp+80h] [rbp-29h] BYREF
  _QWORD v27[2]; // [rsp+A0h] [rbp-9h] BYREF
  SYSTEMTIME v28; // [rsp+B0h] [rbp+7h] BYREF
  int v29; // [rsp+C0h] [rbp+17h]
  struct _SYSTEMTIME SystemTime; // [rsp+C8h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  SystemTime = 0;
  GetSystemTime(&SystemTime);
  FileTime = 0;
  v2 = DAS::Dispatcher::g_watchdogTimeout;
  if ( !SystemTimeToFileTime(&SystemTime, &FileTime) )
  {
    wil::details::in1diag3::Log_GetLastError(retaddr, (void *)0xA8, v3, v4);
    return;
  }
  wil::AcquireSRWLockShared(&SRWLock, this);
  v5 = *(_QWORD *)this[1].Ptr;
  v24 = v5;
  while ( !*(_BYTE *)(v5 + 25) )
  {
    v28 = *(SYSTEMTIME *)(v5 + 28);
    v29 = *(_DWORD *)(v5 + 44);
    v22 = 0;
    if ( !SystemTimeToFileTime((const SYSTEMTIME *)&v28.wDayOfWeek, &v22) )
    {
      wil::details::in1diag3::Log_GetLastError(retaddr, (void *)0xB5, v6, v7);
      break;
    }
    LODWORD(v23) = FileTime.dwLowDateTime - v22.dwLowDateTime;
    HIDWORD(v23) = FileTime.dwHighDateTime - v22.dwHighDateTime;
    if ( v23 > 1000 * (unsigned __int64)(10000 * v2) )
    {
      CurrentProcessId = GetCurrentProcessId();
      v12 = v23 / 0x989680;
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_dddd(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v2 / 0x3E8,
          v10,
          v11,
          v18,
          CurrentProcessId,
          v28.wYear,
          v23 / 0x989680,
          v2 / 0x3E8);
      if ( (Microsoft_Windows_DeviceAssociationServiceEnableBits & 2) != 0 )
        McTemplateU0qqq_EventWriteTransfer(
          v8,
          (unsigned int)WATCHDOG_TIMEOUT,
          CurrentProcessId,
          *(_DWORD *)&v28.wYear,
          v12);
      v19 = CurrentProcessId;
      v27[0] = &v19;
      v27[1] = &v20;
      std::vector<unsigned long>::vector<unsigned long>(v26, v27);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::GetImpl'::`2'::impl) )
      {
        if ( !DAS::Dispatcher::g_dispatcherStopping )
        {
          HostPids = CHostContext::GetHostPids(v26);
          v14 = retaddr;
          if ( HostPids < 0 )
          {
            v15 = 203;
            goto LABEL_17;
          }
        }
      }
      else
      {
        HostPids = CHostContext::GetHostPids(v26);
        v14 = retaddr;
        if ( HostPids < 0 )
        {
          v15 = 208;
LABEL_17:
          wil::details::in1diag3::_Log_Hr(
            v14,
            (void *)v15,
            (int)"onecore\\base\\devices\\association\\service\\lib\\dispatcher.cpp",
            (const char *)(unsigned int)HostPids);
        }
      }
      v16 = ReportCoreHang(v26[0], (__int64)(v26[1] - v26[0]) >> 2, *(unsigned int *)&v28.wYear, 32);
      if ( v16 < 0 )
        wil::details::in1diag3::_Log_NtStatus(retaddr, (void *)0xD3, v17, (const char *)(unsigned int)v16, v18);
      std::vector<unsigned long>::_Tidy(v26);
    }
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<ProviderContext>>>>,std::_Iterator_base0>::operator++(&v24);
    v5 = v24;
  }
  if ( SRWLock )
    ReleaseSRWLockShared(SRWLock);
}

```

## disassembly

```asm
0x180047e74  push    rbp
0x180047e76  push    rbx
0x180047e77  push    rsi
0x180047e78  push    rdi
0x180047e79  lea     rbp, [rsp-3Fh]
0x180047e7e  sub     rsp, 0E8h
0x180047e85  mov     rax, cs:__security_cookie
0x180047e8c  xor     rax, rsp
0x180047e8f  mov     [rbp+57h+var_28], rax
0x180047e93  mov     rbx, rcx
0x180047e96  xorps   xmm0, xmm0
0x180047e99  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x180047e9d  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x180047ea1  call    cs:__imp_GetSystemTime
0x180047ea7  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], 0
0x180047eaf  mov     esi, cs:?g_watchdogTimeout@Dispatcher@DAS@@3KA; ulong DAS::Dispatcher::g_watchdogTimeout
0x180047eb5  lea     rdx, [rbp+57h+FileTime]; lpFileTime
0x180047eb9  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x180047ebd  call    cs:__imp_SystemTimeToFileTime
0x180047ec3  test    eax, eax
0x180047ec5  jnz     short loc_180047EDA
0x180047ec7  mov     rcx, [rbp+5Fh]; this
0x180047ecb  mov     edx, 0A8h; void *
0x180047ed0  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x180047ed5  jmp     loc_1800480B0
0x180047eda  mov     rdx, rbx
0x180047edd  lea     rcx, [rbp+57h+SRWLock]
0x180047ee1  call    ?AcquireSRWLockShared@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockShared(_RTL_SRWLOCK *)
0x180047ee6  nop
0x180047ee7  mov     rax, [rbx+8]
0x180047eeb  mov     rax, [rax]
0x180047eee  mov     [rbp+57h+var_90], rax
0x180047ef2  cmp     byte ptr [rax+19h], 0
0x180047ef6  jnz     loc_1800480A1
0x180047efc  movups  xmm0, xmmword ptr [rax+1Ch]
0x180047f00  movups  xmmword ptr [rbp+57h+var_50.wYear], xmm0
0x180047f04  mov     ecx, [rax+2Ch]
0x180047f07  mov     [rbp+57h+var_40], ecx
0x180047f0a  mov     qword ptr [rbp+57h+var_A0.dwLowDateTime], 0
0x180047f12  lea     rdx, [rbp+57h+var_A0]; lpFileTime
0x180047f16  lea     rcx, [rbp+57h+var_50.wDayOfWeek]; lpSystemTime
0x180047f1a  call    cs:__imp_SystemTimeToFileTime
0x180047f20  test    eax, eax
0x180047f22  jz      loc_180048092
0x180047f28  mov     eax, [rbp+57h+FileTime.dwLowDateTime]
0x180047f2b  sub     eax, [rbp+57h+var_A0.dwLowDateTime]
0x180047f2e  mov     dword ptr [rbp+57h+var_98], eax
0x180047f31  mov     eax, [rbp+57h+FileTime.dwHighDateTime]
0x180047f34  sub     eax, [rbp+57h+var_A0.dwHighDateTime]
0x180047f37  mov     dword ptr [rbp+57h+var_98+4], eax
0x180047f3a  imul    ecx, esi, 2710h
0x180047f40  imul    rax, rcx, 3E8h
0x180047f47  cmp     [rbp+57h+var_98], rax
0x180047f4b  jbe     loc_180048080
0x180047f51  call    cs:__imp_GetCurrentProcessId
0x180047f57  mov     edi, eax
0x180047f59  mov     rax, 0D6BF94D5E57A42BDh
0x180047f63  mul     [rbp+57h+var_98]
0x180047f67  mov     rbx, rdx
0x180047f6a  shr     rbx, 17h
0x180047f6e  lea     rax, WPP_RECORDER_INITIALIZED
0x180047f75  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180047f7c  jz      short loc_180047FAB
0x180047f7e  mov     eax, 10624DD3h
0x180047f83  mul     esi
0x180047f85  shr     edx, 6
0x180047f88  mov     [rsp+100h+var_C0], edx
0x180047f8c  mov     [rsp+100h+var_C8], ebx
0x180047f90  mov     eax, dword ptr [rbp+57h+var_50.wYear]
0x180047f93  mov     [rsp+100h+var_D0], eax
0x180047f97  mov     [rsp+100h+var_D8], edi
0x180047f9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180047fa2  mov     rcx, [rcx+28h]
0x180047fa6  call    WPP_RECORDER_SF_dddd
0x180047fab  test    byte ptr cs:Microsoft_Windows_DeviceAssociationServiceEnableBits, 2
0x180047fb2  jz      short loc_180047FCB
0x180047fb4  mov     [rsp+100h+var_E0], ebx; int
0x180047fb8  mov     r9d, dword ptr [rbp+57h+var_50.wYear]
0x180047fbc  mov     r8d, edi
0x180047fbf  lea     rdx, WATCHDOG_TIMEOUT
0x180047fc6  call    McTemplateU0qqq_EventWriteTransfer
0x180047fcb  mov     [rbp+57h+var_B0], edi
0x180047fce  lea     rax, [rbp+57h+var_B0]
0x180047fd2  mov     [rbp+57h+var_60], rax
0x180047fd6  lea     rax, [rbp+57h+var_AC]
0x180047fda  mov     [rbp+57h+var_58], rax
0x180047fde  lea     rdx, [rbp+57h+var_60]
0x180047fe2  lea     rcx, [rbp+57h+var_80]
0x180047fe6  call    ??0?$vector@KV?$allocator@K@std@@@std@@QEAA@V?$initializer_list@K@1@AEBV?$allocator@K@1@@Z; std::vector<ulong>::vector<ulong>(std::initializer_list<ulong>,std::allocator<ulong> const &)
0x180047feb  nop
0x180047fec  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher> `wil::Feature<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::GetImpl(void)'::`2'::impl
0x180047ff3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::__private_IsEnabled(void)
0x180047ff8  test    al, al
0x180047ffa  jz      short loc_18004801D
0x180047ffc  cmp     cs:?g_dispatcherStopping@Dispatcher@DAS@@3_NA, 0; bool DAS::Dispatcher::g_dispatcherStopping
0x180048003  jnz     short loc_180048042
0x180048005  lea     rcx, [rbp+57h+var_80]
0x180048009  call    ?GetHostPids@CHostContext@@SAJAEAV?$vector@KV?$allocator@K@std@@@std@@@Z; CHostContext::GetHostPids(std::vector<ulong> &)
0x18004800e  mov     rcx, [rbp+5Fh]
0x180048012  test    eax, eax
0x180048014  jns     short loc_180048042
0x180048016  mov     edx, 0CBh
0x18004801b  jmp     short loc_180048033
0x18004801d  lea     rcx, [rbp+57h+var_80]
0x180048021  call    ?GetHostPids@CHostContext@@SAJAEAV?$vector@KV?$allocator@K@std@@@std@@@Z; CHostContext::GetHostPids(std::vector<ulong> &)
0x180048026  mov     rcx, [rbp+5Fh]; this
0x18004802a  test    eax, eax
0x18004802c  jns     short loc_180048042
0x18004802e  mov     edx, 0D0h; void *
0x180048033  mov     r9d, eax; char *
0x180048036  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\association\\se"...
0x18004803d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180048042  mov     rcx, [rbp+57h+var_80]
0x180048046  mov     rdx, [rbp+57h+var_78]
0x18004804a  sub     rdx, rcx
0x18004804d  sar     rdx, 2
0x180048051  mov     r9d, 20h ; ' '
0x180048057  mov     r8d, dword ptr [rbp+57h+var_50.wYear]
0x18004805b  call    cs:__imp_ReportCoreHang
0x180048061  mov     rcx, [rbp+5Fh]; this
0x180048065  test    eax, eax
0x180048067  jns     short loc_180048077
0x180048069  mov     r9d, eax; char *
0x18004806c  mov     edx, 0D3h; void *
0x180048071  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x180048076  nop
0x180048077  lea     rcx, [rbp+57h+var_80]
0x18004807b  call    ?_Tidy@?$vector@KV?$allocator@K@std@@@std@@AEAAXXZ; std::vector<ulong>::_Tidy(void)
0x180048080  lea     rcx, [rbp+57h+var_90]
0x180048084  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VProviderContext@@@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<ProviderContext>>>>,std::_Iterator_base0>::operator++(void)
0x180048089  mov     rax, [rbp+57h+var_90]
0x18004808d  jmp     loc_180047EF2
0x180048092  mov     rcx, [rbp+5Fh]; this
0x180048096  mov     edx, 0B5h; void *
0x18004809b  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x1800480a0  nop
0x1800480a1  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800480a5  test    rcx, rcx
0x1800480a8  jz      short loc_1800480B0
0x1800480aa  call    cs:__imp_ReleaseSRWLockShared
0x1800480b0  mov     rcx, [rbp+57h+var_28]
0x1800480b4  xor     rcx, rsp; StackCookie
0x1800480b7  call    __security_check_cookie
0x1800480bc  add     rsp, 0E8h
0x1800480c3  pop     rdi
0x1800480c4  pop     rsi
0x1800480c5  pop     rbx
0x1800480c6  pop     rbp
0x1800480c7  retn
```
