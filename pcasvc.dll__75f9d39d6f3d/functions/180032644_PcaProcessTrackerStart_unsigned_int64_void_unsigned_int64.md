# PcaProcessTrackerStart(unsigned __int64,void *,unsigned __int64)

- ea: `0x180032644`
- end: `0x180032a36`
- name: `?PcaProcessTrackerStart@@YAK_KPEAX0@Z`
- size: `1010`
- prototype: `unsigned int __fastcall(LPVOID lpParameter, HANDLE hProcess, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001d23c`

## callees

- `0x180012920`
- `0x180032644`
- `0x18007a9cf`
- `0x1800f1f10`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800327e1`
- `ntdll!RtlFreeHeap` at `0x1800327e1`
- `ntdll!RtlReAllocateHeap` at `0x18003294e`
- `ntdll!RtlReAllocateHeap` at `0x18003294e`
- `ntdll!RtlAllocateHeap` at `0x1800326cb`
- `ntdll!RtlAllocateHeap` at `0x180032913`
- `ntdll!RtlAllocateHeap` at `0x1800326cb`
- `ntdll!RtlAllocateHeap` at `0x180032913`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800327f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800327f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032696`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032696`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032841`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800328c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003298e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800329a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800329b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800329d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800329f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032841`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800328c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003298e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800329a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800329b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800329d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800329f4`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003297b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003297b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032a2b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032a2b`
- `api-ms-win-core-job-l2-1-0!CreateJobObjectW` at `0x1800326e8`
- `api-ms-win-core-job-l2-1-0!CreateJobObjectW` at `0x1800326e8`
- `api-ms-win-core-job-l2-1-0!QueryInformationJobObject` at `0x180032714`
- `api-ms-win-core-job-l2-1-0!QueryInformationJobObject` at `0x180032714`
- `api-ms-win-core-job-l2-1-0!AssignProcessToJobObject` at `0x180032772`
- `api-ms-win-core-job-l2-1-0!AssignProcessToJobObject` at `0x180032772`
- `api-ms-win-core-job-l2-1-0!SetInformationJobObject` at `0x180032733`
- `api-ms-win-core-job-l2-1-0!SetInformationJobObject` at `0x18003275e`
- `api-ms-win-core-job-l2-1-0!SetInformationJobObject` at `0x180032733`
- `api-ms-win-core-job-l2-1-0!SetInformationJobObject` at `0x18003275e`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x18003282e`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x18003282e`

## string_xrefs

- `0x180032847`: `Failed to create completion port [%d]`
- `0x1800328cd`: `Failed to associate completion port data with job object [%d]`
- `0x180032994`: `Failed to create job thread [%d]`

## pseudocode

```c
__int64 __fastcall PcaProcessTrackerStart(struct _RTL_CRITICAL_SECTION *lpParameter, HANDLE hProcess, __int64 a3)
{
  DWORD v6; // ebx
  _QWORD *Heap; // rax
  _QWORD *v8; // r14
  HANDLE JobObjectW; // rax
  void *v10; // rsi
  unsigned __int64 OwningThread; // r13
  struct _RTL_CRITICAL_SECTION_DEBUG *v12; // rax
  const char *v13; // r9
  int v14; // r8d
  int v15; // ecx
  HANDLE IoCompletionPort; // rax
  DWORD LastError; // eax
  const char *v19; // r9
  int v20; // r8d
  unsigned __int64 v21; // rcx
  __int64 v22; // r15
  unsigned __int64 v23; // r15
  unsigned __int128 v24; // rax
  size_t v25; // r12
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // r8
  PRTL_CRITICAL_SECTION_DEBUG v27; // rcx
  struct _RTL_CRITICAL_SECTION_DEBUG *v28; // rax
  struct _RTL_CRITICAL_SECTION_DEBUG *v29; // rbx
  HANDLE Thread; // rax
  DWORD lpReturnLength; // [rsp+20h] [rbp-A9h]
  DWORD lpReturnLengtha; // [rsp+20h] [rbp-A9h]
  DWORD lpReturnLengthb; // [rsp+20h] [rbp-A9h]
  DWORD lpReturnLengthc; // [rsp+20h] [rbp-A9h]
  __int128 v35; // [rsp+38h] [rbp-91h] BYREF
  _BYTE JobObjectInformation[16]; // [rsp+50h] [rbp-79h] BYREF
  int v37; // [rsp+60h] [rbp-69h]

  v35 = 0;
  memset_0(JobObjectInformation, 0, 0x90u);
  EnterCriticalSection(lpParameter);
  if ( !lpParameter[2].OwningThread )
  {
    IoCompletionPort = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, 0);
    lpParameter[2].OwningThread = IoCompletionPort;
    if ( !IoCompletionPort )
    {
      LastError = GetLastError();
      v19 = "Failed to create completion port [%d]";
      v20 = 501;
LABEL_21:
      v6 = LastError;
      AslLogCallPrintf(1, (unsigned int)"PcaProcessTrackerStart", v20, (_DWORD)v19);
      goto LABEL_18;
    }
  }
  if ( !*(_QWORD *)&lpParameter[2].LockCount )
  {
    Thread = CreateThread(0, 0, PcapJobTrackerThread, lpParameter, 0, 0);
    *(_QWORD *)&lpParameter[2].LockCount = Thread;
    if ( !Thread )
    {
      LastError = GetLastError();
      v19 = "Failed to create job thread [%d]";
      v20 = 515;
      goto LABEL_21;
    }
  }
  v6 = 8;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x18u);
  v8 = Heap;
  if ( !Heap )
  {
    AslLogCallPrintf(1, (unsigned int)"PcaProcessTrackerStart", 527, (unsigned int)"Out of memory");
    goto LABEL_18;
  }
  *Heap = lpParameter;
  Heap[2] = a3;
  JobObjectW = CreateJobObjectW(0, 0);
  v10 = JobObjectW;
  if ( JobObjectW )
  {
    v8[1] = JobObjectW;
    if ( !QueryInformationJobObject(JobObjectW, JobObjectExtendedLimitInformation, JobObjectInformation, 0x90u, 0) )
    {
      lpReturnLengtha = GetLastError();
      v13 = "Failed to query job information [%d]";
      v6 = lpReturnLengtha;
      v14 = 561;
      goto LABEL_14;
    }
    v37 |= 0x800u;
    if ( !SetInformationJobObject(v10, JobObjectExtendedLimitInformation, JobObjectInformation, 0x90u) )
    {
      lpReturnLengthb = GetLastError();
      v13 = "Failed to allow breakaway on job object [%d]";
      v6 = lpReturnLengthb;
      v14 = 573;
      v15 = 2;
      goto LABEL_15;
    }
    *((_QWORD *)&v35 + 1) = lpParameter[2].OwningThread;
    *(_QWORD *)&v35 = v8;
    if ( !SetInformationJobObject(v10, JobObjectAssociateCompletionPortInformation, &v35, 0x10u) )
    {
      lpReturnLength = GetLastError();
      v13 = "Failed to associate completion port data with job object [%d]";
      v6 = lpReturnLength;
      v14 = 591;
      goto LABEL_14;
    }
    if ( !AssignProcessToJobObject(v10, hProcess) )
    {
      lpReturnLengthc = GetLastError();
      v13 = "Failed to associate process with job [%d]";
      v6 = lpReturnLengthc;
      v14 = 602;
      goto LABEL_14;
    }
    OwningThread = (unsigned __int64)lpParameter[1].OwningThread;
    if ( (HANDLE)OwningThread < lpParameter[1].LockSemaphore )
      goto LABEL_10;
    v21 = OwningThread + 1;
    if ( (HANDLE)(OwningThread + 1) <= lpParameter[1].LockSemaphore )
    {
      v6 = -1073741811;
    }
    else
    {
      v22 = lpParameter[1].SpinCount - 1;
      if ( v22 + v21 >= v21
        && is_mul_ok((unsigned __int64)lpParameter[1].LockSemaphore, *(_QWORD *)&lpParameter[1].LockCount)
        && (v23 = (v22 + v21) & ~v22,
            v24 = v23 * (unsigned __int128)*(unsigned __int64 *)&lpParameter[1].LockCount,
            v25 = v23 * *(_QWORD *)&lpParameter[1].LockCount,
            is_mul_ok(v23, *(_QWORD *)&lpParameter[1].LockCount)) )
      {
        DebugInfo = lpParameter[2].DebugInfo;
        v27 = lpParameter[1].DebugInfo;
        if ( DebugInfo )
        {
          v29 = (struct _RTL_CRITICAL_SECTION_DEBUG *)RtlReAllocateHeap(
                                                        v27,
                                                        DWORD2(v24),
                                                        DebugInfo,
                                                        v23 * *(_QWORD *)&lpParameter[1].LockCount);
        }
        else
        {
          v28 = (struct _RTL_CRITICAL_SECTION_DEBUG *)RtlAllocateHeap(
                                                        v27,
                                                        DWORD2(v24),
                                                        v23 * *(_QWORD *)&lpParameter[1].LockCount);
          v29 = v28;
          if ( v28 )
            memset_0(v28, 0, v25);
        }
        if ( v29 )
        {
          lpParameter[2].DebugInfo = v29;
          lpParameter[1].LockSemaphore = (HANDLE)v23;
LABEL_10:
          if ( is_mul_ok(*(_QWORD *)&lpParameter[1].LockCount, OwningThread) )
          {
            v12 = (PRTL_CRITICAL_SECTION_DEBUG)((char *)lpParameter[2].DebugInfo
                                              + *(_QWORD *)&lpParameter[1].LockCount * OwningThread);
            if ( v12 >= lpParameter[2].DebugInfo )
            {
              *(_QWORD *)&v12->Type = v8;
              ++lpParameter[1].OwningThread;
              v6 = 0;
              goto LABEL_18;
            }
          }
          v6 = -1073741675;
          goto LABEL_13;
        }
        v6 = -1073741801;
      }
      else
      {
        v6 = -1073741675;
      }
    }
LABEL_13:
    v13 = "Failed to add context to the list [%d]";
    v14 = 612;
LABEL_14:
    v15 = 1;
LABEL_15:
    AslLogCallPrintf(v15, (unsigned int)"PcaProcessTrackerStart", v14, (_DWORD)v13);
    goto LABEL_16;
  }
  v6 = GetLastError();
LABEL_16:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
  if ( v10 )
    CloseHandle(v10);
LABEL_18:
  LeaveCriticalSection(lpParameter);
  return v6;
}

```

## disassembly

```asm
0x180032644  mov     [rsp-8+arg_10], rbx
0x180032649  push    rbp
0x18003264a  push    rsi
0x18003264b  push    rdi
0x18003264c  push    r12
0x18003264e  push    r13
0x180032650  push    r14
0x180032652  push    r15
0x180032654  lea     rbp, [rsp-27h]
0x180032659  sub     rsp, 0F0h
0x180032660  mov     rax, cs:__security_cookie
0x180032667  xor     rax, rsp
0x18003266a  mov     [rbp+57h+var_40], rax
0x18003266e  mov     rsi, r8
0x180032671  mov     r15, rdx
0x180032674  mov     rdi, rcx
0x180032677  xorps   xmm0, xmm0
0x18003267a  mov     r13d, 90h
0x180032680  lea     rcx, [rbp+57h+JobObjectInformation]; void *
0x180032684  mov     r8d, r13d; Size
0x180032687  xor     edx, edx; Val
0x180032689  movups  [rsp+120h+var_E8], xmm0
0x18003268e  call    memset_0
0x180032693  mov     rcx, rdi; lpCriticalSection
0x180032696  call    cs:__imp_EnterCriticalSection
0x18003269c  xor     r12d, r12d
0x18003269f  cmp     [rdi+60h], r12
0x1800326a3  jz      loc_180032822
0x1800326a9  cmp     [rdi+58h], r12
0x1800326ad  jz      loc_180032963
0x1800326b3  mov     rcx, gs:60h
0x1800326bc  mov     ebx, 8
0x1800326c1  mov     edx, ebx; Flags
0x1800326c3  mov     rcx, [rcx+30h]; HeapHandle
0x1800326c7  lea     r8d, [rbx+10h]; Size
0x1800326cb  call    cs:__imp_RtlAllocateHeap
0x1800326d1  mov     r14, rax
0x1800326d4  test    rax, rax
0x1800326d7  jz      loc_18003286D
0x1800326dd  mov     [rax], rdi
0x1800326e0  xor     edx, edx; lpName
0x1800326e2  xor     ecx, ecx; lpJobAttributes
0x1800326e4  mov     [rax+10h], rsi
0x1800326e8  call    cs:__imp_CreateJobObjectW
0x1800326ee  mov     rsi, rax
0x1800326f1  test    rax, rax
0x1800326f4  jz      loc_1800329A6
0x1800326fa  mov     ebx, 9
0x1800326ff  mov     [r14+8], rax
0x180032703  mov     edx, ebx; JobObjectInformationClass
0x180032705  mov     [rsp+120h+lpReturnLength], r12; lpReturnLength
0x18003270a  mov     r9d, r13d; cbJobObjectInformationLength
0x18003270d  lea     r8, [rbp+57h+JobObjectInformation]; lpJobObjectInformation
0x180032711  mov     rcx, rax; hJob
0x180032714  call    cs:__imp_QueryInformationJobObject
0x18003271a  test    eax, eax
0x18003271c  jz      loc_1800329B3
0x180032722  bts     [rbp+57h+var_C0], 0Bh
0x180032727  lea     r8, [rbp+57h+JobObjectInformation]; lpJobObjectInformation
0x18003272b  mov     r9d, r13d; cbJobObjectInformationLength
0x18003272e  mov     edx, ebx; JobObjectInformationClass
0x180032730  mov     rcx, rsi; hJob
0x180032733  call    cs:__imp_SetInformationJobObject
0x180032739  test    eax, eax
0x18003273b  jz      loc_1800329D1
0x180032741  mov     rax, [rdi+60h]
0x180032745  lea     r9d, [rbx+7]; cbJobObjectInformationLength
0x180032749  lea     r8, [rsp+120h+var_E8]; lpJobObjectInformation
0x18003274e  mov     qword ptr [rsp+120h+var_E8+8], rax
0x180032753  lea     edx, [rbx-2]; JobObjectInformationClass
0x180032756  mov     qword ptr [rsp+120h+var_E8], r14
0x18003275b  mov     rcx, rsi; hJob
0x18003275e  call    cs:__imp_SetInformationJobObject
0x180032764  test    eax, eax
0x180032766  jz      loc_1800328C3
0x18003276c  mov     rdx, r15; hProcess
0x18003276f  mov     rcx, rsi; hJob
0x180032772  call    cs:__imp_AssignProcessToJobObject
0x180032778  test    eax, eax
0x18003277a  jz      loc_1800329F4
0x180032780  mov     r13, [rdi+38h]
0x180032784  cmp     r13, [rdi+40h]
0x180032788  jnb     loc_180032890
0x18003278e  mov     rax, r13
0x180032791  mul     qword ptr [rdi+30h]
0x180032795  test    rdx, rdx
0x180032798  jnz     short loc_1800327A8
0x18003279a  add     rax, [rdi+50h]
0x18003279e  cmp     rax, [rdi+50h]
0x1800327a2  jnb     loc_180032A1C
0x1800327a8  mov     ebx, 0C0000095h
0x1800327ad  mov     dword ptr [rsp+120h+lpReturnLength], ebx
0x1800327b1  lea     r9, aFailedToAddCon; "Failed to add context to the list [%d]"
0x1800327b8  mov     r8d, 264h
0x1800327be  mov     ecx, 1
0x1800327c3  lea     rdx, aPcaprocesstrac; "PcaProcessTrackerStart"
0x1800327ca  call    AslLogCallPrintf
0x1800327cf  mov     rcx, gs:60h
0x1800327d8  mov     r8, r14; P
0x1800327db  xor     edx, edx; Flags
0x1800327dd  mov     rcx, [rcx+30h]; HeapHandle
0x1800327e1  call    cs:__imp_RtlFreeHeap
0x1800327e7  test    rsi, rsi
0x1800327ea  jnz     loc_180032A28
0x1800327f0  mov     rcx, rdi; lpCriticalSection
0x1800327f3  call    cs:__imp_LeaveCriticalSection
0x1800327f9  mov     eax, ebx
0x1800327fb  mov     rcx, [rbp+57h+var_40]
0x1800327ff  xor     rcx, rsp; StackCookie
0x180032802  call    __security_check_cookie
0x180032807  mov     rbx, [rsp+120h+arg_10]
0x18003280f  add     rsp, 0F0h
0x180032816  pop     r15
0x180032818  pop     r14
0x18003281a  pop     r13
0x18003281c  pop     r12
0x18003281e  pop     rdi
0x18003281f  pop     rsi
0x180032820  pop     rbp
0x180032821  retn
0x180032822  xor     r9d, r9d; NumberOfConcurrentThreads
0x180032825  xor     r8d, r8d; CompletionKey
0x180032828  xor     edx, edx; ExistingCompletionPort
0x18003282a  or      rcx, 0FFFFFFFFFFFFFFFFh; FileHandle
0x18003282e  call    cs:__imp_CreateIoCompletionPort
0x180032834  mov     [rdi+60h], rax
0x180032838  test    rax, rax
0x18003283b  jnz     loc_1800326A9
0x180032841  call    cs:__imp_GetLastError
0x180032847  lea     r9, aFailedToCreate_80; "Failed to create completion port [%d]"
0x18003284e  mov     r8d, 1F5h
0x180032854  lea     rdx, aPcaprocesstrac; "PcaProcessTrackerStart"
0x18003285b  mov     dword ptr [rsp+120h+lpReturnLength], eax
0x18003285f  mov     ecx, 1
0x180032864  mov     ebx, eax
0x180032866  call    AslLogCallPrintf
0x18003286b  jmp     short loc_1800327F0
0x18003286d  lea     r9, aOutOfMemory; "Out of memory"
0x180032874  mov     r8d, 20Fh
0x18003287a  lea     rdx, aPcaprocesstrac; "PcaProcessTrackerStart"
0x180032881  mov     ecx, 1
0x180032886  call    AslLogCallPrintf
0x18003288b  jmp     loc_1800327F0
0x180032890  lea     rcx, [r13+1]
0x180032894  cmp     rcx, [rdi+40h]
0x180032898  jbe     loc_180032A12
0x18003289e  mov     r15, [rdi+48h]
0x1800328a2  dec     r15
0x1800328a5  lea     r8, [r15+rcx]
0x1800328a9  cmp     r8, rcx
0x1800328ac  jnb     short loc_1800328E1
0x1800328ae  mov     ebx, 0C0000095h
0x1800328b3  test    ebx, ebx
0x1800328b5  jnz     loc_1800327AD
0x1800328bb  mov     ebx, r12d
0x1800328be  jmp     loc_1800327F0
0x1800328c3  call    cs:__imp_GetLastError
0x1800328c9  mov     dword ptr [rsp+120h+lpReturnLength], eax
0x1800328cd  lea     r9, aFailedToAssoci_0; "Failed to associate completion port dat"...
0x1800328d4  mov     ebx, eax
0x1800328d6  mov     r8d, 24Fh
0x1800328dc  jmp     loc_1800327BE
0x1800328e1  mov     rax, [rdi+30h]
0x1800328e5  mul     qword ptr [rdi+40h]
0x1800328e9  test    rdx, rdx
0x1800328ec  jnz     short loc_1800328AE
0x1800328ee  mov     rax, [rdi+30h]
0x1800328f2  not     r15
0x1800328f5  and     r15, r8
0x1800328f8  mul     r15
0x1800328fb  mov     r12, rax
0x1800328fe  test    rdx, rdx
0x180032901  jnz     short loc_180032943
0x180032903  mov     r8, [rdi+50h]; Ptr
0x180032907  mov     rcx, [rdi+28h]; Heap
0x18003290b  test    r8, r8
0x18003290e  jnz     short loc_18003294B
0x180032910  mov     r8, rax; Size
0x180032913  call    cs:__imp_RtlAllocateHeap
0x180032919  mov     rbx, rax
0x18003291c  test    rax, rax
0x18003291f  jz      short loc_18003292E
0x180032921  mov     r8, r12; Size
0x180032924  xor     edx, edx; Val
0x180032926  mov     rcx, rax; void *
0x180032929  call    memset_0
0x18003292e  xor     r12d, r12d
0x180032931  test    rbx, rbx
0x180032934  jz      short loc_180032959
0x180032936  mov     [rdi+50h], rbx
0x18003293a  mov     [rdi+40h], r15
0x18003293e  jmp     loc_18003278E
0x180032943  xor     r12d, r12d
0x180032946  jmp     loc_1800328AE
0x18003294b  mov     r9, r12; Size
0x18003294e  call    cs:__imp_RtlReAllocateHeap
0x180032954  mov     rbx, rax
0x180032957  jmp     short loc_18003292E
0x180032959  mov     ebx, 0C0000017h
0x18003295e  jmp     loc_1800328B3
0x180032963  mov     [rsp+120h+lpThreadId], r12; lpThreadId
0x180032968  lea     r8, ?PcapJobTrackerThread@@YAKPEAX@Z; lpStartAddress
0x18003296f  mov     r9, rdi; lpParameter
0x180032972  mov     dword ptr [rsp+120h+lpReturnLength], r12d; dwCreationFlags
0x180032977  xor     edx, edx; dwStackSize
0x180032979  xor     ecx, ecx; lpThreadAttributes
0x18003297b  call    cs:__imp_CreateThread
0x180032981  mov     [rdi+58h], rax
0x180032985  test    rax, rax
0x180032988  jnz     loc_1800326B3
0x18003298e  call    cs:__imp_GetLastError
0x180032994  lea     r9, aFailedToCreate_33; "Failed to create job thread [%d]"
0x18003299b  mov     r8d, 203h
0x1800329a1  jmp     loc_180032854
0x1800329a6  call    cs:__imp_GetLastError
0x1800329ac  mov     ebx, eax
0x1800329ae  jmp     loc_1800327CF
0x1800329b3  call    cs:__imp_GetLastError
0x1800329b9  mov     dword ptr [rsp+120h+lpReturnLength], eax
0x1800329bd  lea     r9, aFailedToQueryJ; "Failed to query job information [%d]"
0x1800329c4  mov     ebx, eax
0x1800329c6  mov     r8d, 231h
0x1800329cc  jmp     loc_1800327BE
0x1800329d1  call    cs:__imp_GetLastError
0x1800329d7  mov     dword ptr [rsp+120h+lpReturnLength], eax
0x1800329db  lea     r9, aFailedToAllowB; "Failed to allow breakaway on job object"...
0x1800329e2  mov     ebx, eax
0x1800329e4  mov     r8d, 23Dh
0x1800329ea  mov     ecx, 2
0x1800329ef  jmp     loc_1800327C3
0x1800329f4  call    cs:__imp_GetLastError
0x1800329fa  mov     dword ptr [rsp+120h+lpReturnLength], eax
0x1800329fe  lea     r9, aFailedToAssoci; "Failed to associate process with job [%"...
0x180032a05  mov     ebx, eax
0x180032a07  mov     r8d, 25Ah
0x180032a0d  jmp     loc_1800327BE
0x180032a12  mov     ebx, 0C000000Dh
0x180032a17  jmp     loc_1800328B3
0x180032a1c  mov     [rax], r14
0x180032a1f  inc     qword ptr [rdi+38h]
0x180032a23  jmp     loc_1800328BB
0x180032a28  mov     rcx, rsi; hObject
0x180032a2b  call    cs:__imp_CloseHandle
0x180032a31  jmp     loc_1800327F0
```
