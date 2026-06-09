# ATL::CComBSTR::CComBSTR(ushort const *)

- ea: `0x18001256c`
- end: `0x18001259d`
- name: `??0CComBSTR@ATL@@QEAA@PEBG@Z`
- size: `49`
- prototype: `_QWORD(ATL::CComBSTR *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001cf30`
- `0x18001d130`

## callees

- `0x18001256c`
- `0x18001cbbc`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180012589`
- `OLEAUT32!__imp_SysAllocString` at `0x180012589`

## pseudocode

```c
ATL::CComBSTR *__fastcall ATL::CComBSTR::CComBSTR(ATL::CComBSTR *this, const unsigned __int16 *a2)
{
  BSTR v4; // rax
  int v5; // ecx

  if ( a2 )
  {
    v4 = SysAllocString(a2);
    *(_QWORD *)this = v4;
    if ( !v4 )
      ATL::AtlThrowImpl(v5);
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
0x18001256c  push    rbx
0x18001256e  sub     rsp, 20h
0x180012572  mov     rbx, rcx
0x180012575  test    rdx, rdx
0x180012578  jnz     short loc_180012586
0x18001257a  mov     [rcx], rdx
0x18001257d  mov     rax, rbx
0x180012580  add     rsp, 20h
0x180012584  pop     rbx
0x180012585  retn
0x180012586  mov     rcx, rdx; psz
0x180012589  call    cs:__imp_SysAllocString
0x18001258f  mov     [rbx], rax
0x180012592  test    rax, rax
0x180012595  jnz     short loc_18001257D
0x180012597  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
