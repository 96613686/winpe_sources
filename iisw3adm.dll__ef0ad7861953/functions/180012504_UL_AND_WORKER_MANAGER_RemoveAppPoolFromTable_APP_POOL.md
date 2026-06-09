# UL_AND_WORKER_MANAGER::RemoveAppPoolFromTable(APP_POOL *)

- ea: `0x180012504`
- end: `0x18001260d`
- name: `?RemoveAppPoolFromTable@UL_AND_WORKER_MANAGER@@QEAAXPEAVAPP_POOL@@@Z`
- size: `265`
- prototype: `void __fastcall(UL_AND_WORKER_MANAGER *__hidden this, struct APP_POOL *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18001ac94`

## callees

- `0x180012504`
- `0x180062010`

## import_xrefs

- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18001258a`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x1800125e2`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18001258a`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x1800125e2`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x180012520`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x180012520`
- `iisutil!PuDbgPrint` at `0x1800125c4`
- `iisutil!PuDbgPrint` at `0x1800125c4`
- `iisutil!PuDbgPrintError` at `0x180012563`
- `iisutil!PuDbgPrintError` at `0x180012563`

## string_xrefs

- `0x18001255c`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\ul_and_worker_manager.cxx`
- `0x1800125a2`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\ul_and_worker_manager.cxx`
- `0x180012547`: `UL_AND_WORKER_MANAGER::RemoveAppPoolFromTable`
- `0x180012597`: `UL_AND_WORKER_MANAGER::RemoveAppPoolFromTable`
- `0x1800125b8`: `App pool: %S deleted from app pool hashtable; total number now: %lu\n`

## pseudocode

```c
void __fastcall UL_AND_WORKER_MANAGER::RemoveAppPoolFromTable(UL_AND_WORKER_MANAGER *this, struct APP_POOL *a2)
{
  CLKRHashTable *v2; // rdi
  bool v5; // zf
  int v6; // eax
  unsigned int v7; // eax

  v2 = (UL_AND_WORKER_MANAGER *)((char *)this + 16);
  v5 = (unsigned int)CLKRHashTable::DeleteRecord((char *)this + 16, a2) == 0;
  v6 = g_dwDebugFlags;
  if ( !v5 && (g_dwDebugFlags & 0xF) != 0 )
  {
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\ul_and_worker_manager.cxx",
      5207,
      "UL_AND_WORKER_MANAGER::RemoveAppPoolFromTable",
      -2147467259,
      "Removing app pool from hashtable failed\n");
    v6 = g_dwDebugFlags;
  }
  *((_DWORD *)a2 + 4) = 0;
  if ( (v6 & 0x30000) != 0 && (v6 & 3) != 0 )
  {
    v7 = CLKRHashTable::Size(v2);
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\ul_and_worker_manager.cxx",
      5228,
      "UL_AND_WORKER_MANAGER::RemoveAppPoolFromTable",
      "App pool: %S deleted from app pool hashtable; total number now: %lu\n",
      *((const wchar_t **)a2 + 7),
      v7);
  }
  (*(void (__fastcall **)(struct APP_POOL *))(*(_QWORD *)a2 + 8LL))(a2);
  if ( *((_DWORD *)this + 3) == 3 && !CLKRHashTable::Size(v2) )
    *((_DWORD *)g_pWebAdminService + 292) = 1;
}

```

## disassembly

```asm
0x180012504  mov     [rsp+arg_0], rbx
0x180012509  mov     [rsp+arg_8], rsi
0x18001250e  push    rdi
0x18001250f  sub     rsp, 40h
0x180012513  lea     rdi, [rcx+10h]
0x180012517  mov     rsi, rcx
0x18001251a  mov     rcx, rdi
0x18001251d  mov     rbx, rdx
0x180012520  call    cs:__imp_?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z; CLKRHashTable::DeleteRecord(void const *)
0x180012526  test    eax, eax
0x180012528  mov     eax, cs:g_dwDebugFlags
0x18001252e  jz      short loc_18001256F
0x180012530  test    al, 0Fh
0x180012532  jz      short loc_18001256F
0x180012534  mov     rcx, cs:g_pDebug
0x18001253b  lea     rax, aRemovingAppPoo; "Removing app pool from hashtable failed"...
0x180012542  mov     [rsp+48h+var_20], rax
0x180012547  lea     r9, aUlAndWorkerMan_17; "UL_AND_WORKER_MANAGER::RemoveAppPoolFro"...
0x18001254e  mov     r8d, 1457h
0x180012554  mov     dword ptr [rsp+48h+var_28], 80004005h
0x18001255c  lea     rdx, aServercommonIn_68; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180012563  call    cs:__imp_PuDbgPrintError
0x180012569  mov     eax, cs:g_dwDebugFlags
0x18001256f  test    eax, 30000h
0x180012574  mov     dword ptr [rbx+10h], 0
0x18001257b  setnz   cl
0x18001257e  test    al, 3
0x180012580  setnz   al
0x180012583  test    al, cl
0x180012585  jz      short loc_1800125CA
0x180012587  mov     rcx, rdi
0x18001258a  call    cs:__imp_?Size@CLKRHashTable@@QEBAKXZ; CLKRHashTable::Size(void)
0x180012590  mov     rcx, cs:g_pDebug
0x180012597  lea     r9, aUlAndWorkerMan_17; "UL_AND_WORKER_MANAGER::RemoveAppPoolFro"...
0x18001259e  mov     [rsp+48h+var_18], eax
0x1800125a2  lea     rdx, aServercommonIn_68; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800125a9  mov     rax, [rbx+38h]
0x1800125ad  mov     r8d, 146Ch
0x1800125b3  mov     [rsp+48h+var_20], rax
0x1800125b8  lea     rax, aAppPoolSDelete; "App pool: %S deleted from app pool hash"...
0x1800125bf  mov     [rsp+48h+var_28], rax
0x1800125c4  call    cs:__imp_PuDbgPrint
0x1800125ca  mov     rax, [rbx]
0x1800125cd  mov     rcx, rbx
0x1800125d0  mov     rax, [rax+8]
0x1800125d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125d9  cmp     dword ptr [rsi+0Ch], 3
0x1800125dd  jnz     short loc_1800125FD
0x1800125df  mov     rcx, rdi
0x1800125e2  call    cs:__imp_?Size@CLKRHashTable@@QEBAKXZ; CLKRHashTable::Size(void)
0x1800125e8  test    eax, eax
0x1800125ea  jnz     short loc_1800125FD
0x1800125ec  mov     rax, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x1800125f3  mov     dword ptr [rax+490h], 1
0x1800125fd  mov     rbx, [rsp+48h+arg_0]
0x180012602  mov     rsi, [rsp+48h+arg_8]
0x180012607  add     rsp, 40h
0x18001260b  pop     rdi
0x18001260c  retn
```
