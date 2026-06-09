# ATL::CComBSTR::CComBSTR(ushort const *)

- ea: `0x180007ac8`
- end: `0x180007afe`
- name: `??0CComBSTR@ATL@@QEAA@PEBG@Z`
- size: `54`
- prototype: `ATL::CComBSTR *__fastcall(ATL::CComBSTR *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007e58`
- `0x18002032c`

## callees

- `0x180007ac8`
- `0x180007cc4`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180007ae5`
- `OLEAUT32!__imp_SysAllocString` at `0x180007ae5`

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
0x180007ac8  push    rbx
0x180007aca  sub     rsp, 20h
0x180007ace  mov     rbx, rcx
0x180007ad1  test    rdx, rdx
0x180007ad4  jnz     short loc_180007AE2
0x180007ad6  mov     [rcx], rdx
0x180007ad9  mov     rax, rbx
0x180007adc  add     rsp, 20h
0x180007ae0  pop     rbx
0x180007ae1  retn
0x180007ae2  mov     rcx, rdx; psz
0x180007ae5  call    cs:__imp_SysAllocString
0x180007aeb  mov     [rbx], rax
0x180007aee  test    rax, rax
0x180007af1  jnz     short loc_180007AD9
0x180007af3  mov     ecx, 8007000Eh; int
0x180007af8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
