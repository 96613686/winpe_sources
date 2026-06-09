# CUserProfile::DecrementRefCount(ulong *)

- ea: `0x18000ab10`
- end: `0x18000adba`
- name: `?DecrementRefCount@CUserProfile@@IEAAJPEAK@Z`
- size: `682`
- prototype: `__int64 __fastcall(CUserProfile *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000b540`

## callees

- `0x18000ab10`
- `0x18002e648`
- `0x18002f8e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ab34`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ab34`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ac3e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000acc6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ad78`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ac3e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000acc6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ad78`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000abf4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000abf4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ac21`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ac30`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000aca9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000acb8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ad5b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ad6a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ac21`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ac30`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000aca9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000acb8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ad5b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ad6a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000ac8d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000ac8d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000ab75`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000abb8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000ab75`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000abb8`

## string_xrefs

- `0x18000ac02`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18000acd7`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18000ad03`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18000ad41`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18000ad92`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18000ad2f`: `Attempting to Decrement Profile RefCount beyond 0`
- `0x18000ab48`: `Software\Microsoft\Windows NT\CurrentVersion\ProfileService\References`

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
0x18000ab10  push    rbp
0x18000ab12  push    rbx
0x18000ab13  push    rsi
0x18000ab14  push    rdi
0x18000ab15  push    r14
0x18000ab17  mov     rbp, rsp
0x18000ab1a  sub     rsp, 50h
0x18000ab1e  lea     rbx, [rcx+128h]
0x18000ab25  mov     rdi, rcx
0x18000ab28  xor     r14d, r14d
0x18000ab2b  mov     rcx, rbx; SRWLock
0x18000ab2e  mov     rsi, rdx
0x18000ab31  mov     [rdx], r14d
0x18000ab34  call    cs:__imp_AcquireSRWLockExclusive
0x18000ab3a  mov     [rsp+50h+lpdwDisposition], r14; lpdwDisposition
0x18000ab3f  lea     rax, [rbp+hKey]
0x18000ab43  mov     [rsp+50h+phkResult], rax; phkResult
0x18000ab48  lea     rdx, aSoftwareMicros_32; "Software\\Microsoft\\Windows NT\\Curren"...
0x18000ab4f  mov     [rsp+50h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18000ab54  xor     r9d, r9d; lpClass
0x18000ab57  mov     [rsp+50h+samDesired], 2001Fh; samDesired
0x18000ab5f  xor     r8d, r8d; Reserved
0x18000ab62  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000ab69  mov     [rsp+50h+dwOptions], 1; unsigned int
0x18000ab71  mov     [rbp+hKey], r14
0x18000ab75  call    cs:__imp_RegCreateKeyExW
0x18000ab7b  test    eax, eax
0x18000ab7d  jnz     loc_18000ACD3
0x18000ab83  mov     rdx, [rdi+30h]; lpSubKey
0x18000ab87  lea     rax, [rbp+arg_10]
0x18000ab8b  mov     rcx, [rbp+hKey]; hKey
0x18000ab8f  xor     r9d, r9d; lpClass
0x18000ab92  mov     [rsp+50h+lpdwDisposition], r14; lpdwDisposition
0x18000ab97  xor     r8d, r8d; Reserved
0x18000ab9a  mov     [rsp+50h+phkResult], rax; phkResult
0x18000ab9f  mov     [rsp+50h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18000aba4  mov     [rsp+50h+samDesired], 2001Fh; samDesired
0x18000abac  mov     [rsp+50h+dwOptions], 1; unsigned int
0x18000abb4  mov     [rbp+arg_10], r14
0x18000abb8  call    cs:__imp_RegCreateKeyExW
0x18000abbe  test    eax, eax
0x18000abc0  jnz     loc_18000ACFF
0x18000abc6  mov     rcx, [rbp+arg_10]; hKey
0x18000abca  lea     rax, [rbp+cbData]
0x18000abce  mov     qword ptr [rsp+50h+samDesired], rax; char *
0x18000abd3  lea     rdx, ValueName; "RefCount"
0x18000abda  lea     rax, [rbp+Data]
0x18000abde  mov     [rbp+Data], r14d
0x18000abe2  xor     r9d, r9d; lpType
0x18000abe5  mov     qword ptr [rsp+50h+dwOptions], rax; unsigned int
0x18000abea  xor     r8d, r8d; lpReserved
0x18000abed  mov     [rbp+cbData], 4
0x18000abf4  call    cs:__imp_RegQueryValueExW
0x18000abfa  test    eax, eax
0x18000abfc  jz      short loc_18000AC51
0x18000abfe  mov     rcx, [rbp+28h]; this
0x18000ac02  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000ac09  mov     r9d, eax; char *
0x18000ac0c  mov     edx, 97Ch; void *
0x18000ac11  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000ac16  mov     rcx, [rbp+arg_10]; hKey
0x18000ac1a  mov     edi, eax
0x18000ac1c  test    rcx, rcx
0x18000ac1f  jz      short loc_18000AC27
0x18000ac21  call    cs:__imp_RegCloseKey
0x18000ac27  mov     rcx, [rbp+hKey]; hKey
0x18000ac2b  test    rcx, rcx
0x18000ac2e  jz      short loc_18000AC36
0x18000ac30  call    cs:__imp_RegCloseKey
0x18000ac36  test    rbx, rbx
0x18000ac39  jz      short loc_18000AC44
0x18000ac3b  mov     rcx, rbx; SRWLock
0x18000ac3e  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ac44  mov     eax, edi
0x18000ac46  add     rsp, 50h
0x18000ac4a  pop     r14
0x18000ac4c  pop     rdi
0x18000ac4d  pop     rsi
0x18000ac4e  pop     rbx
0x18000ac4f  pop     rbp
0x18000ac50  retn
0x18000ac51  mov     eax, [rbp+Data]
0x18000ac54  test    eax, eax
0x18000ac56  jz      loc_18000AD2B
0x18000ac5c  mov     rcx, [rbp+arg_10]; hKey
0x18000ac60  lea     rdx, ValueName; "RefCount"
0x18000ac67  dec     eax
0x18000ac69  mov     [rsp+50h+samDesired], 4; cbData
0x18000ac71  mov     [rbp+Data], eax
0x18000ac74  mov     r9d, 3; dwType
0x18000ac7a  lea     rax, [rbp+Data]
0x18000ac7e  mov     [rbp+cbData], 4
0x18000ac85  xor     r8d, r8d; Reserved
0x18000ac88  mov     qword ptr [rsp+50h+dwOptions], rax; unsigned int
0x18000ac8d  call    cs:__imp_RegSetValueExW
0x18000ac93  test    eax, eax
0x18000ac95  jnz     loc_18000AD8E
0x18000ac9b  mov     rcx, [rbp+arg_10]; hKey
0x18000ac9f  mov     eax, [rbp+Data]
0x18000aca2  mov     [rsi], eax
0x18000aca4  test    rcx, rcx
0x18000aca7  jz      short loc_18000ACAF
0x18000aca9  call    cs:__imp_RegCloseKey
0x18000acaf  mov     rcx, [rbp+hKey]; hKey
0x18000acb3  test    rcx, rcx
0x18000acb6  jz      short loc_18000ACBE
0x18000acb8  call    cs:__imp_RegCloseKey
0x18000acbe  test    rbx, rbx
0x18000acc1  jz      short loc_18000ACCC
0x18000acc3  mov     rcx, rbx; SRWLock
0x18000acc6  call    cs:__imp_ReleaseSRWLockExclusive
0x18000accc  xor     eax, eax
0x18000acce  jmp     loc_18000AC46
0x18000acd3  mov     rcx, [rbp+28h]; this
0x18000acd7  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000acde  mov     r9d, eax; char *
0x18000ace1  mov     edx, 975h; void *
0x18000ace6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000aceb  mov     rcx, [rbp+hKey]
0x18000acef  mov     edi, eax
0x18000acf1  test    rcx, rcx
0x18000acf4  jz      loc_18000AC36
0x18000acfa  jmp     loc_18000AC30
0x18000acff  mov     rcx, [rbp+28h]; this
0x18000ad03  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000ad0a  mov     r9d, eax; char *
0x18000ad0d  mov     edx, 978h; void *
0x18000ad12  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000ad17  mov     rcx, [rbp+arg_10]
0x18000ad1b  mov     edi, eax
0x18000ad1d  test    rcx, rcx
0x18000ad20  jz      loc_18000AC27
0x18000ad26  jmp     loc_18000AC21
0x18000ad2b  mov     rcx, [rbp+28h]; this
0x18000ad2f  lea     rax, aAttemptingToDe; "Attempting to Decrement Profile RefCoun"...
0x18000ad36  mov     r9d, 8000000Bh; char *
0x18000ad3c  mov     qword ptr [rsp+50h+dwOptions], rax; int
0x18000ad41  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000ad48  mov     edx, 97Dh; void *
0x18000ad4d  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000ad52  mov     rcx, [rbp+arg_10]; hKey
0x18000ad56  test    rcx, rcx
0x18000ad59  jz      short loc_18000AD61
0x18000ad5b  call    cs:__imp_RegCloseKey
0x18000ad61  mov     rcx, [rbp+hKey]; hKey
0x18000ad65  test    rcx, rcx
0x18000ad68  jz      short loc_18000AD70
0x18000ad6a  call    cs:__imp_RegCloseKey
0x18000ad70  test    rbx, rbx
0x18000ad73  jz      short loc_18000AD7E
0x18000ad75  mov     rcx, rbx; SRWLock
0x18000ad78  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ad7e  mov     eax, 8000000Bh
0x18000ad83  add     rsp, 50h
0x18000ad87  pop     r14
0x18000ad89  pop     rdi
0x18000ad8a  pop     rsi
0x18000ad8b  pop     rbx
0x18000ad8c  pop     rbp
0x18000ad8d  retn
0x18000ad8e  mov     rcx, [rbp+28h]; this
0x18000ad92  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000ad99  mov     r9d, eax; char *
0x18000ad9c  mov     edx, 981h; void *
0x18000ada1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000ada6  mov     rcx, [rbp+arg_10]
0x18000adaa  mov     edi, eax
0x18000adac  test    rcx, rcx
0x18000adaf  jz      loc_18000AC27
0x18000adb5  jmp     loc_18000AC21
```
