# std::_Destroy_range<std::allocator<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj,std::default_delete<HvStatsPanel::Impl::HvPerfObj>>>>(std::unique_ptr<HvStatsPanel::Impl::HvPerfObj,std::default_delete<HvStatsPanel::Impl::HvPerfObj>> *,std::unique_ptr<HvStatsPanel::Impl::HvPerfObj,std::default_delete<HvStatsPanel::Impl::HvPerfObj>> * const,std::allocator<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj,std::default_delete<HvStatsPanel::Impl::HvPerfObj>>> &)

- ea: `0x180006b30`
- end: `0x180006b61`
- name: `??$_Destroy_range@V?$allocator@V?$unique_ptr@UHvPerfObj@Impl@HvStatsPanel@@U?$default_delete@UHvPerfObj@Impl@HvStatsPanel@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@UHvPerfObj@Impl@HvStatsPanel@@U?$default_delete@UHvPerfObj@Impl@HvStatsPanel@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@UHvPerfObj@Impl@HvStatsPanel@@U?$default_delete@UHvPerfObj@Impl@HvStatsPanel@@@std@@@std@@@0@@Z`
- size: `49`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180006b68`
- `0x180006d00`
- `0x1800070c0`
- `0x180007210`
- `0x180007934`

## callees

- `0x180006b30`
- `0x180007018`

## pseudocode

```c
__int64 __fastcall std::_Destroy_range<std::allocator<std::unique_ptr<HvStatsPanel::Impl::HvPerfObj>>>(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rbx
  __int64 result; // rax

  if ( a1 != a2 )
  {
    v3 = a1;
    do
    {
      result = std::unique_ptr<HvStatsPanel::Impl::HvPerfObj>::~unique_ptr<HvStatsPanel::Impl::HvPerfObj>(v3);
      v3 += 8;
    }
    while ( v3 != a2 );
  }
  return result;
}

```

## disassembly

```asm
0x180006b30  cmp     rcx, rdx
0x180006b33  jz      short locret_180006B60
0x180006b35  mov     [rsp+arg_0], rbx
0x180006b3a  push    rdi
0x180006b3b  sub     rsp, 20h
0x180006b3f  mov     rdi, rdx
0x180006b42  mov     rbx, rcx
0x180006b45  mov     rcx, rbx
0x180006b48  call    ??1?$unique_ptr@UHvPerfObj@Impl@HvStatsPanel@@U?$default_delete@UHvPerfObj@Impl@HvStatsPanel@@@std@@@std@@QEAA@XZ; std::unique_ptr<HvStatsPanel::Impl::HvPerfObj>::~unique_ptr<HvStatsPanel::Impl::HvPerfObj>(void)
0x180006b4d  add     rbx, 8
0x180006b51  cmp     rbx, rdi
0x180006b54  jnz     short loc_180006B45
0x180006b56  mov     rbx, [rsp+28h+arg_0]
0x180006b5b  add     rsp, 20h
0x180006b5f  pop     rdi
0x180006b60  retn
```
