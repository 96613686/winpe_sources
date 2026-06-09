# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18001977c`
- end: `0x180019878`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `252`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18001b2a0`

## callees

- `0x18000915c`
- `0x18000c938`
- `0x18000f884`
- `0x180013750`
- `0x180016bb8`
- `0x18001977c`
- `0x18001c040`
- `0x18001c170`
- `0x180022830`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800197bf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800197bf`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180019821`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180019821`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        char *pv,
        int a2,
        __int16 a3,
        int a4)
{
  PTP_TIMER ThreadpoolTimer; // rax
  _BYTE v9[8]; // [rsp+20h] [rbp-58h] BYREF
  char *v10; // [rsp+28h] [rbp-50h] BYREF
  int v11; // [rsp+30h] [rbp-48h] BYREF
  __int16 v12; // [rsp+34h] [rbp-44h]
  __int16 v13; // [rsp+36h] [rbp-42h]
  int v14; // [rsp+38h] [rbp-40h]

  if ( *pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
    v10 = pv + 40;
    v13 = 0;
    v11 = a2;
    v12 = a3;
    v14 = a4;
    wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(pv + 232), &v11, 0xCu);
    if ( !pv[64] )
    {
      if ( !*((_QWORD *)pv + 7) )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v9);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          pv + 56,
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v9);
      }
      wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)pv + 7, pv + 64, 5000);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  }
}

```

## disassembly

```asm
0x18001977c  push    rbx
0x18001977e  push    rbp
0x18001977f  push    rsi
0x180019780  push    rdi
0x180019781  push    r14
0x180019783  sub     rsp, 50h
0x180019787  mov     rax, cs:__security_cookie
0x18001978e  xor     rax, rsp
0x180019791  mov     [rsp+78h+var_38], rax
0x180019796  mov     r14d, r9d
0x180019799  movzx   ebp, r8w
0x18001979d  mov     esi, edx
0x18001979f  mov     rdi, rcx
0x1800197a2  cmp     byte ptr [rcx], 0
0x1800197a5  jz      loc_18001985F
0x1800197ab  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800197b0  test    al, al
0x1800197b2  jnz     loc_18001985F
0x1800197b8  lea     rbx, [rdi+28h]
0x1800197bc  mov     rcx, rbx; SRWLock
0x1800197bf  call    cs:__imp_AcquireSRWLockExclusive
0x1800197c6  nop     dword ptr [rax+rax+00h]
0x1800197cb  mov     [rsp+78h+var_50], rbx
0x1800197d0  xor     eax, eax
0x1800197d2  mov     [rsp+78h+var_42], ax
0x1800197d7  mov     [rsp+78h+var_48], esi
0x1800197db  mov     [rsp+78h+var_44], bp
0x1800197e0  mov     [rsp+78h+var_40], r14d
0x1800197e5  lea     rcx, [rdi+0E8h]; this
0x1800197ec  lea     r8d, [rax+0Ch]; unsigned __int64
0x1800197f0  lea     rdx, [rsp+78h+var_48]; void *
0x1800197f5  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800197fa  cmp     byte ptr [rdi+40h], 0
0x1800197fe  jnz     short loc_180019854
0x180019800  lea     rbx, [rdi+38h]
0x180019804  cmp     qword ptr [rbx], 0
0x180019808  jnz     short loc_180019842
0x18001980a  lea     rcx, [rsp+78h+var_58]; this
0x18001980f  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180019814  xor     r8d, r8d; pcbe
0x180019817  mov     rdx, rdi; pv
0x18001981a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180019821  call    cs:__imp_CreateThreadpoolTimer
0x180019828  nop     dword ptr [rax+rax+00h]
0x18001982d  mov     rdx, rax
0x180019830  mov     rcx, rbx
0x180019833  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180019838  lea     rcx, [rsp+78h+var_58]; this
0x18001983d  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180019842  mov     r8d, 1388h
0x180019848  lea     rdx, [rdi+40h]
0x18001984c  mov     rcx, rbx
0x18001984f  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180019854  lea     rcx, [rsp+78h+var_50]
0x180019859  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001985e  nop
0x18001985f  mov     rcx, [rsp+78h+var_38]
0x180019864  xor     rcx, rsp; StackCookie
0x180019867  call    __security_check_cookie
0x18001986c  add     rsp, 50h
0x180019870  pop     r14
0x180019872  pop     rdi
0x180019873  pop     rsi
0x180019874  pop     rbp
0x180019875  pop     rbx
0x180019876  retn
```
