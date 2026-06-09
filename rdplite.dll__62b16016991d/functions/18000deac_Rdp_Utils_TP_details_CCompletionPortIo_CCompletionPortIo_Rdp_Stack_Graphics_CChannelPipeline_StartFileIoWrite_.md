# Rdp::Utils::TP::details::CCompletionPortIo::CCompletionPortIo__Rdp::Stack::Graphics::CChannelPipeline::StartFileIoWrite_::_2_::_lambda_1___

- ea: `0x18000deac`
- end: `0x18000dfd3`
- name: `Rdp::Utils::TP::details::CCompletionPortIo::CCompletionPortIo__Rdp::Stack::Graphics::CChannelPipeline::StartFileIoWrite_::_2_::_lambda_1___`
- size: `295`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e45c`

## callees

- `0x18000e270`
- `0x18000ed34`
- `0x18000ed74`
- `0x18000f008`
- `0x18000ff8c`
- `0x18001000c`
- `0x1800129cc`

## import_xrefs

- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x18000def5`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x18000df3a`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x18000def5`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x18000df3a`

## string_xrefs

- `0x18000df0b`: `Failed to create completion port`
- `0x18000df1a`: `onecoreuap\termsrv\rdp_bin\win\common\inc\ThreadPoolIo.h`
- `0x18000df54`: `onecoreuap\termsrv\rdp_bin\win\common\inc\ThreadPoolIo.h`
- `0x18000df45`: `Failed to associate completion port with file handle`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Rdp::Utils::TP::details::CCompletionPortIo::CCompletionPortIo__Rdp::Stack::Graphics::CChannelPipeline::StartFileIoWrite_::_2_::_lambda_1___(
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
  std::function_void___cdecl_void___unsigned_long_unsigned___int64__::operator___Rdp::Stack::Graphics::CChannelPipeline::StartFileIoWrite_::_2_::_lambda_1__0_(
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
0x18000deac  mov     [rsp+arg_8], rbx
0x18000deb1  mov     [rsp+arg_10], rbp
0x18000deb6  mov     [rsp+arg_0], rcx
0x18000debb  push    rsi
0x18000debc  push    rdi
0x18000debd  push    r14
0x18000debf  sub     rsp, 50h
0x18000dec3  mov     rsi, r8
0x18000dec6  mov     rdi, rdx
0x18000dec9  mov     r14, rcx
0x18000decc  mov     qword ptr [rcx], 0
0x18000ded3  xorps   xmm0, xmm0
0x18000ded6  movups  xmmword ptr [rcx+8], xmm0
0x18000deda  mov     byte ptr [rcx+18h], 0
0x18000dede  mov     qword ptr [rcx+58h], 0
0x18000dee6  mov     r9d, 1; NumberOfConcurrentThreads
0x18000deec  xor     r8d, r8d; CompletionKey
0x18000deef  xor     edx, edx; ExistingCompletionPort
0x18000def1  or      rcx, 0FFFFFFFFFFFFFFFFh; FileHandle
0x18000def5  call    cs:__imp_CreateIoCompletionPort
0x18000defb  mov     rdx, rax
0x18000defe  mov     rcx, r14
0x18000df01  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18000df06  mov     rcx, [rsp+68h]
0x18000df0b  lea     rax, aFailedToCreate; "Failed to create completion port"
0x18000df12  mov     [rsp+68h+var_48], rax
0x18000df17  mov     r9, r14
0x18000df1a  lea     r8, aOnecoreuapTerm_19; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x18000df21  mov     edx, 0DAh
0x18000df26  call    ??$Throw_GetLastErrorIfNullMsg@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@$0A@@in1diag3@details@wil@@YAXPEAXIPEBDAEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@2@1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,0>(void *,uint,char const *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &,char const *,...)
0x18000df2b  mov     r9d, 1; NumberOfConcurrentThreads
0x18000df31  xor     r8d, r8d; CompletionKey
0x18000df34  mov     rdx, [r14]; ExistingCompletionPort
0x18000df37  mov     rcx, rdi; FileHandle
0x18000df3a  call    cs:__imp_CreateIoCompletionPort
0x18000df40  mov     rcx, [rsp+68h]
0x18000df45  lea     rdx, aFailedToAssoci; "Failed to associate completion port wit"...
0x18000df4c  mov     [rsp+68h+var_48], rdx
0x18000df51  mov     r9, rax
0x18000df54  lea     r8, aOnecoreuapTerm_19; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x18000df5b  mov     edx, 0E5h
0x18000df60  call    ??$Throw_GetLastErrorIfNullMsg@P6AJPEBUAVENC_VERSION_INFO@Avenc@Rdp@@PEAU123@1@Z$0A@@in1diag3@details@wil@@YAP6AJPEBUAVENC_VERSION_INFO@Avenc@Rdp@@PEAU345@1@ZPEAXIPEBDP6AJ011@Z3ZZ; wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<long (*)(Rdp::Avenc::AVENC_VERSION_INFO const *,Rdp::Avenc::AVENC_VERSION_INFO *,Rdp::Avenc::AVENC_VERSION_INFO *),0>(void *,uint,char const *,long (*)(Rdp::Avenc::AVENC_VERSION_INFO const *,Rdp::Avenc::AVENC_VERSION_INFO *,Rdp::Avenc::AVENC_VERSION_INFO *),char const *,...)
0x18000df65  mov     rdx, rsi
0x18000df68  lea     rcx, [r14+20h]
0x18000df6c  call    std__function_void___cdecl_void___unsigned_long_unsigned___int64____operator___Rdp__Stack__Graphics__CChannelPipeline__StartFileIoWrite____2____lambda_1__0_
0x18000df71  xor     eax, eax
0x18000df73  xchg    al, [r14+18h]
0x18000df77  mov     [rsp+68h+arg_18], r14
0x18000df7f  lea     rax, ?CompletionPortWorker@CCompletionPortIo@details@TP@Utils@Rdp@@AEAAXXZ; Rdp::Utils::TP::details::CCompletionPortIo::CompletionPortWorker(void)
0x18000df86  mov     [rsp+68h+var_38], rax
0x18000df8b  lea     r8, [rsp+68h+arg_18]
0x18000df93  lea     rdx, [rsp+68h+var_38]
0x18000df98  lea     rcx, [rsp+68h+var_30]
0x18000df9d  call    ??$_Start@P8CCompletionPortIo@details@TP@Utils@Rdp@@EAAXXZPEAV12345@@thread@std@@AEAAX$$QEAP8CCompletionPortIo@details@TP@Utils@Rdp@@EAAXXZ$$QEAPEAV23456@@Z; std::thread::_Start<void (Rdp::Utils::TP::details::CCompletionPortIo::*)(void),Rdp::Utils::TP::details::CCompletionPortIo *>(void (Rdp::Utils::TP::details::CCompletionPortIo::*&&)(void),Rdp::Utils::TP::details::CCompletionPortIo * &&)
0x18000dfa2  lea     rdx, [rsp+68h+var_30]
0x18000dfa7  lea     rcx, [r14+8]
0x18000dfab  call    ??4thread@std@@QEAAAEAV01@$$QEAV01@@Z; std::thread::operator=(std::thread &&)
0x18000dfb0  lea     rcx, [rsp+68h+var_30]; this
0x18000dfb5  call    ??1thread@std@@QEAA@XZ; std::thread::~thread(void)
0x18000dfba  nop
0x18000dfbb  mov     rax, r14
0x18000dfbe  lea     r11, [rsp+68h+var_18]
0x18000dfc3  mov     rbx, [r11+28h]
0x18000dfc7  mov     rbp, [r11+30h]
0x18000dfcb  mov     rsp, r11
0x18000dfce  pop     r14
0x18000dfd0  pop     rdi
0x18000dfd1  pop     rsi
0x18000dfd2  retn
```
