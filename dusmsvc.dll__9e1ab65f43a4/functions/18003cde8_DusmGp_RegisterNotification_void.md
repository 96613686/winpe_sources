# DusmGp::RegisterNotification(void)

- ea: `0x18003cde8`
- end: `0x18003cef5`
- name: `?RegisterNotification@DusmGp@@AEAAXXZ`
- size: `269`
- prototype: `void __fastcall(DusmGp *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18003cc84`

## callees

- `0x180001234`
- `0x1800122a4`
- `0x180013444`
- `0x18001374c`
- `0x1800171a8`
- `0x18003cde8`
- `0x18003cf68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003ce08`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003ce08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cea2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cea2`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18003ce5f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18003ce5f`
- `USERENV!RegisterGPNotification` at `0x18003ce98`
- `USERENV!RegisterGPNotification` at `0x18003ce98`

## string_xrefs

- `0x18003ce22`: `DusmGp::RegisterNotification::CreateEventW`

## pseudocode

```c
void __fastcall DusmGp::RegisterNotification(DusmGp *this)
{
  HANDLE *v1; // rbx
  HANDLE EventW; // rax
  __int64 LastErrorIfNull; // rax
  BOOL v4; // eax
  DWORD LastError; // edi
  _DWORD *v6; // r8
  int v7; // r9d
  const char *dwFlags; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  DusmGp *v10; // [rsp+40h] [rbp+8h] BYREF

  v10 = this;
  v1 = (HANDLE *)DusmGp::s_pInstance;
  EventW = CreateEventW(0, 0, 0, 0);
  LastErrorIfNull = wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<void *,0>(
                      retaddr,
                      130,
                      "onecoreuap\\net\\dusm\\lib\\dusmgp.cpp",
                      EventW,
                      "DusmGp::RegisterNotification::CreateEventW");
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    v1,
    LastErrorIfNull);
  v4 = RegisterWaitForSingleObject(v1 + 1, *v1, DusmGp::GpCallback, v1, 0xFFFFFFFF, 0);
  wil::details::in1diag3::Throw_GetLastErrorIfFalseMsg(
    retaddr,
    (void *)0x86,
    (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmgp.cpp",
    (const char *)v4,
    (bool)"DusmGp::RegisterNotification::RegisterWaitForSingleObject",
    dwFlags);
  if ( !RegisterGPNotification(*v1, 1) )
  {
    LastError = GetLastError();
    v6 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get() + 8);
    if ( *v6 > 5u )
    {
      LODWORD(v10) = LastError;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (_DWORD)v6,
        (unsigned int)byte_18005B773,
        (_DWORD)v6,
        v7,
        (__int64)&v10);
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      v1,
      0);
    DusmGp::UnregisterNotification((DusmGp *)v1);
  }
}

```

## disassembly

```asm
0x18003cde8  mov     [rsp+arg_8], rbx
0x18003cded  mov     [rsp+arg_0], rcx
0x18003cdf2  push    rdi
0x18003cdf3  sub     rsp, 30h
0x18003cdf7  mov     rbx, cs:?s_pInstance@DusmGp@@0PEAV1@EA; DusmGp * DusmGp::s_pInstance
0x18003cdfe  xor     r9d, r9d; lpName
0x18003ce01  xor     r8d, r8d; bInitialState
0x18003ce04  xor     edx, edx; bManualReset
0x18003ce06  xor     ecx, ecx; lpEventAttributes
0x18003ce08  call    cs:__imp_CreateEventW
0x18003ce0e  mov     rcx, [rsp+38h]
0x18003ce13  lea     r8, aOnecoreuapNetD_13; "onecoreuap\\net\\dusm\\lib\\dusmgp.cpp"
0x18003ce1a  mov     r9, rax
0x18003ce1d  mov     edx, 82h
0x18003ce22  lea     rax, aDusmgpRegister_0; "DusmGp::RegisterNotification::CreateEve"...
0x18003ce29  mov     qword ptr [rsp+38h+dwMilliseconds], rax
0x18003ce2e  call    ??$Throw_GetLastErrorIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBD01ZZ; wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<void *,0>(void *,uint,char const *,void *,char const *,...)
0x18003ce33  mov     rdx, rax
0x18003ce36  mov     rcx, rbx
0x18003ce39  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18003ce3e  mov     rdx, [rbx]; hObject
0x18003ce41  lea     rcx, [rbx+8]; phNewWaitObject
0x18003ce45  mov     r9, rbx; Context
0x18003ce48  mov     [rsp+38h+dwFlags], 0; char *
0x18003ce50  lea     r8, ?GpCallback@DusmGp@@CAXPEAXE@Z; Callback
0x18003ce57  mov     [rsp+38h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x18003ce5f  call    cs:__imp_RegisterWaitForSingleObject
0x18003ce65  mov     rcx, [rsp+38h]; this
0x18003ce6a  lea     rdx, aDusmgpRegister; "DusmGp::RegisterNotification::RegisterW"...
0x18003ce71  test    eax, eax
0x18003ce73  mov     qword ptr [rsp+38h+dwMilliseconds], rdx; bool
0x18003ce78  lea     r8, aOnecoreuapNetD_13; "onecoreuap\\net\\dusm\\lib\\dusmgp.cpp"
0x18003ce7f  mov     edx, 86h; void *
0x18003ce84  setnz   al
0x18003ce87  movzx   r9d, al; char *
0x18003ce8b  call    ?Throw_GetLastErrorIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfFalseMsg(void *,uint,char const *,bool,char const *,...)
0x18003ce90  mov     rcx, [rbx]; hEvent
0x18003ce93  mov     edx, 1; bMachine
0x18003ce98  call    cs:__imp_RegisterGPNotification
0x18003ce9e  test    eax, eax
0x18003cea0  jnz     short loc_18003CEEA
0x18003cea2  call    cs:__imp_GetLastError
0x18003cea8  mov     edi, eax
0x18003ceaa  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18003ceaf  mov     r8, [rax+8]
0x18003ceb3  mov     ecx, [r8]
0x18003ceb6  cmp     ecx, 5
0x18003ceb9  jbe     short loc_18003CED8
0x18003cebb  lea     rax, [rsp+38h+arg_0]
0x18003cec0  mov     dword ptr [rsp+38h+arg_0], edi
0x18003cec4  lea     rdx, byte_18005B773
0x18003cecb  mov     qword ptr [rsp+38h+dwMilliseconds], rax
0x18003ced0  mov     rcx, r8
0x18003ced3  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18003ced8  xor     edx, edx
0x18003ceda  mov     rcx, rbx
0x18003cedd  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18003cee2  mov     rcx, rbx; this
0x18003cee5  call    ?UnregisterNotification@DusmGp@@AEAAXXZ; DusmGp::UnregisterNotification(void)
0x18003ceea  mov     rbx, [rsp+38h+arg_8]
0x18003ceef  add     rsp, 30h
0x18003cef3  pop     rdi
0x18003cef4  retn
```
