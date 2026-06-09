# Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CThreadPoolIo<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&Rdp::Utils::TP::details::DestroyThreadpoolIo(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>>>>::StartRead(Rdp::Stack::Driver::IoBuffer *)

- ea: `0x18001c2a8`
- end: `0x18001c384`
- name: `?StartRead@?$CFileChannel@V?$CThreadPoolIo@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_IO@@P6AXPEAU1@@Z$1?DestroyThreadpoolIo@details@TP@Utils@Rdp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@TP@Utils@Rdp@@@Driver@Stack@Rdp@@QEAA_NPEAUIoBuffer@234@@Z`
- size: `220`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001b698`
- `0x18001c230`

## callees

- `0x18000f2e0`
- `0x18000fbe4`
- `0x18001094c`
- `0x180012188`
- `0x18001c2a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c319`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c333`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c319`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c333`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18001c32d`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18001c32d`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18001c2e9`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18001c2e9`

## string_xrefs

- `0x18001c341`: `Failed to read from I/O channel`

## pseudocode

```c
char __fastcall Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CThreadPoolIo<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&void Rdp::Utils::TP::details::DestroyThreadpoolIo(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>>>>::StartRead(
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
    *(_DWORD *)(a2 + 32) = 0;
    *(_OWORD *)a2 = 0;
    *(_OWORD *)(a2 + 16) = 0;
    if ( !(unsigned int)Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CCompletionPortIo>::InternalReadFile(
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
        (void *)0x1F4,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\inc\\FileChannel.h",
        (const char *)LastError,
        (unsigned int)"Failed to read from I/O channel",
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
0x18001c2a8  mov     [rsp+arg_0], rbx
0x18001c2ad  push    rdi
0x18001c2ae  sub     rsp, 40h
0x18001c2b2  mov     rdi, rdx
0x18001c2b5  mov     rbx, rcx
0x18001c2b8  lea     rdx, [rcx+10h]
0x18001c2bc  lea     rcx, [rsp+48h+var_18]
0x18001c2c1  call    ??0?$shared_lock@Vrundown_mutex@Synchronization@Utils@Rdp@@@std@@QEAA@AEAVrundown_mutex@Synchronization@Utils@Rdp@@Utry_to_lock_t@1@@Z; std::shared_lock<Rdp::Utils::Synchronization::rundown_mutex>::shared_lock<Rdp::Utils::Synchronization::rundown_mutex>(Rdp::Utils::Synchronization::rundown_mutex &,std::try_to_lock_t)
0x18001c2c6  nop
0x18001c2c7  cmp     [rsp+48h+var_10], 0
0x18001c2cc  jz      loc_18001C36D
0x18001c2d2  mov     rax, [rbx]
0x18001c2d5  dec     rax
0x18001c2d8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001c2dc  ja      loc_18001C36D
0x18001c2e2  mov     rcx, [rbx+8]
0x18001c2e6  mov     rcx, [rcx]; pio
0x18001c2e9  call    cs:__imp_StartThreadpoolIo
0x18001c2ef  mov     dword ptr [rdi+20h], 0
0x18001c2f6  xorps   xmm0, xmm0
0x18001c2f9  movups  xmmword ptr [rdi], xmm0
0x18001c2fc  movups  xmmword ptr [rdi+10h], xmm0
0x18001c300  mov     [rsp+48h+var_28], rdi; LPOVERLAPPED
0x18001c305  mov     r8d, [rdi+3Ch]; int
0x18001c309  mov     rdx, [rdi+28h]; int
0x18001c30d  mov     rcx, [rbx]; int
0x18001c310  call    ?InternalReadFile@?$CFileChannel@VCCompletionPortIo@details@TP@Utils@Rdp@@@Driver@Stack@Rdp@@CAHPEAX0KPEAKPEAU_OVERLAPPED@@@Z; Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CCompletionPortIo>::InternalReadFile(void *,void *,ulong,ulong *,_OVERLAPPED *)
0x18001c315  test    eax, eax
0x18001c317  jnz     short loc_18001C35F
0x18001c319  call    cs:__imp_GetLastError
0x18001c31f  cmp     eax, 3E5h
0x18001c324  jz      short loc_18001C35F
0x18001c326  mov     rcx, [rbx+8]
0x18001c32a  mov     rcx, [rcx]; pio
0x18001c32d  call    cs:__imp_CancelThreadpoolIo
0x18001c333  call    cs:__imp_GetLastError
0x18001c339  mov     r9d, eax; char *
0x18001c33c  mov     rcx, [rsp+48h]; this
0x18001c341  lea     rax, aFailedToReadFr_1; "Failed to read from I/O channel"
0x18001c348  mov     [rsp+48h+var_28], rax; unsigned int
0x18001c34d  lea     r8, aOnecoreuapTerm_13; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18001c354  mov     edx, 1F4h; void *
0x18001c359  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18001c35f  lea     rcx, [rsp+48h+var_18]
0x18001c364  call    ??1?$shared_lock@Vrundown_mutex@Synchronization@Utils@Rdp@@@std@@QEAA@XZ; std::shared_lock<Rdp::Utils::Synchronization::rundown_mutex>::~shared_lock<Rdp::Utils::Synchronization::rundown_mutex>(void)
0x18001c369  mov     al, 1
0x18001c36b  jmp     short loc_18001C379
0x18001c36d  lea     rcx, [rsp+48h+var_18]
0x18001c372  call    ??1?$shared_lock@Vrundown_mutex@Synchronization@Utils@Rdp@@@std@@QEAA@XZ; std::shared_lock<Rdp::Utils::Synchronization::rundown_mutex>::~shared_lock<Rdp::Utils::Synchronization::rundown_mutex>(void)
0x18001c377  xor     al, al
0x18001c379  mov     rbx, [rsp+48h+arg_0]
0x18001c37e  add     rsp, 40h
0x18001c382  pop     rdi
0x18001c383  retn
```
