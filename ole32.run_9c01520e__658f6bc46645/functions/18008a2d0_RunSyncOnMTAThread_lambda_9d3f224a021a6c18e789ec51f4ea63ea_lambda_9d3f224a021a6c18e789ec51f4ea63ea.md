# RunSyncOnMTAThread<_lambda_9d3f224a021a6c18e789ec51f4ea63ea_>(_lambda_9d3f224a021a6c18e789ec51f4ea63ea_)

- ea: `0x18008a2d0`
- end: `0x18008a36e`
- name: `??$RunSyncOnMTAThread@V_lambda_9d3f224a021a6c18e789ec51f4ea63ea_@@@@YAJV_lambda_9d3f224a021a6c18e789ec51f4ea63ea_@@@Z`
- size: `158`
- prototype: `HRESULT __fastcall(CDragDropBroker::UnregisterDropTarget::__l5::<lambda_9d3f224a021a6c18e789ec51f4ea63ea> operation)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18008bb00`

## callees

- `0x18008a2d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a316`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a316`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18008a337`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18008a337`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18008a302`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18008a302`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18008a357`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18008a357`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18008a348`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18008a348`

## pseudocode

```c
__int64 __fastcall RunSyncOnMTAThread<_lambda_9d3f224a021a6c18e789ec51f4ea63ea_>(
        CDragDropBroker::UnregisterDropTarget::__l5::<lambda_9d3f224a021a6c18e789ec51f4ea63ea> operation)
{
  _TP_WORK *v1; // rax
  _TP_WORK *v2; // rbx
  signed int LastError; // eax
  RunSyncOnMTAThread::__l2::<lambda_7ec28f4538e10499ff58daa918b0ca77> hrHandlerOverOperation; // [rsp+20h] [rbp-18h] BYREF
  HWND__ **hwnd; // [rsp+40h] [rbp+8h] BYREF
  HRESULT hr; // [rsp+48h] [rbp+10h] BYREF

  hwnd = operation.hwnd;
  hr = 0;
  hrHandlerOverOperation.operation = (CDragDropBroker::UnregisterDropTarget::__l5::<lambda_9d3f224a021a6c18e789ec51f4ea63ea> *)&hwnd;
  hrHandlerOverOperation.hr = &hr;
  v1 = CreateThreadpoolWork(MTAThreadPoolWorker__lambda_7ec28f4538e10499ff58daa918b0ca77_, &hrHandlerOverOperation, 0);
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
0x18008a2d0  mov     r11, rsp
0x18008a2d3  mov     [r11+8], operation
0x18008a2d7  push    rbx
0x18008a2d8  sub     rsp, 30h
0x18008a2dc  lea     rax, [r11+8]
0x18008a2e0  mov     [rsp+38h+hr], 0
0x18008a2e8  mov     [r11-18h], rax
0x18008a2ec  lea     rdx, [r11-18h]; pv
0x18008a2f0  lea     rax, [r11+10h]
0x18008a2f4  xor     r8d, r8d; pcbe
0x18008a2f7  lea     operation, MTAThreadPoolWorker__lambda_7ec28f4538e10499ff58daa918b0ca77___; pfnwk
0x18008a2fe  mov     [r11-10h], rax
0x18008a302  call    cs:__imp_CreateThreadpoolWork
0x18008a309  nop     dword ptr [rax+rax+00h]
0x18008a30e  mov     rbx, rax
0x18008a311  test    rax, rax
0x18008a314  jnz     short loc_18008A334
0x18008a316  call    cs:__imp_GetLastError
0x18008a31d  nop     dword ptr [rax+rax+00h]
0x18008a322  test    eax, eax
0x18008a324  jle     short loc_18008A32E
0x18008a326  movzx   eax, ax
0x18008a329  or      eax, 80070000h
0x18008a32e  mov     [rsp+38h+hr], eax
0x18008a332  jmp     short loc_18008A363
0x18008a334  mov     operation, rbx; pwk
0x18008a337  call    cs:__imp_SubmitThreadpoolWork
0x18008a33e  nop     dword ptr [rax+rax+00h]
0x18008a343  xor     edx, edx; fCancelPendingCallbacks
0x18008a345  mov     operation, rbx; pwk
0x18008a348  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18008a34f  nop     dword ptr [rax+rax+00h]
0x18008a354  mov     operation, rbx; pwk
0x18008a357  call    cs:__imp_CloseThreadpoolWork
0x18008a35e  nop     dword ptr [rax+rax+00h]
0x18008a363  mov     eax, [rsp+38h+hr]
0x18008a367  add     rsp, 30h
0x18008a36b  pop     rbx
0x18008a36c  retn
```
