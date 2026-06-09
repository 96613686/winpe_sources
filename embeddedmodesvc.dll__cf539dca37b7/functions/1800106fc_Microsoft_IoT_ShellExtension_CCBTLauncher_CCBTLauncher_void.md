# Microsoft::IoT::ShellExtension::CCBTLauncher::~CCBTLauncher(void)

- ea: `0x1800106fc`
- end: `0x180010915`
- name: `??1CCBTLauncher@ShellExtension@IoT@Microsoft@@UEAA@XZ`
- size: `537`
- prototype: `void __fastcall(Microsoft::IoT::ShellExtension::CCBTLauncher *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180010d80`

## callees

- `0x1800044e0`
- `0x180005590`
- `0x180008358`
- `0x180008378`
- `0x180009f7c`
- `0x18000a060`
- `0x18000a9f4`
- `0x18000c300`
- `0x18000d410`
- `0x1800106fc`
- `0x180010f74`
- `0x180011134`
- `0x180014dfc`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800108d6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800108d6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010725`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010725`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall Microsoft::IoT::ShellExtension::CCBTLauncher::~CCBTLauncher(
        Microsoft::IoT::ShellExtension::CCBTLauncher *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  bool v3; // r8
  struct Microsoft::IoT::ShellExtension::CCBT *i; // rbx
  int v5; // eax
  unsigned int v6; // eax
  __int64 v7; // rcx
  int v8; // eax
  __int64 v9; // rcx
  Microsoft::IoT::ShellExtension::CCBT *v10; // rcx
  Microsoft::IoT::ShellExtension::CCBT *v11; // rcx
  void *v12; // rdx
  std::_Ref_count_base *v13; // rcx
  int v14; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  struct _RTL_CRITICAL_SECTION *v16; // [rsp+50h] [rbp+8h] BYREF

  *(_QWORD *)this = &Microsoft::IoT::ShellExtension::CCBTLauncher::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IBackgroundSessionCallbacks>>'};
  *((_QWORD *)this + 4) = &Microsoft::IoT::ShellExtension::CCBTLauncher::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IBackgroundSessionCallbacks>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IBackgroundSessionCallbacks>>'};
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 96);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  v16 = v2;
  for ( i = (struct Microsoft::IoT::ShellExtension::CCBT *)*((_QWORD *)this + 20);
        i != *((struct Microsoft::IoT::ShellExtension::CCBT **)this + 21);
        i = (struct Microsoft::IoT::ShellExtension::CCBT *)((char *)i + 88) )
  {
    v5 = Microsoft::IoT::ShellExtension::CCBTLauncher::CancelTask(this, i, v3);
    if ( v5 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1B9,
        (unsigned int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\shellcbt.cpp",
        (const char *)(unsigned int)v5,
        v14);
  }
  Microsoft::IoT::ShellExtension::CCBTLauncher::CheckForPendingTasks(this);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v16);
  v6 = Microsoft::IoT::ShellExtension::CCBTLauncher::WaitForLaunchResults(this);
  if ( (int)(v6 + 0x80000000) >= 0 && v6 != -2147024638 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x330,
      (unsigned int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\shellcbt.cpp",
      (const char *)v6,
      v14);
  v7 = *((_QWORD *)this + 11);
  if ( v7 )
  {
    v8 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v7 + 48LL))(v7, *((unsigned int *)this + 14));
    if ( v8 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x335,
        (unsigned int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\shellcbt.cpp",
        (const char *)(unsigned int)v8,
        v14);
  }
  v9 = *((_QWORD *)this + 25);
  if ( v9 )
  {
    *((_QWORD *)this + 25) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  Microsoft::WRL::Details::MakeAllocator<Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost>::~MakeAllocator<Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost>((void **)this + 24);
  v10 = (Microsoft::IoT::ShellExtension::CCBT *)*((_QWORD *)this + 20);
  if ( v10 )
  {
    std::_Destroy_range<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(
      v10,
      *((Microsoft::IoT::ShellExtension::CCBT **)this + 21));
    std::_Deallocate<16>(*((_QWORD **)this + 20), 8 * ((__int64)(*((_QWORD *)this + 22) - *((_QWORD *)this + 20)) >> 3));
    *((_QWORD *)this + 20) = 0;
    *((_QWORD *)this + 21) = 0;
    *((_QWORD *)this + 22) = 0;
  }
  v11 = (Microsoft::IoT::ShellExtension::CCBT *)*((_QWORD *)this + 17);
  if ( v11 )
  {
    std::_Destroy_range<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(
      v11,
      *((Microsoft::IoT::ShellExtension::CCBT **)this + 18));
    std::_Deallocate<16>(*((_QWORD **)this + 17), 8 * ((__int64)(*((_QWORD *)this + 19) - *((_QWORD *)this + 17)) >> 3));
    *((_QWORD *)this + 17) = 0;
    *((_QWORD *)this + 18) = 0;
    *((_QWORD *)this + 19) = 0;
  }
  DeleteCriticalSection(v2);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 88);
  v13 = (std::_Ref_count_base *)*((_QWORD *)this + 10);
  if ( v13 )
    std::_Ref_count_base::_Decref(v13);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    (wil::details **)this + 8,
    v12);
  *((_DWORD *)this + 11) = -1073741823;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 24);
}

```

## disassembly

```asm
0x1800106fc  push    rbx
0x1800106fe  push    rsi
0x1800106ff  push    rdi
0x180010700  push    r14
0x180010702  sub     rsp, 28h
0x180010706  mov     rdi, rcx
0x180010709  lea     rax, ??_7CCBTLauncher@ShellExtension@IoT@Microsoft@@6B?$Selector@VFtmBase@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIBackgroundSessionCallbacks@@@Details@23@@Details@WRL@3@@; const Microsoft::IoT::ShellExtension::CCBTLauncher::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IBackgroundSessionCallbacks>>'}
0x180010710  mov     [rcx], rax
0x180010713  lea     rax, ??_7CCBTLauncher@ShellExtension@IoT@Microsoft@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIBackgroundSessionCallbacks@@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIBackgroundSessionCallbacks@@@234@@Details@WRL@3@@; const Microsoft::IoT::ShellExtension::CCBTLauncher::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IBackgroundSessionCallbacks>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IBackgroundSessionCallbacks>>'}
0x18001071a  mov     [rcx+20h], rax
0x18001071e  lea     rsi, [rcx+60h]
0x180010722  mov     rcx, rsi; lpCriticalSection
0x180010725  call    cs:__imp_EnterCriticalSection
0x18001072b  mov     [rsp+48h+arg_0], rsi
0x180010730  mov     rbx, [rdi+0A0h]
0x180010737  lea     r14, aOnecoreuapShel_2; "onecoreuap\\shell\\embedded\\shell\\iot"...
0x18001073e  mov     rcx, rdi; this
0x180010741  cmp     rbx, [rdi+0A8h]
0x180010748  jz      short loc_180010771
0x18001074a  mov     rdx, rbx; struct Microsoft::IoT::ShellExtension::CCBT *
0x18001074d  call    ?CancelTask@CCBTLauncher@ShellExtension@IoT@Microsoft@@AEAAJAEAVCCBT@234@_N@Z; Microsoft::IoT::ShellExtension::CCBTLauncher::CancelTask(Microsoft::IoT::ShellExtension::CCBT &,bool)
0x180010752  test    eax, eax
0x180010754  jns     short loc_18001076B
0x180010756  mov     rcx, [rsp+48h]; this
0x18001075b  mov     r9d, eax; char *
0x18001075e  mov     r8, r14; unsigned int
0x180010761  mov     edx, 1B9h; void *
0x180010766  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001076b  add     rbx, 58h ; 'X'
0x18001076f  jmp     short loc_18001073E
0x180010771  call    ?CheckForPendingTasks@CCBTLauncher@ShellExtension@IoT@Microsoft@@AEAAXXZ; Microsoft::IoT::ShellExtension::CCBTLauncher::CheckForPendingTasks(void)
0x180010776  lea     rcx, [rsp+48h+arg_0]
0x18001077b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180010780  mov     rcx, rdi; this
0x180010783  call    ?WaitForLaunchResults@CCBTLauncher@ShellExtension@IoT@Microsoft@@QEAAJXZ; Microsoft::IoT::ShellExtension::CCBTLauncher::WaitForLaunchResults(void)
0x180010788  mov     edx, 80000000h
0x18001078d  lea     ecx, [rax+rdx]
0x180010790  test    edx, ecx
0x180010792  jnz     short loc_1800107B1
0x180010794  cmp     eax, 80070102h
0x180010799  jz      short loc_1800107B1
0x18001079b  mov     rcx, [rsp+48h]; this
0x1800107a0  mov     r9d, eax; char *
0x1800107a3  mov     r8, r14; unsigned int
0x1800107a6  mov     edx, 330h; void *
0x1800107ab  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800107b1  mov     rcx, [rdi+58h]
0x1800107b5  test    rcx, rcx
0x1800107b8  jz      short loc_1800107E3
0x1800107ba  mov     rax, [rcx]
0x1800107bd  mov     edx, [rdi+38h]
0x1800107c0  mov     rax, [rax+30h]
0x1800107c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107c9  mov     rcx, [rsp+48h]; this
0x1800107ce  test    eax, eax
0x1800107d0  jns     short loc_1800107E3
0x1800107d2  mov     r9d, eax; char *
0x1800107d5  mov     r8, r14; unsigned int
0x1800107d8  mov     edx, 335h; void *
0x1800107dd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800107e2  nop
0x1800107e3  mov     rcx, [rdi+0C8h]
0x1800107ea  test    rcx, rcx
0x1800107ed  jz      short loc_180010807
0x1800107ef  mov     qword ptr [rdi+0C8h], 0
0x1800107fa  mov     rax, [rcx]
0x1800107fd  mov     rax, [rax+10h]
0x180010801  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010806  nop
0x180010807  lea     rcx, [rdi+0C0h]
0x18001080e  call    ??1?$MakeAllocator@VEmbeddedModeTaskHost@EmbeddedMode@IoT@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost>::~MakeAllocator<Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost>(void)
0x180010813  mov     rcx, [rdi+0A0h]; this
0x18001081a  mov     r14, 2E8BA2E8BA2E8BA3h
0x180010824  test    rcx, rcx
0x180010827  jz      short loc_180010878
0x180010829  mov     rdx, [rdi+0A8h]
0x180010830  call    ??$_Destroy_range@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@YAXPEAVCCBT@ShellExtension@IoT@Microsoft@@QEAV1234@AEAV?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(Microsoft::IoT::ShellExtension::CCBT *,Microsoft::IoT::ShellExtension::CCBT * const,std::allocator<Microsoft::IoT::ShellExtension::CCBT> &)
0x180010835  mov     rcx, [rdi+0A0h]
0x18001083c  mov     rax, [rdi+0B0h]
0x180010843  sub     rax, rcx
0x180010846  sar     rax, 3
0x18001084a  imul    rax, r14
0x18001084e  imul    rdx, rax, 58h ; 'X'
0x180010852  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180010857  mov     qword ptr [rdi+0A0h], 0
0x180010862  mov     qword ptr [rdi+0A8h], 0
0x18001086d  mov     qword ptr [rdi+0B0h], 0
0x180010878  mov     rcx, [rdi+88h]; this
0x18001087f  test    rcx, rcx
0x180010882  jz      short loc_1800108D3
0x180010884  mov     rdx, [rdi+90h]
0x18001088b  call    ??$_Destroy_range@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@YAXPEAVCCBT@ShellExtension@IoT@Microsoft@@QEAV1234@AEAV?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(Microsoft::IoT::ShellExtension::CCBT *,Microsoft::IoT::ShellExtension::CCBT * const,std::allocator<Microsoft::IoT::ShellExtension::CCBT> &)
0x180010890  mov     rcx, [rdi+88h]
0x180010897  mov     rax, [rdi+98h]
0x18001089e  sub     rax, rcx
0x1800108a1  sar     rax, 3
0x1800108a5  imul    rax, r14
0x1800108a9  imul    rdx, rax, 58h ; 'X'
0x1800108ad  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800108b2  mov     qword ptr [rdi+88h], 0
0x1800108bd  mov     qword ptr [rdi+90h], 0
0x1800108c8  mov     qword ptr [rdi+98h], 0
0x1800108d3  mov     rcx, rsi; lpCriticalSection
0x1800108d6  call    cs:__imp_DeleteCriticalSection
0x1800108dc  lea     rcx, [rdi+58h]
0x1800108e0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800108e5  mov     rcx, [rdi+50h]; this
0x1800108e9  test    rcx, rcx
0x1800108ec  jz      short loc_1800108F3
0x1800108ee  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800108f3  lea     rcx, [rdi+40h]
0x1800108f7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800108fc  mov     dword ptr [rdi+2Ch], 0C0000001h
0x180010903  lea     rcx, [rdi+18h]
0x180010907  add     rsp, 28h
0x18001090b  pop     r14
0x18001090d  pop     rdi
0x18001090e  pop     rsi
0x18001090f  pop     rbx
0x180010910  jmp     ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
```
