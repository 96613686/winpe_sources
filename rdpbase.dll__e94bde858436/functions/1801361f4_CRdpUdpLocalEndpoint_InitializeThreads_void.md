# CRdpUdpLocalEndpoint::InitializeThreads(void)

- ea: `0x1801361f4`
- end: `0x18013630a`
- name: `?InitializeThreads@CRdpUdpLocalEndpoint@@IEAAJXZ`
- size: `278`
- prototype: `__int64 __fastcall(CRdpUdpLocalEndpoint *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180135350`

## callees

- `0x1800018a4`
- `0x1801361f4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1801362f5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1801362f5`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180136237`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180136237`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013624d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013624d`

## string_xrefs

- `0x1801362a2`: `Failed to create thread`
- `0x180136271`: `InitializeThreads`

## pseudocode

```c
__int64 __fastcall CRdpUdpLocalEndpoint::InitializeThreads(CRdpUdpLocalEndpoint *this)
{
  HANDLE Thread; // rax
  signed int LastError; // eax
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d
  unsigned int v7; // ebx
  const char *v9; // [rsp+50h] [rbp-18h] BYREF
  int v10; // [rsp+70h] [rbp+8h] BYREF
  unsigned int v11; // [rsp+78h] [rbp+10h] BYREF
  const char *v12; // [rsp+80h] [rbp+18h] BYREF
  const char *v13; // [rsp+88h] [rbp+20h] BYREF

  if ( *((_QWORD *)this + 62) )
  {
    return 1;
  }
  else
  {
    *((_DWORD *)this + 120) = 0;
    Thread = CreateThread(0, 0, CRdpUdpLocalEndpoint::STATIC_UdpLocalEndpointThread, this, 0x60u, (LPDWORD)this + 126);
    *((_QWORD *)this + 62) = Thread;
    if ( Thread )
    {
      v7 = 0;
      SetThreadPriority(Thread, 15);
    }
    else
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      if ( (unsigned int)CallbackContext > 2 )
      {
        v10 = 150;
        v12 = "InitializeThreads";
        v11 = v7;
        v13 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudplocalendpoint.cpp";
        v9 = "Failed to create thread";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v4,
          (unsigned int)word_1801D4A72,
          v5,
          v6,
          (__int64)&v9,
          (__int64)&v11,
          (__int64)&v13,
          (__int64)&v10,
          (__int64)&v12);
      }
    }
  }
  return v7;
}

```

## disassembly

```asm
0x1801361f4  push    rbx
0x1801361f6  sub     rsp, 60h
0x1801361fa  cmp     qword ptr [rcx+1F0h], 0
0x180136202  mov     rbx, rcx
0x180136205  jnz     loc_1801362FD
0x18013620b  lea     rax, [rcx+1F8h]
0x180136212  mov     dword ptr [rcx+1E0h], 0
0x18013621c  mov     r9, rcx; lpParameter
0x18013621f  mov     [rsp+68h+lpThreadId], rax; lpThreadId
0x180136224  lea     r8, ?STATIC_UdpLocalEndpointThread@CRdpUdpLocalEndpoint@@KAKPEAX@Z; lpStartAddress
0x18013622b  mov     [rsp+68h+dwCreationFlags], 60h ; '`'; dwCreationFlags
0x180136233  xor     edx, edx; dwStackSize
0x180136235  xor     ecx, ecx; lpThreadAttributes
0x180136237  call    cs:__imp_CreateThread
0x18013623d  mov     [rbx+1F0h], rax
0x180136244  test    rax, rax
0x180136247  jnz     loc_1801362ED
0x18013624d  call    cs:__imp_GetLastError
0x180136253  mov     ebx, eax
0x180136255  test    eax, eax
0x180136257  jle     short loc_180136262
0x180136259  movzx   ebx, ax
0x18013625c  or      ebx, 80070000h
0x180136262  mov     eax, cs:CallbackContext
0x180136268  cmp     eax, 2
0x18013626b  jbe     loc_180136302
0x180136271  lea     rax, aInitializethre; "InitializeThreads"
0x180136278  mov     [rsp+68h+arg_0], 96h
0x180136280  mov     [rsp+68h+arg_10], rax
0x180136288  lea     rdx, word_1801D4A72
0x18013628f  lea     rax, aOnecoreTermsrv_26; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180136296  mov     [rsp+68h+arg_8], ebx
0x18013629a  mov     [rsp+68h+arg_18], rax
0x1801362a2  lea     rax, aFailedToCreate_27; "Failed to create thread"
0x1801362a9  mov     [rsp+68h+var_18], rax
0x1801362ae  lea     rax, [rsp+68h+arg_10]
0x1801362b6  mov     [rsp+68h+var_28], rax
0x1801362bb  lea     rax, [rsp+68h+arg_0]
0x1801362c0  mov     [rsp+68h+var_30], rax
0x1801362c5  lea     rax, [rsp+68h+arg_18]
0x1801362cd  mov     [rsp+68h+var_38], rax
0x1801362d2  lea     rax, [rsp+68h+arg_8]
0x1801362d7  mov     [rsp+68h+lpThreadId], rax
0x1801362dc  lea     rax, [rsp+68h+var_18]
0x1801362e1  mov     qword ptr [rsp+68h+dwCreationFlags], rax
0x1801362e6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1801362eb  jmp     short loc_180136302
0x1801362ed  xor     ebx, ebx
0x1801362ef  mov     rcx, rax; hThread
0x1801362f2  lea     edx, [rbx+0Fh]; nPriority
0x1801362f5  call    cs:__imp_SetThreadPriority
0x1801362fb  jmp     short loc_180136302
0x1801362fd  mov     ebx, 1
0x180136302  mov     eax, ebx
0x180136304  add     rsp, 60h
0x180136308  pop     rbx
0x180136309  retn
```
