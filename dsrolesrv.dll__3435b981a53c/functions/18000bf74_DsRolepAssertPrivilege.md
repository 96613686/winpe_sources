# DsRolepAssertPrivilege

- ea: `0x18000bf74`
- end: `0x18000c03f`
- name: `DsRolepAssertPrivilege`
- size: `203`
- prototype: `__int64 __fastcall(LPCWSTR lpName, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000c600`

## callees

- `0x18000bf74`
- `0x18002c050`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c007`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c007`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c01a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c01a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000bfbb`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000bfbb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000bfaa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000bfaa`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18000bffd`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18000bffd`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18000bfd3`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18000bfd3`

## pseudocode

```c
__int64 __fastcall DsRolepAssertPrivilege(LPCWSTR lpName, int a2)
{
  DWORD LastError; // esi
  HANDLE CurrentProcess; // rax
  void *TokenHandle; // [rsp+30h] [rbp-28h] BYREF
  _LUID Luid[2]; // [rsp+38h] [rbp-20h] BYREF

  TokenHandle = (void *)-1LL;
  *(_OWORD *)&Luid[0].LowPart = 0;
  LastError = 0;
  CurrentProcess = GetCurrentProcess();
  OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle);
  Luid[0].LowPart = 1;
  LookupPrivilegeValueW(0, lpName, (PLUID)&Luid[0].HighPart);
  Luid[1].HighPart = a2 != 0 ? 2 : 0;
  if ( !AdjustTokenPrivileges(TokenHandle, 0, (PTOKEN_PRIVILEGES)Luid, 0, 0, 0) )
    LastError = GetLastError();
  if ( TokenHandle != (void *)-1LL )
    CloseHandle(TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x18000bf74  mov     [rsp+arg_8], rbx
0x18000bf79  mov     [rsp+arg_10], rsi
0x18000bf7e  push    rdi
0x18000bf7f  sub     rsp, 50h
0x18000bf83  mov     rax, cs:__security_cookie
0x18000bf8a  xor     rax, rsp
0x18000bf8d  mov     [rsp+58h+var_10], rax
0x18000bf92  xorps   xmm0, xmm0
0x18000bf95  mov     [rsp+58h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18000bf9e  movups  xmmword ptr [rsp+58h+Luid.LowPart], xmm0
0x18000bfa3  mov     edi, edx
0x18000bfa5  mov     rbx, rcx
0x18000bfa8  xor     esi, esi
0x18000bfaa  call    cs:__imp_GetCurrentProcess
0x18000bfb0  mov     rcx, rax; ProcessHandle
0x18000bfb3  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x18000bfb8  lea     edx, [rsi+28h]; DesiredAccess
0x18000bfbb  call    cs:__imp_OpenProcessToken
0x18000bfc1  lea     r8, [rsp+58h+Luid.HighPart]; lpLuid
0x18000bfc6  mov     [rsp+58h+Luid.LowPart], 1
0x18000bfce  mov     rdx, rbx; lpName
0x18000bfd1  xor     ecx, ecx; lpSystemName
0x18000bfd3  call    cs:__imp_LookupPrivilegeValueW
0x18000bfd9  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x18000bfde  lea     r8, [rsp+58h+Luid]; NewState
0x18000bfe3  neg     edi
0x18000bfe5  mov     [rsp+58h+ReturnLength], rsi; ReturnLength
0x18000bfea  mov     [rsp+58h+PreviousState], rsi; PreviousState
0x18000bfef  sbb     eax, eax
0x18000bff1  xor     r9d, r9d; BufferLength
0x18000bff4  and     eax, 2
0x18000bff7  xor     edx, edx; DisableAllPrivileges
0x18000bff9  mov     [rsp+58h+Luid.HighPart+8], eax
0x18000bffd  call    cs:__imp_AdjustTokenPrivileges
0x18000c003  test    eax, eax
0x18000c005  jnz     short loc_18000C00F
0x18000c007  call    cs:__imp_GetLastError
0x18000c00d  mov     esi, eax
0x18000c00f  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x18000c014  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000c018  jz      short loc_18000C020
0x18000c01a  call    cs:__imp_CloseHandle
0x18000c020  mov     eax, esi
0x18000c022  mov     rcx, [rsp+58h+var_10]
0x18000c027  xor     rcx, rsp; StackCookie
0x18000c02a  call    __security_check_cookie
0x18000c02f  mov     rbx, [rsp+58h+arg_8]
0x18000c034  mov     rsi, [rsp+58h+arg_10]
0x18000c039  add     rsp, 50h
0x18000c03d  pop     rdi
0x18000c03e  retn
```
