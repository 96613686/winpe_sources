# ??$call@P6A?AUCoreWindow@Core@UI@Windows@winrt@@AEBUICoreWindowStatic@2345@@Z@?$factory_cache_entry@UCoreWindow@Core@UI@Windows@winrt@@UICoreWindowStatic@2345@@impl@winrt@@QEAA?A_P$$QEAP6A?AUCoreWindow@Core@UI@Windows@2@AEBUICoreWindowStatic@4562@@Z@Z

- ea: `0x1800138f8`
- end: `0x180013a0e`
- name: `??$call@P6A?AUCoreWindow@Core@UI@Windows@winrt@@AEBUICoreWindowStatic@2345@@Z@?$factory_cache_entry@UCoreWindow@Core@UI@Windows@winrt@@UICoreWindowStatic@2345@@impl@winrt@@QEAA?A_P$$QEAP6A?AUCoreWindow@Core@UI@Windows@2@AEBUICoreWindowStatic@4562@@Z@Z`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180014a38`

## callees

- `0x180002471`
- `0x180003444`
- `0x180003580`
- `0x1800065f0`
- `0x1800138f8`
- `0x180013ae8`
- `0x180028010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::UI::Core::CoreWindow,winrt::Windows::UI::Core::ICoreWindowStatic>::call<winrt::Windows::UI::Core::CoreWindow (*)(winrt::Windows::UI::Core::ICoreWindowStatic const &)>(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 **),
        __int64 a2,
        void (__fastcall **a3)(__int64, __int64 *))
{
  _QWORD v6[2]; // [rsp+28h] [rbp-38h] BYREF
  _BYTE v7[40]; // [rsp+38h] [rbp-28h] BYREF
  void (__fastcall ***v8)(_QWORD, __int64 *, __int64 **); // [rsp+70h] [rbp+10h] BYREF
  __int64 *v9; // [rsp+88h] [rbp+28h] BYREF

  v8 = a1;
  v6[0] = L"Windows.UI.Core.CoreWindow";
  v6[1] = 26;
  winrt::param::hstring::hstring(v7, v6);
  winrt::get_activation_factory<winrt::Windows::UI::Core::ICoreWindowStatic>(&v8, v7);
  if ( v8 && (v9 = 0, (**v8)(v8, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v9), v9) )
  {
    winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref((__int64 *)&v9);
    v9 = &qword_180035908;
    _InterlockedIncrement64(&qword_180035908);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Core::CoreWindow,winrt::Windows::UI::Core::ICoreWindowStatic>,
            (signed __int64)v8,
            0) )
    {
      v8 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180035910);
    }
    (*a3)(
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Core::CoreWindow,winrt::Windows::UI::Core::ICoreWindowStatic>);
    _InterlockedDecrement64(&qword_180035908);
  }
  else
  {
    (*a3)(a2, (__int64 *)&v8);
  }
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v8);
  return a2;
}

```

## disassembly

```asm
0x1800138f8  mov     [rsp-8+arg_8], rbx
0x1800138fd  mov     [rsp-8+arg_10], rdi
0x180013902  mov     [rsp-8+arg_0], rcx
0x180013907  push    rbp
0x180013908  mov     rbp, rsp
0x18001390b  sub     rsp, 60h
0x18001390f  mov     rdi, r8
0x180013912  mov     rbx, rdx
0x180013915  lea     rax, aWindowsUiCoreC; "Windows.UI.Core.CoreWindow"
0x18001391c  mov     [rbp+var_38], rax
0x180013920  mov     [rbp+var_30], 1Ah
0x180013928  lea     rdx, [rbp+var_38]
0x18001392c  lea     rcx, [rbp+var_28]
0x180013930  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x180013935  lea     rdx, [rbp+var_28]
0x180013939  lea     rcx, [rbp+arg_0]
0x18001393d  call    ??$get_activation_factory@UICoreWindowStatic@Core@UI@Windows@winrt@@@winrt@@YA?AUICoreWindowStatic@Core@UI@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::UI::Core::ICoreWindowStatic>(winrt::param::hstring const &)
0x180013942  nop
0x180013943  mov     rcx, [rbp+arg_0]
0x180013947  test    rcx, rcx
0x18001394a  jz      loc_1800139E0
0x180013950  mov     [rbp+arg_18], 0
0x180013958  mov     rax, [rcx]
0x18001395b  lea     r8, [rbp+arg_18]
0x18001395f  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180013966  mov     rax, [rax]
0x180013969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001396e  mov     rax, [rbp+arg_18]
0x180013972  mov     [rbp+arg_18], rax
0x180013976  test    rax, rax
0x180013979  jz      short loc_1800139E0
0x18001397b  lea     rcx, [rbp+arg_18]
0x18001397f  call    ?unconditional_release_ref@?$com_ptr@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(void)
0x180013984  lea     rax, qword_180035908
0x18001398b  mov     [rbp+arg_18], rax
0x18001398f  lock inc cs:qword_180035908
0x180013997  mov     rcx, [rbp+arg_0]
0x18001399b  xor     eax, eax
0x18001399d  lock cmpxchg cs:??$factory_cache_entry_v@UCoreWindow@Core@UI@Windows@winrt@@UICoreWindowStatic@2345@@impl@winrt@@3U?$factory_cache_entry@UCoreWindow@Core@UI@Windows@winrt@@UICoreWindowStatic@2345@@12@A, rcx; factory_cache_entry<winrt::Windows::UI::Core::CoreWindow,winrt::Windows::UI::Core::ICoreWindowStatic>::winrt::factory_cache_entry<winrt::Windows::UI::Core::CoreWindow,winrt::Windows::UI::Core::ICoreWindowStatic> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Core::CoreWindow,winrt::Windows::UI::Core::ICoreWindowStatic>
0x1800139a6  jnz     short loc_1800139C3
0x1800139a8  mov     [rbp+arg_0], 0
0x1800139b0  lea     rdx, stru_180035910; ListEntry
0x1800139b7  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x1800139be  call    WINRT_IMPL_InterlockedPushEntrySList
0x1800139c3  lea     rdx, ??$factory_cache_entry_v@UCoreWindow@Core@UI@Windows@winrt@@UICoreWindowStatic@2345@@impl@winrt@@3U?$factory_cache_entry@UCoreWindow@Core@UI@Windows@winrt@@UICoreWindowStatic@2345@@12@A; factory_cache_entry<winrt::Windows::UI::Core::CoreWindow,winrt::Windows::UI::Core::ICoreWindowStatic>::winrt::factory_cache_entry<winrt::Windows::UI::Core::CoreWindow,winrt::Windows::UI::Core::ICoreWindowStatic> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Core::CoreWindow,winrt::Windows::UI::Core::ICoreWindowStatic>
0x1800139ca  mov     rcx, rbx
0x1800139cd  mov     rax, [rdi]
0x1800139d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800139d5  nop
0x1800139d6  lock dec cs:qword_180035908
0x1800139de  jmp     short loc_1800139F0
0x1800139e0  lea     rdx, [rbp+arg_0]
0x1800139e4  mov     rcx, rbx
0x1800139e7  mov     rax, [rdi]
0x1800139ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800139ef  nop
0x1800139f0  lea     rcx, [rbp+arg_0]
0x1800139f4  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x1800139f9  mov     rax, rbx
0x1800139fc  lea     r11, [rsp+60h+var_s0]
0x180013a01  mov     rbx, [r11+18h]
0x180013a05  mov     rdi, [r11+20h]
0x180013a09  mov     rsp, r11
0x180013a0c  pop     rbp
0x180013a0d  retn
```
