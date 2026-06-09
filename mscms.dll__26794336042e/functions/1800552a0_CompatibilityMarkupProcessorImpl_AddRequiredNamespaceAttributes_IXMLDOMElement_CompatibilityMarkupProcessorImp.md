# CompatibilityMarkupProcessorImpl::AddRequiredNamespaceAttributes(IXMLDOMElement *,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> const *,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> const *)

- ea: `0x1800552a0`
- end: `0x18005551f`
- name: `?AddRequiredNamespaceAttributes@CompatibilityMarkupProcessorImpl@@AEAAJPEAUIXMLDOMElement@@PEBU?$Vector@VCComBSTR@ATL@@$0BJ@@1@1@Z`
- size: `639`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800557c4`

## callees

- `0x1800089d8`
- `0x1800098b0`
- `0x18001aa80`
- `0x18001c800`
- `0x1800286cc`
- `0x18002eab4`
- `0x18004bed8`
- `0x1800552a0`
- `0x180084010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18005540b`
- `OLEAUT32!__imp_SysAllocString` at `0x18005540b`
- `OLEAUT32!__imp_SysFreeString` at `0x18005546c`
- `OLEAUT32!__imp_SysFreeString` at `0x180055476`
- `OLEAUT32!__imp_SysFreeString` at `0x18005548a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800554c1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800554cb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800554d6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800554e0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800554fe`
- `OLEAUT32!__imp_SysFreeString` at `0x18005546c`
- `OLEAUT32!__imp_SysFreeString` at `0x180055476`
- `OLEAUT32!__imp_SysFreeString` at `0x18005548a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800554c1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800554cb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800554d6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800554e0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800554fe`
- `OLEAUT32!__imp_SysStringLen` at `0x1800552f8`
- `OLEAUT32!__imp_SysStringLen` at `0x1800552f8`
- `OLEAUT32!__imp_VariantInit` at `0x1800553b6`
- `OLEAUT32!__imp_VariantInit` at `0x1800553b6`
- `OLEAUT32!__imp_VariantClear` at `0x1800553f9`
- `OLEAUT32!__imp_VariantClear` at `0x18005544e`
- `OLEAUT32!__imp_VariantClear` at `0x180055462`
- `OLEAUT32!__imp_VariantClear` at `0x1800554b7`
- `OLEAUT32!__imp_VariantClear` at `0x1800553f9`
- `OLEAUT32!__imp_VariantClear` at `0x18005544e`
- `OLEAUT32!__imp_VariantClear` at `0x180055462`
- `OLEAUT32!__imp_VariantClear` at `0x1800554b7`

## string_xrefs

- `0x180055350`: `xmlns`
- `0x180055365`: `xmlns`

## pseudocode

```c
__int64 __fastcall CompatibilityMarkupProcessorImpl::AddRequiredNamespaceAttributes(
        unsigned __int16 *a1,
        __int64 *a2,
        __int64 a3,
        __int64 a4)
{
  int i; // r15d
  OLECHAR *v6; // rdi
  UINT v7; // eax
  __int64 v8; // rsi
  unsigned __int64 v9; // rbx
  unsigned __int16 *v10; // r14
  int v11; // eax
  OLECHAR *v12; // rsi
  OLECHAR *v13; // rbx
  __int64 *v14; // r12
  int v15; // eax
  int v16; // r14d
  __int64 v17; // r14
  OLECHAR *psz; // [rsp+38h] [rbp-49h] BYREF
  BSTR bstrString; // [rsp+40h] [rbp-41h] BYREF
  VARIANTARG v21; // [rsp+48h] [rbp-39h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp-21h] BYREF
  VARIANTARG v23; // [rsp+78h] [rbp-9h] BYREF
  unsigned __int16 *v24; // [rsp+E8h] [rbp+67h] BYREF
  __int64 *v25; // [rsp+F0h] [rbp+6Fh]
  BSTR pbstr; // [rsp+F8h] [rbp+77h] BYREF
  __int64 v27; // [rsp+100h] [rbp+7Fh]

  v27 = a4;
  v25 = a2;
  v24 = a1;
  for ( i = 0; i < *(_DWORD *)(a3 + 200); ++i )
  {
    ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&pbstr, (const struct ATL::CComBSTR *)(a3 + 8LL * i));
    v6 = pbstr;
    v7 = SysStringLen(pbstr);
    v8 = v7;
    v9 = v7 + 7LL;
    if ( !v7 )
      v9 = 6;
    v10 = (unsigned __int16 *)operator new[](saturated_mul(v9, 2u));
    v24 = 0;
    NCoreLibrary::TGenericSP<LuvColorF,NCoreLibrary::TAutoPtrArray<LuvColorF>,LuvColorF *,0,LuvColorF const *>::Reset(&v24);
    v24 = v10;
    if ( v8 )
      v11 = StringCchPrintfW(v10, v9, L"%s:%s", L"xmlns", v6);
    else
      v11 = StringCchCopyW(v10, v9, L"xmlns");
    if ( v11 < 0 )
    {
      v16 = v11;
      goto LABEL_21;
    }
    ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, v10);
    ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&psz, *(const unsigned __int16 **)(v27 + 8LL * i));
    v12 = psz;
    v13 = bstrString;
    if ( !bstrString || !psz )
    {
      SysFreeString(psz);
      SysFreeString(v13);
      v16 = -2147024882;
      goto LABEL_21;
    }
    VariantInit(&pvarg);
    v14 = v25;
    v15 = (*(__int64 (__fastcall **)(__int64 *, OLECHAR *, VARIANTARG *))(*v25 + 352))(v25, v13, &pvarg);
    v16 = v15;
    if ( v15 < 0 )
      goto LABEL_18;
    if ( v15 == 1 )
    {
      v17 = *v14;
      v21.vt = 0;
      VariantClear(&v21);
      v21.vt = 8;
      v21.llVal = (LONGLONG)SysAllocString(v12);
      if ( !v21.llVal )
      {
        if ( v12 )
        {
          v21.vt = 10;
          v21.lVal = -2147024882;
          ATL::AtlThrowImpl(-2147024882);
        }
      }
      v23 = v21;
      v16 = (*(__int64 (__fastcall **)(__int64 *, OLECHAR *, VARIANTARG *))(v17 + 360))(v14, v13, &v23);
      VariantClear(&v21);
      if ( v16 < 0 )
      {
LABEL_18:
        VariantClear(&pvarg);
        SysFreeString(v12);
        SysFreeString(v13);
LABEL_21:
        NCoreLibrary::TGenericSP<LuvColorF,NCoreLibrary::TAutoPtrArray<LuvColorF>,LuvColorF *,0,LuvColorF const *>::Reset(&v24);
        SysFreeString(v6);
        return (unsigned int)v16;
      }
    }
    VariantClear(&pvarg);
    SysFreeString(v12);
    SysFreeString(v13);
    NCoreLibrary::TGenericSP<LuvColorF,NCoreLibrary::TAutoPtrArray<LuvColorF>,LuvColorF *,0,LuvColorF const *>::Reset(&v24);
    SysFreeString(v6);
  }
  return 0;
}

```

## disassembly

```asm
0x1800552a0  mov     rax, rsp
0x1800552a3  mov     [rax+20h], r9
0x1800552a7  mov     [rax+10h], rdx
0x1800552ab  mov     [rax+8], rcx
0x1800552af  push    rbp
0x1800552b0  push    rbx
0x1800552b1  push    rsi
0x1800552b2  push    rdi
0x1800552b3  push    r12
0x1800552b5  push    r13
0x1800552b7  push    r14
0x1800552b9  push    r15
0x1800552bb  lea     rbp, [rax-5Fh]
0x1800552bf  sub     rsp, 98h
0x1800552c6  mov     r13, r8
0x1800552c9  xor     r15d, r15d
0x1800552cc  cmp     r15d, [r13+0C8h]
0x1800552d3  jge     loc_180055509
0x1800552d9  movsxd  r12, r15d
0x1800552dc  lea     rdx, ds:0[r12*8]
0x1800552e4  add     rdx, r13; struct ATL::CComBSTR *
0x1800552e7  lea     rcx, [rbp+57h+pbstr]; this
0x1800552eb  call    ??0CComBSTR@ATL@@QEAA@AEBV01@@Z; ATL::CComBSTR::CComBSTR(ATL::CComBSTR const &)
0x1800552f0  nop
0x1800552f1  mov     rdi, [rbp+57h+pbstr]
0x1800552f5  mov     rcx, rdi; pbstr
0x1800552f8  call    cs:__imp_SysStringLen
0x1800552fe  mov     esi, eax
0x180055300  test    eax, eax
0x180055302  lea     rbx, [rsi+7]
0x180055306  jnz     short loc_18005530D
0x180055308  mov     ebx, 6
0x18005530d  mov     eax, 2
0x180055312  mul     rbx
0x180055315  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18005531c  cmovb   rax, rcx
0x180055320  mov     rcx, rax; unsigned __int64
0x180055323  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180055328  mov     r14, rax
0x18005532b  mov     [rbp+57h+arg_0], 0
0x180055333  lea     rcx, [rbp+57h+arg_0]
0x180055337  call    ?Reset@?$TGenericSP@ULuvColorF@@V?$TAutoPtrArray@ULuvColorF@@@NCoreLibrary@@PEAU1@$0A@PEBU1@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<LuvColorF,NCoreLibrary::TAutoPtrArray<LuvColorF>,LuvColorF *,0,LuvColorF const *>::Reset(void)
0x18005533c  mov     [rbp+57h+arg_0], r14
0x180055340  mov     rdx, rbx; unsigned __int64
0x180055343  mov     rcx, r14; unsigned __int16 *
0x180055346  test    rsi, rsi
0x180055349  jz      short loc_180055365
0x18005534b  mov     [rsp+20h], rdi
0x180055350  lea     r9, aXmlns; "xmlns"
0x180055357  lea     r8, aSS_1; "%s:%s"
0x18005535e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180055363  jmp     short loc_180055371
0x180055365  lea     r8, aXmlns; "xmlns"
0x18005536c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180055371  test    eax, eax
0x180055373  js      loc_1800554EE
0x180055379  mov     rdx, r14; unsigned __int16 *
0x18005537c  lea     rcx, [rbp+57h+bstrString]; this
0x180055380  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180055385  nop
0x180055386  mov     rax, [rbp+57h+arg_18]
0x18005538a  mov     rdx, [rax+r12*8]; unsigned __int16 *
0x18005538e  lea     rcx, [rbp+57h+psz]; this
0x180055392  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180055397  nop
0x180055398  mov     rsi, [rbp+57h+psz]
0x18005539c  mov     rbx, [rbp+57h+bstrString]
0x1800553a0  test    rbx, rbx
0x1800553a3  jz      loc_1800554D3
0x1800553a9  test    rsi, rsi
0x1800553ac  jz      loc_1800554D3
0x1800553b2  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800553b6  call    cs:__imp_VariantInit
0x1800553bc  nop
0x1800553bd  mov     r12, [rbp+57h+arg_8]
0x1800553c1  mov     rax, [r12]
0x1800553c5  lea     r8, [rbp+57h+pvarg]
0x1800553c9  mov     rdx, rbx
0x1800553cc  mov     rcx, r12
0x1800553cf  mov     rax, [rax+160h]
0x1800553d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800553db  mov     r14d, eax
0x1800553de  test    eax, eax
0x1800553e0  js      loc_1800554B3
0x1800553e6  cmp     eax, 1
0x1800553e9  jnz     short loc_18005545E
0x1800553eb  mov     r14, [r12]
0x1800553ef  xor     eax, eax
0x1800553f1  mov     word ptr [rbp+57h+var_90], ax
0x1800553f5  lea     rcx, [rbp+57h+var_90]; pvarg
0x1800553f9  call    cs:__imp_VariantClear
0x1800553ff  mov     eax, 8
0x180055404  mov     word ptr [rbp+57h+var_90], ax
0x180055408  mov     rcx, rsi; psz
0x18005540b  call    cs:__imp_SysAllocString
0x180055411  mov     qword ptr [rbp+57h+var_90+8], rax
0x180055415  test    rax, rax
0x180055418  jnz     short loc_18005541F
0x18005541a  test    rsi, rsi
0x18005541d  jnz     short loc_180055498
0x18005541f  movups  xmm0, xmmword ptr [rbp+57h+var_90]
0x180055423  movaps  [rbp+57h+var_60], xmm0
0x180055427  movsd   xmm1, qword ptr [rbp+57h+var_90+10h]
0x18005542c  movsd   [rbp+57h+var_50], xmm1
0x180055431  lea     r8, [rbp+57h+var_60]
0x180055435  mov     rdx, rbx
0x180055438  mov     rcx, r12
0x18005543b  mov     rax, [r14+168h]
0x180055442  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055447  mov     r14d, eax
0x18005544a  lea     rcx, [rbp+57h+var_90]; pvarg
0x18005544e  call    cs:__imp_VariantClear
0x180055454  mov     eax, r14d
0x180055457  shr     eax, 1Fh
0x18005545a  test    al, al
0x18005545c  jnz     short loc_1800554B3
0x18005545e  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180055462  call    cs:__imp_VariantClear
0x180055468  nop
0x180055469  mov     rcx, rsi; bstrString
0x18005546c  call    cs:__imp_SysFreeString
0x180055472  nop
0x180055473  mov     rcx, rbx; bstrString
0x180055476  call    cs:__imp_SysFreeString
0x18005547c  nop
0x18005547d  lea     rcx, [rbp+57h+arg_0]
0x180055481  call    ?Reset@?$TGenericSP@ULuvColorF@@V?$TAutoPtrArray@ULuvColorF@@@NCoreLibrary@@PEAU1@$0A@PEBU1@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<LuvColorF,NCoreLibrary::TAutoPtrArray<LuvColorF>,LuvColorF *,0,LuvColorF const *>::Reset(void)
0x180055486  nop
0x180055487  mov     rcx, rdi; bstrString
0x18005548a  call    cs:__imp_SysFreeString
0x180055490  inc     r15d
0x180055493  jmp     loc_1800552CC
0x180055498  mov     eax, 0Ah
0x18005549d  mov     word ptr [rbp+57h+var_90], ax
0x1800554a1  mov     dword ptr [rbp+57h+var_90+8], 8007000Eh
0x1800554a8  mov     ecx, 8007000Eh; int
0x1800554ad  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800554b3  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800554b7  call    cs:__imp_VariantClear
0x1800554bd  nop
0x1800554be  mov     rcx, rsi; bstrString
0x1800554c1  call    cs:__imp_SysFreeString
0x1800554c7  nop
0x1800554c8  mov     rcx, rbx; bstrString
0x1800554cb  call    cs:__imp_SysFreeString
0x1800554d1  jmp     short loc_1800554F1
0x1800554d3  mov     rcx, rsi; bstrString
0x1800554d6  call    cs:__imp_SysFreeString
0x1800554dc  nop
0x1800554dd  mov     rcx, rbx; bstrString
0x1800554e0  call    cs:__imp_SysFreeString
0x1800554e6  mov     r14d, 8007000Eh
0x1800554ec  jmp     short loc_1800554F1
0x1800554ee  mov     r14d, eax
0x1800554f1  lea     rcx, [rbp+57h+arg_0]
0x1800554f5  call    ?Reset@?$TGenericSP@ULuvColorF@@V?$TAutoPtrArray@ULuvColorF@@@NCoreLibrary@@PEAU1@$0A@PEBU1@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<LuvColorF,NCoreLibrary::TAutoPtrArray<LuvColorF>,LuvColorF *,0,LuvColorF const *>::Reset(void)
0x1800554fa  nop
0x1800554fb  mov     rcx, rdi; bstrString
0x1800554fe  call    cs:__imp_SysFreeString
0x180055504  mov     eax, r14d
0x180055507  jmp     short loc_18005550B
0x180055509  xor     eax, eax
0x18005550b  add     rsp, 98h
0x180055512  pop     r15
0x180055514  pop     r14
0x180055516  pop     r13
0x180055518  pop     r12
0x18005551a  pop     rdi
0x18005551b  pop     rsi
0x18005551c  pop     rbx
0x18005551d  pop     rbp
0x18005551e  retn
```
