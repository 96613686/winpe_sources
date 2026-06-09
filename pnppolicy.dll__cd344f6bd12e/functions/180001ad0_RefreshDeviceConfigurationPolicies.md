# RefreshDeviceConfigurationPolicies

- ea: `0x180001ad0`
- end: `0x180001c43`
- name: `RefreshDeviceConfigurationPolicies`
- size: `371`
- prototype: `_BOOL8()`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180001da8`

## callees

- `0x180001ad0`
- `0x18000355c`
- `0x180003820`

## import_xrefs

- `ntdll!NtClose` at `0x180001c14`
- `ntdll!NtClose` at `0x180001c21`
- `ntdll!NtClose` at `0x180001c14`
- `ntdll!NtClose` at `0x180001c21`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180001b63`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180001b63`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x180001be2`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x180001be2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001c29`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001c29`
- `SETUPAPI!SetupGetThreadLogToken` at `0x180001aec`
- `SETUPAPI!SetupGetThreadLogToken` at `0x180001aec`
- `SETUPAPI!SetupWriteTextLog` at `0x180001b40`
- `SETUPAPI!SetupWriteTextLog` at `0x180001bbb`
- `SETUPAPI!SetupWriteTextLog` at `0x180001c07`
- `SETUPAPI!SetupWriteTextLog` at `0x180001b40`
- `SETUPAPI!SetupWriteTextLog` at `0x180001bbb`
- `SETUPAPI!SetupWriteTextLog` at `0x180001c07`

## string_xrefs

- `0x180001af8`: `Software\Policies\Microsoft\Windows\DeviceInstall`
- `0x180001b27`: `Failed to open device installation policies. Error = 0x%08X`
- `0x180001bcc`: `Failed to delete device configuration policies. Error = 0x%08X`
- `0x180001ba2`: `Failed to create device configuration policies. Error = 0x%08X`
- `0x180001bee`: `Failed to copy device installation policies. Error = 0x%08X`

## pseudocode

```c
_BOOL8 RefreshDeviceConfigurationPolicies()
{
  HKEY v0; // rsi
  SP_LOG_TOKEN ThreadLogToken; // rbp
  __int64 v2; // r8
  DWORD v3; // eax
  DWORD v4; // ebx
  HKEY v5; // rdi
  LSTATUS v6; // eax
  __int64 v7; // rcx
  __int64 v8; // r8
  DWORD Key; // eax
  const CHAR *v10; // r9
  __int64 v12; // [rsp+20h] [rbp-38h]
  HANDLE Handle; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKeyDest; // [rsp+68h] [rbp+10h]

  v0 = 0;
  Handle = 0;
  hKeyDest = 0;
  ThreadLogToken = SetupGetThreadLogToken();
  v3 = pSetupOpenKey(-2147483646, L"Software\\Policies\\Microsoft\\Windows\\DeviceInstall", v2, 0x2000000, &Handle);
  v4 = v3;
  if ( v3 == 2 )
  {
    v5 = 0;
    goto LABEL_6;
  }
  if ( !v3 )
  {
    v5 = (HKEY)Handle;
LABEL_6:
    v6 = RegDeleteTreeW(HKEY_LOCAL_MACHINE, L"System\\DriverDatabase\\Policies");
    v4 = v6;
    if ( v6 == 2 )
    {
      v4 = 0;
    }
    else if ( v6 )
    {
      v10 = "Failed to delete device configuration policies. Error = 0x%08X";
      goto LABEL_15;
    }
    if ( !v5 )
      goto LABEL_20;
    Key = pSetupCreateKeyEx(v7, L"System\\DriverDatabase\\Policies", v8, 0, 0x2000000);
    v4 = Key;
    if ( Key )
    {
      SetupWriteTextLog(
        ThreadLogToken,
        0x800000u,
        1u,
        "Failed to create device configuration policies. Error = 0x%08X",
        Key);
      v0 = hKeyDest;
      goto LABEL_16;
    }
    v0 = hKeyDest;
    v6 = RegCopyTreeW(v5, 0, hKeyDest);
    v4 = v6;
    if ( !v6 )
      goto LABEL_16;
    v10 = "Failed to copy device installation policies. Error = 0x%08X";
LABEL_15:
    LODWORD(v12) = v6;
    SetupWriteTextLog(ThreadLogToken, 0x800000u, 1u, v10, v12);
    goto LABEL_16;
  }
  SetupWriteTextLog(ThreadLogToken, 0x800000u, 1u, "Failed to open device installation policies. Error = 0x%08X", v3);
  v5 = (HKEY)Handle;
LABEL_16:
  if ( v5 )
    NtClose((HANDLE)(unsigned int)v5);
  if ( v0 )
    NtClose((HANDLE)(unsigned int)v0);
LABEL_20:
  SetLastError(v4);
  return v4 == 0;
}

```

## disassembly

```asm
0x180001ad0  mov     [rsp+arg_10], rbx
0x180001ad5  push    rbp
0x180001ad6  push    rsi
0x180001ad7  push    rdi
0x180001ad8  sub     rsp, 40h
0x180001adc  xor     esi, esi
0x180001ade  mov     [rsp+58h+Handle], 0
0x180001ae7  mov     [rsp+58h+hKeyDest], rsi
0x180001aec  call    cs:__imp_SetupGetThreadLogToken
0x180001af2  mov     r9d, 2000000h
0x180001af8  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x180001aff  mov     rbp, rax
0x180001b02  mov     rcx, 0FFFFFFFF80000002h
0x180001b09  lea     rax, [rsp+58h+Handle]
0x180001b0e  mov     [rsp+58h+var_38], rax
0x180001b13  call    pSetupOpenKey
0x180001b18  mov     ebx, eax
0x180001b1a  cmp     eax, 2
0x180001b1d  jnz     short loc_180001B23
0x180001b1f  xor     edi, edi
0x180001b21  jmp     short loc_180001B55
0x180001b23  test    eax, eax
0x180001b25  jz      short loc_180001B50
0x180001b27  lea     r9, MessageStr; "Failed to open device installation poli"...
0x180001b2e  mov     dword ptr [rsp+58h+var_38], eax
0x180001b32  mov     edx, 800000h; Category
0x180001b37  mov     r8d, 1; Flags
0x180001b3d  mov     rcx, rbp; LogToken
0x180001b40  call    cs:__imp_SetupWriteTextLog
0x180001b46  mov     rdi, [rsp+58h+Handle]
0x180001b4b  jmp     loc_180001C0D
0x180001b50  mov     rdi, [rsp+58h+Handle]
0x180001b55  lea     rdx, SubKey; "System\\DriverDatabase\\Policies"
0x180001b5c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180001b63  call    cs:__imp_RegDeleteTreeW
0x180001b69  mov     ebx, eax
0x180001b6b  cmp     eax, 2
0x180001b6e  jnz     short loc_180001BC8
0x180001b70  xor     ebx, ebx
0x180001b72  test    rdi, rdi
0x180001b75  jz      loc_180001C27
0x180001b7b  lea     rax, [rsp+58h+hKeyDest]
0x180001b80  xor     r9d, r9d
0x180001b83  mov     [rsp+58h+var_28], rax
0x180001b88  lea     rdx, SubKey; "System\\DriverDatabase\\Policies"
0x180001b8f  mov     dword ptr [rsp+58h+var_38], 2000000h
0x180001b97  call    pSetupCreateKeyEx
0x180001b9c  mov     ebx, eax
0x180001b9e  test    eax, eax
0x180001ba0  jz      short loc_180001BD5
0x180001ba2  lea     r9, aFailedToCreate; "Failed to create device configuration p"...
0x180001ba9  mov     dword ptr [rsp+58h+var_38], eax
0x180001bad  mov     edx, 800000h; Category
0x180001bb2  mov     r8d, 1; Flags
0x180001bb8  mov     rcx, rbp; LogToken
0x180001bbb  call    cs:__imp_SetupWriteTextLog
0x180001bc1  mov     rsi, [rsp+58h+hKeyDest]
0x180001bc6  jmp     short loc_180001C0D
0x180001bc8  test    eax, eax
0x180001bca  jz      short loc_180001B72
0x180001bcc  lea     r9, aFailedToDelete; "Failed to delete device configuration p"...
0x180001bd3  jmp     short loc_180001BF5
0x180001bd5  mov     rsi, [rsp+58h+hKeyDest]
0x180001bda  xor     edx, edx; lpSubKey
0x180001bdc  mov     r8, rsi; hKeyDest
0x180001bdf  mov     rcx, rdi; hKeySrc
0x180001be2  call    cs:__imp_RegCopyTreeW
0x180001be8  mov     ebx, eax
0x180001bea  test    eax, eax
0x180001bec  jz      short loc_180001C0D
0x180001bee  lea     r9, aFailedToCopyDe; "Failed to copy device installation poli"...
0x180001bf5  mov     r8d, 1; Flags
0x180001bfb  mov     dword ptr [rsp+58h+var_38], eax
0x180001bff  mov     edx, 800000h; Category
0x180001c04  mov     rcx, rbp; LogToken
0x180001c07  call    cs:__imp_SetupWriteTextLog
0x180001c0d  test    rdi, rdi
0x180001c10  jz      short loc_180001C1A
0x180001c12  mov     ecx, edi; Handle
0x180001c14  call    cs:__imp_NtClose
0x180001c1a  test    rsi, rsi
0x180001c1d  jz      short loc_180001C27
0x180001c1f  mov     ecx, esi; Handle
0x180001c21  call    cs:__imp_NtClose
0x180001c27  mov     ecx, ebx; dwErrCode
0x180001c29  call    cs:__imp_SetLastError
0x180001c2f  xor     eax, eax
0x180001c31  test    ebx, ebx
0x180001c33  mov     rbx, [rsp+58h+arg_10]
0x180001c38  setz    al
0x180001c3b  add     rsp, 40h
0x180001c3f  pop     rdi
0x180001c40  pop     rsi
0x180001c41  pop     rbp
0x180001c42  retn
```
