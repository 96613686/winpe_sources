# HrSafeArrayFromNetConPropertiesEx(tagNETCON_PROPERTIES_EX *,tagSAFEARRAY * *)

- ea: `0x18003202c`
- end: `0x180032107`
- name: `?HrSafeArrayFromNetConPropertiesEx@@YAJPEAUtagNETCON_PROPERTIES_EX@@PEAPEAUtagSAFEARRAY@@@Z`
- size: `219`
- prototype: `__int64 __fastcall(struct tagNETCON_PROPERTIES_EX *, struct tagSAFEARRAY **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180023080`

## callees

- `0x18003202c`
- `0x1800325dc`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180032096`
- `OLEAUT32!__imp_VariantInit` at `0x180032096`
- `OLEAUT32!__imp_VariantClear` at `0x1800320c9`
- `OLEAUT32!__imp_VariantClear` at `0x1800320d7`
- `OLEAUT32!__imp_VariantClear` at `0x1800320eb`
- `OLEAUT32!__imp_VariantClear` at `0x1800320c9`
- `OLEAUT32!__imp_VariantClear` at `0x1800320d7`
- `OLEAUT32!__imp_VariantClear` at `0x1800320eb`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180032074`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180032074`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1800320bd`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1800320bd`

## pseudocode

```c
__int64 __fastcall HrSafeArrayFromNetConPropertiesEx(struct tagNETCON_PROPERTIES_EX *a1, struct tagSAFEARRAY **a2)
{
  SAFEARRAY *v5; // rax
  HRESULT Field; // ebx
  int i; // eax
  VARIANTARG pvarg; // [rsp+20h] [rbp-20h] BYREF
  LONG rgIndices; // [rsp+60h] [rbp+20h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+70h] [rbp+30h] BYREF
  struct tagNETCON_PROPERTIES_EX *v11; // [rsp+78h] [rbp+38h] BYREF

  rgsabound.lLbound = 0;
  if ( !a1 )
    return 2147942487LL;
  if ( !a2 )
    return 2147500035LL;
  rgsabound = (SAFEARRAYBOUND)12LL;
  v5 = SafeArrayCreate(0xCu, 1u, &rgsabound);
  *a2 = v5;
  if ( v5 )
  {
    Field = 0;
    v11 = a1;
    rgIndices = 0;
    for ( i = 0; i <= 11; i = ++rgIndices )
    {
      VariantInit(&pvarg);
      Field = CPropertiesEx::GetField((CPropertiesEx *)&v11, rgIndices, &pvarg);
      if ( Field < 0 || (Field = SafeArrayPutElement(*a2, &rgIndices, &pvarg), VariantClear(&pvarg), Field < 0) )
      {
        VariantClear(&pvarg);
        return (unsigned int)Field;
      }
      VariantClear(&pvarg);
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)Field;
}

```

## disassembly

```asm
0x18003202c  mov     [rsp-18h+arg_8], rbx
0x180032031  push    rbp
0x180032032  push    rsi
0x180032033  push    rdi
0x180032034  mov     rbp, rsp
0x180032037  sub     rsp, 40h
0x18003203b  xor     eax, eax
0x18003203d  mov     rdi, rdx
0x180032040  mov     [rbp+rgsabound.lLbound], eax
0x180032043  mov     rsi, rcx
0x180032046  test    rcx, rcx
0x180032049  jnz     short loc_180032055
0x18003204b  mov     eax, 80070057h
0x180032050  jmp     loc_1800320FA
0x180032055  test    rdi, rdi
0x180032058  jnz     short loc_180032064
0x18003205a  mov     eax, 80004003h
0x18003205f  jmp     loc_1800320FA
0x180032064  mov     ecx, 0Ch; vt
0x180032069  lea     r8, [rbp+rgsabound]; rgsabound
0x18003206d  mov     qword ptr [rbp+rgsabound.cElements], rcx
0x180032071  lea     edx, [rcx-0Bh]; cDims
0x180032074  call    cs:__imp_SafeArrayCreate
0x18003207a  mov     [rdi], rax
0x18003207d  test    rax, rax
0x180032080  jz      short loc_1800320F3
0x180032082  xor     ebx, ebx
0x180032084  mov     [rbp+arg_18], rsi
0x180032088  mov     [rbp+rgIndices], ebx
0x18003208b  xor     eax, eax
0x18003208d  cmp     eax, 0Bh
0x180032090  jg      short loc_1800320F8
0x180032092  lea     rcx, [rbp+pvarg]; pvarg
0x180032096  call    cs:__imp_VariantInit
0x18003209c  mov     edx, [rbp+rgIndices]; int
0x18003209f  lea     r8, [rbp+pvarg]; struct tagVARIANT *
0x1800320a3  lea     rcx, [rbp+arg_18]; this
0x1800320a7  call    ?GetField@CPropertiesEx@@QEAAJHAEAUtagVARIANT@@@Z; CPropertiesEx::GetField(int,tagVARIANT &)
0x1800320ac  mov     ebx, eax
0x1800320ae  test    eax, eax
0x1800320b0  js      short loc_1800320E7
0x1800320b2  mov     rcx, [rdi]; psa
0x1800320b5  lea     r8, [rbp+pvarg]; pv
0x1800320b9  lea     rdx, [rbp+rgIndices]; rgIndices
0x1800320bd  call    cs:__imp_SafeArrayPutElement
0x1800320c3  lea     rcx, [rbp+pvarg]; pvarg
0x1800320c7  mov     ebx, eax
0x1800320c9  call    cs:__imp_VariantClear
0x1800320cf  test    ebx, ebx
0x1800320d1  js      short loc_1800320E7
0x1800320d3  lea     rcx, [rbp+pvarg]; pvarg
0x1800320d7  call    cs:__imp_VariantClear
0x1800320dd  mov     eax, [rbp+rgIndices]
0x1800320e0  inc     eax
0x1800320e2  mov     [rbp+rgIndices], eax
0x1800320e5  jmp     short loc_18003208D
0x1800320e7  lea     rcx, [rbp+pvarg]; pvarg
0x1800320eb  call    cs:__imp_VariantClear
0x1800320f1  jmp     short loc_1800320F8
0x1800320f3  mov     ebx, 8007000Eh
0x1800320f8  mov     eax, ebx
0x1800320fa  mov     rbx, [rsp+40h+arg_8]
0x1800320ff  add     rsp, 40h
0x180032103  pop     rdi
0x180032104  pop     rsi
0x180032105  pop     rbp
0x180032106  retn
```
