# InitWorker(int,char *,char *,char *,int)

- ea: `0x18001fa58`
- end: `0x18002000e`
- name: `?InitWorker@@YAJHPEAD00H@Z`
- size: `1462`
- prototype: `__int64 __fastcall(int, char *, char *, char *, int)`
- caller_count: `2`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180018d50`
- `0x18001a584`

## callees

- `0x1800037d8`
- `0x180008364`
- `0x18000959c`
- `0x18000f04c`
- `0x18000f0f4`
- `0x18000f128`
- `0x18000f2d0`
- `0x180013bb0`
- `0x180014310`
- `0x180014ef8`
- `0x18001b368`
- `0x18001deb8`
- `0x18001fa58`
- `0x18002019c`
- `0x180021330`
- `0x180021c40`
- `0x180025800`
- `0x180025ffc`
- `0x180027190`
- `0x180031010`

## import_xrefs

- `KERNEL32!CreateEventA` at `0x18001fd50`
- `KERNEL32!CreateEventA` at `0x18001fd78`
- `KERNEL32!CreateEventA` at `0x18001fd50`
- `KERNEL32!CreateEventA` at `0x18001fd78`
- `IisRTL!?ReadOrWriteUnlock@CReaderWriterLock3@@QEAAX_N@Z` at `0x18001ff44`
- `IisRTL!?ReadOrWriteUnlock@CReaderWriterLock3@@QEAAX_N@Z` at `0x18001ff44`
- `IisRTL!?ConvertSharedToExclusive@CReaderWriterLock3@@QEAAXXZ` at `0x18001fc29`
- `IisRTL!?ConvertSharedToExclusive@CReaderWriterLock3@@QEAAXXZ` at `0x18001fc29`
- `IisRTL!?IsValid@STRAU@@QEAAHXZ` at `0x18001fcc0`
- `IisRTL!?IsValid@STRAU@@QEAAHXZ` at `0x18001fcc0`
- `IisRTL!PuDbgPrint` at `0x18001fac6`
- `IisRTL!PuDbgPrint` at `0x18001fb1e`
- `IisRTL!PuDbgPrint` at `0x18001fb68`
- `IisRTL!PuDbgPrint` at `0x18001fbb7`
- `IisRTL!PuDbgPrint` at `0x18001fc17`
- `IisRTL!PuDbgPrint` at `0x18001fc5f`
- `IisRTL!PuDbgPrint` at `0x18001ff22`
- `IisRTL!PuDbgPrint` at `0x18001ffb0`
- `IisRTL!PuDbgPrint` at `0x18001fff5`
- `IisRTL!PuDbgPrint` at `0x18001fac6`
- `IisRTL!PuDbgPrint` at `0x18001fb1e`
- `IisRTL!PuDbgPrint` at `0x18001fb68`
- `IisRTL!PuDbgPrint` at `0x18001fbb7`
- `IisRTL!PuDbgPrint` at `0x18001fc17`
- `IisRTL!PuDbgPrint` at `0x18001fc5f`
- `IisRTL!PuDbgPrint` at `0x18001ff22`
- `IisRTL!PuDbgPrint` at `0x18001ffb0`
- `IisRTL!PuDbgPrint` at `0x18001fff5`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001fae8`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001fae8`
- `IisRTL!?TryWriteLock@CReaderWriterLock3@@QEAA_NXZ` at `0x18001fad3`
- `IisRTL!?TryWriteLock@CReaderWriterLock3@@QEAA_NXZ` at `0x18001fad3`
- `IISCFG!DllGetSimpleObjectByIDEx` at `0x18001fdbd`
- `IISCFG!DllGetSimpleObjectByIDEx` at `0x18001fdbd`

## string_xrefs

- `0x18001fafe`: `InitWorker ReadLock\n`
- `0x18001fc3f`: `InitWorker WriteLock\n`
- `0x18001ff6f`: `Write`

## pseudocode

```c
__int64 __fastcall InitWorker(int a1, char *a2, char *a3, char *a4, int a5)
{
  CListenerController *v5; // rsi
  signed __int32 v9; // ebx
  char v10; // al
  signed __int32 v11; // edi
  int Object; // ebx
  bool v13; // r14
  __int64 v14; // r8
  struct CMDBaseObject *BaseObject; // rax
  struct CHandleTable **v16; // rcx
  unsigned int v17; // r8d
  struct CMDHandle *CMDHandle; // rax
  CHandleTable *v19; // rcx
  CMDHandle *v20; // rbp
  const char *v21; // rax
  __int64 v23; // [rsp+40h] [rbp-58h] BYREF
  _QWORD v24[10]; // [rsp+48h] [rbp-50h] BYREF

  v5 = 0;
  v23 = 0;
  v24[0] = 0;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
      3489,
      "InitWorker",
      "Enter InitWorker g_dwInitialized = %d\n",
      g_dwInitialized);
  if ( !CReaderWriterLock3::TryWriteLock((CReaderWriterLock3 *)&g_LockMasterResource) )
  {
    CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)&g_LockMasterResource);
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(g_pDebug, "inetsrv\\iis\\mb\\metadata\\metasub.cxx", 3499, "InitWorker", "InitWorker ReadLock\n");
    v9 = g_dwInitialized;
    v10 = g_dwDebugFlags;
    while ( 1 )
    {
      if ( !v9 )
      {
        CReaderWriterLock3::ConvertSharedToExclusive((CReaderWriterLock3 *)&g_LockMasterResource);
        goto LABEL_18;
      }
      if ( (v10 & 3) != 0 )
        PuDbgPrint(g_pDebug, "inetsrv\\iis\\mb\\metadata\\metasub.cxx", 3508, "InitWorker", "InitWorker Old = %d\n", v9);
      v11 = _InterlockedCompareExchange((volatile signed __int32 *)&g_dwInitialized, v9 + 1, v9);
      v10 = g_dwDebugFlags;
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
          3516,
          "InitWorker",
          "InitWorker Old = %d New = %d\n",
          v9,
          v11);
        v10 = g_dwDebugFlags;
      }
      if ( v9 == v11 )
        break;
      v9 = v11;
    }
    Object = g_hresInitWarning;
    v13 = 1;
    if ( (v10 & 3) == 0 )
      goto LABEL_61;
    v14 = 3527;
    goto LABEL_16;
  }
LABEL_18:
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(g_pDebug, "inetsrv\\iis\\mb\\metadata\\metasub.cxx", 3542, "InitWorker", "InitWorker WriteLock\n");
  v13 = 0;
  if ( _InterlockedIncrement((volatile signed __int32 *)&g_dwInitialized) == 1 )
  {
    InitializeGlobalsToNull();
    BaseObject = CMDBaseObject::CreateBaseObject("MasterRoot");
    g_pboMasterRoot = BaseObject;
    if ( !BaseObject || !STRAU::IsValid((struct CMDBaseObject *)((char *)BaseObject + 8)) )
    {
      Object = -2147024882;
      goto LABEL_57;
    }
    *((_QWORD *)g_pboMasterRoot + 23) = 0;
    Object = CHandleTable::CreateObject(v16);
    if ( Object >= 0 )
    {
      if ( !g_pHandleTable )
      {
        Object = -2147418113;
        goto LABEL_54;
      }
      if ( !g_pboMasterRoot )
      {
        Object = -2147467259;
        goto LABEL_54;
      }
      CMDHandle = CMDHandle::CreateCMDHandle(g_pboMasterRoot, 1u, v17, 0, 0);
      v20 = CMDHandle;
      if ( !CMDHandle )
      {
        Object = -2147024882;
        goto LABEL_54;
      }
      Object = CHandleTable::Add(v19, CMDHandle);
      if ( Object < 0 )
      {
        CMDHandle::Destroy(v20);
      }
      else
      {
        g_phEventHandles = CreateEventA(0, 1, 0, 0);
        if ( g_phEventHandles )
        {
          *(&g_phEventHandles + 1) = CreateEventA(0, 1, 0, 0);
          if ( *(&g_phEventHandles + 1) )
          {
            Object = HASH_BUFFER_ENTRY::Initialize();
            if ( Object < 0 )
              goto LABEL_57;
            Object = SetStorageSecurityDescriptor();
            if ( Object < 0 )
              goto LABEL_57;
            Object = DllGetSimpleObjectByIDEx(1, &IID_ISimpleTableDispenser2, &v23, L"IIS");
            if ( Object < 0 )
              goto LABEL_57;
            Object = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))v23)(
                       v23,
                       &IID_IAdvancedTableDispenser,
                       v24);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
            v23 = 0;
            if ( Object < 0 )
              goto LABEL_57;
            Object = (*(__int64 (__fastcall **)(_QWORD, struct ICatalogErrorLogger2 **))(*(_QWORD *)v24[0] + 48LL))(
                       v24[0],
                       &g_pEventLog);
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v24[0] + 16LL))(v24[0]);
            v24[0] = 0;
            if ( Object < 0 )
              goto LABEL_57;
            Object = SetDataFile();
            if ( Object < 0 )
              goto LABEL_57;
            Object = ReadAllDataFromXML(a2, a3, a4, a1, a5);
            if ( Object == -2147024894 )
              Object = ReadAllDataFromBin(a2, a3, a1);
            if ( Object < 0 )
              goto LABEL_57;
            CheckForNewMetabaseVersion();
            if ( g_dwMajorVersionNumber )
            {
              Object = CListenerController::InitializeListenerController();
              if ( Object < 0 )
                goto LABEL_57;
              if ( !g_dwEnableEditWhileRunning )
              {
                v5 = g_pListenerController;
                if ( g_pListenerController )
                  _InterlockedAdd((volatile signed __int32 *)g_pListenerController + 17, 1u);
                goto LABEL_60;
              }
              Object = CListenerController::Start(g_pListenerController);
              if ( Object < 0 )
                goto LABEL_57;
              goto LABEL_60;
            }
            Object = -2146646014;
            goto LABEL_57;
          }
        }
        Object = GetLastHResult();
      }
LABEL_54:
      if ( Object < 0 )
        goto LABEL_57;
LABEL_60:
      g_hresInitWarning = Object;
      goto LABEL_61;
    }
LABEL_57:
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
        3711,
        "InitWorker",
        "InitWorker Failed hr = 0x%08x!!!\n",
        Object);
    _InterlockedDecrement((volatile signed __int32 *)&g_dwInitialized);
    TerminateWorker();
    goto LABEL_60;
  }
  Object = g_hresInitWarning;
  if ( (g_dwDebugFlags & 3) != 0 )
  {
    v14 = 3558;
LABEL_16:
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
      v14,
      "InitWorker",
      "InitWorker Done hr = 0x%08x g_dwInitialized = %d\n",
      Object,
      g_dwInitialized);
  }
LABEL_61:
  CReaderWriterLock3::ReadOrWriteUnlock((CReaderWriterLock3 *)&g_LockMasterResource, v13);
  if ( v5 )
  {
    CListenerController::Stop(v5, 0);
    CListenerController::Release(v5);
  }
  if ( (g_dwDebugFlags & 3) != 0 )
  {
    v21 = "Read";
    if ( !v13 )
      v21 = "Write";
    PuDbgPrint(g_pDebug, "inetsrv\\iis\\mb\\metadata\\metasub.cxx", 3734, "InitWorker", "InitWorker %sUnlock\n", v21);
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
        3739,
        "InitWorker",
        "End InitWorker hr = 0x%08x g_dwInitialized = %d\n",
        Object,
        g_dwInitialized);
  }
  return (unsigned int)Object;
}

```

## disassembly

```asm
0x18001fa58  mov     r11, rsp
0x18001fa5b  mov     [r11+20h], r9
0x18001fa5f  push    rbx
0x18001fa60  push    rbp
0x18001fa61  push    rsi
0x18001fa62  push    rdi
0x18001fa63  push    r12
0x18001fa65  push    r13
0x18001fa67  push    r14
0x18001fa69  push    r15
0x18001fa6b  sub     rsp, 58h
0x18001fa6f  xor     esi, esi
0x18001fa71  mov     qword ptr [r11-58h], 0
0x18001fa79  mov     r14b, 3
0x18001fa7c  mov     qword ptr [r11-50h], 0
0x18001fa84  test    byte ptr cs:g_dwDebugFlags, r14b
0x18001fa8b  mov     r15, r8
0x18001fa8e  mov     r12, rdx
0x18001fa91  mov     r13d, ecx
0x18001fa94  jz      short loc_18001FACC
0x18001fa96  mov     eax, cs:?g_dwInitialized@@3KC; ulong volatile g_dwInitialized
0x18001fa9c  lea     r9, aInitworker; "InitWorker"
0x18001faa3  mov     rcx, cs:g_pDebug
0x18001faaa  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18001fab1  mov     dword ptr [rsp+98h+var_70], eax
0x18001fab5  mov     r8d, 0DA1h
0x18001fabb  lea     rax, aEnterInitworke; "Enter InitWorker g_dwInitialized = %d\n"
0x18001fac2  mov     [r11-78h], rax
0x18001fac6  call    cs:__imp_PuDbgPrint
0x18001facc  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x18001fad3  call    cs:__imp_?TryWriteLock@CReaderWriterLock3@@QEAA_NXZ; CReaderWriterLock3::TryWriteLock(void)
0x18001fad9  test    al, al
0x18001fadb  jnz     loc_18001FC2F
0x18001fae1  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x18001fae8  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18001faee  test    byte ptr cs:g_dwDebugFlags, r14b
0x18001faf5  jz      short loc_18001FB24
0x18001faf7  mov     rcx, cs:g_pDebug
0x18001fafe  lea     rax, aInitworkerRead; "InitWorker ReadLock\n"
0x18001fb05  lea     r9, aInitworker; "InitWorker"
0x18001fb0c  mov     qword ptr [rsp+98h+var_78], rax
0x18001fb11  mov     r8d, 0DABh
0x18001fb17  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18001fb1e  call    cs:__imp_PuDbgPrint
0x18001fb24  mov     ebx, cs:?g_dwInitialized@@3KC; ulong volatile g_dwInitialized
0x18001fb2a  mov     eax, cs:g_dwDebugFlags
0x18001fb30  test    ebx, ebx
0x18001fb32  jz      loc_18001FC22
0x18001fb38  test    r14b, al
0x18001fb3b  jz      short loc_18001FB6E
0x18001fb3d  mov     rcx, cs:g_pDebug
0x18001fb44  lea     rax, aInitworkerOldD; "InitWorker Old = %d\n"
0x18001fb4b  mov     dword ptr [rsp+98h+var_70], ebx
0x18001fb4f  lea     r9, aInitworker; "InitWorker"
0x18001fb56  mov     r8d, 0DB4h
0x18001fb5c  mov     qword ptr [rsp+98h+var_78], rax
0x18001fb61  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18001fb68  call    cs:__imp_PuDbgPrint
0x18001fb6e  lea     ecx, [rbx+1]
0x18001fb71  mov     eax, ebx
0x18001fb73  lock cmpxchg cs:?g_dwInitialized@@3KC, ecx; ulong volatile g_dwInitialized
0x18001fb7b  mov     edi, eax
0x18001fb7d  mov     eax, cs:g_dwDebugFlags
0x18001fb83  test    r14b, al
0x18001fb86  jz      short loc_18001FBC3
0x18001fb88  mov     rcx, cs:g_pDebug
0x18001fb8f  lea     rax, aInitworkerOldD_0; "InitWorker Old = %d New = %d\n"
0x18001fb96  mov     [rsp+98h+var_68], edi
0x18001fb9a  lea     r9, aInitworker; "InitWorker"
0x18001fba1  mov     dword ptr [rsp+98h+var_70], ebx
0x18001fba5  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18001fbac  mov     r8d, 0DBCh
0x18001fbb2  mov     qword ptr [rsp+98h+var_78], rax
0x18001fbb7  call    cs:__imp_PuDbgPrint
0x18001fbbd  mov     eax, cs:g_dwDebugFlags
0x18001fbc3  cmp     ebx, edi
0x18001fbc5  jz      short loc_18001FBCE
0x18001fbc7  mov     ebx, edi
0x18001fbc9  jmp     loc_18001FB30
0x18001fbce  mov     ebx, cs:?g_hresInitWarning@@3JA; long g_hresInitWarning
0x18001fbd4  mov     r14d, 1
0x18001fbda  test    al, 3
0x18001fbdc  jz      loc_18001FF3A
0x18001fbe2  mov     r8d, 0DC7h
0x18001fbe8  mov     eax, cs:?g_dwInitialized@@3KC; ulong volatile g_dwInitialized
0x18001fbee  lea     r9, aInitworker; "InitWorker"
0x18001fbf5  mov     rcx, cs:g_pDebug
0x18001fbfc  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18001fc03  mov     [rsp+98h+var_68], eax
0x18001fc07  lea     rax, aInitworkerDone; "InitWorker Done hr = 0x%08x g_dwInitial"...
0x18001fc0e  mov     dword ptr [rsp+98h+var_70], ebx
0x18001fc12  mov     qword ptr [rsp+98h+var_78], rax
0x18001fc17  call    cs:__imp_PuDbgPrint
0x18001fc1d  jmp     loc_18001FF3A
0x18001fc22  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x18001fc29  call    cs:__imp_?ConvertSharedToExclusive@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ConvertSharedToExclusive(void)
0x18001fc2f  test    byte ptr cs:g_dwDebugFlags, r14b
0x18001fc36  jz      short loc_18001FC65
0x18001fc38  mov     rcx, cs:g_pDebug
0x18001fc3f  lea     rax, aInitworkerWrit; "InitWorker WriteLock\n"
0x18001fc46  lea     r9, aInitworker; "InitWorker"
0x18001fc4d  mov     qword ptr [rsp+98h+var_78], rax
0x18001fc52  mov     r8d, 0DD6h
0x18001fc58  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18001fc5f  call    cs:__imp_PuDbgPrint
0x18001fc65  mov     edi, 1
0x18001fc6a  xor     r14b, r14b
0x18001fc6d  mov     eax, edi
0x18001fc6f  lock xadd cs:?g_dwInitialized@@3KC, eax; ulong volatile g_dwInitialized
0x18001fc77  add     eax, edi
0x18001fc79  cmp     eax, edi
0x18001fc7b  jz      short loc_18001FC9B
0x18001fc7d  test    byte ptr cs:g_dwDebugFlags, 3
0x18001fc84  mov     ebx, cs:?g_hresInitWarning@@3JA; long g_hresInitWarning
0x18001fc8a  jz      loc_18001FF3A
0x18001fc90  mov     r8d, 0DE6h
0x18001fc96  jmp     loc_18001FBE8
0x18001fc9b  call    ?InitializeGlobalsToNull@@YAXXZ; InitializeGlobalsToNull(void)
0x18001fca0  lea     rcx, aMasterroot; "MasterRoot"
0x18001fca7  call    ?CreateBaseObject@CMDBaseObject@@SAPEAV1@PEAD@Z; CMDBaseObject::CreateBaseObject(char *)
0x18001fcac  mov     cs:?g_pboMasterRoot@@3PEAVCMDBaseObject@@EA, rax; CMDBaseObject * g_pboMasterRoot
0x18001fcb3  test    rax, rax
0x18001fcb6  jz      loc_18001FEE9
0x18001fcbc  lea     rcx, [rax+8]
0x18001fcc0  call    cs:__imp_?IsValid@STRAU@@QEAAHXZ; STRAU::IsValid(void)
0x18001fcc6  test    eax, eax
0x18001fcc8  jz      loc_18001FEE9
0x18001fcce  mov     rax, cs:?g_pboMasterRoot@@3PEAVCMDBaseObject@@EA; CMDBaseObject * g_pboMasterRoot
0x18001fcd5  mov     [rax+0B8h], rsi
0x18001fcdc  call    ?CreateObject@CHandleTable@@SAJPEAPEAV1@@Z; CHandleTable::CreateObject(CHandleTable * *)
0x18001fce1  mov     ebx, eax
0x18001fce3  test    eax, eax
0x18001fce5  js      loc_18001FEEE
0x18001fceb  cmp     cs:?g_pHandleTable@@3PEAVCHandleTable@@EA, rsi; CHandleTable * g_pHandleTable
0x18001fcf2  jnz     short loc_18001FCFE
0x18001fcf4  mov     ebx, 8000FFFFh
0x18001fcf9  jmp     loc_18001FEE3
0x18001fcfe  mov     rcx, cs:?g_pboMasterRoot@@3PEAVCMDBaseObject@@EA; struct CMDBaseObject *
0x18001fd05  test    rcx, rcx
0x18001fd08  jnz     short loc_18001FD14
0x18001fd0a  mov     ebx, 80004005h
0x18001fd0f  jmp     loc_18001FEE3
0x18001fd14  xor     r9d, r9d; unsigned int
0x18001fd17  mov     [rsp+98h+var_78], esi; int
0x18001fd1b  mov     edx, edi; unsigned int
0x18001fd1d  call    ?CreateCMDHandle@CMDHandle@@SAPEAV1@PEAVCMDBaseObject@@KKKH@Z; CMDHandle::CreateCMDHandle(CMDBaseObject *,ulong,ulong,ulong,int)
0x18001fd22  mov     rbp, rax
0x18001fd25  test    rax, rax
0x18001fd28  jnz     short loc_18001FD34
0x18001fd2a  mov     ebx, 8007000Eh
0x18001fd2f  jmp     loc_18001FEE3
0x18001fd34  mov     rdx, rbp; struct CMDHandle *
0x18001fd37  call    ?Add@CHandleTable@@QEAAJPEAVCMDHandle@@@Z; CHandleTable::Add(CMDHandle *)
0x18001fd3c  mov     ebx, eax
0x18001fd3e  test    eax, eax
0x18001fd40  js      loc_18001FEDB
0x18001fd46  xor     r9d, r9d; lpName
0x18001fd49  xor     r8d, r8d; bInitialState
0x18001fd4c  mov     edx, edi; bManualReset
0x18001fd4e  xor     ecx, ecx; lpEventAttributes
0x18001fd50  call    cs:__imp_CreateEventA
0x18001fd56  mov     qword ptr cs:?g_phEventHandles@@3PAPEAXA, rax; void * near * g_phEventHandles
0x18001fd5d  test    rax, rax
0x18001fd60  jnz     short loc_18001FD6E
0x18001fd62  call    ?GetLastHResult@@YAJXZ; GetLastHResult(void)
0x18001fd67  mov     ebx, eax
0x18001fd69  jmp     loc_18001FEE3
0x18001fd6e  xor     r9d, r9d; lpName
0x18001fd71  xor     r8d, r8d; bInitialState
0x18001fd74  mov     edx, edi; bManualReset
0x18001fd76  xor     ecx, ecx; lpEventAttributes
0x18001fd78  call    cs:__imp_CreateEventA
0x18001fd7e  mov     qword ptr cs:?g_phEventHandles@@3PAPEAXA+8, rax; void * near * g_phEventHandles
0x18001fd85  test    rax, rax
0x18001fd88  jz      short loc_18001FD62
0x18001fd8a  call    ?Initialize@HASH_BUFFER_ENTRY@@SAJXZ; HASH_BUFFER_ENTRY::Initialize(void)
0x18001fd8f  mov     ebx, eax
0x18001fd91  test    eax, eax
0x18001fd93  js      loc_18001FEEE
0x18001fd99  call    ?SetStorageSecurityDescriptor@@YAJXZ; SetStorageSecurityDescriptor(void)
0x18001fd9e  mov     ebx, eax
0x18001fda0  test    eax, eax
0x18001fda2  js      loc_18001FEEE
0x18001fda8  lea     r9, aIis; "IIS"
0x18001fdaf  mov     ecx, edi
0x18001fdb1  lea     r8, [rsp+98h+var_58]
0x18001fdb6  lea     rdx, IID_ISimpleTableDispenser2
0x18001fdbd  call    cs:__imp_DllGetSimpleObjectByIDEx
0x18001fdc3  mov     ebx, eax
0x18001fdc5  test    eax, eax
0x18001fdc7  js      loc_18001FEEE
0x18001fdcd  mov     rcx, [rsp+98h+var_58]
0x18001fdd2  lea     r8, [rsp+98h+var_50]
0x18001fdd7  lea     rdx, IID_IAdvancedTableDispenser
0x18001fdde  mov     rax, [rcx]
0x18001fde1  mov     rax, [rax]
0x18001fde4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fde9  mov     rcx, [rsp+98h+var_58]
0x18001fdee  mov     ebx, eax
0x18001fdf0  mov     rax, [rcx]
0x18001fdf3  mov     rax, [rax+10h]
0x18001fdf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fdfc  mov     [rsp+98h+var_58], rsi
0x18001fe01  test    ebx, ebx
0x18001fe03  js      loc_18001FEEE
0x18001fe09  mov     rcx, [rsp+98h+var_50]
0x18001fe0e  lea     rdx, ?g_pEventLog@@3PEAUICatalogErrorLogger2@@EA; ICatalogErrorLogger2 * g_pEventLog
0x18001fe15  mov     rax, [rcx]
0x18001fe18  mov     rax, [rax+30h]
0x18001fe1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe21  mov     rcx, [rsp+98h+var_50]
0x18001fe26  mov     ebx, eax
0x18001fe28  mov     rax, [rcx]
0x18001fe2b  mov     rax, [rax+10h]
0x18001fe2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe34  mov     [rsp+98h+var_50], rsi
0x18001fe39  test    ebx, ebx
0x18001fe3b  js      loc_18001FEEE
0x18001fe41  call    ?SetDataFile@@YAJXZ; SetDataFile(void)
0x18001fe46  mov     ebx, eax
0x18001fe48  test    eax, eax
0x18001fe4a  js      loc_18001FEEE
0x18001fe50  mov     eax, [rsp+98h+arg_20]
0x18001fe57  mov     r9d, r13d; int
0x18001fe5a  mov     r8, [rsp+98h+lpMultiByteStr]; lpMultiByteStr
0x18001fe62  mov     rdx, r15; char *
0x18001fe65  mov     rcx, r12; char *
0x18001fe68  mov     [rsp+98h+var_78], eax; int
0x18001fe6c  call    ?ReadAllDataFromXML@@YAJPEAD00HH@Z; ReadAllDataFromXML(char *,char *,char *,int,int)
0x18001fe71  mov     ebx, eax
0x18001fe73  cmp     eax, 80070002h
0x18001fe78  jnz     short loc_18001FE8A
0x18001fe7a  mov     r8d, r13d; int
0x18001fe7d  mov     rdx, r15; char *
0x18001fe80  mov     rcx, r12; char *
0x18001fe83  call    ?ReadAllDataFromBin@@YAJPEAD0H@Z; ReadAllDataFromBin(char *,char *,int)
0x18001fe88  mov     ebx, eax
0x18001fe8a  test    ebx, ebx
0x18001fe8c  js      short loc_18001FEEE
0x18001fe8e  call    ?CheckForNewMetabaseVersion@@YAXXZ; CheckForNewMetabaseVersion(void)
0x18001fe93  cmp     cs:?g_dwMajorVersionNumber@@3KA, edi; ulong g_dwMajorVersionNumber
0x18001fe99  jb      short loc_18001FED4
0x18001fe9b  call    ?InitializeListenerController@CListenerController@@SAJXZ; CListenerController::InitializeListenerController(void)
0x18001fea0  mov     ebx, eax
0x18001fea2  test    eax, eax
0x18001fea4  js      short loc_18001FEEE
0x18001fea6  cmp     cs:?g_dwEnableEditWhileRunning@@3KA, esi; ulong g_dwEnableEditWhileRunning
0x18001feac  jz      short loc_18001FEC2
0x18001feae  mov     rcx, cs:?g_pListenerController@@3PEAVCListenerController@@EA; this
0x18001feb5  call    ?Start@CListenerController@@QEAAJXZ; CListenerController::Start(void)
0x18001feba  mov     ebx, eax
0x18001febc  test    eax, eax
0x18001febe  js      short loc_18001FEEE
0x18001fec0  jmp     short loc_18001FF34
0x18001fec2  mov     rsi, cs:?g_pListenerController@@3PEAVCListenerController@@EA; CListenerController * g_pListenerController
0x18001fec9  test    rsi, rsi
0x18001fecc  jz      short loc_18001FF34
0x18001fece  lock add [rsi+44h], edi
0x18001fed2  jmp     short loc_18001FF34
0x18001fed4  mov     ebx, 800CC802h
0x18001fed9  jmp     short loc_18001FEEE
0x18001fedb  mov     rcx, rbp; this
0x18001fede  call    ?Destroy@CMDHandle@@QEAAXXZ; CMDHandle::Destroy(void)
0x18001fee3  test    ebx, ebx
0x18001fee5  jns     short loc_18001FF34
0x18001fee7  jmp     short loc_18001FEEE
0x18001fee9  mov     ebx, 8007000Eh
0x18001feee  test    byte ptr cs:g_dwDebugFlags, 3
0x18001fef5  jz      short loc_18001FF28
0x18001fef7  mov     rcx, cs:g_pDebug
0x18001fefe  lea     rax, aInitworkerFail; "InitWorker Failed hr = 0x%08x!!!\n"
0x18001ff05  mov     dword ptr [rsp+98h+var_70], ebx
0x18001ff09  lea     r9, aInitworker; "InitWorker"
0x18001ff10  mov     r8d, 0E7Fh
0x18001ff16  mov     qword ptr [rsp+98h+var_78], rax
0x18001ff1b  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18001ff22  call    cs:__imp_PuDbgPrint
0x18001ff28  lock dec cs:?g_dwInitialized@@3KC; ulong volatile g_dwInitialized
0x18001ff2f  call    ?TerminateWorker@@YAXXZ; TerminateWorker(void)
0x18001ff34  mov     cs:?g_hresInitWarning@@3JA, ebx; long g_hresInitWarning
0x18001ff3a  mov     dl, r14b
0x18001ff3d  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x18001ff44  call    cs:__imp_?ReadOrWriteUnlock@CReaderWriterLock3@@QEAAX_N@Z; CReaderWriterLock3::ReadOrWriteUnlock(bool)
0x18001ff4a  test    rsi, rsi
0x18001ff4d  jz      short loc_18001FF61
0x18001ff4f  xor     edx, edx
0x18001ff51  mov     rcx, rsi
0x18001ff54  call    ?Stop@CListenerController@@QEAAJW4eSTATE@@@Z; CListenerController::Stop(eSTATE)
0x18001ff59  mov     rcx, rsi; this
0x18001ff5c  call    ?Release@CListenerController@@QEAAKXZ; CListenerController::Release(void)
0x18001ff61  mov     eax, cs:g_dwDebugFlags
0x18001ff67  test    al, 3
0x18001ff69  jz      loc_18001FFFB
0x18001ff6f  lea     rcx, aWrite; "Write"
0x18001ff76  test    r14b, r14b
0x18001ff79  lea     rax, aRead; "Read"
0x18001ff80  mov     r8d, 0E96h
0x18001ff86  cmovz   rax, rcx
0x18001ff8a  lea     r9, aInitworker; "InitWorker"
0x18001ff91  mov     rcx, cs:g_pDebug
  ... truncated ...
```
