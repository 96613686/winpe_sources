# std::vector<DISPLAYCONFIG_PATH_INFO,std::allocator<DISPLAYCONFIG_PATH_INFO>>::_Construct_n<>(unsigned __int64)

- ea: `0x14000df8c`
- end: `0x14000dfed`
- name: `??$_Construct_n@$$V@?$vector@UDISPLAYCONFIG_PATH_INFO@@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@AEAAX_K@Z`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000e7e4`

## callees

- `0x1400061b8`
- `0x14000df8c`
- `0x14000e178`
- `0x14000f004`

## pseudocode

```c
__int64 __fastcall std::vector<DISPLAYCONFIG_PATH_INFO>::_Construct_n<>(void **a1, __int64 a2)
{
  __int64 v2; // rbx
  char *v4; // rdi
  int v5; // edx
  __int64 result; // rax
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF

  if ( a2 )
  {
    v2 = a2;
    std::vector<DISPLAYCONFIG_PATH_INFO>::_Buy_nonzero();
    v4 = (char *)*a1;
    LOBYTE(v5) = 0;
    memset_0(*a1, v5, 72 * v2);
    do
    {
      v4 += 72;
      --v2;
    }
    while ( v2 );
    a1[1] = v4;
    v7 = 0;
    return std::_Tidy_guard<std::vector<DISPLAYCONFIG_PATH_INFO>>::~_Tidy_guard<std::vector<DISPLAYCONFIG_PATH_INFO>>(&v7);
  }
  return result;
}

```

## disassembly

```asm
0x14000df8c  test    rdx, rdx
0x14000df8f  jz      short locret_14000DFEC
0x14000df91  mov     [rsp+arg_8], rbx
0x14000df96  mov     [rsp+arg_10], rsi
0x14000df9b  push    rdi
0x14000df9c  sub     rsp, 20h
0x14000dfa0  mov     rbx, rdx
0x14000dfa3  mov     rsi, rcx
0x14000dfa6  call    ?_Buy_nonzero@?$vector@UDISPLAYCONFIG_PATH_INFO@@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@AEAAX_K@Z; std::vector<DISPLAYCONFIG_PATH_INFO>::_Buy_nonzero(unsigned __int64)
0x14000dfab  mov     rdi, [rsi]
0x14000dfae  lea     r8, [rbx+rbx*8]
0x14000dfb2  shl     r8, 3; Size
0x14000dfb6  xor     dl, dl; Val
0x14000dfb8  mov     rcx, rdi; void *
0x14000dfbb  call    memset_0
0x14000dfc0  add     rdi, 48h ; 'H'
0x14000dfc4  sub     rbx, 1
0x14000dfc8  jnz     short loc_14000DFC0
0x14000dfca  lea     rcx, [rsp+28h+arg_0]
0x14000dfcf  mov     [rsi+8], rdi
0x14000dfd3  mov     [rsp+28h+arg_0], rbx
0x14000dfd8  call    ??1?$_Tidy_guard@V?$vector@UDISPLAYCONFIG_PATH_INFO@@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<DISPLAYCONFIG_PATH_INFO>>::~_Tidy_guard<std::vector<DISPLAYCONFIG_PATH_INFO>>(void)
0x14000dfdd  mov     rbx, [rsp+28h+arg_8]
0x14000dfe2  mov     rsi, [rsp+28h+arg_10]
0x14000dfe7  add     rsp, 20h
0x14000dfeb  pop     rdi
0x14000dfec  retn
```
