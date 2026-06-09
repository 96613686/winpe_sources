# IsLowBattery(void)

- ea: `0x18000f698`
- end: `0x18000f72b`
- name: `?IsLowBattery@@YA_NXZ`
- size: `147`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010a10`

## callees

- `0x180002b60`
- `0x18000b098`
- `0x18000f698`
- `0x180010134`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-0!GetSystemPowerStatus` at `0x18000f6bd`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetSystemPowerStatus` at `0x18000f6bd`

## string_xrefs

- `0x18000f6d5`: `shellcommon\shell\oobe\core\components\common\oobebatteryhelper.h`

## pseudocode

```c
char IsLowBattery(void)
{
  int Error; // eax
  char v1; // bl
  bool v2; // al
  _SYSTEM_POWER_STATUS SystemPowerStatus; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *(_QWORD *)&SystemPowerStatus.ACLineStatus = 0;
  SystemPowerStatus.BatteryFullLifeTime = 0;
  if ( GetSystemPowerStatus(&SystemPowerStatus) || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    v1 = 1;
    v2 = (SystemPowerStatus.BatteryFlag & 0x80u) == 0 && (SystemPowerStatus.BatteryFlag & 2) == 0;
    if ( SystemPowerStatus.ACLineStatus == 1 || v2 )
      return 0;
  }
  else
  {
    v1 = 1;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xB,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\common\\oobebatteryhelper.h",
      (const char *)(unsigned int)Error,
      *(int *)&SystemPowerStatus.ACLineStatus);
  }
  return v1;
}

```

## disassembly

```asm
0x18000f698  push    rbx
0x18000f69a  sub     rsp, 40h
0x18000f69e  mov     rax, cs:__security_cookie
0x18000f6a5  xor     rax, rsp
0x18000f6a8  mov     [rsp+48h+var_18], rax
0x18000f6ad  xor     eax, eax
0x18000f6af  lea     rcx, [rsp+48h+SystemPowerStatus]; lpSystemPowerStatus
0x18000f6b4  mov     qword ptr [rsp+48h+SystemPowerStatus.ACLineStatus], rax; int
0x18000f6b9  mov     [rsp+48h+SystemPowerStatus.BatteryFullLifeTime], eax
0x18000f6bd  call    cs:__imp_GetSystemPowerStatus
0x18000f6c3  test    eax, eax
0x18000f6c5  jnz     short loc_18000F6ED
0x18000f6c7  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000f6cc  test    eax, eax
0x18000f6ce  jns     short loc_18000F6ED
0x18000f6d0  mov     rcx, [rsp+48h]; this
0x18000f6d5  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\oobe\\core\\compone"...
0x18000f6dc  mov     r9d, eax; char *
0x18000f6df  mov     edx, 0Bh; void *
0x18000f6e4  mov     bl, 1
0x18000f6e6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000f6eb  jmp     short loc_18000F716
0x18000f6ed  mov     al, [rsp+48h+SystemPowerStatus.BatteryFlag]
0x18000f6f1  mov     bl, 1
0x18000f6f3  cmp     [rsp+48h+SystemPowerStatus.ACLineStatus], bl
0x18000f6f7  setz    cl
0x18000f6fa  cmp     al, 0FFh
0x18000f6fc  jz      short loc_18000F70A
0x18000f6fe  test    al, al
0x18000f700  js      short loc_18000F70A
0x18000f702  test    al, 2
0x18000f704  jnz     short loc_18000F70A
0x18000f706  mov     al, bl
0x18000f708  jmp     short loc_18000F70C
0x18000f70a  xor     al, al
0x18000f70c  test    cl, cl
0x18000f70e  jnz     short loc_18000F714
0x18000f710  test    al, al
0x18000f712  jz      short loc_18000F716
0x18000f714  xor     bl, bl
0x18000f716  mov     al, bl
0x18000f718  mov     rcx, [rsp+48h+var_18]
0x18000f71d  xor     rcx, rsp; StackCookie
0x18000f720  call    __security_check_cookie
0x18000f725  add     rsp, 40h
0x18000f729  pop     rbx
0x18000f72a  retn
```
