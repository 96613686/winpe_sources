# EdpCredSvcShutdownServiceQueue(void)

- ea: `0x18008649c`
- end: `0x18008661a`
- name: `?EdpCredSvcShutdownServiceQueue@@YAXXZ`
- size: `382`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180080da0`

## callees

- `0x1800637e8`
- `0x18008649c`
- `0x1800e0010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800864ed`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800864ed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008656c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008656c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800865b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800865b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800865be`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800865be`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800865da`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800865da`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800865e3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800865e3`

## pseudocode

```c
void __fastcall EdpCredSvcShutdownServiceQueue(int a1)
{
  struct _TP_WORK *v1; // rdi
  LPVOID *v2; // rax
  __int64 v3; // rcx
  LPVOID **v4; // rcx
  int v5; // ecx
  _QWORD *v6; // rbx
  __int64 v7; // rax
  void (__fastcall *v8)(_QWORD); // rax
  HANDLE ProcessHeap; // rax
  LPVOID lpMem[2]; // [rsp+30h] [rbp-10h] BYREF

  fnEfsLogTrace1Strings(a1, (unsigned int)EFS_TRACE_ENTER_EVENT, (unsigned int)&sourceString, 38, 14);
  lpMem[1] = lpMem;
  lpMem[0] = lpMem;
  EnterCriticalSection(&g_ServiceQueue);
  v1 = pwk;
  pwk = 0;
  HIDWORD(qword_180117480) = 1;
  while ( 1 )
  {
    v2 = (LPVOID *)::lpMem;
    if ( ::lpMem == &::lpMem )
      break;
    if ( *((LPVOID **)::lpMem + 1) != &::lpMem
      || (v3 = *(_QWORD *)::lpMem, *(LPVOID *)(*(_QWORD *)::lpMem + 8LL) != ::lpMem)
      || (::lpMem = *(LPVOID *)::lpMem,
          *(_QWORD *)(v3 + 8) = &::lpMem,
          v4 = (LPVOID **)lpMem[1],
          *(LPVOID **)lpMem[1] != lpMem) )
    {
LABEL_14:
      __fastfail(3u);
    }
    v2[1] = lpMem[1];
    *v2 = lpMem;
    *v4 = v2;
    lpMem[1] = v2;
  }
  LeaveCriticalSection(&g_ServiceQueue);
  while ( 1 )
  {
    v6 = lpMem[0];
    if ( lpMem[0] == lpMem )
      break;
    if ( *((LPVOID **)lpMem[0] + 1) != lpMem )
      goto LABEL_14;
    v7 = *(_QWORD *)lpMem[0];
    if ( *(LPVOID *)(*(_QWORD *)lpMem[0] + 8LL) != lpMem[0] )
      goto LABEL_14;
    lpMem[0] = *(LPVOID *)lpMem[0];
    *(_QWORD *)(v7 + 8) = lpMem;
    v8 = (void (__fastcall *)(_QWORD))v6[5];
    if ( v8 )
      v8(v6[4]);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v6);
  }
  if ( v1 )
  {
    WaitForThreadpoolWorkCallbacks(v1, 1);
    CloseThreadpoolWork(v1);
  }
  fnEfsLogTrace1Strings(v5, (unsigned int)EFS_TRACE_LEAVE_EVENT, (unsigned int)&sourceString, 38, 87);
}

```

## disassembly

```asm
0x18008649c  mov     [rsp-8+arg_0], rbx
0x1800864a1  mov     [rsp-8+arg_8], rdi
0x1800864a6  push    rbp
0x1800864a7  mov     rbp, rsp
0x1800864aa  sub     rsp, 40h
0x1800864ae  xorps   xmm0, xmm0
0x1800864b1  mov     [rsp+40h+var_20], 120Eh
0x1800864b9  mov     r9d, 26h ; '&'
0x1800864bf  lea     r8, sourceString
0x1800864c6  lea     rdx, EFS_TRACE_ENTER_EVENT
0x1800864cd  movups  xmmword ptr [rbp+lpMem], xmm0
0x1800864d1  call    fnEfsLogTrace1Strings
0x1800864d6  lea     rax, [rbp+lpMem]
0x1800864da  mov     [rbp+lpMem+8], rax
0x1800864de  lea     rcx, ?g_ServiceQueue@@3U_EDP_CRED_SVC_QUEUE@@A; lpCriticalSection
0x1800864e5  lea     rax, [rbp+lpMem]
0x1800864e9  mov     [rbp+lpMem], rax
0x1800864ed  call    cs:__imp_EnterCriticalSection
0x1800864f3  mov     rdi, cs:pwk
0x1800864fa  lea     r8, lpMem
0x180086501  mov     cs:pwk, 0
0x18008650c  mov     dword ptr cs:qword_180117480+4, 1
0x180086516  mov     rax, cs:lpMem
0x18008651d  cmp     rax, r8
0x180086520  jz      short loc_180086565
0x180086522  cmp     [rax+8], r8
0x180086526  jnz     loc_1800865C6
0x18008652c  mov     rcx, [rax]
0x18008652f  cmp     [rcx+8], rax
0x180086533  jnz     loc_1800865C6
0x180086539  mov     cs:lpMem, rcx
0x180086540  lea     rdx, [rbp+lpMem]
0x180086544  mov     [rcx+8], r8
0x180086548  mov     rcx, [rbp+lpMem+8]
0x18008654c  cmp     [rcx], rdx
0x18008654f  jnz     short loc_1800865C6
0x180086551  mov     [rax+8], rcx
0x180086555  lea     rdx, [rbp+lpMem]
0x180086559  mov     [rax], rdx
0x18008655c  mov     [rcx], rax
0x18008655f  mov     [rbp+lpMem+8], rax
0x180086563  jmp     short loc_180086516
0x180086565  lea     rcx, ?g_ServiceQueue@@3U_EDP_CRED_SVC_QUEUE@@A; lpCriticalSection
0x18008656c  call    cs:__imp_LeaveCriticalSection
0x180086572  mov     rbx, [rbp+lpMem]
0x180086576  lea     rax, [rbp+lpMem]
0x18008657a  cmp     rbx, rax
0x18008657d  jz      short loc_1800865CD
0x18008657f  lea     rax, [rbp+lpMem]
0x180086583  cmp     [rbx+8], rax
0x180086587  jnz     short loc_1800865C6
0x180086589  mov     rax, [rbx]
0x18008658c  cmp     [rax+8], rbx
0x180086590  jnz     short loc_1800865C6
0x180086592  mov     [rbp+lpMem], rax
0x180086596  lea     rcx, [rbp+lpMem]
0x18008659a  mov     [rax+8], rcx
0x18008659e  mov     rax, [rbx+28h]
0x1800865a2  test    rax, rax
0x1800865a5  jz      short loc_1800865B0
0x1800865a7  mov     rcx, [rbx+20h]
0x1800865ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800865b0  call    cs:__imp_GetProcessHeap
0x1800865b6  mov     r8, rbx; lpMem
0x1800865b9  xor     edx, edx; dwFlags
0x1800865bb  mov     rcx, rax; hHeap
0x1800865be  call    cs:__imp_HeapFree
0x1800865c4  jmp     short loc_180086572
0x1800865c6  mov     ecx, 3
0x1800865cb  int     29h; Win8: RtlFailFast(ecx)
0x1800865cd  test    rdi, rdi
0x1800865d0  jz      short loc_1800865E9
0x1800865d2  mov     edx, 1; fCancelPendingCallbacks
0x1800865d7  mov     rcx, rdi; pwk
0x1800865da  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x1800865e0  mov     rcx, rdi; pwk
0x1800865e3  call    cs:__imp_CloseThreadpoolWork
0x1800865e9  mov     r9d, 26h ; '&'
0x1800865ef  mov     [rsp+40h+var_20], 1257h
0x1800865f7  lea     r8, sourceString
0x1800865fe  lea     rdx, EFS_TRACE_LEAVE_EVENT
0x180086605  call    fnEfsLogTrace1Strings
0x18008660a  mov     rbx, [rsp+40h+arg_0]
0x18008660f  mov     rdi, [rsp+40h+arg_8]
0x180086614  add     rsp, 40h
0x180086618  pop     rbp
0x180086619  retn
```
