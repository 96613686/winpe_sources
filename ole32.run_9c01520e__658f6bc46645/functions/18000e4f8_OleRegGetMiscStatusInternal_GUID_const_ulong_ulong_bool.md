# OleRegGetMiscStatusInternal(_GUID const &,ulong,ulong *,bool)

- ea: `0x18000e4f8`
- end: `0x18000e6e4`
- name: `?OleRegGetMiscStatusInternal@@YAJAEBU_GUID@@KPEAK_N@Z`
- size: `492`
- prototype: `HRESULT __fastcall(const _GUID *clsid, unsigned int dwAspect, unsigned int *pdwStatus, bool clsid)`
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000e370`
- `0x18003ea40`
- `0x1800a4010`

## callees

- `0x18000e4f8`
- `0x18000e6ec`
- `0x18000e808`
- `0x18000f358`
- `0x18001217c`
- `0x180033bb0`
- `0x18009a128`
- `0x18009a5b8`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e5cd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e5cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e5f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e6ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e5f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e6ce`
- `api-ms-win-core-com-private-l1-3-1!InternalRegOpenClassKey` at `0x18000e59e`
- `api-ms-win-core-com-private-l1-3-1!InternalRegOpenClassKey` at `0x18000e59e`

## string_xrefs

- `0x18000e62a`: `com\ole32\ole232\stdimpl\olereg.cpp`

## pseudocode

```c
__int64 __fastcall OleRegGetMiscStatusInternal(
        const _GUID *clsid,
        unsigned int dwAspect,
        unsigned int *pdwStatus,
        bool a4)
{
  unsigned int Dword; // ebx
  HRESULT MiscStatus; // eax
  IOleClassInfo *m_ptr; // rcx
  HRESULT v11; // eax
  unsigned int v12; // esi
  wil::com_ptr_t<IOleClassInfo,wil::err_returncode_policy> oleClassInfo; // [rsp+30h] [rbp-20h] BYREF
  HKEY__ *hkeyMisc; // [rsp+38h] [rbp-18h] BYREF
  HKEY__ *hkeyClsid; // [rsp+40h] [rbp-10h] BYREF
  void *retaddr; // [rsp+58h] [rbp+8h]

  oleClassInfo.m_ptr = 0;
  Dword = 0;
  hkeyClsid = 0;
  hkeyMisc = 0;
  if ( !pdwStatus )
    return (unsigned int)-2147024809;
  *pdwStatus = 0;
  MiscStatus = FusionpOleRegGetMiscStatus(clsid, dwAspect, pdwStatus);
  m_ptr = oleClassInfo.m_ptr;
  if ( MiscStatus )
  {
    oleClassInfo.m_ptr = 0;
    if ( m_ptr )
      ((void (__fastcall *)(IOleClassInfo *))m_ptr->lpVtbl->Release)(m_ptr);
    if ( GetClassInfoWithInprocOrLocalServer(
           clsid,
           0,
           &GUID_e942fe11_d674_da46_8c4f_c9568fc9d593,
           (void **)&oleClassInfo.m_ptr) >= 0 )
    {
      Dword = OleClassInfoRegGetMiscStatus(oleClassInfo.m_ptr, dwAspect, pdwStatus);
      wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>((wil::com_ptr_t<IProxyServerIdentity,wil::err_returncode_policy> *)&oleClassInfo);
      return Dword;
    }
    v11 = InternalRegOpenClassKey(clsid, 131097, &hkeyClsid);
    v12 = v11;
    if ( v11 >= 0 )
    {
      if ( !RegOpenKeyExW(hkeyClsid, Com::Catalog::Constants::MiscStatus, 0, 0x20019u, &hkeyMisc)
        && OleRegGetDword_0(hkeyMisc, dwAspect, pdwStatus) )
      {
        Dword = OleRegGetDword(hkeyMisc, 0, pdwStatus);
      }
      if ( hkeyMisc )
      {
        RegCloseKey(hkeyMisc);
        hkeyMisc = 0;
      }
      if ( hkeyClsid )
      {
        RegCloseKey(hkeyClsid);
        hkeyClsid = 0;
      }
      if ( oleClassInfo.m_ptr )
        ((void (__fastcall *)(IOleClassInfo *))oleClassInfo.m_ptr->lpVtbl->Release)(oleClassInfo.m_ptr);
      return Dword;
    }
    wil::details::in1diag3::Return_Hr(retaddr, 0x290u, "com\\ole32\\ole232\\stdimpl\\olereg.cpp", v11);
    if ( oleClassInfo.m_ptr )
      ((void (__fastcall *)(IOleClassInfo *))oleClassInfo.m_ptr->lpVtbl->Release)(oleClassInfo.m_ptr);
    return v12;
  }
  else
  {
    if ( oleClassInfo.m_ptr )
      ((void (*)(void))oleClassInfo.m_ptr->lpVtbl->Release)();
    return 0;
  }
}

```

## disassembly

```asm
0x18000e4f8  mov     rax, rsp
0x18000e4fb  mov     [rax+8], rbx
0x18000e4ff  mov     [rax+10h], rsi
0x18000e503  mov     [rax+18h], rdi
0x18000e507  mov     [rax+20h], r14
0x18000e50b  push    rbp
0x18000e50c  mov     rbp, rsp
0x18000e50f  sub     rsp, 50h
0x18000e513  and     [rbp+oleClassInfo.m_ptr], 0
0x18000e518  xor     ebx, ebx
0x18000e51a  and     [rbp+hkeyClsid], 0
0x18000e51f  mov     rdi, pdwStatus
0x18000e522  and     [rbp+hkeyMisc], 0
0x18000e527  mov     r14d, dwAspect
0x18000e52a  mov     rsi, clsid
0x18000e52d  test    pdwStatus, pdwStatus
0x18000e530  jnz     short loc_18000E554
0x18000e532  mov     ebx, 80070057h
0x18000e537  mov     eax, ebx
0x18000e539  mov     rbx, [rsp+50h+arg_0]
0x18000e53e  mov     rsi, [rsp+50h+arg_8]
0x18000e543  mov     rdi, [rsp+50h+arg_10]
0x18000e548  mov     r14, [rsp+50h+arg_18]
0x18000e54d  add     rsp, 50h
0x18000e551  pop     rbp
0x18000e552  retn
0x18000e554  and     [pdwStatus], ebx
0x18000e557  call    FusionpOleRegGetMiscStatus
0x18000e55c  mov     clsid, [rbp+oleClassInfo.m_ptr]
0x18000e560  test    eax, eax
0x18000e562  jz      loc_18000E65A
0x18000e568  and     [rbp+oleClassInfo.m_ptr], rbx
0x18000e56c  test    clsid, clsid
0x18000e56f  jnz     loc_18000E672
0x18000e575  lea     r9, [rbp+oleClassInfo]; ppv
0x18000e579  xor     dwAspect, dwAspect; pComCatalog
0x18000e57b  lea     pdwStatus, _GUID_e942fe11_d674_da46_8c4f_c9568fc9d593; riid
0x18000e582  mov     clsid, rsi; clsid
0x18000e585  call    ?GetClassInfoWithInprocOrLocalServer@@YAJAEBU_GUID@@PEAUIComCatalogSCM@@0PEAPEAX@Z; GetClassInfoWithInprocOrLocalServer(_GUID const &,IComCatalogSCM *,_GUID const &,void * *)
0x18000e58a  test    eax, eax
0x18000e58c  jns     loc_18000E683
0x18000e592  lea     pdwStatus, [rbp+hkeyClsid]
0x18000e596  mov     dwAspect, 20019h
0x18000e59b  mov     clsid, rsi
0x18000e59e  call    cs:__imp_InternalRegOpenClassKey
0x18000e5a5  nop     dword ptr [rax+rax+00h]
0x18000e5aa  mov     esi, eax
0x18000e5ac  test    eax, eax
0x18000e5ae  js      short loc_18000E626
0x18000e5b0  mov     clsid, [rbp+hkeyClsid]; hKey
0x18000e5b4  lea     rax, [rbp+hkeyMisc]
0x18000e5b8  mov     r9d, 20019h; samDesired
0x18000e5be  mov     [rsp+50h+phkResult], rax; phkResult
0x18000e5c3  xor     r8d, r8d; ulOptions
0x18000e5c6  lea     rdx, ?MiscStatus@Constants@Catalog@Com@@3QBGB; lpSubKey
0x18000e5cd  call    cs:__imp_RegOpenKeyExW
0x18000e5d4  nop     dword ptr [rax+rax+00h]
0x18000e5d9  test    eax, eax
0x18000e5db  jz      loc_18000E6A2
0x18000e5e1  mov     clsid, [rbp+hkeyMisc]; hKey
0x18000e5e5  test    clsid, clsid
0x18000e5e8  jnz     loc_18000E6CE
0x18000e5ee  mov     clsid, [rbp+hkeyClsid]; hKey
0x18000e5f2  test    clsid, clsid
0x18000e5f5  jz      short $safeRtn
0x18000e5f7  call    cs:__imp_RegCloseKey
0x18000e5fe  nop     dword ptr [rax+rax+00h]
0x18000e603  and     [rbp+hkeyClsid], 0
0x18000e608  mov     clsid, [rbp+oleClassInfo.m_ptr]
0x18000e60c  test    clsid, clsid
0x18000e60f  jz      loc_18000E537
0x18000e615  mov     rax, [clsid]
0x18000e618  mov     rax, [rax+10h]
0x18000e61c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e621  jmp     loc_18000E537
0x18000e626  mov     clsid, [rbp+8]; callerReturnAddress
0x18000e62a  lea     pdwStatus, aComOle32Ole232_5; "com\\ole32\\ole232\\stdimpl\\olereg.cpp"
0x18000e631  mov     r9d, esi; hr
0x18000e634  mov     dwAspect, 290h; lineNumber
0x18000e639  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e63e  mov     clsid, [rbp+oleClassInfo.m_ptr]
0x18000e642  test    clsid, clsid
0x18000e645  jz      short loc_18000E653
0x18000e647  mov     rdx, [clsid]
0x18000e64a  mov     rax, [rdx+10h]
0x18000e64e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e653  mov     eax, esi
0x18000e655  jmp     loc_18000E539
0x18000e65a  test    clsid, clsid
0x18000e65d  jz      short loc_18000E66B
0x18000e65f  mov     rax, [clsid]
0x18000e662  mov     rax, [rax+10h]
0x18000e666  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e66b  xor     eax, eax
0x18000e66d  jmp     loc_18000E539
0x18000e672  mov     rax, [clsid]
0x18000e675  mov     rax, [rax+10h]
0x18000e679  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e67e  jmp     loc_18000E575
0x18000e683  mov     clsid, [rbp+oleClassInfo.m_ptr]; pOleClassInfo
0x18000e687  mov     pdwStatus, rdi; pdwStatus
0x18000e68a  mov     dwAspect, r14d; dwAspect
0x18000e68d  call    OleClassInfoRegGetMiscStatus
0x18000e692  lea     clsid, [rbp+oleClassInfo]; this
0x18000e696  mov     ebx, eax
0x18000e698  call    ??1?$com_ptr_t@UICallFrameEvents@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>(void)
0x18000e69d  jmp     loc_18000E537
0x18000e6a2  mov     clsid, [rbp+hkeyMisc]; hkey
0x18000e6a6  mov     pdwStatus, rdi; pdw
0x18000e6a9  mov     dwAspect, r14d; dwKey
0x18000e6ac  call    OleRegGetDword_0
0x18000e6b1  test    eax, eax
0x18000e6b3  jz      $errRtn_2
0x18000e6b9  mov     clsid, [rbp+hkeyMisc]; hkey
0x18000e6bd  mov     pdwStatus, rdi; pdw
0x18000e6c0  xor     dwAspect, dwAspect; szKey
0x18000e6c2  call    OleRegGetDword
0x18000e6c7  mov     ebx, eax
0x18000e6c9  jmp     $errRtn_2
0x18000e6ce  call    cs:__imp_RegCloseKey
0x18000e6d5  nop     dword ptr [rax+rax+00h]
0x18000e6da  and     [rbp+hkeyMisc], 0
0x18000e6df  jmp     loc_18000E5EE
```
