# UL_AND_WORKER_MANAGER::CreateVirtualSite(SITE_DATA_OBJECT *,int)

- ea: `0x18000fb50`
- end: `0x18000fe63`
- name: `?CreateVirtualSite@UL_AND_WORKER_MANAGER@@QEAAXPEAVSITE_DATA_OBJECT@@H@Z`
- size: `787`
- prototype: `void __fastcall(UL_AND_WORKER_MANAGER *__hidden this, struct SITE_DATA_OBJECT *, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000fa3c`
- `0x18003a1b0`

## callees

- `0x180001234`
- `0x18000fb50`
- `0x180014d44`
- `0x18003ddd4`
- `0x18004079c`
- `0x180062010`

## import_xrefs

- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18000fdb6`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18000fdb6`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18000fd2b`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18000fd2b`
- `iisutil!PuDbgPrint` at `0x18000fdee`
- `iisutil!PuDbgPrint` at `0x18000fdee`
- `iisutil!PuDbgPrintError` at `0x18000fd19`
- `iisutil!PuDbgPrintError` at `0x18000fd6d`
- `iisutil!PuDbgPrintError` at `0x18000fe3d`
- `iisutil!PuDbgPrintError` at `0x18000fd19`
- `iisutil!PuDbgPrintError` at `0x18000fd6d`
- `iisutil!PuDbgPrintError` at `0x18000fe3d`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000fb8f`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000fb99`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000fb8f`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000fb99`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x18000fba6`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x18000fba6`

## string_xrefs

- `0x18000fd12`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\ul_and_worker_manager.cxx`
- `0x18000fd66`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\ul_and_worker_manager.cxx`
- `0x18000fdce`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\ul_and_worker_manager.cxx`
- `0x18000fe36`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\ul_and_worker_manager.cxx`
- `0x18000fd01`: `UL_AND_WORKER_MANAGER::CreateVirtualSite`
- `0x18000fd51`: `UL_AND_WORKER_MANAGER::CreateVirtualSite`
- `0x18000fdc3`: `UL_AND_WORKER_MANAGER::CreateVirtualSite`
- `0x18000fe21`: `UL_AND_WORKER_MANAGER::CreateVirtualSite`

## pseudocode

```c
void __fastcall UL_AND_WORKER_MANAGER::CreateVirtualSite(
        UL_AND_WORKER_MANAGER *this,
        struct SITE_DATA_OBJECT *a2,
        int a3)
{
  WAS_ERROR_LOGGER *v6; // rcx
  char *v7; // rbx
  __int64 v8; // rcx
  _BYTE *v9; // rax
  __int64 v10; // rcx
  _BYTE *v11; // rax
  int v12; // edi
  char v13; // al
  bool v14; // zf
  unsigned int v15; // eax
  unsigned int v16; // edx

  v7 = (char *)operator new(0x2F0u);
  if ( !v7 )
  {
    v12 = -2147024888;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\ul_and_worker_manager.cxx",
        581,
        "UL_AND_WORKER_MANAGER::CreateVirtualSite",
        -2147024888,
        "Allocating VIRTUAL_SITE failed\n");
    goto LABEL_20;
  }
  *(_QWORD *)v7 = &VIRTUAL_SITE::`vftable';
  STRU::STRU((STRU *)(v7 + 16));
  STRU::STRU((STRU *)(v7 + 72));
  MULTISZ::MULTISZ((MULTISZ *)(v7 + 176));
  *((_QWORD *)v7 + 75) = 0;
  *((_QWORD *)v7 + 79) = v7 + 600;
  *((_DWORD *)v7 + 160) = 32;
  *((_WORD *)v7 + 322) = 256;
  ENABLE_PROTOCOL_LIST::ENABLE_PROTOCOL_LIST((ENABLE_PROTOCOL_LIST *)(v7 + 656));
  *((_DWORD *)v7 + 34) = 4;
  *((_QWORD *)v7 + 19) = v7 + 144;
  *((_QWORD *)v7 + 18) = v7 + 144;
  v8 = 20;
  v9 = v7 + 560;
  *((_DWORD *)v7 + 3) = -1;
  *((_DWORD *)v7 + 40) = 0;
  *((_DWORD *)v7 + 60) = 1;
  *((_QWORD *)v7 + 36) = 0;
  *((_QWORD *)v7 + 37) = 0;
  *((_QWORD *)v7 + 31) = 0;
  *((_DWORD *)v7 + 61) = 5;
  *((_QWORD *)v7 + 32) = 0;
  *((_QWORD *)v7 + 33) = 0;
  *((_DWORD *)v7 + 68) = 0;
  *((_QWORD *)v7 + 38) = 0;
  *((_DWORD *)v7 + 145) = 0;
  do
  {
    *v9++ = 0;
    --v8;
  }
  while ( v8 );
  v10 = 248;
  v11 = v7 + 312;
  do
  {
    *v11++ = 0;
    --v10;
  }
  while ( v10 );
  *((_DWORD *)v7 + 78) = 248;
  *((_QWORD *)v7 + 73) = 0;
  *((_DWORD *)v7 + 70) = -1;
  *((_DWORD *)v7 + 69) = -1;
  *((_DWORD *)v7 + 71) = 120;
  *((_QWORD *)v7 + 74) = 0;
  *((_DWORD *)v7 + 162) = 0;
  *((_QWORD *)v7 + 92) = 0;
  *((_QWORD *)v7 + 93) = 0;
  *((_QWORD *)v7 + 21) = 0;
  *((_QWORD *)v7 + 16) = 0;
  *((_DWORD *)v7 + 2) = 1163154262;
  v12 = VIRTUAL_SITE::Initialize((VIRTUAL_SITE *)v7, a2);
  if ( v12 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\ul_and_worker_manager.cxx",
        596,
        "UL_AND_WORKER_MANAGER::CreateVirtualSite",
        v12,
        "Initializing virtual site object failed\n");
LABEL_13:
    (**(void (__fastcall ***)(void *, __int64))v7)(v7, 1);
LABEL_20:
    v16 = -1073736722;
    goto LABEL_21;
  }
  if ( (unsigned int)CLKRHashTable::InsertRecord((char *)this + 96, v7, 0) )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\ul_and_worker_manager.cxx",
        613,
        "UL_AND_WORKER_MANAGER::CreateVirtualSite",
        -2147467259,
        "Inserting virtual site into hashtable failed\n");
    v12 = -2147467259;
    goto LABEL_13;
  }
  v13 = g_dwDebugFlags;
  v14 = (g_dwDebugFlags & 0x30000) == 0;
  *((_DWORD *)this + 102) = 1;
  if ( !v14 && (v13 & 3) != 0 )
  {
    v15 = CLKRHashTable::Size((UL_AND_WORKER_MANAGER *)((char *)this + 96));
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\ul_and_worker_manager.cxx",
      627,
      "UL_AND_WORKER_MANAGER::CreateVirtualSite",
      "New virtual site: %lu added to virtual site hashtable; total number now: %lu\n",
      *((_DWORD *)a2 + 12),
      v15);
  }
  if ( a3 )
  {
    v16 = 1073747009;
LABEL_21:
    WAS_ERROR_LOGGER::LogSiteError(v6, v16, v12, *((_DWORD *)a2 + 12));
  }
}

```

## disassembly

```asm
0x18000fb50  push    rbx
0x18000fb52  push    rbp
0x18000fb53  push    rsi
0x18000fb54  push    rdi
0x18000fb55  push    r12
0x18000fb57  push    r14
0x18000fb59  push    r15
0x18000fb5b  sub     rsp, 40h
0x18000fb5f  mov     r14, rcx
0x18000fb62  mov     r15d, r8d
0x18000fb65  mov     ecx, 2F0h; Size
0x18000fb6a  mov     rsi, rdx
0x18000fb6d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000fb72  xor     r12d, r12d
0x18000fb75  mov     rbx, rax
0x18000fb78  test    rax, rax
0x18000fb7b  jz      loc_18000FE00
0x18000fb81  lea     rax, ??_7VIRTUAL_SITE@@6B@; const VIRTUAL_SITE::`vftable'
0x18000fb88  lea     rcx, [rbx+10h]
0x18000fb8c  mov     [rbx], rax
0x18000fb8f  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000fb95  lea     rcx, [rbx+48h]
0x18000fb99  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000fb9f  lea     rcx, [rbx+0B0h]
0x18000fba6  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x18000fbac  lea     rax, [rbx+258h]
0x18000fbb3  lea     rcx, [rbx+290h]; this
0x18000fbba  mov     [rax], r12
0x18000fbbd  mov     [rax+20h], rax
0x18000fbc1  mov     dword ptr [rax+28h], 20h ; ' '
0x18000fbc8  mov     word ptr [rax+2Ch], 100h
0x18000fbce  call    ??0ENABLE_PROTOCOL_LIST@@QEAA@XZ; ENABLE_PROTOCOL_LIST::ENABLE_PROTOCOL_LIST(void)
0x18000fbd3  lea     rax, [rbx+90h]
0x18000fbda  mov     dword ptr [rbx+88h], 4
0x18000fbe4  or      r9d, 0FFFFFFFFh
0x18000fbe8  mov     [rax+8], rax
0x18000fbec  mov     [rax], rax
0x18000fbef  lea     ecx, [r12+14h]
0x18000fbf4  lea     rax, [rbx+230h]
0x18000fbfb  mov     [rbx+0Ch], r9d
0x18000fbff  mov     [rbx+0A0h], r12d
0x18000fc06  mov     dword ptr [rbx+0F0h], 1
0x18000fc10  mov     [rbx+120h], r12
0x18000fc17  mov     [rbx+128h], r12
0x18000fc1e  mov     [rbx+0F8h], r12
0x18000fc25  mov     dword ptr [rbx+0F4h], 5
0x18000fc2f  mov     [rbx+100h], r12
0x18000fc36  mov     [rbx+108h], r12
0x18000fc3d  mov     [rbx+110h], r12d
0x18000fc44  mov     [rbx+130h], r12
0x18000fc4b  mov     [rbx+244h], r12d
0x18000fc52  mov     [rax], r12b
0x18000fc55  inc     rax
0x18000fc58  sub     rcx, 1
0x18000fc5c  jnz     short loc_18000FC52
0x18000fc5e  mov     r8d, 0F8h
0x18000fc64  lea     rdx, [rbx+138h]
0x18000fc6b  mov     ecx, r8d
0x18000fc6e  mov     rax, rdx
0x18000fc71  mov     [rax], r12b
0x18000fc74  inc     rax
0x18000fc77  sub     rcx, 1
0x18000fc7b  jnz     short loc_18000FC71
0x18000fc7d  mov     [rdx], r8d
0x18000fc80  mov     rcx, rbx; this
0x18000fc83  mov     rdx, rsi; struct SITE_DATA_OBJECT *
0x18000fc86  mov     [rbx+248h], r12
0x18000fc8d  mov     [rbx+118h], r9d
0x18000fc94  mov     [rbx+114h], r9d
0x18000fc9b  mov     dword ptr [rbx+11Ch], 78h ; 'x'
0x18000fca5  mov     [rbx+250h], r12
0x18000fcac  mov     [rbx+288h], r12d
0x18000fcb3  mov     [rbx+2E0h], r12
0x18000fcba  mov     [rbx+2E8h], r12
0x18000fcc1  mov     [rbx+0A8h], r12
0x18000fcc8  mov     [rbx+80h], r12
0x18000fccf  mov     dword ptr [rbx+8], 45545356h
0x18000fcd6  call    ?Initialize@VIRTUAL_SITE@@QEAAJPEAVSITE_DATA_OBJECT@@@Z; VIRTUAL_SITE::Initialize(SITE_DATA_OBJECT *)
0x18000fcdb  mov     edi, eax
0x18000fcdd  test    eax, eax
0x18000fcdf  jns     short loc_18000FD21
0x18000fce1  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000fce8  jz      loc_18000FD78
0x18000fcee  mov     rcx, cs:g_pDebug
0x18000fcf5  lea     rax, aInitializingVi; "Initializing virtual site object failed"...
0x18000fcfc  mov     [rsp+78h+var_50], rax
0x18000fd01  lea     r9, aUlAndWorkerMan_15; "UL_AND_WORKER_MANAGER::CreateVirtualSit"...
0x18000fd08  mov     r8d, 254h
0x18000fd0e  mov     dword ptr [rsp+78h+var_58], edi
0x18000fd12  lea     rdx, aServercommonIn_68; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000fd19  call    cs:__imp_PuDbgPrintError
0x18000fd1f  jmp     short loc_18000FD78
0x18000fd21  xor     r8d, r8d
0x18000fd24  lea     rcx, [r14+60h]
0x18000fd28  mov     rdx, rbx
0x18000fd2b  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x18000fd31  test    eax, eax
0x18000fd33  jz      short loc_18000FD90
0x18000fd35  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000fd3c  jz      short loc_18000FD73
0x18000fd3e  mov     rcx, cs:g_pDebug
0x18000fd45  lea     rax, aInsertingVirtu; "Inserting virtual site into hashtable f"...
0x18000fd4c  mov     [rsp+78h+var_50], rax
0x18000fd51  lea     r9, aUlAndWorkerMan_15; "UL_AND_WORKER_MANAGER::CreateVirtualSit"...
0x18000fd58  mov     r8d, 265h
0x18000fd5e  mov     dword ptr [rsp+78h+var_58], 80004005h
0x18000fd66  lea     rdx, aServercommonIn_68; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000fd6d  call    cs:__imp_PuDbgPrintError
0x18000fd73  mov     edi, 80004005h
0x18000fd78  mov     rax, [rbx]
0x18000fd7b  mov     edx, 1
0x18000fd80  mov     rcx, rbx
0x18000fd83  mov     rax, [rax]
0x18000fd86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd8b  jmp     loc_18000FE43
0x18000fd90  mov     eax, cs:g_dwDebugFlags
0x18000fd96  test    eax, 30000h
0x18000fd9b  mov     dword ptr [r14+198h], 1
0x18000fda6  setnz   dl
0x18000fda9  test    al, 3
0x18000fdab  setnz   al
0x18000fdae  test    al, dl
0x18000fdb0  jz      short loc_18000FDF4
0x18000fdb2  lea     rcx, [r14+60h]
0x18000fdb6  call    cs:__imp_?Size@CLKRHashTable@@QEBAKXZ; CLKRHashTable::Size(void)
0x18000fdbc  mov     rcx, cs:g_pDebug
0x18000fdc3  lea     r9, aUlAndWorkerMan_15; "UL_AND_WORKER_MANAGER::CreateVirtualSit"...
0x18000fdca  mov     [rsp+78h+var_48], eax
0x18000fdce  lea     rdx, aServercommonIn_68; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000fdd5  mov     eax, [rsi+30h]
0x18000fdd8  mov     r8d, 273h
0x18000fdde  mov     dword ptr [rsp+78h+var_50], eax
0x18000fde2  lea     rax, aNewVirtualSite; "New virtual site: %lu added to virtual "...
0x18000fde9  mov     [rsp+78h+var_58], rax
0x18000fdee  call    cs:__imp_PuDbgPrint
0x18000fdf4  test    r15d, r15d
0x18000fdf7  jz      short loc_18000FE54
0x18000fdf9  mov     edx, 40001441h
0x18000fdfe  jmp     short loc_18000FE48
0x18000fe00  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000fe07  mov     edi, 80070008h
0x18000fe0c  jz      short loc_18000FE43
0x18000fe0e  mov     rcx, cs:g_pDebug
0x18000fe15  lea     rax, aAllocatingVirt; "Allocating VIRTUAL_SITE failed\n"
0x18000fe1c  mov     [rsp+78h+var_50], rax
0x18000fe21  lea     r9, aUlAndWorkerMan_15; "UL_AND_WORKER_MANAGER::CreateVirtualSit"...
0x18000fe28  mov     r8d, 245h
0x18000fe2e  mov     dword ptr [rsp+78h+var_58], 80070008h
0x18000fe36  lea     rdx, aServercommonIn_68; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000fe3d  call    cs:__imp_PuDbgPrintError
0x18000fe43  mov     edx, 0C00013EEh; unsigned int
0x18000fe48  mov     r9d, [rsi+30h]; unsigned int
0x18000fe4c  mov     r8d, edi; int
0x18000fe4f  call    ?LogSiteError@WAS_ERROR_LOGGER@@QEAAXKJK@Z; WAS_ERROR_LOGGER::LogSiteError(ulong,long,ulong)
0x18000fe54  add     rsp, 40h
0x18000fe58  pop     r15
0x18000fe5a  pop     r14
0x18000fe5c  pop     r12
0x18000fe5e  pop     rdi
0x18000fe5f  pop     rsi
0x18000fe60  pop     rbp
0x18000fe61  pop     rbx
0x18000fe62  retn
```
