# NtlmCredIsoIum::GetCredentialKey(_MSV1_0_SECRETS_WRAPPER *,void *,_MSV1_0_CREDENTIAL_KEY_TYPE,_MSV1_0_CREDENTIAL_KEY *)

- ea: `0x180056e10`
- end: `0x180056f32`
- name: `?GetCredentialKey@NtlmCredIsoIum@@UEAAJPEAU_MSV1_0_SECRETS_WRAPPER@@PEAXW4_MSV1_0_CREDENTIAL_KEY_TYPE@@PEAU_MSV1_0_CREDENTIAL_KEY@@@Z`
- size: `290`
- prototype: `int(NtlmCredIsoIum *__hidden this, struct _MSV1_0_SECRETS_WRAPPER *, void *, enum _MSV1_0_CREDENTIAL_KEY_TYPE, struct _MSV1_0_CREDENTIAL_KEY *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180001ed0`
- `0x18000dea0`
- `0x1800200e8`
- `0x180020574`
- `0x180056e10`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x180056e39`
- `ntdll!RtlLengthSid` at `0x180056e39`
- `RPCRT4!NdrClientCall3` at `0x180056e91`
- `RPCRT4!NdrClientCall3` at `0x180056e91`
- `RPCRT4!I_RpcMapWin32Status` at `0x180056ea9`
- `RPCRT4!I_RpcMapWin32Status` at `0x180056ea9`

## pseudocode

```c
__int64 __fastcall NtlmCredIsoIum::GetCredentialKey(
        NtlmCredIsoIum *this,
        struct _MSV1_0_SECRETS_WRAPPER *a2,
        void *a3,
        enum _MSV1_0_CREDENTIAL_KEY_TYPE a4,
        struct _MSV1_0_CREDENTIAL_KEY *a5)
{
  int v10; // [rsp+20h] [rbp-88h]
  ULONG v11; // [rsp+38h] [rbp-70h]
  enum _MSV1_0_CREDENTIAL_KEY_TYPE v12; // [rsp+48h] [rbp-60h]

  TraceRpcStart("NtlmCredIsoIum::GetCredentialKey");
  v12 = a4;
  v11 = RtlLengthSid(a3);
  v10 = NtLmGlobalRootSecret;
  LODWORD(a3) = (unsigned int)NdrClientCall3(
                                (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                                0xCu,
                                0,
                                *((_QWORD *)this + 2),
                                v10,
                                qword_1800876B0,
                                a2,
                                v11,
                                a3,
                                v12,
                                a5).Pointer;
  TraceRpcEnd("NtlmCredIsoIum::GetCredentialKey");
  NtlmTraceStatusViaWpp("NtlmCredIsoIum::GetCredentialKey", 779, (unsigned int)a3);
  return (unsigned int)a3;
}

```

## disassembly

```asm
0x180056e10  push    rbx
0x180056e12  push    rsi
0x180056e13  push    rdi
0x180056e14  push    r14
0x180056e16  sub     rsp, 88h
0x180056e1d  mov     edi, r9d
0x180056e20  mov     rbx, r8
0x180056e23  mov     rsi, rdx
0x180056e26  mov     r14, rcx
0x180056e29  lea     rcx, aNtlmcredisoium_13; "NtlmCredIsoIum::GetCredentialKey"
0x180056e30  call    TraceRpcStart
0x180056e35  nop
0x180056e36  mov     rcx, rbx; Sid
0x180056e39  call    cs:__imp_RtlLengthSid
0x180056e3f  mov     rdx, cs:qword_1800876B0
0x180056e46  mov     r8d, cs:NtLmGlobalRootSecret
0x180056e4d  mov     [rsp+0A8h+var_40], 0
0x180056e56  mov     rcx, [rsp+0A8h+arg_20]
0x180056e5e  mov     [rsp+0A8h+var_58], rcx
0x180056e63  mov     [rsp+0A8h+var_60], edi
0x180056e67  mov     [rsp+0A8h+var_68], rbx
0x180056e6c  mov     [rsp+0A8h+var_70], eax
0x180056e70  mov     [rsp+0A8h+var_78], rsi
0x180056e75  mov     [rsp+0A8h+var_80], rdx
0x180056e7a  mov     dword ptr [rsp+0A8h+var_88], r8d
0x180056e7f  mov     r9, [r14+10h]
0x180056e83  xor     r8d, r8d; pReturnValue
0x180056e86  lea     edx, [r8+0Ch]; nProcNum
0x180056e8a  lea     rcx, pProxyInfo; pProxyInfo
0x180056e91  call    cs:__imp_NdrClientCall3
0x180056e97  mov     rbx, rax
0x180056e9a  mov     [rsp+0A8h+var_40], rax
0x180056e9f  mov     [rsp+0A8h+var_48], eax
0x180056ea3  jmp     short loc_180056F03
0x180056ea5  mov     edi, eax
0x180056ea7  mov     ecx, eax; Status
0x180056ea9  call    cs:__imp_I_RpcMapWin32Status
0x180056eaf  mov     ebx, eax
0x180056eb1  mov     [rsp+0A8h+var_48], eax
0x180056eb5  mov     ecx, cs:dword_1800861D8
0x180056ebb  cmp     ecx, 2
0x180056ebe  jbe     short loc_180056F03
0x180056ec0  mov     [rsp+0A8h+var_44], edi
0x180056ec4  mov     dword ptr [rsp+0A8h+var_40], 309h
0x180056ecc  lea     rax, aNtlmcredisoium_13; "NtlmCredIsoIum::GetCredentialKey"
0x180056ed3  mov     [rsp+0A8h+var_38], rax
0x180056ed8  lea     rax, [rsp+0A8h+var_44]
0x180056edd  mov     [rsp+0A8h+var_78], rax
0x180056ee2  lea     rax, [rsp+0A8h+var_40]
0x180056ee7  mov     [rsp+0A8h+var_80], rax
0x180056eec  lea     rax, [rsp+0A8h+var_38]
0x180056ef1  mov     [rsp+0A8h+var_88], rax
0x180056ef6  lea     rdx, word_18007AB42
0x180056efd  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180056f02  nop
0x180056f03  lea     rcx, aNtlmcredisoium_13; "NtlmCredIsoIum::GetCredentialKey"
0x180056f0a  call    TraceRpcEnd
0x180056f0f  mov     r8d, ebx
0x180056f12  mov     edx, 30Bh
0x180056f17  lea     rcx, aNtlmcredisoium_13; "NtlmCredIsoIum::GetCredentialKey"
0x180056f1e  call    NtlmTraceStatusViaWpp
0x180056f23  mov     eax, ebx
0x180056f25  add     rsp, 88h
0x180056f2c  pop     r14
0x180056f2e  pop     rdi
0x180056f2f  pop     rsi
0x180056f30  pop     rbx
0x180056f31  retn
0x18006c2dc  push    rbp
0x18006c2de  sub     rsp, 60h
0x18006c2e2  mov     rbp, rdx
0x18006c2e5  mov     rcx, [rcx]
0x18006c2e8  mov     ecx, [rcx]; ExceptionCode
0x18006c2ea  call    cs:__imp_RpcExceptionFilter
0x18006c2f0  nop
0x18006c2f1  add     rsp, 60h
0x18006c2f5  pop     rbp
0x18006c2f6  retn
```
