# ServiceHandler::Init(ushort const *)

- ea: `0x1800d7ba4`
- end: `0x1800d7d69`
- name: `?Init@ServiceHandler@@AEAAJPEBG@Z`
- size: `453`
- prototype: `__int64 __fastcall(ServiceHandler *__hidden this, LPCWSTR lpServiceName)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800d8118`

## callees

- `0x1800017c8`
- `0x180009174`
- `0x18000e46c`
- `0x18006ba8c`
- `0x180071a34`
- `0x1800726f0`
- `0x1800d7ba4`
- `0x1800d8570`
- `0x180101010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x1800d7bcd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x1800d7bcd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800d7c7f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800d7c9b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800d7cb7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800d7c7f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800d7c9b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800d7cb7`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800d7c57`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800d7c57`

## string_xrefs

- `0x1800d7d1e`: `LpaServiceHost`
- `0x1800d7d0f`: `ServiceHandler::Init`

## pseudocode

```c
__int64 __fastcall ServiceHandler::Init(ServiceHandler *this, LPCWSTR lpServiceName)
{
  int LastErrorToHResultAndForceFailure; // edi
  int v5; // eax
  LPA::CoreLpa *v6; // rax
  CommonUtil *v7; // rcx
  __int64 v8; // rcx
  SERVICE_STATUS_HANDLE v9; // rax
  CommonUtil *v10; // rcx
  int v11; // r8d
  int v12; // r9d
  HANDLE EventW; // rax
  HANDLE v14; // rax
  HANDLE v15; // rax
  CommonUtil *v16; // rcx
  _QWORD *v17; // rax
  ServiceHandler *v19; // [rsp+70h] [rbp+8h] BYREF
  LPCWSTR v20; // [rsp+78h] [rbp+10h]
  const char *v21; // [rsp+80h] [rbp+18h] BYREF
  const char *v22; // [rsp+88h] [rbp+20h] BYREF

  v20 = lpServiceName;
  v19 = this;
  LastErrorToHResultAndForceFailure = 0;
  *((_OWORD *)this + 1) = 0;
  *(_OWORD *)((char *)this + 28) = 0;
  *(_QWORD *)this = _o__wcsdup(lpServiceName);
  ServiceHandler::s_lLoggingRegistered = TraceLoggingRegisterEx_EventRegister_EventSetInformation(&CallbackContext);
  v5 = TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_18015A5E0);
  try
  {
    ServiceHandler::s_lTelLoggingRegistered = v5;
    v6 = (LPA::CoreLpa *)operator new(0xD8u);
    *((_QWORD *)this + 11) = LPA::CoreLpa::CoreLpa(v6);
  }
  catch ( ... )
  {
    CommonUtil::ExceptionToHResult(v7);
  }
  v8 = *((_QWORD *)this + 11);
  if ( v8 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
    v9 = RegisterServiceCtrlHandlerExW(lpServiceName, ServiceHandler::ServiceControlHandler, this);
    *((_QWORD *)this + 1) = v9;
    if ( v9
      || (LastErrorToHResultAndForceFailure = CommonUtil::GetLastErrorToHResultAndForceFailure(v10),
          LastErrorToHResultAndForceFailure >= 0) )
    {
      EventW = CreateEventW(0, 0, 0, 0);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        (char *)this + 56,
        EventW);
      v14 = CreateEventW(0, 0, 0, 0);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        (char *)this + 64,
        v14);
      v15 = CreateEventW(0, 0, 0, 0);
      wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::reset(
        (char *)this + 72,
        v15);
      if ( (unsigned __int64)(*((_QWORD *)this + 7) - 1LL) > 0xFFFFFFFFFFFFFFFDuLL
        || (unsigned __int64)(*((_QWORD *)this + 8) - 1LL) > 0xFFFFFFFFFFFFFFFDuLL
        || (v17 = (_QWORD *)*((_QWORD *)this + 9)) == 0
        || ((*v17 + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      {
        LastErrorToHResultAndForceFailure = CommonUtil::GetLastErrorToHResultAndForceFailure(v16);
      }
    }
  }
  else
  {
    LastErrorToHResultAndForceFailure = -2147024888;
  }
  if ( (_DWORD)CallbackContext )
  {
    LODWORD(v19) = LastErrorToHResultAndForceFailure;
    v21 = "ServiceHandler::Init";
    v22 = "LpaServiceHost";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (_DWORD)CallbackContext,
      (unsigned int)byte_180134A03,
      v11,
      v12,
      (__int64)&v22,
      (__int64)&v21,
      (__int64)&v19);
  }
  return (unsigned int)LastErrorToHResultAndForceFailure;
}

```

## disassembly

```asm
0x1800d7ba4  mov     [rsp+arg_8], rdx
0x1800d7ba9  mov     [rsp+arg_0], rcx
0x1800d7bae  push    rbx
0x1800d7baf  push    rsi
0x1800d7bb0  push    rdi
0x1800d7bb1  push    r14
0x1800d7bb3  sub     rsp, 48h
0x1800d7bb7  mov     rbx, rdx
0x1800d7bba  mov     rsi, rcx
0x1800d7bbd  xor     edi, edi
0x1800d7bbf  xorps   xmm0, xmm0
0x1800d7bc2  movups  xmmword ptr [rcx+10h], xmm0
0x1800d7bc6  movups  xmmword ptr [rcx+1Ch], xmm0
0x1800d7bca  mov     rcx, rdx
0x1800d7bcd  call    cs:__imp__o__wcsdup
0x1800d7bd3  mov     [rsi], rax
0x1800d7bd6  lea     rcx, CallbackContext; CallbackContext
0x1800d7bdd  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x1800d7be2  mov     cs:?s_lLoggingRegistered@ServiceHandler@@0JA, eax; long ServiceHandler::s_lLoggingRegistered
0x1800d7be8  lea     rcx, dword_18015A5E0; CallbackContext
0x1800d7bef  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x1800d7bf4  mov     cs:?s_lTelLoggingRegistered@ServiceHandler@@0JA, eax; long ServiceHandler::s_lTelLoggingRegistered
0x1800d7bfa  mov     ecx, 0D8h; Size
0x1800d7bff  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d7c04  mov     rcx, rax; this
0x1800d7c07  call    ??0CoreLpa@LPA@@QEAA@XZ; LPA::CoreLpa::CoreLpa(void)
0x1800d7c0c  mov     [rsi+58h], rax
0x1800d7c10  jmp     short loc_1800D7C23
0x1800d7c12  mov     rsi, [rsp+68h+arg_0]
0x1800d7c17  mov     rbx, [rsp+68h+arg_8]
0x1800d7c1c  mov     edi, dword ptr [rsp+68h+arg_10]
0x1800d7c23  mov     rcx, [rsi+58h]
0x1800d7c27  test    rcx, rcx
0x1800d7c2a  jnz     short loc_1800D7C36
0x1800d7c2c  mov     edi, 80070008h
0x1800d7c31  jmp     loc_1800D7D01
0x1800d7c36  mov     rax, [rcx]
0x1800d7c39  mov     rax, [rax+8]
0x1800d7c3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7c42  test    edi, edi
0x1800d7c44  js      loc_1800D7D01
0x1800d7c4a  mov     r8, rsi; lpContext
0x1800d7c4d  lea     rdx, ?ServiceControlHandler@ServiceHandler@@CAKKKPEAX0@Z; lpHandlerProc
0x1800d7c54  mov     rcx, rbx; lpServiceName
0x1800d7c57  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x1800d7c5d  mov     [rsi+8], rax
0x1800d7c61  test    rax, rax
0x1800d7c64  jnz     short loc_1800D7C75
0x1800d7c66  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x1800d7c6b  mov     edi, eax
0x1800d7c6d  test    eax, eax
0x1800d7c6f  js      loc_1800D7D01
0x1800d7c75  xor     r9d, r9d; lpName
0x1800d7c78  xor     r8d, r8d; bInitialState
0x1800d7c7b  xor     edx, edx; bManualReset
0x1800d7c7d  xor     ecx, ecx; lpEventAttributes
0x1800d7c7f  call    cs:__imp_CreateEventW
0x1800d7c85  mov     rdx, rax
0x1800d7c88  lea     rcx, [rsi+38h]
0x1800d7c8c  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800d7c91  xor     r9d, r9d; lpName
0x1800d7c94  xor     r8d, r8d; bInitialState
0x1800d7c97  xor     edx, edx; bManualReset
0x1800d7c99  xor     ecx, ecx; lpEventAttributes
0x1800d7c9b  call    cs:__imp_CreateEventW
0x1800d7ca1  mov     rdx, rax
0x1800d7ca4  lea     rcx, [rsi+40h]
0x1800d7ca8  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800d7cad  xor     r9d, r9d; lpName
0x1800d7cb0  xor     r8d, r8d; bInitialState
0x1800d7cb3  xor     edx, edx; bManualReset
0x1800d7cb5  xor     ecx, ecx; lpEventAttributes
0x1800d7cb7  call    cs:__imp_CreateEventW
0x1800d7cbd  mov     rdx, rax
0x1800d7cc0  lea     rcx, [rsi+48h]
0x1800d7cc4  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::reset(void *)
0x1800d7cc9  mov     rax, [rsi+38h]
0x1800d7ccd  dec     rax
0x1800d7cd0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800d7cd4  ja      short loc_1800D7CFA
0x1800d7cd6  mov     rax, [rsi+40h]
0x1800d7cda  dec     rax
0x1800d7cdd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800d7ce1  ja      short loc_1800D7CFA
0x1800d7ce3  mov     rax, [rsi+48h]
0x1800d7ce7  test    rax, rax
0x1800d7cea  jz      short loc_1800D7CFA
0x1800d7cec  mov     rax, [rax]
0x1800d7cef  inc     rax
0x1800d7cf2  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800d7cf8  jnz     short loc_1800D7D01
0x1800d7cfa  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x1800d7cff  mov     edi, eax
0x1800d7d01  mov     ecx, cs:CallbackContext
0x1800d7d07  test    ecx, ecx
0x1800d7d09  jz      short loc_1800D7D5D
0x1800d7d0b  mov     dword ptr [rsp+68h+arg_0], edi
0x1800d7d0f  lea     rax, aServicehandler_1; "ServiceHandler::Init"
0x1800d7d16  mov     [rsp+68h+arg_10], rax
0x1800d7d1e  lea     rax, aLpaservicehost; "LpaServiceHost"
0x1800d7d25  mov     [rsp+68h+arg_18], rax
0x1800d7d2d  lea     rax, [rsp+68h+arg_0]
0x1800d7d32  mov     [rsp+68h+var_38], rax
0x1800d7d37  lea     rax, [rsp+68h+arg_10]
0x1800d7d3f  mov     [rsp+68h+var_40], rax
0x1800d7d44  lea     rax, [rsp+68h+arg_18]
0x1800d7d4c  mov     [rsp+68h+var_48], rax
0x1800d7d51  lea     rdx, byte_180134A03
0x1800d7d58  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800d7d5d  mov     eax, edi
0x1800d7d5f  add     rsp, 48h
0x1800d7d63  pop     r14
0x1800d7d65  pop     rdi
0x1800d7d66  pop     rsi
0x1800d7d67  pop     rbx
0x1800d7d68  retn
```
