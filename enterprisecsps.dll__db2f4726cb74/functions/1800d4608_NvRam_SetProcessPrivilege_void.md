# NvRam::SetProcessPrivilege(void)

- ea: `0x1800d4608`
- end: `0x1800d46e3`
- name: `?SetProcessPrivilege@NvRam@@AEAAJXZ`
- size: `219`
- prototype: `__int64 __fastcall(NvRam *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800d3c5c`

## callees

- `0x180008de0`
- `0x1800d4608`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d4655`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d4655`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800d4645`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800d4645`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800d462c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800d462c`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800d46be`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800d46be`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x1800d467d`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x1800d467d`

## string_xrefs

- `0x1800d4676`: `SeSystemEnvironmentPrivilege`

## pseudocode

```c
signed int __fastcall NvRam::SetProcessPrivilege(NvRam *this)
{
  HANDLE CurrentProcess; // rax
  signed int result; // eax
  void *TokenHandle; // [rsp+30h] [rbp-28h] BYREF
  struct _LUID Luid[2]; // [rsp+38h] [rbp-20h] BYREF

  TokenHandle = 0;
  *(_OWORD *)&Luid[0].LowPart = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
  {
    if ( LookupPrivilegeValueW(0, L"SeSystemEnvironmentPrivilege", (PLUID)&Luid[0].HighPart) )
    {
      Luid[0].LowPart = 1;
      Luid[1].HighPart = 2;
      if ( AdjustTokenPrivileges(TokenHandle, 0, (PTOKEN_PRIVILEGES)Luid, 0, 0, 0) )
        return 0;
    }
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800d4608  sub     rsp, 58h
0x1800d460c  mov     rax, cs:__security_cookie
0x1800d4613  xor     rax, rsp
0x1800d4616  mov     [rsp+58h+var_10], rax
0x1800d461b  xorps   xmm0, xmm0
0x1800d461e  mov     [rsp+58h+TokenHandle], 0
0x1800d4627  movups  xmmword ptr [rsp+58h+Luid.LowPart], xmm0
0x1800d462c  call    cs:__imp_GetCurrentProcess
0x1800d4633  nop     dword ptr [rax+rax+00h]
0x1800d4638  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x1800d463d  mov     edx, 28h ; '('; DesiredAccess
0x1800d4642  mov     rcx, rax; ProcessHandle
0x1800d4645  call    cs:__imp_OpenProcessToken
0x1800d464c  nop     dword ptr [rax+rax+00h]
0x1800d4651  test    eax, eax
0x1800d4653  jnz     short loc_1800D466F
0x1800d4655  call    cs:__imp_GetLastError
0x1800d465c  nop     dword ptr [rax+rax+00h]
0x1800d4661  test    eax, eax
0x1800d4663  jle     short loc_1800D46D0
0x1800d4665  movzx   eax, ax
0x1800d4668  or      eax, 80070000h
0x1800d466d  jmp     short loc_1800D46D0
0x1800d466f  lea     r8, [rsp+58h+Luid.HighPart]; lpLuid
0x1800d4674  xor     ecx, ecx; lpSystemName
0x1800d4676  lea     rdx, aSesystemenviro; "SeSystemEnvironmentPrivilege"
0x1800d467d  call    cs:__imp_LookupPrivilegeValueW
0x1800d4684  nop     dword ptr [rax+rax+00h]
0x1800d4689  test    eax, eax
0x1800d468b  jz      short loc_1800D4655
0x1800d468d  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x1800d4692  lea     r8, [rsp+58h+Luid]; NewState
0x1800d4697  mov     [rsp+58h+ReturnLength], 0; ReturnLength
0x1800d46a0  xor     r9d, r9d; BufferLength
0x1800d46a3  xor     edx, edx; DisableAllPrivileges
0x1800d46a5  mov     [rsp+58h+PreviousState], 0; PreviousState
0x1800d46ae  mov     [rsp+58h+Luid.LowPart], 1
0x1800d46b6  mov     [rsp+58h+Luid.HighPart+8], 2
0x1800d46be  call    cs:__imp_AdjustTokenPrivileges
0x1800d46c5  nop     dword ptr [rax+rax+00h]
0x1800d46ca  test    eax, eax
0x1800d46cc  jz      short loc_1800D4655
0x1800d46ce  xor     eax, eax
0x1800d46d0  mov     rcx, [rsp+58h+var_10]
0x1800d46d5  xor     rcx, rsp; StackCookie
0x1800d46d8  call    __security_check_cookie
0x1800d46dd  add     rsp, 58h
0x1800d46e1  retn
```
