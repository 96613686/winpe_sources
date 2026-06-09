# WORKER_PROCESS::HandleQueueStarted(ushort const *,ulong)

- ea: `0x180023794`
- end: `0x1800238a6`
- name: `?HandleQueueStarted@WORKER_PROCESS@@QEAAXPEBGK@Z`
- size: `274`
- prototype: `void __fastcall(WORKER_PROCESS *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180028fd0`

## callees

- `0x180004ed4`
- `0x180023794`
- `0x18003e118`
- `0x180061060`

## import_xrefs

- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180023830`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180023830`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180023885`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180023885`
- `iisutil!PuDbgPrintError` at `0x18002386e`
- `iisutil!PuDbgPrintError` at `0x18002386e`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800237bf`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800237bf`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800237ee`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800237ee`

## string_xrefs

- `0x180023863`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\worker_process.cxx`
- `0x180023803`: `Could not setup the protocol id string to find the request queue instance\n`

## pseudocode

```c
void __fastcall WORKER_PROCESS::HandleQueueStarted(WORKER_PROCESS *this, const unsigned __int16 *a2, int a3)
{
  WEB_ADMIN_SERVICE *v6; // rcx
  int v7; // ebx
  REQUEST_QUEUE_INSTANCE *v8; // [rsp+30h] [rbp-78h] BYREF
  _BYTE v9[56]; // [rsp+40h] [rbp-68h] BYREF
  int v10; // [rsp+78h] [rbp-30h]

  STRU::STRU((STRU *)v9);
  v6 = g_pWebAdminService;
  if ( *((_DWORD *)g_pWebAdminService + 412) )
  {
    *((_DWORD *)this + 114) = 0;
    WEB_ADMIN_SERVICE::FinishLaunchHttpLA(v6, 0);
  }
  v7 = STRU::Copy((STRU *)v9, a2);
  if ( v7 >= 0 )
  {
    v10 = a3;
    v8 = 0;
    if ( (unsigned int)CLKRHashTable::FindKey((char *)this + 272, v9, &v8) )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\worker_process.cxx",
          7739,
          "WORKER_PROCESS::HandleQueueStarted",
          v7,
          "Could not find request queue instance to report the queue started\n");
    }
    else
    {
      REQUEST_QUEUE_INSTANCE::RegisterQueueStarted(v8);
    }
  }
  else if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\worker_process.cxx",
      7712,
      "WORKER_PROCESS::HandleQueueStarted",
      v7,
      "Could not setup the protocol id string to find the request queue instance\n");
  }
  STRU::~STRU((STRU *)v9);
}

```

## disassembly

```asm
0x180023794  push    rbx
0x180023796  push    rsi
0x180023797  push    rdi
0x180023798  sub     rsp, 90h
0x18002379f  mov     rax, cs:__security_cookie
0x1800237a6  xor     rax, rsp
0x1800237a9  mov     [rsp+0A8h+var_28], rax
0x1800237b1  mov     rdi, rcx
0x1800237b4  mov     esi, r8d
0x1800237b7  lea     rcx, [rsp+0A8h+var_68]
0x1800237bc  mov     rbx, rdx
0x1800237bf  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800237c5  mov     rcx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; this
0x1800237cc  cmp     dword ptr [rcx+670h], 0
0x1800237d3  jz      short loc_1800237E6
0x1800237d5  xor     edx, edx; int
0x1800237d7  mov     dword ptr [rdi+1C8h], 0
0x1800237e1  call    ?FinishLaunchHttpLA@WEB_ADMIN_SERVICE@@QEAAXJ@Z; WEB_ADMIN_SERVICE::FinishLaunchHttpLA(long)
0x1800237e6  mov     rdx, rbx
0x1800237e9  lea     rcx, [rsp+0A8h+var_68]
0x1800237ee  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800237f4  mov     ebx, eax
0x1800237f6  test    eax, eax
0x1800237f8  jns     short loc_180023812
0x1800237fa  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180023801  jz      short loc_180023880
0x180023803  lea     rax, aCouldNotSetupT; "Could not setup the protocol id string "...
0x18002380a  mov     r8d, 1E20h
0x180023810  jmp     short loc_180023850
0x180023812  lea     rcx, [rdi+110h]
0x180023819  mov     [rsp+0A8h+var_30], esi
0x18002381d  lea     r8, [rsp+0A8h+var_78]
0x180023822  mov     [rsp+0A8h+var_78], 0
0x18002382b  lea     rdx, [rsp+0A8h+var_68]
0x180023830  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x180023836  test    eax, eax
0x180023838  jz      short loc_180023876
0x18002383a  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180023841  jz      short loc_180023880
0x180023843  lea     rax, aCouldNotFindRe; "Could not find request queue instance t"...
0x18002384a  mov     r8d, 1E3Bh
0x180023850  mov     rcx, cs:g_pDebug
0x180023857  lea     r9, aWorkerProcessH_4; "WORKER_PROCESS::HandleQueueStarted"
0x18002385e  mov     [rsp+0A8h+var_80], rax
0x180023863  lea     rdx, aServercommonIn_24; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002386a  mov     [rsp+0A8h+var_88], ebx
0x18002386e  call    cs:__imp_PuDbgPrintError
0x180023874  jmp     short loc_180023880
0x180023876  mov     rcx, [rsp+0A8h+var_78]; this
0x18002387b  call    ?RegisterQueueStarted@REQUEST_QUEUE_INSTANCE@@QEAAXXZ; REQUEST_QUEUE_INSTANCE::RegisterQueueStarted(void)
0x180023880  lea     rcx, [rsp+0A8h+var_68]
0x180023885  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002388b  mov     rcx, [rsp+0A8h+var_28]
0x180023893  xor     rcx, rsp; StackCookie
0x180023896  call    __security_check_cookie
0x18002389b  add     rsp, 90h
0x1800238a2  pop     rdi
0x1800238a3  pop     rsi
0x1800238a4  pop     rbx
0x1800238a5  retn
```
