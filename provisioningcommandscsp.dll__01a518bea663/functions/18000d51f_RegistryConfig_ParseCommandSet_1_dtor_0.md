# _RegistryConfig::ParseCommandSet_::_1_::dtor$0

- ea: `0x18000d51f`
- end: `0x18000d545`
- name: `_RegistryConfig::ParseCommandSet_::_1_::dtor$0`
- size: `38`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000a010`
- `0x18000d51f`

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
0x18000d51f  push    rbp
0x18000d521  sub     rsp, 20h
0x18000d525  mov     rbp, rdx
0x18000d528  mov     eax, [rbp+40h]
0x18000d52b  and     eax, 1
0x18000d52e  test    eax, eax
0x18000d530  jz      short loc_18000D53F
0x18000d532  and     dword ptr [rbp+40h], 0FFFFFFFEh
0x18000d536  mov     rcx, [rbp+60h]; this
0x18000d53a  call    ??1CommandSet@@QEAA@XZ; CommandSet::~CommandSet(void)
0x18000d53f  add     rsp, 20h
0x18000d543  pop     rbp
0x18000d544  retn
```
