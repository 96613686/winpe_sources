# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180426538`
- end: `0x180426593`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `91`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1803c31b8`
- `0x1803c3224`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18042656e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18042656e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180426580`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180426580`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180426557`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180426557`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(
        struct _TP_TIMER *a1)
{
  SetThreadpoolTimer(a1, 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(a1, 1);
  CloseThreadpoolTimer(a1);
}

```

## disassembly

```asm
0x180426538  mov     [rsp+pti], rcx
0x18042653d  sub     rsp, 38h
0x180426541  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18042654a  xor     r9d, r9d; msWindowLength
0x18042654d  xor     r8d, r8d; msPeriod
0x180426550  xor     edx, edx; pftDueTime
0x180426552  mov     rcx, [rsp+38h+pti]; pti
0x180426557  call    cs:__imp_SetThreadpoolTimer
0x18042655e  nop     dword ptr [rax+rax+00h]
0x180426563  nop
0x180426564  mov     edx, 1; fCancelPendingCallbacks
0x180426569  mov     rcx, [rsp+38h+pti]; pti
0x18042656e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180426575  nop     dword ptr [rax+rax+00h]
0x18042657a  nop
0x18042657b  mov     rcx, [rsp+38h+pti]; pti
0x180426580  call    cs:__imp_CloseThreadpoolTimer
0x180426587  nop     dword ptr [rax+rax+00h]
0x18042658c  nop
0x18042658d  add     rsp, 38h
0x180426591  retn
```
