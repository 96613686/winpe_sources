# CPushButtonReset::Execute(void)

- ea: `0x18001cc3c`
- end: `0x18001cee1`
- name: `?Execute@CPushButtonReset@@SAJXZ`
- size: `677`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001a6b4`

## callees

- `0x180001008`
- `0x18000113c`
- `0x18001cae4`
- `0x18001cc3c`
- `0x18001cee8`
- `0x18001cffc`
- `0x18001d10c`
- `0x18001f652`
- `0x18001f690`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18001ce7d`
- `ADVAPI32!RegSetValueExW` at `0x18001ce7d`
- `ADVAPI32!RegOpenKeyExW` at `0x18001ce4a`
- `ADVAPI32!RegOpenKeyExW` at `0x18001ce4a`
- `ADVAPI32!RegCloseKey` at `0x18001ce88`
- `ADVAPI32!RegCloseKey` at `0x18001ce88`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18001ceaf`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18001ceaf`

## string_xrefs

- `0x18001cd27`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\NetworkList\Nla\Cache\Intranet`
- `0x18001cd3e`: `NLM profile reset - nla-Cache-Intranet`
- `0x18001cd4a`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\NetworkList\Nla\Cache\IntranetAuth`
- `0x18001cd5c`: `NLM profile reset - nla-Cache-IntranetAuth`

## pseudocode

```c
__int64 CPushButtonReset::Execute(void)
{
  unsigned int v0; // eax
  int v1; // edi
  unsigned int v2; // eax
  int v3; // ebx
  unsigned int v4; // eax
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  REGHANDLE v12; // rcx
  HKEY hKey; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v15[32]; // [rsp+38h] [rbp-30h] BYREF

  memset_0(&CPushButtonReset::_wszErrorInfo, 0, 0x2000u);
  TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_18002F358);
  if ( (unsigned int)dword_18002F358 > 5
    && (qword_18002F368 & 0x400000000000LL) != 0
    && (qword_18002F370 & 0x400000000000LL) == qword_18002F370 )
  {
    tlgWriteTransfer_EventWriteTransfer(&dword_18002F358, &byte_180029097, 0, 0, 2, v15);
  }
  v0 = CPushButtonReset::RunSystemProcess(L"netcfg.exe -d");
  if ( v0 )
  {
    v1 = 0;
    CPushButtonReset::LogPushButtonResetFailure(L"netcfg", v0);
  }
  else
  {
    v1 = 1;
  }
  v2 = CPushButtonReset::RunSystemProcess(L"netsh.exe winsock reset");
  v3 = v2;
  if ( v2 )
    CPushButtonReset::LogPushButtonResetFailure(L"winsock reset", v2);
  else
    v1 = 1;
  v4 = CPushButtonReset::DeleteRegKeySubTree(L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\NetworkList\\Nla\\Cache\\Intranet");
  if ( (v4 & 0xFFFFFFFD) != 0 )
    CPushButtonReset::LogPushButtonResetFailure(L"NLM profile reset - nla-Cache-Intranet", v4);
  v5 = CPushButtonReset::DeleteRegKeySubTree(L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\NetworkList\\Nla\\Cache\\IntranetAuth");
  if ( (v5 & 0xFFFFFFFD) != 0 )
    CPushButtonReset::LogPushButtonResetFailure(L"NLM profile reset - nla-Cache-IntranetAuth", v5);
  v6 = CPushButtonReset::DeleteRegKeySubTree(L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\NetworkList\\Nla\\IntranetEnabled");
  if ( (v6 & 0xFFFFFFFD) != 0 )
    CPushButtonReset::LogPushButtonResetFailure(L"NLM profile reset - nla-IntranetEnabled", v6);
  v7 = CPushButtonReset::DeleteRegKeySubTree(L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\NetworkList\\Nla\\Wireless");
  if ( (v7 & 0xFFFFFFFD) != 0 )
    CPushButtonReset::LogPushButtonResetFailure(L"NLM profile reset - nla-Wireless", v7);
  v8 = CPushButtonReset::DeleteRegKeySubTree(L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\NetworkList\\Profiles");
  if ( (v8 & 0xFFFFFFFD) != 0 )
    CPushButtonReset::LogPushButtonResetFailure(L"NLM profile reset - NetworkList-Profiles", v8);
  v9 = CPushButtonReset::DeleteRegKeySubTree(L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\NetworkList\\Permissions");
  if ( (v9 & 0xFFFFFFFD) != 0 )
    CPushButtonReset::LogPushButtonResetFailure(L"NLM profile reset - NetworkList-Permissions", v9);
  v10 = CPushButtonReset::DeleteRegKeySubTree(L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\NetworkList\\Signatures\\Managed");
  if ( (v10 & 0xFFFFFFFD) != 0 )
    CPushButtonReset::LogPushButtonResetFailure(L"NLM profile reset - Signatures-Managed", v10);
  v11 = CPushButtonReset::DeleteRegKeySubTree(L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\NetworkList\\Signatures\\Unmanaged");
  if ( (v11 & 0xFFFFFFFD) != 0 )
    CPushButtonReset::LogPushButtonResetFailure(L"NLM profile reset - Signatures-Unmanaged", v11);
  if ( v1 )
  {
    hKey = 0;
    if ( !RegOpenKeyExW(HKEY_CURRENT_USER, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\RunOnce", 0, 2u, &hKey) )
    {
      RegSetValueExW(hKey, L"NetworkResetPostReboot", 0, 1u, L"netsh.exe trace postreset", 0x34u);
      RegCloseKey(hKey);
    }
    CPushButtonReset::InitiateReboot();
  }
  v12 = RegHandle;
  dword_18002F358 = 0;
  RegHandle = 0;
  EventUnregister(v12);
  if ( v3 > 0 )
    return (unsigned __int16)v3 | 0x80070000;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001cc3c  mov     [rsp+arg_0], rbx
0x18001cc41  mov     [rsp+arg_8], rbp
0x18001cc46  push    rdi
0x18001cc47  sub     rsp, 60h
0x18001cc4b  mov     rax, cs:__security_cookie
0x18001cc52  xor     rax, rsp
0x18001cc55  mov     [rsp+68h+var_10], rax
0x18001cc5a  xor     edx, edx; Val
0x18001cc5c  lea     rcx, ?_wszErrorInfo@CPushButtonReset@@0PAGA; void *
0x18001cc63  mov     r8d, 2000h; Size
0x18001cc69  call    memset_0
0x18001cc6e  xor     r8d, r8d
0x18001cc71  lea     rcx, dword_18002F358; CallbackContext
0x18001cc78  xor     edx, edx
0x18001cc7a  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18001cc7f  mov     eax, cs:dword_18002F358
0x18001cc85  cmp     eax, 5
0x18001cc88  jbe     short loc_18001CCDD
0x18001cc8a  mov     rdx, cs:qword_18002F370
0x18001cc91  mov     r8, 400000000000h
0x18001cc9b  mov     rax, cs:qword_18002F368
0x18001cca2  test    r8, rax
0x18001cca5  jz      short loc_18001CCDD
0x18001cca7  mov     rax, rdx
0x18001ccaa  and     rax, r8
0x18001ccad  cmp     rax, rdx
0x18001ccb0  jnz     short loc_18001CCDD
0x18001ccb2  lea     rax, [rsp+68h+var_30]
0x18001ccb7  xor     r9d, r9d
0x18001ccba  mov     qword ptr [rsp+68h+cbData], rax
0x18001ccbf  lea     rdx, byte_180029097
0x18001ccc6  xor     r8d, r8d
0x18001ccc9  mov     dword ptr [rsp+68h+phkResult], 2
0x18001ccd1  lea     rcx, dword_18002F358
0x18001ccd8  call    _tlgWriteTransfer_EventWriteTransfer
0x18001ccdd  lea     rcx, aNetcfgExeD; "netcfg.exe -d"
0x18001cce4  call    ?RunSystemProcess@CPushButtonReset@@CAKPEBG@Z; CPushButtonReset::RunSystemProcess(ushort const *)
0x18001cce9  test    eax, eax
0x18001cceb  jnz     short loc_18001CCF2
0x18001cced  lea     edi, [rax+1]
0x18001ccf0  jmp     short loc_18001CD02
0x18001ccf2  xor     edi, edi
0x18001ccf4  lea     rcx, aNetcfg; "netcfg"
0x18001ccfb  mov     edx, eax; unsigned int
0x18001ccfd  call    ?LogPushButtonResetFailure@CPushButtonReset@@CAXPEBGK@Z; CPushButtonReset::LogPushButtonResetFailure(ushort const *,ulong)
0x18001cd02  lea     rcx, aNetshExeWinsoc; "netsh.exe winsock reset"
0x18001cd09  call    ?RunSystemProcess@CPushButtonReset@@CAKPEBG@Z; CPushButtonReset::RunSystemProcess(ushort const *)
0x18001cd0e  mov     ebx, eax
0x18001cd10  test    eax, eax
0x18001cd12  jnz     short loc_18001CD19
0x18001cd14  lea     edi, [rax+1]
0x18001cd17  jmp     short loc_18001CD27
0x18001cd19  mov     edx, ebx; unsigned int
0x18001cd1b  lea     rcx, aWinsockReset; "winsock reset"
0x18001cd22  call    ?LogPushButtonResetFailure@CPushButtonReset@@CAXPEBGK@Z; CPushButtonReset::LogPushButtonResetFailure(ushort const *,ulong)
0x18001cd27  lea     rcx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18001cd2e  call    ?DeleteRegKeySubTree@CPushButtonReset@@CAKPEBG@Z; CPushButtonReset::DeleteRegKeySubTree(ushort const *)
0x18001cd33  mov     ebp, 0FFFFFFFDh
0x18001cd38  test    ebp, eax
0x18001cd3a  jz      short loc_18001CD4A
0x18001cd3c  mov     edx, eax; unsigned int
0x18001cd3e  lea     rcx, aNlmProfileRese_3; "NLM profile reset - nla-Cache-Intranet"
0x18001cd45  call    ?LogPushButtonResetFailure@CPushButtonReset@@CAXPEBGK@Z; CPushButtonReset::LogPushButtonResetFailure(ushort const *,ulong)
0x18001cd4a  lea     rcx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18001cd51  call    ?DeleteRegKeySubTree@CPushButtonReset@@CAKPEBG@Z; CPushButtonReset::DeleteRegKeySubTree(ushort const *)
0x18001cd56  test    ebp, eax
0x18001cd58  jz      short loc_18001CD68
0x18001cd5a  mov     edx, eax; unsigned int
0x18001cd5c  lea     rcx, aNlmProfileRese; "NLM profile reset - nla-Cache-IntranetA"...
0x18001cd63  call    ?LogPushButtonResetFailure@CPushButtonReset@@CAXPEBGK@Z; CPushButtonReset::LogPushButtonResetFailure(ushort const *,ulong)
0x18001cd68  lea     rcx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18001cd6f  call    ?DeleteRegKeySubTree@CPushButtonReset@@CAKPEBG@Z; CPushButtonReset::DeleteRegKeySubTree(ushort const *)
0x18001cd74  test    ebp, eax
0x18001cd76  jz      short loc_18001CD86
0x18001cd78  mov     edx, eax; unsigned int
0x18001cd7a  lea     rcx, aNlmProfileRese_2; "NLM profile reset - nla-IntranetEnabled"
0x18001cd81  call    ?LogPushButtonResetFailure@CPushButtonReset@@CAXPEBGK@Z; CPushButtonReset::LogPushButtonResetFailure(ushort const *,ulong)
0x18001cd86  lea     rcx, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18001cd8d  call    ?DeleteRegKeySubTree@CPushButtonReset@@CAKPEBG@Z; CPushButtonReset::DeleteRegKeySubTree(ushort const *)
0x18001cd92  test    ebp, eax
0x18001cd94  jz      short loc_18001CDA4
0x18001cd96  mov     edx, eax; unsigned int
0x18001cd98  lea     rcx, aNlmProfileRese_1; "NLM profile reset - nla-Wireless"
0x18001cd9f  call    ?LogPushButtonResetFailure@CPushButtonReset@@CAXPEBGK@Z; CPushButtonReset::LogPushButtonResetFailure(ushort const *,ulong)
0x18001cda4  lea     rcx, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18001cdab  call    ?DeleteRegKeySubTree@CPushButtonReset@@CAKPEBG@Z; CPushButtonReset::DeleteRegKeySubTree(ushort const *)
0x18001cdb0  test    ebp, eax
0x18001cdb2  jz      short loc_18001CDC2
0x18001cdb4  mov     edx, eax; unsigned int
0x18001cdb6  lea     rcx, aNlmProfileRese_0; "NLM profile reset - NetworkList-Profile"...
0x18001cdbd  call    ?LogPushButtonResetFailure@CPushButtonReset@@CAXPEBGK@Z; CPushButtonReset::LogPushButtonResetFailure(ushort const *,ulong)
0x18001cdc2  lea     rcx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18001cdc9  call    ?DeleteRegKeySubTree@CPushButtonReset@@CAKPEBG@Z; CPushButtonReset::DeleteRegKeySubTree(ushort const *)
0x18001cdce  test    ebp, eax
0x18001cdd0  jz      short loc_18001CDE0
0x18001cdd2  mov     edx, eax; unsigned int
0x18001cdd4  lea     rcx, aNlmProfileRese_6; "NLM profile reset - NetworkList-Permiss"...
0x18001cddb  call    ?LogPushButtonResetFailure@CPushButtonReset@@CAXPEBGK@Z; CPushButtonReset::LogPushButtonResetFailure(ushort const *,ulong)
0x18001cde0  lea     rcx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18001cde7  call    ?DeleteRegKeySubTree@CPushButtonReset@@CAKPEBG@Z; CPushButtonReset::DeleteRegKeySubTree(ushort const *)
0x18001cdec  test    ebp, eax
0x18001cdee  jz      short loc_18001CDFE
0x18001cdf0  mov     edx, eax; unsigned int
0x18001cdf2  lea     rcx, aNlmProfileRese_4; "NLM profile reset - Signatures-Managed"
0x18001cdf9  call    ?LogPushButtonResetFailure@CPushButtonReset@@CAXPEBGK@Z; CPushButtonReset::LogPushButtonResetFailure(ushort const *,ulong)
0x18001cdfe  lea     rcx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18001ce05  call    ?DeleteRegKeySubTree@CPushButtonReset@@CAKPEBG@Z; CPushButtonReset::DeleteRegKeySubTree(ushort const *)
0x18001ce0a  test    ebp, eax
0x18001ce0c  jz      short loc_18001CE1C
0x18001ce0e  mov     edx, eax; unsigned int
0x18001ce10  lea     rcx, aNlmProfileRese_5; "NLM profile reset - Signatures-Unmanage"...
0x18001ce17  call    ?LogPushButtonResetFailure@CPushButtonReset@@CAXPEBGK@Z; CPushButtonReset::LogPushButtonResetFailure(ushort const *,ulong)
0x18001ce1c  test    edi, edi
0x18001ce1e  jz      short loc_18001CE93
0x18001ce20  lea     rax, [rsp+68h+hKey]
0x18001ce25  mov     [rsp+68h+hKey], 0
0x18001ce2e  mov     r9d, 2; samDesired
0x18001ce34  mov     [rsp+68h+phkResult], rax; phkResult
0x18001ce39  xor     r8d, r8d; ulOptions
0x18001ce3c  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001ce43  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18001ce4a  call    cs:__imp_RegOpenKeyExW
0x18001ce50  test    eax, eax
0x18001ce52  jnz     short loc_18001CE8E
0x18001ce54  mov     rcx, [rsp+68h+hKey]; hKey
0x18001ce59  lea     rax, Data; "netsh.exe trace postreset"
0x18001ce60  mov     [rsp+68h+cbData], 34h ; '4'; cbData
0x18001ce68  lea     rdx, aNetworkresetpo; "NetworkResetPostReboot"
0x18001ce6f  mov     r9d, 1; dwType
0x18001ce75  mov     [rsp+68h+phkResult], rax; lpData
0x18001ce7a  xor     r8d, r8d; Reserved
0x18001ce7d  call    cs:__imp_RegSetValueExW
0x18001ce83  mov     rcx, [rsp+68h+hKey]; hKey
0x18001ce88  call    cs:__imp_RegCloseKey
0x18001ce8e  call    ?InitiateReboot@CPushButtonReset@@CAJXZ; CPushButtonReset::InitiateReboot(void)
0x18001ce93  mov     rcx, cs:RegHandle; RegHandle
0x18001ce9a  mov     cs:dword_18002F358, 0
0x18001cea4  mov     cs:RegHandle, 0
0x18001ceaf  call    cs:__imp_EventUnregister
0x18001ceb5  test    ebx, ebx
0x18001ceb7  jle     short loc_18001CEC2
0x18001ceb9  movzx   ebx, bx
0x18001cebc  or      ebx, 80070000h
0x18001cec2  mov     eax, ebx
0x18001cec4  mov     rcx, [rsp+68h+var_10]
0x18001cec9  xor     rcx, rsp; StackCookie
0x18001cecc  call    __security_check_cookie
0x18001ced1  mov     rbx, [rsp+68h+arg_0]
0x18001ced6  mov     rbp, [rsp+68h+arg_8]
0x18001cedb  add     rsp, 60h
0x18001cedf  pop     rdi
0x18001cee0  retn
```
