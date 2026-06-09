# DOMProcessor::get_input(tagVARIANT *)

- ea: `0x1800dfdb0`
- end: `0x1800dfdf0`
- name: `?get_input@DOMProcessor@@UEAAJPEAUtagVARIANT@@@Z`
- size: `64`
- prototype: `HRESULT __fastcall(DOMProcessor *this, tagVARIANT *pVar)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800dfdb0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800dfdcf`
- `OLEAUT32!__imp_VariantInit` at `0x1800dfdcf`
- `OLEAUT32!__imp_VariantCopy` at `0x1800dfddf`
- `OLEAUT32!__imp_VariantCopy` at `0x1800dfddf`

## pseudocode

```c
HRESULT __fastcall DOMProcessor::get_input(DOMProcessor *this, tagVARIANT *pVar)
{
  if ( !pVar )
    return -2147024809;
  VariantInit(pVar);
  return VariantCopy(pVar, &this->_varInput);
}

```

## disassembly

```asm
0x1800dfdb0  mov     [rsp+arg_0], rbx
0x1800dfdb5  push    rdi
0x1800dfdb6  sub     rsp, 20h
0x1800dfdba  mov     rbx, pVar
0x1800dfdbd  mov     rdi, this
0x1800dfdc0  test    pVar, pVar
0x1800dfdc3  jnz     short loc_1800DFDCC
0x1800dfdc5  mov     eax, 80070057h
0x1800dfdca  jmp     short loc_1800DFDE5
0x1800dfdcc  mov     this, rbx; pvarg
0x1800dfdcf  call    cs:__imp_VariantInit
0x1800dfdd5  lea     pVar, [rdi+0A8h]; pvargSrc
0x1800dfddc  mov     this, rbx; pvargDest
0x1800dfddf  call    cs:__imp_VariantCopy
0x1800dfde5  mov     rbx, [rsp+28h+arg_0]
0x1800dfdea  add     rsp, 20h
0x1800dfdee  pop     rdi
0x1800dfdef  retn
```
