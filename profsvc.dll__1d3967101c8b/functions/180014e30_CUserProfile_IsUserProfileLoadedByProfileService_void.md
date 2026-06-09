# CUserProfile::IsUserProfileLoadedByProfileService(void)

- ea: `0x180014e30`
- end: `0x180014fbe`
- name: `?IsUserProfileLoadedByProfileService@CUserProfile@@IEAA_NXZ`
- size: `398`
- prototype: `bool __fastcall(CUserProfile *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800140c0`

## callees

- `0x180014e30`
- `0x180041e18`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014e49`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014e49`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014f75`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014f75`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014f32`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014f32`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014f54`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014f67`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014f54`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014f67`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180014e94`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180014ee3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180014e94`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180014ee3`

## string_xrefs

- `0x180014f8d`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180014fa8`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180014e5e`: `Software\Microsoft\Windows NT\CurrentVersion\ProfileService\References`

## pseudocode

```c
_BOOL8 __fastcall CUserProfile::IsUserProfileLoadedByProfileService(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v1; // rbx
  bool v3; // si
  unsigned int v4; // eax
  const WCHAR *Ptr; // rdx
  unsigned int v6; // eax
  unsigned int dwOptions; // [rsp+20h] [rbp-58h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  int Data; // [rsp+80h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+88h] [rbp+10h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+20h] BYREF

  v1 = this + 37;
  v3 = 0;
  AcquireSRWLockExclusive(this + 37);
  hKey = 0;
  v4 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\ProfileService\\References",
         0,
         0,
         1u,
         0x2001Fu,
         0,
         &hKey,
         0);
  if ( v4 )
  {
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x990,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
      (const char *)v4,
      dwOptions);
  }
  else
  {
    Ptr = (const WCHAR *)this[6].Ptr;
    phkResult = 0;
    v6 = RegCreateKeyExW(hKey, Ptr, 0, 0, 1u, 0x2001Fu, 0, &phkResult, 0);
    if ( v6 )
    {
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x993,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)v6,
        dwOptionsa);
    }
    else
    {
      Data = 0;
      cbData = 4;
      if ( !RegQueryValueExW(phkResult, L"RefCount", 0, 0, (LPBYTE)&Data, &cbData) )
        v3 = Data != 0;
    }
    if ( phkResult )
      RegCloseKey(phkResult);
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v1 )
    ReleaseSRWLockExclusive(v1);
  return v3;
}

```

## disassembly

```asm
0x180014e30  push    rbx
0x180014e32  push    rbp
0x180014e33  push    rsi
0x180014e34  push    rdi
0x180014e35  sub     rsp, 58h
0x180014e39  lea     rbx, [rcx+128h]
0x180014e40  mov     rdi, rcx
0x180014e43  mov     rcx, rbx; SRWLock
0x180014e46  xor     sil, sil
0x180014e49  call    cs:__imp_AcquireSRWLockExclusive
0x180014e4f  xor     ebp, ebp
0x180014e51  lea     rax, [rsp+78h+hKey]
0x180014e59  mov     [rsp+78h+lpdwDisposition], rbp; lpdwDisposition
0x180014e5e  lea     rdx, aSoftwareMicros_32; "Software\\Microsoft\\Windows NT\\Curren"...
0x180014e65  mov     [rsp+78h+phkResult], rax; phkResult
0x180014e6a  xor     r9d, r9d; lpClass
0x180014e6d  mov     [rsp+78h+lpSecurityAttributes], rbp; lpSecurityAttributes
0x180014e72  xor     r8d, r8d; Reserved
0x180014e75  mov     [rsp+78h+samDesired], 2001Fh; samDesired
0x180014e7d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180014e84  mov     [rsp+78h+dwOptions], 1; unsigned int
0x180014e8c  mov     [rsp+78h+hKey], rbp
0x180014e94  call    cs:__imp_RegCreateKeyExW
0x180014e9a  test    eax, eax
0x180014e9c  jnz     loc_180014F88
0x180014ea2  mov     rdx, [rdi+30h]; lpSubKey
0x180014ea6  lea     rax, [rsp+78h+arg_10]
0x180014eae  mov     rcx, [rsp+78h+hKey]; hKey
0x180014eb6  xor     r9d, r9d; lpClass
0x180014eb9  mov     [rsp+78h+lpdwDisposition], rbp; lpdwDisposition
0x180014ebe  xor     r8d, r8d; Reserved
0x180014ec1  mov     [rsp+78h+phkResult], rax; phkResult
0x180014ec6  mov     [rsp+78h+lpSecurityAttributes], rbp; lpSecurityAttributes
0x180014ecb  mov     [rsp+78h+samDesired], 2001Fh; samDesired
0x180014ed3  mov     [rsp+78h+dwOptions], 1; unsigned int
0x180014edb  mov     [rsp+78h+arg_10], rbp
0x180014ee3  call    cs:__imp_RegCreateKeyExW
0x180014ee9  test    eax, eax
0x180014eeb  jnz     loc_180014FA3
0x180014ef1  mov     rcx, [rsp+78h+arg_10]; hKey
0x180014ef9  lea     rax, [rsp+78h+cbData]
0x180014f01  mov     qword ptr [rsp+78h+samDesired], rax; lpcbData
0x180014f06  lea     rdx, ValueName; "RefCount"
0x180014f0d  lea     rax, [rsp+78h+Data]
0x180014f15  mov     [rsp+78h+Data], ebp
0x180014f1c  xor     r9d, r9d; lpType
0x180014f1f  mov     qword ptr [rsp+78h+dwOptions], rax; lpData
0x180014f24  xor     r8d, r8d; lpReserved
0x180014f27  mov     [rsp+78h+cbData], 4
0x180014f32  call    cs:__imp_RegQueryValueExW
0x180014f38  test    eax, eax
0x180014f3a  jnz     short loc_180014F47
0x180014f3c  cmp     [rsp+78h+Data], ebp
0x180014f43  setnz   sil
0x180014f47  mov     rcx, [rsp+78h+arg_10]; hKey
0x180014f4f  test    rcx, rcx
0x180014f52  jz      short loc_180014F5A
0x180014f54  call    cs:__imp_RegCloseKey
0x180014f5a  mov     rcx, [rsp+78h+hKey]; hKey
0x180014f62  test    rcx, rcx
0x180014f65  jz      short loc_180014F6D
0x180014f67  call    cs:__imp_RegCloseKey
0x180014f6d  test    rbx, rbx
0x180014f70  jz      short loc_180014F7B
0x180014f72  mov     rcx, rbx; SRWLock
0x180014f75  call    cs:__imp_ReleaseSRWLockExclusive
0x180014f7b  movzx   eax, sil
0x180014f7f  add     rsp, 58h
0x180014f83  pop     rdi
0x180014f84  pop     rsi
0x180014f85  pop     rbp
0x180014f86  pop     rbx
0x180014f87  retn
0x180014f88  mov     rcx, [rsp+78h]; this
0x180014f8d  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180014f94  mov     r9d, eax; char *
0x180014f97  mov     edx, 990h; void *
0x180014f9c  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180014fa1  jmp     short loc_180014F5A
0x180014fa3  mov     rcx, [rsp+78h]; this
0x180014fa8  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180014faf  mov     r9d, eax; char *
0x180014fb2  mov     edx, 993h; void *
0x180014fb7  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180014fbc  jmp     short loc_180014F47
```
