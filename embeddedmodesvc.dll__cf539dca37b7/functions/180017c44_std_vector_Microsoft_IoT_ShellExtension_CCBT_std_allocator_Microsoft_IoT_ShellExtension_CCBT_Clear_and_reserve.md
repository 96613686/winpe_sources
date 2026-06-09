# std::vector<Microsoft::IoT::ShellExtension::CCBT,std::allocator<Microsoft::IoT::ShellExtension::CCBT>>::_Clear_and_reserve_geometric(unsigned __int64)

- ea: `0x180017c44`
- end: `0x180017cee`
- name: `?_Clear_and_reserve_geometric@?$vector@VCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@AEAAX_K@Z`
- size: `170`
- prototype: `Microsoft::IoT::ShellExtension::CCBT *__fastcall(Microsoft::IoT::ShellExtension::CCBT **, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001533c`

## callees

- `0x180009f7c`
- `0x18000a060`
- `0x18000f7b0`
- `0x180014e8c`
- `0x180017c44`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180017c66`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180017c66`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
Microsoft::IoT::ShellExtension::CCBT *__fastcall std::vector<Microsoft::IoT::ShellExtension::CCBT>::_Clear_and_reserve_geometric(
        Microsoft::IoT::ShellExtension::CCBT **a1,
        unsigned __int64 a2)
{
  __int64 v3; // rax
  Microsoft::IoT::ShellExtension::CCBT *v4; // rcx
  Microsoft::IoT::ShellExtension::CCBT **v5; // rdi
  _QWORD *v6; // rsi
  __int64 v7; // rbp
  Microsoft::IoT::ShellExtension::CCBT *result; // rax
  __int64 v9; // [rsp+50h] [rbp+8h] BYREF

  if ( a2 > 0x2E8BA2E8BA2E8BALL )
    std::_Xlength_error("vector too long");
  v3 = std::vector<Microsoft::IoT::ShellExtension::CCBT>::_Calculate_growth(a1, a2);
  v4 = *a1;
  v5 = a1 + 1;
  v6 = a1 + 2;
  v7 = v3;
  if ( *a1 )
  {
    std::_Destroy_range<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(v4, *v5);
    std::_Deallocate<16>(*a1, 8 * ((__int64)(*v6 - (_QWORD)*a1) >> 3));
    *a1 = 0;
    *v5 = 0;
    *v6 = 0;
  }
  v9 = v7;
  result = (Microsoft::IoT::ShellExtension::CCBT *)std::_Allocate_at_least_helper<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(
                                                     (__int64)v4,
                                                     &v9);
  *a1 = result;
  *v5 = result;
  *v6 = (char *)result + 88 * v7;
  return result;
}

```

## disassembly

```asm
0x180017c44  push    rbx
0x180017c46  push    rbp
0x180017c47  push    rsi
0x180017c48  push    rdi
0x180017c49  sub     rsp, 28h
0x180017c4d  mov     rax, 2E8BA2E8BA2E8BAh
0x180017c57  mov     rbx, rcx
0x180017c5a  cmp     rdx, rax
0x180017c5d  jbe     short loc_180017C6D
0x180017c5f  lea     rcx, aVectorTooLong; "vector too long"
0x180017c66  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180017c6d  call    ?_Calculate_growth@?$vector@VCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@AEBA_K_K@Z; std::vector<Microsoft::IoT::ShellExtension::CCBT>::_Calculate_growth(unsigned __int64)
0x180017c72  mov     rcx, [rbx]; this
0x180017c75  lea     rdi, [rbx+8]
0x180017c79  lea     rsi, [rbx+10h]
0x180017c7d  mov     rbp, rax
0x180017c80  test    rcx, rcx
0x180017c83  jz      short loc_180017CC6
0x180017c85  mov     rdx, [rdi]
0x180017c88  call    ??$_Destroy_range@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@YAXPEAVCCBT@ShellExtension@IoT@Microsoft@@QEAV1234@AEAV?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(Microsoft::IoT::ShellExtension::CCBT *,Microsoft::IoT::ShellExtension::CCBT * const,std::allocator<Microsoft::IoT::ShellExtension::CCBT> &)
0x180017c8d  mov     rdx, [rsi]
0x180017c90  mov     rax, 2E8BA2E8BA2E8BA3h
0x180017c9a  sub     rdx, [rbx]
0x180017c9d  mov     rcx, [rbx]
0x180017ca0  sar     rdx, 3
0x180017ca4  imul    rdx, rax
0x180017ca8  imul    rdx, 58h ; 'X'
0x180017cac  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180017cb1  mov     qword ptr [rbx], 0
0x180017cb8  mov     qword ptr [rdi], 0
0x180017cbf  mov     qword ptr [rsi], 0
0x180017cc6  lea     rdx, [rsp+48h+arg_0]
0x180017ccb  mov     [rsp+48h+arg_0], rbp
0x180017cd0  call    ??$_Allocate_at_least_helper@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@YAPEAVCCBT@ShellExtension@IoT@Microsoft@@AEAV?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@0@AEA_K@Z; std::_Allocate_at_least_helper<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(std::allocator<Microsoft::IoT::ShellExtension::CCBT> &,unsigned __int64 &)
0x180017cd5  mov     [rbx], rax
0x180017cd8  imul    rcx, rbp, 58h ; 'X'
0x180017cdc  mov     [rdi], rax
0x180017cdf  add     rcx, rax
0x180017ce2  mov     [rsi], rcx
0x180017ce5  add     rsp, 28h
0x180017ce9  pop     rdi
0x180017cea  pop     rsi
0x180017ceb  pop     rbp
0x180017cec  pop     rbx
0x180017ced  retn
```
