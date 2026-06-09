# CoVrfCheckSecuritySettings(void)

- ea: `0x18013d560`
- end: `0x18013d5f8`
- name: `?CoVrfCheckSecuritySettings@@YAXXZ`
- size: `152`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180111200`

## callees

- `0x18013d560`
- `0x180255010`

## import_xrefs

- `ntdll!RtlApplicationVerifierStop` at `0x18024e5b9`
- `ntdll!RtlApplicationVerifierStop` at `0x18024e64f`
- `ntdll!RtlApplicationVerifierStop` at `0x18024e5b9`
- `ntdll!RtlApplicationVerifierStop` at `0x18024e64f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18024e659`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18024e663`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18024e659`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18024e663`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18013d5a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18013d5a7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18013d5b9`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18013d5b9`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18013d5de`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18013d5de`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18024e5d6`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18024e5d6`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18024e5f2`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18024e5f2`

## string_xrefs

- `0x18024e573`: `Security Descriptor`
- `0x18024e611`: `Security Descriptor`
- `0x18024e581`: `Calling CoInitializeSecurity with NULL DACL`
- `0x18024e61d`: `Calling CoInitializeSecurity with NULL DACL`

## pseudocode

```c
void CoVrfCheckSecuritySettings(void)
{
  HANDLE CurrentProcess; // rax
  int fIsLocalSystem; // [rsp+90h] [rbp+28h] BYREF
  void *hImpToken; // [rsp+98h] [rbp+30h] BYREF
  void *hToken; // [rsp+A0h] [rbp+38h] BYREF
  _ACL *pACL; // [rsp+A8h] [rbp+40h] BYREF

  if ( ComVerifierSettings::s_singleton._pSettingsState
    && ComVerifierSettings::s_singleton._pSettingsState->_fEnableVerifySecurity )
  {
    if ( gSecDesc )
    {
      fIsLocalSystem = 0;
      LODWORD(hImpToken) = 0;
      pACL = 0;
      GetSecurityDescriptorDacl(gSecDesc, &fIsLocalSystem, &pACL, (LPBOOL)&hImpToken);
      if ( !fIsLocalSystem || !pACL )
      {
        if ( gMockApplicationVerifierStop )
          gMockApplicationVerifierStop(
            268436486u,
            "Calling CoInitializeSecurity with NULL DACL",
            (unsigned __int64)gSecDesc,
            "Security Descriptor",
            0,
            (char *)Description4,
            0,
            (char *)Description4,
            0,
            (char *)Description4);
        else
          RtlApplicationVerifierStop(
            0x10000406u,
            "Calling CoInitializeSecurity with NULL DACL",
            gSecDesc,
            "Security Descriptor",
            0,
            Description4,
            0,
            Description4,
            0,
            Description4);
      }
    }
    hToken = 0;
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 2u, &hToken) )
    {
      hImpToken = 0;
      if ( DuplicateToken(hToken, SecurityImpersonation, &hImpToken) )
      {
        fIsLocalSystem = 0;
        if ( CheckTokenMembership(hImpToken, &LOCAL_SYSTEM_SID_0, &fIsLocalSystem) && fIsLocalSystem && !gSecDesc )
        {
          if ( gMockApplicationVerifierStop )
            gMockApplicationVerifierStop(
              268436486u,
              "Calling CoInitializeSecurity with NULL DACL",
              0,
              "Security Descriptor",
              0,
              (char *)Description4,
              0,
              (char *)Description4,
              0,
              (char *)Description4);
          else
            RtlApplicationVerifierStop(
              0x10000406u,
              "Calling CoInitializeSecurity with NULL DACL",
              0,
              "Security Descriptor",
              0,
              Description4,
              0,
              Description4,
              0,
              Description4);
        }
        CloseHandle(hImpToken);
      }
      CloseHandle(hToken);
    }
  }
}

```

## disassembly

```asm
0x18013d560  push    rbp
0x18013d562  push    rbx
0x18013d563  push    rdi
0x18013d564  push    r15
0x18013d566  mov     rbp, rsp
0x18013d569  sub     rsp, 68h
0x18013d56d  mov     rax, cs:?s_singleton@ComVerifierSettings@@0V1@A._pSettingsState; ComVerifierSettings ComVerifierSettings::s_singleton ...
0x18013d574  xor     ebx, ebx
0x18013d576  test    rax, rax
0x18013d579  jnz     short loc_18013D585
0x18013d57b  add     rsp, 68h
0x18013d57f  pop     r15
0x18013d581  pop     rdi
0x18013d582  pop     rbx
0x18013d583  pop     rbp
0x18013d584  retn
0x18013d585  cmp     [rax+7], bl
0x18013d588  jz      short loc_18013D57B
0x18013d58a  mov     rcx, cs:?gSecDesc@@3PEAU_SECURITY_DESCRIPTOR@@EA; pSecurityDescriptor
0x18013d591  lea     rdi, Description4
0x18013d598  mov     r15d, 10000406h
0x18013d59e  test    rcx, rcx
0x18013d5a1  jnz     short loc_18013D5C8
0x18013d5a3  mov     [rbp+hToken], rbx
0x18013d5a7  call    cs:__imp_GetCurrentProcess
0x18013d5ad  lea     r8, [rbp+hToken]; TokenHandle
0x18013d5b1  mov     edx, 2; DesiredAccess
0x18013d5b6  mov     rcx, rax; ProcessHandle
0x18013d5b9  call    cs:__imp_OpenProcessToken
0x18013d5bf  test    eax, eax
0x18013d5c1  jz      short loc_18013D57B
0x18013d5c3  jmp     loc_18024E5C5
0x18013d5c8  lea     r9, [rbp+hImpToken]; lpbDaclDefaulted
0x18013d5cc  mov     [rbp+fIsLocalSystem], ebx
0x18013d5cf  lea     r8, [rbp+pACL]; pDacl
0x18013d5d3  mov     dword ptr [rbp+hImpToken], ebx
0x18013d5d6  lea     rdx, [rbp+fIsLocalSystem]; lpbDaclPresent
0x18013d5da  mov     [rbp+pACL], rbx
0x18013d5de  call    cs:__imp_GetSecurityDescriptorDacl
0x18013d5e4  cmp     [rbp+fIsLocalSystem], ebx
0x18013d5e7  jz      loc_18024E56C
0x18013d5ed  cmp     [rbp+pACL], rbx
0x18013d5f1  jnz     short loc_18013D5A3
0x18013d5f3  jmp     loc_18024E56C
0x18024e56c  mov     rax, cs:?gMockApplicationVerifierStop@@3P6AX_KPEAD01010101@ZEA; void (*gMockApplicationVerifierStop)(unsigned __int64,char *,unsigned __int64,char *,unsigned __int64,char *,unsigned __int64,char *,unsigned __int64,char *)
0x18024e573  lea     r9, aSecurityDescri; "Security Descriptor"
0x18024e57a  mov     r8, cs:?gSecDesc@@3PEAU_SECURITY_DESCRIPTOR@@EA; Value1
0x18024e581  lea     rdx, aCallingCoiniti; "Calling CoInitializeSecurity with NULL "...
0x18024e588  mov     [rsp+68h+Description4], rdi; Description4
0x18024e58d  mov     rcx, r15; Code
0x18024e590  mov     [rsp+68h+Value4], rbx; Value4
0x18024e595  mov     [rsp+68h+Description3], rdi; Description3
0x18024e59a  mov     [rsp+68h+Value3], rbx; Value3
0x18024e59f  mov     [rsp+68h+Description2], rdi; Description2
0x18024e5a4  mov     [rsp+68h+Value2], rbx; Value2
0x18024e5a9  test    rax, rax
0x18024e5ac  jz      short loc_18024E5B9
0x18024e5ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024e5b3  nop
0x18024e5b4  jmp     loc_18013D5A3
0x18024e5b9  call    cs:__imp_RtlApplicationVerifierStop
0x18024e5bf  nop
0x18024e5c0  jmp     loc_18013D5A3
0x18024e5c5  mov     rcx, [rbp+hToken]; ExistingTokenHandle
0x18024e5c9  lea     r8, [rbp+hImpToken]; DuplicateTokenHandle
0x18024e5cd  mov     edx, 2; ImpersonationLevel
0x18024e5d2  mov     [rbp+hImpToken], rbx
0x18024e5d6  call    cs:__imp_DuplicateToken
0x18024e5dc  test    eax, eax
0x18024e5de  jz      short loc_18024E65F
0x18024e5e0  mov     rcx, [rbp+hImpToken]; TokenHandle
0x18024e5e4  lea     r8, [rbp+fIsLocalSystem]; IsMember
0x18024e5e8  lea     rdx, LOCAL_SYSTEM_SID_0; SidToCheck
0x18024e5ef  mov     [rbp+fIsLocalSystem], ebx
0x18024e5f2  call    cs:__imp_CheckTokenMembership
0x18024e5f8  test    eax, eax
0x18024e5fa  jz      short loc_18024E655
0x18024e5fc  cmp     [rbp+fIsLocalSystem], ebx
0x18024e5ff  jz      short loc_18024E655
0x18024e601  cmp     cs:?gSecDesc@@3PEAU_SECURITY_DESCRIPTOR@@EA, rbx; _SECURITY_DESCRIPTOR * gSecDesc
0x18024e608  jnz     short loc_18024E655
0x18024e60a  mov     rax, cs:?gMockApplicationVerifierStop@@3P6AX_KPEAD01010101@ZEA; void (*gMockApplicationVerifierStop)(unsigned __int64,char *,unsigned __int64,char *,unsigned __int64,char *,unsigned __int64,char *,unsigned __int64,char *)
0x18024e611  lea     r9, aSecurityDescri; "Security Descriptor"
0x18024e618  mov     [rsp+68h+Description4], rdi; Description4
0x18024e61d  lea     rdx, aCallingCoiniti; "Calling CoInitializeSecurity with NULL "...
0x18024e624  mov     [rsp+68h+Value4], rbx; Value4
0x18024e629  xor     r8d, r8d; Value1
0x18024e62c  mov     [rsp+68h+Description3], rdi; Description3
0x18024e631  mov     rcx, r15; Code
0x18024e634  mov     [rsp+68h+Value3], rbx; Value3
0x18024e639  mov     [rsp+68h+Description2], rdi; Description2
0x18024e63e  mov     [rsp+68h+Value2], rbx; Value2
0x18024e643  test    rax, rax
0x18024e646  jz      short loc_18024E64F
0x18024e648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024e64d  jmp     short loc_18024E655
0x18024e64f  call    cs:__imp_RtlApplicationVerifierStop
0x18024e655  mov     rcx, [rbp+hImpToken]; hObject
0x18024e659  call    cs:__imp_CloseHandle
0x18024e65f  mov     rcx, [rbp+hToken]; hObject
0x18024e663  call    cs:__imp_CloseHandle
0x18024e669  nop
0x18024e66a  jmp     loc_18013D57B
```
