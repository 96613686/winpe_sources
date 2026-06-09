# RunSyncOnMTAThread__lambda_ac11c26dd3ae65ee398a5e6a0af64263_

- ea: `0x1800875fc`
- end: `0x180087692`
- name: `RunSyncOnMTAThread__lambda_ac11c26dd3ae65ee398a5e6a0af64263___`
- size: `150`
- prototype: `HRESULT __fastcall(RenderFormat::__l28::<lambda_ac11c26dd3ae65ee398a5e6a0af64263> operation)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18003b5f8`

## callees

- `0x1800875fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008763a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008763a`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18008765b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18008765b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180087626`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180087626`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18008767b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18008767b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18008766c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18008766c`

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
0x1800875fc  mov     r11, rsp
0x1800875ff  push    rbx
0x180087600  sub     rsp, 30h
0x180087604  mov     [r11-18h], operation
0x180087608  lea     rax, [r11+8]
0x18008760c  lea     operation, MTAThreadPoolWorker__lambda_2c8f2a792b4da02e47c1023e6a4a2993___; pfnwk
0x180087613  mov     [r11-10h], rax
0x180087617  xor     r8d, r8d; pcbe
0x18008761a  mov     [rsp+38h+hr], 0
0x180087622  lea     rdx, [r11-18h]; pv
0x180087626  call    cs:__imp_CreateThreadpoolWork
0x18008762d  nop     dword ptr [rax+rax+00h]
0x180087632  mov     rbx, rax
0x180087635  test    rax, rax
0x180087638  jnz     short loc_180087658
0x18008763a  call    cs:__imp_GetLastError
0x180087641  nop     dword ptr [rax+rax+00h]
0x180087646  test    eax, eax
0x180087648  jle     short loc_180087652
0x18008764a  movzx   eax, ax
0x18008764d  or      eax, 80070000h
0x180087652  mov     [rsp+38h+hr], eax
0x180087656  jmp     short loc_180087687
0x180087658  mov     operation, rbx; pwk
0x18008765b  call    cs:__imp_SubmitThreadpoolWork
0x180087662  nop     dword ptr [rax+rax+00h]
0x180087667  xor     edx, edx; fCancelPendingCallbacks
0x180087669  mov     operation, rbx; pwk
0x18008766c  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180087673  nop     dword ptr [rax+rax+00h]
0x180087678  mov     operation, rbx; pwk
0x18008767b  call    cs:__imp_CloseThreadpoolWork
0x180087682  nop     dword ptr [rax+rax+00h]
0x180087687  mov     eax, [rsp+38h+hr]
0x18008768b  add     rsp, 30h
0x18008768f  pop     rbx
0x180087690  retn
```
