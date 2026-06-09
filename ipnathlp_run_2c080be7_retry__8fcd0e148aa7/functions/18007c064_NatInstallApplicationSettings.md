# NatInstallApplicationSettings

- ea: `0x18007c064`
- end: `0x18007c351`
- name: `NatInstallApplicationSettings`
- size: `749`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18004b360`
- `0x18007351c`
- `0x180079490`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x18007c064`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007c1c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007c2b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007c1c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007c2b0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007c1d8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007c1d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007c2c4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007c2c4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007c0bf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007c0d2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007c0bf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007c0d2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007c107`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007c11a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007c2ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007c2fd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007c107`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007c11a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007c2ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007c2fd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007c0e8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007c0e8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007c2a4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007c2a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c142`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c142`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007c30c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007c30c`
- `ntdll!NtDeviceIoControlFile` at `0x18007c28b`
- `ntdll!NtDeviceIoControlFile` at `0x18007c28b`

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
0x18007c064  push    rbx
0x18007c066  push    rbp
0x18007c067  push    rsi
0x18007c068  push    rdi
0x18007c069  push    r12
0x18007c06b  push    r14
0x18007c06d  push    r15
0x18007c06f  sub     rsp, 60h
0x18007c073  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c07a  lea     r12, WPP_GLOBAL_Control
0x18007c081  lea     r15, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x18007c088  mov     r14d, 200h
0x18007c08e  cmp     rcx, r12
0x18007c091  jz      short loc_18007C0B0
0x18007c093  test    [rcx+1Ch], r14d
0x18007c097  jz      short loc_18007C0B0
0x18007c099  cmp     byte ptr [rcx+19h], 6
0x18007c09d  jb      short loc_18007C0B0
0x18007c09f  mov     rcx, [rcx+10h]
0x18007c0a3  mov     edx, 67h ; 'g'
0x18007c0a8  mov     r8, r15
0x18007c0ab  call    WPP_SF_
0x18007c0b0  xorps   xmm0, xmm0
0x18007c0b3  lea     rcx, NatInterfaceLock; lpCriticalSection
0x18007c0ba  movups  xmmword ptr [rsp+98h+var_48], xmm0
0x18007c0bf  call    cs:__imp_EnterCriticalSection
0x18007c0c6  nop     dword ptr [rax+rax+00h]
0x18007c0cb  lea     rcx, ?NhLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18007c0d2  call    cs:__imp_EnterCriticalSection
0x18007c0d9  nop     dword ptr [rax+rax+00h]
0x18007c0de  xor     r9d, r9d; lpName
0x18007c0e1  xor     r8d, r8d; bInitialState
0x18007c0e4  xor     edx, edx; bManualReset
0x18007c0e6  xor     ecx, ecx; lpEventAttributes
0x18007c0e8  call    cs:__imp_CreateEventW
0x18007c0ef  nop     dword ptr [rax+rax+00h]
0x18007c0f4  mov     rsi, rax
0x18007c0f7  test    rax, rax
0x18007c0fa  jnz     loc_18007C195
0x18007c100  lea     rcx, ?NhLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18007c107  call    cs:__imp_LeaveCriticalSection
0x18007c10e  nop     dword ptr [rax+rax+00h]
0x18007c113  lea     rcx, NatInterfaceLock; lpCriticalSection
0x18007c11a  call    cs:__imp_LeaveCriticalSection
0x18007c121  nop     dword ptr [rax+rax+00h]
0x18007c126  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c12d  cmp     rcx, r12
0x18007c130  jz      loc_18007C341
0x18007c136  test    [rcx+1Ch], r14d
0x18007c13a  jz      short loc_18007C16E
0x18007c13c  cmp     byte ptr [rcx+19h], 2
0x18007c140  jb      short loc_18007C16E
0x18007c142  call    cs:__imp_GetLastError
0x18007c149  nop     dword ptr [rax+rax+00h]
0x18007c14e  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c155  lea     edx, [rsi+68h]
0x18007c158  mov     r9d, eax
0x18007c15b  mov     r8, r15
0x18007c15e  mov     rcx, [rcx+10h]
0x18007c162  call    WPP_SF_d
0x18007c167  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c16e  cmp     rcx, r12
0x18007c171  jz      loc_18007C341
0x18007c177  test    [rcx+1Ch], r14d
0x18007c17b  jz      loc_18007C341
0x18007c181  cmp     byte ptr [rcx+19h], 6
0x18007c185  jb      loc_18007C341
0x18007c18b  mov     edx, 69h ; 'i'
0x18007c190  jmp     loc_18007C335
0x18007c195  mov     rdi, cs:?NhApplicationSettingsList@@3U_LIST_ENTRY@@A; _LIST_ENTRY NhApplicationSettingsList
0x18007c19c  lea     rax, ?NhApplicationSettingsList@@3U_LIST_ENTRY@@A; _LIST_ENTRY NhApplicationSettingsList
0x18007c1a3  cmp     rdi, rax
0x18007c1a6  jz      loc_18007C2E3
0x18007c1ac  lea     r15, ?NhApplicationSettingsList@@3U_LIST_ENTRY@@A; _LIST_ENTRY NhApplicationSettingsList
0x18007c1b3  movzx   eax, word ptr [rdi+14h]
0x18007c1b7  lea     ecx, [rax+rax*2]
0x18007c1ba  lea     ebp, ds:8[rcx*2]
0x18007c1c1  call    cs:__imp_GetProcessHeap
0x18007c1c8  nop     dword ptr [rax+rax+00h]
0x18007c1cd  mov     r8d, ebp; dwBytes
0x18007c1d0  mov     edx, 8; dwFlags
0x18007c1d5  mov     rcx, rax; hHeap
0x18007c1d8  call    cs:__imp_HeapAlloc
0x18007c1df  nop     dword ptr [rax+rax+00h]
0x18007c1e4  mov     rbx, rax
0x18007c1e7  test    rax, rax
0x18007c1ea  jz      loc_18007C2DC
0x18007c1f0  mov     al, [rdi+10h]
0x18007c1f3  xor     r9d, r9d
0x18007c1f6  mov     [rbx], al
0x18007c1f8  movzx   eax, word ptr [rdi+12h]
0x18007c1fc  mov     [rbx+2], ax
0x18007c200  movzx   eax, word ptr [rdi+14h]
0x18007c204  mov     [rbx+4], eax
0x18007c207  xor     eax, eax
0x18007c209  cmp     ax, [rdi+14h]
0x18007c20d  jnb     short loc_18007C24F
0x18007c20f  mov     rax, [rdi+18h]
0x18007c213  lea     r8, [r9+r9*2]
0x18007c217  mov     cl, [rax+r8*2]
0x18007c21b  mov     [rbx+r8*2+8], cl
0x18007c220  mov     rax, [rdi+18h]
0x18007c224  movzx   ecx, word ptr [rax+r8*2+2]
0x18007c22a  mov     [rbx+r8*2+0Ah], cx
0x18007c230  lea     rcx, [r9+r9*2]
0x18007c234  mov     rax, [rdi+18h]
0x18007c238  inc     r9d
0x18007c23b  movzx   eax, word ptr [rax+r8*2+4]
0x18007c241  mov     [rbx+rcx*2+0Ch], ax
0x18007c246  movzx   eax, word ptr [rdi+14h]
0x18007c24a  cmp     r9d, eax
0x18007c24d  jb      short loc_18007C20F
0x18007c24f  mov     rcx, cs:NatFileHandle; FileHandle
0x18007c256  lea     rax, [rsp+98h+var_48]
0x18007c25b  mov     [rsp+98h+OutputBufferLength], 0; OutputBufferLength
0x18007c263  xor     r9d, r9d; ApcContext
0x18007c266  mov     [rsp+98h+OutputBuffer], 0; OutputBuffer
0x18007c26f  xor     r8d, r8d; ApcRoutine
0x18007c272  mov     [rsp+98h+InputBufferLength], ebp; InputBufferLength
0x18007c276  mov     rdx, rsi; Event
0x18007c279  mov     [rsp+98h+InputBuffer], rbx; InputBuffer
0x18007c27e  mov     [rsp+98h+IoControlCode], 128040h; IoControlCode
0x18007c286  mov     [rsp+98h+IoStatusBlock], rax; IoStatusBlock
0x18007c28b  call    cs:__imp_NtDeviceIoControlFile
0x18007c292  nop     dword ptr [rax+rax+00h]
0x18007c297  cmp     eax, 103h
0x18007c29c  jnz     short loc_18007C2B0
0x18007c29e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18007c2a1  mov     rcx, rsi; hHandle
0x18007c2a4  call    cs:__imp_WaitForSingleObject
0x18007c2ab  nop     dword ptr [rax+rax+00h]
0x18007c2b0  call    cs:__imp_GetProcessHeap
0x18007c2b7  nop     dword ptr [rax+rax+00h]
0x18007c2bc  mov     r8, rbx; lpMem
0x18007c2bf  xor     edx, edx; dwFlags
0x18007c2c1  mov     rcx, rax; hHeap
0x18007c2c4  call    cs:__imp_HeapFree
0x18007c2cb  nop     dword ptr [rax+rax+00h]
0x18007c2d0  mov     rdi, [rdi]
0x18007c2d3  cmp     rdi, r15
0x18007c2d6  jnz     loc_18007C1B3
0x18007c2dc  lea     r15, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x18007c2e3  lea     rcx, ?NhLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18007c2ea  call    cs:__imp_LeaveCriticalSection
0x18007c2f1  nop     dword ptr [rax+rax+00h]
0x18007c2f6  lea     rcx, NatInterfaceLock; lpCriticalSection
0x18007c2fd  call    cs:__imp_LeaveCriticalSection
0x18007c304  nop     dword ptr [rax+rax+00h]
0x18007c309  mov     rcx, rsi; hObject
0x18007c30c  call    cs:__imp_CloseHandle
0x18007c313  nop     dword ptr [rax+rax+00h]
0x18007c318  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c31f  cmp     rcx, r12
0x18007c322  jz      short loc_18007C341
0x18007c324  test    [rcx+1Ch], r14d
0x18007c328  jz      short loc_18007C341
0x18007c32a  cmp     byte ptr [rcx+19h], 6
0x18007c32e  jb      short loc_18007C341
0x18007c330  mov     edx, 6Ah ; 'j'
0x18007c335  mov     rcx, [rcx+10h]
0x18007c339  mov     r8, r15
0x18007c33c  call    WPP_SF_
0x18007c341  add     rsp, 60h
0x18007c345  pop     r15
0x18007c347  pop     r14
0x18007c349  pop     r12
0x18007c34b  pop     rdi
0x18007c34c  pop     rsi
0x18007c34d  pop     rbp
0x18007c34e  pop     rbx
0x18007c34f  retn
```
