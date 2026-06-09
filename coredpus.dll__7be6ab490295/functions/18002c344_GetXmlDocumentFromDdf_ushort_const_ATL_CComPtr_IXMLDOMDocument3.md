# GetXmlDocumentFromDdf(ushort const *,ATL::CComPtr<IXMLDOMDocument3> &)

- ea: `0x18002c344`
- end: `0x18002c709`
- name: `?GetXmlDocumentFromDdf@@YAJPEBGAEAV?$CComPtr@UIXMLDOMDocument3@@@ATL@@@Z`
- size: `965`
- prototype: `__int64 __fastcall(unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012d80`
- `0x18002d6bc`

## callees

- `0x180001280`
- `0x180001ae0`
- `0x180011d9c`
- `0x180028a28`
- `0x18002b808`
- `0x18002c344`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002c650`
- `OLEAUT32!__imp_SysAllocString` at `0x18002c650`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c414`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c492`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c577`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c414`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c492`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c577`
- `OLEAUT32!__imp_VariantClear` at `0x18002c425`
- `OLEAUT32!__imp_VariantClear` at `0x18002c4a3`
- `OLEAUT32!__imp_VariantClear` at `0x18002c4dc`
- `OLEAUT32!__imp_VariantClear` at `0x18002c566`
- `OLEAUT32!__imp_VariantClear` at `0x18002c638`
- `OLEAUT32!__imp_VariantClear` at `0x18002c6a0`
- `OLEAUT32!__imp_VariantClear` at `0x18002c425`
- `OLEAUT32!__imp_VariantClear` at `0x18002c4a3`
- `OLEAUT32!__imp_VariantClear` at `0x18002c4dc`
- `OLEAUT32!__imp_VariantClear` at `0x18002c566`
- `OLEAUT32!__imp_VariantClear` at `0x18002c638`
- `OLEAUT32!__imp_VariantClear` at `0x18002c6a0`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18002c4ff`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18002c4ff`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18002c510`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18002c510`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002c389`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002c389`

## string_xrefs

- `0x18002c649`: `XPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall GetXmlDocumentFromDdf(unsigned __int16 *a1, LPVOID *a2)
{
  HRESULT Instance; // ebx
  __int64 v5; // rdx
  LPVOID v7; // rdi
  __int64 (__fastcall *v8)(LPVOID, _QWORD, VARIANTARG *); // rbx
  _QWORD *v9; // rax
  LPVOID v10; // rdi
  __int64 (__fastcall *v11)(LPVOID, _QWORD, VARIANTARG *); // rbx
  __int128 v12; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  _QWORD *v14; // rax
  LPVOID v15; // rdi
  __int64 v16; // r15
  BSTR *v17; // rbx
  BSTR v18; // rax
  UINT v19; // eax
  __int16 v20; // dx
  int v21; // ecx
  int v22; // r8d
  int v23; // r9d
  LPVOID v24; // rbx
  __int64 v25; // rdi
  int ppv; // [rsp+28h] [rbp-69h]
  unsigned __int16 *v27; // [rsp+48h] [rbp-49h] BYREF
  const char *v28; // [rsp+50h] [rbp-41h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-39h] BYREF
  VARIANTARG v30[2]; // [rsp+78h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F0h] [rbp+5Fh]
  __int16 v32; // [rsp+100h] [rbp+6Fh] BYREF
  BSTR bstrString; // [rsp+108h] [rbp+77h] BYREF
  HRESULT v34; // [rsp+110h] [rbp+7Fh] BYREF

  v32 = 0;
  Instance = CoCreateInstance(
               &GUID_88d96a05_f192_11d4_a65f_0040963251e5,
               0,
               0x17u,
               &GUID_2933bf96_7b36_11d2_b20e_00c04f983e60,
               a2);
  if ( Instance < 0 )
  {
    v5 = 53;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\admin\\dm\\coredpus\\wapdpu\\ddfinfo.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
    return (unsigned int)Instance;
  }
  v7 = *a2;
  v8 = *(__int64 (__fastcall **)(LPVOID, _QWORD, VARIANTARG *))(*(_QWORD *)*a2 + 640LL);
  pvarg.vt = 3;
  pvarg.lVal = 0;
  v9 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"ProhibitDTD");
  v30[0] = pvarg;
  Instance = v8(v7, *v9, v30);
  SysFreeString(bstrString);
  VariantClear(&pvarg);
  if ( Instance < 0 )
  {
    v5 = 54;
    goto LABEL_3;
  }
  v10 = *a2;
  v11 = *(__int64 (__fastcall **)(LPVOID, _QWORD, VARIANTARG *))(*(_QWORD *)*a2 + 640LL);
  pvarg.vt = 3;
  pvarg.lVal = 0;
  v12 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  v14 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"ValidateOnParse");
  *(_OWORD *)&v30[0].vt = v12;
  v30[0].pRecInfo = pRecInfo;
  Instance = v11(v10, *v14, v30);
  SysFreeString(bstrString);
  VariantClear(&pvarg);
  if ( Instance < 0 )
  {
    v5 = 55;
    goto LABEL_3;
  }
  v15 = *a2;
  v16 = *(_QWORD *)*a2;
  v17 = (BSTR *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, a1);
  pvarg.vt = 0;
  VariantClear(&pvarg);
  pvarg.vt = 8;
  if ( *v17 )
  {
    v19 = SysStringByteLen(*v17);
    v18 = SysAllocStringByteLen((LPCSTR)*v17, v19);
  }
  else
  {
    v18 = 0;
  }
  pvarg.llVal = (LONGLONG)v18;
  if ( !v18 && *v17 )
  {
    pvarg.vt = 10;
    pvarg.lVal = -2147024882;
    ATL::AtlThrowImpl(SHIDWORD(v18));
  }
  v30[0] = pvarg;
  Instance = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int16 *))(v16 + 464))(v15, v30, &v32);
  VariantClear(&pvarg);
  SysFreeString(bstrString);
  if ( Instance < 0 || (v20 = v32) == 0 )
  {
    if ( (unsigned int)dword_18003E080 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18003E080, 0x200000000000LL) )
    {
      LODWORD(bstrString) = v32;
      v34 = Instance;
      v27 = a1;
      v28 = "Failed to load DDF";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v21,
        (unsigned int)&unk_180037D70,
        v22,
        v23,
        (__int64)&v28,
        (__int64)&v27,
        (__int64)&v34,
        (__int64)&bstrString);
    }
    if ( Instance < 0 )
    {
      v5 = 71;
      goto LABEL_3;
    }
    v20 = v32;
  }
  if ( !v20 )
  {
    Instance = -2102788095;
    v5 = 72;
    goto LABEL_3;
  }
  v24 = *a2;
  v25 = *(_QWORD *)*a2;
  pvarg.vt = 0;
  VariantClear(&pvarg);
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)SysAllocString(L"XPath");
  if ( !pvarg.llVal )
  {
    pvarg.vt = 10;
    pvarg.lVal = -2147024882;
    ATL::AtlThrowImpl(pvarg.cyVal.Hi);
  }
  v30[0] = pvarg;
  Instance = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, VARIANTARG *))(v25 + 640))(
               v24,
               L"SelectionLanguage",
               v30);
  VariantClear(&pvarg);
  if ( Instance < 0 )
  {
    v5 = 73;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x18002c344  mov     rax, rsp
0x18002c347  push    rbp
0x18002c348  push    rbx
0x18002c349  push    rsi
0x18002c34a  push    rdi
0x18002c34b  push    r13
0x18002c34d  push    r14
0x18002c34f  push    r15
0x18002c351  lea     rbp, [rax-5Fh]
0x18002c355  sub     rsp, 0B0h
0x18002c35c  movaps  xmmword ptr [rax-48h], xmm6
0x18002c360  movaps  xmmword ptr [rax-58h], xmm7
0x18002c364  mov     rsi, rdx
0x18002c367  mov     r14, rcx
0x18002c36a  xor     eax, eax
0x18002c36c  mov     [rbp+57h+arg_8], ax
0x18002c370  mov     [rsp+0E0h+ppv], rdx; int
0x18002c375  lea     r9, _GUID_2933bf96_7b36_11d2_b20e_00c04f983e60; riid
0x18002c37c  xor     edx, edx; pUnkOuter
0x18002c37e  lea     r8d, [rax+17h]; dwClsContext
0x18002c382  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x18002c389  call    cs:__imp_CoCreateInstance
0x18002c390  nop     dword ptr [rax+rax+00h]
0x18002c395  mov     ebx, eax
0x18002c397  test    eax, eax
0x18002c399  jns     short loc_18002C3BA
0x18002c39b  mov     edx, 35h ; '5'; void *
0x18002c3a0  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\dm\\coredpus\\wapdpu"...
0x18002c3a7  mov     r9d, ebx; char *
0x18002c3aa  mov     rcx, [rbp+5Fh]; this
0x18002c3ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c3b3  mov     eax, ebx
0x18002c3b5  jmp     loc_18002C6BC
0x18002c3ba  mov     rdi, [rsi]
0x18002c3bd  mov     rax, [rdi]
0x18002c3c0  mov     rbx, [rax+280h]
0x18002c3c7  mov     r15d, 3
0x18002c3cd  mov     word ptr [rbp+57h+pvarg], r15w
0x18002c3d2  mov     dword ptr [rbp+57h+pvarg+8], 0
0x18002c3d9  movups  xmm6, xmmword ptr [rbp+57h+pvarg]
0x18002c3dd  movsd   xmm7, qword ptr [rbp+57h+pvarg+10h]
0x18002c3e2  lea     rdx, aProhibitdtd; "ProhibitDTD"
0x18002c3e9  lea     rcx, [rbp+57h+bstrString]; this
0x18002c3ed  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18002c3f2  nop
0x18002c3f3  movaps  [rbp+57h+var_70], xmm6
0x18002c3f7  movsd   [rbp+57h+var_60], xmm7
0x18002c3fc  lea     r8, [rbp+57h+var_70]
0x18002c400  mov     rdx, [rax]
0x18002c403  mov     rcx, rdi
0x18002c406  mov     rax, rbx
0x18002c409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c40e  mov     ebx, eax
0x18002c410  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18002c414  call    cs:__imp_SysFreeString
0x18002c41b  nop     dword ptr [rax+rax+00h]
0x18002c420  nop
0x18002c421  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002c425  call    cs:__imp_VariantClear
0x18002c42c  nop     dword ptr [rax+rax+00h]
0x18002c431  test    ebx, ebx
0x18002c433  jns     short loc_18002C43E
0x18002c435  lea     edx, [r15+33h]
0x18002c439  jmp     loc_18002C3A0
0x18002c43e  mov     rdi, [rsi]
0x18002c441  mov     rax, [rdi]
0x18002c444  mov     rbx, [rax+280h]
0x18002c44b  mov     word ptr [rbp+57h+pvarg], r15w
0x18002c450  mov     dword ptr [rbp+57h+pvarg+8], 0
0x18002c457  movups  xmm6, xmmword ptr [rbp+57h+pvarg]
0x18002c45b  movsd   xmm7, qword ptr [rbp+57h+pvarg+10h]
0x18002c460  lea     rdx, aValidateonpars; "ValidateOnParse"
0x18002c467  lea     rcx, [rbp+57h+bstrString]; this
0x18002c46b  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18002c470  nop
0x18002c471  movaps  [rbp+57h+var_70], xmm6
0x18002c475  movsd   [rbp+57h+var_60], xmm7
0x18002c47a  lea     r8, [rbp+57h+var_70]
0x18002c47e  mov     rdx, [rax]
0x18002c481  mov     rcx, rdi
0x18002c484  mov     rax, rbx
0x18002c487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c48c  mov     ebx, eax
0x18002c48e  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18002c492  call    cs:__imp_SysFreeString
0x18002c499  nop     dword ptr [rax+rax+00h]
0x18002c49e  nop
0x18002c49f  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002c4a3  call    cs:__imp_VariantClear
0x18002c4aa  nop     dword ptr [rax+rax+00h]
0x18002c4af  test    ebx, ebx
0x18002c4b1  jns     short loc_18002C4BD
0x18002c4b3  mov     edx, 37h ; '7'
0x18002c4b8  jmp     loc_18002C3A0
0x18002c4bd  mov     rdi, [rsi]
0x18002c4c0  mov     r15, [rdi]
0x18002c4c3  mov     rdx, r14; unsigned __int16 *
0x18002c4c6  lea     rcx, [rbp+57h+bstrString]; this
0x18002c4ca  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18002c4cf  mov     rbx, rax
0x18002c4d2  xor     ecx, ecx
0x18002c4d4  mov     word ptr [rbp+57h+pvarg], cx
0x18002c4d8  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002c4dc  call    cs:__imp_VariantClear
0x18002c4e3  nop     dword ptr [rax+rax+00h]
0x18002c4e8  mov     r13d, 8
0x18002c4ee  mov     word ptr [rbp+57h+pvarg], r13w
0x18002c4f3  mov     rcx, [rbx]; bstr
0x18002c4f6  test    rcx, rcx
0x18002c4f9  jnz     short loc_18002C4FF
0x18002c4fb  xor     eax, eax
0x18002c4fd  jmp     short loc_18002C51C
0x18002c4ff  call    cs:__imp_SysStringByteLen
0x18002c506  nop     dword ptr [rax+rax+00h]
0x18002c50b  mov     edx, eax; len
0x18002c50d  mov     rcx, [rbx]; psz
0x18002c510  call    cs:__imp_SysAllocStringByteLen
0x18002c517  nop     dword ptr [rax+rax+00h]
0x18002c51c  mov     dword ptr [rbp+57h+pvarg+8], eax
0x18002c51f  mov     rcx, rax
0x18002c522  sar     rcx, 20h; int
0x18002c526  mov     dword ptr [rbp+57h+pvarg+0Ch], ecx
0x18002c529  test    rax, rax
0x18002c52c  jnz     short loc_18002C537
0x18002c52e  cmp     [rbx], rax
0x18002c531  jnz     loc_18002C6F3
0x18002c537  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x18002c53b  movaps  [rbp+57h+var_70], xmm0
0x18002c53f  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x18002c544  movsd   [rbp+57h+var_60], xmm1
0x18002c549  lea     r8, [rbp+57h+arg_8]
0x18002c54d  lea     rdx, [rbp+57h+var_70]
0x18002c551  mov     rcx, rdi
0x18002c554  mov     rax, [r15+1D0h]
0x18002c55b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c560  mov     ebx, eax
0x18002c562  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002c566  call    cs:__imp_VariantClear
0x18002c56d  nop     dword ptr [rax+rax+00h]
0x18002c572  nop
0x18002c573  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18002c577  call    cs:__imp_SysFreeString
0x18002c57e  nop     dword ptr [rax+rax+00h]
0x18002c583  test    ebx, ebx
0x18002c585  js      short loc_18002C596
0x18002c587  xor     ecx, ecx
0x18002c589  movzx   edx, [rbp+57h+arg_8]
0x18002c58d  cmp     cx, dx
0x18002c590  jnz     loc_18002C616
0x18002c596  mov     eax, cs:dword_18003E080
0x18002c59c  cmp     eax, 2
0x18002c59f  jbe     short loc_18002C604
0x18002c5a1  mov     rdx, 200000000000h
0x18002c5ab  lea     rcx, dword_18003E080
0x18002c5b2  call    _tlgKeywordOn
0x18002c5b7  test    al, al
0x18002c5b9  jz      short loc_18002C604
0x18002c5bb  movsx   eax, [rbp+57h+arg_8]
0x18002c5bf  mov     dword ptr [rbp+57h+bstrString], eax
0x18002c5c2  mov     [rbp+57h+arg_18], ebx
0x18002c5c5  mov     [rbp+57h+var_A0], r14
0x18002c5c9  lea     rax, aFailedToLoadDd; "Failed to load DDF"
0x18002c5d0  mov     [rbp+57h+var_98], rax
0x18002c5d4  lea     rax, [rbp+57h+bstrString]
0x18002c5d8  mov     [rsp+0E0h+var_A8], rax
0x18002c5dd  lea     rax, [rbp+57h+arg_18]
0x18002c5e1  mov     [rsp+0E0h+var_B0], rax
0x18002c5e6  lea     rax, [rbp+57h+var_A0]
0x18002c5ea  mov     [rsp+0E0h+var_B8], rax
0x18002c5ef  lea     rax, [rbp+57h+var_98]
0x18002c5f3  mov     [rsp+0E0h+ppv], rax
0x18002c5f8  lea     rdx, unk_180037D70
0x18002c5ff  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002c604  test    ebx, ebx
0x18002c606  jns     short loc_18002C612
0x18002c608  mov     edx, 47h ; 'G'
0x18002c60d  jmp     loc_18002C3A0
0x18002c612  movzx   edx, [rbp+57h+arg_8]
0x18002c616  xor     eax, eax
0x18002c618  cmp     ax, dx
0x18002c61b  jnz     short loc_18002C62A
0x18002c61d  mov     ebx, 82AA0001h
0x18002c622  lea     edx, [rax+48h]
0x18002c625  jmp     loc_18002C3A0
0x18002c62a  mov     rbx, [rsi]
0x18002c62d  mov     rdi, [rbx]
0x18002c630  mov     word ptr [rbp+57h+pvarg], ax
0x18002c634  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002c638  call    cs:__imp_VariantClear
0x18002c63f  nop     dword ptr [rax+rax+00h]
0x18002c644  mov     word ptr [rbp+57h+pvarg], r13w
0x18002c649  lea     rcx, aXpath; "XPath"
0x18002c650  call    cs:__imp_SysAllocString
0x18002c657  nop     dword ptr [rax+rax+00h]
0x18002c65c  mov     dword ptr [rbp+57h+pvarg+8], eax
0x18002c65f  mov     rcx, rax
0x18002c662  sar     rcx, 20h; int
0x18002c666  mov     dword ptr [rbp+57h+pvarg+0Ch], ecx
0x18002c669  test    rax, rax
0x18002c66c  jz      short loc_18002C6DD
0x18002c66e  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x18002c672  movaps  [rbp+57h+var_70], xmm0
0x18002c676  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x18002c67b  movsd   [rbp+57h+var_60], xmm1
0x18002c680  lea     r8, [rbp+57h+var_70]
0x18002c684  lea     rdx, aSelectionlangu; "SelectionLanguage"
0x18002c68b  mov     rcx, rbx
0x18002c68e  mov     rax, [rdi+280h]
0x18002c695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c69a  mov     ebx, eax
0x18002c69c  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002c6a0  call    cs:__imp_VariantClear
0x18002c6a7  nop     dword ptr [rax+rax+00h]
0x18002c6ac  test    ebx, ebx
0x18002c6ae  jns     short loc_18002C6BA
0x18002c6b0  mov     edx, 49h ; 'I'
0x18002c6b5  jmp     loc_18002C3A0
0x18002c6ba  xor     eax, eax
0x18002c6bc  lea     r11, [rsp+0E0h+var_30]
0x18002c6c4  movaps  xmm6, xmmword ptr [r11-10h]
0x18002c6c9  movaps  xmm7, xmmword ptr [r11-20h]
0x18002c6ce  mov     rsp, r11
0x18002c6d1  pop     r15
0x18002c6d3  pop     r14
0x18002c6d5  pop     r13
0x18002c6d7  pop     rdi
0x18002c6d8  pop     rsi
0x18002c6d9  pop     rbx
0x18002c6da  pop     rbp
0x18002c6db  retn
0x18002c6dd  mov     eax, 0Ah
0x18002c6e2  mov     word ptr [rbp+57h+pvarg], ax
0x18002c6e6  mov     dword ptr [rbp+57h+pvarg+8], 8007000Eh
0x18002c6ed  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002c6f3  mov     eax, 0Ah
0x18002c6f8  mov     word ptr [rbp+57h+pvarg], ax
0x18002c6fc  mov     dword ptr [rbp+57h+pvarg+8], 8007000Eh
0x18002c703  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
