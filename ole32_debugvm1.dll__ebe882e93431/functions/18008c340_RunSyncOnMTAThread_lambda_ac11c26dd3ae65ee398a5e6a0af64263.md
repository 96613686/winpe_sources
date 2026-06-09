# RunSyncOnMTAThread__lambda_ac11c26dd3ae65ee398a5e6a0af64263_

- ea: `0x18008c340`
- end: `0x18008c3b7`
- name: `RunSyncOnMTAThread__lambda_ac11c26dd3ae65ee398a5e6a0af64263___`
- size: `119`
- prototype: `HRESULT __fastcall(RenderFormat::__l28::<lambda_ac11c26dd3ae65ee398a5e6a0af64263> operation)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800376b8`

## callees

- `0x18008c340`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008c378`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008c378`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18008c393`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18008c393`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18008c36a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18008c36a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18008c3a7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18008c3a7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18008c39e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18008c39e`

## pseudocode

```c
__int64 __fastcall RunSyncOnMTAThread__lambda_ac11c26dd3ae65ee398a5e6a0af64263_(
        RenderFormat::__l28::<lambda_ac11c26dd3ae65ee398a5e6a0af64263> *operation)
{
  _TP_WORK *v1; // rax
  _TP_WORK *v2; // rbx
  signed int LastError; // eax
  RunSyncOnMTAThread::__l2::<lambda_2c8f2a792b4da02e47c1023e6a4a2993> hrHandlerOverOperation; // [rsp+20h] [rbp-18h] BYREF
  HRESULT hr; // [rsp+40h] [rbp+8h] BYREF

  hrHandlerOverOperation.operation = operation;
  hrHandlerOverOperation.hr = &hr;
  hr = 0;
  v1 = CreateThreadpoolWork(MTAThreadPoolWorker__lambda_2c8f2a792b4da02e47c1023e6a4a2993_, &hrHandlerOverOperation, 0);
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
0x18008c340  mov     r11, rsp
0x18008c343  push    rbx
0x18008c344  sub     rsp, 30h
0x18008c348  mov     [r11-18h], operation
0x18008c34c  lea     rax, [r11+8]
0x18008c350  lea     operation, MTAThreadPoolWorker__lambda_2c8f2a792b4da02e47c1023e6a4a2993___; pfnwk
0x18008c357  mov     [r11-10h], rax
0x18008c35b  xor     r8d, r8d; pcbe
0x18008c35e  mov     [rsp+38h+hr], 0
0x18008c366  lea     rdx, [r11-18h]; pv
0x18008c36a  call    cs:__imp_CreateThreadpoolWork
0x18008c370  mov     rbx, rax
0x18008c373  test    rax, rax
0x18008c376  jnz     short loc_18008C390
0x18008c378  call    cs:__imp_GetLastError
0x18008c37e  test    eax, eax
0x18008c380  jle     short loc_18008C38A
0x18008c382  movzx   eax, ax
0x18008c385  or      eax, 80070000h
0x18008c38a  mov     [rsp+38h+hr], eax
0x18008c38e  jmp     short loc_18008C3AD
0x18008c390  mov     operation, rbx; pwk
0x18008c393  call    cs:__imp_SubmitThreadpoolWork
0x18008c399  xor     edx, edx; fCancelPendingCallbacks
0x18008c39b  mov     operation, rbx; pwk
0x18008c39e  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18008c3a4  mov     operation, rbx; pwk
0x18008c3a7  call    cs:__imp_CloseThreadpoolWork
0x18008c3ad  mov     eax, [rsp+38h+hr]
0x18008c3b1  add     rsp, 30h
0x18008c3b5  pop     rbx
0x18008c3b6  retn
```
