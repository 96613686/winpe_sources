# std::vector<Microsoft::IoT::ShellExtension::CCBT,std::allocator<Microsoft::IoT::ShellExtension::CCBT>>::_Reallocate<0>(unsigned __int64 &)

- ea: `0x1800155ec`
- end: `0x180015689`
- name: `??$_Reallocate@$0A@@?$vector@VCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@AEAAXAEA_K@Z`
- size: `157`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180015e98`

## callees

- `0x180009ebc`
- `0x18000c548`
- `0x18000fc68`
- `0x180014ed4`
- `0x1800155ec`
- `0x180015a08`

## pseudocode

```c
__int64 __fastcall std::vector<Microsoft::IoT::ShellExtension::CCBT>::_Reallocate<0>(_QWORD *a1, _QWORD *a2)
{
  __int64 v4; // rdi
  _QWORD *v5; // rbx
  _QWORD v7[9]; // [rsp+20h] [rbp-48h] BYREF

  if ( *a2 > 0x2E8BA2E8BA2E8BAuLL )
    std::_Throw_bad_array_new_length();
  v4 = 0x2E8BA2E8BA2E8BA3LL * ((__int64)(a1[1] - *a1) >> 3);
  v5 = std::_Allocate<16,std::_Default_allocate_traits>(88LL * *a2);
  std::_Uninitialized_copy<Microsoft::IoT::ShellExtension::CCBT *,Microsoft::IoT::ShellExtension::CCBT *,std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(
    *a1,
    a1[1],
    v5,
    a1,
    a1,
    v5,
    *a2,
    v7[3],
    v7[4]);
  v7[1] = 0;
  std::vector<Microsoft::IoT::ShellExtension::CCBT>::_Change_array(a1, v5, v4, *a2);
  return std::vector<Microsoft::IoT::ShellExtension::CCBT>::_Simple_reallocation_guard::~_Simple_reallocation_guard(v7);
}

```

## disassembly

```asm
0x1800155ec  push    rbx
0x1800155ee  push    rsi
0x1800155ef  push    rdi
0x1800155f0  push    r14
0x1800155f2  sub     rsp, 48h
0x1800155f6  mov     rsi, rdx
0x1800155f9  mov     r14, rcx
0x1800155fc  mov     rax, 2E8BA2E8BA2E8BAh
0x180015606  cmp     [rdx], rax
0x180015609  ja      short loc_180015683
0x18001560b  mov     rdi, [rcx+8]
0x18001560f  sub     rdi, [rcx]
0x180015612  sar     rdi, 3
0x180015616  mov     rax, 2E8BA2E8BA2E8BA3h
0x180015620  imul    rdi, rax
0x180015624  imul    rcx, [rdx], 58h ; 'X'
0x180015628  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18001562d  mov     rbx, rax
0x180015630  mov     [rsp+68h+var_48], r14
0x180015635  mov     [rsp+68h+var_40], rax
0x18001563a  mov     rcx, [rsi]
0x18001563d  mov     [rsp+68h+var_38], rcx
0x180015642  mov     r9, r14
0x180015645  mov     r8, rax
0x180015648  mov     rdx, [r14+8]
0x18001564c  mov     rcx, [r14]
0x18001564f  call    ??$_Uninitialized_copy@PEAVCCBT@ShellExtension@IoT@Microsoft@@PEAV1234@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@YAPEAVCCBT@ShellExtension@IoT@Microsoft@@PEAV1234@00AEAV?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@0@@Z; std::_Uninitialized_copy<Microsoft::IoT::ShellExtension::CCBT *,Microsoft::IoT::ShellExtension::CCBT *,std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(Microsoft::IoT::ShellExtension::CCBT *,Microsoft::IoT::ShellExtension::CCBT *,Microsoft::IoT::ShellExtension::CCBT *,std::allocator<Microsoft::IoT::ShellExtension::CCBT> &)
0x180015654  mov     [rsp+68h+var_40], 0
0x18001565d  mov     r9, [rsi]
0x180015660  mov     r8, rdi
0x180015663  mov     rdx, rbx
0x180015666  mov     rcx, r14
0x180015669  call    ?_Change_array@?$vector@VCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@AEAAXQEAVCCBT@ShellExtension@IoT@Microsoft@@_K1@Z; std::vector<Microsoft::IoT::ShellExtension::CCBT>::_Change_array(Microsoft::IoT::ShellExtension::CCBT * const,unsigned __int64,unsigned __int64)
0x18001566e  nop
0x18001566f  lea     rcx, [rsp+68h+var_48]
0x180015674  call    ??1_Simple_reallocation_guard@?$vector@VCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::IoT::ShellExtension::CCBT>::_Simple_reallocation_guard::~_Simple_reallocation_guard(void)
0x180015679  add     rsp, 48h
0x18001567d  pop     r14
0x18001567f  pop     rdi
0x180015680  pop     rsi
0x180015681  pop     rbx
0x180015682  retn
0x180015683  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
```
