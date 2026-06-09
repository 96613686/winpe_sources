# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x1800170a8`
- end: `0x1800171f6`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task`

## callers

- `0x180031500`

## callees

- `0x18001007c`
- `0x1800170a8`
- `0x1800171fc`
- `0x18001721c`
- `0x180017260`
- `0x180017280`
- `0x1800289a0`
- `0x18002b0f0`
- `0x18002b83c`
- `0x180030a30`
- `0x180030a64`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017158`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017158`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001710a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001717f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001710a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001717f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800171b1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800171b1`

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
  _QWORD v13[9]; // [rsp+20h] [rbp-48h] BYREF
  char v14; // [rsp+70h] [rbp+8h] BYREF

  if ( !*(_BYTE *)a1 || !wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1) )
    return;
  v8 = *(_QWORD *)(a1 + 24);
  if ( a3 == 254 )
  {
    wil::details_abi::FeatureStateData::RecordUsage(*(wil::details_abi::FeatureStateData **)(a1 + 24));
LABEL_17:
    if ( !wil::ProcessShutdownInProgress(v10) )
    {
      AcquireSRWLockExclusive((PSRWLOCK)(a1 + 32));
      v13[0] = a1 + 32;
      if ( !*(_BYTE *)(a1 + 65) )
      {
        if ( !*(_QWORD *)(a1 + 48) )
        {
          wil::last_error_context::last_error_context((wil::last_error_context *)&v14);
          ThreadpoolTimer = CreateThreadpoolTimer(
                              _lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_,
                              (PVOID)a1,
                              0);
          wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
            a1 + 48,
            ThreadpoolTimer);
          wil::last_error_context::~last_error_context((wil::last_error_context *)&v14);
        }
        wil::details::EnsureCoalescedTimer_SetTimer(a1 + 48, a1 + 65, 300000);
      }
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v13);
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
0x1800170a8  push    rbx
0x1800170aa  push    rbp
0x1800170ab  push    rsi
0x1800170ac  push    rdi
0x1800170ad  push    r14
0x1800170af  push    r15
0x1800170b1  sub     rsp, 38h
0x1800170b5  mov     r15, r9
0x1800170b8  mov     ebx, r8d
0x1800170bb  mov     r14d, edx
0x1800170be  mov     rdi, rcx
0x1800170c1  cmp     byte ptr [rcx], 0
0x1800170c4  jz      loc_1800171E9
0x1800170ca  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1800170cf  test    al, al
0x1800170d1  jz      loc_1800171E9
0x1800170d7  mov     rsi, [rdi+18h]
0x1800170db  cmp     ebx, 0FEh
0x1800170e1  jz      loc_180017167
0x1800170e7  cmp     ebx, 0C8h
0x1800170ed  jb      short loc_180017107
0x1800170ef  cmp     ebx, 100h
0x1800170f5  jl      loc_1800171E9
0x1800170fb  cmp     ebx, 200h
0x180017101  jnb     loc_1800171E9
0x180017107  mov     rcx, rsi; SRWLock
0x18001710a  call    cs:__imp_AcquireSRWLockExclusive
0x180017110  cmp     ebx, 7
0x180017113  ja      short loc_18001711F
0x180017115  mov     eax, 0CCh
0x18001711a  bt      eax, ebx
0x18001711d  jb      short loc_18001713F
0x18001711f  lea     eax, [rbx-100h]
0x180017125  cmp     eax, 7Fh
0x180017128  jbe     short loc_18001713F
0x18001712a  mov     r9d, r15d
0x18001712d  lea     rcx, [rsi+48h]
0x180017131  mov     r8d, r14d
0x180017134  mov     edx, ebx
0x180017136  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18001713b  mov     bl, al
0x18001713d  jmp     short loc_180017150
0x18001713f  mov     r8d, r14d
0x180017142  mov     edx, ebx
0x180017144  lea     rcx, [rsi+8]
0x180017148  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18001714d  mov     bl, [rsi+40h]
0x180017150  test    rsi, rsi
0x180017153  jz      short loc_18001715E
0x180017155  mov     rcx, rsi; SRWLock
0x180017158  call    cs:__imp_ReleaseSRWLockExclusive
0x18001715e  test    bl, bl
0x180017160  jnz     short loc_18001716F
0x180017162  jmp     loc_1800171E9
0x180017167  mov     rcx, rsi; this
0x18001716a  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18001716f  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180017174  test    al, al
0x180017176  jnz     short loc_1800171E9
0x180017178  lea     rbx, [rdi+20h]
0x18001717c  mov     rcx, rbx; SRWLock
0x18001717f  call    cs:__imp_AcquireSRWLockExclusive
0x180017185  mov     [rsp+68h+var_48], rbx
0x18001718a  cmp     byte ptr [rdi+41h], 0
0x18001718e  jnz     short loc_1800171DE
0x180017190  lea     rbx, [rdi+30h]
0x180017194  cmp     qword ptr [rbx], 0
0x180017198  jnz     short loc_1800171CC
0x18001719a  lea     rcx, [rsp+68h+arg_0]; this
0x18001719f  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800171a4  xor     r8d, r8d; pcbe
0x1800171a7  mov     rdx, rdi; pv
0x1800171aa  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800171b1  call    cs:__imp_CreateThreadpoolTimer
0x1800171b7  mov     rdx, rax
0x1800171ba  mov     rcx, rbx
0x1800171bd  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800171c2  lea     rcx, [rsp+68h+arg_0]; this
0x1800171c7  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800171cc  mov     r8d, 493E0h
0x1800171d2  lea     rdx, [rdi+41h]
0x1800171d6  mov     rcx, rbx
0x1800171d9  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x1800171de  lea     rcx, [rsp+68h+var_48]
0x1800171e3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800171e8  nop
0x1800171e9  add     rsp, 38h
0x1800171ed  pop     r15
0x1800171ef  pop     r14
0x1800171f1  pop     rdi
0x1800171f2  pop     rsi
0x1800171f3  pop     rbp
0x1800171f4  pop     rbx
0x1800171f5  retn
```
