# WORKER_PROCESS::HandleQueueStopped(ushort const *,ulong,long)

- ea: `0x1800238ac`
- end: `0x1800239e5`
- name: `?HandleQueueStopped@WORKER_PROCESS@@QEAAXPEBGKJ@Z`
- size: `313`
- prototype: `void(WORKER_PROCESS *__hidden this, const unsigned __int16 *, unsigned int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180029090`

## callees

- `0x180004ed4`
- `0x1800238ac`
- `0x180025928`
- `0x18003e498`
- `0x180061060`

## import_xrefs

- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180023959`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180023959`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800239c3`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800239c3`
- `iisutil!PuDbgPrintError` at `0x180023997`
- `iisutil!PuDbgPrintError` at `0x180023997`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800238db`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800238db`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180023913`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180023913`

## string_xrefs

- `0x18002398c`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\worker_process.cxx`
- `0x18002392c`: `Could not setup the protocol id string to find the request queue instance\n`

## pseudocode

```c
void __fastcall WORKER_PROCESS::HandleQueueStopped(WORKER_PROCESS *this, const unsigned __int16 *a2, int a3, int a4)
{
  WEB_ADMIN_SERVICE *v8; // rcx
  int v9; // edi
  struct REQUEST_QUEUE_INSTANCE *v10; // [rsp+30h] [rbp-88h] BYREF
  _BYTE v11[56]; // [rsp+40h] [rbp-78h] BYREF
  int v12; // [rsp+78h] [rbp-40h]

  STRU::STRU((STRU *)v11);
  if ( *((_DWORD *)this + 114) )
  {
    v8 = g_pWebAdminService;
    if ( *((_DWORD *)g_pWebAdminService + 412) )
    {
      *((_DWORD *)this + 114) = 0;
      WEB_ADMIN_SERVICE::FinishLaunchHttpLA(v8, a4);
    }
  }
  v9 = STRU::Copy((STRU *)v11, a2);
  if ( v9 >= 0 )
  {
    v12 = a3;
    v10 = 0;
    if ( (unsigned int)CLKRHashTable::FindKey((char *)this + 272, v11, &v10) )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\worker_process.cxx",
          7847,
          "WORKER_PROCESS::HandleQueueStopped",
          v9,
          "Could not find request queue instance to report the queue stopped\n");
    }
    else if ( a4 >= 0 )
    {
      REQUEST_QUEUE_INSTANCE::Terminate(v10);
    }
    else
    {
      WORKER_PROCESS::ReportIllnessCausedByQueueStopping(*((WORKER_PROCESS **)v10 + 6), v10, a4);
    }
  }
  else if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\worker_process.cxx",
      7820,
      "WORKER_PROCESS::HandleQueueStopped",
      v9,
      "Could not setup the protocol id string to find the request queue instance\n");
  }
  STRU::~STRU((STRU *)v11);
}

```

## disassembly

```asm
0x1800238ac  push    rbx
0x1800238ae  push    rbp
0x1800238af  push    rsi
0x1800238b0  push    rdi
0x1800238b1  sub     rsp, 98h
0x1800238b8  mov     rax, cs:__security_cookie
0x1800238bf  xor     rax, rsp
0x1800238c2  mov     [rsp+0B8h+var_38], rax
0x1800238ca  mov     rsi, rcx
0x1800238cd  mov     ebx, r9d
0x1800238d0  lea     rcx, [rsp+0B8h+var_78]
0x1800238d5  mov     ebp, r8d
0x1800238d8  mov     rdi, rdx
0x1800238db  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800238e1  cmp     dword ptr [rsi+1C8h], 0
0x1800238e8  jz      short loc_18002390B
0x1800238ea  mov     rcx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; this
0x1800238f1  cmp     dword ptr [rcx+670h], 0
0x1800238f8  jz      short loc_18002390B
0x1800238fa  mov     edx, ebx; int
0x1800238fc  mov     dword ptr [rsi+1C8h], 0
0x180023906  call    ?FinishLaunchHttpLA@WEB_ADMIN_SERVICE@@QEAAXJ@Z; WEB_ADMIN_SERVICE::FinishLaunchHttpLA(long)
0x18002390b  mov     rdx, rdi
0x18002390e  lea     rcx, [rsp+0B8h+var_78]
0x180023913  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180023919  mov     edi, eax
0x18002391b  test    eax, eax
0x18002391d  jns     short loc_18002393B
0x18002391f  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180023926  jz      loc_1800239BE
0x18002392c  lea     rax, aCouldNotSetupT; "Could not setup the protocol id string "...
0x180023933  mov     r8d, 1E8Ch
0x180023939  jmp     short loc_180023979
0x18002393b  lea     rcx, [rsi+110h]
0x180023942  mov     [rsp+0B8h+var_40], ebp
0x180023946  lea     r8, [rsp+0B8h+var_88]
0x18002394b  mov     [rsp+0B8h+var_88], 0
0x180023954  lea     rdx, [rsp+0B8h+var_78]
0x180023959  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x18002395f  test    eax, eax
0x180023961  jz      short loc_18002399F
0x180023963  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002396a  jz      short loc_1800239BE
0x18002396c  lea     rax, aCouldNotFindRe_0; "Could not find request queue instance t"...
0x180023973  mov     r8d, 1EA7h
0x180023979  mov     rcx, cs:g_pDebug
0x180023980  lea     r9, aWorkerProcessH_2; "WORKER_PROCESS::HandleQueueStopped"
0x180023987  mov     [rsp+0B8h+var_90], rax
0x18002398c  lea     rdx, aServercommonIn_24; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180023993  mov     [rsp+0B8h+var_98], edi
0x180023997  call    cs:__imp_PuDbgPrintError
0x18002399d  jmp     short loc_1800239BE
0x18002399f  mov     rcx, [rsp+0B8h+var_88]; this
0x1800239a4  test    ebx, ebx
0x1800239a6  jns     short loc_1800239B9
0x1800239a8  mov     rdx, rcx; struct REQUEST_QUEUE_INSTANCE *
0x1800239ab  mov     r8d, ebx; int
0x1800239ae  mov     rcx, [rcx+30h]; this
0x1800239b2  call    ?ReportIllnessCausedByQueueStopping@WORKER_PROCESS@@QEAAXPEAVREQUEST_QUEUE_INSTANCE@@J@Z; WORKER_PROCESS::ReportIllnessCausedByQueueStopping(REQUEST_QUEUE_INSTANCE *,long)
0x1800239b7  jmp     short loc_1800239BE
0x1800239b9  call    ?Terminate@REQUEST_QUEUE_INSTANCE@@QEAAXXZ; REQUEST_QUEUE_INSTANCE::Terminate(void)
0x1800239be  lea     rcx, [rsp+0B8h+var_78]
0x1800239c3  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800239c9  mov     rcx, [rsp+0B8h+var_38]
0x1800239d1  xor     rcx, rsp; StackCookie
0x1800239d4  call    __security_check_cookie
0x1800239d9  add     rsp, 98h
0x1800239e0  pop     rdi
0x1800239e1  pop     rsi
0x1800239e2  pop     rbp
0x1800239e3  pop     rbx
0x1800239e4  retn
```
