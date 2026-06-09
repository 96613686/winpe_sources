# PsmpQueryBatteryCharge

- ea: `0x180015994`
- end: `0x180015a23`
- name: `PsmpQueryBatteryCharge`
- size: `143`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180015894`

## callees

- `0x180015994`
- `0x180017f60`
- `0x18001b7e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800159ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800159ff`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetSystemPowerStatus` at `0x1800159b9`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetSystemPowerStatus` at `0x1800159b9`

## pseudocode

```c
__int64 PsmpQueryBatteryCharge()
{
  __int64 result; // rax
  __int64 v1; // rbx
  DWORD LastError; // eax
  _SYSTEM_POWER_STATUS SystemPowerStatus; // [rsp+20h] [rbp-28h] BYREF

  *(_QWORD *)&SystemPowerStatus.ACLineStatus = 0;
  SystemPowerStatus.BatteryFullLifeTime = 0;
  if ( GetSystemPowerStatus(&SystemPowerStatus) )
  {
    result = SystemPowerStatus.BatteryLifePercent;
    if ( SystemPowerStatus.BatteryLifePercent > 0x64u )
      return 50;
  }
  else
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v1 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      LastError = GetLastError();
      WPP_SF_d(v1, 87, &WPP_c1878895bf8430c1024ddd3cf0a685b6_Traceguids, LastError);
    }
    return 50;
  }
  return result;
}

```

## disassembly

```asm
0x180015994  push    rbx
0x180015996  sub     rsp, 40h
0x18001599a  mov     rax, cs:__security_cookie
0x1800159a1  xor     rax, rsp
0x1800159a4  mov     [rsp+48h+var_18], rax
0x1800159a9  xor     eax, eax
0x1800159ab  lea     rcx, [rsp+48h+SystemPowerStatus]; lpSystemPowerStatus
0x1800159b0  mov     qword ptr [rsp+48h+SystemPowerStatus.ACLineStatus], rax
0x1800159b5  mov     [rsp+48h+SystemPowerStatus.BatteryFullLifeTime], eax
0x1800159b9  call    cs:__imp_GetSystemPowerStatus
0x1800159bf  test    eax, eax
0x1800159c1  jz      short loc_1800159E8
0x1800159c3  cmp     [rsp+48h+SystemPowerStatus.BatteryLifePercent], 64h ; 'd'
0x1800159c8  mov     ecx, 32h ; '2'
0x1800159cd  movzx   eax, [rsp+48h+SystemPowerStatus.BatteryLifePercent]
0x1800159d2  cmova   eax, ecx
0x1800159d5  mov     rcx, [rsp+48h+var_18]
0x1800159da  xor     rcx, rsp; StackCookie
0x1800159dd  call    __security_check_cookie
0x1800159e2  add     rsp, 40h
0x1800159e6  pop     rbx
0x1800159e7  retn
0x1800159e8  mov     rbx, cs:WPP_GLOBAL_Control
0x1800159ef  test    byte ptr [rbx+1Ch], 1
0x1800159f3  jz      short loc_180015A1C
0x1800159f5  cmp     byte ptr [rbx+19h], 2
0x1800159f9  jb      short loc_180015A1C
0x1800159fb  mov     rbx, [rbx+10h]
0x1800159ff  call    cs:__imp_GetLastError
0x180015a05  mov     edx, 57h ; 'W'
0x180015a0a  lea     r8, WPP_c1878895bf8430c1024ddd3cf0a685b6_Traceguids
0x180015a11  mov     r9d, eax
0x180015a14  mov     rcx, rbx
0x180015a17  call    WPP_SF_d
0x180015a1c  mov     eax, 32h ; '2'
0x180015a21  jmp     short loc_1800159D5
```
