# _DataStoreServer::LoadXML_::_1_::dtor$24

- ea: `0x18000eab7`
- end: `0x18000eae3`
- name: `_DataStoreServer::LoadXML_::_1_::dtor$24`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x1800076dc`
- `0x18000eab7`

## pseudocode

```c
void __fastcall DataStoreServer::LoadXML_::_1_::dtor_24(__int64 a1, __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 240) & 8) != 0 )
  {
    *(_DWORD *)(a2 + 240) &= ~8u;
    _bstr_t::~_bstr_t((_bstr_t *)(a2 + 80));
  }
}

```

## disassembly

```asm
0x18000eab7  push    rbp
0x18000eab9  sub     rsp, 20h
0x18000eabd  mov     rbp, rdx
0x18000eac0  mov     eax, [rbp+0F0h]
0x18000eac6  and     eax, 8
0x18000eac9  test    eax, eax
0x18000eacb  jz      short loc_18000EADD
0x18000eacd  and     dword ptr [rbp+0F0h], 0FFFFFFF7h
0x18000ead4  lea     rcx, [rbp+50h]; this
0x18000ead8  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18000eadd  add     rsp, 20h
0x18000eae1  pop     rbp
0x18000eae2  retn
```
