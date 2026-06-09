# DataStoreServer::GetTemplates(ushort const *,int &,ushort * &)

- ea: `0x1800086c8`
- end: `0x180008b7b`
- name: `?GetTemplates@DataStoreServer@@QEAAJPEBGAEAHAEAPEAG@Z`
- size: `1203`
- prototype: `int(DataStoreServer *__hidden this, const unsigned __int16 *, int *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180006e00`

## callees

- `0x1800020b1`
- `0x180007150`
- `0x1800071ac`
- `0x180007628`
- `0x1800076dc`
- `0x1800086c8`
- `0x180008ce4`
- `0x1800093cc`
- `0x180009af8`
- `0x18000bf74`
- `0x18000d8f0`
- `0x18000d990`
- `0x18000db68`
- `0x18000db7c`
- `0x180010010`

## import_xrefs

- `KERNEL32!TryEnterCriticalSection` at `0x1800087d2`
- `KERNEL32!TryEnterCriticalSection` at `0x1800087d2`
- `KERNEL32!SwitchToThread` at `0x1800087c9`
- `KERNEL32!SwitchToThread` at `0x1800087c9`
- `KERNEL32!EnterCriticalSection` at `0x1800087e1`
- `KERNEL32!EnterCriticalSection` at `0x1800087e1`
- `KERNEL32!LeaveCriticalSection` at `0x180008ad9`
- `KERNEL32!LeaveCriticalSection` at `0x180008ad9`
- `ole32!CoTaskMemAlloc` at `0x180008a66`
- `ole32!CoTaskMemAlloc` at `0x180008a66`
- `OLEAUT32!__imp_SysStringLen` at `0x180008a47`
- `OLEAUT32!__imp_SysStringLen` at `0x180008a47`

## string_xrefs

- `0x18000877d`: `Invalid parameter for DataStoreServer::GetTemplates`
- `0x180008845`: `DataStoreServer::GetTemplates() failed to load xml text to IAS Dom`
- `0x1800088c4`: `Load failed:%!hresult! in GetTemplates`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall DataStoreServer::GetTemplates(
        DataStoreServer *this,
        const unsigned __int16 *a2,
        int *a3,
        unsigned __int16 **a4)
{
  struct IUnknown *v6; // r14
  struct IUnknown *v7; // rdi
  struct _RTL_CRITICAL_SECTION *v9; // r15
  int v10; // esi
  struct IUnknown **v11; // r15
  __int64 v12; // rcx
  int XML; // esi
  struct IUnknown *v14; // rbx
  int v15; // eax
  struct IUnknown *v16; // rbx
  struct IUnknown **v17; // rax
  struct IUnknown *v18; // rcx
  int v19; // eax
  int v20; // eax
  struct IUnknown *v21; // rbx
  OLECHAR ***v22; // rax
  OLECHAR *v23; // rcx
  UINT v24; // eax
  int *v25; // rbx
  unsigned __int16 *v26; // rax
  void **v27; // r12
  _QWORD *v28; // rdx
  _BYTE v29[8]; // [rsp+30h] [rbp-30h] BYREF
  struct IUnknown *v30; // [rsp+38h] [rbp-28h]
  __int64 v31; // [rsp+40h] [rbp-20h]
  struct IUnknown *v32; // [rsp+48h] [rbp-18h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+50h] [rbp-10h]
  struct IUnknown *v34; // [rsp+A0h] [rbp+40h] BYREF
  int *v35; // [rsp+B0h] [rbp+50h]
  unsigned __int16 **v36; // [rsp+B8h] [rbp+58h]

  v36 = a4;
  v35 = a3;
  v6 = 0;
  v30 = 0;
  v7 = 0;
  v32 = 0;
  if ( !*((_BYTE *)this + 48) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WppDbgPrint("DataStoreServer() is not initialized");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids, "NPSDS");
    }
    return 2147500037LL;
  }
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WppDbgPrint("Invalid parameter for DataStoreServer::GetTemplates");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids, "NPSDS");
    }
    return 2147942487LL;
  }
  v9 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 8);
  v10 = 0;
  while ( !TryEnterCriticalSection(v9) )
  {
    if ( ++v10 >= 100 )
    {
      EnterCriticalSection(v9);
      break;
    }
    SwitchToThread();
  }
  v11 = (struct IUnknown **)((char *)this + 2152);
  if ( IASFileExists((const WCHAR *)this + 286) )
  {
    XML = 0;
    if ( !*v11 )
    {
      XML = DataStoreServer::Load(v12, (const OLECHAR *)this + 286, (LPVOID *)this + 269);
      if ( XML < 0 || !*v11 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          WppDbgPrint("Load failed:%!hresult! in GetTemplates");
          WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids);
        }
        goto LABEL_57;
      }
    }
  }
  else
  {
    XML = DataStoreServer::LoadXML(v12, *((const unsigned __int16 **)this + 275), (LPVOID *)this + 269);
    if ( XML < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WppDbgPrint("DataStoreServer::GetTemplates() failed to load xml text to IAS Dom");
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids, "NPSDS");
      }
      goto LABEL_60;
    }
  }
  v14 = *v11;
  if ( !*v11 )
    _com_issue_error(-2147467261);
  v34 = 0;
  v15 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v14->lpVtbl[15].QueryInterface)(v14, &v34);
  if ( v15 < 0 )
    _com_issue_errorex(v15, v14, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60);
  v16 = v34;
  if ( !v34 )
    _com_issue_error(-2147467261);
  _bstr_t::_bstr_t((_bstr_t *)v29, a2);
  v17 = (struct IUnknown **)MSXML2::IXMLDOMNode::selectNodes(v16);
  v18 = *v17;
  if ( *v17 )
  {
    v6 = *v17;
    v30 = *v17;
    ((void (__fastcall *)(struct IUnknown *))v18->lpVtbl->AddRef)(v18);
  }
  if ( v31 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  ((void (__fastcall *)(struct IUnknown *))v16->lpVtbl->Release)(v16);
  if ( !v6 )
    goto LABEL_59;
  LODWORD(v34) = 0;
  v19 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v6->lpVtbl[2].Release)(v6, &v34);
  if ( v19 < 0 )
    _com_issue_errorex(v19, v6, &GUID_2933bf82_7b36_11d2_b20e_00c04f983e60);
  if ( (_DWORD)v34 != 1 )
  {
LABEL_59:
    XML = -2147024809;
    goto LABEL_60;
  }
  v34 = 0;
  v20 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v6->lpVtbl[3].QueryInterface)(v6, &v34);
  if ( v20 < 0 )
    _com_issue_errorex(v20, v6, &GUID_2933bf82_7b36_11d2_b20e_00c04f983e60);
  v21 = v34;
  if ( v34 )
  {
    v7 = v34;
    v32 = v34;
    ((void (__fastcall *)(struct IUnknown *))v34->lpVtbl->AddRef)(v34);
  }
  if ( v21 )
    ((void (__fastcall *)(struct IUnknown *))v21->lpVtbl->Release)(v21);
  if ( !v7 )
    _com_issue_error(-2147467261);
  v22 = (OLECHAR ***)MSXML2::IXMLDOMNode::Getxml(v7, &v34);
  if ( *v22 && (v23 = **v22) != 0 )
    v24 = SysStringLen(v23);
  else
    v24 = 0;
  v25 = v35;
  *v35 = v24;
  _bstr_t::~_bstr_t((_bstr_t *)&v34);
  v26 = (unsigned __int16 *)CoTaskMemAlloc(2LL * *v25);
  v27 = (void **)v36;
  *v36 = v26;
  if ( !v26 )
  {
    XML = -2147024882;
    goto LABEL_60;
  }
  v28 = *(_QWORD **)MSXML2::IXMLDOMNode::Getxml(v7, &v34);
  if ( v28 )
    v28 = (_QWORD *)*v28;
  memcpy_0(*v27, v28, 2LL * *v25);
  _bstr_t::~_bstr_t((_bstr_t *)&v34);
LABEL_57:
  if ( XML < 0 )
  {
LABEL_60:
    if ( *v11 )
    {
      ((void (__fastcall *)(struct IUnknown *))(*v11)->lpVtbl->Release)(*v11);
      *v11 = 0;
    }
  }
  LeaveCriticalSection(lpCriticalSection);
  if ( v7 )
    ((void (__fastcall *)(struct IUnknown *))v7->lpVtbl->Release)(v7);
  if ( v6 )
    ((void (__fastcall *)(struct IUnknown *))v6->lpVtbl->Release)(v6);
  return (unsigned int)XML;
}

```

## disassembly

```asm
0x1800086c8  mov     [rsp-38h+arg_8], rbx
0x1800086cd  mov     [rsp-38h+arg_18], r9
0x1800086d2  mov     [rsp-38h+arg_10], r8
0x1800086d7  push    rbp
0x1800086d8  push    rsi
0x1800086d9  push    rdi
0x1800086da  push    r12
0x1800086dc  push    r13
0x1800086de  push    r14
0x1800086e0  push    r15
0x1800086e2  mov     rbp, rsp
0x1800086e5  sub     rsp, 60h
0x1800086e9  mov     r13, rdx
0x1800086ec  mov     rbx, rcx
0x1800086ef  xor     r14d, r14d
0x1800086f2  mov     [rbp+var_28], r14
0x1800086f6  xor     edi, edi
0x1800086f8  mov     [rbp+var_18], rdi
0x1800086fc  cmp     [rcx+30h], dil
0x180008700  jnz     short loc_180008759
0x180008702  lea     rax, WPP_GLOBAL_Control
0x180008709  mov     rcx, cs:WPP_GLOBAL_Control
0x180008710  cmp     rcx, rax
0x180008713  jz      short loc_18000874F
0x180008715  cmp     byte ptr [rcx+19h], 2
0x180008719  jb      short loc_18000874F
0x18000871b  test    byte ptr [rcx+1Ch], 10h
0x18000871f  jz      short loc_18000874F
0x180008721  lea     rcx, aDatastoreserve_6; "DataStoreServer() is not initialized"
0x180008728  call    WppDbgPrint
0x18000872d  lea     edx, [rdi+29h]
0x180008730  lea     r9, aNpsds; "NPSDS"
0x180008737  lea     r8, WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids
0x18000873e  mov     rcx, cs:WPP_GLOBAL_Control
0x180008745  mov     rcx, [rcx+10h]
0x180008749  call    WPP_SF_s
0x18000874e  nop
0x18000874f  mov     eax, 80004005h
0x180008754  jmp     loc_180008B0C
0x180008759  test    r13, r13
0x18000875c  jnz     short loc_1800087B6
0x18000875e  lea     rax, WPP_GLOBAL_Control
0x180008765  mov     rcx, cs:WPP_GLOBAL_Control
0x18000876c  cmp     rcx, rax
0x18000876f  jz      short loc_1800087AC
0x180008771  cmp     byte ptr [rcx+19h], 2
0x180008775  jb      short loc_1800087AC
0x180008777  test    byte ptr [rcx+1Ch], 10h
0x18000877b  jz      short loc_1800087AC
0x18000877d  lea     rcx, aInvalidParamet_0; "Invalid parameter for DataStoreServer::"...
0x180008784  call    WppDbgPrint
0x180008789  lea     edx, [r13+2Ah]
0x18000878d  lea     r9, aNpsds; "NPSDS"
0x180008794  lea     r8, WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids
0x18000879b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800087a2  mov     rcx, [rcx+10h]
0x1800087a6  call    WPP_SF_s
0x1800087ab  nop
0x1800087ac  mov     eax, 80070057h
0x1800087b1  jmp     loc_180008B0C
0x1800087b6  lea     r15, [rcx+8]
0x1800087ba  mov     [rbp+lpCriticalSection], r15
0x1800087be  xor     esi, esi
0x1800087c0  jmp     short loc_1800087CF
0x1800087c2  inc     esi
0x1800087c4  cmp     esi, 64h ; 'd'
0x1800087c7  jge     short loc_1800087DE
0x1800087c9  call    cs:__imp_SwitchToThread
0x1800087cf  mov     rcx, r15; lpCriticalSection
0x1800087d2  call    cs:__imp_TryEnterCriticalSection
0x1800087d8  test    eax, eax
0x1800087da  jz      short loc_1800087C2
0x1800087dc  jmp     short loc_1800087E7
0x1800087de  mov     rcx, r15; lpCriticalSection
0x1800087e1  call    cs:__imp_EnterCriticalSection
0x1800087e7  lea     r12, [rbx+23Ch]
0x1800087ee  lea     r15, [rbx+868h]
0x1800087f5  mov     rcx, r12
0x1800087f8  call    IASFileExists
0x1800087fd  test    al, al
0x1800087ff  jnz     short loc_180008879
0x180008801  mov     r8, r15
0x180008804  mov     rdx, [rbx+898h]
0x18000880b  call    ?LoadXML@DataStoreServer@@AEAAJPEBGAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z; DataStoreServer::LoadXML(ushort const *,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &)
0x180008810  mov     esi, eax
0x180008812  test    eax, eax
0x180008814  jns     loc_1800088F5
0x18000881a  lea     rax, WPP_GLOBAL_Control
0x180008821  mov     rcx, cs:WPP_GLOBAL_Control
0x180008828  cmp     rcx, rax
0x18000882b  jz      loc_180008ABA
0x180008831  cmp     byte ptr [rcx+19h], 2
0x180008835  jb      loc_180008ABA
0x18000883b  test    byte ptr [rcx+1Ch], 10h
0x18000883f  jz      loc_180008ABA
0x180008845  lea     rcx, aDatastoreserve_25; "DataStoreServer::GetTemplates() failed "...
0x18000884c  call    WppDbgPrint
0x180008851  mov     edx, 2Bh ; '+'
0x180008856  lea     r9, aNpsds; "NPSDS"
0x18000885d  lea     r8, WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids
0x180008864  mov     rcx, cs:WPP_GLOBAL_Control
0x18000886b  mov     rcx, [rcx+10h]
0x18000886f  call    WPP_SF_s
0x180008874  jmp     loc_180008ABA
0x180008879  xor     esi, esi
0x18000887b  cmp     [r15], rsi
0x18000887e  jnz     short loc_1800088F5
0x180008880  mov     r8, r15
0x180008883  mov     rdx, r12
0x180008886  call    ?Load@DataStoreServer@@AEAAJPEBGAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z; DataStoreServer::Load(ushort const *,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &)
0x18000888b  mov     esi, eax
0x18000888d  test    eax, eax
0x18000888f  js      short loc_180008897
0x180008891  cmp     qword ptr [r15], 0
0x180008895  jnz     short loc_1800088F5
0x180008897  lea     rax, WPP_GLOBAL_Control
0x18000889e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800088a5  cmp     rcx, rax
0x1800088a8  jz      loc_180008AAF
0x1800088ae  cmp     byte ptr [rcx+19h], 2
0x1800088b2  jb      loc_180008AAF
0x1800088b8  test    byte ptr [rcx+1Ch], 10h
0x1800088bc  jz      loc_180008AAF
0x1800088c2  mov     edx, esi
0x1800088c4  lea     rcx, aLoadFailedHres_1; "Load failed:%!hresult! in GetTemplates"
0x1800088cb  call    WppDbgPrint
0x1800088d0  mov     edx, 2Ch ; ','
0x1800088d5  mov     [rsp+60h+var_40], esi
0x1800088d9  lea     r8, WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids
0x1800088e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800088e7  mov     rcx, [rcx+10h]
0x1800088eb  call    WPP_SF_sd
0x1800088f0  jmp     loc_180008AAF
0x1800088f5  mov     rbx, [r15]
0x1800088f8  test    rbx, rbx
0x1800088fb  jz      loc_180008B2F
0x180008901  mov     [rbp+arg_0], 0
0x180008909  mov     rax, [rbx]
0x18000890c  lea     rdx, [rbp+arg_0]
0x180008910  mov     rcx, rbx
0x180008913  mov     rax, [rax+168h]
0x18000891a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000891f  test    eax, eax
0x180008921  js      loc_180008B3A
0x180008927  mov     rbx, [rbp+arg_0]
0x18000892b  mov     [rbp+arg_0], rbx
0x18000892f  test    rbx, rbx
0x180008932  jz      loc_180008B4C
0x180008938  mov     rdx, r13; unsigned __int16 *
0x18000893b  lea     rcx, [rbp+var_30]; this
0x18000893f  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180008944  mov     r8, rax
0x180008947  lea     rdx, [rbp+var_20]
0x18000894b  mov     rcx, rbx; struct IUnknown *
0x18000894e  call    ?selectNodes@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNodeList@MSXML2@@$1?_GUID_2933bf82_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectNodes(_bstr_t)
0x180008953  mov     rcx, [rax]
0x180008956  test    rcx, rcx
0x180008959  jz      short loc_18000896F
0x18000895b  mov     r14, rcx
0x18000895e  mov     [rbp+var_28], rcx
0x180008962  mov     rax, [rcx]
0x180008965  mov     rax, [rax+8]
0x180008969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000896e  nop
0x18000896f  mov     rcx, [rbp+var_20]
0x180008973  test    rcx, rcx
0x180008976  jz      short loc_180008985
0x180008978  mov     rax, [rcx]
0x18000897b  mov     rax, [rax+10h]
0x18000897f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008984  nop
0x180008985  mov     rax, [rbx]
0x180008988  mov     rcx, rbx
0x18000898b  mov     rax, [rax+10h]
0x18000898f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008994  nop
0x180008995  test    r14, r14
0x180008998  jz      loc_180008AB5
0x18000899e  mov     dword ptr [rbp+arg_0], 0
0x1800089a5  mov     rax, [r14]
0x1800089a8  lea     rdx, [rbp+arg_0]
0x1800089ac  mov     rcx, r14
0x1800089af  mov     rax, [rax+40h]
0x1800089b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089b8  test    eax, eax
0x1800089ba  js      loc_180008B57
0x1800089c0  cmp     dword ptr [rbp+arg_0], 1
0x1800089c4  jnz     loc_180008AB5
0x1800089ca  mov     [rbp+arg_0], 0
0x1800089d2  mov     rax, [r14]
0x1800089d5  lea     rdx, [rbp+arg_0]
0x1800089d9  mov     rcx, r14
0x1800089dc  mov     rax, [rax+48h]
0x1800089e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089e5  test    eax, eax
0x1800089e7  js      loc_180008B69
0x1800089ed  mov     rbx, [rbp+arg_0]
0x1800089f1  test    rbx, rbx
0x1800089f4  jz      short loc_180008A0D
0x1800089f6  mov     rdi, rbx
0x1800089f9  mov     [rbp+var_18], rbx
0x1800089fd  mov     rax, [rbx]
0x180008a00  mov     rcx, rbx
0x180008a03  mov     rax, [rax+8]
0x180008a07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a0c  nop
0x180008a0d  test    rbx, rbx
0x180008a10  jz      short loc_180008A22
0x180008a12  mov     rax, [rbx]
0x180008a15  mov     rcx, rbx
0x180008a18  mov     rax, [rax+10h]
0x180008a1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a21  nop
0x180008a22  test    rdi, rdi
0x180008a25  jz      loc_180008B24
0x180008a2b  lea     rdx, [rbp+arg_0]
0x180008a2f  mov     rcx, rdi
0x180008a32  call    ?Getxml@IXMLDOMNode@MSXML2@@QEAA?AV_bstr_t@@XZ; MSXML2::IXMLDOMNode::Getxml(void)
0x180008a37  mov     rcx, [rax]
0x180008a3a  test    rcx, rcx
0x180008a3d  jz      short loc_180008A4F
0x180008a3f  mov     rcx, [rcx]; pbstr
0x180008a42  test    rcx, rcx
0x180008a45  jz      short loc_180008A4F
0x180008a47  call    cs:__imp_SysStringLen
0x180008a4d  jmp     short loc_180008A51
0x180008a4f  xor     eax, eax
0x180008a51  mov     rbx, [rbp+arg_10]
0x180008a55  mov     [rbx], eax
0x180008a57  lea     rcx, [rbp+arg_0]; this
0x180008a5b  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180008a60  movsxd  rcx, dword ptr [rbx]
0x180008a63  add     rcx, rcx; cb
0x180008a66  call    cs:__imp_CoTaskMemAlloc
0x180008a6c  mov     r12, [rbp+arg_18]
0x180008a70  mov     [r12], rax
0x180008a74  test    rax, rax
0x180008a77  jnz     short loc_180008A80
0x180008a79  mov     esi, 8007000Eh
0x180008a7e  jmp     short loc_180008ABA
0x180008a80  lea     rdx, [rbp+arg_0]
0x180008a84  mov     rcx, rdi
0x180008a87  call    ?Getxml@IXMLDOMNode@MSXML2@@QEAA?AV_bstr_t@@XZ; MSXML2::IXMLDOMNode::Getxml(void)
0x180008a8c  mov     rdx, [rax]
0x180008a8f  test    rdx, rdx
0x180008a92  jz      short loc_180008A97
0x180008a94  mov     rdx, [rdx]; Src
0x180008a97  movsxd  r8, dword ptr [rbx]
0x180008a9a  add     r8, r8; Size
0x180008a9d  mov     rcx, [r12]; void *
0x180008aa1  call    memcpy_0
0x180008aa6  lea     rcx, [rbp+arg_0]; this
0x180008aaa  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180008aaf  test    esi, esi
0x180008ab1  jns     short loc_180008AD5
0x180008ab3  jmp     short loc_180008ABA
0x180008ab5  mov     esi, 80070057h
0x180008aba  mov     rcx, [r15]
0x180008abd  test    rcx, rcx
0x180008ac0  jz      short loc_180008AD5
0x180008ac2  mov     rax, [rcx]
0x180008ac5  mov     rax, [rax+10h]
0x180008ac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ace  mov     qword ptr [r15], 0
0x180008ad5  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x180008ad9  call    cs:__imp_LeaveCriticalSection
0x180008adf  nop
0x180008ae0  test    rdi, rdi
0x180008ae3  jz      short loc_180008AF5
0x180008ae5  mov     rax, [rdi]
0x180008ae8  mov     rcx, rdi
0x180008aeb  mov     rax, [rax+10h]
0x180008aef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008af4  nop
0x180008af5  test    r14, r14
0x180008af8  jz      short loc_180008B0A
0x180008afa  mov     rax, [r14]
0x180008afd  mov     rcx, r14
0x180008b00  mov     rax, [rax+10h]
0x180008b04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b09  nop
0x180008b0a  mov     eax, esi
0x180008b0c  mov     rbx, [rsp+60h+arg_8]
0x180008b14  add     rsp, 60h
0x180008b18  pop     r15
0x180008b1a  pop     r14
0x180008b1c  pop     r13
0x180008b1e  pop     r12
0x180008b20  pop     rdi
0x180008b21  pop     rsi
0x180008b22  pop     rbp
0x180008b23  retn
0x180008b24  mov     ecx, 80004003h; int
0x180008b29  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180008b2f  mov     ecx, 80004003h; int
0x180008b34  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180008b3a  lea     r8, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; struct _GUID *
0x180008b41  mov     rdx, rbx; struct IUnknown *
0x180008b44  mov     ecx, eax; int
0x180008b46  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
  ... truncated ...
```
