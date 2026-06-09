# RestrictServicePrivileges(void)

- ea: `0x18002e9bc`
- end: `0x18002eaf5`
- name: `?RestrictServicePrivileges@@YAJXZ`
- size: `313`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002cd84`

## callees

- `0x18002c61c`
- `0x18002e9bc`
- `0x1800d6ea0`

## import_xrefs

- `mqsec!MQSec_RemovePrivilegesFromProcessToken` at `0x18002eab6`
- `mqsec!MQSec_RemovePrivilegesFromProcessToken` at `0x18002eab6`

## string_xrefs

- `0x18002e9dc`: `SeAssignPrimaryTokenPrivilege`
- `0x18002e9f0`: `SeBackupPrivilege`
- `0x18002e9fb`: `SeCreatePagefilePrivilege`
- `0x18002ea06`: `SeCreatePermanentPrivilege`
- `0x18002ea11`: `SeCreateTokenPrivilege`
- `0x18002ea1c`: `SeDebugPrivilege`
- `0x18002ea27`: `SeEnableDelegationPrivilege`
- `0x18002ea32`: `SeIncreaseBasePriorityPrivilege`
- `0x18002ea3d`: `SeLoadDriverPrivilege`
- `0x18002ea48`: `SeLockMemoryPrivilege`
- `0x18002ea53`: `SeRemoteShutdownPrivilege`
- `0x18002ea5e`: `SeRestorePrivilege`
- `0x18002ea69`: `SeSecurityPrivilege`
- `0x18002ea74`: `SeShutdownPrivilege`
- `0x18002ea7f`: `SeSystemEnvironmentPrivilege`
- `0x18002ea8a`: `SeSystemtimePrivilege`
- `0x18002ea95`: `SeTakeOwnershipPrivilege`
- `0x18002eaa0`: `SeTcbPrivilege`
- `0x18002eaab`: `SeUndockPrivilege`

## pseudocode

```c
__int64 RestrictServicePrivileges(void)
{
  int v0; // eax
  unsigned int v1; // ebx
  const wchar_t *v3[20]; // [rsp+20h] [rbp-59h] BYREF

  v3[0] = L"SeAssignPrimaryTokenPrivilege";
  v3[1] = L"SeBackupPrivilege";
  v3[2] = L"SeCreatePagefilePrivilege";
  v3[3] = L"SeCreatePermanentPrivilege";
  v3[4] = L"SeCreateTokenPrivilege";
  v3[5] = L"SeDebugPrivilege";
  v3[6] = L"SeEnableDelegationPrivilege";
  v3[7] = L"SeIncreaseBasePriorityPrivilege";
  v3[8] = L"SeLoadDriverPrivilege";
  v3[9] = L"SeLockMemoryPrivilege";
  v3[10] = L"SeRemoteShutdownPrivilege";
  v3[11] = L"SeRestorePrivilege";
  v3[12] = L"SeSecurityPrivilege";
  v3[13] = L"SeShutdownPrivilege";
  v3[14] = L"SeSystemEnvironmentPrivilege";
  v3[15] = L"SeSystemtimePrivilege";
  v3[16] = L"SeTakeOwnershipPrivilege";
  v3[17] = L"SeTcbPrivilege";
  v3[18] = L"SeUndockPrivilege";
  v0 = MQSec_RemovePrivilegesFromProcessToken(v3, 0x13u);
  v1 = v0;
  if ( v0 < 0 )
    LogMsgHR(v0, (wchar_t *)L"main", 0x4B5u);
  return v1;
}

```

## disassembly

```asm
0x18002e9bc  mov     [rsp-8+arg_0], rbx
0x18002e9c1  push    rbp
0x18002e9c2  lea     rbp, [rsp-57h]
0x18002e9c7  sub     rsp, 0D0h
0x18002e9ce  mov     rax, cs:__security_cookie
0x18002e9d5  xor     rax, rsp
0x18002e9d8  mov     [rbp+57h+var_10], rax
0x18002e9dc  lea     rax, aSeassignprimar; "SeAssignPrimaryTokenPrivilege"
0x18002e9e3  mov     edx, 13h
0x18002e9e8  mov     [rbp+57h+var_B0], rax
0x18002e9ec  lea     rcx, [rbp+57h+var_B0]
0x18002e9f0  lea     rax, aSebackupprivil; "SeBackupPrivilege"
0x18002e9f7  mov     [rbp+57h+var_A8], rax
0x18002e9fb  lea     rax, aSecreatepagefi; "SeCreatePagefilePrivilege"
0x18002ea02  mov     [rbp+57h+var_A0], rax
0x18002ea06  lea     rax, aSecreateperman; "SeCreatePermanentPrivilege"
0x18002ea0d  mov     [rbp+57h+var_98], rax
0x18002ea11  lea     rax, aSecreatetokenp; "SeCreateTokenPrivilege"
0x18002ea18  mov     [rbp+57h+var_90], rax
0x18002ea1c  lea     rax, aSedebugprivile; "SeDebugPrivilege"
0x18002ea23  mov     [rbp+57h+var_88], rax
0x18002ea27  lea     rax, aSeenabledelega; "SeEnableDelegationPrivilege"
0x18002ea2e  mov     [rbp+57h+var_80], rax
0x18002ea32  lea     rax, aSeincreasebase; "SeIncreaseBasePriorityPrivilege"
0x18002ea39  mov     [rbp+57h+var_78], rax
0x18002ea3d  lea     rax, aSeloaddriverpr; "SeLoadDriverPrivilege"
0x18002ea44  mov     [rbp+57h+var_70], rax
0x18002ea48  lea     rax, aSelockmemorypr; "SeLockMemoryPrivilege"
0x18002ea4f  mov     [rbp+57h+var_68], rax
0x18002ea53  lea     rax, aSeremoteshutdo; "SeRemoteShutdownPrivilege"
0x18002ea5a  mov     [rbp+57h+var_60], rax
0x18002ea5e  lea     rax, aSerestoreprivi; "SeRestorePrivilege"
0x18002ea65  mov     [rbp+57h+var_58], rax
0x18002ea69  lea     rax, aSesecuritypriv; "SeSecurityPrivilege"
0x18002ea70  mov     [rbp+57h+var_50], rax
0x18002ea74  lea     rax, aSeshutdownpriv; "SeShutdownPrivilege"
0x18002ea7b  mov     [rbp+57h+var_48], rax
0x18002ea7f  lea     rax, aSesystemenviro; "SeSystemEnvironmentPrivilege"
0x18002ea86  mov     [rbp+57h+var_40], rax
0x18002ea8a  lea     rax, aSesystemtimepr; "SeSystemtimePrivilege"
0x18002ea91  mov     [rbp+57h+var_38], rax
0x18002ea95  lea     rax, aSetakeownershi; "SeTakeOwnershipPrivilege"
0x18002ea9c  mov     [rbp+57h+var_30], rax
0x18002eaa0  lea     rax, aSetcbprivilege; "SeTcbPrivilege"
0x18002eaa7  mov     [rbp+57h+var_28], rax
0x18002eaab  lea     rax, aSeundockprivil; "SeUndockPrivilege"
0x18002eab2  mov     [rbp+57h+var_20], rax
0x18002eab6  call    cs:__imp_?MQSec_RemovePrivilegesFromProcessToken@@YAJPEBQEB_WK@Z; MQSec_RemovePrivilegesFromProcessToken(wchar_t const * const *,ulong)
0x18002eabc  mov     ebx, eax
0x18002eabe  test    eax, eax
0x18002eac0  jns     short loc_18002EAD6
0x18002eac2  mov     r8d, 4B5h; unsigned __int16
0x18002eac8  lea     rdx, aMain; "main"
0x18002eacf  mov     ecx, eax; int
0x18002ead1  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18002ead6  mov     eax, ebx
0x18002ead8  mov     rcx, [rbp+57h+var_10]
0x18002eadc  xor     rcx, rsp; StackCookie
0x18002eadf  call    __security_check_cookie
0x18002eae4  mov     rbx, [rsp+0D0h+arg_0]
0x18002eaec  add     rsp, 0D0h
0x18002eaf3  pop     rbp
0x18002eaf4  retn
```
