# CRATicketInfo::InitializeTicket(ushort *)

- ea: `0x1400393ac`
- end: `0x140039e23`
- name: `?InitializeTicket@CRATicketInfo@@QEAAJPEAG@Z`
- size: `2679`
- prototype: `__int64 __fastcall(unsigned __int16 **this, unsigned __int16 *Src)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140035328`
- `0x1400380dc`

## callees

- `0x14000a0e4`
- `0x140034ce4`
- `0x140036070`
- `0x140038db8`
- `0x1400393ac`
- `0x14004d010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x14003963e`
- `KERNEL32!GetProcessHeap` at `0x140039689`
- `KERNEL32!GetProcessHeap` at `0x14003963e`
- `KERNEL32!GetProcessHeap` at `0x140039689`
- `KERNEL32!HeapAlloc` at `0x140039655`
- `KERNEL32!HeapAlloc` at `0x1400396a0`
- `KERNEL32!HeapAlloc` at `0x140039655`
- `KERNEL32!HeapAlloc` at `0x1400396a0`
- `OLEAUT32!__imp_SysFreeString` at `0x140039d5f`
- `OLEAUT32!__imp_SysFreeString` at `0x140039d70`
- `OLEAUT32!__imp_SysFreeString` at `0x140039d80`
- `OLEAUT32!__imp_SysFreeString` at `0x140039d90`
- `OLEAUT32!__imp_SysFreeString` at `0x140039da0`
- `OLEAUT32!__imp_SysFreeString` at `0x140039d5f`
- `OLEAUT32!__imp_SysFreeString` at `0x140039d70`
- `OLEAUT32!__imp_SysFreeString` at `0x140039d80`
- `OLEAUT32!__imp_SysFreeString` at `0x140039d90`
- `OLEAUT32!__imp_SysFreeString` at `0x140039da0`
- `OLEAUT32!__imp_VariantInit` at `0x1400396fd`
- `OLEAUT32!__imp_VariantInit` at `0x14003970e`
- `OLEAUT32!__imp_VariantInit` at `0x1400396fd`
- `OLEAUT32!__imp_VariantInit` at `0x14003970e`
- `OLEAUT32!__imp_VariantClear` at `0x14003988d`
- `OLEAUT32!__imp_VariantClear` at `0x14003989e`
- `OLEAUT32!__imp_VariantClear` at `0x140039cd5`
- `OLEAUT32!__imp_VariantClear` at `0x140039ce6`
- `OLEAUT32!__imp_VariantClear` at `0x14003988d`
- `OLEAUT32!__imp_VariantClear` at `0x14003989e`
- `OLEAUT32!__imp_VariantClear` at `0x140039cd5`
- `OLEAUT32!__imp_VariantClear` at `0x140039ce6`

## string_xrefs

- `0x140039446`: `base\diagnosis\ra\racommon\src\ticketinfo.cpp`
- `0x14003948f`: `base\diagnosis\ra\racommon\src\ticketinfo.cpp`
- `0x1400394d8`: `base\diagnosis\ra\racommon\src\ticketinfo.cpp`
- `0x140039567`: `base\diagnosis\ra\racommon\src\ticketinfo.cpp`
- `0x1400398e4`: `base\diagnosis\ra\racommon\src\ticketinfo.cpp`
- `0x140039955`: `base\diagnosis\ra\racommon\src\ticketinfo.cpp`
- `0x1400399c6`: `base\diagnosis\ra\racommon\src\ticketinfo.cpp`
- `0x140039a3b`: `base\diagnosis\ra\racommon\src\ticketinfo.cpp`
- `0x140039ab1`: `base\diagnosis\ra\racommon\src\ticketinfo.cpp`
- `0x140039b22`: `base\diagnosis\ra\racommon\src\ticketinfo.cpp`
- `0x140039b97`: `base\diagnosis\ra\racommon\src\ticketinfo.cpp`
- `0x140039c0d`: `base\diagnosis\ra\racommon\src\ticketinfo.cpp`
- `0x140039c7b`: `base\diagnosis\ra\racommon\src\ticketinfo.cpp`
- `0x140039d16`: `base\diagnosis\ra\racommon\src\ticketinfo.cpp`
- `0x140039d47`: `base\diagnosis\ra\racommon\src\ticketinfo.cpp`

## pseudocode

```c
__int64 __fastcall CRATicketInfo::InitializeTicket(unsigned __int16 **this, unsigned __int16 *Src)
{
  struct IXMLDOMDocument2 *v4; // rbx
  OLECHAR *v5; // rdi
  OLECHAR *v6; // rsi
  OLECHAR *v7; // r14
  signed int v8; // eax
  CEventLogger *v9; // rcx
  int v10; // r15d
  unsigned int v11; // r9d
  signed int v12; // eax
  CEventLogger *v13; // rcx
  signed int inited; // eax
  CEventLogger *v15; // rcx
  signed int v16; // eax
  CEventLogger *v17; // rcx
  signed int v18; // eax
  CEventLogger *v19; // rcx
  unsigned int v20; // r9d
  unsigned __int16 **v21; // r12
  SIZE_T v22; // r15
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v24; // rax
  CEventLogger *v25; // rcx
  SIZE_T v26; // r15
  HANDLE v27; // rax
  unsigned __int16 *v28; // rax
  CEventLogger *v29; // rcx
  int v30; // r13d
  signed int v31; // eax
  CEventLogger *v32; // rcx
  signed int v33; // eax
  CEventLogger *v34; // rcx
  signed int v35; // eax
  CEventLogger *v36; // rcx
  signed int v37; // eax
  CEventLogger *v38; // rcx
  signed int v39; // eax
  CEventLogger *v40; // rcx
  signed int v41; // eax
  CEventLogger *v42; // rcx
  signed int v43; // eax
  CEventLogger *v44; // rcx
  __int64 v45; // rcx
  CEventLogger *v47; // [rsp+30h] [rbp-59h] BYREF
  __int64 v48; // [rsp+38h] [rbp-51h] BYREF
  __int64 v49; // [rsp+40h] [rbp-49h] BYREF
  struct IXMLDOMDocument2 *v50; // [rsp+48h] [rbp-41h] BYREF
  __int64 v51; // [rsp+50h] [rbp-39h] BYREF
  VARIANTARG v52; // [rsp+58h] [rbp-31h] BYREF
  VARIANTARG pvarg; // [rsp+70h] [rbp-19h] BYREF
  BSTR v54; // [rsp+88h] [rbp-1h] BYREF
  OLECHAR *v55; // [rsp+90h] [rbp+7h] BYREF
  OLECHAR *v56; // [rsp+98h] [rbp+Fh] BYREF
  BSTR bstrString; // [rsp+A0h] [rbp+17h] BYREF
  BSTR v58[7]; // [rsp+A8h] [rbp+1Fh] BYREF
  __int64 v60; // [rsp+100h] [rbp+77h] BYREF
  CEventLogger *v61; // [rsp+108h] [rbp+7Fh] BYREF

  v4 = 0;
  v50 = 0;
  v51 = 0;
  v49 = 0;
  v48 = 0;
  v5 = 0;
  v54 = 0;
  v6 = 0;
  v55 = 0;
  v7 = 0;
  v56 = 0;
  v58[0] = 0;
  bstrString = 0;
  v8 = DuplicateString(Src, this);
  v10 = v8;
  if ( v8 < 0 )
  {
    v11 = 95;
LABEL_118:
    CEventLogger::LogError(
      v9,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\racommon\\src\\ticketinfo.cpp",
      v11,
      L"CRATicketInfo::InitializeTicket",
      v8);
    goto LABEL_119;
  }
  v12 = ATL::CComBSTR::Append((ATL::CComBSTR *)&v54, Src);
  v10 = v12;
  if ( v12 < 0 )
  {
    CEventLogger::LogError(
      v13,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\racommon\\src\\ticketinfo.cpp",
      0x62u,
      L"CRATicketInfo::InitializeTicket",
      v12);
    v5 = v54;
    goto LABEL_119;
  }
  v5 = v54;
  inited = InitXMLDocWithString(v54, &v50);
  v10 = inited;
  if ( inited < 0 )
  {
    CEventLogger::LogError(
      v15,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\racommon\\src\\ticketinfo.cpp",
      0x65u,
      L"CRATicketInfo::InitializeTicket",
      inited);
    v4 = v50;
    goto LABEL_119;
  }
  v16 = ATL::CComBSTR::Append((ATL::CComBSTR *)&v55, L"E/C");
  v10 = v16;
  if ( v16 < 0 )
  {
    CEventLogger::LogError(
      v17,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\racommon\\src\\ticketinfo.cpp",
      0x67u,
      L"CRATicketInfo::InitializeTicket",
      v16);
    v4 = v50;
    v6 = v55;
    goto LABEL_119;
  }
  v4 = v50;
  v6 = v55;
  v8 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, OLECHAR *, __int64 *))v50->lpVtbl->selectSingleNode)(
         v50,
         v55,
         &v51);
  v10 = v8;
  if ( v8 < 0 || v8 == 1 )
  {
    v11 = 105;
    goto LABEL_118;
  }
  if ( !v51 )
  {
    v20 = 106;
    goto LABEL_116;
  }
  v18 = ATL::CComBSTR::Append((ATL::CComBSTR *)&v56, L"T/L");
  v10 = v18;
  if ( v18 < 0 )
  {
    CEventLogger::LogError(
      v19,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\racommon\\src\\ticketinfo.cpp",
      0x6Cu,
      L"CRATicketInfo::InitializeTicket",
      v18);
    v7 = v56;
    goto LABEL_119;
  }
  v7 = v56;
  v8 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, __int64 *))(*(_QWORD *)v51 + 288LL))(v51, v56, &v49);
  v10 = v8;
  if ( v8 < 0 || v8 == 1 )
  {
    v11 = 110;
    goto LABEL_118;
  }
  if ( !v49 )
  {
    v20 = 111;
LABEL_116:
    CEventLogger::LogError(
      v9,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\racommon\\src\\ticketinfo.cpp",
      v20,
      L"CRATicketInfo::InitializeTicket",
      0);
    v10 = -2147467259;
    goto LABEL_119;
  }
  v8 = ATL::CComBSTR::Append((ATL::CComBSTR *)v58, L"P");
  v10 = v8;
  if ( v8 < 0 )
  {
    v11 = 113;
    goto LABEL_118;
  }
  v8 = ATL::CComBSTR::Append((ATL::CComBSTR *)&bstrString, L"N");
  v10 = v8;
  if ( v8 < 0 )
  {
    v11 = 115;
    goto LABEL_118;
  }
  v21 = this + 1;
  v8 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v49 + 64LL))(v49, this + 1);
  v10 = v8;
  if ( v8 < 0 )
  {
    v11 = 117;
    goto LABEL_118;
  }
  v22 = 8LL * *(int *)v21;
  ProcessHeap = GetProcessHeap();
  v24 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, v22);
  this[2] = v24;
  if ( v24 )
  {
    v26 = 8LL * *(int *)v21;
    v27 = GetProcessHeap();
    v28 = (unsigned __int16 *)HeapAlloc(v27, 8u, v26);
    this[3] = v28;
    if ( v28 )
    {
      v30 = 0;
      while ( 1 )
      {
        v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v49 + 72LL))(v49, &v48);
        if ( v10 < 0 || !v48 )
          goto LABEL_119;
        VariantInit(&pvarg);
        VariantInit(&v52);
        v60 = 0;
        v47 = 0;
        v61 = 0;
        v31 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v48 + 136LL))(v48, &v60);
        v10 = v31;
        if ( v31 < 0 )
        {
          CEventLogger::LogError(
            v32,
            &Recoverable_Error,
            L"base\\diagnosis\\ra\\racommon\\src\\ticketinfo.cpp",
            0x88u,
            L"CRATicketInfo::InitializeTicket",
            v31);
          if ( v61 )
            (*(void (__fastcall **)(CEventLogger *))(*(_QWORD *)v61 + 16LL))(v61);
          if ( v47 )
            (*(void (__fastcall **)(CEventLogger *))(*(_QWORD *)v47 + 16LL))(v47);
          if ( v60 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
          goto LABEL_113;
        }
        v33 = (*(__int64 (__fastcall **)(__int64, BSTR, CEventLogger **))(*(_QWORD *)v60 + 56LL))(v60, bstrString, &v61);
        v10 = v33;
        if ( v33 < 0 || v33 == 1 )
        {
          CEventLogger::LogError(
            v34,
            &Recoverable_Error,
            L"base\\diagnosis\\ra\\racommon\\src\\ticketinfo.cpp",
            0x8Au,
            L"CRATicketInfo::InitializeTicket",
            v33);
          if ( v61 )
            (*(void (__fastcall **)(CEventLogger *))(*(_QWORD *)v61 + 16LL))(v61);
          if ( v47 )
            (*(void (__fastcall **)(CEventLogger *))(*(_QWORD *)v47 + 16LL))(v47);
          if ( v60 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
          goto LABEL_113;
        }
        if ( !v61 )
        {
          CEventLogger::LogError(
            0,
            &Recoverable_Error,
            L"base\\diagnosis\\ra\\racommon\\src\\ticketinfo.cpp",
            0x8Bu,
            L"CRATicketInfo::InitializeTicket",
            0);
          v10 = -2147467259;
          if ( v61 )
            (*(void (__fastcall **)(CEventLogger *))(*(_QWORD *)v61 + 16LL))(v61);
          if ( v47 )
            (*(void (__fastcall **)(CEventLogger *))(*(_QWORD *)v47 + 16LL))(v47);
          if ( v60 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
          goto LABEL_113;
        }
        v35 = (*(__int64 (__fastcall **)(CEventLogger *, VARIANTARG *))(*(_QWORD *)v61 + 64LL))(v61, &v52);
        v10 = v35;
        if ( v35 < 0 )
        {
          CEventLogger::LogError(
            v36,
            &Recoverable_Error,
            L"base\\diagnosis\\ra\\racommon\\src\\ticketinfo.cpp",
            0x8Du,
            L"CRATicketInfo::InitializeTicket",
            v35);
          if ( v61 )
            (*(void (__fastcall **)(CEventLogger *))(*(_QWORD *)v61 + 16LL))(v61);
          if ( v47 )
            (*(void (__fastcall **)(CEventLogger *))(*(_QWORD *)v47 + 16LL))(v47);
          if ( v60 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
          goto LABEL_113;
        }
        v37 = (*(__int64 (__fastcall **)(__int64, BSTR, CEventLogger **))(*(_QWORD *)v60 + 56LL))(v60, v58[0], &v47);
        v10 = v37;
        if ( v37 < 0 || v37 == 1 )
        {
          CEventLogger::LogError(
            v38,
            &Recoverable_Error,
            L"base\\diagnosis\\ra\\racommon\\src\\ticketinfo.cpp",
            0x8Fu,
            L"CRATicketInfo::InitializeTicket",
            v37);
          if ( v61 )
            (*(void (__fastcall **)(CEventLogger *))(*(_QWORD *)v61 + 16LL))(v61);
          if ( v47 )
            (*(void (__fastcall **)(CEventLogger *))(*(_QWORD *)v47 + 16LL))(v47);
          if ( v60 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
          goto LABEL_113;
        }
        if ( !v47 )
        {
          CEventLogger::LogError(
            0,
            &Recoverable_Error,
            L"base\\diagnosis\\ra\\racommon\\src\\ticketinfo.cpp",
            0x90u,
            L"CRATicketInfo::InitializeTicket",
            0);
          v10 = -2147467259;
          if ( v61 )
            (*(void (__fastcall **)(CEventLogger *))(*(_QWORD *)v61 + 16LL))(v61);
          if ( v47 )
            (*(void (__fastcall **)(CEventLogger *))(*(_QWORD *)v47 + 16LL))(v47);
          if ( v60 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
          goto LABEL_113;
        }
        v39 = (*(__int64 (__fastcall **)(CEventLogger *, VARIANTARG *))(*(_QWORD *)v47 + 64LL))(v47, &pvarg);
        v10 = v39;
        if ( v39 < 0 )
        {
          CEventLogger::LogError(
            v40,
            &Recoverable_Error,
            L"base\\diagnosis\\ra\\racommon\\src\\ticketinfo.cpp",
            0x92u,
            L"CRATicketInfo::InitializeTicket",
            v39);
          if ( v61 )
            (*(void (__fastcall **)(CEventLogger *))(*(_QWORD *)v61 + 16LL))(v61);
          if ( v47 )
            (*(void (__fastcall **)(CEventLogger *))(*(_QWORD *)v47 + 16LL))(v47);
          if ( v60 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
          goto LABEL_113;
        }
        v41 = DuplicateString(v52.bstrVal, (unsigned __int16 **)&this[2][4 * v30]);
        v10 = v41;
        if ( v41 < 0 )
          break;
        v43 = DuplicateString(pvarg.bstrVal, (unsigned __int16 **)&this[3][4 * v30]);
        v10 = v43;
        if ( v43 < 0 )
        {
          CEventLogger::LogError(
            v44,
            &Recoverable_Error,
            L"base\\diagnosis\\ra\\racommon\\src\\ticketinfo.cpp",
            0x98u,
            L"CRATicketInfo::InitializeTicket",
            v43);
          if ( v61 )
            (*(void (__fastcall **)(CEventLogger *))(*(_QWORD *)v61 + 16LL))(v61);
          if ( v47 )
            (*(void (__fastcall **)(CEventLogger *))(*(_QWORD *)v47 + 16LL))(v47);
          if ( v60 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
LABEL_113:
          VariantClear(&v52);
          VariantClear(&pvarg);
          goto LABEL_119;
        }
        ++v30;
        if ( v61 )
          (*(void (__fastcall **)(CEventLogger *))(*(_QWORD *)v61 + 16LL))(v61);
        if ( v47 )
          (*(void (__fastcall **)(CEventLogger *))(*(_QWORD *)v47 + 16LL))(v47);
        if ( v60 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
        VariantClear(&v52);
        VariantClear(&pvarg);
        v45 = v48;
        if ( v48 )
        {
          v48 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
        }
      }
      CEventLogger::LogError(
        v42,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\racommon\\src\\ticketinfo.cpp",
        0x95u,
        L"CRATicketInfo::InitializeTicket",
        v41);
      if ( v61 )
        (*(void (__fastcall **)(CEventLogger *))(*(_QWORD *)v61 + 16LL))(v61);
      if ( v47 )
        (*(void (__fastcall **)(CEventLogger *))(*(_QWORD *)v47 + 16LL))(v47);
      if ( v60 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
      goto LABEL_113;
    }
    v10 = -2147024882;
    CEventLogger::LogError(
      v29,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\racommon\\src\\ticketinfo.cpp",
      0x7Bu,
      L"CRATicketInfo::InitializeTicket",
      0x8007000E);
  }
  else
  {
    v10 = -2147024882;
    CEventLogger::LogError(
      v25,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\racommon\\src\\ticketinfo.cpp",
      0x7Au,
      L"CRATicketInfo::InitializeTicket",
      0x8007000E);
  }
LABEL_119:
  SysFreeString(bstrString);
  SysFreeString(v58[0]);
  SysFreeString(v7);
  SysFreeString(v6);
  SysFreeString(v5);
  if ( v48 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
  if ( v49 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
  if ( v51 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
  if ( v4 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v4->lpVtbl->Release)(v4);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1400393ac  mov     [rsp-8+arg_8], rbx
0x1400393b1  mov     [rsp-8+arg_0], rcx
0x1400393b6  push    rbp
0x1400393b7  push    rsi
0x1400393b8  push    rdi
0x1400393b9  push    r12
0x1400393bb  push    r13
0x1400393bd  push    r14
0x1400393bf  push    r15
0x1400393c1  lea     rbp, [rsp-27h]
0x1400393c6  sub     rsp, 0B0h
0x1400393cd  mov     r12, rdx
0x1400393d0  mov     r13, rcx
0x1400393d3  xor     eax, eax
0x1400393d5  mov     ebx, eax
0x1400393d7  mov     [rbp+57h+var_98], rax
0x1400393db  mov     [rbp+57h+var_90], rax
0x1400393df  mov     [rbp+57h+var_A0], rax
0x1400393e3  mov     [rbp+57h+var_A8], rax
0x1400393e7  mov     edi, eax
0x1400393e9  mov     [rbp+57h+var_58], rax
0x1400393ed  mov     esi, eax
0x1400393ef  mov     [rbp+57h+var_50], rax
0x1400393f3  mov     r14d, eax
0x1400393f6  mov     [rbp+57h+var_48], rax
0x1400393fa  mov     [rbp+57h+var_38], rax
0x1400393fe  mov     [rbp+57h+bstrString], rax
0x140039402  mov     rdx, rcx; unsigned __int16 **
0x140039405  mov     rcx, r12; Src
0x140039408  call    ?DuplicateString@@YAJPEBGPEAPEAG@Z; DuplicateString(ushort const *,ushort * *)
0x14003940d  mov     r15d, eax
0x140039410  test    eax, eax
0x140039412  jns     short loc_14003941D
0x140039414  lea     r9d, [r14+5Fh]
0x140039418  jmp     loc_140039D37
0x14003941d  mov     rdx, r12; unsigned __int16 *
0x140039420  lea     rcx, [rbp+57h+var_58]; this
0x140039424  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x140039429  mov     r15d, eax
0x14003942c  test    eax, eax
0x14003942e  jns     short loc_140039462
0x140039430  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x140039434  lea     rax, aCraticketinfoI; "CRATicketInfo::InitializeTicket"
0x14003943b  mov     [rsp+0E0h+var_C0], rax; unsigned __int16 *
0x140039440  mov     r9d, 62h ; 'b'; unsigned int
0x140039446  lea     r8, aBaseDiagnosisR_31; "base\\diagnosis\\ra\\racommon\\src\\tic"...
0x14003944d  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140039454  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140039459  mov     rdi, [rbp+57h+var_58]
0x14003945d  jmp     loc_140039D5B
0x140039462  lea     rdx, [rbp+57h+var_98]; struct IXMLDOMDocument2 **
0x140039466  mov     rdi, [rbp+57h+var_58]
0x14003946a  mov     rcx, rdi; unsigned __int16 *
0x14003946d  call    ?InitXMLDocWithString@@YAJQEAGPEAPEAUIXMLDOMDocument2@@@Z; InitXMLDocWithString(ushort * const,IXMLDOMDocument2 * *)
0x140039472  mov     r15d, eax
0x140039475  test    eax, eax
0x140039477  jns     short loc_1400394AB
0x140039479  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x14003947d  lea     rax, aCraticketinfoI; "CRATicketInfo::InitializeTicket"
0x140039484  mov     [rsp+0E0h+var_C0], rax; unsigned __int16 *
0x140039489  mov     r9d, 65h ; 'e'; unsigned int
0x14003948f  lea     r8, aBaseDiagnosisR_31; "base\\diagnosis\\ra\\racommon\\src\\tic"...
0x140039496  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14003949d  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400394a2  mov     rbx, [rbp+57h+var_98]
0x1400394a6  jmp     loc_140039D5B
0x1400394ab  lea     rdx, aEC; "E/C"
0x1400394b2  lea     rcx, [rbp+57h+var_50]; this
0x1400394b6  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x1400394bb  mov     r15d, eax
0x1400394be  test    eax, eax
0x1400394c0  jns     short loc_1400394F8
0x1400394c2  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x1400394c6  lea     rax, aCraticketinfoI; "CRATicketInfo::InitializeTicket"
0x1400394cd  mov     [rsp+0E0h+var_C0], rax; unsigned __int16 *
0x1400394d2  mov     r9d, 67h ; 'g'; unsigned int
0x1400394d8  lea     r8, aBaseDiagnosisR_31; "base\\diagnosis\\ra\\racommon\\src\\tic"...
0x1400394df  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x1400394e6  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400394eb  mov     rbx, [rbp+57h+var_98]
0x1400394ef  mov     rsi, [rbp+57h+var_50]
0x1400394f3  jmp     loc_140039D5B
0x1400394f8  mov     rbx, [rbp+57h+var_98]
0x1400394fc  mov     rax, [rbx]
0x1400394ff  lea     r8, [rbp+57h+var_90]
0x140039503  mov     rsi, [rbp+57h+var_50]
0x140039507  mov     rdx, rsi
0x14003950a  mov     rcx, rbx
0x14003950d  mov     rax, [rax+128h]
0x140039514  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140039519  mov     r15d, eax
0x14003951c  bt      eax, 1Fh
0x140039520  jb      loc_140039D31
0x140039526  cmp     eax, 1
0x140039529  jz      loc_140039D31
0x14003952f  cmp     [rbp+57h+var_90], 0
0x140039534  jz      loc_140039CFC
0x14003953a  lea     rdx, aTL; "T/L"
0x140039541  lea     rcx, [rbp+57h+var_48]; this
0x140039545  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x14003954a  mov     r15d, eax
0x14003954d  test    eax, eax
0x14003954f  jns     short loc_140039583
0x140039551  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x140039555  lea     rax, aCraticketinfoI; "CRATicketInfo::InitializeTicket"
0x14003955c  mov     [rsp+0E0h+var_C0], rax; unsigned __int16 *
0x140039561  mov     r9d, 6Ch ; 'l'; unsigned int
0x140039567  lea     r8, aBaseDiagnosisR_31; "base\\diagnosis\\ra\\racommon\\src\\tic"...
0x14003956e  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140039575  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14003957a  mov     r14, [rbp+57h+var_48]
0x14003957e  jmp     loc_140039D5B
0x140039583  mov     rcx, [rbp+57h+var_90]
0x140039587  mov     rax, [rcx]
0x14003958a  lea     r8, [rbp+57h+var_A0]
0x14003958e  mov     r14, [rbp+57h+var_48]
0x140039592  mov     rdx, r14
0x140039595  mov     rax, [rax+120h]
0x14003959c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400395a1  mov     r15d, eax
0x1400395a4  bt      eax, 1Fh
0x1400395a8  jb      loc_140039CF4
0x1400395ae  cmp     eax, 1
0x1400395b1  jz      loc_140039CF4
0x1400395b7  cmp     [rbp+57h+var_A0], 0
0x1400395bc  jnz     short loc_1400395C9
0x1400395be  mov     r9d, 6Fh ; 'o'
0x1400395c4  jmp     loc_140039D02
0x1400395c9  lea     rdx, aP; "P"
0x1400395d0  lea     rcx, [rbp+57h+var_38]; this
0x1400395d4  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x1400395d9  mov     r15d, eax
0x1400395dc  test    eax, eax
0x1400395de  jns     short loc_1400395EB
0x1400395e0  mov     r9d, 71h ; 'q'
0x1400395e6  jmp     loc_140039D37
0x1400395eb  lea     rdx, aN; "N"
0x1400395f2  lea     rcx, [rbp+57h+bstrString]; this
0x1400395f6  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x1400395fb  mov     r15d, eax
0x1400395fe  test    eax, eax
0x140039600  jns     short loc_14003960D
0x140039602  mov     r9d, 73h ; 's'
0x140039608  jmp     loc_140039D37
0x14003960d  mov     rcx, [rbp+57h+var_A0]
0x140039611  lea     r12, [r13+8]
0x140039615  mov     rax, [rcx]
0x140039618  mov     rdx, r12
0x14003961b  mov     rax, [rax+40h]
0x14003961f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140039624  mov     r15d, eax
0x140039627  test    eax, eax
0x140039629  jns     short loc_140039636
0x14003962b  mov     r9d, 75h ; 'u'
0x140039631  jmp     loc_140039D37
0x140039636  movsxd  r15, dword ptr [r12]
0x14003963a  shl     r15, 3
0x14003963e  call    cs:__imp_GetProcessHeap
0x140039645  nop     dword ptr [rax+rax+00h]
0x14003964a  mov     r8, r15; dwBytes
0x14003964d  mov     edx, 8; dwFlags
0x140039652  mov     rcx, rax; hHeap
0x140039655  call    cs:__imp_HeapAlloc
0x14003965c  nop     dword ptr [rax+rax+00h]
0x140039661  mov     [r13+10h], rax
0x140039665  test    rax, rax
0x140039668  jnz     short loc_140039681
0x14003966a  mov     r15d, 8007000Eh
0x140039670  mov     [rsp+0E0h+var_B8], 8007000Eh
0x140039678  lea     r9d, [rax+7Ah]
0x14003967c  jmp     loc_140039D3B
0x140039681  movsxd  r15, dword ptr [r12]
0x140039685  shl     r15, 3
0x140039689  call    cs:__imp_GetProcessHeap
0x140039690  nop     dword ptr [rax+rax+00h]
0x140039695  mov     r8, r15; dwBytes
0x140039698  mov     edx, 8; dwFlags
0x14003969d  mov     rcx, rax; hHeap
0x1400396a0  call    cs:__imp_HeapAlloc
0x1400396a7  nop     dword ptr [rax+rax+00h]
0x1400396ac  mov     [r13+18h], rax
0x1400396b0  test    rax, rax
0x1400396b3  jnz     short loc_1400396CC
0x1400396b5  mov     r15d, 8007000Eh
0x1400396bb  mov     [rsp+0E0h+var_B8], 8007000Eh
0x1400396c3  lea     r9d, [rax+7Bh]
0x1400396c7  jmp     loc_140039D3B
0x1400396cc  xor     r13d, r13d
0x1400396cf  mov     rcx, [rbp+57h+var_A0]
0x1400396d3  mov     rax, [rcx]
0x1400396d6  lea     rdx, [rbp+57h+var_A8]
0x1400396da  mov     rax, [rax+48h]
0x1400396de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400396e3  mov     r15d, eax
0x1400396e6  test    eax, eax
0x1400396e8  js      loc_140039D5B
0x1400396ee  cmp     [rbp+57h+var_A8], 0
0x1400396f3  jz      loc_140039D5B
0x1400396f9  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1400396fd  call    cs:__imp_VariantInit
0x140039704  nop     dword ptr [rax+rax+00h]
0x140039709  nop
0x14003970a  lea     rcx, [rbp+57h+var_88]; pvarg
0x14003970e  call    cs:__imp_VariantInit
0x140039715  nop     dword ptr [rax+rax+00h]
0x14003971a  nop
0x14003971b  mov     [rbp+57h+arg_10], 0
0x140039723  mov     [rbp+57h+var_B0], 0
0x14003972b  mov     [rbp+57h+arg_18], 0
0x140039733  mov     rcx, [rbp+57h+var_A8]
0x140039737  mov     rax, [rcx]
0x14003973a  lea     rdx, [rbp+57h+arg_10]
0x14003973e  mov     rax, [rax+88h]
0x140039745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003974a  mov     r15d, eax
0x14003974d  test    eax, eax
0x14003974f  js      loc_140039C65
0x140039755  mov     rcx, [rbp+57h+arg_10]
0x140039759  mov     rax, [rcx]
0x14003975c  lea     r8, [rbp+57h+arg_18]
0x140039760  mov     rdx, [rbp+57h+bstrString]
0x140039764  mov     rax, [rax+38h]
0x140039768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003976d  mov     r15d, eax
0x140039770  bt      eax, 1Fh
0x140039774  jb      loc_140039BF7
0x14003977a  cmp     eax, 1
0x14003977d  jz      loc_140039BF7
0x140039783  mov     rcx, [rbp+57h+arg_18]; this
0x140039787  test    rcx, rcx
0x14003978a  jz      loc_140039B7D
0x140039790  mov     rax, [rcx]
0x140039793  lea     rdx, [rbp+57h+var_88]
0x140039797  mov     rax, [rax+40h]
0x14003979b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400397a0  mov     r15d, eax
0x1400397a3  test    eax, eax
0x1400397a5  js      loc_140039B0C
0x1400397ab  mov     rcx, [rbp+57h+arg_10]
0x1400397af  mov     rax, [rcx]
0x1400397b2  lea     r8, [rbp+57h+var_B0]
0x1400397b6  mov     rdx, [rbp+57h+var_38]
0x1400397ba  mov     rax, [rax+38h]
0x1400397be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400397c3  mov     r15d, eax
0x1400397c6  bt      eax, 1Fh
0x1400397ca  jb      loc_140039A9B
0x1400397d0  cmp     eax, 1
0x1400397d3  jz      loc_140039A9B
0x1400397d9  mov     rcx, [rbp+57h+var_B0]; this
0x1400397dd  test    rcx, rcx
0x1400397e0  jz      loc_140039A21
0x1400397e6  mov     rax, [rcx]
0x1400397e9  lea     rdx, [rbp+57h+pvarg]
0x1400397ed  mov     rax, [rax+40h]
0x1400397f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400397f6  mov     r15d, eax
0x1400397f9  test    eax, eax
0x1400397fb  js      loc_1400399B0
0x140039801  movsxd  r12, r13d
0x140039804  mov     rax, [rbp+57h+arg_0]
0x140039808  mov     rax, [rax+10h]
0x14003980c  lea     rdx, [rax+r12*8]; unsigned __int16 **
0x140039810  mov     rcx, qword ptr [rbp+57h+var_88+8]; Src
0x140039814  call    ?DuplicateString@@YAJPEBGPEAPEAG@Z; DuplicateString(ushort const *,ushort * *)
0x140039819  mov     r15d, eax
0x14003981c  test    eax, eax
0x14003981e  js      loc_14003993F
0x140039824  mov     rax, [rbp+57h+arg_0]
0x140039828  mov     rax, [rax+18h]
0x14003982c  lea     rdx, [rax+r12*8]; unsigned __int16 **
0x140039830  mov     rcx, qword ptr [rbp+57h+pvarg+8]; Src
0x140039834  call    ?DuplicateString@@YAJPEBGPEAPEAG@Z; DuplicateString(ushort const *,ushort * *)
0x140039839  mov     r15d, eax
0x14003983c  test    eax, eax
0x14003983e  js      loc_1400398CE
0x140039844  inc     r13d
0x140039847  mov     rcx, [rbp+57h+arg_18]
0x14003984b  test    rcx, rcx
0x14003984e  jz      short loc_14003985D
0x140039850  mov     rax, [rcx]
0x140039853  mov     rax, [rax+10h]
0x140039857  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003985c  nop
0x14003985d  mov     rcx, [rbp+57h+var_B0]
0x140039861  test    rcx, rcx
0x140039864  jz      short loc_140039873
0x140039866  mov     rax, [rcx]
0x140039869  mov     rax, [rax+10h]
0x14003986d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140039872  nop
0x140039873  mov     rcx, [rbp+57h+arg_10]
0x140039877  test    rcx, rcx
0x14003987a  jz      short loc_140039889
0x14003987c  mov     rax, [rcx]
0x14003987f  mov     rax, [rax+10h]
0x140039883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140039888  nop
0x140039889  lea     rcx, [rbp+57h+var_88]; pvarg
0x14003988d  call    cs:__imp_VariantClear
  ... truncated ...
```
