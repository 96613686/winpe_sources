# _anonymous_namespace_::ShouldShowMessage

- ea: `0x140041ef0`
- end: `0x14004209c`
- name: `_anonymous_namespace_::ShouldShowMessage`
- size: `428`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14004209c`

## callees

- `0x140001020`
- `0x140041ef0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140041fc4`
- `ADVAPI32!RegCloseKey` at `0x14004202c`
- `ADVAPI32!RegCloseKey` at `0x140042040`
- `ADVAPI32!RegCloseKey` at `0x140041fc4`
- `ADVAPI32!RegCloseKey` at `0x14004202c`
- `ADVAPI32!RegCloseKey` at `0x140042040`
- `ADVAPI32!RegOpenKeyExW` at `0x140041f44`
- `ADVAPI32!RegOpenKeyExW` at `0x140041f44`
- `ADVAPI32!RegQueryValueExW` at `0x140041f98`
- `ADVAPI32!RegQueryValueExW` at `0x140041f98`
- `KERNEL32!FileTimeToSystemTime` at `0x140042009`
- `KERNEL32!FileTimeToSystemTime` at `0x140042009`
- `KERNEL32!SystemTimeToFileTime` at `0x14004204d`
- `KERNEL32!SystemTimeToFileTime` at `0x140042077`
- `KERNEL32!SystemTimeToFileTime` at `0x14004204d`
- `KERNEL32!SystemTimeToFileTime` at `0x140042077`
- `KERNEL32!CompareFileTime` at `0x140042089`
- `KERNEL32!CompareFileTime` at `0x140042089`
- `KERNEL32!GetLastError` at `0x140042013`
- `KERNEL32!GetLastError` at `0x140042057`
- `KERNEL32!GetLastError` at `0x140042013`
- `KERNEL32!GetLastError` at `0x140042057`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::ShouldShowMessage(__int64 a1, const SYSTEMTIME *a2)
{
  unsigned int v3; // ebx
  HKEY v4; // rdi
  __int64 result; // rax
  signed int LastError; // eax
  signed int v7; // esi
  signed int v8; // ecx
  HKEY hKey; // [rsp+30h] [rbp-50h] BYREF
  DWORD cbData; // [rsp+38h] [rbp-48h] BYREF
  FILETIME Data; // [rsp+40h] [rbp-40h] BYREF
  FILETIME FileTime; // [rsp+48h] [rbp-38h] BYREF
  FILETIME FileTime2; // [rsp+50h] [rbp-30h] BYREF
  FILETIME FileTime1; // [rsp+58h] [rbp-28h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+60h] [rbp-20h] BYREF

  v3 = 0;
  hKey = 0;
  if ( RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\VisualStudio\\17.0", 0, 0x20019u, &hKey) )
    return 0;
  v4 = hKey;
  cbData = 8;
  if ( RegQueryValueExW(hKey, L"SetupMessageTimestamp", 0, (LPDWORD)&hKey, (LPBYTE)&Data, &cbData) || (_DWORD)hKey != 11 )
  {
    if ( v4 )
      RegCloseKey(v4);
    return 0;
  }
  FileTime = Data;
  if ( FileTimeToSystemTime(&FileTime, &SystemTime) )
  {
    if ( v4 )
      RegCloseKey(v4);
  }
  else
  {
    LastError = GetLastError();
    v7 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v7 = LastError;
    if ( v4 )
      RegCloseKey(v4);
    if ( v7 < 0 )
      return 0;
  }
  if ( SystemTimeToFileTime(a2, &FileTime1) && SystemTimeToFileTime(&SystemTime, &FileTime2) )
  {
    LOBYTE(v3) = CompareFileTime(&FileTime1, &FileTime2) <= 0;
    return v3;
  }
  else
  {
    v8 = GetLastError();
    result = (unsigned __int16)v8 | 0x80070000;
    if ( v8 <= 0 )
      return (unsigned int)v8;
  }
  return result;
}

```

## disassembly

```asm
0x140041ef0  mov     r11, rsp
0x140041ef3  mov     [r11+8], rbx
0x140041ef7  mov     [r11+18h], rsi
0x140041efb  mov     [r11+20h], rdi
0x140041eff  push    rbp
0x140041f00  push    r14
0x140041f02  push    r15
0x140041f04  mov     rbp, rsp
0x140041f07  sub     rsp, 80h
0x140041f0e  mov     rax, cs:__security_cookie
0x140041f15  xor     rax, rsp
0x140041f18  mov     [rbp+var_10], rax
0x140041f1c  mov     r14, rdx
0x140041f1f  lea     rax, [rbp+hKey]
0x140041f23  xor     ebx, ebx
0x140041f25  mov     [r11-78h], rax
0x140041f29  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\VisualStudio\\17.0"
0x140041f30  mov     [rbp+hKey], rbx
0x140041f34  mov     r9d, 20019h; samDesired
0x140041f3a  xor     r8d, r8d; ulOptions
0x140041f3d  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140041f44  call    cs:__imp_RegOpenKeyExW
0x140041f4a  mov     ecx, eax
0x140041f4c  mov     r15d, 80070000h
0x140041f52  test    eax, eax
0x140041f54  jnz     short loc_140041F5C
0x140041f56  mov     rdi, [rbp+hKey]
0x140041f5a  jmp     short loc_140041F6E
0x140041f5c  movzx   eax, cx
0x140041f5f  mov     rdi, rbx
0x140041f62  or      eax, r15d
0x140041f65  test    ecx, ecx
0x140041f67  cmovle  eax, ecx
0x140041f6a  test    eax, eax
0x140041f6c  js      short loc_140041FCA
0x140041f6e  lea     rax, [rbp+cbData]
0x140041f72  mov     [rbp+cbData], 8
0x140041f79  mov     [rsp+80h+lpcbData], rax; lpcbData
0x140041f7e  lea     r9, [rbp+hKey]; lpType
0x140041f82  lea     rax, [rbp+Data]
0x140041f86  xor     r8d, r8d; lpReserved
0x140041f89  lea     rdx, aSetupmessageti; "SetupMessageTimestamp"
0x140041f90  mov     [rsp+80h+lpData], rax; lpData
0x140041f95  mov     rcx, rdi; hKey
0x140041f98  call    cs:__imp_RegQueryValueExW
0x140041f9e  mov     ecx, eax
0x140041fa0  test    eax, eax
0x140041fa2  jnz     short loc_140041FAD
0x140041fa4  cmp     dword ptr [rbp+hKey], 0Bh
0x140041fa8  jz      short loc_140041FF5
0x140041faa  lea     ecx, [rax+0Dh]
0x140041fad  movzx   eax, cx
0x140041fb0  or      eax, r15d
0x140041fb3  test    ecx, ecx
0x140041fb5  cmovle  eax, ecx
0x140041fb8  test    eax, eax
0x140041fba  jns     short loc_140041FF5
0x140041fbc  test    rdi, rdi
0x140041fbf  jz      short loc_140041FCA
0x140041fc1  mov     rcx, rdi; hKey
0x140041fc4  call    cs:__imp_RegCloseKey
0x140041fca  xor     eax, eax
0x140041fcc  mov     rcx, [rbp+var_10]
0x140041fd0  xor     rcx, rsp; StackCookie
0x140041fd3  call    __security_check_cookie
0x140041fd8  lea     r11, [rsp+80h+var_s0]
0x140041fe0  mov     rbx, [r11+20h]
0x140041fe4  mov     rsi, [r11+30h]
0x140041fe8  mov     rdi, [r11+38h]
0x140041fec  mov     rsp, r11
0x140041fef  pop     r15
0x140041ff1  pop     r14
0x140041ff3  pop     rbp
0x140041ff4  retn
0x140041ff5  mov     eax, dword ptr [rbp+Data+4]
0x140041ff8  lea     rdx, [rbp+SystemTime]; lpSystemTime
0x140041ffc  mov     [rbp+FileTime.dwHighDateTime], eax
0x140041fff  lea     rcx, [rbp+FileTime]; lpFileTime
0x140042003  mov     eax, dword ptr [rbp+Data]
0x140042006  mov     [rbp+FileTime.dwLowDateTime], eax
0x140042009  call    cs:__imp_FileTimeToSystemTime
0x14004200f  test    eax, eax
0x140042011  jnz     short loc_140042038
0x140042013  call    cs:__imp_GetLastError
0x140042019  movzx   esi, ax
0x14004201c  or      esi, r15d
0x14004201f  test    eax, eax
0x140042021  cmovle  esi, eax
0x140042024  test    rdi, rdi
0x140042027  jz      short loc_140042032
0x140042029  mov     rcx, rdi; hKey
0x14004202c  call    cs:__imp_RegCloseKey
0x140042032  test    esi, esi
0x140042034  js      short loc_140041FCA
0x140042036  jmp     short loc_140042046
0x140042038  test    rdi, rdi
0x14004203b  jz      short loc_140042046
0x14004203d  mov     rcx, rdi; hKey
0x140042040  call    cs:__imp_RegCloseKey
0x140042046  lea     rdx, [rbp+FileTime1]; lpFileTime
0x14004204a  mov     rcx, r14; lpSystemTime
0x14004204d  call    cs:__imp_SystemTimeToFileTime
0x140042053  test    eax, eax
0x140042055  jnz     short loc_14004206F
0x140042057  call    cs:__imp_GetLastError
0x14004205d  mov     ecx, eax
0x14004205f  movzx   eax, ax
0x140042062  or      eax, r15d
0x140042065  test    ecx, ecx
0x140042067  cmovle  eax, ecx
0x14004206a  jmp     loc_140041FCC
0x14004206f  lea     rdx, [rbp+FileTime2]; lpFileTime
0x140042073  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x140042077  call    cs:__imp_SystemTimeToFileTime
0x14004207d  test    eax, eax
0x14004207f  jz      short loc_140042057
0x140042081  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x140042085  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x140042089  call    cs:__imp_CompareFileTime
0x14004208f  test    eax, eax
0x140042091  setle   bl
0x140042094  mov     eax, ebx
0x140042096  jmp     loc_140041FCC
```
