# Rdp::Stack::Driver::CFileChannel_Rdp::Utils::TP::details::CCompletionPortIo_::Open__Rdp::Stack::Graphics::CChannelPipeline::StartFileIoRead_::_10_::_lambda_2___

- ea: `0x18000e794`
- end: `0x18000e91f`
- name: `Rdp::Stack::Driver::CFileChannel_Rdp::Utils::TP::details::CCompletionPortIo_::Open__Rdp::Stack::Graphics::CChannelPipeline::StartFileIoRead_::_10_::_lambda_2___`
- size: `395`
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
- `0x18000e10c`
- `0x18000e23c`
- `0x18000fc90`
- `0x18000fcac`
- `0x18000ffd4`
- `0x1800107bc`
- `0x180012104`
- `0x180012144`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000e7ea`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000e7ea`

## string_xrefs

- `0x18000e821`: `Failed to open channel: %s`

## pseudocode

```c
__int64 __fastcall Rdp::Stack::Driver::CFileChannel_Rdp::Utils::TP::details::CCompletionPortIo_::Open__Rdp::Stack::Graphics::CChannelPipeline::StartFileIoRead_::_10_::_lambda_2___(
        HANDLE *a1,
        const WCHAR *a2,
        __int128 *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
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
  __int64 v19; // [rsp+6Ch] [rbp-25h]
  __int64 v20; // [rsp+74h] [rbp-1Dh]
  int v21; // [rsp+8Ch] [rbp-5h]
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
  v16[0] = Rdp::Utils::TP::details::CCompletionPortIo::CCompletionPortIo__Rdp::Stack::Graphics::CChannelPipeline::StartFileIoRead_::_10_::_lambda_2___(
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
  v19 = 1;
  v18 = *a3;
  v21 = 0;
  v20 = 0;
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
0x18000e794  push    rbp
0x18000e796  push    rbx
0x18000e797  push    rsi
0x18000e798  push    rdi
0x18000e799  push    r14
0x18000e79b  lea     rbp, [rsp-0Fh]
0x18000e7a0  sub     rsp, 0A0h
0x18000e7a7  mov     rax, cs:__security_cookie
0x18000e7ae  xor     rax, rsp
0x18000e7b1  mov     [rbp+2Fh+var_30], rax
0x18000e7b5  mov     rsi, r8
0x18000e7b8  mov     rbx, rdx
0x18000e7bb  mov     r14, rcx
0x18000e7be  mov     rdi, [rbp+2Fh+arg_40]
0x18000e7c2  mov     [rsp+0C0h+hTemplateFile], 0; hTemplateFile
0x18000e7cb  mov     [rsp+0C0h+dwFlagsAndAttributes], 40800080h; dwFlagsAndAttributes
0x18000e7d3  mov     [rsp+0C0h+dwCreationDisposition], 4; dwCreationDisposition
0x18000e7db  xor     r9d, r9d; lpSecurityAttributes
0x18000e7de  mov     edx, 10000000h; dwDesiredAccess
0x18000e7e3  lea     r8d, [r9+3]; dwShareMode
0x18000e7e7  mov     rcx, rbx; lpFileName
0x18000e7ea  call    cs:__imp_CreateFileW
0x18000e7f0  mov     [rbp+2Fh+var_80], rax
0x18000e7f4  lea     rdx, [rbp+2Fh+var_80]
0x18000e7f8  mov     rcx, r14
0x18000e7fb  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x18000e800  lea     rcx, [rbp+2Fh+var_80]
0x18000e804  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000e809  mov     rax, [r14]
0x18000e80c  inc     rax
0x18000e80f  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000e815  setz    al
0x18000e818  mov     rcx, [rbp+37h]; this
0x18000e81c  mov     qword ptr [rsp+0C0h+dwFlagsAndAttributes], rbx; char *
0x18000e821  lea     rdx, Event; "Failed to open channel: %s"
0x18000e828  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rdx; bool
0x18000e82d  movzx   r9d, al; char *
0x18000e831  lea     r8, aOnecoreuapTerm_13; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18000e838  mov     edx, 125h; void *
0x18000e83d  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x18000e842  mov     rbx, [r14]
0x18000e845  mov     ecx, 60h ; '`'; Size
0x18000e84a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e84f  mov     [rbp+2Fh+var_80], rax
0x18000e853  mov     r8, rdi
0x18000e856  mov     rdx, rbx
0x18000e859  mov     rcx, rax
0x18000e85c  call    Rdp__Utils__TP__details__CCompletionPortIo__CCompletionPortIo__Rdp__Stack__Graphics__CChannelPipeline__StartFileIoRead____10____lambda_2___
0x18000e861  nop
0x18000e862  mov     [rbp+2Fh+var_80], rax
0x18000e866  lea     rcx, [r14+8]
0x18000e86a  lea     rdx, [rbp+2Fh+var_80]
0x18000e86e  call    ??$?4U?$default_delete@VCCompletionPortIo@details@TP@Utils@Rdp@@@std@@$0A@@?$unique_ptr@VCCompletionPortIo@details@TP@Utils@Rdp@@U?$default_delete@VCCompletionPortIo@details@TP@Utils@Rdp@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Rdp::Utils::TP::details::CCompletionPortIo>::operator=<std::default_delete<Rdp::Utils::TP::details::CCompletionPortIo>,0>(std::unique_ptr<Rdp::Utils::TP::details::CCompletionPortIo> &&)
0x18000e873  lea     rcx, [rbp+2Fh+var_80]
0x18000e877  call    ??1?$unique_ptr@VCCompletionPortIo@details@TP@Utils@Rdp@@U?$default_delete@VCCompletionPortIo@details@TP@Utils@Rdp@@@std@@@std@@QEAA@XZ; std::unique_ptr<Rdp::Utils::TP::details::CCompletionPortIo>::~unique_ptr<Rdp::Utils::TP::details::CCompletionPortIo>(void)
0x18000e87c  mov     ebx, 40h ; '@'
0x18000e881  mov     r8d, ebx; Size
0x18000e884  xor     edx, edx; Val
0x18000e886  lea     rcx, [rbp+2Fh+var_70]; void *
0x18000e88a  call    memset_0
0x18000e88f  mov     [rbp+2Fh+var_70], ebx
0x18000e892  mov     [rbp+2Fh+var_68], 8
0x18000e899  mov     [rbp+2Fh+var_54], 1
0x18000e8a1  movups  xmm0, xmmword ptr [rsi]
0x18000e8a4  movdqu  [rbp+2Fh+var_64], xmm0
0x18000e8a9  mov     [rbp+2Fh+var_34], 0
0x18000e8b0  mov     [rbp+2Fh+var_4C], 0
0x18000e8b8  mov     [rsp+0C0h+hTemplateFile], 0; __int64
0x18000e8c1  mov     [rsp+0C0h+dwFlagsAndAttributes], 0; char *
0x18000e8c9  mov     qword ptr [rsp+0C0h+dwCreationDisposition], 0; PVOID
0x18000e8d2  mov     r9d, ebx
0x18000e8d5  lea     r8, [rbp+2Fh+var_70]
0x18000e8d9  mov     rcx, [r14]; FileHandle
0x18000e8dc  call    ?InternalDeviceIoControl@?$CFileChannel@VCCompletionPortIo@details@TP@Utils@Rdp@@@Driver@Stack@Rdp@@CAHPEAXK0K0KPEAK@Z; Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CCompletionPortIo>::InternalDeviceIoControl(void *,ulong,void *,ulong,void *,ulong,ulong *)
0x18000e8e1  mov     rcx, [rbp+37h]; this
0x18000e8e5  lea     rdx, aFailedToStartC; "Failed to start channel"
0x18000e8ec  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rdx; int
0x18000e8f1  mov     r9d, eax; char *
0x18000e8f4  lea     r8, aOnecoreuapTerm_13; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18000e8fb  mov     edx, 142h; void *
0x18000e900  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x18000e905  mov     rcx, [rbp+2Fh+var_30]
0x18000e909  xor     rcx, rsp; StackCookie
0x18000e90c  call    __security_check_cookie
0x18000e911  add     rsp, 0A0h
0x18000e918  pop     r14
0x18000e91a  pop     rdi
0x18000e91b  pop     rsi
0x18000e91c  pop     rbx
0x18000e91d  pop     rbp
0x18000e91e  retn
```
