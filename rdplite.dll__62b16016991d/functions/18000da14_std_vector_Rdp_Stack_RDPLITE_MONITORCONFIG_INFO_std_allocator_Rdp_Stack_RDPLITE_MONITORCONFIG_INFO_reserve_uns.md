# std::vector<Rdp::Stack::RDPLITE_MONITORCONFIG_INFO,std::allocator<Rdp::Stack::RDPLITE_MONITORCONFIG_INFO>>::reserve(unsigned __int64)

- ea: `0x18000da14`
- end: `0x18000dab6`
- name: `?reserve@?$vector@URDPLITE_MONITORCONFIG_INFO@Stack@Rdp@@V?$allocator@URDPLITE_MONITORCONFIG_INFO@Stack@Rdp@@@std@@@std@@QEAAX_K@Z`
- size: `162`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18000c0f0`

## callees

- `0x180004958`
- `0x180008be0`
- `0x180009d98`
- `0x18000aa30`
- `0x18000d250`
- `0x18000da14`
- `0x18002834c`

## pseudocode

```c
unsigned __int64 __fastcall std::vector<Rdp::Stack::RDPLITE_MONITORCONFIG_INFO>::reserve(
        __int64 a1,
        unsigned __int64 a2)
{
  unsigned __int64 result; // rax
  __int64 v5; // rdi
  __int64 size_of; // rax
  void *v7; // rbx
  _QWORD v8[9]; // [rsp+20h] [rbp-48h] BYREF

  result = (__int64)(*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) >> 4;
  if ( a2 > result )
  {
    if ( a2 > 0xFFFFFFFFFFFFFFFLL )
      std::_Xlength_error("vector too long");
    v5 = (__int64)(*(_QWORD *)(a1 + 8) - *(_QWORD *)a1) >> 4;
    size_of = std::_Get_size_of_n<16>(a2);
    v7 = (void *)std::_Allocate<16,std::_Default_allocate_traits>(size_of);
    memmove_0(v7, *(const void **)a1, *(_QWORD *)(a1 + 8) - *(_QWORD *)a1);
    std::vector<Rdp::Stack::RDPLITE_MONITORCONFIG_INFO>::_Change_array(a1, v7, v5, a2, a1, 0, a2, v8[3], v8[4]);
    return std::vector<Rdp::Stack::RDPLITE_MONITORCONFIG_INFO>::_Reallocation_guard::~_Reallocation_guard(v8);
  }
  return result;
}

```

## disassembly

```asm
0x18000da14  push    rbx
0x18000da16  push    rbp
0x18000da17  push    rsi
0x18000da18  push    rdi
0x18000da19  sub     rsp, 48h
0x18000da1d  mov     rax, [rcx+10h]
0x18000da21  mov     rbp, rdx
0x18000da24  sub     rax, [rcx]
0x18000da27  mov     rsi, rcx
0x18000da2a  sar     rax, 4
0x18000da2e  cmp     rdx, rax
0x18000da31  jbe     short loc_18000DAAD
0x18000da33  mov     rax, 0FFFFFFFFFFFFFFFh
0x18000da3d  cmp     rdx, rax
0x18000da40  jbe     short loc_18000DA4F
0x18000da42  lea     rcx, aVectorTooLong; "vector too long"
0x18000da49  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000da4f  mov     rdi, [rcx+8]
0x18000da53  sub     rdi, [rcx]
0x18000da56  mov     rcx, rbp
0x18000da59  sar     rdi, 4
0x18000da5d  call    ??$_Get_size_of_n@$0BA@@std@@YA_K_K@Z; std::_Get_size_of_n<16>(unsigned __int64)
0x18000da62  mov     rcx, rax
0x18000da65  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000da6a  mov     r8, [rsi+8]
0x18000da6e  mov     rcx, rax; void *
0x18000da71  sub     r8, [rsi]; Size
0x18000da74  mov     rbx, rax
0x18000da77  mov     rdx, [rsi]; Src
0x18000da7a  mov     [rsp+68h+var_48], rsi
0x18000da7f  mov     [rsp+68h+var_38], rbp
0x18000da84  call    memmove_0
0x18000da89  mov     r9, rbp
0x18000da8c  mov     [rsp+68h+var_40], 0
0x18000da95  mov     r8, rdi
0x18000da98  mov     rdx, rbx
0x18000da9b  mov     rcx, rsi
0x18000da9e  call    ?_Change_array@?$vector@URDPLITE_MONITORCONFIG_INFO@Stack@Rdp@@V?$allocator@URDPLITE_MONITORCONFIG_INFO@Stack@Rdp@@@std@@@std@@AEAAXQEAURDPLITE_MONITORCONFIG_INFO@Stack@Rdp@@_K1@Z; std::vector<Rdp::Stack::RDPLITE_MONITORCONFIG_INFO>::_Change_array(Rdp::Stack::RDPLITE_MONITORCONFIG_INFO * const,unsigned __int64,unsigned __int64)
0x18000daa3  lea     rcx, [rsp+68h+var_48]
0x18000daa8  call    ??1_Reallocation_guard@?$vector@URDPLITE_MONITORCONFIG_INFO@Stack@Rdp@@V?$allocator@URDPLITE_MONITORCONFIG_INFO@Stack@Rdp@@@std@@@std@@QEAA@XZ; std::vector<Rdp::Stack::RDPLITE_MONITORCONFIG_INFO>::_Reallocation_guard::~_Reallocation_guard(void)
0x18000daad  add     rsp, 48h
0x18000dab1  pop     rdi
0x18000dab2  pop     rsi
0x18000dab3  pop     rbp
0x18000dab4  pop     rbx
0x18000dab5  retn
```
