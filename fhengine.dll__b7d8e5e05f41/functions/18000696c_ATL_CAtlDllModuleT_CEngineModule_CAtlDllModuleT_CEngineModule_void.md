# ATL::CAtlDllModuleT<CEngineModule>::~CAtlDllModuleT<CEngineModule>(void)

- ea: `0x18000696c`
- end: `0x180006989`
- name: `??1?$CAtlDllModuleT@VCEngineModule@@@ATL@@UEAA@XZ`
- size: `29`
- prototype: `void __fastcall(ATL::CAtlModule *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800069c0`
- `0x1800336d0`

## callees

- `0x180007178`
- `0x180007368`

## pseudocode

```c
void __fastcall ATL::CAtlDllModuleT<CEngineModule>::~CAtlDllModuleT<CEngineModule>(ATL::CAtlModule *this)
{
  ATL::CAtlComModule::ExecuteObjectMain(this, 0);
  ATL::CAtlModule::Term(this);
}

```

## disassembly

```asm
0x18000696c  push    rbx
0x18000696e  sub     rsp, 20h
0x180006972  mov     rbx, rcx
0x180006975  xor     edx, edx; bool
0x180006977  call    ?ExecuteObjectMain@CAtlComModule@ATL@@QEAAX_N@Z; ATL::CAtlComModule::ExecuteObjectMain(bool)
0x18000697c  mov     rcx, rbx; this
0x18000697f  add     rsp, 20h
0x180006983  pop     rbx
0x180006984  jmp     ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
```
