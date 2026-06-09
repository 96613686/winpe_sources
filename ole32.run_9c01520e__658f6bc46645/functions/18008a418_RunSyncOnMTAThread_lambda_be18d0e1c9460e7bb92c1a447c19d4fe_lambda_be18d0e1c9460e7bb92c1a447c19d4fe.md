# RunSyncOnMTAThread<_lambda_be18d0e1c9460e7bb92c1a447c19d4fe_>(_lambda_be18d0e1c9460e7bb92c1a447c19d4fe_)

- ea: `0x18008a418`
- end: `0x18008a4ae`
- name: `??$RunSyncOnMTAThread@V_lambda_be18d0e1c9460e7bb92c1a447c19d4fe_@@@@YAJV_lambda_be18d0e1c9460e7bb92c1a447c19d4fe_@@@Z`
- size: `150`
- prototype: `HRESULT __fastcall(CClipboardBroker::SetClipboard::__l34::<lambda_be18d0e1c9460e7bb92c1a447c19d4fe> operation)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001dbc0`

## callees

- `0x18008a418`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a456`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a456`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18008a477`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18008a477`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18008a442`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18008a442`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18008a497`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18008a497`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18008a488`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18008a488`

## pseudocode

```c
__int64 __fastcall RunSyncOnMTAThread<_lambda_be18d0e1c9460e7bb92c1a447c19d4fe_>(
        CClipboardBroker::SetClipboard::__l34::<lambda_be18d0e1c9460e7bb92c1a447c19d4fe> *operation)
{
  _TP_WORK *v1; // rax
  _TP_WORK *v2; // rbx
  signed int LastError; // eax
  RunSyncOnMTAThread::__l2::<lambda_9b16054ad48e172bb5548ecd4adf6ab4> hrHandlerOverOperation; // [rsp+20h] [rbp-18h] BYREF
  HRESULT hr; // [rsp+40h] [rbp+8h] BYREF

  hrHandlerOverOperation.operation = operation;
  hrHandlerOverOperation.hr = &hr;
  hr = 0;
  v1 = CreateThreadpoolWork(MTAThreadPoolWorker__lambda_9b16054ad48e172bb5548ecd4adf6ab4_, &hrHandlerOverOperation, 0);
  v2 = v1;
  if ( v1 )
  {
    SubmitThreadpoolWork(v1);
    WaitForThreadpoolWorkCallbacks(v2, 0);
    CloseThreadpoolWork(v2);
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
    return (unsigned int)LastError;
  }
  return (unsigned int)hr;
}

```

## disassembly

```asm
0x18008a418  mov     r11, rsp
0x18008a41b  push    rbx
0x18008a41c  sub     rsp, 30h
0x18008a420  mov     [r11-18h], operation
0x18008a424  lea     rax, [r11+8]
0x18008a428  lea     operation, MTAThreadPoolWorker__lambda_9b16054ad48e172bb5548ecd4adf6ab4___; pfnwk
0x18008a42f  mov     [r11-10h], rax
0x18008a433  xor     r8d, r8d; pcbe
0x18008a436  mov     [rsp+38h+hr], 0
0x18008a43e  lea     rdx, [r11-18h]; pv
0x18008a442  call    cs:__imp_CreateThreadpoolWork
0x18008a449  nop     dword ptr [rax+rax+00h]
0x18008a44e  mov     rbx, rax
0x18008a451  test    rax, rax
0x18008a454  jnz     short loc_18008A474
0x18008a456  call    cs:__imp_GetLastError
0x18008a45d  nop     dword ptr [rax+rax+00h]
0x18008a462  test    eax, eax
0x18008a464  jle     short loc_18008A46E
0x18008a466  movzx   eax, ax
0x18008a469  or      eax, 80070000h
0x18008a46e  mov     [rsp+38h+hr], eax
0x18008a472  jmp     short loc_18008A4A3
0x18008a474  mov     operation, rbx; pwk
0x18008a477  call    cs:__imp_SubmitThreadpoolWork
0x18008a47e  nop     dword ptr [rax+rax+00h]
0x18008a483  xor     edx, edx; fCancelPendingCallbacks
0x18008a485  mov     operation, rbx; pwk
0x18008a488  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18008a48f  nop     dword ptr [rax+rax+00h]
0x18008a494  mov     operation, rbx; pwk
0x18008a497  call    cs:__imp_CloseThreadpoolWork
0x18008a49e  nop     dword ptr [rax+rax+00h]
0x18008a4a3  mov     eax, [rsp+38h+hr]
0x18008a4a7  add     rsp, 30h
0x18008a4ab  pop     rbx
0x18008a4ac  retn
```
