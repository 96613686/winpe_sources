# ATL::CAtlDllModuleT<CTraceMergeModule>::~CAtlDllModuleT<CTraceMergeModule>(void)

- ea: `0x180007e74`
- end: `0x180007e91`
- name: `??1?$CAtlDllModuleT@VCTraceMergeModule@@@ATL@@UEAA@XZ`
- size: `29`
- prototype: `__int64 __fastcall(ATL::CAtlModule *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007f80`
- `0x180026a20`

## callees

- `0x18000844c`
- `0x180008ca8`

## pseudocode

```c
void __fastcall ATL::CAtlDllModuleT<CTraceMergeModule>::~CAtlDllModuleT<CTraceMergeModule>(ATL::CAtlModule *this)
{
  ATL::CAtlComModule::ExecuteObjectMain(this, 0);
  ATL::CAtlModule::Term(this);
}

```

## disassembly

```asm
0x180007e74  push    rbx
0x180007e76  sub     rsp, 20h
0x180007e7a  mov     rbx, rcx
0x180007e7d  xor     edx, edx; bool
0x180007e7f  call    ?ExecuteObjectMain@CAtlComModule@ATL@@QEAAX_N@Z; ATL::CAtlComModule::ExecuteObjectMain(bool)
0x180007e84  mov     rcx, rbx; this
0x180007e87  add     rsp, 20h
0x180007e8b  pop     rbx
0x180007e8c  jmp     ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
```
