# UL_AND_WORKER_MANAGER::CreateOrModifyApplication(APPLICATION_DATA_OBJECT *)

- ea: `0x18000f6f4`
- end: `0x18000f919`
- name: `?CreateOrModifyApplication@UL_AND_WORKER_MANAGER@@QEAAXPEAVAPPLICATION_DATA_OBJECT@@@Z`
- size: `549`
- prototype: `void __fastcall(UL_AND_WORKER_MANAGER *__hidden this, struct APPLICATION_DATA_OBJECT *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003ad70`
- `0x18003b1d0`

## callees

- `0x18000edf8`
- `0x18000f6f4`
- `0x180016174`
- `0x18003dd48`
- `0x180061060`

## import_xrefs

- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18000f897`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18000f897`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18000f7a3`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18000f7f1`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18000f7a3`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18000f7f1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000f8ef`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000f8ef`
- `iisutil!PuDbgPrint` at `0x18000f8e5`
- `iisutil!PuDbgPrint` at `0x18000f8e5`
- `iisutil!PuDbgPrintError` at `0x18000f77e`
- `iisutil!PuDbgPrintError` at `0x18000f833`
- `iisutil!PuDbgPrintError` at `0x18000f77e`
- `iisutil!PuDbgPrintError` at `0x18000f833`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000f726`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000f726`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000f73a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000f73a`

## string_xrefs

- `0x18000f777`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\ul_and_worker_manager.cxx`
- `0x18000f824`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\ul_and_worker_manager.cxx`
- `0x18000f8af`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\ul_and_worker_manager.cxx`
- `0x18000f75a`: `Failed memory allocation when checking if created application exists\n`
- `0x18000f766`: `UL_AND_WORKER_MANAGER::CreateOrModifyApplication`
- `0x18000f818`: `UL_AND_WORKER_MANAGER::CreateOrModifyApplication`
- `0x18000f8a4`: `UL_AND_WORKER_MANAGER::CreateOrModifyApplication`
- `0x18000f8d9`: `Modify application in site: %lu with path: %S, assigned to app pool: %S, total number now: %lu, config change id %lu\n`

## pseudocode

```c
void __fastcall UL_AND_WORKER_MANAGER::CreateOrModifyApplication(
        UL_AND_WORKER_MANAGER *this,
        struct APPLICATION_DATA_OBJECT *a2)
{
  const unsigned __int16 *v4; // rdx
  WAS_ERROR_LOGGER *v5; // rcx
  int v6; // ebx
  CLKRHashTable *v7; // r14
  int Key; // eax
  __int64 v9; // rdx
  struct APP_POOL *v10; // rsi
  int v11; // ebx
  unsigned int v12; // eax
  struct APP_POOL *v13; // [rsp+50h] [rbp-19h] BYREF
  APPLICATION *v14; // [rsp+58h] [rbp-11h] BYREF
  int v15; // [rsp+60h] [rbp-9h] BYREF
  _BYTE v16[56]; // [rsp+68h] [rbp-1h] BYREF

  STRU::STRU((STRU *)v16);
  v4 = (const unsigned __int16 *)*((_QWORD *)a2 + 10);
  v15 = *((_DWORD *)a2 + 26);
  v6 = STRU::Copy((STRU *)v16, v4);
  if ( v6 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\ul_and_worker_manager.cxx",
        3227,
        "UL_AND_WORKER_MANAGER::CreateOrModifyApplication",
        v6,
        "Failed memory allocation when checking if created application exists\n");
    goto LABEL_13;
  }
  v7 = (UL_AND_WORKER_MANAGER *)((char *)this + 184);
  v14 = 0;
  Key = CLKRHashTable::FindKey((char *)this + 184, &v15, &v14);
  if ( Key == 2 )
  {
    UL_AND_WORKER_MANAGER::CreateApplication(this, a2);
    goto LABEL_16;
  }
  if ( Key )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\ul_and_worker_manager.cxx",
        3260,
        "UL_AND_WORKER_MANAGER::CreateOrModifyApplication",
        -2147467259,
        "Finding application to modify in hashtable failed\n");
LABEL_12:
    v6 = -2147467259;
LABEL_13:
    WAS_ERROR_LOGGER::LogApplicationError(
      v5,
      0xC00013F2,
      v6,
      *((_DWORD *)a2 + 26),
      *((const unsigned __int16 **)a2 + 10));
    goto LABEL_16;
  }
  v9 = *((_QWORD *)a2 + 19);
  v13 = 0;
  if ( (unsigned int)CLKRHashTable::FindKey((char *)this + 16, v9, &v13) )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\ul_and_worker_manager.cxx",
        3284,
        "UL_AND_WORKER_MANAGER::CreateOrModifyApplication",
        -2147467259,
        "Looking up app pool referenced by application failed\n");
    goto LABEL_12;
  }
  v10 = v13;
  APPLICATION::SetConfiguration(v14, a2, v13);
  if ( (g_dwDebugFlags & 0x30000) != 0 && (g_dwDebugFlags & 3) != 0 )
  {
    v11 = *((_DWORD *)g_pWebAdminService + 259);
    v12 = CLKRHashTable::Size(v7);
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\ul_and_worker_manager.cxx",
      3307,
      "UL_AND_WORKER_MANAGER::CreateOrModifyApplication",
      "Modify application in site: %lu with path: %S, assigned to app pool: %S, total number now: %lu, config change id %lu\n",
      *((_DWORD *)a2 + 26),
      *((const wchar_t **)a2 + 10),
      *((const wchar_t **)v10 + 7),
      v12,
      v11);
  }
LABEL_16:
  STRU::~STRU((STRU *)v16);
}

```

## disassembly

```asm
0x18000f6f4  mov     [rsp-8+arg_10], rbx
0x18000f6f9  mov     [rsp-8+arg_18], rsi
0x18000f6fe  push    rbp
0x18000f6ff  push    rdi
0x18000f700  push    r14
0x18000f702  lea     rbp, [rsp-47h]
0x18000f707  sub     rsp, 0B0h
0x18000f70e  mov     rax, cs:__security_cookie
0x18000f715  xor     rax, rsp
0x18000f718  mov     [rbp+57h+var_20], rax
0x18000f71c  mov     rsi, rcx
0x18000f71f  mov     rdi, rdx
0x18000f722  lea     rcx, [rbp+57h+var_58]
0x18000f726  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000f72c  mov     eax, [rdi+68h]
0x18000f72f  lea     rcx, [rbp+57h+var_58]
0x18000f733  mov     rdx, [rdi+50h]
0x18000f737  mov     [rbp+57h+var_60], eax
0x18000f73a  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000f740  mov     ebx, eax
0x18000f742  test    eax, eax
0x18000f744  jns     short loc_18000F789
0x18000f746  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000f74d  jz      loc_18000F83E
0x18000f753  mov     rcx, cs:g_pDebug
0x18000f75a  lea     rax, aFailedMemoryAl_0; "Failed memory allocation when checking "...
0x18000f761  mov     [rsp+0C0h+var_98], rax
0x18000f766  lea     r9, aUlAndWorkerMan_0; "UL_AND_WORKER_MANAGER::CreateOrModifyAp"...
0x18000f76d  mov     r8d, 0C9Bh
0x18000f773  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x18000f777  lea     rdx, aServercommonIn_68; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000f77e  call    cs:__imp_PuDbgPrintError
0x18000f784  jmp     loc_18000F83E
0x18000f789  lea     r14, [rsi+0B8h]
0x18000f790  mov     [rbp+57h+var_68], 0
0x18000f798  mov     rcx, r14
0x18000f79b  lea     r8, [rbp+57h+var_68]
0x18000f79f  lea     rdx, [rbp+57h+var_60]
0x18000f7a3  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x18000f7a9  cmp     eax, 2
0x18000f7ac  jnz     short loc_18000F7BE
0x18000f7ae  mov     rdx, rdi; struct APPLICATION_DATA_OBJECT *
0x18000f7b1  mov     rcx, rsi; this
0x18000f7b4  call    ?CreateApplication@UL_AND_WORKER_MANAGER@@QEAAXPEAVAPPLICATION_DATA_OBJECT@@@Z; UL_AND_WORKER_MANAGER::CreateApplication(APPLICATION_DATA_OBJECT *)
0x18000f7b9  jmp     loc_18000F8EB
0x18000f7be  test    eax, eax
0x18000f7c0  jz      short loc_18000F7DA
0x18000f7c2  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000f7c9  jz      short loc_18000F839
0x18000f7cb  lea     rax, aFindingApplica_0; "Finding application to modify in hashta"...
0x18000f7d2  mov     r8d, 0CBCh
0x18000f7d8  jmp     short loc_18000F811
0x18000f7da  mov     rdx, [rdi+98h]
0x18000f7e1  lea     rcx, [rsi+10h]
0x18000f7e5  lea     r8, [rbp+57h+var_70]
0x18000f7e9  mov     [rbp+57h+var_70], 0
0x18000f7f1  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x18000f7f7  test    eax, eax
0x18000f7f9  jz      short loc_18000F85D
0x18000f7fb  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000f802  jz      short loc_18000F839
0x18000f804  lea     rax, aLookingUpAppPo_0; "Looking up app pool referenced by appli"...
0x18000f80b  mov     r8d, 0CD4h
0x18000f811  mov     rcx, cs:g_pDebug
0x18000f818  lea     r9, aUlAndWorkerMan_0; "UL_AND_WORKER_MANAGER::CreateOrModifyAp"...
0x18000f81f  mov     [rsp+0C0h+var_98], rax
0x18000f824  lea     rdx, aServercommonIn_68; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000f82b  mov     dword ptr [rsp+0C0h+var_A0], 80004005h
0x18000f833  call    cs:__imp_PuDbgPrintError
0x18000f839  mov     ebx, 80004005h
0x18000f83e  mov     rax, [rdi+50h]
0x18000f842  mov     r8d, ebx; int
0x18000f845  mov     r9d, [rdi+68h]; unsigned int
0x18000f849  mov     edx, 0C00013F2h; unsigned int
0x18000f84e  mov     [rsp+0C0h+var_A0], rax; unsigned __int16 *
0x18000f853  call    ?LogApplicationError@WAS_ERROR_LOGGER@@QEAAXKJKPEBG@Z; WAS_ERROR_LOGGER::LogApplicationError(ulong,long,ulong,ushort const *)
0x18000f858  jmp     loc_18000F8EB
0x18000f85d  mov     rsi, [rbp+57h+var_70]
0x18000f861  mov     rdx, rdi; struct APPLICATION_DATA_OBJECT *
0x18000f864  mov     rcx, [rbp+57h+var_68]; this
0x18000f868  mov     r8, rsi; struct APP_POOL *
0x18000f86b  call    ?SetConfiguration@APPLICATION@@QEAAXPEAVAPPLICATION_DATA_OBJECT@@PEAVAPP_POOL@@@Z; APPLICATION::SetConfiguration(APPLICATION_DATA_OBJECT *,APP_POOL *)
0x18000f870  mov     eax, cs:g_dwDebugFlags
0x18000f876  test    eax, 30000h
0x18000f87b  setnz   dl
0x18000f87e  test    al, 3
0x18000f880  setnz   al
0x18000f883  test    al, dl
0x18000f885  jz      short loc_18000F8EB
0x18000f887  mov     rax, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x18000f88e  mov     rcx, r14
0x18000f891  mov     ebx, [rax+40Ch]
0x18000f897  call    cs:__imp_?Size@CLKRHashTable@@QEBAKXZ; CLKRHashTable::Size(void)
0x18000f89d  mov     rcx, cs:g_pDebug
0x18000f8a4  lea     r9, aUlAndWorkerMan_0; "UL_AND_WORKER_MANAGER::CreateOrModifyAp"...
0x18000f8ab  mov     [rsp+0C0h+var_78], ebx
0x18000f8af  lea     rdx, aServercommonIn_68; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000f8b6  mov     [rsp+0C0h+var_80], eax
0x18000f8ba  mov     r8d, 0CEBh
0x18000f8c0  mov     rax, [rsi+38h]
0x18000f8c4  mov     [rsp+0C0h+var_88], rax
0x18000f8c9  mov     rax, [rdi+50h]
0x18000f8cd  mov     [rsp+0C0h+var_90], rax
0x18000f8d2  mov     eax, [rdi+68h]
0x18000f8d5  mov     dword ptr [rsp+0C0h+var_98], eax
0x18000f8d9  lea     rax, aModifyApplicat; "Modify application in site: %lu with pa"...
0x18000f8e0  mov     [rsp+0C0h+var_A0], rax
0x18000f8e5  call    cs:__imp_PuDbgPrint
0x18000f8eb  lea     rcx, [rbp+57h+var_58]
0x18000f8ef  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000f8f5  mov     rcx, [rbp+57h+var_20]
0x18000f8f9  xor     rcx, rsp; StackCookie
0x18000f8fc  call    __security_check_cookie
0x18000f901  lea     r11, [rsp+0C0h+var_10]
0x18000f909  mov     rbx, [r11+30h]
0x18000f90d  mov     rsi, [r11+38h]
0x18000f911  mov     rsp, r11
0x18000f914  pop     r14
0x18000f916  pop     rdi
0x18000f917  pop     rbp
0x18000f918  retn
```
