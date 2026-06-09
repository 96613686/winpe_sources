# Microsoft::IoT::ShellExtension::CCBTLauncher::CCBTLauncher(Microsoft::IoT::ShellExtension::ILauncherControl *,std::shared_ptr<Microsoft::IoT::Utility::MTAThreadPool> &,ulong,bool)

- ea: `0x18001029c`
- end: `0x1800103b5`
- name: `??0CCBTLauncher@ShellExtension@IoT@Microsoft@@QEAA@PEAUILauncherControl@123@AEAV?$shared_ptr@VMTAThreadPool@Utility@IoT@Microsoft@@@std@@K_N@Z`
- size: `281`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *, int, char)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000f4dc`

## callees

- `0x180007dd0`
- `0x18000a730`
- `0x18000c81c`
- `0x18000f440`
- `0x18000ff60`
- `0x18001029c`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180010320`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180010320`

## pseudocode

```c
__int64 __fastcall Microsoft::IoT::ShellExtension::CCBTLauncher::CCBTLauncher(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        int a4,
        char a5)
{
  __int64 v9; // rax
  _QWORD *v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v14; // [rsp+58h] [rbp+10h] BYREF
  __int64 v15; // [rsp+60h] [rbp+18h] BYREF
  int v16; // [rsp+68h] [rbp+20h] BYREF

  Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::FtmBase,IBackgroundSessionCallbacks>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::FtmBase,IBackgroundSessionCallbacks>();
  *(_QWORD *)a1 = &Microsoft::IoT::ShellExtension::CCBTLauncher::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IBackgroundSessionCallbacks>>'};
  *(_QWORD *)(a1 + 32) = &Microsoft::IoT::ShellExtension::CCBTLauncher::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IBackgroundSessionCallbacks>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IBackgroundSessionCallbacks>>'};
  *(_QWORD *)(a1 + 48) = a2;
  *(_DWORD *)(a1 + 56) = 0;
  v16 = 1;
  ____0W4EventOptions_wil____V___unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
    a1 + 64,
    &v16);
  *(_QWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  v9 = a3[1];
  if ( v9 )
    _InterlockedIncrement((volatile signed __int32 *)(v9 + 8));
  *(_QWORD *)(a1 + 72) = *a3;
  *(_QWORD *)(a1 + 80) = a3[1];
  *(_QWORD *)(a1 + 88) = 0;
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(a1 + 96), 0, 0);
  std::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>(a1 + 136);
  std::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>(a1 + 160);
  *(_DWORD *)(a1 + 184) = a4;
  *(_QWORD *)(a1 + 192) = 0;
  v15 = a1;
  v10 = (_QWORD *)Microsoft::WRL::Details::Make<Microsoft::IoT::ShellExtension::CCBTBackgroundSessionCallbacks,Microsoft::IoT::ShellExtension::CCBTLauncher *>(
                    &v14,
                    &v15);
  v11 = (*v10 + 32LL) & -(__int64)(*v10 != 0);
  *(_QWORD *)(a1 + 200) = v11;
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
  v12 = v14;
  if ( v14 )
  {
    v14 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::FtmBase,Microsoft::IoT::ShellExtension::ILauncherControl>::Release(v12);
  }
  *(_BYTE *)(a1 + 208) = a5;
  *(_BYTE *)(a1 + 209) = 0;
  return a1;
}

```

## disassembly

```asm
0x18001029c  mov     [rsp+arg_0], rcx
0x1800102a1  push    rbx
0x1800102a2  push    rbp
0x1800102a3  push    rsi
0x1800102a4  push    rdi
0x1800102a5  sub     rsp, 28h
0x1800102a9  mov     ebp, r9d
0x1800102ac  mov     rsi, r8
0x1800102af  mov     rbx, rdx
0x1800102b2  mov     rdi, rcx
0x1800102b5  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@VFtmBase@23@UIBackgroundSessionCallbacks@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::FtmBase,IBackgroundSessionCallbacks>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::FtmBase,IBackgroundSessionCallbacks>(void)
0x1800102ba  nop
0x1800102bb  lea     rax, ??_7CCBTLauncher@ShellExtension@IoT@Microsoft@@6B?$Selector@VFtmBase@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIBackgroundSessionCallbacks@@@Details@23@@Details@WRL@3@@; const Microsoft::IoT::ShellExtension::CCBTLauncher::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IBackgroundSessionCallbacks>>'}
0x1800102c2  mov     [rdi], rax
0x1800102c5  lea     rax, ??_7CCBTLauncher@ShellExtension@IoT@Microsoft@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIBackgroundSessionCallbacks@@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIBackgroundSessionCallbacks@@@234@@Details@WRL@3@@; const Microsoft::IoT::ShellExtension::CCBTLauncher::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IBackgroundSessionCallbacks>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IBackgroundSessionCallbacks>>'}
0x1800102cc  mov     [rdi+20h], rax
0x1800102d0  mov     [rdi+30h], rbx
0x1800102d4  xor     ebx, ebx
0x1800102d6  mov     [rdi+38h], ebx
0x1800102d9  mov     [rsp+48h+arg_18], 1
0x1800102e1  lea     rcx, [rdi+40h]
0x1800102e5  lea     rdx, [rsp+48h+arg_18]
0x1800102ea  call    ??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x1800102ef  mov     [rdi+48h], rbx
0x1800102f3  mov     [rdi+50h], rbx
0x1800102f7  mov     rax, [rsi+8]
0x1800102fb  test    rax, rax
0x1800102fe  jz      short loc_180010304
0x180010300  lock inc dword ptr [rax+8]
0x180010304  mov     rax, [rsi]
0x180010307  mov     [rdi+48h], rax
0x18001030b  mov     rax, [rsi+8]
0x18001030f  mov     [rdi+50h], rax
0x180010313  mov     [rdi+58h], rbx
0x180010317  lea     rcx, [rdi+60h]; lpCriticalSection
0x18001031b  xor     r8d, r8d; Flags
0x18001031e  xor     edx, edx; dwSpinCount
0x180010320  call    cs:__imp_InitializeCriticalSectionEx
0x180010326  lea     rcx, [rdi+88h]
0x18001032d  call    ??0?$vector@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>(void)
0x180010332  lea     rcx, [rdi+0A0h]
0x180010339  call    ??0?$vector@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>(void)
0x18001033e  mov     [rdi+0B8h], ebp
0x180010344  mov     [rdi+0C0h], rbx
0x18001034b  mov     [rsp+48h+arg_10], rdi
0x180010350  lea     rdx, [rsp+48h+arg_10]
0x180010355  lea     rcx, [rsp+48h+arg_8]
0x18001035a  call    ??$Make@VCCBTBackgroundSessionCallbacks@ShellExtension@IoT@Microsoft@@PEAVCCBTLauncher@234@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCCBTBackgroundSessionCallbacks@ShellExtension@IoT@Microsoft@@@12@$$QEAPEAVCCBTLauncher@ShellExtension@IoT@2@@Z; Microsoft::WRL::Details::Make<Microsoft::IoT::ShellExtension::CCBTBackgroundSessionCallbacks,Microsoft::IoT::ShellExtension::CCBTLauncher *>(Microsoft::IoT::ShellExtension::CCBTLauncher * &&)
0x18001035f  mov     rcx, [rax]
0x180010362  lea     rax, [rcx+20h]
0x180010366  neg     rcx
0x180010369  sbb     rcx, rcx
0x18001036c  and     rcx, rax
0x18001036f  mov     [rdi+0C8h], rcx
0x180010376  jz      short loc_180010385
0x180010378  mov     rax, [rcx]
0x18001037b  mov     rax, [rax+8]
0x18001037f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010384  nop
0x180010385  mov     rcx, [rsp+48h+arg_8]
0x18001038a  test    rcx, rcx
0x18001038d  jz      short loc_180010399
0x18001038f  mov     [rsp+48h+arg_8], rbx
0x180010394  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@VFtmBase@23@UILauncherControl@ShellExtension@IoT@3@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::FtmBase,Microsoft::IoT::ShellExtension::ILauncherControl>::Release(void)
0x180010399  mov     al, [rsp+48h+arg_20]
0x18001039d  mov     [rdi+0D0h], al
0x1800103a3  mov     [rdi+0D1h], bl
0x1800103a9  mov     rax, rdi
0x1800103ac  add     rsp, 28h
0x1800103b0  pop     rdi
0x1800103b1  pop     rsi
0x1800103b2  pop     rbp
0x1800103b3  pop     rbx
0x1800103b4  retn
```
