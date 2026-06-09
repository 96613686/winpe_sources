# wil::details::registry_watcher_state::~registry_watcher_state(void)

- ea: `0x1800efd64`
- end: `0x1800efdf7`
- name: `??1registry_watcher_state@details@wil@@QEAA@XZ`
- size: `147`
- prototype: `void __fastcall(wil::details::registry_watcher_state *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800f0b30`
- `0x1800f82f4`
- `0x1800f86fc`

## callees

- `0x180064018`
- `0x1800efd64`
- `0x1802b7010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800efdae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800efdae`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800efd85`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800efd85`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800efd93`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800efd93`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800efd9c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800efd9c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800efdc1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800efdc1`

## pseudocode

```c
void __fastcall wil::details::registry_watcher_state::~registry_watcher_state(
        wil::details::registry_watcher_state *this)
{
  struct _TP_WAIT *v1; // rdi
  void *v3; // rcx
  unsigned int v4; // r8d
  const char *v5; // r9
  HKEY v6; // rcx
  __int64 v7; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = (struct _TP_WAIT *)*((_QWORD *)this + 17);
  if ( v1 )
  {
    SetThreadpoolWait(*((PTP_WAIT *)this + 17), 0, 0);
    WaitForThreadpoolWaitCallbacks(v1, 1);
    CloseThreadpoolWait(v1);
  }
  v3 = (void *)*((_QWORD *)this + 16);
  if ( v3 && !CloseHandle(v3) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v4, v5);
  v6 = (HKEY)*((_QWORD *)this + 15);
  if ( v6 )
    RegCloseKey(v6);
  v7 = *((_QWORD *)this + 14);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 24LL))(v7);
}

```

## disassembly

```asm
0x1800efd64  mov     [rsp+arg_0], rbx
0x1800efd69  push    rdi
0x1800efd6a  sub     rsp, 20h
0x1800efd6e  mov     rdi, [rcx+88h]
0x1800efd75  mov     rbx, rcx
0x1800efd78  test    rdi, rdi
0x1800efd7b  jz      short loc_1800EFDA2
0x1800efd7d  xor     r8d, r8d; pftTimeout
0x1800efd80  xor     edx, edx; h
0x1800efd82  mov     rcx, rdi; pwa
0x1800efd85  call    cs:__imp_SetThreadpoolWait
0x1800efd8b  mov     edx, 1; fCancelPendingCallbacks
0x1800efd90  mov     rcx, rdi; pwa
0x1800efd93  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800efd99  mov     rcx, rdi; pwa
0x1800efd9c  call    cs:__imp_CloseThreadpoolWait
0x1800efda2  mov     rcx, [rbx+80h]; hObject
0x1800efda9  test    rcx, rcx
0x1800efdac  jz      short loc_1800EFDB8
0x1800efdae  call    cs:__imp_CloseHandle
0x1800efdb4  test    eax, eax
0x1800efdb6  jz      short loc_1800EFDE7
0x1800efdb8  mov     rcx, [rbx+78h]; hKey
0x1800efdbc  test    rcx, rcx
0x1800efdbf  jz      short loc_1800EFDC7
0x1800efdc1  call    cs:__imp_RegCloseKey
0x1800efdc7  mov     rcx, [rbx+70h]
0x1800efdcb  test    rcx, rcx
0x1800efdce  jz      short loc_1800EFDDC
0x1800efdd0  mov     rax, [rcx]
0x1800efdd3  mov     rax, [rax+18h]
0x1800efdd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efddc  mov     rbx, [rsp+28h+arg_0]
0x1800efde1  add     rsp, 20h
0x1800efde5  pop     rdi
0x1800efde6  retn
0x1800efde7  mov     rcx, [rsp+28h]; this
0x1800efdec  mov     edx, 0A0Bh; void *
0x1800efdf1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
