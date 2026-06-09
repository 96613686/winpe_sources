# ATL::CAtlDllModuleT<CDataIntegrityScanModule>::~CAtlDllModuleT<CDataIntegrityScanModule>(void)

- ea: `0x180006928`
- end: `0x180006945`
- name: `??1?$CAtlDllModuleT@VCDataIntegrityScanModule@@@ATL@@UEAA@XZ`
- size: `29`
- prototype: `void __fastcall(ATL::CAtlModule *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800069b0`
- `0x180038c70`

## callees

- `0x18000748c`
- `0x1800076d8`

## pseudocode

```c
void __fastcall ATL::CAtlDllModuleT<CDataIntegrityScanModule>::~CAtlDllModuleT<CDataIntegrityScanModule>(
        ATL::CAtlModule *this)
{
  ATL::CAtlComModule::ExecuteObjectMain(this, 0);
  ATL::CAtlModule::Term(this);
}

```

## disassembly

```asm
0x180006928  push    rbx
0x18000692a  sub     rsp, 20h
0x18000692e  mov     rbx, rcx
0x180006931  xor     edx, edx; bool
0x180006933  call    ?ExecuteObjectMain@CAtlComModule@ATL@@QEAAX_N@Z; ATL::CAtlComModule::ExecuteObjectMain(bool)
0x180006938  mov     rcx, rbx; this
0x18000693b  add     rsp, 20h
0x18000693f  pop     rbx
0x180006940  jmp     ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
```
