# NPrintTicketUtil::CPrintTicketWrapper::CreateValue(IXMLDOMElement *,ushort const *,ushort const *,ushort const *,IXMLDOMElement * *)

- ea: `0x180006d70`
- end: `0x180006f78`
- name: `?CreateValue@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG11PEAPEAU3@@Z`
- size: `520`
- prototype: `__int64 __usercall@<rax>(NPrintTicketUtil::CPrintTicketWrapper *__hidden this@<rcx>, struct IXMLDOMElement *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, const unsigned __int16 *, struct IXMLDOMElement **)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800064a0`
- `0x180006b10`
- `0x180007a04`
- `0x180009da8`
- `0x18001f850`

## callees

- `0x180006d70`
- `0x1800070e0`
- `0x18000a76c`
- `0x180023010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180006de8`
- `OLEAUT32!__imp_SysFreeString` at `0x180006e6b`
- `OLEAUT32!__imp_SysFreeString` at `0x180006de8`
- `OLEAUT32!__imp_SysFreeString` at `0x180006e6b`
- `OLEAUT32!__imp_VariantInit` at `0x180006ecd`
- `OLEAUT32!__imp_VariantInit` at `0x180006ecd`
- `OLEAUT32!__imp_VariantClear` at `0x180006f26`
- `OLEAUT32!__imp_VariantClear` at `0x180006f26`

## string_xrefs

- `0x180006dab`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework`
- `0x180006ee0`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework`
- `0x180006e9d`: `http://www.w3.org/2001/XMLSchema-instance`

## pseudocode

```c
__int64 __fastcall NPrintTicketUtil::CPrintTicketWrapper::CreateValue(
        __int64 **this,
        struct IXMLDOMElement *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct IXMLDOMElement *a5,
        struct IXMLDOMElement **a6)
{
  int QName; // ebx
  int v12; // eax
  OLECHAR *v13; // rdi
  __int64 *v14; // rcx
  __int64 v15; // rax
  __int64 (__fastcall *v16)(__int64 *, __int128 *, BSTR, const unsigned __int16 *, struct IXMLDOMElement ***); // rax
  unsigned __int16 **v17; // [rsp+28h] [rbp-50h]
  unsigned __int16 **v18; // [rsp+28h] [rbp-50h]
  struct IXMLDOMElement *v19; // [rsp+30h] [rbp-48h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-40h] BYREF
  __int128 v21; // [rsp+50h] [rbp-28h] BYREF
  IRecordInfo *pRecInfo; // [rsp+60h] [rbp-18h]
  BSTR bstrString; // [rsp+C0h] [rbp+48h] BYREF

  if ( !a3 || !a2 )
    return 2147942487LL;
  a6 = 0;
  bstrString = 0;
  QName = NPrintTicketUtil::CreateQName(
            (NPrintTicketUtil *)this,
            a2,
            (struct IXMLDOMElement *)&stru_180026B28,
            L"http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework",
            (const unsigned __int16 *)&bstrString,
            v17,
            0);
  if ( QName >= 0 )
  {
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    v14 = this[1];
    pvarg.vt = 3;
    pvarg.lVal = 1;
    v15 = *v14;
    pRecInfo = pvarg.pRecInfo;
    v16 = *(__int64 (__fastcall **)(__int64 *, __int128 *, BSTR, const unsigned __int16 *, struct IXMLDOMElement ***))(v15 + 448);
    v21 = *(_OWORD *)&pvarg.vt;
    QName = v16(
              v14,
              &v21,
              bstrString,
              L"http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework",
              &a6);
    VariantClear(&pvarg);
    if ( QName >= 0 )
    {
      QName = ((__int64 (__fastcall *)(struct IXMLDOMElement *, struct IXMLDOMElement **, _QWORD))a2->lpVtbl->appendChild)(
                a2,
                a6,
                0);
      if ( QName >= 0 )
        QName = ((__int64 (__fastcall *)(struct IXMLDOMElement **, GUID *, struct IXMLDOMElement **))(*a6)->lpVtbl)(
                  a6,
                  &IID_IXMLDOMElement,
                  &v19);
    }
  }
  if ( bstrString )
    SysFreeString(bstrString);
  if ( a6 )
    ((void (__fastcall *)(struct IXMLDOMElement **))(*a6)[2].lpVtbl)(a6);
  if ( QName >= 0 )
  {
    if ( !a5 || !a4 )
      goto LABEL_19;
    bstrString = 0;
    v12 = NPrintTicketUtil::CreateQName(
            (NPrintTicketUtil *)this,
            a2,
            a5,
            a4,
            (const unsigned __int16 *)&bstrString,
            v18,
            (const unsigned __int16 *)v19);
    v13 = bstrString;
    QName = v12;
    if ( v12 >= 0 )
      QName = NPrintTicketUtil::CPrintTicketWrapper::CreateXMLAttribute2(
                (NPrintTicketUtil::CPrintTicketWrapper *)this,
                v19,
                L"xsi:type",
                L"http://www.w3.org/2001/XMLSchema-instance",
                bstrString);
    if ( v13 )
      SysFreeString(v13);
    if ( QName >= 0 )
LABEL_19:
      QName = ((__int64 (__fastcall *)(struct IXMLDOMElement *, const unsigned __int16 *))v19->lpVtbl->put_text)(
                v19,
                a3);
  }
  if ( v19 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v19->lpVtbl->Release)(v19);
  return (unsigned int)QName;
}

```

## disassembly

```asm
0x180006d70  push    rbp
0x180006d72  push    rbx
0x180006d73  push    rdi
0x180006d74  push    r12
0x180006d76  push    r14
0x180006d78  push    r15
0x180006d7a  mov     rbp, rsp
0x180006d7d  sub     rsp, 78h
0x180006d81  mov     r15, r9
0x180006d84  mov     r12, r8
0x180006d87  mov     rdi, rdx
0x180006d8a  mov     r14, rcx
0x180006d8d  test    r8, r8
0x180006d90  jz      loc_180006E92
0x180006d96  test    rdx, rdx
0x180006d99  jz      loc_180006E92
0x180006d9f  lea     rax, [rbp+bstrString]
0x180006da3  mov     [rbp+var_48], 0
0x180006dab  lea     r9, aHttpSchemasMic_0; "http://schemas.microsoft.com/windows/20"...
0x180006db2  mov     [rsp+78h+psz], rax; unsigned __int16 *
0x180006db7  lea     r8, stru_180026B28; struct IXMLDOMElement *
0x180006dbe  mov     [rbp+arg_28], 0
0x180006dc6  mov     [rbp+bstrString], 0
0x180006dce  call    ?CreateQName@NPrintTicketUtil@@YAJPEAVCPrintTicketWrapper@1@PEAUIXMLDOMElement@@PEBG2PEAPEAG2@Z; NPrintTicketUtil::CreateQName(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,ushort const *,ushort const *,ushort * *,ushort const *)
0x180006dd3  mov     ebx, eax
0x180006dd5  test    eax, eax
0x180006dd7  jns     loc_180006EBC
0x180006ddd  cmp     [rbp+bstrString], 0
0x180006de2  jz      short loc_180006DEE
0x180006de4  mov     rcx, [rbp+bstrString]; bstrString
0x180006de8  call    cs:__imp_SysFreeString
0x180006dee  mov     rcx, [rbp+arg_28]
0x180006df2  test    rcx, rcx
0x180006df5  jz      short loc_180006E03
0x180006df7  mov     rax, [rcx]
0x180006dfa  mov     rax, [rax+10h]
0x180006dfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e03  test    ebx, ebx
0x180006e05  jns     short loc_180006E2C
0x180006e07  mov     rcx, [rbp+var_48]
0x180006e0b  test    rcx, rcx
0x180006e0e  jz      short loc_180006E1C
0x180006e10  mov     rax, [rcx]
0x180006e13  mov     rax, [rax+10h]
0x180006e17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e1c  mov     eax, ebx
0x180006e1e  add     rsp, 78h
0x180006e22  pop     r15
0x180006e24  pop     r14
0x180006e26  pop     r12
0x180006e28  pop     rdi
0x180006e29  pop     rbx
0x180006e2a  pop     rbp
0x180006e2b  retn
0x180006e2c  mov     r8, [rbp+arg_20]; struct IXMLDOMElement *
0x180006e30  test    r8, r8
0x180006e33  jz      short loc_180006E75
0x180006e35  test    r15, r15
0x180006e38  jz      short loc_180006E75
0x180006e3a  lea     rax, [rbp+bstrString]
0x180006e3e  mov     [rbp+bstrString], 0
0x180006e46  mov     r9, r15; unsigned __int16 *
0x180006e49  mov     [rsp+78h+psz], rax; unsigned __int16 *
0x180006e4e  mov     rdx, rdi; struct IXMLDOMElement *
0x180006e51  mov     rcx, r14; this
0x180006e54  call    ?CreateQName@NPrintTicketUtil@@YAJPEAVCPrintTicketWrapper@1@PEAUIXMLDOMElement@@PEBG2PEAPEAG2@Z; NPrintTicketUtil::CreateQName(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,ushort const *,ushort const *,ushort * *,ushort const *)
0x180006e59  mov     rdi, [rbp+bstrString]
0x180006e5d  mov     ebx, eax
0x180006e5f  test    eax, eax
0x180006e61  jns     short loc_180006E99
0x180006e63  test    rdi, rdi
0x180006e66  jz      short loc_180006E71
0x180006e68  mov     rcx, rdi; bstrString
0x180006e6b  call    cs:__imp_SysFreeString
0x180006e71  test    ebx, ebx
0x180006e73  js      short loc_180006E07
0x180006e75  mov     rcx, [rbp+var_48]
0x180006e79  mov     rdx, r12
0x180006e7c  mov     rax, [rcx]
0x180006e7f  mov     rax, [rax+0D8h]
0x180006e86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e8b  mov     ebx, eax
0x180006e8d  jmp     loc_180006E07
0x180006e92  mov     eax, 80070057h
0x180006e97  jmp     short loc_180006E1E
0x180006e99  mov     rdx, [rbp+var_48]; struct IXMLDOMElement *
0x180006e9d  lea     r9, aHttpWwwW3Org20_0; "http://www.w3.org/2001/XMLSchema-instan"...
0x180006ea4  lea     r8, aXsiType; "xsi:type"
0x180006eab  mov     [rsp+78h+psz], rdi; psz
0x180006eb0  mov     rcx, r14; this
0x180006eb3  call    ?CreateXMLAttribute2@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG11@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateXMLAttribute2(IXMLDOMElement *,ushort const *,ushort const *,ushort const *)
0x180006eb8  mov     ebx, eax
0x180006eba  jmp     short loc_180006E63
0x180006ebc  xorps   xmm0, xmm0
0x180006ebf  lea     rcx, [rbp+pvarg]; pvarg
0x180006ec3  xor     eax, eax
0x180006ec5  movups  xmmword ptr [rbp+pvarg], xmm0
0x180006ec9  mov     qword ptr [rbp+pvarg+10h], rax
0x180006ecd  call    cs:__imp_VariantInit
0x180006ed3  mov     rcx, [r14+8]
0x180006ed7  lea     rdx, [rbp+arg_28]
0x180006edb  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x180006ee0  lea     r9, aHttpSchemasMic_0; "http://schemas.microsoft.com/windows/20"...
0x180006ee7  mov     r8, [rbp+bstrString]
0x180006eeb  mov     eax, 3
0x180006ef0  mov     word ptr [rbp+pvarg], ax
0x180006ef4  mov     dword ptr [rbp+pvarg+8], 1
0x180006efb  mov     rax, [rcx]
0x180006efe  movups  xmm0, xmmword ptr [rbp+pvarg]
0x180006f02  mov     [rsp+78h+psz], rdx
0x180006f07  lea     rdx, [rbp+var_28]
0x180006f0b  movsd   [rbp+var_18], xmm1
0x180006f10  mov     rax, [rax+1C0h]
0x180006f17  movaps  [rbp+var_28], xmm0
0x180006f1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f20  lea     rcx, [rbp+pvarg]; pvarg
0x180006f24  mov     ebx, eax
0x180006f26  call    cs:__imp_VariantClear
0x180006f2c  test    ebx, ebx
0x180006f2e  js      loc_180006DDD
0x180006f34  mov     rax, [rdi]
0x180006f37  xor     r8d, r8d
0x180006f3a  mov     rdx, [rbp+arg_28]
0x180006f3e  mov     rcx, rdi
0x180006f41  mov     rax, [rax+0A8h]
0x180006f48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f4d  mov     ebx, eax
0x180006f4f  test    eax, eax
0x180006f51  js      loc_180006DDD
0x180006f57  mov     rcx, [rbp+arg_28]
0x180006f5b  lea     r8, [rbp+var_48]
0x180006f5f  lea     rdx, IID_IXMLDOMElement
0x180006f66  mov     rax, [rcx]
0x180006f69  mov     rax, [rax]
0x180006f6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f71  mov     ebx, eax
0x180006f73  jmp     loc_180006DDD
```
