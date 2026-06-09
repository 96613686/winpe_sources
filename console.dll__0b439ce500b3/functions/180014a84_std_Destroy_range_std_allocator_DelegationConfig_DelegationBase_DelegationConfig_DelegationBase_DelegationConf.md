# std::_Destroy_range<std::allocator<DelegationConfig::DelegationBase>>(DelegationConfig::DelegationBase *,DelegationConfig::DelegationBase * const,std::allocator<DelegationConfig::DelegationBase> &)

- ea: `0x180014a84`
- end: `0x180014aba`
- name: `??$_Destroy_range@V?$allocator@UDelegationBase@DelegationConfig@@@std@@@std@@YAXPEAUDelegationBase@DelegationConfig@@QEAU12@AEAV?$allocator@UDelegationBase@DelegationConfig@@@0@@Z`
- size: `54`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180014dc0`
- `0x180015114`
- `0x1800151ac`
- `0x1800156f8`
- `0x180016c14`

## callees

- `0x180008cc0`
- `0x180014a84`

## pseudocode

```c
void __fastcall std::_Destroy_range<std::allocator<DelegationConfig::DelegationBase>>(__int64 a1, __int64 a2)
{
  __int64 v3; // rbx

  if ( a1 != a2 )
  {
    v3 = a1;
    do
    {
      DelegationConfig::PackageInfo::~PackageInfo((DelegationConfig::PackageInfo *)(v3 + 16));
      v3 += 152;
    }
    while ( v3 != a2 );
  }
}

```

## disassembly

```asm
0x180014a84  cmp     rcx, rdx
0x180014a87  jz      short locret_180014AB8
0x180014a89  mov     [rsp+arg_0], rbx
0x180014a8e  push    rdi
0x180014a8f  sub     rsp, 20h
0x180014a93  mov     rdi, rdx
0x180014a96  mov     rbx, rcx
0x180014a99  lea     rcx, [rbx+10h]; this
0x180014a9d  call    ??1PackageInfo@DelegationConfig@@QEAA@XZ; DelegationConfig::PackageInfo::~PackageInfo(void)
0x180014aa2  add     rbx, 98h
0x180014aa9  cmp     rbx, rdi
0x180014aac  jnz     short loc_180014A99
0x180014aae  mov     rbx, [rsp+28h+arg_0]
0x180014ab3  add     rsp, 20h
0x180014ab7  pop     rdi
0x180014ab8  retn
```
