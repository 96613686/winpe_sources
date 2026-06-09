# Microsoft::WRL::Details::Make<Microsoft::WRL::Details::WeakReferenceImpl,IUnknown * &>(IUnknown * &)

- ea: `0x180042a8c`
- end: `0x180042b46`
- name: `??$Make@VWeakReferenceImpl@Details@WRL@Microsoft@@AEAPEAUIUnknown@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VWeakReferenceImpl@Details@WRL@Microsoft@@@12@AEAPEAUIUnknown@@@Z`
- size: `186`
- prototype: `__int64 *__fastcall(__int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180042fb0`

## callees

- `0x1800098c0`
- `0x18001cb94`
- `0x18001ce50`
- `0x18001f644`
- `0x180042a8c`
- `0x180045010`

## pseudocode

```c
__int64 *__fastcall Microsoft::WRL::Details::Make<Microsoft::WRL::Details::WeakReferenceImpl,IUnknown * &>(
        __int64 *a1,
        __int64 *a2)
{
  void *v4; // rax
  _DWORD *v5; // rbx
  __int64 v6; // rsi
  volatile int *v7; // rdx
  void *v9; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  v4 = operator new(0x20u, &std::nothrow);
  v9 = v4;
  v5 = v4;
  if ( v4 )
  {
    v6 = *a2;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>((__int64)v4);
    *(_QWORD *)v5 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IWeakReference>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      Microsoft::WRL::Details::ModuleBase::module_->IncrementObjectCount(Microsoft::WRL::Details::ModuleBase::module_);
    v5[4] = 0x3FFFFFFF;
    *(_QWORD *)v5 = &Microsoft::WRL::Details::WeakReferenceImpl::`vftable';
    *((_QWORD *)v5 + 3) = v6;
    v5[3] = 2;
    if ( *a1 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(
        *a1,
        v7);
    *a1 = (__int64)v5;
    v9 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator<CapabilityAccessHelper>::~MakeAllocator<CapabilityAccessHelper>(&v9);
  return a1;
}

```

## disassembly

```asm
0x180042a8c  mov     [rsp+arg_8], rbx
0x180042a91  mov     [rsp+arg_10], rsi
0x180042a96  push    rdi
0x180042a97  sub     rsp, 20h
0x180042a9b  mov     rsi, rdx
0x180042a9e  mov     qword ptr [rcx], 0
0x180042aa5  mov     rdi, rcx
0x180042aa8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180042aaf  mov     ecx, 20h ; ' '; unsigned __int64
0x180042ab4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180042ab9  mov     [rsp+28h+arg_0], rax
0x180042abe  mov     rbx, rax
0x180042ac1  test    rax, rax
0x180042ac4  jz      short loc_180042B28
0x180042ac6  mov     rsi, [rsi]
0x180042ac9  mov     rcx, rax
0x180042acc  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>(void)
0x180042ad1  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIWeakReference@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IWeakReference>::`vftable'
0x180042ad8  mov     [rbx], rcx
0x180042adb  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180042ae2  test    rcx, rcx
0x180042ae5  jz      short loc_180042AF3
0x180042ae7  mov     rdx, [rcx]
0x180042aea  mov     rax, [rdx+8]
0x180042aee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042af3  mov     dword ptr [rbx+10h], 3FFFFFFFh
0x180042afa  lea     rax, ??_7WeakReferenceImpl@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::WeakReferenceImpl::`vftable'
0x180042b01  mov     [rbx], rax
0x180042b04  mov     [rbx+18h], rsi
0x180042b08  mov     dword ptr [rbx+0Ch], 2
0x180042b0f  mov     rcx, [rdi]
0x180042b12  test    rcx, rcx
0x180042b15  jz      short loc_180042B1C
0x180042b17  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x180042b1c  mov     [rdi], rbx
0x180042b1f  mov     [rsp+28h+arg_0], 0
0x180042b28  lea     rcx, [rsp+28h+arg_0]
0x180042b2d  call    ??1?$MakeAllocator@VCapabilityAccessHelper@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<CapabilityAccessHelper>::~MakeAllocator<CapabilityAccessHelper>(void)
0x180042b32  mov     rbx, [rsp+28h+arg_8]
0x180042b37  mov     rax, rdi
0x180042b3a  mov     rsi, [rsp+28h+arg_10]
0x180042b3f  add     rsp, 20h
0x180042b43  pop     rdi
0x180042b44  retn
```
