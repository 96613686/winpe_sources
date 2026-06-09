# CmLockSvcInitialize(void)

- ea: `0x18000f00c`
- end: `0x18000f0b1`
- name: `?CmLockSvcInitialize@@YAJXZ`
- size: `165`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180007b9c`

## callees

- `0x180001008`
- `0x180001284`
- `0x18000f00c`
- `0x18000f178`

## string_xrefs

- `0x18000f040`: `ConfigManagerMutex`
- `0x18000f039`: `Global\ConfigManagerMutex`

## pseudocode

```c
__int64 __fastcall CmLockSvcInitialize(const unsigned __int16 *a1)
{
  const unsigned __int16 *v1; // rcx
  int inited; // ebx
  __int64 v3; // r8
  __int64 v4; // r9
  int v6; // [rsp+40h] [rbp+8h] BYREF
  char *v7; // [rsp+48h] [rbp+10h] BYREF

  if ( _InterlockedIncrement(&g_cTraceLoggingRegister) == 1 )
    TraceLoggingRegister_EventRegister_EventSetInformation(&dword_18001B0E8);
  inited = InitNamedMutex(a1, L"ConfigManagerMutex", L"Global\\ConfigManagerMutex", &g_hConfigManagerMutex);
  if ( inited >= 0 )
    inited = InitNamedMutex(v1, L"PolicyManagerMutex", L"Global\\PolicyManagerMutex", &g_hPolicyManagerMutex);
  if ( (unsigned int)dword_18001B0E8 > 5 )
  {
    v6 = inited;
    v7 = "CmLockSvcInitialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (__int64)v1,
      (__int64)qword_180017580,
      v3,
      v4,
      (const unsigned __int16 **)&v7,
      (__int64)&v6);
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18000f00c  push    rbx
0x18000f00e  sub     rsp, 30h
0x18000f012  mov     eax, 1
0x18000f017  lock xadd cs:?g_cTraceLoggingRegister@@3JA, eax; long g_cTraceLoggingRegister
0x18000f01f  inc     eax
0x18000f021  cmp     eax, 1
0x18000f024  jnz     short loc_18000F032
0x18000f026  lea     rcx, dword_18001B0E8; CallbackContext
0x18000f02d  call    TraceLoggingRegister_EventRegister_EventSetInformation
0x18000f032  lea     r9, ?g_hConfigManagerMutex@@3PEAXEA; void **
0x18000f039  lea     r8, aGlobalConfigma; "Global\\ConfigManagerMutex"
0x18000f040  lea     rdx, aConfigmanagerm; "ConfigManagerMutex"
0x18000f047  call    ?InitNamedMutex@@YAJPEBG00PEAPEAX@Z; InitNamedMutex(ushort const *,ushort const *,ushort const *,void * *)
0x18000f04c  mov     ebx, eax
0x18000f04e  test    eax, eax
0x18000f050  js      short loc_18000F06E
0x18000f052  lea     r9, ?g_hPolicyManagerMutex@@3PEAXEA; void **
0x18000f059  lea     r8, aGlobalPolicyma; "Global\\PolicyManagerMutex"
0x18000f060  lea     rdx, aPolicymanagerm; "PolicyManagerMutex"
0x18000f067  call    ?InitNamedMutex@@YAJPEBG00PEAPEAX@Z; InitNamedMutex(ushort const *,ushort const *,ushort const *,void * *)
0x18000f06c  mov     ebx, eax
0x18000f06e  mov     eax, cs:dword_18001B0E8
0x18000f074  cmp     eax, 5
0x18000f077  jbe     short loc_18000F0A9
0x18000f079  lea     rax, ?s_lookupTable@?1???$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z@4QBDB+40h; "CmLockSvcInitialize"
0x18000f080  mov     [rsp+38h+arg_0], ebx
0x18000f084  mov     [rsp+38h+arg_8], rax
0x18000f089  lea     rdx, qword_180017580
0x18000f090  lea     rax, [rsp+38h+arg_0]
0x18000f095  mov     [rsp+38h+var_10], rax
0x18000f09a  lea     rax, [rsp+38h+arg_8]
0x18000f09f  mov     [rsp+38h+var_18], rax
0x18000f0a4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000f0a9  mov     eax, ebx
0x18000f0ab  add     rsp, 30h
0x18000f0af  pop     rbx
0x18000f0b0  retn
```
