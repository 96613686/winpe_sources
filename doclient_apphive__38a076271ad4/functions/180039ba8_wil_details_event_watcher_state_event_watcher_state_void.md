# wil::details::event_watcher_state::~event_watcher_state(void)

- ea: `0x180039ba8`
- end: `0x180039c29`
- name: `??1event_watcher_state@details@wil@@QEAA@XZ`
- size: `129`
- prototype: `void __fastcall(wil::details::event_watcher_state *__hidden this)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180028a94`
- `0x180028ac4`
- `0x180028e9c`
- `0x18002cdb8`
- `0x1800a8c3c`

## callees

- `0x18000a4e0`
- `0x180039ba8`
- `0x180108e50`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039bef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039bef`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180039bd7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180039bd7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180039bc9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180039bc9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180039be0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180039be0`

## pseudocode

```c
void __fastcall wil::details::event_watcher_state::~event_watcher_state(wil::details::event_watcher_state *this)
{
  struct _TP_WAIT *v1; // rdi
  void *v3; // rcx
  unsigned int v4; // r8d
  const char *v5; // r9
  __int64 v6; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = (struct _TP_WAIT *)*((_QWORD *)this + 16);
  if ( v1 )
  {
    SetThreadpoolWait(*((PTP_WAIT *)this + 16), 0, 0);
    WaitForThreadpoolWaitCallbacks(v1, 1);
    CloseThreadpoolWait(v1);
  }
  v3 = (void *)*((_QWORD *)this + 15);
  if ( v3 && !CloseHandle(v3) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v4, v5);
  v6 = *((_QWORD *)this + 14);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 24LL))(v6);
}

```

## disassembly

```asm
0x180039ba8  mov     [rsp+arg_0], rbx
0x180039bad  push    rdi
0x180039bae  sub     rsp, 20h
0x180039bb2  mov     rdi, [rcx+80h]
0x180039bb9  mov     rbx, rcx
0x180039bbc  test    rdi, rdi
0x180039bbf  jz      short loc_180039BE6
0x180039bc1  xor     r8d, r8d; pftTimeout
0x180039bc4  xor     edx, edx; h
0x180039bc6  mov     rcx, rdi; pwa
0x180039bc9  call    cs:__imp_SetThreadpoolWait
0x180039bcf  mov     edx, 1; fCancelPendingCallbacks
0x180039bd4  mov     rcx, rdi; pwa
0x180039bd7  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180039bdd  mov     rcx, rdi; pwa
0x180039be0  call    cs:__imp_CloseThreadpoolWait
0x180039be6  mov     rcx, [rbx+78h]; hObject
0x180039bea  test    rcx, rcx
0x180039bed  jz      short loc_180039BF9
0x180039bef  call    cs:__imp_CloseHandle
0x180039bf5  test    eax, eax
0x180039bf7  jz      short loc_180039C19
0x180039bf9  mov     rcx, [rbx+70h]
0x180039bfd  test    rcx, rcx
0x180039c00  jz      short loc_180039C0E
0x180039c02  mov     rax, [rcx]
0x180039c05  mov     rax, [rax+18h]
0x180039c09  call    _guard_dispatch_icall
0x180039c0e  mov     rbx, [rsp+28h+arg_0]
0x180039c13  add     rsp, 20h
0x180039c17  pop     rdi
0x180039c18  retn
0x180039c19  mov     rcx, [rsp+28h]; this
0x180039c1e  mov     edx, 9D1h; void *
0x180039c23  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
