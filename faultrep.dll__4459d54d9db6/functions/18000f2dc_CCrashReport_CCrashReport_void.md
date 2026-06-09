# CCrashReport::~CCrashReport(void)

- ea: `0x18000f2dc`
- end: `0x18000f5f8`
- name: `??1CCrashReport@@QEAA@XZ`
- size: `796`
- prototype: `void __fastcall(CCrashReport *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x18000e7c0`

## callees

- `0x1800028b4`
- `0x18000f2dc`
- `0x1800172a0`
- `0x1800195e8`
- `0x180025330`
- `0x180025798`
- `0x18002847c`
- `0x180042f54`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000f32d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000f32d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f35e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f37c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f394`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f3b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f3ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f3fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f419`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f44a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f4b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f4cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f55f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f576`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f58d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f5aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f5be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f5d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f35e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f37c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f394`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f3b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f3ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f3fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f419`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f44a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f4b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f4cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f55f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f576`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f58d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f5aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f5be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f5d2`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000f3dd`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000f5e1`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000f3dd`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000f5e1`
- `api-ms-win-core-processsnapshot-l1-1-0!PssFreeSnapshot` at `0x18000f339`
- `api-ms-win-core-processsnapshot-l1-1-0!PssFreeSnapshot` at `0x18000f339`
- `wer!WerpFlushImageCache` at `0x18000f31b`
- `wer!WerpFlushImageCache` at `0x18000f31b`
- `wer!WerpFreeUnmappedVaRanges` at `0x18000f302`
- `wer!WerpFreeUnmappedVaRanges` at `0x18000f302`
- `wer!WerpAuxmdFree` at `0x18000f2f5`
- `wer!WerpAuxmdFree` at `0x18000f2f5`

## pseudocode

```c
void __fastcall CCrashReport::~CCrashReport(CCrashReport *this)
{
  __int64 v2; // rbx
  HANDLE CurrentProcess; // rax
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  const void *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx
  CPluginList *v12; // rcx
  void *v13; // rcx
  char *v14; // rcx
  char *v15; // rcx
  void *v16; // rcx
  void *v17; // rcx
  char *v18; // rcx
  char *v19; // rcx
  char *v20; // rcx
  CPluginList *v21; // rcx
  void *v22; // rcx
  void *v23; // rcx
  void *v24; // rcx
  void *v25; // rcx
  void *v26; // rcx
  void *v27; // rcx
  const void *v28; // rcx

  WerpAuxmdFree((char *)this + 5144);
  WerpFreeUnmappedVaRanges((char *)this + 5112);
  if ( *((_DWORD *)this + 2536) )
    WerpFlushImageCache((CCrashReport *)((char *)this + 9336), 0);
  v2 = *((_QWORD *)this + 617);
  if ( v2 )
  {
    CurrentProcess = GetCurrentProcess();
    PssFreeSnapshot(CurrentProcess, v2);
    *((_QWORD *)this + 617) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 616);
  *((_QWORD *)this + 616) = 0;
  if ( (unsigned __int64)v4 + 1 > 1 )
    CloseHandle(v4);
  v5 = (void *)*((_QWORD *)this + 615);
  *((_QWORD *)this + 615) = 0;
  if ( (unsigned __int64)v5 + 1 > 1 )
    CloseHandle(v5);
  v6 = (void *)*((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = 0;
  if ( (unsigned __int64)v6 + 1 > 1 )
    CloseHandle(v6);
  v7 = (void *)*((_QWORD *)this + 93);
  *((_QWORD *)this + 93) = 0;
  if ( (unsigned __int64)v7 + 1 > 1 )
    CloseHandle(v7);
  v8 = (void *)*((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( (unsigned __int64)v8 + 1 > 1 )
    CloseHandle(v8);
  v9 = (const void *)*((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = 0;
  if ( v9 )
    UnmapViewOfFile(v9);
  v10 = (void *)*((_QWORD *)this + 96);
  *((_QWORD *)this + 96) = 0;
  if ( (unsigned __int64)v10 + 1 > 1 )
    CloseHandle(v10);
  v11 = (void *)*((_QWORD *)this + 95);
  *((_QWORD *)this + 95) = 0;
  if ( (unsigned __int64)v11 + 1 > 1 )
    CloseHandle(v11);
  v12 = (CPluginList *)*((_QWORD *)this + 97);
  *((_QWORD *)this + 97) = 0;
  if ( v12 )
    WerPluginsDestroy(v12);
  v13 = (void *)*((_QWORD *)this + 8);
  *((_QWORD *)this + 8) = 0;
  if ( (unsigned __int64)v13 + 1 > 1 )
    CloseHandle(v13);
  HamConnector::Disconnect((PSRWLOCK)this + 1317);
  utl::vector<utl::unique_ptr<HamConnector::HamActivity,utl::default_delete<HamConnector::HamActivity>>,utl::allocator<utl::unique_ptr<HamConnector::HamActivity,utl::default_delete<HamConnector::HamActivity>>>>::~vector<utl::unique_ptr<HamConnector::HamActivity,utl::default_delete<HamConnector::HamActivity>>,utl::allocator<utl::unique_ptr<HamConnector::HamActivity,utl::default_delete<HamConnector::HamActivity>>>>((__int64)this + 10552);
  v14 = (char *)*((_QWORD *)this + 1313);
  if ( v14 != (char *)this + 10520 )
    operator delete(v14, (const struct std::nothrow_t *)&std::nothrow);
  v15 = (char *)*((_QWORD *)this + 1309);
  if ( v15 != (char *)this + 10488 )
    operator delete(v15, (const struct std::nothrow_t *)&std::nothrow);
  v16 = (void *)*((_QWORD *)this + 616);
  if ( (unsigned __int64)v16 + 1 > 1 )
    CloseHandle(v16);
  v17 = (void *)*((_QWORD *)this + 615);
  if ( (unsigned __int64)v17 + 1 > 1 )
    CloseHandle(v17);
  v18 = (char *)*((_QWORD *)this + 611);
  if ( v18 != (char *)this + 4904 )
    operator delete(v18, (const struct std::nothrow_t *)&std::nothrow);
  CLocalDumpGenerator::~CLocalDumpGenerator((CCrashReport *)((char *)this + 3616));
  CElevatedDataCollection::~CElevatedDataCollection((CCrashReport *)((char *)this + 2240));
  v19 = (char *)*((_QWORD *)this + 276);
  if ( v19 != (char *)this + 2224 )
    operator delete(v19, (const struct std::nothrow_t *)&std::nothrow);
  v20 = (char *)*((_QWORD *)this + 98);
  if ( v20 != (char *)this + 800 )
    operator delete(v20, (const struct std::nothrow_t *)&std::nothrow);
  v21 = (CPluginList *)*((_QWORD *)this + 97);
  if ( v21 )
    WerPluginsDestroy(v21);
  v22 = (void *)*((_QWORD *)this + 96);
  if ( (unsigned __int64)v22 + 1 > 1 )
    CloseHandle(v22);
  v23 = (void *)*((_QWORD *)this + 95);
  if ( (unsigned __int64)v23 + 1 > 1 )
    CloseHandle(v23);
  v24 = (void *)*((_QWORD *)this + 93);
  if ( (unsigned __int64)v24 + 1 > 1 )
    CloseHandle(v24);
  CCrashSignature::~CCrashSignature((CCrashReport *)((char *)this + 72));
  v25 = (void *)*((_QWORD *)this + 8);
  if ( (unsigned __int64)v25 + 1 > 1 )
    CloseHandle(v25);
  v26 = (void *)*((_QWORD *)this + 7);
  if ( (unsigned __int64)v26 + 1 > 1 )
    CloseHandle(v26);
  v27 = (void *)*((_QWORD *)this + 6);
  if ( (unsigned __int64)v27 + 1 > 1 )
    CloseHandle(v27);
  v28 = (const void *)*((_QWORD *)this + 5);
  if ( v28 )
    UnmapViewOfFile(v28);
}

```

## disassembly

```asm
0x18000f2dc  mov     [rsp+arg_0], rbx
0x18000f2e1  mov     [rsp+arg_8], rsi
0x18000f2e6  push    rdi
0x18000f2e7  sub     rsp, 20h
0x18000f2eb  mov     rdi, rcx
0x18000f2ee  add     rcx, 1418h
0x18000f2f5  call    cs:__imp_WerpAuxmdFree
0x18000f2fb  lea     rcx, [rdi+13F8h]
0x18000f302  call    cs:__imp_WerpFreeUnmappedVaRanges
0x18000f308  xor     esi, esi
0x18000f30a  cmp     [rdi+27A0h], esi
0x18000f310  jz      short loc_18000F321
0x18000f312  lea     rcx, [rdi+2478h]
0x18000f319  xor     edx, edx
0x18000f31b  call    cs:__imp_?WerpFlushImageCache@@YAKPEAUWERP_IMAGE_CACHE@@K@Z; WerpFlushImageCache(WERP_IMAGE_CACHE *,ulong)
0x18000f321  mov     rbx, [rdi+1348h]
0x18000f328  test    rbx, rbx
0x18000f32b  jz      short loc_18000F346
0x18000f32d  call    cs:__imp_GetCurrentProcess
0x18000f333  mov     rdx, rbx
0x18000f336  mov     rcx, rax
0x18000f339  call    cs:__imp_PssFreeSnapshot
0x18000f33f  mov     [rdi+1348h], rsi
0x18000f346  mov     rcx, [rdi+1340h]; hObject
0x18000f34d  mov     [rdi+1340h], rsi
0x18000f354  lea     rax, [rcx+1]
0x18000f358  cmp     rax, 1
0x18000f35c  jbe     short loc_18000F364
0x18000f35e  call    cs:__imp_CloseHandle
0x18000f364  mov     rcx, [rdi+1338h]; hObject
0x18000f36b  mov     [rdi+1338h], rsi
0x18000f372  lea     rax, [rcx+1]
0x18000f376  cmp     rax, 1
0x18000f37a  jbe     short loc_18000F382
0x18000f37c  call    cs:__imp_CloseHandle
0x18000f382  mov     rcx, [rdi+30h]; hObject
0x18000f386  mov     [rdi+30h], rsi
0x18000f38a  lea     rax, [rcx+1]
0x18000f38e  cmp     rax, 1
0x18000f392  jbe     short loc_18000F39A
0x18000f394  call    cs:__imp_CloseHandle
0x18000f39a  mov     rcx, [rdi+2E8h]; hObject
0x18000f3a1  mov     [rdi+2E8h], rsi
0x18000f3a8  lea     rax, [rcx+1]
0x18000f3ac  cmp     rax, 1
0x18000f3b0  jbe     short loc_18000F3B8
0x18000f3b2  call    cs:__imp_CloseHandle
0x18000f3b8  mov     rcx, [rdi+38h]; hObject
0x18000f3bc  mov     [rdi+38h], rsi
0x18000f3c0  lea     rax, [rcx+1]
0x18000f3c4  cmp     rax, 1
0x18000f3c8  jbe     short loc_18000F3D0
0x18000f3ca  call    cs:__imp_CloseHandle
0x18000f3d0  mov     rcx, [rdi+28h]; lpBaseAddress
0x18000f3d4  mov     [rdi+28h], rsi
0x18000f3d8  test    rcx, rcx
0x18000f3db  jz      short loc_18000F3E3
0x18000f3dd  call    cs:__imp_UnmapViewOfFile
0x18000f3e3  mov     rcx, [rdi+300h]; hObject
0x18000f3ea  mov     [rdi+300h], rsi
0x18000f3f1  lea     rax, [rcx+1]
0x18000f3f5  cmp     rax, 1
0x18000f3f9  jbe     short loc_18000F401
0x18000f3fb  call    cs:__imp_CloseHandle
0x18000f401  mov     rcx, [rdi+2F8h]; hObject
0x18000f408  mov     [rdi+2F8h], rsi
0x18000f40f  lea     rax, [rcx+1]
0x18000f413  cmp     rax, 1
0x18000f417  jbe     short loc_18000F41F
0x18000f419  call    cs:__imp_CloseHandle
0x18000f41f  mov     rcx, [rdi+308h]; this
0x18000f426  mov     [rdi+308h], rsi
0x18000f42d  test    rcx, rcx
0x18000f430  jz      short loc_18000F438
0x18000f432  call    ?WerPluginsDestroy@@YAJPEAX@Z; WerPluginsDestroy(void *)
0x18000f437  nop
0x18000f438  mov     rcx, [rdi+40h]; hObject
0x18000f43c  mov     [rdi+40h], rsi
0x18000f440  lea     rax, [rcx+1]
0x18000f444  cmp     rax, 1
0x18000f448  jbe     short loc_18000F450
0x18000f44a  call    cs:__imp_CloseHandle
0x18000f450  lea     rbx, [rdi+2928h]
0x18000f457  mov     rcx, rbx; SRWLock
0x18000f45a  call    ?Disconnect@HamConnector@@QEAAJXZ; HamConnector::Disconnect(void)
0x18000f45f  lea     rcx, [rbx+10h]
0x18000f463  call    ??1?$vector@V?$unique_ptr@UHamActivity@HamConnector@@U?$default_delete@UHamActivity@HamConnector@@@utl@@@utl@@V?$allocator@V?$unique_ptr@UHamActivity@HamConnector@@U?$default_delete@UHamActivity@HamConnector@@@utl@@@utl@@@2@@utl@@QEAA@XZ; utl::vector<utl::unique_ptr<HamConnector::HamActivity,utl::default_delete<HamConnector::HamActivity>>,utl::allocator<utl::unique_ptr<HamConnector::HamActivity,utl::default_delete<HamConnector::HamActivity>>>>::~vector<utl::unique_ptr<HamConnector::HamActivity,utl::default_delete<HamConnector::HamActivity>>,utl::allocator<utl::unique_ptr<HamConnector::HamActivity,utl::default_delete<HamConnector::HamActivity>>>>(void)
0x18000f468  mov     rcx, [rdi+2908h]; void *
0x18000f46f  lea     rax, [rdi+2918h]
0x18000f476  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18000f47d  cmp     rcx, rax
0x18000f480  jz      short loc_18000F48A
0x18000f482  mov     rdx, rbx; struct std::nothrow_t *
0x18000f485  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000f48a  mov     rcx, [rdi+28E8h]; void *
0x18000f491  lea     rax, [rdi+28F8h]
0x18000f498  cmp     rcx, rax
0x18000f49b  jz      short loc_18000F4A5
0x18000f49d  mov     rdx, rbx; struct std::nothrow_t *
0x18000f4a0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000f4a5  mov     rcx, [rdi+1340h]; hObject
0x18000f4ac  lea     rax, [rcx+1]
0x18000f4b0  cmp     rax, 1
0x18000f4b4  jbe     short loc_18000F4BC
0x18000f4b6  call    cs:__imp_CloseHandle
0x18000f4bc  mov     rcx, [rdi+1338h]; hObject
0x18000f4c3  lea     rax, [rcx+1]
0x18000f4c7  cmp     rax, 1
0x18000f4cb  jbe     short loc_18000F4D3
0x18000f4cd  call    cs:__imp_CloseHandle
0x18000f4d3  mov     rcx, [rdi+1318h]; void *
0x18000f4da  lea     rax, [rdi+1328h]
0x18000f4e1  cmp     rcx, rax
0x18000f4e4  jz      short loc_18000F4EE
0x18000f4e6  mov     rdx, rbx; struct std::nothrow_t *
0x18000f4e9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000f4ee  lea     rcx, [rdi+0E20h]; this
0x18000f4f5  call    ??1CLocalDumpGenerator@@UEAA@XZ; CLocalDumpGenerator::~CLocalDumpGenerator(void)
0x18000f4fa  lea     rcx, [rdi+8C0h]; this
0x18000f501  call    ??1CElevatedDataCollection@@QEAA@XZ; CElevatedDataCollection::~CElevatedDataCollection(void)
0x18000f506  mov     rcx, [rdi+8A0h]; void *
0x18000f50d  lea     rax, [rdi+8B0h]
0x18000f514  cmp     rcx, rax
0x18000f517  jz      short loc_18000F521
0x18000f519  mov     rdx, rbx; struct std::nothrow_t *
0x18000f51c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000f521  mov     rcx, [rdi+310h]; void *
0x18000f528  lea     rax, [rdi+320h]
0x18000f52f  cmp     rcx, rax
0x18000f532  jz      short loc_18000F53C
0x18000f534  mov     rdx, rbx; struct std::nothrow_t *
0x18000f537  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000f53c  mov     rcx, [rdi+308h]; this
0x18000f543  test    rcx, rcx
0x18000f546  jz      short loc_18000F54E
0x18000f548  call    ?WerPluginsDestroy@@YAJPEAX@Z; WerPluginsDestroy(void *)
0x18000f54d  nop
0x18000f54e  mov     rcx, [rdi+300h]; hObject
0x18000f555  lea     rax, [rcx+1]
0x18000f559  cmp     rax, 1
0x18000f55d  jbe     short loc_18000F565
0x18000f55f  call    cs:__imp_CloseHandle
0x18000f565  mov     rcx, [rdi+2F8h]; hObject
0x18000f56c  lea     rax, [rcx+1]
0x18000f570  cmp     rax, 1
0x18000f574  jbe     short loc_18000F57C
0x18000f576  call    cs:__imp_CloseHandle
0x18000f57c  mov     rcx, [rdi+2E8h]; hObject
0x18000f583  lea     rax, [rcx+1]
0x18000f587  cmp     rax, 1
0x18000f58b  jbe     short loc_18000F593
0x18000f58d  call    cs:__imp_CloseHandle
0x18000f593  lea     rcx, [rdi+48h]; this
0x18000f597  call    ??1CCrashSignature@@QEAA@XZ; CCrashSignature::~CCrashSignature(void)
0x18000f59c  mov     rcx, [rdi+40h]; hObject
0x18000f5a0  lea     rax, [rcx+1]
0x18000f5a4  cmp     rax, 1
0x18000f5a8  jbe     short loc_18000F5B0
0x18000f5aa  call    cs:__imp_CloseHandle
0x18000f5b0  mov     rcx, [rdi+38h]; hObject
0x18000f5b4  lea     rax, [rcx+1]
0x18000f5b8  cmp     rax, 1
0x18000f5bc  jbe     short loc_18000F5C4
0x18000f5be  call    cs:__imp_CloseHandle
0x18000f5c4  mov     rcx, [rdi+30h]; hObject
0x18000f5c8  lea     rax, [rcx+1]
0x18000f5cc  cmp     rax, 1
0x18000f5d0  jbe     short loc_18000F5D8
0x18000f5d2  call    cs:__imp_CloseHandle
0x18000f5d8  mov     rcx, [rdi+28h]; lpBaseAddress
0x18000f5dc  test    rcx, rcx
0x18000f5df  jz      short loc_18000F5E8
0x18000f5e1  call    cs:__imp_UnmapViewOfFile
0x18000f5e7  nop
0x18000f5e8  mov     rbx, [rsp+28h+arg_0]
0x18000f5ed  mov     rsi, [rsp+28h+arg_8]
0x18000f5f2  add     rsp, 20h
0x18000f5f6  pop     rdi
0x18000f5f7  retn
```
