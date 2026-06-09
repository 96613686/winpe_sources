# Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CCompletionPortIo>::StartRead(Rdp::Stack::Driver::IoBuffer *)

- ea: `0x180011ee4`
- end: `0x180011f99`
- name: `?StartRead@?$CFileChannel@VCCompletionPortIo@details@TP@Utils@Rdp@@@Driver@Stack@Rdp@@QEAA_NPEAUIoBuffer@234@@Z`
- size: `181`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180011048`
- `0x180011b5c`

## callees

- `0x18000f2e0`
- `0x18000fbe4`
- `0x18001094c`
- `0x180011ee4`
- `0x180012188`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011f41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011f4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011f41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011f4e`

## string_xrefs

- `0x180011f5c`: `Failed to read from I/O channel`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CCompletionPortIo>::StartRead(__int64 a1)
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
    *(_DWORD *)(v1 + 32) = 0;
    *(_OWORD *)v1 = 0;
    *(_OWORD *)(v1 + 16) = 0;
    if ( !Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CCompletionPortIo>::InternalReadFile(
            *v2,
            *(void **)(v1 + 40),
            *(_DWORD *)(v1 + 60),
            v1,
            (LPOVERLAPPED)v1)
      && GetLastError() != 997 )
    {
      LastError = GetLastError();
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x1F4,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\inc\\FileChannel.h",
        (const char *)LastError,
        (unsigned int)"Failed to read from I/O channel",
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
0x180011ee4  sub     rsp, 48h
0x180011ee8  mov     r9, rdx
0x180011eeb  mov     r10, rcx
0x180011eee  lea     rdx, [rcx+10h]
0x180011ef2  lea     rcx, [rsp+48h+var_18]
0x180011ef7  call    ??0?$shared_lock@Vrundown_mutex@Synchronization@Utils@Rdp@@@std@@QEAA@AEAVrundown_mutex@Synchronization@Utils@Rdp@@Utry_to_lock_t@1@@Z; std::shared_lock<Rdp::Utils::Synchronization::rundown_mutex>::shared_lock<Rdp::Utils::Synchronization::rundown_mutex>(Rdp::Utils::Synchronization::rundown_mutex &,std::try_to_lock_t)
0x180011efc  nop
0x180011efd  cmp     [rsp+48h+var_10], 0
0x180011f02  jz      loc_180011F88
0x180011f08  mov     rax, [r10]
0x180011f0b  dec     rax
0x180011f0e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180011f12  ja      short loc_180011F88
0x180011f14  mov     dword ptr [r9+20h], 0
0x180011f1c  xorps   xmm0, xmm0
0x180011f1f  movups  xmmword ptr [r9], xmm0
0x180011f23  movups  xmmword ptr [r9+10h], xmm0
0x180011f28  mov     [rsp+48h+var_28], r9; LPOVERLAPPED
0x180011f2d  mov     r8d, [r9+3Ch]; int
0x180011f31  mov     rdx, [r9+28h]; int
0x180011f35  mov     rcx, [r10]; int
0x180011f38  call    ?InternalReadFile@?$CFileChannel@VCCompletionPortIo@details@TP@Utils@Rdp@@@Driver@Stack@Rdp@@CAHPEAX0KPEAKPEAU_OVERLAPPED@@@Z; Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CCompletionPortIo>::InternalReadFile(void *,void *,ulong,ulong *,_OVERLAPPED *)
0x180011f3d  test    eax, eax
0x180011f3f  jnz     short loc_180011F7A
0x180011f41  call    cs:__imp_GetLastError
0x180011f47  cmp     eax, 3E5h
0x180011f4c  jz      short loc_180011F7A
0x180011f4e  call    cs:__imp_GetLastError
0x180011f54  mov     r9d, eax; char *
0x180011f57  mov     rcx, [rsp+48h]; this
0x180011f5c  lea     rax, aFailedToReadFr_1; "Failed to read from I/O channel"
0x180011f63  mov     [rsp+48h+var_28], rax; unsigned int
0x180011f68  lea     r8, aOnecoreuapTerm_13; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180011f6f  mov     edx, 1F4h; void *
0x180011f74  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x180011f7a  lea     rcx, [rsp+48h+var_18]
0x180011f7f  call    ??1?$shared_lock@Vrundown_mutex@Synchronization@Utils@Rdp@@@std@@QEAA@XZ; std::shared_lock<Rdp::Utils::Synchronization::rundown_mutex>::~shared_lock<Rdp::Utils::Synchronization::rundown_mutex>(void)
0x180011f84  mov     al, 1
0x180011f86  jmp     short loc_180011F94
0x180011f88  lea     rcx, [rsp+48h+var_18]
0x180011f8d  call    ??1?$shared_lock@Vrundown_mutex@Synchronization@Utils@Rdp@@@std@@QEAA@XZ; std::shared_lock<Rdp::Utils::Synchronization::rundown_mutex>::~shared_lock<Rdp::Utils::Synchronization::rundown_mutex>(void)
0x180011f92  xor     al, al
0x180011f94  add     rsp, 48h
0x180011f98  retn
```
