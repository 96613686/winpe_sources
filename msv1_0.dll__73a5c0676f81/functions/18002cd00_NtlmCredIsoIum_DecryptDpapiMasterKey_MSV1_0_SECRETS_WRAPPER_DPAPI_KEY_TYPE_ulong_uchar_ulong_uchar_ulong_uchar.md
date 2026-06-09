# NtlmCredIsoIum::DecryptDpapiMasterKey(_MSV1_0_SECRETS_WRAPPER *,_DPAPI_KEY_TYPE,ulong,uchar *,ulong,uchar *,ulong,uchar *,void *,ulong *,uchar * *)

- ea: `0x18002cd00`
- end: `0x18002cedb`
- name: `?DecryptDpapiMasterKey@NtlmCredIsoIum@@UEAAJPEAU_MSV1_0_SECRETS_WRAPPER@@W4_DPAPI_KEY_TYPE@@KPEAEK2K2PEAXPEAKPEAPEAE@Z`
- size: `475`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180001ed0`
- `0x18000dea0`
- `0x1800200e8`
- `0x180020574`
- `0x18002cd00`
- `0x180057844`
- `0x18006d010`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18002cdbc`
- `ntdll!RtlLengthSid` at `0x18002cdbc`
- `RPCRT4!RpcExceptionFilter` at `0x18006c2a6`
- `RPCRT4!RpcExceptionFilter` at `0x18006c2a6`
- `RPCRT4!I_RpcMapWin32Status` at `0x18002ce40`
- `RPCRT4!I_RpcMapWin32Status` at `0x18002ce40`

## pseudocode

```c
__int64 __fastcall NtlmCredIsoIum::DecryptDpapiMasterKey(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4,
        __int64 a5,
        int a6,
        __int64 a7,
        int a8,
        __int64 a9,
        PSID Sid,
        __int64 a11,
        __int64 a12)
{
  int v14; // edi
  unsigned int v16; // ebx
  ULONG v17; // eax

  v14 = a2;
  if ( *(_BYTE *)(a2 + 8) )
  {
    TraceRpcStart("NtlmCredIsoIum::DecryptDpapiMasterKey");
    v17 = RtlLengthSid(Sid);
    v16 = NtlmIumDecryptDpapiMasterKey(
            *(_QWORD *)(a1 + 16),
            v14,
            a3,
            a4,
            a5,
            a6,
            a7,
            a8,
            a9,
            v17,
            (__int64)Sid,
            a11,
            a12);
    TraceRpcEnd("NtlmCredIsoIum::DecryptDpapiMasterKey");
  }
  else
  {
    v16 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 8) + 96LL))(*(_QWORD *)(a1 + 8), a2);
  }
  NtlmTraceStatusViaWpp("NtlmCredIsoIum::DecryptDpapiMasterKey", 694, v16);
  return v16;
}

```

## disassembly

```asm
0x18002cd00  mov     r11, rsp
0x18002cd03  mov     [r11+8], rbx
0x18002cd07  mov     [r11+18h], rsi
0x18002cd0b  push    rdi
0x18002cd0c  push    r14
0x18002cd0e  push    r15
0x18002cd10  sub     rsp, 80h
0x18002cd17  mov     esi, r9d
0x18002cd1a  mov     r14d, r8d
0x18002cd1d  mov     rdi, rdx
0x18002cd20  mov     r15, rcx
0x18002cd23  cmp     byte ptr [rdx+8], 0
0x18002cd27  jnz     short loc_18002CDA4
0x18002cd29  mov     rcx, [rcx+8]
0x18002cd2d  mov     rax, [rcx]
0x18002cd30  mov     r10, [rax+60h]
0x18002cd34  mov     rax, [rsp+98h+arg_58]
0x18002cd3c  mov     [r11-40h], rax
0x18002cd40  mov     rax, [rsp+98h+arg_50]
0x18002cd48  mov     [r11-48h], rax
0x18002cd4c  mov     rax, [rsp+98h+Sid]
0x18002cd54  mov     [r11-50h], rax
0x18002cd58  mov     rdx, [rsp+98h+arg_40]
0x18002cd60  mov     [r11-58h], rdx
0x18002cd64  mov     edx, [rsp+98h+arg_38]
0x18002cd6b  mov     [rsp+98h+var_60], edx
0x18002cd6f  mov     rdx, [rsp+98h+arg_30]
0x18002cd77  mov     [r11-68h], rdx
0x18002cd7b  mov     edx, [rsp+98h+arg_28]
0x18002cd82  mov     dword ptr [rsp+98h+var_70], edx
0x18002cd86  mov     rdx, [rsp+98h+arg_20]
0x18002cd8e  mov     [r11-78h], rdx
0x18002cd92  mov     rdx, rdi
0x18002cd95  mov     rax, r10
0x18002cd98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cd9d  mov     ebx, eax
0x18002cd9f  jmp     loc_18002CEAC
0x18002cda4  lea     rcx, aNtlmcredisoium_20; "NtlmCredIsoIum::DecryptDpapiMasterKey"
0x18002cdab  call    TraceRpcStart
0x18002cdb0  nop
0x18002cdb1  mov     rbx, [rsp+98h+Sid]
0x18002cdb9  mov     rcx, rbx; Sid
0x18002cdbc  call    cs:__imp_RtlLengthSid
0x18002cdc2  mov     rcx, [rsp+98h+arg_58]
0x18002cdca  mov     [rsp+98h+var_38], rcx
0x18002cdcf  mov     rcx, [rsp+98h+arg_50]
0x18002cdd7  mov     [rsp+98h+var_40], rcx
0x18002cddc  mov     [rsp+98h+var_48], rbx
0x18002cde1  mov     [rsp+98h+var_50], eax
0x18002cde5  mov     rax, [rsp+98h+arg_40]
0x18002cded  mov     [rsp+98h+var_58], rax
0x18002cdf2  mov     eax, [rsp+98h+arg_38]
0x18002cdf9  mov     [rsp+98h+var_60], eax
0x18002cdfd  mov     rax, [rsp+98h+arg_30]
0x18002ce05  mov     [rsp+98h+var_68], rax
0x18002ce0a  mov     eax, [rsp+98h+arg_28]
0x18002ce11  mov     dword ptr [rsp+98h+var_70], eax
0x18002ce15  mov     rax, [rsp+98h+arg_20]
0x18002ce1d  mov     [rsp+98h+var_78], rax
0x18002ce22  mov     r9d, esi
0x18002ce25  mov     r8d, r14d
0x18002ce28  mov     rdx, rdi
0x18002ce2b  mov     rcx, [r15+10h]
0x18002ce2f  call    NtlmIumDecryptDpapiMasterKey
0x18002ce34  mov     ebx, eax
0x18002ce36  mov     [rsp+98h+var_28], eax
0x18002ce3a  jmp     short loc_18002CEA0
0x18002ce3c  mov     edi, eax
0x18002ce3e  mov     ecx, eax; Status
0x18002ce40  call    cs:__imp_I_RpcMapWin32Status
0x18002ce46  mov     ebx, eax
0x18002ce48  mov     [rsp+98h+var_28], eax
0x18002ce4c  mov     ecx, cs:dword_1800861D8
0x18002ce52  cmp     ecx, 2
0x18002ce55  jbe     short loc_18002CEA0
0x18002ce57  mov     [rsp+98h+arg_8], edi
0x18002ce5e  mov     [rsp+98h+var_24], 2B3h
0x18002ce66  lea     rax, aNtlmcredisoium_20; "NtlmCredIsoIum::DecryptDpapiMasterKey"
0x18002ce6d  mov     [rsp+98h+var_20], rax
0x18002ce72  lea     rax, [rsp+98h+arg_8]
0x18002ce7a  mov     [rsp+98h+var_68], rax
0x18002ce7f  lea     rax, [rsp+98h+var_24]
0x18002ce84  mov     [rsp+98h+var_70], rax
0x18002ce89  lea     rax, [rsp+98h+var_20]
0x18002ce8e  mov     [rsp+98h+var_78], rax
0x18002ce93  lea     rdx, word_18007ADAE
0x18002ce9a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002ce9f  nop
0x18002cea0  lea     rcx, aNtlmcredisoium_20; "NtlmCredIsoIum::DecryptDpapiMasterKey"
0x18002cea7  call    TraceRpcEnd
0x18002ceac  mov     r8d, ebx
0x18002ceaf  mov     edx, 2B6h
0x18002ceb4  lea     rcx, aNtlmcredisoium_20; "NtlmCredIsoIum::DecryptDpapiMasterKey"
0x18002cebb  call    NtlmTraceStatusViaWpp
0x18002cec0  mov     eax, ebx
0x18002cec2  lea     r11, [rsp+98h+var_18]
0x18002ceca  mov     rbx, [r11+20h]
0x18002cece  mov     rsi, [r11+30h]
0x18002ced2  mov     rsp, r11
0x18002ced5  pop     r15
0x18002ced7  pop     r14
0x18002ced9  pop     rdi
0x18002ceda  retn
0x18006c298  push    rbp
0x18006c29a  sub     rsp, 70h
0x18006c29e  mov     rbp, rdx
0x18006c2a1  mov     rcx, [rcx]
0x18006c2a4  mov     ecx, [rcx]; ExceptionCode
0x18006c2a6  call    cs:__imp_RpcExceptionFilter
0x18006c2ac  nop
0x18006c2ad  add     rsp, 70h
0x18006c2b1  pop     rbp
0x18006c2b2  retn
```
