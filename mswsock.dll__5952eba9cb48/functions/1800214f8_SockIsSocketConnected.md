# SockIsSocketConnected

- ea: `0x1800214f8`
- end: `0x180021615`
- name: `SockIsSocketConnected`
- size: `285`
- prototype: ``
- caller_count: `11`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000203c`
- `0x180002240`
- `0x18000faa0`
- `0x180010030`
- `0x180011e60`
- `0x1800182d0`
- `0x180018ba0`
- `0x18001bc7c`
- `0x180021800`
- `0x180026eb8`
- `0x180027140`

## callees

- `0x180018ea0`
- `0x1800214f8`

## import_xrefs

- `ntdll!NtRemoveIoCompletion` at `0x180021578`
- `ntdll!NtRemoveIoCompletion` at `0x180021578`
- `ntdll!NtSetIoCompletion` at `0x1800215e3`
- `ntdll!NtSetIoCompletion` at `0x1800215e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021550`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021550`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800215a4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800215f2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800215a4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800215f2`

## pseudocode

```c
bool __fastcall SockIsSocketConnected(__int64 a1)
{
  __int64 v2; // rax
  NTSTATUS v3; // esi
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+30h] [rbp-10h] BYREF
  PVOID CompletionKey; // [rsp+60h] [rbp+20h] BYREF
  PVOID CompletionContext; // [rsp+68h] [rbp+28h] BYREF
  union _LARGE_INTEGER Timeout; // [rsp+70h] [rbp+30h] BYREF

  Timeout.QuadPart = 0;
  IoStatusBlock = 0;
  CompletionContext = 0;
  CompletionKey = 0;
  while ( 1 )
  {
    v2 = *(_QWORD *)(a1 + 200);
    if ( !v2 || *(_DWORD *)(v2 + 16) == 259 )
      break;
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 224));
    v3 = NtRemoveIoCompletion(SockAsyncQueuePort, &CompletionKey, &CompletionContext, &IoStatusBlock, &Timeout);
    if ( !v3 )
    {
      if ( CompletionKey == (PVOID)-1LL )
      {
        NtSetIoCompletion(SockAsyncQueuePort, (PVOID)0xFFFFFFFFFFFFFFFFLL, (PVOID)0xFFFFFFFFFFFFFFFFLL, 0, 0);
        EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 224));
        return *(_DWORD *)(a1 + 24) == 3;
      }
      SockHandleAsyncIndication(CompletionKey, CompletionContext, &IoStatusBlock);
    }
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 224));
    if ( v3 == 258 )
      Timeout.QuadPart = -100000;
  }
  return *(_DWORD *)(a1 + 24) == 3;
}

```

## disassembly

```asm
0x1800214f8  mov     [rsp-18h+arg_18], rbx
0x1800214fd  push    rbp
0x1800214fe  push    rsi
0x1800214ff  push    rdi
0x180021500  mov     rbp, rsp
0x180021503  sub     rsp, 40h
0x180021507  xorps   xmm0, xmm0
0x18002150a  mov     qword ptr [rbp+arg_10], 0
0x180021512  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x180021516  mov     rbx, rcx
0x180021519  mov     [rbp+CompletionContext], 0
0x180021521  mov     [rbp+CompletionKey], 0
0x180021529  mov     rax, [rbx+0C8h]
0x180021530  test    rax, rax
0x180021533  jz      loc_1800215FE
0x180021539  cmp     dword ptr [rax+10h], 103h
0x180021540  jz      loc_1800215FE
0x180021546  lea     rdi, [rbx+0E0h]
0x18002154d  mov     rcx, rdi; lpCriticalSection
0x180021550  call    cs:__imp_LeaveCriticalSection
0x180021557  nop     dword ptr [rax+rax+00h]
0x18002155c  mov     rcx, cs:SockAsyncQueuePort; IoCompletionHandle
0x180021563  lea     rax, [rbp+arg_10]
0x180021567  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x18002156b  mov     [rsp+40h+Timeout], rax; Timeout
0x180021570  lea     r8, [rbp+CompletionContext]; CompletionContext
0x180021574  lea     rdx, [rbp+CompletionKey]; CompletionKey
0x180021578  call    cs:__imp_NtRemoveIoCompletion
0x18002157f  nop     dword ptr [rax+rax+00h]
0x180021584  mov     esi, eax
0x180021586  test    eax, eax
0x180021588  jnz     short loc_1800215A1
0x18002158a  mov     rcx, [rbp+CompletionKey]
0x18002158e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180021592  jz      short loc_1800215C9
0x180021594  mov     rdx, [rbp+CompletionContext]
0x180021598  lea     r8, [rbp+IoStatusBlock]
0x18002159c  call    SockHandleAsyncIndication
0x1800215a1  mov     rcx, rdi; lpCriticalSection
0x1800215a4  call    cs:__imp_EnterCriticalSection
0x1800215ab  nop     dword ptr [rax+rax+00h]
0x1800215b0  cmp     esi, 102h
0x1800215b6  jnz     loc_180021529
0x1800215bc  mov     qword ptr [rbp+arg_10], 0FFFFFFFFFFFE7960h
0x1800215c4  jmp     loc_180021529
0x1800215c9  mov     rcx, cs:SockAsyncQueuePort; IoCompletionPortHandle
0x1800215d0  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionContext
0x1800215d4  or      rdx, r8; CompletionKey
0x1800215d7  mov     [rsp+40h+Timeout], 0; CompletionInformation
0x1800215e0  xor     r9d, r9d; CompletionStatus
0x1800215e3  call    cs:__imp_NtSetIoCompletion
0x1800215ea  nop     dword ptr [rax+rax+00h]
0x1800215ef  mov     rcx, rdi; lpCriticalSection
0x1800215f2  call    cs:__imp_EnterCriticalSection
0x1800215f9  nop     dword ptr [rax+rax+00h]
0x1800215fe  mov     eax, [rbx+18h]
0x180021601  cmp     eax, 3
0x180021604  mov     rbx, [rsp+40h+arg_18]
0x180021609  setz    al
0x18002160c  add     rsp, 40h
0x180021610  pop     rdi
0x180021611  pop     rsi
0x180021612  pop     rbp
0x180021613  retn
```
