# _dynamic_initializer_for__CDSLink::m_aProperty__

- ea: `0x180001010`
- end: `0x18000104b`
- name: `_dynamic_initializer_for__CDSLink::m_aProperty__`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 dynamic_initializer_for__CDSLink::m_aProperty__()
{
  __int64 result; // rax
  unsigned int v1; // [rsp+14h] [rbp-14h]

  dword_18001E034 = v1;
  dword_18001E06C = v1;
  dword_18001E0A4 = v1;
  dword_18001E0DC = v1;
  result = v1;
  dword_18001E114 = v1;
  return result;
}

```

## disassembly

```asm
0x180001010  sub     rsp, 28h
0x180001014  mov     eax, [rsp+28h+var_14]
0x180001018  mov     cs:dword_18001E034, eax
0x18000101e  mov     eax, [rsp+28h+var_14]
0x180001022  mov     cs:dword_18001E06C, eax
0x180001028  mov     eax, [rsp+28h+var_14]
0x18000102c  mov     cs:dword_18001E0A4, eax
0x180001032  mov     eax, [rsp+28h+var_14]
0x180001036  mov     cs:dword_18001E0DC, eax
0x18000103c  mov     eax, [rsp+28h+var_14]
0x180001040  mov     cs:dword_18001E114, eax
0x180001046  add     rsp, 28h
0x18000104a  retn
```
