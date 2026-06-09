# Resolution_SetupExtension(IResolution *)

- ea: `0x14004f5cc`
- end: `0x14004fcbe`
- name: `?Resolution_SetupExtension@@YAJPEAVIResolution@@@Z`
- size: `1778`
- prototype: `__int64 __fastcall(struct IResolution *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x140048d70`

## callees

- `0x140001d54`
- `0x140018678`
- `0x140020420`
- `0x1400210f0`
- `0x14004270c`
- `0x140044700`
- `0x14004f474`
- `0x14004f5cc`
- `0x140063010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14004fa96`
- `KERNEL32!HeapFree` at `0x14004faff`
- `KERNEL32!HeapFree` at `0x14004fc9e`
- `KERNEL32!HeapFree` at `0x14004fa96`
- `KERNEL32!HeapFree` at `0x14004faff`
- `KERNEL32!HeapFree` at `0x14004fc9e`
- `KERNEL32!GetProcessHeap` at `0x14004fa82`
- `KERNEL32!GetProcessHeap` at `0x14004faeb`
- `KERNEL32!GetProcessHeap` at `0x14004fc8a`
- `KERNEL32!GetProcessHeap` at `0x14004fa82`
- `KERNEL32!GetProcessHeap` at `0x14004faeb`
- `KERNEL32!GetProcessHeap` at `0x14004fc8a`
- `OLEAUT32!__imp_SysAllocString` at `0x14004fa6e`
- `OLEAUT32!__imp_SysAllocString` at `0x14004fad6`
- `OLEAUT32!__imp_SysAllocString` at `0x14004fb12`
- `OLEAUT32!__imp_SysAllocString` at `0x14004fa6e`
- `OLEAUT32!__imp_SysAllocString` at `0x14004fad6`
- `OLEAUT32!__imp_SysAllocString` at `0x14004fb12`
- `OLEAUT32!__imp_SysFreeString` at `0x14004f97f`
- `OLEAUT32!__imp_SysFreeString` at `0x14004fc06`
- `OLEAUT32!__imp_SysFreeString` at `0x14004fc23`
- `OLEAUT32!__imp_SysFreeString` at `0x14004fc40`
- `OLEAUT32!__imp_SysFreeString` at `0x14004fc5d`
- `OLEAUT32!__imp_SysFreeString` at `0x14004fc79`
- `OLEAUT32!__imp_SysFreeString` at `0x14004f97f`
- `OLEAUT32!__imp_SysFreeString` at `0x14004fc06`
- `OLEAUT32!__imp_SysFreeString` at `0x14004fc23`
- `OLEAUT32!__imp_SysFreeString` at `0x14004fc40`
- `OLEAUT32!__imp_SysFreeString` at `0x14004fc5d`
- `OLEAUT32!__imp_SysFreeString` at `0x14004fc79`

## string_xrefs

- `0x14004f784`: `./ExtensionPoint/Link`
- `0x14004f7f5`: `./ExtensionPoint/LinkText`
- `0x14004f8fd`: `./ExtensionPoint/RTFDescription`
- `0x14004f8a5`: `./ExtensionPoint/LinkFlushWithText`
- `0x14004f6bd`: `Resolution_SetupExtension`
- `0x14004f863`: `Resolution_SetupExtension`
- `0x14004fa45`: `Resolution_SetupExtension`
- `0x14004fb7f`: `Resolution_SetupExtension`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Resolution_SetupExtension(struct IResolution *a1)
{
  __int64 v1; // rax
  struct IXMLDOMDocument2 *v2; // rsi
  OLECHAR *v3; // r15
  unsigned __int16 *v4; // r13
  __int64 (__fastcall *v5)(struct IResolution *, struct ResolutionExtension **); // rax
  int v7; // eax
  int v8; // ebx
  int v9; // r9d
  char *v10; // rax
  int v11; // eax
  int v12; // r9d
  struct IXMLDOMDocument2 *v13; // rax
  struct IXMLDOMDocument2 *v14; // r14
  int v15; // eax
  int v16; // r9d
  struct IXMLDOMNode *v17; // r8
  int v18; // eax
  int v19; // r9d
  HANDLE ProcessHeap; // rax
  HANDLE v21; // rax
  HANDLE v22; // rax
  BSTR bstrString; // [rsp+30h] [rbp-48h] BYREF
  OLECHAR *psz; // [rsp+38h] [rbp-40h] BYREF
  struct IXMLDOMNode *v26; // [rsp+40h] [rbp-38h] BYREF
  __int64 v27; // [rsp+48h] [rbp-30h] BYREF
  BSTR v28; // [rsp+50h] [rbp-28h] BYREF
  BSTR v29; // [rsp+58h] [rbp-20h] BYREF
  BSTR v30; // [rsp+60h] [rbp-18h] BYREF
  unsigned __int16 *v31; // [rsp+68h] [rbp-10h] BYREF
  int v32; // [rsp+C0h] [rbp+48h] BYREF
  __int64 v33; // [rsp+C8h] [rbp+50h] BYREF
  struct IXMLDOMDocument2 *v34; // [rsp+D0h] [rbp+58h] BYREF
  struct ResolutionExtension *v35; // [rsp+D8h] [rbp+60h] BYREF

  v1 = *(_QWORD *)a1;
  v2 = 0;
  v32 = 0;
  v3 = 0;
  v35 = 0;
  v4 = 0;
  v34 = 0;
  v5 = *(__int64 (__fastcall **)(struct IResolution *, struct ResolutionExtension **))(v1 + 32);
  v33 = 0;
  v26 = 0;
  psz = 0;
  v29 = 0;
  v31 = 0;
  v30 = 0;
  v28 = 0;
  bstrString = 0;
  v27 = 0;
  v7 = v5(a1, &v35);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = 97;
    goto LABEL_76;
  }
  if ( v35 )
  {
    v35 = 0;
    goto LABEL_77;
  }
  v10 = (char *)operator new(0x20u);
  v35 = (struct ResolutionExtension *)v10;
  if ( !v10 )
  {
    v35 = 0;
    v9 = 105;
    goto LABEL_75;
  }
  *(_QWORD *)v10 = 0;
  *((_DWORD *)v10 + 2) = 0;
  *(_QWORD *)(v10 + 12) = 1;
  *((_QWORD *)v10 + 3) = 0;
  v35 = (struct ResolutionExtension *)v10;
  v7 = (*(__int64 (__fastcall **)(struct IResolution *, BSTR *))(*(_QWORD *)a1 + 40LL))(a1, &bstrString);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = 108;
    goto LABEL_76;
  }
  v11 = DwzXmlCreate(bstrString, &v34);
  v8 = v11;
  if ( v11 < 0 )
  {
    v12 = 111;
LABEL_10:
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Resolution_SetupExtension", v12, v11);
    v2 = v34;
    goto LABEL_77;
  }
  v11 = (*(__int64 (__fastcall **)(struct IResolution *, int *))(*(_QWORD *)a1 + 88LL))(a1, &v32);
  v8 = v11;
  if ( v11 < 0 )
  {
    v12 = 117;
    goto LABEL_10;
  }
  v2 = v34;
  if ( !v32 )
  {
    v7 = Resolution_PhysicalUserCheck(v35, v34);
    v8 = v7;
    if ( v7 < 0 )
    {
      v9 = 121;
      goto LABEL_76;
    }
  }
  v13 = (struct IXMLDOMDocument2 *)operator new(0x28u);
  v34 = v13;
  v14 = v13;
  if ( !v13 )
  {
    v9 = 130;
LABEL_75:
    v7 = -2147024882;
    v8 = -2147024882;
    goto LABEL_76;
  }
  v13->lpVtbl = 0;
  v13[1].lpVtbl = 0;
  v13[2].lpVtbl = 0;
  v13[3].lpVtbl = 0;
  *((_QWORD *)v35 + 3) = v13;
  if ( v33 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    v33 = 0;
  }
  v7 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, const wchar_t *, __int64 *))v2->lpVtbl->selectSingleNode)(
         v2,
         L"./ExtensionPoint/Link",
         &v33);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = 139;
    goto LABEL_76;
  }
  if ( !v7 )
  {
    v7 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v33 + 208LL))(v33, &v29);
    v8 = v7;
    if ( v7 < 0 )
    {
      v9 = 142;
      goto LABEL_76;
    }
  }
  if ( v33 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    v33 = 0;
  }
  v7 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, const wchar_t *, __int64 *))v2->lpVtbl->selectSingleNode)(
         v2,
         L"./ExtensionPoint/LinkText",
         &v33);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = 150;
    goto LABEL_76;
  }
  if ( !v7 )
  {
    v7 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v33 + 208LL))(v33, &v30);
    v8 = v7;
    if ( v7 < 0 )
    {
      v9 = 153;
      goto LABEL_76;
    }
    v15 = DwzTryLoadResourceString(v30, &v31);
    v8 = v15;
    if ( v15 < 0 )
    {
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Resolution_SetupExtension", 156, v15);
      v4 = v31;
      goto LABEL_77;
    }
    v4 = v31;
  }
  if ( v33 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    v33 = 0;
  }
  v8 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, const wchar_t *, __int64 *))v2->lpVtbl->selectSingleNode)(
         v2,
         L"./ExtensionPoint/LinkFlushWithText",
         &v33);
  if ( v8 < 0 )
  {
    v16 = 164;
LABEL_38:
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Resolution_SetupExtension", v16, v8);
    goto LABEL_77;
  }
  LODWORD(v14[4].lpVtbl) = v8 == 0;
  if ( v33 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    v33 = 0;
  }
  v7 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, const wchar_t *, __int64 *))v2->lpVtbl->selectSingleNode)(
         v2,
         L"./ExtensionPoint/RTFDescription",
         &v33);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = 172;
    goto LABEL_76;
  }
  if ( !v7 )
  {
    v7 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v33 + 208LL))(v33, &v28);
    v8 = v7;
    if ( v7 < 0 )
    {
      v9 = 175;
      goto LABEL_76;
    }
  }
  v7 = (*(__int64 (__fastcall **)(struct IResolution *, __int64 *))(*(_QWORD *)a1 + 136LL))(a1, &v27);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = 179;
    goto LABEL_76;
  }
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  ((void (__fastcall *)(struct IXMLDOMDocument2 *))v2->lpVtbl->Release)(v2);
  v2 = 0;
  v34 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v27 + 96LL))(v27, &bstrString);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = 185;
    goto LABEL_76;
  }
  v11 = DwzXmlCreate(bstrString, &v34);
  v8 = v11;
  if ( v11 < 0 )
  {
    v12 = 188;
    goto LABEL_10;
  }
  v2 = v34;
  v7 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, struct IXMLDOMNode **))v34->lpVtbl->get_documentElement)(
         v34,
         &v26);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = 191;
    goto LABEL_76;
  }
  if ( v7 == 1 || (v17 = v26) == 0 )
  {
    v8 = -2147467259;
    v16 = 195;
    goto LABEL_38;
  }
  if ( v29 )
  {
    v18 = DwzSubstituteXmlParameters(&psz, v29, v26);
    v8 = v18;
    if ( v18 < 0 )
    {
      v19 = 204;
LABEL_61:
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Resolution_SetupExtension", v19, v18);
      v3 = psz;
      goto LABEL_77;
    }
    v3 = psz;
    v14->lpVtbl = (struct IXMLDOMDocument2Vtbl *)SysAllocString(psz);
    if ( v3 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v3);
      v3 = 0;
      psz = 0;
    }
    v17 = v26;
  }
  if ( v4 )
  {
    v18 = DwzSubstituteXmlParameters(&psz, v4, v17);
    v8 = v18;
    if ( v18 < 0 )
    {
      v19 = 212;
      goto LABEL_61;
    }
    v3 = psz;
    v14[1].lpVtbl = (struct IXMLDOMDocument2Vtbl *)SysAllocString(psz);
    if ( v3 )
    {
      v21 = GetProcessHeap();
      HeapFree(v21, 0, v3);
      v3 = 0;
    }
  }
  v14[2].lpVtbl = (struct IXMLDOMDocument2Vtbl *)SysAllocString(v28);
  LinkAndRTFExtension::SetParamNode((LinkAndRTFExtension *)v14, v26);
  v7 = (*(__int64 (__fastcall **)(struct IResolution *, struct ResolutionExtension *))(*(_QWORD *)a1 + 24LL))(a1, v35);
  v8 = v7;
  if ( v7 >= 0 )
    goto LABEL_77;
  v9 = 223;
LABEL_76:
  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Resolution_SetupExtension", v9, v7);
LABEL_77:
  if ( v27 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    v27 = 0;
  }
  if ( v2 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v2->lpVtbl->Release)(v2);
  if ( v33 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    v33 = 0;
  }
  if ( v26 )
  {
    ((void (__fastcall *)(struct IXMLDOMNode *))v26->lpVtbl->Release)(v26);
    v26 = 0;
  }
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v28 )
  {
    SysFreeString(v28);
    v28 = 0;
  }
  if ( v29 )
  {
    SysFreeString(v29);
    v29 = 0;
  }
  if ( v30 )
  {
    SysFreeString(v30);
    v30 = 0;
  }
  if ( v4 )
    SysFreeString(v4);
  if ( v3 )
  {
    v22 = GetProcessHeap();
    HeapFree(v22, 0, v3);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14004f5cc  push    rbp
0x14004f5ce  push    rbx
0x14004f5cf  push    rsi
0x14004f5d0  push    rdi
0x14004f5d1  push    r12
0x14004f5d3  push    r13
0x14004f5d5  push    r14
0x14004f5d7  push    r15
0x14004f5d9  mov     rbp, rsp
0x14004f5dc  sub     rsp, 78h
0x14004f5e0  mov     rax, [rcx]
0x14004f5e3  lea     rdx, [rbp+arg_18]
0x14004f5e7  xor     esi, esi
0x14004f5e9  mov     [rbp+arg_0], 0
0x14004f5f0  xor     r15d, r15d
0x14004f5f3  mov     [rbp+arg_18], 0
0x14004f5fb  xor     r13d, r13d
0x14004f5fe  mov     [rbp+arg_10], rsi
0x14004f602  mov     rax, [rax+20h]
0x14004f606  mov     r12, rcx
0x14004f609  mov     [rbp+arg_8], rsi
0x14004f60d  mov     [rbp+var_38], rsi
0x14004f611  mov     [rbp+psz], r15
0x14004f615  mov     [rbp+var_20], rsi
0x14004f619  mov     [rbp+var_10], r13
0x14004f61d  mov     [rbp+var_18], rsi
0x14004f621  mov     [rbp+var_28], rsi
0x14004f625  mov     [rbp+bstrString], rsi
0x14004f629  mov     [rbp+var_30], rsi
0x14004f62d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f632  mov     ebx, eax
0x14004f634  test    eax, eax
0x14004f636  jns     short loc_14004F644
0x14004f638  lea     r9d, [rsi+61h]
0x14004f63c  lea     ecx, [rsi+1]
0x14004f63f  jmp     loc_14004FB7B
0x14004f644  cmp     [rbp+arg_18], rsi
0x14004f648  jz      short loc_14004F653
0x14004f64a  mov     [rbp+arg_18], rsi
0x14004f64e  jmp     loc_14004FB92
0x14004f653  mov     ecx, 20h ; ' '; Size
0x14004f658  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14004f65d  mov     [rbp+arg_18], rax
0x14004f661  mov     edi, 1
0x14004f666  test    rax, rax
0x14004f669  jz      loc_14004FB68
0x14004f66f  mov     [rax], rsi
0x14004f672  lea     rdx, [rbp+bstrString]
0x14004f676  mov     [rax+8], esi
0x14004f679  mov     rcx, r12
0x14004f67c  mov     [rax+0Ch], rdi
0x14004f680  mov     [rax+18h], rsi
0x14004f684  mov     [rbp+arg_18], rax
0x14004f688  mov     rax, [r12]
0x14004f68c  mov     rax, [rax+28h]
0x14004f690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f695  mov     ebx, eax
0x14004f697  test    eax, eax
0x14004f699  jns     short loc_14004F6A4
0x14004f69b  lea     r9d, [rdi+6Bh]
0x14004f69f  jmp     loc_14004FB79
0x14004f6a4  mov     rcx, [rbp+bstrString]; psz
0x14004f6a8  lea     rdx, [rbp+arg_10]; struct IXMLDOMDocument2 **
0x14004f6ac  call    ?DwzXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; DwzXmlCreate(ushort const *,IXMLDOMDocument2 * *)
0x14004f6b1  mov     ebx, eax
0x14004f6b3  test    eax, eax
0x14004f6b5  jns     short loc_14004F6DF
0x14004f6b7  mov     r9d, 6Fh ; 'o'
0x14004f6bd  lea     r8, aResolutionSetu; "Resolution_SetupExtension"
0x14004f6c4  mov     [rsp+78h+var_58], eax
0x14004f6c8  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14004f6cf  mov     ecx, edi; Level
0x14004f6d1  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14004f6d6  mov     rsi, [rbp+arg_10]
0x14004f6da  jmp     loc_14004FB92
0x14004f6df  mov     rax, [r12]
0x14004f6e3  lea     rdx, [rbp+arg_0]
0x14004f6e7  mov     rcx, r12
0x14004f6ea  mov     rax, [rax+58h]
0x14004f6ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f6f3  mov     ebx, eax
0x14004f6f5  test    eax, eax
0x14004f6f7  jns     short loc_14004F701
0x14004f6f9  mov     r9d, 75h ; 'u'
0x14004f6ff  jmp     short loc_14004F6BD
0x14004f701  mov     rsi, [rbp+arg_10]
0x14004f705  cmp     [rbp+arg_0], r13d
0x14004f709  jnz     short loc_14004F728
0x14004f70b  mov     rcx, [rbp+arg_18]; struct ResolutionExtension *
0x14004f70f  mov     rdx, rsi; struct IXMLDOMDocument2 *
0x14004f712  call    ?Resolution_PhysicalUserCheck@@YAJPEAVResolutionExtension@@PEAUIXMLDOMDocument2@@@Z; Resolution_PhysicalUserCheck(ResolutionExtension *,IXMLDOMDocument2 *)
0x14004f717  mov     ebx, eax
0x14004f719  test    eax, eax
0x14004f71b  jns     short loc_14004F728
0x14004f71d  mov     r9d, 79h ; 'y'
0x14004f723  jmp     loc_14004FB79
0x14004f728  mov     ecx, 28h ; '('; Size
0x14004f72d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14004f732  xor     ebx, ebx
0x14004f734  mov     [rbp+arg_10], rax
0x14004f738  mov     r14, rax
0x14004f73b  test    rax, rax
0x14004f73e  jz      loc_14004FB60
0x14004f744  mov     [rax], rbx
0x14004f747  mov     [rax+8], rbx
0x14004f74b  mov     [rax+10h], rbx
0x14004f74f  mov     [rax+18h], rbx
0x14004f753  test    rax, rax
0x14004f756  jz      loc_14004FB60
0x14004f75c  mov     rax, [rbp+arg_18]
0x14004f760  mov     [rax+18h], r14
0x14004f764  mov     rcx, [rbp+arg_8]
0x14004f768  test    rcx, rcx
0x14004f76b  jz      short loc_14004F77D
0x14004f76d  mov     rax, [rcx]
0x14004f770  mov     rax, [rax+10h]
0x14004f774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f779  mov     [rbp+arg_8], rbx
0x14004f77d  mov     rax, [rsi]
0x14004f780  lea     r8, [rbp+arg_8]
0x14004f784  lea     rdx, aExtensionpoint_14; "./ExtensionPoint/Link"
0x14004f78b  mov     rcx, rsi
0x14004f78e  mov     rax, [rax+128h]
0x14004f795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f79a  mov     ebx, eax
0x14004f79c  test    eax, eax
0x14004f79e  jns     short loc_14004F7AB
0x14004f7a0  mov     r9d, 8Bh
0x14004f7a6  jmp     loc_14004FB79
0x14004f7ab  jnz     short loc_14004F7D5
0x14004f7ad  mov     rcx, [rbp+arg_8]
0x14004f7b1  lea     rdx, [rbp+var_20]
0x14004f7b5  mov     rax, [rcx]
0x14004f7b8  mov     rax, [rax+0D0h]
0x14004f7bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f7c4  mov     ebx, eax
0x14004f7c6  test    eax, eax
0x14004f7c8  jns     short loc_14004F7D5
0x14004f7ca  mov     r9d, 8Eh
0x14004f7d0  jmp     loc_14004FB79
0x14004f7d5  mov     rcx, [rbp+arg_8]
0x14004f7d9  test    rcx, rcx
0x14004f7dc  jz      short loc_14004F7EE
0x14004f7de  mov     rax, [rcx]
0x14004f7e1  mov     rax, [rax+10h]
0x14004f7e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f7ea  mov     [rbp+arg_8], r13
0x14004f7ee  mov     rax, [rsi]
0x14004f7f1  lea     r8, [rbp+arg_8]
0x14004f7f5  lea     rdx, aExtensionpoint_7; "./ExtensionPoint/LinkText"
0x14004f7fc  mov     rcx, rsi
0x14004f7ff  mov     rax, [rax+128h]
0x14004f806  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f80b  mov     ebx, eax
0x14004f80d  test    eax, eax
0x14004f80f  jns     short loc_14004F81C
0x14004f811  mov     r9d, 96h
0x14004f817  jmp     loc_14004FB79
0x14004f81c  jnz     short loc_14004F885
0x14004f81e  mov     rcx, [rbp+arg_8]
0x14004f822  lea     rdx, [rbp+var_18]
0x14004f826  mov     rax, [rcx]
0x14004f829  mov     rax, [rax+0D0h]
0x14004f830  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f835  mov     ebx, eax
0x14004f837  test    eax, eax
0x14004f839  jns     short loc_14004F846
0x14004f83b  mov     r9d, 99h
0x14004f841  jmp     loc_14004FB79
0x14004f846  mov     rcx, [rbp+var_18]; psz
0x14004f84a  lea     rdx, [rbp+var_10]; unsigned __int16 **
0x14004f84e  call    ?DwzTryLoadResourceString@@YAJPEBGPEAPEAG@Z; DwzTryLoadResourceString(ushort const *,ushort * *)
0x14004f853  mov     ebx, eax
0x14004f855  test    eax, eax
0x14004f857  jns     short loc_14004F881
0x14004f859  mov     r9d, 9Ch
0x14004f85f  mov     [rsp+78h+var_58], eax
0x14004f863  lea     r8, aResolutionSetu; "Resolution_SetupExtension"
0x14004f86a  mov     ecx, edi; Level
0x14004f86c  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14004f873  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14004f878  mov     r13, [rbp+var_10]
0x14004f87c  jmp     loc_14004FB92
0x14004f881  mov     r13, [rbp+var_10]
0x14004f885  mov     rcx, [rbp+arg_8]
0x14004f889  test    rcx, rcx
0x14004f88c  jz      short loc_14004F89E
0x14004f88e  mov     rax, [rcx]
0x14004f891  mov     rax, [rax+10h]
0x14004f895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f89a  mov     [rbp+arg_8], r15
0x14004f89e  mov     rax, [rsi]
0x14004f8a1  lea     r8, [rbp+arg_8]
0x14004f8a5  lea     rdx, aExtensionpoint_18; "./ExtensionPoint/LinkFlushWithText"
0x14004f8ac  mov     rcx, rsi
0x14004f8af  mov     rax, [rax+128h]
0x14004f8b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f8bb  mov     ebx, eax
0x14004f8bd  test    eax, eax
0x14004f8bf  jns     short loc_14004F8D2
0x14004f8c1  mov     r9d, 0A4h
0x14004f8c7  mov     [rsp+78h+var_58], ebx
0x14004f8cb  mov     ecx, edi
0x14004f8cd  jmp     loc_14004FB7F
0x14004f8d2  xor     eax, eax
0x14004f8d4  test    ebx, ebx
0x14004f8d6  setz    al
0x14004f8d9  mov     [r14+20h], eax
0x14004f8dd  mov     rcx, [rbp+arg_8]
0x14004f8e1  test    rcx, rcx
0x14004f8e4  jz      short loc_14004F8F6
0x14004f8e6  mov     rax, [rcx]
0x14004f8e9  mov     rax, [rax+10h]
0x14004f8ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f8f2  mov     [rbp+arg_8], r15
0x14004f8f6  mov     rax, [rsi]
0x14004f8f9  lea     r8, [rbp+arg_8]
0x14004f8fd  lea     rdx, aExtensionpoint_12; "./ExtensionPoint/RTFDescription"
0x14004f904  mov     rcx, rsi
0x14004f907  mov     rax, [rax+128h]
0x14004f90e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f913  mov     ebx, eax
0x14004f915  test    eax, eax
0x14004f917  jns     short loc_14004F924
0x14004f919  mov     r9d, 0ACh
0x14004f91f  jmp     loc_14004FB79
0x14004f924  jnz     short loc_14004F94E
0x14004f926  mov     rcx, [rbp+arg_8]
0x14004f92a  lea     rdx, [rbp+var_28]
0x14004f92e  mov     rax, [rcx]
0x14004f931  mov     rax, [rax+0D0h]
0x14004f938  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f93d  mov     ebx, eax
0x14004f93f  test    eax, eax
0x14004f941  jns     short loc_14004F94E
0x14004f943  mov     r9d, 0AFh
0x14004f949  jmp     loc_14004FB79
0x14004f94e  mov     rax, [r12]
0x14004f952  lea     rdx, [rbp+var_30]
0x14004f956  mov     rcx, r12
0x14004f959  mov     rax, [rax+88h]
0x14004f960  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f965  mov     ebx, eax
0x14004f967  test    eax, eax
0x14004f969  jns     short loc_14004F976
0x14004f96b  mov     r9d, 0B3h
0x14004f971  jmp     loc_14004FB79
0x14004f976  mov     rcx, [rbp+bstrString]; bstrString
0x14004f97a  test    rcx, rcx
0x14004f97d  jz      short loc_14004F98F
0x14004f97f  call    cs:__imp_SysFreeString
0x14004f986  nop     dword ptr [rax+rax+00h]
0x14004f98b  mov     [rbp+bstrString], r15
0x14004f98f  mov     rax, [rsi]
0x14004f992  mov     rcx, rsi
0x14004f995  mov     rax, [rax+10h]
0x14004f999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f99e  mov     rcx, [rbp+var_30]
0x14004f9a2  lea     rdx, [rbp+bstrString]
0x14004f9a6  xor     esi, esi
0x14004f9a8  mov     [rbp+arg_10], rsi
0x14004f9ac  mov     rax, [rcx]
0x14004f9af  mov     rax, [rax+60h]
0x14004f9b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f9b8  mov     ebx, eax
0x14004f9ba  test    eax, eax
0x14004f9bc  jns     short loc_14004F9C9
0x14004f9be  mov     r9d, 0B9h
0x14004f9c4  jmp     loc_14004FB79
0x14004f9c9  mov     rcx, [rbp+bstrString]; psz
0x14004f9cd  lea     rdx, [rbp+arg_10]; struct IXMLDOMDocument2 **
0x14004f9d1  call    ?DwzXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; DwzXmlCreate(ushort const *,IXMLDOMDocument2 * *)
0x14004f9d6  mov     ebx, eax
0x14004f9d8  test    eax, eax
0x14004f9da  jns     short loc_14004F9E7
0x14004f9dc  mov     r9d, 0BCh
0x14004f9e2  jmp     loc_14004F6BD
0x14004f9e7  mov     rsi, [rbp+arg_10]
0x14004f9eb  lea     rdx, [rbp+var_38]
0x14004f9ef  mov     rcx, rsi
0x14004f9f2  mov     rax, [rsi]
0x14004f9f5  mov     rax, [rax+168h]
0x14004f9fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004fa01  mov     ebx, eax
0x14004fa03  test    eax, eax
0x14004fa05  jns     short loc_14004FA12
0x14004fa07  mov     r9d, 0BFh
0x14004fa0d  jmp     loc_14004FB79
0x14004fa12  cmp     eax, edi
0x14004fa14  jz      loc_14004FB50
0x14004fa1a  mov     r8, [rbp+var_38]; struct IXMLDOMNode *
0x14004fa1e  test    r8, r8
0x14004fa21  jz      loc_14004FB50
0x14004fa27  mov     rdx, [rbp+var_20]; unsigned __int16 *
0x14004fa2b  test    rdx, rdx
0x14004fa2e  jz      short loc_14004FAAD
0x14004fa30  lea     rcx, [rbp+psz]; unsigned __int16 **
0x14004fa34  call    ?DwzSubstituteXmlParameters@@YAJPEAPEAGPEBGPEAUIXMLDOMNode@@@Z; DwzSubstituteXmlParameters(ushort * *,ushort const *,IXMLDOMNode *)
0x14004fa39  mov     ebx, eax
0x14004fa3b  test    eax, eax
  ... truncated ...
```
