# ATL::CComBSTR::CComBSTR(ushort const *)

- ea: `0x1800094ec`
- end: `0x180009522`
- name: `??0CComBSTR@ATL@@QEAA@PEBG@Z`
- size: `54`
- prototype: `ATL::CComBSTR *__fastcall(ATL::CComBSTR *this, const unsigned __int16 *)`
- caller_count: `13`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a4ac`
- `0x18000ac60`
- `0x18000d348`
- `0x18000e078`
- `0x18000eed8`
- `0x1800163cc`
- `0x180017c68`
- `0x180018ee0`
- `0x180019dd0`
- `0x18001b4e0`
- `0x18001baf8`
- `0x18001f92c`
- `0x18001fee4`

## callees

- `0x1800042e8`
- `0x1800094ec`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180009509`
- `OLEAUT32!__imp_SysAllocString` at `0x180009509`

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
0x1800094ec  push    rbx
0x1800094ee  sub     rsp, 20h
0x1800094f2  mov     rbx, rcx
0x1800094f5  test    rdx, rdx
0x1800094f8  jnz     short loc_180009506
0x1800094fa  mov     [rcx], rdx
0x1800094fd  mov     rax, rbx
0x180009500  add     rsp, 20h
0x180009504  pop     rbx
0x180009505  retn
0x180009506  mov     rcx, rdx; psz
0x180009509  call    cs:__imp_SysAllocString
0x18000950f  mov     [rbx], rax
0x180009512  test    rax, rax
0x180009515  jnz     short loc_1800094FD
0x180009517  mov     ecx, 8007000Eh; int
0x18000951c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
