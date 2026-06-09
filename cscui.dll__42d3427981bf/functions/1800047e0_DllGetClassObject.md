# DllGetClassObject

- ea: `0x1800047e0`
- end: `0x180004b4e`
- name: `DllGetClassObject`
- size: `878`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800047e0`
- `0x180004b54`
- `0x18000c1e8`
- `0x18004d010`

## import_xrefs

- `SHLWAPI!__imp_IsOS` at `0x180004842`
- `SHLWAPI!__imp_IsOS` at `0x180004842`
- `RPCRT4!NdrDllGetClassObject` at `0x18000482a`
- `RPCRT4!NdrDllGetClassObject` at `0x18000482a`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  const CLSID *pclsid; // rax
  HRESULT result; // eax
  __int64 v8; // rcx
  int (*v9)(const struct _GUID *, void **); // rbx
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  CClassFactory *v26; // rax
  CClassFactory *v27; // rax
  CClassFactory *v28; // rsi
  HRESULT v29; // ebx

  *ppv = 0;
  pclsid = (const CLSID *)*aProxyFileList->pStubVtblList;
  if ( pclsid )
    pclsid = *(const CLSID **)&pclsid->Data1;
  result = NdrDllGetClassObject(rclsid, riid, ppv, (const ProxyFileInfo **)&aProxyFileList, pclsid, &gPFactory);
  if ( result == -2147221231 )
  {
    if ( !IsOS(0x13u) )
    {
      v8 = *(_QWORD *)&rclsid->Data1 - *(_QWORD *)&CLSID_OfflineFilesFolder.Data1;
      if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_OfflineFilesFolder.Data1 )
        v8 = *(_QWORD *)rclsid->Data4 - *(_QWORD *)CLSID_OfflineFilesFolder.Data4;
      if ( !v8 )
      {
        v9 = (int (*)(const struct _GUID *, void **))OfflineFilesFolder_CreateInstance;
LABEL_72:
        v26 = (CClassFactory *)operator new(0x18u);
        if ( !v26 )
          return -2147024882;
        v27 = CClassFactory::CClassFactory(v26, v9);
        v28 = v27;
        if ( !v27 )
          return -2147024882;
        v29 = (**(__int64 (__fastcall ***)(CClassFactory *, const IID *const, LPVOID *))v27)(v27, riid, ppv);
        (*(void (__fastcall **)(CClassFactory *))(*(_QWORD *)v28 + 16LL))(v28);
        return v29;
      }
      v10 = *(_QWORD *)&rclsid->Data1 - *(_QWORD *)&CLSID_OfflineFilesControlPanel.Data1;
      if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_OfflineFilesControlPanel.Data1 )
        v10 = *(_QWORD *)rclsid->Data4 - *(_QWORD *)CLSID_OfflineFilesControlPanel.Data4;
      if ( !v10 )
      {
        v9 = (int (*)(const struct _GUID *, void **))COfflineFilesControlPanel_CreateInstance;
        goto LABEL_72;
      }
      v11 = *(_QWORD *)&rclsid->Data1 - *(_QWORD *)&CLSID_OfflineFilesLaunchSyncCenter.Data1;
      if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_OfflineFilesLaunchSyncCenter.Data1 )
        v11 = *(_QWORD *)rclsid->Data4 - *(_QWORD *)CLSID_OfflineFilesLaunchSyncCenter.Data4;
      if ( !v11 )
      {
        v9 = (int (*)(const struct _GUID *, void **))COfflineFilesLaunchSyncCenter_CreateInstance;
        goto LABEL_72;
      }
      v12 = *(_QWORD *)&rclsid->Data1 - *(_QWORD *)&CLSID_OfflineFilesManageOfflineFiles.Data1;
      if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_OfflineFilesManageOfflineFiles.Data1 )
        v12 = *(_QWORD *)rclsid->Data4 - *(_QWORD *)CLSID_OfflineFilesManageOfflineFiles.Data4;
      if ( !v12 )
      {
        v9 = (int (*)(const struct _GUID *, void **))COfflineFilesManageOfflineFiles_CreateInstance;
        goto LABEL_72;
      }
      v13 = *(_QWORD *)&rclsid->Data1 - *(_QWORD *)&CLSID_OfflineFilesContextMenuExt.Data1;
      if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_OfflineFilesContextMenuExt.Data1 )
        v13 = *(_QWORD *)rclsid->Data4 - *(_QWORD *)CLSID_OfflineFilesContextMenuExt.Data4;
      if ( !v13 )
      {
        v9 = (int (*)(const struct _GUID *, void **))CContextMenuExt_CreateInstance;
        goto LABEL_72;
      }
      v14 = *(_QWORD *)&rclsid->Data1 - *(_QWORD *)&CLSID_OfflineFilesIconOverlayExt.Data1;
      if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_OfflineFilesIconOverlayExt.Data1 )
        v14 = *(_QWORD *)rclsid->Data4 - *(_QWORD *)CLSID_OfflineFilesIconOverlayExt.Data4;
      if ( !v14 )
      {
        v9 = (int (*)(const struct _GUID *, void **))CIconOverlayExt_CreateInstance;
        goto LABEL_72;
      }
      v15 = *(_QWORD *)&rclsid->Data1 - *(_QWORD *)&CLSID_CscUpdateHandler.Data1;
      if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_CscUpdateHandler.Data1 )
        v15 = *(_QWORD *)rclsid->Data4 - *(_QWORD *)CLSID_CscUpdateHandler.Data4;
      if ( !v15 )
      {
        v9 = (int (*)(const struct _GUID *, void **))CSyncHandler_CreateInstance;
        goto LABEL_72;
      }
      v16 = *(_QWORD *)&rclsid->Data1 - *(_QWORD *)&CLSID_OfflineFilesSyncConflictStore.Data1;
      if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_OfflineFilesSyncConflictStore.Data1 )
        v16 = *(_QWORD *)rclsid->Data4 - *(_QWORD *)CLSID_OfflineFilesSyncConflictStore.Data4;
      if ( !v16 )
      {
        v9 = (int (*)(const struct _GUID *, void **))CSyncConflictStore_CreateInstance;
        goto LABEL_72;
      }
      v17 = *(_QWORD *)&rclsid->Data1 - *(_QWORD *)&CLSID_OfflineFilesPropSheetExt.Data1;
      if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_OfflineFilesPropSheetExt.Data1 )
        v17 = *(_QWORD *)rclsid->Data4 - *(_QWORD *)CLSID_OfflineFilesPropSheetExt.Data4;
      if ( !v17 )
      {
        v9 = (int (*)(const struct _GUID *, void **))COfflinePropSheetExt_CreateInstance;
        goto LABEL_72;
      }
      v18 = *(_QWORD *)&rclsid->Data1 - *(_QWORD *)&CLSID_OfflineFilesShellSvcObject.Data1;
      if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_OfflineFilesShellSvcObject.Data1 )
        v18 = *(_QWORD *)rclsid->Data4 - *(_QWORD *)CLSID_OfflineFilesShellSvcObject.Data4;
      if ( !v18 )
      {
        v9 = (int (*)(const struct _GUID *, void **))CCSCShellServiceObject_CreateInstance;
        goto LABEL_72;
      }
      v19 = *(_QWORD *)&rclsid->Data1 - *(_QWORD *)&IID_ITaskHandler.Data1;
      if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&IID_ITaskHandler.Data1 )
        v19 = *(_QWORD *)rclsid->Data4 - *(_QWORD *)IID_ITaskHandler.Data4;
      if ( !v19 )
        goto LABEL_71;
      v20 = *(_QWORD *)&rclsid->Data1 - *(_QWORD *)&CLSID_OfflineFilesBackgroundSyncHandler.Data1;
      if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_OfflineFilesBackgroundSyncHandler.Data1 )
        v20 = *(_QWORD *)rclsid->Data4 - *(_QWORD *)CLSID_OfflineFilesBackgroundSyncHandler.Data4;
      if ( !v20 )
      {
LABEL_71:
        v9 = (int (*)(const struct _GUID *, void **))COfflineFilesBackgroundSyncHandler_CreateInstance;
        goto LABEL_72;
      }
      v21 = *(_QWORD *)&rclsid->Data1 - *(_QWORD *)&CLSID_OfflineFilesSyncStatusProvider.Data1;
      if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_OfflineFilesSyncStatusProvider.Data1 )
        v21 = *(_QWORD *)rclsid->Data4 - *(_QWORD *)CLSID_OfflineFilesSyncStatusProvider.Data4;
      if ( !v21 )
      {
        v9 = (int (*)(const struct _GUID *, void **))COfflineFilesSyncStatusProvider_CreateInstance;
        goto LABEL_72;
      }
      v22 = *(_QWORD *)&rclsid->Data1 - *(_QWORD *)&CLSID_OfflineFilesSyncStatusProviderInternal.Data1;
      if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_OfflineFilesSyncStatusProviderInternal.Data1 )
        v22 = *(_QWORD *)rclsid->Data4 - *(_QWORD *)CLSID_OfflineFilesSyncStatusProviderInternal.Data4;
      if ( !v22 )
      {
        v9 = (int (*)(const struct _GUID *, void **))COfflineFilesSyncStatusProviderInternal_CreateInstance;
        goto LABEL_72;
      }
      v23 = *(_QWORD *)&rclsid->Data1 - *(_QWORD *)&CLSID_OfflineFilesWorkOfflineOnlineCommand.Data1;
      if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_OfflineFilesWorkOfflineOnlineCommand.Data1 )
        v23 = *(_QWORD *)rclsid->Data4 - *(_QWORD *)CLSID_OfflineFilesWorkOfflineOnlineCommand.Data4;
      if ( !v23 )
      {
        v9 = (int (*)(const struct _GUID *, void **))COfflineFilesWorkOfflineOnlineCommand_CreateInstance;
        goto LABEL_72;
      }
      v24 = *(_QWORD *)&rclsid->Data1 - *(_QWORD *)&CLSID_OfflineFilesSyncCommand.Data1;
      if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_OfflineFilesSyncCommand.Data1 )
        v24 = *(_QWORD *)rclsid->Data4 - *(_QWORD *)CLSID_OfflineFilesSyncCommand.Data4;
      if ( !v24 )
      {
        v9 = (int (*)(const struct _GUID *, void **))COfflineFilesSyncCommand_CreateInstance;
        goto LABEL_72;
      }
      v25 = *(_QWORD *)&rclsid->Data1 - *(_QWORD *)&CLSID_OfflineFilesMakeAvailableOffline.Data1;
      if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_OfflineFilesMakeAvailableOffline.Data1 )
        v25 = *(_QWORD *)rclsid->Data4 - *(_QWORD *)CLSID_OfflineFilesMakeAvailableOffline.Data4;
      if ( !v25 )
      {
        v9 = (int (*)(const struct _GUID *, void **))COfflineFilesMakeAvailableOfflineCommand_CreateInstance;
        goto LABEL_72;
      }
    }
    return -2147221231;
  }
  return result;
}

```

## disassembly

```asm
0x1800047e0  push    rbx
0x1800047e2  push    rbp
0x1800047e3  push    rsi
0x1800047e4  push    rdi
0x1800047e5  sub     rsp, 38h
0x1800047e9  mov     qword ptr [r8], 0
0x1800047f0  mov     rbx, rcx
0x1800047f3  mov     rax, cs:aProxyFileList
0x1800047fa  mov     rdi, r8
0x1800047fd  mov     rbp, rdx
0x180004800  mov     rcx, [rax+8]
0x180004804  mov     rax, [rcx]
0x180004807  test    rax, rax
0x18000480a  jz      short loc_18000480F
0x18000480c  mov     rax, [rax]
0x18000480f  lea     rcx, gPFactory
0x180004816  mov     [rsp+58h+pPSFactoryBuffer], rcx; pPSFactoryBuffer
0x18000481b  lea     r9, aProxyFileList; pProxyFileList
0x180004822  mov     rcx, rbx; rclsid
0x180004825  mov     [rsp+58h+pclsid], rax; pclsid
0x18000482a  call    cs:__imp_NdrDllGetClassObject
0x180004830  mov     esi, eax
0x180004832  cmp     eax, 80040111h
0x180004837  jnz     loc_180004B45
0x18000483d  mov     ecx, 13h; dwOS
0x180004842  call    cs:__imp_IsOS
0x180004848  test    eax, eax
0x18000484a  jnz     loc_180004B43
0x180004850  mov     rcx, [rbx]
0x180004853  sub     rcx, qword ptr cs:CLSID_OfflineFilesFolder.Data1
0x18000485a  jnz     short loc_180004867
0x18000485c  mov     rcx, [rbx+8]
0x180004860  sub     rcx, qword ptr cs:CLSID_OfflineFilesFolder.Data4
0x180004867  test    rcx, rcx
0x18000486a  jnz     short loc_180004878
0x18000486c  lea     rbx, ?OfflineFilesFolder_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z; OfflineFilesFolder_CreateInstance(_GUID const &,void * *)
0x180004873  jmp     loc_180004AE3
0x180004878  mov     rax, [rbx]
0x18000487b  sub     rax, qword ptr cs:CLSID_OfflineFilesControlPanel.Data1
0x180004882  jnz     short loc_18000488F
0x180004884  mov     rax, [rbx+8]
0x180004888  sub     rax, qword ptr cs:CLSID_OfflineFilesControlPanel.Data4
0x18000488f  test    rax, rax
0x180004892  jnz     short loc_1800048A0
0x180004894  lea     rbx, ?COfflineFilesControlPanel_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z; COfflineFilesControlPanel_CreateInstance(_GUID const &,void * *)
0x18000489b  jmp     loc_180004AE3
0x1800048a0  mov     rax, [rbx]
0x1800048a3  sub     rax, qword ptr cs:CLSID_OfflineFilesLaunchSyncCenter.Data1
0x1800048aa  jnz     short loc_1800048B7
0x1800048ac  mov     rax, [rbx+8]
0x1800048b0  sub     rax, qword ptr cs:CLSID_OfflineFilesLaunchSyncCenter.Data4
0x1800048b7  test    rax, rax
0x1800048ba  jnz     short loc_1800048C8
0x1800048bc  lea     rbx, ?COfflineFilesLaunchSyncCenter_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z; COfflineFilesLaunchSyncCenter_CreateInstance(_GUID const &,void * *)
0x1800048c3  jmp     loc_180004AE3
0x1800048c8  mov     rax, [rbx]
0x1800048cb  sub     rax, qword ptr cs:CLSID_OfflineFilesManageOfflineFiles.Data1
0x1800048d2  jnz     short loc_1800048DF
0x1800048d4  mov     rax, [rbx+8]
0x1800048d8  sub     rax, qword ptr cs:CLSID_OfflineFilesManageOfflineFiles.Data4
0x1800048df  test    rax, rax
0x1800048e2  jnz     short loc_1800048F0
0x1800048e4  lea     rbx, ?COfflineFilesManageOfflineFiles_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z; COfflineFilesManageOfflineFiles_CreateInstance(_GUID const &,void * *)
0x1800048eb  jmp     loc_180004AE3
0x1800048f0  mov     rax, [rbx]
0x1800048f3  sub     rax, qword ptr cs:CLSID_OfflineFilesContextMenuExt.Data1
0x1800048fa  jnz     short loc_180004907
0x1800048fc  mov     rax, [rbx+8]
0x180004900  sub     rax, qword ptr cs:CLSID_OfflineFilesContextMenuExt.Data4
0x180004907  test    rax, rax
0x18000490a  jnz     short loc_180004918
0x18000490c  lea     rbx, ?CContextMenuExt_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z; CContextMenuExt_CreateInstance(_GUID const &,void * *)
0x180004913  jmp     loc_180004AE3
0x180004918  mov     rax, [rbx]
0x18000491b  sub     rax, qword ptr cs:CLSID_OfflineFilesIconOverlayExt.Data1
0x180004922  jnz     short loc_18000492F
0x180004924  mov     rax, [rbx+8]
0x180004928  sub     rax, qword ptr cs:CLSID_OfflineFilesIconOverlayExt.Data4
0x18000492f  test    rax, rax
0x180004932  jnz     short loc_180004940
0x180004934  lea     rbx, ?CIconOverlayExt_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z; CIconOverlayExt_CreateInstance(_GUID const &,void * *)
0x18000493b  jmp     loc_180004AE3
0x180004940  mov     rax, [rbx]
0x180004943  sub     rax, qword ptr cs:CLSID_CscUpdateHandler.Data1
0x18000494a  jnz     short loc_180004957
0x18000494c  mov     rax, [rbx+8]
0x180004950  sub     rax, qword ptr cs:CLSID_CscUpdateHandler.Data4
0x180004957  test    rax, rax
0x18000495a  jnz     short loc_180004968
0x18000495c  lea     rbx, ?CSyncHandler_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z; CSyncHandler_CreateInstance(_GUID const &,void * *)
0x180004963  jmp     loc_180004AE3
0x180004968  mov     rax, [rbx]
0x18000496b  sub     rax, qword ptr cs:CLSID_OfflineFilesSyncConflictStore.Data1
0x180004972  jnz     short loc_18000497F
0x180004974  mov     rax, [rbx+8]
0x180004978  sub     rax, qword ptr cs:CLSID_OfflineFilesSyncConflictStore.Data4
0x18000497f  test    rax, rax
0x180004982  jnz     short loc_180004990
0x180004984  lea     rbx, ?CSyncConflictStore_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z; CSyncConflictStore_CreateInstance(_GUID const &,void * *)
0x18000498b  jmp     loc_180004AE3
0x180004990  mov     rax, [rbx]
0x180004993  sub     rax, qword ptr cs:CLSID_OfflineFilesPropSheetExt.Data1
0x18000499a  jnz     short loc_1800049A7
0x18000499c  mov     rax, [rbx+8]
0x1800049a0  sub     rax, qword ptr cs:CLSID_OfflineFilesPropSheetExt.Data4
0x1800049a7  test    rax, rax
0x1800049aa  jnz     short loc_1800049B8
0x1800049ac  lea     rbx, ?COfflinePropSheetExt_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z; COfflinePropSheetExt_CreateInstance(_GUID const &,void * *)
0x1800049b3  jmp     loc_180004AE3
0x1800049b8  mov     rax, [rbx]
0x1800049bb  sub     rax, qword ptr cs:CLSID_OfflineFilesShellSvcObject.Data1
0x1800049c2  jnz     short loc_1800049CF
0x1800049c4  mov     rax, [rbx+8]
0x1800049c8  sub     rax, qword ptr cs:CLSID_OfflineFilesShellSvcObject.Data4
0x1800049cf  test    rax, rax
0x1800049d2  jnz     short loc_1800049E0
0x1800049d4  lea     rbx, ?CCSCShellServiceObject_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z; CCSCShellServiceObject_CreateInstance(_GUID const &,void * *)
0x1800049db  jmp     loc_180004AE3
0x1800049e0  mov     rax, [rbx]
0x1800049e3  sub     rax, qword ptr cs:IID_ITaskHandler.Data1
0x1800049ea  jnz     short loc_1800049F7
0x1800049ec  mov     rax, [rbx+8]
0x1800049f0  sub     rax, qword ptr cs:IID_ITaskHandler.Data4
0x1800049f7  test    rax, rax
0x1800049fa  jz      loc_180004ADC
0x180004a00  mov     rax, [rbx]
0x180004a03  sub     rax, qword ptr cs:CLSID_OfflineFilesBackgroundSyncHandler.Data1
0x180004a0a  jnz     short loc_180004A17
0x180004a0c  mov     rax, [rbx+8]
0x180004a10  sub     rax, qword ptr cs:CLSID_OfflineFilesBackgroundSyncHandler.Data4
0x180004a17  test    rax, rax
0x180004a1a  jz      loc_180004ADC
0x180004a20  mov     rax, [rbx]
0x180004a23  sub     rax, qword ptr cs:CLSID_OfflineFilesSyncStatusProvider.Data1
0x180004a2a  jnz     short loc_180004A37
0x180004a2c  mov     rax, [rbx+8]
0x180004a30  sub     rax, qword ptr cs:CLSID_OfflineFilesSyncStatusProvider.Data4
0x180004a37  test    rax, rax
0x180004a3a  jnz     short loc_180004A48
0x180004a3c  lea     rbx, ?COfflineFilesSyncStatusProvider_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z; COfflineFilesSyncStatusProvider_CreateInstance(_GUID const &,void * *)
0x180004a43  jmp     loc_180004AE3
0x180004a48  mov     rax, [rbx]
0x180004a4b  sub     rax, qword ptr cs:CLSID_OfflineFilesSyncStatusProviderInternal.Data1
0x180004a52  jnz     short loc_180004A5F
0x180004a54  mov     rax, [rbx+8]
0x180004a58  sub     rax, qword ptr cs:CLSID_OfflineFilesSyncStatusProviderInternal.Data4
0x180004a5f  test    rax, rax
0x180004a62  jnz     short loc_180004A6D
0x180004a64  lea     rbx, ?COfflineFilesSyncStatusProviderInternal_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z; COfflineFilesSyncStatusProviderInternal_CreateInstance(_GUID const &,void * *)
0x180004a6b  jmp     short loc_180004AE3
0x180004a6d  mov     rax, [rbx]
0x180004a70  sub     rax, qword ptr cs:CLSID_OfflineFilesWorkOfflineOnlineCommand.Data1
0x180004a77  jnz     short loc_180004A84
0x180004a79  mov     rax, [rbx+8]
0x180004a7d  sub     rax, qword ptr cs:CLSID_OfflineFilesWorkOfflineOnlineCommand.Data4
0x180004a84  test    rax, rax
0x180004a87  jnz     short loc_180004A92
0x180004a89  lea     rbx, ?COfflineFilesWorkOfflineOnlineCommand_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z; COfflineFilesWorkOfflineOnlineCommand_CreateInstance(_GUID const &,void * *)
0x180004a90  jmp     short loc_180004AE3
0x180004a92  mov     rax, [rbx]
0x180004a95  sub     rax, qword ptr cs:CLSID_OfflineFilesSyncCommand.Data1
0x180004a9c  jnz     short loc_180004AA9
0x180004a9e  mov     rax, [rbx+8]
0x180004aa2  sub     rax, qword ptr cs:CLSID_OfflineFilesSyncCommand.Data4
0x180004aa9  test    rax, rax
0x180004aac  jnz     short loc_180004AB7
0x180004aae  lea     rbx, ?COfflineFilesSyncCommand_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z; COfflineFilesSyncCommand_CreateInstance(_GUID const &,void * *)
0x180004ab5  jmp     short loc_180004AE3
0x180004ab7  mov     rax, [rbx]
0x180004aba  sub     rax, qword ptr cs:CLSID_OfflineFilesMakeAvailableOffline.Data1
0x180004ac1  jnz     short loc_180004ACE
0x180004ac3  mov     rax, [rbx+8]
0x180004ac7  sub     rax, qword ptr cs:CLSID_OfflineFilesMakeAvailableOffline.Data4
0x180004ace  test    rax, rax
0x180004ad1  jnz     short loc_180004B43
0x180004ad3  lea     rbx, ?COfflineFilesMakeAvailableOfflineCommand_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z; COfflineFilesMakeAvailableOfflineCommand_CreateInstance(_GUID const &,void * *)
0x180004ada  jmp     short loc_180004AE3
0x180004adc  lea     rbx, ?COfflineFilesBackgroundSyncHandler_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z; COfflineFilesBackgroundSyncHandler_CreateInstance(_GUID const &,void * *)
0x180004ae3  mov     ecx, 18h; Size
0x180004ae8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004aed  test    rax, rax
0x180004af0  jz      short loc_180004B35
0x180004af2  mov     rdx, rbx; int (*)(const struct _GUID *, void **)
0x180004af5  mov     rcx, rax; this
0x180004af8  call    ??0CClassFactory@@QEAA@P6AJAEBU_GUID@@PEAPEAX@Z@Z; CClassFactory::CClassFactory(long (*)(_GUID const &,void * *))
0x180004afd  mov     rsi, rax
0x180004b00  test    rax, rax
0x180004b03  jz      short loc_180004B35
0x180004b05  mov     rcx, [rax]
0x180004b08  mov     r8, rdi
0x180004b0b  mov     rdx, rbp
0x180004b0e  mov     rax, [rcx]
0x180004b11  mov     rcx, rsi
0x180004b14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b19  mov     rcx, [rsi]
0x180004b1c  mov     ebx, eax
0x180004b1e  mov     rax, [rcx+10h]
0x180004b22  mov     rcx, rsi
0x180004b25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b2a  mov     eax, ebx
0x180004b2c  add     rsp, 38h
0x180004b30  pop     rdi
0x180004b31  pop     rsi
0x180004b32  pop     rbp
0x180004b33  pop     rbx
0x180004b34  retn
0x180004b35  mov     eax, 8007000Eh
0x180004b3a  add     rsp, 38h
0x180004b3e  pop     rdi
0x180004b3f  pop     rsi
0x180004b40  pop     rbp
0x180004b41  pop     rbx
0x180004b42  retn
0x180004b43  mov     eax, esi
0x180004b45  add     rsp, 38h
0x180004b49  pop     rdi
0x180004b4a  pop     rsi
0x180004b4b  pop     rbp
0x180004b4c  pop     rbx
0x180004b4d  retn
```
