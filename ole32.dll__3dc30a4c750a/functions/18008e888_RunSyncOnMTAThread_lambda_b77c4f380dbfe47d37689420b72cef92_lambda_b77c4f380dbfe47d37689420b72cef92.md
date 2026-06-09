# RunSyncOnMTAThread<_lambda_b77c4f380dbfe47d37689420b72cef92_>(_lambda_b77c4f380dbfe47d37689420b72cef92_)

- ea: `0x18008e888`
- end: `0x18008e8ff`
- name: `??$RunSyncOnMTAThread@V_lambda_b77c4f380dbfe47d37689420b72cef92_@@@@YAJV_lambda_b77c4f380dbfe47d37689420b72cef92_@@@Z`
- size: `119`
- prototype: `__int64 __fastcall(CDragDropBroker::RegisterDropTarget::__l11::<lambda_b77c4f380dbfe47d37689420b72cef92> *operation)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18008f7e0`

## callees

- `0x18008e888`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e8c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e8c0`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18008e8db`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18008e8db`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18008e8b2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18008e8b2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18008e8ef`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18008e8ef`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18008e8e6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18008e8e6`

## pseudocode

```c
__int64 __fastcall RunSyncOnMTAThread<_lambda_b77c4f380dbfe47d37689420b72cef92_>(
        CDragDropBroker::RegisterDropTarget::__l11::<lambda_b77c4f380dbfe47d37689420b72cef92> *operation)
{
  _TP_WORK *v1; // rax
  _TP_WORK *v2; // rbx
  signed int LastError; // eax
  RunSyncOnMTAThread::__l2::<lambda_13155382125dd69003103d0de547befd> hrHandlerOverOperation; // [rsp+20h] [rbp-18h] BYREF
  HRESULT hr; // [rsp+40h] [rbp+8h] BYREF

  hrHandlerOverOperation.operation = operation;
  hrHandlerOverOperation.hr = &hr;
  hr = 0;
  v1 = CreateThreadpoolWork(MTAThreadPoolWorker__lambda_13155382125dd69003103d0de547befd_, &hrHandlerOverOperation, 0);
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
0x18008e888  mov     r11, rsp
0x18008e88b  push    rbx
0x18008e88c  sub     rsp, 30h
0x18008e890  mov     [r11-18h], operation
0x18008e894  lea     rax, [r11+8]
0x18008e898  lea     operation, MTAThreadPoolWorker__lambda_13155382125dd69003103d0de547befd___; pfnwk
0x18008e89f  mov     [r11-10h], rax
0x18008e8a3  xor     r8d, r8d; pcbe
0x18008e8a6  mov     [rsp+38h+hr], 0
0x18008e8ae  lea     rdx, [r11-18h]; pv
0x18008e8b2  call    cs:__imp_CreateThreadpoolWork
0x18008e8b8  mov     rbx, rax
0x18008e8bb  test    rax, rax
0x18008e8be  jnz     short loc_18008E8D8
0x18008e8c0  call    cs:__imp_GetLastError
0x18008e8c6  test    eax, eax
0x18008e8c8  jle     short loc_18008E8D2
0x18008e8ca  movzx   eax, ax
0x18008e8cd  or      eax, 80070000h
0x18008e8d2  mov     [rsp+38h+hr], eax
0x18008e8d6  jmp     short loc_18008E8F5
0x18008e8d8  mov     operation, rbx; pwk
0x18008e8db  call    cs:__imp_SubmitThreadpoolWork
0x18008e8e1  xor     edx, edx; fCancelPendingCallbacks
0x18008e8e3  mov     operation, rbx; pwk
0x18008e8e6  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18008e8ec  mov     operation, rbx; pwk
0x18008e8ef  call    cs:__imp_CloseThreadpoolWork
0x18008e8f5  mov     eax, [rsp+38h+hr]
0x18008e8f9  add     rsp, 30h
0x18008e8fd  pop     rbx
0x18008e8fe  retn
```
