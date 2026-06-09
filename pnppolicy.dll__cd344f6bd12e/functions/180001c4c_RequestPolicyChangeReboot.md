# RequestPolicyChangeReboot

- ea: `0x180001c4c`
- end: `0x180001da0`
- name: `RequestPolicyChangeReboot`
- size: `340`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180001da8`

## callees

- `0x180001a78`
- `0x180001c4c`
- `0x1800040d8`
- `0x1800041cc`
- `0x18000a1a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001d5a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a57c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001d5a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a57c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a591`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a591`
- `api-ms-win-core-shutdown-l1-1-1!InitiateShutdownW` at `0x180001d4b`
- `api-ms-win-core-shutdown-l1-1-1!InitiateShutdownW` at `0x180001d4b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180001d65`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000a587`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180001d65`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000a587`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001d7d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a5a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001d7d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a5a0`
- `SETUPAPI!SetupGetThreadLogToken` at `0x180001c6a`
- `SETUPAPI!SetupGetThreadLogToken` at `0x180001c6a`
- `SETUPAPI!SetupWriteTextLog` at `0x180001d30`
- `SETUPAPI!SetupWriteTextLog` at `0x180001d30`

## string_xrefs

- `0x180001c8a`: `Software\Policies\Microsoft\Windows\DeviceInstall`
- `0x180001cb3`: `Software\Policies\Microsoft\Windows\DeviceInstall`
- `0x180001d1b`: `The system will restart in %d seconds in order to enforce device installation restriction policy.`

## pseudocode

```c
int RequestPolicyChangeReboot()
{
  SP_LOG_TOKEN ThreadLogToken; // rsi
  __int64 v1; // rcx
  __int64 v2; // r8
  int result; // eax
  __int64 v4; // rcx
  __int64 v5; // r8
  DWORD PolicyValue; // eax
  __int64 v7; // rcx
  __int64 v8; // r8
  DWORD v9; // edi
  void *v10; // rbx
  void *v11; // [rsp+30h] [rbp-38h] BYREF
  char v12[16]; // [rsp+38h] [rbp-30h] BYREF
  void **v13; // [rsp+48h] [rbp-20h]
  __int64 v14; // [rsp+50h] [rbp-18h]

  ThreadLogToken = SetupGetThreadLogToken();
  result = pSetupGetPolicyValue(v1, L"Software\\Policies\\Microsoft\\Windows\\DeviceInstall", v2, L"ForceReboot", 0, 1u);
  if ( result == 1 )
  {
    PolicyValue = pSetupGetPolicyValue(
                    v4,
                    L"Software\\Policies\\Microsoft\\Windows\\DeviceInstall",
                    v5,
                    L"RebootTime",
                    0x78u,
                    0x78u);
    v9 = PolicyValue;
    if ( (Microsoft_Windows_UserPnpEnableBits & 2) != 0 )
    {
      LODWORD(v11) = PolicyValue;
      v13 = &v11;
      v14 = 4;
      McGenEventWrite_EventWriteTransfer(v7, DM_POLICY_REBOOT, v8, 2, v12);
    }
    LODWORD(v11) = 19;
    v10 = (void *)pSetupEnableThreadPrivileges(&v11);
    v11 = v10;
    SetupWriteTextLog(
      ThreadLogToken,
      0x800000u,
      2u,
      "The system will restart in %d seconds in order to enforce device installation restriction policy.",
      v9);
    result = InitiateShutdownW(0, 0, v9, 7u, 0x20013u);
    if ( v10 != (void *)-1LL )
    {
      SetLastError(0);
      result = SetThreadToken(0, v10);
      if ( !result )
        result = GetLastError();
      if ( v10 )
        return CloseHandle(v10);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180001c4c  mov     [rsp+arg_0], rbx
0x180001c51  mov     [rsp+arg_8], rsi
0x180001c56  push    rdi
0x180001c57  sub     rsp, 60h
0x180001c5b  mov     rax, cs:__security_cookie
0x180001c62  xor     rax, rsp
0x180001c65  mov     [rsp+68h+var_10], rax
0x180001c6a  call    cs:__imp_SetupGetThreadLogToken
0x180001c70  mov     rsi, rax
0x180001c73  mov     [rsp+68h+var_40], 1
0x180001c7b  mov     [rsp+68h+dwReason], 0
0x180001c83  lea     r9, aForcereboot; "ForceReboot"
0x180001c8a  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x180001c91  call    pSetupGetPolicyValue
0x180001c96  cmp     eax, 1
0x180001c99  jnz     loc_180001D83
0x180001c9f  mov     eax, 78h ; 'x'
0x180001ca4  mov     [rsp+68h+var_40], eax
0x180001ca8  mov     [rsp+68h+dwReason], eax
0x180001cac  lea     r9, aReboottime; "RebootTime"
0x180001cb3  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x180001cba  call    pSetupGetPolicyValue
0x180001cbf  mov     edi, eax
0x180001cc1  test    cs:Microsoft_Windows_UserPnpEnableBits, 2
0x180001cc8  jz      short loc_180001CFD
0x180001cca  mov     dword ptr [rsp+68h+var_38], eax
0x180001cce  lea     rax, [rsp+68h+var_38]
0x180001cd3  mov     [rsp+68h+var_20], rax
0x180001cd8  mov     [rsp+68h+var_18], 4
0x180001ce1  lea     rax, [rsp+68h+var_30]
0x180001ce6  mov     qword ptr [rsp+68h+dwReason], rax
0x180001ceb  mov     r9d, 2
0x180001cf1  lea     rdx, DM_POLICY_REBOOT
0x180001cf8  call    McGenEventWrite_EventWriteTransfer
0x180001cfd  mov     dword ptr [rsp+68h+var_38], 13h
0x180001d05  lea     rcx, [rsp+68h+var_38]
0x180001d0a  call    pSetupEnableThreadPrivileges
0x180001d0f  mov     rbx, rax
0x180001d12  mov     [rsp+68h+var_38], rax
0x180001d17  mov     [rsp+68h+dwReason], edi
0x180001d1b  lea     r9, aTheSystemWillR; "The system will restart in %d seconds i"...
0x180001d22  mov     edx, 800000h; Category
0x180001d27  mov     r8d, 2; Flags
0x180001d2d  mov     rcx, rsi; LogToken
0x180001d30  call    cs:__imp_SetupWriteTextLog
0x180001d36  mov     [rsp+68h+dwReason], 20013h; dwReason
0x180001d3e  mov     r9d, 7; dwShutdownFlags
0x180001d44  mov     r8d, edi; dwGracePeriod
0x180001d47  xor     edx, edx; lpMessage
0x180001d49  xor     ecx, ecx; lpMachineName
0x180001d4b  call    cs:__imp_InitiateShutdownW
0x180001d51  nop
0x180001d52  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180001d56  jz      short loc_180001D83
0x180001d58  xor     ecx, ecx; dwErrCode
0x180001d5a  call    cs:__imp_SetLastError
0x180001d60  mov     rdx, rbx; Token
0x180001d63  xor     ecx, ecx; Thread
0x180001d65  call    cs:__imp_SetThreadToken
0x180001d6b  test    eax, eax
0x180001d6d  jnz     short loc_180001D75
0x180001d6f  call    cs:__imp_GetLastError
0x180001d75  test    rbx, rbx
0x180001d78  jz      short loc_180001D83
0x180001d7a  mov     rcx, rbx; hObject
0x180001d7d  call    cs:__imp_CloseHandle
0x180001d83  mov     rcx, [rsp+68h+var_10]
0x180001d88  xor     rcx, rsp; StackCookie
0x180001d8b  call    __security_check_cookie
0x180001d90  mov     rbx, [rsp+68h+arg_0]
0x180001d95  mov     rsi, [rsp+68h+arg_8]
0x180001d9a  add     rsp, 60h
0x180001d9e  pop     rdi
0x180001d9f  retn
0x18000a566  push    rbx
0x18000a568  push    rbp
0x18000a569  sub     rsp, 38h
0x18000a56d  mov     rbp, rdx
0x18000a570  mov     rbx, [rbp+30h]
0x18000a574  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000a578  jz      short loc_18000A5A7
0x18000a57a  xor     ecx, ecx; dwErrCode
0x18000a57c  call    cs:__imp_SetLastError
0x18000a582  mov     rdx, rbx; Token
0x18000a585  xor     ecx, ecx; Thread
0x18000a587  call    cs:__imp_SetThreadToken
0x18000a58d  test    eax, eax
0x18000a58f  jnz     short loc_18000A598
0x18000a591  call    cs:__imp_GetLastError
0x18000a597  nop
0x18000a598  test    rbx, rbx
0x18000a59b  jz      short loc_18000A5A7
0x18000a59d  mov     rcx, rbx; hObject
0x18000a5a0  call    cs:__imp_CloseHandle
0x18000a5a6  nop
0x18000a5a7  add     rsp, 38h
0x18000a5ab  pop     rbp
0x18000a5ac  pop     rbx
0x18000a5ad  retn
```
