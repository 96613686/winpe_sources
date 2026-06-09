# NGENService::ServiceNewWork(void)

- ea: `0x18001b038`
- end: `0x18001b126`
- name: `?ServiceNewWork@NGENService@@YAJXZ`
- size: `238`
- prototype: `__int64 __fastcall(NGENService *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x1800283d0`

## callees

- `0x180003c90`
- `0x18001ac30`
- `0x18001aca8`
- `0x18001afbc`
- `0x18001b038`
- `0x18002e1d0`
- `0x1800364c0`
- `0x180037c10`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18001b10d`
- `KERNEL32!CloseHandle` at `0x18001b10d`

## string_xrefs

- `0x18001b076`: `ngenservicelock.dat`
- `0x18001b08d`: `ServiceNewWork(): Failed to acquire service lock`
- `0x18001b0d9`: `ServiceNewWork(): Failed to service to autostart\n`
- `0x18001b0e2`: `ServiceNewWork(): Service was set to autostart\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall NGENService::ServiceNewWork(NGENService *this)
{
  unsigned __int16 *v2; // rdx
  NGENService *v3; // rcx
  int started; // ebx
  wchar_t *v5; // rcx
  HKEY *v6; // rdx
  NGENService *v7; // rcx
  NGENService *v8; // rcx
  unsigned int v9; // edx
  void **v10; // [rsp+20h] [rbp-18h] BYREF
  HANDLE hObject; // [rsp+28h] [rbp-10h]

  if ( IsNgenOffline() )
    return 0;
  hObject = (HANDLE)-1LL;
  v10 = (void **)&VersionedMutexHolder::`vftable';
  started = FileLockHolder::AcquireNoThrow((FileLockHolder *)&v10, L"ngenservicelock.dat", 0, 0);
  if ( started < 0 )
  {
    v5 = L"ServiceNewWork(): Failed to acquire service lock";
LABEL_5:
    NGENService::DebugLog((NGENService *)v5, v2);
    goto LABEL_15;
  }
  if ( NGENService::g_bProcessNGENService )
  {
    started = NGENService::ControllerNotifyNewWorkAvailable(v3, (HKEY *)v2);
    if ( started < 0 )
      goto LABEL_15;
    goto LABEL_14;
  }
  started = NGENService::WaitForServiceShutdown(v3);
  if ( started >= 0 )
  {
    started = NGENService::ControllerNotifyNewWorkAvailable(v7, v6);
    if ( started >= 0 )
    {
      LOBYTE(v8) = 1;
      started = NGENService::StartServiceW(v8, 0);
      if ( started >= 0 )
      {
        started = NGENService::SetServiceStartType((NGENService *)2, v9);
        if ( started < 0 )
        {
          v5 = L"ServiceNewWork(): Failed to service to autostart\n";
          goto LABEL_5;
        }
        NGENService::DebugLog((NGENService *)L"ServiceNewWork(): Service was set to autostart\n", v2);
LABEL_14:
        started = 0;
      }
    }
  }
LABEL_15:
  v10 = &FileLockHolder::`vftable';
  if ( hObject != (HANDLE)-1LL )
  {
    CloseHandle(hObject);
    hObject = (HANDLE)-1LL;
  }
  return (unsigned int)started;
}

```

## disassembly

```asm
0x18001b038  mov     [rsp+arg_0], rbx
0x18001b03d  push    rsi
0x18001b03e  sub     rsp, 30h
0x18001b042  call    ?IsNgenOffline@@YA_NXZ; IsNgenOffline(void)
0x18001b047  test    al, al
0x18001b049  jz      short loc_18001B052
0x18001b04b  xor     eax, eax
0x18001b04d  jmp     loc_18001B11B
0x18001b052  lea     rsi, ??_7FileLockHolder@@6B@; const FileLockHolder::`vftable'
0x18001b059  mov     [rsp+38h+var_18], rsi
0x18001b05e  or      [rsp+38h+hObject], 0FFFFFFFFFFFFFFFFh
0x18001b064  lea     rax, ??_7VersionedMutexHolder@@6B@; const VersionedMutexHolder::`vftable'
0x18001b06b  mov     [rsp+38h+var_18], rax
0x18001b070  xor     r9d, r9d; int *
0x18001b073  xor     r8d, r8d; void *
0x18001b076  lea     rdx, aNgenserviceloc; "ngenservicelock.dat"
0x18001b07d  lea     rcx, [rsp+38h+var_18]; this
0x18001b082  call    ?AcquireNoThrow@FileLockHolder@@QEAAJPEBGPEAXPEAH@Z; FileLockHolder::AcquireNoThrow(ushort const *,void *,int *)
0x18001b087  mov     ebx, eax
0x18001b089  test    eax, eax
0x18001b08b  jns     short loc_18001B09B
0x18001b08d  lea     rcx, aServicenewwork_0; "ServiceNewWork(): Failed to acquire ser"...
0x18001b094  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x18001b099  jmp     short loc_18001B0FD
0x18001b09b  cmp     cs:?g_bProcessNGENService@NGENService@@3_NA, 0; bool NGENService::g_bProcessNGENService
0x18001b0a2  jnz     short loc_18001B0F0
0x18001b0a4  call    ?WaitForServiceShutdown@NGENService@@YAJXZ; NGENService::WaitForServiceShutdown(void)
0x18001b0a9  mov     ebx, eax
0x18001b0ab  test    eax, eax
0x18001b0ad  js      short loc_18001B0FD
0x18001b0af  call    ?ControllerNotifyNewWorkAvailable@NGENService@@YAJXZ; NGENService::ControllerNotifyNewWorkAvailable(void)
0x18001b0b4  mov     ebx, eax
0x18001b0b6  test    eax, eax
0x18001b0b8  js      short loc_18001B0FD
0x18001b0ba  xor     edx, edx; bool
0x18001b0bc  mov     cl, 1; this
0x18001b0be  call    ?StartServiceW@NGENService@@YAJ_N0@Z; NGENService::StartServiceW(bool,bool)
0x18001b0c3  mov     ebx, eax
0x18001b0c5  test    eax, eax
0x18001b0c7  js      short loc_18001B0FD
0x18001b0c9  mov     ecx, 2; this
0x18001b0ce  call    ?SetServiceStartType@NGENService@@YAJK@Z; NGENService::SetServiceStartType(ulong)
0x18001b0d3  mov     ebx, eax
0x18001b0d5  test    eax, eax
0x18001b0d7  jns     short loc_18001B0E2
0x18001b0d9  lea     rcx, aServicenewwork; "ServiceNewWork(): Failed to service to "...
0x18001b0e0  jmp     short loc_18001B094
0x18001b0e2  lea     rcx, aServicenewwork_1; "ServiceNewWork(): Service was set to au"...
0x18001b0e9  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x18001b0ee  jmp     short loc_18001B0FB
0x18001b0f0  call    ?ControllerNotifyNewWorkAvailable@NGENService@@YAJXZ; NGENService::ControllerNotifyNewWorkAvailable(void)
0x18001b0f5  mov     ebx, eax
0x18001b0f7  test    eax, eax
0x18001b0f9  js      short loc_18001B0FD
0x18001b0fb  xor     ebx, ebx
0x18001b0fd  mov     [rsp+38h+var_18], rsi
0x18001b102  mov     rcx, [rsp+38h+hObject]; hObject
0x18001b107  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001b10b  jz      short loc_18001B119
0x18001b10d  call    cs:__imp_CloseHandle
0x18001b113  or      [rsp+38h+hObject], 0FFFFFFFFFFFFFFFFh
0x18001b119  mov     eax, ebx
0x18001b11b  mov     rbx, [rsp+38h+arg_0]
0x18001b120  add     rsp, 30h
0x18001b124  pop     rsi
0x18001b125  retn
```
