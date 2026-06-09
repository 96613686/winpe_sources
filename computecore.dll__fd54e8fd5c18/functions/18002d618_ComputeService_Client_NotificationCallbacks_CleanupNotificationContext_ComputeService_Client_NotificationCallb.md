# ComputeService::Client::NotificationCallbacks::CleanupNotificationContext(ComputeService::Client::NotificationCallbacks::NotificationContext *)

- ea: `0x18002d618`
- end: `0x18002d702`
- name: `?CleanupNotificationContext@NotificationCallbacks@Client@ComputeService@@CAXPEAUNotificationContext@123@@Z`
- size: `234`
- prototype: `void __fastcall(struct ComputeService::Client::NotificationCallbacks::NotificationContext *)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002d5e0`
- `0x18002dd9c`

## callees

- `0x18002d618`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d680`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d6e4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d680`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d6e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d651`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d6b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d651`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d6b5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002d642`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002d661`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002d6a6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002d6c5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002d642`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002d661`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002d6a6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002d6c5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18002d633`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18002d66f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18002d697`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18002d6d3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18002d633`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18002d66f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18002d697`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18002d6d3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18002d678`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18002d6dc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18002d678`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18002d6dc`

## pseudocode

```c
void __fastcall ComputeService::Client::NotificationCallbacks::CleanupNotificationContext(PTP_WAIT *a1)
{
  struct _TP_WAIT *v2; // rsi
  DWORD LastError; // ebx
  struct _TP_WAIT *v4; // rsi
  DWORD v5; // ebx

  WaitForThreadpoolWaitCallbacks(a1[5], 1);
  SetThreadpoolWait(a1[5], 0, 0);
  v2 = a1[5];
  if ( v2 )
  {
    LastError = GetLastError();
    SetThreadpoolWait(v2, 0, 0);
    WaitForThreadpoolWaitCallbacks(v2, 1);
    CloseThreadpoolWait(v2);
    SetLastError(LastError);
  }
  a1[5] = 0;
  WaitForThreadpoolWaitCallbacks(a1[7], 1);
  SetThreadpoolWait(a1[7], 0, 0);
  v4 = a1[7];
  if ( v4 )
  {
    v5 = GetLastError();
    SetThreadpoolWait(v4, 0, 0);
    WaitForThreadpoolWaitCallbacks(v4, 1);
    CloseThreadpoolWait(v4);
    SetLastError(v5);
  }
  a1[7] = 0;
}

```

## disassembly

```asm
0x18002d618  mov     [rsp+arg_0], rbx
0x18002d61d  mov     [rsp+arg_8], rsi
0x18002d622  push    rdi
0x18002d623  sub     rsp, 20h
0x18002d627  mov     rdi, rcx
0x18002d62a  mov     edx, 1; fCancelPendingCallbacks
0x18002d62f  mov     rcx, [rcx+28h]; pwa
0x18002d633  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18002d639  mov     rcx, [rdi+28h]; pwa
0x18002d63d  xor     r8d, r8d; pftTimeout
0x18002d640  xor     edx, edx; h
0x18002d642  call    cs:__imp_SetThreadpoolWait
0x18002d648  mov     rsi, [rdi+28h]
0x18002d64c  test    rsi, rsi
0x18002d64f  jz      short loc_18002D686
0x18002d651  call    cs:__imp_GetLastError
0x18002d657  xor     r8d, r8d; pftTimeout
0x18002d65a  xor     edx, edx; h
0x18002d65c  mov     rcx, rsi; pwa
0x18002d65f  mov     ebx, eax
0x18002d661  call    cs:__imp_SetThreadpoolWait
0x18002d667  mov     edx, 1; fCancelPendingCallbacks
0x18002d66c  mov     rcx, rsi; pwa
0x18002d66f  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18002d675  mov     rcx, rsi; pwa
0x18002d678  call    cs:__imp_CloseThreadpoolWait
0x18002d67e  mov     ecx, ebx; dwErrCode
0x18002d680  call    cs:__imp_SetLastError
0x18002d686  mov     qword ptr [rdi+28h], 0
0x18002d68e  mov     edx, 1; fCancelPendingCallbacks
0x18002d693  mov     rcx, [rdi+38h]; pwa
0x18002d697  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18002d69d  mov     rcx, [rdi+38h]; pwa
0x18002d6a1  xor     r8d, r8d; pftTimeout
0x18002d6a4  xor     edx, edx; h
0x18002d6a6  call    cs:__imp_SetThreadpoolWait
0x18002d6ac  mov     rsi, [rdi+38h]
0x18002d6b0  test    rsi, rsi
0x18002d6b3  jz      short loc_18002D6EA
0x18002d6b5  call    cs:__imp_GetLastError
0x18002d6bb  xor     r8d, r8d; pftTimeout
0x18002d6be  xor     edx, edx; h
0x18002d6c0  mov     rcx, rsi; pwa
0x18002d6c3  mov     ebx, eax
0x18002d6c5  call    cs:__imp_SetThreadpoolWait
0x18002d6cb  mov     edx, 1; fCancelPendingCallbacks
0x18002d6d0  mov     rcx, rsi; pwa
0x18002d6d3  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18002d6d9  mov     rcx, rsi; pwa
0x18002d6dc  call    cs:__imp_CloseThreadpoolWait
0x18002d6e2  mov     ecx, ebx; dwErrCode
0x18002d6e4  call    cs:__imp_SetLastError
0x18002d6ea  mov     rbx, [rsp+28h+arg_0]
0x18002d6ef  mov     rsi, [rsp+28h+arg_8]
0x18002d6f4  mov     qword ptr [rdi+38h], 0
0x18002d6fc  add     rsp, 20h
0x18002d700  pop     rdi
0x18002d701  retn
```
