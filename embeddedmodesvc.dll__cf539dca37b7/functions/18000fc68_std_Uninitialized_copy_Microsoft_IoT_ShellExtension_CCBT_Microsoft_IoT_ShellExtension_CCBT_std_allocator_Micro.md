# std::_Uninitialized_copy<Microsoft::IoT::ShellExtension::CCBT *,Microsoft::IoT::ShellExtension::CCBT *,std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(Microsoft::IoT::ShellExtension::CCBT *,Microsoft::IoT::ShellExtension::CCBT *,Microsoft::IoT::ShellExtension::CCBT *,std::allocator<Microsoft::IoT::ShellExtension::CCBT> &)

- ea: `0x18000fc68`
- end: `0x18000fccd`
- name: `??$_Uninitialized_copy@PEAVCCBT@ShellExtension@IoT@Microsoft@@PEAV1234@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@YAPEAVCCBT@ShellExtension@IoT@Microsoft@@PEAV1234@00AEAV?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@0@@Z`
- size: `101`
- prototype: `Microsoft::IoT::ShellExtension::CCBT *__fastcall(__int64, __int64, Microsoft::IoT::ShellExtension::CCBT *)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000f9a4`
- `0x18000fae0`
- `0x1800155ec`

## callees

- `0x18000a060`
- `0x18000fc68`
- `0x18000fd5c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
Microsoft::IoT::ShellExtension::CCBT *__fastcall std::_Uninitialized_copy<Microsoft::IoT::ShellExtension::CCBT *,Microsoft::IoT::ShellExtension::CCBT *,std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(
        __int64 a1,
        __int64 a2,
        Microsoft::IoT::ShellExtension::CCBT *a3)
{
  __int64 i; // rdi

  for ( i = a1; i != a2; i += 88 )
  {
    std::_Default_allocator_traits<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>::construct<Microsoft::IoT::ShellExtension::CCBT,Microsoft::IoT::ShellExtension::CCBT const &>(
      a1,
      a3,
      i);
    a3 = (Microsoft::IoT::ShellExtension::CCBT *)((char *)a3 + 88);
  }
  std::_Destroy_range<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(a3, a3);
  return a3;
}

```

## disassembly

```asm
0x18000fc68  mov     rax, rsp
0x18000fc6b  mov     [rax+8], rbx
0x18000fc6f  mov     [rax+10h], rsi
0x18000fc73  push    rdi
0x18000fc74  sub     rsp, 40h
0x18000fc78  mov     rbx, r8
0x18000fc7b  mov     rsi, rdx
0x18000fc7e  mov     rdi, rcx
0x18000fc81  mov     [rax-28h], rbx
0x18000fc85  mov     [rax-20h], rbx
0x18000fc89  mov     [rax-18h], r9
0x18000fc8d  cmp     rcx, rdx
0x18000fc90  jz      short loc_18000FCAF
0x18000fc92  mov     r8, rdi
0x18000fc95  mov     rdx, rbx
0x18000fc98  call    ??$construct@VCCBT@ShellExtension@IoT@Microsoft@@AEBV1234@@?$_Default_allocator_traits@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@SAXAEAV?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@1@QEAVCCBT@ShellExtension@IoT@Microsoft@@AEBV3456@@Z; std::_Default_allocator_traits<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>::construct<Microsoft::IoT::ShellExtension::CCBT,Microsoft::IoT::ShellExtension::CCBT const &>(std::allocator<Microsoft::IoT::ShellExtension::CCBT> &,Microsoft::IoT::ShellExtension::CCBT * const,Microsoft::IoT::ShellExtension::CCBT const &)
0x18000fc9d  add     rbx, 58h ; 'X'
0x18000fca1  mov     [rsp+48h+var_20], rbx
0x18000fca6  add     rdi, 58h ; 'X'
0x18000fcaa  cmp     rdi, rsi
0x18000fcad  jnz     short loc_18000FC92
0x18000fcaf  mov     rdx, rbx
0x18000fcb2  mov     rcx, rbx; this
0x18000fcb5  call    ??$_Destroy_range@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@YAXPEAVCCBT@ShellExtension@IoT@Microsoft@@QEAV1234@AEAV?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(Microsoft::IoT::ShellExtension::CCBT *,Microsoft::IoT::ShellExtension::CCBT * const,std::allocator<Microsoft::IoT::ShellExtension::CCBT> &)
0x18000fcba  mov     rax, rbx
0x18000fcbd  mov     rbx, [rsp+48h+arg_0]
0x18000fcc2  mov     rsi, [rsp+48h+arg_8]
0x18000fcc7  add     rsp, 40h
0x18000fccb  pop     rdi
0x18000fccc  retn
```
