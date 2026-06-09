# ATL::CComEnumImpl<IEnumVARIANT,&_GUID const IID_IEnumVARIANT,tagVARIANT,ATL::_Copy<tagVARIANT>,ATL::CComEnum<IEnumVARIANT,&_GUID const IID_IEnumVARIANT,tagVARIANT,ATL::_Copy<tagVARIANT>,ATL::CComSingleThreadModel>>::Next(ulong,tagVARIANT *,ulong *)

- ea: `0x18002482c`
- end: `0x180024945`
- name: `?Next@?$CComEnumImpl@UIEnumVARIANT@@$1?IID_IEnumVARIANT@@3U_GUID@@BUtagVARIANT@@V?$_Copy@UtagVARIANT@@@ATL@@V?$CComEnum@UIEnumVARIANT@@$1?IID_IEnumVARIANT@@3U_GUID@@BUtagVARIANT@@V?$_Copy@UtagVARIANT@@@ATL@@VCComSingleThreadModel@6@@6@@ATL@@UEAAJKPEAUtagVARIANT@@PEAK@Z`
- size: `281`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180024820`

## callees

- `0x18002482c`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180024909`
- `OLEAUT32!__imp_VariantClear` at `0x180024909`
- `OLEAUT32!__imp_VariantCopy` at `0x1800248e8`
- `OLEAUT32!__imp_VariantCopy` at `0x1800248e8`

## pseudocode

```c
__int64 __fastcall ATL::CComEnumImpl<IEnumVARIANT,&_GUID const IID_IEnumVARIANT,tagVARIANT,ATL::_Copy<tagVARIANT>,ATL::CComEnum<IEnumVARIANT,&_GUID const IID_IEnumVARIANT,tagVARIANT,ATL::_Copy<tagVARIANT>,ATL::CComSingleThreadModel>>::Next(
        __int64 a1,
        unsigned int a2,
        VARIANTARG *a3,
        unsigned int *a4)
{
  VARIANTARG *v5; // rdi
  __int64 v8; // rbx
  unsigned int v9; // ebx
  BOOL v10; // r12d
  VARIANTARG *i; // rbp
  HRESULT v12; // r15d
  VARIANTARG *v13; // rcx

  v5 = a3;
  if ( !a2 )
  {
    if ( !a3 )
    {
      if ( a4 )
      {
        *a4 = -1431655765 * ((__int64)(*(_QWORD *)(a1 + 24) - *(_QWORD *)(a1 + 32)) >> 3);
        return 0;
      }
      return 2147500035LL;
    }
    goto LABEL_7;
  }
  if ( !a3 )
    return 2147500035LL;
  if ( a2 != 1 )
  {
LABEL_7:
    if ( a4 )
      goto LABEL_8;
    return 2147500035LL;
  }
LABEL_8:
  if ( !*(_QWORD *)(a1 + 16) )
    return 2147500037LL;
  v8 = *(_QWORD *)(a1 + 24);
  if ( !v8 || !*(_QWORD *)(a1 + 32) )
    return 2147500037LL;
  v9 = -1431655765 * ((v8 - *(_QWORD *)(a1 + 32)) >> 3);
  v10 = v9 < a2;
  if ( v9 > a2 )
    v9 = a2;
  if ( a4 )
    *a4 = v9;
  for ( i = a3; ; ++i )
  {
    if ( !v9 )
      return v10;
    v12 = VariantCopy(i, *(const VARIANTARG **)(a1 + 32));
    if ( v12 < 0 )
      break;
    --v9;
    *(_QWORD *)(a1 + 32) += 24LL;
  }
  while ( v5 < i )
  {
    v13 = v5++;
    VariantClear(v13);
  }
  if ( a4 )
    *a4 = 0;
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18002482c  push    rbx
0x18002482e  push    rbp
0x18002482f  push    rsi
0x180024830  push    rdi
0x180024831  push    r12
0x180024833  push    r14
0x180024835  push    r15
0x180024837  sub     rsp, 20h
0x18002483b  mov     r14, r9
0x18002483e  mov     rdi, r8
0x180024841  mov     rsi, rcx
0x180024844  test    edx, edx
0x180024846  jnz     short loc_18002487A
0x180024848  test    r8, r8
0x18002484b  jnz     short loc_180024888
0x18002484d  test    r9, r9
0x180024850  jz      loc_180024931
0x180024856  mov     rax, [rcx+18h]
0x18002485a  sub     rax, [rcx+20h]
0x18002485e  mov     rcx, 0AAAAAAAAAAAAAAABh
0x180024868  sar     rax, 3
0x18002486c  imul    rax, rcx
0x180024870  mov     [r9], eax
0x180024873  xor     eax, eax
0x180024875  jmp     loc_180024936
0x18002487a  test    rdi, rdi
0x18002487d  jz      loc_180024931
0x180024883  cmp     edx, 1
0x180024886  jz      short loc_180024891
0x180024888  test    r14, r14
0x18002488b  jz      loc_180024931
0x180024891  cmp     qword ptr [rcx+10h], 0
0x180024896  jz      loc_18002492A
0x18002489c  mov     rbx, [rcx+18h]
0x1800248a0  test    rbx, rbx
0x1800248a3  jz      loc_18002492A
0x1800248a9  cmp     qword ptr [rcx+20h], 0
0x1800248ae  jz      short loc_18002492A
0x1800248b0  sub     rbx, [rcx+20h]
0x1800248b4  xor     r12d, r12d
0x1800248b7  sar     rbx, 3
0x1800248bb  mov     rcx, 0AAAAAAAAAAAAAAABh
0x1800248c5  imul    rbx, rcx
0x1800248c9  cmp     ebx, edx
0x1800248cb  setb    r12b
0x1800248cf  cmova   ebx, edx
0x1800248d2  test    r14, r14
0x1800248d5  jz      short loc_1800248DA
0x1800248d7  mov     [r9], ebx
0x1800248da  mov     rbp, rdi
0x1800248dd  test    ebx, ebx
0x1800248df  jz      short loc_180024925
0x1800248e1  mov     rdx, [rsi+20h]; pvargSrc
0x1800248e5  mov     rcx, rbp; pvargDest
0x1800248e8  call    cs:__imp_VariantCopy
0x1800248ee  mov     r15d, eax
0x1800248f1  test    eax, eax
0x1800248f3  js      short loc_18002490F
0x1800248f5  dec     ebx
0x1800248f7  add     rbp, 18h
0x1800248fb  add     qword ptr [rsi+20h], 18h
0x180024900  jmp     short loc_1800248DD
0x180024902  mov     rcx, rdi; pvarg
0x180024905  add     rdi, 18h
0x180024909  call    cs:__imp_VariantClear
0x18002490f  cmp     rdi, rbp
0x180024912  jb      short loc_180024902
0x180024914  test    r14, r14
0x180024917  jz      short loc_180024920
0x180024919  mov     dword ptr [r14], 0
0x180024920  mov     eax, r15d
0x180024923  jmp     short loc_180024936
0x180024925  mov     eax, r12d
0x180024928  jmp     short loc_180024936
0x18002492a  mov     eax, 80004005h
0x18002492f  jmp     short loc_180024936
0x180024931  mov     eax, 80004003h
0x180024936  add     rsp, 20h
0x18002493a  pop     r15
0x18002493c  pop     r14
0x18002493e  pop     r12
0x180024940  pop     rdi
0x180024941  pop     rsi
0x180024942  pop     rbp
0x180024943  pop     rbx
0x180024944  retn
```
