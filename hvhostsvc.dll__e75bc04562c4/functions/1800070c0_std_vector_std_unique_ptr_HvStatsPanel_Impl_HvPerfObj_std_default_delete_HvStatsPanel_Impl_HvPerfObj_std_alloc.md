# std::vector<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj,std::default_delete<HvStatsPanel::Impl::HvPerfObj>>,std::allocator<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj,std::default_delete<HvStatsPanel::Impl::HvPerfObj>>>>::~vector<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj,std::default_delete<HvStatsPanel::Impl::HvPerfObj>>,std::allocator<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj,std::default_delete<HvStatsPanel::Impl::HvPerfObj>>>>(void)

- ea: `0x1800070c0`
- end: `0x18000710a`
- name: `??1?$vector@V?$unique_ptr@UHvPerfObj@Impl@HvStatsPanel@@U?$default_delete@UHvPerfObj@Impl@HvStatsPanel@@@std@@@std@@V?$allocator@V?$unique_ptr@UHvPerfObj@Impl@HvStatsPanel@@U?$default_delete@UHvPerfObj@Impl@HvStatsPanel@@@std@@@std@@@2@@std@@QEAA@XZ`
- size: `74`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180006af0`
- `0x180006b30`
- `0x1800070c0`

## pseudocode

```c
void __fastcall std::vector<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj>>::~vector<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj>>(
        __int64 *a1)
{
  __int64 v2; // rcx

  v2 = *a1;
  if ( v2 )
  {
    std::_Destroy_range<std::allocator<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj>>>(v2, a1[1]);
    std::_Deallocate<16>((void *)*a1, (struct std::nothrow_t *)((a1[2] - *a1) & 0xFFFFFFFFFFFFFFF8uLL));
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
}

```

## disassembly

```asm
0x1800070c0  push    rbx
0x1800070c2  sub     rsp, 20h
0x1800070c6  mov     rbx, rcx
0x1800070c9  mov     rcx, [rcx]
0x1800070cc  test    rcx, rcx
0x1800070cf  jz      short loc_180007104
0x1800070d1  mov     rdx, [rbx+8]
0x1800070d5  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@UHvPerfObj@Impl@HvStatsPanel@@U?$default_delete@UHvPerfObj@Impl@HvStatsPanel@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@UHvPerfObj@Impl@HvStatsPanel@@U?$default_delete@UHvPerfObj@Impl@HvStatsPanel@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@UHvPerfObj@Impl@HvStatsPanel@@U?$default_delete@UHvPerfObj@Impl@HvStatsPanel@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj>>>(std::unique_ptr<HvStatsPanel::Impl::HvPerfObj> *,std::unique_ptr<HvStatsPanel::Impl::HvPerfObj> * const,std::allocator<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj>> &)
0x1800070da  mov     rdx, [rbx+10h]
0x1800070de  sub     rdx, [rbx]
0x1800070e1  mov     rcx, [rbx]
0x1800070e4  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1800070e8  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800070ed  mov     qword ptr [rbx], 0
0x1800070f4  mov     qword ptr [rbx+8], 0
0x1800070fc  mov     qword ptr [rbx+10h], 0
0x180007104  add     rsp, 20h
0x180007108  pop     rbx
0x180007109  retn
```
