# P2P_THREAD_POOL::Terminate(void)

- ea: `0x18007d71c`
- end: `0x18007d7a6`
- name: `?Terminate@P2P_THREAD_POOL@@QEAAXXZ`
- size: `138`
- prototype: `void __fastcall(P2P_THREAD_POOL *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180088c2c`
- `0x1800f95a8`

## callees

- `0x18007d71c`
- `0x1800f9564`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007d790`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007d790`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007d782`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007d782`
- `api-ms-win-core-processthreads-l1-1-0!SwitchToThread` at `0x18007d754`
- `api-ms-win-core-processthreads-l1-1-0!SwitchToThread` at `0x18007d754`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18007d763`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18007d763`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x18007d746`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x18007d746`

## pseudocode

```c
void __fastcall P2P_THREAD_POOL::Terminate(P2P_THREAD_POOL *this)
{
  int v2; // edi
  HANDLE ProcessHeap; // rax

  if ( *((_QWORD *)this + 1) )
  {
    v2 = 1;
    do
    {
      if ( PostQueuedCompletionStatus(*(HANDLE *)this, 0, 0, (LPOVERLAPPED)((char *)this + 16)) )
      {
        --v2;
      }
      else if ( !SwitchToThread() )
      {
        Sleep(0x3E8u);
      }
    }
    while ( v2 );
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 14, 0xFFFFFFFF) == 1 )
  {
    P2P_THREAD_POOL::~P2P_THREAD_POOL(this);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, this);
  }
}

```

## disassembly

```asm
0x18007d71c  mov     [rsp+arg_0], rbx
0x18007d721  mov     [rsp+arg_8], rsi
0x18007d726  push    rdi
0x18007d727  sub     rsp, 20h
0x18007d72b  cmp     qword ptr [rcx+8], 0
0x18007d730  mov     rbx, rcx
0x18007d733  jz      short loc_18007D76D
0x18007d735  mov     edi, 1
0x18007d73a  mov     rcx, [rbx]; CompletionPort
0x18007d73d  lea     r9, [rbx+10h]; lpOverlapped
0x18007d741  xor     r8d, r8d; dwCompletionKey
0x18007d744  xor     edx, edx; dwNumberOfBytesTransferred
0x18007d746  call    cs:__imp_PostQueuedCompletionStatus
0x18007d74c  test    eax, eax
0x18007d74e  jz      short loc_18007D754
0x18007d750  dec     edi
0x18007d752  jmp     short loc_18007D769
0x18007d754  call    cs:__imp_SwitchToThread
0x18007d75a  test    eax, eax
0x18007d75c  jnz     short loc_18007D769
0x18007d75e  mov     ecx, 3E8h; dwMilliseconds
0x18007d763  call    cs:__imp_Sleep
0x18007d769  test    edi, edi
0x18007d76b  jnz     short loc_18007D73A
0x18007d76d  or      eax, 0FFFFFFFFh
0x18007d770  lock xadd [rbx+38h], eax
0x18007d775  cmp     eax, 1
0x18007d778  jnz     short loc_18007D796
0x18007d77a  mov     rcx, rbx; this
0x18007d77d  call    ??1P2P_THREAD_POOL@@QEAA@XZ; P2P_THREAD_POOL::~P2P_THREAD_POOL(void)
0x18007d782  call    cs:__imp_GetProcessHeap
0x18007d788  mov     r8, rbx; lpMem
0x18007d78b  xor     edx, edx; dwFlags
0x18007d78d  mov     rcx, rax; hHeap
0x18007d790  call    cs:__imp_HeapFree
0x18007d796  mov     rbx, [rsp+28h+arg_0]
0x18007d79b  mov     rsi, [rsp+28h+arg_8]
0x18007d7a0  add     rsp, 20h
0x18007d7a4  pop     rdi
0x18007d7a5  retn
```
