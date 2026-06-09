# OleGetAutoConvertInternal(_GUID const &,_GUID *,bool)

- ea: `0x18009a3a0`
- end: `0x18009a5b0`
- name: `?OleGetAutoConvertInternal@@YAJAEBU_GUID@@PEAU1@_N@Z`
- size: `528`
- prototype: `HRESULT __fastcall(const _GUID *clsidOld, _GUID *pClsidNew, bool clsidOld)`
- caller_count: `7`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18003ff8c`
- `0x180053188`
- `0x18007702c`
- `0x180077858`
- `0x18007cde4`
- `0x18007ed20`
- `0x18009a870`

## callees

- `0x18000e860`
- `0x18000f358`
- `0x18001217c`
- `0x18001d110`
- `0x180033bb0`
- `0x18009a3a0`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009a572`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009a572`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18009a55b`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18009a55b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18009a411`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18009a411`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009a585`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009a585`
- `api-ms-win-core-com-private-l1-3-1!InternalRegOpenClassKey` at `0x18009a4fe`
- `api-ms-win-core-com-private-l1-3-1!InternalRegOpenClassKey` at `0x18009a4fe`

## string_xrefs

- `0x18009a4be`: `com\ole32\ole232\stdimpl\olereg.cpp`
- `0x18009a514`: `com\ole32\ole232\stdimpl\olereg.cpp`

## pseudocode

```c
__int64 __fastcall OleGetAutoConvertInternal(const _GUID *clsidOld, _GUID *pClsidNew, bool a3)
{
  HRESULT v6; // eax
  unsigned int v7; // ebx
  unsigned int v8; // edx
  HRESULT v9; // eax
  int String; // eax
  IPackagedComClassCatalogInternal *m_ptr; // rdi
  HKEY__ *hkeyClsid; // [rsp+30h] [rbp-20h] BYREF
  wil::com_ptr_t<IComCatalogSCM,wil::err_returncode_policy> comCatalogScm; // [rsp+38h] [rbp-18h] BYREF
  wil::com_ptr_t<IPackagedComClassCatalogInternal,wil::err_returncode_policy> packagedComCatalog; // [rsp+40h] [rbp-10h] BYREF
  void *retaddr; // [rsp+68h] [rbp+18h]
  RegistrationSource source; // [rsp+80h] [rbp+30h] BYREF
  wil::com_ptr_t<IRegistration,wil::err_returncode_policy> registrationInfo; // [rsp+88h] [rbp+38h] BYREF

  LOBYTE(source) = a3;
  hkeyClsid = 0;
  packagedComCatalog.m_ptr = 0;
  if ( !IsValidPtrOut(pClsidNew, 0x10u) )
    return 2147942487LL;
  comCatalogScm.m_ptr = 0;
  *pClsidNew = GUID_NULL;
  if ( CoCreateInstance(
         &GUID_00000346_0000_0000_c000_000000000046,
         0,
         1u,
         &GUID_000001fd_0000_0000_c000_000000000046,
         (LPVOID *)&comCatalogScm.m_ptr) < 0 )
    goto LABEL_15;
  registrationInfo.m_ptr = 0;
  if ( GetClassInfoWithInprocOrLocalServer(
         clsidOld,
         comCatalogScm.m_ptr,
         &GUID_430be197_0244_2f7b_80fd_c7c473983ad0,
         (void **)&registrationInfo.m_ptr) < 0
    || (source = RegistrationSourceSystemRegistry,
        ((int (__fastcall *)(IRegistration *, RegistrationSource *))registrationInfo.m_ptr->lpVtbl[1].QueryInterface)(
          registrationInfo.m_ptr,
          &source) < 0)
    || source != RegistrationSourcePackagedCom )
  {
    wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>((wil::com_ptr_t<IProxyServerIdentity,wil::err_returncode_policy> *)&registrationInfo);
LABEL_15:
    v9 = InternalRegOpenClassKey(clsidOld, 131097, &hkeyClsid);
    v7 = v9;
    if ( v9 >= 0 )
    {
      String = OleRegGetString(hkeyClsid, Com::Catalog::Constants::AutoConvertTo, (wchar_t **)&packagedComCatalog);
      m_ptr = packagedComCatalog.m_ptr;
      v7 = String;
      if ( String >= 0 )
      {
        if ( LOWORD(packagedComCatalog.m_ptr->lpVtbl) )
          v7 = CLSIDFromString((LPCOLESTR)packagedComCatalog.m_ptr, pClsidNew);
        else
          v7 = -2147221166;
      }
      if ( hkeyClsid )
      {
        RegCloseKey(hkeyClsid);
        hkeyClsid = 0;
      }
      CoTaskMemFree(m_ptr);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(retaddr, 0x2F5u, "com\\ole32\\ole232\\stdimpl\\olereg.cpp", v9);
    }
    goto LABEL_24;
  }
  packagedComCatalog.m_ptr = 0;
  v6 = ((__int64 (__fastcall *)(IComCatalogSCM *, GUID *, wil::com_ptr_t<IPackagedComClassCatalogInternal,wil::err_returncode_policy> *))comCatalogScm.m_ptr->lpVtbl->QueryInterface)(
         comCatalogScm.m_ptr,
         &GUID_84066cce_9a85_496d_9444_12646c933b4a,
         &packagedComCatalog);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v6 = ((__int64 (__fastcall *)(IPackagedComClassCatalogInternal *, const _GUID *, _GUID *))packagedComCatalog.m_ptr->lpVtbl[1].Release)(
           packagedComCatalog.m_ptr,
           clsidOld,
           pClsidNew);
    v7 = v6;
    if ( v6 >= 0 )
    {
      v7 = 0;
      goto LABEL_13;
    }
    v8 = 751;
  }
  else
  {
    v8 = 749;
  }
  wil::details::in1diag3::Return_Hr(retaddr, v8, "com\\ole32\\ole232\\stdimpl\\olereg.cpp", v6);
LABEL_13:
  wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>((wil::com_ptr_t<IProxyServerIdentity,wil::err_returncode_policy> *)&packagedComCatalog);
  wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>((wil::com_ptr_t<IProxyServerIdentity,wil::err_returncode_policy> *)&registrationInfo);
LABEL_24:
  wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>((wil::com_ptr_t<IProxyServerIdentity,wil::err_returncode_policy> *)&comCatalogScm);
  return v7;
}

```

## disassembly

```asm
0x18009a3a0  mov     [rsp-18h+arg_0], rbx
0x18009a3a5  mov     [rsp-18h+arg_8], rsi
0x18009a3aa  mov     byte ptr [rsp-18h+source], r8b
0x18009a3af  push    rbp
0x18009a3b0  push    rdi
0x18009a3b1  push    r14
0x18009a3b3  mov     rbp, rsp
0x18009a3b6  sub     rsp, 50h
0x18009a3ba  xor     r14d, r14d
0x18009a3bd  mov     rsi, pClsidNew
0x18009a3c0  mov     rdi, clsidOld
0x18009a3c3  mov     [rbp+hkeyClsid], r14
0x18009a3c7  mov     clsidOld, rsi; pv
0x18009a3ca  mov     [rbp+packagedComCatalog.m_ptr], r14
0x18009a3ce  lea     edx, [r14+10h]; cb
0x18009a3d2  call    ?IsValidPtrOut@@YAHPEAX_K@Z; IsValidPtrOut(void *,unsigned __int64)
0x18009a3d7  test    eax, eax
0x18009a3d9  jnz     short loc_18009A3E5
0x18009a3db  mov     eax, 80070057h
0x18009a3e0  jmp     loc_18009A59C
0x18009a3e5  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18009a3ec  xor     edx, edx; pUnkOuter
0x18009a3ee  mov     [rbp+comCatalogScm.m_ptr], r14
0x18009a3f2  lea     rax, [rbp+comCatalogScm]
0x18009a3f6  lea     r9, _GUID_000001fd_0000_0000_c000_000000000046; riid
0x18009a3fd  mov     [rsp+50h+ppv], rax; ppv
0x18009a402  lea     clsidOld, _GUID_00000346_0000_0000_c000_000000000046; rclsid
0x18009a409  lea     r8d, [pClsidNew+1]; dwClsContext
0x18009a40d  movdqu  xmmword ptr [rsi], xmm0
0x18009a411  call    cs:__imp_CoCreateInstance
0x18009a418  nop     dword ptr [rax+rax+00h]
0x18009a41d  test    eax, eax
0x18009a41f  js      loc_18009A4F2
0x18009a425  mov     pClsidNew, [rbp+comCatalogScm.m_ptr]; pComCatalog
0x18009a429  lea     r9, [rbp+registrationInfo]; ppv
0x18009a42d  lea     r8, _GUID_430be197_0244_2f7b_80fd_c7c473983ad0; riid
0x18009a434  mov     [rbp+registrationInfo.m_ptr], r14
0x18009a438  mov     clsidOld, rdi; clsid
0x18009a43b  call    ?GetClassInfoWithInprocOrLocalServer@@YAJAEBU_GUID@@PEAUIComCatalogSCM@@0PEAPEAX@Z; GetClassInfoWithInprocOrLocalServer(_GUID const &,IComCatalogSCM *,_GUID const &,void * *)
0x18009a440  test    eax, eax
0x18009a442  js      loc_18009A4E9
0x18009a448  mov     clsidOld, [rbp+registrationInfo.m_ptr]
0x18009a44c  lea     pClsidNew, [rbp+source]
0x18009a450  mov     [rbp+source], r14d
0x18009a454  mov     rax, [clsidOld]
0x18009a457  mov     rax, [rax+18h]
0x18009a45b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a460  test    eax, eax
0x18009a462  js      loc_18009A4E9
0x18009a468  cmp     [rbp+source], 2
0x18009a46c  jnz     short loc_18009A4E9
0x18009a46e  mov     clsidOld, [rbp+comCatalogScm.m_ptr]
0x18009a472  lea     r8, [rbp+packagedComCatalog]
0x18009a476  mov     [rbp+packagedComCatalog.m_ptr], r14
0x18009a47a  lea     pClsidNew, _GUID_84066cce_9a85_496d_9444_12646c933b4a
0x18009a481  mov     rax, [clsidOld]
0x18009a484  mov     rax, [rax]
0x18009a487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a48c  mov     ebx, eax
0x18009a48e  test    eax, eax
0x18009a490  jns     short loc_18009A499
0x18009a492  mov     edx, 2EDh
0x18009a497  jmp     short loc_18009A4BA
0x18009a499  mov     clsidOld, [rbp+packagedComCatalog.m_ptr]
0x18009a49d  mov     r8, rsi
0x18009a4a0  mov     pClsidNew, rdi
0x18009a4a3  mov     rax, [clsidOld]
0x18009a4a6  mov     rax, [rax+28h]
0x18009a4aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a4af  mov     ebx, eax
0x18009a4b1  test    eax, eax
0x18009a4b3  jns     short loc_18009A4CF
0x18009a4b5  mov     edx, 2EFh; lineNumber
0x18009a4ba  mov     clsidOld, [rbp+18h]; callerReturnAddress
0x18009a4be  lea     r8, aComOle32Ole232_5; "com\\ole32\\ole232\\stdimpl\\olereg.cpp"
0x18009a4c5  mov     r9d, eax; hr
0x18009a4c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009a4cd  jmp     short loc_18009A4D2
0x18009a4cf  mov     ebx, r14d
0x18009a4d2  lea     clsidOld, [rbp+packagedComCatalog]; this
0x18009a4d6  call    ??1?$com_ptr_t@UICallFrameEvents@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>(void)
0x18009a4db  lea     clsidOld, [rbp+registrationInfo]; this
0x18009a4df  call    ??1?$com_ptr_t@UICallFrameEvents@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>(void)
0x18009a4e4  jmp     loc_18009A591
0x18009a4e9  lea     clsidOld, [rbp+registrationInfo]; this
0x18009a4ed  call    ??1?$com_ptr_t@UICallFrameEvents@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>(void)
0x18009a4f2  lea     r8, [rbp+hkeyClsid]
0x18009a4f6  mov     edx, 20019h
0x18009a4fb  mov     clsidOld, rdi
0x18009a4fe  call    cs:__imp_InternalRegOpenClassKey
0x18009a505  nop     dword ptr [rax+rax+00h]
0x18009a50a  mov     ebx, eax
0x18009a50c  test    eax, eax
0x18009a50e  jns     short loc_18009A52A
0x18009a510  mov     clsidOld, [rbp+18h]; callerReturnAddress
0x18009a514  lea     r8, aComOle32Ole232_5; "com\\ole32\\ole232\\stdimpl\\olereg.cpp"
0x18009a51b  mov     r9d, eax; hr
0x18009a51e  mov     edx, 2F5h; lineNumber
0x18009a523  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009a528  jmp     short loc_18009A591
0x18009a52a  mov     clsidOld, [rbp+hkeyClsid]; hkey
0x18009a52e  lea     r8, [rbp+packagedComCatalog]; ppszValue
0x18009a532  lea     pClsidNew, ?AutoConvertTo@Constants@Catalog@Com@@3QBGB; szKey
0x18009a539  call    OleRegGetString
0x18009a53e  mov     rdi, [rbp+packagedComCatalog.m_ptr]
0x18009a542  mov     ebx, eax
0x18009a544  test    eax, eax
0x18009a546  js      short loc_18009A569
0x18009a548  cmp     r14w, [rdi]
0x18009a54c  jnz     short loc_18009A555
0x18009a54e  mov     ebx, 80040152h
0x18009a553  jmp     short loc_18009A569
0x18009a555  mov     pClsidNew, rsi; pclsid
0x18009a558  mov     clsidOld, rdi; lpsz
0x18009a55b  call    cs:__imp_CLSIDFromString
0x18009a562  nop     dword ptr [rax+rax+00h]
0x18009a567  mov     ebx, eax
0x18009a569  mov     clsidOld, [rbp+hkeyClsid]; hKey
0x18009a56d  test    clsidOld, clsidOld
0x18009a570  jz      short loc_18009A582
0x18009a572  call    cs:__imp_RegCloseKey
0x18009a579  nop     dword ptr [rax+rax+00h]
0x18009a57e  mov     [rbp+hkeyClsid], r14
0x18009a582  mov     clsidOld, rdi; pv
0x18009a585  call    cs:__imp_CoTaskMemFree
0x18009a58c  nop     dword ptr [rax+rax+00h]
0x18009a591  lea     clsidOld, [rbp+comCatalogScm]; this
0x18009a595  call    ??1?$com_ptr_t@UICallFrameEvents@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>(void)
0x18009a59a  mov     eax, ebx
0x18009a59c  mov     rbx, [rsp+50h+arg_0]
0x18009a5a1  mov     rsi, [rsp+50h+arg_8]
0x18009a5a6  add     rsp, 50h
0x18009a5aa  pop     r14
0x18009a5ac  pop     rdi
0x18009a5ad  pop     rbp
0x18009a5ae  retn
```
