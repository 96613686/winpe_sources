# Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Windows::Internal::ApplicationModel::WindowManagement::WindowId &>(Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext * *,Windows::Internal::ApplicationModel::WindowManagement::WindowId &)

- ea: `0x1800076a4`
- end: `0x180007754`
- name: `??$MakeAndInitialize@VActivationFactoryContractRedirectorContext@Details@PlatformExtensions@Internal@Windows@@UIActivationFactoryContractRedirectorContext@Contracts@Foundation@45@AEAUWindowId@WindowManagement@ApplicationModel@45@@Details@WRL@Microsoft@@YAJPEAPEAUIActivationFactoryContractRedirectorContext@Contracts@Foundation@Internal@Windows@@AEAUWindowId@WindowManagement@ApplicationModel@67@@Z`
- size: `176`
- prototype: `__int64 __fastcall(_QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000e11c`

## callees

- `0x180006354`
- `0x180007484`
- `0x1800076a4`
- `0x1800082fc`
- `0x1800087fc`
- `0x18000c5f0`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Windows::Internal::ApplicationModel::WindowManagement::WindowId &>(
        _QWORD *a1,
        _DWORD *a2)
{
  Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext *v4; // rax
  unsigned int v5; // edi
  __int64 v6; // rbx
  Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext *v8; // [rsp+30h] [rbp+8h] BYREF
  __int64 v9; // [rsp+40h] [rbp+18h]

  *a1 = 0;
  v8 = 0;
  v4 = (Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext *)operator new(0x48u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v4;
  if ( v4 )
  {
    v6 = Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext::ActivationFactoryContractRedirectorContext(v4);
    v9 = v6;
    v8 = 0;
    *(_DWORD *)(v6 + 68) = *a2;
    v5 = Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Microsoft::WRL::FtmBase>>(
           v6,
           &GUID_7d6e17e4_e332_45e3_a8c9_b7291a38c23b,
           a1);
    v9 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Microsoft::WRL::FtmBase>::Release(v6);
  }
  else
  {
    v5 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext>::~MakeAllocator<Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext>(&v8);
  return v5;
}

```

## disassembly

```asm
0x1800076a4  mov     [rsp+arg_8], rbx
0x1800076a9  mov     [rsp+arg_18], rsi
0x1800076ae  push    rdi
0x1800076af  sub     rsp, 20h
0x1800076b3  mov     rsi, rdx
0x1800076b6  mov     rdi, rcx
0x1800076b9  mov     qword ptr [rcx], 0
0x1800076c0  mov     [rsp+28h+arg_0], 0
0x1800076c9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800076d0  mov     ecx, 48h ; 'H'; unsigned __int64
0x1800076d5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800076da  mov     [rsp+28h+arg_0], rax
0x1800076df  test    rax, rax
0x1800076e2  jnz     short loc_1800076EB
0x1800076e4  mov     edi, 8007000Eh
0x1800076e9  jmp     short loc_180007738
0x1800076eb  mov     rcx, rax; this
0x1800076ee  call    ??0ActivationFactoryContractRedirectorContext@Details@PlatformExtensions@Internal@Windows@@QEAA@XZ; Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext::ActivationFactoryContractRedirectorContext(void)
0x1800076f3  mov     rbx, rax
0x1800076f6  mov     [rsp+28h+arg_10], 0
0x1800076ff  mov     [rsp+28h+arg_10], rax
0x180007704  mov     [rsp+28h+arg_0], 0
0x18000770d  mov     ecx, [rsi]
0x18000770f  mov     [rax+44h], ecx
0x180007712  mov     r8, rdi
0x180007715  lea     rdx, _GUID_7d6e17e4_e332_45e3_a8c9_b7291a38c23b
0x18000771c  mov     rcx, rax
0x18000771f  call    ??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIActivationFactoryContractRedirectorContext@Contracts@Foundation@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$02@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIActivationFactoryContractRedirectorContext@Contracts@Foundation@Internal@Windows@@VFtmBase@23@@123@AEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Microsoft::WRL::FtmBase> *,_GUID const &,void * *)
0x180007724  mov     edi, eax
0x180007726  mov     [rsp+28h+arg_10], 0
0x18000772f  mov     rcx, rbx
0x180007732  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIActivationFactoryContractRedirectorContext@Contracts@Foundation@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Microsoft::WRL::FtmBase>::Release(void)
0x180007737  nop
0x180007738  lea     rcx, [rsp+28h+arg_0]
0x18000773d  call    ??1?$MakeAllocator@VActivationFactoryContractRedirectorContext@Details@PlatformExtensions@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext>::~MakeAllocator<Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext>(void)
0x180007742  mov     eax, edi
0x180007744  mov     rbx, [rsp+28h+arg_8]
0x180007749  mov     rsi, [rsp+28h+arg_18]
0x18000774e  add     rsp, 20h
0x180007752  pop     rdi
0x180007753  retn
```
