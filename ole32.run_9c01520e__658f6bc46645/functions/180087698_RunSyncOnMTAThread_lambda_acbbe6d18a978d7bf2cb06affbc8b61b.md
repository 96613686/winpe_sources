# RunSyncOnMTAThread__lambda_acbbe6d18a978d7bf2cb06affbc8b61b_

- ea: `0x180087698`
- end: `0x180087736`
- name: `RunSyncOnMTAThread__lambda_acbbe6d18a978d7bf2cb06affbc8b61b___`
- size: `158`
- prototype: `HRESULT __fastcall(RemoveClipboardDataObject::__l14::<lambda_acbbe6d18a978d7bf2cb06affbc8b61b> operation)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180028c84`

## callees

- `0x180087698`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800876de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800876de`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800876ff`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800876ff`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800876ca`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800876ca`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18008771f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18008771f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180087710`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180087710`

## pseudocode

```c
__int64 __fastcall RunSyncOnMTAThread__lambda_acbbe6d18a978d7bf2cb06affbc8b61b_(
        RemoveClipboardDataObject::__l14::<lambda_acbbe6d18a978d7bf2cb06affbc8b61b> operation)
{
  _TP_WORK *v1; // rax
  _TP_WORK *v2; // rbx
  signed int LastError; // eax
  RunSyncOnMTAThread::__l2::<lambda_8a24869d9b18bed7b3421b4230e9e935> hrHandlerOverOperation; // [rsp+20h] [rbp-18h] BYREF
  void **pDataObjInMTA; // [rsp+40h] [rbp+8h] BYREF
  HRESULT hr; // [rsp+48h] [rbp+10h] BYREF

  pDataObjInMTA = operation.pDataObjInMTA;
  hr = 0;
  hrHandlerOverOperation.operation = (RemoveClipboardDataObject::__l14::<lambda_acbbe6d18a978d7bf2cb06affbc8b61b> *)&pDataObjInMTA;
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
0x180087698  mov     r11, rsp
0x18008769b  mov     [r11+8], operation
0x18008769f  push    rbx
0x1800876a0  sub     rsp, 30h
0x1800876a4  lea     rax, [r11+8]
0x1800876a8  mov     [rsp+38h+hr], 0
0x1800876b0  mov     [r11-18h], rax
0x1800876b4  lea     rdx, [r11-18h]; pv
0x1800876b8  lea     rax, [r11+10h]
0x1800876bc  xor     r8d, r8d; pcbe
0x1800876bf  lea     operation, MTAThreadPoolWorker__lambda_fd5f26b17dc0b306889b51c5fa24ff59___; pfnwk
0x1800876c6  mov     [r11-10h], rax
0x1800876ca  call    cs:__imp_CreateThreadpoolWork
0x1800876d1  nop     dword ptr [rax+rax+00h]
0x1800876d6  mov     rbx, rax
0x1800876d9  test    rax, rax
0x1800876dc  jnz     short loc_1800876FC
0x1800876de  call    cs:__imp_GetLastError
0x1800876e5  nop     dword ptr [rax+rax+00h]
0x1800876ea  test    eax, eax
0x1800876ec  jle     short loc_1800876F6
0x1800876ee  movzx   eax, ax
0x1800876f1  or      eax, 80070000h
0x1800876f6  mov     [rsp+38h+hr], eax
0x1800876fa  jmp     short loc_18008772B
0x1800876fc  mov     operation, rbx; pwk
0x1800876ff  call    cs:__imp_SubmitThreadpoolWork
0x180087706  nop     dword ptr [rax+rax+00h]
0x18008770b  xor     edx, edx; fCancelPendingCallbacks
0x18008770d  mov     operation, rbx; pwk
0x180087710  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180087717  nop     dword ptr [rax+rax+00h]
0x18008771c  mov     operation, rbx; pwk
0x18008771f  call    cs:__imp_CloseThreadpoolWork
0x180087726  nop     dword ptr [rax+rax+00h]
0x18008772b  mov     eax, [rsp+38h+hr]
0x18008772f  add     rsp, 30h
0x180087733  pop     rbx
0x180087734  retn
```
