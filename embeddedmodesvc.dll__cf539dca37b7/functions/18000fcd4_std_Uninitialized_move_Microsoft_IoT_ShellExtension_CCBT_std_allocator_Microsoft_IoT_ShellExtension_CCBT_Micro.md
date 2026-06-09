# std::_Uninitialized_move<Microsoft::IoT::ShellExtension::CCBT *,std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(Microsoft::IoT::ShellExtension::CCBT * const,Microsoft::IoT::ShellExtension::CCBT * const,Microsoft::IoT::ShellExtension::CCBT *,std::allocator<Microsoft::IoT::ShellExtension::CCBT> &)

- ea: `0x18000fcd4`
- end: `0x18000fd14`
- name: `??$_Uninitialized_move@PEAVCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@YAPEAVCCBT@ShellExtension@IoT@Microsoft@@QEAV1234@0PEAV1234@AEAV?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@0@@Z`
- size: `64`
- prototype: `Microsoft::IoT::ShellExtension::CCBT *__fastcall(__int64, __int64, Microsoft::IoT::ShellExtension::CCBT *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000f9a4`
- `0x18000fae0`

## callees

- `0x18000a060`
- `0x18000fcd4`
- `0x18000fd70`

## pseudocode

```c
Microsoft::IoT::ShellExtension::CCBT *__fastcall std::_Uninitialized_move<Microsoft::IoT::ShellExtension::CCBT *>(
        __int64 a1,
        __int64 a2,
        Microsoft::IoT::ShellExtension::CCBT *a3)
{
  __int64 v4; // r10
  __int64 v5; // r10
  __int64 v6; // r11

  v4 = a1;
  if ( a1 != a2 )
  {
    do
    {
      std::_Default_allocator_traits<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>::construct<Microsoft::IoT::ShellExtension::CCBT,Microsoft::IoT::ShellExtension::CCBT>(
        a1,
        a3,
        v4);
      a3 = (Microsoft::IoT::ShellExtension::CCBT *)((char *)a3 + 88);
      v4 = v5 + 88;
    }
    while ( v4 != v6 );
  }
  std::_Destroy_range<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(a3, a3);
  return a3;
}

```

## disassembly

```asm
0x18000fcd4  push    rbx
0x18000fcd6  sub     rsp, 20h
0x18000fcda  mov     rbx, r8
0x18000fcdd  mov     r11, rdx
0x18000fce0  mov     r10, rcx
0x18000fce3  cmp     rcx, rdx
0x18000fce6  jz      short loc_18000FD00
0x18000fce8  mov     r8, r10
0x18000fceb  mov     rdx, rbx
0x18000fcee  call    ??$construct@VCCBT@ShellExtension@IoT@Microsoft@@V1234@@?$_Default_allocator_traits@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@SAXAEAV?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@1@QEAVCCBT@ShellExtension@IoT@Microsoft@@$$QEAV3456@@Z; std::_Default_allocator_traits<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>::construct<Microsoft::IoT::ShellExtension::CCBT,Microsoft::IoT::ShellExtension::CCBT>(std::allocator<Microsoft::IoT::ShellExtension::CCBT> &,Microsoft::IoT::ShellExtension::CCBT * const,Microsoft::IoT::ShellExtension::CCBT &&)
0x18000fcf3  add     rbx, 58h ; 'X'
0x18000fcf7  add     r10, 58h ; 'X'
0x18000fcfb  cmp     r10, r11
0x18000fcfe  jnz     short loc_18000FCE8
0x18000fd00  mov     rdx, rbx
0x18000fd03  mov     rcx, rbx; this
0x18000fd06  call    ??$_Destroy_range@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@YAXPEAVCCBT@ShellExtension@IoT@Microsoft@@QEAV1234@AEAV?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(Microsoft::IoT::ShellExtension::CCBT *,Microsoft::IoT::ShellExtension::CCBT * const,std::allocator<Microsoft::IoT::ShellExtension::CCBT> &)
0x18000fd0b  mov     rax, rbx
0x18000fd0e  add     rsp, 20h
0x18000fd12  pop     rbx
0x18000fd13  retn
```
