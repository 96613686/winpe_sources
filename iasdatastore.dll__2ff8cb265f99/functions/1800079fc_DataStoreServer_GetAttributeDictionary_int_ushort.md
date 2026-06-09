# DataStoreServer::GetAttributeDictionary(int &,ushort * &)

- ea: `0x1800079fc`
- end: `0x180007fab`
- name: `?GetAttributeDictionary@DataStoreServer@@QEAAJAEAHAEAPEAG@Z`
- size: `1455`
- prototype: `__int64 __fastcall(DataStoreServer *__hidden this, int *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180006b50`

## callees

- `0x1800020b1`
- `0x180007150`
- `0x1800071ac`
- `0x180007628`
- `0x1800076dc`
- `0x1800079fc`
- `0x180008ce4`
- `0x1800093cc`
- `0x180009af8`
- `0x18000c000`
- `0x18000d8f0`
- `0x18000d990`
- `0x18000db68`
- `0x18000db7c`
- `0x180010010`

## import_xrefs

- `msvcrt!_wtoi` at `0x180007ccb`
- `msvcrt!_wtoi` at `0x180007ccb`
- `KERNEL32!TryEnterCriticalSection` at `0x180007aaf`
- `KERNEL32!TryEnterCriticalSection` at `0x180007aaf`
- `KERNEL32!SwitchToThread` at `0x180007aa6`
- `KERNEL32!SwitchToThread` at `0x180007aa6`
- `KERNEL32!EnterCriticalSection` at `0x180007abe`
- `KERNEL32!EnterCriticalSection` at `0x180007abe`
- `KERNEL32!LeaveCriticalSection` at `0x180007f1d`
- `KERNEL32!LeaveCriticalSection` at `0x180007f1d`
- `ole32!CoTaskMemAlloc` at `0x180007eab`
- `ole32!CoTaskMemAlloc` at `0x180007eab`
- `OLEAUT32!__imp_SysAllocString` at `0x180007da7`
- `OLEAUT32!__imp_SysAllocString` at `0x180007da7`
- `OLEAUT32!__imp_SysFreeString` at `0x180007a86`
- `OLEAUT32!__imp_SysFreeString` at `0x180007f28`
- `OLEAUT32!__imp_SysFreeString` at `0x180007a86`
- `OLEAUT32!__imp_SysFreeString` at `0x180007f28`
- `OLEAUT32!__imp_SysStringLen` at `0x180007e35`
- `OLEAUT32!__imp_SysStringLen` at `0x180007e35`
- `OLEAUT32!__imp_VariantClear` at `0x180007dfe`
- `OLEAUT32!__imp_VariantClear` at `0x180007dfe`

## string_xrefs

- `0x180007b41`: `DataStoreServer::GetAttributeDictionary() failed to load xml text to Dnary Dom `
- `0x180007c16`: `IXMLDOMDocument2::selectSingleNode failed for version`
- `0x180007c96`: `IXMLDOMNode::get_text failed with %!hresult!`
- `0x180007cf9`: `The dnary in resource file is of newer version than the dnary on disk. Replacing the disk copy.`
- `0x180007d82`: `DataStoreServer::GetAttributeDictionary() failed to load xml text to Dnary Dom: %!hresult! `

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall DataStoreServer::GetAttributeDictionary(DataStoreServer *this, int *a2, unsigned __int16 **a3)
{
  int *v3; // rsi
  __int64 v5; // rbx
  OLECHAR *v6; // rcx
  struct _RTL_CRITICAL_SECTION *v8; // r13
  int v9; // edi
  struct IUnknown **v10; // r14
  char v11; // al
  __int64 v12; // rcx
  int XML; // edi
  struct IUnknown *v14; // rsi
  _QWORD *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rcx
  struct IUnknown *v18; // rsi
  BSTR v19; // rax
  int v20; // eax
  HRESULT v21; // eax
  OLECHAR ***v22; // rax
  OLECHAR *v23; // rcx
  UINT v24; // eax
  unsigned __int16 *v25; // rax
  void **v26; // r15
  _QWORD *v27; // rdx
  __int64 v28; // [rsp+38h] [rbp-31h]
  VARIANTARG pvarg; // [rsp+40h] [rbp-29h] BYREF
  VARIANTARG v30; // [rsp+60h] [rbp-9h] BYREF
  BSTR bstrString; // [rsp+D0h] [rbp+67h] BYREF
  int *v32; // [rsp+D8h] [rbp+6Fh]
  unsigned __int16 **v33; // [rsp+E0h] [rbp+77h]
  char v34; // [rsp+E8h] [rbp+7Fh] BYREF

  v33 = a3;
  v32 = a2;
  v3 = a2;
  v5 = 0;
  v6 = 0;
  bstrString = 0;
  if ( !*((_BYTE *)this + 48) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WppDbgPrint("DataStoreServer() is not initialized");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids, "NPSDS");
      v6 = bstrString;
    }
    SysFreeString(v6);
    return 2147500037LL;
  }
  v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  v9 = 0;
  while ( !TryEnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8)) )
  {
    if ( ++v9 >= 100 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
      break;
    }
    SwitchToThread();
  }
  v10 = (struct IUnknown **)((char *)this + 2160);
  v11 = IASFileExists((const WCHAR *)this + 808);
  v12 = *((_QWORD *)this + 270);
  if ( !v11 )
  {
    if ( v12 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      *v10 = 0;
    }
    XML = DataStoreServer::LoadXML(v12, *((const unsigned __int16 **)this + 276), (LPVOID *)this + 270);
    if ( XML < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WppDbgPrint("DataStoreServer::GetAttributeDictionary() failed to load xml text to Dnary Dom ");
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids, "NPSDS");
      }
      goto LABEL_73;
    }
    goto LABEL_57;
  }
  XML = 0;
  if ( !v12 )
  {
    XML = DataStoreServer::Load(0, (const OLECHAR *)this + 808, (LPVOID *)this + 270);
    if ( XML < 0 || (v14 = *v10) == 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WppDbgPrint("Load() failed:%!hresult! for GetAttributeDictionary");
        WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids);
      }
      goto LABEL_72;
    }
    _bstr_t::_bstr_t((_bstr_t *)&v34, L"//Version");
    v15 = (_QWORD *)MSXML2::IXMLDOMNode::selectSingleNode(v14);
    if ( *v15 )
    {
      v5 = *v15;
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v15 + 8LL))(*v15);
    }
    if ( v28 )
      (*(void (__fastcall **)())(*(_QWORD *)v28 + 16LL))();
    if ( !v5 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WppDbgPrint("IXMLDOMDocument2::selectSingleNode failed for version");
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids, "NPSDS");
      }
      XML = -2147024883;
      goto LABEL_73;
    }
    XML = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v5 + 208LL))(v5, &bstrString);
    if ( XML < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WppDbgPrint("IXMLDOMNode::get_text failed with %!hresult!");
        v16 = 23;
LABEL_39:
        WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, &WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids);
        goto LABEL_73;
      }
      goto LABEL_73;
    }
    if ( _wtoi(bstrString) < 11 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WppDbgPrint("The dnary in resource file is of newer version than the dnary on disk. Replacing the disk copy.");
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids, "NPSDS");
      }
      if ( !*v10 )
        _com_issue_error(-2147467261);
      ((void (__fastcall *)(struct IUnknown *))(*v10)->lpVtbl->Release)(*v10);
      *v10 = 0;
      XML = DataStoreServer::LoadXML(v17, *((const unsigned __int16 **)this + 276), (LPVOID *)this + 270);
      if ( XML < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          WppDbgPrint("DataStoreServer::GetAttributeDictionary() failed to load xml text to Dnary Dom: %!hresult! ");
          v16 = 25;
          goto LABEL_39;
        }
LABEL_73:
        if ( *v10 )
        {
          ((void (__fastcall *)(struct IUnknown *))(*v10)->lpVtbl->Release)(*v10);
          *v10 = 0;
        }
        goto LABEL_75;
      }
      v18 = *v10;
      if ( !*v10 )
        _com_issue_error(-2147467261);
      v19 = SysAllocString((const OLECHAR *)this + 808);
      if ( !v19 && this != (DataStoreServer *)-1616LL )
        _com_issue_error(-2147024882);
      pvarg.vt = 8;
      pvarg.llVal = (LONGLONG)v19;
      v30 = pvarg;
      v20 = ((__int64 (__fastcall *)(struct IUnknown *, VARIANTARG *))v18->lpVtbl[22].QueryInterface)(v18, &v30);
      XML = v20;
      if ( v20 < 0 )
        _com_issue_errorex(v20, v18, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60);
      v21 = VariantClear(&pvarg);
      if ( v21 < 0 )
        _com_issue_error(v21);
    }
    v3 = v32;
  }
LABEL_57:
  if ( !*v10 )
    _com_issue_error(-2147467261);
  v22 = (OLECHAR ***)MSXML2::IXMLDOMNode::Getxml(*v10, &v34);
  if ( *v22 && (v23 = **v22) != 0 )
    v24 = SysStringLen(v23);
  else
    v24 = 0;
  *v3 = v24;
  _bstr_t::~_bstr_t((_bstr_t *)&v34);
  v25 = (unsigned __int16 *)CoTaskMemAlloc(2LL * *v3);
  v26 = (void **)v33;
  *v33 = v25;
  if ( !v25 )
  {
    XML = -2147024882;
    goto LABEL_73;
  }
  if ( !*v10 )
    _com_issue_error(-2147467261);
  v27 = *(_QWORD **)MSXML2::IXMLDOMNode::Getxml(*v10, &v34);
  if ( v27 )
    v27 = (_QWORD *)*v27;
  memcpy_0(*v26, v27, 2LL * *v3);
  _bstr_t::~_bstr_t((_bstr_t *)&v34);
LABEL_72:
  if ( XML < 0 )
    goto LABEL_73;
LABEL_75:
  LeaveCriticalSection(v8);
  SysFreeString(bstrString);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  return (unsigned int)XML;
}

```

## disassembly

```asm
0x1800079fc  mov     [rsp-8+arg_10], r8
0x180007a01  mov     [rsp-8+arg_8], rdx
0x180007a06  push    rbp
0x180007a07  push    rbx
0x180007a08  push    rsi
0x180007a09  push    rdi
0x180007a0a  push    r12
0x180007a0c  push    r13
0x180007a0e  push    r14
0x180007a10  push    r15
0x180007a12  lea     rbp, [rsp-1Fh]
0x180007a17  sub     rsp, 88h
0x180007a1e  mov     rsi, rdx
0x180007a21  mov     r15, rcx
0x180007a24  xor     ebx, ebx
0x180007a26  mov     [rbp+57h+var_90], rbx
0x180007a2a  xor     ecx, ecx
0x180007a2c  mov     [rbp+57h+bstrString], rcx
0x180007a30  cmp     [r15+30h], cl
0x180007a34  jnz     short loc_180007A97
0x180007a36  lea     rsi, WPP_GLOBAL_Control
0x180007a3d  mov     rax, cs:WPP_GLOBAL_Control
0x180007a44  cmp     rax, rsi
0x180007a47  jz      short loc_180007A86
0x180007a49  cmp     byte ptr [rax+19h], 2
0x180007a4d  jb      short loc_180007A86
0x180007a4f  test    byte ptr [rax+1Ch], 10h
0x180007a53  jz      short loc_180007A86
0x180007a55  lea     rcx, aDatastoreserve_6; "DataStoreServer() is not initialized"
0x180007a5c  call    WppDbgPrint
0x180007a61  lea     edx, [rbx+13h]
0x180007a64  lea     r9, aNpsds; "NPSDS"
0x180007a6b  lea     r8, WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids
0x180007a72  mov     rcx, cs:WPP_GLOBAL_Control
0x180007a79  mov     rcx, [rcx+10h]
0x180007a7d  call    WPP_SF_s
0x180007a82  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180007a86  call    cs:__imp_SysFreeString
0x180007a8c  nop
0x180007a8d  mov     eax, 80004005h
0x180007a92  jmp     loc_180007F46
0x180007a97  lea     r13, [r15+8]
0x180007a9b  xor     edi, edi
0x180007a9d  jmp     short loc_180007AAC
0x180007a9f  inc     edi
0x180007aa1  cmp     edi, 64h ; 'd'
0x180007aa4  jge     short loc_180007ABB
0x180007aa6  call    cs:__imp_SwitchToThread
0x180007aac  mov     rcx, r13; lpCriticalSection
0x180007aaf  call    cs:__imp_TryEnterCriticalSection
0x180007ab5  test    eax, eax
0x180007ab7  jz      short loc_180007A9F
0x180007ab9  jmp     short loc_180007AC4
0x180007abb  mov     rcx, r13; lpCriticalSection
0x180007abe  call    cs:__imp_EnterCriticalSection
0x180007ac4  lea     r12, [r15+650h]
0x180007acb  lea     r14, [r15+870h]
0x180007ad2  mov     rcx, r12
0x180007ad5  call    IASFileExists
0x180007ada  mov     rcx, [r14]
0x180007add  test    al, al
0x180007adf  jnz     loc_180007B75
0x180007ae5  test    rcx, rcx
0x180007ae8  jz      short loc_180007AFD
0x180007aea  mov     rax, [rcx]
0x180007aed  mov     rax, [rax+10h]
0x180007af1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007af6  mov     qword ptr [r14], 0
0x180007afd  mov     r8, r14
0x180007b00  mov     rdx, [r15+8A0h]
0x180007b07  call    ?LoadXML@DataStoreServer@@AEAAJPEBGAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z; DataStoreServer::LoadXML(ushort const *,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &)
0x180007b0c  mov     edi, eax
0x180007b0e  test    eax, eax
0x180007b10  jns     loc_180007E10
0x180007b16  lea     rsi, WPP_GLOBAL_Control
0x180007b1d  mov     rax, cs:WPP_GLOBAL_Control
0x180007b24  cmp     rax, rsi
0x180007b27  jz      loc_180007EFF
0x180007b2d  cmp     byte ptr [rax+19h], 2
0x180007b31  jb      loc_180007EFF
0x180007b37  test    byte ptr [rax+1Ch], 10h
0x180007b3b  jz      loc_180007EFF
0x180007b41  lea     rcx, aDatastoreserve_24; "DataStoreServer::GetAttributeDictionary"...
0x180007b48  call    WppDbgPrint
0x180007b4d  mov     edx, 14h
0x180007b52  lea     r9, aNpsds; "NPSDS"
0x180007b59  lea     r8, WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids
0x180007b60  mov     rcx, cs:WPP_GLOBAL_Control
0x180007b67  mov     rcx, [rcx+10h]
0x180007b6b  call    WPP_SF_s
0x180007b70  jmp     loc_180007EFF
0x180007b75  xor     edi, edi
0x180007b77  test    rcx, rcx
0x180007b7a  jnz     loc_180007E10
0x180007b80  mov     r8, r14
0x180007b83  mov     rdx, r12
0x180007b86  call    ?Load@DataStoreServer@@AEAAJPEBGAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z; DataStoreServer::Load(ushort const *,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &)
0x180007b8b  mov     edi, eax
0x180007b8d  test    eax, eax
0x180007b8f  js      loc_180007E3D
0x180007b95  mov     rsi, [r14]
0x180007b98  test    rsi, rsi
0x180007b9b  jz      loc_180007E3D
0x180007ba1  lea     rdx, aVersion; "//Version"
0x180007ba8  lea     rcx, [rbp+57h+arg_18]; this
0x180007bac  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180007bb1  mov     r8, rax
0x180007bb4  lea     rdx, [rbp+57h+var_88]
0x180007bb8  mov     rcx, rsi; struct IUnknown *
0x180007bbb  call    ?selectSingleNode@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectSingleNode(_bstr_t)
0x180007bc0  mov     rcx, [rax]
0x180007bc3  test    rcx, rcx
0x180007bc6  jz      short loc_180007BDC
0x180007bc8  mov     rbx, rcx
0x180007bcb  mov     [rbp+57h+var_90], rcx
0x180007bcf  mov     rax, [rcx]
0x180007bd2  mov     rax, [rax+8]
0x180007bd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bdb  nop
0x180007bdc  mov     rcx, [rbp+57h+var_88]
0x180007be0  test    rcx, rcx
0x180007be3  jz      short loc_180007BF2
0x180007be5  mov     rax, [rcx]
0x180007be8  mov     rax, [rax+10h]
0x180007bec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bf1  nop
0x180007bf2  test    rbx, rbx
0x180007bf5  jnz     short loc_180007C4D
0x180007bf7  lea     rsi, WPP_GLOBAL_Control
0x180007bfe  mov     rax, cs:WPP_GLOBAL_Control
0x180007c05  cmp     rax, rsi
0x180007c08  jz      short loc_180007C43
0x180007c0a  cmp     byte ptr [rax+19h], 2
0x180007c0e  jb      short loc_180007C43
0x180007c10  test    byte ptr [rax+1Ch], 10h
0x180007c14  jz      short loc_180007C43
0x180007c16  lea     rcx, aIxmldomdocumen_0; "IXMLDOMDocument2::selectSingleNode fail"...
0x180007c1d  call    WppDbgPrint
0x180007c22  lea     edx, [rbx+16h]
0x180007c25  lea     r9, aNpsds; "NPSDS"
0x180007c2c  lea     r8, WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids
0x180007c33  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c3a  mov     rcx, [rcx+10h]
0x180007c3e  call    WPP_SF_s
0x180007c43  mov     edi, 8007000Dh
0x180007c48  jmp     loc_180007EFF
0x180007c4d  mov     rax, [rbx]
0x180007c50  lea     rdx, [rbp+57h+bstrString]
0x180007c54  mov     rcx, rbx
0x180007c57  mov     rax, [rax+0D0h]
0x180007c5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c63  mov     edi, eax
0x180007c65  test    eax, eax
0x180007c67  jns     short loc_180007CC7
0x180007c69  lea     rsi, WPP_GLOBAL_Control
0x180007c70  mov     rax, cs:WPP_GLOBAL_Control
0x180007c77  cmp     rax, rsi
0x180007c7a  jz      loc_180007EFF
0x180007c80  cmp     byte ptr [rax+19h], 2
0x180007c84  jb      loc_180007EFF
0x180007c8a  test    byte ptr [rax+1Ch], 10h
0x180007c8e  jz      loc_180007EFF
0x180007c94  mov     edx, edi
0x180007c96  lea     rcx, aIxmldomnodeGet; "IXMLDOMNode::get_text failed with %!hre"...
0x180007c9d  call    WppDbgPrint
0x180007ca2  mov     edx, 17h
0x180007ca7  mov     [rsp+0C0h+var_A0], edi
0x180007cab  lea     r8, WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids
0x180007cb2  mov     rcx, cs:WPP_GLOBAL_Control
0x180007cb9  mov     rcx, [rcx+10h]
0x180007cbd  call    WPP_SF_sd
0x180007cc2  jmp     loc_180007EFF
0x180007cc7  mov     rcx, [rbp+57h+bstrString]; String
0x180007ccb  call    cs:__imp__wtoi
0x180007cd1  cmp     eax, 0Bh
0x180007cd4  jge     loc_180007E0C
0x180007cda  lea     rsi, WPP_GLOBAL_Control
0x180007ce1  mov     rax, cs:WPP_GLOBAL_Control
0x180007ce8  cmp     rax, rsi
0x180007ceb  jz      short loc_180007D28
0x180007ced  cmp     byte ptr [rax+19h], 2
0x180007cf1  jb      short loc_180007D28
0x180007cf3  test    byte ptr [rax+1Ch], 10h
0x180007cf7  jz      short loc_180007D28
0x180007cf9  lea     rcx, aTheDnaryInReso; "The dnary in resource file is of newer "...
0x180007d00  call    WppDbgPrint
0x180007d05  mov     edx, 18h
0x180007d0a  lea     r9, aNpsds; "NPSDS"
0x180007d11  lea     r8, WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids
0x180007d18  mov     rcx, cs:WPP_GLOBAL_Control
0x180007d1f  mov     rcx, [rcx+10h]
0x180007d23  call    WPP_SF_s
0x180007d28  mov     rcx, [r14]
0x180007d2b  test    rcx, rcx
0x180007d2e  jz      loc_180007F65
0x180007d34  mov     rax, [rcx]
0x180007d37  mov     rax, [rax+10h]
0x180007d3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d40  mov     qword ptr [r14], 0
0x180007d47  mov     r8, r14
0x180007d4a  mov     rdx, [r15+8A0h]
0x180007d51  call    ?LoadXML@DataStoreServer@@AEAAJPEBGAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z; DataStoreServer::LoadXML(ushort const *,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &)
0x180007d56  mov     edi, eax
0x180007d58  test    eax, eax
0x180007d5a  jns     short loc_180007D98
0x180007d5c  mov     rax, cs:WPP_GLOBAL_Control
0x180007d63  cmp     rax, rsi
0x180007d66  jz      loc_180007EFF
0x180007d6c  cmp     byte ptr [rax+19h], 2
0x180007d70  jb      loc_180007EFF
0x180007d76  test    byte ptr [rax+1Ch], 10h
0x180007d7a  jz      loc_180007EFF
0x180007d80  mov     edx, edi
0x180007d82  lea     rcx, aDatastoreserve_13; "DataStoreServer::GetAttributeDictionary"...
0x180007d89  call    WppDbgPrint
0x180007d8e  mov     edx, 19h
0x180007d93  jmp     loc_180007CA7
0x180007d98  mov     rsi, [r14]
0x180007d9b  test    rsi, rsi
0x180007d9e  jz      loc_180007F70
0x180007da4  mov     rcx, r12; psz
0x180007da7  call    cs:__imp_SysAllocString
0x180007dad  test    rax, rax
0x180007db0  jnz     short loc_180007DBB
0x180007db2  test    r12, r12
0x180007db5  jnz     loc_180007F7B
0x180007dbb  mov     ecx, 8
0x180007dc0  mov     word ptr [rbp+57h+pvarg], cx
0x180007dc4  mov     qword ptr [rbp+57h+pvarg+8], rax
0x180007dc8  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x180007dcc  movaps  [rbp+57h+var_60], xmm0
0x180007dd0  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x180007dd5  movsd   [rbp+57h+var_50], xmm1
0x180007dda  mov     rax, [rsi]
0x180007ddd  lea     rdx, [rbp+57h+var_60]
0x180007de1  mov     rcx, rsi
0x180007de4  mov     rax, [rax+210h]
0x180007deb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007df0  mov     edi, eax
0x180007df2  test    eax, eax
0x180007df4  js      loc_180007F86
0x180007dfa  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180007dfe  call    cs:__imp_VariantClear
0x180007e04  test    eax, eax
0x180007e06  js      loc_180007F98
0x180007e0c  mov     rsi, [rbp+57h+arg_8]
0x180007e10  mov     rcx, [r14]
0x180007e13  test    rcx, rcx
0x180007e16  jz      loc_180007FA0
0x180007e1c  lea     rdx, [rbp+57h+arg_18]
0x180007e20  call    ?Getxml@IXMLDOMNode@MSXML2@@QEAA?AV_bstr_t@@XZ; MSXML2::IXMLDOMNode::Getxml(void)
0x180007e25  mov     rcx, [rax]
0x180007e28  test    rcx, rcx
0x180007e2b  jz      short loc_180007E98
0x180007e2d  mov     rcx, [rcx]; pbstr
0x180007e30  test    rcx, rcx
0x180007e33  jz      short loc_180007E98
0x180007e35  call    cs:__imp_SysStringLen
0x180007e3b  jmp     short loc_180007E9A
0x180007e3d  lea     rsi, WPP_GLOBAL_Control
0x180007e44  mov     rax, cs:WPP_GLOBAL_Control
0x180007e4b  cmp     rax, rsi
0x180007e4e  jz      loc_180007EFB
0x180007e54  cmp     byte ptr [rax+19h], 2
0x180007e58  jb      loc_180007EFB
0x180007e5e  test    byte ptr [rax+1Ch], 10h
0x180007e62  jz      loc_180007EFB
0x180007e68  mov     edx, edi
0x180007e6a  lea     rcx, aLoadFailedHres; "Load() failed:%!hresult! for GetAttribu"...
0x180007e71  call    WppDbgPrint
0x180007e76  mov     edx, 15h
0x180007e7b  mov     [rsp+0C0h+var_A0], edi
0x180007e7f  lea     r8, WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids
0x180007e86  mov     rcx, cs:WPP_GLOBAL_Control
0x180007e8d  mov     rcx, [rcx+10h]
0x180007e91  call    WPP_SF_sd
0x180007e96  jmp     short loc_180007EFB
0x180007e98  xor     eax, eax
0x180007e9a  mov     [rsi], eax
0x180007e9c  lea     rcx, [rbp+57h+arg_18]; this
0x180007ea0  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180007ea5  movsxd  rcx, dword ptr [rsi]
0x180007ea8  add     rcx, rcx; cb
0x180007eab  call    cs:__imp_CoTaskMemAlloc
0x180007eb1  mov     r15, [rbp+57h+arg_10]
0x180007eb5  mov     [r15], rax
0x180007eb8  test    rax, rax
0x180007ebb  jnz     short loc_180007EC4
0x180007ebd  mov     edi, 8007000Eh
0x180007ec2  jmp     short loc_180007EFF
0x180007ec4  mov     rcx, [r14]
0x180007ec7  test    rcx, rcx
0x180007eca  jz      loc_180007F5A
0x180007ed0  lea     rdx, [rbp+57h+arg_18]
0x180007ed4  call    ?Getxml@IXMLDOMNode@MSXML2@@QEAA?AV_bstr_t@@XZ; MSXML2::IXMLDOMNode::Getxml(void)
0x180007ed9  mov     rdx, [rax]
0x180007edc  test    rdx, rdx
0x180007edf  jz      short loc_180007EE4
0x180007ee1  mov     rdx, [rdx]; Src
0x180007ee4  movsxd  r8, dword ptr [rsi]
  ... truncated ...
```
