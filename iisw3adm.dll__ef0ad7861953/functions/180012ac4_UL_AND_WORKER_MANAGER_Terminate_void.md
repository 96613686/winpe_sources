# UL_AND_WORKER_MANAGER::Terminate(void)

- ea: `0x180012ac4`
- end: `0x180012f28`
- name: `?Terminate@UL_AND_WORKER_MANAGER@@QEAAXXZ`
- size: `1124`
- prototype: `void __fastcall(UL_AND_WORKER_MANAGER *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180006880`

## callees

- `0x180004290`
- `0x180005b60`
- `0x180012798`
- `0x180012ac4`
- `0x18001ac94`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-perfcounters-l1-1-0!PerfStopProvider` at `0x180012dbf`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStopProvider` at `0x180012dbf`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x180012b33`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x180012c32`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x180012d28`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x180012de6`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x180012e6d`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x180012e9d`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x180012b33`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x180012c32`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x180012d28`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x180012de6`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x180012e6d`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x180012e9d`
- `iisutil!?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z` at `0x180012b67`
- `iisutil!?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z` at `0x180012c60`
- `iisutil!?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z` at `0x180012d57`
- `iisutil!?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z` at `0x180012e14`
- `iisutil!?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z` at `0x180012ec4`
- `iisutil!?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z` at `0x180012b67`
- `iisutil!?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z` at `0x180012c60`
- `iisutil!?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z` at `0x180012d57`
- `iisutil!?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z` at `0x180012e14`
- `iisutil!?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z` at `0x180012ec4`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x180012bb2`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x180012cab`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x180012bb2`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x180012cab`
- `iisutil!PuDbgPrintError` at `0x180012bf4`
- `iisutil!PuDbgPrintError` at `0x180012ced`
- `iisutil!PuDbgPrintError` at `0x180012bf4`
- `iisutil!PuDbgPrintError` at `0x180012ced`

## string_xrefs

- `0x180012ce6`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\virtual_site_table.cxx`
- `0x180012bed`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\application_table.cxx`

## pseudocode

```c
void __fastcall UL_AND_WORKER_MANAGER::Terminate(UL_AND_WORKER_MANAGER *this)
{
  __int64 v2; // rax
  __int64 v3; // rcx
  void (__fastcall ***v4)(_QWORD, __int64); // rbx
  __int64 v5; // rax
  __int64 v6; // rcx
  void (__fastcall ***v7)(_QWORD, __int64); // rbx
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rax
  _QWORD v14[2]; // [rsp+30h] [rbp-49h] BYREF
  _QWORD v15[2]; // [rsp+40h] [rbp-39h] BYREF
  _QWORD v16[2]; // [rsp+50h] [rbp-29h] BYREF
  _QWORD v17[2]; // [rsp+60h] [rbp-19h] BYREF
  _QWORD v18[2]; // [rsp+70h] [rbp-9h] BYREF
  __int64 v19; // [rsp+80h] [rbp+7h] BYREF
  void *v20; // [rsp+88h] [rbp+Fh]
  _QWORD *v21; // [rsp+90h] [rbp+17h]

  *((_DWORD *)this + 3) = 4;
  if ( *((_QWORD *)this + 59) )
    WEB_ADMIN_SERVICE::CancelTimer(this, (struct _TP_TIMER **)this + 59);
  if ( *((_QWORD *)this + 60) )
    WEB_ADMIN_SERVICE::CancelTimer(this, (struct _TP_TIMER **)this + 60);
  if ( *((_QWORD *)this + 61) )
    WEB_ADMIN_SERVICE::CancelTimer(this, (struct _TP_TIMER **)this + 61);
  v14[1] = v14;
  v14[0] = v14;
  CLKRHashTable::Size((UL_AND_WORKER_MANAGER *)((char *)this + 184));
  v19 = 0;
  v20 = &APPLICATION_TABLE::DeleteApplicationAction;
  v21 = v14;
  CLKRHashTable::Apply(
    (char *)this + 184,
    CTypedHashTable<HASH_POOL_HASH,POOL_HASH_ENTRY,APP_POOL_HASH const *,CLKRHashTable>::_Action,
    &v19,
    2);
  while ( 1 )
  {
    v2 = v14[0];
    if ( (_QWORD *)v14[0] == v14 )
      break;
    if ( *(_QWORD **)(v14[0] + 8LL) != v14 || (v3 = *(_QWORD *)v14[0], *(_QWORD *)(*(_QWORD *)v14[0] + 8LL) != v14[0]) )
LABEL_45:
      __fastfail(3u);
    v14[0] = *(_QWORD *)v14[0];
    *(_QWORD *)(v3 + 8) = v14;
    v4 = (void (__fastcall ***)(_QWORD, __int64))(v2 - 136);
    if ( (unsigned int)CLKRHashTable::DeleteRecord((char *)this + 184, v2 - 136) && (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\application_table.cxx",
        122,
        "APPLICATION_TABLE::Terminate",
        -2147467259,
        "Removing application from hashtable failed\n");
    if ( v4 )
      (**v4)(v4, 1);
  }
  v15[1] = v15;
  v15[0] = v15;
  CLKRHashTable::Size((UL_AND_WORKER_MANAGER *)((char *)this + 96));
  v19 = 0;
  v20 = &VIRTUAL_SITE_TABLE::DeleteVirtualSiteAction;
  v21 = v15;
  CLKRHashTable::Apply(
    (char *)this + 96,
    CTypedHashTable<HASH_POOL_HASH,POOL_HASH_ENTRY,APP_POOL_HASH const *,CLKRHashTable>::_Action,
    &v19,
    2);
  while ( 1 )
  {
    v5 = v15[0];
    if ( (_QWORD *)v15[0] == v15 )
      break;
    if ( *(_QWORD **)(v15[0] + 8LL) != v15 )
      goto LABEL_45;
    v6 = *(_QWORD *)v15[0];
    if ( *(_QWORD *)(*(_QWORD *)v15[0] + 8LL) != v15[0] )
      goto LABEL_45;
    v15[0] = *(_QWORD *)v15[0];
    *(_QWORD *)(v6 + 8) = v15;
    v7 = (void (__fastcall ***)(_QWORD, __int64))(v5 - 288);
    if ( (unsigned int)CLKRHashTable::DeleteRecord((char *)this + 96, v5 - 288) && (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\virtual_site_table.cxx",
        120,
        "VIRTUAL_SITE_TABLE::Terminate",
        -2147467259,
        "Removing virtual site from hashtable failed\n");
    if ( v7 )
      (**v7)(v7, 1);
  }
  v16[1] = v16;
  v16[0] = v16;
  CLKRHashTable::Size((UL_AND_WORKER_MANAGER *)((char *)this + 16));
  v19 = 0;
  v20 = &APP_POOL_TABLE::DeleteAppPoolAction;
  v21 = v16;
  CLKRHashTable::Apply(
    (char *)this + 16,
    CTypedHashTable<HASH_POOL_HASH,POOL_HASH_ENTRY,APP_POOL_HASH const *,CLKRHashTable>::_Action,
    &v19,
    2);
  while ( 1 )
  {
    v8 = v16[0];
    if ( (_QWORD *)v16[0] == v16 )
      break;
    if ( *(_QWORD **)(v16[0] + 8LL) != v16 )
      goto LABEL_45;
    v9 = *(_QWORD *)v16[0];
    if ( *(_QWORD *)(*(_QWORD *)v16[0] + 8LL) != v16[0] )
      goto LABEL_45;
    v16[0] = *(_QWORD *)v16[0];
    *(_QWORD *)(v9 + 8) = v16;
    APP_POOL::Terminate((APP_POOL *)(v8 - 200));
  }
  if ( !*((_DWORD *)g_pWebAdminService + 412) && *((_QWORD *)this + 62) )
  {
    PerfStopProvider(hDataSource_app_pool_counters_1);
    *((_QWORD *)this + 62) = 0;
  }
  v17[1] = v17;
  v17[0] = v17;
  CLKRHashTable::Size((UL_AND_WORKER_MANAGER *)((char *)this + 256));
  v19 = 0;
  v21 = v17;
  v20 = &PROTOCOL_TABLE::DeleteProtocolAction;
  CLKRHashTable::Apply(
    (char *)this + 256,
    CTypedHashTable<HASH_POOL_HASH,POOL_HASH_ENTRY,APP_POOL_HASH const *,CLKRHashTable>::_Action,
    &v19,
    2);
  while ( 1 )
  {
    v10 = v17[0];
    if ( (_QWORD *)v17[0] == v17 )
      break;
    if ( *(_QWORD **)(v17[0] + 8LL) != v17 )
      goto LABEL_45;
    v11 = *(_QWORD *)v17[0];
    if ( *(_QWORD *)(*(_QWORD *)v17[0] + 8LL) != v17[0] )
      goto LABEL_45;
    v17[0] = *(_QWORD *)v17[0];
    *(_QWORD *)(v11 + 8) = v17;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v10 - 56) + 56LL))(v10 - 56);
  }
  *((_DWORD *)this + 103) = 1;
  if ( CLKRHashTable::Size((UL_AND_WORKER_MANAGER *)((char *)this + 256)) )
    WEB_ADMIN_SERVICE::ProcessMainQueueDuringShutdown(g_pWebAdminService);
  *((_DWORD *)this + 103) = 0;
  v18[1] = v18;
  v18[0] = v18;
  CLKRHashTable::Size((UL_AND_WORKER_MANAGER *)((char *)this + 256));
  v19 = 0;
  v21 = v18;
  v20 = &PROTOCOL_TABLE::DeleteProtocolAction;
  CLKRHashTable::Apply(
    (char *)this + 256,
    CTypedHashTable<HASH_POOL_HASH,POOL_HASH_ENTRY,APP_POOL_HASH const *,CLKRHashTable>::_Action,
    &v19,
    2);
  while ( 1 )
  {
    v12 = v18[0];
    if ( (_QWORD *)v18[0] == v18 )
      break;
    if ( *(_QWORD **)(v18[0] + 8LL) != v18 )
      goto LABEL_45;
    v13 = *(_QWORD *)v18[0];
    if ( *(_QWORD *)(*(_QWORD *)v18[0] + 8LL) != v18[0] )
      goto LABEL_45;
    v18[0] = *(_QWORD *)v18[0];
    *(_QWORD *)(v13 + 8) = v18;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v12 - 56) + 40LL))(v12 - 56);
  }
  UL_AND_WORKER_MANAGER::StopW3LogSvc((struct _TP_TIMER **)this, 0);
}

```

## disassembly

```asm
0x180012ac4  push    rbp
0x180012ac6  push    rbx
0x180012ac7  push    rsi
0x180012ac8  push    rdi
0x180012ac9  push    r12
0x180012acb  push    r14
0x180012acd  lea     rbp, [rsp-2Fh]
0x180012ad2  sub     rsp, 0A8h
0x180012ad9  lea     rdx, [rcx+1D8h]; struct _TP_TIMER **
0x180012ae0  mov     dword ptr [rcx+0Ch], 4
0x180012ae7  xor     r14d, r14d
0x180012aea  mov     rdi, rcx
0x180012aed  cmp     [rdx], r14
0x180012af0  jz      short loc_180012AF7
0x180012af2  call    ?CancelTimer@WEB_ADMIN_SERVICE@@QEAAJPEAPEAU_TP_TIMER@@@Z; WEB_ADMIN_SERVICE::CancelTimer(_TP_TIMER * *)
0x180012af7  lea     rdx, [rdi+1E0h]; struct _TP_TIMER **
0x180012afe  cmp     [rdx], r14
0x180012b01  jz      short loc_180012B08
0x180012b03  call    ?CancelTimer@WEB_ADMIN_SERVICE@@QEAAJPEAPEAU_TP_TIMER@@@Z; WEB_ADMIN_SERVICE::CancelTimer(_TP_TIMER * *)
0x180012b08  lea     rdx, [rdi+1E8h]; struct _TP_TIMER **
0x180012b0f  cmp     [rdx], r14
0x180012b12  jz      short loc_180012B19
0x180012b14  call    ?CancelTimer@WEB_ADMIN_SERVICE@@QEAAJPEAPEAU_TP_TIMER@@@Z; WEB_ADMIN_SERVICE::CancelTimer(_TP_TIMER * *)
0x180012b19  lea     rax, [rbp+57h+var_A0]
0x180012b1d  mov     [rbp+57h+var_98], rax
0x180012b21  lea     rsi, [rdi+0B8h]
0x180012b28  lea     rax, [rbp+57h+var_A0]
0x180012b2c  mov     rcx, rsi
0x180012b2f  mov     [rbp+57h+var_A0], rax
0x180012b33  call    cs:__imp_?Size@CLKRHashTable@@QEBAKXZ; CLKRHashTable::Size(void)
0x180012b39  lea     rax, ?DeleteApplicationAction@APPLICATION_TABLE@@SA?AW4LK_ACTION@@PEAVAPPLICATION@@PEAX@Z; APPLICATION_TABLE::DeleteApplicationAction(APPLICATION *,void *)
0x180012b40  mov     [rbp+57h+var_50], r14
0x180012b44  mov     [rbp+57h+var_48], rax
0x180012b48  lea     r8, [rbp+57h+var_50]
0x180012b4c  lea     rax, [rbp+57h+var_A0]
0x180012b50  mov     r12d, 2
0x180012b56  mov     r9d, r12d
0x180012b59  mov     [rbp+57h+var_40], rax
0x180012b5d  lea     rdx, ?_Action@?$CTypedHashTable@VHASH_POOL_HASH@@VPOOL_HASH_ENTRY@@PEBUAPP_POOL_HASH@@VCLKRHashTable@@@@CA?AW4LK_ACTION@@PEBXPEAX@Z; CTypedHashTable<HASH_POOL_HASH,POOL_HASH_ENTRY,APP_POOL_HASH const *,CLKRHashTable>::_Action(void const *,void *)
0x180012b64  mov     rcx, rsi
0x180012b67  call    cs:__imp_?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z; CLKRHashTable::Apply(LK_ACTION (*)(void const *,void *),void *,LK_LOCKTYPE)
0x180012b6d  mov     rax, [rbp+57h+var_A0]
0x180012b71  lea     rcx, [rbp+57h+var_A0]
0x180012b75  cmp     rax, rcx
0x180012b78  jz      loc_180012C1B
0x180012b7e  lea     rcx, [rbp+57h+var_A0]
0x180012b82  cmp     [rax+8], rcx
0x180012b86  jnz     loc_180012F08
0x180012b8c  mov     rcx, [rax]
0x180012b8f  cmp     [rcx+8], rax
0x180012b93  jnz     loc_180012F08
0x180012b99  mov     [rbp+57h+var_A0], rcx
0x180012b9d  lea     rdx, [rbp+57h+var_A0]
0x180012ba1  mov     [rcx+8], rdx
0x180012ba5  lea     rbx, [rax-88h]
0x180012bac  mov     rdx, rbx
0x180012baf  mov     rcx, rsi
0x180012bb2  call    cs:__imp_?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z; CLKRHashTable::DeleteRecord(void const *)
0x180012bb8  test    eax, eax
0x180012bba  jz      short loc_180012BFA
0x180012bbc  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180012bc3  jz      short loc_180012BFA
0x180012bc5  mov     rcx, cs:g_pDebug
0x180012bcc  lea     rax, aRemovingApplic; "Removing application from hashtable fai"...
0x180012bd3  mov     [rsp+0D0h+var_A8], rax
0x180012bd8  lea     r9, aApplicationTab; "APPLICATION_TABLE::Terminate"
0x180012bdf  mov     r8d, 7Ah ; 'z'
0x180012be5  mov     [rsp+0D0h+var_B0], 80004005h
0x180012bed  lea     rdx, aServercommonIn_47; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180012bf4  call    cs:__imp_PuDbgPrintError
0x180012bfa  test    rbx, rbx
0x180012bfd  jz      loc_180012B6D
0x180012c03  mov     rax, [rbx]
0x180012c06  mov     edx, 1
0x180012c0b  mov     rcx, rbx
0x180012c0e  mov     rax, [rax]
0x180012c11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c16  jmp     loc_180012B6D
0x180012c1b  lea     rax, [rbp+57h+var_90]
0x180012c1f  mov     [rbp+57h+var_88], rax
0x180012c23  lea     rsi, [rdi+60h]
0x180012c27  lea     rax, [rbp+57h+var_90]
0x180012c2b  mov     rcx, rsi
0x180012c2e  mov     [rbp+57h+var_90], rax
0x180012c32  call    cs:__imp_?Size@CLKRHashTable@@QEBAKXZ; CLKRHashTable::Size(void)
0x180012c38  lea     rax, ?DeleteVirtualSiteAction@VIRTUAL_SITE_TABLE@@SA?AW4LK_ACTION@@PEAVVIRTUAL_SITE@@PEAX@Z; VIRTUAL_SITE_TABLE::DeleteVirtualSiteAction(VIRTUAL_SITE *,void *)
0x180012c3f  mov     [rbp+57h+var_50], r14
0x180012c43  mov     [rbp+57h+var_48], rax
0x180012c47  lea     r8, [rbp+57h+var_50]
0x180012c4b  lea     rax, [rbp+57h+var_90]
0x180012c4f  mov     r9d, r12d
0x180012c52  lea     rdx, ?_Action@?$CTypedHashTable@VHASH_POOL_HASH@@VPOOL_HASH_ENTRY@@PEBUAPP_POOL_HASH@@VCLKRHashTable@@@@CA?AW4LK_ACTION@@PEBXPEAX@Z; CTypedHashTable<HASH_POOL_HASH,POOL_HASH_ENTRY,APP_POOL_HASH const *,CLKRHashTable>::_Action(void const *,void *)
0x180012c59  mov     [rbp+57h+var_40], rax
0x180012c5d  mov     rcx, rsi
0x180012c60  call    cs:__imp_?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z; CLKRHashTable::Apply(LK_ACTION (*)(void const *,void *),void *,LK_LOCKTYPE)
0x180012c66  mov     rax, [rbp+57h+var_90]
0x180012c6a  lea     rcx, [rbp+57h+var_90]
0x180012c6e  cmp     rax, rcx
0x180012c71  jz      loc_180012D14
0x180012c77  lea     rcx, [rbp+57h+var_90]
0x180012c7b  cmp     [rax+8], rcx
0x180012c7f  jnz     loc_180012F08
0x180012c85  mov     rcx, [rax]
0x180012c88  cmp     [rcx+8], rax
0x180012c8c  jnz     loc_180012F08
0x180012c92  mov     [rbp+57h+var_90], rcx
0x180012c96  lea     rdx, [rbp+57h+var_90]
0x180012c9a  mov     [rcx+8], rdx
0x180012c9e  lea     rbx, [rax-120h]
0x180012ca5  mov     rdx, rbx
0x180012ca8  mov     rcx, rsi
0x180012cab  call    cs:__imp_?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z; CLKRHashTable::DeleteRecord(void const *)
0x180012cb1  test    eax, eax
0x180012cb3  jz      short loc_180012CF3
0x180012cb5  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180012cbc  jz      short loc_180012CF3
0x180012cbe  mov     rcx, cs:g_pDebug
0x180012cc5  lea     rax, aRemovingVirtua; "Removing virtual site from hashtable fa"...
0x180012ccc  mov     [rsp+0D0h+var_A8], rax
0x180012cd1  lea     r9, aVirtualSiteTab; "VIRTUAL_SITE_TABLE::Terminate"
0x180012cd8  mov     r8d, 78h ; 'x'
0x180012cde  mov     [rsp+0D0h+var_B0], 80004005h
0x180012ce6  lea     rdx, aServercommonIn_23; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180012ced  call    cs:__imp_PuDbgPrintError
0x180012cf3  test    rbx, rbx
0x180012cf6  jz      loc_180012C66
0x180012cfc  mov     rax, [rbx]
0x180012cff  mov     edx, 1
0x180012d04  mov     rcx, rbx
0x180012d07  mov     rax, [rax]
0x180012d0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d0f  jmp     loc_180012C66
0x180012d14  lea     rax, [rbp+57h+var_80]
0x180012d18  mov     [rbp+57h+var_78], rax
0x180012d1c  lea     rcx, [rdi+10h]
0x180012d20  lea     rax, [rbp+57h+var_80]
0x180012d24  mov     [rbp+57h+var_80], rax
0x180012d28  call    cs:__imp_?Size@CLKRHashTable@@QEBAKXZ; CLKRHashTable::Size(void)
0x180012d2e  lea     rax, ?DeleteAppPoolAction@APP_POOL_TABLE@@SA?AW4LK_ACTION@@PEAVAPP_POOL@@PEAX@Z; APP_POOL_TABLE::DeleteAppPoolAction(APP_POOL *,void *)
0x180012d35  mov     [rbp+57h+var_50], r14
0x180012d39  mov     [rbp+57h+var_48], rax
0x180012d3d  lea     r8, [rbp+57h+var_50]
0x180012d41  lea     rax, [rbp+57h+var_80]
0x180012d45  mov     r9d, r12d
0x180012d48  lea     rdx, ?_Action@?$CTypedHashTable@VHASH_POOL_HASH@@VPOOL_HASH_ENTRY@@PEBUAPP_POOL_HASH@@VCLKRHashTable@@@@CA?AW4LK_ACTION@@PEBXPEAX@Z; CTypedHashTable<HASH_POOL_HASH,POOL_HASH_ENTRY,APP_POOL_HASH const *,CLKRHashTable>::_Action(void const *,void *)
0x180012d4f  mov     [rbp+57h+var_40], rax
0x180012d53  lea     rcx, [rdi+10h]
0x180012d57  call    cs:__imp_?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z; CLKRHashTable::Apply(LK_ACTION (*)(void const *,void *),void *,LK_LOCKTYPE)
0x180012d5d  mov     rcx, [rbp+57h+var_80]
0x180012d61  lea     rax, [rbp+57h+var_80]
0x180012d65  cmp     rcx, rax
0x180012d68  jz      short loc_180012D9F
0x180012d6a  lea     rax, [rbp+57h+var_80]
0x180012d6e  cmp     [rcx+8], rax
0x180012d72  jnz     loc_180012F08
0x180012d78  mov     rax, [rcx]
0x180012d7b  cmp     [rax+8], rcx
0x180012d7f  jnz     loc_180012F08
0x180012d85  lea     rdx, [rbp+57h+var_80]
0x180012d89  mov     [rbp+57h+var_80], rax
0x180012d8d  add     rcx, 0FFFFFFFFFFFFFF38h; this
0x180012d94  mov     [rax+8], rdx
0x180012d98  call    ?Terminate@APP_POOL@@QEAAXXZ; APP_POOL::Terminate(void)
0x180012d9d  jmp     short loc_180012D5D
0x180012d9f  mov     rax, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x180012da6  cmp     [rax+670h], r14d
0x180012dad  jnz     short loc_180012DCC
0x180012daf  cmp     [rdi+1F0h], r14
0x180012db6  jz      short loc_180012DCC
0x180012db8  mov     rcx, cs:hDataSource_app_pool_counters_1; ProviderHandle
0x180012dbf  call    cs:__imp_PerfStopProvider
0x180012dc5  mov     [rdi+1F0h], r14
0x180012dcc  lea     rax, [rbp+57h+var_70]
0x180012dd0  mov     [rbp+57h+var_68], rax
0x180012dd4  lea     rbx, [rdi+100h]
0x180012ddb  lea     rax, [rbp+57h+var_70]
0x180012ddf  mov     rcx, rbx
0x180012de2  mov     [rbp+57h+var_70], rax
0x180012de6  call    cs:__imp_?Size@CLKRHashTable@@QEBAKXZ; CLKRHashTable::Size(void)
0x180012dec  lea     rax, [rbp+57h+var_70]
0x180012df0  mov     [rbp+57h+var_50], r14
0x180012df4  lea     rsi, ?DeleteProtocolAction@PROTOCOL_TABLE@@SA?AW4LK_ACTION@@PEAVPROTOCOL@@PEAX@Z; PROTOCOL_TABLE::DeleteProtocolAction(PROTOCOL *,void *)
0x180012dfb  mov     [rbp+57h+var_40], rax
0x180012dff  mov     r9d, r12d
0x180012e02  mov     [rbp+57h+var_48], rsi
0x180012e06  lea     r8, [rbp+57h+var_50]
0x180012e0a  mov     rcx, rbx
0x180012e0d  lea     rdx, ?_Action@?$CTypedHashTable@VHASH_POOL_HASH@@VPOOL_HASH_ENTRY@@PEBUAPP_POOL_HASH@@VCLKRHashTable@@@@CA?AW4LK_ACTION@@PEBXPEAX@Z; CTypedHashTable<HASH_POOL_HASH,POOL_HASH_ENTRY,APP_POOL_HASH const *,CLKRHashTable>::_Action(void const *,void *)
0x180012e14  call    cs:__imp_?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z; CLKRHashTable::Apply(LK_ACTION (*)(void const *,void *),void *,LK_LOCKTYPE)
0x180012e1a  mov     rcx, [rbp+57h+var_70]
0x180012e1e  lea     rax, [rbp+57h+var_70]
0x180012e22  cmp     rcx, rax
0x180012e25  jz      short loc_180012E60
0x180012e27  lea     rax, [rbp+57h+var_70]
0x180012e2b  cmp     [rcx+8], rax
0x180012e2f  jnz     loc_180012F08
0x180012e35  mov     rax, [rcx]
0x180012e38  cmp     [rax+8], rcx
0x180012e3c  jnz     loc_180012F08
0x180012e42  mov     [rbp+57h+var_70], rax
0x180012e46  lea     rdx, [rbp+57h+var_70]
0x180012e4a  mov     [rax+8], rdx
0x180012e4e  add     rcx, 0FFFFFFFFFFFFFFC8h
0x180012e52  mov     rax, [rcx]
0x180012e55  mov     rax, [rax+38h]
0x180012e59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e5e  jmp     short loc_180012E1A
0x180012e60  mov     rcx, rbx
0x180012e63  mov     dword ptr [rdi+19Ch], 1
0x180012e6d  call    cs:__imp_?Size@CLKRHashTable@@QEBAKXZ; CLKRHashTable::Size(void)
0x180012e73  test    eax, eax
0x180012e75  jz      short loc_180012E83
0x180012e77  mov     rcx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; this
0x180012e7e  call    ?ProcessMainQueueDuringShutdown@WEB_ADMIN_SERVICE@@QEAAXXZ; WEB_ADMIN_SERVICE::ProcessMainQueueDuringShutdown(void)
0x180012e83  lea     rax, [rbp+57h+var_60]
0x180012e87  mov     [rdi+19Ch], r14d
0x180012e8e  mov     [rbp+57h+var_58], rax
0x180012e92  mov     rcx, rbx
0x180012e95  lea     rax, [rbp+57h+var_60]
0x180012e99  mov     [rbp+57h+var_60], rax
0x180012e9d  call    cs:__imp_?Size@CLKRHashTable@@QEBAKXZ; CLKRHashTable::Size(void)
0x180012ea3  lea     rax, [rbp+57h+var_60]
0x180012ea7  mov     [rbp+57h+var_50], r14
0x180012eab  mov     r9d, r12d
0x180012eae  mov     [rbp+57h+var_40], rax
0x180012eb2  lea     r8, [rbp+57h+var_50]
0x180012eb6  mov     [rbp+57h+var_48], rsi
0x180012eba  lea     rdx, ?_Action@?$CTypedHashTable@VHASH_POOL_HASH@@VPOOL_HASH_ENTRY@@PEBUAPP_POOL_HASH@@VCLKRHashTable@@@@CA?AW4LK_ACTION@@PEBXPEAX@Z; CTypedHashTable<HASH_POOL_HASH,POOL_HASH_ENTRY,APP_POOL_HASH const *,CLKRHashTable>::_Action(void const *,void *)
0x180012ec1  mov     rcx, rbx
0x180012ec4  call    cs:__imp_?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z; CLKRHashTable::Apply(LK_ACTION (*)(void const *,void *),void *,LK_LOCKTYPE)
0x180012eca  mov     rcx, [rbp+57h+var_60]
0x180012ece  lea     rax, [rbp+57h+var_60]
0x180012ed2  cmp     rcx, rax
0x180012ed5  jz      short loc_180012F0F
0x180012ed7  lea     rax, [rbp+57h+var_60]
0x180012edb  cmp     [rcx+8], rax
0x180012edf  jnz     short loc_180012F08
0x180012ee1  mov     rax, [rcx]
0x180012ee4  cmp     [rax+8], rcx
0x180012ee8  jnz     short loc_180012F08
0x180012eea  mov     [rbp+57h+var_60], rax
0x180012eee  lea     rdx, [rbp+57h+var_60]
0x180012ef2  mov     [rax+8], rdx
0x180012ef6  add     rcx, 0FFFFFFFFFFFFFFC8h
0x180012efa  mov     rax, [rcx]
0x180012efd  mov     rax, [rax+28h]
0x180012f01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f06  jmp     short loc_180012ECA
0x180012f08  mov     ecx, 3
0x180012f0d  int     29h; Win8: RtlFailFast(ecx)
0x180012f0f  xor     edx, edx; unsigned int
0x180012f11  mov     rcx, rdi; this
0x180012f14  add     rsp, 0A8h
0x180012f1b  pop     r14
0x180012f1d  pop     r12
0x180012f1f  pop     rdi
0x180012f20  pop     rsi
0x180012f21  pop     rbx
0x180012f22  pop     rbp
0x180012f23  jmp     ?StopW3LogSvc@UL_AND_WORKER_MANAGER@@QEAAJK@Z; UL_AND_WORKER_MANAGER::StopW3LogSvc(ulong)
```
