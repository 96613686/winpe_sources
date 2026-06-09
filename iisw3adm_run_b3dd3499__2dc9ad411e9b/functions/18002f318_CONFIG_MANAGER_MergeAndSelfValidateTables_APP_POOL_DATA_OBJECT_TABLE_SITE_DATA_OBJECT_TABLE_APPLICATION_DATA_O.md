# CONFIG_MANAGER::MergeAndSelfValidateTables(APP_POOL_DATA_OBJECT_TABLE *,SITE_DATA_OBJECT_TABLE *,APPLICATION_DATA_OBJECT_TABLE *,GLOBAL_DATA_STORE *,PROTOCOL_DATA_OBJECT_TABLE *)

- ea: `0x18002f318`
- end: `0x18002f663`
- name: `?MergeAndSelfValidateTables@CONFIG_MANAGER@@AEAAJPEAVAPP_POOL_DATA_OBJECT_TABLE@@PEAVSITE_DATA_OBJECT_TABLE@@PEAVAPPLICATION_DATA_OBJECT_TABLE@@PEAVGLOBAL_DATA_STORE@@PEAVPROTOCOL_DATA_OBJECT_TABLE@@@Z`
- size: `843`
- prototype: `__int64 __fastcall(CONFIG_MANAGER *__hidden this, struct APP_POOL_DATA_OBJECT_TABLE *, struct SITE_DATA_OBJECT_TABLE *, struct APPLICATION_DATA_OBJECT_TABLE *, struct GLOBAL_DATA_STORE *, struct PROTOCOL_DATA_OBJECT_TABLE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002e1c0`

## callees

- `0x18002f318`
- `0x18003bd4c`
- `0x18003c40c`
- `0x180062010`

## import_xrefs

- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18002f3fd`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18002f40d`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18002f4a9`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18002f4b9`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18002f555`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18002f565`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18002f609`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18002f619`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18002f3fd`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18002f40d`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18002f4a9`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18002f4b9`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18002f555`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18002f565`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18002f609`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18002f619`
- `iisutil!PuDbgPrint` at `0x18002f442`
- `iisutil!PuDbgPrint` at `0x18002f4ee`
- `iisutil!PuDbgPrint` at `0x18002f59a`
- `iisutil!PuDbgPrint` at `0x18002f64e`
- `iisutil!PuDbgPrint` at `0x18002f442`
- `iisutil!PuDbgPrint` at `0x18002f4ee`
- `iisutil!PuDbgPrint` at `0x18002f59a`
- `iisutil!PuDbgPrint` at `0x18002f64e`
- `iisutil!PuDbgPrintError` at `0x18002f380`
- `iisutil!PuDbgPrintError` at `0x18002f380`

## string_xrefs

- `0x18002f375`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\config_manager.cxx`
- `0x18002f425`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\config_manager.cxx`
- `0x18002f4d1`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\config_manager.cxx`
- `0x18002f57d`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\config_manager.cxx`
- `0x18002f631`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\config_manager.cxx`
- `0x18002f369`: `CONFIG_MANAGER::MergeAndSelfValidateTables`
- `0x18002f41a`: `CONFIG_MANAGER::MergeAndSelfValidateTables`
- `0x18002f4c6`: `CONFIG_MANAGER::MergeAndSelfValidateTables`
- `0x18002f572`: `CONFIG_MANAGER::MergeAndSelfValidateTables`
- `0x18002f626`: `CONFIG_MANAGER::MergeAndSelfValidateTables`
- `0x18002f436`: `Size of Pool Orig Table = %d, Temp Table %d\n`
- `0x18002f4e2`: `Size of site Orig Table = %d, Temp Table %d\n`
- `0x18002f58e`: `Size of app Orig Table = %d, Temp Table %d\n`
- `0x18002f5d4`: `Failed to merge the protocol data\n`
- `0x18002f642`: `Size of Protocol Orig Table = %d, Temp Table %d\n`

## pseudocode

```c
__int64 __fastcall CONFIG_MANAGER::MergeAndSelfValidateTables(
        GLOBAL_DATA_STORE **this,
        struct APP_POOL_DATA_OBJECT_TABLE *a2,
        struct SITE_DATA_OBJECT_TABLE *a3,
        struct APPLICATION_DATA_OBJECT_TABLE *a4,
        struct GLOBAL_DATA_STORE *a5,
        struct PROTOCOL_DATA_OBJECT_TABLE *a6)
{
  int v10; // edi
  unsigned int v11; // ebx
  unsigned int v12; // eax
  unsigned int v13; // ebx
  unsigned int v14; // eax
  unsigned int v15; // ebx
  unsigned int v16; // eax
  unsigned int v17; // ebx
  unsigned int v18; // eax

  v10 = GLOBAL_DATA_STORE::MergeTable(this[6], a5);
  if ( v10 >= 0 )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this[6] + 1) + 16LL))(*((_QWORD *)this[6] + 1));
    v10 = (*(__int64 (__fastcall **)(GLOBAL_DATA_STORE *, struct APP_POOL_DATA_OBJECT_TABLE *, _QWORD, _QWORD))(*(_QWORD *)this[3] + 8LL))(
            this[3],
            a2,
            0,
            0);
    if ( v10 >= 0 )
    {
      DATA_OBJECT_TABLE::PerformSelfValidation(this[3]);
      if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x10000000) != 0 )
      {
        v11 = CLKRHashTable::Size((struct APP_POOL_DATA_OBJECT_TABLE *)((char *)a2 + 8));
        v12 = CLKRHashTable::Size((GLOBAL_DATA_STORE *)((char *)this[3] + 8));
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_manager.cxx",
          1142,
          "CONFIG_MANAGER::MergeAndSelfValidateTables",
          "Size of Pool Orig Table = %d, Temp Table %d\n",
          v12,
          v11);
      }
      v10 = (*(__int64 (__fastcall **)(GLOBAL_DATA_STORE *, struct SITE_DATA_OBJECT_TABLE *, _QWORD, _QWORD))(*(_QWORD *)this[4] + 8LL))(
              this[4],
              a3,
              0,
              0);
      if ( v10 >= 0 )
      {
        DATA_OBJECT_TABLE::PerformSelfValidation(this[4]);
        if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x10000000) != 0 )
        {
          v13 = CLKRHashTable::Size((struct SITE_DATA_OBJECT_TABLE *)((char *)a3 + 8));
          v14 = CLKRHashTable::Size((GLOBAL_DATA_STORE *)((char *)this[4] + 8));
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_manager.cxx",
            1171,
            "CONFIG_MANAGER::MergeAndSelfValidateTables",
            "Size of site Orig Table = %d, Temp Table %d\n",
            v14,
            v13);
        }
        v10 = (*(__int64 (__fastcall **)(GLOBAL_DATA_STORE *, struct APPLICATION_DATA_OBJECT_TABLE *, _QWORD, _QWORD))(*(_QWORD *)this[5] + 8LL))(
                this[5],
                a4,
                0,
                0);
        if ( v10 >= 0 )
        {
          DATA_OBJECT_TABLE::PerformSelfValidation(this[5]);
          if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x10000000) != 0 )
          {
            v15 = CLKRHashTable::Size((struct APPLICATION_DATA_OBJECT_TABLE *)((char *)a4 + 8));
            v16 = CLKRHashTable::Size((GLOBAL_DATA_STORE *)((char *)this[5] + 8));
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_manager.cxx",
              1200,
              "CONFIG_MANAGER::MergeAndSelfValidateTables",
              "Size of app Orig Table = %d, Temp Table %d\n",
              v16,
              v15);
          }
          v10 = (*(__int64 (__fastcall **)(GLOBAL_DATA_STORE *, struct PROTOCOL_DATA_OBJECT_TABLE *, _QWORD, _QWORD))(*(_QWORD *)this[7] + 8LL))(
                  this[7],
                  a6,
                  0,
                  0);
          if ( v10 >= 0 )
          {
            DATA_OBJECT_TABLE::PerformSelfValidation(this[7]);
            if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x10000000) != 0 )
            {
              v17 = CLKRHashTable::Size((struct PROTOCOL_DATA_OBJECT_TABLE *)((char *)a6 + 8));
              v18 = CLKRHashTable::Size((GLOBAL_DATA_STORE *)((char *)this[7] + 8));
              PuDbgPrint(
                g_pDebug,
                "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_manager.cxx",
                1229,
                "CONFIG_MANAGER::MergeAndSelfValidateTables",
                "Size of Protocol Orig Table = %d, Temp Table %d\n",
                v18,
                v17);
            }
          }
          else if ( (g_dwDebugFlags & 0xF) != 0 )
          {
            PuDbgPrintError(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_manager.cxx",
              1215,
              "CONFIG_MANAGER::MergeAndSelfValidateTables",
              v10,
              "Failed to merge the protocol data\n");
          }
        }
        else if ( (g_dwDebugFlags & 0xF) != 0 )
        {
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_manager.cxx",
            1187,
            "CONFIG_MANAGER::MergeAndSelfValidateTables",
            v10,
            "Failed to merge the application data\n");
        }
      }
      else if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_manager.cxx",
          1158,
          "CONFIG_MANAGER::MergeAndSelfValidateTables",
          v10,
          "Failed to merge the site data\n");
      }
    }
    else if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_manager.cxx",
        1128,
        "CONFIG_MANAGER::MergeAndSelfValidateTables",
        v10,
        "Failed to merge the app pool data\n");
    }
  }
  else if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_manager.cxx",
      1107,
      "CONFIG_MANAGER::MergeAndSelfValidateTables",
      v10,
      "Failed to merge the global data\n");
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18002f318  push    rbx
0x18002f31a  push    rdi
0x18002f31b  push    r13
0x18002f31d  push    r14
0x18002f31f  push    r15
0x18002f321  sub     rsp, 40h
0x18002f325  mov     rbx, rdx
0x18002f328  mov     r14, rcx
0x18002f32b  mov     rdx, [rsp+68h+arg_20]; struct GLOBAL_DATA_STORE *
0x18002f333  mov     r13, r9
0x18002f336  mov     rcx, [rcx+30h]; this
0x18002f33a  mov     r15, r8
0x18002f33d  call    ?MergeTable@GLOBAL_DATA_STORE@@QEAAJPEAV1@@Z; GLOBAL_DATA_STORE::MergeTable(GLOBAL_DATA_STORE *)
0x18002f342  mov     edi, eax
0x18002f344  test    eax, eax
0x18002f346  jns     short loc_18002F38B
0x18002f348  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002f34f  jz      loc_18002F654
0x18002f355  lea     rax, aFailedToMergeT_2; "Failed to merge the global data\n"
0x18002f35c  mov     r8d, 453h
0x18002f362  mov     rcx, cs:g_pDebug
0x18002f369  lea     r9, aConfigManagerM; "CONFIG_MANAGER::MergeAndSelfValidateTab"...
0x18002f370  mov     [rsp+68h+var_40], rax
0x18002f375  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002f37c  mov     dword ptr [rsp+68h+var_48], edi
0x18002f380  call    cs:__imp_PuDbgPrintError
0x18002f386  jmp     loc_18002F654
0x18002f38b  mov     rax, [r14+30h]
0x18002f38f  mov     rcx, [rax+8]
0x18002f393  mov     rax, [rcx]
0x18002f396  mov     rax, [rax+10h]
0x18002f39a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f39f  mov     rcx, [r14+18h]
0x18002f3a3  xor     r9d, r9d
0x18002f3a6  xor     r8d, r8d
0x18002f3a9  mov     rdx, rbx
0x18002f3ac  mov     rax, [rcx]
0x18002f3af  mov     rax, [rax+8]
0x18002f3b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f3b8  mov     edi, eax
0x18002f3ba  test    eax, eax
0x18002f3bc  jns     short loc_18002F3DA
0x18002f3be  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002f3c5  jz      loc_18002F654
0x18002f3cb  lea     rax, aFailedToMergeT_1; "Failed to merge the app pool data\n"
0x18002f3d2  mov     r8d, 468h
0x18002f3d8  jmp     short loc_18002F362
0x18002f3da  mov     rcx, [r14+18h]; this
0x18002f3de  call    ?PerformSelfValidation@DATA_OBJECT_TABLE@@QEAAXXZ; DATA_OBJECT_TABLE::PerformSelfValidation(void)
0x18002f3e3  mov     eax, cs:g_dwDebugFlags
0x18002f3e9  test    al, 3
0x18002f3eb  setnz   cl
0x18002f3ee  bt      eax, 1Ch
0x18002f3f2  setb    al
0x18002f3f5  test    al, cl
0x18002f3f7  jz      short loc_18002F448
0x18002f3f9  lea     rcx, [rbx+8]
0x18002f3fd  call    cs:__imp_?Size@CLKRHashTable@@QEBAKXZ; CLKRHashTable::Size(void)
0x18002f403  mov     rcx, [r14+18h]
0x18002f407  mov     ebx, eax
0x18002f409  add     rcx, 8
0x18002f40d  call    cs:__imp_?Size@CLKRHashTable@@QEBAKXZ; CLKRHashTable::Size(void)
0x18002f413  mov     rcx, cs:g_pDebug
0x18002f41a  lea     r9, aConfigManagerM; "CONFIG_MANAGER::MergeAndSelfValidateTab"...
0x18002f421  mov     [rsp+68h+var_38], ebx
0x18002f425  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002f42c  mov     dword ptr [rsp+68h+var_40], eax
0x18002f430  mov     r8d, 476h
0x18002f436  lea     rax, aSizeOfPoolOrig; "Size of Pool Orig Table = %d, Temp Tabl"...
0x18002f43d  mov     [rsp+68h+var_48], rax
0x18002f442  call    cs:__imp_PuDbgPrint
0x18002f448  mov     rcx, [r14+20h]
0x18002f44c  xor     r9d, r9d
0x18002f44f  xor     r8d, r8d
0x18002f452  mov     rdx, r15
0x18002f455  mov     rax, [rcx]
0x18002f458  mov     rax, [rax+8]
0x18002f45c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f461  mov     edi, eax
0x18002f463  test    eax, eax
0x18002f465  jns     short loc_18002F486
0x18002f467  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002f46e  jz      loc_18002F654
0x18002f474  lea     rax, aFailedToMergeT_0; "Failed to merge the site data\n"
0x18002f47b  mov     r8d, 486h
0x18002f481  jmp     loc_18002F362
0x18002f486  mov     rcx, [r14+20h]; this
0x18002f48a  call    ?PerformSelfValidation@DATA_OBJECT_TABLE@@QEAAXXZ; DATA_OBJECT_TABLE::PerformSelfValidation(void)
0x18002f48f  mov     eax, cs:g_dwDebugFlags
0x18002f495  test    al, 3
0x18002f497  setnz   cl
0x18002f49a  bt      eax, 1Ch
0x18002f49e  setb    al
0x18002f4a1  test    al, cl
0x18002f4a3  jz      short loc_18002F4F4
0x18002f4a5  lea     rcx, [r15+8]
0x18002f4a9  call    cs:__imp_?Size@CLKRHashTable@@QEBAKXZ; CLKRHashTable::Size(void)
0x18002f4af  mov     rcx, [r14+20h]
0x18002f4b3  mov     ebx, eax
0x18002f4b5  add     rcx, 8
0x18002f4b9  call    cs:__imp_?Size@CLKRHashTable@@QEBAKXZ; CLKRHashTable::Size(void)
0x18002f4bf  mov     rcx, cs:g_pDebug
0x18002f4c6  lea     r9, aConfigManagerM; "CONFIG_MANAGER::MergeAndSelfValidateTab"...
0x18002f4cd  mov     [rsp+68h+var_38], ebx
0x18002f4d1  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002f4d8  mov     dword ptr [rsp+68h+var_40], eax
0x18002f4dc  mov     r8d, 493h
0x18002f4e2  lea     rax, aSizeOfSiteOrig; "Size of site Orig Table = %d, Temp Tabl"...
0x18002f4e9  mov     [rsp+68h+var_48], rax
0x18002f4ee  call    cs:__imp_PuDbgPrint
0x18002f4f4  mov     rcx, [r14+28h]
0x18002f4f8  xor     r9d, r9d
0x18002f4fb  xor     r8d, r8d
0x18002f4fe  mov     rdx, r13
0x18002f501  mov     rax, [rcx]
0x18002f504  mov     rax, [rax+8]
0x18002f508  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f50d  mov     edi, eax
0x18002f50f  test    eax, eax
0x18002f511  jns     short loc_18002F532
0x18002f513  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002f51a  jz      loc_18002F654
0x18002f520  lea     rax, aFailedToMergeT; "Failed to merge the application data\n"
0x18002f527  mov     r8d, 4A3h
0x18002f52d  jmp     loc_18002F362
0x18002f532  mov     rcx, [r14+28h]; this
0x18002f536  call    ?PerformSelfValidation@DATA_OBJECT_TABLE@@QEAAXXZ; DATA_OBJECT_TABLE::PerformSelfValidation(void)
0x18002f53b  mov     eax, cs:g_dwDebugFlags
0x18002f541  test    al, 3
0x18002f543  setnz   cl
0x18002f546  bt      eax, 1Ch
0x18002f54a  setb    al
0x18002f54d  test    al, cl
0x18002f54f  jz      short loc_18002F5A0
0x18002f551  lea     rcx, [r13+8]
0x18002f555  call    cs:__imp_?Size@CLKRHashTable@@QEBAKXZ; CLKRHashTable::Size(void)
0x18002f55b  mov     rcx, [r14+28h]
0x18002f55f  mov     ebx, eax
0x18002f561  add     rcx, 8
0x18002f565  call    cs:__imp_?Size@CLKRHashTable@@QEBAKXZ; CLKRHashTable::Size(void)
0x18002f56b  mov     rcx, cs:g_pDebug
0x18002f572  lea     r9, aConfigManagerM; "CONFIG_MANAGER::MergeAndSelfValidateTab"...
0x18002f579  mov     [rsp+68h+var_38], ebx
0x18002f57d  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002f584  mov     dword ptr [rsp+68h+var_40], eax
0x18002f588  mov     r8d, 4B0h
0x18002f58e  lea     rax, aSizeOfAppOrigT; "Size of app Orig Table = %d, Temp Table"...
0x18002f595  mov     [rsp+68h+var_48], rax
0x18002f59a  call    cs:__imp_PuDbgPrint
0x18002f5a0  mov     rcx, [r14+38h]
0x18002f5a4  xor     r9d, r9d
0x18002f5a7  mov     rbx, [rsp+68h+arg_28]
0x18002f5af  xor     r8d, r8d
0x18002f5b2  mov     rdx, rbx
0x18002f5b5  mov     rax, [rcx]
0x18002f5b8  mov     rax, [rax+8]
0x18002f5bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f5c1  mov     edi, eax
0x18002f5c3  test    eax, eax
0x18002f5c5  jns     short loc_18002F5E6
0x18002f5c7  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002f5ce  jz      loc_18002F654
0x18002f5d4  lea     rax, aFailedToMergeT_3; "Failed to merge the protocol data\n"
0x18002f5db  mov     r8d, 4BFh
0x18002f5e1  jmp     loc_18002F362
0x18002f5e6  mov     rcx, [r14+38h]; this
0x18002f5ea  call    ?PerformSelfValidation@DATA_OBJECT_TABLE@@QEAAXXZ; DATA_OBJECT_TABLE::PerformSelfValidation(void)
0x18002f5ef  mov     eax, cs:g_dwDebugFlags
0x18002f5f5  test    al, 3
0x18002f5f7  setnz   cl
0x18002f5fa  bt      eax, 1Ch
0x18002f5fe  setb    al
0x18002f601  test    al, cl
0x18002f603  jz      short loc_18002F654
0x18002f605  lea     rcx, [rbx+8]
0x18002f609  call    cs:__imp_?Size@CLKRHashTable@@QEBAKXZ; CLKRHashTable::Size(void)
0x18002f60f  mov     rcx, [r14+38h]
0x18002f613  mov     ebx, eax
0x18002f615  add     rcx, 8
0x18002f619  call    cs:__imp_?Size@CLKRHashTable@@QEBAKXZ; CLKRHashTable::Size(void)
0x18002f61f  mov     rcx, cs:g_pDebug
0x18002f626  lea     r9, aConfigManagerM; "CONFIG_MANAGER::MergeAndSelfValidateTab"...
0x18002f62d  mov     [rsp+68h+var_38], ebx
0x18002f631  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002f638  mov     dword ptr [rsp+68h+var_40], eax
0x18002f63c  mov     r8d, 4CDh
0x18002f642  lea     rax, aSizeOfProtocol; "Size of Protocol Orig Table = %d, Temp "...
0x18002f649  mov     [rsp+68h+var_48], rax
0x18002f64e  call    cs:__imp_PuDbgPrint
0x18002f654  mov     eax, edi
0x18002f656  add     rsp, 40h
0x18002f65a  pop     r15
0x18002f65c  pop     r14
0x18002f65e  pop     r13
0x18002f660  pop     rdi
0x18002f661  pop     rbx
0x18002f662  retn
```
