# boost::asio::detail::win_iocp_io_context::~win_iocp_io_context(void)

- ea: `0x1801659dc`
- end: `0x180165a72`
- name: `??1win_iocp_io_context@detail@asio@boost@@UEAA@XZ`
- size: `150`
- prototype: `void __fastcall(boost::asio::detail::win_iocp_io_context *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18016583c`
- `0x180166990`
- `0x18039e82f`

## callees

- `0x180164f94`
- `0x1801659dc`
- `0x18016f00c`
- `0x180172d58`
- `0x18032f050`
- `0x1803449f0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180165a3b`
- `KERNEL32!CloseHandle` at `0x180165a51`
- `KERNEL32!CloseHandle` at `0x180165a3b`
- `KERNEL32!CloseHandle` at `0x180165a51`
- `KERNEL32!DeleteCriticalSection` at `0x180165a2c`
- `KERNEL32!DeleteCriticalSection` at `0x180165a2c`

## pseudocode

```c
void __fastcall boost::asio::detail::win_iocp_io_context::~win_iocp_io_context(
        boost::asio::detail::win_iocp_io_context *this)
{
  boost::asio::detail::win_thread *v2; // rdi
  void *v3; // rcx
  void *v4; // rcx

  *(_QWORD *)this = &boost::asio::detail::win_iocp_io_context::`vftable';
  v2 = (boost::asio::detail::win_iocp_io_context *)((char *)this + 176);
  if ( *((_QWORD *)this + 22) )
  {
    boost::asio::detail::win_iocp_io_context::stop(this);
    boost::asio::detail::win_thread::join(v2);
    if ( *(_QWORD *)v2 )
      goto LABEL_9;
  }
  boost::asio::detail::op_queue<boost::asio::detail::reactor_op>::~op_queue<boost::asio::detail::reactor_op>((char *)this + 152);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  v3 = (void *)*((_QWORD *)this + 11);
  if ( v3 )
    CloseHandle(v3);
  if ( *((_QWORD *)this + 10) )
LABEL_9:
    terminate();
  v4 = (void *)*((_QWORD *)this + 6);
  if ( v4 )
    CloseHandle(v4);
  *(_QWORD *)this = &boost::asio::execution_context::service::`vftable';
}

```

## disassembly

```asm
0x1801659dc  mov     [rsp+arg_0], rbx
0x1801659e1  push    rdi
0x1801659e2  mov     eax, 20h
0x1801659e7  call    _alloca_probe
0x1801659ec  sub     rsp, rax
0x1801659ef  mov     rbx, rcx
0x1801659f2  lea     rax, ??_7win_iocp_io_context@detail@asio@boost@@6B@; const boost::asio::detail::win_iocp_io_context::`vftable'
0x1801659f9  mov     [rcx], rax
0x1801659fc  lea     rdi, [rcx+0B0h]
0x180165a03  cmp     qword ptr [rdi], 0
0x180165a07  jz      short loc_180165A1C
0x180165a09  call    ?stop@win_iocp_io_context@detail@asio@boost@@QEAAXXZ; boost::asio::detail::win_iocp_io_context::stop(void)
0x180165a0e  mov     rcx, rdi; this
0x180165a11  call    ?join@win_thread@detail@asio@boost@@QEAAXXZ; boost::asio::detail::win_thread::join(void)
0x180165a16  cmp     qword ptr [rdi], 0
0x180165a1a  jnz     short loc_180165A6C
0x180165a1c  lea     rcx, [rbx+98h]
0x180165a23  call    ??1?$op_queue@Vreactor_op@detail@asio@boost@@@detail@asio@boost@@QEAA@XZ; boost::asio::detail::op_queue<boost::asio::detail::reactor_op>::~op_queue<boost::asio::detail::reactor_op>(void)
0x180165a28  lea     rcx, [rbx+68h]; lpCriticalSection
0x180165a2c  call    cs:__imp_DeleteCriticalSection
0x180165a32  mov     rcx, [rbx+58h]; hObject
0x180165a36  test    rcx, rcx
0x180165a39  jz      short loc_180165A41
0x180165a3b  call    cs:__imp_CloseHandle
0x180165a41  cmp     qword ptr [rbx+50h], 0
0x180165a46  jnz     short loc_180165A6C
0x180165a48  mov     rcx, [rbx+30h]; hObject
0x180165a4c  test    rcx, rcx
0x180165a4f  jz      short loc_180165A57
0x180165a51  call    cs:__imp_CloseHandle
0x180165a57  lea     rax, ??_7service@execution_context@asio@boost@@6B@; const boost::asio::execution_context::service::`vftable'
0x180165a5e  mov     [rbx], rax
0x180165a61  mov     rbx, [rsp+28h+arg_0]
0x180165a66  add     rsp, 20h
0x180165a6a  pop     rdi
0x180165a6b  retn
0x180165a6c  call    terminate
```
