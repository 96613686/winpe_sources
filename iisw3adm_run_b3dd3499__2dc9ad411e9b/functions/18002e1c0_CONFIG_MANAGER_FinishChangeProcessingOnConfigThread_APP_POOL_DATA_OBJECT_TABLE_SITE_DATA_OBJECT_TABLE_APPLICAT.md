# CONFIG_MANAGER::FinishChangeProcessingOnConfigThread(APP_POOL_DATA_OBJECT_TABLE *,SITE_DATA_OBJECT_TABLE *,APPLICATION_DATA_OBJECT_TABLE *,GLOBAL_DATA_STORE *,PROTOCOL_DATA_OBJECT_TABLE *,APP_POOL_CHANGED_LIST *,int)

- ea: `0x18002e1c0`
- end: `0x18002e713`
- name: `?FinishChangeProcessingOnConfigThread@CONFIG_MANAGER@@AEAAJPEAVAPP_POOL_DATA_OBJECT_TABLE@@PEAVSITE_DATA_OBJECT_TABLE@@PEAVAPPLICATION_DATA_OBJECT_TABLE@@PEAVGLOBAL_DATA_STORE@@PEAVPROTOCOL_DATA_OBJECT_TABLE@@PEAVAPP_POOL_CHANGED_LIST@@H@Z`
- size: `1363`
- prototype: `__int64 __fastcall(CONFIG_MANAGER *__hidden this, struct APP_POOL_DATA_OBJECT_TABLE *, struct SITE_DATA_OBJECT_TABLE *, struct APPLICATION_DATA_OBJECT_TABLE *, struct GLOBAL_DATA_STORE *, struct PROTOCOL_DATA_OBJECT_TABLE *, struct APP_POOL_CHANGED_LIST *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002fad4`

## callees

- `0x180001234`
- `0x1800073fc`
- `0x18002d780`
- `0x18002e1c0`
- `0x18002f318`
- `0x18002f66c`
- `0x18003cc00`
- `0x18003cf50`
- `0x180062010`

## import_xrefs

- `iisutil!?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z` at `0x18002e5ea`
- `iisutil!?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z` at `0x18002e60b`
- `iisutil!?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z` at `0x18002e62c`
- `iisutil!?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z` at `0x18002e670`
- `iisutil!?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z` at `0x18002e5ea`
- `iisutil!?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z` at `0x18002e60b`
- `iisutil!?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z` at `0x18002e62c`
- `iisutil!?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z` at `0x18002e670`
- `iisutil!?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z` at `0x18002e258`
- `iisutil!?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z` at `0x18002e27c`
- `iisutil!?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z` at `0x18002e2a0`
- `iisutil!?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z` at `0x18002e2e4`
- `iisutil!?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z` at `0x18002e439`
- `iisutil!?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z` at `0x18002e45d`
- `iisutil!?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z` at `0x18002e481`
- `iisutil!?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z` at `0x18002e4be`
- `iisutil!?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z` at `0x18002e258`
- `iisutil!?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z` at `0x18002e27c`
- `iisutil!?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z` at `0x18002e2a0`
- `iisutil!?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z` at `0x18002e2e4`
- `iisutil!?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z` at `0x18002e439`
- `iisutil!?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z` at `0x18002e45d`
- `iisutil!?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z` at `0x18002e481`
- `iisutil!?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z` at `0x18002e4be`
- `iisutil!PuDbgPrint` at `0x18002e225`
- `iisutil!PuDbgPrint` at `0x18002e328`
- `iisutil!PuDbgPrint` at `0x18002e401`
- `iisutil!PuDbgPrint` at `0x18002e500`
- `iisutil!PuDbgPrint` at `0x18002e6b4`
- `iisutil!PuDbgPrint` at `0x18002e225`
- `iisutil!PuDbgPrint` at `0x18002e328`
- `iisutil!PuDbgPrint` at `0x18002e401`
- `iisutil!PuDbgPrint` at `0x18002e500`
- `iisutil!PuDbgPrint` at `0x18002e6b4`
- `iisutil!PuDbgPrintError` at `0x18002e6f7`
- `iisutil!PuDbgPrintError` at `0x18002e6f7`

## string_xrefs

- `0x18002e21e`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\config_manager.cxx`
- `0x18002e321`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\config_manager.cxx`
- `0x18002e3fa`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\config_manager.cxx`
- `0x18002e4f9`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\config_manager.cxx`
- `0x18002e6ad`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\config_manager.cxx`
- `0x18002e6f0`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\config_manager.cxx`
- `0x18002e205`: `\n **********  Starting to dump the temp data table *********** \n`
- `0x18002e20c`: `CONFIG_MANAGER::FinishChangeProcessingOnConfigThread`
- `0x18002e30f`: `CONFIG_MANAGER::FinishChangeProcessingOnConfigThread`
- `0x18002e3e8`: `CONFIG_MANAGER::FinishChangeProcessingOnConfigThread`
- `0x18002e4e7`: `CONFIG_MANAGER::FinishChangeProcessingOnConfigThread`
- `0x18002e69b`: `CONFIG_MANAGER::FinishChangeProcessingOnConfigThread`
- `0x18002e6e9`: `CONFIG_MANAGER::FinishChangeProcessingOnConfigThread`
- `0x18002e308`: `\n **********  Done with dump the temp data table ************* \n`
- `0x18002e6cc`: `Failed to send the changes to the main thread\n`
- `0x18002e694`: `Completed processing a change on the change processing thread \n`

## pseudocode

```c
__int64 __fastcall CONFIG_MANAGER::FinishChangeProcessingOnConfigThread(
        CONFIG_MANAGER *this,
        struct APP_POOL_DATA_OBJECT_TABLE *a2,
        struct SITE_DATA_OBJECT_TABLE *a3,
        struct APPLICATION_DATA_OBJECT_TABLE *a4,
        struct GLOBAL_DATA_STORE *a5,
        struct PROTOCOL_DATA_OBJECT_TABLE *a6,
        struct APP_POOL_CHANGED_LIST *a7,
        int a8)
{
  __int64 v12; // rcx
  int v13; // eax
  int v14; // ebx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  WAS_CHANGE_ITEM *v20; // rax
  WAS_CHANGE_ITEM *v21; // rax
  struct WORK_DISPATCH *v22; // rsi
  __int64 v23; // rcx
  CLKRHashTable *v24; // rcx
  CLKRHashTable *v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rax
  CLKRHashTable *v28; // rcx
  void *v30; // [rsp+30h] [rbp-61h] BYREF
  void *v31; // [rsp+38h] [rbp-59h]
  __int64 v32; // [rsp+40h] [rbp-51h]
  void *v33; // [rsp+48h] [rbp-49h] BYREF
  void *v34; // [rsp+50h] [rbp-41h]
  __int64 v35; // [rsp+58h] [rbp-39h]
  void *v36; // [rsp+60h] [rbp-31h] BYREF
  void *v37; // [rsp+68h] [rbp-29h]
  __int64 v38; // [rsp+70h] [rbp-21h]
  void *v39; // [rsp+78h] [rbp-19h] BYREF
  void *v40; // [rsp+80h] [rbp-11h]
  __int64 v41; // [rsp+88h] [rbp-9h]

  if ( (g_dwDebugFlags & 0x50000) != 0 && (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_manager.cxx",
      2056,
      "CONFIG_MANAGER::FinishChangeProcessingOnConfigThread",
      "\n **********  Starting to dump the temp data table *********** \n");
  v30 = 0;
  v31 = &DATA_OBJECT_TABLE::DumpObjectAction;
  v32 = 0;
  CLKRHashTable::Apply(
    (char *)a2 + 8,
    CTypedHashTable<HASH_POOL_HASH,POOL_HASH_ENTRY,APP_POOL_HASH const *,CLKRHashTable>::_Action,
    &v30,
    2);
  v33 = 0;
  v34 = &DATA_OBJECT_TABLE::DumpObjectAction;
  v35 = 0;
  CLKRHashTable::Apply(
    (char *)a3 + 8,
    CTypedHashTable<HASH_POOL_HASH,POOL_HASH_ENTRY,APP_POOL_HASH const *,CLKRHashTable>::_Action,
    &v33,
    2);
  v36 = 0;
  v37 = &DATA_OBJECT_TABLE::DumpObjectAction;
  v38 = 0;
  CLKRHashTable::Apply(
    (char *)a4 + 8,
    CTypedHashTable<HASH_POOL_HASH,POOL_HASH_ENTRY,APP_POOL_HASH const *,CLKRHashTable>::_Action,
    &v36,
    2);
  v12 = *((_QWORD *)a5 + 1);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 48LL))(v12);
  v40 = &DATA_OBJECT_TABLE::DumpObjectAction;
  v39 = 0;
  v41 = 0;
  CLKRHashTable::Apply(
    (char *)a6 + 8,
    CTypedHashTable<HASH_POOL_HASH,POOL_HASH_ENTRY,APP_POOL_HASH const *,CLKRHashTable>::_Action,
    &v39,
    2);
  if ( (g_dwDebugFlags & 0x50000) != 0 && (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_manager.cxx",
      2071,
      "CONFIG_MANAGER::FinishChangeProcessingOnConfigThread",
      "\n **********  Done with dump the temp data table ************* \n");
  if ( (*((_BYTE *)this + 248) & 0x20) != 0 )
    v13 = CONFIG_MANAGER::MergeAndSelfValidateTablesDynamic(this, a2, a3, a4, a5, a6);
  else
    v13 = CONFIG_MANAGER::MergeAndSelfValidateTables(this, a2, a3, a4, a5, a6);
  v14 = v13;
  if ( v13 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_manager.cxx",
        2096,
        "CONFIG_MANAGER::FinishChangeProcessingOnConfigThread",
        v13,
        "merging and self validating tables failed\n");
    return (unsigned int)v14;
  }
  v14 = CONFIG_MANAGER::CrossValidateDataObjects(this);
  if ( v14 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_manager.cxx",
        2108,
        "CONFIG_MANAGER::FinishChangeProcessingOnConfigThread",
        v14,
        "Failed cross validating data\n");
    return (unsigned int)v14;
  }
  if ( (g_dwDebugFlags & 0x50000) != 0 && (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_manager.cxx",
      2116,
      "CONFIG_MANAGER::FinishChangeProcessingOnConfigThread",
      "\n *********  Starting to dump the real data table *********** \n");
  v15 = *((_QWORD *)this + 3);
  v39 = 0;
  v41 = 0;
  v40 = &DATA_OBJECT_TABLE::DumpObjectAction;
  CLKRHashTable::Apply(
    v15 + 8,
    CTypedHashTable<HASH_POOL_HASH,POOL_HASH_ENTRY,APP_POOL_HASH const *,CLKRHashTable>::_Action,
    &v39,
    2);
  v16 = *((_QWORD *)this + 4) + 8LL;
  v36 = 0;
  v37 = &DATA_OBJECT_TABLE::DumpObjectAction;
  v38 = 0;
  CLKRHashTable::Apply(
    v16,
    CTypedHashTable<HASH_POOL_HASH,POOL_HASH_ENTRY,APP_POOL_HASH const *,CLKRHashTable>::_Action,
    &v36,
    2);
  v17 = *((_QWORD *)this + 5) + 8LL;
  v33 = 0;
  v34 = &DATA_OBJECT_TABLE::DumpObjectAction;
  v35 = 0;
  CLKRHashTable::Apply(
    v17,
    CTypedHashTable<HASH_POOL_HASH,POOL_HASH_ENTRY,APP_POOL_HASH const *,CLKRHashTable>::_Action,
    &v33,
    2);
  v18 = *(_QWORD *)(*((_QWORD *)this + 6) + 8LL);
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 48LL))(v18);
  v19 = *((_QWORD *)this + 7) + 8LL;
  v30 = 0;
  v31 = &DATA_OBJECT_TABLE::DumpObjectAction;
  v32 = 0;
  CLKRHashTable::Apply(
    v19,
    CTypedHashTable<HASH_POOL_HASH,POOL_HASH_ENTRY,APP_POOL_HASH const *,CLKRHashTable>::_Action,
    &v30,
    2);
  if ( (g_dwDebugFlags & 0x50000) != 0 && (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_manager.cxx",
      2131,
      "CONFIG_MANAGER::FinishChangeProcessingOnConfigThread",
      "\n *********  Done with dump the real data table ********** \n");
  if ( !a8 && a7 )
    *((_DWORD *)a7 + 4) = 0;
  v20 = (WAS_CHANGE_ITEM *)operator new(0x198u);
  if ( !v20 || (v21 = WAS_CHANGE_ITEM::WAS_CHANGE_ITEM(v20, *((_DWORD *)this + 82), a7), (v22 = v21) == 0) )
  {
    v14 = -2147024888;
    goto LABEL_35;
  }
  v14 = WAS_CHANGE_ITEM::CopyChanges(
          v21,
          *((struct GLOBAL_DATA_STORE **)this + 6),
          *((struct SITE_DATA_OBJECT_TABLE **)this + 4),
          *((struct APPLICATION_DATA_OBJECT_TABLE **)this + 5),
          *((struct APP_POOL_DATA_OBJECT_TABLE **)this + 3),
          *((struct PROTOCOL_DATA_OBJECT_TABLE **)this + 7));
  if ( v14 < 0 )
  {
    (*(void (__fastcall **)(struct WORK_DISPATCH *))(*(_QWORD *)v22 + 8LL))(v22);
    goto LABEL_35;
  }
  v14 = WORK_QUEUE::GetAndQueueWorkItem((WEB_ADMIN_SERVICE *)((char *)g_pWebAdminService + 16), v22, 1u);
  (*(void (__fastcall **)(struct WORK_DISPATCH *))(*(_QWORD *)v22 + 8LL))(v22);
  if ( v14 < 0 )
  {
LABEL_35:
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_manager.cxx",
        2153,
        "CONFIG_MANAGER::FinishChangeProcessingOnConfigThread",
        v14,
        "Failed to send the changes to the main thread\n");
    return (unsigned int)v14;
  }
  v23 = *((_QWORD *)this + 3);
  v40 = 0;
  v39 = &DATA_OBJECT_TABLE::DeletePredicate;
  v41 = 0;
  CLKRHashTable::DeleteIf(
    (CLKRHashTable *)(v23 + 8),
    (enum LK_PREDICATE (__high *)(const void *, void *))CTypedHashTable<TOKEN_CACHE,TOKEN_CACHE_ENTRY,TOKEN_CACHE_KEY *,CLKRHashTable>::_Pred,
    &v39);
  v24 = (CLKRHashTable *)(*((_QWORD *)this + 4) + 8LL);
  v36 = &DATA_OBJECT_TABLE::DeletePredicate;
  v37 = 0;
  v38 = 0;
  CLKRHashTable::DeleteIf(
    v24,
    (enum LK_PREDICATE (__high *)(const void *, void *))CTypedHashTable<TOKEN_CACHE,TOKEN_CACHE_ENTRY,TOKEN_CACHE_KEY *,CLKRHashTable>::_Pred,
    &v36);
  v25 = (CLKRHashTable *)(*((_QWORD *)this + 5) + 8LL);
  v33 = &DATA_OBJECT_TABLE::DeletePredicate;
  v34 = 0;
  v35 = 0;
  CLKRHashTable::DeleteIf(
    v25,
    (enum LK_PREDICATE (__high *)(const void *, void *))CTypedHashTable<TOKEN_CACHE,TOKEN_CACHE_ENTRY,TOKEN_CACHE_KEY *,CLKRHashTable>::_Pred,
    &v33);
  v26 = *((_QWORD *)this + 6);
  v27 = *(_QWORD *)(v26 + 8);
  if ( v27 )
  {
    *(_DWORD *)(v27 + 16) = 1;
    (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v26 + 8) + 40LL))(*(_QWORD *)(v26 + 8), 0);
  }
  v28 = (CLKRHashTable *)(*((_QWORD *)this + 7) + 8LL);
  v30 = &DATA_OBJECT_TABLE::DeletePredicate;
  v31 = 0;
  v32 = 0;
  CLKRHashTable::DeleteIf(
    v28,
    (enum LK_PREDICATE (__high *)(const void *, void *))CTypedHashTable<TOKEN_CACHE,TOKEN_CACHE_ENTRY,TOKEN_CACHE_KEY *,CLKRHashTable>::_Pred,
    &v30);
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x10000000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_manager.cxx",
      2169,
      "CONFIG_MANAGER::FinishChangeProcessingOnConfigThread",
      "Completed processing a change on the change processing thread \n");
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18002e1c0  push    rbp
0x18002e1c2  push    rbx
0x18002e1c3  push    rsi
0x18002e1c4  push    rdi
0x18002e1c5  push    r12
0x18002e1c7  push    r13
0x18002e1c9  push    r14
0x18002e1cb  push    r15
0x18002e1cd  lea     rbp, [rsp-7]
0x18002e1d2  sub     rsp, 98h
0x18002e1d9  mov     eax, cs:g_dwDebugFlags
0x18002e1df  mov     rsi, r9
0x18002e1e2  test    eax, 50000h
0x18002e1e7  mov     r14, r8
0x18002e1ea  mov     r15, rdx
0x18002e1ed  mov     rdi, rcx
0x18002e1f0  setnz   r10b
0x18002e1f4  test    al, 3
0x18002e1f6  setnz   al
0x18002e1f9  test    al, r10b
0x18002e1fc  jz      short loc_18002E22B
0x18002e1fe  mov     rcx, cs:g_pDebug
0x18002e205  lea     rax, aStartingToDump_0; "\n **********  Starting to dump the tem"...
0x18002e20c  lea     r9, aConfigManagerF; "CONFIG_MANAGER::FinishChangeProcessingO"...
0x18002e213  mov     [rsp+0D0h+var_B0], rax
0x18002e218  mov     r8d, 808h
0x18002e21e  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002e225  call    cs:__imp_PuDbgPrint
0x18002e22b  xor     r12d, r12d
0x18002e22e  lea     rbx, ?DumpObjectAction@DATA_OBJECT_TABLE@@CA?AW4LK_ACTION@@PEAVDATA_OBJECT@@PEAX@Z; DATA_OBJECT_TABLE::DumpObjectAction(DATA_OBJECT *,void *)
0x18002e235  lea     rcx, [r15+8]
0x18002e239  mov     [rbp+3Fh+var_A0], r12
0x18002e23d  lea     r8, [rbp+3Fh+var_A0]
0x18002e241  mov     [rbp+3Fh+var_98], rbx
0x18002e245  lea     rdx, ?_Action@?$CTypedHashTable@VHASH_POOL_HASH@@VPOOL_HASH_ENTRY@@PEBUAPP_POOL_HASH@@VCLKRHashTable@@@@CA?AW4LK_ACTION@@PEBXPEAX@Z; CTypedHashTable<HASH_POOL_HASH,POOL_HASH_ENTRY,APP_POOL_HASH const *,CLKRHashTable>::_Action(void const *,void *)
0x18002e24c  mov     [rbp+3Fh+var_90], r12
0x18002e250  lea     r13d, [r12+2]
0x18002e255  mov     r9d, r13d
0x18002e258  call    cs:__imp_?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z; CLKRHashTable::Apply(LK_ACTION (*)(void const *,void *),void *,LK_LOCKTYPE)
0x18002e25e  lea     rcx, [r14+8]
0x18002e262  mov     [rbp+3Fh+var_88], r12
0x18002e266  mov     r9d, r13d
0x18002e269  mov     [rbp+3Fh+var_80], rbx
0x18002e26d  lea     r8, [rbp+3Fh+var_88]
0x18002e271  mov     [rbp+3Fh+var_78], r12
0x18002e275  lea     rdx, ?_Action@?$CTypedHashTable@VHASH_POOL_HASH@@VPOOL_HASH_ENTRY@@PEBUAPP_POOL_HASH@@VCLKRHashTable@@@@CA?AW4LK_ACTION@@PEBXPEAX@Z; CTypedHashTable<HASH_POOL_HASH,POOL_HASH_ENTRY,APP_POOL_HASH const *,CLKRHashTable>::_Action(void const *,void *)
0x18002e27c  call    cs:__imp_?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z; CLKRHashTable::Apply(LK_ACTION (*)(void const *,void *),void *,LK_LOCKTYPE)
0x18002e282  lea     rcx, [rsi+8]
0x18002e286  mov     [rbp+3Fh+var_70], r12
0x18002e28a  mov     r9d, r13d
0x18002e28d  mov     [rbp+3Fh+var_68], rbx
0x18002e291  lea     r8, [rbp+3Fh+var_70]
0x18002e295  mov     [rbp+3Fh+var_60], r12
0x18002e299  lea     rdx, ?_Action@?$CTypedHashTable@VHASH_POOL_HASH@@VPOOL_HASH_ENTRY@@PEBUAPP_POOL_HASH@@VCLKRHashTable@@@@CA?AW4LK_ACTION@@PEBXPEAX@Z; CTypedHashTable<HASH_POOL_HASH,POOL_HASH_ENTRY,APP_POOL_HASH const *,CLKRHashTable>::_Action(void const *,void *)
0x18002e2a0  call    cs:__imp_?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z; CLKRHashTable::Apply(LK_ACTION (*)(void const *,void *),void *,LK_LOCKTYPE)
0x18002e2a6  mov     r13, [rbp+3Fh+arg_20]
0x18002e2aa  mov     rcx, [r13+8]
0x18002e2ae  test    rcx, rcx
0x18002e2b1  jz      short loc_18002E2BF
0x18002e2b3  mov     rax, [rcx]
0x18002e2b6  mov     rax, [rax+30h]
0x18002e2ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e2bf  mov     [rbp+3Fh+var_50], rbx
0x18002e2c3  lea     r8, [rbp+3Fh+var_58]
0x18002e2c7  mov     rbx, [rbp+3Fh+arg_28]
0x18002e2cb  lea     rdx, ?_Action@?$CTypedHashTable@VHASH_POOL_HASH@@VPOOL_HASH_ENTRY@@PEBUAPP_POOL_HASH@@VCLKRHashTable@@@@CA?AW4LK_ACTION@@PEBXPEAX@Z; CTypedHashTable<HASH_POOL_HASH,POOL_HASH_ENTRY,APP_POOL_HASH const *,CLKRHashTable>::_Action(void const *,void *)
0x18002e2d2  mov     r9d, 2
0x18002e2d8  mov     [rbp+3Fh+var_58], r12
0x18002e2dc  mov     [rbp+3Fh+var_48], r12
0x18002e2e0  lea     rcx, [rbx+8]
0x18002e2e4  call    cs:__imp_?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z; CLKRHashTable::Apply(LK_ACTION (*)(void const *,void *),void *,LK_LOCKTYPE)
0x18002e2ea  mov     eax, cs:g_dwDebugFlags
0x18002e2f0  test    eax, 50000h
0x18002e2f5  setnz   cl
0x18002e2f8  test    al, 3
0x18002e2fa  setnz   al
0x18002e2fd  test    al, cl
0x18002e2ff  jz      short loc_18002E32E
0x18002e301  mov     rcx, cs:g_pDebug
0x18002e308  lea     rax, aDoneWithDumpTh; "\n **********  Done with dump the temp "...
0x18002e30f  lea     r9, aConfigManagerF; "CONFIG_MANAGER::FinishChangeProcessingO"...
0x18002e316  mov     [rsp+0D0h+var_B0], rax
0x18002e31b  mov     r8d, 817h
0x18002e321  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002e328  call    cs:__imp_PuDbgPrint
0x18002e32e  test    byte ptr [rdi+0F8h], 20h
0x18002e335  mov     r9, rsi; struct APPLICATION_DATA_OBJECT_TABLE *
0x18002e338  mov     [rsp+0D0h+var_A8], rbx; struct PROTOCOL_DATA_OBJECT_TABLE *
0x18002e33d  mov     r8, r14; struct SITE_DATA_OBJECT_TABLE *
0x18002e340  mov     [rsp+0D0h+var_B0], r13; struct GLOBAL_DATA_STORE *
0x18002e345  mov     rdx, r15; struct APP_POOL_DATA_OBJECT_TABLE *
0x18002e348  mov     rcx, rdi; this
0x18002e34b  jz      short loc_18002E354
0x18002e34d  call    ?MergeAndSelfValidateTablesDynamic@CONFIG_MANAGER@@AEAAJPEAVAPP_POOL_DATA_OBJECT_TABLE@@PEAVSITE_DATA_OBJECT_TABLE@@PEAVAPPLICATION_DATA_OBJECT_TABLE@@PEAVGLOBAL_DATA_STORE@@PEAVPROTOCOL_DATA_OBJECT_TABLE@@@Z; CONFIG_MANAGER::MergeAndSelfValidateTablesDynamic(APP_POOL_DATA_OBJECT_TABLE *,SITE_DATA_OBJECT_TABLE *,APPLICATION_DATA_OBJECT_TABLE *,GLOBAL_DATA_STORE *,PROTOCOL_DATA_OBJECT_TABLE *)
0x18002e352  jmp     short loc_18002E359
0x18002e354  call    ?MergeAndSelfValidateTables@CONFIG_MANAGER@@AEAAJPEAVAPP_POOL_DATA_OBJECT_TABLE@@PEAVSITE_DATA_OBJECT_TABLE@@PEAVAPPLICATION_DATA_OBJECT_TABLE@@PEAVGLOBAL_DATA_STORE@@PEAVPROTOCOL_DATA_OBJECT_TABLE@@@Z; CONFIG_MANAGER::MergeAndSelfValidateTables(APP_POOL_DATA_OBJECT_TABLE *,SITE_DATA_OBJECT_TABLE *,APPLICATION_DATA_OBJECT_TABLE *,GLOBAL_DATA_STORE *,PROTOCOL_DATA_OBJECT_TABLE *)
0x18002e359  mov     ebx, eax
0x18002e35b  test    eax, eax
0x18002e35d  jns     short loc_18002E387
0x18002e35f  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002e366  jz      loc_18002E6FD
0x18002e36c  lea     rax, aMergingAndSelf; "merging and self validating tables fail"...
0x18002e373  mov     r8d, 830h
0x18002e379  mov     [rsp+0D0h+var_A8], rax
0x18002e37e  mov     dword ptr [rsp+0D0h+var_B0], ebx
0x18002e382  jmp     loc_18002E6E2
0x18002e387  mov     rcx, rdi; this
0x18002e38a  call    ?CrossValidateDataObjects@CONFIG_MANAGER@@AEAAJXZ; CONFIG_MANAGER::CrossValidateDataObjects(void)
0x18002e38f  mov     ebx, eax
0x18002e391  test    eax, eax
0x18002e393  jns     short loc_18002E3BD
0x18002e395  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002e39c  jz      loc_18002E6FD
0x18002e3a2  lea     rax, aFailedCrossVal_0; "Failed cross validating data\n"
0x18002e3a9  mov     r8d, 83Ch
0x18002e3af  mov     [rsp+0D0h+var_A8], rax
0x18002e3b4  mov     dword ptr [rsp+0D0h+var_B0], ebx
0x18002e3b8  jmp     loc_18002E6E2
0x18002e3bd  mov     eax, cs:g_dwDebugFlags
0x18002e3c3  mov     ebx, 50000h
0x18002e3c8  test    ebx, eax
0x18002e3ca  mov     r13b, 3
0x18002e3cd  setnz   cl
0x18002e3d0  test    r13b, al
0x18002e3d3  setnz   al
0x18002e3d6  test    al, cl
0x18002e3d8  jz      short loc_18002E407
0x18002e3da  mov     rcx, cs:g_pDebug
0x18002e3e1  lea     rax, aStartingToDump; "\n *********  Starting to dump the real"...
0x18002e3e8  lea     r9, aConfigManagerF; "CONFIG_MANAGER::FinishChangeProcessingO"...
0x18002e3ef  mov     [rsp+0D0h+var_B0], rax
0x18002e3f4  mov     r8d, 844h
0x18002e3fa  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002e401  call    cs:__imp_PuDbgPrint
0x18002e407  mov     rcx, [rdi+18h]
0x18002e40b  lea     r15, ?_Action@?$CTypedHashTable@VHASH_POOL_HASH@@VPOOL_HASH_ENTRY@@PEBUAPP_POOL_HASH@@VCLKRHashTable@@@@CA?AW4LK_ACTION@@PEBXPEAX@Z; CTypedHashTable<HASH_POOL_HASH,POOL_HASH_ENTRY,APP_POOL_HASH const *,CLKRHashTable>::_Action(void const *,void *)
0x18002e412  mov     r14d, 2
0x18002e418  mov     [rbp+3Fh+var_58], r12
0x18002e41c  lea     rsi, ?DumpObjectAction@DATA_OBJECT_TABLE@@CA?AW4LK_ACTION@@PEAVDATA_OBJECT@@PEAX@Z; DATA_OBJECT_TABLE::DumpObjectAction(DATA_OBJECT *,void *)
0x18002e423  mov     [rbp+3Fh+var_48], r12
0x18002e427  add     rcx, 8
0x18002e42b  mov     [rbp+3Fh+var_50], rsi
0x18002e42f  mov     r9d, r14d
0x18002e432  lea     r8, [rbp+3Fh+var_58]
0x18002e436  mov     rdx, r15
0x18002e439  call    cs:__imp_?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z; CLKRHashTable::Apply(LK_ACTION (*)(void const *,void *),void *,LK_LOCKTYPE)
0x18002e43f  mov     rcx, [rdi+20h]
0x18002e443  lea     r8, [rbp+3Fh+var_70]
0x18002e447  add     rcx, 8
0x18002e44b  mov     [rbp+3Fh+var_70], r12
0x18002e44f  mov     r9d, r14d
0x18002e452  mov     [rbp+3Fh+var_68], rsi
0x18002e456  mov     rdx, r15
0x18002e459  mov     [rbp+3Fh+var_60], r12
0x18002e45d  call    cs:__imp_?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z; CLKRHashTable::Apply(LK_ACTION (*)(void const *,void *),void *,LK_LOCKTYPE)
0x18002e463  mov     rcx, [rdi+28h]
0x18002e467  lea     r8, [rbp+3Fh+var_88]
0x18002e46b  add     rcx, 8
0x18002e46f  mov     [rbp+3Fh+var_88], r12
0x18002e473  mov     r9d, r14d
0x18002e476  mov     [rbp+3Fh+var_80], rsi
0x18002e47a  mov     rdx, r15
0x18002e47d  mov     [rbp+3Fh+var_78], r12
0x18002e481  call    cs:__imp_?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z; CLKRHashTable::Apply(LK_ACTION (*)(void const *,void *),void *,LK_LOCKTYPE)
0x18002e487  mov     rax, [rdi+30h]
0x18002e48b  mov     rcx, [rax+8]
0x18002e48f  test    rcx, rcx
0x18002e492  jz      short loc_18002E4A0
0x18002e494  mov     rax, [rcx]
0x18002e497  mov     rax, [rax+30h]
0x18002e49b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e4a0  mov     rcx, [rdi+38h]
0x18002e4a4  lea     r8, [rbp+3Fh+var_A0]
0x18002e4a8  add     rcx, 8
0x18002e4ac  mov     [rbp+3Fh+var_A0], r12
0x18002e4b0  mov     r9d, r14d
0x18002e4b3  mov     [rbp+3Fh+var_98], rsi
0x18002e4b7  mov     rdx, r15
0x18002e4ba  mov     [rbp+3Fh+var_90], r12
0x18002e4be  call    cs:__imp_?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z; CLKRHashTable::Apply(LK_ACTION (*)(void const *,void *),void *,LK_LOCKTYPE)
0x18002e4c4  mov     eax, cs:g_dwDebugFlags
0x18002e4ca  test    ebx, eax
0x18002e4cc  setnz   cl
0x18002e4cf  test    r13b, al
0x18002e4d2  setnz   al
0x18002e4d5  test    al, cl
0x18002e4d7  jz      short loc_18002E506
0x18002e4d9  mov     rcx, cs:g_pDebug
0x18002e4e0  lea     rax, aDoneWithDumpTh_0; "\n *********  Done with dump the real d"...
0x18002e4e7  lea     r9, aConfigManagerF; "CONFIG_MANAGER::FinishChangeProcessingO"...
0x18002e4ee  mov     [rsp+0D0h+var_B0], rax
0x18002e4f3  mov     r8d, 853h
0x18002e4f9  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002e500  call    cs:__imp_PuDbgPrint
0x18002e506  mov     rbx, [rbp+3Fh+arg_30]
0x18002e50a  cmp     [rbp+3Fh+arg_38], r12d
0x18002e511  jnz     short loc_18002E51C
0x18002e513  test    rbx, rbx
0x18002e516  jz      short loc_18002E51C
0x18002e518  mov     [rbx+10h], r12d
0x18002e51c  mov     ecx, 198h; Size
0x18002e521  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002e526  test    rax, rax
0x18002e529  jz      loc_18002E6BC
0x18002e52f  mov     edx, [rdi+148h]; unsigned int
0x18002e535  mov     r8, rbx; struct APP_POOL_CHANGED_LIST *
0x18002e538  mov     rcx, rax; this
0x18002e53b  call    ??0WAS_CHANGE_ITEM@@QEAA@KPEAVAPP_POOL_CHANGED_LIST@@@Z; WAS_CHANGE_ITEM::WAS_CHANGE_ITEM(ulong,APP_POOL_CHANGED_LIST *)
0x18002e540  mov     rsi, rax
0x18002e543  test    rax, rax
0x18002e546  jz      loc_18002E6BC
0x18002e54c  mov     rcx, [rdi+38h]
0x18002e550  mov     r9, [rdi+28h]; struct APPLICATION_DATA_OBJECT_TABLE *
0x18002e554  mov     r8, [rdi+20h]; struct SITE_DATA_OBJECT_TABLE *
0x18002e558  mov     rdx, [rdi+30h]; struct GLOBAL_DATA_STORE *
0x18002e55c  mov     [rsp+0D0h+var_A8], rcx; struct PROTOCOL_DATA_OBJECT_TABLE *
0x18002e561  mov     rcx, [rdi+18h]
0x18002e565  mov     [rsp+0D0h+var_B0], rcx; struct APP_POOL_DATA_OBJECT_TABLE *
0x18002e56a  mov     rcx, rax; this
0x18002e56d  call    ?CopyChanges@WAS_CHANGE_ITEM@@QEAAJPEAVGLOBAL_DATA_STORE@@PEAVSITE_DATA_OBJECT_TABLE@@PEAVAPPLICATION_DATA_OBJECT_TABLE@@PEAVAPP_POOL_DATA_OBJECT_TABLE@@PEAVPROTOCOL_DATA_OBJECT_TABLE@@@Z; WAS_CHANGE_ITEM::CopyChanges(GLOBAL_DATA_STORE *,SITE_DATA_OBJECT_TABLE *,APPLICATION_DATA_OBJECT_TABLE *,APP_POOL_DATA_OBJECT_TABLE *,PROTOCOL_DATA_OBJECT_TABLE *)
0x18002e572  mov     ebx, eax
0x18002e574  test    eax, eax
0x18002e576  jns     short loc_18002E58C
0x18002e578  mov     rax, [rsi]
0x18002e57b  mov     rcx, rsi
0x18002e57e  mov     rax, [rax+8]
0x18002e582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e587  jmp     loc_18002E6C1
0x18002e58c  mov     rcx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x18002e593  mov     r15d, 1
0x18002e599  add     rcx, 10h; this
0x18002e59d  mov     r8d, r15d; unsigned __int64
0x18002e5a0  mov     rdx, rsi; struct WORK_DISPATCH *
0x18002e5a3  call    ?GetAndQueueWorkItem@WORK_QUEUE@@QEAAJPEAVWORK_DISPATCH@@_K@Z; WORK_QUEUE::GetAndQueueWorkItem(WORK_DISPATCH *,unsigned __int64)
0x18002e5a8  mov     ebx, eax
0x18002e5aa  mov     rcx, rsi
0x18002e5ad  mov     rax, [rsi]
0x18002e5b0  mov     rax, [rax+8]
0x18002e5b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e5b9  test    ebx, ebx
0x18002e5bb  js      loc_18002E6C1
0x18002e5c1  mov     rcx, [rdi+18h]
0x18002e5c5  lea     r14, ?_Pred@?$CTypedHashTable@VTOKEN_CACHE@@VTOKEN_CACHE_ENTRY@@PEAVTOKEN_CACHE_KEY@@VCLKRHashTable@@@@CA?AW4LK_PREDICATE@@PEBXPEAX@Z; CTypedHashTable<TOKEN_CACHE,TOKEN_CACHE_ENTRY,TOKEN_CACHE_KEY *,CLKRHashTable>::_Pred(void const *,void *)
0x18002e5cc  lea     rsi, ?DeletePredicate@DATA_OBJECT_TABLE@@CA?AW4LK_PREDICATE@@PEAVDATA_OBJECT@@PEAX@Z; DATA_OBJECT_TABLE::DeletePredicate(DATA_OBJECT *,void *)
0x18002e5d3  mov     [rbp+3Fh+var_50], r12
0x18002e5d7  add     rcx, 8
0x18002e5db  mov     [rbp+3Fh+var_58], rsi
0x18002e5df  mov     rdx, r14
0x18002e5e2  mov     [rbp+3Fh+var_48], r12
0x18002e5e6  lea     r8, [rbp+3Fh+var_58]
0x18002e5ea  call    cs:__imp_?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z; CLKRHashTable::DeleteIf(LK_PREDICATE (*)(void const *,void *),void *)
0x18002e5f0  mov     rcx, [rdi+20h]
0x18002e5f4  lea     r8, [rbp+3Fh+var_70]
0x18002e5f8  add     rcx, 8
0x18002e5fc  mov     [rbp+3Fh+var_70], rsi
0x18002e600  mov     rdx, r14
0x18002e603  mov     [rbp+3Fh+var_68], r12
0x18002e607  mov     [rbp+3Fh+var_60], r12
0x18002e60b  call    cs:__imp_?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z; CLKRHashTable::DeleteIf(LK_PREDICATE (*)(void const *,void *),void *)
0x18002e611  mov     rcx, [rdi+28h]
0x18002e615  lea     r8, [rbp+3Fh+var_88]
0x18002e619  add     rcx, 8
0x18002e61d  mov     [rbp+3Fh+var_88], rsi
0x18002e621  mov     rdx, r14
0x18002e624  mov     [rbp+3Fh+var_80], r12
0x18002e628  mov     [rbp+3Fh+var_78], r12
0x18002e62c  call    cs:__imp_?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z; CLKRHashTable::DeleteIf(LK_PREDICATE (*)(void const *,void *),void *)
0x18002e632  mov     rcx, [rdi+30h]
0x18002e636  mov     rax, [rcx+8]
0x18002e63a  test    rax, rax
0x18002e63d  jz      short loc_18002E655
0x18002e63f  mov     [rax+10h], r15d
0x18002e643  xor     edx, edx
0x18002e645  mov     rcx, [rcx+8]
0x18002e649  mov     rax, [rcx]
0x18002e64c  mov     rax, [rax+28h]
0x18002e650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e655  mov     rcx, [rdi+38h]
0x18002e659  lea     r8, [rbp+3Fh+var_A0]
0x18002e65d  add     rcx, 8
0x18002e661  mov     [rbp+3Fh+var_A0], rsi
0x18002e665  mov     rdx, r14
0x18002e668  mov     [rbp+3Fh+var_98], r12
0x18002e66c  mov     [rbp+3Fh+var_90], r12
0x18002e670  call    cs:__imp_?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z; CLKRHashTable::DeleteIf(LK_PREDICATE (*)(void const *,void *),void *)
0x18002e676  mov     eax, cs:g_dwDebugFlags
0x18002e67c  test    r13b, al
0x18002e67f  setnz   cl
0x18002e682  bt      eax, 1Ch
0x18002e686  setb    al
0x18002e689  test    al, cl
0x18002e68b  jz      short loc_18002E6FD
0x18002e68d  mov     rcx, cs:g_pDebug
0x18002e694  lea     rax, aCompletedProce; "Completed processing a change on the ch"...
0x18002e69b  lea     r9, aConfigManagerF; "CONFIG_MANAGER::FinishChangeProcessingO"...
0x18002e6a2  mov     [rsp+0D0h+var_B0], rax
0x18002e6a7  mov     r8d, 879h
0x18002e6ad  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002e6b4  call    cs:__imp_PuDbgPrint
0x18002e6ba  jmp     short loc_18002E6FD
  ... truncated ...
```
