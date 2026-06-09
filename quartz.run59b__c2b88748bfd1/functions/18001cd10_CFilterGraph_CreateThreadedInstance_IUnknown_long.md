# CFilterGraph::CreateThreadedInstance(IUnknown *,long *)

- ea: `0x18001cd10`
- end: `0x18001d1ab`
- name: `?CreateThreadedInstance@CFilterGraph@@SAPEAVCUnknown@@PEAUIUnknown@@PEAJ@Z`
- size: `1179`
- prototype: `struct CUnknown *__fastcall(struct IUnknown *, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18001cd10`
- `0x18002f120`
- `0x1800388a0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18001ce51`
- `KERNEL32!FreeLibrary` at `0x18001ce51`
- `KERNEL32!LoadLibraryW` at `0x18001cdfb`
- `KERNEL32!LoadLibraryW` at `0x18001cdfb`
- `KERNEL32!GetCurrentThread` at `0x18001d03b`
- `KERNEL32!GetCurrentThread` at `0x18001d05e`
- `KERNEL32!GetCurrentThread` at `0x18001d0c2`
- `KERNEL32!GetCurrentThread` at `0x18001d03b`
- `KERNEL32!GetCurrentThread` at `0x18001d05e`
- `KERNEL32!GetCurrentThread` at `0x18001d0c2`
- `KERNEL32!GetThreadPriority` at `0x18001d04a`
- `KERNEL32!GetThreadPriority` at `0x18001d04a`
- `KERNEL32!GetTickCount` at `0x18001d018`
- `KERNEL32!GetTickCount` at `0x18001d018`
- `KERNEL32!SetThreadPriority` at `0x18001d072`
- `KERNEL32!SetThreadPriority` at `0x18001d0d4`
- `KERNEL32!SetThreadPriority` at `0x18001d072`
- `KERNEL32!SetThreadPriority` at `0x18001d0d4`
- `KERNEL32!CreateThread` at `0x18001ce36`
- `KERNEL32!CreateThread` at `0x18001ce36`
- `KERNEL32!WaitForSingleObject` at `0x18001ced2`
- `KERNEL32!WaitForSingleObject` at `0x18001ced2`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x18001cf79`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x18001d098`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x18001cf79`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x18001d098`
- `KERNEL32!CreateEventW` at `0x18001cd5b`
- `KERNEL32!CreateEventW` at `0x18001cd5b`
- `KERNEL32!LeaveCriticalSection` at `0x18001ce64`
- `KERNEL32!LeaveCriticalSection` at `0x18001cf40`
- `KERNEL32!LeaveCriticalSection` at `0x18001ce64`
- `KERNEL32!LeaveCriticalSection` at `0x18001cf40`
- `KERNEL32!EnterCriticalSection` at `0x18001cd91`
- `KERNEL32!EnterCriticalSection` at `0x18001cd91`
- `KERNEL32!GetModuleFileNameW` at `0x18001cdc4`
- `KERNEL32!GetModuleFileNameW` at `0x18001cdc4`
- `KERNEL32!GetCurrentThreadId` at `0x18001d166`
- `KERNEL32!GetCurrentThreadId` at `0x18001d166`
- `KERNEL32!CloseHandle` at `0x18001ce9d`
- `KERNEL32!CloseHandle` at `0x18001cee1`
- `KERNEL32!CloseHandle` at `0x18001ce9d`
- `KERNEL32!CloseHandle` at `0x18001cee1`
- `KERNEL32!GetLastError` at `0x18001cdd4`
- `KERNEL32!GetLastError` at `0x18001cdd4`
- `USER32!GetQueueStatus` at `0x18001d0e5`
- `USER32!GetQueueStatus` at `0x18001d0e5`
- `USER32!PeekMessageW` at `0x18001d004`
- `USER32!PeekMessageW` at `0x18001d150`
- `USER32!PeekMessageW` at `0x18001d004`
- `USER32!PeekMessageW` at `0x18001d150`
- `USER32!MsgWaitForMultipleObjects` at `0x18001cfbc`
- `USER32!MsgWaitForMultipleObjects` at `0x18001cfbc`
- `USER32!RegisterWindowMessageW` at `0x18001d10d`
- `USER32!RegisterWindowMessageW` at `0x18001d10d`
- `USER32!PostThreadMessageW` at `0x18001cf0f`
- `USER32!PostThreadMessageW` at `0x18001d17c`
- `USER32!PostThreadMessageW` at `0x18001cf0f`
- `USER32!PostThreadMessageW` at `0x18001d17c`

## pseudocode

```c
struct CUnknown *__fastcall CFilterGraph::CreateThreadedInstance(struct IUnknown *a1, int *a2)
{
  int *v3; // rdi
  int v4; // ebx
  BOOL v5; // ebx
  DWORD v6; // ecx
  signed int LastError; // eax
  bool v8; // sf
  signed int LastErrorToHResult; // eax
  HANDLE Thread; // rbx
  __int64 v11; // rbx
  unsigned int v13; // esi
  int v14; // ebx
  DWORD v15; // r14d
  unsigned int ThreadPriority; // r15d
  DWORD v17; // r12d
  DWORD v18; // eax
  DWORD TickCount; // eax
  HANDLE CurrentThread; // rax
  HANDLE v21; // rax
  HANDLE v22; // rax
  UINT v23; // ebx
  BOOL v24; // eax
  DWORD CurrentThreadId; // eax
  LPVOID lpParameter[2]; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v27; // [rsp+48h] [rbp-C0h]
  __int64 v28; // [rsp+50h] [rbp-B8h]
  HANDLE Handles[2]; // [rsp+58h] [rbp-B0h] BYREF
  _QWORD Msg[8]; // [rsp+68h] [rbp-A0h] BYREF
  WCHAR Filename[1000]; // [rsp+A8h] [rbp-60h] BYREF

  v3 = a2;
  Msg[0] = a2;
  v4 = 0;
  lpParameter[0] = CreateEventW(0, 0, 0, 0);
  if ( !lpParameter[0] )
    v4 = -2147024882;
  LODWORD(v27) = 0;
  v5 = v4 >= 0;
  v28 = 0;
  lpParameter[1] = a1;
  EnterCriticalSection(&g_csObjectThread);
  v6 = g_dwObjectThreadId;
  if ( g_dwObjectThreadId )
  {
    if ( !v5 )
      goto LABEL_16;
    v13 = -1;
    goto LABEL_23;
  }
  if ( !v5 )
    goto LABEL_16;
  if ( !GetModuleFileNameW(g_hInst, Filename, 0x3E8u) )
  {
    LastError = GetLastError();
    v8 = LastError < 0;
    if ( LastError )
    {
      if ( LastError <= 0 )
        goto LABEL_13;
      LastErrorToHResult = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      LastErrorToHResult = -2147467259;
    }
LABEL_12:
    v8 = LastErrorToHResult < 0;
LABEL_13:
    if ( !v8 )
      goto LABEL_14;
LABEL_16:
    LeaveCriticalSection(&g_csObjectThread);
    *v3 = -2147024882;
    goto LABEL_17;
  }
  if ( !LoadLibraryW(Filename) )
  {
    LastErrorToHResult = AmGetLastErrorToHResult();
    goto LABEL_12;
  }
LABEL_14:
  Thread = CreateThread(0, 0, ObjectThread, lpParameter[0], 0, &g_dwObjectThreadId);
  if ( !Thread )
  {
    FreeLibrary(g_hInst);
    goto LABEL_16;
  }
  v13 = -1;
  WaitForSingleObject(lpParameter[0], 0xFFFFFFFF);
  CloseHandle(Thread);
  v6 = g_dwObjectThreadId;
LABEL_23:
  if ( !PostThreadMessageW(v6, 0x400u, (WPARAM)lpParameter, 0) )
    goto LABEL_16;
  ++g_cFGObjects;
  LeaveCriticalSection(&g_csObjectThread);
  Handles[0] = lpParameter[0];
  Handles[1] = 0;
  v14 = 0;
  v15 = 0;
  ThreadPriority = 0;
  if ( WaitForMultipleObjectsEx(1u, Handles, 0, 0, 0) )
  {
    do
    {
      v17 = v13;
      if ( v13 > 0xA )
        v17 = 10;
      v18 = MsgWaitForMultipleObjects(1u, Handles, 0, v17, 0x40u);
      if ( v18 != 1 && (v18 != 258 || v17 == v13) )
        break;
      memset(&Msg[1], 0, 48);
      PeekMessageW((LPMSG)&Msg[1], 0, 0, 0, 0);
      if ( v13 - 1 <= 0xFFFFFFFD )
      {
        TickCount = GetTickCount();
        if ( TickCount - v15 <= v13 )
          v13 -= TickCount - v15;
        else
          v13 = 0;
        v15 = TickCount;
      }
      if ( !v14 )
      {
        CurrentThread = GetCurrentThread();
        ThreadPriority = GetThreadPriority(CurrentThread);
        if ( ThreadPriority < 2 )
        {
          v21 = GetCurrentThread();
          SetThreadPriority(v21, 2);
        }
        v14 = 1;
      }
    }
    while ( WaitForMultipleObjectsEx(1u, Handles, 0, 0, 0) );
    v3 = (int *)Msg[0];
    if ( v14 )
    {
      v22 = GetCurrentThread();
      SetThreadPriority(v22, ThreadPriority);
      if ( (GetQueueStatus(8u) & 0x80000) != 0 )
      {
        v23 = wMsgFilterMax;
        if ( wMsgFilterMax || (wMsgFilterMax = RegisterWindowMessageW(L"AMUnblock"), (v23 = wMsgFilterMax) != 0) )
        {
          memset(&Msg[1], 0, 48);
          do
          {
            v24 = PeekMessageW((LPMSG)&Msg[1], HWND_MESSAGE|0x2LL, v23, v23, 1u);
            v23 = wMsgFilterMax;
          }
          while ( v24 );
        }
        CurrentThreadId = GetCurrentThreadId();
        PostThreadMessageW(CurrentThreadId, v23, 0, 0);
      }
    }
  }
  if ( (int)v27 < 0 )
    *v3 = v27;
LABEL_17:
  v11 = v28;
  if ( lpParameter[0] )
    CloseHandle(lpParameter[0]);
  return (struct CUnknown *)v11;
}

```

## disassembly

```asm
0x18001cd10  mov     r11, rsp
0x18001cd13  push    rbp
0x18001cd14  push    rbx
0x18001cd15  lea     rbp, [r11-7B8h]
0x18001cd1c  sub     rsp, 8A8h
0x18001cd23  mov     rax, cs:__security_cookie
0x18001cd2a  xor     rax, rsp
0x18001cd2d  mov     [rbp+7B0h+var_40], rax
0x18001cd34  mov     [r11+18h], rsi
0x18001cd38  xor     r9d, r9d; lpName
0x18001cd3b  mov     [r11-18h], rdi
0x18001cd3f  mov     rsi, rcx
0x18001cd42  mov     [r11-28h], r13
0x18001cd46  mov     rdi, rdx
0x18001cd49  mov     [rsp+8B0h+Msg], rdx
0x18001cd4e  xor     r13d, r13d
0x18001cd51  xor     r8d, r8d; bInitialState
0x18001cd54  xor     edx, edx; bManualReset
0x18001cd56  xor     ecx, ecx; lpEventAttributes
0x18001cd58  mov     ebx, r13d
0x18001cd5b  call    cs:__imp_CreateEventW
0x18001cd62  nop     dword ptr [rax+rax+00h]
0x18001cd67  mov     [rsp+8B0h+lpParameter], rax
0x18001cd6c  test    rax, rax
0x18001cd6f  jnz     short loc_18001CD76
0x18001cd71  mov     ebx, 8007000Eh
0x18001cd76  not     ebx
0x18001cd78  mov     dword ptr [rsp+8B0h+var_870], r13d
0x18001cd7d  lea     rcx, ?g_csObjectThread@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001cd84  shr     ebx, 1Fh
0x18001cd87  mov     [rsp+8B0h+var_868], r13
0x18001cd8c  mov     qword ptr [rsp+8B0h+var_878], rsi
0x18001cd91  call    cs:__imp_EnterCriticalSection
0x18001cd98  nop     dword ptr [rax+rax+00h]
0x18001cd9d  mov     ecx, cs:?g_dwObjectThreadId@@3KA; idThread
0x18001cda3  test    ecx, ecx
0x18001cda5  jnz     loc_18001CEF5
0x18001cdab  test    ebx, ebx
0x18001cdad  jz      loc_18001CE5D
0x18001cdb3  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hModule
0x18001cdba  lea     rdx, [rbp+7B0h+Filename]; lpFilename
0x18001cdbe  mov     r8d, 3E8h; nSize
0x18001cdc4  call    cs:__imp_GetModuleFileNameW
0x18001cdcb  nop     dword ptr [rax+rax+00h]
0x18001cdd0  test    eax, eax
0x18001cdd2  jnz     short loc_18001CDF7
0x18001cdd4  call    cs:__imp_GetLastError
0x18001cddb  nop     dword ptr [rax+rax+00h]
0x18001cde0  test    eax, eax
0x18001cde2  jz      short loc_18001CDF0
0x18001cde4  jle     short loc_18001CE13
0x18001cde6  movzx   eax, ax
0x18001cde9  or      eax, 80070000h
0x18001cdee  jmp     short loc_18001CE11
0x18001cdf0  mov     eax, 80004005h
0x18001cdf5  jmp     short loc_18001CE11
0x18001cdf7  lea     rcx, [rbp+7B0h+Filename]; lpLibFileName
0x18001cdfb  call    cs:__imp_LoadLibraryW
0x18001ce02  nop     dword ptr [rax+rax+00h]
0x18001ce07  test    rax, rax
0x18001ce0a  jnz     short loc_18001CE15
0x18001ce0c  call    ?AmGetLastErrorToHResult@@YAJXZ; AmGetLastErrorToHResult(void)
0x18001ce11  test    eax, eax
0x18001ce13  js      short loc_18001CE5D
0x18001ce15  mov     r9, [rsp+8B0h+lpParameter]; lpParameter
0x18001ce1a  lea     rax, ?g_dwObjectThreadId@@3KA; ulong g_dwObjectThreadId
0x18001ce21  mov     [rsp+8B0h+lpThreadId], rax; lpThreadId
0x18001ce26  lea     r8, ?ObjectThread@@YAKPEAX@Z; lpStartAddress
0x18001ce2d  xor     edx, edx; dwStackSize
0x18001ce2f  mov     [rsp+8B0h+dwCreationFlags], r13d; dwCreationFlags
0x18001ce34  xor     ecx, ecx; lpThreadAttributes
0x18001ce36  call    cs:__imp_CreateThread
0x18001ce3d  nop     dword ptr [rax+rax+00h]
0x18001ce42  mov     rbx, rax
0x18001ce45  test    rax, rax
0x18001ce48  jnz     short loc_18001CEC6
0x18001ce4a  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hLibModule
0x18001ce51  call    cs:__imp_FreeLibrary
0x18001ce58  nop     dword ptr [rax+rax+00h]
0x18001ce5d  lea     rcx, ?g_csObjectThread@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001ce64  call    cs:__imp_LeaveCriticalSection
0x18001ce6b  nop     dword ptr [rax+rax+00h]
0x18001ce70  mov     dword ptr [rdi], 8007000Eh
0x18001ce76  mov     rcx, [rsp+8B0h+lpParameter]; hObject
0x18001ce7b  mov     rbx, [rsp+8B0h+var_868]
0x18001ce80  mov     r13, [rsp+8B0h+var_20]
0x18001ce88  mov     rdi, [rsp+8A0h]
0x18001ce90  mov     rsi, [rsp+8B0h+arg_10]
0x18001ce98  test    rcx, rcx
0x18001ce9b  jz      short loc_18001CEA9
0x18001ce9d  call    cs:__imp_CloseHandle
0x18001cea4  nop     dword ptr [rax+rax+00h]
0x18001cea9  mov     rax, rbx
0x18001ceac  mov     rcx, [rbp+7B0h+var_40]
0x18001ceb3  xor     rcx, rsp; StackCookie
0x18001ceb6  call    __security_check_cookie
0x18001cebb  add     rsp, 8A8h
0x18001cec2  pop     rbx
0x18001cec3  pop     rbp
0x18001cec4  retn
0x18001cec6  mov     rcx, [rsp+8B0h+lpParameter]; hHandle
0x18001cecb  mov     esi, 0FFFFFFFFh
0x18001ced0  mov     edx, esi; dwMilliseconds
0x18001ced2  call    cs:__imp_WaitForSingleObject
0x18001ced9  nop     dword ptr [rax+rax+00h]
0x18001cede  mov     rcx, rbx; hObject
0x18001cee1  call    cs:__imp_CloseHandle
0x18001cee8  nop     dword ptr [rax+rax+00h]
0x18001ceed  mov     ecx, cs:?g_dwObjectThreadId@@3KA; ulong g_dwObjectThreadId
0x18001cef3  jmp     short loc_18001CF02
0x18001cef5  test    ebx, ebx
0x18001cef7  jz      loc_18001CE5D
0x18001cefd  mov     esi, 0FFFFFFFFh
0x18001cf02  xor     r9d, r9d; lParam
0x18001cf05  lea     r8, [rsp+8B0h+lpParameter]; wParam
0x18001cf0a  mov     edx, 400h; Msg
0x18001cf0f  call    cs:__imp_PostThreadMessageW
0x18001cf16  nop     dword ptr [rax+rax+00h]
0x18001cf1b  test    eax, eax
0x18001cf1d  jz      loc_18001CE5D
0x18001cf23  inc     cs:?g_cFGObjects@@3KA; ulong g_cFGObjects
0x18001cf29  lea     rcx, ?g_csObjectThread@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001cf30  mov     [rsp+8B0h+var_28], r14
0x18001cf38  mov     [rsp+8B0h+var_30], r15
0x18001cf40  call    cs:__imp_LeaveCriticalSection
0x18001cf47  nop     dword ptr [rax+rax+00h]
0x18001cf4c  mov     rax, [rsp+8B0h+lpParameter]
0x18001cf51  lea     rdx, [rsp+8B0h+Handles]; lpHandles
0x18001cf56  xor     r9d, r9d; dwMilliseconds
0x18001cf59  mov     [rsp+8B0h+Handles], rax
0x18001cf5e  xor     r8d, r8d; bWaitAll
0x18001cf61  mov     [rsp+8B0h+var_858], r13
0x18001cf66  mov     ecx, 1; nCount
0x18001cf6b  mov     [rsp+8B0h+dwCreationFlags], r13d; bAlertable
0x18001cf70  mov     ebx, r13d
0x18001cf73  mov     r14d, r13d
0x18001cf76  mov     r15d, r13d
0x18001cf79  call    cs:__imp_WaitForMultipleObjectsEx
0x18001cf80  nop     dword ptr [rax+rax+00h]
0x18001cf85  cmp     eax, 1
0x18001cf88  jb      loc_18001D188
0x18001cf8e  mov     [rsp+8B0h+var_18], r12
0x18001cf96  mov     edi, 0Ah
0x18001cf9b  cmp     esi, edi
0x18001cf9d  mov     [rsp+8B0h+dwCreationFlags], 40h ; '@'; dwWakeMask
0x18001cfa5  mov     r12d, esi
0x18001cfa8  lea     rdx, [rsp+8B0h+Handles]; pHandles
0x18001cfad  cmova   r12d, edi
0x18001cfb1  mov     ecx, 1; nCount
0x18001cfb6  mov     r9d, r12d; dwMilliseconds
0x18001cfb9  xor     r8d, r8d; fWaitAll
0x18001cfbc  call    cs:__imp_MsgWaitForMultipleObjects
0x18001cfc3  nop     dword ptr [rax+rax+00h]
0x18001cfc8  cmp     eax, 1
0x18001cfcb  jz      short loc_18001CFE1
0x18001cfcd  cmp     eax, 102h
0x18001cfd2  jnz     loc_18001D0AD
0x18001cfd8  cmp     r12d, esi
0x18001cfdb  jz      loc_18001D0AD
0x18001cfe1  xorps   xmm0, xmm0
0x18001cfe4  mov     [rsp+8B0h+dwCreationFlags], r13d; wRemoveMsg
0x18001cfe9  xor     r9d, r9d; wMsgFilterMax
0x18001cfec  lea     rcx, [rsp+8B0h+Msg+8]; lpMsg
0x18001cff1  xor     r8d, r8d; wMsgFilterMin
0x18001cff4  xor     edx, edx; hWnd
0x18001cff6  movups  xmmword ptr [rsp+8B0h+Msg+8], xmm0
0x18001cffb  movups  xmmword ptr [rsp+8B0h+Msg+18h], xmm0
0x18001d000  movups  xmmword ptr [rbp+7B0h+Msg+28h], xmm0
0x18001d004  call    cs:__imp_PeekMessageW
0x18001d00b  nop     dword ptr [rax+rax+00h]
0x18001d010  lea     eax, [rsi-1]
0x18001d013  cmp     eax, 0FFFFFFFDh
0x18001d016  ja      short loc_18001D037
0x18001d018  call    cs:__imp_GetTickCount
0x18001d01f  nop     dword ptr [rax+rax+00h]
0x18001d024  mov     ecx, eax
0x18001d026  sub     ecx, r14d
0x18001d029  cmp     ecx, esi
0x18001d02b  jbe     short loc_18001D032
0x18001d02d  mov     esi, r13d
0x18001d030  jmp     short loc_18001D034
0x18001d032  sub     esi, ecx
0x18001d034  mov     r14d, eax
0x18001d037  test    ebx, ebx
0x18001d039  jnz     short loc_18001D083
0x18001d03b  call    cs:__imp_GetCurrentThread
0x18001d042  nop     dword ptr [rax+rax+00h]
0x18001d047  mov     rcx, rax; hThread
0x18001d04a  call    cs:__imp_GetThreadPriority
0x18001d051  nop     dword ptr [rax+rax+00h]
0x18001d056  mov     r15d, eax
0x18001d059  cmp     eax, 2
0x18001d05c  jnb     short loc_18001D07E
0x18001d05e  call    cs:__imp_GetCurrentThread
0x18001d065  nop     dword ptr [rax+rax+00h]
0x18001d06a  mov     rcx, rax; hThread
0x18001d06d  mov     edx, 2; nPriority
0x18001d072  call    cs:__imp_SetThreadPriority
0x18001d079  nop     dword ptr [rax+rax+00h]
0x18001d07e  mov     ebx, 1
0x18001d083  xor     r9d, r9d; dwMilliseconds
0x18001d086  mov     [rsp+8B0h+dwCreationFlags], r13d; bAlertable
0x18001d08b  xor     r8d, r8d; bWaitAll
0x18001d08e  lea     rdx, [rsp+8B0h+Handles]; lpHandles
0x18001d093  mov     ecx, 1; nCount
0x18001d098  call    cs:__imp_WaitForMultipleObjectsEx
0x18001d09f  nop     dword ptr [rax+rax+00h]
0x18001d0a4  cmp     eax, 1
0x18001d0a7  jnb     loc_18001CF9B
0x18001d0ad  mov     r12, [rsp+8B0h+var_18]
0x18001d0b5  mov     rdi, [rsp+8B0h+Msg]
0x18001d0ba  test    ebx, ebx
0x18001d0bc  jz      loc_18001D188
0x18001d0c2  call    cs:__imp_GetCurrentThread
0x18001d0c9  nop     dword ptr [rax+rax+00h]
0x18001d0ce  mov     rcx, rax; hThread
0x18001d0d1  mov     edx, r15d; nPriority
0x18001d0d4  call    cs:__imp_SetThreadPriority
0x18001d0db  nop     dword ptr [rax+rax+00h]
0x18001d0e0  mov     ecx, 8; flags
0x18001d0e5  call    cs:__imp_GetQueueStatus
0x18001d0ec  nop     dword ptr [rax+rax+00h]
0x18001d0f1  shr     eax, 10h
0x18001d0f4  test    al, 8
0x18001d0f6  jz      loc_18001D188
0x18001d0fc  mov     ebx, cs:wMsgFilterMax
0x18001d102  test    ebx, ebx
0x18001d104  jnz     short loc_18001D125
0x18001d106  lea     rcx, String; "AMUnblock"
0x18001d10d  call    cs:__imp_RegisterWindowMessageW
0x18001d114  nop     dword ptr [rax+rax+00h]
0x18001d119  mov     cs:wMsgFilterMax, eax
0x18001d11f  mov     ebx, eax
0x18001d121  test    eax, eax
0x18001d123  jz      short loc_18001D166
0x18001d125  xorps   xmm0, xmm0
0x18001d128  movups  xmmword ptr [rsp+8B0h+Msg+8], xmm0
0x18001d12d  movups  xmmword ptr [rsp+8B0h+Msg+18h], xmm0
0x18001d132  movups  xmmword ptr [rbp+7B0h+Msg+28h], xmm0
0x18001d136  mov     r9d, ebx; wMsgFilterMax
0x18001d139  mov     [rsp+8B0h+dwCreationFlags], 1; wRemoveMsg
0x18001d141  mov     r8d, ebx; wMsgFilterMin
0x18001d144  lea     rcx, [rsp+8B0h+Msg+8]; lpMsg
0x18001d149  mov     rdx, 0FFFFFFFFFFFFFFFFh; hWnd
0x18001d150  call    cs:__imp_PeekMessageW
0x18001d157  nop     dword ptr [rax+rax+00h]
0x18001d15c  mov     ebx, cs:wMsgFilterMax
0x18001d162  test    eax, eax
0x18001d164  jnz     short loc_18001D136
0x18001d166  call    cs:__imp_GetCurrentThreadId
0x18001d16d  nop     dword ptr [rax+rax+00h]
0x18001d172  xor     r9d, r9d; lParam
0x18001d175  xor     r8d, r8d; wParam
0x18001d178  mov     ecx, eax; idThread
0x18001d17a  mov     edx, ebx; Msg
0x18001d17c  call    cs:__imp_PostThreadMessageW
0x18001d183  nop     dword ptr [rax+rax+00h]
0x18001d188  mov     eax, dword ptr [rsp+8B0h+var_870]
0x18001d18c  mov     r15, [rsp+8B0h+var_30]
0x18001d194  mov     r14, [rsp+8B0h+var_28]
0x18001d19c  test    eax, eax
0x18001d19e  jns     loc_18001CE76
0x18001d1a4  mov     [rdi], eax
0x18001d1a6  jmp     loc_18001CE76
```
