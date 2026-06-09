# ScriptSite::QueryService(_GUID const &,_GUID const &,void * *)

- ea: `0x180052d40`
- end: `0x180053383`
- name: `?QueryService@ScriptSite@@UEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `1603`
- prototype: `__int64 __fastcall(ScriptSite *__hidden this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180027e88`
- `0x18002ac90`
- `0x18002d7e0`
- `0x180052d40`
- `0x18005338c`
- `0x180053af0`
- `0x18005f9b8`
- `0x180064034`
- `0x180068550`
- `0x18006cd68`
- `0x1800b6924`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x180052e67`
- `msvcrt!_resetstkoflw` at `0x180053037`
- `msvcrt!_resetstkoflw` at `0x180053274`
- `msvcrt!_resetstkoflw` at `0x180052e67`
- `msvcrt!_resetstkoflw` at `0x180053037`
- `msvcrt!_resetstkoflw` at `0x180053274`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180052eba`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005308a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800532c7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180052eba`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005308a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800532c7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180052e55`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180052ee6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180053025`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800530b6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180053262`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800532f3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180052e55`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180052ee6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180053025`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800530b6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180053262`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800532f3`
- `OLEAUT32!__imp_SysFreeString` at `0x180053194`
- `OLEAUT32!__imp_SysFreeString` at `0x180053194`

## pseudocode

```c
__int64 __fastcall ScriptSite::QueryService(
        ScriptSite *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        struct IInternetHostSecurityManager **a4)
{
  ScriptSite *v8; // rbx
  int v9; // r15d
  __int64 v11; // rax
  unsigned int v12; // ebx
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  struct IInternetHostSecurityManager *HostSecurityManager; // rax
  int v17; // eax
  Document *v18; // rax
  __int64 v19; // r8
  __int64 (__fastcall ***v20)(_QWORD, const struct _GUID *, struct IInternetHostSecurityManager **); // rax
  unsigned int v21; // eax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  struct IInternetHostSecurityManager *v27; // rdi
  struct IInternetHostSecurityManager *v28; // rbx
  OLECHAR *lpVtbl; // rcx
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  struct IInternetHostSecurityManager *v33; // [rsp+38h] [rbp-40h] BYREF
  _BYTE v34[56]; // [rsp+40h] [rbp-38h] BYREF
  void *v35; // [rsp+80h] [rbp+8h] BYREF
  struct IInternetHostSecurityManager **v36; // [rsp+98h] [rbp+20h]

  v36 = a4;
  v8 = (ScriptSite *)((char *)this - 32);
  v9 = ModelInit::init(v34, (*((_DWORD *)this - 4) & 4LL) == 0, a3);
  if ( v9 < 0 )
  {
    ModelInit::~ModelInit((ModelInit *)v34);
    return (unsigned int)v9;
  }
  v35 = 0;
  v11 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IInternetHostSecurityManager.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IInternetHostSecurityManager.Data1 )
    v11 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IInternetHostSecurityManager.Data4;
  if ( !v11 )
  {
    v12 = 0;
    v13 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IXMLDOMDocument.Data1;
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IXMLDOMDocument.Data1 )
      v13 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IXMLDOMDocument.Data4;
    if ( v13 )
    {
      v14 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IXMLDOMDocument2.Data1;
      if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IXMLDOMDocument2.Data1 )
        v14 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IXMLDOMDocument2.Data4;
      if ( v14 )
      {
        v15 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IHTMLDocument2.Data1;
        if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IHTMLDocument2.Data1 )
          v15 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IHTMLDocument2.Data4;
        if ( v15 )
        {
          HostSecurityManager = Processor::getHostSecurityManager(*((Processor **)this + 3));
          v17 = ((__int64 (__fastcall *)(struct IInternetHostSecurityManager *, const struct _GUID *, struct IInternetHostSecurityManager **))HostSecurityManager->lpVtbl->QueryInterface)(
                  HostSecurityManager,
                  a3,
                  a4);
          checkhr(v17);
          goto LABEL_55;
        }
      }
    }
    v18 = (Document *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 3) + 1448LL) + 400LL))(*(_QWORD *)(*((_QWORD *)this + 3) + 1448LL));
    if ( Document::getSafeURL(v18) )
    {
      v20 = (__int64 (__fastcall ***)(_QWORD, const struct _GUID *, struct IInternetHostSecurityManager **))(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 3) + 1448LL) + 400LL))(*(_QWORD *)(*((_QWORD *)this + 3) + 1448LL));
      v21 = (**v20)(v20, a3, a4);
LABEL_29:
      v12 = v21;
      goto LABEL_55;
    }
    v22 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IInternetHostSecurityManager.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IInternetHostSecurityManager.Data1 )
      v22 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IInternetHostSecurityManager.Data4;
    if ( v22 )
      goto LABEL_26;
    v23 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IInternetHostSecurityManager.Data1;
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IInternetHostSecurityManager.Data1 )
      v23 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IInternetHostSecurityManager.Data4;
    if ( v23 )
    {
LABEL_26:
      COMSafeControlRoot::getSite((COMSafeControlRoot *)(v19 + 24), &IID_IServiceProvider, &v35);
      if ( v35 )
      {
        v21 = (*(__int64 (__fastcall **)(void *, const struct _GUID *, const struct _GUID *, struct IInternetHostSecurityManager **))(*(_QWORD *)v35 + 24LL))(
                v35,
                a2,
                a3,
                a4);
        goto LABEL_29;
      }
    }
    else
    {
      v33 = 0;
      COMSafeControlRoot::getHostSecurityManager((COMSafeControlRoot *)(v19 + 24), &v33);
      if ( v33 )
      {
        *a4 = v33;
        goto LABEL_55;
      }
    }
    v12 = -2147467259;
    goto LABEL_55;
  }
  v24 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IBindHost.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IBindHost.Data1 )
    v24 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IBindHost.Data4;
  if ( v24 )
  {
    v25 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&SID_SContainerDispatch.Revision;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&SID_SContainerDispatch.Revision )
      v25 = *(_QWORD *)a2->Data4 - *(_QWORD *)SID_SContainerDispatch.SubAuthority;
    if ( v25 )
      goto LABEL_46;
    v26 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IHTMLDocument2.Data1;
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IHTMLDocument2.Data1 )
      v26 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IHTMLDocument2.Data4;
    if ( v26 )
    {
LABEL_46:
      v30 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IActiveScriptSite.Data1;
      if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IActiveScriptSite.Data1 )
        v30 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IActiveScriptSite.Data4;
      if ( !v30 )
      {
        v31 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IOleCommandTarget.Data1;
        if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IOleCommandTarget.Data1 )
          v31 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IOleCommandTarget.Data4;
        if ( !v31 )
        {
          v32 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 3) + 1448LL) + 400LL))(*(_QWORD *)(*((_QWORD *)this + 3) + 1448LL));
          COMSafeControlRoot::getSite((COMSafeControlRoot *)(v32 + 24), &IID_IServiceProvider, &v35);
          v12 = (*(__int64 (__fastcall **)(void *, const struct _GUID *, const struct _GUID *, struct IInternetHostSecurityManager **))(*(_QWORD *)v35 + 24LL))(
                  v35,
                  a2,
                  a3,
                  a4);
          if ( v35 )
          {
            (*(void (__fastcall **)(void *))(*(_QWORD *)v35 + 16LL))(v35);
            v35 = 0;
          }
          goto LABEL_55;
        }
      }
    }
    else
    {
      v33 = 0;
      if ( (int)ScriptSite::getSecureBaseURL(v8, (unsigned __int16 **)&v33) < 0 )
      {
        v12 = -2147024882;
        goto LABEL_55;
      }
      v27 = v33;
      if ( v33 )
      {
        v28 = (struct IInternetHostSecurityManager *)((char *)v8 + 72);
        lpVtbl = (OLECHAR *)v28[1].lpVtbl;
        if ( lpVtbl )
          SysFreeString(lpVtbl);
        v28[1].lpVtbl = (struct IInternetHostSecurityManagerVtbl *)v27;
        *a4 = v28;
        ((void (__fastcall *)(struct IInternetHostSecurityManager *))v28->lpVtbl->AddRef)(v28);
        v12 = 0;
        goto LABEL_55;
      }
    }
    v12 = -2147467262;
    goto LABEL_55;
  }
  v12 = (**(__int64 (__fastcall ***)(ScriptSite *, const struct _GUID *, struct IInternetHostSecurityManager **))v8)(
          v8,
          a3,
          a4);
LABEL_55:
  if ( v35 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v35 + 16LL))(v35);
  ModelInit::~ModelInit((ModelInit *)v34);
  return v12;
}

```

## disassembly

```asm
0x180052d40  mov     [rsp+arg_8], rbx
0x180052d45  mov     [rsp+arg_18], r9
0x180052d4a  push    rsi
0x180052d4b  push    rdi
0x180052d4c  push    r13
0x180052d4e  push    r14
0x180052d50  push    r15
0x180052d52  sub     rsp, 50h
0x180052d56  mov     r14, r9
0x180052d59  mov     rdi, r8
0x180052d5c  mov     rsi, rdx
0x180052d5f  mov     r13, rcx
0x180052d62  lea     rbx, [rcx-20h]
0x180052d66  mov     edx, [rbx+10h]
0x180052d69  shr     rdx, 2
0x180052d6d  not     edx
0x180052d6f  and     edx, 1
0x180052d72  lea     rcx, [rsp+78h+var_38]
0x180052d77  call    ?init@ModelInit@@QEAAJW4RentalEnum@@@Z; ModelInit::init(RentalEnum)
0x180052d7c  mov     r15d, eax
0x180052d7f  test    eax, eax
0x180052d81  jns     short loc_180052D95
0x180052d83  lea     rcx, [rsp+78h+var_38]; this
0x180052d88  call    ??1ModelInit@@QEAA@XZ; ModelInit::~ModelInit(void)
0x180052d8d  mov     eax, r15d
0x180052d90  jmp     loc_18005336E
0x180052d95  mov     [rsp+78h+arg_0], 0
0x180052da1  mov     rax, [rsi]
0x180052da4  sub     rax, qword ptr cs:IID_IInternetHostSecurityManager.Data1
0x180052dab  jnz     short loc_180052DB8
0x180052dad  mov     rax, [rsi+8]
0x180052db1  sub     rax, qword ptr cs:IID_IInternetHostSecurityManager.Data4
0x180052db8  test    rax, rax
0x180052dbb  jnz     loc_1800530F4
0x180052dc1  xor     ebx, ebx
0x180052dc3  mov     rax, [rdi]
0x180052dc6  sub     rax, qword ptr cs:IID_IXMLDOMDocument.Data1
0x180052dcd  jnz     short loc_180052DDA
0x180052dcf  mov     rax, [rdi+8]
0x180052dd3  sub     rax, qword ptr cs:IID_IXMLDOMDocument.Data4
0x180052dda  test    rax, rax
0x180052ddd  jz      loc_180052F11
0x180052de3  mov     rax, [rdi]
0x180052de6  sub     rax, qword ptr cs:IID_IXMLDOMDocument2.Data1
0x180052ded  jnz     short loc_180052DFA
0x180052def  mov     rax, [rdi+8]
0x180052df3  sub     rax, qword ptr cs:IID_IXMLDOMDocument2.Data4
0x180052dfa  test    rax, rax
0x180052dfd  jz      loc_180052F11
0x180052e03  mov     rax, [rdi]
0x180052e06  sub     rax, qword ptr cs:IID_IHTMLDocument2.Data1
0x180052e0d  jnz     short loc_180052E1A
0x180052e0f  mov     rax, [rdi+8]
0x180052e13  sub     rax, qword ptr cs:IID_IHTMLDocument2.Data4
0x180052e1a  test    rax, rax
0x180052e1d  jz      loc_180052F11
0x180052e23  mov     rcx, [r13+18h]; this
0x180052e27  call    ?getHostSecurityManager@Processor@@QEAAPEAUIInternetHostSecurityManager@@XZ; Processor::getHostSecurityManager(void)
0x180052e2c  mov     r9, rax
0x180052e2f  mov     rcx, [rax]
0x180052e32  mov     rax, [rcx]
0x180052e35  mov     r8, r14
0x180052e38  mov     rdx, rdi
0x180052e3b  mov     rcx, r9
0x180052e3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052e43  mov     ecx, eax; int
0x180052e45  call    ?checkhr@@YAXJ@Z; checkhr(long)
0x180052e4a  jmp     loc_180053349
0x180052e4f  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x180052e55  call    cs:__imp_TlsGetValue
0x180052e5b  mov     rbx, rax
0x180052e5e  cmp     dword ptr [rax+54h], 0C00000FDh
0x180052e65  jnz     short loc_180052EE0
0x180052e67  call    cs:__imp__resetstkoflw
0x180052e6d  test    eax, eax
0x180052e6f  jnz     short loc_180052EC2
0x180052e71  mov     rcx, cs:?g_pMutexGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexGC
0x180052e78  test    rcx, rcx
0x180052e7b  jz      short loc_180052E8F
0x180052e7d  cmp     [rcx+50h], rbx
0x180052e81  jnz     short loc_180052E8F
0x180052e83  mov     rax, [rcx]
0x180052e86  mov     rax, [rax+20h]
0x180052e8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052e8f  mov     rcx, cs:?g_pMutexFullGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexFullGC
0x180052e96  test    rcx, rcx
0x180052e99  jz      short loc_180052EAD
0x180052e9b  cmp     [rcx+50h], rbx
0x180052e9f  jnz     short loc_180052EAD
0x180052ea1  mov     rax, [rcx]
0x180052ea4  mov     rax, [rax+20h]
0x180052ea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052ead  xor     r9d, r9d; lpArguments
0x180052eb0  xor     r8d, r8d; nNumberOfArguments
0x180052eb3  xor     edx, edx; dwExceptionFlags
0x180052eb5  mov     ecx, 0C00000FDh; dwExceptionCode
0x180052eba  call    cs:__imp_RaiseException
0x180052ec0  jmp     short loc_180052EE0
0x180052ec2  mov     rax, [rbx+60h]
0x180052ec6  mov     [rbx+68h], rax
0x180052eca  lea     rax, ?s_cexpOutOfStack@Exception@@2V_CodebaseException@@B; _CodebaseException const Exception::s_cexpOutOfStack
0x180052ed1  mov     [rbx+60h], rax
0x180052ed5  mov     dword ptr [rbx+54h], 800703E9h
0x180052edc  mov     byte ptr [rbx+78h], 0
0x180052ee0  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x180052ee6  call    cs:__imp_TlsGetValue
0x180052eec  mov     rcx, [rax+60h]; struct Exception *
0x180052ef0  call    ?setErrorInfo@_dispatchImpl@@SAPEAVException@@PEAV2@@Z; _dispatchImpl::setErrorInfo(Exception *)
0x180052ef5  mov     rdx, rax
0x180052ef8  mov     rcx, [rax]
0x180052efb  mov     rax, [rcx+80h]
0x180052f02  mov     rcx, rdx
0x180052f05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052f0a  mov     ebx, eax
0x180052f0c  jmp     loc_180053349
0x180052f11  mov     rax, [r13+18h]
0x180052f15  mov     rcx, [rax+5A8h]
0x180052f1c  mov     rax, [rcx]
0x180052f1f  mov     rax, [rax+190h]
0x180052f26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052f2b  mov     r8, rax
0x180052f2e  mov     rcx, rax; this
0x180052f31  call    ?getSafeURL@Document@@QEAAPEAVString@@XZ; Document::getSafeURL(void)
0x180052f36  test    rax, rax
0x180052f39  jz      short loc_180052F71
0x180052f3b  mov     rax, [r13+18h]
0x180052f3f  mov     rcx, [rax+5A8h]
0x180052f46  mov     rax, [rcx]
0x180052f49  mov     rax, [rax+190h]
0x180052f50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052f55  mov     r9, rax
0x180052f58  mov     rcx, [rax]
0x180052f5b  mov     rax, [rcx]
0x180052f5e  mov     r8, r14
0x180052f61  mov     rdx, rdi
0x180052f64  mov     rcx, r9
0x180052f67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052f6c  jmp     loc_180053014
0x180052f71  mov     rax, [rsi]
0x180052f74  mov     rdx, qword ptr cs:IID_IInternetHostSecurityManager.Data1
0x180052f7b  sub     rax, rdx
0x180052f7e  mov     rcx, qword ptr cs:IID_IInternetHostSecurityManager.Data4
0x180052f85  jnz     short loc_180052F8E
0x180052f87  mov     rax, [rsi+8]
0x180052f8b  sub     rax, rcx
0x180052f8e  test    rax, rax
0x180052f91  jnz     short loc_180052FC9
0x180052f93  mov     rax, [rdi]
0x180052f96  sub     rax, rdx
0x180052f99  jnz     short loc_180052FA2
0x180052f9b  mov     rax, [rdi+8]
0x180052f9f  sub     rax, rcx
0x180052fa2  test    rax, rax
0x180052fa5  jnz     short loc_180052FC9
0x180052fa7  mov     [rsp+78h+var_40], rax
0x180052fac  lea     rcx, [r8+18h]; this
0x180052fb0  lea     rdx, [rsp+78h+var_40]; struct IInternetHostSecurityManager **
0x180052fb5  call    ?getHostSecurityManager@COMSafeControlRoot@@QEAAJPEAPEAUIInternetHostSecurityManager@@@Z; COMSafeControlRoot::getHostSecurityManager(IInternetHostSecurityManager * *)
0x180052fba  mov     rax, [rsp+78h+var_40]
0x180052fbf  test    rax, rax
0x180052fc2  jz      short loc_180052FEC
0x180052fc4  mov     [r14], rax
0x180052fc7  jmp     short loc_18005301A
0x180052fc9  lea     rcx, [r8+18h]; this
0x180052fcd  lea     r8, [rsp+78h+arg_0]; void **
0x180052fd5  lea     rdx, IID_IServiceProvider; struct _GUID *
0x180052fdc  call    ?getSite@COMSafeControlRoot@@QEAAXAEBU_GUID@@PEAPEAX@Z; COMSafeControlRoot::getSite(_GUID const &,void * *)
0x180052fe1  cmp     [rsp+78h+arg_0], 0
0x180052fea  jnz     short loc_180052FF7
0x180052fec  mov     ebx, 80004005h
0x180052ff1  mov     [rsp+78h+var_48], ebx
0x180052ff5  jmp     short loc_18005301A
0x180052ff7  mov     rcx, [rsp+78h+arg_0]
0x180052fff  mov     rax, [rcx]
0x180053002  mov     r9, r14
0x180053005  mov     r8, rdi
0x180053008  mov     rdx, rsi
0x18005300b  mov     rax, [rax+18h]
0x18005300f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053014  mov     [rsp+78h+var_48], eax
0x180053018  mov     ebx, eax
0x18005301a  jmp     loc_180053349
0x18005301f  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x180053025  call    cs:__imp_TlsGetValue
0x18005302b  mov     rbx, rax
0x18005302e  cmp     dword ptr [rax+54h], 0C00000FDh
0x180053035  jnz     short loc_1800530B0
0x180053037  call    cs:__imp__resetstkoflw
0x18005303d  test    eax, eax
0x18005303f  jnz     short loc_180053092
0x180053041  mov     rcx, cs:?g_pMutexGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexGC
0x180053048  test    rcx, rcx
0x18005304b  jz      short loc_18005305F
0x18005304d  cmp     [rcx+50h], rbx
0x180053051  jnz     short loc_18005305F
0x180053053  mov     rax, [rcx]
0x180053056  mov     rax, [rax+20h]
0x18005305a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005305f  mov     rcx, cs:?g_pMutexFullGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexFullGC
0x180053066  test    rcx, rcx
0x180053069  jz      short loc_18005307D
0x18005306b  cmp     [rcx+50h], rbx
0x18005306f  jnz     short loc_18005307D
0x180053071  mov     rax, [rcx]
0x180053074  mov     rax, [rax+20h]
0x180053078  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005307d  xor     r9d, r9d; lpArguments
0x180053080  xor     r8d, r8d; nNumberOfArguments
0x180053083  xor     edx, edx; dwExceptionFlags
0x180053085  mov     ecx, 0C00000FDh; dwExceptionCode
0x18005308a  call    cs:__imp_RaiseException
0x180053090  jmp     short loc_1800530B0
0x180053092  mov     rax, [rbx+60h]
0x180053096  mov     [rbx+68h], rax
0x18005309a  lea     rax, ?s_cexpOutOfStack@Exception@@2V_CodebaseException@@B; _CodebaseException const Exception::s_cexpOutOfStack
0x1800530a1  mov     [rbx+60h], rax
0x1800530a5  mov     dword ptr [rbx+54h], 800703E9h
0x1800530ac  mov     byte ptr [rbx+78h], 0
0x1800530b0  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x1800530b6  call    cs:__imp_TlsGetValue
0x1800530bc  mov     rcx, [rax+60h]; struct Exception *
0x1800530c0  call    ?setErrorInfo@_dispatchImpl@@SAPEAVException@@PEAV2@@Z; _dispatchImpl::setErrorInfo(Exception *)
0x1800530c5  mov     rdx, rax
0x1800530c8  mov     rcx, [rax]
0x1800530cb  mov     rax, [rcx+80h]
0x1800530d2  mov     rcx, rdx
0x1800530d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800530da  mov     ebx, eax
0x1800530dc  mov     [rsp+78h+var_48], eax
0x1800530e0  mov     rax, [rsp+78h+arg_18]
0x1800530e8  mov     qword ptr [rax], 0
0x1800530ef  jmp     loc_180053349
0x1800530f4  mov     rax, [rsi]
0x1800530f7  sub     rax, qword ptr cs:IID_IBindHost.Data1
0x1800530fe  jnz     short loc_18005310B
0x180053100  mov     rax, [rsi+8]
0x180053104  sub     rax, qword ptr cs:IID_IBindHost.Data4
0x18005310b  test    rax, rax
0x18005310e  jnz     short loc_18005312B
0x180053110  mov     rax, [rbx]
0x180053113  mov     r8, r14
0x180053116  mov     rdx, rdi
0x180053119  mov     rcx, rbx
0x18005311c  mov     rax, [rax]
0x18005311f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053124  mov     ebx, eax
0x180053126  jmp     loc_180053349
0x18005312b  mov     rax, [rsi]
0x18005312e  sub     rax, qword ptr cs:SID_SContainerDispatch.Revision
0x180053135  jnz     short loc_180053142
0x180053137  mov     rax, [rsi+8]
0x18005313b  sub     rax, qword ptr cs:SID_SContainerDispatch.SubAuthority
0x180053142  test    rax, rax
0x180053145  jnz     short loc_1800531C1
0x180053147  mov     rax, [rdi]
0x18005314a  sub     rax, qword ptr cs:IID_IHTMLDocument2.Data1
0x180053151  jnz     short loc_18005315E
0x180053153  mov     rax, [rdi+8]
0x180053157  sub     rax, qword ptr cs:IID_IHTMLDocument2.Data4
0x18005315e  test    rax, rax
0x180053161  jnz     short loc_1800531C1
0x180053163  mov     [rsp+78h+var_40], rax
0x180053168  lea     rdx, [rsp+78h+var_40]; unsigned __int16 **
0x18005316d  mov     rcx, rbx; this
0x180053170  call    ?getSecureBaseURL@ScriptSite@@IEAAJPEAPEAG@Z; ScriptSite::getSecureBaseURL(ushort * *)
0x180053175  test    eax, eax
0x180053177  js      short loc_1800531B7
0x180053179  mov     rdi, [rsp+78h+var_40]
0x18005317e  test    rdi, rdi
0x180053181  jz      loc_180053344
0x180053187  add     rbx, 48h ; 'H'
0x18005318b  mov     rcx, [rbx+8]; bstrString
0x18005318f  test    rcx, rcx
0x180053192  jz      short loc_18005319A
0x180053194  call    cs:__imp_SysFreeString
0x18005319a  mov     [rbx+8], rdi
0x18005319e  mov     [r14], rbx
0x1800531a1  mov     rax, [rbx]
0x1800531a4  mov     rcx, rbx
0x1800531a7  mov     rax, [rax+8]
0x1800531ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800531b0  xor     ebx, ebx
0x1800531b2  jmp     loc_180053349
0x1800531b7  mov     ebx, 8007000Eh
0x1800531bc  jmp     loc_180053349
0x1800531c1  mov     rax, [rsi]
0x1800531c4  sub     rax, qword ptr cs:IID_IActiveScriptSite.Data1
0x1800531cb  jnz     short loc_1800531D8
0x1800531cd  mov     rax, [rsi+8]
0x1800531d1  sub     rax, qword ptr cs:IID_IActiveScriptSite.Data4
0x1800531d8  test    rax, rax
0x1800531db  jnz     loc_180053344
0x1800531e1  mov     rax, [rdi]
0x1800531e4  sub     rax, qword ptr cs:IID_IOleCommandTarget.Data1
0x1800531eb  jnz     short loc_1800531F8
0x1800531ed  mov     rax, [rdi+8]
0x1800531f1  sub     rax, qword ptr cs:IID_IOleCommandTarget.Data4
0x1800531f8  test    rax, rax
0x1800531fb  jnz     loc_180053344
0x180053201  mov     rax, [r13+18h]
  ... truncated ...
```
