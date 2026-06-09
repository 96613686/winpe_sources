# ATL::CComBSTR::CComBSTR(ushort const *)

- ea: `0x180025a88`
- end: `0x180025abe`
- name: `??0CComBSTR@ATL@@QEAA@PEBG@Z`
- size: `54`
- prototype: `_QWORD(ATL::CComBSTR *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180025e44`
- `0x180025f20`

## callees

- `0x18000afe0`
- `0x180025a88`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180025aa5`
- `OLEAUT32!__imp_SysAllocString` at `0x180025aa5`

## pseudocode

```c
ATL::CComBSTR *__fastcall ATL::CComBSTR::CComBSTR(ATL::CComBSTR *this, const unsigned __int16 *a2)
{
  BSTR v4; // rax

  if ( a2 )
  {
    v4 = SysAllocString(a2);
    *(_QWORD *)this = v4;
    if ( !v4 )
      ATL::AtlThrowImpl(-2147024882);
  }
  else
  {
    *(_QWORD *)this = 0;
  }
  return this;
}

```

## disassembly

```asm
0x180025a88  push    rbx
0x180025a8a  sub     rsp, 20h
0x180025a8e  mov     rbx, rcx
0x180025a91  test    rdx, rdx
0x180025a94  jnz     short loc_180025AA2
0x180025a96  mov     [rcx], rdx
0x180025a99  mov     rax, rbx
0x180025a9c  add     rsp, 20h
0x180025aa0  pop     rbx
0x180025aa1  retn
0x180025aa2  mov     rcx, rdx; psz
0x180025aa5  call    cs:__imp_SysAllocString
0x180025aab  mov     [rbx], rax
0x180025aae  test    rax, rax
0x180025ab1  jnz     short loc_180025A99
0x180025ab3  mov     ecx, 8007000Eh; int
0x180025ab8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
