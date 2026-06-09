# std::vector<Microsoft::IoT::ShellExtension::CCBT,std::allocator<Microsoft::IoT::ShellExtension::CCBT>>::clear(void)

- ea: `0x180014fd0`
- end: `0x180014ff7`
- name: `?clear@?$vector@VCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@QEAAXXZ`
- size: `39`
- prototype: `Microsoft::IoT::ShellExtension::CCBT *__fastcall(Microsoft::IoT::ShellExtension::CCBT **)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800114f0`
- `0x180011c34`
- `0x180013360`
- `0x180015e98`

## callees

- `0x18000a060`
- `0x180014fd0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
Microsoft::IoT::ShellExtension::CCBT *__fastcall std::vector<Microsoft::IoT::ShellExtension::CCBT>::clear(
        Microsoft::IoT::ShellExtension::CCBT **a1)
{
  Microsoft::IoT::ShellExtension::CCBT *v1; // rdx
  Microsoft::IoT::ShellExtension::CCBT *result; // rax

  v1 = a1[1];
  if ( *a1 != v1 )
  {
    std::_Destroy_range<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(*a1, v1);
    result = *a1;
    a1[1] = *a1;
  }
  return result;
}

```

## disassembly

```asm
0x180014fd0  push    rbx
0x180014fd2  sub     rsp, 20h
0x180014fd6  mov     rdx, [rcx+8]
0x180014fda  mov     rbx, rcx
0x180014fdd  cmp     [rcx], rdx
0x180014fe0  jz      short loc_180014FF1
0x180014fe2  mov     rcx, [rcx]; this
0x180014fe5  call    ??$_Destroy_range@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@YAXPEAVCCBT@ShellExtension@IoT@Microsoft@@QEAV1234@AEAV?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(Microsoft::IoT::ShellExtension::CCBT *,Microsoft::IoT::ShellExtension::CCBT * const,std::allocator<Microsoft::IoT::ShellExtension::CCBT> &)
0x180014fea  mov     rax, [rbx]
0x180014fed  mov     [rbx+8], rax
0x180014ff1  add     rsp, 20h
0x180014ff5  pop     rbx
0x180014ff6  retn
```
