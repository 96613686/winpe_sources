# SNITerminate

- ea: `0x100419574`
- end: `0x100419913`
- name: `SNITerminate`
- size: `927`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x10045fd58`

## callees

- `0x1004167a4`
- `0x100416868`
- `0x100419574`
- `0x10041a500`
- `0x10043a7c4`
- `0x10043a930`
- `0x10043f80c`
- `0x10044336c`
- `0x10044b2e0`
- `0x100545d84`
- `0x100546aa8`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x100419643`
- `KERNEL32!WaitForSingleObject` at `0x100419643`
- `KERNEL32!PostQueuedCompletionStatus` at `0x100419732`
- `KERNEL32!PostQueuedCompletionStatus` at `0x100419732`
- `KERNEL32!GetLastError` at `0x10041964e`
- `KERNEL32!GetLastError` at `0x1004196e3`
- `KERNEL32!GetLastError` at `0x1004197d6`
- `KERNEL32!GetLastError` at `0x10041964e`
- `KERNEL32!GetLastError` at `0x1004196e3`
- `KERNEL32!GetLastError` at `0x1004197d6`
- `KERNEL32!CloseHandle` at `0x1004196cb`
- `KERNEL32!CloseHandle` at `0x1004197c8`
- `KERNEL32!CloseHandle` at `0x1004197f4`
- `KERNEL32!CloseHandle` at `0x1004196cb`
- `KERNEL32!CloseHandle` at `0x1004197c8`
- `KERNEL32!CloseHandle` at `0x1004197f4`

## pseudocode

```c
__int64 SNITerminate()
{
  struct CCriticalSectionNT_SNI *v0; // rbp
  unsigned int v1; // ebx
  LastConnectCache *v2; // rcx
  BOOL v3; // eax
  DWORD v4; // ebx
  unsigned int i; // ebx
  void *v6; // rcx
  BOOL v7; // eax
  DWORD v9; // [rsp+28h] [rbp-30h]
  __int64 v10; // [rsp+60h] [rbp+8h] BYREF

  v10 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_1005E7768[0] && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *, wchar_t *, _QWORD))off_1005D39F0)(
      bidID,
      0,
      0,
      &v10,
      off_1005E7768[0],
      0);
  v0 = g_csInitialize;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)g_csInitialize + 2) + 32LL) + 8LL))(*((_QWORD *)g_csInitialize
                                                                                                + 2) + 32LL);
  if ( _InterlockedExchangeAdd(&gcSNIInitialized, 0xFFFFFFFF) != 1 )
    goto LABEL_41;
  if ( ghWaitClose )
    (*(void (__fastcall **)(_QWORD))(*ghWaitClose + 24LL))(ghWaitClose);
  if ( WaitForSingleObject(hObject, 0x927C0u) == -1 )
    GetLastError();
  if ( !gnConns )
  {
    v2 = (LastConnectCache *)hObject;
    if ( hObject )
    {
      v3 = CloseHandle(hObject);
      hObject = 0;
      ghWaitClose = 0;
      if ( !v3 )
        GetLastError();
    }
    LastConnectCache::Shutdown(v2);
    LocalDB::Terminate();
    if ( g_csLocalDBInitialize )
    {
      (**(void (__fastcall ***)(struct CCriticalSectionNT_SNI *, __int64))g_csLocalDBInitialize)(
        g_csLocalDBInitialize,
        1);
      g_csLocalDBInitialize = 0;
    }
    SNI_Provider::Terminate();
    g_fTerminate = 1;
    PostQueuedCompletionStatus(ghIoCompletionPort, 0, 0, 0);
    if ( gnWorkerThreadCount )
    {
      v4 = ThreadHandle<SNIThreadHandleAllocator>::WaitForAllThreadsToExit(
             gnWorkerThreadCount,
             (__int64)rghWorkerThreads,
             0);
      if ( v4 )
      {
        if ( (bidGblFlags & 2) != 0 && off_1005E45E0[0] )
        {
          v9 = v4;
          SniErrorIdFromStringId(0xC3B4u);
          bidTraceW(0, 1316864, off_1005E45E0[0], 9);
        }
        SNISetLastError(9, v4, 50100);
      }
      for ( i = 0; i < gnWorkerThreadCount; ++i )
      {
        v6 = (void *)rghWorkerThreads[i];
        if ( v6 )
        {
          v7 = CloseHandle(v6);
          rghWorkerThreads[i] = 0;
          if ( !v7 )
            GetLastError();
        }
      }
      gnWorkerThreadCount = 0;
    }
    CloseHandle(ghIoCompletionPort);
    ghIoCompletionPort = 0;
    if ( SNI_MemRegions::s_pClientMemRegions )
    {
      SNI_MemRegions::Terminate(SNI_MemRegions::s_pClientMemRegions);
      SNI_MemRegions::s_pClientMemRegions = 0;
    }
    else if ( (bidGblFlags & 2) != 0 && off_1005E45E8[0] && bidID != -1 )
    {
      ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD, DWORD))off_1005D39E0[0])(
        bidID,
        0,
        1342464,
        off_1005E45E8[0],
        0,
        v9);
    }
    SNI_NodeIOCompletionQueues::Terminate(SNI_NodeIOCompletionQueues::sm_pClientCompletionQueues);
    SNI_NodeIOCompletionQueues::sm_pClientCompletionQueues = 0;
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E45F0[0] )
      bidTraceW(0, 1350656, off_1005E45F0[0], 0);
LABEL_41:
    v1 = 0;
    goto LABEL_42;
  }
  _InterlockedIncrement(&gcSNIInitialized);
  v1 = 5023;
  if ( (bidGblFlags & 2) != 0 && off_1005E45D8[0] )
  {
    SniErrorIdFromStringId(0xC3B4u);
    bidTraceW(0, 1277952, off_1005E45D8[0], 9);
  }
  SNISetLastError(9, 5023, 50100);
LABEL_42:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)v0 + 2) + 32LL) + 24LL))(*((_QWORD *)v0 + 2) + 32LL);
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E45F8[0] )
    bidTraceW(0, 1356800, off_1005E45F8[0], v1);
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v10);
  return v1;
}

```

## disassembly

```asm
0x100419574  mov     r11, rsp
0x100419577  mov     [r11+10h], rbx
0x10041957b  mov     [r11+18h], rbp
0x10041957f  mov     [r11+20h], rdi
0x100419583  push    r12
0x100419585  push    r13
0x100419587  push    r14
0x100419589  sub     rsp, 40h
0x10041958d  mov     eax, cs:_bidGblFlags
0x100419593  mov     ecx, 20004h
0x100419598  or      qword ptr [r11+8], 0FFFFFFFFFFFFFFFFh
0x10041959d  and     eax, ecx
0x10041959f  xor     r14d, r14d
0x1004195a2  cmp     eax, ecx
0x1004195a4  jnz     short loc_1004195E8
0x1004195a6  mov     rax, cs:off_1005E7768; "<SNITerminate|API|SNI> \n"
0x1004195ad  test    rax, rax
0x1004195b0  jz      short loc_1004195E8
0x1004195b2  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x1004195ba  jz      short loc_1004195E8
0x1004195bc  mov     rcx, cs:off_1005E7768; "<SNITerminate|API|SNI> \n"
0x1004195c3  lea     r9, [r11+8]
0x1004195c7  mov     rax, cs:off_1005D39F0
0x1004195ce  xor     r8d, r8d
0x1004195d1  mov     [r11-30h], r14
0x1004195d5  xor     edx, edx
0x1004195d7  mov     [r11-38h], rcx
0x1004195db  mov     rcx, cs:_bidID
0x1004195e2  call    cs:__guard_dispatch_icall_fptr
0x1004195e8  mov     rbp, cs:?g_csInitialize@@3PEAVCCriticalSectionNT_SNI@@EA; CCriticalSectionNT_SNI * g_csInitialize
0x1004195ef  mov     rcx, [rbp+10h]
0x1004195f3  add     rcx, 20h ; ' '
0x1004195f7  mov     rax, [rcx]
0x1004195fa  mov     rax, [rax+8]
0x1004195fe  call    cs:__guard_dispatch_icall_fptr
0x100419604  or      eax, 0FFFFFFFFh
0x100419607  lock xadd cs:?gcSNIInitialized@@3JA, eax; long gcSNIInitialized
0x10041960f  mov     r13d, 20002h
0x100419615  cmp     eax, 1
0x100419618  jnz     loc_1004198A5
0x10041961e  mov     rcx, cs:?ghWaitClose@@3VEventHandle@@A; EventHandle ghWaitClose
0x100419625  test    rcx, rcx
0x100419628  jz      short loc_100419637
0x10041962a  mov     rax, [rcx]
0x10041962d  mov     rax, [rax+18h]
0x100419631  call    cs:__guard_dispatch_icall_fptr
0x100419637  mov     rcx, cs:hObject; hHandle
0x10041963e  mov     edx, 927C0h; dwMilliseconds
0x100419643  call    cs:__imp_WaitForSingleObject
0x100419649  cmp     eax, 0FFFFFFFFh
0x10041964c  jnz     short loc_100419654
0x10041964e  call    cs:__imp_GetLastError
0x100419654  cmp     cs:?gnConns@@3JA, r14d; long gnConns
0x10041965b  jz      short loc_1004196BF
0x10041965d  lock inc cs:?gcSNIInitialized@@3JA; long gcSNIInitialized
0x100419664  test    byte ptr cs:_bidGblFlags, 2
0x10041966b  mov     ebx, 139Fh
0x100419670  mov     edi, 0C3B4h
0x100419675  jz      short loc_1004196AB
0x100419677  mov     rax, cs:off_1005E45D8; "<SNITerminate|ERR|SNI> ProviderNum: %d{"...
0x10041967e  test    rax, rax
0x100419681  jz      short loc_1004196AB
0x100419683  mov     ecx, edi; unsigned int
0x100419685  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x10041968a  mov     r8, cs:off_1005E45D8; "<SNITerminate|ERR|SNI> ProviderNum: %d{"...
0x100419691  mov     r9d, 9
0x100419697  mov     edx, 138000h
0x10041969c  mov     [rsp+58h+var_30], ebx
0x1004196a0  xor     ecx, ecx
0x1004196a2  mov     dword ptr [rsp+58h+var_38], eax
0x1004196a6  call    _bidTraceW
0x1004196ab  mov     r8d, edi
0x1004196ae  mov     edx, ebx
0x1004196b0  mov     ecx, 9
0x1004196b5  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x1004196ba  jmp     loc_1004198A8
0x1004196bf  mov     rcx, cs:hObject; hObject
0x1004196c6  test    rcx, rcx
0x1004196c9  jz      short loc_1004196E9
0x1004196cb  call    cs:__imp_CloseHandle
0x1004196d1  mov     cs:hObject, r14
0x1004196d8  mov     cs:?ghWaitClose@@3VEventHandle@@A, r14; EventHandle ghWaitClose
0x1004196df  test    eax, eax
0x1004196e1  jnz     short loc_1004196E9
0x1004196e3  call    cs:__imp_GetLastError
0x1004196e9  call    ?Shutdown@LastConnectCache@@YAXXZ; LastConnectCache::Shutdown(void)
0x1004196ee  call    ?Terminate@LocalDB@@SAXXZ; LocalDB::Terminate(void)
0x1004196f3  mov     rcx, cs:?g_csLocalDBInitialize@@3PEAVCCriticalSectionNT_SNI@@EA; CCriticalSectionNT_SNI * g_csLocalDBInitialize
0x1004196fa  test    rcx, rcx
0x1004196fd  jz      short loc_100419717
0x1004196ff  mov     rax, [rcx]
0x100419702  mov     edx, 1
0x100419707  mov     rax, [rax]
0x10041970a  call    cs:__guard_dispatch_icall_fptr
0x100419710  mov     cs:?g_csLocalDBInitialize@@3PEAVCCriticalSectionNT_SNI@@EA, r14; CCriticalSectionNT_SNI * g_csLocalDBInitialize
0x100419717  call    ?Terminate@SNI_Provider@@SAXXZ; SNI_Provider::Terminate(void)
0x10041971c  mov     rcx, cs:?ghIoCompletionPort@@3PEAXEA; CompletionPort
0x100419723  xor     r9d, r9d; lpOverlapped
0x100419726  xor     r8d, r8d; dwCompletionKey
0x100419729  mov     cs:?g_fTerminate@@3_NA, 1; bool g_fTerminate
0x100419730  xor     edx, edx; dwNumberOfBytesTransferred
0x100419732  call    cs:__imp_PostQueuedCompletionStatus
0x100419738  mov     eax, cs:?gnWorkerThreadCount@@3KA; ulong gnWorkerThreadCount
0x10041973e  test    eax, eax
0x100419740  jz      loc_1004197ED
0x100419746  lea     r12, ?rghWorkerThreads@@3PAV?$ThreadHandle@USNIThreadHandleAllocator@@@@A; ThreadHandle<SNIThreadHandleAllocator> near * rghWorkerThreads
0x10041974d  mov     ecx, eax
0x10041974f  mov     rdx, r12
0x100419752  xor     r8d, r8d
0x100419755  call    ?WaitForAllThreadsToExit@?$ThreadHandle@USNIThreadHandleAllocator@@@@SAK_KPEAV1@PEAK@Z; ThreadHandle<SNIThreadHandleAllocator>::WaitForAllThreadsToExit(unsigned __int64,ThreadHandle<SNIThreadHandleAllocator> *,ulong *)
0x10041975a  mov     ebx, eax
0x10041975c  test    eax, eax
0x10041975e  jz      short loc_1004197B1
0x100419760  test    byte ptr cs:_bidGblFlags, 2
0x100419767  mov     edi, 0C3B4h
0x10041976c  jz      short loc_1004197A2
0x10041976e  mov     rcx, cs:off_1005E45E0; "<SNITerminate|ERR|SNI> ProviderNum: %d{"...
0x100419775  test    rcx, rcx
0x100419778  jz      short loc_1004197A2
0x10041977a  mov     ecx, edi; unsigned int
0x10041977c  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x100419781  mov     r8, cs:off_1005E45E0; "<SNITerminate|ERR|SNI> ProviderNum: %d{"...
0x100419788  mov     r9d, 9
0x10041978e  mov     edx, 141800h
0x100419793  mov     [rsp+58h+var_30], ebx
0x100419797  xor     ecx, ecx
0x100419799  mov     dword ptr [rsp+58h+var_38], eax
0x10041979d  call    _bidTraceW
0x1004197a2  mov     r8d, edi
0x1004197a5  mov     edx, ebx
0x1004197a7  mov     ecx, 9
0x1004197ac  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x1004197b1  cmp     cs:?gnWorkerThreadCount@@3KA, r14d; ulong gnWorkerThreadCount
0x1004197b8  mov     ebx, r14d
0x1004197bb  jbe     short loc_1004197E6
0x1004197bd  mov     edi, ebx
0x1004197bf  mov     rcx, [r12+rdi*8]; hObject
0x1004197c3  test    rcx, rcx
0x1004197c6  jz      short loc_1004197DC
0x1004197c8  call    cs:__imp_CloseHandle
0x1004197ce  mov     [r12+rdi*8], r14
0x1004197d2  test    eax, eax
0x1004197d4  jnz     short loc_1004197DC
0x1004197d6  call    cs:__imp_GetLastError
0x1004197dc  inc     ebx
0x1004197de  cmp     ebx, cs:?gnWorkerThreadCount@@3KA; ulong gnWorkerThreadCount
0x1004197e4  jb      short loc_1004197BD
0x1004197e6  mov     cs:?gnWorkerThreadCount@@3KA, r14d; ulong gnWorkerThreadCount
0x1004197ed  mov     rcx, cs:?ghIoCompletionPort@@3PEAXEA; hObject
0x1004197f4  call    cs:__imp_CloseHandle
0x1004197fa  mov     rcx, cs:?s_pClientMemRegions@SNI_MemRegions@@2PEAV1@EA; this
0x100419801  mov     cs:?ghIoCompletionPort@@3PEAXEA, r14; void * ghIoCompletionPort
0x100419808  test    rcx, rcx
0x10041980b  jz      short loc_10041981B
0x10041980d  call    ?Terminate@SNI_MemRegions@@SAXPEAV1@@Z; SNI_MemRegions::Terminate(SNI_MemRegions *)
0x100419812  mov     cs:?s_pClientMemRegions@SNI_MemRegions@@2PEAV1@EA, r14; SNI_MemRegions * SNI_MemRegions::s_pClientMemRegions
0x100419819  jmp     short loc_100419862
0x10041981b  test    byte ptr cs:_bidGblFlags, 2
0x100419822  jz      short loc_100419862
0x100419824  mov     rax, cs:off_1005E45E8; "<SNITerminate|ERR|SNI> SNI_MemRegions::"...
0x10041982b  test    rax, rax
0x10041982e  jz      short loc_100419862
0x100419830  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x100419838  jz      short loc_100419862
0x10041983a  mov     r9, cs:off_1005E45E8; "<SNITerminate|ERR|SNI> SNI_MemRegions::"...
0x100419841  xor     edx, edx
0x100419843  mov     rcx, cs:_bidID
0x10041984a  mov     r8d, 147C00h
0x100419850  mov     rax, cs:off_1005D39E0
0x100419857  mov     [rsp+58h+var_38], r14
0x10041985c  call    cs:__guard_dispatch_icall_fptr
0x100419862  mov     rcx, cs:?sm_pClientCompletionQueues@SNI_NodeIOCompletionQueues@@2PEAV1@EA; struct SNI_NodeIOCompletionQueues *
0x100419869  call    ?Terminate@SNI_NodeIOCompletionQueues@@SAXPEAV1@@Z; SNI_NodeIOCompletionQueues::Terminate(SNI_NodeIOCompletionQueues *)
0x10041986e  mov     eax, cs:_bidGblFlags
0x100419874  and     eax, r13d
0x100419877  mov     cs:?sm_pClientCompletionQueues@SNI_NodeIOCompletionQueues@@2PEAV1@EA, r14; SNI_NodeIOCompletionQueues * SNI_NodeIOCompletionQueues::sm_pClientCompletionQueues
0x10041987e  cmp     eax, r13d
0x100419881  jnz     short loc_1004198A5
0x100419883  mov     rax, cs:off_1005E45F0; "<SNITerminate|RET|SNI> %d{WINERR}\n"
0x10041988a  test    rax, rax
0x10041988d  jz      short loc_1004198A5
0x10041988f  mov     r8, cs:off_1005E45F0; "<SNITerminate|RET|SNI> %d{WINERR}\n"
0x100419896  xor     r9d, r9d
0x100419899  mov     edx, 149C00h
0x10041989e  xor     ecx, ecx
0x1004198a0  call    _bidTraceW
0x1004198a5  mov     ebx, r14d
0x1004198a8  mov     rcx, [rbp+10h]
0x1004198ac  add     rcx, 20h ; ' '
0x1004198b0  mov     rax, [rcx]
0x1004198b3  mov     rax, [rax+18h]
0x1004198b7  call    cs:__guard_dispatch_icall_fptr
0x1004198bd  mov     eax, cs:_bidGblFlags
0x1004198c3  and     eax, r13d
0x1004198c6  cmp     eax, r13d
0x1004198c9  jnz     short loc_1004198ED
0x1004198cb  mov     rcx, cs:off_1005E45F8; "<SNITerminate|RET|SNI> %d{WINERR}\n"
0x1004198d2  test    rcx, rcx
0x1004198d5  jz      short loc_1004198ED
0x1004198d7  mov     r8, cs:off_1005E45F8; "<SNITerminate|RET|SNI> %d{WINERR}\n"
0x1004198de  mov     r9d, ebx
0x1004198e1  mov     edx, 14B400h
0x1004198e6  xor     ecx, ecx
0x1004198e8  call    _bidTraceW
0x1004198ed  lea     rcx, [rsp+58h+arg_0]; this
0x1004198f2  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x1004198f7  mov     rbp, [rsp+58h+arg_10]
0x1004198fc  mov     eax, ebx
0x1004198fe  mov     rbx, [rsp+58h+arg_8]
0x100419903  mov     rdi, [rsp+58h+arg_18]
0x100419908  add     rsp, 40h
0x10041990c  pop     r14
0x10041990e  pop     r13
0x100419910  pop     r12
0x100419912  retn
```
