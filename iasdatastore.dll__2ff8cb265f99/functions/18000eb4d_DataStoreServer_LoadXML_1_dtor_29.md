# _DataStoreServer::LoadXML_::_1_::dtor$29

- ea: `0x18000eb4d`
- end: `0x18000eb7c`
- name: `_DataStoreServer::LoadXML_::_1_::dtor$29`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x1800076dc`
- `0x18000eb4d`

## pseudocode

```c
void __fastcall DataStoreServer::LoadXML_::_1_::dtor_29(__int64 a1, __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 240) & 0x80) != 0 )
  {
    *(_DWORD *)(a2 + 240) &= ~0x80u;
    _bstr_t::~_bstr_t((_bstr_t *)(a2 + 56));
  }
}

```

## disassembly

```asm
0x18000eb4d  push    rbp
0x18000eb4f  sub     rsp, 20h
0x18000eb53  mov     rbp, rdx
0x18000eb56  mov     eax, [rbp+0F0h]
0x18000eb5c  and     eax, 80h
0x18000eb61  test    eax, eax
0x18000eb63  jz      short loc_18000EB76
0x18000eb65  btr     dword ptr [rbp+0F0h], 7
0x18000eb6d  lea     rcx, [rbp+38h]; this
0x18000eb71  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18000eb76  add     rsp, 20h
0x18000eb7a  pop     rbp
0x18000eb7b  retn
```
