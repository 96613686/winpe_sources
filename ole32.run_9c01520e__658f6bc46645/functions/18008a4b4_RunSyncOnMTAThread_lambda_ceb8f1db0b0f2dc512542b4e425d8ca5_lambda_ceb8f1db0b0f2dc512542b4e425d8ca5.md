# RunSyncOnMTAThread<_lambda_ceb8f1db0b0f2dc512542b4e425d8ca5_>(_lambda_ceb8f1db0b0f2dc512542b4e425d8ca5_)

- ea: `0x18008a4b4`
- end: `0x18008a552`
- name: `??$RunSyncOnMTAThread@V_lambda_ceb8f1db0b0f2dc512542b4e425d8ca5_@@@@YAJV_lambda_ceb8f1db0b0f2dc512542b4e425d8ca5_@@@Z`
- size: `158`
- prototype: `HRESULT __fastcall(CClipboardBroker::SetClipboard::__l49::<lambda_ceb8f1db0b0f2dc512542b4e425d8ca5> operation)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001dbc0`

## callees

- `0x18008a4b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a4fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a4fa`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18008a51b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18008a51b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18008a4e6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18008a4e6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18008a53b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18008a53b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18008a52c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18008a52c`

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
0x18008a4b4  mov     r11, rsp
0x18008a4b7  mov     [r11+8], operation
0x18008a4bb  push    rbx
0x18008a4bc  sub     rsp, 30h
0x18008a4c0  lea     rax, [r11+8]
0x18008a4c4  mov     [rsp+38h+hr], 0
0x18008a4cc  mov     [r11-18h], rax
0x18008a4d0  lea     rdx, [r11-18h]; pv
0x18008a4d4  lea     rax, [r11+10h]
0x18008a4d8  xor     r8d, r8d; pcbe
0x18008a4db  lea     operation, MTAThreadPoolWorker__lambda_fd5f26b17dc0b306889b51c5fa24ff59___; pfnwk
0x18008a4e2  mov     [r11-10h], rax
0x18008a4e6  call    cs:__imp_CreateThreadpoolWork
0x18008a4ed  nop     dword ptr [rax+rax+00h]
0x18008a4f2  mov     rbx, rax
0x18008a4f5  test    rax, rax
0x18008a4f8  jnz     short loc_18008A518
0x18008a4fa  call    cs:__imp_GetLastError
0x18008a501  nop     dword ptr [rax+rax+00h]
0x18008a506  test    eax, eax
0x18008a508  jle     short loc_18008A512
0x18008a50a  movzx   eax, ax
0x18008a50d  or      eax, 80070000h
0x18008a512  mov     [rsp+38h+hr], eax
0x18008a516  jmp     short loc_18008A547
0x18008a518  mov     operation, rbx; pwk
0x18008a51b  call    cs:__imp_SubmitThreadpoolWork
0x18008a522  nop     dword ptr [rax+rax+00h]
0x18008a527  xor     edx, edx; fCancelPendingCallbacks
0x18008a529  mov     operation, rbx; pwk
0x18008a52c  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18008a533  nop     dword ptr [rax+rax+00h]
0x18008a538  mov     operation, rbx; pwk
0x18008a53b  call    cs:__imp_CloseThreadpoolWork
0x18008a542  nop     dword ptr [rax+rax+00h]
0x18008a547  mov     eax, [rsp+38h+hr]
0x18008a54b  add     rsp, 30h
0x18008a54f  pop     rbx
0x18008a550  retn
```
