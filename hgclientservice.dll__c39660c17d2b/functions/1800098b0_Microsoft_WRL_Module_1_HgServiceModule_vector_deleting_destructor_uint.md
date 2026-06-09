# Microsoft::WRL::Module<1,HgServiceModule>::`vector deleting destructor'(uint)

- ea: `0x1800098b0`
- end: `0x180009903`
- name: `??_E?$Module@$00VHgServiceModule@@@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `83`
- prototype: `Microsoft::WRL::Details *__fastcall(Microsoft::WRL::Details *Block, struct Microsoft::WRL::Details::ModuleBase *, const wchar_t *, bool)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180001bb4`
- `0x1800098b0`
- `0x18000a6a4`

## pseudocode

```c
Microsoft::WRL::Details *__fastcall Microsoft::WRL::Module<1,HgServiceModule>::`vector deleting destructor'(
        Microsoft::WRL::Details *Block,
        struct Microsoft::WRL::Details::ModuleBase *a2,
        const wchar_t *a3,
        bool a4)
{
  char v4; // bl

  LOBYTE(a3) = 1;
  *(_QWORD *)Block = &Microsoft::WRL::Module<1,HgServiceModule>::`vftable';
  v4 = (char)a2;
  Microsoft::WRL::Details::TerminateMap(Block, a2, a3, a4);
  Microsoft::WRL::Module<1,HgServiceModule>::isInitialized = 0;
  Microsoft::WRL::Details::ModuleBase::module_ = 0;
  if ( (v4 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x1800098b0  mov     [rsp+arg_0], rbx
0x1800098b5  push    rdi
0x1800098b6  sub     rsp, 20h
0x1800098ba  lea     rax, ??_7?$Module@$00VHgServiceModule@@@WRL@Microsoft@@6B@; const Microsoft::WRL::Module<1,HgServiceModule>::`vftable'
0x1800098c1  mov     r8b, 1; wchar_t *
0x1800098c4  mov     [rcx], rax
0x1800098c7  mov     ebx, edx
0x1800098c9  mov     rdi, rcx
0x1800098cc  call    ?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEB_W_N@Z; Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,wchar_t const *,bool)
0x1800098d1  mov     cs:?isInitialized@?$Module@$00VHgServiceModule@@@WRL@Microsoft@@0_NA, 0; bool Microsoft::WRL::Module<1,HgServiceModule>::isInitialized
0x1800098d8  mov     cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA, 0; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800098e3  test    bl, 1
0x1800098e6  jz      short loc_1800098F5
0x1800098e8  mov     edx, 8
0x1800098ed  mov     rcx, rdi; Block
0x1800098f0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800098f5  mov     rbx, [rsp+28h+arg_0]
0x1800098fa  mov     rax, rdi
0x1800098fd  add     rsp, 20h
0x180009901  pop     rdi
0x180009902  retn
```
