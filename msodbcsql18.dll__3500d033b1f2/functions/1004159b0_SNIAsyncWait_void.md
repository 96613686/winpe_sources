# SNIAsyncWait(void *)

- ea: `0x1004159b0`
- end: `0x100415ae9`
- name: `?SNIAsyncWait@@YAKPEAX@Z`
- size: `313`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1004159b0`
- `0x100545d84`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!GetQueuedCompletionStatus` at `0x100415a44`
- `KERNEL32!GetQueuedCompletionStatus` at `0x100415a44`
- `KERNEL32!GetLastError` at `0x100415a4e`
- `KERNEL32!GetLastError` at `0x100415a4e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SNIAsyncWait(void *a1)
{
  DWORD LastError; // ebx
  DWORD dwMilliseconds[2]; // [rsp+20h] [rbp-30h]
  unsigned __int64 CompletionKey; // [rsp+48h] [rbp-8h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+68h] [rbp+18h] BYREF
  LPOVERLAPPED Overlapped; // [rsp+70h] [rbp+20h] BYREF
  __int64 v7; // [rsp+78h] [rbp+28h] BYREF

  v7 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && *(_QWORD *)&::dwMilliseconds && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *, _QWORD, _QWORD))off_1005D39F0)(
      bidID,
      0,
      0,
      &v7,
      *(_QWORD *)&::dwMilliseconds,
      0);
  while ( 1 )
  {
    while ( 1 )
    {
      Overlapped = 0;
      NumberOfBytesTransferred = 0;
      LastError = 0;
      if ( !GetQueuedCompletionStatus(
              ghIoCompletionPort,
              &NumberOfBytesTransferred,
              &CompletionKey,
              &Overlapped,
              0xFFFFFFFF) )
        LastError = GetLastError();
      if ( !Overlapped )
        break;
      Overlapped[1].OffsetHigh = LastError;
      Overlapped[1].Offset = NumberOfBytesTransferred;
      ((void (*)(void))Overlapped[1].Internal)();
    }
    if ( g_fTerminate )
      break;
    if ( (bidGblFlags & 2) != 0 && off_1005E4778[0] && bidID != -1 )
      ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, unsigned __int64))off_1005D39E0)(
        bidID,
        0,
        2718720,
        off_1005E4778[0],
        (unsigned __int64)Overlapped & *(_QWORD *)dwMilliseconds);
  }
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v7);
  return 0;
}

```

## disassembly

```asm
0x1004159b0  push    rbp
0x1004159b2  mov     rbp, rsp
0x1004159b5  sub     rsp, 50h
0x1004159b9  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFEh
0x1004159c1  mov     [rsp+50h+arg_0], rbx
0x1004159c6  or      [rbp+arg_18], 0FFFFFFFFFFFFFFFFh
0x1004159cb  mov     eax, cs:_bidGblFlags
0x1004159d1  mov     ecx, 20004h
0x1004159d6  and     eax, ecx
0x1004159d8  cmp     eax, ecx
0x1004159da  jnz     short loc_100415A21
0x1004159dc  mov     rax, cs:dwMilliseconds
0x1004159e3  test    rax, rax
0x1004159e6  jz      short loc_100415A21
0x1004159e8  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x1004159f0  jz      short loc_100415A21
0x1004159f2  mov     rax, cs:off_1005D39F0
0x1004159f9  and     [rsp+50h+var_28], 0
0x1004159ff  mov     rcx, cs:dwMilliseconds
0x100415a06  mov     qword ptr [rsp+50h+dwMilliseconds], rcx; dwMilliseconds
0x100415a0b  lea     r9, [rbp+arg_18]
0x100415a0f  xor     r8d, r8d
0x100415a12  xor     edx, edx
0x100415a14  mov     rcx, cs:_bidID
0x100415a1b  call    cs:__guard_dispatch_icall_fptr
0x100415a21  and     [rbp+Overlapped], 0
0x100415a26  and     [rbp+NumberOfBytesTransferred], 0
0x100415a2a  xor     ebx, ebx
0x100415a2c  or      [rsp+50h+dwMilliseconds], 0FFFFFFFFh
0x100415a31  lea     r9, [rbp+Overlapped]; lpOverlapped
0x100415a35  lea     r8, [rbp+CompletionKey]; lpCompletionKey
0x100415a39  lea     rdx, [rbp+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x100415a3d  mov     rcx, cs:?ghIoCompletionPort@@3PEAXEA; CompletionPort
0x100415a44  call    cs:__imp_GetQueuedCompletionStatus
0x100415a4a  test    eax, eax
0x100415a4c  jnz     short loc_100415A56
0x100415a4e  call    cs:__imp_GetLastError
0x100415a54  mov     ebx, eax
0x100415a56  mov     rcx, [rbp+Overlapped]
0x100415a5a  test    rcx, rcx
0x100415a5d  jnz     short loc_100415AB3
0x100415a5f  cmp     cs:?g_fTerminate@@3_NA, cl; bool g_fTerminate
0x100415a65  jnz     short loc_100415AD3
0x100415a67  test    byte ptr cs:_bidGblFlags, 2
0x100415a6e  jz      short loc_100415A21
0x100415a70  mov     rax, cs:off_1005E4778; "<SNIAsyncWait|ERR|SNI> System call GetQ"...
0x100415a77  test    rax, rax
0x100415a7a  jz      short loc_100415A21
0x100415a7c  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x100415a84  jz      short loc_100415A21
0x100415a86  mov     rax, cs:off_1005D39E0
0x100415a8d  and     qword ptr [rsp+50h+dwMilliseconds], rcx
0x100415a92  mov     r9, cs:off_1005E4778; "<SNIAsyncWait|ERR|SNI> System call GetQ"...
0x100415a99  xor     edx, edx
0x100415a9b  mov     r8d, 297C00h
0x100415aa1  mov     rcx, cs:_bidID
0x100415aa8  call    cs:__guard_dispatch_icall_fptr
0x100415aae  jmp     loc_100415A21
0x100415ab3  mov     [rcx+34h], ebx
0x100415ab6  mov     rcx, [rbp+Overlapped]
0x100415aba  mov     eax, [rbp+NumberOfBytesTransferred]
0x100415abd  mov     [rcx+30h], eax
0x100415ac0  mov     rcx, [rbp+Overlapped]
0x100415ac4  mov     rax, [rcx+20h]
0x100415ac8  call    cs:__guard_dispatch_icall_fptr
0x100415ace  jmp     loc_100415A21
0x100415ad3  lea     rcx, [rbp+arg_18]; this
0x100415ad7  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x100415adc  xor     eax, eax
0x100415ade  mov     rbx, [rsp+50h+arg_0]
0x100415ae3  add     rsp, 50h
0x100415ae7  pop     rbp
0x100415ae8  retn
```
