# TenantRestrictions::TenantRestrictions(void)

- ea: `0x180009e80`
- end: `0x180009fea`
- name: `??0TenantRestrictions@@QEAA@XZ`
- size: `362`
- prototype: `TenantRestrictions *__fastcall(TenantRestrictions *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000b080`

## callees

- `0x180001a50`
- `0x1800026d0`
- `0x180008d64`
- `0x180009ab4`
- `0x180009dec`
- `0x180009e50`
- `0x180009e80`
- `0x18000a748`
- `0x18000a8c4`
- `0x18000b1d0`
- `0x18000c400`
- `0x18000c874`
- `0x18000cb1c`

## import_xrefs

- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x180009f02`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x180009f02`

## string_xrefs

- `0x180009f15`: `onecoreuap\ds\ext\common\ntservice\lib\tenantrestrictions.cpp`

## pseudocode

```c
TenantRestrictions *__fastcall TenantRestrictions::TenantRestrictions(TenantRestrictions *this)
{
  __int64 v2; // rcx
  TenantRestrictions **v3; // rdi
  HANDLE TimerQueue; // rax
  const char *v5; // r9
  unsigned __int64 v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // r8
  TenantRestrictions *v11; // [rsp+20h] [rbp-69h] BYREF
  TenantRestrictions *v12; // [rsp+28h] [rbp-61h] BYREF
  __int64 v13; // [rsp+30h] [rbp-59h] BYREF
  char v14[8]; // [rsp+38h] [rbp-51h] BYREF
  _QWORD v15[14]; // [rsp+40h] [rbp-49h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v12 = this;
  std::wstring::wstring(this);
  std::unordered_map<std::wstring,std::wstring>::unordered_map<std::wstring,std::wstring>(v2 + 32);
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_BYTE *)this + 128) = 0;
  *((_BYTE *)this + 144) = 0;
  *((_BYTE *)this + 160) = 0;
  v3 = (TenantRestrictions **)((char *)this + 168);
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 22) = 0;
  std::wstring::wstring((char *)this + 184);
  TimerQueue = CreateTimerQueue();
  *((_QWORD *)this + 14) = TimerQueue;
  if ( !TimerQueue )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x67,
      (unsigned int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\tenantrestrictions.cpp",
      v5);
  *((_DWORD *)this + 24) = 1000;
  v6 = std::_WChar_traits<unsigned short>::length(L"(no successful sync)");
  std::wstring::_Assign<unsigned short>((__int64)this + 184, v7, v6);
  TenantRestrictions::OnPolicyChange((RTL_SRWLOCK *)this, 1);
  v8 = *wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
          &v13,
          (__int64)this);
  v15[0] = off_1800133A0;
  v15[1] = v8;
  v15[13] = v15;
  v12 = 0;
  if ( (int)wil::details::make_wnf_subscription_state<wil::details::empty_wnf_state>(v8, v14, v9, &v12) < 0 )
    v11 = 0;
  else
    v11 = v12;
  if ( v3 != &v11 )
  {
    wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::reset(v3);
    v11 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(&v11);
  wistd::function<void (void)>::~function<void (void)>(v14);
  return this;
}

```

## disassembly

```asm
0x180009e80  push    rbp
0x180009e82  push    rbx
0x180009e83  push    rsi
0x180009e84  push    rdi
0x180009e85  lea     rbp, [rsp-3Fh]
0x180009e8a  sub     rsp, 0C8h
0x180009e91  mov     rax, cs:__security_cookie
0x180009e98  xor     rax, rsp
0x180009e9b  mov     [rbp+57h+var_30], rax
0x180009e9f  mov     rbx, rcx
0x180009ea2  mov     [rbp+57h+var_B8], rcx
0x180009ea6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180009eab  nop
0x180009eac  add     rcx, 20h ; ' '
0x180009eb0  call    ??0?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::unordered_map<std::wstring,std::wstring>::unordered_map<std::wstring,std::wstring>(void)
0x180009eb5  nop
0x180009eb6  mov     qword ptr [rbx+68h], 0
0x180009ebe  mov     qword ptr [rbx+70h], 0
0x180009ec6  mov     byte ptr [rbx+80h], 0
0x180009ecd  mov     byte ptr [rbx+90h], 0
0x180009ed4  mov     byte ptr [rbx+0A0h], 0
0x180009edb  lea     rdi, [rbx+0A8h]
0x180009ee2  mov     qword ptr [rdi], 0
0x180009ee9  xor     eax, eax
0x180009eeb  mov     [rbx+0B0h], rax
0x180009ef2  lea     rsi, [rbx+0B8h]
0x180009ef9  mov     rcx, rsi
0x180009efc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180009f01  nop
0x180009f02  call    cs:__imp_CreateTimerQueue
0x180009f08  mov     [rbx+70h], rax
0x180009f0c  mov     rcx, [rbp+5Fh]; this
0x180009f10  test    rax, rax
0x180009f13  jnz     short loc_180009F25
0x180009f15  lea     r8, aOnecoreuapDsEx_1; "onecoreuap\\ds\\ext\\common\\ntservice"...
0x180009f1c  lea     edx, [rax+67h]; void *
0x180009f1f  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180009f25  mov     dword ptr [rbx+60h], 3E8h
0x180009f2c  lea     rcx, aNoSuccessfulSy; "(no successful sync)"
0x180009f33  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180009f38  mov     r8, rax
0x180009f3b  mov     rdx, rcx
0x180009f3e  mov     rcx, rsi
0x180009f41  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180009f46  mov     dl, 1; bool
0x180009f48  mov     rcx, rbx; this
0x180009f4b  call    ?OnPolicyChange@TenantRestrictions@@AEAAX_N@Z; TenantRestrictions::OnPolicyChange(bool)
0x180009f50  mov     rdx, rbx
0x180009f53  lea     rcx, [rbp+57h+var_B0]
0x180009f57  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x180009f5c  mov     rcx, [rax]
0x180009f5f  lea     rax, off_1800133A0
0x180009f66  mov     [rbp+57h+var_A0], rax
0x180009f6a  mov     [rbp+57h+var_98], rcx
0x180009f6e  lea     rax, [rbp+57h+var_A0]
0x180009f72  mov     [rbp+57h+var_38], rax
0x180009f76  mov     [rbp+57h+var_B8], 0
0x180009f7e  lea     r9, [rbp+57h+var_B8]
0x180009f82  lea     rdx, [rbp+57h+var_A8]
0x180009f86  call    ??$make_wnf_subscription_state@Uempty_wnf_state@details@wil@@@details@wil@@YAJAEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXXZ@wistd@@KPEAPEAU?$wnf_subscription_state@Uempty_wnf_state@details@wil@@@01@@Z; wil::details::make_wnf_subscription_state<wil::details::empty_wnf_state>(_WNF_STATE_NAME const &,wistd::function<void (void)> &&,ulong,wil::details::wnf_subscription_state<wil::details::empty_wnf_state> * *)
0x180009f8b  test    eax, eax
0x180009f8d  js      short loc_180009F99
0x180009f8f  mov     rdx, [rbp+57h+var_B8]
0x180009f93  mov     [rbp+57h+var_C0], rdx
0x180009f97  jmp     short loc_180009FA3
0x180009f99  mov     [rbp+57h+var_C0], 0
0x180009fa1  xor     edx, edx
0x180009fa3  lea     rax, [rbp+57h+var_C0]
0x180009fa7  cmp     rdi, rax
0x180009faa  jz      short loc_180009FBC
0x180009fac  mov     rcx, rdi
0x180009faf  call    ?reset@?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUwnf_subscription_state_base@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::reset(wil::details::wnf_subscription_state_base *)
0x180009fb4  mov     [rbp+57h+var_C0], 0
0x180009fbc  lea     rcx, [rbp+57h+var_C0]
0x180009fc0  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x180009fc5  lea     rcx, [rbp+57h+var_A8]
0x180009fc9  call    ??1?$function@$$A6AXXZ@wistd@@QEAA@XZ; wistd::function<void (void)>::~function<void (void)>(void)
0x180009fce  nop
0x180009fcf  mov     rax, rbx
0x180009fd2  mov     rcx, [rbp+57h+var_30]
0x180009fd6  xor     rcx, rsp; StackCookie
0x180009fd9  call    __security_check_cookie
0x180009fde  add     rsp, 0C8h
0x180009fe5  pop     rdi
0x180009fe6  pop     rsi
0x180009fe7  pop     rbx
0x180009fe8  pop     rbp
0x180009fe9  retn
```
