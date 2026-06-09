# _CMSMQRuleHandler::InvokeCOMComponent_::_1_::dtor$4

- ea: `0x18001f124`
- end: `0x18001f153`
- name: `_CMSMQRuleHandler::InvokeCOMComponent_::_1_::dtor$4`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800056bc`
- `0x18001f124`

## pseudocode

```c
void __fastcall CMSMQRuleHandler::InvokeCOMComponent_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 280) & 1) != 0 )
  {
    *(_DWORD *)(a2 + 280) &= ~1u;
    _bstr_t::~_bstr_t((_bstr_t *)(a2 + 272));
  }
}

```

## disassembly

```asm
0x18001f124  push    rbp
0x18001f126  sub     rsp, 20h
0x18001f12a  mov     rbp, rdx
0x18001f12d  mov     eax, [rbp+118h]
0x18001f133  and     eax, 1
0x18001f136  test    eax, eax
0x18001f138  jz      short loc_18001F14D
0x18001f13a  and     dword ptr [rbp+118h], 0FFFFFFFEh
0x18001f141  lea     rcx, [rbp+110h]; this
0x18001f148  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001f14d  add     rsp, 20h
0x18001f151  pop     rbp
0x18001f152  retn
```
