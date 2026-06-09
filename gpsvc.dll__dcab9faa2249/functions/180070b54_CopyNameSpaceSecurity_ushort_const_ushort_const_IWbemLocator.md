# CopyNameSpaceSecurity(ushort const *,ushort const *,IWbemLocator *)

- ea: `0x180070b54`
- end: `0x180070e87`
- name: `?CopyNameSpaceSecurity@@YAJPEBG0PEAUIWbemLocator@@@Z`
- size: `819`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, struct IWbemLocator *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800b74e0`

## callees

- `0x18000a504`
- `0x18000a52c`
- `0x1800535a0`
- `0x1800585e8`
- `0x180070b54`
- `0x180072a08`
- `0x1800b5ee8`
- `0x1800b6140`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070ba5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070cbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070d37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070dc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070ba5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070cbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070d37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070dc6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180070b8e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180070b8e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180070b78`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180070b78`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180070cb2`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180070d2d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180070dbc`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180070e1f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180070cb2`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180070d2d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180070dbc`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180070e1f`
- `OLEAUT32!__imp_SysFreeString` at `0x180070c2d`
- `OLEAUT32!__imp_SysFreeString` at `0x180070c66`
- `OLEAUT32!__imp_SysFreeString` at `0x180070cf1`
- `OLEAUT32!__imp_SysFreeString` at `0x180070cfa`
- `OLEAUT32!__imp_SysFreeString` at `0x180070e59`
- `OLEAUT32!__imp_SysFreeString` at `0x180070e62`
- `OLEAUT32!__imp_SysFreeString` at `0x180070c2d`
- `OLEAUT32!__imp_SysFreeString` at `0x180070c66`
- `OLEAUT32!__imp_SysFreeString` at `0x180070cf1`
- `OLEAUT32!__imp_SysFreeString` at `0x180070cfa`
- `OLEAUT32!__imp_SysFreeString` at `0x180070e59`
- `OLEAUT32!__imp_SysFreeString` at `0x180070e62`

## string_xrefs

- `0x180070cce`: `CopyNameSpaceSecurity: SetThreadToken failed for src. hr=0x%08X`
- `0x180070d49`: `CopyNameSpaceSecurity: SetThreadToken failed for src. hr=0x%08X`
- `0x180070dd8`: `CopyNameSpaceSecurity: SetThreadToken failed for src. hr=0x%08X`
- `0x180070bbd`: `CopyNameSpaceSecurity: Openthreadtoken failed with error 0x%x.`
- `0x180070bf0`: `CopyNameSpaceSecurity: Copying Sec Desc from <%s> -> <%s>.`
- `0x180070c19`: `CopyNameSpaceSecurity: Function failed to allocate memory.`
- `0x180070c52`: `CopyNameSpaceSecurity: Function failed to allocate memory.`
- `0x180070d0b`: `CopyNameSpaceSecurity: ConnectServer failed for src. hr=0x%08X`
- `0x180070d72`: `CopyNameSpaceSecurity: GetNameSpaceSD failed for src. hr=0x%08X`
- `0x180070e01`: `CopyNameSpaceSecurity: ConnectServer failed for Dst. hr=0x%08X`
- `0x180070e2d`: `CopyNameSpaceSecurity: SetNamespaceSD failed on Dst, 0x%08X`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CopyNameSpaceSecurity(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        struct IWbemLocator *a3)
{
  HANDLE CurrentThread; // rax
  signed int v7; // eax
  unsigned int v8; // ebx
  OLECHAR *v9; // rbx
  OLECHAR *v10; // rcx
  OLECHAR *v11; // rdi
  HRESULT (__stdcall *ConnectServer)(IWbemLocator *, const BSTR, const BSTR, const BSTR, const BSTR, int, const BSTR, IWbemContext *, IWbemServices **); // rax
  signed int NamespaceSD; // esi
  signed int LastError; // eax
  signed int v15; // eax
  HRESULT (__stdcall *v16)(IWbemLocator *, const BSTR, const BSTR, const BSTR, const BSTR, int, const BSTR, IWbemContext *, IWbemServices **); // rax
  signed int v17; // eax
  const unsigned __int16 *v18; // r8
  BSTR bstrString; // [rsp+50h] [rbp-28h] BYREF
  __int64 v21; // [rsp+58h] [rbp-20h] BYREF
  void *TokenHandle[3]; // [rsp+60h] [rbp-18h] BYREF
  __int64 v23; // [rsp+D8h] [rbp+60h] BYREF

  TokenHandle[0] = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x2000Cu, 1, TokenHandle) )
  {
LABEL_7:
    CDebugWrapper::Msg(
      (CDebugWrapper *)dbgRsop,
      4u,
      L"CopyNameSpaceSecurity: Copying Sec Desc from <%s> -> <%s>.",
      a1,
      a2);
    XBStr::XBStr((XBStr *)&bstrString, a1);
    v9 = bstrString;
    if ( !bstrString )
    {
      CDebugWrapper::Msg((CDebugWrapper *)dbgRsop, 2u, L"CopyNameSpaceSecurity: Function failed to allocate memory.");
      v10 = 0;
LABEL_9:
      SysFreeString(v10);
      v8 = -2147024882;
      goto LABEL_38;
    }
    XBStr::XBStr((XBStr *)&bstrString, a2);
    v11 = bstrString;
    if ( !bstrString )
    {
      CDebugWrapper::Msg((CDebugWrapper *)dbgRsop, 2u, L"CopyNameSpaceSecurity: Function failed to allocate memory.");
      SysFreeString(0);
      v10 = v9;
      goto LABEL_9;
    }
    ConnectServer = a3->lpVtbl->ConnectServer;
    v23 = 0;
    NamespaceSD = ((__int64 (__fastcall *)(struct IWbemLocator *, OLECHAR *, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, __int64 *))ConnectServer)(
                    a3,
                    v9,
                    0,
                    0,
                    0,
                    0,
                    0,
                    0,
                    &v23);
    if ( !SetThreadToken(0, TokenHandle[0]) )
    {
      LastError = GetLastError();
      NamespaceSD = LastError;
      if ( LastError > 0 )
        NamespaceSD = (unsigned __int16)LastError | 0x80070000;
      CDebugWrapper::Msg(
        (CDebugWrapper *)dbgRsop,
        2u,
        L"CopyNameSpaceSecurity: SetThreadToken failed for src. hr=0x%08X",
        (unsigned int)NamespaceSD);
      goto LABEL_16;
    }
    if ( NamespaceSD < 0 )
    {
      CDebugWrapper::Msg(
        (CDebugWrapper *)dbgRsop,
        2u,
        L"CopyNameSpaceSecurity: ConnectServer failed for src. hr=0x%08X",
        (unsigned int)NamespaceSD);
LABEL_16:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
      SysFreeString(v11);
      SysFreeString(v9);
      v8 = NamespaceSD;
      goto LABEL_38;
    }
    bstrString = 0;
    NamespaceSD = GetNamespaceSD(v23, &bstrString);
    if ( !SetThreadToken(0, TokenHandle[0]) )
    {
      v15 = GetLastError();
      NamespaceSD = v15;
      if ( v15 > 0 )
        NamespaceSD = (unsigned __int16)v15 | 0x80070000;
      CDebugWrapper::Msg(
        (CDebugWrapper *)dbgRsop,
        2u,
        L"CopyNameSpaceSecurity: SetThreadToken failed for src. hr=0x%08X",
        (unsigned int)NamespaceSD);
      goto LABEL_23;
    }
    if ( NamespaceSD < 0 )
    {
      CDebugWrapper::Msg(
        (CDebugWrapper *)dbgRsop,
        2u,
        L"CopyNameSpaceSecurity: GetNameSpaceSD failed for src. hr=0x%08X",
        (unsigned int)NamespaceSD);
LABEL_23:
      XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&bstrString);
      goto LABEL_16;
    }
    v16 = a3->lpVtbl->ConnectServer;
    v21 = 0;
    NamespaceSD = ((__int64 (__fastcall *)(struct IWbemLocator *, OLECHAR *, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, __int64 *))v16)(
                    a3,
                    v11,
                    0,
                    0,
                    0,
                    0,
                    0,
                    0,
                    &v21);
    if ( SetThreadToken(0, TokenHandle[0]) )
    {
      if ( NamespaceSD < 0 )
      {
        v18 = L"CopyNameSpaceSecurity: ConnectServer failed for Dst. hr=0x%08X";
LABEL_30:
        CDebugWrapper::Msg((CDebugWrapper *)dbgRsop, 2u, v18, (unsigned int)NamespaceSD);
LABEL_31:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v21);
        goto LABEL_23;
      }
      NamespaceSD = SetNamespaceSD(bstrString);
      if ( SetThreadToken(0, TokenHandle[0]) )
      {
        if ( NamespaceSD >= 0 )
        {
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v21);
          XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&bstrString);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
          SysFreeString(v11);
          SysFreeString(v9);
          v8 = 0;
          goto LABEL_38;
        }
        CDebugWrapper::Msg(
          (CDebugWrapper *)dbgRsop,
          4u,
          L"CopyNameSpaceSecurity: SetNamespaceSD failed on Dst, 0x%08X",
          (unsigned int)NamespaceSD);
        goto LABEL_31;
      }
    }
    v17 = GetLastError();
    NamespaceSD = v17;
    if ( v17 > 0 )
      NamespaceSD = (unsigned __int16)v17 | 0x80070000;
    v18 = L"CopyNameSpaceSecurity: SetThreadToken failed for src. hr=0x%08X";
    goto LABEL_30;
  }
  v7 = GetLastError();
  v8 = v7;
  if ( v7 > 0 )
    v8 = (unsigned __int16)v7 | 0x80070000;
  if ( v8 == -2147023888 )
  {
    CDebugWrapper::Msg((CDebugWrapper *)dbgRsop, 4u, L"CopyNameSpaceSecurity: Openthreadtoken failed with error 0x%x.");
    goto LABEL_7;
  }
  CDebugWrapper::Msg(
    (CDebugWrapper *)dbgRsop,
    2u,
    L"CopyNameSpaceSecurity: Openthreadtoken failed with error 0x%x.",
    v8);
LABEL_38:
  XHandle::~XHandle(TokenHandle);
  return v8;
}

```

## disassembly

```asm
0x180070b54  push    rbp
0x180070b56  push    rbx
0x180070b57  push    rsi
0x180070b58  push    rdi
0x180070b59  push    r12
0x180070b5b  push    r13
0x180070b5d  push    r14
0x180070b5f  push    r15
0x180070b61  mov     rbp, rsp
0x180070b64  sub     rsp, 78h
0x180070b68  xor     r15d, r15d
0x180070b6b  mov     r14, r8
0x180070b6e  mov     [rbp+TokenHandle], r15
0x180070b72  mov     rdi, rdx
0x180070b75  mov     rsi, rcx
0x180070b78  call    cs:__imp_GetCurrentThread
0x180070b7e  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180070b82  mov     edx, 2000Ch; DesiredAccess
0x180070b87  mov     rcx, rax; ThreadHandle
0x180070b8a  lea     r8d, [r15+1]; OpenAsSelf
0x180070b8e  call    cs:__imp_OpenThreadToken
0x180070b94  mov     r13d, 80070000h
0x180070b9a  lea     r12, ?dbgRsop@@3VCDebugWrapper@@A; CDebugWrapper dbgRsop
0x180070ba1  test    eax, eax
0x180070ba3  jnz     short loc_180070BE8
0x180070ba5  call    cs:__imp_GetLastError
0x180070bab  mov     ebx, eax
0x180070bad  test    eax, eax
0x180070baf  jle     short loc_180070BB7
0x180070bb1  movzx   ebx, ax
0x180070bb4  or      ebx, r13d
0x180070bb7  mov     r9d, 800703F0h
0x180070bbd  lea     r8, aCopynamespaces_2; "CopyNameSpaceSecurity: Openthreadtoken "...
0x180070bc4  mov     rcx, r12; this
0x180070bc7  cmp     ebx, r9d
0x180070bca  jz      short loc_180070BDE
0x180070bcc  mov     r9d, ebx
0x180070bcf  mov     edx, 2; unsigned int
0x180070bd4  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x180070bd9  jmp     loc_180070E6B
0x180070bde  mov     edx, 4; unsigned int
0x180070be3  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x180070be8  mov     r9, rsi
0x180070beb  mov     [rsp+78h+var_58], rdi
0x180070bf0  lea     r8, aCopynamespaces_1; "CopyNameSpaceSecurity: Copying Sec Desc"...
0x180070bf7  mov     edx, 4; unsigned int
0x180070bfc  mov     rcx, r12; this
0x180070bff  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x180070c04  mov     rdx, rsi; unsigned __int16 *
0x180070c07  lea     rcx, [rbp+bstrString]; this
0x180070c0b  call    ??0XBStr@@QEAA@PEBG@Z; XBStr::XBStr(ushort const *)
0x180070c10  mov     rbx, [rbp+bstrString]
0x180070c14  test    rbx, rbx
0x180070c17  jnz     short loc_180070C3D
0x180070c19  lea     r8, aCopynamespaces_3; "CopyNameSpaceSecurity: Function failed "...
0x180070c20  mov     rcx, r12; this
0x180070c23  lea     edx, [rbx+2]; unsigned int
0x180070c26  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x180070c2b  xor     ecx, ecx; bstrString
0x180070c2d  call    cs:__imp_SysFreeString
0x180070c33  mov     ebx, 8007000Eh
0x180070c38  jmp     loc_180070E6B
0x180070c3d  mov     rdx, rdi; unsigned __int16 *
0x180070c40  lea     rcx, [rbp+bstrString]; this
0x180070c44  call    ??0XBStr@@QEAA@PEBG@Z; XBStr::XBStr(ushort const *)
0x180070c49  mov     rdi, [rbp+bstrString]
0x180070c4d  test    rdi, rdi
0x180070c50  jnz     short loc_180070C71
0x180070c52  lea     r8, aCopynamespaces_3; "CopyNameSpaceSecurity: Function failed "...
0x180070c59  mov     rcx, r12; this
0x180070c5c  lea     edx, [rdi+2]; unsigned int
0x180070c5f  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x180070c64  xor     ecx, ecx; bstrString
0x180070c66  call    cs:__imp_SysFreeString
0x180070c6c  mov     rcx, rbx
0x180070c6f  jmp     short loc_180070C2D
0x180070c71  mov     rax, [r14]
0x180070c74  lea     rcx, [rbp+arg_18]
0x180070c78  mov     [rsp+78h+var_38], rcx
0x180070c7d  xor     r9d, r9d
0x180070c80  mov     [rsp+78h+var_40], r15
0x180070c85  xor     r8d, r8d
0x180070c88  mov     [rsp+78h+var_48], r15
0x180070c8d  mov     rdx, rbx
0x180070c90  mov     rax, [rax+18h]
0x180070c94  mov     rcx, r14
0x180070c97  mov     [rsp+78h+var_50], r15d
0x180070c9c  mov     [rsp+78h+var_58], r15
0x180070ca1  mov     [rbp+arg_18], r15
0x180070ca5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070caa  mov     rdx, [rbp+TokenHandle]; Token
0x180070cae  xor     ecx, ecx; Thread
0x180070cb0  mov     esi, eax
0x180070cb2  call    cs:__imp_SetThreadToken
0x180070cb8  test    eax, eax
0x180070cba  jnz     short loc_180070D07
0x180070cbc  call    cs:__imp_GetLastError
0x180070cc2  mov     esi, eax
0x180070cc4  test    eax, eax
0x180070cc6  jle     short loc_180070CCE
0x180070cc8  movzx   esi, ax
0x180070ccb  or      esi, r13d
0x180070cce  lea     r8, aCopynamespaces; "CopyNameSpaceSecurity: SetThreadToken f"...
0x180070cd5  mov     r9d, esi
0x180070cd8  mov     edx, 2; unsigned int
0x180070cdd  mov     rcx, r12; this
0x180070ce0  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x180070ce5  lea     rcx, [rbp+arg_18]
0x180070ce9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180070cee  mov     rcx, rdi; bstrString
0x180070cf1  call    cs:__imp_SysFreeString
0x180070cf7  mov     rcx, rbx; bstrString
0x180070cfa  call    cs:__imp_SysFreeString
0x180070d00  mov     ebx, esi
0x180070d02  jmp     loc_180070E6B
0x180070d07  test    esi, esi
0x180070d09  jns     short loc_180070D14
0x180070d0b  lea     r8, aCopynamespaces_6; "CopyNameSpaceSecurity: ConnectServer fa"...
0x180070d12  jmp     short loc_180070CD5
0x180070d14  mov     rcx, [rbp+arg_18]
0x180070d18  lea     rdx, [rbp+bstrString]
0x180070d1c  mov     [rbp+bstrString], r15
0x180070d20  call    GetNamespaceSD
0x180070d25  mov     rdx, [rbp+TokenHandle]; Token
0x180070d29  xor     ecx, ecx; Thread
0x180070d2b  mov     esi, eax
0x180070d2d  call    cs:__imp_SetThreadToken
0x180070d33  test    eax, eax
0x180070d35  jnz     short loc_180070D6E
0x180070d37  call    cs:__imp_GetLastError
0x180070d3d  mov     esi, eax
0x180070d3f  test    eax, eax
0x180070d41  jle     short loc_180070D49
0x180070d43  movzx   esi, ax
0x180070d46  or      esi, r13d
0x180070d49  lea     r8, aCopynamespaces; "CopyNameSpaceSecurity: SetThreadToken f"...
0x180070d50  mov     r9d, esi
0x180070d53  mov     edx, 2; unsigned int
0x180070d58  mov     rcx, r12; this
0x180070d5b  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x180070d60  lea     rcx, [rbp+bstrString]
0x180070d64  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x180070d69  jmp     loc_180070CE5
0x180070d6e  test    esi, esi
0x180070d70  jns     short loc_180070D7B
0x180070d72  lea     r8, aCopynamespaces_4; "CopyNameSpaceSecurity: GetNameSpaceSD f"...
0x180070d79  jmp     short loc_180070D50
0x180070d7b  mov     rax, [r14]
0x180070d7e  lea     rcx, [rbp+var_20]
0x180070d82  mov     [rsp+78h+var_38], rcx
0x180070d87  xor     r9d, r9d
0x180070d8a  mov     [rsp+78h+var_40], r15
0x180070d8f  xor     r8d, r8d
0x180070d92  mov     [rsp+78h+var_48], r15
0x180070d97  mov     rdx, rdi
0x180070d9a  mov     rax, [rax+18h]
0x180070d9e  mov     rcx, r14
0x180070da1  mov     [rsp+78h+var_50], r15d
0x180070da6  mov     [rsp+78h+var_58], r15
0x180070dab  mov     [rbp+var_20], r15
0x180070daf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070db4  mov     rdx, [rbp+TokenHandle]; Token
0x180070db8  xor     ecx, ecx; Thread
0x180070dba  mov     esi, eax
0x180070dbc  call    cs:__imp_SetThreadToken
0x180070dc2  test    eax, eax
0x180070dc4  jnz     short loc_180070DFD
0x180070dc6  call    cs:__imp_GetLastError
0x180070dcc  mov     esi, eax
0x180070dce  test    eax, eax
0x180070dd0  jle     short loc_180070DD8
0x180070dd2  movzx   esi, ax
0x180070dd5  or      esi, r13d
0x180070dd8  lea     r8, aCopynamespaces; "CopyNameSpaceSecurity: SetThreadToken f"...
0x180070ddf  mov     edx, 2; unsigned int
0x180070de4  mov     r9d, esi
0x180070de7  mov     rcx, r12; this
0x180070dea  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x180070def  lea     rcx, [rbp+var_20]
0x180070df3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180070df8  jmp     loc_180070D60
0x180070dfd  test    esi, esi
0x180070dff  jns     short loc_180070E0A
0x180070e01  lea     r8, aCopynamespaces_5; "CopyNameSpaceSecurity: ConnectServer fa"...
0x180070e08  jmp     short loc_180070DDF
0x180070e0a  mov     rdx, [rbp+var_20]
0x180070e0e  mov     rcx, [rbp+bstrString]; Src
0x180070e12  call    SetNamespaceSD
0x180070e17  mov     rdx, [rbp+TokenHandle]; Token
0x180070e1b  xor     ecx, ecx; Thread
0x180070e1d  mov     esi, eax
0x180070e1f  call    cs:__imp_SetThreadToken
0x180070e25  test    eax, eax
0x180070e27  jz      short loc_180070DC6
0x180070e29  test    esi, esi
0x180070e2b  jns     short loc_180070E3B
0x180070e2d  lea     r8, aCopynamespaces_0; "CopyNameSpaceSecurity: SetNamespaceSD f"...
0x180070e34  mov     edx, 4
0x180070e39  jmp     short loc_180070DE4
0x180070e3b  lea     rcx, [rbp+var_20]
0x180070e3f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180070e44  lea     rcx, [rbp+bstrString]
0x180070e48  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x180070e4d  lea     rcx, [rbp+arg_18]
0x180070e51  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180070e56  mov     rcx, rdi; bstrString
0x180070e59  call    cs:__imp_SysFreeString
0x180070e5f  mov     rcx, rbx; bstrString
0x180070e62  call    cs:__imp_SysFreeString
0x180070e68  mov     ebx, r15d
0x180070e6b  lea     rcx, [rbp+TokenHandle]; this
0x180070e6f  call    ??1XHandle@@QEAA@XZ; XHandle::~XHandle(void)
0x180070e74  mov     eax, ebx
0x180070e76  add     rsp, 78h
0x180070e7a  pop     r15
0x180070e7c  pop     r14
0x180070e7e  pop     r13
0x180070e80  pop     r12
0x180070e82  pop     rdi
0x180070e83  pop     rsi
0x180070e84  pop     rbx
0x180070e85  pop     rbp
0x180070e86  retn
```
