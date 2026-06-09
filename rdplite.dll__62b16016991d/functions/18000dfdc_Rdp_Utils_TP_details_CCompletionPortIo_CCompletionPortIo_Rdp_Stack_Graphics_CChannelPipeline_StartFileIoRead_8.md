# Rdp::Utils::TP::details::CCompletionPortIo::CCompletionPortIo__Rdp::Stack::Graphics::CChannelPipeline::StartFileIoRead_::_8_::_lambda_1___

- ea: `0x18000dfdc`
- end: `0x18000e103`
- name: `Rdp::Utils::TP::details::CCompletionPortIo::CCompletionPortIo__Rdp::Stack::Graphics::CChannelPipeline::StartFileIoRead_::_8_::_lambda_1___`
- size: `295`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e5fc`

## callees

- `0x18000e314`
- `0x18000ed34`
- `0x18000ed74`
- `0x18000f008`
- `0x18000ff8c`
- `0x18001000c`
- `0x1800129cc`

## import_xrefs

- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x18000e025`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x18000e06a`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x18000e025`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x18000e06a`

## string_xrefs

- `0x18000e03b`: `Failed to create completion port`
- `0x18000e04a`: `onecoreuap\termsrv\rdp_bin\win\common\inc\ThreadPoolIo.h`
- `0x18000e084`: `onecoreuap\termsrv\rdp_bin\win\common\inc\ThreadPoolIo.h`
- `0x18000e075`: `Failed to associate completion port with file handle`

## pseudocode

```c
__int64 __fastcall Rdp::Utils::TP::details::CCompletionPortIo::CCompletionPortIo__Rdp::Stack::Graphics::CChannelPipeline::StartFileIoRead_::_8_::_lambda_1___(
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
  std::function_void___cdecl_void___unsigned_long_unsigned___int64__::operator___Rdp::Stack::Graphics::CChannelPipeline::StartFileIoRead_::_8_::_lambda_1__0_(
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
0x18000dfdc  mov     [rsp+arg_8], rbx
0x18000dfe1  mov     [rsp+arg_10], rbp
0x18000dfe6  mov     [rsp+arg_0], rcx
0x18000dfeb  push    rsi
0x18000dfec  push    rdi
0x18000dfed  push    r14
0x18000dfef  sub     rsp, 50h
0x18000dff3  mov     rsi, r8
0x18000dff6  mov     rdi, rdx
0x18000dff9  mov     r14, rcx
0x18000dffc  mov     qword ptr [rcx], 0
0x18000e003  xorps   xmm0, xmm0
0x18000e006  movups  xmmword ptr [rcx+8], xmm0
0x18000e00a  mov     byte ptr [rcx+18h], 0
0x18000e00e  mov     qword ptr [rcx+58h], 0
0x18000e016  mov     r9d, 1; NumberOfConcurrentThreads
0x18000e01c  xor     r8d, r8d; CompletionKey
0x18000e01f  xor     edx, edx; ExistingCompletionPort
0x18000e021  or      rcx, 0FFFFFFFFFFFFFFFFh; FileHandle
0x18000e025  call    cs:__imp_CreateIoCompletionPort
0x18000e02b  mov     rdx, rax
0x18000e02e  mov     rcx, r14
0x18000e031  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18000e036  mov     rcx, [rsp+68h]
0x18000e03b  lea     rax, aFailedToCreate; "Failed to create completion port"
0x18000e042  mov     [rsp+68h+var_48], rax
0x18000e047  mov     r9, r14
0x18000e04a  lea     r8, aOnecoreuapTerm_19; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x18000e051  mov     edx, 0DAh
0x18000e056  call    ??$Throw_GetLastErrorIfNullMsg@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@$0A@@in1diag3@details@wil@@YAXPEAXIPEBDAEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@2@1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,0>(void *,uint,char const *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &,char const *,...)
0x18000e05b  mov     r9d, 1; NumberOfConcurrentThreads
0x18000e061  xor     r8d, r8d; CompletionKey
0x18000e064  mov     rdx, [r14]; ExistingCompletionPort
0x18000e067  mov     rcx, rdi; FileHandle
0x18000e06a  call    cs:__imp_CreateIoCompletionPort
0x18000e070  mov     rcx, [rsp+68h]
0x18000e075  lea     rdx, aFailedToAssoci; "Failed to associate completion port wit"...
0x18000e07c  mov     [rsp+68h+var_48], rdx
0x18000e081  mov     r9, rax
0x18000e084  lea     r8, aOnecoreuapTerm_19; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x18000e08b  mov     edx, 0E5h
0x18000e090  call    ??$Throw_GetLastErrorIfNullMsg@P6AJPEBUAVENC_VERSION_INFO@Avenc@Rdp@@PEAU123@1@Z$0A@@in1diag3@details@wil@@YAP6AJPEBUAVENC_VERSION_INFO@Avenc@Rdp@@PEAU345@1@ZPEAXIPEBDP6AJ011@Z3ZZ; wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<long (*)(Rdp::Avenc::AVENC_VERSION_INFO const *,Rdp::Avenc::AVENC_VERSION_INFO *,Rdp::Avenc::AVENC_VERSION_INFO *),0>(void *,uint,char const *,long (*)(Rdp::Avenc::AVENC_VERSION_INFO const *,Rdp::Avenc::AVENC_VERSION_INFO *,Rdp::Avenc::AVENC_VERSION_INFO *),char const *,...)
0x18000e095  mov     rdx, rsi
0x18000e098  lea     rcx, [r14+20h]
0x18000e09c  call    std__function_void___cdecl_void___unsigned_long_unsigned___int64____operator___Rdp__Stack__Graphics__CChannelPipeline__StartFileIoRead____8____lambda_1__0_
0x18000e0a1  xor     eax, eax
0x18000e0a3  xchg    al, [r14+18h]
0x18000e0a7  mov     [rsp+68h+arg_18], r14
0x18000e0af  lea     rax, ?CompletionPortWorker@CCompletionPortIo@details@TP@Utils@Rdp@@AEAAXXZ; Rdp::Utils::TP::details::CCompletionPortIo::CompletionPortWorker(void)
0x18000e0b6  mov     [rsp+68h+var_38], rax
0x18000e0bb  lea     r8, [rsp+68h+arg_18]
0x18000e0c3  lea     rdx, [rsp+68h+var_38]
0x18000e0c8  lea     rcx, [rsp+68h+var_30]
0x18000e0cd  call    ??$_Start@P8CCompletionPortIo@details@TP@Utils@Rdp@@EAAXXZPEAV12345@@thread@std@@AEAAX$$QEAP8CCompletionPortIo@details@TP@Utils@Rdp@@EAAXXZ$$QEAPEAV23456@@Z; std::thread::_Start<void (Rdp::Utils::TP::details::CCompletionPortIo::*)(void),Rdp::Utils::TP::details::CCompletionPortIo *>(void (Rdp::Utils::TP::details::CCompletionPortIo::*&&)(void),Rdp::Utils::TP::details::CCompletionPortIo * &&)
0x18000e0d2  lea     rdx, [rsp+68h+var_30]
0x18000e0d7  lea     rcx, [r14+8]
0x18000e0db  call    ??4thread@std@@QEAAAEAV01@$$QEAV01@@Z; std::thread::operator=(std::thread &&)
0x18000e0e0  lea     rcx, [rsp+68h+var_30]; this
0x18000e0e5  call    ??1thread@std@@QEAA@XZ; std::thread::~thread(void)
0x18000e0ea  nop
0x18000e0eb  mov     rax, r14
0x18000e0ee  lea     r11, [rsp+68h+var_18]
0x18000e0f3  mov     rbx, [r11+28h]
0x18000e0f7  mov     rbp, [r11+30h]
0x18000e0fb  mov     rsp, r11
0x18000e0fe  pop     r14
0x18000e100  pop     rdi
0x18000e101  pop     rsi
0x18000e102  retn
```
