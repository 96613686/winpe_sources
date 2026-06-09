# MakeAdminRegKeyOwner(HKEY__ *,ushort const *)

- ea: `0x180198d20`
- end: `0x180198f42`
- name: `?MakeAdminRegKeyOwner@@YAHPEAUHKEY__@@PEBG@Z`
- size: `546`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180195edc`

## callees

- `0x180040908`
- `0x180198d20`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `ADVAPI32!OpenProcessToken` at `0x180198d9e`
- `ADVAPI32!OpenProcessToken` at `0x180198d9e`
- `ADVAPI32!LookupPrivilegeValueW` at `0x180198dbf`
- `ADVAPI32!LookupPrivilegeValueW` at `0x180198dbf`
- `ADVAPI32!AdjustTokenPrivileges` at `0x180198e02`
- `ADVAPI32!AdjustTokenPrivileges` at `0x180198ef5`
- `ADVAPI32!AdjustTokenPrivileges` at `0x180198e02`
- `ADVAPI32!AdjustTokenPrivileges` at `0x180198ef5`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180198e50`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180198e50`
- `ADVAPI32!FreeSid` at `0x180198eb6`
- `ADVAPI32!FreeSid` at `0x180198eb6`
- `ADVAPI32!RegCloseKey` at `0x180198ecb`
- `ADVAPI32!RegCloseKey` at `0x180198ecb`
- `KERNEL32!CloseHandle` at `0x180198f0b`
- `KERNEL32!CloseHandle` at `0x180198f0b`
- `KERNEL32!GetCurrentProcess` at `0x180198d87`
- `KERNEL32!GetCurrentProcess` at `0x180198d87`

## string_xrefs

- `0x180198db8`: `SeTakeOwnershipPrivilege`

## pseudocode

```c
_BOOL8 __fastcall MakeAdminRegKeyOwner(HKEY a1, const unsigned __int16 *a2)
{
  BOOL v2; // ebx
  int v3; // edi
  HANDLE CurrentProcess; // rax
  unsigned int v7; // r8d
  void *TokenHandle; // [rsp+60h] [rbp-19h] BYREF
  DWORD ReturnLength; // [rsp+68h] [rbp-11h] BYREF
  PSID pSid; // [rsp+70h] [rbp-9h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-1h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+80h] [rbp+7h] BYREF
  struct _LUID Luid[2]; // [rsp+88h] [rbp+Fh] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+98h] [rbp+1Fh] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  pSid = 0;
  hKey = 0;
  v2 = 0;
  *(_OWORD *)&Luid[0].LowPart = 0;
  ReturnLength = 0;
  v3 = 0;
  NewState = 0;
  TokenHandle = (void *)-1LL;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
  {
    if ( LookupPrivilegeValueW(0, L"SeTakeOwnershipPrivilege", (PLUID)&Luid[0].HighPart) )
    {
      Luid[0].LowPart = 1;
      Luid[1].HighPart = 2;
      if ( AdjustTokenPrivileges(TokenHandle, 0, (PTOKEN_PRIVILEGES)Luid, 0x10u, &NewState, &ReturnLength) )
      {
        v3 = 1;
        if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &pSid) )
        {
          if ( !MsiRegOpen64bitKey(a1, a2, v7, 0x80000u, &hKey) )
            v2 = ((__int64 (__fastcall *)(HKEY, __int64, __int64, PSID, _QWORD, _QWORD, _QWORD))ADVAPI32::SetSecurityInfo)(
                   hKey,
                   4,
                   1,
                   pSid,
                   0,
                   0,
                   0) == 0;
        }
      }
    }
  }
  if ( pSid )
    FreeSid(pSid);
  if ( hKey )
    RegCloseKey(hKey);
  if ( v3 )
    AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, 0, 0);
  if ( TokenHandle != (void *)-1LL )
    CloseHandle(TokenHandle);
  return v2;
}

```

## disassembly

```asm
0x180198d20  mov     [rsp-8+arg_10], rbx
0x180198d25  mov     [rsp-8+arg_18], rsi
0x180198d2a  push    rbp
0x180198d2b  push    rdi
0x180198d2c  push    r12
0x180198d2e  push    r14
0x180198d30  push    r15
0x180198d32  lea     rbp, [rsp-37h]
0x180198d37  sub     rsp, 0B0h
0x180198d3e  mov     rax, cs:__security_cookie
0x180198d45  xor     rax, rsp
0x180198d48  mov     [rbp+57h+var_28], rax
0x180198d4c  xor     r15d, r15d
0x180198d4f  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x180198d55  xorps   xmm0, xmm0
0x180198d58  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r15d
0x180198d5c  xorps   xmm1, xmm1
0x180198d5f  mov     [rbp+57h+var_60], r15
0x180198d63  mov     [rbp+57h+hKey], r15
0x180198d67  mov     ebx, r15d
0x180198d6a  movups  xmmword ptr [rbp+57h+Luid.LowPart], xmm0
0x180198d6e  mov     [rbp+57h+var_68], r15d
0x180198d72  mov     edi, r15d
0x180198d75  movups  xmmword ptr [rbp+57h+NewState.PrivilegeCount], xmm1
0x180198d79  mov     r14, rdx
0x180198d7c  mov     [rbp+57h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x180198d84  mov     rsi, rcx
0x180198d87  call    cs:__imp_GetCurrentProcess
0x180198d8e  nop     dword ptr [rax+rax+00h]
0x180198d93  mov     rcx, rax; ProcessHandle
0x180198d96  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x180198d9a  lea     edx, [r15+28h]; DesiredAccess
0x180198d9e  call    cs:__imp_OpenProcessToken
0x180198da5  nop     dword ptr [rax+rax+00h]
0x180198daa  test    eax, eax
0x180198dac  jz      loc_180198EAD
0x180198db2  lea     r8, [rbp+57h+Luid.HighPart]; lpLuid
0x180198db6  xor     ecx, ecx; lpSystemName
0x180198db8  lea     rdx, aSetakeownershi; "SeTakeOwnershipPrivilege"
0x180198dbf  call    cs:__imp_LookupPrivilegeValueW
0x180198dc6  nop     dword ptr [rax+rax+00h]
0x180198dcb  test    eax, eax
0x180198dcd  jz      loc_180198EAD
0x180198dd3  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180198dd7  lea     rax, [rbp+57h+var_68]
0x180198ddb  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x180198de0  lea     r12d, [r15+1]
0x180198de4  lea     rax, [rbp+57h+NewState]
0x180198de8  mov     [rbp+57h+Luid.LowPart], r12d
0x180198dec  lea     r9d, [r15+10h]; BufferLength
0x180198df0  mov     [rsp+0D0h+PreviousState], rax; PreviousState
0x180198df5  lea     r8, [rbp+57h+Luid]; NewState
0x180198df9  mov     [rbp+57h+Luid.HighPart+8], 2
0x180198e00  xor     edx, edx; DisableAllPrivileges
0x180198e02  call    cs:__imp_AdjustTokenPrivileges
0x180198e09  nop     dword ptr [rax+rax+00h]
0x180198e0e  test    eax, eax
0x180198e10  jz      loc_180198EAD
0x180198e16  lea     rax, [rbp+57h+var_60]
0x180198e1a  mov     r9d, 220h; nSubAuthority1
0x180198e20  mov     [rsp+0D0h+pSid], rax; pSid
0x180198e25  lea     r8d, [r15+20h]; nSubAuthority0
0x180198e29  mov     [rsp+0D0h+nSubAuthority7], r15d; nSubAuthority7
0x180198e2e  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180198e32  mov     [rsp+0D0h+nSubAuthority6], r15d; nSubAuthority6
0x180198e37  mov     dl, 2; nSubAuthorityCount
0x180198e39  mov     [rsp+0D0h+nSubAuthority5], r15d; nSubAuthority5
0x180198e3e  mov     edi, r12d
0x180198e41  mov     [rsp+0D0h+nSubAuthority4], r15d; nSubAuthority4
0x180198e46  mov     dword ptr [rsp+0D0h+ReturnLength], r15d; nSubAuthority3
0x180198e4b  mov     dword ptr [rsp+0D0h+PreviousState], r15d; nSubAuthority2
0x180198e50  call    cs:__imp_AllocateAndInitializeSid
0x180198e57  nop     dword ptr [rax+rax+00h]
0x180198e5c  test    eax, eax
0x180198e5e  jz      short loc_180198EAD
0x180198e60  lea     rax, [rbp+57h+hKey]
0x180198e64  mov     r9d, 80000h; unsigned int
0x180198e6a  mov     rdx, r14; unsigned __int16 *
0x180198e6d  mov     [rsp+0D0h+PreviousState], rax; HKEY *
0x180198e72  mov     rcx, rsi; HKEY
0x180198e75  call    ?MsiRegOpen64bitKey@@YAKPEAUHKEY__@@PEBGKKPEAPEAU1@@Z; MsiRegOpen64bitKey(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x180198e7a  test    eax, eax
0x180198e7c  jnz     short loc_180198EAD
0x180198e7e  mov     r9, [rbp+57h+var_60]
0x180198e82  lea     edx, [rax+4]
0x180198e85  mov     rax, cs:?SetSecurityInfo@ADVAPI32@@3P6AKPEAXW4_SE_OBJECT_TYPE@@K00PEAU_ACL@@2@ZEA; ulong (*ADVAPI32::SetSecurityInfo)(void *,_SE_OBJECT_TYPE,ulong,void *,void *,_ACL *,_ACL *)
0x180198e8c  mov     r8d, r12d
0x180198e8f  mov     rcx, [rbp+57h+hKey]
0x180198e93  mov     qword ptr [rsp+0D0h+nSubAuthority4], r15
0x180198e98  mov     [rsp+0D0h+ReturnLength], r15
0x180198e9d  mov     [rsp+0D0h+PreviousState], r15
0x180198ea2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198ea7  test    eax, eax
0x180198ea9  cmovz   ebx, r12d
0x180198ead  mov     rcx, [rbp+57h+var_60]; pSid
0x180198eb1  test    rcx, rcx
0x180198eb4  jz      short loc_180198EC2
0x180198eb6  call    cs:__imp_FreeSid
0x180198ebd  nop     dword ptr [rax+rax+00h]
0x180198ec2  mov     rcx, [rbp+57h+hKey]; hKey
0x180198ec6  test    rcx, rcx
0x180198ec9  jz      short loc_180198ED7
0x180198ecb  call    cs:__imp_RegCloseKey
0x180198ed2  nop     dword ptr [rax+rax+00h]
0x180198ed7  test    edi, edi
0x180198ed9  jz      short loc_180198F01
0x180198edb  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180198edf  lea     r8, [rbp+57h+NewState]; NewState
0x180198ee3  mov     [rsp+0D0h+ReturnLength], r15; ReturnLength
0x180198ee8  mov     r9d, 10h; BufferLength
0x180198eee  xor     edx, edx; DisableAllPrivileges
0x180198ef0  mov     [rsp+0D0h+PreviousState], r15; PreviousState
0x180198ef5  call    cs:__imp_AdjustTokenPrivileges
0x180198efc  nop     dword ptr [rax+rax+00h]
0x180198f01  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180198f05  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180198f09  jz      short loc_180198F17
0x180198f0b  call    cs:__imp_CloseHandle
0x180198f12  nop     dword ptr [rax+rax+00h]
0x180198f17  mov     eax, ebx
0x180198f19  mov     rcx, [rbp+57h+var_28]
0x180198f1d  xor     rcx, rsp; StackCookie
0x180198f20  call    __security_check_cookie
0x180198f25  lea     r11, [rsp+0D0h+var_20]
0x180198f2d  mov     rbx, [r11+40h]
0x180198f31  mov     rsi, [r11+48h]
0x180198f35  mov     rsp, r11
0x180198f38  pop     r15
0x180198f3a  pop     r14
0x180198f3c  pop     r12
0x180198f3e  pop     rdi
0x180198f3f  pop     rbp
0x180198f40  retn
```
