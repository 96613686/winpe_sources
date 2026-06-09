# PostNotificationCompletion

- ea: `0x18000c918`
- end: `0x18000c96e`
- name: `PostNotificationCompletion`
- size: `86`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000272c`
- `0x18000cb80`
- `0x180014240`

## callees

- `0x18000c918`
- `0x18000d92c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c955`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c955`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x18000c94b`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x18000c94b`

## string_xrefs

- `0x18000c928`: `PostNotificationCompletion: NULL completion port`
- `0x18000c95d`: `PostNotificationCompletion:PostQueuedCompletionStatus failed. 0x%x`

## pseudocode

```c
int __fastcall PostNotificationCompletion(__int64 a1)
{
  int result; // eax

  if ( !*(_QWORD *)(a1 + 240) )
    return RasTapiTrace("PostNotificationCompletion: NULL completion port");
  result = PostQueuedCompletionStatus(*(HANDLE *)(a1 + 240), 0, *(unsigned int *)(a1 + 248), (LPOVERLAPPED)(a1 + 896));
  if ( !result )
  {
    GetLastError();
    return RasTapiTrace("PostNotificationCompletion:PostQueuedCompletionStatus failed. 0x%x");
  }
  return result;
}

```

## disassembly

```asm
0x18000c918  sub     rsp, 28h
0x18000c91c  mov     rax, [rcx+0F0h]
0x18000c923  test    rax, rax
0x18000c926  jnz     short loc_18000C938
0x18000c928  lea     rcx, aPostnotificati_5; "PostNotificationCompletion: NULL comple"...
0x18000c92f  add     rsp, 28h
0x18000c933  jmp     RasTapiTrace
0x18000c938  mov     r8d, [rcx+0F8h]; dwCompletionKey
0x18000c93f  lea     r9, [rcx+380h]; lpOverlapped
0x18000c946  mov     rcx, rax; CompletionPort
0x18000c949  xor     edx, edx; dwNumberOfBytesTransferred
0x18000c94b  call    cs:__imp_PostQueuedCompletionStatus
0x18000c951  test    eax, eax
0x18000c953  jnz     short loc_18000C969
0x18000c955  call    cs:__imp_GetLastError
0x18000c95b  mov     edx, eax
0x18000c95d  lea     rcx, aPostnotificati; "PostNotificationCompletion:PostQueuedCo"...
0x18000c964  call    RasTapiTrace
0x18000c969  add     rsp, 28h
0x18000c96d  retn
```
