# UL_AND_WORKER_MANAGER::CreateApplication(APPLICATION_DATA_OBJECT *)

- ea: `0x18000edf8`
- end: `0x18000f209`
- name: `?CreateApplication@UL_AND_WORKER_MANAGER@@QEAAXPEAVAPPLICATION_DATA_OBJECT@@@Z`
- size: `1041`
- prototype: `void __fastcall(UL_AND_WORKER_MANAGER *__hidden this, struct APPLICATION_DATA_OBJECT *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000f6f4`

## callees

- `0x180001234`
- `0x18000edf8`
- `0x180015b84`
- `0x180016038`
- `0x18003dd48`
- `0x180061060`
- `0x180062010`

## import_xrefs

- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18000f123`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18000f123`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18000ee87`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18000ef2a`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18000ee87`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18000ef2a`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18000f086`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18000f086`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000f1db`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000f1db`
- `iisutil!PuDbgPrint` at `0x18000f171`
- `iisutil!PuDbgPrint` at `0x18000f171`
- `iisutil!PuDbgPrintError` at `0x18000eeeb`
- `iisutil!PuDbgPrintError` at `0x18000ef9a`
- `iisutil!PuDbgPrintError` at `0x18000f04b`
- `iisutil!PuDbgPrintError` at `0x18000f0c8`
- `iisutil!PuDbgPrintError` at `0x18000f1b6`
- `iisutil!PuDbgPrintError` at `0x18000eeeb`
- `iisutil!PuDbgPrintError` at `0x18000ef9a`
- `iisutil!PuDbgPrintError` at `0x18000f04b`
- `iisutil!PuDbgPrintError` at `0x18000f0c8`
- `iisutil!PuDbgPrintError` at `0x18000f1b6`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000ee2a`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000ee2a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000ee40`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000ee40`

## string_xrefs

- `0x18000eebd`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\ul_and_worker_manager.cxx`
- `0x18000ef64`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\ul_and_worker_manager.cxx`
- `0x18000f044`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\ul_and_worker_manager.cxx`
- `0x18000f0b9`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\ul_and_worker_manager.cxx`
- `0x18000f13b`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\ul_and_worker_manager.cxx`
- `0x18000f1af`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\ul_and_worker_manager.cxx`
- `0x18000ee59`: `Failed memory allocation when checking if created application exists\n`
- `0x18000eeaf`: `UL_AND_WORKER_MANAGER::CreateApplication`
- `0x18000ef56`: `UL_AND_WORKER_MANAGER::CreateApplication`
- `0x18000f033`: `UL_AND_WORKER_MANAGER::CreateApplication`
- `0x18000f0ad`: `UL_AND_WORKER_MANAGER::CreateApplication`
- `0x18000f130`: `UL_AND_WORKER_MANAGER::CreateApplication`
- `0x18000f1a8`: `UL_AND_WORKER_MANAGER::CreateApplication`
- `0x18000eed7`: `Attempting to create application ( site %d, url %S ) that references a non-existent virtual site\n`
- `0x18000ef86`: `Attempting to create application ( site %d, url %S ) that references a non-existent app pool %S\n`
- `0x18000f165`: `New application in site: %lu with path: %S, assigned to app pool: %S, added to application hashtable; total number now: %lu; change id %lu\n`

## pseudocode

```c
void __fastcall UL_AND_WORKER_MANAGER::CreateApplication(
        UL_AND_WORKER_MANAGER *this,
        struct APPLICATION_DATA_OBJECT *a2)
{
  const unsigned __int16 *v4; // rdx
  WAS_ERROR_LOGGER *v5; // rcx
  int v6; // ebx
  __int64 v7; // rdx
  APPLICATION *v8; // rdi
  int Key; // eax
  __int64 v10; // rdx
  int v11; // eax
  APPLICATION *v12; // rax
  struct APP_POOL *v13; // r14
  int v14; // eax
  int v15; // ebx
  unsigned int v16; // eax
  struct APP_POOL *v17; // [rsp+50h] [rbp-78h] BYREF
  struct VIRTUAL_SITE *v18; // [rsp+58h] [rbp-70h] BYREF
  int v19; // [rsp+60h] [rbp-68h]
  _BYTE v20[56]; // [rsp+68h] [rbp-60h] BYREF

  STRU::STRU((STRU *)v20);
  v4 = (const unsigned __int16 *)*((_QWORD *)a2 + 10);
  v19 = *((_DWORD *)a2 + 26);
  v6 = STRU::Copy((STRU *)v20, v4);
  if ( v6 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\ul_and_worker_manager.cxx",
        815,
        "UL_AND_WORKER_MANAGER::CreateApplication",
        v6,
        "Failed memory allocation when checking if created application exists\n");
    goto LABEL_34;
  }
  v7 = *((unsigned int *)a2 + 26);
  v8 = 0;
  v18 = 0;
  Key = CLKRHashTable::FindKey((char *)this + 96, v7, &v18);
  if ( Key )
  {
    if ( Key == 2 )
    {
      v6 = -2147024809;
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\ul_and_worker_manager.cxx",
          854,
          "UL_AND_WORKER_MANAGER::CreateApplication",
          -2147024809,
          "Attempting to create application ( site %d, url %S ) that references a non-existent virtual site\n",
          *((_QWORD *)a2 + 10),
          *((_DWORD *)a2 + 26));
      goto LABEL_34;
    }
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\ul_and_worker_manager.cxx",
        867,
        "UL_AND_WORKER_MANAGER::CreateApplication",
        -2147467259,
        "Looking up virtual site referenced by application failed\n");
LABEL_28:
    v6 = -2147467259;
    if ( !v8 )
    {
LABEL_34:
      WAS_ERROR_LOGGER::LogApplicationError(
        v5,
        0xC00013EC,
        v6,
        *((_DWORD *)a2 + 26),
        *((const unsigned __int16 **)a2 + 10));
      goto LABEL_35;
    }
LABEL_29:
    (**(void (__fastcall ***)(APPLICATION *, __int64))v8)(v8, 1);
    goto LABEL_34;
  }
  v10 = *((_QWORD *)a2 + 19);
  v17 = 0;
  v11 = CLKRHashTable::FindKey((char *)this + 16, v10, &v17);
  if ( v11 )
  {
    if ( v11 == 2 )
    {
      v6 = -2147024809;
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\ul_and_worker_manager.cxx",
          896,
          "UL_AND_WORKER_MANAGER::CreateApplication",
          -2147024809,
          "Attempting to create application ( site %d, url %S ) that references a non-existent app pool %S\n",
          *((_DWORD *)a2 + 26),
          *((const wchar_t **)a2 + 10),
          *((const wchar_t **)a2 + 19));
      goto LABEL_34;
    }
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\ul_and_worker_manager.cxx",
        909,
        "UL_AND_WORKER_MANAGER::CreateApplication",
        -2147467259,
        "Looking up app pool referenced by application failed\n");
    goto LABEL_28;
  }
  v12 = (APPLICATION *)operator new(0x158u);
  if ( !v12 || (v8 = APPLICATION::APPLICATION(v12)) == 0 )
  {
    v6 = -2147024888;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\ul_and_worker_manager.cxx",
        924,
        "UL_AND_WORKER_MANAGER::CreateApplication",
        -2147024888,
        "Allocating APPLICATION failed\n");
    goto LABEL_34;
  }
  v13 = v17;
  v6 = APPLICATION::Initialize(v8, a2, v18, v17, *((_DWORD *)this + 109));
  if ( v6 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\ul_and_worker_manager.cxx",
        943,
        "UL_AND_WORKER_MANAGER::CreateApplication",
        v6,
        "Initializing application object failed\n");
    goto LABEL_29;
  }
  v14 = *((_DWORD *)this + 109);
  if ( v14 == -1 )
  {
    *((_DWORD *)this + 109) = 0;
  }
  else if ( v14 )
  {
    *((_DWORD *)this + 109) = v14 + 1;
  }
  if ( (unsigned int)CLKRHashTable::InsertRecord((char *)this + 184, v8, 0) )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\ul_and_worker_manager.cxx",
        984,
        "UL_AND_WORKER_MANAGER::CreateApplication",
        -2147467259,
        "Inserting application into hashtable failed\n");
    goto LABEL_28;
  }
  if ( (g_dwDebugFlags & 0x30000) != 0 && (g_dwDebugFlags & 3) != 0 )
  {
    v15 = *((_DWORD *)g_pWebAdminService + 259);
    v16 = CLKRHashTable::Size((UL_AND_WORKER_MANAGER *)((char *)this + 184));
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\ul_and_worker_manager.cxx",
      1002,
      "UL_AND_WORKER_MANAGER::CreateApplication",
      "New application in site: %lu with path: %S, assigned to app pool: %S, added to application hashtable; total number"
      " now: %lu; change id %lu\n",
      *((_DWORD *)a2 + 26),
      *((const wchar_t **)a2 + 10),
      *((const wchar_t **)v13 + 7),
      v16,
      v15);
  }
LABEL_35:
  STRU::~STRU((STRU *)v20);
}

```

## disassembly

```asm
0x18000edf8  mov     [rsp+arg_10], rbx
0x18000edfd  mov     [rsp+arg_18], rbp
0x18000ee02  push    rsi
0x18000ee03  push    rdi
0x18000ee04  push    r14
0x18000ee06  sub     rsp, 0B0h
0x18000ee0d  mov     rax, cs:__security_cookie
0x18000ee14  xor     rax, rsp
0x18000ee17  mov     [rsp+0C8h+var_28], rax
0x18000ee1f  mov     rbp, rcx
0x18000ee22  mov     rsi, rdx
0x18000ee25  lea     rcx, [rsp+0C8h+var_60]
0x18000ee2a  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000ee30  mov     eax, [rsi+68h]
0x18000ee33  lea     rcx, [rsp+0C8h+var_60]
0x18000ee38  mov     rdx, [rsi+50h]
0x18000ee3c  mov     [rsp+0C8h+var_68], eax
0x18000ee40  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000ee46  mov     ebx, eax
0x18000ee48  test    eax, eax
0x18000ee4a  jns     short loc_18000EE74
0x18000ee4c  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000ee53  jz      loc_18000F1BC
0x18000ee59  lea     rax, aFailedMemoryAl_0; "Failed memory allocation when checking "...
0x18000ee60  mov     r8d, 32Fh
0x18000ee66  mov     [rsp+0C8h+var_A0], rax
0x18000ee6b  mov     dword ptr [rsp+0C8h+var_A8], ebx
0x18000ee6f  jmp     loc_18000F1A1
0x18000ee74  mov     edx, [rsi+68h]
0x18000ee77  lea     rcx, [rbp+60h]
0x18000ee7b  xor     edi, edi
0x18000ee7d  lea     r8, [rsp+0C8h+var_70]
0x18000ee82  mov     [rsp+0C8h+var_70], rdi
0x18000ee87  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x18000ee8d  test    eax, eax
0x18000ee8f  jz      loc_18000EF15
0x18000ee95  cmp     eax, 2
0x18000ee98  jnz     short loc_18000EEF6
0x18000ee9a  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000eea1  mov     ebx, 80070057h
0x18000eea6  jz      loc_18000F1BC
0x18000eeac  mov     eax, [rsi+68h]
0x18000eeaf  lea     r9, aUlAndWorkerMan_16; "UL_AND_WORKER_MANAGER::CreateApplicatio"...
0x18000eeb6  mov     rcx, cs:g_pDebug
0x18000eebd  lea     rdx, aServercommonIn_68; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000eec4  mov     dword ptr [rsp+0C8h+var_90], eax
0x18000eec8  mov     r8d, 356h
0x18000eece  mov     rax, [rsi+50h]
0x18000eed2  mov     [rsp+0C8h+var_98], rax
0x18000eed7  lea     rax, aAttemptingToCr_0; "Attempting to create application ( site"...
0x18000eede  mov     [rsp+0C8h+var_A0], rax
0x18000eee3  mov     dword ptr [rsp+0C8h+var_A8], 80070057h
0x18000eeeb  call    cs:__imp_PuDbgPrintError
0x18000eef1  jmp     loc_18000F1BC
0x18000eef6  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000eefd  jz      loc_18000F0CE
0x18000ef03  lea     rax, aLookingUpVirtu; "Looking up virtual site referenced by a"...
0x18000ef0a  mov     r8d, 363h
0x18000ef10  jmp     loc_18000F0A6
0x18000ef15  mov     rdx, [rsi+98h]
0x18000ef1c  lea     rcx, [rbp+10h]
0x18000ef20  lea     r8, [rsp+0C8h+var_78]
0x18000ef25  mov     [rsp+0C8h+var_78], rdi
0x18000ef2a  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x18000ef30  test    eax, eax
0x18000ef32  jz      loc_18000EFC4
0x18000ef38  cmp     eax, 2
0x18000ef3b  jnz     short loc_18000EFA5
0x18000ef3d  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000ef44  mov     ebx, 80070057h
0x18000ef49  jz      loc_18000F1BC
0x18000ef4f  mov     rax, [rsi+98h]
0x18000ef56  lea     r9, aUlAndWorkerMan_16; "UL_AND_WORKER_MANAGER::CreateApplicatio"...
0x18000ef5d  mov     rcx, cs:g_pDebug
0x18000ef64  lea     rdx, aServercommonIn_68; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000ef6b  mov     [rsp+0C8h+var_88], rax
0x18000ef70  mov     r8d, 380h
0x18000ef76  mov     rax, [rsi+50h]
0x18000ef7a  mov     [rsp+0C8h+var_90], rax
0x18000ef7f  mov     eax, [rsi+68h]
0x18000ef82  mov     dword ptr [rsp+0C8h+var_98], eax
0x18000ef86  lea     rax, aAttemptingToCr; "Attempting to create application ( site"...
0x18000ef8d  mov     [rsp+0C8h+var_A0], rax
0x18000ef92  mov     dword ptr [rsp+0C8h+var_A8], 80070057h
0x18000ef9a  call    cs:__imp_PuDbgPrintError
0x18000efa0  jmp     loc_18000F1BC
0x18000efa5  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000efac  jz      loc_18000F0CE
0x18000efb2  lea     rax, aLookingUpAppPo_0; "Looking up app pool referenced by appli"...
0x18000efb9  mov     r8d, 38Dh
0x18000efbf  jmp     loc_18000F0A6
0x18000efc4  mov     ecx, 158h; Size
0x18000efc9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000efce  test    rax, rax
0x18000efd1  jz      loc_18000F179
0x18000efd7  mov     rcx, rax; this
0x18000efda  call    ??0APPLICATION@@QEAA@XZ; APPLICATION::APPLICATION(void)
0x18000efdf  mov     rdi, rax
0x18000efe2  test    rax, rax
0x18000efe5  jz      loc_18000F179
0x18000efeb  mov     eax, [rbp+1B4h]
0x18000eff1  mov     rdx, rsi; struct APPLICATION_DATA_OBJECT *
0x18000eff4  mov     r14, [rsp+0C8h+var_78]
0x18000eff9  mov     rcx, rdi; this
0x18000effc  mov     r8, [rsp+0C8h+var_70]; struct VIRTUAL_SITE *
0x18000f001  mov     r9, r14; struct APP_POOL *
0x18000f004  mov     dword ptr [rsp+0C8h+var_A8], eax; unsigned int
0x18000f008  call    ?Initialize@APPLICATION@@QEAAJPEAVAPPLICATION_DATA_OBJECT@@PEAVVIRTUAL_SITE@@PEAVAPP_POOL@@K@Z; APPLICATION::Initialize(APPLICATION_DATA_OBJECT *,VIRTUAL_SITE *,APP_POOL *,ulong)
0x18000f00d  mov     ebx, eax
0x18000f00f  test    eax, eax
0x18000f011  jns     short loc_18000F056
0x18000f013  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000f01a  jz      loc_18000F0DC
0x18000f020  mov     rcx, cs:g_pDebug
0x18000f027  lea     rax, aInitializingAp_0; "Initializing application object failed"...
0x18000f02e  mov     [rsp+0C8h+var_A0], rax
0x18000f033  lea     r9, aUlAndWorkerMan_16; "UL_AND_WORKER_MANAGER::CreateApplicatio"...
0x18000f03a  mov     r8d, 3AFh
0x18000f040  mov     dword ptr [rsp+0C8h+var_A8], ebx
0x18000f044  lea     rdx, aServercommonIn_68; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000f04b  call    cs:__imp_PuDbgPrintError
0x18000f051  jmp     loc_18000F0DC
0x18000f056  mov     eax, [rbp+1B4h]
0x18000f05c  cmp     eax, 0FFFFFFFFh
0x18000f05f  jnz     short loc_18000F06D
0x18000f061  mov     dword ptr [rbp+1B4h], 0
0x18000f06b  jmp     short loc_18000F079
0x18000f06d  test    eax, eax
0x18000f06f  jz      short loc_18000F079
0x18000f071  inc     eax
0x18000f073  mov     [rbp+1B4h], eax
0x18000f079  xor     r8d, r8d
0x18000f07c  lea     rcx, [rbp+0B8h]
0x18000f083  mov     rdx, rdi
0x18000f086  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x18000f08c  test    eax, eax
0x18000f08e  jz      short loc_18000F0F4
0x18000f090  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000f097  jz      short loc_18000F0CE
0x18000f099  lea     rax, aInsertingAppli; "Inserting application into hashtable fa"...
0x18000f0a0  mov     r8d, 3D8h
0x18000f0a6  mov     rcx, cs:g_pDebug
0x18000f0ad  lea     r9, aUlAndWorkerMan_16; "UL_AND_WORKER_MANAGER::CreateApplicatio"...
0x18000f0b4  mov     [rsp+0C8h+var_A0], rax
0x18000f0b9  lea     rdx, aServercommonIn_68; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000f0c0  mov     dword ptr [rsp+0C8h+var_A8], 80004005h
0x18000f0c8  call    cs:__imp_PuDbgPrintError
0x18000f0ce  mov     ebx, 80004005h
0x18000f0d3  test    rdi, rdi
0x18000f0d6  jz      loc_18000F1BC
0x18000f0dc  mov     rax, [rdi]
0x18000f0df  mov     edx, 1
0x18000f0e4  mov     rcx, rdi
0x18000f0e7  mov     rax, [rax]
0x18000f0ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0ef  jmp     loc_18000F1BC
0x18000f0f4  mov     eax, cs:g_dwDebugFlags
0x18000f0fa  test    eax, 30000h
0x18000f0ff  setnz   dl
0x18000f102  test    al, 3
0x18000f104  setnz   al
0x18000f107  test    al, dl
0x18000f109  jz      loc_18000F1D6
0x18000f10f  mov     rax, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x18000f116  lea     rcx, [rbp+0B8h]
0x18000f11d  mov     ebx, [rax+40Ch]
0x18000f123  call    cs:__imp_?Size@CLKRHashTable@@QEBAKXZ; CLKRHashTable::Size(void)
0x18000f129  mov     rcx, cs:g_pDebug
0x18000f130  lea     r9, aUlAndWorkerMan_16; "UL_AND_WORKER_MANAGER::CreateApplicatio"...
0x18000f137  mov     [rsp+0C8h+var_80], ebx
0x18000f13b  lea     rdx, aServercommonIn_68; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000f142  mov     dword ptr [rsp+0C8h+var_88], eax
0x18000f146  mov     r8d, 3EAh
0x18000f14c  mov     rax, [r14+38h]
0x18000f150  mov     [rsp+0C8h+var_90], rax
0x18000f155  mov     rax, [rsi+50h]
0x18000f159  mov     [rsp+0C8h+var_98], rax
0x18000f15e  mov     eax, [rsi+68h]
0x18000f161  mov     dword ptr [rsp+0C8h+var_A0], eax
0x18000f165  lea     rax, aNewApplication; "New application in site: %lu with path:"...
0x18000f16c  mov     [rsp+0C8h+var_A8], rax
0x18000f171  call    cs:__imp_PuDbgPrint
0x18000f177  jmp     short loc_18000F1D6
0x18000f179  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000f180  mov     ebx, 80070008h
0x18000f185  jz      short loc_18000F1BC
0x18000f187  lea     rax, aAllocatingAppl; "Allocating APPLICATION failed\n"
0x18000f18e  mov     r8d, 39Ch
0x18000f194  mov     [rsp+0C8h+var_A0], rax
0x18000f199  mov     dword ptr [rsp+0C8h+var_A8], 80070008h
0x18000f1a1  mov     rcx, cs:g_pDebug
0x18000f1a8  lea     r9, aUlAndWorkerMan_16; "UL_AND_WORKER_MANAGER::CreateApplicatio"...
0x18000f1af  lea     rdx, aServercommonIn_68; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000f1b6  call    cs:__imp_PuDbgPrintError
0x18000f1bc  mov     rax, [rsi+50h]
0x18000f1c0  mov     r8d, ebx; int
0x18000f1c3  mov     r9d, [rsi+68h]; unsigned int
0x18000f1c7  mov     edx, 0C00013ECh; unsigned int
0x18000f1cc  mov     [rsp+0C8h+var_A8], rax; unsigned __int16 *
0x18000f1d1  call    ?LogApplicationError@WAS_ERROR_LOGGER@@QEAAXKJKPEBG@Z; WAS_ERROR_LOGGER::LogApplicationError(ulong,long,ulong,ushort const *)
0x18000f1d6  lea     rcx, [rsp+0C8h+var_60]
0x18000f1db  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000f1e1  mov     rcx, [rsp+0C8h+var_28]
0x18000f1e9  xor     rcx, rsp; StackCookie
0x18000f1ec  call    __security_check_cookie
0x18000f1f1  lea     r11, [rsp+0C8h+var_18]
0x18000f1f9  mov     rbx, [r11+30h]
0x18000f1fd  mov     rbp, [r11+38h]
0x18000f201  mov     rsp, r11
0x18000f204  pop     r14
0x18000f206  pop     rdi
0x18000f207  pop     rsi
0x18000f208  retn
```
