# NPrintTicketUtil::CPrintTicketWrapper::StartDocument(ushort const *,IXMLDOMElement * *)

- ea: `0x180008acc`
- end: `0x180008d9e`
- name: `?StartDocument@CPrintTicketWrapper@NPrintTicketUtil@@AEAAJPEBGPEAPEAUIXMLDOMElement@@@Z`
- size: `722`
- prototype: `__int64 __fastcall(NPrintTicketUtil::CPrintTicketWrapper *__hidden this, const unsigned __int16 *, struct IXMLDOMElement **)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180008848`
- `0x18000ea40`
- `0x18001adb4`

## callees

- `0x1800076e8`
- `0x180008acc`
- `0x180008da4`
- `0x180023010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180008b50`
- `OLEAUT32!__imp_VariantInit` at `0x180008cc0`
- `OLEAUT32!__imp_VariantInit` at `0x180008b50`
- `OLEAUT32!__imp_VariantInit` at `0x180008cc0`
- `OLEAUT32!__imp_VariantClear` at `0x180008ba7`
- `OLEAUT32!__imp_VariantClear` at `0x180008d1f`
- `OLEAUT32!__imp_VariantClear` at `0x180008ba7`
- `OLEAUT32!__imp_VariantClear` at `0x180008d1f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180008b17`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180008b17`

## string_xrefs

- `0x180008b62`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework`
- `0x180008bd5`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework`
- `0x180008d5f`: `http://www.w3.org/2001/XMLSchema`
- `0x180008bdc`: `xmlns:psf`
- `0x180008d42`: `http://www.w3.org/2001/XMLSchema-instance`
- `0x180008d49`: `xmlns:xsi`
- `0x180008d66`: `xmlns:xsd`

## pseudocode

```c
__int64 __fastcall NPrintTicketUtil::CPrintTicketWrapper::StartDocument(
        NPrintTicketUtil::CPrintTicketWrapper *this,
        struct IXMLDOMDocument2 **a2,
        struct IXMLDOMElement **a3)
{
  __int64 **v3; // rsi
  HRESULT DomDocument; // ebx
  __int64 *v7; // rcx
  __int64 v8; // rax
  __int64 (__fastcall *v9)(__int64 *, __int128 *, struct IXMLDOMDocument2 **, const unsigned __int16 *, __int64 *); // rax
  NPrintTicketUtil::CPrintTicketWrapper *v10; // rcx
  __int64 *v11; // rcx
  __int64 *v12; // rcx
  __int64 v13; // rax
  void (__fastcall *v14)(__int64 *, struct IXMLDOMElement *, __int128 *, _QWORD); // rax
  NPrintTicketUtil::CPrintTicketWrapper *v15; // rcx
  NPrintTicketUtil::CPrintTicketWrapper *v16; // rcx
  NPrintTicketUtil::CPrintTicketWrapper *v17; // rcx
  VARIANTARG pvarg; // [rsp+30h] [rbp-40h] BYREF
  __int128 v20; // [rsp+50h] [rbp-20h] BYREF
  IRecordInfo *pRecInfo; // [rsp+60h] [rbp-10h]
  __int64 v22; // [rsp+A0h] [rbp+30h] BYREF
  struct IXMLDOMElement *v23; // [rsp+B0h] [rbp+40h] BYREF
  __int64 v24; // [rsp+B8h] [rbp+48h] BYREF

  v23 = (struct IXMLDOMElement *)a3;
  v3 = (__int64 **)((char *)this + 8);
  DomDocument = NPrintTicketUtil::CreateDomDocument((LPVOID *)this + 1, a2);
  if ( DomDocument >= 0 )
  {
    DomDocument = CoCreateInstance(&CLSID_MXNamespaceManager60, 0, 1u, &IID_IMXNamespaceManager, (LPVOID *)this + 2);
    if ( DomDocument >= 0 )
    {
      v24 = 0;
      v22 = 0;
      memset(&pvarg, 0, sizeof(pvarg));
      v23 = 0;
      VariantInit(&pvarg);
      v7 = *v3;
      pvarg.lVal = 1;
      pvarg.vt = 3;
      v8 = *v7;
      pRecInfo = pvarg.pRecInfo;
      v9 = *(__int64 (__fastcall **)(__int64 *, __int128 *, struct IXMLDOMDocument2 **, const unsigned __int16 *, __int64 *))(v8 + 448);
      v20 = *(_OWORD *)&pvarg.vt;
      DomDocument = v9(
                      v7,
                      &v20,
                      a2,
                      L"http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework",
                      &v24);
      VariantClear(&pvarg);
      if ( DomDocument >= 0 )
      {
        DomDocument = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IXMLDOMElement **))v24)(
                        v24,
                        &IID_IXMLDOMElement,
                        &v23);
        if ( DomDocument >= 0 )
        {
          DomDocument = NPrintTicketUtil::CPrintTicketWrapper::CreateXMLAttribute(
                          v10,
                          v23,
                          L"xmlns:psf",
                          L"http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework");
          if ( DomDocument >= 0 )
          {
            DomDocument = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(**v3 + 168))(*v3, v24, &v22);
            if ( DomDocument >= 0 )
              DomDocument = (**(__int64 (__fastcall ***)(__int64, GUID *, char *))v22)(
                              v22,
                              &IID_IXMLDOMElement,
                              (char *)this + 24);
          }
        }
      }
      if ( v23 )
      {
        ((void (__fastcall *)(struct IXMLDOMElement *))v23->lpVtbl->Release)(v23);
        v23 = 0;
      }
      if ( v22 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
        v22 = 0;
      }
      if ( v24 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      if ( DomDocument >= 0 )
      {
        v11 = *v3;
        v23 = 0;
        memset(&pvarg, 0, sizeof(pvarg));
        DomDocument = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, const wchar_t *, struct IXMLDOMElement **))(*v11 + 416))(
                        v11,
                        L"xml",
                        L"version=\"1.0\" encoding=\"UTF-8\"",
                        &v23);
        VariantInit(&pvarg);
        if ( DomDocument >= 0 )
        {
          DomDocument = (*(__int64 (__fastcall **)(__int64 *, CY *))(**v3 + 104))(*v3, &pvarg.cyVal);
          if ( DomDocument >= 0 )
          {
            v12 = *v3;
            pvarg.vt = 13;
            v13 = *v12;
            pRecInfo = pvarg.pRecInfo;
            v14 = *(void (__fastcall **)(__int64 *, struct IXMLDOMElement *, __int128 *, _QWORD))(v13 + 144);
            v20 = *(_OWORD *)&pvarg.vt;
            v14(v12, v23, &v20, 0);
          }
        }
        VariantClear(&pvarg);
        v15 = (NPrintTicketUtil::CPrintTicketWrapper *)v23;
        if ( v23 )
          ((void (__fastcall *)(struct IXMLDOMElement *))v23->lpVtbl->Release)(v23);
        if ( DomDocument >= 0 )
        {
          DomDocument = NPrintTicketUtil::CPrintTicketWrapper::CreateXMLAttribute(
                          v15,
                          *((struct IXMLDOMElement **)this + 3),
                          L"xmlns:xsi",
                          L"http://www.w3.org/2001/XMLSchema-instance");
          if ( DomDocument >= 0 )
          {
            DomDocument = NPrintTicketUtil::CPrintTicketWrapper::CreateXMLAttribute(
                            v16,
                            *((struct IXMLDOMElement **)this + 3),
                            L"xmlns:xsd",
                            L"http://www.w3.org/2001/XMLSchema");
            if ( DomDocument >= 0 )
              return (unsigned int)NPrintTicketUtil::CPrintTicketWrapper::CreateXMLAttribute(
                                     v17,
                                     *((struct IXMLDOMElement **)this + 3),
                                     L"version",
                                     L"1");
          }
        }
      }
    }
  }
  return (unsigned int)DomDocument;
}

```

## disassembly

```asm
0x180008acc  mov     [rsp-28h+arg_10], r8
0x180008ad1  push    rbp
0x180008ad2  push    rbx
0x180008ad3  push    rsi
0x180008ad4  push    rdi
0x180008ad5  push    r14
0x180008ad7  mov     rbp, rsp
0x180008ada  sub     rsp, 70h
0x180008ade  lea     rsi, [rcx+8]
0x180008ae2  mov     rdi, rcx
0x180008ae5  mov     rcx, rsi; ppv
0x180008ae8  mov     r14, rdx
0x180008aeb  call    ?CreateDomDocument@NPrintTicketUtil@@YAJPEAPEAUIXMLDOMDocument2@@@Z; NPrintTicketUtil::CreateDomDocument(IXMLDOMDocument2 * *)
0x180008af0  mov     ebx, eax
0x180008af2  test    eax, eax
0x180008af4  js      loc_180008D91
0x180008afa  xor     edx, edx; pUnkOuter
0x180008afc  lea     rax, [rdi+10h]
0x180008b00  lea     r9, IID_IMXNamespaceManager; riid
0x180008b07  mov     [rsp+70h+ppv], rax; ppv
0x180008b0c  lea     rcx, CLSID_MXNamespaceManager60; rclsid
0x180008b13  lea     r8d, [rdx+1]; dwClsContext
0x180008b17  call    cs:__imp_CoCreateInstance
0x180008b1d  mov     ebx, eax
0x180008b1f  test    eax, eax
0x180008b21  js      loc_180008D91
0x180008b27  xorps   xmm0, xmm0
0x180008b2a  mov     [rbp+arg_18], 0
0x180008b32  xor     eax, eax
0x180008b34  mov     [rbp+arg_0], 0
0x180008b3c  lea     rcx, [rbp+pvarg]; pvarg
0x180008b40  mov     qword ptr [rbp+pvarg+10h], rax
0x180008b44  movups  xmmword ptr [rbp+pvarg], xmm0
0x180008b48  mov     [rbp+arg_10], 0
0x180008b50  call    cs:__imp_VariantInit
0x180008b56  mov     rcx, [rsi]
0x180008b59  lea     rdx, [rbp+arg_18]
0x180008b5d  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x180008b62  lea     r9, aHttpSchemasMic_0; "http://schemas.microsoft.com/windows/20"...
0x180008b69  mov     dword ptr [rbp+pvarg+8], 1
0x180008b70  mov     eax, 3
0x180008b75  mov     word ptr [rbp+pvarg], ax
0x180008b79  mov     r8, r14
0x180008b7c  mov     rax, [rcx]
0x180008b7f  movups  xmm0, xmmword ptr [rbp+pvarg]
0x180008b83  mov     [rsp+70h+ppv], rdx
0x180008b88  lea     rdx, [rbp+var_20]
0x180008b8c  movsd   [rbp+var_10], xmm1
0x180008b91  mov     rax, [rax+1C0h]
0x180008b98  movaps  [rbp+var_20], xmm0
0x180008b9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ba1  lea     rcx, [rbp+pvarg]; pvarg
0x180008ba5  mov     ebx, eax
0x180008ba7  call    cs:__imp_VariantClear
0x180008bad  test    ebx, ebx
0x180008baf  js      short loc_180008C2A
0x180008bb1  mov     rcx, [rbp+arg_18]
0x180008bb5  lea     r8, [rbp+arg_10]
0x180008bb9  lea     rdx, IID_IXMLDOMElement
0x180008bc0  mov     rax, [rcx]
0x180008bc3  mov     rax, [rax]
0x180008bc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bcb  mov     ebx, eax
0x180008bcd  test    eax, eax
0x180008bcf  js      short loc_180008C2A
0x180008bd1  mov     rdx, [rbp+arg_10]; struct IXMLDOMElement *
0x180008bd5  lea     r9, aHttpSchemasMic_0; "http://schemas.microsoft.com/windows/20"...
0x180008bdc  lea     r8, aXmlnsPsf; "xmlns:psf"
0x180008be3  call    ?CreateXMLAttribute@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateXMLAttribute(IXMLDOMElement *,ushort const *,ushort const *)
0x180008be8  mov     ebx, eax
0x180008bea  test    eax, eax
0x180008bec  js      short loc_180008C2A
0x180008bee  mov     rcx, [rsi]
0x180008bf1  lea     r8, [rbp+arg_0]
0x180008bf5  mov     rdx, [rbp+arg_18]
0x180008bf9  mov     rax, [rcx]
0x180008bfc  mov     rax, [rax+0A8h]
0x180008c03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c08  mov     ebx, eax
0x180008c0a  test    eax, eax
0x180008c0c  js      short loc_180008C2A
0x180008c0e  mov     rcx, [rbp+arg_0]
0x180008c12  lea     r8, [rdi+18h]
0x180008c16  lea     rdx, IID_IXMLDOMElement
0x180008c1d  mov     rax, [rcx]
0x180008c20  mov     rax, [rax]
0x180008c23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c28  mov     ebx, eax
0x180008c2a  mov     rcx, [rbp+arg_10]
0x180008c2e  test    rcx, rcx
0x180008c31  jz      short loc_180008C47
0x180008c33  mov     rax, [rcx]
0x180008c36  mov     rax, [rax+10h]
0x180008c3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c3f  mov     [rbp+arg_10], 0
0x180008c47  mov     rcx, [rbp+arg_0]
0x180008c4b  test    rcx, rcx
0x180008c4e  jz      short loc_180008C64
0x180008c50  mov     rax, [rcx]
0x180008c53  mov     rax, [rax+10h]
0x180008c57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c5c  mov     [rbp+arg_0], 0
0x180008c64  mov     rcx, [rbp+arg_18]
0x180008c68  test    rcx, rcx
0x180008c6b  jz      short loc_180008C79
0x180008c6d  mov     rax, [rcx]
0x180008c70  mov     rax, [rax+10h]
0x180008c74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c79  test    ebx, ebx
0x180008c7b  js      loc_180008D91
0x180008c81  mov     rcx, [rsi]
0x180008c84  lea     r9, [rbp+arg_10]
0x180008c88  xor     eax, eax
0x180008c8a  mov     [rbp+arg_10], 0
0x180008c92  mov     qword ptr [rbp+pvarg+10h], rax
0x180008c96  lea     r8, aVersion10Encod; "version=\"1.0\" encoding=\"UTF-8\""
0x180008c9d  xorps   xmm0, xmm0
0x180008ca0  lea     rdx, aXml; "xml"
0x180008ca7  movups  xmmword ptr [rbp+pvarg], xmm0
0x180008cab  mov     rax, [rcx]
0x180008cae  mov     rax, [rax+1A0h]
0x180008cb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cba  lea     rcx, [rbp+pvarg]; pvarg
0x180008cbe  mov     ebx, eax
0x180008cc0  call    cs:__imp_VariantInit
0x180008cc6  test    ebx, ebx
0x180008cc8  js      short loc_180008D1B
0x180008cca  mov     rcx, [rsi]
0x180008ccd  lea     rdx, [rbp+pvarg+8]
0x180008cd1  mov     rax, [rcx]
0x180008cd4  mov     rax, [rax+68h]
0x180008cd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cdd  mov     ebx, eax
0x180008cdf  test    eax, eax
0x180008ce1  js      short loc_180008D1B
0x180008ce3  mov     rcx, [rsi]
0x180008ce6  lea     r8, [rbp+var_20]
0x180008cea  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x180008cef  mov     eax, 0Dh
0x180008cf4  mov     rdx, [rbp+arg_10]
0x180008cf8  xor     r9d, r9d
0x180008cfb  mov     word ptr [rbp+pvarg], ax
0x180008cff  mov     rax, [rcx]
0x180008d02  movups  xmm0, xmmword ptr [rbp+pvarg]
0x180008d06  movsd   [rbp+var_10], xmm1
0x180008d0b  mov     rax, [rax+90h]
0x180008d12  movaps  [rbp+var_20], xmm0
0x180008d16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d1b  lea     rcx, [rbp+pvarg]; pvarg
0x180008d1f  call    cs:__imp_VariantClear
0x180008d25  mov     rcx, [rbp+arg_10]
0x180008d29  test    rcx, rcx
0x180008d2c  jz      short loc_180008D3A
0x180008d2e  mov     rax, [rcx]
0x180008d31  mov     rax, [rax+10h]
0x180008d35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d3a  test    ebx, ebx
0x180008d3c  js      short loc_180008D91
0x180008d3e  mov     rdx, [rdi+18h]; struct IXMLDOMElement *
0x180008d42  lea     r9, aHttpWwwW3Org20_0; "http://www.w3.org/2001/XMLSchema-instan"...
0x180008d49  lea     r8, aXmlnsXsi; "xmlns:xsi"
0x180008d50  call    ?CreateXMLAttribute@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateXMLAttribute(IXMLDOMElement *,ushort const *,ushort const *)
0x180008d55  mov     ebx, eax
0x180008d57  test    eax, eax
0x180008d59  js      short loc_180008D91
0x180008d5b  mov     rdx, [rdi+18h]; struct IXMLDOMElement *
0x180008d5f  lea     r9, aHttpWwwW3Org20; "http://www.w3.org/2001/XMLSchema"
0x180008d66  lea     r8, aXmlnsXsd; "xmlns:xsd"
0x180008d6d  call    ?CreateXMLAttribute@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateXMLAttribute(IXMLDOMElement *,ushort const *,ushort const *)
0x180008d72  mov     ebx, eax
0x180008d74  test    eax, eax
0x180008d76  js      short loc_180008D91
0x180008d78  mov     rdx, [rdi+18h]; struct IXMLDOMElement *
0x180008d7c  lea     r9, a1; "1"
0x180008d83  lea     r8, aVersion; "version"
0x180008d8a  call    ?CreateXMLAttribute@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateXMLAttribute(IXMLDOMElement *,ushort const *,ushort const *)
0x180008d8f  mov     ebx, eax
0x180008d91  mov     eax, ebx
0x180008d93  add     rsp, 70h
0x180008d97  pop     r14
0x180008d99  pop     rdi
0x180008d9a  pop     rsi
0x180008d9b  pop     rbx
0x180008d9c  pop     rbp
0x180008d9d  retn
```
