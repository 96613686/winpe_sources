# ATL::CAtlDllModuleT<MapsbtsvcDllModule>::~CAtlDllModuleT<MapsbtsvcDllModule>(void)

- ea: `0x180002a3c`
- end: `0x180002a59`
- name: `??1?$CAtlDllModuleT@VMapsbtsvcDllModule@@@ATL@@UEAA@XZ`
- size: `29`
- prototype: `void __fastcall(ATL::CAtlModule *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002b50`
- `0x180014890`

## callees

- `0x180002f4c`
- `0x180003248`

## pseudocode

```c
void __fastcall ATL::CAtlDllModuleT<MapsbtsvcDllModule>::~CAtlDllModuleT<MapsbtsvcDllModule>(ATL::CAtlModule *this)
{
  ATL::CAtlComModule::ExecuteObjectMain(this, 0);
  ATL::CAtlModule::Term(this);
}

```

## disassembly

```asm
0x180002a3c  push    rbx
0x180002a3e  sub     rsp, 20h
0x180002a42  mov     rbx, rcx
0x180002a45  xor     edx, edx; bool
0x180002a47  call    ?ExecuteObjectMain@CAtlComModule@ATL@@QEAAX_N@Z; ATL::CAtlComModule::ExecuteObjectMain(bool)
0x180002a4c  mov     rcx, rbx; this
0x180002a4f  add     rsp, 20h
0x180002a53  pop     rbx
0x180002a54  jmp     ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
```
