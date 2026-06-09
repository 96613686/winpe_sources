# DllGetClassObject

- ea: `0x180005610`
- end: `0x18000579b`
- name: `DllGetClassObject`
- size: `395`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180005610`
- `0x1800057b0`
- `0x18000b390`
- `0x18002c010`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x180005667`
- `RPCRT4!NdrDllGetClassObject` at `0x180005667`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  const PCInterfaceStubVtblList *pStubVtblList; // rcx
  const CLSID *pclsid; // rcx
  HRESULT ClassObject; // ebp
  __int64 v10; // rcx
  CClassFactory *v11; // rax
  int (*v12)(const struct _GUID *, void **); // rdx
  CClassFactory *v13; // rax
  CClassFactory *v14; // rdi
  __int64 v15; // rax
  __int64 v16; // rax

  if ( ppv )
  {
    pStubVtblList = aProxyFileList->pStubVtblList;
    if ( *pStubVtblList )
      pclsid = **(const CLSID ***)pStubVtblList;
    else
      pclsid = 0;
    ClassObject = NdrDllGetClassObject(rclsid, riid, ppv, (const ProxyFileInfo **)&aProxyFileList, pclsid, &gPFactory);
    if ( ClassObject != -2147221231 )
      return ClassObject;
    v10 = *(_QWORD *)&CLSID_OfflineFilesCache.Data1 - *(_QWORD *)&rclsid->Data1;
    if ( *(_QWORD *)&CLSID_OfflineFilesCache.Data1 == *(_QWORD *)&rclsid->Data1 )
      v10 = *(_QWORD *)CLSID_OfflineFilesCache.Data4 - *(_QWORD *)rclsid->Data4;
    if ( v10 )
    {
      v15 = *(_QWORD *)&CLSID_OfflineFilesWmiProvider.Data1 - *(_QWORD *)&rclsid->Data1;
      if ( *(_QWORD *)&CLSID_OfflineFilesWmiProvider.Data1 == *(_QWORD *)&rclsid->Data1 )
        v15 = *(_QWORD *)CLSID_OfflineFilesWmiProvider.Data4 - *(_QWORD *)rclsid->Data4;
      if ( v15 )
      {
        v16 = *(_QWORD *)&CLSID_ProfileNotifyHandler.Data1 - *(_QWORD *)&rclsid->Data1;
        if ( *(_QWORD *)&CLSID_ProfileNotifyHandler.Data1 == *(_QWORD *)&rclsid->Data1 )
          v16 = *(_QWORD *)CLSID_ProfileNotifyHandler.Data4 - *(_QWORD *)rclsid->Data4;
        if ( v16 )
          return ClassObject;
        ClassObject = -2147024882;
        v11 = (CClassFactory *)operator new(0x18u);
        if ( !v11 )
          return ClassObject;
        v12 = (int (*)(const struct _GUID *, void **))CProfileNotifyHandler_CreateInstance;
        goto LABEL_12;
      }
      ClassObject = -2147024882;
      v11 = (CClassFactory *)operator new(0x18u);
      if ( v11 )
      {
        v12 = (int (*)(const struct _GUID *, void **))CWmiProvider_CreateInstance;
LABEL_12:
        v13 = CClassFactory::CClassFactory(v11, v12);
        v14 = v13;
        if ( v13 )
        {
          ClassObject = (**(__int64 (__fastcall ***)(CClassFactory *, const IID *const, LPVOID *))v13)(v13, riid, ppv);
          (*(void (__fastcall **)(CClassFactory *))(*(_QWORD *)v14 + 16LL))(v14);
        }
      }
    }
    else
    {
      ClassObject = -2147024882;
      v11 = (CClassFactory *)operator new(0x18u);
      if ( v11 )
      {
        v12 = (int (*)(const struct _GUID *, void **))COfflineFilesCache::CreateInstance;
        goto LABEL_12;
      }
    }
    return ClassObject;
  }
  return -2147024809;
}

```

## disassembly

```asm
0x180005610  mov     [rsp+arg_8], rbx
0x180005615  mov     [rsp+arg_10], rsi
0x18000561a  push    rdi
0x18000561b  sub     rsp, 30h
0x18000561f  mov     rbx, r8
0x180005622  mov     rsi, rdx
0x180005625  mov     rdi, rcx
0x180005628  test    r8, r8
0x18000562b  jz      loc_180005702
0x180005631  mov     rax, cs:aProxyFileList
0x180005638  mov     [rsp+38h+arg_0], rbp
0x18000563d  mov     rcx, [rax+8]
0x180005641  mov     rax, [rcx]
0x180005644  test    rax, rax
0x180005647  jz      short loc_18000568D
0x180005649  mov     rcx, [rax]
0x18000564c  lea     rax, gPFactory
0x180005653  mov     [rsp+38h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x180005658  lea     r9, aProxyFileList; pProxyFileList
0x18000565f  mov     [rsp+38h+pclsid], rcx; pclsid
0x180005664  mov     rcx, rdi; rclsid
0x180005667  call    cs:__imp_NdrDllGetClassObject
0x18000566d  mov     ebp, eax
0x18000566f  cmp     eax, 80040111h
0x180005674  jz      short loc_180005691
0x180005676  mov     eax, ebp
0x180005678  mov     rbp, [rsp+38h+arg_0]
0x18000567d  mov     rbx, [rsp+38h+arg_8]
0x180005682  mov     rsi, [rsp+38h+arg_10]
0x180005687  add     rsp, 30h
0x18000568b  pop     rdi
0x18000568c  retn
0x18000568d  xor     ecx, ecx
0x18000568f  jmp     short loc_18000564C
0x180005691  mov     rcx, qword ptr cs:CLSID_OfflineFilesCache.Data1
0x180005698  sub     rcx, [rdi]
0x18000569b  jnz     short loc_1800056A8
0x18000569d  mov     rcx, qword ptr cs:CLSID_OfflineFilesCache.Data4
0x1800056a4  sub     rcx, [rdi+8]
0x1800056a8  test    rcx, rcx
0x1800056ab  jnz     short loc_180005717
0x1800056ad  mov     ecx, 18h; Size
0x1800056b2  mov     ebp, 8007000Eh
0x1800056b7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800056bc  test    rax, rax
0x1800056bf  jz      short loc_180005676
0x1800056c1  lea     rdx, ?CreateInstance@COfflineFilesCache@@SAJAEBU_GUID@@PEAPEAX@Z; int (*)(const struct _GUID *, void **)
0x1800056c8  mov     rcx, rax; this
0x1800056cb  call    ??0CClassFactory@@AEAA@P6AJAEBU_GUID@@PEAPEAX@Z@Z; CClassFactory::CClassFactory(long (*)(_GUID const &,void * *))
0x1800056d0  mov     rdi, rax
0x1800056d3  test    rax, rax
0x1800056d6  jz      short loc_180005676
0x1800056d8  mov     rcx, [rax]
0x1800056db  mov     r8, rbx
0x1800056de  mov     rdx, rsi
0x1800056e1  mov     rax, [rcx]
0x1800056e4  mov     rcx, rdi
0x1800056e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056ec  mov     rcx, [rdi]
0x1800056ef  mov     ebp, eax
0x1800056f1  mov     rax, [rcx+10h]
0x1800056f5  mov     rcx, rdi
0x1800056f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056fd  jmp     loc_180005676
0x180005702  mov     rbx, [rsp+38h+arg_8]
0x180005707  mov     eax, 80070057h
0x18000570c  mov     rsi, [rsp+38h+arg_10]
0x180005711  add     rsp, 30h
0x180005715  pop     rdi
0x180005716  retn
0x180005717  mov     rax, qword ptr cs:CLSID_OfflineFilesWmiProvider.Data1
0x18000571e  sub     rax, [rdi]
0x180005721  jnz     short loc_18000572E
0x180005723  mov     rax, qword ptr cs:CLSID_OfflineFilesWmiProvider.Data4
0x18000572a  sub     rax, [rdi+8]
0x18000572e  test    rax, rax
0x180005731  jnz     short loc_180005757
0x180005733  mov     ecx, 18h; Size
0x180005738  mov     ebp, 8007000Eh
0x18000573d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005742  test    rax, rax
0x180005745  jz      loc_180005676
0x18000574b  lea     rdx, ?CWmiProvider_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z; CWmiProvider_CreateInstance(_GUID const &,void * *)
0x180005752  jmp     loc_1800056C8
0x180005757  mov     rax, qword ptr cs:CLSID_ProfileNotifyHandler.Data1
0x18000575e  sub     rax, [rdi]
0x180005761  jnz     short loc_18000576E
0x180005763  mov     rax, qword ptr cs:CLSID_ProfileNotifyHandler.Data4
0x18000576a  sub     rax, [rdi+8]
0x18000576e  test    rax, rax
0x180005771  jnz     loc_180005676
0x180005777  mov     ecx, 18h; Size
0x18000577c  mov     ebp, 8007000Eh
0x180005781  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005786  test    rax, rax
0x180005789  jz      loc_180005676
0x18000578f  lea     rdx, ?CProfileNotifyHandler_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z; CProfileNotifyHandler_CreateInstance(_GUID const &,void * *)
0x180005796  jmp     loc_1800056C8
```
