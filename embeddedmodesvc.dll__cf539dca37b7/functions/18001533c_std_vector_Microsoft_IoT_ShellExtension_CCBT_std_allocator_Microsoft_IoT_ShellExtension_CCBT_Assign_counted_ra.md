# std::vector<Microsoft::IoT::ShellExtension::CCBT,std::allocator<Microsoft::IoT::ShellExtension::CCBT>>::_Assign_counted_range<Microsoft::IoT::ShellExtension::CCBT *>(Microsoft::IoT::ShellExtension::CCBT *,unsigned __int64)

- ea: `0x18001533c`
- end: `0x18001540a`
- name: `??$_Assign_counted_range@PEAVCCBT@ShellExtension@IoT@Microsoft@@@?$vector@VCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@AEAAXPEAVCCBT@ShellExtension@IoT@Microsoft@@_K@Z`
- size: `206`
- prototype: `__int64 __fastcall(__int64 *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180015e98`

## callees

- `0x18000a060`
- `0x18001533c`
- `0x180015690`
- `0x180015a2c`
- `0x180017c44`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::vector<Microsoft::IoT::ShellExtension::CCBT>::_Assign_counted_range<Microsoft::IoT::ShellExtension::CCBT *>(
        __int64 *a1,
        __int64 a2,
        unsigned __int64 a3)
{
  __int64 v3; // rbx
  unsigned __int64 v5; // rdi
  __int64 v7; // r8
  unsigned __int64 v8; // rbp
  Microsoft::IoT::ShellExtension::CCBT *i; // rbp
  __int64 result; // rax

  v3 = *a1;
  v5 = a3;
  if ( a3 > 0x2E8BA2E8BA2E8BA3LL * ((a1[2] - *a1) >> 3) )
  {
    std::vector<Microsoft::IoT::ShellExtension::CCBT>::_Clear_and_reserve_geometric(a1, a3);
    v7 = *a1;
LABEL_11:
    result = std::_Uninitialized_copy_n<Microsoft::IoT::ShellExtension::CCBT *>(a2, v5, v7, a1);
    i = (Microsoft::IoT::ShellExtension::CCBT *)result;
    goto LABEL_7;
  }
  v7 = a1[1];
  v8 = 0x2E8BA2E8BA2E8BA3LL * ((v7 - v3) >> 3);
  if ( v5 > v8 )
  {
    while ( v3 != v7 )
    {
      Microsoft::IoT::ShellExtension::CCBT::operator=(v3, a2);
      v7 = a1[1];
      v3 += 88;
      a2 += 88;
    }
    v5 -= v8;
    goto LABEL_11;
  }
  for ( i = (Microsoft::IoT::ShellExtension::CCBT *)(v3 + 88 * v5); v5; --v5 )
  {
    Microsoft::IoT::ShellExtension::CCBT::operator=(v3, a2);
    v3 += 88;
    a2 += 88;
  }
  result = std::_Destroy_range<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(i);
LABEL_7:
  a1[1] = (__int64)i;
  return result;
}

```

## disassembly

```asm
0x18001533c  push    rbx
0x18001533e  push    rbp
0x18001533f  push    rsi
0x180015340  push    rdi
0x180015341  push    r14
0x180015343  sub     rsp, 20h
0x180015347  mov     rbx, [rcx]
0x18001534a  mov     rsi, rcx
0x18001534d  mov     rax, [rcx+10h]
0x180015351  mov     rdi, r8
0x180015354  sub     rax, rbx
0x180015357  mov     rcx, 2E8BA2E8BA2E8BA3h
0x180015361  sar     rax, 3
0x180015365  mov     r14, rdx
0x180015368  imul    rax, rcx
0x18001536c  cmp     r8, rax
0x18001536f  jbe     short loc_180015381
0x180015371  mov     rdx, r8
0x180015374  mov     rcx, rsi
0x180015377  call    ?_Clear_and_reserve_geometric@?$vector@VCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@AEAAX_K@Z; std::vector<Microsoft::IoT::ShellExtension::CCBT>::_Clear_and_reserve_geometric(unsigned __int64)
0x18001537c  mov     r8, [rsi]
0x18001537f  jmp     short loc_1800153F7
0x180015381  mov     r8, [rsi+8]
0x180015385  mov     rbp, r8
0x180015388  sub     rbp, rbx
0x18001538b  sar     rbp, 3
0x18001538f  imul    rbp, rcx
0x180015393  cmp     rdi, rbp
0x180015396  ja      short loc_1800153EF
0x180015398  imul    rbp, rdi, 58h ; 'X'
0x18001539c  add     rbp, rbx
0x18001539f  test    rdi, rdi
0x1800153a2  jz      short loc_1800153BD
0x1800153a4  mov     rdx, r14
0x1800153a7  mov     rcx, rbx
0x1800153aa  call    ??4CCBT@ShellExtension@IoT@Microsoft@@QEAAAEAV0123@AEAV0123@@Z; Microsoft::IoT::ShellExtension::CCBT::operator=(Microsoft::IoT::ShellExtension::CCBT &)
0x1800153af  add     rbx, 58h ; 'X'
0x1800153b3  add     r14, 58h ; 'X'
0x1800153b7  sub     rdi, 1
0x1800153bb  jnz     short loc_1800153A4
0x1800153bd  mov     rdx, [rsi+8]
0x1800153c1  mov     rcx, rbp; this
0x1800153c4  call    ??$_Destroy_range@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@YAXPEAVCCBT@ShellExtension@IoT@Microsoft@@QEAV1234@AEAV?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(Microsoft::IoT::ShellExtension::CCBT *,Microsoft::IoT::ShellExtension::CCBT * const,std::allocator<Microsoft::IoT::ShellExtension::CCBT> &)
0x1800153c9  mov     [rsi+8], rbp
0x1800153cd  add     rsp, 20h
0x1800153d1  pop     r14
0x1800153d3  pop     rdi
0x1800153d4  pop     rsi
0x1800153d5  pop     rbp
0x1800153d6  pop     rbx
0x1800153d7  retn
0x1800153d8  mov     rdx, r14
0x1800153db  mov     rcx, rbx
0x1800153de  call    ??4CCBT@ShellExtension@IoT@Microsoft@@QEAAAEAV0123@AEAV0123@@Z; Microsoft::IoT::ShellExtension::CCBT::operator=(Microsoft::IoT::ShellExtension::CCBT &)
0x1800153e3  mov     r8, [rsi+8]
0x1800153e7  add     rbx, 58h ; 'X'
0x1800153eb  add     r14, 58h ; 'X'
0x1800153ef  cmp     rbx, r8
0x1800153f2  jnz     short loc_1800153D8
0x1800153f4  sub     rdi, rbp
0x1800153f7  mov     r9, rsi
0x1800153fa  mov     rdx, rdi
0x1800153fd  mov     rcx, r14
0x180015400  call    ??$_Uninitialized_copy_n@PEAVCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@YAPEAVCCBT@ShellExtension@IoT@Microsoft@@PEAV1234@_K0AEAV?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@0@@Z; std::_Uninitialized_copy_n<Microsoft::IoT::ShellExtension::CCBT *>(Microsoft::IoT::ShellExtension::CCBT *,unsigned __int64,Microsoft::IoT::ShellExtension::CCBT *,std::allocator<Microsoft::IoT::ShellExtension::CCBT> &)
0x180015405  mov     rbp, rax
0x180015408  jmp     short loc_1800153C9
```
