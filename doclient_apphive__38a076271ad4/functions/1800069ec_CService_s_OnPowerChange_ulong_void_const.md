# CService::s_OnPowerChange(ulong,void const *)

- ea: `0x1800069ec`
- end: `0x180006ae0`
- name: `?s_OnPowerChange@CService@@CAXKPEBX@Z`
- size: `244`
- prototype: `void __fastcall(unsigned int, const void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task`

## callers

- `0x180006d20`

## callees

- `0x1800069ec`
- `0x1800a1ea4`
- `0x1800f82f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180006a0e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180006a0e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180006a25`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180006a25`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetSystemPowerStatus` at `0x180006a56`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetSystemPowerStatus` at `0x180006a56`

## string_xrefs

- `0x180006a82`: `CService::s_OnPowerChange`
- `0x180006ab7`: `CService::s_OnPowerChange`

## pseudocode

```c
void __fastcall CService::s_OnPowerChange(int a1, const void *a2)
{
  bool v3; // bl
  _SYSTEM_POWER_STATUS SystemPowerStatus; // [rsp+40h] [rbp-28h] BYREF

  AcquireSRWLockShared(&CService::_svcStatusLock);
  v3 = CService::_svcStatusInfo.dwCurrentState == 4;
  ReleaseSRWLockShared(&CService::_svcStatusLock);
  if ( v3 )
  {
    switch ( a1 )
    {
      case 4:
        LogMessage(4u, "CService::s_OnPowerChange", 0x1BFu, "System is entering sleep/hibernation state");
        break;
      case 7:
        LogMessage(4u, "CService::s_OnPowerChange", 0x1C3u, "System is resuming after sleep/hibernation state");
        break;
      case 10:
        *(_QWORD *)&SystemPowerStatus.ACLineStatus = 0;
        SystemPowerStatus.BatteryFullLifeTime = 0;
        if ( GetSystemPowerStatus(&SystemPowerStatus) )
          LogMessage(
            4u,
            "CService::s_OnPowerChange",
            0x1CFu,
            "A/C power status: %u, Battery status: %x, Battery level: %u%%",
            SystemPowerStatus.ACLineStatus,
            SystemPowerStatus.BatteryFlag,
            SystemPowerStatus.BatteryLifePercent);
        break;
    }
  }
}

```

## disassembly

```asm
0x1800069ec  mov     [rsp+arg_0], rbx
0x1800069f1  push    rdi
0x1800069f2  sub     rsp, 60h
0x1800069f6  mov     rax, cs:__security_cookie
0x1800069fd  xor     rax, rsp
0x180006a00  mov     [rsp+68h+var_18], rax
0x180006a05  mov     edi, ecx
0x180006a07  lea     rcx, ?_svcStatusLock@CService@@0VSRWLock@Wrappers@WRL@Microsoft@@A; SRWLock
0x180006a0e  call    cs:__imp_AcquireSRWLockShared
0x180006a14  cmp     cs:?_svcStatusInfo@CService@@0U_SERVICE_STATUS@@A.dwCurrentState, 4; _SERVICE_STATUS CService::_svcStatusInfo ...
0x180006a1b  lea     rcx, ?_svcStatusLock@CService@@0VSRWLock@Wrappers@WRL@Microsoft@@A; SRWLock
0x180006a22  setz    bl
0x180006a25  call    cs:__imp_ReleaseSRWLockShared
0x180006a2b  test    bl, bl
0x180006a2d  jz      loc_180006AC8
0x180006a33  cmp     edi, 4
0x180006a36  jz      short loc_180006AAA
0x180006a38  cmp     edi, 7
0x180006a3b  jz      short loc_180006A9B
0x180006a3d  cmp     edi, 0Ah
0x180006a40  jnz     loc_180006AC8
0x180006a46  xor     eax, eax
0x180006a48  lea     rcx, [rsp+68h+SystemPowerStatus]; lpSystemPowerStatus
0x180006a4d  mov     qword ptr [rsp+68h+SystemPowerStatus.ACLineStatus], rax
0x180006a52  mov     [rsp+68h+SystemPowerStatus.BatteryFullLifeTime], eax
0x180006a56  call    cs:__imp_GetSystemPowerStatus
0x180006a5c  test    eax, eax
0x180006a5e  jz      short loc_180006AC8
0x180006a60  movzx   edx, [rsp+68h+SystemPowerStatus.BatteryFlag]
0x180006a65  lea     r9, aACPowerStatusU; "A/C power status: %u, Battery status: %"...
0x180006a6c  movzx   r8d, [rsp+68h+SystemPowerStatus.ACLineStatus]
0x180006a72  lea     ecx, [rdi-6]; unsigned __int8
0x180006a75  movzx   eax, [rsp+68h+SystemPowerStatus.BatteryLifePercent]
0x180006a7a  mov     [rsp+68h+var_38], eax
0x180006a7e  mov     [rsp+68h+var_40], edx
0x180006a82  lea     rdx, aCserviceSOnpow; "CService::s_OnPowerChange"
0x180006a89  mov     [rsp+68h+var_48], r8d
0x180006a8e  mov     r8d, 1CFh; unsigned int
0x180006a94  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x180006a99  jmp     short loc_180006AC8
0x180006a9b  lea     r9, aSystemIsResumi; "System is resuming after sleep/hibernat"...
0x180006aa2  mov     r8d, 1C3h
0x180006aa8  jmp     short loc_180006AB7
0x180006aaa  lea     r9, aSystemIsEnteri; "System is entering sleep/hibernation st"...
0x180006ab1  mov     r8d, 1BFh; unsigned int
0x180006ab7  lea     rdx, aCserviceSOnpow; "CService::s_OnPowerChange"
0x180006abe  mov     ecx, 4; unsigned __int8
0x180006ac3  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x180006ac8  mov     rcx, [rsp+68h+var_18]
0x180006acd  xor     rcx, rsp; StackCookie
0x180006ad0  call    __security_check_cookie
0x180006ad5  mov     rbx, [rsp+68h+arg_0]
0x180006ada  add     rsp, 60h
0x180006ade  pop     rdi
0x180006adf  retn
```
