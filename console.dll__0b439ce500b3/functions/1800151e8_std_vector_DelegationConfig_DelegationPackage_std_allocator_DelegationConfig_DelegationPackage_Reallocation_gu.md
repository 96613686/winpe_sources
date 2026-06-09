# std::vector<DelegationConfig::DelegationPackage,std::allocator<DelegationConfig::DelegationPackage>>::_Reallocation_guard::~_Reallocation_guard(void)

- ea: `0x1800151e8`
- end: `0x18001521d`
- name: `??1_Reallocation_guard@?$vector@UDelegationPackage@DelegationConfig@@V?$allocator@UDelegationPackage@DelegationConfig@@@std@@@std@@QEAA@XZ`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180014c20`

## callees

- `0x180008c34`
- `0x180008c74`
- `0x1800151e8`

## pseudocode

```c
__int64 __fastcall std::vector<DelegationConfig::DelegationPackage>::_Reallocation_guard::~_Reallocation_guard(
        _QWORD *a1)
{
  __int64 result; // rax

  if ( a1[1] )
  {
    std::_Destroy_range<std::allocator<DelegationConfig::DelegationPackage>>(a1[3], a1[4]);
    return std::_Deallocate<16>(a1[1], 176LL * a1[2]);
  }
  return result;
}

```

## disassembly

```asm
0x1800151e8  push    rbx
0x1800151ea  sub     rsp, 20h
0x1800151ee  cmp     qword ptr [rcx+8], 0
0x1800151f3  mov     rbx, rcx
0x1800151f6  jz      short loc_180015216
0x1800151f8  mov     rdx, [rcx+20h]
0x1800151fc  mov     rcx, [rcx+18h]
0x180015200  call    ??$_Destroy_range@V?$allocator@UDelegationPackage@DelegationConfig@@@std@@@std@@YAXPEAUDelegationPackage@DelegationConfig@@QEAU12@AEAV?$allocator@UDelegationPackage@DelegationConfig@@@0@@Z; std::_Destroy_range<std::allocator<DelegationConfig::DelegationPackage>>(DelegationConfig::DelegationPackage *,DelegationConfig::DelegationPackage * const,std::allocator<DelegationConfig::DelegationPackage> &)
0x180015205  imul    rdx, [rbx+10h], 0B0h
0x18001520d  mov     rcx, [rbx+8]
0x180015211  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180015216  add     rsp, 20h
0x18001521a  pop     rbx
0x18001521b  retn
```
