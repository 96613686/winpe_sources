# UserName(CDataSource *,tagVARIANT *)

- ea: `0x1004b2c0`
- end: `0x1004b30f`
- name: `?UserName@@YGJPAVCDataSource@@PAUtagVARIANT@@@Z`
- size: `79`
- prototype: `int __stdcall(struct CDataSource *, VARIANTARG *pvargDest)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1001f2d0`
- `0x1004b2c0`

## import_xrefs

- `OLEAUT32!__imp__VariantCopy@8` at `0x1004b2f6`
- `OLEAUT32!__imp__VariantCopy@8` at `0x1004b2f6`

## pseudocode

```c
HRESULT __stdcall UserName(struct CDataSource *a1, VARIANTARG *pvargDest)
{
  JoltProperties *v2; // esi
  const VARIANTARG *v3; // eax
  unsigned int v5; // [esp+4h] [ebp-4h] BYREF

  v2 = (JoltProperties *)*((_DWORD *)a1 + 40);
  if ( JoltProperties::BinarySearch(v2, 0xCu, &v5) >= 0
    && (v3 = (const VARIANTARG *)(*((_DWORD *)v2 + 4) + 48 * v5)) != 0 )
  {
    return VariantCopy(pvargDest, v3 + 1);
  }
  else
  {
    return -2147467259;
  }
}

```

## disassembly

```asm
0x1004b2c0  mov     edi, edi
0x1004b2c2  push    ebp
0x1004b2c3  mov     ebp, esp
0x1004b2c5  push    ecx
0x1004b2c6  mov     eax, [ebp+arg_0]
0x1004b2c9  push    esi
0x1004b2ca  mov     esi, [eax+0A0h]
0x1004b2d0  lea     eax, [ebp+var_4]
0x1004b2d3  push    eax; unsigned int *
0x1004b2d4  push    0Ch; unsigned int
0x1004b2d6  mov     ecx, esi; this
0x1004b2d8  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x1004b2dd  test    eax, eax
0x1004b2df  js      short loc_1004B303
0x1004b2e1  mov     eax, [ebp+var_4]
0x1004b2e4  lea     eax, [eax+eax*2]
0x1004b2e7  shl     eax, 4
0x1004b2ea  add     eax, [esi+10h]
0x1004b2ed  jz      short loc_1004B303
0x1004b2ef  add     eax, 10h
0x1004b2f2  push    eax; pvargSrc
0x1004b2f3  push    [ebp+pvargDest]; pvargDest
0x1004b2f6  call    ds:__imp__VariantCopy@8; VariantCopy(x,x)
0x1004b2fc  pop     esi
0x1004b2fd  mov     esp, ebp
0x1004b2ff  pop     ebp
0x1004b300  retn    8
0x1004b303  mov     eax, 80004005h
0x1004b308  pop     esi
0x1004b309  mov     esp, ebp
0x1004b30b  pop     ebp
0x1004b30c  retn    8
```
