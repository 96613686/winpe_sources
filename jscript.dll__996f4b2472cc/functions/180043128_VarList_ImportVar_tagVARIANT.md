# VarList::ImportVar(tagVARIANT *)

- ea: `0x180043128`
- end: `0x180043167`
- name: `?ImportVar@VarList@@IEAAJPEAUtagVARIANT@@@Z`
- size: `63`
- prototype: `__int64 __fastcall(VarList *__hidden this, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001192c`

## callees

- `0x18000eea4`
- `0x180043128`

## import_xrefs

- `OLEAUT32!__imp_VariantCopyInd` at `0x180043144`
- `OLEAUT32!__imp_VariantCopyInd` at `0x180043144`

## pseudocode

```c
HRESULT __fastcall VarList::ImportVar(VarList *this, struct tagVARIANT *a2)
{
  HRESULT result; // eax

  *((_QWORD *)this + 2) -= 24LL;
  **((_WORD **)this + 2) = 0;
  result = VariantCopyInd(*((VARIANT **)this + 2), a2);
  if ( result >= 0 )
    return VAR::Import(*((VARIANTARG **)this + 2), *(struct CSession **)this);
  return result;
}

```

## disassembly

```asm
0x180043128  push    rbx
0x18004312a  sub     rsp, 20h
0x18004312e  add     qword ptr [rcx+10h], 0FFFFFFFFFFFFFFE8h
0x180043133  xor     eax, eax
0x180043135  mov     r8, [rcx+10h]
0x180043139  mov     rbx, rcx
0x18004313c  mov     [r8], ax
0x180043140  mov     rcx, [rcx+10h]; pvarDest
0x180043144  call    cs:__imp_VariantCopyInd
0x18004314b  nop     dword ptr [rax+rax+00h]
0x180043150  test    eax, eax
0x180043152  js      short loc_180043160
0x180043154  mov     rdx, [rbx]; struct CSession *
0x180043157  mov     rcx, [rbx+10h]; this
0x18004315b  call    ?Import@VAR@@QEAAJPEAVCSession@@@Z; VAR::Import(CSession *)
0x180043160  add     rsp, 20h
0x180043164  pop     rbx
0x180043165  retn
```
