# ReadDnsPolicyConfigInformation

- ea: `0x180073de0`
- end: `0x180073f34`
- name: `ReadDnsPolicyConfigInformation`
- size: `340`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006d40`
- `0x180059170`
- `0x1800a4a7c`

## callees

- `0x180017900`
- `0x1800659a4`
- `0x180073de0`
- `0x1800813d4`
- `0x18008b5f0`
- `0x1800a4c10`
- `0x1800dc9e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180073e5f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180073e5f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180073e48`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180073e48`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180073e77`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180073e77`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180073ef0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180073ef0`

## string_xrefs

- `0x180073e3a`: `SOFTWARE\Policies\Microsoft\Windows NT\DNSClient\DnsPolicyConfig`

## pseudocode

```c
__int64 __fastcall ReadDnsPolicyConfigInformation(unsigned int a1)
{
  char v1; // bl
  unsigned int DnsPolicyTableConfigInfo; // ebx
  unsigned int SuffixAndPrefixPolicyTable; // eax
  __int64 v4; // rdx
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF

  v1 = a1;
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_d(1035, 50, WPP_3bf4b884ef3b304972f753916e0d484b_Traceguids, a1);
  if ( (v1 & 2) != 0 )
  {
    hKey = 0;
    DnsPolicyTableConfigInfo = RegOpenKeyExW(
                                 HKEY_LOCAL_MACHINE,
                                 L"SOFTWARE\\Policies\\Microsoft\\Windows NT\\DNSClient\\DnsPolicyConfig",
                                 0,
                                 0x20019u,
                                 &hKey);
    if ( !DnsPolicyTableConfigInfo )
    {
      RegCloseKey(hKey);
      goto LABEL_16;
    }
  }
  AcquireSRWLockExclusive(&g_DnsPolicyTableLock);
  SuffixAndPrefixPolicyTable = AllocateSuffixAndPrefixPolicyTable(&g_DnsPolicyTable);
  DnsPolicyTableConfigInfo = SuffixAndPrefixPolicyTable;
  if ( SuffixAndPrefixPolicyTable )
  {
    if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
      goto LABEL_15;
    v4 = 51;
LABEL_14:
    WPP_SF_d(1035, v4, WPP_3bf4b884ef3b304972f753916e0d484b_Traceguids, SuffixAndPrefixPolicyTable);
    goto LABEL_15;
  }
  EmptyDnsPolicyTable();
  DnsPolicyTableConfigInfo = ReadDnsPolicyTableConfigInfo();
  if ( !DnsPolicyTableConfigInfo )
  {
    SuffixAndPrefixPolicyTable = CanonicalizeDnsPolicyTable();
    DnsPolicyTableConfigInfo = SuffixAndPrefixPolicyTable;
    if ( !SuffixAndPrefixPolicyTable || (BYTE1(xmmword_1801119E0) & 8) == 0 )
      goto LABEL_15;
    v4 = 52;
    goto LABEL_14;
  }
  EmptyDnsPolicyTable();
LABEL_15:
  ReleaseSRWLockExclusive(&g_DnsPolicyTableLock);
LABEL_16:
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_d(1035, 53, WPP_3bf4b884ef3b304972f753916e0d484b_Traceguids, DnsPolicyTableConfigInfo);
  return DnsPolicyTableConfigInfo;
}

```

## disassembly

```asm
0x180073de0  push    rbx
0x180073de2  sub     rsp, 40h
0x180073de6  mov     rax, cs:__security_cookie
0x180073ded  xor     rax, rsp
0x180073df0  mov     [rsp+48h+var_10], rax
0x180073df5  mov     ebx, ecx
0x180073df7  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180073dfe  jz      short loc_180073E19
0x180073e00  mov     edx, 32h ; '2'
0x180073e05  lea     r8, WPP_3bf4b884ef3b304972f753916e0d484b_Traceguids
0x180073e0c  mov     ecx, 40Bh
0x180073e11  mov     r9d, ebx
0x180073e14  call    WPP_SF_d
0x180073e19  test    bl, 2
0x180073e1c  jz      short loc_180073E70
0x180073e1e  lea     rax, [rsp+48h+hKey]
0x180073e23  mov     [rsp+48h+hKey], 0
0x180073e2c  mov     r9d, 20019h; samDesired
0x180073e32  mov     [rsp+48h+phkResult], rax; phkResult
0x180073e37  xor     r8d, r8d; ulOptions
0x180073e3a  lea     rdx, aSoftwarePolici_1; "SOFTWARE\\Policies\\Microsoft\\Windows "...
0x180073e41  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180073e48  call    cs:__imp_RegOpenKeyExW
0x180073e4f  nop     dword ptr [rax+rax+00h]
0x180073e54  mov     ebx, eax
0x180073e56  test    eax, eax
0x180073e58  jnz     short loc_180073E70
0x180073e5a  mov     rcx, [rsp+48h+hKey]; hKey
0x180073e5f  call    cs:__imp_RegCloseKey
0x180073e66  nop     dword ptr [rax+rax+00h]
0x180073e6b  jmp     loc_180073EFC
0x180073e70  lea     rcx, g_DnsPolicyTableLock; SRWLock
0x180073e77  call    cs:__imp_AcquireSRWLockExclusive
0x180073e7e  nop     dword ptr [rax+rax+00h]
0x180073e83  lea     rcx, g_DnsPolicyTable
0x180073e8a  call    AllocateSuffixAndPrefixPolicyTable
0x180073e8f  mov     ebx, eax
0x180073e91  test    eax, eax
0x180073e93  jnz     short loc_180073EC7
0x180073e95  call    EmptyDnsPolicyTable
0x180073e9a  call    ReadDnsPolicyTableConfigInfo
0x180073e9f  mov     ebx, eax
0x180073ea1  test    eax, eax
0x180073ea3  jz      short loc_180073EAC
0x180073ea5  call    EmptyDnsPolicyTable
0x180073eaa  jmp     short loc_180073EE9
0x180073eac  call    CanonicalizeDnsPolicyTable
0x180073eb1  mov     ebx, eax
0x180073eb3  test    eax, eax
0x180073eb5  jz      short loc_180073EE9
0x180073eb7  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180073ebe  jz      short loc_180073EE9
0x180073ec0  mov     edx, 34h ; '4'
0x180073ec5  jmp     short loc_180073ED5
0x180073ec7  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180073ece  jz      short loc_180073EE9
0x180073ed0  mov     edx, 33h ; '3'
0x180073ed5  mov     r9d, eax
0x180073ed8  lea     r8, WPP_3bf4b884ef3b304972f753916e0d484b_Traceguids
0x180073edf  mov     ecx, 40Bh
0x180073ee4  call    WPP_SF_d
0x180073ee9  lea     rcx, g_DnsPolicyTableLock; SRWLock
0x180073ef0  call    cs:__imp_ReleaseSRWLockExclusive
0x180073ef7  nop     dword ptr [rax+rax+00h]
0x180073efc  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180073f03  jz      short loc_180073F1E
0x180073f05  mov     edx, 35h ; '5'
0x180073f0a  lea     r8, WPP_3bf4b884ef3b304972f753916e0d484b_Traceguids
0x180073f11  mov     ecx, 40Bh
0x180073f16  mov     r9d, ebx
0x180073f19  call    WPP_SF_d
0x180073f1e  mov     eax, ebx
0x180073f20  mov     rcx, [rsp+48h+var_10]
0x180073f25  xor     rcx, rsp; StackCookie
0x180073f28  call    __security_check_cookie
0x180073f2d  add     rsp, 40h
0x180073f31  pop     rbx
0x180073f32  retn
```
