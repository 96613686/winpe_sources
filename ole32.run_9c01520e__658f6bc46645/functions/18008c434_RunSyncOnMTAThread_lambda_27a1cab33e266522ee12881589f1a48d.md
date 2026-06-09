# RunSyncOnMTAThread__lambda_27a1cab33e266522ee12881589f1a48d_

- ea: `0x18008c434`
- end: `0x18008c4ca`
- name: `RunSyncOnMTAThread__lambda_27a1cab33e266522ee12881589f1a48d___`
- size: `150`
- prototype: `HRESULT __fastcall(CClipDataObject::CacheDataPointer::__l54::<lambda_27a1cab33e266522ee12881589f1a48d> operation)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180019864`

## callees

- `0x18008c434`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008c472`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008c472`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18008c493`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18008c493`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18008c45e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18008c45e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18008c4b3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18008c4b3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18008c4a4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18008c4a4`

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
0x18008c434  mov     r11, rsp
0x18008c437  push    rbx
0x18008c438  sub     rsp, 30h
0x18008c43c  mov     [r11-18h], operation
0x18008c440  lea     rax, [r11+8]
0x18008c444  lea     operation, MTAThreadPoolWorker__lambda_38ef1b70e7c7bbb6bcbf325f13bce3ad___; pfnwk
0x18008c44b  mov     [r11-10h], rax
0x18008c44f  xor     r8d, r8d; pcbe
0x18008c452  mov     [rsp+38h+hr], 0
0x18008c45a  lea     rdx, [r11-18h]; pv
0x18008c45e  call    cs:__imp_CreateThreadpoolWork
0x18008c465  nop     dword ptr [rax+rax+00h]
0x18008c46a  mov     rbx, rax
0x18008c46d  test    rax, rax
0x18008c470  jnz     short loc_18008C490
0x18008c472  call    cs:__imp_GetLastError
0x18008c479  nop     dword ptr [rax+rax+00h]
0x18008c47e  test    eax, eax
0x18008c480  jle     short loc_18008C48A
0x18008c482  movzx   eax, ax
0x18008c485  or      eax, 80070000h
0x18008c48a  mov     [rsp+38h+hr], eax
0x18008c48e  jmp     short loc_18008C4BF
0x18008c490  mov     operation, rbx; pwk
0x18008c493  call    cs:__imp_SubmitThreadpoolWork
0x18008c49a  nop     dword ptr [rax+rax+00h]
0x18008c49f  xor     edx, edx; fCancelPendingCallbacks
0x18008c4a1  mov     operation, rbx; pwk
0x18008c4a4  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18008c4ab  nop     dword ptr [rax+rax+00h]
0x18008c4b0  mov     operation, rbx; pwk
0x18008c4b3  call    cs:__imp_CloseThreadpoolWork
0x18008c4ba  nop     dword ptr [rax+rax+00h]
0x18008c4bf  mov     eax, [rsp+38h+hr]
0x18008c4c3  add     rsp, 30h
0x18008c4c7  pop     rbx
0x18008c4c8  retn
```
