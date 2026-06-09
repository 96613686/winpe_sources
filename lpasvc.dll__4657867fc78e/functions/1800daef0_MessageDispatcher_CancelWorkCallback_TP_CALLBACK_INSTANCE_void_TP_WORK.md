# MessageDispatcher::_CancelWorkCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x1800daef0`
- end: `0x1800daf23`
- name: `?_CancelWorkCallback@MessageDispatcher@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `51`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800daef0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800daf17`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800daf17`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800daf05`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800daf05`

## pseudocode

```c
void __fastcall MessageDispatcher::_CancelWorkCallback(
        PTP_CALLBACK_INSTANCE Instance,
        PTP_WORK *Context,
        PTP_WORK Work)
{
  PTP_WORK v4; // rcx

  WaitForThreadpoolWorkCallbacks(Context[16], 1);
  v4 = Context[17];
  if ( v4 )
    SetEvent(v4);
}

```

## disassembly

```asm
0x1800daef0  push    rbx
0x1800daef2  sub     rsp, 20h
0x1800daef6  mov     rbx, rdx
0x1800daef9  mov     edx, 1; fCancelPendingCallbacks
0x1800daefe  mov     rcx, [rbx+80h]; pwk
0x1800daf05  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x1800daf0b  mov     rcx, [rbx+88h]; hEvent
0x1800daf12  test    rcx, rcx
0x1800daf15  jz      short loc_1800DAF1D
0x1800daf17  call    cs:__imp_SetEvent
0x1800daf1d  add     rsp, 20h
0x1800daf21  pop     rbx
0x1800daf22  retn
```
