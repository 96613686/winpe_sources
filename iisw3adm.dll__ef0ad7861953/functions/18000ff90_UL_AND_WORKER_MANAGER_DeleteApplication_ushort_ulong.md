# UL_AND_WORKER_MANAGER::DeleteApplication(ushort *,ulong)

- ea: `0x18000ff90`
- end: `0x1800101fd`
- name: `?DeleteApplication@UL_AND_WORKER_MANAGER@@QEAAXPEAGK@Z`
- size: `621`
- prototype: `void(UL_AND_WORKER_MANAGER *__hidden this, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003adb0`

## callees

- `0x18000ff90`
- `0x18003dd48`
- `0x180061060`
- `0x180062010`

## import_xrefs

- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x180010005`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x180010005`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x1800100aa`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x1800100aa`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x18001014f`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x18001014f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800101d0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800101d0`
- `iisutil!PuDbgPrint` at `0x18001003b`
- `iisutil!PuDbgPrint` at `0x1800100f8`
- `iisutil!PuDbgPrint` at `0x18001003b`
- `iisutil!PuDbgPrint` at `0x1800100f8`
- `iisutil!PuDbgPrintError` at `0x180010089`
- `iisutil!PuDbgPrintError` at `0x180010137`
- `iisutil!PuDbgPrintError` at `0x18001018d`
- `iisutil!PuDbgPrintError` at `0x180010089`
- `iisutil!PuDbgPrintError` at `0x180010137`
- `iisutil!PuDbgPrintError` at `0x18001018d`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000ffc3`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000ffc3`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001004d`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001004d`

## string_xrefs

- `0x18000ffdd`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\ul_and_worker_manager.cxx`
- `0x18001006d`: `Failed memory allocation when checking if created application exists\n`
- `0x18001002b`: `Deleting application in site: %lu with path: %S, total number before delete: %lu; config change %lu\n`
- `0x18000ffcf`: `UL_AND_WORKER_MANAGER::DeleteApplication`
- `0x180010117`: `Finding application to delete in hashtable failed\n`
- `0x180010175`: `UL_AND_WORKER_MANAGER::DeleteApplicationInternal`

## pseudocode

```c
void __fastcall UL_AND_WORKER_MANAGER::DeleteApplication(
        UL_AND_WORKER_MANAGER *this,
        unsigned __int16 *a2,
        unsigned int a3)
{
  CLKRHashTable *v6; // r14
  int v7; // ebx
  unsigned int v8; // eax
  WAS_ERROR_LOGGER *v9; // rcx
  int v10; // ebx
  int Key; // eax
  void (__fastcall ***v12)(_QWORD, __int64); // rdi
  void (__fastcall ***v13)(_QWORD, __int64); // [rsp+50h] [rbp-88h] BYREF
  unsigned int v14; // [rsp+60h] [rbp-78h] BYREF
  _BYTE v15[56]; // [rsp+68h] [rbp-70h] BYREF

  STRU::STRU((STRU *)v15);
  v6 = (UL_AND_WORKER_MANAGER *)((char *)this + 184);
  if ( (g_dwDebugFlags & 0x30000) != 0 && (g_dwDebugFlags & 3) != 0 )
  {
    v7 = *((_DWORD *)g_pWebAdminService + 259);
    v8 = CLKRHashTable::Size(v6);
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\ul_and_worker_manager.cxx",
      1835,
      "UL_AND_WORKER_MANAGER::DeleteApplication",
      "Deleting application in site: %lu with path: %S, total number before delete: %lu; config change %lu\n",
      a3,
      a2,
      v8,
      v7);
  }
  v14 = a3;
  v10 = STRU::Copy((STRU *)v15, a2);
  if ( v10 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\ul_and_worker_manager.cxx",
        1848,
        "UL_AND_WORKER_MANAGER::DeleteApplication",
        v10,
        "Failed memory allocation when checking if created application exists\n");
LABEL_20:
    WAS_ERROR_LOGGER::LogApplicationError(v9, 0xC00013EF, v10, a3, a2);
    goto LABEL_21;
  }
  v13 = 0;
  Key = CLKRHashTable::FindKey(v6, &v14, &v13);
  if ( Key == 2 )
  {
    if ( (g_dwDebugFlags & 0x50000) != 0 && (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\ul_and_worker_manager.cxx",
        1883,
        "UL_AND_WORKER_MANAGER::DeleteApplication",
        "Received a change notification for an application '%S' with Site Id '%d' that does not exist\n",
        a2,
        a3);
  }
  else
  {
    if ( Key )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\ul_and_worker_manager.cxx",
          1898,
          "UL_AND_WORKER_MANAGER::DeleteApplication",
          -2147467259,
          "Finding application to delete in hashtable failed\n");
      v10 = -2147467259;
      goto LABEL_20;
    }
    v12 = v13;
    if ( (unsigned int)CLKRHashTable::DeleteRecord(v6, v13) )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\ul_and_worker_manager.cxx",
          1964,
          "UL_AND_WORKER_MANAGER::DeleteApplicationInternal",
          -2147467259,
          "Removing application from hashtable failed\n");
      v10 = -2147467259;
    }
    else
    {
      v10 = 0;
      if ( v12 )
        (**v12)(v12, 1);
    }
    if ( v10 < 0 )
      goto LABEL_20;
  }
LABEL_21:
  STRU::~STRU((STRU *)v15);
}

```

## disassembly

```asm
0x18000ff90  mov     [rsp+arg_18], rbx
0x18000ff95  push    rbp
0x18000ff96  push    rsi
0x18000ff97  push    rdi
0x18000ff98  push    r14
0x18000ff9a  push    r15
0x18000ff9c  sub     rsp, 0B0h
0x18000ffa3  mov     rax, cs:__security_cookie
0x18000ffaa  xor     rax, rsp
0x18000ffad  mov     [rsp+0D8h+var_38], rax
0x18000ffb5  mov     r14, rcx
0x18000ffb8  mov     ebp, r8d
0x18000ffbb  lea     rcx, [rsp+0D8h+var_70]
0x18000ffc0  mov     rsi, rdx
0x18000ffc3  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000ffc9  mov     eax, cs:g_dwDebugFlags
0x18000ffcf  lea     rdi, aUlAndWorkerMan_13; "UL_AND_WORKER_MANAGER::DeleteApplicatio"...
0x18000ffd6  add     r14, 0B8h
0x18000ffdd  lea     r15, aServercommonIn_68; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000ffe4  test    eax, 30000h
0x18000ffe9  setnz   cl
0x18000ffec  test    al, 3
0x18000ffee  setnz   al
0x18000fff1  test    al, cl
0x18000fff3  jz      short loc_180010041
0x18000fff5  mov     rax, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x18000fffc  mov     rcx, r14
0x18000ffff  mov     ebx, [rax+40Ch]
0x180010005  call    cs:__imp_?Size@CLKRHashTable@@QEBAKXZ; CLKRHashTable::Size(void)
0x18001000b  mov     rcx, cs:g_pDebug
0x180010012  mov     r9, rdi
0x180010015  mov     [rsp+0D8h+var_98], ebx
0x180010019  mov     r8d, 72Bh
0x18001001f  mov     [rsp+0D8h+var_A0], eax
0x180010023  mov     rdx, r15
0x180010026  mov     [rsp+0D8h+var_A8], rsi
0x18001002b  lea     rax, aDeletingApplic; "Deleting application in site: %lu with "...
0x180010032  mov     dword ptr [rsp+0D8h+var_B0], ebp
0x180010036  mov     [rsp+0D8h+var_B8], rax
0x18001003b  call    cs:__imp_PuDbgPrint
0x180010041  mov     rdx, rsi
0x180010044  mov     [rsp+0D8h+var_78], ebp
0x180010048  lea     rcx, [rsp+0D8h+var_70]
0x18001004d  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180010053  mov     ebx, eax
0x180010055  test    eax, eax
0x180010057  jns     short loc_180010094
0x180010059  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180010060  jz      loc_1800101B6
0x180010066  mov     rcx, cs:g_pDebug
0x18001006d  lea     rax, aFailedMemoryAl_0; "Failed memory allocation when checking "...
0x180010074  mov     [rsp+0D8h+var_B0], rax
0x180010079  mov     r9, rdi
0x18001007c  mov     r8d, 738h
0x180010082  mov     dword ptr [rsp+0D8h+var_B8], ebx
0x180010086  mov     rdx, r15
0x180010089  call    cs:__imp_PuDbgPrintError
0x18001008f  jmp     loc_1800101B6
0x180010094  lea     r8, [rsp+0D8h+var_88]
0x180010099  mov     [rsp+0D8h+var_88], 0
0x1800100a2  lea     rdx, [rsp+0D8h+var_78]
0x1800100a7  mov     rcx, r14
0x1800100aa  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x1800100b0  cmp     eax, 2
0x1800100b3  jnz     short loc_180010103
0x1800100b5  mov     eax, cs:g_dwDebugFlags
0x1800100bb  test    eax, 50000h
0x1800100c0  setnz   cl
0x1800100c3  test    al, 3
0x1800100c5  setnz   al
0x1800100c8  test    al, cl
0x1800100ca  jz      loc_1800101CB
0x1800100d0  mov     rcx, cs:g_pDebug
0x1800100d7  lea     rax, aReceivedAChang; "Received a change notification for an a"...
0x1800100de  mov     dword ptr [rsp+0D8h+var_A8], ebp
0x1800100e2  mov     r9, rdi
0x1800100e5  mov     [rsp+0D8h+var_B0], rsi
0x1800100ea  mov     r8d, 75Bh
0x1800100f0  mov     rdx, r15
0x1800100f3  mov     [rsp+0D8h+var_B8], rax
0x1800100f8  call    cs:__imp_PuDbgPrint
0x1800100fe  jmp     loc_1800101CB
0x180010103  test    eax, eax
0x180010105  jz      short loc_180010144
0x180010107  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001010e  jz      short loc_18001013D
0x180010110  mov     rcx, cs:g_pDebug
0x180010117  lea     rax, aFindingApplica; "Finding application to delete in hashta"...
0x18001011e  mov     [rsp+0D8h+var_B0], rax
0x180010123  mov     r9, rdi
0x180010126  mov     r8d, 76Ah
0x18001012c  mov     dword ptr [rsp+0D8h+var_B8], 80004005h
0x180010134  mov     rdx, r15
0x180010137  call    cs:__imp_PuDbgPrintError
0x18001013d  mov     ebx, 80004005h
0x180010142  jmp     short loc_1800101B6
0x180010144  mov     rdi, [rsp+0D8h+var_88]
0x180010149  mov     rcx, r14
0x18001014c  mov     rdx, rdi
0x18001014f  call    cs:__imp_?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z; CLKRHashTable::DeleteRecord(void const *)
0x180010155  test    eax, eax
0x180010157  jz      short loc_18001019A
0x180010159  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180010160  jz      short loc_180010193
0x180010162  mov     rcx, cs:g_pDebug
0x180010169  lea     rax, aRemovingApplic; "Removing application from hashtable fai"...
0x180010170  mov     [rsp+0D8h+var_B0], rax
0x180010175  lea     r9, aUlAndWorkerMan_2; "UL_AND_WORKER_MANAGER::DeleteApplicatio"...
0x18001017c  mov     r8d, 7ACh
0x180010182  mov     dword ptr [rsp+0D8h+var_B8], 80004005h
0x18001018a  mov     rdx, r15
0x18001018d  call    cs:__imp_PuDbgPrintError
0x180010193  mov     ebx, 80004005h
0x180010198  jmp     short loc_1800101B2
0x18001019a  xor     ebx, ebx
0x18001019c  test    rdi, rdi
0x18001019f  jz      short loc_1800101B2
0x1800101a1  mov     rax, [rdi]
0x1800101a4  lea     edx, [rbx+1]
0x1800101a7  mov     rcx, rdi
0x1800101aa  mov     rax, [rax]
0x1800101ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101b2  test    ebx, ebx
0x1800101b4  jns     short loc_1800101CB
0x1800101b6  mov     r9d, ebp; unsigned int
0x1800101b9  mov     [rsp+0D8h+var_B8], rsi; unsigned __int16 *
0x1800101be  mov     r8d, ebx; int
0x1800101c1  mov     edx, 0C00013EFh; unsigned int
0x1800101c6  call    ?LogApplicationError@WAS_ERROR_LOGGER@@QEAAXKJKPEBG@Z; WAS_ERROR_LOGGER::LogApplicationError(ulong,long,ulong,ushort const *)
0x1800101cb  lea     rcx, [rsp+0D8h+var_70]
0x1800101d0  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800101d6  mov     rcx, [rsp+0D8h+var_38]
0x1800101de  xor     rcx, rsp; StackCookie
0x1800101e1  call    __security_check_cookie
0x1800101e6  mov     rbx, [rsp+0D8h+arg_18]
0x1800101ee  add     rsp, 0B0h
0x1800101f5  pop     r15
0x1800101f7  pop     r14
0x1800101f9  pop     rdi
0x1800101fa  pop     rsi
0x1800101fb  pop     rbp
0x1800101fc  retn
```
