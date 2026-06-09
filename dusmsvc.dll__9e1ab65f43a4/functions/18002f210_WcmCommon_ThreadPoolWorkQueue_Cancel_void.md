# WcmCommon::ThreadPoolWorkQueue::Cancel(void)

- ea: `0x18002f210`
- end: `0x18002f37e`
- name: `?Cancel@ThreadPoolWorkQueue@WcmCommon@@QEAAXXZ`
- size: `366`
- prototype: `void __fastcall(WcmCommon::ThreadPoolWorkQueue *__hidden this)`
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002f024`
- `0x18002f098`
- `0x1800325b4`

## callees

- `0x180007c90`
- `0x180008704`
- `0x18000f094`
- `0x18002f150`
- `0x18002f210`
- `0x18002fffc`
- `0x18003005c`
- `0x1800300bc`
- `0x180030288`
- `0x1800302dc`
- `0x180030330`
- `0x18004b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f241`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f241`

## pseudocode

```c
void __fastcall WcmCommon::ThreadPoolWorkQueue::Cancel(WcmCommon::ThreadPoolWorkQueue *this)
{
  char *v1; // rbx
  bool v3; // zf
  __int64 v4; // rbx
  __int64 v5; // r15
  __int64 v6; // rcx
  __int64 v7; // rbx
  __int64 v8; // r14
  _BYTE *v9; // rax
  char *v10; // [rsp+20h] [rbp-20h] BYREF
  char *v11; // [rsp+28h] [rbp-18h] BYREF
  __int64 v12; // [rsp+30h] [rbp-10h]

  v1 = (char *)this + 8;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v10 = v1;
  v3 = *((_QWORD *)this + 16) == 0;
  *((_BYTE *)this + 272) = 1;
  if ( !v3 )
  {
    v3 = *(_DWORD *)this == 1;
    v12 = 0;
    if ( v3 )
    {
      v4 = *((_QWORD *)this + 27);
      v5 = v4 + *((_QWORD *)this + 28);
      v11 = (char *)this + 192;
      while ( 1 )
      {
        v12 = v4;
        if ( v4 == v5 )
          break;
        v6 = *(_QWORD *)std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>>>::operator*(&v11);
        if ( v6 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
        ++v4;
      }
      std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Tidy((char *)this + 192);
      std::deque<std::function<void (void)>>::_Tidy((char *)this + 152);
    }
    else
    {
      v7 = *((_QWORD *)this + 32);
      v8 = v7 + *((_QWORD *)this + 33);
      v11 = (char *)this + 232;
      while ( 1 )
      {
        v12 = v7;
        if ( v7 == v8 )
          break;
        v9 = (_BYTE *)std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>>>::operator*(&v11);
        if ( v9 && v9[64] == 1 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v9 + 16LL))(*(_QWORD *)v9);
        ++v7;
      }
      std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::_Tidy((char *)this + 232);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::reset(
      &v10,
      0);
    wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(
      (char *)this + 128,
      0);
    wil::details::unique_storage<wil::details::resource_policy<_TP_POOL *,void (*)(_TP_POOL *),&void CloseThreadpool(_TP_POOL *),wistd::integral_constant<unsigned __int64,0>,_TP_POOL *,_TP_POOL *,0,std::nullptr_t>>::reset(
      (struct _TP_POOL **)this + 15,
      0);
    memset_0((char *)this + 48, 0, 0x48u);
    _InterlockedExchange64((volatile __int64 *)this + 17, 0);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v10);
}

```

## disassembly

```asm
0x18002f210  mov     [rsp-28h+arg_8], rbx
0x18002f215  mov     [rsp-28h+arg_10], rsi
0x18002f21a  push    rbp
0x18002f21b  push    rdi
0x18002f21c  push    r12
0x18002f21e  push    r14
0x18002f220  push    r15
0x18002f222  mov     rbp, rsp
0x18002f225  sub     rsp, 40h
0x18002f229  mov     rax, cs:__security_cookie
0x18002f230  xor     rax, rsp
0x18002f233  mov     [rbp+var_8], rax
0x18002f237  lea     rbx, [rcx+8]
0x18002f23b  mov     rdi, rcx
0x18002f23e  mov     rcx, rbx; lpCriticalSection
0x18002f241  call    cs:__imp_EnterCriticalSection
0x18002f247  lea     r12, [rdi+80h]
0x18002f24e  mov     [rbp+var_20], rbx
0x18002f252  cmp     qword ptr [r12], 0
0x18002f257  lea     r14, [rdi+98h]
0x18002f25e  mov     byte ptr [r14+78h], 1
0x18002f263  jz      loc_18002F350
0x18002f269  cmp     dword ptr [rdi], 1
0x18002f26c  mov     [rbp+var_10], 0
0x18002f274  jnz     short loc_18002F2C9
0x18002f276  lea     rsi, [rdi+0C0h]
0x18002f27d  mov     rbx, [rsi+18h]
0x18002f281  mov     r15, [rsi+20h]
0x18002f285  add     r15, rbx
0x18002f288  mov     [rbp+var_18], rsi
0x18002f28c  mov     [rbp+var_10], rbx
0x18002f290  cmp     rbx, r15
0x18002f293  jz      short loc_18002F2B7
0x18002f295  lea     rcx, [rbp+var_18]
0x18002f299  call    ??D?$_Deque_unchecked_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@std@@@std@@@std@@QEBAAEAV?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@XZ; std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>>>::operator*(void)
0x18002f29e  mov     rcx, [rax]
0x18002f2a1  test    rcx, rcx
0x18002f2a4  jz      short loc_18002F2B2
0x18002f2a6  mov     rax, [rcx]
0x18002f2a9  mov     rax, [rax+10h]
0x18002f2ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f2b2  inc     rbx
0x18002f2b5  jmp     short loc_18002F28C
0x18002f2b7  mov     rcx, rsi
0x18002f2ba  call    ?_Tidy@?$deque@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@V?$allocator@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@@2@@std@@AEAAXXZ; std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Tidy(void)
0x18002f2bf  mov     rcx, r14
0x18002f2c2  call    ?_Tidy@?$deque@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@AEAAXXZ; std::deque<std::function<void (void)>>::_Tidy(void)
0x18002f2c7  jmp     short loc_18002F318
0x18002f2c9  lea     rsi, [rdi+0E8h]
0x18002f2d0  mov     rbx, [rsi+18h]
0x18002f2d4  mov     r14, [rsi+20h]
0x18002f2d8  add     r14, rbx
0x18002f2db  mov     [rbp+var_18], rsi
0x18002f2df  mov     [rbp+var_10], rbx
0x18002f2e3  cmp     rbx, r14
0x18002f2e6  jz      short loc_18002F310
0x18002f2e8  lea     rcx, [rbp+var_18]
0x18002f2ec  call    ??D?$_Deque_unchecked_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@std@@@std@@@std@@QEBAAEAV?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@XZ; std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>>>::operator*(void)
0x18002f2f1  test    rax, rax
0x18002f2f4  jz      short loc_18002F30B
0x18002f2f6  cmp     byte ptr [rax+40h], 1
0x18002f2fa  jnz     short loc_18002F30B
0x18002f2fc  mov     rcx, [rax]
0x18002f2ff  mov     rax, [rcx]
0x18002f302  mov     rax, [rax+10h]
0x18002f306  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f30b  inc     rbx
0x18002f30e  jmp     short loc_18002F2DF
0x18002f310  mov     rcx, rsi
0x18002f313  call    ?_Tidy@?$deque@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@V?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@2@@std@@AEAAXXZ; std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::_Tidy(void)
0x18002f318  xor     edx, edx
0x18002f31a  lea     rcx, [rbp+var_20]
0x18002f31e  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::reset(_RTL_CRITICAL_SECTION *)
0x18002f323  xor     edx, edx
0x18002f325  mov     rcx, r12
0x18002f328  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WORK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(_TP_WORK *)
0x18002f32d  lea     rcx, [rdi+78h]
0x18002f331  xor     edx, edx
0x18002f333  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_POOL@@P6AXPEAU1@@Z$1?CloseThreadpool@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_POOL@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_POOL *,void (*)(_TP_POOL *),&CloseThreadpool(_TP_POOL *),wistd::integral_constant<unsigned __int64,0>,_TP_POOL *,_TP_POOL *,0,std::nullptr_t>>::reset(_TP_POOL *)
0x18002f338  xor     edx, edx; Val
0x18002f33a  lea     rcx, [rdi+30h]; void *
0x18002f33e  lea     r8d, [rdx+48h]; Size
0x18002f342  call    memset_0
0x18002f347  xor     eax, eax
0x18002f349  xchg    rax, [rdi+88h]
0x18002f350  lea     rcx, [rbp+var_20]
0x18002f354  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002f359  mov     rcx, [rbp+var_8]
0x18002f35d  xor     rcx, rsp; StackCookie
0x18002f360  call    __security_check_cookie
0x18002f365  lea     r11, [rsp+40h+var_s0]
0x18002f36a  mov     rbx, [r11+38h]
0x18002f36e  mov     rsi, [r11+40h]
0x18002f372  mov     rsp, r11
0x18002f375  pop     r15
0x18002f377  pop     r14
0x18002f379  pop     r12
0x18002f37b  pop     rdi
0x18002f37c  pop     rbp
0x18002f37d  retn
```
