# CsrpCheckRequestThreads

- ea: `0x180001aa0`
- end: `0x180001b9c`
- name: `CsrpCheckRequestThreads`
- size: `252`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001200`
- `0x1800097f0`

## callees

- `0x180001aa0`
- `0x180001bb0`

## import_xrefs

- `ntdll!NtClose` at `0x180001b5c`
- `ntdll!NtClose` at `0x180001b5c`
- `ntdll!NtResumeThread` at `0x180001b88`
- `ntdll!NtResumeThread` at `0x180001b88`
- `ntdll!RtlCreateUserThread` at `0x180001b17`
- `ntdll!RtlCreateUserThread` at `0x180001b17`
- `ntdll!NtTerminateThread` at `0x180001b4b`
- `ntdll!NtTerminateThread` at `0x180001b4b`

## pseudocode

```c
__int64 __fastcall CsrpCheckRequestThreads(__int64 a1, __int64 a2, void *a3)
{
  __int128 Reserved8; // [rsp+50h] [rbp-18h] BYREF
  HANDLE ThreadHandle; // [rsp+70h] [rbp+8h] BYREF

  if ( _InterlockedExchangeAdd(&CsrpStaticThreadCount, 0xFFFFFFFF) != 1 )
    return 0;
  if ( CsrpDynamicThreadTotal >= (int)CsrMaxApiRequestThreads )
    return 0;
  ThreadHandle = 0;
  LOBYTE(a3) = 1;
  Reserved8 = 0;
  if ( RtlCreateUserThread(
         (PVOID)0xFFFFFFFFFFFFFFFFLL,
         0,
         a3,
         0,
         0,
         0,
         CsrApiRequestThread,
         0,
         &ThreadHandle,
         &Reserved8) < 0 )
    return 0;
  if ( CsrAddStaticServerThread(ThreadHandle, &Reserved8, 16) )
  {
    _InterlockedIncrement(&CsrpStaticThreadCount);
    _InterlockedIncrement(&CsrpDynamicThreadTotal);
    NtResumeThread(ThreadHandle, 0);
    return 0;
  }
  else
  {
    NtTerminateThread(ThreadHandle, -1073741823);
    NtClose(ThreadHandle);
    return 3221225473LL;
  }
}

```

## disassembly

```asm
0x180001aa0  sub     rsp, 68h
0x180001aa4  mov     eax, 0FFFFFFFFh
0x180001aa9  lock xadd cs:CsrpStaticThreadCount, eax
0x180001ab1  cmp     eax, 1
0x180001ab4  jz      short loc_180001ABE
0x180001ab6  xor     eax, eax
0x180001ab8  add     rsp, 68h
0x180001abc  retn
0x180001abe  mov     eax, cs:CsrMaxApiRequestThreads
0x180001ac4  cmp     cs:CsrpDynamicThreadTotal, eax
0x180001aca  jge     short loc_180001AB6
0x180001acc  xor     edx, edx; OutThreadHandle
0x180001ace  lea     rax, [rsp+68h+var_18]
0x180001ad3  mov     [rsp+68h+Reserved8], rax; Reserved8
0x180001ad8  xorps   xmm0, xmm0
0x180001adb  lea     rax, [rsp+68h+ThreadHandle]
0x180001ae0  mov     [rsp+68h+ThreadHandle], rdx
0x180001ae5  mov     [rsp+68h+Reserved7], rax; Reserved7
0x180001aea  xor     r9d, r9d; Reserved2
0x180001aed  mov     [rsp+68h+Reserved6], rdx; Reserved6
0x180001af2  lea     rax, CsrApiRequestThread
0x180001af9  mov     [rsp+68h+Reserved5], rax; Reserved5
0x180001afe  mov     r8b, 1; Reserved1
0x180001b01  mov     [rsp+68h+Reserved4], rdx; Reserved4
0x180001b06  mov     rcx, 0FFFFFFFFFFFFFFFFh; ThreadContext
0x180001b0d  mov     [rsp+68h+Reserved3], rdx; Reserved3
0x180001b12  movups  [rsp+68h+var_18], xmm0
0x180001b17  call    cs:__imp_RtlCreateUserThread
0x180001b1e  nop     dword ptr [rax+rax+00h]
0x180001b23  test    eax, eax
0x180001b25  js      short loc_180001AB6
0x180001b27  mov     rcx, [rsp+68h+ThreadHandle]
0x180001b2c  lea     rdx, [rsp+68h+var_18]
0x180001b31  mov     r8d, 10h
0x180001b37  call    CsrAddStaticServerThread
0x180001b3c  test    rax, rax
0x180001b3f  jnz     short loc_180001B73
0x180001b41  mov     rcx, [rsp+68h+ThreadHandle]; ThreadHandle
0x180001b46  mov     edx, 0C0000001h; ExitStatus
0x180001b4b  call    cs:__imp_NtTerminateThread
0x180001b52  nop     dword ptr [rax+rax+00h]
0x180001b57  mov     rcx, [rsp+68h+ThreadHandle]; Handle
0x180001b5c  call    cs:__imp_NtClose
0x180001b63  nop     dword ptr [rax+rax+00h]
0x180001b68  mov     eax, 0C0000001h
0x180001b6d  add     rsp, 68h
0x180001b71  retn
0x180001b73  lock inc cs:CsrpStaticThreadCount
0x180001b7a  lock inc cs:CsrpDynamicThreadTotal
0x180001b81  mov     rcx, [rsp+68h+ThreadHandle]; ThreadHandle
0x180001b86  xor     edx, edx; SuspendCount
0x180001b88  call    cs:__imp_NtResumeThread
0x180001b8f  nop     dword ptr [rax+rax+00h]
0x180001b94  xor     eax, eax
0x180001b96  add     rsp, 68h
0x180001b9a  retn
```
