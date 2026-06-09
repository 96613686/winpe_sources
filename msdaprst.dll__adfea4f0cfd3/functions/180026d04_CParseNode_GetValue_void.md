# CParseNode::GetValue(void)

- ea: `0x180026d04`
- end: `0x180026d16`
- name: `?GetValue@CParseNode@@QEAAAEAVCComBSTR@ATL@@XZ`
- size: `18`
- prototype: `struct ATL::CComBSTR *__fastcall(CParseNode *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180024434`
- `0x1800248d8`
- `0x180026a9c`
- `0x1800275e4`
- `0x18002851c`
- `0x1800287cc`

## callees

- `0x180026d04`

## pseudocode

```c
struct ATL::CComBSTR *__fastcall CParseNode::GetValue(CParseNode *this)
{
  struct ATL::CComBSTR *result; // rax

  result = (CParseNode *)((char *)this + 48);
  if ( !*((_QWORD *)this + 6) )
    return (struct ATL::CComBSTR *)&CParseNode::s_bstrZLS;
  return result;
}

```

## disassembly

```asm
0x180026d04  lea     rax, [rcx+30h]
0x180026d08  cmp     qword ptr [rax], 0
0x180026d0c  jnz     short locret_180026D15
0x180026d0e  lea     rax, ?s_bstrZLS@CParseNode@@0VCComBSTR@ATL@@A; ATL::CComBSTR CParseNode::s_bstrZLS
0x180026d15  retn
```
