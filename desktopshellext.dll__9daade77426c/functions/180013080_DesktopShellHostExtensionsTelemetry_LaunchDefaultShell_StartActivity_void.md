# DesktopShellHostExtensionsTelemetry::LaunchDefaultShell::StartActivity(void)

- ea: `0x180013080`
- end: `0x18001328e`
- name: `?StartActivity@LaunchDefaultShell@DesktopShellHostExtensionsTelemetry@@QEAAXXZ`
- size: `526`
- prototype: `void __fastcall(DesktopShellHostExtensionsTelemetry::LaunchDefaultShell *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800201d4`

## callees

- `0x18000b8f0`
- `0x18000cad8`
- `0x18000e83c`
- `0x180013080`
- `0x18002a3d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800130bf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800130bf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800130d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800130ed`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013151`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800130d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800130ed`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013151`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001318b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001318b`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180013259`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180013259`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180013134`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180013134`

## pseudocode

```c
void __fastcall DesktopShellHostExtensionsTelemetry::LaunchDefaultShell::StartActivity(
        DesktopShellHostExtensionsTelemetry::LaunchDefaultShell *this)
{
  RTL_SRWLOCK *v2; // rbx
  RTL_SRWLOCK *v3; // rbx
  __int64 v4; // rsi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // rbx
  __int64 v7; // r8
  const GUID *v8; // r9
  PSRWLOCK v9; // [rsp+38h] [rbp-51h] BYREF
  __int64 v10; // [rsp+40h] [rbp-49h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-41h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-29h] BYREF
  __int16 *v13; // [rsp+70h] [rbp-19h]
  int v14; // [rsp+78h] [rbp-11h]
  int v15; // [rsp+7Ch] [rbp-Dh]
  __int64 *v16; // [rsp+80h] [rbp-9h]
  __int64 v17; // [rsp+88h] [rbp-1h]
  PSRWLOCK *v18; // [rsp+90h] [rbp+7h]
  __int64 v19; // [rsp+98h] [rbp+Fh]

  v2 = (RTL_SRWLOCK *)*((_QWORD *)this + 35);
  if ( v2 )
  {
    v3 = v2 + 33;
    AcquireSRWLockExclusive(v3);
  }
  else
  {
    v9 = 0;
    v3 = 0;
  }
  v4 = *((_QWORD *)this + 34);
  v5 = DesktopShellHostExtensionsLogging::Provider();
  if ( *(_DWORD *)v5 > 5u
    && (*((_QWORD *)v5 + 2) & 0x400000000000LL) != 0
    && (*((_QWORD *)v5 + 3) & 0x400000000000LL) == *((_QWORD *)v5 + 3) )
  {
    EventActivityIdControl(3u, (LPGUID)(v4 + 8));
  }
  else
  {
    *(_OWORD *)(v4 + 8) = 0;
  }
  *(_DWORD *)v4 = 1;
  if ( v3 )
    ReleaseSRWLockExclusive(v3);
  v6 = *((_QWORD *)DesktopShellHostExtensionsLogging::Instance() + 1);
  if ( *(_DWORD *)v6 > 5u
    && (*(_QWORD *)(v6 + 16) & 0x400000000000LL) != 0
    && (*(_QWORD *)(v6 + 24) & 0x400000000000LL) == *(_QWORD *)(v6 + 24) )
  {
    LODWORD(v9) = GetCurrentThreadId();
    v10 = 0;
    v7 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v7 + 4)
      || (v8 = (const GUID *)(v7 + 24), !*(_DWORD *)(v7 + 24))
      && !*(_DWORD *)(v7 + 28)
      && !*(_DWORD *)(v7 + 32)
      && !*(_DWORD *)(v7 + 36) )
    {
      v8 = 0;
    }
    v18 = &v9;
    v19 = 4;
    v16 = &v10;
    v17 = 8;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 261;
    EventDescriptor.Keyword = 0x400000000000LL;
    UserData.Ptr = *(_QWORD *)(v6 + 8);
    UserData.Size = *(unsigned __int16 *)UserData.Ptr;
    UserData.Reserved = 2;
    v13 = word_180099BA2;
    v14 = 62;
    v15 = 1;
    EventWriteTransfer(*(_QWORD *)(v6 + 32), &EventDescriptor, (LPCGUID)(v7 + 8), v8, 4u, &UserData);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((DesktopShellHostExtensionsTelemetry::LaunchDefaultShell *)((char *)this + 288));
}

```

## disassembly

```asm
0x180013080  push    rbp
0x180013082  push    rbx
0x180013083  push    rsi
0x180013084  push    rdi
0x180013085  push    r14
0x180013087  push    r15
0x180013089  lea     rbp, [rsp-2Fh]
0x18001308e  sub     rsp, 0B8h
0x180013095  mov     rax, cs:__security_cookie
0x18001309c  xor     rax, rsp
0x18001309f  mov     [rbp+57h+var_40], rax
0x1800130a3  mov     rdi, rcx
0x1800130a6  xor     r14d, r14d
0x1800130a9  mov     rbx, [rcx+118h]
0x1800130b0  test    rbx, rbx
0x1800130b3  jz      short loc_1800130DD
0x1800130b5  add     rbx, 108h
0x1800130bc  mov     rcx, rbx; SRWLock
0x1800130bf  call    cs:__imp_AcquireSRWLockExclusive
0x1800130c5  lea     rax, [rbp+57h+SRWLock]
0x1800130c9  mov     [rax], r14
0x1800130cc  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800130d0  test    rcx, rcx
0x1800130d3  jz      short loc_1800130F6
0x1800130d5  call    cs:__imp_ReleaseSRWLockExclusive
0x1800130db  jmp     short loc_1800130F6
0x1800130dd  lea     rax, [rbp+57h+var_A8]
0x1800130e1  mov     [rax], r14
0x1800130e4  mov     rcx, [rbp+57h+var_A8]; SRWLock
0x1800130e8  test    rcx, rcx
0x1800130eb  jz      short loc_1800130F3
0x1800130ed  call    cs:__imp_ReleaseSRWLockExclusive
0x1800130f3  mov     rbx, r14
0x1800130f6  mov     rsi, [rdi+110h]
0x1800130fd  call    ?Provider@DesktopShellHostExtensionsLogging@@SAPEBU_tlgProvider_t@@XZ; DesktopShellHostExtensionsLogging::Provider(void)
0x180013102  mov     ecx, [rax]
0x180013104  mov     r15, 400000000000h
0x18001310e  cmp     ecx, 5
0x180013111  jbe     short loc_18001313C
0x180013113  mov     rcx, [rax+18h]
0x180013117  mov     rax, [rax+10h]
0x18001311b  test    r15, rax
0x18001311e  jz      short loc_18001313C
0x180013120  mov     rax, rcx
0x180013123  and     rax, r15
0x180013126  cmp     rax, rcx
0x180013129  jnz     short loc_18001313C
0x18001312b  lea     rdx, [rsi+8]; ActivityId
0x18001312f  mov     ecx, 3; ControlCode
0x180013134  call    cs:__imp_EventActivityIdControl
0x18001313a  jmp     short loc_180013143
0x18001313c  xorps   xmm0, xmm0
0x18001313f  movups  xmmword ptr [rsi+8], xmm0
0x180013143  mov     dword ptr [rsi], 1
0x180013149  test    rbx, rbx
0x18001314c  jz      short loc_180013157
0x18001314e  mov     rcx, rbx; SRWLock
0x180013151  call    cs:__imp_ReleaseSRWLockExclusive
0x180013157  call    ?Instance@DesktopShellHostExtensionsLogging@@KAPEAV1@XZ; DesktopShellHostExtensionsLogging::Instance(void)
0x18001315c  mov     rbx, [rax+8]
0x180013160  mov     eax, [rbx]
0x180013162  cmp     eax, 5
0x180013165  jbe     loc_18001325F
0x18001316b  mov     rcx, [rbx+18h]
0x18001316f  mov     rax, [rbx+10h]
0x180013173  test    r15, rax
0x180013176  jz      loc_18001325F
0x18001317c  mov     rax, rcx
0x18001317f  and     rax, r15
0x180013182  cmp     rax, rcx
0x180013185  jnz     loc_18001325F
0x18001318b  call    cs:__imp_GetCurrentThreadId
0x180013191  mov     dword ptr [rbp+57h+var_A8], eax
0x180013194  mov     [rbp+57h+var_A0], r14
0x180013198  mov     r8, [rdi+110h]
0x18001319f  cmp     [r8+4], r14b
0x1800131a3  jz      short loc_1800131C0
0x1800131a5  lea     r9, [r8+18h]
0x1800131a9  cmp     [r9], r14d
0x1800131ac  jnz     short loc_1800131C3
0x1800131ae  cmp     [r9+4], r14d
0x1800131b2  jnz     short loc_1800131C3
0x1800131b4  cmp     [r9+8], r14d
0x1800131b8  jnz     short loc_1800131C3
0x1800131ba  cmp     [r9+0Ch], r14d
0x1800131be  jnz     short loc_1800131C3
0x1800131c0  mov     r9, r14; RelatedActivityId
0x1800131c3  lea     rax, [rbp+57h+var_A8]
0x1800131c7  mov     [rbp+57h+var_50], rax
0x1800131cb  mov     [rbp+57h+var_48], 4
0x1800131d3  lea     rax, [rbp+57h+var_A0]
0x1800131d7  mov     [rbp+57h+var_60], rax
0x1800131db  mov     [rbp+57h+var_58], 8
0x1800131e3  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x1800131ea  movzx   eax, cs:word_180099B98
0x1800131f1  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x1800131f4  mov     [rbp+57h+EventDescriptor.Keyword], r15
0x1800131f8  mov     rax, [rbx+8]
0x1800131fc  mov     [rbp+57h+var_80.Ptr], rax
0x180013200  movzx   eax, word ptr [rax]
0x180013203  mov     [rbp+57h+var_80.Size], eax
0x180013206  mov     dword ptr [rbp+57h+var_80.0Ch], 2
0x18001320d  lea     rax, word_180099BA2
0x180013214  mov     [rbp+57h+var_70], rax
0x180013218  mov     [rbp+57h+var_68], 3Eh ; '>'
0x18001321f  mov     [rbp+57h+var_64], 1
0x180013226  lea     rax, _TraceLoggingMetadataEnd
0x18001322d  lea     rcx, _TraceLoggingMetadata
0x180013234  sub     eax, ecx
0x180013236  mov     dword ptr [rbp+57h+SRWLock], eax
0x180013239  mov     eax, dword ptr [rbp+57h+SRWLock]
0x18001323c  add     r8, 8; ActivityId
0x180013240  lea     rax, [rbp+57h+var_80]
0x180013244  mov     [rsp+0E0h+UserData], rax; UserData
0x180013249  mov     [rsp+0E0h+UserDataCount], 4; UserDataCount
0x180013251  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x180013255  mov     rcx, [rbx+20h]; RegHandle
0x180013259  call    cs:__imp_EventWriteTransfer
0x18001325f  lea     rcx, [rdi+120h]; this
0x180013266  cmp     [rcx+18h], r14d
0x18001326a  jnz     short loc_180013272
0x18001326c  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180013271  nop
0x180013272  mov     rcx, [rbp+57h+var_40]
0x180013276  xor     rcx, rsp; StackCookie
0x180013279  call    __security_check_cookie
0x18001327e  add     rsp, 0B8h
0x180013285  pop     r15
0x180013287  pop     r14
0x180013289  pop     rdi
0x18001328a  pop     rsi
0x18001328b  pop     rbx
0x18001328c  pop     rbp
0x18001328d  retn
```
