# DataStoreServer::LoadXML(ushort const *,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &)

- ea: `0x180009af8`
- end: `0x18000a193`
- name: `?LoadXML@DataStoreServer@@AEAAJPEBGAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z`
- size: `1691`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, LPVOID *)`
- caller_count: `5`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800079fc`
- `0x1800081b8`
- `0x1800086c8`
- `0x18000a4a0`
- `0x18000b210`

## callees

- `0x180002310`
- `0x1800071ac`
- `0x180007460`
- `0x18000750c`
- `0x180007628`
- `0x1800076dc`
- `0x18000784c`
- `0x180007894`
- `0x180007938`
- `0x180009af8`
- `0x18000c08c`
- `0x18000d990`
- `0x18000db68`
- `0x18000db7c`
- `0x180010010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180009f89`
- `OLEAUT32!__imp_VariantClear` at `0x180009f89`

## string_xrefs

- `0x180009b55`: `IXMLDOMDocument2::CreateInstance failed %!hresult!`
- `0x18000a048`: `DataStoreServer LoadXML failed: %S`

## pseudocode

```c
__int64 __fastcall DataStoreServer::LoadXML(__int64 a1, const unsigned __int16 *a2, LPVOID *a3)
{
  int Instance; // eax
  unsigned int v6; // ebx
  __int64 result; // rax
  struct IUnknown *v8; // rbx
  int v9; // eax
  struct IUnknown *v10; // rbx
  _bstr_t *v11; // rdi
  __int64 v12; // rdx
  int v13; // eax
  __int16 v14; // bx
  struct IUnknown *v15; // rbx
  int v16; // eax
  struct IUnknown *v17; // rbx
  _bstr_t *v18; // rdi
  struct _bstr_t *v19; // rax
  __int64 v20; // rcx
  int v21; // eax
  __int64 v22; // r14
  _QWORD *v23; // rax
  struct _bstr_t *v24; // rax
  int v25; // eax
  __int64 v26; // r14
  _QWORD *v27; // rax
  struct _bstr_t *v28; // rax
  int v29; // eax
  struct _bstr_t *v30; // rax
  _bstr_t *v31; // rax
  HRESULT v32; // eax
  int v33; // r8d
  int v34; // r9d
  __int64 v35; // rcx
  LPVOID v36; // rcx
  struct IUnknown *v37; // [rsp+30h] [rbp-B8h] BYREF
  __int64 v38; // [rsp+38h] [rbp-B0h] BYREF
  __int64 v39; // [rsp+40h] [rbp-A8h] BYREF
  __int64 v40; // [rsp+48h] [rbp-A0h] BYREF
  __int64 v41; // [rsp+50h] [rbp-98h] BYREF
  __int64 v42; // [rsp+58h] [rbp-90h] BYREF
  __int64 *v43; // [rsp+60h] [rbp-88h] BYREF
  _QWORD *v44; // [rsp+68h] [rbp-80h] BYREF
  _QWORD *v45; // [rsp+70h] [rbp-78h] BYREF
  _bstr_t *v46; // [rsp+78h] [rbp-70h] BYREF
  _BYTE v47[8]; // [rsp+80h] [rbp-68h] BYREF
  _BYTE v48[8]; // [rsp+88h] [rbp-60h] BYREF
  _BYTE v49[8]; // [rsp+90h] [rbp-58h] BYREF
  _BYTE v50[8]; // [rsp+98h] [rbp-50h] BYREF
  _BYTE v51[8]; // [rsp+A0h] [rbp-48h] BYREF
  VARIANTARG pvarg; // [rsp+A8h] [rbp-40h] BYREF
  struct IUnknown *v53; // [rsp+C0h] [rbp-28h]
  const _com_error *v54; // [rsp+C8h] [rbp-20h] BYREF
  unsigned int v55; // [rsp+F0h] [rbp+8h] BYREF
  int v56; // [rsp+F4h] [rbp+Ch]
  __int64 v57; // [rsp+108h] [rbp+20h] BYREF

  v56 = HIDWORD(a1);
  v55 = 0;
  Instance = ((__int64 (__fastcall *)(LPVOID *))_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::CreateInstance)(a3);
  v6 = Instance;
  if ( Instance >= 0 )
  {
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v8 = (struct IUnknown *)*a3;
      if ( !*a3 )
        _com_issue_error(-2147467261);
      v9 = ((__int64 (__fastcall *)(LPVOID, _QWORD))v8->lpVtbl[21].QueryInterface)(*a3, 0);
      if ( v9 < 0 )
        _com_issue_errorex(v9, v8, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60);
      v10 = (struct IUnknown *)*a3;
      if ( !*a3 )
        _com_issue_error(-2147467261);
      v11 = _bstr_t::_bstr_t((_bstr_t *)&v57, a2);
      v46 = v11;
      LOWORD(v55) = 0;
      if ( *(_QWORD *)v11 )
        v12 = **(_QWORD **)v11;
      else
        v12 = 0;
      v13 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, unsigned int *))v10->lpVtbl[21].Release)(
              v10,
              v12,
              &v55);
      if ( v13 < 0 )
        _com_issue_errorex(v13, v10, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60);
      v14 = v55;
      _bstr_t::~_bstr_t(v11);
      if ( v14 == -1 )
      {
        result = 0;
      }
      else
      {
        v15 = (struct IUnknown *)*a3;
        if ( !*a3 )
          _com_issue_error(-2147467261);
        v37 = 0;
        v16 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v15->lpVtbl[20].QueryInterface)(v15, &v37);
        if ( v16 < 0 )
          _com_issue_errorex(v16, v15, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60);
        v17 = v37;
        v53 = v37;
        v18 = _bstr_t::_bstr_t((_bstr_t *)&v46, "\n=====================");
        v19 = _bstr_t::_bstr_t((_bstr_t *)v51, "\nReason: ");
        v20 = *(_QWORD *)v18;
        v42 = v20;
        if ( v20 )
        {
          _InterlockedAdd((volatile signed __int32 *)(v20 + 16), 1u);
          v17 = v37;
        }
        v55 = 3;
        _bstr_t::operator+=((struct _bstr_t *)&v42, v19);
        if ( !v17 )
          _com_issue_error(-2147467261);
        v57 = 0;
        v21 = ((__int64 (__fastcall *)(struct IUnknown *, __int64 *))v17->lpVtbl[3].QueryInterface)(v17, &v57);
        if ( v21 < 0 )
          _com_issue_errorex(v21, v17, &GUID_3efaa426_272f_11d2_836f_0000f87a7782);
        v22 = v57;
        v23 = operator new(0x18u);
        v45 = v23;
        if ( v23 )
        {
          v23[1] = 0;
          *((_DWORD *)v23 + 4) = 1;
          *v23 = v22;
        }
        v45 = v23;
        if ( !v23 )
          _com_issue_error(-2147024882);
        v41 = v42;
        if ( v42 )
        {
          _InterlockedAdd((volatile signed __int32 *)(v42 + 16), 1u);
          v17 = v37;
        }
        v55 = 15;
        _bstr_t::operator+=((struct _bstr_t *)&v41, (struct _bstr_t *)&v45);
        v24 = _bstr_t::_bstr_t((_bstr_t *)v50, "\nSource: ");
        v40 = v41;
        if ( v41 )
        {
          _InterlockedAdd((volatile signed __int32 *)(v41 + 16), 1u);
          v17 = v37;
        }
        v55 = 31;
        _bstr_t::operator+=((struct _bstr_t *)&v40, v24);
        v57 = 0;
        v25 = ((__int64 (__fastcall *)(struct IUnknown *, __int64 *))v17->lpVtbl[3].AddRef)(v17, &v57);
        if ( v25 < 0 )
          _com_issue_errorex(v25, v17, &GUID_3efaa426_272f_11d2_836f_0000f87a7782);
        v26 = v57;
        v27 = operator new(0x18u);
        v44 = v27;
        if ( v27 )
        {
          v27[1] = 0;
          *((_DWORD *)v27 + 4) = 1;
          *v27 = v26;
        }
        v44 = v27;
        if ( !v27 )
          _com_issue_error(-2147024882);
        v39 = v40;
        if ( v40 )
        {
          _InterlockedAdd((volatile signed __int32 *)(v40 + 16), 1u);
          v17 = v37;
        }
        v55 = 127;
        _bstr_t::operator+=((struct _bstr_t *)&v39, (struct _bstr_t *)&v44);
        v28 = _bstr_t::_bstr_t((_bstr_t *)v49, "\nLine: ");
        v38 = v39;
        if ( v39 )
        {
          _InterlockedAdd((volatile signed __int32 *)(v39 + 16), 1u);
          v17 = v37;
        }
        v55 = 255;
        _bstr_t::operator+=((struct _bstr_t *)&v38, v28);
        LODWORD(v57) = 0;
        v29 = ((__int64 (__fastcall *)(struct IUnknown *, __int64 *))v17->lpVtbl[3].Release)(v17, &v57);
        if ( v29 < 0 )
          _com_issue_errorex(v29, v17, &GUID_3efaa426_272f_11d2_836f_0000f87a7782);
        pvarg.vt = 3;
        pvarg.lVal = v57;
        v30 = _bstr_t::_bstr_t((_bstr_t *)v48, (const struct _variant_t *)&pvarg);
        v57 = v38;
        if ( v38 )
        {
          _InterlockedAdd((volatile signed __int32 *)(v38 + 16), 1u);
          v17 = v37;
        }
        v55 = 511;
        _bstr_t::operator+=((struct _bstr_t *)&v57, v30);
        v31 = _bstr_t::_bstr_t((_bstr_t *)v47, "\n");
        _bstr_t::operator+(&v57, &v43, v31);
        _bstr_t::~_bstr_t((_bstr_t *)v47);
        v55 = 255;
        _bstr_t::~_bstr_t((_bstr_t *)&v57);
        _bstr_t::~_bstr_t((_bstr_t *)v48);
        v32 = VariantClear(&pvarg);
        if ( v32 < 0 )
          _com_issue_error(v32);
        _bstr_t::~_bstr_t((_bstr_t *)&v38);
        _bstr_t::~_bstr_t((_bstr_t *)v49);
        _bstr_t::~_bstr_t((_bstr_t *)&v39);
        _bstr_t::~_bstr_t((_bstr_t *)&v44);
        _bstr_t::~_bstr_t((_bstr_t *)&v40);
        _bstr_t::~_bstr_t((_bstr_t *)v50);
        _bstr_t::~_bstr_t((_bstr_t *)&v41);
        _bstr_t::~_bstr_t((_bstr_t *)&v45);
        _bstr_t::~_bstr_t((_bstr_t *)&v42);
        _bstr_t::~_bstr_t((_bstr_t *)v51);
        _bstr_t::~_bstr_t((_bstr_t *)&v46);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          WppDbgPrint("DataStoreServer LoadXML failed: %S");
          if ( v43 )
            v35 = *v43;
          else
            v35 = 0;
          WPP_SF_sS(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, v33, v34, v35);
        }
        v36 = *a3;
        if ( *a3 )
        {
          *a3 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v36 + 16LL))(v36);
        }
        _bstr_t::~_bstr_t((_bstr_t *)&v43);
        ((void (__fastcall *)(struct IUnknown *))v17->lpVtbl->Release)(v17);
        result = 2147500037LL;
      }
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &_com_error `RTTI Type Descriptor', &v54) )
      {
        v55 = *((_DWORD *)v54 + 2);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          WppDbgPrint("IXMLDOMDocument2::loadXML failed %!hresult!");
          WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids);
        }
        result = v55;
        __eh34_try_continuation(0, &_com_error `RTTI Type Descriptor', &loc_18000A0C2);
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WppDbgPrint("IXMLDOMDocument2::CreateInstance failed %!hresult!");
      WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids);
    }
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x180009af8  mov     rax, rsp
0x180009afb  mov     [rax+10h], rbx
0x180009aff  mov     [rax+18h], rsi
0x180009b03  mov     [rax+8], rcx
0x180009b07  push    rdi
0x180009b08  push    r13
0x180009b0a  push    r14
0x180009b0c  sub     rsp, 0D0h
0x180009b13  mov     rsi, r8
0x180009b16  mov     rdi, rdx
0x180009b19  mov     dword ptr [rax+8], 0
0x180009b20  mov     r9d, 17h
0x180009b26  mov     rcx, r8; ppv
0x180009b29  call    ?CreateInstance@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEAAJAEBU_GUID@@PEAUIUnknown@@K@Z; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::CreateInstance(_GUID const &,IUnknown *,ulong)
0x180009b2e  mov     ebx, eax
0x180009b30  test    eax, eax
0x180009b32  jns     short loc_180009B88
0x180009b34  lea     rax, WPP_GLOBAL_Control
0x180009b3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b42  cmp     rcx, rax
0x180009b45  jz      short loc_180009B81
0x180009b47  cmp     byte ptr [rcx+19h], 2
0x180009b4b  jb      short loc_180009B81
0x180009b4d  test    byte ptr [rcx+1Ch], 10h
0x180009b51  jz      short loc_180009B81
0x180009b53  mov     edx, ebx
0x180009b55  lea     rcx, aIxmldomdocumen_3; "IXMLDOMDocument2::CreateInstance failed"...
0x180009b5c  call    WppDbgPrint
0x180009b61  mov     edx, 39h ; '9'
0x180009b66  mov     dword ptr [rsp+0E8h+var_C8], ebx
0x180009b6a  lea     r8, WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids
0x180009b71  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b78  mov     rcx, [rcx+10h]
0x180009b7c  call    WPP_SF_sd
0x180009b81  mov     eax, ebx
0x180009b83  jmp     loc_18000A0C9
0x180009b88  mov     rbx, [rsi]
0x180009b8b  test    rbx, rbx
0x180009b8e  jz      loc_18000A0E2
0x180009b94  mov     rax, [rbx]
0x180009b97  xor     edx, edx
0x180009b99  mov     rcx, rbx
0x180009b9c  mov     rax, [rax+1F8h]
0x180009ba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ba8  test    eax, eax
0x180009baa  js      loc_18000A0EC
0x180009bb0  mov     rbx, [rsi]
0x180009bb3  test    rbx, rbx
0x180009bb6  jz      loc_18000A0FD
0x180009bbc  mov     rdx, rdi; unsigned __int16 *
0x180009bbf  lea     rcx, [rsp+0E8h+arg_18]; this
0x180009bc7  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180009bcc  mov     rdi, rax
0x180009bcf  mov     [rsp+0E8h+var_70], rax
0x180009bd4  xor     ecx, ecx
0x180009bd6  mov     word ptr [rsp+0E8h+arg_0], cx
0x180009bde  mov     rcx, [rbx]
0x180009be1  mov     r9, [rcx+208h]
0x180009be8  mov     rax, [rax]
0x180009beb  test    rax, rax
0x180009bee  jz      short loc_180009BF5
0x180009bf0  mov     rdx, [rax]
0x180009bf3  jmp     short loc_180009BF7
0x180009bf5  xor     edx, edx
0x180009bf7  lea     r8, [rsp+0E8h+arg_0]
0x180009bff  mov     rcx, rbx
0x180009c02  mov     rax, r9
0x180009c05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c0a  test    eax, eax
0x180009c0c  js      loc_18000A108
0x180009c12  movzx   ebx, word ptr [rsp+0E8h+arg_0]
0x180009c1a  mov     rcx, rdi; this
0x180009c1d  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180009c22  cmp     bx, 0FFFFh
0x180009c26  jz      loc_18000A0BE
0x180009c2c  mov     rbx, [rsi]
0x180009c2f  test    rbx, rbx
0x180009c32  jz      loc_18000A11A
0x180009c38  mov     [rsp+0E8h+var_B8], 0
0x180009c41  mov     rax, [rbx]
0x180009c44  lea     rdx, [rsp+0E8h+var_B8]
0x180009c49  mov     rcx, rbx
0x180009c4c  mov     rax, [rax+1E0h]
0x180009c53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c58  test    eax, eax
0x180009c5a  js      loc_18000A124
0x180009c60  mov     rbx, [rsp+0E8h+var_B8]
0x180009c65  mov     [rsp+0E8h+var_28], rbx
0x180009c6d  lea     rdx, asc_180015048; "\n====================="
0x180009c74  lea     rcx, [rsp+0E8h+var_70]; this
0x180009c79  call    ??0_bstr_t@@QEAA@PEBD@Z; _bstr_t::_bstr_t(char const *)
0x180009c7e  mov     rdi, rax
0x180009c81  lea     rdx, aReason; "\nReason: "
0x180009c88  lea     rcx, [rsp+0E8h+var_48]; this
0x180009c90  call    ??0_bstr_t@@QEAA@PEBD@Z; _bstr_t::_bstr_t(char const *)
0x180009c95  nop
0x180009c96  mov     rcx, [rdi]
0x180009c99  mov     [rsp+0E8h+var_90], rcx
0x180009c9e  mov     edi, 1
0x180009ca3  test    rcx, rcx
0x180009ca6  jz      short loc_180009CB1
0x180009ca8  lock add [rcx+10h], edi
0x180009cac  mov     rbx, [rsp+0E8h+var_B8]
0x180009cb1  mov     r13d, 3
0x180009cb7  mov     [rsp+0E8h+arg_0], r13d
0x180009cbf  mov     rdx, rax; struct _bstr_t *
0x180009cc2  lea     rcx, [rsp+0E8h+var_90]; struct _bstr_t *
0x180009cc7  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x180009ccc  test    rbx, rbx
0x180009ccf  jz      loc_18000A136
0x180009cd5  mov     [rsp+0E8h+arg_18], 0
0x180009ce1  mov     rax, [rbx]
0x180009ce4  lea     rdx, [rsp+0E8h+arg_18]
0x180009cec  mov     rcx, rbx
0x180009cef  mov     rax, [rax+48h]
0x180009cf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009cf8  test    eax, eax
0x180009cfa  js      loc_18000A140
0x180009d00  mov     r14, [rsp+0E8h+arg_18]
0x180009d08  mov     ecx, 18h; Size
0x180009d0d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009d12  mov     [rsp+0E8h+var_78], rax
0x180009d17  test    rax, rax
0x180009d1a  jz      short loc_180009D2A
0x180009d1c  mov     qword ptr [rax+8], 0
0x180009d24  mov     [rax+10h], edi
0x180009d27  mov     [rax], r14
0x180009d2a  mov     [rsp+0E8h+var_78], rax
0x180009d2f  test    rax, rax
0x180009d32  jz      loc_18000A151
0x180009d38  mov     rax, [rsp+0E8h+var_90]
0x180009d3d  mov     [rsp+0E8h+var_98], rax
0x180009d42  test    rax, rax
0x180009d45  jz      short loc_180009D50
0x180009d47  lock add [rax+10h], edi
0x180009d4b  mov     rbx, [rsp+0E8h+var_B8]
0x180009d50  mov     [rsp+0E8h+arg_0], 0Fh
0x180009d5b  lea     rdx, [rsp+0E8h+var_78]; struct _bstr_t *
0x180009d60  lea     rcx, [rsp+0E8h+var_98]; struct _bstr_t *
0x180009d65  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x180009d6a  lea     rdx, aSource; "\nSource: "
0x180009d71  lea     rcx, [rsp+0E8h+var_50]; this
0x180009d79  call    ??0_bstr_t@@QEAA@PEBD@Z; _bstr_t::_bstr_t(char const *)
0x180009d7e  nop
0x180009d7f  mov     rcx, [rsp+0E8h+var_98]
0x180009d84  mov     [rsp+0E8h+var_A0], rcx
0x180009d89  test    rcx, rcx
0x180009d8c  jz      short loc_180009D97
0x180009d8e  lock add [rcx+10h], edi
0x180009d92  mov     rbx, [rsp+0E8h+var_B8]
0x180009d97  mov     [rsp+0E8h+arg_0], 1Fh
0x180009da2  mov     rdx, rax; struct _bstr_t *
0x180009da5  lea     rcx, [rsp+0E8h+var_A0]; struct _bstr_t *
0x180009daa  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x180009daf  mov     [rsp+0E8h+arg_18], 0
0x180009dbb  mov     rax, [rbx]
0x180009dbe  lea     rdx, [rsp+0E8h+arg_18]
0x180009dc6  mov     rcx, rbx
0x180009dc9  mov     rax, [rax+50h]
0x180009dcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009dd2  test    eax, eax
0x180009dd4  js      loc_18000A15C
0x180009dda  mov     r14, [rsp+0E8h+arg_18]
0x180009de2  mov     ecx, 18h; Size
0x180009de7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009dec  mov     [rsp+0E8h+var_80], rax
0x180009df1  test    rax, rax
0x180009df4  jz      short loc_180009E04
0x180009df6  mov     qword ptr [rax+8], 0
0x180009dfe  mov     [rax+10h], edi
0x180009e01  mov     [rax], r14
0x180009e04  mov     [rsp+0E8h+var_80], rax
0x180009e09  test    rax, rax
0x180009e0c  jz      loc_18000A16D
0x180009e12  mov     rax, [rsp+0E8h+var_A0]
0x180009e17  mov     [rsp+0E8h+var_A8], rax
0x180009e1c  test    rax, rax
0x180009e1f  jz      short loc_180009E2A
0x180009e21  lock add [rax+10h], edi
0x180009e25  mov     rbx, [rsp+0E8h+var_B8]
0x180009e2a  mov     [rsp+0E8h+arg_0], 7Fh
0x180009e35  lea     rdx, [rsp+0E8h+var_80]; struct _bstr_t *
0x180009e3a  lea     rcx, [rsp+0E8h+var_A8]; struct _bstr_t *
0x180009e3f  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x180009e44  lea     rdx, aLine; "\nLine: "
0x180009e4b  lea     rcx, [rsp+0E8h+var_58]; this
0x180009e53  call    ??0_bstr_t@@QEAA@PEBD@Z; _bstr_t::_bstr_t(char const *)
0x180009e58  nop
0x180009e59  mov     rcx, [rsp+0E8h+var_A8]
0x180009e5e  mov     [rsp+0E8h+var_B0], rcx
0x180009e63  test    rcx, rcx
0x180009e66  jz      short loc_180009E71
0x180009e68  lock add [rcx+10h], edi
0x180009e6c  mov     rbx, [rsp+0E8h+var_B8]
0x180009e71  mov     r14d, 0FFh
0x180009e77  mov     [rsp+0E8h+arg_0], r14d
0x180009e7f  mov     rdx, rax; struct _bstr_t *
0x180009e82  lea     rcx, [rsp+0E8h+var_B0]; struct _bstr_t *
0x180009e87  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x180009e8c  mov     dword ptr [rsp+0E8h+arg_18], 0
0x180009e97  mov     rax, [rbx]
0x180009e9a  lea     rdx, [rsp+0E8h+arg_18]
0x180009ea2  mov     rcx, rbx
0x180009ea5  mov     rax, [rax+58h]
0x180009ea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009eae  test    eax, eax
0x180009eb0  js      loc_18000A178
0x180009eb6  mov     word ptr [rsp+0E8h+pvarg], r13w
0x180009ebf  mov     eax, dword ptr [rsp+0E8h+arg_18]
0x180009ec6  mov     word ptr [rsp+0E8h+pvarg+8], ax
0x180009ece  sar     eax, 10h
0x180009ed1  mov     word ptr [rsp+0E8h+pvarg+0Ah], ax
0x180009ed9  lea     rdx, [rsp+0E8h+pvarg]; struct _variant_t *
0x180009ee1  lea     rcx, [rsp+0E8h+var_60]; this
0x180009ee9  call    ??0_bstr_t@@QEAA@AEBV_variant_t@@@Z; _bstr_t::_bstr_t(_variant_t const &)
0x180009eee  nop
0x180009eef  mov     rcx, [rsp+0E8h+var_B0]
0x180009ef4  mov     [rsp+0E8h+arg_18], rcx
0x180009efc  test    rcx, rcx
0x180009eff  jz      short loc_180009F0A
0x180009f01  lock add [rcx+10h], edi
0x180009f05  mov     rbx, [rsp+0E8h+var_B8]
0x180009f0a  mov     [rsp+0E8h+arg_0], 1FFh
0x180009f15  mov     rdx, rax; struct _bstr_t *
0x180009f18  lea     rcx, [rsp+0E8h+arg_18]; struct _bstr_t *
0x180009f20  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x180009f25  lea     rdx, asc_180015088; "\n"
0x180009f2c  lea     rcx, [rsp+0E8h+var_68]; this
0x180009f34  call    ??0_bstr_t@@QEAA@PEBD@Z; _bstr_t::_bstr_t(char const *)
0x180009f39  nop
0x180009f3a  mov     r8, rax
0x180009f3d  lea     rdx, [rsp+0E8h+var_88]
0x180009f42  lea     rcx, [rsp+0E8h+arg_18]
0x180009f4a  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x180009f4f  nop
0x180009f50  lea     rcx, [rsp+0E8h+var_68]; this
0x180009f58  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180009f5d  mov     [rsp+0E8h+arg_0], r14d
0x180009f65  lea     rcx, [rsp+0E8h+arg_18]; this
0x180009f6d  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180009f72  nop
0x180009f73  lea     rcx, [rsp+0E8h+var_60]; this
0x180009f7b  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180009f80  nop
0x180009f81  lea     rcx, [rsp+0E8h+pvarg]; pvarg
0x180009f89  call    cs:__imp_VariantClear
0x180009f8f  test    eax, eax
0x180009f91  js      loc_18000A18A
0x180009f97  lea     rcx, [rsp+0E8h+var_B0]; this
0x180009f9c  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180009fa1  nop
0x180009fa2  lea     rcx, [rsp+0E8h+var_58]; this
0x180009faa  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180009faf  nop
0x180009fb0  lea     rcx, [rsp+0E8h+var_A8]; this
0x180009fb5  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180009fba  nop
0x180009fbb  lea     rcx, [rsp+0E8h+var_80]; this
0x180009fc0  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180009fc5  nop
0x180009fc6  lea     rcx, [rsp+0E8h+var_A0]; this
0x180009fcb  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180009fd0  nop
0x180009fd1  lea     rcx, [rsp+0E8h+var_50]; this
0x180009fd9  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180009fde  nop
0x180009fdf  lea     rcx, [rsp+0E8h+var_98]; this
0x180009fe4  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180009fe9  nop
0x180009fea  lea     rcx, [rsp+0E8h+var_78]; this
0x180009fef  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180009ff4  nop
0x180009ff5  lea     rcx, [rsp+0E8h+var_90]; this
0x180009ffa  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180009fff  nop
0x18000a000  lea     rcx, [rsp+0E8h+var_48]; this
0x18000a008  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18000a00d  nop
0x18000a00e  lea     rcx, [rsp+0E8h+var_70]; this
0x18000a013  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18000a018  lea     rax, WPP_GLOBAL_Control
0x18000a01f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a026  cmp     rcx, rax
0x18000a029  jz      short loc_18000A080
0x18000a02b  cmp     byte ptr [rcx+19h], 2
0x18000a02f  jb      short loc_18000A080
0x18000a031  test    byte ptr [rcx+1Ch], 10h
0x18000a035  jz      short loc_18000A080
0x18000a037  mov     rax, [rsp+0E8h+var_88]
0x18000a03c  test    rax, rax
0x18000a03f  jz      short loc_18000A046
0x18000a041  mov     rdx, [rax]
0x18000a044  jmp     short loc_18000A048
0x18000a046  xor     edx, edx
0x18000a048  lea     rcx, aDatastoreserve_21; "DataStoreServer LoadXML failed: %S"
0x18000a04f  call    WppDbgPrint
0x18000a054  mov     rax, [rsp+0E8h+var_88]
0x18000a059  test    rax, rax
0x18000a05c  jz      short loc_18000A063
0x18000a05e  mov     rcx, [rax]
  ... truncated ...
```
