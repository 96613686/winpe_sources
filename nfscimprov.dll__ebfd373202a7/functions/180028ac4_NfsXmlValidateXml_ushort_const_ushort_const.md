# NfsXmlValidateXml(ushort const *,ushort const *)

- ea: `0x180028ac4`
- end: `0x180028ca3`
- name: `?NfsXmlValidateXml@@YAJPEBG0@Z`
- size: `479`
- prototype: `__int64 __fastcall(OLECHAR *psz, OLECHAR *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180027c5c`

## callees

- `0x180027adc`
- `0x180027b7c`
- `0x18002889c`
- `0x180028ac4`
- `0x180037010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180028b28`
- `ole32!CoCreateInstance` at `0x180028ba0`
- `ole32!CoCreateInstance` at `0x180028b28`
- `ole32!CoCreateInstance` at `0x180028ba0`
- `OLEAUT32!__imp_SysAllocString` at `0x180028bd4`
- `OLEAUT32!__imp_SysAllocString` at `0x180028bd4`
- `OLEAUT32!__imp_VariantInit` at `0x180028b05`
- `OLEAUT32!__imp_VariantInit` at `0x180028b05`
- `OLEAUT32!__imp_VariantClear` at `0x180028c49`
- `OLEAUT32!__imp_VariantClear` at `0x180028c49`

## string_xrefs

- `0x180028bcd`: `http://schemas.microsoft.com/nfs/2011/03/share`

## pseudocode

```c
__int64 __fastcall NfsXmlValidateXml(OLECHAR *psz, OLECHAR *a2)
{
  HRESULT Instance; // ebx
  BSTR v5; // rdx
  struct IXMLDOMSchemaCollectionVtbl *lpVtbl; // rax
  bool IsNameSpaceValid; // al
  int v8; // ecx
  struct IXMLDOMDocument *ppv; // [rsp+30h] [rbp-50h] BYREF
  LPVOID v11; // [rsp+38h] [rbp-48h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-40h] BYREF
  VARIANTARG v13; // [rsp+60h] [rbp-20h] BYREF
  LONGLONG v14; // [rsp+B0h] [rbp+30h] BYREF
  struct IXMLDOMSchemaCollection *v15; // [rsp+B8h] [rbp+38h] BYREF

  v11 = 0;
  ppv = 0;
  v15 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v14 = 0;
  VariantInit(&pvarg);
  Instance = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument, (LPVOID *)&ppv);
  if ( Instance >= 0 )
  {
    Instance = NfsXmlLoadXmlFromString(a2, &v11, 1u);
    if ( Instance >= 0 )
    {
      Instance = (*(__int64 (__fastcall **)(LPVOID, LONGLONG *))(*(_QWORD *)v11 + 360LL))(v11, &v14);
      if ( Instance >= 0 )
      {
        if ( v14 )
        {
          Instance = CoCreateInstance(&CLSID_XMLSchemaCache60, 0, 0x15u, &IID_IXMLDOMSchemaCollection, (LPVOID *)&v15);
          if ( Instance >= 0 )
          {
            pvarg.vt = 9;
            pvarg.llVal = v14;
            (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)v14 + 8LL))(v14);
            v5 = SysAllocString(L"http://schemas.microsoft.com/nfs/2011/03/share");
            if ( !v5 )
              Instance = -2147024888;
            if ( Instance >= 0 )
            {
              lpVtbl = v15->lpVtbl;
              v13 = pvarg;
              Instance = ((__int64 (__fastcall *)(struct IXMLDOMSchemaCollection *, BSTR, VARIANTARG *))lpVtbl->add)(
                           v15,
                           v5,
                           &v13);
              if ( Instance >= 0 )
              {
                Instance = NfsXmlSchemaValidation(psz, (LPVOID *)&ppv, &v15);
                if ( Instance >= 0 )
                {
                  IsNameSpaceValid = NfsXmlIsNameSpaceValid(&ppv);
                  v8 = Instance;
                  if ( !IsNameSpaceValid )
                    v8 = -2147467259;
                  Instance = v8;
                }
              }
            }
          }
        }
        else
        {
          Instance = -2147467259;
        }
      }
    }
  }
  VariantClear(&pvarg);
  if ( v14 )
    (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)v14 + 16LL))(v14);
  if ( v11 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v11 + 16LL))(v11);
  if ( v15 )
    ((void (__fastcall *)(struct IXMLDOMSchemaCollection *))v15->lpVtbl->Release)(v15);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180028ac4  mov     [rsp-18h+arg_0], rbx
0x180028ac9  push    rbp
0x180028aca  push    rsi
0x180028acb  push    rdi
0x180028acc  mov     rbp, rsp
0x180028acf  sub     rsp, 80h
0x180028ad6  xor     eax, eax
0x180028ad8  mov     [rbp+var_48], 0
0x180028ae0  mov     rsi, rcx
0x180028ae3  mov     qword ptr [rbp+pvarg+10h], rax
0x180028ae7  xorps   xmm0, xmm0
0x180028aea  mov     [rbp+var_50], rax
0x180028aee  lea     rcx, [rbp+pvarg]; pvarg
0x180028af2  mov     [rbp+arg_18], rax
0x180028af6  movups  xmmword ptr [rbp+pvarg], xmm0
0x180028afa  mov     rdi, rdx
0x180028afd  mov     [rbp+arg_10], 0
0x180028b05  call    cs:__imp_VariantInit
0x180028b0b  xor     edx, edx; pUnkOuter
0x180028b0d  lea     rax, [rbp+var_50]
0x180028b11  lea     r9, IID_IXMLDOMDocument; riid
0x180028b18  mov     [rsp+80h+ppv], rax; ppv
0x180028b1d  lea     rcx, CLSID_DOMDocument60; rclsid
0x180028b24  lea     r8d, [rdx+1]; dwClsContext
0x180028b28  call    cs:__imp_CoCreateInstance
0x180028b2e  mov     ebx, eax
0x180028b30  test    eax, eax
0x180028b32  js      loc_180028C45
0x180028b38  mov     r8b, 1; unsigned __int8
0x180028b3b  lea     rdx, [rbp+var_48]; ppv
0x180028b3f  mov     rcx, rdi; psz
0x180028b42  call    ?NfsXmlLoadXmlFromString@@YAJPEBGPEAPEAUIXMLDOMDocument@@E@Z; NfsXmlLoadXmlFromString(ushort const *,IXMLDOMDocument * *,uchar)
0x180028b47  mov     ebx, eax
0x180028b49  test    eax, eax
0x180028b4b  js      loc_180028C45
0x180028b51  mov     rcx, [rbp+var_48]
0x180028b55  lea     rdx, [rbp+arg_10]
0x180028b59  mov     rax, [rcx]
0x180028b5c  mov     rax, [rax+168h]
0x180028b63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028b68  mov     ebx, eax
0x180028b6a  test    eax, eax
0x180028b6c  js      loc_180028C45
0x180028b72  cmp     [rbp+arg_10], 0
0x180028b77  jnz     short loc_180028B83
0x180028b79  mov     ebx, 80004005h
0x180028b7e  jmp     loc_180028C45
0x180028b83  xor     edx, edx; pUnkOuter
0x180028b85  lea     rax, [rbp+arg_18]
0x180028b89  lea     r9, IID_IXMLDOMSchemaCollection; riid
0x180028b90  mov     [rsp+80h+ppv], rax; ppv
0x180028b95  lea     rcx, CLSID_XMLSchemaCache60; rclsid
0x180028b9c  lea     r8d, [rdx+15h]; dwClsContext
0x180028ba0  call    cs:__imp_CoCreateInstance
0x180028ba6  mov     ebx, eax
0x180028ba8  test    eax, eax
0x180028baa  js      loc_180028C45
0x180028bb0  mov     rcx, [rbp+arg_10]
0x180028bb4  mov     eax, 9
0x180028bb9  mov     word ptr [rbp+pvarg], ax
0x180028bbd  mov     qword ptr [rbp+pvarg+8], rcx
0x180028bc1  mov     rax, [rcx]
0x180028bc4  mov     rax, [rax+8]
0x180028bc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028bcd  lea     rcx, aHttpSchemasMic; "http://schemas.microsoft.com/nfs/2011/0"...
0x180028bd4  call    cs:__imp_SysAllocString
0x180028bda  mov     rdx, rax
0x180028bdd  mov     eax, 80070008h
0x180028be2  test    rdx, rdx
0x180028be5  cmovz   ebx, eax
0x180028be8  test    ebx, ebx
0x180028bea  js      short loc_180028C45
0x180028bec  mov     rcx, [rbp+arg_18]
0x180028bf0  lea     r8, [rbp+var_20]
0x180028bf4  movups  xmm0, xmmword ptr [rbp+pvarg]
0x180028bf8  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x180028bfd  mov     rax, [rcx]
0x180028c00  movaps  [rbp+var_20], xmm0
0x180028c04  movsd   [rbp+var_10], xmm1
0x180028c09  mov     rax, [rax+38h]
0x180028c0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028c12  mov     ebx, eax
0x180028c14  test    eax, eax
0x180028c16  js      short loc_180028C45
0x180028c18  lea     r8, [rbp+arg_18]; struct IXMLDOMSchemaCollection **
0x180028c1c  mov     rcx, rsi; psz
0x180028c1f  lea     rdx, [rbp+var_50]; ppv
0x180028c23  call    ?NfsXmlSchemaValidation@@YAJPEBGPEAPEAUIXMLDOMDocument@@PEAPEAUIXMLDOMSchemaCollection@@@Z; NfsXmlSchemaValidation(ushort const *,IXMLDOMDocument * *,IXMLDOMSchemaCollection * *)
0x180028c28  mov     ebx, eax
0x180028c2a  test    eax, eax
0x180028c2c  js      short loc_180028C45
0x180028c2e  lea     rcx, [rbp+var_50]; struct IXMLDOMDocument **
0x180028c32  call    ?NfsXmlIsNameSpaceValid@@YA_NPEAPEAUIXMLDOMDocument@@@Z; NfsXmlIsNameSpaceValid(IXMLDOMDocument * *)
0x180028c37  mov     ecx, ebx
0x180028c39  test    al, al
0x180028c3b  mov     ebx, 80004005h
0x180028c40  cmovz   ecx, ebx
0x180028c43  mov     ebx, ecx
0x180028c45  lea     rcx, [rbp+pvarg]; pvarg
0x180028c49  call    cs:__imp_VariantClear
0x180028c4f  mov     rcx, [rbp+arg_10]
0x180028c53  test    rcx, rcx
0x180028c56  jz      short loc_180028C64
0x180028c58  mov     rax, [rcx]
0x180028c5b  mov     rax, [rax+10h]
0x180028c5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028c64  mov     rcx, [rbp+var_48]
0x180028c68  test    rcx, rcx
0x180028c6b  jz      short loc_180028C79
0x180028c6d  mov     rax, [rcx]
0x180028c70  mov     rax, [rax+10h]
0x180028c74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028c79  mov     rcx, [rbp+arg_18]
0x180028c7d  test    rcx, rcx
0x180028c80  jz      short loc_180028C8E
0x180028c82  mov     rax, [rcx]
0x180028c85  mov     rax, [rax+10h]
0x180028c89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028c8e  mov     eax, ebx
0x180028c90  mov     rbx, [rsp+80h+arg_0]
0x180028c98  add     rsp, 80h
0x180028c9f  pop     rdi
0x180028ca0  pop     rsi
0x180028ca1  pop     rbp
0x180028ca2  retn
```
