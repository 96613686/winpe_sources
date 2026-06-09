# nfsoncrpc_get_next_xid

- ea: `0x180030160`
- end: `0x1800302b6`
- name: `nfsoncrpc_get_next_xid`
- size: `342`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002ece0`
- `0x18002f180`
- `0x18002f770`
- `0x18002fe34`

## callees

- `0x180030160`

## import_xrefs

- `ntdll!RtlRandomEx` at `0x1800301cb`
- `ntdll!RtlRandomEx` at `0x1800301d7`
- `ntdll!RtlRandomEx` at `0x1800301e3`
- `ntdll!RtlRandomEx` at `0x1800301ef`
- `ntdll!RtlRandomEx` at `0x1800301fc`
- `ntdll!RtlRandomEx` at `0x180030209`
- `ntdll!RtlRandomEx` at `0x180030216`
- `ntdll!RtlRandomEx` at `0x180030223`
- `ntdll!RtlRandomEx` at `0x180030230`
- `ntdll!RtlRandomEx` at `0x1800301cb`
- `ntdll!RtlRandomEx` at `0x1800301d7`
- `ntdll!RtlRandomEx` at `0x1800301e3`
- `ntdll!RtlRandomEx` at `0x1800301ef`
- `ntdll!RtlRandomEx` at `0x1800301fc`
- `ntdll!RtlRandomEx` at `0x180030209`
- `ntdll!RtlRandomEx` at `0x180030216`
- `ntdll!RtlRandomEx` at `0x180030223`
- `ntdll!RtlRandomEx` at `0x180030230`
- `KERNEL32!GetCurrentThreadId` at `0x180030197`
- `KERNEL32!GetCurrentThreadId` at `0x180030197`
- `KERNEL32!GetCurrentProcessId` at `0x18003018e`
- `KERNEL32!GetCurrentProcessId` at `0x18003018e`
- `KERNEL32!Sleep` at `0x18003027e`
- `KERNEL32!Sleep` at `0x18003027e`
- `KERNEL32!GetTickCount` at `0x1800301a0`
- `KERNEL32!GetTickCount` at `0x1800301a0`
- `KERNEL32!GetSystemTimes` at `0x1800301c1`
- `KERNEL32!GetSystemTimes` at `0x1800301c1`

## pseudocode

```c
__int64 nfsoncrpc_get_next_xid()
{
  ULONG v0; // ebx
  ULONG v1; // edi
  ULONG v2; // esi
  ULONG v3; // r14d
  ULONG v4; // r15d
  ULONG v5; // r12d
  ULONG v6; // r13d
  ULONG v7; // ecx
  struct _FILETIME IdleTime; // [rsp+20h] [rbp-28h] BYREF
  struct _FILETIME KernelTime; // [rsp+28h] [rbp-20h] BYREF
  struct _FILETIME UserTime; // [rsp+30h] [rbp-18h] BYREF
  ULONG Seed; // [rsp+90h] [rbp+48h] BYREF
  ULONG CurrentThreadId; // [rsp+98h] [rbp+50h] BYREF
  ULONG TickCount; // [rsp+A0h] [rbp+58h] BYREF
  ULONG v15; // [rsp+A8h] [rbp+60h]

  if ( _InterlockedCompareExchange(&dword_1800566FC, 0, 0) != 2 )
  {
    Seed = GetCurrentProcessId();
    CurrentThreadId = GetCurrentThreadId();
    IdleTime = 0;
    TickCount = GetTickCount();
    KernelTime = 0;
    UserTime = 0;
    GetSystemTimes(&IdleTime, &KernelTime, &UserTime);
    v0 = RtlRandomEx(&Seed);
    v1 = RtlRandomEx(&CurrentThreadId);
    v2 = RtlRandomEx(&TickCount);
    v3 = RtlRandomEx((PULONG)&IdleTime);
    v4 = RtlRandomEx(&IdleTime.dwHighDateTime);
    v5 = RtlRandomEx((PULONG)&KernelTime);
    v6 = RtlRandomEx(&KernelTime.dwHighDateTime);
    v15 = RtlRandomEx((PULONG)&UserTime);
    v7 = RtlRandomEx(&UserTime.dwHighDateTime);
    if ( _InterlockedCompareExchange(&dword_1800566FC, 1, 0) )
    {
      while ( _InterlockedCompareExchange(&dword_1800566FC, 0, 0) != 2 )
        Sleep(1u);
    }
    else
    {
      _InterlockedCompareExchange(&dword_1800566F8, v0 ^ v1 ^ v2 ^ v3 ^ v4 ^ v5 ^ v6 ^ v15 ^ v7, 0);
      _InterlockedCompareExchange(&dword_1800566FC, 2, 1);
    }
  }
  return (unsigned int)_InterlockedIncrement(&dword_1800566F8);
}

```

## disassembly

```asm
0x180030160  push    rbp
0x180030162  push    rbx
0x180030163  push    rsi
0x180030164  push    rdi
0x180030165  push    r12
0x180030167  push    r13
0x180030169  push    r14
0x18003016b  push    r15
0x18003016d  mov     rbp, rsp
0x180030170  sub     rsp, 48h
0x180030174  xor     ebx, ebx
0x180030176  mov     ecx, ebx
0x180030178  xor     eax, eax
0x18003017a  lock cmpxchg cs:dword_1800566FC, ecx
0x180030182  lea     edx, [rbx+1]
0x180030185  cmp     eax, 2
0x180030188  jz      loc_180030299
0x18003018e  call    cs:__imp_GetCurrentProcessId
0x180030194  mov     [rbp+Seed], eax
0x180030197  call    cs:__imp_GetCurrentThreadId
0x18003019d  mov     [rbp+arg_8], eax
0x1800301a0  call    cs:__imp_GetTickCount
0x1800301a6  lea     r8, [rbp+UserTime]; lpUserTime
0x1800301aa  mov     qword ptr [rbp+IdleTime.dwLowDateTime], rbx
0x1800301ae  lea     rdx, [rbp+KernelTime]; lpKernelTime
0x1800301b2  mov     [rbp+arg_10], eax
0x1800301b5  lea     rcx, [rbp+IdleTime]; lpIdleTime
0x1800301b9  mov     qword ptr [rbp+KernelTime.dwLowDateTime], rbx
0x1800301bd  mov     qword ptr [rbp+UserTime.dwLowDateTime], rbx
0x1800301c1  call    cs:__imp_GetSystemTimes
0x1800301c7  lea     rcx, [rbp+Seed]; Seed
0x1800301cb  call    cs:__imp_RtlRandomEx
0x1800301d1  lea     rcx, [rbp+arg_8]; Seed
0x1800301d5  mov     ebx, eax
0x1800301d7  call    cs:__imp_RtlRandomEx
0x1800301dd  lea     rcx, [rbp+arg_10]; Seed
0x1800301e1  mov     edi, eax
0x1800301e3  call    cs:__imp_RtlRandomEx
0x1800301e9  lea     rcx, [rbp+IdleTime]; Seed
0x1800301ed  mov     esi, eax
0x1800301ef  call    cs:__imp_RtlRandomEx
0x1800301f5  lea     rcx, [rbp+IdleTime.dwHighDateTime]; Seed
0x1800301f9  mov     r14d, eax
0x1800301fc  call    cs:__imp_RtlRandomEx
0x180030202  lea     rcx, [rbp+KernelTime]; Seed
0x180030206  mov     r15d, eax
0x180030209  call    cs:__imp_RtlRandomEx
0x18003020f  lea     rcx, [rbp+KernelTime.dwHighDateTime]; Seed
0x180030213  mov     r12d, eax
0x180030216  call    cs:__imp_RtlRandomEx
0x18003021c  lea     rcx, [rbp+UserTime]; Seed
0x180030220  mov     r13d, eax
0x180030223  call    cs:__imp_RtlRandomEx
0x180030229  lea     rcx, [rbp+UserTime.dwHighDateTime]; Seed
0x18003022d  mov     [rbp+arg_18], eax
0x180030230  call    cs:__imp_RtlRandomEx
0x180030236  mov     ecx, eax
0x180030238  xor     eax, eax
0x18003023a  lea     edx, [rax+1]
0x18003023d  lock cmpxchg cs:dword_1800566FC, edx
0x180030245  jnz     short loc_180030275
0x180030247  xor     ecx, [rbp+arg_18]
0x18003024a  xor     ecx, r13d
0x18003024d  xor     ecx, r12d
0x180030250  xor     ecx, r15d
0x180030253  xor     ecx, r14d
0x180030256  xor     ecx, esi
0x180030258  xor     ecx, edi
0x18003025a  xor     ecx, ebx
0x18003025c  xor     eax, eax
0x18003025e  lock cmpxchg cs:dword_1800566F8, ecx
0x180030266  mov     eax, edx
0x180030268  lea     ebx, [rdx+1]
0x18003026b  lock cmpxchg cs:dword_1800566FC, ebx
0x180030273  jmp     short loc_180030299
0x180030275  mov     ebx, 2
0x18003027a  jmp     short loc_180030289
0x18003027c  mov     ecx, edx; dwMilliseconds
0x18003027e  call    cs:__imp_Sleep
0x180030284  mov     edx, 1
0x180030289  xor     eax, eax
0x18003028b  xor     ecx, ecx
0x18003028d  lock cmpxchg cs:dword_1800566FC, ecx
0x180030295  cmp     eax, ebx
0x180030297  jnz     short loc_18003027C
0x180030299  mov     eax, edx
0x18003029b  lock xadd cs:dword_1800566F8, eax
0x1800302a3  add     eax, edx
0x1800302a5  add     rsp, 48h
0x1800302a9  pop     r15
0x1800302ab  pop     r14
0x1800302ad  pop     r13
0x1800302af  pop     r12
0x1800302b1  pop     rdi
0x1800302b2  pop     rsi
0x1800302b3  pop     rbx
0x1800302b4  pop     rbp
0x1800302b5  retn
```
