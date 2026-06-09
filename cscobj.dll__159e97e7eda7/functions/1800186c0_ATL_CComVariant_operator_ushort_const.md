# ATL::CComVariant::operator=(ushort const *)

- ea: `0x1800186c0`
- end: `0x180018713`
- name: `??4CComVariant@ATL@@QEAAAEAV01@PEBG@Z`
- size: `83`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001b674`
- `0x18001dc18`
- `0x18001e100`
- `0x1800230ac`
- `0x1800281bc`

## callees

- `0x1800186c0`
- `0x18001886c`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800186de`
- `OLEAUT32!__imp_SysAllocString` at `0x1800186de`
- `OLEAUT32!__imp_VariantClear` at `0x1800186d0`
- `OLEAUT32!__imp_VariantClear` at `0x1800186d0`

## pseudocode

```c
VARIANTARG *__fastcall ATL::CComVariant::operator=(VARIANTARG *a1, const OLECHAR *a2)
{
  BSTR v4; // rax

  VariantClear(a1);
  a1->vt = 8;
  v4 = SysAllocString(a2);
  a1->llVal = (LONGLONG)v4;
  if ( !v4 && a2 )
  {
    a1->vt = 10;
    a1->lVal = -2147024882;
    ATL::AtlThrowImpl(-2147024882);
  }
  return a1;
}

```

## disassembly

```asm
0x1800186c0  mov     [rsp+arg_0], rbx
0x1800186c5  push    rdi
0x1800186c6  sub     rsp, 20h
0x1800186ca  mov     rdi, rdx
0x1800186cd  mov     rbx, rcx
0x1800186d0  call    cs:__imp_VariantClear
0x1800186d6  mov     rcx, rdi; psz
0x1800186d9  mov     word ptr [rbx], 8
0x1800186de  call    cs:__imp_SysAllocString
0x1800186e4  mov     [rbx+8], rax
0x1800186e8  test    rax, rax
0x1800186eb  jnz     short loc_180018705
0x1800186ed  test    rdi, rdi
0x1800186f0  jz      short loc_180018705
0x1800186f2  mov     ecx, 8007000Eh; int
0x1800186f7  mov     word ptr [rbx], 0Ah
0x1800186fc  mov     [rbx+8], ecx
0x1800186ff  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180018705  mov     rax, rbx
0x180018708  mov     rbx, [rsp+28h+arg_0]
0x18001870d  add     rsp, 20h
0x180018711  pop     rdi
0x180018712  retn
```
