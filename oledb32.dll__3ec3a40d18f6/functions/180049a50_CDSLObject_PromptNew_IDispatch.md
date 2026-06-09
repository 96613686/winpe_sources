# CDSLObject::PromptNew(IDispatch * *)

- ea: `0x180049a50`
- end: `0x180049e27`
- name: `?PromptNew@CDSLObject@@UEAAJPEAPEAUIDispatch@@@Z`
- size: `983`
- prototype: `int(CDSLObject *__hidden this, struct IDispatch **)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x180013870`
- `0x180026940`
- `0x18002ec0c`
- `0x18004931c`
- `0x180049a50`
- `0x180049e30`
- `0x180049e74`
- `0x18005989c`
- `0x180087010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180049bf9`
- `OLEAUT32!__imp_SysAllocString` at `0x180049bf9`
- `OLEAUT32!__imp_SysFreeString` at `0x180049c32`
- `OLEAUT32!__imp_SysFreeString` at `0x180049c32`
- `ole32!CoTaskMemFree` at `0x180049ca3`
- `ole32!CoTaskMemFree` at `0x180049ca3`
- `ole32!CoCreateInstance` at `0x180049ba0`
- `ole32!CoCreateInstance` at `0x180049ba0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDSLObject::PromptNew(CDSLObject *this, LPVOID *a2)
{
  int v5; // ebx
  __int64 v6; // r8
  char v7; // al
  int v8; // eax
  unsigned int v9; // ebx
  HRESULT Instance; // eax
  __int64 v11; // rcx
  unsigned int v12; // ebx
  int v13; // eax
  unsigned int v14; // ebx
  OLECHAR *v15; // rbx
  int v16; // eax
  unsigned int v17; // esi
  int v18; // ecx
  int ppv; // [rsp+20h] [rbp-78h]
  int pExceptionObject; // [rsp+50h] [rbp-48h] BYREF
  int v21; // [rsp+54h] [rbp-44h] BYREF
  int v22; // [rsp+58h] [rbp-40h] BYREF
  int v23; // [rsp+5Ch] [rbp-3Ch] BYREF
  int v24; // [rsp+60h] [rbp-38h] BYREF
  OLECHAR *psz; // [rsp+68h] [rbp-30h] BYREF
  _QWORD v26[5]; // [rsp+70h] [rbp-28h] BYREF
  int v28; // [rsp+B0h] [rbp+18h]
  __int64 v29; // [rsp+B8h] [rbp+20h] BYREF

  if ( !a2 )
  {
    DSLUtils::SetErrorInfo(
      (DSLUtils *)0x69,
      0,
      (unsigned int)&IID_IDataSourceLocator,
      (const struct _GUID *)0x80070057LL,
      ppv);
    return 2147942487LL;
  }
  *a2 = 0;
  v26[0] = 0;
  v5 = (*(__int64 (__fastcall **)(char *, _QWORD, _QWORD, __int64, _DWORD, _QWORD, _QWORD, GUID *, _QWORD *))(*((_QWORD *)this - 6) + 24LL))(
         (char *)this - 48,
         0,
         *((_QWORD *)this + 127),
         1,
         0,
         0,
         0,
         &IID_IUnknown,
         v26);
  if ( v5 >= 0 )
  {
    try
    {
      psz = 0;
      LOBYTE(v6) = 1;
      v8 = (*(__int64 (__fastcall **)(char *, _QWORD, __int64, OLECHAR **))(*((_QWORD *)this - 5) + 32LL))(
             (char *)this - 40,
             v26[0],
             v6,
             &psz);
      v9 = v8;
      if ( v8 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
          OLEDBTraceErr(v8, L"<CDSLObject::PromptNew|OLEDB|ERR> ", 0x5Bu);
        pExceptionObject = anonymous_namespace_::SetErrorInfo_0(107, v9, v9);
        throw (long *)&pExceptionObject;
      }
      Instance = CoCreateInstance(&CLSID_CADOConnection, 0, 0x17u, &IID_IDispatch, a2);
      v12 = Instance;
      if ( Instance < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
          OLEDBTraceErr(Instance, L"<CDSLObject::PromptNew|OLEDB|ERR> ", 0x62u);
        v21 = anonymous_namespace_::SetErrorInfo(v11, v12, v12);
        throw (long *)&v21;
      }
      v29 = 0;
      v13 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))*a2)(*a2, &IID_IADOConnection, &v29);
      v14 = v13;
      if ( v13 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
          OLEDBTraceErr(v13, L"<CDSLObject::PromptNew|OLEDB|ERR> ", 0x6Au);
        v22 = anonymous_namespace_::SetErrorInfo_0(109, 2147942487LL, v14);
        throw (long *)&v22;
      }
      v15 = SysAllocString(psz);
      v26[1] = v15;
      v16 = (*(__int64 (__fastcall **)(__int64, OLECHAR *))(*(_QWORD *)v29 + 72LL))(v29, v15);
      v17 = v16;
      v28 = v16;
      if ( v16 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
          OLEDBTraceErr(v16, L"<CDSLObject::PromptNew|OLEDB|ERR> ", 0x72u);
        DSLUtils::auto_IF<IDBInitialize>::operator IDBInitialize *(&v29);
        v23 = anonymous_namespace_::SetErrorInfo_0(109, v17, v17);
        throw (long *)&v23;
      }
      SysFreeString(v15);
      ATL::CComPtr<IRowsetChange>::~CComPtr<IRowsetChange>(&v29);
    }
    catch ( long v24 )
    {
      if ( v28 >= 0 )
      {
        v18 = -2147418113;
        if ( v24 < 0 )
          v18 = v24;
        v28 = v18;
        if ( (bidGblFlags & 2) != 0 )
          OLEDBTraceErr(v18, L"<CDSLObject::PromptNew|OLEDB|ERR> ", 0x7Cu);
      }
      v17 = v28;
      if ( v28 < 0 )
      {
LABEL_17:
        if ( *a2 )
        {
          if ( (bidGblFlags & 2) != 0 )
            OLEDBTraceErr(v17, L"<CDSLObject::PromptNew|OLEDB|ERR> ", 0x87u);
          (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)*a2 + 16LL))(*a2, *(_QWORD *)*a2);
          *a2 = 0;
        }
      }
    }
    catch ( ... )
    {
      if ( (bidGblFlags & 2) != 0 )
        OLEDBTraceErr(-2147418113, L"<CDSLObject::PromptNew|OLEDB|ERR> ", 0x82u);
      v17 = -2147418113;
      goto LABEL_17;
    }
    CoTaskMemFree(psz);
    psz = 0;
    ATL::CComPtr<IRowsetChange>::~CComPtr<IRowsetChange>(v26);
    return v17;
  }
  v7 = bidGblFlags;
  if ( (bidGblFlags & 2) != 0 )
  {
    OLEDBTraceErr(v5, L"<CDSLObject::PromptNew|OLEDB|ERR> ", 0x47u);
    v7 = bidGblFlags;
  }
  if ( v5 == -2147217842 )
  {
    if ( (v7 & 2) != 0 )
      OLEDBTraceErr(-2147217842, L"<CDSLObject::PromptNew|OLEDB|ERR> ", 0x4Bu);
    v5 = 1;
  }
  ATL::CComPtr<IRowsetChange>::~CComPtr<IRowsetChange>(v26);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180049a50  mov     [rsp+arg_0], rbx
0x180049a55  mov     [rsp+arg_8], rdx
0x180049a5a  push    rsi
0x180049a5b  push    r14
0x180049a5d  push    r15
0x180049a5f  sub     rsp, 80h
0x180049a66  mov     rsi, rdx
0x180049a69  mov     r14, rcx
0x180049a6c  test    rdx, rdx
0x180049a6f  jnz     short loc_180049A90
0x180049a71  mov     r9d, 80070057h; struct _GUID *
0x180049a77  lea     r8, IID_IDataSourceLocator; unsigned int
0x180049a7e  lea     ecx, [rdx+69h]; this
0x180049a81  call    ?SetErrorInfo@DSLUtils@@YAXIIAEBU_GUID@@J@Z; DSLUtils::SetErrorInfo(uint,uint,_GUID const &,long)
0x180049a86  mov     eax, 80070057h
0x180049a8b  jmp     loc_180049CBE
0x180049a90  mov     qword ptr [rdx], 0
0x180049a97  mov     [rsp+98h+var_28], 0
0x180049aa0  add     rcx, 0FFFFFFFFFFFFFFD0h
0x180049aa4  mov     rax, [rcx]
0x180049aa7  lea     rdx, [rsp+98h+var_28]
0x180049aac  mov     [rsp+98h+var_58], rdx
0x180049ab1  lea     rdx, IID_IUnknown
0x180049ab8  mov     [rsp+98h+var_60], rdx
0x180049abd  mov     [rsp+98h+var_68], 0
0x180049ac6  mov     [rsp+98h+var_70], 0
0x180049acf  mov     dword ptr [rsp+98h+ppv], 0
0x180049ad7  mov     r15d, 1
0x180049add  mov     r9d, r15d
0x180049ae0  mov     r8, [r14+3F8h]
0x180049ae7  xor     edx, edx
0x180049ae9  mov     rax, [rax+18h]
0x180049aed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049af2  mov     ebx, eax
0x180049af4  mov     [rsp+98h+arg_10], eax
0x180049afb  test    eax, eax
0x180049afd  jns     short loc_180049B54
0x180049aff  mov     eax, cs:_bidGblFlags
0x180049b05  test    al, 2
0x180049b07  jz      short loc_180049B21
0x180049b09  lea     r8d, [r15+46h]; unsigned int
0x180049b0d  lea     rdx, aCdslobjectProm_0; "<CDSLObject::PromptNew|OLEDB|ERR> "
0x180049b14  mov     ecx, ebx; int
0x180049b16  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180049b1b  mov     eax, cs:_bidGblFlags
0x180049b21  mov     ecx, 80040E4Eh; int
0x180049b26  cmp     ebx, ecx
0x180049b28  jnz     short loc_180049B43
0x180049b2a  test    al, 2
0x180049b2c  jz      short loc_180049B40
0x180049b2e  mov     r8d, 4Bh ; 'K'; unsigned int
0x180049b34  lea     rdx, aCdslobjectProm_0; "<CDSLObject::PromptNew|OLEDB|ERR> "
0x180049b3b  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180049b40  mov     ebx, r15d
0x180049b43  lea     rcx, [rsp+98h+var_28]
0x180049b48  call    ??1?$CComPtr@UIRowsetChange@@@ATL@@QEAA@XZ; ATL::CComPtr<IRowsetChange>::~CComPtr<IRowsetChange>(void)
0x180049b4d  mov     eax, ebx
0x180049b4f  jmp     loc_180049CBE
0x180049b54  mov     [rsp+98h+psz], 0
0x180049b5d  lea     rcx, [r14-28h]
0x180049b61  mov     rax, [rcx]
0x180049b64  lea     r9, [rsp+98h+psz]
0x180049b69  mov     r8b, r15b
0x180049b6c  mov     rdx, [rsp+98h+var_28]
0x180049b71  mov     rax, [rax+20h]
0x180049b75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049b7a  mov     ebx, eax
0x180049b7c  test    eax, eax
0x180049b7e  js      loc_180049CD3
0x180049b84  mov     [rsp+98h+ppv], rsi; ppv
0x180049b89  lea     r14, IID_IDispatch
0x180049b90  mov     r9, r14; riid
0x180049b93  xor     edx, edx; pUnkOuter
0x180049b95  lea     r8d, [rdx+17h]; dwClsContext
0x180049b99  lea     rcx, CLSID_CADOConnection; rclsid
0x180049ba0  call    cs:__imp_CoCreateInstance
0x180049ba6  mov     ebx, eax
0x180049ba8  mov     [rsp+98h+arg_10], eax
0x180049baf  test    eax, eax
0x180049bb1  js      loc_180049D30
0x180049bb7  mov     [rsp+98h+arg_18], 0
0x180049bc3  mov     rcx, [rsi]
0x180049bc6  mov     rax, [rcx]
0x180049bc9  lea     r8, [rsp+98h+arg_18]
0x180049bd1  lea     r15, IID_IADOConnection
0x180049bd8  mov     rdx, r15
0x180049bdb  mov     rax, [rax]
0x180049bde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049be3  mov     ebx, eax
0x180049be5  mov     [rsp+98h+arg_10], eax
0x180049bec  test    eax, eax
0x180049bee  js      loc_180049D74
0x180049bf4  mov     rcx, [rsp+98h+psz]; psz
0x180049bf9  call    cs:__imp_SysAllocString
0x180049bff  mov     rbx, rax
0x180049c02  mov     [rsp+98h+var_20], rax
0x180049c07  mov     rcx, [rsp+98h+arg_18]
0x180049c0f  mov     rax, [rcx]
0x180049c12  mov     rdx, rbx
0x180049c15  mov     rax, [rax+48h]
0x180049c19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049c1e  mov     esi, eax
0x180049c20  mov     [rsp+98h+arg_10], eax
0x180049c27  test    eax, eax
0x180049c29  js      loc_180049DC8
0x180049c2f  mov     rcx, rbx; bstrString
0x180049c32  call    cs:__imp_SysFreeString
0x180049c38  nop
0x180049c39  lea     rcx, [rsp+98h+arg_18]
0x180049c41  call    ??1?$CComPtr@UIRowsetChange@@@ATL@@QEAA@XZ; ATL::CComPtr<IRowsetChange>::~CComPtr<IRowsetChange>(void)
0x180049c46  nop
0x180049c47  jmp     short loc_180049C9E
0x180049c49  mov     esi, [rsp+98h+arg_10]
0x180049c50  test    esi, esi
0x180049c52  jns     short loc_180049C9E
0x180049c54  jmp     short loc_180049C5D
0x180049c56  mov     esi, [rsp+98h+arg_10]
0x180049c5d  mov     rbx, [rsp+98h+arg_8]
0x180049c65  cmp     qword ptr [rbx], 0
0x180049c69  jz      short loc_180049C9E
0x180049c6b  test    byte ptr cs:_bidGblFlags, 2
0x180049c72  jz      short loc_180049C88
0x180049c74  mov     r8d, 87h; unsigned int
0x180049c7a  lea     rdx, aCdslobjectProm_0; "<CDSLObject::PromptNew|OLEDB|ERR> "
0x180049c81  mov     ecx, esi; int
0x180049c83  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180049c88  mov     rcx, [rbx]
0x180049c8b  mov     rdx, [rcx]
0x180049c8e  mov     rax, [rdx+10h]
0x180049c92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049c97  mov     qword ptr [rbx], 0
0x180049c9e  mov     rcx, [rsp+98h+psz]; pv
0x180049ca3  call    cs:__imp_CoTaskMemFree
0x180049ca9  mov     [rsp+98h+psz], 0
0x180049cb2  lea     rcx, [rsp+98h+var_28]
0x180049cb7  call    ??1?$CComPtr@UIRowsetChange@@@ATL@@QEAA@XZ; ATL::CComPtr<IRowsetChange>::~CComPtr<IRowsetChange>(void)
0x180049cbc  mov     eax, esi
0x180049cbe  mov     rbx, [rsp+98h+arg_0]
0x180049cc6  add     rsp, 80h
0x180049ccd  pop     r15
0x180049ccf  pop     r14
0x180049cd1  pop     rsi
0x180049cd2  retn
0x180049cd3  mov     [rsp+98h+arg_10], eax
0x180049cda  test    byte ptr cs:_bidGblFlags, 2
0x180049ce1  jz      short loc_180049CF7
0x180049ce3  mov     r8d, 5Bh ; '['; unsigned int
0x180049ce9  lea     rdx, aCdslobjectProm_0; "<CDSLObject::PromptNew|OLEDB|ERR> "
0x180049cf0  mov     ecx, eax; int
0x180049cf2  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180049cf7  lea     rax, IID_IDataInitialize
0x180049cfe  mov     [rsp+98h+ppv], rax
0x180049d03  xor     r9d, r9d
0x180049d06  mov     r8d, ebx
0x180049d09  mov     edx, ebx
0x180049d0b  lea     ecx, [r9+6Bh]
0x180049d0f  call    _anonymous_namespace___SetErrorInfo_0
0x180049d14  mov     [rsp+98h+arg_10], eax
0x180049d1b  mov     [rsp+98h+pExceptionObject], eax
0x180049d1f  lea     rdx, _TI1J; pThrowInfo
0x180049d26  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x180049d2b  call    _CxxThrowException_0
0x180049d30  test    byte ptr cs:_bidGblFlags, 2
0x180049d37  jz      short loc_180049D4D
0x180049d39  mov     r8d, 62h ; 'b'; unsigned int
0x180049d3f  lea     rdx, aCdslobjectProm_0; "<CDSLObject::PromptNew|OLEDB|ERR> "
0x180049d46  mov     ecx, eax; int
0x180049d48  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180049d4d  mov     r8d, ebx
0x180049d50  mov     edx, ebx
0x180049d52  call    _anonymous_namespace___SetErrorInfo
0x180049d57  mov     [rsp+98h+arg_10], eax
0x180049d5e  mov     [rsp+98h+var_44], eax
0x180049d62  lea     rdx, _TI1J; pThrowInfo
0x180049d69  lea     rcx, [rsp+98h+var_44]; pExceptionObject
0x180049d6e  call    _CxxThrowException_0
0x180049d74  test    byte ptr cs:_bidGblFlags, 2
0x180049d7b  jz      short loc_180049D91
0x180049d7d  mov     r8d, 6Ah ; 'j'; unsigned int
0x180049d83  lea     rdx, aCdslobjectProm_0; "<CDSLObject::PromptNew|OLEDB|ERR> "
0x180049d8a  mov     ecx, eax; int
0x180049d8c  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180049d91  mov     [rsp+98h+ppv], r14
0x180049d96  mov     r9, [rsi]
0x180049d99  mov     r8d, ebx
0x180049d9c  mov     edx, 80070057h
0x180049da1  mov     ecx, 6Dh ; 'm'
0x180049da6  call    _anonymous_namespace___SetErrorInfo_0
0x180049dab  mov     [rsp+98h+arg_10], eax
0x180049db2  mov     [rsp+98h+var_40], eax
0x180049db6  lea     rdx, _TI1J; pThrowInfo
0x180049dbd  lea     rcx, [rsp+98h+var_40]; pExceptionObject
0x180049dc2  call    _CxxThrowException_0
0x180049dc8  test    byte ptr cs:_bidGblFlags, 2
0x180049dcf  jz      short loc_180049DE5
0x180049dd1  mov     r8d, 72h ; 'r'; unsigned int
0x180049dd7  lea     rdx, aCdslobjectProm_0; "<CDSLObject::PromptNew|OLEDB|ERR> "
0x180049dde  mov     ecx, eax; int
0x180049de0  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180049de5  lea     rcx, [rsp+98h+arg_18]
0x180049ded  call    ??B?$auto_IF@UIDBInitialize@@@DSLUtils@@QEAAPEAUIDBInitialize@@XZ; DSLUtils::auto_IF<IDBInitialize>::operator IDBInitialize *(void)
0x180049df2  mov     r9, rax
0x180049df5  mov     [rsp+98h+ppv], r15
0x180049dfa  mov     r8d, esi
0x180049dfd  mov     edx, esi
0x180049dff  mov     ecx, 6Dh ; 'm'
0x180049e04  call    _anonymous_namespace___SetErrorInfo_0
0x180049e09  mov     [rsp+98h+arg_10], eax
0x180049e10  mov     [rsp+98h+var_3C], eax
0x180049e14  lea     rdx, _TI1J; pThrowInfo
0x180049e1b  lea     rcx, [rsp+98h+var_3C]; pExceptionObject
0x180049e20  call    _CxxThrowException_0
```
