# Rdp::Stack::Driver::CFileChannel_Rdp::Utils::TP::details::CCompletionPortIo_::Open__Rdp::Stack::Graphics::CChannelPipeline::StartFileIoWrite_::_2_::_lambda_1___

- ea: `0x18000e45c`
- end: `0x18000e5f3`
- name: `Rdp::Stack::Driver::CFileChannel_Rdp::Utils::TP::details::CCompletionPortIo_::Open__Rdp::Stack::Graphics::CChannelPipeline::StartFileIoWrite_::_2_::_lambda_1___`
- size: `407`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180011c64`

## callees

- `0x1800036f0`
- `0x180003714`
- `0x18000deac`
- `0x18000e23c`
- `0x18000fc90`
- `0x18000fcac`
- `0x18000ffd4`
- `0x1800107bc`
- `0x180012104`
- `0x180012144`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000e4b0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000e4b0`

## string_xrefs

- `0x18000e4e7`: `Failed to open channel: %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Rdp::Stack::Driver::CFileChannel_Rdp::Utils::TP::details::CCompletionPortIo_::Open__Rdp::Stack::Graphics::CChannelPipeline::StartFileIoWrite_::_2_::_lambda_1___(
        HANDLE *a1,
        const WCHAR *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  HANDLE v11; // rbx
  unsigned int v12; // eax
  const char *dwFlagsAndAttributes; // [rsp+28h] [rbp-59h]
  __int64 v15[3]; // [rsp+40h] [rbp-41h] BYREF
  int v16; // [rsp+58h] [rbp-29h]
  GUID v17; // [rsp+5Ch] [rbp-25h]
  __int64 v18; // [rsp+6Ch] [rbp-15h]
  __int64 v19; // [rsp+74h] [rbp-Dh]
  __int64 v20; // [rsp+7Ch] [rbp-5h]
  __int64 v21; // [rsp+84h] [rbp+3h]
  int v22; // [rsp+8Ch] [rbp+Bh]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+37h]

  v15[0] = (__int64)CreateFileW(a2, 0x10000000u, 3u, 0, 4u, 0x40800080u, 0);
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
    a1,
    v15);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v15);
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0x125,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\inc\\FileChannel.h",
    (const char *)((((unsigned __int64)*a1 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0),
    (bool)"Failed to open channel: %s",
    (const char *)a2);
  v11 = *a1;
  v15[0] = (__int64)operator new(0x60u);
  v15[0] = Rdp::Utils::TP::details::CCompletionPortIo::CCompletionPortIo__Rdp::Stack::Graphics::CChannelPipeline::StartFileIoWrite_::_2_::_lambda_1___(
             v15[0],
             v11,
             a9);
  std::unique_ptr<Rdp::Utils::TP::details::CCompletionPortIo>::operator=<std::default_delete<Rdp::Utils::TP::details::CCompletionPortIo>,0>(
    a1 + 1,
    v15);
  std::unique_ptr<Rdp::Utils::TP::details::CCompletionPortIo>::~unique_ptr<Rdp::Utils::TP::details::CCompletionPortIo>(v15);
  v15[2] = 64;
  v20 = 0;
  v21 = 0;
  v16 = 8;
  v18 = 1;
  v17 = GUID_AvencFileIoChannelGraphics;
  v22 = 2;
  v19 = 0;
  v12 = Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CCompletionPortIo>::InternalDeviceIoControl(
          *a1,
          0,
          0,
          0);
  return wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
           retaddr,
           (void *)0x142,
           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\inc\\FileChannel.h",
           (const char *)v12,
           (int)"Failed to start channel",
           dwFlagsAndAttributes);
}

```

## disassembly

```asm
0x18000e45c  mov     [rsp-8+arg_10], rbx
0x18000e461  push    rbp
0x18000e462  push    rsi
0x18000e463  push    rdi
0x18000e464  lea     rbp, [rsp-1Fh]
0x18000e469  sub     rsp, 0A0h
0x18000e470  mov     rax, cs:__security_cookie
0x18000e477  xor     rax, rsp
0x18000e47a  mov     [rbp+2Fh+var_20], rax
0x18000e47e  mov     rbx, rdx
0x18000e481  mov     rsi, rcx
0x18000e484  mov     rdi, [rbp+2Fh+arg_40]
0x18000e488  mov     [rsp+0B0h+hTemplateFile], 0; hTemplateFile
0x18000e491  mov     [rsp+0B0h+dwFlagsAndAttributes], 40800080h; dwFlagsAndAttributes
0x18000e499  mov     [rsp+0B0h+dwCreationDisposition], 4; dwCreationDisposition
0x18000e4a1  xor     r9d, r9d; lpSecurityAttributes
0x18000e4a4  mov     edx, 10000000h; dwDesiredAccess
0x18000e4a9  lea     r8d, [r9+3]; dwShareMode
0x18000e4ad  mov     rcx, rbx; lpFileName
0x18000e4b0  call    cs:__imp_CreateFileW
0x18000e4b6  mov     [rbp+2Fh+var_70], rax
0x18000e4ba  lea     rdx, [rbp+2Fh+var_70]
0x18000e4be  mov     rcx, rsi
0x18000e4c1  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x18000e4c6  lea     rcx, [rbp+2Fh+var_70]
0x18000e4ca  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000e4cf  mov     rax, [rsi]
0x18000e4d2  inc     rax
0x18000e4d5  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000e4db  setz    al
0x18000e4de  mov     rcx, [rbp+37h]; this
0x18000e4e2  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], rbx; char *
0x18000e4e7  lea     rdx, Event; "Failed to open channel: %s"
0x18000e4ee  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rdx; bool
0x18000e4f3  movzx   r9d, al; char *
0x18000e4f7  lea     r8, aOnecoreuapTerm_13; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18000e4fe  mov     edx, 125h; void *
0x18000e503  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x18000e508  mov     rbx, [rsi]
0x18000e50b  mov     ecx, 60h ; '`'; Size
0x18000e510  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e515  mov     [rbp+2Fh+var_70], rax
0x18000e519  mov     r8, rdi
0x18000e51c  mov     rdx, rbx
0x18000e51f  mov     rcx, rax
0x18000e522  call    Rdp__Utils__TP__details__CCompletionPortIo__CCompletionPortIo__Rdp__Stack__Graphics__CChannelPipeline__StartFileIoWrite____2____lambda_1___
0x18000e527  nop
0x18000e528  mov     [rbp+2Fh+var_70], rax
0x18000e52c  lea     rcx, [rsi+8]
0x18000e530  lea     rdx, [rbp+2Fh+var_70]
0x18000e534  call    ??$?4U?$default_delete@VCCompletionPortIo@details@TP@Utils@Rdp@@@std@@$0A@@?$unique_ptr@VCCompletionPortIo@details@TP@Utils@Rdp@@U?$default_delete@VCCompletionPortIo@details@TP@Utils@Rdp@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Rdp::Utils::TP::details::CCompletionPortIo>::operator=<std::default_delete<Rdp::Utils::TP::details::CCompletionPortIo>,0>(std::unique_ptr<Rdp::Utils::TP::details::CCompletionPortIo> &&)
0x18000e539  lea     rcx, [rbp+2Fh+var_70]
0x18000e53d  call    ??1?$unique_ptr@VCCompletionPortIo@details@TP@Utils@Rdp@@U?$default_delete@VCCompletionPortIo@details@TP@Utils@Rdp@@@std@@@std@@QEAA@XZ; std::unique_ptr<Rdp::Utils::TP::details::CCompletionPortIo>::~unique_ptr<Rdp::Utils::TP::details::CCompletionPortIo>(void)
0x18000e542  mov     [rbp+2Fh+var_60], 40h ; '@'
0x18000e54a  mov     [rbp+2Fh+var_34], 0
0x18000e552  mov     [rbp+2Fh+var_2C], 0
0x18000e55a  mov     r9d, 40h ; '@'
0x18000e560  mov     [rbp+2Fh+var_58], 8
0x18000e567  mov     [rbp+2Fh+var_44], 1
0x18000e56f  movups  xmm0, xmmword ptr cs:GUID_AvencFileIoChannelGraphics.Data1
0x18000e576  movdqu  [rbp+2Fh+var_54], xmm0
0x18000e57b  mov     [rbp+2Fh+var_24], 2
0x18000e582  mov     [rbp+2Fh+var_3C], 0
0x18000e58a  mov     [rsp+0B0h+hTemplateFile], 0; __int64
0x18000e593  mov     [rsp+0B0h+dwFlagsAndAttributes], 0; char *
0x18000e59b  mov     qword ptr [rsp+0B0h+dwCreationDisposition], 0; PVOID
0x18000e5a4  lea     r8, [rbp+2Fh+var_60]
0x18000e5a8  mov     rcx, [rsi]; FileHandle
0x18000e5ab  call    ?InternalDeviceIoControl@?$CFileChannel@VCCompletionPortIo@details@TP@Utils@Rdp@@@Driver@Stack@Rdp@@CAHPEAXK0K0KPEAK@Z; Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CCompletionPortIo>::InternalDeviceIoControl(void *,ulong,void *,ulong,void *,ulong,ulong *)
0x18000e5b0  mov     rcx, [rbp+37h]; this
0x18000e5b4  lea     rdx, aFailedToStartC; "Failed to start channel"
0x18000e5bb  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rdx; int
0x18000e5c0  mov     r9d, eax; char *
0x18000e5c3  lea     r8, aOnecoreuapTerm_13; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18000e5ca  mov     edx, 142h; void *
0x18000e5cf  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x18000e5d4  mov     rcx, [rbp+2Fh+var_20]
0x18000e5d8  xor     rcx, rsp; StackCookie
0x18000e5db  call    __security_check_cookie
0x18000e5e0  mov     rbx, [rsp+0B0h+arg_10]
0x18000e5e8  add     rsp, 0A0h
0x18000e5ef  pop     rdi
0x18000e5f0  pop     rsi
0x18000e5f1  pop     rbp
0x18000e5f2  retn
```
