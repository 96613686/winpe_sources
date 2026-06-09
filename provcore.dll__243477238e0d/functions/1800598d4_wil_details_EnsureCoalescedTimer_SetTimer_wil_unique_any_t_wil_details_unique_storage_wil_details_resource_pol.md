# wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)

- ea: `0x1800598d4`
- end: `0x18005992b`
- name: `?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z`
- size: `87`
- prototype: `void __fastcall(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (__cdecl*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy,wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t> > > *timer, bool *timerSet, __int64 delay)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18005bfd0`
- `0x18005c0ac`
- `0x18005c4bc`

## callees

- `0x180002790`
- `0x1800598d4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005990f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005990f`

## pseudocode

```c
void __fastcall wil::details::EnsureCoalescedTimer_SetTimer(
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (__cdecl*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy,wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t> > > *timer,
        bool *timerSet,
        __int64 delay)
{
  struct _TP_TIMER *m_ptr; // rcx
  _FILETIME dueTime; // [rsp+20h] [rbp-18h] BYREF

  m_ptr = timer->m_ptr;
  if ( m_ptr )
  {
    dueTime = (_FILETIME)(-10000 * delay);
    SetThreadpoolTimer(m_ptr, &dueTime, 0, (unsigned int)delay >> 2);
    *timerSet = 1;
  }
}

```

## disassembly

```asm
0x1800598d4  push    rbx
0x1800598d6  sub     rsp, 30h
0x1800598da  mov     rax, cs:__security_cookie
0x1800598e1  xor     rax, rsp
0x1800598e4  mov     [rsp+38h+var_10], rax
0x1800598e9  mov     timer, [timer]; pti
0x1800598ec  mov     rbx, timerSet
0x1800598ef  test    timer, timer
0x1800598f2  jz      short loc_180059918
0x1800598f4  imul    rax, delay, 0FFFFFFFFFFFFD8F0h
0x1800598fb  shr     r8d, 2
0x1800598ff  lea     timerSet, [rsp+38h+dueTime]; pftDueTime
0x180059904  mov     r9d, r8d; msWindowLength
0x180059907  mov     qword ptr [rsp+38h+dueTime.dwLowDateTime], rax
0x18005990c  xor     r8d, r8d; msPeriod
0x18005990f  call    cs:__imp_SetThreadpoolTimer
0x180059915  mov     byte ptr [rbx], 1
0x180059918  mov     timer, [rsp+38h+var_10]
0x18005991d  xor     timer, rsp; StackCookie
0x180059920  call    __security_check_cookie
0x180059925  add     rsp, 30h
0x180059929  pop     rbx
0x18005992a  retn
```
