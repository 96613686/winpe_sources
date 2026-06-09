# TerminateWorker1(int)

- ea: `0x180026cb8`
- end: `0x180027189`
- name: `?TerminateWorker1@@YAJH@Z`
- size: `1233`
- prototype: `__int64 __fastcall(int)`
- caller_count: `3`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001a0c0`
- `0x18001a584`
- `0x18001aa04`

## callees

- `0x18000f2d0`
- `0x18001f638`
- `0x180023548`
- `0x180026cb8`
- `0x180027190`
- `0x180028f34`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180027127`
- `ole32!CoTaskMemFree` at `0x180027127`
- `IisRTL!?ReadOrWriteUnlock@CReaderWriterLock3@@QEAAX_N@Z` at `0x180027116`
- `IisRTL!?ReadOrWriteUnlock@CReaderWriterLock3@@QEAAX_N@Z` at `0x180027116`
- `IisRTL!?ConvertSharedToExclusive@CReaderWriterLock3@@QEAAXXZ` at `0x180026edd`
- `IisRTL!?ConvertSharedToExclusive@CReaderWriterLock3@@QEAAXXZ` at `0x180026edd`
- `IisRTL!PuDbgPrint` at `0x180026d38`
- `IisRTL!PuDbgPrint` at `0x180026d8b`
- `IisRTL!PuDbgPrint` at `0x180026dd0`
- `IisRTL!PuDbgPrint` at `0x180026e26`
- `IisRTL!PuDbgPrint` at `0x180026e85`
- `IisRTL!PuDbgPrint` at `0x180026ecb`
- `IisRTL!PuDbgPrint` at `0x180026f15`
- `IisRTL!PuDbgPrint` at `0x180026f7e`
- `IisRTL!PuDbgPrint` at `0x180026fcc`
- `IisRTL!PuDbgPrint` at `0x180027011`
- `IisRTL!PuDbgPrint` at `0x180027048`
- `IisRTL!PuDbgPrint` at `0x1800270b5`
- `IisRTL!PuDbgPrint` at `0x180027106`
- `IisRTL!PuDbgPrint` at `0x180027167`
- `IisRTL!PuDbgPrint` at `0x180026d38`
- `IisRTL!PuDbgPrint` at `0x180026d8b`
- `IisRTL!PuDbgPrint` at `0x180026dd0`
- `IisRTL!PuDbgPrint` at `0x180026e26`
- `IisRTL!PuDbgPrint` at `0x180026e85`
- `IisRTL!PuDbgPrint` at `0x180026ecb`
- `IisRTL!PuDbgPrint` at `0x180026f15`
- `IisRTL!PuDbgPrint` at `0x180026f7e`
- `IisRTL!PuDbgPrint` at `0x180026fcc`
- `IisRTL!PuDbgPrint` at `0x180027011`
- `IisRTL!PuDbgPrint` at `0x180027048`
- `IisRTL!PuDbgPrint` at `0x1800270b5`
- `IisRTL!PuDbgPrint` at `0x180027106`
- `IisRTL!PuDbgPrint` at `0x180027167`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180026d5d`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180026d5d`
- `IisRTL!?TryWriteLock@CReaderWriterLock3@@QEAA_NXZ` at `0x180026d45`
- `IisRTL!?TryWriteLock@CReaderWriterLock3@@QEAA_NXZ` at `0x180026d45`

## string_xrefs

- `0x1800270d0`: `Write`
- `0x180026d73`: `TerminateWorker1 ReadLock\n`
- `0x180026efd`: `TerminateWorker1 WriteLock\n`

## pseudocode

```c
__int64 __fastcall TerminateWorker1(int a1)
{
  int v1; // ebx
  struct _IIS_CRYPTO_BLOB *v2; // rsi
  bool v4; // r15
  signed __int32 i; // edi
  signed __int32 v6; // eax
  signed __int32 v7; // r14d
  __int64 v8; // r8
  int inited; // eax
  __int64 v10; // rcx
  const char *v11; // rax
  _QWORD v13[2]; // [rsp+40h] [rbp-38h] BYREF
  int v14; // [rsp+50h] [rbp-28h]
  __int128 v15; // [rsp+58h] [rbp-20h]
  __int64 v16; // [rsp+68h] [rbp-10h]
  struct _IIS_CRYPTO_BLOB *v17; // [rsp+C8h] [rbp+50h] BYREF

  v1 = 0;
  v2 = 0;
  v13[1] = 0;
  v14 = 0;
  v13[0] = &IIS_CRYPTO_STORAGE::`vftable';
  v16 = 0;
  v15 = 0;
  v17 = 0;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
      3757,
      "TerminateWorker1",
      "Enter TerminateWorker1 g_dwInitialized = %d\n",
      g_dwInitialized);
  if ( CReaderWriterLock3::TryWriteLock((CReaderWriterLock3 *)&g_LockMasterResource) )
  {
LABEL_21:
    v4 = 0;
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
        3819,
        "TerminateWorker1",
        "TerminateWorker1 WriteLock\n");
    if ( g_dwInitialized )
    {
      if ( g_dwInitialized == 1 )
      {
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
            3833,
            "TerminateWorker1",
            "TerminateWorker1 Stopping EWR\n");
        if ( g_pListenerController )
        {
          v1 = CListenerController::Stop(g_pListenerController, 1);
          if ( v1 < 0 )
            goto LABEL_44;
        }
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
            3845,
            "TerminateWorker1",
            "TerminateWorker1 Getting key\n");
        inited = InitStorageAndSessionKey((struct IIS_CRYPTO_STORAGE *)v13, &v17);
        v1 = inited;
        if ( inited < 0 )
        {
          if ( (g_dwDebugFlags & 3) != 0 )
            PuDbgPrint(
              g_pDebug,
              "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
              3851,
              "TerminateWorker1",
              "TerminateWorker1.InitStorageAndSessionKey:Failed - error 0x%0x\n",
              inited);
          v2 = v17;
          goto LABEL_44;
        }
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
            3857,
            "TerminateWorker1",
            "TerminateWorker1 Saving data\n");
        v2 = v17;
        v1 = SaveAllData(v10, (struct IIS_CRYPTO_STORAGE *)v13, v17, 0, 0, 0, a1, 1);
        if ( v1 < 0 )
          goto LABEL_44;
      }
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)&g_dwInitialized, 0xFFFFFFFF) == 1 )
      {
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
            3876,
            "TerminateWorker1",
            "TerminateWorker1 Last Terminate\n");
        TerminateWorker();
      }
      goto LABEL_44;
    }
    v1 = -2146646016;
    if ( (g_dwDebugFlags & 3) == 0 )
      goto LABEL_48;
    v8 = 3826;
  }
  else
  {
    v4 = 1;
    CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)&g_LockMasterResource);
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
        3765,
        "TerminateWorker1",
        "TerminateWorker1 ReadLock\n");
    for ( i = g_dwInitialized; ; i = v7 )
    {
      if ( i == 1 )
      {
        CReaderWriterLock3::ConvertSharedToExclusive((CReaderWriterLock3 *)&g_LockMasterResource);
        goto LABEL_21;
      }
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
          3774,
          "TerminateWorker1",
          "TerminateWorker1 Old = %d\n",
          i);
      if ( !i )
        break;
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)&g_dwInitialized, i - 1, i);
      v7 = v6;
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
          3791,
          "TerminateWorker1",
          "TerminateWorker1 Old = %d New = %d\n",
          i,
          v6);
      if ( i == v7 )
      {
        if ( (g_dwDebugFlags & 3) == 0 )
          goto LABEL_48;
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
          3798,
          "TerminateWorker1",
          "TerminateWorker1 Done hr = 0x%08x g_dwInitialized = %d\n",
          0,
          g_dwInitialized);
        goto LABEL_44;
      }
    }
    v1 = -2146646016;
    if ( (g_dwDebugFlags & 3) == 0 )
      goto LABEL_48;
    v8 = 3781;
  }
  PuDbgPrint(
    g_pDebug,
    "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
    v8,
    "TerminateWorker1",
    "TerminateWorker1 Not Initialized hr = 0x%08x!!!\n",
    -2146646016);
LABEL_44:
  if ( (g_dwDebugFlags & 3) != 0 )
  {
    v11 = "Read";
    if ( !v4 )
      v11 = "Write";
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
      3883,
      "TerminateWorker1",
      "TerminateWorker1 %sUnlock\n",
      v11);
  }
LABEL_48:
  CReaderWriterLock3::ReadOrWriteUnlock((CReaderWriterLock3 *)&g_LockMasterResource, v4);
  if ( v2 )
  {
    *(_BYTE *)v2 = 88;
    CoTaskMemFree(v2);
  }
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
      3895,
      "TerminateWorker1",
      "End TerminateWorker1 hr = 0x%08x g_dwInitialized = %d\n",
      v1,
      g_dwInitialized);
  IIS_CRYPTO_STORAGE::~IIS_CRYPTO_STORAGE((IIS_CRYPTO_STORAGE *)v13);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180026cb8  push    rbp
0x180026cba  push    rbx
0x180026cbb  push    rsi
0x180026cbc  push    rdi
0x180026cbd  push    r12
0x180026cbf  push    r13
0x180026cc1  push    r14
0x180026cc3  push    r15
0x180026cc5  mov     rbp, rsp
0x180026cc8  sub     rsp, 78h
0x180026ccc  xor     ebx, ebx
0x180026cce  lea     rax, ??_7IIS_CRYPTO_STORAGE@@6B@; const IIS_CRYPTO_STORAGE::`vftable'
0x180026cd5  xor     esi, esi
0x180026cd7  mov     [rbp+var_30], rbx
0x180026cdb  mov     r13b, 3
0x180026cde  mov     [rbp+var_28], ebx
0x180026ce1  test    byte ptr cs:g_dwDebugFlags, r13b
0x180026ce8  lea     r14, aTerminateworke_8; "TerminateWorker1"
0x180026cef  xorps   xmm0, xmm0
0x180026cf2  mov     [rbp+var_38], rax
0x180026cf6  mov     r12d, ecx
0x180026cf9  mov     [rbp+var_10], rbx
0x180026cfd  movdqu  [rbp+var_20], xmm0
0x180026d02  mov     [rbp+arg_8], rsi
0x180026d06  lea     rdi, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x180026d0d  jz      short loc_180026D3E
0x180026d0f  mov     eax, cs:?g_dwInitialized@@3KC; ulong volatile g_dwInitialized
0x180026d15  mov     r9, r14
0x180026d18  mov     rcx, cs:g_pDebug
0x180026d1f  mov     r8d, 0EADh
0x180026d25  mov     [rsp+78h+var_50], eax
0x180026d29  mov     rdx, rdi
0x180026d2c  lea     rax, aEnterTerminate; "Enter TerminateWorker1 g_dwInitialized "...
0x180026d33  mov     [rsp+78h+var_58], rax
0x180026d38  call    cs:__imp_PuDbgPrint
0x180026d3e  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180026d45  call    cs:__imp_?TryWriteLock@CReaderWriterLock3@@QEAA_NXZ; CReaderWriterLock3::TryWriteLock(void)
0x180026d4b  test    al, al
0x180026d4d  jnz     loc_180026EEA
0x180026d53  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180026d5a  mov     r15b, 1
0x180026d5d  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180026d63  test    byte ptr cs:g_dwDebugFlags, r13b
0x180026d6a  jz      short loc_180026D91
0x180026d6c  mov     rcx, cs:g_pDebug
0x180026d73  lea     rax, aTerminateworke_2; "TerminateWorker1 ReadLock\n"
0x180026d7a  mov     r9, r14
0x180026d7d  mov     [rsp+78h+var_58], rax
0x180026d82  mov     r8d, 0EB5h
0x180026d88  mov     rdx, rdi
0x180026d8b  call    cs:__imp_PuDbgPrint
0x180026d91  mov     edi, cs:?g_dwInitialized@@3KC; ulong volatile g_dwInitialized
0x180026d97  cmp     edi, 1
0x180026d9a  jz      loc_180026ED6
0x180026da0  test    byte ptr cs:g_dwDebugFlags, r13b
0x180026da7  jz      short loc_180026DD6
0x180026da9  mov     rcx, cs:g_pDebug
0x180026db0  lea     rax, aTerminateworke_7; "TerminateWorker1 Old = %d\n"
0x180026db7  mov     [rsp+78h+var_50], edi
0x180026dbb  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x180026dc2  mov     r9, r14
0x180026dc5  mov     [rsp+78h+var_58], rax
0x180026dca  mov     r8d, 0EBEh
0x180026dd0  call    cs:__imp_PuDbgPrint
0x180026dd6  test    edi, edi
0x180026dd8  jz      loc_180026E90
0x180026dde  lea     ecx, [rdi-1]
0x180026de1  mov     eax, edi
0x180026de3  lock cmpxchg cs:?g_dwInitialized@@3KC, ecx; ulong volatile g_dwInitialized
0x180026deb  test    byte ptr cs:g_dwDebugFlags, r13b
0x180026df2  mov     r14d, eax
0x180026df5  jz      short loc_180026E2C
0x180026df7  mov     rcx, cs:g_pDebug
0x180026dfe  lea     r9, aTerminateworke_8; "TerminateWorker1"
0x180026e05  mov     [rsp+78h+var_48], eax
0x180026e09  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x180026e10  lea     rax, aTerminateworke_0; "TerminateWorker1 Old = %d New = %d\n"
0x180026e17  mov     [rsp+78h+var_50], edi
0x180026e1b  mov     r8d, 0ECFh
0x180026e21  mov     [rsp+78h+var_58], rax
0x180026e26  call    cs:__imp_PuDbgPrint
0x180026e2c  cmp     edi, r14d
0x180026e2f  jz      short loc_180026E40
0x180026e31  mov     edi, r14d
0x180026e34  lea     r14, aTerminateworke_8; "TerminateWorker1"
0x180026e3b  jmp     loc_180026D97
0x180026e40  test    byte ptr cs:g_dwDebugFlags, r13b
0x180026e47  lea     r14, aTerminateworke_8; "TerminateWorker1"
0x180026e4e  jz      loc_18002710C
0x180026e54  mov     eax, cs:?g_dwInitialized@@3KC; ulong volatile g_dwInitialized
0x180026e5a  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x180026e61  mov     rcx, cs:g_pDebug
0x180026e68  mov     r9, r14
0x180026e6b  mov     [rsp+78h+var_48], eax
0x180026e6f  mov     r8d, 0ED6h
0x180026e75  lea     rax, aTerminateworke_10; "TerminateWorker1 Done hr = 0x%08x g_dwI"...
0x180026e7c  mov     [rsp+78h+var_50], ebx
0x180026e80  mov     [rsp+78h+var_58], rax
0x180026e85  call    cs:__imp_PuDbgPrint
0x180026e8b  jmp     loc_1800270C0
0x180026e90  test    byte ptr cs:g_dwDebugFlags, r13b
0x180026e97  mov     eax, 800CC800h
0x180026e9c  mov     ebx, eax
0x180026e9e  jz      loc_18002710C
0x180026ea4  mov     r8d, 0EC5h
0x180026eaa  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x180026eb1  mov     rcx, cs:g_pDebug
0x180026eb8  mov     r9, r14
0x180026ebb  mov     [rsp+78h+var_50], eax
0x180026ebf  lea     rax, aTerminateworke_1; "TerminateWorker1 Not Initialized hr = 0"...
0x180026ec6  mov     [rsp+78h+var_58], rax
0x180026ecb  call    cs:__imp_PuDbgPrint
0x180026ed1  jmp     loc_1800270C0
0x180026ed6  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180026edd  call    cs:__imp_?ConvertSharedToExclusive@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ConvertSharedToExclusive(void)
0x180026ee3  lea     rdi, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x180026eea  xor     r15b, r15b
0x180026eed  test    byte ptr cs:g_dwDebugFlags, r13b
0x180026ef4  jz      short loc_180026F1B
0x180026ef6  mov     rcx, cs:g_pDebug
0x180026efd  lea     rax, aTerminateworke_6; "TerminateWorker1 WriteLock\n"
0x180026f04  mov     r9, r14
0x180026f07  mov     [rsp+78h+var_58], rax
0x180026f0c  mov     r8d, 0EEBh
0x180026f12  mov     rdx, rdi
0x180026f15  call    cs:__imp_PuDbgPrint
0x180026f1b  mov     eax, cs:?g_dwInitialized@@3KC; ulong volatile g_dwInitialized
0x180026f21  test    eax, eax
0x180026f23  jnz     short loc_180026F47
0x180026f25  test    byte ptr cs:g_dwDebugFlags, r13b
0x180026f2c  mov     eax, 800CC800h
0x180026f31  mov     ebx, eax
0x180026f33  jz      loc_18002710C
0x180026f39  mov     r8d, 0EF2h
0x180026f3f  mov     rdx, rdi
0x180026f42  jmp     loc_180026EB1
0x180026f47  mov     eax, cs:?g_dwInitialized@@3KC; ulong volatile g_dwInitialized
0x180026f4d  cmp     eax, 1
0x180026f50  jnz     loc_18002707D
0x180026f56  test    byte ptr cs:g_dwDebugFlags, r13b
0x180026f5d  jz      short loc_180026F84
0x180026f5f  mov     rcx, cs:g_pDebug
0x180026f66  lea     rax, aTerminateworke_9; "TerminateWorker1 Stopping EWR\n"
0x180026f6d  mov     r9, r14
0x180026f70  mov     [rsp+78h+var_58], rax
0x180026f75  mov     r8d, 0EF9h
0x180026f7b  mov     rdx, rdi
0x180026f7e  call    cs:__imp_PuDbgPrint
0x180026f84  mov     rcx, cs:?g_pListenerController@@3PEAVCListenerController@@EA; CListenerController * g_pListenerController
0x180026f8b  test    rcx, rcx
0x180026f8e  jz      short loc_180026FA4
0x180026f90  mov     edx, 1
0x180026f95  call    ?Stop@CListenerController@@QEAAJW4eSTATE@@@Z; CListenerController::Stop(eSTATE)
0x180026f9a  mov     ebx, eax
0x180026f9c  test    eax, eax
0x180026f9e  js      loc_1800270C0
0x180026fa4  test    byte ptr cs:g_dwDebugFlags, r13b
0x180026fab  jz      short loc_180026FD2
0x180026fad  mov     rcx, cs:g_pDebug
0x180026fb4  lea     rax, aTerminateworke_11; "TerminateWorker1 Getting key\n"
0x180026fbb  mov     r9, r14
0x180026fbe  mov     [rsp+78h+var_58], rax
0x180026fc3  mov     r8d, 0F05h
0x180026fc9  mov     rdx, rdi
0x180026fcc  call    cs:__imp_PuDbgPrint
0x180026fd2  lea     rdx, [rbp+arg_8]; struct _IIS_CRYPTO_BLOB **
0x180026fd6  lea     rcx, [rbp+var_38]; this
0x180026fda  call    ?InitStorageAndSessionKey@@YAJPEAVIIS_CRYPTO_STORAGE@@PEAPEFAU_IIS_CRYPTO_BLOB@@@Z; InitStorageAndSessionKey(IIS_CRYPTO_STORAGE *,_IIS_CRYPTO_BLOB * *)
0x180026fdf  mov     ebx, eax
0x180026fe1  test    eax, eax
0x180026fe3  jns     short loc_180027020
0x180026fe5  test    byte ptr cs:g_dwDebugFlags, r13b
0x180026fec  jz      short loc_180027017
0x180026fee  mov     rcx, cs:g_pDebug
0x180026ff5  mov     r9, r14
0x180026ff8  mov     [rsp+78h+var_50], eax
0x180026ffc  mov     r8d, 0F0Bh
0x180027002  lea     rax, aTerminateworke_5; "TerminateWorker1.InitStorageAndSessionK"...
0x180027009  mov     rdx, rdi
0x18002700c  mov     [rsp+78h+var_58], rax
0x180027011  call    cs:__imp_PuDbgPrint
0x180027017  mov     rsi, [rbp+arg_8]
0x18002701b  jmp     loc_1800270C0
0x180027020  test    byte ptr cs:g_dwDebugFlags, r13b
0x180027027  jz      short loc_18002704E
0x180027029  mov     rcx, cs:g_pDebug
0x180027030  lea     rax, aTerminateworke_4; "TerminateWorker1 Saving data\n"
0x180027037  mov     r9, r14
0x18002703a  mov     [rsp+78h+var_58], rax
0x18002703f  mov     r8d, 0F11h
0x180027045  mov     rdx, rdi
0x180027048  call    cs:__imp_PuDbgPrint
0x18002704e  mov     [rsp+78h+var_40], 1; int
0x180027056  lea     rdx, [rbp+var_38]; struct IIS_CRYPTO_STORAGE *
0x18002705a  mov     [rsp+78h+var_48], r12d; int
0x18002705f  xor     r9d, r9d; unsigned __int16 *
0x180027062  mov     [rsp+78h+var_50], esi; unsigned int
0x180027066  mov     [rsp+78h+var_58], rsi; unsigned __int16 *
0x18002706b  mov     rsi, [rbp+arg_8]
0x18002706f  mov     r8, rsi; struct _IIS_CRYPTO_BLOB *
0x180027072  call    ?SaveAllData@@YAJHPEAVIIS_CRYPTO_STORAGE@@PEFAU_IIS_CRYPTO_BLOB@@PEAG2KHH@Z; SaveAllData(int,IIS_CRYPTO_STORAGE *,_IIS_CRYPTO_BLOB *,ushort *,ushort *,ulong,int,int)
0x180027077  mov     ebx, eax
0x180027079  test    eax, eax
0x18002707b  js      short loc_1800270C0
0x18002707d  or      eax, 0FFFFFFFFh
0x180027080  lock xadd cs:?g_dwInitialized@@3KC, eax; ulong volatile g_dwInitialized
0x180027088  cmp     eax, 1
0x18002708b  jnz     short loc_1800270C0
0x18002708d  test    byte ptr cs:g_dwDebugFlags, r13b
0x180027094  jz      short loc_1800270BB
0x180027096  mov     rcx, cs:g_pDebug
0x18002709d  lea     rax, aTerminateworke_3; "TerminateWorker1 Last Terminate\n"
0x1800270a4  mov     r9, r14
0x1800270a7  mov     [rsp+78h+var_58], rax
0x1800270ac  mov     r8d, 0F24h
0x1800270b2  mov     rdx, rdi
0x1800270b5  call    cs:__imp_PuDbgPrint
0x1800270bb  call    ?TerminateWorker@@YAXXZ; TerminateWorker(void)
0x1800270c0  test    byte ptr cs:g_dwDebugFlags, r13b
0x1800270c7  jz      short loc_18002710C
0x1800270c9  mov     rcx, cs:g_pDebug
0x1800270d0  lea     rdx, aWrite; "Write"
0x1800270d7  test    r15b, r15b
0x1800270da  lea     rax, aRead; "Read"
0x1800270e1  mov     r9, r14
0x1800270e4  mov     r8d, 0F2Bh
0x1800270ea  cmovz   rax, rdx
0x1800270ee  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x1800270f5  mov     qword ptr [rsp+78h+var_50], rax
0x1800270fa  lea     rax, aTerminateworke; "TerminateWorker1 %sUnlock\n"
0x180027101  mov     [rsp+78h+var_58], rax
0x180027106  call    cs:__imp_PuDbgPrint
0x18002710c  mov     dl, r15b
0x18002710f  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180027116  call    cs:__imp_?ReadOrWriteUnlock@CReaderWriterLock3@@QEAAX_N@Z; CReaderWriterLock3::ReadOrWriteUnlock(bool)
0x18002711c  test    rsi, rsi
0x18002711f  jz      short loc_18002712D
0x180027121  mov     rcx, rsi; pv
0x180027124  mov     byte ptr [rsi], 58h ; 'X'
0x180027127  call    cs:__imp_CoTaskMemFree
0x18002712d  test    byte ptr cs:g_dwDebugFlags, r13b
0x180027134  jz      short loc_18002716D
0x180027136  mov     eax, cs:?g_dwInitialized@@3KC; ulong volatile g_dwInitialized
0x18002713c  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x180027143  mov     rcx, cs:g_pDebug
0x18002714a  mov     r9, r14
0x18002714d  mov     [rsp+78h+var_48], eax
0x180027151  mov     r8d, 0F37h
0x180027157  lea     rax, aEndTerminatewo; "End TerminateWorker1 hr = 0x%08x g_dwIn"...
0x18002715e  mov     [rsp+78h+var_50], ebx
0x180027162  mov     [rsp+78h+var_58], rax
0x180027167  call    cs:__imp_PuDbgPrint
0x18002716d  lea     rcx, [rbp+var_38]; this
0x180027171  call    ??1IIS_CRYPTO_STORAGE@@QEAA@XZ; IIS_CRYPTO_STORAGE::~IIS_CRYPTO_STORAGE(void)
0x180027176  mov     eax, ebx
0x180027178  add     rsp, 78h
0x18002717c  pop     r15
0x18002717e  pop     r14
0x180027180  pop     r13
0x180027182  pop     r12
0x180027184  pop     rdi
0x180027185  pop     rsi
0x180027186  pop     rbx
0x180027187  pop     rbp
0x180027188  retn
```
