# _RegistryConfig::ParsePhase_::_1_::dtor$0

- ea: `0x18000d54b`
- end: `0x18000d574`
- name: `_RegistryConfig::ParsePhase_::_1_::dtor$0`
- size: `41`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180006a00`
- `0x18000d54b`

## pseudocode

```c
void __fastcall RegistryConfig::ParsePhase_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 104) & 1) != 0 )
  {
    *(_DWORD *)(a2 + 104) &= ~1u;
    std::list<CommandSet>::~list<CommandSet>(*(_QWORD **)(a2 + 152));
  }
}

```

## disassembly

```asm
0x18000d54b  push    rbp
0x18000d54d  sub     rsp, 20h
0x18000d551  mov     rbp, rdx
0x18000d554  mov     eax, [rbp+68h]
0x18000d557  and     eax, 1
0x18000d55a  test    eax, eax
0x18000d55c  jz      short loc_18000D56E
0x18000d55e  and     dword ptr [rbp+68h], 0FFFFFFFEh
0x18000d562  mov     rcx, [rbp+98h]; void *
0x18000d569  call    ??1?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAA@XZ; std::list<CommandSet>::~list<CommandSet>(void)
0x18000d56e  add     rsp, 20h
0x18000d572  pop     rbp
0x18000d573  retn
```
