# PostNotificationRemoveLine

- ea: `0x18000caac`
- end: `0x18000cb73`
- name: `PostNotificationRemoveLine`
- size: `199`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000cb80`

## callees

- `0x18000caac`
- `0x18000d92c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000cac0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000cafa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000cac0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000cafa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cb1c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cb1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cadc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cb05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cb4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cadc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cb05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cb4a`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x18000cb40`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x18000cb40`

## string_xrefs

- `0x18000cac8`: `PostNotificationRemoveLine: %d`
- `0x18000cae4`: `PostNotificationRemovePort: failed to allocate`
- `0x18000cb0b`: `PostNotificationRemovePort: failed to allocate`
- `0x18000cb50`: `PostNotificationRemovePort: Failed to post the notification. %d`
- `0x18000cb5c`: `PostNotificationRemovePort: Posted 0x%x`

## pseudocode

```c
HLOCAL __fastcall PostNotificationRemoveLine(int a1)
{
  struct _OVERLAPPED *v2; // rbx
  _DWORD *v4; // rax
  const CHAR *v5; // rcx
  HANDLE v6; // rcx

  v2 = (struct _OVERLAPPED *)LocalAlloc(0x40u, 0x38u);
  RasTapiTrace("PostNotificationRemoveLine: %d");
  if ( !v2 )
  {
    GetLastError();
    return (HLOCAL)RasTapiTrace("PostNotificationRemovePort: failed to allocate");
  }
  v4 = LocalAlloc(0x40u, 4u);
  if ( !v4 )
  {
    GetLastError();
    v5 = "PostNotificationRemovePort: failed to allocate";
LABEL_5:
    RasTapiTrace(v5);
    return LocalFree(v2);
  }
  v6 = g_hIoCompletionPort;
  *v4 = a1;
  LODWORD(v2[1].Internal) = 8;
  v2[1].InternalHigh = (ULONG_PTR)v4;
  if ( !PostQueuedCompletionStatus(v6, 0, 0, v2) )
  {
    GetLastError();
    v5 = "PostNotificationRemovePort: Failed to post the notification. %d";
    goto LABEL_5;
  }
  return (HLOCAL)RasTapiTrace("PostNotificationRemovePort: Posted 0x%x");
}

```

## disassembly

```asm
0x18000caac  mov     [rsp+arg_0], rbx
0x18000cab1  push    rdi
0x18000cab2  sub     rsp, 20h
0x18000cab6  mov     edx, 38h ; '8'; uBytes
0x18000cabb  mov     edi, ecx
0x18000cabd  lea     ecx, [rdx+8]; uFlags
0x18000cac0  call    cs:__imp_LocalAlloc
0x18000cac6  mov     edx, edi
0x18000cac8  lea     rcx, aPostnotificati_8; "PostNotificationRemoveLine: %d"
0x18000cacf  mov     rbx, rax
0x18000cad2  call    RasTapiTrace
0x18000cad7  test    rbx, rbx
0x18000cada  jnz     short loc_18000CAF2
0x18000cadc  call    cs:__imp_GetLastError
0x18000cae2  mov     edx, eax
0x18000cae4  lea     rcx, aPostnotificati_2; "PostNotificationRemovePort: failed to a"...
0x18000caeb  call    RasTapiTrace
0x18000caf0  jmp     short loc_18000CB68
0x18000caf2  mov     edx, 4; uBytes
0x18000caf7  lea     ecx, [rdx+3Ch]; uFlags
0x18000cafa  call    cs:__imp_LocalAlloc
0x18000cb00  test    rax, rax
0x18000cb03  jnz     short loc_18000CB24
0x18000cb05  call    cs:__imp_GetLastError
0x18000cb0b  lea     rcx, aPostnotificati_2; "PostNotificationRemovePort: failed to a"...
0x18000cb12  mov     edx, eax
0x18000cb14  call    RasTapiTrace
0x18000cb19  mov     rcx, rbx; hMem
0x18000cb1c  call    cs:__imp_LocalFree
0x18000cb22  jmp     short loc_18000CB68
0x18000cb24  mov     rcx, cs:g_hIoCompletionPort; CompletionPort
0x18000cb2b  mov     r9, rbx; lpOverlapped
0x18000cb2e  mov     [rax], edi
0x18000cb30  xor     r8d, r8d; dwCompletionKey
0x18000cb33  xor     edx, edx; dwNumberOfBytesTransferred
0x18000cb35  mov     dword ptr [rbx+20h], 8
0x18000cb3c  mov     [rbx+28h], rax
0x18000cb40  call    cs:__imp_PostQueuedCompletionStatus
0x18000cb46  test    eax, eax
0x18000cb48  jnz     short loc_18000CB59
0x18000cb4a  call    cs:__imp_GetLastError
0x18000cb50  lea     rcx, aPostnotificati_0; "PostNotificationRemovePort: Failed to p"...
0x18000cb57  jmp     short loc_18000CB12
0x18000cb59  mov     rdx, rbx
0x18000cb5c  lea     rcx, aPostnotificati_7; "PostNotificationRemovePort: Posted 0x%x"
0x18000cb63  call    RasTapiTrace
0x18000cb68  mov     rbx, [rsp+28h+arg_0]
0x18000cb6d  add     rsp, 20h
0x18000cb71  pop     rdi
0x18000cb72  retn
```
