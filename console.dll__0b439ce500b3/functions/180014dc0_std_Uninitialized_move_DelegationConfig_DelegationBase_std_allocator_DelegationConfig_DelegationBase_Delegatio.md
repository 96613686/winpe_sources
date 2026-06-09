# std::_Uninitialized_move<DelegationConfig::DelegationBase *,std::allocator<DelegationConfig::DelegationBase>>(DelegationConfig::DelegationBase * const,DelegationConfig::DelegationBase * const,DelegationConfig::DelegationBase *,std::allocator<DelegationConfig::DelegationBase> &)

- ea: `0x180014dc0`
- end: `0x180014e1a`
- name: `??$_Uninitialized_move@PEAUDelegationBase@DelegationConfig@@V?$allocator@UDelegationBase@DelegationConfig@@@std@@@std@@YAPEAUDelegationBase@DelegationConfig@@QEAU12@0PEAU12@AEAV?$allocator@UDelegationBase@DelegationConfig@@@0@@Z`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180014ac0`

## callees

- `0x180014a84`
- `0x180014dc0`
- `0x180014e80`

## pseudocode

```c
__int64 __fastcall std::_Uninitialized_move<DelegationConfig::DelegationBase *>(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 i; // rdi

  for ( i = a1; i != a2; i += 152 )
  {
    std::construct_at<DelegationConfig::DelegationBase,DelegationConfig::DelegationBase>(a3, i);
    a3 += 152;
  }
  std::_Destroy_range<std::allocator<DelegationConfig::DelegationBase>>(a3, a3);
  return a3;
}

```

## disassembly

```asm
0x180014dc0  mov     [rsp+arg_0], rbx
0x180014dc5  mov     [rsp+arg_8], rsi
0x180014dca  push    rdi
0x180014dcb  sub     rsp, 20h
0x180014dcf  mov     rbx, r8
0x180014dd2  mov     rsi, rdx
0x180014dd5  mov     rdi, rcx
0x180014dd8  cmp     rcx, rdx
0x180014ddb  jz      short loc_180014DFB
0x180014ddd  mov     rdx, rdi
0x180014de0  mov     rcx, rbx
0x180014de3  call    ??$construct_at@UDelegationBase@DelegationConfig@@U12@@std@@YAPEAUDelegationBase@DelegationConfig@@QEAU12@$$QEAU12@@Z; std::construct_at<DelegationConfig::DelegationBase,DelegationConfig::DelegationBase>(DelegationConfig::DelegationBase * const,DelegationConfig::DelegationBase &&)
0x180014de8  add     rbx, 98h
0x180014def  add     rdi, 98h
0x180014df6  cmp     rdi, rsi
0x180014df9  jnz     short loc_180014DDD
0x180014dfb  mov     rdx, rbx
0x180014dfe  mov     rcx, rbx
0x180014e01  call    ??$_Destroy_range@V?$allocator@UDelegationBase@DelegationConfig@@@std@@@std@@YAXPEAUDelegationBase@DelegationConfig@@QEAU12@AEAV?$allocator@UDelegationBase@DelegationConfig@@@0@@Z; std::_Destroy_range<std::allocator<DelegationConfig::DelegationBase>>(DelegationConfig::DelegationBase *,DelegationConfig::DelegationBase * const,std::allocator<DelegationConfig::DelegationBase> &)
0x180014e06  mov     rsi, [rsp+28h+arg_8]
0x180014e0b  mov     rax, rbx
0x180014e0e  mov     rbx, [rsp+28h+arg_0]
0x180014e13  add     rsp, 20h
0x180014e17  pop     rdi
0x180014e18  retn
```
