# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180012030`
- end: `0x1800120b5`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `133`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180012308`

## callees

- `0x1800086fc`
- `0x18000c8c8`
- `0x18000cad8`
- `0x180010a6c`
- `0x180012030`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012057`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012057`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *this,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  int Ptr; // eax
  _DWORD v8[2]; // [rsp+20h] [rbp-38h] BYREF
  struct wil_details_FeatureReportingCache *v9; // [rsp+28h] [rbp-30h]
  RTL_SRWLOCK *v10; // [rsp+60h] [rbp+8h] BYREF

  if ( LODWORD(this->Ptr) && !wil::ProcessShutdownInProgress((wil *)this) )
  {
    AcquireSRWLockExclusive(this + 1);
    Ptr = (int)this->Ptr;
    v10 = this + 1;
    if ( Ptr )
    {
      if ( !wil::ProcessShutdownInProgress(v6) )
      {
        v8[0] = a2;
        v8[1] = 0;
        v9 = a3;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&this[4], v8, 0x10u);
        wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>(&this[2].Ptr, &this[3], this);
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  }
}

```

## disassembly

```asm
0x180012030  push    rbx
0x180012032  push    rbp
0x180012033  push    rsi
0x180012034  push    rdi
0x180012035  sub     rsp, 38h
0x180012039  mov     eax, [rcx]
0x18001203b  mov     rsi, r8
0x18001203e  mov     ebp, edx
0x180012040  mov     rdi, rcx
0x180012043  test    eax, eax
0x180012045  jz      short loc_1800120AC
0x180012047  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18001204c  test    al, al
0x18001204e  jnz     short loc_1800120AC
0x180012050  lea     rbx, [rdi+8]
0x180012054  mov     rcx, rbx; SRWLock
0x180012057  call    cs:__imp_AcquireSRWLockExclusive
0x18001205d  mov     eax, [rdi]
0x18001205f  mov     [rsp+58h+arg_0], rbx
0x180012064  test    eax, eax
0x180012066  jz      short loc_1800120A2
0x180012068  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18001206d  test    al, al
0x18001206f  jnz     short loc_1800120A2
0x180012071  xor     eax, eax
0x180012073  mov     [rsp+58h+var_38], ebp
0x180012077  lea     rcx, [rdi+20h]; this
0x18001207b  mov     [rsp+58h+var_34], eax
0x18001207f  lea     rdx, [rsp+58h+var_38]; void *
0x180012084  mov     [rsp+58h+var_30], rsi
0x180012089  lea     r8d, [rax+10h]; unsigned __int64
0x18001208d  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180012092  lea     rdx, [rdi+18h]
0x180012096  mov     r8, rdi
0x180012099  lea     rcx, [rdi+10h]
0x18001209d  call    ??$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVEnabledStateManager@01@@Z; wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::EnabledStateManager *)
0x1800120a2  lea     rcx, [rsp+58h+arg_0]
0x1800120a7  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800120ac  add     rsp, 38h
0x1800120b0  pop     rdi
0x1800120b1  pop     rsi
0x1800120b2  pop     rbp
0x1800120b3  pop     rbx
0x1800120b4  retn
```
