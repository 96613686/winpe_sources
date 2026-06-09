# NtlmCredIsoIum::ComparePasswordToSspCredentialPassword(_UNICODE_STRING *,_SSP_CREDENTIAL *,int *)

- ea: `0x18002cb70`
- end: `0x18002ccf0`
- name: `?ComparePasswordToSspCredentialPassword@NtlmCredIsoIum@@UEAAJPEAU_UNICODE_STRING@@PEAU_SSP_CREDENTIAL@@PEAH@Z`
- size: `384`
- prototype: `__int64 __fastcall(NtlmCredIsoIum *__hidden this, struct _UNICODE_STRING *, struct _SSP_CREDENTIAL *, int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180001ed0`
- `0x18000dea0`
- `0x1800200e8`
- `0x180020574`
- `0x18002cb70`
- `0x18006d010`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18002cc18`
- `RPCRT4!NdrClientCall3` at `0x18002cc18`
- `RPCRT4!RpcExceptionFilter` at `0x18006c284`
- `RPCRT4!RpcExceptionFilter` at `0x18006c284`
- `RPCRT4!I_RpcMapWin32Status` at `0x18002cc30`
- `RPCRT4!I_RpcMapWin32Status` at `0x18002cc30`

## string_xrefs

- `0x18002cbe1`: `NtlmCredIsoIum::ComparePasswordToSspCredentialPassword`
- `0x18002cc53`: `NtlmCredIsoIum::ComparePasswordToSspCredentialPassword`
- `0x18002cc9b`: `NtlmCredIsoIum::ComparePasswordToSspCredentialPassword`
- `0x18002ccc8`: `NtlmCredIsoIum::ComparePasswordToSspCredentialPassword`

## pseudocode

```c
__int64 __fastcall NtlmCredIsoIum::ComparePasswordToSspCredentialPassword(
        NtlmCredIsoIum *this,
        struct _UNICODE_STRING *a2,
        struct _SSP_CREDENTIAL *a3,
        int *a4)
{
  _BYTE *v8; // r14
  _QWORD *v9; // rdi
  unsigned int Pointer; // ebx
  char *v11; // rbx

  v8 = (char *)a3 + 98;
  v9 = (_QWORD *)((char *)a3 + 88);
  if ( *((_BYTE *)a3 + 98) )
  {
    v11 = (char *)a3 + 80;
    ((void (__fastcall *)(_QWORD, _QWORD))qword_180088378)(*v9, *((unsigned __int16 *)a3 + 41));
    TraceRpcStart("NtlmCredIsoIum::ComparePasswordToSspCredentialPassword");
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                              0x14u,
                              0,
                              *((_QWORD *)this + 2),
                              a2,
                              v11,
                              a4).Pointer;
    TraceRpcEnd("NtlmCredIsoIum::ComparePasswordToSspCredentialPassword");
  }
  else
  {
    Pointer = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 184LL))(*((_QWORD *)this + 1));
  }
  if ( *v8 )
    ((void (__fastcall *)(_QWORD, _QWORD))qword_180088370)(*v9, *((unsigned __int16 *)a3 + 41));
  NtlmTraceStatusViaWpp("NtlmCredIsoIum::ComparePasswordToSspCredentialPassword", 1029, Pointer);
  return Pointer;
}

```

## disassembly

```asm
0x18002cb70  mov     [rsp+arg_0], rbx
0x18002cb75  mov     [rsp+arg_8], rsi
0x18002cb7a  mov     [rsp+arg_10], r8
0x18002cb7f  push    rdi
0x18002cb80  push    r12
0x18002cb82  push    r13
0x18002cb84  push    r14
0x18002cb86  push    r15
0x18002cb88  sub     rsp, 70h
0x18002cb8c  mov     r15, r9
0x18002cb8f  mov     rsi, r8
0x18002cb92  mov     r12, rdx
0x18002cb95  mov     r13, rcx
0x18002cb98  lea     r14, [r8+62h]
0x18002cb9c  mov     [rsp+98h+var_38], r14
0x18002cba1  lea     rdi, [r8+58h]
0x18002cba5  mov     [rsp+98h+var_40], rdi
0x18002cbaa  cmp     byte ptr [r14], 0
0x18002cbae  jnz     short loc_18002CBCA
0x18002cbb0  mov     rcx, [rcx+8]
0x18002cbb4  mov     rax, [rcx]
0x18002cbb7  mov     rax, [rax+0B8h]
0x18002cbbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cbc3  mov     ebx, eax
0x18002cbc5  jmp     loc_18002CCA7
0x18002cbca  lea     rbx, [r8+50h]
0x18002cbce  movzx   edx, word ptr [rbx+2]
0x18002cbd2  mov     rcx, [rdi]
0x18002cbd5  mov     rax, cs:qword_180088378
0x18002cbdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cbe1  lea     rcx, aNtlmcredisoium; "NtlmCredIsoIum::ComparePasswordToSspCre"...
0x18002cbe8  call    TraceRpcStart
0x18002cbed  nop
0x18002cbee  mov     [rsp+98h+var_50], 0
0x18002cbf7  mov     [rsp+98h+var_68], r15
0x18002cbfc  mov     [rsp+98h+var_70], rbx
0x18002cc01  mov     [rsp+98h+var_78], r12
0x18002cc06  mov     r9, [r13+10h]
0x18002cc0a  xor     r8d, r8d; pReturnValue
0x18002cc0d  lea     edx, [r8+14h]; nProcNum
0x18002cc11  lea     rcx, pProxyInfo; pProxyInfo
0x18002cc18  call    cs:__imp_NdrClientCall3
0x18002cc1e  mov     rbx, rax
0x18002cc21  mov     [rsp+98h+var_50], rax
0x18002cc26  mov     [rsp+98h+var_58], eax
0x18002cc2a  jmp     short loc_18002CC9B
0x18002cc2c  mov     edi, eax
0x18002cc2e  mov     ecx, eax; Status
0x18002cc30  call    cs:__imp_I_RpcMapWin32Status
0x18002cc36  mov     ebx, eax
0x18002cc38  mov     [rsp+98h+var_58], eax
0x18002cc3c  mov     ecx, cs:dword_1800861D8
0x18002cc42  cmp     ecx, 2
0x18002cc45  jbe     short loc_18002CC89
0x18002cc47  mov     [rsp+98h+var_54], edi
0x18002cc4b  mov     dword ptr [rsp+98h+var_50], 3F4h
0x18002cc53  lea     rax, aNtlmcredisoium; "NtlmCredIsoIum::ComparePasswordToSspCre"...
0x18002cc5a  mov     [rsp+98h+var_48], rax
0x18002cc5f  lea     rax, [rsp+98h+var_54]
0x18002cc64  mov     [rsp+98h+var_68], rax
0x18002cc69  lea     rax, [rsp+98h+var_50]
0x18002cc6e  mov     [rsp+98h+var_70], rax
0x18002cc73  lea     rax, [rsp+98h+var_48]
0x18002cc78  mov     [rsp+98h+var_78], rax
0x18002cc7d  lea     rdx, unk_18007AF60
0x18002cc84  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002cc89  mov     rsi, [rsp+98h+arg_10]
0x18002cc91  mov     rdi, [rsp+98h+var_40]
0x18002cc96  mov     r14, [rsp+98h+var_38]
0x18002cc9b  lea     rcx, aNtlmcredisoium; "NtlmCredIsoIum::ComparePasswordToSspCre"...
0x18002cca2  call    TraceRpcEnd
0x18002cca7  cmp     byte ptr [r14], 0
0x18002ccab  jz      short loc_18002CCC0
0x18002ccad  movzx   edx, word ptr [rsi+52h]
0x18002ccb1  mov     rcx, [rdi]
0x18002ccb4  mov     rax, cs:qword_180088370
0x18002ccbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ccc0  mov     r8d, ebx
0x18002ccc3  mov     edx, 405h
0x18002ccc8  lea     rcx, aNtlmcredisoium; "NtlmCredIsoIum::ComparePasswordToSspCre"...
0x18002cccf  call    NtlmTraceStatusViaWpp
0x18002ccd4  mov     eax, ebx
0x18002ccd6  lea     r11, [rsp+98h+var_28]
0x18002ccdb  mov     rbx, [r11+30h]
0x18002ccdf  mov     rsi, [r11+38h]
0x18002cce3  mov     rsp, r11
0x18002cce6  pop     r15
0x18002cce8  pop     r14
0x18002ccea  pop     r13
0x18002ccec  pop     r12
0x18002ccee  pop     rdi
0x18002ccef  retn
0x18006c276  push    rbp
0x18006c278  sub     rsp, 40h
0x18006c27c  mov     rbp, rdx
0x18006c27f  mov     rcx, [rcx]
0x18006c282  mov     ecx, [rcx]; ExceptionCode
0x18006c284  call    cs:__imp_RpcExceptionFilter
0x18006c28a  nop
0x18006c28b  add     rsp, 40h
0x18006c28f  pop     rbp
0x18006c290  retn
```
