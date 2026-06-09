# ProfileProperties::GetLocalizedPropertyValueFromProfile(IXMLDOMElement *,COLORPROFILETYPE,WcsProperty::Enum,ushort const *,ulong,ushort * *)

- ea: `0x180057e50`
- end: `0x18005839a`
- name: `?GetLocalizedPropertyValueFromProfile@ProfileProperties@@YAJPEAUIXMLDOMElement@@W4COLORPROFILETYPE@@W4Enum@WcsProperty@@PEBGKPEAPEAG@Z`
- size: `1354`
- prototype: `int __high(struct IXMLDOMElement *, enum COLORPROFILETYPE, enum WcsProperty::Enum, const unsigned __int16 *, unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x180057d94`

## callees

- `0x1800098b0`
- `0x18002e614`
- `0x18002eab4`
- `0x18002f2f4`
- `0x180057e50`
- `0x1800815d4`
- `0x180084010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180058150`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180058181`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180058150`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180058181`
- `api-ms-win-core-string-l2-1-0!CharUpperW` at `0x1800580de`
- `api-ms-win-core-string-l2-1-0!CharUpperW` at `0x1800580de`
- `OLEAUT32!__imp_SysAllocString` at `0x180057eea`
- `OLEAUT32!__imp_SysAllocString` at `0x180057f17`
- `OLEAUT32!__imp_SysAllocString` at `0x180057f40`
- `OLEAUT32!__imp_SysAllocString` at `0x180057eea`
- `OLEAUT32!__imp_SysAllocString` at `0x180057f17`
- `OLEAUT32!__imp_SysAllocString` at `0x180057f40`
- `OLEAUT32!__imp_SysFreeString` at `0x18005831d`
- `OLEAUT32!__imp_SysFreeString` at `0x180058326`
- `OLEAUT32!__imp_SysFreeString` at `0x180058330`
- `OLEAUT32!__imp_SysFreeString` at `0x18005833a`
- `OLEAUT32!__imp_SysFreeString` at `0x18005835e`
- `OLEAUT32!__imp_SysFreeString` at `0x18005831d`
- `OLEAUT32!__imp_SysFreeString` at `0x180058326`
- `OLEAUT32!__imp_SysFreeString` at `0x180058330`
- `OLEAUT32!__imp_SysFreeString` at `0x18005833a`
- `OLEAUT32!__imp_SysFreeString` at `0x18005835e`
- `OLEAUT32!__imp_SysStringLen` at `0x180058235`
- `OLEAUT32!__imp_SysStringLen` at `0x180058235`
- `OLEAUT32!__imp_VariantInit` at `0x180057ead`
- `OLEAUT32!__imp_VariantInit` at `0x180057ead`
- `OLEAUT32!__imp_VariantClear` at `0x180058377`
- `OLEAUT32!__imp_VariantClear` at `0x180058377`

## string_xrefs

- `0x180057f39`: `xml:lang`

## pseudocode

```c
__int64 __fastcall ProfileProperties::GetLocalizedPropertyValueFromProfile(
        __int64 a1,
        int a2,
        int a3,
        const wchar_t *a4,
        unsigned int a5,
        unsigned __int16 **a6)
{
  __int64 v6; // rsi
  void *v8; // r12
  __int64 v10; // rdi
  const wchar_t *v11; // r14
  __int64 v12; // r13
  OLECHAR *v13; // rax
  int v14; // edi
  OLECHAR *v15; // rbx
  OLECHAR *v16; // rsi
  int v17; // ebx
  char *v18; // r15
  unsigned __int16 *v19; // r14
  int v20; // eax
  char *v21; // r15
  int v22; // eax
  const wchar_t *v23; // r13
  int v24; // r15d
  char v25; // si
  const wchar_t *v26; // rbx
  signed __int64 v27; // rdx
  int v28; // eax
  int v29; // ecx
  wchar_t *v30; // rax
  __int64 v31; // rax
  size_t v32; // r8
  bool v33; // zf
  signed __int64 v34; // rdx
  int v35; // eax
  __int64 v36; // rax
  __int64 v37; // rax
  UINT v38; // eax
  UINT v39; // ebx
  __int64 v40; // rcx
  BSTR v42; // [rsp+28h] [rbp-58h]
  __int64 v43; // [rsp+30h] [rbp-50h] BYREF
  __int64 v44; // [rsp+38h] [rbp-48h] BYREF
  BSTR pbstr; // [rsp+40h] [rbp-40h] BYREF
  __int64 v46; // [rsp+48h] [rbp-38h] BYREF
  __int64 v47; // [rsp+50h] [rbp-30h] BYREF
  BSTR v48; // [rsp+58h] [rbp-28h]
  VARIANTARG pvarg; // [rsp+60h] [rbp-20h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp-8h]
  int v51; // [rsp+C8h] [rbp+48h] BYREF
  char *v52; // [rsp+D8h] [rbp+58h]

  v6 = a3;
  v46 = 0;
  v47 = 0;
  v44 = 0;
  v43 = 0;
  v48 = 0;
  v8 = 0;
  pbstr = 0;
  v51 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v10 = a2;
  VariantInit(&pvarg);
  v11 = aEnUs;
  v12 = 7;
  if ( a4 )
    v11 = a4;
  *a6 = 0;
  if ( a4 )
    v12 = a5;
  v13 = SysAllocString(*(&off_180086580[3 * v10] + v6 - 3));
  v14 = 0;
  bstrString = v13;
  v15 = v13;
  if ( !v13 )
  {
    v16 = 0;
    v17 = -2147024882;
    v18 = 0;
    v19 = 0;
    goto LABEL_60;
  }
  v42 = SysAllocString(L"wcs:Text");
  v16 = v42;
  if ( !v42 || (v48 = SysAllocString(L"xml:lang")) == 0 )
  {
    v17 = -2147024882;
    goto LABEL_9;
  }
  v20 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, __int64 *))(*(_QWORD *)a1 + 296LL))(a1, v15, &v46);
  v17 = v20;
  if ( v20 < 0 )
    goto LABEL_9;
  if ( v20 == 1 )
  {
    v17 = 0;
    v18 = 0;
    v19 = 0;
    goto LABEL_60;
  }
  v17 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v46)(v46, &IID_IXMLDOMElement, &v47);
  if ( v17 < 0
    || (v17 = (*(__int64 (__fastcall **)(__int64, BSTR, __int64 *))(*(_QWORD *)v47 + 400LL))(v47, v42, &v44), v17 < 0)
    || (v17 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v44 + 64LL))(v44, &v51), v17 < 0) )
  {
LABEL_9:
    v18 = 0;
    v19 = 0;
    goto LABEL_60;
  }
  if ( v51 <= 0 )
  {
    v17 = -2147022885;
    goto LABEL_9;
  }
  v8 = operator new[](saturated_mul(v51, 8u));
  memset_0(v8, 0, 8LL * v51);
  v18 = (char *)operator new[](saturated_mul(v51, 8u));
  v52 = v18;
  memset_0(v18, 0, 8LL * v51);
  if ( v51 > 0 )
  {
    while ( 1 )
    {
      v17 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v44 + 56LL))(
              v44,
              (unsigned int)v14,
              &v43);
      if ( v17 < 0 )
        break;
      v21 = &v18[8 * v14];
      v17 = (**(__int64 (__fastcall ***)(__int64, GUID *, char *))v43)(v43, &IID_IXMLDOMElement, v21);
      if ( v17 < 0
        || (v22 = (*(__int64 (__fastcall **)(_QWORD, BSTR, VARIANTARG *))(**(_QWORD **)v21 + 352LL))(
                    *(_QWORD *)v21,
                    v48,
                    &pvarg),
            v17 = v22,
            v22 < 0) )
      {
        v18 = v52;
        break;
      }
      if ( !v22 )
      {
        *((_QWORD *)v8 + v14) = pvarg.llVal;
        pvarg.llVal = 0;
        CharUpperW(*((LPWSTR *)v8 + v14));
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
      ++v14;
      v43 = 0;
      v18 = v52;
      if ( v14 >= v51 )
        goto LABEL_26;
    }
    v14 = 0;
    goto LABEL_59;
  }
LABEL_26:
  v14 = 0;
  v23 = &v11[v12];
  v24 = 0;
  v25 = 0;
  while ( v11 < v23 && *v11 && !v25 )
  {
    if ( v51 > 0 )
    {
      do
      {
        v26 = (const wchar_t *)*((_QWORD *)v8 + v14);
        if ( !v26 )
          goto LABEL_46;
        if ( wcschr(v11, 0x2Du) )
        {
          v27 = (char *)v11 - (char *)v26;
          do
          {
            v28 = *(const wchar_t *)((char *)v26 + v27);
            v29 = *v26 - v28;
            if ( v29 )
              break;
            ++v26;
          }
          while ( v28 );
        }
        else
        {
          v30 = wcschr(v26, 0x2Du);
          if ( v30 )
          {
            v31 = v30 - v26;
            v32 = -1;
            do
              ++v32;
            while ( v11[v32] );
            if ( (unsigned int)v31 != v32 )
              goto LABEL_46;
            v33 = wcsncmp_0(v26, v11, v32) == 0;
            goto LABEL_45;
          }
          v34 = (char *)v11 - (char *)v26;
          do
          {
            v35 = *(const wchar_t *)((char *)v26 + v34);
            v29 = *v26 - v35;
            if ( v29 )
              break;
            ++v26;
          }
          while ( v35 );
        }
        v33 = v29 == 0;
LABEL_45:
        if ( v33 )
        {
          v24 = v14;
          v25 = 1;
          break;
        }
LABEL_46:
        ++v14;
      }
      while ( v14 < v51 );
    }
    v36 = -1;
    v14 = 0;
    do
      ++v36;
    while ( v11[v36] );
    v11 += v36 + 1;
  }
  v37 = v24;
  v18 = v52;
  v17 = (*(__int64 (__fastcall **)(_QWORD, BSTR *))(**(_QWORD **)&v52[8 * v37] + 208LL))(
          *(_QWORD *)&v52[8 * v37],
          &pbstr);
  if ( v17 < 0 || (v38 = SysStringLen(pbstr) + 1, v38 == 1) )
  {
LABEL_59:
    v16 = v42;
    v19 = 0;
    goto LABEL_60;
  }
  v39 = v38;
  v19 = (unsigned __int16 *)operator new[](saturated_mul(v38, 2u));
  v16 = v42;
  v17 = StringCchCopyW(v19, v39, pbstr);
  if ( v17 >= 0 )
    *a6 = v19;
LABEL_60:
  if ( v46 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
  if ( v47 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
  if ( v44 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
  if ( v43 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  if ( v18 )
  {
    if ( v51 > 0 )
    {
      do
      {
        v40 = *(_QWORD *)&v18[8 * v14];
        if ( v40 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
        ++v14;
      }
      while ( v14 < v51 );
    }
    v14 = 0;
  }
  operator delete(v18);
  SysFreeString(bstrString);
  SysFreeString(v16);
  SysFreeString(v48);
  SysFreeString(pbstr);
  if ( v17 < 0 )
    operator delete(v19);
  if ( v8 && v51 > 0 )
  {
    do
      SysFreeString(*((BSTR *)v8 + v14++));
    while ( v14 < v51 );
  }
  operator delete(v8);
  VariantClear(&pvarg);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180057e50  mov     [rsp-38h+arg_0], rbx
0x180057e55  push    rbp
0x180057e56  push    rsi
0x180057e57  push    rdi
0x180057e58  push    r12
0x180057e5a  push    r13
0x180057e5c  push    r14
0x180057e5e  push    r15
0x180057e60  mov     rbp, rsp
0x180057e63  sub     rsp, 80h
0x180057e6a  xor     r13d, r13d
0x180057e6d  movsxd  rsi, r8d
0x180057e70  mov     r15, rcx
0x180057e73  mov     [rbp+var_38], r13
0x180057e77  xorps   xmm0, xmm0
0x180057e7a  mov     [rbp+var_30], r13
0x180057e7e  xor     eax, eax
0x180057e80  mov     [rbp+var_48], r13
0x180057e84  lea     rcx, [rbp+pvarg]; pvarg
0x180057e88  mov     [rbp+var_50], r13
0x180057e8c  mov     [rbp+var_28], r13
0x180057e90  mov     r12d, r13d
0x180057e93  mov     [rbp+pbstr], r13
0x180057e97  mov     rbx, r9
0x180057e9a  mov     [rbp+var_60], r13
0x180057e9e  mov     [rbp+arg_8], r13d
0x180057ea2  movups  xmmword ptr [rbp+pvarg], xmm0
0x180057ea6  mov     qword ptr [rbp+pvarg+10h], rax
0x180057eaa  movsxd  rdi, edx
0x180057ead  call    cs:__imp_VariantInit
0x180057eb3  mov     rax, [rbp+arg_28]
0x180057eb7  lea     r14, aEnUs; "en-US"
0x180057ebe  test    rbx, rbx
0x180057ec1  lea     r13d, [r12+7]
0x180057ec6  cmovnz  r14, rbx
0x180057eca  xor     ecx, ecx
0x180057ecc  mov     [rax], rcx
0x180057ecf  test    rbx, rbx
0x180057ed2  lea     rax, off_180086580; "./cdm:ProfileName[1]"
0x180057ed9  cmovnz  r13d, [rbp+arg_20]
0x180057ede  lea     rcx, [rdi+rdi*2]
0x180057ee2  add     rcx, rsi
0x180057ee5  mov     rcx, [rax+rcx*8-18h]; psz
0x180057eea  call    cs:__imp_SysAllocString
0x180057ef0  xor     edi, edi
0x180057ef2  mov     [rbp+bstrString], rax
0x180057ef6  mov     rbx, rax
0x180057ef9  test    rax, rax
0x180057efc  jnz     short loc_180057F10
0x180057efe  mov     esi, edi
0x180057f00  mov     ebx, 8007000Eh
0x180057f05  mov     r15d, edi
0x180057f08  mov     r14d, edi
0x180057f0b  jmp     loc_180058291
0x180057f10  lea     rcx, aWcsText; "wcs:Text"
0x180057f17  call    cs:__imp_SysAllocString
0x180057f1d  mov     [rbp+var_58], rax
0x180057f21  mov     rsi, rax
0x180057f24  test    rax, rax
0x180057f27  jnz     short loc_180057F39
0x180057f29  mov     ebx, 8007000Eh
0x180057f2e  mov     r15, rdi
0x180057f31  mov     r14, rdi
0x180057f34  jmp     loc_180058291
0x180057f39  lea     rcx, aXmlLang; "xml:lang"
0x180057f40  call    cs:__imp_SysAllocString
0x180057f46  mov     [rbp+var_28], rax
0x180057f4a  test    rax, rax
0x180057f4d  jz      short loc_180057F29
0x180057f4f  mov     rax, [r15]
0x180057f52  lea     r8, [rbp+var_38]
0x180057f56  mov     rdx, rbx
0x180057f59  mov     rcx, r15
0x180057f5c  mov     rax, [rax+128h]
0x180057f63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057f68  mov     ebx, eax
0x180057f6a  test    eax, eax
0x180057f6c  js      short loc_180057F2E
0x180057f6e  cmp     eax, 1
0x180057f71  jnz     short loc_180057F80
0x180057f73  mov     ebx, edi
0x180057f75  mov     r15d, ebx
0x180057f78  mov     r14d, ebx
0x180057f7b  jmp     loc_180058291
0x180057f80  mov     rcx, [rbp+var_38]
0x180057f84  lea     r8, [rbp+var_30]
0x180057f88  lea     rdx, IID_IXMLDOMElement
0x180057f8f  mov     rax, [rcx]
0x180057f92  mov     rax, [rax]
0x180057f95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057f9a  mov     ebx, eax
0x180057f9c  test    eax, eax
0x180057f9e  js      short loc_180057F2E
0x180057fa0  mov     rcx, [rbp+var_30]
0x180057fa4  lea     r8, [rbp+var_48]
0x180057fa8  mov     rdx, rsi
0x180057fab  mov     rax, [rcx]
0x180057fae  mov     rax, [rax+190h]
0x180057fb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057fba  mov     ebx, eax
0x180057fbc  test    eax, eax
0x180057fbe  js      loc_180057F2E
0x180057fc4  mov     rcx, [rbp+var_48]
0x180057fc8  lea     rdx, [rbp+arg_8]
0x180057fcc  mov     rax, [rcx]
0x180057fcf  mov     rax, [rax+40h]
0x180057fd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057fd8  mov     ebx, eax
0x180057fda  test    eax, eax
0x180057fdc  js      loc_180057F2E
0x180057fe2  cmp     [rbp+arg_8], edi
0x180057fe5  jg      short loc_180057FF1
0x180057fe7  mov     ebx, 800707DBh
0x180057fec  jmp     loc_180057F2E
0x180057ff1  movsxd  rcx, [rbp+arg_8]
0x180057ff5  mov     ebx, 8
0x180057ffa  mov     eax, ebx
0x180057ffc  mul     rcx
0x180057fff  lea     rsi, [rbx-9]
0x180058003  cmovb   rax, rsi
0x180058007  mov     rcx, rax; unsigned __int64
0x18005800a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18005800f  movsxd  r8, [rbp+arg_8]
0x180058013  xor     edx, edx; Val
0x180058015  shl     r8, 3; Size
0x180058019  mov     rcx, rax; void *
0x18005801c  mov     r12, rax
0x18005801f  call    memset_0
0x180058024  movsxd  rcx, [rbp+arg_8]
0x180058028  mov     eax, ebx
0x18005802a  mul     rcx
0x18005802d  cmovb   rax, rsi
0x180058031  mov     rcx, rax; unsigned __int64
0x180058034  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180058039  movsxd  r8, [rbp+arg_8]
0x18005803d  xor     edx, edx; Val
0x18005803f  shl     r8, 3; Size
0x180058043  mov     rcx, rax; void *
0x180058046  mov     r15, rax
0x180058049  mov     [rbp+arg_18], rax
0x18005804d  call    memset_0
0x180058052  cmp     [rbp+arg_8], edi
0x180058055  jle     loc_180058107
0x18005805b  mov     rcx, [rbp+var_48]
0x18005805f  lea     r8, [rbp+var_50]
0x180058063  mov     edx, edi
0x180058065  mov     rax, [rcx]
0x180058068  mov     rax, [rax+38h]
0x18005806c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058071  mov     ebx, eax
0x180058073  test    eax, eax
0x180058075  js      loc_180058287
0x18005807b  mov     rcx, [rbp+var_50]
0x18005807f  lea     rdx, IID_IXMLDOMElement
0x180058086  movsxd  rsi, edi
0x180058089  mov     rax, [rcx]
0x18005808c  lea     r15, [r15+rsi*8]
0x180058090  mov     r8, r15
0x180058093  mov     rax, [rax]
0x180058096  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005809b  mov     ebx, eax
0x18005809d  test    eax, eax
0x18005809f  js      loc_180058283
0x1800580a5  mov     rcx, [r15]
0x1800580a8  lea     r8, [rbp+pvarg]
0x1800580ac  mov     rdx, [rbp+var_28]
0x1800580b0  mov     rax, [rcx]
0x1800580b3  mov     rax, [rax+160h]
0x1800580ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800580bf  xor     r15d, r15d
0x1800580c2  mov     ebx, eax
0x1800580c4  test    eax, eax
0x1800580c6  js      loc_180058283
0x1800580cc  jnz     short loc_1800580E4
0x1800580ce  mov     rax, qword ptr [rbp+pvarg+8]
0x1800580d2  mov     [r12+rsi*8], rax
0x1800580d6  mov     qword ptr [rbp+pvarg+8], r15
0x1800580da  mov     rcx, [r12+rsi*8]; lpsz
0x1800580de  call    cs:__imp_CharUpperW
0x1800580e4  mov     rcx, [rbp+var_50]
0x1800580e8  mov     rax, [rcx]
0x1800580eb  mov     rax, [rax+10h]
0x1800580ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800580f4  inc     edi
0x1800580f6  mov     [rbp+var_50], r15
0x1800580fa  mov     r15, [rbp+arg_18]
0x1800580fe  cmp     edi, [rbp+arg_8]
0x180058101  jl      loc_18005805B
0x180058107  xor     edi, edi
0x180058109  lea     r13, [r14+r13*2]
0x18005810d  mov     r15d, edi
0x180058110  mov     sil, dil
0x180058113  jmp     loc_180058204
0x180058118  cmp     [r14], di
0x18005811c  jz      loc_18005820D
0x180058122  test    sil, sil
0x180058125  jnz     loc_18005820D
0x18005812b  xor     r9d, r9d
0x18005812e  cmp     [rbp+arg_8], r9d
0x180058132  jle     loc_1800581EC
0x180058138  movsxd  rax, edi
0x18005813b  mov     rbx, [r12+rax*8]
0x18005813f  test    rbx, rbx
0x180058142  jz      loc_1800581D9
0x180058148  mov     edx, 2Dh ; '-'; Ch
0x18005814d  mov     rcx, r14; Str
0x180058150  call    cs:__imp_wcschr
0x180058156  xor     r9d, r9d
0x180058159  test    rax, rax
0x18005815c  jz      short loc_180058179
0x18005815e  mov     rdx, r14
0x180058161  sub     rdx, rbx
0x180058164  movzx   ecx, word ptr [rbx]
0x180058167  movzx   eax, word ptr [rbx+rdx]
0x18005816b  sub     ecx, eax
0x18005816d  jnz     short loc_1800581D5
0x18005816f  add     rbx, 2
0x180058173  test    eax, eax
0x180058175  jnz     short loc_180058164
0x180058177  jmp     short loc_1800581D5
0x180058179  mov     edx, 2Dh ; '-'; Ch
0x18005817e  mov     rcx, rbx; Str
0x180058181  call    cs:__imp_wcschr
0x180058187  xor     r9d, r9d
0x18005818a  test    rax, rax
0x18005818d  jz      short loc_1800581BC
0x18005818f  sub     rax, rbx
0x180058192  sar     rax, 1
0x180058195  mov     ecx, eax
0x180058197  or      r8, 0FFFFFFFFFFFFFFFFh
0x18005819b  inc     r8; MaxCount
0x18005819e  cmp     [r14+r8*2], r9w
0x1800581a3  jnz     short loc_18005819B
0x1800581a5  cmp     rcx, r8
0x1800581a8  jnz     short loc_1800581D9
0x1800581aa  mov     rdx, r14; String2
0x1800581ad  mov     rcx, rbx; String1
0x1800581b0  call    wcsncmp_0
0x1800581b5  xor     r9d, r9d
0x1800581b8  test    eax, eax
0x1800581ba  jmp     short loc_1800581D7
0x1800581bc  mov     rdx, r14
0x1800581bf  sub     rdx, rbx
0x1800581c2  movzx   ecx, word ptr [rbx]
0x1800581c5  movzx   eax, word ptr [rbx+rdx]
0x1800581c9  sub     ecx, eax
0x1800581cb  jnz     short loc_1800581D5
0x1800581cd  add     rbx, 2
0x1800581d1  test    eax, eax
0x1800581d3  jnz     short loc_1800581C2
0x1800581d5  test    ecx, ecx
0x1800581d7  jz      short loc_1800581E6
0x1800581d9  inc     edi
0x1800581db  cmp     edi, [rbp+arg_8]
0x1800581de  jl      loc_180058138
0x1800581e4  jmp     short loc_1800581EC
0x1800581e6  mov     r15d, edi
0x1800581e9  mov     sil, 1
0x1800581ec  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800581f0  xor     edi, edi
0x1800581f2  inc     rax
0x1800581f5  cmp     [r14+rax*2], di
0x1800581fa  jnz     short loc_1800581F2
0x1800581fc  lea     r14, [r14+rax*2]
0x180058200  add     r14, 2
0x180058204  cmp     r14, r13
0x180058207  jb      loc_180058118
0x18005820d  movsxd  rax, r15d
0x180058210  lea     rdx, [rbp+pbstr]
0x180058214  mov     r15, [rbp+arg_18]
0x180058218  mov     rcx, [r15+rax*8]
0x18005821c  mov     rax, [rcx]
0x18005821f  mov     rax, [rax+0D0h]
0x180058226  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005822b  mov     ebx, eax
0x18005822d  test    eax, eax
0x18005822f  js      short loc_180058289
0x180058231  mov     rcx, [rbp+pbstr]; pbstr
0x180058235  call    cs:__imp_SysStringLen
0x18005823b  inc     eax
0x18005823d  cmp     eax, 1
0x180058240  jz      short loc_180058289
0x180058242  mov     ebx, eax
0x180058244  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18005824b  mov     eax, 2
0x180058250  mul     rbx
0x180058253  cmovb   rax, rcx
0x180058257  mov     rcx, rax; unsigned __int64
0x18005825a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18005825f  mov     r8, [rbp+pbstr]; unsigned __int16 *
0x180058263  mov     edx, ebx; unsigned __int64
0x180058265  mov     rcx, rax; unsigned __int16 *
0x180058268  mov     r14, rax
0x18005826b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180058270  mov     rsi, [rbp+var_58]
0x180058274  mov     ebx, eax
0x180058276  test    eax, eax
0x180058278  js      short loc_180058291
0x18005827a  mov     rax, [rbp+arg_28]
0x18005827e  mov     [rax], r14
  ... truncated ...
```
