# PostDisconnectCompletion

- ea: `0x18000c8bc`
- end: `0x18000c912`
- name: `PostDisconnectCompletion`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000cb80`

## callees

- `0x18000c8bc`
- `0x18000d92c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c8f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c8f9`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x18000c8ef`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x18000c8ef`

## string_xrefs

- `0x18000c8cc`: `PostDisconnectionCompletion: NULL completion port`
- `0x18000c901`: `PostDisconnectCompletion:PostQueuedCompletionStatus failed. 0x%x`

## pseudocode

```c
int __fastcall PostDisconnectCompletion(__int64 a1)
{
  int result; // eax

  if ( !*(_QWORD *)(a1 + 240) )
    return RasTapiTrace("PostDisconnectionCompletion: NULL completion port");
  result = PostQueuedCompletionStatus(*(HANDLE *)(a1 + 240), 0, *(unsigned int *)(a1 + 248), (LPOVERLAPPED)(a1 + 1008));
  if ( !result )
  {
    GetLastError();
    return RasTapiTrace("PostDisconnectCompletion:PostQueuedCompletionStatus failed. 0x%x");
  }
  return result;
}

```

## disassembly

```asm
0x18000c8bc  sub     rsp, 28h
0x18000c8c0  mov     rax, [rcx+0F0h]
0x18000c8c7  test    rax, rax
0x18000c8ca  jnz     short loc_18000C8DC
0x18000c8cc  lea     rcx, aPostdisconnect_0; "PostDisconnectionCompletion: NULL compl"...
0x18000c8d3  add     rsp, 28h
0x18000c8d7  jmp     RasTapiTrace
0x18000c8dc  mov     r8d, [rcx+0F8h]; dwCompletionKey
0x18000c8e3  lea     r9, [rcx+3F0h]; lpOverlapped
0x18000c8ea  mov     rcx, rax; CompletionPort
0x18000c8ed  xor     edx, edx; dwNumberOfBytesTransferred
0x18000c8ef  call    cs:__imp_PostQueuedCompletionStatus
0x18000c8f5  test    eax, eax
0x18000c8f7  jnz     short loc_18000C90D
0x18000c8f9  call    cs:__imp_GetLastError
0x18000c8ff  mov     edx, eax
0x18000c901  lea     rcx, aPostdisconnect; "PostDisconnectCompletion:PostQueuedComp"...
0x18000c908  call    RasTapiTrace
0x18000c90d  add     rsp, 28h
0x18000c911  retn
```
