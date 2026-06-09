# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18006fd84`
- end: `0x18006fe67`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `227`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180063600`

## callees

- `0x18003c298`
- `0x18003d080`
- `0x18003d700`
- `0x18003dbb0`
- `0x180052c04`
- `0x180058c1c`
- `0x18005b0c0`
- `0x18006fd84`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006fdc0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006fdc0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18006fe1c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18006fe1c`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        char *pv,
        int a2,
        __int16 a3,
        int a4)
{
  PTP_TIMER ThreadpoolTimer; // rax
  char *v9; // [rsp+20h] [rbp-38h] BYREF
  int Src; // [rsp+28h] [rbp-30h] BYREF
  __int16 v11; // [rsp+2Ch] [rbp-2Ch]
  __int16 v12; // [rsp+2Eh] [rbp-2Ah]
  int v13; // [rsp+30h] [rbp-28h]
  char v14; // [rsp+60h] [rbp+8h] BYREF

  if ( *pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
    v9 = pv + 40;
    v12 = 0;
    Src = a2;
    v11 = a3;
    v13 = a4;
    wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(pv + 232), &Src, 0xCu);
    if ( !pv[64] )
    {
      if ( !*((_QWORD *)pv + 7) )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v14);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          pv + 56,
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v14);
      }
      wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)pv + 7, pv + 64, 5000);
    }
    CSRWLock::CWriterLock::~CWriterLock((CSRWLock::CWriterLock *)&v9);
  }
}

```

## disassembly

```asm
0x18006fd84  mov     [rsp+arg_8], rbx
0x18006fd89  mov     [rsp+arg_10], rbp
0x18006fd8e  push    rsi
0x18006fd8f  push    rdi
0x18006fd90  push    r14
0x18006fd92  sub     rsp, 40h
0x18006fd96  mov     esi, r9d
0x18006fd99  movzx   ebp, r8w
0x18006fd9d  mov     r14d, edx
0x18006fda0  mov     rdi, rcx
0x18006fda3  cmp     byte ptr [rcx], 0
0x18006fda6  jz      loc_18006FE54
0x18006fdac  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18006fdb1  test    al, al
0x18006fdb3  jnz     loc_18006FE54
0x18006fdb9  lea     rbx, [rdi+28h]
0x18006fdbd  mov     rcx, rbx; SRWLock
0x18006fdc0  call    cs:__imp_AcquireSRWLockExclusive
0x18006fdc6  mov     [rsp+58h+var_38], rbx
0x18006fdcb  xor     eax, eax
0x18006fdcd  mov     [rsp+58h+var_2A], ax
0x18006fdd2  mov     [rsp+58h+Src], r14d
0x18006fdd7  mov     [rsp+58h+var_2C], bp
0x18006fddc  mov     [rsp+58h+var_28], esi
0x18006fde0  lea     rcx, [rdi+0E8h]; this
0x18006fde7  lea     r8d, [rax+0Ch]; Size
0x18006fdeb  lea     rdx, [rsp+58h+Src]; Src
0x18006fdf0  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18006fdf5  cmp     byte ptr [rdi+40h], 0
0x18006fdf9  jnz     short loc_18006FE49
0x18006fdfb  lea     rbx, [rdi+38h]
0x18006fdff  cmp     qword ptr [rbx], 0
0x18006fe03  jnz     short loc_18006FE37
0x18006fe05  lea     rcx, [rsp+58h+arg_0]; this
0x18006fe0a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18006fe0f  xor     r8d, r8d; pcbe
0x18006fe12  mov     rdx, rdi; pv
0x18006fe15  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18006fe1c  call    cs:__imp_CreateThreadpoolTimer
0x18006fe22  mov     rdx, rax
0x18006fe25  mov     rcx, rbx
0x18006fe28  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18006fe2d  lea     rcx, [rsp+58h+arg_0]; this
0x18006fe32  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18006fe37  mov     r8d, 1388h
0x18006fe3d  lea     rdx, [rdi+40h]
0x18006fe41  mov     rcx, rbx
0x18006fe44  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18006fe49  lea     rcx, [rsp+58h+var_38]; this
0x18006fe4e  call    ??1CWriterLock@CSRWLock@@QEAA@XZ; CSRWLock::CWriterLock::~CWriterLock(void)
0x18006fe53  nop
0x18006fe54  mov     rbx, [rsp+58h+arg_8]
0x18006fe59  mov     rbp, [rsp+58h+arg_10]
0x18006fe5e  add     rsp, 40h
0x18006fe62  pop     r14
0x18006fe64  pop     rdi
0x18006fe65  pop     rsi
0x18006fe66  retn
```
