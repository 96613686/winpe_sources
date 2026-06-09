# TRANSPORT::StaticTerminate(void)

- ea: `0x1800023c0`
- end: `0x180002463`
- name: `?StaticTerminate@TRANSPORT@@SAJXZ`
- size: `163`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008af4`

## callees

- `0x1800023c0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000241c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000243f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000241c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000243f`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x1800023e1`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x1800023e1`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18000240b`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18000240b`
- `WS2_32!__imp_WSACleanup` at `0x180002450`
- `WS2_32!__imp_WSACleanup` at `0x180002450`

## pseudocode

```c
__int64 TRANSPORT::StaticTerminate(void)
{
  int v0; // ebx
  __int64 i; // rbx
  void *v2; // rcx

  v0 = 4;
  do
  {
    PostQueuedCompletionStatus(TRANSPORT::sm_hCompletionPort, 0, 0x98765432, 0);
    --v0;
  }
  while ( v0 );
  if ( TRANSPORT::sm_hThread )
    WaitForMultipleObjects(4u, &TRANSPORT::sm_hThread, 1, 0xFFFFFFFF);
  for ( i = 0; i != 4; ++i )
  {
    v2 = *(&TRANSPORT::sm_hThread + i);
    if ( v2 )
    {
      CloseHandle(v2);
      *(&TRANSPORT::sm_hThread + i) = 0;
    }
  }
  if ( TRANSPORT::sm_hCompletionPort )
  {
    CloseHandle(TRANSPORT::sm_hCompletionPort);
    TRANSPORT::sm_hCompletionPort = 0;
  }
  WSACleanup();
  return 0;
}

```

## disassembly

```asm
0x1800023c0  mov     [rsp+arg_0], rbx
0x1800023c5  push    rsi
0x1800023c6  sub     rsp, 20h
0x1800023ca  mov     ebx, 4
0x1800023cf  mov     rcx, cs:?sm_hCompletionPort@TRANSPORT@@1PEAXEA; CompletionPort
0x1800023d6  xor     r9d, r9d; lpOverlapped
0x1800023d9  xor     edx, edx; dwNumberOfBytesTransferred
0x1800023db  mov     r8d, 98765432h; dwCompletionKey
0x1800023e1  call    cs:__imp_PostQueuedCompletionStatus
0x1800023e7  add     ebx, 0FFFFFFFFh
0x1800023ea  jnz     short loc_1800023CF
0x1800023ec  cmp     cs:?sm_hThread@TRANSPORT@@0PAPEAXA, 0; void * near * TRANSPORT::sm_hThread
0x1800023f4  lea     rsi, ?sm_hThread@TRANSPORT@@0PAPEAXA; void * near * TRANSPORT::sm_hThread
0x1800023fb  jz      short loc_180002411
0x1800023fd  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180002401  lea     r8d, [rbx+1]; bWaitAll
0x180002405  mov     rdx, rsi; lpHandles
0x180002408  lea     ecx, [rbx+4]; nCount
0x18000240b  call    cs:__imp_WaitForMultipleObjects
0x180002411  xor     ebx, ebx
0x180002413  mov     rcx, [rsi+rbx*8]; hObject
0x180002417  test    rcx, rcx
0x18000241a  jz      short loc_18000242A
0x18000241c  call    cs:__imp_CloseHandle
0x180002422  mov     qword ptr [rsi+rbx*8], 0
0x18000242a  inc     rbx
0x18000242d  cmp     rbx, 4
0x180002431  jnz     short loc_180002413
0x180002433  mov     rcx, cs:?sm_hCompletionPort@TRANSPORT@@1PEAXEA; hObject
0x18000243a  test    rcx, rcx
0x18000243d  jz      short loc_180002450
0x18000243f  call    cs:__imp_CloseHandle
0x180002445  mov     cs:?sm_hCompletionPort@TRANSPORT@@1PEAXEA, 0; void * TRANSPORT::sm_hCompletionPort
0x180002450  call    cs:__imp_WSACleanup
0x180002456  mov     rbx, [rsp+28h+arg_0]
0x18000245b  xor     eax, eax
0x18000245d  add     rsp, 20h
0x180002461  pop     rsi
0x180002462  retn
```
