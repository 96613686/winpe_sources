# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180005750`
- end: `0x18000592c`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `476`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180012910`

## callees

- `0x180004900`
- `0x180004980`
- `0x180005750`
- `0x180005940`
- `0x180006cf0`
- `0x18000aae0`
- `0x180031230`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800057a7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005809`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800058cd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800057a7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005809`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800058cd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800057d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000581d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005845`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800057d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000581d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005845`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000585f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800058a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000585f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800058a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000584d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005888`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000584d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005888`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180005874`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180005874`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        _BYTE *a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4)
{
  __int64 v8; // rsi
  int v9; // eax
  char v10; // di
  DWORD v11; // edi
  struct _TP_TIMER *ThreadpoolTimer; // rax
  DWORD LastError; // ebp
  __int64 Shared; // r12

  if ( *a1 )
  {
    if ( !*((_QWORD *)a1 + 3) )
    {
      LastError = GetLastError();
      if ( *((_QWORD *)a1 + 3) )
        Shared = 0;
      else
        Shared = wil::details_abi::ProcessLocalStorage<wil::details_abi::FeatureStateData>::GetShared((__int64)(a1 + 8));
      AcquireSRWLockExclusive((PSRWLOCK)a1 + 4);
      if ( !*((_QWORD *)a1 + 3) )
        *((_QWORD *)a1 + 3) = Shared;
      if ( a1 != (_BYTE *)-32LL )
        ReleaseSRWLockExclusive((PSRWLOCK)a1 + 4);
      SetLastError(LastError);
    }
    v8 = *((_QWORD *)a1 + 3);
    if ( v8 )
    {
      if ( a3 == 254 )
      {
        wil::details_abi::FeatureStateData::RecordUsage(*((PSRWLOCK *)a1 + 3));
      }
      else
      {
        if ( a3 >= 0xC8 && ((int)a3 < 256 || a3 >= 0x200) )
          return;
        if ( (AcquireSRWLockExclusive(*((PSRWLOCK *)a1 + 3)), a3 <= 7) && (v9 = 204, _bittest(&v9, a3))
          || a3 - 256 <= 0x7F )
        {
          wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,0>::RecordUsage((wil::details_abi::RawUsageIndex *)(v8 + 8));
          v10 = *(_BYTE *)(v8 + 64);
        }
        else
        {
          v10 = wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,2>::RecordUsage(
                  v8 + 72,
                  a3,
                  a2,
                  a4);
        }
        ReleaseSRWLockExclusive((PSRWLOCK)v8);
        if ( !v10 )
          return;
      }
      if ( !wil::details::g_processShutdownInProgress
        && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
      {
        AcquireSRWLockExclusive((PSRWLOCK)a1 + 4);
        if ( !a1[65] )
        {
          if ( !*((_QWORD *)a1 + 6) )
          {
            v11 = GetLastError();
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_,
                                a1,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              (struct _TP_TIMER **)a1 + 6,
              ThreadpoolTimer);
            SetLastError(v11);
          }
          wil::details::EnsureCoalescedTimer_SetTimer(a1 + 48, a1 + 65, 300000);
        }
        if ( a1 != (_BYTE *)-32LL )
          ReleaseSRWLockExclusive((PSRWLOCK)a1 + 4);
      }
    }
  }
}

```

## disassembly

```asm
0x180005750  push    rbx
0x180005752  push    rbp
0x180005753  push    rsi
0x180005754  push    rdi
0x180005755  push    r12
0x180005757  push    r14
0x180005759  push    r15
0x18000575b  sub     rsp, 20h
0x18000575f  mov     r15, r9
0x180005762  mov     edi, r8d
0x180005765  mov     r14d, edx
0x180005768  mov     rbx, rcx
0x18000576b  cmp     byte ptr [rcx], 0
0x18000576e  jz      loc_180005824
0x180005774  cmp     qword ptr [rcx+18h], 0
0x180005779  jz      loc_1800058A6
0x18000577f  mov     rsi, [rbx+18h]
0x180005783  test    rsi, rsi
0x180005786  jz      loc_180005824
0x18000578c  cmp     edi, 0FEh
0x180005792  jz      loc_180005833
0x180005798  cmp     edi, 0C8h
0x18000579e  jnb     loc_1800058E7
0x1800057a4  mov     rcx, rsi; SRWLock
0x1800057a7  call    cs:__imp_AcquireSRWLockExclusive
0x1800057ad  cmp     edi, 7
0x1800057b0  ja      loc_180005904
0x1800057b6  mov     eax, 0CCh
0x1800057bb  bt      eax, edi
0x1800057be  jnb     loc_180005904
0x1800057c4  mov     r8d, r14d
0x1800057c7  mov     edx, edi
0x1800057c9  lea     rcx, [rsi+8]; this
0x1800057cd  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800057d2  movzx   edi, byte ptr [rsi+40h]
0x1800057d6  mov     rcx, rsi; SRWLock
0x1800057d9  call    cs:__imp_ReleaseSRWLockExclusive
0x1800057df  test    dil, dil
0x1800057e2  jz      short loc_180005824
0x1800057e4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800057eb  jnz     short loc_180005824
0x1800057ed  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800057f4  test    rax, rax
0x1800057f7  jz      short loc_180005802
0x1800057f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057fe  test    al, al
0x180005800  jnz     short loc_180005824
0x180005802  lea     rsi, [rbx+20h]
0x180005806  mov     rcx, rsi; SRWLock
0x180005809  call    cs:__imp_AcquireSRWLockExclusive
0x18000580f  cmp     byte ptr [rbx+41h], 0
0x180005813  jz      short loc_180005858
0x180005815  test    rsi, rsi
0x180005818  jz      short loc_180005824
0x18000581a  mov     rcx, rsi; SRWLock
0x18000581d  call    cs:__imp_ReleaseSRWLockExclusive
0x180005823  nop
0x180005824  add     rsp, 20h
0x180005828  pop     r15
0x18000582a  pop     r14
0x18000582c  pop     r12
0x18000582e  pop     rdi
0x18000582f  pop     rsi
0x180005830  pop     rbp
0x180005831  pop     rbx
0x180005832  retn
0x180005833  mov     rcx, rsi; SRWLock
0x180005836  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000583b  jmp     short loc_1800057E4
0x18000583d  test    rsi, rsi
0x180005840  jz      short loc_18000584B
0x180005842  mov     rcx, rsi; SRWLock
0x180005845  call    cs:__imp_ReleaseSRWLockExclusive
0x18000584b  mov     ecx, ebp; dwErrCode
0x18000584d  call    cs:__imp_SetLastError
0x180005853  jmp     loc_18000577F
0x180005858  cmp     qword ptr [rbx+30h], 0
0x18000585d  jnz     short loc_18000588E
0x18000585f  call    cs:__imp_GetLastError
0x180005865  mov     edi, eax
0x180005867  xor     r8d, r8d; pcbe
0x18000586a  mov     rdx, rbx; pv
0x18000586d  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180005874  call    cs:__imp_CreateThreadpoolTimer
0x18000587a  mov     rdx, rax
0x18000587d  lea     rcx, [rbx+30h]
0x180005881  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180005886  mov     ecx, edi; dwErrCode
0x180005888  call    cs:__imp_SetLastError
0x18000588e  mov     r8d, 493E0h
0x180005894  lea     rdx, [rbx+41h]
0x180005898  lea     rcx, [rbx+30h]
0x18000589c  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x1800058a1  jmp     loc_180005815
0x1800058a6  call    cs:__imp_GetLastError
0x1800058ac  mov     ebp, eax
0x1800058ae  cmp     qword ptr [rbx+18h], 0
0x1800058b3  jz      short loc_1800058BA
0x1800058b5  xor     r12d, r12d
0x1800058b8  jmp     short loc_1800058C6
0x1800058ba  lea     rcx, [rbx+8]
0x1800058be  call    ?GetShared@?$ProcessLocalStorage@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAPEAVFeatureStateData@23@XZ; wil::details_abi::ProcessLocalStorage<wil::details_abi::FeatureStateData>::GetShared(void)
0x1800058c3  mov     r12, rax
0x1800058c6  lea     rsi, [rbx+20h]
0x1800058ca  mov     rcx, rsi; SRWLock
0x1800058cd  call    cs:__imp_AcquireSRWLockExclusive
0x1800058d3  cmp     qword ptr [rbx+18h], 0
0x1800058d8  jnz     loc_18000583D
0x1800058de  mov     [rbx+18h], r12
0x1800058e2  jmp     loc_18000583D
0x1800058e7  cmp     edi, 100h
0x1800058ed  jl      loc_180005824
0x1800058f3  cmp     edi, 200h
0x1800058f9  jnb     loc_180005824
0x1800058ff  jmp     loc_1800057A4
0x180005904  lea     eax, [rdi-100h]
0x18000590a  cmp     eax, 7Fh
0x18000590d  jbe     loc_1800057C4
0x180005913  mov     r9d, r15d
0x180005916  lea     rcx, [rsi+48h]
0x18000591a  mov     r8d, r14d
0x18000591d  mov     edx, edi
0x18000591f  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180005924  movzx   edi, al
0x180005927  jmp     loc_1800057D6
```
