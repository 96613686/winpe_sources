# std::vector<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj,std::default_delete<HvStatsPanel::Impl::HvPerfObj>>,std::allocator<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj,std::default_delete<HvStatsPanel::Impl::HvPerfObj>>>>::_Reallocation_guard::~_Reallocation_guard(void)

- ea: `0x180007210`
- end: `0x180007244`
- name: `??1_Reallocation_guard@?$vector@V?$unique_ptr@UHvPerfObj@Impl@HvStatsPanel@@U?$default_delete@UHvPerfObj@Impl@HvStatsPanel@@@std@@@std@@V?$allocator@V?$unique_ptr@UHvPerfObj@Impl@HvStatsPanel@@U?$default_delete@UHvPerfObj@Impl@HvStatsPanel@@@std@@@std@@@2@@std@@QEAA@XZ`
- size: `52`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180006b68`

## callees

- `0x180006af0`
- `0x180006b30`
- `0x180007210`

## pseudocode

```c
void __fastcall std::vector<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj>>::_Reallocation_guard::~_Reallocation_guard(
        __int64 a1)
{
  if ( *(_QWORD *)(a1 + 8) )
  {
    std::_Destroy_range<std::allocator<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj>>>(
      *(_QWORD *)(a1 + 24),
      *(_QWORD *)(a1 + 32));
    std::_Deallocate<16>(*(void **)(a1 + 8), (struct std::nothrow_t *)(8LL * *(_QWORD *)(a1 + 16)));
  }
}

```

## disassembly

```asm
0x180007210  push    rbx
0x180007212  sub     rsp, 20h
0x180007216  cmp     qword ptr [rcx+8], 0
0x18000721b  mov     rbx, rcx
0x18000721e  jz      short loc_18000723E
0x180007220  mov     rdx, [rcx+20h]
0x180007224  mov     rcx, [rcx+18h]
0x180007228  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@UHvPerfObj@Impl@HvStatsPanel@@U?$default_delete@UHvPerfObj@Impl@HvStatsPanel@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@UHvPerfObj@Impl@HvStatsPanel@@U?$default_delete@UHvPerfObj@Impl@HvStatsPanel@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@UHvPerfObj@Impl@HvStatsPanel@@U?$default_delete@UHvPerfObj@Impl@HvStatsPanel@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj>>>(std::unique_ptr<HvStatsPanel::Impl::HvPerfObj> *,std::unique_ptr<HvStatsPanel::Impl::HvPerfObj> * const,std::allocator<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj>> &)
0x18000722d  mov     rdx, [rbx+10h]
0x180007231  mov     rcx, [rbx+8]
0x180007235  shl     rdx, 3
0x180007239  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000723e  add     rsp, 20h
0x180007242  pop     rbx
0x180007243  retn
```
