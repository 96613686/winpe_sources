# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18004acec`
- end: `0x18004ae5b`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `367`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180080320`

## callees

- `0x18004a66c`
- `0x18004a690`
- `0x18004a6d4`
- `0x18004a6f4`
- `0x18004acec`
- `0x18004ae64`
- `0x18004b600`
- `0x18004b8ec`
- `0x1800a02b0`
- `0x18010a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004ad84`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004adc7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004ad84`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004adc7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004ad4e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004adb3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004ad4e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004adb3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18004ae05`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18004ae05`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4)
{
  __int64 v8; // rsi
  int v9; // eax
  char v10; // bl
  PTP_TIMER ThreadpoolTimer; // rax
  char v12; // [rsp+60h] [rbp+8h] BYREF

  if ( !*(_BYTE *)a1 || !wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1) )
    return;
  v8 = *(_QWORD *)(a1 + 24);
  if ( a3 == 254 )
  {
    wil::details_abi::FeatureStateData::RecordUsage(*(PSRWLOCK *)(a1 + 24));
LABEL_13:
    if ( !wil::details::g_processShutdownInProgress
      && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
    {
      AcquireSRWLockExclusive((PSRWLOCK)(a1 + 32));
      if ( !*(_BYTE *)(a1 + 65) )
      {
        if ( !*(_QWORD *)(a1 + 48) )
        {
          wil::last_error_context::last_error_context((wil::last_error_context *)&v12);
          ThreadpoolTimer = CreateThreadpoolTimer(
                              _lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_,
                              (PVOID)a1,
                              0);
          wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
            a1 + 48,
            ThreadpoolTimer);
          wil::last_error_context::~last_error_context((wil::last_error_context *)&v12);
        }
        wil::details::EnsureCoalescedTimer_SetTimer(a1 + 48, a1 + 65, 300000);
      }
      if ( a1 != -32 )
        ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 32));
    }
    return;
  }
  if ( a3 < 0xC8 || (int)a3 >= 256 && a3 < 0x200 )
  {
    AcquireSRWLockExclusive(*(PSRWLOCK *)(a1 + 24));
    if ( a3 <= 7 && (v9 = 204, _bittest(&v9, a3)) || a3 - 256 <= 0x7F )
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
    if ( v8 )
      ReleaseSRWLockExclusive((PSRWLOCK)v8);
    if ( v10 )
      goto LABEL_13;
  }
}

```

## disassembly

```asm
0x18004acec  push    rbx
0x18004acee  push    rbp
0x18004acef  push    rsi
0x18004acf0  push    rdi
0x18004acf1  push    r14
0x18004acf3  push    r15
0x18004acf5  sub     rsp, 28h
0x18004acf9  cmp     byte ptr [rcx], 0
0x18004acfc  mov     r15, r9
0x18004acff  mov     ebx, r8d
0x18004ad02  mov     r14d, edx
0x18004ad05  mov     rdi, rcx
0x18004ad08  jz      loc_18004ADCD
0x18004ad0e  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18004ad13  test    al, al
0x18004ad15  jz      loc_18004ADCD
0x18004ad1b  mov     rsi, [rdi+18h]
0x18004ad1f  cmp     ebx, 0FEh
0x18004ad25  jz      loc_18004ADDA
0x18004ad2b  cmp     ebx, 0C8h
0x18004ad31  jb      short loc_18004AD4B
0x18004ad33  cmp     ebx, 100h
0x18004ad39  jl      loc_18004ADCD
0x18004ad3f  cmp     ebx, 200h
0x18004ad45  jnb     loc_18004ADCD
0x18004ad4b  mov     rcx, rsi; SRWLock
0x18004ad4e  call    cs:__imp_AcquireSRWLockExclusive
0x18004ad54  cmp     ebx, 7
0x18004ad57  ja      loc_18004AE34
0x18004ad5d  mov     eax, 0CCh
0x18004ad62  bt      eax, ebx
0x18004ad65  jnb     loc_18004AE34
0x18004ad6b  mov     r8d, r14d
0x18004ad6e  lea     rcx, [rsi+8]; this
0x18004ad72  mov     edx, ebx
0x18004ad74  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18004ad79  mov     bl, [rsi+40h]
0x18004ad7c  test    rsi, rsi
0x18004ad7f  jz      short loc_18004AD8A
0x18004ad81  mov     rcx, rsi; SRWLock
0x18004ad84  call    cs:__imp_ReleaseSRWLockExclusive
0x18004ad8a  test    bl, bl
0x18004ad8c  jz      short loc_18004ADCD
0x18004ad8e  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18004ad95  jnz     short loc_18004ADCD
0x18004ad97  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18004ad9e  test    rax, rax
0x18004ada1  jz      short loc_18004ADAC
0x18004ada3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ada8  test    al, al
0x18004adaa  jnz     short loc_18004ADCD
0x18004adac  lea     rbx, [rdi+20h]
0x18004adb0  mov     rcx, rbx; SRWLock
0x18004adb3  call    cs:__imp_AcquireSRWLockExclusive
0x18004adb9  cmp     byte ptr [rdi+41h], 0
0x18004adbd  jz      short loc_18004ADE4
0x18004adbf  test    rbx, rbx
0x18004adc2  jz      short loc_18004ADCD
0x18004adc4  mov     rcx, rbx; SRWLock
0x18004adc7  call    cs:__imp_ReleaseSRWLockExclusive
0x18004adcd  add     rsp, 28h
0x18004add1  pop     r15
0x18004add3  pop     r14
0x18004add5  pop     rdi
0x18004add6  pop     rsi
0x18004add7  pop     rbp
0x18004add8  pop     rbx
0x18004add9  retn
0x18004adda  mov     rcx, rsi; SRWLock
0x18004addd  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18004ade2  jmp     short loc_18004AD8E
0x18004ade4  lea     rsi, [rdi+30h]
0x18004ade8  cmp     qword ptr [rsi], 0
0x18004adec  jnz     short loc_18004AE20
0x18004adee  lea     rcx, [rsp+58h+arg_0]; this
0x18004adf3  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18004adf8  xor     r8d, r8d; pcbe
0x18004adfb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18004ae02  mov     rdx, rdi; pv
0x18004ae05  call    cs:__imp_CreateThreadpoolTimer
0x18004ae0b  mov     rdx, rax
0x18004ae0e  mov     rcx, rsi
0x18004ae11  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18004ae16  lea     rcx, [rsp+58h+arg_0]; this
0x18004ae1b  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18004ae20  mov     r8d, 493E0h
0x18004ae26  lea     rdx, [rdi+41h]
0x18004ae2a  mov     rcx, rsi
0x18004ae2d  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18004ae32  jmp     short loc_18004ADBF
0x18004ae34  lea     eax, [rbx-100h]
0x18004ae3a  cmp     eax, 7Fh
0x18004ae3d  jbe     loc_18004AD6B
0x18004ae43  mov     r9d, r15d
0x18004ae46  lea     rcx, [rsi+48h]
0x18004ae4a  mov     r8d, r14d
0x18004ae4d  mov     edx, ebx
0x18004ae4f  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18004ae54  mov     bl, al
0x18004ae56  jmp     loc_18004AD7C
```
