# CSyncMLDPU::IsRebootRequiredCommand(SyncMLElemType,IConfigManager2URI *,int *)

- ea: `0x1800070a0`
- end: `0x18000780e`
- name: `?IsRebootRequiredCommand@CSyncMLDPU@@QEAAJW4SyncMLElemType@@PEAUIConfigManager2URI@@PEAH@Z`
- size: `1902`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000e490`

## callees

- `0x1800070a0`
- `0x180011d9c`
- `0x180014330`
- `0x1800146e4`
- `0x180014c60`
- `0x180015c7b`
- `0x18001d670`
- `0x18001d7e0`
- `0x18001e1a8`
- `0x180030010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800071a9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180007590`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800071a9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180007590`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180007740`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180007740`
- `OLEAUT32!__imp_SysFreeString` at `0x1800073fd`
- `OLEAUT32!__imp_SysFreeString` at `0x180007442`
- `OLEAUT32!__imp_SysFreeString` at `0x18000760e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800077da`
- `OLEAUT32!__imp_SysFreeString` at `0x1800073fd`
- `OLEAUT32!__imp_SysFreeString` at `0x180007442`
- `OLEAUT32!__imp_SysFreeString` at `0x18000760e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800077da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000740b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000740b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800073ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800073ec`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CSyncMLDPU::IsRebootRequiredCommand(__int64 a1, unsigned __int64 a2, __int64 *a3, _DWORD *a4)
{
  __int64 v8; // rcx
  int v9; // eax
  unsigned int v10; // edi
  __int64 v11; // rax
  int v12; // ebx
  __int64 v13; // rcx
  int v14; // eax
  unsigned int v15; // ebx
  __int64 *v16; // rcx
  __int64 v17; // rax
  int v18; // ebx
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rdx
  int v22; // edi
  ULONGLONG Keyword; // r15
  ULONGLONG *v24; // rsi
  OLECHAR *v25; // r14
  DWORD LastError; // ebx
  __int64 v27; // rbx
  __int64 v28; // r15
  unsigned __int64 v29; // rsi
  _OWORD *v30; // r14
  unsigned __int64 v31; // rax
  unsigned __int64 v32; // rdi
  size_t v33; // rcx
  void *v34; // rax
  void *v35; // rcx
  _QWORD *v36; // rax
  void **v37; // rdx
  const struct std::nothrow_t *v38; // rdx
  void *v39; // rcx
  void **v40; // rcx
  __int64 v41; // rax
  int v42; // eax
  void **v43; // r8
  const struct std::nothrow_t *v44; // rdx
  void *v45; // rcx
  ULONG UserDataCount; // [rsp+20h] [rbp-79h]
  __int64 *v47; // [rsp+30h] [rbp-69h] BYREF
  __int64 *v48; // [rsp+38h] [rbp-61h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-59h] BYREF
  char v50; // [rsp+50h] [rbp-49h]
  BSTR bstrString; // [rsp+58h] [rbp-41h] BYREF
  __int64 v52; // [rsp+60h] [rbp-39h] BYREF
  void *v53[2]; // [rsp+68h] [rbp-31h] BYREF
  unsigned __int64 v54; // [rsp+78h] [rbp-21h]
  unsigned __int64 v55; // [rsp+80h] [rbp-19h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+88h] [rbp-11h] BYREF
  void *v57; // [rsp+98h] [rbp-1h]
  int v58; // [rsp+A0h] [rbp+7h]
  int v59; // [rsp+A4h] [rbp+Bh]
  void **v60; // [rsp+A8h] [rbp+Fh]
  int v61; // [rsp+B0h] [rbp+17h]
  int v62; // [rsp+B4h] [rbp+1Bh]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x451,
      (unsigned int)"onecoreuap\\admin\\dm\\coredpus\\syncmldpu\\syncmldpu.cpp",
      (const char *)0x80070057LL,
      UserDataCount);
    return 2147942487LL;
  }
  if ( !a4 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x452,
      (unsigned int)"onecoreuap\\admin\\dm\\coredpus\\syncmldpu\\syncmldpu.cpp",
      (const char *)0x80004003LL,
      UserDataCount);
    return 2147500035LL;
  }
  *a4 = 0;
  if ( (unsigned int)a2 > 0x24 )
    return 0;
  v8 = 0x10C4000000LL;
  if ( !_bittest64(&v8, a2) )
    return 0;
  v52 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(*a3 + 88))(a3, 1, &v52);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x459,
      (unsigned int)"onecoreuap\\admin\\dm\\coredpus\\syncmldpu\\syncmldpu.cpp",
      (const char *)(unsigned int)v9,
      UserDataCount);
    return v10;
  }
  v47 = a3;
  (*(void (__fastcall **)(__int64 *))(*a3 + 8))(a3);
  if ( !(unsigned int)_o__wcsicmp(L"vendor", v52) )
  {
    v48 = 0;
    v11 = *a3;
    *(_QWORD *)&EventDescriptor.Id = &v48;
    EventDescriptor.Keyword = 0;
    v50 = 1;
    v12 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, ULONGLONG *))(v11 + 144))(a3, 0, &EventDescriptor.Keyword);
    if ( v50 )
    {
      v13 = **(_QWORD **)&EventDescriptor.Id;
      **(_QWORD **)&EventDescriptor.Id = EventDescriptor.Keyword;
      if ( v13 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x462,
        (unsigned int)"onecoreuap\\admin\\dm\\coredpus\\syncmldpu\\syncmldpu.cpp",
        (const char *)(unsigned int)v12,
        UserDataCount);
      if ( v48 )
        (*(void (__fastcall **)(__int64 *))(*v48 + 16))(v48);
      if ( v47 )
        (*(void (__fastcall **)(__int64 *))(*v47 + 16))(v47);
      return (unsigned int)v12;
    }
    v14 = (*(__int64 (__fastcall **)(__int64 *, __int64, const wchar_t *, _QWORD))(*v48 + 208))(v48, 1, L"device", 0);
    v15 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x464,
        (unsigned int)"onecoreuap\\admin\\dm\\coredpus\\syncmldpu\\syncmldpu.cpp",
        (const char *)(unsigned int)v14,
        UserDataCount);
      if ( v48 )
        (*(void (__fastcall **)(__int64 *))(*v48 + 16))(v48);
      if ( v47 )
        (*(void (__fastcall **)(__int64 *))(*v47 + 16))(v47);
      return v15;
    }
    v16 = v47;
    v47 = 0;
    if ( v16 )
      (*(void (__fastcall **)(__int64 *))(*v16 + 16))(v16);
    v17 = *v48;
    *(_QWORD *)&EventDescriptor.Id = &v47;
    EventDescriptor.Keyword = 0;
    v50 = 1;
    v18 = (*(__int64 (__fastcall **)(__int64 *, ULONGLONG *))(v17 + 224))(v48, &EventDescriptor.Keyword);
    if ( v50 )
    {
      v19 = **(_QWORD **)&EventDescriptor.Id;
      **(_QWORD **)&EventDescriptor.Id = EventDescriptor.Keyword;
      if ( v19 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x468,
        (unsigned int)"onecoreuap\\admin\\dm\\coredpus\\syncmldpu\\syncmldpu.cpp",
        (const char *)(unsigned int)v18,
        UserDataCount);
      if ( v48 )
        (*(void (__fastcall **)(__int64 *))(*v48 + 16))(v48);
      if ( v47 )
        (*(void (__fastcall **)(__int64 *))(*v47 + 16))(v47);
      return (unsigned int)v18;
    }
    if ( v48 )
      (*(void (__fastcall **)(__int64 *))(*v48 + 16))(v48);
  }
  bstrString = 0;
  v20 = *v47;
  *(_QWORD *)&EventDescriptor.Id = &bstrString;
  EventDescriptor.Keyword = 0;
  v50 = 1;
  v22 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, ULONGLONG *))(v20 + 120))(
          v47,
          0,
          47,
          &EventDescriptor.Keyword);
  if ( v50 )
  {
    Keyword = EventDescriptor.Keyword;
    v24 = *(ULONGLONG **)&EventDescriptor.Id;
    v25 = **(OLECHAR ***)&EventDescriptor.Id;
    if ( **(_QWORD **)&EventDescriptor.Id )
    {
      LastError = GetLastError();
      SysFreeString(v25);
      SetLastError(LastError);
    }
    *v24 = Keyword;
  }
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46D,
      (unsigned int)"onecoreuap\\admin\\dm\\coredpus\\syncmldpu\\syncmldpu.cpp",
      (const char *)(unsigned int)v22,
      UserDataCount);
    if ( bstrString )
      SysFreeString(bstrString);
    if ( v47 )
      (*(void (__fastcall **)(__int64 *))(*v47 + 16))(v47);
    return (unsigned int)v22;
  }
  v27 = *(_QWORD *)(a1 + 448);
  v28 = *(_QWORD *)(a1 + 456);
  if ( v27 == v28 )
  {
LABEL_77:
    if ( bstrString )
      SysFreeString(bstrString);
    if ( v47 )
      (*(void (__fastcall **)(__int64 *, __int64))(*v47 + 16))(v47, v21);
    return 0;
  }
  while ( 1 )
  {
    *(_OWORD *)v53 = 0;
    v54 = 0;
    v55 = 0;
    v29 = *(_QWORD *)(v27 + 16);
    if ( *(_QWORD *)(v27 + 24) <= 7u )
      v30 = (_OWORD *)v27;
    else
      v30 = *(_OWORD **)v27;
    if ( v29 > 0x7FFFFFFFFFFFFFFELL )
      std::_Xlen_string();
    if ( v29 <= 7 )
    {
      v54 = *(_QWORD *)(v27 + 16);
      v31 = 7;
      v55 = 7;
      *(_OWORD *)v53 = *v30;
      goto LABEL_68;
    }
    v32 = v29 | 7;
    if ( (v29 | 7) > 0x7FFFFFFFFFFFFFFELL )
    {
      v32 = 0x7FFFFFFFFFFFFFFELL;
      v33 = -2;
LABEL_57:
      if ( v33 < 0x1000 )
      {
        v36 = operator new(v33);
      }
      else
      {
        if ( v33 + 39 < v33 )
          goto LABEL_107;
        v34 = operator new(v33 + 39);
        v35 = v34;
        if ( !v34 )
          goto LABEL_99;
        v36 = (_QWORD *)(((unsigned __int64)v34 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v36 - 1) = v35;
      }
      goto LABEL_67;
    }
    if ( v32 < 0xA )
      v32 = 10;
    if ( v32 + 1 > 0x7FFFFFFFFFFFFFFFLL )
LABEL_107:
      std::_Throw_bad_array_new_length();
    v33 = 2 * (v32 + 1);
    if ( v33 )
      goto LABEL_57;
    v36 = 0;
LABEL_67:
    v53[0] = v36;
    v54 = v29;
    v55 = v32;
    memcpy_0(v36, v30, 2 * v29 + 2);
    v31 = v55;
LABEL_68:
    v37 = v53;
    if ( v31 > 7 )
      v37 = (void **)v53[0];
    if ( !(unsigned int)_o__wcsicmp(bstrString, v37) )
      break;
    if ( v55 > 7 )
    {
      v38 = (const struct std::nothrow_t *)(2 * v55 + 2);
      v39 = v53[0];
      if ( (unsigned __int64)v38 >= 0x1000 )
      {
        if ( (unsigned __int64)v53[0] - *((_QWORD *)v53[0] - 1) - 8 > 0x1F )
          goto LABEL_99;
        v38 = (const struct std::nothrow_t *)(2 * v55 + 41);
        v39 = (void *)*((_QWORD *)v53[0] - 1);
      }
      operator delete(v39, v38);
    }
    v27 += 32;
    v21 = 0x7FFFFFFFFFFFFFFFLL;
    if ( v27 == v28 )
      goto LABEL_77;
  }
  *a4 = 1;
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    v40 = v53;
    if ( v55 > 7 )
      v40 = (void **)v53[0];
    if ( v40 )
    {
      v41 = -1;
      do
        ++v41;
      while ( *((_WORD *)v40 + v41) );
      v42 = 2 * v41 + 2;
    }
    else
    {
      v40 = (void **)&word_180032B28;
      v42 = 2;
    }
    v60 = v40;
    v61 = v42;
    v62 = 0;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 5;
    EventDescriptor.Keyword = 0;
    UserData.Ptr = (ULONGLONG)off_18003E050;
    UserData.Size = (unsigned __int16)*off_18003E050;
    UserData.Reserved = 2;
    v57 = &unk_180035FA8;
    v58 = 26;
    v59 = 1;
    LODWORD(v48) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
  if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x10) != 0 )
  {
    v43 = v53;
    if ( v55 > 7 )
      v43 = (void **)v53[0];
    McTemplateU0z_EventWriteTransfer(&MDM_ENTERPRISE_DIAGNOSTICS_Context, RebootRequiredURI, v43);
  }
  if ( v55 > 7 )
  {
    v44 = (const struct std::nothrow_t *)(2 * v55 + 2);
    if ( (unsigned __int64)v44 < 0x1000 )
    {
      v45 = v53[0];
    }
    else
    {
      v45 = (void *)*((_QWORD *)v53[0] - 1);
      if ( (unsigned __int64)((char *)v53[0] - (char *)v45 - 8) > 0x1F )
LABEL_99:
        __fastfail(5u);
      v44 = (const struct std::nothrow_t *)(2 * v55 + 41);
    }
    operator delete(v45, v44);
  }
  v54 = 0;
  v55 = 7;
  LOWORD(v53[0]) = 0;
  if ( bstrString )
    SysFreeString(bstrString);
  if ( v47 )
    (*(void (__fastcall **)(__int64 *))(*v47 + 16))(v47);
  return 0;
}

```

## disassembly

```asm
0x1800070a0  mov     [rsp-8+arg_8], rbx
0x1800070a5  push    rbp
0x1800070a6  push    rsi
0x1800070a7  push    rdi
0x1800070a8  push    r12
0x1800070aa  push    r13
0x1800070ac  push    r14
0x1800070ae  push    r15
0x1800070b0  lea     rbp, [rsp-27h]
0x1800070b5  sub     rsp, 0C0h
0x1800070bc  mov     rax, cs:__security_cookie
0x1800070c3  xor     rax, rsp
0x1800070c6  mov     [rbp+57h+var_38], rax
0x1800070ca  mov     r12, r9
0x1800070cd  mov     rbx, r8
0x1800070d0  mov     r13, rcx
0x1800070d3  test    r8, r8
0x1800070d6  jnz     short loc_1800070FD
0x1800070d8  mov     rcx, [rbp+5Fh]; this
0x1800070dc  mov     r9d, 80070057h; char *
0x1800070e2  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\coredpus\\syncml"...
0x1800070e9  mov     edx, 451h; void *
0x1800070ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800070f3  mov     eax, 80070057h
0x1800070f8  jmp     loc_180007633
0x1800070fd  test    r12, r12
0x180007100  jnz     short loc_180007127
0x180007102  mov     rcx, [rbp+5Fh]; this
0x180007106  mov     r9d, 80004003h; char *
0x18000710c  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\coredpus\\syncml"...
0x180007113  mov     edx, 452h; void *
0x180007118  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000711d  mov     eax, 80004003h
0x180007122  jmp     loc_180007633
0x180007127  xor     esi, esi
0x180007129  mov     [r9], esi
0x18000712c  cmp     edx, 24h ; '$'
0x18000712f  ja      loc_180007631
0x180007135  mov     rcx, 10C4000000h
0x18000713f  bt      rcx, rdx
0x180007143  jnb     loc_180007631
0x180007149  mov     [rbp+57h+var_90], rsi
0x18000714d  mov     rax, [r8]
0x180007150  lea     r8, [rbp+57h+var_90]
0x180007154  mov     edx, 1
0x180007159  mov     rcx, rbx
0x18000715c  mov     rax, [rax+58h]
0x180007160  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007165  mov     edi, eax
0x180007167  test    eax, eax
0x180007169  jns     short loc_18000718A
0x18000716b  mov     rcx, [rbp+5Fh]; this
0x18000716f  mov     r9d, eax; char *
0x180007172  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\coredpus\\syncml"...
0x180007179  mov     edx, 459h; void *
0x18000717e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007183  mov     eax, edi
0x180007185  jmp     loc_180007633
0x18000718a  mov     [rbp+57h+var_C0], rbx
0x18000718e  mov     rax, [rbx]
0x180007191  mov     rcx, rbx
0x180007194  mov     rax, [rax+8]
0x180007198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000719d  nop
0x18000719e  mov     rdx, [rbp+57h+var_90]
0x1800071a2  lea     rcx, aVendor; "vendor"
0x1800071a9  call    cs:__imp__o__wcsicmp
0x1800071b0  nop     dword ptr [rax+rax+00h]
0x1800071b5  test    eax, eax
0x1800071b7  jnz     loc_1800073A4
0x1800071bd  mov     [rbp+57h+var_B8], rsi
0x1800071c1  mov     rax, [rbx]
0x1800071c4  lea     rcx, [rbp+57h+var_B8]
0x1800071c8  mov     qword ptr [rbp+57h+EventDescriptor.Id], rcx
0x1800071cc  mov     [rbp+57h+EventDescriptor.Keyword], rsi
0x1800071d0  mov     [rbp+57h+var_A0], 1
0x1800071d4  lea     r8, [rbp+57h+EventDescriptor.Keyword]
0x1800071d8  xor     edx, edx
0x1800071da  mov     rcx, rbx
0x1800071dd  mov     rax, [rax+90h]
0x1800071e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071e9  mov     ebx, eax
0x1800071eb  cmp     [rbp+57h+var_A0], 0
0x1800071ef  jz      short loc_180007211
0x1800071f1  mov     r8, [rbp+57h+EventDescriptor.Keyword]
0x1800071f5  mov     rdx, qword ptr [rbp+57h+EventDescriptor.Id]
0x1800071f9  mov     rcx, [rdx]
0x1800071fc  mov     [rdx], r8
0x1800071ff  test    rcx, rcx
0x180007202  jz      short loc_180007211
0x180007204  mov     rdx, [rcx]
0x180007207  mov     rax, [rdx+10h]
0x18000720b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007210  nop
0x180007211  test    ebx, ebx
0x180007213  jns     short loc_180007261
0x180007215  mov     rcx, [rbp+5Fh]; this
0x180007219  mov     r9d, ebx; char *
0x18000721c  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\coredpus\\syncml"...
0x180007223  mov     edx, 462h; void *
0x180007228  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000722d  nop
0x18000722e  mov     rcx, [rbp+57h+var_B8]
0x180007232  test    rcx, rcx
0x180007235  jz      short loc_180007244
0x180007237  mov     rax, [rcx]
0x18000723a  mov     rax, [rax+10h]
0x18000723e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007243  nop
0x180007244  mov     rcx, [rbp+57h+var_C0]
0x180007248  test    rcx, rcx
0x18000724b  jz      short loc_18000725A
0x18000724d  mov     rax, [rcx]
0x180007250  mov     rax, [rax+10h]
0x180007254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007259  nop
0x18000725a  mov     eax, ebx
0x18000725c  jmp     loc_180007633
0x180007261  mov     rcx, [rbp+57h+var_B8]
0x180007265  mov     rax, [rcx]
0x180007268  xor     r9d, r9d
0x18000726b  lea     r8, aDevice; "device"
0x180007272  mov     edx, 1
0x180007277  mov     rax, [rax+0D0h]
0x18000727e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007283  mov     ebx, eax
0x180007285  test    eax, eax
0x180007287  jns     short loc_1800072D5
0x180007289  mov     rcx, [rbp+5Fh]; this
0x18000728d  mov     r9d, eax; char *
0x180007290  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\coredpus\\syncml"...
0x180007297  mov     edx, 464h; void *
0x18000729c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800072a1  nop
0x1800072a2  mov     rcx, [rbp+57h+var_B8]
0x1800072a6  test    rcx, rcx
0x1800072a9  jz      short loc_1800072B8
0x1800072ab  mov     rax, [rcx]
0x1800072ae  mov     rax, [rax+10h]
0x1800072b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072b7  nop
0x1800072b8  mov     rcx, [rbp+57h+var_C0]
0x1800072bc  test    rcx, rcx
0x1800072bf  jz      short loc_1800072CE
0x1800072c1  mov     rax, [rcx]
0x1800072c4  mov     rax, [rax+10h]
0x1800072c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072cd  nop
0x1800072ce  mov     eax, ebx
0x1800072d0  jmp     loc_180007633
0x1800072d5  mov     rcx, [rbp+57h+var_C0]
0x1800072d9  mov     [rbp+57h+var_C0], rsi
0x1800072dd  test    rcx, rcx
0x1800072e0  jz      short loc_1800072EF
0x1800072e2  mov     rax, [rcx]
0x1800072e5  mov     rax, [rax+10h]
0x1800072e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072ee  nop
0x1800072ef  mov     rcx, [rbp+57h+var_B8]
0x1800072f3  mov     rax, [rcx]
0x1800072f6  lea     rdx, [rbp+57h+var_C0]
0x1800072fa  mov     qword ptr [rbp+57h+EventDescriptor.Id], rdx
0x1800072fe  mov     [rbp+57h+EventDescriptor.Keyword], rsi
0x180007302  mov     [rbp+57h+var_A0], 1
0x180007306  lea     rdx, [rbp+57h+EventDescriptor.Keyword]
0x18000730a  mov     rax, [rax+0E0h]
0x180007311  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007316  mov     ebx, eax
0x180007318  cmp     [rbp+57h+var_A0], 0
0x18000731c  jz      short loc_18000733E
0x18000731e  mov     r8, [rbp+57h+EventDescriptor.Keyword]
0x180007322  mov     rdx, qword ptr [rbp+57h+EventDescriptor.Id]
0x180007326  mov     rcx, [rdx]
0x180007329  mov     [rdx], r8
0x18000732c  test    rcx, rcx
0x18000732f  jz      short loc_18000733E
0x180007331  mov     rdx, [rcx]
0x180007334  mov     rax, [rdx+10h]
0x180007338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000733d  nop
0x18000733e  test    ebx, ebx
0x180007340  jns     short loc_18000738E
0x180007342  mov     rcx, [rbp+5Fh]; this
0x180007346  mov     r9d, ebx; char *
0x180007349  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\coredpus\\syncml"...
0x180007350  mov     edx, 468h; void *
0x180007355  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000735a  nop
0x18000735b  mov     rcx, [rbp+57h+var_B8]
0x18000735f  test    rcx, rcx
0x180007362  jz      short loc_180007371
0x180007364  mov     rax, [rcx]
0x180007367  mov     rax, [rax+10h]
0x18000736b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007370  nop
0x180007371  mov     rcx, [rbp+57h+var_C0]
0x180007375  test    rcx, rcx
0x180007378  jz      short loc_180007387
0x18000737a  mov     rax, [rcx]
0x18000737d  mov     rax, [rax+10h]
0x180007381  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007386  nop
0x180007387  mov     eax, ebx
0x180007389  jmp     loc_180007633
0x18000738e  mov     rcx, [rbp+57h+var_B8]
0x180007392  test    rcx, rcx
0x180007395  jz      short loc_1800073A4
0x180007397  mov     rax, [rcx]
0x18000739a  mov     rax, [rax+10h]
0x18000739e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073a3  nop
0x1800073a4  mov     [rbp+57h+bstrString], rsi
0x1800073a8  mov     rcx, [rbp+57h+var_C0]
0x1800073ac  mov     rax, [rcx]
0x1800073af  lea     rdx, [rbp+57h+bstrString]
0x1800073b3  mov     qword ptr [rbp+57h+EventDescriptor.Id], rdx
0x1800073b7  mov     [rbp+57h+EventDescriptor.Keyword], rsi
0x1800073bb  mov     [rbp+57h+var_A0], 1
0x1800073bf  mov     r8d, 2Fh ; '/'
0x1800073c5  lea     r9, [rbp+57h+EventDescriptor.Keyword]
0x1800073c9  xor     edx, edx
0x1800073cb  mov     rax, [rax+78h]
0x1800073cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073d4  mov     edi, eax
0x1800073d6  cmp     [rbp+57h+var_A0], 0
0x1800073da  jz      short loc_18000741C
0x1800073dc  mov     r15, [rbp+57h+EventDescriptor.Keyword]
0x1800073e0  mov     rsi, qword ptr [rbp+57h+EventDescriptor.Id]
0x1800073e4  mov     r14, [rsi]
0x1800073e7  test    r14, r14
0x1800073ea  jz      short loc_180007417
0x1800073ec  call    cs:__imp_GetLastError
0x1800073f3  nop     dword ptr [rax+rax+00h]
0x1800073f8  mov     ebx, eax
0x1800073fa  mov     rcx, r14; bstrString
0x1800073fd  call    cs:__imp_SysFreeString
0x180007404  nop     dword ptr [rax+rax+00h]
0x180007409  mov     ecx, ebx; dwErrCode
0x18000740b  call    cs:__imp_SetLastError
0x180007412  nop     dword ptr [rax+rax+00h]
0x180007417  mov     [rsi], r15
0x18000741a  xor     esi, esi
0x18000741c  test    edi, edi
0x18000741e  jns     short loc_18000746C
0x180007420  mov     rcx, [rbp+5Fh]; this
0x180007424  mov     r9d, edi; char *
0x180007427  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\coredpus\\syncml"...
0x18000742e  mov     edx, 46Dh; void *
0x180007433  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007438  nop
0x180007439  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18000743d  test    rcx, rcx
0x180007440  jz      short loc_18000744F
0x180007442  call    cs:__imp_SysFreeString
0x180007449  nop     dword ptr [rax+rax+00h]
0x18000744e  nop
0x18000744f  mov     rcx, [rbp+57h+var_C0]
0x180007453  test    rcx, rcx
0x180007456  jz      short loc_180007465
0x180007458  mov     rax, [rcx]
0x18000745b  mov     rax, [rax+10h]
0x18000745f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007464  nop
0x180007465  mov     eax, edi
0x180007467  jmp     loc_180007633
0x18000746c  mov     rbx, [r13+1C0h]
0x180007473  mov     r15, [r13+1C8h]
0x18000747a  cmp     rbx, r15
0x18000747d  jz      loc_180007605
0x180007483  mov     eax, 0Ah
0x180007488  mov     rdx, 7FFFFFFFFFFFFFFFh
0x180007492  mov     r13, 7FFFFFFFFFFFFFFEh
0x18000749c  nop     dword ptr [rax+00h]
0x1800074a0  xorps   xmm0, xmm0
0x1800074a3  movups  xmmword ptr [rbp+57h+var_88], xmm0
0x1800074a7  mov     [rbp+57h+var_78], rsi
0x1800074ab  mov     [rbp+57h+var_70], rsi
0x1800074af  mov     rsi, [rbx+10h]
0x1800074b3  cmp     qword ptr [rbx+18h], 7
0x1800074b8  jbe     short loc_1800074BF
0x1800074ba  mov     r14, [rbx]
0x1800074bd  jmp     short loc_1800074C2
0x1800074bf  mov     r14, rbx
0x1800074c2  cmp     rsi, r13
0x1800074c5  ja      loc_180007808
0x1800074cb  cmp     rsi, 7
0x1800074cf  ja      short loc_1800074EB
0x1800074d1  mov     [rbp+57h+var_78], rsi
0x1800074d5  mov     eax, 7
0x1800074da  mov     [rbp+57h+var_70], rax
0x1800074de  movups  xmm0, xmmword ptr [r14]
0x1800074e2  movups  xmmword ptr [rbp+57h+var_88], xmm0
0x1800074e6  jmp     loc_18000757F
0x1800074eb  mov     rdi, rsi
0x1800074ee  or      rdi, 7
0x1800074f2  cmp     rdi, r13
0x1800074f5  jbe     short loc_180007539
0x1800074f7  mov     rdi, r13
0x1800074fa  mov     rcx, 0FFFFFFFFFFFFFFFEh; Size
0x180007501  cmp     rcx, 1000h
  ... truncated ...
```
