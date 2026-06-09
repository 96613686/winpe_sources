# Microsoft::WRL::Module<1,Windows::Internal::ServiceModule>::~Module<1,Windows::Internal::ServiceModule>(void)

- ea: `0x180004124`
- end: `0x180004153`
- name: `??1?$Module@$00VServiceModule@Internal@Windows@@@WRL@Microsoft@@UEAA@XZ`
- size: `47`
- prototype: `bool __fastcall(Microsoft::WRL::Details *, __int64, const unsigned __int16 *, bool)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004194`
- `0x180004a60`

## callees

- `0x180007734`

## pseudocode

```c
bool __fastcall Microsoft::WRL::Module<1,Windows::Internal::ServiceModule>::~Module<1,Windows::Internal::ServiceModule>(
        Microsoft::WRL::Details *a1,
        __int64 a2,
        const unsigned __int16 *a3,
        bool a4)
{
  bool result; // al

  LOBYTE(a3) = 1;
  *(_QWORD *)a1 = &Microsoft::WRL::Module<1,Windows::Internal::ServiceModule>::`vftable';
  result = Microsoft::WRL::Details::TerminateMap(a1, 0, a3, a4);
  Microsoft::WRL::Module<1,Windows::Internal::ServiceModule>::isInitialized = 0;
  Microsoft::WRL::Details::ModuleBase::module_ = 0;
  return result;
}

```

## disassembly

```asm
0x180004124  sub     rsp, 28h
0x180004128  lea     rax, ??_7?$Module@$00VServiceModule@Internal@Windows@@@WRL@Microsoft@@6B@; const Microsoft::WRL::Module<1,Windows::Internal::ServiceModule>::`vftable'
0x18000412f  mov     r8b, 1; unsigned __int16 *
0x180004132  xor     edx, edx; struct Microsoft::WRL::Details::ModuleBase *
0x180004134  mov     [rcx], rax
0x180004137  call    ?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z; Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)
0x18000413c  mov     cs:?isInitialized@?$Module@$00VServiceModule@Internal@Windows@@@WRL@Microsoft@@0_NA, 0; bool Microsoft::WRL::Module<1,Windows::Internal::ServiceModule>::isInitialized
0x180004143  mov     cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA, 0; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000414e  add     rsp, 28h
0x180004152  retn
```
