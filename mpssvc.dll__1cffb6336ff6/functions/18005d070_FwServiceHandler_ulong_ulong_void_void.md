# FwServiceHandler(ulong,ulong,void *,void *)

- ea: `0x18005d070`
- end: `0x18005d2cc`
- name: `?FwServiceHandler@@YAKKKPEAX0@Z`
- size: `604`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, service_task`

## callees

- `0x180001518`
- `0x180001820`
- `0x180017110`
- `0x18004d58c`
- `0x18005cf9c`
- `0x18005d070`
- `0x180075194`
- `0x18007529c`
- `0x180078498`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18005d22d`
- `ntdll!EtwEventWrite` at `0x18005d22d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005d1ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005d1ef`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005d1ad`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005d244`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005d1ad`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005d244`
- `fwbase!FwCriticalSectionEnter` at `0x18005d127`
- `fwbase!FwCriticalSectionEnter` at `0x18005d127`
- `fwbase!FwCriticalSectionLeave` at `0x18005d294`
- `fwbase!FwCriticalSectionLeave` at `0x18005d294`

## pseudocode

```c
__int64 __fastcall FwServiceHandler(DWORD dwControl, __int64 dwEventType, LPVOID lpEventData, LPVOID lpContext)
{
  DWORD v4; // ebx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  const char *v18[7]; // [rsp+30h] [rbp-38h] BYREF
  DWORD CurrentProcessId; // [rsp+70h] [rbp+8h] BYREF

  v4 = dwEventType;
  v6 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 40, WPP_37aa6ebbaa413bd78411cd982c84adcd_Traceguids);
      v6 = WPP_GLOBAL_Control;
    }
    if ( (_UNKNOWN *)v6 != &WPP_GLOBAL_Control && (*(_BYTE *)(v6 + 28) & 4) != 0 )
      WPP_SF_LL(*(_QWORD *)(v6 + 16), dwEventType, lpEventData, dwControl, v4);
  }
  if ( (unsigned int)dword_1801263B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1801263B0, 0x4000000000000LL) )
  {
    CurrentProcessId = v4;
    LODWORD(v18[0]) = dwControl;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (int)&dword_1801263B0,
      (int)&dword_18010E5B4,
      v7,
      v8,
      (__int64)v18,
      (__int64)&CurrentProcessId);
  }
  FwCriticalSectionEnter(qword_18012BEE8);
  switch ( dwControl )
  {
    case 1u:
      goto LABEL_24;
    case 4u:
      break;
    case 5u:
LABEL_24:
      if ( g_Provider )
        EtwEventWrite(g_Provider, MPS_SVC_Stop_Begin, 0, 0);
      FwServiceChangeState(3u);
      SetEvent(qword_18012BF70);
      if ( (unsigned int)dword_1801263B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1801263B0, 0x4000000000000LL) )
      {
        v18[0] = "pending_set_shutdown_event";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v14,
          (int)byte_18010E64B,
          v15,
          v16,
          v18);
      }
      break;
    case 0xDu:
      if ( (v4 == 7 || v4 == 18)
        && (unsigned int)dword_1801263B0 > 4
        && (unsigned __int8)tlgKeywordOn(&dword_1801263B0, 0x4000000000000LL) )
      {
        CurrentProcessId = GetCurrentProcessId();
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (int)&dword_1801263B0,
          (int)word_18010E5FA,
          v12,
          v13,
          (__int64)&CurrentProcessId);
      }
      break;
    default:
      if ( (unsigned int)dword_1801263B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1801263B0, 0x4000000000000LL) )
      {
        v18[0] = "unknown_event_queue_control";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v9,
          (int)&unk_18010E7D8,
          v10,
          v11,
          v18);
      }
      FwServiceControlQueuePushBack(dwControl);
      if ( byte_18012BF62 )
        SetEvent(qword_18012BF50);
      break;
  }
  FwCriticalSectionLeave(qword_18012BEE8);
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 42, WPP_37aa6ebbaa413bd78411cd982c84adcd_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x18005d070  push    rbx
0x18005d072  push    rbp
0x18005d073  push    rsi
0x18005d074  push    rdi
0x18005d075  sub     rsp, 48h
0x18005d079  mov     ebx, edx
0x18005d07b  mov     edi, ecx
0x18005d07d  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d084  lea     rbp, WPP_GLOBAL_Control
0x18005d08b  cmp     rcx, rbp
0x18005d08e  jz      short loc_18005D0CD
0x18005d090  test    byte ptr [rcx+1Ch], 8
0x18005d094  jz      short loc_18005D0B2
0x18005d096  mov     rcx, [rcx+10h]
0x18005d09a  lea     r8, WPP_37aa6ebbaa413bd78411cd982c84adcd_Traceguids
0x18005d0a1  mov     edx, 28h ; '('
0x18005d0a6  call    WPP_SF_
0x18005d0ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d0b2  cmp     rcx, rbp
0x18005d0b5  jz      short loc_18005D0CD
0x18005d0b7  test    byte ptr [rcx+1Ch], 4
0x18005d0bb  jz      short loc_18005D0CD
0x18005d0bd  mov     rcx, [rcx+10h]
0x18005d0c1  mov     r9d, edi
0x18005d0c4  mov     dword ptr [rsp+68h+var_48], ebx
0x18005d0c8  call    WPP_SF_LL
0x18005d0cd  mov     eax, cs:dword_1801263B0
0x18005d0d3  lea     rsi, dword_1801263B0
0x18005d0da  cmp     eax, 4
0x18005d0dd  jbe     short loc_18005D120
0x18005d0df  mov     rdx, 4000000000000h
0x18005d0e9  mov     rcx, rsi
0x18005d0ec  call    _tlgKeywordOn
0x18005d0f1  test    al, al
0x18005d0f3  jz      short loc_18005D120
0x18005d0f5  lea     rax, [rsp+68h+arg_0]
0x18005d0fa  mov     [rsp+68h+arg_0], ebx
0x18005d0fe  mov     [rsp+68h+var_40], rax
0x18005d103  lea     rdx, dword_18010E5B4
0x18005d10a  lea     rax, [rsp+68h+var_38]
0x18005d10f  mov     dword ptr [rsp+68h+var_38], edi
0x18005d113  mov     rcx, rsi
0x18005d116  mov     [rsp+68h+var_48], rax
0x18005d11b  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18005d120  lea     rcx, qword_18012BEE8
0x18005d127  call    cs:__imp_FwCriticalSectionEnter
0x18005d12d  mov     eax, edi
0x18005d12f  sub     eax, 1
0x18005d132  jz      loc_18005D214
0x18005d138  sub     eax, 3
0x18005d13b  jz      loc_18005D28D
0x18005d141  sub     eax, 1
0x18005d144  jz      loc_18005D214
0x18005d14a  cmp     eax, 8
0x18005d14d  jz      short loc_18005D1B8
0x18005d14f  mov     eax, cs:dword_1801263B0
0x18005d155  cmp     eax, 4
0x18005d158  jbe     short loc_18005D192
0x18005d15a  mov     rdx, 4000000000000h
0x18005d164  mov     rcx, rsi
0x18005d167  call    _tlgKeywordOn
0x18005d16c  test    al, al
0x18005d16e  jz      short loc_18005D192
0x18005d170  lea     rax, aUnknownEventQu; "unknown_event_queue_control"
0x18005d177  mov     [rsp+68h+var_38], rax
0x18005d17c  lea     rdx, unk_18010E7D8
0x18005d183  lea     rax, [rsp+68h+var_38]
0x18005d188  mov     [rsp+68h+var_48], rax
0x18005d18d  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18005d192  mov     ecx, edi; unsigned int
0x18005d194  call    ?FwServiceControlQueuePushBack@@YAJK@Z; FwServiceControlQueuePushBack(ulong)
0x18005d199  cmp     cs:byte_18012BF62, 0
0x18005d1a0  jz      loc_18005D28D
0x18005d1a6  mov     rcx, cs:qword_18012BF50; hEvent
0x18005d1ad  call    cs:__imp_SetEvent
0x18005d1b3  jmp     loc_18005D28D
0x18005d1b8  cmp     ebx, 7
0x18005d1bb  jz      short loc_18005D1C6
0x18005d1bd  cmp     ebx, 12h
0x18005d1c0  jnz     loc_18005D28D
0x18005d1c6  mov     eax, cs:dword_1801263B0
0x18005d1cc  cmp     eax, 4
0x18005d1cf  jbe     loc_18005D28D
0x18005d1d5  mov     rdx, 4000000000000h
0x18005d1df  mov     rcx, rsi
0x18005d1e2  call    _tlgKeywordOn
0x18005d1e7  test    al, al
0x18005d1e9  jz      loc_18005D28D
0x18005d1ef  call    cs:__imp_GetCurrentProcessId
0x18005d1f5  mov     [rsp+68h+arg_0], eax
0x18005d1f9  lea     rdx, word_18010E5FA
0x18005d200  lea     rax, [rsp+68h+arg_0]
0x18005d205  mov     rcx, rsi
0x18005d208  mov     [rsp+68h+var_48], rax
0x18005d20d  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18005d212  jmp     short loc_18005D28D
0x18005d214  mov     rcx, cs:g_Provider
0x18005d21b  test    rcx, rcx
0x18005d21e  jz      short loc_18005D233
0x18005d220  xor     r9d, r9d
0x18005d223  lea     rdx, MPS_SVC_Stop_Begin
0x18005d22a  xor     r8d, r8d
0x18005d22d  call    cs:__imp_EtwEventWrite
0x18005d233  mov     ecx, 3; unsigned int
0x18005d238  call    ?FwServiceChangeState@@YAJK@Z; FwServiceChangeState(ulong)
0x18005d23d  mov     rcx, cs:qword_18012BF70; hEvent
0x18005d244  call    cs:__imp_SetEvent
0x18005d24a  mov     eax, cs:dword_1801263B0
0x18005d250  cmp     eax, 4
0x18005d253  jbe     short loc_18005D28D
0x18005d255  mov     rdx, 4000000000000h
0x18005d25f  mov     rcx, rsi
0x18005d262  call    _tlgKeywordOn
0x18005d267  test    al, al
0x18005d269  jz      short loc_18005D28D
0x18005d26b  lea     rax, aPendingSetShut; "pending_set_shutdown_event"
0x18005d272  mov     [rsp+68h+var_38], rax
0x18005d277  lea     rdx, byte_18010E64B
0x18005d27e  lea     rax, [rsp+68h+var_38]
0x18005d283  mov     [rsp+68h+var_48], rax
0x18005d288  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18005d28d  lea     rcx, qword_18012BEE8
0x18005d294  call    cs:__imp_FwCriticalSectionLeave
0x18005d29a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d2a1  cmp     rcx, rbp
0x18005d2a4  jz      short loc_18005D2C1
0x18005d2a6  test    byte ptr [rcx+1Ch], 8
0x18005d2aa  jz      short loc_18005D2C1
0x18005d2ac  mov     rcx, [rcx+10h]
0x18005d2b0  lea     r8, WPP_37aa6ebbaa413bd78411cd982c84adcd_Traceguids
0x18005d2b7  mov     edx, 2Ah ; '*'
0x18005d2bc  call    WPP_SF_
0x18005d2c1  xor     eax, eax
0x18005d2c3  add     rsp, 48h
0x18005d2c7  pop     rdi
0x18005d2c8  pop     rsi
0x18005d2c9  pop     rbp
0x18005d2ca  pop     rbx
0x18005d2cb  retn
```
