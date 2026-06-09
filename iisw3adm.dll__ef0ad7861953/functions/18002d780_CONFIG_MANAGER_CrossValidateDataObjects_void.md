# CONFIG_MANAGER::CrossValidateDataObjects(void)

- ea: `0x18002d780`
- end: `0x18002e10b`
- name: `?CrossValidateDataObjects@CONFIG_MANAGER@@AEAAJXZ`
- size: `2443`
- prototype: `__int64 __fastcall(CONFIG_MANAGER *__hidden this)`
- caller_count: `4`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002e1c0`
- `0x18002e84c`
- `0x1800300b4`
- `0x18003027c`

## callees

- `0x180005878`
- `0x18002d780`
- `0x18003d7e4`
- `0x18003db80`
- `0x18003dc04`
- `0x1800600f8`
- `0x180060130`
- `0x180060160`
- `0x1800603e4`
- `0x18006100e`
- `0x180061060`
- `0x180062010`

## import_xrefs

- `msvcrt!_ultow` at `0x18002dff9`
- `msvcrt!_ultow` at `0x18002dff9`
- `msvcrt!_wcsicmp` at `0x18002dae2`
- `msvcrt!_wcsicmp` at `0x18002dae2`
- `iisutil!?Begin@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x18002d83b`
- `iisutil!?Begin@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x18002d9d8`
- `iisutil!?Begin@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x18002dc10`
- `iisutil!?Begin@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x18002dea6`
- `iisutil!?Begin@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x18002d83b`
- `iisutil!?Begin@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x18002d9d8`
- `iisutil!?Begin@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x18002dc10`
- `iisutil!?Begin@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x18002dea6`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18002db05`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18002dcea`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18002ddc0`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18002df7b`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18002db05`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18002dcea`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18002ddc0`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18002df7b`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x18002d848`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x18002d872`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x18002d98b`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x18002d9e5`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x18002dbae`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x18002dc1d`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x18002dc4a`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x18002de59`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x18002deb4`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x18002e05b`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x18002d848`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x18002d872`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x18002d98b`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x18002d9e5`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x18002dbae`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x18002dc1d`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x18002dc4a`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x18002de59`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x18002deb4`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x18002e05b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002e0a6`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002e0d2`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002e0e0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002e0a6`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002e0d2`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002e0e0`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18002d852`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18002d87c`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18002d898`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18002d995`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18002d9b1`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18002d9c3`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18002d9ef`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18002dbb8`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18002dbd4`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18002dbe6`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18002dc27`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18002dc57`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18002dc73`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18002de66`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18002de82`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18002de94`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18002debe`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18002e065`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18002e086`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18002e099`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18002d852`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18002d87c`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18002d898`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18002d995`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18002d9b1`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18002d9c3`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18002d9ef`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18002dbb8`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18002dbd4`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18002dbe6`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18002dc27`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18002dc57`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18002dc73`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18002de66`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18002de82`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18002de94`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18002debe`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18002e065`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18002e086`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18002e099`
- `iisutil!?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x18002d864`
- `iisutil!?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x18002d97d`
- `iisutil!?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x18002dba0`
- `iisutil!?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x18002dc3c`
- `iisutil!?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x18002de4b`
- `iisutil!?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x18002e04b`
- `iisutil!?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x18002d864`
- `iisutil!?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x18002d97d`
- `iisutil!?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x18002dba0`
- `iisutil!?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x18002dc3c`
- `iisutil!?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x18002de4b`
- `iisutil!?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x18002e04b`
- `iisutil!PuDbgPrint` at `0x18002da7f`
- `iisutil!PuDbgPrint` at `0x18002df59`
- `iisutil!PuDbgPrint` at `0x18002da7f`
- `iisutil!PuDbgPrint` at `0x18002df59`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18002d7bf`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18002d7de`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18002d809`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18002d7bf`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18002d7de`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18002d809`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002da90`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002dcbe`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002dd9a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002da90`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002dcbe`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002dd9a`
- `iisutil!??9CLKRHashTable_Iterator@@QEBA_NAEBV0@@Z` at `0x18002d88b`
- `iisutil!??9CLKRHashTable_Iterator@@QEBA_NAEBV0@@Z` at `0x18002d9a4`
- `iisutil!??9CLKRHashTable_Iterator@@QEBA_NAEBV0@@Z` at `0x18002dbc7`
- `iisutil!??9CLKRHashTable_Iterator@@QEBA_NAEBV0@@Z` at `0x18002dc66`
- `iisutil!??9CLKRHashTable_Iterator@@QEBA_NAEBV0@@Z` at `0x18002de75`
- `iisutil!??9CLKRHashTable_Iterator@@QEBA_NAEBV0@@Z` at `0x18002e077`
- `iisutil!??9CLKRHashTable_Iterator@@QEBA_NAEBV0@@Z` at `0x18002d88b`
- `iisutil!??9CLKRHashTable_Iterator@@QEBA_NAEBV0@@Z` at `0x18002d9a4`
- `iisutil!??9CLKRHashTable_Iterator@@QEBA_NAEBV0@@Z` at `0x18002dbc7`
- `iisutil!??9CLKRHashTable_Iterator@@QEBA_NAEBV0@@Z` at `0x18002dc66`
- `iisutil!??9CLKRHashTable_Iterator@@QEBA_NAEBV0@@Z` at `0x18002de75`
- `iisutil!??9CLKRHashTable_Iterator@@QEBA_NAEBV0@@Z` at `0x18002e077`
- `iisutil!?Increment@CLKRHashTable_Iterator@@QEAA_NXZ` at `0x18002d96b`
- `iisutil!?Increment@CLKRHashTable_Iterator@@QEAA_NXZ` at `0x18002db8e`
- `iisutil!?Increment@CLKRHashTable_Iterator@@QEAA_NXZ` at `0x18002de36`
- `iisutil!?Increment@CLKRHashTable_Iterator@@QEAA_NXZ` at `0x18002e039`
- `iisutil!?Increment@CLKRHashTable_Iterator@@QEAA_NXZ` at `0x18002d96b`
- `iisutil!?Increment@CLKRHashTable_Iterator@@QEAA_NXZ` at `0x18002db8e`
- `iisutil!?Increment@CLKRHashTable_Iterator@@QEAA_NXZ` at `0x18002de36`
- `iisutil!?Increment@CLKRHashTable_Iterator@@QEAA_NXZ` at `0x18002e039`

## string_xrefs

- `0x18002da51`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\config_manager.cxx`
- `0x18002df2b`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\config_manager.cxx`
- `0x18002da43`: `CONFIG_MANAGER::CrossValidateDataObjects`
- `0x18002df1d`: `CONFIG_MANAGER::CrossValidateDataObjects`

## pseudocode

```c
__int64 __fastcall CONFIG_MANAGER::CrossValidateDataObjects(CONFIG_MANAGER *this)
{
  int v2; // edi
  int v3; // r14d
  int v4; // r12d
  const struct CLKRHashTable_Iterator *v5; // rax
  const struct CLKRHashTable_Iterator *v6; // rax
  char v7; // bl
  __int64 v8; // rbx
  signed int AppPoolSid; // eax
  const struct CLKRHashTable_Iterator *v10; // rax
  char v11; // bl
  const wchar_t *v12; // rsi
  const struct CLKRHashTable_Iterator *v13; // rax
  __int64 v14; // rbx
  const wchar_t *v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rcx
  void *v19; // rcx
  const struct CLKRHashTable_Iterator *v20; // rax
  char v21; // bl
  CLKRHashTable_Iterator *v22; // rcx
  const struct CLKRHashTable_Iterator *v23; // rax
  const struct CLKRHashTable_Iterator *v24; // rax
  char v25; // bl
  __int64 v26; // rbx
  int v27; // esi
  __int64 v28; // rcx
  volatile signed __int32 *v29; // rdi
  __int64 v30; // rbx
  unsigned int v31; // esi
  __int64 v32; // rcx
  void (__fastcall ***v33)(_QWORD); // rcx
  void (__fastcall ***v34)(void *, __int64); // rcx
  const struct CLKRHashTable_Iterator *v35; // rax
  const struct CLKRHashTable_Iterator *v36; // rax
  __int64 v37; // rsi
  __int64 v38; // rcx
  volatile signed __int32 *v39; // rcx
  unsigned __int16 *v40; // rbx
  const struct CLKRHashTable_Iterator *v41; // rax
  char v42; // bl
  void *v44; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v45[16]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v46; // [rsp+58h] [rbp-A8h]
  __int16 v47; // [rsp+64h] [rbp-9Ch]
  unsigned __int16 *v48[2]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v49[16]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v50; // [rsp+90h] [rbp-70h]
  __int16 v51; // [rsp+9Ch] [rbp-64h]
  _BYTE v52[16]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v53; // [rsp+B8h] [rbp-48h]
  __int16 v54; // [rsp+C4h] [rbp-3Ch]
  void **v55; // [rsp+D0h] [rbp-30h] BYREF
  int v56; // [rsp+D8h] [rbp-28h]
  _BYTE v57[48]; // [rsp+E0h] [rbp-20h] BYREF
  void **v58; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v59[56]; // [rsp+118h] [rbp+18h] BYREF
  void **v60; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v61[56]; // [rsp+158h] [rbp+58h] BYREF
  int v62; // [rsp+190h] [rbp+90h]
  _BYTE v63[32]; // [rsp+1A0h] [rbp+A0h] BYREF
  _WORD *v64; // [rsp+1C0h] [rbp+C0h]
  int v65; // [rsp+1D0h] [rbp+D0h]
  _BYTE v66[160]; // [rsp+1E0h] [rbp+E0h] BYREF
  wchar_t Buffer[20]; // [rsp+280h] [rbp+180h] BYREF

  v60 = &APPLICATION_DATA_OBJECT_KEY::`vftable';
  STRU::STRU((STRU *)v61);
  v58 = &APP_POOL_DATA_OBJECT_KEY::`vftable';
  v62 = 0;
  STRU::STRU((STRU *)v59);
  v56 = 0;
  v55 = &SITE_DATA_OBJECT_KEY::`vftable';
  v2 = 0;
  APP_POOL_HASH_MAPPER::APP_POOL_HASH_MAPPER((APP_POOL_HASH_MAPPER *)v66);
  STRU::STRU((STRU *)v63);
  v3 = 1;
  v44 = 0;
  v4 = *((_DWORD *)g_pWebAdminService + 412);
  if ( !v4 )
  {
    v5 = (const struct CLKRHashTable_Iterator *)CLKRHashTable::Begin(*((_QWORD *)this + 3) + 8LL, v57);
    CLKRHashTable_Iterator::CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v52, v5);
    CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v57);
    v6 = (const struct CLKRHashTable_Iterator *)CLKRHashTable::End(*((_QWORD *)this + 3) + 8LL, v49);
    CLKRHashTable_Iterator::CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v45, v6);
    CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v49);
    v7 = CLKRHashTable_Iterator::operator!=(v52, v45);
    CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v45);
    if ( v7 )
    {
      do
      {
        v8 = *(_QWORD *)(v53 + 8LL * v54 + 24);
        *v64 = 0;
        v65 = 0;
        if ( APP_POOL_HASH_MAPPER::CheckAndAddAppPool(
               (APP_POOL_HASH_MAPPER *)v66,
               *(const unsigned __int16 **)(v8 + 80),
               (struct STRU *)v63) == -2147024844 )
        {
          v48[0] = *(unsigned __int16 **)(v8 + 80);
          WEB_ADMIN_SERVICE::LogEvent(
            g_pWebAdminService,
            0xC0001446,
            1u,
            (const unsigned __int16 **const)v48,
            0x80070034);
          *(_DWORD *)(v8 + 24) = 0;
        }
        AppPoolSid = APP_POOL_HASH_MAPPER::GetAppPoolSid(
                       (APP_POOL_HASH_MAPPER *)v66,
                       *(const unsigned __int16 **)(v8 + 80),
                       &v44);
        v2 = AppPoolSid;
        if ( AppPoolSid < 0 )
        {
          v48[0] = *(unsigned __int16 **)(v8 + 80);
          WEB_ADMIN_SERVICE::LogEvent(
            g_pWebAdminService,
            0xC0001446,
            1u,
            (const unsigned __int16 **const)v48,
            AppPoolSid);
          *(_DWORD *)(v8 + 24) = 0;
        }
        *(_QWORD *)(v8 + 992) = v44;
        v44 = 0;
        CLKRHashTable_Iterator::Increment((CLKRHashTable_Iterator *)v52);
        v10 = (const struct CLKRHashTable_Iterator *)CLKRHashTable::End(*((_QWORD *)this + 3) + 8LL, v49);
        CLKRHashTable_Iterator::CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v45, v10);
        CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v49);
        v11 = CLKRHashTable_Iterator::operator!=(v52, v45);
        CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v45);
      }
      while ( v11 );
    }
    CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v52);
  }
  v12 = 0;
  v13 = (const struct CLKRHashTable_Iterator *)CLKRHashTable::Begin(*((_QWORD *)this + 5) + 8LL, v57);
  CLKRHashTable_Iterator::CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v52, v13);
  CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v57);
  while ( 1 )
  {
    v20 = (const struct CLKRHashTable_Iterator *)CLKRHashTable::End(*((_QWORD *)this + 5) + 8LL, v49);
    CLKRHashTable_Iterator::CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v45, v20);
    CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v49);
    v21 = CLKRHashTable_Iterator::operator!=(v52, v45);
    CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v45);
    if ( !v21 )
      break;
    v14 = *(_QWORD *)(v53 + 8LL * v54 + 24);
    if ( *(_DWORD *)(v14 + 24) && *(_DWORD *)(v14 + 28) && !*(_DWORD *)(v14 + 20) )
    {
      if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x10000000) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_manager.cxx",
          1421,
          "CONFIG_MANAGER::CrossValidateDataObjects",
          "Application '%S' for site '%d' AppPoolId = '%S' \n ",
          *(const wchar_t **)(v14 + 80),
          *(_DWORD *)(v14 + 104),
          *(const wchar_t **)(v14 + 152));
      v2 = STRU::Copy((STRU *)v59, *(const unsigned __int16 **)(v14 + 152));
      if ( v2 < 0 )
      {
        v22 = (CLKRHashTable_Iterator *)v52;
        goto LABEL_91;
      }
      if ( v4 )
      {
        if ( v12 )
        {
          if ( v3 )
          {
            v15 = *(const wchar_t **)(v14 + 152);
            v16 = -1;
            v17 = -1;
            do
              ++v17;
            while ( v15[v17] );
            do
              ++v16;
            while ( v12[v16] );
            if ( v16 != v17 || _wcsicmp(v12, v15) )
              v3 = 0;
          }
        }
        else
        {
          v12 = *(const wchar_t **)(v14 + 152);
        }
      }
      v18 = *((_QWORD *)this + 3) + 8LL;
      v44 = 0;
      if ( (unsigned int)CLKRHashTable::FindKey(v18, &v58, &v44) )
      {
        *(_DWORD *)(v14 + 24) = 0;
      }
      else
      {
        v19 = v44;
        if ( !*((_DWORD *)v44 + 6) || !*((_DWORD *)v44 + 7) || *((_DWORD *)v44 + 5) )
          *(_DWORD *)(v14 + 24) = 0;
        if ( v4 )
          *((_DWORD *)v19 + 256) = 1;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v19 + 3, 0xFFFFFFFF) == 1 )
          (**(void (__fastcall ***)(void *, __int64))v19)(v19, 1);
      }
      if ( !*(_DWORD *)(v14 + 24) )
        WMS_ERROR_LOGGER::LogApplicationInvalidDueToMissingAppPoolId(
          (WEB_ADMIN_SERVICE *)((char *)g_pWebAdminService + 1576),
          *(_DWORD *)(v14 + 104),
          *(const unsigned __int16 **)(v14 + 80),
          *(const unsigned __int16 **)(v14 + 152),
          *(_DWORD *)(v14 + 16));
    }
    CLKRHashTable_Iterator::Increment((CLKRHashTable_Iterator *)v52);
  }
  CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v52);
  if ( !v3 )
  {
    v2 = -2147024828;
    goto LABEL_92;
  }
  v23 = (const struct CLKRHashTable_Iterator *)CLKRHashTable::Begin(*((_QWORD *)this + 4) + 8LL, v57);
  CLKRHashTable_Iterator::CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v49, v23);
  CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v57);
  v24 = (const struct CLKRHashTable_Iterator *)CLKRHashTable::End(*((_QWORD *)this + 4) + 8LL, Buffer);
  CLKRHashTable_Iterator::CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v45, v24);
  CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)Buffer);
  v25 = CLKRHashTable_Iterator::operator!=(v49, v45);
  CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v45);
  while ( v25 )
  {
    v26 = *(_QWORD *)(v50 + 8LL * v51 + 24);
    if ( *(_DWORD *)(v26 + 24) && *(_DWORD *)(v26 + 28) && !*(_DWORD *)(v26 + 20) )
    {
      v27 = *(_DWORD *)(v26 + 48);
      v2 = STRU::Copy((STRU *)v61, L"/");
      if ( v2 < 0 )
      {
LABEL_70:
        v22 = (CLKRHashTable_Iterator *)v49;
        goto LABEL_91;
      }
      v28 = *((_QWORD *)this + 5) + 8LL;
      v62 = v27;
      v44 = 0;
      if ( (unsigned int)CLKRHashTable::FindKey(v28, &v60, &v44) )
      {
        *(_DWORD *)(v26 + 24) = 0;
        WMS_ERROR_LOGGER::LogSiteInvalidDueToMissingAppRoot(
          (WEB_ADMIN_SERVICE *)((char *)g_pWebAdminService + 1576),
          *(_DWORD *)(v26 + 48),
          *(_DWORD *)(v26 + 16));
      }
      else
      {
        v29 = (volatile signed __int32 *)v44;
        if ( !*((_DWORD *)v44 + 7) || !*((_DWORD *)v44 + 6) )
        {
          *(_DWORD *)(v26 + 24) = 0;
          WMS_ERROR_LOGGER::LogSiteInvalidDueToInvalidRootApplication(
            (WEB_ADMIN_SERVICE *)((char *)g_pWebAdminService + 1576),
            *(_DWORD *)(v26 + 48),
            *(_DWORD *)(v26 + 16));
        }
        if ( _InterlockedExchangeAdd(v29 + 3, 0xFFFFFFFF) == 1 )
          (**(void (__fastcall ***)(void *, __int64))v29)((void *)v29, 1);
      }
      v2 = 0;
      if ( *(_DWORD *)(v26 + 24) == 1 )
      {
        v30 = *(_QWORD *)(v26 + 56);
        if ( v30 )
        {
          v31 = *(_DWORD *)(v30 + 8);
          if ( v31 )
          {
            while ( (--v31 & 0x80000000) == 0 )
            {
              v2 = STRU::Copy((STRU *)v59, *(const unsigned __int16 **)(*(_QWORD *)(*(_QWORD *)v30 + 8LL * v31) + 16LL));
              if ( v2 < 0 )
                goto LABEL_70;
              v32 = *((_QWORD *)this + 3) + 8LL;
              v44 = 0;
              if ( (unsigned int)CLKRHashTable::FindKey(v32, &v58, &v44) )
              {
                if ( v31 < *(_DWORD *)(v30 + 8) )
                {
                  v33 = *(void (__fastcall ****)(_QWORD))(*(_QWORD *)v30 + 8LL * v31);
                  (**v33)(v33);
                  memmove_0(
                    (void *)(*(_QWORD *)v30 + 8LL * v31),
                    (const void *)(*(_QWORD *)v30 + 8LL * v31 + 8),
                    8LL * (*(_DWORD *)(v30 + 8) + ~v31));
                  --*(_DWORD *)(v30 + 8);
                }
              }
              else
              {
                v34 = (void (__fastcall ***)(void *, __int64))v44;
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)v44 + 3, 0xFFFFFFFF) == 1 && v34 )
                  (**v34)(v34, 1);
              }
            }
          }
        }
      }
    }
    CLKRHashTable_Iterator::Increment((CLKRHashTable_Iterator *)v49);
    v35 = (const struct CLKRHashTable_Iterator *)CLKRHashTable::End(*((_QWORD *)this + 4) + 8LL, Buffer);
    CLKRHashTable_Iterator::CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v45, v35);
    CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)Buffer);
    v25 = CLKRHashTable_Iterator::operator!=(v49, v45);
    CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v45);
  }
  CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v49);
  v36 = (const struct CLKRHashTable_Iterator *)CLKRHashTable::Begin(*((_QWORD *)this + 5) + 8LL, v57);
  CLKRHashTable_Iterator::CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v45, v36);
  CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v57);
  while ( 1 )
  {
    v41 = (const struct CLKRHashTable_Iterator *)CLKRHashTable::End(*((_QWORD *)this + 5) + 8LL, v57);
    CLKRHashTable_Iterator::CLKRHashTable_Iterator((CLKRHashTable_Iterator *)Buffer, v41);
    CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v57);
    v42 = CLKRHashTable_Iterator::operator!=(v45, Buffer);
    CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)Buffer);
    if ( !v42 )
      break;
    v37 = *(_QWORD *)(v46 + 8LL * v47 + 24);
    if ( *(_DWORD *)(v37 + 24) && *(_DWORD *)(v37 + 28) && !*(_DWORD *)(v37 + 20) )
    {
      if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x10000000) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_manager.cxx",
          1662,
          "CONFIG_MANAGER::CrossValidateDataObjects",
          "Validating site exits on Application '%S' for site '%d' AppPoolId = '%S' \n ",
          *(const wchar_t **)(v37 + 80),
          *(_DWORD *)(v37 + 104),
          *(const wchar_t **)(v37 + 152));
      v38 = *((_QWORD *)this + 4) + 8LL;
      v56 = *(_DWORD *)(v37 + 104);
      v44 = 0;
      if ( (unsigned int)CLKRHashTable::FindKey(v38, &v55, &v44) )
      {
        *(_DWORD *)(v37 + 24) = 0;
      }
      else
      {
        v39 = (volatile signed __int32 *)v44;
        if ( !*((_DWORD *)v44 + 6) || !*((_DWORD *)v44 + 7) || *((_DWORD *)v44 + 5) )
          *(_DWORD *)(v37 + 24) = 0;
        if ( _InterlockedExchangeAdd(v39 + 3, 0xFFFFFFFF) == 1 )
          (**(void (__fastcall ***)(void *, __int64))v39)((void *)v39, 1);
      }
      if ( !*(_DWORD *)(v37 + 24) )
      {
        *(_OWORD *)v48 = 0;
        if ( !*((_DWORD *)g_pWebAdminService + 396) || *(_DWORD *)(v37 + 16) )
        {
          v40 = *(unsigned __int16 **)(v37 + 80);
          _ultow(*(_DWORD *)(v37 + 104), Buffer, 10);
          v48[0] = Buffer;
          v48[1] = v40;
          WEB_ADMIN_SERVICE::LogEvent(
            g_pWebAdminService,
            0x800013BC,
            2u,
            (const unsigned __int16 **const)v48,
            0x8007000D);
        }
      }
    }
    CLKRHashTable_Iterator::Increment((CLKRHashTable_Iterator *)v45);
  }
  v22 = (CLKRHashTable_Iterator *)v45;
LABEL_91:
  CLKRHashTable_Iterator::~CLKRHashTable_Iterator(v22);
LABEL_92:
  STRU::~STRU((STRU *)v63);
  APP_POOL_HASH_MAPPER::~APP_POOL_HASH_MAPPER((APP_POOL_HASH_MAPPER *)v66);
  v58 = &APP_POOL_DATA_OBJECT_KEY::`vftable';
  v55 = &DATA_OBJECT_KEY::`vftable';
  STRU::~STRU((STRU *)v59);
  v58 = &DATA_OBJECT_KEY::`vftable';
  STRU::~STRU((STRU *)v61);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18002d780  push    rbp
0x18002d782  push    rbx
0x18002d783  push    rsi
0x18002d784  push    rdi
0x18002d785  push    r12
0x18002d787  push    r13
0x18002d789  push    r14
0x18002d78b  push    r15
0x18002d78d  lea     rbp, [rsp-1B8h]
0x18002d795  sub     rsp, 2B8h
0x18002d79c  mov     rax, cs:__security_cookie
0x18002d7a3  xor     rax, rsp
0x18002d7a6  mov     [rbp+1F0h+var_48], rax
0x18002d7ad  mov     r15, rcx
0x18002d7b0  lea     rax, ??_7APPLICATION_DATA_OBJECT_KEY@@6B@; const APPLICATION_DATA_OBJECT_KEY::`vftable'
0x18002d7b7  lea     rcx, [rbp+1F0h+var_198]
0x18002d7bb  mov     [rbp+1F0h+var_1A0], rax
0x18002d7bf  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18002d7c5  lea     rax, ??_7APP_POOL_DATA_OBJECT_KEY@@6B@; const APP_POOL_DATA_OBJECT_KEY::`vftable'
0x18002d7cc  xor     r13d, r13d
0x18002d7cf  lea     rcx, [rbp+1F0h+var_1D8]
0x18002d7d3  mov     [rbp+1F0h+var_1E0], rax
0x18002d7d7  mov     [rbp+1F0h+var_160], r13d
0x18002d7de  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18002d7e4  lea     rax, ??_7SITE_DATA_OBJECT_KEY@@6B@; const SITE_DATA_OBJECT_KEY::`vftable'
0x18002d7eb  mov     [rbp+1F0h+var_218], r13d
0x18002d7ef  lea     rcx, [rbp+1F0h+var_110]; this
0x18002d7f6  mov     [rbp+1F0h+var_220], rax
0x18002d7fa  mov     edi, r13d
0x18002d7fd  call    ??0APP_POOL_HASH_MAPPER@@QEAA@XZ; APP_POOL_HASH_MAPPER::APP_POOL_HASH_MAPPER(void)
0x18002d802  lea     rcx, [rbp+1F0h+var_150]
0x18002d809  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18002d80f  mov     rax, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x18002d816  lea     r14d, [r13+1]
0x18002d81a  mov     [rsp+2F0h+var_2B0], r13
0x18002d81f  mov     r12d, [rax+670h]
0x18002d826  test    r12d, r12d
0x18002d829  jnz     loc_18002D9C9
0x18002d82f  mov     rcx, [r15+18h]
0x18002d833  lea     rdx, [rbp+1F0h+var_210]
0x18002d837  add     rcx, 8
0x18002d83b  call    cs:__imp_?Begin@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ; CLKRHashTable::Begin(void)
0x18002d841  mov     rdx, rax
0x18002d844  lea     rcx, [rbp+1F0h+var_248]
0x18002d848  call    cs:__imp_??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z; CLKRHashTable_Iterator::CLKRHashTable_Iterator(CLKRHashTable_Iterator const &)
0x18002d84e  lea     rcx, [rbp+1F0h+var_210]
0x18002d852  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x18002d858  mov     rcx, [r15+18h]
0x18002d85c  lea     rdx, [rbp+1F0h+var_270]
0x18002d860  add     rcx, 8
0x18002d864  call    cs:__imp_?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ; CLKRHashTable::End(void)
0x18002d86a  mov     rdx, rax
0x18002d86d  lea     rcx, [rsp+2F0h+var_2A8]
0x18002d872  call    cs:__imp_??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z; CLKRHashTable_Iterator::CLKRHashTable_Iterator(CLKRHashTable_Iterator const &)
0x18002d878  lea     rcx, [rbp+1F0h+var_270]
0x18002d87c  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x18002d882  lea     rdx, [rsp+2F0h+var_2A8]
0x18002d887  lea     rcx, [rbp+1F0h+var_248]
0x18002d88b  call    cs:__imp_??9CLKRHashTable_Iterator@@QEBA_NAEBV0@@Z; CLKRHashTable_Iterator::operator!=(CLKRHashTable_Iterator const &)
0x18002d891  lea     rcx, [rsp+2F0h+var_2A8]
0x18002d896  mov     bl, al
0x18002d898  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x18002d89e  test    bl, bl
0x18002d8a0  jz      loc_18002D9BF
0x18002d8a6  mov     esi, 0C0001446h
0x18002d8ab  movsx   rcx, [rbp+1F0h+var_22C]
0x18002d8b0  lea     r8, [rbp+1F0h+var_150]; struct STRU *
0x18002d8b7  mov     rax, [rbp+1F0h+var_238]
0x18002d8bb  mov     rbx, [rax+rcx*8+18h]
0x18002d8c0  lea     rcx, [rbp+1F0h+var_110]; this
0x18002d8c7  mov     rax, [rbp+1F0h+var_130]
0x18002d8ce  mov     [rax], r13w
0x18002d8d2  mov     [rbp+1F0h+var_120], r13d
0x18002d8d9  mov     rdx, [rbx+50h]; unsigned __int16 *
0x18002d8dd  call    ?CheckAndAddAppPool@APP_POOL_HASH_MAPPER@@QEAAJPEBGPEAVSTRU@@@Z; APP_POOL_HASH_MAPPER::CheckAndAddAppPool(ushort const *,STRU *)
0x18002d8e2  cmp     eax, 80070034h
0x18002d8e7  jnz     short loc_18002D914
0x18002d8e9  mov     rax, [rbx+50h]
0x18002d8ed  lea     r9, [rsp+2F0h+var_280]; unsigned __int16 **
0x18002d8f2  mov     rcx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; this
0x18002d8f9  mov     r8d, r14d; unsigned __int16
0x18002d8fc  mov     edx, esi; unsigned int
0x18002d8fe  mov     [rsp+2F0h+var_280], rax
0x18002d903  mov     [rsp+2F0h+var_2D0], 80070034h; unsigned int
0x18002d90b  call    ?LogEvent@WEB_ADMIN_SERVICE@@QEAAXKGQEAPEBGK@Z; WEB_ADMIN_SERVICE::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x18002d910  mov     [rbx+18h], r13d
0x18002d914  mov     rdx, [rbx+50h]; unsigned __int16 *
0x18002d918  lea     r8, [rsp+2F0h+var_2B0]; void **
0x18002d91d  lea     rcx, [rbp+1F0h+var_110]; this
0x18002d924  call    ?GetAppPoolSid@APP_POOL_HASH_MAPPER@@QEAAJPEBGPEAPEAX@Z; APP_POOL_HASH_MAPPER::GetAppPoolSid(ushort const *,void * *)
0x18002d929  mov     edi, eax
0x18002d92b  test    eax, eax
0x18002d92d  jns     short loc_18002D956
0x18002d92f  mov     rcx, [rbx+50h]
0x18002d933  lea     r9, [rsp+2F0h+var_280]; unsigned __int16 **
0x18002d938  mov     [rsp+2F0h+var_280], rcx
0x18002d93d  mov     r8d, r14d; unsigned __int16
0x18002d940  mov     rcx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; this
0x18002d947  mov     edx, esi; unsigned int
0x18002d949  mov     [rsp+2F0h+var_2D0], eax; unsigned int
0x18002d94d  call    ?LogEvent@WEB_ADMIN_SERVICE@@QEAAXKGQEAPEBGK@Z; WEB_ADMIN_SERVICE::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x18002d952  mov     [rbx+18h], r13d
0x18002d956  mov     rax, [rsp+2F0h+var_2B0]
0x18002d95b  lea     rcx, [rbp+1F0h+var_248]
0x18002d95f  mov     [rbx+3E0h], rax
0x18002d966  mov     [rsp+2F0h+var_2B0], r13
0x18002d96b  call    cs:__imp_?Increment@CLKRHashTable_Iterator@@QEAA_NXZ; CLKRHashTable_Iterator::Increment(void)
0x18002d971  mov     rcx, [r15+18h]
0x18002d975  lea     rdx, [rbp+1F0h+var_270]
0x18002d979  add     rcx, 8
0x18002d97d  call    cs:__imp_?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ; CLKRHashTable::End(void)
0x18002d983  mov     rdx, rax
0x18002d986  lea     rcx, [rsp+2F0h+var_2A8]
0x18002d98b  call    cs:__imp_??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z; CLKRHashTable_Iterator::CLKRHashTable_Iterator(CLKRHashTable_Iterator const &)
0x18002d991  lea     rcx, [rbp+1F0h+var_270]
0x18002d995  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x18002d99b  lea     rdx, [rsp+2F0h+var_2A8]
0x18002d9a0  lea     rcx, [rbp+1F0h+var_248]
0x18002d9a4  call    cs:__imp_??9CLKRHashTable_Iterator@@QEBA_NAEBV0@@Z; CLKRHashTable_Iterator::operator!=(CLKRHashTable_Iterator const &)
0x18002d9aa  lea     rcx, [rsp+2F0h+var_2A8]
0x18002d9af  mov     bl, al
0x18002d9b1  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x18002d9b7  test    bl, bl
0x18002d9b9  jnz     loc_18002D8AB
0x18002d9bf  lea     rcx, [rbp+1F0h+var_248]
0x18002d9c3  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x18002d9c9  mov     rcx, [r15+28h]
0x18002d9cd  lea     rdx, [rbp+1F0h+var_210]
0x18002d9d1  add     rcx, 8
0x18002d9d5  mov     rsi, r13
0x18002d9d8  call    cs:__imp_?Begin@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ; CLKRHashTable::Begin(void)
0x18002d9de  mov     rdx, rax
0x18002d9e1  lea     rcx, [rbp+1F0h+var_248]
0x18002d9e5  call    cs:__imp_??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z; CLKRHashTable_Iterator::CLKRHashTable_Iterator(CLKRHashTable_Iterator const &)
0x18002d9eb  lea     rcx, [rbp+1F0h+var_210]
0x18002d9ef  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x18002d9f5  jmp     loc_18002DB94
0x18002d9fa  movsx   rcx, [rbp+1F0h+var_22C]
0x18002d9ff  mov     rax, [rbp+1F0h+var_238]
0x18002da03  mov     rbx, [rax+rcx*8+18h]
0x18002da08  cmp     [rbx+18h], r13d
0x18002da0c  jz      loc_18002DB8A
0x18002da12  cmp     [rbx+1Ch], r13d
0x18002da16  jz      loc_18002DB8A
0x18002da1c  cmp     [rbx+14h], r13d
0x18002da20  jnz     loc_18002DB8A
0x18002da26  mov     eax, cs:g_dwDebugFlags
0x18002da2c  test    al, 3
0x18002da2e  setnz   cl
0x18002da31  bt      eax, 1Ch
0x18002da35  setb    al
0x18002da38  test    al, cl
0x18002da3a  jz      short loc_18002DA85
0x18002da3c  mov     rax, [rbx+98h]
0x18002da43  lea     r9, aConfigManagerC_0; "CONFIG_MANAGER::CrossValidateDataObject"...
0x18002da4a  mov     rcx, cs:g_pDebug
0x18002da51  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002da58  mov     [rsp+2F0h+var_2B8], rax
0x18002da5d  mov     r8d, 58Dh
0x18002da63  mov     eax, [rbx+68h]
0x18002da66  mov     [rsp+2F0h+var_2C0], eax
0x18002da6a  mov     rax, [rbx+50h]
0x18002da6e  mov     [rsp+2F0h+var_2C8], rax
0x18002da73  lea     rax, aApplicationSFo; "Application '%S' for site '%d' AppPoolI"...
0x18002da7a  mov     qword ptr [rsp+2F0h+var_2D0], rax
0x18002da7f  call    cs:__imp_PuDbgPrint
0x18002da85  mov     rdx, [rbx+98h]
0x18002da8c  lea     rcx, [rbp+1F0h+var_1D8]
0x18002da90  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18002da96  mov     edi, eax
0x18002da98  test    eax, eax
0x18002da9a  js      loc_18002DBFB
0x18002daa0  test    r12d, r12d
0x18002daa3  jz      short loc_18002DAEF
0x18002daa5  test    rsi, rsi
0x18002daa8  jnz     short loc_18002DAB3
0x18002daaa  mov     rsi, [rbx+98h]
0x18002dab1  jmp     short loc_18002DAEF
0x18002dab3  test    r14d, r14d
0x18002dab6  jz      short loc_18002DAEF
0x18002dab8  mov     rdx, [rbx+98h]; String2
0x18002dabf  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002dac3  mov     rcx, rax
0x18002dac6  inc     rcx
0x18002dac9  cmp     [rdx+rcx*2], r13w
0x18002dace  jnz     short loc_18002DAC6
0x18002dad0  inc     rax
0x18002dad3  cmp     [rsi+rax*2], r13w
0x18002dad8  jnz     short loc_18002DAD0
0x18002dada  cmp     rax, rcx
0x18002dadd  jnz     short loc_18002DAEC
0x18002dadf  mov     rcx, rsi; String1
0x18002dae2  call    cs:__imp__wcsicmp
0x18002dae8  test    eax, eax
0x18002daea  jz      short loc_18002DAEF
0x18002daec  mov     r14d, r13d
0x18002daef  mov     rcx, [r15+18h]
0x18002daf3  lea     r8, [rsp+2F0h+var_2B0]
0x18002daf8  add     rcx, 8
0x18002dafc  mov     [rsp+2F0h+var_2B0], r13
0x18002db01  lea     rdx, [rbp+1F0h+var_1E0]
0x18002db05  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x18002db0b  test    eax, eax
0x18002db0d  jz      short loc_18002DB15
0x18002db0f  mov     [rbx+18h], r13d
0x18002db13  jmp     short loc_18002DB5C
0x18002db15  mov     rcx, [rsp+2F0h+var_2B0]
0x18002db1a  cmp     [rcx+18h], r13d
0x18002db1e  jz      short loc_18002DB2C
0x18002db20  cmp     [rcx+1Ch], r13d
0x18002db24  jz      short loc_18002DB2C
0x18002db26  cmp     [rcx+14h], r13d
0x18002db2a  jz      short loc_18002DB30
0x18002db2c  mov     [rbx+18h], r13d
0x18002db30  test    r12d, r12d
0x18002db33  jz      short loc_18002DB3F
0x18002db35  mov     dword ptr [rcx+400h], 1
0x18002db3f  or      eax, 0FFFFFFFFh
0x18002db42  lock xadd [rcx+0Ch], eax
0x18002db47  cmp     eax, 1
0x18002db4a  jnz     short loc_18002DB5C
0x18002db4c  mov     rax, [rcx]
0x18002db4f  mov     edx, 1
0x18002db54  mov     rax, [rax]
0x18002db57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002db5c  cmp     [rbx+18h], r13d
0x18002db60  jnz     short loc_18002DB8A
0x18002db62  mov     rcx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x18002db69  mov     eax, [rbx+10h]
0x18002db6c  add     rcx, 628h; this
0x18002db73  mov     r9, [rbx+98h]; unsigned __int16 *
0x18002db7a  mov     r8, [rbx+50h]; unsigned __int16 *
0x18002db7e  mov     edx, [rbx+68h]; unsigned int
0x18002db81  mov     [rsp+2F0h+var_2D0], eax; int
0x18002db85  call    ?LogApplicationInvalidDueToMissingAppPoolId@WMS_ERROR_LOGGER@@QEAAXKPEBG0H@Z; WMS_ERROR_LOGGER::LogApplicationInvalidDueToMissingAppPoolId(ulong,ushort const *,ushort const *,int)
0x18002db8a  lea     rcx, [rbp+1F0h+var_248]
0x18002db8e  call    cs:__imp_?Increment@CLKRHashTable_Iterator@@QEAA_NXZ; CLKRHashTable_Iterator::Increment(void)
0x18002db94  mov     rcx, [r15+28h]
0x18002db98  lea     rdx, [rbp+1F0h+var_270]
0x18002db9c  add     rcx, 8
0x18002dba0  call    cs:__imp_?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ; CLKRHashTable::End(void)
0x18002dba6  mov     rdx, rax
0x18002dba9  lea     rcx, [rsp+2F0h+var_2A8]
0x18002dbae  call    cs:__imp_??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z; CLKRHashTable_Iterator::CLKRHashTable_Iterator(CLKRHashTable_Iterator const &)
0x18002dbb4  lea     rcx, [rbp+1F0h+var_270]
0x18002dbb8  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x18002dbbe  lea     rdx, [rsp+2F0h+var_2A8]
0x18002dbc3  lea     rcx, [rbp+1F0h+var_248]
0x18002dbc7  call    cs:__imp_??9CLKRHashTable_Iterator@@QEBA_NAEBV0@@Z; CLKRHashTable_Iterator::operator!=(CLKRHashTable_Iterator const &)
0x18002dbcd  lea     rcx, [rsp+2F0h+var_2A8]
0x18002dbd2  mov     bl, al
0x18002dbd4  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x18002dbda  test    bl, bl
0x18002dbdc  jnz     loc_18002D9FA
0x18002dbe2  lea     rcx, [rbp+1F0h+var_248]
0x18002dbe6  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x18002dbec  test    r14d, r14d
0x18002dbef  jnz     short loc_18002DC04
0x18002dbf1  mov     edi, 80070044h
0x18002dbf6  jmp     loc_18002E09F
0x18002dbfb  lea     rcx, [rbp+1F0h+var_248]
0x18002dbff  jmp     loc_18002E099
0x18002dc04  mov     rcx, [r15+20h]
0x18002dc08  lea     rdx, [rbp+1F0h+var_210]
0x18002dc0c  add     rcx, 8
0x18002dc10  call    cs:__imp_?Begin@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ; CLKRHashTable::Begin(void)
0x18002dc16  mov     rdx, rax
0x18002dc19  lea     rcx, [rbp+1F0h+var_270]
0x18002dc1d  call    cs:__imp_??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z; CLKRHashTable_Iterator::CLKRHashTable_Iterator(CLKRHashTable_Iterator const &)
0x18002dc23  lea     rcx, [rbp+1F0h+var_210]
0x18002dc27  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x18002dc2d  mov     rcx, [r15+20h]
0x18002dc31  lea     rdx, [rbp+1F0h+Buffer]
0x18002dc38  add     rcx, 8
0x18002dc3c  call    cs:__imp_?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ; CLKRHashTable::End(void)
0x18002dc42  mov     rdx, rax
0x18002dc45  lea     rcx, [rsp+2F0h+var_2A8]
0x18002dc4a  call    cs:__imp_??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z; CLKRHashTable_Iterator::CLKRHashTable_Iterator(CLKRHashTable_Iterator const &)
0x18002dc50  lea     rcx, [rbp+1F0h+Buffer]
0x18002dc57  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x18002dc5d  lea     rdx, [rsp+2F0h+var_2A8]
0x18002dc62  lea     rcx, [rbp+1F0h+var_270]
0x18002dc66  call    cs:__imp_??9CLKRHashTable_Iterator@@QEBA_NAEBV0@@Z; CLKRHashTable_Iterator::operator!=(CLKRHashTable_Iterator const &)
0x18002dc6c  lea     rcx, [rsp+2F0h+var_2A8]
0x18002dc71  mov     bl, al
0x18002dc73  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x18002dc79  mov     r12d, 1
0x18002dc7f  jmp     loc_18002DE88
0x18002dc84  movsx   rcx, [rbp+1F0h+var_254]
0x18002dc89  mov     rax, [rbp+1F0h+var_260]
0x18002dc8d  mov     rbx, [rax+rcx*8+18h]
0x18002dc92  cmp     [rbx+18h], r13d
0x18002dc96  jz      loc_18002DE32
0x18002dc9c  cmp     [rbx+1Ch], r13d
0x18002dca0  jz      loc_18002DE32
0x18002dca6  cmp     [rbx+14h], r13d
0x18002dcaa  jnz     loc_18002DE32
0x18002dcb0  mov     esi, [rbx+30h]
0x18002dcb3  lea     rdx, asc_180065774; "/"
0x18002dcba  lea     rcx, [rbp+1F0h+var_198]
  ... truncated ...
```
