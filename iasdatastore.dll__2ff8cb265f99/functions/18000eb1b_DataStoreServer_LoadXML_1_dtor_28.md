# _DataStoreServer::LoadXML_::_1_::dtor$28

- ea: `0x18000eb1b`
- end: `0x18000eb47`
- name: `_DataStoreServer::LoadXML_::_1_::dtor$28`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x1800076dc`
- `0x18000eb1b`

## pseudocode

```c
void __fastcall DataStoreServer::LoadXML_::_1_::dtor_28(__int64 a1, __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 240) & 0x40) != 0 )
  {
    *(_DWORD *)(a2 + 240) &= ~0x40u;
    _bstr_t::~_bstr_t((_bstr_t *)(a2 + 64));
  }
}

```

## disassembly

```asm
0x18000eb1b  push    rbp
0x18000eb1d  sub     rsp, 20h
0x18000eb21  mov     rbp, rdx
0x18000eb24  mov     eax, [rbp+0F0h]
0x18000eb2a  and     eax, 40h
0x18000eb2d  test    eax, eax
0x18000eb2f  jz      short loc_18000EB41
0x18000eb31  and     dword ptr [rbp+0F0h], 0FFFFFFBFh
0x18000eb38  lea     rcx, [rbp+40h]; this
0x18000eb3c  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18000eb41  add     rsp, 20h
0x18000eb45  pop     rbp
0x18000eb46  retn
```
