# DataStoreServer::Load(ushort const *,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &)

- ea: `0x1800093cc`
- end: `0x180009af2`
- name: `?Load@DataStoreServer@@AEAAJPEBGAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z`
- size: `1830`
- prototype: `__int64 __fastcall(__int64, const OLECHAR *, LPVOID *)`
- caller_count: `7`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800079fc`
- `0x180007fb4`
- `0x1800081b8`
- `0x1800086c8`
- `0x18000a334`
- `0x18000a4a0`
- `0x18000b210`

## callees

- `0x180002310`
- `0x1800071ac`
- `0x180007460`
- `0x18000750c`
- `0x1800076dc`
- `0x18000784c`
- `0x180007894`
- `0x180007938`
- `0x1800093cc`
- `0x18000c08c`
- `0x18000d990`
- `0x18000db68`
- `0x18000db7c`
- `0x180010010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000949b`
- `OLEAUT32!__imp_SysAllocString` at `0x18000949b`
- `OLEAUT32!__imp_VariantClear` at `0x180009520`
- `OLEAUT32!__imp_VariantClear` at `0x1800098db`
- `OLEAUT32!__imp_VariantClear` at `0x180009520`
- `OLEAUT32!__imp_VariantClear` at `0x1800098db`

## string_xrefs

- `0x180009432`: `IXMLDOMDocument2::CreateInstance failed %!hresult!`
- `0x180009558`: `IXMLDOMDocument2::load failed with %S`

## pseudocode

```c
__int64 __fastcall DataStoreServer::Load(__int64 a1, const OLECHAR *a2, LPVOID *a3)
{
  __int64 v5; // rdi
  struct IUnknown *v6; // rsi
  int Instance; // ebx
  struct IUnknown *v9; // rbx
  int v10; // eax
  struct IUnknown *v11; // rbx
  BSTR v12; // rax
  int v13; // eax
  bool v14; // bl
  HRESULT v15; // eax
  int v16; // r8d
  int v17; // r9d
  struct IUnknown *v18; // rbx
  int v19; // eax
  struct IUnknown *v20; // rbx
  _bstr_t *v21; // rbx
  struct _bstr_t *v22; // rax
  __int64 v23; // rcx
  int v24; // eax
  __int64 v25; // r14
  _QWORD *v26; // rax
  struct _bstr_t *v27; // rax
  int v28; // eax
  __int64 v29; // r14
  _QWORD *v30; // rax
  struct _bstr_t *v31; // rax
  int v32; // eax
  struct _bstr_t *v33; // rax
  _bstr_t *v34; // rax
  HRESULT v35; // eax
  int v36; // r8d
  int v37; // r9d
  __int64 v38; // [rsp+30h] [rbp-E8h] BYREF
  __int64 v39; // [rsp+38h] [rbp-E0h] BYREF
  __int64 v40; // [rsp+40h] [rbp-D8h] BYREF
  __int64 v41; // [rsp+48h] [rbp-D0h] BYREF
  __int64 v42; // [rsp+50h] [rbp-C8h] BYREF
  __int64 *v43; // [rsp+58h] [rbp-C0h] BYREF
  _QWORD *v44; // [rsp+60h] [rbp-B8h] BYREF
  _QWORD *v45; // [rsp+68h] [rbp-B0h] BYREF
  VARIANTARG pvarg; // [rsp+70h] [rbp-A8h] BYREF
  struct IUnknown *v47; // [rsp+88h] [rbp-90h]
  char v48[8]; // [rsp+90h] [rbp-88h] BYREF
  char v49[8]; // [rsp+98h] [rbp-80h] BYREF
  char v50[8]; // [rsp+A0h] [rbp-78h] BYREF
  char v51[8]; // [rsp+A8h] [rbp-70h] BYREF
  char v52[8]; // [rsp+B0h] [rbp-68h] BYREF
  _BYTE v53[24]; // [rsp+B8h] [rbp-60h] BYREF
  VARIANTARG v54; // [rsp+D0h] [rbp-48h] BYREF
  struct IUnknown *v55; // [rsp+120h] [rbp+8h] BYREF
  __int64 v56; // [rsp+138h] [rbp+20h] BYREF

  HIDWORD(v55) = HIDWORD(a1);
  v5 = 0;
  LODWORD(v55) = 0;
  v6 = 0;
  v47 = 0;
  Instance = _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::CreateInstance(a3);
  if ( Instance >= 0 )
  {
    v9 = (struct IUnknown *)*a3;
    if ( !*a3 )
      _com_issue_error(-2147467261);
    v10 = ((__int64 (__fastcall *)(LPVOID, _QWORD))v9->lpVtbl[21].QueryInterface)(*a3, 0);
    if ( v10 < 0 )
      _com_issue_errorex(v10, v9, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60);
    v11 = (struct IUnknown *)*a3;
    if ( !*a3 )
      _com_issue_error(-2147467261);
    v12 = SysAllocString(a2);
    if ( !v12 && a2 )
      _com_issue_error(-2147024882);
    pvarg.vt = 8;
    pvarg.llVal = (LONGLONG)v12;
    LOWORD(v55) = 0;
    v54 = pvarg;
    v13 = ((__int64 (__fastcall *)(struct IUnknown *, VARIANTARG *, struct IUnknown **))v11->lpVtbl[19].AddRef)(
            v11,
            &v54,
            &v55);
    if ( v13 < 0 )
      _com_issue_errorex(v13, v11, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60);
    v14 = (_WORD)v55 != 0xFFFF;
    v15 = VariantClear(&pvarg);
    if ( v15 < 0 )
      _com_issue_error(v15);
    if ( v14 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WppDbgPrint("IXMLDOMDocument2::load failed with %S");
        WPP_SF_sS(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, v16, v17, (__int64)a2);
      }
      v18 = (struct IUnknown *)*a3;
      if ( !*a3 )
        _com_issue_error(-2147467261);
      v55 = 0;
      v19 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v18->lpVtbl[20].QueryInterface)(v18, &v55);
      if ( v19 < 0 )
        _com_issue_errorex(v19, v18, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60);
      v20 = v55;
      if ( v55 )
      {
        v6 = v55;
        v47 = v55;
        ((void (__fastcall *)(struct IUnknown *))v55->lpVtbl->AddRef)(v55);
      }
      if ( v20 )
        ((void (__fastcall *)(struct IUnknown *))v20->lpVtbl->Release)(v20);
      v21 = _bstr_t::_bstr_t((_bstr_t *)v53, "\n=====================");
      v22 = _bstr_t::_bstr_t((_bstr_t *)v52, "\nReason: ");
      v23 = *(_QWORD *)v21;
      v42 = v23;
      if ( v23 )
        _InterlockedAdd((volatile signed __int32 *)(v23 + 16), 1u);
      LODWORD(v55) = 3;
      _bstr_t::operator+=((struct _bstr_t *)&v42, v22);
      if ( !v6 )
        _com_issue_error(-2147467261);
      v56 = 0;
      v24 = ((__int64 (__fastcall *)(struct IUnknown *, __int64 *))v6->lpVtbl[3].QueryInterface)(v6, &v56);
      if ( v24 < 0 )
        _com_issue_errorex(v24, v6, &GUID_3efaa426_272f_11d2_836f_0000f87a7782);
      v25 = v56;
      v26 = operator new(0x18u);
      v45 = v26;
      if ( v26 )
      {
        v26[1] = 0;
        *((_DWORD *)v26 + 4) = 1;
        *v26 = v25;
      }
      else
      {
        v26 = 0;
      }
      v45 = v26;
      if ( !v26 )
        _com_issue_error(-2147024882);
      v41 = v42;
      if ( v42 )
        _InterlockedAdd((volatile signed __int32 *)(v42 + 16), 1u);
      LODWORD(v55) = 15;
      _bstr_t::operator+=((struct _bstr_t *)&v41, (struct _bstr_t *)&v45);
      v27 = _bstr_t::_bstr_t((_bstr_t *)v51, "\nSource: ");
      v40 = v41;
      if ( v41 )
        _InterlockedAdd((volatile signed __int32 *)(v41 + 16), 1u);
      LODWORD(v55) = 31;
      _bstr_t::operator+=((struct _bstr_t *)&v40, v27);
      v56 = 0;
      v28 = ((__int64 (__fastcall *)(struct IUnknown *, __int64 *))v6->lpVtbl[3].AddRef)(v6, &v56);
      if ( v28 < 0 )
        _com_issue_errorex(v28, v6, &GUID_3efaa426_272f_11d2_836f_0000f87a7782);
      v29 = v56;
      v30 = operator new(0x18u);
      v44 = v30;
      if ( v30 )
      {
        v30[1] = 0;
        *((_DWORD *)v30 + 4) = 1;
        *v30 = v29;
      }
      else
      {
        v30 = 0;
      }
      v44 = v30;
      if ( !v30 )
        _com_issue_error(-2147024882);
      v39 = v40;
      if ( v40 )
        _InterlockedAdd((volatile signed __int32 *)(v40 + 16), 1u);
      LODWORD(v55) = 127;
      _bstr_t::operator+=((struct _bstr_t *)&v39, (struct _bstr_t *)&v44);
      v31 = _bstr_t::_bstr_t((_bstr_t *)v50, "\nLine: ");
      v38 = v39;
      if ( v39 )
        _InterlockedAdd((volatile signed __int32 *)(v39 + 16), 1u);
      LODWORD(v55) = 255;
      _bstr_t::operator+=((struct _bstr_t *)&v38, v31);
      LODWORD(v56) = 0;
      v32 = ((__int64 (__fastcall *)(struct IUnknown *, __int64 *))v6->lpVtbl[3].Release)(v6, &v56);
      if ( v32 < 0 )
        _com_issue_errorex(v32, v6, &GUID_3efaa426_272f_11d2_836f_0000f87a7782);
      pvarg.vt = 3;
      pvarg.lVal = v56;
      v33 = _bstr_t::_bstr_t((_bstr_t *)v49, (const struct _variant_t *)&pvarg);
      v56 = v38;
      if ( v38 )
        _InterlockedAdd((volatile signed __int32 *)(v38 + 16), 1u);
      LODWORD(v55) = 511;
      _bstr_t::operator+=((struct _bstr_t *)&v56, v33);
      v34 = _bstr_t::_bstr_t((_bstr_t *)v48, "\n");
      _bstr_t::operator+(&v56, &v43, v34);
      _bstr_t::~_bstr_t((_bstr_t *)v48);
      LODWORD(v55) = 255;
      _bstr_t::~_bstr_t((_bstr_t *)&v56);
      _bstr_t::~_bstr_t((_bstr_t *)v49);
      v35 = VariantClear(&pvarg);
      if ( v35 < 0 )
        _com_issue_error(v35);
      _bstr_t::~_bstr_t((_bstr_t *)&v38);
      _bstr_t::~_bstr_t((_bstr_t *)v50);
      _bstr_t::~_bstr_t((_bstr_t *)&v39);
      _bstr_t::~_bstr_t((_bstr_t *)&v44);
      _bstr_t::~_bstr_t((_bstr_t *)&v40);
      _bstr_t::~_bstr_t((_bstr_t *)v51);
      _bstr_t::~_bstr_t((_bstr_t *)&v41);
      _bstr_t::~_bstr_t((_bstr_t *)&v45);
      _bstr_t::~_bstr_t((_bstr_t *)&v42);
      _bstr_t::~_bstr_t((_bstr_t *)v52);
      _bstr_t::~_bstr_t((_bstr_t *)v53);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WppDbgPrint("%S");
        if ( v43 )
          v5 = *v43;
        WPP_SF_sS(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, v36, v37, v5);
      }
      _bstr_t::~_bstr_t((_bstr_t *)&v43);
      ((void (__fastcall *)(struct IUnknown *))v6->lpVtbl->Release)(v6);
      return 2147500037LL;
    }
    else
    {
      return 0;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WppDbgPrint("IXMLDOMDocument2::CreateInstance failed %!hresult!");
      WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids);
    }
    return (unsigned int)Instance;
  }
}

```

## disassembly

```asm
0x1800093cc  mov     rax, rsp
0x1800093cf  mov     [rax+10h], rbx
0x1800093d3  mov     [rax+18h], rsi
0x1800093d7  mov     [rax+8], rcx
0x1800093db  push    rdi
0x1800093dc  push    r12
0x1800093de  push    r13
0x1800093e0  push    r14
0x1800093e2  push    r15
0x1800093e4  sub     rsp, 0F0h
0x1800093eb  mov     r14, r8
0x1800093ee  mov     r15, rdx
0x1800093f1  xor     edi, edi
0x1800093f3  mov     [rax+8], edi
0x1800093f6  mov     esi, edi
0x1800093f8  mov     [rax-90h], rdi
0x1800093ff  lea     r9d, [rdi+17h]
0x180009403  mov     rcx, r8; ppv
0x180009406  call    ?CreateInstance@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEAAJAEBU_GUID@@PEAUIUnknown@@K@Z; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::CreateInstance(_GUID const &,IUnknown *,ulong)
0x18000940b  mov     ebx, eax
0x18000940d  test    eax, eax
0x18000940f  jns     short loc_180009464
0x180009411  lea     r12, WPP_GLOBAL_Control
0x180009418  mov     rcx, cs:WPP_GLOBAL_Control
0x18000941f  cmp     rcx, r12
0x180009422  jz      short loc_18000945D
0x180009424  cmp     byte ptr [rcx+19h], 2
0x180009428  jb      short loc_18000945D
0x18000942a  test    byte ptr [rcx+1Ch], 10h
0x18000942e  jz      short loc_18000945D
0x180009430  mov     edx, eax
0x180009432  lea     rcx, aIxmldomdocumen_3; "IXMLDOMDocument2::CreateInstance failed"...
0x180009439  call    WppDbgPrint
0x18000943e  lea     edx, [rdi+35h]
0x180009441  mov     dword ptr [rsp+118h+var_F8], ebx
0x180009445  lea     r8, WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids
0x18000944c  mov     rcx, cs:WPP_GLOBAL_Control
0x180009453  mov     rcx, [rcx+10h]
0x180009457  call    WPP_SF_sd
0x18000945c  nop
0x18000945d  mov     eax, ebx
0x18000945f  jmp     loc_180009A12
0x180009464  mov     rbx, [r14]
0x180009467  test    rbx, rbx
0x18000946a  jz      loc_180009A2F
0x180009470  mov     rax, [rbx]
0x180009473  xor     edx, edx
0x180009475  mov     rcx, rbx
0x180009478  mov     rax, [rax+1F8h]
0x18000947f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009484  test    eax, eax
0x180009486  js      loc_180009A39
0x18000948c  mov     rbx, [r14]
0x18000948f  test    rbx, rbx
0x180009492  jz      loc_180009A4A
0x180009498  mov     rcx, r15; psz
0x18000949b  call    cs:__imp_SysAllocString
0x1800094a1  test    rax, rax
0x1800094a4  jnz     short loc_1800094AF
0x1800094a6  test    r15, r15
0x1800094a9  jnz     loc_180009A54
0x1800094af  mov     ecx, 8
0x1800094b4  mov     word ptr [rsp+118h+pvarg], cx
0x1800094b9  mov     qword ptr [rsp+118h+pvarg+8], rax
0x1800094be  mov     word ptr [rsp+118h+arg_0], di
0x1800094c6  movups  xmm0, xmmword ptr [rsp+118h+pvarg]
0x1800094cb  movaps  [rsp+118h+var_48], xmm0
0x1800094d3  movsd   xmm1, qword ptr [rsp+118h+pvarg+10h]
0x1800094dc  movsd   [rsp+118h+var_38], xmm1
0x1800094e5  mov     rax, [rbx]
0x1800094e8  lea     r8, [rsp+118h+arg_0]
0x1800094f0  lea     rdx, [rsp+118h+var_48]
0x1800094f8  mov     rcx, rbx
0x1800094fb  mov     rax, [rax+1D0h]
0x180009502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009507  test    eax, eax
0x180009509  js      loc_180009A5F
0x18000950f  cmp     word ptr [rsp+118h+arg_0], 0FFFFh
0x180009518  setnz   bl
0x18000951b  lea     rcx, [rsp+118h+pvarg]; pvarg
0x180009520  call    cs:__imp_VariantClear
0x180009526  test    eax, eax
0x180009528  js      loc_180009A71
0x18000952e  test    bl, bl
0x180009530  jz      loc_1800099ED
0x180009536  lea     r12, WPP_GLOBAL_Control
0x18000953d  mov     rax, cs:WPP_GLOBAL_Control
0x180009544  cmp     rax, r12
0x180009547  jz      short loc_18000957E
0x180009549  cmp     byte ptr [rax+19h], 2
0x18000954d  jb      short loc_18000957E
0x18000954f  test    byte ptr [rax+1Ch], 10h
0x180009553  jz      short loc_18000957E
0x180009555  mov     rdx, r15
0x180009558  lea     rcx, aIxmldomdocumen_2; "IXMLDOMDocument2::load failed with %S"
0x18000955f  call    WppDbgPrint
0x180009564  mov     edx, 36h ; '6'
0x180009569  mov     [rsp+118h+var_F8], r15
0x18000956e  mov     rcx, cs:WPP_GLOBAL_Control
0x180009575  mov     rcx, [rcx+10h]
0x180009579  call    WPP_SF_sS
0x18000957e  mov     rbx, [r14]
0x180009581  test    rbx, rbx
0x180009584  jz      loc_180009A79
0x18000958a  mov     [rsp+118h+arg_0], rdi
0x180009592  mov     rax, [rbx]
0x180009595  lea     rdx, [rsp+118h+arg_0]
0x18000959d  mov     rcx, rbx
0x1800095a0  mov     rax, [rax+1E0h]
0x1800095a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095ac  test    eax, eax
0x1800095ae  js      loc_180009A83
0x1800095b4  mov     rbx, [rsp+118h+arg_0]
0x1800095bc  test    rbx, rbx
0x1800095bf  jz      short loc_1800095DC
0x1800095c1  mov     rsi, rbx
0x1800095c4  mov     [rsp+118h+var_90], rbx
0x1800095cc  mov     rax, [rbx]
0x1800095cf  mov     rcx, rbx
0x1800095d2  mov     rax, [rax+8]
0x1800095d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095db  nop
0x1800095dc  test    rbx, rbx
0x1800095df  jz      short loc_1800095F1
0x1800095e1  mov     rax, [rbx]
0x1800095e4  mov     rcx, rbx
0x1800095e7  mov     rax, [rax+10h]
0x1800095eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095f0  nop
0x1800095f1  lea     rdx, asc_180015048; "\n====================="
0x1800095f8  lea     rcx, [rsp+118h+var_60]; this
0x180009600  call    ??0_bstr_t@@QEAA@PEBD@Z; _bstr_t::_bstr_t(char const *)
0x180009605  mov     rbx, rax
0x180009608  lea     rdx, aReason; "\nReason: "
0x18000960f  lea     rcx, [rsp+118h+var_68]; this
0x180009617  call    ??0_bstr_t@@QEAA@PEBD@Z; _bstr_t::_bstr_t(char const *)
0x18000961c  nop
0x18000961d  mov     rcx, [rbx]
0x180009620  mov     [rsp+118h+var_C8], rcx
0x180009625  mov     ebx, 1
0x18000962a  test    rcx, rcx
0x18000962d  jz      short loc_180009633
0x18000962f  lock add [rcx+10h], ebx
0x180009633  mov     r13d, 3
0x180009639  mov     dword ptr [rsp+118h+arg_0], r13d
0x180009641  mov     rdx, rax; struct _bstr_t *
0x180009644  lea     rcx, [rsp+118h+var_C8]; struct _bstr_t *
0x180009649  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x18000964e  test    rsi, rsi
0x180009651  jz      loc_180009A95
0x180009657  mov     [rsp+118h+arg_18], rdi
0x18000965f  mov     rax, [rsi]
0x180009662  lea     rdx, [rsp+118h+arg_18]
0x18000966a  mov     rcx, rsi
0x18000966d  mov     rax, [rax+48h]
0x180009671  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009676  test    eax, eax
0x180009678  js      loc_180009A9F
0x18000967e  mov     r14, [rsp+118h+arg_18]
0x180009686  mov     r15d, 18h
0x18000968c  mov     ecx, r15d; Size
0x18000968f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009694  mov     [rsp+118h+var_B0], rax
0x180009699  test    rax, rax
0x18000969c  jz      short loc_1800096AA
0x18000969e  mov     [rax+8], rdi
0x1800096a2  mov     [rax+10h], ebx
0x1800096a5  mov     [rax], r14
0x1800096a8  jmp     short loc_1800096AD
0x1800096aa  mov     rax, rdi
0x1800096ad  mov     [rsp+118h+var_B0], rax
0x1800096b2  test    rax, rax
0x1800096b5  jz      loc_180009AB0
0x1800096bb  mov     rax, [rsp+118h+var_C8]
0x1800096c0  mov     [rsp+118h+var_D0], rax
0x1800096c5  test    rax, rax
0x1800096c8  jz      short loc_1800096CE
0x1800096ca  lock add [rax+10h], ebx
0x1800096ce  mov     dword ptr [rsp+118h+arg_0], 0Fh
0x1800096d9  lea     rdx, [rsp+118h+var_B0]; struct _bstr_t *
0x1800096de  lea     rcx, [rsp+118h+var_D0]; struct _bstr_t *
0x1800096e3  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x1800096e8  lea     rdx, aSource; "\nSource: "
0x1800096ef  lea     rcx, [rsp+118h+var_70]; this
0x1800096f7  call    ??0_bstr_t@@QEAA@PEBD@Z; _bstr_t::_bstr_t(char const *)
0x1800096fc  nop
0x1800096fd  mov     rcx, [rsp+118h+var_D0]
0x180009702  mov     [rsp+118h+var_D8], rcx
0x180009707  test    rcx, rcx
0x18000970a  jz      short loc_180009710
0x18000970c  lock add [rcx+10h], ebx
0x180009710  mov     dword ptr [rsp+118h+arg_0], 1Fh
0x18000971b  mov     rdx, rax; struct _bstr_t *
0x18000971e  lea     rcx, [rsp+118h+var_D8]; struct _bstr_t *
0x180009723  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x180009728  mov     [rsp+118h+arg_18], rdi
0x180009730  mov     rax, [rsi]
0x180009733  lea     rdx, [rsp+118h+arg_18]
0x18000973b  mov     rcx, rsi
0x18000973e  mov     rax, [rax+50h]
0x180009742  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009747  test    eax, eax
0x180009749  js      loc_180009ABB
0x18000974f  mov     r14, [rsp+118h+arg_18]
0x180009757  mov     rcx, r15; Size
0x18000975a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000975f  mov     [rsp+118h+var_B8], rax
0x180009764  test    rax, rax
0x180009767  jz      short loc_180009775
0x180009769  mov     [rax+8], rdi
0x18000976d  mov     [rax+10h], ebx
0x180009770  mov     [rax], r14
0x180009773  jmp     short loc_180009778
0x180009775  mov     rax, rdi
0x180009778  mov     [rsp+118h+var_B8], rax
0x18000977d  test    rax, rax
0x180009780  jz      loc_180009ACC
0x180009786  mov     rax, [rsp+118h+var_D8]
0x18000978b  mov     [rsp+118h+var_E0], rax
0x180009790  test    rax, rax
0x180009793  jz      short loc_180009799
0x180009795  lock add [rax+10h], ebx
0x180009799  mov     dword ptr [rsp+118h+arg_0], 7Fh
0x1800097a4  lea     rdx, [rsp+118h+var_B8]; struct _bstr_t *
0x1800097a9  lea     rcx, [rsp+118h+var_E0]; struct _bstr_t *
0x1800097ae  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x1800097b3  lea     rdx, aLine; "\nLine: "
0x1800097ba  lea     rcx, [rsp+118h+var_78]; this
0x1800097c2  call    ??0_bstr_t@@QEAA@PEBD@Z; _bstr_t::_bstr_t(char const *)
0x1800097c7  nop
0x1800097c8  mov     rcx, [rsp+118h+var_E0]
0x1800097cd  mov     [rsp+118h+var_E8], rcx
0x1800097d2  test    rcx, rcx
0x1800097d5  jz      short loc_1800097DB
0x1800097d7  lock add [rcx+10h], ebx
0x1800097db  mov     r14d, 0FFh
0x1800097e1  mov     dword ptr [rsp+118h+arg_0], r14d
0x1800097e9  mov     rdx, rax; struct _bstr_t *
0x1800097ec  lea     rcx, [rsp+118h+var_E8]; struct _bstr_t *
0x1800097f1  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x1800097f6  mov     dword ptr [rsp+118h+arg_18], edi
0x1800097fd  mov     rax, [rsi]
0x180009800  lea     rdx, [rsp+118h+arg_18]
0x180009808  mov     rcx, rsi
0x18000980b  mov     rax, [rax+58h]
0x18000980f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009814  test    eax, eax
0x180009816  js      loc_180009AD7
0x18000981c  mov     word ptr [rsp+118h+pvarg], r13w
0x180009822  mov     eax, dword ptr [rsp+118h+arg_18]
0x180009829  mov     word ptr [rsp+118h+pvarg+8], ax
0x18000982e  sar     eax, 10h
0x180009831  mov     word ptr [rsp+118h+pvarg+0Ah], ax
0x180009836  lea     rdx, [rsp+118h+pvarg]; struct _variant_t *
0x18000983b  lea     rcx, [rsp+118h+var_80]; this
0x180009843  call    ??0_bstr_t@@QEAA@AEBV_variant_t@@@Z; _bstr_t::_bstr_t(_variant_t const &)
0x180009848  nop
0x180009849  mov     rcx, [rsp+118h+var_E8]
0x18000984e  mov     [rsp+118h+arg_18], rcx
0x180009856  test    rcx, rcx
0x180009859  jz      short loc_18000985F
0x18000985b  lock add [rcx+10h], ebx
0x18000985f  mov     dword ptr [rsp+118h+arg_0], 1FFh
0x18000986a  mov     rdx, rax; struct _bstr_t *
0x18000986d  lea     rcx, [rsp+118h+arg_18]; struct _bstr_t *
0x180009875  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x18000987a  lea     rdx, asc_180015088; "\n"
0x180009881  lea     rcx, [rsp+118h+var_88]; this
0x180009889  call    ??0_bstr_t@@QEAA@PEBD@Z; _bstr_t::_bstr_t(char const *)
0x18000988e  nop
0x18000988f  mov     r8, rax
0x180009892  lea     rdx, [rsp+118h+var_C0]
0x180009897  lea     rcx, [rsp+118h+arg_18]
0x18000989f  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x1800098a4  nop
0x1800098a5  lea     rcx, [rsp+118h+var_88]; this
0x1800098ad  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800098b2  mov     dword ptr [rsp+118h+arg_0], r14d
0x1800098ba  lea     rcx, [rsp+118h+arg_18]; this
0x1800098c2  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800098c7  nop
0x1800098c8  lea     rcx, [rsp+118h+var_80]; this
0x1800098d0  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800098d5  nop
0x1800098d6  lea     rcx, [rsp+118h+pvarg]; pvarg
0x1800098db  call    cs:__imp_VariantClear
0x1800098e1  test    eax, eax
0x1800098e3  js      loc_180009AE9
0x1800098e9  lea     rcx, [rsp+118h+var_E8]; this
0x1800098ee  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800098f3  nop
0x1800098f4  lea     rcx, [rsp+118h+var_78]; this
0x1800098fc  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180009901  nop
0x180009902  lea     rcx, [rsp+118h+var_E0]; this
0x180009907  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18000990c  nop
0x18000990d  lea     rcx, [rsp+118h+var_B8]; this
0x180009912  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180009917  nop
  ... truncated ...
```
