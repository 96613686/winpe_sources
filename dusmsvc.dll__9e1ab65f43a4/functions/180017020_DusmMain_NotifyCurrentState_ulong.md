# DusmMain::NotifyCurrentState(ulong)

- ea: `0x180017020`
- end: `0x180017074`
- name: `?NotifyCurrentState@DusmMain@@AEAAXK@Z`
- size: `84`
- prototype: `void __fastcall(DusmMain *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180016f44`
- `0x18001716c`
- `0x180017204`

## callees

- `0x180001234`
- `0x180013444`
- `0x180017020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001703c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001703c`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180017032`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180017032`

## pseudocode

```c
void __fastcall DusmMain::NotifyCurrentState(SERVICE_STATUS_HANDLE *this, DWORD a2)
{
  struct _SERVICE_STATUS *v3; // rdx
  SERVICE_STATUS_HANDLE v4; // rcx
  DWORD LastError; // ebx
  __int64 v6; // rdx
  __int64 v7; // rcx
  _DWORD *v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  DWORD v11; // [rsp+48h] [rbp+10h] BYREF

  v3 = (struct _SERVICE_STATUS *)(this + 1);
  v4 = *this;
  v3->dwCurrentState = a2;
  if ( !SetServiceStatus(v4, v3) )
  {
    LastError = GetLastError();
    v8 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v7, v6) + 8);
    if ( *v8 > 5u )
    {
      v11 = LastError;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (int)v8,
        (int)byte_180055E89,
        v9,
        v10,
        (__int64)&v11);
    }
  }
}

```

## disassembly

```asm
0x180017020  push    rbx
0x180017022  sub     rsp, 30h
0x180017026  mov     eax, edx
0x180017028  lea     rdx, [rcx+8]; lpServiceStatus
0x18001702c  mov     rcx, [rcx]; hServiceStatus
0x18001702f  mov     [rdx+4], eax
0x180017032  call    cs:__imp_SetServiceStatus
0x180017038  test    eax, eax
0x18001703a  jnz     short loc_18001706E
0x18001703c  call    cs:__imp_GetLastError
0x180017042  mov     ebx, eax
0x180017044  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x180017049  mov     rcx, [rax+8]
0x18001704d  mov     edx, [rcx]
0x18001704f  cmp     edx, 5
0x180017052  jbe     short loc_18001706E
0x180017054  lea     rax, [rsp+38h+arg_8]
0x180017059  mov     [rsp+38h+arg_8], ebx
0x18001705d  lea     rdx, byte_180055E89
0x180017064  mov     [rsp+38h+var_18], rax
0x180017069  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001706e  add     rsp, 30h
0x180017072  pop     rbx
0x180017073  retn
```
