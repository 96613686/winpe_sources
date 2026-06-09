# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Foundation::Collections::IVectorView<ABI::Windows::ApplicationModel::AppExtensions::AppExtension *> *>,Microsoft::WRL::FtmBase>::Release(void)

- ea: `0x180015610`
- end: `0x180015660`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppExtension@AppExtensions@ApplicationModel@Windows@ABI@@@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180015670`

## callees

- `0x180013b60`
- `0x180015610`
- `0x18001a010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Foundation::Collections::IVectorView<ABI::Windows::ApplicationModel::AppExtensions::AppExtension *> *>,Microsoft::WRL::FtmBase>::Release(
        __int64 a1,
        volatile int *a2)
{
  unsigned int v2; // ebx
  __int64 v3; // r10

  v2 = Microsoft::WRL::Details::SafeUnknownDecrementReference((Microsoft::WRL::Details *)(a1 + 44), a2);
  if ( !v2 )
  {
    if ( v3 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v3 + 32LL))(v3, v2 + 1);
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
  }
  return v2;
}

```

## disassembly

```asm
0x180015610  push    rbx
0x180015612  sub     rsp, 20h
0x180015616  mov     r10, rcx
0x180015619  add     rcx, 2Ch ; ','; this
0x18001561d  call    ?SafeUnknownDecrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownDecrementReference(long volatile &)
0x180015622  mov     ebx, eax
0x180015624  test    eax, eax
0x180015626  jnz     short loc_180015657
0x180015628  test    r10, r10
0x18001562b  jz      short loc_18001563F
0x18001562d  mov     rdx, [r10]
0x180015630  mov     rcx, r10
0x180015633  mov     rax, [rdx+20h]
0x180015637  lea     edx, [rbx+1]
0x18001563a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001563f  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180015646  test    rcx, rcx
0x180015649  jz      short loc_180015657
0x18001564b  mov     rax, [rcx]
0x18001564e  mov     rax, [rax+10h]
0x180015652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015657  mov     eax, ebx
0x180015659  add     rsp, 20h
0x18001565d  pop     rbx
0x18001565e  retn
```
