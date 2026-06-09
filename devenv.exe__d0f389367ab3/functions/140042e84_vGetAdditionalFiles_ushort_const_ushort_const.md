# vGetAdditionalFiles(ushort const *,ushort const *)

- ea: `0x140042e84`
- end: `0x140042ff0`
- name: `?vGetAdditionalFiles@@YAXPEBG0@Z`
- size: `364`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140043800`

## callees

- `0x140001020`
- `0x140001040`
- `0x140042e74`
- `0x140042e84`
- `0x140043b10`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140042fc8`
- `ADVAPI32!RegCloseKey` at `0x140042fc8`
- `ADVAPI32!RegOpenKeyExW` at `0x140042f3b`
- `ADVAPI32!RegOpenKeyExW` at `0x140042f3b`
- `ADVAPI32!RegSetValueExW` at `0x140042f73`
- `ADVAPI32!RegSetValueExW` at `0x140042fbd`
- `ADVAPI32!RegSetValueExW` at `0x140042f73`
- `ADVAPI32!RegSetValueExW` at `0x140042fbd`
- `KERNEL32!SystemTimeToFileTime` at `0x140042f8e`
- `KERNEL32!SystemTimeToFileTime` at `0x140042f8e`
- `KERNEL32!GetSystemTime` at `0x140042f7e`
- `KERNEL32!GetSystemTime` at `0x140042f7e`
- `KERNEL32!GetCurrentProcessId` at `0x140042ed3`
- `KERNEL32!GetCurrentProcessId` at `0x140042ed3`
- `SHELL32!SHGetFolderPathW` at `0x140042f07`
- `SHELL32!SHGetFolderPathW` at `0x140042f07`

## pseudocode

```c
void __fastcall vGetAdditionalFiles(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  HKEY phkResult; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-C8h] BYREF
  struct _FILETIME FileTime; // [rsp+40h] [rbp-C0h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR pszPath; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v8[526]; // [rsp+62h] [rbp-9Eh] BYREF
  WCHAR SubKey[264]; // [rsp+270h] [rbp+170h] BYREF

  pszPath = 0;
  memset_0(v8, 0, 0x206u);
  SEHCollectAppIdFiles(a1);
  GetCurrentProcessId();
  swprintf_s<260>(SubKey, (wchar_t *)L"%s\\PIDs\\%d");
  if ( SHGetFolderPathW(0, 28, 0, 0, &pszPath) >= 0 )
  {
    phkResult = 0;
    if ( !RegOpenKeyExW(HKEY_CURRENT_USER, SubKey, 0, 0x20006u, &phkResult) )
    {
      *(_DWORD *)Data = 2;
      RegSetValueExW(phkResult, L"ShutdownReason", 0, 4u, Data, 4u);
      GetSystemTime(&SystemTime);
      if ( SystemTimeToFileTime(&SystemTime, &FileTime) )
        RegSetValueExW(phkResult, L"CrashTime", 0, 0xBu, (const BYTE *)&FileTime, 8u);
      RegCloseKey(phkResult);
    }
  }
}

```

## disassembly

```asm
0x140042e84  mov     [rsp-8+arg_10], rbx
0x140042e89  push    rbp
0x140042e8a  push    rsi
0x140042e8b  push    rdi
0x140042e8c  lea     rbp, [rsp-390h]
0x140042e94  sub     rsp, 490h
0x140042e9b  mov     rax, cs:__security_cookie
0x140042ea2  xor     rax, rsp
0x140042ea5  mov     [rbp+3A0h+var_20], rax
0x140042eac  mov     rdi, rdx
0x140042eaf  mov     rbx, rcx
0x140042eb2  xor     esi, esi
0x140042eb4  lea     rcx, [rsp+4A0h+var_43E]; void *
0x140042eb9  xor     edx, edx; Val
0x140042ebb  mov     [rsp+4A0h+var_440], si
0x140042ec0  mov     r8d, 206h; Size
0x140042ec6  call    memset_0
0x140042ecb  mov     rcx, rbx; unsigned __int16 *
0x140042ece  call    ?SEHCollectAppIdFiles@@YAXPEBG@Z; SEHCollectAppIdFiles(ushort const *)
0x140042ed3  call    cs:__imp_GetCurrentProcessId
0x140042ed9  mov     r8, rdi
0x140042edc  lea     rdx, aSPidsD; "%s\\PIDs\\%d"
0x140042ee3  mov     r9d, eax
0x140042ee6  lea     rcx, [rbp+3A0h+SubKey]; Buffer
0x140042eed  call    ??$swprintf_s@$0BAE@@@YAHAEAY0BAE@GPEBGZZ; swprintf_s<260>(ushort (&)[260],ushort const *,...)
0x140042ef2  lea     rax, [rsp+4A0h+var_440]
0x140042ef7  xor     r9d, r9d; dwFlags
0x140042efa  xor     r8d, r8d; hToken
0x140042efd  mov     [rsp+4A0h+pszPath], rax; pszPath
0x140042f02  lea     edx, [rsi+1Ch]; csidl
0x140042f05  xor     ecx, ecx; hwnd
0x140042f07  call    cs:__imp_SHGetFolderPathW
0x140042f0d  test    eax, eax
0x140042f0f  js      loc_140042FCE
0x140042f15  lea     rax, [rsp+4A0h+phkResult]
0x140042f1a  mov     [rsp+4A0h+phkResult], rsi
0x140042f1f  mov     r9d, 20006h; samDesired
0x140042f25  mov     [rsp+4A0h+pszPath], rax; phkResult
0x140042f2a  xor     r8d, r8d; ulOptions
0x140042f2d  lea     rdx, [rbp+3A0h+SubKey]; lpSubKey
0x140042f34  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140042f3b  call    cs:__imp_RegOpenKeyExW
0x140042f41  test    eax, eax
0x140042f43  jnz     loc_140042FCE
0x140042f49  mov     rcx, [rsp+4A0h+phkResult]; hKey
0x140042f4e  lea     r9d, [rsi+4]; dwType
0x140042f52  lea     rax, [rsp+4A0h+Data]
0x140042f57  mov     [rsp+4A0h+cbData], r9d; cbData
0x140042f5c  xor     r8d, r8d; Reserved
0x140042f5f  mov     [rsp+4A0h+pszPath], rax; lpData
0x140042f64  lea     rdx, aShutdownreason; "ShutdownReason"
0x140042f6b  mov     dword ptr [rsp+4A0h+Data], 2
0x140042f73  call    cs:__imp_RegSetValueExW
0x140042f79  lea     rcx, [rsp+4A0h+SystemTime]; lpSystemTime
0x140042f7e  call    cs:__imp_GetSystemTime
0x140042f84  lea     rdx, [rsp+4A0h+FileTime]; lpFileTime
0x140042f89  lea     rcx, [rsp+4A0h+SystemTime]; lpSystemTime
0x140042f8e  call    cs:__imp_SystemTimeToFileTime
0x140042f94  test    eax, eax
0x140042f96  jz      short loc_140042FC3
0x140042f98  mov     rcx, [rsp+4A0h+phkResult]; hKey
0x140042f9d  lea     rax, [rsp+4A0h+FileTime]
0x140042fa2  mov     [rsp+4A0h+cbData], 8; cbData
0x140042faa  lea     r9d, [rsi+0Bh]; dwType
0x140042fae  xor     r8d, r8d; Reserved
0x140042fb1  mov     [rsp+4A0h+pszPath], rax; lpData
0x140042fb6  lea     rdx, aCrashtime; "CrashTime"
0x140042fbd  call    cs:__imp_RegSetValueExW
0x140042fc3  mov     rcx, [rsp+4A0h+phkResult]; hKey
0x140042fc8  call    cs:__imp_RegCloseKey
0x140042fce  mov     rcx, [rbp+3A0h+var_20]
0x140042fd5  xor     rcx, rsp; StackCookie
0x140042fd8  call    __security_check_cookie
0x140042fdd  mov     rbx, [rsp+4A0h+arg_10]
0x140042fe5  add     rsp, 490h
0x140042fec  pop     rdi
0x140042fed  pop     rsi
0x140042fee  pop     rbp
0x140042fef  retn
```
