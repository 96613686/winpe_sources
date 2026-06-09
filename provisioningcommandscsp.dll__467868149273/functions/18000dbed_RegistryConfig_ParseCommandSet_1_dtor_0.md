# _RegistryConfig::ParseCommandSet_::_1_::dtor$0

- ea: `0x18000dbed`
- end: `0x18000dc14`
- name: `_RegistryConfig::ParseCommandSet_::_1_::dtor$0`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000a50c`
- `0x18000dbed`

## pseudocode

```c
void __fastcall RegistryConfig::ParseCommandSet_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 64) & 1) != 0 )
  {
    *(_DWORD *)(a2 + 64) &= ~1u;
    CommandSet::~CommandSet(*(void ***)(a2 + 96));
  }
}

```

## disassembly

```asm
0x18000dbed  push    rbp
0x18000dbef  sub     rsp, 20h
0x18000dbf3  mov     rbp, rdx
0x18000dbf6  mov     eax, [rbp+40h]
0x18000dbf9  and     eax, 1
0x18000dbfc  test    eax, eax
0x18000dbfe  jz      short loc_18000DC0D
0x18000dc00  and     dword ptr [rbp+40h], 0FFFFFFFEh
0x18000dc04  mov     rcx, [rbp+60h]; this
0x18000dc08  call    ??1CommandSet@@QEAA@XZ; CommandSet::~CommandSet(void)
0x18000dc0d  add     rsp, 20h
0x18000dc11  pop     rbp
0x18000dc12  retn
```
