# UL_AND_WORKER_MANAGER::DeleteVirtualSite(SITE_DATA_OBJECT *,long)

- ea: `0x1800102dc`
- end: `0x180010426`
- name: `?DeleteVirtualSite@UL_AND_WORKER_MANAGER@@QEAAXPEAVSITE_DATA_OBJECT@@J@Z`
- size: `330`
- prototype: `void __fastcall(UL_AND_WORKER_MANAGER *__hidden this, struct SITE_DATA_OBJECT *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18003a1f0`

## callees

- `0x1800102dc`
- `0x18003ddd4`
- `0x180062010`

## import_xrefs

- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x1800103b3`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x1800103b3`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18001030e`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18001030e`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x18001033b`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x18001033b`
- `iisutil!PuDbgPrint` at `0x1800103eb`
- `iisutil!PuDbgPrint` at `0x1800103eb`
- `iisutil!PuDbgPrintError` at `0x18001037d`
- `iisutil!PuDbgPrintError` at `0x18001037d`

## string_xrefs

- `0x18001036e`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\ul_and_worker_manager.cxx`
- `0x1800103cb`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\ul_and_worker_manager.cxx`
- `0x180010321`: `Finding virtual site to delete in hashtable failed\n`
- `0x180010362`: `UL_AND_WORKER_MANAGER::DeleteVirtualSite`
- `0x1800103c0`: `UL_AND_WORKER_MANAGER::DeleteVirtualSite`
- `0x1800103df`: `Virtual site: %lu removed from hashtable; total number now: %lu\n`

## pseudocode

```c
void __fastcall UL_AND_WORKER_MANAGER::DeleteVirtualSite(
        UL_AND_WORKER_MANAGER *this,
        struct SITE_DATA_OBJECT *a2,
        int a3)
{
  CLKRHashTable *v3; // rsi
  WAS_ERROR_LOGGER *v7; // rcx
  __int64 v8; // rbx
  unsigned int v9; // eax
  __int64 v10; // [rsp+60h] [rbp+8h] BYREF

  v3 = (UL_AND_WORKER_MANAGER *)((char *)this + 96);
  v10 = 0;
  if ( (unsigned int)CLKRHashTable::FindKey((char *)this + 96, *((unsigned int *)a2 + 12), &v10) )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\ul_and_worker_manager.cxx",
        1667,
        "UL_AND_WORKER_MANAGER::DeleteVirtualSite",
        -2147467259,
        "Finding virtual site to delete in hashtable failed\n");
LABEL_7:
    WAS_ERROR_LOGGER::LogSiteError(v7, 0xC00013F1, -2147467259, *((_DWORD *)a2 + 12));
    return;
  }
  v8 = v10;
  if ( (unsigned int)CLKRHashTable::DeleteRecord(v3, v10) )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\ul_and_worker_manager.cxx",
        1684,
        "UL_AND_WORKER_MANAGER::DeleteVirtualSite",
        -2147467259,
        "Removing virtual site from hashtable failed\n");
    goto LABEL_7;
  }
  if ( (g_dwDebugFlags & 0x30000) != 0 && (g_dwDebugFlags & 3) != 0 )
  {
    v9 = CLKRHashTable::Size(v3);
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\ul_and_worker_manager.cxx",
      1697,
      "UL_AND_WORKER_MANAGER::DeleteVirtualSite",
      "Virtual site: %lu removed from hashtable; total number now: %lu\n",
      *((_DWORD *)a2 + 12),
      v9);
  }
  *(_DWORD *)(v8 + 592) = a3;
  (**(void (__fastcall ***)(__int64, __int64))v8)(v8, 1);
  *((_DWORD *)this + 102) = 1;
}

```

## disassembly

```asm
0x1800102dc  mov     rax, rsp
0x1800102df  mov     [rax+10h], rbx
0x1800102e3  mov     [rax+18h], rbp
0x1800102e7  push    rsi
0x1800102e8  push    rdi
0x1800102e9  push    r14
0x1800102eb  sub     rsp, 40h
0x1800102ef  lea     rsi, [rcx+60h]
0x1800102f3  mov     qword ptr [rax+8], 0
0x1800102fb  mov     r14d, r8d
0x1800102fe  mov     rdi, rdx
0x180010301  mov     edx, [rdx+30h]
0x180010304  lea     r8, [rax+8]
0x180010308  mov     rbp, rcx
0x18001030b  mov     rcx, rsi
0x18001030e  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x180010314  test    eax, eax
0x180010316  jz      short loc_180010330
0x180010318  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001031f  jz      short loc_180010383
0x180010321  lea     rax, aFindingVirtual; "Finding virtual site to delete in hasht"...
0x180010328  mov     r8d, 683h
0x18001032e  jmp     short loc_18001035B
0x180010330  mov     rbx, [rsp+58h+arg_0]
0x180010335  mov     rcx, rsi
0x180010338  mov     rdx, rbx
0x18001033b  call    cs:__imp_?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z; CLKRHashTable::DeleteRecord(void const *)
0x180010341  test    eax, eax
0x180010343  jz      short loc_180010399
0x180010345  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001034c  jz      short loc_180010383
0x18001034e  lea     rax, aRemovingVirtua; "Removing virtual site from hashtable fa"...
0x180010355  mov     r8d, 694h
0x18001035b  mov     rcx, cs:g_pDebug
0x180010362  lea     r9, aUlAndWorkerMan_29; "UL_AND_WORKER_MANAGER::DeleteVirtualSit"...
0x180010369  mov     [rsp+58h+var_30], rax
0x18001036e  lea     rdx, aServercommonIn_68; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180010375  mov     dword ptr [rsp+58h+var_38], 80004005h
0x18001037d  call    cs:__imp_PuDbgPrintError
0x180010383  mov     r8d, 80004005h; int
0x180010389  mov     r9d, [rdi+30h]; unsigned int
0x18001038d  mov     edx, 0C00013F1h; unsigned int
0x180010392  call    ?LogSiteError@WAS_ERROR_LOGGER@@QEAAXKJK@Z; WAS_ERROR_LOGGER::LogSiteError(ulong,long,ulong)
0x180010397  jmp     short loc_180010413
0x180010399  mov     eax, cs:g_dwDebugFlags
0x18001039f  test    eax, 30000h
0x1800103a4  setnz   dl
0x1800103a7  test    al, 3
0x1800103a9  setnz   al
0x1800103ac  test    al, dl
0x1800103ae  jz      short loc_1800103F1
0x1800103b0  mov     rcx, rsi
0x1800103b3  call    cs:__imp_?Size@CLKRHashTable@@QEBAKXZ; CLKRHashTable::Size(void)
0x1800103b9  mov     rcx, cs:g_pDebug
0x1800103c0  lea     r9, aUlAndWorkerMan_29; "UL_AND_WORKER_MANAGER::DeleteVirtualSit"...
0x1800103c7  mov     [rsp+58h+var_28], eax
0x1800103cb  lea     rdx, aServercommonIn_68; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800103d2  mov     eax, [rdi+30h]
0x1800103d5  mov     r8d, 6A1h
0x1800103db  mov     dword ptr [rsp+58h+var_30], eax
0x1800103df  lea     rax, aVirtualSiteLuR; "Virtual site: %lu removed from hashtabl"...
0x1800103e6  mov     [rsp+58h+var_38], rax
0x1800103eb  call    cs:__imp_PuDbgPrint
0x1800103f1  mov     [rbx+250h], r14d
0x1800103f8  mov     edi, 1
0x1800103fd  mov     rax, [rbx]
0x180010400  mov     edx, edi
0x180010402  mov     rcx, rbx
0x180010405  mov     rax, [rax]
0x180010408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001040d  mov     [rbp+198h], edi
0x180010413  mov     rbx, [rsp+58h+arg_8]
0x180010418  mov     rbp, [rsp+58h+arg_10]
0x18001041d  add     rsp, 40h
0x180010421  pop     r14
0x180010423  pop     rdi
0x180010424  pop     rsi
0x180010425  retn
```
