# std::_Destroy_range<std::allocator<DelegationConfig::DelegationPackage>>(DelegationConfig::DelegationPackage *,DelegationConfig::DelegationPackage * const,std::allocator<DelegationConfig::DelegationPackage> &)

- ea: `0x180008c74`
- end: `0x180008caa`
- name: `??$_Destroy_range@V?$allocator@UDelegationPackage@DelegationConfig@@@std@@@std@@YAXPEAUDelegationPackage@DelegationConfig@@QEAU12@AEAV?$allocator@UDelegationPackage@DelegationConfig@@@0@@Z`
- size: `54`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180014e20`
- `0x1800151e8`
- `0x180015778`
- `0x180016c14`
- `0x1800196e0`

## callees

- `0x180008c74`
- `0x180008cc0`

## pseudocode

```c
void __fastcall std::_Destroy_range<std::allocator<DelegationConfig::DelegationPackage>>(__int64 a1, __int64 a2)
{
  __int64 v3; // rbx

  if ( a1 != a2 )
  {
    v3 = a1;
    do
    {
      DelegationConfig::PackageInfo::~PackageInfo((DelegationConfig::PackageInfo *)(v3 + 40));
      v3 += 176;
    }
    while ( v3 != a2 );
  }
}

```

## disassembly

```asm
0x180008c74  cmp     rcx, rdx
0x180008c77  jz      short locret_180008CA8
0x180008c79  mov     [rsp+arg_0], rbx
0x180008c7e  push    rdi
0x180008c7f  sub     rsp, 20h
0x180008c83  mov     rdi, rdx
0x180008c86  mov     rbx, rcx
0x180008c89  lea     rcx, [rbx+28h]; this
0x180008c8d  call    ??1PackageInfo@DelegationConfig@@QEAA@XZ; DelegationConfig::PackageInfo::~PackageInfo(void)
0x180008c92  add     rbx, 0B0h
0x180008c99  cmp     rbx, rdi
0x180008c9c  jnz     short loc_180008C89
0x180008c9e  mov     rbx, [rsp+28h+arg_0]
0x180008ca3  add     rsp, 20h
0x180008ca7  pop     rdi
0x180008ca8  retn
```
