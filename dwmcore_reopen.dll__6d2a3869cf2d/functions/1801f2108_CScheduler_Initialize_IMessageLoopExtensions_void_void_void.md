# CScheduler::Initialize(IMessageLoopExtensions *,void *,void *,void *)

- ea: `0x1801f2108`
- end: `0x1801f21ad`
- name: `?Initialize@CScheduler@@QEAAJPEAUIMessageLoopExtensions@@PEAX11@Z`
- size: `165`
- prototype: `__int64 __fastcall(CScheduler *__hidden this, struct IMessageLoopExtensions *, void *, void *, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1801f1970`

## callees

- `0x180050270`
- `0x18015adb4`
- `0x1801f2108`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801f2129`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801f2129`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801f2144`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801f2144`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x1801f2136`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x1801f2136`

## pseudocode

```c
__int64 __fastcall CScheduler::Initialize(
        CScheduler *this,
        struct IMessageLoopExtensions *a2,
        void *a3,
        void *a4,
        void *a5)
{
  HANDLE WaitableTimerW; // rax
  HANDLE v9; // rsi
  signed int LastError; // eax
  signed int v11; // ebx

  *(_QWORD *)this = a5;
  SetLastError(0);
  WaitableTimerW = CreateWaitableTimerW(0, 0, 0);
  v9 = WaitableTimerW;
  if ( WaitableTimerW )
  {
    v11 = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      (char *)this + 8,
      WaitableTimerW);
    *((_QWORD *)this + 3) = a3;
    *((_QWORD *)this + 4) = a4;
    *((_QWORD *)this + 5) = v9;
  }
  else
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    if ( v11 >= 0 )
      v11 = -2003304445;
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v11, 0x1Du, 0);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1801f2108  push    rbx
0x1801f210a  push    rbp
0x1801f210b  push    rsi
0x1801f210c  push    rdi
0x1801f210d  push    r14
0x1801f210f  sub     rsp, 30h
0x1801f2113  mov     rax, [rsp+58h+arg_20]
0x1801f211b  mov     rdi, rcx
0x1801f211e  mov     [rcx], rax
0x1801f2121  mov     rbp, r9
0x1801f2124  xor     ecx, ecx; dwErrCode
0x1801f2126  mov     r14, r8
0x1801f2129  call    cs:__imp_SetLastError
0x1801f212f  xor     r8d, r8d; lpTimerName
0x1801f2132  xor     edx, edx; bManualReset
0x1801f2134  xor     ecx, ecx; lpTimerAttributes
0x1801f2136  call    cs:__imp_CreateWaitableTimerW
0x1801f213c  mov     rsi, rax
0x1801f213f  test    rax, rax
0x1801f2142  jnz     short loc_1801F2186
0x1801f2144  call    cs:__imp_GetLastError
0x1801f214a  mov     ebx, eax
0x1801f214c  test    eax, eax
0x1801f214e  jle     short loc_1801F2159
0x1801f2150  movzx   ebx, ax
0x1801f2153  or      ebx, 80070000h
0x1801f2159  test    ebx, ebx
0x1801f215b  mov     [rsp+58h+var_30], 0; void *
0x1801f2164  mov     eax, 88980003h
0x1801f2169  mov     [rsp+58h+var_38], 1Dh; unsigned int
0x1801f2171  cmovns  ebx, eax
0x1801f2174  xor     edx, edx; int *
0x1801f2176  mov     r9d, ebx; int
0x1801f2179  xor     r8d, r8d; unsigned int
0x1801f217c  lea     ecx, [rdx+14h]; unsigned int
0x1801f217f  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1801f2184  jmp     short loc_1801F21A0
0x1801f2186  xor     ebx, ebx
0x1801f2188  lea     rcx, [rdi+8]
0x1801f218c  mov     rdx, rsi
0x1801f218f  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1801f2194  mov     [rdi+18h], r14
0x1801f2198  mov     [rdi+20h], rbp
0x1801f219c  mov     [rdi+28h], rsi
0x1801f21a0  mov     eax, ebx
0x1801f21a2  add     rsp, 30h
0x1801f21a6  pop     r14
0x1801f21a8  pop     rdi
0x1801f21a9  pop     rsi
0x1801f21aa  pop     rbp
0x1801f21ab  pop     rbx
0x1801f21ac  retn
```
