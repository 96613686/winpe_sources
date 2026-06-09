# CModernShareCommand::GetCloudProviderShareHandlerFromId(ushort const *,IExplorerCommand * *)

- ea: `0x180041d64`
- end: `0x180042018`
- name: `?GetCloudProviderShareHandlerFromId@CModernShareCommand@@QEAAJPEBGPEAPEAUIExplorerCommand@@@Z`
- size: `692`
- prototype: `__int64 __fastcall(CModernShareCommand *__hidden this, const unsigned __int16 *, struct IExplorerCommand **)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001f880`
- `0x18003d22c`

## callees

- `0x180008900`
- `0x18001a258`
- `0x18001ade4`
- `0x18001c064`
- `0x18001d18c`
- `0x1800214cc`
- `0x180021618`
- `0x18002cdd0`
- `0x180041d64`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180041e7a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180041e7a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180041f7e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180041f7e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180041ead`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180041ead`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180041dac`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180041dac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041e2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041f39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041fe7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041e2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041f39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041fe7`

## string_xrefs

- `0x180041dbf`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`
- `0x180041e12`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`
- `0x180041f15`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CModernShareCommand::GetCloudProviderShareHandlerFromId(
        RTL_SRWLOCK *this,
        const unsigned __int16 *a2,
        struct IExplorerCommand **a3)
{
  HRESULT v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rax
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, __int64); // rbx
  __int64 v13; // rax
  RTL_SRWLOCK *v14; // rdi
  struct IExplorerCommand **v15; // rbx
  LPCWCH *v16; // r15
  int v17; // r14d
  __int64 v18; // rdx
  struct IExplorerCommand *v19; // rdi
  int ppv; // [rsp+20h] [rbp-30h]
  __int64 v22; // [rsp+30h] [rbp-20h] BYREF
  struct IExplorerCommand *v23; // [rsp+38h] [rbp-18h] BYREF
  LPVOID v24; // [rsp+40h] [rbp-10h] BYREF
  RTL_SRWLOCK *v25; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  LPVOID pv; // [rsp+90h] [rbp+40h] BYREF
  __int64 v28; // [rsp+98h] [rbp+48h] BYREF

  *a3 = 0;
  v24 = 0;
  v6 = CoCreateInstance(&CLSID_SyncRootManager, 0, 1u, &GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64, &v24);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x885,
      (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
      (const char *)(unsigned int)v6,
      ppv);
    goto LABEL_26;
  }
  v28 = 0;
  pv = 0;
  v8 = *(_QWORD *)v24;
  v28 = 0;
  v9 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, __int64 *))(v8 + 24))(v24, a2, &v28);
  v7 = v9;
  if ( v9 < 0 )
  {
    v10 = 2185;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
      (const char *)(unsigned int)v9,
      ppv);
    if ( pv )
      CoTaskMemFree(pv);
    wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(&v28);
    goto LABEL_26;
  }
  v11 = v28;
  v12 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v28 + 40LL);
  v13 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pv);
  v9 = v12(v11, v13);
  v7 = v9;
  if ( v9 < 0 )
  {
    v10 = 2186;
    goto LABEL_5;
  }
  v14 = this + 24;
  AcquireSRWLockShared(this + 24);
  v23 = (struct IExplorerCommand *)&this[24];
  v15 = (struct IExplorerCommand **)&this[25];
  v16 = (LPCWCH *)&this[26];
  if ( this[25].Ptr && CompareStringOrdinal(*v16, -1, (LPCWCH)pv, -1, 1) == 2 )
  {
    *a3 = *v15;
    Microsoft::WRL::ComPtr<IExplorerCommand>::InternalAddRef(&this[25]);
    *a3 = *v15;
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v23);
LABEL_23:
    if ( pv )
      CoTaskMemFree(pv);
    wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(&v28);
    v7 = 0;
    goto LABEL_26;
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v23);
  v22 = 0;
  v17 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v28)(
          v28,
          &GUID_884abcd3_5446_45ff_9226_e95d8e2a7006,
          &v22);
  if ( v17 >= 0 )
  {
    v17 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, struct IExplorerCommand **))(*(_QWORD *)v22 + 32LL))(
            v22,
            0,
            &IID_IExplorerCommand,
            a3);
    if ( v17 >= 0 )
    {
      AcquireSRWLockExclusive(v14);
      v25 = v14;
      v19 = *a3;
      if ( *v15 != *a3 )
      {
        v23 = *a3;
        Microsoft::WRL::ComPtr<IExplorerCommand>::InternalAddRef(&v23);
        v23 = *v15;
        *v15 = v19;
        Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v23);
      }
      Microsoft::WRL::ComPtr<IExplorerCommand>::InternalAddRef(v15);
      *a3 = *v15;
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::swap(
        v16,
        &pv);
      CAutoSRWExclusiveLock::~CAutoSRWExclusiveLock((CAutoSRWExclusiveLock *)&v25);
      wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(&v22);
      goto LABEL_23;
    }
    v18 = 2202;
  }
  else
  {
    v18 = 2201;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v18,
    (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
    (const char *)(unsigned int)v17,
    ppv);
  wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(&v22);
  if ( pv )
    CoTaskMemFree(pv);
  wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(&v28);
  v7 = v17;
LABEL_26:
  wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(&v24);
  return v7;
}

```

## disassembly

```asm
0x180041d64  mov     [rsp-28h+arg_0], rbx
0x180041d69  push    rbp
0x180041d6a  push    rsi
0x180041d6b  push    rdi
0x180041d6c  push    r14
0x180041d6e  push    r15
0x180041d70  mov     rbp, rsp
0x180041d73  sub     rsp, 50h
0x180041d77  mov     rsi, r8
0x180041d7a  mov     rdi, rdx
0x180041d7d  mov     r14, rcx
0x180041d80  mov     qword ptr [r8], 0
0x180041d87  mov     [rbp+var_10], 0
0x180041d8f  lea     rax, [rbp+var_10]
0x180041d93  mov     qword ptr [rsp+50h+ppv], rax; int
0x180041d98  lea     r9, _GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64; riid
0x180041d9f  xor     edx, edx; pUnkOuter
0x180041da1  lea     r8d, [rdx+1]; dwClsContext
0x180041da5  lea     rcx, CLSID_SyncRootManager; rclsid
0x180041dac  call    cs:__imp_CoCreateInstance
0x180041db2  mov     ebx, eax
0x180041db4  test    eax, eax
0x180041db6  jns     short loc_180041DD5
0x180041db8  mov     rcx, [rbp+28h]; this
0x180041dbc  mov     r9d, eax; char *
0x180041dbf  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x180041dc6  mov     edx, 885h; void *
0x180041dcb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041dd0  jmp     loc_180041FF9
0x180041dd5  mov     [rbp+arg_18], 0
0x180041ddd  mov     [rbp+pv], 0
0x180041de5  mov     rcx, [rbp+var_10]
0x180041de9  mov     rax, [rcx]
0x180041dec  mov     [rbp+arg_18], 0
0x180041df4  lea     r8, [rbp+arg_18]
0x180041df8  mov     rdx, rdi
0x180041dfb  mov     rax, [rax+18h]
0x180041dff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041e04  mov     ebx, eax
0x180041e06  test    eax, eax
0x180041e08  jns     short loc_180041E41
0x180041e0a  mov     edx, 889h; void *
0x180041e0f  mov     r9d, eax; char *
0x180041e12  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x180041e19  mov     rcx, [rbp+28h]; this
0x180041e1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041e22  nop
0x180041e23  mov     rcx, [rbp+pv]; pv
0x180041e27  test    rcx, rcx
0x180041e2a  jz      short loc_180041E33
0x180041e2c  call    cs:__imp_CoTaskMemFree
0x180041e32  nop
0x180041e33  lea     rcx, [rbp+arg_18]
0x180041e37  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x180041e3c  jmp     loc_180041FF9
0x180041e41  mov     rdi, [rbp+arg_18]
0x180041e45  mov     rax, [rdi]
0x180041e48  mov     rbx, [rax+28h]
0x180041e4c  lea     rcx, [rbp+pv]
0x180041e50  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x180041e55  mov     rdx, rax
0x180041e58  mov     rcx, rdi
0x180041e5b  mov     rax, rbx
0x180041e5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041e63  mov     ebx, eax
0x180041e65  test    eax, eax
0x180041e67  jns     short loc_180041E70
0x180041e69  mov     edx, 88Ah
0x180041e6e  jmp     short loc_180041E0F
0x180041e70  lea     rdi, [r14+0C0h]
0x180041e77  mov     rcx, rdi; SRWLock
0x180041e7a  call    cs:__imp_AcquireSRWLockShared
0x180041e80  mov     [rbp+var_18], rdi
0x180041e84  lea     rbx, [r14+0C8h]
0x180041e8b  lea     r15, [r14+0D0h]
0x180041e92  cmp     qword ptr [rbx], 0
0x180041e96  jz      short loc_180041EDA
0x180041e98  mov     [rsp+50h+ppv], 1; bIgnoreCase
0x180041ea0  or      edx, 0FFFFFFFFh; cchCount1
0x180041ea3  mov     r9d, edx; cchCount2
0x180041ea6  mov     r8, [rbp+pv]; lpString2
0x180041eaa  mov     rcx, [r15]; lpString1
0x180041ead  call    cs:__imp_CompareStringOrdinal
0x180041eb3  cmp     eax, 2
0x180041eb6  jnz     short loc_180041EDA
0x180041eb8  mov     rax, [rbx]
0x180041ebb  mov     [rsi], rax
0x180041ebe  mov     rcx, rbx
0x180041ec1  call    ?InternalAddRef@?$ComPtr@UIExplorerCommand@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IExplorerCommand>::InternalAddRef(void)
0x180041ec6  mov     rax, [rbx]
0x180041ec9  mov     [rsi], rax
0x180041ecc  lea     rcx, [rbp+var_18]
0x180041ed0  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180041ed5  jmp     loc_180041FDE
0x180041eda  lea     rcx, [rbp+var_18]
0x180041ede  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180041ee3  nop
0x180041ee4  mov     [rbp+var_20], 0
0x180041eec  mov     rcx, [rbp+arg_18]
0x180041ef0  mov     rax, [rcx]
0x180041ef3  lea     r8, [rbp+var_20]
0x180041ef7  lea     rdx, _GUID_884abcd3_5446_45ff_9226_e95d8e2a7006
0x180041efe  mov     rax, [rax]
0x180041f01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041f06  mov     r14d, eax
0x180041f09  test    eax, eax
0x180041f0b  jns     short loc_180041F51
0x180041f0d  mov     edx, 899h; void *
0x180041f12  mov     r9d, r14d; char *
0x180041f15  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x180041f1c  mov     rcx, [rbp+28h]; this
0x180041f20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041f25  nop
0x180041f26  lea     rcx, [rbp+var_20]
0x180041f2a  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x180041f2f  nop
0x180041f30  mov     rcx, [rbp+pv]; pv
0x180041f34  test    rcx, rcx
0x180041f37  jz      short loc_180041F40
0x180041f39  call    cs:__imp_CoTaskMemFree
0x180041f3f  nop
0x180041f40  lea     rcx, [rbp+arg_18]
0x180041f44  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x180041f49  mov     ebx, r14d
0x180041f4c  jmp     loc_180041FF9
0x180041f51  mov     rcx, [rbp+var_20]
0x180041f55  mov     rax, [rcx]
0x180041f58  mov     r9, rsi
0x180041f5b  lea     r8, IID_IExplorerCommand
0x180041f62  xor     edx, edx
0x180041f64  mov     rax, [rax+20h]
0x180041f68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041f6d  mov     r14d, eax
0x180041f70  test    eax, eax
0x180041f72  jns     short loc_180041F7B
0x180041f74  mov     edx, 89Ah
0x180041f79  jmp     short loc_180041F12
0x180041f7b  mov     rcx, rdi; SRWLock
0x180041f7e  call    cs:__imp_AcquireSRWLockExclusive
0x180041f84  mov     [rbp+var_8], rdi
0x180041f88  mov     rdi, [rsi]
0x180041f8b  cmp     [rbx], rdi
0x180041f8e  jz      short loc_180041FB0
0x180041f90  mov     [rbp+var_18], rdi
0x180041f94  lea     rcx, [rbp+var_18]
0x180041f98  call    ?InternalAddRef@?$ComPtr@UIExplorerCommand@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IExplorerCommand>::InternalAddRef(void)
0x180041f9d  mov     rax, [rbx]
0x180041fa0  mov     [rbp+var_18], rax
0x180041fa4  mov     [rbx], rdi
0x180041fa7  lea     rcx, [rbp+var_18]
0x180041fab  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180041fb0  mov     rcx, rbx
0x180041fb3  call    ?InternalAddRef@?$ComPtr@UIExplorerCommand@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IExplorerCommand>::InternalAddRef(void)
0x180041fb8  mov     rax, [rbx]
0x180041fbb  mov     [rsi], rax
0x180041fbe  lea     rdx, [rbp+pv]
0x180041fc2  mov     rcx, r15
0x180041fc5  call    ?swap@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAXAEAV12@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::swap(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180041fca  lea     rcx, [rbp+var_8]; this
0x180041fce  call    ??1CAutoSRWExclusiveLock@@QEAA@XZ; CAutoSRWExclusiveLock::~CAutoSRWExclusiveLock(void)
0x180041fd3  nop
0x180041fd4  lea     rcx, [rbp+var_20]
0x180041fd8  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x180041fdd  nop
0x180041fde  mov     rcx, [rbp+pv]; pv
0x180041fe2  test    rcx, rcx
0x180041fe5  jz      short loc_180041FEE
0x180041fe7  call    cs:__imp_CoTaskMemFree
0x180041fed  nop
0x180041fee  lea     rcx, [rbp+arg_18]
0x180041ff2  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x180041ff7  xor     ebx, ebx
0x180041ff9  lea     rcx, [rbp+var_10]
0x180041ffd  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x180042002  mov     eax, ebx
0x180042004  mov     rbx, [rsp+50h+arg_0]
0x18004200c  add     rsp, 50h
0x180042010  pop     r15
0x180042012  pop     r14
0x180042014  pop     rdi
0x180042015  pop     rsi
0x180042016  pop     rbp
0x180042017  retn
```
