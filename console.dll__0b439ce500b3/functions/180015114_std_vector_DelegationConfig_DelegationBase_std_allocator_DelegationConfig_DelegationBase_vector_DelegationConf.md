# std::vector<DelegationConfig::DelegationBase,std::allocator<DelegationConfig::DelegationBase>>::~vector<DelegationConfig::DelegationBase,std::allocator<DelegationConfig::DelegationBase>>(void)

- ea: `0x180015114`
- end: `0x180015174`
- name: `??1?$vector@UDelegationBase@DelegationConfig@@V?$allocator@UDelegationBase@DelegationConfig@@@std@@@std@@QEAA@XZ`
- size: `96`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800195a5`
- `0x1800195b7`

## callees

- `0x180008c34`
- `0x180014a84`
- `0x180015114`

## pseudocode

```c
__int64 __fastcall std::vector<DelegationConfig::DelegationBase>::~vector<DelegationConfig::DelegationBase>(
        __int64 *a1)
{
  __int64 v2; // rcx
  __int64 result; // rax

  v2 = *a1;
  if ( v2 )
  {
    std::_Destroy_range<std::allocator<DelegationConfig::DelegationBase>>(v2, a1[1]);
    result = std::_Deallocate<16>(*a1, 8 * ((a1[2] - *a1) >> 3));
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180015114  push    rbx
0x180015116  sub     rsp, 20h
0x18001511a  mov     rbx, rcx
0x18001511d  mov     rcx, [rcx]
0x180015120  test    rcx, rcx
0x180015123  jz      short loc_18001516D
0x180015125  mov     rdx, [rbx+8]
0x180015129  call    ??$_Destroy_range@V?$allocator@UDelegationBase@DelegationConfig@@@std@@@std@@YAXPEAUDelegationBase@DelegationConfig@@QEAU12@AEAV?$allocator@UDelegationBase@DelegationConfig@@@0@@Z; std::_Destroy_range<std::allocator<DelegationConfig::DelegationBase>>(DelegationConfig::DelegationBase *,DelegationConfig::DelegationBase * const,std::allocator<DelegationConfig::DelegationBase> &)
0x18001512e  mov     rax, [rbx+10h]
0x180015132  mov     rcx, 86BCA1AF286BCA1Bh
0x18001513c  sub     rax, [rbx]
0x18001513f  sar     rax, 3
0x180015143  imul    rax, rcx
0x180015147  mov     rcx, [rbx]
0x18001514a  imul    rdx, rax, 98h
0x180015151  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180015156  mov     qword ptr [rbx], 0
0x18001515d  mov     qword ptr [rbx+8], 0
0x180015165  mov     qword ptr [rbx+10h], 0
0x18001516d  add     rsp, 20h
0x180015171  pop     rbx
0x180015172  retn
```
