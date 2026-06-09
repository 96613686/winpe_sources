# RegisterUnknownObject(char const *,_GUID const &)

- ea: `0x18006ba44`
- end: `0x18006bcd0`
- name: `?RegisterUnknownObject@@YAHPEBDAEBU_GUID@@@Z`
- size: `652`
- prototype: `__int64 __fastcall(const char *, const struct _GUID *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18004040c`
- `0x18006aeac`

## callees

- `0x1800029b8`
- `0x1800095c8`
- `0x18006ba44`
- `0x18006bf3c`
- `0x18006c2e4`
- `0x180075c90`

## import_xrefs

- `KERNEL32!GetModuleFileNameA` at `0x18006bc02`
- `KERNEL32!GetModuleFileNameA` at `0x18006bc02`
- `ADVAPI32!RegCloseKey` at `0x18006bc75`
- `ADVAPI32!RegCloseKey` at `0x18006bc80`
- `ADVAPI32!RegCloseKey` at `0x18006bc94`
- `ADVAPI32!RegCloseKey` at `0x18006bca4`
- `ADVAPI32!RegCloseKey` at `0x18006bc75`
- `ADVAPI32!RegCloseKey` at `0x18006bc80`
- `ADVAPI32!RegCloseKey` at `0x18006bc94`
- `ADVAPI32!RegCloseKey` at `0x18006bca4`
- `ADVAPI32!RegCreateKeyExA` at `0x18006bb25`
- `ADVAPI32!RegCreateKeyExA` at `0x18006bbe6`
- `ADVAPI32!RegCreateKeyExA` at `0x18006bb25`
- `ADVAPI32!RegCreateKeyExA` at `0x18006bbe6`
- `ADVAPI32!RegSetValueExA` at `0x18006bb95`
- `ADVAPI32!RegSetValueExA` at `0x18006bc36`
- `ADVAPI32!RegSetValueExA` at `0x18006bc66`
- `ADVAPI32!RegSetValueExA` at `0x18006bb95`
- `ADVAPI32!RegSetValueExA` at `0x18006bc36`
- `ADVAPI32!RegSetValueExA` at `0x18006bc66`

## string_xrefs

- `0x18006bab1`: `CLSID\`
- `0x18006bc54`: `ThreadingModel`

## pseudocode

```c
__int64 __fastcall RegisterUnknownObject(const char *a1, const struct _GUID *a2)
{
  __int64 v4; // rax
  DWORD ModuleFileNameA; // eax
  DWORD dwDisposition; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  char v10[40]; // [rsp+68h] [rbp-98h] BYREF
  CHAR SubKey[272]; // [rsp+90h] [rbp-70h] BYREF

  hKey = 0;
  phkResult = 0;
  dwDisposition = 0;
  UnregisterUnknownObject(a2);
  if ( !StringFromGuidA(a2, v10) )
    goto LABEL_15;
  if ( StringCchCopyA(SubKey, 0x104u, "CLSID\\") < 0 )
    goto LABEL_15;
  if ( (int)StringCchCatA(SubKey, 0x104u, v10) < 0 )
    goto LABEL_15;
  if ( RegCreateKeyExA(HKEY_CLASSES_ROOT, SubKey, 0, (LPSTR)Class, 0, 0x2001Fu, 0, &hKey, &dwDisposition) )
    goto LABEL_15;
  if ( StringCchCopyA(SubKey, 0x104u, a1) < 0 )
    goto LABEL_15;
  if ( (int)StringCchCatA(SubKey, 0x104u, " Object") < 0 )
    goto LABEL_15;
  v4 = -1;
  do
    ++v4;
  while ( SubKey[v4] );
  if ( RegSetValueExA(hKey, 0, 0, 1u, (const BYTE *)SubKey, v4 + 1)
    || RegCreateKeyExA(hKey, "InprocServer32", 0, (LPSTR)Class, 0, 0x2001Fu, 0, &phkResult, &dwDisposition)
    || (ModuleFileNameA = GetModuleFileNameA(hInstance, SubKey, 0x104u), SubKey[259] = 0, ModuleFileNameA - 1 > 0x102)
    || RegSetValueExA(phkResult, 0, 0, 1u, (const BYTE *)SubKey, ModuleFileNameA + 1)
    || RegSetValueExA(phkResult, "ThreadingModel", 0, 1u, "Apartment", 0xAu) )
  {
LABEL_15:
    if ( hKey )
      RegCloseKey(hKey);
    if ( phkResult )
      RegCloseKey(phkResult);
    return 0;
  }
  else
  {
    RegCloseKey(phkResult);
    RegCloseKey(hKey);
    return 1;
  }
}

```

## disassembly

```asm
0x18006ba44  mov     [rsp-8+arg_10], rbx
0x18006ba49  mov     [rsp-8+arg_18], rdi
0x18006ba4e  push    rbp
0x18006ba4f  lea     rbp, [rsp-0B0h]
0x18006ba57  sub     rsp, 1B0h
0x18006ba5e  mov     rax, cs:__security_cookie
0x18006ba65  xor     rax, rsp
0x18006ba68  mov     [rbp+0B0h+var_10], rax
0x18006ba6f  mov     rdi, rcx
0x18006ba72  mov     [rsp+1B0h+hKey], 0
0x18006ba7b  mov     rcx, rdx; struct _GUID *
0x18006ba7e  mov     [rsp+1B0h+var_150], 0
0x18006ba87  mov     rbx, rdx
0x18006ba8a  mov     [rsp+1B0h+dwDisposition], 0
0x18006ba92  call    ?UnregisterUnknownObject@@YAHAEBU_GUID@@@Z; UnregisterUnknownObject(_GUID const &)
0x18006ba97  lea     rdx, [rsp+1B0h+var_148]; char *
0x18006ba9c  mov     rcx, rbx; struct _GUID *
0x18006ba9f  call    ?StringFromGuidA@@YAHAEBU_GUID@@PEAD@Z; StringFromGuidA(_GUID const &,char *)
0x18006baa4  test    eax, eax
0x18006baa6  jz      loc_18006BC8A
0x18006baac  mov     ebx, 104h
0x18006bab1  lea     r8, aClsid_0; "CLSID\\"
0x18006bab8  mov     edx, ebx; unsigned __int64
0x18006baba  lea     rcx, [rbp+0B0h+SubKey]; char *
0x18006babe  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18006bac3  test    eax, eax
0x18006bac5  js      loc_18006BC8A
0x18006bacb  lea     r8, [rsp+1B0h+var_148]; char *
0x18006bad0  mov     edx, ebx; unsigned __int64
0x18006bad2  lea     rcx, [rbp+0B0h+SubKey]; char *
0x18006bad6  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x18006badb  test    eax, eax
0x18006badd  js      loc_18006BC8A
0x18006bae3  lea     rax, [rsp+1B0h+dwDisposition]
0x18006bae8  xor     r8d, r8d; Reserved
0x18006baeb  mov     [rsp+1B0h+lpdwDisposition], rax; lpdwDisposition
0x18006baf0  lea     r9, Class; lpClass
0x18006baf7  lea     rax, [rsp+1B0h+hKey]
0x18006bafc  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18006bb03  mov     [rsp+1B0h+phkResult], rax; phkResult
0x18006bb08  lea     rdx, [rbp+0B0h+SubKey]; lpSubKey
0x18006bb0c  mov     [rsp+1B0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18006bb15  mov     [rsp+1B0h+samDesired], 2001Fh; samDesired
0x18006bb1d  mov     [rsp+1B0h+dwOptions], 0; dwOptions
0x18006bb25  call    cs:__imp_RegCreateKeyExA
0x18006bb2b  test    eax, eax
0x18006bb2d  jnz     loc_18006BC8A
0x18006bb33  mov     r8, rdi; char *
0x18006bb36  lea     rcx, [rbp+0B0h+SubKey]; char *
0x18006bb3a  mov     edx, ebx; unsigned __int64
0x18006bb3c  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18006bb41  test    eax, eax
0x18006bb43  js      loc_18006BC8A
0x18006bb49  lea     r8, aObject; " Object"
0x18006bb50  mov     edx, ebx; unsigned __int64
0x18006bb52  lea     rcx, [rbp+0B0h+SubKey]; char *
0x18006bb56  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x18006bb5b  test    eax, eax
0x18006bb5d  js      loc_18006BC8A
0x18006bb63  lea     rcx, [rbp+0B0h+SubKey]
0x18006bb67  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006bb6b  inc     rax
0x18006bb6e  cmp     byte ptr [rcx+rax], 0
0x18006bb72  jnz     short loc_18006BB6B
0x18006bb74  mov     rcx, [rsp+1B0h+hKey]; hKey
0x18006bb79  inc     eax
0x18006bb7b  mov     [rsp+1B0h+samDesired], eax; cbData
0x18006bb7f  mov     edi, 1
0x18006bb84  lea     rax, [rbp+0B0h+SubKey]
0x18006bb88  mov     r9d, edi; dwType
0x18006bb8b  xor     r8d, r8d; Reserved
0x18006bb8e  mov     qword ptr [rsp+1B0h+dwOptions], rax; lpData
0x18006bb93  xor     edx, edx; lpValueName
0x18006bb95  call    cs:__imp_RegSetValueExA
0x18006bb9b  test    eax, eax
0x18006bb9d  jnz     loc_18006BC8A
0x18006bba3  mov     rcx, [rsp+1B0h+hKey]; hKey
0x18006bba8  lea     rax, [rsp+1B0h+dwDisposition]
0x18006bbad  mov     [rsp+1B0h+lpdwDisposition], rax; lpdwDisposition
0x18006bbb2  lea     r9, Class; lpClass
0x18006bbb9  lea     rax, [rsp+1B0h+var_150]
0x18006bbbe  xor     r8d, r8d; Reserved
0x18006bbc1  mov     [rsp+1B0h+phkResult], rax; phkResult
0x18006bbc6  lea     rdx, aInprocserver32; "InprocServer32"
0x18006bbcd  mov     [rsp+1B0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18006bbd6  mov     [rsp+1B0h+samDesired], 2001Fh; samDesired
0x18006bbde  mov     [rsp+1B0h+dwOptions], 0; dwOptions
0x18006bbe6  call    cs:__imp_RegCreateKeyExA
0x18006bbec  test    eax, eax
0x18006bbee  jnz     loc_18006BC8A
0x18006bbf4  mov     rcx, cs:hInstance; hModule
0x18006bbfb  lea     rdx, [rbp+0B0h+SubKey]; lpFilename
0x18006bbff  mov     r8d, ebx; nSize
0x18006bc02  call    cs:__imp_GetModuleFileNameA
0x18006bc08  mov     [rbp+0B0h+var_1D], 0
0x18006bc0f  lea     ecx, [rax-1]
0x18006bc12  cmp     ecx, 102h
0x18006bc18  ja      short loc_18006BC8A
0x18006bc1a  mov     rcx, [rsp+1B0h+var_150]; hKey
0x18006bc1f  inc     eax
0x18006bc21  mov     [rsp+1B0h+samDesired], eax; cbData
0x18006bc25  mov     r9d, edi; dwType
0x18006bc28  lea     rax, [rbp+0B0h+SubKey]
0x18006bc2c  xor     r8d, r8d; Reserved
0x18006bc2f  xor     edx, edx; lpValueName
0x18006bc31  mov     qword ptr [rsp+1B0h+dwOptions], rax; lpData
0x18006bc36  call    cs:__imp_RegSetValueExA
0x18006bc3c  test    eax, eax
0x18006bc3e  jnz     short loc_18006BC8A
0x18006bc40  lea     rcx, aApartment; "Apartment"
0x18006bc47  mov     [rsp+1B0h+samDesired], 0Ah; cbData
0x18006bc4f  mov     qword ptr [rsp+1B0h+dwOptions], rcx; lpData
0x18006bc54  lea     rdx, aThreadingmodel; "ThreadingModel"
0x18006bc5b  mov     rcx, [rsp+1B0h+var_150]; hKey
0x18006bc60  mov     r9d, edi; dwType
0x18006bc63  xor     r8d, r8d; Reserved
0x18006bc66  call    cs:__imp_RegSetValueExA
0x18006bc6c  test    eax, eax
0x18006bc6e  jnz     short loc_18006BC8A
0x18006bc70  mov     rcx, [rsp+1B0h+var_150]; hKey
0x18006bc75  call    cs:__imp_RegCloseKey
0x18006bc7b  mov     rcx, [rsp+1B0h+hKey]; hKey
0x18006bc80  call    cs:__imp_RegCloseKey
0x18006bc86  mov     eax, edi
0x18006bc88  jmp     short loc_18006BCAC
0x18006bc8a  mov     rcx, [rsp+1B0h+hKey]; hKey
0x18006bc8f  test    rcx, rcx
0x18006bc92  jz      short loc_18006BC9A
0x18006bc94  call    cs:__imp_RegCloseKey
0x18006bc9a  mov     rcx, [rsp+1B0h+var_150]; hKey
0x18006bc9f  test    rcx, rcx
0x18006bca2  jz      short loc_18006BCAA
0x18006bca4  call    cs:__imp_RegCloseKey
0x18006bcaa  xor     eax, eax
0x18006bcac  mov     rcx, [rbp+0B0h+var_10]
0x18006bcb3  xor     rcx, rsp; StackCookie
0x18006bcb6  call    __security_check_cookie
0x18006bcbb  lea     r11, [rsp+1B0h+var_s0]
0x18006bcc3  mov     rbx, [r11+20h]
0x18006bcc7  mov     rdi, [r11+28h]
0x18006bccb  mov     rsp, r11
0x18006bcce  pop     rbp
0x18006bccf  retn
```
