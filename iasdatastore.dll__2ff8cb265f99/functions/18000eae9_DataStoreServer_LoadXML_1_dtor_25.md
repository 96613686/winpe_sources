# _DataStoreServer::LoadXML_::_1_::dtor$25

- ea: `0x18000eae9`
- end: `0x18000eb15`
- name: `_DataStoreServer::LoadXML_::_1_::dtor$25`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x1800076dc`
- `0x18000eae9`

## pseudocode

```c
void __fastcall DataStoreServer::LoadXML_::_1_::dtor_25(__int64 a1, __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 240) & 0x10) != 0 )
  {
    *(_DWORD *)(a2 + 240) &= ~0x10u;
    _bstr_t::~_bstr_t((_bstr_t *)(a2 + 72));
  }
}

```

## disassembly

```asm
0x18000eae9  push    rbp
0x18000eaeb  sub     rsp, 20h
0x18000eaef  mov     rbp, rdx
0x18000eaf2  mov     eax, [rbp+0F0h]
0x18000eaf8  and     eax, 10h
0x18000eafb  test    eax, eax
0x18000eafd  jz      short loc_18000EB0F
0x18000eaff  and     dword ptr [rbp+0F0h], 0FFFFFFEFh
0x18000eb06  lea     rcx, [rbp+48h]; this
0x18000eb0a  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18000eb0f  add     rsp, 20h
0x18000eb13  pop     rbp
0x18000eb14  retn
```
