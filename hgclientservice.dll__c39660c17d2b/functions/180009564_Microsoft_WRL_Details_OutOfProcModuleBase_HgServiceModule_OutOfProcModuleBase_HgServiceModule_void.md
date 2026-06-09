# Microsoft::WRL::Details::OutOfProcModuleBase<HgServiceModule>::~OutOfProcModuleBase<HgServiceModule>(void)

- ea: `0x180009564`
- end: `0x1800095cb`
- name: `??1?$OutOfProcModuleBase@VHgServiceModule@@@Details@WRL@Microsoft@@UEAA@XZ`
- size: `103`
- prototype: `bool __fastcall(Microsoft::WRL::Details *this, struct Microsoft::WRL::Details::ModuleBase *, const wchar_t *, bool)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009558`
- `0x180009910`
- `0x180009950`

## callees

- `0x180009564`
- `0x18000a6a4`
- `0x180017010`

## pseudocode

```c
bool __fastcall Microsoft::WRL::Details::OutOfProcModuleBase<HgServiceModule>::~OutOfProcModuleBase<HgServiceModule>(
        Microsoft::WRL::Details *this,
        struct Microsoft::WRL::Details::ModuleBase *a2,
        const wchar_t *a3,
        bool a4)
{
  __int64 v5; // rcx
  bool result; // al

  *(_QWORD *)this = &Microsoft::WRL::Details::OutOfProcModuleBase<HgServiceModule>::`vftable';
  v5 = *((_QWORD *)this + 1);
  if ( v5 )
  {
    if ( *(_BYTE *)(v5 + 8) )
      (**(void (__fastcall ***)(__int64, __int64))v5)(v5, 1);
    *((_QWORD *)this + 1) = 0;
  }
  LOBYTE(a3) = 1;
  *(_QWORD *)this = &Microsoft::WRL::Module<1,HgServiceModule>::`vftable';
  result = Microsoft::WRL::Details::TerminateMap(this, a2, a3, a4);
  Microsoft::WRL::Module<1,HgServiceModule>::isInitialized = 0;
  Microsoft::WRL::Details::ModuleBase::module_ = 0;
  return result;
}

```

## disassembly

```asm
0x180009564  push    rbx
0x180009566  sub     rsp, 20h
0x18000956a  lea     rax, ??_7?$OutOfProcModuleBase@VHgServiceModule@@@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::OutOfProcModuleBase<HgServiceModule>::`vftable'
0x180009571  mov     rbx, rcx
0x180009574  mov     [rcx], rax
0x180009577  mov     rcx, [rcx+8]
0x18000957b  test    rcx, rcx
0x18000957e  jz      short loc_18000959E
0x180009580  cmp     byte ptr [rcx+8], 0
0x180009584  jz      short loc_180009596
0x180009586  mov     rax, [rcx]
0x180009589  mov     edx, 1
0x18000958e  mov     rax, [rax]
0x180009591  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009596  mov     qword ptr [rbx+8], 0
0x18000959e  lea     rax, ??_7?$Module@$00VHgServiceModule@@@WRL@Microsoft@@6B@; const Microsoft::WRL::Module<1,HgServiceModule>::`vftable'
0x1800095a5  mov     r8b, 1; wchar_t *
0x1800095a8  mov     rcx, rbx; this
0x1800095ab  mov     [rbx], rax
0x1800095ae  call    ?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEB_W_N@Z; Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,wchar_t const *,bool)
0x1800095b3  mov     cs:?isInitialized@?$Module@$00VHgServiceModule@@@WRL@Microsoft@@0_NA, 0; bool Microsoft::WRL::Module<1,HgServiceModule>::isInitialized
0x1800095ba  mov     cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA, 0; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800095c5  add     rsp, 20h
0x1800095c9  pop     rbx
0x1800095ca  retn
```
