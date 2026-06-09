# JoltProperty::GetProperty(tagDBPROP *)

- ea: `0x1001eed0`
- end: `0x1001ef0d`
- name: `?GetProperty@JoltProperty@@UAEJPAUtagDBPROP@@@Z`
- size: `61`
- prototype: `int __thiscall(JoltProperty *__hidden this, struct tagDBPROP *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1001eed0`

## import_xrefs

- `OLEAUT32!__imp__VariantCopy@8` at `0x1001eee9`
- `OLEAUT32!__imp__VariantCopy@8` at `0x1001eee9`

## pseudocode

```c
HRESULT __thiscall JoltProperty::GetProperty(const VARIANTARG *this, struct tagDBPROP *a2)
{
  HRESULT result; // eax

  a2->dwPropertyID = this->cyVal.Lo;
  result = VariantCopy(&a2->vValue, this + 1);
  if ( result >= 0 )
  {
    a2->dwStatus = 0;
    a2->dwOptions = (this[2].lVal & 2) == 0;
  }
  return result;
}

```

## disassembly

```asm
0x1001eed0  mov     edi, edi
0x1001eed2  push    ebp
0x1001eed3  mov     ebp, esp
0x1001eed5  push    esi
0x1001eed6  mov     esi, [ebp+arg_0]
0x1001eed9  push    edi
0x1001eeda  mov     edi, ecx
0x1001eedc  mov     eax, [edi+8]
0x1001eedf  mov     [esi], eax
0x1001eee1  lea     eax, [edi+10h]
0x1001eee4  push    eax; pvargSrc
0x1001eee5  lea     eax, [esi+24h]
0x1001eee8  push    eax; pvargDest
0x1001eee9  call    ds:__imp__VariantCopy@8; VariantCopy(x,x)
0x1001eeef  test    eax, eax
0x1001eef1  js      short loc_1001EF07
0x1001eef3  mov     dword ptr [esi+8], 0
0x1001eefa  mov     ecx, [edi+28h]
0x1001eefd  shr     ecx, 1
0x1001eeff  not     ecx
0x1001ef01  and     ecx, 1
0x1001ef04  mov     [esi+4], ecx
0x1001ef07  pop     edi
0x1001ef08  pop     esi
0x1001ef09  pop     ebp
0x1001ef0a  retn    4
```
