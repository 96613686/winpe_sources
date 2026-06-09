# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Foundation::Collections::IVectorView<ABI::Windows::ApplicationModel::AppExtensions::AppExtension *> *>,Microsoft::WRL::FtmBase>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800154d0`
- end: `0x18001554d`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppExtension@AppExtensions@ApplicationModel@Windows@ABI@@@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `125`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180015560`

## callees

- `0x180013520`
- `0x180013fd8`
- `0x1800154d0`
- `0x18001a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Foundation::Collections::IVectorView<ABI::Windows::ApplicationModel::AppExtensions::AppExtension *> *>,Microsoft::WRL::FtmBase>::QueryInterface(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 v3; // rcx
  _QWORD *v4; // r8
  __int64 v5; // r9
  _QWORD *v6; // r8
  __int64 v7; // r9
  __int64 v8; // r10
  int CanCastTo; // ebx

  *a3 = 0;
  if ( (unsigned int)InlineIsEqualGUID(a2, &GUID_00000000_0000_0000_c000_000000000046, a3, a1) )
  {
    *v4 = v5;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
    return 0;
  }
  if ( (unsigned int)InlineIsEqualGUID(v3, &GUID_cbd3ea3b_1275_5688_8610_0ab1f83442fc, v4, v5) )
  {
    *v6 = v7;
    CanCastTo = 0;
LABEL_5:
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 8LL))(*v6);
    return (unsigned int)CanCastTo;
  }
  CanCastTo = Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::CanCastTo(
                v7 + 8,
                v8);
  if ( CanCastTo >= 0 )
    goto LABEL_5;
  return (unsigned int)CanCastTo;
}

```

## disassembly

```asm
0x1800154d0  push    rbx
0x1800154d2  sub     rsp, 20h
0x1800154d6  mov     r10, rdx
0x1800154d9  mov     r9, rcx
0x1800154dc  mov     qword ptr [r8], 0
0x1800154e3  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800154ea  mov     rcx, r10
0x1800154ed  call    InlineIsEqualGUID
0x1800154f2  test    eax, eax
0x1800154f4  jnz     short loc_180015530
0x1800154f6  lea     rdx, _GUID_cbd3ea3b_1275_5688_8610_0ab1f83442fc
0x1800154fd  call    InlineIsEqualGUID
0x180015502  test    eax, eax
0x180015504  jz      short loc_18001550D
0x180015506  mov     [r8], r9
0x180015509  xor     ebx, ebx
0x18001550b  jmp     short loc_18001551F
0x18001550d  lea     rcx, [r9+8]
0x180015511  mov     rdx, r10
0x180015514  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::CanCastTo(_GUID const &,void * *,bool *)
0x180015519  mov     ebx, eax
0x18001551b  test    eax, eax
0x18001551d  js      short loc_180015544
0x18001551f  mov     rcx, [r8]
0x180015522  mov     rax, [rcx]
0x180015525  mov     rax, [rax+8]
0x180015529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001552e  jmp     short loc_180015544
0x180015530  mov     [r8], r9
0x180015533  mov     rax, [r9]
0x180015536  mov     rcx, r9
0x180015539  mov     rax, [rax+8]
0x18001553d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015542  xor     ebx, ebx
0x180015544  mov     eax, ebx
0x180015546  add     rsp, 20h
0x18001554a  pop     rbx
0x18001554b  retn
```
