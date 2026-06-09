# DOMProcessor::get_input(tagVARIANT *)

- ea: `0x1800e1e50`
- end: `0x1800e1e9d`
- name: `?get_input@DOMProcessor@@UEAAJPEAUtagVARIANT@@@Z`
- size: `77`
- prototype: `HRESULT __fastcall(DOMProcessor *this, tagVARIANT *pVar)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800e1e50`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800e1e6f`
- `OLEAUT32!__imp_VariantInit` at `0x1800e1e6f`
- `OLEAUT32!__imp_VariantCopy` at `0x1800e1e85`
- `OLEAUT32!__imp_VariantCopy` at `0x1800e1e85`

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
0x1800e1e50  mov     [rsp+arg_0], rbx
0x1800e1e55  push    rdi
0x1800e1e56  sub     rsp, 20h
0x1800e1e5a  mov     rbx, pVar
0x1800e1e5d  mov     rdi, this
0x1800e1e60  test    pVar, pVar
0x1800e1e63  jnz     short loc_1800E1E6C
0x1800e1e65  mov     eax, 80070057h
0x1800e1e6a  jmp     short loc_1800E1E91
0x1800e1e6c  mov     this, rbx; pvarg
0x1800e1e6f  call    cs:__imp_VariantInit
0x1800e1e76  nop     dword ptr [rax+rax+00h]
0x1800e1e7b  lea     pVar, [rdi+0A8h]; pvargSrc
0x1800e1e82  mov     this, rbx; pvargDest
0x1800e1e85  call    cs:__imp_VariantCopy
0x1800e1e8c  nop     dword ptr [rax+rax+00h]
0x1800e1e91  mov     rbx, [rsp+28h+arg_0]
0x1800e1e96  add     rsp, 20h
0x1800e1e9a  pop     rdi
0x1800e1e9b  retn
```
