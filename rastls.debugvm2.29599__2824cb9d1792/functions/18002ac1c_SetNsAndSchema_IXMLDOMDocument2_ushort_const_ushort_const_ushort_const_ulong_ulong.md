# SetNsAndSchema(IXMLDOMDocument2 *,ushort const *,ushort const * *,ushort const * *,ulong,ulong)

- ea: `0x18002ac1c`
- end: `0x18002b04c`
- name: `?SetNsAndSchema@@YAJPEAUIXMLDOMDocument2@@PEBGPEAPEBG2KK@Z`
- size: `1072`
- prototype: `int(struct IXMLDOMDocument2 *, const unsigned __int16 *, const unsigned __int16 **, const unsigned __int16 **, unsigned int, unsigned int)`
- caller_count: `5`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180005170`
- `0x18005ea34`
- `0x18005ee0c`
- `0x18005f230`
- `0x18005f628`

## callees

- `0x180004bd0`
- `0x18000f350`
- `0x180017f00`
- `0x18002ac1c`
- `0x18005e7c8`
- `0x18007c010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18002ae15`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18002ae15`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18002ae74`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18002ae74`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002ae5f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002ae5f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002ad4a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002ad4a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002adce`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002adce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aed1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b007`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aed1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b007`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002adb5`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002ade9`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002adb5`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002ade9`
- `OLEAUT32!__imp_SysAllocString` at `0x18002ac92`
- `OLEAUT32!__imp_SysAllocString` at `0x18002acc0`
- `OLEAUT32!__imp_SysAllocString` at `0x18002ac92`
- `OLEAUT32!__imp_SysAllocString` at `0x18002acc0`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18002ae37`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18002ae37`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ac85`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b032`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ac85`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b032`
- `OLEAUT32!__imp_VariantInit` at `0x18002ac4a`
- `OLEAUT32!__imp_VariantInit` at `0x18002ac4a`
- `OLEAUT32!__imp_VariantClear` at `0x18002acae`
- `OLEAUT32!__imp_VariantClear` at `0x18002ae23`
- `OLEAUT32!__imp_VariantClear` at `0x18002af9c`
- `OLEAUT32!__imp_VariantClear` at `0x18002afaa`
- `OLEAUT32!__imp_VariantClear` at `0x18002b028`
- `OLEAUT32!__imp_VariantClear` at `0x18002acae`
- `OLEAUT32!__imp_VariantClear` at `0x18002ae23`
- `OLEAUT32!__imp_VariantClear` at `0x18002af9c`
- `OLEAUT32!__imp_VariantClear` at `0x18002afaa`
- `OLEAUT32!__imp_VariantClear` at `0x18002b028`

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
0x18002ac1c  mov     rax, rsp
0x18002ac1f  mov     [rax+20h], r9
0x18002ac23  mov     [rax+18h], r8
0x18002ac27  mov     [rax+8], rcx
0x18002ac2b  push    rbp
0x18002ac2c  push    rbx
0x18002ac2d  push    rsi
0x18002ac2e  push    rdi
0x18002ac2f  push    r12
0x18002ac31  push    r13
0x18002ac33  push    r14
0x18002ac35  lea     rbp, [rax-4Fh]
0x18002ac39  sub     rsp, 0B0h
0x18002ac40  mov     rdi, rdx
0x18002ac43  mov     r12, rcx
0x18002ac46  lea     rcx, [rbp+47h+pvarg]; pvarg
0x18002ac4a  call    cs:__imp_VariantInit
0x18002ac50  nop
0x18002ac51  mov     [rbp+47h+ppv], 0
0x18002ac59  lea     rax, aWindirSchemasE_0; "%windir%\\schemas\\EAPHost\\"
0x18002ac60  mov     [rbp+47h+lpSrc], rax
0x18002ac64  lea     rax, aWindirSchemasE; "%windir%\\schemas\\EAPMethods\\"
0x18002ac6b  mov     [rbp+47h+var_58], rax
0x18002ac6f  mov     [rbp+47h+var_50], rax
0x18002ac73  mov     [rbp+47h+var_48], rax
0x18002ac77  mov     [rbp+47h+var_40], rax
0x18002ac7b  mov     [rbp+47h+var_38], 0
0x18002ac83  xor     ecx, ecx; bstrString
0x18002ac85  call    cs:__imp_SysFreeString
0x18002ac8b  lea     rcx, aSelectionnames; "SelectionNamespaces"
0x18002ac92  call    cs:__imp_SysAllocString
0x18002ac98  mov     rbx, rax
0x18002ac9b  mov     [rbp+47h+var_90], rax
0x18002ac9f  test    rax, rax
0x18002aca2  jnz     short loc_18002ACAA
0x18002aca4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002acaa  lea     rcx, [rbp+47h+pvarg]; pvarg
0x18002acae  call    cs:__imp_VariantClear
0x18002acb4  mov     eax, 8
0x18002acb9  mov     word ptr [rbp+47h+pvarg], ax
0x18002acbd  mov     rcx, rdi; psz
0x18002acc0  call    cs:__imp_SysAllocString
0x18002acc6  mov     qword ptr [rbp+47h+pvarg+8], rax
0x18002acca  test    rax, rax
0x18002accd  jnz     short loc_18002ACEB
0x18002accf  test    rdi, rdi
0x18002acd2  jz      short loc_18002ACEB
0x18002acd4  mov     eax, 0Ah
0x18002acd9  mov     word ptr [rbp+47h+pvarg], ax
0x18002acdd  mov     edi, 8007000Eh
0x18002ace2  mov     dword ptr [rbp+47h+pvarg+8], edi
0x18002ace5  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002aceb  xor     r14d, r14d
0x18002acee  test    rax, rax
0x18002acf1  jz      loc_18002AFFF
0x18002acf7  movups  xmm0, xmmword ptr [rbp+47h+pvarg]
0x18002acfb  movaps  [rbp+47h+var_80], xmm0
0x18002acff  movsd   xmm1, qword ptr [rbp+47h+pvarg+10h]
0x18002ad04  movsd   [rbp+47h+var_70], xmm1
0x18002ad09  mov     rax, [r12]
0x18002ad0d  lea     r8, [rbp+47h+var_80]
0x18002ad11  mov     rdx, rbx
0x18002ad14  mov     rcx, r12
0x18002ad17  mov     rax, [rax+280h]
0x18002ad1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad23  mov     edi, eax
0x18002ad25  test    eax, eax
0x18002ad27  jnz     loc_18002B004
0x18002ad2d  lea     rax, [rbp+47h+ppv]
0x18002ad31  mov     [rsp+20h], rax; ppv
0x18002ad36  lea     r9, IID_IXMLDOMSchemaCollection2; riid
0x18002ad3d  xor     edx, edx; pUnkOuter
0x18002ad3f  lea     r8d, [r14+1]; dwClsContext
0x18002ad43  lea     rcx, CLSID_XMLSchemaCache60; rclsid
0x18002ad4a  call    cs:__imp_CoCreateInstance
0x18002ad50  mov     edi, eax
0x18002ad52  test    eax, eax
0x18002ad54  jz      short loc_18002AD8A
0x18002ad56  lea     rsi, WPP_GLOBAL_Control
0x18002ad5d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ad64  cmp     rcx, rsi
0x18002ad67  jz      loc_18002B004
0x18002ad6d  mov     edx, 101h
0x18002ad72  mov     r9d, eax
0x18002ad75  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18002ad7c  mov     rcx, [rcx+10h]
0x18002ad80  call    WPP_SF_d
0x18002ad85  jmp     loc_18002B004
0x18002ad8a  xor     eax, eax
0x18002ad8c  lea     rsi, WPP_GLOBAL_Control
0x18002ad93  mov     [rbp+47h+arg_20], eax
0x18002ad96  movsxd  r13, eax
0x18002ad99  mov     rax, [rbp+47h+arg_10]
0x18002ad9d  cmp     qword ptr [rax+r13*8], 0
0x18002ada2  jz      loc_18002AF98
0x18002ada8  mov     r12, [rbp+r13*8+47h+lpSrc]
0x18002adad  xor     r8d, r8d; nSize
0x18002adb0  xor     edx, edx; lpDst
0x18002adb2  mov     rcx, r12; lpSrc
0x18002adb5  call    cs:__imp_ExpandEnvironmentStringsW
0x18002adbb  mov     edi, eax
0x18002adbd  test    eax, eax
0x18002adbf  jz      loc_18002AF6A
0x18002adc5  lea     rdx, [rdi+rdi]; uBytes
0x18002adc9  mov     ecx, 40h ; '@'; uFlags
0x18002adce  call    cs:__imp_LocalAlloc
0x18002add4  mov     r14, rax
0x18002add7  test    rax, rax
0x18002adda  jz      loc_18002AFFF
0x18002ade0  mov     r8d, edi; nSize
0x18002ade3  mov     rdx, rax; lpDst
0x18002ade6  mov     rcx, r12; lpSrc
0x18002ade9  call    cs:__imp_ExpandEnvironmentStringsW
0x18002adef  cmp     eax, edi
0x18002adf1  ja      loc_18002AF38
0x18002adf7  mov     rax, [rbp+47h+arg_10]
0x18002adfb  mov     rdx, [rax+r13*8]
0x18002adff  lea     rcx, [rbp+47h+var_90]
0x18002ae03  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18002ae08  mov     edx, 400h; MaxCount
0x18002ae0d  mov     rcx, [rbp+47h+arg_18]
0x18002ae11  mov     rcx, [rcx+r13*8]; Source
0x18002ae15  call    cs:__imp_wcsnlen
0x18002ae1b  lea     r12d, [rax+rdi]
0x18002ae1f  lea     rcx, [rbp+47h+pvarg]; pvarg
0x18002ae23  call    cs:__imp_VariantClear
0x18002ae29  mov     eax, 8
0x18002ae2e  mov     word ptr [rbp+47h+pvarg], ax
0x18002ae32  mov     edx, r12d; ui
0x18002ae35  xor     ecx, ecx; strIn
0x18002ae37  call    cs:__imp_SysAllocStringLen
0x18002ae3d  mov     qword ptr [rbp+47h+pvarg+8], rax
0x18002ae41  mov     rbx, [rbp+47h+var_90]
0x18002ae45  test    rbx, rbx
0x18002ae48  jz      loc_18002AFFF
0x18002ae4e  test    rax, rax
0x18002ae51  jz      loc_18002AFFF
0x18002ae57  mov     r8, r14
0x18002ae5a  mov     edx, edi
0x18002ae5c  mov     rcx, rax
0x18002ae5f  call    cs:__imp__o_wcscpy_s
0x18002ae65  mov     edx, r12d
0x18002ae68  mov     rax, [rbp+47h+arg_18]
0x18002ae6c  mov     r8, [rax+r13*8]
0x18002ae70  mov     rcx, qword ptr [rbp+47h+pvarg+8]
0x18002ae74  call    cs:__imp__o_wcscat_s
0x18002ae7a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ae81  cmp     rcx, rsi
0x18002ae84  jz      short loc_18002AE9F
0x18002ae86  mov     edx, 104h
0x18002ae8b  mov     r9, qword ptr [rbp+47h+pvarg+8]
0x18002ae8f  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18002ae96  mov     rcx, [rcx+10h]
0x18002ae9a  call    WPP_SF_S
0x18002ae9f  mov     rcx, [rbp+47h+ppv]
0x18002aea3  movups  xmm0, xmmword ptr [rbp+47h+pvarg]
0x18002aea7  movaps  [rbp+47h+var_80], xmm0
0x18002aeab  movsd   xmm1, qword ptr [rbp+47h+pvarg+10h]
0x18002aeb0  movsd   [rbp+47h+var_70], xmm1
0x18002aeb5  mov     rax, [rcx]
0x18002aeb8  lea     r8, [rbp+47h+var_80]
0x18002aebc  mov     rdx, rbx
0x18002aebf  mov     rax, [rax+38h]
0x18002aec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aec8  mov     edi, eax
0x18002aeca  test    eax, eax
0x18002aecc  jnz     short loc_18002AEE1
0x18002aece  mov     rcx, r14; hMem
0x18002aed1  call    cs:__imp_LocalFree
0x18002aed7  mov     eax, [rbp+47h+arg_20]
0x18002aeda  inc     eax
0x18002aedc  jmp     loc_18002AD93
0x18002aee1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aee8  cmp     rcx, rsi
0x18002aeeb  jz      loc_18002B004
0x18002aef1  mov     edx, 105h
0x18002aef6  mov     r9d, edi
0x18002aef9  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18002af00  mov     rcx, [rcx+10h]
0x18002af04  call    WPP_SF_d
0x18002af09  mov     rcx, cs:WPP_GLOBAL_Control
0x18002af10  cmp     rcx, rsi
0x18002af13  jz      loc_18002B004
0x18002af19  mov     eax, edi
0x18002af1b  and     eax, 1FFF0000h
0x18002af20  cmp     eax, 70000h
0x18002af25  movzx   r9d, di
0x18002af29  jz      short loc_18002AF2E
0x18002af2b  mov     r9d, edi
0x18002af2e  mov     edx, 106h
0x18002af33  jmp     loc_18002AD75
0x18002af38  mov     edi, 80004005h
0x18002af3d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002af44  cmp     rcx, rsi
0x18002af47  jz      loc_18002B004
0x18002af4d  mov     edx, 102h
0x18002af52  mov     r9, r12
0x18002af55  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18002af5c  mov     rcx, [rcx+10h]
0x18002af60  call    WPP_SF_S
0x18002af65  jmp     loc_18002B004
0x18002af6a  mov     edi, 80004005h
0x18002af6f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002af76  cmp     rcx, rsi
0x18002af79  jz      short loc_18002AF93
0x18002af7b  mov     edx, 103h
0x18002af80  mov     r9, r12
0x18002af83  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18002af8a  mov     rcx, [rcx+10h]
0x18002af8e  call    WPP_SF_S
0x18002af93  xor     r14d, r14d
0x18002af96  jmp     short loc_18002B004
0x18002af98  lea     rcx, [rbp+47h+pvarg]; pvarg
0x18002af9c  call    cs:__imp_VariantClear
0x18002afa2  mov     rdi, [rbp+47h+ppv]
0x18002afa6  lea     rcx, [rbp+47h+pvarg]; pvarg
0x18002afaa  call    cs:__imp_VariantClear
0x18002afb0  mov     eax, 9
0x18002afb5  mov     word ptr [rbp+47h+pvarg], ax
0x18002afb9  mov     qword ptr [rbp+47h+pvarg+8], rdi
0x18002afbd  test    rdi, rdi
0x18002afc0  jz      short loc_18002AFD2
0x18002afc2  mov     rax, [rdi]
0x18002afc5  mov     rcx, rdi
0x18002afc8  mov     rax, [rax+8]
0x18002afcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002afd1  nop
0x18002afd2  movups  xmm0, xmmword ptr [rbp+47h+pvarg]
0x18002afd6  movaps  [rbp+47h+var_80], xmm0
0x18002afda  movsd   xmm1, qword ptr [rbp+47h+pvarg+10h]
0x18002afdf  movsd   [rbp+47h+var_70], xmm1
0x18002afe4  mov     rcx, [rbp+47h+arg_0]
0x18002afe8  mov     rax, [rcx]
0x18002afeb  lea     rdx, [rbp+47h+var_80]
0x18002afef  mov     rax, [rax+270h]
0x18002aff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002affb  mov     edi, eax
0x18002affd  jmp     short loc_18002AF93
0x18002afff  mov     edi, 8007000Eh
0x18002b004  mov     rcx, r14; hMem
0x18002b007  call    cs:__imp_LocalFree
0x18002b00d  nop
0x18002b00e  mov     rcx, [rbp+47h+ppv]
0x18002b012  test    rcx, rcx
0x18002b015  jz      short loc_18002B024
0x18002b017  mov     rax, [rcx]
0x18002b01a  mov     rax, [rax+10h]
0x18002b01e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b023  nop
0x18002b024  lea     rcx, [rbp+47h+pvarg]; pvarg
0x18002b028  call    cs:__imp_VariantClear
0x18002b02e  nop
0x18002b02f  mov     rcx, rbx; bstrString
0x18002b032  call    cs:__imp_SysFreeString
0x18002b038  mov     eax, edi
0x18002b03a  add     rsp, 0B0h
0x18002b041  pop     r14
0x18002b043  pop     r13
0x18002b045  pop     r12
0x18002b047  pop     rdi
0x18002b048  pop     rsi
0x18002b049  pop     rbx
0x18002b04a  pop     rbp
0x18002b04b  retn
```
