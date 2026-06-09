# Rdp::Utils::TP::CThreadPool::~CThreadPool(void)

- ea: `0x18000da54`
- end: `0x18000dad3`
- name: `??1CThreadPool@TP@Utils@Rdp@@UEAA@XZ`
- size: `127`
- prototype: `void __fastcall(Rdp::Utils::TP::CThreadPool *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d7cc`
- `0x18000e100`

## callees

- `0x18000b07c`
- `0x18000da54`
- `0x18000e760`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000da7c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000da7c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18000dab1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18000dab1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18000da99`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18000da99`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18000daa2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18000daa2`

## pseudocode

```c
void __fastcall Rdp::Utils::TP::CThreadPool::~CThreadPool(PTP_CLEANUP_GROUP *this)
{
  PTP_CLEANUP_GROUP v2; // rcx
  unsigned int v3; // r8d
  const char *v4; // r9
  struct _TP_CLEANUP_GROUP *v5; // rdi
  struct _TP_POOL *v6; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *this = (PTP_CLEANUP_GROUP)&Rdp::Utils::TP::CThreadPool::`vftable';
  Rdp::Utils::TP::CThreadPool::Shutdown((Rdp::Utils::TP::CThreadPool *)this);
  v2 = this[23];
  if ( v2 && !CloseHandle(v2) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v3, v4);
  v5 = this[3];
  if ( v5 )
  {
    CloseThreadpoolCleanupGroupMembers(this[3], 1, 0);
    CloseThreadpoolCleanupGroup(v5);
  }
  v6 = this[2];
  if ( v6 )
    CloseThreadpool(v6);
}

```

## disassembly

```asm
0x18000da54  mov     [rsp+arg_0], rbx
0x18000da59  push    rdi
0x18000da5a  sub     rsp, 20h
0x18000da5e  mov     rbx, rcx
0x18000da61  lea     rax, ??_7CThreadPool@TP@Utils@Rdp@@6B@; const Rdp::Utils::TP::CThreadPool::`vftable'
0x18000da68  mov     [rcx], rax
0x18000da6b  call    ?Shutdown@CThreadPool@TP@Utils@Rdp@@QEAAXXZ; Rdp::Utils::TP::CThreadPool::Shutdown(void)
0x18000da70  mov     rcx, [rbx+0B8h]; hObject
0x18000da77  test    rcx, rcx
0x18000da7a  jz      short loc_18000DA86
0x18000da7c  call    cs:__imp_CloseHandle
0x18000da82  test    eax, eax
0x18000da84  jz      short loc_18000DAC3
0x18000da86  mov     rdi, [rbx+18h]
0x18000da8a  test    rdi, rdi
0x18000da8d  jz      short loc_18000DAA8
0x18000da8f  xor     r8d, r8d; pvCleanupContext
0x18000da92  lea     edx, [r8+1]; fCancelPendingCallbacks
0x18000da96  mov     rcx, rdi; ptpcg
0x18000da99  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18000da9f  mov     rcx, rdi; ptpcg
0x18000daa2  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18000daa8  mov     rcx, [rbx+10h]; ptpp
0x18000daac  test    rcx, rcx
0x18000daaf  jz      short loc_18000DAB8
0x18000dab1  call    cs:__imp_CloseThreadpool
0x18000dab7  nop
0x18000dab8  mov     rbx, [rsp+28h+arg_0]
0x18000dabd  add     rsp, 20h
0x18000dac1  pop     rdi
0x18000dac2  retn
0x18000dac3  mov     rcx, [rsp+28h]; this
0x18000dac8  mov     edx, 0A0Bh; void *
0x18000dacd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
