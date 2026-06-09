# Rdp::Stack::Driver::CFileChannel_Rdp::Utils::TP::details::CCompletionPortIo_::Open__Rdp::Stack::Graphics::CChannelPipeline::StartFileIoRead_::_8_::_lambda_1___

- ea: `0x18000e5fc`
- end: `0x18000e78c`
- name: `Rdp::Stack::Driver::CFileChannel_Rdp::Utils::TP::details::CCompletionPortIo_::Open__Rdp::Stack::Graphics::CChannelPipeline::StartFileIoRead_::_8_::_lambda_1___`
- size: `400`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180011db0`

## callees

- `0x1800036f0`
- `0x180003714`
- `0x180004154`
- `0x18000dfdc`
- `0x18000e23c`
- `0x18000fc90`
- `0x18000fcac`
- `0x18000ffd4`
- `0x1800107bc`
- `0x180012104`
- `0x180012144`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000e652`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000e652`

## string_xrefs

- `0x18000e689`: `Failed to open channel: %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Rdp::Stack::Driver::CFileChannel_Rdp::Utils::TP::details::CCompletionPortIo_::Open__Rdp::Stack::Graphics::CChannelPipeline::StartFileIoRead_::_8_::_lambda_1___(
        HANDLE *a1,
        const WCHAR *a2,
        __int128 *a3,
        __int64 a4,
        __int64 a5,
        int a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  HANDLE v12; // rbx
  unsigned int v13; // eax
  const char *dwFlagsAndAttributes; // [rsp+28h] [rbp-69h]
  __int64 v16[2]; // [rsp+40h] [rbp-51h] BYREF
  _DWORD v17[3]; // [rsp+50h] [rbp-41h] BYREF
  __int128 v18; // [rsp+5Ch] [rbp-35h]
  int v19; // [rsp+6Ch] [rbp-25h]
  int v20; // [rsp+70h] [rbp-21h]
  __int64 v21; // [rsp+74h] [rbp-1Dh]
  int v22; // [rsp+8Ch] [rbp-5h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+37h]

  v16[0] = (__int64)CreateFileW(a2, 0x10000000u, 3u, 0, 4u, 0x40800080u, 0);
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
    a1,
    v16);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v16);
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0x125,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\inc\\FileChannel.h",
    (const char *)((((unsigned __int64)*a1 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0),
    (bool)"Failed to open channel: %s",
    (const char *)a2);
  v12 = *a1;
  v16[0] = (__int64)operator new(0x60u);
  v16[0] = Rdp::Utils::TP::details::CCompletionPortIo::CCompletionPortIo__Rdp::Stack::Graphics::CChannelPipeline::StartFileIoRead_::_8_::_lambda_1___(
             v16[0],
             v12,
             a9);
  std::unique_ptr<Rdp::Utils::TP::details::CCompletionPortIo>::operator=<std::default_delete<Rdp::Utils::TP::details::CCompletionPortIo>,0>(
    a1 + 1,
    v16);
  std::unique_ptr<Rdp::Utils::TP::details::CCompletionPortIo>::~unique_ptr<Rdp::Utils::TP::details::CCompletionPortIo>(v16);
  memset_0(v17, 0, 0x40u);
  v17[0] = 64;
  v17[2] = 8;
  v19 = 2;
  v18 = *a3;
  v22 = 1;
  v20 = a6;
  v21 = 0;
  v13 = Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CCompletionPortIo>::InternalDeviceIoControl(
          *a1,
          0,
          0,
          0);
  return wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
           retaddr,
           (void *)0x142,
           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\inc\\FileChannel.h",
           (const char *)v13,
           (int)"Failed to start channel",
           dwFlagsAndAttributes);
}

```

## disassembly

```asm
0x18000e5fc  push    rbp
0x18000e5fe  push    rbx
0x18000e5ff  push    rsi
0x18000e600  push    rdi
0x18000e601  push    r14
0x18000e603  lea     rbp, [rsp-0Fh]
0x18000e608  sub     rsp, 0A0h
0x18000e60f  mov     rax, cs:__security_cookie
0x18000e616  xor     rax, rsp
0x18000e619  mov     [rbp+2Fh+var_30], rax
0x18000e61d  mov     rsi, r8
0x18000e620  mov     rbx, rdx
0x18000e623  mov     r14, rcx
0x18000e626  mov     rdi, [rbp+2Fh+arg_40]
0x18000e62a  mov     [rsp+0C0h+hTemplateFile], 0; hTemplateFile
0x18000e633  mov     [rsp+0C0h+dwFlagsAndAttributes], 40800080h; dwFlagsAndAttributes
0x18000e63b  mov     [rsp+0C0h+dwCreationDisposition], 4; dwCreationDisposition
0x18000e643  xor     r9d, r9d; lpSecurityAttributes
0x18000e646  mov     edx, 10000000h; dwDesiredAccess
0x18000e64b  lea     r8d, [r9+3]; dwShareMode
0x18000e64f  mov     rcx, rbx; lpFileName
0x18000e652  call    cs:__imp_CreateFileW
0x18000e658  mov     [rbp+2Fh+var_80], rax
0x18000e65c  lea     rdx, [rbp+2Fh+var_80]
0x18000e660  mov     rcx, r14
0x18000e663  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x18000e668  lea     rcx, [rbp+2Fh+var_80]
0x18000e66c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000e671  mov     rax, [r14]
0x18000e674  inc     rax
0x18000e677  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000e67d  setz    al
0x18000e680  mov     rcx, [rbp+37h]; this
0x18000e684  mov     qword ptr [rsp+0C0h+dwFlagsAndAttributes], rbx; char *
0x18000e689  lea     rdx, Event; "Failed to open channel: %s"
0x18000e690  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rdx; bool
0x18000e695  movzx   r9d, al; char *
0x18000e699  lea     r8, aOnecoreuapTerm_13; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18000e6a0  mov     edx, 125h; void *
0x18000e6a5  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x18000e6aa  mov     rbx, [r14]
0x18000e6ad  mov     ecx, 60h ; '`'; Size
0x18000e6b2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e6b7  mov     [rbp+2Fh+var_80], rax
0x18000e6bb  mov     r8, rdi
0x18000e6be  mov     rdx, rbx
0x18000e6c1  mov     rcx, rax
0x18000e6c4  call    Rdp__Utils__TP__details__CCompletionPortIo__CCompletionPortIo__Rdp__Stack__Graphics__CChannelPipeline__StartFileIoRead____8____lambda_1___
0x18000e6c9  nop
0x18000e6ca  mov     [rbp+2Fh+var_80], rax
0x18000e6ce  lea     rcx, [r14+8]
0x18000e6d2  lea     rdx, [rbp+2Fh+var_80]
0x18000e6d6  call    ??$?4U?$default_delete@VCCompletionPortIo@details@TP@Utils@Rdp@@@std@@$0A@@?$unique_ptr@VCCompletionPortIo@details@TP@Utils@Rdp@@U?$default_delete@VCCompletionPortIo@details@TP@Utils@Rdp@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Rdp::Utils::TP::details::CCompletionPortIo>::operator=<std::default_delete<Rdp::Utils::TP::details::CCompletionPortIo>,0>(std::unique_ptr<Rdp::Utils::TP::details::CCompletionPortIo> &&)
0x18000e6db  lea     rcx, [rbp+2Fh+var_80]
0x18000e6df  call    ??1?$unique_ptr@VCCompletionPortIo@details@TP@Utils@Rdp@@U?$default_delete@VCCompletionPortIo@details@TP@Utils@Rdp@@@std@@@std@@QEAA@XZ; std::unique_ptr<Rdp::Utils::TP::details::CCompletionPortIo>::~unique_ptr<Rdp::Utils::TP::details::CCompletionPortIo>(void)
0x18000e6e4  mov     ebx, 40h ; '@'
0x18000e6e9  mov     r8d, ebx; Size
0x18000e6ec  xor     edx, edx; Val
0x18000e6ee  lea     rcx, [rbp+2Fh+var_70]; void *
0x18000e6f2  call    memset_0
0x18000e6f7  mov     [rbp+2Fh+var_70], ebx
0x18000e6fa  mov     [rbp+2Fh+var_68], 8
0x18000e701  mov     [rbp+2Fh+var_54], 2
0x18000e708  movups  xmm0, xmmword ptr [rsi]
0x18000e70b  movdqu  [rbp+2Fh+var_64], xmm0
0x18000e710  mov     [rbp+2Fh+var_34], 1
0x18000e717  mov     eax, [rbp+2Fh+arg_28]
0x18000e71a  mov     [rbp+2Fh+var_50], eax
0x18000e71d  mov     [rbp+2Fh+var_4C], 0
0x18000e725  mov     [rsp+0C0h+hTemplateFile], 0; __int64
0x18000e72e  mov     [rsp+0C0h+dwFlagsAndAttributes], 0; char *
0x18000e736  mov     qword ptr [rsp+0C0h+dwCreationDisposition], 0; PVOID
0x18000e73f  mov     r9d, ebx
0x18000e742  lea     r8, [rbp+2Fh+var_70]
0x18000e746  mov     rcx, [r14]; FileHandle
0x18000e749  call    ?InternalDeviceIoControl@?$CFileChannel@VCCompletionPortIo@details@TP@Utils@Rdp@@@Driver@Stack@Rdp@@CAHPEAXK0K0KPEAK@Z; Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CCompletionPortIo>::InternalDeviceIoControl(void *,ulong,void *,ulong,void *,ulong,ulong *)
0x18000e74e  mov     rcx, [rbp+37h]; this
0x18000e752  lea     rdx, aFailedToStartC; "Failed to start channel"
0x18000e759  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rdx; int
0x18000e75e  mov     r9d, eax; char *
0x18000e761  lea     r8, aOnecoreuapTerm_13; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18000e768  mov     edx, 142h; void *
0x18000e76d  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x18000e772  mov     rcx, [rbp+2Fh+var_30]
0x18000e776  xor     rcx, rsp; StackCookie
0x18000e779  call    __security_check_cookie
0x18000e77e  add     rsp, 0A0h
0x18000e785  pop     r14
0x18000e787  pop     rdi
0x18000e788  pop     rsi
0x18000e789  pop     rbx
0x18000e78a  pop     rbp
0x18000e78b  retn
```
