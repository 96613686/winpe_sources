# std::array<std::vector<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj,std::default_delete<HvStatsPanel::Impl::HvPerfObj>>,std::allocator<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj,std::default_delete<HvStatsPanel::Impl::HvPerfObj>>>>,8>::~array<std::vector<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj,std::default_delete<HvStatsPanel::Impl::HvPerfObj>>,std::allocator<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj,std::default_delete<HvStatsPanel::Impl::HvPerfObj>>>>,8>(void)

- ea: `0x180006fcc`
- end: `0x180006feb`
- name: `??1?$array@V?$vector@V?$unique_ptr@UHvPerfObj@Impl@HvStatsPanel@@U?$default_delete@UHvPerfObj@Impl@HvStatsPanel@@@std@@@std@@V?$allocator@V?$unique_ptr@UHvPerfObj@Impl@HvStatsPanel@@U?$default_delete@UHvPerfObj@Impl@HvStatsPanel@@@std@@@std@@@2@@std@@$07@std@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(void *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800090f9`

## callees

- `0x180002c88`

## pseudocode

```c
void __fastcall std::array<std::vector<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj>>,8>::~array<std::vector<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj>>,8>(
        void *a1)
{
  `eh vector destructor iterator'(
    a1,
    0x18u,
    8u,
    std::vector<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj>>::~vector<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj>>);
}

```

## disassembly

```asm
0x180006fcc  sub     rsp, 28h
0x180006fd0  lea     r9, ??1?$vector@V?$unique_ptr@UHvPerfObj@Impl@HvStatsPanel@@U?$default_delete@UHvPerfObj@Impl@HvStatsPanel@@@std@@@std@@V?$allocator@V?$unique_ptr@UHvPerfObj@Impl@HvStatsPanel@@U?$default_delete@UHvPerfObj@Impl@HvStatsPanel@@@std@@@std@@@2@@std@@QEAA@XZ; void (*)(void *)
0x180006fd7  mov     edx, 18h; unsigned __int64
0x180006fdc  lea     r8d, [rdx-10h]; unsigned __int64
0x180006fe0  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180006fe5  nop
0x180006fe6  add     rsp, 28h
0x180006fea  retn
```
