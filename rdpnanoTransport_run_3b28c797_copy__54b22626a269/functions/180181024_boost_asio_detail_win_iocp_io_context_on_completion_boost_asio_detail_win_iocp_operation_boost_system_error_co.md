# boost::asio::detail::win_iocp_io_context::on_completion(boost::asio::detail::win_iocp_operation *,boost::system::error_code const &,ulong)

- ea: `0x180181024`
- end: `0x180181112`
- name: `?on_completion@win_iocp_io_context@detail@asio@boost@@QEAAXPEAVwin_iocp_operation@234@AEBVerror_code@system@4@K@Z`
- size: `238`
- prototype: `void __fastcall(boost::asio::detail::win_iocp_io_context *__hidden this, struct boost::asio::detail::win_iocp_operation *, const struct boost::system::error_code *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180181290`
- `0x18018146c`

## callees

- `0x180181024`
- `0x18032f050`

## import_xrefs

- `KERNEL32!PostQueuedCompletionStatus` at `0x1801810bc`
- `KERNEL32!PostQueuedCompletionStatus` at `0x1801810bc`
- `KERNEL32!EnterCriticalSection` at `0x1801810ca`
- `KERNEL32!EnterCriticalSection` at `0x1801810ca`
- `KERNEL32!LeaveCriticalSection` at `0x1801810ff`
- `KERNEL32!LeaveCriticalSection` at `0x1801810ff`

## pseudocode

```c
void __fastcall boost::asio::detail::win_iocp_io_context::on_completion(
        boost::asio::detail::win_iocp_io_context *this,
        struct boost::asio::detail::win_iocp_operation *a2,
        const struct boost::system::error_code *a3,
        int a4)
{
  int v4; // eax
  __int64 v5; // rsi
  void ***v8; // rax
  int v9; // eax
  __int64 v10; // rax

  v5 = (unsigned int)(v4 - 31);
  *((_DWORD *)a2 + 12) = v5;
  if ( *((_QWORD *)a3 + 2) )
  {
    v8 = &boost::system::detail::interop_cat_holder<void>::instance;
    if ( *((_QWORD *)a3 + 2) != v5 )
      v8 = (void ***)*((_QWORD *)a3 + 1);
  }
  else
  {
    v8 = &boost::system::detail::system_cat_holder<void>::instance;
  }
  *(_QWORD *)a2 = v8;
  if ( *((_QWORD *)a3 + 2) == v5 )
    v9 = *(_DWORD *)a3 + 1000 * (*((_QWORD *)a3 + 1) % 0x1FFFF7uLL);
  else
    v9 = *(_DWORD *)a3;
  *((_DWORD *)a2 + 5) = a4;
  *((_DWORD *)a2 + 4) = v9;
  if ( !PostQueuedCompletionStatus(*((HANDLE *)this + 6), 0, 2u, (LPOVERLAPPED)a2) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
    *((_QWORD *)a2 + 4) = 0;
    v10 = *((_QWORD *)this + 20);
    if ( v10 )
      *(_QWORD *)(v10 + 32) = a2;
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
0x180181024  mov     [rsp+arg_10], rbx
0x180181029  push    rbp
0x18018102a  push    rsi
0x18018102b  push    rdi
0x18018102c  mov     eax, 20h
0x180181031  call    _alloca_probe
0x180181036  sub     rsp, rax
0x180181039  lea     esi, [rax-1Fh]
0x18018103c  mov     rbx, rdx
0x18018103f  mov     [rdx+30h], esi
0x180181042  mov     rdi, rcx
0x180181045  cmp     qword ptr [r8+10h], 0
0x18018104a  jnz     short loc_180181055
0x18018104c  lea     rax, ?instance@?$system_cat_holder@X@detail@system@boost@@2Vsystem_error_category@234@B; boost::system::detail::system_error_category const boost::system::detail::system_cat_holder<void>::instance
0x180181053  jmp     short loc_180181066
0x180181055  lea     rax, ?instance@?$interop_cat_holder@X@detail@system@boost@@2Vinterop_error_category@234@B; boost::system::detail::interop_error_category const boost::system::detail::interop_cat_holder<void>::instance
0x18018105c  cmp     [r8+10h], rsi
0x180181060  jz      short loc_180181066
0x180181062  mov     rax, [r8+8]
0x180181066  mov     [rdx], rax
0x180181069  cmp     [r8+10h], rsi
0x18018106d  jz      short loc_180181074
0x18018106f  mov     eax, [r8]
0x180181072  jmp     short loc_1801810A8
0x180181074  mov     rcx, [r8+8]
0x180181078  mov     rax, 4800144005B3h
0x180181082  mul     rcx
0x180181085  mov     rax, rcx
0x180181088  sub     rax, rdx
0x18018108b  shr     rax, 1
0x18018108e  add     rax, rdx
0x180181091  shr     rax, 14h
0x180181095  imul    rax, 1FFFF7h
0x18018109c  sub     rcx, rax
0x18018109f  imul    eax, ecx, 3E8h
0x1801810a5  add     eax, [r8]
0x1801810a8  mov     [rbx+14h], r9d
0x1801810ac  xor     edx, edx; dwNumberOfBytesTransferred
0x1801810ae  mov     [rbx+10h], eax
0x1801810b1  mov     r9, rbx; lpOverlapped
0x1801810b4  mov     rcx, [rdi+30h]; CompletionPort
0x1801810b8  lea     r8d, [rdx+2]; dwCompletionKey
0x1801810bc  call    cs:__imp_PostQueuedCompletionStatus
0x1801810c2  test    eax, eax
0x1801810c4  jnz     short loc_180181105
0x1801810c6  lea     rcx, [rdi+68h]; lpCriticalSection
0x1801810ca  call    cs:__imp_EnterCriticalSection
0x1801810d0  mov     qword ptr [rbx+20h], 0
0x1801810d8  mov     rax, [rdi+0A0h]
0x1801810df  test    rax, rax
0x1801810e2  jz      short loc_1801810EA
0x1801810e4  mov     [rax+20h], rbx
0x1801810e8  jmp     short loc_1801810F1
0x1801810ea  mov     [rdi+98h], rbx
0x1801810f1  mov     [rdi+0A0h], rbx
0x1801810f8  lea     rcx, [rdi+68h]; lpCriticalSection
0x1801810fc  xchg    esi, [rdi+60h]
0x1801810ff  call    cs:__imp_LeaveCriticalSection
0x180181105  mov     rbx, [rsp+38h+arg_10]
0x18018110a  add     rsp, 20h
0x18018110e  pop     rdi
0x18018110f  pop     rsi
0x180181110  pop     rbp
0x180181111  retn
```
