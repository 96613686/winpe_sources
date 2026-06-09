# PostNotificationNewPort

- ea: `0x18000c974`
- end: `0x18000caa4`
- name: `PostNotificationNewPort`
- size: `304`
- prototype: `__int64 __fastcall(HLOCAL hMem)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000212c`
- `0x18000dc2c`

## callees

- `0x18000c974`
- `0x18000d92c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c99f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c9c5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c99f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c9c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ca61`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ca6f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ca7d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ca61`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ca6f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ca7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ca4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ca4a`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x18000ca40`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x18000ca40`

## pseudocode

```c
HLOCAL __fastcall PostNotificationNewPort(HLOCAL hMem)
{
  struct _OVERLAPPED *v2; // rdi
  HLOCAL result; // rax
  char *v4; // rax
  char *v5; // rbx
  const char *v6; // r8
  __int64 v7; // rax
  _BYTE *v8; // rcx
  __int64 v9; // rdx
  _BYTE *v10; // rax
  HANDLE v11; // rcx

  RasTapiTrace("PostNotificationNewPort %s");
  v2 = (struct _OVERLAPPED *)LocalAlloc(0x40u, 0x38u);
  if ( v2 )
  {
    v4 = (char *)LocalAlloc(0x40u, 0x18u);
    v5 = v4;
    if ( v4 )
    {
      *(_QWORD *)v4 = hMem;
      v6 = "rastapi";
      v7 = 2147483646;
      v8 = v5 + 8;
      v9 = 16;
      do
      {
        if ( !v7 )
          break;
        if ( !*v6 )
          break;
        *v8++ = *v6++;
        --v7;
        --v9;
      }
      while ( v9 );
      v10 = v8 - 1;
      if ( v9 )
        v10 = v8;
      v11 = g_hIoCompletionPort;
      *v10 = 0;
      LODWORD(v2[1].Internal) = 7;
      v2[1].InternalHigh = (ULONG_PTR)v5;
      if ( PostQueuedCompletionStatus(v11, 0, 0, v2) )
        return (HLOCAL)RasTapiTrace("PostNotificationNewPort: Posted 0x%x");
      GetLastError();
      RasTapiTrace("PostNotificationNewPort: Failed to Post notification. %d");
    }
    else
    {
      RasTapiTrace("PostNotificationNewPort: Failed to allocate NEW_PORT_NOTIF");
    }
    result = LocalFree(v2);
    if ( v5 )
      result = LocalFree(v5);
  }
  else
  {
    result = (HLOCAL)RasTapiTrace("PostNotificationNewPort: Failed to allocate ov.");
  }
  if ( hMem )
    return LocalFree(hMem);
  return result;
}

```

## disassembly

```asm
0x18000c974  mov     [rsp+arg_0], rbx
0x18000c979  mov     [rsp+arg_8], rsi
0x18000c97e  push    rdi
0x18000c97f  sub     rsp, 20h
0x18000c983  mov     rsi, rcx
0x18000c986  mov     rdx, rcx
0x18000c989  lea     rcx, aPostnotificati_9; "PostNotificationNewPort %s"
0x18000c990  call    RasTapiTrace
0x18000c995  mov     edx, 38h ; '8'; uBytes
0x18000c99a  lea     ebx, [rdx+8]
0x18000c99d  mov     ecx, ebx; uFlags
0x18000c99f  call    cs:__imp_LocalAlloc
0x18000c9a5  mov     rdi, rax
0x18000c9a8  test    rax, rax
0x18000c9ab  jnz     short loc_18000C9BE
0x18000c9ad  lea     rcx, aPostnotificati_4; "PostNotificationNewPort: Failed to allo"...
0x18000c9b4  call    RasTapiTrace
0x18000c9b9  jmp     loc_18000CA75
0x18000c9be  mov     edx, 18h; uBytes
0x18000c9c3  mov     ecx, ebx; uFlags
0x18000c9c5  call    cs:__imp_LocalAlloc
0x18000c9cb  mov     rbx, rax
0x18000c9ce  test    rax, rax
0x18000c9d1  jnz     short loc_18000C9E1
0x18000c9d3  lea     rcx, aPostnotificati_1; "PostNotificationNewPort: Failed to allo"...
0x18000c9da  call    RasTapiTrace
0x18000c9df  jmp     short loc_18000CA5E
0x18000c9e1  mov     [rax], rsi
0x18000c9e4  lea     r8, aRastapi; "rastapi"
0x18000c9eb  mov     eax, 7FFFFFFEh
0x18000c9f0  lea     rcx, [rbx+8]
0x18000c9f4  mov     edx, 10h
0x18000c9f9  test    rax, rax
0x18000c9fc  jz      short loc_18000CA18
0x18000c9fe  mov     r9b, [r8]
0x18000ca01  test    r9b, r9b
0x18000ca04  jz      short loc_18000CA18
0x18000ca06  mov     [rcx], r9b
0x18000ca09  inc     r8
0x18000ca0c  inc     rcx
0x18000ca0f  dec     rax
0x18000ca12  sub     rdx, 1
0x18000ca16  jnz     short loc_18000C9F9
0x18000ca18  test    rdx, rdx
0x18000ca1b  lea     rax, [rcx-1]
0x18000ca1f  mov     r9, rdi; lpOverlapped
0x18000ca22  cmovnz  rax, rcx
0x18000ca26  mov     rcx, cs:g_hIoCompletionPort; CompletionPort
0x18000ca2d  xor     r8d, r8d; dwCompletionKey
0x18000ca30  xor     edx, edx; dwNumberOfBytesTransferred
0x18000ca32  mov     byte ptr [rax], 0
0x18000ca35  mov     dword ptr [rdi+20h], 7
0x18000ca3c  mov     [rdi+28h], rbx
0x18000ca40  call    cs:__imp_PostQueuedCompletionStatus
0x18000ca46  test    eax, eax
0x18000ca48  jnz     short loc_18000CA85
0x18000ca4a  call    cs:__imp_GetLastError
0x18000ca50  mov     edx, eax
0x18000ca52  lea     rcx, aPostnotificati_6; "PostNotificationNewPort: Failed to Post"...
0x18000ca59  call    RasTapiTrace
0x18000ca5e  mov     rcx, rdi; hMem
0x18000ca61  call    cs:__imp_LocalFree
0x18000ca67  test    rbx, rbx
0x18000ca6a  jz      short loc_18000CA75
0x18000ca6c  mov     rcx, rbx; hMem
0x18000ca6f  call    cs:__imp_LocalFree
0x18000ca75  test    rsi, rsi
0x18000ca78  jz      short loc_18000CA94
0x18000ca7a  mov     rcx, rsi; hMem
0x18000ca7d  call    cs:__imp_LocalFree
0x18000ca83  jmp     short loc_18000CA94
0x18000ca85  mov     rdx, rdi
0x18000ca88  lea     rcx, aPostnotificati_3; "PostNotificationNewPort: Posted 0x%x"
0x18000ca8f  call    RasTapiTrace
0x18000ca94  mov     rbx, [rsp+28h+arg_0]
0x18000ca99  mov     rsi, [rsp+28h+arg_8]
0x18000ca9e  add     rsp, 20h
0x18000caa2  pop     rdi
0x18000caa3  retn
```
