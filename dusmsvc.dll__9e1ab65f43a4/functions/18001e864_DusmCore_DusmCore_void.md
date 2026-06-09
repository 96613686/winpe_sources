# DusmCore::~DusmCore(void)

- ea: `0x18001e864`
- end: `0x18001e8c3`
- name: `??1DusmCore@@AEAA@XZ`
- size: `95`
- prototype: `void __fastcall(DusmCore *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180020720`

## callees

- `0x18000dc74`
- `0x18001e1e0`
- `0x18001e7f8`
- `0x18001e864`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001e8bc`

## pseudocode

```c
void __fastcall DusmCore::~DusmCore(struct _RTL_CRITICAL_SECTION *this)
{
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx

  wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(&this[1].LockSemaphore);
  DebugInfo = this[1].DebugInfo;
  if ( DebugInfo )
  {
    std::_Destroy_range<std::allocator<std::shared_ptr<DusmConnection>>>(DebugInfo, *(_QWORD *)&this[1].LockCount);
    std::_Deallocate<16>(
      this[1].DebugInfo,
      ((PRTL_CRITICAL_SECTION_DEBUG)this[1].OwningThread - this[1].DebugInfo) & 0xFFFFFFFFFFFFFFF0uLL);
    this[1].DebugInfo = 0;
    *(_QWORD *)&this[1].LockCount = 0;
    this[1].OwningThread = 0;
  }
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x18001e864  push    rbx
0x18001e866  sub     rsp, 20h
0x18001e86a  mov     rbx, rcx
0x18001e86d  add     rcx, 40h ; '@'
0x18001e871  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x18001e876  mov     rcx, [rbx+28h]
0x18001e87a  test    rcx, rcx
0x18001e87d  jz      short loc_18001E8B4
0x18001e87f  mov     rdx, [rbx+30h]
0x18001e883  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VDusmConnection@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VDusmConnection@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VDusmConnection@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<DusmConnection>>>(std::shared_ptr<DusmConnection> *,std::shared_ptr<DusmConnection> * const,std::allocator<std::shared_ptr<DusmConnection>> &)
0x18001e888  mov     rcx, [rbx+28h]
0x18001e88c  mov     rdx, [rbx+38h]
0x18001e890  sub     rdx, rcx
0x18001e893  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18001e897  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001e89c  mov     qword ptr [rbx+28h], 0
0x18001e8a4  mov     qword ptr [rbx+30h], 0
0x18001e8ac  mov     qword ptr [rbx+38h], 0
0x18001e8b4  mov     rcx, rbx
0x18001e8b7  add     rsp, 20h
0x18001e8bb  pop     rbx
0x18001e8bc  jmp     cs:__imp_DeleteCriticalSection
```
