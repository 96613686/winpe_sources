# NatCreateDynamicRedirectInstance

- ea: `0x180031c50`
- end: `0x180031e1a`
- name: `NatCreateDynamicRedirectInstance`
- size: `458`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180031a40`
- `0x1800573a0`

## callees

- `0x180031c50`
- `0x180031e20`
- `0x18004bff8`
- `0x18004ed64`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031c6b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031d08`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031dd5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031c6b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031d08`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031dd5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031c7e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031d17`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031c7e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031d17`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031de3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031de3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180031cf5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180031cf5`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x180031d5d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x180031d5d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x180031dc7`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x180031dc7`
- `ntdll!NtDeviceIoControlFile` at `0x180031dba`
- `ntdll!NtDeviceIoControlFile` at `0x180031dba`

## pseudocode

```c
void __fastcall NatCreateDynamicRedirectInstance(LPCRITICAL_SECTION lpCriticalSection)
{
  HANDLE ProcessHeap; // rax
  void *v3; // rax
  ULONG_PTR v4; // rsi
  LPCRITICAL_SECTION *SpinCount; // rcx
  HANDLE EventW; // rax
  HANDLE v7; // rax
  _QWORD *v8; // rax
  HANDLE *v9; // r14
  void *v10; // rcx
  void *v11; // rbx
  HANDLE v12; // rax

  if ( SHIDWORD(lpCriticalSection[1].DebugInfo) >= 0 )
  {
    _InterlockedIncrement((volatile signed __int32 *)&lpCriticalSection[1]);
    ProcessHeap = GetProcessHeap();
    v3 = HeapAlloc(ProcessHeap, 0, 0x50u);
    v4 = (ULONG_PTR)v3;
    if ( v3 )
    {
      memset_0(v3, 0, 0x50u);
      *(_DWORD *)(v4 + 16) = _InterlockedIncrement(&NextRedirectInstanceId);
      SpinCount = (LPCRITICAL_SECTION *)lpCriticalSection[1].SpinCount;
      if ( *SpinCount != (LPCRITICAL_SECTION)&lpCriticalSection[1].LockSemaphore )
        __fastfail(3u);
      *(_QWORD *)(v4 + 8) = SpinCount;
      *(_QWORD *)v4 = (char *)lpCriticalSection + 64;
      *SpinCount = (LPCRITICAL_SECTION)v4;
      lpCriticalSection[1].SpinCount = v4;
      EventW = CreateEventW(0, 0, 0, 0);
      *(_QWORD *)(v4 + 24) = EventW;
      if ( EventW )
      {
        v7 = GetProcessHeap();
        v8 = HeapAlloc(v7, 0, 0x10u);
        *(_QWORD *)(v4 + 40) = v8;
        if ( v8 )
        {
          *v8 = lpCriticalSection;
          v9 = (HANDLE *)(v4 + 32);
          *(_DWORD *)(*(_QWORD *)(v4 + 40) + 8LL) = *(_DWORD *)(v4 + 16);
          if ( RegisterWaitForSingleObject(
                 (PHANDLE)(v4 + 32),
                 *(HANDLE *)(v4 + 24),
                 NatDynamicRedirectNotificationRoutine,
                 *(PVOID *)(v4 + 40),
                 0xFFFFFFFF,
                 9u) )
          {
            v10 = *(void **)&lpCriticalSection[1].LockCount;
            *(_QWORD *)&lpCriticalSection[2].LockCount = *(_QWORD *)(v4 + 24);
            if ( NtDeviceIoControlFile(
                   v10,
                   *(HANDLE *)(v4 + 24),
                   0,
                   0,
                   &UnusedIoStatus,
                   0x128064u,
                   &lpCriticalSection[2],
                   0x40u,
                   UnusedStatistics,
                   0x30u) >= 0 )
              return;
            if ( UnregisterWait(*v9) )
            {
              v11 = *(void **)(v4 + 40);
              v12 = GetProcessHeap();
              HeapFree(v12, 0, v11);
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)&lpCriticalSection[1], 0xFFFFFFFF) == 1 )
                NatCleanupDynamicRedirect(lpCriticalSection);
            }
            *v9 = 0;
          }
        }
      }
      NatDeleteDynamicRedirectInstance(lpCriticalSection);
    }
    else if ( _InterlockedExchangeAdd((volatile signed __int32 *)&lpCriticalSection[1], 0xFFFFFFFF) == 1 )
    {
      NatCleanupDynamicRedirect(lpCriticalSection);
    }
  }
}

```

## disassembly

```asm
0x180031c50  push    rbx
0x180031c52  push    rsi
0x180031c53  push    rdi
0x180031c54  push    r14
0x180031c56  sub     rsp, 58h
0x180031c5a  cmp     dword ptr [rcx+2Ch], 0
0x180031c5e  mov     rdi, rcx
0x180031c61  jl      loc_180031E10
0x180031c67  lock inc dword ptr [rcx+28h]
0x180031c6b  call    cs:__imp_GetProcessHeap
0x180031c71  mov     ebx, 50h ; 'P'
0x180031c76  xor     edx, edx; dwFlags
0x180031c78  mov     rcx, rax; hHeap
0x180031c7b  mov     r8d, ebx; dwBytes
0x180031c7e  call    cs:__imp_HeapAlloc
0x180031c84  mov     rsi, rax
0x180031c87  test    rax, rax
0x180031c8a  jnz     short loc_180031CAA
0x180031c8c  or      eax, 0FFFFFFFFh
0x180031c8f  lock xadd [rdi+28h], eax
0x180031c94  cmp     eax, 1
0x180031c97  jnz     loc_180031E10
0x180031c9d  mov     rcx, rdi; lpCriticalSection
0x180031ca0  call    NatCleanupDynamicRedirect
0x180031ca5  jmp     loc_180031E10
0x180031caa  mov     r8, rbx; Size
0x180031cad  xor     edx, edx; Val
0x180031caf  mov     rcx, rsi; void *
0x180031cb2  call    memset_0
0x180031cb7  mov     eax, 1
0x180031cbc  lock xadd cs:NextRedirectInstanceId, eax
0x180031cc4  inc     eax
0x180031cc6  mov     [rsi+10h], eax
0x180031cc9  lea     rax, [rdi+40h]
0x180031ccd  mov     rcx, [rax+8]
0x180031cd1  cmp     [rcx], rax
0x180031cd4  jz      short loc_180031CDD
0x180031cd6  mov     ecx, 3
0x180031cdb  int     29h; Win8: RtlFailFast(ecx)
0x180031cdd  mov     [rsi+8], rcx
0x180031ce1  xor     r9d, r9d; lpName
0x180031ce4  mov     [rsi], rax
0x180031ce7  xor     r8d, r8d; bInitialState
0x180031cea  mov     [rcx], rsi
0x180031ced  xor     edx, edx; bManualReset
0x180031cef  xor     ecx, ecx; lpEventAttributes
0x180031cf1  mov     [rax+8], rsi
0x180031cf5  call    cs:__imp_CreateEventW
0x180031cfb  mov     [rsi+18h], rax
0x180031cff  test    rax, rax
0x180031d02  jz      loc_180031E05
0x180031d08  call    cs:__imp_GetProcessHeap
0x180031d0e  xor     edx, edx; dwFlags
0x180031d10  mov     rcx, rax; hHeap
0x180031d13  lea     r8d, [rdx+10h]; dwBytes
0x180031d17  call    cs:__imp_HeapAlloc
0x180031d1d  mov     [rsi+28h], rax
0x180031d21  test    rax, rax
0x180031d24  jz      loc_180031E05
0x180031d2a  mov     [rax], rdi
0x180031d2d  lea     r14, [rsi+20h]
0x180031d31  mov     rcx, [rsi+28h]
0x180031d35  lea     r8, NatDynamicRedirectNotificationRoutine; Callback
0x180031d3c  mov     eax, [rsi+10h]
0x180031d3f  mov     [rsp+78h+dwFlags], 9; dwFlags
0x180031d47  mov     [rsp+78h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x180031d4f  mov     [rcx+8], eax
0x180031d52  mov     rcx, r14; phNewWaitObject
0x180031d55  mov     r9, [rsi+28h]; Context
0x180031d59  mov     rdx, [rsi+18h]; hObject
0x180031d5d  call    cs:__imp_RegisterWaitForSingleObject
0x180031d63  test    eax, eax
0x180031d65  jz      loc_180031E05
0x180031d6b  mov     rax, [rsi+18h]
0x180031d6f  lea     rcx, UnusedStatistics
0x180031d76  mov     [rsp+78h+OutputBufferLength], 30h ; '0'; OutputBufferLength
0x180031d7e  xor     r9d, r9d; ApcContext
0x180031d81  mov     [rsp+78h+OutputBuffer], rcx; OutputBuffer
0x180031d86  xor     r8d, r8d; ApcRoutine
0x180031d89  mov     rcx, [rdi+30h]; FileHandle
0x180031d8d  mov     [rdi+58h], rax
0x180031d91  lea     rax, [rdi+50h]
0x180031d95  mov     rdx, [rsi+18h]; Event
0x180031d99  mov     [rsp+78h+InputBufferLength], 40h ; '@'; InputBufferLength
0x180031da1  mov     [rsp+78h+InputBuffer], rax; InputBuffer
0x180031da6  lea     rax, UnusedIoStatus
0x180031dad  mov     [rsp+78h+dwFlags], 128064h; IoControlCode
0x180031db5  mov     qword ptr [rsp+78h+dwMilliseconds], rax; IoStatusBlock
0x180031dba  call    cs:__imp_NtDeviceIoControlFile
0x180031dc0  test    eax, eax
0x180031dc2  jns     short loc_180031E10
0x180031dc4  mov     rcx, [r14]; WaitHandle
0x180031dc7  call    cs:__imp_UnregisterWait
0x180031dcd  test    eax, eax
0x180031dcf  jz      short loc_180031DFE
0x180031dd1  mov     rbx, [rsi+28h]
0x180031dd5  call    cs:__imp_GetProcessHeap
0x180031ddb  mov     r8, rbx; lpMem
0x180031dde  xor     edx, edx; dwFlags
0x180031de0  mov     rcx, rax; hHeap
0x180031de3  call    cs:__imp_HeapFree
0x180031de9  or      eax, 0FFFFFFFFh
0x180031dec  lock xadd [rdi+28h], eax
0x180031df1  cmp     eax, 1
0x180031df4  jnz     short loc_180031DFE
0x180031df6  mov     rcx, rdi; lpCriticalSection
0x180031df9  call    NatCleanupDynamicRedirect
0x180031dfe  mov     qword ptr [r14], 0
0x180031e05  mov     rdx, rsi
0x180031e08  mov     rcx, rdi; lpCriticalSection
0x180031e0b  call    NatDeleteDynamicRedirectInstance
0x180031e10  add     rsp, 58h
0x180031e14  pop     r14
0x180031e16  pop     rdi
0x180031e17  pop     rsi
0x180031e18  pop     rbx
0x180031e19  retn
```
