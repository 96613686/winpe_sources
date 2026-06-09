# std::vector<DelegationConfig::DelegationBase,std::allocator<DelegationConfig::DelegationBase>>::_Reallocation_guard::~_Reallocation_guard(void)

- ea: `0x1800151ac`
- end: `0x1800151e1`
- name: `??1_Reallocation_guard@?$vector@UDelegationBase@DelegationConfig@@V?$allocator@UDelegationBase@DelegationConfig@@@std@@@std@@QEAA@XZ`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180014ac0`

## callees

- `0x180008c34`
- `0x180014a84`
- `0x1800151ac`

## pseudocode

```c
__int64 __fastcall std::vector<DelegationConfig::DelegationBase>::_Reallocation_guard::~_Reallocation_guard(_QWORD *a1)
{
  __int64 result; // rax

  if ( a1[1] )
  {
    std::_Destroy_range<std::allocator<DelegationConfig::DelegationBase>>(a1[3], a1[4]);
    return std::_Deallocate<16>(a1[1], 152LL * a1[2]);
  }
  return result;
}

```

## disassembly

```asm
0x1800151ac  push    rbx
0x1800151ae  sub     rsp, 20h
0x1800151b2  cmp     qword ptr [rcx+8], 0
0x1800151b7  mov     rbx, rcx
0x1800151ba  jz      short loc_1800151DA
0x1800151bc  mov     rdx, [rcx+20h]
0x1800151c0  mov     rcx, [rcx+18h]
0x1800151c4  call    ??$_Destroy_range@V?$allocator@UDelegationBase@DelegationConfig@@@std@@@std@@YAXPEAUDelegationBase@DelegationConfig@@QEAU12@AEAV?$allocator@UDelegationBase@DelegationConfig@@@0@@Z; std::_Destroy_range<std::allocator<DelegationConfig::DelegationBase>>(DelegationConfig::DelegationBase *,DelegationConfig::DelegationBase * const,std::allocator<DelegationConfig::DelegationBase> &)
0x1800151c9  imul    rdx, [rbx+10h], 98h
0x1800151d1  mov     rcx, [rbx+8]
0x1800151d5  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800151da  add     rsp, 20h
0x1800151de  pop     rbx
0x1800151df  retn
```
