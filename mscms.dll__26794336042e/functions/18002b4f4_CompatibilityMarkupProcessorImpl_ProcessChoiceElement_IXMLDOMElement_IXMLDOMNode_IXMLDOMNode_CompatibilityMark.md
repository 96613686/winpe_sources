# CompatibilityMarkupProcessorImpl::ProcessChoiceElement(IXMLDOMElement *,IXMLDOMNode *,IXMLDOMNode *,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> *,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> *,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> *,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25> *,bool,bool *)

- ea: `0x18002b4f4`
- end: `0x18002b8d2`
- name: `?ProcessChoiceElement@CompatibilityMarkupProcessorImpl@@AEAAJPEAUIXMLDOMElement@@PEAUIXMLDOMNode@@1PEAU?$Map@VCComBSTR@ATL@@V12@$0BJ@@1@2PEAU?$Vector@VCComBSTR@ATL@@$0BJ@@1@PEAU?$Map@VCComBSTR@ATL@@U?$Vector@VCComBSTR@ATL@@$0DC@@CompatibilityMarkupProcessorImpl@@$0BJ@@1@_NPEA_N@Z`
- size: `990`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180056054`

## callees

- `0x180010670`
- `0x180012620`
- `0x1800126c8`
- `0x18001277c`
- `0x1800127cc`
- `0x180020210`
- `0x18002b4f4`
- `0x18002b8d8`
- `0x18002e5f0`
- `0x18002eac0`
- `0x180055528`
- `0x18005561c`
- `0x1800557c4`
- `0x180055c5c`
- `0x180084010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18002b67b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b69d`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b796`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b872`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b67b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b69d`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b796`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b872`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CompatibilityMarkupProcessorImpl::ProcessChoiceElement(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        char *a5,
        __int64 a6,
        void *a7,
        void *a8,
        char a9,
        _BYTE *a10)
{
  __int64 result; // rax
  char *v13; // rbx
  void *v14; // rbx
  void *v15; // rbx
  int v16; // ebx
  int v17; // eax
  __int64 v18; // rax
  __int64 v19; // rcx
  int v20; // ecx
  CompatibilityMarkupProcessorImpl *v21; // rcx
  BSTR bstrString; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v23; // [rsp+38h] [rbp-C8h] BYREF
  struct IXMLDOMNamedNodeMap *v24; // [rsp+40h] [rbp-C0h] BYREF
  char *v25; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v26; // [rsp+50h] [rbp-B0h] BYREF
  void (__fastcall ***v27)(_QWORD, GUID *, _QWORD *); // [rsp+58h] [rbp-A8h] BYREF
  void *v28; // [rsp+60h] [rbp-A0h] BYREF
  void *v29; // [rsp+68h] [rbp-98h] BYREF
  char *v30; // [rsp+70h] [rbp-90h] BYREF
  void *v31; // [rsp+78h] [rbp-88h] BYREF
  void *v32; // [rsp+80h] [rbp-80h] BYREF
  __int64 v33; // [rsp+88h] [rbp-78h]
  __int64 v34; // [rsp+90h] [rbp-70h]
  __int64 v35; // [rsp+98h] [rbp-68h]
  _DWORD v36[52]; // [rsp+A0h] [rbp-60h] BYREF

  v34 = a4;
  v35 = a3;
  v33 = a6;
  *a10 = 0;
  v25 = a5;
  v31 = a7;
  v32 = a8;
  result = CompatibilityMarkupProcessorImpl::ProcessAttributes(a1, a2, &v25, &v31, &v32, 1);
  if ( (int)result >= 0 )
  {
    v30 = 0;
    v13 = v25;
    if ( v25 != a5 )
    {
      NCoreLibrary::TGenericSP<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25>,NCoreLibrary::TAutoPtr<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25>>,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> *,0,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> const *>::Reset(&v30);
      v30 = v13;
    }
    v29 = 0;
    v14 = v31;
    if ( v31 != a7 )
    {
      NCoreLibrary::TGenericSP<CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25>,NCoreLibrary::TAutoPtr<CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25>>,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> *,0,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> const *>::Reset(&v29);
      v29 = v14;
    }
    v28 = 0;
    v15 = v32;
    if ( v32 != a8 )
    {
      NCoreLibrary::TGenericSP<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25>,NCoreLibrary::TAutoPtr<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25>>,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25> *,0,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25> const *>::Reset(&v28);
      v28 = v15;
    }
    v24 = 0;
    v16 = (*(__int64 (__fastcall **)(__int64, struct IXMLDOMNamedNodeMap **))(*(_QWORD *)a2 + 136LL))(a2, &v24);
    if ( v16 < 0 )
      goto LABEL_30;
    v27 = 0;
    v17 = ((__int64 (__fastcall *)(struct IXMLDOMNamedNodeMap *, _QWORD, const OLECHAR *, void (__fastcall ****)(_QWORD, GUID *, _QWORD *)))v24->lpVtbl->getQualifiedItem)(
            v24,
            a1[36],
            &word_1800884E0,
            &v27);
    v16 = v17;
    if ( v17 >= 0 )
    {
      if ( v17 == 1 )
      {
        v16 = -2147221490;
      }
      else
      {
        bstrString = 0;
        v16 = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD, GUID *, _QWORD *), BSTR *))(*v27)[26])(
                v27,
                &bstrString);
        if ( v16 >= 0 )
        {
          v18 = -1;
          do
            ++v18;
          while ( bstrString[v18] );
          if ( !v18 )
          {
            SysFreeString(bstrString);
            v16 = -2147221489;
            goto LABEL_29;
          }
          CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25>::Vector<ATL::CComBSTR,25>(v36);
          v16 = CompatibilityMarkupProcessorImpl::ParseNamespaceListFromString(v19, bstrString, v25, v36);
          if ( v16 < 0
            || !a9
            && CompatibilityMarkupProcessorImpl::AllNamespacesAreUnderstood((__int64)a1, (__int64)v36)
            && (*a10 = 1,
                v16 = CompatibilityMarkupProcessorImpl::HoistChildren(v20, a2, v35, v34, (__int64)v25, v33),
                v16 < 0) )
          {
            `eh vector destructor iterator'((char *)v36, 8, 25, (void (__fastcall *)(char *))ATL::CComBSTR::~CComBSTR);
          }
          else
          {
            ATL::CComQIPtr<IXMLDOMAttribute,&__s_GUID const _GUID_2933bf85_7b36_11d2_b20e_00c04f983e60>::CComQIPtr<IXMLDOMAttribute,&__s_GUID const _GUID_2933bf85_7b36_11d2_b20e_00c04f983e60>(
              &v23,
              v27);
            if ( !v23 )
            {
              ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v23);
              `eh vector destructor iterator'((char *)v36, 8, 25, (void (__fastcall *)(char *))ATL::CComBSTR::~CComBSTR);
              SysFreeString(bstrString);
              v16 = -2147467262;
              goto LABEL_29;
            }
            v26 = 0;
            v16 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)a2 + 392LL))(a2, v23, &v26);
            if ( v16 >= 0 )
            {
              v16 = CompatibilityMarkupProcessorImpl::CheckRemainingAttributes(v21, v24);
              if ( v16 >= 0 )
              {
                ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v26);
                ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v23);
                `eh vector destructor iterator'(
                  (char *)v36,
                  8,
                  25,
                  (void (__fastcall *)(char *))ATL::CComBSTR::~CComBSTR);
                SysFreeString(bstrString);
                v16 = 0;
                goto LABEL_29;
              }
            }
            ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v26);
            ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v23);
            `eh vector destructor iterator'((char *)v36, 8, 25, (void (__fastcall *)(char *))ATL::CComBSTR::~CComBSTR);
          }
        }
        SysFreeString(bstrString);
      }
    }
LABEL_29:
    ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&v27);
LABEL_30:
    ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&v24);
    NCoreLibrary::TGenericSP<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25>,NCoreLibrary::TAutoPtr<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25>>,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25> *,0,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25> const *>::Reset(&v28);
    NCoreLibrary::TGenericSP<CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25>,NCoreLibrary::TAutoPtr<CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25>>,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> *,0,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> const *>::Reset(&v29);
    NCoreLibrary::TGenericSP<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25>,NCoreLibrary::TAutoPtr<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25>>,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> *,0,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> const *>::Reset(&v30);
    return (unsigned int)v16;
  }
  return result;
}

```

## disassembly

```asm
0x18002b4f4  push    rbp
0x18002b4f6  push    rbx
0x18002b4f7  push    rsi
0x18002b4f8  push    rdi
0x18002b4f9  push    r12
0x18002b4fb  push    r13
0x18002b4fd  push    r14
0x18002b4ff  push    r15
0x18002b501  lea     rbp, [rsp-88h]
0x18002b509  sub     rsp, 188h
0x18002b510  mov     rax, cs:__security_cookie
0x18002b517  xor     rax, rsp
0x18002b51a  mov     [rbp+0C0h+var_50], rax
0x18002b51e  mov     [rbp+0C0h+var_130], r9
0x18002b522  mov     [rbp+0C0h+var_128], r8
0x18002b526  mov     rdi, rdx
0x18002b529  mov     r13, rcx
0x18002b52c  mov     rsi, [rbp+0C0h+arg_20]
0x18002b533  mov     rax, [rbp+0C0h+arg_28]
0x18002b53a  mov     [rbp+0C0h+var_138], rax
0x18002b53e  mov     r14, [rbp+0C0h+arg_30]
0x18002b545  mov     r15, [rbp+0C0h+arg_38]
0x18002b54c  mov     r12, [rbp+0C0h+arg_48]
0x18002b553  mov     byte ptr [r12], 0
0x18002b558  mov     [rsp+1C0h+var_178], rsi
0x18002b55d  mov     [rsp+1C0h+var_148], r14
0x18002b562  mov     [rbp+0C0h+var_140], r15
0x18002b566  mov     byte ptr [rsp+1C0h+var_198], 1
0x18002b56b  lea     rax, [rbp+0C0h+var_140]
0x18002b56f  mov     [rsp+1C0h+var_1A0], rax
0x18002b574  lea     r9, [rsp+1C0h+var_148]
0x18002b579  lea     r8, [rsp+1C0h+var_178]
0x18002b57e  call    ?ProcessAttributes@CompatibilityMarkupProcessorImpl@@AEAAJPEAUIXMLDOMElement@@PEAPEAU?$Map@VCComBSTR@ATL@@V12@$0BJ@@1@PEAPEAU?$Vector@VCComBSTR@ATL@@$0BJ@@1@PEAPEAU?$Map@VCComBSTR@ATL@@U?$Vector@VCComBSTR@ATL@@$0DC@@CompatibilityMarkupProcessorImpl@@$0BJ@@1@_N@Z; CompatibilityMarkupProcessorImpl::ProcessAttributes(IXMLDOMElement *,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> * *,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> * *,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25> * *,bool)
0x18002b583  test    eax, eax
0x18002b585  js      loc_18002B8B2
0x18002b58b  mov     [rsp+1C0h+var_150], 0
0x18002b594  mov     rbx, [rsp+1C0h+var_178]
0x18002b599  cmp     rbx, rsi
0x18002b59c  jz      short loc_18002B5AD
0x18002b59e  lea     rcx, [rsp+1C0h+var_150]
0x18002b5a3  call    ?Reset@?$TGenericSP@U?$Map@VCComBSTR@ATL@@V12@$0BJ@@CompatibilityMarkupProcessorImpl@@V?$TAutoPtr@U?$Map@VCComBSTR@ATL@@V12@$0BJ@@CompatibilityMarkupProcessorImpl@@@NCoreLibrary@@PEAU12@$0A@PEBU12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25>,NCoreLibrary::TAutoPtr<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25>>,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> *,0,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> const *>::Reset(void)
0x18002b5a8  mov     [rsp+1C0h+var_150], rbx
0x18002b5ad  xor     esi, esi
0x18002b5af  mov     [rsp+1C0h+var_158], rsi
0x18002b5b4  mov     rbx, [rsp+1C0h+var_148]
0x18002b5b9  cmp     rbx, r14
0x18002b5bc  jz      short loc_18002B5CD
0x18002b5be  lea     rcx, [rsp+1C0h+var_158]
0x18002b5c3  call    ?Reset@?$TGenericSP@U?$Vector@VCComBSTR@ATL@@$0BJ@@CompatibilityMarkupProcessorImpl@@V?$TAutoPtr@U?$Vector@VCComBSTR@ATL@@$0BJ@@CompatibilityMarkupProcessorImpl@@@NCoreLibrary@@PEAU12@$0A@PEBU12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25>,NCoreLibrary::TAutoPtr<CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25>>,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> *,0,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> const *>::Reset(void)
0x18002b5c8  mov     [rsp+1C0h+var_158], rbx
0x18002b5cd  mov     [rsp+1C0h+var_160], rsi
0x18002b5d2  mov     rbx, [rbp+0C0h+var_140]
0x18002b5d6  cmp     rbx, r15
0x18002b5d9  jz      short loc_18002B5EA
0x18002b5db  lea     rcx, [rsp+1C0h+var_160]
0x18002b5e0  call    ?Reset@?$TGenericSP@U?$Map@VCComBSTR@ATL@@U?$Vector@VCComBSTR@ATL@@$0DC@@CompatibilityMarkupProcessorImpl@@$0BJ@@CompatibilityMarkupProcessorImpl@@V?$TAutoPtr@U?$Map@VCComBSTR@ATL@@U?$Vector@VCComBSTR@ATL@@$0DC@@CompatibilityMarkupProcessorImpl@@$0BJ@@CompatibilityMarkupProcessorImpl@@@NCoreLibrary@@PEAU12@$0A@PEBU12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25>,NCoreLibrary::TAutoPtr<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25>>,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25> *,0,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25> const *>::Reset(void)
0x18002b5e5  mov     [rsp+1C0h+var_160], rbx
0x18002b5ea  mov     [rsp+1C0h+var_180], rsi
0x18002b5ef  mov     rax, [rdi]
0x18002b5f2  lea     rdx, [rsp+1C0h+var_180]
0x18002b5f7  mov     rcx, rdi
0x18002b5fa  mov     rax, [rax+88h]
0x18002b601  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b606  mov     ebx, eax
0x18002b608  test    eax, eax
0x18002b60a  js      loc_18002B885
0x18002b610  mov     [rsp+1C0h+var_168], rsi
0x18002b615  mov     rcx, [rsp+1C0h+var_180]
0x18002b61a  mov     rax, [rcx]
0x18002b61d  lea     r9, [rsp+1C0h+var_168]
0x18002b622  lea     r8, word_1800884E0
0x18002b629  mov     rdx, [r13+120h]
0x18002b630  mov     rax, [rax+60h]
0x18002b634  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b639  mov     ebx, eax
0x18002b63b  test    eax, eax
0x18002b63d  js      loc_18002B87A
0x18002b643  cmp     eax, 1
0x18002b646  jnz     short loc_18002B652
0x18002b648  mov     ebx, 8004000Eh
0x18002b64d  jmp     loc_18002B87A
0x18002b652  mov     [rsp+1C0h+bstrString], rsi
0x18002b657  mov     rcx, [rsp+1C0h+var_168]
0x18002b65c  mov     rax, [rcx]
0x18002b65f  lea     rdx, [rsp+1C0h+bstrString]
0x18002b664  mov     rax, [rax+0D0h]
0x18002b66b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b670  mov     ebx, eax
0x18002b672  test    eax, eax
0x18002b674  jns     short loc_18002B686
0x18002b676  mov     rcx, [rsp+1C0h+bstrString]; bstrString
0x18002b67b  call    cs:__imp_SysFreeString
0x18002b681  jmp     loc_18002B87A
0x18002b686  mov     rcx, [rsp+1C0h+bstrString]; bstrString
0x18002b68b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002b68f  inc     rax
0x18002b692  cmp     [rcx+rax*2], si
0x18002b696  jnz     short loc_18002B68F
0x18002b698  test    rax, rax
0x18002b69b  jnz     short loc_18002B6AD
0x18002b69d  call    cs:__imp_SysFreeString
0x18002b6a3  mov     ebx, 8004000Fh
0x18002b6a8  jmp     loc_18002B87A
0x18002b6ad  lea     rcx, [rbp+0C0h+var_120]
0x18002b6b1  call    ??0?$Vector@VCComBSTR@ATL@@$0BJ@@CompatibilityMarkupProcessorImpl@@QEAA@XZ; CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25>::Vector<ATL::CComBSTR,25>(void)
0x18002b6b6  nop
0x18002b6b7  lea     r9, [rbp+0C0h+var_120]
0x18002b6bb  mov     r8, [rsp+1C0h+var_178]
0x18002b6c0  mov     rdx, [rsp+1C0h+bstrString]
0x18002b6c5  call    ?ParseNamespaceListFromString@CompatibilityMarkupProcessorImpl@@AEAAJPEBGPEBU?$Map@VCComBSTR@ATL@@V12@$0BJ@@1@PEAU?$Vector@VCComBSTR@ATL@@$0BJ@@1@@Z; CompatibilityMarkupProcessorImpl::ParseNamespaceListFromString(ushort const *,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> const *,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> *)
0x18002b6ca  mov     ebx, eax
0x18002b6cc  test    eax, eax
0x18002b6ce  jns     short loc_18002B6EC
0x18002b6d0  lea     r9, ??1CComBSTR@ATL@@QEAA@XZ; void (*)(void *)
0x18002b6d7  mov     edx, 8; unsigned __int64
0x18002b6dc  lea     r8d, [rdx+11h]; unsigned __int64
0x18002b6e0  lea     rcx, [rbp+0C0h+var_120]; void *
0x18002b6e4  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18002b6e9  nop
0x18002b6ea  jmp     short loc_18002B676
0x18002b6ec  cmp     [rbp+0C0h+arg_40], sil
0x18002b6f3  jnz     short loc_18002B752
0x18002b6f5  lea     rdx, [rbp+0C0h+var_120]
0x18002b6f9  mov     rcx, r13
0x18002b6fc  call    ?AllNamespacesAreUnderstood@CompatibilityMarkupProcessorImpl@@AEAA_NPEBU?$Vector@VCComBSTR@ATL@@$0BJ@@1@@Z; CompatibilityMarkupProcessorImpl::AllNamespacesAreUnderstood(CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> const *)
0x18002b701  test    al, al
0x18002b703  jz      short loc_18002B752
0x18002b705  mov     byte ptr [r12], 1
0x18002b70a  mov     rax, [rbp+0C0h+var_138]
0x18002b70e  mov     [rsp+1C0h+var_198], rax
0x18002b713  mov     rax, [rsp+1C0h+var_178]
0x18002b718  mov     [rsp+1C0h+var_1A0], rax
0x18002b71d  mov     r9, [rbp+0C0h+var_130]
0x18002b721  mov     r8, [rbp+0C0h+var_128]
0x18002b725  mov     rdx, rdi
0x18002b728  call    ?HoistChildren@CompatibilityMarkupProcessorImpl@@AEAAJPEAUIXMLDOMElement@@PEAUIXMLDOMNode@@1PEBU?$Map@VCComBSTR@ATL@@V12@$0BJ@@1@2@Z; CompatibilityMarkupProcessorImpl::HoistChildren(IXMLDOMElement *,IXMLDOMNode *,IXMLDOMNode *,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> const *,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> const *)
0x18002b72d  mov     ebx, eax
0x18002b72f  test    eax, eax
0x18002b731  jns     short loc_18002B752
0x18002b733  lea     r9, ??1CComBSTR@ATL@@QEAA@XZ; void (*)(void *)
0x18002b73a  mov     edx, 8; unsigned __int64
0x18002b73f  lea     r8d, [rdx+11h]; unsigned __int64
0x18002b743  lea     rcx, [rbp+0C0h+var_120]; void *
0x18002b747  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18002b74c  nop
0x18002b74d  jmp     loc_18002B676
0x18002b752  mov     rdx, [rsp+1C0h+var_168]
0x18002b757  lea     rcx, [rsp+1C0h+var_188]
0x18002b75c  call    ??0?$CComQIPtr@UIXMLDOMAttribute@@$1?_GUID_2933bf85_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IXMLDOMAttribute,&__s_GUID const _GUID_2933bf85_7b36_11d2_b20e_00c04f983e60>::CComQIPtr<IXMLDOMAttribute,&__s_GUID const _GUID_2933bf85_7b36_11d2_b20e_00c04f983e60>(IUnknown *)
0x18002b761  nop
0x18002b762  mov     rdx, [rsp+1C0h+var_188]
0x18002b767  test    rdx, rdx
0x18002b76a  jnz     short loc_18002B7A6
0x18002b76c  lea     rcx, [rsp+1C0h+var_188]
0x18002b771  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18002b776  nop
0x18002b777  lea     r9, ??1CComBSTR@ATL@@QEAA@XZ; void (*)(void *)
0x18002b77e  mov     edx, 8; unsigned __int64
0x18002b783  lea     r8d, [rdx+11h]; unsigned __int64
0x18002b787  lea     rcx, [rbp+0C0h+var_120]; void *
0x18002b78b  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18002b790  nop
0x18002b791  mov     rcx, [rsp+1C0h+bstrString]; bstrString
0x18002b796  call    cs:__imp_SysFreeString
0x18002b79c  mov     ebx, 80004002h
0x18002b7a1  jmp     loc_18002B87A
0x18002b7a6  mov     [rsp+1C0h+var_170], rsi
0x18002b7ab  mov     rax, [rdi]
0x18002b7ae  lea     r8, [rsp+1C0h+var_170]
0x18002b7b3  mov     rcx, rdi
0x18002b7b6  mov     rax, [rax+188h]
0x18002b7bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b7c2  mov     ebx, eax
0x18002b7c4  test    eax, eax
0x18002b7c6  jns     short loc_18002B7FD
0x18002b7c8  lea     rcx, [rsp+1C0h+var_170]
0x18002b7cd  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18002b7d2  nop
0x18002b7d3  lea     rcx, [rsp+1C0h+var_188]
0x18002b7d8  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18002b7dd  nop
0x18002b7de  lea     r9, ??1CComBSTR@ATL@@QEAA@XZ; void (*)(void *)
0x18002b7e5  mov     edx, 8; unsigned __int64
0x18002b7ea  lea     r8d, [rdx+11h]; unsigned __int64
0x18002b7ee  lea     rcx, [rbp+0C0h+var_120]; void *
0x18002b7f2  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18002b7f7  nop
0x18002b7f8  jmp     loc_18002B676
0x18002b7fd  mov     rdx, [rsp+1C0h+var_180]; struct IXMLDOMNamedNodeMap *
0x18002b802  call    ?CheckRemainingAttributes@CompatibilityMarkupProcessorImpl@@AEAAJPEAUIXMLDOMNamedNodeMap@@@Z; CompatibilityMarkupProcessorImpl::CheckRemainingAttributes(IXMLDOMNamedNodeMap *)
0x18002b807  mov     ebx, eax
0x18002b809  lea     rcx, [rsp+1C0h+var_170]
0x18002b80e  test    eax, eax
0x18002b810  jns     short loc_18002B842
0x18002b812  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18002b817  nop
0x18002b818  lea     rcx, [rsp+1C0h+var_188]
0x18002b81d  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18002b822  nop
0x18002b823  lea     r9, ??1CComBSTR@ATL@@QEAA@XZ; void (*)(void *)
0x18002b82a  mov     edx, 8; unsigned __int64
0x18002b82f  lea     r8d, [rdx+11h]; unsigned __int64
0x18002b833  lea     rcx, [rbp+0C0h+var_120]; void *
0x18002b837  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18002b83c  nop
0x18002b83d  jmp     loc_18002B676
0x18002b842  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18002b847  nop
0x18002b848  lea     rcx, [rsp+1C0h+var_188]
0x18002b84d  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18002b852  nop
0x18002b853  lea     r9, ??1CComBSTR@ATL@@QEAA@XZ; void (*)(void *)
0x18002b85a  mov     edx, 8; unsigned __int64
0x18002b85f  lea     r8d, [rdx+11h]; unsigned __int64
0x18002b863  lea     rcx, [rbp+0C0h+var_120]; void *
0x18002b867  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18002b86c  nop
0x18002b86d  mov     rcx, [rsp+1C0h+bstrString]; bstrString
0x18002b872  call    cs:__imp_SysFreeString
0x18002b878  mov     ebx, esi
0x18002b87a  lea     rcx, [rsp+1C0h+var_168]
0x18002b87f  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18002b884  nop
0x18002b885  lea     rcx, [rsp+1C0h+var_180]
0x18002b88a  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18002b88f  nop
0x18002b890  lea     rcx, [rsp+1C0h+var_160]
0x18002b895  call    ?Reset@?$TGenericSP@U?$Map@VCComBSTR@ATL@@U?$Vector@VCComBSTR@ATL@@$0DC@@CompatibilityMarkupProcessorImpl@@$0BJ@@CompatibilityMarkupProcessorImpl@@V?$TAutoPtr@U?$Map@VCComBSTR@ATL@@U?$Vector@VCComBSTR@ATL@@$0DC@@CompatibilityMarkupProcessorImpl@@$0BJ@@CompatibilityMarkupProcessorImpl@@@NCoreLibrary@@PEAU12@$0A@PEBU12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25>,NCoreLibrary::TAutoPtr<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25>>,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25> *,0,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25> const *>::Reset(void)
0x18002b89a  nop
0x18002b89b  lea     rcx, [rsp+1C0h+var_158]
0x18002b8a0  call    ?Reset@?$TGenericSP@U?$Vector@VCComBSTR@ATL@@$0BJ@@CompatibilityMarkupProcessorImpl@@V?$TAutoPtr@U?$Vector@VCComBSTR@ATL@@$0BJ@@CompatibilityMarkupProcessorImpl@@@NCoreLibrary@@PEAU12@$0A@PEBU12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25>,NCoreLibrary::TAutoPtr<CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25>>,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> *,0,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> const *>::Reset(void)
0x18002b8a5  nop
0x18002b8a6  lea     rcx, [rsp+1C0h+var_150]
0x18002b8ab  call    ?Reset@?$TGenericSP@U?$Map@VCComBSTR@ATL@@V12@$0BJ@@CompatibilityMarkupProcessorImpl@@V?$TAutoPtr@U?$Map@VCComBSTR@ATL@@V12@$0BJ@@CompatibilityMarkupProcessorImpl@@@NCoreLibrary@@PEAU12@$0A@PEBU12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25>,NCoreLibrary::TAutoPtr<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25>>,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> *,0,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> const *>::Reset(void)
0x18002b8b0  mov     eax, ebx
0x18002b8b2  mov     rcx, [rbp+0C0h+var_50]
0x18002b8b6  xor     rcx, rsp; StackCookie
0x18002b8b9  call    __security_check_cookie
0x18002b8be  add     rsp, 188h
0x18002b8c5  pop     r15
0x18002b8c7  pop     r14
0x18002b8c9  pop     r13
0x18002b8cb  pop     r12
0x18002b8cd  pop     rdi
0x18002b8ce  pop     rsi
0x18002b8cf  pop     rbx
0x18002b8d0  pop     rbp
0x18002b8d1  retn
```
