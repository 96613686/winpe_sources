# SockDemandStartAfd

- ea: `0x18001ed78`
- end: `0x18001efe1`
- name: `SockDemandStartAfd`
- size: `617`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180002650`
- `0x18000a6b0`
- `0x180019054`
- `0x1800250e0`

## callees

- `0x1800052a0`
- `0x18001ed78`
- `0x180038150`
- `0x18003ae8c`
- `0x18003aec4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001ed96`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001ee47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001ef15`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001ef68`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001ef95`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001efb1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001ed96`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001ee47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001ef15`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001ef68`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001ef95`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001efb1`
- `ntdll!NtSetInformationThread` at `0x18001ef4f`
- `ntdll!NtSetInformationThread` at `0x18001ef4f`
- `ntdll!NtLoadDriver` at `0x18001eede`
- `ntdll!NtLoadDriver` at `0x18001eede`
- `ntdll!RtlAdjustPrivilege` at `0x18001eeaa`
- `ntdll!RtlAdjustPrivilege` at `0x18001eefe`
- `ntdll!RtlAdjustPrivilege` at `0x18001eeaa`
- `ntdll!RtlAdjustPrivilege` at `0x18001eefe`
- `ntdll!RtlInitUnicodeString` at `0x18001eece`
- `ntdll!RtlInitUnicodeString` at `0x18001eece`
- `ntdll!RtlImpersonateSelf` at `0x18001ee79`
- `ntdll!RtlImpersonateSelf` at `0x18001ee79`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18001ee17`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18001ee17`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18001edd6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18001edd6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ee29`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ee29`

## string_xrefs

- `0x18001eebf`: `\Registry\Machine\System\CurrentControlSet\Services\AFD`

## pseudocode

```c
__int64 SockDemandStartAfd()
{
  DWORD CurrentProcessId; // eax
  __int64 v1; // rcx
  LSTATUS Value; // ebx
  DWORD v3; // eax
  NTSTATUS v5; // ebx
  DWORD v6; // eax
  __int64 v7; // rcx
  __int64 v8; // r8
  DWORD v9; // eax
  __int64 v10; // rcx
  DWORD v11; // eax
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // rdx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-10h] BYREF
  int Data; // [rsp+50h] [rbp+10h] BYREF
  __int64 cbData; // [rsp+58h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+20h] BYREF

  hKey = 0;
  if ( (xmmword_180063D60 & 2) != 0 )
  {
    CurrentProcessId = GetCurrentProcessId();
    WPP_SF_l(v1, 47, WPP_7d3a2c81e5df3cefdd06dcec6b626151_Traceguids, CurrentProcessId);
  }
  if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, "System\\Setup", 0, 0x20019u, &hKey) )
  {
    Data = 0;
    LODWORD(cbData) = 4;
    Value = RegQueryValueExA(hKey, "SystemSetupInProgress", 0, 0, (LPBYTE)&Data, (LPDWORD)&cbData);
    RegCloseKey(hKey);
    if ( !Value )
    {
      if ( Data )
      {
        if ( (xmmword_180063D60 & 2) != 0 )
        {
          v3 = GetCurrentProcessId();
          WPP_SF_d(1025, 48, WPP_7d3a2c81e5df3cefdd06dcec6b626151_Traceguids, v3);
        }
        return 10091;
      }
    }
  }
  v5 = RtlImpersonateSelf(SecurityImpersonation);
  if ( v5 < 0 )
  {
    if ( (xmmword_180063D60 & 2) != 0 )
    {
      v11 = GetCurrentProcessId();
      v14 = 52;
      goto LABEL_23;
    }
    return NtStatusToSocketError((unsigned int)v5);
  }
  cbData = 0;
  LOBYTE(Data) = 0;
  v5 = RtlAdjustPrivilege(0xAu, 1u, 1u, (PBOOLEAN)&Data);
  if ( v5 < 0 )
  {
    if ( (xmmword_180063D60 & 2) != 0 )
    {
      v6 = GetCurrentProcessId();
      WPP_SF_LL(v7, 49, v8, v6, v5);
    }
  }
  else
  {
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\AFD");
    v5 = NtLoadDriver(&DestinationString);
    if ( !(_BYTE)Data )
      RtlAdjustPrivilege(0xAu, 0, 1u, (PBOOLEAN)&Data);
  }
  cbData = 0;
  NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &cbData, 8u);
  if ( v5 < 0 )
  {
    if ( (xmmword_180063D60 & 2) != 0 )
    {
      v11 = GetCurrentProcessId();
      v14 = 51;
LABEL_23:
      WPP_SF_LL(v12, v14, v13, v11, v5);
      return NtStatusToSocketError((unsigned int)v5);
    }
    return NtStatusToSocketError((unsigned int)v5);
  }
  if ( (xmmword_180063D60 & 2) != 0 )
  {
    v9 = GetCurrentProcessId();
    WPP_SF_l(v10, 50, WPP_7d3a2c81e5df3cefdd06dcec6b626151_Traceguids, v9);
  }
  return 0;
}

```

## disassembly

```asm
0x18001ed78  mov     [rsp-8+arg_18], rbx
0x18001ed7d  push    rbp
0x18001ed7e  mov     rbp, rsp
0x18001ed81  sub     rsp, 40h
0x18001ed85  mov     [rbp+hKey], 0
0x18001ed8d  test    byte ptr cs:xmmword_180063D60, 2
0x18001ed94  jz      short loc_18001EDB6
0x18001ed96  call    cs:__imp_GetCurrentProcessId
0x18001ed9d  nop     dword ptr [rax+rax+00h]
0x18001eda2  mov     edx, 2Fh ; '/'
0x18001eda7  lea     r8, WPP_7d3a2c81e5df3cefdd06dcec6b626151_Traceguids
0x18001edae  mov     r9d, eax
0x18001edb1  call    WPP_SF_l
0x18001edb6  lea     rax, [rbp+hKey]
0x18001edba  mov     r9d, 20019h; samDesired
0x18001edc0  xor     r8d, r8d; ulOptions
0x18001edc3  mov     [rsp+40h+phkResult], rax; phkResult
0x18001edc8  lea     rdx, aSystemSetup; "System\\Setup"
0x18001edcf  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001edd6  call    cs:__imp_RegOpenKeyExA
0x18001eddd  nop     dword ptr [rax+rax+00h]
0x18001ede2  test    eax, eax
0x18001ede4  jnz     loc_18001EE74
0x18001edea  mov     rcx, [rbp+hKey]; hKey
0x18001edee  lea     rdx, aSystemsetupinp; "SystemSetupInProgress"
0x18001edf5  mov     [rbp+Data], eax
0x18001edf8  xor     r9d, r9d; lpType
0x18001edfb  lea     rax, [rbp+cbData]
0x18001edff  mov     dword ptr [rbp+cbData], 4
0x18001ee06  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18001ee0b  xor     r8d, r8d; lpReserved
0x18001ee0e  lea     rax, [rbp+Data]
0x18001ee12  mov     [rsp+40h+phkResult], rax; lpData
0x18001ee17  call    cs:__imp_RegQueryValueExA
0x18001ee1e  nop     dword ptr [rax+rax+00h]
0x18001ee23  mov     rcx, [rbp+hKey]; hKey
0x18001ee27  mov     ebx, eax
0x18001ee29  call    cs:__imp_RegCloseKey
0x18001ee30  nop     dword ptr [rax+rax+00h]
0x18001ee35  test    ebx, ebx
0x18001ee37  jnz     short loc_18001EE74
0x18001ee39  cmp     [rbp+Data], ebx
0x18001ee3c  jz      short loc_18001EE74
0x18001ee3e  test    byte ptr cs:xmmword_180063D60, 2
0x18001ee45  jz      short loc_18001EE6A
0x18001ee47  call    cs:__imp_GetCurrentProcessId
0x18001ee4e  nop     dword ptr [rax+rax+00h]
0x18001ee53  lea     edx, [rbx+30h]
0x18001ee56  mov     ecx, 401h
0x18001ee5b  mov     r9d, eax
0x18001ee5e  lea     r8, WPP_7d3a2c81e5df3cefdd06dcec6b626151_Traceguids
0x18001ee65  call    WPP_SF_d
0x18001ee6a  mov     eax, 276Bh
0x18001ee6f  jmp     loc_18001EFD5
0x18001ee74  mov     ecx, 2; ImpersonationLevel
0x18001ee79  call    cs:__imp_RtlImpersonateSelf
0x18001ee80  nop     dword ptr [rax+rax+00h]
0x18001ee85  mov     ebx, eax
0x18001ee87  test    eax, eax
0x18001ee89  js      loc_18001EFA8
0x18001ee8f  mov     r8b, 1; ForThread
0x18001ee92  mov     [rbp+cbData], 0
0x18001ee9a  mov     dl, r8b; NewValue
0x18001ee9d  mov     byte ptr [rbp+Data], 0
0x18001eea1  lea     r9, [rbp+Data]; OldValue
0x18001eea5  mov     ecx, 0Ah; Privilege
0x18001eeaa  call    cs:__imp_RtlAdjustPrivilege
0x18001eeb1  nop     dword ptr [rax+rax+00h]
0x18001eeb6  mov     ebx, eax
0x18001eeb8  test    eax, eax
0x18001eeba  js      short loc_18001EF0C
0x18001eebc  xorps   xmm0, xmm0
0x18001eebf  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x18001eec6  lea     rcx, [rbp+DestinationString]; DestinationString
0x18001eeca  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18001eece  call    cs:__imp_RtlInitUnicodeString
0x18001eed5  nop     dword ptr [rax+rax+00h]
0x18001eeda  lea     rcx, [rbp+DestinationString]; DriverServiceName
0x18001eede  call    cs:__imp_NtLoadDriver
0x18001eee5  nop     dword ptr [rax+rax+00h]
0x18001eeea  cmp     byte ptr [rbp+Data], 0
0x18001eeee  mov     ebx, eax
0x18001eef0  jnz     short loc_18001EF32
0x18001eef2  xor     edx, edx; NewValue
0x18001eef4  lea     r9, [rbp+Data]; OldValue
0x18001eef8  mov     r8b, 1; ForThread
0x18001eefb  lea     ecx, [rdx+0Ah]; Privilege
0x18001eefe  call    cs:__imp_RtlAdjustPrivilege
0x18001ef05  nop     dword ptr [rax+rax+00h]
0x18001ef0a  jmp     short loc_18001EF32
0x18001ef0c  test    byte ptr cs:xmmword_180063D60, 2
0x18001ef13  jz      short loc_18001EF32
0x18001ef15  call    cs:__imp_GetCurrentProcessId
0x18001ef1c  nop     dword ptr [rax+rax+00h]
0x18001ef21  mov     edx, 31h ; '1'
0x18001ef26  mov     dword ptr [rsp+40h+phkResult], ebx
0x18001ef2a  mov     r9d, eax
0x18001ef2d  call    WPP_SF_LL
0x18001ef32  mov     r9d, 8; ThreadInformationLength
0x18001ef38  mov     [rbp+cbData], 0
0x18001ef40  lea     r8, [rbp+cbData]; ThreadInformation
0x18001ef44  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18001ef4b  lea     edx, [r9-3]; ThreadInformationClass
0x18001ef4f  call    cs:__imp_NtSetInformationThread
0x18001ef56  nop     dword ptr [rax+rax+00h]
0x18001ef5b  test    ebx, ebx
0x18001ef5d  js      short loc_18001EF8C
0x18001ef5f  test    byte ptr cs:xmmword_180063D60, 2
0x18001ef66  jz      short loc_18001EF88
0x18001ef68  call    cs:__imp_GetCurrentProcessId
0x18001ef6f  nop     dword ptr [rax+rax+00h]
0x18001ef74  mov     edx, 32h ; '2'
0x18001ef79  lea     r8, WPP_7d3a2c81e5df3cefdd06dcec6b626151_Traceguids
0x18001ef80  mov     r9d, eax
0x18001ef83  call    WPP_SF_l
0x18001ef88  xor     eax, eax
0x18001ef8a  jmp     short loc_18001EFD5
0x18001ef8c  test    byte ptr cs:xmmword_180063D60, 2
0x18001ef93  jz      short loc_18001EFCE
0x18001ef95  call    cs:__imp_GetCurrentProcessId
0x18001ef9c  nop     dword ptr [rax+rax+00h]
0x18001efa1  mov     edx, 33h ; '3'
0x18001efa6  jmp     short loc_18001EFC2
0x18001efa8  test    byte ptr cs:xmmword_180063D60, 2
0x18001efaf  jz      short loc_18001EFCE
0x18001efb1  call    cs:__imp_GetCurrentProcessId
0x18001efb8  nop     dword ptr [rax+rax+00h]
0x18001efbd  mov     edx, 34h ; '4'
0x18001efc2  mov     r9d, eax
0x18001efc5  mov     dword ptr [rsp+40h+phkResult], ebx
0x18001efc9  call    WPP_SF_LL
0x18001efce  mov     ecx, ebx
0x18001efd0  call    NtStatusToSocketError
0x18001efd5  mov     rbx, [rsp+40h+arg_18]
0x18001efda  add     rsp, 40h
0x18001efde  pop     rbp
0x18001efdf  retn
```
