# FREB_REQUEST_CONTEXT::Terminate(void)

- ea: `0x1800054e8`
- end: `0x180005581`
- name: `?Terminate@FREB_REQUEST_CONTEXT@@SAXXZ`
- size: `153`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x180001d74`
- `0x180004274`

## callees

- `0x180001048`
- `0x180003b04`
- `0x1800054e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800054fe`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800054fe`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180005543`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180005543`
- `iisutil!?Terminate@LANG_STRING@@QEAAJXZ` at `0x18000551a`
- `iisutil!?Terminate@LANG_STRING@@QEAAJXZ` at `0x18000551a`

## pseudocode

```c
void FREB_REQUEST_CONTEXT::Terminate(void)
{
  FREB_TIMEOUT_MONITOR_LIST *v0; // rbx

  if ( FREB_REQUEST_CONTEXT::sm_fCustomActionLockInited )
  {
    DeleteCriticalSection(&FREB_REQUEST_CONTEXT::sm_csCustomActionSerializer);
    FREB_REQUEST_CONTEXT::sm_fCustomActionLockInited = 0;
  }
  if ( FREB_REQUEST_CONTEXT::sm_pLangString )
  {
    LANG_STRING::Terminate((LANG_STRING *)FREB_REQUEST_CONTEXT::sm_pLangString);
    operator delete(FREB_REQUEST_CONTEXT::sm_pLangString);
    FREB_REQUEST_CONTEXT::sm_pLangString = 0;
  }
  if ( FREB_REQUEST_CONTEXT::sm_hResourceDll )
  {
    FreeLibrary(FREB_REQUEST_CONTEXT::sm_hResourceDll);
    FREB_REQUEST_CONTEXT::sm_hResourceDll = 0;
  }
  v0 = FREB_REQUEST_CONTEXT::sm_pTimeoutMonitor;
  if ( FREB_REQUEST_CONTEXT::sm_pTimeoutMonitor )
  {
    FREB_TIMEOUT_MONITOR_LIST::~FREB_TIMEOUT_MONITOR_LIST(FREB_REQUEST_CONTEXT::sm_pTimeoutMonitor);
    operator delete(v0);
    FREB_REQUEST_CONTEXT::sm_pTimeoutMonitor = 0;
  }
}

```

## disassembly

```asm
0x1800054e8  push    rbx
0x1800054ea  sub     rsp, 20h
0x1800054ee  cmp     cs:?sm_fCustomActionLockInited@FREB_REQUEST_CONTEXT@@0HA, 0; int FREB_REQUEST_CONTEXT::sm_fCustomActionLockInited
0x1800054f5  jz      short loc_18000550E
0x1800054f7  lea     rcx, ?sm_csCustomActionSerializer@FREB_REQUEST_CONTEXT@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800054fe  call    cs:__imp_DeleteCriticalSection
0x180005504  mov     cs:?sm_fCustomActionLockInited@FREB_REQUEST_CONTEXT@@0HA, 0; int FREB_REQUEST_CONTEXT::sm_fCustomActionLockInited
0x18000550e  mov     rcx, cs:?sm_pLangString@FREB_REQUEST_CONTEXT@@0PEAVLANG_STRING@@EA; LANG_STRING * FREB_REQUEST_CONTEXT::sm_pLangString
0x180005515  test    rcx, rcx
0x180005518  jz      short loc_180005537
0x18000551a  call    cs:__imp_?Terminate@LANG_STRING@@QEAAJXZ; LANG_STRING::Terminate(void)
0x180005520  mov     rcx, cs:?sm_pLangString@FREB_REQUEST_CONTEXT@@0PEAVLANG_STRING@@EA; Block
0x180005527  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000552c  mov     cs:?sm_pLangString@FREB_REQUEST_CONTEXT@@0PEAVLANG_STRING@@EA, 0; LANG_STRING * FREB_REQUEST_CONTEXT::sm_pLangString
0x180005537  mov     rcx, cs:?sm_hResourceDll@FREB_REQUEST_CONTEXT@@0PEAUHINSTANCE__@@EA; hLibModule
0x18000553e  test    rcx, rcx
0x180005541  jz      short loc_180005554
0x180005543  call    cs:__imp_FreeLibrary
0x180005549  mov     cs:?sm_hResourceDll@FREB_REQUEST_CONTEXT@@0PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * FREB_REQUEST_CONTEXT::sm_hResourceDll
0x180005554  mov     rbx, cs:?sm_pTimeoutMonitor@FREB_REQUEST_CONTEXT@@0PEAVFREB_TIMEOUT_MONITOR_LIST@@EA; FREB_TIMEOUT_MONITOR_LIST * FREB_REQUEST_CONTEXT::sm_pTimeoutMonitor
0x18000555b  test    rbx, rbx
0x18000555e  jz      short loc_18000557B
0x180005560  mov     rcx, rbx; this
0x180005563  call    ??1FREB_TIMEOUT_MONITOR_LIST@@QEAA@XZ; FREB_TIMEOUT_MONITOR_LIST::~FREB_TIMEOUT_MONITOR_LIST(void)
0x180005568  mov     rcx, rbx; Block
0x18000556b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005570  mov     cs:?sm_pTimeoutMonitor@FREB_REQUEST_CONTEXT@@0PEAVFREB_TIMEOUT_MONITOR_LIST@@EA, 0; FREB_TIMEOUT_MONITOR_LIST * FREB_REQUEST_CONTEXT::sm_pTimeoutMonitor
0x18000557b  add     rsp, 20h
0x18000557f  pop     rbx
0x180005580  retn
```
