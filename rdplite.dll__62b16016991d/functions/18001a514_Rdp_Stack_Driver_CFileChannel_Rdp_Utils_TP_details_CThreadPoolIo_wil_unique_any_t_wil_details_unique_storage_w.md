# Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CThreadPoolIo<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&Rdp::Utils::TP::details::DestroyThreadpoolIo(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>>>>::StartWrite(Rdp::Stack::Driver::IoBuffer *)

- ea: `0x18001a514`
- end: `0x18001a5f0`
- name: `?StartWrite@?$CFileChannel@V?$CThreadPoolIo@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_IO@@P6AXPEAU1@@Z$1?DestroyThreadpoolIo@details@TP@Utils@Rdp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@TP@Utils@Rdp@@@Driver@Stack@Rdp@@QEAA_NPEAUIoBuffer@234@@Z`
- size: `220`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x180019348`

## callees

- `0x18000f2e0`
- `0x18000fbe4`
- `0x180010984`
- `0x180012188`
- `0x18001a514`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a585`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a59f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a585`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a59f`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18001a599`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18001a599`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18001a555`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18001a555`

## string_xrefs

- `0x18001a5ad`: `Failed to write from I/O channel`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CThreadPoolIo<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&void Rdp::Utils::TP::details::DestroyThreadpoolIo(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>>>>::StartWrite(
        __int64 a1,
        __int64 a2)
{
  int v4; // r9d
  DWORD LastError; // eax
  const char *v7; // [rsp+28h] [rbp-20h]
  _BYTE v8[24]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  std::shared_lock<Rdp::Utils::Synchronization::rundown_mutex>::shared_lock<Rdp::Utils::Synchronization::rundown_mutex>(
    v8,
    a1 + 16);
  if ( v8[8] && (unsigned __int64)(*(_QWORD *)a1 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    StartThreadpoolIo(**(PTP_IO **)(a1 + 8));
    *(_DWORD *)(a2 + 32) = 1;
    *(_OWORD *)a2 = 0;
    *(_OWORD *)(a2 + 16) = 0;
    if ( !(unsigned int)Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CThreadPoolIo<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&void Rdp::Utils::TP::details::DestroyThreadpoolIo(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>>>>::InternalWriteFile(
                          *(_QWORD *)a1,
                          *(_QWORD *)(a2 + 40),
                          *(_DWORD *)(a2 + 60),
                          v4,
                          (LPOVERLAPPED)a2)
      && GetLastError() != 997 )
    {
      CancelThreadpoolIo(**(PTP_IO **)(a1 + 8));
      LastError = GetLastError();
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x227,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\inc\\FileChannel.h",
        (const char *)LastError,
        (unsigned int)"Failed to write from I/O channel",
        v7);
    }
    std::shared_lock<Rdp::Utils::Synchronization::rundown_mutex>::~shared_lock<Rdp::Utils::Synchronization::rundown_mutex>(v8);
    return 1;
  }
  else
  {
    std::shared_lock<Rdp::Utils::Synchronization::rundown_mutex>::~shared_lock<Rdp::Utils::Synchronization::rundown_mutex>(v8);
    return 0;
  }
}

```

## disassembly

```asm
0x18001a514  mov     [rsp+arg_0], rbx
0x18001a519  push    rdi
0x18001a51a  sub     rsp, 40h
0x18001a51e  mov     rdi, rdx
0x18001a521  mov     rbx, rcx
0x18001a524  lea     rdx, [rcx+10h]
0x18001a528  lea     rcx, [rsp+48h+var_18]
0x18001a52d  call    ??0?$shared_lock@Vrundown_mutex@Synchronization@Utils@Rdp@@@std@@QEAA@AEAVrundown_mutex@Synchronization@Utils@Rdp@@Utry_to_lock_t@1@@Z; std::shared_lock<Rdp::Utils::Synchronization::rundown_mutex>::shared_lock<Rdp::Utils::Synchronization::rundown_mutex>(Rdp::Utils::Synchronization::rundown_mutex &,std::try_to_lock_t)
0x18001a532  nop
0x18001a533  cmp     [rsp+48h+var_10], 0
0x18001a538  jz      loc_18001A5D9
0x18001a53e  mov     rax, [rbx]
0x18001a541  dec     rax
0x18001a544  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001a548  ja      loc_18001A5D9
0x18001a54e  mov     rcx, [rbx+8]
0x18001a552  mov     rcx, [rcx]; pio
0x18001a555  call    cs:__imp_StartThreadpoolIo
0x18001a55b  mov     dword ptr [rdi+20h], 1
0x18001a562  xorps   xmm0, xmm0
0x18001a565  movups  xmmword ptr [rdi], xmm0
0x18001a568  movups  xmmword ptr [rdi+10h], xmm0
0x18001a56c  mov     [rsp+48h+var_28], rdi; LPOVERLAPPED
0x18001a571  mov     r8d, [rdi+3Ch]; int
0x18001a575  mov     rdx, [rdi+28h]; int
0x18001a579  mov     rcx, [rbx]; int
0x18001a57c  call    ?InternalWriteFile@?$CFileChannel@V?$CThreadPoolIo@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_IO@@P6AXPEAU1@@Z$1?DestroyThreadpoolIo@details@TP@Utils@Rdp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@TP@Utils@Rdp@@@Driver@Stack@Rdp@@CAHPEAX0KPEAKPEAU_OVERLAPPED@@@Z; Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CThreadPoolIo<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&Rdp::Utils::TP::details::DestroyThreadpoolIo(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>>>>::InternalWriteFile(void *,void *,ulong,ulong *,_OVERLAPPED *)
0x18001a581  test    eax, eax
0x18001a583  jnz     short loc_18001A5CB
0x18001a585  call    cs:__imp_GetLastError
0x18001a58b  cmp     eax, 3E5h
0x18001a590  jz      short loc_18001A5CB
0x18001a592  mov     rcx, [rbx+8]
0x18001a596  mov     rcx, [rcx]; pio
0x18001a599  call    cs:__imp_CancelThreadpoolIo
0x18001a59f  call    cs:__imp_GetLastError
0x18001a5a5  mov     r9d, eax; char *
0x18001a5a8  mov     rcx, [rsp+48h]; this
0x18001a5ad  lea     rax, aFailedToWriteF; "Failed to write from I/O channel"
0x18001a5b4  mov     [rsp+48h+var_28], rax; unsigned int
0x18001a5b9  lea     r8, aOnecoreuapTerm_13; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18001a5c0  mov     edx, 227h; void *
0x18001a5c5  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18001a5cb  lea     rcx, [rsp+48h+var_18]
0x18001a5d0  call    ??1?$shared_lock@Vrundown_mutex@Synchronization@Utils@Rdp@@@std@@QEAA@XZ; std::shared_lock<Rdp::Utils::Synchronization::rundown_mutex>::~shared_lock<Rdp::Utils::Synchronization::rundown_mutex>(void)
0x18001a5d5  mov     al, 1
0x18001a5d7  jmp     short loc_18001A5E5
0x18001a5d9  lea     rcx, [rsp+48h+var_18]
0x18001a5de  call    ??1?$shared_lock@Vrundown_mutex@Synchronization@Utils@Rdp@@@std@@QEAA@XZ; std::shared_lock<Rdp::Utils::Synchronization::rundown_mutex>::~shared_lock<Rdp::Utils::Synchronization::rundown_mutex>(void)
0x18001a5e3  xor     al, al
0x18001a5e5  mov     rbx, [rsp+48h+arg_0]
0x18001a5ea  add     rsp, 40h
0x18001a5ee  pop     rdi
0x18001a5ef  retn
```
