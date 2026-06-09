# NvRam::SetProcessPrivilege(void)

- ea: `0x18000b2c0`
- end: `0x18000b37c`
- name: `?SetProcessPrivilege@NvRam@@AEAAJXZ`
- size: `188`
- prototype: `signed int __fastcall(NvRam *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000909c`

## callees

- `0x180001a70`
- `0x18000b2c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b301`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b301`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000b2e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000b2e4`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000b2f7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000b2f7`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18000b35e`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18000b35e`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18000b323`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18000b323`

## string_xrefs

- `0x18000b31c`: `SeSystemEnvironmentPrivilege`

## pseudocode

```c
signed int __fastcall NvRam::SetProcessPrivilege(NvRam *this)
{
  HANDLE CurrentProcess; // rax
  signed int result; // eax
  void *TokenHandle; // [rsp+30h] [rbp-28h] BYREF
  _LUID Luid[2]; // [rsp+38h] [rbp-20h] BYREF

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
0x18000b2c0  sub     rsp, 58h
0x18000b2c4  mov     rax, cs:__security_cookie
0x18000b2cb  xor     rax, rsp
0x18000b2ce  mov     [rsp+58h+var_10], rax
0x18000b2d3  xorps   xmm0, xmm0
0x18000b2d6  mov     [rsp+58h+TokenHandle], 0
0x18000b2df  movups  xmmword ptr [rsp+58h+Luid.LowPart], xmm0
0x18000b2e4  call    cs:__imp_GetCurrentProcess
0x18000b2ea  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x18000b2ef  mov     edx, 28h ; '('; DesiredAccess
0x18000b2f4  mov     rcx, rax; ProcessHandle
0x18000b2f7  call    cs:__imp_OpenProcessToken
0x18000b2fd  test    eax, eax
0x18000b2ff  jnz     short loc_18000B315
0x18000b301  call    cs:__imp_GetLastError
0x18000b307  test    eax, eax
0x18000b309  jle     short loc_18000B36A
0x18000b30b  movzx   eax, ax
0x18000b30e  or      eax, 80070000h
0x18000b313  jmp     short loc_18000B36A
0x18000b315  lea     r8, [rsp+58h+Luid.HighPart]; lpLuid
0x18000b31a  xor     ecx, ecx; lpSystemName
0x18000b31c  lea     rdx, aSesystemenviro; "SeSystemEnvironmentPrivilege"
0x18000b323  call    cs:__imp_LookupPrivilegeValueW
0x18000b329  test    eax, eax
0x18000b32b  jz      short loc_18000B301
0x18000b32d  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x18000b332  lea     r8, [rsp+58h+Luid]; NewState
0x18000b337  mov     [rsp+58h+ReturnLength], 0; ReturnLength
0x18000b340  xor     r9d, r9d; BufferLength
0x18000b343  xor     edx, edx; DisableAllPrivileges
0x18000b345  mov     [rsp+58h+PreviousState], 0; PreviousState
0x18000b34e  mov     [rsp+58h+Luid.LowPart], 1
0x18000b356  mov     [rsp+58h+Luid.HighPart+8], 2
0x18000b35e  call    cs:__imp_AdjustTokenPrivileges
0x18000b364  test    eax, eax
0x18000b366  jz      short loc_18000B301
0x18000b368  xor     eax, eax
0x18000b36a  mov     rcx, [rsp+58h+var_10]
0x18000b36f  xor     rcx, rsp; StackCookie
0x18000b372  call    __security_check_cookie
0x18000b377  add     rsp, 58h
0x18000b37b  retn
```
