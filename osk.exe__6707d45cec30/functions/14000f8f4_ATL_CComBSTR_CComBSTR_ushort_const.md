# ATL::CComBSTR::CComBSTR(ushort const *)

- ea: `0x14000f8f4`
- end: `0x14000f92a`
- name: `??0CComBSTR@ATL@@QEAA@PEBG@Z`
- size: `54`
- prototype: `_QWORD(ATL::CComBSTR *__hidden this, const unsigned __int16 *)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400118d0`
- `0x140011d2c`
- `0x14001a2b4`
- `0x14001a4d8`
- `0x14001a894`
- `0x14001acc0`

## callees

- `0x140005b50`
- `0x14000f8f4`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x14000f911`
- `OLEAUT32!__imp_SysAllocString` at `0x14000f911`

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
0x14000f8f4  push    rbx
0x14000f8f6  sub     rsp, 20h
0x14000f8fa  mov     rbx, rcx
0x14000f8fd  test    rdx, rdx
0x14000f900  jnz     short loc_14000F90E
0x14000f902  mov     [rcx], rdx
0x14000f905  mov     rax, rbx
0x14000f908  add     rsp, 20h
0x14000f90c  pop     rbx
0x14000f90d  retn
0x14000f90e  mov     rcx, rdx; psz
0x14000f911  call    cs:__imp_SysAllocString
0x14000f917  mov     [rbx], rax
0x14000f91a  test    rax, rax
0x14000f91d  jnz     short loc_14000F905
0x14000f91f  mov     ecx, 8007000Eh; int
0x14000f924  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
