# SockCheckAndReferenceAsyncThread

- ea: `0x1800028b8`
- end: `0x180002b46`
- name: `SockCheckAndReferenceAsyncThread`
- size: `654`
- prototype: ``
- caller_count: `12`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000203c`
- `0x180002240`
- `0x180004700`
- `0x180012c10`
- `0x1800216a8`
- `0x180023540`
- `0x180023f14`
- `0x180027140`
- `0x1800423ec`
- `0x180042b50`
- `0x1800485dc`
- `0x180049768`

## callees

- `0x1800028b8`
- `0x180004558`
- `0x18000ca20`
- `0x18000db30`
- `0x18001e14c`
- `0x1800239e4`
- `0x180038104`
- `0x180038118`
- `0x18003aec4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800029d4`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800029d4`
- `ntdll!NtCreateEvent` at `0x180002969`
- `ntdll!NtCreateEvent` at `0x180002969`
- `ntdll!NtClose` at `0x1800029ec`
- `ntdll!NtClose` at `0x180002b14`
- `ntdll!NtClose` at `0x1800029ec`
- `ntdll!NtClose` at `0x180002b14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002a4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002ae7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002a4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002ae7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18000292d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18000292d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002a87`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002a87`

## pseudocode

```c
char SockCheckAndReferenceAsyncThread()
{
  int v0; // eax
  __int64 v2; // rdx
  __int64 v3; // r8
  __int64 v4; // r9
  int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  NTSTATUS v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 WinsockThreadData; // rax
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // rdi
  HANDLE v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 v26; // rcx
  char v27; // bl
  DWORD v28; // eax
  __int64 v29; // rcx
  DWORD LastError; // eax
  __int64 v31; // rcx
  DWORD ThreadId; // [rsp+50h] [rbp+20h] BYREF
  HMODULE phModule; // [rsp+58h] [rbp+28h] BYREF
  void *EventHandle; // [rsp+60h] [rbp+30h] BYREF

  ThreadId = 0;
  phModule = 0;
  EventHandle = 0;
  while ( 1 )
  {
    v0 = SockAsyncThreadReferenceCount;
    if ( SockAsyncThreadReferenceCount <= 0 )
      break;
    if ( v0 == _InterlockedCompareExchange(
                 &SockAsyncThreadReferenceCount,
                 SockAsyncThreadReferenceCount + 1,
                 SockAsyncThreadReferenceCount) )
      return 1;
  }
  SockAcquireRwLockExclusive();
  while ( 1 )
  {
    v5 = SockAsyncThreadReferenceCount;
    if ( SockAsyncThreadReferenceCount <= 0 )
      break;
    v26 = (unsigned int)(SockAsyncThreadReferenceCount + 1);
    if ( v5 == _InterlockedCompareExchange(&SockAsyncThreadReferenceCount, v26, SockAsyncThreadReferenceCount) )
      goto LABEL_16;
  }
  if ( !SockAsyncQueuePort && (int)SockCreateAsyncQueuePort() < 0 )
  {
    v27 = 0;
    goto LABEL_17;
  }
  if ( GetModuleHandleExA(4u, (LPCSTR)WSPStartup, &phModule) )
  {
    if ( (xmmword_180063D60 & 2) != 0 )
      WPP_SF_q(1025, 12, WPP_af4e820e49c9345cba0bf06efab8bbeb_Traceguids, NtCurrentTeb());
    v10 = NtCreateEvent(&EventHandle, 0x1F0003u, 0, NotificationEvent, 0);
    if ( v10 < 0 )
    {
      if ( (xmmword_180063D60 & 2) != 0 )
        WPP_SF_l(v12, 13, WPP_af4e820e49c9345cba0bf06efab8bbeb_Traceguids, (unsigned int)v10);
      SockReleaseRwLockExclusive(v12, v11, v13, v14);
    }
    else
    {
      WinsockThreadData = AllocateWinsockThreadData();
      v20 = WinsockThreadData;
      if ( WinsockThreadData )
      {
        *(_QWORD *)(WinsockThreadData + 24) = phModule;
        *(_QWORD *)(WinsockThreadData + 16) = EventHandle;
        *(_DWORD *)(WinsockThreadData + 40) = 0;
        *(_QWORD *)(WinsockThreadData + 48) = 0;
        *(_QWORD *)(WinsockThreadData + 56) = 0;
        v21 = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)SockAsyncThread, (LPVOID)WinsockThreadData, 0, &ThreadId);
        if ( v21 )
        {
          NtClose(v21);
          _InterlockedAdd(&SockAsyncThreadReferenceCount, 2u);
          if ( (xmmword_180063D60 & 2) != 0 )
            WPP_SF_l(v26, 16, WPP_af4e820e49c9345cba0bf06efab8bbeb_Traceguids, ThreadId);
LABEL_16:
          v27 = 1;
LABEL_17:
          SockReleaseRwLockExclusive(v26, v2, v3, v4);
          return v27;
        }
        if ( (xmmword_180063D60 & 2) != 0 )
        {
          LastError = GetLastError();
          WPP_SF_l(v31, 15, WPP_af4e820e49c9345cba0bf06efab8bbeb_Traceguids, LastError);
        }
        SockReleaseRwLockExclusive(v23, v22, v24, v25);
        FreeWinsockThreadData(v20);
      }
      else
      {
        if ( (xmmword_180063D60 & 2) != 0 )
          WPP_SF_(1025, 14, WPP_af4e820e49c9345cba0bf06efab8bbeb_Traceguids);
        SockReleaseRwLockExclusive(v17, v16, v18, v19);
      }
      NtClose(EventHandle);
    }
    FreeLibrary(phModule);
  }
  else
  {
    SockReleaseRwLockExclusive(v7, v6, v8, v9);
    if ( (xmmword_180063D60 & 2) != 0 )
    {
      v28 = GetLastError();
      WPP_SF_l(v29, 11, WPP_af4e820e49c9345cba0bf06efab8bbeb_Traceguids, v28);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800028b8  push    rbp
0x1800028ba  push    rbx
0x1800028bb  push    rdi
0x1800028bc  mov     rbp, rsp
0x1800028bf  sub     rsp, 30h
0x1800028c3  mov     [rbp+ThreadId], 0
0x1800028ca  mov     [rbp+phModule], 0
0x1800028d2  mov     [rbp+EventHandle], 0
0x1800028da  mov     eax, cs:SockAsyncThreadReferenceCount
0x1800028e0  test    eax, eax
0x1800028e2  jle     short loc_1800028FC
0x1800028e4  lea     ecx, [rax+1]
0x1800028e7  lock cmpxchg cs:SockAsyncThreadReferenceCount, ecx
0x1800028ef  jnz     short loc_1800028DA
0x1800028f1  mov     al, 1
0x1800028f3  add     rsp, 30h
0x1800028f7  pop     rdi
0x1800028f8  pop     rbx
0x1800028f9  pop     rbp
0x1800028fa  retn
0x1800028fc  call    SockAcquireRwLockExclusive
0x180002901  mov     eax, cs:SockAsyncThreadReferenceCount
0x180002907  test    eax, eax
0x180002909  jg      loc_180002A1B
0x18000290f  cmp     cs:SockAsyncQueuePort, 0
0x180002917  jz      loc_180002A2D
0x18000291d  lea     r8, [rbp+phModule]; phModule
0x180002921  mov     ecx, 4; dwFlags
0x180002926  lea     rdx, WSPStartup; lpModuleName
0x18000292d  call    cs:__imp_GetModuleHandleExA
0x180002934  nop     dword ptr [rax+rax+00h]
0x180002939  test    eax, eax
0x18000293b  jz      loc_180002A3E
0x180002941  test    byte ptr cs:xmmword_180063D60, 2
0x180002948  lea     rbx, WPP_af4e820e49c9345cba0bf06efab8bbeb_Traceguids
0x18000294f  jnz     loc_180002A9A
0x180002955  xor     r9d, r9d; EventType
0x180002958  mov     [rsp+30h+InitialState], 0; InitialState
0x18000295d  xor     r8d, r8d; ObjectAttributes
0x180002960  lea     rcx, [rbp+EventHandle]; EventHandle
0x180002964  mov     edx, 1F0003h; DesiredAccess
0x180002969  call    cs:__imp_NtCreateEvent
0x180002970  nop     dword ptr [rax+rax+00h]
0x180002975  test    eax, eax
0x180002977  js      loc_180002ABA
0x18000297d  call    AllocateWinsockThreadData
0x180002982  mov     rdi, rax
0x180002985  test    rax, rax
0x180002988  jz      loc_180002AC5
0x18000298e  mov     rax, [rbp+phModule]
0x180002992  lea     r8, SockAsyncThread; lpStartAddress
0x180002999  mov     [rdi+18h], rax
0x18000299d  mov     r9, rdi; lpParameter
0x1800029a0  mov     rax, [rbp+EventHandle]
0x1800029a4  xor     edx, edx; dwStackSize
0x1800029a6  mov     [rdi+10h], rax
0x1800029aa  xor     ecx, ecx; lpThreadAttributes
0x1800029ac  lea     rax, [rbp+ThreadId]
0x1800029b0  mov     dword ptr [rdi+28h], 0
0x1800029b7  mov     [rsp+30h+lpThreadId], rax; lpThreadId
0x1800029bc  mov     dword ptr [rsp+30h+InitialState], 0; dwCreationFlags
0x1800029c4  mov     qword ptr [rdi+30h], 0
0x1800029cc  mov     qword ptr [rdi+38h], 0
0x1800029d4  call    cs:__imp_CreateThread
0x1800029db  nop     dword ptr [rax+rax+00h]
0x1800029e0  test    rax, rax
0x1800029e3  jz      loc_180002B25
0x1800029e9  mov     rcx, rax; Handle
0x1800029ec  call    cs:__imp_NtClose
0x1800029f3  nop     dword ptr [rax+rax+00h]
0x1800029f8  lock add cs:SockAsyncThreadReferenceCount, 2
0x180002a00  test    byte ptr cs:xmmword_180063D60, 2
0x180002a07  jnz     loc_180002B30
0x180002a0d  mov     bl, 1
0x180002a0f  call    SockReleaseRwLockExclusive
0x180002a14  mov     al, bl
0x180002a16  jmp     loc_1800028F3
0x180002a1b  lea     ecx, [rax+1]
0x180002a1e  lock cmpxchg cs:SockAsyncThreadReferenceCount, ecx
0x180002a26  jz      short loc_180002A0D
0x180002a28  jmp     loc_180002901
0x180002a2d  call    SockCreateAsyncQueuePort
0x180002a32  test    eax, eax
0x180002a34  jns     loc_18000291D
0x180002a3a  xor     ebx, ebx
0x180002a3c  jmp     short loc_180002A0F
0x180002a3e  call    SockReleaseRwLockExclusive
0x180002a43  test    byte ptr cs:xmmword_180063D60, 2
0x180002a4a  jz      short loc_180002A93
0x180002a4c  call    cs:__imp_GetLastError
0x180002a53  nop     dword ptr [rax+rax+00h]
0x180002a58  mov     edx, 0Bh
0x180002a5d  lea     r8, WPP_af4e820e49c9345cba0bf06efab8bbeb_Traceguids
0x180002a64  mov     r9d, eax
0x180002a67  call    WPP_SF_l
0x180002a6c  jmp     short loc_180002A93
0x180002a6e  mov     edx, 0Dh
0x180002a73  mov     r9d, eax
0x180002a76  mov     r8, rbx
0x180002a79  call    WPP_SF_l
0x180002a7e  call    SockReleaseRwLockExclusive
0x180002a83  mov     rcx, [rbp+phModule]; hLibModule
0x180002a87  call    cs:__imp_FreeLibrary
0x180002a8e  nop     dword ptr [rax+rax+00h]
0x180002a93  xor     al, al
0x180002a95  jmp     loc_1800028F3
0x180002a9a  mov     r9, gs:30h
0x180002aa3  mov     edx, 0Ch
0x180002aa8  mov     ecx, 401h
0x180002aad  mov     r8, rbx
0x180002ab0  call    WPP_SF_q
0x180002ab5  jmp     loc_180002955
0x180002aba  test    byte ptr cs:xmmword_180063D60, 2
0x180002ac1  jz      short loc_180002A7E
0x180002ac3  jmp     short loc_180002A6E
0x180002ac5  test    byte ptr cs:xmmword_180063D60, 2
0x180002acc  jz      short loc_180002AE0
0x180002ace  mov     edx, 0Eh
0x180002ad3  mov     ecx, 401h
0x180002ad8  mov     r8, rbx
0x180002adb  call    WPP_SF_
0x180002ae0  call    SockReleaseRwLockExclusive
0x180002ae5  jmp     short loc_180002B10
0x180002ae7  call    cs:__imp_GetLastError
0x180002aee  nop     dword ptr [rax+rax+00h]
0x180002af3  mov     edx, 0Fh
0x180002af8  mov     r8, rbx
0x180002afb  mov     r9d, eax
0x180002afe  call    WPP_SF_l
0x180002b03  call    SockReleaseRwLockExclusive
0x180002b08  mov     rcx, rdi
0x180002b0b  call    FreeWinsockThreadData
0x180002b10  mov     rcx, [rbp+EventHandle]; Handle
0x180002b14  call    cs:__imp_NtClose
0x180002b1b  nop     dword ptr [rax+rax+00h]
0x180002b20  jmp     loc_180002A83
0x180002b25  test    byte ptr cs:xmmword_180063D60, 2
0x180002b2c  jz      short loc_180002B03
0x180002b2e  jmp     short loc_180002AE7
0x180002b30  mov     r9d, [rbp+ThreadId]
0x180002b34  mov     edx, 10h
0x180002b39  mov     r8, rbx
0x180002b3c  call    WPP_SF_l
0x180002b41  jmp     loc_180002A0D
```
