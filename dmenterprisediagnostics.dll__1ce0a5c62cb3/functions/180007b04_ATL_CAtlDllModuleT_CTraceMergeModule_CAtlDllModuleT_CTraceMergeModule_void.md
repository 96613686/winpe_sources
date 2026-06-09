# ATL::CAtlDllModuleT<CTraceMergeModule>::~CAtlDllModuleT<CTraceMergeModule>(void)

- ea: `0x180007b04`
- end: `0x180007b21`
- name: `??1?$CAtlDllModuleT@VCTraceMergeModule@@@ATL@@UEAA@XZ`
- size: `29`
- prototype: `void __fastcall(ATL::CAtlModule *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007c00`
- `0x180025b60`

## callees

- `0x1800080a4`
- `0x180008888`

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
0x180007b04  push    rbx
0x180007b06  sub     rsp, 20h
0x180007b0a  mov     rbx, rcx
0x180007b0d  xor     edx, edx; bool
0x180007b0f  call    ?ExecuteObjectMain@CAtlComModule@ATL@@QEAAX_N@Z; ATL::CAtlComModule::ExecuteObjectMain(bool)
0x180007b14  mov     rcx, rbx; this
0x180007b17  add     rsp, 20h
0x180007b1b  pop     rbx
0x180007b1c  jmp     ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
```
