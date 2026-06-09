# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18003b7d4`
- end: `0x18003b8b6`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `226`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180036840`

## callees

- `0x18002cb90`
- `0x18002cbc8`
- `0x18002cc0c`
- `0x180032fcc`
- `0x18003b7d4`
- `0x18003b944`
- `0x18003b964`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b89c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b89c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003b810`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003b810`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003b867`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003b867`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        char *pv,
        int a2,
        __int16 a3,
        int a4)
{
  PTP_TIMER ThreadpoolTimer; // rax
  int Src; // [rsp+20h] [rbp-28h] BYREF
  __int16 v10; // [rsp+24h] [rbp-24h]
  __int16 v11; // [rsp+26h] [rbp-22h]
  int v12; // [rsp+28h] [rbp-20h]
  char v13; // [rsp+50h] [rbp+8h] BYREF

  if ( *pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
    v11 = 0;
    Src = a2;
    v10 = a3;
    v12 = a4;
    wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(pv + 232), &Src, 0xCu);
    if ( !pv[64] )
    {
      if ( !*((_QWORD *)pv + 7) )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v13);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          pv + 56,
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v13);
      }
      wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)pv + 7, pv + 64, 5000);
    }
    if ( pv != (char *)-40LL )
      ReleaseSRWLockExclusive((PSRWLOCK)pv + 5);
  }
}

```

## disassembly

```asm
0x18003b7d4  mov     [rsp+arg_8], rbx
0x18003b7d9  mov     [rsp+arg_10], rbp
0x18003b7de  push    rsi
0x18003b7df  push    rdi
0x18003b7e0  push    r14
0x18003b7e2  sub     rsp, 30h
0x18003b7e6  mov     edi, r9d
0x18003b7e9  movzx   ebp, r8w
0x18003b7ed  mov     r14d, edx
0x18003b7f0  mov     rbx, rcx
0x18003b7f3  cmp     byte ptr [rcx], 0
0x18003b7f6  jz      loc_18003B8A3
0x18003b7fc  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18003b801  test    al, al
0x18003b803  jnz     loc_18003B8A3
0x18003b809  lea     rsi, [rbx+28h]
0x18003b80d  mov     rcx, rsi; SRWLock
0x18003b810  call    cs:__imp_AcquireSRWLockExclusive
0x18003b816  xor     eax, eax
0x18003b818  mov     [rsp+48h+var_22], ax
0x18003b81d  mov     [rsp+48h+Src], r14d
0x18003b822  mov     [rsp+48h+var_24], bp
0x18003b827  mov     [rsp+48h+var_20], edi
0x18003b82b  lea     rcx, [rbx+0E8h]; this
0x18003b832  lea     r8d, [rax+0Ch]; Size
0x18003b836  lea     rdx, [rsp+48h+Src]; Src
0x18003b83b  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18003b840  cmp     byte ptr [rbx+40h], 0
0x18003b844  jnz     short loc_18003B894
0x18003b846  lea     rdi, [rbx+38h]
0x18003b84a  cmp     qword ptr [rdi], 0
0x18003b84e  jnz     short loc_18003B882
0x18003b850  lea     rcx, [rsp+48h+arg_0]; this
0x18003b855  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18003b85a  xor     r8d, r8d; pcbe
0x18003b85d  mov     rdx, rbx; pv
0x18003b860  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18003b867  call    cs:__imp_CreateThreadpoolTimer
0x18003b86d  mov     rdx, rax
0x18003b870  mov     rcx, rdi
0x18003b873  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18003b878  lea     rcx, [rsp+48h+arg_0]; this
0x18003b87d  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18003b882  mov     r8d, 1388h
0x18003b888  lea     rdx, [rbx+40h]
0x18003b88c  mov     rcx, rdi
0x18003b88f  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18003b894  test    rsi, rsi
0x18003b897  jz      short loc_18003B8A3
0x18003b899  mov     rcx, rsi; SRWLock
0x18003b89c  call    cs:__imp_ReleaseSRWLockExclusive
0x18003b8a2  nop
0x18003b8a3  mov     rbx, [rsp+48h+arg_8]
0x18003b8a8  mov     rbp, [rsp+48h+arg_10]
0x18003b8ad  add     rsp, 30h
0x18003b8b1  pop     r14
0x18003b8b3  pop     rdi
0x18003b8b4  pop     rsi
0x18003b8b5  retn
```
