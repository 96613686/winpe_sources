# CRATicketInfo::InitializeTicket(ushort *)

- ea: `0x180015f1c`
- end: `0x180016508`
- name: `?InitializeTicket@CRATicketInfo@@QEAAJPEAG@Z`
- size: `1516`
- prototype: `__int64 __fastcall(unsigned __int16 **this, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010adc`
- `0x1800149bc`

## callees

- `0x180008924`
- `0x180014660`
- `0x180014da0`
- `0x180015510`
- `0x180015d1c`
- `0x180015f1c`
- `0x18001c010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180016493`
- `OLEAUT32!__imp_SysFreeString` at `0x18001649e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800164a8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800164b2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800164bc`
- `OLEAUT32!__imp_SysFreeString` at `0x180016493`
- `OLEAUT32!__imp_SysFreeString` at `0x18001649e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800164a8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800164b2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800164bc`
- `OLEAUT32!__imp_VariantInit` at `0x18001620a`
- `OLEAUT32!__imp_VariantInit` at `0x180016215`
- `OLEAUT32!__imp_VariantInit` at `0x18001620a`
- `OLEAUT32!__imp_VariantInit` at `0x180016215`
- `OLEAUT32!__imp_VariantClear` at `0x18001634d`
- `OLEAUT32!__imp_VariantClear` at `0x180016358`
- `OLEAUT32!__imp_VariantClear` at `0x180016426`
- `OLEAUT32!__imp_VariantClear` at `0x180016431`
- `OLEAUT32!__imp_VariantClear` at `0x18001634d`
- `OLEAUT32!__imp_VariantClear` at `0x180016358`
- `OLEAUT32!__imp_VariantClear` at `0x180016426`
- `OLEAUT32!__imp_VariantClear` at `0x180016431`
- `KERNEL32!GetProcessHeap` at `0x180016165`
- `KERNEL32!GetProcessHeap` at `0x1800161a3`
- `KERNEL32!GetProcessHeap` at `0x180016165`
- `KERNEL32!GetProcessHeap` at `0x1800161a3`
- `KERNEL32!HeapAlloc` at `0x180016176`
- `KERNEL32!HeapAlloc` at `0x1800161b4`
- `KERNEL32!HeapAlloc` at `0x180016176`
- `KERNEL32!HeapAlloc` at `0x1800161b4`

## string_xrefs

- `0x180015fb3`: `base\diagnosis\ra\racommon\src\ticketinfo.cpp`
- `0x180016017`: `base\diagnosis\ra\racommon\src\ticketinfo.cpp`
- `0x180016097`: `base\diagnosis\ra\racommon\src\ticketinfo.cpp`
- `0x1800163c5`: `base\diagnosis\ra\racommon\src\ticketinfo.cpp`
- `0x1800163f7`: `base\diagnosis\ra\racommon\src\ticketinfo.cpp`
- `0x180016458`: `base\diagnosis\ra\racommon\src\ticketinfo.cpp`
- `0x180016482`: `base\diagnosis\ra\racommon\src\ticketinfo.cpp`

## pseudocode

```c
__int64 __fastcall CRATicketInfo::InitializeTicket(unsigned __int16 **this, unsigned __int16 *a2)
{
  int v4; // r12d
  OLECHAR *v5; // rbx
  OLECHAR *v6; // rdi
  OLECHAR *v7; // rsi
  signed int inited; // eax
  const struct _EVENT_DESCRIPTOR *v9; // rdx
  CEventLogger *v10; // rcx
  int v11; // r14d
  unsigned int v12; // r9d
  signed int v13; // eax
  const struct _EVENT_DESCRIPTOR *v14; // rdx
  CEventLogger *v15; // rcx
  signed int v16; // eax
  const struct _EVENT_DESCRIPTOR *v17; // rdx
  CEventLogger *v18; // rcx
  signed int v19; // eax
  const struct _EVENT_DESCRIPTOR *v20; // rdx
  CEventLogger *v21; // rcx
  unsigned int v22; // r9d
  unsigned __int16 **v23; // r15
  SIZE_T v24; // r14
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v26; // rax
  const struct _EVENT_DESCRIPTOR *v27; // rdx
  CEventLogger *v28; // rcx
  SIZE_T v29; // r14
  HANDLE v30; // rax
  unsigned __int16 *v31; // rax
  const struct _EVENT_DESCRIPTOR *v32; // rdx
  CEventLogger *v33; // rcx
  signed int v34; // eax
  const struct _EVENT_DESCRIPTOR *v35; // rdx
  CEventLogger *v36; // rcx
  __int64 v37; // rcx
  unsigned int v38; // r9d
  unsigned int v39; // r9d
  __int64 v41; // [rsp+30h] [rbp-59h] BYREF
  __int64 v42; // [rsp+38h] [rbp-51h] BYREF
  __int64 v43; // [rsp+40h] [rbp-49h] BYREF
  VARIANTARG v44; // [rsp+48h] [rbp-41h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp-29h] BYREF
  BSTR v46; // [rsp+78h] [rbp-11h] BYREF
  OLECHAR *v47; // [rsp+80h] [rbp-9h] BYREF
  OLECHAR *v48; // [rsp+88h] [rbp-1h] BYREF
  BSTR bstrString; // [rsp+90h] [rbp+7h] BYREF
  BSTR v50; // [rsp+98h] [rbp+Fh] BYREF
  struct IXMLDOMDocument2 *v51[8]; // [rsp+A0h] [rbp+17h] BYREF
  __int64 v52; // [rsp+F0h] [rbp+67h] BYREF
  CEventLogger *v53; // [rsp+100h] [rbp+77h] BYREF
  __int64 v54; // [rsp+108h] [rbp+7Fh] BYREF

  v4 = 0;
  v51[0] = 0;
  v43 = 0;
  v42 = 0;
  v41 = 0;
  v5 = 0;
  v46 = 0;
  v6 = 0;
  v47 = 0;
  v7 = 0;
  v48 = 0;
  v50 = 0;
  bstrString = 0;
  inited = DuplicateString(a2, this);
  v11 = inited;
  if ( inited < 0 )
  {
    v12 = 95;
LABEL_60:
    CEventLogger::LogError(
      v10,
      v9,
      L"base\\diagnosis\\ra\\racommon\\src\\ticketinfo.cpp",
      v12,
      L"CRATicketInfo::InitializeTicket",
      inited);
    goto LABEL_61;
  }
  v13 = ATL::CComBSTR::Append((ATL::CComBSTR *)&v46, a2);
  v11 = v13;
  if ( v13 < 0 )
  {
    CEventLogger::LogError(
      v15,
      v14,
      L"base\\diagnosis\\ra\\racommon\\src\\ticketinfo.cpp",
      0x62u,
      L"CRATicketInfo::InitializeTicket",
      v13);
    v5 = v46;
    goto LABEL_61;
  }
  v5 = v46;
  inited = InitXMLDocWithString(v46, v51);
  v11 = inited;
  if ( inited < 0 )
  {
    v12 = 101;
    goto LABEL_60;
  }
  v16 = ATL::CComBSTR::Append((ATL::CComBSTR *)&v47, L"E/C");
  v11 = v16;
  if ( v16 < 0 )
  {
    CEventLogger::LogError(
      v18,
      v17,
      L"base\\diagnosis\\ra\\racommon\\src\\ticketinfo.cpp",
      0x67u,
      L"CRATicketInfo::InitializeTicket",
      v16);
    v6 = v47;
    goto LABEL_61;
  }
  v6 = v47;
  inited = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, OLECHAR *, __int64 *))v51[0]->lpVtbl->selectSingleNode)(
             v51[0],
             v47,
             &v43);
  v11 = inited;
  if ( inited < 0 || inited == 1 )
  {
    v12 = 105;
    goto LABEL_60;
  }
  if ( !v43 )
  {
    v22 = 106;
    goto LABEL_58;
  }
  v19 = ATL::CComBSTR::Append((ATL::CComBSTR *)&v48, L"T/L");
  v11 = v19;
  if ( v19 < 0 )
  {
    CEventLogger::LogError(
      v21,
      v20,
      L"base\\diagnosis\\ra\\racommon\\src\\ticketinfo.cpp",
      0x6Cu,
      L"CRATicketInfo::InitializeTicket",
      v19);
    v7 = v48;
    goto LABEL_61;
  }
  v7 = v48;
  inited = (*(__int64 (__fastcall **)(__int64, OLECHAR *, __int64 *))(*(_QWORD *)v43 + 288LL))(v43, v48, &v42);
  v11 = inited;
  if ( inited < 0 || inited == 1 )
  {
    v12 = 110;
    goto LABEL_60;
  }
  if ( !v42 )
  {
    v22 = 111;
LABEL_58:
    CEventLogger::LogError(
      v10,
      v9,
      L"base\\diagnosis\\ra\\racommon\\src\\ticketinfo.cpp",
      v22,
      L"CRATicketInfo::InitializeTicket",
      0);
    v11 = -2147467259;
    goto LABEL_61;
  }
  inited = ATL::CComBSTR::Append((ATL::CComBSTR *)&v50, L"P");
  v11 = inited;
  if ( inited < 0 )
  {
    v12 = 113;
    goto LABEL_60;
  }
  inited = ATL::CComBSTR::Append((ATL::CComBSTR *)&bstrString, L"N");
  v11 = inited;
  if ( inited < 0 )
  {
    v12 = 115;
    goto LABEL_60;
  }
  v23 = this + 1;
  inited = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v42 + 64LL))(v42, this + 1);
  v11 = inited;
  if ( inited < 0 )
  {
    v12 = 117;
    goto LABEL_60;
  }
  v24 = 8LL * *(int *)v23;
  ProcessHeap = GetProcessHeap();
  v26 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, v24);
  this[2] = v26;
  if ( v26 )
  {
    v29 = 8LL * *(int *)v23;
    v30 = GetProcessHeap();
    v31 = (unsigned __int16 *)HeapAlloc(v30, 8u, v29);
    this[3] = v31;
    if ( v31 )
    {
      while ( 1 )
      {
        v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v42 + 72LL))(v42, &v41);
        if ( v11 < 0 || !v41 )
          goto LABEL_61;
        VariantInit(&pvarg);
        VariantInit(&v44);
        v52 = 0;
        v54 = 0;
        v53 = 0;
        v34 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v41 + 136LL))(v41, &v52);
        v11 = v34;
        if ( v34 < 0 )
          break;
        v34 = (*(__int64 (__fastcall **)(__int64, BSTR, CEventLogger **))(*(_QWORD *)v52 + 56LL))(v52, bstrString, &v53);
        v11 = v34;
        if ( v34 < 0 || v34 == 1 )
        {
          v38 = 138;
          goto LABEL_54;
        }
        if ( !v53 )
        {
          v39 = 139;
LABEL_51:
          CEventLogger::LogError(
            0,
            v35,
            L"base\\diagnosis\\ra\\racommon\\src\\ticketinfo.cpp",
            v39,
            L"CRATicketInfo::InitializeTicket",
            0);
          v11 = -2147467259;
          goto LABEL_55;
        }
        v34 = (*(__int64 (__fastcall **)(CEventLogger *, VARIANTARG *))(*(_QWORD *)v53 + 64LL))(v53, &v44);
        v11 = v34;
        if ( v34 < 0 )
        {
          v38 = 141;
          goto LABEL_54;
        }
        v34 = (*(__int64 (__fastcall **)(__int64, BSTR, __int64 *))(*(_QWORD *)v52 + 56LL))(v52, v50, &v54);
        v11 = v34;
        if ( v34 < 0 || v34 == 1 )
        {
          v38 = 143;
          goto LABEL_54;
        }
        if ( !v54 )
        {
          v39 = 144;
          goto LABEL_51;
        }
        v34 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v54 + 64LL))(v54, &pvarg);
        v11 = v34;
        if ( v34 < 0 )
        {
          v38 = 146;
          goto LABEL_54;
        }
        v34 = DuplicateString(v44.bstrVal, (unsigned __int16 **)&this[2][4 * v4]);
        v11 = v34;
        if ( v34 < 0 )
        {
          v38 = 149;
          goto LABEL_54;
        }
        v34 = DuplicateString(pvarg.bstrVal, (unsigned __int16 **)&this[3][4 * v4]);
        v11 = v34;
        if ( v34 < 0 )
        {
          v38 = 152;
          goto LABEL_54;
        }
        ++v4;
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v53);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v54);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v52);
        VariantClear(&v44);
        VariantClear(&pvarg);
        v37 = v41;
        if ( v41 )
        {
          v41 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
        }
      }
      v38 = 136;
LABEL_54:
      CEventLogger::LogError(
        v36,
        v35,
        L"base\\diagnosis\\ra\\racommon\\src\\ticketinfo.cpp",
        v38,
        L"CRATicketInfo::InitializeTicket",
        v34);
LABEL_55:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v53);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v54);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v52);
      VariantClear(&v44);
      VariantClear(&pvarg);
      goto LABEL_61;
    }
    v11 = -2147024882;
    CEventLogger::LogError(
      v33,
      v32,
      L"base\\diagnosis\\ra\\racommon\\src\\ticketinfo.cpp",
      0x7Bu,
      L"CRATicketInfo::InitializeTicket",
      0x8007000E);
  }
  else
  {
    v11 = -2147024882;
    CEventLogger::LogError(
      v28,
      v27,
      L"base\\diagnosis\\ra\\racommon\\src\\ticketinfo.cpp",
      0x7Au,
      L"CRATicketInfo::InitializeTicket",
      0x8007000E);
  }
LABEL_61:
  SysFreeString(bstrString);
  SysFreeString(v50);
  SysFreeString(v7);
  SysFreeString(v6);
  SysFreeString(v5);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v42);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v43);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)v51);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180015f1c  mov     [rsp-8+arg_8], rbx
0x180015f21  push    rbp
0x180015f22  push    rsi
0x180015f23  push    rdi
0x180015f24  push    r12
0x180015f26  push    r13
0x180015f28  push    r14
0x180015f2a  push    r15
0x180015f2c  lea     rbp, [rsp-27h]
0x180015f31  sub     rsp, 0B0h
0x180015f38  mov     r15, rdx
0x180015f3b  mov     r13, rcx
0x180015f3e  xor     r12d, r12d
0x180015f41  mov     [rbp+57h+var_40], r12
0x180015f45  mov     [rbp+57h+var_A0], r12
0x180015f49  mov     [rbp+57h+var_A8], r12
0x180015f4d  mov     [rbp+57h+var_B0], r12
0x180015f51  mov     ebx, r12d
0x180015f54  mov     [rbp+57h+var_68], rbx
0x180015f58  mov     edi, r12d
0x180015f5b  mov     [rbp+57h+var_60], r12
0x180015f5f  mov     esi, r12d
0x180015f62  mov     [rbp+57h+var_58], r12
0x180015f66  mov     [rbp+57h+var_48], r12
0x180015f6a  mov     [rbp+57h+bstrString], r12
0x180015f6e  mov     rdx, rcx; unsigned __int16 **
0x180015f71  mov     rcx, r15; Src
0x180015f74  call    ?DuplicateString@@YAJPEBGPEAPEAG@Z; DuplicateString(ushort const *,ushort * *)
0x180015f79  mov     r14d, eax
0x180015f7c  test    eax, eax
0x180015f7e  jns     short loc_180015F8A
0x180015f80  lea     r9d, [r12+5Fh]
0x180015f85  jmp     loc_180016472
0x180015f8a  mov     rdx, r15; unsigned __int16 *
0x180015f8d  lea     rcx, [rbp+57h+var_68]; this
0x180015f91  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x180015f96  mov     r14d, eax
0x180015f99  test    eax, eax
0x180015f9b  jns     short loc_180015FC8
0x180015f9d  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x180015fa1  lea     rax, aCraticketinfoI; "CRATicketInfo::InitializeTicket"
0x180015fa8  mov     [rsp+0E0h+var_C0], rax; unsigned __int16 *
0x180015fad  mov     r9d, 62h ; 'b'; unsigned int
0x180015fb3  lea     r8, aBaseDiagnosisR_8; "base\\diagnosis\\ra\\racommon\\src\\tic"...
0x180015fba  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x180015fbf  mov     rbx, [rbp+57h+var_68]
0x180015fc3  jmp     loc_18001648F
0x180015fc8  lea     rdx, [rbp+57h+var_40]; struct IXMLDOMDocument2 **
0x180015fcc  mov     rbx, [rbp+57h+var_68]
0x180015fd0  mov     rcx, rbx; unsigned __int16 *
0x180015fd3  call    ?InitXMLDocWithString@@YAJQEAGPEAPEAUIXMLDOMDocument2@@@Z; InitXMLDocWithString(ushort * const,IXMLDOMDocument2 * *)
0x180015fd8  mov     r14d, eax
0x180015fdb  test    eax, eax
0x180015fdd  jns     short loc_180015FEA
0x180015fdf  mov     r9d, 65h ; 'e'
0x180015fe5  jmp     loc_180016472
0x180015fea  lea     rdx, aEC; "E/C"
0x180015ff1  lea     rcx, [rbp+57h+var_60]; this
0x180015ff5  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x180015ffa  mov     r14d, eax
0x180015ffd  test    eax, eax
0x180015fff  jns     short loc_18001602C
0x180016001  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x180016005  lea     rax, aCraticketinfoI; "CRATicketInfo::InitializeTicket"
0x18001600c  mov     [rsp+0E0h+var_C0], rax; unsigned __int16 *
0x180016011  mov     r9d, 67h ; 'g'; unsigned int
0x180016017  lea     r8, aBaseDiagnosisR_8; "base\\diagnosis\\ra\\racommon\\src\\tic"...
0x18001601e  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x180016023  mov     rdi, [rbp+57h+var_60]
0x180016027  jmp     loc_18001648F
0x18001602c  mov     rcx, [rbp+57h+var_40]
0x180016030  mov     rax, [rcx]
0x180016033  lea     r8, [rbp+57h+var_A0]
0x180016037  mov     rdi, [rbp+57h+var_60]
0x18001603b  mov     rdx, rdi
0x18001603e  mov     rax, [rax+128h]
0x180016045  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001604a  mov     r14d, eax
0x18001604d  bt      eax, 1Fh
0x180016051  jb      loc_18001646C
0x180016057  cmp     eax, 1
0x18001605a  jz      loc_18001646C
0x180016060  cmp     [rbp+57h+var_A0], r12
0x180016064  jz      loc_180016441
0x18001606a  lea     rdx, aTL; "T/L"
0x180016071  lea     rcx, [rbp+57h+var_58]; this
0x180016075  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x18001607a  mov     r14d, eax
0x18001607d  test    eax, eax
0x18001607f  jns     short loc_1800160AC
0x180016081  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x180016085  lea     rax, aCraticketinfoI; "CRATicketInfo::InitializeTicket"
0x18001608c  mov     [rsp+0E0h+var_C0], rax; unsigned __int16 *
0x180016091  mov     r9d, 6Ch ; 'l'; unsigned int
0x180016097  lea     r8, aBaseDiagnosisR_8; "base\\diagnosis\\ra\\racommon\\src\\tic"...
0x18001609e  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1800160a3  mov     rsi, [rbp+57h+var_58]
0x1800160a7  jmp     loc_18001648F
0x1800160ac  mov     rcx, [rbp+57h+var_A0]
0x1800160b0  mov     rax, [rcx]
0x1800160b3  lea     r8, [rbp+57h+var_A8]
0x1800160b7  mov     rsi, [rbp+57h+var_58]
0x1800160bb  mov     rdx, rsi
0x1800160be  mov     rax, [rax+120h]
0x1800160c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160ca  mov     r14d, eax
0x1800160cd  bt      eax, 1Fh
0x1800160d1  jb      loc_180016439
0x1800160d7  cmp     eax, 1
0x1800160da  jz      loc_180016439
0x1800160e0  cmp     [rbp+57h+var_A8], r12
0x1800160e4  jnz     short loc_1800160F1
0x1800160e6  mov     r9d, 6Fh ; 'o'
0x1800160ec  jmp     loc_180016447
0x1800160f1  lea     rdx, aP; "P"
0x1800160f8  lea     rcx, [rbp+57h+var_48]; this
0x1800160fc  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x180016101  mov     r14d, eax
0x180016104  test    eax, eax
0x180016106  jns     short loc_180016113
0x180016108  mov     r9d, 71h ; 'q'
0x18001610e  jmp     loc_180016472
0x180016113  lea     rdx, aN; "N"
0x18001611a  lea     rcx, [rbp+57h+bstrString]; this
0x18001611e  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x180016123  mov     r14d, eax
0x180016126  test    eax, eax
0x180016128  jns     short loc_180016135
0x18001612a  mov     r9d, 73h ; 's'
0x180016130  jmp     loc_180016472
0x180016135  mov     rcx, [rbp+57h+var_A8]
0x180016139  lea     r15, [r13+8]
0x18001613d  mov     rax, [rcx]
0x180016140  mov     rdx, r15
0x180016143  mov     rax, [rax+40h]
0x180016147  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001614c  mov     r14d, eax
0x18001614f  test    eax, eax
0x180016151  jns     short loc_18001615E
0x180016153  mov     r9d, 75h ; 'u'
0x180016159  jmp     loc_180016472
0x18001615e  movsxd  r14, dword ptr [r15]
0x180016161  shl     r14, 3
0x180016165  call    cs:__imp_GetProcessHeap
0x18001616b  mov     r8, r14; dwBytes
0x18001616e  mov     edx, 8; dwFlags
0x180016173  mov     rcx, rax; hHeap
0x180016176  call    cs:__imp_HeapAlloc
0x18001617c  mov     [r13+10h], rax
0x180016180  test    rax, rax
0x180016183  jnz     short loc_18001619C
0x180016185  mov     r14d, 8007000Eh
0x18001618b  mov     [rsp+0E0h+var_B8], 8007000Eh
0x180016193  lea     r9d, [rax+7Ah]
0x180016197  jmp     loc_180016476
0x18001619c  movsxd  r14, dword ptr [r15]
0x18001619f  shl     r14, 3
0x1800161a3  call    cs:__imp_GetProcessHeap
0x1800161a9  mov     r8, r14; dwBytes
0x1800161ac  mov     edx, 8; dwFlags
0x1800161b1  mov     rcx, rax; hHeap
0x1800161b4  call    cs:__imp_HeapAlloc
0x1800161ba  mov     [r13+18h], rax
0x1800161be  test    rax, rax
0x1800161c1  jnz     short loc_1800161DA
0x1800161c3  mov     r14d, 8007000Eh
0x1800161c9  mov     [rsp+0E0h+var_B8], 8007000Eh
0x1800161d1  lea     r9d, [rax+7Bh]
0x1800161d5  jmp     loc_180016476
0x1800161da  xor     r15d, r15d
0x1800161dd  mov     rcx, [rbp+57h+var_A8]
0x1800161e1  mov     rax, [rcx]
0x1800161e4  lea     rdx, [rbp+57h+var_B0]
0x1800161e8  mov     rax, [rax+48h]
0x1800161ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800161f1  mov     r14d, eax
0x1800161f4  test    eax, eax
0x1800161f6  js      loc_18001648F
0x1800161fc  cmp     [rbp+57h+var_B0], r15
0x180016200  jz      loc_18001648F
0x180016206  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001620a  call    cs:__imp_VariantInit
0x180016210  nop
0x180016211  lea     rcx, [rbp+57h+var_98]; pvarg
0x180016215  call    cs:__imp_VariantInit
0x18001621b  nop
0x18001621c  mov     [rbp+57h+arg_0], r15
0x180016220  mov     [rbp+57h+arg_18], r15
0x180016224  mov     [rbp+57h+arg_10], r15
0x180016228  mov     rcx, [rbp+57h+var_B0]
0x18001622c  mov     rax, [rcx]
0x18001622f  lea     rdx, [rbp+57h+arg_0]
0x180016233  mov     rax, [rax+88h]
0x18001623a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001623f  mov     r14d, eax
0x180016242  test    eax, eax
0x180016244  js      loc_1800163E1
0x18001624a  mov     rcx, [rbp+57h+arg_0]
0x18001624e  mov     rax, [rcx]
0x180016251  lea     r8, [rbp+57h+arg_10]
0x180016255  mov     rdx, [rbp+57h+bstrString]
0x180016259  mov     rax, [rax+38h]
0x18001625d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016262  mov     r14d, eax
0x180016265  test    eax, eax
0x180016267  js      loc_1800163D9
0x18001626d  cmp     eax, 1
0x180016270  jz      loc_1800163D9
0x180016276  mov     rcx, [rbp+57h+arg_10]; this
0x18001627a  test    rcx, rcx
0x18001627d  jz      loc_1800163AE
0x180016283  mov     rax, [rcx]
0x180016286  lea     rdx, [rbp+57h+var_98]
0x18001628a  mov     rax, [rax+40h]
0x18001628e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016293  mov     r14d, eax
0x180016296  test    eax, eax
0x180016298  js      loc_1800163A6
0x18001629e  mov     rcx, [rbp+57h+arg_0]
0x1800162a2  mov     rax, [rcx]
0x1800162a5  lea     r8, [rbp+57h+arg_18]
0x1800162a9  mov     rdx, [rbp+57h+var_48]
0x1800162ad  mov     rax, [rax+38h]
0x1800162b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800162b6  mov     r14d, eax
0x1800162b9  test    eax, eax
0x1800162bb  js      loc_18001639E
0x1800162c1  cmp     eax, 1
0x1800162c4  jz      loc_18001639E
0x1800162ca  mov     rcx, [rbp+57h+arg_18]
0x1800162ce  test    rcx, rcx
0x1800162d1  jz      loc_180016396
0x1800162d7  mov     rax, [rcx]
0x1800162da  lea     rdx, [rbp+57h+pvarg]
0x1800162de  mov     rax, [rax+40h]
0x1800162e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800162e7  mov     r14d, eax
0x1800162ea  test    eax, eax
0x1800162ec  js      loc_18001638E
0x1800162f2  movsxd  r15, r12d
0x1800162f5  mov     rax, [r13+10h]
0x1800162f9  lea     rdx, [rax+r15*8]; unsigned __int16 **
0x1800162fd  mov     rcx, qword ptr [rbp+57h+var_98+8]; Src
0x180016301  call    ?DuplicateString@@YAJPEBGPEAPEAG@Z; DuplicateString(ushort const *,ushort * *)
0x180016306  mov     r14d, eax
0x180016309  test    eax, eax
0x18001630b  js      short loc_180016386
0x18001630d  mov     rax, [r13+18h]
0x180016311  lea     rdx, [rax+r15*8]; unsigned __int16 **
0x180016315  mov     rcx, qword ptr [rbp+57h+pvarg+8]; Src
0x180016319  call    ?DuplicateString@@YAJPEBGPEAPEAG@Z; DuplicateString(ushort const *,ushort * *)
0x18001631e  mov     r14d, eax
0x180016321  xor     r15d, r15d
0x180016324  test    eax, eax
0x180016326  js      short loc_18001637E
0x180016328  inc     r12d
0x18001632b  lea     rcx, [rbp+57h+arg_10]
0x18001632f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180016334  nop
0x180016335  lea     rcx, [rbp+57h+arg_18]
0x180016339  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001633e  nop
0x18001633f  lea     rcx, [rbp+57h+arg_0]
0x180016343  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180016348  nop
0x180016349  lea     rcx, [rbp+57h+var_98]; pvarg
0x18001634d  call    cs:__imp_VariantClear
0x180016353  nop
0x180016354  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180016358  call    cs:__imp_VariantClear
0x18001635e  nop
0x18001635f  mov     rcx, [rbp+57h+var_B0]
0x180016363  test    rcx, rcx
0x180016366  jz      short loc_180016379
0x180016368  mov     [rbp+57h+var_B0], r15
0x18001636c  mov     rax, [rcx]
0x18001636f  mov     rax, [rax+10h]
0x180016373  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016378  nop
0x180016379  jmp     loc_1800161DD
0x18001637e  mov     r9d, 98h
0x180016384  jmp     short loc_1800163E7
0x180016386  mov     r9d, 95h
0x18001638c  jmp     short loc_1800163E7
0x18001638e  mov     r9d, 92h
0x180016394  jmp     short loc_1800163E7
0x180016396  mov     r9d, 90h
0x18001639c  jmp     short loc_1800163B4
0x18001639e  mov     r9d, 8Fh
0x1800163a4  jmp     short loc_1800163E7
0x1800163a6  mov     r9d, 8Dh
0x1800163ac  jmp     short loc_1800163E7
0x1800163ae  mov     r9d, 8Bh; unsigned int
0x1800163b4  mov     [rsp+0E0h+var_B8], r15d; unsigned int
0x1800163b9  lea     rax, aCraticketinfoI; "CRATicketInfo::InitializeTicket"
0x1800163c0  mov     [rsp+0E0h+var_C0], rax; unsigned __int16 *
0x1800163c5  lea     r8, aBaseDiagnosisR_8; "base\\diagnosis\\ra\\racommon\\src\\tic"...
0x1800163cc  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1800163d1  mov     r14d, 80004005h
0x1800163d7  jmp     short loc_180016404
  ... truncated ...
```
