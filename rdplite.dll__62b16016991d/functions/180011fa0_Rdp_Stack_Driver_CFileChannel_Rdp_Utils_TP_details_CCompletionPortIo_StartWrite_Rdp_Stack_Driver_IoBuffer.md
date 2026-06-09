# Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CCompletionPortIo>::StartWrite(Rdp::Stack::Driver::IoBuffer *)

- ea: `0x180011fa0`
- end: `0x180012055`
- name: `?StartWrite@?$CFileChannel@VCCompletionPortIo@details@TP@Utils@Rdp@@@Driver@Stack@Rdp@@QEAA_NPEAUIoBuffer@234@@Z`
- size: `181`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180010a30`

## callees

- `0x18000f2e0`
- `0x18000fbe4`
- `0x180010984`
- `0x180011fa0`
- `0x180012188`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011ffd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001200a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011ffd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001200a`

## string_xrefs

- `0x180012018`: `Failed to write from I/O channel`

## pseudocode

```c
char __fastcall Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CCompletionPortIo>::StartWrite(__int64 a1)
{
  __int64 v1; // r9
  void **v2; // r10
  DWORD LastError; // eax
  const char *v5; // [rsp+28h] [rbp-20h]
  _BYTE v6[24]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  std::shared_lock<Rdp::Utils::Synchronization::rundown_mutex>::shared_lock<Rdp::Utils::Synchronization::rundown_mutex>(
    v6,
    a1 + 16);
  if ( v6[8] && (char *)*v2 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    *(_DWORD *)(v1 + 32) = 1;
    *(_OWORD *)v1 = 0;
    *(_OWORD *)(v1 + 16) = 0;
    if ( !Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CThreadPoolIo<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&void Rdp::Utils::TP::details::DestroyThreadpoolIo(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>>>>::InternalWriteFile(
            *v2,
            *(const void **)(v1 + 40),
            *(_DWORD *)(v1 + 60),
            v1,
            (LPOVERLAPPED)v1)
      && GetLastError() != 997 )
    {
      LastError = GetLastError();
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x227,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\inc\\FileChannel.h",
        (const char *)LastError,
        (unsigned int)"Failed to write from I/O channel",
        v5);
    }
    std::shared_lock<Rdp::Utils::Synchronization::rundown_mutex>::~shared_lock<Rdp::Utils::Synchronization::rundown_mutex>(v6);
    return 1;
  }
  else
  {
    std::shared_lock<Rdp::Utils::Synchronization::rundown_mutex>::~shared_lock<Rdp::Utils::Synchronization::rundown_mutex>(v6);
    return 0;
  }
}

```

## disassembly

```asm
0x180011fa0  sub     rsp, 48h
0x180011fa4  mov     r9, rdx
0x180011fa7  mov     r10, rcx
0x180011faa  lea     rdx, [rcx+10h]
0x180011fae  lea     rcx, [rsp+48h+var_18]
0x180011fb3  call    ??0?$shared_lock@Vrundown_mutex@Synchronization@Utils@Rdp@@@std@@QEAA@AEAVrundown_mutex@Synchronization@Utils@Rdp@@Utry_to_lock_t@1@@Z; std::shared_lock<Rdp::Utils::Synchronization::rundown_mutex>::shared_lock<Rdp::Utils::Synchronization::rundown_mutex>(Rdp::Utils::Synchronization::rundown_mutex &,std::try_to_lock_t)
0x180011fb8  nop
0x180011fb9  cmp     [rsp+48h+var_10], 0
0x180011fbe  jz      loc_180012044
0x180011fc4  mov     rax, [r10]
0x180011fc7  dec     rax
0x180011fca  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180011fce  ja      short loc_180012044
0x180011fd0  mov     dword ptr [r9+20h], 1
0x180011fd8  xorps   xmm0, xmm0
0x180011fdb  movups  xmmword ptr [r9], xmm0
0x180011fdf  movups  xmmword ptr [r9+10h], xmm0
0x180011fe4  mov     [rsp+48h+var_28], r9; LPOVERLAPPED
0x180011fe9  mov     r8d, [r9+3Ch]; int
0x180011fed  mov     rdx, [r9+28h]; int
0x180011ff1  mov     rcx, [r10]; int
0x180011ff4  call    ?InternalWriteFile@?$CFileChannel@V?$CThreadPoolIo@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_IO@@P6AXPEAU1@@Z$1?DestroyThreadpoolIo@details@TP@Utils@Rdp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@TP@Utils@Rdp@@@Driver@Stack@Rdp@@CAHPEAX0KPEAKPEAU_OVERLAPPED@@@Z; Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CThreadPoolIo<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&Rdp::Utils::TP::details::DestroyThreadpoolIo(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>>>>::InternalWriteFile(void *,void *,ulong,ulong *,_OVERLAPPED *)
0x180011ff9  test    eax, eax
0x180011ffb  jnz     short loc_180012036
0x180011ffd  call    cs:__imp_GetLastError
0x180012003  cmp     eax, 3E5h
0x180012008  jz      short loc_180012036
0x18001200a  call    cs:__imp_GetLastError
0x180012010  mov     r9d, eax; char *
0x180012013  mov     rcx, [rsp+48h]; this
0x180012018  lea     rax, aFailedToWriteF; "Failed to write from I/O channel"
0x18001201f  mov     [rsp+48h+var_28], rax; unsigned int
0x180012024  lea     r8, aOnecoreuapTerm_13; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18001202b  mov     edx, 227h; void *
0x180012030  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x180012036  lea     rcx, [rsp+48h+var_18]
0x18001203b  call    ??1?$shared_lock@Vrundown_mutex@Synchronization@Utils@Rdp@@@std@@QEAA@XZ; std::shared_lock<Rdp::Utils::Synchronization::rundown_mutex>::~shared_lock<Rdp::Utils::Synchronization::rundown_mutex>(void)
0x180012040  mov     al, 1
0x180012042  jmp     short loc_180012050
0x180012044  lea     rcx, [rsp+48h+var_18]
0x180012049  call    ??1?$shared_lock@Vrundown_mutex@Synchronization@Utils@Rdp@@@std@@QEAA@XZ; std::shared_lock<Rdp::Utils::Synchronization::rundown_mutex>::~shared_lock<Rdp::Utils::Synchronization::rundown_mutex>(void)
0x18001204e  xor     al, al
0x180012050  add     rsp, 48h
0x180012054  retn
```
