# HNS::Service::Common::Notify::INotifyable::StopNotify(void)

- ea: `0x1800da494`
- end: `0x1800da55b`
- name: `?StopNotify@INotifyable@Notify@Common@Service@HNS@@IEAAXXZ`
- size: `199`
- prototype: `void __fastcall(HNS::Service::Common::Notify::INotifyable *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800d80bc`
- `0x1800f56a0`
- `0x180128da4`
- `0x180130cc0`

## callees

- `0x180064018`
- `0x1800759d8`
- `0x180075aac`
- `0x1800da494`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800da4ef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800da51d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800da4ef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800da51d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800da4c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800da506`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800da4c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800da506`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800da511`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800da511`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800da4d0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800da4d0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800da4de`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800da4de`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800da4e7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800da4e7`

## string_xrefs

- `0x1800da4ab`: `HNS::Service::Common::Notify::INotifyable::StopNotify`
- `0x1800da530`: `HNS::Service::Common::Notify::INotifyable::StopNotify`

## pseudocode

```c
void __fastcall HNS::Service::Common::Notify::INotifyable::StopNotify(HNS::Service::Common::Notify::INotifyable *this)
{
  struct _TP_WAIT *v2; // rsi
  DWORD LastError; // ebx
  void *v4; // rbx
  DWORD v5; // esi
  unsigned int v6; // r8d
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  HNSTraceProvider::TraceEnter("HNS::Service::Common::Notify::INotifyable::StopNotify", 0x1A5u);
  v2 = (struct _TP_WAIT *)*((_QWORD *)this + 2);
  if ( v2 )
  {
    LastError = GetLastError();
    SetThreadpoolWait(v2, 0, 0);
    WaitForThreadpoolWaitCallbacks(v2, 1);
    CloseThreadpoolWait(v2);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 2) = 0;
  v4 = (void *)*((_QWORD *)this + 1);
  if ( v4 )
  {
    v5 = GetLastError();
    if ( !CloseHandle(v4) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v6, v7);
    SetLastError(v5);
  }
  *((_QWORD *)this + 1) = 0;
  HNSTraceProvider::TraceSuccess("HNS::Service::Common::Notify::INotifyable::StopNotify", 0x1A8u);
}

```

## disassembly

```asm
0x1800da494  mov     [rsp+arg_0], rbx
0x1800da499  mov     [rsp+arg_8], rsi
0x1800da49e  push    rdi
0x1800da49f  sub     rsp, 20h
0x1800da4a3  mov     rdi, rcx
0x1800da4a6  mov     edx, 1A5h; unsigned int
0x1800da4ab  lea     rcx, aHnsServiceComm; "HNS::Service::Common::Notify::INotifyab"...
0x1800da4b2  call    ?TraceEnter@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceEnter(char const *,uint)
0x1800da4b7  mov     rsi, [rdi+10h]
0x1800da4bb  test    rsi, rsi
0x1800da4be  jz      short loc_1800DA4F5
0x1800da4c0  call    cs:__imp_GetLastError
0x1800da4c6  xor     r8d, r8d; pftTimeout
0x1800da4c9  xor     edx, edx; h
0x1800da4cb  mov     rcx, rsi; pwa
0x1800da4ce  mov     ebx, eax
0x1800da4d0  call    cs:__imp_SetThreadpoolWait
0x1800da4d6  mov     edx, 1; fCancelPendingCallbacks
0x1800da4db  mov     rcx, rsi; pwa
0x1800da4de  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800da4e4  mov     rcx, rsi; pwa
0x1800da4e7  call    cs:__imp_CloseThreadpoolWait
0x1800da4ed  mov     ecx, ebx; dwErrCode
0x1800da4ef  call    cs:__imp_SetLastError
0x1800da4f5  mov     qword ptr [rdi+10h], 0
0x1800da4fd  mov     rbx, [rdi+8]
0x1800da501  test    rbx, rbx
0x1800da504  jz      short loc_1800DA523
0x1800da506  call    cs:__imp_GetLastError
0x1800da50c  mov     rcx, rbx; hObject
0x1800da50f  mov     esi, eax
0x1800da511  call    cs:__imp_CloseHandle
0x1800da517  test    eax, eax
0x1800da519  jz      short loc_1800DA54B
0x1800da51b  mov     ecx, esi; dwErrCode
0x1800da51d  call    cs:__imp_SetLastError
0x1800da523  mov     edx, 1A8h; unsigned int
0x1800da528  mov     qword ptr [rdi+8], 0
0x1800da530  lea     rcx, aHnsServiceComm; "HNS::Service::Common::Notify::INotifyab"...
0x1800da537  mov     rbx, [rsp+28h+arg_0]
0x1800da53c  mov     rsi, [rsp+28h+arg_8]
0x1800da541  add     rsp, 20h
0x1800da545  pop     rdi
0x1800da546  jmp     ?TraceSuccess@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceSuccess(char const *,uint)
0x1800da54b  mov     rcx, [rsp+28h]; this
0x1800da550  mov     edx, 0A0Bh; void *
0x1800da555  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
