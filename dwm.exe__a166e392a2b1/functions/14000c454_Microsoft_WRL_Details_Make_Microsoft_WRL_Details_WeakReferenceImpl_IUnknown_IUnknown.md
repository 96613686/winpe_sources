# Microsoft::WRL::Details::Make<Microsoft::WRL::Details::WeakReferenceImpl,IUnknown * &>(IUnknown * &)

- ea: `0x14000c454`
- end: `0x14000c50d`
- name: `??$Make@VWeakReferenceImpl@Details@WRL@Microsoft@@AEAPEAUIUnknown@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VWeakReferenceImpl@Details@WRL@Microsoft@@@12@AEAPEAUIUnknown@@@Z`
- size: `185`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14000c930`

## callees

- `0x1400057d0`
- `0x14000c454`
- `0x14000c640`
- `0x14000c654`
- `0x14000cc20`
- `0x140010010`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::Details::Make<Microsoft::WRL::Details::WeakReferenceImpl,IUnknown * &>(
        _QWORD *a1,
        __int64 *a2)
{
  void *v4; // rax
  _DWORD *v5; // rbx
  __int64 v6; // rsi
  void *v8; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  v4 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v4;
  v5 = v4;
  if ( v4 )
  {
    v6 = *a2;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>(v4);
    *(_QWORD *)v5 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IWeakReference>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    v5[4] = 0x3FFFFFFF;
    *(_QWORD *)v5 = &Microsoft::WRL::Details::WeakReferenceImpl::`vftable';
    *((_QWORD *)v5 + 3) = v6;
    v5[3] = 2;
    if ( *a1 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release();
    *a1 = v5;
    v8 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator<HotKeyCallback>::~MakeAllocator<HotKeyCallback>(&v8);
  return a1;
}

```

## disassembly

```asm
0x14000c454  mov     [rsp+arg_8], rbx
0x14000c459  mov     [rsp+arg_10], rsi
0x14000c45e  push    rdi
0x14000c45f  sub     rsp, 20h
0x14000c463  mov     rsi, rdx
0x14000c466  mov     qword ptr [rcx], 0
0x14000c46d  mov     rdi, rcx
0x14000c470  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000c477  mov     ecx, 20h ; ' '; unsigned __int64
0x14000c47c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000c481  mov     [rsp+28h+arg_0], rax
0x14000c486  mov     rbx, rax
0x14000c489  test    rax, rax
0x14000c48c  jz      short loc_14000C4F0
0x14000c48e  mov     rsi, [rsi]
0x14000c491  mov     rcx, rax
0x14000c494  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIWeakReference@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>(void)
0x14000c499  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIWeakReference@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IWeakReference>::`vftable'
0x14000c4a0  mov     [rbx], rcx
0x14000c4a3  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x14000c4aa  test    rcx, rcx
0x14000c4ad  jz      short loc_14000C4BB
0x14000c4af  mov     rdx, [rcx]
0x14000c4b2  mov     rax, [rdx+8]
0x14000c4b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c4bb  mov     dword ptr [rbx+10h], 3FFFFFFFh
0x14000c4c2  lea     rax, ??_7WeakReferenceImpl@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::WeakReferenceImpl::`vftable'
0x14000c4c9  mov     [rbx], rax
0x14000c4cc  mov     [rbx+18h], rsi
0x14000c4d0  mov     dword ptr [rbx+0Ch], 2
0x14000c4d7  mov     rcx, [rdi]
0x14000c4da  test    rcx, rcx
0x14000c4dd  jz      short loc_14000C4E4
0x14000c4df  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIWeakReference@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release(void)
0x14000c4e4  mov     [rdi], rbx
0x14000c4e7  mov     [rsp+28h+arg_0], 0
0x14000c4f0  lea     rcx, [rsp+28h+arg_0]
0x14000c4f5  call    ??1?$MakeAllocator@VHotKeyCallback@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<HotKeyCallback>::~MakeAllocator<HotKeyCallback>(void)
0x14000c4fa  mov     rbx, [rsp+28h+arg_8]
0x14000c4ff  mov     rax, rdi
0x14000c502  mov     rsi, [rsp+28h+arg_10]
0x14000c507  add     rsp, 20h
0x14000c50b  pop     rdi
0x14000c50c  retn
```
