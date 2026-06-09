# ATL::CComBSTR::CComBSTR(ushort const *)

- ea: `0x18000be54`
- end: `0x18000be8a`
- name: `??0CComBSTR@ATL@@QEAA@PEBG@Z`
- size: `54`
- prototype: `ATL::CComBSTR *__fastcall(ATL::CComBSTR *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180010964`

## callees

- `0x18000b48c`
- `0x18000be54`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000be71`
- `OLEAUT32!__imp_SysAllocString` at `0x18000be71`

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
0x18000be54  push    rbx
0x18000be56  sub     rsp, 20h
0x18000be5a  mov     rbx, rcx
0x18000be5d  test    rdx, rdx
0x18000be60  jnz     short loc_18000BE6E
0x18000be62  mov     [rcx], rdx
0x18000be65  mov     rax, rbx
0x18000be68  add     rsp, 20h
0x18000be6c  pop     rbx
0x18000be6d  retn
0x18000be6e  mov     rcx, rdx; psz
0x18000be71  call    cs:__imp_SysAllocString
0x18000be77  mov     [rbx], rax
0x18000be7a  test    rax, rax
0x18000be7d  jnz     short loc_18000BE65
0x18000be7f  mov     ecx, 8007000Eh; int
0x18000be84  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
