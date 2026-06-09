# TRANSPORT::WorkerThread(void *)

- ea: `0x180002470`
- end: `0x180002538`
- name: `?WorkerThread@TRANSPORT@@SAKPEAX@Z`
- size: `200`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002470`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800024ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800024ba`
- `api-ms-win-core-io-l1-1-0!GetQueuedCompletionStatus` at `0x1800024ac`
- `api-ms-win-core-io-l1-1-0!GetQueuedCompletionStatus` at `0x1800024ac`

## pseudocode

```c
__int64 __fastcall TRANSPORT::WorkerThread(PVOID Parameter)
{
  __int64 v1; // rdx
  char *hEvent; // rcx
  DWORD NumberOfBytesTransferred; // [rsp+48h] [rbp+10h] BYREF
  LPOVERLAPPED Overlapped; // [rsp+50h] [rbp+18h] BYREF
  unsigned __int64 CompletionKey; // [rsp+58h] [rbp+20h] BYREF

  NumberOfBytesTransferred = 0;
  CompletionKey = 0;
  while ( 1 )
  {
    Overlapped = 0;
    v1 = GetQueuedCompletionStatus(
           TRANSPORT::sm_hCompletionPort,
           &NumberOfBytesTransferred,
           &CompletionKey,
           &Overlapped,
           0xFFFFFFFF)
       ? 0LL
       : GetLastError();
    if ( !Overlapped )
      break;
    hEvent = (char *)Overlapped[-1].hEvent;
    Overlapped[1].Offset = 1;
    if ( Overlapped == (LPOVERLAPPED)(hEvent + 24) )
    {
      if ( (int)v1 > 0 )
        v1 = (unsigned __int16)v1 | 0x80070000;
      (***((void (__fastcall ****)(_QWORD, __int64, _QWORD))hEvent + 1))(
        *((_QWORD *)hEvent + 1),
        v1,
        NumberOfBytesTransferred);
    }
    else if ( Overlapped == (LPOVERLAPPED)(hEvent + 88) )
    {
      if ( (int)v1 > 0 )
        v1 = (unsigned __int16)v1 | 0x80070000;
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)hEvent + 1) + 8LL))(
        *((_QWORD *)hEvent + 1),
        v1,
        NumberOfBytesTransferred);
    }
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180002470  sub     rsp, 38h
0x180002474  mov     [rsp+38h+NumberOfBytesTransferred], 0
0x18000247c  mov     [rsp+38h+CompletionKey], 0
0x180002485  mov     rcx, cs:?sm_hCompletionPort@TRANSPORT@@1PEAXEA; CompletionPort
0x18000248c  lea     r9, [rsp+38h+Overlapped]; lpOverlapped
0x180002491  lea     r8, [rsp+38h+CompletionKey]; lpCompletionKey
0x180002496  mov     [rsp+38h+Overlapped], 0
0x18000249f  lea     rdx, [rsp+38h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x1800024a4  mov     [rsp+38h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x1800024ac  call    cs:__imp_GetQueuedCompletionStatus
0x1800024b2  test    eax, eax
0x1800024b4  jz      short loc_1800024BA
0x1800024b6  xor     edx, edx
0x1800024b8  jmp     short loc_1800024C2
0x1800024ba  call    cs:__imp_GetLastError
0x1800024c0  mov     edx, eax
0x1800024c2  mov     rax, [rsp+38h+Overlapped]
0x1800024c7  test    rax, rax
0x1800024ca  jz      short loc_180002531
0x1800024cc  mov     rcx, [rax-8]
0x1800024d0  mov     dword ptr [rax+30h], 1
0x1800024d7  lea     rax, [rcx+18h]
0x1800024db  cmp     [rsp+38h+Overlapped], rax
0x1800024e0  jnz     short loc_1800024FB
0x1800024e2  test    edx, edx
0x1800024e4  jle     short loc_1800024EF
0x1800024e6  movzx   edx, dx
0x1800024e9  or      edx, 80070000h
0x1800024ef  mov     rcx, [rcx+8]
0x1800024f3  mov     rax, [rcx]
0x1800024f6  mov     rax, [rax]
0x1800024f9  jmp     short loc_180002522
0x1800024fb  lea     rax, [rcx+58h]
0x1800024ff  cmp     [rsp+38h+Overlapped], rax
0x180002504  jnz     loc_180002485
0x18000250a  test    edx, edx
0x18000250c  jle     short loc_180002517
0x18000250e  movzx   edx, dx
0x180002511  or      edx, 80070000h
0x180002517  mov     rcx, [rcx+8]
0x18000251b  mov     rax, [rcx]
0x18000251e  mov     rax, [rax+8]
0x180002522  mov     r8d, [rsp+38h+NumberOfBytesTransferred]
0x180002527  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000252c  jmp     loc_180002485
0x180002531  mov     eax, edx
0x180002533  add     rsp, 38h
0x180002537  retn
```
