# Microsoft::IoT::ShellExtension::CCBTLauncher::DoLaunchCBT(void)

- ea: `0x1800114f0`
- end: `0x180011a14`
- name: `?DoLaunchCBT@CCBTLauncher@ShellExtension@IoT@Microsoft@@AEAAJXZ`
- size: `1316`
- prototype: `__int64 __fastcall(Microsoft::IoT::ShellExtension::CCBTLauncher *__hidden this)`
- caller_count: `3`
- callee_count: `26`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180010acc`
- `0x180013284`
- `0x180013360`

## callees

- `0x180002b10`
- `0x180005fc4`
- `0x180008358`
- `0x180008378`
- `0x1800091c4`
- `0x180009f7c`
- `0x18000a060`
- `0x18000acf4`
- `0x18000d410`
- `0x18000dc84`
- `0x18000ed5c`
- `0x18000eea8`
- `0x18000f710`
- `0x18000f968`
- `0x18000fe60`
- `0x180010040`
- `0x180010070`
- `0x1800105c8`
- `0x180010678`
- `0x1800114f0`
- `0x18001245c`
- `0x180012f10`
- `0x180013648`
- `0x180013b38`
- `0x180014fd0`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001154d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001154d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180011724`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800118fa`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180011724`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800118fa`

## string_xrefs

- `0x18001176d`: `BackgroundTaskActivation`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::IoT::ShellExtension::CCBTLauncher::DoLaunchCBT(
        Microsoft::IoT::ShellExtension::CCBTLauncher *this)
{
  void *v2; // rdx
  int v3; // ebx
  unsigned int v4; // eax
  int v5; // eax
  unsigned int v6; // ebx
  Microsoft::IoT::ShellExtension::CCBT *v8; // r14
  const unsigned __int16 *v9; // rcx
  const unsigned __int16 *v10; // rbx
  __int64 v11; // rdx
  __int64 v12; // r11
  __int64 (__fastcall *v13)(__int64, __int64, _QWORD, _QWORD); // r10
  const unsigned __int16 *v14; // rcx
  int v15; // eax
  int v16; // ebx
  wil::details::in1diag3 *v17; // rcx
  __int64 v18; // rdx
  const unsigned __int16 *v19; // rcx
  const unsigned __int16 *v20; // rax
  int v21; // [rsp+20h] [rbp-3F8h]
  int v22; // [rsp+20h] [rbp-3F8h]
  const unsigned __int16 *v23; // [rsp+78h] [rbp-3A0h] BYREF
  const unsigned __int16 *v24; // [rsp+80h] [rbp-398h] BYREF
  char *v25; // [rsp+88h] [rbp-390h] BYREF
  Microsoft::IoT::ShellExtension::CCBT *v26; // [rsp+90h] [rbp-388h] BYREF
  Microsoft::IoT::ShellExtension::CCBT *v27; // [rsp+98h] [rbp-380h]
  __int64 v28; // [rsp+A0h] [rbp-378h]
  _BYTE *v29; // [rsp+A8h] [rbp-370h]
  char v30; // [rsp+B0h] [rbp-368h]
  _QWORD v31[2]; // [rsp+B8h] [rbp-360h] BYREF
  char v32; // [rsp+C8h] [rbp-350h]
  char v33[8]; // [rsp+E0h] [rbp-338h] BYREF
  ULONGLONG TickCount64; // [rsp+E8h] [rbp-330h]
  const unsigned __int16 **v35; // [rsp+F0h] [rbp-328h]
  const unsigned __int16 *v36; // [rsp+108h] [rbp-310h]
  int v37; // [rsp+118h] [rbp-300h]
  char v38; // [rsp+12Eh] [rbp-2EAh]
  _QWORD v39[42]; // [rsp+140h] [rbp-2D8h] BYREF
  _BYTE v40[368]; // [rsp+290h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+418h] [rbp+0h]

  Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskLaunch::Start<>((Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskLaunch *)v40);
  v29 = v40;
  v30 = 1;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  v25 = (char *)this + 96;
  if ( *((_QWORD *)this + 17) == *((_QWORD *)this + 18) )
    goto LABEL_13;
  if ( !*((_QWORD *)this + 11) && (int)Microsoft::IoT::ShellExtension::CCBTLauncher::ODBInit(this) < 0 )
  {
    v3 = Microsoft::IoT::ShellExtension::CCBTLauncher::ODBInit(this);
    v4 = Microsoft::IoT::ShellExtension::CCBTLauncher::ODBInit(this);
    if ( v3 != -2147023781 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x17A,
        (unsigned int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\shellcbt.cpp",
        (const char *)v4,
        v21);
    v5 = Microsoft::IoT::ShellExtension::CCBTLauncher::ODBInit(this);
    v6 = v5;
    if ( v5 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x17A,
        (unsigned int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\shellcbt.cpp",
        (const char *)(unsigned int)v5,
        v21);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v25);
    v30 = 0;
    wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v40);
    Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskLaunch::~BackgroundTaskLaunch((Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskLaunch *)v40);
    return v6;
  }
  wil::details::ResetEvent(*((wil::details **)this + 8), v2);
  std::vector<Microsoft::IoT::ShellExtension::CCBT>::vector<Microsoft::IoT::ShellExtension::CCBT>(
    &v26,
    (char *)this + 136);
  std::vector<Microsoft::IoT::ShellExtension::CCBT>::clear((char *)this + 136);
  v8 = v27;
  while ( v26 != v8 )
  {
    v8 = (Microsoft::IoT::ShellExtension::CCBT *)((char *)v8 - 88);
    Microsoft::IoT::ShellExtension::CCBT::CCBT(v33, v8);
    Microsoft::IoT::ShellExtension::CCBT::~CCBT(v8);
    v27 = v8;
    if ( v38 )
    {
      v23 = v36;
      if ( v35 )
        v9 = *v35;
      else
        v9 = 0;
      v24 = v9;
      Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskCanceledPending<unsigned short *,unsigned short *>(
        &v24,
        &v23);
      TickCount64 = GetTickCount64();
      std::vector<Microsoft::IoT::ShellExtension::CCBT>::_Emplace_one_at_back<Microsoft::IoT::ShellExtension::CCBT>(
        (char *)this + 160,
        v33);
      goto LABEL_19;
    }
    if ( v35 )
      v10 = *v35;
    else
      v10 = 0;
    wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
      v39,
      "BackgroundTaskActivation");
    v39[0] = &Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskActivation::`vftable';
    Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskActivation::StartActivity(
      (Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskActivation *)v39,
      v10);
    v31[1] = v39;
    v32 = 1;
    v11 = *((_QWORD *)this + 24);
    v12 = *((_QWORD *)this + 11);
    v13 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v12 + 56LL);
    if ( v11 )
    {
      if ( v35 )
        v14 = *v35;
      else
        LODWORD(v14) = 0;
      v22 = (int)v14;
      v15 = v13(v12, v11, 0, *((unsigned int *)this + 14));
      v16 = v15;
      v17 = retaddr;
      if ( v15 >= 0 )
        goto LABEL_35;
      v18 = 412;
    }
    else
    {
      if ( v35 )
        v19 = *v35;
      else
        LODWORD(v19) = 0;
      v22 = (int)v19;
      v15 = v13(v12, 0, 0, *((unsigned int *)this + 14));
      v16 = v15;
      v17 = retaddr;
      if ( v15 >= 0 )
        goto LABEL_35;
      v18 = 416;
    }
    wil::details::in1diag3::_Log_Hr(
      v17,
      (void *)v18,
      (unsigned int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\shellcbt.cpp",
      (const char *)(unsigned int)v15,
      v22);
LABEL_35:
    LODWORD(v23) = v16;
    if ( v16 >= 0 )
    {
      std::vector<Microsoft::IoT::ShellExtension::CCBT>::_Emplace_one_at_back<Microsoft::IoT::ShellExtension::CCBT>(
        (char *)this + 160,
        v33);
    }
    else
    {
      v37 = v16;
      TickCount64 = GetTickCount64();
      v24 = v36;
      v20 = (const unsigned __int16 *)v35;
      if ( v35 )
        v20 = *v35;
      v31[0] = v20;
      Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskActivationFailed<unsigned short *,unsigned short *,long &>(
        v31,
        &v24,
        &v23);
      Microsoft::IoT::ShellExtension::CCBTLauncher::ReLaunch(this, (struct Microsoft::IoT::ShellExtension::CCBT *)v33);
    }
    v32 = 0;
    wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v39);
    Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskActivation::~BackgroundTaskActivation((Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskActivation *)v39);
LABEL_19:
    Microsoft::IoT::ShellExtension::CCBT::~CCBT((Microsoft::IoT::ShellExtension::CCBT *)v33);
  }
  if ( v26 )
  {
    std::_Destroy_range<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(v26);
    std::_Deallocate<16>(v26, 8 * ((v28 - (__int64)v26) >> 3));
  }
LABEL_13:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v25);
  if ( v30 )
    wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v29);
  Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskLaunch::~BackgroundTaskLaunch((Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskLaunch *)v40);
  return 0;
}

```

## disassembly

```asm
0x1800114f0  mov     [rsp+arg_8], rbx
0x1800114f5  mov     [rsp+arg_10], rsi
0x1800114fa  push    r14
0x1800114fc  sub     rsp, 410h
0x180011503  mov     rax, cs:__security_cookie
0x18001150a  xor     rax, rsp
0x18001150d  mov     [rsp+418h+var_18], rax
0x180011515  mov     rsi, rcx
0x180011518  mov     dword ptr [rsp+418h+var_3A8], 0
0x180011520  lea     rcx, [rsp+418h+var_188]; this
0x180011528  call    ??$Start@$$V@BackgroundTaskLaunch@CTelemetryProvider@ShellExtension@IoT@Microsoft@@SA?AV01234@XZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskLaunch::Start<>(void)
0x18001152d  nop
0x18001152e  lea     rax, [rsp+418h+var_188]
0x180011536  mov     [rsp+418h+var_370], rax
0x18001153e  mov     [rsp+418h+var_368], 1
0x180011546  lea     rbx, [rsi+60h]
0x18001154a  mov     rcx, rbx; lpCriticalSection
0x18001154d  call    cs:__imp_EnterCriticalSection
0x180011553  mov     [rsp+418h+var_390], rbx
0x18001155b  lea     rbx, [rsi+88h]
0x180011562  mov     rax, [rbx+8]
0x180011566  cmp     [rbx], rax
0x180011569  jz      loc_1800116A7
0x18001156f  cmp     qword ptr [rsi+58h], 0
0x180011574  jnz     loc_180011624
0x18001157a  mov     rcx, rsi; this
0x18001157d  call    ?ODBInit@CCBTLauncher@ShellExtension@IoT@Microsoft@@AEAAJXZ; Microsoft::IoT::ShellExtension::CCBTLauncher::ODBInit(void)
0x180011582  test    eax, eax
0x180011584  jns     loc_180011624
0x18001158a  mov     rcx, rsi; this
0x18001158d  call    ?ODBInit@CCBTLauncher@ShellExtension@IoT@Microsoft@@AEAAJXZ; Microsoft::IoT::ShellExtension::CCBTLauncher::ODBInit(void)
0x180011592  mov     ebx, eax
0x180011594  mov     rcx, rsi; this
0x180011597  call    ?ODBInit@CCBTLauncher@ShellExtension@IoT@Microsoft@@AEAAJXZ; Microsoft::IoT::ShellExtension::CCBTLauncher::ODBInit(void)
0x18001159c  mov     rcx, [rsp+418h]; this
0x1800115a4  cmp     ebx, 8007045Bh
0x1800115aa  jz      short loc_1800115C1
0x1800115ac  mov     r9d, eax; char *
0x1800115af  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\embedded\\shell\\iot"...
0x1800115b6  mov     edx, 17Ah; void *
0x1800115bb  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800115c1  mov     rcx, rsi; this
0x1800115c4  call    ?ODBInit@CCBTLauncher@ShellExtension@IoT@Microsoft@@AEAAJXZ; Microsoft::IoT::ShellExtension::CCBTLauncher::ODBInit(void)
0x1800115c9  mov     ebx, eax
0x1800115cb  test    eax, eax
0x1800115cd  jns     short loc_1800115EC
0x1800115cf  mov     rcx, [rsp+418h]; this
0x1800115d7  mov     r9d, eax; char *
0x1800115da  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\embedded\\shell\\iot"...
0x1800115e1  mov     edx, 17Ah; void *
0x1800115e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800115eb  nop
0x1800115ec  lea     rcx, [rsp+418h+var_390]
0x1800115f4  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800115f9  nop
0x1800115fa  mov     [rsp+418h+var_368], 0
0x180011602  lea     rcx, [rsp+418h+var_188]
0x18001160a  call    ?Stop@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001160f  nop
0x180011610  lea     rcx, [rsp+418h+var_188]; this
0x180011618  call    ??1BackgroundTaskLaunch@CTelemetryProvider@ShellExtension@IoT@Microsoft@@QEAA@XZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskLaunch::~BackgroundTaskLaunch(void)
0x18001161d  mov     eax, ebx
0x18001161f  jmp     loc_1800119EE
0x180011624  mov     rcx, [rsi+40h]; this
0x180011628  call    ?ResetEvent@details@wil@@YAXPEAX@Z; wil::details::ResetEvent(void *)
0x18001162d  mov     rdx, rbx
0x180011630  lea     rcx, [rsp+418h+var_388]
0x180011638  call    ??0?$vector@VCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@QEAA@$$QEAV01@@Z; std::vector<Microsoft::IoT::ShellExtension::CCBT>::vector<Microsoft::IoT::ShellExtension::CCBT>(std::vector<Microsoft::IoT::ShellExtension::CCBT> &&)
0x18001163d  nop
0x18001163e  mov     rcx, rbx
0x180011641  call    ?clear@?$vector@VCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@QEAAXXZ; std::vector<Microsoft::IoT::ShellExtension::CCBT>::clear(void)
0x180011646  mov     r14, [rsp+418h+var_380]
0x18001164e  cmp     [rsp+418h+var_388], r14
0x180011656  jnz     short loc_1800116BA
0x180011658  cmp     [rsp+418h+var_388], 0
0x180011661  jz      short loc_1800116A7
0x180011663  mov     rdx, r14
0x180011666  mov     rcx, [rsp+418h+var_388]; this
0x18001166e  call    ??$_Destroy_range@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@YAXPEAVCCBT@ShellExtension@IoT@Microsoft@@QEAV1234@AEAV?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(Microsoft::IoT::ShellExtension::CCBT *,Microsoft::IoT::ShellExtension::CCBT * const,std::allocator<Microsoft::IoT::ShellExtension::CCBT> &)
0x180011673  mov     rax, [rsp+418h+var_378]
0x18001167b  sub     rax, [rsp+418h+var_388]
0x180011683  sar     rax, 3
0x180011687  mov     rcx, 2E8BA2E8BA2E8BA3h
0x180011691  imul    rax, rcx
0x180011695  imul    rdx, rax, 58h ; 'X'
0x180011699  mov     rcx, [rsp+418h+var_388]
0x1800116a1  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800116a6  nop
0x1800116a7  lea     rcx, [rsp+418h+var_390]
0x1800116af  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800116b4  nop
0x1800116b5  jmp     loc_1800119A1
0x1800116ba  add     r14, 0FFFFFFFFFFFFFFA8h
0x1800116be  mov     rdx, r14
0x1800116c1  lea     rcx, [rsp+418h+var_338]
0x1800116c9  call    ??0CCBT@ShellExtension@IoT@Microsoft@@QEAA@$$QEAV0123@@Z; Microsoft::IoT::ShellExtension::CCBT::CCBT(Microsoft::IoT::ShellExtension::CCBT &&)
0x1800116ce  nop
0x1800116cf  mov     rcx, r14; this
0x1800116d2  call    ??1CCBT@ShellExtension@IoT@Microsoft@@QEAA@XZ; Microsoft::IoT::ShellExtension::CCBT::~CCBT(void)
0x1800116d7  mov     [rsp+418h+var_380], r14
0x1800116df  cmp     [rsp+418h+var_2EA], 0
0x1800116e7  jz      short loc_180011759
0x1800116e9  mov     rax, [rsp+418h+var_310]
0x1800116f1  mov     [rsp+418h+var_3A0], rax
0x1800116f6  mov     rax, [rsp+418h+var_328]
0x1800116fe  test    rax, rax
0x180011701  jz      short loc_180011708
0x180011703  mov     rcx, [rax]
0x180011706  jmp     short loc_18001170A
0x180011708  xor     ecx, ecx
0x18001170a  mov     [rsp+418h+var_398], rcx
0x180011712  lea     rdx, [rsp+418h+var_3A0]
0x180011717  lea     rcx, [rsp+418h+var_398]
0x18001171f  call    ??$BackgroundTaskCanceledPending@PEAGPEAG@CTelemetryProvider@ShellExtension@IoT@Microsoft@@SAX$$QEAPEAG0@Z; Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskCanceledPending<ushort *,ushort *>(ushort * &&,ushort * &&)
0x180011724  call    cs:__imp_GetTickCount64
0x18001172a  mov     [rsp+418h+var_330], rax
0x180011732  lea     rcx, [rsi+0A0h]
0x180011739  lea     rdx, [rsp+418h+var_338]
0x180011741  call    ??$_Emplace_one_at_back@VCCBT@ShellExtension@IoT@Microsoft@@@?$vector@VCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@AEAAAEAVCCBT@ShellExtension@IoT@Microsoft@@$$QEAV2345@@Z; std::vector<Microsoft::IoT::ShellExtension::CCBT>::_Emplace_one_at_back<Microsoft::IoT::ShellExtension::CCBT>(Microsoft::IoT::ShellExtension::CCBT &&)
0x180011746  nop
0x180011747  lea     rcx, [rsp+418h+var_338]; this
0x18001174f  call    ??1CCBT@ShellExtension@IoT@Microsoft@@QEAA@XZ; Microsoft::IoT::ShellExtension::CCBT::~CCBT(void)
0x180011754  jmp     loc_18001164E
0x180011759  mov     rax, [rsp+418h+var_328]
0x180011761  test    rax, rax
0x180011764  jz      short loc_18001176B
0x180011766  mov     rbx, [rax]
0x180011769  jmp     short loc_18001176D
0x18001176b  xor     ebx, ebx
0x18001176d  lea     rdx, aBackgroundtask_3; "BackgroundTaskActivation"
0x180011774  lea     rcx, [rsp+418h+var_2D8]
0x18001177c  call    ??0?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180011781  lea     rax, ??_7BackgroundTaskActivation@CTelemetryProvider@ShellExtension@IoT@Microsoft@@6B@; const Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskActivation::`vftable'
0x180011788  mov     [rsp+418h+var_2D8], rax
0x180011790  mov     rdx, rbx; unsigned __int16 *
0x180011793  lea     rcx, [rsp+418h+var_2D8]; this
0x18001179b  call    ?StartActivity@BackgroundTaskActivation@CTelemetryProvider@ShellExtension@IoT@Microsoft@@QEAAXPEBG@Z; Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskActivation::StartActivity(ushort const *)
0x1800117a0  nop
0x1800117a1  lea     rax, [rsp+418h+var_2D8]
0x1800117a9  mov     [rsp+418h+var_358], rax
0x1800117b1  mov     [rsp+418h+var_350], 1
0x1800117b9  mov     rdx, [rsi+0C0h]
0x1800117c0  mov     r11, [rsi+58h]
0x1800117c4  mov     rax, [r11]
0x1800117c7  mov     r10, [rax+38h]
0x1800117cb  mov     rax, [rsp+418h+var_328]
0x1800117d3  test    rdx, rdx
0x1800117d6  jz      loc_18001185E
0x1800117dc  mov     r8, [rsp+418h+var_310]
0x1800117e4  test    rax, rax
0x1800117e7  jz      short loc_1800117EE
0x1800117e9  mov     rcx, [rax]
0x1800117ec  jmp     short loc_1800117F0
0x1800117ee  xor     ecx, ecx
0x1800117f0  lea     rax, [rsp+418h+var_2FC]
0x1800117f8  mov     [rsp+418h+var_3C0], rax
0x1800117fd  mov     [rsp+418h+var_3C8], 0
0x180011806  mov     [rsp+418h+var_3D0], 0
0x18001180f  mov     [rsp+418h+var_3D8], 0
0x180011817  mov     [rsp+418h+var_3E0], 0
0x180011820  mov     [rsp+418h+var_3E8], 0
0x180011829  mov     [rsp+418h+var_3F0], r8
0x18001182e  mov     qword ptr [rsp+418h+var_3F8], rcx
0x180011833  mov     r9d, [rsi+38h]
0x180011837  xor     r8d, r8d
0x18001183a  mov     rcx, r11
0x18001183d  mov     rax, r10
0x180011840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011845  mov     ebx, eax
0x180011847  mov     rcx, [rsp+418h]
0x18001184f  test    eax, eax
0x180011851  jns     loc_1800118EB
0x180011857  mov     edx, 19Ch
0x18001185c  jmp     short loc_1800118DC
0x18001185e  mov     rdx, [rsp+418h+var_310]
0x180011866  test    rax, rax
0x180011869  jz      short loc_180011870
0x18001186b  mov     rcx, [rax]
0x18001186e  jmp     short loc_180011872
0x180011870  xor     ecx, ecx
0x180011872  lea     rax, [rsp+418h+var_2FC]
0x18001187a  mov     [rsp+418h+var_3C0], rax
0x18001187f  mov     [rsp+418h+var_3C8], 0
0x180011888  mov     [rsp+418h+var_3D0], 0
0x180011891  mov     [rsp+418h+var_3D8], 0
0x180011899  mov     [rsp+418h+var_3E0], 0
0x1800118a2  mov     [rsp+418h+var_3E8], 0
0x1800118ab  mov     [rsp+418h+var_3F0], rdx
0x1800118b0  mov     qword ptr [rsp+418h+var_3F8], rcx; int
0x1800118b5  mov     r9d, [rsi+38h]
0x1800118b9  xor     r8d, r8d
0x1800118bc  xor     edx, edx
0x1800118be  mov     rcx, r11
0x1800118c1  mov     rax, r10
0x1800118c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118c9  mov     ebx, eax
0x1800118cb  mov     rcx, [rsp+418h]; this
0x1800118d3  test    eax, eax
0x1800118d5  jns     short loc_1800118EB
0x1800118d7  mov     edx, 1A0h; void *
0x1800118dc  mov     r9d, eax; char *
0x1800118df  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\embedded\\shell\\iot"...
0x1800118e6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800118eb  mov     dword ptr [rsp+418h+var_3A0], ebx
0x1800118ef  test    ebx, ebx
0x1800118f1  jns     short loc_18001195C
0x1800118f3  mov     [rsp+418h+var_300], ebx
0x1800118fa  call    cs:__imp_GetTickCount64
0x180011900  mov     [rsp+418h+var_330], rax
0x180011908  mov     rax, [rsp+418h+var_310]
0x180011910  mov     [rsp+418h+var_398], rax
0x180011918  mov     rax, [rsp+418h+var_328]
0x180011920  test    rax, rax
0x180011923  jz      short loc_180011928
0x180011925  mov     rax, [rax]
0x180011928  mov     [rsp+418h+var_360], rax
0x180011930  lea     r8, [rsp+418h+var_3A0]
0x180011935  lea     rdx, [rsp+418h+var_398]
0x18001193d  lea     rcx, [rsp+418h+var_360]
0x180011945  call    ??$BackgroundTaskActivationFailed@PEAGPEAGAEAJ@CTelemetryProvider@ShellExtension@IoT@Microsoft@@SAX$$QEAPEAG0AEAJ@Z; Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskActivationFailed<ushort *,ushort *,long &>(ushort * &&,ushort * &&,long &)
0x18001194a  lea     rdx, [rsp+418h+var_338]; struct Microsoft::IoT::ShellExtension::CCBT *
0x180011952  mov     rcx, rsi; this
0x180011955  call    ?ReLaunch@CCBTLauncher@ShellExtension@IoT@Microsoft@@AEAAXAEAVCCBT@234@@Z; Microsoft::IoT::ShellExtension::CCBTLauncher::ReLaunch(Microsoft::IoT::ShellExtension::CCBT &)
0x18001195a  jmp     short loc_180011971
0x18001195c  lea     rcx, [rsi+0A0h]
0x180011963  lea     rdx, [rsp+418h+var_338]
0x18001196b  call    ??$_Emplace_one_at_back@VCCBT@ShellExtension@IoT@Microsoft@@@?$vector@VCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@AEAAAEAVCCBT@ShellExtension@IoT@Microsoft@@$$QEAV2345@@Z; std::vector<Microsoft::IoT::ShellExtension::CCBT>::_Emplace_one_at_back<Microsoft::IoT::ShellExtension::CCBT>(Microsoft::IoT::ShellExtension::CCBT &&)
0x180011970  nop
0x180011971  mov     [rsp+418h+var_350], 0
0x180011979  lea     rcx, [rsp+418h+var_2D8]
0x180011981  call    ?Stop@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180011986  nop
0x180011987  lea     rcx, [rsp+418h+var_2D8]; this
0x18001198f  call    ??1BackgroundTaskActivation@CTelemetryProvider@ShellExtension@IoT@Microsoft@@QEAA@XZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskActivation::~BackgroundTaskActivation(void)
0x180011994  jmp     loc_180011747
0x180011999  jmp     short loc_1800119A1
0x18001199b  jmp     short loc_1800119A1
0x18001199d  jmp     short loc_1800119A1
0x18001199f  jmp     short $+2
0x1800119a1  mov     rcx, [rsp+418h]; this
0x1800119a9  mov     r9d, dword ptr [rsp+418h+var_3A8]; char *
0x1800119ae  test    r9d, r9d
0x1800119b1  jns     short loc_1800119C5
0x1800119b3  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\embedded\\shell\\iot"...
0x1800119ba  mov     edx, 1B1h; void *
0x1800119bf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800119c4  nop
0x1800119c5  cmp     [rsp+418h+var_368], 0
0x1800119cd  jz      short loc_1800119DD
0x1800119cf  mov     rcx, [rsp+418h+var_370]
0x1800119d7  call    ?Stop@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800119dc  nop
0x1800119dd  lea     rcx, [rsp+418h+var_188]; this
0x1800119e5  call    ??1BackgroundTaskLaunch@CTelemetryProvider@ShellExtension@IoT@Microsoft@@QEAA@XZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskLaunch::~BackgroundTaskLaunch(void)
0x1800119ea  mov     eax, dword ptr [rsp+418h+var_3A8]
0x1800119ee  mov     rcx, [rsp+418h+var_18]
0x1800119f6  xor     rcx, rsp; StackCookie
0x1800119f9  call    __security_check_cookie
0x1800119fe  lea     r11, [rsp+418h+var_8]
0x180011a06  mov     rbx, [r11+18h]
0x180011a0a  mov     rsi, [r11+20h]
0x180011a0e  mov     rsp, r11
0x180011a11  pop     r14
0x180011a13  retn
```
