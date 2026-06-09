# FwServiceHandler(ulong,ulong,void *,void *)

- ea: `0x180061d60`
- end: `0x180061fe4`
- name: `?FwServiceHandler@@YAKKKPEAX0@Z`
- size: `644`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, service_task`

## callees

- `0x18000151c`
- `0x18000182c`
- `0x1800192e0`
- `0x1800508b4`
- `0x180061c90`
- `0x180061d60`
- `0x180078770`
- `0x180078884`
- `0x18007bd38`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180061f32`
- `ntdll!EtwEventWrite` at `0x180061f32`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180061eeb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180061eeb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180061ea3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180061f4f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180061ea3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180061f4f`
- `fwbase!FwCriticalSectionEnter` at `0x180061e17`
- `fwbase!FwCriticalSectionEnter` at `0x180061e17`
- `fwbase!FwCriticalSectionLeave` at `0x180061fa5`
- `fwbase!FwCriticalSectionLeave` at `0x180061fa5`

## pseudocode

```c
__int64 __fastcall FwServiceHandler(DWORD dwControl, __int64 dwEventType, LPVOID lpEventData, LPVOID lpContext)
{
  DWORD v4; // ebx
  __int64 v6; // rcx
  int v7; // r8d
  int v8; // r9d
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  int v12; // r8d
  int v13; // r9d
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  _QWORD v18[7]; // [rsp+30h] [rbp-38h] BYREF
  DWORD CurrentProcessId; // [rsp+70h] [rbp+8h] BYREF

  v4 = dwEventType;
  v6 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 40, WPP_6ecef8908d8a371d9bc71e6c2b7caf06_Traceguids);
      v6 = WPP_GLOBAL_Control;
    }
    if ( (_UNKNOWN *)v6 != &WPP_GLOBAL_Control && (*(_BYTE *)(v6 + 28) & 4) != 0 )
      WPP_SF_LL(*(_QWORD *)(v6 + 16), dwEventType, lpEventData, dwControl, v4);
  }
  if ( (unsigned int)dword_18012C3B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18012C3B0, 0x4000000000000LL) )
  {
    CurrentProcessId = v4;
    LODWORD(v18[0]) = dwControl;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_18012C3B0,
      (unsigned int)&dword_1801143CC,
      v7,
      v8,
      (__int64)v18,
      (__int64)&CurrentProcessId);
  }
  FwCriticalSectionEnter(qword_1801320C8);
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
      SetEvent(qword_180132150);
      if ( (unsigned int)dword_18012C3B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18012C3B0, 0x4000000000000LL) )
      {
        v18[0] = "pending_set_shutdown_event";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v14,
          (unsigned int)byte_180114463,
          v15,
          v16,
          (__int64)v18);
      }
      break;
    case 0xDu:
      if ( (v4 == 7 || v4 == 18)
        && (unsigned int)dword_18012C3B0 > 4
        && (unsigned __int8)tlgKeywordOn(&dword_18012C3B0, 0x4000000000000LL) )
      {
        CurrentProcessId = GetCurrentProcessId();
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (unsigned int)&dword_18012C3B0,
          (unsigned int)word_180114412,
          v12,
          v13,
          (__int64)&CurrentProcessId);
      }
      break;
    default:
      if ( (unsigned int)dword_18012C3B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18012C3B0, 0x4000000000000LL) )
      {
        v18[0] = "unknown_event_queue_control";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v9,
          (unsigned int)&unk_1801145F0,
          v10,
          v11,
          (__int64)v18);
      }
      FwServiceControlQueuePushBack(dwControl);
      if ( byte_180132142 )
        SetEvent(qword_180132130);
      break;
  }
  FwCriticalSectionLeave(qword_1801320C8);
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 42, WPP_6ecef8908d8a371d9bc71e6c2b7caf06_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x180061d60  push    rbx
0x180061d62  push    rbp
0x180061d63  push    rsi
0x180061d64  push    rdi
0x180061d65  sub     rsp, 48h
0x180061d69  mov     ebx, edx
0x180061d6b  mov     edi, ecx
0x180061d6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180061d74  lea     rbp, WPP_GLOBAL_Control
0x180061d7b  cmp     rcx, rbp
0x180061d7e  jz      short loc_180061DBD
0x180061d80  test    byte ptr [rcx+1Ch], 8
0x180061d84  jz      short loc_180061DA2
0x180061d86  mov     rcx, [rcx+10h]
0x180061d8a  lea     r8, WPP_6ecef8908d8a371d9bc71e6c2b7caf06_Traceguids
0x180061d91  mov     edx, 28h ; '('
0x180061d96  call    WPP_SF_
0x180061d9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180061da2  cmp     rcx, rbp
0x180061da5  jz      short loc_180061DBD
0x180061da7  test    byte ptr [rcx+1Ch], 4
0x180061dab  jz      short loc_180061DBD
0x180061dad  mov     rcx, [rcx+10h]
0x180061db1  mov     r9d, edi
0x180061db4  mov     dword ptr [rsp+68h+var_48], ebx
0x180061db8  call    WPP_SF_LL
0x180061dbd  mov     eax, cs:dword_18012C3B0
0x180061dc3  lea     rsi, dword_18012C3B0
0x180061dca  cmp     eax, 4
0x180061dcd  jbe     short loc_180061E10
0x180061dcf  mov     rdx, 4000000000000h
0x180061dd9  mov     rcx, rsi
0x180061ddc  call    _tlgKeywordOn
0x180061de1  test    al, al
0x180061de3  jz      short loc_180061E10
0x180061de5  lea     rax, [rsp+68h+arg_0]
0x180061dea  mov     [rsp+68h+arg_0], ebx
0x180061dee  mov     [rsp+68h+var_40], rax
0x180061df3  lea     rdx, dword_1801143CC
0x180061dfa  lea     rax, [rsp+68h+var_38]
0x180061dff  mov     dword ptr [rsp+68h+var_38], edi
0x180061e03  mov     rcx, rsi
0x180061e06  mov     [rsp+68h+var_48], rax
0x180061e0b  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180061e10  lea     rcx, qword_1801320C8
0x180061e17  call    cs:__imp_FwCriticalSectionEnter
0x180061e1e  nop     dword ptr [rax+rax+00h]
0x180061e23  mov     eax, edi
0x180061e25  sub     eax, 1
0x180061e28  jz      loc_180061F19
0x180061e2e  sub     eax, 3
0x180061e31  jz      loc_180061F9E
0x180061e37  sub     eax, 1
0x180061e3a  jz      loc_180061F19
0x180061e40  cmp     eax, 8
0x180061e43  jz      short loc_180061EB4
0x180061e45  mov     eax, cs:dword_18012C3B0
0x180061e4b  cmp     eax, 4
0x180061e4e  jbe     short loc_180061E88
0x180061e50  mov     rdx, 4000000000000h
0x180061e5a  mov     rcx, rsi
0x180061e5d  call    _tlgKeywordOn
0x180061e62  test    al, al
0x180061e64  jz      short loc_180061E88
0x180061e66  lea     rax, aUnknownEventQu; "unknown_event_queue_control"
0x180061e6d  mov     [rsp+68h+var_38], rax
0x180061e72  lea     rdx, unk_1801145F0
0x180061e79  lea     rax, [rsp+68h+var_38]
0x180061e7e  mov     [rsp+68h+var_48], rax
0x180061e83  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180061e88  mov     ecx, edi; unsigned int
0x180061e8a  call    ?FwServiceControlQueuePushBack@@YAJK@Z; FwServiceControlQueuePushBack(ulong)
0x180061e8f  cmp     cs:byte_180132142, 0
0x180061e96  jz      loc_180061F9E
0x180061e9c  mov     rcx, cs:qword_180132130; hEvent
0x180061ea3  call    cs:__imp_SetEvent
0x180061eaa  nop     dword ptr [rax+rax+00h]
0x180061eaf  jmp     loc_180061F9E
0x180061eb4  cmp     ebx, 7
0x180061eb7  jz      short loc_180061EC2
0x180061eb9  cmp     ebx, 12h
0x180061ebc  jnz     loc_180061F9E
0x180061ec2  mov     eax, cs:dword_18012C3B0
0x180061ec8  cmp     eax, 4
0x180061ecb  jbe     loc_180061F9E
0x180061ed1  mov     rdx, 4000000000000h
0x180061edb  mov     rcx, rsi
0x180061ede  call    _tlgKeywordOn
0x180061ee3  test    al, al
0x180061ee5  jz      loc_180061F9E
0x180061eeb  call    cs:__imp_GetCurrentProcessId
0x180061ef2  nop     dword ptr [rax+rax+00h]
0x180061ef7  mov     [rsp+68h+arg_0], eax
0x180061efb  lea     rdx, word_180114412
0x180061f02  lea     rax, [rsp+68h+arg_0]
0x180061f07  mov     rcx, rsi
0x180061f0a  mov     [rsp+68h+var_48], rax
0x180061f0f  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180061f14  jmp     loc_180061F9E
0x180061f19  mov     rcx, cs:g_Provider
0x180061f20  test    rcx, rcx
0x180061f23  jz      short loc_180061F3E
0x180061f25  xor     r9d, r9d
0x180061f28  lea     rdx, MPS_SVC_Stop_Begin
0x180061f2f  xor     r8d, r8d
0x180061f32  call    cs:__imp_EtwEventWrite
0x180061f39  nop     dword ptr [rax+rax+00h]
0x180061f3e  mov     ecx, 3; unsigned int
0x180061f43  call    ?FwServiceChangeState@@YAJK@Z; FwServiceChangeState(ulong)
0x180061f48  mov     rcx, cs:qword_180132150; hEvent
0x180061f4f  call    cs:__imp_SetEvent
0x180061f56  nop     dword ptr [rax+rax+00h]
0x180061f5b  mov     eax, cs:dword_18012C3B0
0x180061f61  cmp     eax, 4
0x180061f64  jbe     short loc_180061F9E
0x180061f66  mov     rdx, 4000000000000h
0x180061f70  mov     rcx, rsi
0x180061f73  call    _tlgKeywordOn
0x180061f78  test    al, al
0x180061f7a  jz      short loc_180061F9E
0x180061f7c  lea     rax, aPendingSetShut; "pending_set_shutdown_event"
0x180061f83  mov     [rsp+68h+var_38], rax
0x180061f88  lea     rdx, byte_180114463
0x180061f8f  lea     rax, [rsp+68h+var_38]
0x180061f94  mov     [rsp+68h+var_48], rax
0x180061f99  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180061f9e  lea     rcx, qword_1801320C8
0x180061fa5  call    cs:__imp_FwCriticalSectionLeave
0x180061fac  nop     dword ptr [rax+rax+00h]
0x180061fb1  mov     rcx, cs:WPP_GLOBAL_Control
0x180061fb8  cmp     rcx, rbp
0x180061fbb  jz      short loc_180061FD8
0x180061fbd  test    byte ptr [rcx+1Ch], 8
0x180061fc1  jz      short loc_180061FD8
0x180061fc3  mov     rcx, [rcx+10h]
0x180061fc7  lea     r8, WPP_6ecef8908d8a371d9bc71e6c2b7caf06_Traceguids
0x180061fce  mov     edx, 2Ah ; '*'
0x180061fd3  call    WPP_SF_
0x180061fd8  xor     eax, eax
0x180061fda  add     rsp, 48h
0x180061fde  pop     rdi
0x180061fdf  pop     rsi
0x180061fe0  pop     rbp
0x180061fe1  pop     rbx
0x180061fe2  retn
```
