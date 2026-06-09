# _RegistryConfig::ParsePhase_::_1_::dtor$0

- ea: `0x18000dc1a`
- end: `0x18000dc44`
- name: `_RegistryConfig::ParsePhase_::_1_::dtor$0`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180006d20`
- `0x18000dc1a`

## pseudocode

```c
void __fastcall RegistryConfig::ParsePhase_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 104) & 1) != 0 )
  {
    *(_DWORD *)(a2 + 104) &= ~1u;
    std::list<CommandSet>::~list<CommandSet>(*(void ****)(a2 + 152));
  }
}

```

## disassembly

```asm
0x18000dc1a  push    rbp
0x18000dc1c  sub     rsp, 20h
0x18000dc20  mov     rbp, rdx
0x18000dc23  mov     eax, [rbp+68h]
0x18000dc26  and     eax, 1
0x18000dc29  test    eax, eax
0x18000dc2b  jz      short loc_18000DC3D
0x18000dc2d  and     dword ptr [rbp+68h], 0FFFFFFFEh
0x18000dc31  mov     rcx, [rbp+98h]; void *
0x18000dc38  call    ??1?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAA@XZ; std::list<CommandSet>::~list<CommandSet>(void)
0x18000dc3d  add     rsp, 20h
0x18000dc41  pop     rbp
0x18000dc42  retn
```
