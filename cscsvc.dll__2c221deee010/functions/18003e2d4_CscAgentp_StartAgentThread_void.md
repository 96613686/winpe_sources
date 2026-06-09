# CscAgentp_StartAgentThread(void)

- ea: `0x18003e2d4`
- end: `0x18003e4cb`
- name: `?CscAgentp_StartAgentThread@@YAJXZ`
- size: `503`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x18003ce68`

## callees

- `0x18000d640`
- `0x18001be00`
- `0x180024b60`
- `0x18002f10c`
- `0x180036394`
- `0x18003e2d4`
- `0x1800508f0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e412`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e42c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e449`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e466`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e412`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e42c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e449`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e466`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003e3bd`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003e3bd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003e2f1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003e31c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003e347`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003e2f1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003e31c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003e347`

## pseudocode

```c
__int64 CscAgentp_StartAgentThread(void)
{
  int Error; // ebx
  void *v1; // r9
  _DWORD *v2; // rdi
  _DWORD *v3; // r9
  int v4; // r9d
  void *v5; // rdx
  HANDLE hObject; // [rsp+50h] [rbp+8h] BYREF
  LPVOID lpParameter; // [rsp+58h] [rbp+10h] BYREF

  g_hevtTerminateAgentThread = CreateEventW(0, 1, 0, 0);
  if ( !g_hevtTerminateAgentThread )
  {
    Error = ResultFromLastError();
    if ( Error < 0 )
      goto LABEL_14;
  }
  g_hevtWakeAgentThread = CreateEventW(0, 1, 0, 0);
  if ( !g_hevtWakeAgentThread )
  {
    Error = ResultFromLastError();
    if ( Error < 0 )
      goto LABEL_14;
  }
  hObject = CreateEventW(0, 1, 0, 0);
  if ( hObject )
  {
    lpParameter = 0;
    Error = CscUtil_HeapAlloc(0x10u, 1, &lpParameter, v1);
    if ( Error >= 0 )
    {
      v2 = lpParameter;
      v3 = lpParameter;
      *(_QWORD *)lpParameter = hObject;
      v3[2] = 0;
      g_AgentThreadHandle = CreateThread(0, 0, CscAgentp_ThreadProc, v3, 0, &g_AgentThreadId);
      if ( g_AgentThreadHandle )
      {
        CscUtil_WaitAndProcessThreadMessages(&hObject, 1u, 0xFFFFFFFF, v4, 0, 0, 0);
        Error = v2[2];
      }
      else
      {
        Error = ResultFromLastError();
      }
      CscUtil_HeapFree(v2, v5);
    }
    CloseHandle(hObject);
  }
  else
  {
    Error = ResultFromLastError();
  }
  if ( Error < 0 )
  {
LABEL_14:
    if ( g_hevtTerminateAgentThread )
    {
      CloseHandle(g_hevtTerminateAgentThread);
      g_hevtTerminateAgentThread = 0;
    }
    if ( g_hevtWakeAgentThread )
    {
      CloseHandle(g_hevtWakeAgentThread);
      g_hevtWakeAgentThread = 0;
    }
    if ( g_AgentThreadHandle )
    {
      CloseHandle(g_AgentThreadHandle);
      g_AgentThreadHandle = 0;
      g_AgentThreadId = 0;
    }
    CscEvt_AgentFailedStartup(Error);
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        42,
        WPP_ef399ae69b0439092b78fa9bd8d7e9cf_Traceguids,
        (unsigned int)Error);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18003e2d4  mov     [rsp+arg_10], rbx
0x18003e2d9  mov     [rsp+arg_18], rbp
0x18003e2de  push    rdi
0x18003e2df  sub     rsp, 40h
0x18003e2e3  xor     r9d, r9d; lpName
0x18003e2e6  xor     r8d, r8d; bInitialState
0x18003e2e9  xor     ecx, ecx; lpEventAttributes
0x18003e2eb  lea     ebp, [r9+1]
0x18003e2ef  mov     edx, ebp; bManualReset
0x18003e2f1  call    cs:__imp_CreateEventW
0x18003e2f7  mov     cs:?g_hevtTerminateAgentThread@@3PEAXEA, rax; void * g_hevtTerminateAgentThread
0x18003e2fe  test    rax, rax
0x18003e301  jnz     short loc_18003E312
0x18003e303  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18003e308  mov     ebx, eax
0x18003e30a  test    eax, eax
0x18003e30c  js      loc_18003E420
0x18003e312  xor     r9d, r9d; lpName
0x18003e315  xor     r8d, r8d; bInitialState
0x18003e318  mov     edx, ebp; bManualReset
0x18003e31a  xor     ecx, ecx; lpEventAttributes
0x18003e31c  call    cs:__imp_CreateEventW
0x18003e322  mov     cs:?g_hevtWakeAgentThread@@3PEAXEA, rax; void * g_hevtWakeAgentThread
0x18003e329  test    rax, rax
0x18003e32c  jnz     short loc_18003E33D
0x18003e32e  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18003e333  mov     ebx, eax
0x18003e335  test    eax, eax
0x18003e337  js      loc_18003E420
0x18003e33d  xor     r9d, r9d; lpName
0x18003e340  xor     r8d, r8d; bInitialState
0x18003e343  mov     edx, ebp; bManualReset
0x18003e345  xor     ecx, ecx; lpEventAttributes
0x18003e347  call    cs:__imp_CreateEventW
0x18003e34d  mov     [rsp+48h+hObject], rax
0x18003e352  test    rax, rax
0x18003e355  jnz     short loc_18003E363
0x18003e357  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18003e35c  mov     ebx, eax
0x18003e35e  jmp     loc_18003E418
0x18003e363  lea     r8, [rsp+48h+lpParameter]; void **
0x18003e368  mov     [rsp+48h+lpParameter], 0
0x18003e371  mov     edx, ebp; int
0x18003e373  mov     ecx, 10h; dwBytes
0x18003e378  call    ?CscUtil_HeapAlloc@@YAJ_KHPEAPEAXPEAX@Z; CscUtil_HeapAlloc(unsigned __int64,int,void * *,void *)
0x18003e37d  mov     ebx, eax
0x18003e37f  test    eax, eax
0x18003e381  js      loc_18003E40D
0x18003e387  mov     rax, [rsp+48h+hObject]
0x18003e38c  lea     r8, ?CscAgentp_ThreadProc@@YAKPEAX@Z; lpStartAddress
0x18003e393  mov     rdi, [rsp+48h+lpParameter]
0x18003e398  xor     edx, edx; dwStackSize
0x18003e39a  mov     r9, rdi; lpParameter
0x18003e39d  xor     ecx, ecx; lpThreadAttributes
0x18003e39f  mov     [rdi], rax
0x18003e3a2  lea     rax, ?g_AgentThreadId@@3KA; ulong g_AgentThreadId
0x18003e3a9  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x18003e3ae  mov     [rsp+48h+dwCreationFlags], 0; dwCreationFlags
0x18003e3b6  mov     dword ptr [rdi+8], 0
0x18003e3bd  call    cs:__imp_CreateThread
0x18003e3c3  mov     cs:?g_AgentThreadHandle@@3PEAXEA, rax; void * g_AgentThreadHandle
0x18003e3ca  test    rax, rax
0x18003e3cd  jnz     short loc_18003E3D8
0x18003e3cf  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18003e3d4  mov     ebx, eax
0x18003e3d6  jmp     short loc_18003E405
0x18003e3d8  mov     [rsp+48h+var_18], 0; int *
0x18003e3e1  lea     rcx, [rsp+48h+hObject]; pHandles
0x18003e3e6  mov     [rsp+48h+lpThreadId], 0; int (*)(struct tagMSG *)
0x18003e3ef  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x18003e3f3  mov     edx, ebp; nCount
0x18003e3f5  mov     [rsp+48h+dwCreationFlags], 0; int
0x18003e3fd  call    ?CscUtil_WaitAndProcessThreadMessages@@YAKPEAPEAXKKHHP6AHPEAUtagMSG@@@ZPEAH@Z; CscUtil_WaitAndProcessThreadMessages(void * *,ulong,ulong,int,int,int (*)(tagMSG *),int *)
0x18003e402  mov     ebx, [rdi+8]
0x18003e405  mov     rcx, rdi; lpMem
0x18003e408  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x18003e40d  mov     rcx, [rsp+48h+hObject]; hObject
0x18003e412  call    cs:__imp_CloseHandle
0x18003e418  test    ebx, ebx
0x18003e41a  jns     loc_18003E4B9
0x18003e420  mov     rcx, cs:?g_hevtTerminateAgentThread@@3PEAXEA; hObject
0x18003e427  test    rcx, rcx
0x18003e42a  jz      short loc_18003E43D
0x18003e42c  call    cs:__imp_CloseHandle
0x18003e432  mov     cs:?g_hevtTerminateAgentThread@@3PEAXEA, 0; void * g_hevtTerminateAgentThread
0x18003e43d  mov     rcx, cs:?g_hevtWakeAgentThread@@3PEAXEA; hObject
0x18003e444  test    rcx, rcx
0x18003e447  jz      short loc_18003E45A
0x18003e449  call    cs:__imp_CloseHandle
0x18003e44f  mov     cs:?g_hevtWakeAgentThread@@3PEAXEA, 0; void * g_hevtWakeAgentThread
0x18003e45a  mov     rcx, cs:?g_AgentThreadHandle@@3PEAXEA; hObject
0x18003e461  test    rcx, rcx
0x18003e464  jz      short loc_18003E481
0x18003e466  call    cs:__imp_CloseHandle
0x18003e46c  mov     cs:?g_AgentThreadHandle@@3PEAXEA, 0; void * g_AgentThreadHandle
0x18003e477  mov     cs:?g_AgentThreadId@@3KA, 0; ulong g_AgentThreadId
0x18003e481  mov     ecx, ebx; int
0x18003e483  call    ?CscEvt_AgentFailedStartup@@YAKJ@Z; CscEvt_AgentFailedStartup(long)
0x18003e488  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e48f  lea     rax, WPP_GLOBAL_Control
0x18003e496  cmp     rcx, rax
0x18003e499  jz      short loc_18003E4B9
0x18003e49b  test    byte ptr [rcx+1Ch], 2
0x18003e49f  jz      short loc_18003E4B9
0x18003e4a1  mov     rcx, [rcx+10h]
0x18003e4a5  lea     r8, WPP_ef399ae69b0439092b78fa9bd8d7e9cf_Traceguids
0x18003e4ac  mov     edx, 2Ah ; '*'
0x18003e4b1  mov     r9d, ebx
0x18003e4b4  call    WPP_SF_d
0x18003e4b9  mov     rbp, [rsp+48h+arg_18]
0x18003e4be  mov     eax, ebx
0x18003e4c0  mov     rbx, [rsp+48h+arg_10]
0x18003e4c5  add     rsp, 40h
0x18003e4c9  pop     rdi
0x18003e4ca  retn
```
