# eksvcDebugEnabled(ulong)

- ea: `0x180004c50`
- end: `0x180004da7`
- name: `?eksvcDebugEnabled@@YA_NK@Z`
- size: `343`
- prototype: `bool __fastcall(char)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004790`
- `0x180005ac0`

## callees

- `0x180004c50`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180004c8f`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180004c8f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004d62`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004d62`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004cd1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004cd1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004d23`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004d23`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004c7f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004c7f`

## pseudocode

```c
bool __fastcall eksvcDebugEnabled(char a1)
{
  int v2; // edi
  __int64 i; // rsi
  const WCHAR *v4; // rdx
  bool result; // al
  DWORD Type; // [rsp+60h] [rbp+8h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+68h] [rbp+10h] BYREF
  FILETIME FileTime2; // [rsp+70h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+20h] BYREF

  FileTime2 = (FILETIME)(qword_180012978 + 3000000000LL);
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  if ( CompareFileTime(&SystemTimeAsFileTime, &FileTime2) <= 0 )
  {
    v2 = dword_1800126E8;
  }
  else
  {
    qword_180012978 = (__int64)SystemTimeAsFileTime;
    hKey = 0;
    v2 = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Cryptography\\AutoEnrollment", 0, 0x20019u, &hKey) )
    {
      for ( i = 0; i != 2; ++i )
      {
        v4 = off_18000C1A0[i];
        Type = 0;
        FileTime2.dwLowDateTime = 0;
        SystemTimeAsFileTime.dwLowDateTime = 4;
        if ( !RegQueryValueExW(hKey, v4, 0, &Type, (LPBYTE)&FileTime2, (LPDWORD)&SystemTimeAsFileTime)
          && Type == 4
          && SystemTimeAsFileTime.dwLowDateTime == 4
          && FileTime2.dwLowDateTime )
        {
          v2 |= FileTime2.dwLowDateTime;
        }
      }
    }
    if ( hKey )
      RegCloseKey(hKey);
    dword_1800126E8 = v2;
  }
  result = (a1 & 1) != 0 && v2;
  if ( (a1 & 2) != 0 )
  {
    if ( v2 )
      return 1;
  }
  return result;
}

```

## disassembly

```asm
0x180004c50  push    rdi
0x180004c52  sub     rsp, 50h
0x180004c56  mov     [rsp+58h+var_10], rbx
0x180004c5b  mov     ebx, ecx
0x180004c5d  mov     ecx, 0B2D05E00h
0x180004c62  mov     [rsp+58h+var_18], rbp
0x180004c67  add     rcx, cs:qword_180012978
0x180004c6e  xor     ebp, ebp
0x180004c70  mov     qword ptr [rsp+58h+FileTime2.dwLowDateTime], rcx
0x180004c75  lea     rcx, [rsp+58h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180004c7a  mov     qword ptr [rsp+58h+SystemTimeAsFileTime.dwLowDateTime], rbp
0x180004c7f  call    cs:__imp_GetSystemTimeAsFileTime
0x180004c85  lea     rdx, [rsp+58h+FileTime2]; lpFileTime2
0x180004c8a  lea     rcx, [rsp+58h+SystemTimeAsFileTime]; lpFileTime1
0x180004c8f  call    cs:__imp_CompareFileTime
0x180004c95  test    eax, eax
0x180004c97  jle     loc_180004D70
0x180004c9d  mov     rax, qword ptr [rsp+58h+SystemTimeAsFileTime.dwLowDateTime]
0x180004ca2  lea     rdx, SubKey; "Software\\Microsoft\\Cryptography\\Auto"...
0x180004ca9  mov     cs:qword_180012978, rax
0x180004cb0  mov     r9d, 20019h; samDesired
0x180004cb6  lea     rax, [rsp+58h+hKey]
0x180004cbb  mov     [rsp+58h+hKey], rbp
0x180004cc0  xor     r8d, r8d; ulOptions
0x180004cc3  mov     [rsp+58h+phkResult], rax; phkResult
0x180004cc8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180004ccf  mov     edi, ebp
0x180004cd1  call    cs:__imp_RegOpenKeyExW
0x180004cd7  test    eax, eax
0x180004cd9  jnz     short loc_180004D58
0x180004cdb  mov     [rsp+58h+var_20], rsi
0x180004ce0  mov     esi, ebp
0x180004ce2  mov     [rsp+58h+var_28], r14
0x180004ce7  lea     r14, off_18000C1A0; "Debug"
0x180004cee  mov     rdx, [r14+rsi*8]; lpValueName
0x180004cf2  lea     rax, [rsp+58h+SystemTimeAsFileTime]
0x180004cf7  mov     rcx, [rsp+58h+hKey]; hKey
0x180004cfc  lea     r9, [rsp+58h+Type]; lpType
0x180004d01  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180004d06  xor     r8d, r8d; lpReserved
0x180004d09  lea     rax, [rsp+58h+FileTime2]
0x180004d0e  mov     [rsp+58h+Type], ebp
0x180004d12  mov     [rsp+58h+phkResult], rax; lpData
0x180004d17  mov     [rsp+58h+FileTime2.dwLowDateTime], ebp
0x180004d1b  mov     [rsp+58h+SystemTimeAsFileTime.dwLowDateTime], 4
0x180004d23  call    cs:__imp_RegQueryValueExW
0x180004d29  test    eax, eax
0x180004d2b  jnz     short loc_180004D45
0x180004d2d  cmp     [rsp+58h+Type], 4
0x180004d32  jnz     short loc_180004D45
0x180004d34  cmp     [rsp+58h+SystemTimeAsFileTime.dwLowDateTime], 4
0x180004d39  jnz     short loc_180004D45
0x180004d3b  mov     eax, [rsp+58h+FileTime2.dwLowDateTime]
0x180004d3f  test    eax, eax
0x180004d41  jz      short loc_180004D45
0x180004d43  or      edi, eax
0x180004d45  inc     rsi
0x180004d48  cmp     rsi, 2
0x180004d4c  jnz     short loc_180004CEE
0x180004d4e  mov     r14, [rsp+58h+var_28]
0x180004d53  mov     rsi, [rsp+58h+var_20]
0x180004d58  mov     rcx, [rsp+58h+hKey]; hKey
0x180004d5d  test    rcx, rcx
0x180004d60  jz      short loc_180004D68
0x180004d62  call    cs:__imp_RegCloseKey
0x180004d68  mov     cs:dword_1800126E8, edi
0x180004d6e  jmp     short loc_180004D76
0x180004d70  mov     edi, cs:dword_1800126E8
0x180004d76  mov     rbp, [rsp+58h+var_18]
0x180004d7b  test    bl, 1
0x180004d7e  jz      short loc_180004D88
0x180004d80  test    edi, edi
0x180004d82  jz      short loc_180004D88
0x180004d84  mov     al, 1
0x180004d86  jmp     short loc_180004D8A
0x180004d88  xor     al, al
0x180004d8a  test    bl, 2
0x180004d8d  mov     rbx, [rsp+58h+var_10]
0x180004d92  jz      short loc_180004DA1
0x180004d94  test    edi, edi
0x180004d96  movzx   eax, al
0x180004d99  mov     ecx, 1
0x180004d9e  cmovnz  eax, ecx
0x180004da1  add     rsp, 50h
0x180004da5  pop     rdi
0x180004da6  retn
```
