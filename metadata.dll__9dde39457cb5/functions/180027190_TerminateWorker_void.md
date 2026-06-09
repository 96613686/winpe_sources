# TerminateWorker(void)

- ea: `0x180027190`
- end: `0x1800272f1`
- name: `?TerminateWorker@@YAXXZ`
- size: `353`
- prototype: `void(void)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x18001aa04`
- `0x18001fa58`
- `0x180026cb8`

## callees

- `0x180008a08`
- `0x180009634`
- `0x180009ba8`
- `0x18000f0f4`
- `0x18001adb8`
- `0x18002019c`
- `0x180027190`
- `0x1800272f8`
- `0x180031010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800271c4`
- `KERNEL32!CloseHandle` at `0x1800271c4`
- `IisRTL!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x1800272ce`
- `IisRTL!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x1800272ce`

## pseudocode

```c
void __fastcall TerminateWorker(__int64 a1, unsigned int a2)
{
  __int64 i; // rbx
  void *v3; // rcx
  unsigned int v4; // edx
  STR *v5; // rax
  unsigned int v6; // edx
  void *v7; // rbx

  if ( g_pHandleTable )
  {
    CHandleTable::Terminate(g_pHandleTable);
    g_pHandleTable = 0;
  }
  for ( i = 0; i != 2; ++i )
  {
    v3 = *(&g_phEventHandles + i);
    if ( v3 )
      CloseHandle(v3);
  }
  if ( g_pboMasterRoot )
    (**(void (__fastcall ***)(CMDBaseObject *, __int64))g_pboMasterRoot)(g_pboMasterRoot, 1);
  if ( g_strRealFileName )
  {
    STR::`scalar deleting destructor'(g_strRealFileName, a2);
    v5 = g_strRealFileName;
    if ( g_strRealFileName )
    {
      if ( g_strTempFileName )
      {
        STR::`scalar deleting destructor'(g_strTempFileName, v4);
        v5 = g_strRealFileName;
      }
      if ( v5 )
      {
        if ( g_strBackupFileName )
        {
          STR::`scalar deleting destructor'(g_strBackupFileName, v4);
          v5 = g_strRealFileName;
        }
        if ( v5 )
        {
          if ( g_pstrBackupFilePath )
          {
            STR::`scalar deleting destructor'(g_pstrBackupFilePath, v4);
            v5 = g_strRealFileName;
          }
          if ( v5 && g_strSchemaFileName )
            STR::`scalar deleting destructor'(g_strSchemaFileName, v4);
        }
      }
    }
  }
  UnInitializeUnicodeGlobalDataFileValues();
  if ( g_pGlobalISTHelper )
    CWriterGlobalHelper::`scalar deleting destructor'(g_pGlobalISTHelper, v6);
  if ( g_pEventLog )
    (*(void (__fastcall **)(struct ICatalogErrorLogger2 *))(*(_QWORD *)g_pEventLog + 16LL))(g_pEventLog);
  if ( g_pListenerController )
  {
    CListenerController::Release(g_pListenerController);
    g_pListenerController = 0;
  }
  v7 = HASH_BUFFER_ENTRY::sm_pach;
  if ( HASH_BUFFER_ENTRY::sm_pach )
  {
    ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER((ALLOC_CACHE_HANDLER *)HASH_BUFFER_ENTRY::sm_pach);
    operator delete(v7);
    HASH_BUFFER_ENTRY::sm_pach = 0;
  }
  InitializeGlobalsToNull();
}

```

## disassembly

```asm
0x180027190  push    rbx
0x180027192  sub     rsp, 20h
0x180027196  mov     rcx, cs:?g_pHandleTable@@3PEAVCHandleTable@@EA; this
0x18002719d  test    rcx, rcx
0x1800271a0  jz      short loc_1800271B2
0x1800271a2  call    ?Terminate@CHandleTable@@QEAAJXZ; CHandleTable::Terminate(void)
0x1800271a7  mov     cs:?g_pHandleTable@@3PEAVCHandleTable@@EA, 0; CHandleTable * g_pHandleTable
0x1800271b2  xor     ebx, ebx
0x1800271b4  lea     rcx, ?g_phEventHandles@@3PAPEAXA; void * near * g_phEventHandles
0x1800271bb  mov     rcx, [rcx+rbx*8]; hObject
0x1800271bf  test    rcx, rcx
0x1800271c2  jz      short loc_1800271CA
0x1800271c4  call    cs:__imp_CloseHandle
0x1800271ca  inc     rbx
0x1800271cd  cmp     rbx, 2
0x1800271d1  jnz     short loc_1800271B4
0x1800271d3  mov     rcx, cs:?g_pboMasterRoot@@3PEAVCMDBaseObject@@EA; CMDBaseObject * g_pboMasterRoot
0x1800271da  test    rcx, rcx
0x1800271dd  jz      short loc_1800271ED
0x1800271df  mov     rax, [rcx]
0x1800271e2  lea     edx, [rbx-1]
0x1800271e5  mov     rax, [rax]
0x1800271e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800271ed  mov     rax, cs:?g_strRealFileName@@3PEAVSTR@@EA; STR * g_strRealFileName
0x1800271f4  test    rax, rax
0x1800271f7  jz      short loc_180027275
0x1800271f9  mov     rcx, rax; this
0x1800271fc  call    ??_GSTR@@QEAAPEAXI@Z; STR::`scalar deleting destructor'(uint)
0x180027201  mov     rax, cs:?g_strRealFileName@@3PEAVSTR@@EA; STR * g_strRealFileName
0x180027208  test    rax, rax
0x18002720b  jz      short loc_180027275
0x18002720d  mov     rcx, cs:?g_strTempFileName@@3PEAVSTR@@EA; this
0x180027214  test    rcx, rcx
0x180027217  jz      short loc_180027225
0x180027219  call    ??_GSTR@@QEAAPEAXI@Z; STR::`scalar deleting destructor'(uint)
0x18002721e  mov     rax, cs:?g_strRealFileName@@3PEAVSTR@@EA; STR * g_strRealFileName
0x180027225  test    rax, rax
0x180027228  jz      short loc_180027275
0x18002722a  mov     rcx, cs:?g_strBackupFileName@@3PEAVSTR@@EA; this
0x180027231  test    rcx, rcx
0x180027234  jz      short loc_180027242
0x180027236  call    ??_GSTR@@QEAAPEAXI@Z; STR::`scalar deleting destructor'(uint)
0x18002723b  mov     rax, cs:?g_strRealFileName@@3PEAVSTR@@EA; STR * g_strRealFileName
0x180027242  test    rax, rax
0x180027245  jz      short loc_180027275
0x180027247  mov     rcx, cs:?g_pstrBackupFilePath@@3PEAVSTR@@EA; this
0x18002724e  test    rcx, rcx
0x180027251  jz      short loc_18002725F
0x180027253  call    ??_GSTR@@QEAAPEAXI@Z; STR::`scalar deleting destructor'(uint)
0x180027258  mov     rax, cs:?g_strRealFileName@@3PEAVSTR@@EA; STR * g_strRealFileName
0x18002725f  test    rax, rax
0x180027262  jz      short loc_180027275
0x180027264  mov     rcx, cs:?g_strSchemaFileName@@3PEAVSTR@@EA; this
0x18002726b  test    rcx, rcx
0x18002726e  jz      short loc_180027275
0x180027270  call    ??_GSTR@@QEAAPEAXI@Z; STR::`scalar deleting destructor'(uint)
0x180027275  call    ?UnInitializeUnicodeGlobalDataFileValues@@YAXXZ; UnInitializeUnicodeGlobalDataFileValues(void)
0x18002727a  mov     rcx, cs:?g_pGlobalISTHelper@@3PEAVCWriterGlobalHelper@@EA; this
0x180027281  test    rcx, rcx
0x180027284  jz      short loc_18002728B
0x180027286  call    ??_GCWriterGlobalHelper@@QEAAPEAXI@Z; CWriterGlobalHelper::`scalar deleting destructor'(uint)
0x18002728b  mov     rcx, cs:?g_pEventLog@@3PEAUICatalogErrorLogger2@@EA; ICatalogErrorLogger2 * g_pEventLog
0x180027292  test    rcx, rcx
0x180027295  jz      short loc_1800272A3
0x180027297  mov     rax, [rcx]
0x18002729a  mov     rax, [rax+10h]
0x18002729e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800272a3  mov     rcx, cs:?g_pListenerController@@3PEAVCListenerController@@EA; this
0x1800272aa  test    rcx, rcx
0x1800272ad  jz      short loc_1800272BF
0x1800272af  call    ?Release@CListenerController@@QEAAKXZ; CListenerController::Release(void)
0x1800272b4  mov     cs:?g_pListenerController@@3PEAVCListenerController@@EA, 0; CListenerController * g_pListenerController
0x1800272bf  mov     rbx, cs:?sm_pach@HASH_BUFFER_ENTRY@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * HASH_BUFFER_ENTRY::sm_pach
0x1800272c6  test    rbx, rbx
0x1800272c9  jz      short loc_1800272E7
0x1800272cb  mov     rcx, rbx
0x1800272ce  call    cs:__imp_??1ALLOC_CACHE_HANDLER@@QEAA@XZ; ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER(void)
0x1800272d4  mov     rcx, rbx; Block
0x1800272d7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800272dc  mov     cs:?sm_pach@HASH_BUFFER_ENTRY@@2PEAVALLOC_CACHE_HANDLER@@EA, 0; ALLOC_CACHE_HANDLER * HASH_BUFFER_ENTRY::sm_pach
0x1800272e7  add     rsp, 20h
0x1800272eb  pop     rbx
0x1800272ec  jmp     ?InitializeGlobalsToNull@@YAXXZ; InitializeGlobalsToNull(void)
```
