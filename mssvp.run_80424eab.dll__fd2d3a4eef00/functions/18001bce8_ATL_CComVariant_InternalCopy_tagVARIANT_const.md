# ATL::CComVariant::InternalCopy(tagVARIANT const *)

- ea: `0x18001bce8`
- end: `0x18001bd11`
- name: `?InternalCopy@CComVariant@ATL@@QEAAXPEBUtagVARIANT@@@Z`
- size: `41`
- prototype: `void __fastcall(ATL::CComVariant *__hidden this, const struct tagVARIANT *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001c020`
- `0x18001f8e0`

## callees

- `0x18000419c`
- `0x18001bce8`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x18001bcf1`
- `OLEAUT32!__imp_VariantCopy` at `0x18001bcf1`

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
0x18001bce8  push    rbx
0x18001bcea  sub     rsp, 20h
0x18001bcee  mov     rbx, rcx
0x18001bcf1  call    cs:__imp_VariantCopy
0x18001bcf7  test    eax, eax
0x18001bcf9  jns     short loc_18001BD0B
0x18001bcfb  mov     ecx, eax; int
0x18001bcfd  mov     word ptr [rbx], 0Ah
0x18001bd02  mov     [rbx+8], eax
0x18001bd05  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001bd0b  add     rsp, 20h
0x18001bd0f  pop     rbx
0x18001bd10  retn
```
