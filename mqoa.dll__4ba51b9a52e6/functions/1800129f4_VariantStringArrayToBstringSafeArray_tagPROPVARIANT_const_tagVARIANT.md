# VariantStringArrayToBstringSafeArray(tagPROPVARIANT const &,tagVARIANT *)

- ea: `0x1800129f4`
- end: `0x180012adf`
- name: `?VariantStringArrayToBstringSafeArray@@YAJAEBUtagPROPVARIANT@@PEAUtagVARIANT@@@Z`
- size: `235`
- prototype: `int(const struct tagPROPVARIANT *, struct tagVARIANT *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800083a0`
- `0x180008860`
- `0x1800239c0`

## callees

- `0x1800129f4`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180012a79`
- `OLEAUT32!__imp_SysAllocString` at `0x180012a79`
- `OLEAUT32!__imp_VariantInit` at `0x180012aba`
- `OLEAUT32!__imp_VariantInit` at `0x180012aba`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180012a28`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180012a28`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180012aa6`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180012aa6`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180012a51`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180012a51`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180012a9d`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180012ab1`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180012a9d`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180012ab1`

## pseudocode

```c
HRESULT __fastcall VariantStringArrayToBstringSafeArray(const struct tagPROPVARIANT *a1, struct tagVARIANT *a2)
{
  SAFEARRAY *v4; // rax
  SAFEARRAY *v5; // rdi
  HRESULT result; // eax
  _WORD *v7; // rcx
  __int64 i; // rsi
  BSTR v9; // rax
  void *ppvData; // [rsp+40h] [rbp+8h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+50h] [rbp+18h] BYREF

  rgsabound.cElements = a1->ulVal;
  rgsabound.lLbound = 0;
  v4 = SafeArrayCreate(0xCu, 1u, &rgsabound);
  v5 = v4;
  if ( !v4 )
    return -2147024882;
  ppvData = 0;
  result = SafeArrayAccessData(v4, &ppvData);
  if ( result >= 0 )
  {
    v7 = ppvData;
    for ( i = 0; (unsigned int)i < a1->lVal; i = (unsigned int)(i + 1) )
    {
      v7[12 * i] = 8;
      v9 = SysAllocString(*(const OLECHAR **)&a1->bstrblobVal.pData[8 * i]);
      *((_QWORD *)ppvData + 3 * i + 1) = v9;
      v7 = ppvData;
      if ( !*((_QWORD *)ppvData + 3 * i + 1) )
      {
        SafeArrayUnaccessData(v5);
        SafeArrayDestroy(v5);
        return -2147024882;
      }
    }
    SafeArrayUnaccessData(v5);
    VariantInit(a2);
    result = 0;
    a2->vt = 8204;
    a2->llVal = (LONGLONG)v5;
  }
  return result;
}

```

## disassembly

```asm
0x1800129f4  mov     [rsp+arg_8], rbx
0x1800129f9  mov     [rsp+arg_18], rbp
0x1800129fe  push    rsi
0x1800129ff  push    rdi
0x180012a00  push    r14
0x180012a02  sub     rsp, 20h
0x180012a06  mov     eax, [rcx+8]
0x180012a09  lea     r8, [rsp+38h+rgsabound]; rgsabound
0x180012a0e  mov     rbp, rcx
0x180012a11  mov     [rsp+38h+rgsabound.cElements], eax
0x180012a15  mov     ecx, 0Ch; vt
0x180012a1a  mov     [rsp+38h+rgsabound.lLbound], 0
0x180012a22  mov     r14, rdx
0x180012a25  lea     edx, [rcx-0Bh]; cDims
0x180012a28  call    cs:__imp_SafeArrayCreate
0x180012a2e  mov     rdi, rax
0x180012a31  test    rax, rax
0x180012a34  jnz     short loc_180012A40
0x180012a36  mov     eax, 8007000Eh
0x180012a3b  jmp     loc_180012ACC
0x180012a40  lea     rdx, [rsp+38h+ppvData]; ppvData
0x180012a45  mov     [rsp+38h+ppvData], 0
0x180012a4e  mov     rcx, rdi; psa
0x180012a51  call    cs:__imp_SafeArrayAccessData
0x180012a57  test    eax, eax
0x180012a59  js      short loc_180012ACC
0x180012a5b  mov     rcx, [rsp+38h+ppvData]
0x180012a60  xor     esi, esi
0x180012a62  cmp     esi, [rbp+8]
0x180012a65  jnb     short loc_180012AAE
0x180012a67  lea     rbx, [rsi+rsi*2]
0x180012a6b  mov     word ptr [rcx+rbx*8], 8
0x180012a71  mov     rcx, [rbp+10h]
0x180012a75  mov     rcx, [rcx+rsi*8]; psz
0x180012a79  call    cs:__imp_SysAllocString
0x180012a7f  mov     rcx, [rsp+38h+ppvData]
0x180012a84  mov     [rcx+rbx*8+8], rax
0x180012a89  mov     rcx, [rsp+38h+ppvData]
0x180012a8e  cmp     qword ptr [rcx+rbx*8+8], 0
0x180012a94  jz      short loc_180012A9A
0x180012a96  inc     esi
0x180012a98  jmp     short loc_180012A62
0x180012a9a  mov     rcx, rdi; psa
0x180012a9d  call    cs:__imp_SafeArrayUnaccessData
0x180012aa3  mov     rcx, rdi; psa
0x180012aa6  call    cs:__imp_SafeArrayDestroy
0x180012aac  jmp     short loc_180012A36
0x180012aae  mov     rcx, rdi; psa
0x180012ab1  call    cs:__imp_SafeArrayUnaccessData
0x180012ab7  mov     rcx, r14; pvarg
0x180012aba  call    cs:__imp_VariantInit
0x180012ac0  xor     eax, eax
0x180012ac2  mov     word ptr [r14], 200Ch
0x180012ac8  mov     [r14+8], rdi
0x180012acc  mov     rbx, [rsp+38h+arg_8]
0x180012ad1  mov     rbp, [rsp+38h+arg_18]
0x180012ad6  add     rsp, 20h
0x180012ada  pop     r14
0x180012adc  pop     rdi
0x180012add  pop     rsi
0x180012ade  retn
```
