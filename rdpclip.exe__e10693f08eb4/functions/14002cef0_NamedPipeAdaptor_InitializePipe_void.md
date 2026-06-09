# NamedPipeAdaptor::InitializePipe(void)

- ea: `0x14002cef0`
- end: `0x14002d053`
- name: `?InitializePipe@NamedPipeAdaptor@@AEAAJXZ`
- size: `355`
- prototype: `__int64 __fastcall(NamedPipeAdaptor *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14002d770`

## callees

- `0x1400022fc`
- `0x140008188`
- `0x14002c030`
- `0x14002c074`
- `0x14002c270`
- `0x14002cc10`
- `0x14002cef0`
- `0x14002d05c`
- `0x14002dc6c`
- `0x14006b010`

## import_xrefs

- `api-ms-win-core-namedpipe-l1-1-0!CreateNamedPipeW` at `0x14002cf88`
- `api-ms-win-core-namedpipe-l1-1-0!CreateNamedPipeW` at `0x14002cf88`

## string_xrefs

- `0x14002cf23`: `clientcore\termsrv\rdpplatform\common\namedpipe\namedpipeadaptor.cpp`
- `0x14002cfc7`: `clientcore\termsrv\rdpplatform\common\namedpipe\namedpipeadaptor.cpp`
- `0x14002cfc0`: `CreateNamedPipe failed`

## pseudocode

```c
__int64 __fastcall NamedPipeAdaptor::InitializePipe(NamedPipeAdaptor *this)
{
  int v2; // eax
  unsigned int LastErrorMsg; // ebx
  const WCHAR *v4; // rcx
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  int nOutBufferSize; // [rsp+20h] [rbp-40h]
  DWORD nOutBufferSizeb; // [rsp+20h] [rbp-40h]
  const char *nOutBufferSizea; // [rsp+20h] [rbp-40h]
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+80h] [rbp+20h] BYREF
  const unsigned __int16 *ModeName; // [rsp+88h] [rbp+28h] BYREF
  __int64 v16; // [rsp+90h] [rbp+30h] BYREF
  __int64 v17; // [rsp+98h] [rbp+38h] BYREF

  if ( *((_DWORD *)this + 16) == 1 )
  {
    SecurityDescriptor = 0;
    v2 = NamedPipeAdaptor::InitializePipeSecurityDescriptor(this, &SecurityDescriptor);
    LastErrorMsg = v2;
    if ( v2 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x130,
        (unsigned int)"clientcore\\termsrv\\rdpplatform\\common\\namedpipe\\namedpipeadaptor.cpp",
        (const char *)(unsigned int)v2,
        nOutBufferSize);
LABEL_6:
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_DestroyPrivateObjectSecurity_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&SecurityDescriptor);
      return LastErrorMsg;
    }
    v4 = (const WCHAR *)*((_QWORD *)this + 13);
    SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
    nOutBufferSizeb = *((_DWORD *)this + 35);
    *(_QWORD *)&SecurityAttributes.nLength = 24;
    *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
    ModeName = (const unsigned __int16 *)CreateNamedPipeW(
                                           v4,
                                           0x40000003u,
                                           6u,
                                           0xFFu,
                                           nOutBufferSizeb,
                                           nOutBufferSizeb,
                                           0,
                                           &SecurityAttributes);
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      (char *)this + 200,
      &ModeName);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ModeName);
    if ( ((*((_QWORD *)this + 25) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                       retaddr,
                       (void *)0x141,
                       (unsigned int)"clientcore\\termsrv\\rdpplatform\\common\\namedpipe\\namedpipeadaptor.cpp",
                       "CreateNamedPipe failed",
                       nOutBufferSizea);
      goto LABEL_6;
    }
    if ( (unsigned int)dword_140088090 > 5 )
    {
      ModeName = NamedPipeAdaptor::GetModeName(this);
      v16 = *((_QWORD *)this + 25);
      v17 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 6) + 48LL))((char *)this + 48);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        v6,
        (unsigned int)&unk_14007FDF8,
        v7,
        v8,
        (__int64)&v17,
        (__int64)&v16,
        (__int64)&ModeName);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_DestroyPrivateObjectSecurity_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&SecurityDescriptor);
  }
  return 0;
}

```

## disassembly

```asm
0x14002cef0  push    rbp
0x14002cef2  push    rbx
0x14002cef3  push    rdi
0x14002cef4  mov     rbp, rsp
0x14002cef7  sub     rsp, 60h
0x14002cefb  cmp     dword ptr [rcx+40h], 1
0x14002ceff  mov     rdi, rcx
0x14002cf02  jnz     loc_14002D049
0x14002cf08  lea     rdx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14002cf0c  mov     [rbp+SecurityDescriptor], 0
0x14002cf14  call    ?InitializePipeSecurityDescriptor@NamedPipeAdaptor@@AEAAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?DestroyPrivateObjectSecurity@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z
0x14002cf19  mov     ebx, eax
0x14002cf1b  test    eax, eax
0x14002cf1d  jns     short loc_14002CF3C
0x14002cf1f  mov     rcx, [rbp+18h]; this
0x14002cf23  lea     r8, aClientcoreTerm_0; "clientcore\\termsrv\\rdpplatform\\commo"...
0x14002cf2a  mov     r9d, eax; char *
0x14002cf2d  mov     edx, 130h; void *
0x14002cf32  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002cf37  jmp     loc_14002CFDA
0x14002cf3c  mov     rax, [rbp+SecurityDescriptor]
0x14002cf40  lea     rcx, [rbp+SecurityAttributes]
0x14002cf44  mov     [rsp+60h+lpSecurityAttributes], rcx; lpSecurityAttributes
0x14002cf49  mov     edx, 40000003h; dwOpenMode
0x14002cf4e  mov     rcx, [rdi+68h]; lpName
0x14002cf52  mov     r9d, 0FFh; nMaxInstances
0x14002cf58  mov     [rbp+SecurityAttributes.lpSecurityDescriptor], rax
0x14002cf5c  mov     r8d, 6; dwPipeMode
0x14002cf62  mov     eax, [rdi+8Ch]
0x14002cf68  mov     [rsp+60h+nDefaultTimeOut], 0; nDefaultTimeOut
0x14002cf70  mov     [rsp+60h+nInBufferSize], eax; nInBufferSize
0x14002cf74  mov     [rsp+60h+nOutBufferSize], eax; char *
0x14002cf78  mov     qword ptr [rbp+SecurityAttributes.nLength], 18h
0x14002cf80  mov     qword ptr [rbp+SecurityAttributes.bInheritHandle], 0
0x14002cf88  call    cs:__imp_CreateNamedPipeW
0x14002cf8e  lea     rbx, [rdi+0C8h]
0x14002cf95  mov     [rbp+arg_8], rax
0x14002cf99  mov     rcx, rbx
0x14002cf9c  lea     rdx, [rbp+arg_8]
0x14002cfa0  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x14002cfa5  lea     rcx, [rbp+arg_8]
0x14002cfa9  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14002cfae  mov     rax, [rbx]
0x14002cfb1  inc     rax
0x14002cfb4  test    rax, 0FFFFFFFFFFFFFFFEh
0x14002cfba  jnz     short loc_14002CFE7
0x14002cfbc  mov     rcx, [rbp+18h]; this
0x14002cfc0  lea     r9, aCreatenamedpip_0; "CreateNamedPipe failed"
0x14002cfc7  lea     r8, aClientcoreTerm_0; "clientcore\\termsrv\\rdpplatform\\commo"...
0x14002cfce  mov     edx, 141h; void *
0x14002cfd3  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x14002cfd8  mov     ebx, eax
0x14002cfda  lea     rcx, [rbp+SecurityDescriptor]
0x14002cfde  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?DestroyPrivateObjectSecurity@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14002cfe3  mov     eax, ebx
0x14002cfe5  jmp     short loc_14002D04B
0x14002cfe7  mov     eax, cs:dword_140088090
0x14002cfed  cmp     eax, 5
0x14002cff0  jbe     short loc_14002D040
0x14002cff2  mov     rcx, rdi; this
0x14002cff5  call    ?GetModeName@NamedPipeAdaptor@@AEBAPEBGXZ; NamedPipeAdaptor::GetModeName(void)
0x14002cffa  mov     [rbp+arg_8], rax
0x14002cffe  lea     rcx, [rdi+30h]
0x14002d002  mov     rax, [rbx]
0x14002d005  mov     [rbp+arg_10], rax
0x14002d009  mov     rax, [rcx]
0x14002d00c  mov     rax, [rax+30h]
0x14002d010  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002d015  mov     [rbp+arg_18], rax
0x14002d019  lea     rdx, unk_14007FDF8
0x14002d020  lea     rax, [rbp+arg_8]
0x14002d024  mov     qword ptr [rsp+60h+nDefaultTimeOut], rax
0x14002d029  lea     rax, [rbp+arg_10]
0x14002d02d  mov     qword ptr [rsp+60h+nInBufferSize], rax
0x14002d032  lea     rax, [rbp+arg_18]
0x14002d036  mov     qword ptr [rsp+60h+nOutBufferSize], rax
0x14002d03b  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x14002d040  lea     rcx, [rbp+SecurityDescriptor]
0x14002d044  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?DestroyPrivateObjectSecurity@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14002d049  xor     eax, eax
0x14002d04b  add     rsp, 60h
0x14002d04f  pop     rdi
0x14002d050  pop     rbx
0x14002d051  pop     rbp
0x14002d052  retn
```
