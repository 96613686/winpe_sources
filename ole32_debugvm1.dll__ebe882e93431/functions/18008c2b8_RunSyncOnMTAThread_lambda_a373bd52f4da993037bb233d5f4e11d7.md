# RunSyncOnMTAThread__lambda_a373bd52f4da993037bb233d5f4e11d7_

- ea: `0x18008c2b8`
- end: `0x18008c337`
- name: `RunSyncOnMTAThread__lambda_a373bd52f4da993037bb233d5f4e11d7___`
- size: `127`
- prototype: `HRESULT __fastcall(RenderFormat::__l36::<lambda_a373bd52f4da993037bb233d5f4e11d7> operation)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800376b8`

## callees

- `0x18008c2b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008c2f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008c2f8`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18008c313`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18008c313`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18008c2ea`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18008c2ea`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18008c327`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18008c327`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18008c31e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18008c31e`

## pseudocode

```c
__int64 __fastcall RunSyncOnMTAThread__lambda_a373bd52f4da993037bb233d5f4e11d7_(
        RenderFormat::__l36::<lambda_a373bd52f4da993037bb233d5f4e11d7> operation)
{
  _TP_WORK *v1; // rax
  _TP_WORK *v2; // rbx
  signed int LastError; // eax
  RunSyncOnMTAThread::__l2::<lambda_1f33e66c4d719b5f6d4f05584bc2ec2e> hrHandlerOverOperation; // [rsp+20h] [rbp-18h] BYREF
  tagSTGMEDIUM *medium; // [rsp+40h] [rbp+8h] BYREF
  HRESULT hr; // [rsp+48h] [rbp+10h] BYREF

  medium = operation.medium;
  hr = 0;
  hrHandlerOverOperation.operation = (RenderFormat::__l36::<lambda_a373bd52f4da993037bb233d5f4e11d7> *)&medium;
  hrHandlerOverOperation.hr = &hr;
  v1 = CreateThreadpoolWork(MTAThreadPoolWorker__lambda_1f33e66c4d719b5f6d4f05584bc2ec2e_, &hrHandlerOverOperation, 0);
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
0x18008c2b8  mov     r11, rsp
0x18008c2bb  mov     [r11+8], operation
0x18008c2bf  push    rbx
0x18008c2c0  sub     rsp, 30h
0x18008c2c4  lea     rax, [r11+8]
0x18008c2c8  mov     [rsp+38h+hr], 0
0x18008c2d0  mov     [r11-18h], rax
0x18008c2d4  lea     rdx, [r11-18h]; pv
0x18008c2d8  lea     rax, [r11+10h]
0x18008c2dc  xor     r8d, r8d; pcbe
0x18008c2df  lea     operation, MTAThreadPoolWorker__lambda_1f33e66c4d719b5f6d4f05584bc2ec2e___; pfnwk
0x18008c2e6  mov     [r11-10h], rax
0x18008c2ea  call    cs:__imp_CreateThreadpoolWork
0x18008c2f0  mov     rbx, rax
0x18008c2f3  test    rax, rax
0x18008c2f6  jnz     short loc_18008C310
0x18008c2f8  call    cs:__imp_GetLastError
0x18008c2fe  test    eax, eax
0x18008c300  jle     short loc_18008C30A
0x18008c302  movzx   eax, ax
0x18008c305  or      eax, 80070000h
0x18008c30a  mov     [rsp+38h+hr], eax
0x18008c30e  jmp     short loc_18008C32D
0x18008c310  mov     operation, rbx; pwk
0x18008c313  call    cs:__imp_SubmitThreadpoolWork
0x18008c319  xor     edx, edx; fCancelPendingCallbacks
0x18008c31b  mov     operation, rbx; pwk
0x18008c31e  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18008c324  mov     operation, rbx; pwk
0x18008c327  call    cs:__imp_CloseThreadpoolWork
0x18008c32d  mov     eax, [rsp+38h+hr]
0x18008c331  add     rsp, 30h
0x18008c335  pop     rbx
0x18008c336  retn
```
