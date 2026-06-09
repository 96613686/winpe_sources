# boost::asio::detail::win_iocp_io_context::post_deferred_completion(boost::asio::detail::win_iocp_operation *)

- ea: `0x180170284`
- end: `0x180170307`
- name: `?post_deferred_completion@win_iocp_io_context@detail@asio@boost@@QEAAXPEAVwin_iocp_operation@234@@Z`
- size: `131`
- prototype: `void __fastcall(boost::asio::detail::win_iocp_io_context *__hidden this, struct boost::asio::detail::win_iocp_operation *)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18015fb9c`
- `0x18016ac50`
- `0x18016ca00`
- `0x18017113c`
- `0x1801723ec`
- `0x180172874`
- `0x18017b5f0`

## callees

- `0x180170284`
- `0x18032f050`

## import_xrefs

- `KERNEL32!PostQueuedCompletionStatus` at `0x1801702b1`
- `KERNEL32!PostQueuedCompletionStatus` at `0x1801702b1`
- `KERNEL32!EnterCriticalSection` at `0x1801702bf`
- `KERNEL32!EnterCriticalSection` at `0x1801702bf`
- `KERNEL32!LeaveCriticalSection` at `0x1801702f4`
- `KERNEL32!LeaveCriticalSection` at `0x1801702f4`

## pseudocode

```c
void __fastcall boost::asio::detail::win_iocp_io_context::post_deferred_completion(
        boost::asio::detail::win_iocp_io_context *this,
        struct boost::asio::detail::win_iocp_operation *a2)
{
  int v2; // eax
  __int32 v3; // esi
  __int64 v6; // rax

  v3 = v2 - 31;
  *((_DWORD *)a2 + 12) = v2 - 31;
  if ( !PostQueuedCompletionStatus(*((HANDLE *)this + 6), 0, 0, (LPOVERLAPPED)a2) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
    *((_QWORD *)a2 + 4) = 0;
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
0x180170284  mov     [rsp+arg_10], rbx
0x180170289  push    rbp
0x18017028a  push    rsi
0x18017028b  push    rdi
0x18017028c  mov     eax, 20h
0x180170291  call    _alloca_probe
0x180170296  sub     rsp, rax
0x180170299  lea     esi, [rax-1Fh]
0x18017029c  mov     rdi, rdx
0x18017029f  mov     [rdx+30h], esi
0x1801702a2  mov     rbx, rcx
0x1801702a5  mov     rcx, [rcx+30h]; CompletionPort
0x1801702a9  mov     r9, rdx; lpOverlapped
0x1801702ac  xor     edx, edx; dwNumberOfBytesTransferred
0x1801702ae  xor     r8d, r8d; dwCompletionKey
0x1801702b1  call    cs:__imp_PostQueuedCompletionStatus
0x1801702b7  test    eax, eax
0x1801702b9  jnz     short loc_1801702FA
0x1801702bb  lea     rcx, [rbx+68h]; lpCriticalSection
0x1801702bf  call    cs:__imp_EnterCriticalSection
0x1801702c5  mov     qword ptr [rdi+20h], 0
0x1801702cd  mov     rax, [rbx+0A0h]
0x1801702d4  test    rax, rax
0x1801702d7  jz      short loc_1801702DF
0x1801702d9  mov     [rax+20h], rdi
0x1801702dd  jmp     short loc_1801702E6
0x1801702df  mov     [rbx+98h], rdi
0x1801702e6  mov     [rbx+0A0h], rdi
0x1801702ed  lea     rcx, [rbx+68h]; lpCriticalSection
0x1801702f1  xchg    esi, [rbx+60h]
0x1801702f4  call    cs:__imp_LeaveCriticalSection
0x1801702fa  mov     rbx, [rsp+38h+arg_10]
0x1801702ff  add     rsp, 20h
0x180170303  pop     rdi
0x180170304  pop     rsi
0x180170305  pop     rbp
0x180170306  retn
```
