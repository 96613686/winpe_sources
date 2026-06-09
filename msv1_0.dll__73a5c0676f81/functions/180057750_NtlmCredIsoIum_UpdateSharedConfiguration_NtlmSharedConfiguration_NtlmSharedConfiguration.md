# NtlmCredIsoIum::UpdateSharedConfiguration(_NtlmSharedConfiguration *,_NtlmSharedConfiguration *)

- ea: `0x180057750`
- end: `0x18005783e`
- name: `?UpdateSharedConfiguration@NtlmCredIsoIum@@UEAAJPEAU_NtlmSharedConfiguration@@0@Z`
- size: `238`
- prototype: `__int64 __fastcall(NtlmCredIsoIum *__hidden this, struct _NtlmSharedConfiguration *, struct _NtlmSharedConfiguration *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callees

- `0x180001ed0`
- `0x18000dea0`
- `0x1800200e8`
- `0x180020574`
- `0x180057750`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18005779a`
- `RPCRT4!NdrClientCall3` at `0x18005779a`
- `RPCRT4!RpcExceptionFilter` at `0x18006c21e`
- `RPCRT4!RpcExceptionFilter` at `0x18006c21e`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800577b2`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800577b2`

## string_xrefs

- `0x180057768`: `NtlmCredIsoIum::UpdateSharedConfiguration`
- `0x1800577d5`: `NtlmCredIsoIum::UpdateSharedConfiguration`
- `0x18005780c`: `NtlmCredIsoIum::UpdateSharedConfiguration`
- `0x180057820`: `NtlmCredIsoIum::UpdateSharedConfiguration`

## pseudocode

```c
__int64 __fastcall NtlmCredIsoIum::UpdateSharedConfiguration(
        NtlmCredIsoIum *this,
        struct _NtlmSharedConfiguration *a2,
        struct _NtlmSharedConfiguration *a3)
{
  TraceRpcStart("NtlmCredIsoIum::UpdateSharedConfiguration");
  LODWORD(a3) = (unsigned int)NdrClientCall3(
                                (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                                0xDu,
                                0,
                                *((_QWORD *)this + 2),
                                a2,
                                a3).Pointer;
  TraceRpcEnd("NtlmCredIsoIum::UpdateSharedConfiguration");
  NtlmTraceStatusViaWpp("NtlmCredIsoIum::UpdateSharedConfiguration", 803, (unsigned int)a3);
  return (unsigned int)a3;
}

```

## disassembly

```asm
0x180057750  mov     [rsp+arg_0], rbx
0x180057755  mov     [rsp+arg_8], rsi
0x18005775a  push    rdi
0x18005775b  sub     rsp, 50h
0x18005775f  mov     rbx, r8
0x180057762  mov     rdi, rdx
0x180057765  mov     rsi, rcx
0x180057768  lea     rcx, aNtlmcredisoium_12; "NtlmCredIsoIum::UpdateSharedConfigurati"...
0x18005776f  call    TraceRpcStart
0x180057774  nop
0x180057775  mov     [rsp+58h+arg_18], 0
0x18005777e  mov     [rsp+58h+var_30], rbx
0x180057783  mov     [rsp+58h+var_38], rdi
0x180057788  mov     r9, [rsi+10h]
0x18005778c  xor     r8d, r8d; pReturnValue
0x18005778f  lea     edx, [r8+0Dh]; nProcNum
0x180057793  lea     rcx, pProxyInfo; pProxyInfo
0x18005779a  call    cs:__imp_NdrClientCall3
0x1800577a0  mov     rbx, rax
0x1800577a3  mov     [rsp+58h+arg_18], rax
0x1800577a8  mov     [rsp+58h+var_18], eax
0x1800577ac  jmp     short loc_18005780C
0x1800577ae  mov     edi, eax
0x1800577b0  mov     ecx, eax; Status
0x1800577b2  call    cs:__imp_I_RpcMapWin32Status
0x1800577b8  mov     ebx, eax
0x1800577ba  mov     [rsp+58h+var_18], eax
0x1800577be  mov     ecx, cs:dword_1800861D8
0x1800577c4  cmp     ecx, 2
0x1800577c7  jbe     short loc_18005780C
0x1800577c9  mov     dword ptr [rsp+58h+arg_18], edi
0x1800577cd  mov     [rsp+58h+var_14], 321h
0x1800577d5  lea     rax, aNtlmcredisoium_12; "NtlmCredIsoIum::UpdateSharedConfigurati"...
0x1800577dc  mov     [rsp+58h+var_10], rax
0x1800577e1  lea     rax, [rsp+58h+arg_18]
0x1800577e6  mov     [rsp+58h+var_28], rax
0x1800577eb  lea     rax, [rsp+58h+var_14]
0x1800577f0  mov     [rsp+58h+var_30], rax
0x1800577f5  lea     rax, [rsp+58h+var_10]
0x1800577fa  mov     [rsp+58h+var_38], rax
0x1800577ff  lea     rdx, dword_18007AEE4
0x180057806  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18005780b  nop
0x18005780c  lea     rcx, aNtlmcredisoium_12; "NtlmCredIsoIum::UpdateSharedConfigurati"...
0x180057813  call    TraceRpcEnd
0x180057818  mov     r8d, ebx
0x18005781b  mov     edx, 323h
0x180057820  lea     rcx, aNtlmcredisoium_12; "NtlmCredIsoIum::UpdateSharedConfigurati"...
0x180057827  call    NtlmTraceStatusViaWpp
0x18005782c  mov     eax, ebx
0x18005782e  mov     rbx, [rsp+58h+arg_0]
0x180057833  mov     rsi, [rsp+58h+arg_8]
0x180057838  add     rsp, 50h
0x18005783c  pop     rdi
0x18005783d  retn
0x18006c210  push    rbp
0x18006c212  sub     rsp, 40h
0x18006c216  mov     rbp, rdx
0x18006c219  mov     rcx, [rcx]
0x18006c21c  mov     ecx, [rcx]; ExceptionCode
0x18006c21e  call    cs:__imp_RpcExceptionFilter
0x18006c224  nop
0x18006c225  add     rsp, 40h
0x18006c229  pop     rbp
0x18006c22a  retn
```
