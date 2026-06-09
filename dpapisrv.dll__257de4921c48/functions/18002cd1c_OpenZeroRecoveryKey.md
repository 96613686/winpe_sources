# OpenZeroRecoveryKey

- ea: `0x18002cd1c`
- end: `0x18002cf09`
- name: `OpenZeroRecoveryKey`
- size: `493`
- prototype: `__int64 __fastcall(REGSAM samDesired, PHKEY phkResult)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002c834`
- `0x18002def8`

## callees

- `0x180007f10`
- `0x180013c10`
- `0x18001c9c0`
- `0x18002a694`
- `0x18002cd1c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002cec7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002cec7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002cdd2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002cdd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ce3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ce3c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002ce2c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002ce2c`

## string_xrefs

- `0x18002cd7b`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x18002cdec`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x18002ce59`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`

## pseudocode

```c
__int64 __fastcall OpenZeroRecoveryKey(REGSAM samDesired, PHKEY phkResult)
{
  DWORD LastError; // ebx
  __int64 v5; // r9
  unsigned int v7; // eax
  __int64 v8; // r9
  __int64 v9; // rcx
  unsigned int v10; // eax
  PSECURITY_DESCRIPTOR *p_SecurityDescriptor; // [rsp+50h] [rbp-20h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+58h] [rbp-18h] BYREF
  __int64 SecurityDescriptorSize; // [rsp+A0h] [rbp+30h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+A8h] [rbp+38h] BYREF

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 120, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
  SecurityDescriptorSize = 17;
  LastError = AddPrivilege(17);
  if ( LastError )
  {
    v5 = 7054;
LABEL_6:
    DebugTraceError(LastError, "dwError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", v5);
    return LastError;
  }
  SecurityDescriptorSize = 18;
  LastError = AddPrivilege(18);
  if ( LastError )
  {
    v5 = 7063;
    goto LABEL_6;
  }
  v7 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Cryptography\\Protect\\Recovery",
         0,
         samDesired,
         phkResult);
  if ( v7 )
  {
    DebugTraceError(v7, "dwError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", 7073);
    SecurityDescriptor = 0;
    LODWORD(SecurityDescriptorSize) = 0;
    p_SecurityDescriptor = &SecurityDescriptor;
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
            L"O:SYD:P(A;OICI;KA;;;SY)(A;OICI;WDRC;;;BA)",
            1u,
            &SecurityDescriptor,
            (PULONG)&SecurityDescriptorSize) )
    {
      LastError = GetLastError();
      v8 = 7088;
      v9 = LastError;
LABEL_13:
      DebugTraceError(v9, "dwError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", v8);
      ScopedLocalFree::~ScopedLocalFree((ScopedLocalFree *)&p_SecurityDescriptor);
      return LastError;
    }
    *(_QWORD *)&SecurityAttributes.nLength = 24;
    *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
    SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
    v10 = RegCreateKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Cryptography\\Protect\\Recovery",
            0,
            (LPWSTR)&Class,
            0,
            0x2001Fu,
            &SecurityAttributes,
            phkResult,
            0);
    LastError = v10;
    if ( v10 && v10 != 183 )
    {
      v8 = 7101;
      v9 = v10;
      goto LABEL_13;
    }
    ScopedLocalFree::~ScopedLocalFree((ScopedLocalFree *)&p_SecurityDescriptor);
  }
  return 0;
}

```

## disassembly

```asm
0x18002cd1c  mov     [rsp-18h+arg_0], rbx
0x18002cd21  push    rbp
0x18002cd22  push    rsi
0x18002cd23  push    rdi
0x18002cd24  mov     rbp, rsp
0x18002cd27  sub     rsp, 70h
0x18002cd2b  mov     rdi, rdx
0x18002cd2e  mov     esi, ecx
0x18002cd30  lea     rax, WPP_GLOBAL_Control
0x18002cd37  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cd3e  cmp     rcx, rax
0x18002cd41  jz      short loc_18002CD5E
0x18002cd43  test    byte ptr [rcx+1Ch], 4
0x18002cd47  jz      short loc_18002CD5E
0x18002cd49  mov     edx, 78h ; 'x'
0x18002cd4e  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x18002cd55  mov     rcx, [rcx+10h]
0x18002cd59  call    WPP_SF_
0x18002cd5e  mov     [rbp+SecurityDescriptorSize], 11h
0x18002cd66  mov     rcx, [rbp+SecurityDescriptorSize]
0x18002cd6a  call    AddPrivilege
0x18002cd6f  mov     ebx, eax
0x18002cd71  test    eax, eax
0x18002cd73  jz      short loc_18002CD97
0x18002cd75  mov     r9d, 1B8Eh
0x18002cd7b  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002cd82  lea     rdx, aDwerror; "dwError"
0x18002cd89  mov     ecx, ebx
0x18002cd8b  call    DebugTraceError
0x18002cd90  mov     eax, ebx
0x18002cd92  jmp     loc_18002CEF8
0x18002cd97  mov     [rbp+SecurityDescriptorSize], 12h
0x18002cd9f  mov     rcx, [rbp+SecurityDescriptorSize]
0x18002cda3  call    AddPrivilege
0x18002cda8  mov     ebx, eax
0x18002cdaa  test    eax, eax
0x18002cdac  jz      short loc_18002CDB6
0x18002cdae  mov     r9d, 1B97h
0x18002cdb4  jmp     short loc_18002CD7B
0x18002cdb6  mov     [rsp+70h+phkResult], rdi; phkResult
0x18002cdbb  mov     r9d, esi; samDesired
0x18002cdbe  xor     r8d, r8d; ulOptions
0x18002cdc1  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Cryptography\\Prot"...
0x18002cdc8  mov     rbx, 0FFFFFFFF80000002h
0x18002cdcf  mov     rcx, rbx; hKey
0x18002cdd2  call    cs:__imp_RegOpenKeyExW
0x18002cdd9  nop     dword ptr [rax+rax+00h]
0x18002cdde  test    eax, eax
0x18002cde0  jz      loc_18002CEF6
0x18002cde6  mov     r9d, 1BA1h
0x18002cdec  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002cdf3  lea     rdx, aDwerror; "dwError"
0x18002cdfa  mov     ecx, eax
0x18002cdfc  call    DebugTraceError
0x18002ce01  mov     [rbp+SecurityDescriptor], 0
0x18002ce09  mov     dword ptr [rbp+SecurityDescriptorSize], 0
0x18002ce10  lea     rax, [rbp+SecurityDescriptor]
0x18002ce14  mov     [rbp+var_20], rax
0x18002ce18  lea     r9, [rbp+SecurityDescriptorSize]; SecurityDescriptorSize
0x18002ce1c  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18002ce20  mov     edx, 1; StringSDRevision
0x18002ce25  lea     rcx, aOSydPAOiciKaSy; "O:SYD:P(A;OICI;KA;;;SY)(A;OICI;WDRC;;;B"...
0x18002ce2c  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18002ce33  nop     dword ptr [rax+rax+00h]
0x18002ce38  test    eax, eax
0x18002ce3a  jnz     short loc_18002CE74
0x18002ce3c  call    cs:__imp_GetLastError
0x18002ce43  nop     dword ptr [rax+rax+00h]
0x18002ce48  mov     ebx, eax
0x18002ce4a  mov     r9d, 1BB0h
0x18002ce50  mov     ecx, eax
0x18002ce52  lea     rdx, aDwerror; "dwError"
0x18002ce59  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002ce60  call    DebugTraceError
0x18002ce65  nop
0x18002ce66  lea     rcx, [rbp+var_20]; this
0x18002ce6a  call    ??1ScopedLocalFree@@QEAA@XZ; ScopedLocalFree::~ScopedLocalFree(void)
0x18002ce6f  jmp     loc_18002CD90
0x18002ce74  mov     qword ptr [rbp+SecurityAttributes.nLength], 18h
0x18002ce7c  mov     qword ptr [rbp+SecurityAttributes.bInheritHandle], 0
0x18002ce84  mov     rax, [rbp+SecurityDescriptor]
0x18002ce88  mov     [rbp+SecurityAttributes.lpSecurityDescriptor], rax
0x18002ce8c  mov     [rsp+70h+lpdwDisposition], 0; lpdwDisposition
0x18002ce95  mov     [rsp+70h+var_38], rdi; phkResult
0x18002ce9a  lea     rax, [rbp+SecurityAttributes]
0x18002ce9e  mov     [rsp+70h+lpSecurityAttributes], rax; lpSecurityAttributes
0x18002cea3  mov     [rsp+70h+samDesired], 2001Fh; samDesired
0x18002ceab  mov     dword ptr [rsp+70h+phkResult], 0; dwOptions
0x18002ceb3  lea     r9, Class; lpClass
0x18002ceba  xor     r8d, r8d; Reserved
0x18002cebd  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Cryptography\\Prot"...
0x18002cec4  mov     rcx, rbx; hKey
0x18002cec7  call    cs:__imp_RegCreateKeyExW
0x18002cece  nop     dword ptr [rax+rax+00h]
0x18002ced3  mov     ebx, eax
0x18002ced5  test    eax, eax
0x18002ced7  jz      short loc_18002CEED
0x18002ced9  cmp     eax, 0B7h
0x18002cede  jz      short loc_18002CEED
0x18002cee0  mov     r9d, 1BBDh
0x18002cee6  mov     ecx, eax
0x18002cee8  jmp     loc_18002CE52
0x18002ceed  lea     rcx, [rbp+var_20]; this
0x18002cef1  call    ??1ScopedLocalFree@@QEAA@XZ; ScopedLocalFree::~ScopedLocalFree(void)
0x18002cef6  xor     eax, eax
0x18002cef8  mov     rbx, [rsp+70h+arg_0]
0x18002cf00  add     rsp, 70h
0x18002cf04  pop     rdi
0x18002cf05  pop     rsi
0x18002cf06  pop     rbp
0x18002cf07  retn
```
