# RdpTaskScheduler::STATIC_CleanupThreadpoolGroup(void *)

- ea: `0x14008a7a0`
- end: `0x14008a85c`
- name: `?STATIC_CleanupThreadpoolGroup@RdpTaskScheduler@@KAKPEAX@Z`
- size: `188`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task`

## callees

- `0x1400019e8`
- `0x140003b08`
- `0x14008a7a0`

## import_xrefs

- `KERNEL32!CloseThreadpoolCleanupGroup` at `0x14008a842`
- `KERNEL32!CloseThreadpoolCleanupGroup` at `0x14008a842`
- `KERNEL32!CloseThreadpoolCleanupGroupMembers` at `0x14008a838`
- `KERNEL32!CloseThreadpoolCleanupGroupMembers` at `0x14008a838`
- `KERNEL32!FreeLibraryAndExitThread` at `0x14008a855`
- `KERNEL32!FreeLibraryAndExitThread` at `0x14008a855`

## string_xrefs

- `0x14008a7d6`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x14008a7e9`: `STATIC_CleanupThreadpoolGroup: invalid context pointer`
- `0x14008a7bc`: `STATIC_CleanupThreadpoolGroup`

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
  if ( (unsigned int)dword_140152118 > 2 )
  {
    v8 = 320;
    v10 = "STATIC_CleanupThreadpoolGroup";
    v9 = -2147467261;
    v11 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdptaskscheduler.cpp";
    v7 = "STATIC_CleanupThreadpoolGroup: invalid context pointer";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      0,
      (unsigned int)&byte_1401439FF,
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
0x14008a7a0  mov     r11, rsp
0x14008a7a3  push    rbx
0x14008a7a4  push    rdi
0x14008a7a5  sub     rsp, 68h
0x14008a7a9  mov     rdi, rcx
0x14008a7ac  test    rcx, rcx
0x14008a7af  jnz     short loc_14008A82B
0x14008a7b1  mov     eax, cs:dword_140152118
0x14008a7b7  cmp     eax, 2
0x14008a7ba  jbe     short loc_14008A821
0x14008a7bc  lea     rax, aStaticCleanupt; "STATIC_CleanupThreadpoolGroup"
0x14008a7c3  mov     dword ptr [r11+8], 140h
0x14008a7cb  mov     [r11+18h], rax
0x14008a7cf  lea     rdx, byte_1401439FF
0x14008a7d6  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x14008a7dd  mov     dword ptr [r11+10h], 80004003h
0x14008a7e5  mov     [r11+20h], rax
0x14008a7e9  lea     rax, aStaticCleanupt_0; "STATIC_CleanupThreadpoolGroup: invalid "...
0x14008a7f0  mov     [r11-28h], rax
0x14008a7f4  lea     rax, [r11+18h]
0x14008a7f8  mov     [r11-38h], rax
0x14008a7fc  lea     rax, [r11+8]
0x14008a800  mov     [r11-40h], rax
0x14008a804  lea     rax, [r11+20h]
0x14008a808  mov     [r11-48h], rax
0x14008a80c  lea     rax, [r11+10h]
0x14008a810  mov     [r11-50h], rax
0x14008a814  lea     rax, [r11-28h]
0x14008a818  mov     [r11-58h], rax
0x14008a81c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14008a821  or      eax, 0FFFFFFFFh
0x14008a824  add     rsp, 68h
0x14008a828  pop     rdi
0x14008a829  pop     rbx
0x14008a82a  retn
0x14008a82b  mov     rbx, [rcx]
0x14008a82e  xor     r8d, r8d; pvCleanupContext
0x14008a831  mov     edx, [rcx+10h]; fCancelPendingCallbacks
0x14008a834  mov     rcx, [rcx+8]; ptpcg
0x14008a838  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x14008a83e  mov     rcx, [rdi+8]; ptpcg
0x14008a842  call    cs:__imp_CloseThreadpoolCleanupGroup
0x14008a848  mov     rcx, rdi; Block
0x14008a84b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14008a850  xor     edx, edx; dwExitCode
0x14008a852  mov     rcx, rbx; hLibModule
0x14008a855  call    cs:__imp_FreeLibraryAndExitThread
```
