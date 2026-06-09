# SyncMessageThread

- ea: `0x18000c080`
- end: `0x18000c294`
- name: `SyncMessageThread`
- size: `532`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000c080`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000c0b3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000c0b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000c0a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000c0a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c182`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c204`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c182`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c204`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c0d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c1b6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c264`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c0d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c1b6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c264`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c0e6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c0e6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c1ca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c278`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c1ca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c278`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18000c172`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18000c172`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000c253`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000c253`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000c1ec`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000c1ec`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000c228`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000c228`
- `FLTLIB!FilterGetMessage` at `0x18000c139`
- `FLTLIB!FilterGetMessage` at `0x18000c139`

## pseudocode

```c
__int64 __fastcall SyncMessageThread(PVOID Parameter)
{
  struct _FILTER_MESSAGE_HEADER *v1; // rdi
  DWORD v2; // esi
  HANDLE CurrentThread; // rax
  HANDLE ProcessHeap; // rax
  signed int v5; // ebx
  HRESULT Message; // eax
  signed int v7; // eax
  HANDLE v8; // rax
  struct _TP_WORK *ThreadpoolWork; // rsi
  signed int LastError; // eax
  HANDLE v11; // rax
  struct _OVERLAPPED Overlapped; // [rsp+20h] [rbp-28h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+78h] [rbp+30h] BYREF

  v1 = 0;
  memset(&Overlapped, 0, sizeof(Overlapped));
  NumberOfBytesTransferred = 0;
  v2 = 4096;
  CurrentThread = GetCurrentThread();
  SetThreadPriority(CurrentThread, 1);
  if ( !dword_18002ABE8 )
    return 0;
  do
  {
    if ( !v1 )
    {
      ProcessHeap = GetProcessHeap();
      v1 = (struct _FILTER_MESSAGE_HEADER *)HeapAlloc(ProcessHeap, 0, v2);
      v5 = v1 == 0 ? 8 : 0;
      if ( !v1 )
        v5 |= 0x80070000;
      if ( v5 < 0 )
        break;
    }
    NumberOfBytesTransferred = 0;
    memset(&Overlapped, 0, sizeof(Overlapped));
    Message = FilterGetMessage(*(&hPort + 1), v1, v2, &Overlapped);
    v5 = Message;
    if ( Message >= 0 )
    {
      NumberOfBytesTransferred = Overlapped.InternalHigh;
LABEL_17:
      ThreadpoolWork = CreateThreadpoolWork((PTP_WORK_CALLBACK)SyncWorkThread, v1, 0);
      if ( ThreadpoolWork )
      {
        v5 = 0;
      }
      else
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
      }
      if ( v5 < 0 )
      {
        if ( ThreadpoolWork )
          CloseThreadpoolWork(ThreadpoolWork);
        break;
      }
      SubmitThreadpoolWork(ThreadpoolWork);
      v2 = 4096;
LABEL_23:
      v1 = 0;
      continue;
    }
    if ( Message == -2147023899 )
    {
      if ( GetOverlappedResult(*(&hPort + 1), &Overlapped, &NumberOfBytesTransferred, 1) )
      {
        v5 = 0;
      }
      else
      {
        v7 = GetLastError();
        v5 = v7;
        if ( v7 > 0 )
          v5 = (unsigned __int16)v7 | 0x80070000;
      }
    }
    else if ( Message == -2147024890 )
    {
      break;
    }
    if ( v5 == -2147024774 )
    {
      v8 = GetProcessHeap();
      HeapFree(v8, 0, v1);
      v2 = NumberOfBytesTransferred;
      goto LABEL_23;
    }
    if ( v5 >= 0 )
      goto LABEL_17;
  }
  while ( dword_18002ABE8 );
  if ( v1 )
  {
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v1);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000c080  push    rbp
0x18000c082  push    rbx
0x18000c083  push    rsi
0x18000c084  push    rdi
0x18000c085  mov     rbp, rsp
0x18000c088  sub     rsp, 48h
0x18000c08c  xorps   xmm0, xmm0
0x18000c08f  xor     edi, edi
0x18000c091  movups  xmmword ptr [rbp+Overlapped.Internal], xmm0
0x18000c095  mov     [rbp+NumberOfBytesTransferred], edi
0x18000c098  mov     esi, 1000h
0x18000c09d  movups  xmmword ptr [rbp+Overlapped.10h], xmm0
0x18000c0a1  call    cs:__imp_GetCurrentThread
0x18000c0a8  nop     dword ptr [rax+rax+00h]
0x18000c0ad  mov     rcx, rax; hThread
0x18000c0b0  lea     edx, [rdi+1]; nPriority
0x18000c0b3  call    cs:__imp_SetThreadPriority
0x18000c0ba  nop     dword ptr [rax+rax+00h]
0x18000c0bf  mov     eax, cs:dword_18002ABE8
0x18000c0c5  test    eax, eax
0x18000c0c7  jz      loc_18000C286
0x18000c0cd  test    rdi, rdi
0x18000c0d0  jnz     short loc_18000C116
0x18000c0d2  call    cs:__imp_GetProcessHeap
0x18000c0d9  nop     dword ptr [rax+rax+00h]
0x18000c0de  mov     r8d, esi; dwBytes
0x18000c0e1  xor     edx, edx; dwFlags
0x18000c0e3  mov     rcx, rax; hHeap
0x18000c0e6  call    cs:__imp_HeapAlloc
0x18000c0ed  nop     dword ptr [rax+rax+00h]
0x18000c0f2  mov     rdi, rax
0x18000c0f5  neg     rax
0x18000c0f8  sbb     ebx, ebx
0x18000c0fa  not     ebx
0x18000c0fc  and     ebx, 8
0x18000c0ff  mov     eax, ebx
0x18000c101  or      eax, 80070000h
0x18000c106  test    rdi, rdi
0x18000c109  cmovz   ebx, eax
0x18000c10c  test    ebx, ebx
0x18000c10e  jz      short loc_18000C116
0x18000c110  js      loc_18000C25F
0x18000c116  mov     rcx, qword ptr cs:hPort+8; hPort
0x18000c11d  lea     r9, [rbp+Overlapped]; lpOverlapped
0x18000c121  xorps   xmm0, xmm0
0x18000c124  mov     [rbp+NumberOfBytesTransferred], 0
0x18000c12b  mov     r8d, esi; dwMessageBufferSize
0x18000c12e  mov     rdx, rdi; lpMessageBuffer
0x18000c131  movups  xmmword ptr [rbp+Overlapped.Internal], xmm0
0x18000c135  movups  xmmword ptr [rbp+Overlapped.10h], xmm0
0x18000c139  call    cs:__imp_FilterGetMessage
0x18000c140  nop     dword ptr [rax+rax+00h]
0x18000c145  mov     ebx, eax
0x18000c147  test    eax, eax
0x18000c149  js      short loc_18000C156
0x18000c14b  mov     eax, dword ptr [rbp+Overlapped.InternalHigh]
0x18000c14e  mov     [rbp+NumberOfBytesTransferred], eax
0x18000c151  jmp     loc_18000C1DF
0x18000c156  cmp     eax, 800703E5h
0x18000c15b  jnz     short loc_18000C1A3
0x18000c15d  mov     rcx, qword ptr cs:hPort+8; hFile
0x18000c164  lea     r8, [rbp+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x18000c168  mov     r9d, 1; bWait
0x18000c16e  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x18000c172  call    cs:__imp_GetOverlappedResult
0x18000c179  nop     dword ptr [rax+rax+00h]
0x18000c17e  test    eax, eax
0x18000c180  jnz     short loc_18000C19F
0x18000c182  call    cs:__imp_GetLastError
0x18000c189  nop     dword ptr [rax+rax+00h]
0x18000c18e  mov     ebx, eax
0x18000c190  test    eax, eax
0x18000c192  jle     short loc_18000C1AE
0x18000c194  movzx   ebx, ax
0x18000c197  or      ebx, 80070000h
0x18000c19d  jmp     short loc_18000C1AE
0x18000c19f  xor     ebx, ebx
0x18000c1a1  jmp     short loc_18000C1AE
0x18000c1a3  cmp     eax, 80070006h
0x18000c1a8  jz      loc_18000C25F
0x18000c1ae  cmp     ebx, 8007007Ah
0x18000c1b4  jnz     short loc_18000C1DB
0x18000c1b6  call    cs:__imp_GetProcessHeap
0x18000c1bd  nop     dword ptr [rax+rax+00h]
0x18000c1c2  mov     r8, rdi; lpMem
0x18000c1c5  xor     edx, edx; dwFlags
0x18000c1c7  mov     rcx, rax; hHeap
0x18000c1ca  call    cs:__imp_HeapFree
0x18000c1d1  nop     dword ptr [rax+rax+00h]
0x18000c1d6  mov     esi, [rbp+NumberOfBytesTransferred]
0x18000c1d9  jmp     short loc_18000C239
0x18000c1db  test    ebx, ebx
0x18000c1dd  js      short loc_18000C23B
0x18000c1df  xor     r8d, r8d; pcbe
0x18000c1e2  lea     rcx, SyncWorkThread; pfnwk
0x18000c1e9  mov     rdx, rdi; pv
0x18000c1ec  call    cs:__imp_CreateThreadpoolWork
0x18000c1f3  nop     dword ptr [rax+rax+00h]
0x18000c1f8  mov     rsi, rax
0x18000c1fb  test    rax, rax
0x18000c1fe  jz      short loc_18000C204
0x18000c200  xor     ebx, ebx
0x18000c202  jmp     short loc_18000C21F
0x18000c204  call    cs:__imp_GetLastError
0x18000c20b  nop     dword ptr [rax+rax+00h]
0x18000c210  mov     ebx, eax
0x18000c212  test    eax, eax
0x18000c214  jle     short loc_18000C21F
0x18000c216  movzx   ebx, ax
0x18000c219  or      ebx, 80070000h
0x18000c21f  test    ebx, ebx
0x18000c221  jz      short loc_18000C225
0x18000c223  js      short loc_18000C24B
0x18000c225  mov     rcx, rsi; pwk
0x18000c228  call    cs:__imp_SubmitThreadpoolWork
0x18000c22f  nop     dword ptr [rax+rax+00h]
0x18000c234  mov     esi, 1000h
0x18000c239  xor     edi, edi
0x18000c23b  mov     eax, cs:dword_18002ABE8
0x18000c241  test    eax, eax
0x18000c243  jnz     loc_18000C0CD
0x18000c249  jmp     short loc_18000C25F
0x18000c24b  test    rsi, rsi
0x18000c24e  jz      short loc_18000C25F
0x18000c250  mov     rcx, rsi; pwk
0x18000c253  call    cs:__imp_CloseThreadpoolWork
0x18000c25a  nop     dword ptr [rax+rax+00h]
0x18000c25f  test    rdi, rdi
0x18000c262  jz      short loc_18000C288
0x18000c264  call    cs:__imp_GetProcessHeap
0x18000c26b  nop     dword ptr [rax+rax+00h]
0x18000c270  mov     r8, rdi; lpMem
0x18000c273  xor     edx, edx; dwFlags
0x18000c275  mov     rcx, rax; hHeap
0x18000c278  call    cs:__imp_HeapFree
0x18000c27f  nop     dword ptr [rax+rax+00h]
0x18000c284  jmp     short loc_18000C288
0x18000c286  xor     ebx, ebx
0x18000c288  mov     eax, ebx
0x18000c28a  add     rsp, 48h
0x18000c28e  pop     rdi
0x18000c28f  pop     rsi
0x18000c290  pop     rbx
0x18000c291  pop     rbp
0x18000c292  retn
```
