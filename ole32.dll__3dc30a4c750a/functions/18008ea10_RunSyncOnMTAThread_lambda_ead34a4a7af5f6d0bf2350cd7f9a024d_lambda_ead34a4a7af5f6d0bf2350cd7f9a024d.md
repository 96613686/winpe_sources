# RunSyncOnMTAThread<_lambda_ead34a4a7af5f6d0bf2350cd7f9a024d_>(_lambda_ead34a4a7af5f6d0bf2350cd7f9a024d_)

- ea: `0x18008ea10`
- end: `0x18008ea8f`
- name: `??$RunSyncOnMTAThread@V_lambda_ead34a4a7af5f6d0bf2350cd7f9a024d_@@@@YAJV_lambda_ead34a4a7af5f6d0bf2350cd7f9a024d_@@@Z`
- size: `127`
- prototype: `__int64 __fastcall(CDragDropBroker::UnregisterDropTarget::__l5::<lambda_ead34a4a7af5f6d0bf2350cd7f9a024d> operation)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18008fac0`

## callees

- `0x18008ea10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ea50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ea50`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18008ea6b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18008ea6b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18008ea42`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18008ea42`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18008ea7f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18008ea7f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18008ea76`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18008ea76`

## pseudocode

```c
__int64 __fastcall RunSyncOnMTAThread<_lambda_ead34a4a7af5f6d0bf2350cd7f9a024d_>(
        CDragDropBroker::UnregisterDropTarget::__l5::<lambda_ead34a4a7af5f6d0bf2350cd7f9a024d> operation)
{
  _TP_WORK *v1; // rax
  _TP_WORK *v2; // rbx
  signed int LastError; // eax
  RunSyncOnMTAThread::__l2::<lambda_62491be394b972db9f83c71868d37b41> hrHandlerOverOperation; // [rsp+20h] [rbp-18h] BYREF
  HWND__ **hwnd; // [rsp+40h] [rbp+8h] BYREF
  HRESULT hr; // [rsp+48h] [rbp+10h] BYREF

  hwnd = operation.hwnd;
  hr = 0;
  hrHandlerOverOperation.operation = (CDragDropBroker::UnregisterDropTarget::__l5::<lambda_ead34a4a7af5f6d0bf2350cd7f9a024d> *)&hwnd;
  hrHandlerOverOperation.hr = &hr;
  v1 = CreateThreadpoolWork(MTAThreadPoolWorker__lambda_62491be394b972db9f83c71868d37b41_, &hrHandlerOverOperation, 0);
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
0x18008ea10  mov     r11, rsp
0x18008ea13  mov     [r11+8], operation
0x18008ea17  push    rbx
0x18008ea18  sub     rsp, 30h
0x18008ea1c  lea     rax, [r11+8]
0x18008ea20  mov     [rsp+38h+hr], 0
0x18008ea28  mov     [r11-18h], rax
0x18008ea2c  lea     rdx, [r11-18h]; pv
0x18008ea30  lea     rax, [r11+10h]
0x18008ea34  xor     r8d, r8d; pcbe
0x18008ea37  lea     operation, MTAThreadPoolWorker__lambda_62491be394b972db9f83c71868d37b41___; pfnwk
0x18008ea3e  mov     [r11-10h], rax
0x18008ea42  call    cs:__imp_CreateThreadpoolWork
0x18008ea48  mov     rbx, rax
0x18008ea4b  test    rax, rax
0x18008ea4e  jnz     short loc_18008EA68
0x18008ea50  call    cs:__imp_GetLastError
0x18008ea56  test    eax, eax
0x18008ea58  jle     short loc_18008EA62
0x18008ea5a  movzx   eax, ax
0x18008ea5d  or      eax, 80070000h
0x18008ea62  mov     [rsp+38h+hr], eax
0x18008ea66  jmp     short loc_18008EA85
0x18008ea68  mov     operation, rbx; pwk
0x18008ea6b  call    cs:__imp_SubmitThreadpoolWork
0x18008ea71  xor     edx, edx; fCancelPendingCallbacks
0x18008ea73  mov     operation, rbx; pwk
0x18008ea76  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18008ea7c  mov     operation, rbx; pwk
0x18008ea7f  call    cs:__imp_CloseThreadpoolWork
0x18008ea85  mov     eax, [rsp+38h+hr]
0x18008ea89  add     rsp, 30h
0x18008ea8d  pop     rbx
0x18008ea8e  retn
```
