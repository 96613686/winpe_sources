# SetRegDbVersionInRegistry(__int64)

- ea: `0x18002ea9c`
- end: `0x18002ebb1`
- name: `?SetRegDbVersionInRegistry@@YAJ_J@Z`
- size: `277`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002ee0c`

## callees

- `0x18002ea9c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002eb82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002eb82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eb77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eb8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eb77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eb8a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002eb1b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002eb1b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002eb66`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002eb66`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002eb4c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002eb4c`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18002eaec`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18002eaec`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18002eb6f`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18002eb6f`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x18002eac6`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x18002eac6`

## string_xrefs

- `0x18002eaba`: `Global\__ComCatalogCache__`
- `0x18002eb0d`: `Software\Microsoft\COM3`

## pseudocode

```c
__int64 __fastcall SetRegDbVersionInRegistry(__int64 a1)
{
  HANDLE v1; // rax
  void *v2; // rsi
  volatile __int64 *v3; // rdi
  int LastError; // ebx
  __int64 Data; // [rsp+40h] [rbp+8h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp+10h] BYREF

  Data = a1;
  phkResult = 0;
  v1 = OpenFileMappingW(2u, 0, L"Global\\__ComCatalogCache__");
  v2 = v1;
  if ( v1 )
  {
    v3 = (volatile __int64 *)MapViewOfFile(v1, 2u, 0, 0, 0);
    if ( v3 )
    {
      LastError = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\COM3", 0, 0x20106u, &phkResult);
      if ( !LastError )
      {
        LastError = RegSetValueExW(phkResult, L"REGDBVersion", 0, 3u, (const BYTE *)&Data, 8u);
        if ( !LastError )
          _InterlockedExchange64(v3 + 1, Data);
        RegCloseKey(phkResult);
      }
      UnmapViewOfFile((LPCVOID)v3);
    }
    else
    {
      LastError = GetLastError();
    }
    CloseHandle(v2);
  }
  else
  {
    LastError = GetLastError();
  }
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18002ea9c  mov     rax, rsp
0x18002ea9f  mov     [rax+18h], rbx
0x18002eaa3  mov     [rax+20h], rsi
0x18002eaa7  mov     [rax+8], rcx
0x18002eaab  push    rdi
0x18002eaac  sub     rsp, 30h
0x18002eab0  xor     edx, edx; bInheritHandle
0x18002eab2  mov     qword ptr [rax+10h], 0
0x18002eaba  lea     r8, Name; "Global\\__ComCatalogCache__"
0x18002eac1  lea     ebx, [rdx+2]
0x18002eac4  mov     ecx, ebx; dwDesiredAccess
0x18002eac6  call    cs:__imp_OpenFileMappingW
0x18002eacc  mov     rsi, rax
0x18002eacf  test    rax, rax
0x18002ead2  jz      loc_18002EB8A
0x18002ead8  xor     r9d, r9d; dwFileOffsetLow
0x18002eadb  mov     [rsp+38h+dwNumberOfBytesToMap], 0; dwNumberOfBytesToMap
0x18002eae4  xor     r8d, r8d; dwFileOffsetHigh
0x18002eae7  mov     edx, ebx; dwDesiredAccess
0x18002eae9  mov     rcx, rax; hFileMappingObject
0x18002eaec  call    cs:__imp_MapViewOfFile
0x18002eaf2  mov     rdi, rax
0x18002eaf5  test    rax, rax
0x18002eaf8  jz      short loc_18002EB77
0x18002eafa  lea     rax, [rsp+38h+phkResult]
0x18002eaff  mov     r9d, 20106h; samDesired
0x18002eb05  xor     r8d, r8d; ulOptions
0x18002eb08  mov     [rsp+38h+dwNumberOfBytesToMap], rax; phkResult
0x18002eb0d  lea     rdx, SubKey; "Software\\Microsoft\\COM3"
0x18002eb14  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002eb1b  call    cs:__imp_RegOpenKeyExW
0x18002eb21  mov     ebx, eax
0x18002eb23  test    eax, eax
0x18002eb25  jnz     short loc_18002EB6C
0x18002eb27  mov     rcx, [rsp+38h+phkResult]; hKey
0x18002eb2c  lea     rax, [rsp+38h+Data]
0x18002eb31  mov     [rsp+38h+cbData], 8; cbData
0x18002eb39  lea     r9d, [rbx+3]; dwType
0x18002eb3d  xor     r8d, r8d; Reserved
0x18002eb40  mov     [rsp+38h+dwNumberOfBytesToMap], rax; lpData
0x18002eb45  lea     rdx, ValueName; "REGDBVersion"
0x18002eb4c  call    cs:__imp_RegSetValueExW
0x18002eb52  mov     ebx, eax
0x18002eb54  test    eax, eax
0x18002eb56  jnz     short loc_18002EB61
0x18002eb58  mov     rax, [rsp+38h+Data]
0x18002eb5d  xchg    rax, [rdi+8]
0x18002eb61  mov     rcx, [rsp+38h+phkResult]; hKey
0x18002eb66  call    cs:__imp_RegCloseKey
0x18002eb6c  mov     rcx, rdi; lpBaseAddress
0x18002eb6f  call    cs:__imp_UnmapViewOfFile
0x18002eb75  jmp     short loc_18002EB7F
0x18002eb77  call    cs:__imp_GetLastError
0x18002eb7d  mov     ebx, eax
0x18002eb7f  mov     rcx, rsi; hObject
0x18002eb82  call    cs:__imp_CloseHandle
0x18002eb88  jmp     short loc_18002EB92
0x18002eb8a  call    cs:__imp_GetLastError
0x18002eb90  mov     ebx, eax
0x18002eb92  test    ebx, ebx
0x18002eb94  jle     short loc_18002EB9F
0x18002eb96  movzx   ebx, bx
0x18002eb99  or      ebx, 80070000h
0x18002eb9f  mov     rsi, [rsp+38h+arg_18]
0x18002eba4  mov     eax, ebx
0x18002eba6  mov     rbx, [rsp+38h+arg_10]
0x18002ebab  add     rsp, 30h
0x18002ebaf  pop     rdi
0x18002ebb0  retn
```
