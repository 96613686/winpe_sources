# boost::asio::detail::win_iocp_io_context::win_iocp_io_context(boost::asio::execution_context &,bool)

- ea: `0x1801645a0`
- end: `0x18016472d`
- name: `??0win_iocp_io_context@detail@asio@boost@@QEAA@AEAVexecution_context@23@_N@Z`
- size: `397`
- prototype: `__int64 __fastcall(boost::asio::detail::win_iocp_io_context *__hidden this, struct boost::asio::execution_context *, bool)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18015df7c`
- `0x18017d180`

## callees

- `0x18015dc8c`
- `0x18015fd98`
- `0x180161788`
- `0x180163f50`
- `0x1801645a0`
- `0x18016484c`
- `0x18016dbe4`
- `0x1801729e0`
- `0x18032f050`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18016467e`
- `KERNEL32!GetLastError` at `0x18016467e`
- `KERNEL32!CreateIoCompletionPort` at `0x18016466f`
- `KERNEL32!CreateIoCompletionPort` at `0x18016466f`

## string_xrefs

- `0x180164696`: `C:\__w\1\s\externals\vcpkg_installed\x64-windows-static\include\boost/asio/detail/impl/win_iocp_io_context.ipp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
boost::asio::detail::win_iocp_io_context *__fastcall boost::asio::detail::win_iocp_io_context::win_iocp_io_context(
        boost::asio::detail::win_iocp_io_context *this,
        struct boost::asio::execution_context *a2,
        char a3)
{
  DWORD v6; // ebx
  int v7; // eax
  HANDLE IoCompletionPort; // rax
  DWORD LastError; // eax
  const struct boost::source_location *v10; // r9
  struct boost::asio::detail::win_thread::func_base *v11; // rax
  _BYTE v13[8]; // [rsp+20h] [rbp-50h] BYREF
  boost::asio::detail::win_iocp_io_context *v14; // [rsp+28h] [rbp-48h] BYREF
  char v15[8]; // [rsp+30h] [rbp-40h] BYREF
  const char *v16; // [rsp+38h] [rbp-38h]
  int v17; // [rsp+40h] [rbp-30h]
  int v18; // [rsp+44h] [rbp-2Ch]
  _DWORD v19[4]; // [rsp+48h] [rbp-28h] BYREF
  __int64 v20; // [rsp+58h] [rbp-18h]
  boost::asio::detail::win_iocp_io_context *v21; // [rsp+60h] [rbp-10h]

  v21 = this;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = a2;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *(_QWORD *)this = &boost::asio::detail::win_iocp_io_context::`vftable';
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  v6 = -1;
  *((_DWORD *)this + 18) = -1;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_DWORD *)this + 24) = 0;
  boost::asio::detail::win_mutex::win_mutex((boost::asio::detail::win_iocp_io_context *)((char *)this + 104));
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 0;
  v14 = (boost::asio::detail::win_iocp_io_context *)boost::asio::detail::service_registry::use_service<boost::asio::config_service>(*((_QWORD *)a2 + 1));
  v7 = boost::asio::config::get<int>(&v14, "scheduler", "concurrency_hint", 0xFFFFFFFFLL);
  *((_DWORD *)this + 42) = v7;
  *((_QWORD *)this + 22) = 0;
  if ( v7 >= 0 )
    v6 = v7;
  IoCompletionPort = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, v6);
  *((_QWORD *)this + 6) = IoCompletionPort;
  if ( !IoCompletionPort )
  {
    LastError = GetLastError();
    boost::system::error_code::error_code(
      (boost::system::error_code *)v19,
      LastError,
      (const struct boost::system::error_category *)&boost::system::detail::system_cat_holder<void>::instance);
    *(_QWORD *)v15 = "C:\\__w\\1\\s\\externals\\vcpkg_installed\\x64-windows-static\\include\\boost/asio/detail/impl/win_"
                     "iocp_io_context.ipp";
    v16 = "__cdecl boost::asio::detail::win_iocp_io_context::win_iocp_io_context(class boost::asio::execution_context &,bool)";
    v17 = 104;
    v18 = 26;
    if ( (v20 & 1) != 0 && (v20 != 1 || v19[0]) )
      boost::asio::detail::do_throw_error(
        (boost::asio::detail *)v19,
        (const struct boost::system::error_code *)"iocp",
        v15,
        v10);
  }
  if ( a3 )
  {
    _InterlockedIncrement((volatile signed __int32 *)this + 14);
    v14 = this;
    v11 = (struct boost::asio::detail::win_thread::func_base *)boost::asio::detail::allocate_object<boost::asio::detail::win_thread::func<boost::asio::detail::win_iocp_io_context::thread_function,std::allocator<void>>,std::allocator<void>,boost::asio::detail::win_iocp_io_context::thread_function &,std::allocator<void> const &>(
                                                                 v13,
                                                                 &v14,
                                                                 v13);
    *((_QWORD *)this + 22) = boost::asio::detail::win_thread::start_thread(
                               (boost::asio::detail::win_thread *)&v14,
                               v11,
                               0);
  }
  return this;
}

```

## disassembly

```asm
0x1801645a0  mov     [rsp-28h+arg_10], rbx
0x1801645a5  push    rbp
0x1801645a6  push    rsi
0x1801645a7  push    rdi
0x1801645a8  push    r14
0x1801645aa  push    r15
0x1801645ac  mov     rbp, rsp
0x1801645af  mov     eax, 70h
0x1801645b4  call    _alloca_probe
0x1801645b9  sub     rsp, rax
0x1801645bc  mov     r14b, r8b
0x1801645bf  mov     rdi, rdx
0x1801645c2  mov     rsi, rcx
0x1801645c5  mov     [rbp+var_10], rcx
0x1801645c9  xor     r15d, r15d
0x1801645cc  mov     [rcx+8], r15
0x1801645d0  mov     [rcx+10h], r15
0x1801645d4  mov     [rcx+18h], rdx
0x1801645d8  mov     [rcx+20h], r15
0x1801645dc  mov     [rcx+28h], r15
0x1801645e0  lea     rax, ??_7win_iocp_io_context@detail@asio@boost@@6B@; const boost::asio::detail::win_iocp_io_context::`vftable'
0x1801645e7  mov     [rcx], rax
0x1801645ea  mov     [rcx+30h], r15
0x1801645ee  mov     [rcx+38h], r15
0x1801645f2  mov     [rcx+40h], r15
0x1801645f6  or      ebx, 0FFFFFFFFh
0x1801645f9  mov     [rcx+48h], ebx
0x1801645fc  mov     [rcx+50h], r15
0x180164600  mov     [rcx+58h], r15
0x180164604  mov     [rcx+60h], r15d
0x180164608  add     rcx, 68h ; 'h'; this
0x18016460c  call    ??0win_mutex@detail@asio@boost@@QEAA@XZ; boost::asio::detail::win_mutex::win_mutex(void)
0x180164611  nop
0x180164612  mov     [rsi+90h], r15
0x180164619  mov     [rsi+98h], r15
0x180164620  mov     [rsi+0A0h], r15
0x180164627  mov     rcx, [rdi+8]
0x18016462b  call    ??$use_service@Vconfig_service@asio@boost@@@service_registry@detail@asio@boost@@QEAAAEAVconfig_service@23@XZ; boost::asio::detail::service_registry::use_service<boost::asio::config_service>(void)
0x180164630  mov     [rbp+var_48], rax
0x180164634  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180164638  mov     r9d, edi
0x18016463b  lea     r8, aConcurrencyHin; "concurrency_hint"
0x180164642  lea     rdx, aScheduler; "scheduler"
0x180164649  lea     rcx, [rbp+var_48]
0x18016464d  call    ??$get@H@config@asio@boost@@QEBAHPEBD0H@Z; boost::asio::config::get<int>(char const *,char const *,int)
0x180164652  mov     [rsi+0A8h], eax
0x180164658  mov     [rsi+0B0h], r15
0x18016465f  test    eax, eax
0x180164661  cmovns  ebx, eax
0x180164664  mov     r9d, ebx; NumberOfConcurrentThreads
0x180164667  xor     r8d, r8d; CompletionKey
0x18016466a  xor     edx, edx; ExistingCompletionPort
0x18016466c  mov     rcx, rdi; FileHandle
0x18016466f  call    cs:__imp_CreateIoCompletionPort
0x180164675  mov     [rsi+30h], rax
0x180164679  test    rax, rax
0x18016467c  jnz     short loc_1801646CD
0x18016467e  call    cs:__imp_GetLastError
0x180164684  lea     r8, ?instance@?$system_cat_holder@X@detail@system@boost@@2Vsystem_error_category@234@B; struct boost::system::error_category *
0x18016468b  mov     edx, eax; int
0x18016468d  lea     rcx, [rbp+var_28]; this
0x180164691  call    ??0error_code@system@boost@@QEAA@HAEBVerror_category@12@@Z; boost::system::error_code::error_code(int,boost::system::error_category const &)
0x180164696  lea     rax, aCW1SExternalsV_8; "C:\\__w\\1\\s\\externals\\vcpkg_install"...
0x18016469d  mov     qword ptr [rbp+var_40], rax
0x1801646a1  lea     rax, aCdeclBoostAsio_0; "__cdecl boost::asio::detail::win_iocp_i"...
0x1801646a8  mov     [rbp+var_38], rax
0x1801646ac  mov     [rbp+var_30], 68h ; 'h'
0x1801646b3  mov     [rbp+var_2C], 1Ah
0x1801646ba  test    byte ptr [rbp+var_18], 1
0x1801646be  jz      short loc_1801646CD
0x1801646c0  cmp     [rbp+var_18], 1
0x1801646c5  jnz     short loc_180164718
0x1801646c7  cmp     [rbp+var_28], r15d
0x1801646cb  jnz     short loc_180164718
0x1801646cd  test    r14b, r14b
0x1801646d0  jz      short loc_180164701
0x1801646d2  lock inc dword ptr [rsi+38h]
0x1801646d6  mov     [rbp+var_48], rsi
0x1801646da  lea     r8, [rbp+var_50]
0x1801646de  lea     rdx, [rbp+var_48]
0x1801646e2  lea     rcx, [rbp+var_50]
0x1801646e6  call    ??$allocate_object@V?$func@Uthread_function@win_iocp_io_context@detail@asio@boost@@V?$allocator@X@std@@@win_thread@detail@asio@boost@@V?$allocator@X@std@@AEAUthread_function@win_iocp_io_context@345@AEBV67@@detail@asio@boost@@YAPEAV?$func@Uthread_function@win_iocp_io_context@detail@asio@boost@@V?$allocator@X@std@@@win_thread@012@AEBV?$allocator@X@std@@AEAUthread_function@win_iocp_io_context@012@0@Z; boost::asio::detail::allocate_object<boost::asio::detail::win_thread::func<boost::asio::detail::win_iocp_io_context::thread_function,std::allocator<void>>,std::allocator<void>,boost::asio::detail::win_iocp_io_context::thread_function &,std::allocator<void> const &>(std::allocator<void> const &,boost::asio::detail::win_iocp_io_context::thread_function &,std::allocator<void> const &)
0x1801646eb  mov     rdx, rax; struct boost::asio::detail::win_thread::func_base *
0x1801646ee  xor     r8d, r8d; unsigned int
0x1801646f1  lea     rcx, [rbp+var_48]; this
0x1801646f5  call    ?start_thread@win_thread@detail@asio@boost@@AEAAPEAVfunc_base@1234@PEAV51234@I@Z; boost::asio::detail::win_thread::start_thread(boost::asio::detail::win_thread::func_base *,uint)
0x1801646fa  mov     [rsi+0B0h], rax
0x180164701  mov     rax, rsi
0x180164704  mov     rbx, [rsp+70h+arg_10]
0x18016470c  add     rsp, 70h
0x180164710  pop     r15
0x180164712  pop     r14
0x180164714  pop     rdi
0x180164715  pop     rsi
0x180164716  pop     rbp
0x180164717  retn
0x180164718  lea     r8, [rbp+var_40]; char *
0x18016471c  lea     rdx, aIocp; "iocp"
0x180164723  lea     rcx, [rbp+var_28]; this
0x180164727  call    ?do_throw_error@detail@asio@boost@@YAXAEBVerror_code@system@3@PEBDAEBUsource_location@3@@Z; boost::asio::detail::do_throw_error(boost::system::error_code const &,char const *,boost::source_location const &)
```
