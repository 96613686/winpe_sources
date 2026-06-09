# DOMProcessor::get_input(tagVARIANT *)

- ea: `0x1008f1f0`
- end: `0x1008f21f`
- name: `?get_input@DOMProcessor@@UAGJPAUtagVARIANT@@@Z`
- size: `47`
- prototype: `HRESULT __stdcall(DOMProcessor *this, tagVARIANT *pVar)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1008f1f0`

## import_xrefs

- `OLEAUT32!__imp__VariantInit@4` at `0x1008f205`
- `OLEAUT32!__imp__VariantInit@4` at `0x1008f205`
- `OLEAUT32!__imp__VariantCopy@8` at `0x1008f215`
- `OLEAUT32!__imp__VariantCopy@8` at `0x1008f215`

## pseudocode

```c
HRESULT __stdcall DOMProcessor::get_input(DOMProcessor *this, tagVARIANT *pVar)
{
  if ( !pVar )
    return -2147024809;
  VariantInit(pVar);
  return VariantCopy(pVar, &this->_varInput);
}

```

## disassembly

```asm
0x1008f1f0  mov     edi, edi
0x1008f1f2  push    ebp
0x1008f1f3  mov     ebp, esp
0x1008f1f5  cmp     [ebp+pVar], 0
0x1008f1f9  jnz     short loc_1008F202
0x1008f1fb  mov     eax, 80070057h
0x1008f200  jmp     short loc_1008F21B
0x1008f202  push    [ebp+pVar]; pvarg
0x1008f205  call    ds:__imp__VariantInit@4; VariantInit(x)
0x1008f20b  mov     eax, [ebp+this]
0x1008f20e  add     eax, 58h ; 'X'
0x1008f211  push    eax; pvargSrc
0x1008f212  push    [ebp+pVar]; pvargDest
0x1008f215  call    ds:__imp__VariantCopy@8; VariantCopy(x,x)
0x1008f21b  pop     ebp
0x1008f21c  retn    8
```
