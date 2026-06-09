# std::_Uninitialized_move<DelegationConfig::DelegationPackage *,std::allocator<DelegationConfig::DelegationPackage>>(DelegationConfig::DelegationPackage * const,DelegationConfig::DelegationPackage * const,DelegationConfig::DelegationPackage *,std::allocator<DelegationConfig::DelegationPackage> &)

- ea: `0x180014e20`
- end: `0x180014e7a`
- name: `??$_Uninitialized_move@PEAUDelegationPackage@DelegationConfig@@V?$allocator@UDelegationPackage@DelegationConfig@@@std@@@std@@YAPEAUDelegationPackage@DelegationConfig@@QEAU12@0PEAU12@AEAV?$allocator@UDelegationPackage@DelegationConfig@@@0@@Z`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180014c20`

## callees

- `0x180008c74`
- `0x180014e20`
- `0x180014eac`

## pseudocode

```c
__int64 __fastcall std::_Uninitialized_move<DelegationConfig::DelegationPackage *>(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 i; // rdi

  for ( i = a1; i != a2; i += 176 )
  {
    std::construct_at<DelegationConfig::DelegationPackage,DelegationConfig::DelegationPackage>(a3, i);
    a3 += 176;
  }
  std::_Destroy_range<std::allocator<DelegationConfig::DelegationPackage>>(a3, a3);
  return a3;
}

```

## disassembly

```asm
0x180014e20  mov     [rsp+arg_0], rbx
0x180014e25  mov     [rsp+arg_8], rsi
0x180014e2a  push    rdi
0x180014e2b  sub     rsp, 20h
0x180014e2f  mov     rbx, r8
0x180014e32  mov     rsi, rdx
0x180014e35  mov     rdi, rcx
0x180014e38  cmp     rcx, rdx
0x180014e3b  jz      short loc_180014E5B
0x180014e3d  mov     rdx, rdi
0x180014e40  mov     rcx, rbx
0x180014e43  call    ??$construct_at@UDelegationPackage@DelegationConfig@@U12@@std@@YAPEAUDelegationPackage@DelegationConfig@@QEAU12@$$QEAU12@@Z; std::construct_at<DelegationConfig::DelegationPackage,DelegationConfig::DelegationPackage>(DelegationConfig::DelegationPackage * const,DelegationConfig::DelegationPackage &&)
0x180014e48  add     rbx, 0B0h
0x180014e4f  add     rdi, 0B0h
0x180014e56  cmp     rdi, rsi
0x180014e59  jnz     short loc_180014E3D
0x180014e5b  mov     rdx, rbx
0x180014e5e  mov     rcx, rbx
0x180014e61  call    ??$_Destroy_range@V?$allocator@UDelegationPackage@DelegationConfig@@@std@@@std@@YAXPEAUDelegationPackage@DelegationConfig@@QEAU12@AEAV?$allocator@UDelegationPackage@DelegationConfig@@@0@@Z; std::_Destroy_range<std::allocator<DelegationConfig::DelegationPackage>>(DelegationConfig::DelegationPackage *,DelegationConfig::DelegationPackage * const,std::allocator<DelegationConfig::DelegationPackage> &)
0x180014e66  mov     rsi, [rsp+28h+arg_8]
0x180014e6b  mov     rax, rbx
0x180014e6e  mov     rbx, [rsp+28h+arg_0]
0x180014e73  add     rsp, 20h
0x180014e77  pop     rdi
0x180014e78  retn
```
