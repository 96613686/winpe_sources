# RunSyncOnMTAThread__lambda_27a1cab33e266522ee12881589f1a48d_

- ea: `0x1800902b0`
- end: `0x180090327`
- name: `RunSyncOnMTAThread__lambda_27a1cab33e266522ee12881589f1a48d___`
- size: `119`
- prototype: `HRESULT __fastcall(CClipDataObject::CacheDataPointer::__l54::<lambda_27a1cab33e266522ee12881589f1a48d> operation)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000e034`

## callees

- `0x1800902b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800902e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800902e8`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180090303`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180090303`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800902da`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800902da`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180090317`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180090317`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18009030e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18009030e`

## pseudocode

```c
__int64 __fastcall RunSyncOnMTAThread__lambda_27a1cab33e266522ee12881589f1a48d_(
        CClipDataObject::CacheDataPointer::__l54::<lambda_27a1cab33e266522ee12881589f1a48d> *operation)
{
  _TP_WORK *v1; // rax
  _TP_WORK *v2; // rbx
  signed int LastError; // eax
  RunSyncOnMTAThread::__l2::<lambda_38ef1b70e7c7bbb6bcbf325f13bce3ad> hrHandlerOverOperation; // [rsp+20h] [rbp-18h] BYREF
  HRESULT hr; // [rsp+40h] [rbp+8h] BYREF

  hrHandlerOverOperation.operation = operation;
  hrHandlerOverOperation.hr = &hr;
  hr = 0;
  v1 = CreateThreadpoolWork(MTAThreadPoolWorker__lambda_38ef1b70e7c7bbb6bcbf325f13bce3ad_, &hrHandlerOverOperation, 0);
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
0x1800902b0  mov     r11, rsp
0x1800902b3  push    rbx
0x1800902b4  sub     rsp, 30h
0x1800902b8  mov     [r11-18h], operation
0x1800902bc  lea     rax, [r11+8]
0x1800902c0  lea     operation, MTAThreadPoolWorker__lambda_38ef1b70e7c7bbb6bcbf325f13bce3ad___; pfnwk
0x1800902c7  mov     [r11-10h], rax
0x1800902cb  xor     r8d, r8d; pcbe
0x1800902ce  mov     [rsp+38h+hr], 0
0x1800902d6  lea     rdx, [r11-18h]; pv
0x1800902da  call    cs:__imp_CreateThreadpoolWork
0x1800902e0  mov     rbx, rax
0x1800902e3  test    rax, rax
0x1800902e6  jnz     short loc_180090300
0x1800902e8  call    cs:__imp_GetLastError
0x1800902ee  test    eax, eax
0x1800902f0  jle     short loc_1800902FA
0x1800902f2  movzx   eax, ax
0x1800902f5  or      eax, 80070000h
0x1800902fa  mov     [rsp+38h+hr], eax
0x1800902fe  jmp     short loc_18009031D
0x180090300  mov     operation, rbx; pwk
0x180090303  call    cs:__imp_SubmitThreadpoolWork
0x180090309  xor     edx, edx; fCancelPendingCallbacks
0x18009030b  mov     operation, rbx; pwk
0x18009030e  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180090314  mov     operation, rbx; pwk
0x180090317  call    cs:__imp_CloseThreadpoolWork
0x18009031d  mov     eax, [rsp+38h+hr]
0x180090321  add     rsp, 30h
0x180090325  pop     rbx
0x180090326  retn
```
