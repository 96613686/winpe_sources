# CUserProfile::IncrementRefCount(ulong *)

- ea: `0x1800242a0`
- end: `0x18002452b`
- name: `?IncrementRefCount@CUserProfile@@IEAAJPEAK@Z`
- size: `651`
- prototype: `__int64 __fastcall(CUserProfile *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180030744`

## callees

- `0x1800242a0`
- `0x180031060`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800242bd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800242bd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024458`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002446b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024458`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002446b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800243b6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800243b6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002442b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024444`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800244ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800244e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002442b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024444`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800244ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800244e6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180024401`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180024401`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002430c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180024361`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002430c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180024361`

## string_xrefs

- `0x180024488`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x1800244c3`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180024506`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x1800242db`: `Software\Microsoft\Windows NT\CurrentVersion\ProfileService\References`

## pseudocode

```c
__int64 __fastcall CUserProfile::IncrementRefCount(RTL_SRWLOCK *this, unsigned int *a2)
{
  RTL_SRWLOCK *v2; // rbx
  unsigned int v5; // eax
  const WCHAR *Ptr; // rdx
  unsigned int v7; // eax
  unsigned int v8; // eax
  HKEY v9; // rcx
  int v11; // eax
  HKEY v12; // rcx
  unsigned int v13; // edi
  int v14; // eax
  HKEY v15; // rcx
  int v16; // eax
  unsigned int dwOptions; // [rsp+20h] [rbp-58h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-58h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  unsigned int Data; // [rsp+80h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+88h] [rbp+10h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+20h] BYREF

  v2 = this + 37;
  *a2 = 0;
  AcquireSRWLockExclusive(this + 37);
  hKey = 0;
  v5 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\ProfileService\\References",
         0,
         0,
         1u,
         0x2001Fu,
         0,
         &hKey,
         0);
  if ( !v5 )
  {
    Ptr = (const WCHAR *)this[6].Ptr;
    phkResult = 0;
    v7 = RegCreateKeyExW(hKey, Ptr, 0, 0, 1u, 0x2001Fu, 0, &phkResult, 0);
    if ( v7 )
    {
      v14 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x947,
              (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
              (const char *)v7,
              dwOptionsa);
      v15 = phkResult;
      v13 = v14;
      if ( !phkResult )
        goto LABEL_18;
    }
    else
    {
      Data = 0;
      cbData = 4;
      RegQueryValueExW(phkResult, L"RefCount", 0, 0, (LPBYTE)&Data, &cbData);
      ++Data;
      cbData = 4;
      v8 = RegSetValueExW(phkResult, L"RefCount", 0, 3u, (const BYTE *)&Data, 4u);
      if ( !v8 )
      {
        v9 = phkResult;
        *a2 = Data;
        if ( v9 )
          RegCloseKey(v9);
        if ( hKey )
          RegCloseKey(hKey);
        if ( v2 )
          ReleaseSRWLockExclusive(v2);
        return 0;
      }
      v16 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x94F,
              (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
              (const char *)v8,
              dwOptionsb);
      v15 = phkResult;
      v13 = v16;
      if ( !phkResult )
      {
LABEL_18:
        v12 = hKey;
        if ( !hKey )
          goto LABEL_14;
        goto LABEL_13;
      }
    }
    RegCloseKey(v15);
    goto LABEL_18;
  }
  v11 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)0x944,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
          (const char *)v5,
          dwOptions);
  v12 = hKey;
  v13 = v11;
  if ( hKey )
LABEL_13:
    RegCloseKey(v12);
LABEL_14:
  if ( v2 )
    ReleaseSRWLockExclusive(v2);
  return v13;
}

```

## disassembly

```asm
0x1800242a0  push    rbx
0x1800242a2  push    rbp
0x1800242a3  push    rsi
0x1800242a4  push    rdi
0x1800242a5  sub     rsp, 58h
0x1800242a9  lea     rbx, [rcx+128h]
0x1800242b0  mov     rsi, rcx
0x1800242b3  xor     ebp, ebp
0x1800242b5  mov     rcx, rbx; SRWLock
0x1800242b8  mov     rdi, rdx
0x1800242bb  mov     [rdx], ebp
0x1800242bd  call    cs:__imp_AcquireSRWLockExclusive
0x1800242c4  nop     dword ptr [rax+rax+00h]
0x1800242c9  mov     [rsp+78h+lpdwDisposition], rbp; lpdwDisposition
0x1800242ce  lea     rax, [rsp+78h+hKey]
0x1800242d6  mov     [rsp+78h+phkResult], rax; phkResult
0x1800242db  lea     rdx, aSoftwareMicros_32; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800242e2  mov     [rsp+78h+lpSecurityAttributes], rbp; lpSecurityAttributes
0x1800242e7  xor     r9d, r9d; lpClass
0x1800242ea  mov     [rsp+78h+samDesired], 2001Fh; samDesired
0x1800242f2  xor     r8d, r8d; Reserved
0x1800242f5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800242fc  mov     [rsp+78h+dwOptions], 1; unsigned int
0x180024304  mov     [rsp+78h+hKey], rbp
0x18002430c  call    cs:__imp_RegCreateKeyExW
0x180024313  nop     dword ptr [rax+rax+00h]
0x180024318  test    eax, eax
0x18002431a  jnz     loc_180024483
0x180024320  mov     rdx, [rsi+30h]; lpSubKey
0x180024324  lea     rax, [rsp+78h+arg_10]
0x18002432c  mov     rcx, [rsp+78h+hKey]; hKey
0x180024334  xor     r9d, r9d; lpClass
0x180024337  mov     [rsp+78h+lpdwDisposition], rbp; lpdwDisposition
0x18002433c  xor     r8d, r8d; Reserved
0x18002433f  mov     [rsp+78h+phkResult], rax; phkResult
0x180024344  mov     [rsp+78h+lpSecurityAttributes], rbp; lpSecurityAttributes
0x180024349  mov     [rsp+78h+samDesired], 2001Fh; samDesired
0x180024351  mov     [rsp+78h+dwOptions], 1; unsigned int
0x180024359  mov     [rsp+78h+arg_10], rbp
0x180024361  call    cs:__imp_RegCreateKeyExW
0x180024368  nop     dword ptr [rax+rax+00h]
0x18002436d  test    eax, eax
0x18002436f  jnz     loc_1800244BE
0x180024375  mov     rcx, [rsp+78h+arg_10]; hKey
0x18002437d  lea     rax, [rsp+78h+cbData]
0x180024385  mov     qword ptr [rsp+78h+samDesired], rax; lpcbData
0x18002438a  lea     rdx, aRefcount; "RefCount"
0x180024391  lea     rax, [rsp+78h+Data]
0x180024399  mov     [rsp+78h+Data], ebp
0x1800243a0  xor     r9d, r9d; lpType
0x1800243a3  mov     qword ptr [rsp+78h+dwOptions], rax; lpData
0x1800243a8  xor     r8d, r8d; lpReserved
0x1800243ab  mov     [rsp+78h+cbData], 4
0x1800243b6  call    cs:__imp_RegQueryValueExW
0x1800243bd  nop     dword ptr [rax+rax+00h]
0x1800243c2  mov     rcx, [rsp+78h+arg_10]; hKey
0x1800243ca  lea     rax, [rsp+78h+Data]
0x1800243d2  inc     [rsp+78h+Data]
0x1800243d9  lea     rdx, aRefcount; "RefCount"
0x1800243e0  mov     [rsp+78h+samDesired], 4; cbData
0x1800243e8  mov     r9d, 3; dwType
0x1800243ee  xor     r8d, r8d; Reserved
0x1800243f1  mov     qword ptr [rsp+78h+dwOptions], rax; unsigned int
0x1800243f6  mov     [rsp+78h+cbData], 4
0x180024401  call    cs:__imp_RegSetValueExW
0x180024408  nop     dword ptr [rax+rax+00h]
0x18002440d  test    eax, eax
0x18002440f  jnz     loc_180024501
0x180024415  mov     rcx, [rsp+78h+arg_10]; hKey
0x18002441d  mov     eax, [rsp+78h+Data]
0x180024424  mov     [rdi], eax
0x180024426  test    rcx, rcx
0x180024429  jz      short loc_180024437
0x18002442b  call    cs:__imp_RegCloseKey
0x180024432  nop     dword ptr [rax+rax+00h]
0x180024437  mov     rcx, [rsp+78h+hKey]; hKey
0x18002443f  test    rcx, rcx
0x180024442  jz      short loc_180024450
0x180024444  call    cs:__imp_RegCloseKey
0x18002444b  nop     dword ptr [rax+rax+00h]
0x180024450  test    rbx, rbx
0x180024453  jz      short loc_180024464
0x180024455  mov     rcx, rbx; SRWLock
0x180024458  call    cs:__imp_ReleaseSRWLockExclusive
0x18002445f  nop     dword ptr [rax+rax+00h]
0x180024464  xor     eax, eax
0x180024466  jmp     short loc_180024479
0x180024468  mov     rcx, rbx; SRWLock
0x18002446b  call    cs:__imp_ReleaseSRWLockExclusive
0x180024472  nop     dword ptr [rax+rax+00h]
0x180024477  mov     eax, edi
0x180024479  add     rsp, 58h
0x18002447d  pop     rdi
0x18002447e  pop     rsi
0x18002447f  pop     rbp
0x180024480  pop     rbx
0x180024481  retn
0x180024483  mov     rcx, [rsp+78h]; this
0x180024488  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002448f  mov     r9d, eax; char *
0x180024492  mov     edx, 944h; void *
0x180024497  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002449c  mov     rcx, [rsp+78h+hKey]; hKey
0x1800244a4  mov     edi, eax
0x1800244a6  test    rcx, rcx
0x1800244a9  jz      short loc_1800244B7
0x1800244ab  call    cs:__imp_RegCloseKey
0x1800244b2  nop     dword ptr [rax+rax+00h]
0x1800244b7  test    rbx, rbx
0x1800244ba  jz      short loc_180024477
0x1800244bc  jmp     short loc_180024468
0x1800244be  mov     rcx, [rsp+78h]; this
0x1800244c3  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800244ca  mov     r9d, eax; char *
0x1800244cd  mov     edx, 947h; void *
0x1800244d2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800244d7  mov     rcx, [rsp+78h+arg_10]; hKey
0x1800244df  mov     edi, eax
0x1800244e1  test    rcx, rcx
0x1800244e4  jz      short loc_1800244F2
0x1800244e6  call    cs:__imp_RegCloseKey
0x1800244ed  nop     dword ptr [rax+rax+00h]
0x1800244f2  mov     rcx, [rsp+78h+hKey]
0x1800244fa  test    rcx, rcx
0x1800244fd  jz      short loc_1800244B7
0x1800244ff  jmp     short loc_1800244AB
0x180024501  mov     rcx, [rsp+78h]; this
0x180024506  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002450d  mov     r9d, eax; char *
0x180024510  mov     edx, 94Fh; void *
0x180024515  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002451a  mov     rcx, [rsp+78h+arg_10]
0x180024522  mov     edi, eax
0x180024524  test    rcx, rcx
0x180024527  jz      short loc_1800244F2
0x180024529  jmp     short loc_1800244E6
```
