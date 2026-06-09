# SNITerminate

- ea: `0x1801596a0`
- end: `0x180159b04`
- name: `SNITerminate`
- size: `1124`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x1801941e0`

## callees

- `0x180001f70`
- `0x1800030c0`
- `0x180003d80`
- `0x180151a60`
- `0x1801525d0`
- `0x1801596a0`
- `0x18015a6f0`
- `0x18015a880`
- `0x18015beb0`
- `0x18015c6e0`
- `0x18015e230`
- `0x18017e080`
- `0x1801a65e1`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!Sleep` at `0x180159931`
- `KERNEL32!Sleep` at `0x180159931`
- `KERNEL32!GetLastError` at `0x180159848`
- `KERNEL32!GetLastError` at `0x1801598eb`
- `KERNEL32!GetLastError` at `0x180159848`
- `KERNEL32!GetLastError` at `0x1801598eb`
- `KERNEL32!WaitForMultipleObjects` at `0x180159832`
- `KERNEL32!WaitForMultipleObjects` at `0x180159832`
- `KERNEL32!PostQueuedCompletionStatus` at `0x1801597a7`
- `KERNEL32!PostQueuedCompletionStatus` at `0x1801597a7`
- `KERNEL32!CloseHandle` at `0x1801598de`
- `KERNEL32!CloseHandle` at `0x180159908`
- `KERNEL32!CloseHandle` at `0x1801598de`
- `KERNEL32!CloseHandle` at `0x180159908`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 SNITerminate()
{
  unsigned int v0; // ebp
  struct CCriticalSectionNT_SNI *v1; // r14
  LastConnectCache *v2; // rcx
  unsigned __int64 v3; // rsi
  unsigned __int64 v4; // rbx
  DWORD v5; // edi
  char *v6; // rcx
  DWORD v7; // eax
  DWORD LastError; // edi
  unsigned int i; // ebx
  HANDLE *v10; // rdi
  BOOL v11; // eax
  int v12; // ebx
  SNI_MemRegions *v13; // rbx
  DWORD v15; // [rsp+28h] [rbp-250h]
  _QWORD v16[2]; // [rsp+40h] [rbp-238h] BYREF
  HANDLE Handles; // [rsp+50h] [rbp-228h] BYREF
  char v18; // [rsp+58h] [rbp-220h] BYREF

  v16[0] = -1;
  v0 = 0;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_180266750[0] && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD *, wchar_t *, _QWORD))off_180248060[0])(
      bidID,
      0,
      0,
      v16,
      off_180266750[0],
      0);
  v1 = g_csInitialize;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)g_csInitialize + 2) + 32LL) + 8LL))(*((_QWORD *)g_csInitialize
                                                                                                + 2) + 32LL);
  if ( _InterlockedExchangeAdd(&gcSNIInitialized, 0xFFFFFFFF) != 1 )
    goto LABEL_51;
  LastConnectCache::Shutdown(v2);
  LocalDB::Terminate();
  if ( g_csLocalDBInitialize )
  {
    (**(void (__fastcall ***)(struct CCriticalSectionNT_SNI *, __int64))g_csLocalDBInitialize)(g_csLocalDBInitialize, 1);
    g_csLocalDBInitialize = 0;
  }
  SNI_Provider::Terminate();
  g_fTerminate = 1;
  PostQueuedCompletionStatus(ghIoCompletionPort, 0, 0, 0);
  if ( !gnWorkerThreadCount )
    goto LABEL_34;
  v3 = gnWorkerThreadCount;
  memset_0(&Handles, 0, 0x200u);
  v4 = 0;
  if ( !v3 )
    goto LABEL_28;
  while ( 1 )
  {
    v5 = 0;
    v6 = &v18;
    while ( v4 < v3 )
    {
      *((_QWORD *)v6 - 1) = rghWorkerThreads[v4++];
      if ( v4 >= v3 )
      {
        ++v5;
        break;
      }
      *(_QWORD *)v6 = rghWorkerThreads[v4++];
      v5 += 2;
      v6 += 16;
      if ( v5 >= 0x40 )
        break;
    }
    v7 = WaitForMultipleObjects(v5, &Handles, 1, 0xFFFFFFFF);
    if ( v7 < v5 )
      goto LABEL_20;
    if ( v7 == 258 )
      break;
    if ( v7 != -1 )
    {
      LastError = -2147418113;
      goto LABEL_24;
    }
    LastError = GetLastError();
    if ( LastError )
      goto LABEL_24;
LABEL_20:
    if ( v4 >= v3 )
      goto LABEL_28;
  }
  LastError = 258;
LABEL_24:
  if ( (bidGblFlags & 2) != 0 && off_180263D00[0] )
  {
    v15 = LastError;
    SniErrorIdFromStringId(0xC3B4u);
    bidTraceW(off_1802609B8[0], 1249280, off_180263D00[0], 8);
  }
  SNISetLastError(8, LastError, 50100);
LABEL_28:
  for ( i = 0; i < gnWorkerThreadCount; ++i )
  {
    v10 = (HANDLE *)&rghWorkerThreads[i];
    if ( *v10 )
    {
      v11 = CloseHandle(*v10);
      *v10 = 0;
      if ( !v11 )
        GetLastError();
    }
  }
  gnWorkerThreadCount = 0;
LABEL_34:
  CloseHandle(ghIoCompletionPort);
  ghIoCompletionPort = 0;
  v12 = 0;
  while ( gnConns )
  {
    Sleep(0x3E8u);
    if ( ++v12 >= 10 )
    {
      if ( gnConns )
      {
        _InterlockedIncrement(&gcSNIInitialized);
        v0 = 5023;
        if ( (bidGblFlags & 2) != 0 && off_180263D08[0] )
        {
          SniErrorIdFromStringId(0xC3B4u);
          bidTraceW(off_1802609C0[0], 1292288, off_180263D08[0], 8);
        }
        SNISetLastError(8, 5023, 50100);
        goto LABEL_51;
      }
      break;
    }
  }
  v13 = SNI_MemRegions::s_pClientMemRegions;
  if ( SNI_MemRegions::s_pClientMemRegions )
  {
    SNI_MemRegions::Flush(SNI_MemRegions::s_pClientMemRegions);
    SNI_MemRegions::`scalar deleting destructor'(v13, 1u);
    SNI_MemRegions::s_lMaxMemRegionProvider = 0;
    SNI_MemRegions::s_pClientMemRegions = 0;
  }
  else if ( (bidGblFlags & 2) != 0 && off_180263D10[0] && bidID != -1 )
  {
    ((void (__fastcall *)(__int64, char *, __int64, wchar_t *, _QWORD, DWORD))off_180248050[0])(
      bidID,
      off_1802609C8[0],
      1306624,
      off_180263D10[0],
      0,
      v15);
  }
  SNI_NodeIOCompletionQueues::Terminate(SNI_NodeIOCompletionQueues::sm_pClientCompletionQueues);
  SNI_NodeIOCompletionQueues::sm_pClientCompletionQueues = 0;
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_180263D18[0] )
    bidTraceW(off_1802609D0[0], 1314816, off_180263D18[0], 0);
LABEL_51:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)v1 + 2) + 32LL) + 24LL))(*((_QWORD *)v1 + 2) + 32LL);
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_180263D20[0] )
    bidTraceW(off_1802609D8[0], 1320960, off_180263D20[0], v0);
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)v16);
  return v0;
}

```

## disassembly

```asm
0x1801596a0  mov     [rsp+arg_0], rbx
0x1801596a5  mov     [rsp+arg_8], rbp
0x1801596aa  mov     [rsp+arg_10], rsi
0x1801596af  push    rdi
0x1801596b0  push    r14
0x1801596b2  push    r15
0x1801596b4  sub     rsp, 260h
0x1801596bb  mov     rax, cs:__security_cookie
0x1801596c2  xor     rax, rsp
0x1801596c5  mov     [rsp+278h+var_28], rax
0x1801596cd  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1801596d4  mov     [rsp+278h+var_238], rbx
0x1801596d9  mov     eax, cs:_bidGblFlags
0x1801596df  and     eax, 20004h
0x1801596e4  xor     ebp, ebp
0x1801596e6  cmp     eax, 20004h
0x1801596eb  jnz     short loc_180159734
0x1801596ed  mov     rax, cs:off_180266750; "<SNITerminate|API|SNI> \n"
0x1801596f4  test    rax, rax
0x1801596f7  jz      short loc_180159734
0x1801596f9  cmp     cs:_bidID, rbx
0x180159700  jz      short loc_180159734
0x180159702  mov     r10, cs:off_180248060
0x180159709  mov     qword ptr [rsp+278h+var_250], rbp
0x18015970e  mov     rax, cs:off_180266750; "<SNITerminate|API|SNI> \n"
0x180159715  mov     [rsp+278h+var_258], rax
0x18015971a  lea     r9, [rsp+278h+var_238]
0x18015971f  xor     r8d, r8d
0x180159722  xor     edx, edx
0x180159724  mov     rcx, cs:_bidID
0x18015972b  mov     rax, r10
0x18015972e  call    cs:__guard_dispatch_icall_fptr
0x180159734  mov     r14, cs:?g_csInitialize@@3PEAVCCriticalSectionNT_SNI@@EA; CCriticalSectionNT_SNI * g_csInitialize
0x18015973b  mov     rcx, [r14+10h]
0x18015973f  add     rcx, 20h ; ' '
0x180159743  mov     rax, [rcx]
0x180159746  mov     rax, [rax+8]
0x18015974a  call    cs:__guard_dispatch_icall_fptr
0x180159750  lock xadd cs:?gcSNIInitialized@@3JA, ebx; long gcSNIInitialized
0x180159758  cmp     ebx, 1
0x18015975b  jnz     loc_180159A7B
0x180159761  call    ?Shutdown@LastConnectCache@@YAXXZ; LastConnectCache::Shutdown(void)
0x180159766  call    ?Terminate@LocalDB@@SAXXZ; LocalDB::Terminate(void)
0x18015976b  mov     rcx, cs:?g_csLocalDBInitialize@@3PEAVCCriticalSectionNT_SNI@@EA; CCriticalSectionNT_SNI * g_csLocalDBInitialize
0x180159772  test    rcx, rcx
0x180159775  jz      short loc_18015978C
0x180159777  mov     rax, [rcx]
0x18015977a  mov     edx, ebx
0x18015977c  mov     rax, [rax]
0x18015977f  call    cs:__guard_dispatch_icall_fptr
0x180159785  mov     cs:?g_csLocalDBInitialize@@3PEAVCCriticalSectionNT_SNI@@EA, rbp; CCriticalSectionNT_SNI * g_csLocalDBInitialize
0x18015978c  call    ?Terminate@SNI_Provider@@SAXXZ; SNI_Provider::Terminate(void)
0x180159791  mov     cs:?g_fTerminate@@3_NA, 1; bool g_fTerminate
0x180159798  xor     r9d, r9d; lpOverlapped
0x18015979b  xor     r8d, r8d; dwCompletionKey
0x18015979e  xor     edx, edx; dwNumberOfBytesTransferred
0x1801597a0  mov     rcx, cs:?ghIoCompletionPort@@3PEAXEA; CompletionPort
0x1801597a7  call    cs:__imp_PostQueuedCompletionStatus
0x1801597ad  mov     eax, cs:?gnWorkerThreadCount@@3KA; ulong gnWorkerThreadCount
0x1801597b3  test    eax, eax
0x1801597b5  jz      loc_180159901
0x1801597bb  mov     esi, eax
0x1801597bd  xor     edx, edx; Val
0x1801597bf  mov     r8d, 200h; Size
0x1801597c5  lea     rcx, [rsp+278h+Handles]; void *
0x1801597ca  call    memset_0
0x1801597cf  mov     rbx, rbp
0x1801597d2  lea     r15, ?rghWorkerThreads@@3PAV?$ThreadHandle@USNIThreadHandleAllocator@@@@A; ThreadHandle<SNIThreadHandleAllocator> near * rghWorkerThreads
0x1801597d9  test    rsi, rsi
0x1801597dc  jz      loc_1801598BE
0x1801597e2  mov     edi, ebp
0x1801597e4  lea     rcx, [rsp+278h+var_220]
0x1801597e9  nop     dword ptr [rax+00000000h]
0x1801597f0  cmp     rbx, rsi
0x1801597f3  jnb     short loc_18015981F
0x1801597f5  mov     rax, [r15+rbx*8]
0x1801597f9  mov     [rcx-8], rax
0x1801597fd  inc     rbx
0x180159800  cmp     rbx, rsi
0x180159803  jnb     short loc_18015981D
0x180159805  mov     rax, [r15+rbx*8]
0x180159809  mov     [rcx], rax
0x18015980c  inc     rbx
0x18015980f  add     edi, 2
0x180159812  add     rcx, 10h
0x180159816  cmp     edi, 40h ; '@'
0x180159819  jb      short loc_1801597F0
0x18015981b  jmp     short loc_18015981F
0x18015981d  inc     edi
0x18015981f  mov     r9d, 0FFFFFFFFh; dwMilliseconds
0x180159825  mov     r8d, 1; bWaitAll
0x18015982b  lea     rdx, [rsp+278h+Handles]; lpHandles
0x180159830  mov     ecx, edi; nCount
0x180159832  call    cs:__imp_WaitForMultipleObjects
0x180159838  cmp     eax, edi
0x18015983a  jb      short loc_180159854
0x18015983c  cmp     eax, 102h
0x180159841  jz      short loc_180159862
0x180159843  cmp     eax, 0FFFFFFFFh
0x180159846  jnz     short loc_18015985B
0x180159848  call    cs:__imp_GetLastError
0x18015984e  mov     edi, eax
0x180159850  test    eax, eax
0x180159852  jnz     short loc_180159867
0x180159854  cmp     rbx, rsi
0x180159857  jb      short loc_1801597E2
0x180159859  jmp     short loc_1801598BE
0x18015985b  mov     edi, 8000FFFFh
0x180159860  jmp     short loc_180159867
0x180159862  mov     edi, 102h
0x180159867  test    byte ptr cs:_bidGblFlags, 2
0x18015986e  jz      short loc_1801598AC
0x180159870  mov     rax, cs:off_180263D00; "<SNITerminate|ERR|SNI> ProviderNum: %d{"...
0x180159877  test    rax, rax
0x18015987a  jz      short loc_1801598AC
0x18015987c  mov     ecx, 0C3B4h; unsigned int
0x180159881  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x180159886  mov     [rsp+278h+var_250], edi
0x18015988a  mov     dword ptr [rsp+278h+var_258], eax
0x18015988e  mov     r9d, 8
0x180159894  mov     r8, cs:off_180263D00; "<SNITerminate|ERR|SNI> ProviderNum: %d{"...
0x18015989b  mov     edx, 131000h
0x1801598a0  mov     rcx, cs:off_1802609B8; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x1801598a7  call    _bidTraceW
0x1801598ac  mov     r8d, 0C3B4h
0x1801598b2  mov     edx, edi
0x1801598b4  mov     ecx, 8
0x1801598b9  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x1801598be  mov     ebx, ebp
0x1801598c0  cmp     cs:?gnWorkerThreadCount@@3KA, ebx; ulong gnWorkerThreadCount
0x1801598c6  jbe     short loc_1801598FB
0x1801598c8  nop     dword ptr [rax+rax+00000000h]
0x1801598d0  mov     eax, ebx
0x1801598d2  lea     rdi, [r15+rax*8]
0x1801598d6  mov     rcx, [rdi]; hObject
0x1801598d9  test    rcx, rcx
0x1801598dc  jz      short loc_1801598F1
0x1801598de  call    cs:__imp_CloseHandle
0x1801598e4  mov     [rdi], rbp
0x1801598e7  test    eax, eax
0x1801598e9  jnz     short loc_1801598F1
0x1801598eb  call    cs:__imp_GetLastError
0x1801598f1  inc     ebx
0x1801598f3  cmp     ebx, cs:?gnWorkerThreadCount@@3KA; ulong gnWorkerThreadCount
0x1801598f9  jb      short loc_1801598D0
0x1801598fb  mov     cs:?gnWorkerThreadCount@@3KA, ebp; ulong gnWorkerThreadCount
0x180159901  mov     rcx, cs:?ghIoCompletionPort@@3PEAXEA; hObject
0x180159908  call    cs:__imp_CloseHandle
0x18015990e  mov     cs:?ghIoCompletionPort@@3PEAXEA, rbp; void * ghIoCompletionPort
0x180159915  mov     ebx, ebp
0x180159917  nop     word ptr [rax+rax+00000000h]
0x180159920  cmp     cs:?gnConns@@3JA, ebp; long gnConns
0x180159926  jz      loc_1801599AE
0x18015992c  mov     ecx, 3E8h; dwMilliseconds
0x180159931  call    cs:__imp_Sleep
0x180159937  inc     ebx
0x180159939  cmp     ebx, 0Ah
0x18015993c  jl      short loc_180159920
0x18015993e  cmp     cs:?gnConns@@3JA, ebp; long gnConns
0x180159944  jz      short loc_1801599AE
0x180159946  lock inc cs:?gcSNIInitialized@@3JA; long gcSNIInitialized
0x18015994d  mov     ebp, 139Fh
0x180159952  test    byte ptr cs:_bidGblFlags, 2
0x180159959  jz      short loc_180159997
0x18015995b  mov     rax, cs:off_180263D08; "<SNITerminate|ERR|SNI> ProviderNum: %d{"...
0x180159962  test    rax, rax
0x180159965  jz      short loc_180159997
0x180159967  mov     ecx, 0C3B4h; unsigned int
0x18015996c  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x180159971  mov     [rsp+278h+var_250], ebp
0x180159975  mov     dword ptr [rsp+278h+var_258], eax
0x180159979  mov     r9d, 8
0x18015997f  mov     r8, cs:off_180263D08; "<SNITerminate|ERR|SNI> ProviderNum: %d{"...
0x180159986  mov     edx, 13B800h
0x18015998b  mov     rcx, cs:off_1802609C0; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180159992  call    _bidTraceW
0x180159997  mov     edx, ebp
0x180159999  mov     ecx, 8
0x18015999e  mov     r8d, 0C3B4h
0x1801599a4  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x1801599a9  jmp     loc_180159A7B
0x1801599ae  mov     rbx, cs:?s_pClientMemRegions@SNI_MemRegions@@2PEAV1@EA; SNI_MemRegions * SNI_MemRegions::s_pClientMemRegions
0x1801599b5  test    rbx, rbx
0x1801599b8  jz      short loc_1801599E3
0x1801599ba  mov     rcx, rbx; struct SNI_MemRegions *
0x1801599bd  call    ?Flush@SNI_MemRegions@@SAXPEAV1@@Z; SNI_MemRegions::Flush(SNI_MemRegions *)
0x1801599c2  test    rbx, rbx
0x1801599c5  jz      short loc_1801599D4
0x1801599c7  mov     edx, 1; unsigned int
0x1801599cc  mov     rcx, rbx; this
0x1801599cf  call    ??_GSNI_MemRegions@@QEAAPEAXI@Z; SNI_MemRegions::`scalar deleting destructor'(uint)
0x1801599d4  mov     cs:?s_lMaxMemRegionProvider@SNI_MemRegions@@2JA, ebp; long SNI_MemRegions::s_lMaxMemRegionProvider
0x1801599da  mov     cs:?s_pClientMemRegions@SNI_MemRegions@@2PEAV1@EA, rbp; SNI_MemRegions * SNI_MemRegions::s_pClientMemRegions
0x1801599e1  jmp     short loc_180159A2F
0x1801599e3  test    byte ptr cs:_bidGblFlags, 2
0x1801599ea  jz      short loc_180159A2F
0x1801599ec  mov     rax, cs:off_180263D10; "<SNITerminate|ERR|SNI> SNI_MemRegions::"...
0x1801599f3  test    rax, rax
0x1801599f6  jz      short loc_180159A2F
0x1801599f8  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x180159a00  jz      short loc_180159A2F
0x180159a02  mov     rax, cs:off_180248050
0x180159a09  mov     [rsp+278h+var_258], rbp
0x180159a0e  mov     r9, cs:off_180263D10; "<SNITerminate|ERR|SNI> SNI_MemRegions::"...
0x180159a15  mov     r8d, 13F000h
0x180159a1b  mov     rdx, cs:off_1802609C8; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180159a22  mov     rcx, cs:_bidID
0x180159a29  call    cs:__guard_dispatch_icall_fptr
0x180159a2f  mov     rcx, cs:?sm_pClientCompletionQueues@SNI_NodeIOCompletionQueues@@2PEAV1@EA; struct SNI_NodeIOCompletionQueues *
0x180159a36  call    ?Terminate@SNI_NodeIOCompletionQueues@@SAXPEAV1@@Z; SNI_NodeIOCompletionQueues::Terminate(SNI_NodeIOCompletionQueues *)
0x180159a3b  mov     cs:?sm_pClientCompletionQueues@SNI_NodeIOCompletionQueues@@2PEAV1@EA, rbp; SNI_NodeIOCompletionQueues * SNI_NodeIOCompletionQueues::sm_pClientCompletionQueues
0x180159a42  mov     eax, cs:_bidGblFlags
0x180159a48  and     eax, 20002h
0x180159a4d  cmp     eax, 20002h
0x180159a52  jnz     short loc_180159A7B
0x180159a54  mov     rax, cs:off_180263D18; "<SNITerminate|RET|SNI> %d{WINERR}\n"
0x180159a5b  test    rax, rax
0x180159a5e  jz      short loc_180159A7B
0x180159a60  xor     r9d, r9d
0x180159a63  mov     r8, cs:off_180263D18; "<SNITerminate|RET|SNI> %d{WINERR}\n"
0x180159a6a  mov     edx, 141000h
0x180159a6f  mov     rcx, cs:off_1802609D0; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180159a76  call    _bidTraceW
0x180159a7b  mov     rcx, [r14+10h]
0x180159a7f  add     rcx, 20h ; ' '
0x180159a83  mov     rax, [rcx]
0x180159a86  mov     rax, [rax+18h]
0x180159a8a  call    cs:__guard_dispatch_icall_fptr
0x180159a90  mov     eax, cs:_bidGblFlags
0x180159a96  and     eax, 20002h
0x180159a9b  cmp     eax, 20002h
0x180159aa0  jnz     short loc_180159ACA
0x180159aa2  mov     rax, cs:off_180263D20; "<SNITerminate|RET|SNI> %d{WINERR}\n"
0x180159aa9  test    rax, rax
0x180159aac  jz      short loc_180159ACA
0x180159aae  mov     r9d, ebp
0x180159ab1  mov     r8, cs:off_180263D20; "<SNITerminate|RET|SNI> %d{WINERR}\n"
0x180159ab8  mov     edx, 142800h
0x180159abd  mov     rcx, cs:off_1802609D8; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180159ac4  call    _bidTraceW
0x180159ac9  nop
0x180159aca  lea     rcx, [rsp+278h+var_238]; this
0x180159acf  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x180159ad4  nop
0x180159ad5  mov     eax, ebp
0x180159ad7  mov     rcx, [rsp+278h+var_28]
0x180159adf  xor     rcx, rsp; StackCookie
0x180159ae2  call    __security_check_cookie
0x180159ae7  lea     r11, [rsp+278h+var_18]
0x180159aef  mov     rbx, [r11+20h]
0x180159af3  mov     rbp, [r11+28h]
0x180159af7  mov     rsi, [r11+30h]
0x180159afb  mov     rsp, r11
0x180159afe  pop     r15
0x180159b00  pop     r14
0x180159b02  pop     rdi
0x180159b03  retn
```
