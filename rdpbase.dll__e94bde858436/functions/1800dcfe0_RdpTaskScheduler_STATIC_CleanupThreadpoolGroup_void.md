# RdpTaskScheduler::STATIC_CleanupThreadpoolGroup(void *)

- ea: `0x1800dcfe0`
- end: `0x1800dd09c`
- name: `?STATIC_CleanupThreadpoolGroup@RdpTaskScheduler@@KAKPEAX@Z`
- size: `188`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task`

## callees

- `0x1800018a4`
- `0x180078820`
- `0x1800dcfe0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x1800dd095`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x1800dd095`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x1800dd082`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x1800dd082`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x1800dd078`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x1800dd078`

## string_xrefs

- `0x1800dd016`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x1800dd029`: `STATIC_CleanupThreadpoolGroup: invalid context pointer`
- `0x1800dcffc`: `STATIC_CleanupThreadpoolGroup`

## pseudocode

```c
__int64 __fastcall RdpTaskScheduler::STATIC_CleanupThreadpoolGroup(PVOID Parameter, __int64 a2, int a3, int a4)
{
  PTP_CLEANUP_GROUP v6; // rbx
  const char *v7; // [rsp+50h] [rbp-28h] BYREF
  int v8; // [rsp+80h] [rbp+8h] BYREF
  int v9; // [rsp+88h] [rbp+10h] BYREF
  const char *v10; // [rsp+90h] [rbp+18h] BYREF
  const char *v11; // [rsp+98h] [rbp+20h] BYREF

  if ( Parameter )
  {
    v6 = *(PTP_CLEANUP_GROUP *)Parameter;
    CloseThreadpoolCleanupGroupMembers(*((PTP_CLEANUP_GROUP *)Parameter + 1), *((_DWORD *)Parameter + 4), 0);
    CloseThreadpoolCleanupGroup(*((PTP_CLEANUP_GROUP *)Parameter + 1));
    operator delete(Parameter);
    FreeLibraryAndExitThread((HMODULE)v6, 0);
  }
  if ( (unsigned int)CallbackContext > 2 )
  {
    v8 = 320;
    v10 = "STATIC_CleanupThreadpoolGroup";
    v9 = -2147467261;
    v11 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdptaskscheduler.cpp";
    v7 = "STATIC_CleanupThreadpoolGroup: invalid context pointer";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      0,
      (unsigned int)&byte_1801BC24F,
      a3,
      a4,
      (__int64)&v7,
      (__int64)&v9,
      (__int64)&v11,
      (__int64)&v8,
      (__int64)&v10);
  }
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x1800dcfe0  mov     r11, rsp
0x1800dcfe3  push    rbx
0x1800dcfe4  push    rdi
0x1800dcfe5  sub     rsp, 68h
0x1800dcfe9  mov     rdi, rcx
0x1800dcfec  test    rcx, rcx
0x1800dcfef  jnz     short loc_1800DD06B
0x1800dcff1  mov     eax, cs:CallbackContext
0x1800dcff7  cmp     eax, 2
0x1800dcffa  jbe     short loc_1800DD061
0x1800dcffc  lea     rax, aStaticCleanupt; "STATIC_CleanupThreadpoolGroup"
0x1800dd003  mov     dword ptr [r11+8], 140h
0x1800dd00b  mov     [r11+18h], rax
0x1800dd00f  lea     rdx, byte_1801BC24F
0x1800dd016  lea     rax, aOnecoreTermsrv_52; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800dd01d  mov     dword ptr [r11+10h], 80004003h
0x1800dd025  mov     [r11+20h], rax
0x1800dd029  lea     rax, aStaticCleanupt_0; "STATIC_CleanupThreadpoolGroup: invalid "...
0x1800dd030  mov     [r11-28h], rax
0x1800dd034  lea     rax, [r11+18h]
0x1800dd038  mov     [r11-38h], rax
0x1800dd03c  lea     rax, [r11+8]
0x1800dd040  mov     [r11-40h], rax
0x1800dd044  lea     rax, [r11+20h]
0x1800dd048  mov     [r11-48h], rax
0x1800dd04c  lea     rax, [r11+10h]
0x1800dd050  mov     [r11-50h], rax
0x1800dd054  lea     rax, [r11-28h]
0x1800dd058  mov     [r11-58h], rax
0x1800dd05c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800dd061  or      eax, 0FFFFFFFFh
0x1800dd064  add     rsp, 68h
0x1800dd068  pop     rdi
0x1800dd069  pop     rbx
0x1800dd06a  retn
0x1800dd06b  mov     rbx, [rcx]
0x1800dd06e  xor     r8d, r8d; pvCleanupContext
0x1800dd071  mov     edx, [rcx+10h]; fCancelPendingCallbacks
0x1800dd074  mov     rcx, [rcx+8]; ptpcg
0x1800dd078  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x1800dd07e  mov     rcx, [rdi+8]; ptpcg
0x1800dd082  call    cs:__imp_CloseThreadpoolCleanupGroup
0x1800dd088  mov     rcx, rdi; Block
0x1800dd08b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800dd090  xor     edx, edx; dwExitCode
0x1800dd092  mov     rcx, rbx; hLibModule
0x1800dd095  call    cs:__imp_FreeLibraryAndExitThread
```
