# boost::asio::detail::win_iocp_io_context::on_completion(boost::asio::detail::win_iocp_operation *,ulong,ulong)

- ea: `0x18016f9fc`
- end: `0x18016fa92`
- name: `?on_completion@win_iocp_io_context@detail@asio@boost@@QEAAXPEAVwin_iocp_operation@234@KK@Z`
- size: `150`
- prototype: `void __fastcall(boost::asio::detail::win_iocp_io_context *__hidden this, struct boost::asio::detail::win_iocp_operation *, unsigned int, unsigned int)`
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

- `0x18016f9fc`
- `0x18032f050`

## import_xrefs

- `KERNEL32!PostQueuedCompletionStatus` at `0x18016fa3c`
- `KERNEL32!PostQueuedCompletionStatus` at `0x18016fa3c`
- `KERNEL32!EnterCriticalSection` at `0x18016fa4a`
- `KERNEL32!EnterCriticalSection` at `0x18016fa4a`
- `KERNEL32!LeaveCriticalSection` at `0x18016fa7f`
- `KERNEL32!LeaveCriticalSection` at `0x18016fa7f`

## pseudocode

```c
void __fastcall boost::asio::detail::win_iocp_io_context::on_completion(
        boost::asio::detail::win_iocp_io_context *this,
        struct boost::asio::detail::win_iocp_operation *a2,
        int a3,
        int a4)
{
  int v4; // eax
  __int32 v5; // esi
  __int64 v8; // rax

  v5 = v4 - 31;
  *((_DWORD *)a2 + 5) = a4;
  *((_DWORD *)a2 + 4) = a3;
  *(_QWORD *)a2 = &boost::system::detail::system_cat_holder<void>::instance;
  *((_DWORD *)a2 + 12) = v4 - 31;
  if ( !PostQueuedCompletionStatus(*((HANDLE *)this + 6), 0, (unsigned int)(v4 - 31 + 1), (LPOVERLAPPED)a2) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
    *((_QWORD *)a2 + 4) = 0;
    v8 = *((_QWORD *)this + 20);
    if ( v8 )
      *(_QWORD *)(v8 + 32) = a2;
    else
      *((_QWORD *)this + 19) = a2;
    *((_QWORD *)this + 20) = a2;
    _InterlockedExchange((volatile __int32 *)this + 24, v5);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  }
}

```

## disassembly

```asm
0x18016f9fc  mov     [rsp+arg_10], rbx
0x18016fa01  push    rbp
0x18016fa02  push    rsi
0x18016fa03  push    rdi
0x18016fa04  mov     eax, 20h
0x18016fa09  call    _alloca_probe
0x18016fa0e  sub     rsp, rax
0x18016fa11  lea     esi, [rax-1Fh]
0x18016fa14  mov     [rdx+14h], r9d
0x18016fa18  mov     [rdx+10h], r8d
0x18016fa1c  lea     rax, ?instance@?$system_cat_holder@X@detail@system@boost@@2Vsystem_error_category@234@B; boost::system::detail::system_error_category const boost::system::detail::system_cat_holder<void>::instance
0x18016fa23  mov     [rdx], rax
0x18016fa26  lea     r8d, [rsi+1]; dwCompletionKey
0x18016fa2a  mov     [rdx+30h], esi
0x18016fa2d  mov     rdi, rdx
0x18016fa30  mov     rbx, rcx
0x18016fa33  mov     r9, rdx; lpOverlapped
0x18016fa36  mov     rcx, [rcx+30h]; CompletionPort
0x18016fa3a  xor     edx, edx; dwNumberOfBytesTransferred
0x18016fa3c  call    cs:__imp_PostQueuedCompletionStatus
0x18016fa42  test    eax, eax
0x18016fa44  jnz     short loc_18016FA85
0x18016fa46  lea     rcx, [rbx+68h]; lpCriticalSection
0x18016fa4a  call    cs:__imp_EnterCriticalSection
0x18016fa50  mov     qword ptr [rdi+20h], 0
0x18016fa58  mov     rax, [rbx+0A0h]
0x18016fa5f  test    rax, rax
0x18016fa62  jz      short loc_18016FA6A
0x18016fa64  mov     [rax+20h], rdi
0x18016fa68  jmp     short loc_18016FA71
0x18016fa6a  mov     [rbx+98h], rdi
0x18016fa71  mov     [rbx+0A0h], rdi
0x18016fa78  lea     rcx, [rbx+68h]; lpCriticalSection
0x18016fa7c  xchg    esi, [rbx+60h]
0x18016fa7f  call    cs:__imp_LeaveCriticalSection
0x18016fa85  mov     rbx, [rsp+38h+arg_10]
0x18016fa8a  add     rsp, 20h
0x18016fa8e  pop     rdi
0x18016fa8f  pop     rsi
0x18016fa90  pop     rbp
0x18016fa91  retn
```
