# RunSyncOnMTAThread<_lambda_ceb8f1db0b0f2dc512542b4e425d8ca5_>(_lambda_ceb8f1db0b0f2dc512542b4e425d8ca5_)

- ea: `0x18008e988`
- end: `0x18008ea07`
- name: `??$RunSyncOnMTAThread@V_lambda_ceb8f1db0b0f2dc512542b4e425d8ca5_@@@@YAJV_lambda_ceb8f1db0b0f2dc512542b4e425d8ca5_@@@Z`
- size: `127`
- prototype: `__int64 __fastcall(CClipboardBroker::SetClipboard::__l49::<lambda_ceb8f1db0b0f2dc512542b4e425d8ca5> operation)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800104b0`

## callees

- `0x18008e988`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e9c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e9c8`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18008e9e3`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18008e9e3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18008e9ba`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18008e9ba`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18008e9f7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18008e9f7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18008e9ee`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18008e9ee`

## pseudocode

```c
__int64 __fastcall RunSyncOnMTAThread<_lambda_ceb8f1db0b0f2dc512542b4e425d8ca5_>(
        CClipboardBroker::SetClipboard::__l49::<lambda_ceb8f1db0b0f2dc512542b4e425d8ca5> operation)
{
  _TP_WORK *v1; // rax
  _TP_WORK *v2; // rbx
  signed int LastError; // eax
  RunSyncOnMTAThread::__l2::<lambda_fd5f26b17dc0b306889b51c5fa24ff59> hrHandlerOverOperation; // [rsp+20h] [rbp-18h] BYREF
  void **pMTAWrapperRawAddress; // [rsp+40h] [rbp+8h] BYREF
  HRESULT hr; // [rsp+48h] [rbp+10h] BYREF

  pMTAWrapperRawAddress = operation.pMTAWrapperRawAddress;
  hr = 0;
  hrHandlerOverOperation.operation = (CClipboardBroker::SetClipboard::__l49::<lambda_ceb8f1db0b0f2dc512542b4e425d8ca5> *)&pMTAWrapperRawAddress;
  hrHandlerOverOperation.hr = &hr;
  v1 = CreateThreadpoolWork(MTAThreadPoolWorker__lambda_fd5f26b17dc0b306889b51c5fa24ff59_, &hrHandlerOverOperation, 0);
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
0x18008e988  mov     r11, rsp
0x18008e98b  mov     [r11+8], operation
0x18008e98f  push    rbx
0x18008e990  sub     rsp, 30h
0x18008e994  lea     rax, [r11+8]
0x18008e998  mov     [rsp+38h+hr], 0
0x18008e9a0  mov     [r11-18h], rax
0x18008e9a4  lea     rdx, [r11-18h]; pv
0x18008e9a8  lea     rax, [r11+10h]
0x18008e9ac  xor     r8d, r8d; pcbe
0x18008e9af  lea     operation, MTAThreadPoolWorker__lambda_fd5f26b17dc0b306889b51c5fa24ff59___; pfnwk
0x18008e9b6  mov     [r11-10h], rax
0x18008e9ba  call    cs:__imp_CreateThreadpoolWork
0x18008e9c0  mov     rbx, rax
0x18008e9c3  test    rax, rax
0x18008e9c6  jnz     short loc_18008E9E0
0x18008e9c8  call    cs:__imp_GetLastError
0x18008e9ce  test    eax, eax
0x18008e9d0  jle     short loc_18008E9DA
0x18008e9d2  movzx   eax, ax
0x18008e9d5  or      eax, 80070000h
0x18008e9da  mov     [rsp+38h+hr], eax
0x18008e9de  jmp     short loc_18008E9FD
0x18008e9e0  mov     operation, rbx; pwk
0x18008e9e3  call    cs:__imp_SubmitThreadpoolWork
0x18008e9e9  xor     edx, edx; fCancelPendingCallbacks
0x18008e9eb  mov     operation, rbx; pwk
0x18008e9ee  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18008e9f4  mov     operation, rbx; pwk
0x18008e9f7  call    cs:__imp_CloseThreadpoolWork
0x18008e9fd  mov     eax, [rsp+38h+hr]
0x18008ea01  add     rsp, 30h
0x18008ea05  pop     rbx
0x18008ea06  retn
```
