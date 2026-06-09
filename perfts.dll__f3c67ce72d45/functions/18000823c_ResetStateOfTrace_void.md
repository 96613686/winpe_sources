# ResetStateOfTrace(void)

- ea: `0x18000823c`
- end: `0x18000833e`
- name: `?ResetStateOfTrace@@YAHXZ`
- size: `258`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180004e40`
- `0x18000576c`

## callees

- `0x180001008`
- `0x180006c50`
- `0x18000823c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000827e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000827e`
- `ADVAPI32!ControlTraceW` at `0x180008271`
- `ADVAPI32!ControlTraceW` at `0x180008271`

## string_xrefs

- `0x180008314`: `Failed to create buffer.`

## pseudocode

```c
__int64 ResetStateOfTrace(void)
{
  int v0; // ecx
  int v1; // r8d
  int v2; // r9d
  ULONG v3; // ebx
  char *v5; // rax
  void *v6; // rdx
  PEVENT_TRACE_PROPERTIES Properties; // [rsp+40h] [rbp+8h] BYREF

  Properties = 0;
  if ( MakeBufferForControl(&Properties) )
  {
    v3 = ControlTraceW(0, LagCounterManager::EtwSessionName, Properties, 1u);
    operator delete(Properties);
    if ( !v3 )
    {
      if ( (unsigned int)dword_180012020 > 4 )
      {
        Properties = (PEVENT_TRACE_PROPERTIES)"Session Lag Trace was running, stopping.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v0,
          (unsigned int)&unk_18000EEFB,
          v1,
          v2,
          (__int64)&Properties);
      }
      return 1;
    }
    if ( v3 == 4201 )
    {
      if ( (unsigned int)dword_180012020 > 4 )
      {
        Properties = (PEVENT_TRACE_PROPERTIES)"Session Lag Trace was not running.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (unsigned int)&Properties,
          (unsigned int)&unk_18000F117,
          v1,
          v2,
          (__int64)&Properties);
      }
      return 1;
    }
    if ( (unsigned int)dword_180012020 > 2 )
    {
      v5 = "Unknown status for Session Lag Trace, probably a bug.";
      v6 = &unk_18000F235;
LABEL_13:
      Properties = (PEVENT_TRACE_PROPERTIES)v5;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v0,
        (_DWORD)v6,
        v1,
        v2,
        (__int64)&Properties);
    }
  }
  else if ( (unsigned int)dword_180012020 > 4 )
  {
    v5 = "Failed to create buffer.";
    v6 = &unk_18000EF81;
    goto LABEL_13;
  }
  return 0;
}

```

## disassembly

```asm
0x18000823c  push    rbx
0x18000823e  sub     rsp, 30h
0x180008242  lea     rcx, [rsp+38h+Properties]; struct _EVENT_TRACE_PROPERTIES **
0x180008247  mov     [rsp+38h+Properties], 0
0x180008250  call    ?MakeBufferForControl@@YA_NPEAPEAU_EVENT_TRACE_PROPERTIES@@@Z; MakeBufferForControl(_EVENT_TRACE_PROPERTIES * *)
0x180008255  test    al, al
0x180008257  jz      loc_180008309
0x18000825d  mov     r8, [rsp+38h+Properties]; Properties
0x180008262  lea     rdx, ?EtwSessionName@LagCounterManager@@2PAGA; InstanceName
0x180008269  mov     r9d, 1; ControlCode
0x18000826f  xor     ecx, ecx; TraceHandle
0x180008271  call    cs:__imp_ControlTraceW
0x180008277  mov     rcx, [rsp+38h+Properties]
0x18000827c  mov     ebx, eax
0x18000827e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008284  test    ebx, ebx
0x180008286  jnz     short loc_1800082B2
0x180008288  mov     eax, cs:dword_180012020
0x18000828e  cmp     eax, 4
0x180008291  jbe     short loc_1800082E7
0x180008293  lea     rax, aSessionLagTrac_0; "Session Lag Trace was running, stopping"...
0x18000829a  mov     [rsp+38h+Properties], rax
0x18000829f  lea     rdx, unk_18000EEFB
0x1800082a6  lea     rax, [rsp+38h+Properties]
0x1800082ab  mov     [rsp+38h+var_18], rax
0x1800082b0  jmp     short loc_1800082E2
0x1800082b2  cmp     ebx, 1069h
0x1800082b8  jnz     short loc_1800082EE
0x1800082ba  mov     ecx, cs:dword_180012020
0x1800082c0  cmp     ecx, 4
0x1800082c3  jbe     short loc_1800082E7
0x1800082c5  lea     rcx, aSessionLagTrac; "Session Lag Trace was not running."
0x1800082cc  mov     [rsp+38h+Properties], rcx
0x1800082d1  lea     rdx, unk_18000F117
0x1800082d8  lea     rcx, [rsp+38h+Properties]
0x1800082dd  mov     [rsp+38h+var_18], rcx
0x1800082e2  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800082e7  mov     eax, 1
0x1800082ec  jmp     short loc_180008338
0x1800082ee  mov     eax, cs:dword_180012020
0x1800082f4  cmp     eax, 2
0x1800082f7  jbe     short loc_180008336
0x1800082f9  lea     rax, aUnknownStatusF; "Unknown status for Session Lag Trace, p"...
0x180008300  lea     rdx, unk_18000F235
0x180008307  jmp     short loc_180008322
0x180008309  mov     eax, cs:dword_180012020
0x18000830f  cmp     eax, 4
0x180008312  jbe     short loc_180008336
0x180008314  lea     rax, aFailedToCreate_0; "Failed to create buffer."
0x18000831b  lea     rdx, unk_18000EF81
0x180008322  mov     [rsp+38h+Properties], rax
0x180008327  lea     rax, [rsp+38h+Properties]
0x18000832c  mov     [rsp+38h+var_18], rax
0x180008331  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180008336  xor     eax, eax
0x180008338  add     rsp, 30h
0x18000833c  pop     rbx
0x18000833d  retn
```
