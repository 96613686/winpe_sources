# Rdp::Utils::TP::details::CCompletionPortIo::CCompletionPortIo__Rdp::Stack::Graphics::CChannelPipeline::StartFileIoRead_::_10_::_lambda_2___

- ea: `0x18000e10c`
- end: `0x18000e233`
- name: `Rdp::Utils::TP::details::CCompletionPortIo::CCompletionPortIo__Rdp::Stack::Graphics::CChannelPipeline::StartFileIoRead_::_10_::_lambda_2___`
- size: `295`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e794`

## callees

- `0x18000e3b8`
- `0x18000ed34`
- `0x18000ed74`
- `0x18000f008`
- `0x18000ff8c`
- `0x18001000c`
- `0x1800129cc`

## import_xrefs

- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x18000e155`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x18000e19a`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x18000e155`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x18000e19a`

## string_xrefs

- `0x18000e16b`: `Failed to create completion port`
- `0x18000e17a`: `onecoreuap\termsrv\rdp_bin\win\common\inc\ThreadPoolIo.h`
- `0x18000e1b4`: `onecoreuap\termsrv\rdp_bin\win\common\inc\ThreadPoolIo.h`
- `0x18000e1a5`: `Failed to associate completion port with file handle`

## pseudocode

```c
__int64 __fastcall Rdp::Utils::TP::details::CCompletionPortIo::CCompletionPortIo__Rdp::Stack::Graphics::CChannelPipeline::StartFileIoRead_::_10_::_lambda_2___(
        __int64 a1,
        void *a2,
        __int64 a3)
{
  HANDLE IoCompletionPort; // rax
  HANDLE v7; // rax
  void (__fastcall *v9)(Rdp::Utils::TP::details::CCompletionPortIo *__hidden); // [rsp+30h] [rbp-38h] BYREF
  _BYTE v10[24]; // [rsp+38h] [rbp-30h] BYREF
  void *retaddr; // [rsp+68h] [rbp+0h]
  __int64 v12; // [rsp+88h] [rbp+20h] BYREF

  *(_QWORD *)a1 = 0;
  *(_OWORD *)(a1 + 8) = 0;
  *(_BYTE *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  IoCompletionPort = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, 1u);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    a1,
    IoCompletionPort);
  wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,0>(
    retaddr,
    218,
    "onecoreuap\\termsrv\\rdp_bin\\win\\common\\inc\\ThreadPoolIo.h",
    a1,
    "Failed to create completion port");
  v7 = CreateIoCompletionPort(a2, *(HANDLE *)a1, 0, 1u);
  wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<long (*)(Rdp::Avenc::AVENC_VERSION_INFO const *,Rdp::Avenc::AVENC_VERSION_INFO *,Rdp::Avenc::AVENC_VERSION_INFO *),0>(
    retaddr,
    229,
    "onecoreuap\\termsrv\\rdp_bin\\win\\common\\inc\\ThreadPoolIo.h",
    v7,
    "Failed to associate completion port with file handle");
  std::function_void___cdecl_void___unsigned_long_unsigned___int64__::operator___Rdp::Stack::Graphics::CChannelPipeline::StartFileIoRead_::_10_::_lambda_2__0_(
    a1 + 32,
    a3);
  *(_BYTE *)(a1 + 24) = 0;
  v12 = a1;
  v9 = Rdp::Utils::TP::details::CCompletionPortIo::CompletionPortWorker;
  std::thread::_Start<void (Rdp::Utils::TP::details::CCompletionPortIo::*)(void),Rdp::Utils::TP::details::CCompletionPortIo *>(
    v10,
    &v9,
    &v12);
  std::thread::operator=(a1 + 8, v10);
  std::thread::~thread((std::thread *)v10);
  return a1;
}

```

## disassembly

```asm
0x18000e10c  mov     [rsp+arg_8], rbx
0x18000e111  mov     [rsp+arg_10], rbp
0x18000e116  mov     [rsp+arg_0], rcx
0x18000e11b  push    rsi
0x18000e11c  push    rdi
0x18000e11d  push    r14
0x18000e11f  sub     rsp, 50h
0x18000e123  mov     rsi, r8
0x18000e126  mov     rdi, rdx
0x18000e129  mov     r14, rcx
0x18000e12c  mov     qword ptr [rcx], 0
0x18000e133  xorps   xmm0, xmm0
0x18000e136  movups  xmmword ptr [rcx+8], xmm0
0x18000e13a  mov     byte ptr [rcx+18h], 0
0x18000e13e  mov     qword ptr [rcx+58h], 0
0x18000e146  mov     r9d, 1; NumberOfConcurrentThreads
0x18000e14c  xor     r8d, r8d; CompletionKey
0x18000e14f  xor     edx, edx; ExistingCompletionPort
0x18000e151  or      rcx, 0FFFFFFFFFFFFFFFFh; FileHandle
0x18000e155  call    cs:__imp_CreateIoCompletionPort
0x18000e15b  mov     rdx, rax
0x18000e15e  mov     rcx, r14
0x18000e161  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18000e166  mov     rcx, [rsp+68h]
0x18000e16b  lea     rax, aFailedToCreate; "Failed to create completion port"
0x18000e172  mov     [rsp+68h+var_48], rax
0x18000e177  mov     r9, r14
0x18000e17a  lea     r8, aOnecoreuapTerm_19; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x18000e181  mov     edx, 0DAh
0x18000e186  call    ??$Throw_GetLastErrorIfNullMsg@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@$0A@@in1diag3@details@wil@@YAXPEAXIPEBDAEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@2@1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,0>(void *,uint,char const *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &,char const *,...)
0x18000e18b  mov     r9d, 1; NumberOfConcurrentThreads
0x18000e191  xor     r8d, r8d; CompletionKey
0x18000e194  mov     rdx, [r14]; ExistingCompletionPort
0x18000e197  mov     rcx, rdi; FileHandle
0x18000e19a  call    cs:__imp_CreateIoCompletionPort
0x18000e1a0  mov     rcx, [rsp+68h]
0x18000e1a5  lea     rdx, aFailedToAssoci; "Failed to associate completion port wit"...
0x18000e1ac  mov     [rsp+68h+var_48], rdx
0x18000e1b1  mov     r9, rax
0x18000e1b4  lea     r8, aOnecoreuapTerm_19; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x18000e1bb  mov     edx, 0E5h
0x18000e1c0  call    ??$Throw_GetLastErrorIfNullMsg@P6AJPEBUAVENC_VERSION_INFO@Avenc@Rdp@@PEAU123@1@Z$0A@@in1diag3@details@wil@@YAP6AJPEBUAVENC_VERSION_INFO@Avenc@Rdp@@PEAU345@1@ZPEAXIPEBDP6AJ011@Z3ZZ; wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<long (*)(Rdp::Avenc::AVENC_VERSION_INFO const *,Rdp::Avenc::AVENC_VERSION_INFO *,Rdp::Avenc::AVENC_VERSION_INFO *),0>(void *,uint,char const *,long (*)(Rdp::Avenc::AVENC_VERSION_INFO const *,Rdp::Avenc::AVENC_VERSION_INFO *,Rdp::Avenc::AVENC_VERSION_INFO *),char const *,...)
0x18000e1c5  mov     rdx, rsi
0x18000e1c8  lea     rcx, [r14+20h]
0x18000e1cc  call    std__function_void___cdecl_void___unsigned_long_unsigned___int64____operator___Rdp__Stack__Graphics__CChannelPipeline__StartFileIoRead____10____lambda_2__0_
0x18000e1d1  xor     eax, eax
0x18000e1d3  xchg    al, [r14+18h]
0x18000e1d7  mov     [rsp+68h+arg_18], r14
0x18000e1df  lea     rax, ?CompletionPortWorker@CCompletionPortIo@details@TP@Utils@Rdp@@AEAAXXZ; Rdp::Utils::TP::details::CCompletionPortIo::CompletionPortWorker(void)
0x18000e1e6  mov     [rsp+68h+var_38], rax
0x18000e1eb  lea     r8, [rsp+68h+arg_18]
0x18000e1f3  lea     rdx, [rsp+68h+var_38]
0x18000e1f8  lea     rcx, [rsp+68h+var_30]
0x18000e1fd  call    ??$_Start@P8CCompletionPortIo@details@TP@Utils@Rdp@@EAAXXZPEAV12345@@thread@std@@AEAAX$$QEAP8CCompletionPortIo@details@TP@Utils@Rdp@@EAAXXZ$$QEAPEAV23456@@Z; std::thread::_Start<void (Rdp::Utils::TP::details::CCompletionPortIo::*)(void),Rdp::Utils::TP::details::CCompletionPortIo *>(void (Rdp::Utils::TP::details::CCompletionPortIo::*&&)(void),Rdp::Utils::TP::details::CCompletionPortIo * &&)
0x18000e202  lea     rdx, [rsp+68h+var_30]
0x18000e207  lea     rcx, [r14+8]
0x18000e20b  call    ??4thread@std@@QEAAAEAV01@$$QEAV01@@Z; std::thread::operator=(std::thread &&)
0x18000e210  lea     rcx, [rsp+68h+var_30]; this
0x18000e215  call    ??1thread@std@@QEAA@XZ; std::thread::~thread(void)
0x18000e21a  nop
0x18000e21b  mov     rax, r14
0x18000e21e  lea     r11, [rsp+68h+var_18]
0x18000e223  mov     rbx, [r11+28h]
0x18000e227  mov     rbp, [r11+30h]
0x18000e22b  mov     rsp, r11
0x18000e22e  pop     r14
0x18000e230  pop     rdi
0x18000e231  pop     rsi
0x18000e232  retn
```
