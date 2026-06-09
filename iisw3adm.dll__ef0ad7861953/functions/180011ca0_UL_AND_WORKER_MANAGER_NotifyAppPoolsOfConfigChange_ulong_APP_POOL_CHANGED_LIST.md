# UL_AND_WORKER_MANAGER::NotifyAppPoolsOfConfigChange(ulong,APP_POOL_CHANGED_LIST *)

- ea: `0x180011ca0`
- end: `0x180011f15`
- name: `?NotifyAppPoolsOfConfigChange@UL_AND_WORKER_MANAGER@@QEAAXKPEAVAPP_POOL_CHANGED_LIST@@@Z`
- size: `629`
- prototype: `void __fastcall(UL_AND_WORKER_MANAGER *__hidden this, unsigned int, struct APP_POOL_CHANGED_LIST *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002fa2c`

## callees

- `0x180011ca0`
- `0x180018a9c`

## import_xrefs

- `iisutil!?Begin@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x180011d6e`
- `iisutil!?Begin@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x180011d6e`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180011e9a`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180011e9a`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x180011d7b`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x180011dc4`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x180011d7b`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x180011dc4`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180011d85`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180011dce`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180011de8`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180011df6`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180011d85`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180011dce`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180011de8`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180011df6`
- `iisutil!?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x180011db7`
- `iisutil!?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x180011db7`
- `iisutil!PuDbgPrint` at `0x180011d06`
- `iisutil!PuDbgPrint` at `0x180011d50`
- `iisutil!PuDbgPrint` at `0x180011e74`
- `iisutil!PuDbgPrint` at `0x180011d06`
- `iisutil!PuDbgPrint` at `0x180011d50`
- `iisutil!PuDbgPrint` at `0x180011e74`
- `iisutil!PuDbgPrintError` at `0x180011edc`
- `iisutil!PuDbgPrintError` at `0x180011edc`
- `iisutil!??9CLKRHashTable_Iterator@@QEBA_NAEBV0@@Z` at `0x180011ddc`
- `iisutil!??9CLKRHashTable_Iterator@@QEBA_NAEBV0@@Z` at `0x180011ddc`
- `iisutil!?Increment@CLKRHashTable_Iterator@@QEAA_NXZ` at `0x180011daa`
- `iisutil!?Increment@CLKRHashTable_Iterator@@QEAA_NXZ` at `0x180011daa`

## string_xrefs

- `0x180011cfa`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\ul_and_worker_manager.cxx`
- `0x180011d2c`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\ul_and_worker_manager.cxx`
- `0x180011e56`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\ul_and_worker_manager.cxx`
- `0x180011ed5`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\ul_and_worker_manager.cxx`
- `0x180011ce9`: `UL_AND_WORKER_MANAGER::NotifyAppPoolsOfConfigChange`
- `0x180011d1e`: `UL_AND_WORKER_MANAGER::NotifyAppPoolsOfConfigChange`
- `0x180011e4a`: `UL_AND_WORKER_MANAGER::NotifyAppPoolsOfConfigChange`
- `0x180011ec0`: `UL_AND_WORKER_MANAGER::NotifyAppPoolsOfConfigChange`
- `0x180011eb4`: `Looking up app pool to invalidate its config has failed\n`

## pseudocode

```c
void __fastcall UL_AND_WORKER_MANAGER::NotifyAppPoolsOfConfigChange(
        UL_AND_WORKER_MANAGER *this,
        unsigned int a2,
        struct APP_POOL_CHANGED_LIST *a3)
{
  char v3; // al
  unsigned int v4; // esi
  char *v8; // r14
  const struct CLKRHashTable_Iterator *v9; // rax
  const struct CLKRHashTable_Iterator *v10; // rax
  char v11; // bl
  __int64 i; // rbx
  __int64 v13; // rsi
  const wchar_t *v14; // rax
  bool v15; // zf
  const OLECHAR *v16; // rdx
  _BYTE v17[16]; // [rsp+40h] [rbp-39h] BYREF
  __int64 v18; // [rsp+50h] [rbp-29h]
  __int16 v19; // [rsp+5Ch] [rbp-1Dh]
  _BYTE v20[40]; // [rsp+68h] [rbp-11h] BYREF
  _BYTE v21[48]; // [rsp+90h] [rbp+17h] BYREF
  APP_POOL *v22; // [rsp+E0h] [rbp+67h] BYREF

  v3 = g_dwDebugFlags;
  v4 = 0;
  if ( g_dwDebugFlags >= 0 )
  {
    if ( !a3 )
      goto LABEL_10;
    goto LABEL_8;
  }
  if ( (g_dwDebugFlags & 3) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\ul_and_worker_manager.cxx",
      3366,
      "UL_AND_WORKER_MANAGER::NotifyAppPoolsOfConfigChange",
      "Notify App Pools of Change, New Change Number = %d, pChangedList = 0x%X\n",
      a2,
      (_DWORD)a3);
    v3 = g_dwDebugFlags;
  }
  if ( a3 )
  {
    if ( (v3 & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\ul_and_worker_manager.cxx",
        3375,
        "UL_AND_WORKER_MANAGER::NotifyAppPoolsOfConfigChange",
        "Change Count = %d, ChangeState = %d\n\n",
        *((_DWORD *)a3 + 2),
        *((_DWORD *)a3 + 4));
LABEL_8:
    if ( *((_DWORD *)a3 + 4) )
      v4 = a2;
  }
LABEL_10:
  v8 = (char *)this + 16;
  v9 = (const struct CLKRHashTable_Iterator *)CLKRHashTable::Begin(v8, v21);
  CLKRHashTable_Iterator::CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v17, v9);
  CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v21);
  while ( 1 )
  {
    v10 = (const struct CLKRHashTable_Iterator *)CLKRHashTable::End(v8, v21);
    CLKRHashTable_Iterator::CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v20, v10);
    CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v21);
    v11 = CLKRHashTable_Iterator::operator!=(v17, v20);
    CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v20);
    if ( !v11 )
      break;
    APP_POOL::NotifyConfigChanged(*(APP_POOL **)(v18 + 8LL * v19 + 24), v4, *((_DWORD *)a3 + 5));
    CLKRHashTable_Iterator::Increment((CLKRHashTable_Iterator *)v17);
  }
  CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v17);
  if ( a3 )
  {
    if ( *((_DWORD *)a3 + 4) == 2 )
    {
      for ( i = 0; (unsigned int)i < *((_DWORD *)a3 + 2); i = (unsigned int)(i + 1) )
      {
        v13 = *(_QWORD *)(*(_QWORD *)a3 + 8 * i);
        if ( (g_dwDebugFlags & 3) != 0 && g_dwDebugFlags < 0 )
        {
          v14 = &SourceString;
          if ( *(_QWORD *)(v13 + 16) )
            v14 = *(const wchar_t **)(v13 + 16);
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\ul_and_worker_manager.cxx",
            3411,
            "UL_AND_WORKER_MANAGER::NotifyAppPoolsOfConfigChange",
            "Changed App Pool = %S\n",
            v14);
        }
        v15 = *(_QWORD *)(v13 + 16) == 0;
        v16 = &SourceString;
        v22 = 0;
        if ( !v15 )
          v16 = *(const OLECHAR **)(v13 + 16);
        if ( (unsigned int)CLKRHashTable::FindKey(v8, v16, &v22) )
        {
          if ( (g_dwDebugFlags & 0xF) != 0 )
            PuDbgPrintError(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\ul_and_worker_manager.cxx",
              3426,
              "UL_AND_WORKER_MANAGER::NotifyAppPoolsOfConfigChange",
              -2147467259,
              "Looking up app pool to invalidate its config has failed\n");
        }
        else
        {
          APP_POOL::NotifyConfigChanged(v22, 0, 0);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180011ca0  mov     [rsp-8+arg_8], rbx
0x180011ca5  mov     [rsp-8+arg_10], rsi
0x180011caa  push    rbp
0x180011cab  push    rdi
0x180011cac  push    r14
0x180011cae  lea     rbp, [rsp-47h]
0x180011cb3  sub     rsp, 0C0h
0x180011cba  mov     eax, cs:g_dwDebugFlags
0x180011cc0  xor     esi, esi
0x180011cc2  mov     rdi, r8
0x180011cc5  mov     ebx, edx
0x180011cc7  mov     r14, rcx
0x180011cca  test    eax, eax
0x180011ccc  jns     loc_180011D58
0x180011cd2  test    al, 3
0x180011cd4  jz      short loc_180011D12
0x180011cd6  mov     rcx, cs:g_pDebug
0x180011cdd  lea     rax, aNotifyAppPools; "Notify App Pools of Change, New Change "...
0x180011ce4  mov     [rsp+0D0h+var_A0], r8
0x180011ce9  lea     r9, aUlAndWorkerMan_30; "UL_AND_WORKER_MANAGER::NotifyAppPoolsOf"...
0x180011cf0  mov     dword ptr [rsp+0D0h+var_A8], edx
0x180011cf4  mov     r8d, 0D26h
0x180011cfa  lea     rdx, aServercommonIn_68; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180011d01  mov     [rsp+0D0h+var_B0], rax
0x180011d06  call    cs:__imp_PuDbgPrint
0x180011d0c  mov     eax, cs:g_dwDebugFlags
0x180011d12  test    rdi, rdi
0x180011d15  jz      short loc_180011D63
0x180011d17  test    al, 3
0x180011d19  jz      short loc_180011D5D
0x180011d1b  mov     eax, [rdi+10h]
0x180011d1e  lea     r9, aUlAndWorkerMan_30; "UL_AND_WORKER_MANAGER::NotifyAppPoolsOf"...
0x180011d25  mov     rcx, cs:g_pDebug
0x180011d2c  lea     rdx, aServercommonIn_68; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180011d33  mov     dword ptr [rsp+0D0h+var_A0], eax
0x180011d37  mov     r8d, 0D2Fh
0x180011d3d  mov     eax, [rdi+8]
0x180011d40  mov     dword ptr [rsp+0D0h+var_A8], eax
0x180011d44  lea     rax, aChangeCountDCh; "Change Count = %d, ChangeState = %d\n\n"
0x180011d4b  mov     [rsp+0D0h+var_B0], rax
0x180011d50  call    cs:__imp_PuDbgPrint
0x180011d56  jmp     short loc_180011D5D
0x180011d58  test    rdi, rdi
0x180011d5b  jz      short loc_180011D63
0x180011d5d  cmp     [rdi+10h], esi
0x180011d60  cmovnz  esi, ebx
0x180011d63  add     r14, 10h
0x180011d67  lea     rdx, [rbp+57h+var_40]
0x180011d6b  mov     rcx, r14
0x180011d6e  call    cs:__imp_?Begin@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ; CLKRHashTable::Begin(void)
0x180011d74  mov     rdx, rax
0x180011d77  lea     rcx, [rbp+57h+var_90]
0x180011d7b  call    cs:__imp_??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z; CLKRHashTable_Iterator::CLKRHashTable_Iterator(CLKRHashTable_Iterator const &)
0x180011d81  lea     rcx, [rbp+57h+var_40]
0x180011d85  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x180011d8b  jmp     short loc_180011DB0
0x180011d8d  movsx   rax, [rbp+57h+var_74]
0x180011d92  mov     edx, esi; unsigned int
0x180011d94  mov     rcx, [rbp+57h+var_80]
0x180011d98  mov     r8d, [rdi+14h]; int
0x180011d9c  mov     rcx, [rcx+rax*8+18h]; this
0x180011da1  call    ?NotifyConfigChanged@APP_POOL@@QEAAXKH@Z; APP_POOL::NotifyConfigChanged(ulong,int)
0x180011da6  lea     rcx, [rbp+57h+var_90]
0x180011daa  call    cs:__imp_?Increment@CLKRHashTable_Iterator@@QEAA_NXZ; CLKRHashTable_Iterator::Increment(void)
0x180011db0  lea     rdx, [rbp+57h+var_40]
0x180011db4  mov     rcx, r14
0x180011db7  call    cs:__imp_?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ; CLKRHashTable::End(void)
0x180011dbd  mov     rdx, rax
0x180011dc0  lea     rcx, [rbp+57h+var_68]
0x180011dc4  call    cs:__imp_??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z; CLKRHashTable_Iterator::CLKRHashTable_Iterator(CLKRHashTable_Iterator const &)
0x180011dca  lea     rcx, [rbp+57h+var_40]
0x180011dce  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x180011dd4  lea     rdx, [rbp+57h+var_68]
0x180011dd8  lea     rcx, [rbp+57h+var_90]
0x180011ddc  call    cs:__imp_??9CLKRHashTable_Iterator@@QEBA_NAEBV0@@Z; CLKRHashTable_Iterator::operator!=(CLKRHashTable_Iterator const &)
0x180011de2  lea     rcx, [rbp+57h+var_68]
0x180011de6  mov     bl, al
0x180011de8  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x180011dee  test    bl, bl
0x180011df0  jnz     short loc_180011D8D
0x180011df2  lea     rcx, [rbp+57h+var_90]
0x180011df6  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x180011dfc  test    rdi, rdi
0x180011dff  jz      loc_180011EFD
0x180011e05  cmp     dword ptr [rdi+10h], 2
0x180011e09  jnz     loc_180011EFD
0x180011e0f  xor     ebx, ebx
0x180011e11  cmp     [rdi+8], ebx
0x180011e14  jbe     loc_180011EFD
0x180011e1a  mov     rax, [rdi]
0x180011e1d  mov     rsi, [rax+rbx*8]
0x180011e21  mov     eax, cs:g_dwDebugFlags
0x180011e27  test    al, 3
0x180011e29  setnz   cl
0x180011e2c  bt      eax, 1Fh
0x180011e30  setb    al
0x180011e33  test    al, cl
0x180011e35  jz      short loc_180011E7A
0x180011e37  cmp     qword ptr [rsi+10h], 0
0x180011e3c  lea     rax, SourceString
0x180011e43  mov     rcx, cs:g_pDebug
0x180011e4a  lea     r9, aUlAndWorkerMan_30; "UL_AND_WORKER_MANAGER::NotifyAppPoolsOf"...
0x180011e51  cmovnz  rax, [rsi+10h]
0x180011e56  lea     rdx, aServercommonIn_68; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180011e5d  mov     [rsp+0D0h+var_A8], rax
0x180011e62  mov     r8d, 0D53h
0x180011e68  lea     rax, aChangedAppPool; "Changed App Pool = %S\n"
0x180011e6f  mov     [rsp+0D0h+var_B0], rax
0x180011e74  call    cs:__imp_PuDbgPrint
0x180011e7a  cmp     qword ptr [rsi+10h], 0
0x180011e7f  lea     rdx, SourceString
0x180011e86  lea     r8, [rbp+57h+arg_0]
0x180011e8a  mov     [rbp+57h+arg_0], 0
0x180011e92  cmovnz  rdx, [rsi+10h]
0x180011e97  mov     rcx, r14
0x180011e9a  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x180011ea0  test    eax, eax
0x180011ea2  jz      short loc_180011EE4
0x180011ea4  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180011eab  jz      short loc_180011EF2
0x180011ead  mov     rcx, cs:g_pDebug
0x180011eb4  lea     rax, aLookingUpAppPo; "Looking up app pool to invalidate its c"...
0x180011ebb  mov     [rsp+0D0h+var_A8], rax
0x180011ec0  lea     r9, aUlAndWorkerMan_30; "UL_AND_WORKER_MANAGER::NotifyAppPoolsOf"...
0x180011ec7  mov     r8d, 0D62h
0x180011ecd  mov     dword ptr [rsp+0D0h+var_B0], 80004005h
0x180011ed5  lea     rdx, aServercommonIn_68; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180011edc  call    cs:__imp_PuDbgPrintError
0x180011ee2  jmp     short loc_180011EF2
0x180011ee4  mov     rcx, [rbp+57h+arg_0]; this
0x180011ee8  xor     r8d, r8d; int
0x180011eeb  xor     edx, edx; unsigned int
0x180011eed  call    ?NotifyConfigChanged@APP_POOL@@QEAAXKH@Z; APP_POOL::NotifyConfigChanged(ulong,int)
0x180011ef2  inc     ebx
0x180011ef4  cmp     ebx, [rdi+8]
0x180011ef7  jb      loc_180011E1A
0x180011efd  lea     r11, [rsp+0D0h+var_10]
0x180011f05  mov     rbx, [r11+28h]
0x180011f09  mov     rsi, [r11+30h]
0x180011f0d  mov     rsp, r11
0x180011f10  pop     r14
0x180011f12  pop     rdi
0x180011f13  pop     rbp
0x180011f14  retn
```
