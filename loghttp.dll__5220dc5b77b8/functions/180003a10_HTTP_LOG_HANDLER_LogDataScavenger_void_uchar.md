# HTTP_LOG_HANDLER::LogDataScavenger(void *,uchar)

- ea: `0x180003a10`
- end: `0x180003b4e`
- name: `?LogDataScavenger@HTTP_LOG_HANDLER@@SAXPEAXE@Z`
- size: `318`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180003a10`
- `0x180005720`
- `0x180006010`

## import_xrefs

- `msvcrt!_ultow_s` at `0x180003ad4`
- `msvcrt!_ultow_s` at `0x180003af7`
- `msvcrt!_ultow_s` at `0x180003ad4`
- `msvcrt!_ultow_s` at `0x180003af7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180003a5f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180003a5f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003a40`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003a40`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003ab5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003ab5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003ae4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003ae4`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180003b24`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180003b24`

## pseudocode

```c
void __fastcall HTTP_LOG_HANDLER::LogDataScavenger(PVOID a1)
{
  unsigned int v1; // esi
  struct _LIST_ENTRY *Flink; // rdi
  struct _LIST_ENTRY *v3; // rbp
  int Blink; // ebx
  struct _LIST_ENTRY *v5; // rax
  struct _LIST_ENTRY *v6; // rcx
  DWORD CurrentProcessId; // eax
  __int128 v8; // [rsp+30h] [rbp-88h] BYREF
  wchar_t Buffer[12]; // [rsp+40h] [rbp-78h] BYREF
  wchar_t v10[12]; // [rsp+58h] [rbp-60h] BYREF

  v8 = 0;
  v1 = 0;
  EnterCriticalSection(&HTTP_LOG_HANDLER::sm_csLogDataListLock);
  Flink = HTTP_LOG_HANDLER::sm_LogDataListHead.Flink;
  if ( HTTP_LOG_HANDLER::sm_LogDataListHead.Flink != &HTTP_LOG_HANDLER::sm_LogDataListHead )
  {
    do
    {
      v3 = Flink->Flink;
      Blink = (int)Flink[5].Blink;
      if ( GetTickCount() - Blink > 0x1D4C0 )
      {
        v5 = Flink->Flink;
        if ( Flink->Flink->Blink != Flink || (v6 = Flink->Blink, v6->Flink != Flink) )
          __fastfail(3u);
        v6->Flink = v5;
        v5->Blink = v6;
        ((void (__fastcall *)(struct _LIST_ENTRY **, __int64))Flink[-1].Blink->Flink)(&Flink[-1].Blink, 1);
        ++v1;
      }
      Flink = v3;
    }
    while ( v3 != &HTTP_LOG_HANDLER::sm_LogDataListHead );
  }
  LeaveCriticalSection(&HTTP_LOG_HANDLER::sm_csLogDataListLock);
  if ( v1 )
  {
    _ultow_s(v1, Buffer, 0xBu, 10);
    *(_QWORD *)&v8 = Buffer;
    CurrentProcessId = GetCurrentProcessId();
    _ultow_s(CurrentProcessId, v10, 0xBu, 10);
    *((_QWORD *)&v8 + 1) = v10;
    EVENT_LOG::LogEvent((EVENT_LOG *)g_pEventLog, 0xC0000905, 2u, (const unsigned __int16 **const)&v8, 0);
  }
}

```

## disassembly

```asm
0x180003a10  push    rbx
0x180003a12  push    rbp
0x180003a13  push    rsi
0x180003a14  push    rdi
0x180003a15  push    r14
0x180003a17  push    r15
0x180003a19  sub     rsp, 88h
0x180003a20  mov     rax, cs:__security_cookie
0x180003a27  xor     rax, rsp
0x180003a2a  mov     [rsp+0B8h+var_48], rax
0x180003a2f  xorps   xmm0, xmm0
0x180003a32  lea     rcx, ?sm_csLogDataListLock@HTTP_LOG_HANDLER@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180003a39  movups  [rsp+0B8h+var_88], xmm0
0x180003a3e  xor     esi, esi
0x180003a40  call    cs:__imp_EnterCriticalSection
0x180003a46  mov     rdi, cs:?sm_LogDataListHead@HTTP_LOG_HANDLER@@0U_LIST_ENTRY@@A; _LIST_ENTRY HTTP_LOG_HANDLER::sm_LogDataListHead
0x180003a4d  lea     r15, ?sm_LogDataListHead@HTTP_LOG_HANDLER@@0U_LIST_ENTRY@@A; _LIST_ENTRY HTTP_LOG_HANDLER::sm_LogDataListHead
0x180003a54  cmp     rdi, r15
0x180003a57  jz      short loc_180003AAE
0x180003a59  mov     rbp, [rdi]
0x180003a5c  mov     ebx, [rdi+58h]
0x180003a5f  call    cs:__imp_GetTickCount
0x180003a65  sub     eax, ebx
0x180003a67  cmp     eax, 1D4C0h
0x180003a6c  jbe     short loc_180003AA6
0x180003a6e  mov     rax, [rdi]
0x180003a71  cmp     [rax+8], rdi
0x180003a75  jnz     loc_180003B47
0x180003a7b  mov     rcx, [rdi+8]
0x180003a7f  cmp     [rcx], rdi
0x180003a82  jnz     loc_180003B47
0x180003a88  mov     [rcx], rax
0x180003a8b  mov     edx, 1
0x180003a90  mov     [rax+8], rcx
0x180003a94  lea     rcx, [rdi-8]
0x180003a98  mov     rax, [rdi-8]
0x180003a9c  mov     rax, [rax]
0x180003a9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003aa4  inc     esi
0x180003aa6  mov     rdi, rbp
0x180003aa9  cmp     rbp, r15
0x180003aac  jnz     short loc_180003A59
0x180003aae  lea     rcx, ?sm_csLogDataListLock@HTTP_LOG_HANDLER@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180003ab5  call    cs:__imp_LeaveCriticalSection
0x180003abb  test    esi, esi
0x180003abd  jz      short loc_180003B2A
0x180003abf  mov     edi, 0Ah
0x180003ac4  lea     rdx, [rsp+0B8h+Buffer]; Buffer
0x180003ac9  mov     r9d, edi; Radix
0x180003acc  mov     ecx, esi; Value
0x180003ace  lea     ebx, [rdi+1]
0x180003ad1  mov     r8d, ebx; BufferCount
0x180003ad4  call    cs:__imp__ultow_s
0x180003ada  lea     rax, [rsp+0B8h+Buffer]
0x180003adf  mov     qword ptr [rsp+0B8h+var_88], rax
0x180003ae4  call    cs:__imp_GetCurrentProcessId
0x180003aea  mov     r9d, edi; Radix
0x180003aed  lea     rdx, [rsp+0B8h+var_60]; Buffer
0x180003af2  mov     ecx, eax; Value
0x180003af4  mov     r8d, ebx; BufferCount
0x180003af7  call    cs:__imp__ultow_s
0x180003afd  mov     rcx, cs:?g_pEventLog@@3PEAVEVENT_LOG@@EA; EVENT_LOG * g_pEventLog
0x180003b04  lea     rax, [rsp+0B8h+var_60]
0x180003b09  lea     r8d, [rdi-8]
0x180003b0d  mov     qword ptr [rsp+0B8h+var_88+8], rax
0x180003b12  lea     r9, [rsp+0B8h+var_88]
0x180003b17  mov     [rsp+0B8h+var_98], 0
0x180003b1f  mov     edx, 0C0000905h
0x180003b24  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x180003b2a  mov     rcx, [rsp+0B8h+var_48]
0x180003b2f  xor     rcx, rsp; StackCookie
0x180003b32  call    __security_check_cookie
0x180003b37  add     rsp, 88h
0x180003b3e  pop     r15
0x180003b40  pop     r14
0x180003b42  pop     rdi
0x180003b43  pop     rsi
0x180003b44  pop     rbp
0x180003b45  pop     rbx
0x180003b46  retn
0x180003b47  mov     ecx, 3
0x180003b4c  int     29h; Win8: RtlFailFast(ecx)
```
