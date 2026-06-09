# SetNsAndSchema(IXMLDOMDocument2 *,ushort const *,ushort const * *,ushort const * *)

- ea: `0x180006600`
- end: `0x180006a16`
- name: `?SetNsAndSchema@@YAJPEAUIXMLDOMDocument2@@PEBGPEAPEBG2@Z`
- size: `1046`
- prototype: `int(struct IXMLDOMDocument2 *, const unsigned __int16 *, const unsigned __int16 **, const unsigned __int16 **)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180005df0`
- `0x18001cbe4`

## callees

- `0x180003bd0`
- `0x180006600`
- `0x180006a20`
- `0x180017e80`
- `0x18001cbbc`
- `0x180027010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180006816`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180006816`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180006872`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180006872`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000685d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000685d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800068aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800069c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800068aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800069c8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800067a6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800067a6`
- `OLEAUT32!__imp_SysAllocString` at `0x18000666a`
- `OLEAUT32!__imp_SysAllocString` at `0x180006698`
- `OLEAUT32!__imp_SysAllocString` at `0x1800067eb`
- `OLEAUT32!__imp_SysAllocString` at `0x18000666a`
- `OLEAUT32!__imp_SysAllocString` at `0x180006698`
- `OLEAUT32!__imp_SysAllocString` at `0x1800067eb`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180006838`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180006838`
- `OLEAUT32!__imp_SysFreeString` at `0x18000665d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800067dd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800069f3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000665d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800067dd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800069f3`
- `OLEAUT32!__imp_VariantInit` at `0x180006633`
- `OLEAUT32!__imp_VariantInit` at `0x180006633`
- `OLEAUT32!__imp_VariantClear` at `0x180006686`
- `OLEAUT32!__imp_VariantClear` at `0x180006824`
- `OLEAUT32!__imp_VariantClear` at `0x18000695a`
- `OLEAUT32!__imp_VariantClear` at `0x180006968`
- `OLEAUT32!__imp_VariantClear` at `0x1800069e9`
- `OLEAUT32!__imp_VariantClear` at `0x180006686`
- `OLEAUT32!__imp_VariantClear` at `0x180006824`
- `OLEAUT32!__imp_VariantClear` at `0x18000695a`
- `OLEAUT32!__imp_VariantClear` at `0x180006968`
- `OLEAUT32!__imp_VariantClear` at `0x1800069e9`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000678c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800067c1`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000678c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800067c1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006723`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006723`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SetNsAndSchema(
        struct IXMLDOMDocument2 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 **a3,
        const unsigned __int16 **a4)
{
  int v7; // ecx
  OLECHAR *v8; // rbx
  BSTR v9; // rax
  int v10; // ecx
  WCHAR *v11; // r14
  unsigned int v12; // edi
  int i; // esi
  const WCHAR *v14; // r12
  DWORD v15; // eax
  __int64 v16; // r15
  WCHAR *v17; // rax
  const OLECHAR *v18; // r12
  int v19; // ecx
  UINT v20; // r12d
  BSTR v21; // rax
  LPVOID v22; // rdi
  LPVOID ppv; // [rsp+30h] [rbp-39h] BYREF
  OLECHAR *v25; // [rsp+38h] [rbp-31h]
  VARIANTARG pvarg; // [rsp+40h] [rbp-29h] BYREF
  LPCWSTR lpSrc[3]; // [rsp+58h] [rbp-11h]
  VARIANTARG v28[3]; // [rsp+70h] [rbp+7h] BYREF

  VariantInit(&pvarg);
  ppv = 0;
  lpSrc[0] = L"%windir%\\schemas\\EAPHost\\";
  lpSrc[1] = L"%windir%\\schemas\\EAPMethods\\";
  lpSrc[2] = 0;
  SysFreeString(0);
  v8 = SysAllocString(L"SelectionNamespaces");
  v25 = v8;
  if ( !v8 )
    ATL::AtlThrowImpl(v7);
  VariantClear(&pvarg);
  pvarg.vt = 8;
  v9 = SysAllocString(a2);
  pvarg.llVal = (LONGLONG)v9;
  if ( !v9 && a2 )
  {
    pvarg.vt = 10;
    pvarg.lVal = -2147024882;
    ATL::AtlThrowImpl(v10);
  }
  v11 = 0;
  if ( v9 )
  {
    v28[0] = pvarg;
    v12 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, OLECHAR *, VARIANTARG *))a1->lpVtbl->setProperty)(
            a1,
            v8,
            v28);
    if ( !v12 )
    {
      v12 = CoCreateInstance(&CLSID_XMLSchemaCache60, 0, 1u, &IID_IXMLDOMSchemaCollection2, &ppv);
      if ( v12 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, WPP_47d2ae5abdbe322473422603828ba620_Traceguids, v12);
      }
      else
      {
        for ( i = 0; a3[i]; ++i )
        {
          v14 = lpSrc[i];
          v15 = ExpandEnvironmentStringsW(v14, 0, 0);
          v16 = v15;
          if ( !v15 )
          {
            v12 = -2147467259;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_47d2ae5abdbe322473422603828ba620_Traceguids, v14);
            v11 = 0;
            goto LABEL_36;
          }
          v17 = (WCHAR *)LocalAlloc(0x40u, 2LL * v15);
          v11 = v17;
          if ( !v17 )
            goto LABEL_35;
          if ( ExpandEnvironmentStringsW(v14, v17, v16) > (unsigned int)v16 )
          {
            v12 = -2147467259;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, WPP_47d2ae5abdbe322473422603828ba620_Traceguids, v14);
            goto LABEL_36;
          }
          v18 = a3[i];
          if ( v18 != v8 )
          {
            SysFreeString(v8);
            if ( v18 )
            {
              v8 = SysAllocString(v18);
              v25 = v8;
              if ( !v8 )
                ATL::AtlThrowImpl(v19);
            }
            else
            {
              v8 = 0;
              v25 = 0;
            }
          }
          v20 = wcsnlen(a4[i], 0x400u) + v16;
          VariantClear(&pvarg);
          pvarg.vt = 8;
          v21 = SysAllocStringLen(0, v20);
          pvarg.llVal = (LONGLONG)v21;
          if ( !v8 || !v21 )
            goto LABEL_35;
          _o_wcscpy_s(v21, v16, v11);
          _o_wcscat_s(pvarg.llVal, v20, a4[i]);
          v28[0] = pvarg;
          v12 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, VARIANTARG *))(*(_QWORD *)ppv + 56LL))(ppv, v8, v28);
          if ( v12 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_47d2ae5abdbe322473422603828ba620_Traceguids);
            goto LABEL_36;
          }
          LocalFree(v11);
        }
        VariantClear(&pvarg);
        v22 = ppv;
        VariantClear(&pvarg);
        pvarg.vt = 9;
        pvarg.llVal = (LONGLONG)v22;
        if ( v22 )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v22 + 8LL))(v22);
        v28[0] = pvarg;
        v12 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, VARIANTARG *))a1->lpVtbl->putref_schemas)(a1, v28);
        v11 = 0;
      }
    }
  }
  else
  {
LABEL_35:
    v12 = -2147024882;
  }
LABEL_36:
  LocalFree(v11);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  VariantClear(&pvarg);
  SysFreeString(v8);
  return v12;
}

```

## disassembly

```asm
0x180006600  mov     [rsp-8+arg_8], rbx
0x180006605  mov     [rsp-8+arg_18], r9
0x18000660a  mov     [rsp-8+arg_0], rcx
0x18000660f  push    rbp
0x180006610  push    rsi
0x180006611  push    rdi
0x180006612  push    r12
0x180006614  push    r13
0x180006616  push    r14
0x180006618  push    r15
0x18000661a  lea     rbp, [rsp-27h]
0x18000661f  sub     rsp, 90h
0x180006626  mov     r13, r8
0x180006629  mov     rdi, rdx
0x18000662c  mov     r15, rcx
0x18000662f  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180006633  call    cs:__imp_VariantInit
0x180006639  nop
0x18000663a  xor     r12d, r12d
0x18000663d  mov     [rbp+57h+var_90], r12
0x180006641  lea     rax, aWindirSchemasE_0; "%windir%\\schemas\\EAPHost\\"
0x180006648  mov     [rbp+57h+lpSrc], rax
0x18000664c  lea     rax, aWindirSchemasE; "%windir%\\schemas\\EAPMethods\\"
0x180006653  mov     [rbp+57h+var_60], rax
0x180006657  mov     [rbp+57h+var_58], r12
0x18000665b  xor     ecx, ecx; bstrString
0x18000665d  call    cs:__imp_SysFreeString
0x180006663  lea     rcx, aSelectionnames; "SelectionNamespaces"
0x18000666a  call    cs:__imp_SysAllocString
0x180006670  mov     rbx, rax
0x180006673  mov     [rbp+57h+var_88], rax
0x180006677  test    rax, rax
0x18000667a  jnz     short loc_180006682
0x18000667c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180006682  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180006686  call    cs:__imp_VariantClear
0x18000668c  mov     eax, 8
0x180006691  mov     word ptr [rbp+57h+pvarg], ax
0x180006695  mov     rcx, rdi; psz
0x180006698  call    cs:__imp_SysAllocString
0x18000669e  mov     qword ptr [rbp+57h+pvarg+8], rax
0x1800066a2  test    rax, rax
0x1800066a5  jnz     short loc_1800066C3
0x1800066a7  test    rdi, rdi
0x1800066aa  jz      short loc_1800066C3
0x1800066ac  mov     eax, 0Ah
0x1800066b1  mov     word ptr [rbp+57h+pvarg], ax
0x1800066b5  mov     edi, 8007000Eh
0x1800066ba  mov     dword ptr [rbp+57h+pvarg+8], edi
0x1800066bd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800066c3  mov     r14, r12
0x1800066c6  test    rax, rax
0x1800066c9  jz      loc_1800069C0
0x1800066cf  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x1800066d3  movaps  [rbp+57h+var_50], xmm0
0x1800066d7  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x1800066dc  movsd   [rbp+57h+var_40], xmm1
0x1800066e1  mov     rax, [r15]
0x1800066e4  lea     r8, [rbp+57h+var_50]
0x1800066e8  mov     rdx, rbx
0x1800066eb  mov     rcx, r15
0x1800066ee  mov     rax, [rax+280h]
0x1800066f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066fa  mov     edi, eax
0x1800066fc  test    eax, eax
0x1800066fe  jnz     loc_1800069C5
0x180006704  lea     rax, [rbp+57h+var_90]
0x180006708  mov     [rsp+0C0h+ppv], rax; ppv
0x18000670d  lea     r9, IID_IXMLDOMSchemaCollection2; riid
0x180006714  xor     edx, edx; pUnkOuter
0x180006716  mov     r8d, 1; dwClsContext
0x18000671c  lea     rcx, CLSID_XMLSchemaCache60; rclsid
0x180006723  call    cs:__imp_CoCreateInstance
0x180006729  mov     edi, eax
0x18000672b  test    eax, eax
0x18000672d  jz      short loc_180006763
0x18000672f  lea     rax, WPP_GLOBAL_Control
0x180006736  mov     rcx, cs:WPP_GLOBAL_Control
0x18000673d  cmp     rcx, rax
0x180006740  jz      loc_1800069C5
0x180006746  mov     edx, 3Fh ; '?'
0x18000674b  mov     r9d, edi
0x18000674e  lea     r8, WPP_47d2ae5abdbe322473422603828ba620_Traceguids
0x180006755  mov     rcx, [rcx+10h]
0x180006759  call    WPP_SF_d
0x18000675e  jmp     loc_1800069C5
0x180006763  mov     esi, r12d
0x180006766  nop     word ptr [rax+rax+00000000h]
0x180006770  movsxd  rdi, esi
0x180006773  cmp     qword ptr [r13+rdi*8+0], 0
0x180006779  jz      loc_180006956
0x18000677f  mov     r12, [rbp+rdi*8+57h+lpSrc]
0x180006784  xor     r8d, r8d; nSize
0x180006787  xor     edx, edx; lpDst
0x180006789  mov     rcx, r12; lpSrc
0x18000678c  call    cs:__imp_ExpandEnvironmentStringsW
0x180006792  mov     r15d, eax
0x180006795  test    eax, eax
0x180006797  jz      loc_180006921
0x18000679d  lea     rdx, [r15+r15]; uBytes
0x1800067a1  mov     ecx, 40h ; '@'; uFlags
0x1800067a6  call    cs:__imp_LocalAlloc
0x1800067ac  mov     r14, rax
0x1800067af  test    rax, rax
0x1800067b2  jz      loc_1800069C0
0x1800067b8  mov     r8d, r15d; nSize
0x1800067bb  mov     rdx, rax; lpDst
0x1800067be  mov     rcx, r12; lpSrc
0x1800067c1  call    cs:__imp_ExpandEnvironmentStringsW
0x1800067c7  cmp     eax, r15d
0x1800067ca  ja      loc_1800068E8
0x1800067d0  mov     r12, [r13+rdi*8+0]
0x1800067d5  cmp     r12, rbx
0x1800067d8  jz      short loc_180006809
0x1800067da  mov     rcx, rbx; bstrString
0x1800067dd  call    cs:__imp_SysFreeString
0x1800067e3  test    r12, r12
0x1800067e6  jz      short loc_180006803
0x1800067e8  mov     rcx, r12; psz
0x1800067eb  call    cs:__imp_SysAllocString
0x1800067f1  mov     rbx, rax
0x1800067f4  mov     [rbp+57h+var_88], rax
0x1800067f8  test    rax, rax
0x1800067fb  jnz     short loc_180006809
0x1800067fd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180006803  xor     ebx, ebx
0x180006805  mov     [rbp+57h+var_88], rbx
0x180006809  mov     edx, 400h; MaxCount
0x18000680e  mov     rcx, [rbp+57h+arg_18]
0x180006812  mov     rcx, [rcx+rdi*8]; Source
0x180006816  call    cs:__imp_wcsnlen
0x18000681c  lea     r12d, [rax+r15]
0x180006820  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180006824  call    cs:__imp_VariantClear
0x18000682a  mov     eax, 8
0x18000682f  mov     word ptr [rbp+57h+pvarg], ax
0x180006833  mov     edx, r12d; ui
0x180006836  xor     ecx, ecx; strIn
0x180006838  call    cs:__imp_SysAllocStringLen
0x18000683e  mov     qword ptr [rbp+57h+pvarg+8], rax
0x180006842  test    rbx, rbx
0x180006845  jz      loc_1800069C0
0x18000684b  test    rax, rax
0x18000684e  jz      loc_1800069C0
0x180006854  mov     r8, r14
0x180006857  mov     rdx, r15
0x18000685a  mov     rcx, rax
0x18000685d  call    cs:__imp__o_wcscpy_s
0x180006863  mov     edx, r12d
0x180006866  mov     rax, [rbp+57h+arg_18]
0x18000686a  mov     r8, [rax+rdi*8]
0x18000686e  mov     rcx, qword ptr [rbp+57h+pvarg+8]
0x180006872  call    cs:__imp__o_wcscat_s
0x180006878  mov     rcx, [rbp+57h+var_90]
0x18000687c  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x180006880  movaps  [rbp+57h+var_50], xmm0
0x180006884  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x180006889  movsd   [rbp+57h+var_40], xmm1
0x18000688e  mov     rax, [rcx]
0x180006891  lea     r8, [rbp+57h+var_50]
0x180006895  mov     rdx, rbx
0x180006898  mov     rax, [rax+38h]
0x18000689c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068a1  mov     edi, eax
0x1800068a3  test    eax, eax
0x1800068a5  jnz     short loc_1800068B7
0x1800068a7  mov     rcx, r14; hMem
0x1800068aa  call    cs:__imp_LocalFree
0x1800068b0  inc     esi
0x1800068b2  jmp     loc_180006770
0x1800068b7  lea     rax, WPP_GLOBAL_Control
0x1800068be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800068c5  cmp     rcx, rax
0x1800068c8  jz      loc_1800069C5
0x1800068ce  mov     edx, 42h ; 'B'
0x1800068d3  lea     r8, WPP_47d2ae5abdbe322473422603828ba620_Traceguids
0x1800068da  mov     rcx, [rcx+10h]
0x1800068de  call    WPP_SF_
0x1800068e3  jmp     loc_1800069C5
0x1800068e8  mov     edi, 80004005h
0x1800068ed  lea     rax, WPP_GLOBAL_Control
0x1800068f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800068fb  cmp     rcx, rax
0x1800068fe  jz      loc_1800069C5
0x180006904  mov     edx, 40h ; '@'
0x180006909  mov     r9, r12
0x18000690c  lea     r8, WPP_47d2ae5abdbe322473422603828ba620_Traceguids
0x180006913  mov     rcx, [rcx+10h]
0x180006917  call    WPP_SF_S
0x18000691c  jmp     loc_1800069C5
0x180006921  mov     edi, 80004005h
0x180006926  lea     rax, WPP_GLOBAL_Control
0x18000692d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006934  cmp     rcx, rax
0x180006937  jz      short loc_180006951
0x180006939  mov     edx, 41h ; 'A'
0x18000693e  mov     r9, r12
0x180006941  lea     r8, WPP_47d2ae5abdbe322473422603828ba620_Traceguids
0x180006948  mov     rcx, [rcx+10h]
0x18000694c  call    WPP_SF_S
0x180006951  xor     r14d, r14d
0x180006954  jmp     short loc_1800069C5
0x180006956  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18000695a  call    cs:__imp_VariantClear
0x180006960  mov     rdi, [rbp+57h+var_90]
0x180006964  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180006968  call    cs:__imp_VariantClear
0x18000696e  mov     eax, 9
0x180006973  mov     word ptr [rbp+57h+pvarg], ax
0x180006977  mov     qword ptr [rbp+57h+pvarg+8], rdi
0x18000697b  test    rdi, rdi
0x18000697e  jz      short loc_180006990
0x180006980  mov     rax, [rdi]
0x180006983  mov     rcx, rdi
0x180006986  mov     rax, [rax+8]
0x18000698a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000698f  nop
0x180006990  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x180006994  movaps  [rbp+57h+var_50], xmm0
0x180006998  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x18000699d  movsd   [rbp+57h+var_40], xmm1
0x1800069a2  mov     rcx, [rbp+57h+arg_0]
0x1800069a6  mov     rax, [rcx]
0x1800069a9  lea     rdx, [rbp+57h+var_50]
0x1800069ad  mov     rax, [rax+270h]
0x1800069b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069b9  mov     edi, eax
0x1800069bb  xor     r14d, r14d
0x1800069be  jmp     short loc_1800069C5
0x1800069c0  mov     edi, 8007000Eh
0x1800069c5  mov     rcx, r14; hMem
0x1800069c8  call    cs:__imp_LocalFree
0x1800069ce  nop
0x1800069cf  mov     rcx, [rbp+57h+var_90]
0x1800069d3  test    rcx, rcx
0x1800069d6  jz      short loc_1800069E5
0x1800069d8  mov     rax, [rcx]
0x1800069db  mov     rax, [rax+10h]
0x1800069df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069e4  nop
0x1800069e5  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800069e9  call    cs:__imp_VariantClear
0x1800069ef  nop
0x1800069f0  mov     rcx, rbx; bstrString
0x1800069f3  call    cs:__imp_SysFreeString
0x1800069f9  mov     eax, edi
0x1800069fb  mov     rbx, [rsp+0C0h+arg_8]
0x180006a03  add     rsp, 90h
0x180006a0a  pop     r15
0x180006a0c  pop     r14
0x180006a0e  pop     r13
0x180006a10  pop     r12
0x180006a12  pop     rdi
0x180006a13  pop     rsi
0x180006a14  pop     rbp
0x180006a15  retn
```
