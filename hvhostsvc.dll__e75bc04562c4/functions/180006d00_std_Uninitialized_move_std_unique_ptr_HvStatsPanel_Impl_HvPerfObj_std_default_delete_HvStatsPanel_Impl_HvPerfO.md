# std::_Uninitialized_move<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj,std::default_delete<HvStatsPanel::Impl::HvPerfObj>> *,std::allocator<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj,std::default_delete<HvStatsPanel::Impl::HvPerfObj>>>>(std::unique_ptr<HvStatsPanel::Impl::HvPerfObj,std::default_delete<HvStatsPanel::Impl::HvPerfObj>> * const,std::unique_ptr<HvStatsPanel::Impl::HvPerfObj,std::default_delete<HvStatsPanel::Impl::HvPerfObj>> * const,std::unique_ptr<HvStatsPanel::Impl::HvPerfObj,std::default_delete<HvStatsPanel::Impl::HvPerfObj>> *,std::allocator<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj,std::default_delete<HvStatsPanel::Impl::HvPerfObj>>> &)

- ea: `0x180006d00`
- end: `0x180006d39`
- name: `??$_Uninitialized_move@PEAV?$unique_ptr@UHvPerfObj@Impl@HvStatsPanel@@U?$default_delete@UHvPerfObj@Impl@HvStatsPanel@@@std@@@std@@V?$allocator@V?$unique_ptr@UHvPerfObj@Impl@HvStatsPanel@@U?$default_delete@UHvPerfObj@Impl@HvStatsPanel@@@std@@@std@@@2@@std@@YAPEAV?$unique_ptr@UHvPerfObj@Impl@HvStatsPanel@@U?$default_delete@UHvPerfObj@Impl@HvStatsPanel@@@std@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$unique_ptr@UHvPerfObj@Impl@HvStatsPanel@@U?$default_delete@UHvPerfObj@Impl@HvStatsPanel@@@std@@@std@@@0@@Z`
- size: `57`
- prototype: `_QWORD *__fastcall(__int64 *, __int64 *, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180006b68`

## callees

- `0x180006b30`
- `0x180006d00`

## pseudocode

```c
_QWORD *__fastcall std::_Uninitialized_move<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj> *,std::allocator<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj>>>(
        __int64 *a1,
        __int64 *a2,
        _QWORD *a3)
{
  __int64 v4; // r8

  while ( a1 != a2 )
  {
    v4 = *a1;
    *a1 = 0;
    *a3++ = v4;
    ++a1;
  }
  std::_Destroy_range<std::allocator<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj>>>((__int64)a3, (__int64)a3);
  return a3;
}

```

## disassembly

```asm
0x180006d00  push    rbx
0x180006d02  sub     rsp, 20h
0x180006d06  mov     rbx, r8
0x180006d09  jmp     short loc_180006D20
0x180006d0b  mov     r8, [rcx]
0x180006d0e  mov     qword ptr [rcx], 0
0x180006d15  mov     [rbx], r8
0x180006d18  add     rbx, 8
0x180006d1c  add     rcx, 8
0x180006d20  cmp     rcx, rdx
0x180006d23  jnz     short loc_180006D0B
0x180006d25  mov     rdx, rbx
0x180006d28  mov     rcx, rbx
0x180006d2b  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@UHvPerfObj@Impl@HvStatsPanel@@U?$default_delete@UHvPerfObj@Impl@HvStatsPanel@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@UHvPerfObj@Impl@HvStatsPanel@@U?$default_delete@UHvPerfObj@Impl@HvStatsPanel@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@UHvPerfObj@Impl@HvStatsPanel@@U?$default_delete@UHvPerfObj@Impl@HvStatsPanel@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj>>>(std::unique_ptr<HvStatsPanel::Impl::HvPerfObj> *,std::unique_ptr<HvStatsPanel::Impl::HvPerfObj> * const,std::allocator<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj>> &)
0x180006d30  mov     rax, rbx
0x180006d33  add     rsp, 20h
0x180006d37  pop     rbx
0x180006d38  retn
```
