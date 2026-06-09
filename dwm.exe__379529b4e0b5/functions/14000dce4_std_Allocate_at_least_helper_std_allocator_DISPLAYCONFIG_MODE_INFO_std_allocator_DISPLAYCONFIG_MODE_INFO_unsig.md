# std::_Allocate_at_least_helper<std::allocator<DISPLAYCONFIG_MODE_INFO>>(std::allocator<DISPLAYCONFIG_MODE_INFO> &,unsigned __int64 &)

- ea: `0x14000dce4`
- end: `0x14000dd0d`
- name: `??$_Allocate_at_least_helper@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@YAPEAUDISPLAYCONFIG_MODE_INFO@@AEAV?$allocator@UDISPLAYCONFIG_MODE_INFO@@@0@AEA_K@Z`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14000efa4`

## callees

- `0x14000dc84`
- `0x14000dce4`
- `0x14000f0fc`

## pseudocode

```c
__int64 __fastcall std::_Allocate_at_least_helper<std::allocator<DISPLAYCONFIG_MODE_INFO>>(__int64 a1, _QWORD *a2)
{
  if ( *a2 > 0x3FFFFFFFFFFFFFFuLL )
    std::_Throw_bad_array_new_length();
  return std::_Allocate<16,std::_Default_allocate_traits>(*a2 << 6);
}

```

## disassembly

```asm
0x14000dce4  sub     rsp, 28h
0x14000dce8  mov     rcx, [rdx]
0x14000dceb  mov     rax, 3FFFFFFFFFFFFFFh
0x14000dcf5  cmp     rcx, rax
0x14000dcf8  ja      short loc_14000DD07
0x14000dcfa  shl     rcx, 6
0x14000dcfe  add     rsp, 28h
0x14000dd02  jmp     ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x14000dd07  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
```
