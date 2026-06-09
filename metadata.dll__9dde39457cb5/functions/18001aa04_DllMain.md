# DllMain

- ea: `0x18001aa04`
- end: `0x18001abf2`
- name: `DllMain`
- size: `494`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180008cd4`

## callees

- `0x18001aa04`
- `0x180026cb8`
- `0x180027190`
- `0x1800293b0`
- `0x1800299f0`
- `0x180031010`

## import_xrefs

- `KERNEL32!DisableThreadLibraryCalls` at `0x18001aa9b`
- `KERNEL32!DisableThreadLibraryCalls` at `0x18001aa9b`
- `KERNEL32!OutputDebugStringA` at `0x18001aa48`
- `KERNEL32!OutputDebugStringA` at `0x18001aa48`
- `KERNEL32!DeleteCriticalSection` at `0x18001abb4`
- `KERNEL32!DeleteCriticalSection` at `0x18001abcb`
- `KERNEL32!DeleteCriticalSection` at `0x18001abb4`
- `KERNEL32!DeleteCriticalSection` at `0x18001abcb`
- `IisRTL!PuCreateDebugPrintsObject` at `0x18001aa2f`
- `IisRTL!PuCreateDebugPrintsObject` at `0x18001aa2f`
- `IisRTL!PuLoadDebugFlagsFromRegStr` at `0x18001aa57`
- `IisRTL!PuLoadDebugFlagsFromRegStr` at `0x18001aa57`
- `IisRTL!PuDeleteDebugPrintsObject` at `0x18001abd8`
- `IisRTL!PuDeleteDebugPrintsObject` at `0x18001abd8`
- `IisRTL!IISInitializeCriticalSection` at `0x18001aab2`
- `IisRTL!IISInitializeCriticalSection` at `0x18001aab2`
- `IisRTL!PuDbgPrint` at `0x18001aaf7`
- `IisRTL!PuDbgPrint` at `0x18001aaf7`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001ab57`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001ab57`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001ab1a`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001ab1a`

## string_xrefs

- `0x18001aae5`: `InitializeMetabaseSecurity: error %lx\n`
- `0x18001aad3`: `InitializeMetabaseSecurity`
- `0x18001aade`: `inetsrv\iis\mb\metadata\security.cxx`
- `0x18001aa41`: `Unable to Create Debug Print Object \n`
- `0x18001aa50`: `System\CurrentControlSet\Services\iisadmin\Parameters`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  BOOL v4; // ebx
  int DebugFlagsFromRegStr; // eax
  int v6; // eax
  int v7; // ebx
  int v8; // edi

  v4 = 1;
  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      g_pDebug = PuCreateDebugPrintsObject("Metadata", 1, lpvReserved);
      if ( !g_pDebug )
        OutputDebugStringA("Unable to Create Debug Print Object \n");
      DebugFlagsFromRegStr = PuLoadDebugFlagsFromRegStr("System\\CurrentControlSet\\Services\\iisadmin\\Parameters", 0);
      g_pboMasterRoot = 0;
      g_dwDebugFlags = DebugFlagsFromRegStr;
      *(_OWORD *)&g_phEventHandles = 0;
      g_pHandleTable = 0;
      g_hReadSaveSemaphore = 0;
      g_bSaveDisallowed = 0;
      v4 = DisableThreadLibraryCalls(hinstDLL);
      if ( v4 )
      {
        IISInitializeCriticalSection(&p_SecurityLock);
        v6 = IISCryptoInitialize();
        v7 = v6;
        if ( v6 < 0 && (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\mb\\metadata\\security.cxx",
            68,
            "InitializeMetabaseSecurity",
            "InitializeMetabaseSecurity: error %lx\n",
            v6);
        return v7 >= 0;
      }
    }
  }
  else
  {
    if ( g_pFactory )
    {
      v8 = 0;
      CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)&g_LockMasterResource);
      for ( ; g_dwInitialized; v8 = TerminateWorker1(1) )
      {
        if ( v8 < 0 )
          break;
      }
      g_dwInitialized = 0;
      TerminateWorker();
      CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)&g_LockMasterResource);
      if ( g_pFactory )
        (*(void (__fastcall **)(struct CMDCOMSrvFactory *, __int64))(*(_QWORD *)g_pFactory + 40LL))(g_pFactory, 1);
      g_pFactory = 0;
    }
    if ( p_CryptoProvider )
      IISCryptoCloseContainer(p_CryptoProvider, *(_QWORD *)&fdwReason, lpvReserved);
    if ( p_CryptoProvider2 )
      IISCryptoCloseContainer(p_CryptoProvider2, *(_QWORD *)&fdwReason, lpvReserved);
    if ( dword_180048968 )
    {
      DeleteCriticalSection(&IcpGlobals);
      dword_180048968 = 0;
    }
    DeleteCriticalSection(&p_SecurityLock);
    g_pDebug = PuDeleteDebugPrintsObject(g_pDebug);
  }
  return v4;
}

```

## disassembly

```asm
0x18001aa04  mov     [rsp+arg_0], rbx
0x18001aa09  push    rdi
0x18001aa0a  sub     rsp, 30h
0x18001aa0e  mov     rdi, rcx
0x18001aa11  mov     ebx, 1
0x18001aa16  test    edx, edx
0x18001aa18  jz      loc_18001AB07
0x18001aa1e  cmp     edx, ebx
0x18001aa20  jnz     loc_18001ABE5
0x18001aa26  mov     edx, ebx
0x18001aa28  lea     rcx, aMetadata_0; "Metadata"
0x18001aa2f  call    cs:__imp_PuCreateDebugPrintsObject
0x18001aa35  mov     cs:g_pDebug, rax
0x18001aa3c  test    rax, rax
0x18001aa3f  jnz     short loc_18001AA4E
0x18001aa41  lea     rcx, OutputString; "Unable to Create Debug Print Object \n"
0x18001aa48  call    cs:__imp_OutputDebugStringA
0x18001aa4e  xor     edx, edx
0x18001aa50  lea     rcx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\ii"...
0x18001aa57  call    cs:__imp_PuLoadDebugFlagsFromRegStr
0x18001aa5d  xorps   xmm0, xmm0
0x18001aa60  mov     cs:?g_pboMasterRoot@@3PEAVCMDBaseObject@@EA, 0; CMDBaseObject * g_pboMasterRoot
0x18001aa6b  mov     rcx, rdi; hLibModule
0x18001aa6e  mov     cs:g_dwDebugFlags, eax
0x18001aa74  movups  cs:?g_phEventHandles@@3PAPEAXA, xmm0; void * near * g_phEventHandles
0x18001aa7b  mov     cs:?g_pHandleTable@@3PEAVCHandleTable@@EA, 0; CHandleTable * g_pHandleTable
0x18001aa86  mov     cs:?g_hReadSaveSemaphore@@3PEAXEA, 0; void * g_hReadSaveSemaphore
0x18001aa91  mov     cs:?g_bSaveDisallowed@@3HA, 0; int g_bSaveDisallowed
0x18001aa9b  call    cs:__imp_DisableThreadLibraryCalls
0x18001aaa1  mov     ebx, eax
0x18001aaa3  test    eax, eax
0x18001aaa5  jz      loc_18001ABE5
0x18001aaab  lea     rcx, ?p_SecurityLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION p_SecurityLock
0x18001aab2  call    cs:__imp_IISInitializeCriticalSection
0x18001aab8  call    IISCryptoInitialize
0x18001aabd  mov     ebx, eax
0x18001aabf  test    eax, eax
0x18001aac1  jns     short loc_18001AAFD
0x18001aac3  test    byte ptr cs:g_dwDebugFlags, 3
0x18001aaca  jz      short loc_18001AAFD
0x18001aacc  mov     rcx, cs:g_pDebug
0x18001aad3  lea     r9, aInitializemeta_0; "InitializeMetabaseSecurity"
0x18001aada  mov     [rsp+38h+var_10], eax
0x18001aade  lea     rdx, aInetsrvIisMbMe_1; "inetsrv\\iis\\mb\\metadata\\security.cx"...
0x18001aae5  lea     rax, aInitializemeta; "InitializeMetabaseSecurity: error %lx\n"
0x18001aaec  mov     r8d, 44h ; 'D'
0x18001aaf2  mov     [rsp+38h+var_18], rax
0x18001aaf7  call    cs:__imp_PuDbgPrint
0x18001aafd  not     ebx
0x18001aaff  shr     ebx, 1Fh
0x18001ab02  jmp     loc_18001ABE5
0x18001ab07  cmp     cs:?g_pFactory@@3PEAVCMDCOMSrvFactory@@EA, 0; CMDCOMSrvFactory * g_pFactory
0x18001ab0f  jz      short loc_18001AB82
0x18001ab11  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x18001ab18  xor     edi, edi
0x18001ab1a  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18001ab20  mov     eax, cs:?g_dwInitialized@@3KC; ulong volatile g_dwInitialized
0x18001ab26  test    eax, eax
0x18001ab28  jz      short loc_18001AB41
0x18001ab2a  test    edi, edi
0x18001ab2c  js      short loc_18001AB41
0x18001ab2e  mov     ecx, ebx; int
0x18001ab30  call    ?TerminateWorker1@@YAJH@Z; TerminateWorker1(int)
0x18001ab35  mov     edx, cs:?g_dwInitialized@@3KC; ulong volatile g_dwInitialized
0x18001ab3b  mov     edi, eax
0x18001ab3d  test    edx, edx
0x18001ab3f  jnz     short loc_18001AB2A
0x18001ab41  mov     cs:?g_dwInitialized@@3KC, 0; ulong volatile g_dwInitialized
0x18001ab4b  call    ?TerminateWorker@@YAXXZ; TerminateWorker(void)
0x18001ab50  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x18001ab57  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18001ab5d  mov     rcx, cs:?g_pFactory@@3PEAVCMDCOMSrvFactory@@EA; CMDCOMSrvFactory * g_pFactory
0x18001ab64  test    rcx, rcx
0x18001ab67  jz      short loc_18001AB77
0x18001ab69  mov     rax, [rcx]
0x18001ab6c  mov     edx, ebx
0x18001ab6e  mov     rax, [rax+28h]
0x18001ab72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab77  mov     cs:?g_pFactory@@3PEAVCMDCOMSrvFactory@@EA, 0; CMDCOMSrvFactory * g_pFactory
0x18001ab82  mov     rcx, cs:?p_CryptoProvider@@3_KA; unsigned __int64 p_CryptoProvider
0x18001ab89  test    rcx, rcx
0x18001ab8c  jz      short loc_18001AB93
0x18001ab8e  call    IISCryptoCloseContainer
0x18001ab93  mov     rcx, cs:?p_CryptoProvider2@@3_KA; unsigned __int64 p_CryptoProvider2
0x18001ab9a  test    rcx, rcx
0x18001ab9d  jz      short loc_18001ABA4
0x18001ab9f  call    IISCryptoCloseContainer
0x18001aba4  cmp     cs:dword_180048968, 0
0x18001abab  jz      short loc_18001ABC4
0x18001abad  lea     rcx, ?IcpGlobals@@3U_IC_GLOBALS@@A; lpCriticalSection
0x18001abb4  call    cs:__imp_DeleteCriticalSection
0x18001abba  mov     cs:dword_180048968, 0
0x18001abc4  lea     rcx, ?p_SecurityLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001abcb  call    cs:__imp_DeleteCriticalSection
0x18001abd1  mov     rcx, cs:g_pDebug
0x18001abd8  call    cs:__imp_PuDeleteDebugPrintsObject
0x18001abde  mov     cs:g_pDebug, rax
0x18001abe5  mov     eax, ebx
0x18001abe7  mov     rbx, [rsp+38h+arg_0]
0x18001abec  add     rsp, 30h
0x18001abf0  pop     rdi
0x18001abf1  retn
```
