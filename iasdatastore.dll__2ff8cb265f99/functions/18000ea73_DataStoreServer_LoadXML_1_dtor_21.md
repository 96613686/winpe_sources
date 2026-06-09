# _DataStoreServer::LoadXML_::_1_::dtor$21

- ea: `0x18000ea73`
- end: `0x18000ea9f`
- name: `_DataStoreServer::LoadXML_::_1_::dtor$21`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x1800076dc`
- `0x18000ea73`

## pseudocode

```c
void __fastcall DataStoreServer::LoadXML_::_1_::dtor_21(__int64 a1, __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 240) & 2) != 0 )
  {
    *(_DWORD *)(a2 + 240) &= ~2u;
    _bstr_t::~_bstr_t((_bstr_t *)(a2 + 88));
  }
}

```

## disassembly

```asm
0x18000ea73  push    rbp
0x18000ea75  sub     rsp, 20h
0x18000ea79  mov     rbp, rdx
0x18000ea7c  mov     eax, [rbp+0F0h]
0x18000ea82  and     eax, 2
0x18000ea85  test    eax, eax
0x18000ea87  jz      short loc_18000EA99
0x18000ea89  and     dword ptr [rbp+0F0h], 0FFFFFFFDh
0x18000ea90  lea     rcx, [rbp+58h]; this
0x18000ea94  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18000ea99  add     rsp, 20h
0x18000ea9d  pop     rbp
0x18000ea9e  retn
```
