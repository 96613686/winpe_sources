# DllMain

- ea: `0x180002ed0`
- end: `0x180002fa3`
- name: `DllMain`
- size: `211`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800020e4`

## callees

- `0x180001008`
- `0x180001098`
- `0x180002ed0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180002f44`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180002f93`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180002f44`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180002f93`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  __int64 v3; // rcx
  __int64 v4; // r8
  __int64 v5; // r9
  REGHANDLE v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  REGHANDLE v10; // rcx
  const char *v12; // [rsp+58h] [rbp+20h] BYREF

  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      TraceLoggingRegister_EventRegister_EventSetInformation(&dword_18001E048);
      if ( (unsigned int)dword_18001E048 > 5 )
      {
        v12 = "Reason";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v3,
          (__int64)byte_180018569,
          v4,
          v5,
          (const unsigned __int16 **)&v12);
      }
      TraceLoggingRegister_EventRegister_EventSetInformation(&dword_18001E080);
    }
  }
  else
  {
    v6 = RegHandle;
    dword_18001E080 = 0;
    RegHandle = 0;
    EventUnregister(v6);
    if ( (unsigned int)dword_18001E048 > 5 )
    {
      v12 = "Reason";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v7,
        (__int64)&dword_1800185F4,
        v8,
        v9,
        (const unsigned __int16 **)&v12);
    }
    v10 = qword_18001E068;
    dword_18001E048 = 0;
    qword_18001E068 = 0;
    EventUnregister(v10);
  }
  return 1;
}

```

## disassembly

```asm
0x180002ed0  sub     rsp, 38h
0x180002ed4  test    edx, edx
0x180002ed6  jz      short loc_180002F28
0x180002ed8  cmp     edx, 1
0x180002edb  jnz     loc_180002F99
0x180002ee1  lea     rcx, dword_18001E048; CallbackContext
0x180002ee8  call    TraceLoggingRegister_EventRegister_EventSetInformation
0x180002eed  mov     eax, cs:dword_18001E048
0x180002ef3  cmp     eax, 5
0x180002ef6  jbe     short loc_180002F1A
0x180002ef8  lea     rax, aReason; "Reason"
0x180002eff  mov     [rsp+38h+arg_18], rax
0x180002f04  lea     rdx, byte_180018569
0x180002f0b  lea     rax, [rsp+38h+arg_18]
0x180002f10  mov     [rsp+38h+var_18], rax
0x180002f15  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180002f1a  lea     rcx, dword_18001E080; CallbackContext
0x180002f21  call    TraceLoggingRegister_EventRegister_EventSetInformation
0x180002f26  jmp     short loc_180002F99
0x180002f28  mov     rcx, cs:RegHandle; RegHandle
0x180002f2f  mov     cs:dword_18001E080, 0
0x180002f39  mov     cs:RegHandle, 0
0x180002f44  call    cs:__imp_EventUnregister
0x180002f4a  mov     eax, cs:dword_18001E048
0x180002f50  cmp     eax, 5
0x180002f53  jbe     short loc_180002F77
0x180002f55  lea     rax, aReason; "Reason"
0x180002f5c  mov     [rsp+38h+arg_18], rax
0x180002f61  lea     rdx, dword_1800185F4
0x180002f68  lea     rax, [rsp+38h+arg_18]
0x180002f6d  mov     [rsp+38h+var_18], rax
0x180002f72  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180002f77  mov     rcx, cs:qword_18001E068; RegHandle
0x180002f7e  mov     cs:dword_18001E048, 0
0x180002f88  mov     cs:qword_18001E068, 0
0x180002f93  call    cs:__imp_EventUnregister
0x180002f99  mov     eax, 1
0x180002f9e  add     rsp, 38h
0x180002fa2  retn
```
