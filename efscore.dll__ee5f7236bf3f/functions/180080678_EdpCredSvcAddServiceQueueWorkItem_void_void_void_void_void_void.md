# EdpCredSvcAddServiceQueueWorkItem(void (*)(void *),void *,void (*)(void *),void *)

- ea: `0x180080678`
- end: `0x18008087f`
- name: `?EdpCredSvcAddServiceQueueWorkItem@@YAJP6AXPEAX@Z010@Z`
- size: `519`
- prototype: `__int64 __fastcall(void (*)(void *), void *, void (*)(void *), void *)`
- caller_count: `7`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180085c28`
- `0x180086a88`
- `0x18009ba70`
- `0x1800a849c`
- `0x1800b7794`
- `0x1800bd200`
- `0x1800bd368`

## callees

- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x180080678`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180080746`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180080746`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008081f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008081f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800806fa`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800806fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800806e8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008082a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800806e8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008082a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180080838`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180080838`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800807a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800807a5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18008079a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18008079a`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180080816`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180080816`

## pseudocode

```c
__int64 __fastcall EdpCredSvcAddServiceQueueWorkItem(void (*a1)(void *), void *a2, void (*a3)(void *), void *a4)
{
  unsigned int v8; // ebx
  HANDLE ProcessHeap; // rax
  _QWORD *v10; // rax
  _QWORD *v11; // rdi
  struct _TP_WORK *ThreadpoolWork; // rax
  signed int LastError; // eax
  _QWORD *v14; // rax
  HANDLE v15; // rax

  fnEfsLogTrace1Strings((_DWORD)a1, (unsigned int)EFS_TRACE_ENTER_EVENT, (unsigned int)&sourceString, 38, 247);
  if ( !a1 )
  {
    v8 = -2147024809;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024809, 38, 249);
    goto LABEL_21;
  }
  ProcessHeap = GetProcessHeap();
  v10 = HeapAlloc(ProcessHeap, 8u, 0x30u);
  v11 = v10;
  if ( !v10 )
  {
    v8 = -2147024882;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024882, 38, 1);
    goto LABEL_21;
  }
  *v10 = 0;
  v10[1] = 0;
  v10[4] = a4;
  v10[3] = a1;
  v10[2] = a2;
  v10[5] = a3;
  EnterCriticalSection(&g_ServiceQueue);
  if ( !HIDWORD(qword_180117480) )
  {
    if ( !pwk )
    {
      ThreadpoolWork = CreateThreadpoolWork(EdppCredSvcWorkCallback, &g_ServiceQueue, 0);
      if ( !ThreadpoolWork )
      {
        LastError = GetLastError();
        v8 = LastError;
        if ( LastError > 0 )
          v8 = (unsigned __int16)LastError | 0x80070000;
        fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v8, 38, 40);
        goto LABEL_19;
      }
      pwk = ThreadpoolWork;
    }
    v14 = (_QWORD *)qword_180117470;
    if ( *(LPVOID **)qword_180117470 != &lpMem )
      __fastfail(3u);
    *v11 = &lpMem;
    v8 = 0;
    v11[1] = v14;
    *v14 = v11;
    qword_180117470 = (__int64)v11;
    v11 = 0;
    if ( !(_DWORD)qword_180117480 )
    {
      LODWORD(qword_180117480) = 1;
      SubmitThreadpoolWork(pwk);
    }
    goto LABEL_19;
  }
  v8 = -2147023835;
  fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147023835, 38, 23);
LABEL_19:
  LeaveCriticalSection(&g_ServiceQueue);
  if ( v11 )
  {
    v15 = GetProcessHeap();
    HeapFree(v15, 0, v11);
  }
LABEL_21:
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT_ERROR,
    (unsigned int)&sourceString,
    v8,
    38,
    86);
  return v8;
}

```

## disassembly

```asm
0x180080678  push    rbx
0x18008067a  push    rbp
0x18008067b  push    rsi
0x18008067c  push    rdi
0x18008067d  push    r12
0x18008067f  push    r14
0x180080681  sub     rsp, 48h
0x180080685  mov     rsi, r9
0x180080688  mov     [rsp+78h+var_58], 12F7h
0x180080690  mov     rbp, r8
0x180080693  mov     r14, rdx
0x180080696  mov     r12d, 26h ; '&'
0x18008069c  lea     r8, sourceString
0x1800806a3  mov     r9d, r12d
0x1800806a6  lea     rdx, EFS_TRACE_ENTER_EVENT
0x1800806ad  mov     rbx, rcx
0x1800806b0  call    fnEfsLogTrace1Strings
0x1800806b5  test    rbx, rbx
0x1800806b8  jnz     short loc_1800806E8
0x1800806ba  mov     ebx, 80070057h
0x1800806bf  mov     [rsp+78h+var_58], 12F9h
0x1800806c7  mov     r8d, 80070057h
0x1800806cd  mov     rcx, cs:g_hPublisher
0x1800806d4  lea     rdx, EFS_TRACE_ERROR
0x1800806db  mov     r9d, r12d
0x1800806de  call    fnEfsLogTrace1
0x1800806e3  jmp     loc_18008083E
0x1800806e8  call    cs:__imp_GetProcessHeap
0x1800806ee  mov     edx, 8; dwFlags
0x1800806f3  mov     rcx, rax; hHeap
0x1800806f6  lea     r8d, [rdx+28h]; dwBytes
0x1800806fa  call    cs:__imp_HeapAlloc
0x180080700  mov     rdi, rax
0x180080703  test    rax, rax
0x180080706  jnz     short loc_18008071D
0x180080708  mov     ebx, 8007000Eh
0x18008070d  mov     [rsp+78h+var_58], 1301h
0x180080715  mov     r8d, 8007000Eh
0x18008071b  jmp     short loc_1800806CD
0x18008071d  mov     qword ptr [rax], 0
0x180080724  mov     qword ptr [rax+8], 0
0x18008072c  mov     [rax+20h], rsi
0x180080730  lea     rsi, ?g_ServiceQueue@@3U_EDP_CRED_SVC_QUEUE@@A; _EDP_CRED_SVC_QUEUE g_ServiceQueue
0x180080737  mov     rcx, rsi; lpCriticalSection
0x18008073a  mov     [rax+18h], rbx
0x18008073e  mov     [rax+10h], r14
0x180080742  mov     [rax+28h], rbp
0x180080746  call    cs:__imp_EnterCriticalSection
0x18008074c  cmp     dword ptr cs:qword_180117480+4, 0
0x180080753  jz      short loc_180080783
0x180080755  mov     ebx, 80070425h
0x18008075a  mov     [rsp+78h+var_58], 1317h
0x180080762  mov     r8d, 80070425h
0x180080768  mov     rcx, cs:g_hPublisher
0x18008076f  lea     rdx, EFS_TRACE_ERROR
0x180080776  mov     r9d, r12d
0x180080779  call    fnEfsLogTrace1
0x18008077e  jmp     loc_18008081C
0x180080783  cmp     cs:pwk, 0
0x18008078b  jnz     short loc_1800807CE
0x18008078d  xor     r8d, r8d; pcbe
0x180080790  lea     rcx, ?EdppCredSvcWorkCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180080797  mov     rdx, rsi; pv
0x18008079a  call    cs:__imp_CreateThreadpoolWork
0x1800807a0  test    rax, rax
0x1800807a3  jnz     short loc_1800807C7
0x1800807a5  call    cs:__imp_GetLastError
0x1800807ab  mov     ebx, eax
0x1800807ad  test    eax, eax
0x1800807af  jle     short loc_1800807BA
0x1800807b1  movzx   ebx, ax
0x1800807b4  or      ebx, 80070000h
0x1800807ba  mov     [rsp+78h+var_58], 1328h
0x1800807c2  mov     r8d, ebx
0x1800807c5  jmp     short loc_180080768
0x1800807c7  mov     cs:pwk, rax
0x1800807ce  mov     rax, cs:qword_180117470
0x1800807d5  lea     rcx, lpMem
0x1800807dc  cmp     [rax], rcx
0x1800807df  jz      short loc_1800807E8
0x1800807e1  mov     ecx, 3
0x1800807e6  int     29h; Win8: RtlFailFast(ecx)
0x1800807e8  mov     [rdi], rcx
0x1800807eb  xor     ebx, ebx
0x1800807ed  mov     [rdi+8], rax
0x1800807f1  mov     [rax], rdi
0x1800807f4  mov     cs:qword_180117470, rdi
0x1800807fb  xor     edi, edi
0x1800807fd  cmp     dword ptr cs:qword_180117480, ebx
0x180080803  jnz     short loc_18008081C
0x180080805  mov     rcx, cs:pwk; pwk
0x18008080c  mov     dword ptr cs:qword_180117480, 1
0x180080816  call    cs:__imp_SubmitThreadpoolWork
0x18008081c  mov     rcx, rsi; lpCriticalSection
0x18008081f  call    cs:__imp_LeaveCriticalSection
0x180080825  test    rdi, rdi
0x180080828  jz      short loc_18008083E
0x18008082a  call    cs:__imp_GetProcessHeap
0x180080830  mov     r8, rdi; lpMem
0x180080833  xor     edx, edx; dwFlags
0x180080835  mov     rcx, rax; hHeap
0x180080838  call    cs:__imp_HeapFree
0x18008083e  mov     rcx, cs:g_hPublisher
0x180080845  lea     r9, sourceString
0x18008084c  mov     [rsp+78h+var_48], 1356h
0x180080854  lea     r8, EFS_TRACE_LEAVE_HR_EVENT_ERROR
0x18008085b  mov     [rsp+78h+var_50], r12d
0x180080860  lea     rdx, EFS_TRACE_LEAVE_HR_EVENT
0x180080867  mov     [rsp+78h+var_58], ebx
0x18008086b  call    fnEfsLogTrace1String1Dword
0x180080870  mov     eax, ebx
0x180080872  add     rsp, 48h
0x180080876  pop     r14
0x180080878  pop     r12
0x18008087a  pop     rdi
0x18008087b  pop     rsi
0x18008087c  pop     rbp
0x18008087d  pop     rbx
0x18008087e  retn
```
