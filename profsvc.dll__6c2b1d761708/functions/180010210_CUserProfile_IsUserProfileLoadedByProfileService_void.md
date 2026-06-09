# CUserProfile::IsUserProfileLoadedByProfileService(void)

- ea: `0x180010210`
- end: `0x1800103cc`
- name: `?IsUserProfileLoadedByProfileService@CUserProfile@@IEAA_NXZ`
- size: `444`
- prototype: `bool __fastcall(CUserProfile *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000f330`

## callees

- `0x180010210`
- `0x180043800`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010229`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010229`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010379`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010379`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180010324`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180010324`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001034c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010365`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001034c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010365`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001027a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800102cf`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001027a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800102cf`

## string_xrefs

- `0x180010398`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x1800103b3`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180010244`: `Software\Microsoft\Windows NT\CurrentVersion\ProfileService\References`

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
0x180010210  push    rbx
0x180010212  push    rbp
0x180010213  push    rsi
0x180010214  push    rdi
0x180010215  sub     rsp, 58h
0x180010219  lea     rbx, [rcx+128h]
0x180010220  mov     rdi, rcx
0x180010223  mov     rcx, rbx; SRWLock
0x180010226  xor     sil, sil
0x180010229  call    cs:__imp_AcquireSRWLockExclusive
0x180010230  nop     dword ptr [rax+rax+00h]
0x180010235  xor     ebp, ebp
0x180010237  lea     rax, [rsp+78h+hKey]
0x18001023f  mov     [rsp+78h+lpdwDisposition], rbp; lpdwDisposition
0x180010244  lea     rdx, aSoftwareMicros_32; "Software\\Microsoft\\Windows NT\\Curren"...
0x18001024b  mov     [rsp+78h+phkResult], rax; phkResult
0x180010250  xor     r9d, r9d; lpClass
0x180010253  mov     [rsp+78h+lpSecurityAttributes], rbp; lpSecurityAttributes
0x180010258  xor     r8d, r8d; Reserved
0x18001025b  mov     [rsp+78h+samDesired], 2001Fh; samDesired
0x180010263  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001026a  mov     [rsp+78h+dwOptions], 1; unsigned int
0x180010272  mov     [rsp+78h+hKey], rbp
0x18001027a  call    cs:__imp_RegCreateKeyExW
0x180010281  nop     dword ptr [rax+rax+00h]
0x180010286  test    eax, eax
0x180010288  jnz     loc_180010393
0x18001028e  mov     rdx, [rdi+30h]; lpSubKey
0x180010292  lea     rax, [rsp+78h+arg_10]
0x18001029a  mov     rcx, [rsp+78h+hKey]; hKey
0x1800102a2  xor     r9d, r9d; lpClass
0x1800102a5  mov     [rsp+78h+lpdwDisposition], rbp; lpdwDisposition
0x1800102aa  xor     r8d, r8d; Reserved
0x1800102ad  mov     [rsp+78h+phkResult], rax; phkResult
0x1800102b2  mov     [rsp+78h+lpSecurityAttributes], rbp; lpSecurityAttributes
0x1800102b7  mov     [rsp+78h+samDesired], 2001Fh; samDesired
0x1800102bf  mov     [rsp+78h+dwOptions], 1; unsigned int
0x1800102c7  mov     [rsp+78h+arg_10], rbp
0x1800102cf  call    cs:__imp_RegCreateKeyExW
0x1800102d6  nop     dword ptr [rax+rax+00h]
0x1800102db  test    eax, eax
0x1800102dd  jnz     loc_1800103AE
0x1800102e3  mov     rcx, [rsp+78h+arg_10]; hKey
0x1800102eb  lea     rax, [rsp+78h+cbData]
0x1800102f3  mov     qword ptr [rsp+78h+samDesired], rax; lpcbData
0x1800102f8  lea     rdx, aRefcount; "RefCount"
0x1800102ff  lea     rax, [rsp+78h+Data]
0x180010307  mov     [rsp+78h+Data], ebp
0x18001030e  xor     r9d, r9d; lpType
0x180010311  mov     qword ptr [rsp+78h+dwOptions], rax; lpData
0x180010316  xor     r8d, r8d; lpReserved
0x180010319  mov     [rsp+78h+cbData], 4
0x180010324  call    cs:__imp_RegQueryValueExW
0x18001032b  nop     dword ptr [rax+rax+00h]
0x180010330  test    eax, eax
0x180010332  jnz     short loc_18001033F
0x180010334  cmp     [rsp+78h+Data], ebp
0x18001033b  setnz   sil
0x18001033f  mov     rcx, [rsp+78h+arg_10]; hKey
0x180010347  test    rcx, rcx
0x18001034a  jz      short loc_180010358
0x18001034c  call    cs:__imp_RegCloseKey
0x180010353  nop     dword ptr [rax+rax+00h]
0x180010358  mov     rcx, [rsp+78h+hKey]; hKey
0x180010360  test    rcx, rcx
0x180010363  jz      short loc_180010371
0x180010365  call    cs:__imp_RegCloseKey
0x18001036c  nop     dword ptr [rax+rax+00h]
0x180010371  test    rbx, rbx
0x180010374  jz      short loc_180010385
0x180010376  mov     rcx, rbx; SRWLock
0x180010379  call    cs:__imp_ReleaseSRWLockExclusive
0x180010380  nop     dword ptr [rax+rax+00h]
0x180010385  movzx   eax, sil
0x180010389  add     rsp, 58h
0x18001038d  pop     rdi
0x18001038e  pop     rsi
0x18001038f  pop     rbp
0x180010390  pop     rbx
0x180010391  retn
0x180010393  mov     rcx, [rsp+78h]; this
0x180010398  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001039f  mov     r9d, eax; char *
0x1800103a2  mov     edx, 990h; void *
0x1800103a7  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1800103ac  jmp     short loc_180010358
0x1800103ae  mov     rcx, [rsp+78h]; this
0x1800103b3  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800103ba  mov     r9d, eax; char *
0x1800103bd  mov     edx, 993h; void *
0x1800103c2  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1800103c7  jmp     loc_18001033F
```
