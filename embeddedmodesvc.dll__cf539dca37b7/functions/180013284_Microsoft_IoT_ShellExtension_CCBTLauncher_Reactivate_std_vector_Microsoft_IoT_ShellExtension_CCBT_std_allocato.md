# Microsoft::IoT::ShellExtension::CCBTLauncher::Reactivate(std::vector<Microsoft::IoT::ShellExtension::CCBT,std::allocator<Microsoft::IoT::ShellExtension::CCBT>> const &,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>> const &)

- ea: `0x180013284`
- end: `0x18001335a`
- name: `?Reactivate@CCBTLauncher@ShellExtension@IoT@Microsoft@@QEAAJAEBV?$vector@VCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@AEBV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z`
- size: `214`
- prototype: `__int64 __fastcall(Microsoft::IoT::ShellExtension::CCBTLauncher *this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000b3e8`

## callees

- `0x180008358`
- `0x180008378`
- `0x18000d410`
- `0x18000fddc`
- `0x180010e48`
- `0x180010ee8`
- `0x1800114f0`
- `0x180013284`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800132ad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800132ad`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::IoT::ShellExtension::CCBTLauncher::Reactivate(
        Microsoft::IoT::ShellExtension::CCBTLauncher *this,
        const struct Microsoft::IoT::ShellExtension::CCBT **a2,
        char **a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // rbx
  int active; // eax
  int v8; // eax
  int v9; // eax
  int v11; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  struct _RTL_CRITICAL_SECTION *v13; // [rsp+48h] [rbp+10h] BYREF
  __int64 v14; // [rsp+58h] [rbp+20h] BYREF

  if ( a2[1] != *a2 )
  {
    v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 96);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
    v13 = v6;
    active = Microsoft::IoT::ShellExtension::CCBTLauncher::CancelActiveTasksForPackage(this, a3);
    if ( active < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x245,
        (int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\shellcbt.cpp",
        (const char *)(unsigned int)active);
    v8 = Microsoft::IoT::ShellExtension::CCBTLauncher::CancelPendingTasksForPackage((__int64)this, a3);
    if ( v8 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x246,
        (int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\shellcbt.cpp",
        (const char *)(unsigned int)v8);
    std::move<std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<Microsoft::IoT::ShellExtension::CCBT>>>,std::back_insert_iterator<std::vector<Microsoft::IoT::ShellExtension::CCBT>>>(
      &v14,
      *a2,
      a2[1],
      (_QWORD *)this + 17);
    v9 = Microsoft::IoT::ShellExtension::CCBTLauncher::DoLaunchCBT(this);
    if ( v9 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x249,
        (int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\shellcbt.cpp",
        (const char *)(unsigned int)v9,
        v11);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v13);
  }
  return 0;
}

```

## disassembly

```asm
0x180013284  mov     [rsp+arg_0], rbx
0x180013289  push    rbp
0x18001328a  push    rsi
0x18001328b  push    rdi; int
0x18001328c  sub     rsp, 20h
0x180013290  mov     rbp, r8
0x180013293  mov     rdi, rdx
0x180013296  mov     rsi, rcx
0x180013299  mov     rax, [rdx+8]
0x18001329d  cmp     rax, [rdx]
0x1800132a0  jz      loc_18001334B
0x1800132a6  lea     rbx, [rcx+60h]
0x1800132aa  mov     rcx, rbx; lpCriticalSection
0x1800132ad  call    cs:__imp_EnterCriticalSection
0x1800132b3  mov     [rsp+38h+arg_8], rbx
0x1800132b8  mov     rdx, rbp
0x1800132bb  mov     rcx, rsi; this
0x1800132be  call    ?CancelActiveTasksForPackage@CCBTLauncher@ShellExtension@IoT@Microsoft@@AEAAJAEBV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@_N@Z; Microsoft::IoT::ShellExtension::CCBTLauncher::CancelActiveTasksForPackage(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>> const &,bool)
0x1800132c3  mov     rcx, [rsp+38h]; this
0x1800132c8  lea     rbx, aOnecoreuapShel_2; "onecoreuap\\shell\\embedded\\shell\\iot"...
0x1800132cf  test    eax, eax
0x1800132d1  jns     short loc_1800132E3
0x1800132d3  mov     r9d, eax; char *
0x1800132d6  mov     r8, rbx; unsigned int
0x1800132d9  mov     edx, 245h; void *
0x1800132de  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800132e3  mov     rdx, rbp
0x1800132e6  mov     rcx, rsi
0x1800132e9  call    ?CancelPendingTasksForPackage@CCBTLauncher@ShellExtension@IoT@Microsoft@@AEAAJAEBV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@_N@Z; Microsoft::IoT::ShellExtension::CCBTLauncher::CancelPendingTasksForPackage(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>> const &,bool)
0x1800132ee  mov     rcx, [rsp+38h]; this
0x1800132f3  test    eax, eax
0x1800132f5  jns     short loc_180013307
0x1800132f7  mov     r9d, eax; char *
0x1800132fa  mov     r8, rbx; unsigned int
0x1800132fd  mov     edx, 246h; void *
0x180013302  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180013307  lea     r9, [rsi+88h]
0x18001330e  mov     r8, [rdi+8]
0x180013312  mov     rdx, [rdi]
0x180013315  lea     rcx, [rsp+38h+arg_18]
0x18001331a  call    ??$move@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@@std@@V?$back_insert_iterator@V?$vector@VCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@@2@@std@@YA?AV?$back_insert_iterator@V?$vector@VCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@@0@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@@0@0V10@@Z; std::move<std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<Microsoft::IoT::ShellExtension::CCBT>>>,std::back_insert_iterator<std::vector<Microsoft::IoT::ShellExtension::CCBT>>>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<Microsoft::IoT::ShellExtension::CCBT>>>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<Microsoft::IoT::ShellExtension::CCBT>>>,std::back_insert_iterator<std::vector<Microsoft::IoT::ShellExtension::CCBT>>)
0x18001331f  mov     rcx, rsi; this
0x180013322  call    ?DoLaunchCBT@CCBTLauncher@ShellExtension@IoT@Microsoft@@AEAAJXZ; Microsoft::IoT::ShellExtension::CCBTLauncher::DoLaunchCBT(void)
0x180013327  mov     rcx, [rsp+38h]; this
0x18001332c  test    eax, eax
0x18001332e  jns     short loc_180013341
0x180013330  mov     r9d, eax; char *
0x180013333  mov     r8, rbx; unsigned int
0x180013336  mov     edx, 249h; void *
0x18001333b  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180013341  lea     rcx, [rsp+38h+arg_8]
0x180013346  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18001334b  xor     eax, eax
0x18001334d  mov     rbx, [rsp+38h+arg_0]
0x180013352  add     rsp, 20h
0x180013356  pop     rdi
0x180013357  pop     rsi
0x180013358  pop     rbp
0x180013359  retn
```
