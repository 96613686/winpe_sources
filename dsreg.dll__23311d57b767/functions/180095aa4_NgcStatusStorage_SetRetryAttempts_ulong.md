# NgcStatusStorage::SetRetryAttempts(ulong)

- ea: `0x180095aa4`
- end: `0x180095bf2`
- name: `?SetRetryAttempts@NgcStatusStorage@@CAJK@Z`
- size: `334`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004aa30`
- `0x180095260`

## callees

- `0x1800084f4`
- `0x18001c74c`
- `0x180043e54`
- `0x18008c2d4`
- `0x180095aa4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180095b24`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180095b24`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095bca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095bda`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095bca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095bda`

## string_xrefs

- `0x180095ada`: `OpenRootKey`
- `0x180095b39`: `RegCreateKeyExW`
- `0x180095b5e`: `%s: Failed to create or open registry key "%s\%s". Error code: 0x%08x.`
- `0x180095b57`: `NgcStatusStorage::SetRetryAttempts`
- `0x180095b9c`: `NgcStatusStorage::SetRetryAttempts`

## pseudocode

```c
__int64 __fastcall NgcStatusStorage::SetRetryAttempts(unsigned int a1)
{
  unsigned int v2; // eax
  int v3; // ebx
  const wchar_t *v4; // r8
  LSTATUS v5; // eax
  unsigned int v6; // edi
  __int64 dwOptions; // [rsp+20h] [rbp-38h]
  HKEY phkResult; // [rsp+68h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  hKey = 0;
  phkResult = 0;
  v2 = RegOpenCurrentUserKey(0x20019u, &hKey);
  v3 = v2;
  if ( v2 )
  {
    v4 = L"OpenRootKey";
  }
  else
  {
    v5 = RegCreateKeyExW(
           hKey,
           L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC",
           0,
           0,
           0,
           0x20006u,
           0,
           &phkResult,
           0);
    v3 = v5;
    if ( v5 )
    {
      Logger::WriteRegistryFailureEvent(
        v5,
        L"RegCreateKeyExW",
        L"HKEY_CURRENT_USER\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC");
      LODWORD(dwOptions) = v3;
      Logger::TraceError(
        L"%s: Failed to create or open registry key \"%s\\%s\". Error code: 0x%08x.",
        L"NgcStatusStorage::SetRetryAttempts",
        L"HKEY_CURRENT_USER",
        L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC",
        dwOptions);
      goto LABEL_8;
    }
    v6 = 0;
    v2 = RegSaveDwordValue(
           phkResult,
           0,
           L"NumOfAttRetry",
           L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC",
           a1);
    v3 = v2;
    if ( !v2 )
      goto LABEL_11;
    v4 = L"RegSaveDwordValue";
  }
  Logger::TraceError(L"%s: %s failed with win32 error code: 0x%08x.", L"NgcStatusStorage::SetRetryAttempts", v4, v2);
LABEL_8:
  if ( v3 > 0 )
    v6 = (unsigned __int16)v3 | 0x80070000;
  else
    v6 = v3;
LABEL_11:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x180095aa4  mov     rax, rsp
0x180095aa7  mov     [rax+8], rbx
0x180095aab  mov     [rax+20h], rsi
0x180095aaf  push    rdi
0x180095ab0  sub     rsp, 50h
0x180095ab4  mov     esi, ecx
0x180095ab6  mov     qword ptr [rax+18h], 0
0x180095abe  mov     ecx, 20019h; unsigned int
0x180095ac3  mov     qword ptr [rax+10h], 0
0x180095acb  lea     rdx, [rax+18h]; HKEY *
0x180095acf  call    ?RegOpenCurrentUserKey@@YAKKPEAPEAUHKEY__@@@Z; RegOpenCurrentUserKey(ulong,HKEY__ * *)
0x180095ad4  mov     ebx, eax
0x180095ad6  test    eax, eax
0x180095ad8  jz      short loc_180095AE6
0x180095ada  lea     r8, aOpenrootkey; "OpenRootKey"
0x180095ae1  jmp     loc_180095B99
0x180095ae6  mov     rcx, [rsp+58h+hKey]; hKey
0x180095aeb  lea     rax, [rsp+58h+arg_8]
0x180095af0  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x180095af9  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180095b00  mov     [rsp+58h+phkResult], rax; phkResult
0x180095b05  xor     r9d, r9d; lpClass
0x180095b08  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180095b11  xor     r8d, r8d; Reserved
0x180095b14  mov     [rsp+58h+samDesired], 20006h; samDesired
0x180095b1c  mov     dword ptr [rsp+58h+dwOptions], 0; dwOptions
0x180095b24  call    cs:__imp_RegCreateKeyExW
0x180095b2a  mov     ebx, eax
0x180095b2c  test    eax, eax
0x180095b2e  jz      short loc_180095B6C
0x180095b30  lea     r8, aHkeyCurrentUse_0; "HKEY_CURRENT_USER\\SOFTWARE\\Microsoft"...
0x180095b37  mov     ecx, eax; unsigned int
0x180095b39  lea     rdx, aRegcreatekeyex; "RegCreateKeyExW"
0x180095b40  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG0@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *)
0x180095b45  lea     r9, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180095b4c  mov     dword ptr [rsp+58h+dwOptions], ebx
0x180095b50  lea     r8, aHkeyCurrentUse; "HKEY_CURRENT_USER"
0x180095b57  lea     rdx, aNgcstatusstora_5; "NgcStatusStorage::SetRetryAttempts"
0x180095b5e  lea     rcx, aSFailedToCreat; "%s: Failed to create or open registry k"...
0x180095b65  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180095b6a  jmp     short loc_180095BAF
0x180095b6c  mov     rcx, [rsp+58h+arg_8]; HKEY
0x180095b71  lea     r9, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180095b78  lea     r8, ValueName; "NumOfAttRetry"
0x180095b7f  mov     dword ptr [rsp+58h+dwOptions], esi; unsigned int
0x180095b83  xor     edx, edx; unsigned __int16 *
0x180095b85  xor     edi, edi
0x180095b87  call    ?RegSaveDwordValue@@YAKPEAUHKEY__@@PEBG11K@Z; RegSaveDwordValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong)
0x180095b8c  mov     ebx, eax
0x180095b8e  test    eax, eax
0x180095b90  jz      short loc_180095BC0
0x180095b92  lea     r8, aRegsavedwordva; "RegSaveDwordValue"
0x180095b99  mov     r9d, eax
0x180095b9c  lea     rdx, aNgcstatusstora_5; "NgcStatusStorage::SetRetryAttempts"
0x180095ba3  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x180095baa  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180095baf  test    ebx, ebx
0x180095bb1  jg      short loc_180095BB7
0x180095bb3  mov     edi, ebx
0x180095bb5  jmp     short loc_180095BC0
0x180095bb7  movzx   edi, bx
0x180095bba  or      edi, 80070000h
0x180095bc0  mov     rcx, [rsp+58h+arg_8]; hKey
0x180095bc5  test    rcx, rcx
0x180095bc8  jz      short loc_180095BD0
0x180095bca  call    cs:__imp_RegCloseKey
0x180095bd0  mov     rcx, [rsp+58h+hKey]; hKey
0x180095bd5  test    rcx, rcx
0x180095bd8  jz      short loc_180095BE0
0x180095bda  call    cs:__imp_RegCloseKey
0x180095be0  mov     rbx, [rsp+58h+arg_0]
0x180095be5  mov     eax, edi
0x180095be7  mov     rsi, [rsp+58h+arg_18]
0x180095bec  add     rsp, 50h
0x180095bf0  pop     rdi
0x180095bf1  retn
```
