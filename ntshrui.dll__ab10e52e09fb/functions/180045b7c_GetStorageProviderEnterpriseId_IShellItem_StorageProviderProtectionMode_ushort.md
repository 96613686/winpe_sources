# GetStorageProviderEnterpriseId(IShellItem *,StorageProviderProtectionMode *,ushort * *)

- ea: `0x180045b7c`
- end: `0x180045e79`
- name: `?GetStorageProviderEnterpriseId@@YAJPEAUIShellItem@@PEAW4StorageProviderProtectionMode@@PEAPEAG@Z`
- size: `765`
- prototype: `__int64 __fastcall(struct IShellItem *, enum StorageProviderProtectionMode *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180047af0`

## callees

- `0x180008900`
- `0x18001b5a0`
- `0x18001c16c`
- `0x18001d18c`
- `0x1800214cc`
- `0x180045b7c`
- `0x1800461a4`
- `0x180046a58`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180045dab`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180045dab`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180045c18`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180045c18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045be1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045d2e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045d87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045e1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045e2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045e5d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045be1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045d2e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045d87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045e1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045e2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045e5d`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall GetStorageProviderEnterpriseId(
        struct IShellItem *a1,
        enum StorageProviderProtectionMode *a2,
        unsigned __int16 **a3)
{
  unsigned __int16 **v5; // rax
  int FileSystemOrPlaceholderPath; // eax
  int v7; // ebx
  HRESULT Instance; // eax
  struct ISyncRootManager *v10; // rdi
  __int64 (__fastcall *v11)(struct ISyncRootManager *, LPVOID, struct IStorageProviderInfo **, _QWORD); // rbx
  int v12; // eax
  const struct _GUID *v13; // r8
  int SyncRootShellItem; // eax
  unsigned __int16 **v15; // rax
  int EnterpriseId; // eax
  struct IStorageProviderInfo *v17; // rdi
  __int64 (__fastcall *v18)(struct IStorageProviderInfo *, __int64); // rbx
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rbx
  bool v22; // zf
  __int64 v23; // rdx
  __int64 v24; // rcx
  void *v25; // rax
  int ppv; // [rsp+20h] [rbp-30h]
  int ppva; // [rsp+20h] [rbp-30h]
  int ppvb; // [rsp+20h] [rbp-30h]
  LPVOID v29; // [rsp+30h] [rbp-20h] BYREF
  struct IShellItem *v30; // [rsp+38h] [rbp-18h] BYREF
  LPCWCH lpString1[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  struct ISyncRootManager *v33; // [rsp+88h] [rbp+38h] BYREF
  struct IStorageProviderInfo *v34; // [rsp+90h] [rbp+40h] BYREF
  LPVOID pv; // [rsp+98h] [rbp+48h] BYREF

  *(_DWORD *)a2 = 0;
  *a3 = 0;
  pv = 0;
  v5 = (unsigned __int16 **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pv);
  FileSystemOrPlaceholderPath = GetFileSystemOrPlaceholderPath(a1, v5);
  v7 = FileSystemOrPlaceholderPath;
  if ( FileSystemOrPlaceholderPath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEF,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\StorageProviderUtils.h",
      (const char *)(unsigned int)FileSystemOrPlaceholderPath,
      ppv);
LABEL_3:
    if ( pv )
      CoTaskMemFree(pv);
    return (unsigned int)v7;
  }
  v33 = 0;
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v33);
  Instance = CoCreateInstance(
               &GUID_f324e4f9_8496_40b2_a1ff_9617c1c9affe,
               0,
               1u,
               &GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64,
               (LPVOID *)&v33);
  v7 = Instance;
  if ( Instance < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF2,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\StorageProviderUtils.h",
      (const char *)(unsigned int)Instance,
      ppva);
LABEL_8:
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v33);
    goto LABEL_3;
  }
  v34 = 0;
  v10 = v33;
  v11 = *(__int64 (__fastcall **)(struct ISyncRootManager *, LPVOID, struct IStorageProviderInfo **, _QWORD))(*(_QWORD *)v33 + 32LL);
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v34);
  ppvb = 0;
  v12 = v11(v10, pv, &v34, 0);
  v7 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF5,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\StorageProviderUtils.h",
      (const char *)(unsigned int)v12,
      0);
LABEL_11:
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v34);
    goto LABEL_8;
  }
  v30 = 0;
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v30);
  SyncRootShellItem = GetSyncRootShellItem(v33, v34, v13, (void **)&v30);
  v7 = SyncRootShellItem;
  if ( SyncRootShellItem < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF8,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\StorageProviderUtils.h",
      (const char *)(unsigned int)SyncRootShellItem,
      0);
LABEL_14:
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v30);
    goto LABEL_11;
  }
  v29 = 0;
  v15 = (unsigned __int16 **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&v29);
  EnterpriseId = IShellItem_GetEnterpriseId(v30, v15);
  v7 = EnterpriseId;
  if ( EnterpriseId < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFB,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\StorageProviderUtils.h",
      (const char *)(unsigned int)EnterpriseId,
      0);
LABEL_17:
    if ( v29 )
      CoTaskMemFree(v29);
    goto LABEL_14;
  }
  lpString1[0] = 0;
  v17 = v34;
  v18 = *(__int64 (__fastcall **)(struct IStorageProviderInfo *, __int64))(*(_QWORD *)v34 + 200LL);
  v19 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(lpString1);
  v7 = v18(v17, v19);
  if ( v7 < 0 )
  {
    v20 = 254;
    goto LABEL_21;
  }
  v21 = -1;
  v22 = CompareStringOrdinal(lpString1[0], -1, L"Personal", -1, 1) == 2;
  v25 = v29;
  if ( v22 )
  {
    if ( v29 )
    {
      v7 = -2147418113;
      v20 = 259;
      goto LABEL_21;
    }
    *(_DWORD *)a2 = 2;
  }
  else if ( v29 )
  {
    do
      ++v21;
    while ( *((_WORD *)v29 + v21) );
    v7 = _AllocStringWorker<CTCoAllocPolicy>(v24, v23, v29, v21);
    if ( v7 < 0 )
    {
      v20 = 266;
LABEL_21:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v20,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\StorageProviderUtils.h",
        (const char *)(unsigned int)v7,
        ppvb);
      if ( lpString1[0] )
        CoTaskMemFree((LPVOID)lpString1[0]);
      goto LABEL_17;
    }
    *(_DWORD *)a2 = 1;
    v25 = v29;
  }
  else
  {
    *(_DWORD *)a2 = 3;
  }
  if ( lpString1[0] )
  {
    CoTaskMemFree((LPVOID)lpString1[0]);
    v25 = v29;
  }
  if ( v25 )
    CoTaskMemFree(v25);
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v30);
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v34);
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v33);
  if ( pv )
    CoTaskMemFree(pv);
  return 0;
}

```

## disassembly

```asm
0x180045b7c  mov     [rsp-28h+arg_0], rbx
0x180045b81  push    rbp
0x180045b82  push    rsi
0x180045b83  push    rdi
0x180045b84  push    r14
0x180045b86  push    r15
0x180045b88  mov     rbp, rsp
0x180045b8b  sub     rsp, 50h
0x180045b8f  mov     r14, r8
0x180045b92  mov     rsi, rdx
0x180045b95  mov     rbx, rcx
0x180045b98  xor     r15d, r15d
0x180045b9b  mov     [rdx], r15d
0x180045b9e  mov     [r8], r15
0x180045ba1  mov     [rbp+pv], r15
0x180045ba5  lea     rcx, [rbp+pv]
0x180045ba9  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x180045bae  mov     rdx, rax; unsigned __int16 **
0x180045bb1  mov     rcx, rbx; struct IShellItem *
0x180045bb4  call    ?GetFileSystemOrPlaceholderPath@@YAJPEAUIShellItem@@PEAPEAG@Z; GetFileSystemOrPlaceholderPath(IShellItem *,ushort * *)
0x180045bb9  mov     ebx, eax
0x180045bbb  test    eax, eax
0x180045bbd  jns     short loc_180045BEE
0x180045bbf  mov     rcx, [rbp+28h]; this
0x180045bc3  mov     r9d, eax; char *
0x180045bc6  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180045bcd  mov     edx, 0EFh; void *
0x180045bd2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045bd7  nop
0x180045bd8  mov     rcx, [rbp+pv]; pv
0x180045bdc  test    rcx, rcx
0x180045bdf  jz      short loc_180045BE7
0x180045be1  call    cs:__imp_CoTaskMemFree
0x180045be7  mov     eax, ebx
0x180045be9  jmp     loc_180045E65
0x180045bee  mov     [rbp+arg_8], r15
0x180045bf2  lea     rcx, [rbp+arg_8]
0x180045bf6  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180045bfb  lea     rax, [rbp+arg_8]
0x180045bff  mov     [rsp+50h+ppv], rax; int
0x180045c04  lea     r9, _GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64; riid
0x180045c0b  xor     edx, edx; pUnkOuter
0x180045c0d  lea     r8d, [rdx+1]; dwClsContext
0x180045c11  lea     rcx, _GUID_f324e4f9_8496_40b2_a1ff_9617c1c9affe; rclsid
0x180045c18  call    cs:__imp_CoCreateInstance
0x180045c1e  mov     ebx, eax
0x180045c20  test    eax, eax
0x180045c22  jns     short loc_180045C48
0x180045c24  mov     rcx, [rbp+28h]; this
0x180045c28  mov     r9d, eax; char *
0x180045c2b  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180045c32  mov     edx, 0F2h; void *
0x180045c37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045c3c  nop
0x180045c3d  lea     rcx, [rbp+arg_8]
0x180045c41  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180045c46  jmp     short loc_180045BD8
0x180045c48  mov     [rbp+arg_10], r15
0x180045c4c  mov     rdi, [rbp+arg_8]
0x180045c50  mov     rax, [rdi]
0x180045c53  mov     rbx, [rax+20h]
0x180045c57  lea     rcx, [rbp+arg_10]
0x180045c5b  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180045c60  mov     [rsp+50h+ppv], r15; int
0x180045c65  xor     r9d, r9d
0x180045c68  lea     r8, [rbp+arg_10]
0x180045c6c  mov     rdx, [rbp+pv]
0x180045c70  mov     rcx, rdi
0x180045c73  mov     rax, rbx
0x180045c76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045c7b  mov     ebx, eax
0x180045c7d  test    eax, eax
0x180045c7f  jns     short loc_180045CA5
0x180045c81  mov     rcx, [rbp+28h]; this
0x180045c85  mov     r9d, eax; char *
0x180045c88  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180045c8f  mov     edx, 0F5h; void *
0x180045c94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045c99  nop
0x180045c9a  lea     rcx, [rbp+arg_10]
0x180045c9e  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180045ca3  jmp     short loc_180045C3D
0x180045ca5  mov     [rbp+var_18], r15
0x180045ca9  lea     rcx, [rbp+var_18]
0x180045cad  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180045cb2  lea     r9, [rbp+var_18]; void **
0x180045cb6  mov     rdx, [rbp+arg_10]; struct IStorageProviderInfo *
0x180045cba  mov     rcx, [rbp+arg_8]; struct ISyncRootManager *
0x180045cbe  call    ?GetSyncRootShellItem@@YAJPEAUISyncRootManager@@PEAUIStorageProviderInfo@@AEBU_GUID@@PEAPEAX@Z; GetSyncRootShellItem(ISyncRootManager *,IStorageProviderInfo *,_GUID const &,void * *)
0x180045cc3  mov     ebx, eax
0x180045cc5  test    eax, eax
0x180045cc7  jns     short loc_180045CED
0x180045cc9  mov     rcx, [rbp+28h]; this
0x180045ccd  mov     r9d, eax; char *
0x180045cd0  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180045cd7  mov     edx, 0F8h; void *
0x180045cdc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045ce1  nop
0x180045ce2  lea     rcx, [rbp+var_18]
0x180045ce6  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180045ceb  jmp     short loc_180045C9A
0x180045ced  mov     [rbp+var_20], r15
0x180045cf1  lea     rcx, [rbp+var_20]
0x180045cf5  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x180045cfa  mov     rdx, rax; unsigned __int16 **
0x180045cfd  mov     rcx, [rbp+var_18]; struct IShellItem *
0x180045d01  call    ?IShellItem_GetEnterpriseId@@YAJPEAUIShellItem@@PEAPEAG@Z; IShellItem_GetEnterpriseId(IShellItem *,ushort * *)
0x180045d06  mov     ebx, eax
0x180045d08  test    eax, eax
0x180045d0a  jns     short loc_180045D36
0x180045d0c  mov     rcx, [rbp+28h]; this
0x180045d10  mov     r9d, eax; char *
0x180045d13  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180045d1a  mov     edx, 0FBh; void *
0x180045d1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045d24  nop
0x180045d25  mov     rcx, [rbp+var_20]; pv
0x180045d29  test    rcx, rcx
0x180045d2c  jz      short loc_180045CE2
0x180045d2e  call    cs:__imp_CoTaskMemFree
0x180045d34  jmp     short loc_180045CE2
0x180045d36  mov     [rbp+lpString1], r15
0x180045d3a  mov     rdi, [rbp+arg_10]
0x180045d3e  mov     rax, [rdi]
0x180045d41  mov     rbx, [rax+0C8h]
0x180045d48  lea     rcx, [rbp+lpString1]
0x180045d4c  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x180045d51  mov     rdx, rax
0x180045d54  mov     rcx, rdi
0x180045d57  mov     rax, rbx
0x180045d5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045d5f  mov     ebx, eax
0x180045d61  test    eax, eax
0x180045d63  jns     short loc_180045D8F
0x180045d65  mov     edx, 0FEh; void *
0x180045d6a  mov     rcx, [rbp+28h]; this
0x180045d6e  mov     r9d, ebx; char *
0x180045d71  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180045d78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045d7d  nop
0x180045d7e  mov     rcx, [rbp+lpString1]; pv
0x180045d82  test    rcx, rcx
0x180045d85  jz      short loc_180045D25
0x180045d87  call    cs:__imp_CoTaskMemFree
0x180045d8d  jmp     short loc_180045D25
0x180045d8f  mov     dword ptr [rsp+50h+ppv], 1; bIgnoreCase
0x180045d97  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180045d9b  mov     r9d, ebx; cchCount2
0x180045d9e  lea     r8, aPersonal; "Personal"
0x180045da5  mov     edx, ebx; cchCount1
0x180045da7  mov     rcx, [rbp+lpString1]; lpString1
0x180045dab  call    cs:__imp_CompareStringOrdinal
0x180045db1  cmp     eax, 2
0x180045db4  mov     rax, [rbp+var_20]
0x180045db8  jnz     short loc_180045DD3
0x180045dba  test    rax, rax
0x180045dbd  jz      short loc_180045DCB
0x180045dbf  mov     ebx, 8000FFFFh
0x180045dc4  mov     edx, 103h
0x180045dc9  jmp     short loc_180045D6A
0x180045dcb  mov     dword ptr [rsi], 2
0x180045dd1  jmp     short loc_180045E14
0x180045dd3  test    rax, rax
0x180045dd6  jz      short loc_180045E0E
0x180045dd8  inc     rbx
0x180045ddb  cmp     [rax+rbx*2], r15w
0x180045de0  jnz     short loc_180045DD8
0x180045de2  mov     [rsp+50h+var_28], r14
0x180045de7  mov     r9, rbx
0x180045dea  mov     r8, rax
0x180045ded  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180045df2  mov     ebx, eax
0x180045df4  test    eax, eax
0x180045df6  jns     short loc_180045E02
0x180045df8  mov     edx, 10Ah
0x180045dfd  jmp     loc_180045D6A
0x180045e02  mov     dword ptr [rsi], 1
0x180045e08  mov     rax, [rbp+var_20]
0x180045e0c  jmp     short loc_180045E14
0x180045e0e  mov     dword ptr [rsi], 3
0x180045e14  mov     rcx, [rbp+lpString1]; pv
0x180045e18  test    rcx, rcx
0x180045e1b  jz      short loc_180045E27
0x180045e1d  call    cs:__imp_CoTaskMemFree
0x180045e23  mov     rax, [rbp+var_20]
0x180045e27  test    rax, rax
0x180045e2a  jz      short loc_180045E36
0x180045e2c  mov     rcx, rax; pv
0x180045e2f  call    cs:__imp_CoTaskMemFree
0x180045e35  nop
0x180045e36  lea     rcx, [rbp+var_18]
0x180045e3a  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180045e3f  nop
0x180045e40  lea     rcx, [rbp+arg_10]
0x180045e44  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180045e49  nop
0x180045e4a  lea     rcx, [rbp+arg_8]
0x180045e4e  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180045e53  nop
0x180045e54  mov     rcx, [rbp+pv]; pv
0x180045e58  test    rcx, rcx
0x180045e5b  jz      short loc_180045E63
0x180045e5d  call    cs:__imp_CoTaskMemFree
0x180045e63  xor     eax, eax
0x180045e65  mov     rbx, [rsp+50h+arg_0]
0x180045e6d  add     rsp, 50h
0x180045e71  pop     r15
0x180045e73  pop     r14
0x180045e75  pop     rdi
0x180045e76  pop     rsi
0x180045e77  pop     rbp
0x180045e78  retn
```
