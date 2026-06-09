# SetNsAndSchema(IXMLDOMDocument2 *,ushort const *,ushort const * *,ushort const * *,ulong,ulong)

- ea: `0x18002d070`
- end: `0x18002d519`
- name: `?SetNsAndSchema@@YAJPEAUIXMLDOMDocument2@@PEBGPEAPEBG2KK@Z`
- size: `1193`
- prototype: `int(struct IXMLDOMDocument2 *, const unsigned __int16 *, const unsigned __int16 **, const unsigned __int16 **, unsigned int, unsigned int)`
- caller_count: `5`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800055e0`
- `0x180062228`
- `0x180062614`
- `0x180062a50`
- `0x180062e58`

## callees

- `0x180005010`
- `0x180010140`
- `0x180019730`
- `0x18002d070`
- `0x180061f9c`
- `0x180082010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18002d29f`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18002d29f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18002d316`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18002d316`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002d2fb`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002d2fb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002d1bc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002d1bc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002d24c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002d24c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d379`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d4c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d379`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d4c1`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002d22d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002d26d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002d22d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002d26d`
- `OLEAUT32!__imp_SysAllocString` at `0x18002d0f2`
- `OLEAUT32!__imp_SysAllocString` at `0x18002d12c`
- `OLEAUT32!__imp_SysAllocString` at `0x18002d0f2`
- `OLEAUT32!__imp_SysAllocString` at `0x18002d12c`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18002d2cd`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18002d2cd`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d0df`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d4f8`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d0df`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d4f8`
- `OLEAUT32!__imp_VariantInit` at `0x18002d09e`
- `OLEAUT32!__imp_VariantInit` at `0x18002d09e`
- `OLEAUT32!__imp_VariantClear` at `0x18002d114`
- `OLEAUT32!__imp_VariantClear` at `0x18002d2b3`
- `OLEAUT32!__imp_VariantClear` at `0x18002d44a`
- `OLEAUT32!__imp_VariantClear` at `0x18002d45e`
- `OLEAUT32!__imp_VariantClear` at `0x18002d4e8`
- `OLEAUT32!__imp_VariantClear` at `0x18002d114`
- `OLEAUT32!__imp_VariantClear` at `0x18002d2b3`
- `OLEAUT32!__imp_VariantClear` at `0x18002d44a`
- `OLEAUT32!__imp_VariantClear` at `0x18002d45e`
- `OLEAUT32!__imp_VariantClear` at `0x18002d4e8`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SetNsAndSchema(
        struct IXMLDOMDocument2 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 **a3,
        const unsigned __int16 **a4)
{
  int v6; // ecx
  OLECHAR *v7; // rbx
  BSTR v8; // rax
  int v9; // ecx
  WCHAR *v10; // r14
  unsigned int v11; // edi
  unsigned int v12; // eax
  struct _EAPTLS_CONTROL_BLOCK *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  signed int i; // eax
  __int64 v17; // r13
  const WCHAR *v18; // r12
  DWORD v19; // eax
  DWORD v20; // edi
  WCHAR *v21; // rax
  UINT v22; // r12d
  BSTR v23; // rax
  unsigned int v24; // eax
  LPVOID v25; // rdi
  VARIANTARG pvarg; // [rsp+38h] [rbp-69h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-51h] BYREF
  OLECHAR *v29; // [rsp+58h] [rbp-49h] BYREF
  VARIANTARG v30; // [rsp+68h] [rbp-39h] BYREF
  LPCWSTR lpSrc[12]; // [rsp+88h] [rbp-19h]
  unsigned int v36; // [rsp+118h] [rbp+77h]

  VariantInit(&pvarg);
  ppv = 0;
  lpSrc[0] = L"%windir%\\schemas\\EAPHost\\";
  lpSrc[1] = L"%windir%\\schemas\\EAPMethods\\";
  lpSrc[2] = L"%windir%\\schemas\\EAPMethods\\";
  lpSrc[3] = L"%windir%\\schemas\\EAPMethods\\";
  lpSrc[4] = L"%windir%\\schemas\\EAPMethods\\";
  lpSrc[5] = 0;
  SysFreeString(0);
  v7 = SysAllocString(L"SelectionNamespaces");
  v29 = v7;
  if ( !v7 )
    ATL::AtlThrowImpl(v6);
  VariantClear(&pvarg);
  pvarg.vt = 8;
  v8 = SysAllocString(a2);
  pvarg.llVal = (LONGLONG)v8;
  if ( !v8 && a2 )
  {
    pvarg.vt = 10;
    pvarg.lVal = -2147024882;
    ATL::AtlThrowImpl(v9);
  }
  v10 = 0;
  if ( !v8 )
  {
LABEL_36:
    v11 = -2147024882;
    goto LABEL_37;
  }
  v30 = pvarg;
  v11 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, OLECHAR *, VARIANTARG *))a1->lpVtbl->setProperty)(
          a1,
          v7,
          &v30);
  if ( v11 )
    goto LABEL_37;
  v12 = CoCreateInstance(&CLSID_XMLSchemaCache60, 0, 1u, &IID_IXMLDOMSchemaCollection2, &ppv);
  v11 = v12;
  if ( v12 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      v14 = 257;
      v15 = v12;
      goto LABEL_11;
    }
    goto LABEL_37;
  }
  for ( i = 0; ; i = v36 + 1 )
  {
    v36 = i;
    v17 = i;
    if ( !a3[i] )
    {
      VariantClear(&pvarg);
      v25 = ppv;
      VariantClear(&pvarg);
      pvarg.vt = 9;
      pvarg.llVal = (LONGLONG)v25;
      if ( v25 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v25 + 8LL))(v25);
      v30 = pvarg;
      v11 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, VARIANTARG *))a1->lpVtbl->putref_schemas)(a1, &v30);
      goto LABEL_32;
    }
    v18 = lpSrc[i];
    v19 = ExpandEnvironmentStringsW(v18, 0, 0);
    v20 = v19;
    if ( !v19 )
    {
      v11 = -2147467259;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 259, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v18);
LABEL_32:
      v10 = 0;
      goto LABEL_37;
    }
    v21 = (WCHAR *)LocalAlloc(0x40u, 2LL * v19);
    v10 = v21;
    if ( !v21 )
      goto LABEL_36;
    if ( ExpandEnvironmentStringsW(v18, v21, v20) > v20 )
    {
      v11 = -2147467259;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 258, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v18);
      goto LABEL_37;
    }
    ATL::CComBSTR::operator=(&v29, a3[v17]);
    v22 = wcsnlen(a4[v17], 0x400u) + v20;
    VariantClear(&pvarg);
    pvarg.vt = 8;
    v23 = SysAllocStringLen(0, v22);
    pvarg.llVal = (LONGLONG)v23;
    v7 = v29;
    if ( !v29 || !v23 )
      goto LABEL_36;
    _o_wcscpy_s(v23, v20, v10);
    _o_wcscat_s(pvarg.llVal, v22, a4[v17]);
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 260, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, pvarg.llVal);
    v30 = pvarg;
    v24 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, VARIANTARG *))(*(_QWORD *)ppv + 56LL))(ppv, v7, &v30);
    v11 = v24;
    if ( v24 )
      break;
    LocalFree(v10);
  }
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 261, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v24);
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      v15 = (unsigned __int16)v11;
      if ( (v11 & 0x1FFF0000) != 0x70000 )
        v15 = v11;
      v14 = 262;
LABEL_11:
      WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v15);
    }
  }
LABEL_37:
  LocalFree(v10);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  VariantClear(&pvarg);
  SysFreeString(v7);
  return v11;
}

```

## disassembly

```asm
0x18002d070  mov     rax, rsp
0x18002d073  mov     [rax+20h], r9
0x18002d077  mov     [rax+18h], r8
0x18002d07b  mov     [rax+8], rcx
0x18002d07f  push    rbp
0x18002d080  push    rbx
0x18002d081  push    rsi
0x18002d082  push    rdi
0x18002d083  push    r12
0x18002d085  push    r13
0x18002d087  push    r14
0x18002d089  lea     rbp, [rax-4Fh]
0x18002d08d  sub     rsp, 0B0h
0x18002d094  mov     rdi, rdx
0x18002d097  mov     r12, rcx
0x18002d09a  lea     rcx, [rbp+47h+pvarg]; pvarg
0x18002d09e  call    cs:__imp_VariantInit
0x18002d0a5  nop     dword ptr [rax+rax+00h]
0x18002d0aa  nop
0x18002d0ab  mov     [rbp+47h+ppv], 0
0x18002d0b3  lea     rax, aWindirSchemasE_0; "%windir%\\schemas\\EAPHost\\"
0x18002d0ba  mov     [rbp+47h+lpSrc], rax
0x18002d0be  lea     rax, aWindirSchemasE; "%windir%\\schemas\\EAPMethods\\"
0x18002d0c5  mov     [rbp+47h+var_58], rax
0x18002d0c9  mov     [rbp+47h+var_50], rax
0x18002d0cd  mov     [rbp+47h+var_48], rax
0x18002d0d1  mov     [rbp+47h+var_40], rax
0x18002d0d5  mov     [rbp+47h+var_38], 0
0x18002d0dd  xor     ecx, ecx; bstrString
0x18002d0df  call    cs:__imp_SysFreeString
0x18002d0e6  nop     dword ptr [rax+rax+00h]
0x18002d0eb  lea     rcx, aSelectionnames; "SelectionNamespaces"
0x18002d0f2  call    cs:__imp_SysAllocString
0x18002d0f9  nop     dword ptr [rax+rax+00h]
0x18002d0fe  mov     rbx, rax
0x18002d101  mov     [rbp+47h+var_90], rax
0x18002d105  test    rax, rax
0x18002d108  jnz     short loc_18002D110
0x18002d10a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002d110  lea     rcx, [rbp+47h+pvarg]; pvarg
0x18002d114  call    cs:__imp_VariantClear
0x18002d11b  nop     dword ptr [rax+rax+00h]
0x18002d120  mov     eax, 8
0x18002d125  mov     word ptr [rbp+47h+pvarg], ax
0x18002d129  mov     rcx, rdi; psz
0x18002d12c  call    cs:__imp_SysAllocString
0x18002d133  nop     dword ptr [rax+rax+00h]
0x18002d138  mov     qword ptr [rbp+47h+pvarg+8], rax
0x18002d13c  test    rax, rax
0x18002d13f  jnz     short loc_18002D15D
0x18002d141  test    rdi, rdi
0x18002d144  jz      short loc_18002D15D
0x18002d146  mov     eax, 0Ah
0x18002d14b  mov     word ptr [rbp+47h+pvarg], ax
0x18002d14f  mov     edi, 8007000Eh
0x18002d154  mov     dword ptr [rbp+47h+pvarg+8], edi
0x18002d157  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002d15d  xor     r14d, r14d
0x18002d160  test    rax, rax
0x18002d163  jz      loc_18002D4B9
0x18002d169  movups  xmm0, xmmword ptr [rbp+47h+pvarg]
0x18002d16d  movaps  [rbp+47h+var_80], xmm0
0x18002d171  movsd   xmm1, qword ptr [rbp+47h+pvarg+10h]
0x18002d176  movsd   [rbp+47h+var_70], xmm1
0x18002d17b  mov     rax, [r12]
0x18002d17f  lea     r8, [rbp+47h+var_80]
0x18002d183  mov     rdx, rbx
0x18002d186  mov     rcx, r12
0x18002d189  mov     rax, [rax+280h]
0x18002d190  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d195  mov     edi, eax
0x18002d197  test    eax, eax
0x18002d199  jnz     loc_18002D4BE
0x18002d19f  lea     rax, [rbp+47h+ppv]
0x18002d1a3  mov     [rsp+20h], rax; ppv
0x18002d1a8  lea     r9, IID_IXMLDOMSchemaCollection2; riid
0x18002d1af  xor     edx, edx; pUnkOuter
0x18002d1b1  lea     r8d, [r14+1]; dwClsContext
0x18002d1b5  lea     rcx, CLSID_XMLSchemaCache60; rclsid
0x18002d1bc  call    cs:__imp_CoCreateInstance
0x18002d1c3  nop     dword ptr [rax+rax+00h]
0x18002d1c8  mov     edi, eax
0x18002d1ca  test    eax, eax
0x18002d1cc  jz      short loc_18002D202
0x18002d1ce  lea     rsi, WPP_GLOBAL_Control
0x18002d1d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d1dc  cmp     rcx, rsi
0x18002d1df  jz      loc_18002D4BE
0x18002d1e5  mov     edx, 101h
0x18002d1ea  mov     r9d, eax
0x18002d1ed  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18002d1f4  mov     rcx, [rcx+10h]
0x18002d1f8  call    WPP_SF_d
0x18002d1fd  jmp     loc_18002D4BE
0x18002d202  xor     eax, eax
0x18002d204  lea     rsi, WPP_GLOBAL_Control
0x18002d20b  mov     [rbp+47h+arg_20], eax
0x18002d20e  movsxd  r13, eax
0x18002d211  mov     rax, [rbp+47h+arg_10]
0x18002d215  cmp     qword ptr [rax+r13*8], 0
0x18002d21a  jz      loc_18002D446
0x18002d220  mov     r12, [rbp+r13*8+47h+lpSrc]
0x18002d225  xor     r8d, r8d; nSize
0x18002d228  xor     edx, edx; lpDst
0x18002d22a  mov     rcx, r12; lpSrc
0x18002d22d  call    cs:__imp_ExpandEnvironmentStringsW
0x18002d234  nop     dword ptr [rax+rax+00h]
0x18002d239  mov     edi, eax
0x18002d23b  test    eax, eax
0x18002d23d  jz      loc_18002D418
0x18002d243  lea     rdx, [rdi+rdi]; uBytes
0x18002d247  mov     ecx, 40h ; '@'; uFlags
0x18002d24c  call    cs:__imp_LocalAlloc
0x18002d253  nop     dword ptr [rax+rax+00h]
0x18002d258  mov     r14, rax
0x18002d25b  test    rax, rax
0x18002d25e  jz      loc_18002D4B9
0x18002d264  mov     r8d, edi; nSize
0x18002d267  mov     rdx, rax; lpDst
0x18002d26a  mov     rcx, r12; lpSrc
0x18002d26d  call    cs:__imp_ExpandEnvironmentStringsW
0x18002d274  nop     dword ptr [rax+rax+00h]
0x18002d279  cmp     eax, edi
0x18002d27b  ja      loc_18002D3E6
0x18002d281  mov     rax, [rbp+47h+arg_10]
0x18002d285  mov     rdx, [rax+r13*8]
0x18002d289  lea     rcx, [rbp+47h+var_90]
0x18002d28d  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18002d292  mov     edx, 400h; MaxCount
0x18002d297  mov     rcx, [rbp+47h+arg_18]
0x18002d29b  mov     rcx, [rcx+r13*8]; Source
0x18002d29f  call    cs:__imp_wcsnlen
0x18002d2a6  nop     dword ptr [rax+rax+00h]
0x18002d2ab  lea     r12d, [rax+rdi]
0x18002d2af  lea     rcx, [rbp+47h+pvarg]; pvarg
0x18002d2b3  call    cs:__imp_VariantClear
0x18002d2ba  nop     dword ptr [rax+rax+00h]
0x18002d2bf  mov     eax, 8
0x18002d2c4  mov     word ptr [rbp+47h+pvarg], ax
0x18002d2c8  mov     edx, r12d; ui
0x18002d2cb  xor     ecx, ecx; strIn
0x18002d2cd  call    cs:__imp_SysAllocStringLen
0x18002d2d4  nop     dword ptr [rax+rax+00h]
0x18002d2d9  mov     qword ptr [rbp+47h+pvarg+8], rax
0x18002d2dd  mov     rbx, [rbp+47h+var_90]
0x18002d2e1  test    rbx, rbx
0x18002d2e4  jz      loc_18002D4B9
0x18002d2ea  test    rax, rax
0x18002d2ed  jz      loc_18002D4B9
0x18002d2f3  mov     r8, r14
0x18002d2f6  mov     edx, edi
0x18002d2f8  mov     rcx, rax
0x18002d2fb  call    cs:__imp__o_wcscpy_s
0x18002d302  nop     dword ptr [rax+rax+00h]
0x18002d307  mov     edx, r12d
0x18002d30a  mov     rax, [rbp+47h+arg_18]
0x18002d30e  mov     r8, [rax+r13*8]
0x18002d312  mov     rcx, qword ptr [rbp+47h+pvarg+8]
0x18002d316  call    cs:__imp__o_wcscat_s
0x18002d31d  nop     dword ptr [rax+rax+00h]
0x18002d322  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d329  cmp     rcx, rsi
0x18002d32c  jz      short loc_18002D347
0x18002d32e  mov     edx, 104h
0x18002d333  mov     r9, qword ptr [rbp+47h+pvarg+8]
0x18002d337  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18002d33e  mov     rcx, [rcx+10h]
0x18002d342  call    WPP_SF_S
0x18002d347  mov     rcx, [rbp+47h+ppv]
0x18002d34b  movups  xmm0, xmmword ptr [rbp+47h+pvarg]
0x18002d34f  movaps  [rbp+47h+var_80], xmm0
0x18002d353  movsd   xmm1, qword ptr [rbp+47h+pvarg+10h]
0x18002d358  movsd   [rbp+47h+var_70], xmm1
0x18002d35d  mov     rax, [rcx]
0x18002d360  lea     r8, [rbp+47h+var_80]
0x18002d364  mov     rdx, rbx
0x18002d367  mov     rax, [rax+38h]
0x18002d36b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d370  mov     edi, eax
0x18002d372  test    eax, eax
0x18002d374  jnz     short loc_18002D38F
0x18002d376  mov     rcx, r14; hMem
0x18002d379  call    cs:__imp_LocalFree
0x18002d380  nop     dword ptr [rax+rax+00h]
0x18002d385  mov     eax, [rbp+47h+arg_20]
0x18002d388  inc     eax
0x18002d38a  jmp     loc_18002D20B
0x18002d38f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d396  cmp     rcx, rsi
0x18002d399  jz      loc_18002D4BE
0x18002d39f  mov     edx, 105h
0x18002d3a4  mov     r9d, edi
0x18002d3a7  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18002d3ae  mov     rcx, [rcx+10h]
0x18002d3b2  call    WPP_SF_d
0x18002d3b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d3be  cmp     rcx, rsi
0x18002d3c1  jz      loc_18002D4BE
0x18002d3c7  mov     eax, edi
0x18002d3c9  and     eax, 1FFF0000h
0x18002d3ce  cmp     eax, 70000h
0x18002d3d3  movzx   r9d, di
0x18002d3d7  jz      short loc_18002D3DC
0x18002d3d9  mov     r9d, edi
0x18002d3dc  mov     edx, 106h
0x18002d3e1  jmp     loc_18002D1ED
0x18002d3e6  mov     edi, 80004005h
0x18002d3eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d3f2  cmp     rcx, rsi
0x18002d3f5  jz      loc_18002D4BE
0x18002d3fb  mov     edx, 102h
0x18002d400  mov     r9, r12
0x18002d403  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18002d40a  mov     rcx, [rcx+10h]
0x18002d40e  call    WPP_SF_S
0x18002d413  jmp     loc_18002D4BE
0x18002d418  mov     edi, 80004005h
0x18002d41d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d424  cmp     rcx, rsi
0x18002d427  jz      short loc_18002D441
0x18002d429  mov     edx, 103h
0x18002d42e  mov     r9, r12
0x18002d431  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18002d438  mov     rcx, [rcx+10h]
0x18002d43c  call    WPP_SF_S
0x18002d441  xor     r14d, r14d
0x18002d444  jmp     short loc_18002D4BE
0x18002d446  lea     rcx, [rbp+47h+pvarg]; pvarg
0x18002d44a  call    cs:__imp_VariantClear
0x18002d451  nop     dword ptr [rax+rax+00h]
0x18002d456  mov     rdi, [rbp+47h+ppv]
0x18002d45a  lea     rcx, [rbp+47h+pvarg]; pvarg
0x18002d45e  call    cs:__imp_VariantClear
0x18002d465  nop     dword ptr [rax+rax+00h]
0x18002d46a  mov     eax, 9
0x18002d46f  mov     word ptr [rbp+47h+pvarg], ax
0x18002d473  mov     qword ptr [rbp+47h+pvarg+8], rdi
0x18002d477  test    rdi, rdi
0x18002d47a  jz      short loc_18002D48C
0x18002d47c  mov     rax, [rdi]
0x18002d47f  mov     rcx, rdi
0x18002d482  mov     rax, [rax+8]
0x18002d486  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d48b  nop
0x18002d48c  movups  xmm0, xmmword ptr [rbp+47h+pvarg]
0x18002d490  movaps  [rbp+47h+var_80], xmm0
0x18002d494  movsd   xmm1, qword ptr [rbp+47h+pvarg+10h]
0x18002d499  movsd   [rbp+47h+var_70], xmm1
0x18002d49e  mov     rcx, [rbp+47h+arg_0]
0x18002d4a2  mov     rax, [rcx]
0x18002d4a5  lea     rdx, [rbp+47h+var_80]
0x18002d4a9  mov     rax, [rax+270h]
0x18002d4b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d4b5  mov     edi, eax
0x18002d4b7  jmp     short loc_18002D441
0x18002d4b9  mov     edi, 8007000Eh
0x18002d4be  mov     rcx, r14; hMem
0x18002d4c1  call    cs:__imp_LocalFree
0x18002d4c8  nop     dword ptr [rax+rax+00h]
0x18002d4cd  nop
0x18002d4ce  mov     rcx, [rbp+47h+ppv]
0x18002d4d2  test    rcx, rcx
0x18002d4d5  jz      short loc_18002D4E4
0x18002d4d7  mov     rax, [rcx]
0x18002d4da  mov     rax, [rax+10h]
0x18002d4de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d4e3  nop
0x18002d4e4  lea     rcx, [rbp+47h+pvarg]; pvarg
0x18002d4e8  call    cs:__imp_VariantClear
0x18002d4ef  nop     dword ptr [rax+rax+00h]
0x18002d4f4  nop
0x18002d4f5  mov     rcx, rbx; bstrString
0x18002d4f8  call    cs:__imp_SysFreeString
0x18002d4ff  nop     dword ptr [rax+rax+00h]
0x18002d504  mov     eax, edi
0x18002d506  add     rsp, 0B0h
0x18002d50d  pop     r14
0x18002d50f  pop     r13
0x18002d511  pop     r12
0x18002d513  pop     rdi
0x18002d514  pop     rsi
0x18002d515  pop     rbx
0x18002d516  pop     rbp
0x18002d517  retn
```
