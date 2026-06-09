# DataStoreServer::GetConfiguration(ushort const *,int &,ushort * &)

- ea: `0x1800081b8`
- end: `0x180008685`
- name: `?GetConfiguration@DataStoreServer@@QEAAJPEBGAEAHAEAPEAG@Z`
- size: `1229`
- prototype: `int(DataStoreServer *__hidden this, const unsigned __int16 *, int *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180006cd0`

## callees

- `0x1800020b1`
- `0x180007150`
- `0x1800071ac`
- `0x180007628`
- `0x1800076dc`
- `0x1800081b8`
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

- `KERNEL32!TryEnterCriticalSection` at `0x1800082c2`
- `KERNEL32!TryEnterCriticalSection` at `0x1800082c2`
- `KERNEL32!SwitchToThread` at `0x1800082b9`
- `KERNEL32!SwitchToThread` at `0x1800082b9`
- `KERNEL32!EnterCriticalSection` at `0x1800082d1`
- `KERNEL32!EnterCriticalSection` at `0x1800082d1`
- `KERNEL32!LeaveCriticalSection` at `0x1800085e3`
- `KERNEL32!LeaveCriticalSection` at `0x1800085e3`
- `ole32!CoTaskMemAlloc` at `0x180008570`
- `ole32!CoTaskMemAlloc` at `0x180008570`
- `OLEAUT32!__imp_SysStringLen` at `0x180008551`
- `OLEAUT32!__imp_SysStringLen` at `0x180008551`

## string_xrefs

- `0x18000826d`: `Invalid parameter for DataStoreServer::GetConfiguration`
- `0x18000834e`: `DataStoreServer::GetConfiguration() failed to load xml text to IAS Dom `
- `0x1800083ce`: `Load failed:%!hresult! in GetConfiguration`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall DataStoreServer::GetConfiguration(
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
  char v12; // al
  __int64 v13; // rcx
  int XML; // esi
  struct IUnknown *v15; // rbx
  int v16; // eax
  struct IUnknown *v17; // rbx
  struct IUnknown **v18; // rax
  struct IUnknown *v19; // rcx
  int v20; // eax
  int v21; // eax
  struct IUnknown *v22; // rbx
  OLECHAR ***v23; // rax
  OLECHAR *v24; // rcx
  UINT v25; // eax
  int *v26; // rbx
  unsigned __int16 *v27; // rax
  void **v28; // r12
  _QWORD *v29; // rdx
  _BYTE v30[8]; // [rsp+30h] [rbp-30h] BYREF
  struct IUnknown *v31; // [rsp+38h] [rbp-28h]
  __int64 v32; // [rsp+40h] [rbp-20h]
  struct IUnknown *v33; // [rsp+48h] [rbp-18h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+50h] [rbp-10h]
  struct IUnknown *v35; // [rsp+A0h] [rbp+40h] BYREF
  int *v36; // [rsp+B0h] [rbp+50h]
  unsigned __int16 **v37; // [rsp+B8h] [rbp+58h]

  v37 = a4;
  v36 = a3;
  v6 = 0;
  v31 = 0;
  v7 = 0;
  v33 = 0;
  if ( !*((_BYTE *)this + 48) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WppDbgPrint("DataStoreServer() is not initialized");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids, "NPSDS");
    }
    return 2147500037LL;
  }
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WppDbgPrint("Invalid parameter for DataStoreServer::GetConfiguration");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids, "NPSDS");
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
  v11 = (struct IUnknown **)((char *)this + 2144);
  v12 = IASFileExists((const WCHAR *)this + 25);
  v13 = *((_QWORD *)this + 268);
  if ( v12 )
  {
    XML = 0;
    if ( !v13 )
    {
      XML = DataStoreServer::Load(0, (const OLECHAR *)this + 25, (LPVOID *)this + 268);
      if ( XML < 0 || !*v11 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          WppDbgPrint("Load failed:%!hresult! in GetConfiguration");
          WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids);
        }
        goto LABEL_59;
      }
    }
  }
  else
  {
    if ( v13 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      *v11 = 0;
    }
    XML = DataStoreServer::LoadXML(v13, *((const unsigned __int16 **)this + 274), (LPVOID *)this + 268);
    if ( XML < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WppDbgPrint("DataStoreServer::GetConfiguration() failed to load xml text to IAS Dom ");
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids, "NPSDS");
      }
      goto LABEL_62;
    }
  }
  v15 = *v11;
  if ( !*v11 )
    _com_issue_error(-2147467261);
  v35 = 0;
  v16 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v15->lpVtbl[15].QueryInterface)(v15, &v35);
  if ( v16 < 0 )
    _com_issue_errorex(v16, v15, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60);
  v17 = v35;
  if ( !v35 )
    _com_issue_error(-2147467261);
  _bstr_t::_bstr_t((_bstr_t *)v30, a2);
  v18 = (struct IUnknown **)MSXML2::IXMLDOMNode::selectNodes(v17);
  v19 = *v18;
  if ( *v18 )
  {
    v6 = *v18;
    v31 = *v18;
    ((void (__fastcall *)(struct IUnknown *))v19->lpVtbl->AddRef)(v19);
  }
  if ( v32 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  ((void (__fastcall *)(struct IUnknown *))v17->lpVtbl->Release)(v17);
  if ( !v6 )
    goto LABEL_61;
  LODWORD(v35) = 0;
  v20 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v6->lpVtbl[2].Release)(v6, &v35);
  if ( v20 < 0 )
    _com_issue_errorex(v20, v6, &GUID_2933bf82_7b36_11d2_b20e_00c04f983e60);
  if ( (_DWORD)v35 != 1 )
  {
LABEL_61:
    XML = -2147024809;
    goto LABEL_62;
  }
  v35 = 0;
  v21 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v6->lpVtbl[3].QueryInterface)(v6, &v35);
  if ( v21 < 0 )
    _com_issue_errorex(v21, v6, &GUID_2933bf82_7b36_11d2_b20e_00c04f983e60);
  v22 = v35;
  if ( v35 )
  {
    v7 = v35;
    v33 = v35;
    ((void (__fastcall *)(struct IUnknown *))v35->lpVtbl->AddRef)(v35);
  }
  if ( v22 )
    ((void (__fastcall *)(struct IUnknown *))v22->lpVtbl->Release)(v22);
  if ( !v7 )
    _com_issue_error(-2147467261);
  v23 = (OLECHAR ***)MSXML2::IXMLDOMNode::Getxml(v7, &v35);
  if ( *v23 && (v24 = **v23) != 0 )
    v25 = SysStringLen(v24);
  else
    v25 = 0;
  v26 = v36;
  *v36 = v25;
  _bstr_t::~_bstr_t((_bstr_t *)&v35);
  v27 = (unsigned __int16 *)CoTaskMemAlloc(2LL * *v26);
  v28 = (void **)v37;
  *v37 = v27;
  if ( !v27 )
  {
    XML = -2147024882;
    goto LABEL_62;
  }
  v29 = *(_QWORD **)MSXML2::IXMLDOMNode::Getxml(v7, &v35);
  if ( v29 )
    v29 = (_QWORD *)*v29;
  memcpy_0(*v28, v29, 2LL * *v26);
  _bstr_t::~_bstr_t((_bstr_t *)&v35);
LABEL_59:
  if ( XML < 0 )
  {
LABEL_62:
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
0x1800081b8  mov     [rsp-38h+arg_8], rbx
0x1800081bd  mov     [rsp-38h+arg_18], r9
0x1800081c2  mov     [rsp-38h+arg_10], r8
0x1800081c7  push    rbp
0x1800081c8  push    rsi
0x1800081c9  push    rdi
0x1800081ca  push    r12
0x1800081cc  push    r13
0x1800081ce  push    r14
0x1800081d0  push    r15
0x1800081d2  mov     rbp, rsp
0x1800081d5  sub     rsp, 60h
0x1800081d9  mov     r13, rdx
0x1800081dc  mov     rbx, rcx
0x1800081df  xor     r14d, r14d
0x1800081e2  mov     [rbp+var_28], r14
0x1800081e6  xor     edi, edi
0x1800081e8  mov     [rbp+var_18], rdi
0x1800081ec  cmp     [rcx+30h], dil
0x1800081f0  jnz     short loc_180008249
0x1800081f2  lea     rax, WPP_GLOBAL_Control
0x1800081f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180008200  cmp     rcx, rax
0x180008203  jz      short loc_18000823F
0x180008205  cmp     byte ptr [rcx+19h], 2
0x180008209  jb      short loc_18000823F
0x18000820b  test    byte ptr [rcx+1Ch], 10h
0x18000820f  jz      short loc_18000823F
0x180008211  lea     rcx, aDatastoreserve_6; "DataStoreServer() is not initialized"
0x180008218  call    WppDbgPrint
0x18000821d  lea     edx, [rdi+1Bh]
0x180008220  lea     r9, aNpsds; "NPSDS"
0x180008227  lea     r8, WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids
0x18000822e  mov     rcx, cs:WPP_GLOBAL_Control
0x180008235  mov     rcx, [rcx+10h]
0x180008239  call    WPP_SF_s
0x18000823e  nop
0x18000823f  mov     eax, 80004005h
0x180008244  jmp     loc_180008616
0x180008249  test    r13, r13
0x18000824c  jnz     short loc_1800082A6
0x18000824e  lea     rax, WPP_GLOBAL_Control
0x180008255  mov     rcx, cs:WPP_GLOBAL_Control
0x18000825c  cmp     rcx, rax
0x18000825f  jz      short loc_18000829C
0x180008261  cmp     byte ptr [rcx+19h], 2
0x180008265  jb      short loc_18000829C
0x180008267  test    byte ptr [rcx+1Ch], 10h
0x18000826b  jz      short loc_18000829C
0x18000826d  lea     rcx, aInvalidParamet_1; "Invalid parameter for DataStoreServer::"...
0x180008274  call    WppDbgPrint
0x180008279  lea     edx, [r13+1Ch]
0x18000827d  lea     r9, aNpsds; "NPSDS"
0x180008284  lea     r8, WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids
0x18000828b  mov     rcx, cs:WPP_GLOBAL_Control
0x180008292  mov     rcx, [rcx+10h]
0x180008296  call    WPP_SF_s
0x18000829b  nop
0x18000829c  mov     eax, 80070057h
0x1800082a1  jmp     loc_180008616
0x1800082a6  lea     r15, [rcx+8]
0x1800082aa  mov     [rbp+lpCriticalSection], r15
0x1800082ae  xor     esi, esi
0x1800082b0  jmp     short loc_1800082BF
0x1800082b2  inc     esi
0x1800082b4  cmp     esi, 64h ; 'd'
0x1800082b7  jge     short loc_1800082CE
0x1800082b9  call    cs:__imp_SwitchToThread
0x1800082bf  mov     rcx, r15; lpCriticalSection
0x1800082c2  call    cs:__imp_TryEnterCriticalSection
0x1800082c8  test    eax, eax
0x1800082ca  jz      short loc_1800082B2
0x1800082cc  jmp     short loc_1800082D7
0x1800082ce  mov     rcx, r15; lpCriticalSection
0x1800082d1  call    cs:__imp_EnterCriticalSection
0x1800082d7  lea     r15, [rbx+860h]
0x1800082de  lea     rcx, [rbx+32h]
0x1800082e2  call    IASFileExists
0x1800082e7  mov     rcx, [r15]
0x1800082ea  test    al, al
0x1800082ec  jnz     loc_180008382
0x1800082f2  test    rcx, rcx
0x1800082f5  jz      short loc_18000830A
0x1800082f7  mov     rax, [rcx]
0x1800082fa  mov     rax, [rax+10h]
0x1800082fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008303  mov     qword ptr [r15], 0
0x18000830a  mov     r8, r15
0x18000830d  mov     rdx, [rbx+890h]
0x180008314  call    ?LoadXML@DataStoreServer@@AEAAJPEBGAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z; DataStoreServer::LoadXML(ushort const *,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &)
0x180008319  mov     esi, eax
0x18000831b  test    eax, eax
0x18000831d  jns     loc_1800083FF
0x180008323  lea     rax, WPP_GLOBAL_Control
0x18000832a  mov     rcx, cs:WPP_GLOBAL_Control
0x180008331  cmp     rcx, rax
0x180008334  jz      loc_1800085C4
0x18000833a  cmp     byte ptr [rcx+19h], 2
0x18000833e  jb      loc_1800085C4
0x180008344  test    byte ptr [rcx+1Ch], 10h
0x180008348  jz      loc_1800085C4
0x18000834e  lea     rcx, aDatastoreserve_0; "DataStoreServer::GetConfiguration() fai"...
0x180008355  call    WppDbgPrint
0x18000835a  mov     edx, 1Dh
0x18000835f  lea     r9, aNpsds; "NPSDS"
0x180008366  lea     r8, WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids
0x18000836d  mov     rcx, cs:WPP_GLOBAL_Control
0x180008374  mov     rcx, [rcx+10h]
0x180008378  call    WPP_SF_s
0x18000837d  jmp     loc_1800085C4
0x180008382  xor     esi, esi
0x180008384  test    rcx, rcx
0x180008387  jnz     short loc_1800083FF
0x180008389  mov     r8, r15
0x18000838c  lea     rdx, [rbx+32h]
0x180008390  call    ?Load@DataStoreServer@@AEAAJPEBGAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z; DataStoreServer::Load(ushort const *,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &)
0x180008395  mov     esi, eax
0x180008397  test    eax, eax
0x180008399  js      short loc_1800083A1
0x18000839b  cmp     qword ptr [r15], 0
0x18000839f  jnz     short loc_1800083FF
0x1800083a1  lea     rax, WPP_GLOBAL_Control
0x1800083a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800083af  cmp     rcx, rax
0x1800083b2  jz      loc_1800085B9
0x1800083b8  cmp     byte ptr [rcx+19h], 2
0x1800083bc  jb      loc_1800085B9
0x1800083c2  test    byte ptr [rcx+1Ch], 10h
0x1800083c6  jz      loc_1800085B9
0x1800083cc  mov     edx, esi
0x1800083ce  lea     rcx, aLoadFailedHres_0; "Load failed:%!hresult! in GetConfigurat"...
0x1800083d5  call    WppDbgPrint
0x1800083da  mov     edx, 1Eh
0x1800083df  mov     [rsp+60h+var_40], esi
0x1800083e3  lea     r8, WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids
0x1800083ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800083f1  mov     rcx, [rcx+10h]
0x1800083f5  call    WPP_SF_sd
0x1800083fa  jmp     loc_1800085B9
0x1800083ff  mov     rbx, [r15]
0x180008402  test    rbx, rbx
0x180008405  jz      loc_180008639
0x18000840b  mov     [rbp+arg_0], 0
0x180008413  mov     rax, [rbx]
0x180008416  lea     rdx, [rbp+arg_0]
0x18000841a  mov     rcx, rbx
0x18000841d  mov     rax, [rax+168h]
0x180008424  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008429  test    eax, eax
0x18000842b  js      loc_180008644
0x180008431  mov     rbx, [rbp+arg_0]
0x180008435  mov     [rbp+arg_0], rbx
0x180008439  test    rbx, rbx
0x18000843c  jz      loc_180008656
0x180008442  mov     rdx, r13; unsigned __int16 *
0x180008445  lea     rcx, [rbp+var_30]; this
0x180008449  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000844e  mov     r8, rax
0x180008451  lea     rdx, [rbp+var_20]
0x180008455  mov     rcx, rbx; struct IUnknown *
0x180008458  call    ?selectNodes@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNodeList@MSXML2@@$1?_GUID_2933bf82_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectNodes(_bstr_t)
0x18000845d  mov     rcx, [rax]
0x180008460  test    rcx, rcx
0x180008463  jz      short loc_180008479
0x180008465  mov     r14, rcx
0x180008468  mov     [rbp+var_28], rcx
0x18000846c  mov     rax, [rcx]
0x18000846f  mov     rax, [rax+8]
0x180008473  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008478  nop
0x180008479  mov     rcx, [rbp+var_20]
0x18000847d  test    rcx, rcx
0x180008480  jz      short loc_18000848F
0x180008482  mov     rax, [rcx]
0x180008485  mov     rax, [rax+10h]
0x180008489  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000848e  nop
0x18000848f  mov     rax, [rbx]
0x180008492  mov     rcx, rbx
0x180008495  mov     rax, [rax+10h]
0x180008499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000849e  nop
0x18000849f  test    r14, r14
0x1800084a2  jz      loc_1800085BF
0x1800084a8  mov     dword ptr [rbp+arg_0], 0
0x1800084af  mov     rax, [r14]
0x1800084b2  lea     rdx, [rbp+arg_0]
0x1800084b6  mov     rcx, r14
0x1800084b9  mov     rax, [rax+40h]
0x1800084bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084c2  test    eax, eax
0x1800084c4  js      loc_180008661
0x1800084ca  cmp     dword ptr [rbp+arg_0], 1
0x1800084ce  jnz     loc_1800085BF
0x1800084d4  mov     [rbp+arg_0], 0
0x1800084dc  mov     rax, [r14]
0x1800084df  lea     rdx, [rbp+arg_0]
0x1800084e3  mov     rcx, r14
0x1800084e6  mov     rax, [rax+48h]
0x1800084ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084ef  test    eax, eax
0x1800084f1  js      loc_180008673
0x1800084f7  mov     rbx, [rbp+arg_0]
0x1800084fb  test    rbx, rbx
0x1800084fe  jz      short loc_180008517
0x180008500  mov     rdi, rbx
0x180008503  mov     [rbp+var_18], rbx
0x180008507  mov     rax, [rbx]
0x18000850a  mov     rcx, rbx
0x18000850d  mov     rax, [rax+8]
0x180008511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008516  nop
0x180008517  test    rbx, rbx
0x18000851a  jz      short loc_18000852C
0x18000851c  mov     rax, [rbx]
0x18000851f  mov     rcx, rbx
0x180008522  mov     rax, [rax+10h]
0x180008526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000852b  nop
0x18000852c  test    rdi, rdi
0x18000852f  jz      loc_18000862E
0x180008535  lea     rdx, [rbp+arg_0]
0x180008539  mov     rcx, rdi
0x18000853c  call    ?Getxml@IXMLDOMNode@MSXML2@@QEAA?AV_bstr_t@@XZ; MSXML2::IXMLDOMNode::Getxml(void)
0x180008541  mov     rcx, [rax]
0x180008544  test    rcx, rcx
0x180008547  jz      short loc_180008559
0x180008549  mov     rcx, [rcx]; pbstr
0x18000854c  test    rcx, rcx
0x18000854f  jz      short loc_180008559
0x180008551  call    cs:__imp_SysStringLen
0x180008557  jmp     short loc_18000855B
0x180008559  xor     eax, eax
0x18000855b  mov     rbx, [rbp+arg_10]
0x18000855f  mov     [rbx], eax
0x180008561  lea     rcx, [rbp+arg_0]; this
0x180008565  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18000856a  movsxd  rcx, dword ptr [rbx]
0x18000856d  add     rcx, rcx; cb
0x180008570  call    cs:__imp_CoTaskMemAlloc
0x180008576  mov     r12, [rbp+arg_18]
0x18000857a  mov     [r12], rax
0x18000857e  test    rax, rax
0x180008581  jnz     short loc_18000858A
0x180008583  mov     esi, 8007000Eh
0x180008588  jmp     short loc_1800085C4
0x18000858a  lea     rdx, [rbp+arg_0]
0x18000858e  mov     rcx, rdi
0x180008591  call    ?Getxml@IXMLDOMNode@MSXML2@@QEAA?AV_bstr_t@@XZ; MSXML2::IXMLDOMNode::Getxml(void)
0x180008596  mov     rdx, [rax]
0x180008599  test    rdx, rdx
0x18000859c  jz      short loc_1800085A1
0x18000859e  mov     rdx, [rdx]; Src
0x1800085a1  movsxd  r8, dword ptr [rbx]
0x1800085a4  add     r8, r8; Size
0x1800085a7  mov     rcx, [r12]; void *
0x1800085ab  call    memcpy_0
0x1800085b0  lea     rcx, [rbp+arg_0]; this
0x1800085b4  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800085b9  test    esi, esi
0x1800085bb  jns     short loc_1800085DF
0x1800085bd  jmp     short loc_1800085C4
0x1800085bf  mov     esi, 80070057h
0x1800085c4  mov     rcx, [r15]
0x1800085c7  test    rcx, rcx
0x1800085ca  jz      short loc_1800085DF
0x1800085cc  mov     rax, [rcx]
0x1800085cf  mov     rax, [rax+10h]
0x1800085d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085d8  mov     qword ptr [r15], 0
0x1800085df  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x1800085e3  call    cs:__imp_LeaveCriticalSection
0x1800085e9  nop
0x1800085ea  test    rdi, rdi
0x1800085ed  jz      short loc_1800085FF
0x1800085ef  mov     rax, [rdi]
0x1800085f2  mov     rcx, rdi
0x1800085f5  mov     rax, [rax+10h]
0x1800085f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085fe  nop
0x1800085ff  test    r14, r14
0x180008602  jz      short loc_180008614
0x180008604  mov     rax, [r14]
0x180008607  mov     rcx, r14
0x18000860a  mov     rax, [rax+10h]
0x18000860e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008613  nop
0x180008614  mov     eax, esi
0x180008616  mov     rbx, [rsp+60h+arg_8]
0x18000861e  add     rsp, 60h
0x180008622  pop     r15
0x180008624  pop     r14
0x180008626  pop     r13
0x180008628  pop     r12
0x18000862a  pop     rdi
0x18000862b  pop     rsi
0x18000862c  pop     rbp
0x18000862d  retn
0x18000862e  mov     ecx, 80004003h; int
0x180008633  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
  ... truncated ...
```
