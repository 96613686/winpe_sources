# AssureRunningAsAdministrator(void)

- ea: `0x180015948`
- end: `0x180015aa7`
- name: `?AssureRunningAsAdministrator@@YAJXZ`
- size: `351`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180007a40`

## callees

- `0x180015948`

## import_xrefs

- `ADVAPI32!IsWellKnownSid` at `0x180015a22`
- `ADVAPI32!IsWellKnownSid` at `0x180015a34`
- `ADVAPI32!IsWellKnownSid` at `0x180015a46`
- `ADVAPI32!IsWellKnownSid` at `0x180015a22`
- `ADVAPI32!IsWellKnownSid` at `0x180015a34`
- `ADVAPI32!IsWellKnownSid` at `0x180015a46`
- `ADVAPI32!GetSecurityInfo` at `0x18001599c`
- `ADVAPI32!GetSecurityInfo` at `0x18001599c`
- `KERNEL32!GetCurrentProcess` at `0x180015960`
- `KERNEL32!GetCurrentProcess` at `0x180015960`
- `KERNEL32!LocalFree` at `0x180015a99`
- `KERNEL32!LocalFree` at `0x180015a99`
- `IisRTL!PuDbgPrint` at `0x180015a15`
- `IisRTL!PuDbgPrint` at `0x180015a89`
- `IisRTL!PuDbgPrint` at `0x180015a15`
- `IisRTL!PuDbgPrint` at `0x180015a89`

## string_xrefs

- `0x1800159c0`: `GetSecurityInfo() failed in AssureRunningAsAdministrator hr=0x%08x.\n`
- `0x1800159f5`: `GetSecurityInfo() returned NULL sid.\n`

## pseudocode

```c
__int64 AssureRunningAsAdministrator(void)
{
  HANDLE CurrentProcess; // rax
  signed int SecurityInfo; // eax
  unsigned int v2; // ebx
  const char *v3; // rax
  __int64 v4; // r8
  PSID ppsidOwner; // [rsp+50h] [rbp+8h] BYREF
  PSECURITY_DESCRIPTOR hMem; // [rsp+58h] [rbp+10h] BYREF

  ppsidOwner = 0;
  hMem = 0;
  CurrentProcess = GetCurrentProcess();
  SecurityInfo = GetSecurityInfo(CurrentProcess, SE_KERNEL_OBJECT, 1u, &ppsidOwner, 0, 0, 0, &hMem);
  v2 = SecurityInfo;
  if ( SecurityInfo )
  {
    if ( SecurityInfo > 0 )
      v2 = (unsigned __int16)SecurityInfo | 0x80070000;
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      v3 = "GetSecurityInfo() failed in AssureRunningAsAdministrator hr=0x%08x.\n";
      v4 = 259;
LABEL_14:
      PuDbgPrint(g_pDebug, "inetsrv\\iis\\mb\\metadata\\cofact.cxx", v4, "AssureRunningAsAdministrator", v3);
    }
  }
  else if ( ppsidOwner )
  {
    v2 = 0;
    if ( !IsWellKnownSid(ppsidOwner, WinLogonIdsSid)
      && !IsWellKnownSid(ppsidOwner, WinBuiltinAdministratorsSid)
      && !IsWellKnownSid(ppsidOwner, WinLocalSystemSid) )
    {
      v2 = -2147024891;
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        v3 = "Not running as Administrators/LocalSystem in AssureRunningInIISADMIN.\n";
        v4 = 287;
        goto LABEL_14;
      }
    }
  }
  else
  {
    v2 = -2147467259;
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\cofact.cxx",
        267,
        "AssureRunningAsAdministrator",
        "GetSecurityInfo() returned NULL sid.\n");
  }
  if ( hMem )
    LocalFree(hMem);
  return v2;
}

```

## disassembly

```asm
0x180015948  push    rbx
0x18001594a  sub     rsp, 40h
0x18001594e  mov     [rsp+48h+ppsidOwner], 0
0x180015957  mov     [rsp+48h+hMem], 0
0x180015960  call    cs:__imp_GetCurrentProcess
0x180015966  mov     edx, 6; ObjectType
0x18001596b  lea     r9, [rsp+48h+ppsidOwner]; ppsidOwner
0x180015970  mov     rcx, rax; handle
0x180015973  lea     rax, [rsp+48h+hMem]
0x180015978  mov     [rsp+48h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18001597d  mov     [rsp+48h+ppSacl], 0; ppSacl
0x180015986  mov     [rsp+48h+ppDacl], 0; ppDacl
0x18001598f  lea     r8d, [rdx-5]; SecurityInfo
0x180015993  mov     [rsp+48h+ppsidGroup], 0; ppsidGroup
0x18001599c  call    cs:__imp_GetSecurityInfo
0x1800159a2  mov     ebx, eax
0x1800159a4  test    eax, eax
0x1800159a6  jz      short loc_1800159D2
0x1800159a8  jle     short loc_1800159B3
0x1800159aa  movzx   ebx, ax
0x1800159ad  or      ebx, 80070000h
0x1800159b3  test    byte ptr cs:g_dwDebugFlags, 3
0x1800159ba  jz      loc_180015A8F
0x1800159c0  lea     rax, aGetsecurityinf_0; "GetSecurityInfo() failed in AssureRunni"...
0x1800159c7  mov     r8d, 103h
0x1800159cd  jmp     loc_180015A6B
0x1800159d2  mov     rcx, [rsp+48h+ppsidOwner]; pSid
0x1800159d7  test    rcx, rcx
0x1800159da  jnz     short loc_180015A1D
0x1800159dc  test    byte ptr cs:g_dwDebugFlags, 3
0x1800159e3  mov     ebx, 80004005h
0x1800159e8  jz      loc_180015A8F
0x1800159ee  mov     rcx, cs:g_pDebug
0x1800159f5  lea     rax, aGetsecurityinf; "GetSecurityInfo() returned NULL sid.\n"
0x1800159fc  lea     r9, aAssurerunninga; "AssureRunningAsAdministrator"
0x180015a03  mov     [rsp+48h+ppsidGroup], rax
0x180015a08  mov     r8d, 10Bh
0x180015a0e  lea     rdx, aInetsrvIisMbMe_3; "inetsrv\\iis\\mb\\metadata\\cofact.cxx"
0x180015a15  call    cs:__imp_PuDbgPrint
0x180015a1b  jmp     short loc_180015A8F
0x180015a1d  xor     ebx, ebx
0x180015a1f  lea     edx, [rbx+15h]; WellKnownSidType
0x180015a22  call    cs:__imp_IsWellKnownSid
0x180015a28  test    eax, eax
0x180015a2a  jnz     short loc_180015A8F
0x180015a2c  mov     rcx, [rsp+48h+ppsidOwner]; pSid
0x180015a31  lea     edx, [rbx+1Ah]; WellKnownSidType
0x180015a34  call    cs:__imp_IsWellKnownSid
0x180015a3a  test    eax, eax
0x180015a3c  jnz     short loc_180015A8F
0x180015a3e  mov     rcx, [rsp+48h+ppsidOwner]; pSid
0x180015a43  lea     edx, [rbx+16h]; WellKnownSidType
0x180015a46  call    cs:__imp_IsWellKnownSid
0x180015a4c  test    eax, eax
0x180015a4e  jnz     short loc_180015A8F
0x180015a50  test    byte ptr cs:g_dwDebugFlags, 3
0x180015a57  mov     ebx, 80070005h
0x180015a5c  jz      short loc_180015A8F
0x180015a5e  lea     rax, aNotRunningAsAd; "Not running as Administrators/LocalSyst"...
0x180015a65  mov     r8d, 11Fh
0x180015a6b  mov     rcx, cs:g_pDebug
0x180015a72  lea     r9, aAssurerunninga; "AssureRunningAsAdministrator"
0x180015a79  mov     dword ptr [rsp+48h+ppDacl], ebx
0x180015a7d  lea     rdx, aInetsrvIisMbMe_3; "inetsrv\\iis\\mb\\metadata\\cofact.cxx"
0x180015a84  mov     [rsp+48h+ppsidGroup], rax
0x180015a89  call    cs:__imp_PuDbgPrint
0x180015a8f  mov     rcx, [rsp+48h+hMem]; hMem
0x180015a94  test    rcx, rcx
0x180015a97  jz      short loc_180015A9F
0x180015a99  call    cs:__imp_LocalFree
0x180015a9f  mov     eax, ebx
0x180015aa1  add     rsp, 40h
0x180015aa5  pop     rbx
0x180015aa6  retn
```
