# Osf::OsfQuickCheckManager::IsHighCostNetwork(void)

- ea: `0x18028f840`
- end: `0x18028fb4e`
- name: `?IsHighCostNetwork@OsfQuickCheckManager@Osf@@SA_NXZ`
- size: `782`
- prototype: `static bool(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18029cbd0`

## callees

- `0x18004e790`
- `0x18005815c`
- `0x1800581b0`
- `0x18028ee60`
- `0x18028f840`
- `0x18028fb50`
- `0x18028fca8`
- `0x1802ad37c`
- `0x1802e5170`
- `0x1802e5190`

## import_xrefs

- `Mso30Win32Client!__imp_?MsoGetRemoteHostNetworkStatus@ServerReachability@Mso@@YAXPEB_WPEAPEAUIRemoteHostNetworkStatus@Csi@@@Z` at `0x18028f8aa`
- `Mso30Win32Client!__imp_?MsoGetRemoteHostNetworkStatus@ServerReachability@Mso@@YAXPEB_WPEAPEAUIRemoteHostNetworkStatus@Csi@@@Z` at `0x18028f8aa`
- `Mso30Win32Client!__imp_?GetServiceUrlForGlobalEnv@OfficeWebServiceApi@Mso@@YA?AW4Flags@Status@12@VMsoReserveTag@@W4URL@ConfigURL@12@PEA_WI@Z` at `0x18028f88a`
- `Mso30Win32Client!__imp_?GetServiceUrlForGlobalEnv@OfficeWebServiceApi@Mso@@YA?AW4Flags@Status@12@VMsoReserveTag@@W4URL@ConfigURL@12@PEA_WI@Z` at `0x18028f88a`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18028f90c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18028f90c`
- `Mso20Win32Client!__imp_?Optional@Executor@Futures@Mso@@QEAA?AUOptionalExecutor@23@XZ` at `0x18028fa31`
- `Mso20Win32Client!__imp_?Optional@Executor@Futures@Mso@@QEAA?AUOptionalExecutor@23@XZ` at `0x18028fa31`
- `Mso20Win32Client!__imp_?Cancel@CancellationTokenSource@Mso@@QEBAXXZ` at `0x18028fb25`
- `Mso20Win32Client!__imp_?Cancel@CancellationTokenSource@Mso@@QEBAXXZ` at `0x18028fb25`
- `Mso20Win32Client!__imp_??0CancellationToken@Mso@@QEAA@AEBV01@@Z` at `0x18028f8f0`
- `Mso20Win32Client!__imp_??0CancellationToken@Mso@@QEAA@AEBV01@@Z` at `0x18028f9aa`
- `Mso20Win32Client!__imp_??0CancellationToken@Mso@@QEAA@AEBV01@@Z` at `0x18028fa18`
- `Mso20Win32Client!__imp_??0CancellationToken@Mso@@QEAA@AEBV01@@Z` at `0x18028f8f0`
- `Mso20Win32Client!__imp_??0CancellationToken@Mso@@QEAA@AEBV01@@Z` at `0x18028f9aa`
- `Mso20Win32Client!__imp_??0CancellationToken@Mso@@QEAA@AEBV01@@Z` at `0x18028fa18`
- `Mso20Win32Client!__imp_??0CancellationTokenSource@Mso@@QEAA@XZ` at `0x18028f8d7`
- `Mso20Win32Client!__imp_??0CancellationTokenSource@Mso@@QEAA@XZ` at `0x18028f8d7`
- `Mso20Win32Client!__imp_?SimpleWaitInternal@Details@Synchronization@Mso@@YA_NPEAXK_N1@Z` at `0x18028faad`
- `Mso20Win32Client!__imp_?SimpleWaitInternal@Details@Synchronization@Mso@@YA_NPEAXK_N1@Z` at `0x18028faad`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x18028fb42`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x18028fb42`
- `Mso20Win32Client!__imp_?GetToken@CancellationTokenSource@Mso@@QEBAAEBVCancellationToken@2@XZ` at `0x18028f8e2`
- `Mso20Win32Client!__imp_?GetToken@CancellationTokenSource@Mso@@QEBAAEBVCancellationToken@2@XZ` at `0x18028f8e2`

## pseudocode

```c
char __fastcall Osf::OsfQuickCheckManager::IsHighCostNetwork()
{
  std::_Ref_count_base *v0; // rbx
  struct Csi::IRemoteHostNetworkStatus **v1; // r8
  const struct Mso::CancellationToken *Token; // rax
  std::_Ref_count_base *v3; // rdi
  std::_Ref_count_base *v4; // rcx
  void (__fastcall *v6)(std::_Ref_count_base *, _BYTE *, __int64); // rbx
  __int64 v7; // rax
  Mso::Synchronization::Details **v8; // rsi
  _DWORD *v9; // r14
  __int64 v10; // rax
  __int64 v11; // rcx
  std::_Ref_count_base *v12; // rcx
  _BOOL8 v13; // [rsp+20h] [rbp-E0h] BYREF
  std::_Ref_count_base *v14; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v15; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v16[8]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v17[8]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v18[8]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v19; // [rsp+50h] [rbp-B0h] BYREF
  Mso::Synchronization::Details **v20; // [rsp+58h] [rbp-A8h] BYREF
  std::_Ref_count_base *v21; // [rsp+60h] [rbp-A0h]
  _QWORD v22[2]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v23[2]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v24[8]; // [rsp+88h] [rbp-78h] BYREF
  _DWORD *v25; // [rsp+90h] [rbp-70h] BYREF
  std::_Ref_count_base *v26; // [rsp+98h] [rbp-68h]
  _BYTE v27[4176]; // [rsp+A0h] [rbp-60h] BYREF

  if ( (unsigned int)Mso::OfficeWebServiceApi::GetServiceUrlForGlobalEnv(509151446, 0, v27, 2084) )
    return 0;
  v14 = 0;
  Mso::ServerReachability::MsoGetRemoteHostNetworkStatus((Mso::ServerReachability *)v27, (const wchar_t *)&v14, v1);
  if ( !v14 )
    return 0;
  LODWORD(v15) = 0;
  std::make_shared<enum Csi::NetworkCost,enum Csi::NetworkCost>(&v25, &v15);
  Mso::CancellationTokenSource::CancellationTokenSource((Mso::CancellationTokenSource *)v17);
  Token = Mso::CancellationTokenSource::GetToken((Mso::CancellationTokenSource *)v17);
  Mso::CancellationToken::CancellationToken((Mso::CancellationToken *)v16, Token);
  v3 = v14;
  if ( !v14 )
  {
    CrashWithRecovery(0x1E3C3840u, 0);
LABEL_5:
    if ( v3 )
      std::_Ref_count_base::_Decref(v3);
    Mso::Functor<void (IOsfControlContainer *,unsigned __int64)>::~Functor<void (IOsfControlContainer *,unsigned __int64)>(v18);
    Mso::Functor<void (IOsfControlContainer *,unsigned __int64)>::~Functor<void (IOsfControlContainer *,unsigned __int64)>(v16);
    Mso::Functor<void (IOsfControlContainer *,unsigned __int64)>::~Functor<void (IOsfControlContainer *,unsigned __int64)>(v17);
    if ( v0 )
      std::_Ref_count_base::_Decref(v0);
    v4 = v14;
    if ( v14 )
    {
      v14 = 0;
      (*(void (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v4 + 16LL))(v4);
    }
    return 0;
  }
  v6 = *(void (__fastcall **)(std::_Ref_count_base *, _BYTE *, __int64))(*(_QWORD *)v14 + 72LL);
  v7 = Mso::CancellationToken::CancellationToken(
         (Mso::CancellationToken *)&v19,
         (const struct Mso::CancellationToken *)v16);
  v6(v3, v18, v7);
  LOBYTE(v13) = 1;
  std::make_shared<Mso::Synchronization::SimpleEvent,bool>(&v20, &v13);
  v3 = v21;
  if ( v21 )
    _InterlockedIncrement((volatile signed __int32 *)v21 + 2);
  v8 = v20;
  v22[0] = v20;
  v22[1] = v3;
  v0 = v26;
  if ( v26 )
    _InterlockedIncrement((volatile signed __int32 *)v26 + 2);
  v9 = v25;
  v23[0] = v25;
  v23[1] = v0;
  Mso::CancellationToken::CancellationToken((Mso::CancellationToken *)v24, (const struct Mso::CancellationToken *)v16);
  v15 = 0;
  v10 = Mso::Futures::Executor::Optional(&v15, &v19);
  sub_18028FB50(v18, &v20, v10, v22);
  Mso::Functor<void (IOsfControlContainer *,unsigned __int64)>::~Functor<void (IOsfControlContainer *,unsigned __int64)>(&v20);
  Mso::Functor<void (IOsfControlContainer *,unsigned __int64)>::~Functor<void (IOsfControlContainer *,unsigned __int64)>(&v19);
  v11 = v15;
  if ( v15 )
  {
    v15 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  Mso::Functor<void (IOsfControlContainer *,unsigned __int64)>::~Functor<void (IOsfControlContainer *,unsigned __int64)>(v24);
  std::shared_ptr<xpsrdr::SourceColorBitmap>::~shared_ptr<xpsrdr::SourceColorBitmap>(v23);
  std::shared_ptr<xpsrdr::SourceColorBitmap>::~shared_ptr<xpsrdr::SourceColorBitmap>(v22);
  if ( !Mso::Synchronization::Details::SimpleWaitInternal(*v8, (void *)0x1388, 0, 0, v13) )
  {
    Mso::CancellationTokenSource::Cancel((Mso::CancellationTokenSource *)v17);
    Mso::Logging::MsoSendStructuredTraceTag(
      22859873,
      324,
      15,
      L"IsHighCostNetwork - Timeout while checking network cost");
  }
  if ( *v9 != 2 )
    goto LABEL_5;
  if ( v3 )
    std::_Ref_count_base::_Decref(v3);
  Mso::Functor<void (IOsfControlContainer *,unsigned __int64)>::~Functor<void (IOsfControlContainer *,unsigned __int64)>(v18);
  Mso::Functor<void (IOsfControlContainer *,unsigned __int64)>::~Functor<void (IOsfControlContainer *,unsigned __int64)>(v16);
  Mso::Functor<void (IOsfControlContainer *,unsigned __int64)>::~Functor<void (IOsfControlContainer *,unsigned __int64)>(v17);
  if ( v0 )
    std::_Ref_count_base::_Decref(v0);
  v12 = v14;
  if ( v14 )
  {
    v14 = 0;
    (*(void (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v12 + 16LL))(v12);
  }
  return 1;
}

```

## disassembly

```asm
0x18028f840  mov     rax, rsp
0x18028f843  mov     [rax+8], rbx
0x18028f847  mov     [rax+10h], rsi
0x18028f84b  mov     [rax+18h], rdi
0x18028f84f  mov     [rax+20h], r14
0x18028f853  push    rbp
0x18028f854  lea     rbp, [rax-1008h]
0x18028f85b  mov     eax, 1100h
0x18028f860  call    _alloca_probe
0x18028f865  sub     rsp, rax
0x18028f868  mov     rax, cs:__security_cookie
0x18028f86f  xor     rax, rsp
0x18028f872  mov     [rbp+1000h+var_10], rax
0x18028f879  mov     r9d, 824h
0x18028f87f  lea     r8, [rbp+1000h+var_1060]
0x18028f883  xor     edx, edx
0x18028f885  mov     ecx, 1E5908D6h
0x18028f88a  call    cs:__imp_?GetServiceUrlForGlobalEnv@OfficeWebServiceApi@Mso@@YA?AW4Flags@Status@12@VMsoReserveTag@@W4URL@ConfigURL@12@PEA_WI@Z; Mso::OfficeWebServiceApi::GetServiceUrlForGlobalEnv(MsoReserveTag,Mso::OfficeWebServiceApi::ConfigURL::URL,wchar_t *,uint)
0x18028f890  test    eax, eax
0x18028f892  jnz     loc_18028F96B
0x18028f898  mov     [rsp+1100h+var_10D8], 0
0x18028f8a1  lea     rdx, [rsp+1100h+var_10D8]
0x18028f8a6  lea     rcx, [rbp+1000h+var_1060]
0x18028f8aa  call    cs:__imp_?MsoGetRemoteHostNetworkStatus@ServerReachability@Mso@@YAXPEB_WPEAPEAUIRemoteHostNetworkStatus@Csi@@@Z; Mso::ServerReachability::MsoGetRemoteHostNetworkStatus(wchar_t const *,Csi::IRemoteHostNetworkStatus * *)
0x18028f8b0  cmp     [rsp+1100h+var_10D8], 0
0x18028f8b6  jz      loc_18028F96B
0x18028f8bc  mov     dword ptr [rsp+1100h+var_10D0], 0
0x18028f8c4  lea     rdx, [rsp+1100h+var_10D0]
0x18028f8c9  lea     rcx, [rbp+1000h+var_1070]
0x18028f8cd  call    ??$make_shared@W4NetworkCost@Csi@@W412@@std@@YA?AV?$shared_ptr@W4NetworkCost@Csi@@@0@$$QEAW4NetworkCost@Csi@@@Z; std::make_shared<Csi::NetworkCost,Csi::NetworkCost>(Csi::NetworkCost &&)
0x18028f8d2  lea     rcx, [rsp+1100h+var_10C0]
0x18028f8d7  call    cs:__imp_??0CancellationTokenSource@Mso@@QEAA@XZ; Mso::CancellationTokenSource::CancellationTokenSource(void)
0x18028f8dd  lea     rcx, [rsp+1100h+var_10C0]
0x18028f8e2  call    cs:__imp_?GetToken@CancellationTokenSource@Mso@@QEBAAEBVCancellationToken@2@XZ; Mso::CancellationTokenSource::GetToken(void)
0x18028f8e8  mov     rdx, rax
0x18028f8eb  lea     rcx, [rsp+1100h+var_10C8]
0x18028f8f0  call    cs:__imp_??0CancellationToken@Mso@@QEAA@AEBV01@@Z; Mso::CancellationToken::CancellationToken(Mso::CancellationToken const &)
0x18028f8f6  nop
0x18028f8f7  mov     rdi, [rsp+1100h+var_10D8]
0x18028f8fc  test    rdi, rdi
0x18028f8ff  jnz     loc_18028F999
0x18028f905  xor     edx, edx
0x18028f907  mov     ecx, 1E3C3840h
0x18028f90c  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18028f912  nop
0x18028f913  test    rdi, rdi
0x18028f916  jz      short loc_18028F920
0x18028f918  mov     rcx, rdi; this
0x18028f91b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18028f920  lea     rcx, [rsp+1100h+var_10B8]
0x18028f925  call    ??1?$Functor@$$A6AXPEAUIOsfControlContainer@@_K@Z@Mso@@QEAA@XZ; Mso::Functor<void (IOsfControlContainer *,unsigned __int64)>::~Functor<void (IOsfControlContainer *,unsigned __int64)>(void)
0x18028f92a  lea     rcx, [rsp+1100h+var_10C8]
0x18028f92f  call    ??1?$Functor@$$A6AXPEAUIOsfControlContainer@@_K@Z@Mso@@QEAA@XZ; Mso::Functor<void (IOsfControlContainer *,unsigned __int64)>::~Functor<void (IOsfControlContainer *,unsigned __int64)>(void)
0x18028f934  lea     rcx, [rsp+1100h+var_10C0]
0x18028f939  call    ??1?$Functor@$$A6AXPEAUIOsfControlContainer@@_K@Z@Mso@@QEAA@XZ; Mso::Functor<void (IOsfControlContainer *,unsigned __int64)>::~Functor<void (IOsfControlContainer *,unsigned __int64)>(void)
0x18028f93e  test    rbx, rbx
0x18028f941  jz      short loc_18028F94B
0x18028f943  mov     rcx, rbx; this
0x18028f946  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18028f94b  mov     rcx, [rsp+1100h+var_10D8]
0x18028f950  test    rcx, rcx
0x18028f953  jz      short loc_18028F96B
0x18028f955  mov     [rsp+1100h+var_10D8], 0
0x18028f95e  mov     rax, [rcx]
0x18028f961  mov     rax, [rax+10h]
0x18028f965  call    cs:__guard_dispatch_icall_fptr
0x18028f96b  xor     al, al
0x18028f96d  mov     rcx, [rbp+1000h+var_10]
0x18028f974  xor     rcx, rsp; StackCookie
0x18028f977  call    __security_check_cookie
0x18028f97c  lea     r11, [rsp+1100h+var_s0]
0x18028f984  mov     rbx, [r11+10h]
0x18028f988  mov     rsi, [r11+18h]
0x18028f98c  mov     rdi, [r11+20h]
0x18028f990  mov     r14, [r11+28h]
0x18028f994  mov     rsp, r11
0x18028f997  pop     rbp
0x18028f998  retn
0x18028f999  mov     rax, [rdi]
0x18028f99c  mov     rbx, [rax+48h]
0x18028f9a0  lea     rdx, [rsp+1100h+var_10C8]
0x18028f9a5  lea     rcx, [rsp+1100h+var_10B0]
0x18028f9aa  call    cs:__imp_??0CancellationToken@Mso@@QEAA@AEBV01@@Z; Mso::CancellationToken::CancellationToken(Mso::CancellationToken const &)
0x18028f9b0  mov     r8, rax
0x18028f9b3  lea     rdx, [rsp+1100h+var_10B8]
0x18028f9b8  mov     rcx, rdi
0x18028f9bb  mov     rax, rbx
0x18028f9be  call    cs:__guard_dispatch_icall_fptr
0x18028f9c4  mov     byte ptr [rsp+1100h+var_10E0], 1
0x18028f9c9  lea     rdx, [rsp+1100h+var_10E0]
0x18028f9ce  lea     rcx, [rsp+1100h+var_10A8]
0x18028f9d3  call    ??$make_shared@VSimpleEvent@Synchronization@Mso@@_N@std@@YA?AV?$shared_ptr@VSimpleEvent@Synchronization@Mso@@@0@$$QEA_N@Z; std::make_shared<Mso::Synchronization::SimpleEvent,bool>(bool &&)
0x18028f9d8  mov     rdi, [rsp+1100h+var_10A0]
0x18028f9dd  test    rdi, rdi
0x18028f9e0  jz      short loc_18028F9E6
0x18028f9e2  lock inc dword ptr [rdi+8]
0x18028f9e6  mov     rsi, [rsp+1100h+var_10A8]
0x18028f9eb  mov     [rsp+1100h+var_1098], rsi
0x18028f9f0  mov     [rsp+1100h+var_1090], rdi
0x18028f9f5  mov     rbx, [rbp+1000h+var_1068]
0x18028f9f9  test    rbx, rbx
0x18028f9fc  jz      short loc_18028FA02
0x18028f9fe  lock inc dword ptr [rbx+8]
0x18028fa02  mov     r14, [rbp+1000h+var_1070]
0x18028fa06  mov     [rsp+1100h+var_1088], r14
0x18028fa0b  mov     [rbp+1000h+var_1080], rbx
0x18028fa0f  lea     rdx, [rsp+1100h+var_10C8]
0x18028fa14  lea     rcx, [rbp+1000h+var_1078]
0x18028fa18  call    cs:__imp_??0CancellationToken@Mso@@QEAA@AEBV01@@Z; Mso::CancellationToken::CancellationToken(Mso::CancellationToken const &)
0x18028fa1e  mov     [rsp+1100h+var_10D0], 0
0x18028fa27  lea     rdx, [rsp+1100h+var_10B0]
0x18028fa2c  lea     rcx, [rsp+1100h+var_10D0]
0x18028fa31  call    cs:__imp_?Optional@Executor@Futures@Mso@@QEAA?AUOptionalExecutor@23@XZ; Mso::Futures::Executor::Optional(void)
0x18028fa37  lea     r9, [rsp+1100h+var_1098]
0x18028fa3c  mov     r8, rax
0x18028fa3f  lea     rdx, [rsp+1100h+var_10A8]
0x18028fa44  lea     rcx, [rsp+1100h+var_10B8]
0x18028fa49  call    sub_18028FB50
0x18028fa4e  lea     rcx, [rsp+1100h+var_10A8]
0x18028fa53  call    ??1?$Functor@$$A6AXPEAUIOsfControlContainer@@_K@Z@Mso@@QEAA@XZ; Mso::Functor<void (IOsfControlContainer *,unsigned __int64)>::~Functor<void (IOsfControlContainer *,unsigned __int64)>(void)
0x18028fa58  lea     rcx, [rsp+1100h+var_10B0]
0x18028fa5d  call    ??1?$Functor@$$A6AXPEAUIOsfControlContainer@@_K@Z@Mso@@QEAA@XZ; Mso::Functor<void (IOsfControlContainer *,unsigned __int64)>::~Functor<void (IOsfControlContainer *,unsigned __int64)>(void)
0x18028fa62  mov     rcx, [rsp+1100h+var_10D0]
0x18028fa67  test    rcx, rcx
0x18028fa6a  jz      short loc_18028FA82
0x18028fa6c  mov     [rsp+1100h+var_10D0], 0
0x18028fa75  mov     rax, [rcx]
0x18028fa78  mov     rax, [rax+10h]
0x18028fa7c  call    cs:__guard_dispatch_icall_fptr
0x18028fa82  lea     rcx, [rbp+1000h+var_1078]
0x18028fa86  call    ??1?$Functor@$$A6AXPEAUIOsfControlContainer@@_K@Z@Mso@@QEAA@XZ; Mso::Functor<void (IOsfControlContainer *,unsigned __int64)>::~Functor<void (IOsfControlContainer *,unsigned __int64)>(void)
0x18028fa8b  lea     rcx, [rsp+1100h+var_1088]; void *
0x18028fa90  call    ??1?$shared_ptr@USourceColorBitmap@xpsrdr@@@std@@QEAA@XZ; std::shared_ptr<xpsrdr::SourceColorBitmap>::~shared_ptr<xpsrdr::SourceColorBitmap>(void)
0x18028fa95  lea     rcx, [rsp+1100h+var_1098]; void *
0x18028fa9a  call    ??1?$shared_ptr@USourceColorBitmap@xpsrdr@@@std@@QEAA@XZ; std::shared_ptr<xpsrdr::SourceColorBitmap>::~shared_ptr<xpsrdr::SourceColorBitmap>(void)
0x18028fa9f  xor     r9d, r9d
0x18028faa2  xor     r8d, r8d
0x18028faa5  mov     edx, 1388h
0x18028faaa  mov     rcx, [rsi]
0x18028faad  call    cs:__imp_?SimpleWaitInternal@Details@Synchronization@Mso@@YA_NPEAXK_N1@Z; Mso::Synchronization::Details::SimpleWaitInternal(void *,ulong,bool,bool)
0x18028fab3  test    al, al
0x18028fab5  jz      short loc_18028FB20
0x18028fab7  cmp     dword ptr [r14], 2
0x18028fabb  jnz     loc_18028F913
0x18028fac1  test    rdi, rdi
0x18028fac4  jz      short loc_18028FACE
0x18028fac6  mov     rcx, rdi; this
0x18028fac9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18028face  lea     rcx, [rsp+1100h+var_10B8]
0x18028fad3  call    ??1?$Functor@$$A6AXPEAUIOsfControlContainer@@_K@Z@Mso@@QEAA@XZ; Mso::Functor<void (IOsfControlContainer *,unsigned __int64)>::~Functor<void (IOsfControlContainer *,unsigned __int64)>(void)
0x18028fad8  lea     rcx, [rsp+1100h+var_10C8]
0x18028fadd  call    ??1?$Functor@$$A6AXPEAUIOsfControlContainer@@_K@Z@Mso@@QEAA@XZ; Mso::Functor<void (IOsfControlContainer *,unsigned __int64)>::~Functor<void (IOsfControlContainer *,unsigned __int64)>(void)
0x18028fae2  lea     rcx, [rsp+1100h+var_10C0]
0x18028fae7  call    ??1?$Functor@$$A6AXPEAUIOsfControlContainer@@_K@Z@Mso@@QEAA@XZ; Mso::Functor<void (IOsfControlContainer *,unsigned __int64)>::~Functor<void (IOsfControlContainer *,unsigned __int64)>(void)
0x18028faec  test    rbx, rbx
0x18028faef  jz      short loc_18028FAF9
0x18028faf1  mov     rcx, rbx; this
0x18028faf4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18028faf9  mov     rcx, [rsp+1100h+var_10D8]
0x18028fafe  test    rcx, rcx
0x18028fb01  jz      short loc_18028FB19
0x18028fb03  mov     [rsp+1100h+var_10D8], 0
0x18028fb0c  mov     rdx, [rcx]
0x18028fb0f  mov     rax, [rdx+10h]
0x18028fb13  call    cs:__guard_dispatch_icall_fptr
0x18028fb19  mov     al, 1
0x18028fb1b  jmp     loc_18028F96D
0x18028fb20  lea     rcx, [rsp+1100h+var_10C0]
0x18028fb25  call    cs:__imp_?Cancel@CancellationTokenSource@Mso@@QEBAXXZ; Mso::CancellationTokenSource::Cancel(void)
0x18028fb2b  lea     r9, aIshighcostnetw; "IsHighCostNetwork - Timeout while check"...
0x18028fb32  mov     edx, 144h
0x18028fb37  mov     r8d, 0Fh
0x18028fb3d  mov     ecx, 15CD061h
0x18028fb42  call    cs:__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z; Mso::Logging::MsoSendStructuredTraceTag(ulong,Mso::Logging::Category,Mso::Logging::Severity,wchar_t const *)
0x18028fb48  jmp     loc_18028FAB7
```
