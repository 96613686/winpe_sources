# std::vector<DelegationConfig::DelegationBase,std::allocator<DelegationConfig::DelegationBase>>::_Change_array(DelegationConfig::DelegationBase * const,unsigned __int64,unsigned __int64)

- ea: `0x1800156f8`
- end: `0x18001576f`
- name: `?_Change_array@?$vector@UDelegationBase@DelegationConfig@@V?$allocator@UDelegationBase@DelegationConfig@@@std@@@std@@AEAAXQEAUDelegationBase@DelegationConfig@@_K1@Z`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180014ac0`

## callees

- `0x180008c34`
- `0x180014a84`
- `0x1800156f8`

## pseudocode

```c
__int64 __fastcall std::vector<DelegationConfig::DelegationBase>::_Change_array(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v6; // rcx
  __int64 result; // rax

  v6 = *a1;
  if ( v6 )
  {
    std::_Destroy_range<std::allocator<DelegationConfig::DelegationBase>>(v6, a1[1]);
    std::_Deallocate<16>(*a1, 8 * ((a1[2] - *a1) >> 3));
  }
  *a1 = a2;
  a1[1] = a2 + 152 * a3;
  result = a2 + 152 * a4;
  a1[2] = result;
  return result;
}

```

## disassembly

```asm
0x1800156f8  push    rbx
0x1800156fa  push    rbp
0x1800156fb  push    rsi
0x1800156fc  push    rdi
0x1800156fd  sub     rsp, 28h
0x180015701  mov     rbx, rcx
0x180015704  mov     rsi, r9
0x180015707  mov     rcx, [rcx]
0x18001570a  mov     rbp, r8
0x18001570d  mov     rdi, rdx
0x180015710  test    rcx, rcx
0x180015713  jz      short loc_180015746
0x180015715  mov     rdx, [rbx+8]
0x180015719  call    ??$_Destroy_range@V?$allocator@UDelegationBase@DelegationConfig@@@std@@@std@@YAXPEAUDelegationBase@DelegationConfig@@QEAU12@AEAV?$allocator@UDelegationBase@DelegationConfig@@@0@@Z; std::_Destroy_range<std::allocator<DelegationConfig::DelegationBase>>(DelegationConfig::DelegationBase *,DelegationConfig::DelegationBase * const,std::allocator<DelegationConfig::DelegationBase> &)
0x18001571e  mov     rax, [rbx+10h]
0x180015722  mov     rcx, 86BCA1AF286BCA1Bh
0x18001572c  sub     rax, [rbx]
0x18001572f  sar     rax, 3
0x180015733  imul    rax, rcx
0x180015737  mov     rcx, [rbx]
0x18001573a  imul    rdx, rax, 98h
0x180015741  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180015746  imul    rax, rbp, 98h
0x18001574d  mov     [rbx], rdi
0x180015750  add     rax, rdi
0x180015753  mov     [rbx+8], rax
0x180015757  imul    rax, rsi, 98h
0x18001575e  add     rax, rdi
0x180015761  mov     [rbx+10h], rax
0x180015765  add     rsp, 28h
0x180015769  pop     rdi
0x18001576a  pop     rsi
0x18001576b  pop     rbp
0x18001576c  pop     rbx
0x18001576d  retn
```
