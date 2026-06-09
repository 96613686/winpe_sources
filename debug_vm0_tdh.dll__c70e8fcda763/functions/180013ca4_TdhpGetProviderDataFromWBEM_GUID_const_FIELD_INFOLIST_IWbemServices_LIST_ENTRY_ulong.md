# TdhpGetProviderDataFromWBEM(_GUID const *,FIELD_INFOLIST *,IWbemServices *,_LIST_ENTRY *,ulong *)

- ea: `0x180013ca4`
- end: `0x180014433`
- name: `?TdhpGetProviderDataFromWBEM@@YAKPEBU_GUID@@PEAUFIELD_INFOLIST@@PEAUIWbemServices@@PEAU_LIST_ENTRY@@PEAK@Z`
- size: `1935`
- prototype: `__int64 __fastcall(const struct _GUID *, struct FIELD_INFOLIST *, struct IWbemServices *, struct _LIST_ENTRY *, unsigned int *)`
- caller_count: `3`
- callee_count: `13`
- tags: `registry_config, service_task`

## callers

- `0x1800245f4`
- `0x18002ac2c`
- `0x18002b380`

## callees

- `0x180012fd0`
- `0x180013ca4`
- `0x180014fd8`
- `0x1800159ac`
- `0x180016660`
- `0x180017d74`
- `0x18001c7d0`
- `0x18001d1d0`
- `0x18001ea64`
- `0x18001eb98`
- `0x18001f990`
- `0x1800207c0`
- `0x18004c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800141c1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800141c1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800140fc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014127`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800140fc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014127`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001426d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014285`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001426d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014285`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800140ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014116`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001425f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014277`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800140ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014116`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001425f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014277`
- `OLEAUT32!__imp_SysAllocString` at `0x180013d59`
- `OLEAUT32!__imp_SysAllocString` at `0x180013d59`
- `OLEAUT32!__imp_SysFreeString` at `0x180014294`
- `OLEAUT32!__imp_SysFreeString` at `0x180014294`
- `OLEAUT32!__imp_SysStringLen` at `0x1800140da`
- `OLEAUT32!__imp_SysStringLen` at `0x1800140da`
- `OLEAUT32!__imp_VariantClear` at `0x1800141dc`
- `OLEAUT32!__imp_VariantClear` at `0x1800141dc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TdhpGetProviderDataFromWBEM(
        const struct _GUID *a1,
        struct FIELD_INFOLIST *a2,
        struct IWbemServices *a3,
        struct _LIST_ENTRY *a4,
        unsigned int *a5)
{
  __int64 *v6; // r15
  GUID *v9; // rdi
  unsigned int v10; // r14d
  OLECHAR *v11; // r12
  unsigned int v12; // esi
  HRESULT (__stdcall *CreateClassEnum)(IWbemServices *, const BSTR, int, IWbemContext *, IEnumWbemClassObject **); // r14
  int v14; // ebx
  __int64 v15; // rcx
  __int64 v16; // rax
  int v17; // ebx
  wchar_t *v18; // rcx
  __int64 v19; // rax
  int v20; // ebx
  wchar_t *v21; // rcx
  __int64 v22; // rcx
  BSTR bstrVal; // r8
  __int64 v24; // rdx
  wchar_t *v25; // rax
  wchar_t v26; // r9
  wchar_t *v27; // rcx
  __int64 *v28; // rdi
  void (__fastcall *v29)(__int64 *, __int64); // rbx
  __int64 v30; // rax
  wchar_t *v31; // rdi
  __int64 (__fastcall *v32)(wchar_t *, const wchar_t *, _QWORD, BSTR *, _QWORD); // rbx
  int v33; // eax
  wchar_t *v34; // rdi
  __int64 (__fastcall *v35)(wchar_t *, const wchar_t *, _QWORD, BSTR *, _QWORD); // rbx
  int v36; // eax
  __int64 *v37; // rdi
  int (__fastcall *v38)(__int64 *, const wchar_t *, _QWORD, BSTR *, _QWORD, _QWORD); // rbx
  UINT v39; // ebx
  HANDLE ProcessHeap; // rax
  unsigned int v41; // r14d
  HANDLE v42; // rax
  wchar_t *v43; // rax
  struct _LIST_ENTRY *v44; // r15
  struct _LIST_ENTRY *Blink; // rax
  void *v46; // rbx
  HANDLE v47; // rax
  HANDLE v48; // rax
  __int64 *v49; // rdi
  __int64 (__fastcall *v50)(__int64 *, const wchar_t *, __int64); // rbx
  __int64 v51; // rax
  __int64 *v52; // rdi
  __int64 (__fastcall *v53)(__int64 *, const wchar_t *, __int64); // rbx
  __int64 v54; // rax
  unsigned int v55; // [rsp+40h] [rbp-C0h]
  wchar_t *v56; // [rsp+48h] [rbp-B8h] BYREF
  __int64 *v57; // [rsp+50h] [rbp-B0h] BYREF
  int v58; // [rsp+58h] [rbp-A8h] BYREF
  BSTR pbstr[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v60; // [rsp+70h] [rbp-90h]
  VARIANTARG pvarg; // [rsp+78h] [rbp-88h] BYREF
  __int64 *v62; // [rsp+90h] [rbp-70h] BYREF
  wchar_t *v63; // [rsp+98h] [rbp-68h] BYREF
  wchar_t **v64; // [rsp+A0h] [rbp-60h]
  OLECHAR *v65; // [rsp+B0h] [rbp-50h] BYREF
  struct _LIST_ENTRY *v66; // [rsp+B8h] [rbp-48h]
  struct FIELD_INFOLIST *v67; // [rsp+C0h] [rbp-40h]
  unsigned int *v68; // [rsp+C8h] [rbp-38h]
  wchar_t v69[128]; // [rsp+D0h] [rbp-30h] BYREF
  __int16 v70; // [rsp+1D0h] [rbp+D0h] BYREF
  char v71[72]; // [rsp+1D2h] [rbp+D2h] BYREF
  int v72; // [rsp+21Ah] [rbp+11Ah]
  wchar_t v73[128]; // [rsp+2D0h] [rbp+1D0h] BYREF

  v66 = a4;
  v6 = (__int64 *)a2;
  v67 = a2;
  v68 = a5;
  v62 = 0;
  v58 = 0;
  v65 = 0;
  if ( !a3 )
  {
    utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::~unique_ptr<wchar_t [0],tlx::sysfreestring_delete>(&v65);
    std::unique_ptr<IUnknown,XmlReader::ReleaseDelete>::~unique_ptr<IUnknown,XmlReader::ReleaseDelete>(&v62);
    return 87;
  }
  if ( a1 )
  {
    v70 = 123;
    tlx::guid_to_string_upper<unsigned short>(v71, a1);
    v72 = 125;
  }
  v9 = 0;
  v10 = 0;
  v55 = 0;
  v11 = SysAllocString(L"EventTrace");
  v65 = v11;
  if ( !v11 )
  {
    v12 = 8;
    goto LABEL_60;
  }
  v12 = 1168;
  CreateClassEnum = a3->lpVtbl->CreateClassEnum;
  pbstr[0] = 0;
  pbstr[1] = (BSTR)&v62;
  v62 = 0;
  v14 = ((__int64 (__fastcall *)(struct IWbemServices *, OLECHAR *, __int64, _QWORD, BSTR *))CreateClassEnum)(
          a3,
          v11,
          131073,
          0,
          pbstr);
  if ( pbstr[0] )
  {
    v15 = *(_QWORD *)pbstr[1];
    *(_QWORD *)pbstr[1] = pbstr[0];
    if ( v15 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  if ( v14 < 0 )
    goto LABEL_59;
  v58 = 1;
  while ( 1 )
  {
    v57 = 0;
    v16 = *v62;
    v63 = 0;
    v64 = (wchar_t **)&v57;
    v57 = 0;
    v17 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, wchar_t **, int *))(v16 + 32))(
            v62,
            0xFFFFFFFFLL,
            1,
            &v63,
            &v58);
    if ( v63 )
    {
      v18 = *v64;
      *v64 = v63;
      if ( v18 )
        (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v18 + 16LL))(v18);
    }
    if ( v17 < 0 )
    {
      if ( v57 )
        (*(void (__fastcall **)(__int64 *))(*v57 + 16))(v57);
      goto LABEL_58;
    }
    if ( !v58 )
      goto LABEL_80;
    if ( v58 != 1 )
      goto LABEL_57;
    v56 = 0;
    v19 = *v57;
    v63 = 0;
    v64 = &v56;
    v56 = 0;
    v20 = (*(__int64 (__fastcall **)(__int64 *, wchar_t **))(v19 + 24))(v57, &v63);
    if ( v63 )
    {
      v21 = *v64;
      *v64 = v63;
      if ( v21 )
        (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v21 + 16LL))(v21);
    }
    if ( v20 < 0 )
      goto LABEL_56;
    memset(&pvarg, 0, sizeof(pvarg));
    if ( (*(int (__fastcall **)(wchar_t *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD))(*(_QWORD *)v56 + 24LL))(
           v56,
           L"Guid",
           0,
           &pvarg,
           0) < 0 )
      goto LABEL_55;
    v22 = 2147483646;
    bstrVal = pvarg.bstrVal;
    v24 = 128;
    v25 = v69;
    do
    {
      if ( !v22 )
        break;
      v26 = *bstrVal;
      if ( !*bstrVal )
        break;
      ++bstrVal;
      *v25++ = v26;
      --v22;
      --v24;
    }
    while ( v24 );
    v27 = v25 - 1;
    if ( v24 )
      v27 = v25;
    *v27 = 0;
    if ( !v24
      || v69[0] != 123
      && ((int)StringCchCopyW(v73, 0x80u, v69) < 0 || (int)StringCchPrintfW(v69, 0x80u, L"{%ws}", v73) < 0) )
    {
      goto LABEL_55;
    }
    if ( a1 || v6 )
      break;
    v28 = v57;
    v29 = *(void (__fastcall **)(__int64 *, __int64))(*v57 + 24);
    v30 = utl::out_ptr<void,utl::unique_ptr<IWbemQualifierSet,tlx::release_delete>,>(&v63, &v56);
    v29(v28, v30);
    utl::out_ptr_t<utl::unique_ptr<IWbemQualifierSet,tlx::release_delete>,IWbemQualifierSet *,>::~out_ptr_t<utl::unique_ptr<IWbemQualifierSet,tlx::release_delete>,IWbemQualifierSet *,>(&v63);
    *(_OWORD *)pbstr = 0;
    v60 = 0;
    v31 = v56;
    v32 = *(__int64 (__fastcall **)(wchar_t *, const wchar_t *, _QWORD, BSTR *, _QWORD))(*(_QWORD *)v56 + 24LL);
    tlx::unique_variant::reset((tlx::unique_variant *)pbstr);
    v33 = v32(v31, L"DisplayName", 0, pbstr, 0);
    if ( v33 < 0 )
    {
      if ( v33 != -2147217406 )
        goto LABEL_72;
      v34 = v56;
      v35 = *(__int64 (__fastcall **)(wchar_t *, const wchar_t *, _QWORD, BSTR *, _QWORD))(*(_QWORD *)v56 + 24LL);
      tlx::unique_variant::reset((tlx::unique_variant *)pbstr);
      v36 = v35(v34, L"Description", 0, pbstr, 0);
      if ( v36 < 0 )
      {
        if ( v36 != -2147217406 )
          goto LABEL_72;
        v37 = v57;
        v38 = *(int (__fastcall **)(__int64 *, const wchar_t *, _QWORD, BSTR *, _QWORD, _QWORD))(*v57 + 32);
        tlx::unique_variant::reset((tlx::unique_variant *)pbstr);
        if ( v38(v37, L"__CLASS", 0, pbstr, 0, 0) < 0 )
          goto LABEL_72;
      }
    }
    v39 = SysStringLen(pbstr[1]);
    if ( !v39 )
    {
LABEL_72:
      tlx::unique_variant::reset((tlx::unique_variant *)pbstr);
      goto LABEL_55;
    }
    ProcessHeap = GetProcessHeap();
    v9 = (GUID *)HeapAlloc(ProcessHeap, 8u, 0x30u);
    if ( !v9
      || (v41 = 2 * (v39 + 1),
          v42 = GetProcessHeap(),
          v43 = (wchar_t *)HeapAlloc(v42, 8u, v41),
          (*(_QWORD *)&v9[2].Data1 = v43) == 0)
      || (int)StringCchCopyW(v43, v39 + 1, pbstr[1]) < 0 )
    {
      tlx::unique_variant::reset((tlx::unique_variant *)pbstr);
      tlx::unique_variant::reset((tlx::unique_variant *)&pvarg);
      std::unique_ptr<IUnknown,XmlReader::ReleaseDelete>::~unique_ptr<IUnknown,XmlReader::ReleaseDelete>(&v56);
      std::unique_ptr<IUnknown,XmlReader::ReleaseDelete>::~unique_ptr<IUnknown,XmlReader::ReleaseDelete>(&v57);
      goto LABEL_59;
    }
    *(_DWORD *)v9[2].Data4 = v41;
    if ( !tlx::string_to_guid<wchar_t [128]>(&v9[1], v69) )
      v9[1] = g_NullGuid;
    *(_DWORD *)&v9[2].Data4[4] = 1;
    v44 = v66;
    Blink = v66->Blink;
    if ( Blink->Flink != v66 )
      __fastfail(3u);
    *(_QWORD *)&v9->Data1 = v66;
    *(_QWORD *)v9->Data4 = Blink;
    Blink->Flink = (struct _LIST_ENTRY *)v9;
    v44->Blink = (struct _LIST_ENTRY *)v9;
    ++v55;
    tlx::unique_variant::reset((tlx::unique_variant *)pbstr);
    v6 = (__int64 *)v67;
LABEL_48:
    if ( pvarg.vt )
      VariantClear(&pvarg);
    if ( v56 )
      (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v56 + 16LL))(v56);
    if ( v57 )
      (*(void (__fastcall **)(__int64 *))(*v57 + 16))(v57);
  }
  if ( (unsigned int)_o__wcsicmp(&v70, v69) )
    goto LABEL_48;
  v49 = v57;
  v50 = *(__int64 (__fastcall **)(__int64 *, const wchar_t *, __int64))(*v57 + 88);
  v51 = utl::out_ptr<void,utl::unique_ptr<IWbemQualifierSet,tlx::release_delete>,>(&v63, &v56);
  LODWORD(v50) = v50(v49, L"Flags", v51);
  utl::out_ptr_t<utl::unique_ptr<IWbemQualifierSet,tlx::release_delete>,IWbemQualifierSet *,>::~out_ptr_t<utl::unique_ptr<IWbemQualifierSet,tlx::release_delete>,IWbemQualifierSet *,>(&v63);
  if ( (int)v50 < 0
    || (v12 = TdhpFillProviderFlagsFromWBEM(v56, v6)) != 0
    || (v52 = v57,
        v53 = *(__int64 (__fastcall **)(__int64 *, const wchar_t *, __int64))(*v57 + 88),
        v54 = utl::out_ptr<void,utl::unique_ptr<IWbemQualifierSet,tlx::release_delete>,>(&v63, &v56),
        LODWORD(v53) = v53(v52, L"Level", v54),
        utl::out_ptr_t<utl::unique_ptr<IWbemQualifierSet,tlx::release_delete>,IWbemQualifierSet *,>::~out_ptr_t<utl::unique_ptr<IWbemQualifierSet,tlx::release_delete>,IWbemQualifierSet *,>(&v63),
        (int)v53 < 0)
    || (v12 = TdhpFillProviderFlagsFromWBEM(v56, v6 + 2)) != 0 )
  {
LABEL_55:
    tlx::unique_variant::reset((tlx::unique_variant *)&pvarg);
LABEL_56:
    std::unique_ptr<IUnknown,XmlReader::ReleaseDelete>::~unique_ptr<IUnknown,XmlReader::ReleaseDelete>(&v56);
LABEL_57:
    std::unique_ptr<IUnknown,XmlReader::ReleaseDelete>::~unique_ptr<IUnknown,XmlReader::ReleaseDelete>(&v57);
LABEL_58:
    v9 = 0;
    goto LABEL_59;
  }
  tlx::unique_variant::reset((tlx::unique_variant *)&pvarg);
  std::unique_ptr<IUnknown,XmlReader::ReleaseDelete>::~unique_ptr<IUnknown,XmlReader::ReleaseDelete>(&v56);
LABEL_80:
  std::unique_ptr<IUnknown,XmlReader::ReleaseDelete>::~unique_ptr<IUnknown,XmlReader::ReleaseDelete>(&v57);
  v9 = 0;
  if ( !a1 )
  {
    v12 = 0;
    goto LABEL_58;
  }
LABEL_59:
  v10 = v55;
LABEL_60:
  if ( v68 )
    *v68 = v10;
  if ( v12 && v9 )
  {
    v46 = *(void **)&v9[2].Data1;
    if ( v46 )
    {
      v47 = GetProcessHeap();
      HeapFree(v47, 0, v46);
      *(_QWORD *)&v9[2].Data1 = 0;
    }
    v48 = GetProcessHeap();
    HeapFree(v48, 0, v9);
  }
  if ( v11 )
    SysFreeString(v11);
  if ( v62 )
    (*(void (__fastcall **)(__int64 *))(*v62 + 16))(v62);
  return v12;
}

```

## disassembly

```asm
0x180013ca4  mov     [rsp-8+arg_0], rbx
0x180013ca9  push    rbp
0x180013caa  push    rsi
0x180013cab  push    rdi
0x180013cac  push    r12
0x180013cae  push    r13
0x180013cb0  push    r14
0x180013cb2  push    r15
0x180013cb4  lea     rbp, [rsp-2E0h]
0x180013cbc  sub     rsp, 3E0h
0x180013cc3  mov     rax, cs:__security_cookie
0x180013cca  xor     rax, rsp
0x180013ccd  mov     [rbp+310h+var_40], rax
0x180013cd4  mov     [rbp+310h+var_358], r9
0x180013cd8  mov     rbx, r8
0x180013cdb  mov     r15, rdx
0x180013cde  mov     [rbp+310h+var_350], rdx
0x180013ce2  mov     r13, rcx
0x180013ce5  mov     rax, [rbp+310h+arg_20]
0x180013cec  mov     [rbp+310h+var_348], rax
0x180013cf0  xor     esi, esi
0x180013cf2  mov     [rbp+310h+var_380], rsi
0x180013cf6  mov     [rsp+410h+var_3B8], esi
0x180013cfa  mov     [rbp+310h+var_360], rsi
0x180013cfe  test    r8, r8
0x180013d01  jnz     short loc_180013D1E
0x180013d03  lea     rcx, [rbp+310h+var_360]
0x180013d07  call    ??1?$unique_ptr@$$BY0A@_WUsysfreestring_delete@tlx@@@utl@@QEAA@XZ; utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::~unique_ptr<wchar_t [0],tlx::sysfreestring_delete>(void)
0x180013d0c  nop
0x180013d0d  lea     rcx, [rbp+310h+var_380]
0x180013d11  call    ??1?$unique_ptr@UIUnknown@@UReleaseDelete@XmlReader@@@std@@QEAA@XZ; std::unique_ptr<IUnknown,XmlReader::ReleaseDelete>::~unique_ptr<IUnknown,XmlReader::ReleaseDelete>(void)
0x180013d16  lea     eax, [rbx+57h]
0x180013d19  jmp     loc_1800142B3
0x180013d1e  mov     eax, 7Bh ; '{'
0x180013d23  test    r13, r13
0x180013d26  jz      short loc_180013D48
0x180013d28  mov     [rbp+310h+var_240], ax
0x180013d2f  mov     rdx, r13
0x180013d32  lea     rcx, [rbp+310h+var_23E]
0x180013d39  call    ??$guid_to_string_upper@G@tlx@@YAXPEAGAEBU_GUID@@_N@Z; tlx::guid_to_string_upper<ushort>(ushort *,_GUID const &,bool)
0x180013d3e  mov     [rbp+310h+var_1F6], 7Dh ; '}'
0x180013d48  mov     rdi, rsi
0x180013d4b  mov     r14d, esi
0x180013d4e  mov     [rsp+410h+var_3D0], esi
0x180013d52  lea     rcx, psz; "EventTrace"
0x180013d59  call    cs:__imp_SysAllocString
0x180013d5f  mov     r12, rax
0x180013d62  mov     [rbp+310h+var_360], rax
0x180013d66  test    rax, rax
0x180013d69  jz      loc_180014428
0x180013d6f  mov     esi, 490h
0x180013d74  mov     rcx, [rbx]
0x180013d77  mov     r14, [rcx+60h]
0x180013d7b  xor     r11d, r11d
0x180013d7e  mov     [rsp+410h+pbstr], r11
0x180013d83  lea     rax, [rbp+310h+var_380]
0x180013d87  mov     [rsp+410h+pbstr+8], rax
0x180013d8c  mov     rcx, [rbp+310h+var_380]
0x180013d90  mov     [rbp+310h+var_380], r11
0x180013d94  test    rcx, rcx
0x180013d97  jz      short loc_180013DA6
0x180013d99  mov     rax, [rcx]
0x180013d9c  mov     rax, [rax+10h]
0x180013da0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013da5  nop
0x180013da6  lea     rax, [rsp+410h+pbstr]
0x180013dab  mov     [rsp+410h+var_3F0], rax
0x180013db0  xor     r9d, r9d
0x180013db3  mov     r8d, 20001h
0x180013db9  mov     rdx, r12
0x180013dbc  mov     rcx, rbx
0x180013dbf  mov     rax, r14
0x180013dc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013dc7  mov     ebx, eax
0x180013dc9  mov     r8, [rsp+410h+pbstr]
0x180013dce  xor     r14d, r14d
0x180013dd1  test    r8, r8
0x180013dd4  jz      short loc_180013DF3
0x180013dd6  mov     rdx, [rsp+410h+pbstr+8]
0x180013ddb  mov     rcx, [rdx]
0x180013dde  mov     [rdx], r8
0x180013de1  test    rcx, rcx
0x180013de4  jz      short loc_180013DF3
0x180013de6  mov     rax, [rcx]
0x180013de9  mov     rax, [rax+10h]
0x180013ded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013df2  nop
0x180013df3  test    ebx, ebx
0x180013df5  js      loc_180014239
0x180013dfb  mov     [rsp+410h+var_3B8], 1
0x180013e03  mov     edi, 80h
0x180013e08  mov     [rsp+410h+var_3C0], r14
0x180013e0d  mov     rcx, [rbp+310h+var_380]
0x180013e11  mov     rax, [rcx]
0x180013e14  mov     [rbp+310h+var_378], r14
0x180013e18  lea     rdx, [rsp+410h+var_3C0]
0x180013e1d  mov     [rbp+310h+var_370], rdx
0x180013e21  mov     [rsp+410h+var_3C0], r14
0x180013e26  lea     rdx, [rsp+410h+var_3B8]
0x180013e2b  mov     [rsp+410h+var_3F0], rdx
0x180013e30  lea     r9, [rbp+310h+var_378]
0x180013e34  mov     r8d, 1
0x180013e3a  or      edx, 0FFFFFFFFh
0x180013e3d  mov     rax, [rax+20h]
0x180013e41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e46  mov     ebx, eax
0x180013e48  mov     r8, [rbp+310h+var_378]
0x180013e4c  test    r8, r8
0x180013e4f  jz      short loc_180013E6D
0x180013e51  mov     rdx, [rbp+310h+var_370]
0x180013e55  mov     rcx, [rdx]
0x180013e58  mov     [rdx], r8
0x180013e5b  test    rcx, rcx
0x180013e5e  jz      short loc_180013E6D
0x180013e60  mov     rax, [rcx]
0x180013e63  mov     rax, [rax+10h]
0x180013e67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e6c  nop
0x180013e6d  test    ebx, ebx
0x180013e6f  js      loc_18001440C
0x180013e75  mov     eax, [rsp+410h+var_3B8]
0x180013e79  test    eax, eax
0x180013e7b  jz      loc_1800143EE
0x180013e81  cmp     eax, 1
0x180013e84  jnz     loc_18001422C
0x180013e8a  mov     [rsp+410h+var_3C8], r14
0x180013e8f  mov     rcx, [rsp+410h+var_3C0]
0x180013e94  mov     rax, [rcx]
0x180013e97  mov     [rbp+310h+var_378], r14
0x180013e9b  lea     rdx, [rsp+410h+var_3C8]
0x180013ea0  mov     [rbp+310h+var_370], rdx
0x180013ea4  mov     [rsp+410h+var_3C8], r14
0x180013ea9  lea     rdx, [rbp+310h+var_378]
0x180013ead  mov     rax, [rax+18h]
0x180013eb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013eb6  mov     ebx, eax
0x180013eb8  mov     r8, [rbp+310h+var_378]
0x180013ebc  test    r8, r8
0x180013ebf  jz      short loc_180013EDD
0x180013ec1  mov     rdx, [rbp+310h+var_370]
0x180013ec5  mov     rcx, [rdx]
0x180013ec8  mov     [rdx], r8
0x180013ecb  test    rcx, rcx
0x180013ece  jz      short loc_180013EDD
0x180013ed0  mov     rax, [rcx]
0x180013ed3  mov     rax, [rax+10h]
0x180013ed7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013edc  nop
0x180013edd  test    ebx, ebx
0x180013edf  js      loc_180014221
0x180013ee5  xorps   xmm0, xmm0
0x180013ee8  xor     eax, eax
0x180013eea  movups  xmmword ptr [rsp+410h+pvarg], xmm0
0x180013eef  mov     qword ptr [rbp+310h+pvarg+10h], rax
0x180013ef3  mov     rcx, [rsp+410h+var_3C8]
0x180013ef8  mov     rax, [rcx]
0x180013efb  mov     [rsp+410h+var_3F0], r14
0x180013f00  lea     r9, [rsp+410h+pvarg]
0x180013f05  xor     r8d, r8d
0x180013f08  lea     rdx, aGuid; "Guid"
0x180013f0f  mov     rax, [rax+18h]
0x180013f13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f18  test    eax, eax
0x180013f1a  js      loc_180014216
0x180013f20  mov     ecx, 7FFFFFFEh
0x180013f25  mov     r8, qword ptr [rbp+310h+pvarg+8]
0x180013f29  mov     rdx, rdi
0x180013f2c  lea     rax, [rbp+310h+var_340]
0x180013f30  test    rcx, rcx
0x180013f33  jz      short loc_180013F54
0x180013f35  movzx   r9d, word ptr [r8]
0x180013f39  test    r9w, r9w
0x180013f3d  jz      short loc_180013F54
0x180013f3f  add     r8, 2
0x180013f43  mov     [rax], r9w
0x180013f47  add     rax, 2
0x180013f4b  dec     rcx
0x180013f4e  sub     rdx, 1
0x180013f52  jnz     short loc_180013F30
0x180013f54  lea     rcx, [rax-2]
0x180013f58  test    rdx, rdx
0x180013f5b  cmovnz  rcx, rax
0x180013f5f  mov     [rcx], r14w
0x180013f63  jz      loc_180014216
0x180013f69  mov     eax, 7Bh ; '{'
0x180013f6e  cmp     [rbp+310h+var_340], ax
0x180013f72  jz      short loc_180013FB1
0x180013f74  lea     r8, [rbp+310h+var_340]; wchar_t *
0x180013f78  mov     rdx, rdi; unsigned __int64
0x180013f7b  lea     rcx, [rbp+310h+var_140]; wchar_t *
0x180013f82  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180013f87  test    eax, eax
0x180013f89  js      loc_180014216
0x180013f8f  lea     r9, [rbp+310h+var_140]
0x180013f96  lea     r8, aWs; "{%ws}"
0x180013f9d  mov     rdx, rdi; unsigned __int64
0x180013fa0  lea     rcx, [rbp+310h+var_340]; wchar_t *
0x180013fa4  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180013fa9  test    eax, eax
0x180013fab  js      loc_180014216
0x180013fb1  test    r13, r13
0x180013fb4  jnz     loc_1800141B6
0x180013fba  test    r15, r15
0x180013fbd  jnz     loc_1800141B6
0x180013fc3  mov     rdi, [rsp+410h+var_3C0]
0x180013fc8  mov     rax, [rdi]
0x180013fcb  mov     rbx, [rax+18h]
0x180013fcf  lea     rdx, [rsp+410h+var_3C8]
0x180013fd4  lea     rcx, [rbp+310h+var_378]
0x180013fd8  call    ??$out_ptr@XV?$unique_ptr@UIWbemQualifierSet@@Urelease_delete@tlx@@@utl@@$$V@utl@@YA?A_PAEAV?$unique_ptr@UIWbemQualifierSet@@Urelease_delete@tlx@@@0@@Z
0x180013fdd  nop
0x180013fde  mov     rdx, rax
0x180013fe1  mov     rcx, rdi
0x180013fe4  mov     rax, rbx
0x180013fe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013fec  nop
0x180013fed  lea     rcx, [rbp+310h+var_378]
0x180013ff1  call    ??1?$out_ptr_t@V?$unique_ptr@UIWbemQualifierSet@@Urelease_delete@tlx@@@utl@@PEAUIWbemQualifierSet@@$$V@utl@@QEAA@XZ; utl::out_ptr_t<utl::unique_ptr<IWbemQualifierSet,tlx::release_delete>,IWbemQualifierSet *,>::~out_ptr_t<utl::unique_ptr<IWbemQualifierSet,tlx::release_delete>,IWbemQualifierSet *,>(void)
0x180013ff6  xorps   xmm0, xmm0
0x180013ff9  xor     eax, eax
0x180013ffb  movups  xmmword ptr [rsp+410h+pbstr], xmm0
0x180014000  mov     [rsp+410h+var_3A0], rax
0x180014005  mov     rdi, [rsp+410h+var_3C8]
0x18001400a  mov     rax, [rdi]
0x18001400d  mov     rbx, [rax+18h]
0x180014011  lea     rcx, [rsp+410h+pbstr]; this
0x180014016  call    ?reset@unique_variant@tlx@@QEAAXXZ; tlx::unique_variant::reset(void)
0x18001401b  mov     [rsp+410h+var_3F0], r14
0x180014020  lea     r9, [rsp+410h+pbstr]
0x180014025  xor     r8d, r8d
0x180014028  lea     rdx, aDisplayname; "DisplayName"
0x18001402f  mov     rcx, rdi
0x180014032  mov     rax, rbx
0x180014035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001403a  test    eax, eax
0x18001403c  jns     loc_1800140D5
0x180014042  mov     r15d, 80041002h
0x180014048  cmp     eax, r15d
0x18001404b  jnz     loc_1800142DD
0x180014051  mov     rdi, [rsp+410h+var_3C8]
0x180014056  mov     rax, [rdi]
0x180014059  mov     rbx, [rax+18h]
0x18001405d  lea     rcx, [rsp+410h+pbstr]; this
0x180014062  call    ?reset@unique_variant@tlx@@QEAAXXZ; tlx::unique_variant::reset(void)
0x180014067  mov     [rsp+410h+var_3F0], r14
0x18001406c  lea     r9, [rsp+410h+pbstr]
0x180014071  xor     r8d, r8d
0x180014074  lea     rdx, aDescription; "Description"
0x18001407b  mov     rcx, rdi
0x18001407e  mov     rax, rbx
0x180014081  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014086  test    eax, eax
0x180014088  jns     short loc_1800140D5
0x18001408a  cmp     eax, r15d
0x18001408d  jnz     loc_1800142DD
0x180014093  mov     rdi, [rsp+410h+var_3C0]
0x180014098  mov     rax, [rdi]
0x18001409b  mov     rbx, [rax+20h]
0x18001409f  lea     rcx, [rsp+410h+pbstr]; this
0x1800140a4  call    ?reset@unique_variant@tlx@@QEAAXXZ; tlx::unique_variant::reset(void)
0x1800140a9  mov     [rsp+410h+var_3E8], r14
0x1800140ae  mov     [rsp+410h+var_3F0], r14
0x1800140b3  lea     r9, [rsp+410h+pbstr]
0x1800140b8  xor     r8d, r8d
0x1800140bb  lea     rdx, aClass; "__CLASS"
0x1800140c2  mov     rcx, rdi
0x1800140c5  mov     rax, rbx
0x1800140c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140cd  test    eax, eax
0x1800140cf  js      loc_1800142DD
0x1800140d5  mov     rcx, [rsp+410h+pbstr+8]; pbstr
0x1800140da  call    cs:__imp_SysStringLen
0x1800140e0  mov     ebx, eax
0x1800140e2  test    eax, eax
0x1800140e4  jz      loc_1800142DD
0x1800140ea  call    cs:__imp_GetProcessHeap
0x1800140f0  mov     rcx, rax; hHeap
0x1800140f3  mov     edx, 8; dwFlags
0x1800140f8  lea     r8d, [rdx+28h]; dwBytes
0x1800140fc  call    cs:__imp_HeapAlloc
0x180014102  mov     rdi, rax
0x180014105  test    rax, rax
0x180014108  jz      loc_1800142F3
0x18001410e  lea     r15d, [rbx+1]
0x180014112  lea     r14d, [r15+r15]
0x180014116  call    cs:__imp_GetProcessHeap
0x18001411c  mov     rcx, rax; hHeap
0x18001411f  mov     r8d, r14d; dwBytes
0x180014122  mov     edx, 8; dwFlags
0x180014127  call    cs:__imp_HeapAlloc
0x18001412d  mov     [rdi+20h], rax
0x180014131  test    rax, rax
0x180014134  jz      loc_1800142F3
0x18001413a  mov     edx, r15d; unsigned __int64
0x18001413d  mov     r8, [rsp+410h+pbstr+8]; wchar_t *
0x180014142  mov     rcx, rax; wchar_t *
0x180014145  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18001414a  test    eax, eax
0x18001414c  js      loc_1800142F3
0x180014152  mov     [rdi+28h], r14d
  ... truncated ...
```
