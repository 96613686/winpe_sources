# XcCreateXmlDoc(ushort const *,IXMLDOMSchemaCollection *,IXMLDOMDocument2 * *)

- ea: `0x18003b254`
- end: `0x18003b46c`
- name: `?XcCreateXmlDoc@@YAKPEBGPEAUIXMLDOMSchemaCollection@@PEAPEAUIXMLDOMDocument2@@@Z`
- size: `536`
- prototype: `unsigned int __fastcall(OLECHAR *psz, struct IXMLDOMSchemaCollection *, struct IXMLDOMDocument2 **)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800328f8`
- `0x18003b830`

## callees

- `0x18000c4b0`
- `0x18003a8b0`
- `0x18003a8f4`
- `0x18003b254`
- `0x180040010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003b2ba`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003b2ba`
- `OLEAUT32!__imp_SysFreeString` at `0x18003b43d`
- `OLEAUT32!__imp_SysFreeString` at `0x18003b43d`
- `OLEAUT32!__imp_VariantInit` at `0x18003b28d`
- `OLEAUT32!__imp_VariantInit` at `0x18003b297`
- `OLEAUT32!__imp_VariantInit` at `0x18003b28d`
- `OLEAUT32!__imp_VariantInit` at `0x18003b297`
- `OLEAUT32!__imp_VariantClear` at `0x18003b3b1`
- `OLEAUT32!__imp_VariantClear` at `0x18003b42a`
- `OLEAUT32!__imp_VariantClear` at `0x18003b434`
- `OLEAUT32!__imp_VariantClear` at `0x18003b3b1`
- `OLEAUT32!__imp_VariantClear` at `0x18003b42a`
- `OLEAUT32!__imp_VariantClear` at `0x18003b434`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall XcCreateXmlDoc(OLECHAR *psz, struct IXMLDOMSchemaCollection *a2, struct IXMLDOMDocument2 **a3)
{
  OLECHAR *v6; // rbx
  HRESULT v7; // eax
  unsigned int v8; // edi
  int v9; // eax
  int v10; // eax
  int v11; // eax
  struct IXMLDOMDocument2 *v12; // rcx
  BSTR v14; // [rsp+30h] [rbp-29h] BYREF
  VARIANTARG v15; // [rsp+38h] [rbp-21h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-9h] BYREF
  VARIANTARG v17; // [rsp+70h] [rbp+17h] BYREF
  LPVOID ppv; // [rsp+D8h] [rbp+7Fh] BYREF

  ppv = 0;
  v6 = 0;
  v14 = 0;
  VariantInit(&pvarg);
  VariantInit(&v15);
  v7 = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument2, &ppv);
  v8 = v7;
  if ( v7 >= 0 )
    goto LABEL_5;
  if ( (v7 & 0x1FFF0000) == 0x70000 )
    v8 = (unsigned __int16)v7;
  if ( !v8 )
  {
LABEL_5:
    v9 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 504LL))(ppv, 0);
    v8 = v9;
    if ( v9 < 0 )
    {
      if ( (v9 & 0x1FFF0000) == 0x70000 )
        v8 = (unsigned __int16)v9;
      if ( v8 )
        goto LABEL_26;
    }
    else
    {
      v8 = 0;
    }
    if ( psz )
    {
      AtlAssignNoThrow(&v14, (OLECHAR *)L"SelectionNamespaces");
      AtlAssignNoThrow((struct ATL::CComVariant *)&pvarg, psz);
      v8 = 8;
      v6 = v14;
      if ( !v14 || pvarg.vt != 8 || !pvarg.llVal )
        goto LABEL_26;
      v17 = pvarg;
      v10 = (*(__int64 (__fastcall **)(LPVOID, BSTR, VARIANTARG *))(*(_QWORD *)ppv + 640LL))(ppv, v14, &v17);
      v8 = v10;
      if ( v10 < 0 )
      {
        if ( (v10 & 0x1FFF0000) == 0x70000 )
          v8 = (unsigned __int16)v10;
        if ( v8 )
          goto LABEL_26;
      }
      else
      {
        v8 = 0;
      }
    }
    if ( !a2 )
    {
LABEL_25:
      v12 = (struct IXMLDOMDocument2 *)ppv;
      ppv = 0;
      *a3 = v12;
      goto LABEL_26;
    }
    VariantClear(&v15);
    v15.vt = 9;
    v15.llVal = (LONGLONG)a2;
    ((void (__fastcall *)(struct IXMLDOMSchemaCollection *))a2->lpVtbl->AddRef)(a2);
    v17 = v15;
    v11 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *))(*(_QWORD *)ppv + 624LL))(ppv, &v17);
    v8 = v11;
    if ( v11 >= 0 )
    {
      v8 = 0;
      goto LABEL_25;
    }
    if ( (v11 & 0x1FFF0000) == 0x70000 )
      v8 = (unsigned __int16)v11;
    if ( !v8 )
      goto LABEL_25;
  }
LABEL_26:
  VariantClear(&v15);
  VariantClear(&pvarg);
  SysFreeString(v6);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&ppv);
  return v8;
}

```

## disassembly

```asm
0x18003b254  mov     [rsp-8+arg_0], rbx
0x18003b259  mov     [rsp-8+arg_8], rsi
0x18003b25e  push    rbp
0x18003b25f  push    rdi
0x18003b260  push    r13
0x18003b262  push    r14
0x18003b264  push    r15
0x18003b266  lea     rbp, [rsp-37h]
0x18003b26b  sub     rsp, 90h
0x18003b272  mov     r15, r8
0x18003b275  mov     r14, rdx
0x18003b278  mov     rsi, rcx
0x18003b27b  mov     [rbp+57h+arg_18], 0
0x18003b283  xor     ebx, ebx
0x18003b285  mov     [rbp+57h+var_80], rbx
0x18003b289  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18003b28d  call    cs:__imp_VariantInit
0x18003b293  lea     rcx, [rbp+57h+var_78]; pvarg
0x18003b297  call    cs:__imp_VariantInit
0x18003b29d  lea     rax, [rbp+57h+arg_18]
0x18003b2a1  mov     [rsp+0B0h+ppv], rax; ppv
0x18003b2a6  lea     r9, IID_IXMLDOMDocument2; riid
0x18003b2ad  xor     edx, edx; pUnkOuter
0x18003b2af  lea     r8d, [rbx+1]; dwClsContext
0x18003b2b3  lea     rcx, CLSID_DOMDocument60; rclsid
0x18003b2ba  call    cs:__imp_CoCreateInstance
0x18003b2c0  mov     edi, eax
0x18003b2c2  mov     r13d, 1FFF0000h
0x18003b2c8  test    eax, eax
0x18003b2ca  jns     short loc_18003B2E1
0x18003b2cc  and     eax, r13d
0x18003b2cf  cmp     eax, 70000h
0x18003b2d4  jnz     short loc_18003B2D9
0x18003b2d6  movzx   edi, di
0x18003b2d9  test    edi, edi
0x18003b2db  jnz     loc_18003B426
0x18003b2e1  mov     rcx, [rbp+57h+arg_18]
0x18003b2e5  mov     rax, [rcx]
0x18003b2e8  xor     edx, edx
0x18003b2ea  mov     rax, [rax+1F8h]
0x18003b2f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b2f6  mov     edi, eax
0x18003b2f8  test    eax, eax
0x18003b2fa  js      short loc_18003B300
0x18003b2fc  xor     edi, edi
0x18003b2fe  jmp     short loc_18003B315
0x18003b300  and     eax, r13d
0x18003b303  cmp     eax, 70000h
0x18003b308  jnz     short loc_18003B30D
0x18003b30a  movzx   edi, di
0x18003b30d  test    edi, edi
0x18003b30f  jnz     loc_18003B426
0x18003b315  test    rsi, rsi
0x18003b318  jz      loc_18003B3A8
0x18003b31e  lea     rdx, aSelectionnames; "SelectionNamespaces"
0x18003b325  lea     rcx, [rbp+57h+var_80]; this
0x18003b329  call    ?AtlAssignNoThrow@@YAXAEAVCComBSTR@ATL@@PEBG@Z; AtlAssignNoThrow(ATL::CComBSTR &,ushort const *)
0x18003b32e  mov     rdx, rsi; psz
0x18003b331  lea     rcx, [rbp+57h+pvarg]; this
0x18003b335  call    ?AtlAssignNoThrow@@YAXAEAVCComVariant@ATL@@PEBG@Z; AtlAssignNoThrow(ATL::CComVariant &,ushort const *)
0x18003b33a  mov     edi, 8
0x18003b33f  mov     rbx, [rbp+57h+var_80]
0x18003b343  test    rbx, rbx
0x18003b346  jz      loc_18003B426
0x18003b34c  cmp     word ptr [rbp+57h+pvarg], di
0x18003b350  jnz     loc_18003B426
0x18003b356  cmp     qword ptr [rbp+57h+pvarg+8], 0
0x18003b35b  jz      loc_18003B426
0x18003b361  mov     rcx, [rbp+57h+arg_18]
0x18003b365  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x18003b369  movaps  [rbp+57h+var_40], xmm0
0x18003b36d  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x18003b372  movsd   [rbp+57h+var_30], xmm1
0x18003b377  mov     rax, [rcx]
0x18003b37a  lea     r8, [rbp+57h+var_40]
0x18003b37e  mov     rdx, rbx
0x18003b381  mov     rax, [rax+280h]
0x18003b388  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b38d  mov     edi, eax
0x18003b38f  test    eax, eax
0x18003b391  js      short loc_18003B397
0x18003b393  xor     edi, edi
0x18003b395  jmp     short loc_18003B3A8
0x18003b397  and     eax, r13d
0x18003b39a  cmp     eax, 70000h
0x18003b39f  jnz     short loc_18003B3A4
0x18003b3a1  movzx   edi, di
0x18003b3a4  test    edi, edi
0x18003b3a6  jnz     short loc_18003B426
0x18003b3a8  test    r14, r14
0x18003b3ab  jz      short loc_18003B417
0x18003b3ad  lea     rcx, [rbp+57h+var_78]; pvarg
0x18003b3b1  call    cs:__imp_VariantClear
0x18003b3b7  mov     eax, 9
0x18003b3bc  mov     word ptr [rbp+57h+var_78], ax
0x18003b3c0  mov     qword ptr [rbp+57h+var_78+8], r14
0x18003b3c4  mov     rax, [r14]
0x18003b3c7  mov     rcx, r14
0x18003b3ca  mov     rax, [rax+8]
0x18003b3ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b3d3  mov     rcx, [rbp+57h+arg_18]
0x18003b3d7  movups  xmm0, xmmword ptr [rbp+57h+var_78]
0x18003b3db  movaps  [rbp+57h+var_40], xmm0
0x18003b3df  movsd   xmm1, qword ptr [rbp+57h+var_78+10h]
0x18003b3e4  movsd   [rbp+57h+var_30], xmm1
0x18003b3e9  mov     rax, [rcx]
0x18003b3ec  lea     rdx, [rbp+57h+var_40]
0x18003b3f0  mov     rax, [rax+270h]
0x18003b3f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b3fc  mov     edi, eax
0x18003b3fe  test    eax, eax
0x18003b400  js      short loc_18003B406
0x18003b402  xor     edi, edi
0x18003b404  jmp     short loc_18003B417
0x18003b406  and     eax, r13d
0x18003b409  cmp     eax, 70000h
0x18003b40e  jnz     short loc_18003B413
0x18003b410  movzx   edi, di
0x18003b413  test    edi, edi
0x18003b415  jnz     short loc_18003B426
0x18003b417  mov     rcx, [rbp+57h+arg_18]
0x18003b41b  mov     [rbp+57h+arg_18], 0
0x18003b423  mov     [r15], rcx
0x18003b426  lea     rcx, [rbp+57h+var_78]; pvarg
0x18003b42a  call    cs:__imp_VariantClear
0x18003b430  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18003b434  call    cs:__imp_VariantClear
0x18003b43a  mov     rcx, rbx; bstrString
0x18003b43d  call    cs:__imp_SysFreeString
0x18003b443  nop
0x18003b444  lea     rcx, [rbp+57h+arg_18]
0x18003b448  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18003b44d  nop
0x18003b44e  mov     eax, edi
0x18003b450  lea     r11, [rsp+0B0h+var_20]
0x18003b458  mov     rbx, [r11+30h]
0x18003b45c  mov     rsi, [r11+38h]
0x18003b460  mov     rsp, r11
0x18003b463  pop     r15
0x18003b465  pop     r14
0x18003b467  pop     r13
0x18003b469  pop     rdi
0x18003b46a  pop     rbp
0x18003b46b  retn
```
