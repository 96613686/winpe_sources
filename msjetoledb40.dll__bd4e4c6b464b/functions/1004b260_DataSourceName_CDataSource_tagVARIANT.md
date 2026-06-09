# DataSourceName(CDataSource *,tagVARIANT *)

- ea: `0x1004b260`
- end: `0x1004b2af`
- name: `?DataSourceName@@YGJPAVCDataSource@@PAUtagVARIANT@@@Z`
- size: `79`
- prototype: `int __stdcall(struct CDataSource *, VARIANTARG *pvargDest)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1001f2d0`
- `0x1004b260`

## import_xrefs

- `OLEAUT32!__imp__VariantCopy@8` at `0x1004b296`
- `OLEAUT32!__imp__VariantCopy@8` at `0x1004b296`

## pseudocode

```c
HRESULT __stdcall DataSourceName(struct CDataSource *a1, VARIANTARG *pvargDest)
{
  JoltProperties *v2; // esi
  const VARIANTARG *v3; // eax
  unsigned int v5; // [esp+4h] [ebp-4h] BYREF

  v2 = (JoltProperties *)*((_DWORD *)a1 + 40);
  if ( JoltProperties::BinarySearch(v2, 0x3Bu, &v5) >= 0
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
0x1004b260  mov     edi, edi
0x1004b262  push    ebp
0x1004b263  mov     ebp, esp
0x1004b265  push    ecx
0x1004b266  mov     eax, [ebp+arg_0]
0x1004b269  push    esi
0x1004b26a  mov     esi, [eax+0A0h]
0x1004b270  lea     eax, [ebp+var_4]
0x1004b273  push    eax; unsigned int *
0x1004b274  push    3Bh ; ';'; unsigned int
0x1004b276  mov     ecx, esi; this
0x1004b278  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x1004b27d  test    eax, eax
0x1004b27f  js      short loc_1004B2A3
0x1004b281  mov     eax, [ebp+var_4]
0x1004b284  lea     eax, [eax+eax*2]
0x1004b287  shl     eax, 4
0x1004b28a  add     eax, [esi+10h]
0x1004b28d  jz      short loc_1004B2A3
0x1004b28f  add     eax, 10h
0x1004b292  push    eax; pvargSrc
0x1004b293  push    [ebp+pvargDest]; pvargDest
0x1004b296  call    ds:__imp__VariantCopy@8; VariantCopy(x,x)
0x1004b29c  pop     esi
0x1004b29d  mov     esp, ebp
0x1004b29f  pop     ebp
0x1004b2a0  retn    8
0x1004b2a3  mov     eax, 80004005h
0x1004b2a8  pop     esi
0x1004b2a9  mov     esp, ebp
0x1004b2ab  pop     ebp
0x1004b2ac  retn    8
```
