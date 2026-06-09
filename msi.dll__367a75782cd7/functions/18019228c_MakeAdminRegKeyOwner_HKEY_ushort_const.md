# MakeAdminRegKeyOwner(HKEY__ *,ushort const *)

- ea: `0x18019228c`
- end: `0x180192477`
- name: `?MakeAdminRegKeyOwner@@YAHPEAUHKEY__@@PEBG@Z`
- size: `491`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18018f5e4`

## callees

- `0x180019bb4`
- `0x18019228c`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `ADVAPI32!OpenProcessToken` at `0x180192304`
- `ADVAPI32!OpenProcessToken` at `0x180192304`
- `ADVAPI32!LookupPrivilegeValueW` at `0x18019231f`
- `ADVAPI32!LookupPrivilegeValueW` at `0x18019231f`
- `ADVAPI32!AdjustTokenPrivileges` at `0x18019235c`
- `ADVAPI32!AdjustTokenPrivileges` at `0x180192437`
- `ADVAPI32!AdjustTokenPrivileges` at `0x18019235c`
- `ADVAPI32!AdjustTokenPrivileges` at `0x180192437`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1801923a4`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1801923a4`
- `ADVAPI32!FreeSid` at `0x180192404`
- `ADVAPI32!FreeSid` at `0x180192404`
- `ADVAPI32!RegCloseKey` at `0x180192413`
- `ADVAPI32!RegCloseKey` at `0x180192413`
- `KERNEL32!CloseHandle` at `0x180192447`
- `KERNEL32!CloseHandle` at `0x180192447`
- `KERNEL32!GetCurrentProcess` at `0x1801922f3`
- `KERNEL32!GetCurrentProcess` at `0x1801922f3`

## string_xrefs

- `0x180192318`: `SeTakeOwnershipPrivilege`

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
0x18019228c  mov     [rsp-8+arg_10], rbx
0x180192291  mov     [rsp-8+arg_18], rsi
0x180192296  push    rbp
0x180192297  push    rdi
0x180192298  push    r12
0x18019229a  push    r14
0x18019229c  push    r15
0x18019229e  lea     rbp, [rsp-37h]
0x1801922a3  sub     rsp, 0B0h
0x1801922aa  mov     rax, cs:__security_cookie
0x1801922b1  xor     rax, rsp
0x1801922b4  mov     [rbp+57h+var_28], rax
0x1801922b8  xor     r15d, r15d
0x1801922bb  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x1801922c1  xorps   xmm0, xmm0
0x1801922c4  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r15d
0x1801922c8  xorps   xmm1, xmm1
0x1801922cb  mov     [rbp+57h+var_60], r15
0x1801922cf  mov     [rbp+57h+hKey], r15
0x1801922d3  mov     ebx, r15d
0x1801922d6  movups  xmmword ptr [rbp+57h+Luid.LowPart], xmm0
0x1801922da  mov     [rbp+57h+var_68], r15d
0x1801922de  mov     edi, r15d
0x1801922e1  movups  xmmword ptr [rbp+57h+NewState.PrivilegeCount], xmm1
0x1801922e5  mov     r14, rdx
0x1801922e8  mov     [rbp+57h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x1801922f0  mov     rsi, rcx
0x1801922f3  call    cs:__imp_GetCurrentProcess
0x1801922f9  mov     rcx, rax; ProcessHandle
0x1801922fc  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x180192300  lea     edx, [r15+28h]; DesiredAccess
0x180192304  call    cs:__imp_OpenProcessToken
0x18019230a  test    eax, eax
0x18019230c  jz      loc_1801923FB
0x180192312  lea     r8, [rbp+57h+Luid.HighPart]; lpLuid
0x180192316  xor     ecx, ecx; lpSystemName
0x180192318  lea     rdx, aSetakeownershi; "SeTakeOwnershipPrivilege"
0x18019231f  call    cs:__imp_LookupPrivilegeValueW
0x180192325  test    eax, eax
0x180192327  jz      loc_1801923FB
0x18019232d  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180192331  lea     rax, [rbp+57h+var_68]
0x180192335  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x18019233a  lea     r12d, [r15+1]
0x18019233e  lea     rax, [rbp+57h+NewState]
0x180192342  mov     [rbp+57h+Luid.LowPart], r12d
0x180192346  lea     r9d, [r15+10h]; BufferLength
0x18019234a  mov     [rsp+0D0h+PreviousState], rax; PreviousState
0x18019234f  lea     r8, [rbp+57h+Luid]; NewState
0x180192353  mov     [rbp+57h+Luid.HighPart+8], 2
0x18019235a  xor     edx, edx; DisableAllPrivileges
0x18019235c  call    cs:__imp_AdjustTokenPrivileges
0x180192362  test    eax, eax
0x180192364  jz      loc_1801923FB
0x18019236a  lea     rax, [rbp+57h+var_60]
0x18019236e  mov     r9d, 220h; nSubAuthority1
0x180192374  mov     [rsp+0D0h+pSid], rax; pSid
0x180192379  lea     r8d, [r15+20h]; nSubAuthority0
0x18019237d  mov     [rsp+0D0h+nSubAuthority7], r15d; nSubAuthority7
0x180192382  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180192386  mov     [rsp+0D0h+nSubAuthority6], r15d; nSubAuthority6
0x18019238b  mov     dl, 2; nSubAuthorityCount
0x18019238d  mov     [rsp+0D0h+nSubAuthority5], r15d; nSubAuthority5
0x180192392  mov     edi, r12d
0x180192395  mov     [rsp+0D0h+nSubAuthority4], r15d; nSubAuthority4
0x18019239a  mov     dword ptr [rsp+0D0h+ReturnLength], r15d; nSubAuthority3
0x18019239f  mov     dword ptr [rsp+0D0h+PreviousState], r15d; nSubAuthority2
0x1801923a4  call    cs:__imp_AllocateAndInitializeSid
0x1801923aa  test    eax, eax
0x1801923ac  jz      short loc_1801923FB
0x1801923ae  lea     rax, [rbp+57h+hKey]
0x1801923b2  mov     r9d, 80000h; unsigned int
0x1801923b8  mov     rdx, r14; unsigned __int16 *
0x1801923bb  mov     [rsp+0D0h+PreviousState], rax; HKEY *
0x1801923c0  mov     rcx, rsi; HKEY
0x1801923c3  call    ?MsiRegOpen64bitKey@@YAKPEAUHKEY__@@PEBGKKPEAPEAU1@@Z; MsiRegOpen64bitKey(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x1801923c8  test    eax, eax
0x1801923ca  jnz     short loc_1801923FB
0x1801923cc  mov     r9, [rbp+57h+var_60]
0x1801923d0  lea     edx, [rax+4]
0x1801923d3  mov     rax, cs:?SetSecurityInfo@ADVAPI32@@3P6AKPEAXW4_SE_OBJECT_TYPE@@K00PEAU_ACL@@2@ZEA; ulong (*ADVAPI32::SetSecurityInfo)(void *,_SE_OBJECT_TYPE,ulong,void *,void *,_ACL *,_ACL *)
0x1801923da  mov     r8d, r12d
0x1801923dd  mov     rcx, [rbp+57h+hKey]
0x1801923e1  mov     qword ptr [rsp+0D0h+nSubAuthority4], r15
0x1801923e6  mov     [rsp+0D0h+ReturnLength], r15
0x1801923eb  mov     [rsp+0D0h+PreviousState], r15
0x1801923f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801923f5  test    eax, eax
0x1801923f7  cmovz   ebx, r12d
0x1801923fb  mov     rcx, [rbp+57h+var_60]; pSid
0x1801923ff  test    rcx, rcx
0x180192402  jz      short loc_18019240A
0x180192404  call    cs:__imp_FreeSid
0x18019240a  mov     rcx, [rbp+57h+hKey]; hKey
0x18019240e  test    rcx, rcx
0x180192411  jz      short loc_180192419
0x180192413  call    cs:__imp_RegCloseKey
0x180192419  test    edi, edi
0x18019241b  jz      short loc_18019243D
0x18019241d  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180192421  lea     r8, [rbp+57h+NewState]; NewState
0x180192425  mov     [rsp+0D0h+ReturnLength], r15; ReturnLength
0x18019242a  mov     r9d, 10h; BufferLength
0x180192430  xor     edx, edx; DisableAllPrivileges
0x180192432  mov     [rsp+0D0h+PreviousState], r15; PreviousState
0x180192437  call    cs:__imp_AdjustTokenPrivileges
0x18019243d  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180192441  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180192445  jz      short loc_18019244D
0x180192447  call    cs:__imp_CloseHandle
0x18019244d  mov     eax, ebx
0x18019244f  mov     rcx, [rbp+57h+var_28]
0x180192453  xor     rcx, rsp; StackCookie
0x180192456  call    __security_check_cookie
0x18019245b  lea     r11, [rsp+0D0h+var_20]
0x180192463  mov     rbx, [r11+40h]
0x180192467  mov     rsi, [r11+48h]
0x18019246b  mov     rsp, r11
0x18019246e  pop     r15
0x180192470  pop     r14
0x180192472  pop     r12
0x180192474  pop     rdi
0x180192475  pop     rbp
0x180192476  retn
```
