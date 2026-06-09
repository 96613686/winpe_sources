# NatInstallApplicationSettings

- ea: `0x18007621c`
- end: `0x1800764ae`
- name: `NatInstallApplicationSettings`
- size: `658`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180047810`
- `0x18006dd7c`
- `0x180073920`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x18007621c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180076355`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007642c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180076355`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007642c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180076366`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180076366`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007643a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007643a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180076277`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180076284`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180076277`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180076284`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800762ad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800762ba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007645a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180076467`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800762ad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800762ba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007645a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180076467`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180076294`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180076294`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180076426`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180076426`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800762dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800762dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180076470`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180076470`
- `ntdll!NtDeviceIoControlFile` at `0x180076413`
- `ntdll!NtDeviceIoControlFile` at `0x180076413`

## pseudocode

```c
void NatInstallApplicationSettings()
{
  HANDLE EventW; // rsi
  PVOID *v1; // rcx
  DWORD LastError; // eax
  __int64 v3; // rdx
  LPVOID *v4; // rdi
  ULONG InputBufferLength; // ebp
  HANDLE ProcessHeap; // rax
  _BYTE *InputBuffer; // rax
  void *v8; // rbx
  __int64 v9; // r9
  __int64 v10; // r8
  __int64 v11; // rcx
  HANDLE v12; // rax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-48h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids);
  }
  IoStatusBlock = 0;
  EnterCriticalSection(&NatInterfaceLock);
  EnterCriticalSection(&NhLock);
  EventW = CreateEventW(0, 0, 0, 0);
  if ( EventW )
  {
    v4 = (LPVOID *)NhApplicationSettingsList;
    if ( NhApplicationSettingsList != &NhApplicationSettingsList )
    {
      do
      {
        InputBufferLength = 6 * *((unsigned __int16 *)v4 + 10) + 8;
        ProcessHeap = GetProcessHeap();
        InputBuffer = HeapAlloc(ProcessHeap, 8u, InputBufferLength);
        v8 = InputBuffer;
        if ( !InputBuffer )
          break;
        v9 = 0;
        *InputBuffer = *((_BYTE *)v4 + 16);
        *((_WORD *)InputBuffer + 1) = *((_WORD *)v4 + 9);
        for ( *((_DWORD *)InputBuffer + 1) = *((unsigned __int16 *)v4 + 10);
              (unsigned int)v9 < *((unsigned __int16 *)v4 + 10);
              *(_WORD *)&InputBuffer[2 * v11 + 12] = *((_WORD *)v4[3] + v10 + 2) )
        {
          v10 = 3 * v9;
          InputBuffer[2 * v10 + 8] = *((_BYTE *)v4[3] + 6 * v9);
          *(_WORD *)&InputBuffer[2 * v10 + 10] = *((_WORD *)v4[3] + 3 * v9 + 1);
          v11 = 3 * v9;
          v9 = (unsigned int)(v9 + 1);
        }
        if ( NtDeviceIoControlFile(
               NatFileHandle,
               EventW,
               0,
               0,
               &IoStatusBlock,
               0x128040u,
               InputBuffer,
               InputBufferLength,
               0,
               0) == 259 )
          WaitForSingleObject(EventW, 0xFFFFFFFF);
        v12 = GetProcessHeap();
        HeapFree(v12, 0, v8);
        v4 = (LPVOID *)*v4;
      }
      while ( v4 != &NhApplicationSettingsList );
    }
    LeaveCriticalSection(&NhLock);
    LeaveCriticalSection(&NatInterfaceLock);
    CloseHandle(EventW);
    v1 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      v3 = 106;
      goto LABEL_25;
    }
  }
  else
  {
    LeaveCriticalSection(&NhLock);
    LeaveCriticalSection(&NatInterfaceLock);
    v1 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids, LastError);
        v1 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v1 != &WPP_GLOBAL_Control && (*((_DWORD *)v1 + 7) & 0x200) != 0 && *((_BYTE *)v1 + 25) >= 6u )
      {
        v3 = 105;
LABEL_25:
        WPP_SF_(v1[2], v3, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids);
      }
    }
  }
}

```

## disassembly

```asm
0x18007621c  push    rbx
0x18007621e  push    rbp
0x18007621f  push    rsi
0x180076220  push    rdi
0x180076221  push    r12
0x180076223  push    r14
0x180076225  push    r15
0x180076227  sub     rsp, 60h
0x18007622b  mov     rcx, cs:WPP_GLOBAL_Control
0x180076232  lea     r12, WPP_GLOBAL_Control
0x180076239  lea     r15, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x180076240  mov     r14d, 200h
0x180076246  cmp     rcx, r12
0x180076249  jz      short loc_180076268
0x18007624b  test    [rcx+1Ch], r14d
0x18007624f  jz      short loc_180076268
0x180076251  cmp     byte ptr [rcx+19h], 6
0x180076255  jb      short loc_180076268
0x180076257  mov     rcx, [rcx+10h]
0x18007625b  mov     edx, 67h ; 'g'
0x180076260  mov     r8, r15
0x180076263  call    WPP_SF_
0x180076268  xorps   xmm0, xmm0
0x18007626b  lea     rcx, NatInterfaceLock; lpCriticalSection
0x180076272  movups  xmmword ptr [rsp+98h+var_48], xmm0
0x180076277  call    cs:__imp_EnterCriticalSection
0x18007627d  lea     rcx, ?NhLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180076284  call    cs:__imp_EnterCriticalSection
0x18007628a  xor     r9d, r9d; lpName
0x18007628d  xor     r8d, r8d; bInitialState
0x180076290  xor     edx, edx; bManualReset
0x180076292  xor     ecx, ecx; lpEventAttributes
0x180076294  call    cs:__imp_CreateEventW
0x18007629a  mov     rsi, rax
0x18007629d  test    rax, rax
0x1800762a0  jnz     loc_180076329
0x1800762a6  lea     rcx, ?NhLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800762ad  call    cs:__imp_LeaveCriticalSection
0x1800762b3  lea     rcx, NatInterfaceLock; lpCriticalSection
0x1800762ba  call    cs:__imp_LeaveCriticalSection
0x1800762c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800762c7  cmp     rcx, r12
0x1800762ca  jz      loc_18007649F
0x1800762d0  test    [rcx+1Ch], r14d
0x1800762d4  jz      short loc_180076302
0x1800762d6  cmp     byte ptr [rcx+19h], 2
0x1800762da  jb      short loc_180076302
0x1800762dc  call    cs:__imp_GetLastError
0x1800762e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800762e9  lea     edx, [rsi+68h]
0x1800762ec  mov     r9d, eax
0x1800762ef  mov     r8, r15
0x1800762f2  mov     rcx, [rcx+10h]
0x1800762f6  call    WPP_SF_d
0x1800762fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180076302  cmp     rcx, r12
0x180076305  jz      loc_18007649F
0x18007630b  test    [rcx+1Ch], r14d
0x18007630f  jz      loc_18007649F
0x180076315  cmp     byte ptr [rcx+19h], 6
0x180076319  jb      loc_18007649F
0x18007631f  mov     edx, 69h ; 'i'
0x180076324  jmp     loc_180076493
0x180076329  mov     rdi, cs:?NhApplicationSettingsList@@3U_LIST_ENTRY@@A; _LIST_ENTRY NhApplicationSettingsList
0x180076330  lea     rax, ?NhApplicationSettingsList@@3U_LIST_ENTRY@@A; _LIST_ENTRY NhApplicationSettingsList
0x180076337  cmp     rdi, rax
0x18007633a  jz      loc_180076453
0x180076340  lea     r15, ?NhApplicationSettingsList@@3U_LIST_ENTRY@@A; _LIST_ENTRY NhApplicationSettingsList
0x180076347  movzx   eax, word ptr [rdi+14h]
0x18007634b  lea     ecx, [rax+rax*2]
0x18007634e  lea     ebp, ds:8[rcx*2]
0x180076355  call    cs:__imp_GetProcessHeap
0x18007635b  mov     r8d, ebp; dwBytes
0x18007635e  mov     edx, 8; dwFlags
0x180076363  mov     rcx, rax; hHeap
0x180076366  call    cs:__imp_HeapAlloc
0x18007636c  mov     rbx, rax
0x18007636f  test    rax, rax
0x180076372  jz      loc_18007644C
0x180076378  mov     al, [rdi+10h]
0x18007637b  xor     r9d, r9d
0x18007637e  mov     [rbx], al
0x180076380  movzx   eax, word ptr [rdi+12h]
0x180076384  mov     [rbx+2], ax
0x180076388  movzx   eax, word ptr [rdi+14h]
0x18007638c  mov     [rbx+4], eax
0x18007638f  xor     eax, eax
0x180076391  cmp     ax, [rdi+14h]
0x180076395  jnb     short loc_1800763D7
0x180076397  mov     rax, [rdi+18h]
0x18007639b  lea     r8, [r9+r9*2]
0x18007639f  mov     cl, [rax+r8*2]
0x1800763a3  mov     [rbx+r8*2+8], cl
0x1800763a8  mov     rax, [rdi+18h]
0x1800763ac  movzx   ecx, word ptr [rax+r8*2+2]
0x1800763b2  mov     [rbx+r8*2+0Ah], cx
0x1800763b8  lea     rcx, [r9+r9*2]
0x1800763bc  mov     rax, [rdi+18h]
0x1800763c0  inc     r9d
0x1800763c3  movzx   eax, word ptr [rax+r8*2+4]
0x1800763c9  mov     [rbx+rcx*2+0Ch], ax
0x1800763ce  movzx   eax, word ptr [rdi+14h]
0x1800763d2  cmp     r9d, eax
0x1800763d5  jb      short loc_180076397
0x1800763d7  mov     rcx, cs:NatFileHandle; FileHandle
0x1800763de  lea     rax, [rsp+98h+var_48]
0x1800763e3  mov     [rsp+98h+OutputBufferLength], 0; OutputBufferLength
0x1800763eb  xor     r9d, r9d; ApcContext
0x1800763ee  mov     [rsp+98h+OutputBuffer], 0; OutputBuffer
0x1800763f7  xor     r8d, r8d; ApcRoutine
0x1800763fa  mov     [rsp+98h+InputBufferLength], ebp; InputBufferLength
0x1800763fe  mov     rdx, rsi; Event
0x180076401  mov     [rsp+98h+InputBuffer], rbx; InputBuffer
0x180076406  mov     [rsp+98h+IoControlCode], 128040h; IoControlCode
0x18007640e  mov     [rsp+98h+IoStatusBlock], rax; IoStatusBlock
0x180076413  call    cs:__imp_NtDeviceIoControlFile
0x180076419  cmp     eax, 103h
0x18007641e  jnz     short loc_18007642C
0x180076420  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180076423  mov     rcx, rsi; hHandle
0x180076426  call    cs:__imp_WaitForSingleObject
0x18007642c  call    cs:__imp_GetProcessHeap
0x180076432  mov     r8, rbx; lpMem
0x180076435  xor     edx, edx; dwFlags
0x180076437  mov     rcx, rax; hHeap
0x18007643a  call    cs:__imp_HeapFree
0x180076440  mov     rdi, [rdi]
0x180076443  cmp     rdi, r15
0x180076446  jnz     loc_180076347
0x18007644c  lea     r15, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x180076453  lea     rcx, ?NhLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18007645a  call    cs:__imp_LeaveCriticalSection
0x180076460  lea     rcx, NatInterfaceLock; lpCriticalSection
0x180076467  call    cs:__imp_LeaveCriticalSection
0x18007646d  mov     rcx, rsi; hObject
0x180076470  call    cs:__imp_CloseHandle
0x180076476  mov     rcx, cs:WPP_GLOBAL_Control
0x18007647d  cmp     rcx, r12
0x180076480  jz      short loc_18007649F
0x180076482  test    [rcx+1Ch], r14d
0x180076486  jz      short loc_18007649F
0x180076488  cmp     byte ptr [rcx+19h], 6
0x18007648c  jb      short loc_18007649F
0x18007648e  mov     edx, 6Ah ; 'j'
0x180076493  mov     rcx, [rcx+10h]
0x180076497  mov     r8, r15
0x18007649a  call    WPP_SF_
0x18007649f  add     rsp, 60h
0x1800764a3  pop     r15
0x1800764a5  pop     r14
0x1800764a7  pop     r12
0x1800764a9  pop     rdi
0x1800764aa  pop     rsi
0x1800764ab  pop     rbp
0x1800764ac  pop     rbx
0x1800764ad  retn
```
