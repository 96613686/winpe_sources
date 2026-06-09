# PcaChainManagerChainStart(unsigned __int64 *,unsigned __int64,_PCA_CHAIN_DATA const *,void *)

- ea: `0x18001f254`
- end: `0x18001f51b`
- name: `?PcaChainManagerChainStart@@YAKPEA_K_KPEBU_PCA_CHAIN_DATA@@PEAX@Z`
- size: `711`
- prototype: `unsigned int(unsigned __int64 *, unsigned __int64, const struct _PCA_CHAIN_DATA *, void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001d23c`

## callees

- `0x180012920`
- `0x18001b320`
- `0x18001f254`
- `0x18001f890`
- `0x180025864`
- `0x180026858`
- `0x18004a0e8`
- `0x180056256`
- `0x1800f7010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18001f37c`
- `ntdll!RtlFreeHeap` at `0x18001f37c`
- `ntdll!RtlAllocateHeap` at `0x18001f29c`
- `ntdll!RtlAllocateHeap` at `0x18001f29c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f3f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f461`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f4b9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f3f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f461`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f4b9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f3e8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f3e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f317`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f434`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f317`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f434`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001f30d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001f30d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001f271`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001f271`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18001f42a`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18001f42a`

## string_xrefs

- `0x18001f31d`: `Failed to open process token [%d]`
- `0x18001f358`: `Failed to initialize chain processids [%d]`
- `0x18001f43a`: `Failed to create Chain timer [%d]`

## pseudocode

```c
__int64 __fastcall PcaChainManagerChainStart(
        unsigned __int64 *a1,
        __int64 a2,
        const struct _PCA_CHAIN_DATA *a3,
        void *a4)
{
  ULONGLONG TickCount64; // rax
  struct _PEB *v9; // rcx
  DWORD LastError; // edi
  ULONGLONG v11; // rsi
  char *Heap; // rax
  char *v13; // rbx
  int v14; // ecx
  DWORD v15; // eax
  const char *v16; // r9
  int v17; // r8d
  void *v18; // r8
  unsigned __int64 v19; // rdi
  __int64 v20; // rsi
  __int64 v21; // rdx

  TickCount64 = GetTickCount64();
  v9 = NtCurrentPeb();
  LastError = 8;
  *a1 = 0;
  v11 = TickCount64;
  Heap = (char *)RtlAllocateHeap(v9->ProcessHeap, 8u, 0x1688u);
  v13 = Heap;
  if ( !Heap )
  {
    AslLogCallPrintf(1, (unsigned int)"PcaChainManagerChainStart", 1117, (unsigned int)"Out of memory");
    return LastError;
  }
  *(_QWORD *)Heap = a2;
  v14 = (*(_DWORD *)a2)++;
  *((_DWORD *)Heap + 4) = v14;
  *((_QWORD *)Heap + 680) = v11;
  *((_QWORD *)Heap + 681) = -1;
  memcpy_0(Heap + 24, a3, 0x14C0u);
  if ( OpenProcessToken(a4, 0xEu, (PHANDLE)v13 + 667) )
  {
    LastError = RtlArray<_PCA_PROCESS>::Initialize(v13 + 5344);
    if ( !LastError )
    {
      v18 = (void *)*((_QWORD *)v13 + 679);
      if ( v18 )
        RtlFreeHeap(*((HANDLE *)v13 + 674), 0, v18);
      v19 = 0;
      *((_OWORD *)v13 + 337) = 0;
      *((_OWORD *)v13 + 338) = 0;
      *((_OWORD *)v13 + 339) = 0;
      *((_QWORD *)v13 + 674) = NtCurrentPeb()->ProcessHeap;
      *((_QWORD *)v13 + 678) = 16;
      *((_QWORD *)v13 + 675) = 32;
      while ( 1 )
      {
        if ( v19 >= 0x100 )
        {
          PcapChainManagerEnforceQuotas((struct _PCA_CHAIN_MANAGER *)a2);
          LastError = 1816;
          PcaTracePrintf("Chains", 0, 0, "ChainQuotaExceeded,%S", (const wchar_t *)a3 + 1556);
          PcaMarkEvent(11, 0);
          goto LABEL_20;
        }
        v20 = a2 + 56 * v19;
        if ( !*(_QWORD *)(v20 + 56) )
        {
          EnterCriticalSection((LPCRITICAL_SECTION)(v20 + 16));
          if ( !*(_QWORD *)(v20 + 56) )
          {
            if ( !CreateTimerQueueTimer(
                    (PHANDLE)v13 + 682,
                    0,
                    PcapChainTimerCallback,
                    (PVOID)(v20 + 8),
                    0xFFFFFFFF,
                    0xFFFFFFFF,
                    0) )
            {
              LastError = GetLastError();
              AslLogCallPrintf(
                1,
                (unsigned int)"PcaChainManagerChainStart",
                1189,
                (unsigned int)"Failed to create Chain timer [%d]");
              LeaveCriticalSection((LPCRITICAL_SECTION)(v20 + 16));
              goto LABEL_20;
            }
            *(_QWORD *)(v20 + 56) = v13;
            *((_QWORD *)v13 + 688) |= 1uLL;
            v21 = *((unsigned int *)v13 + 7);
            *((_QWORD *)v13 + 1) = v19;
            *((_DWORD *)v13 + 5) = 1;
            (*(void (__fastcall **)(char *, __int64, void *, char *, _QWORD))(a2 + 14344))(
              v13,
              v21,
              a4,
              v13 + 3136,
              *(_QWORD *)(a2 + 14392));
            *a1 = *((_QWORD *)v13 + 1) + 1LL;
            LeaveCriticalSection((LPCRITICAL_SECTION)(v20 + 16));
            return 0;
          }
          LeaveCriticalSection((LPCRITICAL_SECTION)(v20 + 16));
        }
        ++v19;
      }
    }
    v16 = "Failed to initialize chain processids [%d]";
    v17 = 1141;
  }
  else
  {
    v15 = GetLastError();
    v16 = "Failed to open process token [%d]";
    v17 = 1135;
    LastError = v15;
  }
  AslLogCallPrintf(1, (unsigned int)"PcaChainManagerChainStart", v17, (_DWORD)v16);
LABEL_20:
  PcapChainFree(v13, 0);
  return LastError;
}

```

## disassembly

```asm
0x18001f254  push    rbx
0x18001f256  push    rbp
0x18001f257  push    rsi
0x18001f258  push    rdi
0x18001f259  push    r12
0x18001f25b  push    r13
0x18001f25d  push    r14
0x18001f25f  push    r15
0x18001f261  sub     rsp, 48h
0x18001f265  mov     r12, r9
0x18001f268  mov     r15, r8
0x18001f26b  mov     r14, rdx
0x18001f26e  mov     r13, rcx
0x18001f271  call    cs:__imp_GetTickCount64
0x18001f277  mov     rcx, gs:60h
0x18001f280  mov     edi, 8
0x18001f285  mov     r8d, 1688h; Size
0x18001f28b  mov     qword ptr [r13+0], 0
0x18001f293  mov     edx, edi; Flags
0x18001f295  mov     rsi, rax
0x18001f298  mov     rcx, [rcx+30h]; HeapHandle
0x18001f29c  call    cs:__imp_RtlAllocateHeap
0x18001f2a2  mov     rbx, rax
0x18001f2a5  test    rax, rax
0x18001f2a8  jnz     short loc_18001F2CB
0x18001f2aa  lea     r9, aOutOfMemory; "Out of memory"
0x18001f2b1  mov     r8d, 45Dh
0x18001f2b7  lea     rdx, aPcachainmanage_0; "PcaChainManagerChainStart"
0x18001f2be  lea     ecx, [rdi-7]
0x18001f2c1  call    AslLogCallPrintf
0x18001f2c6  jmp     loc_18001F508
0x18001f2cb  mov     [rax], r14
0x18001f2ce  mov     r8d, 14C0h; Size
0x18001f2d4  mov     ecx, [r14]
0x18001f2d7  mov     rdx, r15; Src
0x18001f2da  lea     eax, [rcx+1]
0x18001f2dd  mov     [r14], eax
0x18001f2e0  mov     [rbx+10h], ecx
0x18001f2e3  lea     rcx, [rbx+18h]; void *
0x18001f2e7  mov     [rbx+1540h], rsi
0x18001f2ee  mov     qword ptr [rbx+1548h], 0FFFFFFFFFFFFFFFFh
0x18001f2f9  call    memcpy_0
0x18001f2fe  lea     r8, [rbx+14D8h]; TokenHandle
0x18001f305  mov     edx, 0Eh; DesiredAccess
0x18001f30a  mov     rcx, r12; ProcessHandle
0x18001f30d  call    cs:__imp_OpenProcessToken
0x18001f313  test    eax, eax
0x18001f315  jnz     short loc_18001F346
0x18001f317  call    cs:__imp_GetLastError
0x18001f31d  lea     r9, aFailedToOpenPr; "Failed to open process token [%d]"
0x18001f324  mov     r8d, 46Fh
0x18001f32a  mov     edi, eax
0x18001f32c  lea     rdx, aPcachainmanage_0; "PcaChainManagerChainStart"
0x18001f333  mov     [rsp+88h+DueTime], eax
0x18001f337  mov     ecx, 1
0x18001f33c  call    AslLogCallPrintf
0x18001f341  jmp     loc_18001F4FE
0x18001f346  lea     rcx, [rbx+14E0h]
0x18001f34d  call    ?Initialize@?$RtlArray@U_PCA_PROCESS@@@@QEAAJPEAX_K1H@Z; RtlArray<_PCA_PROCESS>::Initialize(void *,unsigned __int64,unsigned __int64,int)
0x18001f352  mov     edi, eax
0x18001f354  test    eax, eax
0x18001f356  jz      short loc_18001F367
0x18001f358  lea     r9, aFailedToInitia_10; "Failed to initialize chain processids ["...
0x18001f35f  mov     r8d, 475h
0x18001f365  jmp     short loc_18001F32C
0x18001f367  mov     r8, [rbx+1538h]; P
0x18001f36e  test    r8, r8
0x18001f371  jz      short loc_18001F382
0x18001f373  mov     rcx, [rbx+1510h]; HeapHandle
0x18001f37a  xor     edx, edx; Flags
0x18001f37c  call    cs:__imp_RtlFreeHeap
0x18001f382  xorps   xmm0, xmm0
0x18001f385  xor     edi, edi
0x18001f387  movups  xmmword ptr [rbx+1510h], xmm0
0x18001f38e  movups  xmmword ptr [rbx+1520h], xmm0
0x18001f395  movups  xmmword ptr [rbx+1530h], xmm0
0x18001f39c  mov     rax, gs:60h
0x18001f3a5  mov     rcx, [rax+30h]
0x18001f3a9  mov     [rbx+1510h], rcx
0x18001f3b0  mov     qword ptr [rbx+1530h], 10h
0x18001f3bb  mov     qword ptr [rbx+1518h], 20h ; ' '
0x18001f3c6  cmp     rdi, 100h
0x18001f3cd  jnb     loc_18001F4C3
0x18001f3d3  imul    rsi, rdi, 38h ; '8'
0x18001f3d7  add     rsi, r14
0x18001f3da  cmp     qword ptr [rsi+38h], 0
0x18001f3df  jnz     short loc_18001F3FE
0x18001f3e1  lea     rbp, [rsi+10h]
0x18001f3e5  mov     rcx, rbp; lpCriticalSection
0x18001f3e8  call    cs:__imp_EnterCriticalSection
0x18001f3ee  cmp     qword ptr [rsi+38h], 0
0x18001f3f3  jz      short loc_18001F403
0x18001f3f5  mov     rcx, rbp; lpCriticalSection
0x18001f3f8  call    cs:__imp_LeaveCriticalSection
0x18001f3fe  inc     rdi
0x18001f401  jmp     short loc_18001F3C6
0x18001f403  or      eax, 0FFFFFFFFh
0x18001f406  mov     [rsp+88h+Flags], 0; Flags
0x18001f40e  mov     [rsp+88h+Period], eax; Period
0x18001f412  lea     rcx, [rbx+1550h]; phNewTimer
0x18001f419  lea     r9, [rsi+8]; Parameter
0x18001f41d  mov     [rsp+88h+DueTime], eax; DueTime
0x18001f421  lea     r8, ?PcapChainTimerCallback@@YAXPEAXE@Z; Callback
0x18001f428  xor     edx, edx; TimerQueue
0x18001f42a  call    cs:__imp_CreateTimerQueueTimer
0x18001f430  test    eax, eax
0x18001f432  jnz     short loc_18001F46C
0x18001f434  call    cs:__imp_GetLastError
0x18001f43a  lea     r9, aFailedToCreate_42; "Failed to create Chain timer [%d]"
0x18001f441  mov     r8d, 4A5h
0x18001f447  lea     rdx, aPcachainmanage_0; "PcaChainManagerChainStart"
0x18001f44e  mov     [rsp+88h+DueTime], eax
0x18001f452  mov     ecx, 1
0x18001f457  mov     edi, eax
0x18001f459  call    AslLogCallPrintf
0x18001f45e  mov     rcx, rbp; lpCriticalSection
0x18001f461  call    cs:__imp_LeaveCriticalSection
0x18001f467  jmp     loc_18001F4FE
0x18001f46c  mov     [rsi+38h], rbx
0x18001f470  lea     r9, [rbx+0C40h]
0x18001f477  or      qword ptr [rbx+1580h], 1
0x18001f47f  mov     r8, r12
0x18001f482  mov     edx, [rbx+1Ch]
0x18001f485  mov     [rbx+8], rdi
0x18001f489  mov     dword ptr [rbx+14h], 1
0x18001f490  mov     rcx, [r14+3838h]
0x18001f497  mov     rax, [r14+3808h]
0x18001f49e  mov     qword ptr [rsp+88h+DueTime], rcx
0x18001f4a3  mov     rcx, rbx
0x18001f4a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f4ab  mov     rax, [rbx+8]
0x18001f4af  mov     rcx, rbp; lpCriticalSection
0x18001f4b2  inc     rax
0x18001f4b5  mov     [r13+0], rax
0x18001f4b9  call    cs:__imp_LeaveCriticalSection
0x18001f4bf  xor     edi, edi
0x18001f4c1  jmp     short loc_18001F508
0x18001f4c3  mov     rcx, r14; struct _PCA_CHAIN_MANAGER *
0x18001f4c6  call    ?PcapChainManagerEnforceQuotas@@YAXPEAU_PCA_CHAIN_MANAGER@@@Z; PcapChainManagerEnforceQuotas(_PCA_CHAIN_MANAGER *)
0x18001f4cb  lea     rax, [r15+0C28h]
0x18001f4d2  xor     r8d, r8d; unsigned int
0x18001f4d5  lea     r9, aChainquotaexce_0; "ChainQuotaExceeded,%S"
0x18001f4dc  mov     qword ptr [rsp+88h+DueTime], rax
0x18001f4e1  xor     edx, edx; unsigned int
0x18001f4e3  lea     rcx, aChains; "Chains"
0x18001f4ea  mov     edi, 718h
0x18001f4ef  call    ?PcaTracePrintf@@YAXPEBDIK0ZZ; PcaTracePrintf(char const *,uint,ulong,char const *,...)
0x18001f4f4  xor     edx, edx
0x18001f4f6  lea     ecx, [rdx+0Bh]
0x18001f4f9  call    ?PcaMarkEvent@@YAXW4_PCA_MARK_EVENT@@I@Z; PcaMarkEvent(_PCA_MARK_EVENT,uint)
0x18001f4fe  xor     edx, edx; int
0x18001f500  mov     rcx, rbx; P
0x18001f503  call    ?PcapChainFree@@YAXPEAU_PCA_CHAIN@@H@Z; PcapChainFree(_PCA_CHAIN *,int)
0x18001f508  mov     eax, edi
0x18001f50a  add     rsp, 48h
0x18001f50e  pop     r15
0x18001f510  pop     r14
0x18001f512  pop     r13
0x18001f514  pop     r12
0x18001f516  pop     rdi
0x18001f517  pop     rsi
0x18001f518  pop     rbp
0x18001f519  pop     rbx
0x18001f51a  retn
```
