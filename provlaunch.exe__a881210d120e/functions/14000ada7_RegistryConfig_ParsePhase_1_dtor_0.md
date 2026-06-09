# _RegistryConfig::ParsePhase_::_1_::dtor$0

- ea: `0x14000ada7`
- end: `0x14000add0`
- name: `_RegistryConfig::ParsePhase_::_1_::dtor$0`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140003560`
- `0x14000ada7`

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
0x14000ada7  push    rbp
0x14000ada9  sub     rsp, 20h
0x14000adad  mov     rbp, rdx
0x14000adb0  mov     eax, [rbp+68h]
0x14000adb3  and     eax, 1
0x14000adb6  test    eax, eax
0x14000adb8  jz      short loc_14000ADCA
0x14000adba  and     dword ptr [rbp+68h], 0FFFFFFFEh
0x14000adbe  mov     rcx, [rbp+98h]; void *
0x14000adc5  call    ??1?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAA@XZ; std::list<CommandSet>::~list<CommandSet>(void)
0x14000adca  add     rsp, 20h
0x14000adce  pop     rbp
0x14000adcf  retn
```
