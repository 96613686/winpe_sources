# boost::asio::detail::win_iocp_io_context::win_iocp_io_context(boost::asio::detail::win_iocp_io_context::internal,boost::asio::execution_context &)

- ea: `0x180164730`
- end: `0x18016484c`
- name: `??0win_iocp_io_context@detail@asio@boost@@QEAA@Uinternal@0123@AEAVexecution_context@23@@Z`
- size: `284`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18016412c`

## callees

- `0x180163f50`
- `0x180164730`
- `0x18016484c`
- `0x18016dbe4`
- `0x18032f050`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1801647d1`
- `KERNEL32!GetLastError` at `0x1801647d1`
- `KERNEL32!CreateIoCompletionPort` at `0x1801647c2`
- `KERNEL32!CreateIoCompletionPort` at `0x1801647c2`

## string_xrefs

- `0x1801647ea`: `C:\__w\1\s\externals\vcpkg_installed\x64-windows-static\include\boost/asio/detail/impl/win_iocp_io_context.ipp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall boost::asio::detail::win_iocp_io_context::win_iocp_io_context(__int64 a1, __int64 a2, __int64 a3)
{
  HANDLE IoCompletionPort; // rax
  DWORD LastError; // eax
  const struct boost::source_location *v6; // r9
  char v8[8]; // [rsp+20h] [rbp-48h] BYREF
  const char *v9; // [rsp+28h] [rbp-40h]
  int v10; // [rsp+30h] [rbp-38h]
  int v11; // [rsp+34h] [rbp-34h]
  _DWORD v12[4]; // [rsp+38h] [rbp-30h] BYREF
  __int64 v13; // [rsp+48h] [rbp-20h]
  __int64 v14; // [rsp+50h] [rbp-18h]

  v14 = a1;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = a3;
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  *(_QWORD *)a1 = &boost::asio::detail::win_iocp_io_context::`vftable';
  *(_QWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  *(_DWORD *)(a1 + 72) = -1;
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  *(_DWORD *)(a1 + 96) = 0;
  boost::asio::detail::win_mutex::win_mutex((boost::asio::detail::win_mutex *)(a1 + 104));
  *(_QWORD *)(a1 + 144) = 0;
  *(_QWORD *)(a1 + 152) = 0;
  *(_QWORD *)(a1 + 160) = 0;
  *(_DWORD *)(a1 + 168) = -1;
  *(_QWORD *)(a1 + 176) = 0;
  IoCompletionPort = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, 0xFFFFFFFF);
  *(_QWORD *)(a1 + 48) = IoCompletionPort;
  if ( !IoCompletionPort )
  {
    LastError = GetLastError();
    boost::system::error_code::error_code(
      (boost::system::error_code *)v12,
      LastError,
      (const struct boost::system::error_category *)&boost::system::detail::system_cat_holder<void>::instance);
    *(_QWORD *)v8 = "C:\\__w\\1\\s\\externals\\vcpkg_installed\\x64-windows-static\\include\\boost/asio/detail/impl/win_i"
                    "ocp_io_context.ipp";
    v9 = "__cdecl boost::asio::detail::win_iocp_io_context::win_iocp_io_context(struct boost::asio::detail::win_iocp_io_c"
         "ontext::internal,class boost::asio::execution_context &)";
    v10 = 136;
    v11 = 26;
    if ( (v13 & 1) != 0 && (v13 != 1 || v12[0]) )
      boost::asio::detail::do_throw_error(
        (boost::asio::detail *)v12,
        (const struct boost::system::error_code *)"iocp",
        v8,
        v6);
  }
  return a1;
}

```

## disassembly

```asm
0x180164730  mov     [rsp+arg_8], rbx
0x180164735  push    rsi
0x180164736  mov     eax, 60h
0x18016473b  call    _alloca_probe
0x180164740  sub     rsp, rax
0x180164743  mov     rbx, rcx
0x180164746  mov     [rsp+68h+var_18], rcx
0x18016474b  xor     esi, esi
0x18016474d  mov     [rcx+8], rsi
0x180164751  mov     [rcx+10h], rsi
0x180164755  mov     [rcx+18h], r8
0x180164759  mov     [rcx+20h], rsi
0x18016475d  mov     [rcx+28h], rsi
0x180164761  lea     rax, ??_7win_iocp_io_context@detail@asio@boost@@6B@; const boost::asio::detail::win_iocp_io_context::`vftable'
0x180164768  mov     [rcx], rax
0x18016476b  mov     [rcx+30h], rsi
0x18016476f  mov     [rcx+38h], rsi
0x180164773  mov     [rcx+40h], rsi
0x180164777  mov     dword ptr [rcx+48h], 0FFFFFFFFh
0x18016477e  mov     [rcx+50h], rsi
0x180164782  mov     [rcx+58h], rsi
0x180164786  mov     [rcx+60h], esi
0x180164789  add     rcx, 68h ; 'h'; this
0x18016478d  call    ??0win_mutex@detail@asio@boost@@QEAA@XZ; boost::asio::detail::win_mutex::win_mutex(void)
0x180164792  nop
0x180164793  mov     [rbx+90h], rsi
0x18016479a  mov     [rbx+98h], rsi
0x1801647a1  mov     [rbx+0A0h], rsi
0x1801647a8  or      rcx, 0FFFFFFFFFFFFFFFFh; FileHandle
0x1801647ac  mov     [rbx+0A8h], ecx
0x1801647b2  mov     [rbx+0B0h], rsi
0x1801647b9  or      r9d, 0FFFFFFFFh; NumberOfConcurrentThreads
0x1801647bd  xor     r8d, r8d; CompletionKey
0x1801647c0  xor     edx, edx; ExistingCompletionPort
0x1801647c2  call    cs:__imp_CreateIoCompletionPort
0x1801647c8  mov     [rbx+30h], rax
0x1801647cc  test    rax, rax
0x1801647cf  jnz     short loc_180164827
0x1801647d1  call    cs:__imp_GetLastError
0x1801647d7  lea     r8, ?instance@?$system_cat_holder@X@detail@system@boost@@2Vsystem_error_category@234@B; struct boost::system::error_category *
0x1801647de  mov     edx, eax; int
0x1801647e0  lea     rcx, [rsp+68h+var_30]; this
0x1801647e5  call    ??0error_code@system@boost@@QEAA@HAEBVerror_category@12@@Z; boost::system::error_code::error_code(int,boost::system::error_category const &)
0x1801647ea  lea     rax, aCW1SExternalsV_8; "C:\\__w\\1\\s\\externals\\vcpkg_install"...
0x1801647f1  mov     qword ptr [rsp+68h+var_48], rax
0x1801647f6  lea     rax, aCdeclBoostAsio_2; "__cdecl boost::asio::detail::win_iocp_i"...
0x1801647fd  mov     [rsp+68h+var_40], rax
0x180164802  mov     [rsp+68h+var_38], 88h
0x18016480a  mov     [rsp+68h+var_34], 1Ah
0x180164812  test    byte ptr [rsp+68h+var_20], 1
0x180164817  jz      short loc_180164827
0x180164819  cmp     [rsp+68h+var_20], 1
0x18016481f  jnz     short loc_180164835
0x180164821  cmp     [rsp+68h+var_30], esi
0x180164825  jnz     short loc_180164835
0x180164827  mov     rax, rbx
0x18016482a  mov     rbx, [rsp+68h+arg_8]
0x18016482f  add     rsp, 60h
0x180164833  pop     rsi
0x180164834  retn
0x180164835  lea     r8, [rsp+68h+var_48]; char *
0x18016483a  lea     rdx, aIocp; "iocp"
0x180164841  lea     rcx, [rsp+68h+var_30]; this
0x180164846  call    ?do_throw_error@detail@asio@boost@@YAXAEBVerror_code@system@3@PEBDAEBUsource_location@3@@Z; boost::asio::detail::do_throw_error(boost::system::error_code const &,char const *,boost::source_location const &)
```
