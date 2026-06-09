# HHAccessCheck(char *,ulong)

- ea: `0x18004e790`
- end: `0x18004e952`
- name: `?HHAccessCheck@@YA_NPEADK@Z`
- size: `450`
- prototype: `bool __fastcall(LPCSTR pObjectName, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18004ec38`
- `0x18004f3cc`

## callees

- `0x18004e790`
- `0x18004f5e4`
- `0x180075c90`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18004e924`
- `KERNEL32!CloseHandle` at `0x18004e924`
- `KERNEL32!LocalFree` at `0x18004e914`
- `KERNEL32!LocalFree` at `0x18004e914`
- `KERNEL32!GetCurrentThread` at `0x18004e836`
- `KERNEL32!GetCurrentThread` at `0x18004e836`
- `KERNEL32!GetCurrentProcess` at `0x18004e865`
- `KERNEL32!GetCurrentProcess` at `0x18004e865`
- `KERNEL32!GetLastError` at `0x18004e858`
- `KERNEL32!GetLastError` at `0x18004e858`
- `ADVAPI32!GetNamedSecurityInfoA` at `0x18004e80c`
- `ADVAPI32!GetNamedSecurityInfoA` at `0x18004e80c`
- `ADVAPI32!ImpersonateSelf` at `0x18004e828`
- `ADVAPI32!ImpersonateSelf` at `0x18004e828`
- `ADVAPI32!OpenThreadToken` at `0x18004e84e`
- `ADVAPI32!OpenThreadToken` at `0x18004e84e`
- `ADVAPI32!OpenProcessToken` at `0x18004e874`
- `ADVAPI32!OpenProcessToken` at `0x18004e874`
- `ADVAPI32!MapGenericMask` at `0x18004e8c5`
- `ADVAPI32!MapGenericMask` at `0x18004e8c5`
- `ADVAPI32!AccessCheck` at `0x18004e8ff`
- `ADVAPI32!AccessCheck` at `0x18004e8ff`
- `ADVAPI32!RevertToSelf` at `0x18004e905`
- `ADVAPI32!RevertToSelf` at `0x18004e905`

## pseudocode

```c
bool __fastcall HHAccessCheck(LPCSTR pObjectName, DWORD a2)
{
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  void *TokenHandle; // [rsp+40h] [rbp-9h] BYREF
  DWORD AccessMask; // [rsp+48h] [rbp-1h] BYREF
  WINBOOL AccessStatus; // [rsp+50h] [rbp+7h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+58h] [rbp+Fh] BYREF
  DWORD GrantedAccess; // [rsp+60h] [rbp+17h] BYREF
  DWORD PrivilegeSetLength; // [rsp+64h] [rbp+1Bh] BYREF
  _GENERIC_MAPPING GenericMapping; // [rsp+68h] [rbp+1Fh] BYREF
  _PRIVILEGE_SET PrivilegeSet; // [rsp+78h] [rbp+2Fh] BYREF

  AccessMask = a2;
  if ( !(unsigned int)IsNT() )
    return 1;
  pSecurityDescriptor = 0;
  TokenHandle = (void *)-1LL;
  AccessStatus = 0;
  if ( GetNamedSecurityInfoA(pObjectName, SE_FILE_OBJECT, 7u, 0, 0, 0, 0, &pSecurityDescriptor) )
    goto LABEL_12;
  if ( pSecurityDescriptor )
  {
    if ( ImpersonateSelf(SecurityImpersonation) )
    {
      CurrentThread = GetCurrentThread();
      if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
      {
        if ( GetLastError() == 1008 )
        {
          CurrentProcess = GetCurrentProcess();
          OpenProcessToken(CurrentProcess, 8u, &TokenHandle);
        }
        else
        {
          TokenHandle = (void *)-1LL;
        }
      }
      if ( TokenHandle != (void *)-1LL )
      {
        GenericMapping.GenericRead = 1179785;
        GrantedAccess = 0;
        GenericMapping.GenericWrite = 1179926;
        memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
        GenericMapping.GenericExecute = 1179808;
        GenericMapping.GenericAll = 2032127;
        PrivilegeSetLength = 20;
        MapGenericMask(&AccessMask, &GenericMapping);
        AccessCheck(
          pSecurityDescriptor,
          TokenHandle,
          AccessMask,
          &GenericMapping,
          &PrivilegeSet,
          &PrivilegeSetLength,
          &GrantedAccess,
          &AccessStatus);
      }
      RevertToSelf();
    }
LABEL_12:
    if ( pSecurityDescriptor )
      LocalFree(pSecurityDescriptor);
  }
  if ( TokenHandle != (void *)-1LL )
    CloseHandle(TokenHandle);
  return AccessStatus != 0;
}

```

## disassembly

```asm
0x18004e790  mov     [rsp-8+arg_10], rbx
0x18004e795  push    rbp
0x18004e796  lea     rbp, [rsp-57h]
0x18004e79b  sub     rsp, 0A0h
0x18004e7a2  mov     rax, cs:__security_cookie
0x18004e7a9  xor     rax, rsp
0x18004e7ac  mov     [rbp+57h+var_10], rax
0x18004e7b0  mov     rbx, rcx
0x18004e7b3  mov     [rbp+57h+AccessMask], edx
0x18004e7b6  call    ?IsNT@@YAHXZ; IsNT(void)
0x18004e7bb  test    eax, eax
0x18004e7bd  jz      loc_18004E933
0x18004e7c3  xor     r9d, r9d; ppsidOwner
0x18004e7c6  mov     [rbp+57h+pSecurityDescriptor], 0
0x18004e7ce  lea     rax, [rbp+57h+pSecurityDescriptor]
0x18004e7d2  mov     [rbp+57h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18004e7da  mov     [rsp+0A0h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18004e7df  mov     rcx, rbx; pObjectName
0x18004e7e2  mov     [rsp+0A0h+ppSacl], 0; ppSacl
0x18004e7eb  lea     edx, [r9+1]; ObjectType
0x18004e7ef  mov     [rsp+0A0h+ppDacl], 0; ppDacl
0x18004e7f8  lea     r8d, [r9+7]; SecurityInfo
0x18004e7fc  mov     [rbp+57h+AccessStatus], 0
0x18004e803  mov     [rsp+0A0h+ppsidGroup], 0; ppsidGroup
0x18004e80c  call    cs:__imp_GetNamedSecurityInfoA
0x18004e812  test    eax, eax
0x18004e814  jnz     loc_18004E90B
0x18004e81a  cmp     [rbp+57h+pSecurityDescriptor], 0
0x18004e81f  jz      loc_18004E91A
0x18004e825  lea     ecx, [rax+2]; ImpersonationLevel
0x18004e828  call    cs:__imp_ImpersonateSelf
0x18004e82e  test    eax, eax
0x18004e830  jz      loc_18004E90B
0x18004e836  call    cs:__imp_GetCurrentThread
0x18004e83c  mov     ebx, 8
0x18004e841  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18004e845  mov     rcx, rax; ThreadHandle
0x18004e848  mov     edx, ebx; DesiredAccess
0x18004e84a  lea     r8d, [rbx-7]; OpenAsSelf
0x18004e84e  call    cs:__imp_OpenThreadToken
0x18004e854  test    eax, eax
0x18004e856  jnz     short loc_18004E884
0x18004e858  call    cs:__imp_GetLastError
0x18004e85e  cmp     eax, 3F0h
0x18004e863  jnz     short loc_18004E87C
0x18004e865  call    cs:__imp_GetCurrentProcess
0x18004e86b  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x18004e86f  mov     edx, ebx; DesiredAccess
0x18004e871  mov     rcx, rax; ProcessHandle
0x18004e874  call    cs:__imp_OpenProcessToken
0x18004e87a  jmp     short loc_18004E884
0x18004e87c  mov     [rbp+57h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18004e884  cmp     [rbp+57h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18004e889  jz      short loc_18004E905
0x18004e88b  xor     eax, eax
0x18004e88d  mov     [rbp+57h+GenericMapping.GenericRead], 120089h
0x18004e894  xorps   xmm0, xmm0
0x18004e897  mov     [rbp+57h+PrivilegeSet.Privilege.Attributes], eax
0x18004e89a  lea     rdx, [rbp+57h+GenericMapping]; GenericMapping
0x18004e89e  mov     [rbp+57h+GrantedAccess], eax
0x18004e8a1  lea     rcx, [rbp+57h+AccessMask]; AccessMask
0x18004e8a5  mov     [rbp+57h+GenericMapping.GenericWrite], 120116h
0x18004e8ac  movups  xmmword ptr [rbp+57h+PrivilegeSet.PrivilegeCount], xmm0
0x18004e8b0  mov     [rbp+57h+GenericMapping.GenericExecute], 1200A0h
0x18004e8b7  mov     [rbp+57h+GenericMapping.GenericAll], 1F01FFh
0x18004e8be  mov     [rbp+57h+PrivilegeSetLength], 14h
0x18004e8c5  call    cs:__imp_MapGenericMask
0x18004e8cb  mov     r8d, [rbp+57h+AccessMask]; DesiredAccess
0x18004e8cf  lea     rax, [rbp+57h+AccessStatus]
0x18004e8d3  mov     rdx, [rbp+57h+TokenHandle]; ClientToken
0x18004e8d7  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x18004e8db  mov     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x18004e8df  mov     [rsp+0A0h+ppSecurityDescriptor], rax; AccessStatus
0x18004e8e4  lea     rax, [rbp+57h+GrantedAccess]
0x18004e8e8  mov     [rsp+0A0h+ppSacl], rax; GrantedAccess
0x18004e8ed  lea     rax, [rbp+57h+PrivilegeSetLength]
0x18004e8f1  mov     [rsp+0A0h+ppDacl], rax; PrivilegeSetLength
0x18004e8f6  lea     rax, [rbp+57h+PrivilegeSet]
0x18004e8fa  mov     [rsp+0A0h+ppsidGroup], rax; PrivilegeSet
0x18004e8ff  call    cs:__imp_AccessCheck
0x18004e905  call    cs:__imp_RevertToSelf
0x18004e90b  mov     rcx, [rbp+57h+pSecurityDescriptor]; hMem
0x18004e90f  test    rcx, rcx
0x18004e912  jz      short loc_18004E91A
0x18004e914  call    cs:__imp_LocalFree
0x18004e91a  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18004e91e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18004e922  jz      short loc_18004E92A
0x18004e924  call    cs:__imp_CloseHandle
0x18004e92a  cmp     [rbp+57h+AccessStatus], 0
0x18004e92e  setnz   al
0x18004e931  jmp     short loc_18004E935
0x18004e933  mov     al, 1
0x18004e935  mov     rcx, [rbp+57h+var_10]
0x18004e939  xor     rcx, rsp; StackCookie
0x18004e93c  call    __security_check_cookie
0x18004e941  mov     rbx, [rsp+0A0h+arg_10]
0x18004e949  add     rsp, 0A0h
0x18004e950  pop     rbp
0x18004e951  retn
```
