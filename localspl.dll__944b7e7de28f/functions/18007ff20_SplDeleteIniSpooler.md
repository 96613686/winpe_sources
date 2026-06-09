# SplDeleteIniSpooler

- ea: `0x18007ff20`
- end: `0x180080201`
- name: `SplDeleteIniSpooler`
- size: `737`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, registry_config, loader_planting, installer_update`

## callers

- `0x1800770d4`
- `0x1800a1780`

## callees

- `0x180008520`
- `0x180008560`
- `0x180008730`
- `0x18001af1c`
- `0x180022990`
- `0x180024368`
- `0x180033734`
- `0x18003e984`
- `0x18003ea2c`
- `0x180041c7c`
- `0x18007df54`
- `0x18007edcc`
- `0x18007ff20`
- `0x180080210`
- `0x1800a7c68`
- `0x1800ab0d0`
- `0x1800ab884`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180080149`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180080149`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180080172`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180080172`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800800b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800800c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800800b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800800c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008012a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800801dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008012a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800801dd`
- `SPOOLSS!DllFreeSplStr` at `0x1800800fb`
- `SPOOLSS!DllFreeSplStr` at `0x18008010c`
- `SPOOLSS!DllFreeSplStr` at `0x180080119`
- `SPOOLSS!DllFreeSplStr` at `0x1800800fb`
- `SPOOLSS!DllFreeSplStr` at `0x18008010c`
- `SPOOLSS!DllFreeSplStr` at `0x180080119`
- `SPOOLSS!DllFreeSplMem` at `0x1800800e1`
- `SPOOLSS!DllFreeSplMem` at `0x1800800ea`
- `SPOOLSS!DllFreeSplMem` at `0x180080137`
- `SPOOLSS!DllFreeSplMem` at `0x1800800e1`
- `SPOOLSS!DllFreeSplMem` at `0x1800800ea`
- `SPOOLSS!DllFreeSplMem` at `0x180080137`
- `SPOOLSS!DllFreeSplMem` at `0x1800801fa`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x18007ff3f`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x18007ff3f`

## string_xrefs

- `0x18007ffd7`: `Deleted INISPOOLER %ws`
- `0x18008005c`: `Unable to delete port %ws. Handle %p, Status %x, Jobs %d`
- `0x18007ffde`: `SplDeleteIniSpooler`
- `0x180080075`: `SplDeleteIniSpooler`

## pseudocode

```c
__int64 __fastcall SplDeleteIniSpooler(__int64 a1)
{
  __int64 v2; // rcx
  _DWORD *v3; // r10
  __int64 v4; // rbp
  __int64 v5; // rbx
  __int64 v6; // rdi
  __int64 v7; // rcx
  __int64 v8; // rbx
  __int64 v9; // rbx
  __int64 v10; // rdi
  __int64 MonitorHandle; // rax
  __int64 v12; // rcx
  __int64 v13; // rbx
  HKEY v14; // rcx
  HKEY v15; // rcx
  _QWORD *v16; // rbx
  __int64 v17; // rcx
  unsigned int v18; // edx
  NPackageInstallLocalspl::TDriverStore *v19; // rcx
  unsigned int v20; // edx
  FilePool *v21; // rcx
  TValidataUserManageForm *v22; // rcx
  __int64 v24; // [rsp+20h] [rbp-38h]
  __int64 v25; // [rsp+28h] [rbp-30h]

  EnterSplSem(0);
  v2 = *(_QWORD *)(a1 + 376);
  if ( v2 )
  {
    DevCloseObjectQuery();
    *(_QWORD *)(a1 + 376) = 0;
    if ( !*(_DWORD *)(a1 + 16) || (SafeDecrementReference((unsigned int *)(a1 + 16)), !*v3) )
    {
      if ( (*(_DWORD *)(a1 + 168) & 0x8000) != 0 )
        SplDeleteSpooler(a1);
    }
  }
  v4 = *(_QWORD *)(a1 + 56);
  if ( v4 )
  {
    do
    {
      v5 = *(_QWORD *)(v4 + 56);
      v6 = *(_QWORD *)(v4 + 8);
      *(_QWORD *)(v4 + 56) = 0;
      LeaveSplSem(v2);
      LocalSpoolerTelemetry::WriteDbgTraceInfo(
        "ShutdownMonitors",
        L"Shutting down monitor %ws on %ws",
        *(_QWORD *)(v4 + 24),
        *(_QWORD *)(a1 + 24));
      (*(void (__fastcall **)(__int64))(v4 + 232))(v5);
      EnterSplSem(0);
      v4 = v6;
    }
    while ( v6 );
  }
  LocalSpoolerTelemetry::WriteDbgTraceInfo("SplDeleteIniSpooler", L"Deleted INISPOOLER %ws", *(_QWORD *)(a1 + 24));
  FreeStructurePointers(a1, 0, IniSpoolerOffsets);
  while ( *(_QWORD *)(a1 + 72) )
    DeleteIniForm(*(_QWORD *)(a1 + 72), a1);
  v7 = *(_QWORD *)(a1 + 48);
  if ( v7 != *((_QWORD *)pLocalIniSpooler + 6) && v7 )
  {
    do
    {
      v8 = *(_QWORD *)(v7 + 8);
      FreeIniEnvironment((struct _INIENVIRONMENT *)v7);
      v7 = v8;
    }
    while ( v8 );
  }
  v9 = *(_QWORD *)(a1 + 64);
  if ( v9 )
  {
    do
    {
      v10 = *(_QWORD *)(v9 + 8);
      if ( !(unsigned int)DeletePortEntry(v9) )
      {
        MonitorHandle = GetMonitorHandle(v9);
        LODWORD(v25) = *(_DWORD *)(v9 + 80);
        LODWORD(v24) = *(_DWORD *)(v9 + 48);
        LocalSpoolerTelemetry::WriteDbgTraceError(
          "SplDeleteIniSpooler",
          L"Unable to delete port %ws. Handle %p, Status %x, Jobs %d",
          *(_QWORD *)(v9 + 24),
          MonitorHandle,
          v24,
          v25);
      }
      v9 = v10;
    }
    while ( v10 );
  }
  v12 = *(_QWORD *)(a1 + 56);
  if ( v12 )
  {
    do
    {
      v13 = *(_QWORD *)(v12 + 8);
      if ( !*(_DWORD *)(v12 + 16) )
        FreeIniMonitor(v12);
      v12 = v13;
    }
    while ( v13 );
  }
  v14 = *(HKEY *)(a1 + 232);
  if ( v14 )
    RegCloseKey(v14);
  v15 = *(HKEY *)(a1 + 240);
  if ( v15 )
    RegCloseKey(v15);
  v16 = *(_QWORD **)(a1 + 264);
  if ( v16 )
  {
    if ( *v16 )
      DllFreeSplMem(*v16);
    DllFreeSplMem(v16);
  }
  DllFreeSplStr(*(_QWORD *)(*(_QWORD *)(a1 + 144) + 16LL));
  DllFreeSplStr(*(_QWORD *)(*(_QWORD *)(a1 + 144) + 40LL));
  DllFreeSplStr(*(_QWORD *)(a1 + 216));
  LocalFree(*(HLOCAL *)(*(_QWORD *)(a1 + 144) + 72LL));
  DllFreeSplMem(*(_QWORD *)(a1 + 144));
  LeaveSplSem(v17);
  EnterCriticalSection(&g_PackageLock);
  v19 = *(NPackageInstallLocalspl::TDriverStore **)(a1 + 65928);
  if ( v19 )
  {
    *(_QWORD *)(a1 + 65928) = 0;
    NPackageInstallLocalspl::TDriverStore::`scalar deleting destructor'(v19, v18);
  }
  LeaveCriticalSection(&g_PackageLock);
  v21 = *(FilePool **)(a1 + 304);
  if ( v21 != (FilePool *)-1LL && a1 != -304 && v21 )
  {
    *((_DWORD *)v21 + 39) = 0;
    FilePool::`scalar deleting destructor'(v21, v20);
    *(_QWORD *)(a1 + 304) = 0;
  }
  if ( (*(_DWORD *)(a1 + 168) & 0x5000000) == 0x1000000 )
  {
    v22 = *(TValidataUserManageForm **)(a1 + 360);
    if ( v22 )
    {
      TValidataUserManageForm::`scalar deleting destructor'(v22, v20);
      *(_QWORD *)(a1 + 360) = 0;
    }
  }
  LocalFree(*(HLOCAL *)(a1 + 352));
  NCoreLibrary::TReferenceCount::Release(*(NCoreLibrary::TReferenceCount **)(a1 + 368));
  return DllFreeSplMem(a1);
}

```

## disassembly

```asm
0x18007ff20  push    rbx
0x18007ff22  push    rbp
0x18007ff23  push    rsi
0x18007ff24  push    rdi
0x18007ff25  sub     rsp, 38h
0x18007ff29  mov     rsi, rcx
0x18007ff2c  xor     ecx, ecx
0x18007ff2e  call    EnterSplSem
0x18007ff33  mov     rcx, [rsi+178h]
0x18007ff3a  test    rcx, rcx
0x18007ff3d  jz      short loc_18007FF7C
0x18007ff3f  call    cs:__imp_DevCloseObjectQuery
0x18007ff45  lea     r10, [rsi+10h]
0x18007ff49  mov     qword ptr [rsi+178h], 0
0x18007ff54  cmp     dword ptr [r10], 0
0x18007ff58  jz      short loc_18007FF68
0x18007ff5a  mov     rcx, r10; unsigned int *
0x18007ff5d  call    ?SafeDecrementReference@@YAKPEAK@Z; SafeDecrementReference(ulong *)
0x18007ff62  cmp     dword ptr [r10], 0
0x18007ff66  jnz     short loc_18007FF7C
0x18007ff68  test    dword ptr [rsi+0A8h], 8000h
0x18007ff72  jz      short loc_18007FF7C
0x18007ff74  mov     rcx, rsi
0x18007ff77  call    SplDeleteSpooler
0x18007ff7c  mov     rbp, [rsi+38h]
0x18007ff80  test    rbp, rbp
0x18007ff83  jz      short loc_18007FFD3
0x18007ff85  mov     rbx, [rbp+38h]
0x18007ff89  mov     rdi, [rbp+8]
0x18007ff8d  mov     qword ptr [rbp+38h], 0
0x18007ff95  call    LeaveSplSem
0x18007ff9a  mov     r9, [rsi+18h]
0x18007ff9e  lea     rdx, aShuttingDownMo; "Shutting down monitor %ws on %ws"
0x18007ffa5  mov     r8, [rbp+18h]
0x18007ffa9  lea     rcx, aShutdownmonito; "ShutdownMonitors"
0x18007ffb0  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18007ffb5  mov     rax, [rbp+0E8h]
0x18007ffbc  mov     rcx, rbx
0x18007ffbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ffc4  xor     ecx, ecx
0x18007ffc6  call    EnterSplSem
0x18007ffcb  mov     rbp, rdi
0x18007ffce  test    rdi, rdi
0x18007ffd1  jnz     short loc_18007FF85
0x18007ffd3  mov     r8, [rsi+18h]
0x18007ffd7  lea     rdx, aDeletedInispoo; "Deleted INISPOOLER %ws"
0x18007ffde  lea     rcx, aSpldeleteinisp; "SplDeleteIniSpooler"
0x18007ffe5  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18007ffea  lea     r8, IniSpoolerOffsets
0x18007fff1  xor     edx, edx
0x18007fff3  mov     rcx, rsi
0x18007fff6  call    FreeStructurePointers
0x18007fffb  jmp     short loc_180080008
0x18007fffd  mov     rdx, rsi
0x180080000  mov     rcx, rax
0x180080003  call    DeleteIniForm
0x180080008  mov     rax, [rsi+48h]
0x18008000c  test    rax, rax
0x18008000f  jnz     short loc_18007FFFD
0x180080011  mov     rax, cs:pLocalIniSpooler
0x180080018  mov     rcx, [rsi+30h]; struct _INIENVIRONMENT *
0x18008001c  cmp     rcx, [rax+30h]
0x180080020  jz      short loc_180080038
0x180080022  test    rcx, rcx
0x180080025  jz      short loc_180080038
0x180080027  mov     rbx, [rcx+8]
0x18008002b  call    FreeIniEnvironment
0x180080030  mov     rcx, rbx
0x180080033  test    rbx, rbx
0x180080036  jnz     short loc_180080027
0x180080038  mov     rbx, [rsi+40h]
0x18008003c  test    rbx, rbx
0x18008003f  jz      short loc_180080089
0x180080041  mov     rdi, [rbx+8]
0x180080045  mov     rcx, rbx
0x180080048  call    DeletePortEntry
0x18008004d  test    eax, eax
0x18008004f  jnz     short loc_180080081
0x180080051  mov     rcx, rbx
0x180080054  call    GetMonitorHandle
0x180080059  mov     ecx, [rbx+50h]
0x18008005c  lea     rdx, aUnableToDelete; "Unable to delete port %ws. Handle %p, S"...
0x180080063  mov     r8, [rbx+18h]
0x180080067  mov     r9, rax
0x18008006a  mov     dword ptr [rsp+58h+var_30], ecx
0x18008006e  mov     ecx, [rbx+30h]
0x180080071  mov     dword ptr [rsp+58h+var_38], ecx
0x180080075  lea     rcx, aSpldeleteinisp; "SplDeleteIniSpooler"
0x18008007c  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180080081  mov     rbx, rdi
0x180080084  test    rdi, rdi
0x180080087  jnz     short loc_180080041
0x180080089  mov     rcx, [rsi+38h]
0x18008008d  test    rcx, rcx
0x180080090  jz      short loc_1800800A9
0x180080092  cmp     dword ptr [rcx+10h], 0
0x180080096  mov     rbx, [rcx+8]
0x18008009a  jnz     short loc_1800800A1
0x18008009c  call    FreeIniMonitor
0x1800800a1  mov     rcx, rbx
0x1800800a4  test    rbx, rbx
0x1800800a7  jnz     short loc_180080092
0x1800800a9  mov     rcx, [rsi+0E8h]; hKey
0x1800800b0  test    rcx, rcx
0x1800800b3  jz      short loc_1800800BB
0x1800800b5  call    cs:__imp_RegCloseKey
0x1800800bb  mov     rcx, [rsi+0F0h]; hKey
0x1800800c2  test    rcx, rcx
0x1800800c5  jz      short loc_1800800CD
0x1800800c7  call    cs:__imp_RegCloseKey
0x1800800cd  mov     rbx, [rsi+108h]
0x1800800d4  test    rbx, rbx
0x1800800d7  jz      short loc_1800800F0
0x1800800d9  mov     rcx, [rbx]
0x1800800dc  test    rcx, rcx
0x1800800df  jz      short loc_1800800E7
0x1800800e1  call    cs:__imp_DllFreeSplMem
0x1800800e7  mov     rcx, rbx
0x1800800ea  call    cs:__imp_DllFreeSplMem
0x1800800f0  mov     rcx, [rsi+90h]
0x1800800f7  mov     rcx, [rcx+10h]
0x1800800fb  call    cs:__imp_DllFreeSplStr
0x180080101  mov     rcx, [rsi+90h]
0x180080108  mov     rcx, [rcx+28h]
0x18008010c  call    cs:__imp_DllFreeSplStr
0x180080112  mov     rcx, [rsi+0D8h]
0x180080119  call    cs:__imp_DllFreeSplStr
0x18008011f  mov     rcx, [rsi+90h]
0x180080126  mov     rcx, [rcx+48h]; hMem
0x18008012a  call    cs:__imp_LocalFree
0x180080130  mov     rcx, [rsi+90h]
0x180080137  call    cs:__imp_DllFreeSplMem
0x18008013d  call    LeaveSplSem
0x180080142  lea     rcx, ?g_PackageLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180080149  call    cs:__imp_EnterCriticalSection
0x18008014f  mov     rcx, [rsi+10188h]; this
0x180080156  test    rcx, rcx
0x180080159  jz      short loc_18008016B
0x18008015b  mov     qword ptr [rsi+10188h], 0
0x180080166  call    ??_GTDriverStore@NPackageInstallLocalspl@@QEAAPEAXI@Z; NPackageInstallLocalspl::TDriverStore::`scalar deleting destructor'(uint)
0x18008016b  lea     rcx, ?g_PackageLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180080172  call    cs:__imp_LeaveCriticalSection
0x180080178  lea     rbx, [rsi+130h]
0x18008017f  mov     rcx, [rbx]; this
0x180080182  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180080186  jz      short loc_1800801A8
0x180080188  test    rbx, rbx
0x18008018b  jz      short loc_1800801A8
0x18008018d  test    rcx, rcx
0x180080190  jz      short loc_1800801A8
0x180080192  mov     dword ptr [rcx+9Ch], 0
0x18008019c  call    ??_GFilePool@@QEAAPEAXI@Z; FilePool::`scalar deleting destructor'(uint)
0x1800801a1  mov     qword ptr [rbx], 0
0x1800801a8  mov     eax, [rsi+0A8h]
0x1800801ae  and     eax, 5000000h
0x1800801b3  cmp     eax, 1000000h
0x1800801b8  jnz     short loc_1800801D6
0x1800801ba  mov     rcx, [rsi+168h]; this
0x1800801c1  test    rcx, rcx
0x1800801c4  jz      short loc_1800801D6
0x1800801c6  call    ??_GTValidataUserManageForm@@QEAAPEAXI@Z; TValidataUserManageForm::`scalar deleting destructor'(uint)
0x1800801cb  mov     qword ptr [rsi+168h], 0
0x1800801d6  mov     rcx, [rsi+160h]; hMem
0x1800801dd  call    cs:__imp_LocalFree
0x1800801e3  mov     rcx, [rsi+170h]; this
0x1800801ea  call    ?Release@TReferenceCount@NCoreLibrary@@QEBAJXZ; NCoreLibrary::TReferenceCount::Release(void)
0x1800801ef  mov     rcx, rsi
0x1800801f2  add     rsp, 38h
0x1800801f6  pop     rdi
0x1800801f7  pop     rsi
0x1800801f8  pop     rbp
0x1800801f9  pop     rbx
0x1800801fa  jmp     cs:__imp_DllFreeSplMem
```
