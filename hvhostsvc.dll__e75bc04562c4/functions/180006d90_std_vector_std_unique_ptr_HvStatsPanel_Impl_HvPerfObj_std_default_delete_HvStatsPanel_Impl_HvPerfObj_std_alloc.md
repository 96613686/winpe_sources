# std::vector<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj,std::default_delete<HvStatsPanel::Impl::HvPerfObj>>,std::allocator<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj,std::default_delete<HvStatsPanel::Impl::HvPerfObj>>>>::vector<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj,std::default_delete<HvStatsPanel::Impl::HvPerfObj>>,std::allocator<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj,std::default_delete<HvStatsPanel::Impl::HvPerfObj>>>>(void)

- ea: `0x180006d90`
- end: `0x180006da1`
- name: `??0?$vector@V?$unique_ptr@UHvPerfObj@Impl@HvStatsPanel@@U?$default_delete@UHvPerfObj@Impl@HvStatsPanel@@@std@@@std@@V?$allocator@V?$unique_ptr@UHvPerfObj@Impl@HvStatsPanel@@U?$default_delete@UHvPerfObj@Impl@HvStatsPanel@@@std@@@std@@@2@@std@@QEAA@XZ`
- size: `17`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
void __fastcall std::vector<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj>>::vector<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj>>(
        _QWORD *a1)
{
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
}

```

## disassembly

```asm
0x180006d90  xor     eax, eax
0x180006d92  mov     [rcx], rax
0x180006d95  mov     [rcx+8], rax
0x180006d99  mov     [rcx+10h], rax
0x180006d9d  mov     rax, rcx
0x180006da0  retn
```
