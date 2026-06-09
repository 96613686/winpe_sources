# CONFIG_MANAGER::ProcessConfigChangeOnConfigThread(CONFIG_CHANGES *)

- ea: `0x18002fad4`
- end: `0x1800300ac`
- name: `?ProcessConfigChangeOnConfigThread@CONFIG_MANAGER@@QEAAXPEAUCONFIG_CHANGES@@@Z`
- size: `1496`
- prototype: `void __fastcall(CONFIG_MANAGER *__hidden this, struct CONFIG_CHANGES *)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18003c5e0`
- `0x18003c8c0`

## callees

- `0x180001274`
- `0x180002bbc`
- `0x180005878`
- `0x1800073fc`
- `0x1800074b0`
- `0x1800077e8`
- `0x180007b60`
- `0x180007d98`
- `0x18000d8a4`
- `0x18002d130`
- `0x18002e114`
- `0x18002e1c0`
- `0x18002fad4`
- `0x180042058`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003008b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003008b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003005a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003007d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003005a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003007d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002fbde`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002fc45`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002fbde`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002fc45`
- `iisutil!PuDbgPrint` at `0x18002ff0a`
- `iisutil!PuDbgPrint` at `0x18002ff70`
- `iisutil!PuDbgPrint` at `0x18002ff0a`
- `iisutil!PuDbgPrint` at `0x18002ff70`
- `iisutil!PuDbgPrintError` at `0x18002fda7`
- `iisutil!PuDbgPrintError` at `0x18002fda7`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x18002fb5a`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x18002fb77`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x18002fb5a`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x18002fb77`

## string_xrefs

- `0x18002fd9c`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\config_manager.cxx`
- `0x18002ff03`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\config_manager.cxx`
- `0x18002ff69`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\config_manager.cxx`
- `0x18002fd7c`: `Failed to reread all data\n`
- `0x18002fd90`: `CONFIG_MANAGER::ProcessConfigChangeOnConfigThread`
- `0x18002fef1`: `CONFIG_MANAGER::ProcessConfigChangeOnConfigThread`
- `0x18002ff57`: `CONFIG_MANAGER::ProcessConfigChangeOnConfigThread`
- `0x18002fe79`: `Failed to finish processing the config change\n`
- `0x18002fee6`: `Bad config read, invalidating all app pool config (hr: %d)\n`
- `0x18002ff50`: `Good config read, all app pools should have reset\n`

## pseudocode

```c
void __fastcall CONFIG_MANAGER::ProcessConfigChangeOnConfigThread(CONFIG_MANAGER *this, struct CONFIG_CHANGES *a2)
{
  struct APP_POOL_CHANGED_LIST *v4; // rsi
  int v5; // r12d
  const unsigned __int16 *v6; // rbx
  const unsigned __int16 *v7; // rdx
  _QWORD *v8; // rax
  unsigned int v9; // r15d
  signed int BlankWorkItem; // ebx
  DWORD v11; // ecx
  DWORD v12; // ecx
  struct WORK_DISPATCH *v13; // r15
  PROTOCOL_BINDING_TABLE *v14; // r12
  struct WORK_ITEM *v15; // rbx
  struct WORK_ITEM *v16; // rcx
  LPCWSTR *v17; // rbx
  struct INativeConfigurationSystem *v18; // rax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  bool v22; // zf
  int v23; // eax
  __int64 v24; // rdi
  struct APPLICATION_DATA_OBJECT_TABLE *v25; // [rsp+30h] [rbp-50h]
  struct PROTOCOL_DATA_OBJECT_TABLE *v26; // [rsp+50h] [rbp-30h] BYREF
  PROTOCOL_BINDING_TABLE *v27; // [rsp+58h] [rbp-28h] BYREF
  struct GLOBAL_DATA_STORE *v28; // [rsp+60h] [rbp-20h] BYREF
  struct APP_POOL_CHANGED_LIST *v29; // [rsp+68h] [rbp-18h] BYREF
  struct WORK_ITEM *v30; // [rsp+70h] [rbp-10h] BYREF
  struct SITE_DATA_OBJECT_TABLE *v31; // [rsp+C0h] [rbp+40h] BYREF
  struct APP_POOL_DATA_OBJECT_TABLE *v32; // [rsp+D0h] [rbp+50h] BYREF
  struct APPLICATION_DATA_OBJECT_TABLE *v33; // [rsp+D8h] [rbp+58h] BYREF

  v32 = 0;
  v4 = 0;
  v31 = 0;
  v33 = 0;
  v28 = 0;
  v26 = 0;
  v29 = 0;
  v27 = 0;
  if ( *((_DWORD *)this + 78) && !*((_DWORD *)this + 79) )
  {
    v5 = 0;
    if ( (*((_BYTE *)this + 248) & 0x20) != 0 )
    {
      v6 = &SourceString;
      v7 = &SourceString;
      if ( *((_QWORD *)a2 + 3) )
        v7 = (const unsigned __int16 *)*((_QWORD *)a2 + 3);
      if ( IsStringEqualOrdinalIgnoreCase(L"system.applicationHost/sites", v7) )
        goto LABEL_10;
      if ( *((_QWORD *)a2 + 3) )
        v6 = (const unsigned __int16 *)*((_QWORD *)a2 + 3);
      if ( IsStringEqualOrdinalIgnoreCase(L"system.applicationHost/applicationPools", v6) )
LABEL_10:
        v5 = 1;
    }
    if ( *(_DWORD *)a2 == 1 && (v8 = (_QWORD *)*((_QWORD *)a2 + 1), *v8) && !*(_WORD *)*v8 && v8[1] == 1
      || *((_DWORD *)a2 + 4) == 1 )
    {
      v9 = 0;
      while ( 1 )
      {
        if ( *((_DWORD *)g_pWebAdminService + 412)
          || (BlankWorkItem = CONFIG_CS::ResetConfigSystem(*((CONFIG_CS **)this + 2)), BlankWorkItem >= 0) )
        {
          v25 = (struct APPLICATION_DATA_OBJECT_TABLE *)((unsigned __int64)&v27 & -(__int64)(v5 != 0));
          BlankWorkItem = (*(__int64 (__fastcall **)(_QWORD, struct APP_POOL_DATA_OBJECT_TABLE **, struct SITE_DATA_OBJECT_TABLE **, struct APPLICATION_DATA_OBJECT_TABLE **, struct GLOBAL_DATA_STORE **))(**((_QWORD **)this + 2) + 72LL))(
                            *((_QWORD *)this + 2),
                            &v32,
                            &v31,
                            &v33,
                            &v28);
          if ( BlankWorkItem >= 0 )
          {
            if ( *((_DWORD *)this + 85) == 1 )
            {
              WEB_ADMIN_SERVICE::LogEvent(g_pWebAdminService, 0x40001455u, 0, 0, 0);
              _InterlockedExchange((volatile __int32 *)this + 85, 0);
            }
LABEL_31:
            ++*((_DWORD *)this + 82);
            if ( (*((_BYTE *)this + 248) & 0x20) == 0 )
              goto LABEL_77;
            if ( !v27 )
              goto LABEL_77;
            _InterlockedAdd((volatile signed __int32 *)v27 + 266, 1u);
            v13 = g_pWebAdminService;
            v14 = v27;
            v30 = 0;
            BlankWorkItem = WORK_QUEUE::GetBlankWorkItem((WEB_ADMIN_SERVICE *)((char *)g_pWebAdminService + 16), &v30);
            if ( BlankWorkItem >= 0 )
            {
              v15 = v30;
              v16 = v30;
              *((_QWORD *)v30 + 11) = v14;
              *((_QWORD *)v16 + 3) = 13;
              WORK_ITEM::SetWorkDispatchPointer(v16, v13);
              BlankWorkItem = WORK_QUEUE::QueueWorkItem((WEB_ADMIN_SERVICE *)((char *)g_pWebAdminService + 16), v15);
              if ( BlankWorkItem >= 0 )
              {
LABEL_77:
                if ( *((_DWORD *)g_pWebAdminService + 457) != 1
                  || (v17 = (LPCWSTR *)*((_QWORD *)g_pWebAdminService + 229),
                      v18 = (struct INativeConfigurationSystem *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 136LL))(*((_QWORD *)this + 2)),
                      v19 = APP_POOL_ISOLATION::SetNewConfig(
                              v17,
                              *((_DWORD *)this + 82),
                              a2,
                              *((struct SITE_DATA_OBJECT_TABLE **)this + 4),
                              v31,
                              (struct APPLICATION_DATA_OBJECT_TABLE *)&v26,
                              v25,
                              v18,
                              &v29),
                      v4 = v29,
                      BlankWorkItem = v19,
                      v19 >= 0) )
                {
                  CONFIG_MANAGER::CalculcateDeletesFromTables(this, v32, v31, v33, v26);
                  BlankWorkItem = CONFIG_MANAGER::FinishChangeProcessingOnConfigThread(
                                    this,
                                    v32,
                                    v31,
                                    v33,
                                    v28,
                                    v26,
                                    v4,
                                    *((_DWORD *)this + 84));
                  if ( BlankWorkItem >= 0 )
                  {
                    v4 = 0;
                  }
                  else if ( (g_dwDebugFlags & 0xF) != 0 )
                  {
                    PuDbgPrintError(
                      g_pDebug,
                      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_manager.cxx",
                      807,
                      "CONFIG_MANAGER::ProcessConfigChangeOnConfigThread",
                      BlankWorkItem,
                      "Failed to finish processing the config change\n");
                  }
                }
              }
            }
            goto LABEL_45;
          }
          v12 = 1000;
          if ( v9 >= 0x3C )
            v12 = 5000;
          Sleep(v12);
          ++v9;
        }
        else
        {
          if ( v9 >= 0x3C )
            v11 = 5000;
          else
            v11 = 1000;
          Sleep(v11);
        }
        if ( (unsigned int)CheckWASIsStopping() )
          goto LABEL_45;
      }
    }
    v25 = (struct APPLICATION_DATA_OBJECT_TABLE *)((unsigned __int64)&v27 & -(__int64)(v5 != 0));
    BlankWorkItem = (*(__int64 (__fastcall **)(_QWORD, struct APP_POOL_DATA_OBJECT_TABLE **, struct SITE_DATA_OBJECT_TABLE **, struct APPLICATION_DATA_OBJECT_TABLE **, struct GLOBAL_DATA_STORE **))(**((_QWORD **)this + 2) + 72LL))(
                      *((_QWORD *)this + 2),
                      &v32,
                      &v31,
                      &v33,
                      &v28);
    if ( BlankWorkItem >= 0 )
      goto LABEL_31;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_manager.cxx",
        738,
        "CONFIG_MANAGER::ProcessConfigChangeOnConfigThread",
        BlankWorkItem,
        "Failed to reread all data\n");
LABEL_45:
    if ( *((_DWORD *)g_pWebAdminService + 457) == 1 && !(unsigned int)CheckWASIsStopping() )
    {
      v20 = *((_DWORD *)this + 84);
      if ( BlankWorkItem >= 0 )
      {
        if ( !v20 )
        {
          v23 = g_dwDebugFlags;
          v22 = (g_dwDebugFlags & 3) == 0;
          *((_DWORD *)this + 84) = 1;
          if ( !v22 && v23 < 0 )
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_manager.cxx",
              849,
              "CONFIG_MANAGER::ProcessConfigChangeOnConfigThread",
              "Good config read, all app pools should have reset\n");
        }
      }
      else if ( v20 == 1 )
      {
        v21 = g_dwDebugFlags;
        v22 = (g_dwDebugFlags & 3) == 0;
        *((_DWORD *)this + 84) = 0;
        if ( !v22 && v21 < 0 )
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_manager.cxx",
            831,
            "CONFIG_MANAGER::ProcessConfigChangeOnConfigThread",
            "Bad config read, invalidating all app pool config (hr: %d)\n",
            BlankWorkItem);
        WORK_QUEUE::GetAndQueueWorkItem((WEB_ADMIN_SERVICE *)((char *)g_pWebAdminService + 16), g_pWebAdminService, 9u);
      }
    }
    if ( v32 )
    {
      (**(void (__fastcall ***)(struct APP_POOL_DATA_OBJECT_TABLE *, __int64))v32)(v32, 1);
      v32 = 0;
    }
    if ( v31 )
    {
      (**(void (__fastcall ***)(struct SITE_DATA_OBJECT_TABLE *, __int64))v31)(v31, 1);
      v31 = 0;
    }
    if ( v33 )
    {
      (**(void (__fastcall ***)(struct APPLICATION_DATA_OBJECT_TABLE *, __int64))v33)(v33, 1);
      v33 = 0;
    }
    if ( v28 )
    {
      (**(void (__fastcall ***)(struct GLOBAL_DATA_STORE *, __int64))v28)(v28, 1);
      v28 = 0;
    }
    if ( v26 )
    {
      (**(void (__fastcall ***)(struct PROTOCOL_DATA_OBJECT_TABLE *, __int64))v26)(v26, 1);
      v26 = 0;
    }
    if ( v27 )
    {
      PROTOCOL_BINDING_TABLE::Dereference(v27);
      v27 = 0;
    }
    if ( v4 )
    {
      ARRAY_LIST::~ARRAY_LIST(v4);
      operator delete(v4);
    }
    if ( BlankWorkItem >= 0 )
    {
      v24 = *((_QWORD *)g_pWebAdminService + 231);
      if ( !v24 )
        return;
      EnterCriticalSection((LPCRITICAL_SECTION)(v24 + 80));
      ++*(_DWORD *)(v24 + 72);
    }
    else
    {
      WEB_ADMIN_SERVICE::LogEvent(g_pWebAdminService, 0xC00013BD, 0, 0, BlankWorkItem);
      v24 = *((_QWORD *)g_pWebAdminService + 231);
      if ( !v24 )
        return;
      EnterCriticalSection((LPCRITICAL_SECTION)(v24 + 80));
      ++*(_DWORD *)(v24 + 68);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v24 + 80));
  }
}

```

## disassembly

```asm
0x18002fad4  mov     [rsp-38h+arg_8], rbx
0x18002fad9  push    rbp
0x18002fada  push    rsi
0x18002fadb  push    rdi
0x18002fadc  push    r12
0x18002fade  push    r13
0x18002fae0  push    r14
0x18002fae2  push    r15
0x18002fae4  mov     rbp, rsp
0x18002fae7  sub     rsp, 80h
0x18002faee  xor     r13d, r13d
0x18002faf1  mov     r14, rdx
0x18002faf4  mov     rdi, rcx
0x18002faf7  mov     [rbp+arg_10], r13
0x18002fafb  mov     esi, r13d
0x18002fafe  mov     [rbp+arg_0], r13
0x18002fb02  mov     [rbp+arg_18], r13
0x18002fb06  mov     [rbp+var_20], r13
0x18002fb0a  mov     [rbp+var_30], r13
0x18002fb0e  mov     [rbp+var_18], r13
0x18002fb12  mov     [rbp+var_28], r13
0x18002fb16  cmp     [rcx+138h], r13d
0x18002fb1d  jz      loc_180030091
0x18002fb23  cmp     [rcx+13Ch], r13d
0x18002fb2a  jnz     loc_180030091
0x18002fb30  test    byte ptr [rcx+0F8h], 20h
0x18002fb37  lea     r15d, [r13+1]
0x18002fb3b  mov     r12d, r13d
0x18002fb3e  jz      short loc_18002FB84
0x18002fb40  cmp     [r14+18h], r13
0x18002fb44  lea     rbx, SourceString
0x18002fb4b  mov     rdx, rbx
0x18002fb4e  lea     rcx, aSystemApplicat_5; "system.applicationHost/sites"
0x18002fb55  cmovnz  rdx, [r14+18h]
0x18002fb5a  call    cs:__imp_?IsStringEqualOrdinalIgnoreCase@@YA_NPEBG0@Z; IsStringEqualOrdinalIgnoreCase(ushort const *,ushort const *)
0x18002fb60  test    al, al
0x18002fb62  jnz     short loc_18002FB81
0x18002fb64  cmp     [r14+18h], r13
0x18002fb68  lea     rcx, aSystemApplicat_7; "system.applicationHost/applicationPools"
0x18002fb6f  cmovnz  rbx, [r14+18h]
0x18002fb74  mov     rdx, rbx
0x18002fb77  call    cs:__imp_?IsStringEqualOrdinalIgnoreCase@@YA_NPEBG0@Z; IsStringEqualOrdinalIgnoreCase(ushort const *,ushort const *)
0x18002fb7d  test    al, al
0x18002fb7f  jz      short loc_18002FB84
0x18002fb81  mov     r12d, r15d
0x18002fb84  cmp     [r14], r15d
0x18002fb87  jnz     short loc_18002FBA7
0x18002fb89  mov     rax, [r14+8]
0x18002fb8d  mov     rcx, [rax]
0x18002fb90  test    rcx, rcx
0x18002fb93  jz      short loc_18002FBA7
0x18002fb95  cmp     [rcx], r13w
0x18002fb99  jnz     short loc_18002FBA7
0x18002fb9b  cmp     [rax+8], r15d
0x18002fb9f  jnz     short loc_18002FBA7
0x18002fba1  cmp     [rax+0Ch], r13d
0x18002fba5  jz      short loc_18002FBB1
0x18002fba7  cmp     [r14+10h], r15d
0x18002fbab  jnz     loc_18002FD25
0x18002fbb1  mov     r15d, r13d
0x18002fbb4  mov     rax, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x18002fbbb  cmp     [rax+670h], r13d
0x18002fbc2  jnz     short loc_18002FBED
0x18002fbc4  mov     rcx, [rdi+10h]; this
0x18002fbc8  call    ?ResetConfigSystem@CONFIG_CS@@QEAAJXZ; CONFIG_CS::ResetConfigSystem(void)
0x18002fbcd  mov     ebx, eax
0x18002fbcf  test    eax, eax
0x18002fbd1  jns     short loc_18002FBED
0x18002fbd3  cmp     r15d, 3Ch ; '<'
0x18002fbd7  jnb     short loc_18002FBE6
0x18002fbd9  mov     ecx, 3E8h; dwMilliseconds
0x18002fbde  call    cs:__imp_Sleep
0x18002fbe4  jmp     short loc_18002FC4E
0x18002fbe6  mov     ecx, 1388h
0x18002fbeb  jmp     short loc_18002FBDE
0x18002fbed  mov     rcx, [rdi+10h]
0x18002fbf1  lea     r9, [rbp+arg_18]
0x18002fbf5  mov     eax, r12d
0x18002fbf8  neg     eax
0x18002fbfa  lea     rax, [rbp+var_28]
0x18002fbfe  mov     r8, [rcx]
0x18002fc01  sbb     rdx, rdx
0x18002fc04  and     rdx, rax
0x18002fc07  mov     [rsp+80h+var_50], rdx; struct APPLICATION_DATA_OBJECT_TABLE *
0x18002fc0c  lea     rdx, [rbp+var_30]
0x18002fc10  mov     [rsp+80h+var_58], rdx; struct APPLICATION_DATA_OBJECT_TABLE *
0x18002fc15  lea     rdx, [rbp+var_20]
0x18002fc19  mov     rax, [r8+48h]
0x18002fc1d  lea     r8, [rbp+arg_0]
0x18002fc21  mov     [rsp+80h+var_60], rdx
0x18002fc26  lea     rdx, [rbp+arg_10]
0x18002fc2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fc2f  mov     ebx, eax
0x18002fc31  test    eax, eax
0x18002fc33  jns     short loc_18002FC63
0x18002fc35  mov     ecx, 3E8h
0x18002fc3a  cmp     r15d, 3Ch ; '<'
0x18002fc3e  jb      short loc_18002FC45
0x18002fc40  mov     ecx, 1388h; dwMilliseconds
0x18002fc45  call    cs:__imp_Sleep
0x18002fc4b  inc     r15d
0x18002fc4e  call    ?CheckWASIsStopping@@YAHXZ; CheckWASIsStopping(void)
0x18002fc53  test    eax, eax
0x18002fc55  jz      loc_18002FBB4
0x18002fc5b  test    ebx, ebx
0x18002fc5d  js      loc_18002FD1A
0x18002fc63  mov     r15d, 1
0x18002fc69  cmp     [rdi+154h], r15d
0x18002fc70  jnz     short loc_18002FC97
0x18002fc72  mov     rcx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; this
0x18002fc79  xor     r8d, r8d; unsigned __int16
0x18002fc7c  xor     r9d, r9d; unsigned __int16 **
0x18002fc7f  mov     dword ptr [rsp+80h+var_60], r13d; unsigned int
0x18002fc84  mov     edx, 40001455h; unsigned int
0x18002fc89  call    ?LogEvent@WEB_ADMIN_SERVICE@@QEAAXKGQEAPEBGK@Z; WEB_ADMIN_SERVICE::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x18002fc8e  mov     eax, r13d
0x18002fc91  xchg    eax, [rdi+154h]
0x18002fc97  add     [rdi+148h], r15d
0x18002fc9e  test    byte ptr [rdi+0F8h], 20h
0x18002fca5  jz      loc_18002FDB8
0x18002fcab  mov     rax, [rbp+var_28]
0x18002fcaf  test    rax, rax
0x18002fcb2  jz      loc_18002FDB8
0x18002fcb8  lock add [rax+428h], r15d
0x18002fcc0  mov     r15, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x18002fcc7  lea     rdx, [rbp+var_10]; struct WORK_ITEM **
0x18002fccb  mov     r12, [rbp+var_28]
0x18002fccf  mov     [rbp+var_10], r13
0x18002fcd3  lea     rcx, [r15+10h]; this
0x18002fcd7  call    ?GetBlankWorkItem@WORK_QUEUE@@QEAAJPEAPEAVWORK_ITEM@@@Z; WORK_QUEUE::GetBlankWorkItem(WORK_ITEM * *)
0x18002fcdc  mov     ebx, eax
0x18002fcde  test    eax, eax
0x18002fce0  js      short loc_18002FD1A
0x18002fce2  mov     rbx, [rbp+var_10]
0x18002fce6  mov     rdx, r15; struct WORK_DISPATCH *
0x18002fce9  mov     rcx, rbx; this
0x18002fcec  mov     [rbx+58h], r12
0x18002fcf0  mov     qword ptr [rbx+18h], 0Dh
0x18002fcf8  call    ?SetWorkDispatchPointer@WORK_ITEM@@QEAAXPEAVWORK_DISPATCH@@@Z; WORK_ITEM::SetWorkDispatchPointer(WORK_DISPATCH *)
0x18002fcfd  mov     rcx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x18002fd04  mov     rdx, rbx; struct WORK_ITEM *
0x18002fd07  add     rcx, 10h; this
0x18002fd0b  call    ?QueueWorkItem@WORK_QUEUE@@QEAAJPEAVWORK_ITEM@@@Z; WORK_QUEUE::QueueWorkItem(WORK_ITEM *)
0x18002fd10  mov     ebx, eax
0x18002fd12  test    eax, eax
0x18002fd14  jns     loc_18002FDB2
0x18002fd1a  mov     r15d, 1
0x18002fd20  jmp     loc_18002FE8E
0x18002fd25  mov     rcx, [rdi+10h]
0x18002fd29  lea     r8, [rbp+var_28]
0x18002fd2d  neg     r12d
0x18002fd30  lea     r9, [rbp+arg_18]
0x18002fd34  sbb     rdx, rdx
0x18002fd37  mov     rax, [rcx]
0x18002fd3a  and     rdx, r8
0x18002fd3d  mov     [rsp+80h+var_50], rdx
0x18002fd42  lea     r8, [rbp+arg_0]
0x18002fd46  lea     rdx, [rbp+var_30]
0x18002fd4a  mov     [rsp+80h+var_58], rdx
0x18002fd4f  lea     rdx, [rbp+var_20]
0x18002fd53  mov     rax, [rax+48h]
0x18002fd57  mov     [rsp+80h+var_60], rdx
0x18002fd5c  lea     rdx, [rbp+arg_10]
0x18002fd60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fd65  mov     ebx, eax
0x18002fd67  test    eax, eax
0x18002fd69  jns     loc_18002FC97
0x18002fd6f  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002fd76  jz      loc_18002FE8E
0x18002fd7c  lea     rax, aFailedToReread; "Failed to reread all data\n"
0x18002fd83  mov     r8d, 2E2h
0x18002fd89  mov     rcx, cs:g_pDebug
0x18002fd90  lea     r9, aConfigManagerP_1; "CONFIG_MANAGER::ProcessConfigChangeOnCo"...
0x18002fd97  mov     [rsp+80h+var_58], rax
0x18002fd9c  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002fda3  mov     dword ptr [rsp+80h+var_60], ebx
0x18002fda7  call    cs:__imp_PuDbgPrintError
0x18002fdad  jmp     loc_18002FE8E
0x18002fdb2  mov     r15d, 1
0x18002fdb8  mov     rbx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x18002fdbf  cmp     [rbx+724h], r15d
0x18002fdc6  jnz     short loc_18002FE18
0x18002fdc8  mov     rcx, [rdi+10h]
0x18002fdcc  mov     rbx, [rbx+728h]
0x18002fdd3  mov     rax, [rcx]
0x18002fdd6  mov     rax, [rax+88h]
0x18002fddd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fde2  mov     rdx, [rbp+arg_0]
0x18002fde6  lea     rcx, [rbp+var_18]
0x18002fdea  mov     r9, [rdi+20h]; struct SITE_DATA_OBJECT_TABLE *
0x18002fdee  mov     r8, r14; struct CONFIG_CHANGES *
0x18002fdf1  mov     [rsp+80h+var_40], rcx; struct APP_POOL_CHANGED_LIST **
0x18002fdf6  mov     rcx, rbx; this
0x18002fdf9  mov     [rsp+80h+var_48], rax; struct INativeConfigurationSystem *
0x18002fdfe  mov     [rsp+80h+var_60], rdx; struct SITE_DATA_OBJECT_TABLE *
0x18002fe03  mov     edx, [rdi+148h]; unsigned int
0x18002fe09  call    ?SetNewConfig@APP_POOL_ISOLATION@@QEAAJKPEAUCONFIG_CHANGES@@PEAVSITE_DATA_OBJECT_TABLE@@1PEAVAPPLICATION_DATA_OBJECT_TABLE@@2PEAVINativeConfigurationSystem@@PEAPEAVAPP_POOL_CHANGED_LIST@@@Z; APP_POOL_ISOLATION::SetNewConfig(ulong,CONFIG_CHANGES *,SITE_DATA_OBJECT_TABLE *,SITE_DATA_OBJECT_TABLE *,APPLICATION_DATA_OBJECT_TABLE *,APPLICATION_DATA_OBJECT_TABLE *,INativeConfigurationSystem *,APP_POOL_CHANGED_LIST * *)
0x18002fe0e  mov     rsi, [rbp+var_18]
0x18002fe12  mov     ebx, eax
0x18002fe14  test    eax, eax
0x18002fe16  js      short loc_18002FE8E
0x18002fe18  mov     rax, [rbp+var_30]
0x18002fe1c  mov     rcx, rdi; this
0x18002fe1f  mov     r9, [rbp+arg_18]; struct APPLICATION_DATA_OBJECT_TABLE *
0x18002fe23  mov     r8, [rbp+arg_0]; struct SITE_DATA_OBJECT_TABLE *
0x18002fe27  mov     rdx, [rbp+arg_10]; struct APP_POOL_DATA_OBJECT_TABLE *
0x18002fe2b  mov     [rsp+80h+var_60], rax; struct PROTOCOL_DATA_OBJECT_TABLE *
0x18002fe30  call    ?CalculcateDeletesFromTables@CONFIG_MANAGER@@AEAAXPEAVAPP_POOL_DATA_OBJECT_TABLE@@PEAVSITE_DATA_OBJECT_TABLE@@PEAVAPPLICATION_DATA_OBJECT_TABLE@@PEAVPROTOCOL_DATA_OBJECT_TABLE@@@Z; CONFIG_MANAGER::CalculcateDeletesFromTables(APP_POOL_DATA_OBJECT_TABLE *,SITE_DATA_OBJECT_TABLE *,APPLICATION_DATA_OBJECT_TABLE *,PROTOCOL_DATA_OBJECT_TABLE *)
0x18002fe35  mov     eax, [rdi+150h]
0x18002fe3b  mov     rcx, rdi; this
0x18002fe3e  mov     r9, [rbp+arg_18]; struct APPLICATION_DATA_OBJECT_TABLE *
0x18002fe42  mov     r8, [rbp+arg_0]; struct SITE_DATA_OBJECT_TABLE *
0x18002fe46  mov     rdx, [rbp+arg_10]; struct APP_POOL_DATA_OBJECT_TABLE *
0x18002fe4a  mov     dword ptr [rsp+80h+var_48], eax; int
0x18002fe4e  mov     rax, [rbp+var_30]
0x18002fe52  mov     [rsp+80h+var_50], rsi; struct APP_POOL_CHANGED_LIST *
0x18002fe57  mov     [rsp+80h+var_58], rax; struct PROTOCOL_DATA_OBJECT_TABLE *
0x18002fe5c  mov     rax, [rbp+var_20]
0x18002fe60  mov     [rsp+80h+var_60], rax; struct GLOBAL_DATA_STORE *
0x18002fe65  call    ?FinishChangeProcessingOnConfigThread@CONFIG_MANAGER@@AEAAJPEAVAPP_POOL_DATA_OBJECT_TABLE@@PEAVSITE_DATA_OBJECT_TABLE@@PEAVAPPLICATION_DATA_OBJECT_TABLE@@PEAVGLOBAL_DATA_STORE@@PEAVPROTOCOL_DATA_OBJECT_TABLE@@PEAVAPP_POOL_CHANGED_LIST@@H@Z; CONFIG_MANAGER::FinishChangeProcessingOnConfigThread(APP_POOL_DATA_OBJECT_TABLE *,SITE_DATA_OBJECT_TABLE *,APPLICATION_DATA_OBJECT_TABLE *,GLOBAL_DATA_STORE *,PROTOCOL_DATA_OBJECT_TABLE *,APP_POOL_CHANGED_LIST *,int)
0x18002fe6a  mov     ebx, eax
0x18002fe6c  test    eax, eax
0x18002fe6e  jns     short loc_18002FE8B
0x18002fe70  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002fe77  jz      short loc_18002FE8E
0x18002fe79  lea     rax, aFailedToFinish; "Failed to finish processing the config "...
0x18002fe80  mov     r8d, 327h
0x18002fe86  jmp     loc_18002FD89
0x18002fe8b  mov     rsi, r13
0x18002fe8e  mov     rax, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x18002fe95  cmp     [rax+724h], r15d
0x18002fe9c  jnz     loc_18002FF76
0x18002fea2  call    ?CheckWASIsStopping@@YAHXZ; CheckWASIsStopping(void)
0x18002fea7  test    eax, eax
0x18002fea9  jnz     loc_18002FF76
0x18002feaf  mov     eax, [rdi+150h]
0x18002feb5  test    ebx, ebx
0x18002feb7  jns     short loc_18002FF28
0x18002feb9  cmp     eax, r15d
0x18002febc  jnz     loc_18002FF76
0x18002fec2  mov     eax, cs:g_dwDebugFlags
0x18002fec8  test    al, 3
0x18002feca  mov     [rdi+150h], r13d
0x18002fed1  setnz   cl
0x18002fed4  bt      eax, 1Fh
0x18002fed8  setb    al
0x18002fedb  test    al, cl
0x18002fedd  jz      short loc_18002FF10
0x18002fedf  mov     rcx, cs:g_pDebug
0x18002fee6  lea     rax, aBadConfigReadI; "Bad config read, invalidating all app p"...
0x18002feed  mov     dword ptr [rsp+80h+var_58], ebx
0x18002fef1  lea     r9, aConfigManagerP_1; "CONFIG_MANAGER::ProcessConfigChangeOnCo"...
0x18002fef8  mov     r8d, 33Fh
0x18002fefe  mov     [rsp+80h+var_60], rax
0x18002ff03  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002ff0a  call    cs:__imp_PuDbgPrint
0x18002ff10  mov     rdx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; struct WORK_DISPATCH *
0x18002ff17  mov     r8d, 9; unsigned __int64
0x18002ff1d  lea     rcx, [rdx+10h]; this
0x18002ff21  call    ?GetAndQueueWorkItem@WORK_QUEUE@@QEAAJPEAVWORK_DISPATCH@@_K@Z; WORK_QUEUE::GetAndQueueWorkItem(WORK_DISPATCH *,unsigned __int64)
0x18002ff26  jmp     short loc_18002FF76
0x18002ff28  test    eax, eax
0x18002ff2a  jnz     short loc_18002FF76
0x18002ff2c  mov     eax, cs:g_dwDebugFlags
0x18002ff32  test    al, 3
0x18002ff34  mov     [rdi+150h], r15d
0x18002ff3b  setnz   cl
0x18002ff3e  bt      eax, 1Fh
0x18002ff42  setb    al
0x18002ff45  test    al, cl
0x18002ff47  jz      short loc_18002FF76
0x18002ff49  mov     rcx, cs:g_pDebug
0x18002ff50  lea     rax, aGoodConfigRead; "Good config read, all app pools should "...
0x18002ff57  lea     r9, aConfigManagerP_1; "CONFIG_MANAGER::ProcessConfigChangeOnCo"...
0x18002ff5e  mov     [rsp+80h+var_60], rax
0x18002ff63  mov     r8d, 351h
0x18002ff69  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002ff70  call    cs:__imp_PuDbgPrint
0x18002ff76  mov     rcx, [rbp+arg_10]
0x18002ff7a  test    rcx, rcx
0x18002ff7d  jz      short loc_18002FF91
0x18002ff7f  mov     rax, [rcx]
0x18002ff82  mov     edx, r15d
0x18002ff85  mov     rax, [rax]
0x18002ff88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ff8d  mov     [rbp+arg_10], r13
0x18002ff91  mov     rcx, [rbp+arg_0]
0x18002ff95  test    rcx, rcx
0x18002ff98  jz      short loc_18002FFAC
0x18002ff9a  mov     rax, [rcx]
0x18002ff9d  mov     edx, r15d
0x18002ffa0  mov     rax, [rax]
0x18002ffa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ffa8  mov     [rbp+arg_0], r13
0x18002ffac  mov     rcx, [rbp+arg_18]
0x18002ffb0  test    rcx, rcx
0x18002ffb3  jz      short loc_18002FFC7
0x18002ffb5  mov     rax, [rcx]
0x18002ffb8  mov     edx, r15d
0x18002ffbb  mov     rax, [rax]
  ... truncated ...
```
