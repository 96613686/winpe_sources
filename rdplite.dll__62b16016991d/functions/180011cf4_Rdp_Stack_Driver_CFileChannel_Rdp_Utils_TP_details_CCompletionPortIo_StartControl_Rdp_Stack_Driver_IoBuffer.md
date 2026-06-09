# Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CCompletionPortIo>::StartControl(Rdp::Stack::Driver::IoBuffer *)

- ea: `0x180011cf4`
- end: `0x180011da9`
- name: `?StartControl@?$CFileChannel@VCCompletionPortIo@details@TP@Utils@Rdp@@@Driver@Stack@Rdp@@QEAA_NPEAUIoBuffer@234@@Z`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180011490`

## callees

- `0x18000f2e0`
- `0x18000fbe4`
- `0x180010900`
- `0x180011cf4`
- `0x180012188`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011d51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011d5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011d51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011d5e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CCompletionPortIo>::StartControl(__int64 a1)
{
  int v1; // edx
  __int64 v2; // r10
  _QWORD *v3; // r11
  DWORD LastError; // eax
  int v6; // [rsp+20h] [rbp-38h]
  int v7; // [rsp+28h] [rbp-30h]
  const char *v8; // [rsp+28h] [rbp-30h]
  int v9; // [rsp+30h] [rbp-28h]
  _BYTE v10[24]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  std::shared_lock<Rdp::Utils::Synchronization::rundown_mutex>::shared_lock<Rdp::Utils::Synchronization::rundown_mutex>(
    v10,
    a1 + 16);
  if ( v10[8] && (unsigned __int64)(*v3 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    *(_DWORD *)(v2 + 32) = 2;
    *(_OWORD *)v2 = 0;
    *(_OWORD *)(v2 + 16) = 0;
    if ( !(unsigned int)Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CCompletionPortIo>::InternalDeviceIoControl(
                          *v3,
                          v1,
                          *(_QWORD *)(v2 + 40),
                          *(_DWORD *)(v2 + 60),
                          v6,
                          v7,
                          v9,
                          (LPOVERLAPPED)v2)
      && GetLastError() != 997 )
    {
      LastError = GetLastError();
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x262,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\inc\\FileChannel.h",
        (const char *)LastError,
        (unsigned int)"Failed to issue control request on I/O channel",
        v8);
    }
    std::shared_lock<Rdp::Utils::Synchronization::rundown_mutex>::~shared_lock<Rdp::Utils::Synchronization::rundown_mutex>(v10);
    return 1;
  }
  else
  {
    std::shared_lock<Rdp::Utils::Synchronization::rundown_mutex>::~shared_lock<Rdp::Utils::Synchronization::rundown_mutex>(v10);
    return 0;
  }
}

```

## disassembly

```asm
0x180011cf4  sub     rsp, 58h
0x180011cf8  mov     r10, rdx
0x180011cfb  mov     r11, rcx
0x180011cfe  lea     rdx, [rcx+10h]
0x180011d02  lea     rcx, [rsp+58h+var_18]
0x180011d07  call    ??0?$shared_lock@Vrundown_mutex@Synchronization@Utils@Rdp@@@std@@QEAA@AEAVrundown_mutex@Synchronization@Utils@Rdp@@Utry_to_lock_t@1@@Z; std::shared_lock<Rdp::Utils::Synchronization::rundown_mutex>::shared_lock<Rdp::Utils::Synchronization::rundown_mutex>(Rdp::Utils::Synchronization::rundown_mutex &,std::try_to_lock_t)
0x180011d0c  nop
0x180011d0d  cmp     [rsp+58h+var_10], 0
0x180011d12  jz      loc_180011D98
0x180011d18  mov     rax, [r11]
0x180011d1b  dec     rax
0x180011d1e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180011d22  ja      short loc_180011D98
0x180011d24  mov     dword ptr [r10+20h], 2
0x180011d2c  xorps   xmm0, xmm0
0x180011d2f  movups  xmmword ptr [r10], xmm0
0x180011d33  movups  xmmword ptr [r10+10h], xmm0
0x180011d38  mov     [rsp+58h+var_20], r10; LPOVERLAPPED
0x180011d3d  mov     r9d, [r10+3Ch]; int
0x180011d41  mov     r8, [r10+28h]; int
0x180011d45  mov     rcx, [r11]; int
0x180011d48  call    ?InternalDeviceIoControl@?$CFileChannel@VCCompletionPortIo@details@TP@Utils@Rdp@@@Driver@Stack@Rdp@@CAHPEAXK0K0KPEAKPEAU_OVERLAPPED@@@Z; Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CCompletionPortIo>::InternalDeviceIoControl(void *,ulong,void *,ulong,void *,ulong,ulong *,_OVERLAPPED *)
0x180011d4d  test    eax, eax
0x180011d4f  jnz     short loc_180011D8A
0x180011d51  call    cs:__imp_GetLastError
0x180011d57  cmp     eax, 3E5h
0x180011d5c  jz      short loc_180011D8A
0x180011d5e  call    cs:__imp_GetLastError
0x180011d64  mov     r9d, eax; char *
0x180011d67  mov     rcx, [rsp+58h]; this
0x180011d6c  lea     rax, aFailedToIssueC; "Failed to issue control request on I/O "...
0x180011d73  mov     qword ptr [rsp+58h+var_38], rax; unsigned int
0x180011d78  lea     r8, aOnecoreuapTerm_13; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180011d7f  mov     edx, 262h; void *
0x180011d84  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x180011d8a  lea     rcx, [rsp+58h+var_18]
0x180011d8f  call    ??1?$shared_lock@Vrundown_mutex@Synchronization@Utils@Rdp@@@std@@QEAA@XZ; std::shared_lock<Rdp::Utils::Synchronization::rundown_mutex>::~shared_lock<Rdp::Utils::Synchronization::rundown_mutex>(void)
0x180011d94  mov     al, 1
0x180011d96  jmp     short loc_180011DA4
0x180011d98  lea     rcx, [rsp+58h+var_18]
0x180011d9d  call    ??1?$shared_lock@Vrundown_mutex@Synchronization@Utils@Rdp@@@std@@QEAA@XZ; std::shared_lock<Rdp::Utils::Synchronization::rundown_mutex>::~shared_lock<Rdp::Utils::Synchronization::rundown_mutex>(void)
0x180011da2  xor     al, al
0x180011da4  add     rsp, 58h
0x180011da8  retn
```
