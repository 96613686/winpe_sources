# ATL::CComVariant::InternalCopy(tagVARIANT const *)

- ea: `0x18001957c`
- end: `0x1800195a5`
- name: `?InternalCopy@CComVariant@ATL@@QEAAXPEBUtagVARIANT@@@Z`
- size: `41`
- prototype: `void __fastcall(ATL::CComVariant *__hidden this, const struct tagVARIANT *)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ab6c`
- `0x180019708`
- `0x18001e100`
- `0x18001ec30`
- `0x18001ee5c`
- `0x18001ef70`
- `0x18002938c`

## callees

- `0x18001886c`
- `0x18001957c`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x180019585`
- `OLEAUT32!__imp_VariantCopy` at `0x180019585`

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
0x18001957c  push    rbx
0x18001957e  sub     rsp, 20h
0x180019582  mov     rbx, rcx
0x180019585  call    cs:__imp_VariantCopy
0x18001958b  test    eax, eax
0x18001958d  jns     short loc_18001959F
0x18001958f  mov     ecx, eax; int
0x180019591  mov     word ptr [rbx], 0Ah
0x180019596  mov     [rbx+8], eax
0x180019599  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001959f  add     rsp, 20h
0x1800195a3  pop     rbx
0x1800195a4  retn
```
