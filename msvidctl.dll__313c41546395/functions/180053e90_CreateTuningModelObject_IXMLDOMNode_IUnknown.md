# CreateTuningModelObject(IXMLDOMNode *,IUnknown * *)

- ea: `0x180053e90`
- end: `0x1800540b0`
- name: `?CreateTuningModelObject@@YAJPEAUIXMLDOMNode@@PEAPEAUIUnknown@@@Z`
- size: `544`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, struct IUnknown **)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180052e30`
- `0x1800561f0`

## callees

- `0x180004640`
- `0x180006b38`
- `0x1800145ac`
- `0x180053e90`
- `0x180054780`
- `0x180054c78`
- `0x180055374`
- `0x1800f8010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180054029`
- `ole32!CoCreateInstance` at `0x180054029`
- `OLEAUT32!__imp_SysAllocString` at `0x180053ed3`
- `OLEAUT32!__imp_SysAllocString` at `0x180053ef5`
- `OLEAUT32!__imp_SysAllocString` at `0x180053ed3`
- `OLEAUT32!__imp_SysAllocString` at `0x180053ef5`
- `OLEAUT32!__imp_SysFreeString` at `0x180053f16`
- `OLEAUT32!__imp_SysFreeString` at `0x180053f70`
- `OLEAUT32!__imp_SysFreeString` at `0x180053f96`
- `OLEAUT32!__imp_SysFreeString` at `0x180053faf`
- `OLEAUT32!__imp_SysFreeString` at `0x180054058`
- `OLEAUT32!__imp_SysFreeString` at `0x18005407e`
- `OLEAUT32!__imp_SysFreeString` at `0x180053f16`
- `OLEAUT32!__imp_SysFreeString` at `0x180053f70`
- `OLEAUT32!__imp_SysFreeString` at `0x180053f96`
- `OLEAUT32!__imp_SysFreeString` at `0x180053faf`
- `OLEAUT32!__imp_SysFreeString` at `0x180054058`
- `OLEAUT32!__imp_SysFreeString` at `0x18005407e`
- `OLEAUT32!__imp_VariantClear` at `0x180053f8b`
- `OLEAUT32!__imp_VariantClear` at `0x180054073`
- `OLEAUT32!__imp_VariantClear` at `0x180053f8b`
- `OLEAUT32!__imp_VariantClear` at `0x180054073`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CreateTuningModelObject(struct IXMLDOMNode *a1, struct IUnknown **a2)
{
  OLECHAR *v4; // rbx
  HRESULT XmlAttributeValue; // edi
  OLECHAR *v6; // rcx
  int v8; // eax
  OLECHAR *v9; // rbx
  struct IUnknown *v10; // rax
  BSTR v11; // [rsp+30h] [rbp-50h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-48h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-30h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-28h] BYREF
  IID rclsid; // [rsp+60h] [rbp-20h] BYREF

  if ( !a1 || !a2 )
    return 2147500035LL;
  v11 = SysAllocString(&word_180165740);
  memset(&pvarg, 0, sizeof(pvarg));
  pvarg.vt = 0;
  v4 = SysAllocString(L"type");
  bstrString = v4;
  XmlAttributeValue = GetXmlAttributeValue(a1, v4, &pvarg);
  SysFreeString(v4);
  if ( XmlAttributeValue < 0 )
  {
    if ( XmlAttributeValue != -2147023728 )
    {
LABEL_12:
      if ( pvarg.vt == 4095 )
        pvarg.vt = 8;
      goto LABEL_14;
    }
    SysFreeString(v11);
    v11 = 0;
    v8 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))a1->lpVtbl->get_nodeName)(a1, &v11);
    if ( v8 )
    {
      XmlAttributeValue = -2147467259;
      if ( v8 < 0 )
        XmlAttributeValue = v8;
      goto LABEL_12;
    }
  }
  else
  {
    if ( pvarg.vt != 8 )
    {
      if ( pvarg.vt == 4095 )
        pvarg.vt = 8;
      XmlAttributeValue = -2147418113;
LABEL_14:
      VariantClear(&pvarg);
      SysFreeString(v11);
      return (unsigned int)XmlAttributeValue;
    }
    ATL::CComBSTR::operator=(&v11, pvarg.llVal);
  }
  bstrString = 0;
  XmlAttributeValue = UnprefixType(v11, &bstrString);
  if ( XmlAttributeValue < 0 )
  {
    v6 = bstrString;
LABEL_11:
    SysFreeString(v6);
    goto LABEL_12;
  }
  rclsid = 0;
  v9 = bstrString;
  XmlAttributeValue = GetTuneXmlCLSIDFromTypeName(bstrString, &rclsid);
  if ( XmlAttributeValue < 0 )
  {
LABEL_21:
    v6 = v9;
    goto LABEL_11;
  }
  ppv = 0;
  XmlAttributeValue = CoCreateInstance(&rclsid, 0, 0x17u, &GUID_00000000_0000_0000_c000_000000000046, &ppv);
  if ( XmlAttributeValue < 0 )
  {
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&ppv);
    goto LABEL_21;
  }
  v10 = (struct IUnknown *)ppv;
  ppv = 0;
  *a2 = v10;
  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&ppv);
  SysFreeString(v9);
  if ( pvarg.vt == 4095 )
    pvarg.vt = 8;
  VariantClear(&pvarg);
  SysFreeString(v11);
  return 0;
}

```

## disassembly

```asm
0x180053e90  mov     [rsp-28h+arg_10], rbx
0x180053e95  push    rbp
0x180053e96  push    rsi
0x180053e97  push    rdi
0x180053e98  push    r12
0x180053e9a  push    r14
0x180053e9c  mov     rbp, rsp
0x180053e9f  sub     rsp, 80h
0x180053ea6  mov     rax, cs:__security_cookie
0x180053ead  xor     rax, rsp
0x180053eb0  mov     [rbp+var_10], rax
0x180053eb4  mov     r14, rdx
0x180053eb7  mov     rsi, rcx
0x180053eba  test    rcx, rcx
0x180053ebd  jz      loc_180054088
0x180053ec3  test    rdx, rdx
0x180053ec6  jz      loc_180054088
0x180053ecc  lea     rcx, word_180165740; psz
0x180053ed3  call    cs:__imp_SysAllocString
0x180053ed9  mov     [rbp+var_50], rax
0x180053edd  xorps   xmm0, xmm0
0x180053ee0  xor     eax, eax
0x180053ee2  movups  xmmword ptr [rbp+pvarg], xmm0
0x180053ee6  mov     qword ptr [rbp+pvarg+10h], rax
0x180053eea  mov     word ptr [rbp+pvarg], ax
0x180053eee  lea     rcx, aType; "type"
0x180053ef5  call    cs:__imp_SysAllocString
0x180053efb  mov     rbx, rax
0x180053efe  mov     [rbp+bstrString], rax
0x180053f02  lea     r8, [rbp+pvarg]; struct tagVARIANT *
0x180053f06  mov     rdx, rax; unsigned __int16 *
0x180053f09  mov     rcx, rsi; struct IXMLDOMNode *
0x180053f0c  call    ?GetXmlAttributeValue@@YAJPEAUIXMLDOMNode@@PEAGPEAUtagVARIANT@@@Z; GetXmlAttributeValue(IXMLDOMNode *,ushort *,tagVARIANT *)
0x180053f11  mov     edi, eax
0x180053f13  mov     rcx, rbx; bstrString
0x180053f16  call    cs:__imp_SysFreeString
0x180053f1c  mov     r12d, 8
0x180053f22  test    edi, edi
0x180053f24  js      short loc_180053FA3
0x180053f26  cmp     word ptr [rbp+pvarg], r12w
0x180053f2b  jz      short loc_180053F44
0x180053f2d  mov     eax, 0FFFh
0x180053f32  cmp     word ptr [rbp+pvarg], ax
0x180053f36  jnz     short loc_180053F3D
0x180053f38  mov     word ptr [rbp+pvarg], r12w
0x180053f3d  mov     edi, 8000FFFFh
0x180053f42  jmp     short loc_180053F87
0x180053f44  mov     rdx, qword ptr [rbp+pvarg+8]
0x180053f48  lea     rcx, [rbp+var_50]
0x180053f4c  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x180053f51  mov     [rbp+bstrString], 0
0x180053f59  lea     rdx, [rbp+bstrString]; unsigned __int16 **
0x180053f5d  mov     rcx, [rbp+var_50]; unsigned __int16 *
0x180053f61  call    ?UnprefixType@@YAJPEAGPEAPEAG@Z; UnprefixType(ushort *,ushort * *)
0x180053f66  mov     edi, eax
0x180053f68  test    eax, eax
0x180053f6a  jns     short loc_180053FE2
0x180053f6c  mov     rcx, [rbp+bstrString]; bstrString
0x180053f70  call    cs:__imp_SysFreeString
0x180053f76  nop
0x180053f77  mov     eax, 0FFFh
0x180053f7c  cmp     word ptr [rbp+pvarg], ax
0x180053f80  jnz     short loc_180053F87
0x180053f82  mov     word ptr [rbp+pvarg], r12w
0x180053f87  lea     rcx, [rbp+pvarg]; pvarg
0x180053f8b  call    cs:__imp_VariantClear
0x180053f91  nop
0x180053f92  mov     rcx, [rbp+var_50]; bstrString
0x180053f96  call    cs:__imp_SysFreeString
0x180053f9c  mov     eax, edi
0x180053f9e  jmp     loc_18005408D
0x180053fa3  cmp     edi, 80070490h
0x180053fa9  jnz     short loc_180053F77
0x180053fab  mov     rcx, [rbp+var_50]; bstrString
0x180053faf  call    cs:__imp_SysFreeString
0x180053fb5  mov     [rbp+var_50], 0
0x180053fbd  mov     rax, [rsi]
0x180053fc0  lea     rdx, [rbp+var_50]
0x180053fc4  mov     rcx, rsi
0x180053fc7  mov     rax, [rax+38h]
0x180053fcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053fd0  test    eax, eax
0x180053fd2  jz      loc_180053F51
0x180053fd8  mov     edi, 80004005h
0x180053fdd  cmovs   edi, eax
0x180053fe0  jmp     short loc_180053F77
0x180053fe2  xorps   xmm0, xmm0
0x180053fe5  movups  xmmword ptr [rbp+rclsid.Data1], xmm0
0x180053fe9  lea     rdx, [rbp+rclsid]; pclsid
0x180053fed  mov     rbx, [rbp+bstrString]
0x180053ff1  mov     rcx, rbx; psz
0x180053ff4  call    ?GetTuneXmlCLSIDFromTypeName@@YAJPEAGPEAU_GUID@@@Z; GetTuneXmlCLSIDFromTypeName(ushort *,_GUID *)
0x180053ff9  mov     edi, eax
0x180053ffb  test    eax, eax
0x180053ffd  jns     short loc_180054007
0x180053fff  mov     rcx, rbx
0x180054002  jmp     loc_180053F70
0x180054007  mov     [rbp+var_30], 0
0x18005400f  lea     rax, [rbp+var_30]
0x180054013  mov     [rsp+80h+ppv], rax; ppv
0x180054018  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18005401f  xor     edx, edx; pUnkOuter
0x180054021  lea     r8d, [rdx+17h]; dwClsContext
0x180054025  lea     rcx, [rbp+rclsid]; rclsid
0x180054029  call    cs:__imp_CoCreateInstance
0x18005402f  mov     edi, eax
0x180054031  lea     rcx, [rbp+var_30]
0x180054035  test    eax, eax
0x180054037  jns     short loc_180054040
0x180054039  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18005403e  jmp     short loc_180053FFF
0x180054040  mov     rax, [rbp+var_30]
0x180054044  mov     [rbp+var_30], 0
0x18005404c  mov     [r14], rax
0x18005404f  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180054054  nop
0x180054055  mov     rcx, rbx; bstrString
0x180054058  call    cs:__imp_SysFreeString
0x18005405e  nop
0x18005405f  mov     eax, 0FFFh
0x180054064  cmp     word ptr [rbp+pvarg], ax
0x180054068  jnz     short loc_18005406F
0x18005406a  mov     word ptr [rbp+pvarg], r12w
0x18005406f  lea     rcx, [rbp+pvarg]; pvarg
0x180054073  call    cs:__imp_VariantClear
0x180054079  nop
0x18005407a  mov     rcx, [rbp+var_50]; bstrString
0x18005407e  call    cs:__imp_SysFreeString
0x180054084  xor     eax, eax
0x180054086  jmp     short loc_18005408D
0x180054088  mov     eax, 80004003h
0x18005408d  mov     rcx, [rbp+var_10]
0x180054091  xor     rcx, rsp; StackCookie
0x180054094  call    __security_check_cookie
0x180054099  mov     rbx, [rsp+80h+arg_10]
0x1800540a1  add     rsp, 80h
0x1800540a8  pop     r14
0x1800540aa  pop     r12
0x1800540ac  pop     rdi
0x1800540ad  pop     rsi
0x1800540ae  pop     rbp
0x1800540af  retn
```
