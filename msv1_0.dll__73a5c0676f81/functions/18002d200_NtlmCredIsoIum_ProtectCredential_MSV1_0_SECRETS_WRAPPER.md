# NtlmCredIsoIum::ProtectCredential(_MSV1_0_SECRETS_WRAPPER *)

- ea: `0x18002d200`
- end: `0x18002d2fd`
- name: `?ProtectCredential@NtlmCredIsoIum@@UEAAJPEAU_MSV1_0_SECRETS_WRAPPER@@@Z`
- size: `253`
- prototype: `__int64 __fastcall(NtlmCredIsoIum *__hidden this, struct _MSV1_0_SECRETS_WRAPPER *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001ed0`
- `0x18000dea0`
- `0x1800200e8`
- `0x180020574`
- `0x18002d200`
- `0x180055504`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18002d25e`
- `RPCRT4!NdrClientCall3` at `0x18002d25e`
- `RPCRT4!RpcExceptionFilter` at `0x18006c32e`
- `RPCRT4!RpcExceptionFilter` at `0x18006c32e`
- `RPCRT4!I_RpcMapWin32Status` at `0x18002d276`
- `RPCRT4!I_RpcMapWin32Status` at `0x18002d276`

## string_xrefs

- `0x18002d21d`: `CredentialAlreadyProtected`

## pseudocode

```c
__int64 __fastcall NtlmCredIsoIum::ProtectCredential(NtlmCredIsoIum *this, struct _MSV1_0_SECRETS_WRAPPER *a2)
{
  unsigned int Pointer; // ebx

  if ( *((_BYTE *)a2 + 8) )
  {
    NtlmTraceErrorViaWpp("NtlmCredIsoIum::ProtectCredential", 0xADu, "CredentialAlreadyProtected");
    return 3221225485LL;
  }
  else
  {
    TraceRpcStart("NtlmCredIsoIum::ProtectCredential");
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 1u, 0, *((_QWORD *)this + 2), a2).Pointer;
    TraceRpcEnd("NtlmCredIsoIum::ProtectCredential");
    NtlmTraceStatusViaWpp("NtlmCredIsoIum::ProtectCredential", 188, Pointer);
    return Pointer;
  }
}

```

## disassembly

```asm
0x18002d200  mov     [rsp+arg_0], rbx
0x18002d205  push    rdi
0x18002d206  sub     rsp, 50h
0x18002d20a  mov     rbx, rdx
0x18002d20d  mov     rdi, rcx
0x18002d210  lea     rcx, aNtlmcredisoium_15; "NtlmCredIsoIum::ProtectCredential"
0x18002d217  cmp     byte ptr [rdx+8], 0
0x18002d21b  jz      short loc_18002D238
0x18002d21d  lea     r8, aCredentialalre; "CredentialAlreadyProtected"
0x18002d224  mov     edx, 0ADh; unsigned int
0x18002d229  call    ?NtlmTraceErrorViaWpp@@YAXPEBDK0@Z; NtlmTraceErrorViaWpp(char const *,ulong,char const *)
0x18002d22e  mov     eax, 0C000000Dh
0x18002d233  jmp     loc_18002D2F2
0x18002d238  call    TraceRpcStart
0x18002d23d  nop
0x18002d23e  mov     [rsp+58h+arg_8], 0
0x18002d247  mov     [rsp+58h+var_38], rbx
0x18002d24c  mov     r9, [rdi+10h]
0x18002d250  xor     r8d, r8d; pReturnValue
0x18002d253  lea     edx, [r8+1]; nProcNum
0x18002d257  lea     rcx, pProxyInfo; pProxyInfo
0x18002d25e  call    cs:__imp_NdrClientCall3
0x18002d264  mov     rbx, rax
0x18002d267  mov     [rsp+58h+arg_8], rax
0x18002d26c  mov     [rsp+58h+var_18], eax
0x18002d270  jmp     short loc_18002D2D0
0x18002d272  mov     edi, eax
0x18002d274  mov     ecx, eax; Status
0x18002d276  call    cs:__imp_I_RpcMapWin32Status
0x18002d27c  mov     ebx, eax
0x18002d27e  mov     [rsp+58h+var_18], eax
0x18002d282  mov     ecx, cs:dword_1800861D8
0x18002d288  cmp     ecx, 2
0x18002d28b  jbe     short loc_18002D2D0
0x18002d28d  mov     dword ptr [rsp+58h+arg_8], edi
0x18002d291  mov     [rsp+58h+arg_10], 0B7h
0x18002d299  lea     rax, aNtlmcredisoium_15; "NtlmCredIsoIum::ProtectCredential"
0x18002d2a0  mov     [rsp+58h+arg_18], rax
0x18002d2a5  lea     rax, [rsp+58h+arg_8]
0x18002d2aa  mov     [rsp+58h+var_28], rax
0x18002d2af  lea     rax, [rsp+58h+arg_10]
0x18002d2b4  mov     [rsp+58h+var_30], rax
0x18002d2b9  lea     rax, [rsp+58h+arg_18]
0x18002d2be  mov     [rsp+58h+var_38], rax
0x18002d2c3  lea     rdx, dword_18007ACF4
0x18002d2ca  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002d2cf  nop
0x18002d2d0  lea     rcx, aNtlmcredisoium_15; "NtlmCredIsoIum::ProtectCredential"
0x18002d2d7  call    TraceRpcEnd
0x18002d2dc  mov     r8d, ebx
0x18002d2df  mov     edx, 0BCh
0x18002d2e4  lea     rcx, aNtlmcredisoium_15; "NtlmCredIsoIum::ProtectCredential"
0x18002d2eb  call    NtlmTraceStatusViaWpp
0x18002d2f0  mov     eax, ebx
0x18002d2f2  mov     rbx, [rsp+58h+arg_0]
0x18002d2f7  add     rsp, 50h
0x18002d2fb  pop     rdi
0x18002d2fc  retn
0x18006c320  push    rbp
0x18006c322  sub     rsp, 40h
0x18006c326  mov     rbp, rdx
0x18006c329  mov     rcx, [rcx]
0x18006c32c  mov     ecx, [rcx]; ExceptionCode
0x18006c32e  call    cs:__imp_RpcExceptionFilter
0x18006c334  nop
0x18006c335  add     rsp, 40h
0x18006c339  pop     rbp
0x18006c33a  retn
```
