# LsaLookuprOpenPolicy2_notify

- ea: `0x140001670`
- end: `0x14000168a`
- name: `LsaLookuprOpenPolicy2_notify`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x140001670`
- `0x140006010`

## pseudocode

```c
__int64 LsaLookuprOpenPolicy2_notify()
{
  __int64 result; // rax

  result = gLsapLookupExtension;
  if ( gLsapLookupExtension )
  {
    result = *(_QWORD *)(gLsapLookupExtension + 88);
    if ( result )
      return guard_dispatch_icall_thunk_10345483385596137414();
  }
  return result;
}

```

## disassembly

```asm
0x140001670  mov     rax, cs:gLsapLookupExtension
0x140001677  test    rax, rax
0x14000167a  jz      short locret_140001689
0x14000167c  mov     rax, [rax+58h]
0x140001680  test    rax, rax
0x140001683  jnz     _guard_dispatch_icall$thunk$10345483385596137414
0x140001689  retn
```
