# ATL::CComVariant::operator=(ushort const *)

- ea: `0x18001227c`
- end: `0x1800122ce`
- name: `??4CComVariant@ATL@@QEAAAEAV01@PEBG@Z`
- size: `82`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001cf30`
- `0x18001d130`

## callees

- `0x18001227c`
- `0x18001cbbc`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001229a`
- `OLEAUT32!__imp_SysAllocString` at `0x18001229a`
- `OLEAUT32!__imp_VariantClear` at `0x18001228c`
- `OLEAUT32!__imp_VariantClear` at `0x18001228c`

## pseudocode

```c
VARIANTARG *__fastcall ATL::CComVariant::operator=(VARIANTARG *a1, const OLECHAR *a2)
{
  BSTR v4; // rax
  int v5; // ecx

  VariantClear(a1);
  a1->vt = 8;
  v4 = SysAllocString(a2);
  a1->llVal = (LONGLONG)v4;
  if ( !v4 && a2 )
  {
    a1->vt = 10;
    a1->lVal = -2147024882;
    ATL::AtlThrowImpl(v5);
  }
  return a1;
}

```

## disassembly

```asm
0x18001227c  mov     [rsp+arg_0], rbx
0x180012281  push    rdi
0x180012282  sub     rsp, 20h
0x180012286  mov     rdi, rdx
0x180012289  mov     rbx, rcx
0x18001228c  call    cs:__imp_VariantClear
0x180012292  mov     rcx, rdi; psz
0x180012295  mov     word ptr [rbx], 8
0x18001229a  call    cs:__imp_SysAllocString
0x1800122a0  mov     [rbx+8], rax
0x1800122a4  test    rax, rax
0x1800122a7  jnz     short loc_1800122C0
0x1800122a9  test    rdi, rdi
0x1800122ac  jz      short loc_1800122C0
0x1800122ae  mov     word ptr [rbx], 0Ah
0x1800122b3  mov     dword ptr [rbx+8], 8007000Eh
0x1800122ba  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800122c0  mov     rax, rbx
0x1800122c3  mov     rbx, [rsp+28h+arg_0]
0x1800122c8  add     rsp, 20h
0x1800122cc  pop     rdi
0x1800122cd  retn
```
