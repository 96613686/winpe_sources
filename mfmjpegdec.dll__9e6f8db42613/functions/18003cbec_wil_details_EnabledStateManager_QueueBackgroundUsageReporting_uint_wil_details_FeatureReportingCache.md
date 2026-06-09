# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18003cbec`
- end: `0x18003cc6d`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `129`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18003d114`

## callees

- `0x180021460`
- `0x180021810`
- `0x18003af20`
- `0x18003cbec`
- `0x18003dc50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003cc13`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003cc13`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        wil::details::EnabledStateManager *this,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  int v7; // eax
  unsigned __int64 v8; // r8
  _DWORD Source[2]; // [rsp+20h] [rbp-38h] BYREF
  struct wil_details_FeatureReportingCache *v10; // [rsp+28h] [rbp-30h]
  char *v11; // [rsp+60h] [rbp+8h] BYREF

  if ( *(_DWORD *)this && !wil::ProcessShutdownInProgress(this) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)this + 1);
    v7 = *(_DWORD *)this;
    v11 = (char *)this + 8;
    if ( v7 )
    {
      if ( !wil::ProcessShutdownInProgress(v6) )
      {
        Source[0] = a2;
        Source[1] = 0;
        v10 = a3;
        wil::details_abi::heap_buffer::push_back((wil::details::EnabledStateManager *)((char *)this + 32), Source, v8);
        wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>(
          (struct _TP_TIMER **)this + 2,
          (_BYTE *)this + 24,
          this);
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  }
}

```

## disassembly

```asm
0x18003cbec  push    rbx
0x18003cbee  push    rbp
0x18003cbef  push    rsi
0x18003cbf0  push    rdi
0x18003cbf1  sub     rsp, 38h
0x18003cbf5  mov     eax, [rcx]
0x18003cbf7  mov     rsi, r8
0x18003cbfa  mov     ebp, edx
0x18003cbfc  mov     rdi, rcx
0x18003cbff  test    eax, eax
0x18003cc01  jz      short loc_18003CC64
0x18003cc03  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18003cc08  test    al, al
0x18003cc0a  jnz     short loc_18003CC64
0x18003cc0c  lea     rbx, [rdi+8]
0x18003cc10  mov     rcx, rbx; SRWLock
0x18003cc13  call    cs:__imp_AcquireSRWLockExclusive
0x18003cc19  mov     eax, [rdi]
0x18003cc1b  mov     [rsp+58h+arg_0], rbx
0x18003cc20  test    eax, eax
0x18003cc22  jz      short loc_18003CC5A
0x18003cc24  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18003cc29  test    al, al
0x18003cc2b  jnz     short loc_18003CC5A
0x18003cc2d  xor     eax, eax
0x18003cc2f  mov     [rsp+58h+Source], ebp
0x18003cc33  lea     rcx, [rdi+20h]; this
0x18003cc37  mov     [rsp+58h+var_34], eax
0x18003cc3b  lea     rdx, [rsp+58h+Source]; Source
0x18003cc40  mov     [rsp+58h+var_30], rsi
0x18003cc45  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18003cc4a  lea     rdx, [rdi+18h]
0x18003cc4e  mov     r8, rdi
0x18003cc51  lea     rcx, [rdi+10h]
0x18003cc55  call    ??$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVEnabledStateManager@01@@Z; wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::EnabledStateManager *)
0x18003cc5a  lea     rcx, [rsp+58h+arg_0]
0x18003cc5f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18003cc64  add     rsp, 38h
0x18003cc68  pop     rdi
0x18003cc69  pop     rsi
0x18003cc6a  pop     rbp
0x18003cc6b  pop     rbx
0x18003cc6c  retn
```
