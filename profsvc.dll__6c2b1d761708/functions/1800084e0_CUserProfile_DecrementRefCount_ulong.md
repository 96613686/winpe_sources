# CUserProfile::DecrementRefCount(ulong *)

- ea: `0x1800084e0`
- end: `0x1800087e0`
- name: `?DecrementRefCount@CUserProfile@@IEAAJPEAK@Z`
- size: `768`
- prototype: `__int64 __fastcall(CUserProfile *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180008fa0`

## callees

- `0x1800084e0`
- `0x180031060`
- `0x180035860`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008504`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008504`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008632`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800086d3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008797`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008632`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800086d3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008797`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800085d6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800085d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008609`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000861e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800086aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800086bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000876e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008783`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008609`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000861e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800086aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800086bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000876e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008783`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008688`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008688`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000854b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180008594`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000854b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180008594`

## string_xrefs

- `0x1800085ea`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x1800086ea`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180008716`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180008754`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x1800087b8`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180008742`: `Attempting to Decrement Profile RefCount beyond 0`
- `0x18000851e`: `Software\Microsoft\Windows NT\CurrentVersion\ProfileService\References`

## pseudocode

```c
__int64 __fastcall CUserProfile::DecrementRefCount(RTL_SRWLOCK *this, unsigned int *a2)
{
  RTL_SRWLOCK *v2; // rbx
  unsigned int v5; // eax
  const WCHAR *Ptr; // rdx
  unsigned int v7; // eax
  unsigned int v8; // eax
  int v9; // eax
  HKEY v10; // rcx
  unsigned int v11; // edi
  HKEY v12; // rcx
  unsigned int v14; // eax
  HKEY v15; // rcx
  int v16; // eax
  int v17; // eax
  int v18; // eax
  unsigned int dwOptions; // [rsp+20h] [rbp-30h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-30h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-30h]
  unsigned int dwOptionsc; // [rsp+20h] [rbp-30h]
  const char *samDesired; // [rsp+28h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  unsigned int Data; // [rsp+80h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+88h] [rbp+38h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+48h] BYREF

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
  if ( v5 )
  {
    v16 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x975,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
            (const char *)v5,
            dwOptions);
    v12 = hKey;
    v11 = v16;
    if ( !hKey )
      goto LABEL_8;
    goto LABEL_7;
  }
  Ptr = (const WCHAR *)this[6].Ptr;
  phkResult = 0;
  v7 = RegCreateKeyExW(hKey, Ptr, 0, 0, 1u, 0x2001Fu, 0, &phkResult, 0);
  if ( v7 )
  {
    v17 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x978,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
            (const char *)v7,
            dwOptionsa);
    v10 = phkResult;
    v11 = v17;
    if ( phkResult )
      goto LABEL_5;
    goto LABEL_6;
  }
  Data = 0;
  cbData = 4;
  v8 = RegQueryValueExW(phkResult, L"RefCount", 0, 0, (LPBYTE)&Data, &cbData);
  if ( v8 )
  {
    v9 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x97C,
           (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
           (const char *)v8,
           dwOptionsb);
    v10 = phkResult;
    v11 = v9;
    if ( !phkResult )
      goto LABEL_6;
    goto LABEL_5;
  }
  if ( Data )
  {
    --Data;
    cbData = 4;
    v14 = RegSetValueExW(phkResult, L"RefCount", 0, 3u, (const BYTE *)&Data, 4u);
    if ( !v14 )
    {
      v15 = phkResult;
      *a2 = Data;
      if ( v15 )
        RegCloseKey(v15);
      if ( hKey )
        RegCloseKey(hKey);
      if ( v2 )
        ReleaseSRWLockExclusive(v2);
      return 0;
    }
    v18 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x981,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
            (const char *)v14,
            dwOptionsc);
    v10 = phkResult;
    v11 = v18;
    if ( phkResult )
LABEL_5:
      RegCloseKey(v10);
LABEL_6:
    v12 = hKey;
    if ( !hKey )
    {
LABEL_8:
      if ( v2 )
        ReleaseSRWLockExclusive(v2);
      return v11;
    }
LABEL_7:
    RegCloseKey(v12);
    goto LABEL_8;
  }
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0x97D,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
    (const char *)0x8000000BLL,
    (int)"Attempting to Decrement Profile RefCount beyond 0",
    samDesired);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  if ( v2 )
    ReleaseSRWLockExclusive(v2);
  return 2147483659LL;
}

```

## disassembly

```asm
0x1800084e0  push    rbp
0x1800084e2  push    rbx
0x1800084e3  push    rsi
0x1800084e4  push    rdi
0x1800084e5  push    r14
0x1800084e7  mov     rbp, rsp
0x1800084ea  sub     rsp, 50h
0x1800084ee  lea     rbx, [rcx+128h]
0x1800084f5  mov     rdi, rcx
0x1800084f8  xor     r14d, r14d
0x1800084fb  mov     rcx, rbx; SRWLock
0x1800084fe  mov     rsi, rdx
0x180008501  mov     [rdx], r14d
0x180008504  call    cs:__imp_AcquireSRWLockExclusive
0x18000850b  nop     dword ptr [rax+rax+00h]
0x180008510  mov     [rsp+50h+lpdwDisposition], r14; lpdwDisposition
0x180008515  lea     rax, [rbp+hKey]
0x180008519  mov     [rsp+50h+phkResult], rax; phkResult
0x18000851e  lea     rdx, aSoftwareMicros_32; "Software\\Microsoft\\Windows NT\\Curren"...
0x180008525  mov     [rsp+50h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18000852a  xor     r9d, r9d; lpClass
0x18000852d  mov     [rsp+50h+samDesired], 2001Fh; samDesired
0x180008535  xor     r8d, r8d; Reserved
0x180008538  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000853f  mov     [rsp+50h+dwOptions], 1; unsigned int
0x180008547  mov     [rbp+hKey], r14
0x18000854b  call    cs:__imp_RegCreateKeyExW
0x180008552  nop     dword ptr [rax+rax+00h]
0x180008557  test    eax, eax
0x180008559  jnz     loc_1800086E6
0x18000855f  mov     rdx, [rdi+30h]; lpSubKey
0x180008563  lea     rax, [rbp+arg_10]
0x180008567  mov     rcx, [rbp+hKey]; hKey
0x18000856b  xor     r9d, r9d; lpClass
0x18000856e  mov     [rsp+50h+lpdwDisposition], r14; lpdwDisposition
0x180008573  xor     r8d, r8d; Reserved
0x180008576  mov     [rsp+50h+phkResult], rax; phkResult
0x18000857b  mov     [rsp+50h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180008580  mov     [rsp+50h+samDesired], 2001Fh; samDesired
0x180008588  mov     [rsp+50h+dwOptions], 1; unsigned int
0x180008590  mov     [rbp+arg_10], r14
0x180008594  call    cs:__imp_RegCreateKeyExW
0x18000859b  nop     dword ptr [rax+rax+00h]
0x1800085a0  test    eax, eax
0x1800085a2  jnz     loc_180008712
0x1800085a8  mov     rcx, [rbp+arg_10]; hKey
0x1800085ac  lea     rax, [rbp+cbData]
0x1800085b0  mov     qword ptr [rsp+50h+samDesired], rax; char *
0x1800085b5  lea     rdx, aRefcount; "RefCount"
0x1800085bc  lea     rax, [rbp+Data]
0x1800085c0  mov     [rbp+Data], r14d
0x1800085c4  xor     r9d, r9d; lpType
0x1800085c7  mov     qword ptr [rsp+50h+dwOptions], rax; unsigned int
0x1800085cc  xor     r8d, r8d; lpReserved
0x1800085cf  mov     [rbp+cbData], 4
0x1800085d6  call    cs:__imp_RegQueryValueExW
0x1800085dd  nop     dword ptr [rax+rax+00h]
0x1800085e2  test    eax, eax
0x1800085e4  jz      short loc_18000864C
0x1800085e6  mov     rcx, [rbp+28h]; this
0x1800085ea  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800085f1  mov     r9d, eax; char *
0x1800085f4  mov     edx, 97Ch; void *
0x1800085f9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800085fe  mov     rcx, [rbp+arg_10]; hKey
0x180008602  mov     edi, eax
0x180008604  test    rcx, rcx
0x180008607  jz      short loc_180008615
0x180008609  call    cs:__imp_RegCloseKey
0x180008610  nop     dword ptr [rax+rax+00h]
0x180008615  mov     rcx, [rbp+hKey]; hKey
0x180008619  test    rcx, rcx
0x18000861c  jz      short loc_18000862A
0x18000861e  call    cs:__imp_RegCloseKey
0x180008625  nop     dword ptr [rax+rax+00h]
0x18000862a  test    rbx, rbx
0x18000862d  jz      short loc_18000863E
0x18000862f  mov     rcx, rbx; SRWLock
0x180008632  call    cs:__imp_ReleaseSRWLockExclusive
0x180008639  nop     dword ptr [rax+rax+00h]
0x18000863e  mov     eax, edi
0x180008640  add     rsp, 50h
0x180008644  pop     r14
0x180008646  pop     rdi
0x180008647  pop     rsi
0x180008648  pop     rbx
0x180008649  pop     rbp
0x18000864a  retn
0x18000864c  mov     eax, [rbp+Data]
0x18000864f  test    eax, eax
0x180008651  jz      loc_18000873E
0x180008657  mov     rcx, [rbp+arg_10]; hKey
0x18000865b  lea     rdx, aRefcount; "RefCount"
0x180008662  dec     eax
0x180008664  mov     [rsp+50h+samDesired], 4; cbData
0x18000866c  mov     [rbp+Data], eax
0x18000866f  mov     r9d, 3; dwType
0x180008675  lea     rax, [rbp+Data]
0x180008679  mov     [rbp+cbData], 4
0x180008680  xor     r8d, r8d; Reserved
0x180008683  mov     qword ptr [rsp+50h+dwOptions], rax; unsigned int
0x180008688  call    cs:__imp_RegSetValueExW
0x18000868f  nop     dword ptr [rax+rax+00h]
0x180008694  test    eax, eax
0x180008696  jnz     loc_1800087B4
0x18000869c  mov     rcx, [rbp+arg_10]; hKey
0x1800086a0  mov     eax, [rbp+Data]
0x1800086a3  mov     [rsi], eax
0x1800086a5  test    rcx, rcx
0x1800086a8  jz      short loc_1800086B6
0x1800086aa  call    cs:__imp_RegCloseKey
0x1800086b1  nop     dword ptr [rax+rax+00h]
0x1800086b6  mov     rcx, [rbp+hKey]; hKey
0x1800086ba  test    rcx, rcx
0x1800086bd  jz      short loc_1800086CB
0x1800086bf  call    cs:__imp_RegCloseKey
0x1800086c6  nop     dword ptr [rax+rax+00h]
0x1800086cb  test    rbx, rbx
0x1800086ce  jz      short loc_1800086DF
0x1800086d0  mov     rcx, rbx; SRWLock
0x1800086d3  call    cs:__imp_ReleaseSRWLockExclusive
0x1800086da  nop     dword ptr [rax+rax+00h]
0x1800086df  xor     eax, eax
0x1800086e1  jmp     loc_180008640
0x1800086e6  mov     rcx, [rbp+28h]; this
0x1800086ea  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800086f1  mov     r9d, eax; char *
0x1800086f4  mov     edx, 975h; void *
0x1800086f9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800086fe  mov     rcx, [rbp+hKey]
0x180008702  mov     edi, eax
0x180008704  test    rcx, rcx
0x180008707  jz      loc_18000862A
0x18000870d  jmp     loc_18000861E
0x180008712  mov     rcx, [rbp+28h]; this
0x180008716  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000871d  mov     r9d, eax; char *
0x180008720  mov     edx, 978h; void *
0x180008725  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000872a  mov     rcx, [rbp+arg_10]
0x18000872e  mov     edi, eax
0x180008730  test    rcx, rcx
0x180008733  jz      loc_180008615
0x180008739  jmp     loc_180008609
0x18000873e  mov     rcx, [rbp+28h]; this
0x180008742  lea     rax, aAttemptingToDe; "Attempting to Decrement Profile RefCoun"...
0x180008749  mov     r9d, 8000000Bh; char *
0x18000874f  mov     qword ptr [rsp+50h+dwOptions], rax; int
0x180008754  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000875b  mov     edx, 97Dh; void *
0x180008760  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180008765  mov     rcx, [rbp+arg_10]; hKey
0x180008769  test    rcx, rcx
0x18000876c  jz      short loc_18000877A
0x18000876e  call    cs:__imp_RegCloseKey
0x180008775  nop     dword ptr [rax+rax+00h]
0x18000877a  mov     rcx, [rbp+hKey]; hKey
0x18000877e  test    rcx, rcx
0x180008781  jz      short loc_18000878F
0x180008783  call    cs:__imp_RegCloseKey
0x18000878a  nop     dword ptr [rax+rax+00h]
0x18000878f  test    rbx, rbx
0x180008792  jz      short loc_1800087A3
0x180008794  mov     rcx, rbx; SRWLock
0x180008797  call    cs:__imp_ReleaseSRWLockExclusive
0x18000879e  nop     dword ptr [rax+rax+00h]
0x1800087a3  mov     eax, 8000000Bh
0x1800087a8  add     rsp, 50h
0x1800087ac  pop     r14
0x1800087ae  pop     rdi
0x1800087af  pop     rsi
0x1800087b0  pop     rbx
0x1800087b1  pop     rbp
0x1800087b2  retn
0x1800087b4  mov     rcx, [rbp+28h]; this
0x1800087b8  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800087bf  mov     r9d, eax; char *
0x1800087c2  mov     edx, 981h; void *
0x1800087c7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800087cc  mov     rcx, [rbp+arg_10]
0x1800087d0  mov     edi, eax
0x1800087d2  test    rcx, rcx
0x1800087d5  jz      loc_180008615
0x1800087db  jmp     loc_180008609
```
