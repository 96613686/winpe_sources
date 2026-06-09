# RunSyncOnMTAThread<_lambda_a4e555621f6ed4efaaeeaa7992cb2190_>(_lambda_a4e555621f6ed4efaaeeaa7992cb2190_)

- ea: `0x18008a374`
- end: `0x18008a412`
- name: `??$RunSyncOnMTAThread@V_lambda_a4e555621f6ed4efaaeeaa7992cb2190_@@@@YAJV_lambda_a4e555621f6ed4efaaeeaa7992cb2190_@@@Z`
- size: `158`
- prototype: `HRESULT __fastcall(CClipboardBroker::ValidateAndAcquireACImpersonationSource::__l8::<lambda_a4e555621f6ed4efaaeeaa7992cb2190> operation)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18008bb40`

## callees

- `0x18008a374`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a3ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a3ba`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18008a3db`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18008a3db`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18008a3a6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18008a3a6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18008a3fb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18008a3fb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18008a3ec`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18008a3ec`

## pseudocode

```c
__int64 __fastcall RunSyncOnMTAThread<_lambda_a4e555621f6ed4efaaeeaa7992cb2190_>(
        CClipboardBroker::ValidateAndAcquireACImpersonationSource::__l8::<lambda_a4e555621f6ed4efaaeeaa7992cb2190> operation)
{
  _TP_WORK *v1; // rax
  _TP_WORK *v2; // rbx
  signed int LastError; // eax
  RunSyncOnMTAThread::__l2::<lambda_e0acd7286b12d12902e038044f4b1749> hrHandlerOverOperation; // [rsp+20h] [rbp-18h] BYREF
  Windows::Internal::GitPtr *GITMTAHelper; // [rsp+40h] [rbp+8h] BYREF
  HRESULT hr; // [rsp+48h] [rbp+10h] BYREF

  GITMTAHelper = operation.GITMTAHelper;
  hr = 0;
  hrHandlerOverOperation.operation = (CClipboardBroker::ValidateAndAcquireACImpersonationSource::__l8::<lambda_a4e555621f6ed4efaaeeaa7992cb2190> *)&GITMTAHelper;
  hrHandlerOverOperation.hr = &hr;
  v1 = CreateThreadpoolWork(MTAThreadPoolWorker__lambda_e0acd7286b12d12902e038044f4b1749_, &hrHandlerOverOperation, 0);
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
0x18008a374  mov     r11, rsp
0x18008a377  mov     [r11+8], operation
0x18008a37b  push    rbx
0x18008a37c  sub     rsp, 30h
0x18008a380  lea     rax, [r11+8]
0x18008a384  mov     [rsp+38h+hr], 0
0x18008a38c  mov     [r11-18h], rax
0x18008a390  lea     rdx, [r11-18h]; pv
0x18008a394  lea     rax, [r11+10h]
0x18008a398  xor     r8d, r8d; pcbe
0x18008a39b  lea     operation, MTAThreadPoolWorker__lambda_e0acd7286b12d12902e038044f4b1749___; pfnwk
0x18008a3a2  mov     [r11-10h], rax
0x18008a3a6  call    cs:__imp_CreateThreadpoolWork
0x18008a3ad  nop     dword ptr [rax+rax+00h]
0x18008a3b2  mov     rbx, rax
0x18008a3b5  test    rax, rax
0x18008a3b8  jnz     short loc_18008A3D8
0x18008a3ba  call    cs:__imp_GetLastError
0x18008a3c1  nop     dword ptr [rax+rax+00h]
0x18008a3c6  test    eax, eax
0x18008a3c8  jle     short loc_18008A3D2
0x18008a3ca  movzx   eax, ax
0x18008a3cd  or      eax, 80070000h
0x18008a3d2  mov     [rsp+38h+hr], eax
0x18008a3d6  jmp     short loc_18008A407
0x18008a3d8  mov     operation, rbx; pwk
0x18008a3db  call    cs:__imp_SubmitThreadpoolWork
0x18008a3e2  nop     dword ptr [rax+rax+00h]
0x18008a3e7  xor     edx, edx; fCancelPendingCallbacks
0x18008a3e9  mov     operation, rbx; pwk
0x18008a3ec  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18008a3f3  nop     dword ptr [rax+rax+00h]
0x18008a3f8  mov     operation, rbx; pwk
0x18008a3fb  call    cs:__imp_CloseThreadpoolWork
0x18008a402  nop     dword ptr [rax+rax+00h]
0x18008a407  mov     eax, [rsp+38h+hr]
0x18008a40b  add     rsp, 30h
0x18008a40f  pop     rbx
0x18008a410  retn
```
