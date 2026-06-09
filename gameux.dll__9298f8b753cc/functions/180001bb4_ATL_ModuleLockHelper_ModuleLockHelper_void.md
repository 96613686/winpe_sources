# ATL::ModuleLockHelper::ModuleLockHelper(void)

- ea: `0x180001bb4`
- end: `0x180001bd9`
- name: `??0ModuleLockHelper@ATL@@QEAA@XZ`
- size: `37`
- prototype: `__int64 __fastcall(ATL::ModuleLockHelper *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180002360`
- `0x180002400`
- `0x180002b40`
- `0x180002bd0`
- `0x180002c40`

## callees

- `0x180004010`

## pseudocode

```c
ATL::ModuleLockHelper *__fastcall ATL::ModuleLockHelper::ModuleLockHelper(ATL::ModuleLockHelper *this)
{
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  return this;
}

```

## disassembly

```asm
0x180001bb4  push    rbx
0x180001bb6  sub     rsp, 20h
0x180001bba  mov     rbx, rcx
0x180001bbd  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180001bc4  mov     rax, [rcx]
0x180001bc7  mov     rax, [rax+8]
0x180001bcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001bd0  mov     rax, rbx
0x180001bd3  add     rsp, 20h
0x180001bd7  pop     rbx
0x180001bd8  retn
```
