# CDSLObject::PromptEdit(IDispatch * *,short *)

- ea: `0x180049330`
- end: `0x180049a41`
- name: `?PromptEdit@CDSLObject@@UEAAJPEAPEAUIDispatch@@PEAF@Z`
- size: `1809`
- prototype: `__int64 __fastcall(CDSLObject *__hidden this, struct IDispatch **, __int16 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180013870`
- `0x180026940`
- `0x18002ec0c`
- `0x18004931c`
- `0x180049330`
- `0x180049e74`
- `0x180059100`
- `0x18005989c`
- `0x180087010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18004965a`
- `OLEAUT32!__imp_SysAllocString` at `0x18004965a`
- `OLEAUT32!__imp_SysFreeString` at `0x180049534`
- `OLEAUT32!__imp_SysFreeString` at `0x1800496a0`
- `OLEAUT32!__imp_SysFreeString` at `0x180049534`
- `OLEAUT32!__imp_SysFreeString` at `0x1800496a0`
- `USER32!SetCursor` at `0x1800496f1`
- `USER32!SetCursor` at `0x1800496f1`
- `ole32!CoTaskMemFree` at `0x1800496d4`
- `ole32!CoTaskMemFree` at `0x1800496d4`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CDSLObject::PromptEdit(CDSLObject *this, struct IDispatch **a2, __int16 *a3)
{
  __int64 v6; // rcx
  int v8; // eax
  unsigned int v9; // esi
  int v10; // eax
  unsigned int v11; // esi
  int v12; // eax
  unsigned int v13; // esi
  int v14; // eax
  unsigned int v15; // esi
  char *v16; // r15
  char *v17; // r14
  int v18; // eax
  unsigned int v19; // esi
  unsigned int v20; // esi
  int v21; // eax
  __int64 v22; // r8
  int v23; // esi
  int v24; // eax
  unsigned int v25; // esi
  int v26; // eax
  unsigned int v27; // esi
  OLECHAR *v28; // rbx
  int v29; // eax
  unsigned int v30; // esi
  int v31; // ecx
  int v32; // [rsp+20h] [rbp-C8h]
  __int64 v33; // [rsp+50h] [rbp-98h] BYREF
  __int64 v34; // [rsp+58h] [rbp-90h] BYREF
  __int64 v35; // [rsp+60h] [rbp-88h] BYREF
  OLECHAR *psz; // [rsp+68h] [rbp-80h] BYREF
  BSTR bstrString; // [rsp+70h] [rbp-78h] BYREF
  int pExceptionObject; // [rsp+78h] [rbp-70h] BYREF
  int v39; // [rsp+7Ch] [rbp-6Ch] BYREF
  int v40; // [rsp+80h] [rbp-68h] BYREF
  int v41; // [rsp+84h] [rbp-64h] BYREF
  int v42; // [rsp+88h] [rbp-60h] BYREF
  int v43; // [rsp+8Ch] [rbp-5Ch] BYREF
  int v44; // [rsp+90h] [rbp-58h] BYREF
  int v45; // [rsp+94h] [rbp-54h] BYREF
  int v46; // [rsp+98h] [rbp-50h] BYREF
  __int64 v47; // [rsp+A0h] [rbp-48h] BYREF
  int v48; // [rsp+A8h] [rbp-40h] BYREF
  HCURSOR hCursor; // [rsp+B0h] [rbp-38h] BYREF
  char v50; // [rsp+B8h] [rbp-30h]
  int v52; // [rsp+108h] [rbp+20h]

  if ( !a3 )
  {
    if ( (bidGblFlags & 2) != 0 )
      OLEDBTraceErr(-2147024809, L"<CDSLObject::PromptEdit|OLEDB|ERR> ", 0x9Bu);
    v6 = 110;
LABEL_5:
    DSLUtils::SetErrorInfo(
      (DSLUtils *)v6,
      (unsigned int)a2,
      (unsigned int)&IID_IDataSourceLocator,
      (const struct _GUID *)0x80070057LL,
      v32);
    return 2147942487LL;
  }
  if ( !a2 )
  {
    if ( (bidGblFlags & 2) != 0 )
      OLEDBTraceErr(-2147024809, L"<CDSLObject::PromptEdit|OLEDB|ERR> ", 0xA0u);
    v6 = 105;
    goto LABEL_5;
  }
  if ( !*a2 )
  {
    if ( (bidGblFlags & 2) != 0 )
      OLEDBTraceErr(-2147024809, L"<CDSLObject::PromptEdit|OLEDB|ERR> ", 0xA6u);
    v6 = 111;
    goto LABEL_5;
  }
  DSLUtils::WaitCursor::WaitCursor((DSLUtils::WaitCursor *)&hCursor, 1);
  try
  {
    *a3 = 0;
    psz = 0;
    v34 = 0;
    v8 = ((__int64 (__fastcall *)(_QWORD, GUID *, __int64 *))(*a2)->lpVtbl->QueryInterface)(
           *a2,
           &IID_IADOConnectionConstruction,
           &v34);
    v9 = v8;
    if ( v8 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
        OLEDBTraceErr(v8, L"<CDSLObject::PromptEdit|OLEDB|ERR> ", 0xB7u);
      pExceptionObject = anonymous_namespace_::SetErrorInfo_0(111, 2147942487LL, v9);
      throw (long *)&pExceptionObject;
    }
    v33 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v34 + 24LL))(v34, &v33);
    v11 = v10;
    if ( v10 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
        OLEDBTraceErr(v10, L"<CDSLObject::PromptEdit|OLEDB|ERR> ", 0xC0u);
      DSLUtils::auto_IF<IDBInitialize>::operator IDBInitialize *(&v34);
      v39 = anonymous_namespace_::SetErrorInfo_0(113, 2147942487LL, v11);
      throw (long *)&v39;
    }
    if ( v33 )
    {
      v20 = 18;
      v17 = (char *)this - 48;
      v16 = (char *)this - 40;
    }
    else
    {
      v35 = 0;
      v12 = ((__int64 (__fastcall *)(_QWORD, GUID *, __int64 *))(*a2)->lpVtbl->QueryInterface)(
              *a2,
              &IID_IADOConnection,
              &v35);
      v13 = v12;
      if ( v12 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
          OLEDBTraceErr(v12, L"<CDSLObject::PromptEdit|OLEDB|ERR> ", 0xCDu);
        v40 = anonymous_namespace_::SetErrorInfo_0(111, 2147942487LL, v13);
        throw (long *)&v40;
      }
      bstrString = 0;
      v14 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v35 + 64LL))(v35, &bstrString);
      v15 = v14;
      if ( v14 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
          OLEDBTraceErr(v14, L"<CDSLObject::PromptEdit|OLEDB|ERR> ", 0xD5u);
        DSLUtils::auto_IF<IDBInitialize>::operator IDBInitialize *(&v35);
        v41 = anonymous_namespace_::SetErrorInfo_0(111, 2147942487LL, v15);
        throw (long *)&v41;
      }
      v16 = (char *)this - 40;
      v17 = (char *)this - 48;
      v18 = (*(__int64 (__fastcall **)(char *, _QWORD, __int64, BSTR, GUID *, __int64 *))(*((_QWORD *)this - 5) + 24LL))(
              (char *)this - 40,
              0,
              23,
              bstrString,
              &IID_IUnknown,
              &v33);
      v19 = v18;
      if ( v18 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
          OLEDBTraceErr(v18, L"<CDSLObject::PromptEdit|OLEDB|ERR> ", 0xDBu);
        v42 = anonymous_namespace_::SetErrorInfo_0(107, v19, v19);
        throw (long *)&v42;
      }
      v20 = 2;
      SysFreeString(bstrString);
      ATL::CComPtr<IRowsetChange>::~CComPtr<IRowsetChange>(&v35);
    }
    v21 = (*(__int64 (__fastcall **)(char *, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, GUID *, __int64 *))(*(_QWORD *)v17 + 24LL))(
            v17,
            0,
            *((_QWORD *)this + 127),
            v20,
            0,
            0,
            0,
            &IID_IUnknown,
            &v33);
    v23 = v21;
    if ( v21 >= 0 )
    {
      LOBYTE(v22) = 1;
      v24 = (*(__int64 (__fastcall **)(char *, __int64, __int64, OLECHAR **))(*(_QWORD *)v16 + 32LL))(
              v16,
              v33,
              v22,
              &psz);
      v25 = v24;
      if ( v24 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
          OLEDBTraceErr(v24, L"<CDSLObject::PromptEdit|OLEDB|ERR> ", 0xF8u);
        v44 = anonymous_namespace_::SetErrorInfo_0(107, v25, v25);
        throw (long *)&v44;
      }
      v47 = 0;
      v26 = ((__int64 (__fastcall *)(_QWORD, GUID *, __int64 *))(*a2)->lpVtbl->QueryInterface)(
              *a2,
              &IID_IADOConnection,
              &v47);
      v27 = v26;
      if ( v26 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
          OLEDBTraceErr(v26, L"<CDSLObject::PromptEdit|OLEDB|ERR> ", 0x101u);
        v45 = anonymous_namespace_::SetErrorInfo_0(109, 2147942487LL, v27);
        throw (long *)&v45;
      }
      v28 = SysAllocString(psz);
      bstrString = v28;
      v29 = (*(__int64 (__fastcall **)(__int64, OLECHAR *))(*(_QWORD *)v47 + 72LL))(v47, v28);
      v30 = v29;
      v52 = v29;
      if ( v29 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
          OLEDBTraceErr(v29, L"<CDSLObject::PromptEdit|OLEDB|ERR> ", 0x109u);
        v46 = anonymous_namespace_::SetErrorInfo_0(107, v30, v30);
        throw (long *)&v46;
      }
      *a3 = -1;
      SysFreeString(v28);
      ATL::CComPtr<IRowsetChange>::~CComPtr<IRowsetChange>(&v47);
      ATL::CComPtr<IRowsetChange>::~CComPtr<IRowsetChange>(&v33);
      ATL::CComPtr<IRowsetChange>::~CComPtr<IRowsetChange>(&v34);
    }
    else
    {
      if ( (bidGblFlags & 2) != 0 )
        OLEDBTraceErr(v21, L"<CDSLObject::PromptEdit|OLEDB|ERR> ", 0xE7u);
      if ( v23 != -2147217842 )
      {
        v43 = v23;
        throw (long *)&v43;
      }
      v52 = 1;
      ATL::CComPtr<IRowsetChange>::~CComPtr<IRowsetChange>(&v33);
      ATL::CComPtr<IRowsetChange>::~CComPtr<IRowsetChange>(&v34);
    }
  }
  catch ( long v48 )
  {
    if ( v52 >= 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
        OLEDBTraceErr(v52, L"<CDSLObject::PromptEdit|OLEDB|ERR> ", 0x116u);
      v31 = -2147418113;
      if ( v48 < 0 )
        v31 = v48;
      v52 = v31;
    }
  }
  catch ( ... )
  {
    v52 = -2147418113;
    if ( (bidGblFlags & 2) != 0 )
      OLEDBTraceErr(-2147418113, L"<CDSLObject::PromptEdit|OLEDB|ERR> ", 0x11Eu);
  }
  CoTaskMemFree(psz);
  psz = 0;
  if ( v50 )
    SetCursor(hCursor);
  return (unsigned int)v52;
}

```

## disassembly

```asm
0x180049330  mov     [rsp+arg_0], rbx
0x180049335  mov     [rsp+arg_8], rsi
0x18004933a  mov     [rsp+arg_10], r8
0x18004933f  push    rdi
0x180049340  push    r12
0x180049342  push    r13
0x180049344  push    r14
0x180049346  push    r15
0x180049348  sub     rsp, 0C0h
0x18004934f  mov     rsi, r8
0x180049352  mov     rbx, rdx
0x180049355  mov     r13, rcx
0x180049358  xor     edi, edi
0x18004935a  test    r8, r8
0x18004935d  jnz     short loc_1800493A0
0x18004935f  test    byte ptr cs:_bidGblFlags, 2
0x180049366  jz      short loc_18004937F
0x180049368  mov     r8d, 9Bh; unsigned int
0x18004936e  lea     rdx, aCdslobjectProm_2; "<CDSLObject::PromptEdit|OLEDB|ERR> "
0x180049375  mov     ecx, 80070057h; int
0x18004937a  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004937f  mov     ecx, 6Eh ; 'n'; this
0x180049384  mov     r9d, 80070057h; struct _GUID *
0x18004938a  lea     r8, IID_IDataSourceLocator; unsigned int
0x180049391  call    ?SetErrorInfo@DSLUtils@@YAXIIAEBU_GUID@@J@Z; DSLUtils::SetErrorInfo(uint,uint,_GUID const &,long)
0x180049396  mov     eax, 80070057h
0x18004939b  jmp     loc_1800496FE
0x1800493a0  test    rbx, rbx
0x1800493a3  jnz     short loc_1800493CC
0x1800493a5  test    byte ptr cs:_bidGblFlags, 2
0x1800493ac  jz      short loc_1800493C5
0x1800493ae  mov     r8d, 0A0h; unsigned int
0x1800493b4  lea     rdx, aCdslobjectProm_2; "<CDSLObject::PromptEdit|OLEDB|ERR> "
0x1800493bb  mov     ecx, 80070057h; int
0x1800493c0  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800493c5  mov     ecx, 69h ; 'i'
0x1800493ca  jmp     short loc_180049384
0x1800493cc  cmp     [rdx], rdi
0x1800493cf  jnz     short loc_1800493F8
0x1800493d1  test    byte ptr cs:_bidGblFlags, 2
0x1800493d8  jz      short loc_1800493F1
0x1800493da  mov     r8d, 0A6h; unsigned int
0x1800493e0  lea     rdx, aCdslobjectProm_2; "<CDSLObject::PromptEdit|OLEDB|ERR> "
0x1800493e7  mov     ecx, 80070057h; int
0x1800493ec  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800493f1  mov     ecx, 6Fh ; 'o'
0x1800493f6  jmp     short loc_180049384
0x1800493f8  mov     dl, 1; bool
0x1800493fa  lea     rcx, [rsp+0E8h+hCursor]; this
0x180049402  call    ??0WaitCursor@DSLUtils@@QEAA@_N@Z; DSLUtils::WaitCursor::WaitCursor(bool)
0x180049407  nop
0x180049408  mov     [rsi], di
0x18004940b  mov     [rsp+0E8h+arg_18], edi
0x180049412  mov     [rsp+0E8h+psz], rdi
0x180049417  mov     [rsp+0E8h+var_90], rdi
0x18004941c  mov     rcx, [rbx]
0x18004941f  mov     rax, [rcx]
0x180049422  lea     r8, [rsp+0E8h+var_90]
0x180049427  lea     r14, IID_IADOConnectionConstruction
0x18004942e  mov     rdx, r14
0x180049431  mov     rax, [rax]
0x180049434  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049439  mov     esi, eax
0x18004943b  mov     [rsp+0E8h+arg_18], eax
0x180049442  test    eax, eax
0x180049444  js      loc_18004971B
0x18004944a  mov     [rsp+0E8h+var_98], rdi
0x18004944f  mov     rcx, [rsp+0E8h+var_90]
0x180049454  mov     rax, [rcx]
0x180049457  lea     rdx, [rsp+0E8h+var_98]
0x18004945c  mov     rax, [rax+18h]
0x180049460  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049465  mov     esi, eax
0x180049467  mov     [rsp+0E8h+arg_18], eax
0x18004946e  test    eax, eax
0x180049470  js      loc_180049776
0x180049476  cmp     [rsp+0E8h+var_98], rdi
0x18004947b  jnz     loc_180049547
0x180049481  mov     [rsp+0E8h+var_88], rdi
0x180049486  mov     rcx, [rbx]
0x180049489  mov     rax, [rcx]
0x18004948c  lea     r8, [rsp+0E8h+var_88]
0x180049491  lea     r12, IID_IADOConnection
0x180049498  mov     rdx, r12
0x18004949b  mov     rax, [rax]
0x18004949e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800494a3  mov     esi, eax
0x1800494a5  mov     [rsp+0E8h+arg_18], eax
0x1800494ac  test    eax, eax
0x1800494ae  js      loc_1800497D4
0x1800494b4  mov     [rsp+0E8h+bstrString], rdi
0x1800494b9  mov     rcx, [rsp+0E8h+var_88]
0x1800494be  mov     rax, [rcx]
0x1800494c1  lea     rdx, [rsp+0E8h+bstrString]
0x1800494c6  mov     rax, [rax+40h]
0x1800494ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800494cf  mov     esi, eax
0x1800494d1  mov     [rsp+0E8h+arg_18], eax
0x1800494d8  test    eax, eax
0x1800494da  js      loc_180049835
0x1800494e0  lea     r15, [r13-28h]
0x1800494e4  lea     r14, [r13-30h]
0x1800494e8  mov     rax, [r14+8]
0x1800494ec  lea     rcx, [rsp+0E8h+var_98]
0x1800494f1  mov     [rsp+0E8h+var_C0], rcx
0x1800494f6  lea     rcx, IID_IUnknown
0x1800494fd  mov     [rsp+0E8h+var_C8], rcx
0x180049502  mov     r9, [rsp+0E8h+bstrString]
0x180049507  xor     edx, edx
0x180049509  lea     r8d, [rdx+17h]
0x18004950d  mov     rcx, r15
0x180049510  mov     rax, [rax+18h]
0x180049514  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049519  mov     esi, eax
0x18004951b  mov     [rsp+0E8h+arg_18], eax
0x180049522  test    eax, eax
0x180049524  js      loc_180049898
0x18004952a  mov     esi, 2
0x18004952f  mov     rcx, [rsp+0E8h+bstrString]; bstrString
0x180049534  call    cs:__imp_SysFreeString
0x18004953a  nop
0x18004953b  lea     rcx, [rsp+0E8h+var_88]
0x180049540  call    ??1?$CComPtr@UIRowsetChange@@@ATL@@QEAA@XZ; ATL::CComPtr<IRowsetChange>::~CComPtr<IRowsetChange>(void)
0x180049545  jmp     short loc_18004955B
0x180049547  mov     esi, 12h
0x18004954c  lea     r14, [r13-30h]
0x180049550  lea     r15, [r13-28h]
0x180049554  lea     r12, IID_IADOConnection
0x18004955b  lea     rcx, IID_IUnknown
0x180049562  mov     rax, [r14]
0x180049565  lea     rdx, [rsp+0E8h+var_98]
0x18004956a  mov     [rsp+0E8h+var_A8], rdx
0x18004956f  mov     [rsp+0E8h+var_B0], rcx
0x180049574  mov     [rsp+0E8h+var_B8], rdi
0x180049579  mov     [rsp+0E8h+var_C0], rdi
0x18004957e  mov     dword ptr [rsp+0E8h+var_C8], edi
0x180049582  mov     r9d, esi
0x180049585  mov     r8, [r13+3F8h]
0x18004958c  xor     edx, edx
0x18004958e  mov     rcx, r14
0x180049591  mov     rax, [rax+18h]
0x180049595  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004959a  mov     esi, eax
0x18004959c  mov     [rsp+0E8h+arg_18], eax
0x1800495a3  test    eax, eax
0x1800495a5  jns     short loc_1800495F6
0x1800495a7  test    byte ptr cs:_bidGblFlags, 2
0x1800495ae  jz      short loc_1800495C4
0x1800495b0  mov     r8d, 0E7h; unsigned int
0x1800495b6  lea     rdx, aCdslobjectProm_2; "<CDSLObject::PromptEdit|OLEDB|ERR> "
0x1800495bd  mov     ecx, eax; int
0x1800495bf  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800495c4  cmp     esi, 80040E4Eh
0x1800495ca  jnz     loc_1800498FC
0x1800495d0  mov     [rsp+0E8h+arg_18], 1
0x1800495db  lea     rcx, [rsp+0E8h+var_98]
0x1800495e0  call    ??1?$CComPtr@UIRowsetChange@@@ATL@@QEAA@XZ; ATL::CComPtr<IRowsetChange>::~CComPtr<IRowsetChange>(void)
0x1800495e5  nop
0x1800495e6  lea     rcx, [rsp+0E8h+var_90]
0x1800495eb  call    ??1?$CComPtr@UIRowsetChange@@@ATL@@QEAA@XZ; ATL::CComPtr<IRowsetChange>::~CComPtr<IRowsetChange>(void)
0x1800495f0  nop
0x1800495f1  jmp     loc_1800496CF
0x1800495f6  mov     rax, [r15]
0x1800495f9  lea     r9, [rsp+0E8h+psz]
0x1800495fe  mov     r8b, 1
0x180049601  mov     rdx, [rsp+0E8h+var_98]
0x180049606  mov     rcx, r15
0x180049609  mov     rax, [rax+20h]
0x18004960d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049612  mov     esi, eax
0x180049614  mov     [rsp+0E8h+arg_18], eax
0x18004961b  test    eax, eax
0x18004961d  js      loc_180049917
0x180049623  mov     [rsp+0E8h+var_48], rdi
0x18004962b  mov     rcx, [rbx]
0x18004962e  mov     rax, [rcx]
0x180049631  lea     r8, [rsp+0E8h+var_48]
0x180049639  mov     rdx, r12
0x18004963c  mov     rax, [rax]
0x18004963f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049644  mov     esi, eax
0x180049646  mov     [rsp+0E8h+arg_18], eax
0x18004964d  test    eax, eax
0x18004964f  js      loc_18004997B
0x180049655  mov     rcx, [rsp+0E8h+psz]; psz
0x18004965a  call    cs:__imp_SysAllocString
0x180049660  mov     rbx, rax
0x180049663  mov     [rsp+0E8h+bstrString], rax
0x180049668  mov     rcx, [rsp+0E8h+var_48]
0x180049670  mov     rax, [rcx]
0x180049673  mov     rdx, rbx
0x180049676  mov     rax, [rax+48h]
0x18004967a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004967f  mov     esi, eax
0x180049681  mov     [rsp+0E8h+arg_18], eax
0x180049688  test    eax, eax
0x18004968a  js      loc_1800499DC
0x180049690  mov     rax, [rsp+0E8h+arg_10]
0x180049698  mov     word ptr [rax], 0FFFFh
0x18004969d  mov     rcx, rbx; bstrString
0x1800496a0  call    cs:__imp_SysFreeString
0x1800496a6  nop
0x1800496a7  lea     rcx, [rsp+0E8h+var_48]
0x1800496af  call    ??1?$CComPtr@UIRowsetChange@@@ATL@@QEAA@XZ; ATL::CComPtr<IRowsetChange>::~CComPtr<IRowsetChange>(void)
0x1800496b4  nop
0x1800496b5  lea     rcx, [rsp+0E8h+var_98]
0x1800496ba  call    ??1?$CComPtr@UIRowsetChange@@@ATL@@QEAA@XZ; ATL::CComPtr<IRowsetChange>::~CComPtr<IRowsetChange>(void)
0x1800496bf  nop
0x1800496c0  lea     rcx, [rsp+0E8h+var_90]
0x1800496c5  call    ??1?$CComPtr@UIRowsetChange@@@ATL@@QEAA@XZ; ATL::CComPtr<IRowsetChange>::~CComPtr<IRowsetChange>(void)
0x1800496ca  nop
0x1800496cb  jmp     short loc_1800496CF
0x1800496cd  xor     edi, edi
0x1800496cf  mov     rcx, [rsp+0E8h+psz]; pv
0x1800496d4  call    cs:__imp_CoTaskMemFree
0x1800496da  mov     [rsp+0E8h+psz], rdi
0x1800496df  cmp     [rsp+0E8h+var_30], dil
0x1800496e7  jz      short loc_1800496F7
0x1800496e9  mov     rcx, [rsp+0E8h+hCursor]; hCursor
0x1800496f1  call    cs:__imp_SetCursor
0x1800496f7  mov     eax, [rsp+0E8h+arg_18]
0x1800496fe  lea     r11, [rsp+0E8h+var_28]
0x180049706  mov     rbx, [r11+30h]
0x18004970a  mov     rsi, [r11+38h]
0x18004970e  mov     rsp, r11
0x180049711  pop     r15
0x180049713  pop     r14
0x180049715  pop     r13
0x180049717  pop     r12
0x180049719  pop     rdi
0x18004971a  retn
0x18004971b  test    byte ptr cs:_bidGblFlags, 2
0x180049722  jz      short loc_180049738
0x180049724  mov     r8d, 0B7h; unsigned int
0x18004972a  lea     rdx, aCdslobjectProm_2; "<CDSLObject::PromptEdit|OLEDB|ERR> "
0x180049731  mov     ecx, eax; int
0x180049733  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180049738  lea     rax, IID_IDispatch
0x18004973f  mov     [rsp+0E8h+var_C8], rax
0x180049744  mov     r9, [rbx]
0x180049747  mov     r8d, esi
0x18004974a  mov     edx, 80070057h
0x18004974f  mov     ecx, 6Fh ; 'o'
0x180049754  call    _anonymous_namespace___SetErrorInfo_0
0x180049759  mov     [rsp+0E8h+arg_18], eax
0x180049760  mov     [rsp+0E8h+pExceptionObject], eax
0x180049764  lea     rdx, _TI1J; pThrowInfo
0x18004976b  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x180049770  call    _CxxThrowException_0
0x180049776  test    byte ptr cs:_bidGblFlags, 2
0x18004977d  jz      short loc_180049793
0x18004977f  mov     r8d, 0C0h; unsigned int
0x180049785  lea     rdx, aCdslobjectProm_2; "<CDSLObject::PromptEdit|OLEDB|ERR> "
0x18004978c  mov     ecx, eax; int
0x18004978e  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180049793  lea     rcx, [rsp+0E8h+var_90]
0x180049798  call    ??B?$auto_IF@UIDBInitialize@@@DSLUtils@@QEAAPEAUIDBInitialize@@XZ; DSLUtils::auto_IF<IDBInitialize>::operator IDBInitialize *(void)
0x18004979d  mov     r9, rax
0x1800497a0  mov     [rsp+0E8h+var_C8], r14
0x1800497a5  mov     r8d, esi
0x1800497a8  mov     edx, 80070057h
0x1800497ad  mov     ecx, 71h ; 'q'
0x1800497b2  call    _anonymous_namespace___SetErrorInfo_0
0x1800497b7  mov     [rsp+0E8h+arg_18], eax
0x1800497be  mov     [rsp+0E8h+var_6C], eax
0x1800497c2  lea     rdx, _TI1J; pThrowInfo
0x1800497c9  lea     rcx, [rsp+0E8h+var_6C]; pExceptionObject
0x1800497ce  call    _CxxThrowException_0
0x1800497d4  test    byte ptr cs:_bidGblFlags, 2
0x1800497db  jz      short loc_1800497F1
0x1800497dd  mov     r8d, 0CDh; unsigned int
0x1800497e3  lea     rdx, aCdslobjectProm_2; "<CDSLObject::PromptEdit|OLEDB|ERR> "
0x1800497ea  mov     ecx, eax; int
0x1800497ec  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800497f1  lea     rax, IID_IDispatch
0x1800497f8  mov     [rsp+0E8h+var_C8], rax
0x1800497fd  mov     r9, [rbx]
0x180049800  mov     r8d, esi
0x180049803  mov     edx, 80070057h
0x180049808  mov     ecx, 6Fh ; 'o'
0x18004980d  call    _anonymous_namespace___SetErrorInfo_0
0x180049812  mov     [rsp+0E8h+arg_18], eax
0x180049819  mov     [rsp+0E8h+var_68], eax
0x180049820  lea     rdx, _TI1J; pThrowInfo
0x180049827  lea     rcx, [rsp+0E8h+var_68]; pExceptionObject
0x18004982f  call    _CxxThrowException_0
0x180049835  test    byte ptr cs:_bidGblFlags, 2
0x18004983c  jz      short loc_180049852
0x18004983e  mov     r8d, 0D5h; unsigned int
0x180049844  lea     rdx, aCdslobjectProm_2; "<CDSLObject::PromptEdit|OLEDB|ERR> "
0x18004984b  mov     ecx, eax; int
0x18004984d  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180049852  lea     rcx, [rsp+0E8h+var_88]
0x180049857  call    ??B?$auto_IF@UIDBInitialize@@@DSLUtils@@QEAAPEAUIDBInitialize@@XZ; DSLUtils::auto_IF<IDBInitialize>::operator IDBInitialize *(void)
0x18004985c  mov     r9, rax
0x18004985f  mov     [rsp+0E8h+var_C8], r12
0x180049864  mov     r8d, esi
0x180049867  mov     edx, 80070057h
0x18004986c  mov     ecx, 6Fh ; 'o'
0x180049871  call    _anonymous_namespace___SetErrorInfo_0
  ... truncated ...
```
