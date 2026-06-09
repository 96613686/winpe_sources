# GetTuneXmlNodeFromBSTR(ushort *,IXMLDOMNode * *)

- ea: `0x1800540b8`
- end: `0x180054409`
- name: `?GetTuneXmlNodeFromBSTR@@YAJPEAGPEAPEAUIXMLDOMNode@@@Z`
- size: `849`
- prototype: `__int64 __fastcall(BSTR pbstr, struct IXMLDOMNode **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180054410`

## callees

- `0x180006b38`
- `0x18001424c`
- `0x1800540b8`
- `0x1800544a8`
- `0x180054cec`
- `0x1800f8010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180054108`
- `ole32!CoCreateInstance` at `0x180054108`
- `OLEAUT32!__imp_SysFreeString` at `0x1800541d1`
- `OLEAUT32!__imp_SysFreeString` at `0x180054297`
- `OLEAUT32!__imp_SysFreeString` at `0x1800542ca`
- `OLEAUT32!__imp_SysFreeString` at `0x180054326`
- `OLEAUT32!__imp_SysFreeString` at `0x180054345`
- `OLEAUT32!__imp_SysFreeString` at `0x1800541d1`
- `OLEAUT32!__imp_SysFreeString` at `0x180054297`
- `OLEAUT32!__imp_SysFreeString` at `0x1800542ca`
- `OLEAUT32!__imp_SysFreeString` at `0x180054326`
- `OLEAUT32!__imp_SysFreeString` at `0x180054345`
- `OLEAUT32!__imp_VariantClear` at `0x180054262`
- `OLEAUT32!__imp_VariantClear` at `0x180054262`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall GetTuneXmlNodeFromBSTR(BSTR pbstr, struct IXMLDOMNode **a2)
{
  HRESULT v5; // esi
  int v6; // eax
  bool v7; // sf
  int v8; // ebx
  OLECHAR *v9; // rcx
  int TuneXmlSchema; // ebx
  LPVOID v11; // rdi
  __int64 (__fastcall *v12)(LPVOID, __int128 *); // rbx
  __int64 v13; // rax
  int v14; // ebx
  OLECHAR *v15; // rbx
  int v16; // eax
  int v17; // edi
  OLECHAR *v18; // rcx
  int v19; // eax
  int v20; // eax
  struct IXMLDOMNode *v21; // rax
  struct IXMLDOMNode *v22; // [rsp+30h] [rbp-39h] BYREF
  __int64 v23; // [rsp+38h] [rbp-31h] BYREF
  BSTR bstrString; // [rsp+40h] [rbp-29h] BYREF
  __int64 v25; // [rsp+48h] [rbp-21h] BYREF
  BSTR v26; // [rsp+50h] [rbp-19h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-11h] BYREF
  __int128 v28; // [rsp+70h] [rbp+7h] BYREF
  __int64 v29; // [rsp+80h] [rbp+17h]
  __int16 v30; // [rsp+D8h] [rbp+6Fh] BYREF
  LPVOID ppv; // [rsp+E0h] [rbp+77h] BYREF
  struct IDispatch *v32; // [rsp+E8h] [rbp+7Fh] BYREF

  if ( !a2 )
    return 2147500035LL;
  ppv = 0;
  v5 = CoCreateInstance(&CLSID_DOMDocument60, 0, 0x17u, &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60, &ppv);
  if ( v5 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 560LL))(ppv, 0xFFFFFFFFLL);
    v7 = v6 < 0;
    if ( v6 || (v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 544LL))(ppv, 0), v7 = v6 < 0, v6) )
    {
      v5 = -2147467259;
      if ( v7 )
        v5 = v6;
      goto LABEL_49;
    }
    v30 = 0;
    v5 = -2147467259;
    if ( (*(unsigned int (__fastcall **)(LPVOID, BSTR, __int16 *))(*(_QWORD *)ppv + 520LL))(ppv, pbstr, &v30) || !v30 )
      goto LABEL_16;
    v32 = 0;
    v8 = (*(__int64 (__fastcall **)(LPVOID, struct IDispatch **))(*(_QWORD *)ppv + 632LL))(ppv, &v32);
    if ( v8 )
    {
      v9 = 0;
      bstrString = 0;
      if ( v32 )
      {
        ((void (__fastcall *)(struct IDispatch *, BSTR *))v32->lpVtbl[1].Release)(v32, &bstrString);
        v9 = bstrString;
      }
      v8 = -2147467259;
      SysFreeString(v9);
    }
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v32);
    if ( v8 < 0 )
    {
LABEL_16:
      v32 = 0;
      TuneXmlSchema = GetTuneXmlSchema((struct IXMLDOMSchemaCollection2 **)&v32);
      if ( TuneXmlSchema < 0 )
      {
LABEL_17:
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v32);
        v5 = TuneXmlSchema;
        goto LABEL_49;
      }
      v11 = ppv;
      v12 = *(__int64 (__fastcall **)(LPVOID, __int128 *))(*(_QWORD *)ppv + 624LL);
      v13 = ATL::CComVariant::CComVariant((ATL::CComVariant *)&pvarg, v32);
      v28 = *(_OWORD *)v13;
      v29 = *(_QWORD *)(v13 + 16);
      v14 = v12(v11, &v28);
      if ( pvarg.vt == 4095 )
        pvarg.vt = 8;
      VariantClear(&pvarg);
      if ( v14 )
      {
        if ( v14 < 0 )
          v5 = v14;
        goto LABEL_23;
      }
      bstrString = 0;
      TuneXmlSchema = WrapTuneXmlFragment(pbstr, &bstrString);
      if ( TuneXmlSchema < 0 )
      {
        SysFreeString(bstrString);
        goto LABEL_17;
      }
      v15 = bstrString;
      v16 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int16 *))(*(_QWORD *)ppv + 520LL))(ppv, bstrString, &v30);
      if ( v16 )
      {
        if ( v16 < 0 )
          v5 = v16;
        goto LABEL_29;
      }
      if ( !v30 )
      {
LABEL_29:
        SysFreeString(v15);
LABEL_23:
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v32);
        goto LABEL_49;
      }
      v25 = 0;
      v17 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 632LL))(ppv, &v25);
      if ( v17 )
      {
        v18 = 0;
        v26 = 0;
        if ( v25 )
        {
          (*(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v25 + 72LL))(v25, &v26);
          v18 = v26;
        }
        if ( v17 < 0 )
          v5 = v17;
        SysFreeString(v18);
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v25);
        goto LABEL_29;
      }
      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v25);
      SysFreeString(v15);
      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v32);
    }
    v23 = 0;
    v19 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 360LL))(ppv, &v23);
    if ( v19 )
    {
      if ( v19 < 0 )
        v5 = v19;
    }
    else
    {
      v22 = 0;
      v20 = (*(__int64 (__fastcall **)(__int64, struct IXMLDOMNode **))(*(_QWORD *)v23 + 104LL))(v23, &v22);
      if ( !v20 )
      {
        v21 = v22;
        if ( v22 )
        {
          v22 = 0;
          *a2 = v21;
          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v22);
          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v23);
          v5 = 0;
        }
        else
        {
          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v22);
          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v23);
          v5 = -2147418113;
        }
        goto LABEL_49;
      }
      if ( v20 < 0 )
        v5 = v20;
      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v22);
    }
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v23);
  }
LABEL_49:
  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&ppv);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800540b8  push    rbp
0x1800540ba  push    rbx
0x1800540bb  push    rsi
0x1800540bc  push    rdi
0x1800540bd  push    r12
0x1800540bf  push    r14
0x1800540c1  push    r15
0x1800540c3  lea     rbp, [rsp-27h]
0x1800540c8  sub     rsp, 90h
0x1800540cf  mov     r14, rdx
0x1800540d2  mov     r15, rcx
0x1800540d5  xor     r12d, r12d
0x1800540d8  test    rdx, rdx
0x1800540db  jnz     short loc_1800540E7
0x1800540dd  mov     eax, 80004003h
0x1800540e2  jmp     loc_1800543F7
0x1800540e7  mov     [rbp+57h+arg_10], r12
0x1800540eb  lea     rax, [rbp+57h+arg_10]
0x1800540ef  mov     [rsp+0C0h+ppv], rax; ppv
0x1800540f4  lea     r9, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; riid
0x1800540fb  xor     edx, edx; pUnkOuter
0x1800540fd  lea     r8d, [rdx+17h]; dwClsContext
0x180054101  lea     rcx, CLSID_DOMDocument60; rclsid
0x180054108  call    cs:__imp_CoCreateInstance
0x18005410e  mov     esi, eax
0x180054110  test    eax, eax
0x180054112  js      loc_1800543EC
0x180054118  mov     rcx, [rbp+57h+arg_10]
0x18005411c  mov     rax, [rcx]
0x18005411f  or      edx, 0FFFFFFFFh
0x180054122  mov     rax, [rax+230h]
0x180054129  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005412e  test    eax, eax
0x180054130  jz      short loc_18005413F
0x180054132  mov     esi, 80004005h
0x180054137  cmovs   esi, eax
0x18005413a  jmp     loc_1800543EC
0x18005413f  mov     rcx, [rbp+57h+arg_10]
0x180054143  mov     rax, [rcx]
0x180054146  xor     edx, edx
0x180054148  mov     rax, [rax+220h]
0x18005414f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054154  test    eax, eax
0x180054156  jnz     short loc_180054132
0x180054158  mov     [rbp+57h+arg_8], r12w
0x18005415d  mov     rcx, [rbp+57h+arg_10]
0x180054161  mov     rax, [rcx]
0x180054164  lea     r8, [rbp+57h+arg_8]
0x180054168  mov     rdx, r15
0x18005416b  mov     rax, [rax+208h]
0x180054172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054177  mov     esi, 80004005h
0x18005417c  test    eax, eax
0x18005417e  jnz     short loc_1800541E9
0x180054180  cmp     [rbp+57h+arg_8], r12w
0x180054185  jz      short loc_1800541E9
0x180054187  mov     [rbp+57h+arg_18], r12
0x18005418b  mov     rcx, [rbp+57h+arg_10]
0x18005418f  mov     rax, [rcx]
0x180054192  lea     rdx, [rbp+57h+arg_18]
0x180054196  mov     rax, [rax+278h]
0x18005419d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800541a2  mov     ebx, eax
0x1800541a4  test    eax, eax
0x1800541a6  jz      short loc_1800541D8
0x1800541a8  mov     rcx, r12
0x1800541ab  mov     [rbp+57h+bstrString], rcx
0x1800541af  mov     r8, [rbp+57h+arg_18]
0x1800541b3  test    r8, r8
0x1800541b6  jz      short loc_1800541CF
0x1800541b8  mov     rax, [r8]
0x1800541bb  lea     rdx, [rbp+57h+bstrString]
0x1800541bf  mov     rcx, r8
0x1800541c2  mov     rax, [rax+48h]
0x1800541c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800541cb  mov     rcx, [rbp+57h+bstrString]; bstrString
0x1800541cf  mov     ebx, esi
0x1800541d1  call    cs:__imp_SysFreeString
0x1800541d7  nop
0x1800541d8  lea     rcx, [rbp+57h+arg_18]
0x1800541dc  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800541e1  test    ebx, ebx
0x1800541e3  jns     loc_180054355
0x1800541e9  mov     [rbp+57h+arg_18], r12
0x1800541ed  lea     rcx, [rbp+57h+arg_18]; struct IXMLDOMSchemaCollection2 **
0x1800541f1  call    ?GetTuneXmlSchema@@YAJPEAPEAUIXMLDOMSchemaCollection2@@@Z; GetTuneXmlSchema(IXMLDOMSchemaCollection2 * *)
0x1800541f6  mov     ebx, eax
0x1800541f8  test    eax, eax
0x1800541fa  jns     short loc_18005420C
0x1800541fc  lea     rcx, [rbp+57h+arg_18]
0x180054200  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180054205  mov     esi, ebx
0x180054207  jmp     loc_1800543EC
0x18005420c  mov     rdi, [rbp+57h+arg_10]
0x180054210  mov     rax, [rdi]
0x180054213  mov     rbx, [rax+270h]
0x18005421a  mov     rdx, [rbp+57h+arg_18]; struct IDispatch *
0x18005421e  lea     rcx, [rbp+57h+pvarg]; this
0x180054222  call    ??0CComVariant@ATL@@QEAA@PEAUIDispatch@@@Z; ATL::CComVariant::CComVariant(IDispatch *)
0x180054227  nop
0x180054228  movups  xmm0, xmmword ptr [rax]
0x18005422b  movaps  [rbp+57h+var_50], xmm0
0x18005422f  movsd   xmm1, qword ptr [rax+10h]
0x180054234  movsd   [rbp+57h+var_40], xmm1
0x180054239  lea     rdx, [rbp+57h+var_50]
0x18005423d  mov     rcx, rdi
0x180054240  mov     rax, rbx
0x180054243  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054248  mov     ebx, eax
0x18005424a  mov     eax, 0FFFh
0x18005424f  cmp     word ptr [rbp+57h+pvarg], ax
0x180054253  jnz     short loc_18005425E
0x180054255  mov     eax, 8
0x18005425a  mov     word ptr [rbp+57h+pvarg], ax
0x18005425e  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180054262  call    cs:__imp_VariantClear
0x180054268  test    ebx, ebx
0x18005426a  jz      short loc_18005427D
0x18005426c  cmovs   esi, ebx
0x18005426f  lea     rcx, [rbp+57h+arg_18]
0x180054273  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180054278  jmp     loc_1800543EC
0x18005427d  mov     [rbp+57h+bstrString], r12
0x180054281  lea     rdx, [rbp+57h+bstrString]; unsigned __int16 **
0x180054285  mov     rcx, r15; pbstr
0x180054288  call    ?WrapTuneXmlFragment@@YAJPEAGPEAPEAG@Z; WrapTuneXmlFragment(ushort *,ushort * *)
0x18005428d  mov     ebx, eax
0x18005428f  test    eax, eax
0x180054291  jns     short loc_1800542A2
0x180054293  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180054297  call    cs:__imp_SysFreeString
0x18005429d  jmp     loc_1800541FC
0x1800542a2  mov     rcx, [rbp+57h+arg_10]
0x1800542a6  mov     rax, [rcx]
0x1800542a9  lea     r8, [rbp+57h+arg_8]
0x1800542ad  mov     rbx, [rbp+57h+bstrString]
0x1800542b1  mov     rdx, rbx
0x1800542b4  mov     rax, [rax+208h]
0x1800542bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800542c0  test    eax, eax
0x1800542c2  jz      short loc_1800542D2
0x1800542c4  cmovs   esi, eax
0x1800542c7  mov     rcx, rbx; bstrString
0x1800542ca  call    cs:__imp_SysFreeString
0x1800542d0  jmp     short loc_18005426F
0x1800542d2  cmp     [rbp+57h+arg_8], r12w
0x1800542d7  jz      short loc_1800542C7
0x1800542d9  mov     [rbp+57h+var_78], r12
0x1800542dd  mov     rcx, [rbp+57h+arg_10]
0x1800542e1  mov     rax, [rcx]
0x1800542e4  lea     rdx, [rbp+57h+var_78]
0x1800542e8  mov     rax, [rax+278h]
0x1800542ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800542f4  mov     edi, eax
0x1800542f6  test    eax, eax
0x1800542f8  jz      short loc_180054338
0x1800542fa  mov     rcx, r12
0x1800542fd  mov     [rbp+57h+var_70], rcx
0x180054301  mov     r8, [rbp+57h+var_78]
0x180054305  test    r8, r8
0x180054308  jz      short loc_180054321
0x18005430a  mov     rcx, [r8]
0x18005430d  mov     rax, [rcx+48h]
0x180054311  lea     rdx, [rbp+57h+var_70]
0x180054315  mov     rcx, r8
0x180054318  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005431d  mov     rcx, [rbp+57h+var_70]; bstrString
0x180054321  test    edi, edi
0x180054323  cmovs   esi, edi
0x180054326  call    cs:__imp_SysFreeString
0x18005432c  nop
0x18005432d  lea     rcx, [rbp+57h+var_78]
0x180054331  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180054336  jmp     short loc_1800542C7
0x180054338  lea     rcx, [rbp+57h+var_78]
0x18005433c  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180054341  nop
0x180054342  mov     rcx, rbx; bstrString
0x180054345  call    cs:__imp_SysFreeString
0x18005434b  nop
0x18005434c  lea     rcx, [rbp+57h+arg_18]
0x180054350  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180054355  mov     [rbp+57h+var_88], r12
0x180054359  mov     rcx, [rbp+57h+arg_10]
0x18005435d  mov     rax, [rcx]
0x180054360  lea     rdx, [rbp+57h+var_88]
0x180054364  mov     rax, [rax+168h]
0x18005436b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054370  test    eax, eax
0x180054372  jz      short loc_180054382
0x180054374  cmovs   esi, eax
0x180054377  lea     rcx, [rbp+57h+var_88]
0x18005437b  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180054380  jmp     short loc_1800543EC
0x180054382  mov     [rbp+57h+var_90], r12
0x180054386  mov     rcx, [rbp+57h+var_88]
0x18005438a  mov     rax, [rcx]
0x18005438d  lea     rdx, [rbp+57h+var_90]
0x180054391  mov     rax, [rax+68h]
0x180054395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005439a  test    eax, eax
0x18005439c  jz      short loc_1800543AC
0x18005439e  cmovs   esi, eax
0x1800543a1  lea     rcx, [rbp+57h+var_90]
0x1800543a5  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800543aa  jmp     short loc_180054377
0x1800543ac  mov     rax, [rbp+57h+var_90]
0x1800543b0  test    rax, rax
0x1800543b3  jnz     short loc_1800543CF
0x1800543b5  lea     rcx, [rbp+57h+var_90]
0x1800543b9  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800543be  nop
0x1800543bf  lea     rcx, [rbp+57h+var_88]
0x1800543c3  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800543c8  mov     esi, 8000FFFFh
0x1800543cd  jmp     short loc_1800543EC
0x1800543cf  mov     [rbp+57h+var_90], r12
0x1800543d3  mov     [r14], rax
0x1800543d6  lea     rcx, [rbp+57h+var_90]
0x1800543da  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800543df  nop
0x1800543e0  lea     rcx, [rbp+57h+var_88]
0x1800543e4  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800543e9  mov     esi, r12d
0x1800543ec  lea     rcx, [rbp+57h+arg_10]
0x1800543f0  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800543f5  mov     eax, esi
0x1800543f7  add     rsp, 90h
0x1800543fe  pop     r15
0x180054400  pop     r14
0x180054402  pop     r12
0x180054404  pop     rdi
0x180054405  pop     rsi
0x180054406  pop     rbx
0x180054407  pop     rbp
0x180054408  retn
```
