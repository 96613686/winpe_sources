# DOMProcessor::get_input(tagVARIANT *)

- ea: `0x1008f230`
- end: `0x1008f25f`
- name: `?get_input@DOMProcessor@@UAGJPAUtagVARIANT@@@Z`
- size: `47`
- prototype: `HRESULT __stdcall(DOMProcessor *this, tagVARIANT *pVar)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1008f230`

## import_xrefs

- `OLEAUT32!__imp__VariantInit@4` at `0x1008f245`
- `OLEAUT32!__imp__VariantInit@4` at `0x1008f245`
- `OLEAUT32!__imp__VariantCopy@8` at `0x1008f255`
- `OLEAUT32!__imp__VariantCopy@8` at `0x1008f255`

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
0x1008f230  mov     edi, edi
0x1008f232  push    ebp
0x1008f233  mov     ebp, esp
0x1008f235  cmp     [ebp+pVar], 0
0x1008f239  jnz     short loc_1008F242
0x1008f23b  mov     eax, 80070057h
0x1008f240  jmp     short loc_1008F25B
0x1008f242  push    [ebp+pVar]; pvarg
0x1008f245  call    ds:__imp__VariantInit@4; VariantInit(x)
0x1008f24b  mov     eax, [ebp+this]
0x1008f24e  add     eax, 58h ; 'X'
0x1008f251  push    eax; pvargSrc
0x1008f252  push    [ebp+pVar]; pvargDest
0x1008f255  call    ds:__imp__VariantCopy@8; VariantCopy(x,x)
0x1008f25b  pop     ebp
0x1008f25c  retn    8
```
