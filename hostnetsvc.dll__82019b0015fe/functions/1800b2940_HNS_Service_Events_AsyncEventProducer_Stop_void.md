# HNS::Service::Events::AsyncEventProducer::Stop(void)

- ea: `0x1800b2940`
- end: `0x1800b29ed`
- name: `?Stop@AsyncEventProducer@Events@Service@HNS@@IEAAXXZ`
- size: `173`
- prototype: `void __fastcall(HNS::Service::Events::AsyncEventProducer *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800b2c80`
- `0x1800be9a0`
- `0x1800d0270`
- `0x1800edd20`

## callees

- `0x180064018`
- `0x1800b2940`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b2991`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b29bf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b2991`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b29bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2962`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b29a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2962`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b29a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b29b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b29b3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800b2972`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800b2972`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800b2980`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800b2980`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800b2989`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800b2989`

## pseudocode

```c
void __fastcall HNS::Service::Events::AsyncEventProducer::Stop(HNS::Service::Events::AsyncEventProducer *this)
{
  struct _TP_WAIT *v2; // rsi
  DWORD LastError; // ebx
  void *v4; // rbx
  DWORD v5; // esi
  unsigned int v6; // r8d
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *((_DWORD *)this + 16) = 2;
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
}

```

## disassembly

```asm
0x1800b2940  mov     [rsp+arg_0], rbx
0x1800b2945  mov     [rsp+arg_8], rsi
0x1800b294a  push    rdi
0x1800b294b  sub     rsp, 20h
0x1800b294f  mov     dword ptr [rcx+40h], 2
0x1800b2956  mov     rdi, rcx
0x1800b2959  mov     rsi, [rcx+10h]
0x1800b295d  test    rsi, rsi
0x1800b2960  jz      short loc_1800B2997
0x1800b2962  call    cs:__imp_GetLastError
0x1800b2968  xor     r8d, r8d; pftTimeout
0x1800b296b  xor     edx, edx; h
0x1800b296d  mov     rcx, rsi; pwa
0x1800b2970  mov     ebx, eax
0x1800b2972  call    cs:__imp_SetThreadpoolWait
0x1800b2978  mov     edx, 1; fCancelPendingCallbacks
0x1800b297d  mov     rcx, rsi; pwa
0x1800b2980  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800b2986  mov     rcx, rsi; pwa
0x1800b2989  call    cs:__imp_CloseThreadpoolWait
0x1800b298f  mov     ecx, ebx; dwErrCode
0x1800b2991  call    cs:__imp_SetLastError
0x1800b2997  mov     qword ptr [rdi+10h], 0
0x1800b299f  mov     rbx, [rdi+8]
0x1800b29a3  test    rbx, rbx
0x1800b29a6  jz      short loc_1800B29C5
0x1800b29a8  call    cs:__imp_GetLastError
0x1800b29ae  mov     rcx, rbx; hObject
0x1800b29b1  mov     esi, eax
0x1800b29b3  call    cs:__imp_CloseHandle
0x1800b29b9  test    eax, eax
0x1800b29bb  jz      short loc_1800B29DD
0x1800b29bd  mov     ecx, esi; dwErrCode
0x1800b29bf  call    cs:__imp_SetLastError
0x1800b29c5  mov     rbx, [rsp+28h+arg_0]
0x1800b29ca  mov     rsi, [rsp+28h+arg_8]
0x1800b29cf  mov     qword ptr [rdi+8], 0
0x1800b29d7  add     rsp, 20h
0x1800b29db  pop     rdi
0x1800b29dc  retn
0x1800b29dd  mov     rcx, [rsp+28h]; this
0x1800b29e2  mov     edx, 0A0Bh; void *
0x1800b29e7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
