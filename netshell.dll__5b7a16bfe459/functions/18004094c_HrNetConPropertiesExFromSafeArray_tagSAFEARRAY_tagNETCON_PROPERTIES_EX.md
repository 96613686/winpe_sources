# HrNetConPropertiesExFromSafeArray(tagSAFEARRAY *,tagNETCON_PROPERTIES_EX * *)

- ea: `0x18004094c`
- end: `0x180040a54`
- name: `?HrNetConPropertiesExFromSafeArray@@YAJPEAUtagSAFEARRAY@@PEAPEAUtagNETCON_PROPERTIES_EX@@@Z`
- size: `264`
- prototype: `__int64 __fastcall(SAFEARRAY *psa, struct tagNETCON_PROPERTIES_EX **)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800154c8`

## callees

- `0x1800157f0`
- `0x18001eb7c`
- `0x18004094c`
- `0x180040ad0`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180040985`
- `ole32!CoTaskMemAlloc` at `0x180040985`
- `OLEAUT32!__imp_VariantInit` at `0x1800409e8`
- `OLEAUT32!__imp_VariantInit` at `0x1800409e8`
- `OLEAUT32!__imp_VariantClear` at `0x180040a1f`
- `OLEAUT32!__imp_VariantClear` at `0x180040a30`
- `OLEAUT32!__imp_VariantClear` at `0x180040a1f`
- `OLEAUT32!__imp_VariantClear` at `0x180040a30`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800409c6`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800409c6`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800409ae`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800409ae`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1800409f9`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1800409f9`

## pseudocode

```c
__int64 __fastcall HrNetConPropertiesExFromSafeArray(SAFEARRAY *psa, struct tagNETCON_PROPERTIES_EX **a2)
{
  struct tagNETCON_PROPERTIES_EX *v5; // rax
  HRESULT LBound; // ebx
  int i; // eax
  struct tagNETCON_PROPERTIES_EX *v8; // [rsp+20h] [rbp-20h] BYREF
  VARIANTARG pvarg; // [rsp+28h] [rbp-18h] BYREF
  LONG rgIndices; // [rsp+60h] [rbp+20h] BYREF
  LONG plLbound; // [rsp+70h] [rbp+30h] BYREF
  LONG plUbound; // [rsp+78h] [rbp+38h] BYREF

  plLbound = 0;
  plUbound = 0;
  if ( !psa )
    return 2147942487LL;
  v5 = (struct tagNETCON_PROPERTIES_EX *)CoTaskMemAlloc(0x68u);
  *a2 = v5;
  if ( v5 )
  {
    memset_0(v5, 0, 0x68u);
    LBound = SafeArrayGetLBound(psa, 1u, &plLbound);
    if ( LBound < 0 || (LBound = SafeArrayGetUBound(psa, 1u, &plUbound), LBound < 0) )
    {
LABEL_12:
      HrFreeNetConProperties2(*a2);
    }
    else
    {
      v8 = *a2;
      for ( i = plLbound; ; i = rgIndices + 1 )
      {
        rgIndices = i;
        if ( i > plUbound )
          break;
        VariantInit(&pvarg);
        LBound = SafeArrayGetElement(psa, &rgIndices, &pvarg);
        if ( LBound < 0 || (LBound = CPropertiesEx::SetField((CPropertiesEx *)&v8, rgIndices, &pvarg), LBound < 0) )
        {
          VariantClear(&pvarg);
          goto LABEL_12;
        }
        VariantClear(&pvarg);
      }
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)LBound;
}

```

## disassembly

```asm
0x18004094c  mov     [rsp-18h+arg_8], rbx
0x180040951  push    rbp
0x180040952  push    rsi
0x180040953  push    rdi
0x180040954  mov     rbp, rsp
0x180040957  sub     rsp, 40h
0x18004095b  mov     [rbp+plLbound], 0
0x180040962  mov     rsi, rdx
0x180040965  mov     [rbp+plUbound], 0
0x18004096c  mov     rdi, rcx
0x18004096f  test    rcx, rcx
0x180040972  jnz     short loc_18004097E
0x180040974  mov     eax, 80070057h
0x180040979  jmp     loc_180040A47
0x18004097e  mov     ebx, 68h ; 'h'
0x180040983  mov     ecx, ebx; cb
0x180040985  call    cs:__imp_CoTaskMemAlloc
0x18004098b  mov     [rsi], rax
0x18004098e  test    rax, rax
0x180040991  jz      loc_180040A40
0x180040997  mov     r8d, ebx; Size
0x18004099a  xor     edx, edx; Val
0x18004099c  mov     rcx, rax; void *
0x18004099f  call    memset_0
0x1800409a4  lea     r8, [rbp+plLbound]; plLbound
0x1800409a8  mov     rcx, rdi; psa
0x1800409ab  lea     edx, [rbx-67h]; nDim
0x1800409ae  call    cs:__imp_SafeArrayGetLBound
0x1800409b4  mov     ebx, eax
0x1800409b6  test    eax, eax
0x1800409b8  js      short loc_180040A36
0x1800409ba  lea     r8, [rbp+plUbound]; plUbound
0x1800409be  mov     edx, 1; nDim
0x1800409c3  mov     rcx, rdi; psa
0x1800409c6  call    cs:__imp_SafeArrayGetUBound
0x1800409cc  mov     ebx, eax
0x1800409ce  test    eax, eax
0x1800409d0  js      short loc_180040A36
0x1800409d2  mov     rax, [rsi]
0x1800409d5  mov     [rbp+var_20], rax
0x1800409d9  mov     eax, [rbp+plLbound]
0x1800409dc  mov     [rbp+rgIndices], eax
0x1800409df  cmp     eax, [rbp+plUbound]
0x1800409e2  jg      short loc_180040A45
0x1800409e4  lea     rcx, [rbp+pvarg]; pvarg
0x1800409e8  call    cs:__imp_VariantInit
0x1800409ee  lea     r8, [rbp+pvarg]; pv
0x1800409f2  mov     rcx, rdi; psa
0x1800409f5  lea     rdx, [rbp+rgIndices]; rgIndices
0x1800409f9  call    cs:__imp_SafeArrayGetElement
0x1800409ff  mov     ebx, eax
0x180040a01  test    eax, eax
0x180040a03  js      short loc_180040A2C
0x180040a05  mov     edx, [rbp+rgIndices]; int
0x180040a08  lea     r8, [rbp+pvarg]; struct tagVARIANT *
0x180040a0c  lea     rcx, [rbp+var_20]; this
0x180040a10  call    ?SetField@CPropertiesEx@@QEAAJHAEBUtagVARIANT@@@Z; CPropertiesEx::SetField(int,tagVARIANT const &)
0x180040a15  mov     ebx, eax
0x180040a17  test    eax, eax
0x180040a19  js      short loc_180040A2C
0x180040a1b  lea     rcx, [rbp+pvarg]; pvarg
0x180040a1f  call    cs:__imp_VariantClear
0x180040a25  mov     eax, [rbp+rgIndices]
0x180040a28  inc     eax
0x180040a2a  jmp     short loc_1800409DC
0x180040a2c  lea     rcx, [rbp+pvarg]; pvarg
0x180040a30  call    cs:__imp_VariantClear
0x180040a36  mov     rcx, [rsi]; pv
0x180040a39  call    ?HrFreeNetConProperties2@@YAJPEAUtagNETCON_PROPERTIES_EX@@@Z; HrFreeNetConProperties2(tagNETCON_PROPERTIES_EX *)
0x180040a3e  jmp     short loc_180040A45
0x180040a40  mov     ebx, 8007000Eh
0x180040a45  mov     eax, ebx
0x180040a47  mov     rbx, [rsp+40h+arg_8]
0x180040a4c  add     rsp, 40h
0x180040a50  pop     rdi
0x180040a51  pop     rsi
0x180040a52  pop     rbp
0x180040a53  retn
```
