# UL_AND_WORKER_MANAGER::CreateAppPool(APP_POOL_DATA_OBJECT *,int)

- ea: `0x18000ebe0`
- end: `0x18000edef`
- name: `?CreateAppPool@UL_AND_WORKER_MANAGER@@QEAAXPEAVAPP_POOL_DATA_OBJECT@@H@Z`
- size: `527`
- prototype: `void __fastcall(UL_AND_WORKER_MANAGER *__hidden this, struct APP_POOL_DATA_OBJECT *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000f608`
- `0x180038f70`

## callees

- `0x180001234`
- `0x180005878`
- `0x18000ebe0`
- `0x18001660c`
- `0x1800184ac`
- `0x18001ac94`
- `0x180062010`

## import_xrefs

- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18000ed1e`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18000ed1e`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18000ec93`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18000ec93`
- `iisutil!PuDbgPrint` at `0x18000ed58`
- `iisutil!PuDbgPrint` at `0x18000ed58`
- `iisutil!PuDbgPrintError` at `0x18000ec6f`
- `iisutil!PuDbgPrintError` at `0x18000ecd5`
- `iisutil!PuDbgPrintError` at `0x18000eda7`
- `iisutil!PuDbgPrintError` at `0x18000ec6f`
- `iisutil!PuDbgPrintError` at `0x18000ecd5`
- `iisutil!PuDbgPrintError` at `0x18000eda7`

## string_xrefs

- `0x18000ec68`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\ul_and_worker_manager.cxx`
- `0x18000ecce`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\ul_and_worker_manager.cxx`
- `0x18000ed36`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\ul_and_worker_manager.cxx`
- `0x18000eda0`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\ul_and_worker_manager.cxx`
- `0x18000ec57`: `UL_AND_WORKER_MANAGER::CreateAppPool`
- `0x18000ecb9`: `UL_AND_WORKER_MANAGER::CreateAppPool`
- `0x18000ed2b`: `UL_AND_WORKER_MANAGER::CreateAppPool`
- `0x18000ed8b`: `UL_AND_WORKER_MANAGER::CreateAppPool`

## pseudocode

```c
void __fastcall UL_AND_WORKER_MANAGER::CreateAppPool(UL_AND_WORKER_MANAGER *this, unsigned __int16 **a2, int a3)
{
  APP_POOL *v6; // rax
  APP_POOL *v7; // rax
  APP_POOL *v8; // rbx
  signed int v9; // edi
  char v10; // al
  bool v11; // zf
  unsigned int v12; // eax
  unsigned int v13; // edx
  unsigned __int16 *v14; // [rsp+98h] [rbp+20h] BYREF

  v6 = (APP_POOL *)operator new(0x208u);
  if ( !v6 || (v7 = APP_POOL::APP_POOL(v6), (v8 = v7) == 0) )
  {
    v9 = -2147024888;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\ul_and_worker_manager.cxx",
        410,
        "UL_AND_WORKER_MANAGER::CreateAppPool",
        -2147024888,
        "Allocating APP_POOL failed\n");
    goto LABEL_17;
  }
  v9 = APP_POOL::Initialize(v7, (struct APP_POOL_DATA_OBJECT *)a2, ++*((_DWORD *)this + 128));
  if ( v9 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\ul_and_worker_manager.cxx",
        430,
        "UL_AND_WORKER_MANAGER::CreateAppPool",
        v9,
        "Initializing app pool object failed\n");
    (*(void (__fastcall **)(APP_POOL *))(*(_QWORD *)v8 + 8LL))(v8);
LABEL_17:
    --*((_DWORD *)this + 128);
    v13 = -1073736723;
    goto LABEL_18;
  }
  if ( (unsigned int)CLKRHashTable::InsertRecord((char *)this + 16, v8, 0) )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\ul_and_worker_manager.cxx",
        450,
        "UL_AND_WORKER_MANAGER::CreateAppPool",
        -2147467259,
        "Inserting app pool into hashtable failed\n");
    APP_POOL::Terminate(v8);
    (*(void (__fastcall **)(APP_POOL *))(*(_QWORD *)v8 + 8LL))(v8);
    v9 = -2147467259;
    goto LABEL_17;
  }
  v10 = g_dwDebugFlags;
  v11 = (g_dwDebugFlags & 0x30000) == 0;
  *((_DWORD *)v8 + 4) = 1;
  if ( !v11 && (v10 & 3) != 0 )
  {
    v12 = CLKRHashTable::Size((UL_AND_WORKER_MANAGER *)((char *)this + 16));
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\ul_and_worker_manager.cxx",
      466,
      "UL_AND_WORKER_MANAGER::CreateAppPool",
      "New app pool: %S added to app pool hashtable; total number now: %lu\n",
      a2[10],
      v12);
  }
  if ( a3 )
  {
    v13 = 1073747008;
LABEL_18:
    v14 = a2[10];
    WEB_ADMIN_SERVICE::LogEvent(g_pWebAdminService, v13, 1u, (const unsigned __int16 **const)&v14, v9);
  }
}

```

## disassembly

```asm
0x18000ebe0  push    rbx
0x18000ebe2  push    rbp
0x18000ebe3  push    rsi
0x18000ebe4  push    rdi
0x18000ebe5  push    r14
0x18000ebe7  push    r15
0x18000ebe9  sub     rsp, 48h
0x18000ebed  mov     rsi, rcx
0x18000ebf0  mov     r15d, r8d
0x18000ebf3  mov     ecx, 208h; Size
0x18000ebf8  mov     rbp, rdx
0x18000ebfb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ec00  test    rax, rax
0x18000ec03  jz      loc_18000ED6A
0x18000ec09  mov     rcx, rax; this
0x18000ec0c  call    ??0APP_POOL@@QEAA@XZ; APP_POOL::APP_POOL(void)
0x18000ec11  mov     rbx, rax
0x18000ec14  test    rax, rax
0x18000ec17  jz      loc_18000ED6A
0x18000ec1d  inc     dword ptr [rsi+200h]
0x18000ec23  mov     rdx, rbp; struct APP_POOL_DATA_OBJECT *
0x18000ec26  mov     r8d, [rsi+200h]; unsigned int
0x18000ec2d  mov     rcx, rax; this
0x18000ec30  call    ?Initialize@APP_POOL@@QEAAJPEAVAPP_POOL_DATA_OBJECT@@K@Z; APP_POOL::Initialize(APP_POOL_DATA_OBJECT *,ulong)
0x18000ec35  mov     edi, eax
0x18000ec37  test    eax, eax
0x18000ec39  jns     short loc_18000EC89
0x18000ec3b  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000ec42  jz      short loc_18000EC75
0x18000ec44  mov     rcx, cs:g_pDebug
0x18000ec4b  lea     rax, aInitializingAp; "Initializing app pool object failed\n"
0x18000ec52  mov     [rsp+78h+var_50], rax
0x18000ec57  lea     r9, aUlAndWorkerMan_24; "UL_AND_WORKER_MANAGER::CreateAppPool"
0x18000ec5e  mov     r8d, 1AEh
0x18000ec64  mov     [rsp+78h+var_58], edi
0x18000ec68  lea     rdx, aServercommonIn_68; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000ec6f  call    cs:__imp_PuDbgPrintError
0x18000ec75  mov     rax, [rbx]
0x18000ec78  mov     rcx, rbx
0x18000ec7b  mov     rax, [rax+8]
0x18000ec7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec84  jmp     loc_18000EDAD
0x18000ec89  xor     r8d, r8d
0x18000ec8c  lea     rcx, [rsi+10h]
0x18000ec90  mov     rdx, rbx
0x18000ec93  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x18000ec99  test    eax, eax
0x18000ec9b  jz      short loc_18000ECFC
0x18000ec9d  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000eca4  jz      short loc_18000ECDB
0x18000eca6  mov     rcx, cs:g_pDebug
0x18000ecad  lea     rax, aInsertingAppPo; "Inserting app pool into hashtable faile"...
0x18000ecb4  mov     [rsp+78h+var_50], rax
0x18000ecb9  lea     r9, aUlAndWorkerMan_24; "UL_AND_WORKER_MANAGER::CreateAppPool"
0x18000ecc0  mov     r8d, 1C2h
0x18000ecc6  mov     [rsp+78h+var_58], 80004005h
0x18000ecce  lea     rdx, aServercommonIn_68; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000ecd5  call    cs:__imp_PuDbgPrintError
0x18000ecdb  mov     rcx, rbx; this
0x18000ecde  call    ?Terminate@APP_POOL@@QEAAXXZ; APP_POOL::Terminate(void)
0x18000ece3  mov     rax, [rbx]
0x18000ece6  mov     rcx, rbx
0x18000ece9  mov     rax, [rax+8]
0x18000eced  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ecf2  mov     edi, 80004005h
0x18000ecf7  jmp     loc_18000EDAD
0x18000ecfc  mov     eax, cs:g_dwDebugFlags
0x18000ed02  test    eax, 30000h
0x18000ed07  mov     dword ptr [rbx+10h], 1
0x18000ed0e  setnz   dl
0x18000ed11  test    al, 3
0x18000ed13  setnz   al
0x18000ed16  test    al, dl
0x18000ed18  jz      short loc_18000ED5E
0x18000ed1a  lea     rcx, [rsi+10h]
0x18000ed1e  call    cs:__imp_?Size@CLKRHashTable@@QEBAKXZ; CLKRHashTable::Size(void)
0x18000ed24  mov     rcx, cs:g_pDebug
0x18000ed2b  lea     r9, aUlAndWorkerMan_24; "UL_AND_WORKER_MANAGER::CreateAppPool"
0x18000ed32  mov     [rsp+78h+var_48], eax
0x18000ed36  lea     rdx, aServercommonIn_68; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000ed3d  mov     rax, [rbp+50h]
0x18000ed41  mov     r8d, 1D2h
0x18000ed47  mov     [rsp+78h+var_50], rax
0x18000ed4c  lea     rax, aNewAppPoolSAdd; "New app pool: %S added to app pool hash"...
0x18000ed53  mov     qword ptr [rsp+78h+var_58], rax
0x18000ed58  call    cs:__imp_PuDbgPrint
0x18000ed5e  test    r15d, r15d
0x18000ed61  jz      short loc_18000EDE2
0x18000ed63  mov     edx, 40001440h
0x18000ed68  jmp     short loc_18000EDB8
0x18000ed6a  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000ed71  mov     edi, 80070008h
0x18000ed76  jz      short loc_18000EDAD
0x18000ed78  mov     rcx, cs:g_pDebug
0x18000ed7f  lea     rax, aAllocatingAppP; "Allocating APP_POOL failed\n"
0x18000ed86  mov     [rsp+78h+var_50], rax
0x18000ed8b  lea     r9, aUlAndWorkerMan_24; "UL_AND_WORKER_MANAGER::CreateAppPool"
0x18000ed92  mov     r8d, 19Ah
0x18000ed98  mov     [rsp+78h+var_58], 80070008h
0x18000eda0  lea     rdx, aServercommonIn_68; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000eda7  call    cs:__imp_PuDbgPrintError
0x18000edad  dec     dword ptr [rsi+200h]
0x18000edb3  mov     edx, 0C00013EDh; unsigned int
0x18000edb8  mov     rax, [rbp+50h]
0x18000edbc  lea     r9, [rsp+78h+arg_18]; unsigned __int16 **
0x18000edc4  mov     rcx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; this
0x18000edcb  mov     r8d, 1; unsigned __int16
0x18000edd1  mov     [rsp+78h+arg_18], rax
0x18000edd9  mov     [rsp+78h+var_58], edi; unsigned int
0x18000eddd  call    ?LogEvent@WEB_ADMIN_SERVICE@@QEAAXKGQEAPEBGK@Z; WEB_ADMIN_SERVICE::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x18000ede2  add     rsp, 48h
0x18000ede6  pop     r15
0x18000ede8  pop     r14
0x18000edea  pop     rdi
0x18000edeb  pop     rsi
0x18000edec  pop     rbp
0x18000eded  pop     rbx
0x18000edee  retn
```
