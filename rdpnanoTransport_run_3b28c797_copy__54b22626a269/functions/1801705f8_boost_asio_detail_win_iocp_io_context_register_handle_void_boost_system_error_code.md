# boost::asio::detail::win_iocp_io_context::register_handle(void *,boost::system::error_code &)

- ea: `0x1801705f8`
- end: `0x18017068f`
- name: `?register_handle@win_iocp_io_context@detail@asio@boost@@QEAA?AVerror_code@system@4@PEAXAEAV564@@Z`
- size: `151`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18016c834`
- `0x18016da00`

## callees

- `0x180163f50`
- `0x1801705f8`
- `0x18032f050`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18017062c`
- `KERNEL32!GetLastError` at `0x18017062c`
- `KERNEL32!CreateIoCompletionPort` at `0x180170621`
- `KERNEL32!CreateIoCompletionPort` at `0x180170621`

## pseudocode

```c
__int64 __fastcall boost::asio::detail::win_iocp_io_context::register_handle(
        __int64 a1,
        __int64 a2,
        void *a3,
        __int64 a4)
{
  DWORD LastError; // eax
  __int64 v7; // rax
  __int64 result; // rax
  __int64 v9; // xmm1_8
  _BYTE v10[16]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v11; // [rsp+30h] [rbp-18h]

  if ( CreateIoCompletionPort(a3, *(HANDLE *)(a1 + 48), 0, 0) )
  {
    v11 = 0;
    *(_OWORD *)a4 = 0;
    *(_QWORD *)(a4 + 16) = v11;
  }
  else
  {
    LastError = GetLastError();
    v7 = boost::system::error_code::error_code(
           (boost::system::error_code *)v10,
           LastError,
           (const struct boost::system::error_category *)&boost::system::detail::system_cat_holder<void>::instance);
    *(_OWORD *)a4 = *(_OWORD *)v7;
    *(_QWORD *)(a4 + 16) = *(_QWORD *)(v7 + 16);
  }
  result = a2;
  v9 = *(_QWORD *)(a4 + 16);
  *(_OWORD *)a2 = *(_OWORD *)a4;
  *(_QWORD *)(a2 + 16) = v9;
  return result;
}

```

## disassembly

```asm
0x1801705f8  mov     [rsp+arg_0], rbx
0x1801705fd  push    rdi
0x1801705fe  mov     eax, 40h
0x180170603  call    _alloca_probe
0x180170608  sub     rsp, rax
0x18017060b  mov     rax, r8
0x18017060e  mov     rdi, rdx
0x180170611  mov     rdx, [rcx+30h]; ExistingCompletionPort
0x180170615  mov     rbx, r9
0x180170618  mov     rcx, rax; FileHandle
0x18017061b  xor     r9d, r9d; NumberOfConcurrentThreads
0x18017061e  xor     r8d, r8d; CompletionKey
0x180170621  call    cs:__imp_CreateIoCompletionPort
0x180170627  test    rax, rax
0x18017062a  jnz     short loc_180170657
0x18017062c  call    cs:__imp_GetLastError
0x180170632  mov     edx, eax; int
0x180170634  lea     r8, ?instance@?$system_cat_holder@X@detail@system@boost@@2Vsystem_error_category@234@B; struct boost::system::error_category *
0x18017063b  lea     rcx, [rsp+48h+var_28]; this
0x180170640  call    ??0error_code@system@boost@@QEAA@HAEBVerror_category@12@@Z; boost::system::error_code::error_code(int,boost::system::error_category const &)
0x180170645  movups  xmm0, xmmword ptr [rax]
0x180170648  movups  xmmword ptr [rbx], xmm0
0x18017064b  movsd   xmm1, qword ptr [rax+10h]
0x180170650  movsd   qword ptr [rbx+10h], xmm1
0x180170655  jmp     short loc_180170671
0x180170657  xorps   xmm0, xmm0
0x18017065a  mov     [rsp+48h+var_18], 0
0x180170663  movups  xmmword ptr [rbx], xmm0
0x180170666  movsd   xmm0, [rsp+48h+var_18]
0x18017066c  movsd   qword ptr [rbx+10h], xmm0
0x180170671  movups  xmm0, xmmword ptr [rbx]
0x180170674  mov     rax, rdi
0x180170677  movsd   xmm1, qword ptr [rbx+10h]
0x18017067c  mov     rbx, [rsp+48h+arg_0]
0x180170681  movups  xmmword ptr [rdi], xmm0
0x180170684  movsd   qword ptr [rdi+10h], xmm1
0x180170689  add     rsp, 40h
0x18017068d  pop     rdi
0x18017068e  retn
```
