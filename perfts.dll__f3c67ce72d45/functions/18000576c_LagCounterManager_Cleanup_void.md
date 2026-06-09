# LagCounterManager::Cleanup(void)

- ea: `0x18000576c`
- end: `0x1800058b1`
- name: `?Cleanup@LagCounterManager@@SAXXZ`
- size: `325`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180006d0c`

## callees

- `0x180001008`
- `0x180001098`
- `0x18000576c`
- `0x180006c50`
- `0x18000823c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180005823`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005823`
- `KERNEL32!Sleep` at `0x180005853`
- `KERNEL32!Sleep` at `0x180005853`
- `ADVAPI32!FlushTraceW` at `0x180005818`
- `ADVAPI32!FlushTraceW` at `0x180005818`
- `ADVAPI32!CloseTrace` at `0x180005830`
- `ADVAPI32!CloseTrace` at `0x180005846`
- `ADVAPI32!CloseTrace` at `0x180005830`
- `ADVAPI32!CloseTrace` at `0x180005846`

## string_xrefs

- `0x1800057bd`: `Failed to stop ETW thread during clean up`

## pseudocode

```c
void __fastcall LagCounterManager::Cleanup(int a1, __int64 a2, int a3, int a4)
{
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d
  int v7; // ecx
  ULONG v8; // ebx
  int v9; // r8d
  int v10; // r9d
  PEVENT_TRACE_PROPERTIES Properties; // [rsp+40h] [rbp+8h] BYREF
  const char *v12; // [rsp+48h] [rbp+10h] BYREF

  if ( (unsigned int)dword_180012020 > 4 )
  {
    Properties = (PEVENT_TRACE_PROPERTIES)"Cleaning up Lag counter in Manager Cleanup";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      a1,
      (unsigned int)&unk_18000F215,
      a3,
      a4,
      (__int64)&Properties);
  }
  LagCounterManager::bPendingShutdown = 1;
  if ( !(unsigned int)ResetStateOfTrace() && (unsigned int)dword_180012020 > 2 )
  {
    Properties = (PEVENT_TRACE_PROPERTIES)"Failed to stop ETW thread during clean up";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v4,
      (unsigned int)&unk_18000F2C6,
      v5,
      v6,
      (__int64)&Properties);
  }
  if ( LagCounterManager::hTrace - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    Properties = 0;
    if ( MakeBufferForControl(&Properties) )
    {
      FlushTraceW(LagCounterManager::hTrace, 0, Properties);
      operator delete(Properties);
    }
    v8 = CloseTrace(LagCounterManager::hTrace);
    while ( v8 == 7007 )
    {
      v8 = CloseTrace(LagCounterManager::hTrace);
      Sleep(0x64u);
    }
    if ( v8 )
    {
      if ( (unsigned int)dword_180012020 > 2 )
      {
        LODWORD(Properties) = v8;
        v12 = "Error stopping trace in Lag Counter";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v7,
          (unsigned int)&unk_18000F04C,
          v9,
          v10,
          (__int64)&v12,
          (__int64)&Properties);
      }
    }
    LagCounterManager::hTrace = -1;
  }
}

```

## disassembly

```asm
0x18000576c  push    rbx
0x18000576e  sub     rsp, 30h
0x180005772  mov     eax, cs:dword_180012020
0x180005778  cmp     eax, 4
0x18000577b  jbe     short loc_18000579F
0x18000577d  lea     rax, aCleaningUpLagC; "Cleaning up Lag counter in Manager Clea"...
0x180005784  mov     [rsp+38h+Properties], rax
0x180005789  lea     rdx, unk_18000F215
0x180005790  lea     rax, [rsp+38h+Properties]
0x180005795  mov     [rsp+38h+var_18], rax
0x18000579a  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18000579f  mov     cs:?bPendingShutdown@LagCounterManager@@2HA, 1; int LagCounterManager::bPendingShutdown
0x1800057a9  call    ?ResetStateOfTrace@@YAHXZ; ResetStateOfTrace(void)
0x1800057ae  test    eax, eax
0x1800057b0  jnz     short loc_1800057DF
0x1800057b2  mov     eax, cs:dword_180012020
0x1800057b8  cmp     eax, 2
0x1800057bb  jbe     short loc_1800057DF
0x1800057bd  lea     rax, aFailedToStopEt; "Failed to stop ETW thread during clean "...
0x1800057c4  mov     [rsp+38h+Properties], rax
0x1800057c9  lea     rdx, unk_18000F2C6
0x1800057d0  lea     rax, [rsp+38h+Properties]
0x1800057d5  mov     [rsp+38h+var_18], rax
0x1800057da  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800057df  mov     rax, cs:?hTrace@LagCounterManager@@2_KA; unsigned __int64 LagCounterManager::hTrace
0x1800057e6  dec     rax
0x1800057e9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800057ed  ja      loc_1800058AB
0x1800057f3  lea     rcx, [rsp+38h+Properties]; struct _EVENT_TRACE_PROPERTIES **
0x1800057f8  mov     [rsp+38h+Properties], 0
0x180005801  call    ?MakeBufferForControl@@YA_NPEAPEAU_EVENT_TRACE_PROPERTIES@@@Z; MakeBufferForControl(_EVENT_TRACE_PROPERTIES * *)
0x180005806  test    al, al
0x180005808  jz      short loc_180005829
0x18000580a  mov     r8, [rsp+38h+Properties]; Properties
0x18000580f  xor     edx, edx; InstanceName
0x180005811  mov     rcx, cs:?hTrace@LagCounterManager@@2_KA; TraceHandle
0x180005818  call    cs:__imp_FlushTraceW
0x18000581e  mov     rcx, [rsp+38h+Properties]
0x180005823  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005829  mov     rcx, cs:?hTrace@LagCounterManager@@2_KA; TraceHandle
0x180005830  call    cs:__imp_CloseTrace
0x180005836  mov     ebx, eax
0x180005838  cmp     eax, 1B5Fh
0x18000583d  jnz     short loc_180005861
0x18000583f  mov     rcx, cs:?hTrace@LagCounterManager@@2_KA; TraceHandle
0x180005846  call    cs:__imp_CloseTrace
0x18000584c  mov     ecx, 64h ; 'd'; dwMilliseconds
0x180005851  mov     ebx, eax
0x180005853  call    cs:__imp_Sleep
0x180005859  cmp     ebx, 1B5Fh
0x18000585f  jz      short loc_18000583F
0x180005861  test    ebx, ebx
0x180005863  jz      short loc_1800058A0
0x180005865  mov     eax, cs:dword_180012020
0x18000586b  cmp     eax, 2
0x18000586e  jbe     short loc_1800058A0
0x180005870  lea     rax, aErrorStoppingT; "Error stopping trace in Lag Counter"
0x180005877  mov     dword ptr [rsp+38h+Properties], ebx
0x18000587b  mov     [rsp+38h+arg_8], rax
0x180005880  lea     rdx, unk_18000F04C
0x180005887  lea     rax, [rsp+38h+Properties]
0x18000588c  mov     [rsp+38h+var_10], rax
0x180005891  lea     rax, [rsp+38h+arg_8]
0x180005896  mov     [rsp+38h+var_18], rax
0x18000589b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800058a0  mov     cs:?hTrace@LagCounterManager@@2_KA, 0FFFFFFFFFFFFFFFFh; unsigned __int64 LagCounterManager::hTrace
0x1800058ab  add     rsp, 30h
0x1800058af  pop     rbx
0x1800058b0  retn
```
