# CreateRootTuneXmlNode(IXMLDOMNode * *)

- ea: `0x180053a28`
- end: `0x180053c98`
- name: `?CreateRootTuneXmlNode@@YAJPEAPEAUIXMLDOMNode@@@Z`
- size: `624`
- prototype: `__int64 __fastcall(struct IXMLDOMNode **)`
- caller_count: `31`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800176bc`
- `0x180017c10`
- `0x18001ada0`
- `0x18001c2b0`
- `0x18001de94`
- `0x18001f620`
- `0x180020eec`
- `0x180022840`
- `0x180023f90`
- `0x1800255c0`
- `0x180026a90`
- `0x180027ea0`
- `0x1800291c0`
- `0x18002d37c`
- `0x18002d8d0`
- `0x18002da7c`
- `0x18002dc28`
- `0x18002ddd4`
- `0x18002df80`
- `0x180034960`
- `0x180034b0c`
- `0x18003e9b0`
- `0x18003eb5c`
- `0x18003ed08`
- `0x18003eeb4`
- `0x18003f060`
- `0x18003f20c`
- `0x18003f3b8`
- `0x18003f564`
- `0x18003f710`
- `0x18004f530`

## callees

- `0x180006b38`
- `0x18001424c`
- `0x180053a28`
- `0x1800544a8`
- `0x180054b08`
- `0x1800555c8`
- `0x1800f8010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180053a71`
- `ole32!CoCreateInstance` at `0x180053a71`
- `OLEAUT32!__imp_SysFreeString` at `0x180053b31`
- `OLEAUT32!__imp_SysFreeString` at `0x180053b65`
- `OLEAUT32!__imp_SysFreeString` at `0x180053b6f`
- `OLEAUT32!__imp_SysFreeString` at `0x180053c08`
- `OLEAUT32!__imp_SysFreeString` at `0x180053c12`
- `OLEAUT32!__imp_SysFreeString` at `0x180053c33`
- `OLEAUT32!__imp_SysFreeString` at `0x180053c3d`
- `OLEAUT32!__imp_SysFreeString` at `0x180053c62`
- `OLEAUT32!__imp_SysFreeString` at `0x180053c6c`
- `OLEAUT32!__imp_SysFreeString` at `0x180053b31`
- `OLEAUT32!__imp_SysFreeString` at `0x180053b65`
- `OLEAUT32!__imp_SysFreeString` at `0x180053b6f`
- `OLEAUT32!__imp_SysFreeString` at `0x180053c08`
- `OLEAUT32!__imp_SysFreeString` at `0x180053c12`
- `OLEAUT32!__imp_SysFreeString` at `0x180053c33`
- `OLEAUT32!__imp_SysFreeString` at `0x180053c3d`
- `OLEAUT32!__imp_SysFreeString` at `0x180053c62`
- `OLEAUT32!__imp_SysFreeString` at `0x180053c6c`
- `OLEAUT32!__imp_VariantClear` at `0x180053af6`
- `OLEAUT32!__imp_VariantClear` at `0x180053be7`
- `OLEAUT32!__imp_VariantClear` at `0x180053af6`
- `OLEAUT32!__imp_VariantClear` at `0x180053be7`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CreateRootTuneXmlNode(struct IXMLDOMNode **a1)
{
  HRESULT TuneXmlSchema; // ebx
  LPVOID v4; // rdi
  __int64 (__fastcall *v5)(LPVOID, VARIANTARG *); // rbx
  int v6; // ebx
  int v7; // esi
  OLECHAR *v8; // rbx
  int v9; // edi
  __int64 v10; // rax
  OLECHAR *v11; // rdi
  int v12; // r14d
  struct IXMLDOMNode *v13; // rax
  struct IDispatch *v14; // [rsp+30h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-38h] BYREF
  VARIANTARG v16; // [rsp+50h] [rbp-20h] BYREF
  struct IXMLDOMNode *v17; // [rsp+B0h] [rbp+40h] BYREF
  LPVOID ppv; // [rsp+B8h] [rbp+48h] BYREF
  BSTR bstrString; // [rsp+C0h] [rbp+50h] BYREF
  BSTR v20; // [rsp+C8h] [rbp+58h] BYREF

  if ( !a1 )
    return 2147500035LL;
  ppv = 0;
  TuneXmlSchema = CoCreateInstance(&CLSID_DOMDocument60, 0, 0x17u, &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60, &ppv);
  if ( TuneXmlSchema >= 0 )
  {
    v14 = 0;
    TuneXmlSchema = GetTuneXmlSchema((struct IXMLDOMSchemaCollection2 **)&v14);
    if ( TuneXmlSchema >= 0 )
    {
      v4 = ppv;
      v5 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *))(*(_QWORD *)ppv + 624LL);
      v16 = *(VARIANTARG *)ATL::CComVariant::CComVariant((ATL::CComVariant *)&pvarg, v14);
      v6 = v5(v4, &v16);
      if ( pvarg.vt == 4095 )
        pvarg.vt = 8;
      VariantClear(&pvarg);
      if ( v6 )
      {
        v7 = -2147467259;
        if ( v6 < 0 )
          v7 = v6;
      }
      else
      {
        bstrString = 0;
        TuneXmlSchema = GetTuneXmlPrefixFromNamespace(g_bstrTuneXmlNamespace, &bstrString);
        if ( TuneXmlSchema < 0 )
        {
          SysFreeString(bstrString);
          goto LABEL_24;
        }
        v20 = 0;
        v8 = bstrString;
        v9 = PrefixType(bstrString, g_bstrTuneXmlRootNodeBaseName, &v20);
        if ( v9 < 0 )
        {
          SysFreeString(v20);
          SysFreeString(v8);
          TuneXmlSchema = v9;
          goto LABEL_24;
        }
        v17 = 0;
        v10 = *(_QWORD *)ppv;
        v11 = v20;
        pvarg.vt = 3;
        pvarg.lVal = 1;
        v16 = pvarg;
        v12 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, BSTR, OLECHAR *, struct IXMLDOMNode **))(v10 + 448))(
                ppv,
                &v16,
                v20,
                g_bstrTuneXmlNamespace,
                &v17);
        if ( pvarg.vt == 4095 )
          pvarg.vt = 8;
        VariantClear(&pvarg);
        if ( !v12 )
        {
          v13 = v17;
          if ( v17 )
          {
            v17 = 0;
            *a1 = v13;
            ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v17);
            SysFreeString(v11);
            SysFreeString(v8);
            TuneXmlSchema = 0;
          }
          else
          {
            ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v17);
            SysFreeString(v11);
            SysFreeString(v8);
            TuneXmlSchema = -2147418113;
          }
          goto LABEL_24;
        }
        v7 = -2147467259;
        if ( v12 < 0 )
          v7 = v12;
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v17);
        SysFreeString(v11);
        SysFreeString(v8);
      }
      TuneXmlSchema = v7;
    }
LABEL_24:
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v14);
  }
  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&ppv);
  return (unsigned int)TuneXmlSchema;
}

```

## disassembly

```asm
0x180053a28  push    rbp
0x180053a2a  push    rbx
0x180053a2b  push    rsi
0x180053a2c  push    rdi
0x180053a2d  push    r12
0x180053a2f  push    r13
0x180053a31  push    r14
0x180053a33  mov     rbp, rsp
0x180053a36  sub     rsp, 70h
0x180053a3a  mov     rsi, rcx
0x180053a3d  test    rcx, rcx
0x180053a40  jnz     short loc_180053A4C
0x180053a42  mov     eax, 80004003h
0x180053a47  jmp     loc_180053C89
0x180053a4c  mov     [rbp+arg_8], 0
0x180053a54  lea     rax, [rbp+arg_8]
0x180053a58  mov     [rsp+70h+ppv], rax; ppv
0x180053a5d  lea     r9, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; riid
0x180053a64  xor     edx, edx; pUnkOuter
0x180053a66  lea     r8d, [rdx+17h]; dwClsContext
0x180053a6a  lea     rcx, CLSID_DOMDocument60; rclsid
0x180053a71  call    cs:__imp_CoCreateInstance
0x180053a77  mov     ebx, eax
0x180053a79  test    eax, eax
0x180053a7b  js      loc_180053C7E
0x180053a81  mov     [rbp+var_40], 0
0x180053a89  lea     rcx, [rbp+var_40]; struct IXMLDOMSchemaCollection2 **
0x180053a8d  call    ?GetTuneXmlSchema@@YAJPEAPEAUIXMLDOMSchemaCollection2@@@Z; GetTuneXmlSchema(IXMLDOMSchemaCollection2 * *)
0x180053a92  mov     ebx, eax
0x180053a94  test    eax, eax
0x180053a96  js      loc_180053C74
0x180053a9c  mov     rdi, [rbp+arg_8]
0x180053aa0  mov     rax, [rdi]
0x180053aa3  mov     rbx, [rax+270h]
0x180053aaa  mov     rdx, [rbp+var_40]; struct IDispatch *
0x180053aae  lea     rcx, [rbp+pvarg]; this
0x180053ab2  call    ??0CComVariant@ATL@@QEAA@PEAUIDispatch@@@Z; ATL::CComVariant::CComVariant(IDispatch *)
0x180053ab7  nop
0x180053ab8  movups  xmm0, xmmword ptr [rax]
0x180053abb  movaps  [rbp+var_20], xmm0
0x180053abf  movsd   xmm1, qword ptr [rax+10h]
0x180053ac4  movsd   [rbp+var_10], xmm1
0x180053ac9  lea     rdx, [rbp+var_20]
0x180053acd  mov     rcx, rdi
0x180053ad0  mov     rax, rbx
0x180053ad3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053ad8  mov     ebx, eax
0x180053ada  mov     r13d, 0FFFh
0x180053ae0  mov     r12d, 8
0x180053ae6  cmp     word ptr [rbp+pvarg], r13w
0x180053aeb  jnz     short loc_180053AF2
0x180053aed  mov     word ptr [rbp+pvarg], r12w
0x180053af2  lea     rcx, [rbp+pvarg]; pvarg
0x180053af6  call    cs:__imp_VariantClear
0x180053afc  test    ebx, ebx
0x180053afe  jz      short loc_180053B0F
0x180053b00  mov     esi, 80004005h
0x180053b05  cmovs   esi, ebx
0x180053b08  mov     ebx, esi
0x180053b0a  jmp     loc_180053C74
0x180053b0f  mov     [rbp+bstrString], 0
0x180053b17  lea     rdx, [rbp+bstrString]; unsigned __int16 **
0x180053b1b  mov     rcx, cs:?g_bstrTuneXmlNamespace@@3VCComBSTR@ATL@@A; psz
0x180053b22  call    ?GetTuneXmlPrefixFromNamespace@@YAJPEAGPEAPEAG@Z; GetTuneXmlPrefixFromNamespace(ushort *,ushort * *)
0x180053b27  mov     ebx, eax
0x180053b29  test    eax, eax
0x180053b2b  jns     short loc_180053B3C
0x180053b2d  mov     rcx, [rbp+bstrString]; bstrString
0x180053b31  call    cs:__imp_SysFreeString
0x180053b37  jmp     loc_180053C74
0x180053b3c  mov     [rbp+arg_18], 0
0x180053b44  lea     r8, [rbp+arg_18]; unsigned __int16 **
0x180053b48  mov     rdx, cs:?g_bstrTuneXmlRootNodeBaseName@@3VCComBSTR@ATL@@A; unsigned __int16 *
0x180053b4f  mov     rbx, [rbp+bstrString]
0x180053b53  mov     rcx, rbx; unsigned __int16 *
0x180053b56  call    ?PrefixType@@YAJPEAG0PEAPEAG@Z; PrefixType(ushort *,ushort *,ushort * *)
0x180053b5b  mov     edi, eax
0x180053b5d  test    eax, eax
0x180053b5f  jns     short loc_180053B7C
0x180053b61  mov     rcx, [rbp+arg_18]; bstrString
0x180053b65  call    cs:__imp_SysFreeString
0x180053b6b  nop
0x180053b6c  mov     rcx, rbx; bstrString
0x180053b6f  call    cs:__imp_SysFreeString
0x180053b75  mov     ebx, edi
0x180053b77  jmp     loc_180053C74
0x180053b7c  mov     [rbp+arg_0], 0
0x180053b84  mov     rcx, [rbp+arg_8]
0x180053b88  mov     rax, [rcx]
0x180053b8b  mov     rdi, [rbp+arg_18]
0x180053b8f  mov     edx, 3
0x180053b94  mov     word ptr [rbp+pvarg], dx
0x180053b98  mov     dword ptr [rbp+pvarg+8], 1
0x180053b9f  movups  xmm0, xmmword ptr [rbp+pvarg]
0x180053ba3  movaps  [rbp+var_20], xmm0
0x180053ba7  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x180053bac  movsd   [rbp+var_10], xmm1
0x180053bb1  lea     rdx, [rbp+arg_0]
0x180053bb5  mov     [rsp+70h+ppv], rdx
0x180053bba  mov     r9, cs:?g_bstrTuneXmlNamespace@@3VCComBSTR@ATL@@A; ATL::CComBSTR g_bstrTuneXmlNamespace
0x180053bc1  mov     r8, rdi
0x180053bc4  lea     rdx, [rbp+var_20]
0x180053bc8  mov     rax, [rax+1C0h]
0x180053bcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053bd4  mov     r14d, eax
0x180053bd7  cmp     word ptr [rbp+pvarg], r13w
0x180053bdc  jnz     short loc_180053BE3
0x180053bde  mov     word ptr [rbp+pvarg], r12w
0x180053be3  lea     rcx, [rbp+pvarg]; pvarg
0x180053be7  call    cs:__imp_VariantClear
0x180053bed  test    r14d, r14d
0x180053bf0  jz      short loc_180053C1D
0x180053bf2  mov     esi, 80004005h
0x180053bf7  cmovs   esi, r14d
0x180053bfb  lea     rcx, [rbp+arg_0]
0x180053bff  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180053c04  nop
0x180053c05  mov     rcx, rdi; bstrString
0x180053c08  call    cs:__imp_SysFreeString
0x180053c0e  nop
0x180053c0f  mov     rcx, rbx; bstrString
0x180053c12  call    cs:__imp_SysFreeString
0x180053c18  jmp     loc_180053B08
0x180053c1d  mov     rax, [rbp+arg_0]
0x180053c21  test    rax, rax
0x180053c24  jnz     short loc_180053C4A
0x180053c26  lea     rcx, [rbp+arg_0]
0x180053c2a  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180053c2f  nop
0x180053c30  mov     rcx, rdi; bstrString
0x180053c33  call    cs:__imp_SysFreeString
0x180053c39  nop
0x180053c3a  mov     rcx, rbx; bstrString
0x180053c3d  call    cs:__imp_SysFreeString
0x180053c43  mov     ebx, 8000FFFFh
0x180053c48  jmp     short loc_180053C74
0x180053c4a  mov     [rbp+arg_0], 0
0x180053c52  mov     [rsi], rax
0x180053c55  lea     rcx, [rbp+arg_0]
0x180053c59  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180053c5e  nop
0x180053c5f  mov     rcx, rdi; bstrString
0x180053c62  call    cs:__imp_SysFreeString
0x180053c68  nop
0x180053c69  mov     rcx, rbx; bstrString
0x180053c6c  call    cs:__imp_SysFreeString
0x180053c72  xor     ebx, ebx
0x180053c74  lea     rcx, [rbp+var_40]
0x180053c78  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180053c7d  nop
0x180053c7e  lea     rcx, [rbp+arg_8]
0x180053c82  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180053c87  mov     eax, ebx
0x180053c89  add     rsp, 70h
0x180053c8d  pop     r14
0x180053c8f  pop     r13
0x180053c91  pop     r12
0x180053c93  pop     rdi
0x180053c94  pop     rsi
0x180053c95  pop     rbx
0x180053c96  pop     rbp
0x180053c97  retn
```
