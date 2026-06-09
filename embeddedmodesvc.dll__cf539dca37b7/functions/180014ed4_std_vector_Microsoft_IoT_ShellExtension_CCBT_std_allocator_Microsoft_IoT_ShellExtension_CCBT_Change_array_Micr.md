# std::vector<Microsoft::IoT::ShellExtension::CCBT,std::allocator<Microsoft::IoT::ShellExtension::CCBT>>::_Change_array(Microsoft::IoT::ShellExtension::CCBT * const,unsigned __int64,unsigned __int64)

- ea: `0x180014ed4`
- end: `0x180014f41`
- name: `?_Change_array@?$vector@VCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@AEAAXQEAVCCBT@ShellExtension@IoT@Microsoft@@_K1@Z`
- size: `109`
- prototype: `Microsoft::IoT::ShellExtension::CCBT *__fastcall(Microsoft::IoT::ShellExtension::CCBT **, Microsoft::IoT::ShellExtension::CCBT *, __int64, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000f9a4`
- `0x18000fae0`
- `0x1800155ec`

## callees

- `0x180009f7c`
- `0x18000a060`
- `0x180014ed4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
Microsoft::IoT::ShellExtension::CCBT *__fastcall std::vector<Microsoft::IoT::ShellExtension::CCBT>::_Change_array(
        Microsoft::IoT::ShellExtension::CCBT **a1,
        Microsoft::IoT::ShellExtension::CCBT *a2,
        __int64 a3,
        __int64 a4)
{
  Microsoft::IoT::ShellExtension::CCBT *v6; // rcx
  Microsoft::IoT::ShellExtension::CCBT *result; // rax

  v6 = *a1;
  if ( v6 )
  {
    std::_Destroy_range<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(v6, a1[1]);
    std::_Deallocate<16>(*a1, 8 * ((a1[2] - *a1) >> 3));
  }
  *a1 = a2;
  a1[1] = (Microsoft::IoT::ShellExtension::CCBT *)((char *)a2 + 88 * a3);
  result = (Microsoft::IoT::ShellExtension::CCBT *)((char *)a2 + 88 * a4);
  a1[2] = result;
  return result;
}

```

## disassembly

```asm
0x180014ed4  push    rbx
0x180014ed6  push    rbp
0x180014ed7  push    rsi
0x180014ed8  push    rdi
0x180014ed9  sub     rsp, 28h
0x180014edd  mov     rbx, rcx
0x180014ee0  mov     rsi, r9
0x180014ee3  mov     rcx, [rcx]; this
0x180014ee6  mov     rbp, r8
0x180014ee9  mov     rdi, rdx
0x180014eec  test    rcx, rcx
0x180014eef  jz      short loc_180014F1F
0x180014ef1  mov     rdx, [rbx+8]
0x180014ef5  call    ??$_Destroy_range@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@YAXPEAVCCBT@ShellExtension@IoT@Microsoft@@QEAV1234@AEAV?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(Microsoft::IoT::ShellExtension::CCBT *,Microsoft::IoT::ShellExtension::CCBT * const,std::allocator<Microsoft::IoT::ShellExtension::CCBT> &)
0x180014efa  mov     rax, [rbx+10h]
0x180014efe  mov     rcx, 2E8BA2E8BA2E8BA3h
0x180014f08  sub     rax, [rbx]
0x180014f0b  sar     rax, 3
0x180014f0f  imul    rax, rcx
0x180014f13  mov     rcx, [rbx]
0x180014f16  imul    rdx, rax, 58h ; 'X'
0x180014f1a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180014f1f  imul    rax, rbp, 58h ; 'X'
0x180014f23  mov     [rbx], rdi
0x180014f26  add     rax, rdi
0x180014f29  mov     [rbx+8], rax
0x180014f2d  imul    rax, rsi, 58h ; 'X'
0x180014f31  add     rax, rdi
0x180014f34  mov     [rbx+10h], rax
0x180014f38  add     rsp, 28h
0x180014f3c  pop     rdi
0x180014f3d  pop     rsi
0x180014f3e  pop     rbp
0x180014f3f  pop     rbx
0x180014f40  retn
```
