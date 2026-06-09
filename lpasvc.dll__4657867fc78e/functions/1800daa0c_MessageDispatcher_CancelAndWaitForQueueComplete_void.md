# MessageDispatcher::CancelAndWaitForQueueComplete(void)

- ea: `0x1800daa0c`
- end: `0x1800dab6d`
- name: `?CancelAndWaitForQueueComplete@MessageDispatcher@@QEAAJXZ`
- size: `353`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180072ad4`
- `0x1800733c4`

## callees

- `0x180001010`
- `0x1800017c8`
- `0x1800daa0c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800daa68`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800daa68`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800daa7d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800daa7d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800daa9a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800daa9a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800daa2c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800daa42`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800dab5a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800daa2c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800daa42`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800dab5a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800daa1d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800dab4a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800daa1d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800dab4a`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800daa88`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800daa88`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800daa55`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800daa55`

## string_xrefs

- `0x1800daac1`: `MessageDispatcher::CancelAndWaitForQueueComplete`
- `0x1800dab00`: `MessageDispatcher::CancelAndWaitForQueueComplete`

## pseudocode

```c
__int64 __fastcall MessageDispatcher::CancelAndWaitForQueueComplete(PVOID pv)
{
  struct _RTL_CRITICAL_SECTION *v2; // rcx
  struct _TP_WORK *ThreadpoolWork; // rdi
  HANDLE EventW; // rax
  DWORD v6; // ecx
  int v7; // r8d
  int v8; // r9d
  struct _RTL_CRITICAL_SECTION *v9; // rcx
  const char *v10; // [rsp+50h] [rbp+8h] BYREF
  const char *v11; // [rsp+58h] [rbp+10h] BYREF
  const char *v12; // [rsp+60h] [rbp+18h] BYREF

  EnterCriticalSection(*((LPCRITICAL_SECTION *)pv + 3));
  v2 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)pv + 3);
  if ( *(_DWORD *)pv == 2 )
  {
    *(_DWORD *)pv = 3;
    LeaveCriticalSection(v2);
    ThreadpoolWork = CreateThreadpoolWork(MessageDispatcher::_CancelWorkCallback, pv, 0);
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)pv + 17) = EventW;
    if ( ThreadpoolWork )
      SubmitThreadpoolWork(ThreadpoolWork);
    else
      SetEvent(EventW);
    v6 = WaitForSingleObject(*((HANDLE *)pv + 17), 0x493E0u);
    if ( v6 )
    {
      if ( v6 == 258 )
      {
        if ( (unsigned int)CallbackContext > 4 )
        {
          v10 = "MessageDispatcher::CancelAndWaitForQueueComplete";
          v11 = "Dispatcher";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
            258,
            (unsigned int)byte_180134B19,
            v7,
            v8,
            (__int64)&v11,
            (__int64)&v10);
        }
      }
      else if ( (unsigned int)CallbackContext > 4 )
      {
        LODWORD(v10) = v6;
        v11 = "MessageDispatcher::CancelAndWaitForQueueComplete";
        v12 = "Dispatcher";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v6,
          (unsigned int)&byte_180134B57,
          v7,
          v8,
          (__int64)&v12,
          (__int64)&v11,
          (__int64)&v10);
      }
    }
    EnterCriticalSection(*((LPCRITICAL_SECTION *)pv + 3));
    v9 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)pv + 3);
    *(_DWORD *)pv = 2;
    LeaveCriticalSection(v9);
    return 0;
  }
  else
  {
    LeaveCriticalSection(v2);
    return 2147947423LL;
  }
}

```

## disassembly

```asm
0x1800daa0c  mov     [rsp+arg_18], rbx
0x1800daa11  push    rdi
0x1800daa12  sub     rsp, 40h
0x1800daa16  mov     rbx, rcx
0x1800daa19  mov     rcx, [rcx+18h]; lpCriticalSection
0x1800daa1d  call    cs:__imp_EnterCriticalSection
0x1800daa23  cmp     dword ptr [rbx], 2
0x1800daa26  mov     rcx, [rbx+18h]; lpCriticalSection
0x1800daa2a  jz      short loc_1800DAA3C
0x1800daa2c  call    cs:__imp_LeaveCriticalSection
0x1800daa32  mov     eax, 8007139Fh
0x1800daa37  jmp     loc_1800DAB62
0x1800daa3c  mov     dword ptr [rbx], 3
0x1800daa42  call    cs:__imp_LeaveCriticalSection
0x1800daa48  xor     r8d, r8d; pcbe
0x1800daa4b  lea     rcx, ?_CancelWorkCallback@MessageDispatcher@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800daa52  mov     rdx, rbx; pv
0x1800daa55  call    cs:__imp_CreateThreadpoolWork
0x1800daa5b  xor     r9d, r9d; lpName
0x1800daa5e  xor     r8d, r8d; bInitialState
0x1800daa61  xor     edx, edx; bManualReset
0x1800daa63  xor     ecx, ecx; lpEventAttributes
0x1800daa65  mov     rdi, rax
0x1800daa68  call    cs:__imp_CreateEventW
0x1800daa6e  mov     [rbx+88h], rax
0x1800daa75  test    rdi, rdi
0x1800daa78  jnz     short loc_1800DAA85
0x1800daa7a  mov     rcx, rax; hEvent
0x1800daa7d  call    cs:__imp_SetEvent
0x1800daa83  jmp     short loc_1800DAA8E
0x1800daa85  mov     rcx, rdi; pwk
0x1800daa88  call    cs:__imp_SubmitThreadpoolWork
0x1800daa8e  mov     rcx, [rbx+88h]; hHandle
0x1800daa95  mov     edx, 493E0h; dwMilliseconds
0x1800daa9a  call    cs:__imp_WaitForSingleObject
0x1800daaa0  mov     ecx, eax
0x1800daaa2  test    eax, eax
0x1800daaa4  jz      loc_1800DAB46
0x1800daaaa  mov     eax, cs:CallbackContext
0x1800daab0  cmp     ecx, 102h
0x1800daab6  jnz     short loc_1800DAAFB
0x1800daab8  cmp     eax, 4
0x1800daabb  jbe     loc_1800DAB46
0x1800daac1  lea     rax, aMessagedispatc; "MessageDispatcher::CancelAndWaitForQueu"...
0x1800daac8  mov     [rsp+48h+arg_0], rax
0x1800daacd  lea     rdx, byte_180134B19
0x1800daad4  lea     rax, aDispatcher; "Dispatcher"
0x1800daadb  mov     [rsp+48h+arg_8], rax
0x1800daae0  lea     rax, [rsp+48h+arg_0]
0x1800daae5  mov     [rsp+48h+var_20], rax
0x1800daaea  lea     rax, [rsp+48h+arg_8]
0x1800daaef  mov     [rsp+48h+var_28], rax
0x1800daaf4  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800daaf9  jmp     short loc_1800DAB46
0x1800daafb  cmp     eax, 4
0x1800daafe  jbe     short loc_1800DAB46
0x1800dab00  lea     rax, aMessagedispatc; "MessageDispatcher::CancelAndWaitForQueu"...
0x1800dab07  mov     dword ptr [rsp+48h+arg_0], ecx
0x1800dab0b  mov     [rsp+48h+arg_8], rax
0x1800dab10  lea     rdx, byte_180134B57
0x1800dab17  lea     rax, aDispatcher; "Dispatcher"
0x1800dab1e  mov     [rsp+48h+arg_10], rax
0x1800dab23  lea     rax, [rsp+48h+arg_0]
0x1800dab28  mov     [rsp+48h+var_18], rax
0x1800dab2d  lea     rax, [rsp+48h+arg_8]
0x1800dab32  mov     [rsp+48h+var_20], rax
0x1800dab37  lea     rax, [rsp+48h+arg_10]
0x1800dab3c  mov     [rsp+48h+var_28], rax
0x1800dab41  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800dab46  mov     rcx, [rbx+18h]; lpCriticalSection
0x1800dab4a  call    cs:__imp_EnterCriticalSection
0x1800dab50  mov     rcx, [rbx+18h]; lpCriticalSection
0x1800dab54  mov     dword ptr [rbx], 2
0x1800dab5a  call    cs:__imp_LeaveCriticalSection
0x1800dab60  xor     eax, eax
0x1800dab62  mov     rbx, [rsp+48h+arg_18]
0x1800dab67  add     rsp, 40h
0x1800dab6b  pop     rdi
0x1800dab6c  retn
```
