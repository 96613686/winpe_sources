# Windows::Compat::Inventory::InventoryWatchdog::ThreadProc(void *)

- ea: `0x180060030`
- end: `0x1800601c4`
- name: `?ThreadProc@InventoryWatchdog@Inventory@Compat@Windows@@CAKPEAX@Z`
- size: `404`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180060030`
- `0x180066c10`
- `0x180116010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800600d2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180060121`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180060148`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800600d2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180060121`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180060148`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800600c2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180060100`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800600c2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180060100`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180060065`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180060065`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006006f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006006f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18006010b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18006010b`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800600e7`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800600e7`

## string_xrefs

- `0x1800600aa`: `Windows::Compat::Inventory::InventoryWatchdog::Watch`
- `0x18006015b`: `Windows::Compat::Inventory::InventoryWatchdog::Watch`
- `0x1800601a1`: `Windows::Compat::Inventory::InventoryWatchdog::Watch`
- `0x18006016e`: `m_threadRunningEvent not initialized [%#x]`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Compat::Inventory::InventoryWatchdog::ThreadProc(RTL_SRWLOCK *Parameter)
{
  PVOID Ptr; // rcx
  DWORD v3; // esi
  DWORD v4; // eax
  void (*v5)(void); // rax
  const char *v6; // r9
  __int64 v7; // r8
  DWORD LastError; // [rsp+20h] [rbp-28h]
  HANDLE Handles[3]; // [rsp+30h] [rbp-18h] BYREF

  if ( !Parameter[5].Ptr )
  {
    v6 = "m_stillAliveEvent not initialized [%#x]";
    v7 = 256;
    goto LABEL_23;
  }
  if ( !Parameter[6].Ptr )
  {
    v6 = "m_shutdownEvent not initialized [%#x]";
    v7 = 262;
    goto LABEL_23;
  }
  Ptr = Parameter[7].Ptr;
  if ( !Ptr )
  {
    v6 = "m_threadRunningEvent not initialized [%#x]";
    v7 = 268;
LABEL_23:
    AslLogCallPrintf(1, "Windows::Compat::Inventory::InventoryWatchdog::Watch", v7, v6, -2147418113);
    return 0;
  }
  if ( SetEvent(Ptr) )
  {
    Handles[0] = Parameter[5].Ptr;
    Handles[1] = Parameter[6].Ptr;
    AslLogCallPrintf(3, "Windows::Compat::Inventory::InventoryWatchdog::Watch", 283, "Starting InventoryWatchdog...");
    while ( 1 )
    {
      do
      {
        AcquireSRWLockExclusive(Parameter + 3);
        v3 = (DWORD)Parameter->Ptr;
        if ( Parameter != (RTL_SRWLOCK *)-24LL )
          ReleaseSRWLockExclusive(Parameter + 3);
        v4 = WaitForMultipleObjects(2u, Handles, 0, v3);
      }
      while ( !v4 );
      if ( v4 != 258 )
        break;
      AcquireSRWLockExclusive(Parameter + 3);
      if ( !IsDebuggerPresent() && v3 >= LODWORD(Parameter->Ptr) )
      {
        v5 = Windows::Compat::Inventory::InventoryWatchdog::DefaultTimeoutAction;
        if ( Parameter[1].Ptr )
          v5 = (void (*)(void))Parameter[1].Ptr;
        v5();
        if ( Parameter != (RTL_SRWLOCK *)-24LL )
          ReleaseSRWLockExclusive(Parameter + 3);
        break;
      }
      if ( Parameter != (RTL_SRWLOCK *)-24LL )
        ReleaseSRWLockExclusive(Parameter + 3);
    }
    AslLogCallPrintf(3, "Windows::Compat::Inventory::InventoryWatchdog::Watch", 343, "Stopping InventoryWatchdog.");
  }
  else
  {
    LastError = GetLastError();
    AslLogCallPrintf(1, "Windows::Compat::Inventory::InventoryWatchdog::Watch", 274, "SetEvent failed [%d]", LastError);
  }
  return 0;
}

```

## disassembly

```asm
0x180060030  mov     [rsp+arg_8], rbx
0x180060035  mov     [rsp+arg_10], rsi
0x18006003a  push    rdi
0x18006003b  sub     rsp, 40h
0x18006003f  mov     rdi, rcx
0x180060042  cmp     qword ptr [rcx+28h], 0
0x180060047  jz      loc_18006018C
0x18006004d  cmp     qword ptr [rcx+30h], 0
0x180060052  jz      loc_18006017D
0x180060058  mov     rcx, [rcx+38h]; hEvent
0x18006005c  test    rcx, rcx
0x18006005f  jz      loc_18006016E
0x180060065  call    cs:__imp_SetEvent
0x18006006b  test    eax, eax
0x18006006d  jnz     short loc_18006008B
0x18006006f  call    cs:__imp_GetLastError
0x180060075  mov     [rsp+48h+var_28], eax
0x180060079  lea     r9, aSeteventFailed; "SetEvent failed [%d]"
0x180060080  mov     r8d, 112h
0x180060086  jmp     loc_1800601A1
0x18006008b  mov     rax, [rdi+28h]
0x18006008f  mov     [rsp+48h+Handles], rax
0x180060094  mov     rax, [rdi+30h]
0x180060098  mov     [rsp+48h+var_10], rax
0x18006009d  lea     r9, aStartingInvent; "Starting InventoryWatchdog..."
0x1800600a4  mov     r8d, 11Bh
0x1800600aa  lea     rdx, aWindowsCompatI_11; "Windows::Compat::Inventory::InventoryWa"...
0x1800600b1  mov     ecx, 3
0x1800600b6  call    AslLogCallPrintf
0x1800600bb  lea     rbx, [rdi+18h]
0x1800600bf  mov     rcx, rbx; SRWLock
0x1800600c2  call    cs:__imp_AcquireSRWLockExclusive
0x1800600c8  mov     esi, [rdi]
0x1800600ca  test    rbx, rbx
0x1800600cd  jz      short loc_1800600D8
0x1800600cf  mov     rcx, rbx; SRWLock
0x1800600d2  call    cs:__imp_ReleaseSRWLockExclusive
0x1800600d8  mov     r9d, esi; dwMilliseconds
0x1800600db  xor     r8d, r8d; bWaitAll
0x1800600de  lea     rdx, [rsp+48h+Handles]; lpHandles
0x1800600e3  lea     ecx, [r8+2]; nCount
0x1800600e7  call    cs:__imp_WaitForMultipleObjects
0x1800600ed  test    eax, eax
0x1800600ef  jz      short loc_1800600BF
0x1800600f1  sub     eax, 1
0x1800600f4  jz      short loc_18006014E
0x1800600f6  cmp     eax, 101h
0x1800600fb  jnz     short loc_18006014E
0x1800600fd  mov     rcx, rbx; SRWLock
0x180060100  call    cs:__imp_AcquireSRWLockExclusive
0x180060106  mov     [rsp+48h+arg_0], rbx
0x18006010b  call    cs:__imp_IsDebuggerPresent
0x180060111  test    eax, eax
0x180060113  jnz     short loc_180060119
0x180060115  cmp     esi, [rdi]
0x180060117  jnb     short loc_180060129
0x180060119  test    rbx, rbx
0x18006011c  jz      short loc_1800600BF
0x18006011e  mov     rcx, rbx; SRWLock
0x180060121  call    cs:__imp_ReleaseSRWLockExclusive
0x180060127  jmp     short loc_1800600BF
0x180060129  lea     rax, ?DefaultTimeoutAction@InventoryWatchdog@Inventory@Compat@Windows@@CAXXZ; Windows::Compat::Inventory::InventoryWatchdog::DefaultTimeoutAction(void)
0x180060130  cmp     qword ptr [rdi+8], 0
0x180060135  cmovnz  rax, [rdi+8]
0x18006013a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006013f  nop
0x180060140  test    rbx, rbx
0x180060143  jz      short loc_18006014E
0x180060145  mov     rcx, rbx; SRWLock
0x180060148  call    cs:__imp_ReleaseSRWLockExclusive
0x18006014e  lea     r9, aStoppingInvent; "Stopping InventoryWatchdog."
0x180060155  mov     r8d, 157h
0x18006015b  lea     rdx, aWindowsCompatI_11; "Windows::Compat::Inventory::InventoryWa"...
0x180060162  mov     ecx, 3
0x180060167  call    AslLogCallPrintf
0x18006016c  jmp     short loc_1800601B2
0x18006016e  lea     r9, aMThreadrunning; "m_threadRunningEvent not initialized [%"...
0x180060175  mov     r8d, 10Ch
0x18006017b  jmp     short loc_180060199
0x18006017d  lea     r9, aMShutdownevent; "m_shutdownEvent not initialized [%#x]"
0x180060184  mov     r8d, 106h
0x18006018a  jmp     short loc_180060199
0x18006018c  lea     r9, aMStillaliveeve; "m_stillAliveEvent not initialized [%#x]"
0x180060193  mov     r8d, 100h
0x180060199  mov     [rsp+48h+var_28], 8000FFFFh
0x1800601a1  lea     rdx, aWindowsCompatI_11; "Windows::Compat::Inventory::InventoryWa"...
0x1800601a8  mov     ecx, 1
0x1800601ad  call    AslLogCallPrintf
0x1800601b2  xor     eax, eax
0x1800601b4  mov     rbx, [rsp+48h+arg_8]
0x1800601b9  mov     rsi, [rsp+48h+arg_10]
0x1800601be  add     rsp, 40h
0x1800601c2  pop     rdi
0x1800601c3  retn
```
