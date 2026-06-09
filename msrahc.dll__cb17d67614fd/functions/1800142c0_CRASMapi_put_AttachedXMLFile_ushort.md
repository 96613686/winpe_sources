# CRASMapi::put_AttachedXMLFile(ushort *)

- ea: `0x1800142c0`
- end: `0x1800142d7`
- name: `?put_AttachedXMLFile@CRASMapi@@UEAAJPEAG@Z`
- size: `23`
- prototype: `__int64 __fastcall(CRASMapi *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18001277c`

## pseudocode

```c
__int64 __fastcall CRASMapi::put_AttachedXMLFile(CRASMapi *this, unsigned __int16 *a2)
{
  ATL::CComBSTR::operator=((char *)this + 1104, a2);
  return 0;
}

```

## disassembly

```asm
0x1800142c0  sub     rsp, 28h
0x1800142c4  add     rcx, 450h
0x1800142cb  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x1800142d0  xor     eax, eax
0x1800142d2  add     rsp, 28h
0x1800142d6  retn
```
