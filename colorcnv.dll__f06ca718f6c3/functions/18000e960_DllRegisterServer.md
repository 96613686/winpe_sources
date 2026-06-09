# DllRegisterServer

- ea: `0x18000e960`
- end: `0x18000eaa4`
- name: `DllRegisterServer`
- size: `324`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000a6d0`
- `0x18000d54c`
- `0x18000e960`
- `0x18000eef0`

## import_xrefs

- `msdmo!DMORegister` at `0x18000e9e8`
- `msdmo!DMORegister` at `0x18000e9e8`
- `MFPlat!MFTRegister` at `0x18000ea6a`
- `MFPlat!MFTRegister` at `0x18000ea6a`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  HRESULT result; // eax
  __int64 v1; // rcx
  DMO_PARTIAL_MEDIATYPE *pInTypes; // rdi
  __int64 v3; // rcx
  const DMO_PARTIAL_MEDIATYPE *pOutTypes; // rax
  DMO_PARTIAL_MEDIATYPE *v5; // rbx
  int v6; // esi
  int v7; // eax
  HRESULT v8; // ecx
  DMO_PARTIAL_MEDIATYPE *v9; // rcx
  GUID guidCategory; // [rsp+50h] [rbp-28h] BYREF
  CLSID clsidMFT; // [rsp+60h] [rbp-18h] BYREF

  result = CreateCLSIDRegKey();
  if ( result < 0 )
    return result;
  pInTypes = (DMO_PARTIAL_MEDIATYPE *)GuidPairArray(v1, 20, &off_18002C080);
  pOutTypes = (const DMO_PARTIAL_MEDIATYPE *)GuidPairArray(v3, 16, off_18002C000);
  v5 = (DMO_PARTIAL_MEDIATYPE *)pOutTypes;
  if ( !pInTypes )
  {
    if ( !pOutTypes )
      return -2147024882;
    v9 = (DMO_PARTIAL_MEDIATYPE *)pOutTypes;
LABEL_12:
    operator delete(v9);
    return -2147024882;
  }
  if ( !pOutTypes )
  {
    v9 = pInTypes;
    goto LABEL_12;
  }
  v6 = DMORegister(
         L"Color Converter DMO",
         &CLSID_CColorConvertDMO,
         &DMOCATEGORY_VIDEO_EFFECT,
         0,
         0x14u,
         pInTypes,
         0x10u,
         pOutTypes);
  operator delete(pInTypes);
  operator delete(v5);
  if ( v6 < 0 )
    return v6;
  guidCategory = MFT_CATEGORY_VIDEO_EFFECT;
  clsidMFT = CLSID_CColorConvertDMO;
  v7 = MFTRegister(
         &clsidMFT,
         &guidCategory,
         (LPWSTR)L"Color Converter DMO",
         0,
         0x14u,
         &pInputTypes,
         0x10u,
         &pOutputTypes,
         0);
  v8 = 0;
  if ( v7 < 0 )
    return v7;
  return v8;
}

```

## disassembly

```asm
0x18000e960  mov     [rsp+arg_0], rbx
0x18000e965  mov     [rsp+arg_8], rsi
0x18000e96a  push    rdi
0x18000e96b  sub     rsp, 70h
0x18000e96f  call    CreateCLSIDRegKey
0x18000e974  test    eax, eax
0x18000e976  js      loc_18000EA92
0x18000e97c  lea     r8, off_18002C080
0x18000e983  mov     edx, 14h
0x18000e988  call    GuidPairArray
0x18000e98d  lea     r8, off_18002C000
0x18000e994  mov     edx, 10h
0x18000e999  mov     rdi, rax
0x18000e99c  call    GuidPairArray
0x18000e9a1  mov     rbx, rax
0x18000e9a4  test    rdi, rdi
0x18000e9a7  jz      loc_18000EA80
0x18000e9ad  test    rax, rax
0x18000e9b0  jz      loc_18000EA7B
0x18000e9b6  mov     [rsp+78h+pOutTypes], rax; pOutTypes
0x18000e9bb  lea     r8, DMOCATEGORY_VIDEO_EFFECT; guidCategory
0x18000e9c2  mov     [rsp+78h+cOutTypes], 10h; cOutTypes
0x18000e9ca  lea     rdx, CLSID_CColorConvertDMO; clsidDMO
0x18000e9d1  mov     [rsp+78h+pInTypes], rdi; pInTypes
0x18000e9d6  lea     rcx, pszName; "Color Converter DMO"
0x18000e9dd  xor     r9d, r9d; dwFlags
0x18000e9e0  mov     [rsp+78h+cInTypes], 14h; cInTypes
0x18000e9e8  call    cs:__imp_DMORegister
0x18000e9ee  mov     rcx, rdi; void *
0x18000e9f1  mov     esi, eax
0x18000e9f3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e9f8  mov     rcx, rbx; void *
0x18000e9fb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ea00  test    esi, esi
0x18000ea02  jns     short loc_18000EA0B
0x18000ea04  mov     eax, esi
0x18000ea06  jmp     loc_18000EA92
0x18000ea0b  movups  xmm0, xmmword ptr cs:MFT_CATEGORY_VIDEO_EFFECT.Data1
0x18000ea12  mov     [rsp+78h+pAttributes], 0; pAttributes
0x18000ea1b  lea     rax, pOutputTypes
0x18000ea22  movups  xmm1, xmmword ptr cs:CLSID_CColorConvertDMO.Data1
0x18000ea29  mov     [rsp+78h+pOutTypes], rax; pOutputTypes
0x18000ea2e  lea     r8, pszName; "Color Converter DMO"
0x18000ea35  lea     rax, pInputTypes
0x18000ea3c  mov     [rsp+78h+cOutTypes], 10h; cOutputTypes
0x18000ea44  mov     [rsp+78h+pInTypes], rax; pInputTypes
0x18000ea49  lea     rdx, [rsp+78h+guidCategory]; guidCategory
0x18000ea4e  xor     r9d, r9d; Flags
0x18000ea51  mov     [rsp+78h+cInTypes], 14h; cInputTypes
0x18000ea59  lea     rcx, [rsp+78h+clsidMFT]; clsidMFT
0x18000ea5e  movdqu  xmmword ptr [rsp+78h+guidCategory.Data1], xmm0
0x18000ea64  movdqu  xmmword ptr [rsp+78h+clsidMFT.Data1], xmm1
0x18000ea6a  call    cs:__imp_MFTRegister
0x18000ea70  xor     ecx, ecx
0x18000ea72  test    eax, eax
0x18000ea74  cmovs   ecx, eax
0x18000ea77  mov     eax, ecx
0x18000ea79  jmp     short loc_18000EA92
0x18000ea7b  mov     rcx, rdi
0x18000ea7e  jmp     short loc_18000EA88
0x18000ea80  test    rbx, rbx
0x18000ea83  jz      short loc_18000EA8D
0x18000ea85  mov     rcx, rbx; void *
0x18000ea88  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ea8d  mov     eax, 8007000Eh
0x18000ea92  lea     r11, [rsp+78h+var_8]
0x18000ea97  mov     rbx, [r11+10h]
0x18000ea9b  mov     rsi, [r11+18h]
0x18000ea9f  mov     rsp, r11
0x18000eaa2  pop     rdi
0x18000eaa3  retn
```
