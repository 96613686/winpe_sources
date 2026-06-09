# NamedPipeAdaptor::OpenPipeInternal(void)

- ea: `0x14002d534`
- end: `0x14002d766`
- name: `?OpenPipeInternal@NamedPipeAdaptor@@AEAAJXZ`
- size: `562`
- prototype: `__int64 __fastcall(NamedPipeAdaptor *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x14002d770`

## callees

- `0x1400022fc`
- `0x140006210`
- `0x140008168`
- `0x140008188`
- `0x14002c030`
- `0x14002c270`
- `0x14002cc10`
- `0x14002d534`
- `0x14002dc6c`
- `0x14002dca4`
- `0x14002df68`
- `0x14002e5ec`
- `0x14006b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d59b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d59b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14002d64b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14002d64b`
- `api-ms-win-core-namedpipe-l1-1-0!SetNamedPipeHandleState` at `0x14002d6b2`
- `api-ms-win-core-namedpipe-l1-1-0!SetNamedPipeHandleState` at `0x14002d6b2`
- `api-ms-win-core-namedpipe-l1-1-0!ConnectNamedPipe` at `0x14002d591`
- `api-ms-win-core-namedpipe-l1-1-0!ConnectNamedPipe` at `0x14002d591`

## string_xrefs

- `0x14002d5ba`: `clientcore\termsrv\rdpplatform\common\namedpipe\namedpipeadaptor.cpp`
- `0x14002d5ee`: `clientcore\termsrv\rdpplatform\common\namedpipe\namedpipeadaptor.cpp`
- `0x14002d68b`: `clientcore\termsrv\rdpplatform\common\namedpipe\namedpipeadaptor.cpp`
- `0x14002d6c0`: `clientcore\termsrv\rdpplatform\common\namedpipe\namedpipeadaptor.cpp`
- `0x14002d74b`: `clientcore\termsrv\rdpplatform\common\namedpipe\namedpipeadaptor.cpp`
- `0x14002d684`: `CreateFileW failed`

## pseudocode

```c
__int64 __fastcall NamedPipeAdaptor::OpenPipeInternal(NamedPipeAdaptor *this)
{
  int v2; // eax
  unsigned int LastErrorMsg; // ebx
  __int64 v4; // rdx
  void *v5; // rcx
  DWORD LastError; // eax
  void *v7; // rcx
  const char *v9; // r9
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  const char *dwCreationDisposition; // [rsp+20h] [rbp-40h]
  const char *dwCreationDispositiona; // [rsp+20h] [rbp-40h]
  const char *dwFlagsAndAttributes; // [rsp+28h] [rbp-38h]
  struct _OVERLAPPED Overlapped; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  void *Mode; // [rsp+80h] [rbp+20h] BYREF
  const unsigned __int16 *FileW; // [rsp+88h] [rbp+28h] BYREF
  __int64 v20; // [rsp+90h] [rbp+30h] BYREF
  __int64 v21; // [rsp+98h] [rbp+38h] BYREF

  if ( *((_DWORD *)this + 16) != 1 )
  {
    if ( *((_DWORD *)this + 16) )
    {
      LastErrorMsg = -2147024809;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x176,
        (unsigned int)"clientcore\\termsrv\\rdpplatform\\common\\namedpipe\\namedpipeadaptor.cpp",
        (const char *)0x80070057LL,
        (int)"Named pipe mode is invalid",
        dwFlagsAndAttributes);
      return LastErrorMsg;
    }
    FileW = (const unsigned __int16 *)CreateFileW(*((LPCWSTR *)this + 13), 0xC0000000, 0, 0, 3u, 0x40000000u, 0);
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      (char *)this + 200,
      &FileW);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&FileW);
    v7 = (void *)*((_QWORD *)this + 25);
    if ( (((unsigned __int64)v7 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      return wil::details::in1diag3::Return_GetLastErrorMsg(
               retaddr,
               (void *)0x16B,
               (unsigned int)"clientcore\\termsrv\\rdpplatform\\common\\namedpipe\\namedpipeadaptor.cpp",
               "CreateFileW failed",
               dwCreationDispositiona);
    LODWORD(Mode) = 2;
    if ( !SetNamedPipeHandleState(v7, (LPDWORD)&Mode, 0, 0) )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x16F,
               (unsigned int)"clientcore\\termsrv\\rdpplatform\\common\\namedpipe\\namedpipeadaptor.cpp",
               v9);
    if ( (unsigned int)dword_140088090 > 5 )
    {
      FileW = NamedPipeAdaptor::GetModeName(this);
      v20 = *((_QWORD *)this + 25);
      v21 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 6) + 48LL))((char *)this + 48);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        v10,
        (unsigned int)&unk_14007FDB8,
        v11,
        v12,
        (__int64)&v21,
        (__int64)&v20,
        (__int64)&FileW);
    }
    return 0;
  }
  Mode = 0;
  v2 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
         &Mode,
         1);
  LastErrorMsg = v2;
  if ( v2 < 0 )
  {
    v4 = 336;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"clientcore\\termsrv\\rdpplatform\\common\\namedpipe\\namedpipeadaptor.cpp",
      (const char *)(unsigned int)v2,
      (int)dwCreationDisposition);
    goto LABEL_11;
  }
  v5 = (void *)*((_QWORD *)this + 25);
  Overlapped.hEvent = Mode;
  memset(&Overlapped, 0, 24);
  if ( ConnectNamedPipe(v5, &Overlapped) || (LastError = GetLastError(), LastError == 535) )
  {
LABEL_12:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&Mode);
    return 0;
  }
  if ( LastError == 997 )
  {
    v2 = NamedPipeAdaptor::WaitForEvent(this, &Mode, 0xFFFFFFFFLL);
    LastErrorMsg = v2;
    if ( v2 < 0 )
    {
      v4 = 348;
      goto LABEL_10;
    }
    goto LABEL_12;
  }
  LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                   retaddr,
                   (void *)0x158,
                   (unsigned int)"clientcore\\termsrv\\rdpplatform\\common\\namedpipe\\namedpipeadaptor.cpp",
                   "ConnectNamedPipe failed",
                   dwCreationDisposition);
LABEL_11:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&Mode);
  return LastErrorMsg;
}

```

## disassembly

```asm
0x14002d534  push    rbp
0x14002d536  push    rbx
0x14002d537  push    rdi
0x14002d538  mov     rbp, rsp
0x14002d53b  sub     rsp, 60h
0x14002d53f  mov     edx, 1
0x14002d544  mov     rdi, rcx
0x14002d547  cmp     [rcx+40h], edx
0x14002d54a  jnz     loc_14002D619
0x14002d550  lea     rcx, [rbp+Mode]
0x14002d554  mov     [rbp+Mode], 0
0x14002d55c  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x14002d561  mov     ebx, eax
0x14002d563  test    eax, eax
0x14002d565  jns     short loc_14002D56E
0x14002d567  mov     edx, 150h
0x14002d56c  jmp     short loc_14002D5EA
0x14002d56e  mov     rax, [rbp+Mode]
0x14002d572  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x14002d576  mov     rcx, [rdi+0C8h]; hNamedPipe
0x14002d57d  xorps   xmm0, xmm0
0x14002d580  movdqu  xmmword ptr [rbp+Overlapped.InternalHigh], xmm0
0x14002d585  mov     [rbp+Overlapped.hEvent], rax
0x14002d589  mov     [rbp+Overlapped.Internal], 0
0x14002d591  call    cs:__imp_ConnectNamedPipe
0x14002d597  test    eax, eax
0x14002d599  jnz     short loc_14002D60B
0x14002d59b  call    cs:__imp_GetLastError
0x14002d5a1  cmp     eax, 217h
0x14002d5a6  jz      short loc_14002D60B
0x14002d5a8  cmp     eax, 3E5h
0x14002d5ad  jz      short loc_14002D5CF
0x14002d5af  mov     rcx, [rbp+18h]; this
0x14002d5b3  lea     r9, aConnectnamedpi; "ConnectNamedPipe failed"
0x14002d5ba  lea     r8, aClientcoreTerm_0; "clientcore\\termsrv\\rdpplatform\\commo"...
0x14002d5c1  mov     edx, 158h; void *
0x14002d5c6  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x14002d5cb  mov     ebx, eax
0x14002d5cd  jmp     short loc_14002D5FD
0x14002d5cf  or      r8d, 0FFFFFFFFh
0x14002d5d3  lea     rdx, [rbp+Mode]
0x14002d5d7  mov     rcx, rdi
0x14002d5da  call    ?WaitForEvent@NamedPipeAdaptor@@AEAAJAEBV?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@K@Z
0x14002d5df  mov     ebx, eax
0x14002d5e1  test    eax, eax
0x14002d5e3  jns     short loc_14002D60B
0x14002d5e5  mov     edx, 15Ch; void *
0x14002d5ea  mov     rcx, [rbp+18h]; this
0x14002d5ee  lea     r8, aClientcoreTerm_0; "clientcore\\termsrv\\rdpplatform\\commo"...
0x14002d5f5  mov     r9d, eax; char *
0x14002d5f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002d5fd  lea     rcx, [rbp+Mode]
0x14002d601  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14002d606  jmp     loc_14002D75C
0x14002d60b  lea     rcx, [rbp+Mode]
0x14002d60f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14002d614  jmp     loc_14002D72F
0x14002d619  cmp     dword ptr [rcx+40h], 0
0x14002d61d  jnz     loc_14002D733
0x14002d623  mov     rcx, [rcx+68h]; lpFileName
0x14002d627  xor     r9d, r9d; lpSecurityAttributes
0x14002d62a  mov     [rsp+60h+hTemplateFile], 0; hTemplateFile
0x14002d633  xor     r8d, r8d; dwShareMode
0x14002d636  mov     [rsp+60h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x14002d63e  mov     edx, 0C0000000h; dwDesiredAccess
0x14002d643  mov     [rsp+60h+dwCreationDisposition], 3; char *
0x14002d64b  call    cs:__imp_CreateFileW
0x14002d651  lea     rbx, [rdi+0C8h]
0x14002d658  mov     [rbp+arg_8], rax
0x14002d65c  mov     rcx, rbx
0x14002d65f  lea     rdx, [rbp+arg_8]
0x14002d663  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x14002d668  lea     rcx, [rbp+arg_8]
0x14002d66c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14002d671  mov     rcx, [rbx]; hNamedPipe
0x14002d674  lea     rax, [rcx+1]
0x14002d678  test    rax, 0FFFFFFFFFFFFFFFEh
0x14002d67e  jnz     short loc_14002D6A1
0x14002d680  mov     rcx, [rbp+18h]; this
0x14002d684  lea     r9, aCreatefilewFai; "CreateFileW failed"
0x14002d68b  lea     r8, aClientcoreTerm_0; "clientcore\\termsrv\\rdpplatform\\commo"...
0x14002d692  mov     edx, 16Bh; void *
0x14002d697  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x14002d69c  jmp     loc_14002D75E
0x14002d6a1  xor     r9d, r9d; lpCollectDataTimeout
0x14002d6a4  mov     dword ptr [rbp+Mode], 2
0x14002d6ab  xor     r8d, r8d; lpMaxCollectionCount
0x14002d6ae  lea     rdx, [rbp+Mode]; lpMode
0x14002d6b2  call    cs:__imp_SetNamedPipeHandleState
0x14002d6b8  test    eax, eax
0x14002d6ba  jnz     short loc_14002D6D6
0x14002d6bc  mov     rcx, [rbp+18h]; this
0x14002d6c0  lea     r8, aClientcoreTerm_0; "clientcore\\termsrv\\rdpplatform\\commo"...
0x14002d6c7  mov     edx, 16Fh; void *
0x14002d6cc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14002d6d1  jmp     loc_14002D75E
0x14002d6d6  mov     eax, cs:dword_140088090
0x14002d6dc  cmp     eax, 5
0x14002d6df  jbe     short loc_14002D72F
0x14002d6e1  mov     rcx, rdi; this
0x14002d6e4  call    ?GetModeName@NamedPipeAdaptor@@AEBAPEBGXZ; NamedPipeAdaptor::GetModeName(void)
0x14002d6e9  mov     [rbp+arg_8], rax
0x14002d6ed  lea     rcx, [rdi+30h]
0x14002d6f1  mov     rax, [rbx]
0x14002d6f4  mov     [rbp+arg_10], rax
0x14002d6f8  mov     rax, [rcx]
0x14002d6fb  mov     rax, [rax+30h]
0x14002d6ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002d704  mov     [rbp+arg_18], rax
0x14002d708  lea     rdx, unk_14007FDB8
0x14002d70f  lea     rax, [rbp+arg_8]
0x14002d713  mov     [rsp+60h+hTemplateFile], rax
0x14002d718  lea     rax, [rbp+arg_10]
0x14002d71c  mov     qword ptr [rsp+60h+dwFlagsAndAttributes], rax
0x14002d721  lea     rax, [rbp+arg_18]
0x14002d725  mov     qword ptr [rsp+60h+dwCreationDisposition], rax
0x14002d72a  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x14002d72f  xor     eax, eax
0x14002d731  jmp     short loc_14002D75E
0x14002d733  mov     rcx, [rbp+18h]; this
0x14002d737  lea     rax, aNamedPipeModeI; "Named pipe mode is invalid"
0x14002d73e  mov     ebx, 80070057h
0x14002d743  mov     qword ptr [rsp+60h+dwCreationDisposition], rax; int
0x14002d748  mov     r9d, ebx; char *
0x14002d74b  lea     r8, aClientcoreTerm_0; "clientcore\\termsrv\\rdpplatform\\commo"...
0x14002d752  mov     edx, 176h; void *
0x14002d757  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x14002d75c  mov     eax, ebx
0x14002d75e  add     rsp, 60h
0x14002d762  pop     rdi
0x14002d763  pop     rbx
0x14002d764  pop     rbp
0x14002d765  retn
```
