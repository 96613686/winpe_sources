# CUserProfile::IncrementRefCount(ulong *)

- ea: `0x180021050`
- end: `0x180021298`
- name: `?IncrementRefCount@CUserProfile@@IEAAJPEAK@Z`
- size: `584`
- prototype: `__int64 __fastcall(CUserProfile *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002bf94`

## callees

- `0x180021050`
- `0x18002e648`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002106d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002106d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800211de`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800211eb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800211de`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800211eb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180021154`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180021154`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800211bd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800211d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021224`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021259`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800211bd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800211d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021224`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021259`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180021199`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180021199`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800210b6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180021105`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800210b6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180021105`

## string_xrefs

- `0x180021201`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180021236`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180021273`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180021085`: `Software\Microsoft\Windows NT\CurrentVersion\ProfileService\References`

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
0x180021050  push    rbx
0x180021052  push    rbp
0x180021053  push    rsi
0x180021054  push    rdi
0x180021055  sub     rsp, 58h
0x180021059  lea     rbx, [rcx+128h]
0x180021060  mov     rsi, rcx
0x180021063  xor     ebp, ebp
0x180021065  mov     rcx, rbx; SRWLock
0x180021068  mov     rdi, rdx
0x18002106b  mov     [rdx], ebp
0x18002106d  call    cs:__imp_AcquireSRWLockExclusive
0x180021073  mov     [rsp+78h+lpdwDisposition], rbp; lpdwDisposition
0x180021078  lea     rax, [rsp+78h+hKey]
0x180021080  mov     [rsp+78h+phkResult], rax; phkResult
0x180021085  lea     rdx, aSoftwareMicros_32; "Software\\Microsoft\\Windows NT\\Curren"...
0x18002108c  mov     [rsp+78h+lpSecurityAttributes], rbp; lpSecurityAttributes
0x180021091  xor     r9d, r9d; lpClass
0x180021094  mov     [rsp+78h+samDesired], 2001Fh; samDesired
0x18002109c  xor     r8d, r8d; Reserved
0x18002109f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800210a6  mov     [rsp+78h+dwOptions], 1; unsigned int
0x1800210ae  mov     [rsp+78h+hKey], rbp
0x1800210b6  call    cs:__imp_RegCreateKeyExW
0x1800210bc  test    eax, eax
0x1800210be  jnz     loc_1800211FC
0x1800210c4  mov     rdx, [rsi+30h]; lpSubKey
0x1800210c8  lea     rax, [rsp+78h+arg_10]
0x1800210d0  mov     rcx, [rsp+78h+hKey]; hKey
0x1800210d8  xor     r9d, r9d; lpClass
0x1800210db  mov     [rsp+78h+lpdwDisposition], rbp; lpdwDisposition
0x1800210e0  xor     r8d, r8d; Reserved
0x1800210e3  mov     [rsp+78h+phkResult], rax; phkResult
0x1800210e8  mov     [rsp+78h+lpSecurityAttributes], rbp; lpSecurityAttributes
0x1800210ed  mov     [rsp+78h+samDesired], 2001Fh; samDesired
0x1800210f5  mov     [rsp+78h+dwOptions], 1; unsigned int
0x1800210fd  mov     [rsp+78h+arg_10], rbp
0x180021105  call    cs:__imp_RegCreateKeyExW
0x18002110b  test    eax, eax
0x18002110d  jnz     loc_180021231
0x180021113  mov     rcx, [rsp+78h+arg_10]; hKey
0x18002111b  lea     rax, [rsp+78h+cbData]
0x180021123  mov     qword ptr [rsp+78h+samDesired], rax; lpcbData
0x180021128  lea     rdx, ValueName; "RefCount"
0x18002112f  lea     rax, [rsp+78h+Data]
0x180021137  mov     [rsp+78h+Data], ebp
0x18002113e  xor     r9d, r9d; lpType
0x180021141  mov     qword ptr [rsp+78h+dwOptions], rax; lpData
0x180021146  xor     r8d, r8d; lpReserved
0x180021149  mov     [rsp+78h+cbData], 4
0x180021154  call    cs:__imp_RegQueryValueExW
0x18002115a  mov     rcx, [rsp+78h+arg_10]; hKey
0x180021162  lea     rax, [rsp+78h+Data]
0x18002116a  inc     [rsp+78h+Data]
0x180021171  lea     rdx, ValueName; "RefCount"
0x180021178  mov     [rsp+78h+samDesired], 4; cbData
0x180021180  mov     r9d, 3; dwType
0x180021186  xor     r8d, r8d; Reserved
0x180021189  mov     qword ptr [rsp+78h+dwOptions], rax; unsigned int
0x18002118e  mov     [rsp+78h+cbData], 4
0x180021199  call    cs:__imp_RegSetValueExW
0x18002119f  test    eax, eax
0x1800211a1  jnz     loc_18002126E
0x1800211a7  mov     rcx, [rsp+78h+arg_10]; hKey
0x1800211af  mov     eax, [rsp+78h+Data]
0x1800211b6  mov     [rdi], eax
0x1800211b8  test    rcx, rcx
0x1800211bb  jz      short loc_1800211C3
0x1800211bd  call    cs:__imp_RegCloseKey
0x1800211c3  mov     rcx, [rsp+78h+hKey]; hKey
0x1800211cb  test    rcx, rcx
0x1800211ce  jz      short loc_1800211D6
0x1800211d0  call    cs:__imp_RegCloseKey
0x1800211d6  test    rbx, rbx
0x1800211d9  jz      short loc_1800211E4
0x1800211db  mov     rcx, rbx; SRWLock
0x1800211de  call    cs:__imp_ReleaseSRWLockExclusive
0x1800211e4  xor     eax, eax
0x1800211e6  jmp     short loc_1800211F3
0x1800211e8  mov     rcx, rbx; SRWLock
0x1800211eb  call    cs:__imp_ReleaseSRWLockExclusive
0x1800211f1  mov     eax, edi
0x1800211f3  add     rsp, 58h
0x1800211f7  pop     rdi
0x1800211f8  pop     rsi
0x1800211f9  pop     rbp
0x1800211fa  pop     rbx
0x1800211fb  retn
0x1800211fc  mov     rcx, [rsp+78h]; this
0x180021201  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180021208  mov     r9d, eax; char *
0x18002120b  mov     edx, 944h; void *
0x180021210  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180021215  mov     rcx, [rsp+78h+hKey]; hKey
0x18002121d  mov     edi, eax
0x18002121f  test    rcx, rcx
0x180021222  jz      short loc_18002122A
0x180021224  call    cs:__imp_RegCloseKey
0x18002122a  test    rbx, rbx
0x18002122d  jz      short loc_1800211F1
0x18002122f  jmp     short loc_1800211E8
0x180021231  mov     rcx, [rsp+78h]; this
0x180021236  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002123d  mov     r9d, eax; char *
0x180021240  mov     edx, 947h; void *
0x180021245  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002124a  mov     rcx, [rsp+78h+arg_10]; hKey
0x180021252  mov     edi, eax
0x180021254  test    rcx, rcx
0x180021257  jz      short loc_18002125F
0x180021259  call    cs:__imp_RegCloseKey
0x18002125f  mov     rcx, [rsp+78h+hKey]
0x180021267  test    rcx, rcx
0x18002126a  jz      short loc_18002122A
0x18002126c  jmp     short loc_180021224
0x18002126e  mov     rcx, [rsp+78h]; this
0x180021273  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002127a  mov     r9d, eax; char *
0x18002127d  mov     edx, 94Fh; void *
0x180021282  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180021287  mov     rcx, [rsp+78h+arg_10]
0x18002128f  mov     edi, eax
0x180021291  test    rcx, rcx
0x180021294  jz      short loc_18002125F
0x180021296  jmp     short loc_180021259
```
