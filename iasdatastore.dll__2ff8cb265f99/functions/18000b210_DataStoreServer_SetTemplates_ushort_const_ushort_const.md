# DataStoreServer::SetTemplates(ushort const *,ushort const *)

- ea: `0x18000b210`
- end: `0x18000be03`
- name: `?SetTemplates@DataStoreServer@@QEAAJPEBG0@Z`
- size: `3059`
- prototype: `__int64 __fastcall(DataStoreServer *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180007060`

## callees

- `0x180007150`
- `0x1800071ac`
- `0x180007628`
- `0x1800076dc`
- `0x1800093cc`
- `0x180009af8`
- `0x18000b210`
- `0x18000be1c`
- `0x18000bf74`
- `0x18000c000`
- `0x18000c08c`
- `0x18000d8f0`
- `0x18000d990`
- `0x18000db68`
- `0x18000db7c`
- `0x180010010`

## import_xrefs

- `KERNEL32!TryEnterCriticalSection` at `0x18000b36a`
- `KERNEL32!TryEnterCriticalSection` at `0x18000b36a`
- `KERNEL32!SwitchToThread` at `0x18000b361`
- `KERNEL32!SwitchToThread` at `0x18000b361`
- `KERNEL32!EnterCriticalSection` at `0x18000b379`
- `KERNEL32!EnterCriticalSection` at `0x18000b379`
- `KERNEL32!LeaveCriticalSection` at `0x18000bc5c`
- `KERNEL32!LeaveCriticalSection` at `0x18000bc5c`
- `OLEAUT32!__imp_SysAllocString` at `0x18000b799`
- `OLEAUT32!__imp_SysAllocString` at `0x18000b9ad`
- `OLEAUT32!__imp_SysAllocString` at `0x18000bbc5`
- `OLEAUT32!__imp_SysAllocString` at `0x18000b799`
- `OLEAUT32!__imp_SysAllocString` at `0x18000b9ad`
- `OLEAUT32!__imp_SysAllocString` at `0x18000bbc5`
- `OLEAUT32!__imp_VariantClear` at `0x18000b7fb`
- `OLEAUT32!__imp_VariantClear` at `0x18000ba10`
- `OLEAUT32!__imp_VariantClear` at `0x18000bc27`
- `OLEAUT32!__imp_VariantClear` at `0x18000b7fb`
- `OLEAUT32!__imp_VariantClear` at `0x18000ba10`
- `OLEAUT32!__imp_VariantClear` at `0x18000bc27`

## string_xrefs

- `0x18000b302`: `Invalid data for DataStoreServer::SetTemplates`
- `0x18000b4e7`: `Load() failed:%!hresult! for SetTemplates`
- `0x18000b569`: `DataStoreServer::SetTemplates() failed to load xml text to IAS Dom `
- `0x18000bb0d`: `DataStoreServer::SetTemplates() error: exsiting data doesn't have the:%S node`
- `0x18000b901`: `DataStoreServer::SetTemplates(), failed to loadXML for a root replacement`
- `0x18000ba7f`: `Load failed:%!hresult! in SetTemplates()`
- `0x18000bb63`: `Error: DataStoreServer::SetTemplates() tries to save no data to a non-existing file`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall DataStoreServer::SetTemplates(
        DataStoreServer *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 v6; // rbx
  int v8; // edi
  __int64 v9; // rcx
  int XML; // edi
  struct IUnknown *v11; // rdi
  int v12; // eax
  struct IUnknown *v13; // rdi
  __int64 *v14; // rax
  __int64 v15; // rcx
  const OLECHAR *v16; // r13
  struct IUnknown **v17; // rsi
  char v18; // al
  __int64 v19; // rcx
  struct IUnknown *v20; // rdi
  int v21; // eax
  struct IUnknown *v22; // rdi
  struct IUnknown **v23; // rax
  struct IUnknown *v24; // rcx
  struct IUnknown *v25; // r15
  int v26; // eax
  int v27; // eax
  struct IUnknown *v28; // r14
  int v29; // eax
  struct IUnknown *v30; // r15
  int v31; // eax
  struct IUnknown *v32; // r12
  struct IUnknown *v33; // rdi
  BSTR v34; // rax
  int v35; // eax
  HRESULT v36; // eax
  DataStoreServer *v37; // r13
  struct IUnknown *v38; // rdi
  int v39; // eax
  __int64 v40; // rcx
  struct IUnknown *v41; // rdi
  _bstr_t *v42; // r12
  __int64 v43; // rdx
  int v44; // eax
  __int16 v45; // di
  struct IUnknown *v46; // r12
  BSTR v47; // rax
  int v48; // eax
  HRESULT v49; // eax
  int v50; // r8d
  int v51; // r9d
  struct IUnknown *v52; // r14
  BSTR v53; // rax
  int v54; // eax
  HRESULT v55; // eax
  struct IUnknown *v56; // [rsp+30h] [rbp-98h] BYREF
  struct IUnknown *v57; // [rsp+38h] [rbp-90h] BYREF
  struct IUnknown *v58; // [rsp+40h] [rbp-88h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-80h] BYREF
  struct IUnknown *v60; // [rsp+60h] [rbp-68h]
  struct IUnknown *v61; // [rsp+68h] [rbp-60h]
  VARIANTARG v62; // [rsp+70h] [rbp-58h] BYREF
  __int64 v63; // [rsp+90h] [rbp-38h]
  _bstr_t *v64; // [rsp+98h] [rbp-30h]
  struct IUnknown *v66; // [rsp+E8h] [rbp+20h] BYREF

  v6 = 0;
  v63 = 0;
  v60 = 0;
  v56 = 0;
  if ( !*((_BYTE *)this + 48) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WppDbgPrint("DataStoreServer() is not initialized");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids, "NPSDS");
    }
    return 2147500037LL;
  }
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WppDbgPrint("Invalid data for DataStoreServer::SetTemplates");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids, "NPSDS");
    }
    return 2147942487LL;
  }
  v8 = 0;
  while ( !TryEnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8)) )
  {
    if ( ++v8 >= 100 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
      break;
    }
    SwitchToThread();
  }
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 272) + 16LL))(*((_QWORD *)this + 272));
  try
  {
    if ( a3 )
    {
      XML = DataStoreServer::LoadXML(v9, a3, &v56);
      if ( XML < 0 )
      {
        v17 = (struct IUnknown **)((char *)this + 2152);
LABEL_124:
        v37 = this;
        goto LABEL_125;
      }
      v11 = v56;
      if ( !v56 )
        _com_issue_error(-2147467261);
      v66 = 0;
      v12 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v56->lpVtbl[15].QueryInterface)(v56, &v66);
      if ( v12 < 0 )
        _com_issue_errorex(v12, v11, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60);
      v13 = v66;
      if ( !v66 )
        _com_issue_error(-2147467261);
      _bstr_t::_bstr_t((_bstr_t *)&v58, L".");
      v14 = (__int64 *)MSXML2::IXMLDOMNode::selectSingleNode(v13);
      v15 = *v14;
      if ( *v14 )
      {
        v6 = *v14;
        v63 = *v14;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
      }
      if ( v57 )
        ((void (__fastcall *)(struct IUnknown *))v57->lpVtbl->Release)(v57);
      ((void (__fastcall *)(struct IUnknown *))v13->lpVtbl->Release)(v13);
    }
    v16 = (const OLECHAR *)((char *)this + 572);
    v17 = (struct IUnknown **)((char *)this + 2152);
    v18 = IASFileExists((const WCHAR *)this + 286);
    v19 = *((_QWORD *)this + 269);
    if ( v18 )
    {
      if ( v19 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
        *v17 = 0;
      }
      XML = DataStoreServer::Load(v19, (char *)this + 572, (char *)this + 2152);
      if ( XML < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          WppDbgPrint("Load() failed:%!hresult! for SetTemplates");
          WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids);
        }
        goto LABEL_124;
      }
    }
    else if ( !v19 )
    {
      XML = DataStoreServer::LoadXML(0, *((_QWORD *)this + 275), (char *)this + 2152);
      if ( XML < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          WppDbgPrint("DataStoreServer::SetTemplates() failed to load xml text to IAS Dom ");
          WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids, "NPSDS");
        }
        goto LABEL_124;
      }
    }
    v20 = *v17;
    if ( !*v17 )
    {
      v52 = v56;
      if ( v56 )
      {
        v53 = SysAllocString((const OLECHAR *)this + 286);
        if ( !v53 && this != (DataStoreServer *)-572LL )
          _com_issue_error(-2147024882);
        pvarg.vt = 8;
        pvarg.llVal = (LONGLONG)v53;
        v62 = pvarg;
        v54 = ((__int64 (__fastcall *)(struct IUnknown *, VARIANTARG *))v52->lpVtbl[22].QueryInterface)(v52, &v62);
        XML = v54;
        if ( v54 < 0 )
          _com_issue_errorex(v54, v52, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60);
        v55 = VariantClear(&pvarg);
        if ( v55 < 0 )
          _com_issue_error(v55);
        DataStoreServer::UpdateTemplatesTimestamp(this);
        v37 = this;
        goto LABEL_166;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WppDbgPrint("Error: DataStoreServer::SetTemplates() tries to save no data to a non-existing file");
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids, "NPSDS");
      }
      XML = -2147467259;
      goto LABEL_124;
    }
    v66 = 0;
    v21 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v20->lpVtbl[15].QueryInterface)(v20, &v66);
    if ( v21 < 0 )
      _com_issue_errorex(v21, v20, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60);
    v22 = v66;
    if ( !v66 )
      _com_issue_error(-2147467261);
    _bstr_t::_bstr_t((_bstr_t *)&v57, a2);
    v23 = (struct IUnknown **)MSXML2::IXMLDOMNode::selectNodes(v22);
    v24 = *v23;
    if ( *v23 )
    {
      v25 = *v23;
      v60 = *v23;
      ((void (__fastcall *)(struct IUnknown *))v24->lpVtbl->AddRef)(v24);
    }
    else
    {
      v25 = v60;
    }
    if ( v58 )
      ((void (__fastcall *)(struct IUnknown *))v58->lpVtbl->Release)(v58);
    ((void (__fastcall *)(struct IUnknown *))v22->lpVtbl->Release)(v22);
    if ( !v25 )
      goto LABEL_115;
    LODWORD(v66) = 0;
    v26 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v25->lpVtbl[2].Release)(v25, &v66);
    if ( v26 < 0 )
      _com_issue_errorex(v26, v25, &GUID_2933bf82_7b36_11d2_b20e_00c04f983e60);
    if ( (_DWORD)v66 != 1 )
    {
LABEL_115:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WppDbgPrint("DataStoreServer::SetTemplates() error: exsiting data doesn't have the:%S node");
        WPP_SF_sS(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, v50, v51, (__int64)a2);
      }
      XML = -2147024809;
      goto LABEL_124;
    }
    v66 = 0;
    v27 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v25->lpVtbl[3].QueryInterface)(v25, &v66);
    if ( v27 < 0 )
      _com_issue_errorex(v27, v25, &GUID_2933bf82_7b36_11d2_b20e_00c04f983e60);
    v28 = v66;
    v61 = v66;
    if ( !v66 )
      _com_issue_error(-2147467261);
    v66 = 0;
    v29 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v28->lpVtbl[3].Release)(v28, &v66);
    if ( v29 < 0 )
      _com_issue_errorex(v29, v28, &GUID_2933bf80_7b36_11d2_b20e_00c04f983e60);
    v30 = v66;
    v58 = v66;
    if ( v66 )
    {
      v66 = 0;
      v31 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, struct IUnknown *, struct IUnknown **))v30->lpVtbl[6].AddRef)(
              v30,
              v6,
              v28,
              &v66);
      if ( v31 < 0 )
        _com_issue_errorex(v31, v30, &GUID_2933bf80_7b36_11d2_b20e_00c04f983e60);
      v32 = v66;
      v57 = v66;
      if ( !v66 )
      {
        XML = -2147467259;
        ((void (__fastcall *)(struct IUnknown *))v30->lpVtbl->Release)(v30);
        if ( v28 )
          ((void (__fastcall *)(struct IUnknown *))v28->lpVtbl->Release)(v28);
        goto LABEL_124;
      }
      v33 = *v17;
      v66 = v33;
      if ( !v33 )
        _com_issue_error(-2147467261);
      v34 = SysAllocString(v16);
      if ( !v34 && v16 )
        _com_issue_error(-2147024882);
      pvarg.vt = 8;
      pvarg.llVal = (LONGLONG)v34;
      v62 = pvarg;
      v35 = ((__int64 (__fastcall *)(struct IUnknown *, VARIANTARG *))v33->lpVtbl[22].QueryInterface)(v33, &v62);
      XML = v35;
      if ( v35 < 0 )
        _com_issue_errorex(v35, v66, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60);
      v36 = VariantClear(&pvarg);
      if ( v36 < 0 )
        _com_issue_error(v36);
      v37 = this;
      DataStoreServer::UpdateTemplatesTimestamp(this);
      if ( v32 )
        ((void (__fastcall *)(struct IUnknown *))v32->lpVtbl->Release)(v32);
    }
    else
    {
      v38 = *v17;
      if ( !*v17 )
        _com_issue_error(-2147467261);
      v39 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD))v38->lpVtbl[21].QueryInterface)(*v17, 0);
      if ( v39 < 0 )
        _com_issue_errorex(v39, v38, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60);
      v41 = *v17;
      if ( a3 )
      {
        if ( !v41 )
          _com_issue_error(-2147467261);
        v42 = _bstr_t::_bstr_t((_bstr_t *)&v57, a3);
        v64 = v42;
        LOWORD(v66) = 0;
        if ( *(_QWORD *)v42 )
          v43 = **(_QWORD **)v42;
        else
          v43 = 0;
        v44 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, struct IUnknown **))v41->lpVtbl[21].Release)(
                v41,
                v43,
                &v66);
        if ( v44 < 0 )
          _com_issue_errorex(v44, v41, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60);
        v45 = (__int16)v66;
        _bstr_t::~_bstr_t(v42);
        if ( v45 != -1 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            WppDbgPrint("DataStoreServer::SetTemplates(), failed to loadXML for a root replacement");
            WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids, "NPSDS");
          }
          XML = -2147467259;
          if ( v28 )
            ((void (__fastcall *)(struct IUnknown *))v28->lpVtbl->Release)(v28);
          goto LABEL_124;
        }
      }
      else
      {
        if ( v41 )
        {
          ((void (__fastcall *)(struct IUnknown *))v41->lpVtbl->Release)(*v17);
          *v17 = 0;
        }
        XML = DataStoreServer::Load(v40, v16, v17);
        if ( XML < 0 || !*v17 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            WppDbgPrint("Load failed:%!hresult! in SetTemplates()");
            WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids);
          }
          if ( v28 )
            ((void (__fastcall *)(struct IUnknown *))v28->lpVtbl->Release)(v28);
          v37 = this;
LABEL_111:
          if ( XML < 0 )
          {
LABEL_125:
            if ( *v17 )
            {
              ((void (__fastcall *)(struct IUnknown *))(*v17)->lpVtbl->Release)(*v17);
              *v17 = 0;
            }
            goto LABEL_166;
          }
          goto LABEL_166;
        }
      }
      v46 = *v17;
      if ( !*v17 )
        _com_issue_error(-2147467261);
      v47 = SysAllocString(v16);
      if ( !v47 && v16 )
        _com_issue_error(-2147024882);
      pvarg.vt = 8;
      pvarg.llVal = (LONGLONG)v47;
      v62 = pvarg;
      v48 = ((__int64 (__fastcall *)(struct IUnknown *, VARIANTARG *))v46->lpVtbl[22].QueryInterface)(v46, &v62);
      XML = v48;
      if ( v48 < 0 )
        _com_issue_errorex(v48, v46, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60);
      v49 = VariantClear(&pvarg);
      if ( v49 < 0 )
        _com_issue_error(v49);
      v37 = this;
      DataStoreServer::UpdateTemplatesTimestamp(this);
    }
    if ( v30 )
      ((void (__fastcall *)(struct IUnknown *))v30->lpVtbl->Release)(v30);
    if ( v28 )
      ((void (__fastcall *)(struct IUnknown *))v28->lpVtbl->Release)(v28);
    goto LABEL_111;
  }
  catch ( ... )
  {
    IASTraceExcept();
  }
LABEL_166:
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v37 + 272) + 24LL))(*((_QWORD *)v37 + 272));
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v37 + 8));
  if ( v56 )
    ((void (__fastcall *)(struct IUnknown *))v56->lpVtbl->Release)(v56);
  if ( v60 )
    ((void (__fastcall *)(struct IUnknown *))v60->lpVtbl->Release)(v60);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  return (unsigned int)XML;
}

```

## disassembly

```asm
0x18000b210  mov     rax, rsp
0x18000b213  mov     [rax+10h], rbx
0x18000b217  mov     [rax+18h], rsi
0x18000b21b  mov     [rax+8], rcx
0x18000b21f  push    rdi
0x18000b220  push    r12
0x18000b222  push    r13
0x18000b224  push    r14
0x18000b226  push    r15
0x18000b228  sub     rsp, 0A0h
0x18000b22f  mov     r12, r8
0x18000b232  mov     r14, rdx
0x18000b235  mov     r15, rcx
0x18000b238  xor     r13d, r13d
0x18000b23b  mov     ebx, r13d
0x18000b23e  mov     [rax-38h], rbx
0x18000b242  mov     [rax-68h], r13
0x18000b246  mov     ecx, r13d
0x18000b249  mov     [rsp+0C8h+var_98], rcx
0x18000b24e  cmp     [r15+30h], r13b
0x18000b252  jnz     loc_18000B2DE
0x18000b258  lea     rax, WPP_GLOBAL_Control
0x18000b25f  mov     rdx, cs:WPP_GLOBAL_Control
0x18000b266  cmp     rdx, rax
0x18000b269  jz      short loc_18000B2AA
0x18000b26b  cmp     byte ptr [rdx+19h], 2
0x18000b26f  jb      short loc_18000B2AA
0x18000b271  test    byte ptr [rdx+1Ch], 10h
0x18000b275  jz      short loc_18000B2AA
0x18000b277  lea     rcx, aDatastoreserve_6; "DataStoreServer() is not initialized"
0x18000b27e  call    WppDbgPrint
0x18000b283  lea     edx, [r13+2Dh]
0x18000b287  lea     r9, aNpsds; "NPSDS"
0x18000b28e  lea     r8, WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids
0x18000b295  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b29c  mov     rcx, [rcx+10h]
0x18000b2a0  call    WPP_SF_s
0x18000b2a5  mov     rcx, [rsp+0C8h+var_98]
0x18000b2aa  test    rcx, rcx
0x18000b2ad  jz      short loc_18000B2BC
0x18000b2af  mov     rax, [rcx]
0x18000b2b2  mov     rax, [rax+10h]
0x18000b2b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2bb  nop
0x18000b2bc  mov     eax, 80004005h
0x18000b2c1  lea     r11, [rsp+0C8h+var_28]
0x18000b2c9  mov     rbx, [r11+38h]
0x18000b2cd  mov     rsi, [r11+40h]
0x18000b2d1  mov     rsp, r11
0x18000b2d4  pop     r15
0x18000b2d6  pop     r14
0x18000b2d8  pop     r13
0x18000b2da  pop     r12
0x18000b2dc  pop     rdi
0x18000b2dd  retn
0x18000b2de  test    r14, r14
0x18000b2e1  jnz     short loc_18000B351
0x18000b2e3  lea     rax, WPP_GLOBAL_Control
0x18000b2ea  mov     rdx, cs:WPP_GLOBAL_Control
0x18000b2f1  cmp     rdx, rax
0x18000b2f4  jz      short loc_18000B335
0x18000b2f6  cmp     byte ptr [rdx+19h], 2
0x18000b2fa  jb      short loc_18000B335
0x18000b2fc  test    byte ptr [rdx+1Ch], 10h
0x18000b300  jz      short loc_18000B335
0x18000b302  lea     rcx, aInvalidDataFor; "Invalid data for DataStoreServer::SetTe"...
0x18000b309  call    WppDbgPrint
0x18000b30e  lea     edx, [r14+2Eh]
0x18000b312  lea     r9, aNpsds; "NPSDS"
0x18000b319  lea     r8, WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids
0x18000b320  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b327  mov     rcx, [rcx+10h]
0x18000b32b  call    WPP_SF_s
0x18000b330  mov     rcx, [rsp+0C8h+var_98]
0x18000b335  test    rcx, rcx
0x18000b338  jz      short loc_18000B347
0x18000b33a  mov     rax, [rcx]
0x18000b33d  mov     rax, [rax+10h]
0x18000b341  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b346  nop
0x18000b347  mov     eax, 80070057h
0x18000b34c  jmp     loc_18000B2C1
0x18000b351  lea     rsi, [r15+8]
0x18000b355  mov     edi, r13d
0x18000b358  jmp     short loc_18000B367
0x18000b35a  inc     edi
0x18000b35c  cmp     edi, 64h ; 'd'
0x18000b35f  jge     short loc_18000B376
0x18000b361  call    cs:__imp_SwitchToThread
0x18000b367  mov     rcx, rsi; lpCriticalSection
0x18000b36a  call    cs:__imp_TryEnterCriticalSection
0x18000b370  test    eax, eax
0x18000b372  jz      short loc_18000B35A
0x18000b374  jmp     short loc_18000B37F
0x18000b376  mov     rcx, rsi; lpCriticalSection
0x18000b379  call    cs:__imp_EnterCriticalSection
0x18000b37f  mov     rcx, [r15+880h]
0x18000b386  mov     rax, [rcx]
0x18000b389  mov     rax, [rax+10h]
0x18000b38d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b392  nop
0x18000b393  test    r12, r12
0x18000b396  jz      loc_18000B46C
0x18000b39c  lea     r8, [rsp+0C8h+var_98]
0x18000b3a1  mov     rdx, r12
0x18000b3a4  call    ?LoadXML@DataStoreServer@@AEAAJPEBGAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z; DataStoreServer::LoadXML(ushort const *,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &)
0x18000b3a9  mov     edi, eax
0x18000b3ab  test    eax, eax
0x18000b3ad  js      loc_18000B518
0x18000b3b3  mov     rdi, [rsp+0C8h+var_98]
0x18000b3b8  test    rdi, rdi
0x18000b3bb  jz      loc_18000BCAD
0x18000b3c1  mov     [rsp+0C8h+arg_18], r13
0x18000b3c9  mov     rax, [rdi]
0x18000b3cc  lea     rdx, [rsp+0C8h+arg_18]
0x18000b3d4  mov     rcx, rdi
0x18000b3d7  mov     rax, [rax+168h]
0x18000b3de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3e3  test    eax, eax
0x18000b3e5  js      loc_18000BCB7
0x18000b3eb  mov     rdi, [rsp+0C8h+arg_18]
0x18000b3f3  mov     [rsp+0C8h+arg_18], rdi
0x18000b3fb  test    rdi, rdi
0x18000b3fe  jz      loc_18000BCC9
0x18000b404  lea     rdx, asc_180014B8C; "."
0x18000b40b  lea     rcx, [rsp+0C8h+var_88]; this
0x18000b410  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000b415  mov     r8, rax
0x18000b418  lea     rdx, [rsp+0C8h+var_90]
0x18000b41d  mov     rcx, rdi; struct IUnknown *
0x18000b420  call    ?selectSingleNode@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectSingleNode(_bstr_t)
0x18000b425  mov     rcx, [rax]
0x18000b428  test    rcx, rcx
0x18000b42b  jz      short loc_18000B445
0x18000b42d  mov     rbx, rcx
0x18000b430  mov     [rsp+0C8h+var_38], rcx
0x18000b438  mov     rax, [rcx]
0x18000b43b  mov     rax, [rax+8]
0x18000b43f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b444  nop
0x18000b445  mov     rcx, [rsp+0C8h+var_90]
0x18000b44a  test    rcx, rcx
0x18000b44d  jz      short loc_18000B45C
0x18000b44f  mov     rax, [rcx]
0x18000b452  mov     rax, [rax+10h]
0x18000b456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b45b  nop
0x18000b45c  mov     rax, [rdi]
0x18000b45f  mov     rcx, rdi
0x18000b462  mov     rax, [rax+10h]
0x18000b466  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b46b  nop
0x18000b46c  lea     r13, [r15+23Ch]
0x18000b473  lea     rsi, [r15+868h]
0x18000b47a  mov     rcx, r13
0x18000b47d  call    IASFileExists
0x18000b482  mov     rcx, [rsi]
0x18000b485  test    al, al
0x18000b487  jz      loc_18000B524
0x18000b48d  test    rcx, rcx
0x18000b490  jz      short loc_18000B4A5
0x18000b492  mov     rax, [rcx]
0x18000b495  mov     rax, [rax+10h]
0x18000b499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b49e  mov     qword ptr [rsi], 0
0x18000b4a5  mov     r8, rsi
0x18000b4a8  mov     rdx, r13
0x18000b4ab  call    ?Load@DataStoreServer@@AEAAJPEBGAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z; DataStoreServer::Load(ushort const *,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &)
0x18000b4b0  mov     edi, eax
0x18000b4b2  test    eax, eax
0x18000b4b4  jns     loc_18000B59D
0x18000b4ba  lea     rax, WPP_GLOBAL_Control
0x18000b4c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b4c8  cmp     rcx, rax
0x18000b4cb  jz      loc_18000BB96
0x18000b4d1  cmp     byte ptr [rcx+19h], 2
0x18000b4d5  jb      loc_18000BB96
0x18000b4db  test    byte ptr [rcx+1Ch], 10h
0x18000b4df  jz      loc_18000BB96
0x18000b4e5  mov     edx, edi
0x18000b4e7  lea     rcx, aLoadFailedHres_3; "Load() failed:%!hresult! for SetTemplat"...
0x18000b4ee  call    WppDbgPrint
0x18000b4f3  mov     edx, 2Fh ; '/'
0x18000b4f8  mov     dword ptr [rsp+0C8h+var_A8], edi
0x18000b4fc  lea     r8, WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids
0x18000b503  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b50a  mov     rcx, [rcx+10h]
0x18000b50e  call    WPP_SF_sd
0x18000b513  jmp     loc_18000BB96
0x18000b518  lea     rsi, [r15+868h]
0x18000b51f  jmp     loc_18000BB96
0x18000b524  test    rcx, rcx
0x18000b527  jnz     short loc_18000B59D
0x18000b529  mov     r8, rsi
0x18000b52c  mov     rdx, [r15+898h]
0x18000b533  call    ?LoadXML@DataStoreServer@@AEAAJPEBGAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z; DataStoreServer::LoadXML(ushort const *,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &)
0x18000b538  mov     edi, eax
0x18000b53a  test    eax, eax
0x18000b53c  jns     short loc_18000B59D
0x18000b53e  lea     rax, WPP_GLOBAL_Control
0x18000b545  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b54c  cmp     rcx, rax
0x18000b54f  jz      loc_18000BB96
0x18000b555  cmp     byte ptr [rcx+19h], 2
0x18000b559  jb      loc_18000BB96
0x18000b55f  test    byte ptr [rcx+1Ch], 10h
0x18000b563  jz      loc_18000BB96
0x18000b569  lea     rcx, aDatastoreserve_1; "DataStoreServer::SetTemplates() failed "...
0x18000b570  call    WppDbgPrint
0x18000b575  mov     edx, 30h ; '0'
0x18000b57a  lea     r9, aNpsds; "NPSDS"
0x18000b581  lea     r8, WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids
0x18000b588  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b58f  mov     rcx, [rcx+10h]
0x18000b593  call    WPP_SF_s
0x18000b598  jmp     loc_18000BB96
0x18000b59d  mov     rdi, [rsi]
0x18000b5a0  test    rdi, rdi
0x18000b5a3  jz      loc_18000BB3A
0x18000b5a9  mov     [rsp+0C8h+arg_18], 0
0x18000b5b5  mov     rax, [rdi]
0x18000b5b8  lea     rdx, [rsp+0C8h+arg_18]
0x18000b5c0  mov     rcx, rdi
0x18000b5c3  mov     rax, [rax+168h]
0x18000b5ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5cf  test    eax, eax
0x18000b5d1  js      loc_18000BCD4
0x18000b5d7  mov     rdi, [rsp+0C8h+arg_18]
0x18000b5df  mov     [rsp+0C8h+arg_18], rdi
0x18000b5e7  test    rdi, rdi
0x18000b5ea  jz      loc_18000BCE6
0x18000b5f0  mov     rdx, r14; unsigned __int16 *
0x18000b5f3  lea     rcx, [rsp+0C8h+var_90]; this
0x18000b5f8  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000b5fd  mov     r8, rax
0x18000b600  lea     rdx, [rsp+0C8h+var_88]
0x18000b605  mov     rcx, rdi; struct IUnknown *
0x18000b608  call    ?selectNodes@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNodeList@MSXML2@@$1?_GUID_2933bf82_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectNodes(_bstr_t)
0x18000b60d  mov     rcx, [rax]
0x18000b610  test    rcx, rcx
0x18000b613  jz      short loc_18000B62C
0x18000b615  mov     r15, rcx
0x18000b618  mov     [rsp+0C8h+var_68], rcx
0x18000b61d  mov     rax, [rcx]
0x18000b620  mov     rax, [rax+8]
0x18000b624  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b629  nop
0x18000b62a  jmp     short loc_18000B631
0x18000b62c  mov     r15, [rsp+0C8h+var_68]
0x18000b631  mov     rcx, [rsp+0C8h+var_88]
0x18000b636  test    rcx, rcx
0x18000b639  jz      short loc_18000B648
0x18000b63b  mov     rax, [rcx]
0x18000b63e  mov     rax, [rax+10h]
0x18000b642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b647  nop
0x18000b648  mov     rax, [rdi]
0x18000b64b  mov     rcx, rdi
0x18000b64e  mov     rax, [rax+10h]
0x18000b652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b657  nop
0x18000b658  xor     edi, edi
0x18000b65a  test    r15, r15
0x18000b65d  jz      loc_18000BAEB
0x18000b663  mov     dword ptr [rsp+0C8h+arg_18], edi
0x18000b66a  mov     rax, [r15]
0x18000b66d  lea     rdx, [rsp+0C8h+arg_18]
0x18000b675  mov     rcx, r15
0x18000b678  mov     rax, [rax+40h]
0x18000b67c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b681  test    eax, eax
0x18000b683  js      loc_18000BCF1
0x18000b689  cmp     dword ptr [rsp+0C8h+arg_18], 1
0x18000b691  jnz     loc_18000BAEB
0x18000b697  mov     [rsp+0C8h+arg_18], rdi
0x18000b69f  mov     rax, [r15]
0x18000b6a2  lea     rdx, [rsp+0C8h+arg_18]
0x18000b6aa  mov     rcx, r15
0x18000b6ad  mov     rax, [rax+48h]
0x18000b6b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6b6  test    eax, eax
0x18000b6b8  js      loc_18000BD02
0x18000b6be  mov     r14, [rsp+0C8h+arg_18]
0x18000b6c6  mov     [rsp+0C8h+var_60], r14
0x18000b6cb  test    r14, r14
0x18000b6ce  jz      loc_18000BD14
0x18000b6d4  mov     [rsp+0C8h+arg_18], rdi
0x18000b6dc  mov     rax, [r14]
0x18000b6df  lea     rdx, [rsp+0C8h+arg_18]
0x18000b6e7  mov     rcx, r14
0x18000b6ea  mov     rax, [rax+58h]
0x18000b6ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6f3  test    eax, eax
0x18000b6f5  js      loc_18000BD1E
0x18000b6fb  mov     r15, [rsp+0C8h+arg_18]
0x18000b703  mov     [rsp+0C8h+var_88], r15
0x18000b708  test    r15, r15
0x18000b70b  jz      loc_18000B835
0x18000b711  mov     [rsp+0C8h+arg_18], rdi
0x18000b719  mov     rax, [r15]
  ... truncated ...
```
