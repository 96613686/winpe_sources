# boost::asio::detail::win_iocp_io_context::on_pending(boost::asio::detail::win_iocp_operation *)

- ea: `0x18016fa94`
- end: `0x18016fb20`
- name: `?on_pending@win_iocp_io_context@detail@asio@boost@@QEAAXPEAVwin_iocp_operation@234@@Z`
- size: `140`
- prototype: `void __fastcall(boost::asio::detail::win_iocp_io_context *__hidden this, struct boost::asio::detail::win_iocp_operation *)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1801723ec`
- `0x18017276c`
- `0x1801728f0`
- `0x18017c5f8`
- `0x18017c6f4`
- `0x180181290`
- `0x18018146c`

## callees

- `0x18016fa94`
- `0x18032f050`

## import_xrefs

- `KERNEL32!PostQueuedCompletionStatus` at `0x18016faca`
- `KERNEL32!PostQueuedCompletionStatus` at `0x18016faca`
- `KERNEL32!EnterCriticalSection` at `0x18016fad8`
- `KERNEL32!EnterCriticalSection` at `0x18016fad8`
- `KERNEL32!LeaveCriticalSection` at `0x18016fb0d`
- `KERNEL32!LeaveCriticalSection` at `0x18016fb0d`

## pseudocode

```c
void __fastcall boost::asio::detail::win_iocp_io_context::on_pending(
        boost::asio::detail::win_iocp_io_context *this,
        struct _OVERLAPPED *a2)
{
  int v2; // eax
  __int32 v3; // esi
  __int64 v6; // rax

  v3 = v2 - 31;
  if ( _InterlockedCompareExchange((volatile signed __int32 *)&a2[1].16, v2 - 31, 0) == v2 - 31
    && !PostQueuedCompletionStatus(*((HANDLE *)this + 6), 0, (unsigned int)(v3 + 1), a2) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
    a2[1].Internal = 0;
    v6 = *((_QWORD *)this + 20);
    if ( v6 )
      *(_QWORD *)(v6 + 32) = a2;
    else
      *((_QWORD *)this + 19) = a2;
    *((_QWORD *)this + 20) = a2;
    _InterlockedExchange((volatile __int32 *)this + 24, v3);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  }
}

```

## disassembly

```asm
0x18016fa94  mov     [rsp+arg_10], rbx
0x18016fa99  push    rbp
0x18016fa9a  push    rsi
0x18016fa9b  push    rdi
0x18016fa9c  mov     eax, 20h
0x18016faa1  call    _alloca_probe
0x18016faa6  sub     rsp, rax
0x18016faa9  lea     esi, [rax-1Fh]
0x18016faac  mov     rdi, rdx
0x18016faaf  xor     eax, eax
0x18016fab1  mov     rbx, rcx
0x18016fab4  lock cmpxchg [rdx+30h], esi
0x18016fab9  cmp     eax, esi
0x18016fabb  jnz     short loc_18016FB13
0x18016fabd  mov     rcx, [rcx+30h]; CompletionPort
0x18016fac1  lea     r8d, [rsi+1]; dwCompletionKey
0x18016fac5  mov     r9, rdx; lpOverlapped
0x18016fac8  xor     edx, edx; dwNumberOfBytesTransferred
0x18016faca  call    cs:__imp_PostQueuedCompletionStatus
0x18016fad0  test    eax, eax
0x18016fad2  jnz     short loc_18016FB13
0x18016fad4  lea     rcx, [rbx+68h]; lpCriticalSection
0x18016fad8  call    cs:__imp_EnterCriticalSection
0x18016fade  mov     qword ptr [rdi+20h], 0
0x18016fae6  mov     rax, [rbx+0A0h]
0x18016faed  test    rax, rax
0x18016faf0  jz      short loc_18016FAF8
0x18016faf2  mov     [rax+20h], rdi
0x18016faf6  jmp     short loc_18016FAFF
0x18016faf8  mov     [rbx+98h], rdi
0x18016faff  mov     [rbx+0A0h], rdi
0x18016fb06  lea     rcx, [rbx+68h]; lpCriticalSection
0x18016fb0a  xchg    esi, [rbx+60h]
0x18016fb0d  call    cs:__imp_LeaveCriticalSection
0x18016fb13  mov     rbx, [rsp+38h+arg_10]
0x18016fb18  add     rsp, 20h
0x18016fb1c  pop     rdi
0x18016fb1d  pop     rsi
0x18016fb1e  pop     rbp
0x18016fb1f  retn
```
