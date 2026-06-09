# NtlmCredIsoIum::CompareCredentials(_MSV1_0_SECRETS_WRAPPER *,_MSV1_0_SECRETS_WRAPPER *,int *,int *,int *)

- ea: `0x18002c9f0`
- end: `0x18002cb65`
- name: `?CompareCredentials@NtlmCredIsoIum@@UEAAJPEAU_MSV1_0_SECRETS_WRAPPER@@0PEAH11@Z`
- size: `373`
- prototype: `__int64 __fastcall(NtlmCredIsoIum *__hidden this, struct _MSV1_0_SECRETS_WRAPPER *, struct _MSV1_0_SECRETS_WRAPPER *, int *, int *, int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180001ed0`
- `0x18000dea0`
- `0x1800200e8`
- `0x180020574`
- `0x18002c9f0`
- `0x18006d010`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18002caae`
- `RPCRT4!NdrClientCall3` at `0x18002caae`
- `RPCRT4!RpcExceptionFilter` at `0x18006c262`
- `RPCRT4!RpcExceptionFilter` at `0x18006c262`
- `RPCRT4!I_RpcMapWin32Status` at `0x18002cac9`
- `RPCRT4!I_RpcMapWin32Status` at `0x18002cac9`

## string_xrefs

- `0x18002ca6a`: `NtlmCredIsoIum::CompareCredentials`
- `0x18002caf2`: `NtlmCredIsoIum::CompareCredentials`
- `0x18002cb35`: `NtlmCredIsoIum::CompareCredentials`
- `0x18002cb49`: `NtlmCredIsoIum::CompareCredentials`

## pseudocode

```c
__int64 __fastcall NtlmCredIsoIum::CompareCredentials(
        NtlmCredIsoIum *this,
        struct _MSV1_0_SECRETS_WRAPPER *a2,
        struct _MSV1_0_SECRETS_WRAPPER *a3,
        int *a4,
        int *a5,
        int *a6)
{
  unsigned int Pointer; // ebx

  if ( a4 )
    *a4 = 0;
  if ( a5 )
    *a5 = 0;
  if ( a6 )
    *a6 = 0;
  if ( *((_BYTE *)a2 + 8) || *((_BYTE *)a3 + 8) )
  {
    TraceRpcStart("NtlmCredIsoIum::CompareCredentials");
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                              9u,
                              0,
                              *((_QWORD *)this + 2),
                              a2,
                              a3,
                              a4,
                              a5,
                              a6).Pointer;
    TraceRpcEnd("NtlmCredIsoIum::CompareCredentials");
  }
  else
  {
    Pointer = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 88LL))(*((_QWORD *)this + 1));
  }
  NtlmTraceStatusViaWpp("NtlmCredIsoIum::CompareCredentials", 540, Pointer);
  return Pointer;
}

```

## disassembly

```asm
0x18002c9f0  push    rbx
0x18002c9f2  push    rsi
0x18002c9f3  push    rdi
0x18002c9f4  push    r13
0x18002c9f6  push    r14
0x18002c9f8  push    r15
0x18002c9fa  sub     rsp, 68h
0x18002c9fe  mov     rsi, r9
0x18002ca01  mov     r14, r8
0x18002ca04  mov     r15, rdx
0x18002ca07  mov     r13, rcx
0x18002ca0a  test    r9, r9
0x18002ca0d  jz      short loc_18002CA16
0x18002ca0f  mov     dword ptr [r9], 0
0x18002ca16  mov     rbx, [rsp+98h+arg_20]
0x18002ca1e  test    rbx, rbx
0x18002ca21  jz      short loc_18002CA29
0x18002ca23  mov     dword ptr [rbx], 0
0x18002ca29  mov     rdi, [rsp+98h+arg_28]
0x18002ca31  test    rdi, rdi
0x18002ca34  jz      short loc_18002CA3C
0x18002ca36  mov     dword ptr [rdi], 0
0x18002ca3c  cmp     byte ptr [rdx+8], 0
0x18002ca40  jnz     short loc_18002CA6A
0x18002ca42  cmp     byte ptr [r8+8], 0
0x18002ca47  jnz     short loc_18002CA6A
0x18002ca49  mov     rcx, [rcx+8]
0x18002ca4d  mov     rax, [rcx]
0x18002ca50  mov     [rsp+98h+var_70], rdi
0x18002ca55  mov     [rsp+98h+var_78], rbx
0x18002ca5a  mov     rax, [rax+58h]
0x18002ca5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ca63  mov     ebx, eax
0x18002ca65  jmp     loc_18002CB41
0x18002ca6a  lea     rcx, aNtlmcredisoium_16; "NtlmCredIsoIum::CompareCredentials"
0x18002ca71  call    TraceRpcStart
0x18002ca76  nop
0x18002ca77  mov     [rsp+98h+arg_20], 0
0x18002ca83  mov     [rsp+98h+var_58], rdi
0x18002ca88  mov     [rsp+98h+var_60], rbx
0x18002ca8d  mov     [rsp+98h+var_68], rsi
0x18002ca92  mov     [rsp+98h+var_70], r14
0x18002ca97  mov     [rsp+98h+var_78], r15
0x18002ca9c  mov     r9, [r13+10h]
0x18002caa0  xor     r8d, r8d; pReturnValue
0x18002caa3  lea     edx, [r8+9]; nProcNum
0x18002caa7  lea     rcx, pProxyInfo; pProxyInfo
0x18002caae  call    cs:__imp_NdrClientCall3
0x18002cab4  mov     rbx, rax
0x18002cab7  mov     [rsp+98h+arg_20], rax
0x18002cabf  mov     [rsp+98h+var_48], eax
0x18002cac3  jmp     short loc_18002CB35
0x18002cac5  mov     edi, eax
0x18002cac7  mov     ecx, eax; Status
0x18002cac9  call    cs:__imp_I_RpcMapWin32Status
0x18002cacf  mov     ebx, eax
0x18002cad1  mov     [rsp+98h+var_48], eax
0x18002cad5  mov     ecx, cs:dword_1800861D8
0x18002cadb  cmp     ecx, 2
0x18002cade  jbe     short loc_18002CB35
0x18002cae0  mov     dword ptr [rsp+98h+arg_20], edi
0x18002cae7  mov     dword ptr [rsp+98h+arg_28], 219h
0x18002caf2  lea     rax, aNtlmcredisoium_16; "NtlmCredIsoIum::CompareCredentials"
0x18002caf9  mov     [rsp+98h+arg_8], rax
0x18002cb01  lea     rax, [rsp+98h+arg_20]
0x18002cb09  mov     [rsp+98h+var_68], rax
0x18002cb0e  lea     rax, [rsp+98h+arg_28]
0x18002cb16  mov     [rsp+98h+var_70], rax
0x18002cb1b  lea     rax, [rsp+98h+arg_8]
0x18002cb23  mov     [rsp+98h+var_78], rax
0x18002cb28  lea     rdx, dword_18007AFDC
0x18002cb2f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002cb34  nop
0x18002cb35  lea     rcx, aNtlmcredisoium_16; "NtlmCredIsoIum::CompareCredentials"
0x18002cb3c  call    TraceRpcEnd
0x18002cb41  mov     r8d, ebx
0x18002cb44  mov     edx, 21Ch
0x18002cb49  lea     rcx, aNtlmcredisoium_16; "NtlmCredIsoIum::CompareCredentials"
0x18002cb50  call    NtlmTraceStatusViaWpp
0x18002cb55  mov     eax, ebx
0x18002cb57  add     rsp, 68h
0x18002cb5b  pop     r15
0x18002cb5d  pop     r14
0x18002cb5f  pop     r13
0x18002cb61  pop     rdi
0x18002cb62  pop     rsi
0x18002cb63  pop     rbx
0x18002cb64  retn
0x18006c254  push    rbp
0x18006c256  sub     rsp, 50h
0x18006c25a  mov     rbp, rdx
0x18006c25d  mov     rcx, [rcx]
0x18006c260  mov     ecx, [rcx]; ExceptionCode
0x18006c262  call    cs:__imp_RpcExceptionFilter
0x18006c268  nop
0x18006c269  add     rsp, 50h
0x18006c26d  pop     rbp
0x18006c26e  retn
```
