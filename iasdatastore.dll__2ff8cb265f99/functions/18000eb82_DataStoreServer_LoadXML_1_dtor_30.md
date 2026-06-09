# _DataStoreServer::LoadXML_::_1_::dtor$30

- ea: `0x18000eb82`
- end: `0x18000ebb4`
- name: `_DataStoreServer::LoadXML_::_1_::dtor$30`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x1800076dc`
- `0x18000eb82`

## pseudocode

```c
void __fastcall DataStoreServer::LoadXML_::_1_::dtor_30(__int64 a1, __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 240) & 0x100) != 0 )
  {
    *(_DWORD *)(a2 + 240) &= ~0x100u;
    _bstr_t::~_bstr_t((_bstr_t *)(a2 + 264));
  }
}

```

## disassembly

```asm
0x18000eb82  push    rbp
0x18000eb84  sub     rsp, 20h
0x18000eb88  mov     rbp, rdx
0x18000eb8b  mov     eax, [rbp+0F0h]
0x18000eb91  and     eax, 100h
0x18000eb96  test    eax, eax
0x18000eb98  jz      short loc_18000EBAE
0x18000eb9a  btr     dword ptr [rbp+0F0h], 8
0x18000eba2  lea     rcx, [rbp+108h]; this
0x18000eba9  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18000ebae  add     rsp, 20h
0x18000ebb2  pop     rbp
0x18000ebb3  retn
```
