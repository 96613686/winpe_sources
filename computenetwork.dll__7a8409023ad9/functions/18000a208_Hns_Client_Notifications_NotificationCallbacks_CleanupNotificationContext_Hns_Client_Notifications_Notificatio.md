# Hns::Client::Notifications::NotificationCallbacks::CleanupNotificationContext(Hns::Client::Notifications::NotificationCallbacks::NotificationContext *)

- ea: `0x18000a208`
- end: `0x18000a2f2`
- name: `?CleanupNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@CAXPEAUNotificationContext@1234@@Z`
- size: `234`
- prototype: `void __fastcall(struct Hns::Client::Notifications::NotificationCallbacks::NotificationContext *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a1d0`
- `0x18000aaa0`

## callees

- `0x18000a208`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000a232`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000a251`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000a296`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000a2b5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000a232`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000a251`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000a296`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000a2b5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000a223`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000a25f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000a287`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000a2c3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000a223`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000a25f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000a287`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000a2c3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000a268`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000a2cc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000a268`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000a2cc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a270`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a2d4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a270`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a2d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a241`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a2a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a241`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a2a5`

## pseudocode

```c
void __fastcall Hns::Client::Notifications::NotificationCallbacks::CleanupNotificationContext(PTP_WAIT *a1)
{
  struct _TP_WAIT *v2; // rsi
  DWORD LastError; // ebx
  struct _TP_WAIT *v4; // rsi
  DWORD v5; // ebx

  WaitForThreadpoolWaitCallbacks(a1[4], 1);
  SetThreadpoolWait(a1[4], 0, 0);
  v2 = a1[4];
  if ( v2 )
  {
    LastError = GetLastError();
    SetThreadpoolWait(v2, 0, 0);
    WaitForThreadpoolWaitCallbacks(v2, 1);
    CloseThreadpoolWait(v2);
    SetLastError(LastError);
  }
  a1[4] = 0;
  WaitForThreadpoolWaitCallbacks(a1[6], 1);
  SetThreadpoolWait(a1[6], 0, 0);
  v4 = a1[6];
  if ( v4 )
  {
    v5 = GetLastError();
    SetThreadpoolWait(v4, 0, 0);
    WaitForThreadpoolWaitCallbacks(v4, 1);
    CloseThreadpoolWait(v4);
    SetLastError(v5);
  }
  a1[6] = 0;
}

```

## disassembly

```asm
0x18000a208  mov     [rsp+arg_0], rbx
0x18000a20d  mov     [rsp+arg_8], rsi
0x18000a212  push    rdi
0x18000a213  sub     rsp, 20h
0x18000a217  mov     rdi, rcx
0x18000a21a  mov     edx, 1; fCancelPendingCallbacks
0x18000a21f  mov     rcx, [rcx+20h]; pwa
0x18000a223  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18000a229  mov     rcx, [rdi+20h]; pwa
0x18000a22d  xor     r8d, r8d; pftTimeout
0x18000a230  xor     edx, edx; h
0x18000a232  call    cs:__imp_SetThreadpoolWait
0x18000a238  mov     rsi, [rdi+20h]
0x18000a23c  test    rsi, rsi
0x18000a23f  jz      short loc_18000A276
0x18000a241  call    cs:__imp_GetLastError
0x18000a247  xor     r8d, r8d; pftTimeout
0x18000a24a  xor     edx, edx; h
0x18000a24c  mov     rcx, rsi; pwa
0x18000a24f  mov     ebx, eax
0x18000a251  call    cs:__imp_SetThreadpoolWait
0x18000a257  mov     edx, 1; fCancelPendingCallbacks
0x18000a25c  mov     rcx, rsi; pwa
0x18000a25f  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18000a265  mov     rcx, rsi; pwa
0x18000a268  call    cs:__imp_CloseThreadpoolWait
0x18000a26e  mov     ecx, ebx; dwErrCode
0x18000a270  call    cs:__imp_SetLastError
0x18000a276  mov     qword ptr [rdi+20h], 0
0x18000a27e  mov     edx, 1; fCancelPendingCallbacks
0x18000a283  mov     rcx, [rdi+30h]; pwa
0x18000a287  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18000a28d  mov     rcx, [rdi+30h]; pwa
0x18000a291  xor     r8d, r8d; pftTimeout
0x18000a294  xor     edx, edx; h
0x18000a296  call    cs:__imp_SetThreadpoolWait
0x18000a29c  mov     rsi, [rdi+30h]
0x18000a2a0  test    rsi, rsi
0x18000a2a3  jz      short loc_18000A2DA
0x18000a2a5  call    cs:__imp_GetLastError
0x18000a2ab  xor     r8d, r8d; pftTimeout
0x18000a2ae  xor     edx, edx; h
0x18000a2b0  mov     rcx, rsi; pwa
0x18000a2b3  mov     ebx, eax
0x18000a2b5  call    cs:__imp_SetThreadpoolWait
0x18000a2bb  mov     edx, 1; fCancelPendingCallbacks
0x18000a2c0  mov     rcx, rsi; pwa
0x18000a2c3  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18000a2c9  mov     rcx, rsi; pwa
0x18000a2cc  call    cs:__imp_CloseThreadpoolWait
0x18000a2d2  mov     ecx, ebx; dwErrCode
0x18000a2d4  call    cs:__imp_SetLastError
0x18000a2da  mov     rbx, [rsp+28h+arg_0]
0x18000a2df  mov     rsi, [rsp+28h+arg_8]
0x18000a2e4  mov     qword ptr [rdi+30h], 0
0x18000a2ec  add     rsp, 20h
0x18000a2f0  pop     rdi
0x18000a2f1  retn
```
