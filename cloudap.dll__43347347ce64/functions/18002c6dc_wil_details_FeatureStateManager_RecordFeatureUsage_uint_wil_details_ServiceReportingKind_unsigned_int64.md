# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18002c6dc`
- end: `0x18002c82a`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task`

## callers

- `0x180036840`

## callees

- `0x18002c6dc`
- `0x18002c830`
- `0x18002cb90`
- `0x18002cbc8`
- `0x18002cc0c`
- `0x18003b8bc`
- `0x18003b944`
- `0x18003b964`
- `0x18003bb00`
- `0x1800456e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c78c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c816`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c78c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c816`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002c73e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002c7b4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002c73e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002c7b4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002c7e1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002c7e1`

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
  wil *v10; // rcx
  char v11; // bl
  PTP_TIMER ThreadpoolTimer; // rax
  char v13; // [rsp+60h] [rbp+8h] BYREF

  if ( !*(_BYTE *)a1 || !wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1) )
    return;
  v8 = *(_QWORD *)(a1 + 24);
  if ( a3 == 254 )
  {
    wil::details_abi::FeatureStateData::RecordUsage(*(PSRWLOCK *)(a1 + 24));
LABEL_17:
    if ( !wil::ProcessShutdownInProgress(v10) )
    {
      AcquireSRWLockExclusive((PSRWLOCK)(a1 + 32));
      if ( !*(_BYTE *)(a1 + 65) )
      {
        if ( !*(_QWORD *)(a1 + 48) )
        {
          wil::last_error_context::last_error_context((wil::last_error_context *)&v13);
          ThreadpoolTimer = CreateThreadpoolTimer(
                              _lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_,
                              (PVOID)a1,
                              0);
          wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
            a1 + 48,
            ThreadpoolTimer);
          wil::last_error_context::~last_error_context((wil::last_error_context *)&v13);
        }
        wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)(a1 + 48), (_BYTE *)(a1 + 65), 300000);
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
      wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,0>::RecordUsage(v8 + 8, a3, a2);
      v11 = *(_BYTE *)(v8 + 64);
    }
    else
    {
      v11 = wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,2>::RecordUsage(
              v8 + 72,
              a3,
              a2,
              a4);
    }
    if ( v8 )
      ReleaseSRWLockExclusive((PSRWLOCK)v8);
    if ( v11 )
      goto LABEL_17;
  }
}

```

## disassembly

```asm
0x18002c6dc  push    rbx
0x18002c6de  push    rbp
0x18002c6df  push    rsi
0x18002c6e0  push    rdi
0x18002c6e1  push    r14
0x18002c6e3  push    r15
0x18002c6e5  sub     rsp, 28h
0x18002c6e9  mov     r15, r9
0x18002c6ec  mov     ebx, r8d
0x18002c6ef  mov     r14d, edx
0x18002c6f2  mov     rdi, rcx
0x18002c6f5  cmp     byte ptr [rcx], 0
0x18002c6f8  jz      loc_18002C81D
0x18002c6fe  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18002c703  test    al, al
0x18002c705  jz      loc_18002C81D
0x18002c70b  mov     rsi, [rdi+18h]
0x18002c70f  cmp     ebx, 0FEh
0x18002c715  jz      loc_18002C79C
0x18002c71b  cmp     ebx, 0C8h
0x18002c721  jb      short loc_18002C73B
0x18002c723  cmp     ebx, 100h
0x18002c729  jl      loc_18002C81D
0x18002c72f  cmp     ebx, 200h
0x18002c735  jnb     loc_18002C81D
0x18002c73b  mov     rcx, rsi; SRWLock
0x18002c73e  call    cs:__imp_AcquireSRWLockExclusive
0x18002c744  cmp     ebx, 7
0x18002c747  ja      short loc_18002C753
0x18002c749  mov     eax, 0CCh
0x18002c74e  bt      eax, ebx
0x18002c751  jb      short loc_18002C773
0x18002c753  lea     eax, [rbx-100h]
0x18002c759  cmp     eax, 7Fh
0x18002c75c  jbe     short loc_18002C773
0x18002c75e  mov     r9d, r15d
0x18002c761  lea     rcx, [rsi+48h]
0x18002c765  mov     r8d, r14d
0x18002c768  mov     edx, ebx
0x18002c76a  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18002c76f  mov     bl, al
0x18002c771  jmp     short loc_18002C784
0x18002c773  mov     r8d, r14d
0x18002c776  mov     edx, ebx
0x18002c778  lea     rcx, [rsi+8]
0x18002c77c  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18002c781  mov     bl, [rsi+40h]
0x18002c784  test    rsi, rsi
0x18002c787  jz      short loc_18002C792
0x18002c789  mov     rcx, rsi; SRWLock
0x18002c78c  call    cs:__imp_ReleaseSRWLockExclusive
0x18002c792  test    bl, bl
0x18002c794  jz      loc_18002C81D
0x18002c79a  jmp     short loc_18002C7A4
0x18002c79c  mov     rcx, rsi; SRWLock
0x18002c79f  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18002c7a4  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18002c7a9  test    al, al
0x18002c7ab  jnz     short loc_18002C81D
0x18002c7ad  lea     rbx, [rdi+20h]
0x18002c7b1  mov     rcx, rbx; SRWLock
0x18002c7b4  call    cs:__imp_AcquireSRWLockExclusive
0x18002c7ba  cmp     byte ptr [rdi+41h], 0
0x18002c7be  jnz     short loc_18002C80E
0x18002c7c0  lea     rsi, [rdi+30h]
0x18002c7c4  cmp     qword ptr [rsi], 0
0x18002c7c8  jnz     short loc_18002C7FC
0x18002c7ca  lea     rcx, [rsp+58h+arg_0]; this
0x18002c7cf  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002c7d4  xor     r8d, r8d; pcbe
0x18002c7d7  mov     rdx, rdi; pv
0x18002c7da  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18002c7e1  call    cs:__imp_CreateThreadpoolTimer
0x18002c7e7  mov     rdx, rax
0x18002c7ea  mov     rcx, rsi
0x18002c7ed  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18002c7f2  lea     rcx, [rsp+58h+arg_0]; this
0x18002c7f7  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002c7fc  mov     r8d, 493E0h
0x18002c802  lea     rdx, [rdi+41h]
0x18002c806  mov     rcx, rsi
0x18002c809  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18002c80e  test    rbx, rbx
0x18002c811  jz      short loc_18002C81D
0x18002c813  mov     rcx, rbx; SRWLock
0x18002c816  call    cs:__imp_ReleaseSRWLockExclusive
0x18002c81c  nop
0x18002c81d  add     rsp, 28h
0x18002c821  pop     r15
0x18002c823  pop     r14
0x18002c825  pop     rdi
0x18002c826  pop     rsi
0x18002c827  pop     rbp
0x18002c828  pop     rbx
0x18002c829  retn
```
