# RdpRemoteAppGfxRedirectContainerSharedMemory::CreateFileMappingW(ulong,void * *)

- ea: `0x180013210`
- end: `0x180013348`
- name: `?CreateFileMappingW@RdpRemoteAppGfxRedirectContainerSharedMemory@@UEAAJKPEAPEAX@Z`
- size: `312`
- prototype: `__int64 __fastcall(RdpRemoteAppGfxRedirectionHandler **this, unsigned int, const char **)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callees

- `0x180001724`
- `0x180013210`
- `0x180015a60`
- `0x1800196a4`
- `0x18001e248`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18001323a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18001323a`

## string_xrefs

- `0x1800132c4`: `CreateFileMappingW`
- `0x1800132ab`: `Failed to create VM shared memory section`

## pseudocode

```c
__int64 __fastcall RdpRemoteAppGfxRedirectContainerSharedMemory::CreateFileMappingW(
        RdpRemoteAppGfxRedirectionHandler **this,
        unsigned int a2,
        const char **a3)
{
  __int64 v6; // rdx
  int CurrentMsTime; // eax
  int v8; // r14d
  __int64 v9; // r8
  __int64 v10; // rdx
  int v11; // ecx
  int v12; // ebx
  int v13; // r8d
  int v14; // r9d
  int v15; // eax
  unsigned int v16; // edx
  const char *v18; // [rsp+50h] [rbp-20h] BYREF
  const char *v19; // [rsp+58h] [rbp-18h] BYREF
  const char *v20; // [rsp+60h] [rbp-10h] BYREF
  const char *v21; // [rsp+68h] [rbp-8h] BYREF
  __int64 v22; // [rsp+A0h] [rbp+30h] BYREF
  int v23; // [rsp+A8h] [rbp+38h] BYREF
  LARGE_INTEGER Frequency; // [rsp+B8h] [rbp+48h] BYREF

  v18 = 0;
  Frequency.QuadPart = 0;
  QueryPerformanceFrequency(&Frequency);
  CurrentMsTime = RDSDWMDirectTraceLogging::GetCurrentMsTime((RDSDWMDirectTraceLogging *)Frequency.QuadPart, v6);
  v22 = a2;
  v8 = CurrentMsTime;
  v12 = CreateVmSharedMemorySection((void **)&v18, (__int64)(this + 66), v9, &v22) | 0x10000000;
  if ( this[68] )
  {
    v15 = RDSDWMDirectTraceLogging::GetCurrentMsTime((RDSDWMDirectTraceLogging *)Frequency.QuadPart, v10);
    RdpRemoteAppGfxRedirectionHandler::OnSharedMemorySectionCreated(this[68], v16, v15 - v8, v12);
  }
  if ( v12 >= 0 )
  {
    *a3 = v18;
  }
  else
  {
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v23 = 124;
      v18 = "Failed to create VM shared memory section";
      LODWORD(v22) = v12;
      v19 = "CreateFileMappingW";
      v20 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
      v21 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v11,
        (unsigned int)word_18003D7E2,
        v13,
        v14,
        (__int64)&v21,
        (__int64)&v22,
        (__int64)&v20,
        (__int64)&v23,
        (__int64)&v19,
        (__int64)&v18);
    }
    dword_180044134 = 1;
    return (unsigned int)-2147483638;
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180013210  push    rbp
0x180013212  push    rbx
0x180013213  push    rsi
0x180013214  push    rdi
0x180013215  push    r14
0x180013217  mov     rbp, rsp
0x18001321a  sub     rsp, 70h
0x18001321e  mov     rdi, rcx
0x180013221  mov     [rbp+var_20], 0
0x180013229  lea     rcx, [rbp+Frequency]; lpFrequency
0x18001322d  mov     qword ptr [rbp+Frequency], 0
0x180013235  mov     rsi, r8
0x180013238  mov     ebx, edx
0x18001323a  call    cs:__imp_QueryPerformanceFrequency
0x180013240  mov     rcx, qword ptr [rbp+Frequency]; this
0x180013244  call    ?GetCurrentMsTime@RDSDWMDirectTraceLogging@@YA_J_J@Z; RDSDWMDirectTraceLogging::GetCurrentMsTime(__int64)
0x180013249  lea     rdx, [rdi+210h]
0x180013250  mov     [rbp+arg_4], 0
0x180013257  lea     r9, [rbp+arg_0]
0x18001325b  mov     [rbp+arg_0], ebx
0x18001325e  lea     rcx, [rbp+var_20]
0x180013262  mov     r14, rax
0x180013265  call    CreateVmSharedMemorySection
0x18001326a  mov     ebx, eax
0x18001326c  bts     ebx, 1Ch
0x180013270  cmp     qword ptr [rdi+220h], 0
0x180013278  jz      short loc_180013298
0x18001327a  mov     rcx, qword ptr [rbp+Frequency]; this
0x18001327e  call    ?GetCurrentMsTime@RDSDWMDirectTraceLogging@@YA_J_J@Z; RDSDWMDirectTraceLogging::GetCurrentMsTime(__int64)
0x180013283  mov     rcx, [rdi+220h]; this
0x18001328a  sub     eax, r14d
0x18001328d  mov     r8d, eax; unsigned int
0x180013290  mov     r9d, ebx; int
0x180013293  call    ?OnSharedMemorySectionCreated@RdpRemoteAppGfxRedirectionHandler@@QEAAXIIJ@Z; RdpRemoteAppGfxRedirectionHandler::OnSharedMemorySectionCreated(uint,uint,long)
0x180013298  test    ebx, ebx
0x18001329a  jns     loc_180013334
0x1800132a0  mov     eax, cs:dword_180044008
0x1800132a6  cmp     eax, 2
0x1800132a9  jbe     short loc_180013323
0x1800132ab  lea     rax, aFailedToCreate; "Failed to create VM shared memory secti"...
0x1800132b2  mov     [rbp+arg_8], 7Ch ; '|'
0x1800132b9  mov     [rbp+var_20], rax
0x1800132bd  lea     rdx, word_18003D7E2
0x1800132c4  lea     rax, aCreatefilemapp; "CreateFileMappingW"
0x1800132cb  mov     [rbp+arg_0], ebx
0x1800132ce  mov     [rbp+var_18], rax
0x1800132d2  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x1800132d9  mov     [rbp+var_10], rax
0x1800132dd  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800132e4  mov     [rbp+var_8], rax
0x1800132e8  lea     rax, [rbp+var_20]
0x1800132ec  mov     [rsp+70h+var_28], rax
0x1800132f1  lea     rax, [rbp+var_18]
0x1800132f5  mov     [rsp+70h+var_30], rax
0x1800132fa  lea     rax, [rbp+arg_8]
0x1800132fe  mov     [rsp+70h+var_38], rax
0x180013303  lea     rax, [rbp+var_10]
0x180013307  mov     [rsp+70h+var_40], rax
0x18001330c  lea     rax, [rbp+arg_0]
0x180013310  mov     [rsp+70h+var_48], rax
0x180013315  lea     rax, [rbp+var_8]
0x180013319  mov     [rsp+70h+var_50], rax
0x18001331e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180013323  mov     cs:dword_180044134, 1
0x18001332d  mov     ebx, 8000000Ah
0x180013332  jmp     short loc_18001333B
0x180013334  mov     rcx, [rbp+var_20]
0x180013338  mov     [rsi], rcx
0x18001333b  mov     eax, ebx
0x18001333d  add     rsp, 70h
0x180013341  pop     r14
0x180013343  pop     rdi
0x180013344  pop     rsi
0x180013345  pop     rbx
0x180013346  pop     rbp
0x180013347  retn
```
