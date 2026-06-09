# HTTP_SERVICE::FinishStartService(void)

- ea: `0x180053e68`
- end: `0x1800540b4`
- name: `?FinishStartService@HTTP_SERVICE@@QEAAJXZ`
- size: `588`
- prototype: `__int64 __fastcall(HTTP_SERVICE *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180004ed4`

## callees

- `0x180004290`
- `0x180053e68`
- `0x180054324`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180054063`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180054063`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180053fe8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180053fe8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180053ee7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180053f24`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180053ee7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180053f24`
- `iisutil!?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z` at `0x180053f7c`
- `iisutil!?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z` at `0x180053f7c`
- `iisutil!PuDbgPrint` at `0x180053eda`
- `iisutil!PuDbgPrint` at `0x180053eda`
- `iisutil!PuDbgPrintError` at `0x180053fd9`
- `iisutil!PuDbgPrintError` at `0x180054059`
- `iisutil!PuDbgPrintError` at `0x1800540a9`
- `iisutil!PuDbgPrintError` at `0x180053fd9`
- `iisutil!PuDbgPrintError` at `0x180054059`
- `iisutil!PuDbgPrintError` at `0x1800540a9`

## string_xrefs

- `0x180053ea6`: `Not changing service state to: %lu, because current state is: %lu, was expected to be: %lu\n`
- `0x180054035`: `Could not update service status\n`
- `0x180053ece`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\http_service.cxx`
- `0x180053fd2`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\http_service.cxx`
- `0x180054052`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\http_service.cxx`
- `0x1800540a2`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\http_service.cxx`
- `0x180054091`: `HTTP_SERVICE::FinishStartService`
- `0x180053eb5`: `HTTP_SERVICE::FinishStateTransition`
- `0x180053fc1`: `HTTP_SERVICE::FinishStateTransition`
- `0x180054041`: `HTTP_SERVICE::FinishStateTransition`

## pseudocode

```c
__int64 __fastcall HTTP_SERVICE::FinishStartService(HTTP_SERVICE *this)
{
  int v1; // edx
  int updated; // edi
  WEB_ADMIN_SERVICE *v4; // rbx
  WEB_ADMIN_SERVICE *v5; // rbx
  _QWORD v7[4]; // [rsp+40h] [rbp-28h] BYREF
  int v8; // [rsp+70h] [rbp+8h] BYREF

  v1 = *((_DWORD *)this + 3);
  if ( v1 != 2 )
  {
    updated = 0;
    if ( (g_dwDebugFlags & 0x30000) != 0 && (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\http_service.cxx",
        1157,
        "HTTP_SERVICE::FinishStateTransition",
        "Not changing service state to: %lu, because current state is: %lu, was expected to be: %lu\n",
        4,
        v1,
        2);
LABEL_4:
    v4 = g_pWebAdminService;
    *((_DWORD *)v4 + 352) = GetTickCount64() / 0x3E8;
    v5 = g_pWebAdminService;
    *((_DWORD *)g_pWebAdminService + 353) = 0;
    v7[0] = 0;
    v7[1] = &VIRTUAL_SITE_TABLE::SetVirtualSitesStartTimeAction;
    v7[2] = &v8;
    v8 = GetTickCount64() / 0x3E8;
    CLKRHashTable::Apply(
      (char *)v5 + 208,
      CTypedHashTable<HASH_POOL_HASH,POOL_HASH_ENTRY,APP_POOL_HASH const *,CLKRHashTable>::_Action,
      v7,
      1);
    return (unsigned int)updated;
  }
  updated = WEB_ADMIN_SERVICE::CancelTimer(this, (struct _TP_TIMER **)this + 7);
  if ( updated >= 0 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
    *((_DWORD *)this + 4) = 5;
    updated = HTTP_SERVICE::UpdateServiceStatus(this, 4u, 0, 0, 0, 0, 0);
    if ( updated < 0 && (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\http_service.cxx",
        1205,
        "HTTP_SERVICE::FinishStateTransition",
        updated,
        "Could not update service status\n");
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
    if ( updated >= 0 )
      goto LABEL_4;
  }
  else
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      return (unsigned int)updated;
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\http_service.cxx",
      1171,
      "HTTP_SERVICE::FinishStateTransition",
      updated,
      "Could not cancel timer\n");
  }
  if ( (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\http_service.cxx",
      563,
      "HTTP_SERVICE::FinishStartService",
      updated,
      "Couldn't finish transition into the running state\n");
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180053e68  mov     [rsp+arg_8], rbx
0x180053e6d  mov     [rsp+arg_10], rbp
0x180053e72  push    rdi
0x180053e73  sub     rsp, 60h
0x180053e77  mov     edx, [rcx+0Ch]
0x180053e7a  mov     rbx, rcx
0x180053e7d  cmp     edx, 2
0x180053e80  jz      loc_180053F96
0x180053e86  mov     eax, cs:g_dwDebugFlags
0x180053e8c  xor     edi, edi
0x180053e8e  test    eax, 30000h
0x180053e93  setnz   cl
0x180053e96  test    al, 3
0x180053e98  setnz   al
0x180053e9b  test    al, cl
0x180053e9d  jz      short loc_180053EE0
0x180053e9f  mov     rcx, cs:g_pDebug
0x180053ea6  lea     rax, aNotChangingSer; "Not changing service state to: %lu, bec"...
0x180053ead  mov     [rsp+68h+var_30], 2
0x180053eb5  lea     r9, aHttpServiceFin; "HTTP_SERVICE::FinishStateTransition"
0x180053ebc  mov     [rsp+68h+var_38], edx
0x180053ec0  mov     r8d, 485h
0x180053ec6  mov     [rsp+68h+var_40], 4
0x180053ece  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180053ed5  mov     qword ptr [rsp+68h+var_48], rax
0x180053eda  call    cs:__imp_PuDbgPrint
0x180053ee0  mov     rbx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x180053ee7  call    cs:__imp_GetTickCount64
0x180053eed  mov     rcx, rax
0x180053ef0  mov     rbp, 624DD2F1A9FBE77h
0x180053efa  mov     rax, rbp
0x180053efd  mul     rcx
0x180053f00  sub     rcx, rdx
0x180053f03  shr     rcx, 1
0x180053f06  add     rcx, rdx
0x180053f09  shr     rcx, 9
0x180053f0d  mov     [rbx+580h], ecx
0x180053f13  mov     rbx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x180053f1a  mov     dword ptr [rbx+584h], 0
0x180053f24  call    cs:__imp_GetTickCount64
0x180053f2a  mov     r9d, 1
0x180053f30  mov     [rsp+68h+var_28], 0
0x180053f39  mov     rcx, rax
0x180053f3c  lea     r8, [rsp+68h+var_28]
0x180053f41  mov     rax, rbp
0x180053f44  mul     rcx
0x180053f47  lea     rax, ?SetVirtualSitesStartTimeAction@VIRTUAL_SITE_TABLE@@SA?AW4LK_ACTION@@PEAVVIRTUAL_SITE@@PEAX@Z; VIRTUAL_SITE_TABLE::SetVirtualSitesStartTimeAction(VIRTUAL_SITE *,void *)
0x180053f4e  sub     rcx, rdx
0x180053f51  mov     [rsp+68h+var_20], rax
0x180053f56  shr     rcx, 1
0x180053f59  lea     rax, [rsp+68h+arg_0]
0x180053f5e  add     rcx, rdx
0x180053f61  mov     [rsp+68h+var_18], rax
0x180053f66  shr     rcx, 9
0x180053f6a  lea     rdx, ?_Action@?$CTypedHashTable@VHASH_POOL_HASH@@VPOOL_HASH_ENTRY@@PEBUAPP_POOL_HASH@@VCLKRHashTable@@@@CA?AW4LK_ACTION@@PEBXPEAX@Z; CTypedHashTable<HASH_POOL_HASH,POOL_HASH_ENTRY,APP_POOL_HASH const *,CLKRHashTable>::_Action(void const *,void *)
0x180053f71  mov     [rsp+68h+arg_0], ecx
0x180053f75  lea     rcx, [rbx+0D0h]
0x180053f7c  call    cs:__imp_?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z; CLKRHashTable::Apply(LK_ACTION (*)(void const *,void *),void *,LK_LOCKTYPE)
0x180053f82  lea     r11, [rsp+68h+var_8]
0x180053f87  mov     eax, edi
0x180053f89  mov     rbx, [r11+18h]
0x180053f8d  mov     rbp, [r11+20h]
0x180053f91  mov     rsp, r11
0x180053f94  pop     rdi
0x180053f95  retn
0x180053f96  lea     rdx, [rcx+38h]; struct _TP_TIMER **
0x180053f9a  call    ?CancelTimer@WEB_ADMIN_SERVICE@@QEAAJPEAPEAU_TP_TIMER@@@Z; WEB_ADMIN_SERVICE::CancelTimer(_TP_TIMER * *)
0x180053f9f  mov     edi, eax
0x180053fa1  test    eax, eax
0x180053fa3  jns     short loc_180053FE4
0x180053fa5  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180053fac  jz      short loc_180053F82
0x180053fae  mov     rcx, cs:g_pDebug
0x180053fb5  lea     rax, aCouldNotCancel_3; "Could not cancel timer\n"
0x180053fbc  mov     qword ptr [rsp+68h+var_40], rax
0x180053fc1  lea     r9, aHttpServiceFin; "HTTP_SERVICE::FinishStateTransition"
0x180053fc8  mov     r8d, 493h
0x180053fce  mov     [rsp+68h+var_48], edi
0x180053fd2  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180053fd9  call    cs:__imp_PuDbgPrintError
0x180053fdf  jmp     loc_180054071
0x180053fe4  lea     rcx, [rbx+48h]; lpCriticalSection
0x180053fe8  call    cs:__imp_EnterCriticalSection
0x180053fee  xor     r9d, r9d; unsigned int
0x180053ff1  mov     [rsp+68h+var_38], 0; int
0x180053ff9  mov     [rsp+68h+var_40], 0; unsigned int
0x180054001  xor     r8d, r8d; unsigned int
0x180054004  mov     rcx, rbx; this
0x180054007  mov     dword ptr [rbx+10h], 5
0x18005400e  mov     [rsp+68h+var_48], 0; unsigned int
0x180054016  lea     edx, [r9+4]; unsigned int
0x18005401a  call    ?UpdateServiceStatus@HTTP_SERVICE@@AEAAJKKKKKH@Z; HTTP_SERVICE::UpdateServiceStatus(ulong,ulong,ulong,ulong,ulong,int)
0x18005401f  mov     edi, eax
0x180054021  test    eax, eax
0x180054023  jns     short loc_18005405F
0x180054025  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005402c  jz      short loc_18005405F
0x18005402e  mov     rcx, cs:g_pDebug
0x180054035  lea     rax, aCouldNotUpdate; "Could not update service status\n"
0x18005403c  mov     qword ptr [rsp+68h+var_40], rax
0x180054041  lea     r9, aHttpServiceFin; "HTTP_SERVICE::FinishStateTransition"
0x180054048  mov     r8d, 4B5h
0x18005404e  mov     [rsp+68h+var_48], edi
0x180054052  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180054059  call    cs:__imp_PuDbgPrintError
0x18005405f  lea     rcx, [rbx+48h]; lpCriticalSection
0x180054063  call    cs:__imp_LeaveCriticalSection
0x180054069  test    edi, edi
0x18005406b  jns     loc_180053EE0
0x180054071  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180054078  jz      loc_180053F82
0x18005407e  mov     rcx, cs:g_pDebug
0x180054085  lea     rax, aCouldnTFinishT_0; "Couldn't finish transition into the run"...
0x18005408c  mov     qword ptr [rsp+68h+var_40], rax
0x180054091  lea     r9, aHttpServiceFin_0; "HTTP_SERVICE::FinishStartService"
0x180054098  mov     r8d, 233h
0x18005409e  mov     [rsp+68h+var_48], edi
0x1800540a2  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800540a9  call    cs:__imp_PuDbgPrintError
0x1800540af  jmp     loc_180053F82
```
