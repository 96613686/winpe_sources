# SockSanCheckAsyncPort

- ea: `0x180042344`
- end: `0x1800423e5`
- name: `SockSanCheckAsyncPort`
- size: `161`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800423ec`

## callees

- `0x180018ea0`
- `0x180042344`

## import_xrefs

- `ntdll!NtRemoveIoCompletion` at `0x180042384`
- `ntdll!NtRemoveIoCompletion` at `0x180042384`
- `ntdll!NtSetIoCompletion` at `0x1800423d3`
- `ntdll!NtSetIoCompletion` at `0x1800423d3`

## pseudocode

```c
NTSTATUS SockSanCheckAsyncPort()
{
  NTSTATUS result; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+30h] [rbp-18h] BYREF
  PVOID CompletionKey; // [rsp+50h] [rbp+8h] BYREF
  PVOID CompletionContext; // [rsp+58h] [rbp+10h] BYREF

  CompletionContext = 0;
  IoStatusBlock = 0;
  for ( CompletionKey = 0; ; SockHandleAsyncIndication(CompletionKey, CompletionContext, &IoStatusBlock) )
  {
    while ( 1 )
    {
      result = NtRemoveIoCompletion(
                 SockAsyncQueuePort,
                 &CompletionKey,
                 &CompletionContext,
                 &IoStatusBlock,
                 (PLARGE_INTEGER)&Timeout);
      if ( !result )
        break;
      if ( result == 258 )
        return result;
    }
    if ( CompletionKey == (PVOID)-1LL )
      break;
  }
  return NtSetIoCompletion(SockAsyncQueuePort, (PVOID)0xFFFFFFFFFFFFFFFFLL, (PVOID)0xFFFFFFFFFFFFFFFFLL, 0, 0);
}

```

## disassembly

```asm
0x180042344  sub     rsp, 48h
0x180042348  xorps   xmm0, xmm0
0x18004234b  mov     [rsp+48h+CompletionContext], 0
0x180042354  movups  xmmword ptr [rsp+48h+IoStatusBlock], xmm0
0x180042359  mov     [rsp+48h+CompletionKey], 0
0x180042362  mov     rcx, cs:SockAsyncQueuePort; IoCompletionHandle
0x180042369  lea     rax, Timeout
0x180042370  lea     r9, [rsp+48h+IoStatusBlock]; IoStatusBlock
0x180042375  mov     [rsp+48h+Timeout], rax; Timeout
0x18004237a  lea     r8, [rsp+48h+CompletionContext]; CompletionContext
0x18004237f  lea     rdx, [rsp+48h+CompletionKey]; CompletionKey
0x180042384  call    cs:__imp_NtRemoveIoCompletion
0x18004238b  nop     dword ptr [rax+rax+00h]
0x180042390  test    eax, eax
0x180042392  jnz     short loc_1800423B0
0x180042394  mov     rcx, [rsp+48h+CompletionKey]
0x180042399  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18004239d  jz      short loc_1800423B9
0x18004239f  mov     rdx, [rsp+48h+CompletionContext]
0x1800423a4  lea     r8, [rsp+48h+IoStatusBlock]
0x1800423a9  call    SockHandleAsyncIndication
0x1800423ae  jmp     short loc_180042362
0x1800423b0  cmp     eax, 102h
0x1800423b5  jnz     short loc_180042362
0x1800423b7  jmp     short loc_1800423DF
0x1800423b9  mov     rcx, cs:SockAsyncQueuePort; IoCompletionPortHandle
0x1800423c0  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionContext
0x1800423c4  or      rdx, r8; CompletionKey
0x1800423c7  mov     [rsp+48h+Timeout], 0; CompletionInformation
0x1800423d0  xor     r9d, r9d; CompletionStatus
0x1800423d3  call    cs:__imp_NtSetIoCompletion
0x1800423da  nop     dword ptr [rax+rax+00h]
0x1800423df  add     rsp, 48h
0x1800423e3  retn
```
