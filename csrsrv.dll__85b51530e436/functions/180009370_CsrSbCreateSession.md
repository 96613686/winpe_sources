# CsrSbCreateSession

- ea: `0x180009370`
- end: `0x18000959c`
- name: `CsrSbCreateSession`
- size: `556`
- prototype: `NTSTATUS __fastcall(__int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180009190`

## callees

- `0x180002f60`
- `0x180002fd0`
- `0x180005010`
- `0x180006380`
- `0x1800080b0`
- `0x180009370`
- `0x18000ab80`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180009408`
- `ntdll!RtlFreeHeap` at `0x180009465`
- `ntdll!RtlFreeHeap` at `0x1800094b3`
- `ntdll!RtlFreeHeap` at `0x1800094cb`
- `ntdll!RtlFreeHeap` at `0x180009408`
- `ntdll!RtlFreeHeap` at `0x180009465`
- `ntdll!RtlFreeHeap` at `0x1800094b3`
- `ntdll!RtlFreeHeap` at `0x1800094cb`
- `ntdll!NtResumeThread` at `0x18000955b`
- `ntdll!NtResumeThread` at `0x18000955b`
- `ntdll!RtlEnterCriticalSection` at `0x1800093b3`
- `ntdll!RtlEnterCriticalSection` at `0x1800093b3`
- `ntdll!NtSetInformationProcess` at `0x1800093ea`
- `ntdll!NtSetInformationProcess` at `0x1800093ea`
- `ntdll!NtQueryInformationThread` at `0x180009437`
- `ntdll!NtQueryInformationThread` at `0x180009437`
- `ntdll!RtlLeaveCriticalSection` at `0x18000956d`
- `ntdll!RtlLeaveCriticalSection` at `0x18000956d`

## pseudocode

```c
NTSTATUS __fastcall CsrSbCreateSession(__int64 a1)
{
  void *v1; // rsi
  void *v2; // rbp
  _QWORD *Process; // rdi
  NTSTATUS InformationThread; // esi
  _DWORD *Thread; // rax
  void *v7; // rsi
  NTSTATUS inserted; // ebp
  unsigned __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rax
  _OWORD ThreadInformation[2]; // [rsp+30h] [rbp-48h] BYREF

  v1 = *(void **)(a1 + 64);
  v2 = *(void **)(a1 + 72);
  memset(ThreadInformation, 0, sizeof(ThreadInformation));
  RtlEnterCriticalSection(&CsrProcessStructureLock);
  Process = CsrAllocateProcess();
  if ( !Process )
    goto LABEL_2;
  InformationThread = NtSetInformationProcess(v1, ProcessExceptionPort, &CsrApiPort, 8u);
  if ( InformationThread < 0
    || (InformationThread = NtQueryInformationThread(v2, ThreadTimes, ThreadInformation, 0x20u, 0), InformationThread < 0) )
  {
    RtlFreeHeap(CsrHeap, 0, Process);
    *(_DWORD *)(a1 + 44) = InformationThread;
    return RtlLeaveCriticalSection(&CsrProcessStructureLock);
  }
  Thread = CsrAllocateThread((__int64)Process);
  v7 = Thread;
  if ( !Thread )
  {
    RtlFreeHeap(CsrHeap, 0, Process);
LABEL_2:
    *(_DWORD *)(a1 + 44) = -1073741801;
    return RtlLeaveCriticalSection(&CsrProcessStructureLock);
  }
  *(_QWORD *)Thread = *(_QWORD *)&ThreadInformation[0];
  *(_OWORD *)(Thread + 10) = *(_OWORD *)(a1 + 80);
  *((_QWORD *)Thread + 8) = *(_QWORD *)(a1 + 72);
  Thread[18] = 0;
  inserted = CsrInsertThread((__int64)Process, (__int64)Thread);
  if ( inserted >= 0 )
  {
    Process[6] = CsrAllocateNtSession(*(_DWORD *)(a1 + 48));
    v9 = ((unsigned __int64)Process + 191) & 0xFFFFFFFFFFFFFFF8uLL;
    v10 = 0;
    *(_OWORD *)Process = *(_OWORD *)(a1 + 80);
    Process[10] = *(_QWORD *)(a1 + 64);
    do
    {
      v11 = CsrLoadedServerDll[v10];
      if ( v11 && *(_DWORD *)(v11 + 64) )
      {
        Process[v10 + 17] = v9;
        v9 = (*(unsigned int *)(v11 + 64) + v9 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
      }
      else
      {
        Process[v10 + 17] = 0;
      }
      ++v10;
    }
    while ( v10 != 6 );
    CsrInsertProcess(0, (__int64)Process);
    *(_DWORD *)(a1 + 44) = NtResumeThread(*(HANDLE *)(a1 + 72), 0);
  }
  else
  {
    RtlFreeHeap(CsrHeap, 0, v7);
    RtlFreeHeap(CsrHeap, 0, Process);
    *(_DWORD *)(a1 + 44) = inserted;
  }
  return RtlLeaveCriticalSection(&CsrProcessStructureLock);
}

```

## disassembly

```asm
0x180009370  mov     [rsp+arg_8], rbx
0x180009375  mov     [rsp+arg_10], rbp
0x18000937a  push    rsi
0x18000937b  push    rdi
0x18000937c  push    r15
0x18000937e  sub     rsp, 60h
0x180009382  mov     rax, cs:__security_cookie
0x180009389  xor     rax, rsp
0x18000938c  mov     [rsp+78h+var_28], rax
0x180009391  mov     rsi, [rcx+40h]
0x180009395  lea     r15, CsrProcessStructureLock
0x18000939c  mov     rbp, [rcx+48h]
0x1800093a0  xorps   xmm0, xmm0
0x1800093a3  mov     rbx, rcx
0x1800093a6  mov     rcx, r15; CriticalSection
0x1800093a9  movups  [rsp+78h+ThreadInformation], xmm0
0x1800093ae  movups  [rsp+78h+var_38], xmm0
0x1800093b3  call    cs:__imp_RtlEnterCriticalSection
0x1800093ba  nop     dword ptr [rax+rax+00h]
0x1800093bf  call    CsrAllocateProcess
0x1800093c4  mov     rdi, rax
0x1800093c7  test    rax, rax
0x1800093ca  jnz     short loc_1800093D8
0x1800093cc  mov     dword ptr [rbx+2Ch], 0C0000017h
0x1800093d3  jmp     loc_18000956A
0x1800093d8  mov     edx, 8; ProcessInformationClass
0x1800093dd  lea     r8, CsrApiPort; ProcessInformation
0x1800093e4  mov     r9d, edx; ProcessInformationLength
0x1800093e7  mov     rcx, rsi; ProcessHandle
0x1800093ea  call    cs:__imp_NtSetInformationProcess
0x1800093f1  nop     dword ptr [rax+rax+00h]
0x1800093f6  mov     esi, eax
0x1800093f8  test    eax, eax
0x1800093fa  jns     short loc_18000941C
0x1800093fc  mov     rcx, cs:CsrHeap; HeapHandle
0x180009403  mov     r8, rdi; BaseAddress
0x180009406  xor     edx, edx; Flags
0x180009408  call    cs:__imp_RtlFreeHeap
0x18000940f  nop     dword ptr [rax+rax+00h]
0x180009414  mov     [rbx+2Ch], esi
0x180009417  jmp     loc_18000956A
0x18000941c  mov     r9d, 20h ; ' '; ThreadInformationLength
0x180009422  mov     [rsp+78h+ReturnLength], 0; ReturnLength
0x18000942b  lea     r8, [rsp+78h+ThreadInformation]; ThreadInformation
0x180009430  mov     rcx, rbp; ThreadHandle
0x180009433  lea     edx, [r9-1Fh]; ThreadInformationClass
0x180009437  call    cs:__imp_NtQueryInformationThread
0x18000943e  nop     dword ptr [rax+rax+00h]
0x180009443  mov     esi, eax
0x180009445  test    eax, eax
0x180009447  js      short loc_1800093FC
0x180009449  mov     rcx, rdi
0x18000944c  call    CsrAllocateThread
0x180009451  mov     rsi, rax
0x180009454  test    rax, rax
0x180009457  jnz     short loc_180009476
0x180009459  mov     rcx, cs:CsrHeap; HeapHandle
0x180009460  mov     r8, rdi; BaseAddress
0x180009463  xor     edx, edx; Flags
0x180009465  call    cs:__imp_RtlFreeHeap
0x18000946c  nop     dword ptr [rax+rax+00h]
0x180009471  jmp     loc_1800093CC
0x180009476  mov     rax, qword ptr [rsp+78h+ThreadInformation]
0x18000947b  mov     rdx, rsi
0x18000947e  mov     [rsi], rax
0x180009481  mov     rcx, rdi
0x180009484  movups  xmm0, xmmword ptr [rbx+50h]
0x180009488  movdqu  xmmword ptr [rsi+28h], xmm0
0x18000948d  mov     rax, [rbx+48h]
0x180009491  mov     [rsi+40h], rax
0x180009495  mov     dword ptr [rsi+48h], 0
0x18000949c  call    CsrInsertThread
0x1800094a1  mov     ebp, eax
0x1800094a3  test    eax, eax
0x1800094a5  jns     short loc_1800094DF
0x1800094a7  mov     rcx, cs:CsrHeap; HeapHandle
0x1800094ae  mov     r8, rsi; BaseAddress
0x1800094b1  xor     edx, edx; Flags
0x1800094b3  call    cs:__imp_RtlFreeHeap
0x1800094ba  nop     dword ptr [rax+rax+00h]
0x1800094bf  mov     rcx, cs:CsrHeap; HeapHandle
0x1800094c6  mov     r8, rdi; BaseAddress
0x1800094c9  xor     edx, edx; Flags
0x1800094cb  call    cs:__imp_RtlFreeHeap
0x1800094d2  nop     dword ptr [rax+rax+00h]
0x1800094d7  mov     [rbx+2Ch], ebp
0x1800094da  jmp     loc_18000956A
0x1800094df  mov     ecx, [rbx+30h]
0x1800094e2  call    CsrAllocateNtSession
0x1800094e7  mov     [rdi+30h], rax
0x1800094eb  lea     rdx, [rdi+0BFh]
0x1800094f2  movups  xmm0, xmmword ptr [rbx+50h]
0x1800094f6  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1800094fa  xor     ecx, ecx
0x1800094fc  movdqu  xmmword ptr [rdi], xmm0
0x180009500  mov     rax, [rbx+40h]
0x180009504  mov     [rdi+50h], rax
0x180009508  lea     rax, CsrLoadedServerDll
0x18000950f  mov     rax, [rax+rcx*8]
0x180009513  test    rax, rax
0x180009516  jz      short loc_180009536
0x180009518  cmp     dword ptr [rax+40h], 0
0x18000951c  jz      short loc_180009536
0x18000951e  mov     [rdi+rcx*8+88h], rdx
0x180009526  add     rdx, 7
0x18000952a  mov     eax, [rax+40h]
0x18000952d  add     rdx, rax
0x180009530  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180009534  jmp     short loc_180009542
0x180009536  mov     qword ptr [rdi+rcx*8+88h], 0
0x180009542  inc     rcx
0x180009545  cmp     rcx, 6
0x180009549  jnz     short loc_180009508
0x18000954b  mov     rdx, rdi
0x18000954e  xor     ecx, ecx
0x180009550  call    CsrInsertProcess
0x180009555  mov     rcx, [rbx+48h]; ThreadHandle
0x180009559  xor     edx, edx; SuspendCount
0x18000955b  call    cs:__imp_NtResumeThread
0x180009562  nop     dword ptr [rax+rax+00h]
0x180009567  mov     [rbx+2Ch], eax
0x18000956a  mov     rcx, r15; CriticalSection
0x18000956d  call    cs:__imp_RtlLeaveCriticalSection
0x180009574  nop     dword ptr [rax+rax+00h]
0x180009579  mov     rcx, [rsp+78h+var_28]
0x18000957e  xor     rcx, rsp; StackCookie
0x180009581  call    __security_check_cookie
0x180009586  lea     r11, [rsp+78h+var_18]
0x18000958b  mov     rbx, [r11+28h]
0x18000958f  mov     rbp, [r11+30h]
0x180009593  mov     rsp, r11
0x180009596  pop     r15
0x180009598  pop     rdi
0x180009599  pop     rsi
0x18000959a  retn
```
