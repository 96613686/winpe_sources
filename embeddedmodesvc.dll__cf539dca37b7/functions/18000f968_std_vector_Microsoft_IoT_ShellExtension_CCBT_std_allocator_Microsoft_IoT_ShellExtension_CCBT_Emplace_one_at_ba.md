# std::vector<Microsoft::IoT::ShellExtension::CCBT,std::allocator<Microsoft::IoT::ShellExtension::CCBT>>::_Emplace_one_at_back<Microsoft::IoT::ShellExtension::CCBT>(Microsoft::IoT::ShellExtension::CCBT &&)

- ea: `0x18000f968`
- end: `0x18000f99b`
- name: `??$_Emplace_one_at_back@VCCBT@ShellExtension@IoT@Microsoft@@@?$vector@VCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@AEAAAEAVCCBT@ShellExtension@IoT@Microsoft@@$$QEAV2345@@Z`
- size: `51`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000fd84`
- `0x1800114f0`
- `0x180012f10`
- `0x180015e98`

## callees

- `0x18000f968`
- `0x18000fae0`
- `0x18000fd70`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::vector<Microsoft::IoT::ShellExtension::CCBT>::_Emplace_one_at_back<Microsoft::IoT::ShellExtension::CCBT>(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rdx
  __int64 v4; // r10
  __int64 result; // rax

  v3 = *(_QWORD *)(a1 + 8);
  if ( v3 == *(_QWORD *)(a1 + 16) )
    return std::vector<Microsoft::IoT::ShellExtension::CCBT>::_Emplace_reallocate<Microsoft::IoT::ShellExtension::CCBT>(
             a1,
             v3,
             a2);
  std::_Default_allocator_traits<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>::construct<Microsoft::IoT::ShellExtension::CCBT,Microsoft::IoT::ShellExtension::CCBT>(
    a1,
    v3,
    a2);
  result = *(_QWORD *)(v4 + 8);
  *(_QWORD *)(v4 + 8) = result + 88;
  return result;
}

```

## disassembly

```asm
0x18000f968  sub     rsp, 28h
0x18000f96c  mov     r8, rdx
0x18000f96f  mov     r10, rcx
0x18000f972  mov     rdx, [rcx+8]
0x18000f976  cmp     rdx, [rcx+10h]
0x18000f97a  jz      short loc_18000F992
0x18000f97c  call    ??$construct@VCCBT@ShellExtension@IoT@Microsoft@@V1234@@?$_Default_allocator_traits@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@SAXAEAV?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@1@QEAVCCBT@ShellExtension@IoT@Microsoft@@$$QEAV3456@@Z; std::_Default_allocator_traits<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>::construct<Microsoft::IoT::ShellExtension::CCBT,Microsoft::IoT::ShellExtension::CCBT>(std::allocator<Microsoft::IoT::ShellExtension::CCBT> &,Microsoft::IoT::ShellExtension::CCBT * const,Microsoft::IoT::ShellExtension::CCBT &&)
0x18000f981  mov     rax, [r10+8]
0x18000f985  lea     rdx, [rax+58h]
0x18000f989  mov     [r10+8], rdx
0x18000f98d  add     rsp, 28h
0x18000f991  retn
0x18000f992  add     rsp, 28h
0x18000f996  jmp     ??$_Emplace_reallocate@VCCBT@ShellExtension@IoT@Microsoft@@@?$vector@VCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@AEAAPEAVCCBT@ShellExtension@IoT@Microsoft@@QEAV2345@$$QEAV2345@@Z; std::vector<Microsoft::IoT::ShellExtension::CCBT>::_Emplace_reallocate<Microsoft::IoT::ShellExtension::CCBT>(Microsoft::IoT::ShellExtension::CCBT * const,Microsoft::IoT::ShellExtension::CCBT &&)
```
