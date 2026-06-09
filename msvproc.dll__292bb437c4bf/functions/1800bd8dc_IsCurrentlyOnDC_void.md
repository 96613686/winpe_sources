# IsCurrentlyOnDC(void)

- ea: `0x1800bd8dc`
- end: `0x1800bd9f8`
- name: `?IsCurrentlyOnDC@@YA_NXZ`
- size: `284`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x180009724`

## callees

- `0x18000c9d0`
- `0x18000ecf0`
- `0x180037230`
- `0x180054140`
- `0x180066a98`
- `0x1800bd8dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bd9b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bd9b2`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetSystemPowerStatus` at `0x1800bd93d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetSystemPowerStatus` at `0x1800bd93d`

## pseudocode

```c
char IsCurrentlyOnDC(void)
{
  unsigned __int8 v0; // al
  char v1; // bl
  DWORD LastError; // eax
  _BYTE v4[8]; // [rsp+20h] [rbp-28h] BYREF
  _SYSTEM_POWER_STATUS SystemPowerStatus; // [rsp+28h] [rbp-20h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v4, "IsCurrentlyOnDC", 945);
  if ( g_wppLevels >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, WPP_339a3ee91d6a3f475725bbafa80cf895_Traceguids);
  *(_QWORD *)&SystemPowerStatus.ACLineStatus = 0;
  SystemPowerStatus.BatteryFullLifeTime = 0;
  if ( !GetSystemPowerStatus(&SystemPowerStatus) )
  {
    if ( g_wppLevels >= 4u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, WPP_339a3ee91d6a3f475725bbafa80cf895_Traceguids, LastError);
    }
    goto LABEL_12;
  }
  v0 = g_wppLevels;
  if ( g_wppLevels >= 4u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      71,
      WPP_339a3ee91d6a3f475725bbafa80cf895_Traceguids,
      SystemPowerStatus.ACLineStatus);
    v0 = g_wppLevels;
  }
  v1 = 1;
  if ( SystemPowerStatus.ACLineStatus == 1 )
  {
LABEL_12:
    v1 = 0;
    goto LABEL_13;
  }
  if ( SystemPowerStatus.ACLineStatus )
  {
    if ( v0 >= 4u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, WPP_339a3ee91d6a3f475725bbafa80cf895_Traceguids);
    goto LABEL_12;
  }
LABEL_13:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v4);
  return v1;
}

```

## disassembly

```asm
0x1800bd8dc  push    rbx
0x1800bd8de  sub     rsp, 40h
0x1800bd8e2  mov     rax, cs:__security_cookie
0x1800bd8e9  xor     rax, rsp
0x1800bd8ec  mov     [rsp+48h+var_10], rax
0x1800bd8f1  mov     r8d, 3B1h; int
0x1800bd8f7  lea     rdx, aIscurrentlyond; "IsCurrentlyOnDC"
0x1800bd8fe  lea     rcx, [rsp+48h+var_28]; this
0x1800bd903  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800bd908  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 4; MFWppLevels g_wppLevels
0x1800bd90f  jb      short loc_1800BD92D
0x1800bd911  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bd918  lea     r8, WPP_339a3ee91d6a3f475725bbafa80cf895_Traceguids
0x1800bd91f  mov     edx, 46h ; 'F'
0x1800bd924  mov     rcx, [rcx+10h]
0x1800bd928  call    WPP_SF_
0x1800bd92d  xor     eax, eax
0x1800bd92f  lea     rcx, [rsp+48h+SystemPowerStatus]; lpSystemPowerStatus
0x1800bd934  mov     qword ptr [rsp+48h+SystemPowerStatus.ACLineStatus], rax
0x1800bd939  mov     [rsp+48h+SystemPowerStatus.BatteryFullLifeTime], eax
0x1800bd93d  call    cs:__imp_GetSystemPowerStatus
0x1800bd943  test    eax, eax
0x1800bd945  jz      short loc_1800BD9A9
0x1800bd947  mov     al, cs:?g_wppLevels@@3UMFWppLevels@@A; MFWppLevels g_wppLevels
0x1800bd94d  cmp     al, 4
0x1800bd94f  jb      short loc_1800BD979
0x1800bd951  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bd958  lea     r8, WPP_339a3ee91d6a3f475725bbafa80cf895_Traceguids
0x1800bd95f  movzx   r9d, [rsp+48h+SystemPowerStatus.ACLineStatus]
0x1800bd965  mov     edx, 47h ; 'G'
0x1800bd96a  mov     rcx, [rcx+10h]
0x1800bd96e  call    WPP_SF_d
0x1800bd973  mov     al, cs:?g_wppLevels@@3UMFWppLevels@@A; MFWppLevels g_wppLevels
0x1800bd979  mov     cl, [rsp+48h+SystemPowerStatus.ACLineStatus]
0x1800bd97d  mov     bl, 1
0x1800bd97f  cmp     cl, bl
0x1800bd981  jz      short loc_1800BD9D7
0x1800bd983  test    cl, cl
0x1800bd985  jz      short loc_1800BD9D9
0x1800bd987  cmp     al, 4
0x1800bd989  jb      short loc_1800BD9D7
0x1800bd98b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bd992  lea     r8, WPP_339a3ee91d6a3f475725bbafa80cf895_Traceguids
0x1800bd999  mov     edx, 48h ; 'H'
0x1800bd99e  mov     rcx, [rcx+10h]
0x1800bd9a2  call    WPP_SF_
0x1800bd9a7  jmp     short loc_1800BD9D7
0x1800bd9a9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 4; MFWppLevels g_wppLevels
0x1800bd9b0  jb      short loc_1800BD9D7
0x1800bd9b2  call    cs:__imp_GetLastError
0x1800bd9b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bd9bf  lea     r8, WPP_339a3ee91d6a3f475725bbafa80cf895_Traceguids
0x1800bd9c6  mov     edx, 49h ; 'I'
0x1800bd9cb  mov     r9d, eax
0x1800bd9ce  mov     rcx, [rcx+10h]
0x1800bd9d2  call    WPP_SF_d
0x1800bd9d7  xor     ebx, ebx
0x1800bd9d9  lea     rcx, [rsp+48h+var_28]; this
0x1800bd9de  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800bd9e3  mov     al, bl
0x1800bd9e5  mov     rcx, [rsp+48h+var_10]
0x1800bd9ea  xor     rcx, rsp; StackCookie
0x1800bd9ed  call    __security_check_cookie
0x1800bd9f2  add     rsp, 40h
0x1800bd9f6  pop     rbx
0x1800bd9f7  retn
```
