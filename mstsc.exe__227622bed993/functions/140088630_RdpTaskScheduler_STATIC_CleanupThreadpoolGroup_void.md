# RdpTaskScheduler::STATIC_CleanupThreadpoolGroup(void *)

- ea: `0x140088630`
- end: `0x1400886ec`
- name: `?STATIC_CleanupThreadpoolGroup@RdpTaskScheduler@@KAKPEAX@Z`
- size: `188`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task`

## callees

- `0x1400019e8`
- `0x140003b08`
- `0x140088630`

## import_xrefs

- `KERNEL32!CloseThreadpoolCleanupGroup` at `0x1400886d2`
- `KERNEL32!CloseThreadpoolCleanupGroup` at `0x1400886d2`
- `KERNEL32!CloseThreadpoolCleanupGroupMembers` at `0x1400886c8`
- `KERNEL32!CloseThreadpoolCleanupGroupMembers` at `0x1400886c8`
- `KERNEL32!FreeLibraryAndExitThread` at `0x1400886e5`
- `KERNEL32!FreeLibraryAndExitThread` at `0x1400886e5`

## string_xrefs

- `0x140088666`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x140088679`: `STATIC_CleanupThreadpoolGroup: invalid context pointer`
- `0x14008864c`: `STATIC_CleanupThreadpoolGroup`

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
  if ( (unsigned int)dword_140150118 > 2 )
  {
    v8 = 320;
    v10 = "STATIC_CleanupThreadpoolGroup";
    v9 = -2147467261;
    v11 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdptaskscheduler.cpp";
    v7 = "STATIC_CleanupThreadpoolGroup: invalid context pointer";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      0,
      (unsigned int)&byte_1401418C7,
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
0x140088630  mov     r11, rsp
0x140088633  push    rbx
0x140088634  push    rdi
0x140088635  sub     rsp, 68h
0x140088639  mov     rdi, rcx
0x14008863c  test    rcx, rcx
0x14008863f  jnz     short loc_1400886BB
0x140088641  mov     eax, cs:dword_140150118
0x140088647  cmp     eax, 2
0x14008864a  jbe     short loc_1400886B1
0x14008864c  lea     rax, aStaticCleanupt; "STATIC_CleanupThreadpoolGroup"
0x140088653  mov     dword ptr [r11+8], 140h
0x14008865b  mov     [r11+18h], rax
0x14008865f  lea     rdx, byte_1401418C7
0x140088666  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x14008866d  mov     dword ptr [r11+10h], 80004003h
0x140088675  mov     [r11+20h], rax
0x140088679  lea     rax, aStaticCleanupt_0; "STATIC_CleanupThreadpoolGroup: invalid "...
0x140088680  mov     [r11-28h], rax
0x140088684  lea     rax, [r11+18h]
0x140088688  mov     [r11-38h], rax
0x14008868c  lea     rax, [r11+8]
0x140088690  mov     [r11-40h], rax
0x140088694  lea     rax, [r11+20h]
0x140088698  mov     [r11-48h], rax
0x14008869c  lea     rax, [r11+10h]
0x1400886a0  mov     [r11-50h], rax
0x1400886a4  lea     rax, [r11-28h]
0x1400886a8  mov     [r11-58h], rax
0x1400886ac  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1400886b1  or      eax, 0FFFFFFFFh
0x1400886b4  add     rsp, 68h
0x1400886b8  pop     rdi
0x1400886b9  pop     rbx
0x1400886ba  retn
0x1400886bb  mov     rbx, [rcx]
0x1400886be  xor     r8d, r8d; pvCleanupContext
0x1400886c1  mov     edx, [rcx+10h]; fCancelPendingCallbacks
0x1400886c4  mov     rcx, [rcx+8]; ptpcg
0x1400886c8  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x1400886ce  mov     rcx, [rdi+8]; ptpcg
0x1400886d2  call    cs:__imp_CloseThreadpoolCleanupGroup
0x1400886d8  mov     rcx, rdi; Block
0x1400886db  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400886e0  xor     edx, edx; dwExitCode
0x1400886e2  mov     rcx, rbx; hLibModule
0x1400886e5  call    cs:__imp_FreeLibraryAndExitThread
```
