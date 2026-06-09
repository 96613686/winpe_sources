# nfsoncrpc_get_next_xid

- ea: `0x14000c290`
- end: `0x14000c3e6`
- name: `nfsoncrpc_get_next_xid`
- size: `342`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000d820`
- `0x14000dcf0`
- `0x14000e320`
- `0x14000e9e4`

## callees

- `0x14000c290`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x14000c2d0`
- `KERNEL32!GetTickCount` at `0x14000c2d0`
- `KERNEL32!GetCurrentProcessId` at `0x14000c2be`
- `KERNEL32!GetCurrentProcessId` at `0x14000c2be`
- `KERNEL32!GetCurrentThreadId` at `0x14000c2c7`
- `KERNEL32!GetCurrentThreadId` at `0x14000c2c7`
- `KERNEL32!Sleep` at `0x14000c3ae`
- `KERNEL32!Sleep` at `0x14000c3ae`
- `KERNEL32!GetSystemTimes` at `0x14000c2f1`
- `KERNEL32!GetSystemTimes` at `0x14000c2f1`
- `ntdll!RtlRandomEx` at `0x14000c2fb`
- `ntdll!RtlRandomEx` at `0x14000c307`
- `ntdll!RtlRandomEx` at `0x14000c313`
- `ntdll!RtlRandomEx` at `0x14000c31f`
- `ntdll!RtlRandomEx` at `0x14000c32c`
- `ntdll!RtlRandomEx` at `0x14000c339`
- `ntdll!RtlRandomEx` at `0x14000c346`
- `ntdll!RtlRandomEx` at `0x14000c353`
- `ntdll!RtlRandomEx` at `0x14000c360`
- `ntdll!RtlRandomEx` at `0x14000c2fb`
- `ntdll!RtlRandomEx` at `0x14000c307`
- `ntdll!RtlRandomEx` at `0x14000c313`
- `ntdll!RtlRandomEx` at `0x14000c31f`
- `ntdll!RtlRandomEx` at `0x14000c32c`
- `ntdll!RtlRandomEx` at `0x14000c339`
- `ntdll!RtlRandomEx` at `0x14000c346`
- `ntdll!RtlRandomEx` at `0x14000c353`
- `ntdll!RtlRandomEx` at `0x14000c360`

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

  if ( _InterlockedCompareExchange(&dword_140021BA0, 0, 0) != 2 )
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
    if ( _InterlockedCompareExchange(&dword_140021BA0, 1, 0) )
    {
      while ( _InterlockedCompareExchange(&dword_140021BA0, 0, 0) != 2 )
        Sleep(1u);
    }
    else
    {
      _InterlockedCompareExchange(&dword_140021B9C, v0 ^ v1 ^ v2 ^ v3 ^ v4 ^ v5 ^ v6 ^ v15 ^ v7, 0);
      _InterlockedCompareExchange(&dword_140021BA0, 2, 1);
    }
  }
  return (unsigned int)_InterlockedIncrement(&dword_140021B9C);
}

```

## disassembly

```asm
0x14000c290  push    rbp
0x14000c292  push    rbx
0x14000c293  push    rsi
0x14000c294  push    rdi
0x14000c295  push    r12
0x14000c297  push    r13
0x14000c299  push    r14
0x14000c29b  push    r15
0x14000c29d  mov     rbp, rsp
0x14000c2a0  sub     rsp, 48h
0x14000c2a4  xor     ebx, ebx
0x14000c2a6  mov     ecx, ebx
0x14000c2a8  xor     eax, eax
0x14000c2aa  lock cmpxchg cs:dword_140021BA0, ecx
0x14000c2b2  lea     edx, [rbx+1]
0x14000c2b5  cmp     eax, 2
0x14000c2b8  jz      loc_14000C3C9
0x14000c2be  call    cs:__imp_GetCurrentProcessId
0x14000c2c4  mov     [rbp+Seed], eax
0x14000c2c7  call    cs:__imp_GetCurrentThreadId
0x14000c2cd  mov     [rbp+arg_8], eax
0x14000c2d0  call    cs:__imp_GetTickCount
0x14000c2d6  lea     r8, [rbp+UserTime]; lpUserTime
0x14000c2da  mov     qword ptr [rbp+IdleTime.dwLowDateTime], rbx
0x14000c2de  lea     rdx, [rbp+KernelTime]; lpKernelTime
0x14000c2e2  mov     [rbp+arg_10], eax
0x14000c2e5  lea     rcx, [rbp+IdleTime]; lpIdleTime
0x14000c2e9  mov     qword ptr [rbp+KernelTime.dwLowDateTime], rbx
0x14000c2ed  mov     qword ptr [rbp+UserTime.dwLowDateTime], rbx
0x14000c2f1  call    cs:__imp_GetSystemTimes
0x14000c2f7  lea     rcx, [rbp+Seed]; Seed
0x14000c2fb  call    cs:__imp_RtlRandomEx
0x14000c301  lea     rcx, [rbp+arg_8]; Seed
0x14000c305  mov     ebx, eax
0x14000c307  call    cs:__imp_RtlRandomEx
0x14000c30d  lea     rcx, [rbp+arg_10]; Seed
0x14000c311  mov     edi, eax
0x14000c313  call    cs:__imp_RtlRandomEx
0x14000c319  lea     rcx, [rbp+IdleTime]; Seed
0x14000c31d  mov     esi, eax
0x14000c31f  call    cs:__imp_RtlRandomEx
0x14000c325  lea     rcx, [rbp+IdleTime.dwHighDateTime]; Seed
0x14000c329  mov     r14d, eax
0x14000c32c  call    cs:__imp_RtlRandomEx
0x14000c332  lea     rcx, [rbp+KernelTime]; Seed
0x14000c336  mov     r15d, eax
0x14000c339  call    cs:__imp_RtlRandomEx
0x14000c33f  lea     rcx, [rbp+KernelTime.dwHighDateTime]; Seed
0x14000c343  mov     r12d, eax
0x14000c346  call    cs:__imp_RtlRandomEx
0x14000c34c  lea     rcx, [rbp+UserTime]; Seed
0x14000c350  mov     r13d, eax
0x14000c353  call    cs:__imp_RtlRandomEx
0x14000c359  lea     rcx, [rbp+UserTime.dwHighDateTime]; Seed
0x14000c35d  mov     [rbp+arg_18], eax
0x14000c360  call    cs:__imp_RtlRandomEx
0x14000c366  mov     ecx, eax
0x14000c368  xor     eax, eax
0x14000c36a  lea     edx, [rax+1]
0x14000c36d  lock cmpxchg cs:dword_140021BA0, edx
0x14000c375  jnz     short loc_14000C3A5
0x14000c377  xor     ecx, [rbp+arg_18]
0x14000c37a  xor     ecx, r13d
0x14000c37d  xor     ecx, r12d
0x14000c380  xor     ecx, r15d
0x14000c383  xor     ecx, r14d
0x14000c386  xor     ecx, esi
0x14000c388  xor     ecx, edi
0x14000c38a  xor     ecx, ebx
0x14000c38c  xor     eax, eax
0x14000c38e  lock cmpxchg cs:dword_140021B9C, ecx
0x14000c396  mov     eax, edx
0x14000c398  lea     ebx, [rdx+1]
0x14000c39b  lock cmpxchg cs:dword_140021BA0, ebx
0x14000c3a3  jmp     short loc_14000C3C9
0x14000c3a5  mov     ebx, 2
0x14000c3aa  jmp     short loc_14000C3B9
0x14000c3ac  mov     ecx, edx; dwMilliseconds
0x14000c3ae  call    cs:__imp_Sleep
0x14000c3b4  mov     edx, 1
0x14000c3b9  xor     eax, eax
0x14000c3bb  xor     ecx, ecx
0x14000c3bd  lock cmpxchg cs:dword_140021BA0, ecx
0x14000c3c5  cmp     eax, ebx
0x14000c3c7  jnz     short loc_14000C3AC
0x14000c3c9  mov     eax, edx
0x14000c3cb  lock xadd cs:dword_140021B9C, eax
0x14000c3d3  add     eax, edx
0x14000c3d5  add     rsp, 48h
0x14000c3d9  pop     r15
0x14000c3db  pop     r14
0x14000c3dd  pop     r13
0x14000c3df  pop     r12
0x14000c3e1  pop     rdi
0x14000c3e2  pop     rsi
0x14000c3e3  pop     rbx
0x14000c3e4  pop     rbp
0x14000c3e5  retn
```
