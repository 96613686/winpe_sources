# FREB_LOG_FILE_MANAGER::Initialize(void)

- ea: `0x180008424`
- end: `0x180008540`
- name: `?Initialize@FREB_LOG_FILE_MANAGER@@SAJXZ`
- size: `284`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180003130`

## callees

- `0x180001008`
- `0x180001048`
- `0x180008424`
- `0x18000a934`
- `0x18000aad4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800084c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800084c4`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800084af`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800084af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008521`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008521`

## pseudocode

```c
__int64 FREB_LOG_FILE_MANAGER::Initialize(void)
{
  int v0; // edi
  _QWORD *v1; // rax
  LOSSY_QUEUE *v2; // rcx
  int v3; // ebx
  signed int LastError; // eax

  FREB_LOG_FILE_MANAGER::sm_dwThrottle = 10;
  v0 = 0;
  FREB_LOG_FILE_MANAGER::sm_pLossyQueue = 0;
  FREB_LOG_FILE_MANAGER::sm_fShutdown = 0;
  FREB_LOG_FILE_MANAGER::sm_hWriterThread = 0;
  FREB_LOG_FILE_MANAGER::sm_lScavengesSinceStartup = 0;
  v1 = operator new(0x68u);
  if ( !v1 )
  {
    FREB_LOG_FILE_MANAGER::sm_pLossyQueue = 0;
    v3 = -2147024888;
LABEL_9:
    if ( FREB_LOG_FILE_MANAGER::sm_pLossyQueue )
    {
      if ( v0 )
        LOSSY_QUEUE::Terminate(v2);
      if ( FREB_LOG_FILE_MANAGER::sm_pLossyQueue )
        operator delete(FREB_LOG_FILE_MANAGER::sm_pLossyQueue);
      FREB_LOG_FILE_MANAGER::sm_pLossyQueue = 0;
    }
    if ( FREB_LOG_FILE_MANAGER::sm_hWriterThread )
    {
      CloseHandle(FREB_LOG_FILE_MANAGER::sm_hWriterThread);
      FREB_LOG_FILE_MANAGER::sm_hWriterThread = 0;
    }
    return (unsigned int)v3;
  }
  *(_DWORD *)v1 = 0;
  v1[1] = 0;
  v1[2] = 0;
  v1[3] = 0;
  v1[9] = 0;
  v1[10] = 0;
  v1[11] = 0;
  v1[12] = 0;
  FREB_LOG_FILE_MANAGER::sm_pLossyQueue = v1;
  v3 = LOSSY_QUEUE::Initialize(v2);
  if ( v3 < 0 )
    goto LABEL_9;
  FREB_LOG_FILE_MANAGER::sm_hWriterThread = CreateThread(
                                              0,
                                              0,
                                              (LPTHREAD_START_ROUTINE)FREB_LOG_FILE_MANAGER::WriterThread,
                                              0,
                                              0,
                                              0);
  if ( !FREB_LOG_FILE_MANAGER::sm_hWriterThread )
  {
    v0 = 1;
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( v3 < 0 )
      goto LABEL_9;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180008424  mov     [rsp+arg_0], rbx
0x180008429  mov     [rsp+arg_8], rsi
0x18000842e  push    rdi
0x18000842f  sub     rsp, 30h
0x180008433  xor     esi, esi
0x180008435  mov     cs:?sm_dwThrottle@FREB_LOG_FILE_MANAGER@@0KA, 0Ah; ulong FREB_LOG_FILE_MANAGER::sm_dwThrottle
0x18000843f  mov     edi, esi
0x180008441  mov     cs:?sm_pLossyQueue@FREB_LOG_FILE_MANAGER@@0PEAVLOSSY_QUEUE@@EA, rsi; LOSSY_QUEUE * FREB_LOG_FILE_MANAGER::sm_pLossyQueue
0x180008448  mov     cs:?sm_fShutdown@FREB_LOG_FILE_MANAGER@@0HA, esi; int FREB_LOG_FILE_MANAGER::sm_fShutdown
0x18000844e  mov     cs:?sm_hWriterThread@FREB_LOG_FILE_MANAGER@@0PEAXEA, rsi; void * FREB_LOG_FILE_MANAGER::sm_hWriterThread
0x180008455  lea     ecx, [rsi+68h]; Size
0x180008458  mov     cs:?sm_lScavengesSinceStartup@FREB_LOG_FILE_MANAGER@@0JA, esi; long FREB_LOG_FILE_MANAGER::sm_lScavengesSinceStartup
0x18000845e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008463  test    rax, rax
0x180008466  jz      short loc_1800084DF
0x180008468  mov     [rax], esi
0x18000846a  mov     [rax+8], rsi
0x18000846e  mov     [rax+10h], rsi
0x180008472  mov     [rax+18h], rsi
0x180008476  mov     [rax+48h], rsi
0x18000847a  mov     [rax+50h], rsi
0x18000847e  mov     [rax+58h], rsi
0x180008482  mov     [rax+60h], rsi
0x180008486  mov     cs:?sm_pLossyQueue@FREB_LOG_FILE_MANAGER@@0PEAVLOSSY_QUEUE@@EA, rax; LOSSY_QUEUE * FREB_LOG_FILE_MANAGER::sm_pLossyQueue
0x18000848d  call    ?Initialize@LOSSY_QUEUE@@QEAAJK@Z; LOSSY_QUEUE::Initialize(ulong)
0x180008492  mov     ebx, eax
0x180008494  test    eax, eax
0x180008496  js      short loc_1800084EB
0x180008498  mov     [rsp+38h+lpThreadId], rsi; lpThreadId
0x18000849d  lea     r8, ?WriterThread@FREB_LOG_FILE_MANAGER@@SAKPEAX@Z; lpStartAddress
0x1800084a4  xor     r9d, r9d; lpParameter
0x1800084a7  mov     [rsp+38h+dwCreationFlags], esi; dwCreationFlags
0x1800084ab  xor     edx, edx; dwStackSize
0x1800084ad  xor     ecx, ecx; lpThreadAttributes
0x1800084af  call    cs:__imp_CreateThread
0x1800084b5  mov     cs:?sm_hWriterThread@FREB_LOG_FILE_MANAGER@@0PEAXEA, rax; void * FREB_LOG_FILE_MANAGER::sm_hWriterThread
0x1800084bc  test    rax, rax
0x1800084bf  jnz     short loc_18000852E
0x1800084c1  lea     edi, [rsi+1]
0x1800084c4  call    cs:__imp_GetLastError
0x1800084ca  mov     ebx, eax
0x1800084cc  test    eax, eax
0x1800084ce  jle     short loc_1800084D9
0x1800084d0  movzx   ebx, ax
0x1800084d3  or      ebx, 80070000h
0x1800084d9  test    ebx, ebx
0x1800084db  jns     short loc_18000852E
0x1800084dd  jmp     short loc_1800084EB
0x1800084df  mov     cs:?sm_pLossyQueue@FREB_LOG_FILE_MANAGER@@0PEAVLOSSY_QUEUE@@EA, rsi; LOSSY_QUEUE * FREB_LOG_FILE_MANAGER::sm_pLossyQueue
0x1800084e6  mov     ebx, 80070008h
0x1800084eb  cmp     cs:?sm_pLossyQueue@FREB_LOG_FILE_MANAGER@@0PEAVLOSSY_QUEUE@@EA, rsi; LOSSY_QUEUE * FREB_LOG_FILE_MANAGER::sm_pLossyQueue
0x1800084f2  jz      short loc_180008515
0x1800084f4  test    edi, edi
0x1800084f6  jz      short loc_1800084FD
0x1800084f8  call    ?Terminate@LOSSY_QUEUE@@QEAAJXZ; LOSSY_QUEUE::Terminate(void)
0x1800084fd  mov     rcx, cs:?sm_pLossyQueue@FREB_LOG_FILE_MANAGER@@0PEAVLOSSY_QUEUE@@EA; Block
0x180008504  test    rcx, rcx
0x180008507  jz      short loc_18000850E
0x180008509  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000850e  mov     cs:?sm_pLossyQueue@FREB_LOG_FILE_MANAGER@@0PEAVLOSSY_QUEUE@@EA, rsi; LOSSY_QUEUE * FREB_LOG_FILE_MANAGER::sm_pLossyQueue
0x180008515  mov     rcx, cs:?sm_hWriterThread@FREB_LOG_FILE_MANAGER@@0PEAXEA; hObject
0x18000851c  test    rcx, rcx
0x18000851f  jz      short loc_18000852E
0x180008521  call    cs:__imp_CloseHandle
0x180008527  mov     cs:?sm_hWriterThread@FREB_LOG_FILE_MANAGER@@0PEAXEA, rsi; void * FREB_LOG_FILE_MANAGER::sm_hWriterThread
0x18000852e  mov     rsi, [rsp+38h+arg_8]
0x180008533  mov     eax, ebx
0x180008535  mov     rbx, [rsp+38h+arg_0]
0x18000853a  add     rsp, 30h
0x18000853e  pop     rdi
0x18000853f  retn
```
