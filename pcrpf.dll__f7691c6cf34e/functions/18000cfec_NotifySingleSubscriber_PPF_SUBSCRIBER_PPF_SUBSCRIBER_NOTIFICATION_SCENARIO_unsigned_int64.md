# NotifySingleSubscriber(PPF_SUBSCRIBER *,PPF_SUBSCRIBER_NOTIFICATION_SCENARIO,unsigned __int64)

- ea: `0x18000cfec`
- end: `0x18000d1e2`
- name: `?NotifySingleSubscriber@@YAJPEAUPPF_SUBSCRIBER@@W4PPF_SUBSCRIBER_NOTIFICATION_SCENARIO@@_K@Z`
- size: `502`
- prototype: `__int64 __fastcall(_QWORD *, unsigned int, unsigned __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, installer_update`

## callers

- `0x18000d1e8`

## callees

- `0x180003270`
- `0x18000c458`
- `0x18000c5cc`
- `0x18000ca1c`
- `0x18000cfec`
- `0x18000df64`
- `0x18000dfa0`
- `0x18000e008`
- `0x18000e260`
- `0x18002d5ec`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d0ee`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d0ee`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000d12c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000d192`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000d12c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000d192`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000d0a1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000d0a1`

## string_xrefs

- `0x18000d076`: `Notifying subscriber %ws, dll %ws, function %s`
- `0x18000d089`: `onecore\base\ngscb\pcrpf\dll\subscribers.cpp`
- `0x18000d0d1`: `onecore\base\ngscb\pcrpf\dll\subscribers.cpp`
- `0x18000d116`: `onecore\base\ngscb\pcrpf\dll\subscribers.cpp`
- `0x18000d171`: `onecore\base\ngscb\pcrpf\dll\subscribers.cpp`
- `0x18000d162`: `Subscriber PredictionsUpdated function failed`

## pseudocode

```c
__int64 __fastcall NotifySingleSubscriber(_QWORD *a1, unsigned int a2, unsigned __int64 a3)
{
  HMODULE Library; // rax
  HMODULE v7; // rbx
  int LastErrorMsg; // edi
  FARPROC ProcAddress; // rax
  char *v11; // [rsp+28h] [rbp-D8h]
  unsigned __int64 v12; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v13; // [rsp+50h] [rbp-B0h]
  int v14; // [rsp+54h] [rbp-ACh]
  _QWORD v15[42]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v15,
    "NotifySingleSubscriberActivity");
  v15[0] = &PpfTraceLoggingProvider::NotifySingleSubscriberActivity::`vftable';
  PpfTraceLoggingProvider::NotifySingleSubscriberActivity::StartActivity(
    (PpfTraceLoggingProvider::NotifySingleSubscriberActivity *)v15,
    (const unsigned __int16 *)*a1,
    (const unsigned __int16 *)a1[1],
    (const char *)a1[2],
    a2,
    a3);
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\dll\\subscribers.cpp",
    0x20u,
    "NotifySingleSubscriber",
    "Notifying subscriber %ws, dll %ws, function %s",
    *a1,
    a1[1],
    a1[2]);
  Library = LoadLibraryExW((LPCWSTR)a1[1], 0, 0x800u);
  v7 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, (LPCSTR)a1[2]);
    if ( ProcAddress )
    {
      v14 = 0;
      v13 = a2;
      v12 = a3;
      LastErrorMsg = ((__int64 (__fastcall *)(unsigned __int64 *))ProcAddress)(&v12);
      if ( LastErrorMsg >= 0 )
      {
        wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v15);
        FreeLibrary(v7);
        LastErrorMsg = 0;
        goto LABEL_9;
      }
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x2B,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\subscribers.cpp",
        (const char *)(unsigned int)LastErrorMsg,
        (int)"Subscriber PredictionsUpdated function failed",
        v11);
    }
    else
    {
      LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                       retaddr,
                       (void *)0x26,
                       (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\subscribers.cpp",
                       "Subscriber function %hs failed to load",
                       (const char *)a1[2]);
    }
    FreeLibrary(v7);
  }
  else
  {
    LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                     retaddr,
                     (void *)0x23,
                     (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\subscribers.cpp",
                     "Subscriber module %ws failed to load",
                     (const char *)a1[1]);
  }
LABEL_9:
  v15[0] = &PpfTraceLoggingProvider::NotifySingleSubscriberActivity::`vftable';
  wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v15);
  wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v15);
  return (unsigned int)LastErrorMsg;
}

```

## disassembly

```asm
0x18000cfec  mov     [rsp-8+arg_18], rbx
0x18000cff1  push    rbp
0x18000cff2  push    rsi
0x18000cff3  push    rdi
0x18000cff4  push    r12
0x18000cff6  push    r14
0x18000cff8  lea     rbp, [rsp-0C0h]
0x18000d000  sub     rsp, 1C0h
0x18000d007  mov     rax, cs:__security_cookie
0x18000d00e  xor     rax, rsp
0x18000d011  mov     [rbp+0E0h+var_30], rax
0x18000d018  mov     r14, r8
0x18000d01b  mov     esi, edx
0x18000d01d  mov     rdi, rcx
0x18000d020  lea     rdx, aNotifysinglesu; "NotifySingleSubscriberActivity"
0x18000d027  lea     rcx, [rsp+1E0h+var_180]
0x18000d02c  call    ??0?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000d031  lea     r12, ??_7NotifySingleSubscriberActivity@PpfTraceLoggingProvider@@6B@; const PpfTraceLoggingProvider::NotifySingleSubscriberActivity::`vftable'
0x18000d038  mov     [rsp+1E0h+var_180], r12
0x18000d03d  mov     [rsp+1E0h+var_1B8], r14; unsigned __int64
0x18000d042  mov     dword ptr [rsp+1E0h+var_1C0], esi; unsigned int
0x18000d046  mov     r9, [rdi+10h]; char *
0x18000d04a  mov     r8, [rdi+8]; unsigned __int16 *
0x18000d04e  mov     rdx, [rdi]; unsigned __int16 *
0x18000d051  lea     rcx, [rsp+1E0h+var_180]; this
0x18000d056  call    ?StartActivity@NotifySingleSubscriberActivity@PpfTraceLoggingProvider@@QEAAXPEBG0PEBDI_K@Z; PpfTraceLoggingProvider::NotifySingleSubscriberActivity::StartActivity(ushort const *,ushort const *,char const *,uint,unsigned __int64)
0x18000d05b  nop
0x18000d05c  mov     rax, [rdi+10h]
0x18000d060  mov     [rsp+1E0h+var_1B0], rax
0x18000d065  mov     rax, [rdi+8]
0x18000d069  mov     [rsp+1E0h+var_1B8], rax; char *
0x18000d06e  mov     rax, [rdi]
0x18000d071  mov     [rsp+1E0h+var_1C0], rax
0x18000d076  lea     r9, aNotifyingSubsc_0; "Notifying subscriber %ws, dll %ws, func"...
0x18000d07d  lea     r8, aNotifysinglesu_0; "NotifySingleSubscriber"
0x18000d084  mov     edx, 20h ; ' '; unsigned int
0x18000d089  lea     rcx, aOnecoreBaseNgs_0; "onecore\\base\\ngscb\\pcrpf\\dll\\subsc"...
0x18000d090  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18000d095  xor     edx, edx; hFile
0x18000d097  mov     r8d, 800h; dwFlags
0x18000d09d  mov     rcx, [rdi+8]; lpLibFileName
0x18000d0a1  call    cs:__imp_LoadLibraryExW
0x18000d0a8  nop     dword ptr [rax+rax+00h]
0x18000d0ad  mov     rbx, rax
0x18000d0b0  mov     [rsp+1E0h+var_1A0], rax
0x18000d0b5  test    rax, rax
0x18000d0b8  jnz     short loc_18000D0E7
0x18000d0ba  mov     rcx, [rbp+0E8h]; this
0x18000d0c1  mov     rax, [rdi+8]
0x18000d0c5  mov     [rsp+1E0h+var_1C0], rax; char *
0x18000d0ca  lea     r9, aSubscriberModu; "Subscriber module %ws failed to load"
0x18000d0d1  lea     r8, aOnecoreBaseNgs_0; "onecore\\base\\ngscb\\pcrpf\\dll\\subsc"...
0x18000d0d8  lea     edx, [rbx+23h]; void *
0x18000d0db  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18000d0e0  mov     edi, eax
0x18000d0e2  jmp     loc_18000D1A0
0x18000d0e7  mov     rdx, [rdi+10h]; lpProcName
0x18000d0eb  mov     rcx, rbx; hModule
0x18000d0ee  call    cs:__imp_GetProcAddress
0x18000d0f5  nop     dword ptr [rax+rax+00h]
0x18000d0fa  test    rax, rax
0x18000d0fd  jnz     short loc_18000D13A
0x18000d0ff  mov     rcx, [rbp+0E8h]; this
0x18000d106  mov     rax, [rdi+10h]
0x18000d10a  mov     [rsp+1E0h+var_1C0], rax; char *
0x18000d10f  lea     r9, aSubscriberFunc; "Subscriber function %hs failed to load"
0x18000d116  lea     r8, aOnecoreBaseNgs_0; "onecore\\base\\ngscb\\pcrpf\\dll\\subsc"...
0x18000d11d  mov     edx, 26h ; '&'; void *
0x18000d122  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18000d127  mov     edi, eax
0x18000d129  mov     rcx, rbx; hLibModule
0x18000d12c  call    cs:__imp_FreeLibrary
0x18000d133  nop     dword ptr [rax+rax+00h]
0x18000d138  jmp     short loc_18000D1A0
0x18000d13a  mov     [rsp+1E0h+var_18C], 0
0x18000d142  mov     [rsp+1E0h+var_190], esi
0x18000d146  mov     [rsp+1E0h+var_198], r14
0x18000d14b  lea     rcx, [rsp+1E0h+var_198]
0x18000d150  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d155  mov     edi, eax
0x18000d157  test    eax, eax
0x18000d159  jns     short loc_18000D184
0x18000d15b  mov     rcx, [rbp+0E8h]; this
0x18000d162  lea     rax, aSubscriberPred; "Subscriber PredictionsUpdated function "...
0x18000d169  mov     [rsp+1E0h+var_1C0], rax; int
0x18000d16e  mov     r9d, edi; char *
0x18000d171  lea     r8, aOnecoreBaseNgs_0; "onecore\\base\\ngscb\\pcrpf\\dll\\subsc"...
0x18000d178  mov     edx, 2Bh ; '+'; void *
0x18000d17d  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000d182  jmp     short loc_18000D129
0x18000d184  lea     rcx, [rsp+1E0h+var_180]
0x18000d189  call    ?Stop@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18000d18e  nop
0x18000d18f  mov     rcx, rbx; hLibModule
0x18000d192  call    cs:__imp_FreeLibrary
0x18000d199  nop     dword ptr [rax+rax+00h]
0x18000d19e  xor     edi, edi
0x18000d1a0  mov     [rsp+1E0h+var_180], r12
0x18000d1a5  lea     rcx, [rsp+1E0h+var_180]
0x18000d1aa  call    ?Destroy@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18000d1af  lea     rcx, [rsp+1E0h+var_180]
0x18000d1b4  call    ??1?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000d1b9  mov     eax, edi
0x18000d1bb  mov     rcx, [rbp+0E0h+var_30]
0x18000d1c2  xor     rcx, rsp; StackCookie
0x18000d1c5  call    __security_check_cookie
0x18000d1ca  mov     rbx, [rsp+1E0h+arg_18]
0x18000d1d2  add     rsp, 1C0h
0x18000d1d9  pop     r14
0x18000d1db  pop     r12
0x18000d1dd  pop     rdi
0x18000d1de  pop     rsi
0x18000d1df  pop     rbp
0x18000d1e0  retn
```
