# wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *)

- ea: `0x180008490`
- end: `0x1800084c1`
- name: `?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAXPEAU_TP_WAIT@@@Z`
- size: `49`
- prototype: `void __fastcall(PTP_WAIT pwa)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180008270`
- `0x180008c58`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800084ac`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800084ac`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000849e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000849e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800084ba`

## pseudocode

```c
void __fastcall wil::details::DestroyThreadPoolWait<0>::Destroy(PTP_WAIT pwa)
{
  SetThreadpoolWait(pwa, 0, 0);
  WaitForThreadpoolWaitCallbacks(pwa, 1);
  CloseThreadpoolWait(pwa);
}

```

## disassembly

```asm
0x180008490  push    rbx
0x180008492  sub     rsp, 20h
0x180008496  xor     r8d, r8d; pftTimeout
0x180008499  xor     edx, edx; h
0x18000849b  mov     rbx, rcx
0x18000849e  call    cs:__imp_SetThreadpoolWait
0x1800084a4  mov     edx, 1; fCancelPendingCallbacks
0x1800084a9  mov     rcx, rbx; pwa
0x1800084ac  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800084b2  mov     rcx, rbx
0x1800084b5  add     rsp, 20h
0x1800084b9  pop     rbx
0x1800084ba  jmp     cs:__imp_CloseThreadpoolWait
```
