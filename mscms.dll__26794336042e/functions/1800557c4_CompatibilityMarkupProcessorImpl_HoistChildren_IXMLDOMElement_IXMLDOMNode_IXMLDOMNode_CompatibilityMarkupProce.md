# CompatibilityMarkupProcessorImpl::HoistChildren(IXMLDOMElement *,IXMLDOMNode *,IXMLDOMNode *,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> const *,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> const *)

- ea: `0x1800557c4`
- end: `0x180055c10`
- name: `?HoistChildren@CompatibilityMarkupProcessorImpl@@AEAAJPEAUIXMLDOMElement@@PEAUIXMLDOMNode@@1PEBU?$Map@VCComBSTR@ATL@@V12@$0BJ@@1@2@Z`
- size: `1100`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002b4f4`
- `0x180056800`
- `0x18005695c`

## callees

- `0x1800127cc`
- `0x18001e34c`
- `0x180020210`
- `0x18002e5f0`
- `0x18002eac0`
- `0x1800552a0`
- `0x18005557c`
- `0x1800557c4`
- `0x180084010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180055a27`
- `OLEAUT32!__imp_VariantClear` at `0x180055a27`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CompatibilityMarkupProcessorImpl::HoistChildren(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        LONGLONG a4,
        __int64 a5,
        __int64 a6)
{
  int v8; // esi
  int v10; // ebx
  __int64 v11; // rcx
  int i; // ebx
  unsigned __int16 *v13; // rcx
  __int64 *v14; // rcx
  __int64 (__fastcall *v15)(__int64, void (__fastcall ***)(_QWORD, GUID *, _QWORD *), VARIANTARG *, __int64 *); // rsi
  void (__fastcall ***v16)(_QWORD, GUID *, _QWORD *); // [rsp+30h] [rbp-D0h] BYREF
  __int64 v17; // [rsp+38h] [rbp-C8h] BYREF
  int v18; // [rsp+40h] [rbp-C0h] BYREF
  int v19; // [rsp+44h] [rbp-BCh] BYREF
  __int64 *v20; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v21; // [rsp+50h] [rbp-B0h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-A8h] BYREF
  VARIANTARG v23; // [rsp+70h] [rbp-90h] BYREF
  _DWORD v24[52]; // [rsp+90h] [rbp-70h] BYREF
  _DWORD v25[52]; // [rsp+160h] [rbp+60h] BYREF

  v17 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 96LL))(a2, &v17);
  if ( v8 < 0 )
    goto LABEL_4;
  if ( !v17 )
  {
    v8 = -2147467259;
LABEL_4:
    ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v17);
    return (unsigned int)v8;
  }
  v18 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v17 + 64LL))(v17, &v18);
  if ( v10 >= 0 )
  {
    CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25>::Vector<ATL::CComBSTR,25>(v25);
    CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25>::Vector<ATL::CComBSTR,25>(v24);
    v8 = CompatibilityMarkupProcessorImpl::CalculateRequiredNamespaceAttributes(v11, a5, a6, (__int64)v25, (__int64)v24);
    if ( v8 >= 0 )
    {
      for ( i = 0; ; ++i )
      {
        if ( i >= v18 )
        {
          `eh vector destructor iterator'((char *)v24, 8, 25, (void (__fastcall *)(char *))ATL::CComBSTR::~CComBSTR);
          `eh vector destructor iterator'((char *)v25, 8, 25, (void (__fastcall *)(char *))ATL::CComBSTR::~CComBSTR);
          ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v17);
          return 0;
        }
        v16 = 0;
        v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v17 + 56LL))(v17, 0, &v16);
        if ( v8 < 0 )
          goto LABEL_27;
        if ( !v16 )
          break;
        v19 = 0;
        v8 = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD, GUID *, _QWORD *), int *))(*v16)[10])(v16, &v19);
        if ( v8 < 0 )
          goto LABEL_27;
        if ( v19 == 1 )
        {
          ATL::CComQIPtr<IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>::CComQIPtr<IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>(
            &v20,
            v16);
          if ( !v20 )
          {
            ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&v20);
            ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&v16);
            `eh vector destructor iterator'((char *)v24, 8, 25, (void (__fastcall *)(char *))ATL::CComBSTR::~CComBSTR);
            `eh vector destructor iterator'((char *)v25, 8, 25, (void (__fastcall *)(char *))ATL::CComBSTR::~CComBSTR);
            v8 = -2147467262;
            goto LABEL_4;
          }
          v8 = CompatibilityMarkupProcessorImpl::AddRequiredNamespaceAttributes(v13, v20, (__int64)v25, (__int64)v24);
          v14 = (__int64 *)&v20;
          if ( v8 < 0 )
            goto LABEL_22;
          ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&v20);
        }
        v21 = 0;
        v15 = *(__int64 (__fastcall **)(__int64, void (__fastcall ***)(_QWORD, GUID *, _QWORD *), VARIANTARG *, __int64 *))(*(_QWORD *)a3 + 144LL);
        pvarg.vt = 9;
        pvarg.llVal = a4;
        if ( a4 )
          (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)a4 + 8LL))(a4);
        v23 = pvarg;
        v8 = v15(a3, v16, &v23, &v21);
        VariantClear(&pvarg);
        v14 = &v21;
        if ( v8 < 0 )
        {
LABEL_22:
          ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(v14);
          ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&v16);
          `eh vector destructor iterator'((char *)v24, 8, 25, (void (__fastcall *)(char *))ATL::CComBSTR::~CComBSTR);
          `eh vector destructor iterator'((char *)v25, 8, 25, (void (__fastcall *)(char *))ATL::CComBSTR::~CComBSTR);
          goto LABEL_4;
        }
        ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v21);
        ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&v16);
      }
      v8 = -2147467259;
LABEL_27:
      ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&v16);
      `eh vector destructor iterator'((char *)v24, 8, 25, (void (__fastcall *)(char *))ATL::CComBSTR::~CComBSTR);
      `eh vector destructor iterator'((char *)v25, 8, 25, (void (__fastcall *)(char *))ATL::CComBSTR::~CComBSTR);
    }
    else
    {
      `eh vector destructor iterator'((char *)v24, 8, 25, (void (__fastcall *)(char *))ATL::CComBSTR::~CComBSTR);
      `eh vector destructor iterator'((char *)v25, 8, 25, (void (__fastcall *)(char *))ATL::CComBSTR::~CComBSTR);
    }
    goto LABEL_4;
  }
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v17);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800557c4  mov     [rsp-8+arg_0], rbx
0x1800557c9  mov     [rsp-8+arg_18], rsi
0x1800557ce  push    rbp
0x1800557cf  push    rdi
0x1800557d0  push    r12
0x1800557d2  push    r14
0x1800557d4  push    r15
0x1800557d6  lea     rbp, [rsp-140h]
0x1800557de  sub     rsp, 240h
0x1800557e5  mov     rax, cs:__security_cookie
0x1800557ec  xor     rax, rsp
0x1800557ef  mov     [rbp+160h+var_30], rax
0x1800557f6  mov     rdi, r9
0x1800557f9  mov     r12, r8
0x1800557fc  mov     rcx, rdx
0x1800557ff  mov     r14, [rbp+160h+arg_20]
0x180055806  mov     r15, [rbp+160h+arg_28]
0x18005580d  mov     [rsp+260h+var_228], 0
0x180055816  mov     rax, [rdx]
0x180055819  lea     rdx, [rsp+260h+var_228]
0x18005581e  mov     rax, [rax+60h]
0x180055822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055827  mov     esi, eax
0x180055829  test    eax, eax
0x18005582b  js      short loc_18005583C
0x18005582d  mov     rcx, [rsp+260h+var_228]
0x180055832  test    rcx, rcx
0x180055835  jnz     short loc_180055873
0x180055837  mov     esi, 80004005h
0x18005583c  lea     rcx, [rsp+260h+var_228]
0x180055841  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180055846  mov     eax, esi
0x180055848  mov     rcx, [rbp+160h+var_30]
0x18005584f  xor     rcx, rsp; StackCookie
0x180055852  call    __security_check_cookie
0x180055857  lea     r11, [rsp+260h+var_20]
0x18005585f  mov     rbx, [r11+30h]
0x180055863  mov     rsi, [r11+48h]
0x180055867  mov     rsp, r11
0x18005586a  pop     r15
0x18005586c  pop     r14
0x18005586e  pop     r12
0x180055870  pop     rdi
0x180055871  pop     rbp
0x180055872  retn
0x180055873  mov     [rsp+260h+var_220], 0
0x18005587b  mov     rax, [rcx]
0x18005587e  lea     rdx, [rsp+260h+var_220]
0x180055883  mov     rax, [rax+40h]
0x180055887  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005588c  mov     ebx, eax
0x18005588e  test    eax, eax
0x180055890  jns     short loc_1800558A0
0x180055892  lea     rcx, [rsp+260h+var_228]
0x180055897  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18005589c  mov     eax, ebx
0x18005589e  jmp     short loc_180055848
0x1800558a0  lea     rcx, [rbp+160h+var_100]
0x1800558a4  call    ??0?$Vector@VCComBSTR@ATL@@$0BJ@@CompatibilityMarkupProcessorImpl@@QEAA@XZ; CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25>::Vector<ATL::CComBSTR,25>(void)
0x1800558a9  nop
0x1800558aa  lea     rcx, [rbp+160h+var_1D0]
0x1800558ae  call    ??0?$Vector@VCComBSTR@ATL@@$0BJ@@CompatibilityMarkupProcessorImpl@@QEAA@XZ; CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25>::Vector<ATL::CComBSTR,25>(void)
0x1800558b3  nop
0x1800558b4  lea     rax, [rbp+160h+var_1D0]
0x1800558b8  mov     [rsp+260h+var_240], rax
0x1800558bd  lea     r9, [rbp+160h+var_100]
0x1800558c1  mov     r8, r15
0x1800558c4  mov     rdx, r14
0x1800558c7  call    ?CalculateRequiredNamespaceAttributes@CompatibilityMarkupProcessorImpl@@AEAAJPEBU?$Map@VCComBSTR@ATL@@V12@$0BJ@@1@0PEAU?$Vector@VCComBSTR@ATL@@$0BJ@@1@1@Z; CompatibilityMarkupProcessorImpl::CalculateRequiredNamespaceAttributes(CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> const *,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> const *,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> *,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> *)
0x1800558cc  mov     esi, eax
0x1800558ce  test    eax, eax
0x1800558d0  jns     short loc_18005590B
0x1800558d2  lea     r9, ??1CComBSTR@ATL@@QEAA@XZ; void (*)(void *)
0x1800558d9  mov     ebx, 19h
0x1800558de  mov     r8d, ebx; unsigned __int64
0x1800558e1  lea     edi, [rbx-11h]
0x1800558e4  mov     edx, edi; unsigned __int64
0x1800558e6  lea     rcx, [rbp+160h+var_1D0]; void *
0x1800558ea  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1800558ef  nop
0x1800558f0  lea     r9, ??1CComBSTR@ATL@@QEAA@XZ; void (*)(void *)
0x1800558f7  mov     r8d, ebx; unsigned __int64
0x1800558fa  mov     edx, edi; unsigned __int64
0x1800558fc  lea     rcx, [rbp+160h+var_100]; void *
0x180055900  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180055905  nop
0x180055906  jmp     loc_18005583C
0x18005590b  xor     ebx, ebx
0x18005590d  cmp     ebx, [rsp+260h+var_220]
0x180055911  jge     loc_180055BCB
0x180055917  mov     [rsp+260h+var_230], 0
0x180055920  mov     rcx, [rsp+260h+var_228]
0x180055925  mov     rax, [rcx]
0x180055928  lea     r8, [rsp+260h+var_230]
0x18005592d  xor     edx, edx
0x18005592f  mov     rax, [rax+38h]
0x180055933  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055938  mov     esi, eax
0x18005593a  test    eax, eax
0x18005593c  js      loc_180055B87
0x180055942  mov     rcx, [rsp+260h+var_230]
0x180055947  test    rcx, rcx
0x18005594a  jz      loc_180055B82
0x180055950  mov     [rsp+260h+var_21C], 0
0x180055958  mov     rax, [rcx]
0x18005595b  lea     rdx, [rsp+260h+var_21C]
0x180055960  mov     rax, [rax+50h]
0x180055964  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055969  mov     esi, eax
0x18005596b  test    eax, eax
0x18005596d  js      loc_180055B3E
0x180055973  cmp     [rsp+260h+var_21C], 1
0x180055978  jnz     short loc_1800559B9
0x18005597a  mov     rdx, [rsp+260h+var_230]
0x18005597f  lea     rcx, [rsp+260h+var_218]
0x180055984  call    ??0?$CComQIPtr@UIXMLDOMElement@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>::CComQIPtr<IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>(IUnknown *)
0x180055989  nop
0x18005598a  mov     rdx, [rsp+260h+var_218]
0x18005598f  test    rdx, rdx
0x180055992  jz      loc_180055AA0
0x180055998  lea     r9, [rbp+160h+var_1D0]
0x18005599c  lea     r8, [rbp+160h+var_100]
0x1800559a0  call    ?AddRequiredNamespaceAttributes@CompatibilityMarkupProcessorImpl@@AEAAJPEAUIXMLDOMElement@@PEBU?$Vector@VCComBSTR@ATL@@$0BJ@@1@1@Z; CompatibilityMarkupProcessorImpl::AddRequiredNamespaceAttributes(IXMLDOMElement *,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> const *,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> const *)
0x1800559a5  mov     esi, eax
0x1800559a7  lea     rcx, [rsp+260h+var_218]
0x1800559ac  test    eax, eax
0x1800559ae  js      loc_180055A56
0x1800559b4  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x1800559b9  mov     [rsp+260h+var_210], 0
0x1800559c2  mov     rax, [r12]
0x1800559c6  mov     rsi, [rax+90h]
0x1800559cd  mov     eax, 9
0x1800559d2  mov     word ptr [rsp+260h+pvarg], ax
0x1800559d7  mov     qword ptr [rsp+260h+pvarg+8], rdi
0x1800559dc  test    rdi, rdi
0x1800559df  jz      short loc_1800559F1
0x1800559e1  mov     rax, [rdi]
0x1800559e4  mov     rcx, rdi
0x1800559e7  mov     rax, [rax+8]
0x1800559eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800559f0  nop
0x1800559f1  movups  xmm0, xmmword ptr [rsp+260h+pvarg]
0x1800559f6  movaps  [rsp+260h+var_1F0], xmm0
0x1800559fb  movsd   xmm1, qword ptr [rsp+260h+pvarg+10h]
0x180055a01  movsd   [rbp+160h+var_1E0], xmm1
0x180055a06  lea     r9, [rsp+260h+var_210]
0x180055a0b  lea     r8, [rsp+260h+var_1F0]
0x180055a10  mov     rdx, [rsp+260h+var_230]
0x180055a15  mov     rcx, r12
0x180055a18  mov     rax, rsi
0x180055a1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055a20  mov     esi, eax
0x180055a22  lea     rcx, [rsp+260h+pvarg]; pvarg
0x180055a27  call    cs:__imp_VariantClear
0x180055a2d  mov     ecx, esi
0x180055a2f  shr     ecx, 1Fh
0x180055a32  test    cl, cl
0x180055a34  lea     rcx, [rsp+260h+var_210]
0x180055a39  jnz     loc_180055AF4
0x180055a3f  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180055a44  nop
0x180055a45  lea     rcx, [rsp+260h+var_230]
0x180055a4a  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180055a4f  inc     ebx
0x180055a51  jmp     loc_18005590D
0x180055a56  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180055a5b  nop
0x180055a5c  lea     rcx, [rsp+260h+var_230]
0x180055a61  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180055a66  nop
0x180055a67  lea     r9, ??1CComBSTR@ATL@@QEAA@XZ; void (*)(void *)
0x180055a6e  mov     ebx, 19h
0x180055a73  mov     r8d, ebx; unsigned __int64
0x180055a76  lea     edi, [rbx-11h]
0x180055a79  mov     edx, edi; unsigned __int64
0x180055a7b  lea     rcx, [rbp+160h+var_1D0]; void *
0x180055a7f  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180055a84  nop
0x180055a85  lea     r9, ??1CComBSTR@ATL@@QEAA@XZ; void (*)(void *)
0x180055a8c  mov     r8d, ebx; unsigned __int64
0x180055a8f  mov     edx, edi; unsigned __int64
0x180055a91  lea     rcx, [rbp+160h+var_100]; void *
0x180055a95  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180055a9a  nop
0x180055a9b  jmp     loc_18005583C
0x180055aa0  lea     rcx, [rsp+260h+var_218]
0x180055aa5  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180055aaa  nop
0x180055aab  lea     rcx, [rsp+260h+var_230]
0x180055ab0  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180055ab5  nop
0x180055ab6  lea     r9, ??1CComBSTR@ATL@@QEAA@XZ; void (*)(void *)
0x180055abd  mov     ebx, 19h
0x180055ac2  mov     r8d, ebx; unsigned __int64
0x180055ac5  lea     edi, [rbx-11h]
0x180055ac8  mov     edx, edi; unsigned __int64
0x180055aca  lea     rcx, [rbp+160h+var_1D0]; void *
0x180055ace  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180055ad3  nop
0x180055ad4  lea     r9, ??1CComBSTR@ATL@@QEAA@XZ; void (*)(void *)
0x180055adb  mov     r8d, ebx; unsigned __int64
0x180055ade  mov     edx, edi; unsigned __int64
0x180055ae0  lea     rcx, [rbp+160h+var_100]; void *
0x180055ae4  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180055ae9  nop
0x180055aea  mov     esi, 80004002h
0x180055aef  jmp     loc_18005583C
0x180055af4  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180055af9  nop
0x180055afa  lea     rcx, [rsp+260h+var_230]
0x180055aff  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180055b04  nop
0x180055b05  lea     r9, ??1CComBSTR@ATL@@QEAA@XZ; void (*)(void *)
0x180055b0c  mov     ebx, 19h
0x180055b11  mov     r8d, ebx; unsigned __int64
0x180055b14  lea     edi, [rbx-11h]
0x180055b17  mov     edx, edi; unsigned __int64
0x180055b19  lea     rcx, [rbp+160h+var_1D0]; void *
0x180055b1d  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180055b22  nop
0x180055b23  lea     r9, ??1CComBSTR@ATL@@QEAA@XZ; void (*)(void *)
0x180055b2a  mov     r8d, ebx; unsigned __int64
0x180055b2d  mov     edx, edi; unsigned __int64
0x180055b2f  lea     rcx, [rbp+160h+var_100]; void *
0x180055b33  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180055b38  nop
0x180055b39  jmp     loc_18005583C
0x180055b3e  lea     rcx, [rsp+260h+var_230]
0x180055b43  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180055b48  nop
0x180055b49  lea     r9, ??1CComBSTR@ATL@@QEAA@XZ; void (*)(void *)
0x180055b50  mov     ebx, 19h
0x180055b55  mov     r8d, ebx; unsigned __int64
0x180055b58  lea     edi, [rbx-11h]
0x180055b5b  mov     edx, edi; unsigned __int64
0x180055b5d  lea     rcx, [rbp+160h+var_1D0]; void *
0x180055b61  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180055b66  nop
0x180055b67  lea     r9, ??1CComBSTR@ATL@@QEAA@XZ; void (*)(void *)
0x180055b6e  mov     r8d, ebx; unsigned __int64
0x180055b71  mov     edx, edi; unsigned __int64
0x180055b73  lea     rcx, [rbp+160h+var_100]; void *
0x180055b77  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180055b7c  nop
0x180055b7d  jmp     loc_18005583C
0x180055b82  mov     esi, 80004005h
0x180055b87  lea     rcx, [rsp+260h+var_230]
0x180055b8c  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180055b91  nop
0x180055b92  lea     r9, ??1CComBSTR@ATL@@QEAA@XZ; void (*)(void *)
0x180055b99  mov     ebx, 19h
0x180055b9e  mov     r8d, ebx; unsigned __int64
0x180055ba1  lea     edi, [rbx-11h]
0x180055ba4  mov     edx, edi; unsigned __int64
0x180055ba6  lea     rcx, [rbp+160h+var_1D0]; void *
0x180055baa  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180055baf  nop
0x180055bb0  lea     r9, ??1CComBSTR@ATL@@QEAA@XZ; void (*)(void *)
0x180055bb7  mov     r8d, ebx; unsigned __int64
0x180055bba  mov     edx, edi; unsigned __int64
0x180055bbc  lea     rcx, [rbp+160h+var_100]; void *
0x180055bc0  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180055bc5  nop
0x180055bc6  jmp     loc_18005583C
0x180055bcb  lea     r9, ??1CComBSTR@ATL@@QEAA@XZ; void (*)(void *)
0x180055bd2  mov     ebx, 19h
0x180055bd7  mov     r8d, ebx; unsigned __int64
0x180055bda  lea     edi, [rbx-11h]
0x180055bdd  mov     edx, edi; unsigned __int64
0x180055bdf  lea     rcx, [rbp+160h+var_1D0]; void *
0x180055be3  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180055be8  nop
0x180055be9  lea     r9, ??1CComBSTR@ATL@@QEAA@XZ; void (*)(void *)
0x180055bf0  mov     r8d, ebx; unsigned __int64
0x180055bf3  mov     edx, edi; unsigned __int64
0x180055bf5  lea     rcx, [rbp+160h+var_100]; void *
0x180055bf9  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180055bfe  nop
0x180055bff  lea     rcx, [rsp+260h+var_228]
0x180055c04  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180055c09  xor     eax, eax
0x180055c0b  jmp     loc_180055848
```
