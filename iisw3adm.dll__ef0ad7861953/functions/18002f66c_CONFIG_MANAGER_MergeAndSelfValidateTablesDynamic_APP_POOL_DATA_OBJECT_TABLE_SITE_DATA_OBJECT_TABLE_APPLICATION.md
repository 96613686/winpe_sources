# CONFIG_MANAGER::MergeAndSelfValidateTablesDynamic(APP_POOL_DATA_OBJECT_TABLE *,SITE_DATA_OBJECT_TABLE *,APPLICATION_DATA_OBJECT_TABLE *,GLOBAL_DATA_STORE *,PROTOCOL_DATA_OBJECT_TABLE *)

- ea: `0x18002f66c`
- end: `0x18002fa26`
- name: `?MergeAndSelfValidateTablesDynamic@CONFIG_MANAGER@@AEAAJPEAVAPP_POOL_DATA_OBJECT_TABLE@@PEAVSITE_DATA_OBJECT_TABLE@@PEAVAPPLICATION_DATA_OBJECT_TABLE@@PEAVGLOBAL_DATA_STORE@@PEAVPROTOCOL_DATA_OBJECT_TABLE@@@Z`
- size: `954`
- prototype: `__int64 __fastcall(CONFIG_MANAGER *__hidden this, struct APP_POOL_DATA_OBJECT_TABLE *, struct SITE_DATA_OBJECT_TABLE *, struct APPLICATION_DATA_OBJECT_TABLE *, struct GLOBAL_DATA_STORE *, struct PROTOCOL_DATA_OBJECT_TABLE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002e1c0`

## callees

- `0x18002f66c`
- `0x18003bd4c`
- `0x18003c40c`
- `0x180061060`
- `0x180062010`

## import_xrefs

- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18002f75e`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18002f76d`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18002f807`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18002f817`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18002f8c5`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18002f8d5`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18002f9b2`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18002f9c2`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18002f75e`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18002f76d`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18002f807`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18002f817`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18002f8c5`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18002f8d5`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18002f9b2`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18002f9c2`
- `iisutil!PuDbgPrint` at `0x18002f79a`
- `iisutil!PuDbgPrint` at `0x18002f844`
- `iisutil!PuDbgPrint` at `0x18002f902`
- `iisutil!PuDbgPrint` at `0x18002f9ef`
- `iisutil!PuDbgPrint` at `0x18002f79a`
- `iisutil!PuDbgPrint` at `0x18002f844`
- `iisutil!PuDbgPrint` at `0x18002f902`
- `iisutil!PuDbgPrint` at `0x18002f9ef`
- `iisutil!PuDbgPrintError` at `0x18002f712`
- `iisutil!PuDbgPrintError` at `0x18002f712`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x18002f6ba`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x18002f6ba`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18002f9fa`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18002f9fa`

## string_xrefs

- `0x18002f6fb`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\config_manager.cxx`
- `0x18002f744`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\config_manager.cxx`
- `0x18002f78e`: `Size of Pool Orig Table = %d, Temp Table %d\n`
- `0x18002f838`: `Size of site Orig Table = %d, Temp Table %d\n`
- `0x18002f8f6`: `Size of app Orig Table = %d, Temp Table %d\n`
- `0x18002f97d`: `Failed to merge the protocol data\n`
- `0x18002f9e3`: `Size of Protocol Orig Table = %d, Temp Table %d\n`
- `0x18002f6f4`: `CONFIG_MANAGER::MergeAndSelfValidateTablesDynamic`
- `0x18002f73d`: `CONFIG_MANAGER::MergeAndSelfValidateTablesDynamic`

## pseudocode

```c
__int64 __fastcall CONFIG_MANAGER::MergeAndSelfValidateTablesDynamic(
        CONFIG_MANAGER *this,
        struct APP_POOL_DATA_OBJECT_TABLE *a2,
        struct SITE_DATA_OBJECT_TABLE *a3,
        struct APPLICATION_DATA_OBJECT_TABLE *a4,
        struct GLOBAL_DATA_STORE *a5,
        struct PROTOCOL_DATA_OBJECT_TABLE *a6)
{
  GLOBAL_DATA_STORE *v9; // rcx
  int v10; // edi
  const char *v11; // rax
  __int64 v12; // r8
  _QWORD *v13; // r15
  unsigned int v14; // ebx
  unsigned int v15; // eax
  unsigned int v16; // ebx
  unsigned int v17; // eax
  __int64 v18; // rcx
  unsigned int v19; // ebx
  unsigned int v20; // eax
  unsigned int v21; // ebx
  unsigned int v22; // eax
  __int128 v25; // [rsp+50h] [rbp-98h] BYREF
  _BYTE v26[56]; // [rsp+60h] [rbp-88h] BYREF

  MULTISZ::MULTISZ((MULTISZ *)v26);
  v9 = (GLOBAL_DATA_STORE *)*((_QWORD *)this + 6);
  v25 = 0;
  v10 = GLOBAL_DATA_STORE::MergeTable(v9, a5);
  if ( v10 >= 0 )
  {
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 6) + 8LL) + 16LL))(*(_QWORD *)(*((_QWORD *)this + 6) + 8LL));
    v13 = (_QWORD *)((char *)this + 24);
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x10000000) != 0 )
    {
      v14 = CLKRHashTable::Size((struct APP_POOL_DATA_OBJECT_TABLE *)((char *)a2 + 8));
      v15 = CLKRHashTable::Size((CLKRHashTable *)(*v13 + 8LL));
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_manager.cxx",
        2910,
        "CONFIG_MANAGER::MergeAndSelfValidateTablesDynamic",
        "Size of Pool Orig Table = %d, Temp Table %d\n",
        v15,
        v14);
    }
    v10 = (*(__int64 (__fastcall **)(_QWORD, struct SITE_DATA_OBJECT_TABLE *, _QWORD, _QWORD))(**((_QWORD **)this + 4)
                                                                                             + 8LL))(
            *((_QWORD *)this + 4),
            a3,
            0,
            0);
    if ( v10 < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) == 0 )
        goto LABEL_25;
      v11 = "Failed to merge the site data\n";
      v12 = 2926;
      goto LABEL_4;
    }
    DATA_OBJECT_TABLE::PerformSelfValidation(*((DATA_OBJECT_TABLE **)this + 4));
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x10000000) != 0 )
    {
      v16 = CLKRHashTable::Size((struct SITE_DATA_OBJECT_TABLE *)((char *)a3 + 8));
      v17 = CLKRHashTable::Size((CLKRHashTable *)(*((_QWORD *)this + 4) + 8LL));
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_manager.cxx",
        2939,
        "CONFIG_MANAGER::MergeAndSelfValidateTablesDynamic",
        "Size of site Orig Table = %d, Temp Table %d\n",
        v17,
        v16);
    }
    v18 = *((_QWORD *)this + 5);
    *(_QWORD *)&v25 = *((_QWORD *)this + 4);
    *((_QWORD *)&v25 + 1) = *v13;
    v10 = (*(__int64 (__fastcall **)(__int64, struct APPLICATION_DATA_OBJECT_TABLE *, __int128 *, _BYTE *))(*(_QWORD *)v18 + 8LL))(
            v18,
            a4,
            &v25,
            v26);
    if ( v10 < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) == 0 )
        goto LABEL_25;
      v11 = "Failed to merge the application data\n";
      v12 = 2957;
      goto LABEL_4;
    }
    DATA_OBJECT_TABLE::PerformSelfValidation(*((DATA_OBJECT_TABLE **)this + 5));
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x10000000) != 0 )
    {
      v19 = CLKRHashTable::Size((struct APPLICATION_DATA_OBJECT_TABLE *)((char *)a4 + 8));
      v20 = CLKRHashTable::Size((CLKRHashTable *)(*((_QWORD *)this + 5) + 8LL));
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_manager.cxx",
        2970,
        "CONFIG_MANAGER::MergeAndSelfValidateTablesDynamic",
        "Size of app Orig Table = %d, Temp Table %d\n",
        v20,
        v19);
    }
    v10 = (*(__int64 (__fastcall **)(_QWORD, struct APP_POOL_DATA_OBJECT_TABLE *, _BYTE *, _QWORD))(*(_QWORD *)*v13 + 8LL))(
            *v13,
            a2,
            v26,
            0);
    if ( v10 < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) == 0 )
        goto LABEL_25;
      v11 = "Failed to merge the app pool data\n";
      v12 = 2985;
      goto LABEL_4;
    }
    DATA_OBJECT_TABLE::PerformSelfValidation(*((DATA_OBJECT_TABLE **)this + 3));
    v10 = (*(__int64 (__fastcall **)(_QWORD, struct PROTOCOL_DATA_OBJECT_TABLE *, _QWORD, _QWORD))(**((_QWORD **)this + 7)
                                                                                                 + 8LL))(
            *((_QWORD *)this + 7),
            a6,
            0,
            0);
    if ( v10 < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) == 0 )
        goto LABEL_25;
      v11 = "Failed to merge the protocol data\n";
      v12 = 3004;
      goto LABEL_4;
    }
    DATA_OBJECT_TABLE::PerformSelfValidation(*((DATA_OBJECT_TABLE **)this + 7));
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x10000000) != 0 )
    {
      v21 = CLKRHashTable::Size((struct PROTOCOL_DATA_OBJECT_TABLE *)((char *)a6 + 8));
      v22 = CLKRHashTable::Size((CLKRHashTable *)(*((_QWORD *)this + 7) + 8LL));
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_manager.cxx",
        3018,
        "CONFIG_MANAGER::MergeAndSelfValidateTablesDynamic",
        "Size of Protocol Orig Table = %d, Temp Table %d\n",
        v22,
        v21);
    }
  }
  else if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    v11 = "Failed to merge the global data\n";
    v12 = 2895;
LABEL_4:
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_manager.cxx",
      v12,
      "CONFIG_MANAGER::MergeAndSelfValidateTablesDynamic",
      v10,
      v11);
  }
LABEL_25:
  MULTISZ::~MULTISZ((MULTISZ *)v26);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18002f66c  push    rbx
0x18002f66e  push    rbp
0x18002f66f  push    rsi
0x18002f670  push    rdi
0x18002f671  push    r12
0x18002f673  push    r13
0x18002f675  push    r14
0x18002f677  push    r15
0x18002f679  sub     rsp, 0A8h
0x18002f680  mov     rax, cs:__security_cookie
0x18002f687  xor     rax, rsp
0x18002f68a  mov     [rsp+0E8h+var_50], rax
0x18002f692  mov     rax, [rsp+0E8h+arg_28]
0x18002f69a  mov     r14, rcx
0x18002f69d  mov     rbx, [rsp+0E8h+arg_20]
0x18002f6a5  lea     rcx, [rsp+0E8h+var_88]
0x18002f6aa  mov     [rsp+0E8h+var_A0], rax
0x18002f6af  mov     r13, r8
0x18002f6b2  mov     [rsp+0E8h+var_A8], r9
0x18002f6b7  mov     r12, rdx
0x18002f6ba  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x18002f6c0  mov     rcx, [r14+30h]; this
0x18002f6c4  xorps   xmm0, xmm0
0x18002f6c7  mov     rdx, rbx; struct GLOBAL_DATA_STORE *
0x18002f6ca  movups  [rsp+0E8h+var_98], xmm0
0x18002f6cf  call    ?MergeTable@GLOBAL_DATA_STORE@@QEAAJPEAV1@@Z; GLOBAL_DATA_STORE::MergeTable(GLOBAL_DATA_STORE *)
0x18002f6d4  mov     edi, eax
0x18002f6d6  test    eax, eax
0x18002f6d8  jns     short loc_18002F71D
0x18002f6da  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002f6e1  jz      loc_18002F9F5
0x18002f6e7  lea     rax, aFailedToMergeT_2; "Failed to merge the global data\n"
0x18002f6ee  mov     r8d, 0B4Fh
0x18002f6f4  lea     r9, aConfigManagerM_0; "CONFIG_MANAGER::MergeAndSelfValidateTab"...
0x18002f6fb  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002f702  mov     rcx, cs:g_pDebug
0x18002f709  mov     [rsp+0E8h+var_C0], rax
0x18002f70e  mov     dword ptr [rsp+0E8h+var_C8], edi
0x18002f712  call    cs:__imp_PuDbgPrintError
0x18002f718  jmp     loc_18002F9F5
0x18002f71d  mov     rax, [r14+30h]
0x18002f721  mov     rcx, [rax+8]
0x18002f725  mov     rax, [rcx]
0x18002f728  mov     rax, [rax+10h]
0x18002f72c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f731  mov     eax, cs:g_dwDebugFlags
0x18002f737  lea     r15, [r14+18h]
0x18002f73b  test    al, 3
0x18002f73d  lea     rsi, aConfigManagerM_0; "CONFIG_MANAGER::MergeAndSelfValidateTab"...
0x18002f744  lea     rbp, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002f74b  setnz   cl
0x18002f74e  bt      eax, 1Ch
0x18002f752  setb    al
0x18002f755  test    al, cl
0x18002f757  jz      short loc_18002F7A0
0x18002f759  lea     rcx, [r12+8]
0x18002f75e  call    cs:__imp_?Size@CLKRHashTable@@QEBAKXZ; CLKRHashTable::Size(void)
0x18002f764  mov     rcx, [r15]
0x18002f767  mov     ebx, eax
0x18002f769  add     rcx, 8
0x18002f76d  call    cs:__imp_?Size@CLKRHashTable@@QEBAKXZ; CLKRHashTable::Size(void)
0x18002f773  mov     rcx, cs:g_pDebug
0x18002f77a  mov     r9, rsi
0x18002f77d  mov     [rsp+0E8h+var_B8], ebx
0x18002f781  mov     r8d, 0B5Eh
0x18002f787  mov     dword ptr [rsp+0E8h+var_C0], eax
0x18002f78b  mov     rdx, rbp
0x18002f78e  lea     rax, aSizeOfPoolOrig; "Size of Pool Orig Table = %d, Temp Tabl"...
0x18002f795  mov     [rsp+0E8h+var_C8], rax
0x18002f79a  call    cs:__imp_PuDbgPrint
0x18002f7a0  mov     rcx, [r14+20h]
0x18002f7a4  xor     r9d, r9d
0x18002f7a7  xor     r8d, r8d
0x18002f7aa  mov     rdx, r13
0x18002f7ad  mov     rax, [rcx]
0x18002f7b0  mov     rax, [rax+8]
0x18002f7b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f7b9  mov     edi, eax
0x18002f7bb  test    eax, eax
0x18002f7bd  jns     short loc_18002F7E4
0x18002f7bf  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002f7c6  jz      loc_18002F9F5
0x18002f7cc  lea     rax, aFailedToMergeT_0; "Failed to merge the site data\n"
0x18002f7d3  mov     r8d, 0B6Eh
0x18002f7d9  mov     r9, rsi
0x18002f7dc  mov     rdx, rbp
0x18002f7df  jmp     loc_18002F702
0x18002f7e4  mov     rcx, [r14+20h]; this
0x18002f7e8  call    ?PerformSelfValidation@DATA_OBJECT_TABLE@@QEAAXXZ; DATA_OBJECT_TABLE::PerformSelfValidation(void)
0x18002f7ed  mov     eax, cs:g_dwDebugFlags
0x18002f7f3  test    al, 3
0x18002f7f5  setnz   cl
0x18002f7f8  bt      eax, 1Ch
0x18002f7fc  setb    al
0x18002f7ff  test    al, cl
0x18002f801  jz      short loc_18002F84A
0x18002f803  lea     rcx, [r13+8]
0x18002f807  call    cs:__imp_?Size@CLKRHashTable@@QEBAKXZ; CLKRHashTable::Size(void)
0x18002f80d  mov     rcx, [r14+20h]
0x18002f811  mov     ebx, eax
0x18002f813  add     rcx, 8
0x18002f817  call    cs:__imp_?Size@CLKRHashTable@@QEBAKXZ; CLKRHashTable::Size(void)
0x18002f81d  mov     rcx, cs:g_pDebug
0x18002f824  mov     r9, rsi
0x18002f827  mov     [rsp+0E8h+var_B8], ebx
0x18002f82b  mov     r8d, 0B7Bh
0x18002f831  mov     dword ptr [rsp+0E8h+var_C0], eax
0x18002f835  mov     rdx, rbp
0x18002f838  lea     rax, aSizeOfSiteOrig; "Size of site Orig Table = %d, Temp Tabl"...
0x18002f83f  mov     [rsp+0E8h+var_C8], rax
0x18002f844  call    cs:__imp_PuDbgPrint
0x18002f84a  mov     rax, [r14+20h]
0x18002f84e  lea     r9, [rsp+0E8h+var_88]
0x18002f853  mov     rcx, [r14+28h]
0x18002f857  lea     r8, [rsp+0E8h+var_98]
0x18002f85c  mov     rbx, [rsp+0E8h+var_A8]
0x18002f861  mov     qword ptr [rsp+0E8h+var_98], rax
0x18002f866  mov     rdx, rbx
0x18002f869  mov     rax, [r15]
0x18002f86c  mov     qword ptr [rsp+0E8h+var_98+8], rax
0x18002f871  mov     rax, [rcx]
0x18002f874  mov     rax, [rax+8]
0x18002f878  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f87d  mov     edi, eax
0x18002f87f  test    eax, eax
0x18002f881  jns     short loc_18002F8A2
0x18002f883  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002f88a  jz      loc_18002F9F5
0x18002f890  lea     rax, aFailedToMergeT; "Failed to merge the application data\n"
0x18002f897  mov     r8d, 0B8Dh
0x18002f89d  jmp     loc_18002F7D9
0x18002f8a2  mov     rcx, [r14+28h]; this
0x18002f8a6  call    ?PerformSelfValidation@DATA_OBJECT_TABLE@@QEAAXXZ; DATA_OBJECT_TABLE::PerformSelfValidation(void)
0x18002f8ab  mov     eax, cs:g_dwDebugFlags
0x18002f8b1  test    al, 3
0x18002f8b3  setnz   cl
0x18002f8b6  bt      eax, 1Ch
0x18002f8ba  setb    al
0x18002f8bd  test    al, cl
0x18002f8bf  jz      short loc_18002F908
0x18002f8c1  lea     rcx, [rbx+8]
0x18002f8c5  call    cs:__imp_?Size@CLKRHashTable@@QEBAKXZ; CLKRHashTable::Size(void)
0x18002f8cb  mov     rcx, [r14+28h]
0x18002f8cf  mov     ebx, eax
0x18002f8d1  add     rcx, 8
0x18002f8d5  call    cs:__imp_?Size@CLKRHashTable@@QEBAKXZ; CLKRHashTable::Size(void)
0x18002f8db  mov     rcx, cs:g_pDebug
0x18002f8e2  mov     r9, rsi
0x18002f8e5  mov     [rsp+0E8h+var_B8], ebx
0x18002f8e9  mov     r8d, 0B9Ah
0x18002f8ef  mov     dword ptr [rsp+0E8h+var_C0], eax
0x18002f8f3  mov     rdx, rbp
0x18002f8f6  lea     rax, aSizeOfAppOrigT; "Size of app Orig Table = %d, Temp Table"...
0x18002f8fd  mov     [rsp+0E8h+var_C8], rax
0x18002f902  call    cs:__imp_PuDbgPrint
0x18002f908  mov     rcx, [r15]
0x18002f90b  lea     r8, [rsp+0E8h+var_88]
0x18002f910  xor     r9d, r9d
0x18002f913  mov     rdx, r12
0x18002f916  mov     rax, [rcx]
0x18002f919  mov     rax, [rax+8]
0x18002f91d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f922  mov     edi, eax
0x18002f924  test    eax, eax
0x18002f926  jns     short loc_18002F947
0x18002f928  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002f92f  jz      loc_18002F9F5
0x18002f935  lea     rax, aFailedToMergeT_1; "Failed to merge the app pool data\n"
0x18002f93c  mov     r8d, 0BA9h
0x18002f942  jmp     loc_18002F7D9
0x18002f947  mov     rcx, [r14+18h]; this
0x18002f94b  call    ?PerformSelfValidation@DATA_OBJECT_TABLE@@QEAAXXZ; DATA_OBJECT_TABLE::PerformSelfValidation(void)
0x18002f950  mov     rcx, [r14+38h]
0x18002f954  xor     r9d, r9d
0x18002f957  mov     rbx, [rsp+0E8h+var_A0]
0x18002f95c  xor     r8d, r8d
0x18002f95f  mov     rdx, rbx
0x18002f962  mov     rax, [rcx]
0x18002f965  mov     rax, [rax+8]
0x18002f969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f96e  mov     edi, eax
0x18002f970  test    eax, eax
0x18002f972  jns     short loc_18002F98F
0x18002f974  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002f97b  jz      short loc_18002F9F5
0x18002f97d  lea     rax, aFailedToMergeT_3; "Failed to merge the protocol data\n"
0x18002f984  mov     r8d, 0BBCh
0x18002f98a  jmp     loc_18002F7D9
0x18002f98f  mov     rcx, [r14+38h]; this
0x18002f993  call    ?PerformSelfValidation@DATA_OBJECT_TABLE@@QEAAXXZ; DATA_OBJECT_TABLE::PerformSelfValidation(void)
0x18002f998  mov     eax, cs:g_dwDebugFlags
0x18002f99e  test    al, 3
0x18002f9a0  setnz   cl
0x18002f9a3  bt      eax, 1Ch
0x18002f9a7  setb    al
0x18002f9aa  test    al, cl
0x18002f9ac  jz      short loc_18002F9F5
0x18002f9ae  lea     rcx, [rbx+8]
0x18002f9b2  call    cs:__imp_?Size@CLKRHashTable@@QEBAKXZ; CLKRHashTable::Size(void)
0x18002f9b8  mov     rcx, [r14+38h]
0x18002f9bc  mov     ebx, eax
0x18002f9be  add     rcx, 8
0x18002f9c2  call    cs:__imp_?Size@CLKRHashTable@@QEBAKXZ; CLKRHashTable::Size(void)
0x18002f9c8  mov     rcx, cs:g_pDebug
0x18002f9cf  mov     r9, rsi
0x18002f9d2  mov     [rsp+0E8h+var_B8], ebx
0x18002f9d6  mov     r8d, 0BCAh
0x18002f9dc  mov     dword ptr [rsp+0E8h+var_C0], eax
0x18002f9e0  mov     rdx, rbp
0x18002f9e3  lea     rax, aSizeOfProtocol; "Size of Protocol Orig Table = %d, Temp "...
0x18002f9ea  mov     [rsp+0E8h+var_C8], rax
0x18002f9ef  call    cs:__imp_PuDbgPrint
0x18002f9f5  lea     rcx, [rsp+0E8h+var_88]
0x18002f9fa  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x18002fa00  mov     eax, edi
0x18002fa02  mov     rcx, [rsp+0E8h+var_50]
0x18002fa0a  xor     rcx, rsp; StackCookie
0x18002fa0d  call    __security_check_cookie
0x18002fa12  add     rsp, 0A8h
0x18002fa19  pop     r15
0x18002fa1b  pop     r14
0x18002fa1d  pop     r13
0x18002fa1f  pop     r12
0x18002fa21  pop     rdi
0x18002fa22  pop     rsi
0x18002fa23  pop     rbp
0x18002fa24  pop     rbx
0x18002fa25  retn
```
