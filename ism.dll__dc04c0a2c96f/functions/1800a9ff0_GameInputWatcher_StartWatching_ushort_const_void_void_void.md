# GameInputWatcher::StartWatching(ushort const *,void *,void (*)(void *))

- ea: `0x1800a9ff0`
- end: `0x1800aa190`
- name: `?StartWatching@GameInputWatcher@@QEAAJPEBGPEAXP6AX1@Z@Z`
- size: `416`
- prototype: `__int64 __fastcall(GameInputWatcher *__hidden this, LPCWSTR lpFileName, void *, void (*)(void *))`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x18006b278`

## callees

- `0x1800a9ff0`
- `0x1800aa198`
- `0x1800f0a90`
- `0x1800f2478`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aa15e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aa15e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800aa006`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800aa006`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800aa066`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800aa066`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800aa17f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800aa17f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800aa049`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800aa049`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800aa154`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800aa154`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800aa02a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800aa02a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800aa0a1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800aa0a1`
- `api-ms-win-core-file-l2-1-0!ReadDirectoryChangesW` at `0x1800aa13f`
- `api-ms-win-core-file-l2-1-0!ReadDirectoryChangesW` at `0x1800aa13f`

## pseudocode

```c
__int64 __fastcall GameInputWatcher::StartWatching(
        GameInputWatcher *this,
        LPCWSTR lpFileName,
        void *a3,
        void (*a4)(void *))
{
  unsigned int v7; // ebx
  PTP_TIMER ThreadpoolTimer; // rax
  PTP_WAIT ThreadpoolWait; // rax
  HANDLE EventW; // rax
  HANDLE FileW; // rax
  void *v12; // rax
  const struct std::nothrow_t *v13; // rdx
  void *v14; // rcx
  void *v15; // rdx
  void *v16; // rcx
  signed int LastError; // eax

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  if ( *((_QWORD *)this + 2) == -1 )
  {
    ThreadpoolTimer = CreateThreadpoolTimer(GameInputWatcher::TimerCallback, this, 0);
    *(_QWORD *)this = ThreadpoolTimer;
    if ( !ThreadpoolTimer )
      goto LABEL_12;
    ThreadpoolWait = CreateThreadpoolWait(GameInputWatcher::WaitCallback, this, 0);
    *((_QWORD *)this + 1) = ThreadpoolWait;
    if ( !ThreadpoolWait )
      goto LABEL_12;
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + 3) = EventW;
    if ( !EventW )
      goto LABEL_12;
    FileW = CreateFileW(lpFileName, 0x80000020, 7u, 0, 3u, 0x42000000u, 0);
    *((_QWORD *)this + 2) = FileW;
    if ( FileW == (HANDLE)-1LL )
      goto LABEL_12;
    *((_QWORD *)this + 4) = 0;
    *((_QWORD *)this + 5) = 0;
    *((_QWORD *)this + 6) = 0;
    *((_QWORD *)this + 7) = *((_QWORD *)this + 3);
    v12 = operator new[](0x1000u, (const struct std::nothrow_t *)&std::nothrow);
    v14 = (void *)*((_QWORD *)this + 8);
    *((_QWORD *)this + 8) = v12;
    if ( v14 )
      operator delete(v14, v13);
    v15 = (void *)*((_QWORD *)this + 8);
    if ( v15
      && (*((_QWORD *)this + 15) = GameInputServerProxy::OnModuleUpdated,
          v16 = (void *)*((_QWORD *)this + 2),
          *((_QWORD *)this + 14) = a3,
          ReadDirectoryChangesW(v16, v15, 0x1000u, 0, 0x59u, 0, (LPOVERLAPPED)this + 1, 0)) )
    {
      SetThreadpoolWait(*((PTP_WAIT *)this + 1), *((HANDLE *)this + 3), 0);
      v7 = 0;
    }
    else
    {
LABEL_12:
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      GameInputWatcher::StopWatching(this);
    }
  }
  else
  {
    v7 = -2147418113;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  return v7;
}

```

## disassembly

```asm
0x1800a9ff0  push    rbx
0x1800a9ff2  push    rbp
0x1800a9ff3  push    rsi
0x1800a9ff4  push    rdi
0x1800a9ff5  sub     rsp, 48h
0x1800a9ff9  mov     rdi, rcx
0x1800a9ffc  mov     rbp, r8
0x1800a9fff  add     rcx, 48h ; 'H'; lpCriticalSection
0x1800aa003  mov     rbx, rdx
0x1800aa006  call    cs:__imp_EnterCriticalSection
0x1800aa00c  cmp     qword ptr [rdi+10h], 0FFFFFFFFFFFFFFFFh
0x1800aa011  jz      short loc_1800AA01D
0x1800aa013  mov     ebx, 8000FFFFh
0x1800aa018  jmp     loc_1800AA17B
0x1800aa01d  xor     r8d, r8d; pcbe
0x1800aa020  lea     rcx, ?TimerCallback@GameInputWatcher@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800aa027  mov     rdx, rdi; pv
0x1800aa02a  call    cs:__imp_CreateThreadpoolTimer
0x1800aa030  mov     [rdi], rax
0x1800aa033  test    rax, rax
0x1800aa036  jz      loc_1800AA15E
0x1800aa03c  xor     r8d, r8d; pcbe
0x1800aa03f  lea     rcx, ?WaitCallback@GameInputWatcher@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1800aa046  mov     rdx, rdi; pv
0x1800aa049  call    cs:__imp_CreateThreadpoolWait
0x1800aa04f  mov     [rdi+8], rax
0x1800aa053  test    rax, rax
0x1800aa056  jz      loc_1800AA15E
0x1800aa05c  xor     r9d, r9d; lpName
0x1800aa05f  xor     r8d, r8d; bInitialState
0x1800aa062  xor     edx, edx; bManualReset
0x1800aa064  xor     ecx, ecx; lpEventAttributes
0x1800aa066  call    cs:__imp_CreateEventW
0x1800aa06c  mov     [rdi+18h], rax
0x1800aa070  test    rax, rax
0x1800aa073  jz      loc_1800AA15E
0x1800aa079  xor     r9d, r9d; lpSecurityAttributes
0x1800aa07c  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x1800aa085  mov     [rsp+68h+dwFlagsAndAttributes], 42000000h; dwFlagsAndAttributes
0x1800aa08d  mov     edx, 80000020h; dwDesiredAccess
0x1800aa092  mov     rcx, rbx; lpFileName
0x1800aa095  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x1800aa09d  lea     r8d, [r9+7]; dwShareMode
0x1800aa0a1  call    cs:__imp_CreateFileW
0x1800aa0a7  mov     [rdi+10h], rax
0x1800aa0ab  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800aa0af  jz      loc_1800AA15E
0x1800aa0b5  mov     qword ptr [rdi+20h], 0
0x1800aa0bd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800aa0c4  mov     qword ptr [rdi+28h], 0
0x1800aa0cc  mov     ebx, 1000h
0x1800aa0d1  mov     qword ptr [rdi+30h], 0
0x1800aa0d9  mov     ecx, ebx; unsigned __int64
0x1800aa0db  mov     rax, [rdi+18h]
0x1800aa0df  mov     [rdi+38h], rax
0x1800aa0e3  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800aa0e8  mov     rcx, [rdi+40h]; void *
0x1800aa0ec  mov     [rdi+40h], rax
0x1800aa0f0  test    rcx, rcx
0x1800aa0f3  jz      short loc_1800AA0FA
0x1800aa0f5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800aa0fa  mov     rdx, [rdi+40h]; lpBuffer
0x1800aa0fe  test    rdx, rdx
0x1800aa101  jz      short loc_1800AA15E
0x1800aa103  mov     [rsp+68h+lpCompletionRoutine], 0; lpCompletionRoutine
0x1800aa10c  lea     rax, [rdi+20h]
0x1800aa110  mov     [rsp+68h+hTemplateFile], rax; lpOverlapped
0x1800aa115  lea     rcx, ?OnModuleUpdated@GameInputServerProxy@@CAXPEAX@Z; GameInputServerProxy::OnModuleUpdated(void *)
0x1800aa11c  mov     [rdi+78h], rcx
0x1800aa120  xor     r9d, r9d; bWatchSubtree
0x1800aa123  mov     rcx, [rdi+10h]; hDirectory
0x1800aa127  mov     r8d, ebx; nBufferLength
0x1800aa12a  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], 0; lpBytesReturned
0x1800aa133  mov     [rsp+68h+dwCreationDisposition], 59h ; 'Y'; dwNotifyFilter
0x1800aa13b  mov     [rdi+70h], rbp
0x1800aa13f  call    cs:__imp_ReadDirectoryChangesW
0x1800aa145  test    eax, eax
0x1800aa147  jz      short loc_1800AA15E
0x1800aa149  mov     rdx, [rdi+18h]; h
0x1800aa14d  xor     r8d, r8d; pftTimeout
0x1800aa150  mov     rcx, [rdi+8]; pwa
0x1800aa154  call    cs:__imp_SetThreadpoolWait
0x1800aa15a  xor     ebx, ebx
0x1800aa15c  jmp     short loc_1800AA17B
0x1800aa15e  call    cs:__imp_GetLastError
0x1800aa164  mov     ebx, eax
0x1800aa166  test    eax, eax
0x1800aa168  jle     short loc_1800AA173
0x1800aa16a  movzx   ebx, ax
0x1800aa16d  or      ebx, 80070000h
0x1800aa173  mov     rcx, rdi; this
0x1800aa176  call    ?StopWatching@GameInputWatcher@@QEAAXXZ; GameInputWatcher::StopWatching(void)
0x1800aa17b  lea     rcx, [rdi+48h]; lpCriticalSection
0x1800aa17f  call    cs:__imp_LeaveCriticalSection
0x1800aa185  mov     eax, ebx
0x1800aa187  add     rsp, 48h
0x1800aa18b  pop     rdi
0x1800aa18c  pop     rsi
0x1800aa18d  pop     rbp
0x1800aa18e  pop     rbx
0x1800aa18f  retn
```
