# ATL::CComSafeArray<tagVARIANT,12>::SetAt(long,tagVARIANT const &,int)

- ea: `0x18001dec8`
- end: `0x18001df1d`
- name: `?SetAt@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJJAEBUtagVARIANT@@H@Z`
- size: `85`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001cda0`
- `0x18001dc18`
- `0x1800281bc`

## callees

- `0x18001d954`
- `0x18001d9d8`
- `0x18001dec8`

## import_xrefs

- `OLEAUT32!__imp_VariantCopyInd` at `0x18001df07`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18001df07`

## pseudocode

```c
HRESULT __fastcall ATL::CComSafeArray<tagVARIANT,12>::SetAt(__int64 a1, int a2, const VARIANTARG *a3)
{
  int LowerBound; // esi

  LowerBound = ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(a1);
  if ( a2 < LowerBound || a2 > (int)ATL::CComSafeArray<unsigned short *,8>::GetUpperBound(a1) )
    return -2147024809;
  else
    return VariantCopyInd((VARIANT *)(*(_QWORD *)(*(_QWORD *)a1 + 16LL) + 24LL * (a2 - LowerBound)), a3);
}

```

## disassembly

```asm
0x18001dec8  push    rbx
0x18001deca  push    rbp
0x18001decb  push    rsi
0x18001decc  push    rdi
0x18001decd  sub     rsp, 28h
0x18001ded1  mov     rbp, r8
0x18001ded4  mov     ebx, edx
0x18001ded6  mov     rdi, rcx
0x18001ded9  call    ?GetLowerBound@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAJI@Z; ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(uint)
0x18001dede  mov     esi, eax
0x18001dee0  cmp     ebx, eax
0x18001dee2  jl      short loc_18001DF0F
0x18001dee4  mov     rcx, rdi
0x18001dee7  call    ?GetUpperBound@?$CComSafeArray@PEAG$07@ATL@@QEBAJI@Z; ATL::CComSafeArray<ushort *,8>::GetUpperBound(uint)
0x18001deec  cmp     ebx, eax
0x18001deee  jg      short loc_18001DF0F
0x18001def0  sub     ebx, esi
0x18001def2  movsxd  rax, ebx
0x18001def5  lea     rdx, [rax+rax*2]
0x18001def9  mov     rax, [rdi]
0x18001defc  mov     rcx, [rax+10h]
0x18001df00  lea     rcx, [rcx+rdx*8]; pvarDest
0x18001df04  mov     rdx, rbp; pvargSrc
0x18001df07  call    cs:__imp_VariantCopyInd
0x18001df0d  jmp     short loc_18001DF14
0x18001df0f  mov     eax, 80070057h
0x18001df14  add     rsp, 28h
0x18001df18  pop     rdi
0x18001df19  pop     rsi
0x18001df1a  pop     rbp
0x18001df1b  pop     rbx
0x18001df1c  retn
```
