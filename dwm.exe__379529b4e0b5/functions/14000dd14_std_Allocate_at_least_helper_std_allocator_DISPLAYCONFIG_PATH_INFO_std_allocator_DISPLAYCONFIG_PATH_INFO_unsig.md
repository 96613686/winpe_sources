# std::_Allocate_at_least_helper<std::allocator<DISPLAYCONFIG_PATH_INFO>>(std::allocator<DISPLAYCONFIG_PATH_INFO> &,unsigned __int64 &)

- ea: `0x14000dd14`
- end: `0x14000dd41`
- name: `??$_Allocate_at_least_helper@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@YAPEAUDISPLAYCONFIG_PATH_INFO@@AEAV?$allocator@UDISPLAYCONFIG_PATH_INFO@@@0@AEA_K@Z`
- size: `45`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14000f004`

## callees

- `0x14000dc84`
- `0x14000dd14`
- `0x14000f0fc`

## pseudocode

```c
__int64 __fastcall std::_Allocate_at_least_helper<std::allocator<DISPLAYCONFIG_PATH_INFO>>(__int64 a1, _QWORD *a2)
{
  if ( *a2 > 0x38E38E38E38E38EuLL )
    std::_Throw_bad_array_new_length();
  return std::_Allocate<16,std::_Default_allocate_traits>(72LL * *a2);
}

```

## disassembly

```asm
0x14000dd14  sub     rsp, 28h
0x14000dd18  mov     rax, [rdx]
0x14000dd1b  mov     rcx, 38E38E38E38E38Eh
0x14000dd25  cmp     rax, rcx
0x14000dd28  ja      short loc_14000DD3B
0x14000dd2a  lea     rcx, [rax+rax*8]
0x14000dd2e  shl     rcx, 3
0x14000dd32  add     rsp, 28h
0x14000dd36  jmp     ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x14000dd3b  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
```
