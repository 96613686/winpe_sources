# GetCatalogVersionFromRegistry(__int64 *)

- ea: `0x180002fb8`
- end: `0x1800030f4`
- name: `?GetCatalogVersionFromRegistry@@YAJPEA_J@Z`
- size: `316`
- prototype: `__int64 __fastcall(LPBYTE lpData)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800012e4`
- `0x1800029c8`

## callees

- `0x180002fb8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003039`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003039`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000308b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000308b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800030c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800030c5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800030b8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800030b8`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180003027`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180003027`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x180002ff7`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x180002ff7`

## string_xrefs

- `0x180002fec`: `Global\__ComCatalogCache__`
- `0x18000307d`: `Software\Microsoft\COM3`

## pseudocode

```c
__int64 __fastcall GetCatalogVersionFromRegistry(LPBYTE lpData)
{
  HANDLE v2; // rcx
  _QWORD *v3; // rax
  signed int v4; // edi
  signed int LastError; // eax
  unsigned int v6; // ebx
  LSTATUS v7; // eax
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp+18h] BYREF

  cbData = 8;
  v2 = hObject;
  phkResult = 0;
  if ( !hObject && (hObject = OpenFileMappingW(4u, 0, L"Global\\__ComCatalogCache__"), (v2 = hObject) == 0)
    || (v3 = lpBaseAddress, v4 = 0, !lpBaseAddress) && (v3 = MapViewOfFile(v2, 4u, 0, 0, 0), (lpBaseAddress = v3) == 0) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    v3 = lpBaseAddress;
  }
  v6 = 0;
  if ( v4 >= 0 )
    v6 = v4;
  if ( !v3 )
  {
    v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\COM3", 0, 0x20119u, &phkResult);
    v6 = v7;
    if ( v7 )
    {
      if ( v7 <= 0 )
        return v6;
      v6 = (unsigned __int16)v7;
    }
    else
    {
      v6 = RegQueryValueExW(phkResult, L"REGDBVersion", 0, 0, lpData, &cbData);
      RegCloseKey(phkResult);
      if ( (int)v6 <= 0 )
        return v6;
      v6 = (unsigned __int16)v6;
    }
    v6 |= 0x80070000;
    return v6;
  }
  *(_QWORD *)lpData = v3[1];
  return v6;
}

```

## disassembly

```asm
0x180002fb8  mov     rax, rsp
0x180002fbb  mov     [rax+8], rbx
0x180002fbf  mov     [rax+20h], rdi
0x180002fc3  push    r14
0x180002fc5  sub     rsp, 30h
0x180002fc9  mov     r14, rcx
0x180002fcc  mov     dword ptr [rax+10h], 8
0x180002fd3  mov     rcx, cs:hObject
0x180002fda  mov     ebx, 4
0x180002fdf  mov     qword ptr [rax+18h], 0
0x180002fe7  test    rcx, rcx
0x180002fea  jnz     short loc_18000300C
0x180002fec  lea     r8, Name; "Global\\__ComCatalogCache__"
0x180002ff3  xor     edx, edx; bInheritHandle
0x180002ff5  mov     ecx, ebx; dwDesiredAccess
0x180002ff7  call    cs:__imp_OpenFileMappingW
0x180002ffd  mov     cs:hObject, rax
0x180003004  mov     rcx, rax; hFileMappingObject
0x180003007  test    rax, rax
0x18000300a  jz      short loc_180003039
0x18000300c  mov     rax, cs:lpBaseAddress
0x180003013  xor     edi, edi
0x180003015  test    rax, rax
0x180003018  jnz     short loc_180003055
0x18000301a  xor     r9d, r9d; dwFileOffsetLow
0x18000301d  mov     [rsp+38h+dwNumberOfBytesToMap], rdi; dwNumberOfBytesToMap
0x180003022  xor     r8d, r8d; dwFileOffsetHigh
0x180003025  mov     edx, ebx; dwDesiredAccess
0x180003027  call    cs:__imp_MapViewOfFile
0x18000302d  mov     cs:lpBaseAddress, rax
0x180003034  test    rax, rax
0x180003037  jnz     short loc_180003055
0x180003039  call    cs:__imp_GetLastError
0x18000303f  mov     edi, eax
0x180003041  test    eax, eax
0x180003043  jle     short loc_18000304E
0x180003045  movzx   edi, ax
0x180003048  or      edi, 80070000h
0x18000304e  mov     rax, cs:lpBaseAddress
0x180003055  xor     ebx, ebx
0x180003057  test    edi, edi
0x180003059  cmovns  ebx, edi
0x18000305c  test    rax, rax
0x18000305f  jz      short loc_18000306A
0x180003061  mov     rax, [rax+8]
0x180003065  mov     [r14], rax
0x180003068  jmp     short loc_1800030E1
0x18000306a  lea     rax, [rsp+38h+phkResult]
0x18000306f  mov     r9d, 20119h; samDesired
0x180003075  xor     r8d, r8d; ulOptions
0x180003078  mov     [rsp+38h+dwNumberOfBytesToMap], rax; phkResult
0x18000307d  lea     rdx, SubKey; "Software\\Microsoft\\COM3"
0x180003084  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000308b  call    cs:__imp_RegOpenKeyExW
0x180003091  mov     ebx, eax
0x180003093  test    eax, eax
0x180003095  jnz     short loc_1800030D6
0x180003097  mov     rcx, [rsp+38h+phkResult]; hKey
0x18000309c  lea     rax, [rsp+38h+cbData]
0x1800030a1  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1800030a6  lea     rdx, ValueName; "REGDBVersion"
0x1800030ad  xor     r9d, r9d; lpType
0x1800030b0  mov     [rsp+38h+dwNumberOfBytesToMap], r14; lpData
0x1800030b5  xor     r8d, r8d; lpReserved
0x1800030b8  call    cs:__imp_RegQueryValueExW
0x1800030be  mov     rcx, [rsp+38h+phkResult]; hKey
0x1800030c3  mov     ebx, eax
0x1800030c5  call    cs:__imp_RegCloseKey
0x1800030cb  test    ebx, ebx
0x1800030cd  jz      short loc_1800030E1
0x1800030cf  jle     short loc_1800030E1
0x1800030d1  movzx   ebx, bx
0x1800030d4  jmp     short loc_1800030DB
0x1800030d6  jle     short loc_1800030E1
0x1800030d8  movzx   ebx, ax
0x1800030db  or      ebx, 80070000h
0x1800030e1  mov     rdi, [rsp+38h+arg_18]
0x1800030e6  mov     eax, ebx
0x1800030e8  mov     rbx, [rsp+38h+arg_0]
0x1800030ed  add     rsp, 30h
0x1800030f1  pop     r14
0x1800030f3  retn
```
