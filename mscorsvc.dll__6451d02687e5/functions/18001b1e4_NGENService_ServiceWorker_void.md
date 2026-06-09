# NGENService::ServiceWorker(void)

- ea: `0x18001b1e4`
- end: `0x18001b33a`
- name: `?ServiceWorker@NGENService@@YAXXZ`
- size: `342`
- prototype: `void __fastcall(NGENService *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18001b340`

## callees

- `0x18000352c`
- `0x180005688`
- `0x18001a790`
- `0x18001b1e4`
- `0x18002e1d0`
- `0x18002e418`
- `0x1800364c0`
- `0x180037340`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18001b233`
- `KERNEL32!WaitForSingleObject` at `0x18001b233`
- `KERNEL32!CloseHandle` at `0x18001b308`
- `KERNEL32!CloseHandle` at `0x18001b308`

## string_xrefs

- `0x18001b2ae`: `PendingUpdate`
- `0x18001b284`: `ngenservicelock.dat`
- `0x18001b299`: `DoneWork(): Failed to acquire service lock`
- `0x18001b2d6`: `Completed all work. Shutting down.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall NGENService::ServiceWorker(NGENService *this, unsigned int a2)
{
  unsigned int v2; // edx
  char v3; // bl
  const unsigned __int16 *v4; // rdx
  const unsigned __int16 *v5; // r8
  DWORD v6; // edx
  const unsigned __int16 *v7; // r8
  unsigned __int16 *v8; // [rsp+20h] [rbp-18h] BYREF
  HANDLE hObject; // [rsp+28h] [rbp-10h]

  while ( 1 )
  {
    if ( NGENService::g_bPauseRequested )
    {
      NGENService::g_bPauseRequested = 0;
      NGENService::ServiceUpdateState((NGENService *)7, a2);
      while ( WaitForSingleObject(NGENService::g_hRestartEvent, 0x3E8u) && !NGENService::g_bStopRequested )
        ;
      if ( !NGENService::g_bStopRequested )
        NGENService::ServiceUpdateState((NGENService *)4, v2);
    }
    if ( NGENService::g_bStopRequested )
      break;
    if ( !NGENService::ControllerRun(this) )
    {
      v3 = 0;
      hObject = (HANDLE)-1LL;
      v8 = (unsigned __int16 *)&VersionedMutexHolder::`vftable';
      if ( (int)FileLockHolder::AcquireNoThrow((FileLockHolder *)&v8, L"ngenservicelock.dat", 0, 0) < 0 )
      {
        NGENService::DebugLog((NGENService *)L"DoneWork(): Failed to acquire service lock", v4);
        goto LABEL_15;
      }
      if ( (unsigned int)REGUTIL::GetLong(L"PendingUpdate", (DWORD)v4, v5, NGENService::g_hkNGENServicePersistentState) != 1 )
      {
        if ( (unsigned int)REGUTIL::GetLong(L"RootstoreDirty", v6, v7, NGENService::g_hkNGENServiceListenedState) )
          goto LABEL_15;
        NGENService::EventLog(
          0,
          (const unsigned __int16 *)4,
          0x450u,
          (unsigned int)L"Completed all work. Shutting down.\n",
          v8);
      }
      NGENService::ServiceUpdateState((NGENService *)3, v6);
      v3 = 1;
LABEL_15:
      v8 = (unsigned __int16 *)&FileLockHolder::`vftable';
      if ( hObject != (HANDLE)-1LL )
      {
        CloseHandle(hObject);
        hObject = (HANDLE)-1LL;
      }
      if ( v3 )
        return;
      NGENService::ControllerState::Set(0, 7u);
    }
  }
}

```

## disassembly

```asm
0x18001b1e4  mov     [rsp+arg_0], rbx
0x18001b1e9  mov     [rsp+arg_8], rsi
0x18001b1ee  push    r15
0x18001b1f0  sub     rsp, 30h
0x18001b1f4  mov     esi, 4
0x18001b1f9  lea     r15, ??_7FileLockHolder@@6B@; const FileLockHolder::`vftable'
0x18001b200  mov     al, cs:?g_bPauseRequested@NGENService@@3V?$Volatile@_N@@A; Volatile<bool> NGENService::g_bPauseRequested
0x18001b206  test    al, al
0x18001b208  jz      short loc_18001B24E
0x18001b20a  mov     cs:?g_bPauseRequested@NGENService@@3V?$Volatile@_N@@A, 0; Volatile<bool> NGENService::g_bPauseRequested
0x18001b211  mov     ecx, 7; this
0x18001b216  call    ?ServiceUpdateState@NGENService@@YAXK@Z; NGENService::ServiceUpdateState(ulong)
0x18001b21b  jmp     short loc_18001B227
0x18001b21d  mov     al, cs:?g_bStopRequested@NGENService@@3V?$Volatile@_N@@A; Volatile<bool> NGENService::g_bStopRequested
0x18001b223  test    al, al
0x18001b225  jnz     short loc_18001B23D
0x18001b227  mov     edx, 3E8h; dwMilliseconds
0x18001b22c  mov     rcx, cs:?g_hRestartEvent@NGENService@@3PEAXEA; hHandle
0x18001b233  call    cs:__imp_WaitForSingleObject
0x18001b239  test    eax, eax
0x18001b23b  jnz     short loc_18001B21D
0x18001b23d  mov     al, cs:?g_bStopRequested@NGENService@@3V?$Volatile@_N@@A; Volatile<bool> NGENService::g_bStopRequested
0x18001b243  test    al, al
0x18001b245  jnz     short loc_18001B24E
0x18001b247  mov     ecx, esi; this
0x18001b249  call    ?ServiceUpdateState@NGENService@@YAXK@Z; NGENService::ServiceUpdateState(ulong)
0x18001b24e  mov     al, cs:?g_bStopRequested@NGENService@@3V?$Volatile@_N@@A; Volatile<bool> NGENService::g_bStopRequested
0x18001b254  test    al, al
0x18001b256  jnz     loc_18001B329
0x18001b25c  call    ?ControllerRun@NGENService@@YA_NXZ; NGENService::ControllerRun(void)
0x18001b261  test    al, al
0x18001b263  jnz     short loc_18001B200
0x18001b265  xor     bl, bl
0x18001b267  mov     [rsp+38h+var_18], r15
0x18001b26c  or      [rsp+38h+hObject], 0FFFFFFFFFFFFFFFFh
0x18001b272  lea     rax, ??_7VersionedMutexHolder@@6B@; const VersionedMutexHolder::`vftable'
0x18001b279  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x18001b27e  xor     r9d, r9d; int *
0x18001b281  xor     r8d, r8d; void *
0x18001b284  lea     rdx, aNgenserviceloc; "ngenservicelock.dat"
0x18001b28b  lea     rcx, [rsp+38h+var_18]; this
0x18001b290  call    ?AcquireNoThrow@FileLockHolder@@QEAAJPEBGPEAXPEAH@Z; FileLockHolder::AcquireNoThrow(ushort const *,void *,int *)
0x18001b295  test    eax, eax
0x18001b297  jns     short loc_18001B2A7
0x18001b299  lea     rcx, aDoneworkFailed; "DoneWork(): Failed to acquire service l"...
0x18001b2a0  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x18001b2a5  jmp     short loc_18001B2F8
0x18001b2a7  mov     r9, cs:?g_hkNGENServicePersistentState@NGENService@@3PEAUHKEY__@@EA; HKEY
0x18001b2ae  lea     rcx, aPendingupdate; "PendingUpdate"
0x18001b2b5  call    ?GetLong@REGUTIL@@SAJPEBGJ0PEAUHKEY__@@@Z; REGUTIL::GetLong(ushort const *,long,ushort const *,HKEY__ *)
0x18001b2ba  cmp     eax, 1
0x18001b2bd  jz      short loc_18001B2EC
0x18001b2bf  mov     r9, cs:?g_hkNGENServiceListenedState@NGENService@@3PEAUHKEY__@@EA; HKEY
0x18001b2c6  lea     rcx, aRootstoredirty; "RootstoreDirty"
0x18001b2cd  call    ?GetLong@REGUTIL@@SAJPEBGJ0PEAUHKEY__@@@Z; REGUTIL::GetLong(ushort const *,long,ushort const *,HKEY__ *)
0x18001b2d2  test    eax, eax
0x18001b2d4  jnz     short loc_18001B2F8
0x18001b2d6  lea     r9, aCompletedAllWo; "Completed all work. Shutting down.\n"
0x18001b2dd  mov     r8d, 450h; unsigned __int16
0x18001b2e3  mov     edx, esi; unsigned __int16 *
0x18001b2e5  xor     ecx, ecx; this
0x18001b2e7  call    ?EventLog@NGENService@@YAXPEBGGK0ZZ; NGENService::EventLog(ushort const *,ushort,ulong,ushort const *,...)
0x18001b2ec  mov     ecx, 3; this
0x18001b2f1  call    ?ServiceUpdateState@NGENService@@YAXK@Z; NGENService::ServiceUpdateState(ulong)
0x18001b2f6  mov     bl, 1
0x18001b2f8  mov     [rsp+38h+var_18], r15
0x18001b2fd  mov     rcx, [rsp+38h+hObject]; hObject
0x18001b302  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001b306  jz      short loc_18001B314
0x18001b308  call    cs:__imp_CloseHandle
0x18001b30e  or      [rsp+38h+hObject], 0FFFFFFFFFFFFFFFFh
0x18001b314  test    bl, bl
0x18001b316  jnz     short loc_18001B329
0x18001b318  mov     edx, 7; unsigned int
0x18001b31d  xor     ecx, ecx; unsigned int
0x18001b31f  call    ?Set@ControllerState@NGENService@@SAXKK@Z; NGENService::ControllerState::Set(ulong,ulong)
0x18001b324  jmp     loc_18001B200
0x18001b329  mov     rbx, [rsp+38h+arg_0]
0x18001b32e  mov     rsi, [rsp+38h+arg_8]
0x18001b333  add     rsp, 30h
0x18001b337  pop     r15
0x18001b339  retn
```
