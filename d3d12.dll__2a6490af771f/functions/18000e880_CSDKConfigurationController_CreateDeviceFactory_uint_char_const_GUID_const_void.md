# CSDKConfigurationController::CreateDeviceFactory(uint,char const *,_GUID const &,void * *)

- ea: `0x18000e880`
- end: `0x18000e92b`
- name: `?CreateDeviceFactory@CSDKConfigurationController@@UEAAJIPEBDAEBU_GUID@@PEAPEAX@Z`
- size: `171`
- prototype: `int(CSDKConfigurationController *__hidden this, unsigned int, const char *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000670c`
- `0x18000ad90`
- `0x18000afcc`
- `0x18000afec`
- `0x18000e880`
- `0x18000eee8`
- `0x18000fdc4`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall CSDKConfigurationController::CreateDeviceFactory(
        CSDKConfigurationController *this,
        __int64 a2,
        const char *a3,
        const struct _GUID *a4,
        void **a5)
{
  unsigned int v7; // edi
  struct D3DCoreModule *ExplicitModule; // rax
  struct D3DCoreModule *v9; // rdi
  int v10; // ebx

  v7 = a2;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12IndependentDevices>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_D3D12IndependentDevices>::GetImpl'::`2'::impl,
    a2);
  Smtx_lock_exclusive(&qword_18001E7F8);
  ExplicitModule = CModule::LoadExplicitModule((CModule *)&g_Module, v7, a3, 0);
  v9 = ExplicitModule;
  if ( ExplicitModule )
  {
    v10 = (*((__int64 (__fastcall **)(GUID *, const struct _GUID *, void **))ExplicitModule + 15))(
            &CLSID_D3D12DeviceFactory,
            a4,
            a5);
    if ( v10 < 0 && !(unsigned int)D3DCoreModule::CanD3D12CoreUnloadNow(v9) )
      CModule::UnloadModule((CModule *)&g_Module, v9);
  }
  else
  {
    v10 = -2005008381;
  }
  Smtx_unlock_exclusive(&qword_18001E7F8);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000e880  mov     [rsp+arg_0], rbx
0x18000e885  mov     [rsp+arg_8], rsi
0x18000e88a  push    rdi
0x18000e88b  sub     rsp, 20h
0x18000e88f  mov     rsi, r9
0x18000e892  mov     rbx, r8
0x18000e895  mov     edi, edx
0x18000e897  mov     dl, 1
0x18000e899  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_D3D12IndependentDevices@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_D3D12IndependentDevices@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12IndependentDevices> `wil::Feature<__WilFeatureTraits_Feature_D3D12IndependentDevices>::GetImpl(void)'::`2'::impl
0x18000e8a0  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_D3D12IndependentDevices@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12IndependentDevices>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18000e8a5  lea     rcx, qword_18001E7F8; _Smtx_t *
0x18000e8ac  call    _Smtx_lock_exclusive
0x18000e8b1  xor     r9d, r9d; bool
0x18000e8b4  mov     r8, rbx; char *
0x18000e8b7  mov     edx, edi; unsigned int
0x18000e8b9  lea     rcx, ?g_Module@@3VCModule@@A; this
0x18000e8c0  call    ?LoadExplicitModule@CModule@@QEAAPEAVD3DCoreModule@@IPEBD_N@Z; CModule::LoadExplicitModule(uint,char const *,bool)
0x18000e8c5  mov     rdi, rax
0x18000e8c8  test    rax, rax
0x18000e8cb  jnz     short loc_18000E8D4
0x18000e8cd  mov     ebx, 887E0003h
0x18000e8d2  jmp     short loc_18000E90D
0x18000e8d4  mov     r8, [rsp+28h+arg_20]
0x18000e8d9  mov     rdx, rsi
0x18000e8dc  lea     rcx, CLSID_D3D12DeviceFactory
0x18000e8e3  mov     rax, [rax+78h]
0x18000e8e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8ec  mov     ebx, eax
0x18000e8ee  test    eax, eax
0x18000e8f0  jns     short loc_18000E90D
0x18000e8f2  mov     rcx, rdi; this
0x18000e8f5  call    ?CanD3D12CoreUnloadNow@D3DCoreModule@@QEAAJXZ; D3DCoreModule::CanD3D12CoreUnloadNow(void)
0x18000e8fa  test    eax, eax
0x18000e8fc  jnz     short loc_18000E90D
0x18000e8fe  mov     rdx, rdi; struct D3DCoreModule *
0x18000e901  lea     rcx, ?g_Module@@3VCModule@@A; this
0x18000e908  call    ?UnloadModule@CModule@@QEAAXPEAVD3DCoreModule@@@Z; CModule::UnloadModule(D3DCoreModule *)
0x18000e90d  lea     rcx, qword_18001E7F8; _Smtx_t *
0x18000e914  call    _Smtx_unlock_exclusive
0x18000e919  mov     eax, ebx
0x18000e91b  mov     rbx, [rsp+28h+arg_0]
0x18000e920  mov     rsi, [rsp+28h+arg_8]
0x18000e925  add     rsp, 20h
0x18000e929  pop     rdi
0x18000e92a  retn
```
