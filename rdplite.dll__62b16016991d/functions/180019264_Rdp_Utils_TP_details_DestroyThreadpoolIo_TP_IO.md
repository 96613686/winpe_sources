# Rdp::Utils::TP::details::DestroyThreadpoolIo(_TP_IO *)

- ea: `0x180019264`
- end: `0x180019287`
- name: `?DestroyThreadpoolIo@details@TP@Utils@Rdp@@YAXPEAU_TP_IO@@@Z`
- size: `35`
- prototype: `void __fastcall(Rdp::Utils::TP::details *__hidden this, struct _TP_IO *)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180018870`
- `0x18001b3a0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x180019272`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x180019272`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x180019280`

## pseudocode

```c
void __fastcall Rdp::Utils::TP::details::DestroyThreadpoolIo(Rdp::Utils::TP::details *this, struct _TP_IO *a2)
{
  WaitForThreadpoolIoCallbacks(this, 1);
  CloseThreadpoolIo(this);
}

```

## disassembly

```asm
0x180019264  push    rbx
0x180019266  sub     rsp, 20h
0x18001926a  mov     edx, 1; fCancelPendingCallbacks
0x18001926f  mov     rbx, rcx
0x180019272  call    cs:__imp_WaitForThreadpoolIoCallbacks
0x180019278  mov     rcx, rbx
0x18001927b  add     rsp, 20h
0x18001927f  pop     rbx
0x180019280  jmp     cs:__imp_CloseThreadpoolIo
```
