# ATL::CComVariant::InternalCopy(tagVARIANT const *)

- ea: `0x18001ad28`
- end: `0x18001ad51`
- name: `?InternalCopy@CComVariant@ATL@@QEAAXPEBUtagVARIANT@@@Z`
- size: `41`
- prototype: `void __fastcall(VARIANTARG *this, const struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800019b0`

## callees

- `0x18001a728`
- `0x18001ad28`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x18001ad31`
- `OLEAUT32!__imp_VariantCopy` at `0x18001ad31`

## pseudocode

```c
void __fastcall ATL::CComVariant::InternalCopy(VARIANTARG *this, const struct tagVARIANT *a2)
{
  HRESULT v3; // eax

  v3 = VariantCopy(this, a2);
  if ( v3 < 0 )
  {
    this->vt = 10;
    this->lVal = v3;
    ATL::AtlThrowImpl(v3);
  }
}

```

## disassembly

```asm
0x18001ad28  push    rbx
0x18001ad2a  sub     rsp, 20h
0x18001ad2e  mov     rbx, rcx
0x18001ad31  call    cs:__imp_VariantCopy
0x18001ad37  test    eax, eax
0x18001ad39  jns     short loc_18001AD4B
0x18001ad3b  mov     ecx, eax; int
0x18001ad3d  mov     word ptr [rbx], 0Ah
0x18001ad42  mov     [rbx+8], eax
0x18001ad45  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001ad4b  add     rsp, 20h
0x18001ad4f  pop     rbx
0x18001ad50  retn
```
