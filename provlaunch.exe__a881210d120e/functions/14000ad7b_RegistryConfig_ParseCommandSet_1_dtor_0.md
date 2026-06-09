# _RegistryConfig::ParseCommandSet_::_1_::dtor$0

- ea: `0x14000ad7b`
- end: `0x14000ada1`
- name: `_RegistryConfig::ParseCommandSet_::_1_::dtor$0`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140007ce0`
- `0x14000ad7b`

## pseudocode

```c
void __fastcall RegistryConfig::ParseCommandSet_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 64) & 1) != 0 )
  {
    *(_DWORD *)(a2 + 64) &= ~1u;
    CommandSet::~CommandSet(*(CommandSet **)(a2 + 96));
  }
}

```

## disassembly

```asm
0x14000ad7b  push    rbp
0x14000ad7d  sub     rsp, 20h
0x14000ad81  mov     rbp, rdx
0x14000ad84  mov     eax, [rbp+40h]
0x14000ad87  and     eax, 1
0x14000ad8a  test    eax, eax
0x14000ad8c  jz      short loc_14000AD9B
0x14000ad8e  and     dword ptr [rbp+40h], 0FFFFFFFEh
0x14000ad92  mov     rcx, [rbp+60h]; this
0x14000ad96  call    ??1CommandSet@@QEAA@XZ; CommandSet::~CommandSet(void)
0x14000ad9b  add     rsp, 20h
0x14000ad9f  pop     rbp
0x14000ada0  retn
```
