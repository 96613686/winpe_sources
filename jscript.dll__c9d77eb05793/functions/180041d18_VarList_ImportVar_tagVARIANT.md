# VarList::ImportVar(tagVARIANT *)

- ea: `0x180041d18`
- end: `0x180041d50`
- name: `?ImportVar@VarList@@IEAAJPEAUtagVARIANT@@@Z`
- size: `56`
- prototype: `__int64 __fastcall(VarList *__hidden this, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800145ec`

## callees

- `0x180011c70`
- `0x180041d18`

## import_xrefs

- `OLEAUT32!__imp_VariantCopyInd` at `0x180041d34`
- `OLEAUT32!__imp_VariantCopyInd` at `0x180041d34`

## pseudocode

```c
HRESULT __fastcall VarList::ImportVar(VarList *this, struct tagVARIANT *a2)
{
  HRESULT result; // eax

  *((_QWORD *)this + 2) -= 24LL;
  **((_WORD **)this + 2) = 0;
  result = VariantCopyInd(*((VARIANT **)this + 2), a2);
  if ( result >= 0 )
    return VAR::Import(*((VAR **)this + 2), *(struct CSession **)this);
  return result;
}

```

## disassembly

```asm
0x180041d18  push    rbx
0x180041d1a  sub     rsp, 20h
0x180041d1e  add     qword ptr [rcx+10h], 0FFFFFFFFFFFFFFE8h
0x180041d23  xor     eax, eax
0x180041d25  mov     r8, [rcx+10h]
0x180041d29  mov     rbx, rcx
0x180041d2c  mov     [r8], ax
0x180041d30  mov     rcx, [rcx+10h]; pvarDest
0x180041d34  call    cs:__imp_VariantCopyInd
0x180041d3a  test    eax, eax
0x180041d3c  js      short loc_180041D4A
0x180041d3e  mov     rdx, [rbx]; struct CSession *
0x180041d41  mov     rcx, [rbx+10h]; this
0x180041d45  call    ?Import@VAR@@QEAAJPEAVCSession@@@Z; VAR::Import(CSession *)
0x180041d4a  add     rsp, 20h
0x180041d4e  pop     rbx
0x180041d4f  retn
```
