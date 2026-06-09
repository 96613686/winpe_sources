# CompatibilityMarkupProcessorImpl::WalkTree(IXMLDOMElement *,IXMLDOMNode *,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> *,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> *,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25> *,bool *)

- ea: `0x18000feb0`
- end: `0x18001065e`
- name: `?WalkTree@CompatibilityMarkupProcessorImpl@@AEAAJPEAUIXMLDOMElement@@PEAUIXMLDOMNode@@PEAU?$Map@VCComBSTR@ATL@@V12@$0BJ@@1@PEAU?$Vector@VCComBSTR@ATL@@$0BJ@@1@PEAU?$Map@VCComBSTR@ATL@@U?$Vector@VCComBSTR@ATL@@$0DC@@CompatibilityMarkupProcessorImpl@@$0BJ@@1@PEA_N@Z`
- size: `1966`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000feb0`
- `0x1800121a0`

## callees

- `0x18000fe54`
- `0x18000feb0`
- `0x180010670`
- `0x180012620`
- `0x1800126c8`
- `0x18001277c`
- `0x1800127cc`
- `0x18001b5d8`
- `0x18001c800`
- `0x18002ea84`
- `0x18002eac0`
- `0x18004bed8`
- `0x180056054`
- `0x18005695c`
- `0x180084010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180010012`
- `OLEAUT32!__imp_SysAllocString` at `0x180010012`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ffa7`
- `OLEAUT32!__imp_SysFreeString` at `0x180010065`
- `OLEAUT32!__imp_SysFreeString` at `0x180010226`
- `OLEAUT32!__imp_SysFreeString` at `0x1800103e0`
- `OLEAUT32!__imp_SysFreeString` at `0x180010489`
- `OLEAUT32!__imp_SysFreeString` at `0x180010494`
- `OLEAUT32!__imp_SysFreeString` at `0x18001049f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800104b4`
- `OLEAUT32!__imp_SysFreeString` at `0x180010515`
- `OLEAUT32!__imp_SysFreeString` at `0x180010540`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ffa7`
- `OLEAUT32!__imp_SysFreeString` at `0x180010065`
- `OLEAUT32!__imp_SysFreeString` at `0x180010226`
- `OLEAUT32!__imp_SysFreeString` at `0x1800103e0`
- `OLEAUT32!__imp_SysFreeString` at `0x180010489`
- `OLEAUT32!__imp_SysFreeString` at `0x180010494`
- `OLEAUT32!__imp_SysFreeString` at `0x18001049f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800104b4`
- `OLEAUT32!__imp_SysFreeString` at `0x180010515`
- `OLEAUT32!__imp_SysFreeString` at `0x180010540`
- `OLEAUT32!__imp_VarBstrCmp` at `0x18001004a`
- `OLEAUT32!__imp_VarBstrCmp` at `0x18001004a`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall CompatibilityMarkupProcessorImpl::WalkTree(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        char *a4,
        void *a5,
        char *a6,
        _BYTE *a7)
{
  int v8; // r13d
  void *v11; // r15
  _BYTE *v12; // rdi
  int v13; // eax
  int v14; // ebx
  BSTR v15; // rax
  __int64 v16; // r8
  int v17; // ecx
  int v18; // edx
  char *v19; // rdi
  char *v21; // r14
  void *v22; // r13
  char *v23; // r12
  const unsigned __int16 *v24; // r15
  OLECHAR *v25; // rbx
  int i; // edi
  OLECHAR *v27; // rcx
  __int64 v28; // r15
  __int64 v29; // r13
  unsigned int v30; // edi
  __int64 v31; // rdx
  void *v32; // rbx
  void *v33; // rdi
  BSTR v34; // rax
  int v35; // r9d
  int v36; // edx
  OLECHAR *v37; // rcx
  int v38; // eax
  int v39; // ecx
  BSTR bstrString; // [rsp+40h] [rbp-71h] BYREF
  __int64 v41; // [rsp+48h] [rbp-69h] BYREF
  __int64 v42; // [rsp+50h] [rbp-61h] BYREF
  int v43; // [rsp+58h] [rbp-59h] BYREF
  __int64 v44; // [rsp+60h] [rbp-51h] BYREF
  int v45; // [rsp+68h] [rbp-49h] BYREF
  void *v46; // [rsp+70h] [rbp-41h] BYREF
  char *v47; // [rsp+78h] [rbp-39h] BYREF
  char *v48; // [rsp+80h] [rbp-31h] BYREF
  char *v49; // [rsp+88h] [rbp-29h] BYREF
  void *v50; // [rsp+90h] [rbp-21h] BYREF
  char *v51; // [rsp+98h] [rbp-19h] BYREF
  void *Block; // [rsp+A0h] [rbp-11h]
  char *v53; // [rsp+A8h] [rbp-9h]
  BSTR v55; // [rsp+108h] [rbp+57h] BYREF
  __int64 v56; // [rsp+110h] [rbp+5Fh]
  char *v57; // [rsp+118h] [rbp+67h]

  v57 = a4;
  v56 = a3;
  v8 = a3;
  if ( !a2 )
    return 2147942487LL;
  if ( !a4 )
    return 2147942487LL;
  v11 = a5;
  if ( !a5 )
    return 2147942487LL;
  v12 = a7;
  if ( !a7 )
    return 2147942487LL;
  *a7 = 0;
  bstrString = 0;
  v13 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)a2 + 312LL))(a2, &bstrString);
  v14 = v13;
  if ( v13 < 0 )
  {
LABEL_13:
    SysFreeString(bstrString);
    return (unsigned int)v14;
  }
  if ( v13 == 1 )
  {
    ATL::CComBSTR::operator=(&bstrString, &word_1800884E0);
    v15 = bstrString;
    if ( !bstrString )
    {
      SysFreeString(0);
      return 2147942414LL;
    }
  }
  else
  {
    v15 = bstrString;
  }
  v16 = *(_QWORD *)(a1 + 232) - (_QWORD)v15;
  do
  {
    v17 = *(BSTR)((char *)v15 + v16);
    v18 = *v15 - v17;
    if ( v18 )
      break;
    ++v15;
  }
  while ( v17 );
  if ( v18 )
  {
    v48 = a4;
    v46 = v11;
    v19 = a6;
    v47 = a6;
    v14 = CompatibilityMarkupProcessorImpl::ProcessAttributes((_QWORD *)a1, a2, &v48, &v46, (void **)&v47, 0);
    if ( v14 < 0 )
      goto LABEL_13;
    v21 = 0;
    v51 = 0;
    if ( v48 != a4 )
    {
      v21 = v48;
      NCoreLibrary::TGenericSP<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25>,NCoreLibrary::TAutoPtr<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25>>,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> *,0,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> const *>::Reset(&v51);
      v51 = v21;
    }
    Block = 0;
    v50 = 0;
    v22 = v46;
    if ( v46 != v11 )
    {
      Block = v46;
      NCoreLibrary::TGenericSP<CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25>,NCoreLibrary::TAutoPtr<CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25>>,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> *,0,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> const *>::Reset(&v50);
      v50 = v22;
      v22 = v46;
    }
    v23 = 0;
    v49 = 0;
    if ( v47 != v19 )
    {
      v23 = v47;
      NCoreLibrary::TGenericSP<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25>,NCoreLibrary::TAutoPtr<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25>>,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25> *,0,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25> const *>::Reset(&v49);
      v49 = v23;
      v22 = v46;
    }
    v24 = bstrString;
    if ( bstrString )
    {
      v25 = SysAllocString(bstrString);
      if ( !v25 )
        ATL::AtlThrowImpl(-2147024882);
    }
    else
    {
      v25 = 0;
    }
    for ( i = 0; ; ++i )
    {
      if ( i >= *(_DWORD *)(a1 + 224) )
        goto LABEL_101;
      if ( VarBstrCmp(*(BSTR *)(a1 + 8LL * i + 24), v25, 0x400u, 0) == 1 )
        break;
    }
    if ( i == -1 )
    {
LABEL_101:
      SysFreeString(v25);
      ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v55, v24);
      v38 = CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25>::Find(v22, &v55);
      v27 = v55;
      if ( v38 != -1 )
      {
        SysFreeString(v55);
        v14 = CompatibilityMarkupProcessorImpl::ProcessIgnoredElement(
                v39,
                a2,
                v56,
                (_DWORD)v48,
                (__int64)v57,
                (__int64)v47);
        if ( v14 < 0 )
        {
          NCoreLibrary::TGenericSP<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25>,NCoreLibrary::TAutoPtr<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25>>,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25> *,0,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25> const *>::Reset(&v49);
          NCoreLibrary::TGenericSP<CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25>,NCoreLibrary::TAutoPtr<CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25>>,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> *,0,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> const *>::Reset(&v50);
          NCoreLibrary::TGenericSP<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25>,NCoreLibrary::TAutoPtr<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25>>,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> *,0,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> const *>::Reset(&v51);
          goto LABEL_13;
        }
        *a7 = 1;
        goto LABEL_48;
      }
    }
    else
    {
      v27 = v25;
    }
    SysFreeString(v27);
    v28 = (__int64)v47;
    v29 = (__int64)v46;
    v53 = v48;
    v30 = 0;
    v41 = 0;
    v14 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 96LL))(a2, &v41);
    if ( v14 >= 0 )
    {
      if ( v41 )
      {
        v43 = 0;
        v14 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v41 + 64LL))(v41, &v43);
        if ( v14 >= 0 )
        {
          while ( (int)v30 < v43 )
          {
            v42 = 0;
            v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v41 + 56LL))(v41, v30, &v42);
            if ( v14 < 0 )
              goto LABEL_55;
            if ( !v42 )
            {
              v14 = -2147467259;
LABEL_55:
              if ( v42 )
                (*(void (**)(void))(*(_QWORD *)v42 + 16LL))();
              if ( v41 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
              goto LABEL_59;
            }
            v45 = 0;
            v14 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v42 + 80LL))(v42, &v45);
            if ( v14 < 0 )
            {
              ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v42);
              ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v41);
              goto LABEL_59;
            }
            if ( v45 == 1 )
            {
              v31 = 0;
              v44 = 0;
              if ( v42 )
              {
                (**(void (__fastcall ***)(__int64, GUID *, __int64 *))v42)(
                  v42,
                  &GUID_2933bf86_7b36_11d2_b20e_00c04f983e60,
                  &v44);
                v31 = v44;
              }
              if ( !v31 )
              {
                ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v44);
                ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v42);
                ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v41);
                v14 = -2147467262;
                goto LABEL_59;
              }
              LOBYTE(v55) = 0;
              v14 = CompatibilityMarkupProcessorImpl::WalkTree(a1, v31, a2, (_DWORD)v53, v29, v28, (__int64)&v55);
              if ( v14 < 0 )
              {
                if ( v44 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
                if ( v42 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
                if ( v41 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
                goto LABEL_59;
              }
              if ( (_BYTE)v55 )
              {
                v14 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v41 + 64LL))(v41, &v43);
                if ( v14 < 0 )
                {
                  if ( v44 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
                  if ( v42 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
                  if ( v41 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
                  goto LABEL_59;
                }
                --v30;
              }
              if ( v44 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
            }
            if ( v42 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
            ++v30;
          }
          if ( v41 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
LABEL_48:
          if ( v23 )
          {
            `eh vector destructor iterator'(
              v23,
              416,
              25,
              (void (__fastcall *)(char *))CompatibilityMarkupProcessorImpl::Pair<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>>::~Pair<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>>);
            operator delete(v23);
          }
          v32 = Block;
          if ( Block )
          {
            `eh vector destructor iterator'((char *)Block, 8, 25, (void (__fastcall *)(char *))ATL::CComBSTR::~CComBSTR);
            operator delete(v32);
          }
          if ( v21 )
          {
            `eh vector destructor iterator'(
              v21,
              16,
              25,
              (void (__fastcall *)(char *))CompatibilityMarkupProcessorImpl::Pair<ATL::CComBSTR,ATL::CComBSTR>::~Pair<ATL::CComBSTR,ATL::CComBSTR>);
            operator delete(v21);
          }
          goto LABEL_54;
        }
        ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v41);
LABEL_59:
        if ( v23 )
        {
          `eh vector destructor iterator'(
            v23,
            416,
            25,
            (void (__fastcall *)(char *))CompatibilityMarkupProcessorImpl::Pair<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>>::~Pair<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>>);
          operator delete(v23);
        }
        v33 = Block;
        if ( Block )
        {
          `eh vector destructor iterator'((char *)Block, 8, 25, (void (__fastcall *)(char *))ATL::CComBSTR::~CComBSTR);
          operator delete(v33);
        }
        if ( v21 )
        {
          `eh vector destructor iterator'(
            v21,
            16,
            25,
            (void (__fastcall *)(char *))CompatibilityMarkupProcessorImpl::Pair<ATL::CComBSTR,ATL::CComBSTR>::~Pair<ATL::CComBSTR,ATL::CComBSTR>);
          operator delete(v21);
        }
        goto LABEL_13;
      }
      v14 = -2147467259;
    }
    if ( v41 )
      (*(void (**)(void))(*(_QWORD *)v41 + 16LL))();
    goto LABEL_59;
  }
  v55 = 0;
  v14 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)a2 + 328LL))(a2, &v55);
  v37 = v55;
  if ( v14 < 0 )
  {
LABEL_99:
    SysFreeString(v37);
    goto LABEL_13;
  }
  if ( !v55 || !*v55 )
  {
    v14 = -2147467259;
    goto LABEL_99;
  }
  v34 = v55;
  do
  {
    v35 = *(BSTR)((char *)v34 + *(_QWORD *)(a1 + 240) - (_QWORD)v55);
    v36 = *v34 - v35;
    if ( v36 )
      break;
    ++v34;
  }
  while ( v35 );
  if ( !v36 )
  {
    v14 = CompatibilityMarkupProcessorImpl::ProcessAlternateContent(a1, a2, v8, (_DWORD)a4, (__int64)v11, (__int64)a6);
    if ( v14 >= 0 )
    {
      *v12 = 1;
      SysFreeString(v55);
LABEL_54:
      SysFreeString(bstrString);
      return 0;
    }
    v37 = v55;
    goto LABEL_99;
  }
  SysFreeString(v55);
  SysFreeString(bstrString);
  return 2147745796LL;
}

```

## disassembly

```asm
0x18000feb0  mov     [rsp-8+arg_18], r9
0x18000feb5  mov     [rsp-8+arg_10], r8
0x18000feba  mov     [rsp-8+arg_0], rcx
0x18000febf  push    rbp
0x18000fec0  push    rbx
0x18000fec1  push    rsi
0x18000fec2  push    rdi
0x18000fec3  push    r12
0x18000fec5  push    r13
0x18000fec7  push    r14
0x18000fec9  push    r15
0x18000fecb  lea     rbp, [rsp-7]
0x18000fed0  sub     rsp, 0B8h
0x18000fed7  mov     r12, r9
0x18000feda  mov     r13, r8
0x18000fedd  mov     rsi, rdx
0x18000fee0  mov     r14, rcx
0x18000fee3  test    rdx, rdx
0x18000fee6  jz      loc_180010654
0x18000feec  test    r9, r9
0x18000feef  jz      loc_180010654
0x18000fef5  mov     r15, [rbp+3Fh+arg_20]
0x18000fef9  test    r15, r15
0x18000fefc  jz      loc_180010654
0x18000ff02  mov     rdi, [rbp+3Fh+arg_30]
0x18000ff06  test    rdi, rdi
0x18000ff09  jz      loc_180010654
0x18000ff0f  mov     byte ptr [rdi], 0
0x18000ff12  mov     [rbp+3Fh+bstrString], 0
0x18000ff1a  mov     rax, [rdx]
0x18000ff1d  lea     rdx, [rbp+3Fh+bstrString]
0x18000ff21  mov     rcx, rsi
0x18000ff24  mov     rax, [rax+138h]
0x18000ff2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff30  mov     ebx, eax
0x18000ff32  test    eax, eax
0x18000ff34  js      short loc_18000FFA3
0x18000ff36  cmp     eax, 1
0x18000ff39  jz      loc_1800103C1
0x18000ff3f  mov     rax, [rbp+3Fh+bstrString]
0x18000ff43  mov     r8, [r14+0E8h]
0x18000ff4a  sub     r8, rax
0x18000ff4d  nop     dword ptr [rax]
0x18000ff50  movzx   edx, word ptr [rax]
0x18000ff53  movzx   ecx, word ptr [rax+r8]
0x18000ff58  sub     edx, ecx
0x18000ff5a  jnz     short loc_18000FF64
0x18000ff5c  add     rax, 2
0x18000ff60  test    ecx, ecx
0x18000ff62  jnz     short loc_18000FF50
0x18000ff64  test    edx, edx
0x18000ff66  jz      loc_180010455
0x18000ff6c  mov     [rbp+3Fh+var_70], r12
0x18000ff70  mov     [rbp+3Fh+var_80], r15
0x18000ff74  mov     rdi, [rbp+3Fh+arg_28]
0x18000ff78  mov     [rbp+3Fh+var_78], rdi
0x18000ff7c  mov     byte ptr [rsp+0F0h+var_C8], 0
0x18000ff81  lea     rax, [rbp+3Fh+var_78]
0x18000ff85  mov     [rsp+0F0h+var_D0], rax
0x18000ff8a  lea     r9, [rbp+3Fh+var_80]
0x18000ff8e  lea     r8, [rbp+3Fh+var_70]
0x18000ff92  mov     rdx, rsi
0x18000ff95  mov     rcx, r14
0x18000ff98  call    ?ProcessAttributes@CompatibilityMarkupProcessorImpl@@AEAAJPEAUIXMLDOMElement@@PEAPEAU?$Map@VCComBSTR@ATL@@V12@$0BJ@@1@PEAPEAU?$Vector@VCComBSTR@ATL@@$0BJ@@1@PEAPEAU?$Map@VCComBSTR@ATL@@U?$Vector@VCComBSTR@ATL@@$0DC@@CompatibilityMarkupProcessorImpl@@$0BJ@@1@_N@Z; CompatibilityMarkupProcessorImpl::ProcessAttributes(IXMLDOMElement *,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> * *,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> * *,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25> * *,bool)
0x18000ff9d  mov     ebx, eax
0x18000ff9f  test    eax, eax
0x18000ffa1  jns     short loc_18000FFC3
0x18000ffa3  mov     rcx, [rbp+3Fh+bstrString]; bstrString
0x18000ffa7  call    cs:__imp_SysFreeString
0x18000ffad  mov     eax, ebx
0x18000ffaf  add     rsp, 0B8h
0x18000ffb6  pop     r15
0x18000ffb8  pop     r14
0x18000ffba  pop     r13
0x18000ffbc  pop     r12
0x18000ffbe  pop     rdi
0x18000ffbf  pop     rsi
0x18000ffc0  pop     rbx
0x18000ffc1  pop     rbp
0x18000ffc2  retn
0x18000ffc3  xor     r14d, r14d
0x18000ffc6  mov     [rbp+3Fh+var_58], r14
0x18000ffca  mov     rax, [rbp+3Fh+var_70]
0x18000ffce  cmp     rax, r12
0x18000ffd1  jnz     loc_1800104BF
0x18000ffd7  xor     ebx, ebx
0x18000ffd9  mov     [rbp+3Fh+Block], rbx
0x18000ffdd  mov     [rbp+3Fh+var_60], rbx
0x18000ffe1  mov     r13, [rbp+3Fh+var_80]
0x18000ffe5  cmp     r13, r15
0x18000ffe8  jnz     loc_1800104D4
0x18000ffee  xor     r12d, r12d
0x18000fff1  mov     [rbp+3Fh+var_68], r12
0x18000fff5  mov     rax, [rbp+3Fh+var_78]
0x18000fff9  cmp     rax, rdi
0x18000fffc  jnz     loc_1800104EE
0x180010002  mov     r15, [rbp+3Fh+bstrString]
0x180010006  test    r15, r15
0x180010009  jz      loc_1800103BA
0x18001000f  mov     rcx, r15; psz
0x180010012  call    cs:__imp_SysAllocString
0x180010018  mov     rbx, rax
0x18001001b  test    rax, rax
0x18001001e  jz      loc_180010507
0x180010024  xor     edi, edi
0x180010026  mov     rax, [rbp+3Fh+arg_0]
0x18001002a  cmp     edi, [rax+0E0h]
0x180010030  jge     loc_180010512
0x180010036  movsxd  rcx, edi
0x180010039  xor     r9d, r9d; dwFlags
0x18001003c  mov     r8d, 400h; lcid
0x180010042  mov     rdx, rbx; bstrRight
0x180010045  mov     rcx, [rax+rcx*8+18h]; bstrLeft
0x18001004a  call    cs:__imp_VarBstrCmp
0x180010050  cmp     eax, 1
0x180010053  jz      short loc_180010059
0x180010055  inc     edi
0x180010057  jmp     short loc_180010026
0x180010059  cmp     edi, 0FFFFFFFFh
0x18001005c  jz      loc_180010512
0x180010062  mov     rcx, rbx; bstrString
0x180010065  call    cs:__imp_SysFreeString
0x18001006b  mov     r15, [rbp+3Fh+var_78]
0x18001006f  mov     r13, [rbp+3Fh+var_80]
0x180010073  mov     rax, [rbp+3Fh+var_70]
0x180010077  mov     [rbp+3Fh+var_48], rax
0x18001007b  xor     edi, edi
0x18001007d  mov     [rbp+3Fh+var_A8], rdi
0x180010081  mov     rax, [rsi]
0x180010084  lea     rdx, [rbp+3Fh+var_A8]
0x180010088  mov     rcx, rsi
0x18001008b  mov     rax, [rax+60h]
0x18001008f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010094  mov     ebx, eax
0x180010096  mov     rcx, [rbp+3Fh+var_A8]
0x18001009a  test    eax, eax
0x18001009c  js      loc_1800103A3
0x1800100a2  test    rcx, rcx
0x1800100a5  jz      loc_18001059C
0x1800100ab  mov     [rbp+3Fh+var_98], edi
0x1800100ae  mov     rax, [rcx]
0x1800100b1  lea     rdx, [rbp+3Fh+var_98]
0x1800100b5  mov     rax, [rax+40h]
0x1800100b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100be  mov     ebx, eax
0x1800100c0  test    eax, eax
0x1800100c2  js      loc_1800105A6
0x1800100c8  cmp     edi, [rbp+3Fh+var_98]
0x1800100cb  jge     loc_1800101D1
0x1800100d1  mov     [rbp+3Fh+var_A0], 0
0x1800100d9  mov     rcx, [rbp+3Fh+var_A8]
0x1800100dd  mov     rax, [rcx]
0x1800100e0  lea     r8, [rbp+3Fh+var_A0]
0x1800100e4  mov     edx, edi
0x1800100e6  mov     rax, [rax+38h]
0x1800100ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100ef  mov     ebx, eax
0x1800100f1  mov     rcx, [rbp+3Fh+var_A0]
0x1800100f5  test    eax, eax
0x1800100f7  js      loc_180010258
0x1800100fd  test    rcx, rcx
0x180010100  jz      loc_1800105FA
0x180010106  mov     [rbp+3Fh+var_88], 0
0x18001010d  mov     rax, [rcx]
0x180010110  lea     rdx, [rbp+3Fh+var_88]
0x180010114  mov     rax, [rax+50h]
0x180010118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001011d  mov     ebx, eax
0x18001011f  test    eax, eax
0x180010121  js      loc_1800105E2
0x180010127  cmp     [rbp+3Fh+var_88], 1
0x18001012b  jnz     loc_1800101B4
0x180010131  mov     rcx, [rbp+3Fh+var_A0]
0x180010135  xor     edx, edx
0x180010137  mov     [rbp+3Fh+var_90], rdx
0x18001013b  test    rcx, rcx
0x18001013e  jz      short loc_18001015A
0x180010140  mov     rax, [rcx]
0x180010143  lea     r8, [rbp+3Fh+var_90]
0x180010147  lea     rdx, _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60
0x18001014e  mov     rax, [rax]
0x180010151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010156  mov     rdx, [rbp+3Fh+var_90]
0x18001015a  test    rdx, rdx
0x18001015d  jz      loc_1800105BB
0x180010163  mov     byte ptr [rbp+3Fh+arg_8], 0
0x180010167  lea     rax, [rbp+3Fh+arg_8]
0x18001016b  mov     [rsp+0F0h+var_C0], rax
0x180010170  mov     [rsp+0F0h+var_C8], r15
0x180010175  mov     [rsp+0F0h+var_D0], r13
0x18001017a  mov     r9, [rbp+3Fh+var_48]
0x18001017e  mov     r8, rsi
0x180010181  mov     rcx, [rbp+3Fh+arg_0]
0x180010185  call    ?WalkTree@CompatibilityMarkupProcessorImpl@@AEAAJPEAUIXMLDOMElement@@PEAUIXMLDOMNode@@PEAU?$Map@VCComBSTR@ATL@@V12@$0BJ@@1@PEAU?$Vector@VCComBSTR@ATL@@$0BJ@@1@PEAU?$Map@VCComBSTR@ATL@@U?$Vector@VCComBSTR@ATL@@$0DC@@CompatibilityMarkupProcessorImpl@@$0BJ@@1@PEA_N@Z; CompatibilityMarkupProcessorImpl::WalkTree(IXMLDOMElement *,IXMLDOMNode *,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> *,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> *,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25> *,bool *)
0x18001018a  mov     ebx, eax
0x18001018c  test    eax, eax
0x18001018e  js      loc_1800102CF
0x180010194  cmp     byte ptr [rbp+3Fh+arg_8], 0
0x180010198  jnz     loc_18001033E
0x18001019e  mov     rcx, [rbp+3Fh+var_90]
0x1800101a2  test    rcx, rcx
0x1800101a5  jz      short loc_1800101B4
0x1800101a7  mov     rax, [rcx]
0x1800101aa  mov     rax, [rax+10h]
0x1800101ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101b3  nop
0x1800101b4  mov     rcx, [rbp+3Fh+var_A0]
0x1800101b8  test    rcx, rcx
0x1800101bb  jz      short loc_1800101CA
0x1800101bd  mov     rax, [rcx]
0x1800101c0  mov     rax, [rax+10h]
0x1800101c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101c9  nop
0x1800101ca  inc     edi
0x1800101cc  jmp     loc_1800100C8
0x1800101d1  mov     rcx, [rbp+3Fh+var_A8]
0x1800101d5  test    rcx, rcx
0x1800101d8  jz      short loc_1800101E7
0x1800101da  mov     rax, [rcx]
0x1800101dd  mov     rax, [rax+10h]
0x1800101e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101e6  nop
0x1800101e7  test    r12, r12
0x1800101ea  jnz     short loc_180010233
0x1800101ec  mov     rbx, [rbp+3Fh+Block]
0x1800101f0  test    rbx, rbx
0x1800101f3  jnz     loc_18001062C
0x1800101f9  test    r14, r14
0x1800101fc  jz      short loc_180010222
0x1800101fe  lea     r9, ??1?$Pair@VCComBSTR@ATL@@V12@@CompatibilityMarkupProcessorImpl@@QEAA@XZ; void (*)(void *)
0x180010205  mov     edx, 10h; unsigned __int64
0x18001020a  mov     r8d, 19h; unsigned __int64
0x180010210  mov     rcx, r14; void *
0x180010213  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180010218  nop
0x180010219  mov     rcx, r14; Block
0x18001021c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180010221  nop
0x180010222  mov     rcx, [rbp+3Fh+bstrString]; bstrString
0x180010226  call    cs:__imp_SysFreeString
0x18001022c  xor     eax, eax
0x18001022e  jmp     loc_18000FFAF
0x180010233  lea     r9, ??1?$Pair@VCComBSTR@ATL@@U?$Vector@VCComBSTR@ATL@@$0DC@@CompatibilityMarkupProcessorImpl@@@CompatibilityMarkupProcessorImpl@@QEAA@XZ; void (*)(void *)
0x18001023a  mov     edx, 1A0h; unsigned __int64
0x18001023f  mov     r8d, 19h; unsigned __int64
0x180010245  mov     rcx, r12; void *
0x180010248  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18001024d  nop
0x18001024e  mov     rcx, r12; Block
0x180010251  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180010256  jmp     short loc_1800101EC
0x180010258  test    rcx, rcx
0x18001025b  jz      short loc_18001026A
0x18001025d  mov     rax, [rcx]
0x180010260  mov     rax, [rax+10h]
0x180010264  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010269  nop
0x18001026a  mov     rcx, [rbp+3Fh+var_A8]
0x18001026e  test    rcx, rcx
0x180010271  jz      short loc_180010280
0x180010273  mov     rax, [rcx]
0x180010276  mov     rax, [rax+10h]
0x18001027a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001027f  nop
0x180010280  test    ebx, ebx
0x180010282  jns     loc_1800101E7
0x180010288  test    r12, r12
0x18001028b  jnz     loc_180010316
0x180010291  mov     rdi, [rbp+3Fh+Block]
0x180010295  test    rdi, rdi
0x180010298  jnz     loc_180010604
0x18001029e  test    r14, r14
0x1800102a1  jz      loc_18000FFA3
0x1800102a7  lea     r9, ??1?$Pair@VCComBSTR@ATL@@V12@@CompatibilityMarkupProcessorImpl@@QEAA@XZ; void (*)(void *)
0x1800102ae  mov     edx, 10h; unsigned __int64
0x1800102b3  mov     r8d, 19h; unsigned __int64
0x1800102b9  mov     rcx, r14; void *
0x1800102bc  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1800102c1  nop
0x1800102c2  mov     rcx, r14; Block
0x1800102c5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800102ca  jmp     loc_18000FFA3
0x1800102cf  mov     rcx, [rbp+3Fh+var_90]
0x1800102d3  test    rcx, rcx
0x1800102d6  jz      short loc_1800102E5
0x1800102d8  mov     rax, [rcx]
0x1800102db  mov     rax, [rax+10h]
0x1800102df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102e4  nop
0x1800102e5  mov     rcx, [rbp+3Fh+var_A0]
0x1800102e9  test    rcx, rcx
0x1800102ec  jz      short loc_1800102FB
0x1800102ee  mov     rax, [rcx]
0x1800102f1  mov     rax, [rax+10h]
0x1800102f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102fa  nop
0x1800102fb  mov     rcx, [rbp+3Fh+var_A8]
0x1800102ff  test    rcx, rcx
0x180010302  jz      short loc_180010311
0x180010304  mov     rax, [rcx]
  ... truncated ...
```
