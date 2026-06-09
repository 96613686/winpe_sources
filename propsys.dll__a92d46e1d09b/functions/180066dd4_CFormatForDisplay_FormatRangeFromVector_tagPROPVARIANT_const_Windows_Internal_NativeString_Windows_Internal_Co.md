# CFormatForDisplay::_FormatRangeFromVector(tagPROPVARIANT const &,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)

- ea: `0x180066dd4`
- end: `0x180066f16`
- name: `?_FormatRangeFromVector@CFormatForDisplay@@AEAAJAEBUtagPROPVARIANT@@AEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z`
- size: `322`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180066d48`

## callees

- `0x18000b410`
- `0x18000b560`
- `0x18000f050`
- `0x180066dd4`
- `0x18006ed20`
- `0x18007a8f8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180066e7b`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180066eb0`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180066e7b`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180066eb0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180066e6d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180066ea2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180066ebc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180066ee9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180066ef3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180066e6d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180066ea2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180066ebc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180066ee9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180066ef3`

## pseudocode

```c
__int64 __fastcall CFormatForDisplay::_FormatRangeFromVector(__int64 *a1, const PROPVARIANT *a2, __int64 a3)
{
  int inited; // ebx
  ULONG v7; // edi
  ULONG ElementCount; // esi
  PROPVARIANT ppropvar[2]; // [rsp+20h] [rbp-50h] BYREF
  __int64 v11; // [rsp+30h] [rbp-40h]
  PROPVARIANT propvar2[2]; // [rsp+38h] [rbp-38h] BYREF
  __int64 v13; // [rsp+48h] [rbp-28h]
  PROPVARIANT pvar[2]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v15; // [rsp+60h] [rbp-10h]

  v13 = 0;
  v15 = 0;
  v11 = 0;
  *(_OWORD *)propvar2 = 0;
  *(_OWORD *)pvar = 0;
  inited = 0;
  *(_OWORD *)ppropvar = 0;
  v7 = 0;
  ElementCount = PropVariantGetElementCount(a2);
  if ( ElementCount )
  {
    while ( inited >= 0 )
    {
      inited = InitPropVariantFromPropVariantVectorElem(a2, v7, ppropvar);
      if ( inited >= 0 )
      {
        if ( PropVariantCompareEx(ppropvar, propvar2, PVCU_DEFAULT, 1) >= 0
          || (PropVariantClear(propvar2), inited = PropVariantCopy(propvar2, ppropvar), inited >= 0) )
        {
          if ( PropVariantCompareEx(ppropvar, pvar, PVCU_DEFAULT, 0) > 0 )
          {
            PropVariantClear(pvar);
            inited = PropVariantCopy(pvar, ppropvar);
          }
        }
        PropVariantClear(ppropvar);
      }
      if ( ++v7 >= ElementCount )
      {
        if ( inited < 0 )
          break;
        goto LABEL_11;
      }
    }
  }
  else
  {
LABEL_11:
    inited = CFormatForDisplay::_FormatRangeFromValues(a1, (unsigned __int16 *)propvar2, (unsigned __int16 *)pvar, a3);
  }
  PropVariantClear(propvar2);
  PropVariantClear(pvar);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180066dd4  push    rbp
0x180066dd6  push    rbx
0x180066dd7  push    rsi
0x180066dd8  push    rdi
0x180066dd9  push    r12
0x180066ddb  push    r14
0x180066ddd  push    r15
0x180066ddf  mov     rbp, rsp
0x180066de2  sub     rsp, 70h
0x180066de6  mov     rax, cs:__security_cookie
0x180066ded  xor     rax, rsp
0x180066df0  mov     [rbp+var_8], rax
0x180066df4  xor     eax, eax
0x180066df6  xorps   xmm0, xmm0
0x180066df9  mov     r15, rcx
0x180066dfc  mov     [rbp+var_28], rax
0x180066e00  xorps   xmm1, xmm1
0x180066e03  mov     [rbp+var_10], rax
0x180066e07  mov     rcx, rdx; propvar
0x180066e0a  mov     [rbp+var_40], rax
0x180066e0e  movups  xmmword ptr [rbp+propvar2], xmm0
0x180066e12  mov     r12, r8
0x180066e15  mov     r14, rdx
0x180066e18  movups  xmmword ptr [rbp+pvar], xmm1
0x180066e1c  xor     ebx, ebx
0x180066e1e  movups  xmmword ptr [rbp+ppropvar], xmm0
0x180066e22  call    PropVariantGetElementCount
0x180066e27  xor     edi, edi
0x180066e29  mov     esi, eax
0x180066e2b  test    eax, eax
0x180066e2d  jz      loc_180066ED0
0x180066e33  test    ebx, ebx
0x180066e35  js      loc_180066EE5
0x180066e3b  lea     r8, [rbp+ppropvar]; ppropvar
0x180066e3f  mov     edx, edi; iElem
0x180066e41  mov     rcx, r14; propvarIn
0x180066e44  call    InitPropVariantFromPropVariantVectorElem
0x180066e49  mov     ebx, eax
0x180066e4b  test    eax, eax
0x180066e4d  js      short loc_180066EC2
0x180066e4f  mov     r9d, 1; flags
0x180066e55  lea     rdx, [rbp+propvar2]; propvar2
0x180066e59  xor     r8d, r8d; unit
0x180066e5c  lea     rcx, [rbp+ppropvar]; propvar1
0x180066e60  call    PropVariantCompareEx
0x180066e65  test    eax, eax
0x180066e67  jns     short loc_180066E87
0x180066e69  lea     rcx, [rbp+propvar2]; pvar
0x180066e6d  call    cs:__imp_PropVariantClear
0x180066e73  lea     rdx, [rbp+ppropvar]; pvarSrc
0x180066e77  lea     rcx, [rbp+propvar2]; pvarDest
0x180066e7b  call    cs:__imp_PropVariantCopy
0x180066e81  mov     ebx, eax
0x180066e83  test    eax, eax
0x180066e85  js      short loc_180066EB8
0x180066e87  xor     r9d, r9d; flags
0x180066e8a  lea     rdx, [rbp+pvar]; propvar2
0x180066e8e  xor     r8d, r8d; unit
0x180066e91  lea     rcx, [rbp+ppropvar]; propvar1
0x180066e95  call    PropVariantCompareEx
0x180066e9a  test    eax, eax
0x180066e9c  jle     short loc_180066EB8
0x180066e9e  lea     rcx, [rbp+pvar]; pvar
0x180066ea2  call    cs:__imp_PropVariantClear
0x180066ea8  lea     rdx, [rbp+ppropvar]; pvarSrc
0x180066eac  lea     rcx, [rbp+pvar]; pvarDest
0x180066eb0  call    cs:__imp_PropVariantCopy
0x180066eb6  mov     ebx, eax
0x180066eb8  lea     rcx, [rbp+ppropvar]; pvar
0x180066ebc  call    cs:__imp_PropVariantClear
0x180066ec2  inc     edi
0x180066ec4  cmp     edi, esi
0x180066ec6  jb      loc_180066E33
0x180066ecc  test    ebx, ebx
0x180066ece  js      short loc_180066EE5
0x180066ed0  mov     r9, r12
0x180066ed3  lea     r8, [rbp+pvar]
0x180066ed7  lea     rdx, [rbp+propvar2]
0x180066edb  mov     rcx, r15
0x180066ede  call    ?_FormatRangeFromValues@CFormatForDisplay@@AEAAJAEBUtagPROPVARIANT@@0AEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; CFormatForDisplay::_FormatRangeFromValues(tagPROPVARIANT const &,tagPROPVARIANT const &,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x180066ee3  mov     ebx, eax
0x180066ee5  lea     rcx, [rbp+propvar2]; pvar
0x180066ee9  call    cs:__imp_PropVariantClear
0x180066eef  lea     rcx, [rbp+pvar]; pvar
0x180066ef3  call    cs:__imp_PropVariantClear
0x180066ef9  mov     eax, ebx
0x180066efb  mov     rcx, [rbp+var_8]
0x180066eff  xor     rcx, rsp; StackCookie
0x180066f02  call    __security_check_cookie
0x180066f07  add     rsp, 70h
0x180066f0b  pop     r15
0x180066f0d  pop     r14
0x180066f0f  pop     r12
0x180066f11  pop     rdi
0x180066f12  pop     rsi
0x180066f13  pop     rbx
0x180066f14  pop     rbp
0x180066f15  retn
```
