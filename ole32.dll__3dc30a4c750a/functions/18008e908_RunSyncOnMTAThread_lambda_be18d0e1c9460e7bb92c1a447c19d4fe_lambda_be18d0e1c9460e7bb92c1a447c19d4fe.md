# RunSyncOnMTAThread<_lambda_be18d0e1c9460e7bb92c1a447c19d4fe_>(_lambda_be18d0e1c9460e7bb92c1a447c19d4fe_)

- ea: `0x18008e908`
- end: `0x18008e97f`
- name: `??$RunSyncOnMTAThread@V_lambda_be18d0e1c9460e7bb92c1a447c19d4fe_@@@@YAJV_lambda_be18d0e1c9460e7bb92c1a447c19d4fe_@@@Z`
- size: `119`
- prototype: `__int64 __fastcall(CClipboardBroker::SetClipboard::__l34::<lambda_be18d0e1c9460e7bb92c1a447c19d4fe> *operation)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800104b0`

## callees

- `0x18008e908`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e940`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e940`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18008e95b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18008e95b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18008e932`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18008e932`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18008e96f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18008e96f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18008e966`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18008e966`

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
0x18008e908  mov     r11, rsp
0x18008e90b  push    rbx
0x18008e90c  sub     rsp, 30h
0x18008e910  mov     [r11-18h], operation
0x18008e914  lea     rax, [r11+8]
0x18008e918  lea     operation, MTAThreadPoolWorker__lambda_9b16054ad48e172bb5548ecd4adf6ab4___; pfnwk
0x18008e91f  mov     [r11-10h], rax
0x18008e923  xor     r8d, r8d; pcbe
0x18008e926  mov     [rsp+38h+hr], 0
0x18008e92e  lea     rdx, [r11-18h]; pv
0x18008e932  call    cs:__imp_CreateThreadpoolWork
0x18008e938  mov     rbx, rax
0x18008e93b  test    rax, rax
0x18008e93e  jnz     short loc_18008E958
0x18008e940  call    cs:__imp_GetLastError
0x18008e946  test    eax, eax
0x18008e948  jle     short loc_18008E952
0x18008e94a  movzx   eax, ax
0x18008e94d  or      eax, 80070000h
0x18008e952  mov     [rsp+38h+hr], eax
0x18008e956  jmp     short loc_18008E975
0x18008e958  mov     operation, rbx; pwk
0x18008e95b  call    cs:__imp_SubmitThreadpoolWork
0x18008e961  xor     edx, edx; fCancelPendingCallbacks
0x18008e963  mov     operation, rbx; pwk
0x18008e966  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18008e96c  mov     operation, rbx; pwk
0x18008e96f  call    cs:__imp_CloseThreadpoolWork
0x18008e975  mov     eax, [rsp+38h+hr]
0x18008e979  add     rsp, 30h
0x18008e97d  pop     rbx
0x18008e97e  retn
```
