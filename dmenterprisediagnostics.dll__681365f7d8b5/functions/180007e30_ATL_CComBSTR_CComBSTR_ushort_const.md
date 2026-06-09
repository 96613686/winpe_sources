# ATL::CComBSTR::CComBSTR(ushort const *)

- ea: `0x180007e30`
- end: `0x180007e6d`
- name: `??0CComBSTR@ATL@@QEAA@PEBG@Z`
- size: `61`
- prototype: `_QWORD(ATL::CComBSTR *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800081e4`
- `0x18002101c`

## callees

- `0x180007e30`
- `0x180008044`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180007e4e`
- `OLEAUT32!__imp_SysAllocString` at `0x180007e4e`

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
0x180007e30  push    rbx
0x180007e32  sub     rsp, 20h
0x180007e36  mov     rbx, rcx
0x180007e39  test    rdx, rdx
0x180007e3c  jnz     short loc_180007E4B
0x180007e3e  mov     [rcx], rdx
0x180007e41  mov     rax, rbx
0x180007e44  add     rsp, 20h
0x180007e48  pop     rbx
0x180007e49  retn
0x180007e4b  mov     rcx, rdx; psz
0x180007e4e  call    cs:__imp_SysAllocString
0x180007e55  nop     dword ptr [rax+rax+00h]
0x180007e5a  mov     [rbx], rax
0x180007e5d  test    rax, rax
0x180007e60  jnz     short loc_180007E41
0x180007e62  mov     ecx, 8007000Eh; int
0x180007e67  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
